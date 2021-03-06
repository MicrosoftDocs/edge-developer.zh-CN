---
description: 在 JavaScript 中处理 Windows 运行时事件
title: 在 JavaScript 中处理 Windows 运行时事件
ms.custom: ''
ms.date: 11/03/2020
ms.prod: microsoft-edge
ms.technology: windows-integration
ms.topic: article
helpviewer_keywords:
- JavaScript, Windows Runtime events
- Windows Runtime events [JavaScript]
ms.assetid: d9436aff-2c30-4846-b8df-eaa3e63fd75c
caps.latest.revision: 6
author: MSEdgeTeam
ms.author: msedgedevrel
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 08562f7ebff0c02b96bfc8229238a62463b95451
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11397522"
---
# <a name="handling-windows-runtime-events-in-javascript"></a>在 JavaScript 中处理 Windows 运行时事件  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

Windows 运行时事件在 JavaScript 中的表示方式与在 C++ 或 windows 运行时.NET Framework。  它们不是类属性，而是表示为传递给类和方法的 \ (小写\) 字符串 `addEventListener` `removeEventListener` 标识符。  例如，可以通过将字符串传递给方法来为 [Geolocator.PositionChanged][UwpWindowsGeolocationGeolocatorDevicesPositionChanged] 事件添加 `positionchanged` 事件 `Geolocator.addEventListener` 处理程序：  

```javascript  
var locator = new Windows.Devices.Geolocation.Geolocator();
locator.addEventListener(
    "positionchanged",
    function (ev) {
        console.log("Got event");
    });
```  

还可以设置 `locator.onpositionchanged` 属性：  

```javascript
locator.onpositionchanged =
    function (ev) {
        console.log("Got event");
    };
```  

.NET/C++ 和 JavaScript 之间的另一个区别是事件处理程序使用的参数数。  在 .NET/C++ 中，处理程序采用两个：事件发件人和事件数据。  在 JavaScript 中，两者捆绑为单个 `Event` 对象。  在下面的示例中，参数包含事件 \ (property\) 的发送方和此处的事件数据属性 `ev` `target` \ (\) 。 `position`  事件数据属性是记录每个事件的属性。  

```javascript
function (ev) {
    console.log("Sender: " + ev.target);
    console.log("Position: " +
        ev.position.latitude + "," +
        ev.position.longitude);
};
```  

> [!IMPORTANT]
> Windows 运行时功能不适用于在 Internet Explorer 中运行的应用。  

## <a name="see-also"></a>另请参阅  

[在 JavaScript 中使用 Windows 运行时][WindowsRuntimeJavascript]  

 <!-- links -->  

[WindowsRuntimeJavascript]: ./using-the-windows-runtime-in-javascript.md "在 JavaScript |Microsoft Docs"  

[UwpWindowsGeolocationGeolocatorDevicesPositionChanged]: /uwp/api/Windows.Devices.Geolocation.Geolocator#Windows_Devices_Geolocation_Geolocator_PositionChanged "Geolocator 类|Microsoft Docs"  
