---
description: 创建新的运行时。
title: JsCreateRuntime 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsCreateRuntime
helpviewer_keywords:
- JsCreateRuntime function
ms.assetid: 92d09b89-6593-4d73-a562-88f9fec10228
caps.latest.revision: 15
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: d25c1b46354be1fda0ce906dc68c3643989fe2c6
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563155"
---
# <span data-ttu-id="e1a53-103">JsCreateRuntime 函数</span><span class="sxs-lookup"><span data-stu-id="e1a53-103">JsCreateRuntime Function</span></span>
<span data-ttu-id="e1a53-104">创建新的运行时。</span><span class="sxs-lookup"><span data-stu-id="e1a53-104">Creates a new runtime.</span></span>
  
## <span data-ttu-id="e1a53-105">语法</span><span class="sxs-lookup"><span data-stu-id="e1a53-105">Syntax</span></span>  
  
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
  
#### <span data-ttu-id="e1a53-106">参数</span><span class="sxs-lookup"><span data-stu-id="e1a53-106">Parameters</span></span>  
 `attributes`  
 <span data-ttu-id="e1a53-107">要创建的运行时的属性。</span><span class="sxs-lookup"><span data-stu-id="e1a53-107">The attributes of the runtime to be created.</span></span>  
  
 `version`  
 <span data-ttu-id="e1a53-108">要创建的运行时的版本。</span><span class="sxs-lookup"><span data-stu-id="e1a53-108">The version of the runtime to be created.</span></span>  
  
 `threadService`  
 <span data-ttu-id="e1a53-109">运行时的线程服务。</span><span class="sxs-lookup"><span data-stu-id="e1a53-109">The thread service for the runtime.</span></span> <span data-ttu-id="e1a53-110">可以为 null。</span><span class="sxs-lookup"><span data-stu-id="e1a53-110">Can be null.</span></span>  
  
 `runtime`  
 <span data-ttu-id="e1a53-111">运行时创建。</span><span class="sxs-lookup"><span data-stu-id="e1a53-111">The runtime created.</span></span>  
  
## <span data-ttu-id="e1a53-112">返回值</span><span class="sxs-lookup"><span data-stu-id="e1a53-112">Return Value</span></span>  
 <span data-ttu-id="e1a53-113">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="e1a53-113">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="e1a53-114">备注</span><span class="sxs-lookup"><span data-stu-id="e1a53-114">Remarks</span></span>  
 <span data-ttu-id="e1a53-115">`version`Microsoft Edge 模式不支持该参数。</span><span class="sxs-lookup"><span data-stu-id="e1a53-115">The `version` parameter is not supported in Microsoft Edge mode.</span></span> <span data-ttu-id="e1a53-116">有关在 Microsoft Edge 模式中使用此 API 的详细信息，请参阅确定[Microsoft edge 与传统引擎的目标](../chakra-hosting/targeting-edge-vs-legacy-engines-in-jsrt-apis.md)。</span><span class="sxs-lookup"><span data-stu-id="e1a53-116">For more information on using this API in Microsoft Edge mode, see [Targeting Microsoft Edge vs. Legacy Engines](../chakra-hosting/targeting-edge-vs-legacy-engines-in-jsrt-apis.md).</span></span>  
  
## <span data-ttu-id="e1a53-117">要求</span><span class="sxs-lookup"><span data-stu-id="e1a53-117">Requirements</span></span>  
 <span data-ttu-id="e1a53-118">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="e1a53-118">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="e1a53-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e1a53-119">See Also</span></span>  
 [<span data-ttu-id="e1a53-120">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="e1a53-120">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)