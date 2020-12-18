---
description: 调用函数。
title: JsCallFunction 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsCallFunction
helpviewer_keywords:
- JsCallFunction function
ms.assetid: 8a1dca72-d720-4a28-a86e-6809465006fe
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: dc26f66cb7deae0857ce34cbd4d83ee26046b3c8
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232215"
---
# <span data-ttu-id="5501f-103">JsCallFunction 函数</span><span class="sxs-lookup"><span data-stu-id="5501f-103">JsCallFunction Function</span></span>

<span data-ttu-id="5501f-104">调用函数。</span><span class="sxs-lookup"><span data-stu-id="5501f-104">Invokes a function.</span></span>  
  
## <span data-ttu-id="5501f-105">语法</span><span class="sxs-lookup"><span data-stu-id="5501f-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsCallFunction(  
   _In_ JsValueRef function,  
   _In_reads_(argumentCount) JsValueRef *arguments,  
   _In_ unsigned short argumentCount,  
   _Out_opt_ JsValueRef *result  
);  
```  
  
#### <span data-ttu-id="5501f-106">参数</span><span class="sxs-lookup"><span data-stu-id="5501f-106">Parameters</span></span>  
 `function`  
 <span data-ttu-id="5501f-107">要调用的函数。</span><span class="sxs-lookup"><span data-stu-id="5501f-107">The function to invoke.</span></span>  
  
 `arguments`  
 <span data-ttu-id="5501f-108">调用的参数。</span><span class="sxs-lookup"><span data-stu-id="5501f-108">The arguments to the call.</span></span>  
  
 `argumentCount`  
 <span data-ttu-id="5501f-109">传递给函数的参数数。</span><span class="sxs-lookup"><span data-stu-id="5501f-109">The number of arguments being passed in to the function.</span></span>  
  
 `result`  
 <span data-ttu-id="5501f-110">函数调用返回的值（如果有）。</span><span class="sxs-lookup"><span data-stu-id="5501f-110">The value returned from the function invocation, if any.</span></span>  
  
## <span data-ttu-id="5501f-111">返回值</span><span class="sxs-lookup"><span data-stu-id="5501f-111">Return Value</span></span>  
 <span data-ttu-id="5501f-112">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="5501f-112">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="5501f-113">备注</span><span class="sxs-lookup"><span data-stu-id="5501f-113">Remarks</span></span>  
 <span data-ttu-id="5501f-114">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="5501f-114">Requires an active script context.</span></span>  
  
## <span data-ttu-id="5501f-115">要求</span><span class="sxs-lookup"><span data-stu-id="5501f-115">Requirements</span></span>  
 <span data-ttu-id="5501f-116">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="5501f-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="5501f-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5501f-117">See Also</span></span>  
 [<span data-ttu-id="5501f-118">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="5501f-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
