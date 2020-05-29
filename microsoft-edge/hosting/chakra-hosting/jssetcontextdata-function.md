---
description: 设置 JsrtContext 的内部数据。
title: JsSetContextData 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: be90aa6a-b001-4a6f-90c5-c2135e913be0
caps.latest.revision: 4
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 00521bafdaf6125dd15746de8a1d403eaf03b4a0
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564184"
---
# <span data-ttu-id="993f3-103">JsSetContextData 函数</span><span class="sxs-lookup"><span data-stu-id="993f3-103">JsSetContextData Function</span></span>
<span data-ttu-id="993f3-104">设置 JsrtContext 的内部数据。</span><span class="sxs-lookup"><span data-stu-id="993f3-104">Sets the internal data of JsrtContext.</span></span>  
  
## <span data-ttu-id="993f3-105">语法</span><span class="sxs-lookup"><span data-stu-id="993f3-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsSetContextData(  
  _In_ JsContextRef context,  
  _In_ void *data  
);  
  
```  
  
#### <span data-ttu-id="993f3-106">参数</span><span class="sxs-lookup"><span data-stu-id="993f3-106">Parameters</span></span>  
 `context`  
 <span data-ttu-id="993f3-107">要将数据设置到的上下文。</span><span class="sxs-lookup"><span data-stu-id="993f3-107">The context to set the data to.</span></span>  
  
 `data`  
 <span data-ttu-id="993f3-108">指向要设置的数据的指针。</span><span class="sxs-lookup"><span data-stu-id="993f3-108">The pointer to the data to be set.</span></span>  
  
## <span data-ttu-id="993f3-109">返回值</span><span class="sxs-lookup"><span data-stu-id="993f3-109">Return Value</span></span>  
 <span data-ttu-id="993f3-110">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="993f3-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="993f3-111">备注</span><span class="sxs-lookup"><span data-stu-id="993f3-111">Remarks</span></span>  
 <span data-ttu-id="993f3-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="993f3-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="993f3-113">要求</span><span class="sxs-lookup"><span data-stu-id="993f3-113">Requirements</span></span>  
 <span data-ttu-id="993f3-114">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="993f3-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="993f3-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="993f3-115">See Also</span></span>  
 [<span data-ttu-id="993f3-116">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="993f3-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)