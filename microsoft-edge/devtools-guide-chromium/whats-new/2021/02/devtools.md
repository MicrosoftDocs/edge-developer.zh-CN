---
description: CSS 弹性框调试支持、网页上的性能提示显示、问题工具更新等
title: DevTools 中的新增功能 (Microsoft Edge 90)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.localizationpriority: high
ms.openlocfilehash: a6682043166909bf75a875b72058cc9839c5b43b
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564845"
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
# <a name="whats-new-in-devtools-microsoft-edge-90"></a><span data-ttu-id="58f61-104">DevTools 中的新增功能 (Microsoft Edge 90)</span><span class="sxs-lookup"><span data-stu-id="58f61-104">What's New In DevTools (Microsoft Edge 90)</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/edge-whats-new-note.md)]  

## <a name="group-tools-together-in-focus-mode"></a><span data-ttu-id="58f61-105">在焦点模式下将工具组合在一起</span><span class="sxs-lookup"><span data-stu-id="58f61-105">Group tools together in Focus Mode</span></span>  

<!-- Title: Grouping the tools in Focus Mode  -->  
<!-- Subtitle: Organize your favorite tools into groups with the new Focus Mode UI.  -->  

<span data-ttu-id="58f61-106">焦点模式是一个试验界面，允许你根据自己的调试方案将不同工具组合在一起。</span><span class="sxs-lookup"><span data-stu-id="58f61-106">Focus Mode is an experimental interface that allows you to group different tools together based on your own debugging scenarios.</span></span>  <span data-ttu-id="58f61-107">左侧显示的新“**活动栏**”包括预定义的工具组，如“**布局**”和“**调试**”。</span><span class="sxs-lookup"><span data-stu-id="58f61-107">The new **Activity Bar** displayed on the left includes predefined tool groups such as **Layout** and **Debugging**.</span></span>  <span data-ttu-id="58f61-108">若要自定义每个工具组，请使用“**关闭**”(`X`) 图标关闭工具，或使用“**更多工具**”(`+`) 图标添加新工具。</span><span class="sxs-lookup"><span data-stu-id="58f61-108">To customize each tool group, close tools with the **Close** \(`X`\) icon or add new tools with the **More tools** \(`+`\) icon.</span></span>  

<span data-ttu-id="58f61-109">若要启用试验，请导航至“[启用试验功能][DevtoolsExperimentalFeaturesIndexTurnOnExperimentalFeatures]”，然后选择“**焦点模式和 DevTools 工具提示**”和“**启用 + 按钮选项卡菜单以打开更多工具**”旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="58f61-109">To turn on the experiment, navigate to [Turn on experimental features][DevtoolsExperimentalFeaturesIndexTurnOnExperimentalFeatures] and choose the checkboxes next to **Focus Mode and DevTools Tooltips** and **Enable + button tab menus to open more tools**.</span></span>  <span data-ttu-id="58f61-110">有关此功能的详细信息，或者要用问题和想法进行评论，请导航到 [DevTools：焦点模式 UI][GithubMicrosoftedgeMsedgeexplainersBlobMainDevtoolsFocusmodeExplainer]。</span><span class="sxs-lookup"><span data-stu-id="58f61-110">For more information about this feature or to comment with questions and ideas, navigate to [DevTools: Focus Mode UI][GithubMicrosoftedgeMsedgeexplainersBlobMainDevtoolsFocusmodeExplainer].</span></span>  

:::image type="complex" source="../../media/2021/02/focus-mode.msft.png" alt-text="显示“活动栏”" lightbox="../../media/2021/02/focus-mode.msft.png":::
   <span data-ttu-id="58f61-112">显示“**活动栏**”</span><span class="sxs-lookup"><span data-stu-id="58f61-112">Display the **Activity Bar**</span></span>  
:::image-end:::  

## <a name="learn-about-devtools-with-informative-tooltips"></a><span data-ttu-id="58f61-113">通过信息丰富的工具提示了解 DevTools</span><span class="sxs-lookup"><span data-stu-id="58f61-113">Learn about DevTools with informative tooltips</span></span>  

<!-- Title: DevTools Tooltips  -->  
<!-- Subtitle: Learn more about how to use DevTools with informative DevTools tooltips.  -->  

<span data-ttu-id="58f61-114">DevTools 工具提示功能可帮助你了解所有不同的工具和窗格。</span><span class="sxs-lookup"><span data-stu-id="58f61-114">The DevTools Tooltips feature helps you learn about all the different tools and panes.</span></span>  <span data-ttu-id="58f61-115">选择“**活动栏**”底部的“帮助”(`?`) 图标，以便在 DevTools 中切换工具提示。</span><span class="sxs-lookup"><span data-stu-id="58f61-115">Choose the Help \(`?`\) icon at the bottom of the **Activity Bar** to toggle tooltips in the DevTools.</span></span>  <span data-ttu-id="58f61-116">当工具提示打开时，请将鼠标悬停在 DevTools 的每个概述区域上，以了解有关如何使用工具的更多信息。</span><span class="sxs-lookup"><span data-stu-id="58f61-116">When tooltips are on, hover over each outlined region of DevTools to learn more about how to use the tool.</span></span>  <span data-ttu-id="58f61-117">若要启用试验，请导航至“[启用试验功能][DevtoolsExperimentalFeaturesIndexTurnOnExperimentalFeatures]”，然后选择“**焦点模式和 DevTools 工具提示**”和“**启用 + 按钮选项卡菜单以打开更多工具**”旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="58f61-117">To turn on the experiment, navigate to [Turn on experimental features][DevtoolsExperimentalFeaturesIndexTurnOnExperimentalFeatures] and choose the checkboxes next to **Focus Mode and DevTools Tooltips** and **Enable + button tab menus to open more tools**.</span></span>  <span data-ttu-id="58f61-118">有关此功能的详细信息，或者要用问题和想法进行评论，请导航到 [DevTools：焦点模式 UI][GithubMicrosoftedgeMsedgeexplainersBlobMainDevtoolsFocusmodeExplainer]。</span><span class="sxs-lookup"><span data-stu-id="58f61-118">For more information about this feature or to comment with questions and ideas, navigate to [DevTools: Focus Mode UI][GithubMicrosoftedgeMsedgeexplainersBlobMainDevtoolsFocusmodeExplainer].</span></span>  

:::image type="complex" source="../../media/2021/02/focus-mode-and-tooltips-help.msft.png" alt-text="选择“活动栏”中的“帮助”(?) 图标以显示工具提示" lightbox="../../media/2021/02/focus-mode-and-tooltips-help.msft.png":::
   <span data-ttu-id="58f61-120">选择“**活动栏**”中的“帮助”(`?`) 图标以显示工具提示</span><span class="sxs-lookup"><span data-stu-id="58f61-120">Choose the Help \(`?`\) icon in the **Activity Bar** to display tooltips</span></span>  
:::image-end:::  

## <a name="customize-keyboard-shortcuts-in-settings"></a><span data-ttu-id="58f61-121">在“设置”中自定义键盘快捷方式</span><span class="sxs-lookup"><span data-stu-id="58f61-121">Customize keyboard shortcuts in Settings</span></span>  

