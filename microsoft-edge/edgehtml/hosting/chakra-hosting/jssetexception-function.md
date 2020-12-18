---
description: 将当前上下文的运行时设置为异常状态。
title: JsSetException 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsSetException
helpviewer_keywords:
- JsSetException function
ms.assetid: c528793a-2e1b-4ee1-bd2e-e63fd547dc40
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 2c2e3840d2a831db23a525c5d8854b9b2fcfb8c9
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232397"
---
# <span data-ttu-id="d948b-103">JsSetException 函数</span><span class="sxs-lookup"><span data-stu-id="d948b-103">JsSetException Function</span></span>

<span data-ttu-id="d948b-104">将当前上下文的运行时设置为异常状态。</span><span class="sxs-lookup"><span data-stu-id="d948b-104">Sets the runtime of the current context to an exception state.</span></span>  
  
## <span data-ttu-id="d948b-105">语法</span><span class="sxs-lookup"><span data-stu-id="d948b-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsSetException(  
   _In_ JsValueRef exception  
);  
```  
  
#### <span data-ttu-id="d948b-106">参数</span><span class="sxs-lookup"><span data-stu-id="d948b-106">Parameters</span></span>  
 `exception`  
 <span data-ttu-id="d948b-107">为当前上下文的运行时设置的 JavaScript 异常。</span><span class="sxs-lookup"><span data-stu-id="d948b-107">The JavaScript exception to set for the runtime of the current context.</span></span>  
  
## <span data-ttu-id="d948b-108">返回值</span><span class="sxs-lookup"><span data-stu-id="d948b-108">Return Value</span></span>  
 `JsNoError` <span data-ttu-id="d948b-109">如果引擎已设置为异常状态，则否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="d948b-109">if the engine was set into an exception state, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="d948b-110">备注</span><span class="sxs-lookup"><span data-stu-id="d948b-110">Remarks</span></span>  
 <span data-ttu-id="d948b-111">如果当前上下文的运行时已进入异常状态，则此 API 将返回 `JsErrorInExceptionState` 。</span><span class="sxs-lookup"><span data-stu-id="d948b-111">If the runtime of the current context is already in an exception state, this API will return `JsErrorInExceptionState`.</span></span>  
  
 <span data-ttu-id="d948b-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="d948b-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="d948b-113">要求</span><span class="sxs-lookup"><span data-stu-id="d948b-113">Requirements</span></span>  
 <span data-ttu-id="d948b-114">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="d948b-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="d948b-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d948b-115">See Also</span></span>  
 [<span data-ttu-id="d948b-116">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="d948b-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
