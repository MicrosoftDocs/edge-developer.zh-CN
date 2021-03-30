---
description: 新的 CSS 网格调试工具、Webauthn 工具、可移动工具和计算边栏面板。
title: 'Microsoft Edge 87 (DevTools 中的新增) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: 53aa8f20ba400c7ff95432b1e752f1f008dac919
ms.sourcegitcommit: e29cd1c393fc1f433dba8c3d8f260b425ade63a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/13/2021
ms.locfileid: "11408330"
---
<!-- Copyright Jecelyn Yeen 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->  
# <a name="whats-new-in-devtools-microsoft-edge-87"></a><span data-ttu-id="74dd4-104">Microsoft Edge 87 开发人员工具中的 (功能) </span><span class="sxs-lookup"><span data-stu-id="74dd4-104">What's New In DevTools (Microsoft Edge 87)</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/edge-whats-new-note.md)]  

## <a name="improving-devtools-localization"></a><span data-ttu-id="74dd4-105">改进 DevTools 本地化</span><span class="sxs-lookup"><span data-stu-id="74dd4-105">Improving DevTools localization</span></span>  

<span data-ttu-id="74dd4-106">为了满足翻译需求，Microsoft Edge DevTools 团队专注于提高翻译质量。</span><span class="sxs-lookup"><span data-stu-id="74dd4-106">To meet your translation needs, the Microsoft Edge DevTools team is focused on improving translation quality.</span></span>  <span data-ttu-id="74dd4-107">从 Microsoft Edge 版本 87 开始，锁定了多个字符串和术语，即使开发人员工具的其余部分以其他语言显示，这些字符串和术语也不会改变。</span><span class="sxs-lookup"><span data-stu-id="74dd4-107">Starting in Microsoft Edge version 87, several strings and terms are locked and do not change even when the rest of the DevTools are displayed in other languages.</span></span>  <span data-ttu-id="74dd4-108">受影响字符串和术语的列表包括以下内容。</span><span class="sxs-lookup"><span data-stu-id="74dd4-108">The list of affected strings and terms include the following.</span></span>  

*   <span data-ttu-id="74dd4-109">**Lighthouse 工具中的**字符串。</span><span class="sxs-lookup"><span data-stu-id="74dd4-109">The strings in the **Lighthouse** tool.</span></span>  
*   <span data-ttu-id="74dd4-110">术语 `service worker` 。</span><span class="sxs-lookup"><span data-stu-id="74dd4-110">The term `service worker`.</span></span>  
*   <span data-ttu-id="74dd4-111">一些 **网络工具** 筛选器，如 `URL` `XHR` 、、 `JS` 和 `CSS` 。</span><span class="sxs-lookup"><span data-stu-id="74dd4-111">Some of the **Network** tool filters such as `URL`, `XHR`, `JS`, and `CSS`.</span></span>  
*   <span data-ttu-id="74dd4-112">[$0][DevtoolsGuideChromiumConsoleUtilitiesRecentlySelectedElementJavascriptObject]控制台实用程序 API。</span><span class="sxs-lookup"><span data-stu-id="74dd4-112">The [$0][DevtoolsGuideChromiumConsoleUtilitiesRecentlySelectedElementJavascriptObject] Console Utilities API.</span></span>  
    
