---
description: 设置要用于将投影完成调用回调用方所需线程的回调。
title: JsSetProjectionEnqueueCallback 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: c751ccef-20d2-4d41-9568-1c54adf47cdf
caps.latest.revision: 4
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 7dfedfeb1df5a97159a211795a2dd072d239bb35
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232181"
---
# <span data-ttu-id="172c3-103">JsSetProjectionEnqueueCallback 函数</span><span class="sxs-lookup"><span data-stu-id="172c3-103">JsSetProjectionEnqueueCallback Function</span></span>

<span data-ttu-id="172c3-104">设置要用于将投影完成调用回调用方所需线程的回调。</span><span class="sxs-lookup"><span data-stu-id="172c3-104">Sets the callback to be used in order to invoke a projection completion back to the callers required thread.</span></span>  
  
## <span data-ttu-id="172c3-105">语法</span><span class="sxs-lookup"><span data-stu-id="172c3-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsSetProjectionEnqueueCallback(  
   _In_ JsProjectionEnqueueCallback projectionEnqueueCallback,  
   _In_opt_ void *projectionEnqueueContext);  
  
```  
  
#### <span data-ttu-id="172c3-106">参数</span><span class="sxs-lookup"><span data-stu-id="172c3-106">Parameters</span></span>  
 `projectionEnqueueContext`  
 <span data-ttu-id="172c3-107">每次在后台线程上执行投影完成时将调用的回调。</span><span class="sxs-lookup"><span data-stu-id="172c3-107">The callback that will be invoked any time a projection completion occurs on a background thread.</span></span>  
  
 `callbackState`  
 <span data-ttu-id="172c3-108">提供给的应用程序上下文 `projectionEnqueueContext` 。</span><span class="sxs-lookup"><span data-stu-id="172c3-108">The application context provided to `projectionEnqueueContext`.</span></span>  
  
## <span data-ttu-id="172c3-109">返回值</span><span class="sxs-lookup"><span data-stu-id="172c3-109">Return Value</span></span>  
 <span data-ttu-id="172c3-110">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="172c3-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="172c3-111">备注</span><span class="sxs-lookup"><span data-stu-id="172c3-111">Remarks</span></span>  
 <span data-ttu-id="172c3-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="172c3-112">Requires an active script context.</span></span>  
  
 <span data-ttu-id="172c3-113">该调用应来自不同的 COM 单元或来自同一 MTA 中的不同线程。</span><span class="sxs-lookup"><span data-stu-id="172c3-113">The call should be coming from a different COM apartment or from a different thread in the same MTA.</span></span>  
  
 <span data-ttu-id="172c3-114">此 API 仅在 EdgeHTML 模式下受支持。</span><span class="sxs-lookup"><span data-stu-id="172c3-114">This API is supported only in EdgeHTML mode.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="172c3-115">此 API 当前不支持 PInvoke。</span><span class="sxs-lookup"><span data-stu-id="172c3-115">PInvoke is not currently supported for this API.</span></span>  
  
## <span data-ttu-id="172c3-116">要求</span><span class="sxs-lookup"><span data-stu-id="172c3-116">Requirements</span></span>  
 <span data-ttu-id="172c3-117">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="172c3-117">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="172c3-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="172c3-118">See Also</span></span>  
 [<span data-ttu-id="172c3-119">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="172c3-119">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
