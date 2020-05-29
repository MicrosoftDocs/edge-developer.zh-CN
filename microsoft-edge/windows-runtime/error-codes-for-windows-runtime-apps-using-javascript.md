---
title: 使用 JavaScript 的 Windows 运行时应用的错误代码
ms.custom: ''
ms.date: 04/01/2020
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.technology: windows-integration
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- JavaScript, Windows Runtime error codes
- VS.WebClient.Help.APPHOST9601
- VS.WebClient.Help.APPHOST9602
- VS.WebClient.Help.APPHOST9603
- VS.WebClient.Help.APPHOST9604
- VS.WebClient.Help.APPHOST9605
- VS.WebClient.Help.APPHOST9606
- VS.WebClient.Help.APPHOST9607
- VS.WebClient.Help.APPHOST9608
- VS.WebClient.Help.APPHOST9610
- VS.WebClient.Help.APPHOST9611
- VS.WebClient.Help.APPHOST9613
- VS.WebClient.Help.APPHOST9614
- VS.WebClient.Help.APPHOST9615
- VS.WebClient.Help.APPHOST9616
- VS.WebClient.Help.APPHOST9617
- VS.WebClient.Help.APPHOST9618
- VS.WebClient.Help.APPHOST9619
- VS.WebClient.Help.APPHOST9620
- VS.WebClient.Help.APPHOST9623
- VS.WebClient.Help.APPHOST9624
- VS.WebClient.Help.APPHOST9626
ms.assetid: 4c6d4e90-602a-4b56-ae74-3458929da442
caps.latest.revision: 1
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 7aad8577d79bc5612f526e4e2bf1ceb0f2c2929a
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564590"
---
# 使用 JavaScript 的 Windows 运行时应用的错误代码  

下面是使用 JavaScript 开发 Windows 运行时应用时 Microsoft Visual Studio 控制台显示的错误代码。  

| 错误 | 备注 |  
|:--- |:--- |  
| APPHOST9601： "无法加载*remoteURI*。  应用无法在本地上下文中加载远程 web 内容。 " | 有关 web 上下文中允许的内容的详细信息，请参阅[上下文中的功能和限制][PreviousVersionsWindowsAppsHh465373]。  |  
| APPHOST9602： "' javascript：" 是无效的属性值，将被忽略。  不要在本地上下文中使用 "javascript：" Uri。 " | 出于安全考虑，不能在本地上下文中使用 "javascript：" Uri。  有关本地上下文中允许的内容的详细信息，请参阅[上下文中的功能和限制][PreviousVersionsWindowsAppsHh465373]。  |  
| APPHOST9603： "无法加载具有类 ID *classID*的 ActiveX 插件。  应用无法加载 ActiveX 控件。 " | 使用 JavaScript 的 Windows 运行时应用不支持自定义 Microsoft ActiveXcontrols。  如果需要 UI 控件，请使用标准 web 控件、控件库或创建自己的自定义控件。  如需执行自定义逻辑，则可以创建一个自定义的 Windows 运行时对象。  有关其他 HTML、CSS 和 JavaScript 差异的信息，请参阅[HTML、css 和 javascript 功能和差异][PreviousVersionsWindowsAppsHh465380]。  |  
| APPHOST9604： "无法导航到*uri* ，因为它使用了无效的字符编码。  应用只能导航到 UTF8 编码的文件。 " | Windows 运行时访问的所有 HTML、JavaScript 和 CSS 必须编码为8位 Unicode 转换格式（UTF-8）。  有关其他 HTML、CSS 和 JavaScript 差异的信息，请参阅[HTML、css 和 javascript 功能和差异][PreviousVersionsWindowsAppsHh465380]。  |  
| APPHOST9605： "无法从*sourceURI*导航到*targetURI* ，因为目标 URI 位于更高的安全区域中。  除非你从 web 上下文 URI 导航到本地上下文 uri，并且已使用 MSApp 方法注册了本地上下文 uri，否则无法从较低安全性的区域导航到具有更高安全性的区域。 | 有关详细信息，请参阅[MSApp addPublicLocalApplicationUri][PreviousVersionsHh771917]。  |  
| APPHOST9606： "无法加载*uri* ，因为它使用 HTTP 连接，并且仅存在 ms-https-连接-meta 元素。  使用 ms-HTTPS-仅连接元元素时，仅允许 HTTPS 连接。  使用 HTTPS 连接，或者，如果不需要安全连接，请删除 meta 元素。 " | 有关详细信息，请参阅[如何要求 HTTPS 连接][PreviousVersionsWindowsAppsHh452771]。  |  
| APPHOST9607： "由于此错误，应用无法启动*uri*处的 Uri： *failureCode*。" | 缺少资源或无效文件是导致此错误的常见原因。  |  
| APPHOST9608： "由于此错误，应用无法导航到" 关于：空白 "页面： *errorCode*。" |  |  

