---
title: 'Microsoft Edge 81 实开发人员 (工具中的新增) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/17/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 8e9e6885d04c7ad15a688b51cee4c16440d3ca1e
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "10942093"
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

# <span data-ttu-id="66231-103">DevTools （Microsoft Edge 81）中的新增功能</span><span class="sxs-lookup"><span data-stu-id="66231-103">What's New In DevTools (Microsoft Edge 81)</span></span>  

## <span data-ttu-id="66231-104">来自 Microsoft Edge 开发人员工具团队公告</span><span class="sxs-lookup"><span data-stu-id="66231-104">Announcements from the Microsoft Edge DevTools team</span></span>  

<span data-ttu-id="66231-105">以下各部分是你可能错过的 Microsoft Edge 开发人员工具团队的公告列表！</span><span class="sxs-lookup"><span data-stu-id="66231-105">The following sections are a list of announcements you may have missed from the Microsoft Edge DevTools team!</span></span> <span data-ttu-id="66231-106">请查看这些公告，尝试使用 DevTools 和 VS 代码扩展等中的新功能。</span><span class="sxs-lookup"><span data-stu-id="66231-106">Check them out to try new features in the DevTools, VS Code extensions, and more.</span></span>  <span data-ttu-id="66231-107">若要了解有关开发人员工具中的所有最新功能和最强大功能的最新动态，请下载 [Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels]并[在 Twitter 上关注我们][EdgeDevToolsTwitterAccount]。</span><span class="sxs-lookup"><span data-stu-id="66231-107">To stay up to date on all the latest and greatest features in your developer tools, download the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] and [follow us on Twitter][EdgeDevToolsTwitterAccount].</span></span>  

### <span data-ttu-id="66231-108">DevTools 的辅助功能改进</span><span class="sxs-lookup"><span data-stu-id="66231-108">Accessibility improvements to the DevTools</span></span>  

<span data-ttu-id="66231-109">DevTools 团队已对 Chromium 作了 170 更改，以解决 DevTools 中的高影响颜色对比度、键盘和屏幕阅读器问题。</span><span class="sxs-lookup"><span data-stu-id="66231-109">The DevTools team has contributed 170 changes to Chromium to address high-impact color contrast, keyboard, and screen reader issues in the DevTools.</span></span>  <span data-ttu-id="66231-110">构建 Web 的每个开发人员都应该能够使用 DevTools。</span><span class="sxs-lookup"><span data-stu-id="66231-110">Every developer building the web should be able to use the DevTools.</span></span>  

> ##### <span data-ttu-id="66231-111">图 1</span><span class="sxs-lookup"><span data-stu-id="66231-111">Figure 1</span></span>  
> <span data-ttu-id="66231-112">通过键盘导航和屏幕阅读器改进，开发人员工具中的性能工具</span><span class="sxs-lookup"><span data-stu-id="66231-112">The Performance tool in the DevTools with the keyboard navigation and screen reader improvements</span></span>  
> ![通过键盘导航和屏幕阅读器改进，开发人员工具中的性能工具][ImagePerformanceToolKeyboardReaderImprovements]  

<span data-ttu-id="66231-114">希望了解如何使您的网页对所有用户使用？</span><span class="sxs-lookup"><span data-stu-id="66231-114">Want to learn how to make your web page accessible to all of your users?</span></span>  <span data-ttu-id="66231-115">下载 Microsoft Edge [的辅助][AccessibilityInsights] 功能见解和 [WebHint][WebhintBrowserExtension] 扩展以开始使用。</span><span class="sxs-lookup"><span data-stu-id="66231-115">Download the [Accessibility Insights][AccessibilityInsights] and [webhint][WebhintBrowserExtension] extensions for Microsoft Edge to get started.</span></span>  

