---
description: 确定当前上下文的运行时是否位于异常状态。
title: JsHasException 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsHasException
helpviewer_keywords:
- JsHasException function
ms.assetid: ac7da3ce-c746-4154-bbb8-bcb0859a8d5b
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 4f4abbd6c69a6b2b6414dae2f1de3a2acf21cc32
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232065"
---
# <span data-ttu-id="38418-103">JsHasException 函数</span><span class="sxs-lookup"><span data-stu-id="38418-103">JsHasException Function</span></span>

<span data-ttu-id="38418-104">确定当前上下文的运行时是否位于异常状态。</span><span class="sxs-lookup"><span data-stu-id="38418-104">Determines whether the runtime of the current context is in an exception state.</span></span>  
  
## <span data-ttu-id="38418-105">语法</span><span class="sxs-lookup"><span data-stu-id="38418-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsHasException(  
   _Out_ bool *hasException  
);  
```  
  
#### <span data-ttu-id="38418-106">参数</span><span class="sxs-lookup"><span data-stu-id="38418-106">Parameters</span></span>  
 `hasException`  
 <span data-ttu-id="38418-107">当前上下文的运行时是否位于异常状态。</span><span class="sxs-lookup"><span data-stu-id="38418-107">Whether the runtime of the current context is in the exception state.</span></span>  
  
## <span data-ttu-id="38418-108">返回值</span><span class="sxs-lookup"><span data-stu-id="38418-108">Return Value</span></span>  
 <span data-ttu-id="38418-109">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="38418-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="38418-110">备注</span><span class="sxs-lookup"><span data-stu-id="38418-110">Remarks</span></span>  
 <span data-ttu-id="38418-111">如果对运行时的调用导致异常 (运行脚本或由于转换失败) ，运行时将进入"异常状态"。</span><span class="sxs-lookup"><span data-stu-id="38418-111">If a call into the runtime results in an exception (either as the result of running a script or due to something like a conversion failure), the runtime is placed into an "exception state."</span></span> <span data-ttu-id="38418-112">对运行时应用程序创建的任何上下文的所有 (异常 API 除外) 异常清除之前，将失败 `JsErrorInExceptionState` 。</span><span class="sxs-lookup"><span data-stu-id="38418-112">All calls into any context created by the runtime (except for the exception APIs) will fail with `JsErrorInExceptionState` until the exception is cleared.</span></span>  
  
 <span data-ttu-id="38418-113">如果回调返回到引擎时，当前上下文的运行时为异常状态，则引擎将自动重新引发异常。</span><span class="sxs-lookup"><span data-stu-id="38418-113">If the runtime of the current context is in the exception state when a callback returns into the engine, the engine will automatically rethrow the exception.</span></span>  
  
 <span data-ttu-id="38418-114">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="38418-114">Requires an active script context.</span></span>  
  
## <span data-ttu-id="38418-115">要求</span><span class="sxs-lookup"><span data-stu-id="38418-115">Requirements</span></span>  
 <span data-ttu-id="38418-116">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="38418-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="38418-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="38418-117">See Also</span></span>  
 [<span data-ttu-id="38418-118">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="38418-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
