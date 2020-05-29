---
description: 使用标准 JavaScript 语义将值转换为布尔值。
title: JsConvertValueToBoolean 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsConvertValueToBoolean
helpviewer_keywords:
- JsConvertValueToBoolean function
ms.assetid: 7298ec72-a388-4334-b81b-1691ab4cecf0
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 861871a030d5a47621ccaf40b6cd332f42a06583
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563185"
---
# <span data-ttu-id="51f91-103">JsConvertValueToBoolean 函数</span><span class="sxs-lookup"><span data-stu-id="51f91-103">JsConvertValueToBoolean Function</span></span>
<span data-ttu-id="51f91-104">使用标准 JavaScript 语义将值转换为布尔值。</span><span class="sxs-lookup"><span data-stu-id="51f91-104">Converts the value to Boolean using standard JavaScript semantics.</span></span>  
  
## <span data-ttu-id="51f91-105">语法</span><span class="sxs-lookup"><span data-stu-id="51f91-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsConvertValueToBoolean(  
   _In_ JsValueRef value,  
   _Out_ JsValueRef *booleanValue  
);  
```  
  
#### <span data-ttu-id="51f91-106">参数</span><span class="sxs-lookup"><span data-stu-id="51f91-106">Parameters</span></span>  
 `value`  
 <span data-ttu-id="51f91-107">要转换的值。</span><span class="sxs-lookup"><span data-stu-id="51f91-107">The value to be converted.</span></span>  
  
 `booleanValue`  
 <span data-ttu-id="51f91-108">已转换的值。</span><span class="sxs-lookup"><span data-stu-id="51f91-108">The converted value.</span></span>  
  
## <span data-ttu-id="51f91-109">返回值</span><span class="sxs-lookup"><span data-stu-id="51f91-109">Return Value</span></span>  
 <span data-ttu-id="51f91-110">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="51f91-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="51f91-111">备注</span><span class="sxs-lookup"><span data-stu-id="51f91-111">Remarks</span></span>  
 <span data-ttu-id="51f91-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="51f91-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="51f91-113">要求</span><span class="sxs-lookup"><span data-stu-id="51f91-113">Requirements</span></span>  
 <span data-ttu-id="51f91-114">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="51f91-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="51f91-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="51f91-115">See Also</span></span>  
 [<span data-ttu-id="51f91-116">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="51f91-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)