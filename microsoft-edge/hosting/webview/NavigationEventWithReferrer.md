---
description: 包含有关导航的引用信息
title: NavigationEventWithReferrer 对象
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/10/2020
ms.topic: reference
ms.prod: microsoft-edge
keywords: web 视图、windows 10 应用、uwp、edge
ms.openlocfilehash: 72c8a213f632e9e74145de9c34b949adf074cd22
ms.sourcegitcommit: 037a2d62333691104c9accb4862968f80a3465a2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/18/2020
ms.locfileid: "10752123"
---
# NavigationEventWithReferrer 对象  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

一个对象，表示在启动导航且导航包含 referer 时激发的事件。  

## 属性  

### referer

[Web 视图](../webview.md)中请求导航的页面的统一资源标识符（URI）。  

此属性为只读。  

#### 属性值  

类型： **DOMString**  

```javascript
var referer = NavigationEventWithReferrer.referer;
```  

### uri  

导航的目标的统一资源标识符（URI）。  

此属性为只读。  

```javascript
var uri = NavigationEventWithReferrer.uri;
```  

#### 属性值  

类型： **DOMString**  
