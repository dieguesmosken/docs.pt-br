---
title: Alterações recentes – .NET Framework para o .NET Core
description: Lista as alterações significativas de .NET Framework para o .NET Core.
ms.date: 12/18/2019
ms.openlocfilehash: 9f4ecc8a9de7279bb4b222b3df77e1eb17b33f0a
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937386"
---
# <a name="breaking-changes-for-migration-from-net-framework-to-net-core"></a><span data-ttu-id="f0942-103">Alterações recentes de migração do .NET Framework para o .NET Core</span><span class="sxs-lookup"><span data-stu-id="f0942-103">Breaking changes for migration from .NET Framework to .NET Core</span></span>

<span data-ttu-id="f0942-104">Se você estiver migrando um aplicativo do .NET Framework para o .NET Core, as alterações significativas listadas neste artigo poderão afetar você.</span><span class="sxs-lookup"><span data-stu-id="f0942-104">If you're migrating an app from .NET Framework to .NET Core, the breaking changes listed in this article may affect you.</span></span> <span data-ttu-id="f0942-105">As alterações significativas são agrupadas por categoria e dentro dessas categorias, pela versão do .NET Core em que foram introduzidas.</span><span class="sxs-lookup"><span data-stu-id="f0942-105">Breaking changes are grouped by category, and within those categories, by the version of .NET Core they were introduced in.</span></span>

> [!NOTE]
> <span data-ttu-id="f0942-106">Este artigo não é uma lista completa de alterações significativas entre o .NET Framework e o .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f0942-106">This article is not a complete list of breaking changes between .NET Framework and .NET Core.</span></span> <span data-ttu-id="f0942-107">As alterações significativas mais importantes são adicionadas aqui, pois estamos cientes delas.</span><span class="sxs-lookup"><span data-stu-id="f0942-107">The most important breaking changes are added here as we become aware of them.</span></span>

## <a name="corefx"></a><span data-ttu-id="f0942-108">CoreFx</span><span class="sxs-lookup"><span data-stu-id="f0942-108">CoreFx</span></span>

<span data-ttu-id="f0942-109">Alterações da falha:</span><span class="sxs-lookup"><span data-stu-id="f0942-109">Breaking changes:</span></span>

