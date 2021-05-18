---
description: 3D 视图Visual Studio与 Microsoft Edge 集成等。
title: 'DevTools (Microsoft Edge 81) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 03b17f524e9be55e1ed37147ce46b7a15fc3a17d
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564957"
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
# <a name="whats-new-in-devtools-microsoft-edge-81"></a><span data-ttu-id="6649f-104">DevTools （Microsoft Edge 81）中的新增功能</span><span class="sxs-lookup"><span data-stu-id="6649f-104">What's New In DevTools (Microsoft Edge 81)</span></span>  

## <a name="announcements-from-the-microsoft-edge-devtools-team"></a><span data-ttu-id="6649f-105">来自 Microsoft Edge 开发人员工具团队公告</span><span class="sxs-lookup"><span data-stu-id="6649f-105">Announcements from the Microsoft Edge DevTools team</span></span>  

<span data-ttu-id="6649f-106">以下各节列出了你可能从 DevTools 团队中错过Microsoft Edge通知。</span><span class="sxs-lookup"><span data-stu-id="6649f-106">The following sections are a list of announcements you may have missed from the Microsoft Edge DevTools team.</span></span>  <span data-ttu-id="6649f-107">请查看公告以试用 DevTools、Microsoft Visual Studio代码扩展等中的新功能。</span><span class="sxs-lookup"><span data-stu-id="6649f-107">Check out the announcements to try new features in the DevTools, Microsoft Visual Studio Code extensions, and more.</span></span>  <span data-ttu-id="6649f-108">若要了解有关开发人员工具中的所有最新功能和最强大功能的最新动态，请下载 [Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels]并[在 Twitter 上关注我们][EdgeDevToolsTwitterAccount]。</span><span class="sxs-lookup"><span data-stu-id="6649f-108">To stay up to date on all the latest and greatest features in your developer tools, download the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] and [follow us on Twitter][EdgeDevToolsTwitterAccount].</span></span>  

### <a name="accessibility-improvements-to-the-devtools"></a><span data-ttu-id="6649f-109">对 DevTools 的辅助功能改进</span><span class="sxs-lookup"><span data-stu-id="6649f-109">Accessibility improvements to the DevTools</span></span>  

<span data-ttu-id="6649f-110">DevTools 团队已对 Chromium 进行 170 次更改，以解决 DevTools 中的高影响颜色对比度、键盘和屏幕阅读器问题。</span><span class="sxs-lookup"><span data-stu-id="6649f-110">The DevTools team has contributed 170 changes to Chromium to address high-impact color contrast, keyboard, and screen reader issues in the DevTools.</span></span>  <span data-ttu-id="6649f-111">每个生成 Web 的开发人员都应能够使用 DevTools。</span><span class="sxs-lookup"><span data-stu-id="6649f-111">Every developer building the web should be able to use the DevTools.</span></span>  

:::image type="complex" source="../../images/2020/01/a11y-performance-tool.msft.gif" alt-text="具有键盘导航和屏幕阅读器改进的 DevTools 中的性能工具" lightbox="../../images/2020/01/a11y-performance-tool.msft.gif":::
   <span data-ttu-id="6649f-113">具有 **键盘** 导航和屏幕阅读器改进的 DevTools 中的性能工具</span><span class="sxs-lookup"><span data-stu-id="6649f-113">The **Performance** tool in the DevTools with the keyboard navigation and screen reader improvements</span></span>  
:::image-end:::  

<span data-ttu-id="6649f-114">想要了解如何使网页可供所有用户访问？</span><span class="sxs-lookup"><span data-stu-id="6649f-114">Want to learn how to make your web page accessible to all of your users?</span></span>  <span data-ttu-id="6649f-115">下载[辅助功能见解][AccessibilityInsights]和[webhint][WebhintBrowserExtension]扩展，Microsoft Edge开始操作。</span><span class="sxs-lookup"><span data-stu-id="6649f-115">Download the [Accessibility Insights][AccessibilityInsights] and [webhint][WebhintBrowserExtension] extensions for Microsoft Edge to get started.</span></span>  

