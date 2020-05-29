---
description: 检索 `bool` 布尔值的值。
title: JsBooleanToBool 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsBooleanToBool
helpviewer_keywords:
- JsBooleanToBool function
ms.assetid: ab16ac71-fe47-475d-a7ee-46e4643dee60
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 55b0ef1278cbc73652fc8427e004cab002d76e5b
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563200"
---
# <span data-ttu-id="c7591-103">JsBooleanToBool 函数</span><span class="sxs-lookup"><span data-stu-id="c7591-103">JsBooleanToBool Function</span></span>
<span data-ttu-id="c7591-104">检索 `bool` 布尔值的值。</span><span class="sxs-lookup"><span data-stu-id="c7591-104">Retrieves the `bool` value of a Boolean value.</span></span>  
  
## <span data-ttu-id="c7591-105">语法</span><span class="sxs-lookup"><span data-stu-id="c7591-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsBooleanToBool(  
   _In_ JsValueRef value,  
   _Out_ bool *boolValue  
);  
```  
  
#### <span data-ttu-id="c7591-106">参数</span><span class="sxs-lookup"><span data-stu-id="c7591-106">Parameters</span></span>  
 `value`  
 <span data-ttu-id="c7591-107">要转换的值。</span><span class="sxs-lookup"><span data-stu-id="c7591-107">The value to be converted.</span></span>  
  
 `boolValue`  
 <span data-ttu-id="c7591-108">已转换的值。</span><span class="sxs-lookup"><span data-stu-id="c7591-108">The converted value.</span></span>  
  
## <span data-ttu-id="c7591-109">返回值</span><span class="sxs-lookup"><span data-stu-id="c7591-109">Return Value</span></span>  
 <span data-ttu-id="c7591-110">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="c7591-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="c7591-111">备注</span><span class="sxs-lookup"><span data-stu-id="c7591-111">Remarks</span></span>  
 <span data-ttu-id="c7591-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="c7591-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="c7591-113">要求</span><span class="sxs-lookup"><span data-stu-id="c7591-113">Requirements</span></span>  
 <span data-ttu-id="c7591-114">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="c7591-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="c7591-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c7591-115">See Also</span></span>  
 [<span data-ttu-id="c7591-116">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="c7591-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)