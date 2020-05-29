---
description: 应通过传递到正确线程上的上下文调用的 JsRT 回调 `JsProjectionEnqueueCallback` 。
title: JsProjectionCallback Typedef |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 32f22d37-e57e-4196-b6cd-a3fc75bd0632
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: b30f9a7dc4671896eeacecbf58ef88f0383e9e7e
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563077"
---
# <span data-ttu-id="b591a-103">JsProjectionCallback Typedef</span><span class="sxs-lookup"><span data-stu-id="b591a-103">JsProjectionCallback Typedef</span></span>
<span data-ttu-id="b591a-104">应通过传递到正确线程上的上下文调用的 JsRT 回调 `JsProjectionEnqueueCallback` 。</span><span class="sxs-lookup"><span data-stu-id="b591a-104">The JsRT callback which should be called with the context passed to `JsProjectionEnqueueCallback` on the correct thread.</span></span>  
  
## <span data-ttu-id="b591a-105">语法</span><span class="sxs-lookup"><span data-stu-id="b591a-105">Syntax</span></span>  
  
```cpp  
typedef void (CALLBACK *JsProjectionCallback)(  
  _In_ JsProjectionCallbackContext jsContext  
);  
```  
  
#### <span data-ttu-id="b591a-106">参数</span><span class="sxs-lookup"><span data-stu-id="b591a-106">Parameters</span></span>  
 `jsContext`  
 <span data-ttu-id="b591a-107">需要呼叫 `JsSetProjectionEnqueueCallback` 才能接收回拨。</span><span class="sxs-lookup"><span data-stu-id="b591a-107">Requires calling `JsSetProjectionEnqueueCallback` to receive callbacks.</span></span>  
  
## <span data-ttu-id="b591a-108">备注</span><span class="sxs-lookup"><span data-stu-id="b591a-108">Remarks</span></span>  
 <span data-ttu-id="b591a-109">此 API 仅在 EdgeHTML 模式下受支持。</span><span class="sxs-lookup"><span data-stu-id="b591a-109">This API is supported only in EdgeHTML mode.</span></span>  
  
## <span data-ttu-id="b591a-110">要求</span><span class="sxs-lookup"><span data-stu-id="b591a-110">Requirements</span></span>  
 <span data-ttu-id="b591a-111">jsrt</span><span class="sxs-lookup"><span data-stu-id="b591a-111">jsrt.h</span></span>  
  
## <span data-ttu-id="b591a-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b591a-112">See Also</span></span>  
 [<span data-ttu-id="b591a-113">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="b591a-113">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)