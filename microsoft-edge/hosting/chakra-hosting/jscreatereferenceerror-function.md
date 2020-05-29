---
description: 创建新的 JavaScript ReferenceError error 对象。
title: JsCreateReferenceError 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsCreateReferenceError
helpviewer_keywords:
- JsCreateReferenceError function
ms.assetid: 1d0b2339-4bea-4dd0-a46a-4dcbf0be3bd8
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 958af7111a233077aa7a2c2391b26666f55c634b
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563157"
---
# <span data-ttu-id="a018f-103">JsCreateReferenceError 函数</span><span class="sxs-lookup"><span data-stu-id="a018f-103">JsCreateReferenceError Function</span></span>
<span data-ttu-id="a018f-104">创建新的 JavaScript ReferenceError error 对象。</span><span class="sxs-lookup"><span data-stu-id="a018f-104">Creates a new JavaScript ReferenceError error object.</span></span>
  
## <span data-ttu-id="a018f-105">语法</span><span class="sxs-lookup"><span data-stu-id="a018f-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateReferenceError(  
   _In_ JsValueRef message,  
   _Out_ JsValueRef *error  
);  
```  
  
#### <span data-ttu-id="a018f-106">参数</span><span class="sxs-lookup"><span data-stu-id="a018f-106">Parameters</span></span>  
 `message`  
 <span data-ttu-id="a018f-107">错误对象的消息。</span><span class="sxs-lookup"><span data-stu-id="a018f-107">Message for the error object.</span></span>  
  
 `error`  
 <span data-ttu-id="a018f-108">新的错误对象。</span><span class="sxs-lookup"><span data-stu-id="a018f-108">The new error object.</span></span>  
  
## <span data-ttu-id="a018f-109">返回值</span><span class="sxs-lookup"><span data-stu-id="a018f-109">Return Value</span></span>  
 <span data-ttu-id="a018f-110">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="a018f-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="a018f-111">备注</span><span class="sxs-lookup"><span data-stu-id="a018f-111">Remarks</span></span>  
 <span data-ttu-id="a018f-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="a018f-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="a018f-113">要求</span><span class="sxs-lookup"><span data-stu-id="a018f-113">Requirements</span></span>  
 <span data-ttu-id="a018f-114">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="a018f-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="a018f-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a018f-115">See Also</span></span>  
 [<span data-ttu-id="a018f-116">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="a018f-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)