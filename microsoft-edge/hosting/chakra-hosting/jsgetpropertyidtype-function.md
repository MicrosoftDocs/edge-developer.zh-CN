---
description: 获取属性的类型。
title: JsGetPropertyIdType 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 2b6e85ad-c630-4a07-a759-3b344d06faaa
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: a43cfc2efd69cc14813ad88850afbf602d477d71
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564244"
---
# <span data-ttu-id="e0ab7-103">JsGetPropertyIdType 函数</span><span class="sxs-lookup"><span data-stu-id="e0ab7-103">JsGetPropertyIdType Function</span></span>
<span data-ttu-id="e0ab7-104">获取属性的类型。</span><span class="sxs-lookup"><span data-stu-id="e0ab7-104">Gets the type of property.</span></span>  
  
## <span data-ttu-id="e0ab7-105">语法</span><span class="sxs-lookup"><span data-stu-id="e0ab7-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetPropertyIdType(  
   _In_ JsPropertyIdRef propertyId,  
   _Out_ JsPropertyIdType* propertyIdType  
);  
```  
  
#### <span data-ttu-id="e0ab7-106">参数</span><span class="sxs-lookup"><span data-stu-id="e0ab7-106">Parameters</span></span>  
 `propertyId`  
 <span data-ttu-id="e0ab7-107">要获取其类型的属性 ID。</span><span class="sxs-lookup"><span data-stu-id="e0ab7-107">The property ID to get the type of.</span></span>  
  
 `propertyIdType`  
 <span data-ttu-id="e0ab7-108">`JsPropertyIdType`给定属性 ID 的。</span><span class="sxs-lookup"><span data-stu-id="e0ab7-108">The `JsPropertyIdType` of the given property ID.</span></span>  
  
## <span data-ttu-id="e0ab7-109">返回值</span><span class="sxs-lookup"><span data-stu-id="e0ab7-109">Return Value</span></span>  
 <span data-ttu-id="e0ab7-110">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="e0ab7-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="e0ab7-111">备注</span><span class="sxs-lookup"><span data-stu-id="e0ab7-111">Remarks</span></span>  
 <span data-ttu-id="e0ab7-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="e0ab7-112">Requires an active script context.</span></span>  
  
 <span data-ttu-id="e0ab7-113">此 API 仅在 Microsoft Edge 模式下受支持。</span><span class="sxs-lookup"><span data-stu-id="e0ab7-113">This API is supported only in Microsoft Edge mode.</span></span>  
  
## <span data-ttu-id="e0ab7-114">要求</span><span class="sxs-lookup"><span data-stu-id="e0ab7-114">Requirements</span></span>  
 <span data-ttu-id="e0ab7-115">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="e0ab7-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="e0ab7-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e0ab7-116">See Also</span></span>  
 [<span data-ttu-id="e0ab7-117">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="e0ab7-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)