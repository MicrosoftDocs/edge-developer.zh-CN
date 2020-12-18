---
description: 分配回调事件类型。
title: JsMemoryEventType 枚举 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsMemoryEventType
helpviewer_keywords:
- JsMemoryEventType enumeration
ms.assetid: b4b176b6-b536-472e-8999-95b681a1df55
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: a28010f908285098cf652b497b6d6c272bc763fc
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232007"
---
# <span data-ttu-id="2e434-103">JsMemoryEventType 枚举</span><span class="sxs-lookup"><span data-stu-id="2e434-103">JsMemoryEventType Enumeration</span></span>

<span data-ttu-id="2e434-104">分配回调事件类型。</span><span class="sxs-lookup"><span data-stu-id="2e434-104">Allocation callback event type.</span></span>  
  
## <span data-ttu-id="2e434-105">语法</span><span class="sxs-lookup"><span data-stu-id="2e434-105">Syntax</span></span>  
  
```cpp  
enum JsMemoryEventType;  
```  
  
## <span data-ttu-id="2e434-106">成员</span><span class="sxs-lookup"><span data-stu-id="2e434-106">Members</span></span>  
  
### <span data-ttu-id="2e434-107">值</span><span class="sxs-lookup"><span data-stu-id="2e434-107">Values</span></span>  
  
|<span data-ttu-id="2e434-108">名称</span><span class="sxs-lookup"><span data-stu-id="2e434-108">Name</span></span>|<span data-ttu-id="2e434-109">描述</span><span class="sxs-lookup"><span data-stu-id="2e434-109">Description</span></span>|  
|----------|-----------------|  
|`JsMemoryAllocate`|<span data-ttu-id="2e434-110">指示内存分配请求。</span><span class="sxs-lookup"><span data-stu-id="2e434-110">Indicates a request for memory allocation.</span></span>|  
|`JsMemoryFailure`|<span data-ttu-id="2e434-111">指示分配事件失败。</span><span class="sxs-lookup"><span data-stu-id="2e434-111">Indicates a failed allocation event.</span></span>|  
|`JsMemoryFree`|<span data-ttu-id="2e434-112">指示释放内存事件。</span><span class="sxs-lookup"><span data-stu-id="2e434-112">Indicates a memory freeing event.</span></span>|  
  
## <span data-ttu-id="2e434-113">要求</span><span class="sxs-lookup"><span data-stu-id="2e434-113">Requirements</span></span>  
 <span data-ttu-id="2e434-114">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="2e434-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="2e434-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2e434-115">See Also</span></span>  
 [<span data-ttu-id="2e434-116">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="2e434-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
