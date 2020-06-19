---
description: 包含有关已完成的 web 视图导航的信息
title: NavigationCompletedEvent 对象
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/10/2020
ms.topic: reference
ms.prod: microsoft-edge
keywords: web 视图、windows 10 应用、uwp、edge
ms.openlocfilehash: eb5727ab59dbaf056f05ab4b19450c70f85d595f
ms.sourcegitcommit: 037a2d62333691104c9accb4862968f80a3465a2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/18/2020
ms.locfileid: "10752135"
---
# NavigationCompletedEvent 对象  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

一个对象，表示当[web 视图](../webview.md)已完成加载当前内容或导航失败时引发的事件。  

## 属性  

### uri  

导航的统一资源标识符（URI）。  

此属性为只读。  

```javascript
var uri = NavigationCompletedEvent.uri;
```  

#### 属性值  

类型： **DOMString**  

### isSuccess  

获取一个值，该值指示导航是否已成功完成。  

此属性为只读。  

```javascript
var isSuccess = NavigationCompletedEvent.isSuccess;
```  

#### 属性值  

类型： **Boolean**  

### webErrorStatus  

如果导航失败，获取指示原因的值。  

此属性为只读。  

```javascript
var webErrorStatus = NavigationCompletedEvent.webErrorStatus;
```  

#### 属性值  

类型：**无符号长**  
