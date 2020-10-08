---
description: 将键盘快捷方式与 Visual Studio 代码匹配、模拟 Surface 双核和 Samsung Galaxy 折页、CSS 网格覆盖改进等。
title: DevTools (Microsoft Edge 86) 中的新增功能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/08/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 943eca7e73385513b264feb74ec37c450d5c5a2f
ms.sourcegitcommit: 6b577cb118f34f3ff2c65eab2908b65f155dc151
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/09/2020
ms.locfileid: "11004100"
---
# <span data-ttu-id="81574-104">DevTools (Microsoft Edge 86) 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="81574-104">What's New In DevTools (Microsoft Edge 86)</span></span>  

## <span data-ttu-id="81574-105">来自 Microsoft Edge 开发人员工具团队公告</span><span class="sxs-lookup"><span data-stu-id="81574-105">Announcements from the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/edge-whats-new-note.md)]  

### <span data-ttu-id="81574-106">将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配</span><span class="sxs-lookup"><span data-stu-id="81574-106">Match keyboard shortcuts in DevTools to Visual Studio Code</span></span>  

<span data-ttu-id="81574-107">在 Microsoft Edge 86 中，你可以将 DevTools 中的键盘快捷方式与 [Visual Studio 代码][VisualStudioCode]中的快捷方式相匹配。</span><span class="sxs-lookup"><span data-stu-id="81574-107">In Microsoft Edge 86, you may match keyboard shortcuts in the DevTools to your shortcuts in [Visual Studio Code][VisualStudioCode].</span></span> 

:::image type="complex" source="../../media/2020/08/keyboard-shortcut.msft.png" alt-text="将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配" lightbox="../../media/2020/08/keyboard-shortcut.msft.png":::
   <span data-ttu-id="81574-109">将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配</span><span class="sxs-lookup"><span data-stu-id="81574-109">Match keyboard shortcuts in the DevTools to Visual Studio Code</span></span>  
:::image-end:::  

<span data-ttu-id="81574-110">若要激活此功能，请导航到 [Microsoft Edge DevTools 中的自定义键盘快捷方式][DevtoolsCustomizeShortcuts]。</span><span class="sxs-lookup"><span data-stu-id="81574-110">To activate this feature, navigate to [Customize keyboard shortcuts in the Microsoft Edge DevTools][DevtoolsCustomizeShortcuts].</span></span>  

<span data-ttu-id="81574-111">例如，在 [Visual Studio 代码][VisualStudioCodeShortcutsKeyboardWindows] 中暂停或继续运行脚本的键盘快捷方式是 `F5` 。</span><span class="sxs-lookup"><span data-stu-id="81574-111">For example, the keyboard shortcut for pausing or continuing running a script in [Visual Studio Code][VisualStudioCodeShortcutsKeyboardWindows] is `F5`.</span></span>  <span data-ttu-id="81574-112">通过 \*\*DevTools (默认) \*\* 预设，DevTools 中的同一快捷方式 `F8` ，但选择 **Visual Studio Code** 预置时，该快捷方式现在也是如此 `F5` 。</span><span class="sxs-lookup"><span data-stu-id="81574-112">With the **DevTools (Default)** preset, that same shortcut in the DevTools is `F8`, but when you choose the **Visual Studio Code** preset, that shortcut is now also `F5`.</span></span>  

