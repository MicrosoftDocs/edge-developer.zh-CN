---
description: 本指南概述了 Microsoft Edge 中包含的开发人员功能和标准。
title: EdgeHTML 18 中的新增功能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
ms.technology: edgehtml
keywords: edge， Web 开发， html， css， javascript， 开发人员， 开发工具
ms.custom: RS5
ms.date: 12/02/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 15d3321e05f8a307d8014696f1ab78a8967f7129
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232167"
---
# Microsoft Edge 开发人员指南

> [!TIP]
> 我们已与其他浏览器[](https://blogs.windows.com/msedgedev/2017/10/18/documenting-web-together-mdn-web-docs/)和 Web 社区合作，采用[MDN Web 文档](https://developer.mozilla.org/)作为针对当前和新出现的基于标准的 Web 技术的有用、无偏不的浏览器不可知文档的最终位置。 可以直接在 MDN Web 引用库的每个页面中找到有关 EdgeHTML API [支持的详细信息](https://developer.mozilla.org/docs/Web)。 访问 Microsoft Edge [的平台状态，](https://developer.microsoft.com/microsoft-edge/platform/status/?q=edge%3AShipped%20edge%3APrefixed%20edge%3A'Preview%20Release) 了解 Microsoft Edge 中支持的最新功能。 

## EdgeHTML 18 中的新增功能

EdgeHTML 18 包括当前版本 Microsoft Edge 平台中附带的以下新增和更新的功能，从 [Windows 10 2018 年 10](/windows/uwp/whats-new/windows-10-build-17763) 月更新 (10/2018 内部版本 17763) 开始。 有关特定 [Windows Insider](https://insider.windows.com/) Preview 内部版本的变化，请参阅 Microsoft [Edge 更改日志](https://developer.microsoft.com/microsoft-edge/platform/changelog/) 和 [EdgeHTML 中的新增功能](./whats-new.md)。

下面是以下更改列表的 permalink： [https://aka.ms/devguide_edgehtml_18](./whats-new.md)

## 新增和更新的功能

### 自动播放策略

通过 Windows 10 2018 年 10 月更新，Microsoft Edge 为客户提供了个性化设置其浏览首选项的能力，这些首选项可以自动播放具有声音的媒体，从而最大限度地减少 Web 上的干扰并节省带宽。 用户可以使用全局和每个站点自动播放控件自定义媒体行为。 此外，Microsoft Edge 自动禁止在后台选项卡中自动播放媒体。

请查看 ["自动播放策略](./browser-features/autoplay-policies.md) "指南，了解详细信息和最佳做法，以确保使用网站上托管的媒体获得良好的用户体验。

### 查克拉改进

EdgeHTML 18 除了性能和互操作性改进外，还包括对 Chakra JavaScript 引擎的更新，以支持新的 ES 和 WASM 功能。 有关详细信息， [请查看 ChakraCore 1.11](https://github.com/Microsoft/ChakraCore/wiki/Roadmap#chakracore-111) 发行说明。

### CSS 更新

在启用 CSS 掩码标志 (后，我们在[](https://developer.mozilla.org/docs/Web/CSS/mask-composite)实验性[CSS](https://developer.mozilla.org/docs/Web/CSS/CSS_Masking)掩码实现上** 进一步) 增加了对掩码复合、掩码位置和掩码重复[的支持](https://developer.mozilla.org/docs/Web/CSS/mask-repeat)。 [](https://developer.mozilla.org/docs/Web/CSS/mask-position) 对于站点兼容性，Microsoft Edge 还支持以下 *-webkit-* 属性：-webkit-mask、-webkit-mask-composite、-webkit-mask-image、-webkit-mask-position、-webkit-mask-position-x、-webkit-mask-position-y、-webkit-mask-repeat、-webkit-mask-size。

此外，Microsoft Edge 现在支持[](https://developer.mozilla.org/docs/Web/CSS/overflow-wrap
)溢出换行和部分支持过度[](https://developer.mozilla.org/docs/Web/CSS/overscroll-behavior) (`auto` 和 `contain` 值) 。

### 开发人员工具

Microsoft Edge DevTools 的最新更新为 UI 和底层添加了许多便利，包括适用于服务工作者和存储的新专用面板、调试器中的源文件搜索工具，以及用于样式/布局调试和控制台 API 的新边缘 DevTools 协议域。

[EdgeHTML 18 (中最新的 Windows 10) DevTools ](../devtools-guide/whats-new.md) 包含所有详细信息。

### 听取你的反馈

我们听取你的反馈，并实现了对 EdgeHTML 18 中多个请求的 API 的支持，包括在拖放时用于设置自定义图像的方法，以及性能资源计时 API 的属性，可用于在浏览器启动握手过程前立即返回时间戳，以确保当前连接的安全。 [`DataTransfer.setDragImage()`](https://developer.mozilla.org/docs/Web/API/DataTransfer/setDragImage) [`secureConnectionStart`](https://developer.mozilla.org/docs/Web/API/PerformanceResourceTiming/secureConnectionStart) 

此外，没有人喜欢枚举属性集合，因此添加了对将元素的属性名称作为字符串数组返回的支持，以及切换布尔属性 [`Element.getAttributeNames`](https://developer.mozilla.org/docs/Web/API/Element/getAttributeNames) (（如果存在）和添加（如果不存在）) 。 [`Element.toggleAttribute`](https://developer.mozilla.org/docs/Web/API/Element/toggleAttribute)

### 渐进式 Web 应用

#### 生存期后台脚本

Windows 10 JavaScript 应用 (在 *WWAHost.exe* 进程中运行的 Web 应用) 现在支持一个可选的每个应用程序后台脚本，该脚本在激活任何视图之前启动，在此过程期间运行。 通过此操作，可以监视和修改导航、跨导航跟踪状态、监视导航错误，以及运行代码，然后再激活视图。 

当在应用清单中指定为应用清单时，应用的每个视图 (windows) 都作为新类的实例向脚本公开，从而提供与常规 [`StartPage`](/uwp/schemas/appxpackage/appxmanifestschema2010-v2/element-application) [](/uwp/schemas/appxpackage/appx-package-manifest) ([`WebUIView`](/uwp/api/windows.ui.webui.webuiview) Win32) [WebView](/uwp/api/windows.web.ui.iwebviewcontrol)相同的事件、属性和方法。 脚本可以侦听事件 [`NewWebUIViewCreated`](/uwp/api/windows.ui.webui.newwebuiviewcreatedeventargs) 以截获新视图的导航控制：

```JavaScript
Windows.UI.WebUI.WebUIApplication.addEventListener("newwebuiviewcreated", newWebUIViewCreatedEventHandler);
```

 任何后台脚本的应用激活 `StartPage` 都将依赖脚本本身进行导航。

#### 文本缩放

Windows 10 2018 年 10 月更新引入了"放大文本"设置，以改进最终用户辅助功能，Windows (上安装的 PWA 以及 UWP 和大多数桌面应用) 现在自动支持此功能。 [**](/windows/uwp/design/input/text-scaling#user-experience) 对于 PWA 和 WebView 控件，文本缩放的工作方式与 DPI 缩放相同。 如果用户同时更改文本缩放和 DPI 缩放，则结果是两者的结果。

 有关设计指南，请查看 Windows 开发人员 [中心上的文本缩放](/windows/uwp/design/input/text-scaling) UWP *指南*。

### 服务工作者更新 

有关服务工作者是什么及其工作方法的刷新，请查看合作伙伴在 MDN 上编写的服务工作者 [API]( https://developer.mozilla.org/docs/Web/API/Service_Worker_API) 摘要。  在 EdgeHTML 18 中，对 Microsoft Edge 支持服务工作者进行了多次更新。 允许服务工作线程用于承诺响应，以及返回当前服务工作者控制的客户端的 `fetchEvent` [`preloadResponse`]( https://developer.mozilla.org/docs/Web/API/FetchEvent) [`resultingClientId`]( https://developer.mozilla.org/docs/Web/API/FetchEvent/clientId) ID。  
该接口提供用于管理资源预加载的方法，从而允许您在服务工作者启动时并行提出请求， [`NavigationPreloadManager`]( https://developer.mozilla.org/docs/Web/API/NavigationPreloadManager) 以避免任何时间延迟。 查看服务 [工作线程预加载](#new-apis-in-edgehtml-18) 方法和属性列表的新支持的 API 属性。 

### Web 身份验证

Microsoft Edge 现在包含对新的 Web 身份验证[API（](https://blogs.windows.com/msedgedev/2018/07/30/introducing-web-authentication-microsoft-edge/)即 WebAuthN (）的未) 。 [](https://w3c.github.io/webauthn/) Web 身份验证提供了一个开放、可扩展且可互操作的解决方案，以简化身份验证，从而将密码替换为更强大的硬件绑定凭据，从而提供更好的、更安全的用户体验。 除了 FIDO2 安全密钥或 FIDO U2F 安全密钥等外部验证器外，Microsoft Edge[](https://fidoalliance.org)中的实现还允许使用[Windows Hello](https://www.microsoft.com/windows/windows-hello)让用户使用人脸、指纹或 PIN 登录，从而安全地向网站进行身份验证。

有关详细信息，请前往博客文章 Microsoft Edge 中 [介绍 Web 身份验证](https://blogs.windows.com/msedgedev/2018/07/30/introducing-web-authentication-microsoft-edge)。

### WebDriver

WebDriver 现在是 Windows 按需功能 [ (](/windows-hardware/manufacture/desktop/features-on-demand-v2--capabilities) FoD) ，使在 Microsoft Edge 中自动测试并获取适合你的设备的版本变得更加简单。 安装 WebDriver 时，你不再需要手动匹配内部版本/分支/风格 [，WebDriver](https://www.w3.org/TR/webdriver) 将自动更新以匹配任何新的 Windows 10 更新。 

可以通过打开开发人员模式来安装 WebDriver，或者通过"管理可选功能">应用>应用&功能>安装 WebDriver。 有关详细信息，请查看 Windows 博客网站上 [WebDriver 公告](https://blogs.windows.com/msedgedev/2018/06/14/webdriver-w3c-recommendation-feature-on-demand)。

### Web 通知属性
Web 通知现在支持四个新属性：、、和，这提高了我们创建与现有通知系统兼容的 Web 通知的能力，同时仍与平台 [`actions`](https://developer.mozilla.org/docs/Web/API/notification/actions) [`badge`](https://developer.mozilla.org/docs/Web/API/notification/badge) [`image`](https://developer.mozilla.org/docs/Web/API/notification/image) `maxActions` 无关。

### WebView

#### 服务工作者
[除了 Microsoft](https://developer.mozilla.org/docs/Web/API/Service_Worker_API) Edge 浏览器和 Windows 10 JavaScript 应用之外，WebView 控件现在还支持服务工作者。 所有版本的 Microsoft Edge Webview [](https://developer.mozilla.org/docs/Web/API/Push_API) (PWA、UWP、Win32) 支持服务工作者，但请注意，推送 API 尚不适用于 UWP 和 Win32 版本。 [](../hosting/webview/index.md) [](/uwp/api/Windows.UI.Xaml.Controls.WebView) [](/windows/communitytoolkit/controls/wpf-winforms/webview)

x64 应用体系结构需要 *中性 (任何* CPU) *或 x64* 程序包，因为服务工作者在 WoW64 进程中不受支持。  (节省磁盘空间，Windows.) 

#### Win32 WebView 更新

适用于 Windows 桌面 (Win32) 应用的 EdgeHTML [WebViewControl](/windows/communitytoolkit/controls/wpf-winforms/webview)已更新为多个新功能，包括在页面上运行任何其他脚本之前在页面加载时注入脚本的功能 () 并知道特定 WebViewControl 何时接收或丢失焦点 [`AddInitializeScript`](/uwp/api/windows.web.ui.interop.webviewcontrol.addinitializescript) ([`GotFocus`](/uwp/api/windows.web.ui.interop.webviewcontrol.gotfocus) / [`LostFocus`](/uwp/api/windows.web.ui.interop.webviewcontrol.lostfocus)) 。

此外，你现在可以创建一个新的 WebViewControl 作为打开的窗口 [`window.open`](https://developer.mozilla.org/docs/Web/API/Window/open) 。 当 WebViewControl 中的脚本调用 window.open 时，该事件仍通知应用，因为它始终具有，但使用 EdgeHTML 18 时，该事件包含采取延迟 () 以将新的 [`NewWindowRequested`](/uwp/api/windows.web.ui.iwebviewcontrol.newwindowrequested) [`NewWindowRequestedEventArgs`](/uwp/api/windows.web.ui.webviewcontrolnewwindowrequestedeventargs) [`GetDeferral`](/uwp/api/windows.web.ui.webviewcontrolnewwindowrequestedeventargs.getdeferral) WebViewControl () 设置为 [`NewWindow`](/uwp/api/windows.web.ui.webviewcontrolnewwindowrequestedeventargs.newwindow) window.open 的目标的能力：

```csharp
WebViewControlProcess wvProc;
WebViewControl webView;

void OnWebViewControlNewWindowRequested(WebViewControl sender, WebViewControlNewWindowRequestedEventArgs args)
{

    if (args.Uri.Domain == "mydomain.com")
    {
        using deferral = args.GetDeferral();
        args.NewWindow = await wvProc.CreateWebViewControlAsync(
            parentWindow, targetWebViewBounds);
        deferral.Complete();
    }
    else
    {
        // Prevent WebView from launching in the default browser.
        args.Handled = true;
    }
}

String htmlContent = "<html><script>window.open('http://mydomain.com')</script><body></body></html>";

webView.NavigateToString(htmlContent);
```  

最后，Power 用户可能会注意到桌面应用 *Web* 查看器 (以前名为 *Win32WebViewHost*) ，这是一个代表 Win32 WebView 的内部系统应用，在下列位置显示：
- 在 *Windows 10 操作中心中*。 应了解这些通知的来源，就像从 Win32 应用托管的 WebView 一样。
- 在设备访问设置 UI 中 (*设置>隐私>/位置/麦克风*) 。 禁用其中任何设置将拒绝从 Win32 应用中托管的所有 WebView 访问。

![桌面应用 Web Viewer 设备访问设置](./media/desktop-app-web-viewer.png)

## 已否决的功能

### XSS 筛选器现已停用

使用 EdgeHTML 18，我们将停用 Microsoft Edge 中的 XSS 筛选器。 由于内容安全策略 [ (CSP) ](https://developer.mozilla.org/docs/Web/HTTP/CSP)等现代标准，我们的客户仍然受到保护，这些标准提供更强大的、高性能和安全的机制，以抵御内容注入攻击，同时在新式浏览器中实现高兼容性。

## EdgeHTML 18 中的新 API

查看 EdgeHTML 18 中新 API 的完整列表。 它们以 [接口名称] 格式列出。[api 名称]。

> [!NOTE] 
> 尽管以下 API 在 DOM 中公开，但某些 API 的端到端行为可能仍处于开发阶段，隐藏在实验标志后面。 有关  [功能支持的官方](https://developer.microsoft.com/microsoft-edge/platform/status/) 词语，请参阅 Microsoft Edge 平台状态。

<iframe height='580' scrolling='no' title='EdgeHTML 18 中的新 API' src='//codepen.io/MSEdgeDev/embed/5d7be9404d82575162b486e79d0dd58f
/?height=608&theme-id=23401&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/MSEdgeDev/pen/5d7be9404d82575162b486e79d0dd58f'> New API in EdgeHTML 18 </a> by MSEdgeDev (@MSEdgeDev <a href='https://codepen.io/MSEdgeDev'>) on </a> <a href='https://codepen.io'> </a> CodePen.</iframe>

## 以前的 EdgeHTML 版本

[EdgeHTML 13 /Windows 版本 10586 (2015 年 11 月 11 日) ](./whats-new/edgehtml-13.md)

[EdgeHTML 14 /Windows 版本 14393 (2016 年 8 月 8 日) ](./whats-new/edgehtml-14.md)

[EdgeHTML 15 /Windows 版本 15063 (2017 年 4 月 4 日) ](./whats-new/edgehtml-15.md)

[EdgeHTML 16 /Windows 版本 16299 (2017 年 10 月 10 日) ](./whats-new/edgehtml-16.md)

[EdgeHTML 17 /Windows 版本 17134 (04/2018) ](./whats-new/edgehtml-17.md)
