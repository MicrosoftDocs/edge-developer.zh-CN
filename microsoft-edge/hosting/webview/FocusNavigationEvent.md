---
description: 来自包含导航原因和位置的 focus 事件的已调度对象
title: FocusNavigationEvent 对象
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/10/2020
ms.topic: reference
ms.prod: microsoft-edge
keywords: web 视图、windows 10 应用、uwp、edge
ms.openlocfilehash: 88f0a4ef8834c6e851f81ee10bf4202a0429f969
ms.sourcegitcommit: 037a2d62333691104c9accb4862968f80a3465a2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/18/2020
ms.locfileid: "10752162"
---
# FocusNavigationEvent 对象  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

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

```javascript
var navigationReason = FocusNavigationEvent.navigationReason;
```  

#### 属性值  

类型： **NavigationReason**  

### originHeight  

要获得焦点的元素的原始高度位置。  

此属性为只读。  

```javascript
var originWoriginHeightidth = FocusNavigationEvent.originHeight;
```  

#### 属性值  

类型： **float**  

### originLeft  

要获得焦点的元素的原点左侧位置。  

此属性为只读。  

```javascript
var originLeft = FocusNavigationEvent.originLeft;
```  

#### 属性值  

类型： **float**  

### originTop  

要获得焦点的元素的原点顶部位置。  

此属性为只读。  

```javascript
var originTop = FocusNavigationEvent.originTop;
```  

#### 属性值  

类型： **float**  

### originWidth  

要获得焦点的元素的原始宽度位置。  

此属性为只读。  

```javascript
var originWidth = FocusNavigationEvent.originWidth;
```  

#### 属性值  

类型： **float**  
