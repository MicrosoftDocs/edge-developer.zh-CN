---
description: 将对象的索引属性设置为外部数据。 外部数据将用作对象的索引属性的 back store，并像类型化数组一样进行访问。
title: JsSetIndexedPropertiesToExternalData 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: cee2d86d-ed42-4acb-86ef-95a67e63d0d6
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: c1aed6e194b1dc1c35f403626a7b6c02a7752ffb
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564175"
---
# <span data-ttu-id="7c5b7-104">JsSetIndexedPropertiesToExternalData 函数</span><span class="sxs-lookup"><span data-stu-id="7c5b7-104">JsSetIndexedPropertiesToExternalData Function</span></span>
<span data-ttu-id="7c5b7-105">将对象的索引属性设置为外部数据。</span><span class="sxs-lookup"><span data-stu-id="7c5b7-105">Sets an object's indexed properties to external data.</span></span> <span data-ttu-id="7c5b7-106">外部数据将用作对象的索引属性的 back store，并像类型化数组一样进行访问。</span><span class="sxs-lookup"><span data-stu-id="7c5b7-106">The external data will be used as back store for the object's indexed properties and accessed like a typed array.</span></span>  
  
## <span data-ttu-id="7c5b7-107">语法</span><span class="sxs-lookup"><span data-stu-id="7c5b7-107">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsSetIndexedPropertiesToExternalData(  
   _In_ JsValueRef object,  
   _In_ void* data,  
   _In_ JsTypedArrayType arrayType,  
   _In_ unsigned int elementLength  
);  
```  
  
#### <span data-ttu-id="7c5b7-108">参数</span><span class="sxs-lookup"><span data-stu-id="7c5b7-108">Parameters</span></span>  
 `object`  
 <span data-ttu-id="7c5b7-109">要操作的对象。</span><span class="sxs-lookup"><span data-stu-id="7c5b7-109">The object to operate on.</span></span>  
  
 `data`  
 <span data-ttu-id="7c5b7-110">要用作对象的索引属性的 back store 的外部数据。</span><span class="sxs-lookup"><span data-stu-id="7c5b7-110">The external data to be used as back store for the object's indexed properties.</span></span>  
  
 `arrayType`  
 <span data-ttu-id="7c5b7-111">外部数据中的数组元素类型。</span><span class="sxs-lookup"><span data-stu-id="7c5b7-111">The array element type in external data.</span></span>  
  
 `elementLength`  
 <span data-ttu-id="7c5b7-112">外部数据中数组元素的数量。</span><span class="sxs-lookup"><span data-stu-id="7c5b7-112">The number of array elements in external data.</span></span>  
  
## <span data-ttu-id="7c5b7-113">返回值</span><span class="sxs-lookup"><span data-stu-id="7c5b7-113">Return Value</span></span>  
 <span data-ttu-id="7c5b7-114">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="7c5b7-114">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="7c5b7-115">备注</span><span class="sxs-lookup"><span data-stu-id="7c5b7-115">Remarks</span></span>  
 <span data-ttu-id="7c5b7-116">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="7c5b7-116">Requires an active script context.</span></span>  
  
 <span data-ttu-id="7c5b7-117">此 API 仅在 EdgeHTML 模式下受支持。</span><span class="sxs-lookup"><span data-stu-id="7c5b7-117">This API is supported only in EdgeHTML mode.</span></span>  
  
## <span data-ttu-id="7c5b7-118">要求</span><span class="sxs-lookup"><span data-stu-id="7c5b7-118">Requirements</span></span>  
 <span data-ttu-id="7c5b7-119">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="7c5b7-119">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="7c5b7-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7c5b7-120">See Also</span></span>  
 [<span data-ttu-id="7c5b7-121">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="7c5b7-121">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)