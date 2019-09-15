---
title: 'Como: Obter informações de tipo e membro usando reflexão'
ms.date: 09/03/2019
helpviewer_keywords:
- reflection, obtaining member information
- types [.NET Framework], obtaining member information from
ms.assetid: 348ae651-ccda-4f13-8eda-19e8337e9438
author: rpetrusha
ms.author: ronpet
dev_langs:
- cpp
- csharp
- vb
ms.openlocfilehash: da71845ea276267220636cfd661465ea02b2b50d
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/13/2019
ms.locfileid: "70972917"
---
# <a name="how-to-get-type-and-member-information-by-using-reflection"></a><span data-ttu-id="b6b10-102">Como: Obter informações de tipo e membro usando reflexão</span><span class="sxs-lookup"><span data-stu-id="b6b10-102">How to: Get type and member information by using reflection</span></span>
<span data-ttu-id="b6b10-103">O <xref:System.Reflection> namespace contém muitos métodos para obter informações sobre tipos e seus membros.</span><span class="sxs-lookup"><span data-stu-id="b6b10-103">The <xref:System.Reflection> namespace contains many methods for obtaining information about types and their members.</span></span> <span data-ttu-id="b6b10-104">Este artigo demonstra um desses métodos, <xref:System.Type.GetMembers%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b6b10-104">This article demonstrates one of these methods, <xref:System.Type.GetMembers%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="b6b10-105">Para obter informações adicionais, consulte [visão geral de reflexão](reflection.md).</span><span class="sxs-lookup"><span data-stu-id="b6b10-105">For additional information, see [Reflection overview](reflection.md).</span></span>
  
## <a name="example"></a><span data-ttu-id="b6b10-106">Exemplo</span><span class="sxs-lookup"><span data-stu-id="b6b10-106">Example</span></span>

<span data-ttu-id="b6b10-107">O exemplo a seguir obtém informações de tipo e membro usando reflexão:</span><span class="sxs-lookup"><span data-stu-id="b6b10-107">The following example obtains type and member information by using reflection:</span></span>

[!code-cpp[Get type members](../../../samples/snippets/standard/reflection/memberinfo/gettypemembers.cpp)]
[!code-csharp[Get type members](../../../samples/snippets/standard/reflection/memberinfo/gettypemembers.cs)]
[!code-vb[Get type members](../../../samples/snippets/standard/reflection/memberinfo/gettypemembers.vb)]

## <a name="see-also"></a><span data-ttu-id="b6b10-108">Consulte também</span><span class="sxs-lookup"><span data-stu-id="b6b10-108">See also</span></span>

- [<span data-ttu-id="b6b10-109">Programa com domínios de aplicativo</span><span class="sxs-lookup"><span data-stu-id="b6b10-109">Program with application domains</span></span>](../app-domains/application-domains.md#programming-with-application-domains)
- [<span data-ttu-id="b6b10-110">Reflexão</span><span class="sxs-lookup"><span data-stu-id="b6b10-110">Reflection</span></span>](reflection.md)
- [<span data-ttu-id="b6b10-111">Usar domínios de aplicativo</span><span class="sxs-lookup"><span data-stu-id="b6b10-111">Use application domains</span></span>](../app-domains/use.md)