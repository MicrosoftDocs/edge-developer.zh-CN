---
description: 辅助功能改进，使用其他语言的 DevTools 等。
title: DevTools (Microsoft Edge 80) 中的新增功能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 8f82f46cd683433a37614bcf15745e1de9f31ffb
ms.sourcegitcommit: b337717957529239434b4e8e1e167aebf0543518
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2020
ms.locfileid: "11015466"
---
<!-- Copyright Kayce Basques 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->  

# <span data-ttu-id="41e93-104">DevTools (Microsoft Edge 80) 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="41e93-104">What's new in DevTools (Microsoft Edge 80)</span></span>  

## <span data-ttu-id="41e93-105">来自 Microsoft Edge 开发人员工具团队公告</span><span class="sxs-lookup"><span data-stu-id="41e93-105">Announcements from the Microsoft Edge DevTools team</span></span>  

<span data-ttu-id="41e93-106">以下各部分是你可能错过的 Microsoft Edge 开发人员工具团队的公告列表！</span><span class="sxs-lookup"><span data-stu-id="41e93-106">The following sections are a list of announcements you may have missed from the Microsoft Edge DevTools team!</span></span> <span data-ttu-id="41e93-107">查看它们以尝试 DevTools、Visual Studio 代码扩展等中的新功能。</span><span class="sxs-lookup"><span data-stu-id="41e93-107">Check them out to try new features in the DevTools, Visual Studio Code extensions, and more.</span></span>  <span data-ttu-id="41e93-108">若要了解有关开发人员工具中的所有最新功能和最强大功能的最新动态，请下载 [Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels]并[在 Twitter 上关注我们][EdgeDevToolsTwitterAccount]。</span><span class="sxs-lookup"><span data-stu-id="41e93-108">To stay up to date on all the latest and greatest features in your developer tools, download the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] and [follow us on Twitter][EdgeDevToolsTwitterAccount].</span></span>  

### <span data-ttu-id="41e93-109">对 DevTools 的辅助功能改进</span><span class="sxs-lookup"><span data-stu-id="41e93-109">Accessibility improvements to the DevTools</span></span>  

<span data-ttu-id="41e93-110">DevTools 团队已向 Chromium 提供170更改，以解决 DevTools 中的高影响力颜色对比度、键盘和屏幕阅读器问题。</span><span class="sxs-lookup"><span data-stu-id="41e93-110">The DevTools team has contributed 170 changes to Chromium to address high-impact color contrast, keyboard, and screen reader issues in the DevTools.</span></span>  <span data-ttu-id="41e93-111">每个构建 web 的开发人员都应该能够使用 DevTools。</span><span class="sxs-lookup"><span data-stu-id="41e93-111">Every developer building the web should be able to use the DevTools.</span></span>  

:::image type="complex" source="../../images/2019/12/a11y-performance-tool.msft.gif" alt-text="DevTools 中的性能工具改进了键盘导航和屏幕阅读器" lightbox="../../images/2019/12/a11y-performance-tool.msft.gif":::
   <span data-ttu-id="41e93-113">DevTools 中的 **性能** 工具改进了键盘导航和屏幕阅读器</span><span class="sxs-lookup"><span data-stu-id="41e93-113">The **Performance** tool in the DevTools with the keyboard navigation and screen reader improvements</span></span>  
:::image-end:::  

<span data-ttu-id="41e93-114">希望了解如何让您的网页对所有用户都易于访问？</span><span class="sxs-lookup"><span data-stu-id="41e93-114">Want to learn how to make your web page accessible to all of your users?</span></span>  <span data-ttu-id="41e93-115">下载 Microsoft Edge 的 [辅助功能见解][AccessibilityInsights] 和 [webhint][WebhintBrowserExtension] 扩展以开始使用。</span><span class="sxs-lookup"><span data-stu-id="41e93-115">Download the [Accessibility Insights][AccessibilityInsights] and [webhint][WebhintBrowserExtension] extensions for Microsoft Edge to get started.</span></span>  

<span data-ttu-id="41e93-116">如果您使用屏幕阅读器或键盘在 DevTools 中导航，请 [发推至][PostTweetEdgeDevTools] "发送反馈" 或单击 " [发送反馈](#getting-in-touch-with-microsoft-edge-devtools-team) " 图标！</span><span class="sxs-lookup"><span data-stu-id="41e93-116">If you use screen readers or the keyboard to navigate around the DevTools, send your feedback by [tweeting][PostTweetEdgeDevTools] at us or clicking the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!</span></span>  

