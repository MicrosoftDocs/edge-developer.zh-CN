---
description: 通过 Microsoft Edge WebView2 控件在 Win32、.NET、UWP 应用程序中托管 web 内容
title: Microsoft Edge WebView2 控件
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、CoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html、Windows 窗体、WinForms、WPF、.NET、WinUI、Project 留尼汪岛
ms.openlocfilehash: 02d17b05364f02f26a4917b65ac497156be02b2e
ms.sourcegitcommit: fab44f7e183a3c4f12bf925512fc62d84a4d6edc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/20/2020
ms.locfileid: "11182365"
---
# <span data-ttu-id="89eef-104">Microsoft Edge WebView2 简介</span><span class="sxs-lookup"><span data-stu-id="89eef-104">Introduction to Microsoft Edge WebView2</span></span>  

<span data-ttu-id="89eef-105">Microsoft Edge WebView2 控件使你能够在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript \ ) 。</span><span class="sxs-lookup"><span data-stu-id="89eef-105">The Microsoft Edge WebView2 control enables you to embed web technologies \(HTML, CSS, and JavaScript\) in your native applications.</span></span>  <span data-ttu-id="89eef-106">WebView2 控件使用 [Microsoft Edge () Chromium ][MicrosoftedgeinsiderMain] 作为呈现引擎在本机应用程序中显示 web 内容。</span><span class="sxs-lookup"><span data-stu-id="89eef-106">The WebView2 control uses [Microsoft Edge (Chromium)][MicrosoftedgeinsiderMain] as the rendering engine to display the web content in native applications.</span></span>  <span data-ttu-id="89eef-107">使用 WebView2，你可以将 web 代码嵌入本机应用程序的不同部分，或在单个 Web 视图中构建整个本机应用程序。</span><span class="sxs-lookup"><span data-stu-id="89eef-107">With WebView2, you may embed web code in different parts of your native application, or build the entire native application within a single WebView.</span></span>  <span data-ttu-id="89eef-108">有关如何开始生成 WebView2 应用程序的信息，请导航到 " [开始](#getting-started)"。</span><span class="sxs-lookup"><span data-stu-id="89eef-108">For information on how to start building a WebView2 application, navigate to [Get Started](#getting-started).</span></span>  

:::image type="complex" source="./media/WebView2/whatwebview.png" alt-text="什么是 Web 视图" lightbox="./media/WebView2/whatwebview.png":::
   <span data-ttu-id="89eef-110">什么是 Web 视图</span><span class="sxs-lookup"><span data-stu-id="89eef-110">What is WebView</span></span>  
:::image-end:::  

## <span data-ttu-id="89eef-111">混合应用程序方法</span><span class="sxs-lookup"><span data-stu-id="89eef-111">Hybrid application approach</span></span>  

<span data-ttu-id="89eef-112">开发人员通常必须决定生成 web 应用程序还是本机应用程序。</span><span class="sxs-lookup"><span data-stu-id="89eef-112">Developers often have to decide between building a web application or a native application.</span></span>  <span data-ttu-id="89eef-113">决策在接触和接通电源之间的平衡。</span><span class="sxs-lookup"><span data-stu-id="89eef-113">The decision hinges on the trade-off between reach and power.</span></span>  <span data-ttu-id="89eef-114">Web 应用程序允许广泛访问。</span><span class="sxs-lookup"><span data-stu-id="89eef-114">Web applications allow for a broad reach.</span></span>  <span data-ttu-id="89eef-115">作为 Web 开发人员，你可以在所有不同平台上重复使用大多数代码（如果不是所有代码）。</span><span class="sxs-lookup"><span data-stu-id="89eef-115">As a Web developer, you may reuse most, if not all of your code, across all different platforms.</span></span>  <span data-ttu-id="89eef-116">但是，本机应用程序利用整个本机平台的功能。</span><span class="sxs-lookup"><span data-stu-id="89eef-116">Native applications, however, utilize the capabilities of the entire native platform.</span></span>  

:::image type="complex" source="./media/WebView2/webnative.png" alt-text="Web native" lightbox="./media/WebView2/webnative.png":::
   <span data-ttu-id="89eef-118">Web native</span><span class="sxs-lookup"><span data-stu-id="89eef-118">Web native</span></span>  
:::image-end:::  

<span data-ttu-id="89eef-119">混合应用程序使开发人员能够享受这两个领域的最佳体验。</span><span class="sxs-lookup"><span data-stu-id="89eef-119">Hybrid applications allow developers to enjoy the best of both worlds.</span></span>  <span data-ttu-id="89eef-120">混合应用程序开发人员受益于 web 平台的 ubiquity 和强项，以及本机平台的强大功能和完整功能。</span><span class="sxs-lookup"><span data-stu-id="89eef-120">Hybrid application developers benefit from the ubiquity and strength of the web platform, and the power and full capabilities of the native platform.</span></span>  

## <span data-ttu-id="89eef-121">WebView2 优惠</span><span class="sxs-lookup"><span data-stu-id="89eef-121">WebView2 benefits</span></span>  

:::image type="complex" source="./media/WebView2/webviewreasons.png" alt-text="Web 视图原因" lightbox="./media/WebView2/webviewreasons.png":::
   <span data-ttu-id="89eef-123">Web 视图原因</span><span class="sxs-lookup"><span data-stu-id="89eef-123">WebView reasons</span></span>  
:::image-end:::  

:::row:::
   :::column span="1":::
      **<span data-ttu-id="89eef-124">Web 生态系统 \ & skillset</span><span class="sxs-lookup"><span data-stu-id="89eef-124">Web ecosystem \& skillset</span></span>**  
      <span data-ttu-id="89eef-125">利用 web 生态系统中存在的整个 web 平台、库、工具和人才。</span><span class="sxs-lookup"><span data-stu-id="89eef-125">Utilize the entire web platform, libraries, tooling, and talent that exists within the web ecosystem.</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="89eef-126">快速创新</span><span class="sxs-lookup"><span data-stu-id="89eef-126">Rapid innovation</span></span>**  
      <span data-ttu-id="89eef-127">Web 开发允许更快的部署和迭代。</span><span class="sxs-lookup"><span data-stu-id="89eef-127">Web development allows for faster deployment and iteration.</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="89eef-128">Windows 7、8、10支持</span><span class="sxs-lookup"><span data-stu-id="89eef-128">Windows 7, 8, 10 support</span></span>**  
      <span data-ttu-id="89eef-129">在 Windows 7、8和10上支持一致的用户体验。</span><span class="sxs-lookup"><span data-stu-id="89eef-129">Support for a consistent user experience across Windows 7, 8, and 10.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="89eef-130">本机功能</span><span class="sxs-lookup"><span data-stu-id="89eef-130">Native capabilities</span></span>**  
      <span data-ttu-id="89eef-131">访问完整的本机 Api 集。</span><span class="sxs-lookup"><span data-stu-id="89eef-131">Access the full set of Native APIs.</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="89eef-132">代码共享</span><span class="sxs-lookup"><span data-stu-id="89eef-132">Code-sharing</span></span>**  
      <span data-ttu-id="89eef-133">将 web 代码添加到你的基本代码，可在多个平台之间更好地重复使用。</span><span class="sxs-lookup"><span data-stu-id="89eef-133">Add web code to your codebase allows for increased re-use across multiple platforms.</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="89eef-134">Microsoft 支持</span><span class="sxs-lookup"><span data-stu-id="89eef-134">Microsoft support</span></span>**  
      <span data-ttu-id="89eef-135">Microsoft 在 WebView2 发布为 GA 时提供支持和添加新功能请求。</span><span class="sxs-lookup"><span data-stu-id="89eef-135">Microsoft provides support and adds new feature requests when WebView2 is release as GA.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="89eef-136">长绿分布</span><span class="sxs-lookup"><span data-stu-id="89eef-136">Evergreen distribution</span></span>**  
      <span data-ttu-id="89eef-137">通过常规的平台更新和安全修补程序依赖最新版本的 Chromium。</span><span class="sxs-lookup"><span data-stu-id="89eef-137">Rely on an up-to-date version of Chromium with regular platform updates and security patches.</span></span>  
   :::column-end:::
   :::column span="1":::
      <span data-ttu-id="89eef-138">已**修复**的 \ (即将推出 \ ) </span><span class="sxs-lookup"><span data-stu-id="89eef-138">**Fixed** \(coming soon\)</span></span>  
      <span data-ttu-id="89eef-139">选择将 Chromium 位打包在你的应用程序中。</span><span class="sxs-lookup"><span data-stu-id="89eef-139">Choose to package the Chromium bits in your application.</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="89eef-140">增量采纳</span><span class="sxs-lookup"><span data-stu-id="89eef-140">Incremental adoption</span></span>**  
      <span data-ttu-id="89eef-141">将 web 组件逐个添加到应用程序。</span><span class="sxs-lookup"><span data-stu-id="89eef-141">Add web components piece by piece to your application.</span></span>  
   :::column-end:::
:::row-end:::  

## <span data-ttu-id="89eef-142">即刻体验</span><span class="sxs-lookup"><span data-stu-id="89eef-142">Getting started</span></span>  

<span data-ttu-id="89eef-143">若要使用 WebView2 控件生成和测试你的应用程序，你需要同时安装 [Microsoft Edge (Chromium) ][MicrosoftedgeinsiderDownload] 和 [WebView2 SDK][NugetPackagesMicrosoftWebWebView2] 。</span><span class="sxs-lookup"><span data-stu-id="89eef-143">To build and test your application using the WebView2 control, you need to have both [Microsoft Edge (Chromium)][MicrosoftedgeinsiderDownload] and the [WebView2 SDK][NugetPackagesMicrosoftWebWebView2] installed.</span></span>  <span data-ttu-id="89eef-144">选择以下选项之一开始使用。</span><span class="sxs-lookup"><span data-stu-id="89eef-144">Select one of the following options to get started.</span></span>  

*   [<span data-ttu-id="89eef-145">Win32 C/c + + 入门</span><span class="sxs-lookup"><span data-stu-id="89eef-145">Getting Started with Win32 C/C++</span></span>][Webview2GettingstartedWin32]  
*   [<span data-ttu-id="89eef-146">WPF 入门</span><span class="sxs-lookup"><span data-stu-id="89eef-146">Getting Started with WPF</span></span>][Webview2GettingstartedWpf]  
*   [<span data-ttu-id="89eef-147">WinForms 入门</span><span class="sxs-lookup"><span data-stu-id="89eef-147">Getting Started with WinForms</span></span>][Webview2GettingstartedWinforms]  
*   [<span data-ttu-id="89eef-148">WinUI3 入门</span><span class="sxs-lookup"><span data-stu-id="89eef-148">Getting Started with WinUI3</span></span>][Webview2GettingstartedWinui]  

<span data-ttu-id="89eef-149">[WebView2 示例][GithubMicrosoftedgeWebview2samples]存储库包含演示所有 WebView2 SDK 功能和 API 使用模式的示例。</span><span class="sxs-lookup"><span data-stu-id="89eef-149">The [WebView2 Samples][GithubMicrosoftedgeWebview2samples] repository contains samples that demonstrate all of the WebView2 SDK features and API usage patterns.</span></span>  <span data-ttu-id="89eef-150">随着将更多功能添加到 WebView2 SDK，示例应用程序将更新。</span><span class="sxs-lookup"><span data-stu-id="89eef-150">As more features are added to the WebView2 SDK, the sample applications will be updated.</span></span>  

## <span data-ttu-id="89eef-151">支持的平台</span><span class="sxs-lookup"><span data-stu-id="89eef-151">Supported platforms</span></span>  

<span data-ttu-id="89eef-152">常规可用性 \ (GA \ ) 或预览版版本在以下编程环境中可用。</span><span class="sxs-lookup"><span data-stu-id="89eef-152">A General Availability \(GA\) or Preview version is available on the following programming environments.</span></span>  

*   <span data-ttu-id="89eef-153">Win32 C/c + + \ (GA \ ) </span><span class="sxs-lookup"><span data-stu-id="89eef-153">Win32 C/C++ \(GA\)</span></span>
*   <span data-ttu-id="89eef-154">.NET Framework 4.6.2 或更高版本</span><span class="sxs-lookup"><span data-stu-id="89eef-154">.NET Framework 4.6.2 or later</span></span>
*   <span data-ttu-id="89eef-155">.NET Core 3.1 或更高版本</span><span class="sxs-lookup"><span data-stu-id="89eef-155">.NET Core 3.1 or later</span></span>
*   <span data-ttu-id="89eef-156">.NET 5</span><span class="sxs-lookup"><span data-stu-id="89eef-156">.NET 5</span></span>
*   <span data-ttu-id="89eef-157">[WinUI 3.0][UwpToolkitsWinui3] \ (Preview \ ) </span><span class="sxs-lookup"><span data-stu-id="89eef-157">[WinUI 3.0][UwpToolkitsWinui3] \(Preview\)</span></span>

<span data-ttu-id="89eef-158">你可以在以下版本的 Windows 上运行 WebView2 应用程序。</span><span class="sxs-lookup"><span data-stu-id="89eef-158">You are able to run WebView2 applications on the following versions of Windows.</span></span>  

*   <span data-ttu-id="89eef-159">Windows 10</span><span class="sxs-lookup"><span data-stu-id="89eef-159">Windows 10</span></span>  
*   <span data-ttu-id="89eef-160">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="89eef-160">Windows 8.1</span></span>  
*   <span data-ttu-id="89eef-161">Windows 7 \ \* \ \*</span><span class="sxs-lookup"><span data-stu-id="89eef-161">Windows 7 \*\*</span></span>  
*   <span data-ttu-id="89eef-162">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="89eef-162">Windows Server 2019</span></span>  
*   <span data-ttu-id="89eef-163">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="89eef-163">Windows Server 2016</span></span>  
*   <span data-ttu-id="89eef-164">WindowsServer 2012</span><span class="sxs-lookup"><span data-stu-id="89eef-164">Windows Server 2012</span></span>  
*   <span data-ttu-id="89eef-165">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="89eef-165">Windows Server 2012 R2</span></span>  
*   <span data-ttu-id="89eef-166">Windows Server 2008 R2 \ \* \ \*</span><span class="sxs-lookup"><span data-stu-id="89eef-166">Windows Server 2008 R2 \*\*</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="89eef-167">\ \* \ \* WebView2 支持 Windows 7 和 Windows Server 2008 R2 与 Microsoft Edge 具有相同的支持周期。</span><span class="sxs-lookup"><span data-stu-id="89eef-167">\*\* WebView2 support for Windows 7 and Windows Server 2008 R2 has the same support cycle as Microsoft Edge.</span></span>  <span data-ttu-id="89eef-168">有关详细信息，请导航到 [Microsoft Edge 支持的操作系统][DeployedgeMicrosoftEdgeSupportedOS]。</span><span class="sxs-lookup"><span data-stu-id="89eef-168">For more information, navigate to [Microsoft Edge supported Operating Systems][DeployedgeMicrosoftEdgeSupportedOS].</span></span>  

## <span data-ttu-id="89eef-169">后续步骤</span><span class="sxs-lookup"><span data-stu-id="89eef-169">Next steps</span></span>  

<span data-ttu-id="89eef-170">有关如何构建和部署 WebView2 应用程序的详细信息，请参阅概念文档和操作方法指南。</span><span class="sxs-lookup"><span data-stu-id="89eef-170">For more information on how to build and deploy WebView2 applications, review the conceptual documentation and how-to guides.</span></span>  

#### <span data-ttu-id="89eef-171">概念</span><span class="sxs-lookup"><span data-stu-id="89eef-171">Concepts</span></span>  

*   [<span data-ttu-id="89eef-172">了解 WebView2 SDK 版本</span><span class="sxs-lookup"><span data-stu-id="89eef-172">Understand WebView2 SDK versions</span></span>][Webview2ConceptsVersioning]
*   [<span data-ttu-id="89eef-173">使用 WebView2 的应用程序的分发</span><span class="sxs-lookup"><span data-stu-id="89eef-173">Distribution of applications using WebView2</span></span>][Webview2ConceptsDistribution]  
*   [<span data-ttu-id="89eef-174">开发安全 WebView2 应用程序的最佳做法</span><span class="sxs-lookup"><span data-stu-id="89eef-174">Best practices for developing secure WebView2 applications</span></span>][Webview2ConceptsSecurity]
*   [<span data-ttu-id="89eef-175">管理 WebView2 应用程序中的用户数据文件夹</span><span class="sxs-lookup"><span data-stu-id="89eef-175">Manage User Data Folder in WebView2 Applications</span></span>][Webview2ConceptsUserdatafolder]
 
#### <span data-ttu-id="89eef-176">How-To 指南</span><span class="sxs-lookup"><span data-stu-id="89eef-176">How-To guides</span></span>  

*   [<span data-ttu-id="89eef-177">如何通过 WebView2 进行调试</span><span class="sxs-lookup"><span data-stu-id="89eef-177">How to Debug with WebView2</span></span>][Webview2HowtoDebug]  
*   [<span data-ttu-id="89eef-178">通过 Microsoft Edge 驱动程序自动化和测试 WebView2</span><span class="sxs-lookup"><span data-stu-id="89eef-178">Automating and testing WebView2 with Microsoft Edge Driver</span></span>][Webview2HowtoWebdriver]


## <span data-ttu-id="89eef-179">与 Microsoft Edge Web 上的 Web Edge 团队取得联系</span><span class="sxs-lookup"><span data-stu-id="89eef-179">Getting in touch with the Microsoft Edge WebView team</span></span>  

[!INCLUDE [contact WebView team note](./includes/contact-webview-team-note.md)]  

<!-- links -->  

[Webview2ConceptsDistribution]: ./concepts/distribution.md "使用 WebView2 | 的应用程序的分发Microsoft 文档"  
[Webview2ConceptsSecurity]: ./concepts/security.md "开发安全 WebView2 应用程序的最佳做法 |Microsoft 文档"  
[Webview2ConceptsUserdatafolder]: ./concepts/userdatafolder.md "管理用户数据文件夹 |Microsoft 文档"  
[Webview2ConceptsVersioning]: ./concepts/versioning.md "了解 WebView2 SDK 版本 |Microsoft 文档"  
[Webview2GettingstartedWin32]: ./gettingstarted/win32.md "WebView2 | 入门 |Microsoft 文档"  
[Webview2GettingstartedWinforms]: ./gettingstarted/winforms.md "Windows Forms 应用中的 WebView2 入门 (预览版) |Microsoft 文档"  
[Webview2GettingstartedWinui]: ./gettingstarted/winui.md "WebView2 中的 "开始" WinUI3 () 预览 "|Microsoft 文档"  
[Webview2GettingstartedWpf]: ./gettingstarted/wpf.md "WPF 中的 WebView2 入门 (预览版) |Microsoft 文档"  
[Webview2HowtoDebug]: ./howto/debug.md "如何通过 WebView2 | 进行调试Microsoft 文档"  
[Webview2HowtoWebdriver]: ./howto/webdriver.md "通过 Microsoft Edge 驱动程序自动化和测试 WebView2 |Microsoft 文档"  
[Webview2Releasenotes]: ./releasenotes.md "WebView2 SDK 的发行说明 |Microsoft 文档"  

[UwpToolkitsWinui3]: /uwp/toolkits/winui3/index "Windows UI 库3预览版 2 (2020 年7月) |Microsoft 文档"  

[DeployedgeMicrosoftEdgeSupportedOS]: /deployedge/microsoft-edge-supported-operating-systems "Microsoft Edge 支持的操作系统 |Microsoft 文档"  

[GithubMicrosoftedgeWebview2samples]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 示例-MicrosoftEdge/WebView2Samples |GitHub"  
[GithubMicrosoftedgeWebviewfeddback]: https://github.com/MicrosoftEdge/WebViewFeedback "Web 视图反馈-MicrosoftEdge/WebViewFeedback |GitHub" 

[MicrosoftedgeinsiderMain]: https://www.microsoftedgeinsider.com "Microsoft Edge 预览体验成员"  
[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "下载 Microsoft Edge 预览体验成员"  

[NugetPackagesMicrosoftWebWebView2]: https://www.nuget.org/packages/Microsoft.Web.WebView2 "WebView2 |NuGet 库"  
