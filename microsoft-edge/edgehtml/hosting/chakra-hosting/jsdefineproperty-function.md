---
description: 通过属性描述符定义新对象自己的属性。
title: JsDefineProperty 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsDefineProperty
helpviewer_keywords:
- JsDefineProperty function
ms.assetid: b2cf48d6-eb40-457c-aa8b-b16a50dc5d6a
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: a35dd6214190fa558c50cbb743b0f2b92b5e00b3
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232548"
---
# <span data-ttu-id="ab791-103">JsDefineProperty 函数</span><span class="sxs-lookup"><span data-stu-id="ab791-103">JsDefineProperty Function</span></span>

<span data-ttu-id="ab791-104">通过属性描述符定义新对象自己的属性。</span><span class="sxs-lookup"><span data-stu-id="ab791-104">Defines a new object's own property from a property descriptor.</span></span>  
  
## <span data-ttu-id="ab791-105">语法</span><span class="sxs-lookup"><span data-stu-id="ab791-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsDefineProperty(  
   _In_ JsValueRef object,  
   _In_ JsPropertyIdRef propertyId,  
   _In_ JsValueRef propertyDescriptor,  
   _Out_ bool *result  
);  
```  
  
#### <span data-ttu-id="ab791-106">参数</span><span class="sxs-lookup"><span data-stu-id="ab791-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="ab791-107">具有该属性的对象。</span><span class="sxs-lookup"><span data-stu-id="ab791-107">The object that has the property.</span></span>  
  
 `propertyId`  
 <span data-ttu-id="ab791-108">属性的 ID。</span><span class="sxs-lookup"><span data-stu-id="ab791-108">The ID of the property.</span></span>  
  
 `propertyDescriptor`  
 <span data-ttu-id="ab791-109">属性描述符。</span><span class="sxs-lookup"><span data-stu-id="ab791-109">The property descriptor.</span></span>  
  
 `result`  
 <span data-ttu-id="ab791-110">属性是否已定义。</span><span class="sxs-lookup"><span data-stu-id="ab791-110">Whether the property was defined.</span></span>  
  
## <span data-ttu-id="ab791-111">返回值</span><span class="sxs-lookup"><span data-stu-id="ab791-111">Return Value</span></span>  
 <span data-ttu-id="ab791-112">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="ab791-112">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="ab791-113">备注</span><span class="sxs-lookup"><span data-stu-id="ab791-113">Remarks</span></span>  
 <span data-ttu-id="ab791-114">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="ab791-114">Requires an active script context.</span></span>  
  
## <span data-ttu-id="ab791-115">要求</span><span class="sxs-lookup"><span data-stu-id="ab791-115">Requirements</span></span>  
 <span data-ttu-id="ab791-116">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="ab791-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="ab791-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ab791-117">See Also</span></span>  
 [<span data-ttu-id="ab791-118">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="ab791-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
