---
description: 为指定的运行时设置内存分配回调。
title: JsSetRuntimeMemoryAllocationCallback 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsSetRuntimeMemoryAllocationCallback
helpviewer_keywords:
- JsSetRuntimeMemoryAllocationCallback function
ms.assetid: 6aa7d58d-6456-4df1-815f-1ba36fb4ae14
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: ee2abf36e14c26ac58b90d48a6115fd6502307c9
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232356"
---
# <span data-ttu-id="d5cda-103">JsSetRuntimeMemoryAllocationCallback 函数</span><span class="sxs-lookup"><span data-stu-id="d5cda-103">JsSetRuntimeMemoryAllocationCallback Function</span></span>

<span data-ttu-id="d5cda-104">为指定的运行时设置内存分配回调。</span><span class="sxs-lookup"><span data-stu-id="d5cda-104">Sets a memory allocation callback for specified runtime.</span></span>  
  
## <span data-ttu-id="d5cda-105">语法</span><span class="sxs-lookup"><span data-stu-id="d5cda-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsSetRuntimeMemoryAllocationCallback(  
   _In_ JsRuntimeHandle runtime,  
   _In_opt_ void *callbackState,  
   _In_ JsMemoryAllocationCallback allocationCallback  
);  
```  
  
#### <span data-ttu-id="d5cda-106">参数</span><span class="sxs-lookup"><span data-stu-id="d5cda-106">Parameters</span></span>  
 `runtime`  
 <span data-ttu-id="d5cda-107">要注册其分配回调的运行时。</span><span class="sxs-lookup"><span data-stu-id="d5cda-107">The runtime for which to register the allocation callback.</span></span>  
  
 `callbackState`  
 <span data-ttu-id="d5cda-108">用户提供的状态将传递回回调。</span><span class="sxs-lookup"><span data-stu-id="d5cda-108">User provided state that will be passed back to the callback.</span></span>  
  
 `allocationCallback`  
 <span data-ttu-id="d5cda-109">为内存分配事件调用的内存分配回调。</span><span class="sxs-lookup"><span data-stu-id="d5cda-109">Memory allocation callback to be called for memory allocation events.</span></span>  
  
## <span data-ttu-id="d5cda-110">返回值</span><span class="sxs-lookup"><span data-stu-id="d5cda-110">Return Value</span></span>  
 <span data-ttu-id="d5cda-111">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="d5cda-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="d5cda-112">备注</span><span class="sxs-lookup"><span data-stu-id="d5cda-112">Remarks</span></span>  
 <span data-ttu-id="d5cda-113">注册内存分配回调将导致运行时在从操作系统获取内存或向操作系统释放内存时回调主机。</span><span class="sxs-lookup"><span data-stu-id="d5cda-113">Registering a memory allocation callback will cause the runtime to call back to the host whenever it acquires memory from, or releases memory to, the OS.</span></span> <span data-ttu-id="d5cda-114">在运行时内存管理器分配内存块之前调用回调例程。</span><span class="sxs-lookup"><span data-stu-id="d5cda-114">The callback routine is called before the runtime memory manager allocates a block of memory.</span></span> <span data-ttu-id="d5cda-115">如果回调返回 false，则分配将被拒绝。</span><span class="sxs-lookup"><span data-stu-id="d5cda-115">The allocation will be rejected if the callback returns false.</span></span> <span data-ttu-id="d5cda-116">运行时内存管理器还将在释放内存块后以及分配失败后调用回调例程。</span><span class="sxs-lookup"><span data-stu-id="d5cda-116">The runtime memory manager will also invoke the callback routine after freeing a block of memory, as well as after allocation failures.</span></span>  
  
 <span data-ttu-id="d5cda-117">在当前运行时执行线程上调用回调，因此在回调完成之前将阻止执行。</span><span class="sxs-lookup"><span data-stu-id="d5cda-117">The callback is invoked on the current runtime execution thread, therefore execution is blocked until the callback completes.</span></span>  
  
 <span data-ttu-id="d5cda-118">不存储回调的返回值;以前拒绝的分配不会阻止运行时稍后再次调用回调以用于新的内存分配。</span><span class="sxs-lookup"><span data-stu-id="d5cda-118">The return value of the callback is not stored; previously rejected allocations will not prevent the runtime from invoking the callback again later for new memory allocations.</span></span>  
  
## <span data-ttu-id="d5cda-119">要求</span><span class="sxs-lookup"><span data-stu-id="d5cda-119">Requirements</span></span>  
 <span data-ttu-id="d5cda-120">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="d5cda-120">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="d5cda-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d5cda-121">See Also</span></span>  
 [<span data-ttu-id="d5cda-122">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="d5cda-122">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