<span data-ttu-id="74dd4-113">现在，在控制台中[为](/microsoft-edge/devtools-guide-chromium/console/index.md)使用 DevTools 本地化版本的用户提供[$0。][DevtoolsGuideChromiumConsoleUtilitiesRecentlySelectedElementJavascriptObject]</span><span class="sxs-lookup"><span data-stu-id="74dd4-113">[$0][DevtoolsGuideChromiumConsoleUtilitiesRecentlySelectedElementJavascriptObject] is now available in the [Console](/microsoft-edge/devtools-guide-chromium/console/index.md) for users on localized versions of the DevTools.</span></span>   <span data-ttu-id="74dd4-114">感谢全球开发人员社区帮助改进 Microsoft Edge DevTools 的本地化。</span><span class="sxs-lookup"><span data-stu-id="74dd4-114">Thank you to the global developer community for helping improve localization of the Microsoft Edge DevTools.</span></span>  <span data-ttu-id="74dd4-115">继续 [发送本地化质量反馈](#getting-in-touch-with-microsoft-edge-devtools-team) ，以改进在所有区域设置中对 DevTools 的支持。</span><span class="sxs-lookup"><span data-stu-id="74dd4-115">Continue to [send feedback on localization quality](#getting-in-touch-with-microsoft-edge-devtools-team) to improve support for DevTools in all locales.</span></span>  <span data-ttu-id="74dd4-116">若要在 Chromium 开源项目中查看此功能实时更新，请导航到"问题[#1136655。][CR1136655]</span><span class="sxs-lookup"><span data-stu-id="74dd4-116">To review real-time updates on this feature in the Chromium open-source project, navigate to Issue [#1136655][CR1136655].</span></span>  

:::image type="complex" source="../../media/2020/10/bing-network-japanese.msft.png" alt-text="具有非本地化筛选器的网络工具" lightbox="../../media/2020/10/bing-network-japanese.msft.png":::
   <span data-ttu-id="74dd4-118">**具有** 非本地化筛选器的网络窗格</span><span class="sxs-lookup"><span data-stu-id="74dd4-118">**Network** pane with non-localized filters</span></span>  
:::image-end:::  

## <a name="move-tools-between-top-and-bottom-panels"></a><span data-ttu-id="74dd4-119">在顶部和底部面板之间移动工具</span><span class="sxs-lookup"><span data-stu-id="74dd4-119">Move tools between top and bottom panels</span></span>  

<span data-ttu-id="74dd4-120">DevTools 现在支持在顶部和底部面板之间移动工具。</span><span class="sxs-lookup"><span data-stu-id="74dd4-120">DevTools now supports moving tools between the top and bottom panels.</span></span>  <span data-ttu-id="74dd4-121">通过同时查看两个工具的任意组合来自定义 DevTools 并提高工作效率。</span><span class="sxs-lookup"><span data-stu-id="74dd4-121">Customize your DevTools and improve your productivity by viewing any combination of two tools at the same time.</span></span>  <span data-ttu-id="74dd4-122">例如，将"源"工具移动到 底部\(的同时查看"元素"和"源") 。 </span><span class="sxs-lookup"><span data-stu-id="74dd4-122">For example, view the **Elements** and the **Sources** tools at the same time \(by moving the **Sources** tool to the bottom\).</span></span>  <span data-ttu-id="74dd4-123">若要查看 Chromium 开源项目中此功能的历史记录，请导航到"问题[#1075732"。][CR1075732]</span><span class="sxs-lookup"><span data-stu-id="74dd4-123">To review the history of this feature in the Chromium open-source project, navigate to Issue [#1075732][CR1075732].</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="74dd4-124">若要将任何顶部工具移动到底部，请将鼠标悬停在选项卡上，打开上下文菜单 \(右键单击\) ，然后选择"移动到**底部"。**</span><span class="sxs-lookup"><span data-stu-id="74dd4-124">To move any top tool to the bottom, hover on a tab, open the contextual menu \(right-click\), and choose **Move to bottom**.</span></span>  
      
      :::image type="complex" source="../../media/2020/10/move-to-bottom.msft.png" alt-text="移动到底部" lightbox="../../media/2020/10/move-to-bottom.msft.png":::
         <span data-ttu-id="74dd4-126">移动到底部</span><span class="sxs-lookup"><span data-stu-id="74dd4-126">Move to bottom</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="74dd4-127">若要将任何底部工具移动到顶部，请将鼠标悬停在选项卡上，打开上下文菜单 \(右键单击\) ，然后选择"移动到**顶部"。**</span><span class="sxs-lookup"><span data-stu-id="74dd4-127">To move any bottom tool to the top, hover on a tab, open the contextual menu \(right-click\), and choose **Move to top**.</span></span>  
      
      :::image type="complex" source="../../media/2020/10/move-to-top.msft.png" alt-text="移动到顶部" lightbox="../../media/2020/10/move-to-top.msft.png":::
         <span data-ttu-id="74dd4-129">移动到顶部</span><span class="sxs-lookup"><span data-stu-id="74dd4-129">Move to top</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::

## <a name="save-and-export-using-the-network-console"></a><span data-ttu-id="74dd4-130">使用网络控制台保存和导出</span><span class="sxs-lookup"><span data-stu-id="74dd4-130">Save and export using the Network Console</span></span>  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="实验性功能":::
   <span data-ttu-id="74dd4-132">实验性功能</span><span class="sxs-lookup"><span data-stu-id="74dd4-132">Experimental feature</span></span>  
:::image-end:::  

<span data-ttu-id="74dd4-133">网络 **控制台** 工具现在改进了与 [Postman v2.1][PostmanSchemaJsonCollectionv210Index] 和 [OpenAPI v2 架构][SwaggerSpecificationV2] 的兼容性。</span><span class="sxs-lookup"><span data-stu-id="74dd4-133">The **Network Console** tool now has improved compatibility with the [Postman v2.1][PostmanSchemaJsonCollectionv210Index] and [OpenAPI v2][SwaggerSpecificationV2] schemas.</span></span>  <span data-ttu-id="74dd4-134">若要启用实验，请导航到打开 [实验][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures] 功能，然后选择启用网络控制台旁边的 **复选框**。</span><span class="sxs-lookup"><span data-stu-id="74dd4-134">To enable the experiment, navigate to [Turn on Experimental features][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures] and choose the checkbox next to **Enable Network Console**.</span></span>  <span data-ttu-id="74dd4-135">有关网络控制台 **详细信息，请**导航到启用 [网络控制台实验功能][DevtoolsExperimentalFeaturesEnableNetworkConsole]。</span><span class="sxs-lookup"><span data-stu-id="74dd4-135">For more information about the **Network Console**, navigate to [Enable Network Console Experimental feature][DevtoolsExperimentalFeaturesEnableNetworkConsole].</span></span>  <span data-ttu-id="74dd4-136">此实验现在支持以下操作。</span><span class="sxs-lookup"><span data-stu-id="74dd4-136">This experiment now supports the following actions.</span></span>  

*   <span data-ttu-id="74dd4-137">保存和导出集合和环境。</span><span class="sxs-lookup"><span data-stu-id="74dd4-137">Save and export Collections and Environments.</span></span>  
*   <span data-ttu-id="74dd4-138">在网络控制台工具中编辑和导出 **环境变量** 集。</span><span class="sxs-lookup"><span data-stu-id="74dd4-138">Edit and export sets of environment variables within the **Network Console** tool.</span></span>  
    
<span data-ttu-id="74dd4-139">若要在 Chromium 开源项目中查看此功能实时更新，请导航到"问题 [#1093687"][CR1093687]。</span><span class="sxs-lookup"><span data-stu-id="74dd4-139">To review real-time updates on this feature in the Chromium open-source project, navigate to Issue [#1093687][CR1093687].</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/network-console-environments-new-name.msft.png" alt-text="输入新环境的名称" lightbox="../../media/2020/10/network-console-environments-new-name.msft.png":::
         <span data-ttu-id="74dd4-141">输入新环境的名称</span><span class="sxs-lookup"><span data-stu-id="74dd4-141">Enter name for the new environment</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/network-console-environments-new-format.msft.png" alt-text="选择新环境的格式" lightbox="../../media/2020/10/network-console-environments-new-format.msft.png":::
         <span data-ttu-id="74dd4-143">选择新环境的格式</span><span class="sxs-lookup"><span data-stu-id="74dd4-143">Choose format for the new environment</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="improved-css-grid-tooling"></a><span data-ttu-id="74dd4-144">改进的 CSS 网格工具</span><span class="sxs-lookup"><span data-stu-id="74dd4-144">Improved CSS Grid tooling</span></span>  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="实验性功能":::
   <span data-ttu-id="74dd4-146">实验性功能</span><span class="sxs-lookup"><span data-stu-id="74dd4-146">Experimental feature</span></span>  
:::image-end:::  

<span data-ttu-id="74dd4-147">Microsoft Edge DevTools 现在支持以下功能来检查、查看和调试 CSS 网格。</span><span class="sxs-lookup"><span data-stu-id="74dd4-147">The Microsoft Edge DevTools now support the following features for inspecting, viewing, and debugging your CSS grids.</span></span>  

*   <span data-ttu-id="74dd4-148">使用 Inspect 工具显示简化的网格 **覆盖，或** 获取有关永久性覆盖的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="74dd4-148">Display a simplified grid overlay using the **Inspect** tool, or get more detailed information with persistent overlays.</span></span>  
*   <span data-ttu-id="74dd4-149">若要启用持久网格覆盖，请选择"元素"工具中网格容器元素旁边的网格图标， 或在"布局"工具**中选择**网格。</span><span class="sxs-lookup"><span data-stu-id="74dd4-149">To enable persistent grid overlays, choose the grid icon next to a grid container element in the **Elements** tool or choose the grid in the **Layout** tool.</span></span>  
*   <span data-ttu-id="74dd4-150">你可以为多个网格启用永久性覆盖。</span><span class="sxs-lookup"><span data-stu-id="74dd4-150">You may enable persistent overlays for multiple grids.</span></span>  
*   <span data-ttu-id="74dd4-151">新的 **布局** 工具允许你轻松切换网格覆盖，并为每个覆盖层配置外观和内容。</span><span class="sxs-lookup"><span data-stu-id="74dd4-151">The new **Layout** tool allows you to easily toggle grid overlays and configure the appearance and the content for each.</span></span>  
    
<span data-ttu-id="74dd4-152">默认情况下，这些功能为打开状态。</span><span class="sxs-lookup"><span data-stu-id="74dd4-152">The features are turned on by default.</span></span>  <span data-ttu-id="74dd4-153">有关功能详细信息，请导航到 [CSS 网格][DevtoolsCssGrid]。</span><span class="sxs-lookup"><span data-stu-id="74dd4-153">For more information about the features, navigate to [CSS grids][DevtoolsCssGrid].</span></span>  <span data-ttu-id="74dd4-154">若要查看 Chromium 开放源代码项目中此功能的历史记录，请导航到"问题[#1047356"。][CR1047356]</span><span class="sxs-lookup"><span data-stu-id="74dd4-154">To review the history of this feature in the Chromium open-source project, navigate to Issue [#1047356][CR1047356].</span></span>  <span data-ttu-id="74dd4-155">此外，Microsoft Edge DevTools 团队正在与 Chrome DevTools 团队和 Chromium 社区协作，向 DevTools 添加新的弹性框工具功能。</span><span class="sxs-lookup"><span data-stu-id="74dd4-155">Additionally, the Microsoft Edge DevTools team is collaborating with the Chrome DevTools team and Chromium community to add new flexbox tooling features to DevTools.</span></span>  <span data-ttu-id="74dd4-156">有关 Chromium 开源项目中 flexbox 工具的更新，请导航到"问题 [#1136394"][CR1136394]。</span><span class="sxs-lookup"><span data-stu-id="74dd4-156">For updates on flexbox tooling in the Chromium open-source project, navigate to Issue [#1136394][CR1136394].</span></span>  

:::image type="complex" source="../../media/2020/10/grid-layout-pane.msft.png" alt-text="具有网格的布局工具" lightbox="../../media/2020/10/grid-layout-pane.msft.png":::
   <span data-ttu-id="74dd4-158">**具有** 网格的布局工具</span><span class="sxs-lookup"><span data-stu-id="74dd4-158">**Layout** tool with grids</span></span>  
:::image-end:::  

## <a name="customize-keyboard-shortcuts-in-settings"></a><span data-ttu-id="74dd4-159">在"设置"中自定义键盘快捷方式</span><span class="sxs-lookup"><span data-stu-id="74dd4-159">Customize keyboard shortcuts in Settings</span></span>  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="实验性功能":::
   <span data-ttu-id="74dd4-161">实验性功能</span><span class="sxs-lookup"><span data-stu-id="74dd4-161">Experimental feature</span></span>  
:::image-end:::  

<span data-ttu-id="74dd4-162">现在，你可以为 DevTools 中任何操作自定义键盘快捷方式。</span><span class="sxs-lookup"><span data-stu-id="74dd4-162">You are now able to customize the keyboard shortcut for any action in the DevTools.</span></span>  <span data-ttu-id="74dd4-163">自 Microsoft Edge 版本 84 起，你可以选择使用 Visual Studio **Code** 和 DevTools  (键盘快捷方式) [预设][DevtoolsCustomizeShortcuts]。</span><span class="sxs-lookup"><span data-stu-id="74dd4-163">Since Microsoft Edge version 84, you are able to choose between **Visual Studio Code** and **DevTools (default)** presets for [keyboard shortcuts][DevtoolsCustomizeShortcuts].</span></span>  <span data-ttu-id="74dd4-164">从 Microsoft Edge 版本 87 开始，你可以打开启用 **键盘快捷方式编辑器** 实验以进一 [步自定义键盘快捷方式][DevtoolsExperimentalFeaturesEnableKeyboardShortcutEditor]。</span><span class="sxs-lookup"><span data-stu-id="74dd4-164">Starting in Microsoft Edge version 87, you may turn on the **Enable keyboard shortcut editor** experiment to further [customize keyboard shortcuts][DevtoolsExperimentalFeaturesEnableKeyboardShortcutEditor].</span></span>  

<span data-ttu-id="74dd4-165">若要启用实验，请导航到打开 [实验][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures] 功能，然后选择启用键盘快捷方式编辑器旁边的 **复选框**。</span><span class="sxs-lookup"><span data-stu-id="74dd4-165">To enable the experiment, navigate to [Turn on Experimental features][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures] and choose the checkbox next to **Enable keyboard shortcut editor**.</span></span>  <span data-ttu-id="74dd4-166">有关自定义和编辑快捷方式详细信息，请导航至 [启用键盘快捷方式编辑器实验功能][DevtoolsExperimentalFeaturesEnableKeyboardShortcutEditor]。</span><span class="sxs-lookup"><span data-stu-id="74dd4-166">For more information about customizing and editing shortcuts, navigate to [Enable keyboard shortcut editor Experimental feature][DevtoolsExperimentalFeaturesEnableKeyboardShortcutEditor].</span></span>  <span data-ttu-id="74dd4-167">若要在 Chromium 开源项目中查看此功能实时更新，请导航到"问题[#174309"。][CR174309]</span><span class="sxs-lookup"><span data-stu-id="74dd4-167">To review real-time updates on this feature in the Chromium open-source project, navigate to Issue [#174309][CR174309].</span></span>  

:::image type="complex" source="../../media/2020/10/custom-shortcut-pause-script.msft.png" alt-text="用于暂停脚本的自定义快捷方式" lightbox="../../media/2020/10/custom-shortcut-pause-script.msft.png":::
   <span data-ttu-id="74dd4-169">用于暂停脚本的自定义快捷方式</span><span class="sxs-lookup"><span data-stu-id="74dd4-169">Custom shortcut for pausing a script</span></span>  
:::image-end:::  

## <a name="introducing-the-microsoft-edge-tools-for-visual-studio-code-extension"></a><span data-ttu-id="74dd4-170">Microsoft Edge Tools for Visual Studio Code 扩展</span><span class="sxs-lookup"><span data-stu-id="74dd4-170">Introducing the Microsoft Edge Tools for Visual Studio Code extension</span></span>  

<span data-ttu-id="74dd4-171">Code **Visual Studio Network** **for Visual Studio Code** 扩展的元素现在合并到新的 Microsoft Edge 开发人员工具中 [，Visual Studio代码][VisualStudioCodeMarketplaceMsEdgedevtools] 扩展。</span><span class="sxs-lookup"><span data-stu-id="74dd4-171">The **Elements for Visual Studio Code** and **Network for Visual Studio Code** extensions are now merged into the new [Microsoft Edge Developer Tools for Visual Studio Code][VisualStudioCodeMarketplaceMsEdgedevtools] extension.</span></span>  <span data-ttu-id="74dd4-172">将 Microsoft Edge DevTools 用于以下活动，而无需离开 Microsoft Visual Studio Code。</span><span class="sxs-lookup"><span data-stu-id="74dd4-172">Use the Microsoft Edge DevTools for the following activities without leaving Microsoft Visual Studio Code.</span></span>  

*   <span data-ttu-id="74dd4-173">调试 DOM</span><span class="sxs-lookup"><span data-stu-id="74dd4-173">Debug the DOM</span></span>  
*   <span data-ttu-id="74dd4-174">编辑 CSS</span><span class="sxs-lookup"><span data-stu-id="74dd4-174">Edit CSS</span></span>  
*   <span data-ttu-id="74dd4-175">检查网络流量</span><span class="sxs-lookup"><span data-stu-id="74dd4-175">Inspect network traffic</span></span>  

<span data-ttu-id="74dd4-176">借助扩展，启动 Microsoft Edge，连接到浏览器的现有实例，或者直接从编辑器使用无头浏览器。</span><span class="sxs-lookup"><span data-stu-id="74dd4-176">With the extension, launch Microsoft Edge, connect to an existing instance of the browser, or use a headless browser directly from your editor.</span></span>  <span data-ttu-id="74dd4-177">若要开始提供和归档有关此扩展的反馈问题，请导航到 GitHub 上的 Microsoft Edge 开发人员工具 [Visual Studio代码][GithubMicrosoftVscodeEdgeDevtools] 存储库。</span><span class="sxs-lookup"><span data-stu-id="74dd4-177">To start contributing and filing issues with your feedback about this extension, navigate to the [Microsoft Edge Developer Tools for Visual Studio Code][GithubMicrosoftVscodeEdgeDevtools] repo on GitHub.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/microsoft-edge-tools-full-browser.msft.png" alt-text="在完整浏览器模式下使用扩展的屏幕截图" lightbox="../../media/2020/10/microsoft-edge-tools-full-browser.msft.png":::
         <span data-ttu-id="74dd4-179">在完整浏览器模式下使用扩展的屏幕截图</span><span class="sxs-lookup"><span data-stu-id="74dd4-179">Using the extension in full browser mode screenshot</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/microsoft-edge-tools-headless.msft.png" alt-text="在无头模式下使用扩展屏幕截图" lightbox="../../media/2020/10/microsoft-edge-tools-headless.msft.png":::
         <span data-ttu-id="74dd4-181">在无头模式下使用扩展屏幕截图</span><span class="sxs-lookup"><span data-stu-id="74dd4-181">Using the extension in headless mode screenshot</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="announcements-from-the-chromium-project"></a><span data-ttu-id="74dd4-182">来自 Chromium 项目的公告</span><span class="sxs-lookup"><span data-stu-id="74dd4-182">Announcements from the Chromium project</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/chromium-whats-new-note.md)]  

