---
description: 检索 `double` 数字值的值。
title: JsNumberToDouble 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsNumberToDouble
helpviewer_keywords:
- JsNumberToDouble function
ms.assetid: 5f52e8b6-2b70-49a3-879a-bd83ebf2ac33
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: e4ae744f091045116a639aff619c475c7c7025f3
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232541"
---
# <span data-ttu-id="38944-103">JsNumberToDouble 函数</span><span class="sxs-lookup"><span data-stu-id="38944-103">JsNumberToDouble Function</span></span>

<span data-ttu-id="38944-104">检索 `double` 数字值的值。</span><span class="sxs-lookup"><span data-stu-id="38944-104">Retrieves the `double` value of a number value.</span></span>  
  
## <span data-ttu-id="38944-105">语法</span><span class="sxs-lookup"><span data-stu-id="38944-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsNumberToDouble(  
   _In_ JsValueRef value,  
   _Out_ double *doubleValue  
);  
```  
  
#### <span data-ttu-id="38944-106">参数</span><span class="sxs-lookup"><span data-stu-id="38944-106">Parameters</span></span>  
 `value`  
 <span data-ttu-id="38944-107">要转换为值的数量 `double` 值。</span><span class="sxs-lookup"><span data-stu-id="38944-107">The number value to convert to a `double` value.</span></span>  
  
 `doubleValue`  
 <span data-ttu-id="38944-108">`double`值。</span><span class="sxs-lookup"><span data-stu-id="38944-108">The `double` value.</span></span>  
  
## <span data-ttu-id="38944-109">返回值</span><span class="sxs-lookup"><span data-stu-id="38944-109">Return Value</span></span>  
 <span data-ttu-id="38944-110">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="38944-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="38944-111">备注</span><span class="sxs-lookup"><span data-stu-id="38944-111">Remarks</span></span>  
 <span data-ttu-id="38944-112">此函数检索数字值的值。</span><span class="sxs-lookup"><span data-stu-id="38944-112">This function retrieves the value of a number value.</span></span> <span data-ttu-id="38944-113">如果值的类型 `JsErrorInvalidArgument` 不是数字，则失败。</span><span class="sxs-lookup"><span data-stu-id="38944-113">It will fail with `JsErrorInvalidArgument` if the type of the value is not number.</span></span>  
  
 <span data-ttu-id="38944-114">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="38944-114">Requires an active script context.</span></span>  
  
## <span data-ttu-id="38944-115">要求</span><span class="sxs-lookup"><span data-stu-id="38944-115">Requirements</span></span>  
 <span data-ttu-id="38944-116">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="38944-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="38944-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="38944-117">See Also</span></span>  
 [<span data-ttu-id="38944-118">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="38944-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
