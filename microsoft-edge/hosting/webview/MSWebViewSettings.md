---
description: 定义启用或禁用 web 视图功能的属性
title: MSWebViewSettings 对象
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/10/2020
ms.topic: reference
ms.prod: microsoft-edge
keywords: web 视图、windows 10 应用、uwp、edge
ms.openlocfilehash: 147f852f8fbcb2a748c00b472814e9cc45b9c9da
ms.sourcegitcommit: 037a2d62333691104c9accb4862968f80a3465a2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/18/2020
ms.locfileid: "10752176"
---
# MSWebViewSettings 对象  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

定义启用或禁用[web 视图](../webview.md)功能的属性。  

## 属性  

### isIndexedDBEnabled  

获取或设置一个值，该值指示[web 视图](../webview.md)中是否允许使用 IndexedDB。  

```javascript
var isIndexedDBEnabled = MSWebViewSettings.isIndexedDBEnabled;
MSWebViewSettings.isIndexedDBEnabled = isIndexedDBEnabled;
```  

#### 属性值  

类型： **boolean**  

如果在**web 视图**中允许 IndexedDB，**则为 True** ;否则**为 false**。  

### isJavaScriptEnabled  

获取或设置一个值，该值指示[web 视图](../webview.md)中是否允许使用 JavaScript。  

```javascript
var isJavaScriptEnabled = MSWebViewSettings.isJavaScriptEnabled;
MSWebViewSettings.isJavaScriptEnabled = isJavaScriptEnabled;
```  

#### 属性值  

类型： **boolean**  

**True**在[web 视图](../webview.md)中允许使用 JavaScript;否则**为 false**。  

### isScriptNotifyAllowed  

获取或设置一个值，该值指示[web 视图](../webview.md)中是否允许使用[ScriptNotifyEvent](ScriptNotifyEvent.md) 。  

```javascript
var isScriptNotifyAllowed = MSWebViewSettings.isScriptNotifyAllowed;
MSWebViewSettings.isScriptNotifyAllowed = isScriptNotifyAllowed;
```  

#### 属性值  

类型： **boolean**  

在[web 视图](../webview.md)中允许使用**True** [ScriptNotifyEvent](ScriptNotifyEvent.md) ;否则**为 false**。  
