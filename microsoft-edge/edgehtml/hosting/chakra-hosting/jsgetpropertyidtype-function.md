---
description: 获取属性的类型。
title: JsGetPropertyIdType 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 2b6e85ad-c630-4a07-a759-3b344d06faaa
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 93ee11bf74014361c89aa93bbb58361b426f573f
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232583"
---
# <span data-ttu-id="4124d-103">JsGetPropertyIdType 函数</span><span class="sxs-lookup"><span data-stu-id="4124d-103">JsGetPropertyIdType Function</span></span>

<span data-ttu-id="4124d-104">获取属性的类型。</span><span class="sxs-lookup"><span data-stu-id="4124d-104">Gets the type of property.</span></span>  
  
## <span data-ttu-id="4124d-105">语法</span><span class="sxs-lookup"><span data-stu-id="4124d-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetPropertyIdType(  
   _In_ JsPropertyIdRef propertyId,  
   _Out_ JsPropertyIdType* propertyIdType  
);  
```  
  
#### <span data-ttu-id="4124d-106">参数</span><span class="sxs-lookup"><span data-stu-id="4124d-106">Parameters</span></span>  
 `propertyId`  
 <span data-ttu-id="4124d-107">要获取其类型的属性 ID。</span><span class="sxs-lookup"><span data-stu-id="4124d-107">The property ID to get the type of.</span></span>  
  
 `propertyIdType`  
 <span data-ttu-id="4124d-108">给定 `JsPropertyIdType` 属性 ID 的 ID。</span><span class="sxs-lookup"><span data-stu-id="4124d-108">The `JsPropertyIdType` of the given property ID.</span></span>  
  
## <span data-ttu-id="4124d-109">返回值</span><span class="sxs-lookup"><span data-stu-id="4124d-109">Return Value</span></span>  
 <span data-ttu-id="4124d-110">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="4124d-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="4124d-111">备注</span><span class="sxs-lookup"><span data-stu-id="4124d-111">Remarks</span></span>  
 <span data-ttu-id="4124d-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="4124d-112">Requires an active script context.</span></span>  
  
 <span data-ttu-id="4124d-113">此 API 仅在 Microsoft Edge 模式下受支持。</span><span class="sxs-lookup"><span data-stu-id="4124d-113">This API is supported only in Microsoft Edge mode.</span></span>  
  
## <span data-ttu-id="4124d-114">要求</span><span class="sxs-lookup"><span data-stu-id="4124d-114">Requirements</span></span>  
 <span data-ttu-id="4124d-115">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="4124d-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="4124d-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4124d-116">See Also</span></span>  
 [<span data-ttu-id="4124d-117">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="4124d-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
