---
description: 获取当前 `true` 脚本上下文中的值。
title: JsGetTrueValue 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsGetTrueValue
helpviewer_keywords:
- JsGetTrueValue function
ms.assetid: c2a56d48-344b-492b-90b8-f570710f8310
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 58798e1e8aab57d626be0c8c878f9be39d0af942
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232763"
---
# <span data-ttu-id="01592-103">JsGetTrueValue 函数</span><span class="sxs-lookup"><span data-stu-id="01592-103">JsGetTrueValue Function</span></span>

<span data-ttu-id="01592-104">获取当前 `true` 脚本上下文中的值。</span><span class="sxs-lookup"><span data-stu-id="01592-104">Gets the value of `true` in the current script context.</span></span>  
  
## <span data-ttu-id="01592-105">语法</span><span class="sxs-lookup"><span data-stu-id="01592-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetTrueValue(  
   _Out_ JsValueRef *trueValue  
);  
```  
  
#### <span data-ttu-id="01592-106">参数</span><span class="sxs-lookup"><span data-stu-id="01592-106">Parameters</span></span>  
 `trueValue`  
 <span data-ttu-id="01592-107">`true`值。</span><span class="sxs-lookup"><span data-stu-id="01592-107">The `true` value.</span></span>  
  
## <span data-ttu-id="01592-108">返回值</span><span class="sxs-lookup"><span data-stu-id="01592-108">Return Value</span></span>  
 <span data-ttu-id="01592-109">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="01592-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="01592-110">备注</span><span class="sxs-lookup"><span data-stu-id="01592-110">Remarks</span></span>  
 <span data-ttu-id="01592-111">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="01592-111">Requires an active script context.</span></span>  
  
## <span data-ttu-id="01592-112">要求</span><span class="sxs-lookup"><span data-stu-id="01592-112">Requirements</span></span>  
 <span data-ttu-id="01592-113">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="01592-113">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="01592-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="01592-114">See Also</span></span>  
 [<span data-ttu-id="01592-115">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="01592-115">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
