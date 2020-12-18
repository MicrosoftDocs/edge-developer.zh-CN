---
description: 规划 WinRT 命名空间。
title: JsProjectWinRTNamespace 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 8a23c154-df4b-4ce3-9fef-f41f90acdb87
caps.latest.revision: 5
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: f781cf90aaec68b2bd305bf34c453fc663ad0187
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232765"
---
# <span data-ttu-id="e6570-103">JsProjectWinRTNamespace 函数</span><span class="sxs-lookup"><span data-stu-id="e6570-103">JsProjectWinRTNamespace Function</span></span>

<span data-ttu-id="e6570-104">规划 WinRT 命名空间。</span><span class="sxs-lookup"><span data-stu-id="e6570-104">Project a WinRT namespace.</span></span>  
  
## <span data-ttu-id="e6570-105">语法</span><span class="sxs-lookup"><span data-stu-id="e6570-105">Syntax</span></span>  
  
```cpp  
STDAPI_(JsErrorCode)  
   JsProjectWinRTNamespace(  
   _In_z_ const wchar_t *namespaceName  
);  
```  
  
#### <span data-ttu-id="e6570-106">参数</span><span class="sxs-lookup"><span data-stu-id="e6570-106">Parameters</span></span>  
 `namespaceName`  
 <span data-ttu-id="e6570-107">要规划的 WinRT 命名空间。</span><span class="sxs-lookup"><span data-stu-id="e6570-107">The WinRT namespace to be projected.</span></span>  
  
## <span data-ttu-id="e6570-108">返回值</span><span class="sxs-lookup"><span data-stu-id="e6570-108">Return Value</span></span>  
 <span data-ttu-id="e6570-109">如果 `JsNoError` 操作成功，则代码，否则为失败代码。</span><span class="sxs-lookup"><span data-stu-id="e6570-109">The code `JsNoError` if the operation succeeded, a failure code otherwise.</span></span>  
  
## <span data-ttu-id="e6570-110">备注</span><span class="sxs-lookup"><span data-stu-id="e6570-110">Remarks</span></span>  
 <span data-ttu-id="e6570-111">需要活动脚本上下文。</span><span class="sxs-lookup"><span data-stu-id="e6570-111">Requires an active script context.</span></span>  
  
 <span data-ttu-id="e6570-112">此 API 仅在 EdgeHTML 模式下受支持。</span><span class="sxs-lookup"><span data-stu-id="e6570-112">This API is supported only in EdgeHTML mode.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e6570-113">WinRT 是通用 Windows 平台和 UWP (之前的平台) 。</span><span class="sxs-lookup"><span data-stu-id="e6570-113">WinRT was the platform name before Universal Windows Platform (UWP).</span></span>  
  
## <span data-ttu-id="e6570-114">要求</span><span class="sxs-lookup"><span data-stu-id="e6570-114">Requirements</span></span>  
 <span data-ttu-id="e6570-115">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="e6570-115">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="e6570-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e6570-116">See Also</span></span>  
 [<span data-ttu-id="e6570-117">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="e6570-117">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
