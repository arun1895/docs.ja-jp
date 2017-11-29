---
title: "IAssemblyCache::QueryAssemblyInfo メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IAssemblyCache.QueryAssemblyInfo
api_location: fusion.dll
api_type: COM
f1_keywords: IAssemblyCache::QueryAssemblyInfo
helpviewer_keywords:
- IAssemblyCache::QueryAssemblyInfo method [.NET Framework fusion]
- QueryAssemblyInfo method [.NET Framework fusion]
ms.assetid: 09313cb5-06f6-43bd-94f4-1055c6b0c99a
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 567ff7fc5b9038c4af9aa04e3a07d9585adf44fa
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2017
---
# <a name="iassemblycachequeryassemblyinfo-method"></a><span data-ttu-id="92e3e-102">IAssemblyCache::QueryAssemblyInfo メソッド</span><span class="sxs-lookup"><span data-stu-id="92e3e-102">IAssemblyCache::QueryAssemblyInfo Method</span></span>
<span data-ttu-id="92e3e-103">指定したアセンブリについて、要求されたデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="92e3e-103">Gets the requested data about the specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92e3e-104">構文</span><span class="sxs-lookup"><span data-stu-id="92e3e-104">Syntax</span></span>  
  
```  
HRESULT QueryAssemblyInfo (  
    [in] DWORD dwFlags,  
    [in] LPCWSTR pszAssemblyName,  
    [in, out] ASSEMBLY_INFO *pAsmInfo  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="92e3e-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="92e3e-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="92e3e-106">[in]ものがありますで定義されているフラグです。</span><span class="sxs-lookup"><span data-stu-id="92e3e-106">[in] Flags defined in Fusion.idl.</span></span> <span data-ttu-id="92e3e-107">次の値がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="92e3e-107">The following values are supported:</span></span>  
  
-   <span data-ttu-id="92e3e-108">QUERYASMINFO_FLAG_VALIDATE (0X00000001)</span><span class="sxs-lookup"><span data-stu-id="92e3e-108">QUERYASMINFO_FLAG_VALIDATE (0x00000001)</span></span>  
  
-   <span data-ttu-id="92e3e-109">QUERYASMINFO_FLAG_GETSIZE (0X00000002)</span><span class="sxs-lookup"><span data-stu-id="92e3e-109">QUERYASMINFO_FLAG_GETSIZE (0x00000002)</span></span>  
  
 `pszAssemblyName`  
 <span data-ttu-id="92e3e-110">[in]データの取得対象のアセンブリの名前。</span><span class="sxs-lookup"><span data-stu-id="92e3e-110">[in] The name of the assembly for which data will be retrieved.</span></span>  
  
 `pAsmInfo`  
 <span data-ttu-id="92e3e-111">[入力、出力].[ASSEMBLY_INFO](../../../../docs/framework/unmanaged-api/fusion/assembly-info-structure.md)アセンブリについてのデータを格納する構造体。</span><span class="sxs-lookup"><span data-stu-id="92e3e-111">[in, out] An [ASSEMBLY_INFO](../../../../docs/framework/unmanaged-api/fusion/assembly-info-structure.md) structure that contains data about the assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92e3e-112">要件</span><span class="sxs-lookup"><span data-stu-id="92e3e-112">Requirements</span></span>  
 <span data-ttu-id="92e3e-113">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="92e3e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92e3e-114">**ヘッダー:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="92e3e-114">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="92e3e-115">**.NET framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92e3e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92e3e-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="92e3e-116">See Also</span></span>  
 [<span data-ttu-id="92e3e-117">IAssemblyCache インターフェイス</span><span class="sxs-lookup"><span data-stu-id="92e3e-117">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)