<!-- Title: Change keyboard shortcuts in Settings  -->  
<!-- TODO:  Rachel's feedback is about the fact that this experimental feature is turned on by default, may have separate section in What's New for experimental features)  -->  
<!-- Subtitle: Make DevTools work better for you by creating new keyboard shortcuts for any action in the DevTools.  -->  

<span data-ttu-id="58f61-122">现在，你可以为 DevTools 中的任何操作自定义键盘快捷方式。</span><span class="sxs-lookup"><span data-stu-id="58f61-122">You may now customize the keyboard shortcut for any action in the DevTools.</span></span>  <span data-ttu-id="58f61-123">若要编辑键盘快捷方式，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="58f61-123">To edit a keyboard shortcut, complete the following actions.</span></span>  

1.  <span data-ttu-id="58f61-124">打开 DevTools，然后选择“**设置**” > “**快捷方式**”。</span><span class="sxs-lookup"><span data-stu-id="58f61-124">Open the DevTools, and then choose **Settings** > **Shortcuts**.</span></span>  
1.  <span data-ttu-id="58f61-125">选择要自定义的操作。</span><span class="sxs-lookup"><span data-stu-id="58f61-125">Choose the action you want to customize.</span></span>  
1.  <span data-ttu-id="58f61-126">选择“编辑”（</span><span class="sxs-lookup"><span data-stu-id="58f61-126">Choose the Edit \(</span></span>![“编辑键盘快捷方式”图标](../../media/2021/02/edit-keyboard-shortcut-icon.msft.png)<span data-ttu-id="58f61-128">）图标。</span><span class="sxs-lookup"><span data-stu-id="58f61-128">\) icon.</span></span>  
1.  <span data-ttu-id="58f61-129">选择要绑定到操作的按键。</span><span class="sxs-lookup"><span data-stu-id="58f61-129">Select the keys you want to bind to the action.</span></span>  
1.  <span data-ttu-id="58f61-130">选中复选标记（</span><span class="sxs-lookup"><span data-stu-id="58f61-130">Choose the checkmark \(</span></span>![复选标记键盘快捷方式图标](../../media/2021/02/checkmark-keyboard-shortcut-icon.msft.png)<span data-ttu-id="58f61-132">）图标。</span><span class="sxs-lookup"><span data-stu-id="58f61-132">\) icon.</span></span>  
    
<span data-ttu-id="58f61-133">有关自定义和编辑快捷方式的详细信息，请导航到“[自定义 Microsoft Edge DevTools 中的键盘快捷方式][DevtoolsCustomizeShortcuts]”。</span><span class="sxs-lookup"><span data-stu-id="58f61-133">For more information about customizing and editing shortcuts, navigate to [Customize keyboard shortcuts in the Microsoft Edge DevTools][DevtoolsCustomizeShortcuts].</span></span>  <span data-ttu-id="58f61-134">若要在 Chromium 开源项目中查看此功能的实时更新，请导航至问题 [174309][CR174309]。</span><span class="sxs-lookup"><span data-stu-id="58f61-134">To review real-time updates on this feature in the Chromium open-source project, navigate to Issue [174309][CR174309].</span></span>  

:::image type="complex" source="../../media/2021/02/custom-shortcut-pause-script-checkmark.msft.png" alt-text="在编辑模式下使用快捷方式在“DevTools 设置”的“快捷方式”上自定义键盘快捷方式" lightbox="../../media/2021/02/custom-shortcut-pause-script-checkmark.msft.png":::
   <span data-ttu-id="58f61-136">在编辑模式下使用快捷方式在“[DevTools 设置][DevtoolsCustomizeIndexSettings]”的“快捷方式”上自定义键盘快捷方式</span><span class="sxs-lookup"><span data-stu-id="58f61-136">Customize keyboard shortcuts in the [DevTools Settings][DevtoolsCustomizeIndexSettings] on Shortcuts with a shortcut in edit mode</span></span>  
:::image-end:::  

## <a name="microsoft-edge-devtools-for-visual-studio-code-extension-update-114"></a><span data-ttu-id="58f61-137">Microsoft Edge DevTools for Visual Studio Code 扩展更新 1.1.4</span><span class="sxs-lookup"><span data-stu-id="58f61-137">Microsoft Edge DevTools for Visual Studio Code extension update 1.1.4</span></span>  

<!-- Title: Edge Devtools for Visual Studio code extension update 1.1.4  -->  
<!-- Subtitle: Latest changes including a favicon is displayed next to each of the instances and console messages from the browser are displayed in the console of Visual Studio Code.  -->  

<span data-ttu-id="58f61-138">适用于 Microsoft Visual Studio Code 的 [Microsoft Edge Developer Tools for Visual Studio Code][VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools] 扩展版本 1.1.4 现在在每个 DevTools 实例旁边显示一个网站图标。</span><span class="sxs-lookup"><span data-stu-id="58f61-138">The [Microsoft Edge Developer Tools for Visual Studio Code][VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools] extension version 1.1.4 for Microsoft Visual Studio Code now displays a favicon next to each of the DevTools instances.</span></span>  <span data-ttu-id="58f61-139">来自 Microsoft Edge 的控制台消息现在显示在 Microsoft Visual Studio Code 的“**输出**”下的“**DevTools 控制台**”中。</span><span class="sxs-lookup"><span data-stu-id="58f61-139">Console messages from Microsoft Edge now display in the **DevTools Console** under **Output** of Microsoft Visual Studio Code.</span></span>  <span data-ttu-id="58f61-140">Microsoft Visual Studio Code 会自动更新扩展。</span><span class="sxs-lookup"><span data-stu-id="58f61-140">Microsoft Visual Studio Code updates extensions automatically.</span></span>  <span data-ttu-id="58f61-141">若要手动更新到版本 1.1.4，请导航至“[手动更新扩展][VisualstudioCodeDocsEditorExtensionGalleryUpdateExtensionManually]”。</span><span class="sxs-lookup"><span data-stu-id="58f61-141">To manually update to version 1.1.4, navigate to [Update an extension manually][VisualstudioCodeDocsEditorExtensionGalleryUpdateExtensionManually].</span></span>  <span data-ttu-id="58f61-142">你可以在 [vscode-edge-devtools GitHub repo][GithubMicrosoftVscodeEdgeDevtools] 上提交问题并参与提升扩展。</span><span class="sxs-lookup"><span data-stu-id="58f61-142">You may file issues and contribute to the extension on the [vscode-edge-devtools][GithubMicrosoftVscodeEdgeDevtools] GitHub repo.</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="58f61-143">下图显示了来自 Microsoft Edge 的“**控制台**”工具中记录的示例网页的消息。</span><span class="sxs-lookup"><span data-stu-id="58f61-143">The following figure displays messages from an example webpage logged in the **Console** tool in Microsoft Edge.</span></span>  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="58f61-144">下图显示了来自 Microsoft Visual Studio Code 的“**输出**”下的“**DevTools 控制台**”中记录的示例网页的相同消息。</span><span class="sxs-lookup"><span data-stu-id="58f61-144">The following figure displays the same messages from the example webpage logged in the **DevTools Console** under **Output** of Microsoft Visual Studio Code.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/02/visual-studio-code-extension-log-microsoft-edge.msft.png" alt-text="在 Microsoft Edge DevTools 的控制台中显示消息" lightbox="../../media/2021/02/visual-studio-code-extension-log-microsoft-edge.msft.png":::
         <span data-ttu-id="58f61-146">在 Microsoft Edge DevTools 的控制台中显示消息</span><span class="sxs-lookup"><span data-stu-id="58f61-146">Display a message in Console in Microsoft Edge DevTools</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/02/visual-studio-code-extension-log-editor.msft.png" alt-text="在 Microsoft Visual Studio Code 的“输出”下的“DevTools 控制台”中显示相同消息" lightbox="../../media/2021/02/visual-studio-code-extension-log-editor.msft.png":::
         <span data-ttu-id="58f61-148">在 Microsoft Visual Studio Code 的“输出”下的“DevTools 控制台”中显示相同消息</span><span class="sxs-lookup"><span data-stu-id="58f61-148">Display the same message in the DevTools Console under Output of Microsoft Visual Studio Code</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="improved-css-flexbox-editing-with-visual-flexbox-editor-and-multiple-overlays"></a><span data-ttu-id="58f61-149">通过可视弹性框编辑器和多个覆盖改进了 CSS 弹性框编辑</span><span class="sxs-lookup"><span data-stu-id="58f61-149">Improved CSS flexbox editing with visual flexbox editor and multiple overlays</span></span>  

