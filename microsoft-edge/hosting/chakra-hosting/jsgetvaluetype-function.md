---
description: 获取 JsValueRef 的 JavaScript 类型。
title: JsGetValueType 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsGetValueType
helpviewer_keywords:
- JsGetValueType function
ms.assetid: f403cf7c-c8c0-4a17-bfa9-0302d00e760e
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 85dc6644e26017c6085ab64d914a86196cca8080
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564231"
---
# <span data-ttu-id="77c3c-103">JsGetValueType 函数</span><span class="sxs-lookup"><span data-stu-id="77c3c-103">JsGetValueType Function</span></span>
<span data-ttu-id="77c3c-104">获取 JsValueRef 的 JavaScript 类型。</span><span class="sxs-lookup"><span data-stu-id="77c3c-104">Gets the JavaScript type of a JsValueRef.</span></span>  
  
## <span data-ttu-id="77c3c-105">语法</span><span class="sxs-lookup"><span data-stu-id="77c3c-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetValueType(  
   _In_ JsValueRef value,  
   _Out_ JsValueType *type  
);  
```  
  
#### <span data-ttu-id="77c3c-106">参数</span><span class="sxs-lookup"><span data-stu-id="77c3c-106">Parameters</span></span>  
 `value`  
 <span data-ttu-id="77c3c-107">要返回其类型的值。</span><span class="sxs-lookup"><span data-stu-id="77c3c-107">The value whose type is to be returned.</span></span>  
  
 `type`  
 <span data-ttu-id="77c3c-108">值的类型。</span><span class="sxs-lookup"><span data-stu-id="77c3c-108">The type of the value.</span></span>  
  
## <span data-ttu-id="77c3c-109">返回值</span><span class="sxs-lookup"><span data-stu-id="77c3c-109">Return Value</span></span>  
 <span data-ttu-id="77c3c-110">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="77c3c-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="77c3c-111">备注</span><span class="sxs-lookup"><span data-stu-id="77c3c-111">Remarks</span></span>  
 <span data-ttu-id="77c3c-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="77c3c-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="77c3c-113">要求</span><span class="sxs-lookup"><span data-stu-id="77c3c-113">Requirements</span></span>  
 <span data-ttu-id="77c3c-114">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="77c3c-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="77c3c-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="77c3c-115">See Also</span></span>  
 [<span data-ttu-id="77c3c-116">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="77c3c-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)