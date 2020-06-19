---
description: ''
title: LongRunningScriptDetectedEvent 对象
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/10/2020
ms.topic: reference
ms.prod: microsoft-edge
keywords: web 视图、windows 10 应用、uwp、edge
ms.openlocfilehash: 5fe90495b83ab8f95ee594d3400c8c1a26f0547e
ms.sourcegitcommit: 037a2d62333691104c9accb4862968f80a3465a2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/18/2020
ms.locfileid: "10752148"
---
# <span data-ttu-id="78c59-103">LongRunningScriptDetectedEvent 对象</span><span class="sxs-lookup"><span data-stu-id="78c59-103">LongRunningScriptDetectedEvent object</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

<span data-ttu-id="78c59-104">提供有关[MSWebViewLongRunningScriptDetected](../webview.md#mswebviewlongrunningscriptdetected)的信息。</span><span class="sxs-lookup"><span data-stu-id="78c59-104">Provides information for [MSWebViewLongRunningScriptDetected](../webview.md#mswebviewlongrunningscriptdetected).</span></span>  

## <span data-ttu-id="78c59-105">属性</span><span class="sxs-lookup"><span data-stu-id="78c59-105">Properties</span></span>  

### <span data-ttu-id="78c59-106">executionTime</span><span class="sxs-lookup"><span data-stu-id="78c59-106">executionTime</span></span>  

<span data-ttu-id="78c59-107">获取[web 视图](../webview.md)元素已执行长时间运行的脚本的毫秒数。</span><span class="sxs-lookup"><span data-stu-id="78c59-107">Gets the number of milliseconds that the [webview](../webview.md) element has been executing a long-running script.</span></span>  

```javascript
var executionTime = LongRunningScriptDetectedEvent.executionTime;
```  

#### <span data-ttu-id="78c59-108">属性值</span><span class="sxs-lookup"><span data-stu-id="78c59-108">Property value</span></span>  

<span data-ttu-id="78c59-109">键入： **long**</span><span class="sxs-lookup"><span data-stu-id="78c59-109">Type: **long**</span></span>  

### <span data-ttu-id="78c59-110">stopPageScriptExecution</span><span class="sxs-lookup"><span data-stu-id="78c59-110">stopPageScriptExecution</span></span>  

<span data-ttu-id="78c59-111">停止在[web 视图](../webview.md)元素中执行的长时间运行的脚本。</span><span class="sxs-lookup"><span data-stu-id="78c59-111">Stops a long-running script executing in the [webview](../webview.md) element.</span></span>  

```javascript
var stopPageScriptExecution = LongRunningScriptDetectedEvent.stopPageScriptExecution;
```  

#### <span data-ttu-id="78c59-112">属性值</span><span class="sxs-lookup"><span data-stu-id="78c59-112">Property value</span></span>  

<span data-ttu-id="78c59-113">类型： **Boolean**</span><span class="sxs-lookup"><span data-stu-id="78c59-113">Type: **Boolean**</span></span>  
