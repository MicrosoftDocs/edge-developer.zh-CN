---
description: 获取 `null` 当前脚本上下文中的值。
title: JsGetNullValue 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsGetNullValue
helpviewer_keywords:
- JsGetNullValue function
ms.assetid: 132a1496-8dfe-4d3c-a8f8-389f5b0b50d2
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 84164aa9ce5d522b0933d928d85b26c652be066f
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564255"
---
# <span data-ttu-id="3bb98-103">JsGetNullValue 函数</span><span class="sxs-lookup"><span data-stu-id="3bb98-103">JsGetNullValue Function</span></span>
<span data-ttu-id="3bb98-104">获取 `null` 当前脚本上下文中的值。</span><span class="sxs-lookup"><span data-stu-id="3bb98-104">Gets the value of `null` in the current script context.</span></span>  
  
## <span data-ttu-id="3bb98-105">语法</span><span class="sxs-lookup"><span data-stu-id="3bb98-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetNullValue(  
   _Out_ JsValueRef *nullValue  
);  
```  
  
#### <span data-ttu-id="3bb98-106">参数</span><span class="sxs-lookup"><span data-stu-id="3bb98-106">Parameters</span></span>  
 `nullValue`  
 <span data-ttu-id="3bb98-107">`null`值。</span><span class="sxs-lookup"><span data-stu-id="3bb98-107">The `null` value.</span></span>  
  
## <span data-ttu-id="3bb98-108">返回值</span><span class="sxs-lookup"><span data-stu-id="3bb98-108">Return Value</span></span>  
 <span data-ttu-id="3bb98-109">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="3bb98-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="3bb98-110">备注</span><span class="sxs-lookup"><span data-stu-id="3bb98-110">Remarks</span></span>  
 <span data-ttu-id="3bb98-111">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="3bb98-111">Requires an active script context.</span></span>  
  
## <span data-ttu-id="3bb98-112">要求</span><span class="sxs-lookup"><span data-stu-id="3bb98-112">Requirements</span></span>  
 <span data-ttu-id="3bb98-113">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="3bb98-113">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="3bb98-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3bb98-114">See Also</span></span>  
 [<span data-ttu-id="3bb98-115">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="3bb98-115">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)