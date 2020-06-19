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
# LongRunningScriptDetectedEvent 对象  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

提供有关[MSWebViewLongRunningScriptDetected](../webview.md#mswebviewlongrunningscriptdetected)的信息。  

## 属性  

### executionTime  

获取[web 视图](../webview.md)元素已执行长时间运行的脚本的毫秒数。  

```javascript
var executionTime = LongRunningScriptDetectedEvent.executionTime;
```  

#### 属性值  

键入： **long**  

### stopPageScriptExecution  

停止在[web 视图](../webview.md)元素中执行的长时间运行的脚本。  

```javascript
var stopPageScriptExecution = LongRunningScriptDetectedEvent.stopPageScriptExecution;
```  

#### 属性值  

类型： **Boolean**  
