---
description: 在当前上下文中开始分析。
title: JsStartProfiling 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsStartProfiling
helpviewer_keywords:
- JsStartProfiling function
ms.assetid: 638da395-42dd-4fc5-b581-819e647e887d
caps.latest.revision: 13
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 332ff04a987e6e7ae5030983af96dd48249e58e2
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232390"
---
# <span data-ttu-id="7aede-103">JsStartProfiling 函数</span><span class="sxs-lookup"><span data-stu-id="7aede-103">JsStartProfiling Function</span></span>

<span data-ttu-id="7aede-104">在当前上下文中开始分析。</span><span class="sxs-lookup"><span data-stu-id="7aede-104">Starts profiling in the current context.</span></span>  
  
## <span data-ttu-id="7aede-105">语法</span><span class="sxs-lookup"><span data-stu-id="7aede-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsStartProfiling(  
   _In_ IActiveScriptProfilerCallback *callback,  
   _In_ PROFILER_EVENT_MASK eventMask,  
   _In_ unsigned long context  
);  
```  
  
#### <span data-ttu-id="7aede-106">参数</span><span class="sxs-lookup"><span data-stu-id="7aede-106">Parameters</span></span>  
 `callback`  
 <span data-ttu-id="7aede-107">要使用分析回调。</span><span class="sxs-lookup"><span data-stu-id="7aede-107">The profiling callback to use.</span></span>  
  
 `eventMask`  
 <span data-ttu-id="7aede-108">要回调的分析事件。</span><span class="sxs-lookup"><span data-stu-id="7aede-108">The profiling events to callback with.</span></span>  
  
 `context`  
 <span data-ttu-id="7aede-109">要传递给分析回调的上下文。</span><span class="sxs-lookup"><span data-stu-id="7aede-109">A context to pass to the profiling callback.</span></span>  
  
## <span data-ttu-id="7aede-110">返回值</span><span class="sxs-lookup"><span data-stu-id="7aede-110">Return Value</span></span>  
 <span data-ttu-id="7aede-111">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="7aede-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="7aede-112">备注</span><span class="sxs-lookup"><span data-stu-id="7aede-112">Remarks</span></span>  
 <span data-ttu-id="7aede-113">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="7aede-113">Requires an active script context.</span></span>  
  
 <span data-ttu-id="7aede-114">此 API 在桌面应用中受支持，但在应用商店应用中不受支持。</span><span class="sxs-lookup"><span data-stu-id="7aede-114">This API is supported in desktop apps, but is not supported in Store apps.</span></span>  
  
## <span data-ttu-id="7aede-115">要求</span><span class="sxs-lookup"><span data-stu-id="7aede-115">Requirements</span></span>  
 <span data-ttu-id="7aede-116">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="7aede-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="7aede-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7aede-117">See Also</span></span>  
 [<span data-ttu-id="7aede-118">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="7aede-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
