---
description: 使用标准 JavaScript 语义将值转换为数字。
title: JsConvertValueToNumber 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsConvertValueToNumber
helpviewer_keywords:
- JsConvertValueToNumber function
ms.assetid: c47b8653-0591-4863-b8b5-33187b315816
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 3b3f450a58aaf1c434e1d34cd51577e3a5a9ee31
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563183"
---
# <span data-ttu-id="5b502-103">JsConvertValueToNumber 函数</span><span class="sxs-lookup"><span data-stu-id="5b502-103">JsConvertValueToNumber Function</span></span>
<span data-ttu-id="5b502-104">使用标准 JavaScript 语义将值转换为数字。</span><span class="sxs-lookup"><span data-stu-id="5b502-104">Converts the value to number using standard JavaScript semantics.</span></span>  
  
## <span data-ttu-id="5b502-105">语法</span><span class="sxs-lookup"><span data-stu-id="5b502-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsConvertValueToNumber(  
   _In_ JsValueRef value,  
   _Out_ JsValueRef *numberValue  
);  
```  
  
#### <span data-ttu-id="5b502-106">参数</span><span class="sxs-lookup"><span data-stu-id="5b502-106">Parameters</span></span>  
 `value`  
 <span data-ttu-id="5b502-107">要转换的值。</span><span class="sxs-lookup"><span data-stu-id="5b502-107">The value to be converted.</span></span>  
  
 `numberValue`  
 <span data-ttu-id="5b502-108">已转换的值。</span><span class="sxs-lookup"><span data-stu-id="5b502-108">The converted value.</span></span>  
  
## <span data-ttu-id="5b502-109">返回值</span><span class="sxs-lookup"><span data-stu-id="5b502-109">Return Value</span></span>  
 <span data-ttu-id="5b502-110">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="5b502-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="5b502-111">备注</span><span class="sxs-lookup"><span data-stu-id="5b502-111">Remarks</span></span>  
 <span data-ttu-id="5b502-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="5b502-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="5b502-113">要求</span><span class="sxs-lookup"><span data-stu-id="5b502-113">Requirements</span></span>  
 <span data-ttu-id="5b502-114">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="5b502-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="5b502-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5b502-115">See Also</span></span>  
 [<span data-ttu-id="5b502-116">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="5b502-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)