### <a name="new-webauthn-tool"></a><span data-ttu-id="74dd4-183">新 WebAuthn 工具</span><span class="sxs-lookup"><span data-stu-id="74dd4-183">New WebAuthn tool</span></span>  

<span data-ttu-id="74dd4-184">在早期版本的 Microsoft Edge 中，没有本机 WebAuthn 调试支持。</span><span class="sxs-lookup"><span data-stu-id="74dd4-184">In earlier versions of Microsoft Edge, there was no native WebAuthn debugging support.</span></span>  <span data-ttu-id="74dd4-185">您需要物理验证器来使用 Web 身份验证 API 测试 [Web 应用程序][GithubW3cWebauthn]。</span><span class="sxs-lookup"><span data-stu-id="74dd4-185">You needed physical authenticators to test your web application with the [Web Authentication API][GithubW3cWebauthn].</span></span>  <span data-ttu-id="74dd4-186">使用新的 **WebAuthn** 工具，无需使用任何物理验证器即可执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="74dd4-186">With the new **WebAuthn** tool, you are able to do the following actions without the use of any physical authenticators.</span></span>

*   <span data-ttu-id="74dd4-187">模拟验证器</span><span class="sxs-lookup"><span data-stu-id="74dd4-187">Emulate authenticators</span></span>
*   <span data-ttu-id="74dd4-188">自定义验证器的属性</span><span class="sxs-lookup"><span data-stu-id="74dd4-188">Customize attributes of authenticators</span></span>
*   <span data-ttu-id="74dd4-189">检查验证器状态</span><span class="sxs-lookup"><span data-stu-id="74dd4-189">Inspect states of authenticators</span></span>
    
