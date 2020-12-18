---
description: 获取与名称关联的属性 ID。
title: JsGetPropertyIdFromName 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsGetPropertyIdFromName
helpviewer_keywords:
- JsGetPropertyIdFromName function
ms.assetid: 1674906f-746a-4c62-99cd-023276683a86
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: adc8de4d55fa0c74ad191b4621ceb3a54026d02d
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232550"
---
# <span data-ttu-id="89920-103">JsGetPropertyIdFromName 函数</span><span class="sxs-lookup"><span data-stu-id="89920-103">JsGetPropertyIdFromName Function</span></span>

<span data-ttu-id="89920-104">获取与名称关联的属性 ID。</span><span class="sxs-lookup"><span data-stu-id="89920-104">Gets the property ID associated with the name.</span></span>  
  
## <span data-ttu-id="89920-105">语法</span><span class="sxs-lookup"><span data-stu-id="89920-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetPropertyIdFromName(  
   _In_z_ const wchar_t *name,  
   _Out_ JsPropertyIdRef *propertyId  
);  
```  
  
#### <span data-ttu-id="89920-106">参数</span><span class="sxs-lookup"><span data-stu-id="89920-106">Parameters</span></span>  
 `name`  
 <span data-ttu-id="89920-107">要获取或创建的属性 ID 的名称。</span><span class="sxs-lookup"><span data-stu-id="89920-107">The name of the property ID to get or create.</span></span> <span data-ttu-id="89920-108">该名称可能只包含数字。</span><span class="sxs-lookup"><span data-stu-id="89920-108">The name may consist of only digits.</span></span>  
  
 `propertyId`  
 <span data-ttu-id="89920-109">此运行时中给定名称的属性 ID。</span><span class="sxs-lookup"><span data-stu-id="89920-109">The property ID in this runtime for the given name.</span></span>  
  
## <span data-ttu-id="89920-110">返回值</span><span class="sxs-lookup"><span data-stu-id="89920-110">Return Value</span></span>  
 <span data-ttu-id="89920-111">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="89920-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="89920-112">备注</span><span class="sxs-lookup"><span data-stu-id="89920-112">Remarks</span></span>  
 <span data-ttu-id="89920-113">属性 ID 特定于上下文，不能跨上下文使用。</span><span class="sxs-lookup"><span data-stu-id="89920-113">Property IDs are specific to a context and cannot be used across contexts.</span></span>  
  
 <span data-ttu-id="89920-114">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="89920-114">Requires an active script context.</span></span>  
  
## <span data-ttu-id="89920-115">要求</span><span class="sxs-lookup"><span data-stu-id="89920-115">Requirements</span></span>  
 <span data-ttu-id="89920-116">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="89920-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="89920-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="89920-117">See Also</span></span>  
 [<span data-ttu-id="89920-118">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="89920-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
