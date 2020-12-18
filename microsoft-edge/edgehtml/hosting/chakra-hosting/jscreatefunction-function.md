---
description: 创建新的 JavaScript 函数。
title: JsCreateFunction 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsCreateFunction
helpviewer_keywords:
- JsCreateFunction function
ms.assetid: b298a96a-5ef7-4203-a8c8-55f9bfc6d2bb
caps.latest.revision: 13
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: f7e67e86e6d8055664bfb1b58e6d5653f6d75d1b
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232557"
---
# <span data-ttu-id="4b5de-103">JsCreateFunction 函数</span><span class="sxs-lookup"><span data-stu-id="4b5de-103">JsCreateFunction Function</span></span>

<span data-ttu-id="4b5de-104">创建新的 JavaScript 函数。</span><span class="sxs-lookup"><span data-stu-id="4b5de-104">Creates a new JavaScript function.</span></span>
  
## <span data-ttu-id="4b5de-105">语法</span><span class="sxs-lookup"><span data-stu-id="4b5de-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateFunction(  
   _In_ JsNativeFunction nativeFunction,  
   _In_opt_ void *callbackState,  
   _Out_ JsValueRef *function  
);  
```  
  
#### <span data-ttu-id="4b5de-106">参数</span><span class="sxs-lookup"><span data-stu-id="4b5de-106">Parameters</span></span>  
 `nativeFunction`  
 <span data-ttu-id="4b5de-107">调用函数时要调用的方法。</span><span class="sxs-lookup"><span data-stu-id="4b5de-107">The method to call when the function is invoked.</span></span>  
  
 `callbackState`  
 <span data-ttu-id="4b5de-108">将传递回回调的用户提供的状态。</span><span class="sxs-lookup"><span data-stu-id="4b5de-108">User-provided state that will be passed back to the callback.</span></span>  
  
 `function`  
 <span data-ttu-id="4b5de-109">新函数对象。</span><span class="sxs-lookup"><span data-stu-id="4b5de-109">The new function object.</span></span>  
  
## <span data-ttu-id="4b5de-110">返回值</span><span class="sxs-lookup"><span data-stu-id="4b5de-110">Return Value</span></span>  
 <span data-ttu-id="4b5de-111">呼叫的结果（如果有）。</span><span class="sxs-lookup"><span data-stu-id="4b5de-111">The result of the call, if any.</span></span>  
  
## <span data-ttu-id="4b5de-112">备注</span><span class="sxs-lookup"><span data-stu-id="4b5de-112">Remarks</span></span>  
 <span data-ttu-id="4b5de-113">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="4b5de-113">Requires an active script context.</span></span>  
  
## <span data-ttu-id="4b5de-114">要求</span><span class="sxs-lookup"><span data-stu-id="4b5de-114">Requirements</span></span>  
 <span data-ttu-id="4b5de-115">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="4b5de-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="4b5de-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4b5de-116">See Also</span></span>  
 [<span data-ttu-id="4b5de-117">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="4b5de-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
