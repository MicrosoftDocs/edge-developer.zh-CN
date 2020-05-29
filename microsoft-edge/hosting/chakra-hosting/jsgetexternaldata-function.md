---
description: 检索外部对象中的数据。
title: JsGetExternalData 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsGetExternalData
helpviewer_keywords:
- JsGetExternalData function
ms.assetid: 1919e1da-3ea7-4269-a5fb-a3be06bd029b
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 469d28d47f89b06897e4b72d081baad34eb92a6c
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563125"
---
# <span data-ttu-id="71790-103">JsGetExternalData 函数</span><span class="sxs-lookup"><span data-stu-id="71790-103">JsGetExternalData Function</span></span>
<span data-ttu-id="71790-104">检索外部对象中的数据。</span><span class="sxs-lookup"><span data-stu-id="71790-104">Retrieves the data from an external object.</span></span>  
  
## <span data-ttu-id="71790-105">语法</span><span class="sxs-lookup"><span data-stu-id="71790-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetExternalData(  
   _In_ JsValueRef object,  
   _Out_ void **externalData  
);  
```  
  
#### <span data-ttu-id="71790-106">参数</span><span class="sxs-lookup"><span data-stu-id="71790-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="71790-107">外部对象。</span><span class="sxs-lookup"><span data-stu-id="71790-107">The external object.</span></span>  
  
 `externalData`  
 <span data-ttu-id="71790-108">存储在对象中的外部数据。</span><span class="sxs-lookup"><span data-stu-id="71790-108">The external data stored in the object.</span></span> <span data-ttu-id="71790-109">如果对象中不存储任何外部数据，则可以为 null。</span><span class="sxs-lookup"><span data-stu-id="71790-109">Can be null if no external data is stored in the object.</span></span>  
  
## <span data-ttu-id="71790-110">返回值</span><span class="sxs-lookup"><span data-stu-id="71790-110">Return Value</span></span>  
 <span data-ttu-id="71790-111">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="71790-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="71790-112">备注</span><span class="sxs-lookup"><span data-stu-id="71790-112">Remarks</span></span>  
 <span data-ttu-id="71790-113">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="71790-113">Requires an active script context.</span></span>  
  
## <span data-ttu-id="71790-114">要求</span><span class="sxs-lookup"><span data-stu-id="71790-114">Requirements</span></span>  
 <span data-ttu-id="71790-115">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="71790-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="71790-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="71790-116">See Also</span></span>  
 [<span data-ttu-id="71790-117">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="71790-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)