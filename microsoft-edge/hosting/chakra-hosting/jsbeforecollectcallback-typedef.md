---
description: 在回收之前调用的回调。
title: JsBeforeCollectCallback Typedef |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 58bece47-4e6d-49e7-a93d-b6a8f9928b41
caps.latest.revision: 6
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 17f279c2d2ffcc8d02819994dddebfc22baa4cab
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563199"
---
# <span data-ttu-id="65011-103">JsBeforeCollectCallback Typedef</span><span class="sxs-lookup"><span data-stu-id="65011-103">JsBeforeCollectCallback Typedef</span></span>
<span data-ttu-id="65011-104">在回收之前调用的回调。</span><span class="sxs-lookup"><span data-stu-id="65011-104">A callback called before collection.</span></span>  
  
## <span data-ttu-id="65011-105">语法</span><span class="sxs-lookup"><span data-stu-id="65011-105">Syntax</span></span>  
  
```cpp  
typedef void (CALLBACK *JsBeforeCollectCallback)(  
_In_opt_ void *callbackState  
);  
```  
  
#### <span data-ttu-id="65011-106">参数</span><span class="sxs-lookup"><span data-stu-id="65011-106">Parameters</span></span>  
 <span data-ttu-id="65011-107">callbackState</span><span class="sxs-lookup"><span data-stu-id="65011-107">callbackState</span></span>  
 <span data-ttu-id="65011-108">传递给 JsSetBeforeCollectCallback 的状态。</span><span class="sxs-lookup"><span data-stu-id="65011-108">The state passed to JsSetBeforeCollectCallback.</span></span>  
  
## <span data-ttu-id="65011-109">备注</span><span class="sxs-lookup"><span data-stu-id="65011-109">Remarks</span></span>  
 <span data-ttu-id="65011-110">使用 JsSetBeforeCollectCallback 注册此回调。</span><span class="sxs-lookup"><span data-stu-id="65011-110">Use JsSetBeforeCollectCallback to register this callback.</span></span>  
  
## <span data-ttu-id="65011-111">要求</span><span class="sxs-lookup"><span data-stu-id="65011-111">Requirements</span></span>  
 <span data-ttu-id="65011-112">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="65011-112">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="65011-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="65011-113">See Also</span></span>  
 [<span data-ttu-id="65011-114">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="65011-114">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)