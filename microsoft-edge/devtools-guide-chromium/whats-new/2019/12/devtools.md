---
title: DevTools 中的新增功能（Microsoft Edge 80）
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/20/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: ac85f0d9f8a5f112e702968b9c0aeceb05312ac1
ms.sourcegitcommit: 7e3a876ccb1f0ff3d50d4e32f03af98f780e2930
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/24/2020
ms.locfileid: "10591392"
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








# <span data-ttu-id="757dc-103">DevTools 中的新增功能（Microsoft Edge 80）</span><span class="sxs-lookup"><span data-stu-id="757dc-103">What's new in DevTools (Microsoft Edge 80)</span></span>   



## <span data-ttu-id="757dc-104">Microsoft Edge DevTools 团队的公告</span><span class="sxs-lookup"><span data-stu-id="757dc-104">Announcements from the Microsoft Edge DevTools team</span></span>  

<span data-ttu-id="757dc-105">以下部分是您可能已错过的 Microsoft Edge DevTools 团队的公告列表！</span><span class="sxs-lookup"><span data-stu-id="757dc-105">The following sections are a list of announcements you may have missed from the Microsoft Edge DevTools team!</span></span> <span data-ttu-id="757dc-106">请查看这些功能，尝试 DevTools、VS 代码扩展等中的新功能。</span><span class="sxs-lookup"><span data-stu-id="757dc-106">Check them out to try new features in the DevTools, VS Code extensions, and more.</span></span>  <span data-ttu-id="757dc-107">若要随时了解开发人员工具中的所有最新功能和最新功能，请下载[Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels]并[在 Twitter 上关注我们][EdgeDevToolsTwitterAccount]。</span><span class="sxs-lookup"><span data-stu-id="757dc-107">To stay up to date on all the latest and greatest features in your developer tools, download the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] and [follow us on Twitter][EdgeDevToolsTwitterAccount].</span></span>  

### <span data-ttu-id="757dc-108">对 DevTools 的辅助功能改进</span><span class="sxs-lookup"><span data-stu-id="757dc-108">Accessibility improvements to the DevTools</span></span>  

<span data-ttu-id="757dc-109">DevTools 团队已向 Chromium 提供170更改，以解决 DevTools 中的高影响力颜色对比度、键盘和屏幕阅读器问题。</span><span class="sxs-lookup"><span data-stu-id="757dc-109">The DevTools team has contributed 170 changes to Chromium to address high-impact color contrast, keyboard, and screen reader issues in the DevTools.</span></span>  <span data-ttu-id="757dc-110">每个构建 web 的开发人员都应该能够使用 DevTools。</span><span class="sxs-lookup"><span data-stu-id="757dc-110">Every developer building the web should be able to use the DevTools.</span></span>  

> ##### <span data-ttu-id="757dc-111">图 1</span><span class="sxs-lookup"><span data-stu-id="757dc-111">Figure 1</span></span>  
> <span data-ttu-id="757dc-112">DevTools 中的性能工具改进了键盘导航和屏幕阅读器</span><span class="sxs-lookup"><span data-stu-id="757dc-112">The Performance tool in the DevTools with the keyboard navigation and screen reader improvements</span></span>  
> ![DevTools 中的性能工具改进了键盘导航和屏幕阅读器][ImagePerformanceToolKeyboardReaderImprovements]  

<span data-ttu-id="757dc-114">希望了解如何让您的网页对所有用户都易于访问？</span><span class="sxs-lookup"><span data-stu-id="757dc-114">Want to learn how to make your web page accessible to all of your users?</span></span>  <span data-ttu-id="757dc-115">下载 Microsoft Edge 的[辅助功能见解][AccessibilityInsights]和[webhint][WebhintBrowserExtension]扩展以开始使用。</span><span class="sxs-lookup"><span data-stu-id="757dc-115">Download the [Accessibility Insights][AccessibilityInsights] and [webhint][WebhintBrowserExtension] extensions for Microsoft Edge to get started.</span></span>  

