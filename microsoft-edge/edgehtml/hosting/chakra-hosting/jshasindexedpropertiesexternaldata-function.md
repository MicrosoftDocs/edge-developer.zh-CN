---
description: 确定对象在外部数据中是否具有其索引属性。
title: JsHasIndexedPropertiesExternalData 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: c676db20-3ef1-4f84-8b26-3e06fe0ab2bf
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: e6395bacb15904bc3f2e74d22959844e8e0af373
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232698"
---
# <span data-ttu-id="713df-103">JsHasIndexedPropertiesExternalData 函数</span><span class="sxs-lookup"><span data-stu-id="713df-103">JsHasIndexedPropertiesExternalData Function</span></span>

<span data-ttu-id="713df-104">确定对象在外部数据中是否具有其索引属性。</span><span class="sxs-lookup"><span data-stu-id="713df-104">Determines whether an object has its indexed properties in external data.</span></span>  
  
## <span data-ttu-id="713df-105">语法</span><span class="sxs-lookup"><span data-stu-id="713df-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsHasIndexedPropertiesExternalData(  
   _In_ JsValueRef object,  
   _Out_ bool* value  
);  
```  
  
#### <span data-ttu-id="713df-106">参数</span><span class="sxs-lookup"><span data-stu-id="713df-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="713df-107">对象。</span><span class="sxs-lookup"><span data-stu-id="713df-107">The object.</span></span>  
  
 `value`  
 <span data-ttu-id="713df-108">对象在外部数据中是否具有其索引属性。</span><span class="sxs-lookup"><span data-stu-id="713df-108">Whether the object has its indexed properties in external data.</span></span>  
  
## <span data-ttu-id="713df-109">返回值</span><span class="sxs-lookup"><span data-stu-id="713df-109">Return Value</span></span>  
 <span data-ttu-id="713df-110">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="713df-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="713df-111">备注</span><span class="sxs-lookup"><span data-stu-id="713df-111">Remarks</span></span>  
 <span data-ttu-id="713df-112">此 API 仅在 Microsoft Edge 模式下受支持。</span><span class="sxs-lookup"><span data-stu-id="713df-112">This API is supported only in Microsoft Edge mode.</span></span>  
  
## <span data-ttu-id="713df-113">要求</span><span class="sxs-lookup"><span data-stu-id="713df-113">Requirements</span></span>  
 <span data-ttu-id="713df-114">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="713df-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="713df-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="713df-115">See Also</span></span>  
 [<span data-ttu-id="713df-116">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="713df-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
