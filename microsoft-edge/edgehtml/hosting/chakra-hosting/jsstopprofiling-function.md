---
description: 在当前上下文中停止分析。
title: JsStopProfiling 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsStopProfiling
helpviewer_keywords:
- JsStopProfiling function
ms.assetid: 3639c04f-a0f9-418b-be39-92f64b4e7ef8
caps.latest.revision: 13
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 02c42afda7e61d71b90a9a1a71aa71cc53584ff8
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232391"
---
# <span data-ttu-id="6f704-103">JsStopProfiling 函数</span><span class="sxs-lookup"><span data-stu-id="6f704-103">JsStopProfiling Function</span></span>

<span data-ttu-id="6f704-104">在当前上下文中停止分析。</span><span class="sxs-lookup"><span data-stu-id="6f704-104">Stops profiling in the current context.</span></span>  
  
## <span data-ttu-id="6f704-105">语法</span><span class="sxs-lookup"><span data-stu-id="6f704-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsStopProfiling(  
   _In_ HRESULT reason  
);  
```  
  
#### <span data-ttu-id="6f704-106">参数</span><span class="sxs-lookup"><span data-stu-id="6f704-106">Parameters</span></span>  
 `reason`  
 <span data-ttu-id="6f704-107">停止分析以传递到探查器回调的原因。</span><span class="sxs-lookup"><span data-stu-id="6f704-107">The reason for stopping profiling to pass to the profiler callback.</span></span>  
  
## <span data-ttu-id="6f704-108">返回值</span><span class="sxs-lookup"><span data-stu-id="6f704-108">Return Value</span></span>  
 <span data-ttu-id="6f704-109">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="6f704-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="6f704-110">备注</span><span class="sxs-lookup"><span data-stu-id="6f704-110">Remarks</span></span>  
 <span data-ttu-id="6f704-111">如果分析尚未启动，将不会返回错误。</span><span class="sxs-lookup"><span data-stu-id="6f704-111">Will not return an error if profiling has not started.</span></span>  
  
 <span data-ttu-id="6f704-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="6f704-112">Requires an active script context.</span></span>  
  
 <span data-ttu-id="6f704-113">此 API 在桌面应用中受支持，但在应用商店应用中不受支持。</span><span class="sxs-lookup"><span data-stu-id="6f704-113">This API is supported in desktop apps, but is not supported in Store apps.</span></span>  
  
## <span data-ttu-id="6f704-114">要求</span><span class="sxs-lookup"><span data-stu-id="6f704-114">Requirements</span></span>  
 <span data-ttu-id="6f704-115">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="6f704-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="6f704-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6f704-116">See Also</span></span>  
 [<span data-ttu-id="6f704-117">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="6f704-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
