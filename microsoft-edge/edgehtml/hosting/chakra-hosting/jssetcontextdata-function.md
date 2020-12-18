---
description: 设置 JsrtContext 的内部数据。
title: JsSetContextData 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: be90aa6a-b001-4a6f-90c5-c2135e913be0
caps.latest.revision: 4
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: cac404b9e79bafb5a8eafb47e893dbdf38a02405
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232519"
---
# <span data-ttu-id="89205-103">JsSetContextData 函数</span><span class="sxs-lookup"><span data-stu-id="89205-103">JsSetContextData Function</span></span>

<span data-ttu-id="89205-104">设置 JsrtContext 的内部数据。</span><span class="sxs-lookup"><span data-stu-id="89205-104">Sets the internal data of JsrtContext.</span></span>  
  
## <span data-ttu-id="89205-105">语法</span><span class="sxs-lookup"><span data-stu-id="89205-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsSetContextData(  
  _In_ JsContextRef context,  
  _In_ void *data  
);  
  
```  
  
#### <span data-ttu-id="89205-106">参数</span><span class="sxs-lookup"><span data-stu-id="89205-106">Parameters</span></span>  
 `context`  
 <span data-ttu-id="89205-107">要将数据设置为的上下文。</span><span class="sxs-lookup"><span data-stu-id="89205-107">The context to set the data to.</span></span>  
  
 `data`  
 <span data-ttu-id="89205-108">指向要设置的数据的指针。</span><span class="sxs-lookup"><span data-stu-id="89205-108">The pointer to the data to be set.</span></span>  
  
## <span data-ttu-id="89205-109">返回值</span><span class="sxs-lookup"><span data-stu-id="89205-109">Return Value</span></span>  
 <span data-ttu-id="89205-110">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="89205-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="89205-111">备注</span><span class="sxs-lookup"><span data-stu-id="89205-111">Remarks</span></span>  
 <span data-ttu-id="89205-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="89205-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="89205-113">要求</span><span class="sxs-lookup"><span data-stu-id="89205-113">Requirements</span></span>  
 <span data-ttu-id="89205-114">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="89205-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="89205-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="89205-115">See Also</span></span>  
 [<span data-ttu-id="89205-116">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="89205-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
