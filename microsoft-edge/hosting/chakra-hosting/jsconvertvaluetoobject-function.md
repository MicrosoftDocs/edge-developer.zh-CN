---
description: 使用标准 JavaScript 语义将值转换为对象。
title: JsConvertValueToObject 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsConvertValueToObject
helpviewer_keywords:
- JsConvertValueToObject function
ms.assetid: 6528b28a-1d2b-417f-bf78-bf05547c52e1
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 6a8b1a8933cdcaaf250a2e28ed8fc758ea66cc0e
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563182"
---
# <span data-ttu-id="77e6c-103">JsConvertValueToObject 函数</span><span class="sxs-lookup"><span data-stu-id="77e6c-103">JsConvertValueToObject Function</span></span>
<span data-ttu-id="77e6c-104">使用标准 JavaScript 语义将值转换为对象。</span><span class="sxs-lookup"><span data-stu-id="77e6c-104">Converts the value to object using standard JavaScript semantics.</span></span>  
  
## <span data-ttu-id="77e6c-105">语法</span><span class="sxs-lookup"><span data-stu-id="77e6c-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsConvertValueToObject(  
   _In_ JsValueRef value,  
   _Out_ JsValueRef *object  
);  
```  
  
#### <span data-ttu-id="77e6c-106">参数</span><span class="sxs-lookup"><span data-stu-id="77e6c-106">Parameters</span></span>  
 `value`  
 <span data-ttu-id="77e6c-107">要转换的值。</span><span class="sxs-lookup"><span data-stu-id="77e6c-107">The value to be converted.</span></span>  
  
 `object`  
 <span data-ttu-id="77e6c-108">已转换的值。</span><span class="sxs-lookup"><span data-stu-id="77e6c-108">The converted value.</span></span>  
  
## <span data-ttu-id="77e6c-109">返回值</span><span class="sxs-lookup"><span data-stu-id="77e6c-109">Return Value</span></span>  
 <span data-ttu-id="77e6c-110">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="77e6c-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="77e6c-111">备注</span><span class="sxs-lookup"><span data-stu-id="77e6c-111">Remarks</span></span>  
 <span data-ttu-id="77e6c-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="77e6c-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="77e6c-113">要求</span><span class="sxs-lookup"><span data-stu-id="77e6c-113">Requirements</span></span>  
 <span data-ttu-id="77e6c-114">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="77e6c-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="77e6c-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="77e6c-115">See Also</span></span>  
 [<span data-ttu-id="77e6c-116">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="77e6c-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)