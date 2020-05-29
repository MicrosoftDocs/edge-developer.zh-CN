---
description: 创建新的 JavaScript 函数。
title: JsCreateFunction 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsCreateFunction
helpviewer_keywords:
- JsCreateFunction function
ms.assetid: b298a96a-5ef7-4203-a8c8-55f9bfc6d2bb
caps.latest.revision: 13
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 22585afcb379c281eda621c3b233ccf4bc278ad1
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563164"
---
# <span data-ttu-id="09bac-103">JsCreateFunction 函数</span><span class="sxs-lookup"><span data-stu-id="09bac-103">JsCreateFunction Function</span></span>
<span data-ttu-id="09bac-104">创建新的 JavaScript 函数。</span><span class="sxs-lookup"><span data-stu-id="09bac-104">Creates a new JavaScript function.</span></span>
  
## <span data-ttu-id="09bac-105">语法</span><span class="sxs-lookup"><span data-stu-id="09bac-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateFunction(  
   _In_ JsNativeFunction nativeFunction,  
   _In_opt_ void *callbackState,  
   _Out_ JsValueRef *function  
);  
```  
  
#### <span data-ttu-id="09bac-106">参数</span><span class="sxs-lookup"><span data-stu-id="09bac-106">Parameters</span></span>  
 `nativeFunction`  
 <span data-ttu-id="09bac-107">调用函数时调用的方法。</span><span class="sxs-lookup"><span data-stu-id="09bac-107">The method to call when the function is invoked.</span></span>  
  
 `callbackState`  
 <span data-ttu-id="09bac-108">用户提供的状态将传回回调。</span><span class="sxs-lookup"><span data-stu-id="09bac-108">User-provided state that will be passed back to the callback.</span></span>  
  
 `function`  
 <span data-ttu-id="09bac-109">新的函数对象。</span><span class="sxs-lookup"><span data-stu-id="09bac-109">The new function object.</span></span>  
  
## <span data-ttu-id="09bac-110">返回值</span><span class="sxs-lookup"><span data-stu-id="09bac-110">Return Value</span></span>  
 <span data-ttu-id="09bac-111">通话的结果（如果有）。</span><span class="sxs-lookup"><span data-stu-id="09bac-111">The result of the call, if any.</span></span>  
  
## <span data-ttu-id="09bac-112">备注</span><span class="sxs-lookup"><span data-stu-id="09bac-112">Remarks</span></span>  
 <span data-ttu-id="09bac-113">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="09bac-113">Requires an active script context.</span></span>  
  
## <span data-ttu-id="09bac-114">要求</span><span class="sxs-lookup"><span data-stu-id="09bac-114">Requirements</span></span>  
 <span data-ttu-id="09bac-115">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="09bac-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="09bac-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="09bac-116">See Also</span></span>  
 [<span data-ttu-id="09bac-117">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="09bac-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)