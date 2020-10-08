---
title: 在 JavaScript 中处理 Windows 运行时事件
ms.custom: ''
ms.date: 07/29/2020
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.technology: windows-integration
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- JavaScript, Windows Runtime events
- Windows Runtime events [JavaScript]
ms.assetid: d9436aff-2c30-4846-b8df-eaa3e63fd75c
caps.latest.revision: 6
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: fe44457206569c1e32c40514b4b186bec50d1e3c
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "10942157"
---
# 在 JavaScript 中处理 Windows 运行时事件  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

Windows 运行时事件在 JavaScript 中和在 c + + 或 .NET Framework 中的表现方式不同。  它们不是类属性，而是表示为传递到类和方法的 \ (小写 ) 字符串标识符 `addEventListener` `removeEventListener` 。  例如，你可以通过将字符串传递给该方法来添加 [Geolocator][UwpWindowsGeolocationGeolocatorDevicesPositionChanged] 事件的事件处理程序 `positionchanged` `Geolocator.addEventListener` ：  

```javascript  
var locator = new Windows.Devices.Geolocation.Geolocator();
locator.addEventListener(
    "positionchanged",
    function (ev) {
        console.log("Got event");
    });
```  

您也可以设置 `locator.onpositionchanged` 属性：  

```javascript
locator.onpositionchanged =
    function (ev) {
        console.log("Got event");
    };
```  

.NET/c + + 和 JavaScript 之间的另一个区别是事件处理程序所执行的参数数目。  在 .NET/c + + 中，处理程序使用两个：事件发送程序和事件数据。  在 JavaScript 中，这两个对象被捆绑为单个 `Event` 对象。  在以下示例中，该 `ev` 参数既包含事件 \ (的发送方的 `target` 属性 \ ) 和事件数据属性 \ (此处，而不是 `position` ) 。  事件数据属性是针对每个事件记录的属性。  

```javascript
function (ev) {
    console.log("Sender: " + ev.target);
    console.log("Position: " +
        ev.position.latitude + "," +
        ev.position.longitude);
};
```  

> [!IMPORTANT]
> 对于在 Internet Explorer 中运行的应用，Windows 运行时功能不可用。  

## 另请参阅  

[在 JavaScript 中使用 Windows 运行时][WindowsRuntimeJavascript]  

 <!-- links -->  

[WindowsRuntimeJavascript]: ./using-the-windows-runtime-in-javascript.md "在 JavaScript | 中使用 Windows 运行时Microsoft 文档"  

[UwpWindowsGeolocationGeolocatorDevicesPositionChanged]: /uwp/api/Windows.Devices.Geolocation.Geolocator#Windows_Devices_Geolocation_Geolocator_PositionChanged "Geolocator 类 |Microsoft 文档"  
