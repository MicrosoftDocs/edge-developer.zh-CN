---
description: 获取对象的属性。
title: JsGetProperty 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsGetProperty
helpviewer_keywords:
- JsGetProperty function
ms.assetid: 606bc14f-e849-4f88-a148-6660e923c07b
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: e5731fa3f889fc1b182f88e37ae90c96d3825402
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232004"
---
# <span data-ttu-id="bf10c-103">JsGetProperty 函数</span><span class="sxs-lookup"><span data-stu-id="bf10c-103">JsGetProperty Function</span></span>

<span data-ttu-id="bf10c-104">获取对象的属性。</span><span class="sxs-lookup"><span data-stu-id="bf10c-104">Gets an object's property.</span></span>  
  
## <span data-ttu-id="bf10c-105">语法</span><span class="sxs-lookup"><span data-stu-id="bf10c-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetProperty(  
   _In_ JsValueRef object,  
   _In_ JsPropertyIdRef propertyId,  
   _Out_ JsValueRef *value  
);  
```  
  
#### <span data-ttu-id="bf10c-106">参数</span><span class="sxs-lookup"><span data-stu-id="bf10c-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="bf10c-107">包含该属性的对象。</span><span class="sxs-lookup"><span data-stu-id="bf10c-107">The object that contains the property.</span></span>  
  
 `propertyId`  
 <span data-ttu-id="bf10c-108">属性的 ID。</span><span class="sxs-lookup"><span data-stu-id="bf10c-108">The ID of the property.</span></span>  
  
 `value`  
 <span data-ttu-id="bf10c-109">属性的值。</span><span class="sxs-lookup"><span data-stu-id="bf10c-109">The value of the property.</span></span>  
  
## <span data-ttu-id="bf10c-110">返回值</span><span class="sxs-lookup"><span data-stu-id="bf10c-110">Return Value</span></span>  
 <span data-ttu-id="bf10c-111">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="bf10c-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="bf10c-112">备注</span><span class="sxs-lookup"><span data-stu-id="bf10c-112">Remarks</span></span>  
 <span data-ttu-id="bf10c-113">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="bf10c-113">Requires an active script context.</span></span>  
  
## <span data-ttu-id="bf10c-114">要求</span><span class="sxs-lookup"><span data-stu-id="bf10c-114">Requirements</span></span>  
 <span data-ttu-id="bf10c-115">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="bf10c-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="bf10c-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bf10c-116">See Also</span></span>  
 [<span data-ttu-id="bf10c-117">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="bf10c-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
