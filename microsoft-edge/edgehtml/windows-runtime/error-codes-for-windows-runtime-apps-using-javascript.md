---
description: 使用 JavaScript 的 Windows 运行时应用的错误代码。
title: 使用 JavaScript 的 Windows 运行时应用的错误代码
ms.prod: microsoft-edge
ms.technology: windows-integration
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
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 5a04a9c348a29aee2ec5936e7d923377dd53b21c
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232746"
---
# 使用 JavaScript 的 Windows 运行时应用的错误代码  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

下面是使用 JavaScript 开发 Windows 运行时应用时 Microsoft Visual Studio 控制台显示的错误代码。  

| 错误 | 备注 |  
|:--- |:--- |  
| APPHOST9601：" 无法加载 *remoteURI*。  应用无法在本地上下文中加载远程 Web 内容。" | 有关 Web 上下文中允许的内容详细信息，请参阅功能和 [按上下文的限制][PreviousVersionsWindowsAppsHh465373]。  |  
| APPHOST9602："'javascript：'是无效的属性值，将被忽略。  请勿在本地上下文中使用"javascript："URI。" | 出于安全考虑，不能在本地上下文中使用"javascript："URI。  有关本地上下文中允许使用的功能和限制，请参阅上下文 [的功能和限制][PreviousVersionsWindowsAppsHh465373]。  |  
| APPHOST9603：" 无法加载ActiveX ID 为 *classID*的插件。  应用无法加载ActiveX控件。" | 使用 JavaScript 的 Windows 运行时应用不支持自定义 Microsoft ActiveXcontrols。  如果需要 UI 控件，请使用标准 Web 控件、控件库或创建自己的自定义控件。  如需执行自定义逻辑，则可以创建一个自定义的 Windows 运行时对象。  有关其他 HTML、CSS 和 JavaScript 差异的信息，请参阅 [HTML、CSS 和 JavaScript 的功能和差异][PreviousVersionsWindowsAppsHh465380]。  |  
| APPHOST9604："无法导航到 *uri，* 因为它使用无效的字符编码。  应用只能导航到 UTF8 编码的文件。" | Windows 运行时访问的所有 HTML、JavaScript 和 CSS 必须编码为 UTF-8 (8 位 Unicode 转换) 。  有关其他 HTML、CSS 和 JavaScript 差异的信息，请参阅 [HTML、CSS 和 JavaScript 的功能和差异][PreviousVersionsWindowsAppsHh465380]。  |  
| APPHOST9605："无法从 *sourceURI* 导航到 *targetURI，* 因为目标 URI 位于更高的安全区域中。  除非从 Web 上下文 URI 导航到本地上下文 URI，并且已使用 MSApp.addPublicLocalApplicationUri 方法注册了本地上下文 URI，否则无法从安全性较低的区域导航到安全性较高的区域。" | 有关详细信息，请参阅 [MSApp.addPublicLocalApplicationUri][PreviousVersionsHh771917]。  |  
| APPHOST9606："无法加载 *uri，* 因为它使用 HTTP 连接，并且存在仅 ms-https-connections 元元素。  使用 ms-https-connections-only 元元素时，仅允许 HTTPS 连接。  使用 HTTPS 连接，或者，如果不需要安全连接，请删除元元素。" | 有关详细信息，请参阅 [如何要求 HTTPS 连接][PreviousVersionsWindowsAppsHh452771]。  |  
| APPHOST9607："由于此错误，应用无法从*uri*启动 URI：failureCode **。" | 资源缺失或文件无效是导致此错误的常见原因。  |  
| APPHOST9608："由于此错误，应用无法导航到 about：blank 页面 *：errorCode*。" |  |  

