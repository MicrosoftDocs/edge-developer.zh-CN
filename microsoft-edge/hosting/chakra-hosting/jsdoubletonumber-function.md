---
description: 从 double 值创建一个数值。
title: JsDoubleToNumber 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsDoubleToNumber
helpviewer_keywords:
- JsDoubleToNumber function
ms.assetid: 43eb2ee1-2789-4302-954e-c4087e1ee786
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: c33adbe217f27f77e348fc56e87c4587c6a6ec4c
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564271"
---
# <span data-ttu-id="ea92d-103">JsDoubleToNumber 函数</span><span class="sxs-lookup"><span data-stu-id="ea92d-103">JsDoubleToNumber Function</span></span>
<span data-ttu-id="ea92d-104">从值创建一个数值 `double` 。</span><span class="sxs-lookup"><span data-stu-id="ea92d-104">Creates a number value from a `double` value.</span></span>  
  
## <span data-ttu-id="ea92d-105">语法</span><span class="sxs-lookup"><span data-stu-id="ea92d-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsDoubleToNumber(  
   _In_ double doubleValue,  
   _Out_ JsValueRef *value  
);  
```  
  
#### <span data-ttu-id="ea92d-106">参数</span><span class="sxs-lookup"><span data-stu-id="ea92d-106">Parameters</span></span>  
 `doubleValue`  
 <span data-ttu-id="ea92d-107">`double`要转换为数字值的。</span><span class="sxs-lookup"><span data-stu-id="ea92d-107">The `double` to convert to a number value.</span></span>  
  
 `value`  
 <span data-ttu-id="ea92d-108">新的数字值。</span><span class="sxs-lookup"><span data-stu-id="ea92d-108">The new number value.</span></span>  
  
## <span data-ttu-id="ea92d-109">返回值</span><span class="sxs-lookup"><span data-stu-id="ea92d-109">Return Value</span></span>  
 <span data-ttu-id="ea92d-110">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="ea92d-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="ea92d-111">备注</span><span class="sxs-lookup"><span data-stu-id="ea92d-111">Remarks</span></span>  
 <span data-ttu-id="ea92d-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="ea92d-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="ea92d-113">要求</span><span class="sxs-lookup"><span data-stu-id="ea92d-113">Requirements</span></span>  
 <span data-ttu-id="ea92d-114">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="ea92d-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="ea92d-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ea92d-115">See Also</span></span>  
 [<span data-ttu-id="ea92d-116">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="ea92d-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)