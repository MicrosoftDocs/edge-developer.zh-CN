---
description: 检索 `int` 数字值的值。
title: JsNumberToInt 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 8b9256d6-76ac-4c74-a97c-fbb16c13f5f5
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: cf4c8cb42c737cfb9efee5422fe6bb3c1389cbfd
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564222"
---
# <span data-ttu-id="cee96-103">JsNumberToInt 函数</span><span class="sxs-lookup"><span data-stu-id="cee96-103">JsNumberToInt Function</span></span>
<span data-ttu-id="cee96-104">检索 `int` 数字值的值。</span><span class="sxs-lookup"><span data-stu-id="cee96-104">Retrieves the `int` value of a number value.</span></span>  
  
## <span data-ttu-id="cee96-105">语法</span><span class="sxs-lookup"><span data-stu-id="cee96-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsNumberToInt(  
      _In_ JsValueRef value,  
      _Out_ int *intValue  
);  
```  
  
#### <span data-ttu-id="cee96-106">参数</span><span class="sxs-lookup"><span data-stu-id="cee96-106">Parameters</span></span>  
 `value`  
 <span data-ttu-id="cee96-107">要转换为值的数字值 `int` 。</span><span class="sxs-lookup"><span data-stu-id="cee96-107">The number value to convert to an `int` value.</span></span>  
  
 `intValue`  
 <span data-ttu-id="cee96-108">`int`值。</span><span class="sxs-lookup"><span data-stu-id="cee96-108">The `int` value.</span></span>  
  
## <span data-ttu-id="cee96-109">返回值</span><span class="sxs-lookup"><span data-stu-id="cee96-109">Return Value</span></span>  
  
## <span data-ttu-id="cee96-110">备注</span><span class="sxs-lookup"><span data-stu-id="cee96-110">Remarks</span></span>  
 <span data-ttu-id="cee96-111">此函数可检索数字值的值并将其转换为 `int` 值。</span><span class="sxs-lookup"><span data-stu-id="cee96-111">This function retrieves the value of a number value and converts to an `int` value.</span></span> <span data-ttu-id="cee96-112">`JsErrorInvalidArgument`如果值的类型不是数字，它将失败。</span><span class="sxs-lookup"><span data-stu-id="cee96-112">It will fail with `JsErrorInvalidArgument` if the type of the value is not number.</span></span>  
  
 <span data-ttu-id="cee96-113">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="cee96-113">Requires an active script context.</span></span>  
  
 <span data-ttu-id="cee96-114">此 API 仅在 EdgeHTML 模式下受支持。</span><span class="sxs-lookup"><span data-stu-id="cee96-114">This API is supported only in EdgeHTML mode.</span></span>  
  
## <span data-ttu-id="cee96-115">要求</span><span class="sxs-lookup"><span data-stu-id="cee96-115">Requirements</span></span>  
 <span data-ttu-id="cee96-116">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="cee96-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="cee96-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cee96-117">See Also</span></span>  
 [<span data-ttu-id="cee96-118">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="cee96-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)