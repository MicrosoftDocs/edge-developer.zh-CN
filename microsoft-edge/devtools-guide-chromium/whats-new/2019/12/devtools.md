---
description: 辅助功能改进、在其他语言中使用 DevTools 等。
title: 'DevTools (Microsoft Edge 80) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/11/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 58e5bf43720c7ba94a721804eb44d82ba657b599
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564992"
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
# <a name="whats-new-in-devtools-microsoft-edge-80"></a><span data-ttu-id="07d85-104">DevTools (Microsoft Edge 80) </span><span class="sxs-lookup"><span data-stu-id="07d85-104">What's new in DevTools (Microsoft Edge 80)</span></span>  

## <a name="announcements-from-the-microsoft-edge-devtools-team"></a><span data-ttu-id="07d85-105">来自 Microsoft Edge 开发人员工具团队公告</span><span class="sxs-lookup"><span data-stu-id="07d85-105">Announcements from the Microsoft Edge DevTools team</span></span>  

<span data-ttu-id="07d85-106">以下各节列出了你可能从 DevTools 团队中错过Microsoft Edge通知。</span><span class="sxs-lookup"><span data-stu-id="07d85-106">The following sections are a list of announcements you may have missed from the Microsoft Edge DevTools team.</span></span>  <span data-ttu-id="07d85-107">请查看公告以试用 DevTools、Microsoft Visual Studio代码扩展等中的新功能。</span><span class="sxs-lookup"><span data-stu-id="07d85-107">Check out the announcements to try new features in the DevTools, Microsoft Visual Studio Code extensions, and more.</span></span>  <span data-ttu-id="07d85-108">若要了解有关开发人员工具中的所有最新功能和最强大功能的最新动态，请下载 [Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels]并[在 Twitter 上关注我们][EdgeDevToolsTwitterAccount]。</span><span class="sxs-lookup"><span data-stu-id="07d85-108">To stay up to date on all the latest and greatest features in your developer tools, download the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] and [follow us on Twitter][EdgeDevToolsTwitterAccount].</span></span>  

### <a name="accessibility-improvements-to-the-devtools"></a><span data-ttu-id="07d85-109">对 DevTools 的辅助功能改进</span><span class="sxs-lookup"><span data-stu-id="07d85-109">Accessibility improvements to the DevTools</span></span>  

<span data-ttu-id="07d85-110">DevTools 团队已对 Chromium 进行 170 次更改，以解决 DevTools 中的高影响颜色对比度、键盘和屏幕阅读器问题。</span><span class="sxs-lookup"><span data-stu-id="07d85-110">The DevTools team has contributed 170 changes to Chromium to address high-impact color contrast, keyboard, and screen reader issues in the DevTools.</span></span>  <span data-ttu-id="07d85-111">每个生成 Web 的开发人员都应能够使用 DevTools。</span><span class="sxs-lookup"><span data-stu-id="07d85-111">Every developer building the web should be able to use the DevTools.</span></span>  

:::image type="complex" source="../../images/2019/12/a11y-performance-tool.msft.gif" alt-text="具有键盘导航和屏幕阅读器改进的 DevTools 中的性能工具" lightbox="../../images/2019/12/a11y-performance-tool.msft.gif":::
   <span data-ttu-id="07d85-113">具有 **键盘** 导航和屏幕阅读器改进的 DevTools 中的性能工具</span><span class="sxs-lookup"><span data-stu-id="07d85-113">The **Performance** tool in the DevTools with the keyboard navigation and screen reader improvements</span></span>  
:::image-end:::  

<span data-ttu-id="07d85-114">想要了解如何使网页可供所有用户访问？</span><span class="sxs-lookup"><span data-stu-id="07d85-114">Want to learn how to make your web page accessible to all of your users?</span></span>  <span data-ttu-id="07d85-115">下载[辅助功能见解][AccessibilityInsights]和[webhint][WebhintBrowserExtension]扩展，Microsoft Edge开始操作。</span><span class="sxs-lookup"><span data-stu-id="07d85-115">Download the [Accessibility Insights][AccessibilityInsights] and [webhint][WebhintBrowserExtension] extensions for Microsoft Edge to get started.</span></span>  

