---
description: 当投影 API 在不同于原始线程的线程上完成时由 JsRT 调用的应用程序回调。
title: JsProjectionEnqueueCallback Typedef |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 19c1cefb-a7be-4196-b780-9fe6adf35ba5
caps.latest.revision: 4
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 47527d5e32076e40a82ab5452c2e0f624e8a2818
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232762"
---
# <span data-ttu-id="526ee-103">JsProjectionEnqueueCallback Typedef</span><span class="sxs-lookup"><span data-stu-id="526ee-103">JsProjectionEnqueueCallback Typedef</span></span>

<span data-ttu-id="526ee-104">当投影 API 在不同于原始线程的线程上完成时由 JsRT 调用的应用程序回调。</span><span class="sxs-lookup"><span data-stu-id="526ee-104">The application callback which is called by JsRT when a projection API is completed on a different thread than the original.</span></span>  
  
## <span data-ttu-id="526ee-105">语法</span><span class="sxs-lookup"><span data-stu-id="526ee-105">Syntax</span></span>  
  
```cpp  
typedef void (CALLBACK *JsProjectionEnqueueCallback)(  
  _In_ JsProjectionCallback jsCallback,  
  _In_ JsProjectionCallbackContext jsContext,  
  _In_opt_ void *callbackState  
);  
```  
  
#### <span data-ttu-id="526ee-106">参数</span><span class="sxs-lookup"><span data-stu-id="526ee-106">Parameters</span></span>  
 `jsCallback`  
 <span data-ttu-id="526ee-107">在原始线程上调用的回调。</span><span class="sxs-lookup"><span data-stu-id="526ee-107">The callback to be invoked on the original thread.</span></span>  
  
 `jsContext`  
 <span data-ttu-id="526ee-108">应用程序上下文。</span><span class="sxs-lookup"><span data-stu-id="526ee-108">The applications context.</span></span>  
  
 `callbackState`  
 <span data-ttu-id="526ee-109">必须传递到的 JsRT 上下文 `jsCallback` 。</span><span class="sxs-lookup"><span data-stu-id="526ee-109">The JsRT context that must be passed into `jsCallback`.</span></span>  
  
## <span data-ttu-id="526ee-110">备注</span><span class="sxs-lookup"><span data-stu-id="526ee-110">Remarks</span></span>  
 <span data-ttu-id="526ee-111">需要调用 JsSetProjectionEnqueueCallback 以接收回调。</span><span class="sxs-lookup"><span data-stu-id="526ee-111">Requires calling JsSetProjectionEnqueueCallback to receive callbacks.</span></span>  
  
 <span data-ttu-id="526ee-112">此 API 仅在 EdgeHTML 模式下受支持。</span><span class="sxs-lookup"><span data-stu-id="526ee-112">This API is supported only in EdgeHTML mode.</span></span>  
  
## <span data-ttu-id="526ee-113">要求</span><span class="sxs-lookup"><span data-stu-id="526ee-113">Requirements</span></span>  
 <span data-ttu-id="526ee-114">jsrt.h</span><span class="sxs-lookup"><span data-stu-id="526ee-114">jsrt.h</span></span>  
  
## <span data-ttu-id="526ee-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="526ee-115">See Also</span></span>  
 [<span data-ttu-id="526ee-116">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="526ee-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
