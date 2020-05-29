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
# <span data-ttu-id="5bcf2-104">Microsoft Edge 开发人员指南</span><span class="sxs-lookup"><span data-stu-id="5bcf2-104">Microsoft Edge Developer Guide</span></span>

> [!TIP]
> <span data-ttu-id="5bcf2-105">我们已与其他浏览器和 web 社区[合作](https://blogs.windows.com/msedgedev/2017/10/18/documenting-web-together-mdn-web-docs/)，采用[MDN web 文档](https://developer.mozilla.org/)作为针对当前和新兴的基于标准的 web 技术的有用、无偏差、不限浏览器的文档。</span><span class="sxs-lookup"><span data-stu-id="5bcf2-105">We've [partnered](https://blogs.windows.com/msedgedev/2017/10/18/documenting-web-together-mdn-web-docs/) with other browsers and the web community in adopting [MDN Web Docs](https://developer.mozilla.org/) as the definitive place for useful, unbiased, browser-agnostic documentation for current and emerging standards-based web technologies.</span></span> <span data-ttu-id="5bcf2-106">你可以直接在[MDN web 引用库](https://developer.mozilla.org/docs/Web)的每个页面中找到有关 EdgeHTML API 支持的详细信息。</span><span class="sxs-lookup"><span data-stu-id="5bcf2-106">You can find details about EdgeHTML API support directly in each page of the [MDN web reference library](https://developer.mozilla.org/docs/Web).</span></span> <span data-ttu-id="5bcf2-107">有关 Microsoft Edge 中支持的最新功能，请访问 Microsoft Edge 的[平台状态](https://developer.microsoft.com/microsoft-edge/platform/status/?q=edge%3AShipped%20edge%3APrefixed%20edge%3A'Preview%20Release)。</span><span class="sxs-lookup"><span data-stu-id="5bcf2-107">Visit Microsoft Edge's [Platform status](https://developer.microsoft.com/microsoft-edge/platform/status/?q=edge%3AShipped%20edge%3APrefixed%20edge%3A'Preview%20Release) for the latest features supported in Microsoft Edge.</span></span> 


## <span data-ttu-id="5bcf2-108">EdgeHTML 18 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="5bcf2-108">What's new in EdgeHTML 18</span></span>

<span data-ttu-id="5bcf2-109">EdgeHTML 18 包含当前版本的 Microsoft Edge 平台（从[Windows 10 年10月2018更新](/windows/uwp/whats-new/windows-10-build-17763)（10/2018，内部版本17763）推出的以下新增和更新功能。</span><span class="sxs-lookup"><span data-stu-id="5bcf2-109">EdgeHTML 18 includes the following new and updated features shipped in the current release of the Microsoft Edge platform, as of the [Windows 10 October 2018 Update](/windows/uwp/whats-new/windows-10-build-17763) (10/2018, Build 17763).</span></span> <span data-ttu-id="5bcf2-110">有关特定 Windows 预览[体验计划](https://insider.windows.com/)预览版中的更改，请参阅[Microsoft Edge Changelog](https://developer.microsoft.com/microsoft-edge/platform/changelog/)和[EdgeHTML 中的新增功能](./dev-guide/whats-new.md)。</span><span class="sxs-lookup"><span data-stu-id="5bcf2-110">For changes in specific [Windows Insider](https://insider.windows.com/) Preview builds, see the [Microsoft Edge Changelog](https://developer.microsoft.com/microsoft-edge/platform/changelog/) and [What's New in EdgeHTML](./dev-guide/whats-new.md).</span></span>

<span data-ttu-id="5bcf2-111">下面是以下更改列表的固定链接： [https://aka.ms/devguide_edgehtml_18](https://aka.ms/devguide_edgehtml_18) 。</span><span class="sxs-lookup"><span data-stu-id="5bcf2-111">Here's the permalink for the following list of changes: [https://aka.ms/devguide_edgehtml_18](https://aka.ms/devguide_edgehtml_18).</span></span>

## <span data-ttu-id="5bcf2-112">新增功能和更新功能</span><span class="sxs-lookup"><span data-stu-id="5bcf2-112">New and updated features</span></span>

### <span data-ttu-id="5bcf2-113">自动播放策略</span><span class="sxs-lookup"><span data-stu-id="5bcf2-113">Autoplay policies</span></span>

<span data-ttu-id="5bcf2-114">通过 Windows 10 2018 年10月的更新，Microsoft Edge 使客户能够在网站上个性化浏览首选项，以便在 web 上自动播放媒体，以便最大限度地减少 web 上的干扰并节省带宽。</span><span class="sxs-lookup"><span data-stu-id="5bcf2-114">With the Windows 10 October 2018 Update, Microsoft Edge provides customers with the ability to personalize their browsing preferences on websites that autoplay media with sound in order to minimize distractions on the web and conserve bandwidth.</span></span> <span data-ttu-id="5bcf2-115">用户可以通过全局自动播放控件和每个网站的 "自动播放" 控件自定义媒体行为。</span><span class="sxs-lookup"><span data-stu-id="5bcf2-115">Users can customize media behavior with both global and per-site autoplay controls.</span></span> <span data-ttu-id="5bcf2-116">此外，Microsoft Edge 会自动取消自动播放后台选项卡中的媒体。</span><span class="sxs-lookup"><span data-stu-id="5bcf2-116">Additionally, Microsoft Edge automatically suppresses autoplay of media in background tabs.</span></span>

<span data-ttu-id="5bcf2-117">查看 "[自动播放策略](./dev-guide/browser-features/autoplay-policies.md)" 指南了解详细信息和最佳做法，以确保在您的网站上托管媒体的良好用户体验。</span><span class="sxs-lookup"><span data-stu-id="5bcf2-117">Check out the [Autoplay policies](./dev-guide/browser-features/autoplay-policies.md) guide for details and best practices to ensure a good user experience with media hosted on your site.</span></span>

### <span data-ttu-id="5bcf2-118">Chakra 改进</span><span class="sxs-lookup"><span data-stu-id="5bcf2-118">Chakra improvements</span></span>

<span data-ttu-id="5bcf2-119">EdgeHTML 18 包括对 Chakra JavaScript 引擎的更新，以支持除性能和互操作性改进之外的新 ES 和 WASM 功能。</span><span class="sxs-lookup"><span data-stu-id="5bcf2-119">EdgeHTML 18 includes updates to the Chakra JavaScript engine to support new ES and WASM features in addition to performance and interoperability improvements.</span></span> <span data-ttu-id="5bcf2-120">有关详细信息，请查看[ChakraCore 1.11 发行说明](https://github.com/Microsoft/ChakraCore/wiki/Roadmap#chakracore-111)。</span><span class="sxs-lookup"><span data-stu-id="5bcf2-120">Check out the [ChakraCore 1.11 Release Notes](https://github.com/Microsoft/ChakraCore/wiki/Roadmap#chakracore-111) for details.</span></span>

### <span data-ttu-id="5bcf2-121">CSS 更新</span><span class="sxs-lookup"><span data-stu-id="5bcf2-121">CSS updates</span></span>

<span data-ttu-id="5bcf2-122">我们已在实验性的[Css 掩蔽](https://developer.mozilla.org/docs/Web/CSS/CSS_Masking)实现（在*启用 CSS 掩码*标志之后）进行了进一步的处理，并添加了对[遮罩-复合](https://developer.mozilla.org/docs/Web/CSS/mask-composite)、[遮罩位置](https://developer.mozilla.org/docs/Web/CSS/mask-position)和[掩码重复](https://developer.mozilla.org/docs/Web/CSS/mask-repeat)的支持。</span><span class="sxs-lookup"><span data-stu-id="5bcf2-122">We've made further progress on our experimental [CSS Masking](https://developer.mozilla.org/docs/Web/CSS/CSS_Masking) implementation (behind the *Enable CSS Masking* flag) with added support for [mask-composite](https://developer.mozilla.org/docs/Web/CSS/mask-composite), [mask-position](https://developer.mozilla.org/docs/Web/CSS/mask-position), and [mask-repeat](https://developer.mozilla.org/docs/Web/CSS/mask-repeat).</span></span> <span data-ttu-id="5bcf2-123">对于网站兼容性，Microsoft Edge 还支持以下 *-webkit-* webkit-mask、-webkit-mask、-webkit 掩码、-webkit 蒙版位置、-webkit 蒙版位置、-webkit 蒙板-"-"-"-"-"-"-"-"。</span><span class="sxs-lookup"><span data-stu-id="5bcf2-123">For site compatibility, Microsoft Edge also supports the following *-webkit-* properties: -webkit-mask, -webkit-mask-composite, -webkit-mask-image, -webkit-mask-position, -webkit-mask-position-x, -webkit-mask-position-y, -webkit-mask-repeat, -webkit-mask-size.</span></span>

<span data-ttu-id="5bcf2-124">此外，Microsoft Edge 现在支持对[overscroll](https://developer.mozilla.org/docs/Web/CSS/overscroll-behavior) （和值）进行[溢出环绕](https://developer.mozilla.org/docs/Web/CSS/overflow-wrap
)和部分支持 `auto` `contain` 。</span><span class="sxs-lookup"><span data-stu-id="5bcf2-124">Additionally, Microsoft Edge now has support for [overflow-wrap](https://developer.mozilla.org/docs/Web/CSS/overflow-wrap
) and partial support for [overscroll-behavior](https://developer.mozilla.org/docs/Web/CSS/overscroll-behavior) (`auto` and `contain` values).</span></span>


### <span data-ttu-id="5bcf2-125">开发人员工具</span><span class="sxs-lookup"><span data-stu-id="5bcf2-125">Developer Tools</span></span>

<span data-ttu-id="5bcf2-126">对 Microsoft Edge DevTools 的最新更新向 UI 添加了许多 conveniences，包括服务工作人员和存储的新专用面板、调试程序中的源代码文件搜索工具以及样式/布局调试和控制台 Api 的新的边缘 DevTools 协议域。</span><span class="sxs-lookup"><span data-stu-id="5bcf2-126">The latest update to Microsoft Edge DevTools adds a number of conveniences both to the UI and under the hood, including new dedicated panels for Service Workers and Storage, source file search tools in the Debugger, and new Edge DevTools Protocol domains for style/layout debugging and console APIs.</span></span>

<span data-ttu-id="5bcf2-127">[最新 Windows 10 更新（EdgeHTML 18）中的 DevTools](./devtools-guide/whats-new.md)具有所有详细信息。</span><span class="sxs-lookup"><span data-stu-id="5bcf2-127">[DevTools in the latest Windows 10 update (EdgeHTML 18)](./devtools-guide/whats-new.md) has all the details.</span></span>

### <span data-ttu-id="5bcf2-128">听取您的反馈</span><span class="sxs-lookup"><span data-stu-id="5bcf2-128">Listening to your feedback</span></span>

<span data-ttu-id="5bcf2-129">我们将听取你的反馈，并已实现对 EdgeHTML 18 中的多个请求 Api 的支持，包括 [`DataTransfer.setDragImage()`](https://developer.mozilla.org/docs/Web/API/DataTransfer/setDragImage) 用于在拖放时设置自定义图像的方法，以及 [`secureConnectionStart`](https://developer.mozilla.org/docs/Web/API/PerformanceResourceTiming/secureConnectionStart) 性能资源计时 API 的属性，可用于在浏览器启动握手进程以保护当前连接之前立即返回时间戳。</span><span class="sxs-lookup"><span data-stu-id="5bcf2-129">We listen to your feedback and have implemented support for several requested APIs in EdgeHTML 18, including the [`DataTransfer.setDragImage()`](https://developer.mozilla.org/docs/Web/API/DataTransfer/setDragImage) method used to set a custom image when dragging and dropping, and [`secureConnectionStart`](https://developer.mozilla.org/docs/Web/API/PerformanceResourceTiming/secureConnectionStart), a property of the Performance Resource Timing API, which can be used for returning a timestamp immediately before the browser starts the handshake process to secure the current connection.</span></span> 

<span data-ttu-id="5bcf2-130">此外，没有人喜欢枚举属性集合，因此我们添加了对 [`Element.getAttributeNames`](https://developer.mozilla.org/docs/Web/API/Element/getAttributeNames) 以字符串数组的形式返回元素的属性名称的支持，以及 [`Element.toggleAttribute`](https://developer.mozilla.org/docs/Web/API/Element/toggleAttribute) 切换布尔属性（如果不存在，则删除）。</span><span class="sxs-lookup"><span data-stu-id="5bcf2-130">In addition, no one likes enumerating the attributes collection, so we've added support for [`Element.getAttributeNames`](https://developer.mozilla.org/docs/Web/API/Element/getAttributeNames) to return the attribute names of the element as an Array of strings, as well as, [`Element.toggleAttribute`](https://developer.mozilla.org/docs/Web/API/Element/toggleAttribute) to toggle a boolean attribute (removing if present and adding if not).</span></span>

### <span data-ttu-id="5bcf2-131">渐进式 Web 应用</span><span class="sxs-lookup"><span data-stu-id="5bcf2-131">Progressive Web Apps</span></span>

#### <span data-ttu-id="5bcf2-132">生存期后台脚本</span><span class="sxs-lookup"><span data-stu-id="5bcf2-132">Lifetime background script</span></span>

<span data-ttu-id="5bcf2-133">Windows 10 JavaScript 应用（在*WWAHost*进程中运行的 web 应用）现在支持在任何视图激活之前启动的可选基于应用程序后台脚本，并且在进程的持续时间内运行。</span><span class="sxs-lookup"><span data-stu-id="5bcf2-133">Windows 10 JavaScript apps (web apps running in a *WWAHost.exe* process) now support an optional per-application background script that starts before any views are activated and runs for the duration of the process.</span></span> <span data-ttu-id="5bcf2-134">通过这种方式，你可以在激活视图之前监视和修改导航、跟踪跨导航的状态、监视导航错误和运行代码。</span><span class="sxs-lookup"><span data-stu-id="5bcf2-134">With this, you can monitor and modify navigations, track state across navigations, monitor navigation errors, and run code before views are activated.</span></span> 

<span data-ttu-id="5bcf2-135">当指定为 [`StartPage`](/uwp/schemas/appxpackage/appxmanifestschema2010-v2/element-application) 你的[应用清单](/uwp/schemas/appxpackage/appx-package-manifest)中的应用时，应用的每个视图（windows）作为新类的实例公开给脚本 [`WebUIView`](/uwp/api/windows.ui.webui.webuiview) ，并提供相同的事件、属性和方法作为常规（Win32） [web 视图](/uwp/api/windows.web.ui.iwebviewcontrol)。</span><span class="sxs-lookup"><span data-stu-id="5bcf2-135">When specified as the [`StartPage`](/uwp/schemas/appxpackage/appxmanifestschema2010-v2/element-application) in your [app manifest](/uwp/schemas/appxpackage/appx-package-manifest), each of the app's views (windows) are exposed to the script as instances of the new [`WebUIView`](/uwp/api/windows.ui.webui.webuiview) class, providing the same events, properties, and methods as a general (Win32) [WebView](/uwp/api/windows.web.ui.iwebviewcontrol).</span></span> <span data-ttu-id="5bcf2-136">你的脚本可以侦听 [`NewWebUIViewCreated`](/uwp/api/windows.ui.webui.newwebuiviewcreatedeventargs) 事件以截获对新视图的导航的控制：</span><span class="sxs-lookup"><span data-stu-id="5bcf2-136">Your script can listen for the [`NewWebUIViewCreated`](/uwp/api/windows.ui.webui.newwebuiviewcreatedeventargs) event to intercept control of the navigation for a new view:</span></span>

```JavaScript
Windows.UI.WebUI.WebUIApplication.addEventListener("newwebuiviewcreated", newWebUIViewCreatedEventHandler);
```

 <span data-ttu-id="5bcf2-137">任何具有后台脚本的应用激活 `StartPage` 都将依赖脚本本身进行导航。</span><span class="sxs-lookup"><span data-stu-id="5bcf2-137">Any app activation with the background script as the `StartPage` will rely on the script itself for navigation.</span></span>

#### <span data-ttu-id="5bcf2-138">文本缩放</span><span class="sxs-lookup"><span data-stu-id="5bcf2-138">Text scaling</span></span>

<span data-ttu-id="5bcf2-139">Windows 10 月2018更新引入了 "[*使文本更大*](https://review.docs.microsoft.com/windows/uwp/design/input/text-scaling?branch=master#user-experience)" 设置以提高最终用户的可访问性，在 Windows 上安装的 PWAs （也是 UWP 和大多数桌面应用）现在可自动支持此功能。</span><span class="sxs-lookup"><span data-stu-id="5bcf2-139">The Windows 10 October 2018 Update introduces the [*Make text bigger*](https://review.docs.microsoft.com/windows/uwp/design/input/text-scaling?branch=master#user-experience) setting for improved end-user accessibility, and PWAs installed on Windows (in addition UWP and most desktop apps) now support this feature automatically.</span></span> <span data-ttu-id="5bcf2-140">对于 PWAs 和 Web 视图控件，文本缩放的工作方式与 DPI 缩放的方式相同。</span><span class="sxs-lookup"><span data-stu-id="5bcf2-140">For PWAs and WebView controls, text scale works the same way as DPI scaling.</span></span> <span data-ttu-id="5bcf2-141">如果用户同时更改了文本比例和 DPI 比例，则结果为两个的积。</span><span class="sxs-lookup"><span data-stu-id="5bcf2-141">If a user changes both text scale and DPI scale, the result is the product of the two.</span></span>

 <span data-ttu-id="5bcf2-142">有关设计指南，请查看*Windows 开发人员中心*上的[文本缩放](/windows/uwp/design/input/text-scaling)UWP 指南。</span><span class="sxs-lookup"><span data-stu-id="5bcf2-142">For design guidance, check out the [Text scaling](/windows/uwp/design/input/text-scaling) UWP guide on *Windows Dev Center*.</span></span>

### <span data-ttu-id="5bcf2-143">服务工作人员更新</span><span class="sxs-lookup"><span data-stu-id="5bcf2-143">Service Worker updates</span></span> 

<span data-ttu-id="5bcf2-144">有关服务工作人员及其工作方式的复习，请查看我们的合作伙伴在 MDN 上编写的[服务工作器 API]( https://developer.mozilla.org/docs/Web/API/Service_Worker_API)摘要。</span><span class="sxs-lookup"><span data-stu-id="5bcf2-144">For a refresher on what Service Workers are and how they work, check out the [Service Worker API]( https://developer.mozilla.org/docs/Web/API/Service_Worker_API) summary written by our partners over at MDN.</span></span>  <span data-ttu-id="5bcf2-145">EdgeHTML 18 中有多个 Microsoft Edge 支持服务工作者的更新。</span><span class="sxs-lookup"><span data-stu-id="5bcf2-145">There were several updates to Microsoft Edge supporting Service Workers in EdgeHTML 18.</span></span> <span data-ttu-id="5bcf2-146">`fetchEvent`允许服务工作者使用服务工作者 [`preloadResponse`]( https://developer.mozilla.org/docs/Web/API/FetchEvent) 承诺响应，并 [`resultingClientId`]( https://developer.mozilla.org/docs/Web/API/FetchEvent/clientId) 返回当前服务工作人员正在控制的客户端的 ID。</span><span class="sxs-lookup"><span data-stu-id="5bcf2-146">The `fetchEvent` enables the Service Worker to use [`preloadResponse`]( https://developer.mozilla.org/docs/Web/API/FetchEvent) to promise a response, and the [`resultingClientId`]( https://developer.mozilla.org/docs/Web/API/FetchEvent/clientId) to return the ID of the Client that the current service worker is controlling.</span></span>  
<span data-ttu-id="5bcf2-147">该 [`NavigationPreloadManager`]( https://developer.mozilla.org/docs/Web/API/NavigationPreloadManager) 接口提供用于管理资源预加载的方法，使你能够在服务工作人员启动时并行执行请求，避免任何时间延迟。</span><span class="sxs-lookup"><span data-stu-id="5bcf2-147">The [`NavigationPreloadManager`]( https://developer.mozilla.org/docs/Web/API/NavigationPreloadManager) interface provides methods for managing the preloading of resources, allowing you to make a request in parallel while a service worker is booting-up, avoiding any time delay.</span></span> <span data-ttu-id="5bcf2-148">查看[新支持的 API 属性](#new-apis-in-edgehtml-18)，了解服务工作人员预加载方法和属性的列表。</span><span class="sxs-lookup"><span data-stu-id="5bcf2-148">Check out the [newly supported API properties](#new-apis-in-edgehtml-18) for the list of Service Worker preload methods and properties.</span></span> 

### <span data-ttu-id="5bcf2-149">Web 身份验证</span><span class="sxs-lookup"><span data-stu-id="5bcf2-149">Web Authentication</span></span>

<span data-ttu-id="5bcf2-150">Microsoft Edge 现已[为新的 Web 身份验证 API](https://blogs.windows.com/msedgedev/2018/07/30/introducing-web-authentication-microsoft-edge/) （也称为 " [WebAuthN](https://w3c.github.io/webauthn/)"）提供 unprefixed 支持。</span><span class="sxs-lookup"><span data-stu-id="5bcf2-150">Microsoft Edge now includes [unprefixed support for the new Web Authentication API](https://blogs.windows.com/msedgedev/2018/07/30/introducing-web-authentication-microsoft-edge/) (aka [WebAuthN](https://w3c.github.io/webauthn/)).</span></span> <span data-ttu-id="5bcf2-151">Web 身份验证提供了一个开放、可伸缩且可互操作的解决方案，可简化身份验证，通过使用更强大的硬件绑定凭据替换密码来实现更好、更安全的用户体验。</span><span class="sxs-lookup"><span data-stu-id="5bcf2-151">Web Authentication provides an open, scalable, and interoperable solution to simplify authentication, enabling better and more secure user experiences by replacing passwords with stronger hardware-bound credentials.</span></span> <span data-ttu-id="5bcf2-152">Microsoft Edge 中的实现允许使用[Windows Hello](https://www.microsoft.com/windows/windows-hello) ，除了[外部 AUTHENTICATORS](https://fidoalliance.org) （如 FIDO2 安全密钥或 FIDO U2F 安全密钥）之外，还可让用户使用其表面、指纹或 PIN 进行登录，以安全地向网站进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="5bcf2-152">The implementation in Microsoft Edge allows the use of [Windows Hello](https://www.microsoft.com/windows/windows-hello) enabling users to sign in with their face, fingerprint, or PIN, in addition to [external authenticators](https://fidoalliance.org) like FIDO2 Security Keys or FIDO U2F Security Keys, to securely authenticate to websites.</span></span>

<span data-ttu-id="5bcf2-153">有关详细信息，请转到博客文章[在 Microsoft Edge 中引入 Web 身份验证](https://blogs.windows.com/msedgedev/2018/07/30/introducing-web-authentication-microsoft-edge)。</span><span class="sxs-lookup"><span data-stu-id="5bcf2-153">For more information, head over to the blog post [Introducing Web Authentication in Microsoft Edge](https://blogs.windows.com/msedgedev/2018/07/30/introducing-web-authentication-microsoft-edge).</span></span>

### <span data-ttu-id="5bcf2-154">WebDriver</span><span class="sxs-lookup"><span data-stu-id="5bcf2-154">WebDriver</span></span>

<span data-ttu-id="5bcf2-155">WebDriver 现在是一种[Windows 功能的点播](https://docs.microsoft.com/windows-hardware/manufacture/desktop/features-on-demand-v2--capabilities)（FoD），使你可以比以往更轻松地在 Microsoft Edge 中自动化测试并为你的设备获取正确的版本。</span><span class="sxs-lookup"><span data-stu-id="5bcf2-155">WebDriver is now a [Windows Feature on Demand](https://docs.microsoft.com/windows-hardware/manufacture/desktop/features-on-demand-v2--capabilities) (FoD) making it easier than ever to automate testing in Microsoft Edge and get the right version for your device.</span></span> <span data-ttu-id="5bcf2-156">在安装 WebDriver 时，你将不再需要手动匹配 "生成/分支/风格"，你的[WebDriver](https://www.w3.org/TR/webdriver)将自动更新以匹配任何新的 Windows 10 更新。</span><span class="sxs-lookup"><span data-stu-id="5bcf2-156">You will no longer need to match the build/branch/flavor manually when installing WebDriver, your [WebDriver](https://www.w3.org/TR/webdriver) will automatically update to match any new Windows 10 updates.</span></span> 

<span data-ttu-id="5bcf2-157">你可以通过启用开发人员模式来安装 WebDriver，也可以通过转到 > 应用 > 应用 & 功能 > 管理可选功能来安装它。</span><span class="sxs-lookup"><span data-stu-id="5bcf2-157">You can install WebDriver by turning on Developer Mode, or install it as a standalone by going to Settings > Apps > Apps & features > Manage optional features.</span></span> <span data-ttu-id="5bcf2-158">有关详细信息，请查看[Windows 博客网站上的 WebDriver 公告](https://blogs.windows.com/msedgedev/2018/06/14/webdriver-w3c-recommendation-feature-on-demand)。</span><span class="sxs-lookup"><span data-stu-id="5bcf2-158">For more information, check out the [WebDriver announcement on the Windows Blog site](https://blogs.windows.com/msedgedev/2018/06/14/webdriver-w3c-recommendation-feature-on-demand).</span></span>

### <span data-ttu-id="5bcf2-159">Web 通知属性</span><span class="sxs-lookup"><span data-stu-id="5bcf2-159">Web Notification properties</span></span>
<span data-ttu-id="5bcf2-160">对于 web 通知，现在支持四个新属性： [`actions`](https://developer.mozilla.org/docs/Web/API/notification/actions) 、、 [`badge`](https://developer.mozilla.org/docs/Web/API/notification/badge) [`image`](https://developer.mozilla.org/docs/Web/API/notification/image) 和 `maxActions` ，提高了我们在 web 上创建与现有通知系统兼容的通知的能力，而其余平台独立于平台。</span><span class="sxs-lookup"><span data-stu-id="5bcf2-160">Four new properties are now supported for web notifications: [`actions`](https://developer.mozilla.org/docs/Web/API/notification/actions), [`badge`](https://developer.mozilla.org/docs/Web/API/notification/badge), [`image`](https://developer.mozilla.org/docs/Web/API/notification/image), and  `maxActions`, improving our ability to create notifications on the web that are compatible with existing notification systems, while remaining platform-independent.</span></span>

### <span data-ttu-id="5bcf2-161">WebView</span><span class="sxs-lookup"><span data-stu-id="5bcf2-161">WebView</span></span>

#### <span data-ttu-id="5bcf2-162">服务工作人员</span><span class="sxs-lookup"><span data-stu-id="5bcf2-162">Service workers</span></span>
<span data-ttu-id="5bcf2-163">除了 Microsoft Edge 浏览器和 Windows 10 JavaScript 应用之外，"Web 视图" 控件中现在还支持[服务工作人员](https://developer.mozilla.org/docs/Web/API/Service_Worker_API)。</span><span class="sxs-lookup"><span data-stu-id="5bcf2-163">[Service workers](https://developer.mozilla.org/docs/Web/API/Service_Worker_API) are now supported in the WebView control, in addition to the Microsoft Edge browser and Windows 10 JavaScript apps.</span></span> <span data-ttu-id="5bcf2-164">Microsoft Edge web Edge （[PWA](/microsoft-edge/hosting/webview)、 [UWP](/uwp/api/Windows.UI.Xaml.Controls.WebView)、 [Win32](/windows/communitytoolkit/controls/wpf-winforms/webview)）支持服务工作人员的各种风格，但是请注意，对于 UWP 和 Win32 版本， [Push API](https://developer.mozilla.org/docs/Web/API/Push_API)尚不可用。</span><span class="sxs-lookup"><span data-stu-id="5bcf2-164">All flavors of the Microsoft Edge webview ([PWA](/microsoft-edge/hosting/webview), [UWP](/uwp/api/Windows.UI.Xaml.Controls.WebView), [Win32](/windows/communitytoolkit/controls/wpf-winforms/webview)) support service workers, however please be aware that the [Push API](https://developer.mozilla.org/docs/Web/API/Push_API) is not yet available for the UWP and Win32 versions.</span></span>

<span data-ttu-id="5bcf2-165">x64 应用体系结构需要*中立*（任何 CPU）或*x64*程序包，因为 WoW64 进程不支持服务工作人员。</span><span class="sxs-lookup"><span data-stu-id="5bcf2-165">x64 app architectures require *Neutral* (Any CPU) or *x64* packages, as service workers are not supported in WoW64 processes.</span></span> <span data-ttu-id="5bcf2-166">（为节省磁盘空间，所需 Dll 的 WoW 版本不是本机包含在 Windows 中。）</span><span class="sxs-lookup"><span data-stu-id="5bcf2-166">(To conserve disk space, the WoW version of the required DLLs are not natively included in Windows.)</span></span>

#### <span data-ttu-id="5bcf2-167">Win32 Web 视图更新</span><span class="sxs-lookup"><span data-stu-id="5bcf2-167">Win32 WebView updates</span></span>

<span data-ttu-id="5bcf2-168">Windows desktop （Win32）应用的 EdgeHTML [WebViewControl](/windows/communitytoolkit/controls/wpf-winforms/webview)已使用多个新功能进行了更新，包括在页面加载时插入脚本的功能（ [`AddInitializeScript`](/uwp/api/windows.web.ui.interop.webviewcontrol.addinitializescript) ），并知道特定 WebViewControl 何时接收或失去焦点（） [`GotFocus`](/uwp/api/windows.web.ui.interop.webviewcontrol.gotfocus) / [`LostFocus`](/uwp/api/windows.web.ui.interop.webviewcontrol.lostfocus) 。</span><span class="sxs-lookup"><span data-stu-id="5bcf2-168">The EdgeHTML [WebViewControl](/windows/communitytoolkit/controls/wpf-winforms/webview) for Windows desktop (Win32) apps has been updated with several new features, including the ability to inject script upon page load before any other scripts on the page are run ([`AddInitializeScript`](/uwp/api/windows.web.ui.interop.webviewcontrol.addinitializescript)) and know when a particular WebViewControl receives or loses focus ([`GotFocus`](/uwp/api/windows.web.ui.interop.webviewcontrol.gotfocus)/[`LostFocus`](/uwp/api/windows.web.ui.interop.webviewcontrol.lostfocus)).</span></span>

<span data-ttu-id="5bcf2-169">此外，您现在可以创建新的 WebViewControl 作为打开的窗口 [`window.open`](https://developer.mozilla.org/docs/Web/API/Window/open) 。</span><span class="sxs-lookup"><span data-stu-id="5bcf2-169">Additionally, you can now create a new WebViewControl as the opened window from [`window.open`](https://developer.mozilla.org/docs/Web/API/Window/open).</span></span> <span data-ttu-id="5bcf2-170">[`NewWindowRequested`](/uwp/api/windows.web.ui.iwebviewcontrol.newwindowrequested)当 WebViewControl 调用窗口中的脚本时，该事件仍会通知应用。按原样打开，但对于 EdgeHTML 18，它 [`NewWindowRequestedEventArgs`](/uwp/api/windows.web.ui.webviewcontrolnewwindowrequestedeventargs) 包括可以采取延迟（）的能力，以便 [`GetDeferral`](/uwp/api/windows.web.ui.webviewcontrolnewwindowrequestedeventargs.getdeferral) 将新的 WebViewControl （）设置 [`NewWindow`](/uwp/api/windows.web.ui.webviewcontrolnewwindowrequestedeventargs.newwindow) 为窗口的目标。打开：</span><span class="sxs-lookup"><span data-stu-id="5bcf2-170">The [`NewWindowRequested`](/uwp/api/windows.web.ui.iwebviewcontrol.newwindowrequested) event still notifies an app when script inside the WebViewControl calls window.open as it always has, but with EdgeHTML 18 its [`NewWindowRequestedEventArgs`](/uwp/api/windows.web.ui.webviewcontrolnewwindowrequestedeventargs) include the ability to take a deferral ([`GetDeferral`](/uwp/api/windows.web.ui.webviewcontrolnewwindowrequestedeventargs.getdeferral)) in order to set a new WebViewControl ([`NewWindow`](/uwp/api/windows.web.ui.webviewcontrolnewwindowrequestedeventargs.newwindow)) as the target for the window.open:</span></span>

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

<span data-ttu-id="5bcf2-171">最后，power users 可能会注意到*桌面应用 Web Viewer*的 apppearance （以前称为*Win32WebViewHost*），这是一个内部系统应用，表示 Win32 web 视图，位于以下位置：</span><span class="sxs-lookup"><span data-stu-id="5bcf2-171">Lastly, power users might notice the apppearance of the *Desktop App Web Viewer* (previously named *Win32WebViewHost*), an internal system app representing the Win32 WebView, in the following places:</span></span>
- <span data-ttu-id="5bcf2-172">在*Windows 10 操作中心*中。</span><span class="sxs-lookup"><span data-stu-id="5bcf2-172">In the *Windows 10 Action Center*.</span></span> <span data-ttu-id="5bcf2-173">应从 Win32 应用托管的 Web 视图中理解这些通知的来源。</span><span class="sxs-lookup"><span data-stu-id="5bcf2-173">The source of these notifications should be understood as from a WebView hosted from a Win32 app.</span></span>
- <span data-ttu-id="5bcf2-174">在 "设备访问设置" UI （*设置->隐私->相机/位置/麦克风*）中。</span><span class="sxs-lookup"><span data-stu-id="5bcf2-174">In the device access settings UI (*Settings->Privacy->Camera/Location/Microphone*).</span></span> <span data-ttu-id="5bcf2-175">禁用任何这些设置将拒绝在 Win32 应用中托管的所有 WebViews 的访问权限。</span><span class="sxs-lookup"><span data-stu-id="5bcf2-175">Disabling any of these settings denies access from all WebViews hosted in Win32 apps.</span></span>

![桌面应用程序 Web 查看器设备访问设置](./dev-guide/media/desktop-app-web-viewer.png)


## <span data-ttu-id="5bcf2-177">已否决的功能</span><span class="sxs-lookup"><span data-stu-id="5bcf2-177">Deprecated features</span></span>

### <span data-ttu-id="5bcf2-178">XSS 筛选器现已停用</span><span class="sxs-lookup"><span data-stu-id="5bcf2-178">XSS Filter now retired</span></span>

<span data-ttu-id="5bcf2-179">通过 EdgeHTML 18，我们将在 Microsoft Edge 中停用 XSS 筛选器。</span><span class="sxs-lookup"><span data-stu-id="5bcf2-179">With EdgeHTML 18, we are retiring the XSS filter in Microsoft Edge.</span></span> <span data-ttu-id="5bcf2-180">我们的客户因[内容安全政策（CSP）](https://developer.mozilla.org/docs/Web/HTTP/CSP)等新式标准而保持受保护，它提供了更强大、性能和安全的机制来防止内容注入式攻击，并且在新式浏览器中具有高兼容性。</span><span class="sxs-lookup"><span data-stu-id="5bcf2-180">Our customers remain protected thanks to modern standards like [Content Security Policy (CSP)](https://developer.mozilla.org/docs/Web/HTTP/CSP), which provide more powerful, performant, and secure mechanisms to protect against content injection attacks, with high compatibility across modern browsers.</span></span>

## <span data-ttu-id="5bcf2-181">EdgeHTML 18 中的新 Api</span><span class="sxs-lookup"><span data-stu-id="5bcf2-181">New APIs in EdgeHTML 18</span></span>

<span data-ttu-id="5bcf2-182">查看 EdgeHTML 18 中新 Api 的完整列表。</span><span class="sxs-lookup"><span data-stu-id="5bcf2-182">Check out the full list of new APIs in EdgeHTML 18.</span></span> <span data-ttu-id="5bcf2-183">它们以 [界面名称] 的格式列出。[api 名称]。</span><span class="sxs-lookup"><span data-stu-id="5bcf2-183">They are listed in the format of [interface name].[api name].</span></span>

> [!NOTE] 
> <span data-ttu-id="5bcf2-184">虽然在 DOM 中公开以下 Api，但某些 Api 的端到端行为可能仍在开发和隐藏实验标志背后。</span><span class="sxs-lookup"><span data-stu-id="5bcf2-184">Although the following APIs are exposed in the DOM, the end-to-end behavior of some might still be in development and hidden behind an experimental flag.</span></span> <span data-ttu-id="5bcf2-185">请参阅[Microsoft Edge 平台状态](https://developer.microsoft.com/microsoft-edge/platform/status/)，了解有关功能支持的官方 word 功能。</span><span class="sxs-lookup"><span data-stu-id="5bcf2-185">Refer to  [Microsoft Edge platform status](https://developer.microsoft.com/microsoft-edge/platform/status/) for the official word on feature support.</span></span>

<iframe height='580' scrolling='no' title='<span data-ttu-id="5bcf2-186">EdgeHTML 18 中的新 Api</span><span class="sxs-lookup"><span data-stu-id="5bcf2-186">New APIs in EdgeHTML 18</span></span>' src='//codepen.io/MSEdgeDev/embed/5d7be9404d82575162b486e79d0dd58f
/?height=608&theme-id=23401&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'><span data-ttu-id="5bcf2-187">在 <a href='https://codepen.io/MSEdgeDev/pen/5d7be9404d82575162b486e79d0dd58f'> </a> CodePen 上的 MSEdgeDev （@MSEdgeDev）中查看 EdgeHTML 18 中的笔新 api <a href='https://codepen.io/MSEdgeDev'> </a> <a href='https://codepen.io'> </a> 。</span><span class="sxs-lookup"><span data-stu-id="5bcf2-187">See the Pen <a href='https://codepen.io/MSEdgeDev/pen/5d7be9404d82575162b486e79d0dd58f'>New APIs in EdgeHTML 18</a> by MSEdgeDev (<a href='https://codepen.io/MSEdgeDev'>@MSEdgeDev</a>) on <a href='https://codepen.io'>CodePen</a>.</span></span></iframe>

## <span data-ttu-id="5bcf2-188">以前的 EdgeHTML 版本</span><span class="sxs-lookup"><span data-stu-id="5bcf2-188">Previous EdgeHTML releases</span></span>

[<span data-ttu-id="5bcf2-189">EdgeHTML 13/Windows 内部版本10586（11/2015）</span><span class="sxs-lookup"><span data-stu-id="5bcf2-189">EdgeHTML 13 / Windows build 10586 (11/2015)</span></span>](https://aka.ms/devguide_edgehtml_13)

[<span data-ttu-id="5bcf2-190">EdgeHTML 14/Windows 内部版本14393（8/2016）</span><span class="sxs-lookup"><span data-stu-id="5bcf2-190">EdgeHTML 14 / Windows build 14393 (8/2016)</span></span>](https://aka.ms/devguide_edgehtml_14)

[<span data-ttu-id="5bcf2-191">EdgeHTML 15/Windows 内部版本15063（4/2017）</span><span class="sxs-lookup"><span data-stu-id="5bcf2-191">EdgeHTML 15 / Windows build 15063 (4/2017)</span></span>](https://aka.ms/devguide_edgehtml_15)

[<span data-ttu-id="5bcf2-192">EdgeHTML 16/Windows 内部版本16299（10/2017）</span><span class="sxs-lookup"><span data-stu-id="5bcf2-192">EdgeHTML 16 / Windows build 16299 (10/2017)</span></span>](https://aka.ms/devguide_edgehtml_16)

[<span data-ttu-id="5bcf2-193">EdgeHTML 17/Windows 内部版本17134（04/2018）</span><span class="sxs-lookup"><span data-stu-id="5bcf2-193">EdgeHTML 17 / Windows build 17134 (04/2018)</span></span>](https://aka.ms/devguide_edgehtml_17)
