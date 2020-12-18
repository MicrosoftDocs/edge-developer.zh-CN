---
description: 从字符串指针创建字符串值。
title: JsPointerToString 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsPointerToString
helpviewer_keywords:
- JsPointerToString function
ms.assetid: c71ce07e-4359-450c-afbf-a6ab7d48dddf
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: c00a060098f0b021afca27b300f3e0578e992cb9
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232530"
---
# <span data-ttu-id="cb49c-103">JsPointerToString 函数</span><span class="sxs-lookup"><span data-stu-id="cb49c-103">JsPointerToString Function</span></span>

<span data-ttu-id="cb49c-104">从字符串指针创建字符串值。</span><span class="sxs-lookup"><span data-stu-id="cb49c-104">Creates a string value from a string pointer.</span></span>  
  
## <span data-ttu-id="cb49c-105">语法</span><span class="sxs-lookup"><span data-stu-id="cb49c-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsPointerToString(  
   _In_reads_(stringLength) const wchar_t *stringValue,  
   _In_ size_t stringLength,  
   _Out_ JsValueRef *value  
);  
```  
  
#### <span data-ttu-id="cb49c-106">参数</span><span class="sxs-lookup"><span data-stu-id="cb49c-106">Parameters</span></span>  
 `stringValue`  
 <span data-ttu-id="cb49c-107">要转换为字符串值的字符串指针。</span><span class="sxs-lookup"><span data-stu-id="cb49c-107">The string pointer to convert to a string value.</span></span>  
  
 `stringLength`  
 <span data-ttu-id="cb49c-108">要转换的字符串的长度。</span><span class="sxs-lookup"><span data-stu-id="cb49c-108">The length of the string to convert.</span></span>  
  
 `value`  
 <span data-ttu-id="cb49c-109">新的字符串值。</span><span class="sxs-lookup"><span data-stu-id="cb49c-109">The new string value.</span></span>  
  
## <span data-ttu-id="cb49c-110">返回值</span><span class="sxs-lookup"><span data-stu-id="cb49c-110">Return Value</span></span>  
 <span data-ttu-id="cb49c-111">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="cb49c-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="cb49c-112">备注</span><span class="sxs-lookup"><span data-stu-id="cb49c-112">Remarks</span></span>  
 <span data-ttu-id="cb49c-113">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="cb49c-113">Requires an active script context.</span></span>  
  
## <span data-ttu-id="cb49c-114">要求</span><span class="sxs-lookup"><span data-stu-id="cb49c-114">Requirements</span></span>  
 <span data-ttu-id="cb49c-115">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="cb49c-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="cb49c-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cb49c-116">See Also</span></span>  
 [<span data-ttu-id="cb49c-117">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="cb49c-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
