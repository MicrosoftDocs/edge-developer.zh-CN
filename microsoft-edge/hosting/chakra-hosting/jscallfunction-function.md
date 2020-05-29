---
description: 调用函数。
title: JsCallFunction 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsCallFunction
helpviewer_keywords:
- JsCallFunction function
ms.assetid: 8a1dca72-d720-4a28-a86e-6809465006fe
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: f242ccef71d8a2b361dbe2d1a299728f5551f5d3
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563195"
---
# <span data-ttu-id="8fcdd-103">JsCallFunction 函数</span><span class="sxs-lookup"><span data-stu-id="8fcdd-103">JsCallFunction Function</span></span>
<span data-ttu-id="8fcdd-104">调用函数。</span><span class="sxs-lookup"><span data-stu-id="8fcdd-104">Invokes a function.</span></span>  
  
## <span data-ttu-id="8fcdd-105">语法</span><span class="sxs-lookup"><span data-stu-id="8fcdd-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsCallFunction(  
   _In_ JsValueRef function,  
   _In_reads_(argumentCount) JsValueRef *arguments,  
   _In_ unsigned short argumentCount,  
   _Out_opt_ JsValueRef *result  
);  
```  
  
#### <span data-ttu-id="8fcdd-106">参数</span><span class="sxs-lookup"><span data-stu-id="8fcdd-106">Parameters</span></span>  
 `function`  
 <span data-ttu-id="8fcdd-107">要调用的函数。</span><span class="sxs-lookup"><span data-stu-id="8fcdd-107">The function to invoke.</span></span>  
  
 `arguments`  
 <span data-ttu-id="8fcdd-108">调用的参数。</span><span class="sxs-lookup"><span data-stu-id="8fcdd-108">The arguments to the call.</span></span>  
  
 `argumentCount`  
 <span data-ttu-id="8fcdd-109">传递到函数的参数的数量。</span><span class="sxs-lookup"><span data-stu-id="8fcdd-109">The number of arguments being passed in to the function.</span></span>  
  
 `result`  
 <span data-ttu-id="8fcdd-110">从函数调用中返回的值（如果有）。</span><span class="sxs-lookup"><span data-stu-id="8fcdd-110">The value returned from the function invocation, if any.</span></span>  
  
## <span data-ttu-id="8fcdd-111">返回值</span><span class="sxs-lookup"><span data-stu-id="8fcdd-111">Return Value</span></span>  
 <span data-ttu-id="8fcdd-112">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="8fcdd-112">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="8fcdd-113">备注</span><span class="sxs-lookup"><span data-stu-id="8fcdd-113">Remarks</span></span>  
 <span data-ttu-id="8fcdd-114">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="8fcdd-114">Requires an active script context.</span></span>  
  
## <span data-ttu-id="8fcdd-115">要求</span><span class="sxs-lookup"><span data-stu-id="8fcdd-115">Requirements</span></span>  
 <span data-ttu-id="8fcdd-116">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="8fcdd-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="8fcdd-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8fcdd-117">See Also</span></span>  
 [<span data-ttu-id="8fcdd-118">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="8fcdd-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)