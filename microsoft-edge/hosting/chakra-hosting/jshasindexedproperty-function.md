---
description: 测试对象在指定索引处是否具有值。
title: JsHasIndexedProperty 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsHasIndexedProperty
helpviewer_keywords:
- JsHasIndexedProperty function
ms.assetid: 30436a3d-fda0-407e-aba2-142be2310372
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 85d9fa12c44bd1d961ec2a7ba494484873635586
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564227"
---
# <span data-ttu-id="ef8cd-103">JsHasIndexedProperty 函数</span><span class="sxs-lookup"><span data-stu-id="ef8cd-103">JsHasIndexedProperty Function</span></span>
<span data-ttu-id="ef8cd-104">测试对象在指定索引处是否具有值。</span><span class="sxs-lookup"><span data-stu-id="ef8cd-104">Tests whether an object has a value at the specified index.</span></span>  
  
## <span data-ttu-id="ef8cd-105">语法</span><span class="sxs-lookup"><span data-stu-id="ef8cd-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsHasIndexedProperty(  
   _In_ JsValueRef object,  
   _In_ JsValueRef index,  
   _Out_ bool *result  
);  
```  
  
#### <span data-ttu-id="ef8cd-106">参数</span><span class="sxs-lookup"><span data-stu-id="ef8cd-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="ef8cd-107">要操作的对象。</span><span class="sxs-lookup"><span data-stu-id="ef8cd-107">The object to operate on.</span></span>  
  
 `index`  
 <span data-ttu-id="ef8cd-108">要测试的索引。</span><span class="sxs-lookup"><span data-stu-id="ef8cd-108">The index to test.</span></span>  
  
 `result`  
 <span data-ttu-id="ef8cd-109">对象在指定索引处是否具有值。</span><span class="sxs-lookup"><span data-stu-id="ef8cd-109">Whether the object has an value at the specified index.</span></span>  
  
## <span data-ttu-id="ef8cd-110">返回值</span><span class="sxs-lookup"><span data-stu-id="ef8cd-110">Return Value</span></span>  
 <span data-ttu-id="ef8cd-111">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="ef8cd-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="ef8cd-112">备注</span><span class="sxs-lookup"><span data-stu-id="ef8cd-112">Remarks</span></span>  
 <span data-ttu-id="ef8cd-113">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="ef8cd-113">Requires an active script context.</span></span>  
  
## <span data-ttu-id="ef8cd-114">要求</span><span class="sxs-lookup"><span data-stu-id="ef8cd-114">Requirements</span></span>  
 <span data-ttu-id="ef8cd-115">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="ef8cd-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="ef8cd-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ef8cd-116">See Also</span></span>  
 [<span data-ttu-id="ef8cd-117">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="ef8cd-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)