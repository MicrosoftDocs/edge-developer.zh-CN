---
description: 在当前上下文中停止分析。
title: JsStopProfiling 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsStopProfiling
helpviewer_keywords:
- JsStopProfiling function
ms.assetid: 3639c04f-a0f9-418b-be39-92f64b4e7ef8
caps.latest.revision: 13
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 9d021c7c9849d20283a39d6ecffc89c5b2ea0db0
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564068"
---
# <span data-ttu-id="8d818-103">JsStopProfiling 函数</span><span class="sxs-lookup"><span data-stu-id="8d818-103">JsStopProfiling Function</span></span>
<span data-ttu-id="8d818-104">在当前上下文中停止分析。</span><span class="sxs-lookup"><span data-stu-id="8d818-104">Stops profiling in the current context.</span></span>  
  
## <span data-ttu-id="8d818-105">语法</span><span class="sxs-lookup"><span data-stu-id="8d818-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsStopProfiling(  
   _In_ HRESULT reason  
);  
```  
  
#### <span data-ttu-id="8d818-106">参数</span><span class="sxs-lookup"><span data-stu-id="8d818-106">Parameters</span></span>  
 `reason`  
 <span data-ttu-id="8d818-107">停止分析以传递到探查器回调的原因。</span><span class="sxs-lookup"><span data-stu-id="8d818-107">The reason for stopping profiling to pass to the profiler callback.</span></span>  
  
## <span data-ttu-id="8d818-108">返回值</span><span class="sxs-lookup"><span data-stu-id="8d818-108">Return Value</span></span>  
 <span data-ttu-id="8d818-109">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="8d818-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="8d818-110">备注</span><span class="sxs-lookup"><span data-stu-id="8d818-110">Remarks</span></span>  
 <span data-ttu-id="8d818-111">如果分析尚未启动，则不会返回错误。</span><span class="sxs-lookup"><span data-stu-id="8d818-111">Will not return an error if profiling has not started.</span></span>  
  
 <span data-ttu-id="8d818-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="8d818-112">Requires an active script context.</span></span>  
  
 <span data-ttu-id="8d818-113">此 API 在桌面应用中受支持，但在应用商店应用中不受支持。</span><span class="sxs-lookup"><span data-stu-id="8d818-113">This API is supported in desktop apps, but is not supported in Store apps.</span></span>  
  
## <span data-ttu-id="8d818-114">要求</span><span class="sxs-lookup"><span data-stu-id="8d818-114">Requirements</span></span>  
 <span data-ttu-id="8d818-115">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="8d818-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="8d818-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8d818-116">See Also</span></span>  
 [<span data-ttu-id="8d818-117">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="8d818-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)