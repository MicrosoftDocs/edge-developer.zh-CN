---
description: 承诺延续回调。
title: JsPromiseContinuationCallback Typedef |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 51a3fd02-9668-4cf7-bb0b-e1fd03b2528f
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: da121d186cd9d0ab1a9770be08c9a92b52cf3366
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232760"
---
# <span data-ttu-id="ae8d8-103">JsPromiseContinuationCallback Typedef</span><span class="sxs-lookup"><span data-stu-id="ae8d8-103">JsPromiseContinuationCallback Typedef</span></span>

<span data-ttu-id="ae8d8-104">承诺延续回调。</span><span class="sxs-lookup"><span data-stu-id="ae8d8-104">A promise continuation callback.</span></span>  
  
## <span data-ttu-id="ae8d8-105">语法</span><span class="sxs-lookup"><span data-stu-id="ae8d8-105">Syntax</span></span>  
  
```cpp  
typedef void (CALLBACK *JsPromiseContinuationCallback)(  
  _In_ JsValueRef task,  
  _In_opt_ void *callbackState  
);  
```  
  
#### <span data-ttu-id="ae8d8-106">参数</span><span class="sxs-lookup"><span data-stu-id="ae8d8-106">Parameters</span></span>  
 `task`  
  `callbackState`  
  
## <span data-ttu-id="ae8d8-107">备注</span><span class="sxs-lookup"><span data-stu-id="ae8d8-107">Remarks</span></span>  
 <span data-ttu-id="ae8d8-108">主机可以在 中指定承诺延续回调 `JsSetPromiseContinuationCallback` 。</span><span class="sxs-lookup"><span data-stu-id="ae8d8-108">The host can specify a promise continuation callback in `JsSetPromiseContinuationCallback`.</span></span> <span data-ttu-id="ae8d8-109">如果脚本创建要稍后运行的任务，则承诺延续回调将随任务一起调用，并且该任务应放入 FIFO 队列中，以在当前脚本执行完成时运行。</span><span class="sxs-lookup"><span data-stu-id="ae8d8-109">If a script creates a task to be run later, then the promise continuation callback will be called with the task and the task should be put in a FIFO queue, to be run when the current script is done executing.</span></span>  
  
 <span data-ttu-id="ae8d8-110">此 API 仅在 EdgeHTML 模式下受支持。</span><span class="sxs-lookup"><span data-stu-id="ae8d8-110">This API is supported only in EdgeHTML mode.</span></span>  
  
## <span data-ttu-id="ae8d8-111">要求</span><span class="sxs-lookup"><span data-stu-id="ae8d8-111">Requirements</span></span>  
 <span data-ttu-id="ae8d8-112">jsrt.h</span><span class="sxs-lookup"><span data-stu-id="ae8d8-112">jsrt.h</span></span>  
  
## <span data-ttu-id="ae8d8-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ae8d8-113">See Also</span></span>  
 [<span data-ttu-id="ae8d8-114">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="ae8d8-114">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
