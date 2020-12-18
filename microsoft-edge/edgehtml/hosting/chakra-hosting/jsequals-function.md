---
description: 比较两个相等的 JavaScript 值。
title: JsEquals 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsEquals
helpviewer_keywords:
- JsEquals function
ms.assetid: 8377a7b6-12ff-43e4-8cc8-5a5a198a168b
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 88f906419e73ed0de6ddde0a872becbd18908997
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232774"
---
# <span data-ttu-id="0c00c-103">JsEquals 函数</span><span class="sxs-lookup"><span data-stu-id="0c00c-103">JsEquals Function</span></span>

<span data-ttu-id="0c00c-104">比较两个相等的 JavaScript 值。</span><span class="sxs-lookup"><span data-stu-id="0c00c-104">Compare two JavaScript values for equality.</span></span>  
  
## <span data-ttu-id="0c00c-105">语法</span><span class="sxs-lookup"><span data-stu-id="0c00c-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsEquals(  
   _In_ JsValueRef object1,  
   _In_ JsValueRef object2,  
   _Out_ bool *result  
);  
```  
  
#### <span data-ttu-id="0c00c-106">参数</span><span class="sxs-lookup"><span data-stu-id="0c00c-106">Parameters</span></span>  
 `object1`  
 <span data-ttu-id="0c00c-107">要比较的第一个对象。</span><span class="sxs-lookup"><span data-stu-id="0c00c-107">The first object to compare.</span></span>  
  
 `object2`  
 <span data-ttu-id="0c00c-108">要比较的第二个对象。</span><span class="sxs-lookup"><span data-stu-id="0c00c-108">The second object to compare.</span></span>  
  
 `result`  
 <span data-ttu-id="0c00c-109">值是否相等。</span><span class="sxs-lookup"><span data-stu-id="0c00c-109">Whether the values are equal.</span></span>  
  
## <span data-ttu-id="0c00c-110">返回值</span><span class="sxs-lookup"><span data-stu-id="0c00c-110">Return Value</span></span>  
 <span data-ttu-id="0c00c-111">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="0c00c-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="0c00c-112">备注</span><span class="sxs-lookup"><span data-stu-id="0c00c-112">Remarks</span></span>  
 <span data-ttu-id="0c00c-113">此函数等效于 `==` Javascript 中的运算符。</span><span class="sxs-lookup"><span data-stu-id="0c00c-113">This function is equivalent to the `==` operator in Javascript.</span></span>  
  
 <span data-ttu-id="0c00c-114">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="0c00c-114">Requires an active script context.</span></span>  
  
## <span data-ttu-id="0c00c-115">要求</span><span class="sxs-lookup"><span data-stu-id="0c00c-115">Requirements</span></span>  
 <span data-ttu-id="0c00c-116">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="0c00c-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="0c00c-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0c00c-117">See Also</span></span>  
 [<span data-ttu-id="0c00c-118">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="0c00c-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
