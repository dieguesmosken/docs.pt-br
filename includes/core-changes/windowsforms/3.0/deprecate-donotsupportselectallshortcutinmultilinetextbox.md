---
ms.openlocfilehash: a9d0fe3516ade04bc38b804268a9d989f6891d80
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/28/2019
ms.locfileid: "74643987"
---
### <a name="switchsystemwindowsformsdonotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported"></a><span data-ttu-id="98443-101">Não há suporte para a opção de compatibilidade switch. System. Windows. Forms. DoNotSupportSelectAllShortcutInMultilineTextBox</span><span class="sxs-lookup"><span data-stu-id="98443-101">Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported</span></span>

<span data-ttu-id="98443-102">O `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` opção de compatibilidade, que foi introduzido no .NET Framework 4.6.1, não tem suporte no Windows Forms no .NET Core 3,0.</span><span class="sxs-lookup"><span data-stu-id="98443-102">The `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` compatibility switch, which was introduced in .NET Framework 4.6.1, is not supported in Windows Forms on .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="98443-103">Alterar descrição</span><span class="sxs-lookup"><span data-stu-id="98443-103">Change description</span></span>

<span data-ttu-id="98443-104">Começando com .NET Framework 4.6.1, selecionando o <kbd>Ctrl</kbd> + <kbd>uma</kbd> tecla de atalho em um controle de <xref:System.Windows.Forms.TextBox> selecionou todo o texto.</span><span class="sxs-lookup"><span data-stu-id="98443-104">Starting with .NET Framework 4.6.1, selecting the <kbd>Ctrl</kbd> + <kbd>A</kbd> shortcut key in a <xref:System.Windows.Forms.TextBox> control selected all text.</span></span> <span data-ttu-id="98443-105">No .NET Framework 4,6 e versões anteriores, a seleção do <kbd>Ctrl</kbd> + <kbd>uma</kbd> tecla de atalho falhou ao selecionar todo o texto se as propriedades [TextBox. ShortcutsEnabled](xref:System.Windows.Forms.TextBoxBase.ShortcutsEnabled) e <xref:System.Windows.Forms.TextBox.Multiline?displayProperty=nameWithType> fossem ambas definidas como `true`.</span><span class="sxs-lookup"><span data-stu-id="98443-105">In .NET Framework 4.6 and previous versions, selecting the <kbd>Ctrl</kbd> + <kbd>A</kbd> shortcut key failed to select all text if the [Textbox.ShortcutsEnabled](xref:System.Windows.Forms.TextBoxBase.ShortcutsEnabled) and <xref:System.Windows.Forms.TextBox.Multiline?displayProperty=nameWithType> properties were both set to `true`.</span></span> <span data-ttu-id="98443-106">A opção de compatibilidade `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` foi introduzida em .NET Framework 4.6.1 para manter o comportamento original.</span><span class="sxs-lookup"><span data-stu-id="98443-106">The `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` compatibility switch was introduced in .NET Framework 4.6.1 to retain the original behavior.</span></span> <span data-ttu-id="98443-107">Para obter mais informações, consulte <xref:System.Windows.Forms.TextBox.ProcessCmdKey%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="98443-107">For more information see <xref:System.Windows.Forms.TextBox.ProcessCmdKey%2A?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="98443-108">No .NET Core, não há suporte para a opção `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox`.</span><span class="sxs-lookup"><span data-stu-id="98443-108">In .NET Core, the `Switch.System.Windows.Forms.DoNotSupportSelectAllShortcutInMultilineTextBox` switch is not supported.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="98443-109">Versão introduzida</span><span class="sxs-lookup"><span data-stu-id="98443-109">Version introduced</span></span>

<span data-ttu-id="98443-110">3,0 Preview 9</span><span class="sxs-lookup"><span data-stu-id="98443-110">3.0 Preview 9</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="98443-111">Ação recomendada</span><span class="sxs-lookup"><span data-stu-id="98443-111">Recommended action</span></span>

<span data-ttu-id="98443-112">Remova a opção.</span><span class="sxs-lookup"><span data-stu-id="98443-112">Remove the switch.</span></span> <span data-ttu-id="98443-113">Não há suporte para a opção e nenhuma funcionalidade alternativa está disponível.</span><span class="sxs-lookup"><span data-stu-id="98443-113">The switch is not supported, and no alternative functionality is available.</span></span>

#### <a name="category"></a><span data-ttu-id="98443-114">Categoria</span><span class="sxs-lookup"><span data-stu-id="98443-114">Category</span></span>

<span data-ttu-id="98443-115">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="98443-115">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="98443-116">APIs afetadas</span><span class="sxs-lookup"><span data-stu-id="98443-116">Affected APIs</span></span>

- <span data-ttu-id="98443-117">{1&gt;Nenhum&lt;1}</span><span class="sxs-lookup"><span data-stu-id="98443-117">None</span></span>

<!-- 

### Affected APIs

- Not detectable via API analysis

-->