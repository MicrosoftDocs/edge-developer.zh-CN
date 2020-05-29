---
description: 获取上下文所属的运行时。
title: JsGetRuntime 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsGetRuntime
helpviewer_keywords:
- JsGetRuntime function
ms.assetid: 5b62e940-a885-405a-9fdd-0495fb391b95
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 6eeb132dd35fcb5104828bef8e8f27334a5f34e4
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563112"
---
# <span data-ttu-id="ebe22-103">JsGetRuntime 函数</span><span class="sxs-lookup"><span data-stu-id="ebe22-103">JsGetRuntime Function</span></span>
<span data-ttu-id="ebe22-104">获取上下文所属的运行时。</span><span class="sxs-lookup"><span data-stu-id="ebe22-104">Gets the runtime that the context belongs to.</span></span>  
  
## <span data-ttu-id="ebe22-105">语法</span><span class="sxs-lookup"><span data-stu-id="ebe22-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetRuntime(  
   _In_ JsContextRef context,  
   _Out_ JsRuntimeHandle *runtime  
);  
```  
  
#### <span data-ttu-id="ebe22-106">参数</span><span class="sxs-lookup"><span data-stu-id="ebe22-106">Parameters</span></span>  
 `context`  
 <span data-ttu-id="ebe22-107">要从中获取运行时的上下文。</span><span class="sxs-lookup"><span data-stu-id="ebe22-107">The context to get the runtime from.</span></span>  
  
 `runtime`  
 <span data-ttu-id="ebe22-108">上下文所属的运行时。</span><span class="sxs-lookup"><span data-stu-id="ebe22-108">The runtime the context belongs to.</span></span>  
  
## <span data-ttu-id="ebe22-109">返回值</span><span class="sxs-lookup"><span data-stu-id="ebe22-109">Return Value</span></span>  
 <span data-ttu-id="ebe22-110">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="ebe22-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="ebe22-111">要求</span><span class="sxs-lookup"><span data-stu-id="ebe22-111">Requirements</span></span>  
 <span data-ttu-id="ebe22-112">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="ebe22-112">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="ebe22-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ebe22-113">See Also</span></span>  
 [<span data-ttu-id="ebe22-114">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="ebe22-114">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)