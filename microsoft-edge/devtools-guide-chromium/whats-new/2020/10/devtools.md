---
description: 新的 CSS 网格调试工具、Webauthn 工具、可移动工具和计算的边栏面板。
title: DevTools (Microsoft Edge 87) 中的新增功能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/22/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 0e4b1972918797d69e2068236f6d1336c54cc858
ms.sourcegitcommit: 6e2b26d41a0aa56ac34e6edc7dddd852ddb415b1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2020
ms.locfileid: "11133962"
---
# <span data-ttu-id="a5ad0-104">DevTools (Microsoft Edge 87) 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="a5ad0-104">What's New In DevTools (Microsoft Edge 87)</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/edge-whats-new-note.md)]  

## <span data-ttu-id="a5ad0-105">改进 DevTools 本地化</span><span class="sxs-lookup"><span data-stu-id="a5ad0-105">Improving DevTools localization</span></span>  

<span data-ttu-id="a5ad0-106">为了满足您的翻译需求，Microsoft Edge DevTools 团队致力于改进翻译质量。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-106">To meet your translation needs, the Microsoft Edge DevTools team is focused on improving translation quality.</span></span>  <span data-ttu-id="a5ad0-107">从 Microsoft Edge 版本87开始，将锁定多个字符串和术语，即使 DevTools 的其余部分以其他语言显示，也不会更改。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-107">Starting in Microsoft Edge version 87, several strings and terms are locked and do not change even when the rest of the DevTools are displayed in other languages.</span></span>  <span data-ttu-id="a5ad0-108">受影响的字符串和术语的列表包括以下。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-108">The list of affected strings and terms include the following.</span></span>  

*   <span data-ttu-id="a5ad0-109">**Lighthouse**工具中的字符串。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-109">The strings in the **Lighthouse** tool.</span></span>  
*   <span data-ttu-id="a5ad0-110">术语 `service worker` 。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-110">The term `service worker`.</span></span>  
*   <span data-ttu-id="a5ad0-111">某些 **网络** 工具筛选器，如、 `URL` 、 `XHR` `JS` 和 `CSS` 。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-111">Some of the **Network** tool filters such as `URL`, `XHR`, `JS`, and `CSS`.</span></span>  
*   <span data-ttu-id="a5ad0-112">[$0][DevtoolsGuideChromiumConsoleUtilitiesRecentlySelectedElementJavascriptObject]控制台实用工具 API。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-112">The [$0][DevtoolsGuideChromiumConsoleUtilitiesRecentlySelectedElementJavascriptObject] Console Utilities API.</span></span>  
    
