---
title: "ICorDebugProcess5::EnableNGENPolicy メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess5::EnableNGenPolicy
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess5::EnableNGENPolicy
helpviewer_keywords:
- ICorDebugProcess5::EnableNGENPolicy method [.NET Framework debugging]
- EnableNGENPolicy method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 3b8e15ca-3c72-4685-a937-da4c739cb9e9
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: cd259308494e1a86f0a6cdec8866bb66a1614b76
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess5enablengenpolicy-method"></a><span data-ttu-id="79477-102">ICorDebugProcess5::EnableNGENPolicy メソッド</span><span class="sxs-lookup"><span data-stu-id="79477-102">ICorDebugProcess5::EnableNGENPolicy Method</span></span>
<span data-ttu-id="79477-103">アプリケーションがマネージ デバッガーで実行中にネイティブ イメージを読み込む方法を決定する値を設定します。</span><span class="sxs-lookup"><span data-stu-id="79477-103">Sets a value that determines how an application loads native images while running under a managed debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79477-104">構文</span><span class="sxs-lookup"><span data-stu-id="79477-104">Syntax</span></span>  
  
```  
HRESULT EnableNGENPolicy(  
    [in] CorDebugNGENPolicy ePolicy  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="79477-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="79477-105">Parameters</span></span>  
 `ePolicy`  
 <span data-ttu-id="79477-106">[in]A [CorDebugNGenPolicy](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md)アプリケーションがマネージ デバッガーで実行中にネイティブ イメージを読み込む方法を決定する定数。</span><span class="sxs-lookup"><span data-stu-id="79477-106">[in] A [CorDebugNGenPolicy](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md) constant that determines how an application loads native images while running under a managed debugger.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="79477-107">コメント</span><span class="sxs-lookup"><span data-stu-id="79477-107">Remarks</span></span>  
 <span data-ttu-id="79477-108">メソッドを返しますのかどうか、ポリシーは正常に設定、`S_OK`です。</span><span class="sxs-lookup"><span data-stu-id="79477-108">If the policy is set successfully, the method returns `S_OK`.</span></span> <span data-ttu-id="79477-109">場合`ePolicy`によって定義された列挙値の範囲外である[CorDebugNGenPolicy](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md)、メソッドを返します`E_INVALIDARG`メソッドの呼び出しには影響しません。</span><span class="sxs-lookup"><span data-stu-id="79477-109">If `ePolicy` is outside the range of the enumerated values defined by [CorDebugNGenPolicy](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md), the method returns `E_INVALIDARG` and the method call has no effect.</span></span> <span data-ttu-id="79477-110">ネイティブ イメージ ジェネレーター (Ngen.exe) のポリシーを更新できないかどうか、メソッドを返します`E_FAIL`です。</span><span class="sxs-lookup"><span data-stu-id="79477-110">If the policy of the Native Image Generator (Ngen.exe) cannot be updated, the method returns `E_FAIL`.</span></span>  
  
 <span data-ttu-id="79477-111">`ICorDebugProcess5::EnableNGenPolicy`メソッドは、プロセスの有効期間中にいつでも呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="79477-111">The `ICorDebugProcess5::EnableNGenPolicy` method can be called at any time during the lifetime of the process.</span></span> <span data-ttu-id="79477-112">ポリシーは有効で、ポリシーを設定した後に読み込まれる任意のモジュールです。</span><span class="sxs-lookup"><span data-stu-id="79477-112">The policy is in effect for any modules that are loaded after the policy is set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79477-113">要件</span><span class="sxs-lookup"><span data-stu-id="79477-113">Requirements</span></span>  
 <span data-ttu-id="79477-114">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="79477-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="79477-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="79477-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="79477-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="79477-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="79477-117">**.NET framework のバージョン:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="79477-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79477-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="79477-118">See Also</span></span>  
 [<span data-ttu-id="79477-119">ICorDebugProcess5 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="79477-119">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 [<span data-ttu-id="79477-120">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="79477-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="79477-121">デバッグ</span><span class="sxs-lookup"><span data-stu-id="79477-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)