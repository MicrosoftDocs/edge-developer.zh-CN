---
description: 返回一个值，该值指示是否枚举当前上下文的堆。
title: JsIsEnumeratingHeap 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsIsEnumeratingHeap
helpviewer_keywords:
- JsIsEnumeratingHeap function
ms.assetid: 5d14518e-3153-43f2-9a9c-068580cbd54f
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 5b66fc70ea79d78029f6bc0c900ade1aae38e604
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232573"
---
# <span data-ttu-id="bd318-103">JsIsEnumeratingHeap 函数</span><span class="sxs-lookup"><span data-stu-id="bd318-103">JsIsEnumeratingHeap Function</span></span>

<span data-ttu-id="bd318-104">返回一个值，该值指示是否枚举当前上下文的堆。</span><span class="sxs-lookup"><span data-stu-id="bd318-104">Returns a value that indicates whether the heap of the current context is being enumerated.</span></span>  
  
## <span data-ttu-id="bd318-105">语法</span><span class="sxs-lookup"><span data-stu-id="bd318-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsIsEnumeratingHeap(  
   _Out_ bool *isEnumeratingHeap  
);  
```  
  
#### <span data-ttu-id="bd318-106">参数</span><span class="sxs-lookup"><span data-stu-id="bd318-106">Parameters</span></span>  
 `isEnumeratingHeap`  
 <span data-ttu-id="bd318-107">是否枚举堆。</span><span class="sxs-lookup"><span data-stu-id="bd318-107">Whether the heap is being enumerated.</span></span>  
  
## <span data-ttu-id="bd318-108">返回值</span><span class="sxs-lookup"><span data-stu-id="bd318-108">Return Value</span></span>  
 <span data-ttu-id="bd318-109">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="bd318-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="bd318-110">备注</span><span class="sxs-lookup"><span data-stu-id="bd318-110">Remarks</span></span>  
 <span data-ttu-id="bd318-111">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="bd318-111">Requires an active script context.</span></span>  
  
 <span data-ttu-id="bd318-112">此 API 在桌面应用中受支持，但在应用商店应用中不受支持。</span><span class="sxs-lookup"><span data-stu-id="bd318-112">This API is supported in desktop apps, but is not supported in Store apps.</span></span>  
  
## <span data-ttu-id="bd318-113">要求</span><span class="sxs-lookup"><span data-stu-id="bd318-113">Requirements</span></span>  
 <span data-ttu-id="bd318-114">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="bd318-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="bd318-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bd318-115">See Also</span></span>  
 [<span data-ttu-id="bd318-116">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="bd318-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
