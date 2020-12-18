---
description: 创建具有名称的新 JavaScript 函数。
title: JsCreateNamedFunction 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 72f40d06-ab82-4fed-a632-68af6b4126c2
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: b54add359422a9312a0ded641051fd04585f3d7e
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232338"
---
# <span data-ttu-id="156ed-103">JsCreateNamedFunction 函数</span><span class="sxs-lookup"><span data-stu-id="156ed-103">JsCreateNamedFunction Function</span></span>

<span data-ttu-id="156ed-104">创建具有名称的新 JavaScript 函数。</span><span class="sxs-lookup"><span data-stu-id="156ed-104">Creates a new JavaScript function with name.</span></span>
  
## <span data-ttu-id="156ed-105">语法</span><span class="sxs-lookup"><span data-stu-id="156ed-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateNamedFunction(  
   _In_ JsValueRef name,  
   _In_ JsNativeFunction nativeFunction,  
   _In_opt_ void *callbackState,  
   _Out_ JsValueRef *function  
);  
```  
  
#### <span data-ttu-id="156ed-106">参数</span><span class="sxs-lookup"><span data-stu-id="156ed-106">Parameters</span></span>  
 `name`  
 <span data-ttu-id="156ed-107">将用于诊断和字符串化目的的此函数的名称。</span><span class="sxs-lookup"><span data-stu-id="156ed-107">The name of this function that will be used for diagnostics and stringification purposes.</span></span>  
  
 `nativeFunction`  
 <span data-ttu-id="156ed-108">调用函数时要调用的方法。</span><span class="sxs-lookup"><span data-stu-id="156ed-108">The method to call when the function is invoked.</span></span>  
  
 `callbackState`  
 <span data-ttu-id="156ed-109">用户提供的状态将传递回回调。</span><span class="sxs-lookup"><span data-stu-id="156ed-109">User provided state that will be passed back to the callback.</span></span>  
  
 `function`  
 <span data-ttu-id="156ed-110">新函数对象。</span><span class="sxs-lookup"><span data-stu-id="156ed-110">The new function object.</span></span>  
  
## <span data-ttu-id="156ed-111">返回值</span><span class="sxs-lookup"><span data-stu-id="156ed-111">Return Value</span></span>  
  
## <span data-ttu-id="156ed-112">备注</span><span class="sxs-lookup"><span data-stu-id="156ed-112">Remarks</span></span>  
 <span data-ttu-id="156ed-113">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="156ed-113">Requires an active script context.</span></span>  
  
 <span data-ttu-id="156ed-114">此 API 仅在 Microsoft Edge 模式下受支持。</span><span class="sxs-lookup"><span data-stu-id="156ed-114">This API is supported only in Microsoft Edge mode.</span></span>  
  
## <span data-ttu-id="156ed-115">要求</span><span class="sxs-lookup"><span data-stu-id="156ed-115">Requirements</span></span>  
 <span data-ttu-id="156ed-116">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="156ed-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="156ed-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="156ed-117">See Also</span></span>  
 [<span data-ttu-id="156ed-118">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="156ed-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
