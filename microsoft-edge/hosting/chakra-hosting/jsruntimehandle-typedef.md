---
description: Chakra 运行时的句柄。
title: JsRuntimeHandle Typedef |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 69e59bfd-9b0e-4710-9aa8-fbd6844171bc
caps.latest.revision: 6
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 4ccdcf39ec6062db47e1b9de249d75c8804de405
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564189"
---
# <span data-ttu-id="b67f5-103">JsRuntimeHandle Typedef</span><span class="sxs-lookup"><span data-stu-id="b67f5-103">JsRuntimeHandle Typedef</span></span>
<span data-ttu-id="b67f5-104">Chakra 运行时的句柄。</span><span class="sxs-lookup"><span data-stu-id="b67f5-104">A handle to a Chakra runtime.</span></span>  
  
## <span data-ttu-id="b67f5-105">语法</span><span class="sxs-lookup"><span data-stu-id="b67f5-105">Syntax</span></span>  
  
```cpp  
typedef void *JsRuntimeHandle;  
```  
  
## <span data-ttu-id="b67f5-106">备注</span><span class="sxs-lookup"><span data-stu-id="b67f5-106">Remarks</span></span>  
 <span data-ttu-id="b67f5-107">每个 Chakra 运行时都有其自己的独立执行引擎、JIT 编译器和垃圾回收的堆。</span><span class="sxs-lookup"><span data-stu-id="b67f5-107">Each Chakra runtime has its own independent execution engine, JIT compiler, and garbage collected heap.</span></span> <span data-ttu-id="b67f5-108">因此，每个运行时都与其他运行时完全隔离。</span><span class="sxs-lookup"><span data-stu-id="b67f5-108">As such, each runtime is completely isolated from other runtimes.</span></span>  
  
 <span data-ttu-id="b67f5-109">运行时可以在任何线程上使用，但每次只能有一个线程可以调用运行时。</span><span class="sxs-lookup"><span data-stu-id="b67f5-109">Runtimes can be used on any thread, but only one thread can call into a runtime at any time.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="b67f5-110">与 Chakra 托管 API 中的其他对象引用不同，JsRuntimeHandle 不会被垃圾回收，因为它包含垃圾回收的堆本身。</span><span class="sxs-lookup"><span data-stu-id="b67f5-110">A JsRuntimeHandle, unlike other object references in the Chakra hosting API, is not garbage collected since it contains the garbage collected heap itself.</span></span> <span data-ttu-id="b67f5-111">在调用 JsDisposeRuntime 之前，运行时将继续存在。</span><span class="sxs-lookup"><span data-stu-id="b67f5-111">A runtime will continue to exist until JsDisposeRuntime is called.</span></span>  
  
## <span data-ttu-id="b67f5-112">要求</span><span class="sxs-lookup"><span data-stu-id="b67f5-112">Requirements</span></span>  
 <span data-ttu-id="b67f5-113">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="b67f5-113">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="b67f5-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b67f5-114">See Also</span></span>  
 [<span data-ttu-id="b67f5-115">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="b67f5-115">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)