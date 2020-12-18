---
description: 一个对 Chakra 运行时的句柄。
title: JsRuntimeHandle Typedef |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 69e59bfd-9b0e-4710-9aa8-fbd6844171bc
caps.latest.revision: 6
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: ab08243505b9699fe07ca2e80f7294adf9eb78ad
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232183"
---
# <span data-ttu-id="76add-103">JsRuntimeHandle Typedef</span><span class="sxs-lookup"><span data-stu-id="76add-103">JsRuntimeHandle Typedef</span></span>

<span data-ttu-id="76add-104">一个对 Chakra 运行时的句柄。</span><span class="sxs-lookup"><span data-stu-id="76add-104">A handle to a Chakra runtime.</span></span>  
  
## <span data-ttu-id="76add-105">语法</span><span class="sxs-lookup"><span data-stu-id="76add-105">Syntax</span></span>  
  
```cpp  
typedef void *JsRuntimeHandle;  
```  
  
## <span data-ttu-id="76add-106">备注</span><span class="sxs-lookup"><span data-stu-id="76add-106">Remarks</span></span>  
 <span data-ttu-id="76add-107">每个 Chakra 运行时都有其自己的独立执行引擎、JIT 编译器和垃圾回收堆。</span><span class="sxs-lookup"><span data-stu-id="76add-107">Each Chakra runtime has its own independent execution engine, JIT compiler, and garbage collected heap.</span></span> <span data-ttu-id="76add-108">因此，每个运行时与其他运行时完全隔离。</span><span class="sxs-lookup"><span data-stu-id="76add-108">As such, each runtime is completely isolated from other runtimes.</span></span>  
  
 <span data-ttu-id="76add-109">运行时可用于任何线程，但每次只能有一个线程调用运行时。</span><span class="sxs-lookup"><span data-stu-id="76add-109">Runtimes can be used on any thread, but only one thread can call into a runtime at any time.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="76add-110">JsRuntimeHandle 与 Chakra 托管 API 中的其他对象引用不同，它不包含垃圾回收，因为它包含垃圾回收堆本身。</span><span class="sxs-lookup"><span data-stu-id="76add-110">A JsRuntimeHandle, unlike other object references in the Chakra hosting API, is not garbage collected since it contains the garbage collected heap itself.</span></span> <span data-ttu-id="76add-111">在调用 JsDisposeRuntime 之前，运行时将继续存在。</span><span class="sxs-lookup"><span data-stu-id="76add-111">A runtime will continue to exist until JsDisposeRuntime is called.</span></span>  
  
## <span data-ttu-id="76add-112">要求</span><span class="sxs-lookup"><span data-stu-id="76add-112">Requirements</span></span>  
 <span data-ttu-id="76add-113">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="76add-113">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="76add-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="76add-114">See Also</span></span>  
 [<span data-ttu-id="76add-115">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="76add-115">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
