---
description: 终结器回调。
title: JsFinalizeCallback Typedef |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: aa7a0269-b9d4-4717-97ac-8da7eb6ced15
caps.latest.revision: 6
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: d2ee2c2c11e85094010cd15be59aa7ac587b614f
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564265"
---
# <span data-ttu-id="362af-103">JsFinalizeCallback Typedef</span><span class="sxs-lookup"><span data-stu-id="362af-103">JsFinalizeCallback Typedef</span></span>
<span data-ttu-id="362af-104">终结器回调。</span><span class="sxs-lookup"><span data-stu-id="362af-104">A finalizer callback.</span></span>  
  
## <span data-ttu-id="362af-105">语法</span><span class="sxs-lookup"><span data-stu-id="362af-105">Syntax</span></span>  
  
```cpp  
typedef void (CALLBACK *JsFinalizeCallback)(  
   _In_opt_ void *data  
);  
```  
  
#### <span data-ttu-id="362af-106">参数</span><span class="sxs-lookup"><span data-stu-id="362af-106">Parameters</span></span>  
 <span data-ttu-id="362af-107">数据</span><span class="sxs-lookup"><span data-stu-id="362af-107">data</span></span>  
 <span data-ttu-id="362af-108">创建终止对象时传入的外部数据。</span><span class="sxs-lookup"><span data-stu-id="362af-108">The external data that was passed in when creating the object being finalized.</span></span>  
  
## <span data-ttu-id="362af-109">要求</span><span class="sxs-lookup"><span data-stu-id="362af-109">Requirements</span></span>  
 <span data-ttu-id="362af-110">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="362af-110">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="362af-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="362af-111">See Also</span></span>  
 [<span data-ttu-id="362af-112">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="362af-112">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)