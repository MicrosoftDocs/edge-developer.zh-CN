---
description: 获取字符串值的长度。
title: JsGetStringLength 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsGetStringLength
helpviewer_keywords:
- JsGetStringLength function
ms.assetid: e9f9f28c-e644-439c-aee5-7ce362f71347
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 6b562b2dc58341523910db41fb8b748453b2a836
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563108"
---
# <span data-ttu-id="56b21-103">JsGetStringLength 函数</span><span class="sxs-lookup"><span data-stu-id="56b21-103">JsGetStringLength Function</span></span>
<span data-ttu-id="56b21-104">获取字符串值的长度。</span><span class="sxs-lookup"><span data-stu-id="56b21-104">Gets the length of a string value.</span></span>  
  
## <span data-ttu-id="56b21-105">语法</span><span class="sxs-lookup"><span data-stu-id="56b21-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetStringLength(  
   _In_ JsValueRef stringValue,  
   _Out_ int *length  
);  
```  
  
#### <span data-ttu-id="56b21-106">参数</span><span class="sxs-lookup"><span data-stu-id="56b21-106">Parameters</span></span>  
 `stringValue`  
 <span data-ttu-id="56b21-107">要获取其长度的字符串值。</span><span class="sxs-lookup"><span data-stu-id="56b21-107">The string value to get the length of.</span></span>  
  
 `length`  
 <span data-ttu-id="56b21-108">字符串的长度。</span><span class="sxs-lookup"><span data-stu-id="56b21-108">The length of the string.</span></span>  
  
## <span data-ttu-id="56b21-109">返回值</span><span class="sxs-lookup"><span data-stu-id="56b21-109">Return Value</span></span>  
 <span data-ttu-id="56b21-110">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="56b21-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="56b21-111">备注</span><span class="sxs-lookup"><span data-stu-id="56b21-111">Remarks</span></span>  
 <span data-ttu-id="56b21-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="56b21-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="56b21-113">要求</span><span class="sxs-lookup"><span data-stu-id="56b21-113">Requirements</span></span>  
 <span data-ttu-id="56b21-114">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="56b21-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="56b21-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="56b21-115">See Also</span></span>  
 [<span data-ttu-id="56b21-116">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="56b21-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)