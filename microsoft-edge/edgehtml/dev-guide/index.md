---
description: 本指南概述了 Microsoft Edge 中包含的开发人员功能和标准。
title: EdgeHTML 18 中的新增功能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/03/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: edgehtml
keywords: edge， Web 开发， html， css， javascript， 开发人员， devtools
ms.custom: RS5
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 6b53163115ad7db8e5b792cadda0c59b93b6711b
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11399223"
---
# <a name="microsoft-edge-developer-guide"></a>Microsoft Edge 开发人员指南  

> [!TIP]
> 我们与其他浏览器[](https://blogs.windows.com/msedgedev/2017/10/18/documenting-web-together-mdn-web-docs/)和 Web 社区合作，采用[MDN Web 文档](https://developer.mozilla.org/)作为当前和新出现的基于标准的 Web 技术的有用、无偏不的浏览器不可知文档的最终位置。  可以直接在 MDN Web 引用库的每个页面中查找有关 [EdgeHTML](https://developer.mozilla.org/docs/Web)API 支持的详细信息。  访问 Microsoft Edge [的平台状态](https://developer.microsoft.com/microsoft-edge/platform/status/?q=edge%3AShipped%20edge%3APrefixed%20edge%3A'Preview%20Release) ，了解 Microsoft Edge 中支持的最新功能。  

## <a name="whats-new-in-edgehtml-18"></a>EdgeHTML 18 中的新增功能  

从 [Windows 10 2018 年 10 月更新 \ (10/2018](/windows/uwp/whats-new/windows-10-build-17763) 内部版本 17763\) 开始，EdgeHTML 18 包括 Microsoft Edge 平台当前版本中附带的以下新增和更新功能。  有关特定 [Windows Insider](https://insider.windows.com) Preview 内部版本的变化，请参阅 Microsoft [Edge Changelog](https://developer.microsoft.com/microsoft-edge/platform/changelog) 和 [EdgeHTML 中的新增功能](./whats-new.md)。  

下面是以下更改列表的 permalink： [https://docs.microsoft.com/microsoft-edge/dev-guide](#new-apis-in-edgehtml-18)  

## <a name="new-and-updated-features"></a>新增和更新的功能  

### <a name="autoplay-policies"></a>自动播放策略  

通过 Windows 10 2018 年 10 月更新，Microsoft Edge 为客户提供了在自动播放媒体和声音的网站上个性化浏览首选项的能力，以便最大程度地减少 Web 上的干扰并节省带宽。  用户可以使用全局和每个站点自动播放控件自定义媒体行为。  此外，Microsoft Edge 自动禁止在后台选项卡中自动播放媒体。  

请查看 [自动播放策略](./browser-features/autoplay-policies.md) 指南，了解详细信息和最佳做法，以确保使用网站上托管的媒体获得良好的用户体验。  

### <a name="chakra-improvements"></a>查克拉改进  

EdgeHTML 18 包括对 Chakra JavaScript 引擎的更新，以支持新的 ES 和 WASM 功能以及性能和互操作性改进。  有关详细信息， [请查看 ChakraCore 1.11](https://github.com/Microsoft/ChakraCore/wiki/Roadmap#chakracore-111) 发行说明。  

### <a name="css-updates"></a>CSS 更新  

我们在启用 CSS 掩码标记 ) \ (的[](https://developer.mozilla.org/docs/Web/CSS/mask-position)实验**[CSS](https://developer.mozilla.org/docs/Web/CSS/CSS_Masking)掩码实现上进一步取得进展，增加了对掩码[复合](https://developer.mozilla.org/docs/Web/CSS/mask-composite)、掩码位置和掩码重复的支持。 [](https://developer.mozilla.org/docs/Web/CSS/mask-repeat)  为了实现网站兼容性，Microsoft Edge 还支持以下 *-webkit-* 属性：-webkit-mask、-webkit-mask-composite、-webkit-mask-image、-webkit-mask-position、-webkit-mask-position-x、-webkit-mask-position-y、-webkit-mask-repeat、-webkit-mask-size。  

此外，Microsoft Edge 现在支持[](https://developer.mozilla.org/docs/Web/CSS/overflow-wrap)溢出换行和部分支持过度[](https://developer.mozilla.org/docs/Web/CSS/overscroll-behavior) (`auto` 和 `contain` 值\) 。  

### <a name="developer-tools"></a>开发人员工具  

Microsoft Edge DevTools 的最新更新为 UI 和底层添加了许多便利，包括新的服务工作者和存储专用面板、调试器中的源文件搜索工具，以及用于样式/布局调试和控制台 API 的新边缘 DevTools 协议域。  

[EdgeHTML 18 (中最新的 Windows 10) DevTools ](./whats-new.md) 包含所有详细信息。  

### <a name="listening-to-your-feedback"></a>聆听你的反馈  

我们聆听您的反馈，并实现了对 EdgeHTML 18 中多个请求的 API 的支持，包括 [DataTransfer.setDragImage () ](https://developer.mozilla.org/docs/Web/API/DataTransfer/setDragImage) 方法（用于在拖放时设置自定义图像）和 [secureConnectionStart（](https://developer.mozilla.org/docs/Web/API/PerformanceResourceTiming/secureConnectionStart)性能资源计时 API 的属性，可用于在浏览器启动握手过程前立即返回时间戳，以确保当前连接的安全）。  

此外，没有人喜欢枚举属性集合，因此添加了 [对 Element.getAttributeNames](https://developer.mozilla.org/docs/Web/API/Element/getAttributeNames) 的支持，以将元素的属性名称作为字符串数组返回， [以及 Element.toggleAttribute](https://developer.mozilla.org/docs/Web/API/Element/toggleAttribute) 切换布尔属性 \ (删除（如果存在）并添加（如果不存在）\) 。  

### <a name="progressive-web-apps"></a>渐进式 Web 应用  

#### <a name="lifetime-background-script"></a>生存期后台脚本  

在进程中运行的 Windows 10 JavaScript 应用 \ (Web 应用\) 现在支持一个可选的每个应用程序后台脚本，该脚本在激活任何视图并运行该过程期间之前启动 `WWAHost.exe` 。  这样，你可以监视和修改导航、跨导航跟踪状态、监视导航错误，以及运行代码，然后再激活视图。  

在应用清单中指定为[StartPage](/uwp/schemas/appxpackage/appxmanifestschema2010-v2/element-application)时，每个应用视图 \ (windows\) 都作为新[WebUIView](/uwp/api/windows.ui.webui.webuiview)类的实例向脚本公开，从而提供与常规 \ (Win32\) [WebView](/uwp/api/windows.web.ui.iwebviewcontrol)相同的事件、属性和方法。 [](/uwp/schemas/appxpackage/appx-package-manifest)  脚本可以侦听 [NewWebUIViewCreated](/uwp/api/windows.ui.webui.newwebuiviewcreatedeventargs) 事件，以截获新视图的导航控制：  

```javascript
Windows.UI.WebUI.WebUIApplication.addEventListener("newwebuiviewcreated", newWebUIViewCreatedEventHandler);
```  

 任何后台脚本的应用激活都将 `StartPage` 依赖脚本本身进行导航。  

#### <a name="text-scaling"></a>文本缩放  

Windows 10 2018 年 10 月更新引入了"放大文本"设置以改进最终用户辅助功能，并且 Windows \ (上安装的 PWA 以及 UWP 和大多数桌面应用\) 现在自动支持此功能。 [](/windows/uwp/design/input/text-scaling#user-experience)  对于 PWA 和 WebView 控件，文本缩放的工作方式与 DPI 缩放相同。  如果用户同时更改文本缩放比例和 DPI 缩放比例，则结果是两者的结果。  

 有关设计指南，请查看 Windows 开发人员中心 [上的文本缩放](/windows/uwp/design/input/text-scaling) UWP *指南*。  

### <a name="service-worker-updates"></a>服务工作线程更新  

有关服务工作者是什么及其工作方法的刷新，请查看合作伙伴在 MDN 上编写的服务工作者 [API](https://developer.mozilla.org/docs/Web/API/Service_Worker_API) 摘要。  对 EdgeHTML 18 中支持服务工作者的 Microsoft Edge 进行了多次更新。  `fetchEvent`使服务工作者能够使用[preloadResponse](https://developer.mozilla.org/docs/Web/API/FetchEvent)承诺响应，生成的[ClientId](https://developer.mozilla.org/docs/Web/API/FetchEvent/clientId)返回当前服务工作者控制的客户端的 ID。  
[NavigationPreloadManager](https://developer.mozilla.org/docs/Web/API/NavigationPreloadManager)接口提供用于管理资源预加载的方法，允许您在服务工作者启动时并行提出请求，以避免任何时间延迟。  查看服务 [工作线程](#new-apis-in-edgehtml-18) 预加载方法和属性列表的新受支持的 API 属性。  

### <a name="web-authentication"></a>Web 身份验证  

Microsoft Edge 现在包含对 [新的 Web](https://blogs.windows.com/msedgedev/2018/07/30/introducing-web-authentication-microsoft-edge) 身份验证 API \ ([WebAuthN](https://w3c.github.io/webauthn)\) 的未) 。  Web 身份验证提供了一个开放、可扩展且可互操作的解决方案，以简化身份验证，通过用更强大的硬件绑定凭据替换密码，从而实现更好、更安全的用户体验。  Microsoft Edge 中的实现允许使用[Windows Hello，](https://www.microsoft.com/windows/windows-hello)使用户可以使用人脸、指纹或 PIN 登录，以及使用外部验证[](https://fidoalliance.org)器（如 FIDO2 安全密钥或 FIDO U2F 安全密钥）安全地向网站进行身份验证。  

有关详细信息，请参阅博客文章"Microsoft Edge 中的[Web 身份验证介绍"。](https://blogs.windows.com/msedgedev/2018/07/30/introducing-web-authentication-microsoft-edge)  

### <a name="webdriver"></a>WebDriver  

WebDriver 现在是 Windows [按需功能](https://docs.microsoft.com/windows-hardware/manufacture/desktop/features-on-demand-v2--capabilities) \ (FoD\) 使在 Microsoft Edge 中自动测试并获取适合你的设备的版本变得更加简单。  安装 WebDriver 时，你不再需要手动匹配内部版本/分支/风格 [，WebDriver](https://www.w3.org/TR/webdriver) 将自动更新以匹配任何新的 Windows 10 更新。  

可以通过打开开发人员模式来安装 WebDriver，或者通过访问"设置应用应用"&"**** 功能以  >  ****  >  **独立**  >  **方式安装它**。  有关详细信息，请查看 Windows 博客网站上 [WebDriver 公告](https://blogs.windows.com/msedgedev/2018/06/14/webdriver-w3c-recommendation-feature-on-demand)。  

### <a name="web-notification-properties"></a>Web 通知属性  

Web 通知现在支持四个新属性：[操作](https://developer.mozilla.org/docs/Web/API/notification/actions)、锁屏[提醒](https://developer.mozilla.org/docs/Web/API/notification/badge)、图像和，提高了我们在 Web 上创建与现有通知系统兼容的通知的能力，同时保持独立于[](https://developer.mozilla.org/docs/Web/API/notification/image) `maxActions` 平台。  

### <a name="webview"></a>WebView  

#### <a name="service-workers"></a>服务工作者  

[除了 Microsoft](https://developer.mozilla.org/docs/Web/API/Service_Worker_API) Edge 浏览器和 Windows 10 JavaScript 应用之外，WebView 控件现在还支持服务工作者。  所有版本的 Microsoft Edge webview \ ([PWA、](/microsoft-edge/hosting/webview) [UWP](/uwp/api/Windows.UI.Xaml.Controls.WebView)、 [Win32](/windows/communitytoolkit/controls/wpf-winforms/webview)\) 支持服务工作人员，但请注意，推送 [API](https://developer.mozilla.org/docs/Web/API/Push_API) 尚不适用于 UWP 和 Win32 版本。  

x64 应用体系结构需要中性 \ (任何 CPU\) 或 x64 程序包，因为服务工作者在 WoW64 进程中不受支持。  \ (若要节省磁盘空间，所需的 DLL 的 WoW 版本未本机包含在 Windows 中。\)   

#### <a name="win32-webview-updates"></a>Win32 WebView 更新  

适用于 Windows 桌面版 \ (Win32\) 应用的 EdgeHTML [WebViewControl](/windows/communitytoolkit/controls/wpf-winforms/webview)已更新为多个新功能，包括能够在页面上任何其他脚本运行 \ ([AddInitializeScript](/uwp/api/windows.web.ui.interop.webviewcontrol.addinitializescript)\) 之前在页面加载时注入脚本，并知道特定 WebViewControl 何时接收或失去焦点 \ ([GotFocus](/uwp/api/windows.web.ui.interop.webviewcontrol.gotfocus) / [LostFocus](/uwp/api/windows.web.ui.interop.webviewcontrol.lostfocus)\) 。  

此外，你现在可以创建一个新的 WebViewControl 作为从 [window.open 打开的窗口](https://developer.mozilla.org/docs/Web/API/Window/open)。  当 WebViewControl 中的脚本调用 window.open 时 [，NewWindowRequested](/uwp/api/windows.web.ui.iwebviewcontrol.newwindowrequested) 事件仍通知应用，但使用 EdgeHTML 18，其 [NewWindowRequestedEventArgs](/uwp/api/windows.web.ui.webviewcontrolnewwindowrequestedeventargs) 包含延迟 \ ([GetDeferral](/uwp/api/windows.web.ui.webviewcontrolnewwindowrequestedeventargs.getdeferral)\) 以将新的 WebViewControl \ ([NewWindow](/uwp/api/windows.web.ui.webviewcontrolnewwindowrequestedeventargs.newwindow)\) 设置为窗口的目标的能力。打开：  

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

最后，Power 用户可能会注意到桌面应用程序 Web 查看器 \ (以前名为 Win32WebViewHost\) （表示 Win32 WebView 的内部系统应用）在下列位置的应用：  

*   在 Windows 10 操作中心。  这些通知的来源应理解为从 Win32 应用托管的 WebView。  
*   在设备访问设置 UI \ (`Settings`  >  `Privacy`  >  `Camera/Location/Microphone` \) 。  禁用其中任何设置将拒绝从 Win32 应用中托管的所有 WebView 访问。  

![桌面应用 Web 查看器设备访问设置](./media/desktop-app-web-viewer.png)  

## <a name="deprecated-features"></a>已否决的功能  

### <a name="xss-filter-now-retired"></a>XSS 筛选器现已停用  

使用 EdgeHTML 18，我们将在 Microsoft Edge 中停用 XSS 筛选器。  由于内容安全策略 [ (CSP) ](https://developer.mozilla.org/docs/Web/HTTP/CSP)等现代标准，我们的客户仍受到保护，这些标准提供了更强大的、高性能的安全机制，可抵御内容注入攻击，同时在新式浏览器中实现高兼容性。  

## <a name="new-apis-in-edgehtml-18"></a>EdgeHTML 18 中的新 API  

查看 EdgeHTML 18 中新 API 的完整列表。  它们以 [接口名称] 的格式列出。[api 名称]。  

> [!NOTE] 
> 尽管以下 API 在 DOM 中公开，但某些 API 的端到端行为可能仍在开发中，并且隐藏在实验标志后面。  有关  [功能支持的官方](https://developer.microsoft.com/microsoft-edge/platform/status/) 词，请参阅 Microsoft Edge 平台状态。  

<iframe height='580' scrolling='no' title='EdgeHTML 18 中的新 API' src='//codepen.io/MSEdgeDev/embed/5d7be9404d82575162b486e79d0dd58f
/?height=608&theme-id=23401&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>请参阅 <a href='https://codepen.io/MSEdgeDev/pen/5d7be9404d82575162b486e79d0dd58f'> CodePen 上由 </a> MSEdgeDev (@MSEdgeDev) EdgeHTML 18 <a href='https://codepen.io/MSEdgeDev'> 中的笔新 </a> <a href='https://codepen.io'> </a> API。</iframe>  

## <a name="previous-edgehtml-releases"></a>以前的 EdgeHTML 版本  

[EdgeHTML 13 / Windows 版本 10586 (11/2015) ](./whats-new/edgehtml-13.md)  

[EdgeHTML 14 /Windows 版本 14393 (2016 年 8 月 8 日) ](./whats-new/edgehtml-14.md)  

[EdgeHTML 15 /Windows 版本 15063 (2017 年 4 月 4 日) ](./whats-new/edgehtml-15.md)  

[EdgeHTML 16 / Windows 版本 16299 (10/2017) ](./whats-new/edgehtml-16.md)  

[EdgeHTML 17 / Windows 版本 17134 (04/2018) ](https://aka.ms/devguide_edgehtml_17)  
