---
description: 比较两个 JavaScript 值是否严格相等。
title: JsStrictEquals 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsStrictEquals
helpviewer_keywords:
- JsStrictEquals function
ms.assetid: b35bc655-7ff8-496a-b678-8950bb976047
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: b7f2b7a66c32428100f0c0d0f9db6150559ed7a2
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564166"
---
# <span data-ttu-id="9520c-103">JsStrictEquals 函数</span><span class="sxs-lookup"><span data-stu-id="9520c-103">JsStrictEquals Function</span></span>
<span data-ttu-id="9520c-104">比较两个 JavaScript 值是否严格相等。</span><span class="sxs-lookup"><span data-stu-id="9520c-104">Compare two JavaScript values for strict equality.</span></span>  
  
## <span data-ttu-id="9520c-105">语法</span><span class="sxs-lookup"><span data-stu-id="9520c-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsStrictEquals(  
   _In_ JsValueRef object1,  
   _In_ JsValueRef object2,  
   _Out_ bool *result  
);  
```  
  
#### <span data-ttu-id="9520c-106">参数</span><span class="sxs-lookup"><span data-stu-id="9520c-106">Parameters</span></span>  
 `object1`  
 <span data-ttu-id="9520c-107">要比较的第一个对象。</span><span class="sxs-lookup"><span data-stu-id="9520c-107">The first object to compare.</span></span>  
  
 `object2`  
 <span data-ttu-id="9520c-108">要比较的第二个对象。</span><span class="sxs-lookup"><span data-stu-id="9520c-108">The second object to compare.</span></span>  
  
 `result`  
 <span data-ttu-id="9520c-109">值是否严格相等。</span><span class="sxs-lookup"><span data-stu-id="9520c-109">Whether the values are strictly equal.</span></span>  
  
## <span data-ttu-id="9520c-110">返回值</span><span class="sxs-lookup"><span data-stu-id="9520c-110">Return Value</span></span>  
 <span data-ttu-id="9520c-111">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="9520c-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="9520c-112">备注</span><span class="sxs-lookup"><span data-stu-id="9520c-112">Remarks</span></span>  
 <span data-ttu-id="9520c-113">此函数等效于 `===` Javascript 中的运算符。</span><span class="sxs-lookup"><span data-stu-id="9520c-113">This function is equivalent to the `===` operator in Javascript.</span></span>  
  
 <span data-ttu-id="9520c-114">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="9520c-114">Requires an active script context.</span></span>  
  
## <span data-ttu-id="9520c-115">要求</span><span class="sxs-lookup"><span data-stu-id="9520c-115">Requirements</span></span>  
 <span data-ttu-id="9520c-116">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="9520c-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="9520c-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9520c-117">See Also</span></span>  
 [<span data-ttu-id="9520c-118">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="9520c-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)