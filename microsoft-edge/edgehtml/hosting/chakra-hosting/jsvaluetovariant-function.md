---
description: 初始化作为 `VARIANT` JavaScript 值的投影传入。
title: JsValueToVariant 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsValueToVariant
helpviewer_keywords:
- JsValueToVariant function
ms.assetid: 070244be-a69d-4b78-971b-69c0579c03cf
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: f383f2d8bc3aab70b4a361b370698cd71cb714d3
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232350"
---
# <span data-ttu-id="b827d-103">JsValueToVariant 函数</span><span class="sxs-lookup"><span data-stu-id="b827d-103">JsValueToVariant Function</span></span>

<span data-ttu-id="b827d-104">初始化作为 `VARIANT` JavaScript 值的投影传入。</span><span class="sxs-lookup"><span data-stu-id="b827d-104">Initializes the passed in `VARIANT` as a projection of a JavaScript value.</span></span>  
  
## <span data-ttu-id="b827d-105">语法</span><span class="sxs-lookup"><span data-stu-id="b827d-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsValueToVariant(  
   _In_ JsValueRef object,  
   _Out_ VARIANT *variant  
);  
```  
  
#### <span data-ttu-id="b827d-106">参数</span><span class="sxs-lookup"><span data-stu-id="b827d-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="b827d-107">要作为项目表示的 JavaScript 值 `VARIANT` 。</span><span class="sxs-lookup"><span data-stu-id="b827d-107">A JavaScript value to project as a `VARIANT`.</span></span>  
  
 `variant`  
 <span data-ttu-id="b827d-108">指向将初始化为投影的结构 `VARIANT` 指针。</span><span class="sxs-lookup"><span data-stu-id="b827d-108">A pointer to a `VARIANT` struct that will be initialized as a projection.</span></span>  
  
## <span data-ttu-id="b827d-109">返回值</span><span class="sxs-lookup"><span data-stu-id="b827d-109">Return Value</span></span>  
  
## <span data-ttu-id="b827d-110">备注</span><span class="sxs-lookup"><span data-stu-id="b827d-110">Remarks</span></span>  
 <span data-ttu-id="b827d-111">COM `VARIANT` 自动化客户端可以使用投影来调用投影的 JavaScript 对象。</span><span class="sxs-lookup"><span data-stu-id="b827d-111">The projection `VARIANT` can be used by COM automation clients to call into the projected JavaScript object.</span></span>  
  
 <span data-ttu-id="b827d-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="b827d-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="b827d-113">要求</span><span class="sxs-lookup"><span data-stu-id="b827d-113">Requirements</span></span>  
 <span data-ttu-id="b827d-114">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="b827d-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="b827d-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b827d-115">See Also</span></span>  
 [<span data-ttu-id="b827d-116">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="b827d-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
