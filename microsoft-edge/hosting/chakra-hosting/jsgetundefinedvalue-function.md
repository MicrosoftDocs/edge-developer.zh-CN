---
description: 获取 `undefined` 当前脚本上下文中的值。
title: JsGetUndefinedValue 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsGetUndefinedValue
helpviewer_keywords:
- JsGetUndefinedValue function
ms.assetid: e118eaf6-452c-42f2-86b8-e63c7d987cba
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 5edd536a29f5003591de476cb5d21ddb64f48c0b
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564236"
---
# <span data-ttu-id="c2c30-103">JsGetUndefinedValue 函数</span><span class="sxs-lookup"><span data-stu-id="c2c30-103">JsGetUndefinedValue Function</span></span>
<span data-ttu-id="c2c30-104">获取 `undefined` 当前脚本上下文中的值。</span><span class="sxs-lookup"><span data-stu-id="c2c30-104">Gets the value of `undefined` in the current script context.</span></span>  
  
## <span data-ttu-id="c2c30-105">语法</span><span class="sxs-lookup"><span data-stu-id="c2c30-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetUndefinedValue(  
   _Out_ JsValueRef *undefinedValue  
);  
```  
  
#### <span data-ttu-id="c2c30-106">参数</span><span class="sxs-lookup"><span data-stu-id="c2c30-106">Parameters</span></span>  
 `undefinedValue`  
 <span data-ttu-id="c2c30-107">`undefined`值。</span><span class="sxs-lookup"><span data-stu-id="c2c30-107">The `undefined` value.</span></span>  
  
## <span data-ttu-id="c2c30-108">返回值</span><span class="sxs-lookup"><span data-stu-id="c2c30-108">Return Value</span></span>  
 <span data-ttu-id="c2c30-109">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="c2c30-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="c2c30-110">备注</span><span class="sxs-lookup"><span data-stu-id="c2c30-110">Remarks</span></span>  
 <span data-ttu-id="c2c30-111">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="c2c30-111">Requires an active script context.</span></span>  
  
## <span data-ttu-id="c2c30-112">要求</span><span class="sxs-lookup"><span data-stu-id="c2c30-112">Requirements</span></span>  
 <span data-ttu-id="c2c30-113">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="c2c30-113">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="c2c30-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c2c30-114">See Also</span></span>  
 [<span data-ttu-id="c2c30-115">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="c2c30-115">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)