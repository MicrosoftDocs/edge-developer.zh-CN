---
description: 在集合之前调用的回调。
title: JsBeforeCollectCallback Typedef |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 58bece47-4e6d-49e7-a93d-b6a8f9928b41
caps.latest.revision: 6
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 23ed386a6a28d356aa80cf85650a981d4836a6b6
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232221"
---
# <span data-ttu-id="ad366-103">JsBeforeCollectCallback Typedef</span><span class="sxs-lookup"><span data-stu-id="ad366-103">JsBeforeCollectCallback Typedef</span></span>

<span data-ttu-id="ad366-104">在集合之前调用的回调。</span><span class="sxs-lookup"><span data-stu-id="ad366-104">A callback called before collection.</span></span>  
  
## <span data-ttu-id="ad366-105">语法</span><span class="sxs-lookup"><span data-stu-id="ad366-105">Syntax</span></span>  
  
```cpp  
typedef void (CALLBACK *JsBeforeCollectCallback)(  
_In_opt_ void *callbackState  
);  
```  
  
#### <span data-ttu-id="ad366-106">参数</span><span class="sxs-lookup"><span data-stu-id="ad366-106">Parameters</span></span>  
 <span data-ttu-id="ad366-107">callbackState</span><span class="sxs-lookup"><span data-stu-id="ad366-107">callbackState</span></span>  
 <span data-ttu-id="ad366-108">传递给 JsSetBeforeCollectCallback 的状态。</span><span class="sxs-lookup"><span data-stu-id="ad366-108">The state passed to JsSetBeforeCollectCallback.</span></span>  
  
## <span data-ttu-id="ad366-109">备注</span><span class="sxs-lookup"><span data-stu-id="ad366-109">Remarks</span></span>  
 <span data-ttu-id="ad366-110">使用 JsSetBeforeCollectCallback 注册此回调。</span><span class="sxs-lookup"><span data-stu-id="ad366-110">Use JsSetBeforeCollectCallback to register this callback.</span></span>  
  
## <span data-ttu-id="ad366-111">要求</span><span class="sxs-lookup"><span data-stu-id="ad366-111">Requirements</span></span>  
 <span data-ttu-id="ad366-112">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="ad366-112">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="ad366-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ad366-113">See Also</span></span>  
 [<span data-ttu-id="ad366-114">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="ad366-114">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
