---
description: 使用 WebView2 控件在 Win32、.NET 和 UWP 应用中Microsoft Edge Web 内容
title: Microsoft EdgeWebView2 控件
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/06/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 应用、win32、edge、ICoreWebView2、CoreWebView2、ICoreWebView2Host、浏览器控件、edge html、Windows Forms、WinForms、WPF、.NET、WinUI、Project
ms.openlocfilehash: 154c18a3cc9236a8abd286918d72e1a1968fea38
ms.sourcegitcommit: 777b16ef10363f2dfd755f115ee2d4c81a8de46f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2021
ms.locfileid: "11535720"
---
# <a name="introduction-to-microsoft-edge-webview2"></a><span data-ttu-id="b9c17-104">WebView2 Microsoft Edge简介</span><span class="sxs-lookup"><span data-stu-id="b9c17-104">Introduction to Microsoft Edge WebView2</span></span>  

<span data-ttu-id="b9c17-105">利用 Microsoft Edge WebView2 控件，可以将 Web 技术 \ (HTML、CSS 和 JavaScript\) 嵌入本机应用中。</span><span class="sxs-lookup"><span data-stu-id="b9c17-105">The Microsoft Edge WebView2 control enables you to embed web technologies \(HTML, CSS, and JavaScript\) in your native apps.</span></span>  <span data-ttu-id="b9c17-106">WebView2 控件使用[Microsoft Edge (Chromium) ][MicrosoftedgeinsiderMain]作为呈现引擎，以在本机应用中显示 Web 内容。</span><span class="sxs-lookup"><span data-stu-id="b9c17-106">The WebView2 control uses [Microsoft Edge (Chromium)][MicrosoftedgeinsiderMain] as the rendering engine to display the web content in native apps.</span></span>  <span data-ttu-id="b9c17-107">使用 WebView2，你可以将 Web 代码嵌入本机应用的不同部分。</span><span class="sxs-lookup"><span data-stu-id="b9c17-107">With WebView2, you may embed web code in different parts of your native app.</span></span>  <span data-ttu-id="b9c17-108">在单个 WebView 实例中生成所有本机应用。</span><span class="sxs-lookup"><span data-stu-id="b9c17-108">Build all of the native app within a single WebView instance.</span></span>  <span data-ttu-id="b9c17-109">若要了解如何开始生成 WebView2 应用，请导航到["入门"。](#get-started)</span><span class="sxs-lookup"><span data-stu-id="b9c17-109">For information on how to start building a WebView2 app, navigate to [Get Started](#get-started).</span></span>  

:::image type="complex" source="./media/WebView2/what-webview.png" alt-text="什么是 WebView？" lightbox="./media/WebView2/what-webview.png":::
   <span data-ttu-id="b9c17-111">什么是 WebView？</span><span class="sxs-lookup"><span data-stu-id="b9c17-111">What is WebView?</span></span>  
:::image-end:::    

## <a name="hybrid-app-approach"></a><span data-ttu-id="b9c17-112">混合应用方法</span><span class="sxs-lookup"><span data-stu-id="b9c17-112">Hybrid app approach</span></span>  

<span data-ttu-id="b9c17-113">开发人员通常必须在生成 Web 应用还是生成本机应用之间做出决定。</span><span class="sxs-lookup"><span data-stu-id="b9c17-113">Developers must often decide between building a web app or a native app.</span></span>  <span data-ttu-id="b9c17-114">该决策将决定范围与电源之间的选择。</span><span class="sxs-lookup"><span data-stu-id="b9c17-114">The decision hinges on the trade-off between reach and power.</span></span>  <span data-ttu-id="b9c17-115">Web 应用可广泛覆盖。</span><span class="sxs-lookup"><span data-stu-id="b9c17-115">Web apps allow for a broad reach.</span></span>  <span data-ttu-id="b9c17-116">作为 Web 开发人员，您可以跨不同平台重用大部分代码。</span><span class="sxs-lookup"><span data-stu-id="b9c17-116">As a Web developer, you may reuse most of your code across different platforms.</span></span>  <span data-ttu-id="b9c17-117">若要访问本机平台的所有功能，请使用本机应用。</span><span class="sxs-lookup"><span data-stu-id="b9c17-117">To access the all capabilities of a native platform, use a native app.</span></span>  

:::image type="complex" source="./media/WebView2/web-native.png" alt-text="Web 本机" lightbox="./media/WebView2/web-native.png":::
   <span data-ttu-id="b9c17-119">Web 本机</span><span class="sxs-lookup"><span data-stu-id="b9c17-119">Web native</span></span>  
:::image-end:::    

<span data-ttu-id="b9c17-120">混合应用使开发人员能够享受两全其美。</span><span class="sxs-lookup"><span data-stu-id="b9c17-120">Hybrid apps allow developers to enjoy the best of both worlds.</span></span>  <span data-ttu-id="b9c17-121">混合应用开发人员受益于以下优势。</span><span class="sxs-lookup"><span data-stu-id="b9c17-121">Hybrid app developers benefit from the following advantages.</span></span>  

*   <span data-ttu-id="b9c17-122">Web 平台的优势和强度。</span><span class="sxs-lookup"><span data-stu-id="b9c17-122">The ubiquity and strength of the web platform.</span></span>  
*   <span data-ttu-id="b9c17-123">本机平台的功能和完整功能。</span><span class="sxs-lookup"><span data-stu-id="b9c17-123">The power and full capabilities of the native platform.</span></span>  
    
## <a name="webview2-benefits"></a><span data-ttu-id="b9c17-124">WebView2 优势</span><span class="sxs-lookup"><span data-stu-id="b9c17-124">WebView2 benefits</span></span>   

<!--  
:::image type="complex" source="./media/WebView2/webview-reasons.png" alt-text="WebView reasons" lightbox="./media/WebView2/webview-reasons.png":::
   WebView reasons  
:::image-end:::    
-->  

:::row:::
   :::column span="1":::
      :::image type="icon" source="./media/webview-reasons-web-ecosystem-skillset.msft.png":::  
      **<span data-ttu-id="b9c17-125">Web 生态系统 \&技能集</span><span class="sxs-lookup"><span data-stu-id="b9c17-125">Web ecosystem \& skillset</span></span>**  
      <span data-ttu-id="b9c17-126">利用 Web 生态系统内存在的整个 Web 平台、库、工具和人才。</span><span class="sxs-lookup"><span data-stu-id="b9c17-126">Utilize the entire web platform, libraries, tooling, and talent that exists within the web ecosystem.</span></span>  
   :::column-end:::
   :::column span="1":::
      :::image type="icon" source="./media/webview-reasons-rapid-innovation.msft.png":::  
      **<span data-ttu-id="b9c17-127">快速创新</span><span class="sxs-lookup"><span data-stu-id="b9c17-127">Rapid innovation</span></span>**  
      <span data-ttu-id="b9c17-128">Web 开发允许更快地部署和迭代。</span><span class="sxs-lookup"><span data-stu-id="b9c17-128">Web development allows for faster deployment and iteration.</span></span>  
   :::column-end:::
   :::column span="1":::
      :::image type="icon" source="./media/webview-reasons-windows-7-8-10-support.msft.png":::  
      **<span data-ttu-id="b9c17-129">Windows 7、8 和 10 支持</span><span class="sxs-lookup"><span data-stu-id="b9c17-129">Windows 7, 8, and 10 support</span></span>**  
      <span data-ttu-id="b9c17-130">支持跨 Windows 7、Windows 8 和 Windows 10。</span><span class="sxs-lookup"><span data-stu-id="b9c17-130">Support for a consistent user experience across Windows 7, Windows 8, and Windows 10.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      :::image type="icon" source="./media/webview-reasons-native-capabilities.msft.png":::  
      **<span data-ttu-id="b9c17-131">本机功能</span><span class="sxs-lookup"><span data-stu-id="b9c17-131">Native capabilities</span></span>**  
      <span data-ttu-id="b9c17-132">访问完整的本机 API 集。</span><span class="sxs-lookup"><span data-stu-id="b9c17-132">Access the full set of Native APIs.</span></span>  
   :::column-end:::
   :::column span="1":::
      :::image type="icon" source="./media/webview-reasons-code-sharing.msft.png":::  
      **<span data-ttu-id="b9c17-133">代码共享</span><span class="sxs-lookup"><span data-stu-id="b9c17-133">Code-sharing</span></span>**  
      <span data-ttu-id="b9c17-134">向代码库添加 Web 代码可增强跨多个平台的重用。</span><span class="sxs-lookup"><span data-stu-id="b9c17-134">Add web code to your codebase allows for increased reuse across multiple platforms.</span></span>  
   :::column-end:::
   :::column span="1":::
      :::image type="icon" source="./media/webview-reasons-microsoft-support.msft.png":::  
      **<span data-ttu-id="b9c17-135">Microsoft 支持</span><span class="sxs-lookup"><span data-stu-id="b9c17-135">Microsoft support</span></span>**  
      <span data-ttu-id="b9c17-136">当 WebView2 在通用版本 \ (GA\) 发布时，Microsoft 提供支持并添加新功能) 。</span><span class="sxs-lookup"><span data-stu-id="b9c17-136">Microsoft provides support and adds new feature requests when WebView2 releases at Generally Availability \(GA\).</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      :::image type="icon" source="./media/webview-reasons-evergreen.msft.png":::  
      **<span data-ttu-id="b9c17-137">常青分布</span><span class="sxs-lookup"><span data-stu-id="b9c17-137">Evergreen distribution</span></span>**  
      <span data-ttu-id="b9c17-138">依赖最新版 Chromium定期平台更新和安全修补程序。</span><span class="sxs-lookup"><span data-stu-id="b9c17-138">Rely on an up-to-date version of Chromium with regular platform updates and security patches.</span></span>  
   :::column-end:::
   :::column span="1":::
      :::image type="icon" source="./media/webview-reasons-fixed.msft.png":::  
      **<span data-ttu-id="b9c17-139">已修复</span><span class="sxs-lookup"><span data-stu-id="b9c17-139">Fixed</span></span>**  
      <span data-ttu-id="b9c17-140">\ (即将推出\) 选择在应用中打包Chromium位。</span><span class="sxs-lookup"><span data-stu-id="b9c17-140">\(coming soon\)  Choose to package the Chromium bits in your app.</span></span>  
   :::column-end:::
   :::column span="1":::
      :::image type="icon" source="./media/webview-reasons-incremental-adoption.msft.png":::  
      **<span data-ttu-id="b9c17-141">增量采用</span><span class="sxs-lookup"><span data-stu-id="b9c17-141">Incremental adoption</span></span>**  
      <span data-ttu-id="b9c17-142">将 Web 组件分片添加到应用。</span><span class="sxs-lookup"><span data-stu-id="b9c17-142">Add web components piece by piece to your app.</span></span>  
   :::column-end:::
