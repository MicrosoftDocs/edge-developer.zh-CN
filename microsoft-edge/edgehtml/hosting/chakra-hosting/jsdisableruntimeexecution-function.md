---
description: 暂停脚本执行并终止运行时中任何正在运行的脚本。
title: JsDisableRuntimeExecution 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsDisableRuntimeExecution
helpviewer_keywords:
- JsDisableRuntimeExecution function
ms.assetid: 4bd4670a-a9da-4f8c-b3fd-1fd366d915c3
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 6a08e6a7f89c724f8cf1a73afd97d2cb23c0334e
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232401"
---
# <span data-ttu-id="6b764-103">JsDisableRuntimeExecution 函数</span><span class="sxs-lookup"><span data-stu-id="6b764-103">JsDisableRuntimeExecution Function</span></span>

<span data-ttu-id="6b764-104">暂停脚本执行并终止运行时中任何正在运行的脚本。</span><span class="sxs-lookup"><span data-stu-id="6b764-104">Suspends script execution and terminates any running scripts in a runtime.</span></span>  
  
## <span data-ttu-id="6b764-105">语法</span><span class="sxs-lookup"><span data-stu-id="6b764-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsDisableRuntimeExecution(  
   _In_ JsRuntimeHandle runtime  
);  
```  
  
#### <span data-ttu-id="6b764-106">参数</span><span class="sxs-lookup"><span data-stu-id="6b764-106">Parameters</span></span>  
 `runtime`  
 <span data-ttu-id="6b764-107">要挂起的运行时。</span><span class="sxs-lookup"><span data-stu-id="6b764-107">The runtime to be suspended.</span></span>  
  
## <span data-ttu-id="6b764-108">返回值</span><span class="sxs-lookup"><span data-stu-id="6b764-108">Return Value</span></span>  
 <span data-ttu-id="6b764-109">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="6b764-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="6b764-110">备注</span><span class="sxs-lookup"><span data-stu-id="6b764-110">Remarks</span></span>  
 <span data-ttu-id="6b764-111">调用暂停的运行时将失败，直到 `JsEnableRuntimeExecution` 被调用。</span><span class="sxs-lookup"><span data-stu-id="6b764-111">Calls to a suspended runtime will fail until `JsEnableRuntimeExecution` is called.</span></span>  
  
 <span data-ttu-id="6b764-112">无需在运行时处于活动状态的线程上调用此 API。</span><span class="sxs-lookup"><span data-stu-id="6b764-112">This API does not have to be called on the thread the runtime is active on.</span></span> <span data-ttu-id="6b764-113">尽管运行时将设置为挂起状态，但执行脚本可能不会立即挂起;正在运行的脚本将尽快终止，并出现不可捕获的异常。</span><span class="sxs-lookup"><span data-stu-id="6b764-113">Although the runtime will be set into a suspended state, an executing script may not be suspended immediately; a running script will be terminated with an uncatchable exception as soon as possible.</span></span>  
  
 <span data-ttu-id="6b764-114">在已暂停的运行时中暂停执行是无操作。</span><span class="sxs-lookup"><span data-stu-id="6b764-114">Suspending execution in a runtime that is already suspended is a no-op.</span></span>  
  
## <span data-ttu-id="6b764-115">要求</span><span class="sxs-lookup"><span data-stu-id="6b764-115">Requirements</span></span>  
 <span data-ttu-id="6b764-116">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="6b764-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="6b764-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6b764-117">See Also</span></span>  
 [<span data-ttu-id="6b764-118">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="6b764-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
