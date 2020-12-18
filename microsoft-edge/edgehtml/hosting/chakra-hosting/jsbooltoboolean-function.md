---
description: 从值创建布尔 `bool` 值。
title: JsBoolToBoolean 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsBoolToBoolean
helpviewer_keywords:
- JsBoolToBoolean function
ms.assetid: 24322ea3-0638-40a3-9b4c-fc912ebed3ff
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 3d6ec9f85d53e0d78c6bbe1c7d3282971831717b
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232218"
---
# <span data-ttu-id="57179-103">JsBoolToBoolean 函数</span><span class="sxs-lookup"><span data-stu-id="57179-103">JsBoolToBoolean Function</span></span>

<span data-ttu-id="57179-104">从值创建布尔 `bool` 值。</span><span class="sxs-lookup"><span data-stu-id="57179-104">Creates a Boolean value from a `bool` value.</span></span>  
  
## <span data-ttu-id="57179-105">语法</span><span class="sxs-lookup"><span data-stu-id="57179-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode JsBoolToBoolean(  
   _In_ bool value,  
   _Out_ JsValueRef *booleanValue  
);  
```  
  
#### <span data-ttu-id="57179-106">参数</span><span class="sxs-lookup"><span data-stu-id="57179-106">Parameters</span></span>  
 `value`  
 <span data-ttu-id="57179-107">要转换的值。</span><span class="sxs-lookup"><span data-stu-id="57179-107">The value to be converted.</span></span>  
  
 `booleanValue`  
 <span data-ttu-id="57179-108">转换后的值。</span><span class="sxs-lookup"><span data-stu-id="57179-108">The converted value.</span></span>  
  
## <span data-ttu-id="57179-109">返回值</span><span class="sxs-lookup"><span data-stu-id="57179-109">Return Value</span></span>  
 <span data-ttu-id="57179-110">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="57179-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="57179-111">备注</span><span class="sxs-lookup"><span data-stu-id="57179-111">Remarks</span></span>  
 <span data-ttu-id="57179-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="57179-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="57179-113">要求</span><span class="sxs-lookup"><span data-stu-id="57179-113">Requirements</span></span>  
 <span data-ttu-id="57179-114">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="57179-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="57179-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="57179-115">See Also</span></span>  
 [<span data-ttu-id="57179-116">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="57179-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
