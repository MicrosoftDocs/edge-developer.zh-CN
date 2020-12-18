---
description: 设置线程上的当前脚本上下文。
title: JsSetCurrentContext 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsSetCurrentContext
helpviewer_keywords:
- JsSetCurrentContext function
ms.assetid: 603cc94c-6585-411b-89f9-c6f144e2aa30
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 60ec1760c582f1f6771a5af64f59c4a77b1a43f8
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232358"
---
# <span data-ttu-id="92494-103">JsSetCurrentContext 函数</span><span class="sxs-lookup"><span data-stu-id="92494-103">JsSetCurrentContext Function</span></span>

<span data-ttu-id="92494-104">设置线程上的当前脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="92494-104">Sets the current script context on the thread.</span></span>  
  
## <span data-ttu-id="92494-105">语法</span><span class="sxs-lookup"><span data-stu-id="92494-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsSetCurrentContext(  
   _In_ JsContextRef context  
);  
```  
  
#### <span data-ttu-id="92494-106">参数</span><span class="sxs-lookup"><span data-stu-id="92494-106">Parameters</span></span>  
 `context`  
 <span data-ttu-id="92494-107">要成为当前脚本的脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="92494-107">The script context to make current.</span></span>  
  
## <span data-ttu-id="92494-108">返回值</span><span class="sxs-lookup"><span data-stu-id="92494-108">Return Value</span></span>  
 <span data-ttu-id="92494-109">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="92494-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  

## <span data-ttu-id="92494-110">示例</span><span class="sxs-lookup"><span data-stu-id="92494-110">Example</span></span>

```cpp
JsRuntimeHandle runtime;
JsContextRef context;

// Create a runtime.
JsCreateRuntime(JsRuntimeAttributeNone, nullptr, &runtime);

// Create an execution context.
JsCreateContext(runtime, &context);

// Now set the current execution context.
JsSetCurrentContext(context);
```

## <span data-ttu-id="92494-111">要求</span><span class="sxs-lookup"><span data-stu-id="92494-111">Requirements</span></span>  
 <span data-ttu-id="92494-112">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="92494-112">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="92494-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="92494-113">See Also</span></span>  
 [<span data-ttu-id="92494-114">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="92494-114">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
