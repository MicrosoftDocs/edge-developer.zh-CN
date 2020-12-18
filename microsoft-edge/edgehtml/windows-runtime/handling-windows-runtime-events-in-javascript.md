---
description: 在 JavaScript 中处理 Windows 运行时事件。
title: 在 JavaScript 中处理 Windows 运行时事件
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
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: e0a3e35c908c766c0308903381b271f5ccdb27a3
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232564"
---
# <span data-ttu-id="9b12c-103">在 JavaScript 中处理 Windows 运行时事件</span><span class="sxs-lookup"><span data-stu-id="9b12c-103">Handling Windows Runtime events in JavaScript</span></span>  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

<span data-ttu-id="9b12c-104">Windows 运行时事件在 JavaScript 中的表示方式与在 C++ 或 .NET Framework 中不同。</span><span class="sxs-lookup"><span data-stu-id="9b12c-104">Windows Runtime events are not represented in the same way in JavaScript as they are in C++ or the .NET Framework.</span></span>  <span data-ttu-id="9b12c-105">它们不是类属性，而是表示为 \ (小写\) 传递给类和方法的字符串 `addEventListener` `removeEventListener` 标识符。</span><span class="sxs-lookup"><span data-stu-id="9b12c-105">They are not class properties, but rather are represented as \(lowercase\) string identifiers that are passed to the class's `addEventListener` and `removeEventListener` methods.</span></span>  <span data-ttu-id="9b12c-106">例如，可以通过将字符串传递给方法为 [Geolocator.PositionChanged][UwpWindowsGeolocationGeolocatorDevicesPositionChanged] 事件添加 `positionchanged` 事件 `Geolocator.addEventListener` 处理程序：</span><span class="sxs-lookup"><span data-stu-id="9b12c-106">For example, you can add an event handler for the [Geolocator.PositionChanged][UwpWindowsGeolocationGeolocatorDevicesPositionChanged] event by passing the string `positionchanged` to the `Geolocator.addEventListener` method:</span></span>  

```javascript  
var locator = new Windows.Devices.Geolocation.Geolocator();
locator.addEventListener(
    "positionchanged",
    function (ev) {
        console.log("Got event");
    });
```  

<span data-ttu-id="9b12c-107">您还可以设置 `locator.onpositionchanged` 属性：</span><span class="sxs-lookup"><span data-stu-id="9b12c-107">You can also set the `locator.onpositionchanged` property:</span></span>  

```javascript
locator.onpositionchanged =
    function (ev) {
        console.log("Got event");
    };
```  

<span data-ttu-id="9b12c-108">.NET/C++ 和 JavaScript 之间的另一个区别是事件处理程序使用的参数数。</span><span class="sxs-lookup"><span data-stu-id="9b12c-108">Another difference between .NET/C++ and JavaScript is the number of parameters taken by an event handler.</span></span>  <span data-ttu-id="9b12c-109">在 .NET/C++ 中，处理程序采用两个：事件发送方和事件数据。</span><span class="sxs-lookup"><span data-stu-id="9b12c-109">In .NET/C++, a handler takes two:  the event sender, and the event data.</span></span>  <span data-ttu-id="9b12c-110">在 JavaScript 中，两者捆绑为单个 `Event` 对象。</span><span class="sxs-lookup"><span data-stu-id="9b12c-110">In JavaScript, the two are bundled as a single `Event` object.</span></span>  <span data-ttu-id="9b12c-111">在下面的示例中，参数包含事件 \ (property\) 的发送方和此处的事件数据属性 `ev` `target` \ (\) 。 `position`</span><span class="sxs-lookup"><span data-stu-id="9b12c-111">In the following example, the `ev` parameter contains both the sender of the event \(the `target` property\) and the event data properties \(here, just `position`\).</span></span>  <span data-ttu-id="9b12c-112">事件数据属性是记录每个事件的属性。</span><span class="sxs-lookup"><span data-stu-id="9b12c-112">The event data properties are the ones that are documented for each event.</span></span>  

```javascript
function (ev) {
    console.log("Sender: " + ev.target);
    console.log("Position: " +
        ev.position.latitude + "," +
        ev.position.longitude);
};
```  

> [!IMPORTANT]
> <span data-ttu-id="9b12c-113">Windows 运行时功能不适用于在 Internet Explorer 中运行的应用。</span><span class="sxs-lookup"><span data-stu-id="9b12c-113">Windows Runtime features are not available for apps that run in Internet Explorer.</span></span>  

## <span data-ttu-id="9b12c-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9b12c-114">See also</span></span>  

[<span data-ttu-id="9b12c-115">在 JavaScript 中使用 Windows 运行时</span><span class="sxs-lookup"><span data-stu-id="9b12c-115">Using the Windows Runtime in JavaScript</span></span>][WindowsRuntimeJavascript]  

 <!-- links -->  

[WindowsRuntimeJavascript]: ./using-the-windows-runtime-in-javascript.md "在 JavaScript 中使用 Windows 运行时 |Microsoft Docs"  

[UwpWindowsGeolocationGeolocatorDevicesPositionChanged]: /uwp/api/Windows.Devices.Geolocation.Geolocator#Windows_Devices_Geolocation_Geolocator_PositionChanged "Geolocator 类 |Microsoft Docs"  
