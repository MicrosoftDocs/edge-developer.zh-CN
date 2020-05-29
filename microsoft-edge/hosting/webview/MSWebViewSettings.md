---
description: 定义启用或禁用 web 视图功能的属性
title: MSWebViewSettings 对象
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/10/2018
ms.topic: reference
ms.prod: microsoft-edge
keywords: web 视图、windows 10 应用、uwp、edge
ms.openlocfilehash: 0e164e7eb44edc636201f283ec4bbe866a122b8e
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563033"
---
# MSWebViewSettings 对象

定义启用或禁用[web 视图](../webview.md)功能的属性。

## 属性

### isIndexedDBEnabled

获取或设置一个值，该值指示[web 视图](../webview.md)中是否允许使用 IndexedDB。

```js
var isIndexedDBEnabled = MSWebViewSettings.isIndexedDBEnabled;
MSWebViewSettings.isIndexedDBEnabled = isIndexedDBEnabled;
```

#### 属性值
类型： **boolean**

如果在**web 视图**中允许 IndexedDB，**则为 True** ;否则**为 false**。 

### isJavaScriptEnabled

获取或设置一个值，该值指示[web 视图](../webview.md)中是否允许使用 JavaScript。

```js
var isJavaScriptEnabled = MSWebViewSettings.isJavaScriptEnabled;
MSWebViewSettings.isJavaScriptEnabled = isJavaScriptEnabled;
```

#### 属性值
类型： **boolean**

**True**在[web 视图](../webview.md)中允许使用 JavaScript;否则**为 false**。 

### isScriptNotifyAllowed

获取或设置一个值，该值指示[web 视图](../webview.md)中是否允许使用[ScriptNotifyEvent](ScriptNotifyEvent.md) 。

```js
var isScriptNotifyAllowed = MSWebViewSettings.isScriptNotifyAllowed;
MSWebViewSettings.isScriptNotifyAllowed = isScriptNotifyAllowed;
```

#### 属性值
类型： **boolean**

在[web 视图](../webview.md)中允许使用**True** [ScriptNotifyEvent](ScriptNotifyEvent.md) ;否则**为 false**。 
