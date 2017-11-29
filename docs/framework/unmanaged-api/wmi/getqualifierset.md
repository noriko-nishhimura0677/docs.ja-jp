---
title: "GetQualifierSet 関数 (アンマネージ API リファレンス)"
description: "GetQualifierSet 関数では、クラスまたはインスタンスの設定、修飾子を取得します。"
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: GetQualifierSet
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: GetQualifierSet
helpviewer_keywords: GetQualifierSet function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 15d384003f3a18124a07d83a8308f4b8a5c6a31b
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2017
---
# <a name="getqualifierset-function"></a><span data-ttu-id="16fe1-103">GetQualifierSet 関数</span><span class="sxs-lookup"><span data-stu-id="16fe1-103">GetQualifierSet function</span></span>
<span data-ttu-id="16fe1-104">クラスのインスタンスまたはクラス定義の設定、修飾子を取得します。</span><span class="sxs-lookup"><span data-stu-id="16fe1-104">Retrieves the qualifier set for a class instance or a class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="16fe1-105">構文</span><span class="sxs-lookup"><span data-stu-id="16fe1-105">Syntax</span></span>  
  
```  
HRESULT GetQualifierSet (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [out] IWbemQualifierSet  **ppQualSet
); 
```  

## <a name="parameters"></a><span data-ttu-id="16fe1-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="16fe1-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="16fe1-107">[in]このパラメーターは使用されません。</span><span class="sxs-lookup"><span data-stu-id="16fe1-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="16fe1-108">[in]ポインター、 [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx)インスタンス。</span><span class="sxs-lookup"><span data-stu-id="16fe1-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`ppQualSet`  
<span data-ttu-id="16fe1-109">[out]クラスのオブジェクトの修飾子にアクセスできるようにするインターフェイス ポインターを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="16fe1-109">[out] Receives the interface pointer that allows access to the qualifiers of the class object.</span></span> <span data-ttu-id="16fe1-110">`ppQualSet` として `null` を使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="16fe1-110">`ppQualSet` cannot be `null`.</span></span> <span data-ttu-id="16fe1-111">エラーが発生した、新しいオブジェクトが返されないと、ポインターのまま変更されていません。</span><span class="sxs-lookup"><span data-stu-id="16fe1-111">If an error occurs, a new object is not returned, and the pointer is left unmodified.</span></span> 

## <a name="return-value"></a><span data-ttu-id="16fe1-112">戻り値</span><span class="sxs-lookup"><span data-stu-id="16fe1-112">Return value</span></span>

<span data-ttu-id="16fe1-113">この関数によって返される次の値が定義されている、 *WbemCli.h*ヘッダー ファイル、またはすることができますに定義する定数として、コード。</span><span class="sxs-lookup"><span data-stu-id="16fe1-113">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="16fe1-114">定数</span><span class="sxs-lookup"><span data-stu-id="16fe1-114">Constant</span></span>  |<span data-ttu-id="16fe1-115">値</span><span class="sxs-lookup"><span data-stu-id="16fe1-115">Value</span></span>  |<span data-ttu-id="16fe1-116">説明</span><span class="sxs-lookup"><span data-stu-id="16fe1-116">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="16fe1-117">0x80041001</span><span class="sxs-lookup"><span data-stu-id="16fe1-117">0x80041001</span></span> | <span data-ttu-id="16fe1-118">一般的なエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="16fe1-118">There has been a general failure.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="16fe1-119">0x80041002</span><span class="sxs-lookup"><span data-stu-id="16fe1-119">0x80041002</span></span> | <span data-ttu-id="16fe1-120">指定されたメソッドが存在しません。</span><span class="sxs-lookup"><span data-stu-id="16fe1-120">The specified method does not exist.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="16fe1-121">0x80041006</span><span class="sxs-lookup"><span data-stu-id="16fe1-121">0x80041006</span></span> | <span data-ttu-id="16fe1-122">操作を完了するのに十分なメモリがあります。</span><span class="sxs-lookup"><span data-stu-id="16fe1-122">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="16fe1-123">0x80041008</span><span class="sxs-lookup"><span data-stu-id="16fe1-123">0x80041008</span></span> | <span data-ttu-id="16fe1-124">パラメーターが`null`です。</span><span class="sxs-lookup"><span data-stu-id="16fe1-124">A parameter is `null`.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="16fe1-125">0</span><span class="sxs-lookup"><span data-stu-id="16fe1-125">0</span></span> | <span data-ttu-id="16fe1-126">関数呼び出しに成功しました。</span><span class="sxs-lookup"><span data-stu-id="16fe1-126">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="16fe1-127">コメント</span><span class="sxs-lookup"><span data-stu-id="16fe1-127">Remarks</span></span>

<span data-ttu-id="16fe1-128">この関数への呼び出しをラップする、 [IWbemClassObject::GetQualifierSet](https://msdn.microsoft.com/library/aa391451(v=vs.85).aspx)メソッドです。</span><span class="sxs-lookup"><span data-stu-id="16fe1-128">This function wraps a call to the [IWbemClassObject::GetQualifierSet](https://msdn.microsoft.com/library/aa391451(v=vs.85).aspx) method.</span></span> 

<span data-ttu-id="16fe1-129">[IWbemQualifierSet ポインター](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx)により、呼び出し元を追加、編集、またはこれらの修飾子を削除します。</span><span class="sxs-lookup"><span data-stu-id="16fe1-129">The [IWbemQualifierSet pointer](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) lets the caller add, edit, or delete these qualifiers.</span></span> <span data-ttu-id="16fe1-130">このような追加、編集、または削除した修飾子は、すべてのインスタンスまたはクラス定義に適用されます。</span><span class="sxs-lookup"><span data-stu-id="16fe1-130">Such added, edited, or deleted qualifiers apply to the entire instance or class definition.</span></span>

## <a name="requirements"></a><span data-ttu-id="16fe1-131">要件</span><span class="sxs-lookup"><span data-stu-id="16fe1-131">Requirements</span></span>  
<span data-ttu-id="16fe1-132">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="16fe1-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16fe1-133">**ヘッダー:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="16fe1-133">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="16fe1-134">**.NET framework のバージョン:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="16fe1-134">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16fe1-135">関連項目</span><span class="sxs-lookup"><span data-stu-id="16fe1-135">See also</span></span>  
[<span data-ttu-id="16fe1-136">WMI およびパフォーマンス カウンター (アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="16fe1-136">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)