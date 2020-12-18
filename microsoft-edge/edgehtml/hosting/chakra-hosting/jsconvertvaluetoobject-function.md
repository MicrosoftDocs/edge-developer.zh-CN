---
description: 使用标准 JavaScript 语义将值转换为对象。
title: JsConvertValueToObject 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsConvertValueToObject
helpviewer_keywords:
- JsConvertValueToObject function
ms.assetid: 6528b28a-1d2b-417f-bf78-bf05547c52e1
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 6f3676b512585b0750c994bcfcdf9d2e6e4e1cc3
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232203"
---
# <span data-ttu-id="d6439-103">JsConvertValueToObject 函数</span><span class="sxs-lookup"><span data-stu-id="d6439-103">JsConvertValueToObject Function</span></span>

<span data-ttu-id="d6439-104">使用标准 JavaScript 语义将值转换为对象。</span><span class="sxs-lookup"><span data-stu-id="d6439-104">Converts the value to object using standard JavaScript semantics.</span></span>  
  
## <span data-ttu-id="d6439-105">语法</span><span class="sxs-lookup"><span data-stu-id="d6439-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsConvertValueToObject(  
   _In_ JsValueRef value,  
   _Out_ JsValueRef *object  
);  
```  
  
#### <span data-ttu-id="d6439-106">参数</span><span class="sxs-lookup"><span data-stu-id="d6439-106">Parameters</span></span>  
 `value`  
 <span data-ttu-id="d6439-107">要转换的值。</span><span class="sxs-lookup"><span data-stu-id="d6439-107">The value to be converted.</span></span>  
  
 `object`  
 <span data-ttu-id="d6439-108">转换后的值。</span><span class="sxs-lookup"><span data-stu-id="d6439-108">The converted value.</span></span>  
  
## <span data-ttu-id="d6439-109">返回值</span><span class="sxs-lookup"><span data-stu-id="d6439-109">Return Value</span></span>  
 <span data-ttu-id="d6439-110">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="d6439-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="d6439-111">备注</span><span class="sxs-lookup"><span data-stu-id="d6439-111">Remarks</span></span>  
 <span data-ttu-id="d6439-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="d6439-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="d6439-113">要求</span><span class="sxs-lookup"><span data-stu-id="d6439-113">Requirements</span></span>  
 <span data-ttu-id="d6439-114">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="d6439-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="d6439-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d6439-115">See Also</span></span>  
 [<span data-ttu-id="d6439-116">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="d6439-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
