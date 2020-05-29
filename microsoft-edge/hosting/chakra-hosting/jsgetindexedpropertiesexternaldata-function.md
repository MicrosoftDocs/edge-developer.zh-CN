---
description: 检索对象的索引属性外部数据信息。
title: JsGetIndexedPropertiesExternalData 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 2c313163-3462-42fd-8dee-3dfb3ac7f43f
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 96fdcd4b6fe29ffc20a796983cc1de692c80a3f1
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563119"
---
# <span data-ttu-id="3b1d0-103">JsGetIndexedPropertiesExternalData 函数</span><span class="sxs-lookup"><span data-stu-id="3b1d0-103">JsGetIndexedPropertiesExternalData Function</span></span>
<span data-ttu-id="3b1d0-104">检索对象的索引属性外部数据信息。</span><span class="sxs-lookup"><span data-stu-id="3b1d0-104">Retrieves an object's indexed properties external data information.</span></span>  
  
## <span data-ttu-id="3b1d0-105">语法</span><span class="sxs-lookup"><span data-stu-id="3b1d0-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetIndexedPropertiesExternalData(  
   _In_ JsValueRef object,  
   _Out_ void** data,  
   _Out_ JsTypedArrayType* arrayType,  
   _Out_ unsigned int* elementLength  
);  
```  
  
#### <span data-ttu-id="3b1d0-106">参数</span><span class="sxs-lookup"><span data-stu-id="3b1d0-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="3b1d0-107">该对象。</span><span class="sxs-lookup"><span data-stu-id="3b1d0-107">The object.</span></span>  
  
 `data`  
 <span data-ttu-id="3b1d0-108">对象的索引属性的外部数据后置存储。</span><span class="sxs-lookup"><span data-stu-id="3b1d0-108">The external data back store for the object's indexed properties.</span></span>  
  
 `arrayType`  
 <span data-ttu-id="3b1d0-109">外部数据中的数组元素类型。</span><span class="sxs-lookup"><span data-stu-id="3b1d0-109">The array element type in external data.</span></span>  
  
 `elementLength`  
 <span data-ttu-id="3b1d0-110">外部数据中数组元素的数量。</span><span class="sxs-lookup"><span data-stu-id="3b1d0-110">The number of array elements in external data.</span></span>  
  
## <span data-ttu-id="3b1d0-111">返回值</span><span class="sxs-lookup"><span data-stu-id="3b1d0-111">Return Value</span></span>  
 <span data-ttu-id="3b1d0-112">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="3b1d0-112">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="3b1d0-113">备注</span><span class="sxs-lookup"><span data-stu-id="3b1d0-113">Remarks</span></span>  
 <span data-ttu-id="3b1d0-114">此 API 仅在 Microsoft Edge 模式下受支持。</span><span class="sxs-lookup"><span data-stu-id="3b1d0-114">This API is supported only in Microsoft Edge mode.</span></span>  
  
## <span data-ttu-id="3b1d0-115">要求</span><span class="sxs-lookup"><span data-stu-id="3b1d0-115">Requirements</span></span>  
 <span data-ttu-id="3b1d0-116">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="3b1d0-116">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="3b1d0-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3b1d0-117">See Also</span></span>  
 [<span data-ttu-id="3b1d0-118">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="3b1d0-118">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)