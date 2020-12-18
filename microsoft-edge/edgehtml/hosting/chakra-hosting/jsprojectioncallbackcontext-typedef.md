---
description: 从 JsRT 传递到应用程序回调 JsProjectionEnqueueCallback 的上下文，然后由正确线程上的应用程序在提供的回调中传递回 `JsProjectionCallback` JsRT。
title: JsProjectionCallbackContext Typedef |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 50c705c5-664f-4a1a-92f6-4882fc718ab1
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 7742b0186a49e99f2738b81357b9e55cfe00042b
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232523"
---
# <span data-ttu-id="84e86-103">JsProjectionCallbackContext Typedef</span><span class="sxs-lookup"><span data-stu-id="84e86-103">JsProjectionCallbackContext Typedef</span></span>

<span data-ttu-id="84e86-104">从 JsRT 传递到应用程序回调 JsProjectionEnqueueCallback 的上下文，然后由正确线程上的应用程序在提供的回调中传递回 `JsProjectionCallback` JsRT。</span><span class="sxs-lookup"><span data-stu-id="84e86-104">The context passed into application callback, JsProjectionEnqueueCallback, from JsRT and then passed back to JsRT in the provided callback, `JsProjectionCallback`, by the application on the correct thread.</span></span>  
  
## <span data-ttu-id="84e86-105">语法</span><span class="sxs-lookup"><span data-stu-id="84e86-105">Syntax</span></span>  
  
```cpp  
typedef void *JsProjectionCallbackContext;  
```  
  
## <span data-ttu-id="84e86-106">备注</span><span class="sxs-lookup"><span data-stu-id="84e86-106">Remarks</span></span>  
 <span data-ttu-id="84e86-107">需要调用 `JsSetProjectionEnqueueCallback` 以接收回调。</span><span class="sxs-lookup"><span data-stu-id="84e86-107">Requires calling `JsSetProjectionEnqueueCallback` to receive callbacks.</span></span>  
  
 <span data-ttu-id="84e86-108">此 API 仅在 EdgeHTML 模式下受支持。</span><span class="sxs-lookup"><span data-stu-id="84e86-108">This API is supported only in EdgeHTML mode.</span></span>  
  
## <span data-ttu-id="84e86-109">要求</span><span class="sxs-lookup"><span data-stu-id="84e86-109">Requirements</span></span>  
 <span data-ttu-id="84e86-110">jsrt.h</span><span class="sxs-lookup"><span data-stu-id="84e86-110">jsrt.h</span></span>  
  
## <span data-ttu-id="84e86-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="84e86-111">See Also</span></span>  
 [<span data-ttu-id="84e86-112">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="84e86-112">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
