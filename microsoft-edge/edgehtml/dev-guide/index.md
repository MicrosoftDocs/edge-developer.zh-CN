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
# <a name="microsoft-edge-developer-guide"></a><span data-ttu-id="f0d8f-104">Microsoft Edge 开发人员指南</span><span class="sxs-lookup"><span data-stu-id="f0d8f-104">Microsoft Edge Developer Guide</span></span>  

> [!TIP]
> <span data-ttu-id="f0d8f-105">我们与其他浏览器[](https://blogs.windows.com/msedgedev/2017/10/18/documenting-web-together-mdn-web-docs/)和 Web 社区合作，采用[MDN Web 文档](https://developer.mozilla.org/)作为当前和新出现的基于标准的 Web 技术的有用、无偏不的浏览器不可知文档的最终位置。</span><span class="sxs-lookup"><span data-stu-id="f0d8f-105">We've [partnered](https://blogs.windows.com/msedgedev/2017/10/18/documenting-web-together-mdn-web-docs/) with other browsers and the web community in adopting [MDN Web Docs](https://developer.mozilla.org/) as the definitive place for useful, unbiased, browser-agnostic documentation for current and emerging standards-based web technologies.</span></span>  <span data-ttu-id="f0d8f-106">可以直接在 MDN Web 引用库的每个页面中查找有关 [EdgeHTML](https://developer.mozilla.org/docs/Web)API 支持的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f0d8f-106">You can find details about EdgeHTML API support directly in each page of the [MDN web reference library](https://developer.mozilla.org/docs/Web).</span></span>  <span data-ttu-id="f0d8f-107">访问 Microsoft Edge [的平台状态](https://developer.microsoft.com/microsoft-edge/platform/status/?q=edge%3AShipped%20edge%3APrefixed%20edge%3A'Preview%20Release) ，了解 Microsoft Edge 中支持的最新功能。</span><span class="sxs-lookup"><span data-stu-id="f0d8f-107">Visit Microsoft Edge's [Platform status](https://developer.microsoft.com/microsoft-edge/platform/status/?q=edge%3AShipped%20edge%3APrefixed%20edge%3A'Preview%20Release) for the latest features supported in Microsoft Edge.</span></span>  

## <a name="whats-new-in-edgehtml-18"></a><span data-ttu-id="f0d8f-108">EdgeHTML 18 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="f0d8f-108">What's new in EdgeHTML 18</span></span>  

<span data-ttu-id="f0d8f-109">从 [Windows 10 2018 年 10 月更新 \(10/2018](/windows/uwp/whats-new/windows-10-build-17763) 内部版本 17763\) 开始，EdgeHTML 18 包括 Microsoft Edge 平台当前版本中附带的以下新增和更新功能。</span><span class="sxs-lookup"><span data-stu-id="f0d8f-109">EdgeHTML 18 includes the following new and updated features shipped in the current release of the Microsoft Edge platform, as of the [Windows 10 October 2018 Update](/windows/uwp/whats-new/windows-10-build-17763) \(10/2018, Build 17763\).</span></span>  <span data-ttu-id="f0d8f-110">有关特定 [Windows Insider](https://insider.windows.com) Preview 内部版本的变化，请参阅 Microsoft [Edge Changelog](https://developer.microsoft.com/microsoft-edge/platform/changelog) 和 [EdgeHTML 中的新增功能](./whats-new.md)。</span><span class="sxs-lookup"><span data-stu-id="f0d8f-110">For changes in specific [Windows Insider](https://insider.windows.com) Preview builds, see the [Microsoft Edge Changelog](https://developer.microsoft.com/microsoft-edge/platform/changelog) and [What's New in EdgeHTML](./whats-new.md).</span></span>  

<span data-ttu-id="f0d8f-111">下面是以下更改列表的 permalink： [https://docs.microsoft.com/microsoft-edge/dev-guide](#new-apis-in-edgehtml-18)</span><span class="sxs-lookup"><span data-stu-id="f0d8f-111">Here's the permalink for the following list of changes: [https://docs.microsoft.com/microsoft-edge/dev-guide](#new-apis-in-edgehtml-18).</span></span>  

## <a name="new-and-updated-features"></a><span data-ttu-id="f0d8f-112">新增和更新的功能</span><span class="sxs-lookup"><span data-stu-id="f0d8f-112">New and updated features</span></span>  

### <a name="autoplay-policies"></a><span data-ttu-id="f0d8f-113">自动播放策略</span><span class="sxs-lookup"><span data-stu-id="f0d8f-113">Autoplay policies</span></span>  

<span data-ttu-id="f0d8f-114">通过 Windows 10 2018 年 10 月更新，Microsoft Edge 为客户提供了在自动播放媒体和声音的网站上个性化浏览首选项的能力，以便最大程度地减少 Web 上的干扰并节省带宽。</span><span class="sxs-lookup"><span data-stu-id="f0d8f-114">With the Windows 10 October 2018 Update, Microsoft Edge provides customers with the ability to personalize their browsing preferences on websites that autoplay media with sound in order to minimize distractions on the web and conserve bandwidth.</span></span>  <span data-ttu-id="f0d8f-115">用户可以使用全局和每个站点自动播放控件自定义媒体行为。</span><span class="sxs-lookup"><span data-stu-id="f0d8f-115">Users can customize media behavior with both global and per-site autoplay controls.</span></span>  <span data-ttu-id="f0d8f-116">此外，Microsoft Edge 自动禁止在后台选项卡中自动播放媒体。</span><span class="sxs-lookup"><span data-stu-id="f0d8f-116">Additionally, Microsoft Edge automatically suppresses autoplay of media in background tabs.</span></span>  

<span data-ttu-id="f0d8f-117">请查看 [自动播放策略](./browser-features/autoplay-policies.md) 指南，了解详细信息和最佳做法，以确保使用网站上托管的媒体获得良好的用户体验。</span><span class="sxs-lookup"><span data-stu-id="f0d8f-117">Check out the [Autoplay policies](./browser-features/autoplay-policies.md) guide for details and best practices to ensure a good user experience with media hosted on your site.</span></span>  

### <a name="chakra-improvements"></a><span data-ttu-id="f0d8f-118">查克拉改进</span><span class="sxs-lookup"><span data-stu-id="f0d8f-118">Chakra improvements</span></span>  

<span data-ttu-id="f0d8f-119">EdgeHTML 18 包括对 Chakra JavaScript 引擎的更新，以支持新的 ES 和 WASM 功能以及性能和互操作性改进。</span><span class="sxs-lookup"><span data-stu-id="f0d8f-119">EdgeHTML 18 includes updates to the Chakra JavaScript engine to support new ES and WASM features in addition to performance and interoperability improvements.</span></span>  <span data-ttu-id="f0d8f-120">有关详细信息， [请查看 ChakraCore 1.11](https://github.com/Microsoft/ChakraCore/wiki/Roadmap#chakracore-111) 发行说明。</span><span class="sxs-lookup"><span data-stu-id="f0d8f-120">Check out the [ChakraCore 1.11 Release Notes](https://github.com/Microsoft/ChakraCore/wiki/Roadmap#chakracore-111) for details.</span></span>  

### <a name="css-updates"></a><span data-ttu-id="f0d8f-121">CSS 更新</span><span class="sxs-lookup"><span data-stu-id="f0d8f-121">CSS updates</span></span>  

<span data-ttu-id="f0d8f-122">我们在启用 CSS 掩码标记 ) \(的[](https://developer.mozilla.org/docs/Web/CSS/mask-position)实验[CSS](https://developer.mozilla.org/docs/Web/CSS/CSS_Masking)掩码实现上进一步取得进展，增加了对掩码[复合](https://developer.mozilla.org/docs/Web/CSS/mask-composite)、掩码位置和掩码重复的支持。 [](https://developer.mozilla.org/docs/Web/CSS/mask-repeat)</span><span class="sxs-lookup"><span data-stu-id="f0d8f-122">We've made further progress on our experimental [CSS Masking](https://developer.mozilla.org/docs/Web/CSS/CSS_Masking) implementation \(behind the *Enable CSS Masking* flag\) with added support for [mask-composite](https://developer.mozilla.org/docs/Web/CSS/mask-composite), [mask-position](https://developer.mozilla.org/docs/Web/CSS/mask-position), and [mask-repeat](https://developer.mozilla.org/docs/Web/CSS/mask-repeat).</span></span>  <span data-ttu-id="f0d8f-123">为了实现网站兼容性，Microsoft Edge 还支持以下 *-webkit-* 属性：-webkit-mask、-webkit-mask-composite、-webkit-mask-image、-webkit-mask-position、-webkit-mask-position-x、-webkit-mask-position-y、-webkit-mask-repeat、-webkit-mask-size。</span><span class="sxs-lookup"><span data-stu-id="f0d8f-123">For site compatibility, Microsoft Edge also supports the following *-webkit-* properties: -webkit-mask, -webkit-mask-composite, -webkit-mask-image, -webkit-mask-position, -webkit-mask-position-x, -webkit-mask-position-y, -webkit-mask-repeat, -webkit-mask-size.</span></span>  

<span data-ttu-id="f0d8f-124">此外，Microsoft Edge 现在支持[](https://developer.mozilla.org/docs/Web/CSS/overflow-wrap)溢出换行和部分支持过度[](https://developer.mozilla.org/docs/Web/CSS/overscroll-behavior) (`auto` 和 `contain` 值\) 。</span><span class="sxs-lookup"><span data-stu-id="f0d8f-124">Additionally, Microsoft Edge now has support for [overflow-wrap](https://developer.mozilla.org/docs/Web/CSS/overflow-wrap) and partial support for [overscroll-behavior](https://developer.mozilla.org/docs/Web/CSS/overscroll-behavior) \(`auto` and `contain` values\).</span></span>  

### <a name="developer-tools"></a><span data-ttu-id="f0d8f-125">开发人员工具</span><span class="sxs-lookup"><span data-stu-id="f0d8f-125">Developer Tools</span></span>  

<span data-ttu-id="f0d8f-126">Microsoft Edge DevTools 的最新更新为 UI 和底层添加了许多便利，包括新的服务工作者和存储专用面板、调试器中的源文件搜索工具，以及用于样式/布局调试和控制台 API 的新边缘 DevTools 协议域。</span><span class="sxs-lookup"><span data-stu-id="f0d8f-126">The latest update to Microsoft Edge DevTools adds a number of conveniences both to the UI and under the hood, including new dedicated panels for Service Workers and Storage, source file search tools in the Debugger, and new Edge DevTools Protocol domains for style/layout debugging and console APIs.</span></span>  

<span data-ttu-id="f0d8f-127">[EdgeHTML 18 (中最新的 Windows 10) DevTools ](./whats-new.md) 包含所有详细信息。</span><span class="sxs-lookup"><span data-stu-id="f0d8f-127">[DevTools in the latest Windows 10 update (EdgeHTML 18)](./whats-new.md) has all the details.</span></span>  

### <a name="listening-to-your-feedback"></a><span data-ttu-id="f0d8f-128">聆听你的反馈</span><span class="sxs-lookup"><span data-stu-id="f0d8f-128">Listening to your feedback</span></span>  

<span data-ttu-id="f0d8f-129">我们聆听您的反馈，并实现了对 EdgeHTML 18 中多个请求的 API 的支持，包括 [DataTransfer.setDragImage () ](https://developer.mozilla.org/docs/Web/API/DataTransfer/setDragImage) 方法（用于在拖放时设置自定义图像）和 [secureConnectionStart（](https://developer.mozilla.org/docs/Web/API/PerformanceResourceTiming/secureConnectionStart)性能资源计时 API 的属性，可用于在浏览器启动握手过程前立即返回时间戳，以确保当前连接的安全）。</span><span class="sxs-lookup"><span data-stu-id="f0d8f-129">We listen to your feedback and have implemented support for several requested APIs in EdgeHTML 18, including the [DataTransfer.setDragImage()](https://developer.mozilla.org/docs/Web/API/DataTransfer/setDragImage) method used to set a custom image when dragging and dropping, and [secureConnectionStart](https://developer.mozilla.org/docs/Web/API/PerformanceResourceTiming/secureConnectionStart), a property of the Performance Resource Timing API, which can be used for returning a timestamp immediately before the browser starts the handshake process to secure the current connection.</span></span>  

<span data-ttu-id="f0d8f-130">此外，没有人喜欢枚举属性集合，因此添加了 [对 Element.getAttributeNames](https://developer.mozilla.org/docs/Web/API/Element/getAttributeNames) 的支持，以将元素的属性名称作为字符串数组返回， [以及 Element.toggleAttribute](https://developer.mozilla.org/docs/Web/API/Element/toggleAttribute) 切换布尔属性 \(删除（如果存在）并添加（如果不存在）\) 。</span><span class="sxs-lookup"><span data-stu-id="f0d8f-130">In addition, no one likes enumerating the attributes collection, so we've added support for [Element.getAttributeNames](https://developer.mozilla.org/docs/Web/API/Element/getAttributeNames) to return the attribute names of the element as an Array of strings, as well as, [Element.toggleAttribute](https://developer.mozilla.org/docs/Web/API/Element/toggleAttribute) to toggle a boolean attribute \(removing if present and adding if not\).</span></span>  

### <a name="progressive-web-apps"></a><span data-ttu-id="f0d8f-131">渐进式 Web 应用</span><span class="sxs-lookup"><span data-stu-id="f0d8f-131">Progressive Web Apps</span></span>  

#### <a name="lifetime-background-script"></a><span data-ttu-id="f0d8f-132">生存期后台脚本</span><span class="sxs-lookup"><span data-stu-id="f0d8f-132">Lifetime background script</span></span>  

<span data-ttu-id="f0d8f-133">在进程中运行的 Windows 10 JavaScript 应用 \(Web 应用\) 现在支持一个可选的每个应用程序后台脚本，该脚本在激活任何视图并运行该过程期间之前启动 `WWAHost.exe` 。</span><span class="sxs-lookup"><span data-stu-id="f0d8f-133">Windows 10 JavaScript apps \(web apps running in a `WWAHost.exe` process\) now support an optional per-application background script that starts before any views are activated and runs for the duration of the process.</span></span>  <span data-ttu-id="f0d8f-134">这样，你可以监视和修改导航、跨导航跟踪状态、监视导航错误，以及运行代码，然后再激活视图。</span><span class="sxs-lookup"><span data-stu-id="f0d8f-134">With this, you can monitor and modify navigations, track state across navigations, monitor navigation errors, and run code before views are activated.</span></span>  

<span data-ttu-id="f0d8f-135">在应用清单中指定为[StartPage](/uwp/schemas/appxpackage/appxmanifestschema2010-v2/element-application)时，每个应用视图 \(windows\) 都作为新[WebUIView](/uwp/api/windows.ui.webui.webuiview)类的实例向脚本公开，从而提供与常规 \(Win32\) [WebView](/uwp/api/windows.web.ui.iwebviewcontrol)相同的事件、属性和方法。 [](/uwp/schemas/appxpackage/appx-package-manifest)</span><span class="sxs-lookup"><span data-stu-id="f0d8f-135">When specified as the [StartPage](/uwp/schemas/appxpackage/appxmanifestschema2010-v2/element-application) in your [app manifest](/uwp/schemas/appxpackage/appx-package-manifest), each of the app's views \(windows\) are exposed to the script as instances of the new [WebUIView](/uwp/api/windows.ui.webui.webuiview) class, providing the same events, properties, and methods as a general \(Win32\) [WebView](/uwp/api/windows.web.ui.iwebviewcontrol).</span></span>  <span data-ttu-id="f0d8f-136">脚本可以侦听 [NewWebUIViewCreated](/uwp/api/windows.ui.webui.newwebuiviewcreatedeventargs) 事件，以截获新视图的导航控制：</span><span class="sxs-lookup"><span data-stu-id="f0d8f-136">Your script can listen for the [NewWebUIViewCreated](/uwp/api/windows.ui.webui.newwebuiviewcreatedeventargs) event to intercept control of the navigation for a new view:</span></span>  

```javascript
Windows.UI.WebUI.WebUIApplication.addEventListener("newwebuiviewcreated", newWebUIViewCreatedEventHandler);
```  

 <span data-ttu-id="f0d8f-137">任何后台脚本的应用激活都将 `StartPage` 依赖脚本本身进行导航。</span><span class="sxs-lookup"><span data-stu-id="f0d8f-137">Any app activation with the background script as the `StartPage` will rely on the script itself for navigation.</span></span>  

#### <a name="text-scaling"></a><span data-ttu-id="f0d8f-138">文本缩放</span><span class="sxs-lookup"><span data-stu-id="f0d8f-138">Text scaling</span></span>  

<span data-ttu-id="f0d8f-139">Windows 10 2018 年 10 月更新引入了"放大文本"设置以改进最终用户辅助功能，并且 Windows \(上安装的 PWA 以及 UWP 和大多数桌面应用\) 现在自动支持此功能。 [](/windows/uwp/design/input/text-scaling#user-experience)</span><span class="sxs-lookup"><span data-stu-id="f0d8f-139">The Windows 10 October 2018 Update introduces the [Make text bigger](/windows/uwp/design/input/text-scaling#user-experience) setting for improved end-user accessibility, and PWAs installed on Windows \(in addition UWP and most desktop apps\) now support this feature automatically.</span></span>  <span data-ttu-id="f0d8f-140">对于 PWA 和 WebView 控件，文本缩放的工作方式与 DPI 缩放相同。</span><span class="sxs-lookup"><span data-stu-id="f0d8f-140">For PWAs and WebView controls, text scale works the same way as DPI scaling.</span></span>  <span data-ttu-id="f0d8f-141">如果用户同时更改文本缩放比例和 DPI 缩放比例，则结果是两者的结果。</span><span class="sxs-lookup"><span data-stu-id="f0d8f-141">If a user changes both text scale and DPI scale, the result is the product of the two.</span></span>  

 <span data-ttu-id="f0d8f-142">有关设计指南，请查看 Windows 开发人员中心 [上的文本缩放](/windows/uwp/design/input/text-scaling) UWP *指南*。</span><span class="sxs-lookup"><span data-stu-id="f0d8f-142">For design guidance, check out the [Text scaling](/windows/uwp/design/input/text-scaling) UWP guide on *Windows Dev Center*.</span></span>  

### <a name="service-worker-updates"></a><span data-ttu-id="f0d8f-143">服务工作线程更新</span><span class="sxs-lookup"><span data-stu-id="f0d8f-143">Service Worker updates</span></span>  

<span data-ttu-id="f0d8f-144">有关服务工作者是什么及其工作方法的刷新，请查看合作伙伴在 MDN 上编写的服务工作者 [API](https://developer.mozilla.org/docs/Web/API/Service_Worker_API) 摘要。</span><span class="sxs-lookup"><span data-stu-id="f0d8f-144">For a refresher on what Service Workers are and how they work, check out the [Service Worker API](https://developer.mozilla.org/docs/Web/API/Service_Worker_API) summary written by our partners over at MDN.</span></span>  <span data-ttu-id="f0d8f-145">对 EdgeHTML 18 中支持服务工作者的 Microsoft Edge 进行了多次更新。</span><span class="sxs-lookup"><span data-stu-id="f0d8f-145">There were several updates to Microsoft Edge supporting Service Workers in EdgeHTML 18.</span></span>  <span data-ttu-id="f0d8f-146">`fetchEvent`使服务工作者能够使用[preloadResponse](https://developer.mozilla.org/docs/Web/API/FetchEvent)承诺响应，生成的[ClientId](https://developer.mozilla.org/docs/Web/API/FetchEvent/clientId)返回当前服务工作者控制的客户端的 ID。</span><span class="sxs-lookup"><span data-stu-id="f0d8f-146">The `fetchEvent` enables the Service Worker to use [preloadResponse](https://developer.mozilla.org/docs/Web/API/FetchEvent) to promise a response, and the [resultingClientId](https://developer.mozilla.org/docs/Web/API/FetchEvent/clientId) to return the ID of the Client that the current service worker is controlling.</span></span>  
<span data-ttu-id="f0d8f-147">[NavigationPreloadManager](https://developer.mozilla.org/docs/Web/API/NavigationPreloadManager)接口提供用于管理资源预加载的方法，允许您在服务工作者启动时并行提出请求，以避免任何时间延迟。</span><span class="sxs-lookup"><span data-stu-id="f0d8f-147">The [NavigationPreloadManager](https://developer.mozilla.org/docs/Web/API/NavigationPreloadManager) interface provides methods for managing the preloading of resources, allowing you to make a request in parallel while a service worker is booting-up, avoiding any time delay.</span></span>  <span data-ttu-id="f0d8f-148">查看服务 [工作线程](#new-apis-in-edgehtml-18) 预加载方法和属性列表的新受支持的 API 属性。</span><span class="sxs-lookup"><span data-stu-id="f0d8f-148">Check out the [newly supported API properties](#new-apis-in-edgehtml-18) for the list of Service Worker preload methods and properties.</span></span>  

### <a name="web-authentication"></a><span data-ttu-id="f0d8f-149">Web 身份验证</span><span class="sxs-lookup"><span data-stu-id="f0d8f-149">Web Authentication</span></span>  

<span data-ttu-id="f0d8f-150">Microsoft Edge 现在包含对 [新的 Web](https://blogs.windows.com/msedgedev/2018/07/30/introducing-web-authentication-microsoft-edge) 身份验证 API \([WebAuthN](https://w3c.github.io/webauthn)\) 的未) 。</span><span class="sxs-lookup"><span data-stu-id="f0d8f-150">Microsoft Edge now includes [unprefixed support for the new Web Authentication API](https://blogs.windows.com/msedgedev/2018/07/30/introducing-web-authentication-microsoft-edge) \(aka [WebAuthN](https://w3c.github.io/webauthn)\).</span></span>  <span data-ttu-id="f0d8f-151">Web 身份验证提供了一个开放、可扩展且可互操作的解决方案，以简化身份验证，通过用更强大的硬件绑定凭据替换密码，从而实现更好、更安全的用户体验。</span><span class="sxs-lookup"><span data-stu-id="f0d8f-151">Web Authentication provides an open, scalable, and interoperable solution to simplify authentication, enabling better and more secure user experiences by replacing passwords with stronger hardware-bound credentials.</span></span>  <span data-ttu-id="f0d8f-152">Microsoft Edge 中的实现允许使用[Windows Hello，](https://www.microsoft.com/windows/windows-hello)使用户可以使用人脸、指纹或 PIN 登录，以及使用外部验证[](https://fidoalliance.org)器（如 FIDO2 安全密钥或 FIDO U2F 安全密钥）安全地向网站进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="f0d8f-152">The implementation in Microsoft Edge allows the use of [Windows Hello](https://www.microsoft.com/windows/windows-hello) enabling users to sign in with their face, fingerprint, or PIN, in addition to [external authenticators](https://fidoalliance.org) like FIDO2 Security Keys or FIDO U2F Security Keys, to securely authenticate to websites.</span></span>  

<span data-ttu-id="f0d8f-153">有关详细信息，请参阅博客文章"Microsoft Edge 中的[Web 身份验证介绍"。](https://blogs.windows.com/msedgedev/2018/07/30/introducing-web-authentication-microsoft-edge)</span><span class="sxs-lookup"><span data-stu-id="f0d8f-153">For more information, head over to the blog post [Introducing Web Authentication in Microsoft Edge](https://blogs.windows.com/msedgedev/2018/07/30/introducing-web-authentication-microsoft-edge).</span></span>  

### <a name="webdriver"></a><span data-ttu-id="f0d8f-154">WebDriver</span><span class="sxs-lookup"><span data-stu-id="f0d8f-154">WebDriver</span></span>  

<span data-ttu-id="f0d8f-155">WebDriver 现在是 Windows [按需功能](https://docs.microsoft.com/windows-hardware/manufacture/desktop/features-on-demand-v2--capabilities) \(FoD\) 使在 Microsoft Edge 中自动测试并获取适合你的设备的版本变得更加简单。</span><span class="sxs-lookup"><span data-stu-id="f0d8f-155">WebDriver is now a [Windows Feature on Demand](https://docs.microsoft.com/windows-hardware/manufacture/desktop/features-on-demand-v2--capabilities) \(FoD\) making it easier than ever to automate testing in Microsoft Edge and get the right version for your device.</span></span>  <span data-ttu-id="f0d8f-156">安装 WebDriver 时，你不再需要手动匹配内部版本/分支/风格 [，WebDriver](https://www.w3.org/TR/webdriver) 将自动更新以匹配任何新的 Windows 10 更新。</span><span class="sxs-lookup"><span data-stu-id="f0d8f-156">You will no longer need to match the build/branch/flavor manually when installing WebDriver, your [WebDriver](https://www.w3.org/TR/webdriver) will automatically update to match any new Windows 10 updates.</span></span>  

<span data-ttu-id="f0d8f-157">可以通过打开开发人员模式来安装 WebDriver，或者通过访问"设置应用应用"&" 功能以  >    >  **独立**  >  **方式安装它**。</span><span class="sxs-lookup"><span data-stu-id="f0d8f-157">You can install WebDriver by turning on Developer Mode, or install it as a standalone by going to **Settings** > **Apps** > **Apps & features** > **Manage optional features**.</span></span>  <span data-ttu-id="f0d8f-158">有关详细信息，请查看 Windows 博客网站上 [WebDriver 公告](https://blogs.windows.com/msedgedev/2018/06/14/webdriver-w3c-recommendation-feature-on-demand)。</span><span class="sxs-lookup"><span data-stu-id="f0d8f-158">For more information, check out the [WebDriver announcement on the Windows Blog site](https://blogs.windows.com/msedgedev/2018/06/14/webdriver-w3c-recommendation-feature-on-demand).</span></span>  

### <a name="web-notification-properties"></a><span data-ttu-id="f0d8f-159">Web 通知属性</span><span class="sxs-lookup"><span data-stu-id="f0d8f-159">Web Notification properties</span></span>  

<span data-ttu-id="f0d8f-160">Web 通知现在支持四个新属性：[操作](https://developer.mozilla.org/docs/Web/API/notification/actions)、锁屏[提醒](https://developer.mozilla.org/docs/Web/API/notification/badge)、图像和，提高了我们在 Web 上创建与现有通知系统兼容的通知的能力，同时保持独立于[](https://developer.mozilla.org/docs/Web/API/notification/image) `maxActions` 平台。</span><span class="sxs-lookup"><span data-stu-id="f0d8f-160">Four new properties are now supported for web notifications:  [actions](https://developer.mozilla.org/docs/Web/API/notification/actions), [badge](https://developer.mozilla.org/docs/Web/API/notification/badge), [image](https://developer.mozilla.org/docs/Web/API/notification/image), and  `maxActions`, improving our ability to create notifications on the web that are compatible with existing notification systems, while remaining platform-independent.</span></span>  

### <a name="webview"></a><span data-ttu-id="f0d8f-161">WebView</span><span class="sxs-lookup"><span data-stu-id="f0d8f-161">WebView</span></span>  

#### <a name="service-workers"></a><span data-ttu-id="f0d8f-162">服务工作者</span><span class="sxs-lookup"><span data-stu-id="f0d8f-162">Service workers</span></span>  

<span data-ttu-id="f0d8f-163">[除了 Microsoft](https://developer.mozilla.org/docs/Web/API/Service_Worker_API) Edge 浏览器和 Windows 10 JavaScript 应用之外，WebView 控件现在还支持服务工作者。</span><span class="sxs-lookup"><span data-stu-id="f0d8f-163">[Service workers](https://developer.mozilla.org/docs/Web/API/Service_Worker_API) are now supported in the WebView control, in addition to the Microsoft Edge browser and Windows 10 JavaScript apps.</span></span>  <span data-ttu-id="f0d8f-164">所有版本的 Microsoft Edge webview \([PWA、](/microsoft-edge/hosting/webview) [UWP](/uwp/api/Windows.UI.Xaml.Controls.WebView)、 [Win32](/windows/communitytoolkit/controls/wpf-winforms/webview)\) 支持服务工作人员，但请注意，推送 [API](https://developer.mozilla.org/docs/Web/API/Push_API) 尚不适用于 UWP 和 Win32 版本。</span><span class="sxs-lookup"><span data-stu-id="f0d8f-164">All flavors of the Microsoft Edge webview \([PWA](/microsoft-edge/hosting/webview), [UWP](/uwp/api/Windows.UI.Xaml.Controls.WebView), [Win32](/windows/communitytoolkit/controls/wpf-winforms/webview)\) support service workers, however please be aware that the [Push API](https://developer.mozilla.org/docs/Web/API/Push_API) is not yet available for the UWP and Win32 versions.</span></span>  

<span data-ttu-id="f0d8f-165">x64 应用体系结构需要中性 \(任何 CPU\) 或 x64 程序包，因为服务工作者在 WoW64 进程中不受支持。</span><span class="sxs-lookup"><span data-stu-id="f0d8f-165">x64 app architectures require Neutral \(Any CPU\) or x64 packages, as service workers are not supported in WoW64 processes.</span></span>  <span data-ttu-id="f0d8f-166">\(若要节省磁盘空间，所需的 DLL 的 WoW 版本未本机包含在 Windows 中。\) </span><span class="sxs-lookup"><span data-stu-id="f0d8f-166">\(To conserve disk space, the WoW version of the required DLLs are not natively included in Windows.\)</span></span>  

#### <a name="win32-webview-updates"></a><span data-ttu-id="f0d8f-167">Win32 WebView 更新</span><span class="sxs-lookup"><span data-stu-id="f0d8f-167">Win32 WebView updates</span></span>  

<span data-ttu-id="f0d8f-168">适用于 Windows 桌面版 \(Win32\) 应用的 EdgeHTML [WebViewControl](/windows/communitytoolkit/controls/wpf-winforms/webview)已更新为多个新功能，包括能够在页面上任何其他脚本运行 \([AddInitializeScript](/uwp/api/windows.web.ui.interop.webviewcontrol.addinitializescript)\) 之前在页面加载时注入脚本，并知道特定 WebViewControl 何时接收或失去焦点 \([GotFocus](/uwp/api/windows.web.ui.interop.webviewcontrol.gotfocus) / [LostFocus](/uwp/api/windows.web.ui.interop.webviewcontrol.lostfocus)\) 。</span><span class="sxs-lookup"><span data-stu-id="f0d8f-168">The EdgeHTML [WebViewControl](/windows/communitytoolkit/controls/wpf-winforms/webview) for Windows desktop \(Win32\) apps has been updated with several new features, including the ability to inject script upon page load before any other scripts on the page are run \([AddInitializeScript](/uwp/api/windows.web.ui.interop.webviewcontrol.addinitializescript)\) and know when a particular WebViewControl receives or loses focus \([GotFocus](/uwp/api/windows.web.ui.interop.webviewcontrol.gotfocus)/[LostFocus](/uwp/api/windows.web.ui.interop.webviewcontrol.lostfocus)\).</span></span>  

<span data-ttu-id="f0d8f-169">此外，你现在可以创建一个新的 WebViewControl 作为从 [window.open 打开的窗口](https://developer.mozilla.org/docs/Web/API/Window/open)。</span><span class="sxs-lookup"><span data-stu-id="f0d8f-169">Additionally, you can now create a new WebViewControl as the opened window from [window.open](https://developer.mozilla.org/docs/Web/API/Window/open).</span></span>  <span data-ttu-id="f0d8f-170">当 WebViewControl 中的脚本调用 window.open 时 [，NewWindowRequested](/uwp/api/windows.web.ui.iwebviewcontrol.newwindowrequested) 事件仍通知应用，但使用 EdgeHTML 18，其 [NewWindowRequestedEventArgs](/uwp/api/windows.web.ui.webviewcontrolnewwindowrequestedeventargs) 包含延迟 \([GetDeferral](/uwp/api/windows.web.ui.webviewcontrolnewwindowrequestedeventargs.getdeferral)\) 以将新的 WebViewControl \([NewWindow](/uwp/api/windows.web.ui.webviewcontrolnewwindowrequestedeventargs.newwindow)\) 设置为窗口的目标的能力。打开：</span><span class="sxs-lookup"><span data-stu-id="f0d8f-170">The [NewWindowRequested](/uwp/api/windows.web.ui.iwebviewcontrol.newwindowrequested) event still notifies an app when script inside the WebViewControl calls window.open as it always has, but with EdgeHTML 18 its [NewWindowRequestedEventArgs](/uwp/api/windows.web.ui.webviewcontrolnewwindowrequestedeventargs) include the ability to take a deferral \([GetDeferral](/uwp/api/windows.web.ui.webviewcontrolnewwindowrequestedeventargs.getdeferral)\) in order to set a new WebViewControl \([NewWindow](/uwp/api/windows.web.ui.webviewcontrolnewwindowrequestedeventargs.newwindow)\) as the target for the window.open:</span></span>  

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

<span data-ttu-id="f0d8f-171">最后，Power 用户可能会注意到桌面应用程序 Web 查看器 \(以前名为 Win32WebViewHost\) （表示 Win32 WebView 的内部系统应用）在下列位置的应用：</span><span class="sxs-lookup"><span data-stu-id="f0d8f-171">Lastly, power users might notice the apppearance of the Desktop App Web Viewer \(previously named Win32WebViewHost\), an internal system app representing the Win32 WebView, in the following places:</span></span>  

*   <span data-ttu-id="f0d8f-172">在 Windows 10 操作中心。</span><span class="sxs-lookup"><span data-stu-id="f0d8f-172">In the Windows 10 Action Center.</span></span>  <span data-ttu-id="f0d8f-173">这些通知的来源应理解为从 Win32 应用托管的 WebView。</span><span class="sxs-lookup"><span data-stu-id="f0d8f-173">The source of these notifications should be understood as from a WebView hosted from a Win32 app.</span></span>  
*   <span data-ttu-id="f0d8f-174">在设备访问设置 UI \(`Settings`  >  `Privacy`  >  `Camera/Location/Microphone` \) 。</span><span class="sxs-lookup"><span data-stu-id="f0d8f-174">In the device access settings UI \(`Settings` > `Privacy` > `Camera/Location/Microphone`\).</span></span>  <span data-ttu-id="f0d8f-175">禁用其中任何设置将拒绝从 Win32 应用中托管的所有 WebView 访问。</span><span class="sxs-lookup"><span data-stu-id="f0d8f-175">Disabling any of these settings denies access from all WebViews hosted in Win32 apps.</span></span>  

![桌面应用 Web 查看器设备访问设置](./media/desktop-app-web-viewer.png)  

## <a name="deprecated-features"></a><span data-ttu-id="f0d8f-177">已否决的功能</span><span class="sxs-lookup"><span data-stu-id="f0d8f-177">Deprecated features</span></span>  

### <a name="xss-filter-now-retired"></a><span data-ttu-id="f0d8f-178">XSS 筛选器现已停用</span><span class="sxs-lookup"><span data-stu-id="f0d8f-178">XSS Filter now retired</span></span>  

<span data-ttu-id="f0d8f-179">使用 EdgeHTML 18，我们将在 Microsoft Edge 中停用 XSS 筛选器。</span><span class="sxs-lookup"><span data-stu-id="f0d8f-179">With EdgeHTML 18, we are retiring the XSS filter in Microsoft Edge.</span></span>  <span data-ttu-id="f0d8f-180">由于内容安全策略 [ (CSP) ](https://developer.mozilla.org/docs/Web/HTTP/CSP)等现代标准，我们的客户仍受到保护，这些标准提供了更强大的、高性能的安全机制，可抵御内容注入攻击，同时在新式浏览器中实现高兼容性。</span><span class="sxs-lookup"><span data-stu-id="f0d8f-180">Our customers remain protected thanks to modern standards like [Content Security Policy (CSP)](https://developer.mozilla.org/docs/Web/HTTP/CSP), which provide more powerful, performant, and secure mechanisms to protect against content injection attacks, with high compatibility across modern browsers.</span></span>  

## <a name="new-apis-in-edgehtml-18"></a><span data-ttu-id="f0d8f-181">EdgeHTML 18 中的新 API</span><span class="sxs-lookup"><span data-stu-id="f0d8f-181">New APIs in EdgeHTML 18</span></span>  

<span data-ttu-id="f0d8f-182">查看 EdgeHTML 18 中新 API 的完整列表。</span><span class="sxs-lookup"><span data-stu-id="f0d8f-182">Check out the full list of new APIs in EdgeHTML 18.</span></span>  <span data-ttu-id="f0d8f-183">它们以 [接口名称] 的格式列出。[api 名称]。</span><span class="sxs-lookup"><span data-stu-id="f0d8f-183">They are listed in the format of [interface name].[api name].</span></span>  

> [!NOTE] 
> <span data-ttu-id="f0d8f-184">尽管以下 API 在 DOM 中公开，但某些 API 的端到端行为可能仍在开发中，并且隐藏在实验标志后面。</span><span class="sxs-lookup"><span data-stu-id="f0d8f-184">Although the following APIs are exposed in the DOM, the end-to-end behavior of some might still be in development and hidden behind an experimental flag.</span></span>  <span data-ttu-id="f0d8f-185">有关  [功能支持的官方](https://developer.microsoft.com/microsoft-edge/platform/status/) 词，请参阅 Microsoft Edge 平台状态。</span><span class="sxs-lookup"><span data-stu-id="f0d8f-185">Refer to  [Microsoft Edge platform status](https://developer.microsoft.com/microsoft-edge/platform/status/) for the official word on feature support.</span></span>  

<iframe height='580' scrolling='no' title='<span data-ttu-id="f0d8f-186">EdgeHTML 18 中的新 API</span><span class="sxs-lookup"><span data-stu-id="f0d8f-186">New APIs in EdgeHTML 18</span></span>' src='//codepen.io/MSEdgeDev/embed/5d7be9404d82575162b486e79d0dd58f
/?height=608&theme-id=23401&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'><span data-ttu-id="f0d8f-187">请参阅 <a href='https://codepen.io/MSEdgeDev/pen/5d7be9404d82575162b486e79d0dd58f'> CodePen 上由 </a> MSEdgeDev (@MSEdgeDev) EdgeHTML 18 <a href='https://codepen.io/MSEdgeDev'> 中的笔新 </a> <a href='https://codepen.io'> </a> API。</span><span class="sxs-lookup"><span data-stu-id="f0d8f-187">See the Pen <a href='https://codepen.io/MSEdgeDev/pen/5d7be9404d82575162b486e79d0dd58f'>New APIs in EdgeHTML 18</a> by MSEdgeDev (<a href='https://codepen.io/MSEdgeDev'>@MSEdgeDev</a>) on <a href='https://codepen.io'>CodePen</a>.</span></span></iframe>  

## <a name="previous-edgehtml-releases"></a><span data-ttu-id="f0d8f-188">以前的 EdgeHTML 版本</span><span class="sxs-lookup"><span data-stu-id="f0d8f-188">Previous EdgeHTML releases</span></span>  

[<span data-ttu-id="f0d8f-189">EdgeHTML 13 / Windows 版本 10586 (11/2015) </span><span class="sxs-lookup"><span data-stu-id="f0d8f-189">EdgeHTML 13 / Windows build 10586 (11/2015)</span></span>](./whats-new/edgehtml-13.md)  

[<span data-ttu-id="f0d8f-190">EdgeHTML 14 /Windows 版本 14393 (2016 年 8 月 8 日) </span><span class="sxs-lookup"><span data-stu-id="f0d8f-190">EdgeHTML 14 / Windows build 14393 (8/2016)</span></span>](./whats-new/edgehtml-14.md)  

[<span data-ttu-id="f0d8f-191">EdgeHTML 15 /Windows 版本 15063 (2017 年 4 月 4 日) </span><span class="sxs-lookup"><span data-stu-id="f0d8f-191">EdgeHTML 15 / Windows build 15063 (4/2017)</span></span>](./whats-new/edgehtml-15.md)  

[<span data-ttu-id="f0d8f-192">EdgeHTML 16 / Windows 版本 16299 (10/2017) </span><span class="sxs-lookup"><span data-stu-id="f0d8f-192">EdgeHTML 16 / Windows build 16299 (10/2017)</span></span>](./whats-new/edgehtml-16.md)  

[<span data-ttu-id="f0d8f-193">EdgeHTML 17 / Windows 版本 17134 (04/2018) </span><span class="sxs-lookup"><span data-stu-id="f0d8f-193">EdgeHTML 17 / Windows build 17134 (04/2018)</span></span>](https://aka.ms/devguide_edgehtml_17)  
