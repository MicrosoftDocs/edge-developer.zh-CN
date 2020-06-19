---
description: 表示从 web 视图内容传递到应用程序的通知字符串
title: ScriptNotifyEvent 对象
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/10/2020
ms.topic: reference
ms.prod: microsoft-edge
keywords: web 视图、windows 10 应用、uwp、edge
ms.openlocfilehash: 164bfa7228b1f4ccf9817e4b7231361d090f1394
ms.sourcegitcommit: 037a2d62333691104c9accb4862968f80a3465a2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/18/2020
ms.locfileid: "10752008"
---
# ScriptNotifyEvent 对象  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

一个对象，表示当[web 视图](../webview.md)中包含的内容通过使用 JavaScript 将字符串传递给应用程序时引发的事件。  

## 属性  

### callingUri  

获取页面的统一资源标识符（URI），该页面包含引发**ScriptNotifyEvent**的脚本。  

此属性为只读。  

```javascript
var callingUri = ScriptNotifyEvent.callingUri;
```  

#### 属性值  

类型： **DOMString**  

### 值  

传递给应用程序的方法名称。  

此属性为只读。  

```javascript
var value = ScriptNotifyEvent.value;
```  

#### 属性值  

类型： **DOMString**  
