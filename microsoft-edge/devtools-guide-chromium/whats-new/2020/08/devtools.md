---
description: Match keyboard shortcuts to Visual Studio Code, emulate Surface Duo and Samsung Galaxy Fold, CSS grid overlay improvements, and more.
title: What's new in DevTools (Microsoft Edge 86)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/08/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web development, f12 tools, devtools
ms.openlocfilehash: 943eca7e73385513b264feb74ec37c450d5c5a2f
ms.sourcegitcommit: 6b577cb118f34f3ff2c65eab2908b65f155dc151
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/09/2020
ms.locfileid: "11004100"
---
# <span data-ttu-id="4eaa0-104">What's New In DevTools (Microsoft Edge 86)</span><span class="sxs-lookup"><span data-stu-id="4eaa0-104">What's New In DevTools (Microsoft Edge 86)</span></span>  

## <span data-ttu-id="4eaa0-105">Announcements from the Microsoft Edge DevTools team</span><span class="sxs-lookup"><span data-stu-id="4eaa0-105">Announcements from the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/edge-whats-new-note.md)]  

### <span data-ttu-id="4eaa0-106">Match keyboard shortcuts in DevTools to Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="4eaa0-106">Match keyboard shortcuts in DevTools to Visual Studio Code</span></span>  

<span data-ttu-id="4eaa0-107">In Microsoft Edge 86, you may match keyboard shortcuts in the DevTools to your shortcuts in [Visual Studio Code][VisualStudioCode].</span><span class="sxs-lookup"><span data-stu-id="4eaa0-107">In Microsoft Edge 86, you may match keyboard shortcuts in the DevTools to your shortcuts in [Visual Studio Code][VisualStudioCode].</span></span> 

:::image type="complex" source="../../media/2020/08/keyboard-shortcut.msft.png" alt-text="Match keyboard shortcuts in the DevTools to Visual Studio Code" lightbox="../../media/2020/08/keyboard-shortcut.msft.png":::
   <span data-ttu-id="4eaa0-109">Match keyboard shortcuts in the DevTools to Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="4eaa0-109">Match keyboard shortcuts in the DevTools to Visual Studio Code</span></span>  
:::image-end:::  

<span data-ttu-id="4eaa0-110">To activate this feature, navigate to [Customize keyboard shortcuts in the Microsoft Edge DevTools][DevtoolsCustomizeShortcuts].</span><span class="sxs-lookup"><span data-stu-id="4eaa0-110">To activate this feature, navigate to [Customize keyboard shortcuts in the Microsoft Edge DevTools][DevtoolsCustomizeShortcuts].</span></span>  

<span data-ttu-id="4eaa0-111">For example, the keyboard shortcut for pausing or continuing running a script in [Visual Studio Code][VisualStudioCodeShortcutsKeyboardWindows] is `F5`.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-111">For example, the keyboard shortcut for pausing or continuing running a script in [Visual Studio Code][VisualStudioCodeShortcutsKeyboardWindows] is `F5`.</span></span>  <span data-ttu-id="4eaa0-112">With the **DevTools (Default)** preset, that same shortcut in the DevTools is `F8`, but when you choose the **Visual Studio Code** preset, that shortcut is now also `F5`.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-112">With the **DevTools (Default)** preset, that same shortcut in the DevTools is `F8`, but when you choose the **Visual Studio Code** preset, that shortcut is now also `F5`.</span></span>  

