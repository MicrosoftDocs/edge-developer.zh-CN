---
description: 创建 JavaScript `ArrayBuffer` 对象。
title: JsCreateArrayBuffer 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: c9e74184-7dd9-41a7-a1fe-9575e1701392
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 7e81c50317de5243fbcdf761c09c084f97a8e1e0
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563179"
---
# <span data-ttu-id="feb15-103">JsCreateArrayBuffer 函数</span><span class="sxs-lookup"><span data-stu-id="feb15-103">JsCreateArrayBuffer Function</span></span>
<span data-ttu-id="feb15-104">创建 JavaScript `ArrayBuffer` 对象。</span><span class="sxs-lookup"><span data-stu-id="feb15-104">Creates a JavaScript `ArrayBuffer` object.</span></span>  
  
## <span data-ttu-id="feb15-105">语法</span><span class="sxs-lookup"><span data-stu-id="feb15-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateArrayBuffer(  
   _In_ unsigned int byteLength,  
   _Out_ JsValueRef *result  
);  
```  
  
#### <span data-ttu-id="feb15-106">参数</span><span class="sxs-lookup"><span data-stu-id="feb15-106">Parameters</span></span>  
 `byteLength`  
 <span data-ttu-id="feb15-107">ArrayBuffer 中的字节数。</span><span class="sxs-lookup"><span data-stu-id="feb15-107">The number of bytes in the ArrayBuffer.</span></span>  
  
 `result`  
 <span data-ttu-id="feb15-108">新的 ArrayBuffer 对象。</span><span class="sxs-lookup"><span data-stu-id="feb15-108">The new ArrayBuffer object.</span></span>  
  
## <span data-ttu-id="feb15-109">返回值</span><span class="sxs-lookup"><span data-stu-id="feb15-109">Return Value</span></span>  
 <span data-ttu-id="feb15-110">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="feb15-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="feb15-111">备注</span><span class="sxs-lookup"><span data-stu-id="feb15-111">Remarks</span></span>  
 <span data-ttu-id="feb15-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="feb15-112">Requires an active script context.</span></span>  
  
 <span data-ttu-id="feb15-113">此 API 仅在 Microsoft Edge 模式下受支持。</span><span class="sxs-lookup"><span data-stu-id="feb15-113">This API is supported only in Microsoft Edge mode.</span></span>  
  
## <span data-ttu-id="feb15-114">要求</span><span class="sxs-lookup"><span data-stu-id="feb15-114">Requirements</span></span>  
 <span data-ttu-id="feb15-115">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="feb15-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="feb15-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="feb15-116">See Also</span></span>  
 [<span data-ttu-id="feb15-117">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="feb15-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)