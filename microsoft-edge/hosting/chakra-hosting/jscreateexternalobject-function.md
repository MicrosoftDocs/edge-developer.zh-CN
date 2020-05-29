---
description: 创建存储某些外部数据的新对象。
title: JsCreateExternalObject 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsCreateExternalObject
helpviewer_keywords:
- JsCreateExternalObject function
ms.assetid: 6bcef506-93fb-429b-b06a-a971ff0b71f3
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 9a68f4befea7dc7c3369bcade475e29d53342730
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563165"
---
# <span data-ttu-id="9d42b-103">JsCreateExternalObject 函数</span><span class="sxs-lookup"><span data-stu-id="9d42b-103">JsCreateExternalObject Function</span></span>
<span data-ttu-id="9d42b-104">创建存储某些外部数据的新对象。</span><span class="sxs-lookup"><span data-stu-id="9d42b-104">Creates a new object that stores some external data.</span></span>
  
## <span data-ttu-id="9d42b-105">语法</span><span class="sxs-lookup"><span data-stu-id="9d42b-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateExternalObject(  
   _In_opt_ void *data,  
   _In_opt_ JsFinalizeCallback finalizeCallback,  
   _Out_ JsValueRef *object  
);  
```  
  
#### <span data-ttu-id="9d42b-106">参数</span><span class="sxs-lookup"><span data-stu-id="9d42b-106">Parameters</span></span>  
 `data`  
 <span data-ttu-id="9d42b-107">对象将表示的外部数据。</span><span class="sxs-lookup"><span data-stu-id="9d42b-107">External data that the object will represent.</span></span> <span data-ttu-id="9d42b-108">可能为 null。</span><span class="sxs-lookup"><span data-stu-id="9d42b-108">May be null.</span></span>  
  
 `finalizeCallback`  
 <span data-ttu-id="9d42b-109">终止对象时的回调。</span><span class="sxs-lookup"><span data-stu-id="9d42b-109">A callback for when the object is finalized.</span></span> <span data-ttu-id="9d42b-110">可能为 null。</span><span class="sxs-lookup"><span data-stu-id="9d42b-110">May be null.</span></span>  
  
 `object`  
 <span data-ttu-id="9d42b-111">新对象。</span><span class="sxs-lookup"><span data-stu-id="9d42b-111">The new object.</span></span>  
  
## <span data-ttu-id="9d42b-112">返回值</span><span class="sxs-lookup"><span data-stu-id="9d42b-112">Return Value</span></span>  
 <span data-ttu-id="9d42b-113">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="9d42b-113">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="9d42b-114">备注</span><span class="sxs-lookup"><span data-stu-id="9d42b-114">Remarks</span></span>  
 <span data-ttu-id="9d42b-115">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="9d42b-115">Requires an active script context.</span></span>  
  
## <span data-ttu-id="9d42b-116">要求</span><span class="sxs-lookup"><span data-stu-id="9d42b-116">Requirements</span></span>  
 <span data-ttu-id="9d42b-117">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="9d42b-117">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="9d42b-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9d42b-118">See Also</span></span>  
 [<span data-ttu-id="9d42b-119">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="9d42b-119">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)