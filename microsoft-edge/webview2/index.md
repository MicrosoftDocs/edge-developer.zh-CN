---
description: 使用 Microsoft Edge WebView2 控件在 Win32、.NET 和 UWP 应用中托管 Web 内容
title: Microsoft Edge WebView2 控件
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/24/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 应用、win32、edge、ICoreWebView2、CoreWebView2、ICoreWebView2Host、浏览器控件、edge html、Windows Forms、WinForms、WPF、.NET、WinUI、Project 一线
ms.openlocfilehash: ec22edbc838f57c2f9c591a0f48298d61dce484c
ms.sourcegitcommit: b51df5036642060525e03cd744b7d35726326abe
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/29/2021
ms.locfileid: "11526071"
---
# <a name="introduction-to-microsoft-edge-webview2"></a><span data-ttu-id="69bd8-104">Microsoft Edge WebView2 简介</span><span class="sxs-lookup"><span data-stu-id="69bd8-104">Introduction to Microsoft Edge WebView2</span></span>  

<span data-ttu-id="69bd8-105">Microsoft Edge WebView2 控件使你能够将 Web 技术 \ (HTML、CSS 和 JavaScript\) 嵌入本机应用中。</span><span class="sxs-lookup"><span data-stu-id="69bd8-105">The Microsoft Edge WebView2 control enables you to embed web technologies \(HTML, CSS, and JavaScript\) in your native apps.</span></span>  <span data-ttu-id="69bd8-106">WebView2 控件使用 [Microsoft Edge (Chromium ][MicrosoftedgeinsiderMain]) 作为呈现引擎，以在本机应用中显示 Web 内容。</span><span class="sxs-lookup"><span data-stu-id="69bd8-106">The WebView2 control uses [Microsoft Edge (Chromium)][MicrosoftedgeinsiderMain] as the rendering engine to display the web content in native apps.</span></span>  <span data-ttu-id="69bd8-107">使用 WebView2，你可以将 Web 代码嵌入本机应用的不同部分。</span><span class="sxs-lookup"><span data-stu-id="69bd8-107">With WebView2, you may embed web code in different parts of your native app.</span></span>  <span data-ttu-id="69bd8-108">在单个 WebView 实例中生成所有本机应用。</span><span class="sxs-lookup"><span data-stu-id="69bd8-108">Build all of the native app within a single WebView instance.</span></span>  <span data-ttu-id="69bd8-109">若要了解如何开始生成 WebView2 应用，请导航到"[入门"。](#getting-started)</span><span class="sxs-lookup"><span data-stu-id="69bd8-109">For information on how to start building a WebView2 app, navigate to [Get Started](#getting-started).</span></span>  

:::image type="complex" source="./media/WebView2/whatwebview.png" alt-text="什么是 WebView？" lightbox="./media/WebView2/whatwebview.png":::
   <span data-ttu-id="69bd8-111">什么是 WebView？</span><span class="sxs-lookup"><span data-stu-id="69bd8-111">What is WebView?</span></span>  
:::image-end:::  

## <a name="hybrid-app-approach"></a><span data-ttu-id="69bd8-112">混合应用方法</span><span class="sxs-lookup"><span data-stu-id="69bd8-112">Hybrid app approach</span></span>  

<span data-ttu-id="69bd8-113">开发人员通常必须在生成 Web 应用还是生成本机应用之间做出决定。</span><span class="sxs-lookup"><span data-stu-id="69bd8-113">Developers must often decide between building a web app or a native app.</span></span>  <span data-ttu-id="69bd8-114">该决策将决定范围与电源之间的选择。</span><span class="sxs-lookup"><span data-stu-id="69bd8-114">The decision hinges on the trade-off between reach and power.</span></span>  <span data-ttu-id="69bd8-115">Web 应用可广泛覆盖。</span><span class="sxs-lookup"><span data-stu-id="69bd8-115">Web apps allow for a broad reach.</span></span>  <span data-ttu-id="69bd8-116">作为 Web 开发人员，您可以跨不同平台重用大部分代码。</span><span class="sxs-lookup"><span data-stu-id="69bd8-116">As a Web developer, you may reuse most of your code across different platforms.</span></span>  <span data-ttu-id="69bd8-117">若要访问本机平台的所有功能，请使用本机应用。</span><span class="sxs-lookup"><span data-stu-id="69bd8-117">To access the all capabilities of a native platform, use a native app.</span></span>  

:::image type="complex" source="./media/WebView2/webnative.png" alt-text="Web 本机" lightbox="./media/WebView2/webnative.png":::
   <span data-ttu-id="69bd8-119">Web 本机</span><span class="sxs-lookup"><span data-stu-id="69bd8-119">Web native</span></span>  
:::image-end:::  

<span data-ttu-id="69bd8-120">混合应用使开发人员能够享受两全其美。</span><span class="sxs-lookup"><span data-stu-id="69bd8-120">Hybrid apps allow developers to enjoy the best of both worlds.</span></span>  <span data-ttu-id="69bd8-121">混合应用开发人员受益于以下优势。</span><span class="sxs-lookup"><span data-stu-id="69bd8-121">Hybrid app developers benefit from the following advantages.</span></span>  

*   <span data-ttu-id="69bd8-122">Web 平台的优势和强度。</span><span class="sxs-lookup"><span data-stu-id="69bd8-122">The ubiquity and strength of the web platform.</span></span>  
*   <span data-ttu-id="69bd8-123">本机平台的功能和完整功能。</span><span class="sxs-lookup"><span data-stu-id="69bd8-123">The power and full capabilities of the native platform.</span></span>  
    
## <a name="webview2-benefits"></a><span data-ttu-id="69bd8-124">WebView2 优势</span><span class="sxs-lookup"><span data-stu-id="69bd8-124">WebView2 benefits</span></span>   

<!--  
:::image type="complex" source="./media/WebView2/webviewreasons.png" alt-text="WebView reasons" lightbox="./media/WebView2/webviewreasons.png":::
   WebView reasons  
:::image-end:::  
-->  

:::row:::
   :::column span="1":::
      :::image type="icon" source="./media/webview-reasons-web-ecosystem-skillset.msft.png":::  
      **<span data-ttu-id="69bd8-125">Web 生态系统 \&技能集</span><span class="sxs-lookup"><span data-stu-id="69bd8-125">Web ecosystem \& skillset</span></span>**  
      <span data-ttu-id="69bd8-126">利用 Web 生态系统内存在的整个 Web 平台、库、工具和人才。</span><span class="sxs-lookup"><span data-stu-id="69bd8-126">Utilize the entire web platform, libraries, tooling, and talent that exists within the web ecosystem.</span></span>  
   :::column-end:::
   :::column span="1":::
      :::image type="icon" source="./media/webview-reasons-rapid-innovation.msft.png":::  
      **<span data-ttu-id="69bd8-127">快速创新</span><span class="sxs-lookup"><span data-stu-id="69bd8-127">Rapid innovation</span></span>**  
      <span data-ttu-id="69bd8-128">Web 开发允许更快地部署和迭代。</span><span class="sxs-lookup"><span data-stu-id="69bd8-128">Web development allows for faster deployment and iteration.</span></span>  
   :::column-end:::
   :::column span="1":::
      :::image type="icon" source="./media/webview-reasons-windows-7-8-10-support.msft.png":::  
      **<span data-ttu-id="69bd8-129">Windows 7、8 和 10 支持</span><span class="sxs-lookup"><span data-stu-id="69bd8-129">Windows 7, 8, and 10 support</span></span>**  
      <span data-ttu-id="69bd8-130">支持跨 Windows 7、Windows 8 和 Windows 10 实现一致的用户体验。</span><span class="sxs-lookup"><span data-stu-id="69bd8-130">Support for a consistent user experience across Windows 7, Windows 8, and Windows 10.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      :::image type="icon" source="./media/webview-reasons-native-capabilities.msft.png":::  
      **<span data-ttu-id="69bd8-131">本机功能</span><span class="sxs-lookup"><span data-stu-id="69bd8-131">Native capabilities</span></span>**  
      <span data-ttu-id="69bd8-132">访问完整的本机 API 集。</span><span class="sxs-lookup"><span data-stu-id="69bd8-132">Access the full set of Native APIs.</span></span>  
   :::column-end:::
   :::column span="1":::
      :::image type="icon" source="./media/webview-reasons-code-sharing.msft.png":::  
      **<span data-ttu-id="69bd8-133">代码共享</span><span class="sxs-lookup"><span data-stu-id="69bd8-133">Code-sharing</span></span>**  
      <span data-ttu-id="69bd8-134">向代码库添加 Web 代码可增强跨多个平台的重用。</span><span class="sxs-lookup"><span data-stu-id="69bd8-134">Add web code to your codebase allows for increased reuse across multiple platforms.</span></span>  
   :::column-end:::
   :::column span="1":::
      :::image type="icon" source="./media/webview-reasons-microsoft-support.msft.png":::  
      **<span data-ttu-id="69bd8-135">Microsoft 支持</span><span class="sxs-lookup"><span data-stu-id="69bd8-135">Microsoft support</span></span>**  
      <span data-ttu-id="69bd8-136">当 WebView2 在通用版本 \ (GA\) 发布时，Microsoft 提供支持并添加新功能) 。</span><span class="sxs-lookup"><span data-stu-id="69bd8-136">Microsoft provides support and adds new feature requests when WebView2 releases at Generally Availability \(GA\).</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      :::image type="icon" source="./media/webview-reasons-evergreen.msft.png":::  
      **<span data-ttu-id="69bd8-137">常青分布</span><span class="sxs-lookup"><span data-stu-id="69bd8-137">Evergreen distribution</span></span>**  
      <span data-ttu-id="69bd8-138">依靠具有常规平台更新和安全修补程序的最新版本的 Chromium。</span><span class="sxs-lookup"><span data-stu-id="69bd8-138">Rely on an up-to-date version of Chromium with regular platform updates and security patches.</span></span>  
   :::column-end:::
   :::column span="1":::
      :::image type="icon" source="./media/webview-reasons-fixed.msft.png":::  
      **<span data-ttu-id="69bd8-139">已修复</span><span class="sxs-lookup"><span data-stu-id="69bd8-139">Fixed</span></span>**  
      <span data-ttu-id="69bd8-140">\ (即将推出\) 选择将 Chromium 位打包到应用中。</span><span class="sxs-lookup"><span data-stu-id="69bd8-140">\(coming soon\)  Choose to package the Chromium bits in your app.</span></span>  
   :::column-end:::
   :::column span="1":::
      :::image type="icon" source="./media/webview-reasons-incremental-adoption.msft.png":::  
      **<span data-ttu-id="69bd8-141">增量采用</span><span class="sxs-lookup"><span data-stu-id="69bd8-141">Incremental adoption</span></span>**  
      <span data-ttu-id="69bd8-142">将 Web 组件分片添加到应用。</span><span class="sxs-lookup"><span data-stu-id="69bd8-142">Add web components piece by piece to your app.</span></span>  
   :::column-end:::