| 错误 | 备注 |  
|:--- |:--- |  
| APPHOST9610： "应用在准备导航到自定义错误页面时发现错误： *errorCode*。" |  |  
| APPHOST9611： "由于此错误，应用无法导航到自定义错误页面： *errorCode*。" |  |  
| APPHOST9613： "由于此错误，应用无法导航到*uri* ： *errorCode*。" |  |  
| APPHOST9614： "某个 iframe 中的文档请求了*requestedDocMode* doc 模式，但系统强制使用*currentDocMode* doc 模式。  Iframe 将使用*currentDocMode* doc 模式。 " | 有关显示远程 web 内容的详细信息，请参阅[如何链接到外部][PreviousVersionsWindowsAppsHh780594]网页。  |  
| APPHOST9615： "应用无法在*uri*上下载文件，因为它是在本地上下文外以编程方式调用的。" | 在 web 上下文中的内容尝试以编程方式下载文件时发生。  |  
| APPHOST9616： "此 URI 无法使用地理位置 Api。  只能从属于程序包的 URI 或包含在清单的 ApplicationContentUris 元素中的 URI 调用地理位置 Api。 | 有关 web 上下文中允许的内容的详细信息，请参阅[上下文中的功能和限制][PreviousVersionsWindowsAppsHh465373]。  |  
| APPHOST9617： "此 URI 无法使用剪贴板 Api。  只能从属于程序包的 URI 或包含在清单的 ApplicationContentUris 元素中的 URI 调用剪贴板 Api。 | 有关 web 上下文中允许的内容的详细信息，请参阅[上下文中的功能和限制][PreviousVersionsWindowsAppsHh465373]。  |  
| APPHOST9618： "此 URI 无法使用 window。关闭。  只有使用 ms-appx URI 方案加载的打包内容才能调用 close 方法。 " | 有关 web 上下文中允许的内容的详细信息，请参阅[上下文中的功能和限制][PreviousVersionsWindowsAppsHh465373]。  |  
| APPHOST9619： "应用无法导航到*uri* ，因为 web 上下文中的页面不能是应用的顶级文档。  请改为加载 iframe 中的页面。 " | 不能将顶级页面导航到远程网页，但你的应用可以在[iframe][MDNIframe]中显示网页。  有关显示远程 web 内容的详细信息，请参阅[如何链接到外部][PreviousVersionsWindowsAppsHh780594]网页。  |  

| 错误 | 备注 |  
|:--- |:--- |  
| APPHOST9620： "此应用已关闭，因为它使用的是 HTTP 连接，而 ms-https-仅连接的 meta 元素存在。  使用 ms-HTTPS-仅连接元元素时，仅允许 HTTPS 连接。  使用 HTTPS 连接，或者，如果不需要安全连接，请删除 meta 元素。 " | 有关详细信息，请参阅[如何要求 HTTPS 连接][PreviousVersionsWindowsAppsHh452771]。  |  
| APPHOST9623： "由于此错误，应用无法解析*url* ： *errorCode*。" | 此错误的常见原因是缺少文件。  |  
| APPHOST9624： "应用无法使用脚本加载*url* url，因为该 url 会启动另一个应用。  只有直接用户交互才能启动另一个应用。 " | 应用无法直接启动其他应用。  其他应用可由用户在应用实现某些协定时启动。  有关详细信息，请参阅[应用合约和扩展][PreviousVersionsWindowsAppsHh464906]。  |  
| APPHOST9626： "已检测到对资源文件的直接引用 `ms-appx://1d33240b-0b00-40e4-a416-a4750c48787f/ja-jp\images\logo.scale-140.png` 。  此引用会导致在调试环境外使用时失败。 " | 由于文件路径的原因 `logo.scale-140.png` ，此 PNG 文件被视为本地化资源，导致不能直接引用本地化资源中的错误。  如果你打算将此文件用作语言资源，请参阅[全球化你的应用（HTML）][PreviousVersionsWindowsAppsHh465006] 。  否则，请尝试重命名有问题的目录。  |  

## 另请参阅  

[在 JavaScript 中使用 Windows 运行时][WindowsRuntimeJavascript]  

<!-- image links -->  

<!-- links -->  

[WindowsRuntimeJavascript]: /microsoft-edge/windows-runtime/using-the-windows-runtime-in-javascript "在 JavaScript 中使用 Windows 运行时"  

[UwpWindowsGeolocationGeolocatorDevicesPositionChanged]: /uwp/api/Windows.Devices.Geolocation.Geolocator#Windows_Devices_Geolocation_Geolocator_PositionChanged "Geolocator 类"  

[PreviousVersionsHh771917]: /previous-versions/hh771917(v=vs.85) "addPublicLocalApplicationUri 方法"  

[PreviousVersionsWindowsAppsHh452771]: /previous-versions/windows/apps/hh452771(v=win.10) "如何要求 HTTPS 连接（HTML）"  
[PreviousVersionsWindowsAppsHh464906]: /previous-versions/windows/apps/hh464906(v=win.10) "应用合约和扩展（Windows 运行时应用）"  
[PreviousVersionsWindowsAppsHh465006]: /previous-versions/windows/apps/hh465006(v=win.10) "全球化你的应用（HTML）"  
[PreviousVersionsWindowsAppsHh465373]: /previous-versions/windows/apps/hh465373(v=win.10) "按上下文（HTML）的功能和限制"  
[PreviousVersionsWindowsAppsHh465380]: /previous-versions/windows/apps/hh465380(v=win.10) "HTML、CSS 和 JavaScript 功能和差异（HTML）"  
[PreviousVersionsWindowsAppsHh780594]: /previous-versions/windows/apps/hh780594(v=win.10) "如何链接到外部网页（HTML）"  

[MDNIframe]: https://developer.mozilla.org/docs/Web/HTML/Element/iframe "<iframe>：嵌入式框架元素 |MDN"  