<!-- Title: Try different CSS flexbox layouts with the visual flexbox editor  -->  
<!-- Subtitle: In the Styles pane, choose the icon that appears next to display: flex to try different layout properties for flex containers.  -->  

<span data-ttu-id="58f61-150">DevTools 现在具有专用的 CSS 弹性框调试工具。</span><span class="sxs-lookup"><span data-stu-id="58f61-150">DevTools now has dedicated CSS flexbox debugging tools.</span></span>  <span data-ttu-id="58f61-151">如果将 `display: flex` 或 `display: inline-flex` CSS 样式应用于 HTML 元素，则“**元素**”工具中该元素旁边将显示 `flex` 图标。</span><span class="sxs-lookup"><span data-stu-id="58f61-151">If the `display: flex` or `display: inline-flex` CSS style is applied to an HTML element, a `flex` icon displays next to that element in the **Elements** tool.</span></span>  <span data-ttu-id="58f61-152">若要在网页上显示（或隐藏）弹性覆盖，请选择 `flex` 图标。</span><span class="sxs-lookup"><span data-stu-id="58f61-152">To display \(or hide\) a flex overlay on the webpage, choose the `flex` icon.</span></span>  <span data-ttu-id="58f61-153">若要在 Chromium 开源项目中查看此功能的历史记录，请导航至问题 [1166710][CR1166710] 和 [1175699][CR1175699]。</span><span class="sxs-lookup"><span data-stu-id="58f61-153">To review the history of this feature in the Chromium open-source project, navigate to Issues [1166710][CR1166710] and [1175699][CR1175699].</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="58f61-154">若要打开**弹性框**编辑器，请导航至“**样式**”窗格，然后选择 `display: flex` 或 `display: inline-flex` 样式旁边的新图标。</span><span class="sxs-lookup"><span data-stu-id="58f61-154">To open the **Flexbox** editor, navigate to the **Styles** pane and choose the new icon next to the `display: flex` or `display: inline-flex` style.</span></span>  <span data-ttu-id="58f61-155">**弹性框**编辑器提供了一种快速编辑弹性框属性的方法。</span><span class="sxs-lookup"><span data-stu-id="58f61-155">The **Flexbox** editor provides a quick way to edit the flexbox properties.</span></span>  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="58f61-156">此外，“**布局**”窗格中的“**弹性框**”部分将显示网页上的所有弹性框元素。</span><span class="sxs-lookup"><span data-stu-id="58f61-156">In addition, the **Flexbox** section in the **Layout** pane displays all of the flexbox elements on the webpage.</span></span>  <span data-ttu-id="58f61-157">你可以切换每个元素的覆盖。</span><span class="sxs-lookup"><span data-stu-id="58f61-157">You may toggle the overlay of each element.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/02/elements-styles-display-flex-window.msft.png" alt-text="CSS 弹性框调试工具" lightbox="../../media/2021/02/elements-styles-display-flex-window.msft.png":::
         <span data-ttu-id="58f61-159">CSS 弹性框调试工具</span><span class="sxs-lookup"><span data-stu-id="58f61-159">CSS flexbox debugging tools</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/02/elements-layout-flexbox-flexbox-overlays.msft.png" alt-text="“布局”窗格中的“弹性框”部分" lightbox="../../media/2021/02/elements-layout-flexbox-flexbox-overlays.msft.png":::
         <span data-ttu-id="58f61-161">“**布局**”窗格中的“**弹性框**”部分</span><span class="sxs-lookup"><span data-stu-id="58f61-161">**Flexbox** section in the **Layout** pane</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="keyboard-navigation-improvements-for-network-requests"></a><span data-ttu-id="58f61-162">网络请求的键盘导航改进</span><span class="sxs-lookup"><span data-stu-id="58f61-162">Keyboard navigation improvements for network requests</span></span>  

<!-- Title: Navigate the request initiator chain in the Network tool with the keyboard  -->  
<!-- Subtitle: The Initiator pane may now be expanded or collapsed with the arrow keys.  -->  

<span data-ttu-id="58f61-163">以前，在“**发起程序**”窗格中，你无法使用键盘上的箭头键展开或折叠请求链，这与“**元素**”工具中的 DOM 不同。</span><span class="sxs-lookup"><span data-stu-id="58f61-163">Previously, you were not able to expand or collapse the chain of requests using the arrow keys on the keyboard in the **Initiator** pane, unlike the DOM in the **Elements** tool.</span></span>  <span data-ttu-id="58f61-164">当在“**网络**”工具中选择网络请求时，“**发起程序**”窗格将显示发起当前选定请求的请求链。</span><span class="sxs-lookup"><span data-stu-id="58f61-164">When a network request is selected in the **Network** tool, the **Initiator** pane displays the chain of requests that initiated the currently selected request.</span></span>  