<span data-ttu-id="4eaa0-113">Chromium issue [#174309][CR174309]</span><span class="sxs-lookup"><span data-stu-id="4eaa0-113">Chromium issue [#174309][CR174309]</span></span>  

### <span data-ttu-id="4eaa0-114">Emulate Surface Duo and Samsung Galaxy Fold</span><span class="sxs-lookup"><span data-stu-id="4eaa0-114">Emulate Surface Duo and Samsung Galaxy Fold</span></span>  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="Match keyboard shortcuts in the DevTools to Visual Studio Code":::
   <span data-ttu-id="4eaa0-116">Experimental feature</span><span class="sxs-lookup"><span data-stu-id="4eaa0-116">Experimental feature</span></span>  
:::image-end:::  

<span data-ttu-id="4eaa0-117">You are now able to test the look and feel of your website or app on two new devices:  [Surface Duo][MicrosoftSurfaceDevicesDuo] and [Samsung Galaxy Fold][SamsungMobileGalaxyFold] in Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-117">You are now able to test the look and feel of your website or app on two new devices:  [Surface Duo][MicrosoftSurfaceDevicesDuo] and [Samsung Galaxy Fold][SamsungMobileGalaxyFold] in Microsoft Edge.</span></span>  

<span data-ttu-id="4eaa0-118">To help enhance your website or app for the dual-screen and foldable devices, use the following features when [emulating the device][DevtoolsDeviceModeIndex].</span><span class="sxs-lookup"><span data-stu-id="4eaa0-118">To help enhance your website or app for the dual-screen and foldable devices, use the following features when [emulating the device][DevtoolsDeviceModeIndex].</span></span>  

*   <span data-ttu-id="4eaa0-119">[Spanning][DevtoolsExperimentalFeaturesTestingOnFoldableDualScreenDevices], which is when your website \(or app\) appears across both screens.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-119">[Spanning][DevtoolsExperimentalFeaturesTestingOnFoldableDualScreenDevices], which is when your website \(or app\) appears across both screens.</span></span>
*   <span data-ttu-id="4eaa0-120">[Rendering the seam][DualScreenIntroductionHowWorkSeam], which is the space between the two screens.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-120">[Rendering the seam][DualScreenIntroductionHowWorkSeam], which is the space between the two screens.</span></span>
*   <span data-ttu-id="4eaa0-121">[Enabling experimental Web Platform APIs][DevtoolsExperimentalFeaturesEnableExperimentalApis] to access the new [CSS media screen-spanning feature][DualScreenWebCssMediaSpanning] and [JavaScript getWindowSegments API][DualScreenWebJavascriptGetwindowsegments].</span><span class="sxs-lookup"><span data-stu-id="4eaa0-121">[Enabling experimental Web Platform APIs][DevtoolsExperimentalFeaturesEnableExperimentalApis] to access the new [CSS media screen-spanning feature][DualScreenWebCssMediaSpanning] and [JavaScript getWindowSegments API][DualScreenWebJavascriptGetwindowsegments].</span></span>  

:::image type="complex" source="../../media/2020/08/surface-duo-device-emulation.msft.png" alt-text="Match keyboard shortcuts in the DevTools to Visual Studio Code" lightbox="../../media/2020/08/surface-duo-device-emulation.msft.png":::
   <span data-ttu-id="4eaa0-123">Device emulation for Surface Duo</span><span class="sxs-lookup"><span data-stu-id="4eaa0-123">Device emulation for Surface Duo</span></span>  
:::image-end:::  

<span data-ttu-id="4eaa0-124">To turn on this experimental feature, navigate to [Turn on experimental features][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures] and choose the checkbox next to **Emulation: Support dual screen mode**.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-124">To turn on this experimental feature, navigate to [Turn on experimental features][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures] and choose the checkbox next to **Emulation: Support dual screen mode**.</span></span>  

<span data-ttu-id="4eaa0-125">For more information about this experiment, navigate to [Emulation: Support dual screen mode][DevtoolsExperimentalFeaturesEmulationSupportDualScreenMode].</span><span class="sxs-lookup"><span data-stu-id="4eaa0-125">For more information about this experiment, navigate to [Emulation: Support dual screen mode][DevtoolsExperimentalFeaturesEmulationSupportDualScreenMode].</span></span>  

<span data-ttu-id="4eaa0-126">Chromium issue: [#1054281][CR1054281]</span><span class="sxs-lookup"><span data-stu-id="4eaa0-126">Chromium issue: [#1054281][CR1054281]</span></span>  

### <span data-ttu-id="4eaa0-127">CSS grid overlay improvements and new experimental grid features</span><span class="sxs-lookup"><span data-stu-id="4eaa0-127">CSS grid overlay improvements and new experimental grid features</span></span>  

<span data-ttu-id="4eaa0-128">Thank you for the positive feedback about the improved CSS grid overlays.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-128">Thank you for the positive feedback about the improved CSS grid overlays.</span></span>  <span data-ttu-id="4eaa0-129">The CSS grid overlays are now enabled by default and do not require you to turn on an experiment.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-129">The CSS grid overlays are now enabled by default and do not require you to turn on an experiment.</span></span>  

:::image type="complex" source="../../media/2020/08/css-grid-overlay-article.msft.png" alt-text="Match keyboard shortcuts in the DevTools to Visual Studio Code" lightbox="../../media/2020/08/css-grid-overlay-article.msft.png":::
   <span data-ttu-id="4eaa0-131">CSS grid overlay for `article` element</span><span class="sxs-lookup"><span data-stu-id="4eaa0-131">CSS grid overlay for `article` element</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="4eaa0-132">For more information about grid overlays, go to [CSS grid debugging features][DevtoolsWhatsnew200206DevtoolsCssGridDebuggingFeatures].</span><span class="sxs-lookup"><span data-stu-id="4eaa0-132">For more information about grid overlays, go to [CSS grid debugging features][DevtoolsWhatsnew200206DevtoolsCssGridDebuggingFeatures].</span></span>  

<span data-ttu-id="4eaa0-133">The Microsoft Edge DevTools team and the Chrome DevTools team collaborate on additional features.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-133">The Microsoft Edge DevTools team and the Chrome DevTools team collaborate on additional features.</span></span>  <span data-ttu-id="4eaa0-134">The new features include multiple overlays that are persistent and configurable from a new **Layout** pane on the **Elements** panel.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-134">The new features include multiple overlays that are persistent and configurable from a new **Layout** pane on the **Elements** panel.</span></span>  

<span data-ttu-id="4eaa0-135">To turn on this experimental feature, navigate to [Turn on experimental features][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures] and choose the checkbox next to **Enable new CSS Grid debugging features (configuration options available in Layout sidebar pane in Elements after restart)**.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-135">To turn on this experimental feature, navigate to [Turn on experimental features][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures] and choose the checkbox next to **Enable new CSS Grid debugging features (configuration options available in Layout sidebar pane in Elements after restart)**.</span></span>  

<span data-ttu-id="4eaa0-136">For more information about this experiment, navigate to [Enable new CSS grid debugging features][DevtoolsExperimentalFeaturesEnableNewCssGridDebuggingFeatures].</span><span class="sxs-lookup"><span data-stu-id="4eaa0-136">For more information about this experiment, navigate to [Enable new CSS grid debugging features][DevtoolsExperimentalFeaturesEnableNewCssGridDebuggingFeatures].</span></span>  

<span data-ttu-id="4eaa0-137">Chromium issue: [#1047356][CR1047356]</span><span class="sxs-lookup"><span data-stu-id="4eaa0-137">Chromium issue: [#1047356][CR1047356]</span></span>  

### <span data-ttu-id="4eaa0-138">Table copied from the Console preserves formatting</span><span class="sxs-lookup"><span data-stu-id="4eaa0-138">Table copied from the Console preserves formatting</span></span>  

<span data-ttu-id="4eaa0-139">In Microsoft Edge 85 or earlier, the formatting of a copied `console.table` was lost.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-139">In Microsoft Edge 85 or earlier, the formatting of a copied `console.table` was lost.</span></span>  <span data-ttu-id="4eaa0-140">If you copied the output from the [table][DevtoolsConsoleApiTable] Console API, and pasted it, only the text of the table was kept.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-140">If you copied the output from the [table][DevtoolsConsoleApiTable] Console API, and pasted it, only the text of the table was kept.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/console-table-beta.msft.png" alt-text="Match keyboard shortcuts in the DevTools to Visual Studio Code" lightbox="../../media/2020/08/console-table-beta.msft.png":::
         `table` <span data-ttu-id="4eaa0-142">Console API output in Microsoft Edge 85 or earlier</span><span class="sxs-lookup"><span data-stu-id="4eaa0-142">Console API output in Microsoft Edge 85 or earlier</span></span>  
      :::image-end:::  
   :::column-end:::  
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/console-table-beta-paste-visual-studio-code.msft.png" alt-text="Match keyboard shortcuts in the DevTools to Visual Studio Code" lightbox="../../media/2020/08/console-table-beta-paste-visual-studio-code.msft.png":::
         `table` <span data-ttu-id="4eaa0-144">Console API output from Microsoft Edge 85 or earlier pasted into Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="4eaa0-144">Console API output from Microsoft Edge 85 or earlier pasted into Visual Studio Code</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="4eaa0-145">In Microsoft Edge 86 or later, when you copy a table from the **Console**, the formatting is now preserved.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-145">In Microsoft Edge 86 or later, when you copy a table from the **Console**, the formatting is now preserved.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/console-table-canary.msft.png" alt-text="Match keyboard shortcuts in the DevTools to Visual Studio Code" lightbox="../../media/2020/08/console-table-canary.msft.png":::
         `table` <span data-ttu-id="4eaa0-147">Console API output in Microsoft Edge 86 or later</span><span class="sxs-lookup"><span data-stu-id="4eaa0-147">Console API output in Microsoft Edge 86 or later</span></span>  
      :::image-end:::  
   :::column-end:::  
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/console-table-canary-paste-visual-studio-code.msft.png" alt-text="Match keyboard shortcuts in the DevTools to Visual Studio Code" lightbox="../../media/2020/08/console-table-canary-paste-visual-studio-code.msft.png":::
         `table` <span data-ttu-id="4eaa0-149">Console API output from Microsoft Edge 86 or later pasted into Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="4eaa0-149">Console API output from Microsoft Edge 86 or later pasted into Visual Studio Code</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="4eaa0-150">Chromium issue: [#1115011][CR1115011]</span><span class="sxs-lookup"><span data-stu-id="4eaa0-150">Chromium issue: [#1115011][CR1115011]</span></span>  

### <span data-ttu-id="4eaa0-151">Source Order Viewer for easier accessibility testing</span><span class="sxs-lookup"><span data-stu-id="4eaa0-151">Source Order Viewer for easier accessibility testing</span></span>  

:::image type="complex" source="../../media/2020/06/experimental-tag-14px.msft.png" alt-text="Match keyboard shortcuts in the DevTools to Visual Studio Code":::
   <span data-ttu-id="4eaa0-153">Experimental feature</span><span class="sxs-lookup"><span data-stu-id="4eaa0-153">Experimental feature</span></span>  
:::image-end:::  

<span data-ttu-id="4eaa0-154">The new accessibility helper displays the order of elements in the source.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-154">The new accessibility helper displays the order of elements in the source.</span></span>  

:::image type="complex" source="../../media/2020/08/source-order-viewer.msft.png" alt-text="Match keyboard shortcuts in the DevTools to Visual Studio Code" lightbox="../../media/2020/08/source-order-viewer.msft.png":::
   <span data-ttu-id="4eaa0-156">Activate **Show source order**</span><span class="sxs-lookup"><span data-stu-id="4eaa0-156">Activate **Show source order**</span></span>  
:::image-end:::  

<span data-ttu-id="4eaa0-157">This feature makes it easier to test the way screen reader and keyboard users experience your website or app.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-157">This feature makes it easier to test the way screen reader and keyboard users experience your website or app.</span></span>  <span data-ttu-id="4eaa0-158">Screen readers and keyboard navigation depend on content being placed in a particular order in the source code of your website or app, so that it matches the rendered page.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-158">Screen readers and keyboard navigation depend on content being placed in a particular order in the source code of your website or app, so that it matches the rendered page.</span></span>  <span data-ttu-id="4eaa0-159">The Source Order Viewer displays potential differences in order between the rendered page and the source code.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-159">The Source Order Viewer displays potential differences in order between the rendered page and the source code.</span></span>  

<span data-ttu-id="4eaa0-160">To turn on this experimental feature, navigate to [Turn on experimental features][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures] and choose the checkbox next to **Enable Source Order Viewer**.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-160">To turn on this experimental feature, navigate to [Turn on experimental features][DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures] and choose the checkbox next to **Enable Source Order Viewer**.</span></span>  

<span data-ttu-id="4eaa0-161">For more information about this experiment, navigate to [Enable Source Order Viewer][DevtoolsExperimentalFeaturesEnableSourceOrderViewer].</span><span class="sxs-lookup"><span data-stu-id="4eaa0-161">For more information about this experiment, navigate to [Enable Source Order Viewer][DevtoolsExperimentalFeaturesEnableSourceOrderViewer].</span></span>  

<span data-ttu-id="4eaa0-162">Chromium issue: [#1094406][CR1094406]</span><span class="sxs-lookup"><span data-stu-id="4eaa0-162">Chromium issue: [#1094406][CR1094406]</span></span>  

<!--
### DevTools language enhancements  

Your feedback and internal discoveries uncovered which text strings used in the Microsoft Edge feedback should remain untranslated or create confusion when translated.  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/localization-improvements-chinese-complex-stable.msft.png" alt-text="Match keyboard shortcuts in the DevTools to Visual Studio Code" lightbox="localization-improvements-chinese-complex-stable.msft.png":::
         Microsoft Edge DevTools 85 and earlier in Traditional Chinese  
      :::image-end:::  
   :::column-end:::  
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/localization-improvements-chinese-complex-canary.msft.png" alt-text="Match keyboard shortcuts in the DevTools to Visual Studio Code" lightbox="../../media/2020/08/localization-improvements-chinese-complex-canary.msft.png":::
         Microsoft Edge DevTools 86  or later in Traditional Chinese  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

To meet your translation needs, the Microsoft Edge DevTools team is focused on improving translation quality.  

The current effort to improve translation quality enables easier support for more languages in the future.  
-->  

### <span data-ttu-id="4eaa0-163">Highlight all search results in Elements tool</span><span class="sxs-lookup"><span data-stu-id="4eaa0-163">Highlight all search results in Elements tool</span></span>  

<span data-ttu-id="4eaa0-164">In Microsoft Edge 84 and 85, the first search result in the **Elements** panel did not highlight.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-164">In Microsoft Edge 84 and 85, the first search result in the **Elements** panel did not highlight.</span></span>  <span data-ttu-id="4eaa0-165">The remaining search results were highlighted correctly.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-165">The remaining search results were highlighted correctly.</span></span>  

<span data-ttu-id="4eaa0-166">Thank you for sending your feedback and helping improve Chromium.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-166">Thank you for sending your feedback and helping improve Chromium.</span></span>  <span data-ttu-id="4eaa0-167">Your feedback uncovered Issue [#1103316][CR1103316] in the open-source Chromium project.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-167">Your feedback uncovered Issue [#1103316][CR1103316] in the open-source Chromium project.</span></span>  

:::image type="complex" source="../../media/2020/08/elements- search-highlight-fixed.msft.png" alt-text="Match keyboard shortcuts in the DevTools to Visual Studio Code" lightbox="../../media/2020/08/elements- search-highlight-fixed.msft.png":::
   <span data-ttu-id="4eaa0-169">Highlighted first search result on **Elements** panel in Microsoft Edge 84 or later</span><span class="sxs-lookup"><span data-stu-id="4eaa0-169">Highlighted first search result on **Elements** panel in Microsoft Edge 84 or later</span></span>  
:::image-end:::  

<span data-ttu-id="4eaa0-170">The issue is now fixed in all versions of Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-170">The issue is now fixed in all versions of Microsoft Edge.</span></span>  

<span data-ttu-id="4eaa0-171">Chromium issue: [#1103316][CR1103316]</span><span class="sxs-lookup"><span data-stu-id="4eaa0-171">Chromium issue: [#1103316][CR1103316]</span></span>  

## <span data-ttu-id="4eaa0-172">Announcements from the Chromium project</span><span class="sxs-lookup"><span data-stu-id="4eaa0-172">Announcements from the Chromium project</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/chromium-whats-new-note.md)]  

### <span data-ttu-id="4eaa0-173">New Media panel</span><span class="sxs-lookup"><span data-stu-id="4eaa0-173">New Media panel</span></span>  

<span data-ttu-id="4eaa0-174">DevTools now displays media players information in the [Media][DevtoolsMediaIndex] panel.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-174">DevTools now displays media players information in the [Media][DevtoolsMediaIndex] panel.</span></span>  

<span data-ttu-id="4eaa0-175">To open the new **Media** panel, complete the following step.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-175">To open the new **Media** panel, complete the following step.</span></span>  

1.  <span data-ttu-id="4eaa0-176">Choose **Customize and control DevTools** \(`...`\) > **More tools** > **Media**.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-176">Choose **Customize and control DevTools** \(`...`\) > **More tools** > **Media**.</span></span>  
    
    :::image type="complex" source="../../media/2020/08/media-panel.msft.png" alt-text="Match keyboard shortcuts in the DevTools to Visual Studio Code" lightbox="../../media/2020/08/media-panel.msft.png":::
       <span data-ttu-id="4eaa0-178">New **Media** panel</span><span class="sxs-lookup"><span data-stu-id="4eaa0-178">New **Media** panel</span></span>  
    :::image-end:::  

<span data-ttu-id="4eaa0-179">Before the new **Media** panel in DevTools, the logging and debug information about video players was located under the **Recent Players** setting.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-179">Before the new **Media** panel in DevTools, the logging and debug information about video players was located under the **Recent Players** setting.</span></span>  <span data-ttu-id="4eaa0-180">To open the **Recent Players** setting, go to `edge://media-internals` and choose the **Players** tab.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-180">To open the **Recent Players** setting, go to `edge://media-internals` and choose the **Players** tab.</span></span>  

<span data-ttu-id="4eaa0-181">View live content and inspect potential issues more quickly, including the following examples.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-181">View live content and inspect potential issues more quickly, including the following examples.</span></span>  

*   <span data-ttu-id="4eaa0-182">Why frames are dropped?</span><span class="sxs-lookup"><span data-stu-id="4eaa0-182">Why frames are dropped?</span></span>  
*   <span data-ttu-id="4eaa0-183">Why JavaScript is interacting with the player in an unexpected way?</span><span class="sxs-lookup"><span data-stu-id="4eaa0-183">Why JavaScript is interacting with the player in an unexpected way?</span></span>  

### <span data-ttu-id="4eaa0-184">Capture node screenshots using the Elements panel context menu</span><span class="sxs-lookup"><span data-stu-id="4eaa0-184">Capture node screenshots using the Elements panel context menu</span></span>  

<span data-ttu-id="4eaa0-185">You may now capture node screenshots using the context menu in the **Elements** panel.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-185">You may now capture node screenshots using the context menu in the **Elements** panel.</span></span>  

<span data-ttu-id="4eaa0-186">For example, to take a screenshot of the table of contents, hover on the element, open the contextual menu \(right-click\), and select **Capture node screenshot**.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-186">For example, to take a screenshot of the table of contents, hover on the element, open the contextual menu \(right-click\), and select **Capture node screenshot**.</span></span>  

:::image type="complex" source="../../media/2020/08/capture-node-screenshot.msft.png" alt-text="Match keyboard shortcuts in the DevTools to Visual Studio Code" lightbox="../../media/2020/08/capture-node-screenshot.msft.png":::
   <span data-ttu-id="4eaa0-188">Capture node screenshots</span><span class="sxs-lookup"><span data-stu-id="4eaa0-188">Capture node screenshots</span></span>  
:::image-end:::  

<span data-ttu-id="4eaa0-189">Chromium issue: [#1100253][CR1100253]</span><span class="sxs-lookup"><span data-stu-id="4eaa0-189">Chromium issue: [#1100253][CR1100253]</span></span>  

### <span data-ttu-id="4eaa0-190">Issues tool updates</span><span class="sxs-lookup"><span data-stu-id="4eaa0-190">Issues tool updates</span></span>  

<span data-ttu-id="4eaa0-191">The Issues warning bar on the **Console** panel is now replaced with a regular message.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-191">The Issues warning bar on the **Console** panel is now replaced with a regular message.</span></span>  

<!--todo: this figure need to be updated  -->  

:::image type="complex" source="../../media/2020/08/issue-console-msg.msft.png" alt-text="Match keyboard shortcuts in the DevTools to Visual Studio Code" lightbox="../../media/2020/08/issue-console-msg.msft.png":::
   <span data-ttu-id="4eaa0-193">Issues in console message</span><span class="sxs-lookup"><span data-stu-id="4eaa0-193">Issues in console message</span></span>  
:::image-end:::  

<span data-ttu-id="4eaa0-194">Third-party cookie issues are now hidden by default in the **Issues** tool.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-194">Third-party cookie issues are now hidden by default in the **Issues** tool.</span></span>  <span data-ttu-id="4eaa0-195">Enable the new **Include third-party cookie issues** checkbox to view the issues.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-195">Enable the new **Include third-party cookie issues** checkbox to view the issues.</span></span>  

:::image type="complex" source="../../media/2020/08/third-party-cookies.msft.png" alt-text="Match keyboard shortcuts in the DevTools to Visual Studio Code" lightbox="../../media/2020/08/third-party-cookies.msft.png":::
   <span data-ttu-id="4eaa0-197">third-party cookie issues checkbox</span><span class="sxs-lookup"><span data-stu-id="4eaa0-197">third-party cookie issues checkbox</span></span>  
:::image-end:::  

<span data-ttu-id="4eaa0-198">Chromium issues: [1096481][CR1096481], [1068116][CR1068116], [1080589][CR1080589]</span><span class="sxs-lookup"><span data-stu-id="4eaa0-198">Chromium issues: [1096481][CR1096481], [1068116][CR1068116], [1080589][CR1080589]</span></span>  

### <span data-ttu-id="4eaa0-199">Emulate missing local fonts</span><span class="sxs-lookup"><span data-stu-id="4eaa0-199">Emulate missing local fonts</span></span>  

<span data-ttu-id="4eaa0-200">Open the [Rendering tool][DevtoolsEvaluatePerformanceReferenceAnalyzeRenderingPerformance] and use the new **Disable local fonts** feature to emulate missing `local()` sources in `@font-face` rules.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-200">Open the [Rendering tool][DevtoolsEvaluatePerformanceReferenceAnalyzeRenderingPerformance] and use the new **Disable local fonts** feature to emulate missing `local()` sources in `@font-face` rules.</span></span>  

<span data-ttu-id="4eaa0-201">For example, when the `Rubik` font is installed on your device and the `@font-face src` rule uses it as a `local()` font, Microsoft Edge uses the local font file from your device.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-201">For example, when the `Rubik` font is installed on your device and the `@font-face src` rule uses it as a `local()` font, Microsoft Edge uses the local font file from your device.</span></span>  

<span data-ttu-id="4eaa0-202">When **Disable local fonts** is enabled, DevTools ignores the `local()` fonts and fetches each from the network.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-202">When **Disable local fonts** is enabled, DevTools ignores the `local()` fonts and fetches each from the network.</span></span>  

:::image type="complex" source="../../media/2020/08/disable-font.msft.png" alt-text="Match keyboard shortcuts in the DevTools to Visual Studio Code" lightbox="../../media/2020/08/disable-font.msft.png":::
   <span data-ttu-id="4eaa0-204">Emulate missing local fonts</span><span class="sxs-lookup"><span data-stu-id="4eaa0-204">Emulate missing local fonts</span></span>  
:::image-end:::  

<span data-ttu-id="4eaa0-205">If you use two different copies of the same font during development, such as the following examples.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-205">If you use two different copies of the same font during development, such as the following examples.</span></span>  

*   <span data-ttu-id="4eaa0-206">A local font for your design tools.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-206">A local font for your design tools.</span></span>  
*   <span data-ttu-id="4eaa0-207">A web font for your code.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-207">A web font for your code.</span></span>  

<span data-ttu-id="4eaa0-208">Use **Disable local fonts** to make it easier for you to complete the following tasks.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-208">Use **Disable local fonts** to make it easier for you to complete the following tasks.</span></span>  

*   <span data-ttu-id="4eaa0-209">Debug and measure loading performance and optimization of web fonts.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-209">Debug and measure loading performance and optimization of web fonts.</span></span>  
*   <span data-ttu-id="4eaa0-210">Verify accuracy of your CSS `@font-face` rules.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-210">Verify accuracy of your CSS `@font-face` rules.</span></span>  
*   <span data-ttu-id="4eaa0-211">Discover differences between local versions installed on your device and a web font.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-211">Discover differences between local versions installed on your device and a web font.</span></span>  

<span data-ttu-id="4eaa0-212">Chromium issue: [#384968][CR384968]</span><span class="sxs-lookup"><span data-stu-id="4eaa0-212">Chromium issue: [#384968][CR384968]</span></span>  

### <span data-ttu-id="4eaa0-213">Emulate inactive users</span><span class="sxs-lookup"><span data-stu-id="4eaa0-213">Emulate inactive users</span></span>  

<span data-ttu-id="4eaa0-214">The [Idle Detection API][WebDevIdleDetection] allows developers to detect inactive users and react on idle state changes.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-214">The [Idle Detection API][WebDevIdleDetection] allows developers to detect inactive users and react on idle state changes.</span></span>  <span data-ttu-id="4eaa0-215">You are now able to use DevTools to emulate idle state changes in the **Sensors** tool for both the user state and the screen state instead of waiting for the actual idle state to change.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-215">You are now able to use DevTools to emulate idle state changes in the **Sensors** tool for both the user state and the screen state instead of waiting for the actual idle state to change.</span></span>  <span data-ttu-id="4eaa0-216">You may open the **Sensors** tool from the [Drawer][DevtoolsCustomizeIndexDrawer].</span><span class="sxs-lookup"><span data-stu-id="4eaa0-216">You may open the **Sensors** tool from the [Drawer][DevtoolsCustomizeIndexDrawer].</span></span>  

:::image type="complex" source="../../media/2020/08/emulate-idle.msft.png" alt-text="Match keyboard shortcuts in the DevTools to Visual Studio Code" lightbox="../../media/2020/08/emulate-idle.msft.png":::
   <span data-ttu-id="4eaa0-218">Emulate inactive users</span><span class="sxs-lookup"><span data-stu-id="4eaa0-218">Emulate inactive users</span></span>  
:::image-end:::  

<span data-ttu-id="4eaa0-219">Chromium issue: [#1090802][CR1090802]</span><span class="sxs-lookup"><span data-stu-id="4eaa0-219">Chromium issue: [#1090802][CR1090802]</span></span>  

### <span data-ttu-id="4eaa0-220">Emulate prefers-reduced-data</span><span class="sxs-lookup"><span data-stu-id="4eaa0-220">Emulate prefers-reduced-data</span></span>  

> [!NOTE]
> <span data-ttu-id="4eaa0-221">In Microsoft Edge 86, to enable this feature, go to `edge://flags#enable-experimental-web-platform-features` and turn on the **Experimental Web Platform features** flag.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-221">In Microsoft Edge 86, to enable this feature, go to `edge://flags#enable-experimental-web-platform-features` and turn on the **Experimental Web Platform features** flag.</span></span>  <span data-ttu-id="4eaa0-222">The emulation option is only displayed if the flag is enabled.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-222">The emulation option is only displayed if the flag is enabled.</span></span>  

<span data-ttu-id="4eaa0-223">The [prefers-reduced-data][CsswgDraftsMediaqueries5DescdefMediaPrefersReducedData] media query detects user content preferences for reduced data.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-223">The [prefers-reduced-data][CsswgDraftsMediaqueries5DescdefMediaPrefersReducedData] media query detects user content preferences for reduced data.</span></span>  <span data-ttu-id="4eaa0-224">If selected, the user receives alternate page content that uses less data.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-224">If selected, the user receives alternate page content that uses less data.</span></span>  

<span data-ttu-id="4eaa0-225">You may now use DevTools to emulate the `prefers-reduced-data` media query.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-225">You may now use DevTools to emulate the `prefers-reduced-data` media query.</span></span>  

:::image type="complex" source="../../media/2020/08/emulate-prefers-reduced-data.msft.png" alt-text="Match keyboard shortcuts in the DevTools to Visual Studio Code" lightbox="../../media/2020/08/emulate-prefers-reduced-data.msft.png":::
   <span data-ttu-id="4eaa0-227">Emulate prefers-reduced-data</span><span class="sxs-lookup"><span data-stu-id="4eaa0-227">Emulate prefers-reduced-data</span></span>  
:::image-end:::  

<span data-ttu-id="4eaa0-228">Chromium issue: [#1096068][CR1096068]</span><span class="sxs-lookup"><span data-stu-id="4eaa0-228">Chromium issue: [#1096068][CR1096068]</span></span>  

### <span data-ttu-id="4eaa0-229">Support for new JavaScript features</span><span class="sxs-lookup"><span data-stu-id="4eaa0-229">Support for new JavaScript features</span></span>  

<span data-ttu-id="4eaa0-230">DevTools now have better supported the following JavaScript language features.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-230">DevTools now have better supported the following JavaScript language features.</span></span>  

| <span data-ttu-id="4eaa0-231">JavaScript language feature</span><span class="sxs-lookup"><span data-stu-id="4eaa0-231">JavaScript language feature</span></span> | <span data-ttu-id="4eaa0-232">Details</span><span class="sxs-lookup"><span data-stu-id="4eaa0-232">Details</span></span> |  
|:--- |:--- |  
| [<span data-ttu-id="4eaa0-233">Logical assignment operators</span><span class="sxs-lookup"><span data-stu-id="4eaa0-233">Logical assignment operators</span></span>][V8FeaturesLogicalAssignment] | <span data-ttu-id="4eaa0-234">DevTools now supports logical assignment with the new `&&=`, `||=`, and `??=` operators in the **Console** and **Sources** panels.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-234">DevTools now supports logical assignment with the new `&&=`, `||=`, and `??=` operators in the **Console** and **Sources** panels.</span></span>  |  
| <span data-ttu-id="4eaa0-235">Pretty-print [numeric separators][V8FeaturesNumericSeparators]</span><span class="sxs-lookup"><span data-stu-id="4eaa0-235">Pretty-print [numeric separators][V8FeaturesNumericSeparators]</span></span> | <span data-ttu-id="4eaa0-236">DevTools now properly pretty-prints the numeric separators in the **Sources** panel.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-236">DevTools now properly pretty-prints the numeric separators in the **Sources** panel.</span></span>  |  

<span data-ttu-id="4eaa0-237">Chromium issues: [1086817][CR1086817], [1080569][CR1080569]</span><span class="sxs-lookup"><span data-stu-id="4eaa0-237">Chromium issues: [1086817][CR1086817], [1080569][CR1080569]</span></span>  

### <span data-ttu-id="4eaa0-238">Lighthouse 6.2 in the Lighthouse panel</span><span class="sxs-lookup"><span data-stu-id="4eaa0-238">Lighthouse 6.2 in the Lighthouse panel</span></span>  

<span data-ttu-id="4eaa0-239">The **Lighthouse** panel is now running Lighthouse 6.2.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-239">The **Lighthouse** panel is now running Lighthouse 6.2.</span></span>  <span data-ttu-id="4eaa0-240">For a full list of changes, go to the [Lighthouse release notes][GithubGooglechromeLighthouseV620].</span><span class="sxs-lookup"><span data-stu-id="4eaa0-240">For a full list of changes, go to the [Lighthouse release notes][GithubGooglechromeLighthouseV620].</span></span>  

<span data-ttu-id="4eaa0-241">Chromium issue: [#772558][CR772558]</span><span class="sxs-lookup"><span data-stu-id="4eaa0-241">Chromium issue: [#772558][CR772558]</span></span>  

### <span data-ttu-id="4eaa0-242">Deprecation of other origins listing in the Service Workers pane</span><span class="sxs-lookup"><span data-stu-id="4eaa0-242">Deprecation of other origins listing in the Service Workers pane</span></span>  

<span data-ttu-id="4eaa0-243">DevTools now provides a link from the **Service workers** pane \(**Application** panel > **Service workers** pane\) to view the full list of service workers from other origins.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-243">DevTools now provides a link from the **Service workers** pane \(**Application** panel > **Service workers** pane\) to view the full list of service workers from other origins.</span></span>  <span data-ttu-id="4eaa0-244">To access the list without opening the DevTools, go to `edge://service-worker-internals/?devtools`.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-244">To access the list without opening the DevTools, go to `edge://service-worker-internals/?devtools`.</span></span>  

<span data-ttu-id="4eaa0-245">Previously DevTools displayed a list nested under the **Application** panel > **Service workers** pane.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-245">Previously DevTools displayed a list nested under the **Application** panel > **Service workers** pane.</span></span>  

:::image type="complex" source="../../media/2020/08/sw-other-origins.msft.png" alt-text="Match keyboard shortcuts in the DevTools to Visual Studio Code" lightbox="../../media/2020/08/sw-other-origins.msft.png":::
   <span data-ttu-id="4eaa0-247">Link to other origins</span><span class="sxs-lookup"><span data-stu-id="4eaa0-247">Link to other origins</span></span>  
:::image-end:::  

<span data-ttu-id="4eaa0-248">Chromium issue: [#807440][CR807440]</span><span class="sxs-lookup"><span data-stu-id="4eaa0-248">Chromium issue: [#807440][CR807440]</span></span>  

### <span data-ttu-id="4eaa0-249">Show coverage summary for filtered items</span><span class="sxs-lookup"><span data-stu-id="4eaa0-249">Show coverage summary for filtered items</span></span>  

<span data-ttu-id="4eaa0-250">DevTools now recalculate and display a summary of coverage information dynamically.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-250">DevTools now recalculate and display a summary of coverage information dynamically.</span></span>  <span data-ttu-id="4eaa0-251">The dynamic display is triggered when filters are applied in the [Coverage][DevtoolsCoverageIndex] tool.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-251">The dynamic display is triggered when filters are applied in the [Coverage][DevtoolsCoverageIndex] tool.</span></span>  <span data-ttu-id="4eaa0-252">Before the **Coverage** tool always displayed a summary of all coverage information.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-252">Before the **Coverage** tool always displayed a summary of all coverage information.</span></span>  

<span data-ttu-id="4eaa0-253">In the first of the following figures, the summary initially displays `344 kB of 1.7 MB (20%) used so far.  1.4 MB unused.` and in the second of the following figures, the summary displays `26.8 kB of 408 kB (7%) used so far.  381 kB unused.` after CSS filtering is applied.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-253">In the first of the following figures, the summary initially displays `344 kB of 1.7 MB (20%) used so far.  1.4 MB unused.` and in the second of the following figures, the summary displays `26.8 kB of 408 kB (7%) used so far.  381 kB unused.` after CSS filtering is applied.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/coverage-compare.msft.png" alt-text="Match keyboard shortcuts in the DevTools to Visual Studio Code" lightbox="../../media/2020/08/coverage-compare.msft.png":::
         <span data-ttu-id="4eaa0-255">Coverage summary</span><span class="sxs-lookup"><span data-stu-id="4eaa0-255">Coverage summary</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/coverage-compare-css-filter.msft.png" alt-text="Match keyboard shortcuts in the DevTools to Visual Studio Code" lightbox="../../media/2020/08/coverage-compare-css-filter.msft.png":::
         <span data-ttu-id="4eaa0-257">Coverage summary for filtered items</span><span class="sxs-lookup"><span data-stu-id="4eaa0-257">Coverage summary for filtered items</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::

<span data-ttu-id="4eaa0-258">Chromium issue: [#1061385][CR1090802]</span><span class="sxs-lookup"><span data-stu-id="4eaa0-258">Chromium issue: [#1061385][CR1090802]</span></span>  

### <span data-ttu-id="4eaa0-259">New frame details view in Application panel</span><span class="sxs-lookup"><span data-stu-id="4eaa0-259">New frame details view in Application panel</span></span>  

<span data-ttu-id="4eaa0-260">DevTools now show a detailed view for each frame.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-260">DevTools now show a detailed view for each frame.</span></span>  <span data-ttu-id="4eaa0-261">To access it, choose a frame under the **Frames** menu in the **Application** panel.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-261">To access it, choose a frame under the **Frames** menu in the **Application** panel.</span></span>  

:::image type="complex" source="../../media/2020/08/frame-details.msft.png" alt-text="Match keyboard shortcuts in the DevTools to Visual Studio Code" lightbox="../../media/2020/08/frame-details.msft.png":::
   <span data-ttu-id="4eaa0-263">New detailed view for a frame in **Application** panel</span><span class="sxs-lookup"><span data-stu-id="4eaa0-263">New detailed view for a frame in **Application** panel</span></span>  
:::image-end:::  

<span data-ttu-id="4eaa0-264">Chromium issue: [#1093247][CR1093247]</span><span class="sxs-lookup"><span data-stu-id="4eaa0-264">Chromium issue: [#1093247][CR1093247]</span></span>  

#### <span data-ttu-id="4eaa0-265">Frame details for opened windows</span><span class="sxs-lookup"><span data-stu-id="4eaa0-265">Frame details for opened windows</span></span>  

<span data-ttu-id="4eaa0-266">Open windows and pop-up windows now display under the frame tree as well.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-266">Open windows and pop-up windows now display under the frame tree as well.</span></span>  <span data-ttu-id="4eaa0-267">The detailed view of the opened windows includes additional security information.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-267">The detailed view of the opened windows includes additional security information.</span></span>  

:::image type="complex" source="../../media/2020/08/window-opener.msft.png" alt-text="Match keyboard shortcuts in the DevTools to Visual Studio Code" lightbox="../../media/2020/08/window-opener.msft.png":::
   <span data-ttu-id="4eaa0-269">New frame detailed view for opened windows</span><span class="sxs-lookup"><span data-stu-id="4eaa0-269">New frame detailed view for opened windows</span></span>  
:::image-end:::  

<span data-ttu-id="4eaa0-270">Chromium issue: [#1107766][CR1107766]</span><span class="sxs-lookup"><span data-stu-id="4eaa0-270">Chromium issue: [#1107766][CR1107766]</span></span>  

#### <span data-ttu-id="4eaa0-271">Security and isolation information</span><span class="sxs-lookup"><span data-stu-id="4eaa0-271">Security and isolation information</span></span>  

<span data-ttu-id="4eaa0-272">Secure context, [Cross-Origin-Embedder-Policy (COEP)][WebDevCoopCoep], and [Cross-Origin-Opener-Policy (COOP)][WebDevCoopCoep] are now displayed in the frame details.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-272">Secure context, [Cross-Origin-Embedder-Policy (COEP)][WebDevCoopCoep], and [Cross-Origin-Opener-Policy (COOP)][WebDevCoopCoep] are now displayed in the frame details.</span></span>  

:::image type="complex" source="../../media/2020/08/coep-coop.msft.png" alt-text="Match keyboard shortcuts in the DevTools to Visual Studio Code" lightbox="../../media/2020/08/coep-coop.msft.png":::
   <span data-ttu-id="4eaa0-274">Security and isolation information</span><span class="sxs-lookup"><span data-stu-id="4eaa0-274">Security and isolation information</span></span>  
:::image-end:::  

<span data-ttu-id="4eaa0-275">In the future, the Microsoft Edge DevTools team and the Chrome DevTools team are planning to add more security information to the frame details.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-275">In the future, the Microsoft Edge DevTools team and the Chrome DevTools team are planning to add more security information to the frame details.</span></span>  

<span data-ttu-id="4eaa0-276">Chromium issue: [#1051466][CR1051466]</span><span class="sxs-lookup"><span data-stu-id="4eaa0-276">Chromium issue: [#1051466][CR1051466]</span></span>  

### <span data-ttu-id="4eaa0-277">Elements and Network panel updates</span><span class="sxs-lookup"><span data-stu-id="4eaa0-277">Elements and Network panel updates</span></span>  

#### <span data-ttu-id="4eaa0-278">Accessible color suggestion in the Styles pane</span><span class="sxs-lookup"><span data-stu-id="4eaa0-278">Accessible color suggestion in the Styles pane</span></span>  

<span data-ttu-id="4eaa0-279">DevTools now provides color suggestions for low color contrast text.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-279">DevTools now provides color suggestions for low color contrast text.</span></span>  

<span data-ttu-id="4eaa0-280">In the example below, `h1` has low contrast text.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-280">In the example below, `h1` has low contrast text.</span></span>  <span data-ttu-id="4eaa0-281">To fix it, open the color picker of the `color` property in the **Styles** pane.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-281">To fix it, open the color picker of the `color` property in the **Styles** pane.</span></span>  <span data-ttu-id="4eaa0-282">After you expand the **Contrast ratio** section, DevTools provides AA and AAA color suggestions.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-282">After you expand the **Contrast ratio** section, DevTools provides AA and AAA color suggestions.</span></span>  <span data-ttu-id="4eaa0-283">Select the suggested color to apply the color.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-283">Select the suggested color to apply the color.</span></span>  

:::image type="complex" source="../../media/2020/08/contrast-color-suggestion.msft.png" alt-text="Match keyboard shortcuts in the DevTools to Visual Studio Code" lightbox="../../media/2020/08/contrast-color-suggestion.msft.png":::
   <span data-ttu-id="4eaa0-285">Color picker suggests AA and AAA color suggestions</span><span class="sxs-lookup"><span data-stu-id="4eaa0-285">Color picker suggests AA and AAA color suggestions</span></span>  
:::image-end:::  

<span data-ttu-id="4eaa0-286">Chromium issue: [#1093227][CR1093227]</span><span class="sxs-lookup"><span data-stu-id="4eaa0-286">Chromium issue: [#1093227][CR1093227]</span></span>  

#### <span data-ttu-id="4eaa0-287">Reinstate Properties pane in the Elements panel</span><span class="sxs-lookup"><span data-stu-id="4eaa0-287">Reinstate Properties pane in the Elements panel</span></span>  

<span data-ttu-id="4eaa0-288">The **Properties** pane is back.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-288">The **Properties** pane is back.</span></span>  <span data-ttu-id="4eaa0-289">It was [deprecated in Microsoft Edge 84][DevtoolsWhatsnew200205DevtoolsDeprecationPropertiesPaneElementsPanel].</span><span class="sxs-lookup"><span data-stu-id="4eaa0-289">It was [deprecated in Microsoft Edge 84][DevtoolsWhatsnew200205DevtoolsDeprecationPropertiesPaneElementsPanel].</span></span>  <span data-ttu-id="4eaa0-290">The Microsoft Edge DevTools team and the Chrome DevTools team are planning improvements for inspecting properties of elements.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-290">The Microsoft Edge DevTools team and the Chrome DevTools team are planning improvements for inspecting properties of elements.</span></span>  

:::image type="complex" source="../../media/2020/08/properties-pane.msft.png" alt-text="Match keyboard shortcuts in the DevTools to Visual Studio Code" lightbox="../../media/2020/08/properties-pane.msft.png":::
   <span data-ttu-id="4eaa0-292">**Properties** pane in the **Elements** panel</span><span class="sxs-lookup"><span data-stu-id="4eaa0-292">**Properties** pane in the **Elements** panel</span></span>  
:::image-end:::  

<span data-ttu-id="4eaa0-293">Chromium issue:</span><span class="sxs-lookup"><span data-stu-id="4eaa0-293">Chromium issue:</span></span>  <!--  [#1105205][CR1105205],  -->  <span data-ttu-id="4eaa0-294">[#1116085][CR1116085]</span><span class="sxs-lookup"><span data-stu-id="4eaa0-294">[#1116085][CR1116085]</span></span>  

<!--  
#### Human-readable X-Client-Data header values in the Network panel  

When inspecting a network resource in the Network panel, DevTools now formats any `X-Client-Data` header values in **Headers** pane as code.  

The `X-Client-Data` HTTP header contains a list of experiment IDs and Microsoft Edge flags that are enabled in your browser.  The raw header values look like opaque strings since the values are `base-64-encoded`, serialized [protocol buffers][GoogleDevelopersProtocolBuffers].  To make the contents more transparent to developers, DevTools now shows the decoded values.  

:::image type="complex" source="../../media/2020/08/x-client-data.msft.png" alt-text="Match keyboard shortcuts in the DevTools to Visual Studio Code" lightbox="../../media/2020/08/x-client-data.msft.png":::
   Human-readable `X-Client-Data` header values  
:::image-end:::  

Chromium issue: [#1103854][CR1103854]  
-->  

#### <span data-ttu-id="4eaa0-295">Autocomplete custom fonts in the Styles pane</span><span class="sxs-lookup"><span data-stu-id="4eaa0-295">Autocomplete custom fonts in the Styles pane</span></span>  

<span data-ttu-id="4eaa0-296">Imported font faces are now added to the list of CSS autocompletion when editing the `font-family` property in the **Styles** pane.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-296">Imported font faces are now added to the list of CSS autocompletion when editing the `font-family` property in the **Styles** pane.</span></span>  

<span data-ttu-id="4eaa0-297">For example, if `monospace` is a custom font installed on the local machine, it's displayed in the CSS completion list.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-297">For example, if `monospace` is a custom font installed on the local machine, it's displayed in the CSS completion list.</span></span> <span data-ttu-id="4eaa0-298">In previous versions of Microsoft Edge, the font wasn't displayed.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-298">In previous versions of Microsoft Edge, the font wasn't displayed.</span></span>

:::image type="complex" source="../../media/2020/08/font-auto-complete.msft.png" alt-text="Match keyboard shortcuts in the DevTools to Visual Studio Code" lightbox="../../media/2020/08/font-auto-complete.msft.png":::
   <span data-ttu-id="4eaa0-300">Autocomplete custom fonts</span><span class="sxs-lookup"><span data-stu-id="4eaa0-300">Autocomplete custom fonts</span></span>  
:::image-end:::  

<span data-ttu-id="4eaa0-301">Chromium issue: [#1106221][CR1106221]</span><span class="sxs-lookup"><span data-stu-id="4eaa0-301">Chromium issue: [#1106221][CR1106221]</span></span>  

#### <span data-ttu-id="4eaa0-302">Consistently display resource type in Network panel</span><span class="sxs-lookup"><span data-stu-id="4eaa0-302">Consistently display resource type in Network panel</span></span>  

<span data-ttu-id="4eaa0-303">DevTools now consistently display the same resource type as the original network request and appends `/ Redirect` to the **Type** column value when redirection \(HTTP status code 302\) happens.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-303">DevTools now consistently display the same resource type as the original network request and appends `/ Redirect` to the **Type** column value when redirection \(HTTP status code 302\) happens.</span></span>  

<span data-ttu-id="4eaa0-304">Previously DevTools changed the type to `Other` sometimes.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-304">Previously DevTools changed the type to `Other` sometimes.</span></span>  

:::image type="complex" source="../../media/2020/08/network-redirect.msft.png" alt-text="Match keyboard shortcuts in the DevTools to Visual Studio Code" lightbox="../../media/2020/08/network-redirect.msft.png":::
   <span data-ttu-id="4eaa0-306">Display redirect resource type</span><span class="sxs-lookup"><span data-stu-id="4eaa0-306">Display redirect resource type</span></span>  
:::image-end:::  

<span data-ttu-id="4eaa0-307">Chromium issue: [#997694][CR997694]</span><span class="sxs-lookup"><span data-stu-id="4eaa0-307">Chromium issue: [#997694][CR997694]</span></span>  

#### <span data-ttu-id="4eaa0-308">Clear buttons in the Elements and Network panels</span><span class="sxs-lookup"><span data-stu-id="4eaa0-308">Clear buttons in the Elements and Network panels</span></span>  

<span data-ttu-id="4eaa0-309">The following text boxes now have **Clear** buttons.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-309">The following text boxes now have **Clear** buttons.</span></span>  

*   <span data-ttu-id="4eaa0-310">The filter text boxes in the **Styles** pane and **Network** panel.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-310">The filter text boxes in the **Styles** pane and **Network** panel.</span></span>  
*   <span data-ttu-id="4eaa0-311">The DOM search text box in the **Elements** panel.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-311">The DOM search text box in the **Elements** panel.</span></span>  

<span data-ttu-id="4eaa0-312">Choose the **Clear** button to remove any inputted text.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-312">Choose the **Clear** button to remove any inputted text.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/clear-button-elements.msft.png" alt-text="Match keyboard shortcuts in the DevTools to Visual Studio Code" lightbox="../../media/2020/08/clear-button-elements.msft.png":::
         <span data-ttu-id="4eaa0-314">Clear buttons in the **Elements** panels</span><span class="sxs-lookup"><span data-stu-id="4eaa0-314">Clear buttons in the **Elements** panels</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2020/08/clear-button-network.msft.png" alt-text="Match keyboard shortcuts in the DevTools to Visual Studio Code" lightbox="../../media/2020/08/clear-button-network.msft.png":::
         <span data-ttu-id="4eaa0-316">Clear buttons in the  **Network** panels</span><span class="sxs-lookup"><span data-stu-id="4eaa0-316">Clear buttons in the  **Network** panels</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="4eaa0-317">Chromium issue: [#1067184][CR1067184]</span><span class="sxs-lookup"><span data-stu-id="4eaa0-317">Chromium issue: [#1067184][CR1067184]</span></span>  

## <span data-ttu-id="4eaa0-318">Download the Microsoft Edge preview channels</span><span class="sxs-lookup"><span data-stu-id="4eaa0-318">Download the Microsoft Edge preview channels</span></span>  

<span data-ttu-id="4eaa0-319">如果你使用的是 Windows 或 macOS，请考虑使用 [ Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels] 作为默认开发浏览器。</span><span class="sxs-lookup"><span data-stu-id="4eaa0-319">If you are on Windows or macOS, consider using the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] as your default development browser.</span></span>  <span data-ttu-id="4eaa0-320">The preview channels give you access to the latest DevTools features.</span><span class="sxs-lookup"><span data-stu-id="4eaa0-320">The preview channels give you access to the latest DevTools features.</span></span>  

## <span data-ttu-id="4eaa0-321">Getting in touch with Microsoft Edge DevTools team</span><span class="sxs-lookup"><span data-stu-id="4eaa0-321">Getting in touch with Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]  

<!-- image links -->  

[ImageSettingsIcon]: /microsoft-edge/devtools-guide-chromium/media/settings-icon.msft.png "DevTools Settings icon"  

<!-- links -->  

[DevtoolsWhatsnew200205DevtoolsDeprecationPropertiesPaneElementsPanel]: ../05/devtools.md#deprecation-of-the-properties-pane-in-the-elements-panel "Deprecation of the Properties pane in the Elements panel - What's new in DevTools (Microsoft Edge 84) | Microsoft Docs"  
[DevtoolsWhatsnew200206DevtoolsCssGridDebuggingFeatures]: ../06/devtools.md#css-grid-debugging-features "CSS grid debugging features - What's New In DevTools (Microsoft Edge 85) | Microsoft Docs"  

[DevtoolsDeviceModeIndex]: /microsoft-edge/devtools-guide-chromium/device-mode/index "Emulate mobile devices in Microsoft Edge DevTools | Microsoft Docs"  
[DevtoolsCustomizeShortcuts]: /microsoft-edge/devtools-guide-chromium/customize/shortcuts "Customize keyboard shortcuts in the Microsoft Edge DevTools | Microsoft Docs"  
[DevtoolsExperimentalFeaturesEnableExperimentalApis]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-experimental-apis "Enable experimental APIs - Experimental features | Microsoft Docs"  
[DevtoolsExperimentalFeaturesEnableNewCssGridDebuggingFeatures]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-new-css-grid-debugging-features "Emulation: Support dual screen mode - Experimental features | Microsoft Docs"  
[DevtoolsExperimentalFeaturesEnableSourceOrderViewer]: /microsoft-edge/devtools-guide-chromium/experimental-features#enable-source-order-viewer "Enable Source Order Viewer - Experimental features | Microsoft Docs"
[DevtoolsExperimentalFeaturesEmulationSupportDualScreenMode]: https://review.docs.microsoft.com/microsoft-edge/devtools-guide-chromium/experimental-features?branch=user/zoghadya/dual-screen-experiment#emulation-support-dual-screen-mode "Emulation: Support dual screen mode - Experimental features | Microsoft Docs"  
[DevtoolsExperimentalFeaturesTestingOnFoldableDualScreenDevices]: /microsoft-edge/devtools-guide-chromium/experimental-features#testing-on-foldable-and-dual-screen-devices "Testing on foldable and dual-screen devices - Experimental features | Microsoft Docs"  
[DevtoolsExperimentalFeaturesTurnOnExperimentalFeatures]: /microsoft-edge/devtools-guide-chromium/experimental-features#turn-on-experimental-features "Turn on experimental features - Experimental features | Microsoft Docs"  
[DevtoolsConsoleApiTable]: /microsoft-edge/devtools-guide-chromium/console/api#table "table - Console API reference | Microsoft Docs"  
[DevtoolsCoverageIndex]: /microsoft-edge/devtools-guide-chromium/coverage/index "Find unused JavaScript and CSS code with the Coverage tab in Microsoft Edge DevTools | Microsoft Docs"  
[DevtoolsCustomizeIndexDrawer]: /microsoft-edge/devtools-guide-chromium/customize/index#drawer "Drawer - Customize Microsoft Edge DevTools | Microsoft Docs"  
[DevtoolsEvaluatePerformanceReferenceAnalyzeRenderingPerformance]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference#analyze-rendering-performance-with-the-rendering-tab "Analyze rendering performance with the Rendering tab - Performance Analysis Reference | Microsoft Docs"  
[DevtoolsMediaIndex]: /microsoft-edge/devtools-guide-chromium/media/index "View and debug media players information | Microsoft Docs"  

[DualScreenIntroductionHowWorkSeam]:  /dual-screen/introduction#how-to-work-with-the-seam "How to work with the seam - Introduction to dual-screen devices | Microsoft Docs"  
[DualScreenWebCssMediaSpanning]: /dual-screen/web/css-media-spanning "CSS media screen-spanning feature for dual-screen detection | Microsoft Docs"  
[DualScreenWebJavascriptGetwindowsegments]: /dual-screen/web/javascript-getwindowsegments "The getWindowSegments JavaScript API for dual-screen devices | Microsoft Docs"  

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download "Microsoft Edge Preview Channels"  

[VisualStudioCode]: https://code.visualstudio.com "Visual Studio Code "  
[VisualStudioCodeShortcutsKeyboardWindows]: https://code.visualstudio.com/shortcuts/keyboard-shortcuts-windows.pdf "Visual Studio Code Keyboard shortcuts for Windows"  

[MicrosoftSurfaceDevicesDuo]: https://www.microsoft.com/surface/devices/surface-duo "The new Surface Duo"  

[EdgeDevToolsTwitterAccount]: https://twitter.com/EdgeDevTools "@EdgeDevTools Twitter account"  

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium bugs"  

[CR174309]: https://crbug.com/174309 "DevTools: Allow to customize keyboard shortcuts/key bindings | Chromium bugs"
[CR384968]: https://crbug.com/384968 "Option to ignore local() fonts | Chromium bugs"  
[CR772558]: https://crbug.com/772558 "DevTools: Update to latest version of Lighthouse | Chromium bugs"  
[CR807440]: https://crbug.com/807440 "Chrome locks up with large numbers of SWs | Chromium bugs"  
[CR997694]: https://crbug.com/997694 "XHR requests with 302 status are not shown under the \"xhr\" filter in network panel | Chromium bugs"  
[CR1047356]: https://crbug.com/1047356 "CSS Grid/Flexbox/Table tooling"  
[CR1051466]: https://crbug.com/1051466 "Support COOP/COEP debugging in DevTools | Chromium bugs"  
[CR1054281]: https://crbug.com/1054281 "Feature Request: DevTools should emulate foldable and dual-screen devices | Chromium bugs"  
[CR1067184]: https://crbug.com/1067184 "Feature Request: Clear filter button on Network & Elements -> Style Filter inputs | Chromium bugs"  
[CR1068116]: https://crbug.com/1068116 "☂ Ship issues panel | Chromium bugs"  
[CR1080569]: https://crbug.com/1080569 "acorn doesn't support logical assignment operators | Chromium bugs"  
[CR1080589]: https://crbug.com/1080589 "Classify issues by third-party / first-party | Chromium bugs"  
[CR1086817]: https://crbug.com/1086817 "acorn doesn't support numeric separators | Chromium bugs"  
[CR1090802]: https://crbug.com/1090802 "Simulate idle state changes from Idle Detection API | Chromium bugs"  
[CR1093227]: https://crbug.com/1093227 "DevTools: suggest closest accessible color | Chromium bugs"  
[CR1093247]: https://crbug.com/1093247 "Display info about frames in application panel | Chromium bugs"  
[CR1094406]: https://crbug.com/1094406 "Developers want a source order viewer for AT https://webwewant.fyi/wants/64/"  
[CR1096068]: https://crbug.com/1096068 "DevTools: support emulating the prefers-reduced-data media feature | Chromium bugs"  
[CR1096481]: https://crbug.com/1096481 "Issues banner placement | Chromium bugs"  
[CR1100253]: https://crbug.com/1100253 "Add screenshot node shortcut in Element context menu | Chromium bugs"  
[CR1103316]: https://crbug.com/1103316 "Elements search does not resolveNode (highlight text, etc) on first search result | Chromium bugs"  
[CR1103854]: https://crbug.com/1103854 "De-obfuscate X-Client-Data values in Developer Tools | Chromium bugs"  
<!--  [CR1105205]: https://crbug.com/1105205 "Issue 1105205 | Chromium bugs"  -->  
[CR1106221]: https://crbug.com/1106221 "Add imported fonts to the font-family autocompletion in the Styles panel | Chromium bugs"  
[CR1107766]: https://crbug.com/1107766 "Display info about frames generated by 'window.open()' in frame tree | Chromium bugs"  
[CR1115011]: https://crbug.com/1115011 "When copying a table from the console the structure of the table is not preserved | Chromium bugs"  
[CR1116085]: https://crbug.com/1116085 "Please bring back the DevTools Properties inspector | Chromium bugs"  

[CsswgDraftsMediaqueries5DescdefMediaPrefersReducedData]: https://drafts.csswg.org/mediaqueries-5#descdef-media-prefers-reduced-data "prefers-reduced-data - Media Queries Level 5 | W3C CSS Working Group Editor Drafts"  

[GithubGooglechromeLighthouseV620]: https://github.com/GoogleChrome/lighthouse/releases/tag/v6.2.0 "v6.2.0 - GoogleChrome/lighthouse | GitHub"  

[GoogleDevelopersProtocolBuffers]: https://developers.google.com/protocol-buffers "Protocol Buffers | Google Developers"  

[SamsungMobileGalaxyFold]: https://www.samsung.com/us/mobile/galaxy-fold "Galaxy Fold | Samsung US"  

[V8FeaturesLogicalAssignment]: https://v8.dev/features/logical-assignment "Logical assignment | V8"  
[V8FeaturesNumericSeparators]: https://v8.dev/features/numeric-separators "Numeric separators | V8"  

[WebDevCoopCoep]: https://web.dev/coop-coep "Making your website \"cross-origin isolated\" using COOP and COEP | web.dev"  
[WebDevIdleDetection]: https://web.dev/idle-detection "Detect inactive users with the Idle Detection API | web.dev"  
[WebDevNonCompositedAnimations]: https://web.dev/non-composited-animations "Avoid non-composited animations | web.dev"  

> [!NOTE]
> <span data-ttu-id="4eaa0-382">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="4eaa0-382">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="4eaa0-383">The original page is found [here](https://developers.google.com/web/updates/2020/08/devtools/index) and is authored by [Jecelyn Yeen][JecelynYeen] \(Developer advocate, Chrome DevTools\).</span><span class="sxs-lookup"><span data-stu-id="4eaa0-383">The original page is found [here](https://developers.google.com/web/updates/2020/08/devtools/index) and is authored by [Jecelyn Yeen][JecelynYeen] \(Developer advocate, Chrome DevTools\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="4eaa0-385">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="4eaa0-385">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen  
