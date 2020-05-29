---
description: 传递到应用程序回调、JsProjectionEnqueueCallback、JsRT 的上下文，然后 `JsProjectionCallback` 通过应用程序在正确的线程上传回 JsRT。
title: JsProjectionCallbackContext Typedef |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 50c705c5-664f-4a1a-92f6-4882fc718ab1
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 58d4c74da13ae0dd269f3c101bbf3d2b95e77732
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563078"
---
# <span data-ttu-id="bf58f-103">JsProjectionCallbackContext Typedef</span><span class="sxs-lookup"><span data-stu-id="bf58f-103">JsProjectionCallbackContext Typedef</span></span>
<span data-ttu-id="bf58f-104">传递到应用程序回调、JsProjectionEnqueueCallback、JsRT 的上下文，然后 `JsProjectionCallback` 通过应用程序在正确的线程上传回 JsRT。</span><span class="sxs-lookup"><span data-stu-id="bf58f-104">The context passed into application callback, JsProjectionEnqueueCallback, from JsRT and then passed back to JsRT in the provided callback, `JsProjectionCallback`, by the application on the correct thread.</span></span>  
  
## <span data-ttu-id="bf58f-105">语法</span><span class="sxs-lookup"><span data-stu-id="bf58f-105">Syntax</span></span>  
  
```cpp  
typedef void *JsProjectionCallbackContext;  
```  
  
## <span data-ttu-id="bf58f-106">备注</span><span class="sxs-lookup"><span data-stu-id="bf58f-106">Remarks</span></span>  
 <span data-ttu-id="bf58f-107">需要呼叫 `JsSetProjectionEnqueueCallback` 才能接收回拨。</span><span class="sxs-lookup"><span data-stu-id="bf58f-107">Requires calling `JsSetProjectionEnqueueCallback` to receive callbacks.</span></span>  
  
 <span data-ttu-id="bf58f-108">此 API 仅在 EdgeHTML 模式下受支持。</span><span class="sxs-lookup"><span data-stu-id="bf58f-108">This API is supported only in EdgeHTML mode.</span></span>  
  
## <span data-ttu-id="bf58f-109">要求</span><span class="sxs-lookup"><span data-stu-id="bf58f-109">Requirements</span></span>  
 <span data-ttu-id="bf58f-110">jsrt</span><span class="sxs-lookup"><span data-stu-id="bf58f-110">jsrt.h</span></span>  
  
## <span data-ttu-id="bf58f-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bf58f-111">See Also</span></span>  
 [<span data-ttu-id="bf58f-112">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="bf58f-112">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)