<span data-ttu-id="58f61-165">在 Microsoft Edge 版本 90 中，在“**发起程序**”窗格中，你可以使用键盘上的箭头键展开或折叠请求链。</span><span class="sxs-lookup"><span data-stu-id="58f61-165">In Microsoft Edge version 90, you may expand or collapse the chain of requests using the arrow keys on the keyboard in the **Initiator** pane.</span></span>  <span data-ttu-id="58f61-166">链中的焦点网络请求现在也会突出显示。</span><span class="sxs-lookup"><span data-stu-id="58f61-166">The focused network request in the chain is also now highlighted.</span></span>  <span data-ttu-id="58f61-167">若要在“**网络**”工具中了解有关发起程序的更多信息，请导航至“[显示发起程序和依赖项][DevtoolsNetworkReferenceDisplayInitiatorsDependencies]”。</span><span class="sxs-lookup"><span data-stu-id="58f61-167">To learn more about initiators in the **Network** tool, navigate to [Display initiators and dependencies][DevtoolsNetworkReferenceDisplayInitiatorsDependencies].</span></span>  <span data-ttu-id="58f61-168">若要在 Chromium 开源项目中查看此功能的历史记录，请导航至问题 [1158276][CR1158276] 和 [1160637][CR1160637]。</span><span class="sxs-lookup"><span data-stu-id="58f61-168">To review the history of this feature in the Chromium open-source project, navigate to Issues [1158276][CR1158276] and [1160637][CR1160637].</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/02/network-request-initiator-chain.msft.png" alt-text="选择一个网络请求，然后选择“发起程序”窗格" lightbox="../../media/2021/02/network-request-initiator-chain.msft.png":::
         <span data-ttu-id="58f61-170">选择一个网络请求，然后选择“**发起程序**”窗格</span><span class="sxs-lookup"><span data-stu-id="58f61-170">Choose a Network request and choose the **Initiator** pane</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/02/network-request-initiator-chain-right-arrow-down-twice-down-arrow-thrice.msft.png" alt-text="展开或折叠请求发起程序链并遵循突出显示的行" lightbox="../../media/2021/02/network-request-initiator-chain-right-arrow-down-twice-down-arrow-thrice.msft.png":::
         <span data-ttu-id="58f61-172">展开或折叠请求发起程序链并遵循突出显示的行</span><span class="sxs-lookup"><span data-stu-id="58f61-172">Expand or collapse the request initiator chain and follow the highlighted row</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="filtering-in-the-console-is-more-consistent"></a><span data-ttu-id="58f61-173">控制台中的筛选更加一致</span><span class="sxs-lookup"><span data-stu-id="58f61-173">Filtering in the Console is more consistent</span></span>  

<!-- Title: Console improvements make filtering more consistent  -->  
<!-- Subtitle: The Log Levels dropdown is more clearly disabled when using filters in the Console sidebar.  -->  

<span data-ttu-id="58f61-174">当使用[控制台边栏][DevtoolsConsoleReferenceOpenConsoleSidebar]进行筛选时，“[日志级别][DevtoolsConsoleReferenceFilterByLogLevel]”下拉列表中的筛选器不可用。</span><span class="sxs-lookup"><span data-stu-id="58f61-174">While you filter with the [Console Sidebar][DevtoolsConsoleReferenceOpenConsoleSidebar], the filters in the [Log Levels][DevtoolsConsoleReferenceFilterByLogLevel] dropdown are not available.</span></span>  <span data-ttu-id="58f61-175">以前，“**日志级别**”下拉列表在你悬停时会突出显示，即使从**控制台边栏**中选择了筛选器也是如此。</span><span class="sxs-lookup"><span data-stu-id="58f61-175">Previously, the **Log Levels** dropdown highlighted when you hovered on it, even while a filter from the **Console Sidebar** was chosen.</span></span>  <span data-ttu-id="58f61-176">在 Microsoft Edge 版本 90 中，当你从**控制台边栏**中选择筛选器后将鼠标悬停在“**日志级别**”下拉列表上时，它不再突出显示。</span><span class="sxs-lookup"><span data-stu-id="58f61-176">In Microsoft Edge version 90, the **Log Levels** dropdown no longer highlights when you hover on it while a filter from the **Console Sidebar** is chosen.</span></span>  <span data-ttu-id="58f61-177">若要了解有关**控制台**中的筛选的更多信息，请导航至“[筛选消息][DevtoolsConsoleReferenceFilterMessages]”。</span><span class="sxs-lookup"><span data-stu-id="58f61-177">To learn more about filtering in the **Console**, navigate to [Filter Messages][DevtoolsConsoleReferenceFilterMessages].</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/02/console-sidebar-default-levels-old.msft.png" alt-text="以前，如果打开控制台边栏并将鼠标悬停在“默认级别”上，它会突出显示" lightbox="../../media/2021/02/console-sidebar-default-levels-old.msft.png":::
         <span data-ttu-id="58f61-179">以前，如果打开**控制台边栏**并将鼠标悬停在“**默认级别**”上，它会突出显示</span><span class="sxs-lookup"><span data-stu-id="58f61-179">Previously, if you open the **Console sidebar** and hover on **Default levels** it was highlighted</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/02/console-sidebar-default-levels-new.msft.png" alt-text="从 Microsoft Edge 90 开始，如果你选择控制台边栏并将鼠标悬停在“默认级别”上，它不会突出显示" lightbox="../../media/2021/02/console-sidebar-default-levels-new.msft.png":::
         <span data-ttu-id="58f61-181">从 Microsoft Edge 90 开始，如果你选择**控制台边栏**并将鼠标悬停在“**默认级别**”上，它不会突出显示</span><span class="sxs-lookup"><span data-stu-id="58f61-181">Starting in Microsoft Edge 90, if you choose the **Console sidebar** and hover on **Default levels**, it does not highlight</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="announcements-from-the-chromium-project"></a><span data-ttu-id="58f61-182">来自 Chromium 项目的公告</span><span class="sxs-lookup"><span data-stu-id="58f61-182">Announcements from the Chromium project</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/chromium-whats-new-note.md)]  

### <a name="the-console-now-escapes-double-quote-characters"></a><span data-ttu-id="58f61-183">控制台现在可对双引号字符进行转义</span><span class="sxs-lookup"><span data-stu-id="58f61-183">The Console now escapes double quote characters</span></span>  

<span data-ttu-id="58f61-184">以前，**控制台**不在 JavaScript 字符串中输出有效的双引号 (`"`) 字符。</span><span class="sxs-lookup"><span data-stu-id="58f61-184">Previously, the **Console** did not output valid double quote \(`"`\) characters in JavaScript strings.</span></span>  <span data-ttu-id="58f61-185">从 Microsoft Edge 版本 90 开始，**控制台**将使用转义的双引号 (`"`) 字符输出 JavaScript 字符串。</span><span class="sxs-lookup"><span data-stu-id="58f61-185">Starting in Microsoft Edge version 90, the **Console** outputs JavaScript strings using escaped double quote \(`"`\) characters.</span></span>  <span data-ttu-id="58f61-186">若要在 Chromium 开源项目中查看此功能的历史记录，请导航至问题 [1178530][CR1178530]。</span><span class="sxs-lookup"><span data-stu-id="58f61-186">To review the history of this feature in the Chromium open-source project, navigate to Issue [1178530][CR1178530].</span></span>  

:::image type="complex" source="../../media/2021/02/console-string-formatted-double-quotes.msft.png" alt-text="控制台将使用转义的双引号 (&#0022;) 字符输出 JavaScript 字符串" lightbox="../../media/2021/02/console-string-formatted-double-quotes.msft.png":::
   <span data-ttu-id="58f61-188">**控制台**将使用转义的双引号 (`"`) 字符输出 JavaScript 字符串</span><span class="sxs-lookup"><span data-stu-id="58f61-188">The **Console** outputs JavaScript strings using escaped double quote \(`"`\) characters</span></span>  
:::image-end:::  

