---
description: 获取当前 `false` 脚本上下文中的值。
title: JsGetFalseValue 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsGetFalseValue
helpviewer_keywords:
- JsGetFalseValue function
ms.assetid: 621a584c-4ca8-4ba0-b19a-6cb50cf830b6
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: c87ad969fc7547f4d650148005327fb93dce805d
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232443"
---
# <span data-ttu-id="f520c-103">JsGetFalseValue 函数</span><span class="sxs-lookup"><span data-stu-id="f520c-103">JsGetFalseValue Function</span></span>

<span data-ttu-id="f520c-104">获取当前 `false` 脚本上下文中的值。</span><span class="sxs-lookup"><span data-stu-id="f520c-104">Gets the value of `false` in the current script context.</span></span>  
  
## <span data-ttu-id="f520c-105">语法</span><span class="sxs-lookup"><span data-stu-id="f520c-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetFalseValue(  
   _Out_ JsValueRef *falseValue  
);  
```  
  
#### <span data-ttu-id="f520c-106">参数</span><span class="sxs-lookup"><span data-stu-id="f520c-106">Parameters</span></span>  
 `falseValue`  
 <span data-ttu-id="f520c-107">`false`值。</span><span class="sxs-lookup"><span data-stu-id="f520c-107">The `false` value.</span></span>  
  
## <span data-ttu-id="f520c-108">返回值</span><span class="sxs-lookup"><span data-stu-id="f520c-108">Return Value</span></span>  
 <span data-ttu-id="f520c-109">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="f520c-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="f520c-110">备注</span><span class="sxs-lookup"><span data-stu-id="f520c-110">Remarks</span></span>  
 <span data-ttu-id="f520c-111">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="f520c-111">Requires an active script context.</span></span>  
  
## <span data-ttu-id="f520c-112">要求</span><span class="sxs-lookup"><span data-stu-id="f520c-112">Requirements</span></span>  
 <span data-ttu-id="f520c-113">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="f520c-113">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="f520c-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f520c-114">See Also</span></span>  
 [<span data-ttu-id="f520c-115">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="f520c-115">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
