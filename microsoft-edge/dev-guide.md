---
title: EdgeHTML 18 中的新增功能
description: 本指南概述了 Microsoft Edge 中包含的开发人员功能和标准。
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/06/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: edgehtml
keywords: edge、web 开发、html、css、javascript、开发人员、devtools
ms.custom: RS5
ms.openlocfilehash: b9285be7169f197a687e9f754a20cf67bbde160d
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10562639"
---
# Microsoft Edge 开发人员指南

> [!TIP]
> 我们已与其他浏览器和 web 社区[合作](https://blogs.windows.com/msedgedev/2017/10/18/documenting-web-together-mdn-web-docs/)，采用[MDN web 文档](https://developer.mozilla.org/)作为针对当前和新兴的基于标准的 web 技术的有用、无偏差、不限浏览器的文档。 你可以直接在[MDN web 引用库](https://developer.mozilla.org/docs/Web)的每个页面中找到有关 EdgeHTML API 支持的详细信息。 有关 Microsoft Edge 中支持的最新功能，请访问 Microsoft Edge 的[平台状态](https://developer.microsoft.com/microsoft-edge/platform/status/?q=edge%3AShipped%20edge%3APrefixed%20edge%3A'Preview%20Release)。 


## EdgeHTML 18 中的新增功能

EdgeHTML 18 包含当前版本的 Microsoft Edge 平台（从[Windows 10 年10月2018更新](/windows/uwp/whats-new/windows-10-build-17763)（10/2018，内部版本17763）推出的以下新增和更新功能。 有关特定 Windows 预览[体验计划](https://insider.windows.com/)预览版中的更改，请参阅[Microsoft Edge Changelog](https://developer.microsoft.com/microsoft-edge/platform/changelog/)和[EdgeHTML 中的新增功能](./dev-guide/whats-new.md)。

下面是以下更改列表的固定链接： [https://aka.ms/devguide_edgehtml_18](https://aka.ms/devguide_edgehtml_18) 。

## 新增功能和更新功能

### 自动播放策略

通过 Windows 10 2018 年10月的更新，Microsoft Edge 使客户能够在网站上个性化浏览首选项，以便在 web 上自动播放媒体，以便最大限度地减少 web 上的干扰并节省带宽。 用户可以通过全局自动播放控件和每个网站的 "自动播放" 控件自定义媒体行为。 此外，Microsoft Edge 会自动取消自动播放后台选项卡中的媒体。

查看 "[自动播放策略](./dev-guide/browser-features/autoplay-policies.md)" 指南了解详细信息和最佳做法，以确保在您的网站上托管媒体的良好用户体验。

### Chakra 改进

EdgeHTML 18 包括对 Chakra JavaScript 引擎的更新，以支持除性能和互操作性改进之外的新 ES 和 WASM 功能。 有关详细信息，请查看[ChakraCore 1.11 发行说明](https://github.com/Microsoft/ChakraCore/wiki/Roadmap#chakracore-111)。

### CSS 更新

我们已在实验性的[Css 掩蔽](https://developer.mozilla.org/docs/Web/CSS/CSS_Masking)实现（在*启用 CSS 掩码*标志之后）进行了进一步的处理，并添加了对[遮罩-复合](https://developer.mozilla.org/docs/Web/CSS/mask-composite)、[遮罩位置](https://developer.mozilla.org/docs/Web/CSS/mask-position)和[掩码重复](https://developer.mozilla.org/docs/Web/CSS/mask-repeat)的支持。 对于网站兼容性，Microsoft Edge 还支持以下 *-webkit-* webkit-mask、-webkit-mask、-webkit 掩码、-webkit 蒙版位置、-webkit 蒙版位置、-webkit 蒙板-"-"-"-"-"-"-"-"。

此外，Microsoft Edge 现在支持对[overscroll](https://developer.mozilla.org/docs/Web/CSS/overscroll-behavior) （和值）进行[溢出环绕](https://developer.mozilla.org/docs/Web/CSS/overflow-wrap
)和部分支持 `auto` `contain` 。


### 开发人员工具

对 Microsoft Edge DevTools 的最新更新向 UI 添加了许多 conveniences，包括服务工作人员和存储的新专用面板、调试程序中的源代码文件搜索工具以及样式/布局调试和控制台 Api 的新的边缘 DevTools 协议域。

[最新 Windows 10 更新（EdgeHTML 18）中的 DevTools](./devtools-guide/whats-new.md)具有所有详细信息。

### 听取您的反馈

我们将听取你的反馈，并已实现对 EdgeHTML 18 中的多个请求 Api 的支持，包括 [`DataTransfer.setDragImage()`](https://developer.mozilla.org/docs/Web/API/DataTransfer/setDragImage) 用于在拖放时设置自定义图像的方法，以及 [`secureConnectionStart`](https://developer.mozilla.org/docs/Web/API/PerformanceResourceTiming/secureConnectionStart) 性能资源计时 API 的属性，可用于在浏览器启动握手进程以保护当前连接之前立即返回时间戳。 

此外，没有人喜欢枚举属性集合，因此我们添加了对 [`Element.getAttributeNames`](https://developer.mozilla.org/docs/Web/API/Element/getAttributeNames) 以字符串数组的形式返回元素的属性名称的支持，以及 [`Element.toggleAttribute`](https://developer.mozilla.org/docs/Web/API/Element/toggleAttribute) 切换布尔属性（如果不存在，则删除）。

### 渐进式 Web 应用

#### 生存期后台脚本

Windows 10 JavaScript 应用（在*WWAHost*进程中运行的 web 应用）现在支持在任何视图激活之前启动的可选基于应用程序后台脚本，并且在进程的持续时间内运行。 通过这种方式，你可以在激活视图之前监视和修改导航、跟踪跨导航的状态、监视导航错误和运行代码。 

当指定为 [`StartPage`](/uwp/schemas/appxpackage/appxmanifestschema2010-v2/element-application) 你的[应用清单](/uwp/schemas/appxpackage/appx-package-manifest)中的应用时，应用的每个视图（windows）作为新类的实例公开给脚本 [`WebUIView`](/uwp/api/windows.ui.webui.webuiview) ，并提供相同的事件、属性和方法作为常规（Win32） [web 视图](/uwp/api/windows.web.ui.iwebviewcontrol)。 你的脚本可以侦听 [`NewWebUIViewCreated`](/uwp/api/windows.ui.webui.newwebuiviewcreatedeventargs) 事件以截获对新视图的导航的控制：

```JavaScript
Windows.UI.WebUI.WebUIApplication.addEventListener("newwebuiviewcreated", newWebUIViewCreatedEventHandler);
```

 任何具有后台脚本的应用激活 `StartPage` 都将依赖脚本本身进行导航。

#### 文本缩放

Windows 10 月2018更新引入了 "[*使文本更大*](https://review.docs.microsoft.com/windows/uwp/design/input/text-scaling?branch=master#user-experience)" 设置以提高最终用户的可访问性，在 Windows 上安装的 PWAs （也是 UWP 和大多数桌面应用）现在可自动支持此功能。 对于 PWAs 和 Web 视图控件，文本缩放的工作方式与 DPI 缩放的方式相同。 如果用户同时更改了文本比例和 DPI 比例，则结果为两个的积。

 有关设计指南，请查看*Windows 开发人员中心*上的[文本缩放](/windows/uwp/design/input/text-scaling)UWP 指南。

### 服务工作人员更新 

有关服务工作人员及其工作方式的复习，请查看我们的合作伙伴在 MDN 上编写的[服务工作器 API]( https://developer.mozilla.org/docs/Web/API/Service_Worker_API)摘要。  EdgeHTML 18 中有多个 Microsoft Edge 支持服务工作者的更新。 `fetchEvent`允许服务工作者使用服务工作者 [`preloadResponse`]( https://developer.mozilla.org/docs/Web/API/FetchEvent) 承诺响应，并 [`resultingClientId`]( https://developer.mozilla.org/docs/Web/API/FetchEvent/clientId) 返回当前服务工作人员正在控制的客户端的 ID。  
该 [`NavigationPreloadManager`]( https://developer.mozilla.org/docs/Web/API/NavigationPreloadManager) 接口提供用于管理资源预加载的方法，使你能够在服务工作人员启动时并行执行请求，避免任何时间延迟。 查看[新支持的 API 属性](#new-apis-in-edgehtml-18)，了解服务工作人员预加载方法和属性的列表。 

### Web 身份验证

Microsoft Edge 现已[为新的 Web 身份验证 API](https://blogs.windows.com/msedgedev/2018/07/30/introducing-web-authentication-microsoft-edge/) （也称为 " [WebAuthN](https://w3c.github.io/webauthn/)"）提供 unprefixed 支持。 Web 身份验证提供了一个开放、可伸缩且可互操作的解决方案，可简化身份验证，通过使用更强大的硬件绑定凭据替换密码来实现更好、更安全的用户体验。 Microsoft Edge 中的实现允许使用[Windows Hello](https://www.microsoft.com/windows/windows-hello) ，除了[外部 AUTHENTICATORS](https://fidoalliance.org) （如 FIDO2 安全密钥或 FIDO U2F 安全密钥）之外，还可让用户使用其表面、指纹或 PIN 进行登录，以安全地向网站进行身份验证。

有关详细信息，请转到博客文章[在 Microsoft Edge 中引入 Web 身份验证](https://blogs.windows.com/msedgedev/2018/07/30/introducing-web-authentication-microsoft-edge)。

### WebDriver

WebDriver 现在是一种[Windows 功能的点播](https://docs.microsoft.com/windows-hardware/manufacture/desktop/features-on-demand-v2--capabilities)（FoD），使你可以比以往更轻松地在 Microsoft Edge 中自动化测试并为你的设备获取正确的版本。 在安装 WebDriver 时，你将不再需要手动匹配 "生成/分支/风格"，你的[WebDriver](https://www.w3.org/TR/webdriver)将自动更新以匹配任何新的 Windows 10 更新。 

你可以通过启用开发人员模式来安装 WebDriver，也可以通过转到 > 应用 > 应用 & 功能 > 管理可选功能来安装它。 有关详细信息，请查看[Windows 博客网站上的 WebDriver 公告](https://blogs.windows.com/msedgedev/2018/06/14/webdriver-w3c-recommendation-feature-on-demand)。

### Web 通知属性
对于 web 通知，现在支持四个新属性： [`actions`](https://developer.mozilla.org/docs/Web/API/notification/actions) 、、 [`badge`](https://developer.mozilla.org/docs/Web/API/notification/badge) [`image`](https://developer.mozilla.org/docs/Web/API/notification/image) 和 `maxActions` ，提高了我们在 web 上创建与现有通知系统兼容的通知的能力，而其余平台独立于平台。

### WebView

#### 服务工作人员
除了 Microsoft Edge 浏览器和 Windows 10 JavaScript 应用之外，"Web 视图" 控件中现在还支持[服务工作人员](https://developer.mozilla.org/docs/Web/API/Service_Worker_API)。 Microsoft Edge web Edge （[PWA](/microsoft-edge/hosting/webview)、 [UWP](/uwp/api/Windows.UI.Xaml.Controls.WebView)、 [Win32](/windows/communitytoolkit/controls/wpf-winforms/webview)）支持服务工作人员的各种风格，但是请注意，对于 UWP 和 Win32 版本， [Push API](https://developer.mozilla.org/docs/Web/API/Push_API)尚不可用。

x64 应用体系结构需要*中立*（任何 CPU）或*x64*程序包，因为 WoW64 进程不支持服务工作人员。 （为节省磁盘空间，所需 Dll 的 WoW 版本不是本机包含在 Windows 中。）

#### Win32 Web 视图更新

Windows desktop （Win32）应用的 EdgeHTML [WebViewControl](/windows/communitytoolkit/controls/wpf-winforms/webview)已使用多个新功能进行了更新，包括在页面加载时插入脚本的功能（ [`AddInitializeScript`](/uwp/api/windows.web.ui.interop.webviewcontrol.addinitializescript) ），并知道特定 WebViewControl 何时接收或失去焦点（） [`GotFocus`](/uwp/api/windows.web.ui.interop.webviewcontrol.gotfocus) / [`LostFocus`](/uwp/api/windows.web.ui.interop.webviewcontrol.lostfocus) 。

此外，您现在可以创建新的 WebViewControl 作为打开的窗口 [`window.open`](https://developer.mozilla.org/docs/Web/API/Window/open) 。 [`NewWindowRequested`](/uwp/api/windows.web.ui.iwebviewcontrol.newwindowrequested)当 WebViewControl 调用窗口中的脚本时，该事件仍会通知应用。按原样打开，但对于 EdgeHTML 18，它 [`NewWindowRequestedEventArgs`](/uwp/api/windows.web.ui.webviewcontrolnewwindowrequestedeventargs) 包括可以采取延迟（）的能力，以便 [`GetDeferral`](/uwp/api/windows.web.ui.webviewcontrolnewwindowrequestedeventargs.getdeferral) 将新的 WebViewControl （）设置 [`NewWindow`](/uwp/api/windows.web.ui.webviewcontrolnewwindowrequestedeventargs.newwindow) 为窗口的目标。打开：

```C#
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

最后，power users 可能会注意到*桌面应用 Web Viewer*的 apppearance （以前称为*Win32WebViewHost*），这是一个内部系统应用，表示 Win32 web 视图，位于以下位置：
- 在*Windows 10 操作中心*中。 应从 Win32 应用托管的 Web 视图中理解这些通知的来源。
- 在 "设备访问设置" UI （*设置->隐私->相机/位置/麦克风*）中。 禁用任何这些设置将拒绝在 Win32 应用中托管的所有 WebViews 的访问权限。

![桌面应用程序 Web 查看器设备访问设置](./dev-guide/media/desktop-app-web-viewer.png)


## 已否决的功能

### XSS 筛选器现已停用

通过 EdgeHTML 18，我们将在 Microsoft Edge 中停用 XSS 筛选器。 我们的客户因[内容安全政策（CSP）](https://developer.mozilla.org/docs/Web/HTTP/CSP)等新式标准而保持受保护，它提供了更强大、性能和安全的机制来防止内容注入式攻击，并且在新式浏览器中具有高兼容性。

## EdgeHTML 18 中的新 Api

查看 EdgeHTML 18 中新 Api 的完整列表。 它们以 [界面名称] 的格式列出。[api 名称]。

> [!NOTE] 
> 虽然在 DOM 中公开以下 Api，但某些 Api 的端到端行为可能仍在开发和隐藏实验标志背后。 请参阅[Microsoft Edge 平台状态](https://developer.microsoft.com/microsoft-edge/platform/status/)，了解有关功能支持的官方 word 功能。

<iframe height='580' scrolling='no' title='EdgeHTML 18 中的新 Api' src='//codepen.io/MSEdgeDev/embed/5d7be9404d82575162b486e79d0dd58f
/?height=608&theme-id=23401&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>在 <a href='https://codepen.io/MSEdgeDev/pen/5d7be9404d82575162b486e79d0dd58f'> </a> CodePen 上的 MSEdgeDev （@MSEdgeDev）中查看 EdgeHTML 18 中的笔新 api <a href='https://codepen.io/MSEdgeDev'> </a> <a href='https://codepen.io'> </a> 。</iframe>

## 以前的 EdgeHTML 版本

[EdgeHTML 13/Windows 内部版本10586（11/2015）](https://aka.ms/devguide_edgehtml_13)

[EdgeHTML 14/Windows 内部版本14393（8/2016）](https://aka.ms/devguide_edgehtml_14)

[EdgeHTML 15/Windows 内部版本15063（4/2017）](https://aka.ms/devguide_edgehtml_15)

[EdgeHTML 16/Windows 内部版本16299（10/2017）](https://aka.ms/devguide_edgehtml_16)

[EdgeHTML 17/Windows 内部版本17134（04/2018）](https://aka.ms/devguide_edgehtml_17)
