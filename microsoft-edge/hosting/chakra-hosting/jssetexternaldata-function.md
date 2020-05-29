---
description: 设置外部对象上的外部数据。
title: JsSetExternalData 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsSetExternalData
helpviewer_keywords:
- JsSetExternalData function
ms.assetid: 94e0ad34-67d7-4f7f-88a3-3b057ef5e4b9
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: cc638905786a1baa0a3d5f79bfa3792a764f358f
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564178"
---
# <span data-ttu-id="c33eb-103">JsSetExternalData 函数</span><span class="sxs-lookup"><span data-stu-id="c33eb-103">JsSetExternalData Function</span></span>
<span data-ttu-id="c33eb-104">设置外部对象上的外部数据。</span><span class="sxs-lookup"><span data-stu-id="c33eb-104">Sets the external data on an external object.</span></span>  
  
## <span data-ttu-id="c33eb-105">语法</span><span class="sxs-lookup"><span data-stu-id="c33eb-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsSetExternalData(  
   _In_ JsValueRef object,  
   _In_opt_ void *externalData  
);  
```  
  
#### <span data-ttu-id="c33eb-106">参数</span><span class="sxs-lookup"><span data-stu-id="c33eb-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="c33eb-107">外部对象。</span><span class="sxs-lookup"><span data-stu-id="c33eb-107">The external object.</span></span>  
  
 `externalData`  
 <span data-ttu-id="c33eb-108">存储在对象中的外部数据。</span><span class="sxs-lookup"><span data-stu-id="c33eb-108">The external data stored in the object.</span></span> <span data-ttu-id="c33eb-109">如果对象中不存储任何外部数据，则可以为 null。</span><span class="sxs-lookup"><span data-stu-id="c33eb-109">Can be null if no external data is stored in the object.</span></span>  
  
## <span data-ttu-id="c33eb-110">返回值</span><span class="sxs-lookup"><span data-stu-id="c33eb-110">Return Value</span></span>  
 <span data-ttu-id="c33eb-111">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="c33eb-111">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="c33eb-112">备注</span><span class="sxs-lookup"><span data-stu-id="c33eb-112">Remarks</span></span>  
 <span data-ttu-id="c33eb-113">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="c33eb-113">Requires an active script context.</span></span>  
  
## <span data-ttu-id="c33eb-114">要求</span><span class="sxs-lookup"><span data-stu-id="c33eb-114">Requirements</span></span>  
 <span data-ttu-id="c33eb-115">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="c33eb-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="c33eb-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c33eb-116">See Also</span></span>  
 [<span data-ttu-id="c33eb-117">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="c33eb-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)