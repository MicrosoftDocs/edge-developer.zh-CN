---
description: 设置 JsrtContext 的内部数据。
title: JsSetContextData 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: be90aa6a-b001-4a6f-90c5-c2135e913be0
caps.latest.revision: 4
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: e874f500ca82328dddeaaa03a0b78a188b8fd241
ms.sourcegitcommit: 037a2d62333691104c9accb4862968f80a3465a2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/18/2020
ms.locfileid: "10751931"
---
# <span data-ttu-id="9a8b8-103">JsSetContextData 函数</span><span class="sxs-lookup"><span data-stu-id="9a8b8-103">JsSetContextData Function</span></span>
<span data-ttu-id="9a8b8-104">设置 JsrtContext 的内部数据。</span><span class="sxs-lookup"><span data-stu-id="9a8b8-104">Sets the internal data of JsrtContext.</span></span>  
  
## <span data-ttu-id="9a8b8-105">语法</span><span class="sxs-lookup"><span data-stu-id="9a8b8-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsSetContextData(  
  _In_ JsContextRef context,  
  _In_ void *data  
);  
  
```  
  
#### <span data-ttu-id="9a8b8-106">参数</span><span class="sxs-lookup"><span data-stu-id="9a8b8-106">Parameters</span></span>  
 `context`  
 <span data-ttu-id="9a8b8-107">要将数据设置到的上下文。</span><span class="sxs-lookup"><span data-stu-id="9a8b8-107">The context to set the data to.</span></span>  
  
 `data`  
 <span data-ttu-id="9a8b8-108">指向要设置的数据的指针。</span><span class="sxs-lookup"><span data-stu-id="9a8b8-108">The pointer to the data to be set.</span></span>  
  
## <span data-ttu-id="9a8b8-109">返回值</span><span class="sxs-lookup"><span data-stu-id="9a8b8-109">Return Value</span></span>  
 <span data-ttu-id="9a8b8-110">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="9a8b8-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="9a8b8-111">备注</span><span class="sxs-lookup"><span data-stu-id="9a8b8-111">Remarks</span></span>  
 <span data-ttu-id="9a8b8-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="9a8b8-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="9a8b8-113">要求</span><span class="sxs-lookup"><span data-stu-id="9a8b8-113">Requirements</span></span>  
 <span data-ttu-id="9a8b8-114">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="9a8b8-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="9a8b8-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9a8b8-115">See Also</span></span>  
 [<span data-ttu-id="9a8b8-116">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="9a8b8-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)