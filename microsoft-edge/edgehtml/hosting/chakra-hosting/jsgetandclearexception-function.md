---
description: 返回导致当前上下文的运行时为异常状态并重置该运行时的异常状态异常。
title: JsGetAndClearException 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsGetAndClearException
helpviewer_keywords:
- JsGetAndClearException function
ms.assetid: 6aec8a88-41ee-47f6-b5f4-32f3cae6bb7b
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: cb296ea351d0466a856d5ac020550ebacc254ac9
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232324"
---
# <span data-ttu-id="c22d5-103">JsGetAndClearException 函数</span><span class="sxs-lookup"><span data-stu-id="c22d5-103">JsGetAndClearException Function</span></span>

<span data-ttu-id="c22d5-104">返回导致当前上下文的运行时为异常状态并重置该运行时的异常状态异常。</span><span class="sxs-lookup"><span data-stu-id="c22d5-104">Returns the exception that caused the runtime of the current context to be in the exception state and resets the exception state for that runtime.</span></span>  
  
## <span data-ttu-id="c22d5-105">语法</span><span class="sxs-lookup"><span data-stu-id="c22d5-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetAndClearException(  
   _Out_ JsValueRef *exception  
);  
```  
  
#### <span data-ttu-id="c22d5-106">参数</span><span class="sxs-lookup"><span data-stu-id="c22d5-106">Parameters</span></span>  
 `exception`  
 <span data-ttu-id="c22d5-107">当前上下文运行时的异常。</span><span class="sxs-lookup"><span data-stu-id="c22d5-107">The exception for the runtime of the current context.</span></span>  
  
## <span data-ttu-id="c22d5-108">返回值</span><span class="sxs-lookup"><span data-stu-id="c22d5-108">Return Value</span></span>  
 <span data-ttu-id="c22d5-109">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="c22d5-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="c22d5-110">备注</span><span class="sxs-lookup"><span data-stu-id="c22d5-110">Remarks</span></span>  
 <span data-ttu-id="c22d5-111">如果当前上下文的运行时未在异常状态中，则此 API 将返回 `JsErrorInvalidArgument` 。</span><span class="sxs-lookup"><span data-stu-id="c22d5-111">If the runtime of the current context is not in an exception state, this API will return `JsErrorInvalidArgument`.</span></span> <span data-ttu-id="c22d5-112">如果禁用运行时，这将返回一个指示脚本已终止的异常，但它不会清除该异常 (如果使用) 重新启用运行时，将 `JsEnableRuntimeExecution` 清除该异常。</span><span class="sxs-lookup"><span data-stu-id="c22d5-112">If the runtime is disabled, this will return an exception indicating that the script was terminated, but it will not clear the exception (the exception will be cleared if the runtime is re-enabled using `JsEnableRuntimeExecution`).</span></span>  
  
 <span data-ttu-id="c22d5-113">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="c22d5-113">Requires an active script context.</span></span>  
  
## <span data-ttu-id="c22d5-114">要求</span><span class="sxs-lookup"><span data-stu-id="c22d5-114">Requirements</span></span>  
 <span data-ttu-id="c22d5-115">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="c22d5-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="c22d5-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c22d5-116">See Also</span></span>  
 [<span data-ttu-id="c22d5-117">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="c22d5-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
