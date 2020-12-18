---
description: 分析序列化脚本并返回表示该脚本的函数。
title: JsParseSerializedScript 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsParseSerializedScript
helpviewer_keywords:
- JsParseSerializedScript function
ms.assetid: 40d0c7c4-fd5b-46ed-9e65-38c2db2fc859
caps.latest.revision: 13
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 66ecabb9d96c3f339625f93858444f55d25fd4d7
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232532"
---
# <span data-ttu-id="84f52-103">JsParseSerializedScript 函数</span><span class="sxs-lookup"><span data-stu-id="84f52-103">JsParseSerializedScript Function</span></span>

<span data-ttu-id="84f52-104">分析序列化脚本并返回表示该脚本的函数。</span><span class="sxs-lookup"><span data-stu-id="84f52-104">Parses a serialized script and returns a function representing the script.</span></span>  
  
## <span data-ttu-id="84f52-105">语法</span><span class="sxs-lookup"><span data-stu-id="84f52-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsParseSerializedScript(  
   _In_z_ const wchar_t *script,  
   _In_ BYTE *buffer,  
   _In_ JsSourceContext sourceContext,  
   _In_z_ const wchar_t *sourceUrl,  
   _Out_ JsValueRef *result  
);  
```  
  
#### <span data-ttu-id="84f52-106">参数</span><span class="sxs-lookup"><span data-stu-id="84f52-106">Parameters</span></span>  
 `script`  
 <span data-ttu-id="84f52-107">要分析的脚本。</span><span class="sxs-lookup"><span data-stu-id="84f52-107">The script to parse.</span></span>  
  
 `buffer`  
 <span data-ttu-id="84f52-108">序列化脚本。</span><span class="sxs-lookup"><span data-stu-id="84f52-108">The serialized script.</span></span>  
  
 `sourceContext`  
 <span data-ttu-id="84f52-109">用于标识可调试脚本上下文使用的脚本的 Cookie。</span><span class="sxs-lookup"><span data-stu-id="84f52-109">A cookie identifying the script that can be used by debuggable script contexts.</span></span>  
  
 `sourceUrl`  
 <span data-ttu-id="84f52-110">脚本来自的位置。</span><span class="sxs-lookup"><span data-stu-id="84f52-110">The location the script came from.</span></span>  
  
 `result`  
 <span data-ttu-id="84f52-111">一个代表脚本代码的函数。</span><span class="sxs-lookup"><span data-stu-id="84f52-111">A function representing the script code.</span></span>  
  
## <span data-ttu-id="84f52-112">返回值</span><span class="sxs-lookup"><span data-stu-id="84f52-112">Return Value</span></span>  
 <span data-ttu-id="84f52-113">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="84f52-113">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="84f52-114">备注</span><span class="sxs-lookup"><span data-stu-id="84f52-114">Remarks</span></span>  
 <span data-ttu-id="84f52-115">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="84f52-115">Requires an active script context.</span></span>  
  
 <span data-ttu-id="84f52-116">脚本引擎不会将缓冲区持久化到内存中，因此代码必须保持其活动状态，只要它可用于执行脚本。</span><span class="sxs-lookup"><span data-stu-id="84f52-116">The buffer is not persisted in memory by the scripting engine, so your code must keep it alive for as long as it might be used to execute scripts.</span></span>  
  
## <span data-ttu-id="84f52-117">要求</span><span class="sxs-lookup"><span data-stu-id="84f52-117">Requirements</span></span>  
 <span data-ttu-id="84f52-118">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="84f52-118">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="84f52-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="84f52-119">See Also</span></span>  
 [<span data-ttu-id="84f52-120">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="84f52-120">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
