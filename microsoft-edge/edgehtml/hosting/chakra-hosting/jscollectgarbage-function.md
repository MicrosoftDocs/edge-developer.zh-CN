---
description: 执行完整的垃圾回收。
title: JsCollectGarbage 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsCollectGarbage
helpviewer_keywords:
- JsCollectGarbage function
ms.assetid: 995c79a5-6e18-45be-81ff-2a5d3348edb8
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: c551ddf119ec0aa349fcd756f6001d92dbbb0faa
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232216"
---
# <span data-ttu-id="15ab0-103">JsCollectGarbage 函数</span><span class="sxs-lookup"><span data-stu-id="15ab0-103">JsCollectGarbage Function</span></span>

<span data-ttu-id="15ab0-104">执行完整的垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="15ab0-104">Performs a full garbage collection.</span></span>  
  
## <span data-ttu-id="15ab0-105">语法</span><span class="sxs-lookup"><span data-stu-id="15ab0-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsCollectGarbage(  
   _In_ JsRuntimeHandle runtime  
);  
```  
  
#### <span data-ttu-id="15ab0-106">参数</span><span class="sxs-lookup"><span data-stu-id="15ab0-106">Parameters</span></span>  
 `runtime`  
 <span data-ttu-id="15ab0-107">将在其中执行垃圾回收的运行时。</span><span class="sxs-lookup"><span data-stu-id="15ab0-107">The runtime in which the garbage collection will be performed.</span></span>  
  
## <span data-ttu-id="15ab0-108">返回值</span><span class="sxs-lookup"><span data-stu-id="15ab0-108">Return Value</span></span>  
 <span data-ttu-id="15ab0-109">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="15ab0-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="15ab0-110">要求</span><span class="sxs-lookup"><span data-stu-id="15ab0-110">Requirements</span></span>  
 <span data-ttu-id="15ab0-111">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="15ab0-111">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="15ab0-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="15ab0-112">See Also</span></span>  
 [<span data-ttu-id="15ab0-113">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="15ab0-113">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
