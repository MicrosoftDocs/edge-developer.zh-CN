---
description: 表示从 web 视图内容传递到应用程序的通知字符串
title: ScriptNotifyEvent 对象
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2018
ms.topic: reference
ms.prod: microsoft-edge
keywords: web 视图、windows 10 应用、uwp、edge
ms.openlocfilehash: 22313f2d96ca2c5d4d3554ca40589b9a583c89cd
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10562559"
---
# ScriptNotifyEvent 对象

一个对象，表示当[web 视图](../webview.md)中包含的内容通过使用 JavaScript 将字符串传递给应用程序时引发的事件。

## 属性
    
### callingUri

获取页面的统一资源标识符（URI），该页面包含引发**ScriptNotifyEvent**的脚本。

此属性为只读。

```js
var callingUri = ScriptNotifyEvent.callingUri;
```

#### 属性值
类型： **DOMString**

### 值

传递给应用程序的方法名称。

此属性为只读。

```js
var value = ScriptNotifyEvent.value;
```

#### 属性值
类型： **DOMString**