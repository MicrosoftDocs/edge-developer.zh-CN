---
description: 检索 `double` 数字值的值。
title: JsNumberToDouble 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsNumberToDouble
helpviewer_keywords:
- JsNumberToDouble function
ms.assetid: 5f52e8b6-2b70-49a3-879a-bd83ebf2ac33
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: fc99e02aa0376bb100b4e1302c29532a57bd539f
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563082"
---
# <span data-ttu-id="57b16-103">JsNumberToDouble 函数</span><span class="sxs-lookup"><span data-stu-id="57b16-103">JsNumberToDouble Function</span></span>
<span data-ttu-id="57b16-104">检索 `double` 数字值的值。</span><span class="sxs-lookup"><span data-stu-id="57b16-104">Retrieves the `double` value of a number value.</span></span>  
  
## <span data-ttu-id="57b16-105">语法</span><span class="sxs-lookup"><span data-stu-id="57b16-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsNumberToDouble(  
   _In_ JsValueRef value,  
   _Out_ double *doubleValue  
);  
```  
  
#### <span data-ttu-id="57b16-106">参数</span><span class="sxs-lookup"><span data-stu-id="57b16-106">Parameters</span></span>  
 `value`  
 <span data-ttu-id="57b16-107">要转换为值的数字值 `double` 。</span><span class="sxs-lookup"><span data-stu-id="57b16-107">The number value to convert to a `double` value.</span></span>  
  
 `doubleValue`  
 <span data-ttu-id="57b16-108">`double`值。</span><span class="sxs-lookup"><span data-stu-id="57b16-108">The `double` value.</span></span>  
  
## <span data-ttu-id="57b16-109">返回值</span><span class="sxs-lookup"><span data-stu-id="57b16-109">Return Value</span></span>  
 <span data-ttu-id="57b16-110">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="57b16-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="57b16-111">备注</span><span class="sxs-lookup"><span data-stu-id="57b16-111">Remarks</span></span>  
 <span data-ttu-id="57b16-112">此函数检索数字值的值。</span><span class="sxs-lookup"><span data-stu-id="57b16-112">This function retrieves the value of a number value.</span></span> <span data-ttu-id="57b16-113">`JsErrorInvalidArgument`如果值的类型不是数字，它将失败。</span><span class="sxs-lookup"><span data-stu-id="57b16-113">It will fail with `JsErrorInvalidArgument` if the type of the value is not number.</span></span>  
  
 <span data-ttu-id="57b16-114">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="57b16-114">Requires an active script context.</span></span>  
  
## <span data-ttu-id="57b16-115">要求</span><span class="sxs-lookup"><span data-stu-id="57b16-115">Requirements</span></span>  
 <span data-ttu-id="57b16-116">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="57b16-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="57b16-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="57b16-117">See Also</span></span>  
 [<span data-ttu-id="57b16-118">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="57b16-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)