<span data-ttu-id="07d85-116">如果使用屏幕阅读器或键盘在 DevTools 中导航，请通过向我们发推文[][PostTweetEdgeDevTools]或选择"发送反馈"图标发送[反馈](#getting-in-touch-with-microsoft-edge-devtools-team)！</span><span class="sxs-lookup"><span data-stu-id="07d85-116">If you use screen readers or the keyboard to navigate around the DevTools, send your feedback by [tweeting][PostTweetEdgeDevTools] at us orchoosing the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!</span></span>  

<span data-ttu-id="07d85-117">Chromium 问题 [#963183][CR963183]</span><span class="sxs-lookup"><span data-stu-id="07d85-117">Chromium issue [#963183][CR963183]</span></span>  

### <a name="using-the-devtools-in-other-languages"></a><span data-ttu-id="07d85-118">以其他语言使用 DevTools</span><span class="sxs-lookup"><span data-stu-id="07d85-118">Using the DevTools in other languages</span></span>  

<span data-ttu-id="07d85-119">许多开发人员使用其他开发人员工具（如 StackOverflow 和 Visual Studio Code，使用其本地语言，而不只是使用英语。</span><span class="sxs-lookup"><span data-stu-id="07d85-119">Many developers use other developer tools, like StackOverflow and Visual Studio Code, in their native language, not just in English.</span></span>  <span data-ttu-id="07d85-120">我们很高兴宣布 DevTools 的本地化，你现在可以使用英语之外 10 种语言之一：</span><span class="sxs-lookup"><span data-stu-id="07d85-120">We’re excited to announce localization for the DevTools, which you are now able to use in one of 10 languages besides English:</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="07d85-121">中文 \(Simplified\) - &#20013;&#25991;&#65288;&#31616;&#20307;&#65289;</span><span class="sxs-lookup"><span data-stu-id="07d85-121">Chinese \(Simplified\) - &#20013;&#25991;&#65288;&#31616;&#20307;&#65289;</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="07d85-122">繁体 (中文\) - &#20013;&#25991;&#65288;&#32321;&#39636;&#65289;</span><span class="sxs-lookup"><span data-stu-id="07d85-122">Chinese \(Traditional\) - &#20013;&#25991;&#65288;&#32321;&#39636;&#65289;</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      <span data-ttu-id="07d85-123">法语 –&#231;语</span><span class="sxs-lookup"><span data-stu-id="07d85-123">French – fran&#231;ais</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="07d85-124">德语 - 德语</span><span class="sxs-lookup"><span data-stu-id="07d85-124">German - deutsch</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      <span data-ttu-id="07d85-125">意大利语 - 意大利语</span><span class="sxs-lookup"><span data-stu-id="07d85-125">Italian - italiano</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="07d85-126">日语 - &#26085;&#26412;&#35486;</span><span class="sxs-lookup"><span data-stu-id="07d85-126">Japanese - &#26085;&#26412;&#35486;</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      <span data-ttu-id="07d85-127">朝鲜语 - &#54620;&#44397;&#50612;</span><span class="sxs-lookup"><span data-stu-id="07d85-127">Korean - &#54620;&#44397;&#50612;</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="07d85-128">葡萄牙语 - 图卢&#234;语</span><span class="sxs-lookup"><span data-stu-id="07d85-128">Portuguese - portugu&#234;s</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      <span data-ttu-id="07d85-129">俄语 – &#1088;&#1091;&#1089;&#1089;&#1082;&#1080;&#1081;</span><span class="sxs-lookup"><span data-stu-id="07d85-129">Russian – &#1088;&#1091;&#1089;&#1089;&#1082;&#1080;&#1081;</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="07d85-130">西班牙语 - 电子邮件&#241;ol</span><span class="sxs-lookup"><span data-stu-id="07d85-130">Spanish - espa&#241;ol</span></span>
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

<span data-ttu-id="07d85-131">导航到 `edge://flags` ，将 **"启用本地化开发人员工具"标志**设置为 **"已启用"。**</span><span class="sxs-lookup"><span data-stu-id="07d85-131">Navigate to `edge://flags` and set the **Enable localized Developer Tools** flag to **Enabled**.</span></span>  <span data-ttu-id="07d85-132">此外，将 **"开发人员工具实验"标志**设置为 **"已启用"。**</span><span class="sxs-lookup"><span data-stu-id="07d85-132">Also set the **Developer Tools experiments** flag to **Enabled**.</span></span>  <span data-ttu-id="07d85-133">重新启动Microsoft Edge并打开 DevTools。</span><span class="sxs-lookup"><span data-stu-id="07d85-133">Restart Microsoft Edge and open the DevTools.</span></span>  <!-- Select `F1` in the DevTools or navigate to Settings > Experiments and check the **Match browser language** checkbox.  -->  <span data-ttu-id="07d85-134">DevTools 与用于在 中Microsoft Edge语言 `edge://settings/languages` 匹配。</span><span class="sxs-lookup"><span data-stu-id="07d85-134">The DevTools match the language you use for Microsoft Edge in `edge://settings/languages`.</span></span>  

:::image type="complex" source="../../images/2019/12/localized-devtools.msft.png" alt-text="德语的 DevTools" lightbox="../../images/2019/12/localized-devtools.msft.png":::
   <span data-ttu-id="07d85-136">德语的 DevTools</span><span class="sxs-lookup"><span data-stu-id="07d85-136">The DevTools in German</span></span>  
:::image-end:::  

<span data-ttu-id="07d85-137">如果你想要以与可用版本不同的语言使用 DevTools，请通过我们的推文或选择[][PostTweetEdgeDevTools]"发送反馈["](#getting-in-touch-with-microsoft-edge-devtools-team)图标。</span><span class="sxs-lookup"><span data-stu-id="07d85-137">If you want to use the DevTools in a different language than the ones that are available, [tweet][PostTweetEdgeDevTools] at us or choose the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon.</span></span>  

<span data-ttu-id="07d85-138">Chromium问题[#941561][CR941561]</span><span class="sxs-lookup"><span data-stu-id="07d85-138">Chromium issue [#941561][CR941561]</span></span>  

### <a name="webhint-microsoft-edge-extension"></a><span data-ttu-id="07d85-139">webhint Microsoft Edge扩展</span><span class="sxs-lookup"><span data-stu-id="07d85-139">webhint Microsoft Edge extension</span></span>  

<span data-ttu-id="07d85-140">Webhint Microsoft Edge扩展允许你在 DevTools 中轻松扫描网页并获取有关辅助功能、浏览器兼容性、安全性、性能等的反馈。</span><span class="sxs-lookup"><span data-stu-id="07d85-140">The webhint Microsoft Edge extension allows you to easily scan your web page and get feedback on accessibility, browser compatibility, security, performance, and more within the DevTools.</span></span>  <span data-ttu-id="07d85-141">有关详细信息，请参阅 [https://webhint.io][Webhint] 。</span><span class="sxs-lookup"><span data-stu-id="07d85-141">Read more at [https://webhint.io][Webhint].</span></span>  

:::image type="complex" source="../../images/2019/12/webhint-browser-extension.msft.png" alt-text="安装 Webhint 浏览器扩展时 DevTools 中的 Hints 工具" lightbox="../../images/2019/12/webhint-browser-extension.msft.png":::
   <span data-ttu-id="07d85-143">安装 **Webhint** 浏览器扩展时 DevTools 中的 Hints 工具</span><span class="sxs-lookup"><span data-stu-id="07d85-143">The **Hints** tool in the DevTools when the webhint browser extension is installed</span></span>  
:::image-end:::  

<span data-ttu-id="07d85-144">[尝试 webhint 浏览器扩展Microsoft Edge。][MicrosoftEdgeInsiderAddons]</span><span class="sxs-lookup"><span data-stu-id="07d85-144">[Try the webhint browser extension in Microsoft Edge][MicrosoftEdgeInsiderAddons].</span></span>  <span data-ttu-id="07d85-145">安装扩展后，打开 DevTools 并选择 **提示** 工具。</span><span class="sxs-lookup"><span data-stu-id="07d85-145">Once you install the extension, open the DevTools and choose the **Hints** tool.</span></span>  <span data-ttu-id="07d85-146">从此处运行可自定义的网站扫描。</span><span class="sxs-lookup"><span data-stu-id="07d85-146">From here, run a customizable site scan.</span></span>  <span data-ttu-id="07d85-147">请 [前往][WebhintBrowserExtension] webhint.io 了解更多信息。</span><span class="sxs-lookup"><span data-stu-id="07d85-147">Head over to [webhint.io][WebhintBrowserExtension] to learn more.</span></span>

### <a name="3d-view"></a><span data-ttu-id="07d85-148">3D 视图</span><span class="sxs-lookup"><span data-stu-id="07d85-148">3D View</span></span>  

<span data-ttu-id="07d85-149">使用 **3D 视图** 通过浏览文档对象模型 [\(DOM\) ][MDNDocumentObjectModel] 或 [z 索引][MDNZIndex] 堆栈上下文来调试 Web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="07d85-149">Use the **3D View** to debug your web application by navigating through the [Document Object Model \(DOM\)][MDNDocumentObjectModel] or the [z-index][MDNZIndex] stacking context.</span></span>  

:::image type="complex" source="../../images/2019/12/3dview.msft.png" alt-text="DevTools 中的 3D 视图" lightbox="../../images/2019/12/3dview.msft.png":::
   <span data-ttu-id="07d85-151">DevTools 中的 **3D** 视图</span><span class="sxs-lookup"><span data-stu-id="07d85-151">The **3D View** in the DevTools</span></span>  
:::image-end:::  

<span data-ttu-id="07d85-152">若要访问 3D 视图，请导航到 `edge://flags` 并确保开发人员 **工具实验** 标记设置为 **已启用**。</span><span class="sxs-lookup"><span data-stu-id="07d85-152">To access the 3D View, navigate to `edge://flags` and ensure that the **Developer Tools experiments** flag is set to **Enabled**.</span></span>  <span data-ttu-id="07d85-153">重新启动Microsoft Edge并打开 DevTools。</span><span class="sxs-lookup"><span data-stu-id="07d85-153">Restart Microsoft Edge and open the DevTools.</span></span>  <span data-ttu-id="07d85-154">在 DevTools 中选择或打开设置实验"部分，然后打开 `F1` >  \*\*\*\*"**启用 3D 视图"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="07d85-154">Select `F1` in the DevTools or open the **Settings** > **Experiments** section, and turn on the **Enable 3D View** checkbox.</span></span>  <span data-ttu-id="07d85-155">现在，选择 `Ctrl`  +  `Shift`  +  `P` ，在**3D 视图中键入 ，** 然后选择**显示 3D 视图**。</span><span class="sxs-lookup"><span data-stu-id="07d85-155">Now, select `Ctrl` + `Shift` + `P`, type in **3D View** and select **Show 3D View**.</span></span>  

<span data-ttu-id="07d85-156">We're working on the UI and adding more functionality to the 3D View so please send us your [feedback](#getting-in-touch-with-microsoft-edge-devtools-team).</span><span class="sxs-lookup"><span data-stu-id="07d85-156">We're working on the UI and adding more functionality to the 3D View so please send us your [feedback](#getting-in-touch-with-microsoft-edge-devtools-team).</span></span>  

<span data-ttu-id="07d85-157">Chromium问题[#987787][CR987787]</span><span class="sxs-lookup"><span data-stu-id="07d85-157">Chromium issue [#987787][CR987787]</span></span>

### <a name="visual-studio-code-extensions"></a><span data-ttu-id="07d85-158">Visual Studio Code扩展</span><span class="sxs-lookup"><span data-stu-id="07d85-158">Visual Studio Code extensions</span></span>  

<span data-ttu-id="07d85-159">DevTools 团队还发布了一些适用于 Visual Studio Code[][VisualStudioCode]的扩展，让你可以直接从文本编辑器使用 DevTools 功能。</span><span class="sxs-lookup"><span data-stu-id="07d85-159">The DevTools team has also released some extensions for [Visual Studio Code][VisualStudioCode] that let you use the power of the DevTools directly from your text editor.</span></span> <span data-ttu-id="07d85-160">请查看以下扩展。</span><span class="sxs-lookup"><span data-stu-id="07d85-160">Check out the following extensions.</span></span>  

#### <a name="elements-for-microsoft-edge"></a><span data-ttu-id="07d85-161">用于Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="07d85-161">Elements for Microsoft Edge</span></span>  

<span data-ttu-id="07d85-162">通过将元素添加到 Visual Studio Code 扩展，从 Microsoft Edge (Chromium) [Visual Studio Code][VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension]使用 Elements 工具。</span><span class="sxs-lookup"><span data-stu-id="07d85-162">Use the Elements tool from within Visual Studio Code by adding the [Elements for Microsoft Edge (Chromium)][VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension] Visual Studio Code extension.</span></span>  

:::image type="complex" source="../../images/2019/12/elements-for-edge.msft.png" alt-text="使用元素扩展Visual Studio Code元素的 Microsoft Edge 工具" lightbox="../../images/2019/12/elements-for-edge.msft.png":::
   <span data-ttu-id="07d85-164">元素**工具**Visual Studio Code元素扩展Microsoft Edge元素</span><span class="sxs-lookup"><span data-stu-id="07d85-164">The **Elements** tool in Visual Studio Code using the Elements for Microsoft Edge extension</span></span>  
:::image-end:::  

<span data-ttu-id="07d85-165">有关详细信息，请查看元素[的扩展Microsoft Edge Visual Studio Code元素][VisualStudioCodeElementEdgeExtension]。</span><span class="sxs-lookup"><span data-stu-id="07d85-165">For more information, check out [Elements for Microsoft Edge Visual Studio Code extension][VisualStudioCodeElementEdgeExtension].</span></span>  

#### <a name="debugger-for-microsoft-edge"></a><span data-ttu-id="07d85-166">调试程序Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="07d85-166">Debugger for Microsoft Edge</span></span>  

<span data-ttu-id="07d85-167">使用[调试器 for Microsoft Edge][VisualStudioMarketplaceDebuggerEdge] Visual Studio Code 扩展，直接从 Visual Studio Code 调试 Microsoft Edge 中运行的 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="07d85-167">With the [Debugger for Microsoft Edge][VisualStudioMarketplaceDebuggerEdge] Visual Studio Code extension, debug JavaScript running in Microsoft Edge directly from Visual Studio Code.</span></span>  

:::image type="complex" source="../../images/2019/12/vscode-debugger.msft.png" alt-text="Microsoft Edge Extension 的调试Visual Studio Code" lightbox="../../images/2019/12/vscode-debugger.msft.png":::
   <span data-ttu-id="07d85-169">Microsoft Edge Extension 的调试Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="07d85-169">The Debugger for Microsoft Edge Extension in Visual Studio Code</span></span>  
:::image-end:::  

<span data-ttu-id="07d85-170">有关详细信息，请查看如何从 Microsoft Edge[调试Visual Studio Code。][VisualStudioCodeDebuggerEdgeExtension]</span><span class="sxs-lookup"><span data-stu-id="07d85-170">For more information, check out [how to debug Microsoft Edge from Visual Studio Code][VisualStudioCodeDebuggerEdgeExtension].</span></span>  

#### <a name="webhint"></a><span data-ttu-id="07d85-171">webhint</span><span class="sxs-lookup"><span data-stu-id="07d85-171">webhint</span></span>  

<span data-ttu-id="07d85-172">[Webhint][VisualStudioMarketplaceWebhintExtension] Visual Studio Code在编写网页时 `webhint` 用于改进网页！</span><span class="sxs-lookup"><span data-stu-id="07d85-172">The [webhint][VisualStudioMarketplaceWebhintExtension] Visual Studio Code extension uses `webhint` to improve your web page while you're writing it!</span></span> <span data-ttu-id="07d85-173">此扩展将运行，并基于分析报告工作区文件的 `webhint` 诊断。</span><span class="sxs-lookup"><span data-stu-id="07d85-173">This extension runs and reports diagnostics on your workspace files based on `webhint` analysis.</span></span>  

:::image type="complex" source="../../images/2019/12/webhint-vscode-extension.msft.png" alt-text="Webhint Visual Studio Code扩展，用于分析 web 中的 .tsx Visual Studio Code" lightbox="../../images/2019/12/webhint-vscode-extension.msft.png":::
   <span data-ttu-id="07d85-175">Webhint Visual Studio Code分析 `.tsx` 文件中文件的扩展Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="07d85-175">The webhint Visual Studio Code extension analyzing a `.tsx` file in Visual Studio Code</span></span>  
:::image-end:::  

<span data-ttu-id="07d85-176">[详细了解 webhint Visual Studio Code 。][WebhintVisualStudioCodeExtension]</span><span class="sxs-lookup"><span data-stu-id="07d85-176">[Learn more about the Visual Studio Code webhint extension][WebhintVisualStudioCodeExtension].</span></span>  

### <a name="visual-studio-integration"></a><span data-ttu-id="07d85-177">Visual Studio集成</span><span class="sxs-lookup"><span data-stu-id="07d85-177">Visual Studio integration</span></span>  

<span data-ttu-id="07d85-178">在 Visual Studio 2019 版本 16.2 或更高版本中，使用 Visual Studio 调试程序调试在 Microsoft Edge 中运行的 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="07d85-178">In Visual Studio 2019 version 16.2 or later, use the Visual Studio debugger to debug JavaScript running in Microsoft Edge.</span></span>  <span data-ttu-id="07d85-179">[下载Visual Studio 2019][MicrosoftVisualStudioDownloads]以试用此功能。</span><span class="sxs-lookup"><span data-stu-id="07d85-179">[Download Visual Studio 2019][MicrosoftVisualStudioDownloads] to try this feature out.</span></span>  

:::image type="complex" source="../../images/2019/12/vs.msft.png" alt-text="Visual Studio Canary、Dev 或 Beta Microsoft Edge启动 Web 应用的选项" lightbox="../../images/2019/12/vs.msft.png":::
   <span data-ttu-id="07d85-181">Visual Studio Canary、Dev 或 Beta Microsoft Edge启动 Web 应用的选项</span><span class="sxs-lookup"><span data-stu-id="07d85-181">Visual Studio with the option to launch your web app in Microsoft Edge Canary, Dev, or Beta</span></span>  
:::image-end:::  

<span data-ttu-id="07d85-182">[阅读我们的博客文章，了解如何从 Microsoft Edge 调试Visual Studio。][MicrosoftVisualStudioBlogDebugJavascript]</span><span class="sxs-lookup"><span data-stu-id="07d85-182">[Read our blog post to learn how to debug Microsoft Edge from Visual Studio][MicrosoftVisualStudioBlogDebugJavascript].</span></span>  

### <a name="tracking-prevention-console-messages"></a><span data-ttu-id="07d85-183">跟踪防护控制台消息</span><span class="sxs-lookup"><span data-stu-id="07d85-183">Tracking prevention Console messages</span></span>  

<span data-ttu-id="07d85-184">跟踪防护是网站中Microsoft Edge一项功能，可阻止你在访问网站之前被网站跟踪。</span><span class="sxs-lookup"><span data-stu-id="07d85-184">Tracking prevention is a unique feature in Microsoft Edge that blocks you from being tracked by a website before you visited it.</span></span>  <span data-ttu-id="07d85-185">默认跟踪防护设置为平衡模式，可阻止第三方跟踪器和已知的恶意跟踪器，从而获得平衡隐私和 Web 兼容性的体验。</span><span class="sxs-lookup"><span data-stu-id="07d85-185">The default tracking prevention setting is Balanced mode, which blocks 3rd party trackers and known malicious trackers for an experience that balances privacy and web compatibility.</span></span>  <span data-ttu-id="07d85-186">为了让你深入了解阻止某些跟踪程序时网页的兼容性，Microsoft Edge团队在控制台中添加了跟踪程序被阻止时警告消息。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="07d85-186">To give you more insight into the compatibility of your web page when certain trackers are blocked, The Microsoft Edge team added warning messages in the **Console** when a tracker is blocked.</span></span>  

:::image type="complex" source="../../images/2019/12/tracking-prevention.msft.png" alt-text="跟踪防护时控制台中的邮件阻止对跟踪器存储的访问" lightbox="../../images/2019/12/tracking-prevention.msft.png":::
   <span data-ttu-id="07d85-188">跟踪防护 **时控制台** 中的邮件阻止对跟踪器存储的访问</span><span class="sxs-lookup"><span data-stu-id="07d85-188">Messages in the **Console** when tracking prevention blocks access to storage for a tracker</span></span>  
:::image-end:::  

<span data-ttu-id="07d85-189">[阅读有关跟踪防护以及隐私与 Web 兼容性之间平衡的详细信息][TrackingPrevention]。</span><span class="sxs-lookup"><span data-stu-id="07d85-189">[Read more about tracking prevention and the balance between privacy and web compatibility][TrackingPrevention].</span></span>  

## <a name="announcements-from-the-chromium-project"></a><span data-ttu-id="07d85-190">来自 Chromium 项目的公告</span><span class="sxs-lookup"><span data-stu-id="07d85-190">Announcements from the Chromium project</span></span>  

<span data-ttu-id="07d85-191">以下各节宣布 80 Microsoft Edge开放源代码管理项目中提供的其他Chromium功能。</span><span class="sxs-lookup"><span data-stu-id="07d85-191">The following sections announce additional features available in Microsoft Edge 80 that were contributed to the open source Chromium project.</span></span>  

### <a name="support-for-let-and-class-redeclarations-in-the-console"></a><span data-ttu-id="07d85-192">支持控制台中的 let 和类重新声明</span><span class="sxs-lookup"><span data-stu-id="07d85-192">Support for let and class redeclarations in the Console</span></span>  

<span data-ttu-id="07d85-193">控制台 **现在** 支持重新声明 `let` 和 `class` 语句。</span><span class="sxs-lookup"><span data-stu-id="07d85-193">The **Console** now supports redeclarations of `let` and `class` statements.</span></span>  <span data-ttu-id="07d85-194">对于使用控制台试验新 JavaScript 代码的 Web 开发人员来说，无法重新声明是常见的麻烦。</span><span class="sxs-lookup"><span data-stu-id="07d85-194">The inability to redeclare was a common annoyance for web developers who use the Console to experiment with new JavaScript code.</span></span>  

> [!WARNING]
> <span data-ttu-id="07d85-195">在控制台外部或单个控制台输入中的脚本中重新声明 或 语句仍 `let` `class` 会导致 `SyntaxError` 。</span><span class="sxs-lookup"><span data-stu-id="07d85-195">Redeclaring a `let` or `class` statement in a script outside of the Console or within a single Console input still causes a `SyntaxError`.</span></span>  

<span data-ttu-id="07d85-196">例如，以前，当使用 重新声明本地变量时， `let` 控制台会出错：</span><span class="sxs-lookup"><span data-stu-id="07d85-196">For example, previously, when re-declaring a local variable with `let`, the Console threw an error:</span></span>  

:::image type="complex" source="../../images/2019/12/letbefore.msft.png" alt-text="Microsoft Edge 79 中的控制台显示允许重新声明失败" lightbox="../../images/2019/12/letbefore.msft.png":::
   <span data-ttu-id="07d85-198">Microsoft Edge79 中的控制台显示允许重新声明失败</span><span class="sxs-lookup"><span data-stu-id="07d85-198">The **Console** in Microsoft Edge 79 showing that the let re-declaration fails</span></span>  
:::image-end:::  

<span data-ttu-id="07d85-199">现在，控制台允许重新声明：</span><span class="sxs-lookup"><span data-stu-id="07d85-199">Now, the Console allows the redeclaration:</span></span>  

:::image type="complex" source="../../images/2019/12/letafter.msft.png" alt-text="80 Microsoft Edge中的控制台显示允许重新声明成功" lightbox="../../images/2019/12/letafter.msft.png":::
   <span data-ttu-id="07d85-201">Microsoft Edge80 中的控制台显示允许重新声明成功</span><span class="sxs-lookup"><span data-stu-id="07d85-201">The **Console** in Microsoft Edge 80 showing that the let re-declaration succeeds</span></span>  
:::image-end:::  

<span data-ttu-id="07d85-202">Chromium问题[#1004193][CR1004193]</span><span class="sxs-lookup"><span data-stu-id="07d85-202">Chromium issue [#1004193][CR1004193]</span></span>  

### <a name="improved-webassembly-debugging"></a><span data-ttu-id="07d85-203">改进的 WebAssembly 调试</span><span class="sxs-lookup"><span data-stu-id="07d85-203">Improved WebAssembly debugging</span></span>  

<span data-ttu-id="07d85-204">DevTools 已开始支持 DEBUGG 调试标准，这意味着增加了对在 DevTools 中单步执行代码、设置断点和解析源语言中的堆栈跟踪的支持。</span><span class="sxs-lookup"><span data-stu-id="07d85-204">DevTools has started to support the DWARF Debugging Standard, which means increased support for stepping over code, setting breakpoints, and resolving stack traces in your source languages within DevTools.</span></span>  

<!-- [TODO: Add this link back] -->  
<!--Check out [Improved WebAssembly debugging in Microsoft Edge DevTools][201912Webassembly] for the full story.  -->  

<!-- [TODO: Replace this image with screenshot in Edge] -->  
<!--
:::image type="complex" source="../../images/2019/12/wasm.msft.png" alt-text="The new DWARF-powered WebAssembly debugging" lightbox="../../images/2019/12/wasm.msft.png":::
   The new DWARF-powered WebAssembly debugging  
:::image-end:::  
-->  

### <a name="network-panel-updates"></a><span data-ttu-id="07d85-205">网络面板更新</span><span class="sxs-lookup"><span data-stu-id="07d85-205">Network panel updates</span></span>  

#### <a name="request-initiator-chains-in-the-initiator-panel"></a><span data-ttu-id="07d85-206">发起者面板中的请求发起人链</span><span class="sxs-lookup"><span data-stu-id="07d85-206">Request Initiator Chains in the Initiator panel</span></span>  

<span data-ttu-id="07d85-207">现在，你可以将网络请求的发起方和依赖项作为嵌套列表进行查看。</span><span class="sxs-lookup"><span data-stu-id="07d85-207">You are now able to view the initiators and dependencies of a network request as a nested list.</span></span>  <span data-ttu-id="07d85-208">这可以帮助您了解请求资源的原因，或特定资源 \(（如 script\) 导致的网络活动。</span><span class="sxs-lookup"><span data-stu-id="07d85-208">This may help you understand why a resource was requested, or what network activity a certain resource \(such as a script\) caused.</span></span>  

:::image type="complex" source="../../images/2019/12/initiators.msft.png" alt-text="发起者面板中的请求发起人链" lightbox="../../images/2019/12/initiators.msft.png":::
   <span data-ttu-id="07d85-210">发起者面板中的请求 **发起人** 链</span><span class="sxs-lookup"><span data-stu-id="07d85-210">A Request Initiator Chain in the **Initiator** panel</span></span>  
:::image-end:::  

<span data-ttu-id="07d85-211">在 ["网络"面板][DevToolsNetworkIndex]中记录网络活动后，选择一个资源，然后导航到发起 **者** 面板以查看请求 **发起人链**：</span><span class="sxs-lookup"><span data-stu-id="07d85-211">After [logging network activity in the Network panel][DevToolsNetworkIndex], choose a resource and then navigate to the **Initiator** panel to view the **Request Initiator Chain**:</span></span>  

*   <span data-ttu-id="07d85-212">已 **检查的资源为** 粗体。</span><span class="sxs-lookup"><span data-stu-id="07d85-212">The **inspected resource** is bold.</span></span>  <span data-ttu-id="07d85-213">在以上屏幕截图中 `ai.2.min.js` ， 是已检查的资源。</span><span class="sxs-lookup"><span data-stu-id="07d85-213">In the screenshot above, `ai.2.min.js` is the inspected resource.</span></span>  
*   <span data-ttu-id="07d85-214">已检查资源上方的资源是 **发起者**。</span><span class="sxs-lookup"><span data-stu-id="07d85-214">The resources above the inspected resource are the **initiators**.</span></span>  <span data-ttu-id="07d85-215">在以上屏幕截图中 `https://www.microsoftedgeinsider.com` ， 是 的发起 `ai.2.min.js` 人。</span><span class="sxs-lookup"><span data-stu-id="07d85-215">In the screenshot above, `https://www.microsoftedgeinsider.com` is the initiator of `ai.2.min.js`.</span></span>  <span data-ttu-id="07d85-216">换句话说，导致 `https://www.microsoftedgeinsider.com` 对 的网络请求 `ai.2.min.js` 。</span><span class="sxs-lookup"><span data-stu-id="07d85-216">In other words, `https://www.microsoftedgeinsider.com` caused the network request for `ai.2.min.js`.</span></span>  
*   <span data-ttu-id="07d85-217">已检查资源下方的资源是 **依赖项**。</span><span class="sxs-lookup"><span data-stu-id="07d85-217">The resources below the inspected resource are the **dependencies**.</span></span>  <span data-ttu-id="07d85-218">在以上屏幕截图中 `https://dc.services.visualstudio.com/v2/track` ， 是 的依赖项 `ai.2.min.js` 。</span><span class="sxs-lookup"><span data-stu-id="07d85-218">In the screenshot above, `https://dc.services.visualstudio.com/v2/track` is a dependency of `ai.2.min.js`.</span></span>  <span data-ttu-id="07d85-219">换句话说，导致 `ai.2.min.js` 对 的网络请求 `https://dc.services.visualstudio.com/v2/track` 。</span><span class="sxs-lookup"><span data-stu-id="07d85-219">In other words, `ai.2.min.js` caused the network request for `https://dc.services.visualstudio.com/v2/track`.</span></span>  

> [!NOTE]
> <span data-ttu-id="07d85-220">通过按住并悬停在网络资源上，也可以访问发起方 `Shift` 和依赖关系信息。</span><span class="sxs-lookup"><span data-stu-id="07d85-220">Initiator and dependency information may also be accessed by holding `Shift` and then hovering over network resources.</span></span>  <span data-ttu-id="07d85-221">导航到 [查看发起方和依赖项][DevToolsNetworkReferenceDisplayInitiatorsDependencies]。</span><span class="sxs-lookup"><span data-stu-id="07d85-221">Navigate to [View initiators and dependencies][DevToolsNetworkReferenceDisplayInitiatorsDependencies].</span></span>  

<span data-ttu-id="07d85-222">Chromium问题[#842488][CR842488]</span><span class="sxs-lookup"><span data-stu-id="07d85-222">Chromium issue [#842488][CR842488]</span></span>  

#### <a name="highlight-the-selected-network-request-in-the-overview"></a><span data-ttu-id="07d85-223">在概述中突出显示所选的网络请求</span><span class="sxs-lookup"><span data-stu-id="07d85-223">Highlight the selected network request in the Overview</span></span>  

<span data-ttu-id="07d85-224">选择网络资源以检查它后，网络面板现在在概述中为资源设置蓝色 **边框**。</span><span class="sxs-lookup"><span data-stu-id="07d85-224">After you choose a network resource in order to inspect it, the Network panel now puts a blue border around that resource in the **Overview**.</span></span>  <span data-ttu-id="07d85-225">这可以帮助您检测网络请求是早于还是晚于预期发生。</span><span class="sxs-lookup"><span data-stu-id="07d85-225">This is able to help you detect if the network request is happening earlier or later than expected.</span></span>  

:::image type="complex" source="../../images/2019/12/overview.msft.png" alt-text="突出显示已检查资源的概述窗格" lightbox="../../images/2019/12/overview.msft.png":::
   <span data-ttu-id="07d85-227">突出显示 **已** 检查资源的"概述"窗格</span><span class="sxs-lookup"><span data-stu-id="07d85-227">The **Overview** pane highlighting the inspected resource</span></span>  
:::image-end:::  

<span data-ttu-id="07d85-228">Chromium问题[#988253][CR988253]</span><span class="sxs-lookup"><span data-stu-id="07d85-228">Chromium issue [#988253][CR988253]</span></span>  

#### <a name="url-and-path-columns-in-the-network-panel"></a><span data-ttu-id="07d85-229">网络面板中的 URL 和路径列</span><span class="sxs-lookup"><span data-stu-id="07d85-229">URL and path columns in the Network panel</span></span>  

<span data-ttu-id="07d85-230">使用"**网络"** 工具**中的新"** 路径"和 **"URL"** 列显示每个网络资源的绝对路径或完整 URL。</span><span class="sxs-lookup"><span data-stu-id="07d85-230">Use the new **Path** and **URL** columns in the **Network** tool to display the absolute path or full URL of each network resource.</span></span>  

:::image type="complex" source="../../images/2019/12/columns.msft.png" alt-text="网络面板中的新路径和URL列" lightbox="../../images/2019/12/columns.msft.png":::
   <span data-ttu-id="07d85-232">网络工具中的新 **路径和** URL 列</span><span class="sxs-lookup"><span data-stu-id="07d85-232">The new Path and URL columns in the **Network** tool</span></span>  
:::image-end:::  

<span data-ttu-id="07d85-233">若要显示新列，请将鼠标悬停在**瀑布**表标题上，打开上下文菜单 \(righ-click\) ，然后选择**路径**或**URL。**</span><span class="sxs-lookup"><span data-stu-id="07d85-233">To display the new columns, hover on the **Waterfall** table header, open the contextual menu \(righ-click\), and choose **Path** or **URL**.</span></span>  

<span data-ttu-id="07d85-234">Chromium问题[#993366][CR993366]</span><span class="sxs-lookup"><span data-stu-id="07d85-234">Chromium issue [#993366][CR993366]</span></span>  

#### <a name="updated-user-agent-strings"></a><span data-ttu-id="07d85-235">更新User-Agent字符串</span><span class="sxs-lookup"><span data-stu-id="07d85-235">Updated User-Agent strings</span></span>  

<span data-ttu-id="07d85-236">DevTools 支持通过"网络User-Agent设置 **自定义字符串** 。</span><span class="sxs-lookup"><span data-stu-id="07d85-236">DevTools supports setting a custom User-Agent string through the **Network Conditions** panel.</span></span>  <span data-ttu-id="07d85-237">the User-Agent string affects the `User-Agent` HTTP header attached to network resources， and the value of `navigator.userAgent` .</span><span class="sxs-lookup"><span data-stu-id="07d85-237">The User-Agent string affects the `User-Agent` HTTP header attached to network resources, and also the value of `navigator.userAgent`.</span></span>  

<span data-ttu-id="07d85-238">预定义User-Agent字符串已更新，以反映新式浏览器版本。</span><span class="sxs-lookup"><span data-stu-id="07d85-238">The predefined User-Agent strings have been updated to reflect modern browser versions.</span></span>  

:::image type="complex" source="../../images/2019/12/useragent.msft.png" alt-text="网络条件面板中的用户代理菜单" lightbox="../../images/2019/12/useragent.msft.png":::
   <span data-ttu-id="07d85-240">"网络条件"面板中的" **用户代理"** 菜单</span><span class="sxs-lookup"><span data-stu-id="07d85-240">The User Agent menu in the **Network Conditions** panel</span></span>  
:::image-end:::  

<span data-ttu-id="07d85-241">若要访问**网络条件**[，请打开命令菜单][DevToolsCommandMenuIndex]并运行 `Show Network Conditions` 命令。</span><span class="sxs-lookup"><span data-stu-id="07d85-241">To access **Network Conditions**, [open the Command Menu][DevToolsCommandMenuIndex] and run the `Show Network Conditions` command.</span></span>  

> [!NOTE]
> <span data-ttu-id="07d85-242">还可以在 [设备User-Agent设置字符串][DevToolsDeviceModeIndex]。</span><span class="sxs-lookup"><span data-stu-id="07d85-242">You may also [set User-Agent strings in Device Mode][DevToolsDeviceModeIndex].</span></span>  

<span data-ttu-id="07d85-243">Chromium问题[#1029031][CR1029031]</span><span class="sxs-lookup"><span data-stu-id="07d85-243">Chromium issue [#1029031][CR1029031]</span></span>  

### <a name="audits-panel-updates"></a><span data-ttu-id="07d85-244">审核面板更新</span><span class="sxs-lookup"><span data-stu-id="07d85-244">Audits panel updates</span></span>  

#### <a name="new-configuration-ui"></a><span data-ttu-id="07d85-245">新配置 UI</span><span class="sxs-lookup"><span data-stu-id="07d85-245">New configuration UI</span></span>  

<span data-ttu-id="07d85-246">配置 UI 具有新的响应式设计，并且限制配置选项已简化。</span><span class="sxs-lookup"><span data-stu-id="07d85-246">The configuration UI has a new, responsive design, and the throttling configuration options have been simplified.</span></span>  <span data-ttu-id="07d85-247">有关限制 UI 更改的信息，请导航到"[审核""面板限制"。][GitHubGoogleChromeDevToolsAuditsPanelThrottling]</span><span class="sxs-lookup"><span data-stu-id="07d85-247">For more information on the throttling UI changes, navigate to [Audits Panel Throttling][GitHubGoogleChromeDevToolsAuditsPanelThrottling].</span></span>  

:::image type="complex" source="../../images/2019/12/start.msft.png" alt-text="新配置 UI" lightbox="../../images/2019/12/start.msft.png":::
   <span data-ttu-id="07d85-249">新配置 UI</span><span class="sxs-lookup"><span data-stu-id="07d85-249">The new configuration UI</span></span>  
:::image-end:::  

### <a name="coverage-tool-updates"></a><span data-ttu-id="07d85-250">覆盖工具更新</span><span class="sxs-lookup"><span data-stu-id="07d85-250">Coverage tool updates</span></span>  

#### <a name="per-function-or-per-block-coverage-modes"></a><span data-ttu-id="07d85-251">按功能或按块覆盖模式</span><span class="sxs-lookup"><span data-stu-id="07d85-251">Per-function or per-block coverage modes</span></span>  

<span data-ttu-id="07d85-252">覆盖 [工具][DevToolsCoverageIndex] 具有新的下拉菜单，允许你指定是按函数还是 **按块收集** 代码 **覆盖数据**。</span><span class="sxs-lookup"><span data-stu-id="07d85-252">The [Coverage][DevToolsCoverageIndex] tool has a new dropdown menu that lets you specify whether code coverage data should be collected **per function** or **per block**.</span></span>  <span data-ttu-id="07d85-253">**每个块** 覆盖更加详细，但收集成本也更高。</span><span class="sxs-lookup"><span data-stu-id="07d85-253">**Per block** coverage is more detailed but also far more expensive to collect.</span></span>  <span data-ttu-id="07d85-254">默认情况下，DevTools **现在按** 功能范围使用。</span><span class="sxs-lookup"><span data-stu-id="07d85-254">DevTools uses **per function** coverage by default now.</span></span>  

> [!CAUTION]
> <span data-ttu-id="07d85-255">你可能会注意到 HTML 文件的代码覆盖差异很大，具体取决于是按函数\*\*\*\* 还是**按块模式**使用。</span><span class="sxs-lookup"><span data-stu-id="07d85-255">You may notice large code coverage differences in HTML files depending on whether you use **per function** or **per block** mode.</span></span>  <span data-ttu-id="07d85-256">在按 **函数模式使用** 时，HTML 文件中内联脚本被视为函数。</span><span class="sxs-lookup"><span data-stu-id="07d85-256">When using **per function** mode, inline scripts in HTML files are treated as functions.</span></span>  <span data-ttu-id="07d85-257">如果脚本完全运行，则 DevTools 将整个脚本标记为已用代码。</span><span class="sxs-lookup"><span data-stu-id="07d85-257">If the script runs at all then DevTools marks the entire script as used code.</span></span>  <span data-ttu-id="07d85-258">只有当脚本完全不运行时，DevTools 才将脚本标记为未使用的代码。</span><span class="sxs-lookup"><span data-stu-id="07d85-258">Only if the script does not run at all does DevTools mark the script as unused code.</span></span>  

:::image type="complex" source="../../images/2019/12/modes.msft.png" alt-text="覆盖模式下拉菜单" lightbox="../../images/2019/12/modes.msft.png":::
   <span data-ttu-id="07d85-260">覆盖模式下拉菜单</span><span class="sxs-lookup"><span data-stu-id="07d85-260">The coverage mode dropdown menu</span></span>  
:::image-end:::  

#### <a name="coverage-must-now-be-initiated-by-a-page-refresh"></a><span data-ttu-id="07d85-261">现在必须通过页面刷新启动覆盖</span><span class="sxs-lookup"><span data-stu-id="07d85-261">Coverage must now be initiated by a page refresh</span></span>  

<span data-ttu-id="07d85-262">由于覆盖数据不可靠，因此在未刷新页面的情况下切换代码覆盖已被删除。</span><span class="sxs-lookup"><span data-stu-id="07d85-262">Toggling code coverage without a page refresh has been removed because the coverage data was unreliable.</span></span>  <span data-ttu-id="07d85-263">例如，如果运行库在很长一段时间之前且 V8 垃圾回收器已清理它，函数可能会报告为未使用。</span><span class="sxs-lookup"><span data-stu-id="07d85-263">For example, a function may be reported as unused if the runtime was a long time ago and the V8 garbage collector has cleaned it up.</span></span>  

<span data-ttu-id="07d85-264">Chromium问题[#1004203][CR1004203]</span><span class="sxs-lookup"><span data-stu-id="07d85-264">Chromium issue [#1004203][CR1004203]</span></span>  

## <a name="download-the-microsoft-edge-preview-channels"></a><span data-ttu-id="07d85-265">下载 Microsoft Edge 预览频道</span><span class="sxs-lookup"><span data-stu-id="07d85-265">Download the Microsoft Edge preview channels</span></span>  

<span data-ttu-id="07d85-266">如果你使用的是 Windows 或 macOS，请考虑使用 [ Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels] 作为默认开发浏览器。</span><span class="sxs-lookup"><span data-stu-id="07d85-266">If you are on Windows or macOS, consider using the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] as your default development browser.</span></span>  <span data-ttu-id="07d85-267">预览频道使你能够访问最新的 DevTools 功能。</span><span class="sxs-lookup"><span data-stu-id="07d85-267">The preview channels give you access to the latest DevTools features.</span></span>  

## <a name="getting-in-touch-with-microsoft-edge-devtools-team"></a><span data-ttu-id="07d85-268">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="07d85-268">Getting in touch with Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- links -->  

[DevToolsCommandMenuIndex]: ../../../command-menu/index.md "使用 Microsoft Edge DevTools 命令菜单运行命令 | Microsoft Docs"  
[DevToolsCoverageIndex]: ../../../coverage/index.md "使用 DevTools Microsoft Edge中的覆盖工具查找未使用的 JavaScript 和 CSS |Microsoft Docs"  
[DevToolsDeviceModeIndex]: ../../../device-mode/index.md#simulate-a-mobile-viewport "模拟移动视区 - 在 DevTools Microsoft Edge设备模式下模拟移动设备|Microsoft Docs"  
[DevToolsNetworkIndex]: ../../../network/index.md "检查 Microsoft Edge DevTools |Microsoft Docs"  
[DevToolsNetworkReferenceDisplayInitiatorsDependencies]: ../../../network/reference.md#display-initiators-and-dependencies "显示发起方和依赖项 - 网络分析参考|Microsoft Docs"  
[VisualStudioCodeDebuggerEdgeExtension]: ../../../../visual-studio-code/debugger-for-edge.md "调试程序Microsoft Edge Visual Studio Code扩展|Microsoft Docs"  
[VisualStudioCodeElementEdgeExtension]: ../../../../visual-studio-code/elements-for-edge.md "扩展Microsoft Edge Visual Studio Code元素|Microsoft Docs"  

<!--  [201912Webassembly]: webassembly.md "Improved WebAssembly debugging in Microsoft Edge DevTools"  -->  

[CR842488]: https://crbug.com/842488 "将 Initiator 字段添加到&quot;标题&quot;选项卡|ChromiumBug"  
[CR988253]: https://crbug.com/988253 "Bug DevTools - 网络请求和时间线项目之间Graph |ChromiumBug"  
[CR993366]: https://crbug.com/993366 "请在网络面板请求列表中显示 URL 的路径部分|ChromiumBug"  
[CR1004193]: https://crbug.com/1004193 "V8 | 的 REPL 模式ChromiumBug"  
[CR1004203]: https://crbug.com/1004203 "使代码覆盖更|ChromiumBug"  
[CR1029031]: https://crbug.com/1029031 "UA 字符串已过时|ChromiumBug" 
[CR963183]: https://crbug.com/963183 "DevTools 不符合 WCAG |ChromiumBug"
[CR941561]: https://crbug.com/941561 "DevTools 工具的本地化|ChromiumBug"
[CR987787]: https://crbug.com/987787 "Dom 3D 视图|ChromiumBug"

[AccessibilityInsights]: https://aka.ms/a11yinsights "辅助功能见解"  

[GitHubGoogleChromeDevToolsAuditsPanelThrottling]: https://github.com/GoogleChrome/lighthouse/blob/master/docs/throttling.md#devtools-audits-panel-throttling "DevTools 的审核面板限制 - GoogleChrome/lighthouse |GitHub"  
[GitHubMicrosoftDocsEdgeDeveloperNewIssue]: https://aka.ms/edgedevtoolsdocs/feedback "新问题 - MicrosoftDocs/edge-developer"  
[MicrosoftEdgePreviewChannels]: https://aka.ms/microsoftedge "Microsoft Edge 预览频道"  
[MicrosoftEdgeInsiderAddons]: https://aka.ms/webhint/edge-extension "Microsoft Edge预览体验成员加载项"  
[MicrosoftVisualStudio]: https://aka.ms/vs "Visual Studio"  
[MicrosoftVisualStudioBlogDebugJavascript]: https://aka.ms/vs/debug-edge "在 Microsoft Edge 中调试 JavaScript Visual Studio |Visual Studio博客"  
[MicrosoftVisualStudioDownloads]: https://aka.ms/vs/download "下载 Visual Studio 2019 for Windows \& Mac"  
[MDNDocumentObjectModel]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model "文档对象模型 (DOM) |MDN"  
[MDNZIndex]: https://developer.mozilla.org/docs/Web/CSS/z-index "z-index |MDN"  
[PostTweetEdgeDevTools]: https://aka.ms/tweet/edgedevtools "@EdgeDevTools | 发布推文"  
[EdgeDevToolsTwitterAccount]: https://aka.ms/twitter/edgedevtools "@EdgeDevTools Twitter 帐户"
[VisualStudioCode]: https://aka.ms/vscode "Visual Studio Code"  
[VisualStudioMarketplaceDebuggerEdge]: https://aka.ms/debugger4code "调试程序Microsoft Edge - Visual Studio市场"  
[VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension]: https://aka.ms/elements4code "Microsoft Edge \(Chromium\) - Visual Studio Marketplace 的元素"  
[VisualStudioMarketplaceWebhintExtension]: https://aka.ms/webhint4code "webhint - Visual Studio Marketplace"
[Webhint]: https://aka.ms/webhint "webhint"  
[WebhintBrowserExtension]: https://aka.ms/webhint/browser-extension "Webhint 浏览器扩展|webhint 文档"  
[WebhintVisualStudioCodeExtension]: https://aka.ms/webhint/code-extension "Webhint Visual Studio Code Extension |webhint 文档"  
[TrackingPrevention]: https://aka.ms/microsoftedge/tracking-prevention-blog "改进跟踪防护Microsoft Edge博客文章"
[TheWebWeWant]: https://aka.ms/webwewant "我们想要的网络"

> [!NOTE]
> <span data-ttu-id="07d85-306">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="07d85-306">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="07d85-307">原始页面位于[此处](https://developer.chrome.com/blog/new-in-devtools-80)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="07d85-307">The original page is found [here](https://developer.chrome.com/blog/new-in-devtools-80) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="07d85-309">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="07d85-309">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
