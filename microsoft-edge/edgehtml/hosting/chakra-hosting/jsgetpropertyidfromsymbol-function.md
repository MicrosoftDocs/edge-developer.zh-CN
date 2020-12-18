---
description: 获取与符号关联的属性 ID。
title: JsGetPropertyIdFromSymbol 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 190fe4b9-352e-4b10-9d0e-6c6bbd6363e8
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: d97f1fb517164d692cdd010f899dc40d2e3596ed
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232584"
---
# <span data-ttu-id="356cf-103">JsGetPropertyIdFromSymbol 函数</span><span class="sxs-lookup"><span data-stu-id="356cf-103">JsGetPropertyIdFromSymbol Function</span></span>

<span data-ttu-id="356cf-104">获取与符号关联的属性 ID。</span><span class="sxs-lookup"><span data-stu-id="356cf-104">Gets the property ID associated with the symbol.</span></span>  
  
## <span data-ttu-id="356cf-105">语法</span><span class="sxs-lookup"><span data-stu-id="356cf-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetPropertyIdFromSymbol(  
   _In_ JsValueRef symbol,  
   _Out_ JsPropertyIdRef *propertyId  
);  
```  
  
#### <span data-ttu-id="356cf-106">参数</span><span class="sxs-lookup"><span data-stu-id="356cf-106">Parameters</span></span>  
 `symbol`  
 <span data-ttu-id="356cf-107">检索其属性 ID 的符号。</span><span class="sxs-lookup"><span data-stu-id="356cf-107">The symbol whose property ID is being retrieved.</span></span>  
  
 `propertyId`  
 <span data-ttu-id="356cf-108">给定符号的属性 ID。</span><span class="sxs-lookup"><span data-stu-id="356cf-108">The property ID for the given symbol.</span></span>  
  
## <span data-ttu-id="356cf-109">返回值</span><span class="sxs-lookup"><span data-stu-id="356cf-109">Return Value</span></span>  
 <span data-ttu-id="356cf-110">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="356cf-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="356cf-111">备注</span><span class="sxs-lookup"><span data-stu-id="356cf-111">Remarks</span></span>  
 <span data-ttu-id="356cf-112">属性 ID 特定于上下文，不能跨上下文使用。</span><span class="sxs-lookup"><span data-stu-id="356cf-112">Property IDs are specific to a context and cannot be used across contexts.</span></span>  
  
 <span data-ttu-id="356cf-113">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="356cf-113">Requires an active script context.</span></span>  
  
 <span data-ttu-id="356cf-114">此 API 仅在 Microsoft Edge 模式下受支持。</span><span class="sxs-lookup"><span data-stu-id="356cf-114">This API is supported only in Microsoft Edge mode.</span></span>  
  
## <span data-ttu-id="356cf-115">要求</span><span class="sxs-lookup"><span data-stu-id="356cf-115">Requirements</span></span>  
 <span data-ttu-id="356cf-116">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="356cf-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="356cf-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="356cf-117">See Also</span></span>  
 [<span data-ttu-id="356cf-118">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="356cf-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
