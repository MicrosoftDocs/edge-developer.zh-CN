---
description: Gets the internal data set on JsrtContext.
title: JsGetContextData Function | Microsoft Docs
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
# <span data-ttu-id="ab899-103">JsGetContextData Function</span><span class="sxs-lookup"><span data-stu-id="ab899-103">JsGetContextData Function</span></span>
<span data-ttu-id="ab899-104">Gets the internal data set on JsrtContext.</span><span class="sxs-lookup"><span data-stu-id="ab899-104">Gets the internal data set on JsrtContext.</span></span>  
  
## <span data-ttu-id="ab899-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="ab899-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetContextData(  
  _In_ JsContextRef context,  
  _Out_ void **data  
);  
```  
  
#### <span data-ttu-id="ab899-106">Parameters</span><span class="sxs-lookup"><span data-stu-id="ab899-106">Parameters</span></span>  
 `context`  
 <span data-ttu-id="ab899-107">The context to get the data from.</span><span class="sxs-lookup"><span data-stu-id="ab899-107">The context to get the data from.</span></span>  
  
 `data`  
 <span data-ttu-id="ab899-108">The pointer to the data where data will be returned.</span><span class="sxs-lookup"><span data-stu-id="ab899-108">The pointer to the data where data will be returned.</span></span>  
  
## <span data-ttu-id="ab899-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="ab899-109">Return Value</span></span>  
 <span data-ttu-id="ab899-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span><span class="sxs-lookup"><span data-stu-id="ab899-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="ab899-111">Remarks</span><span class="sxs-lookup"><span data-stu-id="ab899-111">Remarks</span></span>  
 <span data-ttu-id="ab899-112">Requires an active script context.</span><span class="sxs-lookup"><span data-stu-id="ab899-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="ab899-113">Requirements</span><span class="sxs-lookup"><span data-stu-id="ab899-113">Requirements</span></span>  
 <span data-ttu-id="ab899-114">**Header:** jsrt.h</span><span class="sxs-lookup"><span data-stu-id="ab899-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="ab899-115">See Also</span><span class="sxs-lookup"><span data-stu-id="ab899-115">See Also</span></span>  
 [<span data-ttu-id="ab899-116">Reference (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="ab899-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)