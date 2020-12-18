---
description: 枚举当前上下文的堆。
title: JsEnumerateHeap 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsEnumerateHeap
helpviewer_keywords:
- JsEnumerateHeap function
ms.assetid: 3e518e0b-b959-4686-899c-83e6b1946c9d
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: bb76b28f24b769f71827e59be691188e34e9e1a3
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232547"
---
# <span data-ttu-id="19a82-103">JsEnumerateHeap 函数</span><span class="sxs-lookup"><span data-stu-id="19a82-103">JsEnumerateHeap Function</span></span>

<span data-ttu-id="19a82-104">枚举当前上下文的堆。</span><span class="sxs-lookup"><span data-stu-id="19a82-104">Enumerates the heap of the current context.</span></span>  
  
## <span data-ttu-id="19a82-105">语法</span><span class="sxs-lookup"><span data-stu-id="19a82-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsEnumerateHeap(  
   _Out_ IActiveScriptProfilerHeapEnum **enumerator  
);  
```  
  
#### <span data-ttu-id="19a82-106">参数</span><span class="sxs-lookup"><span data-stu-id="19a82-106">Parameters</span></span>  
 `enumerator`  
 <span data-ttu-id="19a82-107">堆枚举器。</span><span class="sxs-lookup"><span data-stu-id="19a82-107">The heap enumerator.</span></span>  
  
## <span data-ttu-id="19a82-108">返回值</span><span class="sxs-lookup"><span data-stu-id="19a82-108">Return Value</span></span>  
 <span data-ttu-id="19a82-109">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="19a82-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="19a82-110">备注</span><span class="sxs-lookup"><span data-stu-id="19a82-110">Remarks</span></span>  
 <span data-ttu-id="19a82-111">在枚举堆时，无法删除当前上下文，在释放堆枚举器之前，修改上下文状态的所有调用都将失败。</span><span class="sxs-lookup"><span data-stu-id="19a82-111">While the heap is being enumerated, the current context cannot be removed, and all calls to modify the state of the context will fail until the heap enumerator is released.</span></span>  
  
 <span data-ttu-id="19a82-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="19a82-112">Requires an active script context.</span></span>  
  
 <span data-ttu-id="19a82-113">此 API 在桌面应用中受支持，但在应用商店应用中不受支持。</span><span class="sxs-lookup"><span data-stu-id="19a82-113">This API is supported in desktop apps, but is not supported in Store apps.</span></span>  
  
## <span data-ttu-id="19a82-114">要求</span><span class="sxs-lookup"><span data-stu-id="19a82-114">Requirements</span></span>  
 <span data-ttu-id="19a82-115">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="19a82-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="19a82-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="19a82-116">See Also</span></span>  
 [<span data-ttu-id="19a82-117">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="19a82-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
