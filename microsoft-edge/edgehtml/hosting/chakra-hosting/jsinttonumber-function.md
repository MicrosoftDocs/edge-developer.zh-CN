---
description: 从值创建数字 `int` 值。
title: JsIntToNumber 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 1393c4ac-7189-4e9c-8e54-b0e041c22112
caps.latest.revision: 4
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 24e861d1535ae79843fb35de8a047031a479fe16
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232581"
---
# <span data-ttu-id="86300-103">JsIntToNumber 函数</span><span class="sxs-lookup"><span data-stu-id="86300-103">JsIntToNumber Function</span></span>

<span data-ttu-id="86300-104">从值创建数字 `int` 值。</span><span class="sxs-lookup"><span data-stu-id="86300-104">Creates a number value from an `int` value.</span></span>  
  
## <span data-ttu-id="86300-105">语法</span><span class="sxs-lookup"><span data-stu-id="86300-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsIntToNumber(  
   _In_ int intValue,  
   _Out_ JsValueRef *value  
);  
```  
  
#### <span data-ttu-id="86300-106">参数</span><span class="sxs-lookup"><span data-stu-id="86300-106">Parameters</span></span>  
 `intValue`  
 <span data-ttu-id="86300-107">`int`要转换为数字值的。</span><span class="sxs-lookup"><span data-stu-id="86300-107">The `int` to convert to a number value.</span></span>  
  
 `value`  
 <span data-ttu-id="86300-108">新数字值。</span><span class="sxs-lookup"><span data-stu-id="86300-108">The new number value.</span></span>  
  
## <span data-ttu-id="86300-109">返回值</span><span class="sxs-lookup"><span data-stu-id="86300-109">Return Value</span></span>  
 <span data-ttu-id="86300-110">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="86300-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="86300-111">备注</span><span class="sxs-lookup"><span data-stu-id="86300-111">Remarks</span></span>  
 <span data-ttu-id="86300-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="86300-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="86300-113">要求</span><span class="sxs-lookup"><span data-stu-id="86300-113">Requirements</span></span>  
 <span data-ttu-id="86300-114">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="86300-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="86300-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="86300-115">See Also</span></span>  
 [<span data-ttu-id="86300-116">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="86300-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
