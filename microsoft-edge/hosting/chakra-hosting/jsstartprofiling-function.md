---
description: 在当前上下文中开始分析。
title: JsStartProfiling 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsStartProfiling
helpviewer_keywords:
- JsStartProfiling function
ms.assetid: 638da395-42dd-4fc5-b581-819e647e887d
caps.latest.revision: 13
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 891c39305e08d214a8f06b680c7022683a9d6fe4
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564069"
---
# <span data-ttu-id="4b2b6-103">JsStartProfiling 函数</span><span class="sxs-lookup"><span data-stu-id="4b2b6-103">JsStartProfiling Function</span></span>
<span data-ttu-id="4b2b6-104">在当前上下文中开始分析。</span><span class="sxs-lookup"><span data-stu-id="4b2b6-104">Starts profiling in the current context.</span></span>  
  
## <span data-ttu-id="4b2b6-105">语法</span><span class="sxs-lookup"><span data-stu-id="4b2b6-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsStartProfiling(  
   _In_ IActiveScriptProfilerCallback *callback,  
   _In_ PROFILER_EVENT_MASK eventMask,  
   _In_ unsigned long context  
);  
```  
  
#### <span data-ttu-id="4b2b6-106">参数</span><span class="sxs-lookup"><span data-stu-id="4b2b6-106">Parameters</span></span>  
 `callback`  
 <span data-ttu-id="4b2b6-107">要使用的分析回调。</span><span class="sxs-lookup"><span data-stu-id="4b2b6-107">The profiling callback to use.</span></span>  
  
 `eventMask`  
 <span data-ttu-id="4b2b6-108">要回调的分析事件。</span><span class="sxs-lookup"><span data-stu-id="4b2b6-108">The profiling events to callback with.</span></span>  
  
 `context`  
 <span data-ttu-id="4b2b6-109">要传递到分析回调的上下文。</span><span class="sxs-lookup"><span data-stu-id="4b2b6-109">A context to pass to the profiling callback.</span></span>  
  
## <span data-ttu-id="4b2b6-110">返回值</span><span class="sxs-lookup"><span data-stu-id="4b2b6-110">Return Value</span></span>  
 <span data-ttu-id="4b2b6-111">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="4b2b6-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="4b2b6-112">备注</span><span class="sxs-lookup"><span data-stu-id="4b2b6-112">Remarks</span></span>  
 <span data-ttu-id="4b2b6-113">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="4b2b6-113">Requires an active script context.</span></span>  
  
 <span data-ttu-id="4b2b6-114">此 API 在桌面应用中受支持，但在应用商店应用中不受支持。</span><span class="sxs-lookup"><span data-stu-id="4b2b6-114">This API is supported in desktop apps, but is not supported in Store apps.</span></span>  
  
## <span data-ttu-id="4b2b6-115">要求</span><span class="sxs-lookup"><span data-stu-id="4b2b6-115">Requirements</span></span>  
 <span data-ttu-id="4b2b6-116">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="4b2b6-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="4b2b6-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4b2b6-117">See Also</span></span>  
 [<span data-ttu-id="4b2b6-118">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="4b2b6-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)