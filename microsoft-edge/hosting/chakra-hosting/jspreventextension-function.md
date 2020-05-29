---
description: 使对象成为非可扩展对象。
title: JsPreventExtension 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsPreventExtension
helpviewer_keywords:
- JsPreventExtension function
ms.assetid: 8da07e20-d076-4ae4-9fb0-3f3c141518c2
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: baa001b2fd26133ef3a20c88213ac6aaf34a2e0d
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564208"
---
# <span data-ttu-id="25e37-103">JsPreventExtension 函数</span><span class="sxs-lookup"><span data-stu-id="25e37-103">JsPreventExtension Function</span></span>
<span data-ttu-id="25e37-104">使对象成为非可扩展对象。</span><span class="sxs-lookup"><span data-stu-id="25e37-104">Makes an object non-extensible.</span></span>  
  
## <span data-ttu-id="25e37-105">语法</span><span class="sxs-lookup"><span data-stu-id="25e37-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsPreventExtension(  
   _In_ JsValueRef object  
);  
```  
  
#### <span data-ttu-id="25e37-106">参数</span><span class="sxs-lookup"><span data-stu-id="25e37-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="25e37-107">要使其不可扩展的对象。</span><span class="sxs-lookup"><span data-stu-id="25e37-107">The object to make non-extensible.</span></span>  
  
## <span data-ttu-id="25e37-108">返回值</span><span class="sxs-lookup"><span data-stu-id="25e37-108">Return Value</span></span>  
 <span data-ttu-id="25e37-109">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="25e37-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="25e37-110">备注</span><span class="sxs-lookup"><span data-stu-id="25e37-110">Remarks</span></span>  
 <span data-ttu-id="25e37-111">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="25e37-111">Requires an active script context.</span></span>  
  
## <span data-ttu-id="25e37-112">要求</span><span class="sxs-lookup"><span data-stu-id="25e37-112">Requirements</span></span>  
 <span data-ttu-id="25e37-113">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="25e37-113">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="25e37-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="25e37-114">See Also</span></span>  
 [<span data-ttu-id="25e37-115">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="25e37-115">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)