---
title: Método ICorProfilerCallback2::GarbageCollectionStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.GarbageCollectionStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::GarbageCollectionStarted
helpviewer_keywords:
- GarbageCollectionStarted method [.NET Framework profiling]
- ICorProfilerCallback2::GarbageCollectionStarted method [.NET Framework profiling]
ms.assetid: 44eef087-f21f-4fe2-b481-f8a0ee022e7d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6c610445d5467a49b8a50b279d8f7fe706e21f73
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54555655"
---
# <a name="icorprofilercallback2garbagecollectionstarted-method"></a>Método ICorProfilerCallback2::GarbageCollectionStarted
Notifica o criador de perfil de código que iniciou a coleta de lixo.  
  
## <a name="syntax"></a>Sintaxe  
  
```  
HRESULT GarbageCollectionStarted(  
    [in] int cGenerations,  
    [in, size_is(cGenerations), length_is(cGenerations)] BOOL generationCollected[],  
    [in] COR_PRF_GC_REASON reason);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `cGenerations`  
 [in] O número total de entradas na `generationCollected` matriz.  
  
 `generationCollected`  
 [in] Uma matriz de valores boolianos, que são `true` se a geração que corresponde ao índice da matriz está sendo coletado por essa coleta de lixo; caso contrário, `false`.  
  
 A matriz é indexada por um valor de [COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md) enumeração, que indica a geração.  
  
 `reason`  
 [in] Um valor igual a [COR_PRF_GC_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-reason-enumeration.md) enumeração que indica o motivo pelo qual a coleta de lixo foi induzida.  
  
## <a name="remarks"></a>Comentários  
 Todos os retornos de chamada que pertencem a essa coleta de lixo ocorrer entre o `GarbageCollectionStarted` retorno de chamada e o correspondente [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) retorno de chamada. Esses retornos de chamada não precisam ocorrer no mesmo thread.  
  
 É seguro para o criador de perfil inspecionar objetos em seus locais originais durante o `GarbageCollectionStarted` retorno de chamada. O coletor de lixo começará a movimentação de objetos após o retorno de `GarbageCollectionStarted`. Depois que o criador de perfil tem retornados desse retorno de chamada, o criador de perfil deve considerar todas as IDs de objeto como inválido até que ele receba um `ICorProfilerCallback2::GarbageCollectionFinished` retorno de chamada.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Confira [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Cabeçalho:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versões do .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte também
- [Interface ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [Interface ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