<span data-ttu-id="41e93-117">Chromium 问题 [#963183][CR963183]</span><span class="sxs-lookup"><span data-stu-id="41e93-117">Chromium issue [#963183][CR963183]</span></span>  

### <span data-ttu-id="41e93-118">使用其他语言的 DevTools</span><span class="sxs-lookup"><span data-stu-id="41e93-118">Using the DevTools in other languages</span></span>  

<span data-ttu-id="41e93-119">许多开发人员使用其他开发人员工具，如 StackOverflow 和 Visual Studio 代码，采用其母语，而不仅仅是英语。</span><span class="sxs-lookup"><span data-stu-id="41e93-119">Many developers use other developer tools, like StackOverflow and Visual Studio Code, in their native language, not just in English.</span></span>  <span data-ttu-id="41e93-120">我们很高兴宣布 DevTools 的本地化，您现在可以使用英语之外的10种语言中的一种：</span><span class="sxs-lookup"><span data-stu-id="41e93-120">We’re excited to announce localization for the DevTools, which you are now able to use in one of 10 languages besides English:</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="41e93-121"> (简体中文 \ ) - &#20013;&#25991;&#65288;&#31616;&#20307;&#65289;</span><span class="sxs-lookup"><span data-stu-id="41e93-121">Chinese \(Simplified\) - &#20013;&#25991;&#65288;&#31616;&#20307;&#65289;</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="41e93-122">中文 (传统版 \ ) - &#20013;&#25991;&#65288;&#32321;&#39636;&#65289;</span><span class="sxs-lookup"><span data-stu-id="41e93-122">Chinese \(Traditional\) - &#20013;&#25991;&#65288;&#32321;&#39636;&#65289;</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      <span data-ttu-id="41e93-123">法语-fran&#231;ais</span><span class="sxs-lookup"><span data-stu-id="41e93-123">French – fran&#231;ais</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="41e93-124">德语-德语</span><span class="sxs-lookup"><span data-stu-id="41e93-124">German - deutsch</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      <span data-ttu-id="41e93-125">意大利语-意大利语</span><span class="sxs-lookup"><span data-stu-id="41e93-125">Italian - italiano</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="41e93-126">日语- &#26085;&#26412;&#35486;</span><span class="sxs-lookup"><span data-stu-id="41e93-126">Japanese - &#26085;&#26412;&#35486;</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      <span data-ttu-id="41e93-127">朝鲜语- &#54620;&#44397;&#50612;</span><span class="sxs-lookup"><span data-stu-id="41e93-127">Korean - &#54620;&#44397;&#50612;</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="41e93-128">葡萄牙语-portugu&#234;s</span><span class="sxs-lookup"><span data-stu-id="41e93-128">Portuguese - portugu&#234;s</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      <span data-ttu-id="41e93-129">俄语–  &#1088;&#1091;&#1089;&#1089;&#1082;&#1080;&#1081;</span><span class="sxs-lookup"><span data-stu-id="41e93-129">Russian – &#1088;&#1091;&#1089;&#1089;&#1082;&#1080;&#1081;</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="41e93-130">西班牙语-espa&#241;ol</span><span class="sxs-lookup"><span data-stu-id="41e93-130">Spanish - espa&#241;ol</span></span>
   :::column-end:::
:::row-end:::

<!--  
|  |  |  
|:--- |:--- |  
| Chinese (Simplified) - 中文（简体）| Chinese (Traditional) - 中文（繁體）|  
| French – français | German - deutsch |  
| Italian - italiano | Portuguese - português |  
| Korean - 한국어 | Japanese - 日本語 |  
| Russian – русский | Spanish - español |  
-->  

<span data-ttu-id="41e93-131">导航到 `edge://flags` "启用已 **本地化的开发人员工具** " 标志并将其设置为 " **启用**"。</span><span class="sxs-lookup"><span data-stu-id="41e93-131">Navigate to `edge://flags` and set the **Enable localized Developer Tools** flag to **Enabled**.</span></span>  <span data-ttu-id="41e93-132">还将 " **开发工具" 试验** 标志设置为 " **启用**"。</span><span class="sxs-lookup"><span data-stu-id="41e93-132">Also set the **Developer Tools experiments** flag to **Enabled**.</span></span>  <span data-ttu-id="41e93-133">重启 Microsoft Edge 并打开 DevTools。</span><span class="sxs-lookup"><span data-stu-id="41e93-133">Restart Microsoft Edge and open the DevTools.</span></span>  <!-- Press `F1` in the DevTools or go to Settings > Experiments and check the **Match browser language** checkbox.  -->  <span data-ttu-id="41e93-134">DevTools 与你用于 Microsoft Edge 的语言相匹配 `edge://settings/languages` 。</span><span class="sxs-lookup"><span data-stu-id="41e93-134">The DevTools match the language you use for Microsoft Edge in `edge://settings/languages`.</span></span>  

:::image type="complex" source="../../images/2019/12/localized-devtools.msft.png" alt-text="DevTools 中的性能工具改进了键盘导航和屏幕阅读器" lightbox="../../images/2019/12/localized-devtools.msft.png":::
   <span data-ttu-id="41e93-136">德语中的 DevTools</span><span class="sxs-lookup"><span data-stu-id="41e93-136">The DevTools in German</span></span>  
:::image-end:::  

<span data-ttu-id="41e93-137">如果您想要使用的 DevTools 语言与可用的语言不同，请 [tweet][PostTweetEdgeDevTools] ，或单击 " [发送反馈](#getting-in-touch-with-microsoft-edge-devtools-team) " 图标。</span><span class="sxs-lookup"><span data-stu-id="41e93-137">If you want to use the DevTools in a different language than the ones that are available, [tweet][PostTweetEdgeDevTools] at us or click the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon.</span></span>  

<span data-ttu-id="41e93-138">Chromium 问题 [#941561][CR941561]</span><span class="sxs-lookup"><span data-stu-id="41e93-138">Chromium issue [#941561][CR941561]</span></span>  

### <span data-ttu-id="41e93-139">webhint Microsoft Edge 扩展</span><span class="sxs-lookup"><span data-stu-id="41e93-139">webhint Microsoft Edge extension</span></span>  

<span data-ttu-id="41e93-140">Webhint Microsoft Edge 扩展使你能够轻松地浏览网页并在 DevTools 中获取有关辅助功能、浏览器兼容性、安全性、性能等的反馈。</span><span class="sxs-lookup"><span data-stu-id="41e93-140">The webhint Microsoft Edge extension allows you to easily scan your web page and get feedback on accessibility, browser compatibility, security, performance, and more within the DevTools.</span></span>  <span data-ttu-id="41e93-141">阅读详细信息 [https://webhint.io][Webhint] 。</span><span class="sxs-lookup"><span data-stu-id="41e93-141">Read more at [https://webhint.io][Webhint].</span></span>  

:::image type="complex" source="../../images/2019/12/webhint-browser-extension.msft.png" alt-text="DevTools 中的性能工具改进了键盘导航和屏幕阅读器" lightbox="../../images/2019/12/webhint-browser-extension.msft.png":::
   <span data-ttu-id="41e93-143">安装 webhint 浏览器扩展时，DevTools 中的 " **提示** " 选项卡</span><span class="sxs-lookup"><span data-stu-id="41e93-143">The **Hints** tab in the DevTools when the webhint browser extension is installed</span></span>  
:::image-end:::  

<span data-ttu-id="41e93-144">[在 Microsoft Edge 中尝试 webhint 浏览器扩展][MicrosoftEdgeInsiderAddons]。</span><span class="sxs-lookup"><span data-stu-id="41e93-144">[Try the webhint browser extension in Microsoft Edge][MicrosoftEdgeInsiderAddons].</span></span>  <span data-ttu-id="41e93-145">安装扩展后，打开 DevTools 并选择 "提示" 选项卡。 在此处，运行可自定义的网站扫描。</span><span class="sxs-lookup"><span data-stu-id="41e93-145">Once you install the extension, open the DevTools and select the Hints tab.  From here, run a customizable site scan.</span></span>  <span data-ttu-id="41e93-146">请转到 [webhint.io][WebhintBrowserExtension] 以了解更多信息。</span><span class="sxs-lookup"><span data-stu-id="41e93-146">Head over to [webhint.io][WebhintBrowserExtension] to learn more.</span></span>

### <span data-ttu-id="41e93-147">3D 视图</span><span class="sxs-lookup"><span data-stu-id="41e93-147">3D View</span></span>  

<span data-ttu-id="41e93-148">通过浏览[文档对象模型 (DOM \ ) ][MDNDocumentObjectModel]或[z 索引][MDNZIndex]堆栈上下文，使用**3d 视图**调试 web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="41e93-148">Use the **3D View** to debug your web application by navigating through the [Document Object Model \(DOM\)][MDNDocumentObjectModel] or the [z-index][MDNZIndex] stacking context.</span></span>  

:::image type="complex" source="../../images/2019/12/3dview.msft.png" alt-text="DevTools 中的性能工具改进了键盘导航和屏幕阅读器" lightbox="../../images/2019/12/3dview.msft.png":::
   <span data-ttu-id="41e93-150">DevTools 中的**3D 视图**</span><span class="sxs-lookup"><span data-stu-id="41e93-150">The **3D View** in the DevTools</span></span>  
:::image-end:::  

<span data-ttu-id="41e93-151">若要访问3D 视图，请导航到 `edge://flags` 并确保 " **开发人员工具实验** " 标志设置为 " **已启用**"。</span><span class="sxs-lookup"><span data-stu-id="41e93-151">To access the 3D View, navigate to `edge://flags` and ensure that the **Developer Tools experiments** flag is set to **Enabled**.</span></span>  <span data-ttu-id="41e93-152">重启 Microsoft Edge 并打开 DevTools。</span><span class="sxs-lookup"><span data-stu-id="41e93-152">Restart Microsoft Edge and open the DevTools.</span></span>  <span data-ttu-id="41e93-153">按 `F1` DevTools 或转到 " **设置**"，导航到 " **实验** " 部分，然后选中 " **启用3d 视图** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="41e93-153">Press `F1` in the DevTools or go to **Settings**, navigate to **Experiments** section, and check the **Enable 3D View** checkbox.</span></span>  <span data-ttu-id="41e93-154">现在，请按 `Ctrl`  +  `Shift`  +  `P` ，在**3d 视图**中键入，然后选择 "**显示3d 视图**"。</span><span class="sxs-lookup"><span data-stu-id="41e93-154">Now, press `Ctrl` + `Shift` + `P`, type in **3D View** and select **Show 3D View**.</span></span>  

<span data-ttu-id="41e93-155">我们正在处理 UI 并向3D 视图添加更多功能，请向我们发送您的 [反馈](#getting-in-touch-with-microsoft-edge-devtools-team)。</span><span class="sxs-lookup"><span data-stu-id="41e93-155">We're working on the UI and adding more functionality to the 3D View so please send us your [feedback](#getting-in-touch-with-microsoft-edge-devtools-team).</span></span>  

<span data-ttu-id="41e93-156">Chromium 问题 [#987787][CR987787]</span><span class="sxs-lookup"><span data-stu-id="41e93-156">Chromium issue [#987787][CR987787]</span></span>

### <span data-ttu-id="41e93-157">Visual Studio 代码扩展</span><span class="sxs-lookup"><span data-stu-id="41e93-157">Visual Studio Code extensions</span></span>  

<span data-ttu-id="41e93-158">DevTools 团队还发布了一些适用于 [Visual Studio 代码][VisualStudioCode] 的扩展，可让你直接从文本编辑器使用 DevTools 的强大功能。</span><span class="sxs-lookup"><span data-stu-id="41e93-158">The DevTools team has also released some extensions for [Visual Studio Code][VisualStudioCode] that let you use the power of the DevTools directly from your text editor.</span></span> <span data-ttu-id="41e93-159">查看以下扩展。</span><span class="sxs-lookup"><span data-stu-id="41e93-159">Check out the following extensions.</span></span>  

#### <span data-ttu-id="41e93-160">Microsoft Edge 元素</span><span class="sxs-lookup"><span data-stu-id="41e93-160">Elements for Microsoft Edge</span></span>  

<span data-ttu-id="41e93-161">通过添加 [Microsoft Edge (Chromium) ][VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension] Visual studio 代码扩展中的元素，从 Visual studio 代码中使用元素工具。</span><span class="sxs-lookup"><span data-stu-id="41e93-161">Use the Elements tool from within Visual Studio Code by adding the [Elements for Microsoft Edge (Chromium)][VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension] Visual Studio Code extension.</span></span>  

:::image type="complex" source="../../images/2019/12/elements-for-edge.msft.png" alt-text="DevTools 中的性能工具改进了键盘导航和屏幕阅读器" lightbox="../../images/2019/12/elements-for-edge.msft.png":::
   <span data-ttu-id="41e93-163">Visual Studio 代码中使用 Microsoft Edge 扩展的元素的 **元素** 工具</span><span class="sxs-lookup"><span data-stu-id="41e93-163">The **Elements** tool in Visual Studio Code using the Elements for Microsoft Edge extension</span></span>  
:::image-end:::  

<span data-ttu-id="41e93-164">有关详细信息，请查看 [Microsoft Edge Visual Studio 代码扩展的元素][VisualStudioCodeElementEdgeExtension]。</span><span class="sxs-lookup"><span data-stu-id="41e93-164">For more information, check out [Elements for Microsoft Edge Visual Studio Code extension][VisualStudioCodeElementEdgeExtension].</span></span>  

#### <span data-ttu-id="41e93-165">Microsoft Edge 调试器</span><span class="sxs-lookup"><span data-stu-id="41e93-165">Debugger for Microsoft Edge</span></span>  

<span data-ttu-id="41e93-166">通过 [适用于 Microsoft edge][VisualStudioMarketplaceDebuggerEdge] Visual Studio 代码扩展的调试器，直接从 Visual Studio 代码调试在 Microsoft edge 中运行的 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="41e93-166">With the [Debugger for Microsoft Edge][VisualStudioMarketplaceDebuggerEdge] Visual Studio Code extension, debug JavaScript running in Microsoft Edge directly from Visual Studio Code.</span></span>  

:::image type="complex" source="../../images/2019/12/vscode-debugger.msft.png" alt-text="DevTools 中的性能工具改进了键盘导航和屏幕阅读器" lightbox="../../images/2019/12/vscode-debugger.msft.png":::
   <span data-ttu-id="41e93-168">Visual Studio 代码中 Microsoft Edge 扩展的调试器</span><span class="sxs-lookup"><span data-stu-id="41e93-168">The Debugger for Microsoft Edge Extension in Visual Studio Code</span></span>  
:::image-end:::  

<span data-ttu-id="41e93-169">有关详细信息，请参阅 [如何从 Visual Studio 代码调试 Microsoft Edge][VisualStudioCodeDebuggerEdgeExtension]。</span><span class="sxs-lookup"><span data-stu-id="41e93-169">For more information, check out [how to debug Microsoft Edge from Visual Studio Code][VisualStudioCodeDebuggerEdgeExtension].</span></span>  

#### <span data-ttu-id="41e93-170">webhint</span><span class="sxs-lookup"><span data-stu-id="41e93-170">webhint</span></span>  

<span data-ttu-id="41e93-171">当你编写网页时， [webhint][VisualStudioMarketplaceWebhintExtension] Visual Studio 代码扩展使用 `webhint` 它来改进网页！</span><span class="sxs-lookup"><span data-stu-id="41e93-171">The [webhint][VisualStudioMarketplaceWebhintExtension] Visual Studio Code extension uses `webhint` to improve your web page while you're writing it!</span></span> <span data-ttu-id="41e93-172">此扩展基于分析对工作区文件运行和报告诊断 `webhint` 。</span><span class="sxs-lookup"><span data-stu-id="41e93-172">This extension runs and reports diagnostics on your workspace files based on `webhint` analysis.</span></span>  

:::image type="complex" source="../../images/2019/12/webhint-vscode-extension.msft.png" alt-text="DevTools 中的性能工具改进了键盘导航和屏幕阅读器" lightbox="../../images/2019/12/webhint-vscode-extension.msft.png":::
   <span data-ttu-id="41e93-174">`.tsx`在 Visual Studio 代码中分析文件的 Webhint Visual Studio 代码扩展</span><span class="sxs-lookup"><span data-stu-id="41e93-174">The webhint Visual Studio Code extension analyzing a `.tsx` file in Visual Studio Code</span></span>  
:::image-end:::  

<span data-ttu-id="41e93-175">[了解有关 Visual Studio 代码 webhint 扩展的详细信息][WebhintVisualStudioCodeExtension]。</span><span class="sxs-lookup"><span data-stu-id="41e93-175">[Learn more about the Visual Studio Code webhint extension][WebhintVisualStudioCodeExtension].</span></span>  

### <span data-ttu-id="41e93-176">Visual Studio 集成</span><span class="sxs-lookup"><span data-stu-id="41e93-176">Visual Studio integration</span></span>
<span data-ttu-id="41e93-177">在 Visual Studio 2019 版本16.2 或更高版本中，使用 Visual Studio 调试器调试在 Microsoft Edge 中运行的 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="41e93-177">In Visual Studio 2019 version 16.2 or later, use the Visual Studio debugger to debug JavaScript running in Microsoft Edge.</span></span>  <span data-ttu-id="41e93-178">[下载 Visual Studio 2019][MicrosoftVisualStudioDownloads] 以试用此功能！</span><span class="sxs-lookup"><span data-stu-id="41e93-178">[Download Visual Studio 2019][MicrosoftVisualStudioDownloads] to try this feature out!</span></span>  

:::image type="complex" source="../../images/2019/12/vs.msft.png" alt-text="DevTools 中的性能工具改进了键盘导航和屏幕阅读器" lightbox="../../images/2019/12/vs.msft.png":::
   <span data-ttu-id="41e93-180">带有在 Microsoft Edge 的 "应用"、"开发" 或 "Beta" 中启动 web 应用选项的 Visual Studio</span><span class="sxs-lookup"><span data-stu-id="41e93-180">Visual Studio with the option to launch your web app in Microsoft Edge Canary, Dev, or Beta</span></span>  
:::image-end:::  

<span data-ttu-id="41e93-181">[阅读我们的博客文章，了解如何从 Visual Studio 调试 Microsoft Edge][MicrosoftVisualStudioBlogDebugJavascript]。</span><span class="sxs-lookup"><span data-stu-id="41e93-181">[Read our blog post to learn how to debug Microsoft Edge from Visual Studio][MicrosoftVisualStudioBlogDebugJavascript].</span></span>  

### <span data-ttu-id="41e93-182">跟踪保护控制台消息</span><span class="sxs-lookup"><span data-stu-id="41e93-182">Tracking prevention Console messages</span></span>  

<span data-ttu-id="41e93-183">"跟踪防护" 是 Microsoft Edge 中的一项独特功能，可防止您以前未访问过的网站对您进行跟踪。</span><span class="sxs-lookup"><span data-stu-id="41e93-183">Tracking prevention is a unique feature in Microsoft Edge that protects you from being tracked by websites you haven't visited before.</span></span>  <span data-ttu-id="41e93-184">默认跟踪防护设置为平衡模式，这将阻止第三方跟踪程序和已知恶意跟踪程序，以获取平衡隐私和 web 兼容性的体验。</span><span class="sxs-lookup"><span data-stu-id="41e93-184">The default tracking prevention setting is Balanced mode, which blocks 3rd party trackers and known malicious trackers for an experience that balances privacy and web compatibility.</span></span>  <span data-ttu-id="41e93-185">若要在某些跟踪器被阻止时更深入地了解网页的兼容性，我们还在跟踪器被阻止时在控制台中添加了警告消息。</span><span class="sxs-lookup"><span data-stu-id="41e93-185">To give you more insight into the compatibility of your web page when certain trackers are blocked, we've also added warning messages in the Console when a tracker is blocked.</span></span>  

:::image type="complex" source="../../images/2019/12/tracking-prevention.msft.png" alt-text="DevTools 中的性能工具改进了键盘导航和屏幕阅读器" lightbox="../../images/2019/12/tracking-prevention.msft.png":::
   <span data-ttu-id="41e93-187">跟踪阻止阻止跟踪对存储的访问权限时的 **控制台** 中的消息</span><span class="sxs-lookup"><span data-stu-id="41e93-187">Messages in the **Console** when tracking prevention blocks access to storage for a tracker</span></span>  
:::image-end:::  

<span data-ttu-id="41e93-188">[阅读有关跟踪防护和隐私和 web 兼容性之间的平衡的详细信息][TrackingPrevention]。</span><span class="sxs-lookup"><span data-stu-id="41e93-188">[Read more about tracking prevention and the balance between privacy and web compatibility][TrackingPrevention].</span></span>  

## <span data-ttu-id="41e93-189">来自 Chromium 项目的公告</span><span class="sxs-lookup"><span data-stu-id="41e93-189">Announcements from the Chromium project</span></span>  

<span data-ttu-id="41e93-190">以下各节宣布了在 Microsoft Edge 80 中提供的其他功能，这些功能由开放的源 Chromium 项目所参与。</span><span class="sxs-lookup"><span data-stu-id="41e93-190">The following sections announce additional features available in Microsoft Edge 80 that were contributed to the open source Chromium project.</span></span>  

### <span data-ttu-id="41e93-191">在控制台中支持 let 和 class redeclarations</span><span class="sxs-lookup"><span data-stu-id="41e93-191">Support for let and class redeclarations in the Console</span></span>  

<span data-ttu-id="41e93-192">现在，该 **控制台** 支持 redeclarations `let` 和 `class` 语句。</span><span class="sxs-lookup"><span data-stu-id="41e93-192">The **Console** now supports redeclarations of `let` and `class` statements.</span></span>  <span data-ttu-id="41e93-193">如果 web 开发人员使用控制台体验新的 JavaScript 代码，则无法重新声明。</span><span class="sxs-lookup"><span data-stu-id="41e93-193">The inability to redeclare was a common annoyance for web developers who use the Console to experiment with new JavaScript code.</span></span>  

> [!WARNING]
> <span data-ttu-id="41e93-194">`let` `class` 在控制台外或单个控制台输入中的脚本中 Redeclaring 或语句仍会导致 a `SyntaxError` 。</span><span class="sxs-lookup"><span data-stu-id="41e93-194">Redeclaring a `let` or `class` statement in a script outside of the Console or within a single Console input still causes a `SyntaxError`.</span></span>  

<span data-ttu-id="41e93-195">例如，以前，当重新声明本地变量时 `let` ，控制台引发错误：</span><span class="sxs-lookup"><span data-stu-id="41e93-195">For example, previously, when re-declaring a local variable with `let`, the Console threw an error:</span></span>  

:::image type="complex" source="../../images/2019/12/letbefore.msft.png" alt-text="DevTools 中的性能工具改进了键盘导航和屏幕阅读器" lightbox="../../images/2019/12/letbefore.msft.png":::
   <span data-ttu-id="41e93-197">Microsoft Edge 79 中的 **控制台** ，显示 "允许重新声明" 失败</span><span class="sxs-lookup"><span data-stu-id="41e93-197">The **Console** in Microsoft Edge 79 showing that the let re-declaration fails</span></span>  
:::image-end:::  

<span data-ttu-id="41e93-198">现在，该控制台允许重新声明：</span><span class="sxs-lookup"><span data-stu-id="41e93-198">Now, the Console allows the redeclaration:</span></span>  

:::image type="complex" source="../../images/2019/12/letafter.msft.png" alt-text="DevTools 中的性能工具改进了键盘导航和屏幕阅读器" lightbox="../../images/2019/12/letafter.msft.png":::
   <span data-ttu-id="41e93-200">Microsoft Edge 80 中的 **控制台** ，显示 "允许重新声明" 成功</span><span class="sxs-lookup"><span data-stu-id="41e93-200">The **Console** in Microsoft Edge 80 showing that the let re-declaration succeeds</span></span>  
:::image-end:::  

<span data-ttu-id="41e93-201">Chromium 问题 [#1004193][CR1004193]</span><span class="sxs-lookup"><span data-stu-id="41e93-201">Chromium issue [#1004193][CR1004193]</span></span>  

### <span data-ttu-id="41e93-202">改进的 WebAssembly 调试</span><span class="sxs-lookup"><span data-stu-id="41e93-202">Improved WebAssembly debugging</span></span>  

<span data-ttu-id="41e93-203">DevTools 已开始支持 [DWARF 调试标准][DwarfHome]，这意味着增加了对代码执行的支持、设置断点以及解析 DevTools 中的源语言的堆栈跟踪。</span><span class="sxs-lookup"><span data-stu-id="41e93-203">DevTools has started to support the [DWARF Debugging Standard][DwarfHome], which means increased support for stepping over code, setting breakpoints, and resolving stack traces in your source languages within DevTools.</span></span>  

<!-- [TODO: Add this link back] -->  
<!--Check out [Improved WebAssembly debugging in Microsoft Edge DevTools][201912Webassembly] for the full story.  -->  

<!-- [TODO: Replace this image with screenshot in Edge] -->  
<!--
:::image type="complex" source="../../images/2019/12/wasm.msft.png" alt-text="DevTools 中的性能工具改进了键盘导航和屏幕阅读器" lightbox="../../images/2019/12/wasm.msft.png":::
   The new DWARF-powered WebAssembly debugging  
:::image-end:::  
-->  

### <span data-ttu-id="41e93-204">网络面板更新</span><span class="sxs-lookup"><span data-stu-id="41e93-204">Network panel updates</span></span>  

#### <span data-ttu-id="41e93-205">在 "启动器" 选项卡中请求启动器链</span><span class="sxs-lookup"><span data-stu-id="41e93-205">Request Initiator Chains in the Initiator tab</span></span>  

<span data-ttu-id="41e93-206">现在，你可以查看作为嵌套列表的网络请求的发起方和依赖关系。</span><span class="sxs-lookup"><span data-stu-id="41e93-206">You are now able to view the initiators and dependencies of a network request as a nested list.</span></span>  <span data-ttu-id="41e93-207">这可能会帮助你了解请求资源的原因或特定资源的哪些网络活动 (如脚本 \ ) 导致的。</span><span class="sxs-lookup"><span data-stu-id="41e93-207">This may help you understand why a resource was requested, or what network activity a certain resource \(such as a script\) caused.</span></span>  

:::image type="complex" source="../../images/2019/12/initiators.msft.png" alt-text="DevTools 中的性能工具改进了键盘导航和屏幕阅读器" lightbox="../../images/2019/12/initiators.msft.png":::
   <span data-ttu-id="41e93-209">" **启动器** " 选项卡中的请求发起人链</span><span class="sxs-lookup"><span data-stu-id="41e93-209">A Request Initiator Chain in the **Initiator** tab</span></span>  
:::image-end:::  

<span data-ttu-id="41e93-210">[在 "网络" 面板中记录网络活动][DevToolsNetworkIndex]后，单击资源，然后转到 "**启动器**" 选项卡以查看**请求启动器链**：</span><span class="sxs-lookup"><span data-stu-id="41e93-210">After [logging network activity in the Network panel][DevToolsNetworkIndex], click a resource and then go to the **Initiator** tab to view the **Request Initiator Chain**:</span></span>  

*   <span data-ttu-id="41e93-211">已 **检查的资源** 为粗体。</span><span class="sxs-lookup"><span data-stu-id="41e93-211">The **inspected resource** is bold.</span></span>  <span data-ttu-id="41e93-212">在上面的屏幕截图中， `ai.2.min.js` 是已检查的资源。</span><span class="sxs-lookup"><span data-stu-id="41e93-212">In the screenshot above, `ai.2.min.js` is the inspected resource.</span></span>  
*   <span data-ttu-id="41e93-213">已检查资源上方的资源是 **启动器**。</span><span class="sxs-lookup"><span data-stu-id="41e93-213">The resources above the inspected resource are the **initiators**.</span></span>  <span data-ttu-id="41e93-214">在上面的屏幕截图中， `https://www.microsoftedgeinsider.com` 是的发起人 `ai.2.min.js` 。</span><span class="sxs-lookup"><span data-stu-id="41e93-214">In the screenshot above, `https://www.microsoftedgeinsider.com` is the initiator of `ai.2.min.js`.</span></span>  <span data-ttu-id="41e93-215">换句话说， `https://www.microsoftedgeinsider.com` 导致网络请求 `ai.2.min.js` 。</span><span class="sxs-lookup"><span data-stu-id="41e93-215">In other words, `https://www.microsoftedgeinsider.com` caused the network request for `ai.2.min.js`.</span></span>  
*   <span data-ttu-id="41e93-216">已检查资源下方的资源是 **依赖关系**。</span><span class="sxs-lookup"><span data-stu-id="41e93-216">The resources below the inspected resource are the **dependencies**.</span></span>  <span data-ttu-id="41e93-217">在上面的屏幕截图中， `https://dc.services.visualstudio.com/v2/track` 是的依赖项 `ai.2.min.js` 。</span><span class="sxs-lookup"><span data-stu-id="41e93-217">In the screenshot above, `https://dc.services.visualstudio.com/v2/track` is a dependency of `ai.2.min.js`.</span></span>  <span data-ttu-id="41e93-218">换句话说， `ai.2.min.js` 导致网络请求 `https://dc.services.visualstudio.com/v2/track` 。</span><span class="sxs-lookup"><span data-stu-id="41e93-218">In other words, `ai.2.min.js` caused the network request for `https://dc.services.visualstudio.com/v2/track`.</span></span>  

> [!NOTE]
> <span data-ttu-id="41e93-219">也可以通过按住 `Shift` 网络资源并将鼠标悬停在网络资源上来访问启动器和相关性信息。</span><span class="sxs-lookup"><span data-stu-id="41e93-219">Initiator and dependency information may also be accessed by holding `Shift` and then hovering over network resources.</span></span>  <span data-ttu-id="41e93-220">请参阅 [查看发起人和依赖关系][DevToolsNetworkReferenceViewInitiatorsDependencies]。</span><span class="sxs-lookup"><span data-stu-id="41e93-220">See [View initiators and dependencies][DevToolsNetworkReferenceViewInitiatorsDependencies].</span></span>  

<span data-ttu-id="41e93-221">Chromium 问题 [#842488][CR842488]</span><span class="sxs-lookup"><span data-stu-id="41e93-221">Chromium issue [#842488][CR842488]</span></span>  

#### <span data-ttu-id="41e93-222">在概述中突出显示所选的网络请求</span><span class="sxs-lookup"><span data-stu-id="41e93-222">Highlight the selected network request in the Overview</span></span>  

<span data-ttu-id="41e93-223">单击网络资源以对其进行检查后，网络面板 **现在将在**该资源周围放置一个蓝色边框。</span><span class="sxs-lookup"><span data-stu-id="41e93-223">After you click a network resource in order to inspect it, the Network panel now puts a blue border around that resource in the **Overview**.</span></span>  <span data-ttu-id="41e93-224">这可以帮助你检测网络请求在之前或之后是否比预期发生。</span><span class="sxs-lookup"><span data-stu-id="41e93-224">This is able to help you detect if the network request is happening earlier or later than expected.</span></span>  

:::image type="complex" source="../../images/2019/12/overview.msft.png" alt-text="DevTools 中的性能工具改进了键盘导航和屏幕阅读器" lightbox="../../images/2019/12/overview.msft.png":::
   <span data-ttu-id="41e93-226">突出显示已检查资源的 **概述** 窗格</span><span class="sxs-lookup"><span data-stu-id="41e93-226">The **Overview** pane highlighting the inspected resource</span></span>  
:::image-end:::  

<span data-ttu-id="41e93-227">Chromium 问题 [#988253][CR988253]</span><span class="sxs-lookup"><span data-stu-id="41e93-227">Chromium issue [#988253][CR988253]</span></span>  

#### <span data-ttu-id="41e93-228">"网络" 面板中的 URL 和路径列</span><span class="sxs-lookup"><span data-stu-id="41e93-228">URL and path columns in the Network panel</span></span>  

<span data-ttu-id="41e93-229">使用 "**网络**" 面板中的 "新**路径**" 和 " **URL** " 列查看每个网络资源的绝对路径或完整 url。</span><span class="sxs-lookup"><span data-stu-id="41e93-229">Use the new **Path** and **URL** columns in the **Network** panel to see the absolute path or full URL of each network resource.</span></span>  

:::image type="complex" source="../../images/2019/12/columns.msft.png" alt-text="DevTools 中的性能工具改进了键盘导航和屏幕阅读器" lightbox="../../images/2019/12/columns.msft.png":::
   <span data-ttu-id="41e93-231">" **网络** " 面板中的新路径和 URL 列</span><span class="sxs-lookup"><span data-stu-id="41e93-231">The new Path and URL columns in the **Network** panel</span></span>  
:::image-end:::  

<span data-ttu-id="41e93-232">右键单击 **瀑布** 表标题，然后选择 " **路径** " 或 " **URL** " 以显示新列。</span><span class="sxs-lookup"><span data-stu-id="41e93-232">Right-click the **Waterfall** table header and select **Path** or **URL** to show the new columns.</span></span>  

<span data-ttu-id="41e93-233">Chromium 问题 [#993366][CR993366]</span><span class="sxs-lookup"><span data-stu-id="41e93-233">Chromium issue [#993366][CR993366]</span></span>  

#### <span data-ttu-id="41e93-234">已更新的用户代理字符串</span><span class="sxs-lookup"><span data-stu-id="41e93-234">Updated User-Agent strings</span></span>  

<span data-ttu-id="41e93-235">DevTools 支持通过 " **网络条件** " 选项卡设置自定义用户代理字符串。 用户代理字符串会影响 `User-Agent` 附加到网络资源的 HTTP 标头以及的值 `navigator.userAgent` 。</span><span class="sxs-lookup"><span data-stu-id="41e93-235">DevTools supports setting a custom User-Agent string through the **Network Conditions** tab.  The User-Agent string affects the `User-Agent` HTTP header attached to network resources, and also the value of `navigator.userAgent`.</span></span>  

<span data-ttu-id="41e93-236">预定义的用户代理字符串已更新，以反映新式浏览器版本。</span><span class="sxs-lookup"><span data-stu-id="41e93-236">The predefined User-Agent strings have been updated to reflect modern browser versions.</span></span>  

:::image type="complex" source="../../images/2019/12/useragent.msft.png" alt-text="DevTools 中的性能工具改进了键盘导航和屏幕阅读器" lightbox="../../images/2019/12/useragent.msft.png":::
   <span data-ttu-id="41e93-238">" **网络条件** " 选项卡中的 "用户代理" 菜单</span><span class="sxs-lookup"><span data-stu-id="41e93-238">The User Agent menu in the **Network Conditions** tab</span></span>  
:::image-end:::  

<span data-ttu-id="41e93-239">若要访问 **网络条件**，请 [打开命令菜单][DevToolsCommandMenuIndex] 并运行 `Show Network Conditions` 命令。</span><span class="sxs-lookup"><span data-stu-id="41e93-239">To access **Network Conditions**, [open the Command Menu][DevToolsCommandMenuIndex] and run the `Show Network Conditions` command.</span></span>  

> [!NOTE]
> <span data-ttu-id="41e93-240">您也可以 [在设备模式下设置用户代理的字符串][DevToolsDeviceModeIndex]。</span><span class="sxs-lookup"><span data-stu-id="41e93-240">You may also [set User-Agent strings in Device Mode][DevToolsDeviceModeIndex].</span></span>  

<span data-ttu-id="41e93-241">Chromium 问题 [#1029031][CR1029031]</span><span class="sxs-lookup"><span data-stu-id="41e93-241">Chromium issue [#1029031][CR1029031]</span></span>  

### <span data-ttu-id="41e93-242">"审核" 面板更新</span><span class="sxs-lookup"><span data-stu-id="41e93-242">Audits panel updates</span></span>  

#### <span data-ttu-id="41e93-243">新的配置 UI</span><span class="sxs-lookup"><span data-stu-id="41e93-243">New configuration UI</span></span>  

<span data-ttu-id="41e93-244">配置 UI 具有新的响应式设计，并且限制配置选项已简化。</span><span class="sxs-lookup"><span data-stu-id="41e93-244">The configuration UI has a new, responsive design, and the throttling configuration options have been simplified.</span></span>  <span data-ttu-id="41e93-245">有关限制 UI 更改的详细信息，请参阅 [审核面板限制][GitHubGoogleChromeDevToolsAuditsPanelThrottling] 。</span><span class="sxs-lookup"><span data-stu-id="41e93-245">See [Audits Panel Throttling][GitHubGoogleChromeDevToolsAuditsPanelThrottling] for more information on the throttling UI changes.</span></span>  

:::image type="complex" source="../../images/2019/12/start.msft.png" alt-text="DevTools 中的性能工具改进了键盘导航和屏幕阅读器" lightbox="../../images/2019/12/start.msft.png":::
   <span data-ttu-id="41e93-247">新的配置 UI</span><span class="sxs-lookup"><span data-stu-id="41e93-247">The new configuration UI</span></span>  
:::image-end:::  

### <span data-ttu-id="41e93-248">覆盖范围选项卡更新</span><span class="sxs-lookup"><span data-stu-id="41e93-248">Coverage tab updates</span></span>  

#### <span data-ttu-id="41e93-249">每个函数或每块覆盖率模式</span><span class="sxs-lookup"><span data-stu-id="41e93-249">Per-function or per-block coverage modes</span></span>  

<span data-ttu-id="41e93-250">" [覆盖范围" 选项卡][DevToolsCoverageIndex] 具有新的下拉菜单，可让你指定是否应 **按每个函数** 或 **每个块**收集代码覆盖率数据。</span><span class="sxs-lookup"><span data-stu-id="41e93-250">The [Coverage tab][DevToolsCoverageIndex] has a new dropdown menu that lets you specify whether code coverage data should be collected **per function** or **per block**.</span></span>  <span data-ttu-id="41e93-251">**每个块** 覆盖率更详细，但更昂贵的收集方式。</span><span class="sxs-lookup"><span data-stu-id="41e93-251">**Per block** coverage is more detailed but also far more expensive to collect.</span></span>  <span data-ttu-id="41e93-252">默认情况下，DevTools 使用 **每个函数** 覆盖率。</span><span class="sxs-lookup"><span data-stu-id="41e93-252">DevTools uses **per function** coverage by default now.</span></span>  

> [!CAUTION]
> <span data-ttu-id="41e93-253">你可能会看到 HTML 文件中的较大代码覆盖率有差异，具体取决于 **每个函数** 还是 **每块** 模式使用。</span><span class="sxs-lookup"><span data-stu-id="41e93-253">You may see large code coverage differences in HTML files depending on whether you use **per function** or **per block** mode.</span></span>  <span data-ttu-id="41e93-254">使用 **每个函数** 模式时，HTML 文件中的内联脚本将被视为函数。</span><span class="sxs-lookup"><span data-stu-id="41e93-254">When using **per function** mode, inline scripts in HTML files are treated as functions.</span></span>  <span data-ttu-id="41e93-255">如果脚本全部运行，则 DevTools 将整个脚本标记为使用的代码。</span><span class="sxs-lookup"><span data-stu-id="41e93-255">If the script runs at all then DevTools marks the entire script as used code.</span></span>  <span data-ttu-id="41e93-256">仅当脚本根本不运行时，DevTools 将脚本标记为未使用的代码。</span><span class="sxs-lookup"><span data-stu-id="41e93-256">Only if the script does not run at all does DevTools mark the script as unused code.</span></span>  

:::image type="complex" source="../../images/2019/12/modes.msft.png" alt-text="DevTools 中的性能工具改进了键盘导航和屏幕阅读器" lightbox="../../images/2019/12/modes.msft.png":::
   <span data-ttu-id="41e93-258">"覆盖模式" 下拉菜单</span><span class="sxs-lookup"><span data-stu-id="41e93-258">The coverage mode dropdown menu</span></span>  
:::image-end:::  

#### <span data-ttu-id="41e93-259">覆盖范围现在必须由页面重装启动</span><span class="sxs-lookup"><span data-stu-id="41e93-259">Coverage must now be initiated by a page reload</span></span>  

<span data-ttu-id="41e93-260">由于覆盖率数据不可靠，因此在没有页面重新加载的情况下切换代码覆盖率已被删除。</span><span class="sxs-lookup"><span data-stu-id="41e93-260">Toggling code coverage without a page reload has been removed because the coverage data was unreliable.</span></span>  <span data-ttu-id="41e93-261">例如，如果运行时以前很长一段时间，并且 V8 垃圾回收器已清理过它，则可能会将函数报告为未使用。</span><span class="sxs-lookup"><span data-stu-id="41e93-261">For example, a function may be reported as unused if the runtime was a long time ago and the V8 garbage collector has cleaned it up.</span></span>  

<span data-ttu-id="41e93-262">Chromium 问题 [#1004203][CR1004203]</span><span class="sxs-lookup"><span data-stu-id="41e93-262">Chromium issue [#1004203][CR1004203]</span></span>  

## <span data-ttu-id="41e93-263">下载 Microsoft Edge 预览频道</span><span class="sxs-lookup"><span data-stu-id="41e93-263">Download the Microsoft Edge preview channels</span></span>  

<span data-ttu-id="41e93-264">如果你使用的是 Windows 或 macOS，请考虑使用 [ Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels] 作为默认开发浏览器。</span><span class="sxs-lookup"><span data-stu-id="41e93-264">If you are on Windows or macOS, consider using the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] as your default development browser.</span></span>  <span data-ttu-id="41e93-265">预览频道使你能够访问最新的 DevTools 功能。</span><span class="sxs-lookup"><span data-stu-id="41e93-265">The preview channels give you access to the latest DevTools features.</span></span>  

## <span data-ttu-id="41e93-266">与 Microsoft Edge DevTools 团队取得联系</span><span class="sxs-lookup"><span data-stu-id="41e93-266">Getting in touch with Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!--<<../../_shared/devtools-feedback.md>> -->

<!--<<../../_shared/canary.md>> -->

<!--<<../../_shared/discover.md>> -->

<!-- image links -->  

<!--[../../images/2019/12/wasm.msft.png]: ../../images/2019/12/wasm.msft.png "Figure: The new DWARF-powered WebAssembly debugging"  -->

<!-- links -->  

[DevToolsCommandMenuIndex]: /microsoft-edge/devtools-guide-chromium/command-menu/index "通过 Microsoft Edge DevTools 命令菜单运行命令 |Microsoft 文档"  
[DevToolsCoverageIndex]: /microsoft-edge/devtools-guide-chromium/coverage/index "使用 Microsoft Edge DevTools | 中的 "覆盖范围" 选项卡查找未使用的 JavaScript 和 CSS 代码。Microsoft 文档"  
[DevToolsDeviceModeIndex]: /microsoft-edge/devtools-guide-chromium/device-mode/index#simulate-a-mobile-viewport "模拟移动区-在 Microsoft Edge DevTools 中使用设备模式模拟移动设备 |Microsoft 文档"  
[DevToolsNetworkIndex]: /microsoft-edge/devtools-guide-chromium/network/index "检查 Microsoft Edge DevTools 中的网络活动 |Microsoft 文档"  
[DevToolsNetworkReferenceViewInitiatorsDependencies]: /microsoft-edge/devtools-guide-chromium/network/reference#view-initiators-and-dependencies "查看启动器和相关性-网络分析参考 |Microsoft 文档"  
[DevGuideEdgeHtmlWhatsNew]: /microsoft-edge/dev-guide/whats-new "EdgeHTML | 中的新增功能 |Microsoft 文档"  
[VisualStudioCodeDebuggerEdgeExtension]: /microsoft-edge/visual-studio-code/debugger-for-edge "Microsoft Edge Visual Studio 代码扩展的调试器 |Microsoft 文档"  
[VisualStudioCodeElementEdgeExtension]: /microsoft-edge/visual-studio-code/elements-for-edge "Microsoft Edge Visual Studio 代码扩展的元素 |Microsoft 文档"  

<!--  [201912Webassembly]: webassembly.md "Improved WebAssembly debugging in Microsoft Edge DevTools"  -->  

[CR842488]: https://crbug.com/842488 "将启动器字段添加到 "页眉" 选项卡 |Chromium Bug"  
[CR988253]: https://crbug.com/988253 "Bug DevTools-网络请求与时间线图之间没有关联 |Chromium Bug"  
[CR993366]: https://crbug.com/993366 "请在网络面板请求列表 | 中显示 URL 的路径部分Chromium Bug"  
[CR1004193]: https://crbug.com/1004193 "V8 | 的复制模式Chromium Bug"  
[CR1004203]: https://crbug.com/1004203 "使代码覆盖率非常有意义 |Chromium Bug"  
[CR1029031]: https://crbug.com/1029031 "UA 字符串即将过时 |Chromium Bug" 
[CR963183]: https://crbug.com/963183 "DevTools 不符合 WCAG 标准 |Chromium Bug"
[CR941561]: https://crbug.com/941561 "DevTools | 的本地化Chromium Bug"
[CR987787]: https://crbug.com/987787 "Dom 3D 视图 |Chromium Bug"

[AccessibilityInsights]: https://aka.ms/a11yinsights "辅助功能见解"  

[DwarfHome]: https://dwarfstd.org "Dwarf 主页"  
[GitHubGoogleChromeDevToolsAuditsPanelThrottling]: https://github.com/GoogleChrome/lighthouse/blob/master/docs/throttling.md#devtools-audits-panel-throttling "DevTools ' 审核面板限制-GoogleChrome/lighthouse |GitHub"  
[GitHubMicrosoftDocsEdgeDeveloperNewIssue]: https://aka.ms/edgedevtoolsdocs/feedback "新问题 - MicrosoftDocs/edge-developer"  
[MicrosoftEdgePreviewChannels]: https://aka.ms/microsoftedge "Microsoft Edge 预览频道"  
[MicrosoftEdgeInsiderAddons]: https://aka.ms/webhint/edge-extension "Microsoft Edge 预览体验计划 Addons"  
[MicrosoftVisualStudio]: https://aka.ms/vs "Visual Studio"  
[MicrosoftVisualStudioBlogDebugJavascript]: https://aka.ms/vs/debug-edge "从 Visual Studio 中的 Microsoft Edge 调试 JavaScript |Visual Studio 博客"  
[MicrosoftVisualStudioDownloads]: https://aka.ms/vs/download "下载适用于 Windows 的 Visual Studio 2019 & Mac"  
[MDNDocumentObjectModel]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model "文档对象模型 (DOM) |MDN"  
[MDNZIndex]: https://developer.mozilla.org/docs/Web/CSS/z-index "z-索引 |MDN"  
[PostTweetEdgeDevTools]: https://aka.ms/tweet/edgedevtools "@EdgeDevTools | 发布推文"  
[EdgeDevToolsTwitterAccount]: https://aka.ms/twitter/edgedevtools "@EdgeDevTools Twitter 帐户"
[VisualStudioCode]: https://aka.ms/vscode "Visual Studio 代码"  
[VisualStudioMarketplaceDebuggerEdge]: https://aka.ms/debugger4code "Microsoft Edge 的调试器-Visual Studio Marketplace"  
[VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension]: https://aka.ms/elements4code "Microsoft Edge \ (的元素 \ ) Chromium \-Visual Studio Marketplace"  
[VisualStudioMarketplaceWebhintExtension]: https://aka.ms/webhint4code "webhint-Visual Studio Marketplace"
[Webhint]: https://aka.ms/webhint "webhint"  
[WebhintBrowserExtension]: https://aka.ms/webhint/browser-extension "Webhint 浏览器扩展 |webhint 文档"  
[WebhintVisualStudioCodeExtension]: https://aka.ms/webhint/code-extension "Webhint Visual Studio 代码扩展 |webhint 文档"  
[TrackingPrevention]: https://aka.ms/microsoftedge/tracking-prevention-blog "改进 Microsoft Edge 博客文章中的跟踪保护"
[TheWebWeWant]: https://aka.ms/webwewant "我们想要的网络"

> [!NOTE]
> <span data-ttu-id="41e93-306">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="41e93-306">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="41e93-307">原始页面位于[此处](https://developers.google.com/web/updates/2019/12/devtools/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="41e93-307">The original page is found [here](https://developers.google.com/web/updates/2019/12/devtools/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="41e93-309">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="41e93-309">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
