---
title: "ICorDebugNativeFrame::GetLocalRegisterValue メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugNativeFrame.GetLocalRegisterValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugNativeFrame::GetLocalRegisterValue
helpviewer_keywords:
- GetLocalRegisterValue method [.NET Framework debugging]
- ICorDebugNativeFrame::GetLocalRegisterValue method [.NET Framework debugging]
ms.assetid: 5ccb74f3-f891-430c-b70a-e370624edde2
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 43fdfc5cf4f17aaa9b26fc4a028c98c63a1b3c54
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugnativeframegetlocalregistervalue-method"></a><span data-ttu-id="df7e0-102">ICorDebugNativeFrame::GetLocalRegisterValue メソッド</span><span class="sxs-lookup"><span data-stu-id="df7e0-102">ICorDebugNativeFrame::GetLocalRegisterValue Method</span></span>
<span data-ttu-id="df7e0-103">引数またはこのネイティブ フレームの指定のレジスタに格納されているローカル変数の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="df7e0-103">Gets the value of an argument or local variable that is stored in the specified register for this native frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df7e0-104">構文</span><span class="sxs-lookup"><span data-stu-id="df7e0-104">Syntax</span></span>  
  
```  
HRESULT GetLocalRegisterValue (  
    [in]  CorDebugRegister   reg,  
    [in]  ULONG              cbSigBlob,  
    [in]  PCCOR_SIGNATURE    pvSigBlob,  
    [out] ICorDebugValue     **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="df7e0-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="df7e0-105">Parameters</span></span>  
 `reg`  
 <span data-ttu-id="df7e0-106">[in]値を含むレジスタを指定する"CorDebugRegister"列挙の値です。</span><span class="sxs-lookup"><span data-stu-id="df7e0-106">[in] A value of the "CorDebugRegister" enumeration that specifies the register containing the value.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="df7e0-107">[in]によって参照されているバイナリ メタデータ シグネチャのサイズを指定する整数、`pvSigBlob`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="df7e0-107">[in] An integer that specifies the size of the binary metadata signature which is referenced by the `pvSigBlob` parameter.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="df7e0-108">[in]A`PCCOR_SIGNATURE`値の型のバイナリ メタデータ シグネチャを指している値。</span><span class="sxs-lookup"><span data-stu-id="df7e0-108">[in] A `PCCOR_SIGNATURE` value that points to the binary metadata signature of the value's type.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="df7e0-109">[out]指定のレジスタに格納されている取得した値を表す"ICorDebugValue"オブジェクトのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="df7e0-109">[out] A pointer to the address of an "ICorDebugValue" object representing the retrieved value that is stored in the specified register.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="df7e0-110">コメント</span><span class="sxs-lookup"><span data-stu-id="df7e0-110">Remarks</span></span>  
 <span data-ttu-id="df7e0-111">`GetLocalRegisterValue`ネイティブ フレームまたは、ジャスト イン-タイム (JIT) のいずれか、メソッドを使用できます-フレームをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="df7e0-111">The `GetLocalRegisterValue` method can be used either in a native frame or a just-in-time (JIT)-compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df7e0-112">要件</span><span class="sxs-lookup"><span data-stu-id="df7e0-112">Requirements</span></span>  
 <span data-ttu-id="df7e0-113">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="df7e0-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df7e0-114">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="df7e0-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="df7e0-115">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="df7e0-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="df7e0-116">**.NET framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df7e0-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df7e0-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="df7e0-117">See Also</span></span>  
 