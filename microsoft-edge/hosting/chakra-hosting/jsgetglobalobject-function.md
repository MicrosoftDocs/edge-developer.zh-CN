---
description: 获取当前脚本上下文中的全局对象。
title: JsGetGlobalObject 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsGetGlobalObject
helpviewer_keywords:
- JsGetGlobalObject function
ms.assetid: d3e91e64-1ca3-4d2b-aada-725ded0fd0b1
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 9f8b540485e75ef80d42ba66f031b3e827b475fa
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563120"
---
# <span data-ttu-id="c35fa-103">JsGetGlobalObject 函数</span><span class="sxs-lookup"><span data-stu-id="c35fa-103">JsGetGlobalObject Function</span></span>
<span data-ttu-id="c35fa-104">获取当前脚本上下文中的全局对象。</span><span class="sxs-lookup"><span data-stu-id="c35fa-104">Gets the global object in the current script context.</span></span>  
  
## <span data-ttu-id="c35fa-105">语法</span><span class="sxs-lookup"><span data-stu-id="c35fa-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetGlobalObject(  
   _Out_ JsValueRef *globalObject  
);  
```  
  
#### <span data-ttu-id="c35fa-106">参数</span><span class="sxs-lookup"><span data-stu-id="c35fa-106">Parameters</span></span>  
 `globalObject`  
 <span data-ttu-id="c35fa-107">全局对象。</span><span class="sxs-lookup"><span data-stu-id="c35fa-107">The global object.</span></span>  
  
## <span data-ttu-id="c35fa-108">返回值</span><span class="sxs-lookup"><span data-stu-id="c35fa-108">Return Value</span></span>  
 <span data-ttu-id="c35fa-109">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="c35fa-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="c35fa-110">备注</span><span class="sxs-lookup"><span data-stu-id="c35fa-110">Remarks</span></span>  
 <span data-ttu-id="c35fa-111">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="c35fa-111">Requires an active script context.</span></span>  
  
## <span data-ttu-id="c35fa-112">要求</span><span class="sxs-lookup"><span data-stu-id="c35fa-112">Requirements</span></span>  
 <span data-ttu-id="c35fa-113">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="c35fa-113">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="c35fa-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c35fa-114">See Also</span></span>  
 [<span data-ttu-id="c35fa-115">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="c35fa-115">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)