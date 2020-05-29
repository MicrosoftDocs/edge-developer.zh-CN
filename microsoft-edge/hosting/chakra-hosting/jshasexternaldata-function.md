---
description: 确定对象是否为外部对象。
title: JsHasExternalData 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsHasExternalData
helpviewer_keywords:
- JsHasExternalData function
ms.assetid: a077e3ac-4f6f-4d94-8398-f1b5cc4c18e0
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 0ca86df09264eb82dac2e928874ca15edd2c8c8e
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564233"
---
# <span data-ttu-id="99654-103">JsHasExternalData 函数</span><span class="sxs-lookup"><span data-stu-id="99654-103">JsHasExternalData Function</span></span>
<span data-ttu-id="99654-104">确定对象是否为外部对象。</span><span class="sxs-lookup"><span data-stu-id="99654-104">Determines whether an object is an external object.</span></span>  
  
## <span data-ttu-id="99654-105">语法</span><span class="sxs-lookup"><span data-stu-id="99654-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsHasExternalData(  
   _In_ JsValueRef object,  
   _Out_ bool *value  
);  
```  
  
#### <span data-ttu-id="99654-106">参数</span><span class="sxs-lookup"><span data-stu-id="99654-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="99654-107">该对象。</span><span class="sxs-lookup"><span data-stu-id="99654-107">The object.</span></span>  
  
 `value`  
 <span data-ttu-id="99654-108">对象是否为外部对象。</span><span class="sxs-lookup"><span data-stu-id="99654-108">Whether the object is an external object.</span></span>  
  
## <span data-ttu-id="99654-109">返回值</span><span class="sxs-lookup"><span data-stu-id="99654-109">Return Value</span></span>  
 <span data-ttu-id="99654-110">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="99654-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="99654-111">备注</span><span class="sxs-lookup"><span data-stu-id="99654-111">Remarks</span></span>  
 <span data-ttu-id="99654-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="99654-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="99654-113">要求</span><span class="sxs-lookup"><span data-stu-id="99654-113">Requirements</span></span>  
 <span data-ttu-id="99654-114">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="99654-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="99654-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="99654-115">See Also</span></span>  
 [<span data-ttu-id="99654-116">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="99654-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)