:::row-end:::  

## <a name="get-started"></a><span data-ttu-id="b9c17-143">入门</span><span class="sxs-lookup"><span data-stu-id="b9c17-143">Get started</span></span>  

<span data-ttu-id="b9c17-144">若要使用 WebView2 控件生成和测试应用，你需要</span><span class="sxs-lookup"><span data-stu-id="b9c17-144">To build and test your app using the WebView2 control, you need to have</span></span> <!--both [Microsoft Edge (Chromium)][MicrosoftedgeinsiderDownload] and  --><span data-ttu-id="b9c17-145">安装的[WebView2 SDK。][NugetPackagesMicrosoftWebWebView2]</span><span class="sxs-lookup"><span data-stu-id="b9c17-145">the [WebView2 SDK][NugetPackagesMicrosoftWebWebView2] installed.</span></span>  <span data-ttu-id="b9c17-146">选择下列选项之一开始。</span><span class="sxs-lookup"><span data-stu-id="b9c17-146">Select one of the following options to get started.</span></span>  

*   [<span data-ttu-id="b9c17-147">入门 Win32 C/C++</span><span class="sxs-lookup"><span data-stu-id="b9c17-147">Get Started with Win32 C/C++</span></span>][Webview2GetStartedWin32]  
*   [<span data-ttu-id="b9c17-148">入门 WPF</span><span class="sxs-lookup"><span data-stu-id="b9c17-148">Get Started with WPF</span></span>][Webview2GetStartedWpf]  
*   [<span data-ttu-id="b9c17-149">入门 WinForms</span><span class="sxs-lookup"><span data-stu-id="b9c17-149">Get Started with WinForms</span></span>][Webview2GetStartedWinforms]  
*   [<span data-ttu-id="b9c17-150">入门 WinUI3</span><span class="sxs-lookup"><span data-stu-id="b9c17-150">Get Started with WinUI3</span></span>][Webview2GetStartedWinui]  
    
