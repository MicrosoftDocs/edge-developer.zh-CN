---
description: 创建新的 JavaScript RangeError 错误对象。
title: JsCreateRangeError 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsCreateRangeError
helpviewer_keywords:
- JsCreateRangeError function
ms.assetid: 0ab05de7-57af-4cfd-9aa5-0a69a893cc97
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 72cf882d5f9517f0f05d9e3367283f5f531dbdb3
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232364"
---
# <span data-ttu-id="79563-103">JsCreateRangeError 函数</span><span class="sxs-lookup"><span data-stu-id="79563-103">JsCreateRangeError Function</span></span>

<span data-ttu-id="79563-104">创建新的 JavaScript RangeError 错误对象。</span><span class="sxs-lookup"><span data-stu-id="79563-104">Creates a new JavaScript RangeError error object.</span></span>
  
## <span data-ttu-id="79563-105">语法</span><span class="sxs-lookup"><span data-stu-id="79563-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateRangeError(  
   _In_ JsValueRef message,  
   _Out_ JsValueRef *error  
);  
```  
  
#### <span data-ttu-id="79563-106">参数</span><span class="sxs-lookup"><span data-stu-id="79563-106">Parameters</span></span>  
 `message`  
 <span data-ttu-id="79563-107">错误对象的消息。</span><span class="sxs-lookup"><span data-stu-id="79563-107">Message for the error object.</span></span>  
  
 `error`  
 <span data-ttu-id="79563-108">新的错误对象。</span><span class="sxs-lookup"><span data-stu-id="79563-108">The new error object.</span></span>  
  
## <span data-ttu-id="79563-109">返回值</span><span class="sxs-lookup"><span data-stu-id="79563-109">Return Value</span></span>  
 <span data-ttu-id="79563-110">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="79563-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="79563-111">备注</span><span class="sxs-lookup"><span data-stu-id="79563-111">Remarks</span></span>  
 <span data-ttu-id="79563-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="79563-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="79563-113">要求</span><span class="sxs-lookup"><span data-stu-id="79563-113">Requirements</span></span>  
 <span data-ttu-id="79563-114">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="79563-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="79563-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="79563-115">See Also</span></span>  
 [<span data-ttu-id="79563-116">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="79563-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
