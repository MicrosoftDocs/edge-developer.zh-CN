---
description: 分析序列化脚本并返回表示脚本的函数。
title: JsParseSerializedScript 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsParseSerializedScript
helpviewer_keywords:
- JsParseSerializedScript function
ms.assetid: 40d0c7c4-fd5b-46ed-9e65-38c2db2fc859
caps.latest.revision: 13
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: a778a007e69f15063d23cc55f999144ab55a306c
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564216"
---
# <span data-ttu-id="7bc37-103">JsParseSerializedScript 函数</span><span class="sxs-lookup"><span data-stu-id="7bc37-103">JsParseSerializedScript Function</span></span>
<span data-ttu-id="7bc37-104">分析序列化脚本并返回表示脚本的函数。</span><span class="sxs-lookup"><span data-stu-id="7bc37-104">Parses a serialized script and returns a function representing the script.</span></span>  
  
## <span data-ttu-id="7bc37-105">语法</span><span class="sxs-lookup"><span data-stu-id="7bc37-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsParseSerializedScript(  
   _In_z_ const wchar_t *script,  
   _In_ BYTE *buffer,  
   _In_ JsSourceContext sourceContext,  
   _In_z_ const wchar_t *sourceUrl,  
   _Out_ JsValueRef *result  
);  
```  
  
#### <span data-ttu-id="7bc37-106">参数</span><span class="sxs-lookup"><span data-stu-id="7bc37-106">Parameters</span></span>  
 `script`  
 <span data-ttu-id="7bc37-107">要分析的脚本。</span><span class="sxs-lookup"><span data-stu-id="7bc37-107">The script to parse.</span></span>  
  
 `buffer`  
 <span data-ttu-id="7bc37-108">序列化脚本。</span><span class="sxs-lookup"><span data-stu-id="7bc37-108">The serialized script.</span></span>  
  
 `sourceContext`  
 <span data-ttu-id="7bc37-109">标识可由可调试脚本上下文使用的脚本的 cookie。</span><span class="sxs-lookup"><span data-stu-id="7bc37-109">A cookie identifying the script that can be used by debuggable script contexts.</span></span>  
  
 `sourceUrl`  
 <span data-ttu-id="7bc37-110">脚本的来源位置。</span><span class="sxs-lookup"><span data-stu-id="7bc37-110">The location the script came from.</span></span>  
  
 `result`  
 <span data-ttu-id="7bc37-111">表示脚本代码的函数。</span><span class="sxs-lookup"><span data-stu-id="7bc37-111">A function representing the script code.</span></span>  
  
## <span data-ttu-id="7bc37-112">返回值</span><span class="sxs-lookup"><span data-stu-id="7bc37-112">Return Value</span></span>  
 <span data-ttu-id="7bc37-113">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="7bc37-113">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="7bc37-114">备注</span><span class="sxs-lookup"><span data-stu-id="7bc37-114">Remarks</span></span>  
 <span data-ttu-id="7bc37-115">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="7bc37-115">Requires an active script context.</span></span>  
  
 <span data-ttu-id="7bc37-116">脚本引擎不会将缓冲区保留在内存中，因此你的代码必须保持活动状态，因为它可能会用于执行脚本。</span><span class="sxs-lookup"><span data-stu-id="7bc37-116">The buffer is not persisted in memory by the scripting engine, so your code must keep it alive for as long as it might be used to execute scripts.</span></span>  
  
## <span data-ttu-id="7bc37-117">要求</span><span class="sxs-lookup"><span data-stu-id="7bc37-117">Requirements</span></span>  
 <span data-ttu-id="7bc37-118">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="7bc37-118">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="7bc37-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7bc37-119">See Also</span></span>  
 [<span data-ttu-id="7bc37-120">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="7bc37-120">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)