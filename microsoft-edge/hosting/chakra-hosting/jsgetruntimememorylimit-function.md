---
description: 获取运行时的当前内存限制。
title: JsGetRuntimeMemoryLimit 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsGetRuntimeMemoryLimit
helpviewer_keywords:
- JsGetRuntimeMemoryLimit function
ms.assetid: ed81ca60-99fd-46b0-89ae-f6ac07926904
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: e6b44bb1dc8ad5fb8c07248a225c10682f96c86a
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563109"
---
# <span data-ttu-id="0bbda-103">JsGetRuntimeMemoryLimit 函数</span><span class="sxs-lookup"><span data-stu-id="0bbda-103">JsGetRuntimeMemoryLimit Function</span></span>
<span data-ttu-id="0bbda-104">获取运行时的当前内存限制。</span><span class="sxs-lookup"><span data-stu-id="0bbda-104">Gets the current memory limit for a runtime.</span></span>  
  
## <span data-ttu-id="0bbda-105">语法</span><span class="sxs-lookup"><span data-stu-id="0bbda-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetRuntimeMemoryLimit(  
   _In_ JsRuntimeHandle runtime,  
   _Out_ size_t *memoryLimit  
);  
```  
  
#### <span data-ttu-id="0bbda-106">参数</span><span class="sxs-lookup"><span data-stu-id="0bbda-106">Parameters</span></span>  
 `runtime`  
 <span data-ttu-id="0bbda-107">要检索其内存限制的运行时。</span><span class="sxs-lookup"><span data-stu-id="0bbda-107">The runtime whose memory limit is to be retrieved.</span></span>  
  
 `memoryLimit`  
 <span data-ttu-id="0bbda-108">运行时的当前内存限制（以字节为单位），如果未设置任何限制，则为-1。</span><span class="sxs-lookup"><span data-stu-id="0bbda-108">The runtime's current memory limit, in bytes, or -1 if no limit has been set.</span></span>  
  
## <span data-ttu-id="0bbda-109">返回值</span><span class="sxs-lookup"><span data-stu-id="0bbda-109">Return Value</span></span>  
 <span data-ttu-id="0bbda-110">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="0bbda-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="0bbda-111">备注</span><span class="sxs-lookup"><span data-stu-id="0bbda-111">Remarks</span></span>  
 <span data-ttu-id="0bbda-112">无论运行时是否在另一个线程上处于活动状态，都可以始终检索运行时的内存限制。</span><span class="sxs-lookup"><span data-stu-id="0bbda-112">The memory limit of a runtime can be always be retrieved, regardless of whether or not the runtime is active on another thread.</span></span>  
  
## <span data-ttu-id="0bbda-113">要求</span><span class="sxs-lookup"><span data-stu-id="0bbda-113">Requirements</span></span>  
 <span data-ttu-id="0bbda-114">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="0bbda-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="0bbda-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0bbda-115">See Also</span></span>  
 [<span data-ttu-id="0bbda-116">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="0bbda-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)