---
description: 在收集对象之前调用的回调。
title: JsObjectBeforeCollectCallback Typedef |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: f21a064a-579f-44cb-9d21-76b62e8c18f5
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 27bbd1aed72cc751397ac4e6734f107612653b66
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563080"
---
# <span data-ttu-id="46652-103">JsObjectBeforeCollectCallback Typedef</span><span class="sxs-lookup"><span data-stu-id="46652-103">JsObjectBeforeCollectCallback Typedef</span></span>
<span data-ttu-id="46652-104">在收集对象之前调用的回调。</span><span class="sxs-lookup"><span data-stu-id="46652-104">A callback called before collecting an object.</span></span>  
  
## <span data-ttu-id="46652-105">语法</span><span class="sxs-lookup"><span data-stu-id="46652-105">Syntax</span></span>  
  
```cpp  
typedef void (CALLBACK *JsObjectBeforeCollectCallback)(  
  _In_ JsRef ref,  
  _In_opt_ void *callbackState  
);  
```  
  
#### <span data-ttu-id="46652-106">参数</span><span class="sxs-lookup"><span data-stu-id="46652-106">Parameters</span></span>  
 `ref`  
 <span data-ttu-id="46652-107">要收集的对象。</span><span class="sxs-lookup"><span data-stu-id="46652-107">The object to be collected.</span></span>  
  
 `callbackState`  
 <span data-ttu-id="46652-108">传递到的状态 `JsSetObjectBeforeCollectCallback` 。</span><span class="sxs-lookup"><span data-stu-id="46652-108">The state passed to `JsSetObjectBeforeCollectCallback`.</span></span>  
  
## <span data-ttu-id="46652-109">备注</span><span class="sxs-lookup"><span data-stu-id="46652-109">Remarks</span></span>  
 <span data-ttu-id="46652-110">此 API 仅在 EdgeHTML 模式下受支持。</span><span class="sxs-lookup"><span data-stu-id="46652-110">This API is supported only in EdgeHTML mode.</span></span>  
  
## <span data-ttu-id="46652-111">要求</span><span class="sxs-lookup"><span data-stu-id="46652-111">Requirements</span></span>  
 <span data-ttu-id="46652-112">jsrt</span><span class="sxs-lookup"><span data-stu-id="46652-112">jsrt.h</span></span>  
  
## <span data-ttu-id="46652-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="46652-113">See Also</span></span>  
 [<span data-ttu-id="46652-114">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="46652-114">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)