<span data-ttu-id="a5ad0-113">[$0][DevtoolsGuideChromiumConsoleUtilitiesRecentlySelectedElementJavascriptObject] 目前在 DevTools 的本地化版本的用户的 [控制台](/microsoft-edge/devtools-guide-chromium/console/index.md) 中可用。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-113">[$0][DevtoolsGuideChromiumConsoleUtilitiesRecentlySelectedElementJavascriptObject] is now available in the [Console](/microsoft-edge/devtools-guide-chromium/console/index.md) for users on localized versions of the DevTools.</span></span>   <span data-ttu-id="a5ad0-114">感谢您参加全球开发人员社区，帮助改进 Microsoft Edge DevTools 的本地化。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-114">Thank you to the global developer community for helping improve localization of the Microsoft Edge DevTools.</span></span>  <span data-ttu-id="a5ad0-115">继续 [发送本地化质量反馈](#getting-in-touch-with-microsoft-edge-devtools-team) ，以改进对所有区域设置中的 DevTools 的支持。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-115">Continue to [send feedback on localization quality](#getting-in-touch-with-microsoft-edge-devtools-team) to improve support for DevTools in all locales.</span></span>  <span data-ttu-id="a5ad0-116">若要在 Chromium open 源代码项目中查看此功能的实时更新，请导航到 "问题 [#1136655][CR1136655]"。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-116">To review real-time updates on this feature in the Chromium open-source project, navigate to Issue [#1136655][CR1136655].</span></span>  

:::image type="complex" source="../../media/2020/10/bing-network-japanese.msft.png" alt-text="具有非本地化筛选器的网络工具" lightbox="../../media/2020/10/bing-network-japanese.msft.png":::
   <span data-ttu-id="a5ad0-118">具有非本地化筛选器的**网络**窗格</span><span class="sxs-lookup"><span data-stu-id="a5ad0-118">**Network** pane with non-localized filters</span></span>  
:::image-end:::  

## <span data-ttu-id="a5ad0-119">在顶部面板和底部面板之间移动工具</span><span class="sxs-lookup"><span data-stu-id="a5ad0-119">Move tools between top and bottom panels</span></span>  

<span data-ttu-id="a5ad0-120">DevTools 现在支持在顶部面板和底部面板之间移动工具。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-120">DevTools now supports moving tools between the top and bottom panels.</span></span>  <span data-ttu-id="a5ad0-121">通过同时查看两个工具的组合，自定义您的 DevTools 并提高工作效率。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-121">Customize your DevTools and improve your productivity by viewing any combination of two tools at the same time.</span></span>  <span data-ttu-id="a5ad0-122">例如，通过将 "**源**" 工具移动到底部的 \ ) ，同时查看 "**元素**" 和 "**源**" 工具 (。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-122">For example, view the **Elements** and the **Sources** tools at the same time \(by moving the **Sources** tool to the bottom\).</span></span>  <span data-ttu-id="a5ad0-123">若要在 Chromium open 源代码项目中查看此功能的历史记录，请导航到 "问题 [#1075732][CR1075732]"。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-123">To review the history of this feature in the Chromium open-source project, navigate to Issue [#1075732][CR1075732].</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="a5ad0-124">若要将任何顶部工具移到底部，请将鼠标悬停在选项卡上，打开上下文菜单 \ (右键单击 "\ ) "，然后选择 " **移至底部**"。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-124">To move any top tool to the bottom, hover on a tab, open the contextual menu \(right-click\), and choose **Move to bottom**.</span></span>  
      
      :::image type="complex" source="../../media/2020/10/move-to-bottom.msft.png" alt-text="具有非本地化筛选器的网络工具" lightbox="../../media/2020/10/move-to-bottom.msft.png":::
         <span data-ttu-id="a5ad0-126">移至底部</span><span class="sxs-lookup"><span data-stu-id="a5ad0-126">Move to bottom</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="a5ad0-127">若要将任何底部工具移到顶部，请将鼠标悬停在选项卡上，打开上下文菜单 \ (右键单击 "\ ) "，然后选择 " **移至页首**"。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-127">To move any bottom tool to the top, hover on a tab, open the contextual menu \(right-click\), and choose **Move to top**.</span></span>  
      
      :::image type="complex" source="../../media/2020/10/move-to-top.msft.png" alt-text="具有非本地化筛选器的网络工具" lightbox="../../media/2020/10/move-to-top.msft.png":::
         <span data-ttu-id="a5ad0-129">移到页首</span><span class="sxs-lookup"><span data-stu-id="a5ad0-129">Move to top</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::

## <span data-ttu-id="a5ad0-130">使用网络控制台保存和导出</span><span class="sxs-lookup"><span data-stu-id="a5ad0-130">Save and export using the Network Console</span></span>  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="具有非本地化筛选器的网络工具":::
   <span data-ttu-id="a5ad0-132">实验性功能</span><span class="sxs-lookup"><span data-stu-id="a5ad0-132">Experimental feature</span></span>  
:::image-end:::  

<span data-ttu-id="a5ad0-133">**网络控制台**工具现在改进了与[Postman v 2.1][PostmanSchemaJsonCollectionv210Index]和[OpenAPI v2][SwaggerSpecificationV2]架构的兼容性。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-133">The **Network Console** tool now has improved compatibility with the [Postman v2.1][PostmanSchemaJsonCollectionv210Index] and [OpenAPI v2][SwaggerSpecificationV2] schemas.</span></span>  <span data-ttu-id="a5ad0-134">若要启用实验，请导航到 ["启用实验功能][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures] "，然后选择 " **启用网络控制台**" 旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-134">To enable the experiment, navigate to [Turn on Experimental features][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures] and choose the checkbox next to **Enable Network Console**.</span></span>  <span data-ttu-id="a5ad0-135">有关 **网络控制台**的详细信息，请导航以 [启用网络控制台实验功能][DevtoolsExperimentalFeaturesEnableNetworkConsole]。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-135">For more information about the **Network Console**, navigate to [Enable Network Console Experimental feature][DevtoolsExperimentalFeaturesEnableNetworkConsole].</span></span>  <span data-ttu-id="a5ad0-136">此次实验现在支持下列操作。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-136">This experiment now supports the following actions.</span></span>  

*   <span data-ttu-id="a5ad0-137">保存和导出集合和环境。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-137">Save and export Collections and Environments.</span></span>  
*   <span data-ttu-id="a5ad0-138">在 **网络控制台** 工具中编辑和导出环境变量集。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-138">Edit and export sets of environment variables within the **Network Console** tool.</span></span>  
    
<span data-ttu-id="a5ad0-139">若要在 Chromium open 源代码项目中查看此功能的实时更新，请导航到 "问题 [#1093687][CR1093687]"。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-139">To review real-time updates on this feature in the Chromium open-source project, navigate to Issue [#1093687][CR1093687].</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/network-console-environments-new-name.msft.png" alt-text="具有非本地化筛选器的网络工具" lightbox="../../media/2020/10/network-console-environments-new-name.msft.png":::
         <span data-ttu-id="a5ad0-141">为新环境输入名称</span><span class="sxs-lookup"><span data-stu-id="a5ad0-141">Enter name for the new environment</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/network-console-environments-new-format.msft.png" alt-text="具有非本地化筛选器的网络工具" lightbox="../../media/2020/10/network-console-environments-new-format.msft.png":::
         <span data-ttu-id="a5ad0-143">为新环境选择格式</span><span class="sxs-lookup"><span data-stu-id="a5ad0-143">Choose format for the new environment</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <span data-ttu-id="a5ad0-144">改进的 CSS 网格工具</span><span class="sxs-lookup"><span data-stu-id="a5ad0-144">Improved CSS Grid tooling</span></span>  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="具有非本地化筛选器的网络工具":::
   <span data-ttu-id="a5ad0-146">实验性功能</span><span class="sxs-lookup"><span data-stu-id="a5ad0-146">Experimental feature</span></span>  
:::image-end:::  

<span data-ttu-id="a5ad0-147">Microsoft Edge DevTools 现在支持用于检查、查看和调试 CSS 网格的以下功能。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-147">The Microsoft Edge DevTools now support the following features for inspecting, viewing, and debugging your CSS grids.</span></span>  

*   <span data-ttu-id="a5ad0-148">使用 " **检查** " 工具显示简化的网格覆盖，或获取更详细的具有永久重叠的信息。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-148">Display a simplified grid overlay using the **Inspect** tool, or get more detailed information with persistent overlays.</span></span>  
*   <span data-ttu-id="a5ad0-149">若要启用永久网格覆盖，请选择 " **元素** " 工具中网格容器元素旁边的网格图标，或在 **布局** 工具中选择网格。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-149">To enable persistent grid overlays, choose the grid icon next to a grid container element in the **Elements** tool or choose the grid in the **Layout** tool.</span></span>  
*   <span data-ttu-id="a5ad0-150">你可以为多个网格启用永久覆盖。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-150">You may enable persistent overlays for multiple grids.</span></span>  
*   <span data-ttu-id="a5ad0-151">新的 **布局** 工具使你可以轻松地切换网格覆盖并配置每个网格的外观和内容。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-151">The new **Layout** tool allows you to easily toggle grid overlays and configure the appearance and the content for each.</span></span>  
    
<span data-ttu-id="a5ad0-152">默认情况下，功能处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-152">The features are turned on by default.</span></span>  <span data-ttu-id="a5ad0-153">有关这些功能的详细信息，请导航到 " [CSS 网格][DevtoolsCssGrid]"。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-153">For more information about the features, navigate to [CSS grids][DevtoolsCssGrid].</span></span>  <span data-ttu-id="a5ad0-154">若要在 Chromium open 源代码项目中查看此功能的历史记录，请导航到 "问题 [#1047356][CR1047356]"。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-154">To review the history of this feature in the Chromium open-source project, navigate to Issue [#1047356][CR1047356].</span></span>  <span data-ttu-id="a5ad0-155">此外，Microsoft Edge DevTools 团队正与 Chrome DevTools 团队和 Chromium 社区协作，将新的 flexbox 工具功能添加到 DevTools。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-155">Additionally, the Microsoft Edge DevTools team is collaborating with the Chrome DevTools team and Chromium community to add new flexbox tooling features to DevTools.</span></span>  <span data-ttu-id="a5ad0-156">有关 Chromium open source 项目中的 flexbox 工具的更新，请导航到 "问题 [#1136394][CR1136394]"。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-156">For updates on flexbox tooling in the Chromium open-source project, navigate to Issue [#1136394][CR1136394].</span></span>  

:::image type="complex" source="../../media/2020/10/grid-layout-pane.msft.png" alt-text="具有非本地化筛选器的网络工具" lightbox="../../media/2020/10/grid-layout-pane.msft.png":::
   <span data-ttu-id="a5ad0-158">带有网格的**布局**工具</span><span class="sxs-lookup"><span data-stu-id="a5ad0-158">**Layout** tool with grids</span></span>  
:::image-end:::  

## <span data-ttu-id="a5ad0-159">在 "设置" 中自定义键盘快捷方式</span><span class="sxs-lookup"><span data-stu-id="a5ad0-159">Customize keyboard shortcuts in Settings</span></span>  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="具有非本地化筛选器的网络工具":::
   <span data-ttu-id="a5ad0-161">实验性功能</span><span class="sxs-lookup"><span data-stu-id="a5ad0-161">Experimental feature</span></span>  
:::image-end:::  

<span data-ttu-id="a5ad0-162">现在，你可以自定义 DevTools 中任何操作的键盘快捷方式。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-162">You are now able to customize the keyboard shortcut for any action in the DevTools.</span></span>  <span data-ttu-id="a5ad0-163">由于 Microsoft Edge 版本84，你可以在**Visual Studio 中选择 Visual Studio 代码**和 DevTools ([键盘快捷方式][DevtoolsCustomizeShortcuts]的\*\*默认) \*\*预设。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-163">Since Microsoft Edge version 84, you are able to choose between **Visual Studio Code** and **DevTools (default)** presets for [keyboard shortcuts][DevtoolsCustomizeShortcuts].</span></span>  <span data-ttu-id="a5ad0-164">从 Microsoft Edge 版本87开始，你可以打开 " **启用键盘快捷方式编辑器** " 体验，进一步 [自定义键盘快捷方式][DevtoolsExperimentalFeaturesEnableKeyboardShortcutEditor]。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-164">Starting in Microsoft Edge version 87, you may turn on the **Enable keyboard shortcut editor** experiment to further [customize keyboard shortcuts][DevtoolsExperimentalFeaturesEnableKeyboardShortcutEditor].</span></span>  

<span data-ttu-id="a5ad0-165">若要启用实验，请导航到 ["启用实验功能][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures] "，然后选中 " **启用键盘快捷方式编辑器**" 旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-165">To enable the experiment, navigate to [Turn on Experimental features][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures] and choose the checkbox next to **Enable keyboard shortcut editor**.</span></span>  <span data-ttu-id="a5ad0-166">有关自定义和编辑快捷方式的详细信息，请导航以 [启用键盘快捷方式编辑器实验功能][DevtoolsExperimentalFeaturesEnableKeyboardShortcutEditor]。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-166">For more information about customizing and editing shortcuts, navigate to [Enable keyboard shortcut editor Experimental feature][DevtoolsExperimentalFeaturesEnableKeyboardShortcutEditor].</span></span>  <span data-ttu-id="a5ad0-167">若要在 Chromium open 源代码项目中查看此功能的实时更新，请导航到 "问题 [#174309][CR174309]"。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-167">To review real-time updates on this feature in the Chromium open-source project, navigate to Issue [#174309][CR174309].</span></span>  

:::image type="complex" source="../../media/2020/10/custom-shortcut-pause-script.msft.png" alt-text="具有非本地化筛选器的网络工具" lightbox="../../media/2020/10/custom-shortcut-pause-script.msft.png":::
   <span data-ttu-id="a5ad0-169">用于暂停脚本的自定义快捷方式</span><span class="sxs-lookup"><span data-stu-id="a5ad0-169">Custom shortcut for pausing a script</span></span>  
:::image-end:::  

## <span data-ttu-id="a5ad0-170">介绍 Visual Studio 代码扩展的 Microsoft Edge 工具</span><span class="sxs-lookup"><span data-stu-id="a5ad0-170">Introducing the Microsoft Edge Tools for Visual Studio Code extension</span></span>  

<span data-ttu-id="a5ad0-171">Visual studio 代码和**网络 For Visual Studio 代码**扩展的**元素**现在合并到[visual Studio 代码扩展的新 Microsoft Edge 开发人员工具][VisualStudioCodeMarketplaceMsEdgedevtools]中。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-171">The **Elements for Visual Studio Code** and **Network for Visual Studio Code** extensions are now merged into the new [Microsoft Edge Developer Tools for Visual Studio Code][VisualStudioCodeMarketplaceMsEdgedevtools] extension.</span></span>  <span data-ttu-id="a5ad0-172">在不退出 Visual Studio 代码的情况下使用 Microsoft Edge DevTools 执行下列活动。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-172">Use the Microsoft Edge DevTools for the following activities without leaving Visual Studio Code.</span></span>  

*   <span data-ttu-id="a5ad0-173">调试 DOM</span><span class="sxs-lookup"><span data-stu-id="a5ad0-173">Debug the DOM</span></span>  
*   <span data-ttu-id="a5ad0-174">编辑 CSS</span><span class="sxs-lookup"><span data-stu-id="a5ad0-174">Edit CSS</span></span>  
*   <span data-ttu-id="a5ad0-175">检查网络流量</span><span class="sxs-lookup"><span data-stu-id="a5ad0-175">Inspect network traffic</span></span>  

<span data-ttu-id="a5ad0-176">使用扩展，启动 Microsoft Edge，连接到浏览器的现有实例，或直接从编辑器使用无外设浏览器。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-176">With the extension, launch Microsoft Edge, connect to an existing instance of the browser, or use a headless browser directly from your editor.</span></span>  <span data-ttu-id="a5ad0-177">若要开始对有关此扩展的反馈提出和归档问题，请导航到 GitHub 上 [Visual Studio 代码库的 Microsoft Edge 开发人员工具][GithubMicrosoftVscodeEdgeDevtools] 。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-177">To start contributing and filing issues with your feedback about this extension, navigate to the [Microsoft Edge Developer Tools for Visual Studio Code][GithubMicrosoftVscodeEdgeDevtools] repo on GitHub.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/microsoft-edge-tools-full-browser.msft.png" alt-text="具有非本地化筛选器的网络工具" lightbox="../../media/2020/10/microsoft-edge-tools-full-browser.msft.png":::
         <span data-ttu-id="a5ad0-179">在完整浏览器模式下使用扩展屏幕截图</span><span class="sxs-lookup"><span data-stu-id="a5ad0-179">Using the extension in full browser mode screenshot</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/microsoft-edge-tools-headless.msft.png" alt-text="具有非本地化筛选器的网络工具" lightbox="../../media/2020/10/microsoft-edge-tools-headless.msft.png":::
         <span data-ttu-id="a5ad0-181">在无外设模式的屏幕截图中使用扩展</span><span class="sxs-lookup"><span data-stu-id="a5ad0-181">Using the extension in headless mode screenshot</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <span data-ttu-id="a5ad0-182">来自 Chromium 项目的公告</span><span class="sxs-lookup"><span data-stu-id="a5ad0-182">Announcements from the Chromium project</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/chromium-whats-new-note.md)]  

### <span data-ttu-id="a5ad0-183">新的 WebAuthn 工具</span><span class="sxs-lookup"><span data-stu-id="a5ad0-183">New WebAuthn tool</span></span>  

<span data-ttu-id="a5ad0-184">在早期版本的 Microsoft Edge 中，没有本机的 WebAuthn 调试支持。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-184">In earlier versions of Microsoft Edge, there was no native WebAuthn debugging support.</span></span>  <span data-ttu-id="a5ad0-185">您需要物理 authenticators 以通过 [Web 身份验证 API][GithubW3cWebauthn]测试 web 应用程序。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-185">You needed physical authenticators to test your web application with the [Web Authentication API][GithubW3cWebauthn].</span></span>  <span data-ttu-id="a5ad0-186">使用新的 " **WebAuthn** " 工具，你可以执行以下操作，而无需使用任何物理 authenticators。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-186">With the new **WebAuthn** tool, you are able to do the following actions without the use of any physical authenticators.</span></span>

*   <span data-ttu-id="a5ad0-187">模拟 authenticators</span><span class="sxs-lookup"><span data-stu-id="a5ad0-187">Emulate authenticators</span></span>
*   <span data-ttu-id="a5ad0-188">自定义 authenticators 的属性</span><span class="sxs-lookup"><span data-stu-id="a5ad0-188">Customize attributes of authenticators</span></span>
*   <span data-ttu-id="a5ad0-189">检查 authenticators 的状态</span><span class="sxs-lookup"><span data-stu-id="a5ad0-189">Inspect states of authenticators</span></span>
    
<span data-ttu-id="a5ad0-190">有关 **WebAuthn** 功能的详细信息，请 [在 Microsoft Edge DevTools 中导航到模拟 Authenticators 和调试 WebAuthn][DevtoolsWebauthnIndex]。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-190">For more information about the **WebAuthn** feature, navigate to [Emulate authenticators and debug WebAuthn in Microsoft Edge DevTools][DevtoolsWebauthnIndex].</span></span>  

<span data-ttu-id="a5ad0-191">你可以通过新的 " [WebAuthn][DevtoolsWebauthnIndex] " 工具模拟 authenticators 和调试[WEB 身份验证 API][GithubW3cWebauthn] 。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-191">You are able to emulate authenticators and debug the [Web Authentication API][GithubW3cWebauthn] with the new [WebAuthn][DevtoolsWebauthnIndex] tool.</span></span>  <span data-ttu-id="a5ad0-192">若要打开 " **WebAuthn** " 工具，请选择 **"自定义和控制 DevTools** \ (`...` \ ) " 图标 > "**更多工具" 工具**  >  **WebAuthn**。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-192">To open the **WebAuthn** tool, choose **the Customize and control DevTools** \(`...`\) icon > **More tools** > **WebAuthn**.</span></span>  <span data-ttu-id="a5ad0-193">若要在 Chromium open 源代码项目中查看此功能的实时更新，请导航到 "问题 [#1034663][CR1034663]"。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-193">To review real-time updates on this feature in the Chromium open-source project, navigate to Issue [#1034663][CR1034663].</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/more-tools-webauthn.msft.png" alt-text="具有非本地化筛选器的网络工具" lightbox="../../media/2020/10/more-tools-webauthn.msft.png":::
         <span data-ttu-id="a5ad0-195">打开 " **WebAuthn** 工具"</span><span class="sxs-lookup"><span data-stu-id="a5ad0-195">Open the **WebAuthn** tool</span></span>  
      :::image-end:::  
   :::column-end:::  
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/webauthn-enable-virtual-auth.msft.png" alt-text="具有非本地化筛选器的网络工具" lightbox="../../media/2020/10/webauthn-enable-virtual-auth.msft.png":::
         <span data-ttu-id="a5ad0-197">**WebAuthn** 工具</span><span class="sxs-lookup"><span data-stu-id="a5ad0-197">**WebAuthn** tool</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

### <span data-ttu-id="a5ad0-198">元素工具更新</span><span class="sxs-lookup"><span data-stu-id="a5ad0-198">Elements tool updates</span></span>  

#### <span data-ttu-id="a5ad0-199">在 "样式" 窗格中查看 "计算的边栏" 窗格</span><span class="sxs-lookup"><span data-stu-id="a5ad0-199">View the Computed sidebar pane in the Styles pane</span></span>  

<span data-ttu-id="a5ad0-200">切换 "**样式**" 窗格中的**计算**窗格。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-200">Toggle the **Computed** pane in the **Styles** pane.</span></span>  <span data-ttu-id="a5ad0-201">默认情况下，"**样式**" 窗格中的**计算**窗格处于折叠状态。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-201">The **Computed** pane in the **Styles** pane is collapsed by default.</span></span>  <span data-ttu-id="a5ad0-202">若要切换它，请选择该按钮。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-202">To toggle it, choose the button.</span></span>  <span data-ttu-id="a5ad0-203">若要在 Chromium open 源代码项目中查看此功能的实时更新，请导航到 "问题 [#1073899][CR1073899]"。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-203">To review real-time updates on this feature in the Chromium open-source project, navigate to Issue [#1073899][CR1073899].</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/computed-sidebar-pane.msft.png" alt-text="具有非本地化筛选器的网络工具" lightbox="../../media/2020/10/computed-sidebar-pane.msft.png":::
         <span data-ttu-id="a5ad0-205">打开 " **计算的边栏** " 窗格</span><span class="sxs-lookup"><span data-stu-id="a5ad0-205">Open the **Computed sidebar** pane</span></span>  
      :::image-end:::  
   :::column-end:::  
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/computed-sidebar-pane-open.msft.png" alt-text="具有非本地化筛选器的网络工具" lightbox="../../media/2020/10/computed-sidebar-pane-open.msft.png":::
         <span data-ttu-id="a5ad0-207">**计算的边栏** 窗格</span><span class="sxs-lookup"><span data-stu-id="a5ad0-207">**Computed sidebar** pane</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

#### <span data-ttu-id="a5ad0-208">在计算的面板中对 CSS 属性进行分组</span><span class="sxs-lookup"><span data-stu-id="a5ad0-208">Grouping CSS properties in the Computed panel</span></span>  

<span data-ttu-id="a5ad0-209">若要使用较少的滚动查看已应用的 CSS，请按 **计算** 窗格中的类别对 css 属性进行分组。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-209">To view your applied CSS with less scrolling, group the CSS properties by categories in the **Computed** pane.</span></span>  <span data-ttu-id="a5ad0-210">你还可以在检查你的 CSS 时有选择地将焦点放在一组相关的属性上。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-210">You may also selectively focus on a set of related properties while you inspect your CSS.</span></span>  <span data-ttu-id="a5ad0-211">从 " **元素** " 工具中，选择一个元素。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-211">From the **Elements** tool, choose an element.</span></span>  <span data-ttu-id="a5ad0-212">若要组 \ (或取消组合 ) CSS 属性，请切换 " **组** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-212">To group \(or ungroup\) the CSS properties, toggle the **Group** checkbox.</span></span>  <span data-ttu-id="a5ad0-213">若要在 Chromium open 源代码项目中查看此功能的实时更新，请导航到 "问题" [#1096230][CR1096230]、" [#1084673][CR1084673]" 和 " [#1106251][CR1106251]"。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-213">To review real-time updates on this feature in the Chromium open-source project, navigate to Issues [#1096230][CR1096230], [#1084673][CR1084673], and [#1106251][CR1106251].</span></span>  

:::image type="complex" source="../../media/2020/10/grouping-css-prop.msft.png" alt-text="具有非本地化筛选器的网络工具" lightbox="../../media/2020/10/grouping-css-prop.msft.png":::
   <span data-ttu-id="a5ad0-215">对 CSS 属性进行分组</span><span class="sxs-lookup"><span data-stu-id="a5ad0-215">Grouping CSS properties</span></span>  
:::image-end:::  

### <span data-ttu-id="a5ad0-216">Lighthouse 工具中的 Lighthouse 6。4</span><span class="sxs-lookup"><span data-stu-id="a5ad0-216">Lighthouse 6.4 in the Lighthouse tool</span></span>  

<span data-ttu-id="a5ad0-217">**Lighthouse**工具现在正在运行 Lighthouse 6.4。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-217">The **Lighthouse** tool is now running Lighthouse 6.4.</span></span>  <span data-ttu-id="a5ad0-218">有关更改的完整列表，请导航到 [Lighthouse 发行说明][GithubGoogleChromeLighthouseReleasesV641]。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-218">For a full list of changes, navigate to the [Lighthouse release notes][GithubGoogleChromeLighthouseReleasesV641].</span></span>  <span data-ttu-id="a5ad0-219">若要在 Chromium open 源代码项目中查看此功能的实时更新，请导航到 "问题 [#772558][CR772558]"。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-219">To review real-time updates on this feature in the Chromium open-source project, navigate to Issue [#772558][CR772558].</span></span>  

### <span data-ttu-id="a5ad0-220">性能：在 "计时" 部分中标记 ( # A1 事件</span><span class="sxs-lookup"><span data-stu-id="a5ad0-220">performance.mark() events in the Timings section</span></span>  

<span data-ttu-id="a5ad0-221">[性能][DevtoolsGuideChromiumEvaluatePerformanceReference]工具中的录制的 "**计时" 部分**现在标记 `performance.mark()` 事件。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-221">The **Timings section** of a recording in the [Performance][DevtoolsGuideChromiumEvaluatePerformanceReference] tool now marks `performance.mark()` events.</span></span>  <span data-ttu-id="a5ad0-222">若要尝试此功能并测量 JavaScript 代码的性能，请将 `performance.mark()` 事件添加到代码。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-222">To try this feature and measure the performance of your JavaScript code, add `performance.mark()` events to your code.</span></span>  <span data-ttu-id="a5ad0-223">例如，以下代码片段 `for` 使用7的增量，在从0循环到1000的循环之前和之后添加标记。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-223">For example, the following code snippet adds markers before and after a `for` loop that iterates from 0 to 1000 using increments of 7.</span></span>  

```javascript
performance.mark('start');
for (var i = 0; i < 1000; i+=7;){
  console.log(i);
}
performance.mark('end');
```  

<span data-ttu-id="a5ad0-224">然后，打开 " [性能][DevtoolsGuideChromiumEvaluatePerformanceReference] " 工具并导航到 " **计时" 部分** ，以记录你的 JavaScript 代码。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-224">Then, open the [Performance][DevtoolsGuideChromiumEvaluatePerformanceReference] tool and navigate to the **Timings section** to record your JavaScript code.</span></span>  <span data-ttu-id="a5ad0-225">`performance.mark()`您添加的事件现在将显示在录制中。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-225">The `performance.mark()` events you added are now displayed in the recording.</span></span>  

:::image type="complex" source="../../media/2020/10/perf-mark.msft.png" alt-text="具有非本地化筛选器的网络工具" lightbox="../../media/2020/10/perf-mark.msft.png":::
   `performance.mark` <span data-ttu-id="a5ad0-227">事件</span><span class="sxs-lookup"><span data-stu-id="a5ad0-227">events</span></span>  
:::image-end:::  

### <span data-ttu-id="a5ad0-228">网络工具中的新资源类型和 url 筛选器</span><span class="sxs-lookup"><span data-stu-id="a5ad0-228">New resource-type and url filters in the Network tool</span></span>  

<span data-ttu-id="a5ad0-229">使用网络工具中的 "新建" `resource-type` 和 " `url` 关键字" 筛选网络请求。 **Network**</span><span class="sxs-lookup"><span data-stu-id="a5ad0-229">Use the new `resource-type` and `url` keywords in the **Network** tool to filter network requests.</span></span>  <span data-ttu-id="a5ad0-230">例如，使用 `resource-type:image` 重点关注图像的网络请求。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-230">For example, use `resource-type:image` to focus on the network requests that are images.</span></span>  

:::image type="complex" source="../../media/2020/10/network-resource-type-filter.msft.png" alt-text="具有非本地化筛选器的网络工具" lightbox="../../media/2020/10/network-resource-type-filter.msft.png":::
   <span data-ttu-id="a5ad0-232">资源类型筛选器</span><span class="sxs-lookup"><span data-stu-id="a5ad0-232">resource-type filter</span></span>  
:::image-end:::  

<span data-ttu-id="a5ad0-233">若要发现更多特殊关键字（如 `resource-type` 和 `url` ），请导航到 " [按属性筛选请求][DevtoolsNetworkReferenceFilterRequestsProperties]"。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-233">To discover more special keywords such as `resource-type` and `url`, navigate to [filter requests by properties][DevtoolsNetworkReferenceFilterRequestsProperties].</span></span>  <span data-ttu-id="a5ad0-234">若要在 Chromium open source 项目中查看此功能的实时更新，请导航到 [#1121141][CR1121141] 和 [#1104188][CR1104188]的问题。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-234">To review real-time updates on this feature in the Chromium open-source project, navigate to Issues [#1121141][CR1121141] and [#1104188][CR1104188].</span></span>  

### <span data-ttu-id="a5ad0-235">框架详细信息视图更新</span><span class="sxs-lookup"><span data-stu-id="a5ad0-235">Frame details view updates</span></span>  

#### <span data-ttu-id="a5ad0-236">将 COEP 和合作基金报告显示给终结点</span><span class="sxs-lookup"><span data-stu-id="a5ad0-236">Display COEP and COOP reporting to endpoint</span></span>  

<span data-ttu-id="a5ad0-237">查看 " `reporting to` **安全 & 隔离** " 部分下的 "跨起源 Embedder 策略 \ (COEP \ ) 和跨源 Opener 策略 \ (合作基金 \ ) 终结点。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-237">View the Cross-Origin Embedder Policy \(COEP\) and Cross-Origin Opener Policy \(COOP\) `reporting to` endpoint under the **Security & Isolation** section.</span></span>  <span data-ttu-id="a5ad0-238">[报告 API][MdnReportingApi]定义了 `Report-To` 一个新的 HTTP 标头，为您提供了一种指定浏览器发送警告和错误的服务器终结点的方法。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-238">The [Reporting API][MdnReportingApi] defines `Report-To`, a new HTTP header, that gives you a way to specify the server endpoints for the browser to send warnings and errors.</span></span>  <span data-ttu-id="a5ad0-239">若要在 Chromium open 源代码项目中查看此功能的实时更新，请导航到 "问题 [#1051466][CR1051466]"。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-239">To review real-time updates on this feature in the Chromium open-source project, navigate to Issue [#1051466][CR1051466].</span></span>  

:::image type="complex" source="../../media/2020/10/https_first_party_test_glitch_me_coop-1.msft.png" alt-text="具有非本地化筛选器的网络工具" lightbox="../../media/2020/10/https_first_party_test_glitch_me_coop-1.msft.png":::
   <span data-ttu-id="a5ad0-241">该 `reporting to` 终结点</span><span class="sxs-lookup"><span data-stu-id="a5ad0-241">The `reporting to` endpoint</span></span>  
:::image-end:::  

#### <span data-ttu-id="a5ad0-242">显示 COEP 和合作基金报告模式</span><span class="sxs-lookup"><span data-stu-id="a5ad0-242">Display COEP and COOP report-only mode</span></span>  

<span data-ttu-id="a5ad0-243">DevTools 现在显示 `report-only` 设置为 "模式" 的 COEP 和市场活动的标签 `report-only` 。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-243">DevTools now display the `report-only` label for COEP and COOP that are set to `report-only` mode.</span></span>  <span data-ttu-id="a5ad0-244">若要在 Chromium open 源代码项目中查看此功能的实时更新，请导航到 "问题 [#1051466][CR1051466]"。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-244">To review real-time updates on this feature in the Chromium open-source project, navigate to Issue [#1051466][CR1051466].</span></span>  

:::image type="complex" source="../../media/2020/10/https_first_party_test_glitch_me_coop-2.msft.png" alt-text="具有非本地化筛选器的网络工具" lightbox="../../media/2020/10/https_first_party_test_glitch_me_coop-2.msft.png":::
   <span data-ttu-id="a5ad0-246">`report-only`模式标签</span><span class="sxs-lookup"><span data-stu-id="a5ad0-246">The `report-only` mode label</span></span>  
:::image-end:::  

### <span data-ttu-id="a5ad0-247">查看和修复 CSS 概述工具中的颜色对比度问题</span><span class="sxs-lookup"><span data-stu-id="a5ad0-247">View and fix color contrast issues in the CSS Overview tool</span></span>  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="具有非本地化筛选器的网络工具":::
   <span data-ttu-id="a5ad0-249">实验性功能</span><span class="sxs-lookup"><span data-stu-id="a5ad0-249">Experimental feature</span></span>  
:::image-end:::  

<span data-ttu-id="a5ad0-250">**CSS 概述**工具现在显示页面上出现颜色对比度问题的元素列表。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-250">The **CSS Overview** tool now displays a list of elements on your page that have color contrast issues.</span></span>  <span data-ttu-id="a5ad0-251">下面的演示页面包含颜色对比度问题的示例。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-251">The following demo page has an example of a color contrast issue.</span></span>  

[<span data-ttu-id="a5ad0-252">CSS 概述易于访问的颜色演示</span><span class="sxs-lookup"><span data-stu-id="a5ad0-252">CSS Overview Accessible Colors Demo</span></span>][GlitchCssOverviewAccessibleColorsDemo]  

<span data-ttu-id="a5ad0-253">若要启用此实验，请在 "**设置**  >  **实验**" 下，选择 " **CSS 概述**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-253">To enable this experiment, under **Settings** > **Experiments**, choose the **CSS Overview** checkbox.</span></span>  <span data-ttu-id="a5ad0-254">若要查看具有颜色对比度问题的元素的列表，请在 **对比度问题**中选择 " **文本**"。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-254">To view a list of elements that have a color contrast issue, on **Contrast issues**, choose **Text**.</span></span>  <span data-ttu-id="a5ad0-255">若要打开 " **元素** " 工具中的元素，请在列表中选择一个元素。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-255">To open the element in the **Elements** tool, choose an element in the list.</span></span>  <span data-ttu-id="a5ad0-256">为了帮助解决对比度问题，Microsoft Edge DevTools [自动提供颜色建议][DevtoolsWhatsnew200208DevtoolsAccessibleColorSuggestionStylesPane]。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-256">To help fix contrast issues, the Microsoft Edge DevTools [automatically provide color suggestions][DevtoolsWhatsnew200208DevtoolsAccessibleColorSuggestionStylesPane].</span></span>  <span data-ttu-id="a5ad0-257">若要在 Chromium open 源代码项目中查看此功能的实时更新，请导航到 "问题 [#1120316][CR1120316]"。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-257">To review real-time updates on this feature in the Chromium open-source project, navigate to Issue [#1120316][CR1120316].</span></span>  

:::image type="complex" source="../../media/2020/10/css-overview.msft.png" alt-text="具有非本地化筛选器的网络工具" lightbox="../../media/2020/10/css-overview.msft.png":::
   <span data-ttu-id="a5ad0-259">低颜色对比度问题</span><span class="sxs-lookup"><span data-stu-id="a5ad0-259">Low color contrast issues</span></span>  
:::image-end:::  

## <span data-ttu-id="a5ad0-260">下载 Microsoft Edge 预览频道</span><span class="sxs-lookup"><span data-stu-id="a5ad0-260">Download the Microsoft Edge preview channels</span></span>  

<span data-ttu-id="a5ad0-261">如果你使用的是 Windows 或 macOS，请考虑使用 [ Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels] 作为默认开发浏览器。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-261">If you are on Windows or macOS, consider using the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] as your default development browser.</span></span>  <span data-ttu-id="a5ad0-262">预览频道使你能够访问最新的 DevTools 功能。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-262">The preview channels give you access to the latest DevTools features.</span></span>  

## <span data-ttu-id="a5ad0-263">与 Microsoft Edge DevTools 团队取得联系</span><span class="sxs-lookup"><span data-stu-id="a5ad0-263">Getting in touch with Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- links -->  

[DevtoolsWhatsnew200205DevtoolsDeprecationPropertiesPaneElementsPanel]: ../05/devtools.md#deprecation-of-the-properties-pane-in-the-elements-tool "弃用 "元素" 工具中的 "属性" 窗格-DevTools 中的新增功能 (Microsoft Edge 84) |Microsoft 文档"  
[DevtoolsWhatsnew200206DevtoolsCssGridDebuggingFeatures]: ../06/devtools.md#css-grid-debugging-features "CSS 网格调试功能-DevTools 中的新增功能 (Microsoft Edge 85) |Microsoft 文档"  
[DevtoolsWhatsnew200208DevtoolsAccessibleColorSuggestionStylesPane]: ../08/devtools.md#accessible-color-suggestion-in-the-styles-pane ""样式" 窗格中的辅助颜色建议-DevTools 中的新增功能 (Microsoft Edge 86) |Microsoft 文档"  

[DevtoolsDeviceModeIndex]: /microsoft-edge/devtools-guide-chromium/device-mode/index "在 Microsoft Edge DevTools 中模拟移动设备 |Microsoft 文档"  
[DevtoolsGuideChromiumConsoleUtilitiesRecentlySelectedElementJavascriptObject]:  https://docs.microsoft.com/microsoft-edge/devtools-guide-chromium/console/utilities#recently-selected-element-or-javascript-object "最近选择的元素或 JavaScript 对象-控制台实用工具 API 参考 |Microsoft 文档"  
[DevtoolsCustomizeShortcuts]: /microsoft-edge/devtools-guide-chromium/customize/shortcuts "自定义 Microsoft Edge DevTools 中的键盘快捷方式 |Microsoft 文档"  
[DevtoolsGuideChromiumEvaluatePerformanceReference]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference "性能分析参考 |Microsoft 文档"  
[DevtoolsExperimentalFeaturesEmulationSupportDualScreenMode]: /microsoft-edge/devtools-guide-chromium/experimental-features#emulation-support-dual-screen-mode "模拟：支持双重屏幕模式-实验功能 |Microsoft 文档"  
[DevtoolsExperimentalFeaturesEnableExperimentalApis]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-experimental-apis "启用实验性 Api-实验性功能 |Microsoft 文档"  
[DevtoolsExperimentalFeaturesEnableKeyboardShortcutEditor]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-keyboard-shortcut-editor "启用键盘快捷方式编辑器-实验功能 |Microsoft 文档"  
[DevtoolsExperimentalFeaturesEnableNewCssGridDebuggingFeatures]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-new-css-grid-debugging-features "模拟：支持双重屏幕模式-实验功能 |Microsoft 文档"  
[DevtoolsExperimentalFeaturesEnableNetworkConsole]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-network-console "启用网络控制台-实验性功能 |Microsoft 文档"  
[DevtoolsExperimentalFeaturesEnableSourceOrderViewer]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-source-order-viewer "启用源订单查看器-实验性功能 |Microsoft 文档"
[DevtoolsExperimentalFeaturesTestingOnFoldableDualScreenDevices]: /microsoft-edge/devtools-guide-chromium/experimental-features#testing-on-foldable-and-dual-screen-devices "在折叠和双屏幕设备上测试-实验功能 |Microsoft 文档"  
[DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures]: /microsoft-edge/devtools-guide-chromium/experimental-features#turn-on-experimental-features "启用实验功能-实验功能 |Microsoft 文档"  
[DevtoolsConsoleApiTable]: /microsoft-edge/devtools-guide-chromium/console/api#table "表-控制台 API 参考 |Microsoft 文档"  
[DevtoolsCoverageIndex]: /microsoft-edge/devtools-guide-chromium/coverage/index "使用 Microsoft Edge DevTools | 中的 "覆盖范围" 选项卡查找未使用的 JavaScript 和 CSS 代码。Microsoft 文档"  
[DevtoolsCssGrid]:  /microsoft-edge/devtools-guide-chromium/css/grid "检查 CSS 网格 |Microsoft 文档"  
[DevtoolsCustomizeIndexDrawer]: /microsoft-edge/devtools-guide-chromium/customize/index#drawer "抽屉-自定义 Microsoft Edge DevTools |Microsoft 文档"  
[DevtoolsCustomizeIndexSettings]: /microsoft-edge/devtools-guide-chromium/customize/index#settings "设置-自定义 Microsoft Edge DevTools |Microsoft 文档"  
[DevtoolsEvaluatePerformanceReferenceAnalyzeRenderingPerformance]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference#analyze-rendering-performance-with-the-rendering-tab "通过 "呈现" 选项卡分析呈现性能-性能分析参考 |Microsoft 文档"  
[DevtoolsMediaIndex]: /microsoft-edge/devtools-guide-chromium/media/index "查看和调试媒体播放器信息 |Microsoft 文档"  
[DevtoolsNetworkReferenceFilterRequestsProperties]: /microsoft-edge/devtools-guide-chromium/network/reference#filter-requests-by-properties  "按属性筛选请求-网络分析参考 |Microsoft 文档"  
[DevtoolsWebauthnIndex]: /microsoft-edge/devtools-guide-chromium/webauthn/index "在 Microsoft Edge DevTools | 中模拟 authenticators 和调试 WebAuthn |Microsoft 文档"  

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download "Microsoft Edge 预览频道"  

[VisualStudioCode]: https://code.visualstudio.com "Visual Studio 代码"  

[VisualStudioCodeMarketplaceMsEdgedevtools]: https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools "适用于 Visual Studio 代码的 Microsoft Edge 工具 |Visual Studio 代码"  

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium bug"  

[CR174309]: https://crbug.com/174309 "DevTools：允许自定义键盘快捷方式/键绑定 |Chromium bug"
[CR772558]: https://crbug.com/772558 "DevTools：更新到最新版本的 Lighthouse |Chromium bug"  
[CR1034663]: https://crbug.com/1034663 "为 "WebAuthn 测试 API" 创建前端 |Chromium bug"  
[CR1047356]: https://crbug.com/1047356 "CSS 网格/Flexbox/表格工具 |Chromium bug"  
[CR1051466]: https://crbug.com/1051466 "在 DevTools | 中支持合作基金/COEP 调试Chromium bug"  
[CR1073899]: https://crbug.com/1073899 ""计算样式" 选项卡在 "响应模式" 中消失 |Chromium bug"  
[CR1075732]: https://crbug.com/1075732 "DevTools 个性化-可移动选项卡 |Chromium bug"  
[CR1084673]: https://crbug.com/1084673 "DevTools：改进了显示 CSS 自定义属性的方式 ( # B1 也称为) 。CSS 变量) 及其值 |Chromium bug"  
[CR1093687]: https://crbug.com/1093687 "创建用于创建和重播合成网络请求的工具 |Chromium bug"  
[CR1096230]: https://crbug.com/1096230 "按计算样式窗格中的类别对 CSS 属性进行分组 |Chromium bug"  
[CR1104188]: https://crbug.com/1104188 "网络工具搜索在搜索完整 URL 时找不到结果 |Chromium bug"  
[CR1106251]: https://crbug.com/1106251 "☂ DevTools：改进 "计算样式" 选项卡 |Chromium bug"  
[CR1120316]: https://crbug.com/1120316 "在 "CSS 概述 > 颜色" 下突出显示 "不良对比度" |Chromium Bug"  
[CR1121141]: https://crbug.com/1121141 "允许按网络日志 | 中的资源类型进行筛选Chromium bug"  
[CR1121312]: https://crbug.com/1121312 "应从 "其他工具" 菜单中删除 "设置" |Chromium bug"  
[CR1136394]: https://crbug.com/1136394 "Flexbox 工具 |Chromium Bug"  
[CR1136655]: https://crbug.com/1136655 "Devtools：本地化 V2 |Chromium bug"  

[MdnReportingApi]: https://developer.mozilla.org/docs/Web/API/Reporting_API "报告 API |MDN"  

[GithubMicrosoftVscodeEdgeDevtools]: https://github.com/Microsoft/vscode-edge-devtools "microsoft/vscode-edge-devtools |GitHub"  

[GithubGoogleChromeLighthouseReleasesV641]: https://github.com/GoogleChrome/lighthouse/releases/v6.4.1 "v 6.4.1-GoogleChrome/lighthouse |GitHub"  

[GithubW3cWebauthn]: https://w3c.github.io/webauthn "Web 身份验证 |GitHub"  

[GlitchCssOverviewAccessibleColorsDemo]: https://css-overview-accessible-colors-demo.glitch.me "你好！ |故障"  

[PostmanSchemaJsonCollectionv210Index]: https://schema.getpostman.com/json/collection/v2.1.0/docs/index.html "Postman 集合格式 v 2.1.0 |Postman"  

[SwaggerSpecificationV2]: https://swagger.io/specification/v2 "OpenAPI 规范 |Swagger"  

<!--[JecFyiDemoPerfMark]: https://jec.fyi/demo/perf-mark "" -->  

> [!NOTE]
> <span data-ttu-id="a5ad0-316">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-316">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="a5ad0-317">原始页面可在 [此处](https://developers.google.com/web/updates/2020/10/devtools/index) 找到，并由 [Jecelyn Yeen][JecelynYeen] (开发人员和 DevTools，Chrome \ ) 。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-317">The original page is found [here](https://developers.google.com/web/updates/2020/10/devtools/index) and is authored by [Jecelyn Yeen][JecelynYeen] \(Developer advocate, Chrome DevTools\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="a5ad0-319">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="a5ad0-319">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen  
