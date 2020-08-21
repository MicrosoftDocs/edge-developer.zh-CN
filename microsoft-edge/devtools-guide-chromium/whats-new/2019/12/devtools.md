---
title: 'Microsoft Edge 80 移动版 DevTools (新增) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/30/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 03fd78eddf54b68d072ba11401a897ad9f109058
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "10942145"
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

# <span data-ttu-id="2f83b-103">Microsoft Edge 80 移动版 DevTools (新增) </span><span class="sxs-lookup"><span data-stu-id="2f83b-103">What's new in DevTools (Microsoft Edge 80)</span></span>  

## <span data-ttu-id="2f83b-104">来自 Microsoft Edge 开发人员工具团队公告</span><span class="sxs-lookup"><span data-stu-id="2f83b-104">Announcements from the Microsoft Edge DevTools team</span></span>  

<span data-ttu-id="2f83b-105">以下各部分是你可能错过的 Microsoft Edge 开发人员工具团队的公告列表！</span><span class="sxs-lookup"><span data-stu-id="2f83b-105">The following sections are a list of announcements you may have missed from the Microsoft Edge DevTools team!</span></span> <span data-ttu-id="2f83b-106">请查看这些公告，尝试使用 DevTools 和 VS 代码扩展等中的新功能。</span><span class="sxs-lookup"><span data-stu-id="2f83b-106">Check them out to try new features in the DevTools, VS Code extensions, and more.</span></span>  <span data-ttu-id="2f83b-107">若要了解有关开发人员工具中的所有最新功能和最强大功能的最新动态，请下载 [Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels]并[在 Twitter 上关注我们][EdgeDevToolsTwitterAccount]。</span><span class="sxs-lookup"><span data-stu-id="2f83b-107">To stay up to date on all the latest and greatest features in your developer tools, download the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] and [follow us on Twitter][EdgeDevToolsTwitterAccount].</span></span>  

### <span data-ttu-id="2f83b-108">DevTools 的辅助功能改进</span><span class="sxs-lookup"><span data-stu-id="2f83b-108">Accessibility improvements to the DevTools</span></span>  

<span data-ttu-id="2f83b-109">DevTools 团队已对 Chromium 作了 170 更改，以解决 DevTools 中的高影响颜色对比度、键盘和屏幕阅读器问题。</span><span class="sxs-lookup"><span data-stu-id="2f83b-109">The DevTools team has contributed 170 changes to Chromium to address high-impact color contrast, keyboard, and screen reader issues in the DevTools.</span></span>  <span data-ttu-id="2f83b-110">构建 Web 的每个开发人员都应该能够使用 DevTools。</span><span class="sxs-lookup"><span data-stu-id="2f83b-110">Every developer building the web should be able to use the DevTools.</span></span>  

> ##### <span data-ttu-id="2f83b-111">图 1</span><span class="sxs-lookup"><span data-stu-id="2f83b-111">Figure 1</span></span>  
> <span data-ttu-id="2f83b-112">通过键盘导航和屏幕阅读器改进，开发人员工具中的性能工具</span><span class="sxs-lookup"><span data-stu-id="2f83b-112">The Performance tool in the DevTools with the keyboard navigation and screen reader improvements</span></span>  
> ![通过键盘导航和屏幕阅读器改进，开发人员工具中的性能工具][ImagePerformanceToolKeyboardReaderImprovements]  

<span data-ttu-id="2f83b-114">希望了解如何使您的网页对所有用户使用？</span><span class="sxs-lookup"><span data-stu-id="2f83b-114">Want to learn how to make your web page accessible to all of your users?</span></span>  <span data-ttu-id="2f83b-115">下载 Microsoft Edge [的辅助][AccessibilityInsights] 功能见解和 [WebHint][WebhintBrowserExtension] 扩展以开始使用。</span><span class="sxs-lookup"><span data-stu-id="2f83b-115">Download the [Accessibility Insights][AccessibilityInsights] and [webhint][WebhintBrowserExtension] extensions for Microsoft Edge to get started.</span></span>  

