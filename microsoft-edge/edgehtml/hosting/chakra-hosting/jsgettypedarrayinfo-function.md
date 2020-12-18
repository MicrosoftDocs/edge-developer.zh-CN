---
description: 获取类型数组的常用属性。
title: JsGetTypedArrayInfo 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 992bc4e9-3d06-4ad2-8b6b-88a437360f81
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: fdc9a05a2aebdabfd0c8e95c848d3bd5f97e580a
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232565"
---
# <span data-ttu-id="feced-103">JsGetTypedArrayInfo 函数</span><span class="sxs-lookup"><span data-stu-id="feced-103">JsGetTypedArrayInfo Function</span></span>

<span data-ttu-id="feced-104">获取类型数组的常用属性。</span><span class="sxs-lookup"><span data-stu-id="feced-104">Obtains frequently used properties of a typed array.</span></span>  
  
## <span data-ttu-id="feced-105">语法</span><span class="sxs-lookup"><span data-stu-id="feced-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetTypedArrayInfo(  
  _In_ JsValueRef typedArray,  
  _Out_opt_ JsTypedArrayType *arrayType,  
  _Out_opt_ JsValueRef *arrayBuffer,  
  _Out_opt_ unsigned int *byteOffset,  
  _Out_opt_ unsigned int *byteLength  
);  
  
```  
  
#### <span data-ttu-id="feced-106">参数</span><span class="sxs-lookup"><span data-stu-id="feced-106">Parameters</span></span>  
 `typedArray`  
 <span data-ttu-id="feced-107">键入的数组实例。</span><span class="sxs-lookup"><span data-stu-id="feced-107">The typed array instance.</span></span>  
  
 `arrayType`  
 <span data-ttu-id="feced-108">数组的类型。</span><span class="sxs-lookup"><span data-stu-id="feced-108">The type of the array.</span></span>  
  
 `arrayBuffer`  
 <span data-ttu-id="feced-109">`ArrayBuffer`数组的后端存储。</span><span class="sxs-lookup"><span data-stu-id="feced-109">The `ArrayBuffer` backstore of the array.</span></span>  
  
 `byteOffset`  
 <span data-ttu-id="feced-110">从数组引用的 arrayBuffer 开始的偏移量（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="feced-110">The offset in bytes from the start of arrayBuffer referenced by the array.</span></span>  
  
 `byteLength`  
 <span data-ttu-id="feced-111">数组中的字节数。</span><span class="sxs-lookup"><span data-stu-id="feced-111">The number of bytes in the array.</span></span>  
  
## <span data-ttu-id="feced-112">返回值</span><span class="sxs-lookup"><span data-stu-id="feced-112">Return Value</span></span>  
 <span data-ttu-id="feced-113">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="feced-113">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="feced-114">备注</span><span class="sxs-lookup"><span data-stu-id="feced-114">Remarks</span></span>  
 <span data-ttu-id="feced-115">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="feced-115">Requires an active script context.</span></span>  
  
## <span data-ttu-id="feced-116">要求</span><span class="sxs-lookup"><span data-stu-id="feced-116">Requirements</span></span>  
 <span data-ttu-id="feced-117">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="feced-117">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="feced-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="feced-118">See Also</span></span>  
 [<span data-ttu-id="feced-119">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="feced-119">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