:::row-end:::  

## <a name="getting-started"></a><span data-ttu-id="69bd8-143">入门</span><span class="sxs-lookup"><span data-stu-id="69bd8-143">Getting started</span></span>  

<span data-ttu-id="69bd8-144">若要使用 WebView2 控件生成和测试应用，你需要</span><span class="sxs-lookup"><span data-stu-id="69bd8-144">To build and test your app using the WebView2 control, you need to have</span></span> <!--both [Microsoft Edge (Chromium)][MicrosoftedgeinsiderDownload] and  --><span data-ttu-id="69bd8-145">安装的[WebView2 SDK。][NugetPackagesMicrosoftWebWebView2]</span><span class="sxs-lookup"><span data-stu-id="69bd8-145">the [WebView2 SDK][NugetPackagesMicrosoftWebWebView2] installed.</span></span>  <span data-ttu-id="69bd8-146">选择下列选项之一开始。</span><span class="sxs-lookup"><span data-stu-id="69bd8-146">Select one of the following options to get started.</span></span>  

*   [<span data-ttu-id="69bd8-147">Win32 C/C++ 入门</span><span class="sxs-lookup"><span data-stu-id="69bd8-147">Getting Started with Win32 C/C++</span></span>][Webview2GettingstartedWin32]  
*   [<span data-ttu-id="69bd8-148">WPF 入门</span><span class="sxs-lookup"><span data-stu-id="69bd8-148">Getting Started with WPF</span></span>][Webview2GettingstartedWpf]  
*   [<span data-ttu-id="69bd8-149">WinForms 入门</span><span class="sxs-lookup"><span data-stu-id="69bd8-149">Getting Started with WinForms</span></span>][Webview2GettingstartedWinforms]  
*   [<span data-ttu-id="69bd8-150">WinUI3 入门</span><span class="sxs-lookup"><span data-stu-id="69bd8-150">Getting Started with WinUI3</span></span>][Webview2GettingstartedWinui]  

