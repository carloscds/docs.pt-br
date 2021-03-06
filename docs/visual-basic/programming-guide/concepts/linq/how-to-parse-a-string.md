---
title: 'Como: Analisar uma cadeia de caracteres (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 896e1b4b-f9bd-4975-8bc1-55b6badce1ac
ms.openlocfilehash: 513a82cbed796be42eb8e531ec71221ef0ac267f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54652443"
---
# <a name="how-to-parse-a-string-visual-basic"></a>Como: Analisar uma cadeia de caracteres (Visual Basic)
Este tópico mostra como criar uma árvore XML no C#.  
  
## <a name="example"></a>Exemplo  
 Você pode analisar uma cadeia de caracteres no Visual Basic usando o `XElement.Parse` método. No entanto, é mais eficiente usar literais XML, conforme mostrado no código a seguir, porque os literais XML não sofrem das mesmas penalidades de desempenho que a análise de XML de uma cadeia de caracteres.  
  
 Usando literais XML, você pode apenas copiar e colar o XML em seu programa em Visual Basic.  
  
> [!NOTE]
>  Analisar texto ou carregar um documento XML de um arquivo de texto é menos eficiente do que a construção funcional. Se você estiver inicializando uma árvore XML de código, o tempo do processador é menor para usar a construção funcional do que para analisar texto.  
  
```vb  
Dim contacts as XElement = _  
    <Contacts>  
        <Contact>  
            <Name>Patrick Hines</Name>  
            <Phone Type="home">206-555-0144</Phone>  
            <Phone Type="work">425-555-0145</Phone>  
            <Address>  
            <Street1>123 Main St</Street1>  
            <City>Mercer Island</City>  
            <State>WA</State>  
            <Postal>68042</Postal>  
            </Address>  
            <NetWorth>10</NetWorth>  
        </Contact>  
        <Contact>  
            <Name>Gretchen Rivas</Name>  
            <Phone Type="mobile">206-555-0163</Phone>  
            <Address>  
            <Street1>123 Main St</Street1>  
            <City>Mercer Island</City>  
            <State>WA</State>  
            <Postal>68042</Postal>  
            </Address>  
            <NetWorth>11</NetWorth>  
        </Contact>  
    </Contacts>  
```  
  
## <a name="see-also"></a>Consulte também
- [Analisando XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
