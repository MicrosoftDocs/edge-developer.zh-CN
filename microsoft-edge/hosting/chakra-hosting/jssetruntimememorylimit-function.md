---
description: 设置运行时的当前内存限制。
title: JsSetRuntimeMemoryLimit 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsSetRuntimeMemoryLimit
helpviewer_keywords:
- JsSetRuntimeMemoryLimit function
ms.assetid: 74feb31f-19f6-43e3-b117-0694c59ac593
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: ec8d098c528ac813926797280541aa2c9c4fee79
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564073"
---
# <span data-ttu-id="b1cfe-103">JsSetRuntimeMemoryLimit 函数</span><span class="sxs-lookup"><span data-stu-id="b1cfe-103">JsSetRuntimeMemoryLimit Function</span></span>
<span data-ttu-id="b1cfe-104">设置运行时的当前内存限制。</span><span class="sxs-lookup"><span data-stu-id="b1cfe-104">Sets the current memory limit for a runtime.</span></span>  
  
## <span data-ttu-id="b1cfe-105">语法</span><span class="sxs-lookup"><span data-stu-id="b1cfe-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsSetRuntimeMemoryLimit(  
   _In_ JsRuntimeHandle runtime,  
   _In_ size_t memoryLimit  
);  
```  
  
#### <span data-ttu-id="b1cfe-106">参数</span><span class="sxs-lookup"><span data-stu-id="b1cfe-106">Parameters</span></span>  
 `runtime`  
 <span data-ttu-id="b1cfe-107">要设置其内存限制的运行时。</span><span class="sxs-lookup"><span data-stu-id="b1cfe-107">The runtime whose memory limit is to be set.</span></span>  
  
 `memoryLimit`  
 <span data-ttu-id="b1cfe-108">新的运行时内存限制（以字节为单位），或者为-1，表示无内存限制。</span><span class="sxs-lookup"><span data-stu-id="b1cfe-108">The new runtime memory limit, in bytes, or -1 for no memory limit.</span></span>  
  
## <span data-ttu-id="b1cfe-109">返回值</span><span class="sxs-lookup"><span data-stu-id="b1cfe-109">Return Value</span></span>  
 <span data-ttu-id="b1cfe-110">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="b1cfe-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="b1cfe-111">备注</span><span class="sxs-lookup"><span data-stu-id="b1cfe-111">Remarks</span></span>  
 <span data-ttu-id="b1cfe-112">内存限制将导致超出限制的任何操作失败，并出现 "内存不足" 错误。</span><span class="sxs-lookup"><span data-stu-id="b1cfe-112">A memory limit will cause any operation which exceeds the limit to fail with an "out of memory" error.</span></span> <span data-ttu-id="b1cfe-113">将运行时的内存限制设置为-1 意味着运行时没有内存限制。</span><span class="sxs-lookup"><span data-stu-id="b1cfe-113">Setting a runtime's memory limit to -1 means that the runtime has no memory limit.</span></span> <span data-ttu-id="b1cfe-114">新的运行时默认为没有内存限制。</span><span class="sxs-lookup"><span data-stu-id="b1cfe-114">New runtimes default to having no memory limit.</span></span> <span data-ttu-id="b1cfe-115">如果新的内存限制超过当前使用，则调用将成功，并且此运行时中的任何未来分配都将失败，直到运行时的内存使用量降到限制以下。</span><span class="sxs-lookup"><span data-stu-id="b1cfe-115">If the new memory limit exceeds current usage, the call will succeed and any future allocations in this runtime will fail until the runtime's memory usage drops below the limit.</span></span>  
  
 <span data-ttu-id="b1cfe-116">无论运行时是否在另一个线程上处于活动状态，都可以始终设置运行时的内存限制。</span><span class="sxs-lookup"><span data-stu-id="b1cfe-116">A runtime's memory limit can be always be set, regardless of whether or not the runtime is active on another thread.</span></span>  
  
## <span data-ttu-id="b1cfe-117">要求</span><span class="sxs-lookup"><span data-stu-id="b1cfe-117">Requirements</span></span>  
 <span data-ttu-id="b1cfe-118">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="b1cfe-118">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="b1cfe-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b1cfe-119">See Also</span></span>  
 [<span data-ttu-id="b1cfe-120">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="b1cfe-120">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)