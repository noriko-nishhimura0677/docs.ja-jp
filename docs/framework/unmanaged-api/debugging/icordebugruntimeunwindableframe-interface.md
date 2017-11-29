---
title: "ICorDebugRuntimeUnwindableFrame インターフェイス"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugUnwindableFrame
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugUnwindableFrame
helpviewer_keywords: ICorDebugUnwindableFrame interface [.NET Framework debugging]
ms.assetid: cd6a3982-6ed3-4909-808d-a66055e813e0
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 003bbab399a9ad0ffe2f1d761aea18ff71ba1834
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugruntimeunwindableframe-interface"></a><span data-ttu-id="534f7-102">ICorDebugRuntimeUnwindableFrame インターフェイス</span><span class="sxs-lookup"><span data-stu-id="534f7-102">ICorDebugRuntimeUnwindableFrame Interface</span></span>
<span data-ttu-id="534f7-103">共通言語ランタイム (CLR: Common Language Runtime) でフレームをアンワインドする必要のあるアンマネージ メソッドに対してサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="534f7-103">Provides support for unmanaged methods that require the common language runtime (CLR) to unwind a frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="534f7-104">コメント</span><span class="sxs-lookup"><span data-stu-id="534f7-104">Remarks</span></span>  
 <span data-ttu-id="534f7-105">`ICorDebugRuntimeUnwindableFrame`ICorDebugFrame インターフェイスの特殊なバージョンがします。</span><span class="sxs-lookup"><span data-stu-id="534f7-105">`ICorDebugRuntimeUnwindableFrame` is a specialized version of the ICorDebugFrame interface.</span></span> <span data-ttu-id="534f7-106">現在のスタックのフレームをアンワインドするランタイムを必要とするアンマネージ メソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="534f7-106">It is used by unmanaged methods that require the runtime to unwind a frame on the current stack.</span></span> <span data-ttu-id="534f7-107">既存のアンワインド規則が機能しないため、JIT コンパイル コードを使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="534f7-107">Existing unwinding conventions do not work, because they do not use JIT-compiled code.</span></span> <span data-ttu-id="534f7-108">デバッガーは、アンワインド可能で、フレームを見て、使用が必要で、 [icordebugstackwalk::next](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md)をアンワインドするメソッドはそれ自体の検査を実行します。</span><span class="sxs-lookup"><span data-stu-id="534f7-108">When the debugger sees an unwindable frame, it should use the [ICorDebugStackWalk::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-next-method.md) method to unwind it, but it should perform inspection itself.</span></span> <span data-ttu-id="534f7-109">デバッガーが受信すると、 `ICorDebugRuntimeUnwindableFrame`、呼び出すことができます、 [icordebugstackwalk::getcontext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md)フレームのコンテキストを取得します。</span><span class="sxs-lookup"><span data-stu-id="534f7-109">When the debugger receives an `ICorDebugRuntimeUnwindableFrame`, it can call the [ICorDebugStackWalk::GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) method to retrieve the context of the frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="534f7-110">要件</span><span class="sxs-lookup"><span data-stu-id="534f7-110">Requirements</span></span>  
 <span data-ttu-id="534f7-111">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="534f7-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="534f7-112">**ヘッダー:** CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="534f7-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="534f7-113">**ライブラリ:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="534f7-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="534f7-114">**.NET framework のバージョン:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="534f7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="534f7-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="534f7-115">See Also</span></span>  
 [<span data-ttu-id="534f7-116">デバッグのインターフェイス</span><span class="sxs-lookup"><span data-stu-id="534f7-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="534f7-117">デバッグ</span><span class="sxs-lookup"><span data-stu-id="534f7-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)