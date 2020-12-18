---
description: 使用标准 JavaScript 语义将值转换为字符串。
title: JsConvertValueToString 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsConvertValueToString
helpviewer_keywords:
- JsConvertValueToString function
ms.assetid: a97aca04-b2ce-446a-acf4-49cd6777a85c
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 499f9555f6385b8458524fb4e14b92339c0aa478
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232202"
---
# <span data-ttu-id="4a0ac-103">JsConvertValueToString 函数</span><span class="sxs-lookup"><span data-stu-id="4a0ac-103">JsConvertValueToString Function</span></span>

<span data-ttu-id="4a0ac-104">使用标准 JavaScript 语义将值转换为字符串。</span><span class="sxs-lookup"><span data-stu-id="4a0ac-104">Converts the value to string using standard JavaScript semantics.</span></span>  
  
## <span data-ttu-id="4a0ac-105">语法</span><span class="sxs-lookup"><span data-stu-id="4a0ac-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsConvertValueToString(  
   _In_ JsValueRef value,  
   _Out_ JsValueRef *stringValue  
);  
```  
  
#### <span data-ttu-id="4a0ac-106">参数</span><span class="sxs-lookup"><span data-stu-id="4a0ac-106">Parameters</span></span>  
 `value`  
 <span data-ttu-id="4a0ac-107">要转换的值。</span><span class="sxs-lookup"><span data-stu-id="4a0ac-107">The value to be converted.</span></span>  
  
 `stringValue`  
 <span data-ttu-id="4a0ac-108">转换后的值。</span><span class="sxs-lookup"><span data-stu-id="4a0ac-108">The converted value.</span></span>  
  
## <span data-ttu-id="4a0ac-109">返回值</span><span class="sxs-lookup"><span data-stu-id="4a0ac-109">Return Value</span></span>  
 <span data-ttu-id="4a0ac-110">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="4a0ac-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="4a0ac-111">备注</span><span class="sxs-lookup"><span data-stu-id="4a0ac-111">Remarks</span></span>  
 <span data-ttu-id="4a0ac-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="4a0ac-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="4a0ac-113">要求</span><span class="sxs-lookup"><span data-stu-id="4a0ac-113">Requirements</span></span>  
 <span data-ttu-id="4a0ac-114">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="4a0ac-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="4a0ac-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4a0ac-115">See Also</span></span>  
 [<span data-ttu-id="4a0ac-116">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="4a0ac-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
