---
description: 获取 `true` 当前脚本上下文中的值。
title: JsGetTrueValue 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsGetTrueValue
helpviewer_keywords:
- JsGetTrueValue function
ms.assetid: c2a56d48-344b-492b-90b8-f570710f8310
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 620ed775947db9d7156d61df1cfdf974a46baec2
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563102"
---
# <span data-ttu-id="361b3-103">JsGetTrueValue 函数</span><span class="sxs-lookup"><span data-stu-id="361b3-103">JsGetTrueValue Function</span></span>
<span data-ttu-id="361b3-104">获取 `true` 当前脚本上下文中的值。</span><span class="sxs-lookup"><span data-stu-id="361b3-104">Gets the value of `true` in the current script context.</span></span>  
  
## <span data-ttu-id="361b3-105">语法</span><span class="sxs-lookup"><span data-stu-id="361b3-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetTrueValue(  
   _Out_ JsValueRef *trueValue  
);  
```  
  
#### <span data-ttu-id="361b3-106">参数</span><span class="sxs-lookup"><span data-stu-id="361b3-106">Parameters</span></span>  
 `trueValue`  
 <span data-ttu-id="361b3-107">`true`值。</span><span class="sxs-lookup"><span data-stu-id="361b3-107">The `true` value.</span></span>  
  
## <span data-ttu-id="361b3-108">返回值</span><span class="sxs-lookup"><span data-stu-id="361b3-108">Return Value</span></span>  
 <span data-ttu-id="361b3-109">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="361b3-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="361b3-110">备注</span><span class="sxs-lookup"><span data-stu-id="361b3-110">Remarks</span></span>  
 <span data-ttu-id="361b3-111">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="361b3-111">Requires an active script context.</span></span>  
  
## <span data-ttu-id="361b3-112">要求</span><span class="sxs-lookup"><span data-stu-id="361b3-112">Requirements</span></span>  
 <span data-ttu-id="361b3-113">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="361b3-113">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="361b3-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="361b3-114">See Also</span></span>  
 [<span data-ttu-id="361b3-115">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="361b3-115">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)