<span data-ttu-id="81574-113">Chromium 问题 [#174309][CR174309]</span><span class="sxs-lookup"><span data-stu-id="81574-113">Chromium issue [#174309][CR174309]</span></span>  

### <span data-ttu-id="81574-114">模拟 Surface 双核和 Samsung Galaxy 折页</span><span class="sxs-lookup"><span data-stu-id="81574-114">Emulate Surface Duo and Samsung Galaxy Fold</span></span>  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配":::
   <span data-ttu-id="81574-116">实验性功能</span><span class="sxs-lookup"><span data-stu-id="81574-116">Experimental feature</span></span>  
:::image-end:::  

<span data-ttu-id="81574-117">现在，你可以在两个新设备上测试你的网站或应用的外观：在 Microsoft Edge 中，  [Surface 双核][MicrosoftSurfaceDevicesDuo] 和 [Samsung Galaxy 折页][SamsungMobileGalaxyFold] 。</span><span class="sxs-lookup"><span data-stu-id="81574-117">You are now able to test the look and feel of your website or app on two new devices:  [Surface Duo][MicrosoftSurfaceDevicesDuo] and [Samsung Galaxy Fold][SamsungMobileGalaxyFold] in Microsoft Edge.</span></span>  

<span data-ttu-id="81574-118">若要帮助增强适用于双屏幕和可折叠设备的网站或应用，请在 [模拟设备][DevtoolsDeviceModeIndex]时使用以下功能。</span><span class="sxs-lookup"><span data-stu-id="81574-118">To help enhance your website or app for the dual-screen and foldable devices, use the following features when [emulating the device][DevtoolsDeviceModeIndex].</span></span>  

*   <span data-ttu-id="81574-119">[跨越][DevtoolsExperimentalFeaturesTestingOnFoldableDualScreenDevices]，即当你的网站 (或应用 \ ) 出现在两个屏幕上时。</span><span class="sxs-lookup"><span data-stu-id="81574-119">[Spanning][DevtoolsExperimentalFeaturesTestingOnFoldableDualScreenDevices], which is when your website \(or app\) appears across both screens.</span></span>
*   <span data-ttu-id="81574-120">[渲染接缝][DualScreenIntroductionHowWorkSeam]，即两个屏幕之间的空间。</span><span class="sxs-lookup"><span data-stu-id="81574-120">[Rendering the seam][DualScreenIntroductionHowWorkSeam], which is the space between the two screens.</span></span>
*   <span data-ttu-id="81574-121">[启用实验性 Web 平台 api][DevtoolsExperimentalFeaturesEnableExperimentalApis] 以访问新的 [CSS 媒体屏幕生成功能][DualScreenWebCssMediaSpanning] 和 [JavaScript getWindowSegments API][DualScreenWebJavascriptGetwindowsegments]。</span><span class="sxs-lookup"><span data-stu-id="81574-121">[Enabling experimental Web Platform APIs][DevtoolsExperimentalFeaturesEnableExperimentalApis] to access the new [CSS media screen-spanning feature][DualScreenWebCssMediaSpanning] and [JavaScript getWindowSegments API][DualScreenWebJavascriptGetwindowsegments].</span></span>  

:::image type="complex" source="../../media/2020/08/surface-duo-device-emulation.msft.png" alt-text="将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配" lightbox="../../media/2020/08/surface-duo-device-emulation.msft.png":::
   <span data-ttu-id="81574-123">Surface 双核设备仿真</span><span class="sxs-lookup"><span data-stu-id="81574-123">Device emulation for Surface Duo</span></span>  
:::image-end:::  

<span data-ttu-id="81574-124">若要启用此实验功能，请导航到 ["启用实验功能][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures] "，然后选择 " **模拟：支持双重屏幕模式**" 旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="81574-124">To turn on this experimental feature, navigate to [Turn on experimental features][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures] and choose the checkbox next to **Emulation: Support dual screen mode**.</span></span>  

<span data-ttu-id="81574-125">有关此实验的详细信息，请导航到 " [模拟：支持双重屏幕模式][DevtoolsExperimentalFeaturesEmulationSupportDualScreenMode]"。</span><span class="sxs-lookup"><span data-stu-id="81574-125">For more information about this experiment, navigate to [Emulation: Support dual screen mode][DevtoolsExperimentalFeaturesEmulationSupportDualScreenMode].</span></span>  

<span data-ttu-id="81574-126">Chromium 问题： [#1054281][CR1054281]</span><span class="sxs-lookup"><span data-stu-id="81574-126">Chromium issue: [#1054281][CR1054281]</span></span>  

### <span data-ttu-id="81574-127">CSS 网格覆盖改进和新的实验性网格功能</span><span class="sxs-lookup"><span data-stu-id="81574-127">CSS grid overlay improvements and new experimental grid features</span></span>  

<span data-ttu-id="81574-128">感谢您对改进的 CSS 网格覆盖的积极反馈。</span><span class="sxs-lookup"><span data-stu-id="81574-128">Thank you for the positive feedback about the improved CSS grid overlays.</span></span>  <span data-ttu-id="81574-129">现在，CSS 网格覆盖在默认情况下处于启用状态，不需要你启用实验。</span><span class="sxs-lookup"><span data-stu-id="81574-129">The CSS grid overlays are now enabled by default and do not require you to turn on an experiment.</span></span>  

:::image type="complex" source="../../media/2020/08/css-grid-overlay-article.msft.png" alt-text="将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配" lightbox="../../media/2020/08/css-grid-overlay-article.msft.png":::
   <span data-ttu-id="81574-131">元素的 CSS 网格覆盖 `article`</span><span class="sxs-lookup"><span data-stu-id="81574-131">CSS grid overlay for `article` element</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="81574-132">有关网格覆盖的详细信息，请转到 [CSS 网格调试功能][DevtoolsWhatsnew200206DevtoolsCssGridDebuggingFeatures]。</span><span class="sxs-lookup"><span data-stu-id="81574-132">For more information about grid overlays, go to [CSS grid debugging features][DevtoolsWhatsnew200206DevtoolsCssGridDebuggingFeatures].</span></span>  

<span data-ttu-id="81574-133">Microsoft Edge DevTools 团队和 Chrome DevTools 团队协作处理其他功能。</span><span class="sxs-lookup"><span data-stu-id="81574-133">The Microsoft Edge DevTools team and the Chrome DevTools team collaborate on additional features.</span></span>  <span data-ttu-id="81574-134">新功能包括在 "**元素**" 面板上的新**布局**窗格中具有持久性和可配置的多个覆盖。</span><span class="sxs-lookup"><span data-stu-id="81574-134">The new features include multiple overlays that are persistent and configurable from a new **Layout** pane on the **Elements** panel.</span></span>  

<span data-ttu-id="81574-135">若要启用此实验功能，请导航到 ["启用实验功能][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures] "，然后选中 " \*\*启用新 CSS 网格调试功能" 旁边的复选框 (在重新启动) 后，元素的 "布局" 侧栏窗格中可用的配置选项 \*\*。</span><span class="sxs-lookup"><span data-stu-id="81574-135">To turn on this experimental feature, navigate to [Turn on experimental features][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures] and choose the checkbox next to **Enable new CSS Grid debugging features (configuration options available in Layout sidebar pane in Elements after restart)**.</span></span>  

<span data-ttu-id="81574-136">有关此实验的详细信息，请导航以 [启用新的 CSS 网格调试功能][DevtoolsExperimentalFeaturesEnableNewCssGridDebuggingFeatures]。</span><span class="sxs-lookup"><span data-stu-id="81574-136">For more information about this experiment, navigate to [Enable new CSS grid debugging features][DevtoolsExperimentalFeaturesEnableNewCssGridDebuggingFeatures].</span></span>  

<span data-ttu-id="81574-137">Chromium 问题： [#1047356][CR1047356]</span><span class="sxs-lookup"><span data-stu-id="81574-137">Chromium issue: [#1047356][CR1047356]</span></span>  

### <span data-ttu-id="81574-138">从控制台复制的表保留格式</span><span class="sxs-lookup"><span data-stu-id="81574-138">Table copied from the Console preserves formatting</span></span>  

<span data-ttu-id="81574-139">在 Microsoft Edge 85 或更早版本中，已复制的格式 `console.table` 丢失。</span><span class="sxs-lookup"><span data-stu-id="81574-139">In Microsoft Edge 85 or earlier, the formatting of a copied `console.table` was lost.</span></span>  <span data-ttu-id="81574-140">如果从 [表][DevtoolsConsoleApiTable] 控制台 API 复制了输出并粘贴了该输出，则仅保留表的文本。</span><span class="sxs-lookup"><span data-stu-id="81574-140">If you copied the output from the [table][DevtoolsConsoleApiTable] Console API, and pasted it, only the text of the table was kept.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/console-table-beta.msft.png" alt-text="将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配" lightbox="../../media/2020/08/console-table-beta.msft.png":::
         `table` <span data-ttu-id="81574-142">Microsoft Edge 85 或更早版本中的控制台 API 输出</span><span class="sxs-lookup"><span data-stu-id="81574-142">Console API output in Microsoft Edge 85 or earlier</span></span>  
      :::image-end:::  
   :::column-end:::  
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/console-table-beta-paste-visual-studio-code.msft.png" alt-text="将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配" lightbox="../../media/2020/08/console-table-beta-paste-visual-studio-code.msft.png":::
         `table` <span data-ttu-id="81574-144">从 Microsoft Edge 85 或更早版本粘贴到 Visual Studio 代码的控制台 API 输出</span><span class="sxs-lookup"><span data-stu-id="81574-144">Console API output from Microsoft Edge 85 or earlier pasted into Visual Studio Code</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="81574-145">在 Microsoft Edge 86 或更高版本中，从 **控制台**复制表格时，格式现在将保留。</span><span class="sxs-lookup"><span data-stu-id="81574-145">In Microsoft Edge 86 or later, when you copy a table from the **Console**, the formatting is now preserved.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/console-table-canary.msft.png" alt-text="将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配" lightbox="../../media/2020/08/console-table-canary.msft.png":::
         `table` <span data-ttu-id="81574-147">Microsoft Edge 86 或更高版本中的控制台 API 输出</span><span class="sxs-lookup"><span data-stu-id="81574-147">Console API output in Microsoft Edge 86 or later</span></span>  
      :::image-end:::  
   :::column-end:::  
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/console-table-canary-paste-visual-studio-code.msft.png" alt-text="将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配" lightbox="../../media/2020/08/console-table-canary-paste-visual-studio-code.msft.png":::
         `table` <span data-ttu-id="81574-149">Microsoft Edge 86 或更高版本中粘贴到 Visual Studio 代码中的控制台 API 输出</span><span class="sxs-lookup"><span data-stu-id="81574-149">Console API output from Microsoft Edge 86 or later pasted into Visual Studio Code</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="81574-150">Chromium 问题： [#1115011] [CR1115011]</span><span class="sxs-lookup"><span data-stu-id="81574-150">Chromium issue: [#1115011][CR1115011]</span></span>  

### <span data-ttu-id="81574-151">源顺序查看器，便于进行辅助功能测试</span><span class="sxs-lookup"><span data-stu-id="81574-151">Source Order Viewer for easier accessibility testing</span></span>  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配":::
   <span data-ttu-id="81574-153">实验性功能</span><span class="sxs-lookup"><span data-stu-id="81574-153">Experimental feature</span></span>  
:::image-end:::  

<span data-ttu-id="81574-154">新的辅助功能帮助程序显示源中元素的顺序。</span><span class="sxs-lookup"><span data-stu-id="81574-154">The new accessibility helper displays the order of elements in the source.</span></span>  

:::image type="complex" source="../../media/2020/08/source-order-viewer.msft.png" alt-text="将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配" lightbox="../../media/2020/08/source-order-viewer.msft.png":::
   <span data-ttu-id="81574-156">激活 "**显示源订单**"</span><span class="sxs-lookup"><span data-stu-id="81574-156">Activate **Show source order**</span></span>  
:::image-end:::  

<span data-ttu-id="81574-157">此功能可让你更轻松地测试屏幕阅读器和键盘用户体验你的网站或应用的方式。</span><span class="sxs-lookup"><span data-stu-id="81574-157">This feature makes it easier to test the way screen reader and keyboard users experience your website or app.</span></span>  <span data-ttu-id="81574-158">屏幕阅读器和键盘导航依赖于在网站或应用的源代码中按特定顺序放置的内容，以便与呈现的页面匹配。</span><span class="sxs-lookup"><span data-stu-id="81574-158">Screen readers and keyboard navigation depend on content being placed in a particular order in the source code of your website or app, so that it matches the rendered page.</span></span>  <span data-ttu-id="81574-159">源顺序查看器在呈现的页面和源代码之间按顺序显示潜在差异。</span><span class="sxs-lookup"><span data-stu-id="81574-159">The Source Order Viewer displays potential differences in order between the rendered page and the source code.</span></span>  

<span data-ttu-id="81574-160">若要启用此实验功能，请导航到 ["打开实验功能][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures] "，然后选中 " **启用源订单查看器**" 旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="81574-160">To turn on this experimental feature, navigate to [Turn on experimental features][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures] and choose the checkbox next to **Enable Source Order Viewer**.</span></span>  

<span data-ttu-id="81574-161">有关此实验的详细信息，请导航到 [启用源订单查看器][DevtoolsExperimentalFeaturesEnableSourceOrderViewer]。</span><span class="sxs-lookup"><span data-stu-id="81574-161">For more information about this experiment, navigate to [Enable Source Order Viewer][DevtoolsExperimentalFeaturesEnableSourceOrderViewer].</span></span>  

<span data-ttu-id="81574-162">Chromium 问题： [#1094406][CR1094406]</span><span class="sxs-lookup"><span data-stu-id="81574-162">Chromium issue: [#1094406][CR1094406]</span></span>  

<!--
### DevTools language enhancements  

Your feedback and internal discoveries uncovered which text strings used in the Microsoft Edge feedback should remain untranslated or create confusion when translated.  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/localization-improvements-chinese-complex-stable.msft.png" alt-text="将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配" lightbox="localization-improvements-chinese-complex-stable.msft.png":::
         Microsoft Edge DevTools 85 and earlier in Traditional Chinese  
      :::image-end:::  
   :::column-end:::  
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/localization-improvements-chinese-complex-canary.msft.png" alt-text="将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配" lightbox="../../media/2020/08/localization-improvements-chinese-complex-canary.msft.png":::
         Microsoft Edge DevTools 86  or later in Traditional Chinese  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

To meet your translation needs, the Microsoft Edge DevTools team is focused on improving translation quality.  

The current effort to improve translation quality enables easier support for more languages in the future.  
-->  

### <span data-ttu-id="81574-163">突出显示 "元素" 工具中的所有搜索结果</span><span class="sxs-lookup"><span data-stu-id="81574-163">Highlight all search results in Elements tool</span></span>  

<span data-ttu-id="81574-164">在 Microsoft Edge 84 和85中，" **元素** " 面板中的第一个搜索结果不突出显示。</span><span class="sxs-lookup"><span data-stu-id="81574-164">In Microsoft Edge 84 and 85, the first search result in the **Elements** panel did not highlight.</span></span>  <span data-ttu-id="81574-165">剩余的搜索结果已正确突出显示。</span><span class="sxs-lookup"><span data-stu-id="81574-165">The remaining search results were highlighted correctly.</span></span>  

<span data-ttu-id="81574-166">感谢您发送反馈并帮助改进 Chromium。</span><span class="sxs-lookup"><span data-stu-id="81574-166">Thank you for sending your feedback and helping improve Chromium.</span></span>  <span data-ttu-id="81574-167">你的反馈发现问题 [#1103316][CR1103316] 在开放源代码 Chromium 项目中。</span><span class="sxs-lookup"><span data-stu-id="81574-167">Your feedback uncovered Issue [#1103316][CR1103316] in the open-source Chromium project.</span></span>  

:::image type="complex" source="../../media/2020/08/elements- search-highlight-fixed.msft.png" alt-text="将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配" lightbox="../../media/2020/08/elements- search-highlight-fixed.msft.png":::
   <span data-ttu-id="81574-169">在 Microsoft Edge 84 或更高版本中突出显示 " **元素** " 面板上的第一个搜索结果</span><span class="sxs-lookup"><span data-stu-id="81574-169">Highlighted first search result on **Elements** panel in Microsoft Edge 84 or later</span></span>  
:::image-end:::  

<span data-ttu-id="81574-170">此问题现已在所有版本的 Microsoft Edge 中修复。</span><span class="sxs-lookup"><span data-stu-id="81574-170">The issue is now fixed in all versions of Microsoft Edge.</span></span>  

<span data-ttu-id="81574-171">Chromium 问题： [#1103316][CR1103316]</span><span class="sxs-lookup"><span data-stu-id="81574-171">Chromium issue: [#1103316][CR1103316]</span></span>  

## <span data-ttu-id="81574-172">来自 Chromium 项目的公告</span><span class="sxs-lookup"><span data-stu-id="81574-172">Announcements from the Chromium project</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/chromium-whats-new-note.md)]  

### <span data-ttu-id="81574-173">新媒体面板</span><span class="sxs-lookup"><span data-stu-id="81574-173">New Media panel</span></span>  

<span data-ttu-id="81574-174">DevTools 现在在 " [媒体][DevtoolsMediaIndex] " 面板中显示媒体播放器信息。</span><span class="sxs-lookup"><span data-stu-id="81574-174">DevTools now displays media players information in the [Media][DevtoolsMediaIndex] panel.</span></span>  

<span data-ttu-id="81574-175">若要打开新的 " **媒体** " 面板，请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="81574-175">To open the new **Media** panel, complete the following step.</span></span>  

1.  <span data-ttu-id="81574-176">选择 "**自定义和控制 DevTools** \ (`...` \ ) " >**更多工具**  >  **媒体**。</span><span class="sxs-lookup"><span data-stu-id="81574-176">Choose **Customize and control DevTools** \(`...`\) > **More tools** > **Media**.</span></span>  
    
    :::image type="complex" source="../../media/2020/08/media-panel.msft.png" alt-text="将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配" lightbox="../../media/2020/08/media-panel.msft.png":::
       <span data-ttu-id="81574-178">新 **媒体** 面板</span><span class="sxs-lookup"><span data-stu-id="81574-178">New **Media** panel</span></span>  
    :::image-end:::  

<span data-ttu-id="81574-179">在 DevTools 中的新 **媒体** 面板之前，有关视频播放器的日志记录和调试信息位于 " **最近使用的播放机** " 设置下。</span><span class="sxs-lookup"><span data-stu-id="81574-179">Before the new **Media** panel in DevTools, the logging and debug information about video players was located under the **Recent Players** setting.</span></span>  <span data-ttu-id="81574-180">若要打开 " **最近使用的播放器** " 设置，请转到 `edge://media-internals` 并选择 " **玩家** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="81574-180">To open the **Recent Players** setting, go to `edge://media-internals` and choose the **Players** tab.</span></span>  

<span data-ttu-id="81574-181">查看实时内容并更快地检查潜在问题，包括以下示例。</span><span class="sxs-lookup"><span data-stu-id="81574-181">View live content and inspect potential issues more quickly, including the following examples.</span></span>  

*   <span data-ttu-id="81574-182">为什么删除框架？</span><span class="sxs-lookup"><span data-stu-id="81574-182">Why frames are dropped?</span></span>  
*   <span data-ttu-id="81574-183">为什么 JavaScript 以意外的方式与玩家交互？</span><span class="sxs-lookup"><span data-stu-id="81574-183">Why JavaScript is interacting with the player in an unexpected way?</span></span>  

### <span data-ttu-id="81574-184">使用 "元素" 面板上下文菜单捕获节点屏幕截图</span><span class="sxs-lookup"><span data-stu-id="81574-184">Capture node screenshots using the Elements panel context menu</span></span>  

<span data-ttu-id="81574-185">现在，你可以使用 " **元素** " 面板中的上下文菜单来捕获节点屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="81574-185">You may now capture node screenshots using the context menu in the **Elements** panel.</span></span>  

<span data-ttu-id="81574-186">例如，若要获取目录的屏幕截图，请将鼠标悬停在该元素上，打开上下文菜单 \ (右键单击 "\ ) "，然后选择 " **捕获节点屏幕截图**"。</span><span class="sxs-lookup"><span data-stu-id="81574-186">For example, to take a screenshot of the table of contents, hover on the element, open the contextual menu \(right-click\), and select **Capture node screenshot**.</span></span>  

:::image type="complex" source="../../media/2020/08/capture-node-screenshot.msft.png" alt-text="将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配" lightbox="../../media/2020/08/capture-node-screenshot.msft.png":::
   <span data-ttu-id="81574-188">捕获节点屏幕截图</span><span class="sxs-lookup"><span data-stu-id="81574-188">Capture node screenshots</span></span>  
:::image-end:::  

<span data-ttu-id="81574-189">Chromium 问题： [#1100253][CR1100253]</span><span class="sxs-lookup"><span data-stu-id="81574-189">Chromium issue: [#1100253][CR1100253]</span></span>  

### <span data-ttu-id="81574-190">问题工具更新</span><span class="sxs-lookup"><span data-stu-id="81574-190">Issues tool updates</span></span>  

<span data-ttu-id="81574-191">**控制台**面板上的问题警告栏现在被替换为常规消息。</span><span class="sxs-lookup"><span data-stu-id="81574-191">The Issues warning bar on the **Console** panel is now replaced with a regular message.</span></span>  

<!--todo: this figure need to be updated  -->  

:::image type="complex" source="../../media/2020/08/issue-console-msg.msft.png" alt-text="将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配" lightbox="../../media/2020/08/issue-console-msg.msft.png":::
   <span data-ttu-id="81574-193">控制台消息中的问题</span><span class="sxs-lookup"><span data-stu-id="81574-193">Issues in console message</span></span>  
:::image-end:::  

<span data-ttu-id="81574-194">默认情况下，在 " **问题** " 工具中，第三方 cookie 问题现已隐藏。</span><span class="sxs-lookup"><span data-stu-id="81574-194">Third-party cookie issues are now hidden by default in the **Issues** tool.</span></span>  <span data-ttu-id="81574-195">启用 "新建 **包含第三方 cookie 问题** " 复选框以查看问题。</span><span class="sxs-lookup"><span data-stu-id="81574-195">Enable the new **Include third-party cookie issues** checkbox to view the issues.</span></span>  

:::image type="complex" source="../../media/2020/08/third-party-cookies.msft.png" alt-text="将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配" lightbox="../../media/2020/08/third-party-cookies.msft.png":::
   <span data-ttu-id="81574-197">第三方 cookie 问题复选框</span><span class="sxs-lookup"><span data-stu-id="81574-197">third-party cookie issues checkbox</span></span>  
:::image-end:::  

<span data-ttu-id="81574-198">Chromium 问题： [1096481][CR1096481]、 [1068116][CR1068116]、 [1080589][CR1080589]</span><span class="sxs-lookup"><span data-stu-id="81574-198">Chromium issues: [1096481][CR1096481], [1068116][CR1068116], [1080589][CR1080589]</span></span>  

### <span data-ttu-id="81574-199">模拟缺少的本地字体</span><span class="sxs-lookup"><span data-stu-id="81574-199">Emulate missing local fonts</span></span>  

<span data-ttu-id="81574-200">打开 [渲染工具][DevtoolsEvaluatePerformanceReferenceAnalyzeRenderingPerformance] 并使用新的 " **禁用本地字体** " 功能来模拟 `local()` 规则中缺少的源 `@font-face` 。</span><span class="sxs-lookup"><span data-stu-id="81574-200">Open the [Rendering tool][DevtoolsEvaluatePerformanceReferenceAnalyzeRenderingPerformance] and use the new **Disable local fonts** feature to emulate missing `local()` sources in `@font-face` rules.</span></span>  

<span data-ttu-id="81574-201">例如，当 `Rubik` 字体安装在设备上并且 `@font-face src` 规则使用它作为 `local()` 字体时，Microsoft Edge 将使用您的设备中的本地字体文件。</span><span class="sxs-lookup"><span data-stu-id="81574-201">For example, when the `Rubik` font is installed on your device and the `@font-face src` rule uses it as a `local()` font, Microsoft Edge uses the local font file from your device.</span></span>  

<span data-ttu-id="81574-202">启用 " **禁用本地字体** " 时，DevTools 将忽略 `local()` 字体并从网络中提取每个字体。</span><span class="sxs-lookup"><span data-stu-id="81574-202">When **Disable local fonts** is enabled, DevTools ignores the `local()` fonts and fetches each from the network.</span></span>  

:::image type="complex" source="../../media/2020/08/disable-font.msft.png" alt-text="将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配" lightbox="../../media/2020/08/disable-font.msft.png":::
   <span data-ttu-id="81574-204">模拟缺少的本地字体</span><span class="sxs-lookup"><span data-stu-id="81574-204">Emulate missing local fonts</span></span>  
:::image-end:::  

<span data-ttu-id="81574-205">如果在开发期间使用同一字体的两个不同副本，例如以下示例。</span><span class="sxs-lookup"><span data-stu-id="81574-205">If you use two different copies of the same font during development, such as the following examples.</span></span>  

*   <span data-ttu-id="81574-206">设计工具的本地字体。</span><span class="sxs-lookup"><span data-stu-id="81574-206">A local font for your design tools.</span></span>  
*   <span data-ttu-id="81574-207">代码的 web 字体。</span><span class="sxs-lookup"><span data-stu-id="81574-207">A web font for your code.</span></span>  

<span data-ttu-id="81574-208">使用 " **禁用本地字体** "，让您能够更轻松地完成以下任务。</span><span class="sxs-lookup"><span data-stu-id="81574-208">Use **Disable local fonts** to make it easier for you to complete the following tasks.</span></span>  

*   <span data-ttu-id="81574-209">调试和测量 web 字体的加载性能和优化。</span><span class="sxs-lookup"><span data-stu-id="81574-209">Debug and measure loading performance and optimization of web fonts.</span></span>  
*   <span data-ttu-id="81574-210">验证 CSS 规则的准确性 `@font-face` 。</span><span class="sxs-lookup"><span data-stu-id="81574-210">Verify accuracy of your CSS `@font-face` rules.</span></span>  
*   <span data-ttu-id="81574-211">发现设备上安装的本地版本和 web 字体之间的差异。</span><span class="sxs-lookup"><span data-stu-id="81574-211">Discover differences between local versions installed on your device and a web font.</span></span>  

<span data-ttu-id="81574-212">Chromium 问题： [#384968][CR384968]</span><span class="sxs-lookup"><span data-stu-id="81574-212">Chromium issue: [#384968][CR384968]</span></span>  

### <span data-ttu-id="81574-213">模拟非活动用户</span><span class="sxs-lookup"><span data-stu-id="81574-213">Emulate inactive users</span></span>  

<span data-ttu-id="81574-214">" [空闲检测" API][WebDevIdleDetection] 允许开发人员检测非活动用户并对空闲状态更改做出响应。</span><span class="sxs-lookup"><span data-stu-id="81574-214">The [Idle Detection API][WebDevIdleDetection] allows developers to detect inactive users and react on idle state changes.</span></span>  <span data-ttu-id="81574-215">现在，你可以使用 DevTools 来模拟用户状态和屏幕状态的 **传感器** 工具中的空闲状态更改，而不是等待实际空闲状态更改。</span><span class="sxs-lookup"><span data-stu-id="81574-215">You are now able to use DevTools to emulate idle state changes in the **Sensors** tool for both the user state and the screen state instead of waiting for the actual idle state to change.</span></span>  <span data-ttu-id="81574-216">您可以从[抽屉][DevtoolsCustomizeIndexDrawer]打开 "**传感器**" 工具。</span><span class="sxs-lookup"><span data-stu-id="81574-216">You may open the **Sensors** tool from the [Drawer][DevtoolsCustomizeIndexDrawer].</span></span>  

:::image type="complex" source="../../media/2020/08/emulate-idle.msft.png" alt-text="将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配" lightbox="../../media/2020/08/emulate-idle.msft.png":::
   <span data-ttu-id="81574-218">模拟非活动用户</span><span class="sxs-lookup"><span data-stu-id="81574-218">Emulate inactive users</span></span>  
:::image-end:::  

<span data-ttu-id="81574-219">Chromium 问题： [#1090802][CR1090802]</span><span class="sxs-lookup"><span data-stu-id="81574-219">Chromium issue: [#1090802][CR1090802]</span></span>  

### <span data-ttu-id="81574-220">模拟首选数据-减少数据</span><span class="sxs-lookup"><span data-stu-id="81574-220">Emulate prefers-reduced-data</span></span>  

> [!NOTE]
> <span data-ttu-id="81574-221">在 Microsoft Edge 86 中，若要启用此功能，请转到 `edge://flags#enable-experimental-web-platform-features` 并打开 **实验性 Web 平台功能** 标志。</span><span class="sxs-lookup"><span data-stu-id="81574-221">In Microsoft Edge 86, to enable this feature, go to `edge://flags#enable-experimental-web-platform-features` and turn on the **Experimental Web Platform features** flag.</span></span>  <span data-ttu-id="81574-222">只有启用了标志，才会显示 "模拟" 选项。</span><span class="sxs-lookup"><span data-stu-id="81574-222">The emulation option is only displayed if the flag is enabled.</span></span>  

<span data-ttu-id="81574-223">" [优先-减少-数据][CsswgDraftsMediaqueries5DescdefMediaPrefersReducedData] 媒体" 查询检测减少数据的用户内容首选项。</span><span class="sxs-lookup"><span data-stu-id="81574-223">The [prefers-reduced-data][CsswgDraftsMediaqueries5DescdefMediaPrefersReducedData] media query detects user content preferences for reduced data.</span></span>  <span data-ttu-id="81574-224">如果选中此选项，用户将收到使用较少数据的备用页面内容。</span><span class="sxs-lookup"><span data-stu-id="81574-224">If selected, the user receives alternate page content that uses less data.</span></span>  

<span data-ttu-id="81574-225">您现在可以使用 DevTools 模拟 `prefers-reduced-data` 媒体查询。</span><span class="sxs-lookup"><span data-stu-id="81574-225">You may now use DevTools to emulate the `prefers-reduced-data` media query.</span></span>  

:::image type="complex" source="../../media/2020/08/emulate-prefers-reduced-data.msft.png" alt-text="将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配" lightbox="../../media/2020/08/emulate-prefers-reduced-data.msft.png":::
   <span data-ttu-id="81574-227">模拟首选数据-减少数据</span><span class="sxs-lookup"><span data-stu-id="81574-227">Emulate prefers-reduced-data</span></span>  
:::image-end:::  

<span data-ttu-id="81574-228">Chromium 问题： [#1096068][CR1096068]</span><span class="sxs-lookup"><span data-stu-id="81574-228">Chromium issue: [#1096068][CR1096068]</span></span>  

### <span data-ttu-id="81574-229">对新的 JavaScript 功能的支持</span><span class="sxs-lookup"><span data-stu-id="81574-229">Support for new JavaScript features</span></span>  

<span data-ttu-id="81574-230">DevTools 现已更好地支持以下 JavaScript 语言功能。</span><span class="sxs-lookup"><span data-stu-id="81574-230">DevTools now have better supported the following JavaScript language features.</span></span>  

| <span data-ttu-id="81574-231">JavaScript 语言功能</span><span class="sxs-lookup"><span data-stu-id="81574-231">JavaScript language feature</span></span> | <span data-ttu-id="81574-232">详细信息</span><span class="sxs-lookup"><span data-stu-id="81574-232">Details</span></span> |  
|:--- |:--- |  
| [<span data-ttu-id="81574-233">逻辑赋值运算符</span><span class="sxs-lookup"><span data-stu-id="81574-233">Logical assignment operators</span></span>][V8FeaturesLogicalAssignment] | <span data-ttu-id="81574-234">DevTools 现在支持 `&&=` `||=` `??=` 在 " **控制台** " 和 " **源** " 面板中通过 "新建"、"和" 运算符进行逻辑赋值。</span><span class="sxs-lookup"><span data-stu-id="81574-234">DevTools now supports logical assignment with the new `&&=`, `||=`, and `??=` operators in the **Console** and **Sources** panels.</span></span>  |  
| <span data-ttu-id="81574-235">整齐打印 [数值分隔符][V8FeaturesNumericSeparators]</span><span class="sxs-lookup"><span data-stu-id="81574-235">Pretty-print [numeric separators][V8FeaturesNumericSeparators]</span></span> | <span data-ttu-id="81574-236">DevTools 现已正确打印 " **源** " 面板中的数字分隔符。</span><span class="sxs-lookup"><span data-stu-id="81574-236">DevTools now properly pretty-prints the numeric separators in the **Sources** panel.</span></span>  |  

<span data-ttu-id="81574-237">Chromium 问题： [1086817][CR1086817]、 [1080569][CR1080569]</span><span class="sxs-lookup"><span data-stu-id="81574-237">Chromium issues: [1086817][CR1086817], [1080569][CR1080569]</span></span>  

### <span data-ttu-id="81574-238">Lighthouse 面板中的 Lighthouse 6。2</span><span class="sxs-lookup"><span data-stu-id="81574-238">Lighthouse 6.2 in the Lighthouse panel</span></span>  

<span data-ttu-id="81574-239">**Lighthouse**面板现在正在运行 Lighthouse 6.2。</span><span class="sxs-lookup"><span data-stu-id="81574-239">The **Lighthouse** panel is now running Lighthouse 6.2.</span></span>  <span data-ttu-id="81574-240">有关更改的完整列表，请转到 [Lighthouse 发行说明][GithubGooglechromeLighthouseV620]。</span><span class="sxs-lookup"><span data-stu-id="81574-240">For a full list of changes, go to the [Lighthouse release notes][GithubGooglechromeLighthouseV620].</span></span>  

<span data-ttu-id="81574-241">Chromium 问题： [#772558][CR772558]</span><span class="sxs-lookup"><span data-stu-id="81574-241">Chromium issue: [#772558][CR772558]</span></span>  

### <span data-ttu-id="81574-242">"服务工作人员" 窗格中的其他来源列表已过时</span><span class="sxs-lookup"><span data-stu-id="81574-242">Deprecation of other origins listing in the Service Workers pane</span></span>  

<span data-ttu-id="81574-243">DevTools 现在提供从 " **服务工作者** " 窗格 \ (**应用程序** 面板 > **服务工作者** 窗格 \ ) 的链接，以查看其他来源的服务工作人员的完整列表。</span><span class="sxs-lookup"><span data-stu-id="81574-243">DevTools now provides a link from the **Service workers** pane \(**Application** panel > **Service workers** pane\) to view the full list of service workers from other origins.</span></span>  <span data-ttu-id="81574-244">若要在不打开 DevTools 的情况下访问列表，请转到 `edge://service-worker-internals/?devtools` 。</span><span class="sxs-lookup"><span data-stu-id="81574-244">To access the list without opening the DevTools, go to `edge://service-worker-internals/?devtools`.</span></span>  

<span data-ttu-id="81574-245">以前的 DevTools 显示了一个嵌套在 **应用程序** 面板 > **服务工作人员** 窗格下的列表。</span><span class="sxs-lookup"><span data-stu-id="81574-245">Previously DevTools displayed a list nested under the **Application** panel > **Service workers** pane.</span></span>  

:::image type="complex" source="../../media/2020/08/sw-other-origins.msft.png" alt-text="将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配" lightbox="../../media/2020/08/sw-other-origins.msft.png":::
   <span data-ttu-id="81574-247">链接到其他来源</span><span class="sxs-lookup"><span data-stu-id="81574-247">Link to other origins</span></span>  
:::image-end:::  

<span data-ttu-id="81574-248">Chromium 问题： [#807440][CR807440]</span><span class="sxs-lookup"><span data-stu-id="81574-248">Chromium issue: [#807440][CR807440]</span></span>  

### <span data-ttu-id="81574-249">显示已筛选项目的覆盖范围摘要</span><span class="sxs-lookup"><span data-stu-id="81574-249">Show coverage summary for filtered items</span></span>  

<span data-ttu-id="81574-250">DevTools 现已动态重新计算并显示覆盖范围信息的摘要。</span><span class="sxs-lookup"><span data-stu-id="81574-250">DevTools now recalculate and display a summary of coverage information dynamically.</span></span>  <span data-ttu-id="81574-251">当在 [覆盖范围][DevtoolsCoverageIndex] 工具中应用筛选器时，将触发动态显示。</span><span class="sxs-lookup"><span data-stu-id="81574-251">The dynamic display is triggered when filters are applied in the [Coverage][DevtoolsCoverageIndex] tool.</span></span>  <span data-ttu-id="81574-252">**覆盖范围**工具始终显示所有覆盖范围信息的摘要之前。</span><span class="sxs-lookup"><span data-stu-id="81574-252">Before the **Coverage** tool always displayed a summary of all coverage information.</span></span>  

<span data-ttu-id="81574-253">在下面的第一条数字中，摘要最初显示在 `344 kB of 1.7 MB (20%) used so far.  1.4 MB unused.` 下图的第二个数字中， `26.8 kB of 408 kB (7%) used so far.  381 kB unused.` 应用 CSS 筛选后将显示摘要。</span><span class="sxs-lookup"><span data-stu-id="81574-253">In the first of the following figures, the summary initially displays `344 kB of 1.7 MB (20%) used so far.  1.4 MB unused.` and in the second of the following figures, the summary displays `26.8 kB of 408 kB (7%) used so far.  381 kB unused.` after CSS filtering is applied.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/coverage-compare.msft.png" alt-text="将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配" lightbox="../../media/2020/08/coverage-compare.msft.png":::
         <span data-ttu-id="81574-255">覆盖范围摘要</span><span class="sxs-lookup"><span data-stu-id="81574-255">Coverage summary</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/coverage-compare-css-filter.msft.png" alt-text="将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配" lightbox="../../media/2020/08/coverage-compare-css-filter.msft.png":::
         <span data-ttu-id="81574-257">已筛选项目的覆盖范围摘要</span><span class="sxs-lookup"><span data-stu-id="81574-257">Coverage summary for filtered items</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::

<span data-ttu-id="81574-258">Chromium 问题： [#1061385][CR1090802]</span><span class="sxs-lookup"><span data-stu-id="81574-258">Chromium issue: [#1061385][CR1090802]</span></span>  

### <span data-ttu-id="81574-259">应用程序面板中新的 "框架详细信息" 视图</span><span class="sxs-lookup"><span data-stu-id="81574-259">New frame details view in Application panel</span></span>  

<span data-ttu-id="81574-260">DevTools 现在显示每个帧的详细视图。</span><span class="sxs-lookup"><span data-stu-id="81574-260">DevTools now show a detailed view for each frame.</span></span>  <span data-ttu-id="81574-261">若要访问它，请在 "**应用程序**" 面板中的 "**框架**" 菜单下选择一个框架。</span><span class="sxs-lookup"><span data-stu-id="81574-261">To access it, choose a frame under the **Frames** menu in the **Application** panel.</span></span>  

:::image type="complex" source="../../media/2020/08/frame-details.msft.png" alt-text="将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配" lightbox="../../media/2020/08/frame-details.msft.png":::
   <span data-ttu-id="81574-263">**应用程序**面板中的框架的新详细视图</span><span class="sxs-lookup"><span data-stu-id="81574-263">New detailed view for a frame in **Application** panel</span></span>  
:::image-end:::  

<span data-ttu-id="81574-264">Chromium 问题： [#1093247][CR1093247]</span><span class="sxs-lookup"><span data-stu-id="81574-264">Chromium issue: [#1093247][CR1093247]</span></span>  

#### <span data-ttu-id="81574-265">打开的窗口的帧详细信息</span><span class="sxs-lookup"><span data-stu-id="81574-265">Frame details for opened windows</span></span>  

<span data-ttu-id="81574-266">打开的窗口和弹出窗口现在也显示在框架树下方。</span><span class="sxs-lookup"><span data-stu-id="81574-266">Open windows and pop-up windows now display under the frame tree as well.</span></span>  <span data-ttu-id="81574-267">打开的窗口的详细视图包含其他安全信息。</span><span class="sxs-lookup"><span data-stu-id="81574-267">The detailed view of the opened windows includes additional security information.</span></span>  

:::image type="complex" source="../../media/2020/08/window-opener.msft.png" alt-text="将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配" lightbox="../../media/2020/08/window-opener.msft.png":::
   <span data-ttu-id="81574-269">打开的窗口的新框架详细视图</span><span class="sxs-lookup"><span data-stu-id="81574-269">New frame detailed view for opened windows</span></span>  
:::image-end:::  

<span data-ttu-id="81574-270">Chromium 问题： [#1107766] [CR1107766]</span><span class="sxs-lookup"><span data-stu-id="81574-270">Chromium issue: [#1107766][CR1107766]</span></span>  

#### <span data-ttu-id="81574-271">安全性和隔离信息</span><span class="sxs-lookup"><span data-stu-id="81574-271">Security and isolation information</span></span>  

<span data-ttu-id="81574-272">安全上下文、 [跨起源 Embedder-策略 (COEP) ][WebDevCoopCoep]和 [基于 Opener (的合作基金) ][WebDevCoopCoep] 现在将显示在 "帧详细信息" 中。</span><span class="sxs-lookup"><span data-stu-id="81574-272">Secure context, [Cross-Origin-Embedder-Policy (COEP)][WebDevCoopCoep], and [Cross-Origin-Opener-Policy (COOP)][WebDevCoopCoep] are now displayed in the frame details.</span></span>  

:::image type="complex" source="../../media/2020/08/coep-coop.msft.png" alt-text="将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配" lightbox="../../media/2020/08/coep-coop.msft.png":::
   <span data-ttu-id="81574-274">安全性和隔离信息</span><span class="sxs-lookup"><span data-stu-id="81574-274">Security and isolation information</span></span>  
:::image-end:::  

<span data-ttu-id="81574-275">将来，Microsoft Edge DevTools 团队和 Chrome DevTools 团队计划向该帧的详细信息添加更多的安全信息。</span><span class="sxs-lookup"><span data-stu-id="81574-275">In the future, the Microsoft Edge DevTools team and the Chrome DevTools team are planning to add more security information to the frame details.</span></span>  

<span data-ttu-id="81574-276">Chromium 问题： [#1051466][CR1051466]</span><span class="sxs-lookup"><span data-stu-id="81574-276">Chromium issue: [#1051466][CR1051466]</span></span>  

### <span data-ttu-id="81574-277">元素和网络面板更新</span><span class="sxs-lookup"><span data-stu-id="81574-277">Elements and Network panel updates</span></span>  

#### <span data-ttu-id="81574-278">"样式" 窗格中的辅助颜色建议</span><span class="sxs-lookup"><span data-stu-id="81574-278">Accessible color suggestion in the Styles pane</span></span>  

<span data-ttu-id="81574-279">DevTools 现在提供低颜色对比度文本的颜色建议。</span><span class="sxs-lookup"><span data-stu-id="81574-279">DevTools now provides color suggestions for low color contrast text.</span></span>  

<span data-ttu-id="81574-280">在下面的示例中， `h1` 具有低对比度文本。</span><span class="sxs-lookup"><span data-stu-id="81574-280">In the example below, `h1` has low contrast text.</span></span>  <span data-ttu-id="81574-281">若要解决此问题，请 `color` 在 " **样式** " 窗格中打开该属性的颜色选取器。</span><span class="sxs-lookup"><span data-stu-id="81574-281">To fix it, open the color picker of the `color` property in the **Styles** pane.</span></span>  <span data-ttu-id="81574-282">展开 " **对比度比率** " 部分后，DevTools 将提供 AA 和 AAA 颜色建议。</span><span class="sxs-lookup"><span data-stu-id="81574-282">After you expand the **Contrast ratio** section, DevTools provides AA and AAA color suggestions.</span></span>  <span data-ttu-id="81574-283">选择建议的颜色以应用颜色。</span><span class="sxs-lookup"><span data-stu-id="81574-283">Select the suggested color to apply the color.</span></span>  

:::image type="complex" source="../../media/2020/08/contrast-color-suggestion.msft.png" alt-text="将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配" lightbox="../../media/2020/08/contrast-color-suggestion.msft.png":::
   <span data-ttu-id="81574-285">颜色选取器建议 AA 和 AAA 颜色建议</span><span class="sxs-lookup"><span data-stu-id="81574-285">Color picker suggests AA and AAA color suggestions</span></span>  
:::image-end:::  

<span data-ttu-id="81574-286">Chromium 问题： [#1093227][CR1093227]</span><span class="sxs-lookup"><span data-stu-id="81574-286">Chromium issue: [#1093227][CR1093227]</span></span>  

#### <span data-ttu-id="81574-287">"元素" 面板中的 "恢复属性" 窗格</span><span class="sxs-lookup"><span data-stu-id="81574-287">Reinstate Properties pane in the Elements panel</span></span>  

<span data-ttu-id="81574-288">" **属性** " 窗格将返回。</span><span class="sxs-lookup"><span data-stu-id="81574-288">The **Properties** pane is back.</span></span>  <span data-ttu-id="81574-289">它已 [在 Microsoft Edge 84 中弃用][DevtoolsWhatsnew200205DevtoolsDeprecationPropertiesPaneElementsPanel]。</span><span class="sxs-lookup"><span data-stu-id="81574-289">It was [deprecated in Microsoft Edge 84][DevtoolsWhatsnew200205DevtoolsDeprecationPropertiesPaneElementsPanel].</span></span>  <span data-ttu-id="81574-290">Microsoft Edge DevTools 团队和 Chrome DevTools 团队是对检查元素的属性进行规划的改进。</span><span class="sxs-lookup"><span data-stu-id="81574-290">The Microsoft Edge DevTools team and the Chrome DevTools team are planning improvements for inspecting properties of elements.</span></span>  

:::image type="complex" source="../../media/2020/08/properties-pane.msft.png" alt-text="将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配" lightbox="../../media/2020/08/properties-pane.msft.png":::
   <span data-ttu-id="81574-292">"**元素**" 面板中的 "**属性**" 窗格</span><span class="sxs-lookup"><span data-stu-id="81574-292">**Properties** pane in the **Elements** panel</span></span>  
:::image-end:::  

<span data-ttu-id="81574-293">Chromium 问题：</span><span class="sxs-lookup"><span data-stu-id="81574-293">Chromium issue:</span></span>  <!--  [#1105205][CR1105205],  -->  <span data-ttu-id="81574-294">[#1116085][CR1116085]</span><span class="sxs-lookup"><span data-stu-id="81574-294">[#1116085][CR1116085]</span></span>  

<!--  
#### Human-readable X-Client-Data header values in the Network panel  

When inspecting a network resource in the Network panel, DevTools now formats any `X-Client-Data` header values in **Headers** pane as code.  

The `X-Client-Data` HTTP header contains a list of experiment IDs and Microsoft Edge flags that are enabled in your browser.  The raw header values look like opaque strings since the values are `base-64-encoded`, serialized [protocol buffers][GoogleDevelopersProtocolBuffers].  To make the contents more transparent to developers, DevTools now shows the decoded values.  

:::image type="complex" source="../../media/2020/08/x-client-data.msft.png" alt-text="将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配" lightbox="../../media/2020/08/x-client-data.msft.png":::
   Human-readable `X-Client-Data` header values  
:::image-end:::  

Chromium issue: [#1103854][CR1103854]  
-->  

#### <span data-ttu-id="81574-295">"样式" 窗格中的 "自动完成" 自定义字体</span><span class="sxs-lookup"><span data-stu-id="81574-295">Autocomplete custom fonts in the Styles pane</span></span>  

<span data-ttu-id="81574-296">在编辑 "样式" 窗格中的属性时，导入的字体现在将添加到 CSS 自动完成列表 `font-family` 中。 **Styles**</span><span class="sxs-lookup"><span data-stu-id="81574-296">Imported font faces are now added to the list of CSS autocompletion when editing the `font-family` property in the **Styles** pane.</span></span>  

<span data-ttu-id="81574-297">例如，如果 `monospace` 是在本地计算机上安装的自定义字体，它将显示在 CSS 完成列表中。</span><span class="sxs-lookup"><span data-stu-id="81574-297">For example, if `monospace` is a custom font installed on the local machine, it's displayed in the CSS completion list.</span></span> <span data-ttu-id="81574-298">在早期版本的 Microsoft Edge 中，字体未显示。</span><span class="sxs-lookup"><span data-stu-id="81574-298">In previous versions of Microsoft Edge, the font wasn't displayed.</span></span>

:::image type="complex" source="../../media/2020/08/font-auto-complete.msft.png" alt-text="将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配" lightbox="../../media/2020/08/font-auto-complete.msft.png":::
   <span data-ttu-id="81574-300">自动完成自定义字体</span><span class="sxs-lookup"><span data-stu-id="81574-300">Autocomplete custom fonts</span></span>  
:::image-end:::  

<span data-ttu-id="81574-301">Chromium 问题： [#1106221] [CR1106221]</span><span class="sxs-lookup"><span data-stu-id="81574-301">Chromium issue: [#1106221][CR1106221]</span></span>  

#### <span data-ttu-id="81574-302">在 "网络" 面板中一致地显示资源类型</span><span class="sxs-lookup"><span data-stu-id="81574-302">Consistently display resource type in Network panel</span></span>  

<span data-ttu-id="81574-303">DevTools 现在与原始网络请求一致地显示相同的资源类型，并且 `/ Redirect` 在重定向 \ (HTTP 状态代码 302 \ ) 时，附加到 " **类型** " 列的值。</span><span class="sxs-lookup"><span data-stu-id="81574-303">DevTools now consistently display the same resource type as the original network request and appends `/ Redirect` to the **Type** column value when redirection \(HTTP status code 302\) happens.</span></span>  

<span data-ttu-id="81574-304">以前 DevTools 将类型更改为 " `Other` 有时"。</span><span class="sxs-lookup"><span data-stu-id="81574-304">Previously DevTools changed the type to `Other` sometimes.</span></span>  

:::image type="complex" source="../../media/2020/08/network-redirect.msft.png" alt-text="将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配" lightbox="../../media/2020/08/network-redirect.msft.png":::
   <span data-ttu-id="81574-306">显示重定向资源类型</span><span class="sxs-lookup"><span data-stu-id="81574-306">Display redirect resource type</span></span>  
:::image-end:::  

<span data-ttu-id="81574-307">Chromium 问题： [#997694][CR997694]</span><span class="sxs-lookup"><span data-stu-id="81574-307">Chromium issue: [#997694][CR997694]</span></span>  

#### <span data-ttu-id="81574-308">在 "元素" 和 "网络" 面板中清除按钮</span><span class="sxs-lookup"><span data-stu-id="81574-308">Clear buttons in the Elements and Network panels</span></span>  

<span data-ttu-id="81574-309">以下文本框现在具有 " **清除** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="81574-309">The following text boxes now have **Clear** buttons.</span></span>  

*   <span data-ttu-id="81574-310">" **样式** " 窗格和 " **网络** " 面板中的 "筛选" 文本框。</span><span class="sxs-lookup"><span data-stu-id="81574-310">The filter text boxes in the **Styles** pane and **Network** panel.</span></span>  
*   <span data-ttu-id="81574-311">" **元素** " 面板中的 "DOM 搜索" 文本框。</span><span class="sxs-lookup"><span data-stu-id="81574-311">The DOM search text box in the **Elements** panel.</span></span>  

<span data-ttu-id="81574-312">选择 " **清除** " 按钮以删除任何输入文本。</span><span class="sxs-lookup"><span data-stu-id="81574-312">Choose the **Clear** button to remove any inputted text.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/clear-button-elements.msft.png" alt-text="将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配" lightbox="../../media/2020/08/clear-button-elements.msft.png":::
         <span data-ttu-id="81574-314">" **元素** " 面板中的 "清除" 按钮</span><span class="sxs-lookup"><span data-stu-id="81574-314">Clear buttons in the **Elements** panels</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/clear-button-network.msft.png" alt-text="将 DevTools 中的键盘快捷方式与 Visual Studio 代码匹配" lightbox="../../media/2020/08/clear-button-network.msft.png":::
         <span data-ttu-id="81574-316">"  **网络** " 面板中的 "清除" 按钮</span><span class="sxs-lookup"><span data-stu-id="81574-316">Clear buttons in the  **Network** panels</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="81574-317">Chromium 问题： [#1067184][CR1067184]</span><span class="sxs-lookup"><span data-stu-id="81574-317">Chromium issue: [#1067184][CR1067184]</span></span>  

## <span data-ttu-id="81574-318">下载 Microsoft Edge 预览频道</span><span class="sxs-lookup"><span data-stu-id="81574-318">Download the Microsoft Edge preview channels</span></span>  

<span data-ttu-id="81574-319">如果你使用的是 Windows 或 macOS，请考虑使用 [ Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels] 作为默认开发浏览器。</span><span class="sxs-lookup"><span data-stu-id="81574-319">If you are on Windows or macOS, consider using the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] as your default development browser.</span></span>  <span data-ttu-id="81574-320">预览频道使你能够访问最新的 DevTools 功能。</span><span class="sxs-lookup"><span data-stu-id="81574-320">The preview channels give you access to the latest DevTools features.</span></span>  

## <span data-ttu-id="81574-321">与 Microsoft Edge DevTools 团队取得联系</span><span class="sxs-lookup"><span data-stu-id="81574-321">Getting in touch with Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- image links -->  

[ImageSettingsIcon]: /microsoft-edge/devtools-guide-chromium/media/settings-icon.msft.png "DevTools "设置" 图标"  

<!-- links -->  

[DevtoolsWhatsnew200205DevtoolsDeprecationPropertiesPaneElementsPanel]: ../05/devtools.md#deprecation-of-the-properties-pane-in-the-elements-panel ""元素" 面板中 "属性" 窗格的弃用-DevTools 中的新增功能 (Microsoft Edge 84) |Microsoft 文档"  
[DevtoolsWhatsnew200206DevtoolsCssGridDebuggingFeatures]: ../06/devtools.md#css-grid-debugging-features "CSS 网格调试功能-DevTools 中的新增功能 (Microsoft Edge 85) |Microsoft 文档"  

[DevtoolsDeviceModeIndex]: /microsoft-edge/devtools-guide-chromium/device-mode/index "在 Microsoft Edge DevTools 中模拟移动设备 |Microsoft 文档"  
[DevtoolsCustomizeShortcuts]: /microsoft-edge/devtools-guide-chromium/customize/shortcuts "自定义 Microsoft Edge DevTools 中的键盘快捷方式 |Microsoft 文档"  
[DevtoolsExperimentalFeaturesEnableExperimentalApis]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-experimental-apis "启用实验性 Api-实验性功能 |Microsoft 文档"  
[DevtoolsExperimentalFeaturesEnableNewCssGridDebuggingFeatures]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-new-css-grid-debugging-features "模拟：支持双重屏幕模式-实验功能 |Microsoft 文档"  
[DevtoolsExperimentalFeaturesEnableSourceOrderViewer]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-source-order-viewer "启用源订单查看器-实验性功能 |Microsoft 文档"
[DevtoolsExperimentalFeaturesEmulationSupportDualScreenMode]: https://review.docs.microsoft.com/microsoft-edge/devtools-guide-chromium/experimental-features?branch=user/zoghadya/dual-screen-experiment#emulation-support-dual-screen-mode "模拟：支持双重屏幕模式-实验功能 |Microsoft 文档"  
[DevtoolsExperimentalFeaturesTestingOnFoldableDualScreenDevices]: /microsoft-edge/devtools-guide-chromium/experimental-features#testing-on-foldable-and-dual-screen-devices "在折叠和双屏幕设备上测试-实验功能 |Microsoft 文档"  
[DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures]: /microsoft-edge/devtools-guide-chromium/experimental-features#turn-on-experimental-features "启用实验功能-实验功能 |Microsoft 文档"  
[DevtoolsConsoleApiTable]: /microsoft-edge/devtools-guide-chromium/console/api#table "表-控制台 API 参考 |Microsoft 文档"  
[DevtoolsCoverageIndex]: /microsoft-edge/devtools-guide-chromium/coverage/index "使用 Microsoft Edge DevTools | 中的 "覆盖范围" 选项卡查找未使用的 JavaScript 和 CSS 代码。Microsoft 文档"  
[DevtoolsCustomizeIndexDrawer]: /microsoft-edge/devtools-guide-chromium/customize/index#drawer "抽屉-自定义 Microsoft Edge DevTools |Microsoft 文档"  
[DevtoolsEvaluatePerformanceReferenceAnalyzeRenderingPerformance]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference#analyze-rendering-performance-with-the-rendering-tab "通过 "呈现" 选项卡分析呈现性能-性能分析参考 |Microsoft 文档"  
[DevtoolsMediaIndex]: /microsoft-edge/devtools-guide-chromium/media/index "查看和调试媒体播放器信息 |Microsoft 文档"  

[DualScreenIntroductionHowWorkSeam]:  /dual-screen/introduction#how-to-work-with-the-seam "如何使用双屏幕设备的接缝简介 |Microsoft 文档"  
[DualScreenWebCssMediaSpanning]: /dual-screen/web/css-media-spanning "适用于双屏幕检测的 CSS 媒体屏幕扩展功能 |Microsoft 文档"  
[DualScreenWebJavascriptGetwindowsegments]: /dual-screen/web/javascript-getwindowsegments "用于双屏幕设备的 getWindowSegments JavaScript API |Microsoft 文档"  

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download "Microsoft Edge 预览频道"  

[VisualStudioCode]: https://code.visualstudio.com "Visual Studio 代码 "  
[VisualStudioCodeShortcutsKeyboardWindows]: https://code.visualstudio.com/shortcuts/keyboard-shortcuts-windows.pdf "适用于 Windows 的 Visual Studio 代码键盘快捷方式"  

[MicrosoftSurfaceDevicesDuo]: https://www.microsoft.com/surface/devices/surface-duo "新的 Surface 双核"  

[EdgeDevToolsTwitterAccount]: https://twitter.com/EdgeDevTools "@EdgeDevTools Twitter 帐户"  

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium bug"  

[CR174309]: https://crbug.com/174309 "DevTools：允许自定义键盘快捷方式/键绑定 |Chromium bug"
[CR384968]: https://crbug.com/384968 "选项可忽略本地 ( # A1 字体 |Chromium bug"  
[CR772558]: https://crbug.com/772558 "DevTools：更新到最新版本的 Lighthouse |Chromium bug"  
[CR807440]: https://crbug.com/807440 "Chrome 通过大量的 SWs |Chromium bug"  
[CR997694]: https://crbug.com/997694 "302状态的 XHR 请求不会显示在 "网络" 面板中的 "XHR" 筛选器 |Chromium bug"  
[CR1047356]: https://crbug.com/1047356 "CSS 网格/Flexbox/表格工具"  
[CR1051466]: https://crbug.com/1051466 "在 DevTools | 中支持合作基金/COEP 调试Chromium bug"  
[CR1054281]: https://crbug.com/1054281 "功能请求： DevTools 应模拟可折叠和双屏幕设备 |Chromium bug"  
[CR1067184]: https://crbug.com/1067184 "功能请求：网络 & 元素上的 "清除筛选" 按钮-> 样式筛选器输入 |Chromium bug"  
[CR1068116]: https://crbug.com/1068116 "☂装运问题面板 |Chromium bug"  
[CR1080569]: https://crbug.com/1080569 "acorn 不支持逻辑赋值运算符 |Chromium bug"  
[CR1080589]: https://crbug.com/1080589 "按第三方/第三方对问题进行分类Chromium bug"  
[CR1086817]: https://crbug.com/1086817 "acorn 不支持数值分隔符 |Chromium bug"  
[CR1090802]: https://crbug.com/1090802 "模拟来自空闲检测 API 的空闲状态更改 |Chromium bug"  
[CR1093227]: https://crbug.com/1093227 "DevTools：建议最接近的辅助颜色 |Chromium bug"  
[CR1093247]: https://crbug.com/1093247 "在应用程序面板中显示有关框架的信息 |Chromium bug"  
[CR1094406]: https://crbug.com/1094406 "开发人员希望使用源订单查看器 https://webwewant.fyi/wants/64/"  
[CR1096068]: https://crbug.com/1096068 "DevTools：支持模拟 "首选-减少-数据媒体" 功能 |Chromium bug"  
[CR1096481]: https://crbug.com/1096481 "问题横幅位置 |Chromium bug"  
[CR1100253]: https://crbug.com/1100253 "在元素上下文菜单中添加屏幕截图节点快捷方式 |Chromium bug"  
[CR1103316]: https://crbug.com/1103316 "在第一个搜索结果 | resolveNode 中，元素搜索不会 (突出显示文本等) Chromium bug"  
[CR1103854]: https://crbug.com/1103854 "在开发工具 | 中取消模糊处理 X 客户端数据值 |Chromium bug"  
<!--  [CR1105205]: https://crbug.com/1105205 "Issue 1105205 | Chromium bugs"  -->  
<span data-ttu-id="81574-369">[CR1106221]： https://crbug.com/1106221 "在样式面板中将导入的字体添加到字体系列自动完成" |Chromium bug "</span><span class="sxs-lookup"><span data-stu-id="81574-369">[CR1106221]: https://crbug.com/1106221 "Add imported fonts to the font-family autocompletion in the Styles panel | Chromium bugs"</span></span>  
<span data-ttu-id="81574-370">[CR1107766]： https://crbug.com/1107766 "显示由" 窗口生成的帧的相关信息。在框架树中打开 ( # A1 "|Chromium bug "</span><span class="sxs-lookup"><span data-stu-id="81574-370">[CR1107766]: https://crbug.com/1107766 "Display info about frames generated by 'window.open()' in frame tree | Chromium bugs"</span></span>  
<span data-ttu-id="81574-371">[CR1115011]： https://crbug.com/1115011 "从控制台复制表时不保留表的结构 |Chromium bug "</span><span class="sxs-lookup"><span data-stu-id="81574-371">[CR1115011]: https://crbug.com/1115011 "When copying a table from the console the structure of the table is not preserved | Chromium bugs"</span></span>  
<span data-ttu-id="81574-372">[CR1116085]： https://crbug.com/1116085 "请返回 DevTools 属性检查器 |Chromium bug "</span><span class="sxs-lookup"><span data-stu-id="81574-372">[CR1116085]: https://crbug.com/1116085 "Please bring back the DevTools Properties inspector | Chromium bugs"</span></span>  

[CsswgDraftsMediaqueries5DescdefMediaPrefersReducedData]: https://drafts.csswg.org/mediaqueries-5#descdef-media-prefers-reduced-data "首选-减少-数据-媒体查询级别 5 |W3C CSS 工作组编辑器草稿"  

[GithubGooglechromeLighthouseV620]: https://github.com/GoogleChrome/lighthouse/releases/tag/v6.2.0 "v 6.2.0-GoogleChrome/lighthouse |GitHub"  

[GoogleDevelopersProtocolBuffers]: https://developers.google.com/protocol-buffers "协议缓冲区 |Google 开发人员"  

[SamsungMobileGalaxyFold]: https://www.samsung.com/us/mobile/galaxy-fold "Galaxy 折页 |美国 Samsung"  

[V8FeaturesLogicalAssignment]: https://v8.dev/features/logical-assignment "逻辑赋值 |V8"  
[V8FeaturesNumericSeparators]: https://v8.dev/features/numeric-separators "数字分隔符 |V8"  

[WebDevCoopCoep]: https://web.dev/coop-coep "使用合作基金和 COEP 将您的网站设置为 "跨原点隔离" |web 开发"  
[WebDevIdleDetection]: https://web.dev/idle-detection "通过 "空闲检测 API" 检测非活动用户 |web 开发"  
[WebDevNonCompositedAnimations]: https://web.dev/non-composited-animations "避免非合成动画 |web 开发"  

> [!NOTE]
> <span data-ttu-id="81574-382">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="81574-382">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="81574-383">原始页面可在 [此处](https://developers.google.com/web/updates/2020/08/devtools/index) 找到，并由 [Jecelyn Yeen][JecelynYeen] (开发人员和 DevTools，Chrome \ ) 。</span><span class="sxs-lookup"><span data-stu-id="81574-383">The original page is found [here](https://developers.google.com/web/updates/2020/08/devtools/index) and is authored by [Jecelyn Yeen][JecelynYeen] \(Developer advocate, Chrome DevTools\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="81574-385">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="81574-385">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen  
