---
description: ''
title: LongRunningScriptDetectedEvent 对象
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/10/2018
ms.topic: reference
ms.prod: microsoft-edge
keywords: web 视图、windows 10 应用、uwp、edge
ms.openlocfilehash: 6cf7af656531eea5046f7af44d4d43ff224d0f08
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563042"
---
# <span data-ttu-id="af569-103">LongRunningScriptDetectedEvent 对象</span><span class="sxs-lookup"><span data-stu-id="af569-103">LongRunningScriptDetectedEvent object</span></span>

<span data-ttu-id="af569-104">提供有关[MSWebViewLongRunningScriptDetected](../webview.md#mswebviewlongrunningscriptdetected)的信息。</span><span class="sxs-lookup"><span data-stu-id="af569-104">Provides information for [MSWebViewLongRunningScriptDetected](../webview.md#mswebviewlongrunningscriptdetected).</span></span>

## <span data-ttu-id="af569-105">属性</span><span class="sxs-lookup"><span data-stu-id="af569-105">Properties</span></span>

### <span data-ttu-id="af569-106">executionTime</span><span class="sxs-lookup"><span data-stu-id="af569-106">executionTime</span></span>

<span data-ttu-id="af569-107">获取[web 视图](../webview.md)元素已执行长时间运行的脚本的毫秒数。</span><span class="sxs-lookup"><span data-stu-id="af569-107">Gets the number of milliseconds that the [webview](../webview.md) element has been executing a long-running script.</span></span>

```js
var executionTime = LongRunningScriptDetectedEvent.executionTime;
```

#### <span data-ttu-id="af569-108">属性值</span><span class="sxs-lookup"><span data-stu-id="af569-108">Property value</span></span>
<span data-ttu-id="af569-109">键入： **long**</span><span class="sxs-lookup"><span data-stu-id="af569-109">Type: **long**</span></span>

### <span data-ttu-id="af569-110">stopPageScriptExecution</span><span class="sxs-lookup"><span data-stu-id="af569-110">stopPageScriptExecution</span></span>
<span data-ttu-id="af569-111">停止在[web 视图](../webview.md)元素中执行的长时间运行的脚本。</span><span class="sxs-lookup"><span data-stu-id="af569-111">Stops a long-running script executing in the [webview](../webview.md) element.</span></span>

```js
var stopPageScriptExecution = LongRunningScriptDetectedEvent.stopPageScriptExecution;
```

#### <span data-ttu-id="af569-112">属性值</span><span class="sxs-lookup"><span data-stu-id="af569-112">Property value</span></span>
<span data-ttu-id="af569-113">类型： **Boolean**</span><span class="sxs-lookup"><span data-stu-id="af569-113">Type: **Boolean**</span></span>