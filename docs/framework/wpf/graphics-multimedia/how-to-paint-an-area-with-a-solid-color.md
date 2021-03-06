---
title: Como pintar uma área com uma cor sólida
ms.date: 03/30/2017
helpviewer_keywords:
- solid colors [WPF], painting with
- brushes [WPF], painting with solid colors
- painting [WPF], with solid colors
ms.assetid: 5d27d8a7-4bd7-4063-bdf3-2c5c0f19f9d3
ms.openlocfilehash: be28a0af04c4e43cdf745a5429468aee99e34c40
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78849516"
---
# <a name="how-to-paint-an-area-with-a-solid-color"></a>Como pintar uma área com uma cor sólida
Para pintar uma área com uma cor sólida, você pode <xref:System.Windows.Media.Brushes.Red%2A> <xref:System.Windows.Media.Brushes.Blue%2A>usar um pincel de <xref:System.Windows.Media.SolidColorBrush> sistema <xref:System.Windows.Media.SolidColorBrush.Color%2A> predefinido, como ou , ou você pode criar um novo e descrever seus valores alfa, vermelho, verde e azul. Em XAML, você também pode pintar uma área com uma cor sólida usando notação hexadecimal.  
  
 Os exemplos a seguir usam cada <xref:System.Windows.Shapes.Rectangle> uma dessas técnicas para pintar um azul.  
  
## <a name="example"></a>Exemplo  
 **Usando um pincel predefinido**  
  
 No exemplo a seguir, <xref:System.Windows.Media.Brushes.Blue%2A> usa o pincel predefinido para pintar um azul retângulo.  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_PredefinedBrush1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_predefinedbrush1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_PredefinedBrush1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_predefinedbrush1)]  
  
 **Usando notação Hexadecimal**  
  
 O exemplo a seguir, usa a notação hexadecimal de 8 dígitos para pintar um retângulo de azul.  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_HexNotation8Digit1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_hexnotation8digit1)]  
  
 **Usando valores ARGB**  
  
 O próximo exemplo <xref:System.Windows.Media.SolidColorBrush> cria a <xref:System.Windows.Media.SolidColorBrush.Color%2A> e descreve seu uso dos valores ARGB para a cor azul.  
  
 [!code-xaml[brushsamples_snip#_graphicsmm_RgbNotation1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_snip/CS/SolidColorBrushExample.xaml#_graphicsmm_rgbnotation1)]  
  
 [!code-csharp[brushsamples_procedural_snip#_graphicsmm_RgbNotation1](~/samples/snippets/csharp/VS_Snippets_Wpf/brushsamples_procedural_snip/CSharp/SolidColorBrushExample.cs#_graphicsmm_rgbnotation1)]  
  
 Para outras formas de <xref:System.Windows.Media.Color> descrever a cor, consulte a estrutura.  
  
 **Tópicos Relacionados**  
  
 Para obter <xref:System.Windows.Media.SolidColorBrush> mais informações e exemplos adicionais, consulte a visão geral da [pintura com cores sólidas e de resumo de gradientes.](painting-with-solid-colors-and-gradients-overview.md)  
  
 Este exemplo de código é parte de <xref:System.Windows.Media.SolidColorBrush> um exemplo maior fornecido para a classe. Para obter o exemplo completo, consulte [Brushes Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes) (Exemplo de pincéis).  
  
## <a name="see-also"></a>Confira também

- <xref:System.Windows.Media.Brushes>
