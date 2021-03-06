---
title: Tipos de dados diversos (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Object data type [Visual Basic], data types
- data types [Visual Basic], choosing
ms.assetid: 64c71a12-9057-4dbf-baca-7379c4aada69
ms.openlocfilehash: 7e32bf158b91c23c32028eb6877bd0089a9019b2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54655043"
---
# <a name="miscellaneous-data-types-visual-basic"></a>Tipos de dados diversos (Visual Basic)
Visual Basic fornece vários tipos de dados que não estão familiarizados com números ou caracteres. Em vez disso, eles lidam com dados especializados, como Sim/não valores, valores de data/hora e endereços de objeto.  
  
 Para uma tabela que mostra uma comparação lado a lado dos tipos de dados do Visual Basic, consulte [tipos de dados](../../../../visual-basic/language-reference/data-types/index.md).  
  
## <a name="boolean-type"></a>Tipo booleano  
 O [tipo de dados Boolean](../../../../visual-basic/language-reference/data-types/boolean-data-type.md) é um valor sem sinal que é interpretado como `True` ou `False`. Sua largura de dados depende da plataforma de implementação. Se uma variável pode conter apenas valores de dois estados, como verdadeiro/falso, Sim/não ou ativado/desativado, declare-o como `Boolean`.  
  
## <a name="date-type"></a>Tipo de data  
 O [tipo de dados de data](../../../../visual-basic/language-reference/data-types/date-data-type.md) é um valor de 64 bits que contém informações de data e hora. Cada incremento representa 100 nanossegundos de tempo decorrido desde o início (12:00 AM) de 1º de janeiro do ano 1 no calendário gregoriano. Se uma variável pode conter um valor de data, um valor de tempo ou ambos, declare-o como `Date`.  
  
## <a name="object-type"></a>Tipo de Objeto  
 O [tipo de dados de objeto](../../../../visual-basic/language-reference/data-types/object-data-type.md) é um endereço de 32 bits que aponta para uma instância de objeto dentro de seu aplicativo ou em algum outro aplicativo. Um `Object` variável pode se referir a qualquer objeto que seu aplicativo reconheça, ou aos dados de qualquer tipo de dados. Isso inclui tanto *tipos de valor*, como `Integer`, `Boolean`e instâncias de estrutura, e *tipos de referência*, que são instâncias de objetos criados de classes, como `String`e <xref:System.Windows.Forms.Form>e instâncias de matriz.  
  
 Se uma variável armazena um ponteiro para uma instância de uma classe que você não souber em tempo de compilação, ou se ele pode apontar para dados de vários tipos de dados, declare-o como `Object`.  
  
 A vantagem do `Object` é do tipo de dados que você pode usá-lo para armazenar dados de qualquer tipo de dados. A desvantagem é que você provoca operações extras que levam mais tempo de execução e tornar seu aplicativo execute mais lentamente. Se você usar um `Object` variável para tipos de valor, você provoca *boxing* e *unboxing*. Se você usá-lo para tipos de referência, você provoca *ligação tardia*.  
  
## <a name="see-also"></a>Consulte também
- [Caracteres de Tipo](../../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)
- [Tipos de Dados Elementares](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [Tipos de Dados Numéricos](../../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)
- [Tipos de Dados de Caractere](../../../../visual-basic/programming-guide/language-features/data-types/character-data-types.md)
- [Solução de problemas de Tipos de Dados](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Associação Antecipada e Tardia](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
