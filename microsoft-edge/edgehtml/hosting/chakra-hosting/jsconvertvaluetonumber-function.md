---
description: 使用标准 JavaScript 语义将值转换为数字。
title: JsConvertValueToNumber 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsConvertValueToNumber
helpviewer_keywords:
- JsConvertValueToNumber function
ms.assetid: c47b8653-0591-4863-b8b5-33187b315816
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 8d00950ef3835c6d75f8f55ffe5002b32c6ee160
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232220"
---
# <span data-ttu-id="90d4b-103">JsConvertValueToNumber 函数</span><span class="sxs-lookup"><span data-stu-id="90d4b-103">JsConvertValueToNumber Function</span></span>

<span data-ttu-id="90d4b-104">使用标准 JavaScript 语义将值转换为数字。</span><span class="sxs-lookup"><span data-stu-id="90d4b-104">Converts the value to number using standard JavaScript semantics.</span></span>  
  
## <span data-ttu-id="90d4b-105">语法</span><span class="sxs-lookup"><span data-stu-id="90d4b-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsConvertValueToNumber(  
   _In_ JsValueRef value,  
   _Out_ JsValueRef *numberValue  
);  
```  
  
#### <span data-ttu-id="90d4b-106">参数</span><span class="sxs-lookup"><span data-stu-id="90d4b-106">Parameters</span></span>  
 `value`  
 <span data-ttu-id="90d4b-107">要转换的值。</span><span class="sxs-lookup"><span data-stu-id="90d4b-107">The value to be converted.</span></span>  
  
 `numberValue`  
 <span data-ttu-id="90d4b-108">转换后的值。</span><span class="sxs-lookup"><span data-stu-id="90d4b-108">The converted value.</span></span>  
  
## <span data-ttu-id="90d4b-109">返回值</span><span class="sxs-lookup"><span data-stu-id="90d4b-109">Return Value</span></span>  
 <span data-ttu-id="90d4b-110">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="90d4b-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="90d4b-111">备注</span><span class="sxs-lookup"><span data-stu-id="90d4b-111">Remarks</span></span>  
 <span data-ttu-id="90d4b-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="90d4b-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="90d4b-113">要求</span><span class="sxs-lookup"><span data-stu-id="90d4b-113">Requirements</span></span>  
 <span data-ttu-id="90d4b-114">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="90d4b-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="90d4b-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="90d4b-115">See Also</span></span>  
 [<span data-ttu-id="90d4b-116">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="90d4b-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
