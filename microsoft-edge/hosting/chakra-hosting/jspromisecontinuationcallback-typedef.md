---
description: 承诺延续回调。
title: JsPromiseContinuationCallback Typedef |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 51a3fd02-9668-4cf7-bb0b-e1fd03b2528f
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 023d88af5ff82056d8f57453e0a53b91b34565a6
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563070"
---
# <span data-ttu-id="9b50d-103">JsPromiseContinuationCallback Typedef</span><span class="sxs-lookup"><span data-stu-id="9b50d-103">JsPromiseContinuationCallback Typedef</span></span>
<span data-ttu-id="9b50d-104">承诺延续回调。</span><span class="sxs-lookup"><span data-stu-id="9b50d-104">A promise continuation callback.</span></span>  
  
## <span data-ttu-id="9b50d-105">语法</span><span class="sxs-lookup"><span data-stu-id="9b50d-105">Syntax</span></span>  
  
```cpp  
typedef void (CALLBACK *JsPromiseContinuationCallback)(  
  _In_ JsValueRef task,  
  _In_opt_ void *callbackState  
);  
```  
  
#### <span data-ttu-id="9b50d-106">参数</span><span class="sxs-lookup"><span data-stu-id="9b50d-106">Parameters</span></span>  
 `task`  
  `callbackState`  
  
## <span data-ttu-id="9b50d-107">备注</span><span class="sxs-lookup"><span data-stu-id="9b50d-107">Remarks</span></span>  
 <span data-ttu-id="9b50d-108">主机可以在中指定承诺延续回调 `JsSetPromiseContinuationCallback` 。</span><span class="sxs-lookup"><span data-stu-id="9b50d-108">The host can specify a promise continuation callback in `JsSetPromiseContinuationCallback`.</span></span> <span data-ttu-id="9b50d-109">如果脚本创建了一个要在以后运行的任务，则将使用该任务调用承诺延续回调，并且应将任务放在一个 FIFO 队列中，以便在当前脚本完成执行时运行。</span><span class="sxs-lookup"><span data-stu-id="9b50d-109">If a script creates a task to be run later, then the promise continuation callback will be called with the task and the task should be put in a FIFO queue, to be run when the current script is done executing.</span></span>  
  
 <span data-ttu-id="9b50d-110">此 API 仅在 EdgeHTML 模式下受支持。</span><span class="sxs-lookup"><span data-stu-id="9b50d-110">This API is supported only in EdgeHTML mode.</span></span>  
  
## <span data-ttu-id="9b50d-111">要求</span><span class="sxs-lookup"><span data-stu-id="9b50d-111">Requirements</span></span>  
 <span data-ttu-id="9b50d-112">jsrt</span><span class="sxs-lookup"><span data-stu-id="9b50d-112">jsrt.h</span></span>  
  
## <span data-ttu-id="9b50d-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9b50d-113">See Also</span></span>  
 [<span data-ttu-id="9b50d-114">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="9b50d-114">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)