### <a name="emulate-the-css-color-gamut-media-feature"></a><span data-ttu-id="58f61-189">模拟 CSS 色域媒体功能</span><span class="sxs-lookup"><span data-stu-id="58f61-189">Emulate the CSS color-gamut media feature</span></span>  

<span data-ttu-id="58f61-190">[色域][ChromestatusFeature5354410980933632]媒体查询会模拟浏览器和你正在测试的设备支持的大致颜色范围。</span><span class="sxs-lookup"><span data-stu-id="58f61-190">The [color-gamut][ChromestatusFeature5354410980933632] media query emulates the approximate range of colors supported by the browser and the device you are testing.</span></span>  <span data-ttu-id="58f61-191">“**模拟 CSS 媒体功能色域**”下的下拉列表包含 DevTools 可能模拟的颜色空间。</span><span class="sxs-lookup"><span data-stu-id="58f61-191">The dropdown under **Emulate CSS media feature color-gamut** contains color spaces that DevTools may emulate.</span></span>  <span data-ttu-id="58f61-192">例如，若要触发 `color-gamut: p3` 媒体查询，请从下拉列表中选择“**色域：p3**”。</span><span class="sxs-lookup"><span data-stu-id="58f61-192">For example, to trigger a `color-gamut: p3` media query, choose **color-gamut: p3** from the dropdown.</span></span>  

<span data-ttu-id="58f61-193">若要模拟 CSS 色域媒体功能，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="58f61-193">To emulate the CSS color-gamut media feature, complete the following actions.</span></span>  

1.  <span data-ttu-id="58f61-194">打开“[命令菜单][DevtoolsCommandMenuIndex]”。</span><span class="sxs-lookup"><span data-stu-id="58f61-194">Open the [Command Menu][DevtoolsCommandMenuIndex].</span></span>  
1.  <span data-ttu-id="58f61-195">键入 `Rendering`。</span><span class="sxs-lookup"><span data-stu-id="58f61-195">Type `Rendering`.</span></span>  
1.  <span data-ttu-id="58f61-196">运行“**显示呈现**”命令。</span><span class="sxs-lookup"><span data-stu-id="58f61-196">Run the **Show Rendering** command.</span></span>  
1.  <span data-ttu-id="58f61-197">导航到“**模拟 CSS 媒体功能色域**”并选择一个选项。</span><span class="sxs-lookup"><span data-stu-id="58f61-197">Navigate to **Emulate CSS media feature color-gamut** and choose an option.</span></span>  

<span data-ttu-id="58f61-198">若要了解有关 `color-gamut` 功能的更多信息，请导航到“[颜色显示质量：‘色域’功能][CsswgDraftsMediaqueries4ColorGamut]”。</span><span class="sxs-lookup"><span data-stu-id="58f61-198">To learn more about the `color-gamut` feature, navigate to [Color Display Quality: the 'color-gamut' feature][CsswgDraftsMediaqueries4ColorGamut].</span></span>  <span data-ttu-id="58f61-199">若要在 Chromium 开源项目中查看此功能的历史记录，请导航至问题 [1073887][CR1073887]。</span><span class="sxs-lookup"><span data-stu-id="58f61-199">To review the history of this feature in the Chromium open-source project, navigate to Issue [1073887][CR1073887].</span></span>  

:::image type="complex" source="../../media/2021/02/rendering-css-color-gamut.msft.png" alt-text="模拟 CSS 色域媒体功能" lightbox="../../media/2021/02/rendering-css-color-gamut.msft.png":::
   <span data-ttu-id="58f61-201">模拟 CSS 色域媒体功能</span><span class="sxs-lookup"><span data-stu-id="58f61-201">Emulate the CSS color-gamut media feature</span></span>  
:::image-end:::  

### <a name="improved-progressive-web-apps-tooling"></a><span data-ttu-id="58f61-202">改进了渐进式 Web 应用工具</span><span class="sxs-lookup"><span data-stu-id="58f61-202">Improved Progressive Web Apps tooling</span></span>  

#### <a name="pwa-installability-warning-in-the-console"></a><span data-ttu-id="58f61-203">控制台中的 PWA 可安装性警告</span><span class="sxs-lookup"><span data-stu-id="58f61-203">PWA installability warning in the Console</span></span>  

<span data-ttu-id="58f61-204">现在，“**控制台**”现在将显示更详细的[渐进式 Web 应用 (PWA)][ProgressiveWebAppsIndex] 可安装性警告消息，其中包含指向“[改进渐进式 Web 应用脱机支持检测][ChromeDeveloperBlogImprovedPwaOfflineDetection]”的链接。</span><span class="sxs-lookup"><span data-stu-id="58f61-204">The **Console** now displays a more detailed [Progressive Web Apps (PWA)][ProgressiveWebAppsIndex] installability warning message with a link to [Improving Progressive Web App offline support detection][ChromeDeveloperBlogImprovedPwaOfflineDetection].</span></span>  

:::image type="complex" source="../../media/2021/02/console-pwa-installability.msft.png" alt-text="“控制台”工具中的 PWA 可安装性警告" lightbox="../../media/2021/02/console-pwa-installability.msft.png":::
   <span data-ttu-id="58f61-206">“**控制台**”工具中的 PWA 可安装性警告</span><span class="sxs-lookup"><span data-stu-id="58f61-206">PWA installability warning in **Console** tool</span></span>  
:::image-end:::  

#### <a name="pwa-description-length-warning-in-the-manifest-pane"></a><span data-ttu-id="58f61-207">“清单”窗格中的 PWA 说明长度警告</span><span class="sxs-lookup"><span data-stu-id="58f61-207">PWA description length warning in the Manifest pane</span></span>

<span data-ttu-id="58f61-208">如果清单说明超过了 324 个字符，“**清单**”窗格现在将显示一条警告消息。</span><span class="sxs-lookup"><span data-stu-id="58f61-208">The **Manifest** pane now displays a warning message if the manifest description exceeds 324 characters.</span></span>  

:::image type="complex" source="../../media/2021/02/application-manifest-errors-and-warnings-truncated.msft.png" alt-text="PWA 说明截断警告" lightbox="../../media/2021/02/application-manifest-errors-and-warnings-truncated.msft.png":::
   <span data-ttu-id="58f61-210">PWA 说明截断警告</span><span class="sxs-lookup"><span data-stu-id="58f61-210">PWA description truncate warning</span></span>  
:::image-end:::  

<span data-ttu-id="58f61-211">若要在 Chromium 开源项目中查看此功能的历史记录，请导航至问题 [965802][CR965802]、[1146450][CR1146450] 和 [1169689][CR1169689]。</span><span class="sxs-lookup"><span data-stu-id="58f61-211">To review the history of this feature in the Chromium open-source project, navigate to Issues [965802][CR965802], [1146450][CR1146450], and [1169689][CR1169689].</span></span>  

### <a name="new-remote-address-space-column-in-the-network-tool"></a><span data-ttu-id="58f61-212">“网络”工具中新的“远程地址空间”列</span><span class="sxs-lookup"><span data-stu-id="58f61-212">New Remote Address Space column in the Network tool</span></span>  

