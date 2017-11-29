---
title: "ICorDebugExceptionObjectValue::EnumerateExceptionCallStack メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugExceptionObjectValue.EnumerateExceptionCallStack
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugExceptionObjectValue::EnumerateExceptionCallStack
helpviewer_keywords:
- EnumerateExceptionCallStack method, ICorDebugExceptionObjectValue interface [.NET Framework debugging]
- ICorDebugExceptionObjectValue::EnumerateExceptionCallStack method [.NET Framework debugging]
ms.assetid: 00c64533-15dd-47f4-bb97-fe80a1ebadef
topic_type: apiref
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 861d2ad5f9ce0fcc11ea7b1743cd369235cbd878
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugexceptionobjectvalueenumerateexceptioncallstack-method"></a><span data-ttu-id="5e81c-102">ICorDebugExceptionObjectValue::EnumerateExceptionCallStack メソッド</span><span class="sxs-lookup"><span data-stu-id="5e81c-102">ICorDebugExceptionObjectValue::EnumerateExceptionCallStack Method</span></span>
<span data-ttu-id="5e81c-103">例外オブジェクトに埋め込まれているコール スタックには、列挙子を取得します。</span><span class="sxs-lookup"><span data-stu-id="5e81c-103">Gets an enumerator to the call stack embedded in an exception object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e81c-104">構文</span><span class="sxs-lookup"><span data-stu-id="5e81c-104">Syntax</span></span>  
  
```  
HRESULT EnumerateExceptionCallStack(  
    [out] ICorDebugExceptionObjectCallStackEnum **ppCallStackEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5e81c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="5e81c-105">Parameters</span></span>  
 <span data-ttu-id="5e81c-106">ppCallStackEnum</span><span class="sxs-lookup"><span data-stu-id="5e81c-106">ppCallStackEnum</span></span>  
 <span data-ttu-id="5e81c-107">[out]アドレスへのポインター、 [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)インターフェイスであるオブジェクトをマネージ例外オブジェクトのスタック トレースの列挙子。</span><span class="sxs-lookup"><span data-stu-id="5e81c-107">[out] A pointer to the address of an [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md) interface object that is a stack trace enumerator for a managed exception object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5e81c-108">コメント</span><span class="sxs-lookup"><span data-stu-id="5e81c-108">Remarks</span></span>  
 <span data-ttu-id="5e81c-109">呼び出し履歴情報がないかどうか、メソッドが返されます`S_OK`、および[ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)は長さ 0 の有効な列挙子。</span><span class="sxs-lookup"><span data-stu-id="5e81c-109">If no call stack information is available, the method returns `S_OK`, and [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md) is a valid enumerator with a length of 0.</span></span> <span data-ttu-id="5e81c-110">メソッドは、スタック トレース情報を取得できませんが場合、戻り値は`E_FAIL`され、列挙子が返されません。</span><span class="sxs-lookup"><span data-stu-id="5e81c-110">If the method is unable to retrieve stack trace information, the return value is `E_FAIL` and no enumerator is returned.</span></span>  
  
 <span data-ttu-id="5e81c-111">[ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)オブジェクトは、スタック トレースからデータをデコードすることを担当する、`_stackTrace`例外オブジェクトのフィールドです。</span><span class="sxs-lookup"><span data-stu-id="5e81c-111">The [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md) object is responsible for decoding the stack trace data from the `_stackTrace` field of the exception object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e81c-112">要件</span><span class="sxs-lookup"><span data-stu-id="5e81c-112">Requirements</span></span>  
 <span data-ttu-id="5e81c-113">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="5e81c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e81c-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5e81c-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5e81c-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5e81c-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5e81c-116">**.NET framework のバージョン:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e81c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e81c-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="5e81c-117">See Also</span></span>  
 [<span data-ttu-id="5e81c-118">ICorDebugExceptionObjectValue インターフェイス</span><span class="sxs-lookup"><span data-stu-id="5e81c-118">ICorDebugExceptionObjectValue Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectvalue-interface.md)  
 [<span data-ttu-id="5e81c-119">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="5e81c-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)