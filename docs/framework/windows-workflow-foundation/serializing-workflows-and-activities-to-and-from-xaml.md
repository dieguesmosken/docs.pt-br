---
title: Serializando fluxos de trabalho e atividades para e do XAML
description: Este artigo é uma visão geral de como serializar definições de fluxo de trabalho e trabalhar com definições de fluxo de trabalhos XAML no Workflow Foundation.
ms.date: 03/30/2017
ms.assetid: 37685b32-24e3-4d72-88d8-45d5fcc49ec2
ms.openlocfilehash: 168dbc9a36cfa80c15fddc7481e986d1ce383adb
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421339"
---
# <a name="serialize-workflows-and-activities-to-and-from-xaml"></a>Serializar fluxos de trabalho e atividades de e para XAML

Além de serem construídas em tipos contidos nos assemblies, as definições de fluxo de trabalho também podem ser serializadas para XAML. Essas definições serializadas possam ser recarregadas para edição ou inspeção, podem ser passadas para um sistema de compilação ou carregadas e chamadas. Este tópico fornece uma visão geral de como serializar definições de fluxo de trabalho e trabalhar com definições de fluxo de trabalho XAML.

## <a name="work-with-xaml-workflow-definitions"></a>Trabalhar com definições de fluxo de trabalho XAML

Para criar uma definição de fluxo de trabalho para serialização, a classe <xref:System.Activities.ActivityBuilder> é usada. Criar um <xref:System.Activities.ActivityBuilder> é bem semelhante a criar um <xref:System.Activities.DynamicActivity>. Todos os argumentos desejados são especificados, e as atividades que constituem o comportamento são configuradas. No exemplo a seguir, uma atividade `Add` é criada e usa dois argumentos de entrada, adiciona-os juntos e retorna o resultado. Como essa atividade retorna um resultado, a classe genérica <xref:System.Activities.ActivityBuilder%601> é usada.

