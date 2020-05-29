---
description: 创建用于运行脚本的脚本上下文。
title: JsCreateContext 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsCreateContext
helpviewer_keywords:
- JsCreateContext function
ms.assetid: aceca043-2c73-4029-a06c-8ad6695109cf
caps.latest.revision: 15
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 06bd4c4780a8c7610ebc95cfc0da058306ce5b78
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563175"
---
# <span data-ttu-id="5a674-103">JsCreateContext 函数</span><span class="sxs-lookup"><span data-stu-id="5a674-103">JsCreateContext Function</span></span>
<span data-ttu-id="5a674-104">创建用于运行脚本的脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="5a674-104">Creates a script context for running scripts.</span></span>  
  
## <span data-ttu-id="5a674-105">语法</span><span class="sxs-lookup"><span data-stu-id="5a674-105">Syntax</span></span>  
  
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
  
#### <span data-ttu-id="5a674-106">参数</span><span class="sxs-lookup"><span data-stu-id="5a674-106">Parameters</span></span>  
 `runtime`  
 <span data-ttu-id="5a674-107">正在其中创建脚本上下文的运行时。</span><span class="sxs-lookup"><span data-stu-id="5a674-107">The runtime the script context is being created in.</span></span>  
  
 `debugApplication`  
 <span data-ttu-id="5a674-108">用于调试的调试应用程序。</span><span class="sxs-lookup"><span data-stu-id="5a674-108">The debug application to use for debugging.</span></span> <span data-ttu-id="5a674-109">此参数可以为 null，在这种情况下，不会为上下文启用调试。</span><span class="sxs-lookup"><span data-stu-id="5a674-109">This parameter can be null, in which case debugging is not enabled for the context.</span></span>  
  
 `newContext`  
 <span data-ttu-id="5a674-110">创建的脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="5a674-110">The created script context.</span></span>  
  
## <span data-ttu-id="5a674-111">返回值</span><span class="sxs-lookup"><span data-stu-id="5a674-111">Return Value</span></span>  
 <span data-ttu-id="5a674-112">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="5a674-112">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="5a674-113">备注</span><span class="sxs-lookup"><span data-stu-id="5a674-113">Remarks</span></span>  
 <span data-ttu-id="5a674-114">每个脚本上下文都有自己的全局对象，该对象独立于所有其他脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="5a674-114">Each script context has its own global object that is isolated from all other script contexts.</span></span>  
  
 <span data-ttu-id="5a674-115">`debugApplication`Microsoft Edge 模式不支持该参数。</span><span class="sxs-lookup"><span data-stu-id="5a674-115">The `debugApplication` parameter is not supported in Microsoft Edge mode.</span></span> <span data-ttu-id="5a674-116">有关在 Microsoft Edge 模式中使用此 API 的详细信息，请参阅确定[Microsoft edge 与传统引擎的目标](../chakra-hosting/targeting-edge-vs-legacy-engines-in-jsrt-apis.md)。</span><span class="sxs-lookup"><span data-stu-id="5a674-116">For more information on using this API in Microsoft Edge mode, see [Targeting Microsoft Edge vs. Legacy Engines](../chakra-hosting/targeting-edge-vs-legacy-engines-in-jsrt-apis.md).</span></span>  
  
## <span data-ttu-id="5a674-117">要求</span><span class="sxs-lookup"><span data-stu-id="5a674-117">Requirements</span></span>  
 <span data-ttu-id="5a674-118">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="5a674-118">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="5a674-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5a674-119">See Also</span></span>  
 [<span data-ttu-id="5a674-120">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="5a674-120">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)