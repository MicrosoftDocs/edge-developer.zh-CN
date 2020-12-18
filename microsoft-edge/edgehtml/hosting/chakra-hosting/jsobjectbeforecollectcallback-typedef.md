---
description: 在收集对象之前调用的回调。
title: JsObjectBeforeCollectCallback Typedef |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: f21a064a-579f-44cb-9d21-76b62e8c18f5
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 4c24385ec5e15919719ffb0ae71c8adf39c1724c
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232537"
---
# <span data-ttu-id="94622-103">JsObjectBeforeCollectCallback Typedef</span><span class="sxs-lookup"><span data-stu-id="94622-103">JsObjectBeforeCollectCallback Typedef</span></span>

<span data-ttu-id="94622-104">在收集对象之前调用的回调。</span><span class="sxs-lookup"><span data-stu-id="94622-104">A callback called before collecting an object.</span></span>  
  
## <span data-ttu-id="94622-105">语法</span><span class="sxs-lookup"><span data-stu-id="94622-105">Syntax</span></span>  
  
```cpp  
typedef void (CALLBACK *JsObjectBeforeCollectCallback)(  
  _In_ JsRef ref,  
  _In_opt_ void *callbackState  
);  
```  
  
#### <span data-ttu-id="94622-106">参数</span><span class="sxs-lookup"><span data-stu-id="94622-106">Parameters</span></span>  
 `ref`  
 <span data-ttu-id="94622-107">要收集的对象。</span><span class="sxs-lookup"><span data-stu-id="94622-107">The object to be collected.</span></span>  
  
 `callbackState`  
 <span data-ttu-id="94622-108">传递给 `JsSetObjectBeforeCollectCallback` 的状态。</span><span class="sxs-lookup"><span data-stu-id="94622-108">The state passed to `JsSetObjectBeforeCollectCallback`.</span></span>  
  
## <span data-ttu-id="94622-109">备注</span><span class="sxs-lookup"><span data-stu-id="94622-109">Remarks</span></span>  
 <span data-ttu-id="94622-110">此 API 仅在 EdgeHTML 模式下受支持。</span><span class="sxs-lookup"><span data-stu-id="94622-110">This API is supported only in EdgeHTML mode.</span></span>  
  
## <span data-ttu-id="94622-111">要求</span><span class="sxs-lookup"><span data-stu-id="94622-111">Requirements</span></span>  
 <span data-ttu-id="94622-112">jsrt.h</span><span class="sxs-lookup"><span data-stu-id="94622-112">jsrt.h</span></span>  
  
## <span data-ttu-id="94622-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="94622-113">See Also</span></span>  
 [<span data-ttu-id="94622-114">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="94622-114">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
