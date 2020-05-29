---
description: 使用名称创建新的 JavaScript 函数。
title: JsCreateNamedFunction 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 72f40d06-ab82-4fed-a632-68af6b4126c2
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: d963fe196b8e56394e22501ed3898a0d887a3d3b
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563162"
---
# <span data-ttu-id="fda31-103">JsCreateNamedFunction 函数</span><span class="sxs-lookup"><span data-stu-id="fda31-103">JsCreateNamedFunction Function</span></span>
<span data-ttu-id="fda31-104">使用名称创建新的 JavaScript 函数。</span><span class="sxs-lookup"><span data-stu-id="fda31-104">Creates a new JavaScript function with name.</span></span>
  
## <span data-ttu-id="fda31-105">语法</span><span class="sxs-lookup"><span data-stu-id="fda31-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateNamedFunction(  
   _In_ JsValueRef name,  
   _In_ JsNativeFunction nativeFunction,  
   _In_opt_ void *callbackState,  
   _Out_ JsValueRef *function  
);  
```  
  
#### <span data-ttu-id="fda31-106">参数</span><span class="sxs-lookup"><span data-stu-id="fda31-106">Parameters</span></span>  
 `name`  
 <span data-ttu-id="fda31-107">将用于诊断和 stringification 用途的此函数的名称。</span><span class="sxs-lookup"><span data-stu-id="fda31-107">The name of this function that will be used for diagnostics and stringification purposes.</span></span>  
  
 `nativeFunction`  
 <span data-ttu-id="fda31-108">调用函数时调用的方法。</span><span class="sxs-lookup"><span data-stu-id="fda31-108">The method to call when the function is invoked.</span></span>  
  
 `callbackState`  
 <span data-ttu-id="fda31-109">用户提供的状态将传回回拨。</span><span class="sxs-lookup"><span data-stu-id="fda31-109">User provided state that will be passed back to the callback.</span></span>  
  
 `function`  
 <span data-ttu-id="fda31-110">新的函数对象。</span><span class="sxs-lookup"><span data-stu-id="fda31-110">The new function object.</span></span>  
  
## <span data-ttu-id="fda31-111">返回值</span><span class="sxs-lookup"><span data-stu-id="fda31-111">Return Value</span></span>  
  
## <span data-ttu-id="fda31-112">备注</span><span class="sxs-lookup"><span data-stu-id="fda31-112">Remarks</span></span>  
 <span data-ttu-id="fda31-113">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="fda31-113">Requires an active script context.</span></span>  
  
 <span data-ttu-id="fda31-114">此 API 仅在 Microsoft Edge 模式下受支持。</span><span class="sxs-lookup"><span data-stu-id="fda31-114">This API is supported only in Microsoft Edge mode.</span></span>  
  
## <span data-ttu-id="fda31-115">要求</span><span class="sxs-lookup"><span data-stu-id="fda31-115">Requirements</span></span>  
 <span data-ttu-id="fda31-116">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="fda31-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="fda31-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fda31-117">See Also</span></span>  
 [<span data-ttu-id="fda31-118">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="fda31-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)