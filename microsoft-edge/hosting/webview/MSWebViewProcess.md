---
description: 表示 web 视图进程。
title: MSWebViewProcess 对象
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/10/2020
ms.topic: reference
ms.prod: microsoft-edge
keywords: web 视图、windows 10 应用、uwp、edge
ms.openlocfilehash: bb70b0e8eb12c7a7c23d71f01ea24e9084caa156
ms.sourcegitcommit: 037a2d62333691104c9accb4862968f80a3465a2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/18/2020
ms.locfileid: "10752153"
---
# MSWebViewProcess 对象  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

表示[web 视图](../webview.md)进程。  

```javascript
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

```javascript
var privateNetwork = wvprocess.isPrivateNetworkClientServerCapabilityEnabled;
```  

此属性为只读。  

#### 属性值  

类型： **Boolean**  

## 方法  

### CreateWebViewAsync  

在特定进程中创建[web 视图](../webview.md)。  

```javascript
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

```javascript
wvprocess.terminate();
```  

#### 返回值  

此方法不返回值。  
