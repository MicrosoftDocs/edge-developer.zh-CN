---
description: 对脚本上下文的引用。
title: JsContextRef Typedef |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 8586bfcc-bb24-430d-a6f2-1a3b3e34ec2e
caps.latest.revision: 6
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: c8a8fcbd67afb150d682cfc19321f0f13acfe3a6
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232219"
---
# <span data-ttu-id="87418-103">JsContextRef Typedef</span><span class="sxs-lookup"><span data-stu-id="87418-103">JsContextRef Typedef</span></span>

<span data-ttu-id="87418-104">对脚本上下文的引用。</span><span class="sxs-lookup"><span data-stu-id="87418-104">A reference to a script context.</span></span>  
  
## <span data-ttu-id="87418-105">语法</span><span class="sxs-lookup"><span data-stu-id="87418-105">Syntax</span></span>  
  
```cpp  
typedef JsRef JsContextRef;  
```  
  
## <span data-ttu-id="87418-106">备注</span><span class="sxs-lookup"><span data-stu-id="87418-106">Remarks</span></span>  
 <span data-ttu-id="87418-107">每个脚本上下文都包含其自己的全局对象，不同于其他脚本上下文中的全局对象。</span><span class="sxs-lookup"><span data-stu-id="87418-107">Each script context contains its own global object, distinct from the global object in other script contexts.</span></span>  
  
 <span data-ttu-id="87418-108">许多 Chakra 托管 API 都需要"活动"脚本上下文，可以使用它进行设置 `JsSetCurrentContext` 。</span><span class="sxs-lookup"><span data-stu-id="87418-108">Many Chakra hosting APIs require an "active" script context, which can be set using `JsSetCurrentContext`.</span></span> <span data-ttu-id="87418-109">需要设置当前上下文的 Chakra 托管 API 将明确记录在文档中。</span><span class="sxs-lookup"><span data-stu-id="87418-109">Chakra hosting APIs that require a current context to be set will note that explicitly in their documentation.</span></span>  
  
## <span data-ttu-id="87418-110">要求</span><span class="sxs-lookup"><span data-stu-id="87418-110">Requirements</span></span>  
 <span data-ttu-id="87418-111">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="87418-111">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="87418-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="87418-112">See Also</span></span>  
 [<span data-ttu-id="87418-113">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="87418-113">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