<span data-ttu-id="b9c17-151">[WebView2 示例][GithubMicrosoftedgeWebview2samples]存储库包含演示所有 WebView2 SDK 功能和 API 使用模式的示例。</span><span class="sxs-lookup"><span data-stu-id="b9c17-151">The [WebView2 Samples][GithubMicrosoftedgeWebview2samples] repository contains samples that demonstrate all of the WebView2 SDK features and API usage patterns.</span></span>  <span data-ttu-id="b9c17-152">随着更多功能添加到 WebView2 SDK 中，示例应用将更新。</span><span class="sxs-lookup"><span data-stu-id="b9c17-152">As more features are added to the WebView2 SDK, the sample apps will be updated.</span></span>  

## <a name="supported-platforms"></a><span data-ttu-id="b9c17-153">支持的平台</span><span class="sxs-lookup"><span data-stu-id="b9c17-153">Supported platforms</span></span>  

<span data-ttu-id="b9c17-154">通用 \ (GA\) 或预览版可在以下编程环境中使用。</span><span class="sxs-lookup"><span data-stu-id="b9c17-154">A General Availability \(GA\) or Preview version is available on the following programming environments.</span></span>  

*   <span data-ttu-id="b9c17-155">Win32 C/C++ \ (GA\) </span><span class="sxs-lookup"><span data-stu-id="b9c17-155">Win32 C/C++ \(GA\)</span></span>  
*   <span data-ttu-id="b9c17-156">.NET Framework 4.5 或更高版本</span><span class="sxs-lookup"><span data-stu-id="b9c17-156">.NET Framework 4.5 or later</span></span>  
*   <span data-ttu-id="b9c17-157">.NET Core 3.1 或更高版本</span><span class="sxs-lookup"><span data-stu-id="b9c17-157">.NET Core 3.1 or later</span></span>  
*   <span data-ttu-id="b9c17-158">.NET 5</span><span class="sxs-lookup"><span data-stu-id="b9c17-158">.NET 5</span></span>  
*   <span data-ttu-id="b9c17-159">[WinUI 3.0][UwpToolkitsWinui3] \ (Preview\) </span><span class="sxs-lookup"><span data-stu-id="b9c17-159">[WinUI 3.0][UwpToolkitsWinui3] \(Preview\)</span></span>  
    
