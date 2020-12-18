---
description: 测试对象是否具有指定索引的值。
title: JsHasIndexedProperty 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsHasIndexedProperty
helpviewer_keywords:
- JsHasIndexedProperty function
ms.assetid: 30436a3d-fda0-407e-aba2-142be2310372
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 9eb1794c465b4b116978a2150285e2fed3ae1d9b
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232411"
---
# <span data-ttu-id="15ed6-103">JsHasIndexedProperty 函数</span><span class="sxs-lookup"><span data-stu-id="15ed6-103">JsHasIndexedProperty Function</span></span>

<span data-ttu-id="15ed6-104">测试对象是否具有指定索引的值。</span><span class="sxs-lookup"><span data-stu-id="15ed6-104">Tests whether an object has a value at the specified index.</span></span>  
  
## <span data-ttu-id="15ed6-105">语法</span><span class="sxs-lookup"><span data-stu-id="15ed6-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsHasIndexedProperty(  
   _In_ JsValueRef object,  
   _In_ JsValueRef index,  
   _Out_ bool *result  
);  
```  
  
#### <span data-ttu-id="15ed6-106">参数</span><span class="sxs-lookup"><span data-stu-id="15ed6-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="15ed6-107">要操作的对象。</span><span class="sxs-lookup"><span data-stu-id="15ed6-107">The object to operate on.</span></span>  
  
 `index`  
 <span data-ttu-id="15ed6-108">要测试的索引。</span><span class="sxs-lookup"><span data-stu-id="15ed6-108">The index to test.</span></span>  
  
 `result`  
 <span data-ttu-id="15ed6-109">对象是否具有指定索引的值。</span><span class="sxs-lookup"><span data-stu-id="15ed6-109">Whether the object has an value at the specified index.</span></span>  
  
## <span data-ttu-id="15ed6-110">返回值</span><span class="sxs-lookup"><span data-stu-id="15ed6-110">Return Value</span></span>  
 <span data-ttu-id="15ed6-111">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="15ed6-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="15ed6-112">备注</span><span class="sxs-lookup"><span data-stu-id="15ed6-112">Remarks</span></span>  
 <span data-ttu-id="15ed6-113">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="15ed6-113">Requires an active script context.</span></span>  
  
## <span data-ttu-id="15ed6-114">要求</span><span class="sxs-lookup"><span data-stu-id="15ed6-114">Requirements</span></span>  
 <span data-ttu-id="15ed6-115">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="15ed6-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="15ed6-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="15ed6-116">See Also</span></span>  
 [<span data-ttu-id="15ed6-117">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="15ed6-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