<span data-ttu-id="69bd8-151">[WebView2 示例][GithubMicrosoftedgeWebview2samples]存储库包含演示所有 WebView2 SDK 功能和 API 使用模式的示例。</span><span class="sxs-lookup"><span data-stu-id="69bd8-151">The [WebView2 Samples][GithubMicrosoftedgeWebview2samples] repository contains samples that demonstrate all of the WebView2 SDK features and API usage patterns.</span></span>  <span data-ttu-id="69bd8-152">随着更多功能添加到 WebView2 SDK 中，示例应用将更新。</span><span class="sxs-lookup"><span data-stu-id="69bd8-152">As more features are added to the WebView2 SDK, the sample apps will be updated.</span></span>  

## <a name="supported-platforms"></a><span data-ttu-id="69bd8-153">支持的平台</span><span class="sxs-lookup"><span data-stu-id="69bd8-153">Supported platforms</span></span>  

<span data-ttu-id="69bd8-154">通用 \ (GA\) 或预览版可在以下编程环境中使用。</span><span class="sxs-lookup"><span data-stu-id="69bd8-154">A General Availability \(GA\) or Preview version is available on the following programming environments.</span></span>  

*   <span data-ttu-id="69bd8-155">Win32 C/C++ \ (GA\) </span><span class="sxs-lookup"><span data-stu-id="69bd8-155">Win32 C/C++ \(GA\)</span></span>  
*   <span data-ttu-id="69bd8-156">.NET Framework 4.5 或更高版本</span><span class="sxs-lookup"><span data-stu-id="69bd8-156">.NET Framework 4.5 or later</span></span>  
*   <span data-ttu-id="69bd8-157">.NET Core 3.1 或更高版本</span><span class="sxs-lookup"><span data-stu-id="69bd8-157">.NET Core 3.1 or later</span></span>  
*   <span data-ttu-id="69bd8-158">.NET 5</span><span class="sxs-lookup"><span data-stu-id="69bd8-158">.NET 5</span></span>  
*   <span data-ttu-id="69bd8-159">[WinUI 3.0][UwpToolkitsWinui3] \ (Preview\) </span><span class="sxs-lookup"><span data-stu-id="69bd8-159">[WinUI 3.0][UwpToolkitsWinui3] \(Preview\)</span></span>  

