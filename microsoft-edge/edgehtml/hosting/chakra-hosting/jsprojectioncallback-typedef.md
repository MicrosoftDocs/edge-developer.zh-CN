---
description: 应在正确的线程上传递上下文时调用的 JsRT `JsProjectionEnqueueCallback` 回调。
title: JsProjectionCallback Typedef |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 32f22d37-e57e-4196-b6cd-a3fc75bd0632
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 211325b536dc84340974b02973f1de9d5749a60a
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232527"
---
# <span data-ttu-id="f0850-103">JsProjectionCallback Typedef</span><span class="sxs-lookup"><span data-stu-id="f0850-103">JsProjectionCallback Typedef</span></span>

<span data-ttu-id="f0850-104">应在正确的线程上传递上下文时调用的 JsRT `JsProjectionEnqueueCallback` 回调。</span><span class="sxs-lookup"><span data-stu-id="f0850-104">The JsRT callback which should be called with the context passed to `JsProjectionEnqueueCallback` on the correct thread.</span></span>  
  
## <span data-ttu-id="f0850-105">语法</span><span class="sxs-lookup"><span data-stu-id="f0850-105">Syntax</span></span>  
  
```cpp  
typedef void (CALLBACK *JsProjectionCallback)(  
  _In_ JsProjectionCallbackContext jsContext  
);  
```  
  
#### <span data-ttu-id="f0850-106">参数</span><span class="sxs-lookup"><span data-stu-id="f0850-106">Parameters</span></span>  
 `jsContext`  
 <span data-ttu-id="f0850-107">需要调用 `JsSetProjectionEnqueueCallback` 以接收回调。</span><span class="sxs-lookup"><span data-stu-id="f0850-107">Requires calling `JsSetProjectionEnqueueCallback` to receive callbacks.</span></span>  
  
## <span data-ttu-id="f0850-108">备注</span><span class="sxs-lookup"><span data-stu-id="f0850-108">Remarks</span></span>  
 <span data-ttu-id="f0850-109">此 API 仅在 EdgeHTML 模式下受支持。</span><span class="sxs-lookup"><span data-stu-id="f0850-109">This API is supported only in EdgeHTML mode.</span></span>  
  
## <span data-ttu-id="f0850-110">要求</span><span class="sxs-lookup"><span data-stu-id="f0850-110">Requirements</span></span>  
 <span data-ttu-id="f0850-111">jsrt.h</span><span class="sxs-lookup"><span data-stu-id="f0850-111">jsrt.h</span></span>  
  
## <span data-ttu-id="f0850-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f0850-112">See Also</span></span>  
 [<span data-ttu-id="f0850-113">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="f0850-113">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
