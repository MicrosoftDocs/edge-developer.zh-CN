---
description: 使用标准 JavaScript 语义将值转换为布尔值。
title: JsConvertValueToBoolean 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsConvertValueToBoolean
helpviewer_keywords:
- JsConvertValueToBoolean function
ms.assetid: 7298ec72-a388-4334-b81b-1691ab4cecf0
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: d2e109690fc8a7a98a1ecb84d6f5abf6a646162b
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232217"
---
# <span data-ttu-id="2b057-103">JsConvertValueToBoolean 函数</span><span class="sxs-lookup"><span data-stu-id="2b057-103">JsConvertValueToBoolean Function</span></span>

<span data-ttu-id="2b057-104">使用标准 JavaScript 语义将值转换为布尔值。</span><span class="sxs-lookup"><span data-stu-id="2b057-104">Converts the value to Boolean using standard JavaScript semantics.</span></span>  
  
## <span data-ttu-id="2b057-105">语法</span><span class="sxs-lookup"><span data-stu-id="2b057-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsConvertValueToBoolean(  
   _In_ JsValueRef value,  
   _Out_ JsValueRef *booleanValue  
);  
```  
  
#### <span data-ttu-id="2b057-106">参数</span><span class="sxs-lookup"><span data-stu-id="2b057-106">Parameters</span></span>  
 `value`  
 <span data-ttu-id="2b057-107">要转换的值。</span><span class="sxs-lookup"><span data-stu-id="2b057-107">The value to be converted.</span></span>  
  
 `booleanValue`  
 <span data-ttu-id="2b057-108">转换后的值。</span><span class="sxs-lookup"><span data-stu-id="2b057-108">The converted value.</span></span>  
  
## <span data-ttu-id="2b057-109">返回值</span><span class="sxs-lookup"><span data-stu-id="2b057-109">Return Value</span></span>  
 <span data-ttu-id="2b057-110">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="2b057-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="2b057-111">备注</span><span class="sxs-lookup"><span data-stu-id="2b057-111">Remarks</span></span>  
 <span data-ttu-id="2b057-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="2b057-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="2b057-113">要求</span><span class="sxs-lookup"><span data-stu-id="2b057-113">Requirements</span></span>  
 <span data-ttu-id="2b057-114">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="2b057-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="2b057-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2b057-115">See Also</span></span>  
 [<span data-ttu-id="2b057-116">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="2b057-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
