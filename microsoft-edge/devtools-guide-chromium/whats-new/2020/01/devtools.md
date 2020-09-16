---
description: 3D 视图、Visual Studio 与 Microsoft Edge 的集成等。
title: DevTools (Microsoft Edge 81) 中的新增功能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 3081ebb256a9ede637aaaddc3c3cdf7a70a201bb
ms.sourcegitcommit: b337717957529239434b4e8e1e167aebf0543518
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2020
ms.locfileid: "11015473"
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

# <span data-ttu-id="b1780-104">DevTools （Microsoft Edge 81）中的新增功能</span><span class="sxs-lookup"><span data-stu-id="b1780-104">What's New In DevTools (Microsoft Edge 81)</span></span>  

## <span data-ttu-id="b1780-105">来自 Microsoft Edge 开发人员工具团队公告</span><span class="sxs-lookup"><span data-stu-id="b1780-105">Announcements from the Microsoft Edge DevTools team</span></span>  

<span data-ttu-id="b1780-106">以下各部分是你可能错过的 Microsoft Edge 开发人员工具团队的公告列表！</span><span class="sxs-lookup"><span data-stu-id="b1780-106">The following sections are a list of announcements you may have missed from the Microsoft Edge DevTools team!</span></span> <span data-ttu-id="b1780-107">查看它们以尝试 DevTools、Visual Studio 代码扩展等中的新功能。</span><span class="sxs-lookup"><span data-stu-id="b1780-107">Check them out to try new features in the DevTools, Visual Studio Code extensions, and more.</span></span>  <span data-ttu-id="b1780-108">若要了解有关开发人员工具中的所有最新功能和最强大功能的最新动态，请下载 [Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels]并[在 Twitter 上关注我们][EdgeDevToolsTwitterAccount]。</span><span class="sxs-lookup"><span data-stu-id="b1780-108">To stay up to date on all the latest and greatest features in your developer tools, download the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] and [follow us on Twitter][EdgeDevToolsTwitterAccount].</span></span>  

### <span data-ttu-id="b1780-109">对 DevTools 的辅助功能改进</span><span class="sxs-lookup"><span data-stu-id="b1780-109">Accessibility improvements to the DevTools</span></span>  

<span data-ttu-id="b1780-110">DevTools 团队已向 Chromium 提供170更改，以解决 DevTools 中的高影响力颜色对比度、键盘和屏幕阅读器问题。</span><span class="sxs-lookup"><span data-stu-id="b1780-110">The DevTools team has contributed 170 changes to Chromium to address high-impact color contrast, keyboard, and screen reader issues in the DevTools.</span></span>  <span data-ttu-id="b1780-111">每个构建 web 的开发人员都应该能够使用 DevTools。</span><span class="sxs-lookup"><span data-stu-id="b1780-111">Every developer building the web should be able to use the DevTools.</span></span>  

:::image type="complex" source="../../images/2020/01/a11y-performance-tool.msft.gif" alt-text="DevTools 中的性能工具改进了键盘导航和屏幕阅读器" lightbox="../../images/2020/01/a11y-performance-tool.msft.gif":::
   <span data-ttu-id="b1780-113">DevTools 中的 **性能** 工具改进了键盘导航和屏幕阅读器</span><span class="sxs-lookup"><span data-stu-id="b1780-113">The **Performance** tool in the DevTools with the keyboard navigation and screen reader improvements</span></span>  
:::image-end:::  

<span data-ttu-id="b1780-114">希望了解如何让您的网页对所有用户都易于访问？</span><span class="sxs-lookup"><span data-stu-id="b1780-114">Want to learn how to make your web page accessible to all of your users?</span></span>  <span data-ttu-id="b1780-115">下载 Microsoft Edge 的 [辅助功能见解][AccessibilityInsights] 和 [webhint][WebhintBrowserExtension] 扩展以开始使用。</span><span class="sxs-lookup"><span data-stu-id="b1780-115">Download the [Accessibility Insights][AccessibilityInsights] and [webhint][WebhintBrowserExtension] extensions for Microsoft Edge to get started.</span></span>  

<span data-ttu-id="b1780-116">如果您使用屏幕阅读器或键盘在 DevTools 中导航，请通过 [发推至][PostTweetEdgeDevTools] 与我们联系或单击 " [发送反馈](#getting-in-touch-with-microsoft-edge-devtools-team) " 图标向我们发送您的反馈！</span><span class="sxs-lookup"><span data-stu-id="b1780-116">If you use screen readers or the keyboard to navigate around the DevTools, send us your feedback by [tweeting][PostTweetEdgeDevTools] at us or clicking the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!</span></span>  

