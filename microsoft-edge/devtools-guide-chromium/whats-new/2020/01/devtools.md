---
description: 3D 视图、Visual Studio 与 Microsoft Edge 的集成等。
title: DevTools (Microsoft Edge 81) 中的新增功能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 9dd47a38f345601f2d459d39e3ee7b1728df8971
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993413"
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

# <span data-ttu-id="d4a48-104">DevTools （Microsoft Edge 81）中的新增功能</span><span class="sxs-lookup"><span data-stu-id="d4a48-104">What's New In DevTools (Microsoft Edge 81)</span></span>  

## <span data-ttu-id="d4a48-105">来自 Microsoft Edge 开发人员工具团队公告</span><span class="sxs-lookup"><span data-stu-id="d4a48-105">Announcements from the Microsoft Edge DevTools team</span></span>  

<span data-ttu-id="d4a48-106">以下各部分是你可能错过的 Microsoft Edge 开发人员工具团队的公告列表！</span><span class="sxs-lookup"><span data-stu-id="d4a48-106">The following sections are a list of announcements you may have missed from the Microsoft Edge DevTools team!</span></span> <span data-ttu-id="d4a48-107">请查看这些公告，尝试使用 DevTools 和 VS 代码扩展等中的新功能。</span><span class="sxs-lookup"><span data-stu-id="d4a48-107">Check them out to try new features in the DevTools, VS Code extensions, and more.</span></span>  <span data-ttu-id="d4a48-108">若要了解有关开发人员工具中的所有最新功能和最强大功能的最新动态，请下载 [Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels]并[在 Twitter 上关注我们][EdgeDevToolsTwitterAccount]。</span><span class="sxs-lookup"><span data-stu-id="d4a48-108">To stay up to date on all the latest and greatest features in your developer tools, download the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] and [follow us on Twitter][EdgeDevToolsTwitterAccount].</span></span>  

### <span data-ttu-id="d4a48-109">对 DevTools 的辅助功能改进</span><span class="sxs-lookup"><span data-stu-id="d4a48-109">Accessibility improvements to the DevTools</span></span>  

<span data-ttu-id="d4a48-110">DevTools 团队已向 Chromium 提供170更改，以解决 DevTools 中的高影响力颜色对比度、键盘和屏幕阅读器问题。</span><span class="sxs-lookup"><span data-stu-id="d4a48-110">The DevTools team has contributed 170 changes to Chromium to address high-impact color contrast, keyboard, and screen reader issues in the DevTools.</span></span>  <span data-ttu-id="d4a48-111">每个构建 web 的开发人员都应该能够使用 DevTools。</span><span class="sxs-lookup"><span data-stu-id="d4a48-111">Every developer building the web should be able to use the DevTools.</span></span>  

> ##### <span data-ttu-id="d4a48-112">图 1</span><span class="sxs-lookup"><span data-stu-id="d4a48-112">Figure 1</span></span>  
> <span data-ttu-id="d4a48-113">DevTools 中的性能工具改进了键盘导航和屏幕阅读器</span><span class="sxs-lookup"><span data-stu-id="d4a48-113">The Performance tool in the DevTools with the keyboard navigation and screen reader improvements</span></span>  
> ![DevTools 中的性能工具改进了键盘导航和屏幕阅读器][ImagePerformanceToolKeyboardReaderImprovements]  

<span data-ttu-id="d4a48-115">希望了解如何让您的网页对所有用户都易于访问？</span><span class="sxs-lookup"><span data-stu-id="d4a48-115">Want to learn how to make your web page accessible to all of your users?</span></span>  <span data-ttu-id="d4a48-116">下载 Microsoft Edge 的 [辅助功能见解][AccessibilityInsights] 和 [webhint][WebhintBrowserExtension] 扩展以开始使用。</span><span class="sxs-lookup"><span data-stu-id="d4a48-116">Download the [Accessibility Insights][AccessibilityInsights] and [webhint][WebhintBrowserExtension] extensions for Microsoft Edge to get started.</span></span>  

<span data-ttu-id="d4a48-117">如果您使用屏幕阅读器或键盘在 DevTools 中导航，请通过 [发推至][PostTweetEdgeDevTools] 与我们联系或单击 " [发送反馈](#getting-in-touch-with-microsoft-edge-devtools-team) " 图标向我们发送您的反馈！</span><span class="sxs-lookup"><span data-stu-id="d4a48-117">If you use screen readers or the keyboard to navigate around the DevTools, send us your feedback by [tweeting][PostTweetEdgeDevTools] at us or clicking the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!</span></span>  

