---
description: 辅助功能改进、在其他语言中使用 DevTools 等。
title: 'Microsoft Edge 80 (DevTools 中的新增) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: 80f870d22c81479bff9b9413717ccc7c323d9a05
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11397557"
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

# <a name="whats-new-in-devtools-microsoft-edge-80"></a><span data-ttu-id="f855b-104">Microsoft Edge 80 (DevTools 中的新增) </span><span class="sxs-lookup"><span data-stu-id="f855b-104">What's new in DevTools (Microsoft Edge 80)</span></span>  

## <a name="announcements-from-the-microsoft-edge-devtools-team"></a><span data-ttu-id="f855b-105">来自 Microsoft Edge 开发人员工具团队公告</span><span class="sxs-lookup"><span data-stu-id="f855b-105">Announcements from the Microsoft Edge DevTools team</span></span>  

<span data-ttu-id="f855b-106">以下各节列出了你可能从 Microsoft Edge DevTools 团队错过的公告。</span><span class="sxs-lookup"><span data-stu-id="f855b-106">The following sections are a list of announcements you may have missed from the Microsoft Edge DevTools team.</span></span>  <span data-ttu-id="f855b-107">查看通知以试用 DevTools、Microsoft Visual Studio代码扩展等中的新功能。</span><span class="sxs-lookup"><span data-stu-id="f855b-107">Check out the announcements to try new features in the DevTools, Microsoft Visual Studio Code extensions, and more.</span></span>  <span data-ttu-id="f855b-108">若要了解有关开发人员工具中的所有最新功能和最强大功能的最新动态，请下载 [Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels]并[在 Twitter 上关注我们][EdgeDevToolsTwitterAccount]。</span><span class="sxs-lookup"><span data-stu-id="f855b-108">To stay up to date on all the latest and greatest features in your developer tools, download the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] and [follow us on Twitter][EdgeDevToolsTwitterAccount].</span></span>  

### <a name="accessibility-improvements-to-the-devtools"></a><span data-ttu-id="f855b-109">DevTools 的辅助功能改进</span><span class="sxs-lookup"><span data-stu-id="f855b-109">Accessibility improvements to the DevTools</span></span>  

<span data-ttu-id="f855b-110">DevTools 团队已对 Chromium 进行 170 项更改，以解决 DevTools 中高影响的颜色对比度、键盘和屏幕阅读器问题。</span><span class="sxs-lookup"><span data-stu-id="f855b-110">The DevTools team has contributed 170 changes to Chromium to address high-impact color contrast, keyboard, and screen reader issues in the DevTools.</span></span>  <span data-ttu-id="f855b-111">每个生成 Web 的开发人员都应能够使用 DevTools。</span><span class="sxs-lookup"><span data-stu-id="f855b-111">Every developer building the web should be able to use the DevTools.</span></span>  

:::image type="complex" source="../../images/2019/12/a11y-performance-tool.msft.gif" alt-text="具有键盘导航和屏幕阅读器改进的 DevTools 中的性能工具" lightbox="../../images/2019/12/a11y-performance-tool.msft.gif":::
   <span data-ttu-id="f855b-113">具有 **键盘** 导航和屏幕阅读器改进的 DevTools 中的性能工具</span><span class="sxs-lookup"><span data-stu-id="f855b-113">The **Performance** tool in the DevTools with the keyboard navigation and screen reader improvements</span></span>  
:::image-end:::  

<span data-ttu-id="f855b-114">想要了解如何使网页可供所有用户访问？</span><span class="sxs-lookup"><span data-stu-id="f855b-114">Want to learn how to make your web page accessible to all of your users?</span></span>  <span data-ttu-id="f855b-115">下载 [Microsoft][AccessibilityInsights] Edge 的辅助功能见解和 [Webhint][WebhintBrowserExtension] 扩展以开始使用。</span><span class="sxs-lookup"><span data-stu-id="f855b-115">Download the [Accessibility Insights][AccessibilityInsights] and [webhint][WebhintBrowserExtension] extensions for Microsoft Edge to get started.</span></span>  

