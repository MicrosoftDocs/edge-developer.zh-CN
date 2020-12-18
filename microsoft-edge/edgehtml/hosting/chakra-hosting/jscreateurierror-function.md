---
description: 创建新的 JavaScript URIError 错误对象。
title: JsCreateURIError 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsCreateURIError
helpviewer_keywords:
- JsCreateURIError function
ms.assetid: 711fd237-12a2-4ff0-b58a-ad74c91e79fb
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 88e6c1fc04607b3be088e297d1fa86f9374bcb03
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232337"
---
# <span data-ttu-id="06c08-103">JsCreateURIError 函数</span><span class="sxs-lookup"><span data-stu-id="06c08-103">JsCreateURIError Function</span></span>

<span data-ttu-id="06c08-104">创建新的 JavaScript URIError 错误对象。</span><span class="sxs-lookup"><span data-stu-id="06c08-104">Creates a new JavaScript URIError error object.</span></span>  
  
## <span data-ttu-id="06c08-105">语法</span><span class="sxs-lookup"><span data-stu-id="06c08-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateURIError(  
   _In_ JsValueRef message,  
   _Out_ JsValueRef *error  
);  
```  
  
#### <span data-ttu-id="06c08-106">参数</span><span class="sxs-lookup"><span data-stu-id="06c08-106">Parameters</span></span>  
 `message`  
 <span data-ttu-id="06c08-107">错误对象的消息。</span><span class="sxs-lookup"><span data-stu-id="06c08-107">Message for the error object.</span></span>  
  
 `error`  
 <span data-ttu-id="06c08-108">新的错误对象。</span><span class="sxs-lookup"><span data-stu-id="06c08-108">The new error object.</span></span>  
  
## <span data-ttu-id="06c08-109">返回值</span><span class="sxs-lookup"><span data-stu-id="06c08-109">Return Value</span></span>  
 <span data-ttu-id="06c08-110">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="06c08-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="06c08-111">备注</span><span class="sxs-lookup"><span data-stu-id="06c08-111">Remarks</span></span>  
 <span data-ttu-id="06c08-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="06c08-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="06c08-113">要求</span><span class="sxs-lookup"><span data-stu-id="06c08-113">Requirements</span></span>  
 <span data-ttu-id="06c08-114">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="06c08-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="06c08-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="06c08-115">See Also</span></span>  
 [<span data-ttu-id="06c08-116">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="06c08-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