<span data-ttu-id="69bd8-160">您可以在以下版本的 Windows 中运行 WebView2 应用。</span><span class="sxs-lookup"><span data-stu-id="69bd8-160">You may run WebView2 apps on the following versions of Windows.</span></span>  

*   <span data-ttu-id="69bd8-161">Windows 10</span><span class="sxs-lookup"><span data-stu-id="69bd8-161">Windows 10</span></span>  
*   <span data-ttu-id="69bd8-162">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="69bd8-162">Windows 8.1</span></span>  
*   <span data-ttu-id="69bd8-163">Windows 7 \*\*</span><span class="sxs-lookup"><span data-stu-id="69bd8-163">Windows 7 \*\*</span></span>  
*   <span data-ttu-id="69bd8-164">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="69bd8-164">Windows Server 2019</span></span>  
*   <span data-ttu-id="69bd8-165">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="69bd8-165">Windows Server 2016</span></span>  
*   <span data-ttu-id="69bd8-166">WindowsServer 2012</span><span class="sxs-lookup"><span data-stu-id="69bd8-166">Windows Server 2012</span></span>  
*   <span data-ttu-id="69bd8-167">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="69bd8-167">Windows Server 2012 R2</span></span>  
*   <span data-ttu-id="69bd8-168">Windows Server 2008 R2 \*\*</span><span class="sxs-lookup"><span data-stu-id="69bd8-168">Windows Server 2008 R2 \*\*</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="69bd8-169">\*\* Windows 7 和 Windows Server 2008 R2 的 WebView2 支持与 Microsoft Edge 具有相同的支持周期。</span><span class="sxs-lookup"><span data-stu-id="69bd8-169">\*\* WebView2 support for Windows 7 and Windows Server 2008 R2 has the same support cycle as Microsoft Edge.</span></span>  <span data-ttu-id="69bd8-170">有关详细信息，请导航到 [Microsoft Edge 支持的操作系统][DeployedgeMicrosoftEdgeSupportedOS]。</span><span class="sxs-lookup"><span data-stu-id="69bd8-170">For more information, navigate to [Microsoft Edge supported Operating Systems][DeployedgeMicrosoftEdgeSupportedOS].</span></span>  

## <a name="next-steps"></a><span data-ttu-id="69bd8-171">后续步骤</span><span class="sxs-lookup"><span data-stu-id="69bd8-171">Next steps</span></span>  

<span data-ttu-id="69bd8-172">若要详细了解如何生成和部署 WebView2 应用，请查看概念文档和帮助指南。</span><span class="sxs-lookup"><span data-stu-id="69bd8-172">For more information on how to build and deploy WebView2 apps, review the conceptual documentation and how-to guides.</span></span>  

#### <a name="concepts"></a><span data-ttu-id="69bd8-173">概念</span><span class="sxs-lookup"><span data-stu-id="69bd8-173">Concepts</span></span>  

