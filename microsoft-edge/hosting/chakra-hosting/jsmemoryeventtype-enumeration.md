---
description: 分配回调事件类型。
title: JsMemoryEventType 枚举 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsMemoryEventType
helpviewer_keywords:
- JsMemoryEventType enumeration
ms.assetid: b4b176b6-b536-472e-8999-95b681a1df55
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 1e9833777ed8fe5a19fd2a1487715296279f7351
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563085"
---
# <span data-ttu-id="6b00b-103">JsMemoryEventType 枚举</span><span class="sxs-lookup"><span data-stu-id="6b00b-103">JsMemoryEventType Enumeration</span></span>
<span data-ttu-id="6b00b-104">分配回调事件类型。</span><span class="sxs-lookup"><span data-stu-id="6b00b-104">Allocation callback event type.</span></span>  
  
## <span data-ttu-id="6b00b-105">语法</span><span class="sxs-lookup"><span data-stu-id="6b00b-105">Syntax</span></span>  
  
```cpp  
enum JsMemoryEventType;  
```  
  
## <span data-ttu-id="6b00b-106">成员</span><span class="sxs-lookup"><span data-stu-id="6b00b-106">Members</span></span>  
  
### <span data-ttu-id="6b00b-107">值</span><span class="sxs-lookup"><span data-stu-id="6b00b-107">Values</span></span>  
  
|<span data-ttu-id="6b00b-108">名称</span><span class="sxs-lookup"><span data-stu-id="6b00b-108">Name</span></span>|<span data-ttu-id="6b00b-109">描述</span><span class="sxs-lookup"><span data-stu-id="6b00b-109">Description</span></span>|  
|----------|-----------------|  
|`JsMemoryAllocate`|<span data-ttu-id="6b00b-110">指示内存分配请求。</span><span class="sxs-lookup"><span data-stu-id="6b00b-110">Indicates a request for memory allocation.</span></span>|  
|`JsMemoryFailure`|<span data-ttu-id="6b00b-111">指示分配失败的事件。</span><span class="sxs-lookup"><span data-stu-id="6b00b-111">Indicates a failed allocation event.</span></span>|  
|`JsMemoryFree`|<span data-ttu-id="6b00b-112">指示内存释放事件。</span><span class="sxs-lookup"><span data-stu-id="6b00b-112">Indicates a memory freeing event.</span></span>|  
  
## <span data-ttu-id="6b00b-113">要求</span><span class="sxs-lookup"><span data-stu-id="6b00b-113">Requirements</span></span>  
 <span data-ttu-id="6b00b-114">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="6b00b-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="6b00b-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6b00b-115">See Also</span></span>  
 [<span data-ttu-id="6b00b-116">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="6b00b-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)