---
description: 运行序列化脚本。
title: JsRunSerializedScript 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsRunSerializedScript
helpviewer_keywords:
- JsRunSerializedScript function
ms.assetid: 3fd3f6f1-eb3e-4751-92a5-c93b1035f3b2
caps.latest.revision: 13
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: bc1e2fb7fdc5df52fde3b7cc59cf9173d658782a
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564202"
---
# <span data-ttu-id="7e982-103">JsRunSerializedScript 函数</span><span class="sxs-lookup"><span data-stu-id="7e982-103">JsRunSerializedScript Function</span></span>
<span data-ttu-id="7e982-104">运行序列化脚本。</span><span class="sxs-lookup"><span data-stu-id="7e982-104">Runs a serialized script.</span></span>  
  
## <span data-ttu-id="7e982-105">语法</span><span class="sxs-lookup"><span data-stu-id="7e982-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsRunSerializedScript(  
   _In_z_ const wchar_t *script,  
   _In_ BYTE *buffer,  
   _In_ JsSourceContext sourceContext,  
   _In_z_ const wchar_t *sourceUrl,  
   _Out_ JsValueRef *result  
);  
```  
  
#### <span data-ttu-id="7e982-106">参数</span><span class="sxs-lookup"><span data-stu-id="7e982-106">Parameters</span></span>  
 `script`  
 <span data-ttu-id="7e982-107">序列化脚本的源代码。</span><span class="sxs-lookup"><span data-stu-id="7e982-107">The source code of the serialized script.</span></span>  
  
 `buffer`  
 <span data-ttu-id="7e982-108">序列化脚本。</span><span class="sxs-lookup"><span data-stu-id="7e982-108">The serialized script.</span></span>  
  
 `sourceContext`  
 <span data-ttu-id="7e982-109">标识可由可调试脚本上下文使用的脚本的 cookie。</span><span class="sxs-lookup"><span data-stu-id="7e982-109">A cookie identifying the script that can be used by debuggable script contexts.</span></span>  
  
 `sourceUrl`  
 <span data-ttu-id="7e982-110">脚本的来源位置。</span><span class="sxs-lookup"><span data-stu-id="7e982-110">The location the script came from.</span></span>  
  
 `result`  
 <span data-ttu-id="7e982-111">运行脚本的结果（如果有）。</span><span class="sxs-lookup"><span data-stu-id="7e982-111">The result of running the script, if any.</span></span> <span data-ttu-id="7e982-112">此参数可以为 null。</span><span class="sxs-lookup"><span data-stu-id="7e982-112">This parameter can be null.</span></span>  
  
## <span data-ttu-id="7e982-113">返回值</span><span class="sxs-lookup"><span data-stu-id="7e982-113">Return Value</span></span>  
 <span data-ttu-id="7e982-114">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="7e982-114">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="7e982-115">备注</span><span class="sxs-lookup"><span data-stu-id="7e982-115">Remarks</span></span>  
 <span data-ttu-id="7e982-116">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="7e982-116">Requires an active script context.</span></span>  
  
 <span data-ttu-id="7e982-117">脚本引擎不会将缓冲区保留在内存中，因此你的代码必须保持活动状态，因为它可能会用于执行脚本。</span><span class="sxs-lookup"><span data-stu-id="7e982-117">The buffer is not persisted in memory by the scripting engine, so your code must keep it alive for as long as it might be used to execute scripts.</span></span>  
  
## <span data-ttu-id="7e982-118">要求</span><span class="sxs-lookup"><span data-stu-id="7e982-118">Requirements</span></span>  
 <span data-ttu-id="7e982-119">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="7e982-119">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="7e982-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7e982-120">See Also</span></span>  
 [<span data-ttu-id="7e982-121">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="7e982-121">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)