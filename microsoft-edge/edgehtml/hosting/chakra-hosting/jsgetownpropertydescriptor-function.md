---
description: 获取对象自己的属性的属性描述符。
title: JsGetOwnPropertyDescriptor 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsGetOwnPropertyDescriptor
helpviewer_keywords:
- JsGetOwnPropertyDescriptor function
ms.assetid: 44c417ce-ab63-44eb-a0ab-19838e3ab34f
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 05c7a58fa12d7ca8013c512f40031963ebc8ac18
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232395"
---
# <span data-ttu-id="268fd-103">JsGetOwnPropertyDescriptor 函数</span><span class="sxs-lookup"><span data-stu-id="268fd-103">JsGetOwnPropertyDescriptor Function</span></span>

<span data-ttu-id="268fd-104">获取对象自己的属性的属性描述符。</span><span class="sxs-lookup"><span data-stu-id="268fd-104">Gets a property descriptor for an object's own property.</span></span>  
  
## <span data-ttu-id="268fd-105">语法</span><span class="sxs-lookup"><span data-stu-id="268fd-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetOwnPropertyDescriptor(  
   _In_ JsValueRef object,  
   _In_ JsPropertyIdRef propertyId,  
   _Out_ JsValueRef *propertyDescriptor  
);  
```  
  
#### <span data-ttu-id="268fd-106">参数</span><span class="sxs-lookup"><span data-stu-id="268fd-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="268fd-107">具有该属性的对象。</span><span class="sxs-lookup"><span data-stu-id="268fd-107">The object that has the property.</span></span>  
  
 `propertyId`  
 <span data-ttu-id="268fd-108">属性的 ID。</span><span class="sxs-lookup"><span data-stu-id="268fd-108">The ID of the property.</span></span>  
  
 `propertyDescriptor`  
 <span data-ttu-id="268fd-109">属性描述符。</span><span class="sxs-lookup"><span data-stu-id="268fd-109">The property descriptor.</span></span>  
  
## <span data-ttu-id="268fd-110">返回值</span><span class="sxs-lookup"><span data-stu-id="268fd-110">Return Value</span></span>  
 <span data-ttu-id="268fd-111">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="268fd-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="268fd-112">备注</span><span class="sxs-lookup"><span data-stu-id="268fd-112">Remarks</span></span>  
 <span data-ttu-id="268fd-113">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="268fd-113">Requires an active script context.</span></span>  
  
## <span data-ttu-id="268fd-114">要求</span><span class="sxs-lookup"><span data-stu-id="268fd-114">Requirements</span></span>  
 <span data-ttu-id="268fd-115">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="268fd-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="268fd-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="268fd-116">See Also</span></span>  
 [<span data-ttu-id="268fd-117">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="268fd-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
