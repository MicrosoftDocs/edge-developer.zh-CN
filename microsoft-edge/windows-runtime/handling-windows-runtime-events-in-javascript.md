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

Windows 运行时事件在 JavaScript 中以相同的方式表示，与在 C++ 或 .NET Framework 中相同。  它们不是类属性，而是表示为传递到类和方法的 \ (小写\) `addEventListener` `removeEventListener` 字符串标识符。  例如，你可以通过将字符串传递给方法 [来为 Geolocator.PositionChanged][UwpWindowsGeolocationGeolocatorDevicesPositionChanged] 事件 `positionchanged` 添加事件 `Geolocator.addEventListener` 处理程序：  

```javascript  
var locator = new Windows.Devices.Geolocation.Geolocator();
locator.addEventListener(
    "positionchanged",
    function (ev) {
        console.log("Got event");
    });
```  

还可以设置该 `locator.onpositionchanged` 属性：  

```javascript
locator.onpositionchanged =
    function (ev) {
        console.log("Got event");
    };
```  

.NET/C++ 和 JavaScript 之间的另一种差别是事件处理程序所采用的参数数。  在 .NET/C++ 中，处理程序有两个：事件发送方以及事件数据。  在 JavaScript 中，这两个对象作为单个对象绑 `Event` 定。  在以下示例中， `ev` 此参数既包含事件 \ (`target` the property\) 和事件数据属性 \ (这里的事件数据属性 \ (here，只 `position` 包含 \) 即可。  事件数据属性是针对每个事件记录的属性。  

```javascript
function (ev) {
    console.log("Sender: " + ev.target);
    console.log("Position: " +
        ev.position.latitude + "," +
        ev.position.longitude);
};
```  

> [!IMPORTANT]
> Windows 运行时功能不适用于在运行时运行Internet Explorer。  

## 另请参阅  

[在 JavaScript 中使用 Windows 运行时][WindowsRuntimeJavascript]  

 <!-- links -->  

[WindowsRuntimeJavascript]: ./using-the-windows-runtime-in-javascript.md "在 JavaScript 中使用 Windows 运行时 |Microsoft 文档"  

[UwpWindowsGeolocationGeolocatorDevicesPositionChanged]: /uwp/api/Windows.Devices.Geolocation.Geolocator#Windows_Devices_Geolocation_Geolocator_PositionChanged "Geolocator Class |Microsoft 文档"  