<span data-ttu-id="74dd4-190">有关**WebAuthn**功能详细信息，请导航到"模拟验证器"，并在[Microsoft Edge DevTools 中调试 WebAuthn。][DevtoolsWebauthnIndex]</span><span class="sxs-lookup"><span data-stu-id="74dd4-190">For more information about the **WebAuthn** feature, navigate to [Emulate authenticators and debug WebAuthn in Microsoft Edge DevTools][DevtoolsWebauthnIndex].</span></span>  

<span data-ttu-id="74dd4-191">您可以使用新的[WebAuthn][DevtoolsWebauthnIndex]工具模拟验证器[][GithubW3cWebauthn]并调试 Web 身份验证 API。</span><span class="sxs-lookup"><span data-stu-id="74dd4-191">You are able to emulate authenticators and debug the [Web Authentication API][GithubW3cWebauthn] with the new [WebAuthn][DevtoolsWebauthnIndex] tool.</span></span>  <span data-ttu-id="74dd4-192">若要打开**WebAuthn**工具，请选择自定义和控制**DevTools** \(`...` \) 图标>**更多工具**  >  **WebAuthn。**</span><span class="sxs-lookup"><span data-stu-id="74dd4-192">To open the **WebAuthn** tool, choose **the Customize and control DevTools** \(`...`\) icon > **More tools** > **WebAuthn**.</span></span>  <span data-ttu-id="74dd4-193">若要在 Chromium 开源项目中查看此功能实时更新，请导航到"问题[#1034663"。][CR1034663]</span><span class="sxs-lookup"><span data-stu-id="74dd4-193">To review real-time updates on this feature in the Chromium open-source project, navigate to Issue [#1034663][CR1034663].</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/more-tools-webauthn.msft.png" alt-text="打开 WebAuthn 工具" lightbox="../../media/2020/10/more-tools-webauthn.msft.png":::
         <span data-ttu-id="74dd4-195">打开 **WebAuthn** 工具</span><span class="sxs-lookup"><span data-stu-id="74dd4-195">Open the **WebAuthn** tool</span></span>  
      :::image-end:::  
   :::column-end:::  
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/webauthn-enable-virtual-auth.msft.png" alt-text="WebAuthn 工具" lightbox="../../media/2020/10/webauthn-enable-virtual-auth.msft.png":::
         <span data-ttu-id="74dd4-197">**WebAuthn** 工具</span><span class="sxs-lookup"><span data-stu-id="74dd4-197">**WebAuthn** tool</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

### <a name="elements-tool-updates"></a><span data-ttu-id="74dd4-198">元素工具更新</span><span class="sxs-lookup"><span data-stu-id="74dd4-198">Elements tool updates</span></span>  

#### <a name="view-the-computed-sidebar-pane-in-the-styles-pane"></a><span data-ttu-id="74dd4-199">查看"样式"窗格中的"计算边栏"窗格</span><span class="sxs-lookup"><span data-stu-id="74dd4-199">View the Computed sidebar pane in the Styles pane</span></span>  

<span data-ttu-id="74dd4-200">切换 **"样式"** 窗格中的"计算 **"** 窗格。</span><span class="sxs-lookup"><span data-stu-id="74dd4-200">Toggle the **Computed** pane in the **Styles** pane.</span></span>  <span data-ttu-id="74dd4-201">默认情况下 **，"样式"窗格中**的计算窗格是折叠的。</span><span class="sxs-lookup"><span data-stu-id="74dd4-201">The **Computed** pane in the **Styles** pane is collapsed by default.</span></span>  <span data-ttu-id="74dd4-202">若要切换它，请选择该按钮。</span><span class="sxs-lookup"><span data-stu-id="74dd4-202">To toggle it, choose the button.</span></span>  <span data-ttu-id="74dd4-203">若要在 Chromium 开源项目中查看此功能实时更新，请导航到"问题[#1073899"。][CR1073899]</span><span class="sxs-lookup"><span data-stu-id="74dd4-203">To review real-time updates on this feature in the Chromium open-source project, navigate to Issue [#1073899][CR1073899].</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/computed-sidebar-pane.msft.png" alt-text="打开计算边栏窗格" lightbox="../../media/2020/10/computed-sidebar-pane.msft.png":::
         <span data-ttu-id="74dd4-205">打开 **"计算边栏"** 窗格</span><span class="sxs-lookup"><span data-stu-id="74dd4-205">Open the **Computed sidebar** pane</span></span>  
      :::image-end:::  
   :::column-end:::  
   :::column span="":::
      :::image type="complex" source="../../media/2020/10/computed-sidebar-pane-open.msft.png" alt-text="计算边栏窗格" lightbox="../../media/2020/10/computed-sidebar-pane-open.msft.png":::
         <span data-ttu-id="74dd4-207">**计算边栏** 窗格</span><span class="sxs-lookup"><span data-stu-id="74dd4-207">**Computed sidebar** pane</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

#### <a name="grouping-css-properties-in-the-computed-panel"></a><span data-ttu-id="74dd4-208">在计算面板中对 CSS 属性进行分组</span><span class="sxs-lookup"><span data-stu-id="74dd4-208">Grouping CSS properties in the Computed panel</span></span>  

<span data-ttu-id="74dd4-209">若要以更少的滚动量查看应用的 CSS，请按"计算"窗格中的类别对 CSS **属性进行** 分组。</span><span class="sxs-lookup"><span data-stu-id="74dd4-209">To view your applied CSS with less scrolling, group the CSS properties by categories in the **Computed** pane.</span></span>  <span data-ttu-id="74dd4-210">在检查 CSS 时，还可以有选择地专注于一组相关属性。</span><span class="sxs-lookup"><span data-stu-id="74dd4-210">You may also selectively focus on a set of related properties while you inspect your CSS.</span></span>  <span data-ttu-id="74dd4-211">从" **元素"** 工具中，选择一个元素。</span><span class="sxs-lookup"><span data-stu-id="74dd4-211">From the **Elements** tool, choose an element.</span></span>  <span data-ttu-id="74dd4-212">若要将 \(或取消组合\) CSS 属性，请切换 **"组"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="74dd4-212">To group \(or ungroup\) the CSS properties, toggle the **Group** checkbox.</span></span>  <span data-ttu-id="74dd4-213">若要在 Chromium 开源项目中查看此功能实时更新，请导航到"问题[#1096230、#1084673][CR1096230]和[#1106251][CR1106251] [][CR1084673]。</span><span class="sxs-lookup"><span data-stu-id="74dd4-213">To review real-time updates on this feature in the Chromium open-source project, navigate to Issues [#1096230][CR1096230], [#1084673][CR1084673], and [#1106251][CR1106251].</span></span>  

:::image type="complex" source="../../media/2020/10/grouping-css-prop.msft.png" alt-text="对 CSS 属性进行分组" lightbox="../../media/2020/10/grouping-css-prop.msft.png":::
   <span data-ttu-id="74dd4-215">对 CSS 属性进行分组</span><span class="sxs-lookup"><span data-stu-id="74dd4-215">Grouping CSS properties</span></span>  
:::image-end:::  

### <a name="lighthouse-64-in-the-lighthouse-tool"></a><span data-ttu-id="74dd4-216">Lighthouse 工具中的 Lighthouse 6.4</span><span class="sxs-lookup"><span data-stu-id="74dd4-216">Lighthouse 6.4 in the Lighthouse tool</span></span>  

<span data-ttu-id="74dd4-217">**Lighthouse**工具现在运行 Lighthouse 6.4。</span><span class="sxs-lookup"><span data-stu-id="74dd4-217">The **Lighthouse** tool is now running Lighthouse 6.4.</span></span>  <span data-ttu-id="74dd4-218">有关更改的完整列表，请导航到 ["Lighthouse"发行说明][GithubGoogleChromeLighthouseReleasesV641]。</span><span class="sxs-lookup"><span data-stu-id="74dd4-218">For a full list of changes, navigate to the [Lighthouse release notes][GithubGoogleChromeLighthouseReleasesV641].</span></span>  <span data-ttu-id="74dd4-219">若要在 Chromium 开源项目中查看此功能实时更新，请导航到"问题 [#772558"][CR772558]。</span><span class="sxs-lookup"><span data-stu-id="74dd4-219">To review real-time updates on this feature in the Chromium open-source project, navigate to Issue [#772558][CR772558].</span></span>  

### <a name="performancemark-events-in-the-timings-section"></a><span data-ttu-id="74dd4-220">performance.mark () "计时"部分中的事件</span><span class="sxs-lookup"><span data-stu-id="74dd4-220">performance.mark() events in the Timings section</span></span>  

<span data-ttu-id="74dd4-221">" **性能"** 工具中记录的"计时" [部分现在][DevtoolsGuideChromiumEvaluatePerformanceReference] 标记 `performance.mark()` 事件。</span><span class="sxs-lookup"><span data-stu-id="74dd4-221">The **Timings section** of a recording in the [Performance][DevtoolsGuideChromiumEvaluatePerformanceReference] tool now marks `performance.mark()` events.</span></span>  <span data-ttu-id="74dd4-222">若要试用此功能并度量 JavaScript 代码的性能，请 `performance.mark()` 向代码添加事件。</span><span class="sxs-lookup"><span data-stu-id="74dd4-222">To try this feature and measure the performance of your JavaScript code, add `performance.mark()` events to your code.</span></span>  <span data-ttu-id="74dd4-223">例如，以下代码段在循环之前和之后添加标记，该循环使用增量 7 从 0 循环到 `for` 1000。</span><span class="sxs-lookup"><span data-stu-id="74dd4-223">For example, the following code snippet adds markers before and after a `for` loop that iterates from 0 to 1000 using increments of 7.</span></span>  

```javascript
performance.mark('start');
for (var i = 0; i < 1000; i+=7;){
  console.log(i);
}
performance.mark('end');
```  

<span data-ttu-id="74dd4-224">然后，打开 ["性能"][DevtoolsGuideChromiumEvaluatePerformanceReference] 工具并导航到" **计时"部分** 以录制 JavaScript 代码。</span><span class="sxs-lookup"><span data-stu-id="74dd4-224">Then, open the [Performance][DevtoolsGuideChromiumEvaluatePerformanceReference] tool and navigate to the **Timings section** to record your JavaScript code.</span></span>  <span data-ttu-id="74dd4-225">`performance.mark()`您添加的事件现在将显示在录制中。</span><span class="sxs-lookup"><span data-stu-id="74dd4-225">The `performance.mark()` events you added are now displayed in the recording.</span></span>  

:::image type="complex" source="../../media/2020/10/perf-mark.msft.png" alt-text="Performance.mark 事件" lightbox="../../media/2020/10/perf-mark.msft.png":::
   `performance.mark` <span data-ttu-id="74dd4-227">事件</span><span class="sxs-lookup"><span data-stu-id="74dd4-227">events</span></span>  
:::image-end:::  

### <a name="new-resource-type-and-url-filters-in-the-network-tool"></a><span data-ttu-id="74dd4-228">网络工具中的新资源类型和 URL 筛选器</span><span class="sxs-lookup"><span data-stu-id="74dd4-228">New resource-type and url filters in the Network tool</span></span>  

<span data-ttu-id="74dd4-229">使用 Network `resource-type` `url` 工具中的 new 和 **关键字** 筛选网络请求。</span><span class="sxs-lookup"><span data-stu-id="74dd4-229">Use the new `resource-type` and `url` keywords in the **Network** tool to filter network requests.</span></span>  <span data-ttu-id="74dd4-230">例如，使用 `resource-type:image` 将焦点放在作为图像的网络请求上。</span><span class="sxs-lookup"><span data-stu-id="74dd4-230">For example, use `resource-type:image` to focus on the network requests that are images.</span></span>  

:::image type="complex" source="../../media/2020/10/network-resource-type-filter.msft.png" alt-text="资源类型筛选器" lightbox="../../media/2020/10/network-resource-type-filter.msft.png":::
   <span data-ttu-id="74dd4-232">资源类型筛选器</span><span class="sxs-lookup"><span data-stu-id="74dd4-232">resource-type filter</span></span>  
:::image-end:::  

<span data-ttu-id="74dd4-233">若要发现更多特殊关键字（如 和 `resource-type` `url` ），请导航到 [按属性 筛选请求][DevtoolsNetworkReferenceFilterRequestsProperties]。</span><span class="sxs-lookup"><span data-stu-id="74dd4-233">To discover more special keywords such as `resource-type` and `url`, navigate to [filter requests by properties][DevtoolsNetworkReferenceFilterRequestsProperties].</span></span>  <span data-ttu-id="74dd4-234">若要在 Chromium 开源项目中查看此功能实时更新，请导航到"问题[][CR1121141]"#1121141"#1104188"。 [][CR1104188]</span><span class="sxs-lookup"><span data-stu-id="74dd4-234">To review real-time updates on this feature in the Chromium open-source project, navigate to Issues [#1121141][CR1121141] and [#1104188][CR1104188].</span></span>  

### <a name="frame-details-view-updates"></a><span data-ttu-id="74dd4-235">框架详细信息视图更新</span><span class="sxs-lookup"><span data-stu-id="74dd4-235">Frame details view updates</span></span>  

#### <a name="display-coep-and-coop-reporting-to-endpoint"></a><span data-ttu-id="74dd4-236">向终结点显示 COEP 和 COOP 报告</span><span class="sxs-lookup"><span data-stu-id="74dd4-236">Display COEP and COOP reporting to endpoint</span></span>  

<span data-ttu-id="74dd4-237">查看"安全与隔离"部分下的跨源嵌入器策略 \(COEP\) 和跨源打开器策略 \(COOP\) `reporting to` **&** 终结点。</span><span class="sxs-lookup"><span data-stu-id="74dd4-237">View the Cross-Origin Embedder Policy \(COEP\) and Cross-Origin Opener Policy \(COOP\) `reporting to` endpoint under the **Security & Isolation** section.</span></span>  <span data-ttu-id="74dd4-238">报告 [API][MdnReportingApi] 定义一个新的 HTTP 标头，它为你提供了一种指定浏览器服务器终结点以 `Report-To` 发送警告和错误的方法。</span><span class="sxs-lookup"><span data-stu-id="74dd4-238">The [Reporting API][MdnReportingApi] defines `Report-To`, a new HTTP header, that gives you a way to specify the server endpoints for the browser to send warnings and errors.</span></span>  <span data-ttu-id="74dd4-239">若要在 Chromium 开源项目中查看此功能实时更新，请导航到"问题 [#1051466"][CR1051466]。</span><span class="sxs-lookup"><span data-stu-id="74dd4-239">To review real-time updates on this feature in the Chromium open-source project, navigate to Issue [#1051466][CR1051466].</span></span>  

:::image type="complex" source="../../media/2020/10/https_first_party_test_glitch_me_coop-1.msft.png" alt-text="报告到终结点" lightbox="../../media/2020/10/https_first_party_test_glitch_me_coop-1.msft.png":::
   <span data-ttu-id="74dd4-241">`reporting to`终结点</span><span class="sxs-lookup"><span data-stu-id="74dd4-241">The `reporting to` endpoint</span></span>  
:::image-end:::  

#### <a name="display-coep-and-coop-report-only-mode"></a><span data-ttu-id="74dd4-242">显示 COEP 和 COOP 仅报告模式</span><span class="sxs-lookup"><span data-stu-id="74dd4-242">Display COEP and COOP report-only mode</span></span>  

<span data-ttu-id="74dd4-243">DevTools 现在显示设置为模式的 COEP 和 `report-only` COOP `report-only` 的标签。</span><span class="sxs-lookup"><span data-stu-id="74dd4-243">DevTools now display the `report-only` label for COEP and COOP that are set to `report-only` mode.</span></span>  <span data-ttu-id="74dd4-244">若要在 Chromium 开源项目中查看此功能实时更新，请导航到"问题 [#1051466"][CR1051466]。</span><span class="sxs-lookup"><span data-stu-id="74dd4-244">To review real-time updates on this feature in the Chromium open-source project, navigate to Issue [#1051466][CR1051466].</span></span>  

:::image type="complex" source="../../media/2020/10/https_first_party_test_glitch_me_coop-2.msft.png" alt-text="仅报告模式标签" lightbox="../../media/2020/10/https_first_party_test_glitch_me_coop-2.msft.png":::
   <span data-ttu-id="74dd4-246">`report-only`模式标签</span><span class="sxs-lookup"><span data-stu-id="74dd4-246">The `report-only` mode label</span></span>  
:::image-end:::  

### <a name="view-and-fix-color-contrast-issues-in-the-css-overview-tool"></a><span data-ttu-id="74dd4-247">在 CSS 概述工具中查看和修复颜色对比度问题</span><span class="sxs-lookup"><span data-stu-id="74dd4-247">View and fix color contrast issues in the CSS Overview tool</span></span>  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="实验性功能":::
   <span data-ttu-id="74dd4-249">实验性功能</span><span class="sxs-lookup"><span data-stu-id="74dd4-249">Experimental feature</span></span>  
:::image-end:::  

<span data-ttu-id="74dd4-250">CSS **概述** 工具现在显示页面上具有颜色对比度问题的元素列表。</span><span class="sxs-lookup"><span data-stu-id="74dd4-250">The **CSS Overview** tool now displays a list of elements on your page that have color contrast issues.</span></span>  <span data-ttu-id="74dd4-251">下面的演示页面包含颜色对比度问题的示例。</span><span class="sxs-lookup"><span data-stu-id="74dd4-251">The following demo page has an example of a color contrast issue.</span></span>  

[<span data-ttu-id="74dd4-252">CSS 概述辅助颜色演示</span><span class="sxs-lookup"><span data-stu-id="74dd4-252">CSS Overview Accessible Colors Demo</span></span>][GlitchCssOverviewAccessibleColorsDemo]  

<span data-ttu-id="74dd4-253">若要启用此实验，在设置**实验**  >  **下**，选择**CSS 概述**复选框。</span><span class="sxs-lookup"><span data-stu-id="74dd4-253">To enable this experiment, under **Settings** > **Experiments**, choose the **CSS Overview** checkbox.</span></span>  <span data-ttu-id="74dd4-254">若要查看具有颜色对比度问题的元素的列表，在对比度问题上，选择文本。</span><span class="sxs-lookup"><span data-stu-id="74dd4-254">To view a list of elements that have a color contrast issue, on **Contrast issues**, choose **Text**.</span></span>  <span data-ttu-id="74dd4-255">若要在"元素"工具 **中打开** 元素，请选择列表中的元素。</span><span class="sxs-lookup"><span data-stu-id="74dd4-255">To open the element in the **Elements** tool, choose an element in the list.</span></span>  <span data-ttu-id="74dd4-256">为了帮助修复对比度问题，Microsoft Edge DevTools [自动提供颜色建议][DevtoolsWhatsnew200208DevtoolsAccessibleColorSuggestionStylesPane]。</span><span class="sxs-lookup"><span data-stu-id="74dd4-256">To help fix contrast issues, the Microsoft Edge DevTools [automatically provide color suggestions][DevtoolsWhatsnew200208DevtoolsAccessibleColorSuggestionStylesPane].</span></span>  <span data-ttu-id="74dd4-257">若要在 Chromium 开源项目中查看此功能实时更新，请导航到"问题[#1120316"。][CR1120316]</span><span class="sxs-lookup"><span data-stu-id="74dd4-257">To review real-time updates on this feature in the Chromium open-source project, navigate to Issue [#1120316][CR1120316].</span></span>  

:::image type="complex" source="../../media/2020/10/css-overview.msft.png" alt-text="低色对比度问题" lightbox="../../media/2020/10/css-overview.msft.png":::
   <span data-ttu-id="74dd4-259">低色对比度问题</span><span class="sxs-lookup"><span data-stu-id="74dd4-259">Low color contrast issues</span></span>  
:::image-end:::  

## <a name="download-the-microsoft-edge-preview-channels"></a><span data-ttu-id="74dd4-260">下载 Microsoft Edge 预览频道</span><span class="sxs-lookup"><span data-stu-id="74dd4-260">Download the Microsoft Edge preview channels</span></span>  

<span data-ttu-id="74dd4-261">如果你使用的是 Windows 或 macOS，请考虑使用 [ Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels] 作为默认开发浏览器。</span><span class="sxs-lookup"><span data-stu-id="74dd4-261">If you are on Windows or macOS, consider using the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] as your default development browser.</span></span>  <span data-ttu-id="74dd4-262">预览频道使你能够访问最新的 DevTools 功能。</span><span class="sxs-lookup"><span data-stu-id="74dd4-262">The preview channels give you access to the latest DevTools features.</span></span>  

