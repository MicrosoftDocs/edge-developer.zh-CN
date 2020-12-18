---
description: '设置垃圾回收前运行时调用的回调函数。 '
title: JsSetRuntimeBeforeCollectCallback 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsSetRuntimeBeforeCollectCallback
helpviewer_keywords:
- JsSetRuntimeBeforeCollectCallback function
ms.assetid: 7b2fb911-6007-4ed9-a307-66cefe590ea4
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 94ad29fcfb778fc630d70664f917c6b5c2637dde
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232186"
---
# <span data-ttu-id="6f8fc-103">JsSetRuntimeBeforeCollectCallback 函数</span><span class="sxs-lookup"><span data-stu-id="6f8fc-103">JsSetRuntimeBeforeCollectCallback Function</span></span>

<span data-ttu-id="6f8fc-104">设置垃圾回收前运行时调用的回调函数。</span><span class="sxs-lookup"><span data-stu-id="6f8fc-104">Sets a callback function that is called by the runtime before garbage collection.</span></span>  
  
## <span data-ttu-id="6f8fc-105">语法</span><span class="sxs-lookup"><span data-stu-id="6f8fc-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsSetRuntimeBeforeCollectCallback(  
   _In_ JsRuntimeHandle runtime,  
   _In_opt_ void *callbackState,  
   _In_ JsBeforeCollectCallback beforeCollectCallback  
);  
```  
  
#### <span data-ttu-id="6f8fc-106">参数</span><span class="sxs-lookup"><span data-stu-id="6f8fc-106">Parameters</span></span>  
 `runtime`  
 <span data-ttu-id="6f8fc-107">要注册其分配回调的运行时。</span><span class="sxs-lookup"><span data-stu-id="6f8fc-107">The runtime for which to register the allocation callback.</span></span>  
  
 `callbackState`  
 <span data-ttu-id="6f8fc-108">用户提供的状态将传递回回调。</span><span class="sxs-lookup"><span data-stu-id="6f8fc-108">User provided state that will be passed back to the callback.</span></span>  
  
 `beforeCollectCallback`  
 <span data-ttu-id="6f8fc-109">正在设置的回调函数。</span><span class="sxs-lookup"><span data-stu-id="6f8fc-109">The callback function being set.</span></span>  
  
## <span data-ttu-id="6f8fc-110">返回值</span><span class="sxs-lookup"><span data-stu-id="6f8fc-110">Return Value</span></span>  
 <span data-ttu-id="6f8fc-111">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="6f8fc-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="6f8fc-112">备注</span><span class="sxs-lookup"><span data-stu-id="6f8fc-112">Remarks</span></span>  
 <span data-ttu-id="6f8fc-113">在当前运行时执行线程上调用回调，因此在回调完成之前将阻止执行。</span><span class="sxs-lookup"><span data-stu-id="6f8fc-113">The callback is invoked on the current runtime execution thread, therefore execution is blocked until the callback completes.</span></span>  
  
 <span data-ttu-id="6f8fc-114">主机可以使用回调来准备垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="6f8fc-114">The callback can be used by hosts to prepare for garbage collection.</span></span> <span data-ttu-id="6f8fc-115">例如，通过释放对 Chakra 对象不必要的引用。</span><span class="sxs-lookup"><span data-stu-id="6f8fc-115">For example, by releasing unnecessary references on Chakra objects.</span></span>  
  
## <span data-ttu-id="6f8fc-116">要求</span><span class="sxs-lookup"><span data-stu-id="6f8fc-116">Requirements</span></span>  
 <span data-ttu-id="6f8fc-117">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="6f8fc-117">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="6f8fc-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6f8fc-118">See Also</span></span>  
 [<span data-ttu-id="6f8fc-119">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="6f8fc-119">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
