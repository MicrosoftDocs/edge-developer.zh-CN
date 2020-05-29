---
description: 创建一个 JavaScript 值，该值是传入的投影 `VARIANT` 。
title: JsVariantToValue 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsVariantToValue
helpviewer_keywords:
- JsVariantToValue function
ms.assetid: e8f9eb8b-55b3-4b65-927e-cad5b482edee
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 01796bc38548cf56b500731d899541ef214ec4e3
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563057"
---
# <span data-ttu-id="8e08d-103">JsVariantToValue 函数</span><span class="sxs-lookup"><span data-stu-id="8e08d-103">JsVariantToValue Function</span></span>
<span data-ttu-id="8e08d-104">创建一个 JavaScript 值，该值是传入的投影 `VARIANT` 。</span><span class="sxs-lookup"><span data-stu-id="8e08d-104">Creates a JavaScript value that is a projection of the passed in `VARIANT`.</span></span>  
  
## <span data-ttu-id="8e08d-105">语法</span><span class="sxs-lookup"><span data-stu-id="8e08d-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsVariantToValue(  
   _In_ VARIANT *variant,  
   _Out_ JsValueRef *value  
);  
```  
  
#### <span data-ttu-id="8e08d-106">参数</span><span class="sxs-lookup"><span data-stu-id="8e08d-106">Parameters</span></span>  
 `variant`  
 <span data-ttu-id="8e08d-107">`VARIANT`要投影的。</span><span class="sxs-lookup"><span data-stu-id="8e08d-107">A `VARIANT` to be projected.</span></span>  
  
 `value`  
 <span data-ttu-id="8e08d-108">作为的投影的 JavaScript 值 `VARIANT` 。</span><span class="sxs-lookup"><span data-stu-id="8e08d-108">A JavaScript value that is a projection of the `VARIANT`.</span></span>  
  
## <span data-ttu-id="8e08d-109">返回值</span><span class="sxs-lookup"><span data-stu-id="8e08d-109">Return Value</span></span>  
 <span data-ttu-id="8e08d-110">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="8e08d-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="8e08d-111">备注</span><span class="sxs-lookup"><span data-stu-id="8e08d-111">Remarks</span></span>  
 <span data-ttu-id="8e08d-112">脚本可以使用投影值从脚本调用 COM 自动化对象。</span><span class="sxs-lookup"><span data-stu-id="8e08d-112">The projected value can be used by script to call a COM automation object from script.</span></span> <span data-ttu-id="8e08d-113">主机负责强制执行 COM 线程处理规则。</span><span class="sxs-lookup"><span data-stu-id="8e08d-113">Hosts are responsible for enforcing COM threading rules.</span></span>  
  
 <span data-ttu-id="8e08d-114">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="8e08d-114">Requires an active script context.</span></span>  
  
## <span data-ttu-id="8e08d-115">要求</span><span class="sxs-lookup"><span data-stu-id="8e08d-115">Requirements</span></span>  
 <span data-ttu-id="8e08d-116">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="8e08d-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="8e08d-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8e08d-117">See Also</span></span>  
 [<span data-ttu-id="8e08d-118">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="8e08d-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)