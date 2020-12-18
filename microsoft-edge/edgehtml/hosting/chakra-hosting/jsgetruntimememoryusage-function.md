---
description: 获取运行时的当前内存使用率。
title: JsGetRuntimeMemoryUsage 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsGetRuntimeMemoryUsage
helpviewer_keywords:
- JsGetRuntimeMemoryUsage function
ms.assetid: b9bd4146-bfbc-4cb1-a0e9-a0ded7fb09bd
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: a9c8d59e8cf73ad178f539f2f9f0ed191ceb47fd
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232771"
---
# <span data-ttu-id="fbd51-103">JsGetRuntimeMemoryUsage 函数</span><span class="sxs-lookup"><span data-stu-id="fbd51-103">JsGetRuntimeMemoryUsage Function</span></span>

<span data-ttu-id="fbd51-104">获取运行时的当前内存使用率。</span><span class="sxs-lookup"><span data-stu-id="fbd51-104">Gets the current memory usage for a runtime.</span></span>  
  
## <span data-ttu-id="fbd51-105">语法</span><span class="sxs-lookup"><span data-stu-id="fbd51-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetRuntimeMemoryUsage(  
   _In_ JsRuntimeHandle runtime,  
   _Out_ size_t *memoryUsage  
);  
```  
  
#### <span data-ttu-id="fbd51-106">参数</span><span class="sxs-lookup"><span data-stu-id="fbd51-106">Parameters</span></span>  
 `runtime`  
 <span data-ttu-id="fbd51-107">要检索其内存使用情况的运行时。</span><span class="sxs-lookup"><span data-stu-id="fbd51-107">The runtime whose memory usage is to be retrieved.</span></span>  
  
 `memoryUsage`  
 <span data-ttu-id="fbd51-108">运行时的当前内存使用率（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="fbd51-108">The runtime's current memory usage, in bytes.</span></span>  
  
## <span data-ttu-id="fbd51-109">返回值</span><span class="sxs-lookup"><span data-stu-id="fbd51-109">Return Value</span></span>  
 <span data-ttu-id="fbd51-110">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="fbd51-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="fbd51-111">备注</span><span class="sxs-lookup"><span data-stu-id="fbd51-111">Remarks</span></span>  
 <span data-ttu-id="fbd51-112">无论运行时是否在另一个线程上处于活动状态，始终可以检索内存使用率。</span><span class="sxs-lookup"><span data-stu-id="fbd51-112">Memory usage can be always be retrieved, regardless of whether or not the runtime is active on another thread.</span></span>  
  
## <span data-ttu-id="fbd51-113">要求</span><span class="sxs-lookup"><span data-stu-id="fbd51-113">Requirements</span></span>  
 <span data-ttu-id="fbd51-114">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="fbd51-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="fbd51-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fbd51-115">See Also</span></span>  
 [<span data-ttu-id="fbd51-116">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="fbd51-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
