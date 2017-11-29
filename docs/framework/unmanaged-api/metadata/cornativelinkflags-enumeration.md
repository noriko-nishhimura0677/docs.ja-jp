---
title: "CorNativeLinkFlags 列挙型"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorNativeLinkFlags
api_location: mscoree.dll
api_type: COM
f1_keywords: CorNativeLinkFlags
helpviewer_keywords: CorNativeLinkFlags enumeration [.NET Framework metadata]
ms.assetid: 8027df7c-cfad-4724-bda0-7538d9519070
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 09afda63959d974af71e0264ad116c20d3af1923
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2017
---
# <a name="cornativelinkflags-enumeration"></a><span data-ttu-id="cc1b3-102">CorNativeLinkFlags 列挙型</span><span class="sxs-lookup"><span data-stu-id="cc1b3-102">CorNativeLinkFlags Enumeration</span></span>
<span data-ttu-id="cc1b3-103">ネイティブ コードをリンクするときに、リンカーが使用するフラグ値を提供します。</span><span class="sxs-lookup"><span data-stu-id="cc1b3-103">Provides flag values used by the linker when linking native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc1b3-104">構文</span><span class="sxs-lookup"><span data-stu-id="cc1b3-104">Syntax</span></span>  
  
```  
typedef enum  
{  
    nlfNone         = 0x00,  
    nlfLastError    = 0x01,  
    nlfNoMangle     = 0x02,  
    nlfMaxValue     = 0x03  
} CorNativeLinkFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="cc1b3-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="cc1b3-105">Members</span></span>  
  
|<span data-ttu-id="cc1b3-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="cc1b3-106">Member</span></span>|<span data-ttu-id="cc1b3-107">説明</span><span class="sxs-lookup"><span data-stu-id="cc1b3-107">Description</span></span>|  
|------------|-----------------|  
|`nlfNone`|<span data-ttu-id="cc1b3-108">フラグがないことを示します。</span><span class="sxs-lookup"><span data-stu-id="cc1b3-108">Indicates no flags.</span></span>|  
|`nlfLastError`|<span data-ttu-id="cc1b3-109">示します、`setLastError`キーワード。</span><span class="sxs-lookup"><span data-stu-id="cc1b3-109">Indicates a `setLastError` keyword.</span></span>|  
|`nlfNoMangle`|<span data-ttu-id="cc1b3-110">示します、`nomangle`キーワード。</span><span class="sxs-lookup"><span data-stu-id="cc1b3-110">Indicates a `nomangle` keyword.</span></span>|  
|`nlfMaxValue`|<span data-ttu-id="cc1b3-111">使用しません。</span><span class="sxs-lookup"><span data-stu-id="cc1b3-111">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cc1b3-112">要件</span><span class="sxs-lookup"><span data-stu-id="cc1b3-112">Requirements</span></span>  
 <span data-ttu-id="cc1b3-113">**プラットフォーム:**を参照してください[システム要件](../../../../docs/framework/get-started/system-requirements.md)です。</span><span class="sxs-lookup"><span data-stu-id="cc1b3-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc1b3-114">**ヘッダー:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="cc1b3-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cc1b3-115">**ライブラリ:** MsCorEE.dll にリソースとして含まれています。</span><span class="sxs-lookup"><span data-stu-id="cc1b3-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cc1b3-116">**.NET framework のバージョン:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc1b3-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc1b3-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="cc1b3-117">See Also</span></span>  
 [<span data-ttu-id="cc1b3-118">メタデータ列挙体</span><span class="sxs-lookup"><span data-stu-id="cc1b3-118">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)