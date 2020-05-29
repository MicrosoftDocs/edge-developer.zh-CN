---
description: 将函数作为构造函数调用。
title: JsConstructObject 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsConstructObject
helpviewer_keywords:
- JsConstructObject function
ms.assetid: b07d2440-db55-4a6a-8376-56b40a8039a1
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 6fb9654b5c7321d6c6b0b255ec897fb30a114041
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563190"
---
# <span data-ttu-id="21f9a-103">JsConstructObject 函数</span><span class="sxs-lookup"><span data-stu-id="21f9a-103">JsConstructObject Function</span></span>
<span data-ttu-id="21f9a-104">将函数作为构造函数调用。</span><span class="sxs-lookup"><span data-stu-id="21f9a-104">Invokes a function as a constructor.</span></span>  
  
## <span data-ttu-id="21f9a-105">语法</span><span class="sxs-lookup"><span data-stu-id="21f9a-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsConstructObject(  
   _In_ JsValueRef function,  
   _In_reads_(argumentCount) JsValueRef *arguments,  
   _In_ unsigned short argumentCount,  
   _Out_opt_ JsValueRef *result  
);  
```  
  
#### <span data-ttu-id="21f9a-106">参数</span><span class="sxs-lookup"><span data-stu-id="21f9a-106">Parameters</span></span>  
 `function`  
 <span data-ttu-id="21f9a-107">要作为构造函数调用的函数。</span><span class="sxs-lookup"><span data-stu-id="21f9a-107">The function to invoke as a constructor.</span></span>  
  
 `arguments`  
 <span data-ttu-id="21f9a-108">调用的参数。</span><span class="sxs-lookup"><span data-stu-id="21f9a-108">The arguments to the call.</span></span>  
  
 `argumentCount`  
 <span data-ttu-id="21f9a-109">传递到函数的参数的数量。</span><span class="sxs-lookup"><span data-stu-id="21f9a-109">The number of arguments being passed in to the function.</span></span>  
  
 `result`  
 <span data-ttu-id="21f9a-110">从函数调用返回的值。</span><span class="sxs-lookup"><span data-stu-id="21f9a-110">The value returned from the function invocation.</span></span>  
  
## <span data-ttu-id="21f9a-111">返回值</span><span class="sxs-lookup"><span data-stu-id="21f9a-111">Return Value</span></span>  
 <span data-ttu-id="21f9a-112">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="21f9a-112">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="21f9a-113">备注</span><span class="sxs-lookup"><span data-stu-id="21f9a-113">Remarks</span></span>  
 <span data-ttu-id="21f9a-114">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="21f9a-114">Requires an active script context.</span></span>  
  
## <span data-ttu-id="21f9a-115">要求</span><span class="sxs-lookup"><span data-stu-id="21f9a-115">Requirements</span></span>  
 <span data-ttu-id="21f9a-116">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="21f9a-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="21f9a-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="21f9a-117">See Also</span></span>  
 [<span data-ttu-id="21f9a-118">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="21f9a-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)