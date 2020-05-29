---
description: 线程服务回调。
title: JsThreadServiceCallback Typedef |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: dbe67be5-418a-4f66-8b68-b38078a6d140
caps.latest.revision: 6
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 5eb9f2986c79db024f01f4d22050f79c9689400c
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563068"
---
# <span data-ttu-id="07f18-103">JsThreadServiceCallback Typedef</span><span class="sxs-lookup"><span data-stu-id="07f18-103">JsThreadServiceCallback Typedef</span></span>
<span data-ttu-id="07f18-104">线程服务回调。</span><span class="sxs-lookup"><span data-stu-id="07f18-104">A thread service callback.</span></span>  
  
## <span data-ttu-id="07f18-105">语法</span><span class="sxs-lookup"><span data-stu-id="07f18-105">Syntax</span></span>  
  
```cpp  
typedef bool (CALLBACK *JsThreadServiceCallback)(  
   _In_ JsBackgroundWorkItemCallback callback,  
   _In_opt_ void *callbackData  
);  
```  
  
#### <span data-ttu-id="07f18-106">参数</span><span class="sxs-lookup"><span data-stu-id="07f18-106">Parameters</span></span>  
 <span data-ttu-id="07f18-107">回调</span><span class="sxs-lookup"><span data-stu-id="07f18-107">callback</span></span>  
 <span data-ttu-id="07f18-108">后台工作项的回调。</span><span class="sxs-lookup"><span data-stu-id="07f18-108">The callback for the background work item.</span></span>  
  
 <span data-ttu-id="07f18-109">callbackData</span><span class="sxs-lookup"><span data-stu-id="07f18-109">callbackData</span></span>  
 <span data-ttu-id="07f18-110">要传递到回调的数据参数。</span><span class="sxs-lookup"><span data-stu-id="07f18-110">The data argument to be passed to the callback.</span></span>  
  
## <span data-ttu-id="07f18-111">备注</span><span class="sxs-lookup"><span data-stu-id="07f18-111">Remarks</span></span>  
 <span data-ttu-id="07f18-112">主机可以在调用 JsCreateRuntime 时指定后台线程服务。</span><span class="sxs-lookup"><span data-stu-id="07f18-112">The host can specify a background thread service when calling JsCreateRuntime.</span></span> <span data-ttu-id="07f18-113">如果已指定，则后台工作项将使用此回调传递到主机。</span><span class="sxs-lookup"><span data-stu-id="07f18-113">If specified, then background work items will be passed to the host using this callback.</span></span> <span data-ttu-id="07f18-114">主机应立即开始执行后台工作项，并返回 true 或返回 false，并且运行时将处理线程中的工作项。</span><span class="sxs-lookup"><span data-stu-id="07f18-114">The host is expected to either begin executing the background work item immediately and return true or return false and the runtime will handle the work item in-thread.</span></span>  
  
## <span data-ttu-id="07f18-115">要求</span><span class="sxs-lookup"><span data-stu-id="07f18-115">Requirements</span></span>  
 <span data-ttu-id="07f18-116">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="07f18-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="07f18-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="07f18-117">See Also</span></span>  
 [<span data-ttu-id="07f18-118">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="07f18-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)