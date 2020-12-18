---
description: 函数回调。
title: JsNativeFunction Typedef |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 56ef6cdf-4ca9-4f7c-b953-e661addb1a8e
caps.latest.revision: 5
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 891fe55f776e8519a5d3c187104b2bc326336482
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232021"
---
# <span data-ttu-id="52eff-103">JsNativeFunction Typedef</span><span class="sxs-lookup"><span data-stu-id="52eff-103">JsNativeFunction Typedef</span></span>

<span data-ttu-id="52eff-104">函数回调。</span><span class="sxs-lookup"><span data-stu-id="52eff-104">A function callback.</span></span>  
  
## <span data-ttu-id="52eff-105">语法</span><span class="sxs-lookup"><span data-stu-id="52eff-105">Syntax</span></span>  
  
```cpp  
typedef _Ret_maybenull_ JsValueRef (CALLBACK * JsNativeFunction)(  
   _In_ JsValueRef callee,  
   _In_ bool isConstructCall,  
   _In_ JsValueRef *arguments,  
   _In_ unsigned short argumentCount  
);  
```  
  
#### <span data-ttu-id="52eff-106">参数</span><span class="sxs-lookup"><span data-stu-id="52eff-106">Parameters</span></span>  
 <span data-ttu-id="52eff-107">被叫方</span><span class="sxs-lookup"><span data-stu-id="52eff-107">callee</span></span>  
 <span data-ttu-id="52eff-108">`Function`一个代表要调用的函数的对象。</span><span class="sxs-lookup"><span data-stu-id="52eff-108">A `Function` object that represents the function being invoked.</span></span>  
  
 <span data-ttu-id="52eff-109">isConstructCall</span><span class="sxs-lookup"><span data-stu-id="52eff-109">isConstructCall</span></span>  
 <span data-ttu-id="52eff-110">指示这是常规呼叫还是"新"呼叫。</span><span class="sxs-lookup"><span data-stu-id="52eff-110">Indicates whether this is a regular call or a 'new' call.</span></span>  
  
 <span data-ttu-id="52eff-111">arguments</span><span class="sxs-lookup"><span data-stu-id="52eff-111">arguments</span></span>  
 <span data-ttu-id="52eff-112">调用的参数。</span><span class="sxs-lookup"><span data-stu-id="52eff-112">The arguments to the call.</span></span>  
  
 <span data-ttu-id="52eff-113">argumentCount</span><span class="sxs-lookup"><span data-stu-id="52eff-113">argumentCount</span></span>  
 <span data-ttu-id="52eff-114">参数数。</span><span class="sxs-lookup"><span data-stu-id="52eff-114">The number of arguments.</span></span>  
  
## <span data-ttu-id="52eff-115">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="52eff-115">Property Value/Return Value</span></span>  
 <span data-ttu-id="52eff-116">呼叫的结果（如果有）。</span><span class="sxs-lookup"><span data-stu-id="52eff-116">The result of the call, if any.</span></span>  
  
## <span data-ttu-id="52eff-117">要求</span><span class="sxs-lookup"><span data-stu-id="52eff-117">Requirements</span></span>  
 <span data-ttu-id="52eff-118">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="52eff-118">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="52eff-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="52eff-119">See Also</span></span>  
 [<span data-ttu-id="52eff-120">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="52eff-120">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
