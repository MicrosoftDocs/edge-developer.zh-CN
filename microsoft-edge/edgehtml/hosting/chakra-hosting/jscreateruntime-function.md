---
description: 创建新的运行时。
title: JsCreateRuntime 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsCreateRuntime
helpviewer_keywords:
- JsCreateRuntime function
ms.assetid: 92d09b89-6593-4d73-a562-88f9fec10228
caps.latest.revision: 15
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 3b893bd75725d6d9da56417ba83adfce18d77bac
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232419"
---
# <span data-ttu-id="3098b-103">JsCreateRuntime 函数</span><span class="sxs-lookup"><span data-stu-id="3098b-103">JsCreateRuntime Function</span></span>

<span data-ttu-id="3098b-104">创建新的运行时。</span><span class="sxs-lookup"><span data-stu-id="3098b-104">Creates a new runtime.</span></span>
  
## <span data-ttu-id="3098b-105">语法</span><span class="sxs-lookup"><span data-stu-id="3098b-105">Syntax</span></span>  
  
```cpp  
// Microsoft Edge mode signature  
STDAPI_(JsErrorCode) JsCreateRuntime(  
   _In_ JsRuntimeAttributes attributes,  
   _In_opt_ JsThreadServiceCallback threadService,  
   _Out_ JsRuntimeHandle *runtime);  
  
// Legacy mode signature  
STDAPI_(JsErrorCode) JsCreateRuntime(  
   _In_ JsRuntimeAttributes attributes,  
   _In_ JsRuntimeVersion version,  
   _In_opt_ JsThreadServiceCallback threadService,  
   _Out_ JsRuntimeHandle *runtime  
);  
```  
  
#### <span data-ttu-id="3098b-106">参数</span><span class="sxs-lookup"><span data-stu-id="3098b-106">Parameters</span></span>  
 `attributes`  
 <span data-ttu-id="3098b-107">要创建的运行时的属性。</span><span class="sxs-lookup"><span data-stu-id="3098b-107">The attributes of the runtime to be created.</span></span>  
  
 `version`  
 <span data-ttu-id="3098b-108">要创建的运行时的版本。</span><span class="sxs-lookup"><span data-stu-id="3098b-108">The version of the runtime to be created.</span></span>  
  
 `threadService`  
 <span data-ttu-id="3098b-109">运行时的线程服务。</span><span class="sxs-lookup"><span data-stu-id="3098b-109">The thread service for the runtime.</span></span> <span data-ttu-id="3098b-110">可以是 null。</span><span class="sxs-lookup"><span data-stu-id="3098b-110">Can be null.</span></span>  
  
 `runtime`  
 <span data-ttu-id="3098b-111">创建的运行时。</span><span class="sxs-lookup"><span data-stu-id="3098b-111">The runtime created.</span></span>  
  
## <span data-ttu-id="3098b-112">返回值</span><span class="sxs-lookup"><span data-stu-id="3098b-112">Return Value</span></span>  
 <span data-ttu-id="3098b-113">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="3098b-113">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="3098b-114">备注</span><span class="sxs-lookup"><span data-stu-id="3098b-114">Remarks</span></span>  
 <span data-ttu-id="3098b-115">Microsoft `version` Edge 模式不支持此参数。</span><span class="sxs-lookup"><span data-stu-id="3098b-115">The `version` parameter is not supported in Microsoft Edge mode.</span></span> <span data-ttu-id="3098b-116">有关在 Microsoft Edge 模式下使用此 API 有关详细信息，请参阅"面向 Microsoft Edge 与[旧版引擎"。](../chakra-hosting/targeting-edge-vs-legacy-engines-in-jsrt-apis.md)</span><span class="sxs-lookup"><span data-stu-id="3098b-116">For more information on using this API in Microsoft Edge mode, see [Targeting Microsoft Edge vs. Legacy Engines](../chakra-hosting/targeting-edge-vs-legacy-engines-in-jsrt-apis.md).</span></span>  
  
## <span data-ttu-id="3098b-117">要求</span><span class="sxs-lookup"><span data-stu-id="3098b-117">Requirements</span></span>  
 <span data-ttu-id="3098b-118">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="3098b-118">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="3098b-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3098b-119">See Also</span></span>  
 [<span data-ttu-id="3098b-120">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="3098b-120">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
