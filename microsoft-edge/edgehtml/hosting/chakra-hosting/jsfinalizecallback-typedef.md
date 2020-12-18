---
description: 完成回调。
title: JsFinalizeCallback Typedef |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: aa7a0269-b9d4-4717-97ac-8da7eb6ced15
caps.latest.revision: 6
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 794edbb3a61c8c213c0908740ed0a867488a2c6d
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232331"
---
# <span data-ttu-id="22ddb-103">JsFinalizeCallback Typedef</span><span class="sxs-lookup"><span data-stu-id="22ddb-103">JsFinalizeCallback Typedef</span></span>

<span data-ttu-id="22ddb-104">完成回调。</span><span class="sxs-lookup"><span data-stu-id="22ddb-104">A finalizer callback.</span></span>  
  
## <span data-ttu-id="22ddb-105">语法</span><span class="sxs-lookup"><span data-stu-id="22ddb-105">Syntax</span></span>  
  
```cpp  
typedef void (CALLBACK *JsFinalizeCallback)(  
   _In_opt_ void *data  
);  
```  
  
#### <span data-ttu-id="22ddb-106">参数</span><span class="sxs-lookup"><span data-stu-id="22ddb-106">Parameters</span></span>  
 <span data-ttu-id="22ddb-107">数据</span><span class="sxs-lookup"><span data-stu-id="22ddb-107">data</span></span>  
 <span data-ttu-id="22ddb-108">创建要完成的对象时传入的外部数据。</span><span class="sxs-lookup"><span data-stu-id="22ddb-108">The external data that was passed in when creating the object being finalized.</span></span>  
  
## <span data-ttu-id="22ddb-109">要求</span><span class="sxs-lookup"><span data-stu-id="22ddb-109">Requirements</span></span>  
 <span data-ttu-id="22ddb-110">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="22ddb-110">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="22ddb-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="22ddb-111">See Also</span></span>  
 [<span data-ttu-id="22ddb-112">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="22ddb-112">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