| 错误 | 备注 |  
|:--- |:--- |  
| APPHOST9610："应用在准备导航到自定义错误页面时发现错误 *：errorCode*。" |  |  
| APPHOST9611："由于此错误，应用无法导航到自定义错误页面 *：errorCode*。" |  |  
| APPHOST9613："由于此错误，应用无法导航到*uri：errorCode* 。" ** |  |  
| APPHOST9614："iframe 中的文档请求请求的 *DocMode* 文档模式，但系统强制执行 *currentDocMode* 文档模式。  iframe 将使用 *currentDocMode* 文档模式。" | 有关显示远程 Web 内容的信息，请参阅如何 [链接到外部网页][PreviousVersionsWindowsAppsHh780594]。  |  
| APPHOST9615："应用无法从 *uri* 下载文件，因为它在本地上下文之外以编程方式调用。" | 当 Web 上下文中的内容尝试以编程方式下载文件时发生。  |  
| APPHOST9616："此 URI 无法使用地理位置 API。  只能从属于程序包的 URI 或包含在清单的 ApplicationContentUris 元素中的 URI 调用地理位置 API。" | 有关 Web 上下文中允许的内容详细信息，请参阅功能和 [按上下文的限制][PreviousVersionsWindowsAppsHh465373]。  |  
| APPHOST9617："此 URI 无法使用剪贴板 API。  剪贴板 API 只能从程序包的一部分或包含在清单的 ApplicationContentUris 元素中的 URI 调用。" | 有关 Web 上下文中允许的内容详细信息，请参阅功能和 [按上下文的限制][PreviousVersionsWindowsAppsHh465373]。  |  
| APPHOST9618："此 URI 不能使用 window.close。  window.close 方法只能从使用 ms-appx URI 方案加载的打包内容中调用。" | 有关 Web 上下文中允许的内容详细信息，请参阅功能和 [按上下文的限制][PreviousVersionsWindowsAppsHh465373]。  |  
| APPHOST9619："应用无法导航到 *uri，* 因为 Web 上下文中的页面不能是应用的顶级文档。  改为在 iframe 中加载页面。" | 无法将顶级页面导航到远程网页，但您的应用程序可以在 [iframe][MDNIframe]中显示网页。  有关显示远程 Web 内容的信息，请参阅如何 [链接到外部网页][PreviousVersionsWindowsAppsHh780594]。  |  

| 错误 | 备注 |  
|:--- |:--- |  
| APPHOST9620："此应用程序已关闭，因为它使用了 HTTP 连接，并且存在仅 ms-https-connections 元元素。  使用 ms-https-connections-only 元元素时，仅允许 HTTPS 连接。  使用 HTTPS 连接，或者，如果不需要安全连接，请删除元元素。" | 有关详细信息，请参阅 [如何要求 HTTPS 连接][PreviousVersionsWindowsAppsHh452771]。  |  
| APPHOST9623："由于此错误，应用无法解析***URL：errorCode*。" | 导致此错误的常见原因是缺少文件。  |  
| APPHOST9624："应用无法使用脚本加载 *url* url，因为 URL 会启动另一个应用。  只有直接的用户交互才能启动另一个应用。" | 应用无法直接启动其他应用。  其他应用可以在应用实现特定合约时由用户启动。  有关详细信息，请参阅[应用合约和扩展][PreviousVersionsWindowsAppsHh464906]。  |  
| APPHOST9626："检测到对资源文件的 `ms-appx://1d33240b-0b00-40e4-a416-a4750c48787f/ja-jp\images\logo.scale-140.png` 直接引用。  此引用会导致在调试环境外部使用时失败。" | 由于文件路径的原因，此 PNG 文件被视为本地化资源，导致无法直接引用本地化 `logo.scale-140.png` 资源中的错误。  如果你 [打算将此文件用作 (资源 ][PreviousVersionsWindowsAppsHh465006] ，请参阅) HTML 文档。  否则，请尝试重命名有问题的目录。  |  

## 另请参阅  

[在 JavaScript 中使用 Windows 运行时][WindowsRuntimeJavascript]  

<!-- links -->  

[WindowsRuntimeJavascript]: ./using-the-windows-runtime-in-javascript.md "在 JavaScript 中使用 Windows 运行时 |Microsoft Docs"  

[UwpWindowsGeolocationGeolocatorDevicesPositionChanged]: /uwp/api/Windows.Devices.Geolocation.Geolocator#Windows_Devices_Geolocation_Geolocator_PositionChanged "Geolocator 类 |Microsoft Docs"  

[PreviousVersionsHh771917]: /previous-versions/hh771917(v=vs.85) "addPublicLocalApplicationUri 方法 |Microsoft Docs"  

[PreviousVersionsWindowsAppsHh452771]: /previous-versions/windows/apps/hh452771(v=win.10) "如何：需要 HTTPS 连接 (HTML) |Microsoft Docs"  
[PreviousVersionsWindowsAppsHh464906]: /previous-versions/windows/apps/hh464906(v=win.10) "Windows 运行时应用中的应用 (和扩展) |Microsoft Docs"  
[PreviousVersionsWindowsAppsHh465006]: /previous-versions/windows/apps/hh465006(v=win.10) "将应用全球化 (HTML) |Microsoft Docs"  
[PreviousVersionsWindowsAppsHh465373]: /previous-versions/windows/apps/hh465373(v=win.10) "按上下文和 HTML 格式 (功能和) |Microsoft Docs"  
[PreviousVersionsWindowsAppsHh465380]: /previous-versions/windows/apps/hh465380(v=win.10) "HTML、CSS 和 JavaScript 功能以及 HTML (的差异) |Microsoft Docs"  
[PreviousVersionsWindowsAppsHh780594]: /previous-versions/windows/apps/hh780594(v=win.10) "如何链接到外部网页 (HTML) |Microsoft Docs"  

[MDNIframe]: https://developer.mozilla.org/docs/Web/HTML/Element/iframe "<iframe>：Inline Frame 元素 |MDN"  
