---
description: 从字符串指针创建字符串值。
title: JsPointerToString 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsPointerToString
helpviewer_keywords:
- JsPointerToString function
ms.assetid: c71ce07e-4359-450c-afbf-a6ab7d48dddf
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: b3c5b2d6439244bc9584e15c361412c8a1e87557
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564214"
---
# <span data-ttu-id="3edcb-103">JsPointerToString 函数</span><span class="sxs-lookup"><span data-stu-id="3edcb-103">JsPointerToString Function</span></span>
<span data-ttu-id="3edcb-104">从字符串指针创建字符串值。</span><span class="sxs-lookup"><span data-stu-id="3edcb-104">Creates a string value from a string pointer.</span></span>  
  
## <span data-ttu-id="3edcb-105">语法</span><span class="sxs-lookup"><span data-stu-id="3edcb-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsPointerToString(  
   _In_reads_(stringLength) const wchar_t *stringValue,  
   _In_ size_t stringLength,  
   _Out_ JsValueRef *value  
);  
```  
  
#### <span data-ttu-id="3edcb-106">参数</span><span class="sxs-lookup"><span data-stu-id="3edcb-106">Parameters</span></span>  
 `stringValue`  
 <span data-ttu-id="3edcb-107">要转换为字符串值的字符串指针。</span><span class="sxs-lookup"><span data-stu-id="3edcb-107">The string pointer to convert to a string value.</span></span>  
  
 `stringLength`  
 <span data-ttu-id="3edcb-108">要转换的字符串的长度。</span><span class="sxs-lookup"><span data-stu-id="3edcb-108">The length of the string to convert.</span></span>  
  
 `value`  
 <span data-ttu-id="3edcb-109">新的字符串值。</span><span class="sxs-lookup"><span data-stu-id="3edcb-109">The new string value.</span></span>  
  
## <span data-ttu-id="3edcb-110">返回值</span><span class="sxs-lookup"><span data-stu-id="3edcb-110">Return Value</span></span>  
 <span data-ttu-id="3edcb-111">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="3edcb-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="3edcb-112">备注</span><span class="sxs-lookup"><span data-stu-id="3edcb-112">Remarks</span></span>  
 <span data-ttu-id="3edcb-113">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="3edcb-113">Requires an active script context.</span></span>  
  
## <span data-ttu-id="3edcb-114">要求</span><span class="sxs-lookup"><span data-stu-id="3edcb-114">Requirements</span></span>  
 <span data-ttu-id="3edcb-115">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="3edcb-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="3edcb-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3edcb-116">See Also</span></span>  
 [<span data-ttu-id="3edcb-117">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="3edcb-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)