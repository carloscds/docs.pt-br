---
title: tipo de associação
ms.date: 03/30/2017
ms.assetid: 26c409f6-06e8-4441-ac78-1b1076a3c005
ms.openlocfilehash: 3b01e053a1d61e2ce413ae6683d350b77c402fb5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54714588"
---
# <a name="association-type"></a>tipo de associação
Uma *tipo de associação* (também chamado de uma associação) é o bloco de construção fundamental para descrever relações no modelo de dados de entidade (EDM). Em um modelo conceitual, uma associação representa uma relação entre dois [tipos de entidade](../../../../docs/framework/data/adonet/entity-type.md) (como `Customer` e `Order`). Em um aplicativo, uma instância de uma associação representa uma associação específica (como uma associação entre uma instância de `Customer` e uma instância de `Order`). Instâncias de associação são agrupadas logicamente em um [conjunto de associações](../../../../docs/framework/data/adonet/association-set.md).  
  
 Uma definição de associação contém as informações a seguir:  
  
-   Um nome exclusivo. (Necessário)  
  
-   Duas [extremidades de associação](../../../../docs/framework/data/adonet/association-end.md), um para cada tipo de entidade na relação. (Necessário)  
  
    > [!NOTE]
    >  Uma associação não pode representar uma relação entre mais de dois tipos de entidade. Uma associação pode, no entanto, definir uma dica relação especificando o mesmo tipo de entidade para cada um das extremidades de associação.  
  
-   Um [restrição de integridade referencial](../../../../docs/framework/data/adonet/referential-integrity-constraint.md). (Opcional)  
  
 Cada extremidade da associação deve especificar um [multiplicidade do final da associação](../../../../docs/framework/data/adonet/association-end-multiplicity.md) que indica o número de instâncias do tipo de entidade que pode estar em uma extremidade da associação. Uma multiplicidade de extremidades de associação pode ter um valor igual a um (1), a zero ou a um (0..1) ou a muitos (*). Instâncias do tipo de entidade em uma extremidade de uma associação podem ser acessadas por meio [propriedades de navegação](../../../../docs/framework/data/adonet/navigation-property.md) ou chaves estrangeiras se são expostos em um tipo de entidade. Para obter mais informações, consulte [modelo de dados de entidade: Chaves estrangeiras](../../../../docs/framework/data/adonet/foreign-key-property.md).  
  
## <a name="example"></a>Exemplo  
 O diagrama a seguir mostra um modelo conceitual com duas associações: `PublishedBy` e `WrittenBy`. Terminar a associação para associação de `PublishedBy` são os tipos de entidade de `Book` e de `Publisher` . A multiplicidade do final de `Publisher` é um (1) e a multiplicidade do final de `Book` é muitas (*), indicando que publica um editor muitos livros e um livro é publicado por um editor.  
  
 ![Modelo de exemplo](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")  
  
 O [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) usa uma linguagem específica de domínio (DSL) chamada linguagem de definição de esquema conceitual ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) para definir modelos conceituais. CSDL seguir define a associação de `PublishedBy` mostrada no diagrama anterior:  
  
 [!code-xml[EDM_Example_Model#AssociationExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#associationexample)]  
  
## <a name="see-also"></a>Consulte também
- [Principais conceitos do Modelo de Dados de Entidade](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [Modelo de Dados de Entidade](../../../../docs/framework/data/adonet/entity-data-model.md)
