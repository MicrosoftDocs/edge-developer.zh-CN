---
description: 检索 `int` 数字值的值。
title: JsNumberToInt 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 8b9256d6-76ac-4c74-a97c-fbb16c13f5f5
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 928be9a7cc5cd3e26e8b8df99af1e08a6c50209c
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232539"
---
# <span data-ttu-id="9a38f-103">JsNumberToInt 函数</span><span class="sxs-lookup"><span data-stu-id="9a38f-103">JsNumberToInt Function</span></span>

<span data-ttu-id="9a38f-104">检索 `int` 数字值的值。</span><span class="sxs-lookup"><span data-stu-id="9a38f-104">Retrieves the `int` value of a number value.</span></span>  
  
## <span data-ttu-id="9a38f-105">语法</span><span class="sxs-lookup"><span data-stu-id="9a38f-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsNumberToInt(  
      _In_ JsValueRef value,  
      _Out_ int *intValue  
);  
```  
  
#### <span data-ttu-id="9a38f-106">参数</span><span class="sxs-lookup"><span data-stu-id="9a38f-106">Parameters</span></span>  
 `value`  
 <span data-ttu-id="9a38f-107">要转换为值的数量 `int` 值。</span><span class="sxs-lookup"><span data-stu-id="9a38f-107">The number value to convert to an `int` value.</span></span>  
  
 `intValue`  
 <span data-ttu-id="9a38f-108">`int`值。</span><span class="sxs-lookup"><span data-stu-id="9a38f-108">The `int` value.</span></span>  
  
## <span data-ttu-id="9a38f-109">返回值</span><span class="sxs-lookup"><span data-stu-id="9a38f-109">Return Value</span></span>  
  
## <span data-ttu-id="9a38f-110">备注</span><span class="sxs-lookup"><span data-stu-id="9a38f-110">Remarks</span></span>  
 <span data-ttu-id="9a38f-111">此函数检索数字值并转换为 `int` 值。</span><span class="sxs-lookup"><span data-stu-id="9a38f-111">This function retrieves the value of a number value and converts to an `int` value.</span></span> <span data-ttu-id="9a38f-112">如果值的类型 `JsErrorInvalidArgument` 不是数字，则失败。</span><span class="sxs-lookup"><span data-stu-id="9a38f-112">It will fail with `JsErrorInvalidArgument` if the type of the value is not number.</span></span>  
  
 <span data-ttu-id="9a38f-113">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="9a38f-113">Requires an active script context.</span></span>  
  
 <span data-ttu-id="9a38f-114">此 API 仅在 EdgeHTML 模式下受支持。</span><span class="sxs-lookup"><span data-stu-id="9a38f-114">This API is supported only in EdgeHTML mode.</span></span>  
  
## <span data-ttu-id="9a38f-115">要求</span><span class="sxs-lookup"><span data-stu-id="9a38f-115">Requirements</span></span>  
 <span data-ttu-id="9a38f-116">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="9a38f-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="9a38f-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9a38f-117">See Also</span></span>  
 [<span data-ttu-id="9a38f-118">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="9a38f-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
