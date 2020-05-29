---
description: 用户为内存分配事件实现回调例程。
title: JsMemoryAllocationCallback Typedef |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 511babc7-3caa-4ee5-82a2-943bbd34db8d
caps.latest.revision: 7
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: b11b3d076c01dbfcae190fd665528323d6f8b987
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563088"
---
# <span data-ttu-id="698ca-103">JsMemoryAllocationCallback Typedef</span><span class="sxs-lookup"><span data-stu-id="698ca-103">JsMemoryAllocationCallback Typedef</span></span>
<span data-ttu-id="698ca-104">用户为内存分配事件实现回调例程。</span><span class="sxs-lookup"><span data-stu-id="698ca-104">User implemented callback routine for memory allocation events.</span></span>  
  
## <span data-ttu-id="698ca-105">语法</span><span class="sxs-lookup"><span data-stu-id="698ca-105">Syntax</span></span>  
  
```cpp  
typedef bool (CALLBACK * JsMemoryAllocationCallback)(  
   _In_opt_ void *callbackState,  
   _In_ JsMemoryEventType allocationEvent,  
   _In_ size_t allocationSize  
);  
```  
  
#### <span data-ttu-id="698ca-106">参数</span><span class="sxs-lookup"><span data-stu-id="698ca-106">Parameters</span></span>  
 <span data-ttu-id="698ca-107">callbackState</span><span class="sxs-lookup"><span data-stu-id="698ca-107">callbackState</span></span>  
 <span data-ttu-id="698ca-108">传递给 JsSetRuntimeMemoryAllocationCallback 的状态。</span><span class="sxs-lookup"><span data-stu-id="698ca-108">The state passed to JsSetRuntimeMemoryAllocationCallback.</span></span>  
  
 <span data-ttu-id="698ca-109">allocationEvent</span><span class="sxs-lookup"><span data-stu-id="698ca-109">allocationEvent</span></span>  
 <span data-ttu-id="698ca-110">类型分配事件的类型。</span><span class="sxs-lookup"><span data-stu-id="698ca-110">The type of type allocation event.</span></span>  
  
 <span data-ttu-id="698ca-111">allocationSize</span><span class="sxs-lookup"><span data-stu-id="698ca-111">allocationSize</span></span>  
 <span data-ttu-id="698ca-112">分配的大小。</span><span class="sxs-lookup"><span data-stu-id="698ca-112">The size of the allocation.</span></span>  
  
## <span data-ttu-id="698ca-113">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="698ca-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="698ca-114">对于 JsMemoryAllocate 事件，返回 true 将允许运行时继续分配。</span><span class="sxs-lookup"><span data-stu-id="698ca-114">For the JsMemoryAllocate event, returning true allows the runtime to continue with allocation.</span></span> <span data-ttu-id="698ca-115">返回 false 表示分配请求被拒绝。</span><span class="sxs-lookup"><span data-stu-id="698ca-115">Returning false indicates the allocation request is rejected.</span></span> <span data-ttu-id="698ca-116">对于其他分配事件，将忽略返回值。</span><span class="sxs-lookup"><span data-stu-id="698ca-116">The return value is ignored for other allocation events.</span></span>  
  
## <span data-ttu-id="698ca-117">备注</span><span class="sxs-lookup"><span data-stu-id="698ca-117">Remarks</span></span>  
 <span data-ttu-id="698ca-118">使用 JsSetRuntimeMemoryAllocationCallback 注册此回调。</span><span class="sxs-lookup"><span data-stu-id="698ca-118">Use JsSetRuntimeMemoryAllocationCallback to register this callback.</span></span>  
  
## <span data-ttu-id="698ca-119">要求</span><span class="sxs-lookup"><span data-stu-id="698ca-119">Requirements</span></span>  
 <span data-ttu-id="698ca-120">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="698ca-120">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="698ca-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="698ca-121">See Also</span></span>  
 [<span data-ttu-id="698ca-122">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="698ca-122">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)