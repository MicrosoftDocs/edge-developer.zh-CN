---
description: 创建新的 JavaScript SyntaxError 错误对象。
title: JsCreateSyntaxError 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsCreateSyntaxError
helpviewer_keywords:
- JsCreateSyntaxError function
ms.assetid: 839845fc-60c4-4ffc-bfcc-fd7a8f06126f
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 7d6534bfa2b59cb2f6ab68c231d7a97c84876d62
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232553"
---
# <span data-ttu-id="931a6-103">JsCreateSyntaxError 函数</span><span class="sxs-lookup"><span data-stu-id="931a6-103">JsCreateSyntaxError Function</span></span>

<span data-ttu-id="931a6-104">创建新的 JavaScript SyntaxError 错误对象。</span><span class="sxs-lookup"><span data-stu-id="931a6-104">Creates a new JavaScript SyntaxError error object.</span></span>  
  
## <span data-ttu-id="931a6-105">语法</span><span class="sxs-lookup"><span data-stu-id="931a6-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateSyntaxError(  
   _In_ JsValueRef message,  
   _Out_ JsValueRef *error  
);  
```  
  
#### <span data-ttu-id="931a6-106">参数</span><span class="sxs-lookup"><span data-stu-id="931a6-106">Parameters</span></span>  
 `message`  
 <span data-ttu-id="931a6-107">错误对象的消息。</span><span class="sxs-lookup"><span data-stu-id="931a6-107">Message for the error object.</span></span>  
  
 `error`  
 <span data-ttu-id="931a6-108">新的错误对象。</span><span class="sxs-lookup"><span data-stu-id="931a6-108">The new error object.</span></span>  
  
## <span data-ttu-id="931a6-109">返回值</span><span class="sxs-lookup"><span data-stu-id="931a6-109">Return Value</span></span>  
 <span data-ttu-id="931a6-110">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="931a6-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="931a6-111">备注</span><span class="sxs-lookup"><span data-stu-id="931a6-111">Remarks</span></span>  
 <span data-ttu-id="931a6-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="931a6-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="931a6-113">要求</span><span class="sxs-lookup"><span data-stu-id="931a6-113">Requirements</span></span>  
 <span data-ttu-id="931a6-114">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="931a6-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="931a6-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="931a6-115">See Also</span></span>  
 [<span data-ttu-id="931a6-116">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="931a6-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
