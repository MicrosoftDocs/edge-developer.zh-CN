---
description: 创建用于运行脚本的脚本上下文。
title: JsCreateContext 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsCreateContext
helpviewer_keywords:
- JsCreateContext function
ms.assetid: aceca043-2c73-4029-a06c-8ad6695109cf
caps.latest.revision: 15
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 5d6c8149b8a5e5fee7cbc8dac821713b1d9649ee
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232200"
---
# <span data-ttu-id="2a179-103">JsCreateContext 函数</span><span class="sxs-lookup"><span data-stu-id="2a179-103">JsCreateContext Function</span></span>

<span data-ttu-id="2a179-104">创建用于运行脚本的脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="2a179-104">Creates a script context for running scripts.</span></span>  
  
## <span data-ttu-id="2a179-105">语法</span><span class="sxs-lookup"><span data-stu-id="2a179-105">Syntax</span></span>  
  
```cpp  
// Microsoft Edge mode signature  
STDAPI_(JsErrorCode) JsCreateContext(  
   _In_ JsRuntimeHandle runtime,  
   _Out_ JsContextRef *newContext);  
  
// Legacy mode signature  
STDAPI_(JsErrorCode) JsCreateContext(  
   _In_ JsRuntimeHandle runtime,  
   _In_ IDebugApplication *debugApplication,  
   _Out_ JsContextRef *newContext  
);  
```  
  
#### <span data-ttu-id="2a179-106">参数</span><span class="sxs-lookup"><span data-stu-id="2a179-106">Parameters</span></span>  
 `runtime`  
 <span data-ttu-id="2a179-107">创建脚本上下文的运行时。</span><span class="sxs-lookup"><span data-stu-id="2a179-107">The runtime the script context is being created in.</span></span>  
  
 `debugApplication`  
 <span data-ttu-id="2a179-108">用于调试的调试应用程序。</span><span class="sxs-lookup"><span data-stu-id="2a179-108">The debug application to use for debugging.</span></span> <span data-ttu-id="2a179-109">此参数可以是 null，在这种情况下，未为上下文启用调试。</span><span class="sxs-lookup"><span data-stu-id="2a179-109">This parameter can be null, in which case debugging is not enabled for the context.</span></span>  
  
 `newContext`  
 <span data-ttu-id="2a179-110">已创建的脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="2a179-110">The created script context.</span></span>  
  
## <span data-ttu-id="2a179-111">返回值</span><span class="sxs-lookup"><span data-stu-id="2a179-111">Return Value</span></span>  
 <span data-ttu-id="2a179-112">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="2a179-112">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="2a179-113">备注</span><span class="sxs-lookup"><span data-stu-id="2a179-113">Remarks</span></span>  
 <span data-ttu-id="2a179-114">每个脚本上下文都有自己的全局对象，该对象独立于所有其他脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="2a179-114">Each script context has its own global object that is isolated from all other script contexts.</span></span>  
  
 <span data-ttu-id="2a179-115">Microsoft `debugApplication` Edge 模式不支持此参数。</span><span class="sxs-lookup"><span data-stu-id="2a179-115">The `debugApplication` parameter is not supported in Microsoft Edge mode.</span></span> <span data-ttu-id="2a179-116">有关在 Microsoft Edge 模式下使用此 API 有关详细信息，请参阅"面向 Microsoft Edge 与[旧版引擎"。](../chakra-hosting/targeting-edge-vs-legacy-engines-in-jsrt-apis.md)</span><span class="sxs-lookup"><span data-stu-id="2a179-116">For more information on using this API in Microsoft Edge mode, see [Targeting Microsoft Edge vs. Legacy Engines](../chakra-hosting/targeting-edge-vs-legacy-engines-in-jsrt-apis.md).</span></span>  
  
## <span data-ttu-id="2a179-117">要求</span><span class="sxs-lookup"><span data-stu-id="2a179-117">Requirements</span></span>  
 <span data-ttu-id="2a179-118">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="2a179-118">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="2a179-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2a179-119">See Also</span></span>  
 [<span data-ttu-id="2a179-120">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="2a179-120">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
