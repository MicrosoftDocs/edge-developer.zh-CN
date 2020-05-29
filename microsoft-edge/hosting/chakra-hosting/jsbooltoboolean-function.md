---
description: 从值创建一个布尔值 `bool` 。
title: JsBoolToBoolean 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsBoolToBoolean
helpviewer_keywords:
- JsBoolToBoolean function
ms.assetid: 24322ea3-0638-40a3-9b4c-fc912ebed3ff
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: f795bdd02a2a21dc4a0c8948a76ef817d6e0fac6
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563198"
---
# <span data-ttu-id="9bf50-103">JsBoolToBoolean 函数</span><span class="sxs-lookup"><span data-stu-id="9bf50-103">JsBoolToBoolean Function</span></span>
<span data-ttu-id="9bf50-104">从值创建一个布尔值 `bool` 。</span><span class="sxs-lookup"><span data-stu-id="9bf50-104">Creates a Boolean value from a `bool` value.</span></span>  
  
## <span data-ttu-id="9bf50-105">语法</span><span class="sxs-lookup"><span data-stu-id="9bf50-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode JsBoolToBoolean(  
   _In_ bool value,  
   _Out_ JsValueRef *booleanValue  
);  
```  
  
#### <span data-ttu-id="9bf50-106">参数</span><span class="sxs-lookup"><span data-stu-id="9bf50-106">Parameters</span></span>  
 `value`  
 <span data-ttu-id="9bf50-107">要转换的值。</span><span class="sxs-lookup"><span data-stu-id="9bf50-107">The value to be converted.</span></span>  
  
 `booleanValue`  
 <span data-ttu-id="9bf50-108">已转换的值。</span><span class="sxs-lookup"><span data-stu-id="9bf50-108">The converted value.</span></span>  
  
## <span data-ttu-id="9bf50-109">返回值</span><span class="sxs-lookup"><span data-stu-id="9bf50-109">Return Value</span></span>  
 <span data-ttu-id="9bf50-110">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="9bf50-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="9bf50-111">备注</span><span class="sxs-lookup"><span data-stu-id="9bf50-111">Remarks</span></span>  
 <span data-ttu-id="9bf50-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="9bf50-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="9bf50-113">要求</span><span class="sxs-lookup"><span data-stu-id="9bf50-113">Requirements</span></span>  
 <span data-ttu-id="9bf50-114">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="9bf50-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="9bf50-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9bf50-115">See Also</span></span>  
 [<span data-ttu-id="9bf50-116">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="9bf50-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)