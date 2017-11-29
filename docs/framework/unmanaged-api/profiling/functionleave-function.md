---
title: "FunctionLeave 関数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: FunctionLeave
api_location: mscorwks.dll
api_type: COM
f1_keywords: FunctionLeave
helpviewer_keywords: FunctionLeave function [.NET Framework profiling]
ms.assetid: 18e89f45-e068-426a-be16-9f53a4346860
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 3368a97adf6ffceaa5ac56b7ffe16d6e2802437c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="functionleave-function"></a><span data-ttu-id="8a762-102">FunctionLeave 関数</span><span class="sxs-lookup"><span data-stu-id="8a762-102">FunctionLeave Function</span></span>
<span data-ttu-id="8a762-103">関数が呼び出し元に戻るには約ことをプロファイラーに通知します。</span><span class="sxs-lookup"><span data-stu-id="8a762-103">Notifies the profiler that a function is about to return to the caller.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8a762-104">`FunctionLeave`関数は、.NET Framework 2.0 で推奨されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="8a762-104">The `FunctionLeave` function is deprecated in the .NET Framework 2.0.</span></span> <span data-ttu-id="8a762-105">作業を続けますが、パフォーマンスの低下が発生します。</span><span class="sxs-lookup"><span data-stu-id="8a762-105">It will continue to work, but will incur a performance penalty.</span></span> <span data-ttu-id="8a762-106">使用して、 [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)関数を使用します。</span><span class="sxs-lookup"><span data-stu-id="8a762-106">Use the [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md) function instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a762-107">構文</span><span class="sxs-lookup"><span data-stu-id="8a762-107">Syntax</span></span>  
  
```  
void __stdcall FunctionLeave (  
    [in] FunctionID funcID  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8a762-108">パラメーター</span><span class="sxs-lookup"><span data-stu-id="8a762-108">Parameters</span></span>  
 `funcID`  
 <span data-ttu-id="8a762-109">[in]返す関数の識別子。</span><span class="sxs-lookup"><span data-stu-id="8a762-109">[in] The identifier of the function that is returning.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8a762-110">コメント</span><span class="sxs-lookup"><span data-stu-id="8a762-110">Remarks</span></span>  
 <span data-ttu-id="8a762-111">`FunctionLeave`関数コールバックです。 これを実装する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a762-111">The `FunctionLeave` function is a callback; you must implement it.</span></span> <span data-ttu-id="8a762-112">実装を使用する必要があります、 `__declspec`(`naked`) ストレージ クラス属性。</span><span class="sxs-lookup"><span data-stu-id="8a762-112">The implementation must use the `__declspec`(`naked`) storage-class attribute.</span></span>  
  
 <span data-ttu-id="8a762-113">実行エンジンは、この関数を呼び出す前に、レジスタを保存できません。</span><span class="sxs-lookup"><span data-stu-id="8a762-113">The execution engine does not save any registers before calling this function.</span></span>  
  
-   <span data-ttu-id="8a762-114">エントリを上には、浮動小数点ユニット (FPU) にあるなど、使用するすべてのレジスタを保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a762-114">On entry, you must save all registers that you use, including those in the floating-point unit (FPU).</span></span>  
  
-   <span data-ttu-id="8a762-115">終了時に、その呼び出し元がプッシュされたすべてのパラメーターをポップすることで、スタックを復元する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a762-115">On exit, you must restore the stack by popping off all the parameters that were pushed by its caller.</span></span>  
  
 <span data-ttu-id="8a762-116">実装`FunctionLeave`ガベージ コレクションを遅らせることがあるためにをブロックしないでください。</span><span class="sxs-lookup"><span data-stu-id="8a762-116">The implementation of `FunctionLeave` should not block because it will delay garbage collection.</span></span> <span data-ttu-id="8a762-117">実装は、ガベージ コレクションをしないでスタックはガベージ コレクションに適した状態ではない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8a762-117">The implementation should not attempt a garbage collection because the stack may not be in a garbage collection-friendly state.</span></span> <span data-ttu-id="8a762-118">ガベージ コレクションが実行されると、ランタイムがまでブロックされます`FunctionLeave`を返します。</span><span class="sxs-lookup"><span data-stu-id="8a762-118">If a garbage collection is attempted, the runtime will block until `FunctionLeave` returns.</span></span>  
  
 <span data-ttu-id="8a762-119">また、`FunctionLeave`関数を呼び出してはならないようにまたはマネージ コードにマネージ メモリの割り当て。</span><span class="sxs-lookup"><span data-stu-id="8a762-119">Also, the `FunctionLeave` function must not call into managed code or in any way cause a managed memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a762-120">要件</span><span class="sxs-lookup"><span data-stu-id="8a762-120">Requirements</span></span>  
 <span data-ttu-id="8a762-121">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="8a762-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a762-122">**ヘッダー:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="8a762-122">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="8a762-123">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8a762-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8a762-124">**.NET framework のバージョン:** 1.1、1.0</span><span class="sxs-lookup"><span data-stu-id="8a762-124">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a762-125">関連項目</span><span class="sxs-lookup"><span data-stu-id="8a762-125">See Also</span></span>  
 [<span data-ttu-id="8a762-126">FunctionEnter2 関数</span><span class="sxs-lookup"><span data-stu-id="8a762-126">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)  
 [<span data-ttu-id="8a762-127">FunctionLeave2 関数</span><span class="sxs-lookup"><span data-stu-id="8a762-127">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)  
 [<span data-ttu-id="8a762-128">FunctionTailcall2 関数</span><span class="sxs-lookup"><span data-stu-id="8a762-128">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)  
 [<span data-ttu-id="8a762-129">SetEnterLeaveFunctionHooks2 メソッド</span><span class="sxs-lookup"><span data-stu-id="8a762-129">SetEnterLeaveFunctionHooks2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)  
 [<span data-ttu-id="8a762-130">プロファイリング グローバル静的関数</span><span class="sxs-lookup"><span data-stu-id="8a762-130">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)