- [<span data-ttu-id="f0942-110">Alteração no valor padrão de UseShellExecute</span><span class="sxs-lookup"><span data-stu-id="f0942-110">Change in default value of UseShellExecute</span></span>](#change-in-default-value-of-useshellexecute)

***

### <a name="net-core-21"></a><span data-ttu-id="f0942-111">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="f0942-111">.NET Core 2.1</span></span>

[!INCLUDE[Process.Start changes](~/includes/core-changes/corefx/2.1/process-start-changes.md)]

***

## <a name="windows-forms"></a><span data-ttu-id="f0942-112">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f0942-112">Windows Forms</span></span>

<span data-ttu-id="f0942-113">Windows Forms suporte foi adicionado ao .NET Core na versão 3,0.</span><span class="sxs-lookup"><span data-stu-id="f0942-113">Windows Forms support was added to .NET Core in version 3.0.</span></span> <span data-ttu-id="f0942-114">Se você estiver migrando um aplicativo Windows Forms do .NET Framework para o .NET Core, as alterações significativas listadas aqui podem afetar seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="f0942-114">If you're migrating a Windows Forms app from .NET Framework to .NET Core, the breaking changes listed here may affect your app.</span></span>

<span data-ttu-id="f0942-115">Alterações da falha:</span><span class="sxs-lookup"><span data-stu-id="f0942-115">Breaking changes:</span></span>

- [<span data-ttu-id="f0942-116">Controles removidos</span><span class="sxs-lookup"><span data-stu-id="f0942-116">Removed controls</span></span>](#removed-controls)
- [<span data-ttu-id="f0942-117">Evento CellFormatting não gerado se ToolTip for mostrado</span><span class="sxs-lookup"><span data-stu-id="f0942-117">CellFormatting event not raised if tooltip is shown</span></span>](#cellformatting-event-not-raised-if-tooltip-is-shown)
- [<span data-ttu-id="f0942-118">Control. DefaultFont alterado para Segoe UI 9 pt</span><span class="sxs-lookup"><span data-stu-id="f0942-118">Control.DefaultFont changed to Segoe UI 9 pt</span></span>](#default-control-font-changed-to-segoe-ui-9-pt)
- [<span data-ttu-id="f0942-119">Modernização do FolderBrowserDialog</span><span class="sxs-lookup"><span data-stu-id="f0942-119">Modernization of the FolderBrowserDialog</span></span>](#modernization-of-the-folderbrowserdialog)
- [<span data-ttu-id="f0942-120">SerializableAttribute removido de alguns tipos de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f0942-120">SerializableAttribute removed from some Windows Forms types</span></span>](#serializableattribute-removed-from-some-windows-forms-types)
- [<span data-ttu-id="f0942-121">Não há suporte para a opção de compatibilidade AllowUpdateChildControlIndexForTabControls</span><span class="sxs-lookup"><span data-stu-id="f0942-121">AllowUpdateChildControlIndexForTabControls compatibility switch not supported</span></span>](#allowupdatechildcontrolindexfortabcontrols-compatibility-switch-not-supported)
- [<span data-ttu-id="f0942-122">Não há suporte para a opção de compatibilidade DomainUpDown. UseLegacyScrolling</span><span class="sxs-lookup"><span data-stu-id="f0942-122">DomainUpDown.UseLegacyScrolling compatibility switch not supported</span></span>](#domainupdownuselegacyscrolling-compatibility-switch-not-supported)
- [<span data-ttu-id="f0942-123">Não há suporte para a opção de compatibilidade DoNotLoadLatestRichEditControl</span><span class="sxs-lookup"><span data-stu-id="f0942-123">DoNotLoadLatestRichEditControl compatibility switch not supported</span></span>](#donotloadlatestricheditcontrol-compatibility-switch-not-supported)
- [<span data-ttu-id="f0942-124">Não há suporte para a opção de compatibilidade DoNotSupportSelectAllShortcutInMultilineTextBox</span><span class="sxs-lookup"><span data-stu-id="f0942-124">DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported</span></span>](#donotsupportselectallshortcutinmultilinetextbox-compatibility-switch-not-supported)
- [<span data-ttu-id="f0942-125">Não há suporte para a opção de compatibilidade DontSupportReentrantFilterMessage</span><span class="sxs-lookup"><span data-stu-id="f0942-125">DontSupportReentrantFilterMessage compatibility switch not supported</span></span>](#dontsupportreentrantfiltermessage-compatibility-switch-not-supported)
- [<span data-ttu-id="f0942-126">Não há suporte para a opção de compatibilidade EnableVisualStyleValidation</span><span class="sxs-lookup"><span data-stu-id="f0942-126">EnableVisualStyleValidation compatibility switch not supported</span></span>](#enablevisualstylevalidation-compatibility-switch-not-supported)
- [<span data-ttu-id="f0942-127">Não há suporte para a opção de compatibilidade UseLegacyContextMenuStripSourceControlValue</span><span class="sxs-lookup"><span data-stu-id="f0942-127">UseLegacyContextMenuStripSourceControlValue compatibility switch not supported</span></span>](#uselegacycontextmenustripsourcecontrolvalue-compatibility-switch-not-supported)
- [<span data-ttu-id="f0942-128">Não há suporte para a opção de compatibilidade UseLegacyImages</span><span class="sxs-lookup"><span data-stu-id="f0942-128">UseLegacyImages compatibility switch not supported</span></span>](#uselegacyimages-compatibility-switch-not-supported)
- [<span data-ttu-id="f0942-129">Alteração de acesso para AccessibleObject. RuntimeIDFirstItem</span><span class="sxs-lookup"><span data-stu-id="f0942-129">Change of access for AccessibleObject.RuntimeIDFirstItem</span></span>](#change-of-access-for-accessibleobjectruntimeidfirstitem)
- [<span data-ttu-id="f0942-130">APIs duplicadas removidas do Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f0942-130">Duplicated APIs removed from Windows Forms</span></span>](#duplicated-apis-removed-from-windows-forms)

### <a name="net-core-31"></a><span data-ttu-id="f0942-131">.NET Core 3,1</span><span class="sxs-lookup"><span data-stu-id="f0942-131">.NET Core 3.1</span></span>

[!INCLUDE[Removed controls](~/includes/core-changes/windowsforms/3.1/remove-controls-3.1.md)]

***

[!INCLUDE[CellFormatting event](~/includes/core-changes/windowsforms/3.1/cellformatting-event-not-raised.md)]

***

### <a name="net-core-30"></a><span data-ttu-id="f0942-132">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="f0942-132">.NET Core 3.0</span></span>

[!INCLUDE[Control.DefaultFont changed to Segoe UI 9 pt](~/includes/core-changes/windowsforms/3.0/control-defaultfont-changed.md)]

***

[!INCLUDE[Modernization of the FolderBrowserDialog](~/includes/core-changes/windowsforms/3.0/modernized-folderbrowserdialog.md)]

***

[!INCLUDE[SerializableAttribute removed from some Windows Forms types](~/includes/core-changes/windowsforms/3.0/remove-serializationattribute.md)]

***

[!INCLUDE[AllowUpdateChildControlIndexForTabControls compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-allowupdatechildcontrolindexfortabcontrols.md)]

***

[!INCLUDE[DomainUpDown.UseLegacyScrolling compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacyscrolling.md)]

***

[!INCLUDE[DoNotLoadLatestRichEditControl compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-donotloadlatestricheditcontrol.md)]

***

[!INCLUDE[DoNotSupportSelectAllShortcutInMultilineTextBox compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-donotsupportselectallshortcutinmultilinetextbox.md)]

***

[!INCLUDE[DontSupportReentrantFilterMessage compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-dontsupportreentrantfiltermessage.md)]

***

[!INCLUDE[EnableVisualStyleValidation compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-enablevisualstylevalidation.md)]

***

[!INCLUDE[UseLegacyContextMenuStripSourceControlValue compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacycontextmenustripsourcecontrolvalue.md)]

***

[!INCLUDE[UseLegacyImages compatibility switch not supported](~/includes/core-changes/windowsforms/3.0/deprecate-uselegacyimages.md)]

***

[!INCLUDE[Change of access for AccessibleObject.RuntimeIDFirstItem](~/includes/core-changes/windowsforms/3.0/changed-access-for-runtimeidfirstitem.md)]

***

[!INCLUDE[Duplicated APIs removed from Windows Forms](~/includes/core-changes/windowsforms/3.0/remove-duplicated-apis.md)]

***

## <a name="see-also"></a><span data-ttu-id="f0942-133">Veja também</span><span class="sxs-lookup"><span data-stu-id="f0942-133">See also</span></span>

- [<span data-ttu-id="f0942-134">APIs que sempre lançam exceções no .NET Core</span><span class="sxs-lookup"><span data-stu-id="f0942-134">APIs that always throw exceptions on .NET Core</span></span>](unsupported-apis.md)
- [<span data-ttu-id="f0942-135">.NET Framework tecnologias não disponíveis no .NET Core</span><span class="sxs-lookup"><span data-stu-id="f0942-135">.NET Framework technologies unavailable on .NET Core</span></span>](../porting/net-framework-tech-unavailable.md)