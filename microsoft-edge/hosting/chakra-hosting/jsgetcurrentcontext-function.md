---
description: 获取线程上的当前脚本上下文。
title: JsGetCurrentContext 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsGetCurrentContext
helpviewer_keywords:
- JsGetCurrentContext function
ms.assetid: dd5fe0fa-d1e5-4af6-809e-e655a27519b5
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 78f04674aab8783c43f22516903669e0f9b7543b
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563128"
---
# <span data-ttu-id="e67cf-103">JsGetCurrentContext 函数</span><span class="sxs-lookup"><span data-stu-id="e67cf-103">JsGetCurrentContext Function</span></span>
<span data-ttu-id="e67cf-104">获取线程上的当前脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="e67cf-104">Gets the current script context on the thread.</span></span>  
  
## <span data-ttu-id="e67cf-105">语法</span><span class="sxs-lookup"><span data-stu-id="e67cf-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetCurrentContext(  
   _Out_ JsContextRef *currentContext  
);  
```  
  
#### <span data-ttu-id="e67cf-106">参数</span><span class="sxs-lookup"><span data-stu-id="e67cf-106">Parameters</span></span>  
 `currentContext`  
 <span data-ttu-id="e67cf-107">线程上的当前脚本上下文，如果没有当前脚本上下文，则为 null。</span><span class="sxs-lookup"><span data-stu-id="e67cf-107">The current script context on the thread, null if there is no current script context.</span></span>  
  
## <span data-ttu-id="e67cf-108">返回值</span><span class="sxs-lookup"><span data-stu-id="e67cf-108">Return Value</span></span>  
 <span data-ttu-id="e67cf-109">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="e67cf-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="e67cf-110">要求</span><span class="sxs-lookup"><span data-stu-id="e67cf-110">Requirements</span></span>  
 <span data-ttu-id="e67cf-111">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="e67cf-111">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="e67cf-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e67cf-112">See Also</span></span>  
 [<span data-ttu-id="e67cf-113">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="e67cf-113">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)