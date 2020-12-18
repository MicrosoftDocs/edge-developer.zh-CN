---
description: 释放运行时。
title: JsDisposeRuntime 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsDisposeRuntime
helpviewer_keywords:
- JsDisposeRuntime function
ms.assetid: 0aefde3f-7250-48be-afc5-53ea85c12f30
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 8cff4578415cdf1aaa01b7203ce734cef9115301
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232402"
---
# <span data-ttu-id="92cab-103">JsDisposeRuntime 函数</span><span class="sxs-lookup"><span data-stu-id="92cab-103">JsDisposeRuntime Function</span></span>

<span data-ttu-id="92cab-104">释放运行时。</span><span class="sxs-lookup"><span data-stu-id="92cab-104">Disposes a runtime.</span></span>  
  
## <span data-ttu-id="92cab-105">语法</span><span class="sxs-lookup"><span data-stu-id="92cab-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsDisposeRuntime(  
   _In_ JsRuntimeHandle runtime  
);  
```  
  
#### <span data-ttu-id="92cab-106">参数</span><span class="sxs-lookup"><span data-stu-id="92cab-106">Parameters</span></span>  
 `runtime`  
 <span data-ttu-id="92cab-107">要释放的运行时。</span><span class="sxs-lookup"><span data-stu-id="92cab-107">The runtime to dispose.</span></span>  
  
## <span data-ttu-id="92cab-108">返回值</span><span class="sxs-lookup"><span data-stu-id="92cab-108">Return Value</span></span>  
 <span data-ttu-id="92cab-109">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="92cab-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="92cab-110">备注</span><span class="sxs-lookup"><span data-stu-id="92cab-110">Remarks</span></span>  
 <span data-ttu-id="92cab-111">释放运行时后，它拥有的所有资源都是无效的，并且不能使用。</span><span class="sxs-lookup"><span data-stu-id="92cab-111">Once a runtime has been disposed, all resources owned by it are invalid and cannot be used.</span></span> <span data-ttu-id="92cab-112">如果运行时处于活动状态 (即，它设置为特定线程上的当前) ，则不能释放它。</span><span class="sxs-lookup"><span data-stu-id="92cab-112">If the runtime is active (i.e. it is set to be current on a particular thread), it cannot be disposed.</span></span>  
  
## <span data-ttu-id="92cab-113">要求</span><span class="sxs-lookup"><span data-stu-id="92cab-113">Requirements</span></span>  
 <span data-ttu-id="92cab-114">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="92cab-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="92cab-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="92cab-115">See Also</span></span>  
 [<span data-ttu-id="92cab-116">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="92cab-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
