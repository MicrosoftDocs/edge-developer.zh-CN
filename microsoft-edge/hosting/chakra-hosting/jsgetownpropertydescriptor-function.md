---
description: 获取对象自己的属性的属性描述符。
title: JsGetOwnPropertyDescriptor 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsGetOwnPropertyDescriptor
helpviewer_keywords:
- JsGetOwnPropertyDescriptor function
ms.assetid: 44c417ce-ab63-44eb-a0ab-19838e3ab34f
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 6f500aec8b892cb2ad437bd7159ab14165a8bfb4
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564256"
---
# <span data-ttu-id="e5e9c-103">JsGetOwnPropertyDescriptor 函数</span><span class="sxs-lookup"><span data-stu-id="e5e9c-103">JsGetOwnPropertyDescriptor Function</span></span>
<span data-ttu-id="e5e9c-104">获取对象自己的属性的属性描述符。</span><span class="sxs-lookup"><span data-stu-id="e5e9c-104">Gets a property descriptor for an object's own property.</span></span>  
  
## <span data-ttu-id="e5e9c-105">语法</span><span class="sxs-lookup"><span data-stu-id="e5e9c-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetOwnPropertyDescriptor(  
   _In_ JsValueRef object,  
   _In_ JsPropertyIdRef propertyId,  
   _Out_ JsValueRef *propertyDescriptor  
);  
```  
  
#### <span data-ttu-id="e5e9c-106">参数</span><span class="sxs-lookup"><span data-stu-id="e5e9c-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="e5e9c-107">具有属性的对象。</span><span class="sxs-lookup"><span data-stu-id="e5e9c-107">The object that has the property.</span></span>  
  
 `propertyId`  
 <span data-ttu-id="e5e9c-108">属性的 ID。</span><span class="sxs-lookup"><span data-stu-id="e5e9c-108">The ID of the property.</span></span>  
  
 `propertyDescriptor`  
 <span data-ttu-id="e5e9c-109">属性描述符。</span><span class="sxs-lookup"><span data-stu-id="e5e9c-109">The property descriptor.</span></span>  
  
## <span data-ttu-id="e5e9c-110">返回值</span><span class="sxs-lookup"><span data-stu-id="e5e9c-110">Return Value</span></span>  
 <span data-ttu-id="e5e9c-111">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="e5e9c-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="e5e9c-112">备注</span><span class="sxs-lookup"><span data-stu-id="e5e9c-112">Remarks</span></span>  
 <span data-ttu-id="e5e9c-113">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="e5e9c-113">Requires an active script context.</span></span>  
  
## <span data-ttu-id="e5e9c-114">要求</span><span class="sxs-lookup"><span data-stu-id="e5e9c-114">Requirements</span></span>  
 <span data-ttu-id="e5e9c-115">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="e5e9c-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="e5e9c-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e5e9c-116">See Also</span></span>  
 [<span data-ttu-id="e5e9c-117">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="e5e9c-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)