---
description: 创建新的 JavaScript TypeError 错误对象。
title: JsCreateTypeError 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsCreateTypeError
helpviewer_keywords:
- JsCreateTypeError function
ms.assetid: 8ef7bb77-2c98-482a-bccb-1f0fe2b826f5
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 627dfdc6f01f0708366720a957b3784fc7bb59a4
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232549"
---
# <span data-ttu-id="c3df6-103">JsCreateTypeError 函数</span><span class="sxs-lookup"><span data-stu-id="c3df6-103">JsCreateTypeError Function</span></span>

<span data-ttu-id="c3df6-104">创建新的 JavaScript TypeError 错误对象。</span><span class="sxs-lookup"><span data-stu-id="c3df6-104">Creates a new JavaScript TypeError error object.</span></span>  
  
## <span data-ttu-id="c3df6-105">语法</span><span class="sxs-lookup"><span data-stu-id="c3df6-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateTypeError(  
   _In_ JsValueRef message,  
   _Out_ JsValueRef *error  
);  
```  
  
#### <span data-ttu-id="c3df6-106">参数</span><span class="sxs-lookup"><span data-stu-id="c3df6-106">Parameters</span></span>  
 `message`  
 <span data-ttu-id="c3df6-107">错误对象的消息。</span><span class="sxs-lookup"><span data-stu-id="c3df6-107">Message for the error object.</span></span>  
  
 `error`  
 <span data-ttu-id="c3df6-108">新的错误对象。</span><span class="sxs-lookup"><span data-stu-id="c3df6-108">The new error object.</span></span>  
  
## <span data-ttu-id="c3df6-109">返回值</span><span class="sxs-lookup"><span data-stu-id="c3df6-109">Return Value</span></span>  
 <span data-ttu-id="c3df6-110">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="c3df6-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="c3df6-111">备注</span><span class="sxs-lookup"><span data-stu-id="c3df6-111">Remarks</span></span>  
 <span data-ttu-id="c3df6-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="c3df6-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="c3df6-113">要求</span><span class="sxs-lookup"><span data-stu-id="c3df6-113">Requirements</span></span>  
 <span data-ttu-id="c3df6-114">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="c3df6-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="c3df6-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c3df6-115">See Also</span></span>  
 [<span data-ttu-id="c3df6-116">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="c3df6-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
