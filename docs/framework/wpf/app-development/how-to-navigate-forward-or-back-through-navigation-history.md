---
title: 'Como: Navegar para frente ou para trás por meio do histórico de navegação'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- history [WPF], navigating forward
- navigation [WPF], through navigation history (forward)
ms.assetid: 5939d574-5f53-469e-85f5-1f2b13607caa
ms.openlocfilehash: 76a78debdce14123cc465ac9abf4db906fe0a2df
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69961346"
---
# <a name="how-to-navigate-forward-or-back-through-navigation-history"></a>Como: Navegar para frente ou para trás por meio do histórico de navegação
Este exemplo ilustra como navegar para frente ou para trás nas entradas no histórico de navegação.  
  
## <a name="example"></a>Exemplo  
 Código executado do conteúdo dos seguintes hosts pode navegar para frente ou para trás no histórico de navegação, uma entrada de cada vez.  
  
- <xref:System.Windows.Navigation.NavigationWindow>usando<xref:System.Windows.Navigation.NavigationService>  
  
- <xref:System.Windows.Controls.Frame>usando<xref:System.Windows.Navigation.NavigationService>  
  
- Internet Explorer  
  
 Para poder navegar para frente em uma entrada, primeiro verifique se existem entradas no histórico de navegação progressiva inspecionando a propriedade **CanGoForward**. Para navegar para frente em uma entrada, chame o método **GoForward**. Isso é ilustrado no exemplo a seguir:  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateForwardCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigateforwardcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateForwardCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigateforwardcode)]  
  
 Para poder navegar para trás em uma entrada, primeiro verifique se há entradas no histórico de navegação de retorno inspecionando a propriedade **CanGoBack**. Para navegar para trás em uma entrada, chame o método **GoBack**. Isso é ilustrado no exemplo a seguir:  
  
 [!code-csharp[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTONavigationSnippets/CSharp/HomePage.xaml.cs#navigatebackcode)]
 [!code-vb[HOWTONavigationSnippets#NavigateBackCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTONavigationSnippets/visualbasic/homepage.xaml.vb#navigatebackcode)]  
  
 **CanGoForward**, **GoForward**, CanGoBack e **GoBack** são implementados pelo <xref:System.Windows.Navigation.NavigationWindow>, <xref:System.Windows.Controls.Frame>e. <xref:System.Windows.Navigation.NavigationService>  
  
> [!NOTE]
> Se você chamar **GoForward**e não houver entradas no histórico de navegação progressiva, ou se você chamar **GoBack**, e não houver entradas no histórico de navegação de volta, um <xref:System.InvalidOperationException> será lançado.
