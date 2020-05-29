---
description: 设置线程上的当前脚本上下文。
title: JsSetCurrentContext 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsSetCurrentContext
helpviewer_keywords:
- JsSetCurrentContext function
ms.assetid: 603cc94c-6585-411b-89f9-c6f144e2aa30
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 57620ad0e986034791ec07765d7cc115b958d661
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564183"
---
# <span data-ttu-id="7c704-103">JsSetCurrentContext 函数</span><span class="sxs-lookup"><span data-stu-id="7c704-103">JsSetCurrentContext Function</span></span>
<span data-ttu-id="7c704-104">设置线程上的当前脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="7c704-104">Sets the current script context on the thread.</span></span>  
  
## <span data-ttu-id="7c704-105">语法</span><span class="sxs-lookup"><span data-stu-id="7c704-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsSetCurrentContext(  
   _In_ JsContextRef context  
);  
```  
  
#### <span data-ttu-id="7c704-106">参数</span><span class="sxs-lookup"><span data-stu-id="7c704-106">Parameters</span></span>  
 `context`  
 <span data-ttu-id="7c704-107">要成为最新的脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="7c704-107">The script context to make current.</span></span>  
  
## <span data-ttu-id="7c704-108">返回值</span><span class="sxs-lookup"><span data-stu-id="7c704-108">Return Value</span></span>  
 <span data-ttu-id="7c704-109">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="7c704-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  

## <span data-ttu-id="7c704-110">示例</span><span class="sxs-lookup"><span data-stu-id="7c704-110">Example</span></span>

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

## <span data-ttu-id="7c704-111">要求</span><span class="sxs-lookup"><span data-stu-id="7c704-111">Requirements</span></span>  
 <span data-ttu-id="7c704-112">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="7c704-112">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="7c704-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7c704-113">See Also</span></span>  
 [<span data-ttu-id="7c704-114">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="7c704-114">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)