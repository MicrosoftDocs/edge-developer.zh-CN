---
description: 函数回调。
title: JsNativeFunction Typedef |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 56ef6cdf-4ca9-4f7c-b953-e661addb1a8e
caps.latest.revision: 5
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: c0b73a11d3a0b2ed0867ef001f3c29c5643132a0
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563086"
---
# <span data-ttu-id="ad43a-103">JsNativeFunction Typedef</span><span class="sxs-lookup"><span data-stu-id="ad43a-103">JsNativeFunction Typedef</span></span>
<span data-ttu-id="ad43a-104">函数回调。</span><span class="sxs-lookup"><span data-stu-id="ad43a-104">A function callback.</span></span>  
  
## <span data-ttu-id="ad43a-105">语法</span><span class="sxs-lookup"><span data-stu-id="ad43a-105">Syntax</span></span>  
  
```cpp  
typedef _Ret_maybenull_ JsValueRef (CALLBACK * JsNativeFunction)(  
   _In_ JsValueRef callee,  
   _In_ bool isConstructCall,  
   _In_ JsValueRef *arguments,  
   _In_ unsigned short argumentCount  
);  
```  
  
#### <span data-ttu-id="ad43a-106">参数</span><span class="sxs-lookup"><span data-stu-id="ad43a-106">Parameters</span></span>  
 <span data-ttu-id="ad43a-107">方</span><span class="sxs-lookup"><span data-stu-id="ad43a-107">callee</span></span>  
 <span data-ttu-id="ad43a-108">一个 `Function` 表示正在调用的函数的对象。</span><span class="sxs-lookup"><span data-stu-id="ad43a-108">A `Function` object that represents the function being invoked.</span></span>  
  
 <span data-ttu-id="ad43a-109">isConstructCall</span><span class="sxs-lookup"><span data-stu-id="ad43a-109">isConstructCall</span></span>  
 <span data-ttu-id="ad43a-110">指示这是常规呼叫还是 "new" 呼叫。</span><span class="sxs-lookup"><span data-stu-id="ad43a-110">Indicates whether this is a regular call or a 'new' call.</span></span>  
  
 <span data-ttu-id="ad43a-111">arguments</span><span class="sxs-lookup"><span data-stu-id="ad43a-111">arguments</span></span>  
 <span data-ttu-id="ad43a-112">调用的参数。</span><span class="sxs-lookup"><span data-stu-id="ad43a-112">The arguments to the call.</span></span>  
  
 <span data-ttu-id="ad43a-113">argumentCount</span><span class="sxs-lookup"><span data-stu-id="ad43a-113">argumentCount</span></span>  
 <span data-ttu-id="ad43a-114">参数的数目。</span><span class="sxs-lookup"><span data-stu-id="ad43a-114">The number of arguments.</span></span>  
  
## <span data-ttu-id="ad43a-115">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="ad43a-115">Property Value/Return Value</span></span>  
 <span data-ttu-id="ad43a-116">通话的结果（如果有）。</span><span class="sxs-lookup"><span data-stu-id="ad43a-116">The result of the call, if any.</span></span>  
  
## <span data-ttu-id="ad43a-117">要求</span><span class="sxs-lookup"><span data-stu-id="ad43a-117">Requirements</span></span>  
 <span data-ttu-id="ad43a-118">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="ad43a-118">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="ad43a-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ad43a-119">See Also</span></span>  
 [<span data-ttu-id="ad43a-120">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="ad43a-120">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)