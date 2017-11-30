---
title: "Enumeração AssemblyOptions"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: AssemblyOptions
api_location: alink.dll
api_type: COM
f1_keywords: AssemblyOptions
helpviewer_keywords:
- Alink API, AssemblyOptions enumeration
- AssemblyOptions enumeration
ms.assetid: 84f83921-64cb-49e3-ac8b-22a0b77b18a8
topic_type: apiref
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ccbbcabd3fbb372322ca6334f6ab6db4fdafc2f1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="assemblyoptions-enumeration"></a><span data-ttu-id="509a4-102">Enumeração AssemblyOptions</span><span class="sxs-lookup"><span data-stu-id="509a4-102">AssemblyOptions Enumeration</span></span>
<span data-ttu-id="509a4-103">Enumera as opções de assembly.</span><span class="sxs-lookup"><span data-stu-id="509a4-103">Enumerates the assembly options.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="509a4-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="509a4-104">Syntax</span></span>  
  
```  
typedef enum _AssemblyOptions {  
    optAssemTitle = 0,  
    optAssemDescription,  
    optAssemConfig,  
    optAssemOS,  
    optAssemProcessor,  
    optAssemLocale,  
    optAssemVersion,  
    optAssemCompany,  
    optAssemProduct,  
    optAssemProductVersion,  
    optAssemCopyright,  
    optAssemTrademark,  
    optAssemKeyFile,  
    optAssemKeyName,  
    optAssemAlgID,  
    optAssemFlags,  
    optAssemHalfSign,  
    optAssemFileVersion,  
    optAssemSatelliteVer,  
    optLastAssemOption  
}   AssemblyOptions;  
```  
  
## <a name="fields"></a><span data-ttu-id="509a4-105">Campos</span><span class="sxs-lookup"><span data-stu-id="509a4-105">Fields</span></span>  
  
