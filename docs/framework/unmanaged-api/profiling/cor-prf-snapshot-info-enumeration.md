---
title: "COR_PRF_SNAPSHOT_INFO 列挙型"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_SNAPSHOT_INFO
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_SNAPSHOT_INFO
helpviewer_keywords: COR_PRF_SNAPSHOT_INFO enumeration [.NET Framework profiling]
ms.assetid: a5906b2a-ad4a-4cc6-a421-2d7d8adf7468
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a9c854360881426f2fc7fc9e401da1dc93b9bd84
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="corprfsnapshotinfo-enumeration"></a><span data-ttu-id="2fc5b-102">COR_PRF_SNAPSHOT_INFO 列挙型</span><span class="sxs-lookup"><span data-stu-id="2fc5b-102">COR_PRF_SNAPSHOT_INFO Enumeration</span></span>
<span data-ttu-id="2fc5b-103">プロファイラーの各呼び出しにスタック スナップショットを使用して渡すデータをバックアップする作業がどの程度を示す[StackSnapshotCallback](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md)関数。</span><span class="sxs-lookup"><span data-stu-id="2fc5b-103">Specifies how much data to pass back with a stack snapshot in each call to the profiler's [StackSnapshotCallback](../../../../docs/framework/unmanaged-api/profiling/stacksnapshotcallback-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2fc5b-104">構文</span><span class="sxs-lookup"><span data-stu-id="2fc5b-104">Syntax</span></span>  
  
```  
typedef enum _COR_PRF_SNAPSHOT_INFO {  
    COR_PRF_SNAPSHOT_DEFAULT = 0x0,  
    COR_PRF_SNAPSHOT_REGISTER_CONTEXT = 0x1,  
    COR_PRF_SNAPSHOT_X86_OPTIMIZED = 0X2  
} COR_PRF_SNAPSHOT_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="2fc5b-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="2fc5b-105">Members</span></span>  
  
|<span data-ttu-id="2fc5b-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="2fc5b-106">Members</span></span>|<span data-ttu-id="2fc5b-107">説明</span><span class="sxs-lookup"><span data-stu-id="2fc5b-107">Description</span></span>|  
|-------------|-----------------|  
|`COR_PRF_SNAPSHOT_DEFAULT`|<span data-ttu-id="2fc5b-108">すべての値を渡す必要があることを示します`StackSnapshotCallback`パラメーターを除く、`context`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="2fc5b-108">Indicates that values must be passed for all `StackSnapshotCallback` parameters, except the `context` parameter.</span></span>|  
|`COR_PRF_SNAPSHOT_REGISTER_CONTEXT`|<span data-ttu-id="2fc5b-109">すべての値を渡す必要があることを示します`StackSnapshotCallback`などのパラメーター、`context`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="2fc5b-109">Indicates that values must be passed for all `StackSnapshotCallback` parameters, including the `context` parameter.</span></span>|  
|`COR_PRF_SNAPSHOT_X86_OPTIMIZED`|<span data-ttu-id="2fc5b-110">単純化し、別のスタック ウォーク アルゴリズムを使用することを示します。</span><span class="sxs-lookup"><span data-stu-id="2fc5b-110">Indicates that a simpler, alternative stack-walking algorithm will be used.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2fc5b-111">コメント</span><span class="sxs-lookup"><span data-stu-id="2fc5b-111">Remarks</span></span>  
 <span data-ttu-id="2fc5b-112">によって指定された値を`COR_PRF_SNAPSHOT_INFO`へのパラメーターとして渡される列挙型、 [DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)メソッドです。</span><span class="sxs-lookup"><span data-stu-id="2fc5b-112">Values that are provided by the `COR_PRF_SNAPSHOT_INFO` enumeration are passed as parameters to the [DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2fc5b-113">要件</span><span class="sxs-lookup"><span data-stu-id="2fc5b-113">Requirements</span></span>  
 <span data-ttu-id="2fc5b-114">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="2fc5b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2fc5b-115">**ヘッダー** : CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2fc5b-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2fc5b-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2fc5b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2fc5b-117">**.NET framework のバージョン:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2fc5b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fc5b-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="2fc5b-118">See Also</span></span>  
 [<span data-ttu-id="2fc5b-119">DoStackSnapshot メソッド</span><span class="sxs-lookup"><span data-stu-id="2fc5b-119">DoStackSnapshot Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)  
 [<span data-ttu-id="2fc5b-120">列挙体のプロファイリング</span><span class="sxs-lookup"><span data-stu-id="2fc5b-120">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)