---
description: 获取当前脚本上下文中的全局对象。
title: JsGetGlobalObject 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsGetGlobalObject
helpviewer_keywords:
- JsGetGlobalObject function
ms.assetid: d3e91e64-1ca3-4d2b-aada-725ded0fd0b1
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: cda960710180c135b99abd359d0cc76776ff0225
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232442"
---
# <span data-ttu-id="a16ee-103">JsGetGlobalObject 函数</span><span class="sxs-lookup"><span data-stu-id="a16ee-103">JsGetGlobalObject Function</span></span>

<span data-ttu-id="a16ee-104">获取当前脚本上下文中的全局对象。</span><span class="sxs-lookup"><span data-stu-id="a16ee-104">Gets the global object in the current script context.</span></span>  
  
## <span data-ttu-id="a16ee-105">语法</span><span class="sxs-lookup"><span data-stu-id="a16ee-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetGlobalObject(  
   _Out_ JsValueRef *globalObject  
);  
```  
  
#### <span data-ttu-id="a16ee-106">参数</span><span class="sxs-lookup"><span data-stu-id="a16ee-106">Parameters</span></span>  
 `globalObject`  
 <span data-ttu-id="a16ee-107">全局对象。</span><span class="sxs-lookup"><span data-stu-id="a16ee-107">The global object.</span></span>  
  
## <span data-ttu-id="a16ee-108">返回值</span><span class="sxs-lookup"><span data-stu-id="a16ee-108">Return Value</span></span>  
 <span data-ttu-id="a16ee-109">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="a16ee-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="a16ee-110">备注</span><span class="sxs-lookup"><span data-stu-id="a16ee-110">Remarks</span></span>  
 <span data-ttu-id="a16ee-111">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="a16ee-111">Requires an active script context.</span></span>  
  
## <span data-ttu-id="a16ee-112">要求</span><span class="sxs-lookup"><span data-stu-id="a16ee-112">Requirements</span></span>  
 <span data-ttu-id="a16ee-113">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="a16ee-113">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="a16ee-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a16ee-114">See Also</span></span>  
 [<span data-ttu-id="a16ee-115">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="a16ee-115">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
