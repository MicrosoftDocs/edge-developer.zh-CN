---
description: 将对象的属性放在一起。
title: JsSetProperty 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsSetProperty
helpviewer_keywords:
- JsSetProperty function
ms.assetid: 2c36bebf-ec86-425c-8131-2dd75fd30f40
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 29c3e04fc240bd63fc755c6727752d053b94484d
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232410"
---
# <span data-ttu-id="bb6c5-103">JsSetProperty 函数</span><span class="sxs-lookup"><span data-stu-id="bb6c5-103">JsSetProperty Function</span></span>

<span data-ttu-id="bb6c5-104">将对象的属性放在一起。</span><span class="sxs-lookup"><span data-stu-id="bb6c5-104">Puts an object's property.</span></span>  
  
## <span data-ttu-id="bb6c5-105">语法</span><span class="sxs-lookup"><span data-stu-id="bb6c5-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsSetProperty(  
   _In_ JsValueRef object,  
   _In_ JsPropertyIdRef propertyId,  
   _In_ JsValueRef value,  
   _In_ bool useStrictRules  
);  
```  
  
#### <span data-ttu-id="bb6c5-106">参数</span><span class="sxs-lookup"><span data-stu-id="bb6c5-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="bb6c5-107">包含该属性的对象。</span><span class="sxs-lookup"><span data-stu-id="bb6c5-107">The object that contains the property.</span></span>  
  
 `propertyId`  
 <span data-ttu-id="bb6c5-108">属性的 ID。</span><span class="sxs-lookup"><span data-stu-id="bb6c5-108">The ID of the property.</span></span>  
  
 `value`  
 <span data-ttu-id="bb6c5-109">属性的新值。</span><span class="sxs-lookup"><span data-stu-id="bb6c5-109">The new value of the property.</span></span>  
  
 `useStrictRules`  
 <span data-ttu-id="bb6c5-110">属性集应遵循严格的模式规则。</span><span class="sxs-lookup"><span data-stu-id="bb6c5-110">The property set should follow strict mode rules.</span></span>  
  
## <span data-ttu-id="bb6c5-111">返回值</span><span class="sxs-lookup"><span data-stu-id="bb6c5-111">Return Value</span></span>  
 <span data-ttu-id="bb6c5-112">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="bb6c5-112">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="bb6c5-113">备注</span><span class="sxs-lookup"><span data-stu-id="bb6c5-113">Remarks</span></span>  
 <span data-ttu-id="bb6c5-114">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="bb6c5-114">Requires an active script context.</span></span>  
  
## <span data-ttu-id="bb6c5-115">要求</span><span class="sxs-lookup"><span data-stu-id="bb6c5-115">Requirements</span></span>  
 <span data-ttu-id="bb6c5-116">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="bb6c5-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="bb6c5-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bb6c5-117">See Also</span></span>  
 [<span data-ttu-id="bb6c5-118">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="bb6c5-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
