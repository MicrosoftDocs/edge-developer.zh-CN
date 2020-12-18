---
description: 获取 JsrtContext 上的内部数据集。
title: JsGetContextData 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: article
ms.assetid: f5d7e446-267a-4a80-a427-6e1b95a3391b
caps.latest.revision: 4
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 8f5f70a9c36fea355792050c1a2a810bca2d07b3
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232323"
---
# <span data-ttu-id="a6ea7-103">JsGetContextData 函数</span><span class="sxs-lookup"><span data-stu-id="a6ea7-103">JsGetContextData Function</span></span>

<span data-ttu-id="a6ea7-104">获取 JsrtContext 上的内部数据集。</span><span class="sxs-lookup"><span data-stu-id="a6ea7-104">Gets the internal data set on JsrtContext.</span></span>  
  
## <span data-ttu-id="a6ea7-105">语法</span><span class="sxs-lookup"><span data-stu-id="a6ea7-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetContextData(  
  _In_ JsContextRef context,  
  _Out_ void **data  
);  
```  
  
#### <span data-ttu-id="a6ea7-106">参数</span><span class="sxs-lookup"><span data-stu-id="a6ea7-106">Parameters</span></span>  
 `context`  
 <span data-ttu-id="a6ea7-107">要获取数据的上下文。</span><span class="sxs-lookup"><span data-stu-id="a6ea7-107">The context to get the data from.</span></span>  
  
 `data`  
 <span data-ttu-id="a6ea7-108">指向将返回数据的数据的指针。</span><span class="sxs-lookup"><span data-stu-id="a6ea7-108">The pointer to the data where data will be returned.</span></span>  
  
## <span data-ttu-id="a6ea7-109">返回值</span><span class="sxs-lookup"><span data-stu-id="a6ea7-109">Return Value</span></span>  
 <span data-ttu-id="a6ea7-110">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="a6ea7-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="a6ea7-111">备注</span><span class="sxs-lookup"><span data-stu-id="a6ea7-111">Remarks</span></span>  
 <span data-ttu-id="a6ea7-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="a6ea7-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="a6ea7-113">要求</span><span class="sxs-lookup"><span data-stu-id="a6ea7-113">Requirements</span></span>  
 <span data-ttu-id="a6ea7-114">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="a6ea7-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="a6ea7-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a6ea7-115">See Also</span></span>  
 [<span data-ttu-id="a6ea7-116">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="a6ea7-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
