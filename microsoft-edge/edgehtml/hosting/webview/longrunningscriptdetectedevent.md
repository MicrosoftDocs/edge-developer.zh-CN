---
description: LongRunningScriptDetectedEvent 对象
title: LongRunningScriptDetectedEvent 对象
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/03/2020
ms.topic: reference
ms.prod: microsoft-edge
keywords: webview， windows 10 应用， uwp， edge
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 5f5eb3230e46ee2cd7926b21f6526e512a7a0322
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11397937"
---
# <a name="longrunningscriptdetectedevent-object"></a><span data-ttu-id="7c94f-104">LongRunningScriptDetectedEvent 对象</span><span class="sxs-lookup"><span data-stu-id="7c94f-104">LongRunningScriptDetectedEvent object</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

<span data-ttu-id="7c94f-105">提供 [MSWebViewLongRunningScriptDetected 的信息](../webview/index.md#mswebviewlongrunningscriptdetected)。</span><span class="sxs-lookup"><span data-stu-id="7c94f-105">Provides information for [MSWebViewLongRunningScriptDetected](../webview/index.md#mswebviewlongrunningscriptdetected).</span></span>  

## <a name="properties"></a><span data-ttu-id="7c94f-106">属性</span><span class="sxs-lookup"><span data-stu-id="7c94f-106">Properties</span></span>  

### <a name="executiontime"></a><span data-ttu-id="7c94f-107">executionTime</span><span class="sxs-lookup"><span data-stu-id="7c94f-107">executionTime</span></span>  

<span data-ttu-id="7c94f-108">获取 [Webview](../webview/index.md) 元素已执行长时间运行的脚本的毫秒数。</span><span class="sxs-lookup"><span data-stu-id="7c94f-108">Gets the number of milliseconds that the [webview](../webview/index.md) element has been executing a long-running script.</span></span>  

```javascript
var executionTime = LongRunningScriptDetectedEvent.executionTime;
```  

#### <a name="property-value"></a><span data-ttu-id="7c94f-109">属性值</span><span class="sxs-lookup"><span data-stu-id="7c94f-109">Property value</span></span>  

<span data-ttu-id="7c94f-110">类型 **：long**</span><span class="sxs-lookup"><span data-stu-id="7c94f-110">Type: **long**</span></span>  

### <a name="stoppagescriptexecution"></a><span data-ttu-id="7c94f-111">stopPageScriptExecution</span><span class="sxs-lookup"><span data-stu-id="7c94f-111">stopPageScriptExecution</span></span>  

<span data-ttu-id="7c94f-112">停止在 [webview](../webview/index.md) 元素中执行长时间运行的脚本。</span><span class="sxs-lookup"><span data-stu-id="7c94f-112">Stops a long-running script executing in the [webview](../webview/index.md) element.</span></span>  

```javascript
var stopPageScriptExecution = LongRunningScriptDetectedEvent.stopPageScriptExecution;
```  

#### <a name="property-value"></a><span data-ttu-id="7c94f-113">属性值</span><span class="sxs-lookup"><span data-stu-id="7c94f-113">Property value</span></span>  

<span data-ttu-id="7c94f-114">类型 **：Boolean**</span><span class="sxs-lookup"><span data-stu-id="7c94f-114">Type: **Boolean**</span></span>  