<!-- does not work in canary 90.0.813.0 -->  
<span data-ttu-id="58f61-213">新的“**远程地址空间**”列显示每个网络资源的网络 IP 地址空间。</span><span class="sxs-lookup"><span data-stu-id="58f61-213">The new **Remote Address Space** column displays the network IP address space of each network resource.</span></span>  <span data-ttu-id="58f61-214">若要显示新的“远程地址空间”列，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="58f61-214">To display the new Remote Address Space column, complete the following actions.</span></span>  

1.  <span data-ttu-id="58f61-215">导航到“**网络**”工具。</span><span class="sxs-lookup"><span data-stu-id="58f61-215">Navigate to the **Network** tool.</span></span>  
1.  <span data-ttu-id="58f61-216">在“请求”表中，将鼠标悬停在标题行上，然后打开上下文菜单（右键单击）。</span><span class="sxs-lookup"><span data-stu-id="58f61-216">In the Requests table, hover on the header row, and open the contextual menu \(right-click\).</span></span>  <span data-ttu-id="58f61-217">若要了解如何在“请求”表中添加或删除列，请导航到“[添加或删除列][DevtoolsNetworkReferenceAddRemoveColumns]。</span><span class="sxs-lookup"><span data-stu-id="58f61-217">To learn how to add or remove columns from the Requests table, navigate to [Add or remove columns][DevtoolsNetworkReferenceAddRemoveColumns].</span></span>  
1.  <span data-ttu-id="58f61-218">选择“**远程地址空间**”。</span><span class="sxs-lookup"><span data-stu-id="58f61-218">Choose **Remote Address Space**.</span></span>  
    
<span data-ttu-id="58f61-219">现在，“请求”表将显示一个标题为“**远程地址空间**”的新列。</span><span class="sxs-lookup"><span data-stu-id="58f61-219">The Requests table now displays a new column with the header named **Remote Address Space**.</span></span>  <span data-ttu-id="58f61-220">若要在 Chromium 开源项目中查看此功能的历史记录，请导航至问题 [1128885][CR1128885]。</span><span class="sxs-lookup"><span data-stu-id="58f61-220">To review the history of this feature in the Chromium open-source project, navigate to Issue [1128885][CR1128885].</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/02/network-requests-contextual-menu-remote-address-space.msft.png" alt-text="在上下文菜单中，选择“远程地址空间”" lightbox="../../media/2021/02/network-requests-contextual-menu-remote-address-space.msft.png":::
         <span data-ttu-id="58f61-222">在上下文菜单中，选择“**远程地址空间**”</span><span class="sxs-lookup"><span data-stu-id="58f61-222">In the contextual menu, choose the **Remote Address Space**</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/02/network-requests-remote-address-space.msft.png" alt-text="“请求”表现在显示“远程地址空间”列" lightbox="../../media/2021/02/network-requests-remote-address-space.msft.png":::
         <span data-ttu-id="58f61-224">“请求”表现在显示“**远程地址空间**”列</span><span class="sxs-lookup"><span data-stu-id="58f61-224">The Requests table now displays the **Remote Address Space** column</span></span> :::image-end:::  
   :::column-end:::
:::row-end:::  

### <a name="display-allowed-and-disallowed-features-in-the-frame-details-view"></a><span data-ttu-id="58f61-225">在“框架详细信息”视图中显示允许和禁止的功能</span><span class="sxs-lookup"><span data-stu-id="58f61-225">Display allowed and disallowed features in the Frame details view</span></span>  

<span data-ttu-id="58f61-226">“框架详细信息”视图现在显示受“[权限策略][GithubW3cWebappsecPermissionsPolicyBlobMainPermissionsPolicyExplainer]”控制的允许和禁止的浏览器功能列表。</span><span class="sxs-lookup"><span data-stu-id="58f61-226">The Frame details view now displays a list of allowed and disallowed browser features controlled by the [Permissions Policy][GithubW3cWebappsecPermissionsPolicyBlobMainPermissionsPolicyExplainer].</span></span>  <span data-ttu-id="58f61-227">“权限策略”是一种 Web 平台 API，它允许（或阻止）网页在单个框架或其嵌入的 iframe 中使用浏览器功能。</span><span class="sxs-lookup"><span data-stu-id="58f61-227">Permissions Policy is a web platform API that allows \(or blocks\) a webpage the use of browser features in an individual frame or in iframes that it embeds.</span></span>  <span data-ttu-id="58f61-228">若要在 Chromium 开源项目中查看此功能的历史记录，请导航至问题 [1158827][CR1158827]。</span><span class="sxs-lookup"><span data-stu-id="58f61-228">To review the history of this feature in the Chromium open-source project, navigate to Issue [1158827][CR1158827].</span></span>  

:::image type="complex" source="../../media/2021/02/application-frames-permissions-policy.msft.png" alt-text="基于权限策略允许和禁止的功能" lightbox="../../media/2021/02/application-frames-permissions-policy.msft.png":::
   <span data-ttu-id="58f61-230">基于权限策略允许和禁止的功能</span><span class="sxs-lookup"><span data-stu-id="58f61-230">Allowed and disallowed features based on the Permission Policy</span></span>  
:::image-end:::  

### <a name="new-sameparty-column-in-the-cookies-pane"></a><span data-ttu-id="58f61-231">“Cookie”窗格中新的“SameParty”列</span><span class="sxs-lookup"><span data-stu-id="58f61-231">New SameParty column in the Cookies pane</span></span>  

<span data-ttu-id="58f61-232">“**应用程序**”工具中的“**Cookie**”窗格现在显示每个 Cookie 的 `SameParty` 属性。</span><span class="sxs-lookup"><span data-stu-id="58f61-232">The **Cookies** pane in the **Application** tool now displays the `SameParty` attribute for each cookie.</span></span>  <span data-ttu-id="58f61-233">`SameParty` 属性是一个新的布尔属性，用于指示在对相同[第一方集][GithubPrivacycgFirstPartySets]的起源的请求中是否包含 cookie。</span><span class="sxs-lookup"><span data-stu-id="58f61-233">The `SameParty` attribute is a new boolean attribute to indicate whether a cookie is included in requests to origins of the same [First-Party Sets][GithubPrivacycgFirstPartySets].</span></span>  <span data-ttu-id="58f61-234">若要在 Chromium 开源项目中查看此功能的历史记录，请导航至问题 [1161427][CR1161427]。</span><span class="sxs-lookup"><span data-stu-id="58f61-234">To review the history of this feature in the Chromium open-source project, navigate to Issue [1161427][CR1161427].</span></span>  

:::image type="complex" source="../../media/2021/02/application-storage-cookies-sameparty.msft.png" alt-text="“Cookie”窗格中的“SameParty”列" lightbox="../../media/2021/02/application-storage-cookies-sameparty.msft.png":::
   <span data-ttu-id="58f61-236">“**Cookie**”窗格中的“**SameParty**”列</span><span class="sxs-lookup"><span data-stu-id="58f61-236">**SameParty** column in the **Cookies** pane</span></span>  
:::image-end:::  

