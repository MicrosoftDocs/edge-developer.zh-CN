---
description: 指示 web 视图正在尝试下载不受支持的文件。
title: UnviewableContentIdentifiedEvent 对象
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/25/2018
ms.topic: reference
ms.prod: microsoft-edge
keywords: web 视图、windows 10 应用、uwp、edge
ms.openlocfilehash: cec85ca2d5458a05cfd88210907523f25fb4af95
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10562558"
---
# UnviewableContentIdentifiedEvent 对象

指示[web 视图](../webview.md)正在尝试导航到不受支持的内容类型的文件。 

## 属性

### 媒体

获取 unviewable 内容的内容类型。

此属性是只读的

```js
var mediaType = UnviewableContentIdentifiedEvent.mediaType;
```

#### 属性值
类型： **DOMString**

### referer

[Web 视图](../webview.md)中请求导航的页面的统一资源标识符（URI）。

此属性为只读。


```js
var referer = NavigationEventWithReferrer.referer;
```

#### 属性值
类型： **DOMString**

### uri

导航的目标的统一资源标识符（URI）。

此属性为只读。

```js
var uri = NavigationEventWithReferrer.uri;
```

#### 属性值
类型： **DOMString**
