---
description: 提供有关权限请求的信息
title: PermissionRequest 对象
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/15/2018
ms.topic: reference
ms.prod: microsoft-edge
keywords: web 视图、windows 10 应用、uwp、edge
ms.openlocfilehash: 023f19170e7b5cdb52a1de9d5d4d7c755c89edbe
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563022"
---
# PermissionRequest 对象

提供有关权限请求的信息。 此对象可从[MSWebViewPermissionRequested](../webview.md#mswebviewpermissionrequested) web 视图事件中的事件参数的 permissionRequest 属性中获取。

```js
webview.addEventListener("MSWebViewPermissionRequested", permissionRequestedEventArgs => {
    const permissionRequest = permissionRequestedEventArgs.permissionRequest;
    switch (permissionRequest.type) {
        case "geolocation":
        case "media":
        case "pointerlock":
        case "webnotifications":
        case "screen":
        case "immersiveview":
            if (permissionRequest.uri.startsWith("https://www.example.com/")) {
                // Implicitly trust particular URI
                permissionRequest.allow();
            }
            else if (permissionRequest.uri.startsWith("https://")) {
                // Defer the request so we can ask the user to allow or deny the request
                permissionRequest.defer();
                // Later we'll need to use webview.getDeferredPermissionRequestById for this
                // request and call allow or deny.
                promptUserForDeferredPermissionRequest(
                    permissionRequest.id,
                    permissionRequest.uri,
                    permissionRequest.type);
            }
            else {
                // Implicitly deny non-https URIs
                permissionRequest.deny();
            }
            break;

        case "unlimitedIndexedDBQuota":
        default:
            permissionRequest.deny();
            break;
    }
});
```

## 方法

### 帮助

允许请求权限。

#### 参数

此方法没有任何参数。

#### 返回值

此方法不返回值。

### 延迟

如果不同步允许或禁止 PermissionRequest，则需要时间与用户交互或执行其他异步操作，请在 PermissionRequest 上调用 defer （）。 PermissionRequest 现在将以 DeferredPermissionRequest 的形式提供给 getDeferredPermissionRequests 和 getDeferredPermissionRequestById。 你可以通过 "匹配 id" 属性将当前 PermissionRequest 关联到相应的 DeferredPermissionRequest。

#### 参数

此方法没有任何参数。

#### 返回值

此方法不返回值。

### 拒绝

拒绝请求权限。

#### 参数

此方法没有任何参数。

#### 返回值

此方法不返回值。

## 属性

### id

可用于将当前 PermissionRequest 与相应的 DeferredPermissionRequest 关联的唯一 ID （如果使用 defer 方法）。 请参阅 defer 方法。

此属性为只读。

##### 属性值

类型：**无符号长**

### 状态

返回 "unknown"、"defer"、"allow" 或 "deny" 以指示权限请求的当前状态。 如果没有调用任何方法，则状态字符串将对应于 "姓氏"、"拒绝" 或 "推迟" 调用的任何方法。

此属性为只读。

#### 属性值

类型： **String**

### 类型

所请求的权限类型。 这可以是以下字符串值之一：

- **地理位置**：通过 "navigator" 作为地理位置访问位置数据。
- **unlimitedIndexedDBQuota**：允许 IndexedDB api 忽略常用的存储数据大小限制。
- **媒体**：通过 getUserMedia 访问麦克风和相机。
- **pointerlock**：能够通过 requestPointerLock 元素锁定和控制鼠标指针。
- **webnotifications**：通过窗口显示桌面通知的功能。通告.
- **屏幕**：能够通过媒体捕获 API 拍摄屏幕截图。
- **immersiveview**：能够控制 VR 显示。

此属性为只读。

#### 属性值

类型： **String**

### uri

请求权限的文档的统一资源标识符（URI）。

此属性为只读。

#### 属性值

类型： **String**
