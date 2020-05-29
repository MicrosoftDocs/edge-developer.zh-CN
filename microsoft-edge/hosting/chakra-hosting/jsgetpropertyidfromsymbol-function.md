---
description: 获取与该符号关联的属性 ID。
title: JsGetPropertyIdFromSymbol 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 190fe4b9-352e-4b10-9d0e-6c6bbd6363e8
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 0d11dbaf25b85e2bcd85a0cf2bac1b499fd4fa3e
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564246"
---
# <span data-ttu-id="d15dd-103">JsGetPropertyIdFromSymbol 函数</span><span class="sxs-lookup"><span data-stu-id="d15dd-103">JsGetPropertyIdFromSymbol Function</span></span>
<span data-ttu-id="d15dd-104">获取与该符号关联的属性 ID。</span><span class="sxs-lookup"><span data-stu-id="d15dd-104">Gets the property ID associated with the symbol.</span></span>  
  
## <span data-ttu-id="d15dd-105">语法</span><span class="sxs-lookup"><span data-stu-id="d15dd-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetPropertyIdFromSymbol(  
   _In_ JsValueRef symbol,  
   _Out_ JsPropertyIdRef *propertyId  
);  
```  
  
#### <span data-ttu-id="d15dd-106">参数</span><span class="sxs-lookup"><span data-stu-id="d15dd-106">Parameters</span></span>  
 `symbol`  
 <span data-ttu-id="d15dd-107">正在检索其属性 ID 的符号。</span><span class="sxs-lookup"><span data-stu-id="d15dd-107">The symbol whose property ID is being retrieved.</span></span>  
  
 `propertyId`  
 <span data-ttu-id="d15dd-108">给定符号的属性 ID。</span><span class="sxs-lookup"><span data-stu-id="d15dd-108">The property ID for the given symbol.</span></span>  
  
## <span data-ttu-id="d15dd-109">返回值</span><span class="sxs-lookup"><span data-stu-id="d15dd-109">Return Value</span></span>  
 <span data-ttu-id="d15dd-110">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="d15dd-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="d15dd-111">备注</span><span class="sxs-lookup"><span data-stu-id="d15dd-111">Remarks</span></span>  
 <span data-ttu-id="d15dd-112">属性 Id 特定于上下文，不能跨上下文使用。</span><span class="sxs-lookup"><span data-stu-id="d15dd-112">Property IDs are specific to a context and cannot be used across contexts.</span></span>  
  
 <span data-ttu-id="d15dd-113">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="d15dd-113">Requires an active script context.</span></span>  
  
 <span data-ttu-id="d15dd-114">此 API 仅在 Microsoft Edge 模式下受支持。</span><span class="sxs-lookup"><span data-stu-id="d15dd-114">This API is supported only in Microsoft Edge mode.</span></span>  
  
## <span data-ttu-id="d15dd-115">要求</span><span class="sxs-lookup"><span data-stu-id="d15dd-115">Requirements</span></span>  
 <span data-ttu-id="d15dd-116">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="d15dd-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="d15dd-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d15dd-117">See Also</span></span>  
 [<span data-ttu-id="d15dd-118">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="d15dd-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)