---
description: 枚举当前上下文的堆。
title: JsEnumerateHeap 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsEnumerateHeap
helpviewer_keywords:
- JsEnumerateHeap function
ms.assetid: 3e518e0b-b959-4686-899c-83e6b1946c9d
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: f1c2590388fcc09b641e3908d45eef7271bcb1ad
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564272"
---
# <span data-ttu-id="ca665-103">JsEnumerateHeap 函数</span><span class="sxs-lookup"><span data-stu-id="ca665-103">JsEnumerateHeap Function</span></span>
<span data-ttu-id="ca665-104">枚举当前上下文的堆。</span><span class="sxs-lookup"><span data-stu-id="ca665-104">Enumerates the heap of the current context.</span></span>  
  
## <span data-ttu-id="ca665-105">语法</span><span class="sxs-lookup"><span data-stu-id="ca665-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsEnumerateHeap(  
   _Out_ IActiveScriptProfilerHeapEnum **enumerator  
);  
```  
  
#### <span data-ttu-id="ca665-106">参数</span><span class="sxs-lookup"><span data-stu-id="ca665-106">Parameters</span></span>  
 `enumerator`  
 <span data-ttu-id="ca665-107">堆枚举器。</span><span class="sxs-lookup"><span data-stu-id="ca665-107">The heap enumerator.</span></span>  
  
## <span data-ttu-id="ca665-108">返回值</span><span class="sxs-lookup"><span data-stu-id="ca665-108">Return Value</span></span>  
 <span data-ttu-id="ca665-109">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="ca665-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="ca665-110">备注</span><span class="sxs-lookup"><span data-stu-id="ca665-110">Remarks</span></span>  
 <span data-ttu-id="ca665-111">枚举堆时，无法删除当前上下文，并且在释放堆枚举器之前，所有对上下文状态进行修改的调用都将失败。</span><span class="sxs-lookup"><span data-stu-id="ca665-111">While the heap is being enumerated, the current context cannot be removed, and all calls to modify the state of the context will fail until the heap enumerator is released.</span></span>  
  
 <span data-ttu-id="ca665-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="ca665-112">Requires an active script context.</span></span>  
  
 <span data-ttu-id="ca665-113">此 API 在桌面应用中受支持，但在应用商店应用中不受支持。</span><span class="sxs-lookup"><span data-stu-id="ca665-113">This API is supported in desktop apps, but is not supported in Store apps.</span></span>  
  
## <span data-ttu-id="ca665-114">要求</span><span class="sxs-lookup"><span data-stu-id="ca665-114">Requirements</span></span>  
 <span data-ttu-id="ca665-115">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="ca665-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="ca665-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ca665-116">See Also</span></span>  
 [<span data-ttu-id="ca665-117">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="ca665-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)