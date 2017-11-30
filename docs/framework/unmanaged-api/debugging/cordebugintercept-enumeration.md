---
title: "Enumeração CorDebugIntercept"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugIntercept
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugIntercept
helpviewer_keywords: CorDebugIntercept enumeration [.NET Framework debugging]
ms.assetid: 3d5b642e-7ef2-428b-a5ae-509c35ed461a
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b7d34b5f1bdff7a7089d780645b91503a8464849
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="cordebugintercept-enumeration"></a><span data-ttu-id="b7a73-102">Enumeração CorDebugIntercept</span><span class="sxs-lookup"><span data-stu-id="b7a73-102">CorDebugIntercept Enumeration</span></span>
<span data-ttu-id="b7a73-103">Indica os tipos de código que pode ser interceptado (isto é, entrado em).</span><span class="sxs-lookup"><span data-stu-id="b7a73-103">Indicates the types of code that can be intercepted (that is, stepped into).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7a73-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="b7a73-104">Syntax</span></span>  
  
```  
typedef enum CorDebugIntercept {  
    INTERCEPT_NONE                = 0x0,  
    INTERCEPT_CLASS_INIT          = 0x01,  
    INTERCEPT_EXCEPTION_FILTER    = 0x02,  
    INTERCEPT_SECURITY            = 0x04,  
    INTERCEPT_CONTEXT_POLICY      = 0x08,  
    INTERCEPT_INTERCEPTION        = 0x10,  
    INTERCEPT_ALL                 = 0xffff  
} CorDebugIntercept;  
```  
  
## <a name="members"></a><span data-ttu-id="b7a73-105">Membros</span><span class="sxs-lookup"><span data-stu-id="b7a73-105">Members</span></span>  
  
|<span data-ttu-id="b7a73-106">Membro</span><span class="sxs-lookup"><span data-stu-id="b7a73-106">Member</span></span>|<span data-ttu-id="b7a73-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="b7a73-107">Description</span></span>|  
|------------|-----------------|  
|`INTERCEPT_NONE`|<span data-ttu-id="b7a73-108">Nenhum código pode ser interceptado.</span><span class="sxs-lookup"><span data-stu-id="b7a73-108">No code can be intercepted.</span></span>|  
|`INTERCEPT_CLASS_INIT`|<span data-ttu-id="b7a73-109">Um construtor pode ser interceptado.</span><span class="sxs-lookup"><span data-stu-id="b7a73-109">A constructor can be intercepted.</span></span>|  
|`INTERCEPT_EXCEPTION_FILTER`|<span data-ttu-id="b7a73-110">Um filtro de exceção pode ser interceptado.</span><span class="sxs-lookup"><span data-stu-id="b7a73-110">An exception filter can be intercepted.</span></span>|  
|`INTERCEPT_SECURITY`|<span data-ttu-id="b7a73-111">Código que impõe a segurança pode ser interceptado.</span><span class="sxs-lookup"><span data-stu-id="b7a73-111">Code that enforces security can be intercepted.</span></span>|  
|`INTERCEPT_CONTEXT_POLICY`|<span data-ttu-id="b7a73-112">Uma política de contexto pode ser interceptada.</span><span class="sxs-lookup"><span data-stu-id="b7a73-112">A context policy can be intercepted.</span></span>|  
|`INTERCEPT_INTERCEPTION`|<span data-ttu-id="b7a73-113">Não usado.</span><span class="sxs-lookup"><span data-stu-id="b7a73-113">Not used.</span></span>|  
|`INTERCEPT_ALL`|<span data-ttu-id="b7a73-114">Todo o código pode ser interceptado.</span><span class="sxs-lookup"><span data-stu-id="b7a73-114">All code can be intercepted.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b7a73-115">Comentários</span><span class="sxs-lookup"><span data-stu-id="b7a73-115">Remarks</span></span>  
 <span data-ttu-id="b7a73-116">Use o [: Setinterceptmask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setinterceptmask-method.md) método para estabelecer os tipos de código que pode ser interceptado.</span><span class="sxs-lookup"><span data-stu-id="b7a73-116">Use the [ICorDebugStepper::SetInterceptMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setinterceptmask-method.md) method to establish the types of code that can be intercepted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7a73-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b7a73-117">Requirements</span></span>  
 <span data-ttu-id="b7a73-118">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7a73-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7a73-119">**Cabeçalho:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b7a73-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b7a73-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b7a73-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b7a73-121">**Versões do .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7a73-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7a73-122">Consulte também</span><span class="sxs-lookup"><span data-stu-id="b7a73-122">See Also</span></span>  
 [<span data-ttu-id="b7a73-123">Declarando enumerações</span><span class="sxs-lookup"><span data-stu-id="b7a73-123">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)