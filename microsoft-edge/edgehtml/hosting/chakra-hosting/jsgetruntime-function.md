---
description: 获取上下文所属的运行时。
title: JsGetRuntime 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsGetRuntime
helpviewer_keywords:
- JsGetRuntime function
ms.assetid: 5b62e940-a885-405a-9fdd-0495fb391b95
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 49739f0cf3675a44b9fc328e3eaa7d49c6282e53
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232413"
---
# <span data-ttu-id="db81f-103">JsGetRuntime 函数</span><span class="sxs-lookup"><span data-stu-id="db81f-103">JsGetRuntime Function</span></span>

<span data-ttu-id="db81f-104">获取上下文所属的运行时。</span><span class="sxs-lookup"><span data-stu-id="db81f-104">Gets the runtime that the context belongs to.</span></span>  
  
## <span data-ttu-id="db81f-105">语法</span><span class="sxs-lookup"><span data-stu-id="db81f-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetRuntime(  
   _In_ JsContextRef context,  
   _Out_ JsRuntimeHandle *runtime  
);  
```  
  
#### <span data-ttu-id="db81f-106">参数</span><span class="sxs-lookup"><span data-stu-id="db81f-106">Parameters</span></span>  
 `context`  
 <span data-ttu-id="db81f-107">获取运行时的上下文。</span><span class="sxs-lookup"><span data-stu-id="db81f-107">The context to get the runtime from.</span></span>  
  
 `runtime`  
 <span data-ttu-id="db81f-108">上下文所属的运行时。</span><span class="sxs-lookup"><span data-stu-id="db81f-108">The runtime the context belongs to.</span></span>  
  
## <span data-ttu-id="db81f-109">返回值</span><span class="sxs-lookup"><span data-stu-id="db81f-109">Return Value</span></span>  
 <span data-ttu-id="db81f-110">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="db81f-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="db81f-111">要求</span><span class="sxs-lookup"><span data-stu-id="db81f-111">Requirements</span></span>  
 <span data-ttu-id="db81f-112">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="db81f-112">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="db81f-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="db81f-113">See Also</span></span>  
 [<span data-ttu-id="db81f-114">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="db81f-114">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