*   [<span data-ttu-id="69bd8-174">了解 WebView2 SDK 版本</span><span class="sxs-lookup"><span data-stu-id="69bd8-174">Understand WebView2 SDK versions</span></span>][Webview2ConceptsVersioning]  
*   [<span data-ttu-id="69bd8-175">使用 WebView2 分发应用</span><span class="sxs-lookup"><span data-stu-id="69bd8-175">Distribution of apps using WebView2</span></span>][Webview2ConceptsDistribution]  
*   [<span data-ttu-id="69bd8-176">开发安全 WebView2 应用的最佳方案</span><span class="sxs-lookup"><span data-stu-id="69bd8-176">Best practices for developing secure WebView2 apps</span></span>][Webview2ConceptsSecurity]  
*   [<span data-ttu-id="69bd8-177">在 WebView2 应用中管理用户数据文件夹</span><span class="sxs-lookup"><span data-stu-id="69bd8-177">Manage User Data Folder in WebView2 apps</span></span>][Webview2ConceptsUserdatafolder]  
 
#### <a name="how-to-guides"></a><span data-ttu-id="69bd8-178">How-To指南</span><span class="sxs-lookup"><span data-stu-id="69bd8-178">How-To guides</span></span>  

*   [<span data-ttu-id="69bd8-179">如何使用 WebView2 调试</span><span class="sxs-lookup"><span data-stu-id="69bd8-179">How to Debug with WebView2</span></span>][Webview2HowtoDebug]  
*   [<span data-ttu-id="69bd8-180">使用 Microsoft Edge 驱动程序自动执行和测试 WebView2</span><span class="sxs-lookup"><span data-stu-id="69bd8-180">Automating and testing WebView2 with Microsoft Edge Driver</span></span>][Webview2HowtoWebdriver]  

## <a name="getting-in-touch-with-the-microsoft-edge-webview-team"></a><span data-ttu-id="69bd8-181">与 Microsoft Edge WebView 团队联系</span><span class="sxs-lookup"><span data-stu-id="69bd8-181">Getting in touch with the Microsoft Edge WebView team</span></span>  

[!INCLUDE [contact WebView team note](./includes/contact-webview-team-note.md)]  

<!-- links -->  

[Webview2ConceptsDistribution]: ./concepts/distribution.md "使用 WebView2 应用程序分配|Microsoft Docs"  
[Webview2ConceptsSecurity]: ./concepts/security.md "开发安全的 WebView2 应用和 web |Microsoft Docs"  
[Webview2ConceptsUserdatafolder]: ./concepts/userdatafolder.md "管理用户数据文件夹|Microsoft Docs"  
[Webview2ConceptsVersioning]: ./concepts/versioning.md "了解 WebView2 SDK |Microsoft Docs"  
[Webview2GettingstartedWin32]: ./gettingstarted/win32.md "WebView2 应用程序|Microsoft Docs"  
[Webview2GettingstartedWinforms]: ./gettingstarted/winforms.md "Windows 窗体应用中的 WebView2 入门 (预览) |Microsoft Docs"  
[Webview2GettingstartedWinui]: ./gettingstarted/winui.md "WinUI3 预览版中的 WebView2 (入门) |Microsoft Docs"  
[Webview2GettingstartedWpf]: ./gettingstarted/wpf.md "WPF 预览版中的 WebView2 (入门) |Microsoft Docs"  
[Webview2HowtoDebug]: ./howto/debug.md "如何使用 WebView2 |Microsoft Docs"  
[Webview2HowtoWebdriver]: ./howto/webdriver.md "使用 Microsoft Edge 驱动程序工具自动执行和测试 WebView2 |Microsoft Docs"  
[Webview2Releasenotes]: ./releasenotes.md "WebView2 SDK |Microsoft Docs"  

[UwpToolkitsWinui3]: /uwp/toolkits/winui3/index "Windows UI Library 3 Preview 2 (2020 年 7 月) |Microsoft Docs"  

[DeployedgeMicrosoftEdgeSupportedOS]: /deployedge/microsoft-edge-supported-operating-systems "Microsoft Edge 支持的操作系统|Microsoft Docs"  

[GithubMicrosoftedgeWebview2samples]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 示例 - MicrosoftEdge/WebView2Samples |GitHub"  
[GithubMicrosoftedgeWebviewfeddback]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView 反馈 - MicrosoftEdge/WebViewFeedback |GitHub"  

[MicrosoftedgeinsiderMain]: https://www.microsoftedgeinsider.com "Microsoft Edge 预览体验成员"  
[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "下载 Microsoft Edge 预览体验成员"  

[NugetPackagesMicrosoftWebWebView2]: https://www.nuget.org/packages/Microsoft.Web.WebView2 "Microsoft.Web.WebView2 |NuGet 库"  