<span data-ttu-id="b9c17-160">你可以运行以下版本的 WebView2 Windows。</span><span class="sxs-lookup"><span data-stu-id="b9c17-160">You may run WebView2 apps on the following versions of Windows.</span></span>  

*   <span data-ttu-id="b9c17-161">Windows 10</span><span class="sxs-lookup"><span data-stu-id="b9c17-161">Windows 10</span></span>  
*   <span data-ttu-id="b9c17-162">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="b9c17-162">Windows 8.1</span></span>  
*   <span data-ttu-id="b9c17-163">Windows 7 \*\*</span><span class="sxs-lookup"><span data-stu-id="b9c17-163">Windows 7 \*\*</span></span>  
*   <span data-ttu-id="b9c17-164">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="b9c17-164">Windows Server 2019</span></span>  
*   <span data-ttu-id="b9c17-165">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="b9c17-165">Windows Server 2016</span></span>  
*   <span data-ttu-id="b9c17-166">WindowsServer 2012</span><span class="sxs-lookup"><span data-stu-id="b9c17-166">Windows Server 2012</span></span>  
*   <span data-ttu-id="b9c17-167">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="b9c17-167">Windows Server 2012 R2</span></span>  
*   <span data-ttu-id="b9c17-168">WindowsServer 2008 R2 \*\*</span><span class="sxs-lookup"><span data-stu-id="b9c17-168">Windows Server 2008 R2 \*\*</span></span>  
    
> [!IMPORTANT]
> <span data-ttu-id="b9c17-169">\*\* 对 Windows 7 和 Windows Server 2008 R2 的 WebView2 支持与 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="b9c17-169">\*\* WebView2 support for Windows 7 and Windows Server 2008 R2 has the same support cycle as Microsoft Edge.</span></span>  <span data-ttu-id="b9c17-170">有关详细信息，请导航到Microsoft Edge[支持的操作系统。][DeployedgeMicrosoftEdgeSupportedOS]</span><span class="sxs-lookup"><span data-stu-id="b9c17-170">For more information, navigate to [Microsoft Edge supported Operating Systems][DeployedgeMicrosoftEdgeSupportedOS].</span></span>  

## <a name="next-steps"></a><span data-ttu-id="b9c17-171">后续步骤</span><span class="sxs-lookup"><span data-stu-id="b9c17-171">Next steps</span></span>  

<span data-ttu-id="b9c17-172">若要详细了解如何生成和部署 WebView2 应用，请查看概念文档和帮助指南。</span><span class="sxs-lookup"><span data-stu-id="b9c17-172">For more information on how to build and deploy WebView2 apps, review the conceptual documentation and how-to guides.</span></span>  

### <a name="concepts"></a><span data-ttu-id="b9c17-173">概念</span><span class="sxs-lookup"><span data-stu-id="b9c17-173">Concepts</span></span>  

