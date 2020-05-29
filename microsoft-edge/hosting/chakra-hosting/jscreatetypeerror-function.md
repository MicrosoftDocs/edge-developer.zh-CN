---
description: 创建新的 JavaScript TypeError error 对象。
title: JsCreateTypeError 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsCreateTypeError
helpviewer_keywords:
- JsCreateTypeError function
ms.assetid: 8ef7bb77-2c98-482a-bccb-1f0fe2b826f5
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 302bf75af3668dfdd0b40336e940e3eef3a74bce
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563145"
---
# <span data-ttu-id="1f82b-103">JsCreateTypeError 函数</span><span class="sxs-lookup"><span data-stu-id="1f82b-103">JsCreateTypeError Function</span></span>
<span data-ttu-id="1f82b-104">创建新的 JavaScript TypeError error 对象。</span><span class="sxs-lookup"><span data-stu-id="1f82b-104">Creates a new JavaScript TypeError error object.</span></span>  
  
## <span data-ttu-id="1f82b-105">语法</span><span class="sxs-lookup"><span data-stu-id="1f82b-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateTypeError(  
   _In_ JsValueRef message,  
   _Out_ JsValueRef *error  
);  
```  
  
#### <span data-ttu-id="1f82b-106">参数</span><span class="sxs-lookup"><span data-stu-id="1f82b-106">Parameters</span></span>  
 `message`  
 <span data-ttu-id="1f82b-107">错误对象的消息。</span><span class="sxs-lookup"><span data-stu-id="1f82b-107">Message for the error object.</span></span>  
  
 `error`  
 <span data-ttu-id="1f82b-108">新的错误对象。</span><span class="sxs-lookup"><span data-stu-id="1f82b-108">The new error object.</span></span>  
  
## <span data-ttu-id="1f82b-109">返回值</span><span class="sxs-lookup"><span data-stu-id="1f82b-109">Return Value</span></span>  
 <span data-ttu-id="1f82b-110">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="1f82b-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="1f82b-111">备注</span><span class="sxs-lookup"><span data-stu-id="1f82b-111">Remarks</span></span>  
 <span data-ttu-id="1f82b-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="1f82b-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="1f82b-113">要求</span><span class="sxs-lookup"><span data-stu-id="1f82b-113">Requirements</span></span>  
 <span data-ttu-id="1f82b-114">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="1f82b-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="1f82b-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1f82b-115">See Also</span></span>  
 [<span data-ttu-id="1f82b-116">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="1f82b-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)