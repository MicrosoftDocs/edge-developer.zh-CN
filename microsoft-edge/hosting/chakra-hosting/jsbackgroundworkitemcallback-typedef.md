---
description: 后台工作项回调。
title: JsBackgroundWorkItemCallback Typedef |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: e6db52e1-830c-46a2-b9f9-cc2d450a1da8
caps.latest.revision: 6
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 9bc1e5687d92d7286e1e6d4387bd6b69d95ceb68
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563202"
---
# <span data-ttu-id="76e81-103">JsBackgroundWorkItemCallback Typedef</span><span class="sxs-lookup"><span data-stu-id="76e81-103">JsBackgroundWorkItemCallback Typedef</span></span>
<span data-ttu-id="76e81-104">后台工作项回调。</span><span class="sxs-lookup"><span data-stu-id="76e81-104">A background work item callback.</span></span>  
  
## <span data-ttu-id="76e81-105">语法</span><span class="sxs-lookup"><span data-stu-id="76e81-105">Syntax</span></span>  
  
```cpp  
typedef void (CALLBACK *JsBackgroundWorkItemCallback)(  
   _In_opt_ void *callbackData  
);  
```  
  
#### <span data-ttu-id="76e81-106">参数</span><span class="sxs-lookup"><span data-stu-id="76e81-106">Parameters</span></span>  
 <span data-ttu-id="76e81-107">callbackData</span><span class="sxs-lookup"><span data-stu-id="76e81-107">callbackData</span></span>  
 <span data-ttu-id="76e81-108">传递给线程服务的数据参数。</span><span class="sxs-lookup"><span data-stu-id="76e81-108">Data argument passed to the thread service.</span></span>  
  
## <span data-ttu-id="76e81-109">备注</span><span class="sxs-lookup"><span data-stu-id="76e81-109">Remarks</span></span>  
 <span data-ttu-id="76e81-110">这将传递到主机的线程服务（如果提供），以允许主机在其选择的后台线程上调用工作项回调。</span><span class="sxs-lookup"><span data-stu-id="76e81-110">This is passed to the host's thread service (if provided) to allow the host to invoke the work item callback on the background thread of its choice.</span></span>  
  
## <span data-ttu-id="76e81-111">要求</span><span class="sxs-lookup"><span data-stu-id="76e81-111">Requirements</span></span>  
 <span data-ttu-id="76e81-112">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="76e81-112">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="76e81-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="76e81-113">See Also</span></span>  
 [<span data-ttu-id="76e81-114">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="76e81-114">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)