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
# <a name="longrunningscriptdetectedevent-object"></a>LongRunningScriptDetectedEvent 对象  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

提供 [MSWebViewLongRunningScriptDetected 的信息](../webview/index.md#mswebviewlongrunningscriptdetected)。  

## <a name="properties"></a>属性  

### <a name="executiontime"></a>executionTime  

获取 [Webview](../webview/index.md) 元素已执行长时间运行的脚本的毫秒数。  

```javascript
var executionTime = LongRunningScriptDetectedEvent.executionTime;
```  

#### <a name="property-value"></a>属性值  

类型 **：long**  

### <a name="stoppagescriptexecution"></a>stopPageScriptExecution  

停止在 [webview](../webview/index.md) 元素中执行长时间运行的脚本。  

```javascript
var stopPageScriptExecution = LongRunningScriptDetectedEvent.stopPageScriptExecution;
```  

#### <a name="property-value"></a>属性值  

类型 **：Boolean**  
