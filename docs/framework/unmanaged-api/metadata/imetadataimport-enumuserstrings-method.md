---
title: "Método IMetaDataImport::EnumUserStrings"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumUserStrings
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumUserStrings
helpviewer_keywords:
- IMetaDataImport::EnumUserStrings method [.NET Framework metadata]
- EnumUserStrings method [.NET Framework metadata]
ms.assetid: 2b1f1418-4be8-4cdb-b418-b3abccc527a7
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 48ec44d993c5cdc2c545125bf8b4bcb80e413f95
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportenumuserstrings-method"></a><span data-ttu-id="f1909-102">Método IMetaDataImport::EnumUserStrings</span><span class="sxs-lookup"><span data-stu-id="f1909-102">IMetaDataImport::EnumUserStrings Method</span></span>
<span data-ttu-id="f1909-103">Enumera os tokens de cadeia de caracteres que representa a cadeias de caracteres codificadas no escopo atual de metadados.</span><span class="sxs-lookup"><span data-stu-id="f1909-103">Enumerates String tokens representing hard-coded strings in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1909-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="f1909-104">Syntax</span></span>  
  
```  
HRESULT EnumUserStrings (  
   [in, out]  HCORENUM    *phEnum,  
   [out]  mdString        rStrings[],  
   [in]   ULONG           cMax,  
   [out]  ULONG           *pcStrings  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f1909-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="f1909-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="f1909-106">[out no] Um ponteiro para o enumerador.</span><span class="sxs-lookup"><span data-stu-id="f1909-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="f1909-107">Isso deve ser NULL para a primeira chamada do método.</span><span class="sxs-lookup"><span data-stu-id="f1909-107">This must be NULL for the first call of this method.</span></span>  
  
 `rStrings`  
 <span data-ttu-id="f1909-108">[out] A matriz usada para armazenar os tokens de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="f1909-108">[out] The array used to store the String tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="f1909-109">[in] O tamanho máximo da `rStrings` matriz.</span><span class="sxs-lookup"><span data-stu-id="f1909-109">[in] The maximum size of the `rStrings` array.</span></span>  
  
 `pcStrings`  
 <span data-ttu-id="f1909-110">[out] O número de tokens de cadeia de caracteres retornados em `rStrings`.</span><span class="sxs-lookup"><span data-stu-id="f1909-110">[out] The number of String tokens returned in `rStrings`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f1909-111">Valor de retorno</span><span class="sxs-lookup"><span data-stu-id="f1909-111">Return Value</span></span>  
  
|<span data-ttu-id="f1909-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f1909-112">HRESULT</span></span>|<span data-ttu-id="f1909-113">Descrição</span><span class="sxs-lookup"><span data-stu-id="f1909-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="f1909-114">`EnumUserStrings`retornou com êxito.</span><span class="sxs-lookup"><span data-stu-id="f1909-114">`EnumUserStrings` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="f1909-115">Não há nenhum tokens para enumerar.</span><span class="sxs-lookup"><span data-stu-id="f1909-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="f1909-116">Nesse caso, `pcStrings` é zero.</span><span class="sxs-lookup"><span data-stu-id="f1909-116">In that case, `pcStrings` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f1909-117">Comentários</span><span class="sxs-lookup"><span data-stu-id="f1909-117">Remarks</span></span>  
 <span data-ttu-id="f1909-118">Os tokens de cadeia de caracteres são criados pelo [: Defineuserstring](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="f1909-118">The String tokens are created by the [IMetaDataEmit::DefineUserString](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) method.</span></span> <span data-ttu-id="f1909-119">Esse método foi projetado para ser usado por um navegador de metadados em vez de um compilador.</span><span class="sxs-lookup"><span data-stu-id="f1909-119">This method is designed to be used by a metadata browser rather than by a compiler.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1909-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f1909-120">Requirements</span></span>  
 <span data-ttu-id="f1909-121">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1909-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1909-122">**Cabeçalho:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f1909-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f1909-123">**Biblioteca:** incluído como um recurso no MSCOREE</span><span class="sxs-lookup"><span data-stu-id="f1909-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f1909-124">**Versões do .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1909-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1909-125">Consulte também</span><span class="sxs-lookup"><span data-stu-id="f1909-125">See Also</span></span>  
 [<span data-ttu-id="f1909-126">Interface IMetaDataImport</span><span class="sxs-lookup"><span data-stu-id="f1909-126">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="f1909-127">Interface IMetaDataImport2</span><span class="sxs-lookup"><span data-stu-id="f1909-127">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)