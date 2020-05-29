---
description: 公开操作是否已成功完成或失败
title: MSWebViewAsyncOperation 对象
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2018
ms.topic: reference
ms.prod: microsoft-edge
keywords: web 视图、windows 10 应用、uwp、edge
ms.openlocfilehash: ebb89c0fc645ebcd97357af10af2be650d8218b9
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563036"
---
# MSWebViewAsyncOperation 对象

公开操作是否已成功完成或失败。 

## 事件

### 完成

指示操作已完成。 

```js
function handler(eventInfo) { /* Your code */ }
 
// addEventListener syntax
MSWebViewAsyncOperation.addEventListener("complete", handler);
MSWebViewAsyncOperation.removeEventListener("complete", handler);
```

#### 事件信息

|            |      |
|------------|------|
|**接口** | **事件**
|**同步** |是 |    
|**气泡**     |否 |   
|**可取消**  |否 |        


### 错误

指示操作出现错误。

```js
function handler(eventInfo) { /* Your code */ }
 
// addEventListener syntax
MSWebViewAsyncOperation.addEventListener("error", handler);
MSWebViewAsyncOperation.removeEventListener("error", handler);
```

#### 事件信息

|            |      |
|------------|------|
|**接口** | **事件**
|**同步** |是 |    
|**气泡**     |否 |   
|**可取消**  |否 |            


## 方法

### start

调用以启动异步任务。 

```js
MSWebViewAsyncOperation.start();
```

### 参数

此方法没有参数。

### 返回值

此方法不返回值。

## 属性

### 错误

出现的错误。

此属性为只读。

```js
var error = MSWebViewAsyncOperation.error;
```

#### 属性值
类型： **DOMError**

### oncomplete

**完整**的事件处理程序。 

```js
var oncomplete = MSWebViewAsyncOperation.oncomplete;
```

#### 属性值
类型： **EventHandler**

### onerror

**错误**事件处理程序。 

```js
var onerror = MSWebViewAsyncOperation.onerror;
```

#### 属性值
类型： **EventHandler**

### readyState

描述对象的准备状态。

此属性为只读。

```js
var readyState = MSWebViewAsyncOperation.readyState;
```

#### 属性值
类型：**无符号的短**

### 结果

操作的结果。

此属性为只读。

```js
var result = MSWebViewAsyncOperation.result;
```

#### 属性值
类型：任何

### target

操作的目标。 

此属性为只读。

```js
var target = MSWebViewAsyncOperation.target;
```

#### 属性值
类型： [ **MSHTMLWebViewElement**](../webview.md)

### 类型

操作的类型。

此属性为只读。

```js
var type = MSWebViewAsyncOperation.type;
```

#### 属性值
类型：**无符号的短**