## <a name="getting-in-touch-with-microsoft-edge-devtools-team"></a><span data-ttu-id="74dd4-263">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="74dd4-263">Getting in touch with Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- links -->  

[DevtoolsWhatsnew200205DevtoolsDeprecationPropertiesPaneElementsPanel]: ../05/devtools.md#deprecation-of-the-properties-pane-in-the-elements-tool ""元素"工具中的"属性"窗格弃用 - DevTools (Microsoft Edge 84 中的新增) |Microsoft Docs"  
[DevtoolsWhatsnew200206DevtoolsCssGridDebuggingFeatures]: ../06/devtools.md#css-grid-debugging-features "CSS 网格调试功能 - Microsoft Edge 85 (中的新增功能) |Microsoft Docs"  
[DevtoolsWhatsnew200208DevtoolsAccessibleColorSuggestionStylesPane]: ../08/devtools.md#accessible-color-suggestion-in-the-styles-pane ""样式"窗格中的可访问颜色建议 - Microsoft Edge 86 (中的新增功能) |Microsoft Docs"  

[DevtoolsDeviceModeIndex]: /microsoft-edge/devtools-guide-chromium/device-mode/index "在 Microsoft Edge DevTools 中模拟移动设备 | Microsoft Docs"  
[DevtoolsGuideChromiumConsoleUtilitiesRecentlySelectedElementJavascriptObject]:  https://docs.microsoft.com/microsoft-edge/devtools-guide-chromium/console/utilities#recently-selected-element-or-javascript-object "最近选择的元素或 JavaScript 对象 - 控制台实用程序 API |Microsoft Docs"  
[DevtoolsCustomizeShortcuts]: /microsoft-edge/devtools-guide-chromium/customize/shortcuts "自定义 Microsoft Edge DevTools 工具中的键盘|Microsoft Docs"  
[DevtoolsGuideChromiumEvaluatePerformanceReference]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference "性能分析参考|Microsoft Docs"  
[DevtoolsExperimentalFeaturesEmulationSupportDualScreenMode]: /microsoft-edge/devtools-guide-chromium/experimental-features#emulation-support-dual-screen-mode "模拟：支持双屏幕模式 - 实验|Microsoft Docs"  
[DevtoolsExperimentalFeaturesEnableExperimentalApis]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-experimental-apis "启用实验性 API - 实验|Microsoft Docs"  
[DevtoolsExperimentalFeaturesEnableKeyboardShortcutEditor]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-keyboard-shortcut-editor "启用键盘快捷方式编辑器 - 实验|Microsoft Docs"  
[DevtoolsExperimentalFeaturesEnableNewCssGridDebuggingFeatures]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-new-css-grid-debugging-features "模拟：支持双屏幕模式 - 实验|Microsoft Docs"  
[DevtoolsExperimentalFeaturesEnableNetworkConsole]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-network-console "启用网络控制台 - 实验功能|Microsoft Docs"  
[DevtoolsExperimentalFeaturesEnableSourceOrderViewer]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-source-order-viewer "启用源订单查看器 - 实验|Microsoft Docs"
[DevtoolsExperimentalFeaturesTestingOnFoldableDualScreenDevices]: /microsoft-edge/devtools-guide-chromium/experimental-features#testing-on-foldable-and-dual-screen-devices "在可折叠和双屏幕设备上进行测试 - 实验|Microsoft Docs"  
[DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures]: /microsoft-edge/devtools-guide-chromium/experimental-features#turn-on-experimental-features "打开实验性功能 - 实验|Microsoft Docs"  
[DevtoolsConsoleApiTable]: /microsoft-edge/devtools-guide-chromium/console/api#table "表 - 控制台 API 参考|Microsoft Docs"  
[DevtoolsCoverageIndex]: /microsoft-edge/devtools-guide-chromium/coverage/index "使用 Microsoft Edge DevTools | 中的"覆盖"选项卡查找未使用的 JavaScript 和 CSS |Microsoft Docs"  
[DevtoolsCssGrid]:  /microsoft-edge/devtools-guide-chromium/css/grid "检查 CSS 网格|Microsoft Docs"  
[DevtoolsCustomizeIndexDrawer]: /microsoft-edge/devtools-guide-chromium/customize/index#drawer "箱 - 自定义 Microsoft Edge DevTools |Microsoft Docs"  
[DevtoolsCustomizeIndexSettings]: /microsoft-edge/devtools-guide-chromium/customize/index#settings "设置 - 自定义 Microsoft Edge DevTools | Microsoft Docs"  
[DevtoolsEvaluatePerformanceReferenceAnalyzeRenderingPerformance]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference#analyze-rendering-performance-with-the-rendering-tab "使用"呈现"选项卡分析呈现性能 - 性能分析参考|Microsoft Docs"  
[DevtoolsMediaIndex]: /microsoft-edge/devtools-guide-chromium/media/index "查看和调试媒体播放器|Microsoft Docs"  
[DevtoolsNetworkReferenceFilterRequestsProperties]: /microsoft-edge/devtools-guide-chromium/network/reference#filter-requests-by-properties  "按属性筛选请求 - 网络分析参考|Microsoft Docs"  
[DevtoolsWebauthnIndex]: /microsoft-edge/devtools-guide-chromium/webauthn/index "模拟验证器，并调试 Microsoft Edge DevTools |Microsoft Docs"  

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download "Microsoft Edge 预览频道"  

