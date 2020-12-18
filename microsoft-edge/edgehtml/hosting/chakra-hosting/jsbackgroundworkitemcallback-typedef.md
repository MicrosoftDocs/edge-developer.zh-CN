---
description: 后台工作项回调。
title: JsBackgroundWorkItemCallback Typedef |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: e6db52e1-830c-46a2-b9f9-cc2d450a1da8
caps.latest.revision: 6
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: d69306b334c2e0c9b27b96a5a417739ffdcd7dd7
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232230"
---
# <span data-ttu-id="82d51-103">JsBackgroundWorkItemCallback Typedef</span><span class="sxs-lookup"><span data-stu-id="82d51-103">JsBackgroundWorkItemCallback Typedef</span></span>

<span data-ttu-id="82d51-104">后台工作项回调。</span><span class="sxs-lookup"><span data-stu-id="82d51-104">A background work item callback.</span></span>  
  
## <span data-ttu-id="82d51-105">语法</span><span class="sxs-lookup"><span data-stu-id="82d51-105">Syntax</span></span>  
  
```cpp  
typedef void (CALLBACK *JsBackgroundWorkItemCallback)(  
   _In_opt_ void *callbackData  
);  
```  
  
#### <span data-ttu-id="82d51-106">参数</span><span class="sxs-lookup"><span data-stu-id="82d51-106">Parameters</span></span>  
 <span data-ttu-id="82d51-107">callbackData</span><span class="sxs-lookup"><span data-stu-id="82d51-107">callbackData</span></span>  
 <span data-ttu-id="82d51-108">传递给线程服务的数据参数。</span><span class="sxs-lookup"><span data-stu-id="82d51-108">Data argument passed to the thread service.</span></span>  
  
## <span data-ttu-id="82d51-109">备注</span><span class="sxs-lookup"><span data-stu-id="82d51-109">Remarks</span></span>  
 <span data-ttu-id="82d51-110">如果提供此参数，则 (主机的线程服务) 以允许主机在其选择的后台线程上调用工作项回调。</span><span class="sxs-lookup"><span data-stu-id="82d51-110">This is passed to the host's thread service (if provided) to allow the host to invoke the work item callback on the background thread of its choice.</span></span>  
  
## <span data-ttu-id="82d51-111">要求</span><span class="sxs-lookup"><span data-stu-id="82d51-111">Requirements</span></span>  
 <span data-ttu-id="82d51-112">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="82d51-112">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="82d51-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="82d51-113">See Also</span></span>  
 [<span data-ttu-id="82d51-114">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="82d51-114">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
