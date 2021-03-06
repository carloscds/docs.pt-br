---
title: 'Exceções: A função failwith'
description: Saiba como a função 'failwith' gera um F# exceção.
ms.date: 05/16/2016
ms.openlocfilehash: 05d385ddfc98a910779a6f59949a7187c38f0812
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/19/2018
ms.locfileid: "53610106"
---
# <a name="exceptions-the-failwith-function"></a>Exceções: A função failwith

O `failwith` função gera uma F# exceção.

## <a name="syntax"></a>Sintaxe

```fsharp
failwith error-message-string
```

## <a name="remarks"></a>Comentários

O *sequência de mensagem de erro* na sintaxe anterior é uma cadeia de caracteres literal ou um valor do tipo `string`. Ele se torna o `Message` propriedade da exceção.

A exceção que é gerada pelo `failwith` é um `System.Exception` exceção, que é uma referência que tem o nome `Failure` em F# código. O código a seguir ilustra o uso de `failwith` para lançar uma exceção.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet6001.fs)]

## <a name="see-also"></a>Consulte também

- [Tratamento de Exceção](index.md)
- [Tipos de Exceção](exception-types.md)
- [Exceções: O `try...with` expressão](the-try-with-expression.md)
- [Exceções: O `try...finally` expressão](the-try-finally-expression.md)
- [Exceções: a função `raise`](the-raise-function.md)