<span data-ttu-id="2f83b-116">如果使用屏幕阅读器或键盘在 DevTools 中导航，请通过 [tweett 发送][PostTweetEdgeDevTools] 或单击"发送反馈"图标来向我们 [发送你的反](#getting-in-touch-with-microsoft-edge-devtools-team) 馈！</span><span class="sxs-lookup"><span data-stu-id="2f83b-116">If you use screen readers or the keyboard to navigate around the DevTools, send us your feedback by [tweeting][PostTweetEdgeDevTools] at us or clicking the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!</span></span>  

<span data-ttu-id="2f83b-117">Chromium 问题 [#963183][crbug963183]</span><span class="sxs-lookup"><span data-stu-id="2f83b-117">Chromium issue [#963183][crbug963183]</span></span>  

### <span data-ttu-id="2f83b-118">使用其他语言的 DevTools</span><span class="sxs-lookup"><span data-stu-id="2f83b-118">Using the DevTools in other languages</span></span>  

<span data-ttu-id="2f83b-119">许多开发人员将使用 StackOverflow 和 VS 代码等其他开发人员工具，不只是使用英语。</span><span class="sxs-lookup"><span data-stu-id="2f83b-119">Many developers use other developer tools, like StackOverflow and VS Code, in their native language, not just in English.</span></span>  <span data-ttu-id="2f83b-120">我们很高为将公布发布的 DevTools 的本地化，你现在可以使用除英语之外的 10 种语言之一：</span><span class="sxs-lookup"><span data-stu-id="2f83b-120">We’re excited to announce localization for the DevTools, which you are now able to use in one of 10 languages besides English:</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="2f83b-121">简体\)  (- &#20013;&#25991;&#65288;&#31616;&#20307;&#65289;</span><span class="sxs-lookup"><span data-stu-id="2f83b-121">Chinese \(Simplified\) - &#20013;&#25991;&#65288;&#31616;&#20307;&#65289;</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="2f83b-122">中文 \ (Traditional\) - &#20013;&#25991;&#65288;&#32321;&#39636;&#65289;</span><span class="sxs-lookup"><span data-stu-id="2f83b-122">Chinese \(Traditional\) - &#20013;&#25991;&#65288;&#32321;&#39636;&#65289;</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      <span data-ttu-id="2f83b-123">法语 – 法国 - 法&#231;出</span><span class="sxs-lookup"><span data-stu-id="2f83b-123">French – fran&#231;ais</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="2f83b-124">German - desch</span><span class="sxs-lookup"><span data-stu-id="2f83b-124">German - deutsch</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      <span data-ttu-id="2f83b-125">意大利语 - 意大利语</span><span class="sxs-lookup"><span data-stu-id="2f83b-125">Italian - italiano</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="2f83b-126">日语 -  &#26085;&#26412;&#35486;</span><span class="sxs-lookup"><span data-stu-id="2f83b-126">Japanese - &#26085;&#26412;&#35486;</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      <span data-ttu-id="2f83b-127">当理 -  &#54620;&#44397;&#50612;</span><span class="sxs-lookup"><span data-stu-id="2f83b-127">Korean - &#54620;&#44397;&#50612;</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="2f83b-128">葡葡葡图 -&#234;葡表</span><span class="sxs-lookup"><span data-stu-id="2f83b-128">Portuguese - portugu&#234;s</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      <span data-ttu-id="2f83b-129">俄语 –  &#1088;&#1091;&#1089;&#1089;&#1082;&#1080;&#1081;</span><span class="sxs-lookup"><span data-stu-id="2f83b-129">Russian – &#1088;&#1091;&#1089;&#1089;&#1082;&#1080;&#1081;</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="2f83b-130">西班牙语 - espa 通&#241;旧</span><span class="sxs-lookup"><span data-stu-id="2f83b-130">Spanish - espa&#241;ol</span></span>
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

<span data-ttu-id="2f83b-131">导航到 `edge://flags` "启用 **"本地化开发人员工具** 标志并将其设为 **"启用**"。</span><span class="sxs-lookup"><span data-stu-id="2f83b-131">Navigate to `edge://flags` and set the **Enable localized Developer Tools** flag to **Enabled**.</span></span>  <span data-ttu-id="2f83b-132">此外， **将开发人员工具实用标志** 设置为" **已启用**"。</span><span class="sxs-lookup"><span data-stu-id="2f83b-132">Also set the **Developer Tools experiments** flag to **Enabled**.</span></span>  <span data-ttu-id="2f83b-133">重新启动 Microsoft Edge 并打开 DevTools。</span><span class="sxs-lookup"><span data-stu-id="2f83b-133">Restart Microsoft Edge and open the DevTools.</span></span>  <!-- Press `F1` in the DevTools or go to Settings > Experiments and check the **Match browser language** checkbox.  -->  <span data-ttu-id="2f83b-134">DevTools 在 Microsoft Edge 中匹配。 `edge://settings/languages`</span><span class="sxs-lookup"><span data-stu-id="2f83b-134">The DevTools match the language you use for Microsoft Edge in `edge://settings/languages`.</span></span>  

> ##### <span data-ttu-id="2f83b-135">图 2</span><span class="sxs-lookup"><span data-stu-id="2f83b-135">Figure 2</span></span>  
> <span data-ttu-id="2f83b-136">常规工具</span><span class="sxs-lookup"><span data-stu-id="2f83b-136">The DevTools in German</span></span>  
> ![常规工具][ImageLocalizedGerman]  

<span data-ttu-id="2f83b-138">如果要使用不同于可用语言的 DevTools， [请向我们提供推][PostTweetEdgeDevTools] 送或单击"发送反馈 ["](#getting-in-touch-with-microsoft-edge-devtools-team) 图标。</span><span class="sxs-lookup"><span data-stu-id="2f83b-138">If you want to use the DevTools in a different language than the ones that are available, [tweet][PostTweetEdgeDevTools] at us or click the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon.</span></span>  

<span data-ttu-id="2f83b-139">Chromium [问题#941561][crbug941561]</span><span class="sxs-lookup"><span data-stu-id="2f83b-139">Chromium issue [#941561][crbug941561]</span></span>  

### <span data-ttu-id="2f83b-140">Webhint Microsoft Edge 扩展</span><span class="sxs-lookup"><span data-stu-id="2f83b-140">webhint Microsoft Edge extension</span></span>  

<span data-ttu-id="2f83b-141">通过 Webhint Microsoft Edge 扩展，可轻松浏览网页，并在 DevTools 中轻松浏览网页，并获取关于辅助功能、浏览器兼容性、安全性、性能等的反馈。</span><span class="sxs-lookup"><span data-stu-id="2f83b-141">The webhint Microsoft Edge extension allows you to easily scan your web page and get feedback on accessibility, browser compatibility, security, performance, and more within the DevTools.</span></span>  <span data-ttu-id="2f83b-142">阅读更多信息 [https://webhint.io][Webhint] 。</span><span class="sxs-lookup"><span data-stu-id="2f83b-142">Read more at [https://webhint.io][Webhint].</span></span>  

> ##### <span data-ttu-id="2f83b-143">图 3</span><span class="sxs-lookup"><span data-stu-id="2f83b-143">Figure 3</span></span>  
> <span data-ttu-id="2f83b-144">安装了 Webhint 浏览器扩展时 DevTools 中的"提示"选项卡</span><span class="sxs-lookup"><span data-stu-id="2f83b-144">The Hints tab in the DevTools when the webhint browser extension is installed</span></span>  
> ![安装了 Webhint 浏览器扩展时 DevTools 中的"提示"选项卡][ImageHintsTabWebhintExtension]  

<span data-ttu-id="2f83b-146">[试用 Microsoft Edge 中的 Webhint 浏览器扩展][MicrosoftEdgeInsiderAddons]。</span><span class="sxs-lookup"><span data-stu-id="2f83b-146">[Try the webhint browser extension in Microsoft Edge][MicrosoftEdgeInsiderAddons].</span></span>  <span data-ttu-id="2f83b-147">安装扩展后，打开 DevTools，然后选择"提示"选项卡。 在此处，运行可自定义网站扫描。</span><span class="sxs-lookup"><span data-stu-id="2f83b-147">Once you install the extension, open the DevTools and select the Hints tab.  From here, run a customizable site scan.</span></span>  <span data-ttu-id="2f83b-148">要了解详细信息 [，请转到][WebhintBrowserExtension] webhint.io。</span><span class="sxs-lookup"><span data-stu-id="2f83b-148">Head over to [webhint.io][WebhintBrowserExtension] to learn more.</span></span>

### <span data-ttu-id="2f83b-149">3D 视图</span><span class="sxs-lookup"><span data-stu-id="2f83b-149">3D View</span></span>  

<span data-ttu-id="2f83b-150">通过 **在文档对象模型** [\ (DOM\) ][MDNDocumentObjectModel] 或 [z 索][MDNZIndex] 引堆叠上下文中导航，使用 3D 视图调试你的 Web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="2f83b-150">Use the **3D View** to debug your web application by navigating through the [Document Object Model \(DOM\)][MDNDocumentObjectModel] or the [z-index][MDNZIndex] stacking context.</span></span>  

> ##### <span data-ttu-id="2f83b-151">图 4</span><span class="sxs-lookup"><span data-stu-id="2f83b-151">Figure 4</span></span>  
> <span data-ttu-id="2f83b-152">DevTools 中的 3D 视图</span><span class="sxs-lookup"><span data-stu-id="2f83b-152">The 3D View in the DevTools</span></span>  
> ![DevTools 中的 3D 视图][Image3DView]  

<span data-ttu-id="2f83b-154">若要访问 3D 视图，请 `edge://flags` 导航到并确保"开发人员 **工具** "实实标志设置为 **"已启用**"。</span><span class="sxs-lookup"><span data-stu-id="2f83b-154">To access the 3D View, navigate to `edge://flags` and ensure that the **Developer Tools experiments** flag is set to **Enabled**.</span></span>  <span data-ttu-id="2f83b-155">重新启动 Microsoft Edge 并打开 DevTools。</span><span class="sxs-lookup"><span data-stu-id="2f83b-155">Restart Microsoft Edge and open the DevTools.</span></span>  <span data-ttu-id="2f83b-156">在 `F1` DevTools 或转到"**Settings**设置"，导航**到实测部分**，然后选中 **"启用 3D 视图**"复选框。</span><span class="sxs-lookup"><span data-stu-id="2f83b-156">Press `F1` in the DevTools or go to **Settings**, navigate to **Experiments** section, and check the **Enable 3D View** checkbox.</span></span>  <span data-ttu-id="2f83b-157">现在，在 `Ctrl`  +  `Shift`  +  `P` **3D 视图中键入并**选择"显示**3D 视图**"。</span><span class="sxs-lookup"><span data-stu-id="2f83b-157">Now, press `Ctrl` + `Shift` + `P`, type in **3D View** and select **Show 3D View**.</span></span>  

<span data-ttu-id="2f83b-158">我们正在处理 UI，并向 3D 视图添加更多功能，因此请向我们发送反 [馈](#getting-in-touch-with-microsoft-edge-devtools-team)。</span><span class="sxs-lookup"><span data-stu-id="2f83b-158">We're working on the UI and adding more functionality to the 3D View so please send us your [feedback](#getting-in-touch-with-microsoft-edge-devtools-team).</span></span>  

<span data-ttu-id="2f83b-159">Chromium [问题#987787][crbug987787]</span><span class="sxs-lookup"><span data-stu-id="2f83b-159">Chromium issue [#987787][crbug987787]</span></span>

### <span data-ttu-id="2f83b-160">Visual Studio代码扩展</span><span class="sxs-lookup"><span data-stu-id="2f83b-160">Visual Studio Code extensions</span></span>  

<span data-ttu-id="2f83b-161">DevTools 团队还发布了 [用于 Visual Studio Code \ (VS Code\) ][VisualStudioCode] 的一些扩展，它允许你直接从文本编辑器使用 DevTools 的功能！</span><span class="sxs-lookup"><span data-stu-id="2f83b-161">The DevTools team has also released some extensions for [Visual Studio Code \(VS Code\)][VisualStudioCode] that let you use the power of the DevTools directly from your text editor!</span></span> <span data-ttu-id="2f83b-162">请参阅以下扩展项：</span><span class="sxs-lookup"><span data-stu-id="2f83b-162">Check out the extensions below:</span></span>  

#### <span data-ttu-id="2f83b-163">Microsoft Edge 的元素</span><span class="sxs-lookup"><span data-stu-id="2f83b-163">Elements for Microsoft Edge</span></span>  

<span data-ttu-id="2f83b-164">通过将 [Microsoft Edge \ (m Chromium\) 按钮扩展添加到的元素，从 VS ][VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension] 代码内使用元素工具。</span><span class="sxs-lookup"><span data-stu-id="2f83b-164">Use the Elements tool from within VS Code by adding the [Elements for Microsoft Edge \(Chromium\)][VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension] VS Code extension.</span></span>  

> ##### <span data-ttu-id="2f83b-165">图 5</span><span class="sxs-lookup"><span data-stu-id="2f83b-165">Figure 5</span></span>  
> <span data-ttu-id="2f83b-166">使用用于 Microsoft Edge 扩展的元素 VS 代码中的元素工具</span><span class="sxs-lookup"><span data-stu-id="2f83b-166">The Elements tool in VS Code using the Elements for Microsoft Edge extension</span></span>  
> ![使用用于 Microsoft Edge 扩展的元素 VS 代码中的元素工具][ImageElementsVisualStudioCode]  

<span data-ttu-id="2f83b-168">有关详细信息，请查目[Microsoft Edge 中的元素与代码扩展。][VisualStudioCodeElementEdgeExtension]</span><span class="sxs-lookup"><span data-stu-id="2f83b-168">For more information, check out [Elements for Microsoft Edge VS Code extension][VisualStudioCodeElementEdgeExtension].</span></span>  

#### <span data-ttu-id="2f83b-169">Microsoft Edge 调试程序</span><span class="sxs-lookup"><span data-stu-id="2f83b-169">Debugger for Microsoft Edge</span></span>  

<span data-ttu-id="2f83b-170">借助 Microsoft Edge 的 [调试程序][VisualStudioMarketplaceDebuggerEdge] ，直接从 VS 代码在 Microsoft Edge 中运行的 JavaScript！</span><span class="sxs-lookup"><span data-stu-id="2f83b-170">With the [Debugger for Microsoft Edge][VisualStudioMarketplaceDebuggerEdge] VS Code extension, debug JavaScript running in Microsoft Edge directly from VS Code!</span></span>  

> ##### <span data-ttu-id="2f83b-171">图 6</span><span class="sxs-lookup"><span data-stu-id="2f83b-171">Figure 6</span></span>  
> <span data-ttu-id="2f83b-172">VS 代码中的 Microsoft Edge 扩展程序</span><span class="sxs-lookup"><span data-stu-id="2f83b-172">The Debugger for Microsoft Edge Extension in VS Code</span></span>  
> ![VS 代码中的 Microsoft Edge 扩展程序][ImageDebuggerExtensionVisualStudioCode]  

<span data-ttu-id="2f83b-174">有关详细信息，请了解如何从[VS 代码调试 Microsoft Edge。][VisualStudioCodeDebuggerEdgeExtension]</span><span class="sxs-lookup"><span data-stu-id="2f83b-174">For more information, check out [how to debug Microsoft Edge from VS Code][VisualStudioCodeDebuggerEdgeExtension].</span></span>  

#### <span data-ttu-id="2f83b-175">webhint</span><span class="sxs-lookup"><span data-stu-id="2f83b-175">webhint</span></span>  

<span data-ttu-id="2f83b-176">[Webhint][VisualStudioMarketplaceWebhintExtension] VS 代码扩展在你编写 `webhint` 时使用它改进网页！</span><span class="sxs-lookup"><span data-stu-id="2f83b-176">The [webhint][VisualStudioMarketplaceWebhintExtension] VS Code extension uses `webhint` to improve your web page while you're writing it!</span></span> <span data-ttu-id="2f83b-177">此扩展基于分析在工作区文件上运行和 `webhint` 报告诊断。</span><span class="sxs-lookup"><span data-stu-id="2f83b-177">This extension runs and reports diagnostics on your workspace files based on `webhint` analysis.</span></span>  

> ##### <span data-ttu-id="2f83b-178">图 7</span><span class="sxs-lookup"><span data-stu-id="2f83b-178">Figure 7</span></span>  
> <span data-ttu-id="2f83b-179">Webhint VS 代码扩展分析 VS 代码中的 .tsx 文件</span><span class="sxs-lookup"><span data-stu-id="2f83b-179">The webhint VS Code extension analyzing a .tsx file in VS Code</span></span>  
> ![Webhint VS 代码扩展分析 VS 代码中的 .tsx 文件][ImageWebhintVisualStudioCodeExtensionWorkspace]  

<span data-ttu-id="2f83b-181">[了解有关 VS 代码 Webhint 扩展的详细信息][WebhintVisualStudioCodeExtension]。</span><span class="sxs-lookup"><span data-stu-id="2f83b-181">[Learn more about the VS Code webhint extension][WebhintVisualStudioCodeExtension].</span></span>  

### <span data-ttu-id="2f83b-182">Visual Studio集成</span><span class="sxs-lookup"><span data-stu-id="2f83b-182">Visual Studio integration</span></span>
<span data-ttu-id="2f83b-183">在 Visual Studio 2019 版本 16.2 或更高版本中，Visual Studio 使用调试器调试在 Microsoft Edge 中运行的 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="2f83b-183">In Visual Studio 2019 version 16.2 or later, use the Visual Studio debugger to debug JavaScript running in Microsoft Edge.</span></span>  <span data-ttu-id="2f83b-184">[请Visual Studio 2019，][MicrosoftVisualStudioDownloads] 试用此功能！</span><span class="sxs-lookup"><span data-stu-id="2f83b-184">[Download Visual Studio 2019][MicrosoftVisualStudioDownloads] to try this feature out!</span></span>  

> ##### <span data-ttu-id="2f83b-185">图 8</span><span class="sxs-lookup"><span data-stu-id="2f83b-185">Figure 8</span></span>  
> <span data-ttu-id="2f83b-186">Visual Studio在 Microsoft Edge Canary、Dev 或 Beta 中启动你的 Web 应用"的选项</span><span class="sxs-lookup"><span data-stu-id="2f83b-186">Visual Studio with the option to launch your web app in Microsoft Edge Canary, Dev, or Beta</span></span>  
> ![Visual Studio在 Microsoft Edge Canary、Dev 或 Beta 中启动你的 Web 应用"的选项][ImageVisualStudioLaunchWebApp]  

<span data-ttu-id="2f83b-188">[阅读我们的博客文章以了解如何从 microsoft Edge Visual Studio。][MicrosoftVisualStudioBlogDebugJavascript]</span><span class="sxs-lookup"><span data-stu-id="2f83b-188">[Read our blog post to learn how to debug Microsoft Edge from Visual Studio][MicrosoftVisualStudioBlogDebugJavascript].</span></span>  

### <span data-ttu-id="2f83b-189">跟踪防护主机消息</span><span class="sxs-lookup"><span data-stu-id="2f83b-189">Tracking prevention Console messages</span></span>  

<span data-ttu-id="2f83b-190">跟踪防护是 Microsoft Edge 中唯一的功能，可防止你被之前尚未访问过的网站进行跟踪。</span><span class="sxs-lookup"><span data-stu-id="2f83b-190">Tracking prevention is a unique feature in Microsoft Edge that protects you from being tracked by websites you haven't visited before.</span></span>  <span data-ttu-id="2f83b-191">默认跟踪防护设置是"平衡模式"，为了使体验保持平衡隐私和 Web 兼容性的体验，这将对第三方跟踪程序和已知的义务跟踪器进行保护。</span><span class="sxs-lookup"><span data-stu-id="2f83b-191">The default tracking prevention setting is Balanced mode, which blocks 3rd party trackers and known malicious trackers for an experience that balances privacy and web compatibility.</span></span>  <span data-ttu-id="2f83b-192">为了在特定跟踪器被阻止时，为更深入地了解网页的兼容性，我们还在跟踪器被阻止时在主机中添加了警告邮件。</span><span class="sxs-lookup"><span data-stu-id="2f83b-192">To give you more insight into the compatibility of your web page when certain trackers are blocked, we've also added warning messages in the Console when a tracker is blocked.</span></span>  

> ##### <span data-ttu-id="2f83b-193">图 9</span><span class="sxs-lookup"><span data-stu-id="2f83b-193">Figure 9</span></span>  
> <span data-ttu-id="2f83b-194">跟踪防护阻止对跟踪器的存储的访问时主机中的消息</span><span class="sxs-lookup"><span data-stu-id="2f83b-194">Messages in the Console when tracking prevention blocks access to storage for a tracker</span></span>  
> ![跟踪防护阻止对跟踪器的存储的访问时主机中的消息][ImageTrackingPrevention]  

<span data-ttu-id="2f83b-196">[了解有关跟踪防护和在隐私和 Web 之间余额之间余额的详细信息][TrackingPrevention]。</span><span class="sxs-lookup"><span data-stu-id="2f83b-196">[Read more about tracking prevention and the balance between privacy and web compatibility][TrackingPrevention].</span></span>  

## <span data-ttu-id="2f83b-197">来自 Chromium 项目的公告</span><span class="sxs-lookup"><span data-stu-id="2f83b-197">Announcements from the Chromium project</span></span>  

<span data-ttu-id="2f83b-198">以下部分公布给开源 Chromium 项目的 Microsoft Edge 中提供的其他功能。</span><span class="sxs-lookup"><span data-stu-id="2f83b-198">The following sections announce additional features available in Microsoft Edge 80 that were contributed to the open source Chromium project.</span></span>  

### <span data-ttu-id="2f83b-199">对主机中的允许和上课绑定的支持</span><span class="sxs-lookup"><span data-stu-id="2f83b-199">Support for let and class redeclarations in the Console</span></span>  

<span data-ttu-id="2f83b-200">现在，主机支持兑换和 `let` `class` 语句。</span><span class="sxs-lookup"><span data-stu-id="2f83b-200">The Console now supports redeclarations of `let` and `class` statements.</span></span>  <span data-ttu-id="2f83b-201">重新声明是使用控制台试用新的 JavaScript 代码的 Web 开发人员的常见概用。</span><span class="sxs-lookup"><span data-stu-id="2f83b-201">The inability to redeclare was a common annoyance for web developers who use the Console to experiment with new JavaScript code.</span></span>  

> [!WARNING]
> <span data-ttu-id="2f83b-202">在主机之外或单台主机输入内，是否在脚本中重新声明 `let` `class` 导致 `SyntaxError` 。</span><span class="sxs-lookup"><span data-stu-id="2f83b-202">Redeclaring a `let` or `class` statement in a script outside of the Console or within a single Console input still causes a `SyntaxError`.</span></span>  

<span data-ttu-id="2f83b-203">例如，以前在使用指南解读本地变量时， `let` 主机将威子数据将引发错误：</span><span class="sxs-lookup"><span data-stu-id="2f83b-203">For example, previously, when redeclaring a local variable with `let`, the Console threw an error:</span></span>  

> ##### <span data-ttu-id="2f83b-204">图 10</span><span class="sxs-lookup"><span data-stu-id="2f83b-204">Figure 10</span></span>  
> <span data-ttu-id="2f83b-205">Microsoft Edge 79 中的主机显示了该按钮无法回收失败</span><span class="sxs-lookup"><span data-stu-id="2f83b-205">The Console in Microsoft Edge 79 showing that the let redeclaration fails</span></span>  
> ![Microsoft Edge 79 中的主机显示了该按钮无法回收失败][ImageConsoleRedeclarationFails]  

<span data-ttu-id="2f83b-207">现在，主机允许重新声明：</span><span class="sxs-lookup"><span data-stu-id="2f83b-207">Now, the Console allows the redeclaration:</span></span>  

> ##### <span data-ttu-id="2f83b-208">图 11</span><span class="sxs-lookup"><span data-stu-id="2f83b-208">Figure 11</span></span>  
> <span data-ttu-id="2f83b-209">Microsoft Edge 80 中的主机显示允许回收成功</span><span class="sxs-lookup"><span data-stu-id="2f83b-209">The Console in Microsoft Edge 80 showing that the let redeclaration succeeds</span></span>  
> ![Microsoft Edge 80 中的主机显示允许回收成功][ImageConsoleRedeclarationSucceeds]  

<span data-ttu-id="2f83b-211">Chromium [问题#1004193][crbug1004193]</span><span class="sxs-lookup"><span data-stu-id="2f83b-211">Chromium issue [#1004193][crbug1004193]</span></span>  

### <span data-ttu-id="2f83b-212">改进了 WebAssembly 调试</span><span class="sxs-lookup"><span data-stu-id="2f83b-212">Improved WebAssembly debugging</span></span>  

<span data-ttu-id="2f83b-213">DevTools 已开始支持 [DWARF][DwarfHome]调试标准，这意味着在 DevTools 中通过代码逐步改进支持、设置断点并解决源语言的堆叠跟踪。</span><span class="sxs-lookup"><span data-stu-id="2f83b-213">DevTools has started to support the [DWARF Debugging Standard][DwarfHome], which means increased support for stepping over code, setting breakpoints, and resolving stack traces in your source languages within DevTools.</span></span>  

<!-- [TODO: Add this link back] -->  
<!--Check out [Improved WebAssembly debugging in Microsoft Edge DevTools][201912Webassembly] for the full story.  -->  

<!-- [TODO: Replace this image with screenshot in Edge] -->  
<!--
> ##### Figure  
> The new DWARF-powered WebAssembly debugging  
> ![The new DWARF-powered WebAssembly debugging][ImageDwarfPoweredWebAssemblyDebugging]  
-->  

### <span data-ttu-id="2f83b-214">网络面板更新</span><span class="sxs-lookup"><span data-stu-id="2f83b-214">Network panel updates</span></span>  

#### <span data-ttu-id="2f83b-215">"设计器"选项卡中的请求初始任务链接</span><span class="sxs-lookup"><span data-stu-id="2f83b-215">Request Initiator Chains in the Initiator tab</span></span>  

<span data-ttu-id="2f83b-216">你现在能够以嵌套列表的形式查看网络请求的初级和依赖项。</span><span class="sxs-lookup"><span data-stu-id="2f83b-216">You are now able to view the initiators and dependencies of a network request as a nested list.</span></span>  <span data-ttu-id="2f83b-217">这有助于你了解为何被请求了资源，或者由于脚本\ () 引发了哪些网络活动。</span><span class="sxs-lookup"><span data-stu-id="2f83b-217">This may help you understand why a resource was requested, or what network activity a certain resource \(such as a script\) caused.</span></span>  

> ##### <span data-ttu-id="2f83b-218">图 12</span><span class="sxs-lookup"><span data-stu-id="2f83b-218">Figure 12</span></span>  
> <span data-ttu-id="2f83b-219">"指示器"选项卡中的请求初始任务链接</span><span class="sxs-lookup"><span data-stu-id="2f83b-219">A Request Initiator Chain in the Initiator tab</span></span>  
> !["指示器"选项卡中的请求初始任务链接][ImageRequestInitiatorChain]  

<span data-ttu-id="2f83b-221">在 ["网络"面板中记录网络活动之后][DevToolsNetworkIndex]，单击某个资源，然后转到 **"启动器"** 选项卡，以查看 **请求启动器中链接**：</span><span class="sxs-lookup"><span data-stu-id="2f83b-221">After [logging network activity in the Network panel][DevToolsNetworkIndex], click a resource and then go to the **Initiator** tab to view the **Request Initiator Chain**:</span></span>  

*   <span data-ttu-id="2f83b-222">检查 **的资源为** 粗体。</span><span class="sxs-lookup"><span data-stu-id="2f83b-222">The **inspected resource** is bold.</span></span>  <span data-ttu-id="2f83b-223">在上面的屏幕截图中，是 `ai.2.min.js` 在检查的资源。</span><span class="sxs-lookup"><span data-stu-id="2f83b-223">In the screenshot above, `ai.2.min.js` is the inspected resource.</span></span>  
*   <span data-ttu-id="2f83b-224">检查的资源上方的资源就是 **初始值**。</span><span class="sxs-lookup"><span data-stu-id="2f83b-224">The resources above the inspected resource are the **initiators**.</span></span>  <span data-ttu-id="2f83b-225">在上面的屏幕截图中， `https://www.microsoftedgeinsider.com` 是初始的初始项 `ai.2.min.js` 。</span><span class="sxs-lookup"><span data-stu-id="2f83b-225">In the screenshot above, `https://www.microsoftedgeinsider.com` is the initiator of `ai.2.min.js`.</span></span>  <span data-ttu-id="2f83b-226">换言之， `https://www.microsoftedgeinsider.com` 导致网络请求 `ai.2.min.js` 。</span><span class="sxs-lookup"><span data-stu-id="2f83b-226">In other words, `https://www.microsoftedgeinsider.com` caused the network request for `ai.2.min.js`.</span></span>  
*   <span data-ttu-id="2f83b-227">已检查资源下方的资源是 **依赖项**。</span><span class="sxs-lookup"><span data-stu-id="2f83b-227">The resources below the inspected resource are the **dependencies**.</span></span>  <span data-ttu-id="2f83b-228">在上面的屏幕截图中，是 `https://dc.services.visualstudio.com/v2/track` 一个依赖关系 `ai.2.min.js` 。</span><span class="sxs-lookup"><span data-stu-id="2f83b-228">In the screenshot above, `https://dc.services.visualstudio.com/v2/track` is a dependency of `ai.2.min.js`.</span></span>  <span data-ttu-id="2f83b-229">换言之， `ai.2.min.js` 导致网络请求 `https://dc.services.visualstudio.com/v2/track` 。</span><span class="sxs-lookup"><span data-stu-id="2f83b-229">In other words, `ai.2.min.js` caused the network request for `https://dc.services.visualstudio.com/v2/track`.</span></span>  

> [!NOTE]
> <span data-ttu-id="2f83b-230">还可以通过保持此操作，然后将鼠标悬停在网络资源上来 `Shift` 访问指示器和依赖关系信息。</span><span class="sxs-lookup"><span data-stu-id="2f83b-230">Initiator and dependency information may also be accessed by holding `Shift` and then hovering over network resources.</span></span>  <span data-ttu-id="2f83b-231">[查看视图指示器和依赖关系][DevToolsNetworkReferenceViewInitiatorsDependencies]。</span><span class="sxs-lookup"><span data-stu-id="2f83b-231">See [View initiators and dependencies][DevToolsNetworkReferenceViewInitiatorsDependencies].</span></span>  

<span data-ttu-id="2f83b-232">Chromium [问题#842488][crbug842488]</span><span class="sxs-lookup"><span data-stu-id="2f83b-232">Chromium issue [#842488][crbug842488]</span></span>  

#### <span data-ttu-id="2f83b-233">突出显示概述中所选的网络请求</span><span class="sxs-lookup"><span data-stu-id="2f83b-233">Highlight the selected network request in the Overview</span></span>  

<span data-ttu-id="2f83b-234">单击网络资源以检查网络资源后，网络面板现在会在概述中为该资源放置蓝 **色边框**。</span><span class="sxs-lookup"><span data-stu-id="2f83b-234">After you click a network resource in order to inspect it, the Network panel now puts a blue border around that resource in the **Overview**.</span></span>  <span data-ttu-id="2f83b-235">这可以帮助您检测网络请求早于或晚于预期的。</span><span class="sxs-lookup"><span data-stu-id="2f83b-235">This is able to help you detect if the network request is happening earlier or later than expected.</span></span>  

> ##### <span data-ttu-id="2f83b-236">图 13</span><span class="sxs-lookup"><span data-stu-id="2f83b-236">Figure 13</span></span>  
> <span data-ttu-id="2f83b-237">突出显示所检查资源的"概述"窗格</span><span class="sxs-lookup"><span data-stu-id="2f83b-237">The Overview pane highlighting the inspected resource</span></span>  
> ![突出显示所检查资源的"概述"窗格][ImageOverviewPaneInspectedResource]  

<span data-ttu-id="2f83b-239">Chromium [问题#988253][crbug988253]</span><span class="sxs-lookup"><span data-stu-id="2f83b-239">Chromium issue [#988253][crbug988253]</span></span>  

#### <span data-ttu-id="2f83b-240">"网络"面板中的 URL 和路径列</span><span class="sxs-lookup"><span data-stu-id="2f83b-240">URL and path columns in the Network panel</span></span>  

<span data-ttu-id="2f83b-241">使用网络**面板**中的新 Path**和\*\*\*\*URL**列查看每个网络资源的绝对路径或完整 URL。</span><span class="sxs-lookup"><span data-stu-id="2f83b-241">Use the new **Path** and **URL** columns in the **Network** panel to see the absolute path or full URL of each network resource.</span></span>  

> ##### <span data-ttu-id="2f83b-242">图 14</span><span class="sxs-lookup"><span data-stu-id="2f83b-242">Figure 14</span></span>  
> <span data-ttu-id="2f83b-243">网络面板中新的路径和 URL 列</span><span class="sxs-lookup"><span data-stu-id="2f83b-243">The new Path and URL columns in the Network panel</span></span>  
> ![网络面板中新的路径和 URL 列][ImagePathNetworkPanel]  

<span data-ttu-id="2f83b-245">右键单击**Waterfall 表标题**，选择路**径\*\*\*\*或 URL**以显示新列。</span><span class="sxs-lookup"><span data-stu-id="2f83b-245">Right-click the **Waterfall** table header and select **Path** or **URL** to show the new columns.</span></span>  

<span data-ttu-id="2f83b-246">Chromium [问题#993366][crbug993366]</span><span class="sxs-lookup"><span data-stu-id="2f83b-246">Chromium issue [#993366][crbug993366]</span></span>  

#### <span data-ttu-id="2f83b-247">更新了用户代理字符串</span><span class="sxs-lookup"><span data-stu-id="2f83b-247">Updated User-Agent strings</span></span>  

<span data-ttu-id="2f83b-248">DevTools 支持通过"网络条件"选项卡设置自定义 **用户代理字符串** 。 用户代理字符串还影响附加到网络资源的 HTTP `User-Agent` 标头以及值 `navigator.userAgent` 。</span><span class="sxs-lookup"><span data-stu-id="2f83b-248">DevTools supports setting a custom User-Agent string through the **Network Conditions** tab.  The User-Agent string affects the `User-Agent` HTTP header attached to network resources, and also the value of `navigator.userAgent`.</span></span>  

<span data-ttu-id="2f83b-249">预定义的用户代理字符串已更新，以反过现代浏览器版本。</span><span class="sxs-lookup"><span data-stu-id="2f83b-249">The predefined User-Agent strings have been updated to reflect modern browser versions.</span></span>  

> ##### <span data-ttu-id="2f83b-250">图 15</span><span class="sxs-lookup"><span data-stu-id="2f83b-250">Figure 15</span></span>  
> <span data-ttu-id="2f83b-251">"网络条件"选项卡上的"用户代理"菜单</span><span class="sxs-lookup"><span data-stu-id="2f83b-251">The User Agent menu in the Network Conditions tab</span></span>  
> !["网络条件"选项卡上的"用户代理"菜单][ImageUserAgentNetworkConditionsTab]  

<span data-ttu-id="2f83b-253">若要访问**网络条件，**[请打开命令菜单][DevToolsCommandMenuIndex]，并运行 `Show Network Conditions` 该命令。</span><span class="sxs-lookup"><span data-stu-id="2f83b-253">To access **Network Conditions**, [open the Command Menu][DevToolsCommandMenuIndex] and run the `Show Network Conditions` command.</span></span>  

> [!NOTE]
> <span data-ttu-id="2f83b-254">你还可以在 [设备模式下设置用户代理字符串][DevToolsDeviceModeIndex]。</span><span class="sxs-lookup"><span data-stu-id="2f83b-254">You may also [set User-Agent strings in Device Mode][DevToolsDeviceModeIndex].</span></span>  

<span data-ttu-id="2f83b-255">Chromium [问题#1029031][crbug1029031]</span><span class="sxs-lookup"><span data-stu-id="2f83b-255">Chromium issue [#1029031][crbug1029031]</span></span>  

### <span data-ttu-id="2f83b-256">"Audits"面板更新</span><span class="sxs-lookup"><span data-stu-id="2f83b-256">Audits panel updates</span></span>  

#### <span data-ttu-id="2f83b-257">新的配置 UI</span><span class="sxs-lookup"><span data-stu-id="2f83b-257">New configuration UI</span></span>  

<span data-ttu-id="2f83b-258">配置 UI 具有新的响应式设计，而且已经简化了控制选项。</span><span class="sxs-lookup"><span data-stu-id="2f83b-258">The configuration UI has a new, responsive design, and the throttling configuration options have been simplified.</span></span>  <span data-ttu-id="2f83b-259">有关 ["约定 UI"更改的详细信息，请参阅][GitHubGoogleChromeDevToolsAuditsPanelThrottling] "审批面板"视图。</span><span class="sxs-lookup"><span data-stu-id="2f83b-259">See [Audits Panel Throttling][GitHubGoogleChromeDevToolsAuditsPanelThrottling] for more information on the throttling UI changes.</span></span>  

> ##### <span data-ttu-id="2f83b-260">图 16</span><span class="sxs-lookup"><span data-stu-id="2f83b-260">Figure 16</span></span>  
> <span data-ttu-id="2f83b-261">新的配置 UI</span><span class="sxs-lookup"><span data-stu-id="2f83b-261">The new configuration UI</span></span>  
> ![新的配置 UI][ImageConfigurationUI]  

### <span data-ttu-id="2f83b-263">范围选项卡更新</span><span class="sxs-lookup"><span data-stu-id="2f83b-263">Coverage tab updates</span></span>  

#### <span data-ttu-id="2f83b-264">每个功能或每块覆盖模式</span><span class="sxs-lookup"><span data-stu-id="2f83b-264">Per-function or per-block coverage modes</span></span>  

<span data-ttu-id="2f83b-265">"[封面"选项卡具有][DevToolsCoverageIndex]新的下拉菜单，允许您指定是否应为每个函数或每个块收集代码**覆盖数据**。 **per function**</span><span class="sxs-lookup"><span data-stu-id="2f83b-265">The [Coverage tab][DevToolsCoverageIndex] has a new dropdown menu that lets you specify whether code coverage data should be collected **per function** or **per block**.</span></span>  <span data-ttu-id="2f83b-266">**每个块** 覆盖范围更加详细，同样也更加收集开环。</span><span class="sxs-lookup"><span data-stu-id="2f83b-266">**Per block** coverage is more detailed but also far more expensive to collect.</span></span>  <span data-ttu-id="2f83b-267">默认情况下，DevTools **使用每个** 函数覆盖。</span><span class="sxs-lookup"><span data-stu-id="2f83b-267">DevTools uses **per function** coverage by default now.</span></span>  

> [!CAUTION]
> <span data-ttu-id="2f83b-268">你可能会看到大型代码覆盖 HTML 文件的差别，具体取决于是每个函数还**是\*\*\*\*每个块模式使用**。</span><span class="sxs-lookup"><span data-stu-id="2f83b-268">You may see large code coverage differences in HTML files depending on whether you use **per function** or **per block** mode.</span></span>  <span data-ttu-id="2f83b-269">使用每个 **功能模式** 时，HTML 文件中的内联脚本将被作为函数处理。</span><span class="sxs-lookup"><span data-stu-id="2f83b-269">When using **per function** mode, inline scripts in HTML files are treated as functions.</span></span>  <span data-ttu-id="2f83b-270">如果该脚本在所有时运行，则 DevTools 将整个脚本标记为使用代码。</span><span class="sxs-lookup"><span data-stu-id="2f83b-270">If the script runs at all then DevTools marks the entire script as used code.</span></span>  <span data-ttu-id="2f83b-271">仅当脚本未在全部运行时，它将该脚本标记为未使用的代码时。</span><span class="sxs-lookup"><span data-stu-id="2f83b-271">Only if the script does not run at all does DevTools mark the script as unused code.</span></span>  

> ##### <span data-ttu-id="2f83b-272">图 17</span><span class="sxs-lookup"><span data-stu-id="2f83b-272">Figure 17</span></span>  
> <span data-ttu-id="2f83b-273">封面模式下拉菜单</span><span class="sxs-lookup"><span data-stu-id="2f83b-273">The coverage mode dropdown menu</span></span>  
> ![封面模式下拉菜单][ImageCoverageMode]  

#### <span data-ttu-id="2f83b-275">只有页面重新加载必须发出覆盖范围</span><span class="sxs-lookup"><span data-stu-id="2f83b-275">Coverage must now be initiated by a page reload</span></span>  

<span data-ttu-id="2f83b-276">由于不可靠而删除不带页面重新加载的代码覆盖范围已被删除。</span><span class="sxs-lookup"><span data-stu-id="2f83b-276">Toggling code coverage without a page reload has been removed because the coverage data was unreliable.</span></span>  <span data-ttu-id="2f83b-277">例如，如果运行时很长，并且 V8 垃圾收集器已将其清理，则函数可以报告为未使用。</span><span class="sxs-lookup"><span data-stu-id="2f83b-277">For example, a function may be reported as unused if the runtime was a long time ago and the V8 garbage collector has cleaned it up.</span></span>  

<span data-ttu-id="2f83b-278">Chromium [问题#1004203][crbug1004203]</span><span class="sxs-lookup"><span data-stu-id="2f83b-278">Chromium issue [#1004203][crbug1004203]</span></span>  

## <span data-ttu-id="2f83b-279">下载 Microsoft Edge 预览频道</span><span class="sxs-lookup"><span data-stu-id="2f83b-279">Download the Microsoft Edge preview channels</span></span>  

<span data-ttu-id="2f83b-280">如果你使用的是 Windows 或 macOS，请考虑使用 [ Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels] 作为默认开发浏览器。</span><span class="sxs-lookup"><span data-stu-id="2f83b-280">If you are on Windows or macOS, consider using the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] as your default development browser.</span></span>  <span data-ttu-id="2f83b-281">预览频道使你能够访问最新的 DevTools 功能。</span><span class="sxs-lookup"><span data-stu-id="2f83b-281">The preview channels give you access to the latest DevTools features.</span></span>  

## <span data-ttu-id="2f83b-282">与 Microsoft Edge DevTools 团队联系</span><span class="sxs-lookup"><span data-stu-id="2f83b-282">Getting in touch with Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!--<<../../_shared/devtools-feedback.md>> -->

<!--<<../../_shared/canary.md>> -->

<!--<<../../_shared/discover.md>> -->

<!-- image links -->  

[ImagePerformanceToolKeyboardReaderImprovements]: ../../images/2019/12/a11y-performance-tool.msft.gif "图 1：DevTools 中的性能工具，可通过键盘导航和屏幕阅读器改进"  
[ImageLocalizedGerman]: ../../images/2019/12/localized-devtools.msft.png "图 2：常规工作区中的 DevTools"  
[ImageHintsTabWebhintExtension]: ../../images/2019/12/webhint-browser-extension.msft.png "图 3：安装 Web hint 浏览器扩展时 Microsoft Edge DevTools 中的"提示"选项卡"  
[Image3DView]: ../../images/2019/12/3dview.msft.png "图 4：Microsoft Edge 开发工具中的 3D 视图"  
[ImageElementsVisualStudioCode]: ../../images/2019/12/elements-for-edge.msft.png "图 5：使用 Microsoft Edge 扩展的元素 ，VS 代码中的元素工具"  
[ImageDebuggerExtensionVisualStudioCode]: ../../images/2019/12/vscode-debugger.msft.png "图 6：使用 VS 代码的 Microsoft Edge 扩展的调试程序"  
[ImageWebhintVisualStudioCodeExtensionWorkspace]: ../../images/2019/12/webhint-vscode-extension.msft.png "图 7：Webhint VS 代码扩展分析 VS 代码中的 .tsx 文件"  
[ImageVisualStudioLaunchWebApp]: ../../images/2019/12/vs.msft.png "图 8：Visual Studio并通过在 Microsoft Edge Canary、Dev 或 Beta 中启动你的 Web 应用的选项"  
[ImageTrackingPrevention]: ../../images/2019/12/tracking-prevention.msft.png "图 9：跟踪阻止对跟踪器的存储的访问权限时，主机中的邮件"  
[ImageConsoleRedeclarationFails]: ../../images/2019/12/letbefore.msft.png "图 10：Microsoft Edge 79 中的主机显示了我们用于回收失败"  
[ImageConsoleRedeclarationSucceeds]: ../../images/2019/12/letafter.msft.png "图 11：Microsoft Edge 80 中的主机显示这是允许回收成功的"  
[ImageRequestInitiatorChain]: ../../images/2019/12/initiators.msft.png "图 12："指发器"选项卡中的请求发度器中链接"  
[ImageOverviewPaneInspectedResource]: ../../images/2019/12/overview.msft.png "图 13："概述"窗格突出显示检查的资源"  
[ImagePathNetworkPanel]: ../../images/2019/12/columns.msft.png "图 14："网络"面板中的新路径和 URL 列"  
[ImageUserAgentNetworkConditionsTab]: ../../images/2019/12/useragent.msft.png "图 15："网络条件"选项卡中的"用户代理"菜单"  
[ImageConfigurationUI]: ../../images/2019/12/start.msft.png "图 16：新的配置 UI"  
[ImageCoverageMode]: ../../images/2019/12/modes.msft.png "图 17："覆盖模式"下拉菜单"  

<!--[ImageDwarfPoweredWebAssemblyDebugging]: ../../images/2019/12/wasm.msft.png "Figure: The new DWARF-powered WebAssembly debugging"  -->

<!-- links -->  

[DevToolsCommandMenuIndex]: ../../../command-menu/index.md "使用 Microsoft Edge 开发人员工具命令菜单运行命令"  
[DevToolsCoverageIndex]: ../../../coverage/index.md "在 Microsoft Edge DevTools 中，使用"覆盖"选项卡查找未使用的 JavaScript 和 CSS 代码"  
[DevToolsDeviceModeIndex]: ../../../device-mode/index.md#simulate-a-mobile-viewport "模拟移动版视区 - 在 Microsoft Edge DevTools 中模拟移动设备和设备模式"  
[DevToolsNetworkIndex]: ../../../network/index.md "检查 Microsoft Edge DevTools 中的网络活动"  
[DevToolsNetworkReferenceViewInitiatorsDependencies]: ../../../network/reference.md#view-initiators-and-dependencies "查看初级指示器和依赖关系 - 网络分析参考"  
[DevGuideEdgeHtmlWhatsNew]: ../../../../dev-guide/whats-new.md "EdgeHTML 中的新增功能"  
[VisualStudioCodeDebuggerEdgeExtension]: ../../../../visual-studio-code/debugger-for-edge.md "Microsoft Edge 的调试程序"  
[VisualStudioCodeElementEdgeExtension]: ../../../../visual-studio-code/elements-for-edge.md "Microsoft Edge 元素与代码扩展"  

<!--  [201912Webassembly]: webassembly.md "Improved WebAssembly debugging in Microsoft Edge DevTools"  -->  

[crbug842488]: https://crbug.com/842488 "842488 - 将"初始指示人"字段添加到"页眉"选项卡 -"监视""  
[crbug988253]: https://crbug.com/988253 "988253 - Bug DevTools - 网络请求和时间线图之间无关联 - 监视"  
[crbug993366]: https://crbug.com/993366 "993366 - 请在网络请求列表中显示 URL 的路径部分 - 监视器"  
[crbug1004193]: https://crbug.com/1004193 "1004193 - V8 的 REPL 模式 - 监视"  
[crbug1004203]: https://crbug.com/1004203 "1004203 - 监视"  
[crbug1029031]: https://crbug.com/1029031 "1029031 - UA 过期的字符串 - 监视器" 
[crbug963183]: https://crbug.com/963183 "963183 - DevTools 不符合 WCAG 兼容性"
[crbug941561]: https://crbug.com/941561 "941561 - DevTools 的本地化能力"
[crbug987787]: https://crbug.com/987787 "987787 - Dom 3D 视图"

[AccessibilityInsights]: https://aka.ms/a11yinsights "辅助功能见解"  

[DwarfHome]: https://dwarfstd.org "Dwarf 主页"  
[GitHubGoogleChromeDevToolsAuditsPanelThrottling]: https://github.com/GoogleChrome/lighthouse/blob/master/docs/throttling.md#devtools-audits-panel-throttling "DevTools 的审计审计面板决定 - GoogleChrome/lighthouse |GitHub"  
[GitHubMicrosoftDocsEdgeDeveloperNewIssue]: https://aka.ms/edgedevtoolsdocs/feedback "新问题 - MicrosoftDocs/edge-developer"  
[MicrosoftEdgePreviewChannels]: https://aka.ms/microsoftedge "Microsoft Edge 预览频道"  
[MicrosoftEdgeInsiderAddons]: https://aka.ms/webhint/edge-extension "Microsoft Edge Insider Addons"  
[MicrosoftVisualStudio]: https://aka.ms/vs "Visual Studio"  
[MicrosoftVisualStudioBlogDebugJavascript]: https://aka.ms/vs/debug-edge "从 Microsoft Edge 中调试 Microsoft Edge 中的 JavaScript 初Visual Studio |Visual Studio客"  
[MicrosoftVisualStudioDownloads]: https://aka.ms/vs/download "下载 Visual Studio 2019 for Windows \& Mac"  
[MDNDocumentObjectModel]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model "文档对象模型 (DOM) |MDN"  
[MDNZIndex]: https://developer.mozilla.org/docs/Web/CSS/z-index "z-index |MDN"  
[PostTweetEdgeDevTools]: https://aka.ms/tweet/edgedevtools "@EdgeDevTools | 发布推文"  
[EdgeDevToolsTwitterAccount]: https://aka.ms/twitter/edgedevtools "@EdgeDevTools Twitter 帐户"
[VisualStudioCode]: https://aka.ms/vscode "Visual Studio代码"  
[VisualStudioMarketplaceDebuggerEdge]: https://aka.ms/debugger4code "Microsoft Edge 调试程序 - 使用比Visual Studio出版"  
[VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension]: https://aka.ms/elements4code "Microsoft Edge \ (Chromium\) - Visual Studio Marketplace 的元素"  
[VisualStudioMarketplaceWebhintExtension]: https://aka.ms/webhint4code "webhint - Visual Studio 商场"
[Webhint]: https://aka.ms/webhint "Webhint"  
[WebhintBrowserExtension]: https://aka.ms/webhint/browser-extension "Webhint 浏览器扩展 |Webhint 文档"  
[WebhintVisualStudioCodeExtension]: https://aka.ms/webhint/code-extension "Webhint 代码扩展 |Webhint 文档"  
[TrackingPrevention]: https://aka.ms/microsoftedge/tracking-prevention-blog "在 Microsoft Edge 博客文章中提进跟踪防护"
[TheWebWeWant]: https://aka.ms/webwewant "我们想要的网络"

> [!NOTE]
> <span data-ttu-id="2f83b-339">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="2f83b-339">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="2f83b-340">原始页面是在此处找到的，由[here](https://developers.google.com/web/updates/2019/12/devtools/index)[Kayce Basques][KayceBasques] \ (Technical Writer、Chrome DevTools 和 & Lighthouse\) 编写。</span><span class="sxs-lookup"><span data-stu-id="2f83b-340">The original page is found [here](https://developers.google.com/web/updates/2019/12/devtools/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools & Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="2f83b-342">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="2f83b-342">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
