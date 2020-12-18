---
description: 将对象的索引属性设置到外部数据。 外部数据将用作对象的索引属性的后端存储，并像类型数组一样访问。
title: JsSetIndexedPropertiesToExternalData 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: cee2d86d-ed42-4acb-86ef-95a67e63d0d6
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: fa0eba3659c20066913cd42a0a18dd5ffe5f857f
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232184"
---
# <span data-ttu-id="7d4c8-104">JsSetIndexedPropertiesToExternalData 函数</span><span class="sxs-lookup"><span data-stu-id="7d4c8-104">JsSetIndexedPropertiesToExternalData Function</span></span>

<span data-ttu-id="7d4c8-105">将对象的索引属性设置到外部数据。</span><span class="sxs-lookup"><span data-stu-id="7d4c8-105">Sets an object's indexed properties to external data.</span></span> <span data-ttu-id="7d4c8-106">外部数据将用作对象的索引属性的后端存储，并像类型数组一样访问。</span><span class="sxs-lookup"><span data-stu-id="7d4c8-106">The external data will be used as back store for the object's indexed properties and accessed like a typed array.</span></span>  
  
## <span data-ttu-id="7d4c8-107">语法</span><span class="sxs-lookup"><span data-stu-id="7d4c8-107">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsSetIndexedPropertiesToExternalData(  
   _In_ JsValueRef object,  
   _In_ void* data,  
   _In_ JsTypedArrayType arrayType,  
   _In_ unsigned int elementLength  
);  
```  
  
#### <span data-ttu-id="7d4c8-108">参数</span><span class="sxs-lookup"><span data-stu-id="7d4c8-108">Parameters</span></span>  
 `object`  
 <span data-ttu-id="7d4c8-109">要操作的对象。</span><span class="sxs-lookup"><span data-stu-id="7d4c8-109">The object to operate on.</span></span>  
  
 `data`  
 <span data-ttu-id="7d4c8-110">要用作对象索引属性的后端存储的外部数据。</span><span class="sxs-lookup"><span data-stu-id="7d4c8-110">The external data to be used as back store for the object's indexed properties.</span></span>  
  
 `arrayType`  
 <span data-ttu-id="7d4c8-111">外部数据中的数组元素类型。</span><span class="sxs-lookup"><span data-stu-id="7d4c8-111">The array element type in external data.</span></span>  
  
 `elementLength`  
 <span data-ttu-id="7d4c8-112">外部数据中的数组元素数。</span><span class="sxs-lookup"><span data-stu-id="7d4c8-112">The number of array elements in external data.</span></span>  
  
## <span data-ttu-id="7d4c8-113">返回值</span><span class="sxs-lookup"><span data-stu-id="7d4c8-113">Return Value</span></span>  
 <span data-ttu-id="7d4c8-114">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="7d4c8-114">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="7d4c8-115">备注</span><span class="sxs-lookup"><span data-stu-id="7d4c8-115">Remarks</span></span>  
 <span data-ttu-id="7d4c8-116">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="7d4c8-116">Requires an active script context.</span></span>  
  
 <span data-ttu-id="7d4c8-117">此 API 仅在 EdgeHTML 模式下受支持。</span><span class="sxs-lookup"><span data-stu-id="7d4c8-117">This API is supported only in EdgeHTML mode.</span></span>  
  
## <span data-ttu-id="7d4c8-118">要求</span><span class="sxs-lookup"><span data-stu-id="7d4c8-118">Requirements</span></span>  
 <span data-ttu-id="7d4c8-119">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="7d4c8-119">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="7d4c8-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7d4c8-120">See Also</span></span>  
 [<span data-ttu-id="7d4c8-121">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="7d4c8-121">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
