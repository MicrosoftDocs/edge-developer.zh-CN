---
description: 当投影 API 在与原始线程不同的线程上完成时，由 JsRT 调用的应用程序回调。
title: JsProjectionEnqueueCallback Typedef |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 19c1cefb-a7be-4196-b780-9fe6adf35ba5
caps.latest.revision: 4
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 064a7d1077ae5222e44ab08ebe0592bb97b1f2af
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563076"
---
# <span data-ttu-id="b0d7f-103">JsProjectionEnqueueCallback Typedef</span><span class="sxs-lookup"><span data-stu-id="b0d7f-103">JsProjectionEnqueueCallback Typedef</span></span>
<span data-ttu-id="b0d7f-104">当投影 API 在与原始线程不同的线程上完成时，由 JsRT 调用的应用程序回调。</span><span class="sxs-lookup"><span data-stu-id="b0d7f-104">The application callback which is called by JsRT when a projection API is completed on a different thread than the original.</span></span>  
  
## <span data-ttu-id="b0d7f-105">语法</span><span class="sxs-lookup"><span data-stu-id="b0d7f-105">Syntax</span></span>  
  
```cpp  
typedef void (CALLBACK *JsProjectionEnqueueCallback)(  
  _In_ JsProjectionCallback jsCallback,  
  _In_ JsProjectionCallbackContext jsContext,  
  _In_opt_ void *callbackState  
);  
```  
  
#### <span data-ttu-id="b0d7f-106">参数</span><span class="sxs-lookup"><span data-stu-id="b0d7f-106">Parameters</span></span>  
 `jsCallback`  
 <span data-ttu-id="b0d7f-107">要在原始线程上调用的回调。</span><span class="sxs-lookup"><span data-stu-id="b0d7f-107">The callback to be invoked on the original thread.</span></span>  
  
 `jsContext`  
 <span data-ttu-id="b0d7f-108">应用程序上下文。</span><span class="sxs-lookup"><span data-stu-id="b0d7f-108">The applications context.</span></span>  
  
 `callbackState`  
 <span data-ttu-id="b0d7f-109">必须传递到的 JsRT 上下文 `jsCallback` 。</span><span class="sxs-lookup"><span data-stu-id="b0d7f-109">The JsRT context that must be passed into `jsCallback`.</span></span>  
  
## <span data-ttu-id="b0d7f-110">备注</span><span class="sxs-lookup"><span data-stu-id="b0d7f-110">Remarks</span></span>  
 <span data-ttu-id="b0d7f-111">需要调用 JsSetProjectionEnqueueCallback 才能接收回调。</span><span class="sxs-lookup"><span data-stu-id="b0d7f-111">Requires calling JsSetProjectionEnqueueCallback to receive callbacks.</span></span>  
  
 <span data-ttu-id="b0d7f-112">此 API 仅在 EdgeHTML 模式下受支持。</span><span class="sxs-lookup"><span data-stu-id="b0d7f-112">This API is supported only in EdgeHTML mode.</span></span>  
  
## <span data-ttu-id="b0d7f-113">要求</span><span class="sxs-lookup"><span data-stu-id="b0d7f-113">Requirements</span></span>  
 <span data-ttu-id="b0d7f-114">jsrt</span><span class="sxs-lookup"><span data-stu-id="b0d7f-114">jsrt.h</span></span>  
  
## <span data-ttu-id="b0d7f-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b0d7f-115">See Also</span></span>  
 [<span data-ttu-id="b0d7f-116">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="b0d7f-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)