<span data-ttu-id="f855b-116">如果使用屏幕阅读器或键盘在 DevTools 中导航，请通过向我们推文或[][PostTweetEdgeDevTools]选择"发送反馈"图标发送[反馈](#getting-in-touch-with-microsoft-edge-devtools-team)！</span><span class="sxs-lookup"><span data-stu-id="f855b-116">If you use screen readers or the keyboard to navigate around the DevTools, send your feedback by [tweeting][PostTweetEdgeDevTools] at us orchoosing the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!</span></span>  

<span data-ttu-id="f855b-117">Chromium 问题 [#963183][CR963183]</span><span class="sxs-lookup"><span data-stu-id="f855b-117">Chromium issue [#963183][CR963183]</span></span>  

### <a name="using-the-devtools-in-other-languages"></a><span data-ttu-id="f855b-118">在其他语言中使用 DevTools</span><span class="sxs-lookup"><span data-stu-id="f855b-118">Using the DevTools in other languages</span></span>  

<span data-ttu-id="f855b-119">许多开发人员使用其他开发人员工具（如 StackOverflow 和 Visual Studio Code）采用其本机语言，而不只是使用英语。</span><span class="sxs-lookup"><span data-stu-id="f855b-119">Many developers use other developer tools, like StackOverflow and Visual Studio Code, in their native language, not just in English.</span></span>  <span data-ttu-id="f855b-120">我们很高兴宣布 DevTools 的本地化，你现在可以使用英语之外 10 种语言之一：</span><span class="sxs-lookup"><span data-stu-id="f855b-120">We’re excited to announce localization for the DevTools, which you are now able to use in one of 10 languages besides English:</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="f855b-121">中文 \ (简体\) - &#20013;&#25991;&#65288;&#31616;&#20307;&#65289;</span><span class="sxs-lookup"><span data-stu-id="f855b-121">Chinese \(Simplified\) - &#20013;&#25991;&#65288;&#31616;&#20307;&#65289;</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="f855b-122">中文 \ (繁体\) - &#20013;&#25991;&#65288;&#32321;&#39636;&#65289;</span><span class="sxs-lookup"><span data-stu-id="f855b-122">Chinese \(Traditional\) - &#20013;&#25991;&#65288;&#32321;&#39636;&#65289;</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      <span data-ttu-id="f855b-123">法语 – 法语&#231;法语</span><span class="sxs-lookup"><span data-stu-id="f855b-123">French – fran&#231;ais</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="f855b-124">德语 - 德语</span><span class="sxs-lookup"><span data-stu-id="f855b-124">German - deutsch</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      <span data-ttu-id="f855b-125">意大利语 - 意大利语</span><span class="sxs-lookup"><span data-stu-id="f855b-125">Italian - italiano</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="f855b-126">日语 - &#26085;&#26412;&#35486;</span><span class="sxs-lookup"><span data-stu-id="f855b-126">Japanese - &#26085;&#26412;&#35486;</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      <span data-ttu-id="f855b-127">朝鲜语 - &#54620;&#44397;&#50612;</span><span class="sxs-lookup"><span data-stu-id="f855b-127">Korean - &#54620;&#44397;&#50612;</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="f855b-128">葡萄牙语 - portugu&#234;s</span><span class="sxs-lookup"><span data-stu-id="f855b-128">Portuguese - portugu&#234;s</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      <span data-ttu-id="f855b-129">俄语 – &#1088;&#1091;&#1089;&#1089;&#1082;&#1080;&#1081;</span><span class="sxs-lookup"><span data-stu-id="f855b-129">Russian – &#1088;&#1091;&#1089;&#1089;&#1082;&#1080;&#1081;</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="f855b-130">西班牙语 - espa&#241;ol</span><span class="sxs-lookup"><span data-stu-id="f855b-130">Spanish - espa&#241;ol</span></span>
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

<span data-ttu-id="f855b-131">导航到 `edge://flags` "**启用本地化开发人员工具"标志，并**设置为 **"已启用"。**</span><span class="sxs-lookup"><span data-stu-id="f855b-131">Navigate to `edge://flags` and set the **Enable localized Developer Tools** flag to **Enabled**.</span></span>  <span data-ttu-id="f855b-132">此外，将 **"开发人员工具"实验**标志设置为 **"已启用"。**</span><span class="sxs-lookup"><span data-stu-id="f855b-132">Also set the **Developer Tools experiments** flag to **Enabled**.</span></span>  <span data-ttu-id="f855b-133">重新启动 Microsoft Edge 并打开 DevTools。</span><span class="sxs-lookup"><span data-stu-id="f855b-133">Restart Microsoft Edge and open the DevTools.</span></span>  <!-- Select `F1` in the DevTools or navigate to Settings > Experiments and check the **Match browser language** checkbox.  -->  <span data-ttu-id="f855b-134">DevTools 与在 中用于 Microsoft Edge 的语言匹配 `edge://settings/languages` 。</span><span class="sxs-lookup"><span data-stu-id="f855b-134">The DevTools match the language you use for Microsoft Edge in `edge://settings/languages`.</span></span>  

:::image type="complex" source="../../images/2019/12/localized-devtools.msft.png" alt-text="德语的 DevTools" lightbox="../../images/2019/12/localized-devtools.msft.png":::
   <span data-ttu-id="f855b-136">德语的 DevTools</span><span class="sxs-lookup"><span data-stu-id="f855b-136">The DevTools in German</span></span>  
:::image-end:::  

<span data-ttu-id="f855b-137">如果你想要使用与可用版本不同的 DevTools，请通过推文联系我们或选择"发送[][PostTweetEdgeDevTools][反馈"](#getting-in-touch-with-microsoft-edge-devtools-team)图标。</span><span class="sxs-lookup"><span data-stu-id="f855b-137">If you want to use the DevTools in a different language than the ones that are available, [tweet][PostTweetEdgeDevTools] at us or choose the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon.</span></span>  

<span data-ttu-id="f855b-138">Chromium 问题 [#941561][CR941561]</span><span class="sxs-lookup"><span data-stu-id="f855b-138">Chromium issue [#941561][CR941561]</span></span>  

### <a name="webhint-microsoft-edge-extension"></a><span data-ttu-id="f855b-139">webhint Microsoft Edge 扩展</span><span class="sxs-lookup"><span data-stu-id="f855b-139">webhint Microsoft Edge extension</span></span>  

<span data-ttu-id="f855b-140">Webhint Microsoft Edge 扩展允许你轻松扫描网页，并获取有关辅助功能、浏览器兼容性、安全性、性能等在 DevTools 中的反馈。</span><span class="sxs-lookup"><span data-stu-id="f855b-140">The webhint Microsoft Edge extension allows you to easily scan your web page and get feedback on accessibility, browser compatibility, security, performance, and more within the DevTools.</span></span>  <span data-ttu-id="f855b-141">有关详细信息，请参阅 [https://webhint.io][Webhint] 。</span><span class="sxs-lookup"><span data-stu-id="f855b-141">Read more at [https://webhint.io][Webhint].</span></span>  

:::image type="complex" source="../../images/2019/12/webhint-browser-extension.msft.png" alt-text="安装 Webhint 浏览器扩展时 DevTools 中的提示工具" lightbox="../../images/2019/12/webhint-browser-extension.msft.png":::
   <span data-ttu-id="f855b-143">安装 **Webhint** 浏览器扩展时 DevTools 中的提示工具</span><span class="sxs-lookup"><span data-stu-id="f855b-143">The **Hints** tool in the DevTools when the webhint browser extension is installed</span></span>  
:::image-end:::  

<span data-ttu-id="f855b-144">[尝试 Microsoft Edge 中的 Webhint 浏览器扩展][MicrosoftEdgeInsiderAddons]。</span><span class="sxs-lookup"><span data-stu-id="f855b-144">[Try the webhint browser extension in Microsoft Edge][MicrosoftEdgeInsiderAddons].</span></span>  <span data-ttu-id="f855b-145">安装扩展后，打开 DevTools 并选择 **提示** 工具。</span><span class="sxs-lookup"><span data-stu-id="f855b-145">Once you install the extension, open the DevTools and choose the **Hints** tool.</span></span>  <span data-ttu-id="f855b-146">从此处运行可自定义的网站扫描。</span><span class="sxs-lookup"><span data-stu-id="f855b-146">From here, run a customizable site scan.</span></span>  <span data-ttu-id="f855b-147">请 [前往webhint.io][WebhintBrowserExtension] 了解更多信息。</span><span class="sxs-lookup"><span data-stu-id="f855b-147">Head over to [webhint.io][WebhintBrowserExtension] to learn more.</span></span>

### <a name="3d-view"></a><span data-ttu-id="f855b-148">3D 视图</span><span class="sxs-lookup"><span data-stu-id="f855b-148">3D View</span></span>  

<span data-ttu-id="f855b-149">使用 **3D 视图** 通过浏览文档对象模型 [\ (DOM\) ][MDNDocumentObjectModel] [或 z 索引][MDNZIndex] 堆叠上下文来调试 Web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="f855b-149">Use the **3D View** to debug your web application by navigating through the [Document Object Model \(DOM\)][MDNDocumentObjectModel] or the [z-index][MDNZIndex] stacking context.</span></span>  

:::image type="complex" source="../../images/2019/12/3dview.msft.png" alt-text="DevTools 中的 3D 视图" lightbox="../../images/2019/12/3dview.msft.png":::
   <span data-ttu-id="f855b-151">DevTools 中的 **3D** 视图</span><span class="sxs-lookup"><span data-stu-id="f855b-151">The **3D View** in the DevTools</span></span>  
:::image-end:::  

<span data-ttu-id="f855b-152">若要访问 3D 视图，请导航到并确保开发人员 `edge://flags` **工具实验**标志设置为 **"已启用"。**</span><span class="sxs-lookup"><span data-stu-id="f855b-152">To access the 3D View, navigate to `edge://flags` and ensure that the **Developer Tools experiments** flag is set to **Enabled**.</span></span>  <span data-ttu-id="f855b-153">重新启动 Microsoft Edge 并打开 DevTools。</span><span class="sxs-lookup"><span data-stu-id="f855b-153">Restart Microsoft Edge and open the DevTools.</span></span>  <span data-ttu-id="f855b-154">在 DevTools 中选择或打开"设置实验"部分，然后打开"启用 `F1` \*\*\*\*  >  \*\*\*\*\*\*3D 视图"\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="f855b-154">Select `F1` in the DevTools or open the **Settings** > **Experiments** section, and turn on the **Enable 3D View** checkbox.</span></span>  <span data-ttu-id="f855b-155">现在，选择 `Ctrl`  +  `Shift`  +  `P` ，在**3D 视图中键入**，然后选择 **"显示 3D 视图"。**</span><span class="sxs-lookup"><span data-stu-id="f855b-155">Now, select `Ctrl` + `Shift` + `P`, type in **3D View** and select **Show 3D View**.</span></span>  

<span data-ttu-id="f855b-156">我们正在处理 UI 并将更多功能添加到 3D 视图，因此请将你的反馈 [发送给我们](#getting-in-touch-with-microsoft-edge-devtools-team)。</span><span class="sxs-lookup"><span data-stu-id="f855b-156">We're working on the UI and adding more functionality to the 3D View so please send us your [feedback](#getting-in-touch-with-microsoft-edge-devtools-team).</span></span>  

<span data-ttu-id="f855b-157">Chromium 问题 [#987787][CR987787]</span><span class="sxs-lookup"><span data-stu-id="f855b-157">Chromium issue [#987787][CR987787]</span></span>

### <a name="visual-studio-code-extensions"></a><span data-ttu-id="f855b-158">Visual Studio代码扩展</span><span class="sxs-lookup"><span data-stu-id="f855b-158">Visual Studio Code extensions</span></span>  

<span data-ttu-id="f855b-159">DevTools 团队还发布了一些适用于 Visual Studio [Code][VisualStudioCode] 的扩展，让你可以直接从文本编辑器使用 DevTools 功能。</span><span class="sxs-lookup"><span data-stu-id="f855b-159">The DevTools team has also released some extensions for [Visual Studio Code][VisualStudioCode] that let you use the power of the DevTools directly from your text editor.</span></span> <span data-ttu-id="f855b-160">查看以下扩展。</span><span class="sxs-lookup"><span data-stu-id="f855b-160">Check out the following extensions.</span></span>  

#### <a name="elements-for-microsoft-edge"></a><span data-ttu-id="f855b-161">Microsoft Edge 的元素</span><span class="sxs-lookup"><span data-stu-id="f855b-161">Elements for Microsoft Edge</span></span>  

<span data-ttu-id="f855b-162">通过添加 Microsoft Edge ([Chromium ][VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension]) Visual Studio代码扩展，在 Visual Studio 代码中使用 Elements 工具。</span><span class="sxs-lookup"><span data-stu-id="f855b-162">Use the Elements tool from within Visual Studio Code by adding the [Elements for Microsoft Edge (Chromium)][VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension] Visual Studio Code extension.</span></span>  

:::image type="complex" source="../../images/2019/12/elements-for-edge.msft.png" alt-text="使用 Microsoft Edge Visual Studio元素的代码中的元素工具" lightbox="../../images/2019/12/elements-for-edge.msft.png":::
   <span data-ttu-id="f855b-164">使用 **Microsoft** Edge 扩展Visual Studio元素的 Microsoft Code 中的 Elements 工具</span><span class="sxs-lookup"><span data-stu-id="f855b-164">The **Elements** tool in Visual Studio Code using the Elements for Microsoft Edge extension</span></span>  
:::image-end:::  

<span data-ttu-id="f855b-165">有关详细信息，请查看 Microsoft [Edge 元素Visual Studio代码扩展][VisualStudioCodeElementEdgeExtension]。</span><span class="sxs-lookup"><span data-stu-id="f855b-165">For more information, check out [Elements for Microsoft Edge Visual Studio Code extension][VisualStudioCodeElementEdgeExtension].</span></span>  

#### <a name="debugger-for-microsoft-edge"></a><span data-ttu-id="f855b-166">适用于 Microsoft Edge 的调试器</span><span class="sxs-lookup"><span data-stu-id="f855b-166">Debugger for Microsoft Edge</span></span>  

<span data-ttu-id="f855b-167">借助 [Microsoft Edge 调试器Visual Studio][VisualStudioMarketplaceDebuggerEdge] 代码扩展，直接从 Microsoft Edge 中调试在 Visual Studio 运行 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="f855b-167">With the [Debugger for Microsoft Edge][VisualStudioMarketplaceDebuggerEdge] Visual Studio Code extension, debug JavaScript running in Microsoft Edge directly from Visual Studio Code.</span></span>  

:::image type="complex" source="../../images/2019/12/vscode-debugger.msft.png" alt-text="Microsoft Edge 扩展的调试器（Visual Studio代码）" lightbox="../../images/2019/12/vscode-debugger.msft.png":::
   <span data-ttu-id="f855b-169">Microsoft Edge 扩展的调试器（Visual Studio代码）</span><span class="sxs-lookup"><span data-stu-id="f855b-169">The Debugger for Microsoft Edge Extension in Visual Studio Code</span></span>  
:::image-end:::  

<span data-ttu-id="f855b-170">有关详细信息，请查看如何从代码Visual Studio [Microsoft Edge。][VisualStudioCodeDebuggerEdgeExtension]</span><span class="sxs-lookup"><span data-stu-id="f855b-170">For more information, check out [how to debug Microsoft Edge from Visual Studio Code][VisualStudioCodeDebuggerEdgeExtension].</span></span>  

#### <a name="webhint"></a><span data-ttu-id="f855b-171">webhint</span><span class="sxs-lookup"><span data-stu-id="f855b-171">webhint</span></span>  

<span data-ttu-id="f855b-172">编写 [网页Visual Studio][VisualStudioMarketplaceWebhintExtension] 代码扩展用于改进网页 `webhint` ！</span><span class="sxs-lookup"><span data-stu-id="f855b-172">The [webhint][VisualStudioMarketplaceWebhintExtension] Visual Studio Code extension uses `webhint` to improve your web page while you're writing it!</span></span> <span data-ttu-id="f855b-173">此扩展将运行，并基于分析报告工作区文件的 `webhint` 诊断。</span><span class="sxs-lookup"><span data-stu-id="f855b-173">This extension runs and reports diagnostics on your workspace files based on `webhint` analysis.</span></span>  

:::image type="complex" source="../../images/2019/12/webhint-vscode-extension.msft.png" alt-text="Webhint Visual Studio代码扩展，用于分析代码中的 .tsx Visual Studio文件" lightbox="../../images/2019/12/webhint-vscode-extension.msft.png":::
   <span data-ttu-id="f855b-175">Webhint Visual Studio代码扩展，用于分析代码 `.tsx` Visual Studio文件</span><span class="sxs-lookup"><span data-stu-id="f855b-175">The webhint Visual Studio Code extension analyzing a `.tsx` file in Visual Studio Code</span></span>  
:::image-end:::  

<span data-ttu-id="f855b-176">[了解有关代码 webhint 扩展Visual Studio代码。][WebhintVisualStudioCodeExtension]</span><span class="sxs-lookup"><span data-stu-id="f855b-176">[Learn more about the Visual Studio Code webhint extension][WebhintVisualStudioCodeExtension].</span></span>  

### <a name="visual-studio-integration"></a><span data-ttu-id="f855b-177">Visual Studio集成</span><span class="sxs-lookup"><span data-stu-id="f855b-177">Visual Studio integration</span></span>  

<span data-ttu-id="f855b-178">在 Visual Studio 2019 版本 16.2 或更高版本中，Visual Studio调试程序调试在 Microsoft Edge 中运行的 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="f855b-178">In Visual Studio 2019 version 16.2 or later, use the Visual Studio debugger to debug JavaScript running in Microsoft Edge.</span></span>  <span data-ttu-id="f855b-179">[下载 Visual Studio 2019][MicrosoftVisualStudioDownloads] 以试用此功能。</span><span class="sxs-lookup"><span data-stu-id="f855b-179">[Download Visual Studio 2019][MicrosoftVisualStudioDownloads] to try this feature out.</span></span>  

:::image type="complex" source="../../images/2019/12/vs.msft.png" alt-text="Visual Studio Microsoft Edge Canary、Dev 或 Beta 中启动 Web 应用的选项" lightbox="../../images/2019/12/vs.msft.png":::
   <span data-ttu-id="f855b-181">Visual Studio Microsoft Edge Canary、Dev 或 Beta 中启动 Web 应用的选项</span><span class="sxs-lookup"><span data-stu-id="f855b-181">Visual Studio with the option to launch your web app in Microsoft Edge Canary, Dev, or Beta</span></span>  
:::image-end:::  

<span data-ttu-id="f855b-182">[阅读我们的博客文章，了解如何][MicrosoftVisualStudioBlogDebugJavascript]从 Visual Studio 调试 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="f855b-182">[Read our blog post to learn how to debug Microsoft Edge from Visual Studio][MicrosoftVisualStudioBlogDebugJavascript].</span></span>  

### <a name="tracking-prevention-console-messages"></a><span data-ttu-id="f855b-183">跟踪防护控制台消息</span><span class="sxs-lookup"><span data-stu-id="f855b-183">Tracking prevention Console messages</span></span>  

<span data-ttu-id="f855b-184">跟踪防护是 Microsoft Edge 中的一项独特功能，可阻止你在访问网站之前被网站跟踪。</span><span class="sxs-lookup"><span data-stu-id="f855b-184">Tracking prevention is a unique feature in Microsoft Edge that blocks you from being tracked by a website before you visited it.</span></span>  <span data-ttu-id="f855b-185">默认跟踪防护设置为"平衡"模式，可阻止第三方跟踪器和已知恶意跟踪器，从而获得平衡隐私和 Web 兼容性的体验。</span><span class="sxs-lookup"><span data-stu-id="f855b-185">The default tracking prevention setting is Balanced mode, which blocks 3rd party trackers and known malicious trackers for an experience that balances privacy and web compatibility.</span></span>  <span data-ttu-id="f855b-186">为了进一步深入了解阻止某些跟踪程序时网页的兼容性，Microsoft Edge 团队在控制台中添加了跟踪程序被阻止时警告\*\*\*\* 消息。</span><span class="sxs-lookup"><span data-stu-id="f855b-186">To give you more insight into the compatibility of your web page when certain trackers are blocked, The Microsoft Edge team added warning messages in the **Console** when a tracker is blocked.</span></span>  

:::image type="complex" source="../../images/2019/12/tracking-prevention.msft.png" alt-text="跟踪防护时控制台中的邮件阻止访问跟踪器的存储" lightbox="../../images/2019/12/tracking-prevention.msft.png":::
   <span data-ttu-id="f855b-188">跟踪防护 **时控制台** 中的邮件阻止访问跟踪器的存储</span><span class="sxs-lookup"><span data-stu-id="f855b-188">Messages in the **Console** when tracking prevention blocks access to storage for a tracker</span></span>  
:::image-end:::  

<span data-ttu-id="f855b-189">[阅读有关跟踪防护以及隐私与 Web 兼容性之间平衡的详细信息][TrackingPrevention]。</span><span class="sxs-lookup"><span data-stu-id="f855b-189">[Read more about tracking prevention and the balance between privacy and web compatibility][TrackingPrevention].</span></span>  

## <a name="announcements-from-the-chromium-project"></a><span data-ttu-id="f855b-190">来自 Chromium 项目的公告</span><span class="sxs-lookup"><span data-stu-id="f855b-190">Announcements from the Chromium project</span></span>  

<span data-ttu-id="f855b-191">以下各节宣布 Microsoft Edge 80 中提供的其他功能，这些功能对开源 Chromium 项目有贡献。</span><span class="sxs-lookup"><span data-stu-id="f855b-191">The following sections announce additional features available in Microsoft Edge 80 that were contributed to the open source Chromium project.</span></span>  

### <a name="support-for-let-and-class-redeclarations-in-the-console"></a><span data-ttu-id="f855b-192">支持控制台中的 let 和类重新声明</span><span class="sxs-lookup"><span data-stu-id="f855b-192">Support for let and class redeclarations in the Console</span></span>  

<span data-ttu-id="f855b-193">控制台 **现在** 支持重新声明 `let` 和 `class` 语句。</span><span class="sxs-lookup"><span data-stu-id="f855b-193">The **Console** now supports redeclarations of `let` and `class` statements.</span></span>  <span data-ttu-id="f855b-194">对于使用控制台试验新 JavaScript 代码的 Web 开发人员来说，无法重新声明是一种常见的麻烦。</span><span class="sxs-lookup"><span data-stu-id="f855b-194">The inability to redeclare was a common annoyance for web developers who use the Console to experiment with new JavaScript code.</span></span>  

> [!WARNING]
> <span data-ttu-id="f855b-195">在控制台外部或单个控制台输入中的脚本中重新声明或 `let` `class` 语句仍会导致 `SyntaxError` .</span><span class="sxs-lookup"><span data-stu-id="f855b-195">Redeclaring a `let` or `class` statement in a script outside of the Console or within a single Console input still causes a `SyntaxError`.</span></span>  

<span data-ttu-id="f855b-196">例如，以前，当使用重新声明本地变量时， `let` 控制台引发错误：</span><span class="sxs-lookup"><span data-stu-id="f855b-196">For example, previously, when re-declaring a local variable with `let`, the Console threw an error:</span></span>  

:::image type="complex" source="../../images/2019/12/letbefore.msft.png" alt-text="Microsoft Edge 79 中的控制台显示允许重新声明失败" lightbox="../../images/2019/12/letbefore.msft.png":::
   <span data-ttu-id="f855b-198">Microsoft \*\*\*\* Edge 79 中的控制台显示允许重新声明失败</span><span class="sxs-lookup"><span data-stu-id="f855b-198">The **Console** in Microsoft Edge 79 showing that the let re-declaration fails</span></span>  
:::image-end:::  

<span data-ttu-id="f855b-199">现在，控制台允许重新声明：</span><span class="sxs-lookup"><span data-stu-id="f855b-199">Now, the Console allows the redeclaration:</span></span>  

:::image type="complex" source="../../images/2019/12/letafter.msft.png" alt-text="Microsoft Edge 80 中的控制台显示允许重新声明成功" lightbox="../../images/2019/12/letafter.msft.png":::
   <span data-ttu-id="f855b-201">Microsoft \*\*\*\* Edge 80 中的控制台显示允许重新声明成功</span><span class="sxs-lookup"><span data-stu-id="f855b-201">The **Console** in Microsoft Edge 80 showing that the let re-declaration succeeds</span></span>  
:::image-end:::  

<span data-ttu-id="f855b-202">Chromium [问题#1004193][CR1004193]</span><span class="sxs-lookup"><span data-stu-id="f855b-202">Chromium issue [#1004193][CR1004193]</span></span>  

### <a name="improved-webassembly-debugging"></a><span data-ttu-id="f855b-203">改进的 WebAssembly 调试</span><span class="sxs-lookup"><span data-stu-id="f855b-203">Improved WebAssembly debugging</span></span>  

<span data-ttu-id="f855b-204">DevTools 已开始支持 [了 DEBUGG 调试标准][DwarfHome]，这意味着增加了对在 DevTools 中单步执行代码、设置断点和解析源语言中的堆栈跟踪的支持。</span><span class="sxs-lookup"><span data-stu-id="f855b-204">DevTools has started to support the [DWARF Debugging Standard][DwarfHome], which means increased support for stepping over code, setting breakpoints, and resolving stack traces in your source languages within DevTools.</span></span>  

<!-- [TODO: Add this link back] -->  
<!--Check out [Improved WebAssembly debugging in Microsoft Edge DevTools][201912Webassembly] for the full story.  -->  

<!-- [TODO: Replace this image with screenshot in Edge] -->  
<!--
:::image type="complex" source="../../images/2019/12/wasm.msft.png" alt-text="The new DWARF-powered WebAssembly debugging" lightbox="../../images/2019/12/wasm.msft.png":::
   The new DWARF-powered WebAssembly debugging  
:::image-end:::  
-->  

### <a name="network-panel-updates"></a><span data-ttu-id="f855b-205">网络面板更新</span><span class="sxs-lookup"><span data-stu-id="f855b-205">Network panel updates</span></span>  

#### <a name="request-initiator-chains-in-the-initiator-panel"></a><span data-ttu-id="f855b-206">请求发起人面板中的发起人链</span><span class="sxs-lookup"><span data-stu-id="f855b-206">Request Initiator Chains in the Initiator panel</span></span>  

<span data-ttu-id="f855b-207">现在，你能够将网络请求的发起方和依赖项作为嵌套列表进行查看。</span><span class="sxs-lookup"><span data-stu-id="f855b-207">You are now able to view the initiators and dependencies of a network request as a nested list.</span></span>  <span data-ttu-id="f855b-208">这可以帮助您了解请求资源的原因，或特定资源 \ (（如脚本\) ）引起的网络活动。</span><span class="sxs-lookup"><span data-stu-id="f855b-208">This may help you understand why a resource was requested, or what network activity a certain resource \(such as a script\) caused.</span></span>  

:::image type="complex" source="../../images/2019/12/initiators.msft.png" alt-text="发起人面板中的请求发起人链" lightbox="../../images/2019/12/initiators.msft.png":::
   <span data-ttu-id="f855b-210">发起人面板中的请求 **发起人** 链</span><span class="sxs-lookup"><span data-stu-id="f855b-210">A Request Initiator Chain in the **Initiator** panel</span></span>  
:::image-end:::  

<span data-ttu-id="f855b-211">在 ["网络"面板中][DevToolsNetworkIndex]记录网络活动后，选择一个资源，然后导航到发起 **人面板** 以查看 **请求发起人链**：</span><span class="sxs-lookup"><span data-stu-id="f855b-211">After [logging network activity in the Network panel][DevToolsNetworkIndex], choose a resource and then navigate to the **Initiator** panel to view the **Request Initiator Chain**:</span></span>  

*   <span data-ttu-id="f855b-212">已 **检查的资源为** 粗体。</span><span class="sxs-lookup"><span data-stu-id="f855b-212">The **inspected resource** is bold.</span></span>  <span data-ttu-id="f855b-213">在以上屏幕截图中 `ai.2.min.js` ，是已检查的资源。</span><span class="sxs-lookup"><span data-stu-id="f855b-213">In the screenshot above, `ai.2.min.js` is the inspected resource.</span></span>  
*   <span data-ttu-id="f855b-214">所检查的资源上方的资源是 **发起者**。</span><span class="sxs-lookup"><span data-stu-id="f855b-214">The resources above the inspected resource are the **initiators**.</span></span>  <span data-ttu-id="f855b-215">在上一张屏幕截图 `https://www.microsoftedgeinsider.com` 中，是 . `ai.2.min.js`</span><span class="sxs-lookup"><span data-stu-id="f855b-215">In the screenshot above, `https://www.microsoftedgeinsider.com` is the initiator of `ai.2.min.js`.</span></span>  <span data-ttu-id="f855b-216">换句话说， `https://www.microsoftedgeinsider.com` 导致网络请求 `ai.2.min.js` 。</span><span class="sxs-lookup"><span data-stu-id="f855b-216">In other words, `https://www.microsoftedgeinsider.com` caused the network request for `ai.2.min.js`.</span></span>  
*   <span data-ttu-id="f855b-217">所检查的资源下方的资源 **是依赖项**。</span><span class="sxs-lookup"><span data-stu-id="f855b-217">The resources below the inspected resource are the **dependencies**.</span></span>  <span data-ttu-id="f855b-218">在上方的屏幕截图中 `https://dc.services.visualstudio.com/v2/track` ，是依赖的 `ai.2.min.js` 。</span><span class="sxs-lookup"><span data-stu-id="f855b-218">In the screenshot above, `https://dc.services.visualstudio.com/v2/track` is a dependency of `ai.2.min.js`.</span></span>  <span data-ttu-id="f855b-219">换句话说， `ai.2.min.js` 导致网络请求 `https://dc.services.visualstudio.com/v2/track` 。</span><span class="sxs-lookup"><span data-stu-id="f855b-219">In other words, `ai.2.min.js` caused the network request for `https://dc.services.visualstudio.com/v2/track`.</span></span>  

> [!NOTE]
> <span data-ttu-id="f855b-220">通过按住然后将鼠标悬停在网络资源上，也可以访问发起人 `Shift` 信息和依赖信息。</span><span class="sxs-lookup"><span data-stu-id="f855b-220">Initiator and dependency information may also be accessed by holding `Shift` and then hovering over network resources.</span></span>  <span data-ttu-id="f855b-221">导航到["查看发起人"和"依赖项"。][DevToolsNetworkReferenceViewInitiatorsDependencies]</span><span class="sxs-lookup"><span data-stu-id="f855b-221">Navigate to [View initiators and dependencies][DevToolsNetworkReferenceViewInitiatorsDependencies].</span></span>  

<span data-ttu-id="f855b-222">Chromium 问题 [#842488][CR842488]</span><span class="sxs-lookup"><span data-stu-id="f855b-222">Chromium issue [#842488][CR842488]</span></span>  

#### <a name="highlight-the-selected-network-request-in-the-overview"></a><span data-ttu-id="f855b-223">在概述中突出显示选定的网络请求</span><span class="sxs-lookup"><span data-stu-id="f855b-223">Highlight the selected network request in the Overview</span></span>  

<span data-ttu-id="f855b-224">选择要检查的网络资源后，网络面板现在在概述中为该资源设置蓝色 **边框**。</span><span class="sxs-lookup"><span data-stu-id="f855b-224">After you choose a network resource in order to inspect it, the Network panel now puts a blue border around that resource in the **Overview**.</span></span>  <span data-ttu-id="f855b-225">这可以帮助您检测网络请求是早于还是晚于预期发生。</span><span class="sxs-lookup"><span data-stu-id="f855b-225">This is able to help you detect if the network request is happening earlier or later than expected.</span></span>  

:::image type="complex" source="../../images/2019/12/overview.msft.png" alt-text="突出显示已检查资源的"概述"窗格" lightbox="../../images/2019/12/overview.msft.png":::
   <span data-ttu-id="f855b-227">突出显示 **已** 检查资源的"概述"窗格</span><span class="sxs-lookup"><span data-stu-id="f855b-227">The **Overview** pane highlighting the inspected resource</span></span>  
:::image-end:::  

<span data-ttu-id="f855b-228">Chromium 问题 [#988253][CR988253]</span><span class="sxs-lookup"><span data-stu-id="f855b-228">Chromium issue [#988253][CR988253]</span></span>  

#### <a name="url-and-path-columns-in-the-network-panel"></a><span data-ttu-id="f855b-229">网络面板中的 URL 和路径列</span><span class="sxs-lookup"><span data-stu-id="f855b-229">URL and path columns in the Network panel</span></span>  

<span data-ttu-id="f855b-230">使用"**网络"** 工具中的新"路径\*\*\*\*"和 **"URL"** 列显示每个网络资源的绝对路径或完整 URL。</span><span class="sxs-lookup"><span data-stu-id="f855b-230">Use the new **Path** and **URL** columns in the **Network** tool to display the absolute path or full URL of each network resource.</span></span>  

:::image type="complex" source="../../images/2019/12/columns.msft.png" alt-text="网络面板中的新路径和 URL 列" lightbox="../../images/2019/12/columns.msft.png":::
   <span data-ttu-id="f855b-232">网络工具中的 **新路径和** URL 列</span><span class="sxs-lookup"><span data-stu-id="f855b-232">The new Path and URL columns in the **Network** tool</span></span>  
:::image-end:::  

<span data-ttu-id="f855b-233">若要显示新列，请将鼠标悬停在 **"瀑布**"表标题上，打开上下文菜单 \ (righ-click\) ，然后选择 **"路径**"或 **"URL"。**</span><span class="sxs-lookup"><span data-stu-id="f855b-233">To display the new columns, hover on the **Waterfall** table header, open the contextual menu \(righ-click\), and choose **Path** or **URL**.</span></span>  

<span data-ttu-id="f855b-234">Chromium 问题 [#993366][CR993366]</span><span class="sxs-lookup"><span data-stu-id="f855b-234">Chromium issue [#993366][CR993366]</span></span>  

#### <a name="updated-user-agent-strings"></a><span data-ttu-id="f855b-235">更新User-Agent字符串</span><span class="sxs-lookup"><span data-stu-id="f855b-235">Updated User-Agent strings</span></span>  

<span data-ttu-id="f855b-236">DevTools 支持通过User-Agent条件 **面板设置自定义** 字符串。</span><span class="sxs-lookup"><span data-stu-id="f855b-236">DevTools supports setting a custom User-Agent string through the **Network Conditions** panel.</span></span>  <span data-ttu-id="f855b-237">字符串User-Agent影响附加到网络资源的 HTTP 标头，以及 `User-Agent` `navigator.userAgent` 值 。</span><span class="sxs-lookup"><span data-stu-id="f855b-237">The User-Agent string affects the `User-Agent` HTTP header attached to network resources, and also the value of `navigator.userAgent`.</span></span>  

<span data-ttu-id="f855b-238">预定义User-Agent字符串已更新以反映新式浏览器版本。</span><span class="sxs-lookup"><span data-stu-id="f855b-238">The predefined User-Agent strings have been updated to reflect modern browser versions.</span></span>  

:::image type="complex" source="../../images/2019/12/useragent.msft.png" alt-text=""网络条件"面板中的"用户代理"菜单" lightbox="../../images/2019/12/useragent.msft.png":::
   <span data-ttu-id="f855b-240">"网络条件"面板 **中的"用户代理"** 菜单</span><span class="sxs-lookup"><span data-stu-id="f855b-240">The User Agent menu in the **Network Conditions** panel</span></span>  
:::image-end:::  

<span data-ttu-id="f855b-241">若要访问 **网络条件**， [请打开命令菜单][DevToolsCommandMenuIndex] 并运行 `Show Network Conditions` 该命令。</span><span class="sxs-lookup"><span data-stu-id="f855b-241">To access **Network Conditions**, [open the Command Menu][DevToolsCommandMenuIndex] and run the `Show Network Conditions` command.</span></span>  

> [!NOTE]
> <span data-ttu-id="f855b-242">还可以在 [设备User-Agent设置字符串][DevToolsDeviceModeIndex]。</span><span class="sxs-lookup"><span data-stu-id="f855b-242">You may also [set User-Agent strings in Device Mode][DevToolsDeviceModeIndex].</span></span>  

<span data-ttu-id="f855b-243">Chromium 问题 [#1029031][CR1029031]</span><span class="sxs-lookup"><span data-stu-id="f855b-243">Chromium issue [#1029031][CR1029031]</span></span>  

### <a name="audits-panel-updates"></a><span data-ttu-id="f855b-244">审核面板更新</span><span class="sxs-lookup"><span data-stu-id="f855b-244">Audits panel updates</span></span>  

#### <a name="new-configuration-ui"></a><span data-ttu-id="f855b-245">新配置 UI</span><span class="sxs-lookup"><span data-stu-id="f855b-245">New configuration UI</span></span>  

<span data-ttu-id="f855b-246">配置 UI 具有新的响应式设计，并且已简化限制配置选项。</span><span class="sxs-lookup"><span data-stu-id="f855b-246">The configuration UI has a new, responsive design, and the throttling configuration options have been simplified.</span></span>  <span data-ttu-id="f855b-247">有关限制 UI 更改的信息，请导航到["审核面板限制"。][GitHubGoogleChromeDevToolsAuditsPanelThrottling]</span><span class="sxs-lookup"><span data-stu-id="f855b-247">For more information on the throttling UI changes, navigate to [Audits Panel Throttling][GitHubGoogleChromeDevToolsAuditsPanelThrottling].</span></span>  

:::image type="complex" source="../../images/2019/12/start.msft.png" alt-text="新的配置 UI" lightbox="../../images/2019/12/start.msft.png":::
   <span data-ttu-id="f855b-249">新的配置 UI</span><span class="sxs-lookup"><span data-stu-id="f855b-249">The new configuration UI</span></span>  
:::image-end:::  

### <a name="coverage-tool-updates"></a><span data-ttu-id="f855b-250">覆盖工具更新</span><span class="sxs-lookup"><span data-stu-id="f855b-250">Coverage tool updates</span></span>  

#### <a name="per-function-or-per-block-coverage-modes"></a><span data-ttu-id="f855b-251">每个函数或每个块覆盖模式</span><span class="sxs-lookup"><span data-stu-id="f855b-251">Per-function or per-block coverage modes</span></span>  

<span data-ttu-id="f855b-252">覆盖[工具][DevToolsCoverageIndex]有一个新的下拉菜单，允许你指定是按函数还是按块**收集代码\*\*\*\*覆盖数据**。</span><span class="sxs-lookup"><span data-stu-id="f855b-252">The [Coverage][DevToolsCoverageIndex] tool has a new dropdown menu that lets you specify whether code coverage data should be collected **per function** or **per block**.</span></span>  <span data-ttu-id="f855b-253">**每个块** 范围更加详细，但收集成本也更高。</span><span class="sxs-lookup"><span data-stu-id="f855b-253">**Per block** coverage is more detailed but also far more expensive to collect.</span></span>  <span data-ttu-id="f855b-254">默认情况下，DevTools **现在使用** 每个函数范围。</span><span class="sxs-lookup"><span data-stu-id="f855b-254">DevTools uses **per function** coverage by default now.</span></span>  

> [!CAUTION]
> <span data-ttu-id="f855b-255">你可能会注意到 HTML 文件中存在较大的代码覆盖差异，具体取决于是按\*\*\*\* 函数还是**按块模式**使用。</span><span class="sxs-lookup"><span data-stu-id="f855b-255">You may notice large code coverage differences in HTML files depending on whether you use **per function** or **per block** mode.</span></span>  <span data-ttu-id="f855b-256">当按 **函数模式** 使用时，HTML 文件中内联脚本将被视为函数。</span><span class="sxs-lookup"><span data-stu-id="f855b-256">When using **per function** mode, inline scripts in HTML files are treated as functions.</span></span>  <span data-ttu-id="f855b-257">如果脚本完全运行，则 DevTools 将整个脚本标记为已用代码。</span><span class="sxs-lookup"><span data-stu-id="f855b-257">If the script runs at all then DevTools marks the entire script as used code.</span></span>  <span data-ttu-id="f855b-258">只有在脚本完全不运行时，DevTools 才将脚本标记为未使用的代码。</span><span class="sxs-lookup"><span data-stu-id="f855b-258">Only if the script does not run at all does DevTools mark the script as unused code.</span></span>  

:::image type="complex" source="../../images/2019/12/modes.msft.png" alt-text="覆盖模式下拉菜单" lightbox="../../images/2019/12/modes.msft.png":::
   <span data-ttu-id="f855b-260">覆盖模式下拉菜单</span><span class="sxs-lookup"><span data-stu-id="f855b-260">The coverage mode dropdown menu</span></span>  
:::image-end:::  

#### <a name="coverage-must-now-be-initiated-by-a-page-refresh"></a><span data-ttu-id="f855b-261">现在必须通过页面刷新启动覆盖</span><span class="sxs-lookup"><span data-stu-id="f855b-261">Coverage must now be initiated by a page refresh</span></span>  

<span data-ttu-id="f855b-262">在未刷新页面的情况下切换代码覆盖已被删除，因为覆盖数据不可靠。</span><span class="sxs-lookup"><span data-stu-id="f855b-262">Toggling code coverage without a page refresh has been removed because the coverage data was unreliable.</span></span>  <span data-ttu-id="f855b-263">例如，如果运行时在很长一段时间之前且 V8 垃圾回收器已清理它，则函数可能会报告为未使用。</span><span class="sxs-lookup"><span data-stu-id="f855b-263">For example, a function may be reported as unused if the runtime was a long time ago and the V8 garbage collector has cleaned it up.</span></span>  

<span data-ttu-id="f855b-264">Chromium 问题 [#1004203][CR1004203]</span><span class="sxs-lookup"><span data-stu-id="f855b-264">Chromium issue [#1004203][CR1004203]</span></span>  

## <a name="download-the-microsoft-edge-preview-channels"></a><span data-ttu-id="f855b-265">下载 Microsoft Edge 预览频道</span><span class="sxs-lookup"><span data-stu-id="f855b-265">Download the Microsoft Edge preview channels</span></span>  

<span data-ttu-id="f855b-266">如果你使用的是 Windows 或 macOS，请考虑使用 [ Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels] 作为默认开发浏览器。</span><span class="sxs-lookup"><span data-stu-id="f855b-266">If you are on Windows or macOS, consider using the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] as your default development browser.</span></span>  <span data-ttu-id="f855b-267">预览频道使你能够访问最新的 DevTools 功能。</span><span class="sxs-lookup"><span data-stu-id="f855b-267">The preview channels give you access to the latest DevTools features.</span></span>  

## <a name="getting-in-touch-with-microsoft-edge-devtools-team"></a><span data-ttu-id="f855b-268">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="f855b-268">Getting in touch with Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- image links -->  

<!--[../../images/2019/12/wasm.msft.png]: ../../images/2019/12/wasm.msft.png "Figure: The new DWARF-powered WebAssembly debugging"  -->

<!-- links -->  

[DevToolsCommandMenuIndex]: /microsoft-edge/devtools-guide-chromium/command-menu/index "使用 Microsoft Edge DevTools 命令菜单运行|Microsoft Docs"  
[DevToolsCoverageIndex]: /microsoft-edge/devtools-guide-chromium/coverage/index "使用 Microsoft Edge 开发人员工具中的"覆盖"工具查找未使用的 JavaScript 和 CSS |Microsoft Docs"  
[DevToolsDeviceModeIndex]: /microsoft-edge/devtools-guide-chromium/device-mode/index#simulate-a-mobile-viewport "模拟移动视口 - 在 Microsoft Edge DevTools |Microsoft Docs"  
[DevToolsNetworkIndex]: /microsoft-edge/devtools-guide-chromium/network/index "检查 Microsoft Edge DevTools |Microsoft Docs"  
[DevToolsNetworkReferenceViewInitiatorsDependencies]: /microsoft-edge/devtools-guide-chromium/network/reference#view-initiators-and-dependencies "查看发起方和依赖项 - 网络分析参考|Microsoft Docs"  
[DevGuideEdgeHtmlWhatsNew]: /microsoft-edge/dev-guide/whats-new "EdgeHTML |Microsoft Docs"  
[VisualStudioCodeDebuggerEdgeExtension]: /microsoft-edge/visual-studio-code/debugger-for-edge "Microsoft Edge 代码扩展Visual Studio调试器|Microsoft Docs"  
[VisualStudioCodeElementEdgeExtension]: /microsoft-edge/visual-studio-code/elements-for-edge "Microsoft Edge 代码扩展Visual Studio元素|Microsoft Docs"  

<!--  [201912Webassembly]: webassembly.md "Improved WebAssembly debugging in Microsoft Edge DevTools"  -->  

[CR842488]: https://crbug.com/842488 "将"发起人"字段添加到"标题"选项卡|Chromium Bugs"  
[CR988253]: https://crbug.com/988253 "Bug DevTools - 网络请求与时间线图|Chromium Bugs"  
[CR993366]: https://crbug.com/993366 "请在网络面板请求列表中显示 URL 的路径部分|Chromium Bugs"  
[CR1004193]: https://crbug.com/1004193 "V8 模式的 REPL |Chromium Bugs"  
[CR1004203]: https://crbug.com/1004203 "使代码覆盖成为出色的|Chromium Bugs"  
[CR1029031]: https://crbug.com/1029031 "UA 字符串正在变得过时|Chromium Bugs" 
[CR963183]: https://crbug.com/963183 "DevTools 与 WCAG 不兼容|Chromium Bugs"
[CR941561]: https://crbug.com/941561 "DevTools |Chromium Bugs"
[CR987787]: https://crbug.com/987787 "Dom 3D 视图|Chromium Bugs"

[AccessibilityInsights]: https://aka.ms/a11yinsights "辅助功能见解"  

[DwarfHome]: https://dwarfstd.org "月形家庭"  
[GitHubGoogleChromeDevToolsAuditsPanelThrottling]: https://github.com/GoogleChrome/lighthouse/blob/master/docs/throttling.md#devtools-audits-panel-throttling "DevTools 的审核面板限制 - GoogleChrome/lighthouse |GitHub"  
[GitHubMicrosoftDocsEdgeDeveloperNewIssue]: https://aka.ms/edgedevtoolsdocs/feedback "新问题 - MicrosoftDocs/edge-developer"  
[MicrosoftEdgePreviewChannels]: https://aka.ms/microsoftedge "Microsoft Edge 预览频道"  
[MicrosoftEdgeInsiderAddons]: https://aka.ms/webhint/edge-extension "Microsoft Edge 预览体验成员加载项"  
[MicrosoftVisualStudio]: https://aka.ms/vs "Visual Studio"  
[MicrosoftVisualStudioBlogDebugJavascript]: https://aka.ms/vs/debug-edge "从 Microsoft Edge 中调试 JavaScript Visual Studio |Visual Studio博客"  
[MicrosoftVisualStudioDownloads]: https://aka.ms/vs/download "下载 Visual Studio 2019 for Windows \& Mac"  
[MDNDocumentObjectModel]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model "文档对象模型 (DOM) |MDN"  
[MDNZIndex]: https://developer.mozilla.org/docs/Web/CSS/z-index "z-index |MDN"  
[PostTweetEdgeDevTools]: https://aka.ms/tweet/edgedevtools "@EdgeDevTools | 发布推文"  
[EdgeDevToolsTwitterAccount]: https://aka.ms/twitter/edgedevtools "@EdgeDevTools Twitter 帐户"
[VisualStudioCode]: https://aka.ms/vscode "Visual Studio代码"  
[VisualStudioMarketplaceDebuggerEdge]: https://aka.ms/debugger4code "适用于 Microsoft Edge 的调试器 - Visual Studio Marketplace"  
[VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension]: https://aka.ms/elements4code "Microsoft Edge 的元素 \ (Chromium\) - Visual Studio Marketplace"  
[VisualStudioMarketplaceWebhintExtension]: https://aka.ms/webhint4code "webhint - Visual Studio Marketplace"
[Webhint]: https://aka.ms/webhint "webhint"  
[WebhintBrowserExtension]: https://aka.ms/webhint/browser-extension "Webhint 浏览器扩展|webhint 文档"  
[WebhintVisualStudioCodeExtension]: https://aka.ms/webhint/code-extension "Webhint Visual Studio代码扩展|webhint 文档"  
[TrackingPrevention]: https://aka.ms/microsoftedge/tracking-prevention-blog "改进 Microsoft Edge 博客文章中的跟踪防护"
[TheWebWeWant]: https://aka.ms/webwewant "我们想要的网络"

> [!NOTE]
> <span data-ttu-id="f855b-308">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="f855b-308">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="f855b-309">原始页面位于[此处](https://developers.google.com/web/updates/2019/12/devtools/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="f855b-309">The original page is found [here](https://developers.google.com/web/updates/2019/12/devtools/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="f855b-311">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="f855b-311">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
