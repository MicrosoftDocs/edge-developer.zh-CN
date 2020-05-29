---
description: 获取 JsrtContext 上的内部数据集。
title: JsGetContextData 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f5d7e446-267a-4a80-a427-6e1b95a3391b
caps.latest.revision: 4
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: bd85ccbc4008897643ec3840e8cdeca3611a50c8
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563134"
---
# <span data-ttu-id="07a01-103">JsGetContextData 函数</span><span class="sxs-lookup"><span data-stu-id="07a01-103">JsGetContextData Function</span></span>
<span data-ttu-id="07a01-104">获取 JsrtContext 上的内部数据集。</span><span class="sxs-lookup"><span data-stu-id="07a01-104">Gets the internal data set on JsrtContext.</span></span>  
  
## <span data-ttu-id="07a01-105">语法</span><span class="sxs-lookup"><span data-stu-id="07a01-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetContextData(  
  _In_ JsContextRef context,  
  _Out_ void **data  
);  
```  
  
#### <span data-ttu-id="07a01-106">参数</span><span class="sxs-lookup"><span data-stu-id="07a01-106">Parameters</span></span>  
 `context`  
 <span data-ttu-id="07a01-107">要从中获取数据的上下文。</span><span class="sxs-lookup"><span data-stu-id="07a01-107">The context to get the data from.</span></span>  
  
 `data`  
 <span data-ttu-id="07a01-108">指向将返回数据的数据的指针。</span><span class="sxs-lookup"><span data-stu-id="07a01-108">The pointer to the data where data will be returned.</span></span>  
  
## <span data-ttu-id="07a01-109">返回值</span><span class="sxs-lookup"><span data-stu-id="07a01-109">Return Value</span></span>  
 <span data-ttu-id="07a01-110">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="07a01-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="07a01-111">备注</span><span class="sxs-lookup"><span data-stu-id="07a01-111">Remarks</span></span>  
 <span data-ttu-id="07a01-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="07a01-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="07a01-113">要求</span><span class="sxs-lookup"><span data-stu-id="07a01-113">Requirements</span></span>  
 <span data-ttu-id="07a01-114">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="07a01-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="07a01-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="07a01-115">See Also</span></span>  
 [<span data-ttu-id="07a01-116">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="07a01-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)