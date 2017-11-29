---
title: "ICorDebugClass::GetStaticFieldValue メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugClass.GetStaticFieldValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugClass::GetStaticFieldValue
helpviewer_keywords:
- GetStaticFieldValue method, ICorDebugClass interface [.NET Framework debugging]
- ICorDebugClass::GetStaticFieldValue method [.NET Framework debugging]
ms.assetid: 56e718b4-fabd-418b-a5b3-3cc33c745683
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 15491728e225799eb0e934c9cc42a3967c19202e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugclassgetstaticfieldvalue-method"></a><span data-ttu-id="618e0-102">ICorDebugClass::GetStaticFieldValue メソッド</span><span class="sxs-lookup"><span data-stu-id="618e0-102">ICorDebugClass::GetStaticFieldValue Method</span></span>
<span data-ttu-id="618e0-103">指定された静的フィールドの値を取得します。</span><span class="sxs-lookup"><span data-stu-id="618e0-103">Gets the value of the specified static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="618e0-104">構文</span><span class="sxs-lookup"><span data-stu-id="618e0-104">Syntax</span></span>  
  
```  
HRESULT GetStaticFieldValue (  
    [in]  mdFieldDef         fieldDef,  
    [in]  ICorDebugFrame     *pFrame,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="618e0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="618e0-105">Parameters</span></span>  
 `fieldDef`  
 <span data-ttu-id="618e0-106">[in]フィールド`Def`を取得するフィールドを参照するトークン。</span><span class="sxs-lookup"><span data-stu-id="618e0-106">[in] A field `Def` token that references the field to be retrieved.</span></span>  
  
 `pFrame`  
 <span data-ttu-id="618e0-107">[in]スレッド、コンテキスト、またはアプリケーション ドメインの静的変数の間であいまいさを解消するために使用するフレームを表す ICorDebugFrame オブジェクトへのポインター。</span><span class="sxs-lookup"><span data-stu-id="618e0-107">[in] A pointer to an ICorDebugFrame object that represents the frame to be used to disambiguate among thread, context, or application domain statics.</span></span>  
  
 <span data-ttu-id="618e0-108">静的フィールドは、スレッド、コンテキスト、またはアプリケーション ドメインとの比較は、フレームに適切な値が判断されます。</span><span class="sxs-lookup"><span data-stu-id="618e0-108">If the static field is relative to a thread, a context, or an application domain, the frame will determine the proper value.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="618e0-109">[out]静的フィールドの値を表す ICorDebugValue オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="618e0-109">[out] A pointer to the address of an ICorDebugValue object that represents the value of the static field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="618e0-110">コメント</span><span class="sxs-lookup"><span data-stu-id="618e0-110">Remarks</span></span>  
 <span data-ttu-id="618e0-111">パラメーター化された型は、特定のインスタンス化の相対静的フィールドの値パスです。</span><span class="sxs-lookup"><span data-stu-id="618e0-111">For parameterized types, the value of a static field is relative to the particular instantiation.</span></span> <span data-ttu-id="618e0-112">そのため、クラス コンス トラクターが型のパラメーターを受け取る場合<xref:System.Type>、呼び出す[icordebugtype::getstaticfieldvalue](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getstaticfieldvalue-method.md)の代わりに`ICorDebugClass::GetStaticFieldValue`です。</span><span class="sxs-lookup"><span data-stu-id="618e0-112">Therefore, if the class constructor takes parameters of type <xref:System.Type>, call [ICorDebugType::GetStaticFieldValue](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-getstaticfieldvalue-method.md) instead of `ICorDebugClass::GetStaticFieldValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="618e0-113">要件</span><span class="sxs-lookup"><span data-stu-id="618e0-113">Requirements</span></span>  
 <span data-ttu-id="618e0-114">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="618e0-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="618e0-115">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="618e0-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="618e0-116">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="618e0-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="618e0-117">**.NET framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="618e0-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>