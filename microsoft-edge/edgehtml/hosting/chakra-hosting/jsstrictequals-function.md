---
description: 比较两个 JavaScript 值以严格相等。
title: JsStrictEquals 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsStrictEquals
helpviewer_keywords:
- JsStrictEquals function
ms.assetid: b35bc655-7ff8-496a-b678-8950bb976047
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 98af1629129986cc21cafe5660d3155e031919dc
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232357"
---
# <span data-ttu-id="b1753-103">JsStrictEquals 函数</span><span class="sxs-lookup"><span data-stu-id="b1753-103">JsStrictEquals Function</span></span>

<span data-ttu-id="b1753-104">比较两个 JavaScript 值以严格相等。</span><span class="sxs-lookup"><span data-stu-id="b1753-104">Compare two JavaScript values for strict equality.</span></span>  
  
## <span data-ttu-id="b1753-105">语法</span><span class="sxs-lookup"><span data-stu-id="b1753-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsStrictEquals(  
   _In_ JsValueRef object1,  
   _In_ JsValueRef object2,  
   _Out_ bool *result  
);  
```  
  
#### <span data-ttu-id="b1753-106">参数</span><span class="sxs-lookup"><span data-stu-id="b1753-106">Parameters</span></span>  
 `object1`  
 <span data-ttu-id="b1753-107">要比较的第一个对象。</span><span class="sxs-lookup"><span data-stu-id="b1753-107">The first object to compare.</span></span>  
  
 `object2`  
 <span data-ttu-id="b1753-108">要比较的第二个对象。</span><span class="sxs-lookup"><span data-stu-id="b1753-108">The second object to compare.</span></span>  
  
 `result`  
 <span data-ttu-id="b1753-109">值是否严格相等。</span><span class="sxs-lookup"><span data-stu-id="b1753-109">Whether the values are strictly equal.</span></span>  
  
## <span data-ttu-id="b1753-110">返回值</span><span class="sxs-lookup"><span data-stu-id="b1753-110">Return Value</span></span>  
 <span data-ttu-id="b1753-111">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="b1753-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="b1753-112">备注</span><span class="sxs-lookup"><span data-stu-id="b1753-112">Remarks</span></span>  
 <span data-ttu-id="b1753-113">此函数等效于 `===` Javascript 中的运算符。</span><span class="sxs-lookup"><span data-stu-id="b1753-113">This function is equivalent to the `===` operator in Javascript.</span></span>  
  
 <span data-ttu-id="b1753-114">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="b1753-114">Requires an active script context.</span></span>  
  
## <span data-ttu-id="b1753-115">要求</span><span class="sxs-lookup"><span data-stu-id="b1753-115">Requirements</span></span>  
 <span data-ttu-id="b1753-116">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="b1753-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="b1753-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b1753-117">See Also</span></span>  
 [<span data-ttu-id="b1753-118">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="b1753-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
