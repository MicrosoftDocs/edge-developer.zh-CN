---
description: 获取字符串值的长度。
title: JsGetStringLength 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsGetStringLength
helpviewer_keywords:
- JsGetStringLength function
ms.assetid: e9f9f28c-e644-439c-aee5-7ce362f71347
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 10fd6be4bb839ccb9eb64c99931cdb474e3aa7a2
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232768"
---
# <span data-ttu-id="fd4be-103">JsGetStringLength 函数</span><span class="sxs-lookup"><span data-stu-id="fd4be-103">JsGetStringLength Function</span></span>

<span data-ttu-id="fd4be-104">获取字符串值的长度。</span><span class="sxs-lookup"><span data-stu-id="fd4be-104">Gets the length of a string value.</span></span>  
  
## <span data-ttu-id="fd4be-105">语法</span><span class="sxs-lookup"><span data-stu-id="fd4be-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetStringLength(  
   _In_ JsValueRef stringValue,  
   _Out_ int *length  
);  
```  
  
#### <span data-ttu-id="fd4be-106">参数</span><span class="sxs-lookup"><span data-stu-id="fd4be-106">Parameters</span></span>  
 `stringValue`  
 <span data-ttu-id="fd4be-107">要获取其长度的字符串值。</span><span class="sxs-lookup"><span data-stu-id="fd4be-107">The string value to get the length of.</span></span>  
  
 `length`  
 <span data-ttu-id="fd4be-108">字符串的长度。</span><span class="sxs-lookup"><span data-stu-id="fd4be-108">The length of the string.</span></span>  
  
## <span data-ttu-id="fd4be-109">返回值</span><span class="sxs-lookup"><span data-stu-id="fd4be-109">Return Value</span></span>  
 <span data-ttu-id="fd4be-110">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="fd4be-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="fd4be-111">备注</span><span class="sxs-lookup"><span data-stu-id="fd4be-111">Remarks</span></span>  
 <span data-ttu-id="fd4be-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="fd4be-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="fd4be-113">要求</span><span class="sxs-lookup"><span data-stu-id="fd4be-113">Requirements</span></span>  
 <span data-ttu-id="fd4be-114">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="fd4be-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="fd4be-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fd4be-115">See Also</span></span>  
 [<span data-ttu-id="fd4be-116">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="fd4be-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