<span data-ttu-id="b1780-117">Chromium 问题 [#963183][CR963183]</span><span class="sxs-lookup"><span data-stu-id="b1780-117">Chromium issue [#963183][CR963183]</span></span>  

### <span data-ttu-id="b1780-118">使用其他语言的 DevTools</span><span class="sxs-lookup"><span data-stu-id="b1780-118">Using the DevTools in other languages</span></span>  

<span data-ttu-id="b1780-119">许多开发人员使用其他开发人员工具，如 StackOverflow 和 Visual Studio 代码，采用其母语，而不仅仅是英语。</span><span class="sxs-lookup"><span data-stu-id="b1780-119">Many developers use other developer tools, like StackOverflow and Visual Studio Code, in their native language, not just in English.</span></span>  <span data-ttu-id="b1780-120">我们很高兴宣布 DevTools 的本地化，您现在可以使用英语之外的10种语言中的一种：</span><span class="sxs-lookup"><span data-stu-id="b1780-120">We’re excited to announce localization for the DevTools, which you are now able to use in one of 10 languages besides English:</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="b1780-121"> (简体中文 \ ) - &#20013;&#25991;&#65288;&#31616;&#20307;&#65289;</span><span class="sxs-lookup"><span data-stu-id="b1780-121">Chinese \(Simplified\) - &#20013;&#25991;&#65288;&#31616;&#20307;&#65289;</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="b1780-122">中文 (传统版 \ ) - &#20013;&#25991;&#65288;&#32321;&#39636;&#65289;</span><span class="sxs-lookup"><span data-stu-id="b1780-122">Chinese \(Traditional\) - &#20013;&#25991;&#65288;&#32321;&#39636;&#65289;</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      <span data-ttu-id="b1780-123">法语-fran&#231;ais</span><span class="sxs-lookup"><span data-stu-id="b1780-123">French – fran&#231;ais</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="b1780-124">德语-德语</span><span class="sxs-lookup"><span data-stu-id="b1780-124">German - deutsch</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      <span data-ttu-id="b1780-125">意大利语-意大利语</span><span class="sxs-lookup"><span data-stu-id="b1780-125">Italian - italiano</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="b1780-126">日语- &#26085;&#26412;&#35486;</span><span class="sxs-lookup"><span data-stu-id="b1780-126">Japanese - &#26085;&#26412;&#35486;</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      <span data-ttu-id="b1780-127">朝鲜语- &#54620;&#44397;&#50612;</span><span class="sxs-lookup"><span data-stu-id="b1780-127">Korean - &#54620;&#44397;&#50612;</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="b1780-128">葡萄牙语-portugu&#234;s</span><span class="sxs-lookup"><span data-stu-id="b1780-128">Portuguese - portugu&#234;s</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      <span data-ttu-id="b1780-129">俄语–  &#1088;&#1091;&#1089;&#1089;&#1082;&#1080;&#1081;</span><span class="sxs-lookup"><span data-stu-id="b1780-129">Russian – &#1088;&#1091;&#1089;&#1089;&#1082;&#1080;&#1081;</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="b1780-130">西班牙语-espa&#241;ol</span><span class="sxs-lookup"><span data-stu-id="b1780-130">Spanish - espa&#241;ol</span></span>
   :::column-end:::
:::row-end:::

<!--  
|  |  |  
|:--- |:--- |  
| Chinese (Simplified) - 中文(简体)（简体）| Chinese (Traditional) - 中文(繁體)（繁體）|  
| French – français | German - deutsch |  
| Italian - italiano | Portuguese - português |  
| Korean - 한국어 | Japanese - 日本語 |  
| Russian – русский | Spanish - español |  
-->  

<span data-ttu-id="b1780-131">DevTools 将自动匹配您在的 Microsoft Edge 中使用的语言 `edge://settings/languages` 。</span><span class="sxs-lookup"><span data-stu-id="b1780-131">The DevTools automatically match the language you use for Microsoft Edge in `edge://settings/languages`.</span></span>  

<span data-ttu-id="b1780-132">如果你希望 Microsoft Edge 采用一种语言，并且你的 DevTools 保留为英语，请按 `F1` DevTools 打开 " [设置][Settings] "，然后禁用 " **匹配浏览器语言**"。</span><span class="sxs-lookup"><span data-stu-id="b1780-132">If you want Microsoft Edge to be in one language and your DevTools to remain in English, press `F1` in the DevTools to open [Settings][Settings] and disable **Match browser language**.</span></span>  

:::image type="complex" source="../../images/2020/01/localized-devtools.msft.png" alt-text="德语中的 DevTools" lightbox="../../images/2020/01/localized-devtools.msft.png":::
   <span data-ttu-id="b1780-134">德语中的 DevTools</span><span class="sxs-lookup"><span data-stu-id="b1780-134">The DevTools in German</span></span>  
:::image-end:::  

<span data-ttu-id="b1780-135">不本地化**控制台**消息。</span><span class="sxs-lookup"><span data-stu-id="b1780-135">**Console** messages are not localized.</span></span>  <span data-ttu-id="b1780-136">仅在 DevTools UI 中使用的字符串以用于 Microsoft Edge 的语言显示。</span><span class="sxs-lookup"><span data-stu-id="b1780-136">Only the strings used in the DevTools UI are displayed in the language you use for Microsoft Edge.</span></span>  

<span data-ttu-id="b1780-137">如果您想要使用的 DevTools 语言与可用的语言不同，请 [tweet][PostTweetEdgeDevTools] ，或单击 " [发送反馈](#getting-in-touch-with-microsoft-edge-devtools-team) " 图标。</span><span class="sxs-lookup"><span data-stu-id="b1780-137">If you want to use the DevTools in a different language than the ones that are available, [tweet][PostTweetEdgeDevTools] at us or click the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon.</span></span>  

<span data-ttu-id="b1780-138">Chromium 问题 [#941561][CR941561]</span><span class="sxs-lookup"><span data-stu-id="b1780-138">Chromium issue [#941561][CR941561]</span></span>  

### <span data-ttu-id="b1780-139">webhint Microsoft Edge 扩展</span><span class="sxs-lookup"><span data-stu-id="b1780-139">webhint Microsoft Edge extension</span></span>  

<span data-ttu-id="b1780-140">Webhint Microsoft Edge 扩展使你能够轻松地浏览网页并在 DevTools 中获取有关辅助功能、浏览器兼容性、安全性、性能等的反馈。</span><span class="sxs-lookup"><span data-stu-id="b1780-140">The webhint Microsoft Edge extension allows you to easily scan your web page and get feedback on accessibility, browser compatibility, security, performance, and more within the DevTools.</span></span>  <span data-ttu-id="b1780-141">阅读详细信息 [https://webhint.io][Webhint] 。</span><span class="sxs-lookup"><span data-stu-id="b1780-141">Read more at [https://webhint.io][Webhint].</span></span>  

:::image type="complex" source="../../images/2020/01/webhint-browser-extension.msft.png" alt-text="安装 webhint 浏览器扩展时，DevTools 中的 "提示" 选项卡" lightbox="../../images/2020/01/webhint-browser-extension.msft.png":::
   <span data-ttu-id="b1780-143">安装 webhint 浏览器扩展时，DevTools 中的 " **提示** " 选项卡</span><span class="sxs-lookup"><span data-stu-id="b1780-143">The **Hints** tab in the DevTools when the webhint browser extension is installed</span></span>  
:::image-end:::  

<span data-ttu-id="b1780-144">[在 Microsoft Edge 中尝试 webhint 浏览器扩展][MicrosoftEdgeInsiderAddons]。</span><span class="sxs-lookup"><span data-stu-id="b1780-144">[Try the webhint browser extension in Microsoft Edge][MicrosoftEdgeInsiderAddons].</span></span>  <span data-ttu-id="b1780-145">安装扩展后，打开 DevTools 并选择 "提示" 选项卡。 在此处，运行可自定义的网站扫描。</span><span class="sxs-lookup"><span data-stu-id="b1780-145">Once you install the extension, open the DevTools and select the Hints tab.  From here, run a customizable site scan.</span></span>  <span data-ttu-id="b1780-146">请转到 [webhint.io][WebhintBrowserExtension] 以了解更多信息。</span><span class="sxs-lookup"><span data-stu-id="b1780-146">Head over to [webhint.io][WebhintBrowserExtension] to learn more.</span></span>  

### <span data-ttu-id="b1780-147">3D 视图</span><span class="sxs-lookup"><span data-stu-id="b1780-147">3D View</span></span>  

<span data-ttu-id="b1780-148">通过浏览[文档对象模型 (DOM \ ) ][MDNDocumentObjectModel]或[z 索引][MDNZIndex]堆栈上下文，使用**3d 视图**调试 web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="b1780-148">Use the **3D View** to debug your web application by navigating through the [Document Object Model \(DOM\)][MDNDocumentObjectModel] or the [z-index][MDNZIndex] stacking context.</span></span>  

:::image type="complex" source="../../images/2020/01/3dview.msft.png" alt-text="DevTools 中的3D 视图" lightbox="../../images/2020/01/3dview.msft.png":::
   <span data-ttu-id="b1780-150">DevTools 中的3D 视图</span><span class="sxs-lookup"><span data-stu-id="b1780-150">The 3D View in the DevTools</span></span>  
:::image-end:::  

<span data-ttu-id="b1780-151">若要访问3d 视图，请按 `Ctrl`  +  `Shift`  +  `P` ，在**3d 视图**中键入，然后选择 "**显示3d 视图**"。</span><span class="sxs-lookup"><span data-stu-id="b1780-151">To access the 3D View, press `Ctrl` + `Shift` + `P`, type in **3D View** and select **Show 3D View**.</span></span>  

<span data-ttu-id="b1780-152">我们正在处理 UI 并向3D 视图添加更多功能，因此请向我们发送 [反馈](#getting-in-touch-with-microsoft-edge-devtools-team)。</span><span class="sxs-lookup"><span data-stu-id="b1780-152">We're working on the UI and adding more functionality to the 3D View, so please send us your [feedback](#getting-in-touch-with-microsoft-edge-devtools-team).</span></span>  

<span data-ttu-id="b1780-153">Chromium 问题 [#987787][CR987787]</span><span class="sxs-lookup"><span data-stu-id="b1780-153">Chromium issue [#987787][CR987787]</span></span>  

### <span data-ttu-id="b1780-154">Visual Studio 代码扩展</span><span class="sxs-lookup"><span data-stu-id="b1780-154">Visual Studio Code extensions</span></span>  

<span data-ttu-id="b1780-155">DevTools 团队还发布了一些适用于 [Visual Studio 代码][VisualStudioCode] 的扩展，可让你直接从文本编辑器中使用 DevTools 的强大功能！</span><span class="sxs-lookup"><span data-stu-id="b1780-155">The DevTools team has also released some extensions for [Visual Studio Code][VisualStudioCode] that let you use the power of the DevTools directly from your text editor!</span></span> <span data-ttu-id="b1780-156">请查看下面的分机：</span><span class="sxs-lookup"><span data-stu-id="b1780-156">Check out the extensions below:</span></span>  

#### <span data-ttu-id="b1780-157">Microsoft Edge 元素</span><span class="sxs-lookup"><span data-stu-id="b1780-157">Elements for Microsoft Edge</span></span>  

<span data-ttu-id="b1780-158">通过添加 [Microsoft Edge \ (Chromium \ ) ][VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension] Visual studio 代码扩展中的元素，从 Visual studio 代码中使用元素工具。</span><span class="sxs-lookup"><span data-stu-id="b1780-158">Use the Elements tool from within Visual Studio Code by adding the [Elements for Microsoft Edge \(Chromium\)][VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension] Visual Studio Code extension.</span></span>  

:::image type="complex" source="../../images/2020/01/elements-for-edge.msft.png" alt-text="Visual Studio 代码中使用 Microsoft Edge 扩展的元素的元素工具" lightbox="../../images/2020/01/elements-for-edge.msft.png":::
   <span data-ttu-id="b1780-160">Visual Studio 代码中使用 Microsoft Edge 扩展的元素的 **元素** 工具</span><span class="sxs-lookup"><span data-stu-id="b1780-160">The **Elements** tool in Visual Studio Code using the Elements for Microsoft Edge extension</span></span>  
:::image-end:::  

<span data-ttu-id="b1780-161">有关详细信息，请查看 [Microsoft Edge Visual Studio 代码扩展的元素][VisualStudioCodeElementEdgeExtension]。</span><span class="sxs-lookup"><span data-stu-id="b1780-161">For more information, check out [Elements for Microsoft Edge Visual Studio Code extension][VisualStudioCodeElementEdgeExtension].</span></span>  

#### <span data-ttu-id="b1780-162">Microsoft Edge 调试器</span><span class="sxs-lookup"><span data-stu-id="b1780-162">Debugger for Microsoft Edge</span></span>  

<span data-ttu-id="b1780-163">通过 [适用于 Microsoft edge][VisualStudioMarketplaceDebuggerEdge] Visual Studio 代码扩展的调试器，直接从 Visual Studio 代码调试在 Microsoft edge 中运行的 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="b1780-163">With the [Debugger for Microsoft Edge][VisualStudioMarketplaceDebuggerEdge] Visual Studio Code extension, debug JavaScript running in Microsoft Edge directly from Visual Studio Code.</span></span>  

:::image type="complex" source="../../images/2020/01/vscode-debugger.msft.png" alt-text="Visual Studio 代码中 Microsoft Edge 扩展的调试器" lightbox="../../images/2020/01/vscode-debugger.msft.png":::
   <span data-ttu-id="b1780-165">Visual Studio 代码中 Microsoft Edge 扩展的调试器</span><span class="sxs-lookup"><span data-stu-id="b1780-165">The Debugger for Microsoft Edge Extension in Visual Studio Code</span></span>  
:::image-end:::  

<span data-ttu-id="b1780-166">有关详细信息，请参阅 [如何从 Visual Studio 代码调试 Microsoft Edge][VisualStudioCodeDebuggerEdgeExtension]。</span><span class="sxs-lookup"><span data-stu-id="b1780-166">For more information, check out [how to debug Microsoft Edge from Visual Studio Code][VisualStudioCodeDebuggerEdgeExtension].</span></span>  

#### <span data-ttu-id="b1780-167">webhint</span><span class="sxs-lookup"><span data-stu-id="b1780-167">webhint</span></span>  

<span data-ttu-id="b1780-168">当你编写网页时， [webhint][VisualStudioMarketplaceWebhintExtension] Visual Studio 代码扩展使用 `webhint` 它来改进网页！</span><span class="sxs-lookup"><span data-stu-id="b1780-168">The [webhint][VisualStudioMarketplaceWebhintExtension] Visual Studio Code extension uses `webhint` to improve your web page while you're writing it!</span></span> <span data-ttu-id="b1780-169">此扩展基于分析对工作区文件运行和报告诊断 `webhint` 。</span><span class="sxs-lookup"><span data-stu-id="b1780-169">This extension runs and reports diagnostics on your workspace files based on `webhint` analysis.</span></span>  

:::image type="complex" source="../../images/2020/01/webhint-vscode-extension.msft.png" alt-text="在 Visual Studio 代码中分析 tsx 文件的 webhint Visual Studio 代码扩展" lightbox="../../images/2020/01/webhint-vscode-extension.msft.png":::
   <span data-ttu-id="b1780-171">`.tsx`在 Visual Studio 代码中分析文件的 Webhint Visual Studio 代码扩展</span><span class="sxs-lookup"><span data-stu-id="b1780-171">The webhint Visual Studio Code extension analyzing a `.tsx` file in Visual Studio Code</span></span>  
:::image-end:::  

<span data-ttu-id="b1780-172">[了解有关 Visual Studio 代码 webhint 扩展的详细信息][WebhintVisualStudioCodeExtension]。</span><span class="sxs-lookup"><span data-stu-id="b1780-172">[Learn more about the Visual Studio Code webhint extension][WebhintVisualStudioCodeExtension].</span></span>  

### <span data-ttu-id="b1780-173">Visual Studio 集成</span><span class="sxs-lookup"><span data-stu-id="b1780-173">Visual Studio integration</span></span>  

<span data-ttu-id="b1780-174">在 Visual Studio 2019 版本16.2 或更高版本中，使用 Visual Studio 调试器调试在 Microsoft Edge 中运行的 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="b1780-174">In Visual Studio 2019 version 16.2 or later, use the Visual Studio debugger to debug JavaScript running in Microsoft Edge.</span></span>  <span data-ttu-id="b1780-175">[下载 Visual Studio 2019][MicrosoftVisualStudioDownloads] 以试用此功能！</span><span class="sxs-lookup"><span data-stu-id="b1780-175">[Download Visual Studio 2019][MicrosoftVisualStudioDownloads] to try this feature out!</span></span>  

:::image type="complex" source="../../images/2020/01/vs.msft.png" alt-text="带有在 Microsoft Edge 的 "应用"、"开发" 或 "Beta" 中启动 web 应用选项的 Visual Studio" lightbox="../../images/2020/01/vs.msft.png":::
   <span data-ttu-id="b1780-177">带有在 Microsoft Edge 的 "应用"、"开发" 或 "Beta" 中启动 web 应用选项的 Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b1780-177">Visual Studio with the option to launch your web app in Microsoft Edge Canary, Dev, or Beta</span></span>  
:::image-end:::  

<span data-ttu-id="b1780-178">[了解有关从 Visual Studio 调试 Microsoft Edge 的详细信息][MicrosoftVisualStudio]。</span><span class="sxs-lookup"><span data-stu-id="b1780-178">[Learn more about debugging Microsoft Edge from Visual Studio][MicrosoftVisualStudio].</span></span>  

### <span data-ttu-id="b1780-179">跟踪保护控制台消息</span><span class="sxs-lookup"><span data-stu-id="b1780-179">Tracking prevention Console messages</span></span>  

<span data-ttu-id="b1780-180">"跟踪防护" 是 Microsoft Edge 中的一项独特功能，可防止您以前未访问过的网站对您进行跟踪。</span><span class="sxs-lookup"><span data-stu-id="b1780-180">Tracking prevention is a unique feature in Microsoft Edge that protects you from being tracked by websites you haven't visited before.</span></span>  <span data-ttu-id="b1780-181">默认跟踪防护设置为平衡模式，这将阻止第三方跟踪程序和已知恶意跟踪程序，以获取平衡隐私和 web 兼容性的体验。</span><span class="sxs-lookup"><span data-stu-id="b1780-181">The default tracking prevention setting is Balanced mode, which blocks 3rd party trackers and known malicious trackers for an experience that balances privacy and web compatibility.</span></span>  <span data-ttu-id="b1780-182">若要在某些跟踪器被阻止时更深入地了解网页的兼容性，我们还在跟踪器被阻止时在控制台中添加了警告消息。</span><span class="sxs-lookup"><span data-stu-id="b1780-182">To give you more insight into the compatibility of your web page when certain trackers are blocked, we've also added warning messages in the Console when a tracker is blocked.</span></span>  

:::image type="complex" source="../../images/2020/01/tracking-prevention.msft.png" alt-text="跟踪阻止阻止跟踪对存储的访问权限时的控制台中的消息" lightbox="../../images/2020/01/tracking-prevention.msft.png":::
   <span data-ttu-id="b1780-184">跟踪阻止阻止跟踪对存储的访问权限时的控制台中的消息</span><span class="sxs-lookup"><span data-stu-id="b1780-184">Messages in the Console when tracking prevention blocks access to storage for a tracker</span></span>  
:::image-end:::  

<span data-ttu-id="b1780-185">[阅读有关跟踪防护和隐私和 web 兼容性之间的平衡的详细信息][TrackingPrevention]。</span><span class="sxs-lookup"><span data-stu-id="b1780-185">[Read more about tracking prevention and the balance between privacy and web compatibility][TrackingPrevention].</span></span>  

## <span data-ttu-id="b1780-186">来自 Chromium 项目的公告</span><span class="sxs-lookup"><span data-stu-id="b1780-186">Announcements from the Chromium project</span></span>  

<span data-ttu-id="b1780-187">以下各节宣布了在 Microsoft Edge 81 中提供的其他功能，这些功能由开放的源 Chromium 项目所参与。</span><span class="sxs-lookup"><span data-stu-id="b1780-187">The following sections announce additional features available in Microsoft Edge 81 that were contributed to the open source Chromium project.</span></span>  

### <span data-ttu-id="b1780-188">设备模式下的 Moto G4 支持</span><span class="sxs-lookup"><span data-stu-id="b1780-188">Moto G4 support in Device Mode</span></span>  

<span data-ttu-id="b1780-189">[启用设备工具栏][DeviceToolbar]后，从**设备**列表中模拟 Moto G4 视区的尺寸。</span><span class="sxs-lookup"><span data-stu-id="b1780-189">After [enabling the Device Toolbar][DeviceToolbar], simulate the dimensions of a Moto G4 viewport from the **Device** list.</span></span>  

:::image type="complex" source="../../images/2020/01/motog4.msft.png" alt-text="模拟 Moto G4 视区" lightbox="../../images/2020/01/motog4.msft.png":::
   <span data-ttu-id="b1780-191">模拟 Moto G4 视区</span><span class="sxs-lookup"><span data-stu-id="b1780-191">Simulating a Moto G4 viewport</span></span>  
:::image-end:::  

<span data-ttu-id="b1780-192">单击 " [显示设备帧][DeviceFrame] " 以显示视区周围的 Moto G4 硬件。</span><span class="sxs-lookup"><span data-stu-id="b1780-192">Click [Show Device Frame][DeviceFrame] to show the Moto G4 hardware around the viewport.</span></span>  

:::image type="complex" source="../../images/2020/01/motog4frame.msft.png" alt-text="显示 Moto G4 硬件" lightbox="../../images/2020/01/motog4frame.msft.png":::
   <span data-ttu-id="b1780-194">显示 Moto G4 硬件</span><span class="sxs-lookup"><span data-stu-id="b1780-194">Showing the Moto G4 hardware</span></span>  
:::image-end:::  

<span data-ttu-id="b1780-195">相关功能：</span><span class="sxs-lookup"><span data-stu-id="b1780-195">Related features:</span></span>  

*   <span data-ttu-id="b1780-196">[Command Menu][CommandMenu] `Capture screenshot` 在启用 "**显示设备框架**") 之后，打开命令菜单并运行命令以获取包含 Moto G4 (硬件的视区的屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="b1780-196">Open the [Command Menu][CommandMenu] and run the `Capture screenshot` command to take a screenshot of the viewport that includes the Moto G4 hardware (after enabling **Show Device Frame**).</span></span>  
*   <span data-ttu-id="b1780-197">[调节网络和 CPU][ThrottleNetworkAndCpu] 以更准确地模拟移动用户的 web 浏览条件。</span><span class="sxs-lookup"><span data-stu-id="b1780-197">[Throttle the network and CPU][ThrottleNetworkAndCpu] to more accurately simulate a mobile user's web browsing conditions.</span></span>  

<span data-ttu-id="b1780-198">Chromium 问题 [#924693][CR924693]</span><span class="sxs-lookup"><span data-stu-id="b1780-198">Chromium issue [#924693][CR924693]</span></span>  

### <span data-ttu-id="b1780-199">与 Cookie 相关的更新</span><span class="sxs-lookup"><span data-stu-id="b1780-199">Cookie-related updates</span></span>  

#### <span data-ttu-id="b1780-200">Cookie 窗格中阻止的 cookie</span><span class="sxs-lookup"><span data-stu-id="b1780-200">Blocked cookies in the Cookies pane</span></span>  

<span data-ttu-id="b1780-201">"应用程序" 面板中的 "Cookie" 窗格现在显示黄色背景的被阻止的 cookie。</span><span class="sxs-lookup"><span data-stu-id="b1780-201">The Cookies pane in the Application panel now displays blocked cookies with a yellow background.</span></span>  

:::image type="complex" source="../../images/2020/01/blockedcookies.msft.png" alt-text="在 "应用程序" 面板的 "Cookie" 窗格中阻止的 cookie" lightbox="../../images/2020/01/blockedcookies.msft.png":::
   <span data-ttu-id="b1780-203">在 "应用程序" 面板的 "Cookie" 窗格中阻止的 cookie</span><span class="sxs-lookup"><span data-stu-id="b1780-203">Blocked cookies in the Cookies pane of the Application panel</span></span>  
:::image-end:::  

<span data-ttu-id="b1780-204">Chromium 问题 [#1030258][CR1030258]</span><span class="sxs-lookup"><span data-stu-id="b1780-204">Chromium issue [#1030258][CR1030258]</span></span>  <!-- inaccessible  -->  

#### <span data-ttu-id="b1780-205">Cookie 窗格中的 cookie 优先级</span><span class="sxs-lookup"><span data-stu-id="b1780-205">Cookie priority in the Cookie pane</span></span>  

<span data-ttu-id="b1780-206">网络和应用程序面板中的 Cookie 表现在包含 " **优先级** " 列。</span><span class="sxs-lookup"><span data-stu-id="b1780-206">The Cookies tables in the Network and Application panels now include a **Priority** column.</span></span>  

> [!CAUTION]
> <span data-ttu-id="b1780-207">基于 Chromium 的浏览器（如 Microsoft Edge）是唯一支持 cookie 优先级的浏览器。</span><span class="sxs-lookup"><span data-stu-id="b1780-207">Chromium-based browsers, like Microsoft Edge, are the only browsers that support cookie priority.</span></span>  

<span data-ttu-id="b1780-208">Chromium 问题 [#1026879][CR1026879]</span><span class="sxs-lookup"><span data-stu-id="b1780-208">Chromium issue [#1026879][CR1026879]</span></span>  

#### <span data-ttu-id="b1780-209">编辑所有 cookie 值</span><span class="sxs-lookup"><span data-stu-id="b1780-209">Edit all cookie values</span></span>  

<span data-ttu-id="b1780-210">现在，Cookie 表中的所有单元格都是可编辑的，但 **Size** 列中的单元格，因为该列表示该 Cookie 的网络大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="b1780-210">All cells in the Cookie tables are editable now, except cells in the **Size** column because that column represents the network size of the cookie, in bytes.</span></span>  <span data-ttu-id="b1780-211">有关每个列的说明，请参阅 [字段][CookiesFields] 。</span><span class="sxs-lookup"><span data-stu-id="b1780-211">See [Fields][CookiesFields] for an explanation of each column.</span></span>  

:::image type="complex" source="../../images/2020/01/editcookie.msft.png" alt-text="编辑 cookie 值" lightbox="../../images/2020/01/editcookie.msft.png":::
   <span data-ttu-id="b1780-213">编辑 cookie 值</span><span class="sxs-lookup"><span data-stu-id="b1780-213">Editing a cookie value</span></span>  
:::image-end:::  

#### <span data-ttu-id="b1780-214">复制为 Node.js 提取以包括 cookie 数据</span><span class="sxs-lookup"><span data-stu-id="b1780-214">Copy as Node.js fetch to include cookie data</span></span>  

<span data-ttu-id="b1780-215">右键单击网络请求并选择 "**复制**  >  **副本" Node.js** "获取" 以获取 `fetch` 包含 cookie 数据的表达式。</span><span class="sxs-lookup"><span data-stu-id="b1780-215">Right-click a network request and select **Copy** > **Copy as Node.js fetch** to get a `fetch` expression that includes cookie data.</span></span>  

:::image type="complex" source="../../images/2020/01/fetchcookies.msft.png" alt-text="复制为 Node.js 提取" lightbox="../../images/2020/01/fetchcookies.msft.png":::
   <span data-ttu-id="b1780-217">复制为 Node.js 提取</span><span class="sxs-lookup"><span data-stu-id="b1780-217">Copy as Node.js fetch</span></span>  
:::image-end:::  

<span data-ttu-id="b1780-218">Chromium 问题 [#1029826][CR1029826]</span><span class="sxs-lookup"><span data-stu-id="b1780-218">Chromium issue [#1029826][CR1029826]</span></span>  

### <span data-ttu-id="b1780-219">更准确的 web 应用清单图标</span><span class="sxs-lookup"><span data-stu-id="b1780-219">More accurate web app manifest icons</span></span>  

<span data-ttu-id="b1780-220">以前，应用程序面板中的清单窗格发送了其自己的请求，以便显示 web 应用清单图标。</span><span class="sxs-lookup"><span data-stu-id="b1780-220">Previously, the Manifest pane in the Application panel sent its own requests in order to display web app manifest icons.</span></span>  <span data-ttu-id="b1780-221">DevTools 现在显示 Microsoft Edge 使用的完全相同的清单图标。</span><span class="sxs-lookup"><span data-stu-id="b1780-221">DevTools now shows the exact same manifest icon that Microsoft Edge uses.</span></span>  

:::image type="complex" source="../../images/2020/01/manifesticons.msft.png" alt-text="清单窗格中的图标" lightbox="../../images/2020/01/manifesticons.msft.png":::
   <span data-ttu-id="b1780-223">清单窗格中的图标</span><span class="sxs-lookup"><span data-stu-id="b1780-223">Icons in the Manifest pane</span></span>  
:::image-end:::  

<span data-ttu-id="b1780-224">Chromium 问题 [#985402][CR985402]</span><span class="sxs-lookup"><span data-stu-id="b1780-224">Chromium issue [#985402][CR985402]</span></span>  

### <span data-ttu-id="b1780-225">将鼠标悬停在 CSS 内容属性上以查看非转义值</span><span class="sxs-lookup"><span data-stu-id="b1780-225">Hover over CSS content properties to see unescaped values</span></span>  

<span data-ttu-id="b1780-226">将鼠标悬停在某个属性的值上 `content` 以查看该值的非转义版本。</span><span class="sxs-lookup"><span data-stu-id="b1780-226">Hover over the value of a `content` property to see the unescaped version of the value.</span></span>  

<span data-ttu-id="b1780-227">例如，在此 [演示][CSSContentDemo] 中，当你检查 `p::after` 伪元素时，在 "样式" 窗格中看到转义的字符串：</span><span class="sxs-lookup"><span data-stu-id="b1780-227">For example, in this [demo][CSSContentDemo] when you inspect the `p::after` pseudo-element you see an escaped string in the Styles pane:</span></span>  

:::image type="complex" source="../../images/2020/01/escapedstring.msft.png" alt-text="转义字符串" lightbox="../../images/2020/01/escapedstring.msft.png":::
   <span data-ttu-id="b1780-229">转义字符串</span><span class="sxs-lookup"><span data-stu-id="b1780-229">The escaped string</span></span>  
:::image-end:::  

<span data-ttu-id="b1780-230">将鼠标悬停在值上时 `content` ，将看到非转义值：</span><span class="sxs-lookup"><span data-stu-id="b1780-230">When you hover over the `content` value you see the unescaped value:</span></span>  

:::image type="complex" source="../../images/2020/01/unescapedstring.msft.png" alt-text="非转义值" lightbox="../../images/2020/01/unescapedstring.msft.png":::
   <span data-ttu-id="b1780-232">非转义值</span><span class="sxs-lookup"><span data-stu-id="b1780-232">The unescaped value</span></span>  
:::image-end:::  

### <span data-ttu-id="b1780-233">控制台中的更多详细源地图错误</span><span class="sxs-lookup"><span data-stu-id="b1780-233">More detailed source map errors in the Console</span></span>  

<span data-ttu-id="b1780-234">该控制台现在提供了有关为何无法加载或分析源映射的详细信息。</span><span class="sxs-lookup"><span data-stu-id="b1780-234">The Console now provides more detail on why a source map failed to load or parse.</span></span>  <span data-ttu-id="b1780-235">以前它只是在未解释出错的情况下提供了错误。</span><span class="sxs-lookup"><span data-stu-id="b1780-235">Previously it just provided an error without explaining what went wrong.</span></span>  

:::image type="complex" source="../../images/2020/01/sourcemap.msft.png" alt-text="控制台中的源映射加载错误" lightbox="../../images/2020/01/sourcemap.msft.png":::
   <span data-ttu-id="b1780-237">控制台中的源映射加载错误</span><span class="sxs-lookup"><span data-stu-id="b1780-237">A source map loading error in the Console</span></span>  
:::image-end:::  

### <span data-ttu-id="b1780-238">用于禁用超过文件末尾的滚动的设置</span><span class="sxs-lookup"><span data-stu-id="b1780-238">Setting for disabling scrolling past the end of a file</span></span>  

<span data-ttu-id="b1780-239">打开 "[设置][Settings]"，然后禁用**首选项**  >  **源**  >  **允许滚动浏览文件末尾**，以禁用在 "**源**" 面板中滚动浏览文件末尾更好的默认 UI 行为。</span><span class="sxs-lookup"><span data-stu-id="b1780-239">Open [Settings][Settings] and then disable **Preferences** > **Sources** > **Allow scrolling past end of file** to disable the default UI behavior that allows you to scroll well past the end of a file in the **Sources** panel.</span></span>  

:::image type="complex" source="../../images/2020/01/settings.msft.png" alt-text="禁用 "允许滚动超过文件结尾"" lightbox="../../images/2020/01/settings.msft.png":::
   <span data-ttu-id="b1780-241">在 "设置" 中禁用 " **允许滚动超过文件结尾** "</span><span class="sxs-lookup"><span data-stu-id="b1780-241">Disabling **Allow scrolling past end of file** in Settings</span></span>  
:::image-end:::  

:::image type="complex" source="../../images/2020/01/scrollingsources.msft.png" alt-text="现在，在 "源" 面板中已禁用滚动超过文件末尾的功能" lightbox="../../images/2020/01/scrollingsources.msft.png":::
   <span data-ttu-id="b1780-243">现在，在 "源" 面板中已禁用滚动超过文件末尾的功能</span><span class="sxs-lookup"><span data-stu-id="b1780-243">Scrolling past the end of a file is now disabled in the Sources panel</span></span>  
:::image-end:::  

## <span data-ttu-id="b1780-244">下载 Microsoft Edge 预览频道</span><span class="sxs-lookup"><span data-stu-id="b1780-244">Download the Microsoft Edge preview channels</span></span>  

<span data-ttu-id="b1780-245">如果你使用的是 Windows 或 macOS，请考虑使用 [ Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels] 作为默认开发浏览器。</span><span class="sxs-lookup"><span data-stu-id="b1780-245">If you are on Windows or macOS, consider using the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] as your default development browser.</span></span>  <span data-ttu-id="b1780-246">预览频道使你能够访问最新的 DevTools 功能。</span><span class="sxs-lookup"><span data-stu-id="b1780-246">The preview channels give you access to the latest DevTools features.</span></span>  

## <span data-ttu-id="b1780-247">与 Microsoft Edge DevTools 团队取得联系</span><span class="sxs-lookup"><span data-stu-id="b1780-247">Getting in touch with Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- links -->  

[DeviceToolbar]: /microsoft-edge/devtools-guide-chromium/device-mode/index#simulate-a-mobile-viewport "模拟移动区-在 Microsoft Edge DevTools 中使用设备模式模拟移动设备 |Microsoft 文档"
[DeviceFrame]: /microsoft-edge/devtools-guide-chromium/device-mode/index#show-device-frame "显示设备框架-在 Microsoft Edge DevTools 中通过设备模式模拟移动设备 |Microsoft 文档"
[CommandMenu]: /microsoft-edge/devtools-guide-chromium/command-menu/index "通过 Microsoft Edge DevTools 命令菜单运行命令 |Microsoft 文档"  
[ThrottleNetworkAndCpu]: /microsoft-edge/devtools-guide-chromium/device-mode/index#throttle-the-network-and-cpu "通过 Microsoft Edge DevTools 中的设备模式对网络和 CPU 进行限制-模拟移动设备 |Microsoft 文档"
[Settings]: /microsoft-edge/devtools-guide-chromium/customize/index#settings "设置-自定义 Microsoft Edge DevTools |Microsoft 文档"
[MicrosoftVisualStudio]: /microsoft-edge/visual-studio/index "Visual Studio |Microsoft 文档"  
[CookiesFields]: /microsoft-edge/devtools-guide-chromium/storage/cookies#fields "字段-查看、编辑和删除 Microsoft Edge DevTools 的 cookie |Microsoft 文档"  

[VisualStudioCodeDebuggerEdgeExtension]: /microsoft-edge/visual-studio-code/debugger-for-edge "Microsoft Edge Visual Studio 代码扩展的调试器"  
[VisualStudioCodeElementEdgeExtension]: /microsoft-edge/visual-studio-code/elements-for-edge "Microsoft Edge Visual Studio 代码扩展的元素"  

[MicrosoftEdgePreviewChannels]: https://aka.ms/microsoftedge "Microsoft Edge 预览频道"  

[VisualStudioCode]: https://aka.ms/vscode "Visual Studio 代码"  
[VisualStudioMarketplaceDebuggerEdge]: https://aka.ms/debugger4code "Microsoft Edge 的调试器-Visual Studio Marketplace"  
[VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension]: https://aka.ms/elements4code "Microsoft Edge \ (的元素 \ ) Chromium \-Visual Studio Marketplace"  
[VisualStudioMarketplaceWebhintExtension]: https://aka.ms/webhint4code "webhint-Visual Studio Marketplace"

[TrackingPrevention]: https://aka.ms/microsoftedge/tracking-prevention-blog "改进 Microsoft Edge 博客文章中的跟踪保护"

[MicrosoftEdgeInsiderAddons]: https://aka.ms/webhint/edge-extension "Microsoft Edge 预览体验计划 Addons"  
[MicrosoftVisualStudioDownloads]: https://aka.ms/vs/download "下载适用于 Windows & Mac 的 Visual Studio 2019"  

[PostTweetEdgeDevTools]: https://aka.ms/tweet/edgedevtools "@EdgeDevTools | 发布推文"  

[CR924693]: https://crbug.com/924693 "功能请求：将 Moto G4 添加到设备模式列表 |Chromium Bug"  
[CR1030258]: https://crbug.com/1030258 "CR 1030258 |Chromium Bug"  
[CR1026879]: https://crbug.com/1026879 "开发人员控制台中的 "Cookie" 选项卡不再显示优先级 |Chromium Bug"  
[CR1029826]: https://crbug.com/1029826 ""网络" 选项卡-> 右键单击以请求-> 复制 > 复制为 "获取" 不复制 cookie |Chromium Bug"  
[CR985402]: https://crbug.com/985402 "web 应用清单图标错误字符串很混乱 |Chromium Bug"  
[CR963183]: https://crbug.com/963183 "DevTools 不符合 WCAG 标准 |Chromium Bug"  
[CR941561]: https://crbug.com/941561 "DevTools | 的本地化Chromium Bug"  
[CR987787]: https://crbug.com/987787 "Dom 3D 视图 |Chromium Bug"  

[CSSContentDemo]: https://mathiasbynens.github.io/css-dbg-stories/css-escapes.html "非转义 CSS 内容的演示"  

[GitHubMicrosoftDocsEdgeDeveloperNewIssue]: https://aka.ms/edgedevtoolsdocs/feedback "新问题 - MicrosoftDocs/edge-developer"  

[TheWebWeWant]: https://aka.ms/webwewant "我们需要的网站"  
[AccessibilityInsights]: https://aka.ms/a11yinsights "辅助功能见解"  
[MDNDocumentObjectModel]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model "文档对象模型 (DOM) |MDN"  
[MDNZIndex]: https://developer.mozilla.org/docs/Web/CSS/z-index "z-索引 |MDN"  
[EdgeDevToolsTwitterAccount]: https://aka.ms/twitter/edgedevtools "@EdgeDevTools Twitter 帐户"  

[Webhint]: https://aka.ms/webhint "webhint"  

[WebhintBrowserExtension]: https://aka.ms/webhint/browser-extension "Webhint 浏览器扩展 |webhint 文档"  
[WebhintVisualStudioCodeExtension]: https://aka.ms/webhint/code-extension "Webhint Visual Studio 代码扩展 |webhint 文档"  

> [!NOTE]
> <span data-ttu-id="b1780-284">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="b1780-284">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="b1780-285">原始页面位于[此处](https://developers.google.com/web/updates/2020/01/devtools/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="b1780-285">The original page is found [here](https://developers.google.com/web/updates/2020/01/devtools/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="b1780-287">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="b1780-287">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  