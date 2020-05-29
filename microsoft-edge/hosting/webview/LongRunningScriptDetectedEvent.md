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
# LongRunningScriptDetectedEvent 对象

提供有关[MSWebViewLongRunningScriptDetected](../webview.md#mswebviewlongrunningscriptdetected)的信息。

## 属性

### executionTime

获取[web 视图](../webview.md)元素已执行长时间运行的脚本的毫秒数。

```js
var executionTime = LongRunningScriptDetectedEvent.executionTime;
```

#### 属性值
键入： **long**

### stopPageScriptExecution
停止在[web 视图](../webview.md)元素中执行的长时间运行的脚本。

```js
var stopPageScriptExecution = LongRunningScriptDetectedEvent.stopPageScriptExecution;
```

#### 属性值
类型： **Boolean**