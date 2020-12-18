---
description: 指示运行时执行所需的任何空闲处理。
title: JsIdle 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsIdle
helpviewer_keywords:
- JsIdle function
ms.assetid: 372d1c62-8e19-4886-aa33-364cabc09bba
caps.latest.revision: 13
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: ecba0aafb6b4dcccb4485c2956cae5ce4045355f
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232711"
---
# <span data-ttu-id="860a2-103">JsIdle 函数</span><span class="sxs-lookup"><span data-stu-id="860a2-103">JsIdle Function</span></span>

<span data-ttu-id="860a2-104">指示运行时执行所需的任何空闲处理。</span><span class="sxs-lookup"><span data-stu-id="860a2-104">Tells the runtime to do any idle processing it need to do.</span></span>  
  
## <span data-ttu-id="860a2-105">语法</span><span class="sxs-lookup"><span data-stu-id="860a2-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsIdle(  
   _Out_opt_ unsigned int *nextIdleTick  
);  
```  
  
#### <span data-ttu-id="860a2-106">参数</span><span class="sxs-lookup"><span data-stu-id="860a2-106">Parameters</span></span>  
 `nextIdleTick`  
 <span data-ttu-id="860a2-107">下一个系统在将有更多的空闲工作时进行计时。</span><span class="sxs-lookup"><span data-stu-id="860a2-107">The next system tick when there will be more idle work to do.</span></span> <span data-ttu-id="860a2-108">可以是 null。</span><span class="sxs-lookup"><span data-stu-id="860a2-108">Can be null.</span></span> <span data-ttu-id="860a2-109">如果没有即将进行的空闲工作，则返回最大刻度数。</span><span class="sxs-lookup"><span data-stu-id="860a2-109">Returns the maximum number of ticks if there no upcoming idle work to do.</span></span>  
  
## <span data-ttu-id="860a2-110">返回值</span><span class="sxs-lookup"><span data-stu-id="860a2-110">Return Value</span></span>  
 <span data-ttu-id="860a2-111">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="860a2-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="860a2-112">备注</span><span class="sxs-lookup"><span data-stu-id="860a2-112">Remarks</span></span>  
 <span data-ttu-id="860a2-113">如果当前运行时已启用空闲处理，调用将通知当前运行时主机处于空闲状态，并且该运行时 `JsIdle` 可以执行内存清理任务。</span><span class="sxs-lookup"><span data-stu-id="860a2-113">If idle processing has been enabled for the current runtime, calling `JsIdle` will inform the current runtime that the host is idle and that the runtime can perform memory cleanup tasks.</span></span>  
  
 `JsIdle` <span data-ttu-id="860a2-114">还可以返回系统刻度数，直到运行时有更多的空闲工作需要执行。</span><span class="sxs-lookup"><span data-stu-id="860a2-114">can also return the number of system ticks until there will be more idle work for the runtime to do.</span></span> <span data-ttu-id="860a2-115">在 `JsIdle` 经过此数量的刻度之前调用将不起作用。</span><span class="sxs-lookup"><span data-stu-id="860a2-115">Calling `JsIdle` before this number of ticks has passed will do no work.</span></span>  
  
 <span data-ttu-id="860a2-116">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="860a2-116">Requires an active script context.</span></span>  
  
## <span data-ttu-id="860a2-117">要求</span><span class="sxs-lookup"><span data-stu-id="860a2-117">Requirements</span></span>  
 <span data-ttu-id="860a2-118">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="860a2-118">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="860a2-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="860a2-119">See Also</span></span>  
 [<span data-ttu-id="860a2-120">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="860a2-120">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
