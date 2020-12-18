---
description: 用户为内存分配事件实现了回调例程。
title: JsMemoryAllocationCallback Typedef |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 511babc7-3caa-4ee5-82a2-943bbd34db8d
caps.latest.revision: 7
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 22b5cc0fe5a2c8b49f71c91d28f95ba29af37849
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232198"
---
# <span data-ttu-id="e5218-103">JsMemoryAllocationCallback Typedef</span><span class="sxs-lookup"><span data-stu-id="e5218-103">JsMemoryAllocationCallback Typedef</span></span>

<span data-ttu-id="e5218-104">用户为内存分配事件实现了回调例程。</span><span class="sxs-lookup"><span data-stu-id="e5218-104">User implemented callback routine for memory allocation events.</span></span>  
  
## <span data-ttu-id="e5218-105">语法</span><span class="sxs-lookup"><span data-stu-id="e5218-105">Syntax</span></span>  
  
```cpp  
typedef bool (CALLBACK * JsMemoryAllocationCallback)(  
   _In_opt_ void *callbackState,  
   _In_ JsMemoryEventType allocationEvent,  
   _In_ size_t allocationSize  
);  
```  
  
#### <span data-ttu-id="e5218-106">参数</span><span class="sxs-lookup"><span data-stu-id="e5218-106">Parameters</span></span>  
 <span data-ttu-id="e5218-107">callbackState</span><span class="sxs-lookup"><span data-stu-id="e5218-107">callbackState</span></span>  
 <span data-ttu-id="e5218-108">传递给 JsSetRuntimeMemoryAllocationCallback 的状态。</span><span class="sxs-lookup"><span data-stu-id="e5218-108">The state passed to JsSetRuntimeMemoryAllocationCallback.</span></span>  
  
 <span data-ttu-id="e5218-109">allocationEvent</span><span class="sxs-lookup"><span data-stu-id="e5218-109">allocationEvent</span></span>  
 <span data-ttu-id="e5218-110">类型分配事件的类型。</span><span class="sxs-lookup"><span data-stu-id="e5218-110">The type of type allocation event.</span></span>  
  
 <span data-ttu-id="e5218-111">allocationSize</span><span class="sxs-lookup"><span data-stu-id="e5218-111">allocationSize</span></span>  
 <span data-ttu-id="e5218-112">分配的大小。</span><span class="sxs-lookup"><span data-stu-id="e5218-112">The size of the allocation.</span></span>  
  
## <span data-ttu-id="e5218-113">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="e5218-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="e5218-114">对于 JsMemoryAllocate 事件，返回 true 允许运行时继续分配。</span><span class="sxs-lookup"><span data-stu-id="e5218-114">For the JsMemoryAllocate event, returning true allows the runtime to continue with allocation.</span></span> <span data-ttu-id="e5218-115">返回 false 表示分配请求被拒绝。</span><span class="sxs-lookup"><span data-stu-id="e5218-115">Returning false indicates the allocation request is rejected.</span></span> <span data-ttu-id="e5218-116">对于其他分配事件，将忽略返回值。</span><span class="sxs-lookup"><span data-stu-id="e5218-116">The return value is ignored for other allocation events.</span></span>  
  
## <span data-ttu-id="e5218-117">备注</span><span class="sxs-lookup"><span data-stu-id="e5218-117">Remarks</span></span>  
 <span data-ttu-id="e5218-118">使用 JsSetRuntimeMemoryAllocationCallback 注册此回调。</span><span class="sxs-lookup"><span data-stu-id="e5218-118">Use JsSetRuntimeMemoryAllocationCallback to register this callback.</span></span>  
  
## <span data-ttu-id="e5218-119">要求</span><span class="sxs-lookup"><span data-stu-id="e5218-119">Requirements</span></span>  
 <span data-ttu-id="e5218-120">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="e5218-120">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="e5218-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e5218-121">See Also</span></span>  
 [<span data-ttu-id="e5218-122">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="e5218-122">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
