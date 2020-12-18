---
description: 删除对象的属性。
title: JsDeleteProperty 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsDeleteProperty
helpviewer_keywords:
- JsDeleteProperty function
ms.assetid: 0f6ac6a7-3576-42f5-98d0-1c06542c8149
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 55089bd4cff7ef4d58bcce1d7531d4ca1c7381ae
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232031"
---
# <span data-ttu-id="9e79e-103">JsDeleteProperty 函数</span><span class="sxs-lookup"><span data-stu-id="9e79e-103">JsDeleteProperty Function</span></span>

<span data-ttu-id="9e79e-104">删除对象的属性。</span><span class="sxs-lookup"><span data-stu-id="9e79e-104">Deletes an object's property.</span></span>  
  
## <span data-ttu-id="9e79e-105">语法</span><span class="sxs-lookup"><span data-stu-id="9e79e-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsDeleteProperty(  
   _In_ JsValueRef object,  
   _In_ JsPropertyIdRef propertyId,  
   _In_ bool useStrictRules,  
   _Out_ JsValueRef *result  
);  
```  
  
#### <span data-ttu-id="9e79e-106">参数</span><span class="sxs-lookup"><span data-stu-id="9e79e-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="9e79e-107">包含该属性的对象。</span><span class="sxs-lookup"><span data-stu-id="9e79e-107">The object that contains the property.</span></span>  
  
 `propertyId`  
 <span data-ttu-id="9e79e-108">属性的 ID。</span><span class="sxs-lookup"><span data-stu-id="9e79e-108">The ID of the property.</span></span>  
  
 `useStrictRules`  
 <span data-ttu-id="9e79e-109">属性集应遵循严格的模式规则。</span><span class="sxs-lookup"><span data-stu-id="9e79e-109">The property set should follow strict mode rules.</span></span>  
  
 `result`  
 <span data-ttu-id="9e79e-110">属性是否已删除。</span><span class="sxs-lookup"><span data-stu-id="9e79e-110">Whether the property was deleted.</span></span>  
  
## <span data-ttu-id="9e79e-111">返回值</span><span class="sxs-lookup"><span data-stu-id="9e79e-111">Return Value</span></span>  
 <span data-ttu-id="9e79e-112">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="9e79e-112">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="9e79e-113">备注</span><span class="sxs-lookup"><span data-stu-id="9e79e-113">Remarks</span></span>  
 <span data-ttu-id="9e79e-114">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="9e79e-114">Requires an active script context.</span></span>  
  
## <span data-ttu-id="9e79e-115">要求</span><span class="sxs-lookup"><span data-stu-id="9e79e-115">Requirements</span></span>  
 <span data-ttu-id="9e79e-116">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="9e79e-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="9e79e-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9e79e-117">See Also</span></span>  
 [<span data-ttu-id="9e79e-118">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="9e79e-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
