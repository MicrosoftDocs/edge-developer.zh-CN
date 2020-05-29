---
description: '设置在垃圾回收之前由运行时调用的回调函数。 '
title: JsSetRuntimeBeforeCollectCallback 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsSetRuntimeBeforeCollectCallback
helpviewer_keywords:
- JsSetRuntimeBeforeCollectCallback function
ms.assetid: 7b2fb911-6007-4ed9-a307-66cefe590ea4
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 31aefd28698c14a6fe17421a990a7c8b120876bf
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564075"
---
# <span data-ttu-id="3342c-103">JsSetRuntimeBeforeCollectCallback 函数</span><span class="sxs-lookup"><span data-stu-id="3342c-103">JsSetRuntimeBeforeCollectCallback Function</span></span>
<span data-ttu-id="3342c-104">设置在垃圾回收之前由运行时调用的回调函数。</span><span class="sxs-lookup"><span data-stu-id="3342c-104">Sets a callback function that is called by the runtime before garbage collection.</span></span>  
  
## <span data-ttu-id="3342c-105">语法</span><span class="sxs-lookup"><span data-stu-id="3342c-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsSetRuntimeBeforeCollectCallback(  
   _In_ JsRuntimeHandle runtime,  
   _In_opt_ void *callbackState,  
   _In_ JsBeforeCollectCallback beforeCollectCallback  
);  
```  
  
#### <span data-ttu-id="3342c-106">参数</span><span class="sxs-lookup"><span data-stu-id="3342c-106">Parameters</span></span>  
 `runtime`  
 <span data-ttu-id="3342c-107">要注册分配回调的运行时。</span><span class="sxs-lookup"><span data-stu-id="3342c-107">The runtime for which to register the allocation callback.</span></span>  
  
 `callbackState`  
 <span data-ttu-id="3342c-108">用户提供的状态将传回回拨。</span><span class="sxs-lookup"><span data-stu-id="3342c-108">User provided state that will be passed back to the callback.</span></span>  
  
 `beforeCollectCallback`  
 <span data-ttu-id="3342c-109">正在设置的回调函数。</span><span class="sxs-lookup"><span data-stu-id="3342c-109">The callback function being set.</span></span>  
  
## <span data-ttu-id="3342c-110">返回值</span><span class="sxs-lookup"><span data-stu-id="3342c-110">Return Value</span></span>  
 <span data-ttu-id="3342c-111">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="3342c-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="3342c-112">备注</span><span class="sxs-lookup"><span data-stu-id="3342c-112">Remarks</span></span>  
 <span data-ttu-id="3342c-113">回调将在当前运行时执行线程上调用，因此执行会被阻止，直到回调完成。</span><span class="sxs-lookup"><span data-stu-id="3342c-113">The callback is invoked on the current runtime execution thread, therefore execution is blocked until the callback completes.</span></span>  
  
 <span data-ttu-id="3342c-114">主机可使用回调准备垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="3342c-114">The callback can be used by hosts to prepare for garbage collection.</span></span> <span data-ttu-id="3342c-115">例如，通过释放 Chakra 对象上的不必要的引用。</span><span class="sxs-lookup"><span data-stu-id="3342c-115">For example, by releasing unnecessary references on Chakra objects.</span></span>  
  
## <span data-ttu-id="3342c-116">要求</span><span class="sxs-lookup"><span data-stu-id="3342c-116">Requirements</span></span>  
 <span data-ttu-id="3342c-117">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="3342c-117">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="3342c-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3342c-118">See Also</span></span>  
 [<span data-ttu-id="3342c-119">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="3342c-119">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)