---
description: 表示 web 视图进程。
title: MSWebViewProcess 对象
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/15/2020
ms.topic: reference
ms.prod: microsoft-edge
keywords: web 视图、windows 10 应用、uwp、edge
ms.openlocfilehash: 7581f6da3a23295180c50f6d41cc282ce998b64e
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563035"
---
# MSWebViewProcess 对象

表示[web 视图](../webview.md)进程。

```js
var wvprocess = new MSWebViewProcess();
```

## 属性

### enterpriseId

流程的企业 ID。

```js
var enterpriseId = wvprocess.enterpriseId;
```

此属性为只读。

#### 属性值
类型： **DOMString**

### isPrivateNetworkClientServerCapabilityEnabled

获取一个值，该值指示[web 视图](../webview.md)进程是否具有在应用部件清单中启用的*专用网络（客户端 & 服务器）* 通用 Windows[应用功能声明](/windows/uwp/packaging/app-capability-declarations)。

```js
var privateNetwork = wvprocess.isPrivateNetworkClientServerCapabilityEnabled;
```

此属性为只读。

#### 属性值
类型： **Boolean**

## 方法

### CreateWebViewAsync

在特定进程中创建[web 视图](../webview.md)。

```js
wvprocess.createWebviewAsync();
```

#### 返回值

处理器类型**`Promise<MSHTMLWebViewElement>`**

### GetWebViews

返回进程中托管的**MSWebViewProcess**对象序列。

#### 返回值

处理器类型**`sequence<MSHTMLWebViewElement>`**

### Terminate

终止进程。

```js
wvprocess.terminate();
```

#### 返回值

此方法不返回值。
