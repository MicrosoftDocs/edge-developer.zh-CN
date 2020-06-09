---
description: 将 Win32 应用中的 web 内容托管到 Microsoft Edge Web 部件2控件中
title: Microsoft Edge WebView2 控件
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/21/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、CoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html、Windows Forms、WinForms、WPF、.NET
ms.openlocfilehash: 1b140d9f644c7a864cac4966bb4cfdd400feeb0d
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10697740"
---
# <span data-ttu-id="30863-104">Microsoft Edge WebView2 简介（预览版）</span><span class="sxs-lookup"><span data-stu-id="30863-104">Introduction to Microsoft Edge WebView2 (Preview)</span></span>  

<span data-ttu-id="30863-105">Microsoft Edge WebView2 控件使你能够在本机应用程序中嵌入 web 技术 \ （HTML、CSS 和 JavaScript \）。</span><span class="sxs-lookup"><span data-stu-id="30863-105">The Microsoft Edge WebView2 control enables you to embed web technologies \(HTML, CSS, and JavaScript\) in your native applications.</span></span>  <span data-ttu-id="30863-106">WebView2 控件使用[Microsoft Edge （Chromium）](https://www.microsoftedgeinsider.com)作为呈现引擎，以在本机应用程序中显示 web 内容。</span><span class="sxs-lookup"><span data-stu-id="30863-106">The WebView2 control uses [Microsoft Edge (Chromium)](https://www.microsoftedgeinsider.com) as the rendering engine to display the web content in native applications.</span></span>  <span data-ttu-id="30863-107">使用 WebView2，你可以将 web 代码嵌入本机应用程序的不同部分，或在单个 Web 视图中构建整个本机应用程序。</span><span class="sxs-lookup"><span data-stu-id="30863-107">With WebView2, you may embed web code in different parts of your native application, or build the entire native application within a single WebView.</span></span>  <span data-ttu-id="30863-108">有关如何开始构建 WebView2 应用程序的信息，请参阅[入门](./index.md#getting-started)。</span><span class="sxs-lookup"><span data-stu-id="30863-108">For information on how to start building a WebView2 application, see [Get Started](./index.md#getting-started).</span></span>  

:::image type="complex" source="./media/WebView2/whatwebview.png" alt-text="什么是 Web 视图":::
   <span data-ttu-id="30863-110">什么是 Web 视图</span><span class="sxs-lookup"><span data-stu-id="30863-110">What is WebView</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="30863-111">WebView2 Preview 适用于早期原型和收集反馈，以帮助对 API 进行整形。</span><span class="sxs-lookup"><span data-stu-id="30863-111">The WebView2 Preview is intended for early prototyping and to gather feedback to help to shape the API.</span></span>  <span data-ttu-id="30863-112">Microsoft Edge Web 图团队不建议在生产应用中使用预览，因为可能会[发生重大更改](./releasenotes.md)。</span><span class="sxs-lookup"><span data-stu-id="30863-112">The Microsoft Edge WebView team does not recommend that you use the preview in your production apps because there may be [breaking changes](./releasenotes.md).</span></span>  

## <span data-ttu-id="30863-113">混合应用程序方法</span><span class="sxs-lookup"><span data-stu-id="30863-113">Hybrid application approach</span></span>  

<span data-ttu-id="30863-114">开发人员通常必须在构建 web 应用程序或本机应用程序之间进行选择。</span><span class="sxs-lookup"><span data-stu-id="30863-114">Developers often have to choose between building a web application or a native application.</span></span>  <span data-ttu-id="30863-115">决策在接触和接通电源之间的平衡。</span><span class="sxs-lookup"><span data-stu-id="30863-115">The decision hinges on the trade-off between reach and power.</span></span>  <span data-ttu-id="30863-116">Web 应用程序允许广泛访问。</span><span class="sxs-lookup"><span data-stu-id="30863-116">Web applications allow for a broad reach.</span></span>  <span data-ttu-id="30863-117">作为 Web 开发人员，你可以在所有不同平台上重复使用大多数代码（如果不是所有代码）。</span><span class="sxs-lookup"><span data-stu-id="30863-117">As a Web developer, you may reuse most, if not all of your code, across all different platforms.</span></span>  <span data-ttu-id="30863-118">但是，本机应用程序利用整个本机平台的功能。</span><span class="sxs-lookup"><span data-stu-id="30863-118">Native applications, however, utilize the capabilities of the entire native platform.</span></span>  

:::image type="complex" source="./media/WebView2/webnative.png" alt-text="Web native":::
   <span data-ttu-id="30863-120">Web native</span><span class="sxs-lookup"><span data-stu-id="30863-120">Web native</span></span>  
:::image-end:::  

<span data-ttu-id="30863-121">混合应用程序使开发人员能够享受这两个领域的最佳体验。</span><span class="sxs-lookup"><span data-stu-id="30863-121">Hybrid applications allow developers to enjoy the best of both worlds.</span></span>  <span data-ttu-id="30863-122">混合应用程序开发人员受益于 web 平台的 ubiquity 和强项，以及本机平台的强大功能和完整功能。</span><span class="sxs-lookup"><span data-stu-id="30863-122">Hybrid application developers benefit from the ubiquity and strength of the web platform, and the power and full capabilities of the native platform.</span></span>  

## <span data-ttu-id="30863-123">WebView2 优惠</span><span class="sxs-lookup"><span data-stu-id="30863-123">WebView2 benefits</span></span>   

:::image type="complex" source="./media/WebView2/webviewreasons.png" alt-text="Web 视图原因":::
   <span data-ttu-id="30863-125">Web 视图原因</span><span class="sxs-lookup"><span data-stu-id="30863-125">WebView reasons</span></span>  
:::image-end:::  

:::row:::
   :::column span="1":::
      **<span data-ttu-id="30863-126">Web 生态系统 \ & skillset</span><span class="sxs-lookup"><span data-stu-id="30863-126">Web ecosystem \& skillset</span></span>**  
      <span data-ttu-id="30863-127">利用 web 生态系统中存在的整个 web 平台、库、工具和人才。</span><span class="sxs-lookup"><span data-stu-id="30863-127">Utilize the entire web platform, libraries, tooling, and talent that exists within the web ecosystem.</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="30863-128">快速创新</span><span class="sxs-lookup"><span data-stu-id="30863-128">Rapid innovation</span></span>**  
      <span data-ttu-id="30863-129">Web 开发允许更快的部署和迭代。</span><span class="sxs-lookup"><span data-stu-id="30863-129">Web development allows for faster deployment and iteration.</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="30863-130">Windows 7、8、10支持</span><span class="sxs-lookup"><span data-stu-id="30863-130">Windows 7, 8, 10 support</span></span>**  
      <span data-ttu-id="30863-131">在 Windows 7、8和10上支持一致的用户体验。</span><span class="sxs-lookup"><span data-stu-id="30863-131">Support for a consistent user experience across Windows 7, 8, and 10.</span></span>  
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="1":::
      **<span data-ttu-id="30863-132">本机功能</span><span class="sxs-lookup"><span data-stu-id="30863-132">Native capabilities</span></span>**  
      <span data-ttu-id="30863-133">访问完整的本机 Api 集。</span><span class="sxs-lookup"><span data-stu-id="30863-133">Access the full set of Native APIs.</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="30863-134">代码共享</span><span class="sxs-lookup"><span data-stu-id="30863-134">Code-sharing</span></span>**  
      <span data-ttu-id="30863-135">将 web 代码添加到你的基本代码，可在多个平台之间更好地重复使用。</span><span class="sxs-lookup"><span data-stu-id="30863-135">Add web code to your codebase allows for increased re-use across multiple platforms.</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="30863-136">Microsoft 支持</span><span class="sxs-lookup"><span data-stu-id="30863-136">Microsoft support</span></span>**  
      <span data-ttu-id="30863-137">Microsoft 在 WebView2 发布为 GA 时提供支持和添加新功能请求。</span><span class="sxs-lookup"><span data-stu-id="30863-137">Microsoft provides support and adds new feature requests when WebView2 is release as GA.</span></span>  
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="1":::
      **<span data-ttu-id="30863-138">长绿分布</span><span class="sxs-lookup"><span data-stu-id="30863-138">Evergreen distribution</span></span>**  
      <span data-ttu-id="30863-139">通过常规的平台更新和安全修补程序依赖最新版本的 Chromium。</span><span class="sxs-lookup"><span data-stu-id="30863-139">Rely on an up-to-date version of Chromium with regular platform updates and security patches.</span></span>  
   :::column-end:::
   :::column span="1":::
      <span data-ttu-id="30863-140">**固定**\ （即将推出 \）</span><span class="sxs-lookup"><span data-stu-id="30863-140">**Fixed** \(coming soon\)</span></span>  
      <span data-ttu-id="30863-141">选择将 Chromium 位打包在你的应用程序中。</span><span class="sxs-lookup"><span data-stu-id="30863-141">Choose to package the Chromium bits in your application.</span></span>  
   :::column-end:::
   :::column span="1":::
      **<span data-ttu-id="30863-142">增量采纳</span><span class="sxs-lookup"><span data-stu-id="30863-142">Incremental adoption</span></span>**  
      <span data-ttu-id="30863-143">将 web 组件逐个添加到应用程序。</span><span class="sxs-lookup"><span data-stu-id="30863-143">Add web components piece by piece to your application.</span></span>  
   :::column-end:::
:::row-end:::

## <span data-ttu-id="30863-144">即刻体验</span><span class="sxs-lookup"><span data-stu-id="30863-144">Getting started</span></span>  

<span data-ttu-id="30863-145">若要使用 WebView2 控件生成和测试你的应用程序，你需要安装[Microsoft Edge （Chromium）](https://www.microsoftedgeinsider.com/download)和[WebView2 SDK](https://aka.ms/webviewnuget) 。</span><span class="sxs-lookup"><span data-stu-id="30863-145">To build and test your application using the WebView2 control, you need to have both [Microsoft Edge (Chromium)](https://www.microsoftedgeinsider.com/download) and the [WebView2 SDK](https://aka.ms/webviewnuget) installed.</span></span>  <span data-ttu-id="30863-146">选择以下选项之一开始使用。</span><span class="sxs-lookup"><span data-stu-id="30863-146">Select one of the following options to get started.</span></span>  

*   [<span data-ttu-id="30863-147">Win32 C/c + + 入门</span><span class="sxs-lookup"><span data-stu-id="30863-147">Getting Started with Win32 C/C++</span></span>](./gettingstarted/win32.md)  
*   [<span data-ttu-id="30863-148">WPF 入门</span><span class="sxs-lookup"><span data-stu-id="30863-148">Getting Started with WPF</span></span>](./gettingstarted/wpf.md)  
*   [<span data-ttu-id="30863-149">WinForms 入门</span><span class="sxs-lookup"><span data-stu-id="30863-149">Getting Started with WinForms</span></span>](./gettingstarted/winforms.md)  

<span data-ttu-id="30863-150">[WebView2 示例](https://github.com/MicrosoftEdge/WebView2Samples)存储库包含演示所有 WebView2 sdk 功能和 API 使用模式的示例。</span><span class="sxs-lookup"><span data-stu-id="30863-150">The [WebView2 Samples](https://github.com/MicrosoftEdge/WebView2Samples) repository contains samples that demonstrate all of the WebView2 SDKs features and API usage patterns.</span></span> <span data-ttu-id="30863-151">随着将更多功能添加到 WebView2 SDK，示例应用程序将更新。</span><span class="sxs-lookup"><span data-stu-id="30863-151">As more features are added to the WebView2 SDK, the sample applications will be updated.</span></span>   

## <span data-ttu-id="30863-152">支持的平台</span><span class="sxs-lookup"><span data-stu-id="30863-152">Supported platforms</span></span>  

<span data-ttu-id="30863-153">开发人员预览版在以下编程环境中可用。</span><span class="sxs-lookup"><span data-stu-id="30863-153">A developer preview is available on the following programming environments.</span></span>  

*   <span data-ttu-id="30863-154">Win32 C/c + +</span><span class="sxs-lookup"><span data-stu-id="30863-154">Win32 C/C++</span></span>  
*   <span data-ttu-id="30863-155">.NET Framework 4.6.2 或更高版本</span><span class="sxs-lookup"><span data-stu-id="30863-155">.NET Framework 4.6.2 or later</span></span>  
*   <span data-ttu-id="30863-156">.NET Core 3.0 或更高版本</span><span class="sxs-lookup"><span data-stu-id="30863-156">.NET Core 3.0 or later</span></span>  
*   [<span data-ttu-id="30863-157">WinUI 3。0</span><span class="sxs-lookup"><span data-stu-id="30863-157">WinUI 3.0</span></span>](/uwp/toolkits/winui3/)  

<span data-ttu-id="30863-158">你可以在以下版本的 Windows 上运行 WebView2 应用程序。</span><span class="sxs-lookup"><span data-stu-id="30863-158">You are able to run WebView2 applications on the following versions of Windows.</span></span>  

*   <span data-ttu-id="30863-159">Windows 10</span><span class="sxs-lookup"><span data-stu-id="30863-159">Windows 10</span></span>  
*   <span data-ttu-id="30863-160">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="30863-160">Windows 8.1</span></span>  
*   <span data-ttu-id="30863-161">Windows 8</span><span class="sxs-lookup"><span data-stu-id="30863-161">Windows 8</span></span>  
*   <span data-ttu-id="30863-162">Windows7</span><span class="sxs-lookup"><span data-stu-id="30863-162">Windows 7</span></span>  
*   <span data-ttu-id="30863-163">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="30863-163">Windows Server 2016</span></span>  
*   <span data-ttu-id="30863-164">WindowsServer 2012</span><span class="sxs-lookup"><span data-stu-id="30863-164">Windows Server 2012</span></span>  
*   <span data-ttu-id="30863-165">Windows Server 2012R2</span><span class="sxs-lookup"><span data-stu-id="30863-165">Windows Server 2012R2</span></span>  
*   <span data-ttu-id="30863-166">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="30863-166">Windows Server 2008 R2</span></span>  

## <span data-ttu-id="30863-167">后续步骤</span><span class="sxs-lookup"><span data-stu-id="30863-167">Next steps</span></span>  

<span data-ttu-id="30863-168">有关如何构建和部署 WebView2 应用程序的更多详细信息，请参阅概念文档和操作方法指南。</span><span class="sxs-lookup"><span data-stu-id="30863-168">For more detailed information on how to build and deploy WebView2 applications, checkout the conceptual documentation and how-to guides.</span></span>  

#### <span data-ttu-id="30863-169">概念</span><span class="sxs-lookup"><span data-stu-id="30863-169">Concepts</span></span>  

*   [<span data-ttu-id="30863-170">WebView2 SDK 和 Microsoft Edge 版本控制</span><span class="sxs-lookup"><span data-stu-id="30863-170">WebView2 SDK and Microsoft Edge versioning</span></span>](./concepts/versioning.md)
*   [<span data-ttu-id="30863-171">分发 WebView2 应用程序</span><span class="sxs-lookup"><span data-stu-id="30863-171">Distributing WebView2 applications</span></span>](./concepts/distribution.md)  
 
#### <span data-ttu-id="30863-172">操作方法指南</span><span class="sxs-lookup"><span data-stu-id="30863-172">How-To guides</span></span>  

*   [<span data-ttu-id="30863-173">通过 DevTools 和 Visual Studio 脚本调试调试 WebView2</span><span class="sxs-lookup"><span data-stu-id="30863-173">Debugging WebView2 with DevTools and Visual Studio script debugging</span></span>](./howto/debug.md)  
*   [<span data-ttu-id="30863-174">通过 Microsoft EdgeDriver 自动化和调试 WebView2</span><span class="sxs-lookup"><span data-stu-id="30863-174">Automating and debugging WebView2 with Microsoft EdgeDriver</span></span>](./howto/webdriver.md)  

<!--todo: add how-tos when available  -->  

## <span data-ttu-id="30863-175">与 WebView2 团队取得联系</span><span class="sxs-lookup"><span data-stu-id="30863-175">Getting in touch with the WebView2 team</span></span>  

<span data-ttu-id="30863-176">通过分享你的反馈来帮助构建更丰富的 WebView2 体验。</span><span class="sxs-lookup"><span data-stu-id="30863-176">Help build a richer WebView2 experience by sharing your feedback.</span></span>  <span data-ttu-id="30863-177">访问 "Web 视图[反馈](https://aka.ms/webviewfeedback)" 存储库以提交功能请求或 bug 报告。</span><span class="sxs-lookup"><span data-stu-id="30863-177">Visit the WebView [feedback repo](https://aka.ms/webviewfeedback) to submit feature requests or bug reports.</span></span>  <span data-ttu-id="30863-178">它也是搜索已知问题的好地方。</span><span class="sxs-lookup"><span data-stu-id="30863-178">It is also a good place to search for known issues.</span></span>  

> [!NOTE]
> <span data-ttu-id="30863-179">在开发人员预览版期间，Microsoft Edge Web 图团队还会收集数据，以帮助构建更好的 Web 视图。</span><span class="sxs-lookup"><span data-stu-id="30863-179">During developer preview, the Microsoft Edge WebView team also collects data to help build a better WebView.</span></span>  <span data-ttu-id="30863-180">用户可以通过导航到 `edge://settings/privacy` Microsoft Edge 浏览器并关闭浏览器数据收集来关闭 Web 视图数据收集。</span><span class="sxs-lookup"><span data-stu-id="30863-180">Users may turn off WebView data collection by navigating to `edge://settings/privacy` in the Microsoft Edge browser and turning off browser data collection.</span></span>  
