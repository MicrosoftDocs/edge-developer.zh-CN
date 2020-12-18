---
description: 获取当前 `null` 脚本上下文中的值。
title: JsGetNullValue 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsGetNullValue
helpviewer_keywords:
- JsGetNullValue function
ms.assetid: 132a1496-8dfe-4d3c-a8f8-389f5b0b50d2
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 31e1ba19f9f27e75f0166238d98390e2c4a26c24
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232027"
---
# <span data-ttu-id="b93bb-103">JsGetNullValue 函数</span><span class="sxs-lookup"><span data-stu-id="b93bb-103">JsGetNullValue Function</span></span>

<span data-ttu-id="b93bb-104">获取当前 `null` 脚本上下文中的值。</span><span class="sxs-lookup"><span data-stu-id="b93bb-104">Gets the value of `null` in the current script context.</span></span>  
  
## <span data-ttu-id="b93bb-105">语法</span><span class="sxs-lookup"><span data-stu-id="b93bb-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetNullValue(  
   _Out_ JsValueRef *nullValue  
);  
```  
  
#### <span data-ttu-id="b93bb-106">参数</span><span class="sxs-lookup"><span data-stu-id="b93bb-106">Parameters</span></span>  
 `nullValue`  
 <span data-ttu-id="b93bb-107">`null`值。</span><span class="sxs-lookup"><span data-stu-id="b93bb-107">The `null` value.</span></span>  
  
## <span data-ttu-id="b93bb-108">返回值</span><span class="sxs-lookup"><span data-stu-id="b93bb-108">Return Value</span></span>  
 <span data-ttu-id="b93bb-109">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="b93bb-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="b93bb-110">备注</span><span class="sxs-lookup"><span data-stu-id="b93bb-110">Remarks</span></span>  
 <span data-ttu-id="b93bb-111">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="b93bb-111">Requires an active script context.</span></span>  
  
## <span data-ttu-id="b93bb-112">要求</span><span class="sxs-lookup"><span data-stu-id="b93bb-112">Requirements</span></span>  
 <span data-ttu-id="b93bb-113">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="b93bb-113">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="b93bb-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b93bb-114">See Also</span></span>  
 [<span data-ttu-id="b93bb-115">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="b93bb-115">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
