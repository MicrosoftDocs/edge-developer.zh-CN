---
description: 获取 `false` 当前脚本上下文中的值。
title: JsGetFalseValue 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsGetFalseValue
helpviewer_keywords:
- JsGetFalseValue function
ms.assetid: 621a584c-4ca8-4ba0-b19a-6cb50cf830b6
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 52e54ad7eb34877c3cb83b06f5aba70edf285bca
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563122"
---
# <span data-ttu-id="2bef0-103">JsGetFalseValue 函数</span><span class="sxs-lookup"><span data-stu-id="2bef0-103">JsGetFalseValue Function</span></span>
<span data-ttu-id="2bef0-104">获取 `false` 当前脚本上下文中的值。</span><span class="sxs-lookup"><span data-stu-id="2bef0-104">Gets the value of `false` in the current script context.</span></span>  
  
## <span data-ttu-id="2bef0-105">语法</span><span class="sxs-lookup"><span data-stu-id="2bef0-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetFalseValue(  
   _Out_ JsValueRef *falseValue  
);  
```  
  
#### <span data-ttu-id="2bef0-106">参数</span><span class="sxs-lookup"><span data-stu-id="2bef0-106">Parameters</span></span>  
 `falseValue`  
 <span data-ttu-id="2bef0-107">`false`值。</span><span class="sxs-lookup"><span data-stu-id="2bef0-107">The `false` value.</span></span>  
  
## <span data-ttu-id="2bef0-108">返回值</span><span class="sxs-lookup"><span data-stu-id="2bef0-108">Return Value</span></span>  
 <span data-ttu-id="2bef0-109">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="2bef0-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="2bef0-110">备注</span><span class="sxs-lookup"><span data-stu-id="2bef0-110">Remarks</span></span>  
 <span data-ttu-id="2bef0-111">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="2bef0-111">Requires an active script context.</span></span>  
  
## <span data-ttu-id="2bef0-112">要求</span><span class="sxs-lookup"><span data-stu-id="2bef0-112">Requirements</span></span>  
 <span data-ttu-id="2bef0-113">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="2bef0-113">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="2bef0-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2bef0-114">See Also</span></span>  
 [<span data-ttu-id="2bef0-115">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="2bef0-115">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)