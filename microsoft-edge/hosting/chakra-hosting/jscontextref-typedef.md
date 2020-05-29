---
description: 对脚本上下文的引用。
title: JsContextRef Typedef |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 8586bfcc-bb24-430d-a6f2-1a3b3e34ec2e
caps.latest.revision: 6
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 80e4b5034079f4f0d26da070bd209aa41bf3475f
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563189"
---
# <span data-ttu-id="5e38f-103">JsContextRef Typedef</span><span class="sxs-lookup"><span data-stu-id="5e38f-103">JsContextRef Typedef</span></span>
<span data-ttu-id="5e38f-104">对脚本上下文的引用。</span><span class="sxs-lookup"><span data-stu-id="5e38f-104">A reference to a script context.</span></span>  
  
## <span data-ttu-id="5e38f-105">语法</span><span class="sxs-lookup"><span data-stu-id="5e38f-105">Syntax</span></span>  
  
```cpp  
typedef JsRef JsContextRef;  
```  
  
## <span data-ttu-id="5e38f-106">备注</span><span class="sxs-lookup"><span data-stu-id="5e38f-106">Remarks</span></span>  
 <span data-ttu-id="5e38f-107">每个脚本上下文都包含其自己的全局对象，与其他脚本上下文中的全局对象不同。</span><span class="sxs-lookup"><span data-stu-id="5e38f-107">Each script context contains its own global object, distinct from the global object in other script contexts.</span></span>  
  
 <span data-ttu-id="5e38f-108">许多 Chakra 托管 Api 需要 "活动" 脚本上下文，可使用进行设置 `JsSetCurrentContext` 。</span><span class="sxs-lookup"><span data-stu-id="5e38f-108">Many Chakra hosting APIs require an "active" script context, which can be set using `JsSetCurrentContext`.</span></span> <span data-ttu-id="5e38f-109">需要设置当前上下文的 Chakra 托管 Api 将在其文档中明确说明。</span><span class="sxs-lookup"><span data-stu-id="5e38f-109">Chakra hosting APIs that require a current context to be set will note that explicitly in their documentation.</span></span>  
  
## <span data-ttu-id="5e38f-110">要求</span><span class="sxs-lookup"><span data-stu-id="5e38f-110">Requirements</span></span>  
 <span data-ttu-id="5e38f-111">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="5e38f-111">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="5e38f-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5e38f-112">See Also</span></span>  
 [<span data-ttu-id="5e38f-113">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="5e38f-113">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)