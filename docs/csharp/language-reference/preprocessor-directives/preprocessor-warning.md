---
title: '##warning – Referência de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '#warning'
helpviewer_keywords:
- '#warning directive [C#]'
ms.assetid: e6fb496d-bb8b-4018-baf6-5b60a0c8902b
ms.openlocfilehash: 55768a354b2841021607ed40b4ef87b9767edcad
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54620312"
---
# <a name="warning-c-reference"></a>#warning (Referência de C#)
`#warning` permite gerar um aviso do compilador [CS1030](../../misc/cs1030.md) de nível um de um local específico no código. Por exemplo:  
  
```csharp
#warning Deprecated code in this method.  
```  
  
## <a name="remarks"></a>Comentários
 Um uso comum de `#warning` é em uma diretiva condicional. Também é possível gerar um erro definido pelo usuário com [#error](../../../csharp/language-reference/preprocessor-directives/preprocessor-error.md).  
  
## <a name="example"></a>Exemplo  

```csharp
// preprocessor_warning.cs  
// CS1030 expected  
#define DEBUG  
class MainClass
{  
    static void Main()
    {  
#if DEBUG  
#warning DEBUG is defined  
#endif  
    }  
}  
```  

## <a name="see-also"></a>Consulte também

- [Referência de C#](../../../csharp/language-reference/index.md)
- [Guia de Programação em C#](../../../csharp/programming-guide/index.md)
- [Diretivas do pré-processador do C#](../../../csharp/language-reference/preprocessor-directives/index.md)
