---
description: 通知运行时执行需要执行的任何空闲处理。
title: JsIdle 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsIdle
helpviewer_keywords:
- JsIdle function
ms.assetid: 372d1c62-8e19-4886-aa33-364cabc09bba
caps.latest.revision: 13
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 4da7148bf7daa3db983ab8f5bba622bfe0b19466
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564224"
---
# <span data-ttu-id="de51b-103">JsIdle 函数</span><span class="sxs-lookup"><span data-stu-id="de51b-103">JsIdle Function</span></span>
<span data-ttu-id="de51b-104">通知运行时执行需要执行的任何空闲处理。</span><span class="sxs-lookup"><span data-stu-id="de51b-104">Tells the runtime to do any idle processing it need to do.</span></span>  
  
## <span data-ttu-id="de51b-105">语法</span><span class="sxs-lookup"><span data-stu-id="de51b-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsIdle(  
   _Out_opt_ unsigned int *nextIdleTick  
);  
```  
  
#### <span data-ttu-id="de51b-106">参数</span><span class="sxs-lookup"><span data-stu-id="de51b-106">Parameters</span></span>  
 `nextIdleTick`  
 <span data-ttu-id="de51b-107">当有更多空闲工作需要执行时，下一个系统将勾选。</span><span class="sxs-lookup"><span data-stu-id="de51b-107">The next system tick when there will be more idle work to do.</span></span> <span data-ttu-id="de51b-108">可以为 null。</span><span class="sxs-lookup"><span data-stu-id="de51b-108">Can be null.</span></span> <span data-ttu-id="de51b-109">如果没有即将进行的空闲工作要执行，则返回最大刻度数。</span><span class="sxs-lookup"><span data-stu-id="de51b-109">Returns the maximum number of ticks if there no upcoming idle work to do.</span></span>  
  
## <span data-ttu-id="de51b-110">返回值</span><span class="sxs-lookup"><span data-stu-id="de51b-110">Return Value</span></span>  
 <span data-ttu-id="de51b-111">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="de51b-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="de51b-112">备注</span><span class="sxs-lookup"><span data-stu-id="de51b-112">Remarks</span></span>  
 <span data-ttu-id="de51b-113">如果当前运行时已启用空闲处理，则调用 `JsIdle` 将通知当前运行时主机处于空闲状态，并且运行时可以执行内存清理任务。</span><span class="sxs-lookup"><span data-stu-id="de51b-113">If idle processing has been enabled for the current runtime, calling `JsIdle` will inform the current runtime that the host is idle and that the runtime can perform memory cleanup tasks.</span></span>  
  
 `JsIdle` <span data-ttu-id="de51b-114">还可以返回系统计时周期数，直到有运行时需要执行的更多空闲工作。</span><span class="sxs-lookup"><span data-stu-id="de51b-114">can also return the number of system ticks until there will be more idle work for the runtime to do.</span></span> <span data-ttu-id="de51b-115">`JsIdle`此滴答数过去的通话将不起作用。</span><span class="sxs-lookup"><span data-stu-id="de51b-115">Calling `JsIdle` before this number of ticks has passed will do no work.</span></span>  
  
 <span data-ttu-id="de51b-116">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="de51b-116">Requires an active script context.</span></span>  
  
## <span data-ttu-id="de51b-117">要求</span><span class="sxs-lookup"><span data-stu-id="de51b-117">Requirements</span></span>  
 <span data-ttu-id="de51b-118">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="de51b-118">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="de51b-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="de51b-119">See Also</span></span>  
 [<span data-ttu-id="de51b-120">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="de51b-120">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)