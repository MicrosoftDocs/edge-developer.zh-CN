---
description: 确定对象在外部数据中是否具有索引属性。
title: JsHasIndexedPropertiesExternalData 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: c676db20-3ef1-4f84-8b26-3e06fe0ab2bf
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: c7f9f87b19016b3d837b637219eec936a11211e9
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564232"
---
# <span data-ttu-id="bdddd-103">JsHasIndexedPropertiesExternalData 函数</span><span class="sxs-lookup"><span data-stu-id="bdddd-103">JsHasIndexedPropertiesExternalData Function</span></span>
<span data-ttu-id="bdddd-104">确定对象在外部数据中是否具有索引属性。</span><span class="sxs-lookup"><span data-stu-id="bdddd-104">Determines whether an object has its indexed properties in external data.</span></span>  
  
## <span data-ttu-id="bdddd-105">语法</span><span class="sxs-lookup"><span data-stu-id="bdddd-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsHasIndexedPropertiesExternalData(  
   _In_ JsValueRef object,  
   _Out_ bool* value  
);  
```  
  
#### <span data-ttu-id="bdddd-106">参数</span><span class="sxs-lookup"><span data-stu-id="bdddd-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="bdddd-107">该对象。</span><span class="sxs-lookup"><span data-stu-id="bdddd-107">The object.</span></span>  
  
 `value`  
 <span data-ttu-id="bdddd-108">对象在外部数据中是否具有索引属性。</span><span class="sxs-lookup"><span data-stu-id="bdddd-108">Whether the object has its indexed properties in external data.</span></span>  
  
## <span data-ttu-id="bdddd-109">返回值</span><span class="sxs-lookup"><span data-stu-id="bdddd-109">Return Value</span></span>  
 <span data-ttu-id="bdddd-110">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="bdddd-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="bdddd-111">备注</span><span class="sxs-lookup"><span data-stu-id="bdddd-111">Remarks</span></span>  
 <span data-ttu-id="bdddd-112">此 API 仅在 Microsoft Edge 模式下受支持。</span><span class="sxs-lookup"><span data-stu-id="bdddd-112">This API is supported only in Microsoft Edge mode.</span></span>  
  
## <span data-ttu-id="bdddd-113">要求</span><span class="sxs-lookup"><span data-stu-id="bdddd-113">Requirements</span></span>  
 <span data-ttu-id="bdddd-114">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="bdddd-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="bdddd-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bdddd-115">See Also</span></span>  
 [<span data-ttu-id="bdddd-116">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="bdddd-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)