[VisualStudioCode]: https://code.visualstudio.com "Visual Studio 代码"  

[VisualStudioCodeMarketplaceMsEdgedevtools]: https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools "Microsoft Edge 代码Visual Studio工具|Visual Studio 代码"  

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium 漏洞"  

[CR174309]: https://crbug.com/174309 "DevTools：允许自定义键盘快捷方式/键绑定|Chromium Bug"
[CR772558]: https://crbug.com/772558 "DevTools：更新到最新版本的 Lighthouse |Chromium Bug"  
[CR1034663]: https://crbug.com/1034663 "为 WebAuthn 测试 API 应用程序创建|Chromium Bug"  
[CR1047356]: https://crbug.com/1047356 "CSS Grid/Flexbox/Table 工具|Chromium Bug"  
[CR1051466]: https://crbug.com/1051466 "支持 DevTools | 中的 COOP/COEP 调试Chromium Bug"  
[CR1073899]: https://crbug.com/1073899 "计算样式选项卡在响应模式下消失|Chromium Bug"  
[CR1075732]: https://crbug.com/1075732 "DevTools 个性化 - "开发工具"选项卡|Chromium Bug"  
[CR1084673]: https://crbug.com/1084673 "DevTools：改进我们呈现 CSS 自定义属性 ( (，) 。CSS 变量) 及其值|Chromium Bug"  
[CR1093687]: https://crbug.com/1093687 "创建用于创建和重播综合网络请求|Chromium Bug"  
[CR1096230]: https://crbug.com/1096230 "在计算样式窗格中按类别分组 CSS |Chromium Bug"  
[CR1104188]: https://crbug.com/1104188 "在搜索完整 URL 搜索时，网络工具搜索找不到|Chromium Bug"  
[CR1106251]: https://crbug.com/1106251 "☂ DevTools：改进"计算样式"选项卡|Chromium Bug"  
[CR1120316]: https://crbug.com/1120316 "突出显示 CSS 概述和颜色>对比度|Chromium Bug"  
[CR1121141]: https://crbug.com/1121141 "允许在网络日志日志中按资源类型|Chromium Bug"  
[CR1121312]: https://crbug.com/1121312 "设置应从"更多工具"菜单中删除|Chromium Bug"  
[CR1136394]: https://crbug.com/1136394 "Flexbox 工具|Chromium Bug"  
[CR1136655]: https://crbug.com/1136655 "开发工具：本地化 V2 |Chromium Bug"  

