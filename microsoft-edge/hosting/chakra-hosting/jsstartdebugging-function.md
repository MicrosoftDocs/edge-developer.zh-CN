---
description: 在当前上下文中开始调试。
title: JsStartDebugging 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsStartDebugging
helpviewer_keywords:
- JsStartDebugging function
ms.assetid: c48ba02d-6d47-466f-a970-02f087d525f3
caps.latest.revision: 15
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 2c94a6f36ad72bfb9354c85d98ae0b5b4e9c77fb
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564072"
---
# <span data-ttu-id="7eed1-103">JsStartDebugging 函数</span><span class="sxs-lookup"><span data-stu-id="7eed1-103">JsStartDebugging Function</span></span>
<span data-ttu-id="7eed1-104">在当前上下文中开始调试。</span><span class="sxs-lookup"><span data-stu-id="7eed1-104">Starts debugging in the current context.</span></span>  
  
## <span data-ttu-id="7eed1-105">语法</span><span class="sxs-lookup"><span data-stu-id="7eed1-105">Syntax</span></span>  
  
```cpp  
// Microsoft Edge mode signature  
STDAPI_(JsErrorCode) JsStartDebugging();  
  
// Legacy mode signature  
STDAPI_(JsErrorCode)  JsStartDebugging(  
   _In_ IDebugApplication *debugApplication  
);  
```  
  
#### <span data-ttu-id="7eed1-106">参数</span><span class="sxs-lookup"><span data-stu-id="7eed1-106">Parameters</span></span>  
 `debugApplication`  
 <span data-ttu-id="7eed1-107">用于调试的调试应用程序。</span><span class="sxs-lookup"><span data-stu-id="7eed1-107">The debug application to use for debugging.</span></span>  
  
## <span data-ttu-id="7eed1-108">返回值</span><span class="sxs-lookup"><span data-stu-id="7eed1-108">Return Value</span></span>  
 <span data-ttu-id="7eed1-109">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="7eed1-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="7eed1-110">备注</span><span class="sxs-lookup"><span data-stu-id="7eed1-110">Remarks</span></span>  
 <span data-ttu-id="7eed1-111">在使用此 API 之前，主机应确保使用 `CoInitializeEx` `COINIT_MULTITHREADED` 或 `COINIT_APARTMENTTHREADED` 至少一次进行调用</span><span class="sxs-lookup"><span data-stu-id="7eed1-111">The host should make sure that `CoInitializeEx` is called with `COINIT_MULTITHREADED` or `COINIT_APARTMENTTHREADED` at least once before using this API</span></span>  
  
 <span data-ttu-id="7eed1-112">`debugApplication`Microsoft Edge 模式不支持该参数。</span><span class="sxs-lookup"><span data-stu-id="7eed1-112">The `debugApplication` parameter is not supported in Microsoft Edge mode.</span></span> <span data-ttu-id="7eed1-113">有关在 Microsoft Edge 模式中使用此 API 的详细信息，请参阅确定[Microsoft edge 与传统引擎的目标](../chakra-hosting/targeting-edge-vs-legacy-engines-in-jsrt-apis.md)。</span><span class="sxs-lookup"><span data-stu-id="7eed1-113">For more information on using this API in Microsoft Edge mode, see [Targeting Microsoft Edge vs. Legacy Engines](../chakra-hosting/targeting-edge-vs-legacy-engines-in-jsrt-apis.md).</span></span>  
  
## <span data-ttu-id="7eed1-114">要求</span><span class="sxs-lookup"><span data-stu-id="7eed1-114">Requirements</span></span>  
 <span data-ttu-id="7eed1-115">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="7eed1-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="7eed1-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7eed1-116">See Also</span></span>  
 [<span data-ttu-id="7eed1-117">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="7eed1-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)