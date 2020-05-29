---
description: 为指定的运行时设置内存分配回调。
title: JsSetRuntimeMemoryAllocationCallback 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsSetRuntimeMemoryAllocationCallback
helpviewer_keywords:
- JsSetRuntimeMemoryAllocationCallback function
ms.assetid: 6aa7d58d-6456-4df1-815f-1ba36fb4ae14
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 5c648761473023f00e894fbf75c794cfcc9422c5
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564074"
---
# <span data-ttu-id="a95e4-103">JsSetRuntimeMemoryAllocationCallback 函数</span><span class="sxs-lookup"><span data-stu-id="a95e4-103">JsSetRuntimeMemoryAllocationCallback Function</span></span>
<span data-ttu-id="a95e4-104">为指定的运行时设置内存分配回调。</span><span class="sxs-lookup"><span data-stu-id="a95e4-104">Sets a memory allocation callback for specified runtime.</span></span>  
  
## <span data-ttu-id="a95e4-105">语法</span><span class="sxs-lookup"><span data-stu-id="a95e4-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsSetRuntimeMemoryAllocationCallback(  
   _In_ JsRuntimeHandle runtime,  
   _In_opt_ void *callbackState,  
   _In_ JsMemoryAllocationCallback allocationCallback  
);  
```  
  
#### <span data-ttu-id="a95e4-106">参数</span><span class="sxs-lookup"><span data-stu-id="a95e4-106">Parameters</span></span>  
 `runtime`  
 <span data-ttu-id="a95e4-107">要注册分配回调的运行时。</span><span class="sxs-lookup"><span data-stu-id="a95e4-107">The runtime for which to register the allocation callback.</span></span>  
  
 `callbackState`  
 <span data-ttu-id="a95e4-108">用户提供的状态将传回回拨。</span><span class="sxs-lookup"><span data-stu-id="a95e4-108">User provided state that will be passed back to the callback.</span></span>  
  
 `allocationCallback`  
 <span data-ttu-id="a95e4-109">为内存分配事件调用内存分配回调。</span><span class="sxs-lookup"><span data-stu-id="a95e4-109">Memory allocation callback to be called for memory allocation events.</span></span>  
  
## <span data-ttu-id="a95e4-110">返回值</span><span class="sxs-lookup"><span data-stu-id="a95e4-110">Return Value</span></span>  
 <span data-ttu-id="a95e4-111">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="a95e4-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="a95e4-112">备注</span><span class="sxs-lookup"><span data-stu-id="a95e4-112">Remarks</span></span>  
 <span data-ttu-id="a95e4-113">注册内存分配回调将使运行时在从操作系统获取内存或释放内存到操作系统时回调主机。</span><span class="sxs-lookup"><span data-stu-id="a95e4-113">Registering a memory allocation callback will cause the runtime to call back to the host whenever it acquires memory from, or releases memory to, the OS.</span></span> <span data-ttu-id="a95e4-114">在运行时内存管理器分配内存块之前调用回调例程。</span><span class="sxs-lookup"><span data-stu-id="a95e4-114">The callback routine is called before the runtime memory manager allocates a block of memory.</span></span> <span data-ttu-id="a95e4-115">如果回调返回 false，则分配将被拒绝。</span><span class="sxs-lookup"><span data-stu-id="a95e4-115">The allocation will be rejected if the callback returns false.</span></span> <span data-ttu-id="a95e4-116">在释放内存块以及分配失败后，运行时内存管理器也将调用回调例程。</span><span class="sxs-lookup"><span data-stu-id="a95e4-116">The runtime memory manager will also invoke the callback routine after freeing a block of memory, as well as after allocation failures.</span></span>  
  
 <span data-ttu-id="a95e4-117">回调将在当前运行时执行线程上调用，因此执行会被阻止，直到回调完成。</span><span class="sxs-lookup"><span data-stu-id="a95e4-117">The callback is invoked on the current runtime execution thread, therefore execution is blocked until the callback completes.</span></span>  
  
 <span data-ttu-id="a95e4-118">不存储回调的返回值;以前拒绝的分配不会阻止运行时再次调用新内存分配的回调。</span><span class="sxs-lookup"><span data-stu-id="a95e4-118">The return value of the callback is not stored; previously rejected allocations will not prevent the runtime from invoking the callback again later for new memory allocations.</span></span>  
  
## <span data-ttu-id="a95e4-119">要求</span><span class="sxs-lookup"><span data-stu-id="a95e4-119">Requirements</span></span>  
 <span data-ttu-id="a95e4-120">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="a95e4-120">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="a95e4-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a95e4-121">See Also</span></span>  
 [<span data-ttu-id="a95e4-122">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="a95e4-122">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)