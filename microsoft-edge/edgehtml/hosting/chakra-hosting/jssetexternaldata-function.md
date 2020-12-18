---
description: 设置外部对象上的外部数据。
title: JsSetExternalData 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsSetExternalData
helpviewer_keywords:
- JsSetExternalData function
ms.assetid: 94e0ad34-67d7-4f7f-88a3-3b057ef5e4b9
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: f2ebdce4448a14f145ce5aafe6ba412f7db26c17
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232514"
---
# <span data-ttu-id="3334e-103">JsSetExternalData 函数</span><span class="sxs-lookup"><span data-stu-id="3334e-103">JsSetExternalData Function</span></span>

<span data-ttu-id="3334e-104">设置外部对象上的外部数据。</span><span class="sxs-lookup"><span data-stu-id="3334e-104">Sets the external data on an external object.</span></span>  
  
## <span data-ttu-id="3334e-105">语法</span><span class="sxs-lookup"><span data-stu-id="3334e-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsSetExternalData(  
   _In_ JsValueRef object,  
   _In_opt_ void *externalData  
);  
```  
  
#### <span data-ttu-id="3334e-106">参数</span><span class="sxs-lookup"><span data-stu-id="3334e-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="3334e-107">外部对象。</span><span class="sxs-lookup"><span data-stu-id="3334e-107">The external object.</span></span>  
  
 `externalData`  
 <span data-ttu-id="3334e-108">对象中存储的外部数据。</span><span class="sxs-lookup"><span data-stu-id="3334e-108">The external data stored in the object.</span></span> <span data-ttu-id="3334e-109">如果对象中未存储任何外部数据，则其值可为空。</span><span class="sxs-lookup"><span data-stu-id="3334e-109">Can be null if no external data is stored in the object.</span></span>  
  
## <span data-ttu-id="3334e-110">返回值</span><span class="sxs-lookup"><span data-stu-id="3334e-110">Return Value</span></span>  
 <span data-ttu-id="3334e-111">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="3334e-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="3334e-112">备注</span><span class="sxs-lookup"><span data-stu-id="3334e-112">Remarks</span></span>  
 <span data-ttu-id="3334e-113">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="3334e-113">Requires an active script context.</span></span>  
  
## <span data-ttu-id="3334e-114">要求</span><span class="sxs-lookup"><span data-stu-id="3334e-114">Requirements</span></span>  
 <span data-ttu-id="3334e-115">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="3334e-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="3334e-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3334e-116">See Also</span></span>  
 [<span data-ttu-id="3334e-117">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="3334e-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
