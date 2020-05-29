---
description: 包含有关导航的引用信息
title: NavigationEventWithReferrer 对象
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/22/2018
ms.topic: reference
ms.prod: microsoft-edge
keywords: web 视图、windows 10 应用、uwp、edge
ms.openlocfilehash: b11f60724387d996d0a730965602b5ead6a84145
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563026"
---
# NavigationEventWithReferrer 对象

一个对象，表示在启动导航且导航包含 referer 时激发的事件。

## 属性

### referer

[Web 视图](../webview.md)中请求导航的页面的统一资源标识符（URI）。

此属性为只读。

#### 属性值
类型： **DOMString**


```js
var referer = NavigationEventWithReferrer.referer;
```

### uri

导航的目标的统一资源标识符（URI）。

此属性为只读。

```js
var uri = NavigationEventWithReferrer.uri;
```

#### 属性值
类型： **DOMString**
