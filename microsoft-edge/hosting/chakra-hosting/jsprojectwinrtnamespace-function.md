---
description: Project for WinRT 命名空间。
title: JsProjectWinRTNamespace 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 8a23c154-df4b-4ce3-9fef-f41f90acdb87
caps.latest.revision: 5
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: c4d63727b3d25bbb346fee7179ae0d942ae37008
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563072"
---
# <span data-ttu-id="9eb9f-103">JsProjectWinRTNamespace 函数</span><span class="sxs-lookup"><span data-stu-id="9eb9f-103">JsProjectWinRTNamespace Function</span></span>
<span data-ttu-id="9eb9f-104">Project for WinRT 命名空间。</span><span class="sxs-lookup"><span data-stu-id="9eb9f-104">Project a WinRT namespace.</span></span>  
  
## <span data-ttu-id="9eb9f-105">语法</span><span class="sxs-lookup"><span data-stu-id="9eb9f-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode)  
   JsProjectWinRTNamespace(  
   _In_z_ const wchar_t *namespaceName  
);  
```  
  
#### <span data-ttu-id="9eb9f-106">参数</span><span class="sxs-lookup"><span data-stu-id="9eb9f-106">Parameters</span></span>  
 `namespaceName`  
 <span data-ttu-id="9eb9f-107">要投影的 WinRT 命名空间。</span><span class="sxs-lookup"><span data-stu-id="9eb9f-107">The WinRT namespace to be projected.</span></span>  
  
## <span data-ttu-id="9eb9f-108">返回值</span><span class="sxs-lookup"><span data-stu-id="9eb9f-108">Return Value</span></span>  
 <span data-ttu-id="9eb9f-109">`JsNoError`如果操作成功，则为代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="9eb9f-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="9eb9f-110">备注</span><span class="sxs-lookup"><span data-stu-id="9eb9f-110">Remarks</span></span>  
 <span data-ttu-id="9eb9f-111">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="9eb9f-111">Requires an active script context.</span></span>  
  
 <span data-ttu-id="9eb9f-112">此 API 仅在 EdgeHTML 模式下受支持。</span><span class="sxs-lookup"><span data-stu-id="9eb9f-112">This API is supported only in EdgeHTML mode.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9eb9f-113">WinRT 是通用 Windows 平台（UWP）之前的平台名称。</span><span class="sxs-lookup"><span data-stu-id="9eb9f-113">WinRT was the platform name before Universal Windows Platform (UWP).</span></span>  
  
## <span data-ttu-id="9eb9f-114">要求</span><span class="sxs-lookup"><span data-stu-id="9eb9f-114">Requirements</span></span>  
 <span data-ttu-id="9eb9f-115">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="9eb9f-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="9eb9f-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9eb9f-116">See Also</span></span>  
 [<span data-ttu-id="9eb9f-117">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="9eb9f-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)