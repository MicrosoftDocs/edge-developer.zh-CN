---
description: 比较两个 JavaScript 值是否相等。
title: JsEquals 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsEquals
helpviewer_keywords:
- JsEquals function
ms.assetid: 8377a7b6-12ff-43e4-8cc8-5a5a198a168b
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 84416584a048512ab20754a3b59eb8ec255901c4
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564267"
---
# <span data-ttu-id="e1780-103">JsEquals 函数</span><span class="sxs-lookup"><span data-stu-id="e1780-103">JsEquals Function</span></span>
<span data-ttu-id="e1780-104">比较两个 JavaScript 值是否相等。</span><span class="sxs-lookup"><span data-stu-id="e1780-104">Compare two JavaScript values for equality.</span></span>  
  
## <span data-ttu-id="e1780-105">语法</span><span class="sxs-lookup"><span data-stu-id="e1780-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsEquals(  
   _In_ JsValueRef object1,  
   _In_ JsValueRef object2,  
   _Out_ bool *result  
);  
```  
  
#### <span data-ttu-id="e1780-106">参数</span><span class="sxs-lookup"><span data-stu-id="e1780-106">Parameters</span></span>  
 `object1`  
 <span data-ttu-id="e1780-107">要比较的第一个对象。</span><span class="sxs-lookup"><span data-stu-id="e1780-107">The first object to compare.</span></span>  
  
 `object2`  
 <span data-ttu-id="e1780-108">要比较的第二个对象。</span><span class="sxs-lookup"><span data-stu-id="e1780-108">The second object to compare.</span></span>  
  
 `result`  
 <span data-ttu-id="e1780-109">值是否相等。</span><span class="sxs-lookup"><span data-stu-id="e1780-109">Whether the values are equal.</span></span>  
  
## <span data-ttu-id="e1780-110">返回值</span><span class="sxs-lookup"><span data-stu-id="e1780-110">Return Value</span></span>  
 <span data-ttu-id="e1780-111">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="e1780-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="e1780-112">备注</span><span class="sxs-lookup"><span data-stu-id="e1780-112">Remarks</span></span>  
 <span data-ttu-id="e1780-113">此函数等效于 `==` Javascript 中的运算符。</span><span class="sxs-lookup"><span data-stu-id="e1780-113">This function is equivalent to the `==` operator in Javascript.</span></span>  
  
 <span data-ttu-id="e1780-114">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="e1780-114">Requires an active script context.</span></span>  
  
## <span data-ttu-id="e1780-115">要求</span><span class="sxs-lookup"><span data-stu-id="e1780-115">Requirements</span></span>  
 <span data-ttu-id="e1780-116">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="e1780-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="e1780-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e1780-117">See Also</span></span>  
 [<span data-ttu-id="e1780-118">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="e1780-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)