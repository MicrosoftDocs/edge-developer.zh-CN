---
description: 确定当前上下文的运行时是否处于异常状态。
title: JsHasException 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsHasException
helpviewer_keywords:
- JsHasException function
ms.assetid: ac7da3ce-c746-4154-bbb8-bcb0859a8d5b
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 25ddb8f9cc407dd414a6cd2210c315eb4dd7b141
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564230"
---
# <span data-ttu-id="1ea47-103">JsHasException 函数</span><span class="sxs-lookup"><span data-stu-id="1ea47-103">JsHasException Function</span></span>
<span data-ttu-id="1ea47-104">确定当前上下文的运行时是否处于异常状态。</span><span class="sxs-lookup"><span data-stu-id="1ea47-104">Determines whether the runtime of the current context is in an exception state.</span></span>  
  
## <span data-ttu-id="1ea47-105">语法</span><span class="sxs-lookup"><span data-stu-id="1ea47-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsHasException(  
   _Out_ bool *hasException  
);  
```  
  
#### <span data-ttu-id="1ea47-106">参数</span><span class="sxs-lookup"><span data-stu-id="1ea47-106">Parameters</span></span>  
 `hasException`  
 <span data-ttu-id="1ea47-107">当前上下文的运行时是否处于异常状态。</span><span class="sxs-lookup"><span data-stu-id="1ea47-107">Whether the runtime of the current context is in the exception state.</span></span>  
  
## <span data-ttu-id="1ea47-108">返回值</span><span class="sxs-lookup"><span data-stu-id="1ea47-108">Return Value</span></span>  
 <span data-ttu-id="1ea47-109">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="1ea47-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="1ea47-110">备注</span><span class="sxs-lookup"><span data-stu-id="1ea47-110">Remarks</span></span>  
 <span data-ttu-id="1ea47-111">如果对运行时的调用导致异常（因为运行脚本或由于类似转换失败），则会将运行时置于 "异常状态"。</span><span class="sxs-lookup"><span data-stu-id="1ea47-111">If a call into the runtime results in an exception (either as the result of running a script or due to something like a conversion failure), the runtime is placed into an "exception state."</span></span> <span data-ttu-id="1ea47-112">对由运行时创建的任何上下文的所有调用（除异常 Api 外）都将失败， `JsErrorInExceptionState` 直到清除该异常。</span><span class="sxs-lookup"><span data-stu-id="1ea47-112">All calls into any context created by the runtime (except for the exception APIs) will fail with `JsErrorInExceptionState` until the exception is cleared.</span></span>  
  
 <span data-ttu-id="1ea47-113">如果在回调返回到引擎时当前上下文的运行时处于异常状态，引擎将自动再次引发该异常。</span><span class="sxs-lookup"><span data-stu-id="1ea47-113">If the runtime of the current context is in the exception state when a callback returns into the engine, the engine will automatically rethrow the exception.</span></span>  
  
 <span data-ttu-id="1ea47-114">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="1ea47-114">Requires an active script context.</span></span>  
  
## <span data-ttu-id="1ea47-115">要求</span><span class="sxs-lookup"><span data-stu-id="1ea47-115">Requirements</span></span>  
 <span data-ttu-id="1ea47-116">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="1ea47-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="1ea47-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1ea47-117">See Also</span></span>  
 [<span data-ttu-id="1ea47-118">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="1ea47-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)