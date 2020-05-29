---
description: 创建新的 JavaScript SyntaxError error 对象。
title: JsCreateSyntaxError 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsCreateSyntaxError
helpviewer_keywords:
- JsCreateSyntaxError function
ms.assetid: 839845fc-60c4-4ffc-bfcc-fd7a8f06126f
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 8f7459e8300df56aa8ccfaa78ef97ce2b6ec6fa0
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563148"
---
# <span data-ttu-id="a50dd-103">JsCreateSyntaxError 函数</span><span class="sxs-lookup"><span data-stu-id="a50dd-103">JsCreateSyntaxError Function</span></span>
<span data-ttu-id="a50dd-104">创建新的 JavaScript SyntaxError error 对象。</span><span class="sxs-lookup"><span data-stu-id="a50dd-104">Creates a new JavaScript SyntaxError error object.</span></span>  
  
## <span data-ttu-id="a50dd-105">语法</span><span class="sxs-lookup"><span data-stu-id="a50dd-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateSyntaxError(  
   _In_ JsValueRef message,  
   _Out_ JsValueRef *error  
);  
```  
  
#### <span data-ttu-id="a50dd-106">参数</span><span class="sxs-lookup"><span data-stu-id="a50dd-106">Parameters</span></span>  
 `message`  
 <span data-ttu-id="a50dd-107">错误对象的消息。</span><span class="sxs-lookup"><span data-stu-id="a50dd-107">Message for the error object.</span></span>  
  
 `error`  
 <span data-ttu-id="a50dd-108">新的错误对象。</span><span class="sxs-lookup"><span data-stu-id="a50dd-108">The new error object.</span></span>  
  
## <span data-ttu-id="a50dd-109">返回值</span><span class="sxs-lookup"><span data-stu-id="a50dd-109">Return Value</span></span>  
 <span data-ttu-id="a50dd-110">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="a50dd-110">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="a50dd-111">备注</span><span class="sxs-lookup"><span data-stu-id="a50dd-111">Remarks</span></span>  
 <span data-ttu-id="a50dd-112">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="a50dd-112">Requires an active script context.</span></span>  
  
## <span data-ttu-id="a50dd-113">要求</span><span class="sxs-lookup"><span data-stu-id="a50dd-113">Requirements</span></span>  
 <span data-ttu-id="a50dd-114">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="a50dd-114">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="a50dd-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a50dd-115">See Also</span></span>  
 [<span data-ttu-id="a50dd-116">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="a50dd-116">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)