<span data-ttu-id="66231-116">如果使用屏幕阅读器或键盘在 DevTools 中导航，请通过 [tweett 发送][PostTweetEdgeDevTools] 或单击"发送反馈"图标来向我们 [发送你的反](#getting-in-touch-with-microsoft-edge-devtools-team) 馈！</span><span class="sxs-lookup"><span data-stu-id="66231-116">If you use screen readers or the keyboard to navigate around the DevTools, send us your feedback by [tweeting][PostTweetEdgeDevTools] at us or clicking the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!</span></span>  

<span data-ttu-id="66231-117">Chromium 问题 [#963183][crbug963183]</span><span class="sxs-lookup"><span data-stu-id="66231-117">Chromium issue [#963183][crbug963183]</span></span>  

### <span data-ttu-id="66231-118">使用其他语言的 DevTools</span><span class="sxs-lookup"><span data-stu-id="66231-118">Using the DevTools in other languages</span></span>  

<span data-ttu-id="66231-119">许多开发人员将使用 StackOverflow 和 VS 代码等其他开发人员工具，不只是使用英语。</span><span class="sxs-lookup"><span data-stu-id="66231-119">Many developers use other developer tools, like StackOverflow and VS Code, in their native language, not just in English.</span></span>  <span data-ttu-id="66231-120">我们很高为将公布发布的 DevTools 的本地化，你现在可以使用除英语之外的 10 种语言之一：</span><span class="sxs-lookup"><span data-stu-id="66231-120">We’re excited to announce localization for the DevTools, which you are now able to use in one of 10 languages besides English:</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="66231-121">简体\)  (- &#20013;&#25991;&#65288;&#31616;&#20307;&#65289;</span><span class="sxs-lookup"><span data-stu-id="66231-121">Chinese \(Simplified\) - &#20013;&#25991;&#65288;&#31616;&#20307;&#65289;</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="66231-122">中文 \ (Traditional\) - &#20013;&#25991;&#65288;&#32321;&#39636;&#65289;</span><span class="sxs-lookup"><span data-stu-id="66231-122">Chinese \(Traditional\) - &#20013;&#25991;&#65288;&#32321;&#39636;&#65289;</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      <span data-ttu-id="66231-123">法语 – 法国 - 法&#231;出</span><span class="sxs-lookup"><span data-stu-id="66231-123">French – fran&#231;ais</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="66231-124">German - desch</span><span class="sxs-lookup"><span data-stu-id="66231-124">German - deutsch</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      <span data-ttu-id="66231-125">意大利语 - 意大利语</span><span class="sxs-lookup"><span data-stu-id="66231-125">Italian - italiano</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="66231-126">日语 -  &#26085;&#26412;&#35486;</span><span class="sxs-lookup"><span data-stu-id="66231-126">Japanese - &#26085;&#26412;&#35486;</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      <span data-ttu-id="66231-127">当理 -  &#54620;&#44397;&#50612;</span><span class="sxs-lookup"><span data-stu-id="66231-127">Korean - &#54620;&#44397;&#50612;</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="66231-128">葡葡葡图 -&#234;葡表</span><span class="sxs-lookup"><span data-stu-id="66231-128">Portuguese - portugu&#234;s</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      <span data-ttu-id="66231-129">俄语 –  &#1088;&#1091;&#1089;&#1089;&#1082;&#1080;&#1081;</span><span class="sxs-lookup"><span data-stu-id="66231-129">Russian – &#1088;&#1091;&#1089;&#1089;&#1082;&#1080;&#1081;</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="66231-130">西班牙语 - espa 通&#241;旧</span><span class="sxs-lookup"><span data-stu-id="66231-130">Spanish - espa&#241;ol</span></span>
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

<span data-ttu-id="66231-131">DevTools 将自动匹配 Microsoft Edge 的语言 `edge://settings/languages` 。</span><span class="sxs-lookup"><span data-stu-id="66231-131">The DevTools automatically match the language you use for Microsoft Edge in `edge://settings/languages`.</span></span>  

<span data-ttu-id="66231-132">如果你希望 Microsoft Edge 使用一种语言，而你的 DevTools 仍使用英语，请按 `F1` DevTools 打开"设置 ["][Settings] 并禁用 **匹配浏览器语言**。</span><span class="sxs-lookup"><span data-stu-id="66231-132">If you want Microsoft Edge to be in one language and your DevTools to remain in English, press `F1` in the DevTools to open [Settings][Settings] and disable **Match browser language**.</span></span>  

> ##### <span data-ttu-id="66231-133">图 2</span><span class="sxs-lookup"><span data-stu-id="66231-133">Figure 2</span></span>  
> <span data-ttu-id="66231-134">常规工具</span><span class="sxs-lookup"><span data-stu-id="66231-134">The DevTools in German</span></span>  
> ![常规工具][ImageLocalizedGerman]  

<span data-ttu-id="66231-136">**主机消息** 未进行本地化。</span><span class="sxs-lookup"><span data-stu-id="66231-136">**Console** messages are not localized.</span></span>  <span data-ttu-id="66231-137">在 DevTools UI 中使用的字符串仅以用于 Microsoft Edge 的语言显示。</span><span class="sxs-lookup"><span data-stu-id="66231-137">Only the strings used in the DevTools UI are displayed in the language you use for Microsoft Edge.</span></span>  

<span data-ttu-id="66231-138">如果要使用不同于可用语言的 DevTools， [请向我们提供推][PostTweetEdgeDevTools] 送或单击"发送反馈 ["](#getting-in-touch-with-microsoft-edge-devtools-team) 图标。</span><span class="sxs-lookup"><span data-stu-id="66231-138">If you want to use the DevTools in a different language than the ones that are available, [tweet][PostTweetEdgeDevTools] at us or click the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon.</span></span>  

<span data-ttu-id="66231-139">Chromium [问题#941561][crbug941561]</span><span class="sxs-lookup"><span data-stu-id="66231-139">Chromium issue [#941561][crbug941561]</span></span>  

### <span data-ttu-id="66231-140">Webhint Microsoft Edge 扩展</span><span class="sxs-lookup"><span data-stu-id="66231-140">webhint Microsoft Edge extension</span></span>  

<span data-ttu-id="66231-141">通过 Webhint Microsoft Edge 扩展，可轻松浏览网页，并在 DevTools 中轻松浏览网页，并获取关于辅助功能、浏览器兼容性、安全性、性能等的反馈。</span><span class="sxs-lookup"><span data-stu-id="66231-141">The webhint Microsoft Edge extension allows you to easily scan your web page and get feedback on accessibility, browser compatibility, security, performance, and more within the DevTools.</span></span>  <span data-ttu-id="66231-142">阅读更多信息 [https://webhint.io][Webhint] 。</span><span class="sxs-lookup"><span data-stu-id="66231-142">Read more at [https://webhint.io][Webhint].</span></span>  

> ##### <span data-ttu-id="66231-143">图 3</span><span class="sxs-lookup"><span data-stu-id="66231-143">Figure 3</span></span>  
> <span data-ttu-id="66231-144">安装了 Webhint 浏览器扩展时 DevTools 中的"提示"选项卡</span><span class="sxs-lookup"><span data-stu-id="66231-144">The Hints tab in the DevTools when the webhint browser extension is installed</span></span>  
> ![安装了 Webhint 浏览器扩展时 DevTools 中的"提示"选项卡][ImageHintsTabWebhintExtension]  

<span data-ttu-id="66231-146">[试用 Microsoft Edge 中的 Webhint 浏览器扩展][MicrosoftEdgeInsiderAddons]。</span><span class="sxs-lookup"><span data-stu-id="66231-146">[Try the webhint browser extension in Microsoft Edge][MicrosoftEdgeInsiderAddons].</span></span>  <span data-ttu-id="66231-147">安装扩展后，打开 DevTools，然后选择"提示"选项卡。 在此处，运行可自定义网站扫描。</span><span class="sxs-lookup"><span data-stu-id="66231-147">Once you install the extension, open the DevTools and select the Hints tab.  From here, run a customizable site scan.</span></span>  <span data-ttu-id="66231-148">要了解详细信息 [，请转到][WebhintBrowserExtension] webhint.io。</span><span class="sxs-lookup"><span data-stu-id="66231-148">Head over to [webhint.io][WebhintBrowserExtension] to learn more.</span></span>  

### <span data-ttu-id="66231-149">3D 视图</span><span class="sxs-lookup"><span data-stu-id="66231-149">3D View</span></span>  

<span data-ttu-id="66231-150">通过 **在文档对象模型** [\ (DOM\) ][MDNDocumentObjectModel] 或 [z 索][MDNZIndex] 引堆叠上下文中导航，使用 3D 视图调试你的 Web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="66231-150">Use the **3D View** to debug your web application by navigating through the [Document Object Model \(DOM\)][MDNDocumentObjectModel] or the [z-index][MDNZIndex] stacking context.</span></span>  

> ##### <span data-ttu-id="66231-151">图 4</span><span class="sxs-lookup"><span data-stu-id="66231-151">Figure 4</span></span>  
> <span data-ttu-id="66231-152">DevTools 中的 3D 视图</span><span class="sxs-lookup"><span data-stu-id="66231-152">The 3D View in the DevTools</span></span>  
> ![DevTools 中的 3D 视图][Image3DView]  

<span data-ttu-id="66231-154">若要访问 3D 视图，在 `Ctrl`  +  `Shift`  +  `P` 3D 视图中**键入内容，** 然后选择"**显示 3D 视图**"。</span><span class="sxs-lookup"><span data-stu-id="66231-154">To access the 3D View, press `Ctrl` + `Shift` + `P`, type in **3D View** and select **Show 3D View**.</span></span>  

<span data-ttu-id="66231-155">我们正在处理 UI 并向 3D 视图添加更多功能，因此请向我们发送你的 [反馈](#getting-in-touch-with-microsoft-edge-devtools-team)。</span><span class="sxs-lookup"><span data-stu-id="66231-155">We're working on the UI and adding more functionality to the 3D View, so please send us your [feedback](#getting-in-touch-with-microsoft-edge-devtools-team).</span></span>  

<span data-ttu-id="66231-156">Chromium [问题#987787][crbug987787]</span><span class="sxs-lookup"><span data-stu-id="66231-156">Chromium issue [#987787][crbug987787]</span></span>  

### <span data-ttu-id="66231-157">Visual Studio代码扩展</span><span class="sxs-lookup"><span data-stu-id="66231-157">Visual Studio Code extensions</span></span>  

<span data-ttu-id="66231-158">DevTools 团队还发布了 [用于 Visual Studio Code \ (VS Code\) ][VisualStudioCode] 的一些扩展，它允许你直接从文本编辑器使用 DevTools 的功能！</span><span class="sxs-lookup"><span data-stu-id="66231-158">The DevTools team has also released some extensions for [Visual Studio Code \(VS Code\)][VisualStudioCode] that let you use the power of the DevTools directly from your text editor!</span></span> <span data-ttu-id="66231-159">请参阅以下扩展项：</span><span class="sxs-lookup"><span data-stu-id="66231-159">Check out the extensions below:</span></span>  

#### <span data-ttu-id="66231-160">Microsoft Edge 的元素</span><span class="sxs-lookup"><span data-stu-id="66231-160">Elements for Microsoft Edge</span></span>  

<span data-ttu-id="66231-161">通过将 [Microsoft Edge \ (m Chromium\) 按钮扩展添加到的元素，从 VS ][VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension] 代码内使用元素工具。</span><span class="sxs-lookup"><span data-stu-id="66231-161">Use the Elements tool from within VS Code by adding the [Elements for Microsoft Edge \(Chromium\)][VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension] VS Code extension.</span></span>  

> ##### <span data-ttu-id="66231-162">图 5</span><span class="sxs-lookup"><span data-stu-id="66231-162">Figure 5</span></span>  
> <span data-ttu-id="66231-163">VS 代码中的元素工具，使用适用于 Microsoft Edge 扩展的 ![ VS 代码中的元素扩展"元素"工具][ImageElementsVisualStudioCode]</span><span class="sxs-lookup"><span data-stu-id="66231-163">The Elements tool in VS Code using the Elements for Microsoft Edge extension ![The Elements tool in VS Code using the Elements for Microsoft Edge extension][ImageElementsVisualStudioCode]</span></span>  

<span data-ttu-id="66231-164">有关详细信息，请查目[Microsoft Edge 中的元素与代码扩展。][VisualStudioCodeElementEdgeExtension]</span><span class="sxs-lookup"><span data-stu-id="66231-164">For more information, check out [Elements for Microsoft Edge VS Code extension][VisualStudioCodeElementEdgeExtension].</span></span>  

#### <span data-ttu-id="66231-165">Microsoft Edge 调试程序</span><span class="sxs-lookup"><span data-stu-id="66231-165">Debugger for Microsoft Edge</span></span>  

<span data-ttu-id="66231-166">借助 Microsoft Edge 的 [调试程序][VisualStudioMarketplaceDebuggerEdge] ，直接从 VS 代码在 Microsoft Edge 中运行的 JavaScript！</span><span class="sxs-lookup"><span data-stu-id="66231-166">With the [Debugger for Microsoft Edge][VisualStudioMarketplaceDebuggerEdge] VS Code extension, debug JavaScript running in Microsoft Edge directly from VS Code!</span></span>  

> ##### <span data-ttu-id="66231-167">图 6</span><span class="sxs-lookup"><span data-stu-id="66231-167">Figure 6</span></span>  
> <span data-ttu-id="66231-168">VS 代码中的 Microsoft Edge 扩展程序</span><span class="sxs-lookup"><span data-stu-id="66231-168">The Debugger for Microsoft Edge Extension in VS Code</span></span>  
> ![VS 代码中的 Microsoft Edge 扩展程序][ImageDebuggerExtensionVisualStudioCode]  

<span data-ttu-id="66231-170">有关详细信息，请了解如何从[VS 代码调试 Microsoft Edge。][VisualStudioCodeDebuggerEdgeExtension]</span><span class="sxs-lookup"><span data-stu-id="66231-170">For more information, check out [how to debug Microsoft Edge from VS Code][VisualStudioCodeDebuggerEdgeExtension].</span></span>  

#### <span data-ttu-id="66231-171">webhint</span><span class="sxs-lookup"><span data-stu-id="66231-171">webhint</span></span>  

<span data-ttu-id="66231-172">[Webhint][VisualStudioMarketplaceWebhintExtension] VS 代码扩展在你编写 `webhint` 时使用它改进网页！</span><span class="sxs-lookup"><span data-stu-id="66231-172">The [webhint][VisualStudioMarketplaceWebhintExtension] VS Code extension uses `webhint` to improve your web page while you're writing it!</span></span> <span data-ttu-id="66231-173">此扩展基于分析在工作区文件上运行和 `webhint` 报告诊断。</span><span class="sxs-lookup"><span data-stu-id="66231-173">This extension runs and reports diagnostics on your workspace files based on `webhint` analysis.</span></span>  

> ##### <span data-ttu-id="66231-174">图 7</span><span class="sxs-lookup"><span data-stu-id="66231-174">Figure 7</span></span>  
> <span data-ttu-id="66231-175">Webhint VS 代码扩展分析 VS 代码中的 .tsx 文件</span><span class="sxs-lookup"><span data-stu-id="66231-175">The webhint VS Code extension analyzing a .tsx file in VS Code</span></span>  
> ![Webhint VS 代码扩展分析 VS 代码中的 .tsx 文件][ImageWebhintVisualStudioCodeExtensionWorkspace]  

<span data-ttu-id="66231-177">[了解有关 VS 代码 Webhint 扩展的详细信息][WebhintVisualStudioCodeExtension]。</span><span class="sxs-lookup"><span data-stu-id="66231-177">[Learn more about the VS Code webhint extension][WebhintVisualStudioCodeExtension].</span></span>  

### <span data-ttu-id="66231-178">Visual Studio集成</span><span class="sxs-lookup"><span data-stu-id="66231-178">Visual Studio integration</span></span>  

<span data-ttu-id="66231-179">在 Visual Studio 2019 版本 16.2 或更高版本中，Visual Studio 使用调试器调试在 Microsoft Edge 中运行的 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="66231-179">In Visual Studio 2019 version 16.2 or later, use the Visual Studio debugger to debug JavaScript running in Microsoft Edge.</span></span>  <span data-ttu-id="66231-180">[请Visual Studio 2019，][MicrosoftVisualStudioDownloads] 试用此功能！</span><span class="sxs-lookup"><span data-stu-id="66231-180">[Download Visual Studio 2019][MicrosoftVisualStudioDownloads] to try this feature out!</span></span>  

> ##### <span data-ttu-id="66231-181">图 8</span><span class="sxs-lookup"><span data-stu-id="66231-181">Figure 8</span></span>  
> <span data-ttu-id="66231-182">Visual Studio在 Microsoft Edge Canary、Dev 或 Beta 中启动你的 Web 应用"的选项</span><span class="sxs-lookup"><span data-stu-id="66231-182">Visual Studio with the option to launch your web app in Microsoft Edge Canary, Dev, or Beta</span></span>  
> ![Visual Studio在 Microsoft Edge Canary、Dev 或 Beta 中启动你的 Web 应用"的选项][ImageVisualStudioLaunchWebApp]  

<span data-ttu-id="66231-184">[了解有关如何从中调试 Microsoft Edge 表Visual Studio。][MicrosoftVisualStudio]</span><span class="sxs-lookup"><span data-stu-id="66231-184">[Learn more about debugging Microsoft Edge from Visual Studio][MicrosoftVisualStudio].</span></span>  

### <span data-ttu-id="66231-185">跟踪防护主机消息</span><span class="sxs-lookup"><span data-stu-id="66231-185">Tracking prevention Console messages</span></span>  

<span data-ttu-id="66231-186">跟踪防护是 Microsoft Edge 中唯一的功能，可防止你被之前尚未访问过的网站进行跟踪。</span><span class="sxs-lookup"><span data-stu-id="66231-186">Tracking prevention is a unique feature in Microsoft Edge that protects you from being tracked by websites you haven't visited before.</span></span>  <span data-ttu-id="66231-187">默认跟踪防护设置是"平衡模式"，为了使体验保持平衡隐私和 Web 兼容性的体验，这将对第三方跟踪程序和已知的义务跟踪器进行保护。</span><span class="sxs-lookup"><span data-stu-id="66231-187">The default tracking prevention setting is Balanced mode, which blocks 3rd party trackers and known malicious trackers for an experience that balances privacy and web compatibility.</span></span>  <span data-ttu-id="66231-188">为了在特定跟踪器被阻止时，为更深入地了解网页的兼容性，我们还在跟踪器被阻止时在主机中添加了警告邮件。</span><span class="sxs-lookup"><span data-stu-id="66231-188">To give you more insight into the compatibility of your web page when certain trackers are blocked, we've also added warning messages in the Console when a tracker is blocked.</span></span>  

> ##### <span data-ttu-id="66231-189">图 9</span><span class="sxs-lookup"><span data-stu-id="66231-189">Figure 9</span></span>  
> <span data-ttu-id="66231-190">跟踪防护阻止对跟踪器的存储的访问时主机中的消息</span><span class="sxs-lookup"><span data-stu-id="66231-190">Messages in the Console when tracking prevention blocks access to storage for a tracker</span></span>  
> ![跟踪防护阻止对跟踪器的存储的访问时主机中的消息][ImageTrackingPrevention]  

<span data-ttu-id="66231-192">[了解有关跟踪防护和在隐私和 Web 之间余额之间余额的详细信息][TrackingPrevention]。</span><span class="sxs-lookup"><span data-stu-id="66231-192">[Read more about tracking prevention and the balance between privacy and web compatibility][TrackingPrevention].</span></span>  

## <span data-ttu-id="66231-193">来自 Chromium 项目的公告</span><span class="sxs-lookup"><span data-stu-id="66231-193">Announcements from the Chromium project</span></span>  

<span data-ttu-id="66231-194">以下部分公布给开源 Chromium 项目的 Microsoft Edge 81 中可用的其他功能。</span><span class="sxs-lookup"><span data-stu-id="66231-194">The following sections announce additional features available in Microsoft Edge 81 that were contributed to the open source Chromium project.</span></span>  

### <span data-ttu-id="66231-195">设备模式下支持</span><span class="sxs-lookup"><span data-stu-id="66231-195">Moto G4 support in Device Mode</span></span>  

<span data-ttu-id="66231-196">[启用设备工具栏后][DeviceToolbar]，请从"设备"列表中模拟马达 G4 视区**的**大小。</span><span class="sxs-lookup"><span data-stu-id="66231-196">After [enabling the Device Toolbar][DeviceToolbar], simulate the dimensions of a Moto G4 viewport from the **Device** list.</span></span>  

> ##### <span data-ttu-id="66231-197">图 10</span><span class="sxs-lookup"><span data-stu-id="66231-197">Figure 10</span></span>  
> <span data-ttu-id="66231-198">模拟 Moto G4 视区</span><span class="sxs-lookup"><span data-stu-id="66231-198">Simulating a Moto G4 viewport</span></span>  
> ![模拟 Moto G4 视区][ImageMotoG4]  

<span data-ttu-id="66231-200">单击 ["显示设备][DeviceFrame] 框架"以在视区的 Moto G4 硬件中显示 Moto G4 硬件。</span><span class="sxs-lookup"><span data-stu-id="66231-200">Click [Show Device Frame][DeviceFrame] to show the Moto G4 hardware around the viewport.</span></span>  

> ##### <span data-ttu-id="66231-201">图 11</span><span class="sxs-lookup"><span data-stu-id="66231-201">Figure 11</span></span>  
> <span data-ttu-id="66231-202">显示 Moto G4 硬件</span><span class="sxs-lookup"><span data-stu-id="66231-202">Showing the Moto G4 hardware</span></span>  
> ![显示 Moto G4 硬件][ImageMotoG4Frame]  

<span data-ttu-id="66231-204">相关功能：</span><span class="sxs-lookup"><span data-stu-id="66231-204">Related features:</span></span>  

*   <span data-ttu-id="66231-205">打开 ["命令"][CommandMenu] 菜单并 `Capture screenshot` 运行命令以获取视区的屏幕截图，该视区包括 Moto G4 (在启用 **"显示**) 。</span><span class="sxs-lookup"><span data-stu-id="66231-205">Open the [Command Menu][CommandMenu] and run the `Capture screenshot` command to take a screenshot of the viewport that includes the Moto G4 hardware (after enabling **Show Device Frame**).</span></span>  
*   <span data-ttu-id="66231-206">[将网络和 CPU 恢复][ThrottleNetworkAndCpu] 为更准确地模拟移动用户的 Web 浏览条件。</span><span class="sxs-lookup"><span data-stu-id="66231-206">[Throttle the network and CPU][ThrottleNetworkAndCpu] to more accurately simulate a mobile user's web browsing conditions.</span></span>  

<span data-ttu-id="66231-207">Chromium [问题#924693][crbug924693]</span><span class="sxs-lookup"><span data-stu-id="66231-207">Chromium issue [#924693][crbug924693]</span></span>  

### <span data-ttu-id="66231-208">Cookie 相关的更新</span><span class="sxs-lookup"><span data-stu-id="66231-208">Cookie-related updates</span></span>  

#### <span data-ttu-id="66231-209">在 Cookie 窗格中阻止 Cookie</span><span class="sxs-lookup"><span data-stu-id="66231-209">Blocked cookies in the Cookies pane</span></span>  

<span data-ttu-id="66231-210">应用程序面板中的 Cookie 窗格现在显示了带有黄色背景的 Cookie。</span><span class="sxs-lookup"><span data-stu-id="66231-210">The Cookies pane in the Application panel now displays blocked cookies with a yellow background.</span></span>  

> ##### <span data-ttu-id="66231-211">图 12</span><span class="sxs-lookup"><span data-stu-id="66231-211">Figure 12</span></span>  
> <span data-ttu-id="66231-212">在应用程序面板的 Cookie 窗格中阻止 Cookie</span><span class="sxs-lookup"><span data-stu-id="66231-212">Blocked cookies in the Cookies pane of the Application panel</span></span>  
> ![在应用程序面板的 Cookie 窗格中阻止 Cookie][ImageBlockedCookies]  

<span data-ttu-id="66231-214">Chromium [问题#1030258][crbug|::ref1::|]</span><span class="sxs-lookup"><span data-stu-id="66231-214">Chromium issue [#1030258][crbug|::ref1::|]</span></span>  

#### <span data-ttu-id="66231-215">Cookie 窗格中的 Cookie 优先级</span><span class="sxs-lookup"><span data-stu-id="66231-215">Cookie priority in the Cookie pane</span></span>  

<span data-ttu-id="66231-216">网络和应用程序面板中的 Cookie 表现包含" **优先级"** 列。</span><span class="sxs-lookup"><span data-stu-id="66231-216">The Cookies tables in the Network and Application panels now include a **Priority** column.</span></span>  

> [!CAUTION]
> <span data-ttu-id="66231-217">基于 Chromium 的浏览器（如 Microsoft Edge）是唯一支持 Cookie 优先级的浏览器。</span><span class="sxs-lookup"><span data-stu-id="66231-217">Chromium-based browsers, like Microsoft Edge, are the only browsers that support cookie priority.</span></span>  

<span data-ttu-id="66231-218">Chromium [#1026879][crbug1026879]</span><span class="sxs-lookup"><span data-stu-id="66231-218">Chromium issue [#1026879][crbug1026879]</span></span>  

#### <span data-ttu-id="66231-219">编辑所有 Cookie 值</span><span class="sxs-lookup"><span data-stu-id="66231-219">Edit all cookie values</span></span>  

<span data-ttu-id="66231-220">Cookie 表中的所有单元格现在都可编辑，"大小 **"列中的** 单元格除外，因为该列表示 Cookie 的网络大小（字节）。</span><span class="sxs-lookup"><span data-stu-id="66231-220">All cells in the Cookie tables are editable now, except cells in the **Size** column because that column represents the network size of the cookie, in bytes.</span></span>  <span data-ttu-id="66231-221">请参阅 [字段][CookiesFields] ，获取每列的说明。</span><span class="sxs-lookup"><span data-stu-id="66231-221">See [Fields][CookiesFields] for an explanation of each column.</span></span>  

> ##### <span data-ttu-id="66231-222">图 13</span><span class="sxs-lookup"><span data-stu-id="66231-222">Figure 13</span></span>  
> <span data-ttu-id="66231-223">编辑 Cookie 值</span><span class="sxs-lookup"><span data-stu-id="66231-223">Editing a cookie value</span></span>  
> ![编辑 Cookie 值][ImageEditCookie]  

#### <span data-ttu-id="66231-225">以网站Node.js复制以包括 Cookie 数据</span><span class="sxs-lookup"><span data-stu-id="66231-225">Copy as Node.js fetch to include cookie data</span></span>  

<span data-ttu-id="66231-226">右键单击网络请求并选择**Copy**  >  **"复制副本"作为 Node.js提**，以获取 `fetch` 包括 Cookie 数据的表达式。</span><span class="sxs-lookup"><span data-stu-id="66231-226">Right-click a network request and select **Copy** > **Copy as Node.js fetch** to get a `fetch` expression that includes cookie data.</span></span>  

> ##### <span data-ttu-id="66231-227">图 14</span><span class="sxs-lookup"><span data-stu-id="66231-227">Figure 14</span></span>  
> <span data-ttu-id="66231-228">以提Node.js复制</span><span class="sxs-lookup"><span data-stu-id="66231-228">Copy as Node.js fetch</span></span>  
> ![以提Node.js复制][ImageCopyFetch]  

<span data-ttu-id="66231-230">Chromium [问题#1029826][crbug1029826]</span><span class="sxs-lookup"><span data-stu-id="66231-230">Chromium issue [#1029826][crbug1029826]</span></span>  

### <span data-ttu-id="66231-231">更多准确的 Web 应用清单图标</span><span class="sxs-lookup"><span data-stu-id="66231-231">More accurate web app manifest icons</span></span>  

<span data-ttu-id="66231-232">以前，应用程序面板中的清单窗格为了显示 Web 应用清单图标而发送了自己的请求。</span><span class="sxs-lookup"><span data-stu-id="66231-232">Previously, the Manifest pane in the Application panel sent its own requests in order to display web app manifest icons.</span></span>  <span data-ttu-id="66231-233">开发工具现在显示 Microsoft Edge 使用的确实清单图标。</span><span class="sxs-lookup"><span data-stu-id="66231-233">DevTools now shows the exact same manifest icon that Microsoft Edge uses.</span></span>  

> ##### <span data-ttu-id="66231-234">图 15</span><span class="sxs-lookup"><span data-stu-id="66231-234">Figure 15</span></span>  
> <span data-ttu-id="66231-235">清单窗格中的图标</span><span class="sxs-lookup"><span data-stu-id="66231-235">Icons in the Manifest pane</span></span>  
> ![清单窗格中的图标][ImageManifestIcon]  

<span data-ttu-id="66231-237">Chromium [问题#985402][crbug985402]</span><span class="sxs-lookup"><span data-stu-id="66231-237">Chromium issue [#985402][crbug985402]</span></span>  

### <span data-ttu-id="66231-238">将鼠标指悬停在 CSS 内容属性上可查看未捕获的值</span><span class="sxs-lookup"><span data-stu-id="66231-238">Hover over CSS content properties to see unescaped values</span></span>  

<span data-ttu-id="66231-239">将鼠标悬停在 `content` 属性值上以查看未被接受的值版本。</span><span class="sxs-lookup"><span data-stu-id="66231-239">Hover over the value of a `content` property to see the unescaped version of the value.</span></span>  

<span data-ttu-id="66231-240">例如，当你 [检查][CSSContentDemo] `p::after` pseudo-element 时，可以在"样式"窗格中看到转义字符串：</span><span class="sxs-lookup"><span data-stu-id="66231-240">For example, in this [demo][CSSContentDemo] when you inspect the `p::after` pseudo-element you see an escaped string in the Styles pane:</span></span>  

> ##### <span data-ttu-id="66231-241">图 16</span><span class="sxs-lookup"><span data-stu-id="66231-241">Figure 16</span></span>  
> <span data-ttu-id="66231-242">已转换的字符串</span><span class="sxs-lookup"><span data-stu-id="66231-242">The escaped string</span></span>  
> ![已转换的字符串][ImageEscapedString]  

<span data-ttu-id="66231-244">将鼠标悬停 `content` 在您看到一个未使用的值上时：</span><span class="sxs-lookup"><span data-stu-id="66231-244">When you hover over the `content` value you see the unescaped value:</span></span>  

> ##### <span data-ttu-id="66231-245">图 17</span><span class="sxs-lookup"><span data-stu-id="66231-245">Figure 17</span></span>  
> <span data-ttu-id="66231-246">未入的值</span><span class="sxs-lookup"><span data-stu-id="66231-246">The unescaped value</span></span>  
> ![未入的值][ImageUnescapedString]  

### <span data-ttu-id="66231-248">在主机中更详细的源映射错误</span><span class="sxs-lookup"><span data-stu-id="66231-248">More detailed source map errors in the Console</span></span>  

<span data-ttu-id="66231-249">该控制台现在提供了有关源映射加载或分析失败的原因的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="66231-249">The Console now provides more detail on why a source map failed to load or parse.</span></span>  <span data-ttu-id="66231-250">之前，它只提供了一个错误但不解解问题出现的问题。</span><span class="sxs-lookup"><span data-stu-id="66231-250">Previously it just provided an error without explaining what went wrong.</span></span>  

> ##### <span data-ttu-id="66231-251">图 18</span><span class="sxs-lookup"><span data-stu-id="66231-251">Figure 18</span></span>  
> <span data-ttu-id="66231-252">主机中的源映射加载错误</span><span class="sxs-lookup"><span data-stu-id="66231-252">A source map loading error in the Console</span></span>  
> ![主机中的源映射加载错误][ImageSourcemapError]  

### <span data-ttu-id="66231-254">用于禁用滚动的设置，将趋移文件末尾</span><span class="sxs-lookup"><span data-stu-id="66231-254">Setting for disabling scrolling past the end of a file</span></span>  

<span data-ttu-id="66231-255">打开["设置][Settings]**"，然后禁用**  >  **"首**  >  **选项源"，允许以前结**束文件的一项时间，禁止你在源面板中很好地**滚**动文件的末尾。</span><span class="sxs-lookup"><span data-stu-id="66231-255">Open [Settings][Settings] and then disable **Preferences** > **Sources** > **Allow scrolling past end of file** to disable the default UI behavior that allows you to scroll well past the end of a file in the **Sources** panel.</span></span>  

> ##### <span data-ttu-id="66231-256">图 19</span><span class="sxs-lookup"><span data-stu-id="66231-256">Figure 19</span></span>  
> <span data-ttu-id="66231-257">禁用"设置"**中文件的"允许滚动即将结束"**</span><span class="sxs-lookup"><span data-stu-id="66231-257">Disabling **Allow scrolling past end of file** in Settings</span></span>  
> ![禁用"允许滚动"文件的终止][ImageSettings]  

> ##### <span data-ttu-id="66231-259">图 20</span><span class="sxs-lookup"><span data-stu-id="66231-259">Figure 20</span></span>  
> <span data-ttu-id="66231-260">源面板中现已禁用通过文件的末尾滚动</span><span class="sxs-lookup"><span data-stu-id="66231-260">Scrolling past the end of a file is now disabled in the Sources panel</span></span>  
> ![源面板中现已禁用通过文件的末尾滚动][ImageScroll]  

## <span data-ttu-id="66231-262">下载 Microsoft Edge 预览频道</span><span class="sxs-lookup"><span data-stu-id="66231-262">Download the Microsoft Edge preview channels</span></span>  

<span data-ttu-id="66231-263">如果你使用的是 Windows 或 macOS，请考虑使用 [ Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels] 作为默认开发浏览器。</span><span class="sxs-lookup"><span data-stu-id="66231-263">If you are on Windows or macOS, consider using the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] as your default development browser.</span></span>  <span data-ttu-id="66231-264">预览频道使你能够访问最新的 DevTools 功能。</span><span class="sxs-lookup"><span data-stu-id="66231-264">The preview channels give you access to the latest DevTools features.</span></span>  

## <span data-ttu-id="66231-265">与 Microsoft Edge DevTools 团队联系</span><span class="sxs-lookup"><span data-stu-id="66231-265">Getting in touch with Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- <<../../_shared/devtools-feedback.md>>  

<<../../_shared/canary.md>>  

<<../../_shared/discover.md>> -->  

<!-- image links -->  

[ImagePerformanceToolKeyboardReaderImprovements]: ../../images/2020/01/a11y-performance-tool.msft.gif "图 1：DevTools 中的性能工具，可通过键盘导航和屏幕阅读器改进"  
[ImageLocalizedGerman]: ../../images/2020/01/localized-devtools.msft.png "图 2：常规工作区中的 DevTools"  
[ImageHintsTabWebhintExtension]: ../../images/2020/01/webhint-browser-extension.msft.png "图 3：安装 Web hint 浏览器扩展时 Microsoft Edge DevTools 中的"提示"选项卡"  
[Image3DView]: ../../images/2020/01/3dview.msft.png "图 4：Microsoft Edge 开发工具中的 3D 视图"  
[ImageElementsVisualStudioCode]: ../../images/2020/01/elements-for-edge.msft.png "图 5：使用 Microsoft Edge 扩展的元素 ，VS 代码中的元素工具"  
[ImageDebuggerExtensionVisualStudioCode]: ../../images/2020/01/vscode-debugger.msft.png "图 6：使用 VS 代码的 Microsoft Edge 扩展的调试程序"  
[ImageWebhintVisualStudioCodeExtensionWorkspace]: ../../images/2020/01/webhint-vscode-extension.msft.png "图 7：Webhint VS 代码扩展分析 VS 代码中的 .tsx 文件"  
[ImageVisualStudioLaunchWebApp]: ../../images/2020/01/vs.msft.png "图 8：Visual Studio并通过在 Microsoft Edge Canary、Dev 或 Beta 中启动你的 Web 应用的选项"  
[ImageTrackingPrevention]: ../../images/2020/01/tracking-prevention.msft.png "图 9：跟踪阻止对跟踪器的存储的访问权限时，主机中的邮件" 
[ImageMotoG4]: ../../images/2020/01/motog4.msft.png "图 10：模拟 Moto G4 视区" 
[ImageMotoG4Frame]: ../../images/2020/01/motog4frame.msft.png "图 11：显示 Moto G4 硬件" 
[ImageBlockedCookies]: ../../images/2020/01/blockedcookies.msft.png "图 12：在应用程序面板的 Cookie 窗格中阻止 Cookie"
[ImageEditCookie]: ../../images/2020/01/editcookie.msft.png "图 13：编辑 Cookie 值"
[ImageCopyFetch]: ../../images/2020/01/fetchcookies.msft.png "图 14：作为提Node.js复制"
[ImageManifestIcon]: ../../images/2020/01/manifesticons.msft.png "图 15：清单窗格中的图标"
[ImageEscapedString]: ../../images/2020/01/escapedstring.msft.png "图 16：转码的字符串"
[ImageUnescapedString]: ../../images/2020/01/unescapedstring.msft.png "图 17：未转动的值"
[ImageSourcemapError]: ../../images/2020/01/sourcemap.msft.png "图 18：主机中的源映射加载错误"
[ImageSettings]: ../../images/2020/01/settings.msft.png "图 19：禁用"设置"中文件的过时端文件"
[ImageScroll]: ../../images/2020/01/scrollingsources.msft.png "图 20：源面板中现已禁用通过文件末尾滚动"

<!-- links -->  

[DeviceToolbar]: ../../../device-mode/index.md#simulate-a-mobile-viewport "在 Microsoft Edge DevTools 中使用设备模式模拟移动视区"
[DeviceFrame]: ../../../device-mode/index.md#show-device-frame "选择"显示设备框架"以显示视区中物理设备框架。"
[CommandMenu]: ../../../command-menu/index.md "使用 Microsoft Edge 开发人员工具命令菜单运行命令"  
[ThrottleNetworkAndCpu]: ../../../device-mode/index.md#throttle-the-network-and-cpu "将网络和 CPU 固定到更准确地模拟移动用户的 Web 浏览条件。"
[crbug924693]: https://crbug.com/924693 "924693：功能请求：将 Moto G4 添加到设备模式列表"
[crbug1030258]: https://crbug.com/1030258 "1030258"
[crbug1026879]: https://crbug.com/1026879 "1026879：开发者主机中的"Cookie"选项卡不如此优先级显示优先级"
[CookiesFields]: ../../../storage/cookies.md#fields "Cookie 表中的字段"
[crbug1029826]: https://crbug.com/1029826 "1029826：网络选项卡 -> 右键单击可请求 ->复制 -> 副本作为提取值，无需复制 Cookie"
[crbug985402]: https://crbug.com/985402 "985402：Web 应用清单图标错误字符串比较为复选"
[CSSContentDemo]: https://mathiasbynens.github.io/css-dbg-stories/css-escapes.html "未转接的 CSS 内容的演示"
[Settings]: ../../../customize/index.md#settings "使用"设置"自定义 Microsoft Edge 开发工具"
[PostTweetEdgeDevTools]: https://aka.ms/tweet/edgedevtools "@EdgeDevTools | 发布推文"  
[GitHubMicrosoftDocsEdgeDeveloperNewIssue]: https://aka.ms/edgedevtoolsdocs/feedback "新问题 - MicrosoftDocs/edge-developer"  
[TheWebWeWant]: https://aka.ms/webwewant "我们想要的网络"
[MicrosoftEdgePreviewChannels]: https://aka.ms/microsoftedge "Microsoft Edge 预览频道"  
[VisualStudioCodeDebuggerEdgeExtension]: ../../../../visual-studio-code/debugger-for-edge.md "Microsoft Edge 的调试程序"  
[VisualStudioCodeElementEdgeExtension]: ../../../../visual-studio-code/elements-for-edge.md "Microsoft Edge 元素与代码扩展"  
[crbug963183]: https://crbug.com/963183 "963183 - DevTools 不符合 WCAG 兼容性"
[crbug941561]: https://crbug.com/941561 "941561 - DevTools 的本地化能力"
[crbug987787]: https://crbug.com/987787 "987787 - Dom 3D 视图"
[AccessibilityInsights]: https://aka.ms/a11yinsights "辅助功能见解"  
[MicrosoftEdgeInsiderAddons]: https://aka.ms/webhint/edge-extension "Microsoft Edge Insider Addons"  
[MicrosoftVisualStudio]: ../../../../visual-studio/index.md "Visual Studio"  
[MicrosoftVisualStudioDownloads]: https://aka.ms/vs/download "下载 Visual Studio 2019 for Windows \& Mac"  
[MDNDocumentObjectModel]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model "文档对象模型 (DOM) |MDN"  
[MDNZIndex]: https://developer.mozilla.org/docs/Web/CSS/z-index "z-index |MDN"  
[EdgeDevToolsTwitterAccount]: https://aka.ms/twitter/edgedevtools "@EdgeDevTools Twitter 帐户"
[VisualStudioCode]: https://aka.ms/vscode "Visual Studio代码"  
[VisualStudioMarketplaceDebuggerEdge]: https://aka.ms/debugger4code "Microsoft Edge 调试程序 - 使用比Visual Studio出版"  
[VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension]: https://aka.ms/elements4code "Microsoft Edge \ (Chromium\) - Visual Studio Marketplace 的元素"  
[VisualStudioMarketplaceWebhintExtension]: https://aka.ms/webhint4code "webhint - Visual Studio 商场"
[Webhint]: https://aka.ms/webhint "Webhint"  
[WebhintBrowserExtension]: https://aka.ms/webhint/browser-extension "Webhint 浏览器扩展 |Webhint 文档"  
[WebhintVisualStudioCodeExtension]: https://aka.ms/webhint/code-extension "Webhint 代码扩展 |Webhint 文档"  
[TrackingPrevention]: https://aka.ms/microsoftedge/tracking-prevention-blog "在 Microsoft Edge 博客文章中提进跟踪防护"

> [!NOTE]
> <span data-ttu-id="66231-322">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="66231-322">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="66231-323">原始页面是在此处找到的，由[here](https://developers.google.com/web/updates/2020/01/devtools/index)[Kayce Basques][KayceBasques] \ (Technical Writer、Chrome DevTools 和 & Lighthouse\) 编写。</span><span class="sxs-lookup"><span data-stu-id="66231-323">The original page is found [here](https://developers.google.com/web/updates/2020/01/devtools/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools & Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="66231-325">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="66231-325">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  