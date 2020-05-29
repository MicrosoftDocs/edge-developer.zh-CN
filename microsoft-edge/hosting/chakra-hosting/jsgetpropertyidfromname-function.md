---
description: 获取与名称关联的属性 ID。
title: JsGetPropertyIdFromName 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsGetPropertyIdFromName
helpviewer_keywords:
- JsGetPropertyIdFromName function
ms.assetid: 1674906f-746a-4c62-99cd-023276683a86
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: e1954b86937056523a30c15dbf350ac02fd63dde
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564245"
---
# <span data-ttu-id="b89cd-103">JsGetPropertyIdFromName 函数</span><span class="sxs-lookup"><span data-stu-id="b89cd-103">JsGetPropertyIdFromName Function</span></span>
<span data-ttu-id="b89cd-104">获取与名称关联的属性 ID。</span><span class="sxs-lookup"><span data-stu-id="b89cd-104">Gets the property ID associated with the name.</span></span>  
  
## <span data-ttu-id="b89cd-105">语法</span><span class="sxs-lookup"><span data-stu-id="b89cd-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetPropertyIdFromName(  
   _In_z_ const wchar_t *name,  
   _Out_ JsPropertyIdRef *propertyId  
);  
```  
  
#### <span data-ttu-id="b89cd-106">参数</span><span class="sxs-lookup"><span data-stu-id="b89cd-106">Parameters</span></span>  
 `name`  
 <span data-ttu-id="b89cd-107">要获取或创建的属性 ID 的名称。</span><span class="sxs-lookup"><span data-stu-id="b89cd-107">The name of the property ID to get or create.</span></span> <span data-ttu-id="b89cd-108">该名称只能包含数字。</span><span class="sxs-lookup"><span data-stu-id="b89cd-108">The name may consist of only digits.</span></span>  
  
 `propertyId`  
 <span data-ttu-id="b89cd-109">此运行时中给定名称的属性 ID。</span><span class="sxs-lookup"><span data-stu-id="b89cd-109">The property ID in this runtime for the given name.</span></span>  
  
## <span data-ttu-id="b89cd-110">返回值</span><span class="sxs-lookup"><span data-stu-id="b89cd-110">Return Value</span></span>  
 <span data-ttu-id="b89cd-111">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="b89cd-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="b89cd-112">备注</span><span class="sxs-lookup"><span data-stu-id="b89cd-112">Remarks</span></span>  
 <span data-ttu-id="b89cd-113">属性 Id 特定于上下文，不能跨上下文使用。</span><span class="sxs-lookup"><span data-stu-id="b89cd-113">Property IDs are specific to a context and cannot be used across contexts.</span></span>  
  
 <span data-ttu-id="b89cd-114">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="b89cd-114">Requires an active script context.</span></span>  
  
## <span data-ttu-id="b89cd-115">要求</span><span class="sxs-lookup"><span data-stu-id="b89cd-115">Requirements</span></span>  
 <span data-ttu-id="b89cd-116">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="b89cd-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="b89cd-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b89cd-117">See Also</span></span>  
 [<span data-ttu-id="b89cd-118">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="b89cd-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)