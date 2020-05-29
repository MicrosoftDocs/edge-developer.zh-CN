---
description: 设置对象的原型。
title: JsSetPrototype 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 88e1e421-4ae5-4e3b-b377-19256cc80e9f
caps.latest.revision: 4
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 625269c5f9f459a5c7eecb6cfc31cb85fc24214b
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564087"
---
# <span data-ttu-id="0d1b8-103">JsSetPrototype 函数</span><span class="sxs-lookup"><span data-stu-id="0d1b8-103">JsSetPrototype Function</span></span>
<span data-ttu-id="0d1b8-104">设置对象的原型。</span><span class="sxs-lookup"><span data-stu-id="0d1b8-104">Sets the prototype of an object.</span></span>  
  
## <span data-ttu-id="0d1b8-105">语法</span><span class="sxs-lookup"><span data-stu-id="0d1b8-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsSetPrototype(  
   _In_ JsValueRef object,  
   _In_ JsValueRef prototypeObject  
);  
```  
  
#### <span data-ttu-id="0d1b8-106">参数</span><span class="sxs-lookup"><span data-stu-id="0d1b8-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="0d1b8-107">要更改其原型的对象。</span><span class="sxs-lookup"><span data-stu-id="0d1b8-107">The object whose prototype is to be changed.</span></span>  
  
 `prototypeObject`  
 <span data-ttu-id="0d1b8-108">对象的新原型。</span><span class="sxs-lookup"><span data-stu-id="0d1b8-108">The object's new prototype.</span></span>  
  
## <span data-ttu-id="0d1b8-109">返回值</span><span class="sxs-lookup"><span data-stu-id="0d1b8-109">Return Value</span></span>  
 <span data-ttu-id="0d1b8-110">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="0d1b8-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="0d1b8-111">备注</span><span class="sxs-lookup"><span data-stu-id="0d1b8-111">Remarks</span></span>  
 <span data-ttu-id="0d1b8-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="0d1b8-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="0d1b8-113">要求</span><span class="sxs-lookup"><span data-stu-id="0d1b8-113">Requirements</span></span>  
 <span data-ttu-id="0d1b8-114">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="0d1b8-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="0d1b8-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0d1b8-115">See Also</span></span>  
 [<span data-ttu-id="0d1b8-116">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="0d1b8-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)