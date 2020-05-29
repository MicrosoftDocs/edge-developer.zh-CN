---
description: 获取运行时的当前内存使用情况。
title: JsGetRuntimeMemoryUsage 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsGetRuntimeMemoryUsage
helpviewer_keywords:
- JsGetRuntimeMemoryUsage function
ms.assetid: b9bd4146-bfbc-4cb1-a0e9-a0ded7fb09bd
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 9ec8472132b4c50b279ee95f36995bf46c0e29e5
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563105"
---
# <span data-ttu-id="9c2cc-103">JsGetRuntimeMemoryUsage 函数</span><span class="sxs-lookup"><span data-stu-id="9c2cc-103">JsGetRuntimeMemoryUsage Function</span></span>
<span data-ttu-id="9c2cc-104">获取运行时的当前内存使用情况。</span><span class="sxs-lookup"><span data-stu-id="9c2cc-104">Gets the current memory usage for a runtime.</span></span>  
  
## <span data-ttu-id="9c2cc-105">语法</span><span class="sxs-lookup"><span data-stu-id="9c2cc-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetRuntimeMemoryUsage(  
   _In_ JsRuntimeHandle runtime,  
   _Out_ size_t *memoryUsage  
);  
```  
  
#### <span data-ttu-id="9c2cc-106">参数</span><span class="sxs-lookup"><span data-stu-id="9c2cc-106">Parameters</span></span>  
 `runtime`  
 <span data-ttu-id="9c2cc-107">要检索其内存使用情况的运行时。</span><span class="sxs-lookup"><span data-stu-id="9c2cc-107">The runtime whose memory usage is to be retrieved.</span></span>  
  
 `memoryUsage`  
 <span data-ttu-id="9c2cc-108">运行时的当前内存使用（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="9c2cc-108">The runtime's current memory usage, in bytes.</span></span>  
  
## <span data-ttu-id="9c2cc-109">返回值</span><span class="sxs-lookup"><span data-stu-id="9c2cc-109">Return Value</span></span>  
 <span data-ttu-id="9c2cc-110">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="9c2cc-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="9c2cc-111">备注</span><span class="sxs-lookup"><span data-stu-id="9c2cc-111">Remarks</span></span>  
 <span data-ttu-id="9c2cc-112">无论运行时是否在另一个线程上处于活动状态，都可以始终检索内存使用情况。</span><span class="sxs-lookup"><span data-stu-id="9c2cc-112">Memory usage can be always be retrieved, regardless of whether or not the runtime is active on another thread.</span></span>  
  
## <span data-ttu-id="9c2cc-113">要求</span><span class="sxs-lookup"><span data-stu-id="9c2cc-113">Requirements</span></span>  
 <span data-ttu-id="9c2cc-114">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="9c2cc-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="9c2cc-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9c2cc-115">See Also</span></span>  
 [<span data-ttu-id="9c2cc-116">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="9c2cc-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)