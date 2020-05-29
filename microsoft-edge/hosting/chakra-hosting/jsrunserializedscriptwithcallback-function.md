---
description: 运行序列化脚本。 仅当需要时，才提供延迟加载脚本源的功能。
title: JsRunSerializedScriptWithCallback 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0608d778-f65b-4dc5-a745-364aac57ef59
caps.latest.revision: 4
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 31669615d5e00cb2dbe3730ed20e24d904161f8b
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564197"
---
# <span data-ttu-id="fd522-104">JsRunSerializedScriptWithCallback 函数</span><span class="sxs-lookup"><span data-stu-id="fd522-104">JsRunSerializedScriptWithCallback Function</span></span>
<span data-ttu-id="fd522-105">运行序列化脚本。</span><span class="sxs-lookup"><span data-stu-id="fd522-105">Runs a serialized script.</span></span> <span data-ttu-id="fd522-106">仅当需要时，才提供延迟加载脚本源的功能。</span><span class="sxs-lookup"><span data-stu-id="fd522-106">Provides the ability to lazy load the script source only if/when it is needed.</span></span>  
  
## <span data-ttu-id="fd522-107">语法</span><span class="sxs-lookup"><span data-stu-id="fd522-107">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsRunSerializedScriptWithCallback(  
  _In_ JsSerializedScriptLoadSourceCallback scriptLoadCallback,  
  _In_ JsSerializedScriptUnloadCallback scriptUnloadCallback,  
  _In_ BYTE *buffer,  
  _In_ JsSourceContext sourceContext,  
  _In_z_ const wchar_t *sourceUrl,  
  _Out_opt_ JsValueRef *result  
);  
  
```  
  
#### <span data-ttu-id="fd522-108">参数</span><span class="sxs-lookup"><span data-stu-id="fd522-108">Parameters</span></span>  
 `scriptLoadCallback`  
 <span data-ttu-id="fd522-109">回调需要加载脚本的源代码时调用。</span><span class="sxs-lookup"><span data-stu-id="fd522-109">Callback called when the source code of the script needs to be loaded.</span></span>  
  
 `scriptUnloadCallback`  
 <span data-ttu-id="fd522-110">当不再需要序列化脚本和源代码时调用回调。</span><span class="sxs-lookup"><span data-stu-id="fd522-110">Callback called when the serialized script and source code are no longer needed.</span></span>  
  
 `buffer`  
 <span data-ttu-id="fd522-111">序列化脚本。</span><span class="sxs-lookup"><span data-stu-id="fd522-111">The serialized script.</span></span>  
  
 `sourceContext`  
 <span data-ttu-id="fd522-112">标识可由可调试脚本上下文使用的脚本的 cookie。</span><span class="sxs-lookup"><span data-stu-id="fd522-112">A cookie identifying the script that can be used by debuggable script contexts.</span></span>     <span data-ttu-id="fd522-113">此上下文将传递到 scriptLoadCallback 和 scriptUnloadCallback。</span><span class="sxs-lookup"><span data-stu-id="fd522-113">This context will passed into scriptLoadCallback and scriptUnloadCallback.</span></span>  
  
 `sourceUrl`  
 <span data-ttu-id="fd522-114">脚本的来源位置。</span><span class="sxs-lookup"><span data-stu-id="fd522-114">The location the script came from.</span></span>  
  
 `result`  
 <span data-ttu-id="fd522-115">运行脚本的结果（如果有）。</span><span class="sxs-lookup"><span data-stu-id="fd522-115">The result of running the script, if any.</span></span> <span data-ttu-id="fd522-116">此参数可以为 null。</span><span class="sxs-lookup"><span data-stu-id="fd522-116">This parameter can be null.</span></span>  
  
## <span data-ttu-id="fd522-117">返回值</span><span class="sxs-lookup"><span data-stu-id="fd522-117">Return Value</span></span>  
 <span data-ttu-id="fd522-118">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="fd522-118">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="fd522-119">备注</span><span class="sxs-lookup"><span data-stu-id="fd522-119">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fd522-120">此 API 尚不可用于应用商店应用。</span><span class="sxs-lookup"><span data-stu-id="fd522-120">This API is not yet available for Store apps.</span></span>  
  
 <span data-ttu-id="fd522-121">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="fd522-121">Requires an active script context.</span></span>  
  
 <span data-ttu-id="fd522-122">运行时将一直保留到缓冲区，直到从缓冲区创建的所有函数的所有实例都被垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="fd522-122">The runtime will hold on to the buffer until all instances of any functions created from     the buffer are garbage collected.</span></span>  <span data-ttu-id="fd522-123">然后，它将调用 scriptUnloadCallback 以通知呼叫者安全释放。</span><span class="sxs-lookup"><span data-stu-id="fd522-123">It will then call scriptUnloadCallback to inform the     caller that it is safe to release.</span></span>  
  
## <span data-ttu-id="fd522-124">要求</span><span class="sxs-lookup"><span data-stu-id="fd522-124">Requirements</span></span>  
 <span data-ttu-id="fd522-125">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="fd522-125">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="fd522-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fd522-126">See Also</span></span>  
 [<span data-ttu-id="fd522-127">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="fd522-127">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)