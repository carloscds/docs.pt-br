---
title: Método ISymUnmanagedDocument::GetSourceRange
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDocument.GetSourceRange
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDocument::GetSourceRange
helpviewer_keywords:
- ISymUnmanagedDocument::GetSourceRange method [.NET Framework debugging]
- GetSourceRange method [.NET Framework debugging]
ms.assetid: 20fefee7-1040-41ba-93dc-bd42f68b90c2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a89c706ece0949ffa3c182d53b57221acf81b18d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54515058"
---
# <a name="isymunmanageddocumentgetsourcerange-method"></a>Método ISymUnmanagedDocument::GetSourceRange
Retorna o intervalo especificado da origem inserida para o buffer fornecido. O buffer deve ser grande o suficiente para manter o código-fonte.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
HRESULT GetSourceRange(  
    [in]  ULONG32  startLine,  
    [in]  ULONG32  startColumn,  
    [in]  ULONG32  endLine,  
    [in]  ULONG32  endColumn,  
    [in]  ULONG32  cSourceBytes,  
    [out] ULONG32  *pcSourceBytes,  
    [out, size_is(cSourceBytes),  
        length_is(*pcSourceBytes)] BYTE source[]);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `startLine`  
 [in] A linha inicial no documento atual.  
  
 `startColumn`  
 [in] A coluna inicial no documento atual.  
  
 `endLine`  
 [in] A linha final no documento atual.  
  
 `endColumn`  
 [in] A coluna final no documento atual.  
  
 `cSourceBytes`  
 [in] O tamanho da fonte, em bytes.  
  
 `pcSourceBytes`  
 [out] Um ponteiro para uma variável que recebe o tamanho da fonte.  
  
 `source`  
 [out] O tamanho e o comprimento do intervalo especificado do documento de origem, em bytes.  
  
## <a name="return-value"></a>Valor de retorno  
 S_OK se o método for bem-sucedido.  
  
## <a name="see-also"></a>Consulte também
- [Interface ISymUnmanagedDocument](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