<span data-ttu-id="757dc-116">如果您使用屏幕阅读器或键盘在 DevTools 中导航，请向我们发送您的反馈[发推至][PostTweetEdgeDevTools]，或单击 "[反馈](#feedback)" 图标！</span><span class="sxs-lookup"><span data-stu-id="757dc-116">If you use screen readers or the keyboard to navigate around the DevTools, send us your feedback by [tweeting][PostTweetEdgeDevTools] at us or clicking the [Feedback](#feedback) icon!</span></span>  

<span data-ttu-id="757dc-117">Chromium 问题[#963183][crbug963183]</span><span class="sxs-lookup"><span data-stu-id="757dc-117">Chromium issue [#963183][crbug963183]</span></span>  

### <span data-ttu-id="757dc-118">使用其他语言的 DevTools</span><span class="sxs-lookup"><span data-stu-id="757dc-118">Using the DevTools in other languages</span></span>  

<span data-ttu-id="757dc-119">许多开发人员使用其他开发人员工具，如 StackOverflow 和 VS 代码，采用其母语，而不仅仅是英语。</span><span class="sxs-lookup"><span data-stu-id="757dc-119">Many developers use other developer tools, like StackOverflow and VS Code, in their native language, not just in English.</span></span>  <span data-ttu-id="757dc-120">我们很高兴宣布 DevTools 的本地化，您现在可以使用英语之外的10种语言中的一种：</span><span class="sxs-lookup"><span data-stu-id="757dc-120">We’re excited to announce localization for the DevTools, which you are now able to use in one of 10 languages besides English:</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="757dc-121">中文 \ （简体）- &#20013;&#25991;&#65288;&#31616;&#20307;&#65289;</span><span class="sxs-lookup"><span data-stu-id="757dc-121">Chinese \(Simplified\) - &#20013;&#25991;&#65288;&#31616;&#20307;&#65289;</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="757dc-122">中文 \ （繁体）- &#20013;&#25991;&#65288;&#32321;&#39636;&#65289;</span><span class="sxs-lookup"><span data-stu-id="757dc-122">Chinese \(Traditional\) - &#20013;&#25991;&#65288;&#32321;&#39636;&#65289;</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      <span data-ttu-id="757dc-123">法语-fran&#231;ais</span><span class="sxs-lookup"><span data-stu-id="757dc-123">French – fran&#231;ais</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="757dc-124">德语-德语</span><span class="sxs-lookup"><span data-stu-id="757dc-124">German - deutsch</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      <span data-ttu-id="757dc-125">意大利语-意大利语</span><span class="sxs-lookup"><span data-stu-id="757dc-125">Italian - italiano</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="757dc-126">日语- &#26085;&#26412;&#35486;</span><span class="sxs-lookup"><span data-stu-id="757dc-126">Japanese - &#26085;&#26412;&#35486;</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      <span data-ttu-id="757dc-127">朝鲜语- &#54620;&#44397;&#50612;</span><span class="sxs-lookup"><span data-stu-id="757dc-127">Korean - &#54620;&#44397;&#50612;</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="757dc-128">葡萄牙语-portugu&#234;s</span><span class="sxs-lookup"><span data-stu-id="757dc-128">Portuguese - portugu&#234;s</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      <span data-ttu-id="757dc-129">俄语–  &#1088;&#1091;&#1089;&#1089;&#1082;&#1080;&#1081;</span><span class="sxs-lookup"><span data-stu-id="757dc-129">Russian – &#1088;&#1091;&#1089;&#1089;&#1082;&#1080;&#1081;</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="757dc-130">西班牙语-espa&#241;ol</span><span class="sxs-lookup"><span data-stu-id="757dc-130">Spanish - espa&#241;ol</span></span>
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

<span data-ttu-id="757dc-131">导航到 `edge://flags` "启用已**本地化的开发人员工具**" 标志并将其设置为 "**启用**"。</span><span class="sxs-lookup"><span data-stu-id="757dc-131">Navigate to `edge://flags` and set the **Enable localized Developer Tools** flag to **Enabled**.</span></span>  <span data-ttu-id="757dc-132">还将 "**开发工具" 试验**标志设置为 "**启用**"。</span><span class="sxs-lookup"><span data-stu-id="757dc-132">Also set the **Developer Tools experiments** flag to **Enabled**.</span></span>  <span data-ttu-id="757dc-133">重启 Microsoft Edge 并打开 DevTools。</span><span class="sxs-lookup"><span data-stu-id="757dc-133">Restart Microsoft Edge and open the DevTools.</span></span>  <!-- Press `F1` in the DevTools or go to Settings > Experiments and check the **Match browser language** checkbox.  -->  <span data-ttu-id="757dc-134">DevTools 与你用于 Microsoft Edge 的语言相匹配 `edge://settings/languages` 。</span><span class="sxs-lookup"><span data-stu-id="757dc-134">The DevTools match the language you use for Microsoft Edge in `edge://settings/languages`.</span></span>  

> ##### <span data-ttu-id="757dc-135">图 2</span><span class="sxs-lookup"><span data-stu-id="757dc-135">Figure 2</span></span>  
> <span data-ttu-id="757dc-136">德语中的 DevTools</span><span class="sxs-lookup"><span data-stu-id="757dc-136">The DevTools in German</span></span>  
> ![德语中的 DevTools][ImageLocalizedGerman]  

<span data-ttu-id="757dc-138">如果您想要使用的 DevTools 语言与可用的语言不同，请[tweet][PostTweetEdgeDevTools] ，或单击 "[反馈](#feedback)" 图标。</span><span class="sxs-lookup"><span data-stu-id="757dc-138">If you want to use the DevTools in a different language than the ones that are available, [tweet][PostTweetEdgeDevTools] at us or click the [Feedback](#feedback) icon.</span></span>  

<span data-ttu-id="757dc-139">Chromium 问题[#941561][crbug941561]</span><span class="sxs-lookup"><span data-stu-id="757dc-139">Chromium issue [#941561][crbug941561]</span></span>  

### <span data-ttu-id="757dc-140">webhint Microsoft Edge 扩展</span><span class="sxs-lookup"><span data-stu-id="757dc-140">webhint Microsoft Edge extension</span></span>  

<span data-ttu-id="757dc-141">Webhint Microsoft Edge 扩展使你能够轻松地浏览网页并在 DevTools 中获取有关辅助功能、浏览器兼容性、安全性、性能等的反馈。</span><span class="sxs-lookup"><span data-stu-id="757dc-141">The webhint Microsoft Edge extension allows you to easily scan your web page and get feedback on accessibility, browser compatibility, security, performance, and more within the DevTools.</span></span>  <span data-ttu-id="757dc-142">阅读详细信息 [https://webhint.io][Webhint] 。</span><span class="sxs-lookup"><span data-stu-id="757dc-142">Read more at [https://webhint.io][Webhint].</span></span>  

> ##### <span data-ttu-id="757dc-143">图 3</span><span class="sxs-lookup"><span data-stu-id="757dc-143">Figure 3</span></span>  
> <span data-ttu-id="757dc-144">安装 webhint 浏览器扩展时，DevTools 中的 "提示" 选项卡</span><span class="sxs-lookup"><span data-stu-id="757dc-144">The Hints tab in the DevTools when the webhint browser extension is installed</span></span>  
> ![安装 webhint 浏览器扩展时，DevTools 中的 "提示" 选项卡][ImageHintsTabWebhintExtension]  

<span data-ttu-id="757dc-146">[在 Microsoft Edge 中尝试 webhint 浏览器扩展][MicrosoftEdgeInsiderAddons]。</span><span class="sxs-lookup"><span data-stu-id="757dc-146">[Try the webhint browser extension in Microsoft Edge][MicrosoftEdgeInsiderAddons].</span></span>  <span data-ttu-id="757dc-147">安装扩展后，打开 DevTools 并选择 "提示" 选项卡。 在此处，运行可自定义的网站扫描。</span><span class="sxs-lookup"><span data-stu-id="757dc-147">Once you install the extension, open the DevTools and select the Hints tab.  From here, run a customizable site scan.</span></span>  <span data-ttu-id="757dc-148">请转到[webhint.io][WebhintBrowserExtension]以了解更多信息。</span><span class="sxs-lookup"><span data-stu-id="757dc-148">Head over to [webhint.io][WebhintBrowserExtension] to learn more.</span></span>

### <span data-ttu-id="757dc-149">3D 视图</span><span class="sxs-lookup"><span data-stu-id="757dc-149">3D View</span></span>  

<span data-ttu-id="757dc-150">通过浏览[文档对象模型 \ （DOM \）][MDNDocumentObjectModel]或[z 索引][MDNZIndex]堆栈上下文，使用**3d 视图**调试 web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="757dc-150">Use the **3D View** to debug your web application by navigating through the [Document Object Model \(DOM\)][MDNDocumentObjectModel] or the [z-index][MDNZIndex] stacking context.</span></span>  

> ##### <span data-ttu-id="757dc-151">图 4</span><span class="sxs-lookup"><span data-stu-id="757dc-151">Figure 4</span></span>  
> <span data-ttu-id="757dc-152">DevTools 中的3D 视图</span><span class="sxs-lookup"><span data-stu-id="757dc-152">The 3D View in the DevTools</span></span>  
> ![DevTools 中的3D 视图][Image3DView]  

<span data-ttu-id="757dc-154">若要访问3D 视图，请导航到 `edge://flags` 并确保 "**开发人员工具实验**" 标志设置为 "**已启用**"。</span><span class="sxs-lookup"><span data-stu-id="757dc-154">To access the 3D View, navigate to `edge://flags` and ensure that the **Developer Tools experiments** flag is set to **Enabled**.</span></span>  <span data-ttu-id="757dc-155">重启 Microsoft Edge 并打开 DevTools。</span><span class="sxs-lookup"><span data-stu-id="757dc-155">Restart Microsoft Edge and open the DevTools.</span></span>  <span data-ttu-id="757dc-156">按 `F1` DevTools 或转到 "**设置**"，导航到 "**实验**" 部分，然后选中 "**启用3d 视图**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="757dc-156">Press `F1` in the DevTools or go to **Settings**, navigate to **Experiments** section, and check the **Enable 3D View** checkbox.</span></span>  <span data-ttu-id="757dc-157">现在，请按 `Ctrl`  +  `Shift`  +  `P` ，在**3d 视图**中键入，然后选择 "**显示3d 视图**"。</span><span class="sxs-lookup"><span data-stu-id="757dc-157">Now, press `Ctrl` + `Shift` + `P`, type in **3D View** and select **Show 3D View**.</span></span>  

<span data-ttu-id="757dc-158">我们正在处理 UI 并向3D 视图添加更多功能，请向我们发送您的[反馈](#feedback)。</span><span class="sxs-lookup"><span data-stu-id="757dc-158">We're working on the UI and adding more functionality to the 3D View so please send us your [feedback](#feedback).</span></span>  

<span data-ttu-id="757dc-159">Chromium 问题[#987787][crbug987787]</span><span class="sxs-lookup"><span data-stu-id="757dc-159">Chromium issue [#987787][crbug987787]</span></span>

### <span data-ttu-id="757dc-160">Visual Studio 代码扩展</span><span class="sxs-lookup"><span data-stu-id="757dc-160">Visual Studio Code extensions</span></span>  

<span data-ttu-id="757dc-161">DevTools 团队还发布了一些[Visual Studio 代码 \ （VS 代码 \）][VisualStudioCode]的扩展，可让你直接从文本编辑器使用 DevTools 的强大功能！</span><span class="sxs-lookup"><span data-stu-id="757dc-161">The DevTools team has also released some extensions for [Visual Studio Code \(VS Code\)][VisualStudioCode] that let you use the power of the DevTools directly from your text editor!</span></span> <span data-ttu-id="757dc-162">请查看下面的分机：</span><span class="sxs-lookup"><span data-stu-id="757dc-162">Check out the extensions below:</span></span>  

#### <span data-ttu-id="757dc-163">Microsoft Edge 元素</span><span class="sxs-lookup"><span data-stu-id="757dc-163">Elements for Microsoft Edge</span></span>  

<span data-ttu-id="757dc-164">通过添加[Microsoft Edge \ （Chromium \）][VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension]和代码扩展的元素，从 VS 代码中使用 "元素" 工具。</span><span class="sxs-lookup"><span data-stu-id="757dc-164">Use the Elements tool from within VS Code by adding the [Elements for Microsoft Edge \(Chromium\)][VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension] VS Code extension.</span></span>  

> ##### <span data-ttu-id="757dc-165">图 5</span><span class="sxs-lookup"><span data-stu-id="757dc-165">Figure 5</span></span>  
> <span data-ttu-id="757dc-166">VS 代码中的 "元素" 工具使用 Microsoft Edge 扩展的元素</span><span class="sxs-lookup"><span data-stu-id="757dc-166">The Elements tool in VS Code using the Elements for Microsoft Edge extension</span></span>  
> ![VS 代码中的 "元素" 工具使用 Microsoft Edge 扩展的元素][ImageElementsVisualStudioCode]  

<span data-ttu-id="757dc-168">有关详细信息，请查看[Microsoft Edge 的元素与代码扩展][VisualStudioCodeElementEdgeExtension]。</span><span class="sxs-lookup"><span data-stu-id="757dc-168">For more information, check out [Elements for Microsoft Edge VS Code extension][VisualStudioCodeElementEdgeExtension].</span></span>  

#### <span data-ttu-id="757dc-169">Microsoft Edge 调试器</span><span class="sxs-lookup"><span data-stu-id="757dc-169">Debugger for Microsoft Edge</span></span>  

<span data-ttu-id="757dc-170">借助[适用于 Microsoft edge][VisualStudioMarketplaceDebuggerEdge]和代码扩展的调试器，在 microsoft Edge 中直接通过 VS 代码调试运行 JavaScript！</span><span class="sxs-lookup"><span data-stu-id="757dc-170">With the [Debugger for Microsoft Edge][VisualStudioMarketplaceDebuggerEdge] VS Code extension, debug JavaScript running in Microsoft Edge directly from VS Code!</span></span>  

> ##### <span data-ttu-id="757dc-171">图 6</span><span class="sxs-lookup"><span data-stu-id="757dc-171">Figure 6</span></span>  
> <span data-ttu-id="757dc-172">VS 代码中的 Microsoft Edge 扩展调试器</span><span class="sxs-lookup"><span data-stu-id="757dc-172">The Debugger for Microsoft Edge Extension in VS Code</span></span>  
> ![VS 代码中的 Microsoft Edge 扩展调试器][ImageDebuggerExtensionVisualStudioCode]  

<span data-ttu-id="757dc-174">有关详细信息，请参阅[如何从 VS 代码调试 Microsoft Edge][VisualStudioCodeDebuggerEdgeExtension]。</span><span class="sxs-lookup"><span data-stu-id="757dc-174">For more information, check out [how to debug Microsoft Edge from VS Code][VisualStudioCodeDebuggerEdgeExtension].</span></span>  

#### <span data-ttu-id="757dc-175">webhint</span><span class="sxs-lookup"><span data-stu-id="757dc-175">webhint</span></span>  

<span data-ttu-id="757dc-176">编写时， [webhint][VisualStudioMarketplaceWebhintExtension]和代码扩展用于 `webhint` 改进网页！</span><span class="sxs-lookup"><span data-stu-id="757dc-176">The [webhint][VisualStudioMarketplaceWebhintExtension] VS Code extension uses `webhint` to improve your web page while you're writing it!</span></span> <span data-ttu-id="757dc-177">此扩展基于分析对工作区文件运行和报告诊断 `webhint` 。</span><span class="sxs-lookup"><span data-stu-id="757dc-177">This extension runs and reports diagnostics on your workspace files based on `webhint` analysis.</span></span>  

> ##### <span data-ttu-id="757dc-178">图 7</span><span class="sxs-lookup"><span data-stu-id="757dc-178">Figure 7</span></span>  
> <span data-ttu-id="757dc-179">在 VS 代码中分析 tsx 文件的 webhint 与代码扩展</span><span class="sxs-lookup"><span data-stu-id="757dc-179">The webhint VS Code extension analyzing a .tsx file in VS Code</span></span>  
> ![在 VS 代码中分析 tsx 文件的 webhint 与代码扩展][ImageWebhintVisualStudioCodeExtensionWorkspace]  

<span data-ttu-id="757dc-181">[了解有关 VS 代码 webhint 扩展的详细信息][WebhintVisualStudioCodeExtension]。</span><span class="sxs-lookup"><span data-stu-id="757dc-181">[Learn more about the VS Code webhint extension][WebhintVisualStudioCodeExtension].</span></span>  

### <span data-ttu-id="757dc-182">Visual Studio 集成</span><span class="sxs-lookup"><span data-stu-id="757dc-182">Visual Studio integration</span></span>
<span data-ttu-id="757dc-183">在 Visual Studio 2019 版本16.2 或更高版本中，使用 Visual Studio 调试器调试在 Microsoft Edge 中运行的 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="757dc-183">In Visual Studio 2019 version 16.2 or later, use the Visual Studio debugger to debug JavaScript running in Microsoft Edge.</span></span>  <span data-ttu-id="757dc-184">[下载 Visual Studio 2019][MicrosoftVisualStudioDownloads]以试用此功能！</span><span class="sxs-lookup"><span data-stu-id="757dc-184">[Download Visual Studio 2019][MicrosoftVisualStudioDownloads] to try this feature out!</span></span>  

> ##### <span data-ttu-id="757dc-185">图 8</span><span class="sxs-lookup"><span data-stu-id="757dc-185">Figure 8</span></span>  
> <span data-ttu-id="757dc-186">带有在 Microsoft Edge 的 "应用"、"开发" 或 "Beta" 中启动 web 应用选项的 Visual Studio</span><span class="sxs-lookup"><span data-stu-id="757dc-186">Visual Studio with the option to launch your web app in Microsoft Edge Canary, Dev, or Beta</span></span>  
> ![带有在 Microsoft Edge 的 "应用"、"开发" 或 "Beta" 中启动 web 应用选项的 Visual Studio][ImageVisualStudioLaunchWebApp]  

<span data-ttu-id="757dc-188">[阅读我们的博客文章，了解如何从 Visual Studio 调试 Microsoft Edge][MicrosoftVisualStudioBlogDebugJavascript]。</span><span class="sxs-lookup"><span data-stu-id="757dc-188">[Read our blog post to learn how to debug Microsoft Edge from Visual Studio][MicrosoftVisualStudioBlogDebugJavascript].</span></span>  

### <span data-ttu-id="757dc-189">跟踪保护控制台消息</span><span class="sxs-lookup"><span data-stu-id="757dc-189">Tracking prevention Console messages</span></span>  

<span data-ttu-id="757dc-190">"跟踪防护" 是 Microsoft Edge 中的一项独特功能，可防止您以前未访问过的网站对您进行跟踪。</span><span class="sxs-lookup"><span data-stu-id="757dc-190">Tracking prevention is a unique feature in Microsoft Edge that protects you from being tracked by websites you haven't visited before.</span></span>  <span data-ttu-id="757dc-191">默认跟踪防护设置为平衡模式，这将阻止第三方跟踪程序和已知恶意跟踪程序，以获取平衡隐私和 web 兼容性的体验。</span><span class="sxs-lookup"><span data-stu-id="757dc-191">The default tracking prevention setting is Balanced mode, which blocks 3rd party trackers and known malicious trackers for an experience that balances privacy and web compatibility.</span></span>  <span data-ttu-id="757dc-192">若要在某些跟踪器被阻止时更深入地了解网页的兼容性，我们还在跟踪器被阻止时在控制台中添加了警告消息。</span><span class="sxs-lookup"><span data-stu-id="757dc-192">To give you more insight into the compatibility of your web page when certain trackers are blocked, we've also added warning messages in the Console when a tracker is blocked.</span></span>  

> ##### <span data-ttu-id="757dc-193">图 9</span><span class="sxs-lookup"><span data-stu-id="757dc-193">Figure 9</span></span>  
> <span data-ttu-id="757dc-194">跟踪阻止阻止跟踪对存储的访问权限时的控制台中的消息</span><span class="sxs-lookup"><span data-stu-id="757dc-194">Messages in the Console when tracking prevention blocks access to storage for a tracker</span></span>  
> ![跟踪阻止阻止跟踪对存储的访问权限时的控制台中的消息][ImageTrackingPrevention]  

<span data-ttu-id="757dc-196">[阅读有关跟踪防护和隐私和 web 兼容性之间的平衡的详细信息][TrackingPrevention]。</span><span class="sxs-lookup"><span data-stu-id="757dc-196">[Read more about tracking prevention and the balance between privacy and web compatibility][TrackingPrevention].</span></span>  

## <span data-ttu-id="757dc-197">来自 Chromium 项目的公告</span><span class="sxs-lookup"><span data-stu-id="757dc-197">Announcements from the Chromium project</span></span>  

<span data-ttu-id="757dc-198">以下各节宣布了在 Microsoft Edge 80 中提供的其他功能，这些功能由开放的源 Chromium 项目所参与。</span><span class="sxs-lookup"><span data-stu-id="757dc-198">The following sections announce additional features available in Microsoft Edge 80 that were contributed to the open source Chromium project.</span></span>  

### <span data-ttu-id="757dc-199">在控制台中支持 let 和 class redeclarations</span><span class="sxs-lookup"><span data-stu-id="757dc-199">Support for let and class redeclarations in the Console</span></span>   

<span data-ttu-id="757dc-200">现在，该控制台支持 redeclarations `let` 和 `class` 语句。</span><span class="sxs-lookup"><span data-stu-id="757dc-200">The Console now supports redeclarations of `let` and `class` statements.</span></span>  <span data-ttu-id="757dc-201">如果 web 开发人员使用控制台体验新的 JavaScript 代码，则无法重新声明。</span><span class="sxs-lookup"><span data-stu-id="757dc-201">The inability to redeclare was a common annoyance for web developers who use the Console to experiment with new JavaScript code.</span></span>  

> [!WARNING]
> <span data-ttu-id="757dc-202">`let` `class` 在控制台外或单个控制台输入中的脚本中 Redeclaring 或语句仍会导致 a `SyntaxError` 。</span><span class="sxs-lookup"><span data-stu-id="757dc-202">Redeclaring a `let` or `class` statement in a script outside of the Console or within a single Console input still causes a `SyntaxError`.</span></span>  

<span data-ttu-id="757dc-203">例如，以前，当 redeclaring 本地变量时 `let` ，控制台会引发错误：</span><span class="sxs-lookup"><span data-stu-id="757dc-203">For example, previously, when redeclaring a local variable with `let`, the Console threw an error:</span></span>  

> ##### <span data-ttu-id="757dc-204">图 10</span><span class="sxs-lookup"><span data-stu-id="757dc-204">Figure 10</span></span>  
> <span data-ttu-id="757dc-205">Microsoft Edge 79 中的控制台，显示允许重新声明失败</span><span class="sxs-lookup"><span data-stu-id="757dc-205">The Console in Microsoft Edge 79 showing that the let redeclaration fails</span></span>  
> ![Microsoft Edge 79 中的控制台，显示允许重新声明失败][ImageConsoleRedeclarationFails]  

<span data-ttu-id="757dc-207">现在，该控制台允许重新声明：</span><span class="sxs-lookup"><span data-stu-id="757dc-207">Now, the Console allows the redeclaration:</span></span>  

> ##### <span data-ttu-id="757dc-208">图 11</span><span class="sxs-lookup"><span data-stu-id="757dc-208">Figure 11</span></span>  
> <span data-ttu-id="757dc-209">Microsoft Edge 80 中的控制台，显示允许重新声明成功</span><span class="sxs-lookup"><span data-stu-id="757dc-209">The Console in Microsoft Edge 80 showing that the let redeclaration succeeds</span></span>  
> ![Microsoft Edge 80 中的控制台，显示允许重新声明成功][ImageConsoleRedeclarationSucceeds]  

<span data-ttu-id="757dc-211">Chromium 问题[#1004193][crbug1004193]</span><span class="sxs-lookup"><span data-stu-id="757dc-211">Chromium issue [#1004193][crbug1004193]</span></span>  

### <span data-ttu-id="757dc-212">改进的 WebAssembly 调试</span><span class="sxs-lookup"><span data-stu-id="757dc-212">Improved WebAssembly debugging</span></span>   

<span data-ttu-id="757dc-213">DevTools 已开始支持[DWARF 调试标准][DwarfHome]，这意味着增加了对代码执行的支持、设置断点以及解析 DevTools 中的源语言的堆栈跟踪。</span><span class="sxs-lookup"><span data-stu-id="757dc-213">DevTools has started to support the [DWARF Debugging Standard][DwarfHome], which means increased support for stepping over code, setting breakpoints, and resolving stack traces in your source languages within DevTools.</span></span>  

<!-- [TODO: Add this link back] -->  
<!--Check out [Improved WebAssembly debugging in Microsoft Edge DevTools][201912Webassembly] for the full story.  -->  

<!-- [TODO: Replace this image with screenshot in Edge] -->  
<!--
> ##### Figure  
> The new DWARF-powered WebAssembly debugging  
> ![The new DWARF-powered WebAssembly debugging][ImageDwarfPoweredWebAssemblyDebugging]  
-->  

### <span data-ttu-id="757dc-214">网络面板更新</span><span class="sxs-lookup"><span data-stu-id="757dc-214">Network panel updates</span></span>   

#### <span data-ttu-id="757dc-215">在 "启动器" 选项卡中请求启动器链</span><span class="sxs-lookup"><span data-stu-id="757dc-215">Request Initiator Chains in the Initiator tab</span></span>   

<span data-ttu-id="757dc-216">现在，你可以查看作为嵌套列表的网络请求的发起方和依赖关系。</span><span class="sxs-lookup"><span data-stu-id="757dc-216">You are now able to view the initiators and dependencies of a network request as a nested list.</span></span>  <span data-ttu-id="757dc-217">这可能会帮助你了解请求资源的原因或导致特定资源的网络活动 \ （如脚本）。</span><span class="sxs-lookup"><span data-stu-id="757dc-217">This may help you understand why a resource was requested, or what network activity a certain resource \(such as a script\) caused.</span></span>  

> ##### <span data-ttu-id="757dc-218">图 12</span><span class="sxs-lookup"><span data-stu-id="757dc-218">Figure 12</span></span>  
> <span data-ttu-id="757dc-219">"启动器" 选项卡中的请求发起人链</span><span class="sxs-lookup"><span data-stu-id="757dc-219">A Request Initiator Chain in the Initiator tab</span></span>  
> !["启动器" 选项卡中的请求发起人链][ImageRequestInitiatorChain]  

<span data-ttu-id="757dc-221">[在 "网络" 面板中记录网络活动][DevToolsNetworkIndex]后，单击资源，然后转到 "**启动器**" 选项卡以查看**请求启动器链**：</span><span class="sxs-lookup"><span data-stu-id="757dc-221">After [logging network activity in the Network panel][DevToolsNetworkIndex], click a resource and then go to the **Initiator** tab to view the **Request Initiator Chain**:</span></span>  

*   <span data-ttu-id="757dc-222">已**检查的资源**为粗体。</span><span class="sxs-lookup"><span data-stu-id="757dc-222">The **inspected resource** is bold.</span></span>  <span data-ttu-id="757dc-223">在上面的屏幕截图中， `ai.2.min.js` 是已检查的资源。</span><span class="sxs-lookup"><span data-stu-id="757dc-223">In the screenshot above, `ai.2.min.js` is the inspected resource.</span></span>  
*   <span data-ttu-id="757dc-224">已检查资源上方的资源是**启动器**。</span><span class="sxs-lookup"><span data-stu-id="757dc-224">The resources above the inspected resource are the **initiators**.</span></span>  <span data-ttu-id="757dc-225">在上面的屏幕截图中， `https://www.microsoftedgeinsider.com` 是的发起人 `ai.2.min.js` 。</span><span class="sxs-lookup"><span data-stu-id="757dc-225">In the screenshot above, `https://www.microsoftedgeinsider.com` is the initiator of `ai.2.min.js`.</span></span>  <span data-ttu-id="757dc-226">换句话说， `https://www.microsoftedgeinsider.com` 导致网络请求 `ai.2.min.js` 。</span><span class="sxs-lookup"><span data-stu-id="757dc-226">In other words, `https://www.microsoftedgeinsider.com` caused the network request for `ai.2.min.js`.</span></span>  
*   <span data-ttu-id="757dc-227">已检查资源下方的资源是**依赖关系**。</span><span class="sxs-lookup"><span data-stu-id="757dc-227">The resources below the inspected resource are the **dependencies**.</span></span>  <span data-ttu-id="757dc-228">在上面的屏幕截图中， `https://dc.services.visualstudio.com/v2/track` 是的依赖项 `ai.2.min.js` 。</span><span class="sxs-lookup"><span data-stu-id="757dc-228">In the screenshot above, `https://dc.services.visualstudio.com/v2/track` is a dependency of `ai.2.min.js`.</span></span>  <span data-ttu-id="757dc-229">换句话说， `ai.2.min.js` 导致网络请求 `https://dc.services.visualstudio.com/v2/track` 。</span><span class="sxs-lookup"><span data-stu-id="757dc-229">In other words, `ai.2.min.js` caused the network request for `https://dc.services.visualstudio.com/v2/track`.</span></span>  

> [!NOTE]
> <span data-ttu-id="757dc-230">也可以通过按住 `Shift` 网络资源并将鼠标悬停在网络资源上来访问启动器和相关性信息。</span><span class="sxs-lookup"><span data-stu-id="757dc-230">Initiator and dependency information may also be accessed by holding `Shift` and then hovering over network resources.</span></span>  <span data-ttu-id="757dc-231">请参阅[查看发起人和依赖关系][DevToolsNetworkReferenceViewInitiatorsDependencies]。</span><span class="sxs-lookup"><span data-stu-id="757dc-231">See [View initiators and dependencies][DevToolsNetworkReferenceViewInitiatorsDependencies].</span></span>  

<span data-ttu-id="757dc-232">Chromium 问题[#842488][crbug842488]</span><span class="sxs-lookup"><span data-stu-id="757dc-232">Chromium issue [#842488][crbug842488]</span></span>  

#### <span data-ttu-id="757dc-233">在概述中突出显示所选的网络请求</span><span class="sxs-lookup"><span data-stu-id="757dc-233">Highlight the selected network request in the Overview</span></span>   

<span data-ttu-id="757dc-234">单击网络资源以对其进行检查后，网络面板**现在将在**该资源周围放置一个蓝色边框。</span><span class="sxs-lookup"><span data-stu-id="757dc-234">After you click a network resource in order to inspect it, the Network panel now puts a blue border around that resource in the **Overview**.</span></span>  <span data-ttu-id="757dc-235">这可以帮助你检测网络请求在之前或之后是否比预期发生。</span><span class="sxs-lookup"><span data-stu-id="757dc-235">This is able to help you detect if the network request is happening earlier or later than expected.</span></span>  

> ##### <span data-ttu-id="757dc-236">图 13</span><span class="sxs-lookup"><span data-stu-id="757dc-236">Figure 13</span></span>  
> <span data-ttu-id="757dc-237">突出显示已检查资源的概述窗格</span><span class="sxs-lookup"><span data-stu-id="757dc-237">The Overview pane highlighting the inspected resource</span></span>  
> ![突出显示已检查资源的概述窗格][ImageOverviewPaneInspectedResource]  

<span data-ttu-id="757dc-239">Chromium 问题[#988253][crbug988253]</span><span class="sxs-lookup"><span data-stu-id="757dc-239">Chromium issue [#988253][crbug988253]</span></span>  

#### <span data-ttu-id="757dc-240">"网络" 面板中的 URL 和路径列</span><span class="sxs-lookup"><span data-stu-id="757dc-240">URL and path columns in the Network panel</span></span>   

<span data-ttu-id="757dc-241">使用 "**网络**" 面板中的 "新**路径**" 和 " **URL** " 列查看每个网络资源的绝对路径或完整 url。</span><span class="sxs-lookup"><span data-stu-id="757dc-241">Use the new **Path** and **URL** columns in the **Network** panel to see the absolute path or full URL of each network resource.</span></span>  

> ##### <span data-ttu-id="757dc-242">图 14</span><span class="sxs-lookup"><span data-stu-id="757dc-242">Figure 14</span></span>  
> <span data-ttu-id="757dc-243">"网络" 面板中的新路径和 URL 列</span><span class="sxs-lookup"><span data-stu-id="757dc-243">The new Path and URL columns in the Network panel</span></span>  
> !["网络" 面板中的新路径和 URL 列][ImagePathNetworkPanel]  

<span data-ttu-id="757dc-245">右键单击**瀑布**表标题，然后选择 "**路径**" 或 " **URL** " 以显示新列。</span><span class="sxs-lookup"><span data-stu-id="757dc-245">Right-click the **Waterfall** table header and select **Path** or **URL** to show the new columns.</span></span>  

<span data-ttu-id="757dc-246">Chromium 问题[#993366][crbug993366]</span><span class="sxs-lookup"><span data-stu-id="757dc-246">Chromium issue [#993366][crbug993366]</span></span>  

#### <span data-ttu-id="757dc-247">已更新的用户代理字符串</span><span class="sxs-lookup"><span data-stu-id="757dc-247">Updated User-Agent strings</span></span>   

<span data-ttu-id="757dc-248">DevTools 支持通过 "**网络条件**" 选项卡设置自定义用户代理字符串。 用户代理字符串会影响 `User-Agent` 附加到网络资源的 HTTP 标头以及的值 `navigator.userAgent` 。</span><span class="sxs-lookup"><span data-stu-id="757dc-248">DevTools supports setting a custom User-Agent string through the **Network Conditions** tab.  The User-Agent string affects the `User-Agent` HTTP header attached to network resources, and also the value of `navigator.userAgent`.</span></span>  

<span data-ttu-id="757dc-249">预定义的用户代理字符串已更新，以反映新式浏览器版本。</span><span class="sxs-lookup"><span data-stu-id="757dc-249">The predefined User-Agent strings have been updated to reflect modern browser versions.</span></span>  

> ##### <span data-ttu-id="757dc-250">图 15</span><span class="sxs-lookup"><span data-stu-id="757dc-250">Figure 15</span></span>  
> <span data-ttu-id="757dc-251">"网络条件" 选项卡中的 "用户代理" 菜单</span><span class="sxs-lookup"><span data-stu-id="757dc-251">The User Agent menu in the Network Conditions tab</span></span>  
> !["网络条件" 选项卡中的 "用户代理" 菜单][ImageUserAgentNetworkConditionsTab]  

<span data-ttu-id="757dc-253">若要访问**网络条件**，请[打开命令菜单][DevToolsCommandMenuIndex]并运行 `Show Network Conditions` 命令。</span><span class="sxs-lookup"><span data-stu-id="757dc-253">To access **Network Conditions**, [open the Command Menu][DevToolsCommandMenuIndex] and run the `Show Network Conditions` command.</span></span>  

> [!NOTE]
> <span data-ttu-id="757dc-254">您也可以[在设备模式下设置用户代理的字符串][DevToolsDeviceModeIndex]。</span><span class="sxs-lookup"><span data-stu-id="757dc-254">You may also [set User-Agent strings in Device Mode][DevToolsDeviceModeIndex].</span></span>  

<span data-ttu-id="757dc-255">Chromium 问题[#1029031][crbug1029031]</span><span class="sxs-lookup"><span data-stu-id="757dc-255">Chromium issue [#1029031][crbug1029031]</span></span>  

### <span data-ttu-id="757dc-256">"审核" 面板更新</span><span class="sxs-lookup"><span data-stu-id="757dc-256">Audits panel updates</span></span>   

#### <span data-ttu-id="757dc-257">新的配置 UI</span><span class="sxs-lookup"><span data-stu-id="757dc-257">New configuration UI</span></span>   

<span data-ttu-id="757dc-258">配置 UI 具有新的响应式设计，并且限制配置选项已简化。</span><span class="sxs-lookup"><span data-stu-id="757dc-258">The configuration UI has a new, responsive design, and the throttling configuration options have been simplified.</span></span>  <span data-ttu-id="757dc-259">有关限制 UI 更改的详细信息，请参阅[审核面板限制][GitHubGoogleChromeDevToolsAuditsPanelThrottling]。</span><span class="sxs-lookup"><span data-stu-id="757dc-259">See [Audits Panel Throttling][GitHubGoogleChromeDevToolsAuditsPanelThrottling] for more information on the throttling UI changes.</span></span>  

> ##### <span data-ttu-id="757dc-260">图 16</span><span class="sxs-lookup"><span data-stu-id="757dc-260">Figure 16</span></span>  
> <span data-ttu-id="757dc-261">新的配置 UI</span><span class="sxs-lookup"><span data-stu-id="757dc-261">The new configuration UI</span></span>  
> ![新的配置 UI][ImageConfigurationUI]  

### <span data-ttu-id="757dc-263">覆盖范围选项卡更新</span><span class="sxs-lookup"><span data-stu-id="757dc-263">Coverage tab updates</span></span>   

#### <span data-ttu-id="757dc-264">每个函数或每块覆盖率模式</span><span class="sxs-lookup"><span data-stu-id="757dc-264">Per-function or per-block coverage modes</span></span>   

<span data-ttu-id="757dc-265">"[覆盖范围" 选项卡][DevToolsCoverageIndex]具有新的下拉菜单，可让你指定是否应**按每个函数**或**每个块**收集代码覆盖率数据。</span><span class="sxs-lookup"><span data-stu-id="757dc-265">The [Coverage tab][DevToolsCoverageIndex] has a new dropdown menu that lets you specify whether code coverage data should be collected **per function** or **per block**.</span></span>  <span data-ttu-id="757dc-266">**每个块**覆盖率更详细，但更昂贵的收集方式。</span><span class="sxs-lookup"><span data-stu-id="757dc-266">**Per block** coverage is more detailed but also far more expensive to collect.</span></span>  <span data-ttu-id="757dc-267">默认情况下，DevTools 使用**每个函数**覆盖率。</span><span class="sxs-lookup"><span data-stu-id="757dc-267">DevTools uses **per function** coverage by default now.</span></span>  

> [!CAUTION]
> <span data-ttu-id="757dc-268">你可能会看到 HTML 文件中的较大代码覆盖率有差异，具体取决于**每个函数**还是**每块**模式使用。</span><span class="sxs-lookup"><span data-stu-id="757dc-268">You may see large code coverage differences in HTML files depending on whether you use **per function** or **per block** mode.</span></span>  <span data-ttu-id="757dc-269">使用**每个函数**模式时，HTML 文件中的内联脚本将被视为函数。</span><span class="sxs-lookup"><span data-stu-id="757dc-269">When using **per function** mode, inline scripts in HTML files are treated as functions.</span></span>  <span data-ttu-id="757dc-270">如果脚本全部运行，则 DevTools 将整个脚本标记为使用的代码。</span><span class="sxs-lookup"><span data-stu-id="757dc-270">If the script runs at all then DevTools marks the entire script as used code.</span></span>  <span data-ttu-id="757dc-271">仅当脚本根本不运行时，DevTools 将脚本标记为未使用的代码。</span><span class="sxs-lookup"><span data-stu-id="757dc-271">Only if the script does not run at all does DevTools mark the script as unused code.</span></span>  

> ##### <span data-ttu-id="757dc-272">图 17</span><span class="sxs-lookup"><span data-stu-id="757dc-272">Figure 17</span></span>  
> <span data-ttu-id="757dc-273">"覆盖模式" 下拉菜单</span><span class="sxs-lookup"><span data-stu-id="757dc-273">The coverage mode dropdown menu</span></span>  
> !["覆盖模式" 下拉菜单][ImageCoverageMode]  

#### <span data-ttu-id="757dc-275">覆盖范围现在必须由页面重装启动</span><span class="sxs-lookup"><span data-stu-id="757dc-275">Coverage must now be initiated by a page reload</span></span>   

<span data-ttu-id="757dc-276">由于覆盖率数据不可靠，因此在没有页面重新加载的情况下切换代码覆盖率已被删除。</span><span class="sxs-lookup"><span data-stu-id="757dc-276">Toggling code coverage without a page reload has been removed because the coverage data was unreliable.</span></span>  <span data-ttu-id="757dc-277">例如，如果运行时以前很长一段时间，并且 V8 垃圾回收器已清理过它，则可能会将函数报告为未使用。</span><span class="sxs-lookup"><span data-stu-id="757dc-277">For example, a function may be reported as unused if the runtime was a long time ago and the V8 garbage collector has cleaned it up.</span></span>  

<span data-ttu-id="757dc-278">Chromium 问题[#1004203][crbug1004203]</span><span class="sxs-lookup"><span data-stu-id="757dc-278">Chromium issue [#1004203][crbug1004203]</span></span>  

## <span data-ttu-id="757dc-279">反馈</span><span class="sxs-lookup"><span data-stu-id="757dc-279">Feedback</span></span>   



<span data-ttu-id="757dc-280">若要讨论此文章中的新功能和更改，或与 DevTools 相关的任何其他内容，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="757dc-280">To discuss the new features and changes in this post, or anything else related to DevTools:</span></span>  

*   <span data-ttu-id="757dc-281">使用 DevTools 中的**反馈**图标发送反馈</span><span class="sxs-lookup"><span data-stu-id="757dc-281">Send your feedback using the **Feedback** icon in the DevTools</span></span>  

> ##### <span data-ttu-id="757dc-282">图18</span><span class="sxs-lookup"><span data-stu-id="757dc-282">Figure 18</span></span>
> <span data-ttu-id="757dc-283">Microsoft Edge DevTools 中的 "**反馈**" 图标</span><span class="sxs-lookup"><span data-stu-id="757dc-283">The **Feedback** icon in the Microsoft Edge DevTools</span></span>  
> ![Microsoft Edge DevTools 中的 \* \* 反馈 \* \* 图标][ImageFeedbackIcon]  

*   <span data-ttu-id="757dc-285">Tweet [@EdgeDevTools][PostTweetEdgeDevTools]</span><span class="sxs-lookup"><span data-stu-id="757dc-285">Tweet at [@EdgeDevTools][PostTweetEdgeDevTools]</span></span>  
*   <span data-ttu-id="757dc-286">向[我们需要的网站][TheWebWeWant]提交建议</span><span class="sxs-lookup"><span data-stu-id="757dc-286">Submit a suggestion to [The Web We Want][TheWebWeWant]</span></span>  
*   <span data-ttu-id="757dc-287">此文档在[edge-开发人员][GitHubMicrosoftDocsEdgeDeveloperNewIssue]存储库中的文件错误</span><span class="sxs-lookup"><span data-stu-id="757dc-287">File bugs on this document in the [edge-developer][GitHubMicrosoftDocsEdgeDeveloperNewIssue] repository</span></span>  

## <span data-ttu-id="757dc-288">下载 Microsoft Edge 预览频道</span><span class="sxs-lookup"><span data-stu-id="757dc-288">Download the Microsoft Edge preview channels</span></span>   

<span data-ttu-id="757dc-289">如果你使用的是 Windows 或 macOS，请考虑将[Microsoft Edge 预览通道][MicrosoftEdgePreviewChannels]用作默认开发浏览器。</span><span class="sxs-lookup"><span data-stu-id="757dc-289">If you are on Windows or macOS, consider using the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] as your default development browser.</span></span>  <span data-ttu-id="757dc-290">预览频道使您可以访问最新的 DevTools 功能。</span><span class="sxs-lookup"><span data-stu-id="757dc-290">The preview channels give you access to the latest DevTools features.</span></span>  

<!--<<../../_shared/devtools-feedback.md>> -->

<!--<<../../_shared/canary.md>> -->

<!--<<../../_shared/discover.md>> -->



<!-- image links -->  

[ImagePerformanceToolKeyboardReaderImprovements]: ../../images/2019/12/a11y-performance-tool.msft.gif "图1：具有键盘导航和屏幕阅读器的 DevTools 中的性能工具改进"  
[ImageLocalizedGerman]: ../../images/2019/12/localized-devtools.msft.png "图2：德语中的 DevTools"  
[ImageHintsTabWebhintExtension]: ../../images/2019/12/webhint-browser-extension.msft.png "图3：安装 webhint 浏览器扩展时，Microsoft Edge DevTools 中的 "提示" 选项卡"  
[Image3DView]: ../../images/2019/12/3dview.msft.png "图4： Microsoft Edge DevTools 中的3D 视图"  
[ImageElementsVisualStudioCode]: ../../images/2019/12/elements-for-edge.msft.png "图5：使用 Microsoft Edge 扩展元素的 VS 代码中的元素工具"  
[ImageDebuggerExtensionVisualStudioCode]: ../../images/2019/12/vscode-debugger.msft.png "图6： VS 代码中的 Microsoft Edge 扩展调试器"  
[ImageWebhintVisualStudioCodeExtensionWorkspace]: ../../images/2019/12/webhint-vscode-extension.msft.png "图7：分析 VS 代码中的 tsx 文件的 webhint 与代码扩展"  
[ImageVisualStudioLaunchWebApp]: ../../images/2019/12/vs.msft.png "图8：具有在 Microsoft Edge 的 "应用程序"、"开发" 或 "Beta" 中启动 web 应用选项的 Visual Studio"  
[ImageTrackingPrevention]: ../../images/2019/12/tracking-prevention.msft.png "图9：当跟踪阻止阻止跟踪对存储的访问时，在控制台中的消息"  
[ImageConsoleRedeclarationFails]: ../../images/2019/12/letbefore.msft.png "图10： Microsoft Edge 79 中的控制台，显示允许重新声明失败"  
[ImageConsoleRedeclarationSucceeds]: ../../images/2019/12/letafter.msft.png "图11： Microsoft Edge 80 中的控制台，显示允许重新声明成功"  
[ImageRequestInitiatorChain]: ../../images/2019/12/initiators.msft.png "图12： "启动器" 选项卡中的请求启动器链"  
[ImageOverviewPaneInspectedResource]: ../../images/2019/12/overview.msft.png "图13：突出显示已检查资源的概述窗格"  
[ImagePathNetworkPanel]: ../../images/2019/12/columns.msft.png "图14： "网络" 面板中的新路径和 URL 列"  
[ImageUserAgentNetworkConditionsTab]: ../../images/2019/12/useragent.msft.png "图15： "网络条件" 选项卡中的 "用户代理" 菜单"  
[ImageConfigurationUI]: ../../images/2019/12/start.msft.png "图16：新的配置 UI"  
[ImageCoverageMode]: ../../images/2019/12/modes.msft.png "图17： "覆盖率模式" 下拉菜单"  
[ImageFeedbackIcon]: ../../images/2019/12/feedback-icon.msft.png "图18： Microsoft Edge DevTools 中的 * * 反馈 * * 图标"

<!--[ImageDwarfPoweredWebAssemblyDebugging]: ../../images/2019/12/wasm.msft.png "Figure: The new DWARF-powered WebAssembly debugging"  -->

<!-- links -->  

[DevToolsCommandMenuIndex]: ../../../command-menu/index.md "通过 Microsoft Edge DevTools 命令菜单运行命令"  
[DevToolsCoverageIndex]: ../../../coverage/index.md "使用 Microsoft Edge DevTools 中的 "覆盖范围" 选项卡查找未使用的 JavaScript 和 CSS 代码"  
[DevToolsDeviceModeIndex]: ../../../device-mode/index.md#simulate-a-mobile-viewport "模拟移动区-在 Microsoft Edge DevTools 中使用设备模式模拟移动设备"  
[DevToolsNetworkIndex]: ../../../network/index.md "检查 Microsoft Edge DevTools 中的网络活动"  
[DevToolsNetworkReferenceViewInitiatorsDependencies]: ../../../network/reference.md#view-initiators-and-dependencies "查看启动器和相关性-网络分析参考"  
[DevGuideEdgeHtmlWhatsNew]: ../../../../dev-guide/whats-new.md "EdgeHTML 中的新增功能"  
[VisualStudioCodeDebuggerEdgeExtension]: ../../../../visual-studio-code/debugger-for-edge.md "Microsoft Edge 与代码扩展的调试器"  
[VisualStudioCodeElementEdgeExtension]: ../../../../visual-studio-code/elements-for-edge.md "Microsoft Edge 与代码扩展的元素"  

<!--  [201912Webassembly]: webassembly.md "Improved WebAssembly debugging in Microsoft Edge DevTools"  -->  

[crbug842488]: https://crbug.com/842488 "842488-将 "发起方" 字段添加到 "页眉" 选项卡-Monorail"  
[crbug988253]: https://crbug.com/988253 "988253-Bug DevTools-网络请求与时间线图之间没有关联-Monorail"  
[crbug993366]: https://crbug.com/993366 "993366-请在网络面板请求列表中显示 URL 的路径部分-Monorail"  
[crbug1004193]: https://crbug.com/1004193 "1004193-V8-Monorail 的复制模式"  
[crbug1004203]: https://crbug.com/1004203 "1004203-Monorail"  
[crbug1029031]: https://crbug.com/1029031 "1029031-UA 字符串过期-Monorail" 
[crbug963183]: https://crbug.com/963183 "963183-DevTools 不符合 WCAG"
[crbug941561]: https://crbug.com/941561 "941561-DevTools 的本地化"
[crbug987787]: https://crbug.com/987787 "987787-Dom 3D 视图"

[AccessibilityInsights]: https://aka.ms/a11yinsights "辅助功能见解"  

[DwarfHome]: https://dwarfstd.org "Dwarf 主页"  
[GitHubGoogleChromeDevToolsAuditsPanelThrottling]: https://github.com/GoogleChrome/lighthouse/blob/master/docs/throttling.md#devtools-audits-panel-throttling "DevTools ' 审核面板限制-GoogleChrome/lighthouse |GitHub"  
[GitHubMicrosoftDocsEdgeDeveloperNewIssue]: https://aka.ms/edgedevtoolsdocs/feedback "新问题-MicrosoftDocs/edge-开发人员"  
[MicrosoftEdgePreviewChannels]: https://aka.ms/microsoftedge "Microsoft Edge 预览频道"  
[MicrosoftEdgeInsiderAddons]: https://aka.ms/webhint/edge-extension "Microsoft Edge 预览体验计划 Addons"  
[MicrosoftVisualStudio]: https://aka.ms/vs "Visual Studio"  
[MicrosoftVisualStudioBlogDebugJavascript]: https://aka.ms/vs/debug-edge "从 Visual Studio 中的 Microsoft Edge 调试 JavaScript |Visual Studio 博客"  
[MicrosoftVisualStudioDownloads]: https://aka.ms/vs/download "下载适用于 Windows 的 Visual Studio 2019 & Mac"  
[MDNDocumentObjectModel]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model "文档对象模型（DOM） |MDN"  
[MDNZIndex]: https://developer.mozilla.org/docs/Web/CSS/z-index "z-索引 |MDN"  
[PostTweetEdgeDevTools]: https://aka.ms/tweet/edgedevtools "@EdgeDevTools |发布 Tweet"  
[EdgeDevToolsTwitterAccount]: https://aka.ms/twitter/edgedevtools "@EdgeDevTools Twitter 帐户"
[VisualStudioCode]: https://aka.ms/vscode "Visual Studio 代码"  
[VisualStudioMarketplaceDebuggerEdge]: https://aka.ms/debugger4code "Microsoft Edge 的调试器-Visual Studio Marketplace"  
[VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension]: https://aka.ms/elements4code "Microsoft Edge 的元素 \ （Chromium \）-Visual Studio Marketplace"  
[VisualStudioMarketplaceWebhintExtension]: https://aka.ms/webhint4code "webhint-Visual Studio Marketplace"
[Webhint]: https://aka.ms/webhint "webhint"  
[WebhintBrowserExtension]: https://aka.ms/webhint/browser-extension "Webhint 浏览器扩展 |webhint 文档"  
[WebhintVisualStudioCodeExtension]: https://aka.ms/webhint/code-extension "Webhint 与代码扩展 |webhint 文档"  
[TrackingPrevention]: https://aka.ms/microsoftedge/tracking-prevention-blog "改进 Microsoft Edge 博客文章中的跟踪保护"
[TheWebWeWant]: https://aka.ms/webwewant "我们需要的网站"

> [!NOTE]
> <span data-ttu-id="757dc-348">此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="757dc-348">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="757dc-349">原始页面位于[此处](https://developers.google.com/web/updates/2019/12/devtools/index)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools & Lighthouse \）创作。</span><span class="sxs-lookup"><span data-stu-id="757dc-349">The original page is found [here](https://developers.google.com/web/updates/2019/12/devtools/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools & Lighthouse\).</span></span>  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
<span data-ttu-id="757dc-351">此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="757dc-351">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
