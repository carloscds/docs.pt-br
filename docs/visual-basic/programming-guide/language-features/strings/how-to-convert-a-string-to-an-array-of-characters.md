---
title: 'Como: Converter uma cadeia de caracteres em uma matriz de caracteres no Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- character arrays [Visual Basic], converting strings
- arrays [Visual Basic], converting strings to
- examples [Visual Basic], string conversion
- strings [Visual Basic], converting to arrays
- string conversion [Visual Basic], arrays
ms.assetid: 1b54b686-ab29-413b-adce-6bd5422376eb
ms.openlocfilehash: 9d68e3d90c52d6a4312ccb7c0c9610968e7a4b55
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54603749"
---
# <a name="how-to-convert-a-string-to-an-array-of-characters-in-visual-basic"></a>Como: Converter uma cadeia de caracteres em uma matriz de caracteres no Visual Basic
Às vezes é útil ter dados sobre os caracteres na cadeia de caracteres e as posições desses caracteres na cadeia de caracteres, como quando você estiver analisando uma cadeia de caracteres. Este exemplo mostra como obter uma matriz de caracteres em uma cadeia de caracteres chamando a cadeia de caracteres <xref:System.String.ToCharArray%2A> método.  
  
## <a name="example"></a>Exemplo  
 Este exemplo demonstra como dividir uma cadeia de caracteres em uma `Char` matriz e como dividir uma cadeia de caracteres em um `String` matriz de seus caracteres de texto Unicode. A razão para essa distinção é que os caracteres de texto Unicode podem ser compostos de duas ou mais `Char` caracteres (como um par substituto ou uma combinação sequência de caracteres). Para obter mais informações, consulte <xref:System.Globalization.TextElementEnumerator> e [o padrão Unicode](https://www.unicode.org/standard/standard.html).  
  
 [!code-vb[VbVbalrStrings#75](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-convert-a-string-to-an-array-of-characters_1.vb)]  
  
## <a name="example"></a>Exemplo  
 É mais difícil dividir uma cadeia de caracteres em seus caracteres de texto Unicode, mas isso é necessário se você precisar de informações sobre a representação visual de uma cadeia de caracteres. Este exemplo usa o <xref:System.Globalization.StringInfo.SubstringByTextElements%2A> método para obter informações sobre os caracteres de texto Unicode que compõem uma cadeia de caracteres.  
  
 [!code-vb[VbVbalrStrings#76](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-convert-a-string-to-an-array-of-characters_2.vb)]  
  
## <a name="see-also"></a>Consulte também
- <xref:System.String.Chars%2A>
- <xref:System.Globalization.StringInfo?displayProperty=nameWithType>
- [Como: Caracteres de acesso em cadeias de caracteres](../../../../visual-basic/programming-guide/language-features/strings/how-to-access-characters-in-strings.md)
- [Convertendo cadeias de caracteres em outros tipos de dados no Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/converting-between-strings-and-other-data-types.md)
- [Cadeias de Caracteres](../../../../visual-basic/programming-guide/language-features/strings/index.md)
