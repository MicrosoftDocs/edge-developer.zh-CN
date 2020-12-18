---
description: 从双精度值创建数字值。
title: JsDoubleToNumber 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsDoubleToNumber
helpviewer_keywords:
- JsDoubleToNumber function
ms.assetid: 43eb2ee1-2789-4302-954e-c4087e1ee786
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: d3385633f41c2e20c43ca865eaeec763b6ff7f43
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232400"
---
# <span data-ttu-id="b7834-103">JsDoubleToNumber 函数</span><span class="sxs-lookup"><span data-stu-id="b7834-103">JsDoubleToNumber Function</span></span>

<span data-ttu-id="b7834-104">从值创建数字 `double` 值。</span><span class="sxs-lookup"><span data-stu-id="b7834-104">Creates a number value from a `double` value.</span></span>  
  
## <span data-ttu-id="b7834-105">语法</span><span class="sxs-lookup"><span data-stu-id="b7834-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsDoubleToNumber(  
   _In_ double doubleValue,  
   _Out_ JsValueRef *value  
);  
```  
  
#### <span data-ttu-id="b7834-106">参数</span><span class="sxs-lookup"><span data-stu-id="b7834-106">Parameters</span></span>  
 `doubleValue`  
 <span data-ttu-id="b7834-107">`double`要转换为数字值的。</span><span class="sxs-lookup"><span data-stu-id="b7834-107">The `double` to convert to a number value.</span></span>  
  
 `value`  
 <span data-ttu-id="b7834-108">新数字值。</span><span class="sxs-lookup"><span data-stu-id="b7834-108">The new number value.</span></span>  
  
## <span data-ttu-id="b7834-109">返回值</span><span class="sxs-lookup"><span data-stu-id="b7834-109">Return Value</span></span>  
 <span data-ttu-id="b7834-110">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="b7834-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="b7834-111">备注</span><span class="sxs-lookup"><span data-stu-id="b7834-111">Remarks</span></span>  
 <span data-ttu-id="b7834-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="b7834-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="b7834-113">要求</span><span class="sxs-lookup"><span data-stu-id="b7834-113">Requirements</span></span>  
 <span data-ttu-id="b7834-114">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="b7834-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="b7834-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b7834-115">See Also</span></span>  
 [<span data-ttu-id="b7834-116">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="b7834-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
