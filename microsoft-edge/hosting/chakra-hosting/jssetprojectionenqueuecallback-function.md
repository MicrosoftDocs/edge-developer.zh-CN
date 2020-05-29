---
description: 设置要使用的回调，以便将投影完成调用回调用方所需的线程。
title: JsSetProjectionEnqueueCallback 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: c751ccef-20d2-4d41-9568-1c54adf47cdf
caps.latest.revision: 4
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 02da0238360b0dc6fff9bb86c9f5ab04d1ba7112
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564168"
---
# <span data-ttu-id="493b1-103">JsSetProjectionEnqueueCallback 函数</span><span class="sxs-lookup"><span data-stu-id="493b1-103">JsSetProjectionEnqueueCallback Function</span></span>
<span data-ttu-id="493b1-104">设置要使用的回调，以便将投影完成调用回调用方所需的线程。</span><span class="sxs-lookup"><span data-stu-id="493b1-104">Sets the callback to be used in order to invoke a projection completion back to the callers required thread.</span></span>  
  
## <span data-ttu-id="493b1-105">语法</span><span class="sxs-lookup"><span data-stu-id="493b1-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsSetProjectionEnqueueCallback(  
   _In_ JsProjectionEnqueueCallback projectionEnqueueCallback,  
   _In_opt_ void *projectionEnqueueContext);  
  
```  
  
#### <span data-ttu-id="493b1-106">参数</span><span class="sxs-lookup"><span data-stu-id="493b1-106">Parameters</span></span>  
 `projectionEnqueueContext`  
 <span data-ttu-id="493b1-107">任何时候在后台线程上发生投影完成时将调用的回调。</span><span class="sxs-lookup"><span data-stu-id="493b1-107">The callback that will be invoked any time a projection completion occurs on a background thread.</span></span>  
  
 `callbackState`  
 <span data-ttu-id="493b1-108">提供给的应用程序上下文 `projectionEnqueueContext` 。</span><span class="sxs-lookup"><span data-stu-id="493b1-108">The application context provided to `projectionEnqueueContext`.</span></span>  
  
## <span data-ttu-id="493b1-109">返回值</span><span class="sxs-lookup"><span data-stu-id="493b1-109">Return Value</span></span>  
 <span data-ttu-id="493b1-110">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="493b1-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="493b1-111">备注</span><span class="sxs-lookup"><span data-stu-id="493b1-111">Remarks</span></span>  
 <span data-ttu-id="493b1-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="493b1-112">Requires an active script context.</span></span>  
  
 <span data-ttu-id="493b1-113">该调用应来自不同的 COM 单元或来自同一 MTA 中的不同线程。</span><span class="sxs-lookup"><span data-stu-id="493b1-113">The call should be coming from a different COM apartment or from a different thread in the same MTA.</span></span>  
  
 <span data-ttu-id="493b1-114">此 API 仅在 EdgeHTML 模式下受支持。</span><span class="sxs-lookup"><span data-stu-id="493b1-114">This API is supported only in EdgeHTML mode.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="493b1-115">此 API 目前不支持 PInvoke。</span><span class="sxs-lookup"><span data-stu-id="493b1-115">PInvoke is not currently supported for this API.</span></span>  
  
## <span data-ttu-id="493b1-116">要求</span><span class="sxs-lookup"><span data-stu-id="493b1-116">Requirements</span></span>  
 <span data-ttu-id="493b1-117">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="493b1-117">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="493b1-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="493b1-118">See Also</span></span>  
 [<span data-ttu-id="493b1-119">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="493b1-119">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)