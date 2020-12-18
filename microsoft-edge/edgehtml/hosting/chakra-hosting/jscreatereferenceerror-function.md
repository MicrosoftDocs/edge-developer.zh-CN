---
description: 创建新的 JavaScript ReferenceError 错误对象。
title: JsCreateReferenceError 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsCreateReferenceError
helpviewer_keywords:
- JsCreateReferenceError function
ms.assetid: 1d0b2339-4bea-4dd0-a46a-4dcbf0be3bd8
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: fc8f10c443d6ca019c1460c84344bf04513e44b9
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232420"
---
# <span data-ttu-id="e7e58-103">JsCreateReferenceError 函数</span><span class="sxs-lookup"><span data-stu-id="e7e58-103">JsCreateReferenceError Function</span></span>

<span data-ttu-id="e7e58-104">创建新的 JavaScript ReferenceError 错误对象。</span><span class="sxs-lookup"><span data-stu-id="e7e58-104">Creates a new JavaScript ReferenceError error object.</span></span>
  
## <span data-ttu-id="e7e58-105">语法</span><span class="sxs-lookup"><span data-stu-id="e7e58-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateReferenceError(  
   _In_ JsValueRef message,  
   _Out_ JsValueRef *error  
);  
```  
  
#### <span data-ttu-id="e7e58-106">参数</span><span class="sxs-lookup"><span data-stu-id="e7e58-106">Parameters</span></span>  
 `message`  
 <span data-ttu-id="e7e58-107">错误对象的消息。</span><span class="sxs-lookup"><span data-stu-id="e7e58-107">Message for the error object.</span></span>  
  
 `error`  
 <span data-ttu-id="e7e58-108">新的错误对象。</span><span class="sxs-lookup"><span data-stu-id="e7e58-108">The new error object.</span></span>  
  
## <span data-ttu-id="e7e58-109">返回值</span><span class="sxs-lookup"><span data-stu-id="e7e58-109">Return Value</span></span>  
 <span data-ttu-id="e7e58-110">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="e7e58-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="e7e58-111">备注</span><span class="sxs-lookup"><span data-stu-id="e7e58-111">Remarks</span></span>  
 <span data-ttu-id="e7e58-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="e7e58-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="e7e58-113">要求</span><span class="sxs-lookup"><span data-stu-id="e7e58-113">Requirements</span></span>  
 <span data-ttu-id="e7e58-114">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="e7e58-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="e7e58-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e7e58-115">See Also</span></span>  
 [<span data-ttu-id="e7e58-116">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="e7e58-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
