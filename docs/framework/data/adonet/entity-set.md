---
title: conjunto de entidades
ms.date: 03/30/2017
ms.assetid: 59ec6ab0-88e5-4d25-b112-7a4eccbe61f0
ms.openlocfilehash: 5a2465801c270813dd7bca2144d05fa202571153
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738425"
---
# <a name="entity-set"></a>conjunto de entidades
Um *conjunto de entidades* é um contêiner lógico para instâncias de um [tipo de entidade](entity-type.md) e instâncias de qualquer tipo derivado desse tipo de entidade. (Para obter informações sobre tipos derivados, consulte [modelo de dados de entidade: herança](entity-data-model-inheritance.md).) A relação entre um tipo de entidade e um conjunto de entidades é análoga à relação entre uma linha e uma tabela em um banco de dados relacional: como uma linha, um tipo de entidade descreve a estrutura de dados e, como uma tabela, um conjunto de entidades contém instâncias de uma determinada estrutura. Um conjunto de entidades não é um dados que modelam a compilação; não descreve a estrutura de dados. Em vez disso, um conjunto de entidades fornece uma compilação para um ambiente de hospedagem ou de armazenamento (como Common Language Runtime ou um base de dados do SQL Server) instâncias de tipo de entidade do grupo de modo que eles possam ser mapeadas em um armazenamento de dados.  
  
 Um conjunto de entidades é definido em um [contêiner de entidade](entity-container.md), que é um agrupamento lógico de conjuntos de entidades e conjuntos de [Associação](association-set.md).  
  
 Para uma instância do tipo de entidade existe em um conjunto de entidades, o seguinte deve ser verdadeira:  
  
- O tipo de qualquer instância é o mesmo como o tipo de objeto no qual o conjunto de entidades é baseado, ou o tipo de instância é um subtipo do tipo de objeto.  
  
- A [chave de entidade](entity-key.md) para a instância é exclusiva dentro do conjunto de entidades.  
  
- A instância não existir em qualquer outro conjunto de entidades.  
  
    > [!NOTE]
    > Os vários conjuntos de entidades podem ser definidos usando o mesmo tipo de entidade, mas uma instância de um tipo de dado entidade só pode existir em um conjunto de entidades.  
  
 Você não precisa definir um conjunto de entidades para cada tipo de entidade em um modelo conceitual.  
  
## <a name="example"></a>Exemplo  
 O diagrama a seguir mostra um modelo conceitual com três tipos de entidade: `Book`, `Publisher`, e `Author`.  
  
 ![Modelo de exemplo com três tipos de entidade](./media/entity-set/example-model-three-entity-types.gif)  
  
 A seguir temos de diagrama dois conjuntos de entidades (`Books` e `Publishers`) e um conjunto de associações (`PublishedBy`) com base no modelo conceitual mostrado acima. O bi no conjunto de entidades de `Books` representa uma instância do tipo de entidade `Book` em tempo de execução. Da mesma forma, PJ representa uma instância de `Publisher` no conjunto de entidades `Publishers`. BiPj representa uma instância da Associação de `PublishedBy` no conjunto de associação `PublishedBy`.  
  
 ![Captura de tela que mostra um exemplo de conjuntos.](./media/entity-set/sets-example-association.gif)  
  
 O [Entity Framework ADO.net](./ef/index.md) usa uma DSL (linguagem específica de domínio) chamada[CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)(linguagem de definição de esquema conceitual) para definir modelos conceituais. CSDL seguir define um contêiner de entidade com um conjunto de entidades para cada tipo de entidade no modelo conceitual mostrado acima. Observe que o nome e o tipo de entidade para cada conjunto de entidades são definidos usando atributos XML.  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
 É possível definir vários conjuntos de entidades por tipo (MEST). CSDL seguir define um contêiner de entidade com dois conjuntos de entidades para o tipo de entidade de `Book` :  
  
 [!code-xml[EDM_Example_Model#MESTExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books2.edmx#mestexample)]  
  
## <a name="see-also"></a>Consulte também

- [Principais conceitos do Modelo de Dados de Entidade](entity-data-model-key-concepts.md)
- [Modelo de Dados de Entidade](entity-data-model.md)
