---
description: 设置运行时的当前内存限制。
title: JsSetRuntimeMemoryLimit 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsSetRuntimeMemoryLimit
helpviewer_keywords:
- JsSetRuntimeMemoryLimit function
ms.assetid: 74feb31f-19f6-43e3-b117-0694c59ac593
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 1c31d8bbbec4be22fc1af09e546ad4c95f8ec2bd
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232008"
---
# <span data-ttu-id="bf138-103">JsSetRuntimeMemoryLimit 函数</span><span class="sxs-lookup"><span data-stu-id="bf138-103">JsSetRuntimeMemoryLimit Function</span></span>

<span data-ttu-id="bf138-104">设置运行时的当前内存限制。</span><span class="sxs-lookup"><span data-stu-id="bf138-104">Sets the current memory limit for a runtime.</span></span>  
  
## <span data-ttu-id="bf138-105">语法</span><span class="sxs-lookup"><span data-stu-id="bf138-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsSetRuntimeMemoryLimit(  
   _In_ JsRuntimeHandle runtime,  
   _In_ size_t memoryLimit  
);  
```  
  
#### <span data-ttu-id="bf138-106">参数</span><span class="sxs-lookup"><span data-stu-id="bf138-106">Parameters</span></span>  
 `runtime`  
 <span data-ttu-id="bf138-107">要设置其内存限制的运行时。</span><span class="sxs-lookup"><span data-stu-id="bf138-107">The runtime whose memory limit is to be set.</span></span>  
  
 `memoryLimit`  
 <span data-ttu-id="bf138-108">新的运行时内存限制（以字节为单位）或 -1（无内存限制）。</span><span class="sxs-lookup"><span data-stu-id="bf138-108">The new runtime memory limit, in bytes, or -1 for no memory limit.</span></span>  
  
## <span data-ttu-id="bf138-109">返回值</span><span class="sxs-lookup"><span data-stu-id="bf138-109">Return Value</span></span>  
 <span data-ttu-id="bf138-110">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="bf138-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="bf138-111">备注</span><span class="sxs-lookup"><span data-stu-id="bf138-111">Remarks</span></span>  
 <span data-ttu-id="bf138-112">内存限制将导致任何超过该限制的操作失败，并出现"内存不足"错误。</span><span class="sxs-lookup"><span data-stu-id="bf138-112">A memory limit will cause any operation which exceeds the limit to fail with an "out of memory" error.</span></span> <span data-ttu-id="bf138-113">将运行时的内存限制设置为 -1 意味着运行时没有内存限制。</span><span class="sxs-lookup"><span data-stu-id="bf138-113">Setting a runtime's memory limit to -1 means that the runtime has no memory limit.</span></span> <span data-ttu-id="bf138-114">新运行时默认为没有内存限制。</span><span class="sxs-lookup"><span data-stu-id="bf138-114">New runtimes default to having no memory limit.</span></span> <span data-ttu-id="bf138-115">如果新内存限制超过当前使用量，调用将成功，并且此运行时中任何未来分配将失败，直到运行时的内存使用率低于该限制。</span><span class="sxs-lookup"><span data-stu-id="bf138-115">If the new memory limit exceeds current usage, the call will succeed and any future allocations in this runtime will fail until the runtime's memory usage drops below the limit.</span></span>  
  
 <span data-ttu-id="bf138-116">运行时的内存限制始终可以设置，而不管该运行时在另一个线程上是否处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="bf138-116">A runtime's memory limit can be always be set, regardless of whether or not the runtime is active on another thread.</span></span>  
  
## <span data-ttu-id="bf138-117">要求</span><span class="sxs-lookup"><span data-stu-id="bf138-117">Requirements</span></span>  
 <span data-ttu-id="bf138-118">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="bf138-118">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="bf138-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bf138-119">See Also</span></span>  
 [<span data-ttu-id="bf138-120">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="bf138-120">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