<span data-ttu-id="6649f-116">如果使用屏幕阅读器或键盘在 DevTools 中导航，请通过向我们发推文或[][PostTweetEdgeDevTools]选择"发送反馈"图标向我们发送[反馈](#getting-in-touch-with-microsoft-edge-devtools-team)！</span><span class="sxs-lookup"><span data-stu-id="6649f-116">If you use screen readers or the keyboard to navigate around the DevTools, send us your feedback by [tweeting][PostTweetEdgeDevTools] at us orchoosing the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon!</span></span>  

<span data-ttu-id="6649f-117">Chromium 问题 [#963183][CR963183]</span><span class="sxs-lookup"><span data-stu-id="6649f-117">Chromium issue [#963183][CR963183]</span></span>  

### <a name="using-the-devtools-in-other-languages"></a><span data-ttu-id="6649f-118">以其他语言使用 DevTools</span><span class="sxs-lookup"><span data-stu-id="6649f-118">Using the DevTools in other languages</span></span>  

<span data-ttu-id="6649f-119">许多开发人员使用其他开发人员工具（如 StackOverflow 和 Visual Studio Code，使用其本地语言，而不只是使用英语。</span><span class="sxs-lookup"><span data-stu-id="6649f-119">Many developers use other developer tools, like StackOverflow and Visual Studio Code, in their native language, not just in English.</span></span>  <span data-ttu-id="6649f-120">我们很高兴宣布 DevTools 的本地化，你现在可以使用英语之外 10 种语言之一：</span><span class="sxs-lookup"><span data-stu-id="6649f-120">We’re excited to announce localization for the DevTools, which you are now able to use in one of 10 languages besides English:</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="6649f-121">中文 \(Simplified\) - &#20013;&#25991;&#65288;&#31616;&#20307;&#65289;</span><span class="sxs-lookup"><span data-stu-id="6649f-121">Chinese \(Simplified\) - &#20013;&#25991;&#65288;&#31616;&#20307;&#65289;</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="6649f-122">繁体 (中文\) - &#20013;&#25991;&#65288;&#32321;&#39636;&#65289;</span><span class="sxs-lookup"><span data-stu-id="6649f-122">Chinese \(Traditional\) - &#20013;&#25991;&#65288;&#32321;&#39636;&#65289;</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      <span data-ttu-id="6649f-123">法语 –&#231;语</span><span class="sxs-lookup"><span data-stu-id="6649f-123">French – fran&#231;ais</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="6649f-124">德语 - 德语</span><span class="sxs-lookup"><span data-stu-id="6649f-124">German - deutsch</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      <span data-ttu-id="6649f-125">意大利语 - 意大利语</span><span class="sxs-lookup"><span data-stu-id="6649f-125">Italian - italiano</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="6649f-126">日语 - &#26085;&#26412;&#35486;</span><span class="sxs-lookup"><span data-stu-id="6649f-126">Japanese - &#26085;&#26412;&#35486;</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      <span data-ttu-id="6649f-127">朝鲜语 - &#54620;&#44397;&#50612;</span><span class="sxs-lookup"><span data-stu-id="6649f-127">Korean - &#54620;&#44397;&#50612;</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="6649f-128">葡萄牙语 - 图卢&#234;语</span><span class="sxs-lookup"><span data-stu-id="6649f-128">Portuguese - portugu&#234;s</span></span>
   :::column-end:::
:::row-end:::
:::row:::
   :::column span="":::
      <span data-ttu-id="6649f-129">俄语 – &#1088;&#1091;&#1089;&#1089;&#1082;&#1080;&#1081;</span><span class="sxs-lookup"><span data-stu-id="6649f-129">Russian – &#1088;&#1091;&#1089;&#1089;&#1082;&#1080;&#1081;</span></span>
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="6649f-130">西班牙语 - 电子邮件&#241;ol</span><span class="sxs-lookup"><span data-stu-id="6649f-130">Spanish - espa&#241;ol</span></span>
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

<span data-ttu-id="6649f-131">DevTools 会自动匹配你在 中用于Microsoft Edge的语言 `edge://settings/languages` 。</span><span class="sxs-lookup"><span data-stu-id="6649f-131">The DevTools automatically match the language you use for Microsoft Edge in `edge://settings/languages`.</span></span>  

<span data-ttu-id="6649f-132">如果你希望Microsoft Edge一种语言，并且你的 DevTools 保持为英语，请在 DevTools 中选择以打开设置 `F1` 并禁用[][DevtoolsCustomizeIndexSettings]**匹配浏览器语言**。</span><span class="sxs-lookup"><span data-stu-id="6649f-132">If you want Microsoft Edge to be in one language and your DevTools to remain in English, select `F1` in the DevTools to open [Settings][DevtoolsCustomizeIndexSettings] and disable **Match browser language**.</span></span>  

:::image type="complex" source="../../images/2020/01/localized-devtools.msft.png" alt-text="德语的 DevTools" lightbox="../../images/2020/01/localized-devtools.msft.png":::
   <span data-ttu-id="6649f-134">德语的 DevTools</span><span class="sxs-lookup"><span data-stu-id="6649f-134">The DevTools in German</span></span>  
:::image-end:::  

<span data-ttu-id="6649f-135">**控制台** 消息未本地化。</span><span class="sxs-lookup"><span data-stu-id="6649f-135">**Console** messages are not localized.</span></span>  <span data-ttu-id="6649f-136">只有 DevTools UI 中使用的字符串以你用于开发工具Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="6649f-136">Only the strings used in the DevTools UI are displayed in the language you use for Microsoft Edge.</span></span>  

<span data-ttu-id="6649f-137">如果你想要以与可用版本不同的语言使用 DevTools，请通过我们的推文或选择[][PostTweetEdgeDevTools]"发送反馈["](#getting-in-touch-with-microsoft-edge-devtools-team)图标。</span><span class="sxs-lookup"><span data-stu-id="6649f-137">If you want to use the DevTools in a different language than the ones that are available, [tweet][PostTweetEdgeDevTools] at us or choose the [Send Feedback](#getting-in-touch-with-microsoft-edge-devtools-team) icon.</span></span>  

<span data-ttu-id="6649f-138">Chromium问题[#941561][CR941561]</span><span class="sxs-lookup"><span data-stu-id="6649f-138">Chromium issue [#941561][CR941561]</span></span>  

### <a name="webhint-microsoft-edge-extension"></a><span data-ttu-id="6649f-139">webhint Microsoft Edge扩展</span><span class="sxs-lookup"><span data-stu-id="6649f-139">webhint Microsoft Edge extension</span></span>  

<span data-ttu-id="6649f-140">Webhint Microsoft Edge扩展允许你在 DevTools 中轻松扫描网页并获取有关辅助功能、浏览器兼容性、安全性、性能等的反馈。</span><span class="sxs-lookup"><span data-stu-id="6649f-140">The webhint Microsoft Edge extension allows you to easily scan your web page and get feedback on accessibility, browser compatibility, security, performance, and more within the DevTools.</span></span>  <span data-ttu-id="6649f-141">有关详细信息，请参阅 [https://webhint.io][Webhint] 。</span><span class="sxs-lookup"><span data-stu-id="6649f-141">Read more at [https://webhint.io][Webhint].</span></span>  

:::image type="complex" source="../../images/2020/01/webhint-browser-extension.msft.png" alt-text="安装 Webhint 浏览器扩展时 DevTools 中的 Hints 工具" lightbox="../../images/2020/01/webhint-browser-extension.msft.png":::
   <span data-ttu-id="6649f-143">安装 **Webhint** 浏览器扩展时 DevTools 中的 Hints 工具</span><span class="sxs-lookup"><span data-stu-id="6649f-143">The **Hints** tool in the DevTools when the webhint browser extension is installed</span></span>  
:::image-end:::  

<span data-ttu-id="6649f-144">[尝试 webhint 浏览器扩展Microsoft Edge。][MicrosoftEdgeInsiderAddons]</span><span class="sxs-lookup"><span data-stu-id="6649f-144">[Try the webhint browser extension in Microsoft Edge][MicrosoftEdgeInsiderAddons].</span></span>  <span data-ttu-id="6649f-145">安装扩展后，打开 DevTools 并选择 **提示** 工具。</span><span class="sxs-lookup"><span data-stu-id="6649f-145">Once you install the extension, open the DevTools and choose the **Hints** tool.</span></span>  <span data-ttu-id="6649f-146">从此处运行可自定义的网站扫描。</span><span class="sxs-lookup"><span data-stu-id="6649f-146">From here, run a customizable site scan.</span></span>  <span data-ttu-id="6649f-147">请 [前往][WebhintBrowserExtension] webhint.io 了解更多信息。</span><span class="sxs-lookup"><span data-stu-id="6649f-147">Head over to [webhint.io][WebhintBrowserExtension] to learn more.</span></span>  

### <a name="3d-view"></a><span data-ttu-id="6649f-148">3D 视图</span><span class="sxs-lookup"><span data-stu-id="6649f-148">3D View</span></span>  

<span data-ttu-id="6649f-149">使用 **3D 视图** 通过浏览文档对象模型 [\(DOM\) ][MDNDocumentObjectModel] 或 [z 索引][MDNZIndex] 堆栈上下文来调试 Web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="6649f-149">Use the **3D View** to debug your web application by navigating through the [Document Object Model \(DOM\)][MDNDocumentObjectModel] or the [z-index][MDNZIndex] stacking context.</span></span>  

:::image type="complex" source="../../images/2020/01/3dview.msft.png" alt-text="DevTools 中的 3D 视图" lightbox="../../images/2020/01/3dview.msft.png":::
   <span data-ttu-id="6649f-151">DevTools 中的 3D 视图</span><span class="sxs-lookup"><span data-stu-id="6649f-151">The 3D View in the DevTools</span></span>  
:::image-end:::  

<span data-ttu-id="6649f-152">若要访问 3D 视图，请选择 `Ctrl`  +  `Shift`  +  `P` ，键入**3D 视图，** 然后选择**显示 3D 视图**。</span><span class="sxs-lookup"><span data-stu-id="6649f-152">To access the 3D View, select `Ctrl` + `Shift` + `P`, type in **3D View** and select **Show 3D View**.</span></span>  

<span data-ttu-id="6649f-153">该Microsoft Edge团队正在与 UI 上的 Chromium 团队合作，并将更多功能添加到 3D 视图，因此请[发送反馈。](#getting-in-touch-with-microsoft-edge-devtools-team)</span><span class="sxs-lookup"><span data-stu-id="6649f-153">The Microsoft Edge team is working with the Chromium team on the UI and adding more functionality to the 3D View, so please send your [feedback](#getting-in-touch-with-microsoft-edge-devtools-team).</span></span>  

<span data-ttu-id="6649f-154">Chromium问题[#987787][CR987787]</span><span class="sxs-lookup"><span data-stu-id="6649f-154">Chromium issue [#987787][CR987787]</span></span>  

### <a name="visual-studio-code-extensions"></a><span data-ttu-id="6649f-155">Visual Studio Code扩展</span><span class="sxs-lookup"><span data-stu-id="6649f-155">Visual Studio Code extensions</span></span>  

<span data-ttu-id="6649f-156">DevTools 团队还发布了一些 Visual Studio Code，[][VisualStudioCode]让你可以直接从文本编辑器使用 DevTools 功能！</span><span class="sxs-lookup"><span data-stu-id="6649f-156">The DevTools team has also released some extensions for [Visual Studio Code][VisualStudioCode] that let you use the power of the DevTools directly from your text editor!</span></span> <span data-ttu-id="6649f-157">请查看以下扩展：</span><span class="sxs-lookup"><span data-stu-id="6649f-157">Check out the extensions below:</span></span>  

#### <a name="elements-for-microsoft-edge"></a><span data-ttu-id="6649f-158">用于Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="6649f-158">Elements for Microsoft Edge</span></span>  

<span data-ttu-id="6649f-159">通过添加[\Microsoft Edge\(Chromium\) ][VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension] Visual Studio Code 元素，在 Visual Studio Code 元素工具。</span><span class="sxs-lookup"><span data-stu-id="6649f-159">Use the Elements tool from within Visual Studio Code by adding the [Elements for Microsoft Edge \(Chromium\)][VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension] Visual Studio Code extension.</span></span>  

:::image type="complex" source="../../images/2020/01/elements-for-edge.msft.png" alt-text="使用元素扩展Visual Studio Code元素的 Microsoft Edge 工具" lightbox="../../images/2020/01/elements-for-edge.msft.png":::
   <span data-ttu-id="6649f-161">元素**工具**Visual Studio Code元素扩展Microsoft Edge元素</span><span class="sxs-lookup"><span data-stu-id="6649f-161">The **Elements** tool in Visual Studio Code using the Elements for Microsoft Edge extension</span></span>  
:::image-end:::  

<span data-ttu-id="6649f-162">有关详细信息，请查看元素[的扩展Microsoft Edge Visual Studio Code元素][VisualStudioCodeElementEdgeExtension]。</span><span class="sxs-lookup"><span data-stu-id="6649f-162">For more information, check out [Elements for Microsoft Edge Visual Studio Code extension][VisualStudioCodeElementEdgeExtension].</span></span>  

#### <a name="debugger-for-microsoft-edge"></a><span data-ttu-id="6649f-163">调试程序Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="6649f-163">Debugger for Microsoft Edge</span></span>  

<span data-ttu-id="6649f-164">使用[调试器 for Microsoft Edge][VisualStudioMarketplaceDebuggerEdge] Visual Studio Code 扩展，直接从 Visual Studio Code 调试 Microsoft Edge 中运行的 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="6649f-164">With the [Debugger for Microsoft Edge][VisualStudioMarketplaceDebuggerEdge] Visual Studio Code extension, debug JavaScript running in Microsoft Edge directly from Visual Studio Code.</span></span>  

:::image type="complex" source="../../images/2020/01/vscode-debugger.msft.png" alt-text="Microsoft Edge Extension 的调试Visual Studio Code" lightbox="../../images/2020/01/vscode-debugger.msft.png":::
   <span data-ttu-id="6649f-166">Microsoft Edge Extension 的调试Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="6649f-166">The Debugger for Microsoft Edge Extension in Visual Studio Code</span></span>  
:::image-end:::  

<span data-ttu-id="6649f-167">有关详细信息，请查看如何从 Microsoft Edge[调试Visual Studio Code。][VisualStudioCodeDebuggerEdgeExtension]</span><span class="sxs-lookup"><span data-stu-id="6649f-167">For more information, check out [how to debug Microsoft Edge from Visual Studio Code][VisualStudioCodeDebuggerEdgeExtension].</span></span>  

#### <a name="webhint"></a><span data-ttu-id="6649f-168">webhint</span><span class="sxs-lookup"><span data-stu-id="6649f-168">webhint</span></span>  

<span data-ttu-id="6649f-169">[Webhint][VisualStudioMarketplaceWebhintExtension] Visual Studio Code在编写网页 `webhint` 时用于改进网页。</span><span class="sxs-lookup"><span data-stu-id="6649f-169">The [webhint][VisualStudioMarketplaceWebhintExtension] Visual Studio Code extension uses `webhint` to improve your web page while you are writing it.</span></span>  <span data-ttu-id="6649f-170">此扩展将运行，并基于分析报告工作区文件的 `webhint` 诊断。</span><span class="sxs-lookup"><span data-stu-id="6649f-170">This extension runs and reports diagnostics on your workspace files based on `webhint` analysis.</span></span>  

:::image type="complex" source="../../images/2020/01/webhint-vscode-extension.msft.png" alt-text="Webhint Visual Studio Code扩展，用于分析 web 中的 .tsx Visual Studio Code" lightbox="../../images/2020/01/webhint-vscode-extension.msft.png":::
   <span data-ttu-id="6649f-172">Webhint Visual Studio Code分析 `.tsx` 文件中文件的扩展Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="6649f-172">The webhint Visual Studio Code extension analyzing a `.tsx` file in Visual Studio Code</span></span>  
:::image-end:::  

<span data-ttu-id="6649f-173">[详细了解 webhint Visual Studio Code 。][WebhintVisualStudioCodeExtension]</span><span class="sxs-lookup"><span data-stu-id="6649f-173">[Learn more about the Visual Studio Code webhint extension][WebhintVisualStudioCodeExtension].</span></span>  

### <a name="visual-studio-integration"></a><span data-ttu-id="6649f-174">Visual Studio集成</span><span class="sxs-lookup"><span data-stu-id="6649f-174">Visual Studio integration</span></span>  

<span data-ttu-id="6649f-175">在 Visual Studio 2019 版本 16.2 或更高版本中，使用 Visual Studio 调试程序调试在 Microsoft Edge 中运行的 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="6649f-175">In Visual Studio 2019 version 16.2 or later, use the Visual Studio debugger to debug JavaScript running in Microsoft Edge.</span></span>  <span data-ttu-id="6649f-176">[下载Visual Studio 2019][MicrosoftVisualStudioDownloads]以试用此功能！</span><span class="sxs-lookup"><span data-stu-id="6649f-176">[Download Visual Studio 2019][MicrosoftVisualStudioDownloads] to try this feature out!</span></span>  

:::image type="complex" source="../../images/2020/01/vs.msft.png" alt-text="Visual Studio Canary、Dev 或 Beta Microsoft Edge启动 Web 应用的选项" lightbox="../../images/2020/01/vs.msft.png":::
   <span data-ttu-id="6649f-178">Visual Studio Canary、Dev 或 Beta Microsoft Edge启动 Web 应用的选项</span><span class="sxs-lookup"><span data-stu-id="6649f-178">Visual Studio with the option to launch your web app in Microsoft Edge Canary, Dev, or Beta</span></span>  
:::image-end:::  

<span data-ttu-id="6649f-179">[详细了解如何从 Microsoft Edge 调试Visual Studio。][VisualStudioIndex]</span><span class="sxs-lookup"><span data-stu-id="6649f-179">[Learn more about debugging Microsoft Edge from Visual Studio][VisualStudioIndex].</span></span>  

### <a name="tracking-prevention-console-messages"></a><span data-ttu-id="6649f-180">跟踪防护控制台消息</span><span class="sxs-lookup"><span data-stu-id="6649f-180">Tracking prevention Console messages</span></span>  

<span data-ttu-id="6649f-181">跟踪防护是网站中Microsoft Edge一项功能，可保护你免受之前未访问过的网站的跟踪。</span><span class="sxs-lookup"><span data-stu-id="6649f-181">Tracking prevention is a unique feature in Microsoft Edge that protects you from being tracked by websites you have not visited before.</span></span>  <span data-ttu-id="6649f-182">默认跟踪防护设置为平衡模式，可阻止第三方跟踪器和已知的恶意跟踪器，从而获得平衡隐私和 Web 兼容性的体验。</span><span class="sxs-lookup"><span data-stu-id="6649f-182">The default tracking prevention setting is Balanced mode, which blocks 3rd party trackers and known malicious trackers for an experience that balances privacy and web compatibility.</span></span>  <span data-ttu-id="6649f-183">为了让你深入了解阻止某些跟踪程序时网页的兼容性，当跟踪器被阻止时，控制台中添加了警告消息。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="6649f-183">To give you more insight into the compatibility of your web page when certain trackers are blocked, warning messages were added in the **Console** when a tracker is blocked.</span></span>  

:::image type="complex" source="../../images/2020/01/tracking-prevention.msft.png" alt-text="跟踪防护时控制台中的邮件阻止对跟踪器存储的访问" lightbox="../../images/2020/01/tracking-prevention.msft.png":::
   <span data-ttu-id="6649f-185">跟踪防护 **时控制台** 中的邮件阻止对跟踪器存储的访问</span><span class="sxs-lookup"><span data-stu-id="6649f-185">Messages in the **Console** when tracking prevention blocks access to storage for a tracker</span></span>  
:::image-end:::  

<span data-ttu-id="6649f-186">[阅读有关跟踪防护以及隐私与 Web 兼容性之间平衡的详细信息][TrackingPrevention]。</span><span class="sxs-lookup"><span data-stu-id="6649f-186">[Read more about tracking prevention and the balance between privacy and web compatibility][TrackingPrevention].</span></span>  

## <a name="announcements-from-the-chromium-project"></a><span data-ttu-id="6649f-187">来自 Chromium 项目的公告</span><span class="sxs-lookup"><span data-stu-id="6649f-187">Announcements from the Chromium project</span></span>  

<span data-ttu-id="6649f-188">以下各节宣布 81 Microsoft Edge开放源代码管理项目中提供的其他Chromium功能。</span><span class="sxs-lookup"><span data-stu-id="6649f-188">The following sections announce additional features available in Microsoft Edge 81 that were contributed to the open source Chromium project.</span></span>  

### <a name="moto-g4-support-in-device-mode"></a><span data-ttu-id="6649f-189">设备模式下的 Moto G4 支持</span><span class="sxs-lookup"><span data-stu-id="6649f-189">Moto G4 support in Device Mode</span></span>  

<span data-ttu-id="6649f-190">启用 [设备工具栏后][DevtoolsDeviceModeIndexSimulateMobileViewport]，从设备列表中模拟 Moto G4 **视口** 的尺寸。</span><span class="sxs-lookup"><span data-stu-id="6649f-190">After [enabling the Device Toolbar][DevtoolsDeviceModeIndexSimulateMobileViewport], simulate the dimensions of a Moto G4 viewport from the **Device** list.</span></span>  

:::image type="complex" source="../../images/2020/01/motog4.msft.png" alt-text="模拟 Moto G4 视口" lightbox="../../images/2020/01/motog4.msft.png":::
   <span data-ttu-id="6649f-192">模拟 Moto G4 视口</span><span class="sxs-lookup"><span data-stu-id="6649f-192">Simulating a Moto G4 viewport</span></span>  
:::image-end:::  

<span data-ttu-id="6649f-193">选择 ["显示设备框架][DevtoolsDeviceModeIndexShowDeviceFrame] "以在视口周围显示 Moto G4 硬件。</span><span class="sxs-lookup"><span data-stu-id="6649f-193">Choose [Show Device Frame][DevtoolsDeviceModeIndexShowDeviceFrame] to show the Moto G4 hardware around the viewport.</span></span>  

:::image type="complex" source="../../images/2020/01/motog4frame.msft.png" alt-text="显示 Moto G4 硬件" lightbox="../../images/2020/01/motog4frame.msft.png":::
   <span data-ttu-id="6649f-195">显示 Moto G4 硬件</span><span class="sxs-lookup"><span data-stu-id="6649f-195">Showing the Moto G4 hardware</span></span>  
:::image-end:::  

<span data-ttu-id="6649f-196">相关功能：</span><span class="sxs-lookup"><span data-stu-id="6649f-196">Related features:</span></span>  

*   <span data-ttu-id="6649f-197">打开[命令菜单][DevtoolsCommandMenuIndex]并运行命令，在启用"显示设备框架"菜单后，为包含 Moto G4 硬件 (的视口拍摄 `Capture screenshot`) 。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="6649f-197">Open the [Command Menu][DevtoolsCommandMenuIndex] and run the `Capture screenshot` command to take a screenshot of the viewport that includes the Moto G4 hardware (after enabling **Show Device Frame**).</span></span>  
*   <span data-ttu-id="6649f-198">[限制网络和 CPU][DevtoolsDeviceModeIndexThrottleNetworkCpu] 以更精确地模拟移动用户的 Web 浏览条件。</span><span class="sxs-lookup"><span data-stu-id="6649f-198">[Throttle the network and CPU][DevtoolsDeviceModeIndexThrottleNetworkCpu] to more accurately simulate a mobile user's web browsing conditions.</span></span>  

<span data-ttu-id="6649f-199">Chromium问题[#924693][CR924693]</span><span class="sxs-lookup"><span data-stu-id="6649f-199">Chromium issue [#924693][CR924693]</span></span>  

### <a name="cookie-related-updates"></a><span data-ttu-id="6649f-200">与 Cookie 相关的更新</span><span class="sxs-lookup"><span data-stu-id="6649f-200">Cookie-related updates</span></span>  

#### <a name="blocked-cookies-in-the-cookies-pane"></a><span data-ttu-id="6649f-201">"Cookie"窗格中阻止的 Cookie</span><span class="sxs-lookup"><span data-stu-id="6649f-201">Blocked cookies in the Cookies pane</span></span>  

<span data-ttu-id="6649f-202">"应用程序"面板中的"Cookie"窗格现在显示带黄色背景的阻止的 Cookie。</span><span class="sxs-lookup"><span data-stu-id="6649f-202">The Cookies pane in the Application panel now displays blocked cookies with a yellow background.</span></span>  

:::image type="complex" source="../../images/2020/01/blockedcookies.msft.png" alt-text="应用程序面板的 Cookie 窗格中阻止的 Cookie" lightbox="../../images/2020/01/blockedcookies.msft.png":::
   <span data-ttu-id="6649f-204">"应用程序"面板的"Cookie"窗格中阻止的 Cookie</span><span class="sxs-lookup"><span data-stu-id="6649f-204">Blocked cookies in the Cookies pane of the Application panel</span></span>  
:::image-end:::  

<span data-ttu-id="6649f-205">Chromium问题[#1030258][CR1030258]</span><span class="sxs-lookup"><span data-stu-id="6649f-205">Chromium issue [#1030258][CR1030258]</span></span>  <!-- inaccessible  -->  

#### <a name="cookie-priority-in-the-cookie-pane"></a><span data-ttu-id="6649f-206">Cookie 窗格中的 Cookie 优先级</span><span class="sxs-lookup"><span data-stu-id="6649f-206">Cookie priority in the Cookie pane</span></span>  

<span data-ttu-id="6649f-207">网络和应用程序 **工具中的** Cookie **表现在** 包含"优先级 **"** 列。</span><span class="sxs-lookup"><span data-stu-id="6649f-207">The Cookies tables in the **Network** and **Application** tools now include a **Priority** column.</span></span>  

> [!CAUTION]
> <span data-ttu-id="6649f-208">Chromium的浏览器（如 Microsoft Edge）是唯一支持 Cookie 优先级的浏览器。</span><span class="sxs-lookup"><span data-stu-id="6649f-208">Chromium-based browsers, like Microsoft Edge, are the only browsers that support cookie priority.</span></span>  

<span data-ttu-id="6649f-209">Chromium问题[#1026879][CR1026879]</span><span class="sxs-lookup"><span data-stu-id="6649f-209">Chromium issue [#1026879][CR1026879]</span></span>  

#### <a name="edit-all-cookie-values"></a><span data-ttu-id="6649f-210">编辑所有 Cookie 值</span><span class="sxs-lookup"><span data-stu-id="6649f-210">Edit all cookie values</span></span>  

<span data-ttu-id="6649f-211">Cookie 表中的所有单元格现在均可编辑 **，"大小** "列中的单元格除外，因为该列表示 Cookie 的网络大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="6649f-211">All cells in the Cookie tables are editable now, except cells in the **Size** column because that column represents the network size of the cookie, in bytes.</span></span>  <span data-ttu-id="6649f-212">有关每列的说明，请导航到"字段["。][DevtoolsStorageCookiesFields]</span><span class="sxs-lookup"><span data-stu-id="6649f-212">For an explanation of each column, navigate to [Fields][DevtoolsStorageCookiesFields].</span></span>  

:::image type="complex" source="../../images/2020/01/editcookie.msft.png" alt-text="编辑 Cookie 值" lightbox="../../images/2020/01/editcookie.msft.png":::
   <span data-ttu-id="6649f-214">编辑 Cookie 值</span><span class="sxs-lookup"><span data-stu-id="6649f-214">Editing a cookie value</span></span>  
:::image-end:::  

#### <a name="copy-as-nodejs-fetch-to-include-cookie-data"></a><span data-ttu-id="6649f-215">复制为Node.js提取以包含 Cookie 数据</span><span class="sxs-lookup"><span data-stu-id="6649f-215">Copy as Node.js fetch to include cookie data</span></span>  

<span data-ttu-id="6649f-216">若要获取包含 Cookie 数据的表达式，请将鼠标悬停在网络请求上，打开上下文菜单 \(右键单击\) ，然后选择"复制复制"作为"Node.js `fetch` >  **提取"。**</span><span class="sxs-lookup"><span data-stu-id="6649f-216">To get a `fetch` expression that includes cookie data, hover on a network request, open the contextual menu \(right-click\), and choose **Copy** > **Copy as Node.js fetch**.</span></span>  

:::image type="complex" source="../../images/2020/01/fetchcookies.msft.png" alt-text="作为提取Node.js复制" lightbox="../../images/2020/01/fetchcookies.msft.png":::
   <span data-ttu-id="6649f-218">作为提取Node.js复制</span><span class="sxs-lookup"><span data-stu-id="6649f-218">Copy as Node.js fetch</span></span>  
:::image-end:::  

<span data-ttu-id="6649f-219">Chromium问题[#1029826][CR1029826]</span><span class="sxs-lookup"><span data-stu-id="6649f-219">Chromium issue [#1029826][CR1029826]</span></span>  

### <a name="more-accurate-web-app-manifest-icons"></a><span data-ttu-id="6649f-220">更准确的 Web 应用清单图标</span><span class="sxs-lookup"><span data-stu-id="6649f-220">More accurate web app manifest icons</span></span>  

<span data-ttu-id="6649f-221">以前，应用程序面板中的"清单"窗格发送了自己的请求，以显示 Web 应用部件清单图标。</span><span class="sxs-lookup"><span data-stu-id="6649f-221">Previously, the Manifest pane in the Application panel sent its own requests in order to display web app manifest icons.</span></span>  <span data-ttu-id="6649f-222">DevTools 现在显示你使用的完全相同Microsoft Edge图标。</span><span class="sxs-lookup"><span data-stu-id="6649f-222">DevTools now shows the exact same manifest icon that Microsoft Edge uses.</span></span>  

:::image type="complex" source="../../images/2020/01/manifesticons.msft.png" alt-text="清单窗格中的图标" lightbox="../../images/2020/01/manifesticons.msft.png":::
   <span data-ttu-id="6649f-224">清单窗格中的图标</span><span class="sxs-lookup"><span data-stu-id="6649f-224">Icons in the Manifest pane</span></span>  
:::image-end:::  

<span data-ttu-id="6649f-225">Chromium问题[#985402][CR985402]</span><span class="sxs-lookup"><span data-stu-id="6649f-225">Chromium issue [#985402][CR985402]</span></span>  

### <a name="hover-on-css-content-properties-to-display-unescaped-values"></a><span data-ttu-id="6649f-226">将鼠标悬停在 CSS 内容属性上以显示未转义的值</span><span class="sxs-lookup"><span data-stu-id="6649f-226">Hover on CSS content properties to display unescaped values</span></span>  

<span data-ttu-id="6649f-227">将鼠标悬停在 `content` 属性的值上可显示该值的未转义版本。</span><span class="sxs-lookup"><span data-stu-id="6649f-227">Hover on the value of a `content` property to display the unescaped version of the value.</span></span>  

<span data-ttu-id="6649f-228">例如，在此 [演示中][CSSContentDemo] ，检查伪元素时，转义字符串 `p::after` 将显示在" **样式** "窗格中：</span><span class="sxs-lookup"><span data-stu-id="6649f-228">For example, in this [demo][CSSContentDemo] when you inspect the `p::after` pseudo-element an escaped string is displayed in the **Styles** pane:</span></span>  

:::image type="complex" source="../../images/2020/01/escapedstring.msft.png" alt-text="转义字符串" lightbox="../../images/2020/01/escapedstring.msft.png":::
   <span data-ttu-id="6649f-230">转义字符串</span><span class="sxs-lookup"><span data-stu-id="6649f-230">The escaped string</span></span>  
:::image-end:::  

<span data-ttu-id="6649f-231">当您将鼠标悬停在 `content` 该值上时，将显示未转义的值。</span><span class="sxs-lookup"><span data-stu-id="6649f-231">When you hover on the `content` value, the unescaped value is displayed.</span></span>  

:::image type="complex" source="../../images/2020/01/unescapedstring.msft.png" alt-text="未转义值" lightbox="../../images/2020/01/unescapedstring.msft.png":::
   <span data-ttu-id="6649f-233">未转义值</span><span class="sxs-lookup"><span data-stu-id="6649f-233">The unescaped value</span></span>  
:::image-end:::  

### <a name="more-detailed-source-map-errors-in-the-console"></a><span data-ttu-id="6649f-234">控制台中更详细的源映射错误</span><span class="sxs-lookup"><span data-stu-id="6649f-234">More detailed source map errors in the Console</span></span>  

<span data-ttu-id="6649f-235">控制台现在提供有关源映射无法加载或分析的原因的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="6649f-235">The Console now provides more detail on why a source map failed to load or parse.</span></span>  <span data-ttu-id="6649f-236">以前，它只是提供了一个错误，而没有解释错误。</span><span class="sxs-lookup"><span data-stu-id="6649f-236">Previously it just provided an error without explaining what went wrong.</span></span>  

:::image type="complex" source="../../images/2020/01/sourcemap.msft.png" alt-text="控制台中的源映射加载错误" lightbox="../../images/2020/01/sourcemap.msft.png":::
   <span data-ttu-id="6649f-238">控制台中的源映射加载错误</span><span class="sxs-lookup"><span data-stu-id="6649f-238">A source map loading error in the Console</span></span>  
:::image-end:::  

### <a name="setting-for-disabling-scrolling-past-the-end-of-a-file"></a><span data-ttu-id="6649f-239">用于禁用滚动过文件末尾的设置</span><span class="sxs-lookup"><span data-stu-id="6649f-239">Setting for disabling scrolling past the end of a file</span></span>  

<span data-ttu-id="6649f-240">打开[设置，][DevtoolsCustomizeIndexSettings]然后禁用首选项源\*\*\*\* 允许滚动文件末尾以禁用默认 UI 行为，该行为允许你在"源"面板中的文件末尾良好  >  > 滚动。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="6649f-240">Open [Settings][DevtoolsCustomizeIndexSettings] and then disable **Preferences** > **Sources** > **Allow scrolling past end of file** to disable the default UI behavior that allows you to scroll well past the end of a file in the **Sources** panel.</span></span>  

:::image type="complex" source="../../images/2020/01/settings.msft.png" alt-text="禁用 允许滚动到文件的末尾" lightbox="../../images/2020/01/settings.msft.png":::
   <span data-ttu-id="6649f-242">禁用**允许滚动到文件末尾设置**</span><span class="sxs-lookup"><span data-stu-id="6649f-242">Disabling **Allow scrolling past end of file** in Settings</span></span>  
:::image-end:::  

:::image type="complex" source="../../images/2020/01/scrollingsources.msft.png" alt-text="滚动过文件末尾现在在"源"面板中处于禁用状态" lightbox="../../images/2020/01/scrollingsources.msft.png":::
   <span data-ttu-id="6649f-244">滚动过文件末尾现在在"源"面板中处于禁用状态</span><span class="sxs-lookup"><span data-stu-id="6649f-244">Scrolling past the end of a file is now disabled in the Sources panel</span></span>  
:::image-end:::  

## <a name="download-the-microsoft-edge-preview-channels"></a><span data-ttu-id="6649f-245">下载 Microsoft Edge 预览频道</span><span class="sxs-lookup"><span data-stu-id="6649f-245">Download the Microsoft Edge preview channels</span></span>  

<span data-ttu-id="6649f-246">如果你使用的是 Windows 或 macOS，请考虑使用 [ Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels] 作为默认开发浏览器。</span><span class="sxs-lookup"><span data-stu-id="6649f-246">If you are on Windows or macOS, consider using the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] as your default development browser.</span></span>  <span data-ttu-id="6649f-247">预览频道使你能够访问最新的 DevTools 功能。</span><span class="sxs-lookup"><span data-stu-id="6649f-247">The preview channels give you access to the latest DevTools features.</span></span>  

## <a name="getting-in-touch-with-microsoft-edge-devtools-team"></a><span data-ttu-id="6649f-248">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="6649f-248">Getting in touch with Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- links -->  

[DevtoolsDeviceModeIndexSimulateMobileViewport]: ../../../device-mode/index.md#simulate-a-mobile-viewport "模拟移动视区 - 在 DevTools Microsoft Edge设备模式下模拟移动设备|Microsoft Docs"
[DevtoolsDeviceModeIndexShowDeviceFrame]: ../../../device-mode/index.md#show-device-frame "显示设备帧 - 在 DevTools Microsoft Edge设备模式下模拟移动设备|Microsoft Docs"
[DevtoolsCommandMenuIndex]: ../../../command-menu/index.md "使用 Microsoft Edge DevTools 命令菜单运行命令 | Microsoft Docs"  
[DevtoolsDeviceModeIndexThrottleNetworkCpu]: ../../../device-mode/index.md#throttle-the-network-and-cpu "限制网络和 CPU - 在 DevTools Microsoft Edge设备模式下模拟移动设备|Microsoft Docs"
[DevtoolsCustomizeIndexSettings]: ../../../customize/index.md#settings "设置 - 自定义 Microsoft Edge DevTools | Microsoft Docs"
[DevtoolsStorageCookiesFields]: ../../../storage/cookies.md#fields "字段 - 使用 DevTools Microsoft Edge、查看、编辑和|Microsoft Docs"  

[VisualStudioIndex]: ../../../../visual-studio/index.md "Visual Studio |Microsoft Docs"  

[VisualStudioCodeDebuggerEdgeExtension]: ../../../../visual-studio-code/debugger-for-edge.md "调试程序Microsoft Edge Visual Studio Code扩展|Microsoft Docs"  
[VisualStudioCodeElementEdgeExtension]: ../../../../visual-studio-code/elements-for-edge.md "扩展Microsoft Edge Visual Studio Code元素|Microsoft Docs"  

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download "Microsoft Edge 预览频道"  

[VisualStudioCode]: https://code.visualstudio.com "Visual Studio Code"  
[VisualStudioMarketplaceDebuggerEdge]: https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge "调试程序Microsoft Edge |Visual StudioMarketplace"  
[VisualStudioMarketplaceElementsMicrosoftEdgeChromiumExtension]: https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools "Microsoft Edge \(Chromium\) |Visual StudioMarketplace"  
[VisualStudioMarketplaceWebhintExtension]: https://marketplace.visualstudio.com/items?itemName=webhint.vscode-webhint "webhint |Visual StudioMarketplace"

[TrackingPrevention]: https://blogs.windows.com/msedgedev/2019/12/03/improving-tracking-prevention-microsoft-edge-79 "改进跟踪防护Microsoft Edge博客文章"

[MicrosoftEdgeInsiderAddons]: https://microsoftedge.microsoft.com/addons/detail/webhint/mlgfbihcfnkaenjpdcngdnhcpkdmcdee "Microsoft Edge预览体验成员加载项"  
[MicrosoftVisualStudioDownloads]: https://visualstudio.microsoft.com/downloads "下载 Visual Studio 2019 for Windows & Mac"  

[PostTweetEdgeDevTools]: https://twitter.com/intent/tweet?text=@EdgeDevTools "@EdgeDevTools | 发布推文"  

[CR924693]: https://crbug.com/924693 "功能请求：将 Moto G4 添加到设备模式列表|ChromiumBug"  
[CR1030258]: https://crbug.com/1030258 "CR 1030258 |ChromiumBug"  
[CR1026879]: https://crbug.com/1026879 "开发人员控制台中的&quot;Cookie&quot;选项卡不再显示优先级|ChromiumBug"  
[CR1029826]: https://crbug.com/1029826 "network tab -> right choose to request -> copy -> copy as fetch does not copy cookies |ChromiumBug"  
[CR985402]: https://crbug.com/985402 "Web 应用清单图标错误字符串令人困惑|ChromiumBug"  
[CR963183]: https://crbug.com/963183 "DevTools 不符合 WCAG |ChromiumBug"  
[CR941561]: https://crbug.com/941561 "DevTools 工具的本地化|ChromiumBug"  
[CR987787]: https://crbug.com/987787 "Dom 3D 视图|ChromiumBug"  

[CSSContentDemo]: https://mathiasbynens.github.io/css-dbg-stories/css-escapes.html "未转义 CSS 内容的演示"  

[GitHubMicrosoftDocsEdgeDeveloperNewIssue]: https://github.com/MicrosoftDocs/edge-developer/issues/new?title=[DevTools%20Docs%20Feedback] "新问题 - MicrosoftDocs/edge-developer"  

[TheWebWeWant]: https://webwewant.fyi "我们需要的 Web"  
[AccessibilityInsights]: https://accessibilityinsights.io "辅助功能见解"  
[MDNDocumentObjectModel]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model "文档对象模型 (DOM) |MDN"  
[MDNZIndex]: https://developer.mozilla.org/docs/Web/CSS/z-index "z-index |MDN"  
[EdgeDevToolsTwitterAccount]: https://twitter.com/EdgeDevTools "@EdgeDevTools Twitter 帐户"  

[Webhint]: https://webhint.io "webhint"  

[WebhintBrowserExtension]: https://webhint.io/docs/user-guide/extensions/extension-browser "Webhint 浏览器扩展|webhint 文档"  
[WebhintVisualStudioCodeExtension]: https://webhint.io/docs/user-guide/extensions/vscode-webhint "Webhint Visual Studio Code Extension |webhint 文档"  

> [!NOTE]
> <span data-ttu-id="6649f-285">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="6649f-285">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="6649f-286">原始页面位于[此处](https://developer.chrome.com/blog/new-in-devtools-81)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="6649f-286">The original page is found [here](https://developer.chrome.com/blog/new-in-devtools-81) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="6649f-288">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="6649f-288">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  