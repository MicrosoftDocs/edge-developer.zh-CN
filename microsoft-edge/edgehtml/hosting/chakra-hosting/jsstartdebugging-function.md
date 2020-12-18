---
description: 在当前上下文中开始调试。
title: JsStartDebugging 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsStartDebugging
helpviewer_keywords:
- JsStartDebugging function
ms.assetid: c48ba02d-6d47-466f-a970-02f087d525f3
caps.latest.revision: 15
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 9685779911db8e3045986682b66d13e38c70fe8d
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232693"
---
# <span data-ttu-id="752a4-103">JsStartDebugging 函数</span><span class="sxs-lookup"><span data-stu-id="752a4-103">JsStartDebugging Function</span></span>

<span data-ttu-id="752a4-104">在当前上下文中开始调试。</span><span class="sxs-lookup"><span data-stu-id="752a4-104">Starts debugging in the current context.</span></span>  
  
## <span data-ttu-id="752a4-105">语法</span><span class="sxs-lookup"><span data-stu-id="752a4-105">Syntax</span></span>  
  
```cpp  
// Microsoft Edge mode signature  
STDAPI_(JsErrorCode) JsStartDebugging();  
  
// Legacy mode signature  
STDAPI_(JsErrorCode)  JsStartDebugging(  
   _In_ IDebugApplication *debugApplication  
);  
```  
  
#### <span data-ttu-id="752a4-106">参数</span><span class="sxs-lookup"><span data-stu-id="752a4-106">Parameters</span></span>  
 `debugApplication`  
 <span data-ttu-id="752a4-107">用于调试的调试应用程序。</span><span class="sxs-lookup"><span data-stu-id="752a4-107">The debug application to use for debugging.</span></span>  
  
## <span data-ttu-id="752a4-108">返回值</span><span class="sxs-lookup"><span data-stu-id="752a4-108">Return Value</span></span>  
 <span data-ttu-id="752a4-109">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="752a4-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="752a4-110">备注</span><span class="sxs-lookup"><span data-stu-id="752a4-110">Remarks</span></span>  
 <span data-ttu-id="752a4-111">在使用此 API 之前，主机应确保使用或 `CoInitializeEx` `COINIT_MULTITHREADED` 至少调用 `COINIT_APARTMENTTHREADED` 一次</span><span class="sxs-lookup"><span data-stu-id="752a4-111">The host should make sure that `CoInitializeEx` is called with `COINIT_MULTITHREADED` or `COINIT_APARTMENTTHREADED` at least once before using this API</span></span>  
  
 <span data-ttu-id="752a4-112">Microsoft `debugApplication` Edge 模式不支持此参数。</span><span class="sxs-lookup"><span data-stu-id="752a4-112">The `debugApplication` parameter is not supported in Microsoft Edge mode.</span></span> <span data-ttu-id="752a4-113">有关在 Microsoft Edge 模式下使用此 API 有关详细信息，请参阅"面向 Microsoft Edge 与[旧版引擎"。](../chakra-hosting/targeting-edge-vs-legacy-engines-in-jsrt-apis.md)</span><span class="sxs-lookup"><span data-stu-id="752a4-113">For more information on using this API in Microsoft Edge mode, see [Targeting Microsoft Edge vs. Legacy Engines](../chakra-hosting/targeting-edge-vs-legacy-engines-in-jsrt-apis.md).</span></span>  
  
## <span data-ttu-id="752a4-114">要求</span><span class="sxs-lookup"><span data-stu-id="752a4-114">Requirements</span></span>  
 <span data-ttu-id="752a4-115">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="752a4-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="752a4-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="752a4-116">See Also</span></span>  
 [<span data-ttu-id="752a4-117">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="752a4-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
