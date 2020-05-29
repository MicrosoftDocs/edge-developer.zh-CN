---
description: 来自包含导航原因和位置的 focus 事件的已调度对象
title: FocusNavigationEvent 对象
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2018
ms.topic: reference
ms.prod: microsoft-edge
keywords: web 视图、windows 10 应用、uwp、edge
ms.openlocfilehash: b988bcd7ff252b9972bef9a31339a34b4b58d9ee
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563043"
---
# FocusNavigationEvent 对象

[**NavigateFocus**](../webview.md#navigatefocus) / [**DepartingFocus**](../webview.md#departingfocus)中包含[**NavigationReason**](#navigationreason)和 location 的已调度对象。 

## 方法

### requestFocus

调用以将焦点从应用移动到 web 视图。

### 参数

此方法没有参数。

### 返回值

此方法不返回值。

## 属性
    
### navigationReason

枚举类型**NavigationReason**，"左"、"上"、"右" 或 "向下"。 

此属性为只读。

```js
var navigationReason = FocusNavigationEvent.navigationReason;
```

#### 属性值
类型： **NavigationReason**

### originHeight

要获得焦点的元素的原始高度位置。

此属性为只读。

```js
var originWoriginHeightidth = FocusNavigationEvent.originHeight;
```

#### 属性值
类型： **float**

### originLeft

要获得焦点的元素的原点左侧位置。

此属性为只读。

```js
var originLeft = FocusNavigationEvent.originLeft;
```

#### 属性值
类型： **float**

### originTop

要获得焦点的元素的原点顶部位置。

此属性为只读。

```js
var originTop = FocusNavigationEvent.originTop;
```

#### 属性值
类型： **float**

### originWidth

要获得焦点的元素的原始宽度位置。

此属性为只读。

```js
var originWidth = FocusNavigationEvent.originWidth;
```

#### 属性值
类型： **float**

