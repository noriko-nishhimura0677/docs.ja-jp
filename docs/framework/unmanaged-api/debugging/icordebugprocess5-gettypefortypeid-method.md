---
title: "ICorDebugProcess5::GetTypeForTypeID メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess5.GetTypeForTypeID
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess5::GetTypeForTypeID
helpviewer_keywords:
- GetTypeForTypeID method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::GetTypeForTypeID method [.NET Framework debugging]
ms.assetid: e0eed5a8-fa6d-4818-bd00-7babcea30325
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 08c4b72b5b37d9e3a2a2e19bad9e79449906b495
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess5gettypefortypeid-method"></a><span data-ttu-id="21e45-102">ICorDebugProcess5::GetTypeForTypeID メソッド</span><span class="sxs-lookup"><span data-stu-id="21e45-102">ICorDebugProcess5::GetTypeForTypeID Method</span></span>
<span data-ttu-id="21e45-103">ICorDebugType 値型の識別子に変換します。</span><span class="sxs-lookup"><span data-stu-id="21e45-103">Converts a type identifier to an ICorDebugType value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21e45-104">構文</span><span class="sxs-lookup"><span data-stu-id="21e45-104">Syntax</span></span>  
  
```  
HRESULT GetTypeForTypeID(  
    [in] COR_TYPEID id, [  
    out] ICorDebugType **ppType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="21e45-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="21e45-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="21e45-106">[in]型の識別子です。</span><span class="sxs-lookup"><span data-stu-id="21e45-106">[in] The type identifier.</span></span>  
  
 `ppType`  
 <span data-ttu-id="21e45-107">[out]ICorDebugType オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="21e45-107">[out] A pointer to the address of an ICorDebugType object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="21e45-108">コメント</span><span class="sxs-lookup"><span data-stu-id="21e45-108">Remarks</span></span>  
 <span data-ttu-id="21e45-109">場合によっては、型識別子を返すメソッドが null を返す可能性があります`COR_TYPEID`値。</span><span class="sxs-lookup"><span data-stu-id="21e45-109">In some cases, methods that return a type identifier may return a null `COR_TYPEID` value.</span></span> <span data-ttu-id="21e45-110">この値として渡された場合、`id`引数、`GetTypeForTypeID`メソッドが失敗し、返されます`E_FAIL`です。</span><span class="sxs-lookup"><span data-stu-id="21e45-110">If this value is passed as the `id` argument, the `GetTypeForTypeID` method will fail and return `E_FAIL`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21e45-111">要件</span><span class="sxs-lookup"><span data-stu-id="21e45-111">Requirements</span></span>  
 <span data-ttu-id="21e45-112">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="21e45-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21e45-113">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="21e45-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="21e45-114">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="21e45-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="21e45-115">**.NET framework のバージョン:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21e45-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21e45-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="21e45-116">See Also</span></span>  
 [<span data-ttu-id="21e45-117">ICorDebugProcess5 インターフェイス</span><span class="sxs-lookup"><span data-stu-id="21e45-117">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 [<span data-ttu-id="21e45-118">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="21e45-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)