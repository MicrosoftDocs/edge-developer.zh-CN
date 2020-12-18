---
description: 设置一个回调函数，该函数在对象垃圾回收之前由运行时调用。
title: JsSetObjectBeforeCollectCallback 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: ea2cbd94-d8b0-4fa9-a4a1-c75a4e338eaf
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 4689184dccaf6bc9f98eeacda5f5a4b91a927d40
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232185"
---
# <span data-ttu-id="43e20-103">JsSetObjectBeforeCollectCallback 函数</span><span class="sxs-lookup"><span data-stu-id="43e20-103">JsSetObjectBeforeCollectCallback Function</span></span>

<span data-ttu-id="43e20-104">设置一个回调函数，该函数在对象垃圾回收之前由运行时调用。</span><span class="sxs-lookup"><span data-stu-id="43e20-104">Sets a callback function that is called by the runtime before garbage collection of an object.</span></span>  
  
## <span data-ttu-id="43e20-105">语法</span><span class="sxs-lookup"><span data-stu-id="43e20-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsSetObjectBeforeCollectCallback(  
   _In_ JsRef ref,  
   _In_opt_ void *callbackState,  
   _In_ JsObjectBeforeCollectCallback objectBeforeCollectCallback  
);  
```  
  
#### <span data-ttu-id="43e20-106">参数</span><span class="sxs-lookup"><span data-stu-id="43e20-106">Parameters</span></span>  
 `ref`  
 <span data-ttu-id="43e20-107">要注册回调的对象。</span><span class="sxs-lookup"><span data-stu-id="43e20-107">The object for which to register the callback.</span></span>  
  
 `callbackState`  
 <span data-ttu-id="43e20-108">将传递回回调的用户提供的状态。</span><span class="sxs-lookup"><span data-stu-id="43e20-108">User-provided state that will be passed back to the callback.</span></span>  
  
 `objectBeforeCollectCallback`  
 <span data-ttu-id="43e20-109">正在设置的回调函数。</span><span class="sxs-lookup"><span data-stu-id="43e20-109">The callback function being set.</span></span> <span data-ttu-id="43e20-110">使用 null 清除以前注册的回调。</span><span class="sxs-lookup"><span data-stu-id="43e20-110">Use null to clear previously registered callback.</span></span>  
  
## <span data-ttu-id="43e20-111">返回值</span><span class="sxs-lookup"><span data-stu-id="43e20-111">Return Value</span></span>  
 <span data-ttu-id="43e20-112">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="43e20-112">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="43e20-113">备注</span><span class="sxs-lookup"><span data-stu-id="43e20-113">Remarks</span></span>  
 <span data-ttu-id="43e20-114">在当前运行时执行线程上调用回调，因此在回调完成之前将阻止执行。</span><span class="sxs-lookup"><span data-stu-id="43e20-114">The callback is invoked on the current runtime execution thread, therefore execution is blocked until the callback completes.</span></span>  
  
 <span data-ttu-id="43e20-115">此 API 仅在 EdgeHTML 模式下受支持。</span><span class="sxs-lookup"><span data-stu-id="43e20-115">This API is supported only in EdgeHTML mode.</span></span>  
  
## <span data-ttu-id="43e20-116">要求</span><span class="sxs-lookup"><span data-stu-id="43e20-116">Requirements</span></span>  
 <span data-ttu-id="43e20-117">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="43e20-117">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="43e20-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="43e20-118">See Also</span></span>  
 [<span data-ttu-id="43e20-119">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="43e20-119">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
