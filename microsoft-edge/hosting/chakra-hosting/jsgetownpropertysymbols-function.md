---
description: 获取对象上的所有符号属性的列表。
title: JsGetOwnPropertySymbols 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 57c431e3-de0b-4ed0-b750-87a86448daff
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: c7a7f4e88986a45fbccfae0c53e92ff2e5313991
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564250"
---
# <span data-ttu-id="7bf03-103">JsGetOwnPropertySymbols 函数</span><span class="sxs-lookup"><span data-stu-id="7bf03-103">JsGetOwnPropertySymbols Function</span></span>
<span data-ttu-id="7bf03-104">获取对象上的所有符号属性的列表。</span><span class="sxs-lookup"><span data-stu-id="7bf03-104">Gets the list of all symbol properties on the object.</span></span>  
  
## <span data-ttu-id="7bf03-105">语法</span><span class="sxs-lookup"><span data-stu-id="7bf03-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsGetOwnPropertySymbols(  
   _In_ JsValueRef object,  
   _Out_ JsValueRef *propertySymbols  
);  
```  
  
#### <span data-ttu-id="7bf03-106">参数</span><span class="sxs-lookup"><span data-stu-id="7bf03-106">Parameters</span></span>  
 `object`  
 <span data-ttu-id="7bf03-107">要从中获取属性符号的对象。</span><span class="sxs-lookup"><span data-stu-id="7bf03-107">The object from which to get the property symbols.</span></span>  
  
 `propertySymbols`  
 <span data-ttu-id="7bf03-108">属性符号数组。</span><span class="sxs-lookup"><span data-stu-id="7bf03-108">An array of property symbols.</span></span>  
  
## <span data-ttu-id="7bf03-109">返回值</span><span class="sxs-lookup"><span data-stu-id="7bf03-109">Return Value</span></span>  
 <span data-ttu-id="7bf03-110">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="7bf03-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="7bf03-111">备注</span><span class="sxs-lookup"><span data-stu-id="7bf03-111">Remarks</span></span>  
 <span data-ttu-id="7bf03-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="7bf03-112">Requires an active script context.</span></span>  
  
 <span data-ttu-id="7bf03-113">此 API 仅在 Microsoft Edge 模式下受支持。</span><span class="sxs-lookup"><span data-stu-id="7bf03-113">This API is supported only in Microsoft Edge mode.</span></span>  
  
## <span data-ttu-id="7bf03-114">要求</span><span class="sxs-lookup"><span data-stu-id="7bf03-114">Requirements</span></span>  
 <span data-ttu-id="7bf03-115">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="7bf03-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="7bf03-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7bf03-116">See Also</span></span>  
 [<span data-ttu-id="7bf03-117">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="7bf03-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)