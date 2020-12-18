---
description: 调用函数作为构造函数。
title: JsConstructObject 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsConstructObject
helpviewer_keywords:
- JsConstructObject function
ms.assetid: b07d2440-db55-4a6a-8376-56b40a8039a1
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 8dbb757456412e50efaf3a026d169e6b3612b6b1
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232213"
---
# <span data-ttu-id="9a36d-103">JsConstructObject 函数</span><span class="sxs-lookup"><span data-stu-id="9a36d-103">JsConstructObject Function</span></span>

<span data-ttu-id="9a36d-104">调用函数作为构造函数。</span><span class="sxs-lookup"><span data-stu-id="9a36d-104">Invokes a function as a constructor.</span></span>  
  
## <span data-ttu-id="9a36d-105">语法</span><span class="sxs-lookup"><span data-stu-id="9a36d-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsConstructObject(  
   _In_ JsValueRef function,  
   _In_reads_(argumentCount) JsValueRef *arguments,  
   _In_ unsigned short argumentCount,  
   _Out_opt_ JsValueRef *result  
);  
```  
  
#### <span data-ttu-id="9a36d-106">参数</span><span class="sxs-lookup"><span data-stu-id="9a36d-106">Parameters</span></span>  
 `function`  
 <span data-ttu-id="9a36d-107">要调用为构造函数的函数。</span><span class="sxs-lookup"><span data-stu-id="9a36d-107">The function to invoke as a constructor.</span></span>  
  
 `arguments`  
 <span data-ttu-id="9a36d-108">调用的参数。</span><span class="sxs-lookup"><span data-stu-id="9a36d-108">The arguments to the call.</span></span>  
  
 `argumentCount`  
 <span data-ttu-id="9a36d-109">传递给函数的参数数。</span><span class="sxs-lookup"><span data-stu-id="9a36d-109">The number of arguments being passed in to the function.</span></span>  
  
 `result`  
 <span data-ttu-id="9a36d-110">函数调用返回的值。</span><span class="sxs-lookup"><span data-stu-id="9a36d-110">The value returned from the function invocation.</span></span>  
  
## <span data-ttu-id="9a36d-111">返回值</span><span class="sxs-lookup"><span data-stu-id="9a36d-111">Return Value</span></span>  
 <span data-ttu-id="9a36d-112">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="9a36d-112">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="9a36d-113">备注</span><span class="sxs-lookup"><span data-stu-id="9a36d-113">Remarks</span></span>  
 <span data-ttu-id="9a36d-114">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="9a36d-114">Requires an active script context.</span></span>  
  
## <span data-ttu-id="9a36d-115">要求</span><span class="sxs-lookup"><span data-stu-id="9a36d-115">Requirements</span></span>  
 <span data-ttu-id="9a36d-116">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="9a36d-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="9a36d-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9a36d-117">See Also</span></span>  
 [<span data-ttu-id="9a36d-118">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="9a36d-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