### <a name="fndisplayname-property-in-the-console-tool-is-now-deprecated"></a><span data-ttu-id="58f61-237">“控制台”工具中的 fn.displayName 属性现已弃用</span><span class="sxs-lookup"><span data-stu-id="58f61-237">fn.displayName property in the Console tool is now deprecated</span></span>  

<span data-ttu-id="58f61-238">以前，`fn.displayName` 属性允许你控制要在 `error.stack` 和 DevTools 堆栈跟踪中显示的函数的调试名称。</span><span class="sxs-lookup"><span data-stu-id="58f61-238">Previously, the `fn.displayName` property allowed you to control debug names for functions to display in `error.stack` and in DevTools stack traces.</span></span>  <span data-ttu-id="58f61-239">从 Microsoft Edge 版本 90 开始，`fn.displayName` 属性现已弃用，并替换为 `fn.name` 属性。</span><span class="sxs-lookup"><span data-stu-id="58f61-239">Starting in Microsoft Edge version 90, the `fn.displayName` property is now deprecated, and replaced by the `fn.name` property.</span></span>  <span data-ttu-id="58f61-240">使用标准 `Object.defineProperty` 方法定义 `fn.name` 属性。</span><span class="sxs-lookup"><span data-stu-id="58f61-240">Use the standard `Object.defineProperty` method to define the `fn.name` property.</span></span>  <span data-ttu-id="58f61-241">若要了解有关 `fn.name` 的更多信息，请导航至 [Function.name][MdnJavascriptReferenceGlobalObjectsFunctionName]。</span><span class="sxs-lookup"><span data-stu-id="58f61-241">To learn more about `fn.name`, navigate to [Function.name][MdnJavascriptReferenceGlobalObjectsFunctionName].</span></span>  <span data-ttu-id="58f61-242">若要在 Chromium 开源项目中查看此功能的历史记录，请导航至问题 [1177685][CR1177685]。</span><span class="sxs-lookup"><span data-stu-id="58f61-242">To review the history of this feature in the Chromium open-source project, navigate to Issue [1177685][CR1177685].</span></span>  

:::image type="complex" source="../../media/2021/02/console-display-name-name.msft.png" alt-text="用于控制函数的调试名称的 fn.name 属性示例" lightbox="../../media/2021/02/console-display-name-name.msft.png":::
   <span data-ttu-id="58f61-244">用于控制函数的调试名称的 `fn.name` 属性示例</span><span class="sxs-lookup"><span data-stu-id="58f61-244">An example of the `fn.name` property to control debug names for functions</span></span>  
:::image-end:::  

### <a name="full-accessibility-tree-view-in-the-elements-tool"></a><span data-ttu-id="58f61-245">“元素”工具中的完整辅助功能树视图</span><span class="sxs-lookup"><span data-stu-id="58f61-245">Full accessibility tree view in the Elements tool</span></span>  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

<span data-ttu-id="58f61-246">此试验在“**元素**”工具中提供**完整的辅助功能树视图**。</span><span class="sxs-lookup"><span data-stu-id="58f61-246">This experiment provides a **full accessibility tree view** in the **Elements** tool.</span></span>  <span data-ttu-id="58f61-247">“[辅助功能][DevtoolsAccessibilityReferenceAccessibilityPanel]”窗格提供部分辅助功能树视图，其显示从根节点到被检查节点的直接上级链。</span><span class="sxs-lookup"><span data-stu-id="58f61-247">The [Accessibility][DevtoolsAccessibilityReferenceAccessibilityPanel] pane provides a partial accessibility tree view, that displays the direct ancestor chain from the root node to the inspected node.</span></span>  
<span data-ttu-id="58f61-248">启用此试验并重新加载 DevTools 后，请选择以下按钮之一以在“元素”工具中切换网页上所有元素的显示。</span><span class="sxs-lookup"><span data-stu-id="58f61-248">After you turn on this experiment and reload the DevTools, choose one of the following buttons to switch the display in the Elements tool for all elements on the webpage.</span></span>  

*   <span data-ttu-id="58f61-249">若要显示完整的辅助功能树视图，请选择“**切换到辅助功能树视图**”。</span><span class="sxs-lookup"><span data-stu-id="58f61-249">To display the full accessibility tree view , choose the **Switch to Accessibility Tree view**.</span></span>  
*   <span data-ttu-id="58f61-250">若要显示 DOM 树视图，请选择“**切换到 DOM 树视图**”。</span><span class="sxs-lookup"><span data-stu-id="58f61-250">To display the DOM tree view, choose the **Switch to DOM Tree view**.</span></span>  
    
<span data-ttu-id="58f61-251">若要启用试验，请导航至“[启用试验功能][DevtoolsExperimentalFeaturesIndexTurnOnExperimentalFeatures]”，然后选中“**在‘元素’窗格中启用完整的辅助功能树视图**”旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="58f61-251">To turn on the experiment, navigate to [Turn on experimental features][DevtoolsExperimentalFeaturesIndexTurnOnExperimentalFeatures] and choose the checkbox next to **Enable full accessibility tree view in Elements pane**.</span></span>  <span data-ttu-id="58f61-252">若要在 Chromium 开源项目中查看此功能的历史记录，请导航至问题 [887173][CR887173]。</span><span class="sxs-lookup"><span data-stu-id="58f61-252">To review the history of this feature in the Chromium open-source project, navigate to Issue [887173][CR887173].</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/02/elements-switch-to-accessibility-tree-view.msft.png" alt-text="显示 DOM 树视图" lightbox="../../media/2021/02/elements-switch-to-accessibility-tree-view.msft.png":::
         <span data-ttu-id="58f61-254">显示 **DOM 视图**</span><span class="sxs-lookup"><span data-stu-id="58f61-254">Display the **DOM view**</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/02/elements-switch-to-dom-tree-view.msft.png" alt-text="显示完整的辅助功能树视图" lightbox="../../media/2021/02/elements-switch-to-dom-tree-view.msft.png":::
         <span data-ttu-id="58f61-256">显示**完整的辅助功能树视图**</span><span class="sxs-lookup"><span data-stu-id="58f61-256">Display the **Full Accessibility Tree view**</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="download-the-microsoft-edge-preview-channels"></a><span data-ttu-id="58f61-257">下载 Microsoft Edge 预览频道</span><span class="sxs-lookup"><span data-stu-id="58f61-257">Download the Microsoft Edge preview channels</span></span>  

<span data-ttu-id="58f61-258">如果你使用的是 Windows、Linux 或 macOS，请考虑使用 [ Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels]作为默认开发浏览器。</span><span class="sxs-lookup"><span data-stu-id="58f61-258">If you are on Windows, Linux, or macOS, consider using the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] as your default development browser.</span></span>  <span data-ttu-id="58f61-259">预览频道使你能够访问最新的 DevTools 功能。</span><span class="sxs-lookup"><span data-stu-id="58f61-259">The preview channels give you access to the latest DevTools features.</span></span>  

## <a name="getting-in-touch-with-microsoft-edge-devtools-team"></a><span data-ttu-id="58f61-260">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="58f61-260">Getting in touch with Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]

<!-- links -->  

