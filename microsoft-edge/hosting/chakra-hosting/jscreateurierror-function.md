---
description: 创建新的 JavaScript URIError error 对象。
title: JsCreateURIError 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsCreateURIError
helpviewer_keywords:
- JsCreateURIError function
ms.assetid: 711fd237-12a2-4ff0-b58a-ad74c91e79fb
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 5188827cd0b89b1dd6b54af005f6e118c4ae4c94
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563144"
---
# <span data-ttu-id="ba6ad-103">JsCreateURIError 函数</span><span class="sxs-lookup"><span data-stu-id="ba6ad-103">JsCreateURIError Function</span></span>
<span data-ttu-id="ba6ad-104">创建新的 JavaScript URIError error 对象。</span><span class="sxs-lookup"><span data-stu-id="ba6ad-104">Creates a new JavaScript URIError error object.</span></span>  
  
## <span data-ttu-id="ba6ad-105">语法</span><span class="sxs-lookup"><span data-stu-id="ba6ad-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateURIError(  
   _In_ JsValueRef message,  
   _Out_ JsValueRef *error  
);  
```  
  
#### <span data-ttu-id="ba6ad-106">参数</span><span class="sxs-lookup"><span data-stu-id="ba6ad-106">Parameters</span></span>  
 `message`  
 <span data-ttu-id="ba6ad-107">错误对象的消息。</span><span class="sxs-lookup"><span data-stu-id="ba6ad-107">Message for the error object.</span></span>  
  
 `error`  
 <span data-ttu-id="ba6ad-108">新的错误对象。</span><span class="sxs-lookup"><span data-stu-id="ba6ad-108">The new error object.</span></span>  
  
## <span data-ttu-id="ba6ad-109">返回值</span><span class="sxs-lookup"><span data-stu-id="ba6ad-109">Return Value</span></span>  
 <span data-ttu-id="ba6ad-110">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="ba6ad-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="ba6ad-111">备注</span><span class="sxs-lookup"><span data-stu-id="ba6ad-111">Remarks</span></span>  
 <span data-ttu-id="ba6ad-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="ba6ad-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="ba6ad-113">要求</span><span class="sxs-lookup"><span data-stu-id="ba6ad-113">Requirements</span></span>  
 <span data-ttu-id="ba6ad-114">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="ba6ad-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="ba6ad-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ba6ad-115">See Also</span></span>  
 [<span data-ttu-id="ba6ad-116">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="ba6ad-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)