|<span data-ttu-id="509a4-106">Campo</span><span class="sxs-lookup"><span data-stu-id="509a4-106">Field</span></span>|<span data-ttu-id="509a4-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="509a4-107">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="509a4-108">optAssemTitle</span><span class="sxs-lookup"><span data-stu-id="509a4-108">optAssemTitle</span></span>|<span data-ttu-id="509a4-109">Cadeia de caracteres – representa o título do assembly.</span><span class="sxs-lookup"><span data-stu-id="509a4-109">String - Represents the assembly title.</span></span>|  
|<span data-ttu-id="509a4-110">optAssemDescription</span><span class="sxs-lookup"><span data-stu-id="509a4-110">optAssemDescription</span></span>|<span data-ttu-id="509a4-111">Cadeia de caracteres - contém a descrição do assembly.</span><span class="sxs-lookup"><span data-stu-id="509a4-111">String - Contains the assembly description.</span></span>|  
|<span data-ttu-id="509a4-112">optAssemConfig</span><span class="sxs-lookup"><span data-stu-id="509a4-112">optAssemConfig</span></span>|<span data-ttu-id="509a4-113">Cadeia de caracteres - contém a configuração de assembly.</span><span class="sxs-lookup"><span data-stu-id="509a4-113">String - Contains the assembly configuration.</span></span>|  
|<span data-ttu-id="509a4-114">optAssemOS</span><span class="sxs-lookup"><span data-stu-id="509a4-114">optAssemOS</span></span>|<span data-ttu-id="509a4-115">Cadeia de caracteres - codificada como: "dwOSPlatformId.dwOSMajorVersion.dwOSMinorVersion".</span><span class="sxs-lookup"><span data-stu-id="509a4-115">String - Encoded as: "dwOSPlatformId.dwOSMajorVersion.dwOSMinorVersion".</span></span>|  
|<span data-ttu-id="509a4-116">optAssemProcessor</span><span class="sxs-lookup"><span data-stu-id="509a4-116">optAssemProcessor</span></span>|<span data-ttu-id="509a4-117">ULONG</span><span class="sxs-lookup"><span data-stu-id="509a4-117">ULONG</span></span>|  
|<span data-ttu-id="509a4-118">optAssemLocale</span><span class="sxs-lookup"><span data-stu-id="509a4-118">optAssemLocale</span></span>|<span data-ttu-id="509a4-119">Cadeia de caracteres - contém a localidade de assembly.</span><span class="sxs-lookup"><span data-stu-id="509a4-119">String - Contains the assembly locale.</span></span>|  
|<span data-ttu-id="509a4-120">optAssemVersion</span><span class="sxs-lookup"><span data-stu-id="509a4-120">optAssemVersion</span></span>|<span data-ttu-id="509a4-121">Cadeia de caracteres - codificada como: "Revision".</span><span class="sxs-lookup"><span data-stu-id="509a4-121">String - Encoded as: "Major.Minor.Build.Revision".</span></span>|  
|<span data-ttu-id="509a4-122">optAssemCompany</span><span class="sxs-lookup"><span data-stu-id="509a4-122">optAssemCompany</span></span>|<span data-ttu-id="509a4-123">Cadeia de caracteres - contém a empresa.</span><span class="sxs-lookup"><span data-stu-id="509a4-123">String - Contains the company.</span></span>|  
|<span data-ttu-id="509a4-124">optAssemProduct</span><span class="sxs-lookup"><span data-stu-id="509a4-124">optAssemProduct</span></span>|<span data-ttu-id="509a4-125">Cadeia de caracteres - contém o nome do produto.</span><span class="sxs-lookup"><span data-stu-id="509a4-125">String - Contains the product name.</span></span>|  
|<span data-ttu-id="509a4-126">optAssemProductVersion</span><span class="sxs-lookup"><span data-stu-id="509a4-126">optAssemProductVersion</span></span>|<span data-ttu-id="509a4-127">Cadeia de caracteres (também conhecido como InformationalVersion).</span><span class="sxs-lookup"><span data-stu-id="509a4-127">String (also known as InformationalVersion).</span></span>|  
|<span data-ttu-id="509a4-128">optAssemCopyright</span><span class="sxs-lookup"><span data-stu-id="509a4-128">optAssemCopyright</span></span>|<span data-ttu-id="509a4-129">Cadeia de caracteres - contém as informações de direitos autorais.</span><span class="sxs-lookup"><span data-stu-id="509a4-129">String - Contains the copyright information.</span></span>|  
|<span data-ttu-id="509a4-130">optAssemTrademark</span><span class="sxs-lookup"><span data-stu-id="509a4-130">optAssemTrademark</span></span>|<span data-ttu-id="509a4-131">Cadeia de caracteres - contém as informações de marca comercial.</span><span class="sxs-lookup"><span data-stu-id="509a4-131">String - Contains the trademark information.</span></span>|  
|<span data-ttu-id="509a4-132">optAssemKeyFile</span><span class="sxs-lookup"><span data-stu-id="509a4-132">optAssemKeyFile</span></span>|<span data-ttu-id="509a4-133">Cadeia de caracteres (nome de arquivo).</span><span class="sxs-lookup"><span data-stu-id="509a4-133">String (file name).</span></span>|  
|<span data-ttu-id="509a4-134">optAssemKeyName</span><span class="sxs-lookup"><span data-stu-id="509a4-134">optAssemKeyName</span></span>|<span data-ttu-id="509a4-135">Cadeia de caracteres (o nome da chave).</span><span class="sxs-lookup"><span data-stu-id="509a4-135">String (The key name).</span></span>|  
|<span data-ttu-id="509a4-136">optAssemAlgID</span><span class="sxs-lookup"><span data-stu-id="509a4-136">optAssemAlgID</span></span>|<span data-ttu-id="509a4-137">ULONG</span><span class="sxs-lookup"><span data-stu-id="509a4-137">ULONG</span></span>|  
|<span data-ttu-id="509a4-138">optAssemFlags</span><span class="sxs-lookup"><span data-stu-id="509a4-138">optAssemFlags</span></span>|<span data-ttu-id="509a4-139">ULONG</span><span class="sxs-lookup"><span data-stu-id="509a4-139">ULONG</span></span>|  
|<span data-ttu-id="509a4-140">optAssemHalfSign</span><span class="sxs-lookup"><span data-stu-id="509a4-140">optAssemHalfSign</span></span>|<span data-ttu-id="509a4-141">Bool (também conhecido como DelaySign).</span><span class="sxs-lookup"><span data-stu-id="509a4-141">Bool (Also known as DelaySign).</span></span>|  
|<span data-ttu-id="509a4-142">optAssemFileVersion</span><span class="sxs-lookup"><span data-stu-id="509a4-142">optAssemFileVersion</span></span>|<span data-ttu-id="509a4-143">Cadeia de caracteres - codificada como "Revision" – mesmo que ProductVersion.</span><span class="sxs-lookup"><span data-stu-id="509a4-143">String - Encoded as "Major.Minor.Build.Revision"--same as ProductVersion.</span></span>|  
|<span data-ttu-id="509a4-144">optAssemSatelliteVer</span><span class="sxs-lookup"><span data-stu-id="509a4-144">optAssemSatelliteVer</span></span>|<span data-ttu-id="509a4-145">Cadeia de caracteres - codificada como "Revision".</span><span class="sxs-lookup"><span data-stu-id="509a4-145">String - Encoded as "Major.Minor.Build.Revision".</span></span>|  
|<span data-ttu-id="509a4-146">optLastAssemOption</span><span class="sxs-lookup"><span data-stu-id="509a4-146">optLastAssemOption</span></span>|<span data-ttu-id="509a4-147">Um contador do número de elementos.</span><span class="sxs-lookup"><span data-stu-id="509a4-147">A counter of the number of elements.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="509a4-148">Requisitos</span><span class="sxs-lookup"><span data-stu-id="509a4-148">Requirements</span></span>  
 <span data-ttu-id="509a4-149">**Cabeçalho:** alink.h</span><span class="sxs-lookup"><span data-stu-id="509a4-149">**Header:** alink.h</span></span>  
  
 <span data-ttu-id="509a4-150">**Biblioteca**: arquivo</span><span class="sxs-lookup"><span data-stu-id="509a4-150">**Library**: alink.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="509a4-151">Consulte também</span><span class="sxs-lookup"><span data-stu-id="509a4-151">See Also</span></span>  
 [<span data-ttu-id="509a4-152">Al.exe (Assembly Linker)</span><span class="sxs-lookup"><span data-stu-id="509a4-152">Al.exe (Assembly Linker)</span></span>](../../../../docs/framework/tools/al-exe-assembly-linker.md)