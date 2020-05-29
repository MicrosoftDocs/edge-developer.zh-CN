---
description: 将当前上下文的运行时设置为异常状态。
title: JsSetException 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsSetException
helpviewer_keywords:
- JsSetException function
ms.assetid: c528793a-2e1b-4ee1-bd2e-e63fd547dc40
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 75d2895a725c622a0b46887d10154c3a0c56c7e9
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564181"
---
# <span data-ttu-id="04e8d-103">JsSetException 函数</span><span class="sxs-lookup"><span data-stu-id="04e8d-103">JsSetException Function</span></span>
<span data-ttu-id="04e8d-104">将当前上下文的运行时设置为异常状态。</span><span class="sxs-lookup"><span data-stu-id="04e8d-104">Sets the runtime of the current context to an exception state.</span></span>  
  
## <span data-ttu-id="04e8d-105">语法</span><span class="sxs-lookup"><span data-stu-id="04e8d-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsSetException(  
   _In_ JsValueRef exception  
);  
```  
  
#### <span data-ttu-id="04e8d-106">参数</span><span class="sxs-lookup"><span data-stu-id="04e8d-106">Parameters</span></span>  
 `exception`  
 <span data-ttu-id="04e8d-107">要为当前上下文的运行时设置的 JavaScript 异常。</span><span class="sxs-lookup"><span data-stu-id="04e8d-107">The JavaScript exception to set for the runtime of the current context.</span></span>  
  
## <span data-ttu-id="04e8d-108">返回值</span><span class="sxs-lookup"><span data-stu-id="04e8d-108">Return Value</span></span>  
 `JsNoError` <span data-ttu-id="04e8d-109">如果引擎已设置为例外状态，则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="04e8d-109">if the engine was set into an exception state, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="04e8d-110">备注</span><span class="sxs-lookup"><span data-stu-id="04e8d-110">Remarks</span></span>  
 <span data-ttu-id="04e8d-111">如果当前上下文的运行时已处于异常状态，此 API 将返回 `JsErrorInExceptionState` 。</span><span class="sxs-lookup"><span data-stu-id="04e8d-111">If the runtime of the current context is already in an exception state, this API will return `JsErrorInExceptionState`.</span></span>  
  
 <span data-ttu-id="04e8d-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="04e8d-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="04e8d-113">要求</span><span class="sxs-lookup"><span data-stu-id="04e8d-113">Requirements</span></span>  
 <span data-ttu-id="04e8d-114">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="04e8d-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="04e8d-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="04e8d-115">See Also</span></span>  
 [<span data-ttu-id="04e8d-116">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="04e8d-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)