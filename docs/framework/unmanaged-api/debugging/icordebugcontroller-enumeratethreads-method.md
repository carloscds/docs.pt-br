---
title: Método ICorDebugController::EnumerateThreads
ms.date: 03/30/2017
api_name:
- ICorDebugController.EnumerateThreads
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::EnumerateThreads
helpviewer_keywords:
- ICorDebugController::EnumerateThreads method [.NET Framework debugging]
- EnumerateThreads method [.NET Framework debugging]
ms.assetid: 73f536f6-4668-4a4a-b3e4-ac7df862d5be
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d73a82ddbb15ba7895f1e5e10f7066909a3c7e43
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54697135"
---
# <a name="icordebugcontrollerenumeratethreads-method"></a>Método ICorDebugController::EnumerateThreads
Obtém um enumerador para os Active Directory threads gerenciados no processo.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
HRESULT EnumerateThreads (  
    [out] ICorDebugThreadEnum **ppThreads  
);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `ppThreads`  
 [out] Um ponteiro para o endereço de um objeto de "ICorDebugThreadEnum" que representa um enumerador para todos os threads gerenciados que estão ativos no processo.  
  
## <a name="remarks"></a>Comentários  
 Um thread é considerado ativo após o [icordebugmanagedcallback:: CreateThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md) retorno de chamada foi distribuído e antes do [icordebugmanagedcallback:: ExitThread](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitthread-method.md) foi distribuído de retorno de chamada . Um thread gerenciado não pode ter necessariamente quadros gerenciados na sua pilha. Threads podem ser enumerados mesmo antes de [icordebugmanagedcallback:: CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) retorno de chamada. A enumeração naturalmente estará vazia.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Confira [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versões do .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte também

