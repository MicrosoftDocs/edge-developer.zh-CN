---
description: 获取运行时的当前内存限制。
title: JsGetRuntimeMemoryLimit 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsGetRuntimeMemoryLimit
helpviewer_keywords:
- JsGetRuntimeMemoryLimit function
ms.assetid: ed81ca60-99fd-46b0-89ae-f6ac07926904
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: ed04a0fb921d22eea17eaf86ef7a0152fbf2a1d0
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232710"
---
# <span data-ttu-id="3b0a2-103">JsGetRuntimeMemoryLimit 函数</span><span class="sxs-lookup"><span data-stu-id="3b0a2-103">JsGetRuntimeMemoryLimit Function</span></span>

<span data-ttu-id="3b0a2-104">获取运行时的当前内存限制。</span><span class="sxs-lookup"><span data-stu-id="3b0a2-104">Gets the current memory limit for a runtime.</span></span>  
  
## <span data-ttu-id="3b0a2-105">语法</span><span class="sxs-lookup"><span data-stu-id="3b0a2-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetRuntimeMemoryLimit(  
   _In_ JsRuntimeHandle runtime,  
   _Out_ size_t *memoryLimit  
);  
```  
  
#### <span data-ttu-id="3b0a2-106">参数</span><span class="sxs-lookup"><span data-stu-id="3b0a2-106">Parameters</span></span>  
 `runtime`  
 <span data-ttu-id="3b0a2-107">要检索其内存限制的运行时。</span><span class="sxs-lookup"><span data-stu-id="3b0a2-107">The runtime whose memory limit is to be retrieved.</span></span>  
  
 `memoryLimit`  
 <span data-ttu-id="3b0a2-108">运行时的当前内存限制（以字节为单位）或 -1（如果尚未设置限制）。</span><span class="sxs-lookup"><span data-stu-id="3b0a2-108">The runtime's current memory limit, in bytes, or -1 if no limit has been set.</span></span>  
  
## <span data-ttu-id="3b0a2-109">返回值</span><span class="sxs-lookup"><span data-stu-id="3b0a2-109">Return Value</span></span>  
 <span data-ttu-id="3b0a2-110">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="3b0a2-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="3b0a2-111">备注</span><span class="sxs-lookup"><span data-stu-id="3b0a2-111">Remarks</span></span>  
 <span data-ttu-id="3b0a2-112">运行时的内存限制始终可以检索，而不管该运行时在另一个线程上是否处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="3b0a2-112">The memory limit of a runtime can be always be retrieved, regardless of whether or not the runtime is active on another thread.</span></span>  
  
## <span data-ttu-id="3b0a2-113">要求</span><span class="sxs-lookup"><span data-stu-id="3b0a2-113">Requirements</span></span>  
 <span data-ttu-id="3b0a2-114">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="3b0a2-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="3b0a2-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3b0a2-115">See Also</span></span>  
 [<span data-ttu-id="3b0a2-116">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="3b0a2-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
