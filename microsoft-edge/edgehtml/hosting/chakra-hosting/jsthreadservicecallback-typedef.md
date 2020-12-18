---
description: 线程服务回调。
title: JsThreadServiceCallback Typedef |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: dbe67be5-418a-4f66-8b68-b38078a6d140
caps.latest.revision: 6
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: a5f1fe416e158e9524bdd1caab847977a5dd21b8
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232352"
---
# <span data-ttu-id="7340f-103">JsThreadServiceCallback Typedef</span><span class="sxs-lookup"><span data-stu-id="7340f-103">JsThreadServiceCallback Typedef</span></span>

<span data-ttu-id="7340f-104">线程服务回调。</span><span class="sxs-lookup"><span data-stu-id="7340f-104">A thread service callback.</span></span>  
  
## <span data-ttu-id="7340f-105">语法</span><span class="sxs-lookup"><span data-stu-id="7340f-105">Syntax</span></span>  
  
```cpp  
typedef bool (CALLBACK *JsThreadServiceCallback)(  
   _In_ JsBackgroundWorkItemCallback callback,  
   _In_opt_ void *callbackData  
);  
```  
  
#### <span data-ttu-id="7340f-106">参数</span><span class="sxs-lookup"><span data-stu-id="7340f-106">Parameters</span></span>  
 <span data-ttu-id="7340f-107">回调</span><span class="sxs-lookup"><span data-stu-id="7340f-107">callback</span></span>  
 <span data-ttu-id="7340f-108">后台工作项的回调。</span><span class="sxs-lookup"><span data-stu-id="7340f-108">The callback for the background work item.</span></span>  
  
 <span data-ttu-id="7340f-109">callbackData</span><span class="sxs-lookup"><span data-stu-id="7340f-109">callbackData</span></span>  
 <span data-ttu-id="7340f-110">要传递给回调的数据参数。</span><span class="sxs-lookup"><span data-stu-id="7340f-110">The data argument to be passed to the callback.</span></span>  
  
## <span data-ttu-id="7340f-111">备注</span><span class="sxs-lookup"><span data-stu-id="7340f-111">Remarks</span></span>  
 <span data-ttu-id="7340f-112">主机可以在调用 JsCreateRuntime 时指定后台线程服务。</span><span class="sxs-lookup"><span data-stu-id="7340f-112">The host can specify a background thread service when calling JsCreateRuntime.</span></span> <span data-ttu-id="7340f-113">如果指定，则后台工作项将使用此回调传递给主机。</span><span class="sxs-lookup"><span data-stu-id="7340f-113">If specified, then background work items will be passed to the host using this callback.</span></span> <span data-ttu-id="7340f-114">主机应立即开始执行后台工作项并返回 true 或返回 false，运行时将在线程中处理工作项。</span><span class="sxs-lookup"><span data-stu-id="7340f-114">The host is expected to either begin executing the background work item immediately and return true or return false and the runtime will handle the work item in-thread.</span></span>  
  
## <span data-ttu-id="7340f-115">要求</span><span class="sxs-lookup"><span data-stu-id="7340f-115">Requirements</span></span>  
 <span data-ttu-id="7340f-116">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="7340f-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="7340f-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7340f-117">See Also</span></span>  
 [<span data-ttu-id="7340f-118">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="7340f-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
