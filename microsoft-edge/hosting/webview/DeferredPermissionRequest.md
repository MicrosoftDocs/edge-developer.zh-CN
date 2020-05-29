---
description: 表示对访问设备功能的用户权限的延迟请求
title: DeferredPermissionRequest 对象
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/15/2018
ms.topic: reference
ms.prod: microsoft-edge
keywords: web 视图、windows 10 应用、uwp、edge
ms.openlocfilehash: 6013f20195fc0f5d4f33b871a9c1b01392bf023e
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563045"
---
# DeferredPermissionRequest 对象

表示由[web 视图](../webview.md)内容的延迟请求，用于最终用户访问专用设备功能（如地理位置或指针锁定）。

```js
// In this sample, when we receive a permission request we construct some basic UI to ask the
// user if they want to give permission.
webview.addEventListener("MSWebViewPermissionRequested", permissionRequestedEventArgs => {
    const permissionRequest = permissionRequestedEventArgs.permissionRequest;
    const requestContainer = document.createElement("div");

    // We use this function as the handler for the allow and deny buttons.
    function completeDeferredPermissionRequest(allow) {
        // Find the DeferredPermissionRequest using the id of the PermissionRequest we deferred.
        const deferredPermissionRequest = webview.getDeferredPermissionRequestById(permissionRequest.id);
        if (allow) {
            deferredPermissionRequest.allow();
        }
        else {
            deferredPermissionRequest.deny();
        }
        requestContainer.parentElement.removeChild(requestContainer);
    }

    // Construct some simple UI to tell the user about the permission request and get their
    // feedback via the allow and deny buttons
    const description = document.createElement("span");
    description.textContent = "Allow " + uri + " to access " + type + "?";

    const allow = document.createElement("button");
    allow.textContent = "Allow";
    allow.addEventListener("click", () => completeDeferredPermissionRequest(true));

    const deny = document.createElement("button");
    deny.textContent = "Deny";
    deny.addEventListener("click", () => completeDeferredPermissionRequest(false));

    requestContainer.appendChild(description);
    requestContainer.appendChild(allow);
    requestContainer.appendChild(deny);
    document.body.appendChild(requestContainer);

    permissionRequest.defer();
});
```

## 方法

### 帮助

允许请求权限。

```js
deferredPermissionRequest.allow();
```

#### 参数

此方法没有任何参数。

#### 返回值

此方法不返回值。

### 拒绝

拒绝请求权限。

```js
deferredPermissionRequest.deny();
```

#### 参数

此方法没有任何参数。

#### 返回值

此方法不返回值。

## 属性

### id

可用于将当前 DeferredPermissionRequest 与 PermissionRequest 对象的唯一 ID 与上一个 MSWebViewPermissionRequested 事件关联。 请参阅**webview.permissionrequested**方法。

此属性为只读。

```js
var id = deferredPermissionRequest.id;
```

##### 属性值

类型：**无符号长**

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

```js
var type = deferredPermissionRequest.type;
```

#### 属性值

类型： **String**

### uri

请求权限的文档的统一资源标识符（URI）。

此属性为只读。

```js
var uri = deferredPermissionRequest.uri;
```

##### 属性值

类型： **String**

## 要求

|                                           |                                      |
|-------------------------------------------|--------------------------------------|
| <strong>最低受支持的客户端</strong> | Windows 10 [仅限 Windows 应用商店应用] |
| <strong>最低受支持的服务器</strong> |            不支持             |
| <strong>最低受支持的电话</strong>  |            不支持             |
