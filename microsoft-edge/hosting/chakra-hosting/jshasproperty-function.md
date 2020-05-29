---
description: 确定对象是否具有属性。
title: JsHasProperty 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsHasProperty
helpviewer_keywords:
- JsHasProperty function
ms.assetid: 26c94c3d-aae6-4257-8644-df63c7e714fb
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: c6cc195ae02c28500f0a018256d24278ad4b47d8
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564226"
---
# <span data-ttu-id="e038b-103">JsHasProperty 函数</span><span class="sxs-lookup"><span data-stu-id="e038b-103">JsHasProperty Function</span></span>
<span data-ttu-id="e038b-104">确定对象是否具有属性。</span><span class="sxs-lookup"><span data-stu-id="e038b-104">Determines whether an object has a property.</span></span>  
  
## <span data-ttu-id="e038b-105">语法</span><span class="sxs-lookup"><span data-stu-id="e038b-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsHasProperty(  
   _In_ JsValueRef object,  
   _In_ JsPropertyIdRef propertyId,  
   _Out_ bool *hasProperty  
);  
```  
  
#### <span data-ttu-id="e038b-106">参数</span><span class="sxs-lookup"><span data-stu-id="e038b-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="e038b-107">可能包含属性的对象。</span><span class="sxs-lookup"><span data-stu-id="e038b-107">The object that may contain the property.</span></span>  
  
 `propertyId`  
 <span data-ttu-id="e038b-108">属性的 ID。</span><span class="sxs-lookup"><span data-stu-id="e038b-108">The ID of the property.</span></span>  
  
 `hasProperty`  
 <span data-ttu-id="e038b-109">对象（或原型）是否具有属性。</span><span class="sxs-lookup"><span data-stu-id="e038b-109">Whether the object (or a prototype) has the property.</span></span>  
  
## <span data-ttu-id="e038b-110">返回值</span><span class="sxs-lookup"><span data-stu-id="e038b-110">Return Value</span></span>  
 <span data-ttu-id="e038b-111">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="e038b-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="e038b-112">备注</span><span class="sxs-lookup"><span data-stu-id="e038b-112">Remarks</span></span>  
 <span data-ttu-id="e038b-113">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="e038b-113">Requires an active script context.</span></span>  
  
## <span data-ttu-id="e038b-114">要求</span><span class="sxs-lookup"><span data-stu-id="e038b-114">Requirements</span></span>  
 <span data-ttu-id="e038b-115">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="e038b-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="e038b-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e038b-116">See Also</span></span>  
 [<span data-ttu-id="e038b-117">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="e038b-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)