[DevtoolsAccessibilityReferenceAccessibilityPanel]: ../../../accessibility/reference.md#the-accessibility-panel "“辅助功能”窗格 - 辅助功能参考 | Microsoft Docs"  
[DevtoolsCommandMenuIndex]: ../../../command-menu/index.md "使用 Microsoft Edge DevTools 命令菜单运行命令 | Microsoft Docs"  
[DevtoolsConsoleReferenceFilterByLogLevel]: ../../../console/reference.md#filter-by-log-level "按日志级别筛选 - 控制台参考 | Microsoft Docs"  
[DevtoolsConsoleReferenceFilterMessages]: ../../../console/reference.md#filter-messages "筛选消息 - 控制台参考 | Microsoft Docs"  
[DevtoolsConsoleReferenceOpenConsoleSidebar]: ../../../console/reference.md#open-the-console-sidebar "打开控制台边栏 - 控制台参考 | Microsoft Docs"  
[DevtoolsCustomizeIndexSettings]: ../../../customize/index.md#settings "设置 - 自定义 Microsoft Edge DevTools | Microsoft Docs"  
[DevtoolsCustomizeShortcuts]: ../../../customize/shortcuts.md "自定义 Microsoft Edge DevTools 中的键盘快捷方式 | Microsoft Docs"  
[DevtoolsExperimentalFeaturesIndexEnablePlusButtonTabMenusToOpenMoreTools]: ../../../experimental-features/index.md#enable--button-tab-menus-to-open-more-tools "启用 + 按钮选项卡菜单以打开更多工具 - 试验功能 | Microsoft Docs"  
[DevtoolsExperimentalFeaturesIndexTurnOnExperimentalFeatures]: ../../../experimental-features/index.md#turn-on-experimental-features "打开试验功能 - 试验功能 | Microsoft Docs"  
[DevtoolsNetworkReferenceAddRemoveColumns]: ../../../network/reference.md#add-or-remove-columns "添加或删除列 - 网络分析参考 | Microsoft Docs"  
[DevtoolsNetworkReferenceDisplayInitiatorsDependencies]: ../../../network/reference.md#display-initiators-and-dependencies "显示发起程序和依赖项 - 网络分析参考 | Microsoft Docs"  

[ProgressiveWebAppsIndex]: ../../../../progressive-web-apps-chromium/index.md "Windows 上的渐进式 Web 应用概述 | Microsoft Docs"  

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download "Microsoft Edge 预览频道"  

[VisualstudioCodeDocsEditorExtensionGalleryUpdateExtensionManually]: https://code.visualstudio.com/docs/editor/extension-gallery#_update-an-extension-manually "手动更新扩展 - Extension Marketplace | Visual Studio Code"  

[VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools]: https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools "Microsoft Edge Tools for Visual Studio Code | Visual Studio Marketplace"  

[ChromeDeveloperBlogImprovedPwaOfflineDetection]: https://developer.chrome.com/blog/improved-pwa-offline-detection "改进渐进式 Web 应用脱机支持检测 | Chrome 开发人员"  

[ChromestatusFeature5354410980933632]: https://www.chromestatus.com/feature/5354410980933632 "色域媒体功能 | Chrome 平台状态"  

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium bug"  
[CR174309]: https://crbug.com/174309 "问题 174309：DevTools：允许自定义键盘快捷方式/键绑定 | Chromium bug"  
[CR887173]: https://crbug.com/887173 "问题 887173：DevTools：完整的辅助功能树检查 | Chromium bug"  
[CR965802]: https://crbug.com/965802 "问题 965802：实现更准确的服务工作进程脱机功能检测 | Chromium bug"  
[CR1073887]: https://crbug.com/1073887 "问题 1073887：DevTools：@media (color-gamut: ...) 颜色空间模拟 | Chromium bug"  
[CR1128885]: https://crbug.com/1128885 "问题 1128885：DevTools 对 CORS-RFC1918 的支持 | Chromium bug"  
[CR1146450]: https://crbug.com/1146450 "问题 1146450：[Android] 实施底页安装 | Chromium bug"  
[CR1158276]: https://crbug.com/1158276 "问题 1158276：在 DevTools 的“网络”部分中无法使用箭头键展开/收起“请求发起程序链”窗格 | Chromium bug"  
[CR1158827]: https://crbug.com/1158827 "问题 1158827：[权限策略] 实现对权限策略的 devtool 支持 | Chromium bug"  
[CR1160637]: https://crbug.com/1160637 "问题 1160637：在“开发人员工具”窗口的“网络”部分发现“请求发起程序链”上的焦点不完整 | Chromium bug"  
[CR1161427]: https://crbug.com/1161427 "问题 1161427：&#9730; 在 DevTools 中支持 SameParty Cookie 属性调试 | Chromium bug"  
[CR1166710]: https://crbug.com/1166710 "问题 1166710：默认情况下打开弹性框工具试验 | Chromium bug"  
[CR1169689]: https://crbug.com/1169689 "问题 1169689：PWA 安装底页不应具有类别 | Chromium bug"  
[CR1175699]: https://crbug.com/1175699 "问题 1175699：弹性框编辑器 | Chromium bug"  
[CR1177685]: https://crbug.com/1177685 "问题 1177685：删除非标准 fn.displayName 支持 | Chromium bug"  
[CR1178530]: https://crbug.com/1178530 "问题 1178530：在打印字符串时，控制台不会转义双引号 | Chromium bug"  

[CsswgDraftsMediaqueries4ColorGamut]: https://drafts.csswg.org/mediaqueries-4#color-gamut "颜色显示质量：“色域”功能 | CSS 工作组编辑器草稿"  

[GithubMicrosoftedgeMsedgeexplainersBlobMainDevtoolsFocusmodeExplainer]: https://github.com/MicrosoftEdge/MSEdgeExplainers/blob/main/DevTools/FocusMode/explainer.md "DevTools：焦点模式 UI - MicrosoftEdge/MSEdgeExplainers | GitHub"  

[GithubMicrosoftVscodeEdgeDevtools]: https://github.com/microsoft/vscode-edge-devtools "microsoft/vscode-edge-devtools | GitHub"  

[GithubPrivacycgFirstPartySets]: https://github.com/privacycg/first-party-sets "第一方集 | GitHub"  

[GithubW3cWebappsecPermissionsPolicyBlobMainPermissionsPolicyExplainer]: https://github.com/w3c/webappsec-permissions-policy/blob/main/permissions-policy-explainer.md "权限策略解释器 | GitHub"  

[MdnJavascriptReferenceGlobalObjectsFunctionName]: https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Function/name "Function.name | MDN"  

> [!NOTE]
> <span data-ttu-id="58f61-300">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="58f61-300">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="58f61-301">原始页面位于 [此处](https://developer.chrome.com/blog/new-in-devtools-90)，并由 [Jecelyn Yeen][JecelynYeen] \（开发人员支持者，Chrome DevTools\）制作。</span><span class="sxs-lookup"><span data-stu-id="58f61-301">The original page is found [here](https://developer.chrome.com/blog/new-in-devtools-90) and is authored by [Jecelyn Yeen][JecelynYeen] \(Developer advocate, Chrome DevTools\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="58f61-303">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="58f61-303">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors#jecelyn-yeen  
