---
description: 返回导致当前上下文的运行时处于异常状态并为该运行时重置异常状态的异常。
title: JsGetAndClearException 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsGetAndClearException
helpviewer_keywords:
- JsGetAndClearException function
ms.assetid: 6aec8a88-41ee-47f6-b5f4-32f3cae6bb7b
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: eb70b4b66b4bb270d9f26487708720efddc2effa
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564264"
---
# <span data-ttu-id="43829-103">JsGetAndClearException 函数</span><span class="sxs-lookup"><span data-stu-id="43829-103">JsGetAndClearException Function</span></span>
<span data-ttu-id="43829-104">返回导致当前上下文的运行时处于异常状态并为该运行时重置异常状态的异常。</span><span class="sxs-lookup"><span data-stu-id="43829-104">Returns the exception that caused the runtime of the current context to be in the exception state and resets the exception state for that runtime.</span></span>  
  
## <span data-ttu-id="43829-105">语法</span><span class="sxs-lookup"><span data-stu-id="43829-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetAndClearException(  
   _Out_ JsValueRef *exception  
);  
```  
  
#### <span data-ttu-id="43829-106">参数</span><span class="sxs-lookup"><span data-stu-id="43829-106">Parameters</span></span>  
 `exception`  
 <span data-ttu-id="43829-107">当前上下文的运行时的异常。</span><span class="sxs-lookup"><span data-stu-id="43829-107">The exception for the runtime of the current context.</span></span>  
  
## <span data-ttu-id="43829-108">返回值</span><span class="sxs-lookup"><span data-stu-id="43829-108">Return Value</span></span>  
 <span data-ttu-id="43829-109">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="43829-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="43829-110">备注</span><span class="sxs-lookup"><span data-stu-id="43829-110">Remarks</span></span>  
 <span data-ttu-id="43829-111">如果当前上下文的运行时未处于异常状态，此 API 将返回 `JsErrorInvalidArgument` 。</span><span class="sxs-lookup"><span data-stu-id="43829-111">If the runtime of the current context is not in an exception state, this API will return `JsErrorInvalidArgument`.</span></span> <span data-ttu-id="43829-112">如果运行时已禁用，这将返回一个异常，指示脚本已终止，但不会清除异常（如果运行时使用重新启用，则会清除异常 `JsEnableRuntimeExecution` ）。</span><span class="sxs-lookup"><span data-stu-id="43829-112">If the runtime is disabled, this will return an exception indicating that the script was terminated, but it will not clear the exception (the exception will be cleared if the runtime is re-enabled using `JsEnableRuntimeExecution`).</span></span>  
  
 <span data-ttu-id="43829-113">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="43829-113">Requires an active script context.</span></span>  
  
## <span data-ttu-id="43829-114">要求</span><span class="sxs-lookup"><span data-stu-id="43829-114">Requirements</span></span>  
 <span data-ttu-id="43829-115">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="43829-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="43829-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="43829-116">See Also</span></span>  
 [<span data-ttu-id="43829-117">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="43829-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)