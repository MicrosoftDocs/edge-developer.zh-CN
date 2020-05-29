---
description: 返回一个值，该值指示是否正在枚举当前上下文的堆栈。
title: JsIsEnumeratingHeap 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsIsEnumeratingHeap
helpviewer_keywords:
- JsIsEnumeratingHeap function
ms.assetid: 5d14518e-3153-43f2-9a9c-068580cbd54f
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 79f263547ef5812d905103d09ede7499d56c5dfb
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563092"
---
# <span data-ttu-id="01935-103">JsIsEnumeratingHeap 函数</span><span class="sxs-lookup"><span data-stu-id="01935-103">JsIsEnumeratingHeap Function</span></span>
<span data-ttu-id="01935-104">返回一个值，该值指示是否正在枚举当前上下文的堆栈。</span><span class="sxs-lookup"><span data-stu-id="01935-104">Returns a value that indicates whether the heap of the current context is being enumerated.</span></span>  
  
## <span data-ttu-id="01935-105">语法</span><span class="sxs-lookup"><span data-stu-id="01935-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsIsEnumeratingHeap(  
   _Out_ bool *isEnumeratingHeap  
);  
```  
  
#### <span data-ttu-id="01935-106">参数</span><span class="sxs-lookup"><span data-stu-id="01935-106">Parameters</span></span>  
 `isEnumeratingHeap`  
 <span data-ttu-id="01935-107">是否枚举堆。</span><span class="sxs-lookup"><span data-stu-id="01935-107">Whether the heap is being enumerated.</span></span>  
  
## <span data-ttu-id="01935-108">返回值</span><span class="sxs-lookup"><span data-stu-id="01935-108">Return Value</span></span>  
 <span data-ttu-id="01935-109">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="01935-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="01935-110">备注</span><span class="sxs-lookup"><span data-stu-id="01935-110">Remarks</span></span>  
 <span data-ttu-id="01935-111">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="01935-111">Requires an active script context.</span></span>  
  
 <span data-ttu-id="01935-112">此 API 在桌面应用中受支持，但在应用商店应用中不受支持。</span><span class="sxs-lookup"><span data-stu-id="01935-112">This API is supported in desktop apps, but is not supported in Store apps.</span></span>  
  
## <span data-ttu-id="01935-113">要求</span><span class="sxs-lookup"><span data-stu-id="01935-113">Requirements</span></span>  
 <span data-ttu-id="01935-114">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="01935-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="01935-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="01935-115">See Also</span></span>  
 [<span data-ttu-id="01935-116">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="01935-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)