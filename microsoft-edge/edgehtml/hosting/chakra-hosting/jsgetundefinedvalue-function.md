---
description: 获取当前 `undefined` 脚本上下文中的值。
title: JsGetUndefinedValue 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsGetUndefinedValue
helpviewer_keywords:
- JsGetUndefinedValue function
ms.assetid: e118eaf6-452c-42f2-86b8-e63c7d987cba
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 34bfaec4548ee2b77d6d98749c3049bb8f679134
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232061"
---
# <span data-ttu-id="9a764-103">JsGetUndefinedValue 函数</span><span class="sxs-lookup"><span data-stu-id="9a764-103">JsGetUndefinedValue Function</span></span>

<span data-ttu-id="9a764-104">获取当前 `undefined` 脚本上下文中的值。</span><span class="sxs-lookup"><span data-stu-id="9a764-104">Gets the value of `undefined` in the current script context.</span></span>  
  
## <span data-ttu-id="9a764-105">语法</span><span class="sxs-lookup"><span data-stu-id="9a764-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetUndefinedValue(  
   _Out_ JsValueRef *undefinedValue  
);  
```  
  
#### <span data-ttu-id="9a764-106">参数</span><span class="sxs-lookup"><span data-stu-id="9a764-106">Parameters</span></span>  
 `undefinedValue`  
 <span data-ttu-id="9a764-107">`undefined`值。</span><span class="sxs-lookup"><span data-stu-id="9a764-107">The `undefined` value.</span></span>  
  
## <span data-ttu-id="9a764-108">返回值</span><span class="sxs-lookup"><span data-stu-id="9a764-108">Return Value</span></span>  
 <span data-ttu-id="9a764-109">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="9a764-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="9a764-110">备注</span><span class="sxs-lookup"><span data-stu-id="9a764-110">Remarks</span></span>  
 <span data-ttu-id="9a764-111">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="9a764-111">Requires an active script context.</span></span>  
  
## <span data-ttu-id="9a764-112">要求</span><span class="sxs-lookup"><span data-stu-id="9a764-112">Requirements</span></span>  
 <span data-ttu-id="9a764-113">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="9a764-113">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="9a764-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9a764-114">See Also</span></span>  
 [<span data-ttu-id="9a764-115">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="9a764-115">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
