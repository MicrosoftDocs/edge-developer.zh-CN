---
description: 检索 `bool` 布尔值的值。
title: JsBooleanToBool 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsBooleanToBool
helpviewer_keywords:
- JsBooleanToBool function
ms.assetid: ab16ac71-fe47-475d-a7ee-46e4643dee60
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 36bf2dc32b94466d8cdea37886e86a42c4ec01d3
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232214"
---
# <span data-ttu-id="a783b-103">JsBooleanToBool 函数</span><span class="sxs-lookup"><span data-stu-id="a783b-103">JsBooleanToBool Function</span></span>

<span data-ttu-id="a783b-104">检索 `bool` 布尔值的值。</span><span class="sxs-lookup"><span data-stu-id="a783b-104">Retrieves the `bool` value of a Boolean value.</span></span>  
  
## <span data-ttu-id="a783b-105">语法</span><span class="sxs-lookup"><span data-stu-id="a783b-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsBooleanToBool(  
   _In_ JsValueRef value,  
   _Out_ bool *boolValue  
);  
```  
  
#### <span data-ttu-id="a783b-106">参数</span><span class="sxs-lookup"><span data-stu-id="a783b-106">Parameters</span></span>  
 `value`  
 <span data-ttu-id="a783b-107">要转换的值。</span><span class="sxs-lookup"><span data-stu-id="a783b-107">The value to be converted.</span></span>  
  
 `boolValue`  
 <span data-ttu-id="a783b-108">转换后的值。</span><span class="sxs-lookup"><span data-stu-id="a783b-108">The converted value.</span></span>  
  
## <span data-ttu-id="a783b-109">返回值</span><span class="sxs-lookup"><span data-stu-id="a783b-109">Return Value</span></span>  
 <span data-ttu-id="a783b-110">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="a783b-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="a783b-111">备注</span><span class="sxs-lookup"><span data-stu-id="a783b-111">Remarks</span></span>  
 <span data-ttu-id="a783b-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="a783b-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="a783b-113">要求</span><span class="sxs-lookup"><span data-stu-id="a783b-113">Requirements</span></span>  
 <span data-ttu-id="a783b-114">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="a783b-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="a783b-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a783b-115">See Also</span></span>  
 [<span data-ttu-id="a783b-116">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="a783b-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
