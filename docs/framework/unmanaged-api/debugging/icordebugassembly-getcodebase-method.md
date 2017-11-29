---
title: "ICorDebugAssembly::GetCodeBase メソッド"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAssembly.GetCodeBase
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugAssembly::GetCodeBase
helpviewer_keywords:
- GetCodeBase method [.NET Framework debugging]
- ICorDebugAssembly::GetCodeBase method [.NET Framework debugging]
ms.assetid: 48adc154-9058-4fef-9c43-e9aad80e4dbf
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: dc39d9d73485eaf8abbf2679fba044502823f31f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugassemblygetcodebase-method"></a><span data-ttu-id="5011c-102">ICorDebugAssembly::GetCodeBase メソッド</span><span class="sxs-lookup"><span data-stu-id="5011c-102">ICorDebugAssembly::GetCodeBase Method</span></span>
<span data-ttu-id="5011c-103">.NET Framework の現在のバージョンでは、このメソッドが実装されていません。</span><span class="sxs-lookup"><span data-stu-id="5011c-103">This method is not implemented in the current version of the .NET Framework.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5011c-104">構文</span><span class="sxs-lookup"><span data-stu-id="5011c-104">Syntax</span></span>  
  
```  
HRESULT GetCodeBase (  
    [in] ULONG32  cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]   
        WCHAR szName[]  
);  
```