[!code-csharp[CFX_WorkflowApplicationExample#41](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#41)]

Cada uma das instâncias <xref:System.Activities.DynamicActivityProperty> representa um dos argumentos de entrada para o fluxo de trabalho, e <xref:System.Activities.ActivityBuilder.Implementation%2A> contém as atividades que compõem a lógica do fluxo de trabalho. Observe que as expressões de valor r neste exemplo são expressões do Visual Basic. As expressões lambda não são serializáveis para XAML a menos que <xref:System.Activities.Expressions.ExpressionServices.Convert%2A> seja usado. Se os fluxos de trabalho serializados devem ser abertos ou editados no designer de fluxo de trabalho, Visual Basic expressões devem ser usadas. Para obter mais informações, consulte [criando fluxos de trabalho, atividades e expressões usando código imperativo](authoring-workflows-activities-and-expressions-using-imperative-code.md).

Para serializar a definição de fluxo de trabalho representada pela instância <xref:System.Activities.ActivityBuilder> para XAML, use <xref:System.Activities.XamlIntegration.ActivityXamlServices> para criar um <xref:System.Xaml.XamlWriter> e, em seguida, use <xref:System.Xaml.XamlServices> para serializar a definição de fluxo de trabalho usando o <xref:System.Xaml.XamlWriter>. <xref:System.Activities.XamlIntegration.ActivityXamlServices>tem métodos para mapear <xref:System.Activities.ActivityBuilder> instâncias de e para XAML e para carregar fluxos de trabalho XAML e retornar um <xref:System.Activities.DynamicActivity> que pode ser invocado. No exemplo a seguir, a <xref:System.Activities.ActivityBuilder> instância do exemplo anterior é serializada para uma cadeia de caracteres e salva em um arquivo.

```csharp
// Serialize the workflow to XAML and store it in a string.
StringBuilder sb = new StringBuilder();
StringWriter tw = new StringWriter(sb);
XamlWriter xw = ActivityXamlServices.CreateBuilderWriter(new XamlXmlWriter(tw, new XamlSchemaContext()));
XamlServices.Save(xw, ab);
string serializedAB = sb.ToString();

// Display the XAML to the console.
Console.WriteLine(serializedAB);

// Serialize the workflow to XAML and save it to a file.
StreamWriter sw = File.CreateText(@"C:\Workflows\add.xaml");
XamlWriter xw2 = ActivityXamlServices.CreateBuilderWriter(new XamlXmlWriter(sw, new XamlSchemaContext()));
XamlServices.Save(xw2, ab);
sw.Close();
```

O exemplo a seguir representa o fluxo de trabalho serializado.

```xaml
<Activity
  x:TypeArguments="x:Int32"
  x:Class="Add"
  xmlns="http://schemas.microsoft.com/netfx/2009/xaml/activities"
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">
  <x:Members>
    <x:Property Name="Operand1" Type="InArgument(x:Int32)" />
    <x:Property Name="Operand2" Type="InArgument(x:Int32)" />
  </x:Members>
  <Sequence>
    <WriteLine Text="[Operand1.ToString() + " + " + Operand2.ToString()]" />
    <Assign x:TypeArguments="x:Int32" Value="[Operand1 + Operand2]">
      <Assign.To>
        <OutArgument x:TypeArguments="x:Int32">
          <ArgumentReference x:TypeArguments="x:Int32" ArgumentName="Result" />
          </OutArgument>
      </Assign.To>
    </Assign>
  </Sequence>
</Activity>
```

Para carregar um fluxo de trabalho serializado, use o <xref:System.Activities.XamlIntegration.ActivityXamlServices> <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A> método. Isso utiliza a definição de fluxo de trabalho serializado e retorna um <xref:System.Activities.DynamicActivity> que representa a definição de fluxo de trabalho. Observe que o XAML não é desserializado até que <xref:System.Activities.Activity.CacheMetadata%2A> seja chamado no corpo do <xref:System.Activities.DynamicActivity> durante o processo de validação. Se a validação não for chamada explicitamente, ela será executada quando o fluxo de trabalho for invocado. Se a definição de fluxo de trabalho XAML for inválida, uma exceção <xref:System.ArgumentException> será gerada. Todas as exceções geradas de <xref:System.Activities.Activity.CacheMetadata%2A> escapam da chamada para <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> e devem ser tratadas pelo chamador. No exemplo a seguir, o fluxo de trabalho serializado do exemplo anterior é carregado e é chamado usando <xref:System.Activities.WorkflowInvoker>.

[!code-csharp[CFX_WorkflowApplicationExample#43](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#43)]

Quando esse fluxo de trabalho é chamado, a seguinte saída é exibida no console.

**25 + 15**\
**40**

> [!NOTE]
> Para obter mais informações sobre como invocar fluxos de trabalho com argumentos de entrada e saída, consulte [usando WorkflowInvoker e WorkflowApplication](using-workflowinvoker-and-workflowapplication.md) e <xref:System.Activities.WorkflowInvoker.Invoke%2A> .

Se o fluxo de trabalho serializado contiver expressões C#, uma <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings> instância com sua <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> propriedade definida como `true` deve ser passada como um parâmetro para <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A?displayProperty=nameWithType> , caso contrário, uma <xref:System.NotSupportedException> será lançada com uma mensagem semelhante à seguinte: o **tipo de atividade de expressão ' csharpvalue ' 1 ' requer compilação para ser executado.  Verifique se o fluxo de trabalho foi compilado.**

```csharp
ActivityXamlServicesSettings settings = new ActivityXamlServicesSettings
{
    CompileExpressions = true
};

DynamicActivity<int> wf = ActivityXamlServices.Load(new StringReader(serializedAB), settings) as DynamicActivity<int>;
```

Para obter mais informações, consulte [expressões C#](csharp-expressions.md).

Uma definição de fluxo de trabalho serializada também pode ser carregada em uma <xref:System.Activities.ActivityBuilder> instância usando o <xref:System.Activities.XamlIntegration.ActivityXamlServices> <xref:System.Activities.XamlIntegration.ActivityXamlServices.CreateBuilderReader%2A> método. Depois que um fluxo de trabalho serializado é carregado em uma <xref:System.Activities.ActivityBuilder> instância, ele pode ser inspecionado e modificado. Isso é útil para autores do designer do fluxo de trabalho personalizado e fornece um mecanismo para salvar e recarregar definições de fluxo de trabalho durante o processo de design. No exemplo a seguir, a definição do fluxo de trabalho serializado do exemplo anterior é carregada e suas propriedades são inspecionadas.

[!code-csharp[CFX_WorkflowApplicationExample#44](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#44)]
