---
description: 设置一个承诺延续回调函数，该函数在任务需要排队等待将来执行时由上下文调用。
title: JsSetPromiseContinuationCallback 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 6ef0faf4-1500-4bd9-aeca-c208492af8ea
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: da928431f05831c95d5bc116dbd129de9cb5f3b4
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232436"
---
# <span data-ttu-id="c126c-103">JsSetPromiseContinuationCallback 函数</span><span class="sxs-lookup"><span data-stu-id="c126c-103">JsSetPromiseContinuationCallback Function</span></span>

<span data-ttu-id="c126c-104">设置一个承诺延续回调函数，该函数在任务需要排队等待将来执行时由上下文调用。</span><span class="sxs-lookup"><span data-stu-id="c126c-104">Sets a promise continuation callback function that is called by the context when a task needs to be queued for future execution.</span></span>  
  
## <span data-ttu-id="c126c-105">语法</span><span class="sxs-lookup"><span data-stu-id="c126c-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsSetPromiseContinuationCallback(  
   _In_ JsPromiseContinuationCallback promiseContinuationCallback,  
   _In_opt_ void *callbackState  
);  
```  
  
#### <span data-ttu-id="c126c-106">参数</span><span class="sxs-lookup"><span data-stu-id="c126c-106">Parameters</span></span>  
 `promiseContinuationCallback`  
 <span data-ttu-id="c126c-107">正在设置的回调函数。</span><span class="sxs-lookup"><span data-stu-id="c126c-107">The callback function being set.</span></span>  
  
 `callbackState`  
 <span data-ttu-id="c126c-108">用户提供的状态将传递回回调。</span><span class="sxs-lookup"><span data-stu-id="c126c-108">User provided state that will be passed back to the callback.</span></span>  
  
## <span data-ttu-id="c126c-109">返回值</span><span class="sxs-lookup"><span data-stu-id="c126c-109">Return Value</span></span>  
 <span data-ttu-id="c126c-110">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="c126c-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="c126c-111">备注</span><span class="sxs-lookup"><span data-stu-id="c126c-111">Remarks</span></span>  
 <span data-ttu-id="c126c-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="c126c-112">Requires an active script context.</span></span>  
  
 <span data-ttu-id="c126c-113">此 API 仅在 EdgeHTML 模式下受支持。</span><span class="sxs-lookup"><span data-stu-id="c126c-113">This API is supported only in EdgeHTML mode.</span></span>  
  
## <span data-ttu-id="c126c-114">要求</span><span class="sxs-lookup"><span data-stu-id="c126c-114">Requirements</span></span>  
 <span data-ttu-id="c126c-115">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="c126c-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="c126c-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c126c-116">See Also</span></span>  
 [<span data-ttu-id="c126c-117">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="c126c-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