<span data-ttu-id="d4a48-118">Chromium 问题 [#963183][crbug963183]</span><span class="sxs-lookup"><span data-stu-id="d4a48-118">Chromium issue [#963183][crbug963183]</span></span>  

### <span data-ttu-id="d4a48-119">使用其他语言的 DevTools</span><span class="sxs-lookup"><span data-stu-id="d4a48-119">Using the DevTools in other languages</span></span>  

<span data-ttu-id="d4a48-120">许多开发人员使用其他开发人员工具，如 StackOverflow 和 VS 代码，采用其母语，而不仅仅是英语。</span><span class="sxs-lookup"><span data-stu-id="d4a48-120">Many developers use other developer tools, like StackOverflow and VS Code, in their native language, not just in English.</span></span>  <span data-ttu-id="d4a48-121">我们很高兴宣布 DevTools 的本地化，您现在可以使用英语之外的10种语言中的一种：</span><span class="sxs-lookup"><span data-stu-id="d4a48-121">We’re excited to announce localization for the DevTools, which you are now able to use in one of 10 languages besides English:</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="d4a48-122"> (简体中文 \ ) - &#20013;&#25991;&#65288;&#31616;&#20307;&#65289;</span><span class="sxs-lookup"><span data-stu-id="d4a48-122">Chinese \(Simplified\) - &#20013;&#25991;&#65288;&#31616;&#20307;&#65289;</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="d4a48-123">中文 (传统版 \ ) - &#20013;&#25991;&#65288;&#32321;&#39636;&#65289;</span><span class="sxs-lookup"><span data-stu-id="d4a48-123">Chinese \(Traditional\) - &#20013;&#25991;&#65288;&#32321;&#39636;&#65289;</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      <span data-ttu-id="d4a48-124">法语-fran&#231;ais</span><span class="sxs-lookup"><span data-stu-id="d4a48-124">French – fran&#231;ais</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="d4a48-125">德语-德语</span><span class="sxs-lookup"><span data-stu-id="d4a48-125">German - deutsch</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      <span data-ttu-id="d4a48-126">意大利语-意大利语</span><span class="sxs-lookup"><span data-stu-id="d4a48-126">Italian - italiano</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="d4a48-127">日语- &#26085;&#26412;&#35486;</span><span class="sxs-lookup"><span data-stu-id="d4a48-127">Japanese - &#26085;&#26412;&#35486;</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      <span data-ttu-id="d4a48-128">朝鲜语- &#54620;&#44397;&#50612;</span><span class="sxs-lookup"><span data-stu-id="d4a48-128">Korean - &#54620;&#44397;&#50612;</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="d4a48-129">葡萄牙语-portugu&#234;s</span><span class="sxs-lookup"><span data-stu-id="d4a48-129">Portuguese - portugu&#234;s</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      <span data-ttu-id="d4a48-130">俄语–  &#1088;&#1091;&#1089;&#1089;&#1082;&#1080;&#1081;</span><span class="sxs-lookup"><span data-stu-id="d4a48-130">Russian – &#1088;&#1091;&#1089;&#1089;&#1082;&#1080;&#1081;</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="d4a48-131">西班牙语-espa&#241;ol</span><span class="sxs-lookup"><span data-stu-id="d4a48-131">Spanish - espa&#241;ol</span></span>
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

<span data-ttu-id="d4a48-132">DevTools 将自动匹配您在的 Microsoft Edge 中使用的语言 `edge://settings/languages` 。</span><span class="sxs-lookup"><span data-stu-id="d4a48-132">The DevTools automatically match the language you use for Microsoft Edge in `edge://settings/languages`.</span></span>  

<span data-ttu-id="d4a48-133">如果你希望 Microsoft Edge 采用一种语言，并且你的 DevTools 保留为英语，请按 `F1` DevTools 打开 " [设置][Settings] "，然后禁用 " **匹配浏览器语言**"。</span><span class="sxs-lookup"><span data-stu-id="d4a48-133">If you want Microsoft Edge to be in one language and your DevTools to remain in English, press `F1` in the DevTools to open [Settings][Settings] and disable **Match browser language**.</span></span>  

> ##### <span data-ttu-id="d4a48-134">图 2</span><span class="sxs-lookup"><span data-stu-id="d4a48-134">Figure 2</span></span>  
> <span data-ttu-id="d4a48-135">德语中的 DevTools</span><span class="sxs-lookup"><span data-stu-id="d4a48-135">The DevTools in German</span></span>  
> ![德语中的 DevTools][ImageLocalizedGerman]  

<span data-ttu-id="d4a48-137">不本地化**控制台**消息。</span><span class="sxs-lookup"><span data-stu-id="d4a48-137">**Console** messages are not localized.</span></span>  <span data-ttu-id="d4a48-138">仅在 DevTools UI 中使用的字符串以用于 Microsoft Edge 的语言显示。</span><span class="sxs-lookup"><span data-stu-id="d4a48-138">Only the strings used in the DevTools UI are displayed in the language you use for Microsoft Edge.</span></span>  

<span data-ttu-id="d4a48-139">如果您想要使用的 DevTools 语言与可用的语言不同，请 [tweet][PostTweetEdgeDevTools] ，或单击 " [发送反馈](#getting-in-touch-with-microsoft-edge-devtools-team) " 图标。</span><span class="sxs-lookup"><span data-stu-id="d4a48-139">If you want to use the DevTools in a different language than the ones that are available, [tweet][PostTweetEdgeDevTools] at us or click the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon.</span></span>  

<span data-ttu-id="d4a48-140">Chromium 问题 [#941561][crbug941561]</span><span class="sxs-lookup"><span data-stu-id="d4a48-140">Chromium issue [#941561][crbug941561]</span></span>  

### <span data-ttu-id="d4a48-141">webhint Microsoft Edge 扩展</span><span class="sxs-lookup"><span data-stu-id="d4a48-141">webhint Microsoft Edge extension</span></span>  

<span data-ttu-id="d4a48-142">Webhint Microsoft Edge 扩展使你能够轻松地浏览网页并在 DevTools 中获取有关辅助功能、浏览器兼容性、安全性、性能等的反馈。</span><span class="sxs-lookup"><span data-stu-id="d4a48-142">The webhint Microsoft Edge extension allows you to easily scan your web page and get feedback on accessibility, browser compatibility, security, performance, and more within the DevTools.</span></span>  <span data-ttu-id="d4a48-143">阅读详细信息 [https://webhint.io][Webhint] 。</span><span class="sxs-lookup"><span data-stu-id="d4a48-143">Read more at [https://webhint.io][Webhint].</span></span>  

> ##### <span data-ttu-id="d4a48-144">图 3</span><span class="sxs-lookup"><span data-stu-id="d4a48-144">Figure 3</span></span>  
> <span data-ttu-id="d4a48-145">安装 webhint 浏览器扩展时，DevTools 中的 "提示" 选项卡</span><span class="sxs-lookup"><span data-stu-id="d4a48-145">The Hints tab in the DevTools when the webhint browser extension is installed</span></span>  
> ![安装 webhint 浏览器扩展时，DevTools 中的 "提示" 选项卡][ImageHintsTabWebhintExtension]  

<span data-ttu-id="d4a48-147">[在 Microsoft Edge 中尝试 webhint 浏览器扩展][MicrosoftEdgeInsiderAddons]。</span><span class="sxs-lookup"><span data-stu-id="d4a48-147">[Try the webhint browser extension in Microsoft Edge][MicrosoftEdgeInsiderAddons].</span></span>  <span data-ttu-id="d4a48-148">安装扩展后，打开 DevTools 并选择 "提示" 选项卡。 在此处，运行可自定义的网站扫描。</span><span class="sxs-lookup"><span data-stu-id="d4a48-148">Once you install the extension, open the DevTools and select the Hints tab.  From here, run a customizable site scan.</span></span>  <span data-ttu-id="d4a48-149">请转到 [webhint.io][WebhintBrowserExtension] 以了解更多信息。</span><span class="sxs-lookup"><span data-stu-id="d4a48-149">Head over to [webhint.io][WebhintBrowserExtension] to learn more.</span></span>  

### <span data-ttu-id="d4a48-150">3D 视图</span><span class="sxs-lookup"><span data-stu-id="d4a48-150">3D View</span></span>  

<span data-ttu-id="d4a48-151">通过浏览[文档对象模型 (DOM \ ) ][MDNDocumentObjectModel]或[z 索引][MDNZIndex]堆栈上下文，使用**3d 视图**调试 web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="d4a48-151">Use the **3D View** to debug your web application by navigating through the [Document Object Model \(DOM\)][MDNDocumentObjectModel] or the [z-index][MDNZIndex] stacking context.</span></span>  

> ##### <span data-ttu-id="d4a48-152">图 4</span><span class="sxs-lookup"><span data-stu-id="d4a48-152">Figure 4</span></span>  
> <span data-ttu-id="d4a48-153">DevTools 中的3D 视图</span><span class="sxs-lookup"><span data-stu-id="d4a48-153">The 3D View in the DevTools</span></span>  
> ![DevTools 中的3D 视图][Image3DView]  

<span data-ttu-id="d4a48-155">若要访问3d 视图，请按 `Ctrl`  +  `Shift`  +  `P` ，在**3d 视图**中键入，然后选择 "**显示3d 视图**"。</span><span class="sxs-lookup"><span data-stu-id="d4a48-155">To access the 3D View, press `Ctrl` + `Shift` + `P`, type in **3D View** and select **Show 3D View**.</span></span>  

<span data-ttu-id="d4a48-156">我们正在处理 UI 并向3D 视图添加更多功能，因此请向我们发送 [反馈](#getting-in-touch-with-microsoft-edge-devtools-team)。</span><span class="sxs-lookup"><span data-stu-id="d4a48-156">We're working on the UI and adding more functionality to the 3D View, so please send us your [feedback](#getting-in-touch-with-microsoft-edge-devtools-team).</span></span>  

<span data-ttu-id="d4a48-157">Chromium 问题 [#987787][crbug987787]</span><span class="sxs-lookup"><span data-stu-id="d4a48-157">Chromium issue [#987787][crbug987787]</span></span>  

### <span data-ttu-id="d4a48-158">Visual Studio 代码扩展</span><span class="sxs-lookup"><span data-stu-id="d4a48-158">Visual Studio Code extensions</span></span>  

<span data-ttu-id="d4a48-159">DevTools 团队还发布了一些适用于 [Visual Studio 代码 \ (和代码 \ ) ][VisualStudioCode] 的扩展，使你可以直接从文本编辑器中使用 DevTools 的强大功能！</span><span class="sxs-lookup"><span data-stu-id="d4a48-159">The DevTools team has also released some extensions for [Visual Studio Code \(VS Code\)][VisualStudioCode] that let you use the power of the DevTools directly from your text editor!</span></span> <span data-ttu-id="d4a48-160">请查看下面的分机：</span><span class="sxs-lookup"><span data-stu-id="d4a48-160">Check out the extensions below:</span></span>  

#### <span data-ttu-id="d4a48-161">Microsoft Edge 元素</span><span class="sxs-lookup"><span data-stu-id="d4a48-161">Elements for Microsoft Edge</span></span>  

<span data-ttu-id="d4a48-162">通过添加 [Microsoft Edge \ (Chromium \ ) ][VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension] 与代码扩展的元素，从 vs 代码内使用 "元素" 工具。</span><span class="sxs-lookup"><span data-stu-id="d4a48-162">Use the Elements tool from within VS Code by adding the [Elements for Microsoft Edge \(Chromium\)][VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension] VS Code extension.</span></span>  

> ##### <span data-ttu-id="d4a48-163">图 5</span><span class="sxs-lookup"><span data-stu-id="d4a48-163">Figure 5</span></span>  
> <span data-ttu-id="d4a48-164">VS 代码中的元素工具使用 Microsoft Edge 扩展的元素 ![ 使用适用于 Microsoft edge 扩展的元素的 Vs 代码中的元素工具][ImageElementsVisualStudioCode]</span><span class="sxs-lookup"><span data-stu-id="d4a48-164">The Elements tool in VS Code using the Elements for Microsoft Edge extension ![The Elements tool in VS Code using the Elements for Microsoft Edge extension][ImageElementsVisualStudioCode]</span></span>  

<span data-ttu-id="d4a48-165">有关详细信息，请查看 [Microsoft Edge 的元素与代码扩展][VisualStudioCodeElementEdgeExtension]。</span><span class="sxs-lookup"><span data-stu-id="d4a48-165">For more information, check out [Elements for Microsoft Edge VS Code extension][VisualStudioCodeElementEdgeExtension].</span></span>  

#### <span data-ttu-id="d4a48-166">Microsoft Edge 调试器</span><span class="sxs-lookup"><span data-stu-id="d4a48-166">Debugger for Microsoft Edge</span></span>  

<span data-ttu-id="d4a48-167">借助 [适用于 Microsoft edge][VisualStudioMarketplaceDebuggerEdge] 和代码扩展的调试器，在 microsoft Edge 中直接通过 VS 代码调试运行 JavaScript！</span><span class="sxs-lookup"><span data-stu-id="d4a48-167">With the [Debugger for Microsoft Edge][VisualStudioMarketplaceDebuggerEdge] VS Code extension, debug JavaScript running in Microsoft Edge directly from VS Code!</span></span>  

> ##### <span data-ttu-id="d4a48-168">图 6</span><span class="sxs-lookup"><span data-stu-id="d4a48-168">Figure 6</span></span>  
> <span data-ttu-id="d4a48-169">VS 代码中的 Microsoft Edge 扩展调试器</span><span class="sxs-lookup"><span data-stu-id="d4a48-169">The Debugger for Microsoft Edge Extension in VS Code</span></span>  
> ![VS 代码中的 Microsoft Edge 扩展调试器][ImageDebuggerExtensionVisualStudioCode]  

<span data-ttu-id="d4a48-171">有关详细信息，请参阅 [如何从 VS 代码调试 Microsoft Edge][VisualStudioCodeDebuggerEdgeExtension]。</span><span class="sxs-lookup"><span data-stu-id="d4a48-171">For more information, check out [how to debug Microsoft Edge from VS Code][VisualStudioCodeDebuggerEdgeExtension].</span></span>  

#### <span data-ttu-id="d4a48-172">webhint</span><span class="sxs-lookup"><span data-stu-id="d4a48-172">webhint</span></span>  

<span data-ttu-id="d4a48-173">编写时， [webhint][VisualStudioMarketplaceWebhintExtension] 和代码扩展用于 `webhint` 改进网页！</span><span class="sxs-lookup"><span data-stu-id="d4a48-173">The [webhint][VisualStudioMarketplaceWebhintExtension] VS Code extension uses `webhint` to improve your web page while you're writing it!</span></span> <span data-ttu-id="d4a48-174">此扩展基于分析对工作区文件运行和报告诊断 `webhint` 。</span><span class="sxs-lookup"><span data-stu-id="d4a48-174">This extension runs and reports diagnostics on your workspace files based on `webhint` analysis.</span></span>  

> ##### <span data-ttu-id="d4a48-175">图 7</span><span class="sxs-lookup"><span data-stu-id="d4a48-175">Figure 7</span></span>  
> <span data-ttu-id="d4a48-176">在 VS 代码中分析 tsx 文件的 webhint 与代码扩展</span><span class="sxs-lookup"><span data-stu-id="d4a48-176">The webhint VS Code extension analyzing a .tsx file in VS Code</span></span>  
> ![在 VS 代码中分析 tsx 文件的 webhint 与代码扩展][ImageWebhintVisualStudioCodeExtensionWorkspace]  

<span data-ttu-id="d4a48-178">[了解有关 VS 代码 webhint 扩展的详细信息][WebhintVisualStudioCodeExtension]。</span><span class="sxs-lookup"><span data-stu-id="d4a48-178">[Learn more about the VS Code webhint extension][WebhintVisualStudioCodeExtension].</span></span>  

### <span data-ttu-id="d4a48-179">Visual Studio 集成</span><span class="sxs-lookup"><span data-stu-id="d4a48-179">Visual Studio integration</span></span>  

<span data-ttu-id="d4a48-180">在 Visual Studio 2019 版本16.2 或更高版本中，使用 Visual Studio 调试器调试在 Microsoft Edge 中运行的 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="d4a48-180">In Visual Studio 2019 version 16.2 or later, use the Visual Studio debugger to debug JavaScript running in Microsoft Edge.</span></span>  <span data-ttu-id="d4a48-181">[下载 Visual Studio 2019][MicrosoftVisualStudioDownloads] 以试用此功能！</span><span class="sxs-lookup"><span data-stu-id="d4a48-181">[Download Visual Studio 2019][MicrosoftVisualStudioDownloads] to try this feature out!</span></span>  

> ##### <span data-ttu-id="d4a48-182">图 8</span><span class="sxs-lookup"><span data-stu-id="d4a48-182">Figure 8</span></span>  
> <span data-ttu-id="d4a48-183">带有在 Microsoft Edge 的 "应用"、"开发" 或 "Beta" 中启动 web 应用选项的 Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d4a48-183">Visual Studio with the option to launch your web app in Microsoft Edge Canary, Dev, or Beta</span></span>  
> ![带有在 Microsoft Edge 的 "应用"、"开发" 或 "Beta" 中启动 web 应用选项的 Visual Studio][ImageVisualStudioLaunchWebApp]  

<span data-ttu-id="d4a48-185">[了解有关从 Visual Studio 调试 Microsoft Edge 的详细信息][MicrosoftVisualStudio]。</span><span class="sxs-lookup"><span data-stu-id="d4a48-185">[Learn more about debugging Microsoft Edge from Visual Studio][MicrosoftVisualStudio].</span></span>  

### <span data-ttu-id="d4a48-186">跟踪保护控制台消息</span><span class="sxs-lookup"><span data-stu-id="d4a48-186">Tracking prevention Console messages</span></span>  

<span data-ttu-id="d4a48-187">"跟踪防护" 是 Microsoft Edge 中的一项独特功能，可防止您以前未访问过的网站对您进行跟踪。</span><span class="sxs-lookup"><span data-stu-id="d4a48-187">Tracking prevention is a unique feature in Microsoft Edge that protects you from being tracked by websites you haven't visited before.</span></span>  <span data-ttu-id="d4a48-188">默认跟踪防护设置为平衡模式，这将阻止第三方跟踪程序和已知恶意跟踪程序，以获取平衡隐私和 web 兼容性的体验。</span><span class="sxs-lookup"><span data-stu-id="d4a48-188">The default tracking prevention setting is Balanced mode, which blocks 3rd party trackers and known malicious trackers for an experience that balances privacy and web compatibility.</span></span>  <span data-ttu-id="d4a48-189">若要在某些跟踪器被阻止时更深入地了解网页的兼容性，我们还在跟踪器被阻止时在控制台中添加了警告消息。</span><span class="sxs-lookup"><span data-stu-id="d4a48-189">To give you more insight into the compatibility of your web page when certain trackers are blocked, we've also added warning messages in the Console when a tracker is blocked.</span></span>  

> ##### <span data-ttu-id="d4a48-190">图 9</span><span class="sxs-lookup"><span data-stu-id="d4a48-190">Figure 9</span></span>  
> <span data-ttu-id="d4a48-191">跟踪阻止阻止跟踪对存储的访问权限时的控制台中的消息</span><span class="sxs-lookup"><span data-stu-id="d4a48-191">Messages in the Console when tracking prevention blocks access to storage for a tracker</span></span>  
> ![跟踪阻止阻止跟踪对存储的访问权限时的控制台中的消息][ImageTrackingPrevention]  

<span data-ttu-id="d4a48-193">[阅读有关跟踪防护和隐私和 web 兼容性之间的平衡的详细信息][TrackingPrevention]。</span><span class="sxs-lookup"><span data-stu-id="d4a48-193">[Read more about tracking prevention and the balance between privacy and web compatibility][TrackingPrevention].</span></span>  

## <span data-ttu-id="d4a48-194">来自 Chromium 项目的公告</span><span class="sxs-lookup"><span data-stu-id="d4a48-194">Announcements from the Chromium project</span></span>  

<span data-ttu-id="d4a48-195">以下各节宣布了在 Microsoft Edge 81 中提供的其他功能，这些功能由开放的源 Chromium 项目所参与。</span><span class="sxs-lookup"><span data-stu-id="d4a48-195">The following sections announce additional features available in Microsoft Edge 81 that were contributed to the open source Chromium project.</span></span>  

### <span data-ttu-id="d4a48-196">设备模式下的 Moto G4 支持</span><span class="sxs-lookup"><span data-stu-id="d4a48-196">Moto G4 support in Device Mode</span></span>  

<span data-ttu-id="d4a48-197">[启用设备工具栏][DeviceToolbar]后，从**设备**列表中模拟 Moto G4 视区的尺寸。</span><span class="sxs-lookup"><span data-stu-id="d4a48-197">After [enabling the Device Toolbar][DeviceToolbar], simulate the dimensions of a Moto G4 viewport from the **Device** list.</span></span>  

> ##### <span data-ttu-id="d4a48-198">图 10</span><span class="sxs-lookup"><span data-stu-id="d4a48-198">Figure 10</span></span>  
> <span data-ttu-id="d4a48-199">模拟 Moto G4 视区</span><span class="sxs-lookup"><span data-stu-id="d4a48-199">Simulating a Moto G4 viewport</span></span>  
> ![模拟 Moto G4 视区][ImageMotoG4]  

<span data-ttu-id="d4a48-201">单击 " [显示设备帧][DeviceFrame] " 以显示视区周围的 Moto G4 硬件。</span><span class="sxs-lookup"><span data-stu-id="d4a48-201">Click [Show Device Frame][DeviceFrame] to show the Moto G4 hardware around the viewport.</span></span>  

> ##### <span data-ttu-id="d4a48-202">图 11</span><span class="sxs-lookup"><span data-stu-id="d4a48-202">Figure 11</span></span>  
> <span data-ttu-id="d4a48-203">显示 Moto G4 硬件</span><span class="sxs-lookup"><span data-stu-id="d4a48-203">Showing the Moto G4 hardware</span></span>  
> ![显示 Moto G4 硬件][ImageMotoG4Frame]  

<span data-ttu-id="d4a48-205">相关功能：</span><span class="sxs-lookup"><span data-stu-id="d4a48-205">Related features:</span></span>  

*   <span data-ttu-id="d4a48-206">[Command Menu][CommandMenu] `Capture screenshot` 在启用 "**显示设备框架**") 之后，打开命令菜单并运行命令以获取包含 Moto G4 (硬件的视区的屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="d4a48-206">Open the [Command Menu][CommandMenu] and run the `Capture screenshot` command to take a screenshot of the viewport that includes the Moto G4 hardware (after enabling **Show Device Frame**).</span></span>  
*   <span data-ttu-id="d4a48-207">[调节网络和 CPU][ThrottleNetworkAndCpu] 以更准确地模拟移动用户的 web 浏览条件。</span><span class="sxs-lookup"><span data-stu-id="d4a48-207">[Throttle the network and CPU][ThrottleNetworkAndCpu] to more accurately simulate a mobile user's web browsing conditions.</span></span>  

<span data-ttu-id="d4a48-208">Chromium 问题 [#924693][crbug924693]</span><span class="sxs-lookup"><span data-stu-id="d4a48-208">Chromium issue [#924693][crbug924693]</span></span>  

### <span data-ttu-id="d4a48-209">与 Cookie 相关的更新</span><span class="sxs-lookup"><span data-stu-id="d4a48-209">Cookie-related updates</span></span>  

#### <span data-ttu-id="d4a48-210">Cookie 窗格中阻止的 cookie</span><span class="sxs-lookup"><span data-stu-id="d4a48-210">Blocked cookies in the Cookies pane</span></span>  

<span data-ttu-id="d4a48-211">"应用程序" 面板中的 "Cookie" 窗格现在显示黄色背景的被阻止的 cookie。</span><span class="sxs-lookup"><span data-stu-id="d4a48-211">The Cookies pane in the Application panel now displays blocked cookies with a yellow background.</span></span>  

> ##### <span data-ttu-id="d4a48-212">图 12</span><span class="sxs-lookup"><span data-stu-id="d4a48-212">Figure 12</span></span>  
> <span data-ttu-id="d4a48-213">在 "应用程序" 面板的 "Cookie" 窗格中阻止的 cookie</span><span class="sxs-lookup"><span data-stu-id="d4a48-213">Blocked cookies in the Cookies pane of the Application panel</span></span>  
> ![在 "应用程序" 面板的 "Cookie" 窗格中阻止的 cookie][ImageBlockedCookies]  

<span data-ttu-id="d4a48-215">Chromium 问题 [#1030258][crbug|::ref1::|]</span><span class="sxs-lookup"><span data-stu-id="d4a48-215">Chromium issue [#1030258][crbug|::ref1::|]</span></span>  

#### <span data-ttu-id="d4a48-216">Cookie 窗格中的 cookie 优先级</span><span class="sxs-lookup"><span data-stu-id="d4a48-216">Cookie priority in the Cookie pane</span></span>  

<span data-ttu-id="d4a48-217">网络和应用程序面板中的 Cookie 表现在包含 " **优先级** " 列。</span><span class="sxs-lookup"><span data-stu-id="d4a48-217">The Cookies tables in the Network and Application panels now include a **Priority** column.</span></span>  

> [!CAUTION]
> <span data-ttu-id="d4a48-218">基于 Chromium 的浏览器（如 Microsoft Edge）是唯一支持 cookie 优先级的浏览器。</span><span class="sxs-lookup"><span data-stu-id="d4a48-218">Chromium-based browsers, like Microsoft Edge, are the only browsers that support cookie priority.</span></span>  

<span data-ttu-id="d4a48-219">Chromium 问题 [#1026879][crbug1026879]</span><span class="sxs-lookup"><span data-stu-id="d4a48-219">Chromium issue [#1026879][crbug1026879]</span></span>  

#### <span data-ttu-id="d4a48-220">编辑所有 cookie 值</span><span class="sxs-lookup"><span data-stu-id="d4a48-220">Edit all cookie values</span></span>  

<span data-ttu-id="d4a48-221">现在，Cookie 表中的所有单元格都是可编辑的，但 **Size** 列中的单元格，因为该列表示该 Cookie 的网络大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="d4a48-221">All cells in the Cookie tables are editable now, except cells in the **Size** column because that column represents the network size of the cookie, in bytes.</span></span>  <span data-ttu-id="d4a48-222">有关每个列的说明，请参阅 [字段][CookiesFields] 。</span><span class="sxs-lookup"><span data-stu-id="d4a48-222">See [Fields][CookiesFields] for an explanation of each column.</span></span>  

> ##### <span data-ttu-id="d4a48-223">图 13</span><span class="sxs-lookup"><span data-stu-id="d4a48-223">Figure 13</span></span>  
> <span data-ttu-id="d4a48-224">编辑 cookie 值</span><span class="sxs-lookup"><span data-stu-id="d4a48-224">Editing a cookie value</span></span>  
> ![编辑 cookie 值][ImageEditCookie]  

#### <span data-ttu-id="d4a48-226">复制为 Node.js 提取以包括 cookie 数据</span><span class="sxs-lookup"><span data-stu-id="d4a48-226">Copy as Node.js fetch to include cookie data</span></span>  

<span data-ttu-id="d4a48-227">右键单击网络请求并选择 "**复制**  >  **副本" Node.js** "获取" 以获取 `fetch` 包含 cookie 数据的表达式。</span><span class="sxs-lookup"><span data-stu-id="d4a48-227">Right-click a network request and select **Copy** > **Copy as Node.js fetch** to get a `fetch` expression that includes cookie data.</span></span>  

> ##### <span data-ttu-id="d4a48-228">图 14</span><span class="sxs-lookup"><span data-stu-id="d4a48-228">Figure 14</span></span>  
> <span data-ttu-id="d4a48-229">复制为 Node.js 提取</span><span class="sxs-lookup"><span data-stu-id="d4a48-229">Copy as Node.js fetch</span></span>  
> ![复制为 Node.js 提取][ImageCopyFetch]  

<span data-ttu-id="d4a48-231">Chromium 问题 [#1029826][crbug1029826]</span><span class="sxs-lookup"><span data-stu-id="d4a48-231">Chromium issue [#1029826][crbug1029826]</span></span>  

### <span data-ttu-id="d4a48-232">更准确的 web 应用清单图标</span><span class="sxs-lookup"><span data-stu-id="d4a48-232">More accurate web app manifest icons</span></span>  

<span data-ttu-id="d4a48-233">以前，应用程序面板中的清单窗格发送了其自己的请求，以便显示 web 应用清单图标。</span><span class="sxs-lookup"><span data-stu-id="d4a48-233">Previously, the Manifest pane in the Application panel sent its own requests in order to display web app manifest icons.</span></span>  <span data-ttu-id="d4a48-234">DevTools 现在显示 Microsoft Edge 使用的完全相同的清单图标。</span><span class="sxs-lookup"><span data-stu-id="d4a48-234">DevTools now shows the exact same manifest icon that Microsoft Edge uses.</span></span>  

> ##### <span data-ttu-id="d4a48-235">图 15</span><span class="sxs-lookup"><span data-stu-id="d4a48-235">Figure 15</span></span>  
> <span data-ttu-id="d4a48-236">清单窗格中的图标</span><span class="sxs-lookup"><span data-stu-id="d4a48-236">Icons in the Manifest pane</span></span>  
> ![清单窗格中的图标][ImageManifestIcon]  

<span data-ttu-id="d4a48-238">Chromium 问题 [#985402][crbug985402]</span><span class="sxs-lookup"><span data-stu-id="d4a48-238">Chromium issue [#985402][crbug985402]</span></span>  

### <span data-ttu-id="d4a48-239">将鼠标悬停在 CSS 内容属性上以查看非转义值</span><span class="sxs-lookup"><span data-stu-id="d4a48-239">Hover over CSS content properties to see unescaped values</span></span>  

<span data-ttu-id="d4a48-240">将鼠标悬停在某个属性的值上 `content` 以查看该值的非转义版本。</span><span class="sxs-lookup"><span data-stu-id="d4a48-240">Hover over the value of a `content` property to see the unescaped version of the value.</span></span>  

<span data-ttu-id="d4a48-241">例如，在此 [演示][CSSContentDemo] 中，当你检查 `p::after` 伪元素时，在 "样式" 窗格中看到转义的字符串：</span><span class="sxs-lookup"><span data-stu-id="d4a48-241">For example, in this [demo][CSSContentDemo] when you inspect the `p::after` pseudo-element you see an escaped string in the Styles pane:</span></span>  

> ##### <span data-ttu-id="d4a48-242">图 16</span><span class="sxs-lookup"><span data-stu-id="d4a48-242">Figure 16</span></span>  
> <span data-ttu-id="d4a48-243">转义字符串</span><span class="sxs-lookup"><span data-stu-id="d4a48-243">The escaped string</span></span>  
> ![转义字符串][ImageEscapedString]  

<span data-ttu-id="d4a48-245">将鼠标悬停在值上时 `content` ，将看到非转义值：</span><span class="sxs-lookup"><span data-stu-id="d4a48-245">When you hover over the `content` value you see the unescaped value:</span></span>  

> ##### <span data-ttu-id="d4a48-246">图 17</span><span class="sxs-lookup"><span data-stu-id="d4a48-246">Figure 17</span></span>  
> <span data-ttu-id="d4a48-247">非转义值</span><span class="sxs-lookup"><span data-stu-id="d4a48-247">The unescaped value</span></span>  
> ![非转义值][ImageUnescapedString]  

### <span data-ttu-id="d4a48-249">控制台中的更多详细源地图错误</span><span class="sxs-lookup"><span data-stu-id="d4a48-249">More detailed source map errors in the Console</span></span>  

<span data-ttu-id="d4a48-250">该控制台现在提供了有关为何无法加载或分析源映射的详细信息。</span><span class="sxs-lookup"><span data-stu-id="d4a48-250">The Console now provides more detail on why a source map failed to load or parse.</span></span>  <span data-ttu-id="d4a48-251">以前它只是在未解释出错的情况下提供了错误。</span><span class="sxs-lookup"><span data-stu-id="d4a48-251">Previously it just provided an error without explaining what went wrong.</span></span>  

> ##### <span data-ttu-id="d4a48-252">图18</span><span class="sxs-lookup"><span data-stu-id="d4a48-252">Figure 18</span></span>  
> <span data-ttu-id="d4a48-253">控制台中的源映射加载错误</span><span class="sxs-lookup"><span data-stu-id="d4a48-253">A source map loading error in the Console</span></span>  
> ![控制台中的源映射加载错误][ImageSourcemapError]  

### <span data-ttu-id="d4a48-255">用于禁用超过文件末尾的滚动的设置</span><span class="sxs-lookup"><span data-stu-id="d4a48-255">Setting for disabling scrolling past the end of a file</span></span>  

<span data-ttu-id="d4a48-256">打开 "[设置][Settings]"，然后禁用**首选项**  >  **源**  >  **允许滚动浏览文件末尾**，以禁用在 "**源**" 面板中滚动浏览文件末尾更好的默认 UI 行为。</span><span class="sxs-lookup"><span data-stu-id="d4a48-256">Open [Settings][Settings] and then disable **Preferences** > **Sources** > **Allow scrolling past end of file** to disable the default UI behavior that allows you to scroll well past the end of a file in the **Sources** panel.</span></span>  

> ##### <span data-ttu-id="d4a48-257">图19</span><span class="sxs-lookup"><span data-stu-id="d4a48-257">Figure 19</span></span>  
> <span data-ttu-id="d4a48-258">在 "设置" 中禁用 " **允许滚动超过文件结尾** "</span><span class="sxs-lookup"><span data-stu-id="d4a48-258">Disabling **Allow scrolling past end of file** in Settings</span></span>  
> ![禁用 "允许滚动超过文件结尾"][ImageSettings]  

> ##### <span data-ttu-id="d4a48-260">图20</span><span class="sxs-lookup"><span data-stu-id="d4a48-260">Figure 20</span></span>  
> <span data-ttu-id="d4a48-261">现在，在 "源" 面板中已禁用滚动超过文件末尾的功能</span><span class="sxs-lookup"><span data-stu-id="d4a48-261">Scrolling past the end of a file is now disabled in the Sources panel</span></span>  
> ![现在，在 "源" 面板中已禁用滚动超过文件末尾的功能][ImageScroll]  

## <span data-ttu-id="d4a48-263">下载 Microsoft Edge 预览频道</span><span class="sxs-lookup"><span data-stu-id="d4a48-263">Download the Microsoft Edge preview channels</span></span>  

<span data-ttu-id="d4a48-264">如果你使用的是 Windows 或 macOS，请考虑使用 [ Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels] 作为默认开发浏览器。</span><span class="sxs-lookup"><span data-stu-id="d4a48-264">If you are on Windows or macOS, consider using the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] as your default development browser.</span></span>  <span data-ttu-id="d4a48-265">预览频道使你能够访问最新的 DevTools 功能。</span><span class="sxs-lookup"><span data-stu-id="d4a48-265">The preview channels give you access to the latest DevTools features.</span></span>  

## <span data-ttu-id="d4a48-266">与 Microsoft Edge DevTools 团队取得联系</span><span class="sxs-lookup"><span data-stu-id="d4a48-266">Getting in touch with Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- <<../../_shared/devtools-feedback.md>>  

<<../../_shared/canary.md>>  

<<../../_shared/discover.md>> -->  

<!-- image links -->  

[ImagePerformanceToolKeyboardReaderImprovements]: ../../images/2020/01/a11y-performance-tool.msft.gif "图1：具有键盘导航和屏幕阅读器的 DevTools 中的性能工具改进"  
[ImageLocalizedGerman]: ../../images/2020/01/localized-devtools.msft.png "图2：德语中的 DevTools"  
[ImageHintsTabWebhintExtension]: ../../images/2020/01/webhint-browser-extension.msft.png "图3：安装 webhint 浏览器扩展时，Microsoft Edge DevTools 中的 "提示" 选项卡"  
[Image3DView]: ../../images/2020/01/3dview.msft.png "图4： Microsoft Edge DevTools 中的3D 视图"  
[ImageElementsVisualStudioCode]: ../../images/2020/01/elements-for-edge.msft.png "图5：使用 Microsoft Edge 扩展元素的 VS 代码中的元素工具"  
[ImageDebuggerExtensionVisualStudioCode]: ../../images/2020/01/vscode-debugger.msft.png "图6： VS 代码中的 Microsoft Edge 扩展调试器"  
[ImageWebhintVisualStudioCodeExtensionWorkspace]: ../../images/2020/01/webhint-vscode-extension.msft.png "图7：分析 VS 代码中的 tsx 文件的 webhint 与代码扩展"  
[ImageVisualStudioLaunchWebApp]: ../../images/2020/01/vs.msft.png "图8：具有在 Microsoft Edge 的 "应用程序"、"开发" 或 "Beta" 中启动 web 应用选项的 Visual Studio"  
[ImageTrackingPrevention]: ../../images/2020/01/tracking-prevention.msft.png "图9：当跟踪阻止阻止跟踪对存储的访问时，在控制台中的消息" 
[ImageMotoG4]: ../../images/2020/01/motog4.msft.png "图10：模拟 Moto G4 视区" 
[ImageMotoG4Frame]: ../../images/2020/01/motog4frame.msft.png "图11：显示 Moto G4 硬件" 
[ImageBlockedCookies]: ../../images/2020/01/blockedcookies.msft.png "图12：在 "应用程序" 面板的 "Cookie" 窗格中阻止的 cookie"
[ImageEditCookie]: ../../images/2020/01/editcookie.msft.png "图13：编辑 cookie 值"
[ImageCopyFetch]: ../../images/2020/01/fetchcookies.msft.png "图14：复制为 Node.js 提取"
[ImageManifestIcon]: ../../images/2020/01/manifesticons.msft.png "图15：清单窗格中的图标"
[ImageEscapedString]: ../../images/2020/01/escapedstring.msft.png "图16：转义字符串"
[ImageUnescapedString]: ../../images/2020/01/unescapedstring.msft.png "图17：非转义值"
[ImageSourcemapError]: ../../images/2020/01/sourcemap.msft.png "图18：控制台中的源映射加载错误"
[ImageSettings]: ../../images/2020/01/settings.msft.png "图19：在 "设置" 中禁用 "允许滚动超过文件结尾""
[ImageScroll]: ../../images/2020/01/scrollingsources.msft.png "图20：已在 "源" 面板中禁用超出文件末尾的滚动"

<!-- links -->  

[DeviceToolbar]: ../../../device-mode/index.md#simulate-a-mobile-viewport "在 Microsoft Edge DevTools 中使用设备模式模拟移动视口"
[DeviceFrame]: ../../../device-mode/index.md#show-device-frame "选择 "显示设备帧" 以显示视区周围的物理设备帧。"
[CommandMenu]: ../../../command-menu/index.md "使用 Microsoft Edge 开发人员工具命令菜单运行命令"  
[ThrottleNetworkAndCpu]: ../../../device-mode/index.md#throttle-the-network-and-cpu "调节网络和 CPU 以更准确地模拟移动用户的 web 浏览条件。"
[crbug924693]: https://crbug.com/924693 "924693：功能请求：将 Moto G4 添加到设备模式列表"
[crbug1030258]: https://crbug.com/1030258 "1030258"
[crbug1026879]: https://crbug.com/1026879 "1026879：开发人员控制台中的 "Cookie" 选项卡不再显示优先级"
[CookiesFields]: ../../../storage/cookies.md#fields "Cookie 表中的字段"
[crbug1029826]: https://crbug.com/1029826 "1029826： "网络" 选项卡-> 右键单击以请求-> 复制 > 复制为 "获取" 不复制 cookie"
[crbug985402]: https://crbug.com/985402 "985402： web app 清单图标错误字符串很混乱"
[CSSContentDemo]: https://mathiasbynens.github.io/css-dbg-stories/css-escapes.html "非转义 CSS 内容的演示"
[Settings]: ../../../customize/index.md#settings "自定义 Microsoft Edge DevTools 设置"
[PostTweetEdgeDevTools]: https://aka.ms/tweet/edgedevtools "@EdgeDevTools | 发布推文"  
[GitHubMicrosoftDocsEdgeDeveloperNewIssue]: https://aka.ms/edgedevtoolsdocs/feedback "新问题 - MicrosoftDocs/edge-developer"  
[TheWebWeWant]: https://aka.ms/webwewant "我们想要的网络"
[MicrosoftEdgePreviewChannels]: https://aka.ms/microsoftedge "Microsoft Edge 预览频道"  
[VisualStudioCodeDebuggerEdgeExtension]: ../../../../visual-studio-code/debugger-for-edge.md "Microsoft Edge 与代码扩展的调试器"  
[VisualStudioCodeElementEdgeExtension]: ../../../../visual-studio-code/elements-for-edge.md "Microsoft Edge 与代码扩展的元素"  
[crbug963183]: https://crbug.com/963183 "963183-DevTools 不符合 WCAG"
[crbug941561]: https://crbug.com/941561 "941561-DevTools 的本地化"
[crbug987787]: https://crbug.com/987787 "987787-Dom 3D 视图"
[AccessibilityInsights]: https://aka.ms/a11yinsights "辅助功能见解"  
[MicrosoftEdgeInsiderAddons]: https://aka.ms/webhint/edge-extension "Microsoft Edge 预览体验计划 Addons"  
[MicrosoftVisualStudio]: ../../../../visual-studio/index.md "Visual Studio"  
[MicrosoftVisualStudioDownloads]: https://aka.ms/vs/download "下载适用于 Windows 的 Visual Studio 2019 & Mac"  
[MDNDocumentObjectModel]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model "文档对象模型 (DOM) |MDN"  
[MDNZIndex]: https://developer.mozilla.org/docs/Web/CSS/z-index "z-索引 |MDN"  
[EdgeDevToolsTwitterAccount]: https://aka.ms/twitter/edgedevtools "@EdgeDevTools Twitter 帐户"
[VisualStudioCode]: https://aka.ms/vscode "Visual Studio 代码"  
[VisualStudioMarketplaceDebuggerEdge]: https://aka.ms/debugger4code "Microsoft Edge 的调试器-Visual Studio Marketplace"  
[VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension]: https://aka.ms/elements4code "Microsoft Edge \ (的元素 \ ) Chromium \-Visual Studio Marketplace"  
[VisualStudioMarketplaceWebhintExtension]: https://aka.ms/webhint4code "webhint-Visual Studio Marketplace"
[Webhint]: https://aka.ms/webhint "webhint"  
[WebhintBrowserExtension]: https://aka.ms/webhint/browser-extension "Webhint 浏览器扩展 |webhint 文档"  
[WebhintVisualStudioCodeExtension]: https://aka.ms/webhint/code-extension "Webhint 与代码扩展 |webhint 文档"  
[TrackingPrevention]: https://aka.ms/microsoftedge/tracking-prevention-blog "改进 Microsoft Edge 博客文章中的跟踪保护"

> [!NOTE]
> <span data-ttu-id="d4a48-323">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="d4a48-323">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="d4a48-324">原始页面位于[此处](https://developers.google.com/web/updates/2020/01/devtools/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="d4a48-324">The original page is found [here](https://developers.google.com/web/updates/2020/01/devtools/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="d4a48-326">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="d4a48-326">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  