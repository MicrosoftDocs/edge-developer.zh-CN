---
title: 使用 JavaScript 的 Windows 运行时应用的错误代码
ms.custom: ''
ms.date: 07/29/2020
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
ms.openlocfilehash: 7779da61da9f011e55eeb496c7332e5b7cd5a023
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "10942152"
---
# 使用 JavaScript 的 Windows 运行时应用的错误代码  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

下面是在开发使用 JavaScript 的 Windows Visual Studio 运行时应用时 Microsoft Visual Studio台显示的错误代码。  

| 错误 | 备注 |  
|:--- |:--- |  
| APPHOST9601："无法加*载远程URI。*  应用无法在本地上下文中加载远程 Web 内容。" | 有关 Web 上下文中允许使用哪些功能的详细信息，请参阅 ["功能"和"按上下文分类][PreviousVersionsWindowsAppsHh465373]"。  |  
| APPHOST9602："'javascript：'是一个无效的属性值，将被忽略。  请勿在本地上下文中使用"javascript："URI"。 | 出于安全原因，你不能在本地上下文中使用"javascript："URI。  有关本地上下文中允许使用哪些功能的详细信息，请参阅 ["功能"和"按上下文分类][PreviousVersionsWindowsAppsHh465373]"。  |  
| APPHOST9603："不能在该元素中加载ActiveX为类 ID 类 ID 的 *插件*。  应用无法加载和ActiveX控件。" | 使用 JavaScript 的 Windows 运行时应用不支持自定义 Microsoft ActiveXcontrol。  如果你需要 UI 控件，可以使用标准 web 控件、控件库或创建自己的自定义控件。  如需执行自定义逻辑，则可以创建一个自定义的 Windows 运行时对象。  有关其他 HTML、CSS 和 JavaScript 区别的信息，请参阅 [HTML、CSS 和 JavaScript 功能和区别][PreviousVersionsWindowsAppsHh465380]。  |  
| APPHOST9604："无法导航到 *Uri，* 因为它使用无效的字符编码。  应用只能导航到 UTF8 编码的文件。" | Windows 运行时访问的所有 HTML、JavaScript 和 CSS 都必须编码为 8 位 Unicode 转换格式 (UTF-8) 。  有关其他 HTML、CSS 和 JavaScript 区别的信息，请参阅 [HTML、CSS 和 JavaScript 功能和区别][PreviousVersionsWindowsAppsHh465380]。  |  
| APPHOST9605："无法从来源URI 导航到*目标URI，* 因为目标 URI 位于更高的安全区域中。 *targetURI*  除非要从 Web 上下文 URI 导航到本地上下文 URI，且已使用 MSApp.addPublicLocalApplicationUri 方法，否则你不能从具有较高安全性的区域导航到区域。" | 有关详细信息，请参阅[MSApp.addPublicLocalApplicationUri。][PreviousVersionsHh771917]  |  
| APPHOST9606："无法加载 *Uri，* 因为它使用 HTTP 连接，并且存在 ms-https-connections-only meta 元素。  使用仅 ms-https-connections-only meta 元素时，将仅允许 HTTPS 连接。  使用 HTTPS 连接，或者，如果您不需要安全连接，则删除元数据元素。" | 有关详细信息，请参阅" [如何要求 HTTPS 连接][PreviousVersionsWindowsAppsHh452771]"。  |  
| APPHOST9607："应用无法在 URI 的 URI 中启动*URI：**失败代码*." | 缺少资源或无效文件是此错误的常见原因。  |  
| APPHOST9608："由于此错误：错误代码，应用无法导航到 about：blank *页面*。" |  |  

| 错误 | 备注 |  
|:--- |:--- |  
| APPHOST9610："应用在准备导航到自定义错误页面时发现有一个错误： *错误代码*." |  |  
| APPHOST9611："由于此错误，应用无法导航到自定义错误页面：错误代码."的 *错误页面*。" |  |  
| APPHOST9613："由于此错误，应用无法导航*uri**到*Uri Uri。" |  |  
| APPHOST9614："iframe 中的文档请求了 *所请求DocMode* 文档模式，但系统强制 *实践 currentDocMode* 文档模式。  该 iframe 将使用 *currentDocMode* 文档模式。" | 有关显示远程 Web 内容的详细信息，请参阅" [如何链接到外部网页][PreviousVersionsWindowsAppsHh780594]"。  |  
| APPHOST9615："应用无法在 *uri* 下载文件，因为它已在本地上下文以编程方式调用。" | 当 Web 上下文中的内容尝试以编程方式下载文件时发生。  |  
| APPHOST9616："此 URI 不能使用地理位置 API。  只能从属于程序包一部分的 URI 调用地理位置 API 或包含在清单的 ApplicationContentUris 元素中。" | 有关 Web 上下文中允许使用哪些功能的详细信息，请参阅 ["功能"和"按上下文分类][PreviousVersionsWindowsAppsHh465373]"。  |  
| APPHOST9617："此 URI 无法使用剪贴板 API。  只能从属于程序包一部分的 URI 调用剪贴板 API 或包含在清单的 ApplicationContentUris 元素中。" | 有关 Web 上下文中允许使用哪些功能的详细信息，请参阅 ["功能"和"按上下文分类][PreviousVersionsWindowsAppsHh465373]"。  |  
| APPHOST9618："此 URI 无法使用 window.close。  只能从使用 ms-appx URI 方案一起加载的打包内容调用 window.close 方法。" | 有关 Web 上下文中允许使用哪些功能的详细信息，请参阅 ["功能"和"按上下文分类][PreviousVersionsWindowsAppsHh465373]"。  |  
| APPHOST9619："应用不能导航到 *Uri，* 因为 Web 上下文中的页面不能是应用的顶层文档。  改为在 iFrame 中加载页面。 | 你不能将顶层页面导航到远程网页，但是你的应用可以在 iframe 中显示 [网页][MDNIframe]。  有关显示远程 Web 内容的详细信息，请参阅" [如何链接到外部网页][PreviousVersionsWindowsAppsHh780594]"。  |  

| 错误 | 备注 |  
|:--- |:--- |  
| APPHOST9620："此应用已关闭，因为它使用 HTTP 连接，并且 ms-https-connections-only meta 元素存在。  使用仅 ms-https-connections-only meta 元素时，将仅允许 HTTPS 连接。  使用 HTTPS 连接，或者，如果您不需要安全连接，则删除元数据元素。" | 有关详细信息，请参阅" [如何要求 HTTPS 连接][PreviousVersionsWindowsAppsHh452771]"。  |  
| APPHOST9623："由于此错误，应用无法解析*url**url：errorCode."* | 此错误的一个常见原因是缺少文件。  |  
| APPHOST9624："应用不能使用脚本加载 *URL，* 因为该 URL 启动其他应用。  只有直接用户交互可以启动另一个应用。" | 应用无法直接启动其他应用。  其他应用可在实现特定合约时启动。  有关详细信息，请参阅[应用合约和扩展][PreviousVersionsWindowsAppsHh464906]。  |  
| APPHOST9626："检测到对资源文件 `ms-appx://1d33240b-0b00-40e4-a416-a4750c48787f/ja-jp\images\logo.scale-140.png` 的直接引用。  在调试环境之外使用此引用将导致失败。" | 由于文件路径，此 `logo.scale-140.png` PNG 文件被视为本地化资源，从而无法直接引用该本地化资源中的错误。  如果 [想要将文件用作语言资源 (如何) 在 HTML ][PreviousVersionsWindowsAppsHh465006] UI 中全球化你的应用。  否则，请尝试重命名有问题的目录。  |  

## 另请参阅  

[在 JavaScript 中使用 Windows 运行时][WindowsRuntimeJavascript]  

<!-- links -->  

[WindowsRuntimeJavascript]: ./using-the-windows-runtime-in-javascript.md "在 JavaScript 中使用 Windows 运行时 |Microsoft 文档"  

[UwpWindowsGeolocationGeolocatorDevicesPositionChanged]: /uwp/api/Windows.Devices.Geolocation.Geolocator#Windows_Devices_Geolocation_Geolocator_PositionChanged "Geolocator Class |Microsoft 文档"  

[PreviousVersionsHh771917]: /previous-versions/hh771917(v=vs.85) "addPublicLocalApplicationUri 方法 |Microsoft 文档"  

[PreviousVersionsWindowsAppsHh452771]: /previous-versions/windows/apps/hh452771(v=win.10) "如何要求 HTTPS 连接 (HTML) |Microsoft 文档"  
[PreviousVersionsWindowsAppsHh464906]: /previous-versions/windows/apps/hh464906(v=win.10) "Windows 运行时应用的 (合约和扩展文件) |Microsoft 文档"  
[PreviousVersionsWindowsAppsHh465006]: /previous-versions/windows/apps/hh465006(v=win.10) "全球化应用， (HTML) |Microsoft 文档"  
[PreviousVersionsWindowsAppsHh465373]: /previous-versions/windows/apps/hh465373(v=win.10) "HTML 格式上下文来的功能 () 限制Microsoft 文档"  
[PreviousVersionsWindowsAppsHh465380]: /previous-versions/windows/apps/hh465380(v=win.10) "HTML、CSS 和 JavaScript 功能和区别;HTML () |Microsoft 文档"  
[PreviousVersionsWindowsAppsHh780594]: /previous-versions/windows/apps/hh780594(v=win.10) "如何使用 HTML 数据 (|外部网) |Microsoft 文档"  

[MDNIframe]: https://developer.mozilla.org/docs/Web/HTML/Element/iframe "<iframe>：内联框元素 |MDN"  
