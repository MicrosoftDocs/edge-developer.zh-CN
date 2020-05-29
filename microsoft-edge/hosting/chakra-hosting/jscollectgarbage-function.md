---
description: 执行完整垃圾回收。
title: JsCollectGarbage 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsCollectGarbage
helpviewer_keywords:
- JsCollectGarbage function
ms.assetid: 995c79a5-6e18-45be-81ff-2a5d3348edb8
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 1702ad960a0a2f366e97b8a994abd0700cec50e7
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563192"
---
# <span data-ttu-id="df68b-103">JsCollectGarbage 函数</span><span class="sxs-lookup"><span data-stu-id="df68b-103">JsCollectGarbage Function</span></span>
<span data-ttu-id="df68b-104">执行完整垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="df68b-104">Performs a full garbage collection.</span></span>  
  
## <span data-ttu-id="df68b-105">语法</span><span class="sxs-lookup"><span data-stu-id="df68b-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsCollectGarbage(  
   _In_ JsRuntimeHandle runtime  
);  
```  
  
#### <span data-ttu-id="df68b-106">参数</span><span class="sxs-lookup"><span data-stu-id="df68b-106">Parameters</span></span>  
 `runtime`  
 <span data-ttu-id="df68b-107">将在其中执行垃圾回收的运行时。</span><span class="sxs-lookup"><span data-stu-id="df68b-107">The runtime in which the garbage collection will be performed.</span></span>  
  
## <span data-ttu-id="df68b-108">返回值</span><span class="sxs-lookup"><span data-stu-id="df68b-108">Return Value</span></span>  
 <span data-ttu-id="df68b-109">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="df68b-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="df68b-110">要求</span><span class="sxs-lookup"><span data-stu-id="df68b-110">Requirements</span></span>  
 <span data-ttu-id="df68b-111">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="df68b-111">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="df68b-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="df68b-112">See Also</span></span>  
 [<span data-ttu-id="df68b-113">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="df68b-113">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)