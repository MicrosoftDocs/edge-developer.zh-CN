---
description: 创建新的 JavaScript 错误对象。
title: JsCreateError 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsCreateError
helpviewer_keywords:
- JsCreateError function
ms.assetid: dadbcac8-c56f-4f30-ba00-2d284daee191
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: cd2fd0172902cc6dc8a4dd169eef5947d0b25256
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232199"
---
# <span data-ttu-id="5ce7b-103">JsCreateError 函数</span><span class="sxs-lookup"><span data-stu-id="5ce7b-103">JsCreateError Function</span></span>

<span data-ttu-id="5ce7b-104">创建新的 JavaScript 错误对象。</span><span class="sxs-lookup"><span data-stu-id="5ce7b-104">Creates a new JavaScript error object.</span></span>  
  
## <span data-ttu-id="5ce7b-105">语法</span><span class="sxs-lookup"><span data-stu-id="5ce7b-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateError(  
   _In_ JsValueRef message,  
   _Out_ JsValueRef *error  
);  
```  
  
#### <span data-ttu-id="5ce7b-106">参数</span><span class="sxs-lookup"><span data-stu-id="5ce7b-106">Parameters</span></span>  
 `message`  
 <span data-ttu-id="5ce7b-107">错误对象的消息。</span><span class="sxs-lookup"><span data-stu-id="5ce7b-107">Message for the error object.</span></span>  
  
 `error`  
 <span data-ttu-id="5ce7b-108">新的错误对象。</span><span class="sxs-lookup"><span data-stu-id="5ce7b-108">The new error object.</span></span>  
  
## <span data-ttu-id="5ce7b-109">返回值</span><span class="sxs-lookup"><span data-stu-id="5ce7b-109">Return Value</span></span>  
 <span data-ttu-id="5ce7b-110">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="5ce7b-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="5ce7b-111">备注</span><span class="sxs-lookup"><span data-stu-id="5ce7b-111">Remarks</span></span>  
 <span data-ttu-id="5ce7b-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="5ce7b-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="5ce7b-113">要求</span><span class="sxs-lookup"><span data-stu-id="5ce7b-113">Requirements</span></span>  
 <span data-ttu-id="5ce7b-114">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="5ce7b-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="5ce7b-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5ce7b-115">See Also</span></span>  
 [<span data-ttu-id="5ce7b-116">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="5ce7b-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
