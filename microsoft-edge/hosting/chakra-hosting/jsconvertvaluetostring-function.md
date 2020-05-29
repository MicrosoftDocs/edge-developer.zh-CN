---
description: 使用标准 JavaScript 语义将值转换为字符串。
title: JsConvertValueToString 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsConvertValueToString
helpviewer_keywords:
- JsConvertValueToString function
ms.assetid: a97aca04-b2ce-446a-acf4-49cd6777a85c
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 21c77ca3050773c07572665c6d58e0ebc05d8ee9
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563180"
---
# <span data-ttu-id="fc15d-103">JsConvertValueToString 函数</span><span class="sxs-lookup"><span data-stu-id="fc15d-103">JsConvertValueToString Function</span></span>
<span data-ttu-id="fc15d-104">使用标准 JavaScript 语义将值转换为字符串。</span><span class="sxs-lookup"><span data-stu-id="fc15d-104">Converts the value to string using standard JavaScript semantics.</span></span>  
  
## <span data-ttu-id="fc15d-105">语法</span><span class="sxs-lookup"><span data-stu-id="fc15d-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsConvertValueToString(  
   _In_ JsValueRef value,  
   _Out_ JsValueRef *stringValue  
);  
```  
  
#### <span data-ttu-id="fc15d-106">参数</span><span class="sxs-lookup"><span data-stu-id="fc15d-106">Parameters</span></span>  
 `value`  
 <span data-ttu-id="fc15d-107">要转换的值。</span><span class="sxs-lookup"><span data-stu-id="fc15d-107">The value to be converted.</span></span>  
  
 `stringValue`  
 <span data-ttu-id="fc15d-108">已转换的值。</span><span class="sxs-lookup"><span data-stu-id="fc15d-108">The converted value.</span></span>  
  
## <span data-ttu-id="fc15d-109">返回值</span><span class="sxs-lookup"><span data-stu-id="fc15d-109">Return Value</span></span>  
 <span data-ttu-id="fc15d-110">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="fc15d-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="fc15d-111">备注</span><span class="sxs-lookup"><span data-stu-id="fc15d-111">Remarks</span></span>  
 <span data-ttu-id="fc15d-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="fc15d-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="fc15d-113">要求</span><span class="sxs-lookup"><span data-stu-id="fc15d-113">Requirements</span></span>  
 <span data-ttu-id="fc15d-114">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="fc15d-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="fc15d-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fc15d-115">See Also</span></span>  
 [<span data-ttu-id="fc15d-116">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="fc15d-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)