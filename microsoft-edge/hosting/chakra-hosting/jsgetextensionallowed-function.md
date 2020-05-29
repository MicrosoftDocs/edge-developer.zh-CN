---
description: 返回一个值，该值指示对象是否可扩展。
title: JsGetExtensionAllowed 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsGetExtensionAllowed
helpviewer_keywords:
- JsGetExtensionAllowed function
ms.assetid: 839054a1-d643-47d9-89db-6a015bba0d91
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: e3baa6449294f7b055251d861a32095deb1bdfe9
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563124"
---
# <span data-ttu-id="a4884-103">JsGetExtensionAllowed 函数</span><span class="sxs-lookup"><span data-stu-id="a4884-103">JsGetExtensionAllowed Function</span></span>
<span data-ttu-id="a4884-104">返回一个值，该值指示对象是否可扩展。</span><span class="sxs-lookup"><span data-stu-id="a4884-104">Returns a value that indicates whether an object is extensible or not.</span></span>  
  
## <span data-ttu-id="a4884-105">语法</span><span class="sxs-lookup"><span data-stu-id="a4884-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetExtensionAllowed(  
   _In_ JsValueRef object,  
   _Out_ bool *value  
);  
```  
  
#### <span data-ttu-id="a4884-106">参数</span><span class="sxs-lookup"><span data-stu-id="a4884-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="a4884-107">要测试的对象。</span><span class="sxs-lookup"><span data-stu-id="a4884-107">The object to test.</span></span>  
  
 `value`  
 <span data-ttu-id="a4884-108">对象是否可扩展。</span><span class="sxs-lookup"><span data-stu-id="a4884-108">Whether the object is extensible or not.</span></span>  
  
## <span data-ttu-id="a4884-109">返回值</span><span class="sxs-lookup"><span data-stu-id="a4884-109">Return Value</span></span>  
 <span data-ttu-id="a4884-110">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="a4884-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="a4884-111">备注</span><span class="sxs-lookup"><span data-stu-id="a4884-111">Remarks</span></span>  
 <span data-ttu-id="a4884-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="a4884-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="a4884-113">要求</span><span class="sxs-lookup"><span data-stu-id="a4884-113">Requirements</span></span>  
 <span data-ttu-id="a4884-114">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="a4884-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="a4884-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a4884-115">See Also</span></span>  
 [<span data-ttu-id="a4884-116">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="a4884-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)