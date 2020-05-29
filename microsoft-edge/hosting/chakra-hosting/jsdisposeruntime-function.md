---
description: 释放运行时。
title: JsDisposeRuntime 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsDisposeRuntime
helpviewer_keywords:
- JsDisposeRuntime function
ms.assetid: 0aefde3f-7250-48be-afc5-53ea85c12f30
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 89166249616c265ce75ebc43a01c838d607bdd08
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564274"
---
# <span data-ttu-id="38fa0-103">JsDisposeRuntime 函数</span><span class="sxs-lookup"><span data-stu-id="38fa0-103">JsDisposeRuntime Function</span></span>
<span data-ttu-id="38fa0-104">释放运行时。</span><span class="sxs-lookup"><span data-stu-id="38fa0-104">Disposes a runtime.</span></span>  
  
## <span data-ttu-id="38fa0-105">语法</span><span class="sxs-lookup"><span data-stu-id="38fa0-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsDisposeRuntime(  
   _In_ JsRuntimeHandle runtime  
);  
```  
  
#### <span data-ttu-id="38fa0-106">参数</span><span class="sxs-lookup"><span data-stu-id="38fa0-106">Parameters</span></span>  
 `runtime`  
 <span data-ttu-id="38fa0-107">要释放的运行时。</span><span class="sxs-lookup"><span data-stu-id="38fa0-107">The runtime to dispose.</span></span>  
  
## <span data-ttu-id="38fa0-108">返回值</span><span class="sxs-lookup"><span data-stu-id="38fa0-108">Return Value</span></span>  
 <span data-ttu-id="38fa0-109">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="38fa0-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="38fa0-110">备注</span><span class="sxs-lookup"><span data-stu-id="38fa0-110">Remarks</span></span>  
 <span data-ttu-id="38fa0-111">当运行时已释放时，它所拥有的所有资源都无效，并且不能使用。</span><span class="sxs-lookup"><span data-stu-id="38fa0-111">Once a runtime has been disposed, all resources owned by it are invalid and cannot be used.</span></span> <span data-ttu-id="38fa0-112">如果运行时处于活动状态（即它在特定线程上设置为 "当前"），则无法释放它。</span><span class="sxs-lookup"><span data-stu-id="38fa0-112">If the runtime is active (i.e. it is set to be current on a particular thread), it cannot be disposed.</span></span>  
  
## <span data-ttu-id="38fa0-113">要求</span><span class="sxs-lookup"><span data-stu-id="38fa0-113">Requirements</span></span>  
 <span data-ttu-id="38fa0-114">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="38fa0-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="38fa0-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="38fa0-115">See Also</span></span>  
 [<span data-ttu-id="38fa0-116">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="38fa0-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)