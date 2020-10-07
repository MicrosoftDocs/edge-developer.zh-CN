---
title: Handling Windows Runtime Events in JavaScript
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
# <span data-ttu-id="9a9bc-102">Handling Windows Runtime events in JavaScript</span><span class="sxs-lookup"><span data-stu-id="9a9bc-102">Handling Windows Runtime events in JavaScript</span></span>  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

<span data-ttu-id="9a9bc-103">Windows Runtime events are not represented in the same way in JavaScript as they are in C++ or the .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9a9bc-103">Windows Runtime events are not represented in the same way in JavaScript as they are in C++ or the .NET Framework.</span></span>  <span data-ttu-id="9a9bc-104">They are not class properties, but rather are represented as \(lowercase\) string identifiers that are passed to the class's `addEventListener` and `removeEventListener` methods.</span><span class="sxs-lookup"><span data-stu-id="9a9bc-104">They are not class properties, but rather are represented as \(lowercase\) string identifiers that are passed to the class's `addEventListener` and `removeEventListener` methods.</span></span>  <span data-ttu-id="9a9bc-105">For example, you can add an event handler for the [Geolocator.PositionChanged][UwpWindowsGeolocationGeolocatorDevicesPositionChanged] event by passing the string `positionchanged` to the `Geolocator.addEventListener` method:</span><span class="sxs-lookup"><span data-stu-id="9a9bc-105">For example, you can add an event handler for the [Geolocator.PositionChanged][UwpWindowsGeolocationGeolocatorDevicesPositionChanged] event by passing the string `positionchanged` to the `Geolocator.addEventListener` method:</span></span>  

```javascript  
var locator = new Windows.Devices.Geolocation.Geolocator();
locator.addEventListener(
    "positionchanged",
    function (ev) {
        console.log("Got event");
    });
```  

<span data-ttu-id="9a9bc-106">You can also set the `locator.onpositionchanged` property:</span><span class="sxs-lookup"><span data-stu-id="9a9bc-106">You can also set the `locator.onpositionchanged` property:</span></span>  

```javascript
locator.onpositionchanged =
    function (ev) {
        console.log("Got event");
    };
```  

<span data-ttu-id="9a9bc-107">Another difference between .NET/C++ and JavaScript is the number of parameters taken by an event handler.</span><span class="sxs-lookup"><span data-stu-id="9a9bc-107">Another difference between .NET/C++ and JavaScript is the number of parameters taken by an event handler.</span></span>  <span data-ttu-id="9a9bc-108">In .NET/C++, a handler takes two:  the event sender, and the event data.</span><span class="sxs-lookup"><span data-stu-id="9a9bc-108">In .NET/C++, a handler takes two:  the event sender, and the event data.</span></span>  <span data-ttu-id="9a9bc-109">In JavaScript, the two are bundled as a single `Event` object.</span><span class="sxs-lookup"><span data-stu-id="9a9bc-109">In JavaScript, the two are bundled as a single `Event` object.</span></span>  <span data-ttu-id="9a9bc-110">In the following example, the `ev` parameter contains both the sender of the event \(the `target` property\) and the event data properties \(here, just `position`\).</span><span class="sxs-lookup"><span data-stu-id="9a9bc-110">In the following example, the `ev` parameter contains both the sender of the event \(the `target` property\) and the event data properties \(here, just `position`\).</span></span>  <span data-ttu-id="9a9bc-111">The event data properties are the ones that are documented for each event.</span><span class="sxs-lookup"><span data-stu-id="9a9bc-111">The event data properties are the ones that are documented for each event.</span></span>  

```javascript
function (ev) {
    console.log("Sender: " + ev.target);
    console.log("Position: " +
        ev.position.latitude + "," +
        ev.position.longitude);
};
```  

> [!IMPORTANT]
> <span data-ttu-id="9a9bc-112">Windows Runtime features are not available for apps that run in Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="9a9bc-112">Windows Runtime features are not available for apps that run in Internet Explorer.</span></span>  

## <span data-ttu-id="9a9bc-113">See also</span><span class="sxs-lookup"><span data-stu-id="9a9bc-113">See also</span></span>  

[<span data-ttu-id="9a9bc-114">Using the Windows Runtime in JavaScript</span><span class="sxs-lookup"><span data-stu-id="9a9bc-114">Using the Windows Runtime in JavaScript</span></span>][WindowsRuntimeJavascript]  

 <!-- links -->  

[WindowsRuntimeJavascript]: ./using-the-windows-runtime-in-javascript.md "Using the Windows Runtime in JavaScript | Microsoft Docs"  

[UwpWindowsGeolocationGeolocatorDevicesPositionChanged]: /uwp/api/Windows.Devices.Geolocation.Geolocator#Windows_Devices_Geolocation_Geolocator_PositionChanged "Geolocator Class | Microsoft Docs"  
