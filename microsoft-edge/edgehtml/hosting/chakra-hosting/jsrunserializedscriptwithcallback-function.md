---
description: 运行序列化脚本。 仅在需要脚本源时，才提供延迟加载脚本源的能力。
title: JsRunSerializedScriptWithCallback 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 0608d778-f65b-4dc5-a745-364aac57ef59
caps.latest.revision: 4
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: ac9ac08357cd479f78e3500bc5eef151fb8e4e6c
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232694"
---
# <span data-ttu-id="b827f-104">JsRunSerializedScriptWithCallback 函数</span><span class="sxs-lookup"><span data-stu-id="b827f-104">JsRunSerializedScriptWithCallback Function</span></span>

<span data-ttu-id="b827f-105">运行序列化脚本。</span><span class="sxs-lookup"><span data-stu-id="b827f-105">Runs a serialized script.</span></span> <span data-ttu-id="b827f-106">仅在需要脚本源时，才提供延迟加载脚本源的能力。</span><span class="sxs-lookup"><span data-stu-id="b827f-106">Provides the ability to lazy load the script source only if/when it is needed.</span></span>  
  
## <span data-ttu-id="b827f-107">语法</span><span class="sxs-lookup"><span data-stu-id="b827f-107">Syntax</span></span>  
  
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
  
#### <span data-ttu-id="b827f-108">参数</span><span class="sxs-lookup"><span data-stu-id="b827f-108">Parameters</span></span>  
 `scriptLoadCallback`  
 <span data-ttu-id="b827f-109">在需要加载脚本的源代码时调用的回调。</span><span class="sxs-lookup"><span data-stu-id="b827f-109">Callback called when the source code of the script needs to be loaded.</span></span>  
  
 `scriptUnloadCallback`  
 <span data-ttu-id="b827f-110">当不再需要序列化脚本和源代码时调用的回调。</span><span class="sxs-lookup"><span data-stu-id="b827f-110">Callback called when the serialized script and source code are no longer needed.</span></span>  
  
 `buffer`  
 <span data-ttu-id="b827f-111">序列化脚本。</span><span class="sxs-lookup"><span data-stu-id="b827f-111">The serialized script.</span></span>  
  
 `sourceContext`  
 <span data-ttu-id="b827f-112">用于标识可调试脚本上下文使用的脚本的 Cookie。</span><span class="sxs-lookup"><span data-stu-id="b827f-112">A cookie identifying the script that can be used by debuggable script contexts.</span></span>     <span data-ttu-id="b827f-113">此上下文将传递到 scriptLoadCallback 和 scriptUnloadCallback。</span><span class="sxs-lookup"><span data-stu-id="b827f-113">This context will passed into scriptLoadCallback and scriptUnloadCallback.</span></span>  
  
 `sourceUrl`  
 <span data-ttu-id="b827f-114">脚本来自的位置。</span><span class="sxs-lookup"><span data-stu-id="b827f-114">The location the script came from.</span></span>  
  
 `result`  
 <span data-ttu-id="b827f-115">运行脚本的结果（如果有）。</span><span class="sxs-lookup"><span data-stu-id="b827f-115">The result of running the script, if any.</span></span> <span data-ttu-id="b827f-116">此参数可以是 null。</span><span class="sxs-lookup"><span data-stu-id="b827f-116">This parameter can be null.</span></span>  
  
## <span data-ttu-id="b827f-117">返回值</span><span class="sxs-lookup"><span data-stu-id="b827f-117">Return Value</span></span>  
 <span data-ttu-id="b827f-118">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="b827f-118">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="b827f-119">备注</span><span class="sxs-lookup"><span data-stu-id="b827f-119">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b827f-120">此 API 尚不可用于应用商店应用。</span><span class="sxs-lookup"><span data-stu-id="b827f-120">This API is not yet available for Store apps.</span></span>  
  
 <span data-ttu-id="b827f-121">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="b827f-121">Requires an active script context.</span></span>  
  
 <span data-ttu-id="b827f-122">运行时将保持该缓冲区，直到从缓冲区创建的任何函数的所有实例都进行垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="b827f-122">The runtime will hold on to the buffer until all instances of any functions created from     the buffer are garbage collected.</span></span>  <span data-ttu-id="b827f-123">然后，它将调用 scriptUnloadCallback 以通知调用方安全释放。</span><span class="sxs-lookup"><span data-stu-id="b827f-123">It will then call scriptUnloadCallback to inform the     caller that it is safe to release.</span></span>  
  
## <span data-ttu-id="b827f-124">要求</span><span class="sxs-lookup"><span data-stu-id="b827f-124">Requirements</span></span>  
 <span data-ttu-id="b827f-125">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="b827f-125">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="b827f-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b827f-126">See Also</span></span>  
 [<span data-ttu-id="b827f-127">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="b827f-127">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
