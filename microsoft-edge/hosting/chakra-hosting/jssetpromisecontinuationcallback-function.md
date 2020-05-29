---
description: 设置当任务需要排队以供将来执行时，上下文调用的承诺延续回调函数。
title: JsSetPromiseContinuationCallback 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 6ef0faf4-1500-4bd9-aeca-c208492af8ea
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 9438bf05d879b0c2014c0a4d49d374d26eff3fb4
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564169"
---
# <span data-ttu-id="74960-103">JsSetPromiseContinuationCallback 函数</span><span class="sxs-lookup"><span data-stu-id="74960-103">JsSetPromiseContinuationCallback Function</span></span>
<span data-ttu-id="74960-104">设置当任务需要排队以供将来执行时，上下文调用的承诺延续回调函数。</span><span class="sxs-lookup"><span data-stu-id="74960-104">Sets a promise continuation callback function that is called by the context when a task needs to be queued for future execution.</span></span>  
  
## <span data-ttu-id="74960-105">语法</span><span class="sxs-lookup"><span data-stu-id="74960-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsSetPromiseContinuationCallback(  
   _In_ JsPromiseContinuationCallback promiseContinuationCallback,  
   _In_opt_ void *callbackState  
);  
```  
  
#### <span data-ttu-id="74960-106">参数</span><span class="sxs-lookup"><span data-stu-id="74960-106">Parameters</span></span>  
 `promiseContinuationCallback`  
 <span data-ttu-id="74960-107">正在设置的回调函数。</span><span class="sxs-lookup"><span data-stu-id="74960-107">The callback function being set.</span></span>  
  
 `callbackState`  
 <span data-ttu-id="74960-108">用户提供的状态将传回回拨。</span><span class="sxs-lookup"><span data-stu-id="74960-108">User provided state that will be passed back to the callback.</span></span>  
  
## <span data-ttu-id="74960-109">返回值</span><span class="sxs-lookup"><span data-stu-id="74960-109">Return Value</span></span>  
 <span data-ttu-id="74960-110">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="74960-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="74960-111">备注</span><span class="sxs-lookup"><span data-stu-id="74960-111">Remarks</span></span>  
 <span data-ttu-id="74960-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="74960-112">Requires an active script context.</span></span>  
  
 <span data-ttu-id="74960-113">此 API 仅在 EdgeHTML 模式下受支持。</span><span class="sxs-lookup"><span data-stu-id="74960-113">This API is supported only in EdgeHTML mode.</span></span>  
  
## <span data-ttu-id="74960-114">要求</span><span class="sxs-lookup"><span data-stu-id="74960-114">Requirements</span></span>  
 <span data-ttu-id="74960-115">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="74960-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="74960-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="74960-116">See Also</span></span>  
 [<span data-ttu-id="74960-117">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="74960-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)