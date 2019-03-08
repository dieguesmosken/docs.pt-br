---
title: RepeatButton estilos e modelos
ms.date: 03/30/2017
helpviewer_keywords:
- RepeatButton [WPF], styles and templates
- styles [WPF], RepeatButton
- templates [WPF], RepeatButton
- parts [WPF], RepeatButton
- ControlTemplate [WPF], RepeatButton
- states [WPF], RepeatButton
ms.assetid: fd340743-f44f-4990-9077-085301469670
ms.openlocfilehash: 86f212326bc707e4b07b8cab8d9a95d4f6ef8920
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57509585"
---
# <a name="repeatbutton-styles-and-templates"></a><span data-ttu-id="b6ab3-102">RepeatButton estilos e modelos</span><span class="sxs-lookup"><span data-stu-id="b6ab3-102">RepeatButton Styles and Templates</span></span>

<span data-ttu-id="b6ab3-103">Este tópico descreve os estilos e modelos para o <xref:System.Windows.Controls.Primitives.RepeatButton> controle.</span><span class="sxs-lookup"><span data-stu-id="b6ab3-103">This topic describes the styles and templates for the <xref:System.Windows.Controls.Primitives.RepeatButton> control.</span></span> <span data-ttu-id="b6ab3-104">Você pode modificar o padrão <xref:System.Windows.Controls.ControlTemplate> para dar ao controle uma aparência exclusiva.</span><span class="sxs-lookup"><span data-stu-id="b6ab3-104">You can modify the default <xref:System.Windows.Controls.ControlTemplate> to give the control a unique appearance.</span></span> <span data-ttu-id="b6ab3-105">Para obter mais informações, consulte [Personalizando a aparência de um controle existente criando um ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span><span class="sxs-lookup"><span data-stu-id="b6ab3-105">For more information, see [Customizing the Appearance of an Existing Control by Creating a ControlTemplate](customizing-the-appearance-of-an-existing-control.md).</span></span>

## <a name="repeatbutton-parts"></a><span data-ttu-id="b6ab3-106">Partes de RepeatButton</span><span class="sxs-lookup"><span data-stu-id="b6ab3-106">RepeatButton Parts</span></span>

<span data-ttu-id="b6ab3-107">O <xref:System.Windows.Controls.Primitives.RepeatButton> controle não tem nenhuma parte nomeada.</span><span class="sxs-lookup"><span data-stu-id="b6ab3-107">The <xref:System.Windows.Controls.Primitives.RepeatButton> control does not have any named parts.</span></span>

## <a name="repeatbutton-states"></a><span data-ttu-id="b6ab3-108">Estados de RepeatButton</span><span class="sxs-lookup"><span data-stu-id="b6ab3-108">RepeatButton States</span></span>

<span data-ttu-id="b6ab3-109">A tabela a seguir lista os estados visuais para o <xref:System.Windows.Controls.Primitives.RepeatButton> controle.</span><span class="sxs-lookup"><span data-stu-id="b6ab3-109">The following table lists the visual states for the <xref:System.Windows.Controls.Primitives.RepeatButton> control.</span></span>

|<span data-ttu-id="b6ab3-110">Nome do VisualState</span><span class="sxs-lookup"><span data-stu-id="b6ab3-110">VisualState Name</span></span>|<span data-ttu-id="b6ab3-111">Nome do VisualStateGroup</span><span class="sxs-lookup"><span data-stu-id="b6ab3-111">VisualStateGroup Name</span></span>|<span data-ttu-id="b6ab3-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="b6ab3-112">Description</span></span>|
|-|-|-|
|<span data-ttu-id="b6ab3-113">Normal</span><span class="sxs-lookup"><span data-stu-id="b6ab3-113">Normal</span></span>|<span data-ttu-id="b6ab3-114">CommonStates</span><span class="sxs-lookup"><span data-stu-id="b6ab3-114">CommonStates</span></span>|<span data-ttu-id="b6ab3-115">O estado padrão.</span><span class="sxs-lookup"><span data-stu-id="b6ab3-115">The default state.</span></span>|
|<span data-ttu-id="b6ab3-116">MouseOver</span><span class="sxs-lookup"><span data-stu-id="b6ab3-116">MouseOver</span></span>|<span data-ttu-id="b6ab3-117">CommonStates</span><span class="sxs-lookup"><span data-stu-id="b6ab3-117">CommonStates</span></span>|<span data-ttu-id="b6ab3-118">O ponteiro do mouse é posicionado sobre o controle.</span><span class="sxs-lookup"><span data-stu-id="b6ab3-118">The mouse pointer is positioned over the control.</span></span>|
|<span data-ttu-id="b6ab3-119">Pressionado</span><span class="sxs-lookup"><span data-stu-id="b6ab3-119">Pressed</span></span>|<span data-ttu-id="b6ab3-120">CommonStates</span><span class="sxs-lookup"><span data-stu-id="b6ab3-120">CommonStates</span></span>|<span data-ttu-id="b6ab3-121">O controle é pressionado.</span><span class="sxs-lookup"><span data-stu-id="b6ab3-121">The control is pressed.</span></span>|
|<span data-ttu-id="b6ab3-122">Disabled</span><span class="sxs-lookup"><span data-stu-id="b6ab3-122">Disabled</span></span>|<span data-ttu-id="b6ab3-123">CommonStates</span><span class="sxs-lookup"><span data-stu-id="b6ab3-123">CommonStates</span></span>|<span data-ttu-id="b6ab3-124">O controle está desabilitado.</span><span class="sxs-lookup"><span data-stu-id="b6ab3-124">The control is disabled.</span></span>|
|<span data-ttu-id="b6ab3-125">Focalizado</span><span class="sxs-lookup"><span data-stu-id="b6ab3-125">Focused</span></span>|<span data-ttu-id="b6ab3-126">FocusStates</span><span class="sxs-lookup"><span data-stu-id="b6ab3-126">FocusStates</span></span>|<span data-ttu-id="b6ab3-127">O controle tem foco.</span><span class="sxs-lookup"><span data-stu-id="b6ab3-127">The control has focus.</span></span>|
|<span data-ttu-id="b6ab3-128">Sem foco</span><span class="sxs-lookup"><span data-stu-id="b6ab3-128">Unfocused</span></span>|<span data-ttu-id="b6ab3-129">FocusStates</span><span class="sxs-lookup"><span data-stu-id="b6ab3-129">FocusStates</span></span>|<span data-ttu-id="b6ab3-130">O controle não tem foco.</span><span class="sxs-lookup"><span data-stu-id="b6ab3-130">The control does not have focus.</span></span>|
|<span data-ttu-id="b6ab3-131">Válido</span><span class="sxs-lookup"><span data-stu-id="b6ab3-131">Valid</span></span>|<span data-ttu-id="b6ab3-132">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b6ab3-132">ValidationStates</span></span>|<span data-ttu-id="b6ab3-133">O controle usa o <xref:System.Windows.Controls.Validation> classe e o <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propriedade anexada é `false`.</span><span class="sxs-lookup"><span data-stu-id="b6ab3-133">The control uses the <xref:System.Windows.Controls.Validation> class and the <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `false`.</span></span>|
|<span data-ttu-id="b6ab3-134">InvalidFocused</span><span class="sxs-lookup"><span data-stu-id="b6ab3-134">InvalidFocused</span></span>|<span data-ttu-id="b6ab3-135">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b6ab3-135">ValidationStates</span></span>|<span data-ttu-id="b6ab3-136">O <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propriedade anexada é `true` tem o controle tem foco.</span><span class="sxs-lookup"><span data-stu-id="b6ab3-136">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control has focus.</span></span>|
|<span data-ttu-id="b6ab3-137">InvalidUnfocused</span><span class="sxs-lookup"><span data-stu-id="b6ab3-137">InvalidUnfocused</span></span>|<span data-ttu-id="b6ab3-138">ValidationStates</span><span class="sxs-lookup"><span data-stu-id="b6ab3-138">ValidationStates</span></span>|<span data-ttu-id="b6ab3-139">O <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> propriedade anexada é `true` tem o controle não tem o foco.</span><span class="sxs-lookup"><span data-stu-id="b6ab3-139">The <xref:System.Windows.Controls.Validation.HasError%2A?displayProperty=nameWithType> attached property is `true` has the control does not have focus.</span></span>|

## <a name="repeatbutton-controltemplate-example"></a><span data-ttu-id="b6ab3-140">Exemplo de ControlTemplate de RepeatButton</span><span class="sxs-lookup"><span data-stu-id="b6ab3-140">RepeatButton ControlTemplate Example</span></span>

<span data-ttu-id="b6ab3-141">O exemplo a seguir mostra como definir um <xref:System.Windows.Controls.ControlTemplate> para o <xref:System.Windows.Controls.Primitives.RepeatButton> controle.</span><span class="sxs-lookup"><span data-stu-id="b6ab3-141">The following example shows how to define a <xref:System.Windows.Controls.ControlTemplate> for the <xref:System.Windows.Controls.Primitives.RepeatButton> control.</span></span>

[!code-xaml[ControlTemplateExamples#RepeatButton](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/scrollbar.xaml#repeatbutton)]

<span data-ttu-id="b6ab3-142">O exemplo anterior usa um ou mais dos seguintes recursos.</span><span class="sxs-lookup"><span data-stu-id="b6ab3-142">The preceding example uses one or more of the following resources.</span></span>

[!code-xaml[ControlTemplateExamples#Resources](~/samples/snippets/csharp/VS_Snippets_Wpf/ControlTemplateExamples/CS/resources/shared.xaml#resources)]

<span data-ttu-id="b6ab3-143">Para ver o exemplo completo, consulte [Styling with ControlTemplates Sample (Estilos com a amostra ControlTemplates)](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span><span class="sxs-lookup"><span data-stu-id="b6ab3-143">For the complete sample, see [Styling with ControlTemplates Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Styles%20&%20Templates/IntroToStylingAndTemplating).</span></span>

## <a name="see-also"></a><span data-ttu-id="b6ab3-144">Consulte também</span><span class="sxs-lookup"><span data-stu-id="b6ab3-144">See also</span></span>

- <xref:System.Windows.FrameworkElement.Style%2A>
- <xref:System.Windows.Controls.ControlTemplate>
- [<span data-ttu-id="b6ab3-145">Estilos e modelos de controle</span><span class="sxs-lookup"><span data-stu-id="b6ab3-145">Control Styles and Templates</span></span>](control-styles-and-templates.md)
- [<span data-ttu-id="b6ab3-146">Personalização do controle</span><span class="sxs-lookup"><span data-stu-id="b6ab3-146">Control Customization</span></span>](control-customization.md)
- [<span data-ttu-id="b6ab3-147">Estilo e modelagem</span><span class="sxs-lookup"><span data-stu-id="b6ab3-147">Styling and Templating</span></span>](styling-and-templating.md)
- [<span data-ttu-id="b6ab3-148">Personalizando a aparência de um controle existente criando um ControlTemplate</span><span class="sxs-lookup"><span data-stu-id="b6ab3-148">Customizing the Appearance of an Existing Control by Creating a ControlTemplate</span></span>](customizing-the-appearance-of-an-existing-control.md)