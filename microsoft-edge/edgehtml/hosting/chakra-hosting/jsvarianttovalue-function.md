---
description: 创建一个 JavaScript 值，该值是传入的投影 `VARIANT` 。
title: JsVariantToValue 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsVariantToValue
helpviewer_keywords:
- JsVariantToValue function
ms.assetid: e8f9eb8b-55b3-4b65-927e-cad5b482edee
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 58c928b519b5a9a678b6cd6ad367e1db2332f021
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232347"
---
# <span data-ttu-id="5d770-103">JsVariantToValue 函数</span><span class="sxs-lookup"><span data-stu-id="5d770-103">JsVariantToValue Function</span></span>

<span data-ttu-id="5d770-104">创建一个 JavaScript 值，该值是传入的投影 `VARIANT` 。</span><span class="sxs-lookup"><span data-stu-id="5d770-104">Creates a JavaScript value that is a projection of the passed in `VARIANT`.</span></span>  
  
## <span data-ttu-id="5d770-105">语法</span><span class="sxs-lookup"><span data-stu-id="5d770-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsVariantToValue(  
   _In_ VARIANT *variant,  
   _Out_ JsValueRef *value  
);  
```  
  
#### <span data-ttu-id="5d770-106">参数</span><span class="sxs-lookup"><span data-stu-id="5d770-106">Parameters</span></span>  
 `variant`  
 <span data-ttu-id="5d770-107">要 `VARIANT` 规划的 A。</span><span class="sxs-lookup"><span data-stu-id="5d770-107">A `VARIANT` to be projected.</span></span>  
  
 `value`  
 <span data-ttu-id="5d770-108">作为投影的 JavaScript 值 `VARIANT` 。</span><span class="sxs-lookup"><span data-stu-id="5d770-108">A JavaScript value that is a projection of the `VARIANT`.</span></span>  
  
## <span data-ttu-id="5d770-109">返回值</span><span class="sxs-lookup"><span data-stu-id="5d770-109">Return Value</span></span>  
 <span data-ttu-id="5d770-110">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="5d770-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="5d770-111">备注</span><span class="sxs-lookup"><span data-stu-id="5d770-111">Remarks</span></span>  
 <span data-ttu-id="5d770-112">脚本可以使用预计值从脚本调用 COM 自动化对象。</span><span class="sxs-lookup"><span data-stu-id="5d770-112">The projected value can be used by script to call a COM automation object from script.</span></span> <span data-ttu-id="5d770-113">主机负责强制实施 COM 线程规则。</span><span class="sxs-lookup"><span data-stu-id="5d770-113">Hosts are responsible for enforcing COM threading rules.</span></span>  
  
 <span data-ttu-id="5d770-114">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="5d770-114">Requires an active script context.</span></span>  
  
## <span data-ttu-id="5d770-115">要求</span><span class="sxs-lookup"><span data-stu-id="5d770-115">Requirements</span></span>  
 <span data-ttu-id="5d770-116">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="5d770-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="5d770-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5d770-117">See Also</span></span>  
 [<span data-ttu-id="5d770-118">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="5d770-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
