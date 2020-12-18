---
description: 检索对象的索引属性外部数据信息。
title: JsGetIndexedPropertiesExternalData 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 2c313163-3462-42fd-8dee-3dfb3ac7f43f
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 627aaef48def2e042927467e1cbb6d6b7c06a525
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232030"
---
# <span data-ttu-id="e7b1b-103">JsGetIndexedPropertiesExternalData 函数</span><span class="sxs-lookup"><span data-stu-id="e7b1b-103">JsGetIndexedPropertiesExternalData Function</span></span>

<span data-ttu-id="e7b1b-104">检索对象的索引属性外部数据信息。</span><span class="sxs-lookup"><span data-stu-id="e7b1b-104">Retrieves an object's indexed properties external data information.</span></span>  
  
## <span data-ttu-id="e7b1b-105">语法</span><span class="sxs-lookup"><span data-stu-id="e7b1b-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetIndexedPropertiesExternalData(  
   _In_ JsValueRef object,  
   _Out_ void** data,  
   _Out_ JsTypedArrayType* arrayType,  
   _Out_ unsigned int* elementLength  
);  
```  
  
#### <span data-ttu-id="e7b1b-106">参数</span><span class="sxs-lookup"><span data-stu-id="e7b1b-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="e7b1b-107">对象。</span><span class="sxs-lookup"><span data-stu-id="e7b1b-107">The object.</span></span>  
  
 `data`  
 <span data-ttu-id="e7b1b-108">对象的索引属性的外部数据回存储。</span><span class="sxs-lookup"><span data-stu-id="e7b1b-108">The external data back store for the object's indexed properties.</span></span>  
  
 `arrayType`  
 <span data-ttu-id="e7b1b-109">外部数据中的数组元素类型。</span><span class="sxs-lookup"><span data-stu-id="e7b1b-109">The array element type in external data.</span></span>  
  
 `elementLength`  
 <span data-ttu-id="e7b1b-110">外部数据中的数组元素数。</span><span class="sxs-lookup"><span data-stu-id="e7b1b-110">The number of array elements in external data.</span></span>  
  
## <span data-ttu-id="e7b1b-111">返回值</span><span class="sxs-lookup"><span data-stu-id="e7b1b-111">Return Value</span></span>  
 <span data-ttu-id="e7b1b-112">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="e7b1b-112">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="e7b1b-113">备注</span><span class="sxs-lookup"><span data-stu-id="e7b1b-113">Remarks</span></span>  
 <span data-ttu-id="e7b1b-114">此 API 仅在 Microsoft Edge 模式下受支持。</span><span class="sxs-lookup"><span data-stu-id="e7b1b-114">This API is supported only in Microsoft Edge mode.</span></span>  
  
## <span data-ttu-id="e7b1b-115">要求</span><span class="sxs-lookup"><span data-stu-id="e7b1b-115">Requirements</span></span>  
 <span data-ttu-id="e7b1b-116">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="e7b1b-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="e7b1b-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e7b1b-117">See Also</span></span>  
 [<span data-ttu-id="e7b1b-118">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="e7b1b-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
