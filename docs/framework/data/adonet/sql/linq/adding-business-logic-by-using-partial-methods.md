---
title: Adicionando a lógica comercial usando métodos parciais
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3a73991e-fd4e-4610-93fb-7ced4dc6b7f9
ms.openlocfilehash: 251d7a05971ff7940f85ec9d555d26f2e57067c3
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248129"
---
# <a name="adding-business-logic-by-using-partial-methods"></a>Adicionando a lógica comercial usando métodos parciais
Você pode personalizar Visual Basic e C# código gerado em seus [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] projetos usando *métodos parciais*. O código que [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] gerencia define assinaturas como uma parte de um método parcial. Se você deseja implementar o método, você pode adicionar seu próprio método parcial. Se você não adiciona sua própria implementação, o compilador descarta a assinatura parcial de métodos e chama os métodos padrão em [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
> [!NOTE]
> Se você estiver usando o Visual Studio, poderá usar o Object Relational Designer para adicionar validação e outras personalizações a classes de entidade.  
  
 Por exemplo, o mapeamento padrão para a classe de `Customer` na base de dados de exemplo Northwind inclui o seguinte método parcial:  
  
 [!code-csharp[DLinqOverrideDefault#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/northwind.cs#2)]
 [!code-vb[DLinqOverrideDefault#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/northwind.vb#2)]  
  
 Você pode implementar seu próprio método adicionando o código como o seguinte a sua própria classe parcial de `Customer` :  
  
 [!code-csharp[DLinqOverrideDefault#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/Program.cs#3)]
 [!code-vb[DLinqOverrideDefault#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/Module1.vb#3)]  
  
 Essa abordagem é normalmente usada no [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] para substituir os métodos padrão `Insert`para `Update`, `Delete`, e para validar Propriedades durante eventos do ciclo de vida do objeto.  
  
 Para obter mais informações, consulte [partial Methods](../../../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md) (Visual Basic) ou [Partial (MethodC# ) (Reference)](../../../../../csharp/language-reference/keywords/partial-method.md) (C#).  
  
## <a name="example"></a>Exemplo  
  
### <a name="description"></a>Descrição  
 O exemplo a seguir mostra como `ExampleClass` primeiro pode ser definido por uma ferramenta de geração como SQLMetal e em seguida, como você pode implementar apenas um dos dois métodos.  
  
### <a name="code"></a>Código  
 [!code-csharp[DLinqSubmittingChanges#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#4)]
 [!code-vb[DLinqSubmittingChanges#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#4)]  
  
## <a name="example"></a>Exemplo  
  
### <a name="description"></a>Descrição  
 O exemplo a seguir usa a relação entre `Shipper` e entidades de `Order` . Observe entre os métodos métodos parciais, `InsertShipper` e `DeleteShipper`. Esses métodos substituem os métodos parciais padrão [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] fornecidos pelo mapeamento.  
  
### <a name="code"></a>Código  
 [!code-csharp[DLinqOverrideDefault#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqOverrideDefault/cs/northwind.cs#1)]
 [!code-vb[DLinqOverrideDefault#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqOverrideDefault/vb/northwind.vb#1)]  
  
## <a name="see-also"></a>Consulte também

- [Realizando e enviando alterações de dados](making-and-submitting-data-changes.md)
- [Personalizando as operações de inserção, atualização e exclusão](customizing-insert-update-and-delete-operations.md)