[MdnReportingApi]: https://developer.mozilla.org/docs/Web/API/Reporting_API "报告 API |MDN"  

[GithubMicrosoftVscodeEdgeDevtools]: https://github.com/Microsoft/vscode-edge-devtools "microsoft/vscode-edge-devtools |GitHub"  

[GithubGoogleChromeLighthouseReleasesV641]: https://github.com/GoogleChrome/lighthouse/releases/v6.4.1 "v6.4.1 - GoogleChrome/lighthouse |GitHub"  

[GithubW3cWebauthn]: https://w3c.github.io/webauthn "Web 身份验证|GitHub"  

[GlitchCssOverviewAccessibleColorsDemo]: https://css-overview-accessible-colors-demo.glitch.me "你好！|小故障"  

[PostmanSchemaJsonCollectionv210Index]: https://schema.getpostman.com/json/collection/v2.1.0/docs/index.html "Postman 集合格式 v2.1.0 |Postman"  

[SwaggerSpecificationV2]: https://swagger.io/specification/v2 "OpenAPI 规范|Swagger"  

<!--[JecFyiDemoPerfMark]: https://jec.fyi/demo/perf-mark "" -->  

> [!NOTE]
> <span data-ttu-id="74dd4-316">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="74dd4-316">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="74dd4-317">原始页面位于 [此处](https://developers.google.com/web/updates/2020/10/devtools/index)，并由 [Jecelyn Yeen][JecelynYeen] \（开发人员支持者，Chrome DevTools\）制作。</span><span class="sxs-lookup"><span data-stu-id="74dd4-317">The original page is found [here](https://developers.google.com/web/updates/2020/10/devtools/index) and is authored by [Jecelyn Yeen][JecelynYeen] \(Developer advocate, Chrome DevTools\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="74dd4-319">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="74dd4-319">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen  
