---
description: 确定对象是否具有属性。
title: JsHasProperty 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsHasProperty
helpviewer_keywords:
- JsHasProperty function
ms.assetid: 26c94c3d-aae6-4257-8644-df63c7e714fb
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: e45ecfaafb06c49a6a3773eb798ee93a19fd6d6e
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232409"
---
# <span data-ttu-id="314c3-103">JsHasProperty 函数</span><span class="sxs-lookup"><span data-stu-id="314c3-103">JsHasProperty Function</span></span>

<span data-ttu-id="314c3-104">确定对象是否具有属性。</span><span class="sxs-lookup"><span data-stu-id="314c3-104">Determines whether an object has a property.</span></span>  
  
## <span data-ttu-id="314c3-105">语法</span><span class="sxs-lookup"><span data-stu-id="314c3-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsHasProperty(  
   _In_ JsValueRef object,  
   _In_ JsPropertyIdRef propertyId,  
   _Out_ bool *hasProperty  
);  
```  
  
#### <span data-ttu-id="314c3-106">参数</span><span class="sxs-lookup"><span data-stu-id="314c3-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="314c3-107">可能包含该属性的对象。</span><span class="sxs-lookup"><span data-stu-id="314c3-107">The object that may contain the property.</span></span>  
  
 `propertyId`  
 <span data-ttu-id="314c3-108">属性的 ID。</span><span class="sxs-lookup"><span data-stu-id="314c3-108">The ID of the property.</span></span>  
  
 `hasProperty`  
 <span data-ttu-id="314c3-109">对象是 (还是原型) 属性。</span><span class="sxs-lookup"><span data-stu-id="314c3-109">Whether the object (or a prototype) has the property.</span></span>  
  
## <span data-ttu-id="314c3-110">返回值</span><span class="sxs-lookup"><span data-stu-id="314c3-110">Return Value</span></span>  
 <span data-ttu-id="314c3-111">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="314c3-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="314c3-112">备注</span><span class="sxs-lookup"><span data-stu-id="314c3-112">Remarks</span></span>  
 <span data-ttu-id="314c3-113">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="314c3-113">Requires an active script context.</span></span>  
  
## <span data-ttu-id="314c3-114">要求</span><span class="sxs-lookup"><span data-stu-id="314c3-114">Requirements</span></span>  
 <span data-ttu-id="314c3-115">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="314c3-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="314c3-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="314c3-116">See Also</span></span>  
 [<span data-ttu-id="314c3-117">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="314c3-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