*   [<span data-ttu-id="b9c17-174">了解 WebView2 SDK 版本</span><span class="sxs-lookup"><span data-stu-id="b9c17-174">Understand WebView2 SDK versions</span></span>][Webview2ConceptsVersioning]  
*   [<span data-ttu-id="b9c17-175">使用 WebView2 分发应用</span><span class="sxs-lookup"><span data-stu-id="b9c17-175">Distribution of apps using WebView2</span></span>][Webview2ConceptsDistribution]  
*   [<span data-ttu-id="b9c17-176">开发安全 WebView2 应用的最佳方案</span><span class="sxs-lookup"><span data-stu-id="b9c17-176">Best practices for developing secure WebView2 apps</span></span>][Webview2ConceptsSecurity]  
*   [<span data-ttu-id="b9c17-177">在 WebView2 应用中管理用户数据文件夹</span><span class="sxs-lookup"><span data-stu-id="b9c17-177">Manage User Data Folder in WebView2 apps</span></span>][Webview2ConceptsUserDataFolder]  
 
### <a name="how-to-guides"></a><span data-ttu-id="b9c17-178">How-To指南</span><span class="sxs-lookup"><span data-stu-id="b9c17-178">How-To guides</span></span>  

*   [<span data-ttu-id="b9c17-179">如何使用 WebView2 调试</span><span class="sxs-lookup"><span data-stu-id="b9c17-179">How to Debug with WebView2</span></span>][Webview2HowToDebug]  
*   [<span data-ttu-id="b9c17-180">使用驱动程序自动化和测试 WebView2 Microsoft Edge驱动程序</span><span class="sxs-lookup"><span data-stu-id="b9c17-180">Automating and testing WebView2 with Microsoft Edge Driver</span></span>][Webview2HowToWebdriver]  

## <a name="getting-in-touch-with-the-microsoft-edge-webview-team"></a><span data-ttu-id="b9c17-181">与 WebView 团队Microsoft Edge联系</span><span class="sxs-lookup"><span data-stu-id="b9c17-181">Getting in touch with the Microsoft Edge WebView team</span></span>  

[!INCLUDE [contact WebView team note](./includes/contact-webview-team-note.md)]  

<!-- links -->  

[Webview2ConceptsDistribution]: ./concepts/distribution.md "使用 WebView2 应用程序分配|Microsoft Docs"  
[Webview2ConceptsSecurity]: ./concepts/security.md "开发安全的 WebView2 应用和 web |Microsoft Docs"  
[Webview2ConceptsUserDataFolder]: ./concepts/user-data-folder.md "管理用户数据文件夹|Microsoft Docs"  
[Webview2ConceptsVersioning]: ./concepts/versioning.md "了解 WebView2 SDK |Microsoft Docs"  
[Webview2GetStartedWin32]: ./get-started/win32.md "WebView2 |Microsoft Docs"  
[Webview2GetStartedWinforms]: ./get-started/winforms.md "Windows Forms 应用中的 WebView2 (预览) |Microsoft Docs"  
[Webview2GetStartedWinui]: ./get-started/winui.md "WinUI3 预览版中的 WebView2 (入门) |Microsoft Docs"  
[Webview2GetStartedWpf]: ./get-started/wpf.md "WPF 预览版中的 WebView2 (入门) |Microsoft Docs"  
[Webview2HowToDebug]: ./how-to/debug.md "如何使用 WebView2 |Microsoft Docs"  
[Webview2HowToWebdriver]: ./how-to/webdriver.md "使用驱动程序测试工具自动Microsoft Edge WebView2 |Microsoft Docs"  
[Webview2ReleaseNotes]: ./release-notes.md "WebView2 SDK |Microsoft Docs"  

[UwpToolkitsWinui3]: /uwp/toolkits/winui3/index "WindowsUI Library 3 Preview 2 (2020 年 7 月) |Microsoft Docs"  

[DeployedgeMicrosoftEdgeSupportedOS]: /deployedge/microsoft-edge-supported-operating-systems "Microsoft Edge支持的操作系统|Microsoft Docs"  

[GithubMicrosoftedgeWebview2samples]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 示例 - MicrosoftEdge/WebView2Samples |GitHub"  
[GithubMicrosoftedgeWebviewfeddback]: https://github.com/MicrosoftEdge/WebViewFeedback "WebView 反馈 - MicrosoftEdge/WebViewFeedback |GitHub"  

[MicrosoftedgeinsiderMain]: https://www.microsoftedgeinsider.com "Microsoft Edge预览体验成员"  
[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "下载Microsoft Edge预览体验成员"  

[NugetPackagesMicrosoftWebWebView2]: https://www.nuget.org/packages/Microsoft.Web.WebView2 "Microsoft.Web.WebView2 |NuGet库"  
