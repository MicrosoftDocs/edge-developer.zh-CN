---
description: 获取线程上的当前脚本上下文。
title: JsGetCurrentContext 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsGetCurrentContext
helpviewer_keywords:
- JsGetCurrentContext function
ms.assetid: dd5fe0fa-d1e5-4af6-809e-e655a27519b5
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: a43b9a6d4413ef1dc1b66321d6078aef84a0645f
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232450"
---
# <span data-ttu-id="85257-103">JsGetCurrentContext 函数</span><span class="sxs-lookup"><span data-stu-id="85257-103">JsGetCurrentContext Function</span></span>

<span data-ttu-id="85257-104">获取线程上的当前脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="85257-104">Gets the current script context on the thread.</span></span>  
  
## <span data-ttu-id="85257-105">语法</span><span class="sxs-lookup"><span data-stu-id="85257-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetCurrentContext(  
   _Out_ JsContextRef *currentContext  
);  
```  
  
#### <span data-ttu-id="85257-106">参数</span><span class="sxs-lookup"><span data-stu-id="85257-106">Parameters</span></span>  
 `currentContext`  
 <span data-ttu-id="85257-107">线程上的当前脚本上下文，如果没有当前脚本上下文，则为空。</span><span class="sxs-lookup"><span data-stu-id="85257-107">The current script context on the thread, null if there is no current script context.</span></span>  
  
## <span data-ttu-id="85257-108">返回值</span><span class="sxs-lookup"><span data-stu-id="85257-108">Return Value</span></span>  
 <span data-ttu-id="85257-109">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="85257-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="85257-110">要求</span><span class="sxs-lookup"><span data-stu-id="85257-110">Requirements</span></span>  
 <span data-ttu-id="85257-111">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="85257-111">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="85257-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="85257-112">See Also</span></span>  
 [<span data-ttu-id="85257-113">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="85257-113">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
