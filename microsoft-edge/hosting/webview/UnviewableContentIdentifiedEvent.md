---
description: 指示 web 视图正在尝试下载不受支持的文件。
title: UnviewableContentIdentifiedEvent 对象
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/10/2020
ms.topic: reference
ms.prod: microsoft-edge
keywords: web 视图、windows 10 应用、uwp、edge
ms.openlocfilehash: 0179522f3eaf0813531084eb996ee9d392e8249d
ms.sourcegitcommit: 037a2d62333691104c9accb4862968f80a3465a2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/18/2020
ms.locfileid: "10752011"
---
# UnviewableContentIdentifiedEvent 对象  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

指示[web 视图](../webview.md)正在尝试导航到不受支持的内容类型的文件。  

## 属性  

### 媒体  

获取 unviewable 内容的内容类型。  

此属性是只读的  

```javascript
var mediaType = UnviewableContentIdentifiedEvent.mediaType;
```  

#### 属性值  

类型： **DOMString**  

### referer  

[Web 视图](../webview.md)中请求导航的页面的统一资源标识符（URI）。  

此属性为只读。  

```javascript
var referer = NavigationEventWithReferrer.referer;
```  

#### 属性值  

类型： **DOMString**  

### uri  

导航的目标的统一资源标识符（URI）。  

此属性为只读。  

```javascript
var uri = NavigationEventWithReferrer.uri;
```  

#### 属性值  

类型： **DOMString**  
