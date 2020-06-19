---
description: 获取类型化数组的常用属性。
title: JsGetTypedArrayInfo 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 992bc4e9-3d06-4ad2-8b6b-88a437360f81
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 24046acc7118cd8f540ba8ceb9976368e93d51ff
ms.sourcegitcommit: 037a2d62333691104c9accb4862968f80a3465a2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/18/2020
ms.locfileid: "10752267"
---
# <span data-ttu-id="e486b-103">JsGetTypedArrayInfo 函数</span><span class="sxs-lookup"><span data-stu-id="e486b-103">JsGetTypedArrayInfo Function</span></span>
<span data-ttu-id="e486b-104">获取类型化数组的常用属性。</span><span class="sxs-lookup"><span data-stu-id="e486b-104">Obtains frequently used properties of a typed array.</span></span>  
  
## <span data-ttu-id="e486b-105">语法</span><span class="sxs-lookup"><span data-stu-id="e486b-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetTypedArrayInfo(  
  _In_ JsValueRef typedArray,  
  _Out_opt_ JsTypedArrayType *arrayType,  
  _Out_opt_ JsValueRef *arrayBuffer,  
  _Out_opt_ unsigned int *byteOffset,  
  _Out_opt_ unsigned int *byteLength  
);  
  
```  
  
#### <span data-ttu-id="e486b-106">参数</span><span class="sxs-lookup"><span data-stu-id="e486b-106">Parameters</span></span>  
 `typedArray`  
 <span data-ttu-id="e486b-107">类型化数组实例。</span><span class="sxs-lookup"><span data-stu-id="e486b-107">The typed array instance.</span></span>  
  
 `arrayType`  
 <span data-ttu-id="e486b-108">数组的类型。</span><span class="sxs-lookup"><span data-stu-id="e486b-108">The type of the array.</span></span>  
  
 `arrayBuffer`  
 <span data-ttu-id="e486b-109">`ArrayBuffer`数组的 backstore。</span><span class="sxs-lookup"><span data-stu-id="e486b-109">The `ArrayBuffer` backstore of the array.</span></span>  
  
 `byteOffset`  
 <span data-ttu-id="e486b-110">由数组引用的 arrayBuffer 的起始处的偏移量（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="e486b-110">The offset in bytes from the start of arrayBuffer referenced by the array.</span></span>  
  
 `byteLength`  
 <span data-ttu-id="e486b-111">数组中的字节数。</span><span class="sxs-lookup"><span data-stu-id="e486b-111">The number of bytes in the array.</span></span>  
  
## <span data-ttu-id="e486b-112">返回值</span><span class="sxs-lookup"><span data-stu-id="e486b-112">Return Value</span></span>  
 <span data-ttu-id="e486b-113">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="e486b-113">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="e486b-114">备注</span><span class="sxs-lookup"><span data-stu-id="e486b-114">Remarks</span></span>  
 <span data-ttu-id="e486b-115">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="e486b-115">Requires an active script context.</span></span>  
  
## <span data-ttu-id="e486b-116">要求</span><span class="sxs-lookup"><span data-stu-id="e486b-116">Requirements</span></span>  
 <span data-ttu-id="e486b-117">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="e486b-117">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="e486b-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e486b-118">See Also</span></span>  
 [<span data-ttu-id="e486b-119">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="e486b-119">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)