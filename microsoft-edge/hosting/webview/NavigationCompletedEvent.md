---
description: 包含有关已完成的 web 视图导航的信息
title: NavigationCompletedEvent 对象
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/26/2018
ms.topic: reference
ms.prod: microsoft-edge
keywords: web 视图、windows 10 应用、uwp、edge
ms.openlocfilehash: 11974f0c66d48569ee63c592bdd3b0153db075b1
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563032"
---
# NavigationCompletedEvent 对象

一个对象，表示当[web 视图](../webview.md)已完成加载当前内容或导航失败时引发的事件。

## 属性
    
### uri

导航的统一资源标识符（URI）。

此属性为只读。

```js
var uri = NavigationCompletedEvent.uri;
```

#### 属性值
类型： **DOMString**

### isSuccess

获取一个值，该值指示导航是否已成功完成。

此属性是只读的

```js
var isSuccess = NavigationCompletedEvent.isSuccess;
```

#### 属性值
类型： **Boolean**

### webErrorStatus

如果导航失败，获取指示原因的值。

此属性是只读的

```js
var webErrorStatus = NavigationCompletedEvent.webErrorStatus;
```

#### 属性值
类型：**无符号长**
