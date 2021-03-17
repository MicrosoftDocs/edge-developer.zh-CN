---
description: Microsoft Edge DevTools 中的最新实验功能
title: 实验功能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/15/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， Web 开发， f12 工具， 开发工具， 实验
no-loc:
- Enable webhint
- Enable Network Console
- Source Order Viewer
- Enable Composited Layers in 3D View
- Enable new Font Editor tool within the Styles pane
- Enable new CSS Flexbox debugging features
- Enable + button tab menus to open more tools
- Enable Welcome tab
- 3D View
- Turn on support to move tabs between panels
- Match keyboard shortcuts in the DevTools to Microsoft Visual Studio Code
- Edit keyboard shortcuts for any action in the DevTools
- Turn on new CSS grid debugging features
- 'Emulation: Support dual screen mode'
ms.openlocfilehash: c76830cb8bbcc597aa026f58e1926cd2f9bc2d62
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439582"
---
# <a name="experimental-features"></a><span data-ttu-id="ec0ad-104">实验功能</span><span class="sxs-lookup"><span data-stu-id="ec0ad-104">Experimental features</span></span>  

<span data-ttu-id="ec0ad-105">Microsoft Edge DevTools 提供对仍在开发中的实验性功能的访问权限。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-105">Microsoft Edge DevTools provide access to experimental features that are still in development.</span></span>  <span data-ttu-id="ec0ad-106">您可以在发布每个 [功能之前](#providing-feedback-on-experimental-features) 进行测试并提供反馈。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-106">You may test and [provide feedback](#providing-feedback-on-experimental-features) before each feature is released.</span></span>  

<span data-ttu-id="ec0ad-107">尽管实验功能在 Microsoft Edge 的所有渠道中都可用，但你可能会使用 Microsoft Edge Canary 渠道获取最新的实验功能。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-107">While experimental features are available in all channels of Microsoft Edge, you may get the latest experimental features using the Microsoft Edge Canary channel.</span></span>  

## <a name="turn-on-experimental-features"></a><span data-ttu-id="ec0ad-108">打开实验性功能</span><span class="sxs-lookup"><span data-stu-id="ec0ad-108">Turn on experimental features</span></span>  

<span data-ttu-id="ec0ad-109">若要在 Microsoft Edge (\) 或关闭\) 实验功能，请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-109">To turn on \(or off\) experimental features in Microsoft Edge, complete the following steps.</span></span>  

1.  <span data-ttu-id="ec0ad-110">[打开 DevTools][DevtoolsOpenIndex]。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-110">[Open DevTools][DevtoolsOpenIndex].</span></span>  
    *   <span data-ttu-id="ec0ad-111">选择 `Control` + `Shift` + `I` \ (Windows、Linux\) 或 `Command` + `Option` + `I` \ (macOS\) 。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-111">Select `Control`+`Shift`+`I` \(Windows, Linux\) or `Command`+`Option`+`I` \(macOS\).</span></span>  <span data-ttu-id="ec0ad-112">有关详细信息，请导航到 [Microsoft Edge DevTools 键盘快捷方式][DevtoolsShortcutsIndex]。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-112">For more information, navigate to [Microsoft Edge DevTools keyboard shortcuts][DevtoolsShortcutsIndex].</span></span>  
1.  <span data-ttu-id="ec0ad-113">打开" [设置"][DevToolsCustomizeIndexSettings] 窗格。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-113">Open the [Settings][DevToolsCustomizeIndexSettings] pane.</span></span>  
    *   <span data-ttu-id="ec0ad-114">选择 `Shift` + `?` 。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-114">Select `Shift`+`?`.</span></span>  <span data-ttu-id="ec0ad-115">有关详细信息，请导航到 [Microsoft Edge DevTools 键盘快捷方式][DevtoolsShortcutsIndex]。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-115">For more information, navigate to [Microsoft Edge DevTools keyboard shortcuts][DevtoolsShortcutsIndex].</span></span>  
1.  <span data-ttu-id="ec0ad-116">在"设置"窗格 **的左侧** ，选择"实验 **"** 部分。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-116">On the left side of the **Settings** pane, choose the **Experiments** section.</span></span>  
    
    :::image type="complex" source="../media/experiments-devtools.msft.png" alt-text=""设置"中的"实验"页面" lightbox="../media/experiments-devtools.msft.png":::
       <span data-ttu-id="ec0ad-118">" **设置"** 中的"实验 **"页面**</span><span class="sxs-lookup"><span data-stu-id="ec0ad-118">The **Experiments** page in **Settings**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="ec0ad-119">在 **实验** 页面上，滚动浏览所有可用实验功能的列表，并选中要测试的每个功能旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-119">On the **Experiments** page, scroll through the list of all available experimental features and choose the checkbox next to each feature that you want to test.</span></span>  
1.  <span data-ttu-id="ec0ad-120">关闭并重新打开 Microsoft Edge DevTools。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-120">Close and reopen Microsoft Edge DevTools.</span></span>  
    
> [!NOTE]
> <span data-ttu-id="ec0ad-121">实验性功能会不断更新，并且可能会导致性能问题。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-121">Experimental features are constantly being updated and may cause performance issues.</span></span>  <span data-ttu-id="ec0ad-122">若要关闭实验功能，请打开实验 **页面** 并清除要关闭的实验功能复选框。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-122">To turn off an experimental feature, open the **Experiments** page and clear the checkbox of the experimental feature that you want to turn off.</span></span>  

## <a name="highlighted-experimental-features"></a><span data-ttu-id="ec0ad-123">突出显示的实验功能</span><span class="sxs-lookup"><span data-stu-id="ec0ad-123">Highlighted experimental features</span></span>  

<span data-ttu-id="ec0ad-124">以下各节介绍 Microsoft Edge 中提供的新实验功能。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-124">The following sections describe the new experimental features that are available in Microsoft Edge.</span></span>  

| <span data-ttu-id="ec0ad-125">实验性功能</span><span class="sxs-lookup"><span data-stu-id="ec0ad-125">Experimental feature</span></span> | <span data-ttu-id="ec0ad-126">Microsoft Edge 版本</span><span class="sxs-lookup"><span data-stu-id="ec0ad-126">Microsoft Edge version</span></span> |  
|:--- |:--- |  
| [Enable webhint](#enable-webhint) | <span data-ttu-id="ec0ad-127">85 或更高版本</span><span class="sxs-lookup"><span data-stu-id="ec0ad-127">85 or later</span></span> |  
| [Enable Network Console](#enable-network-console) | <span data-ttu-id="ec0ad-128">85 或更高版本</span><span class="sxs-lookup"><span data-stu-id="ec0ad-128">85 or later</span></span> |  
| [Source Order Viewer](#source-order-viewer) | <span data-ttu-id="ec0ad-129">86 或更高版本</span><span class="sxs-lookup"><span data-stu-id="ec0ad-129">86 or later</span></span> |  
| [Enable Composited Layers in 3D View](#enable-composited-layers-in-3d-view) | <span data-ttu-id="ec0ad-130">87 或更高版本</span><span class="sxs-lookup"><span data-stu-id="ec0ad-130">87 or later</span></span> |  
| [Enable new Font Editor tool within the Styles pane](#enable-new-font-editor-tool-within-the-styles-pane) | <span data-ttu-id="ec0ad-131">89 或更高版本</span><span class="sxs-lookup"><span data-stu-id="ec0ad-131">89 or later</span></span> |  
| [Enable new CSS Flexbox debugging features](#enable-new-css-flexbox-debugging-features) | <span data-ttu-id="ec0ad-132">89 或更高版本</span><span class="sxs-lookup"><span data-stu-id="ec0ad-132">89 or later</span></span> |  
| [Enable + button tab menus to open more tools](#enable--button-tab-menus-to-open-more-tools) | <span data-ttu-id="ec0ad-133">89 或更高版本</span><span class="sxs-lookup"><span data-stu-id="ec0ad-133">89 or later</span></span> |  
| [Enable Welcome tab](#enable-welcome-tab) | <span data-ttu-id="ec0ad-134">89 或更高版本</span><span class="sxs-lookup"><span data-stu-id="ec0ad-134">89 or later</span></span> |  

### Enable webhint  

<span data-ttu-id="ec0ad-135">[webhint][WebhintMain] 是一个开放源代码工具，可为网站和本地网页提供实时反馈。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-135">[webhint][WebhintMain] is an open-source tool that provides real-time feedback for websites and local webpages.</span></span>  <span data-ttu-id="ec0ad-136">Webhint 提供 [的反馈类型][WebhintMain]。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-136">The type of feedback provided by [webhint][WebhintMain].</span></span>  

*   <span data-ttu-id="ec0ad-137">辅助功能</span><span class="sxs-lookup"><span data-stu-id="ec0ad-137">accessibility</span></span>  
*   <span data-ttu-id="ec0ad-138">跨浏览器兼容性</span><span class="sxs-lookup"><span data-stu-id="ec0ad-138">cross-browser compatibility</span></span>  
*   <span data-ttu-id="ec0ad-139">安全性</span><span class="sxs-lookup"><span data-stu-id="ec0ad-139">security</span></span>  
*   <span data-ttu-id="ec0ad-140">性能</span><span class="sxs-lookup"><span data-stu-id="ec0ad-140">performance</span></span>  
*   <span data-ttu-id="ec0ad-141">渐进式 Web (PBA) </span><span class="sxs-lookup"><span data-stu-id="ec0ad-141">Progressive Web Apps (PWAs)</span></span>  
*   <span data-ttu-id="ec0ad-142">其他常见的 Web 开发问题</span><span class="sxs-lookup"><span data-stu-id="ec0ad-142">other common web development issues</span></span>  
    
<span data-ttu-id="ec0ad-143">[Webhint 实验][WebhintMain]在问题面板中显示[Webhint][DevtoolsIssuesIndex]反馈。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-143">The [webhint][WebhintMain] experiment displays the webhint feedback in the [Issues][DevtoolsIssuesIndex] panel.</span></span>  <span data-ttu-id="ec0ad-144">选择一个问题，在网站上显示解决方案文档和受影响资源的列表。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-144">Choose an issue to display solution documentation and a list of the affected resources on your website.</span></span>  <span data-ttu-id="ec0ad-145">选择资源链接以在 DevTools\*\*\*\*\*\*中\*\*打开\*\*\*\* 相关的"网络、源"或"元素"窗格。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-145">Choose a resource link to open the relevant **Network**, **Sources**, or **Elements** pane in DevTools.</span></span>  

:::image type="complex" source="../media/experiments-webhint.msft.png" alt-text="问题面板中的 webhint 反馈" lightbox="../media/experiments-webhint.msft.png":::
   <span data-ttu-id="ec0ad-147">问题面板中的 **webhint** 反馈</span><span class="sxs-lookup"><span data-stu-id="ec0ad-147">webhint feedback in the **Issues** panel</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### Enable Network Console  

<span data-ttu-id="ec0ad-148">**网络控制台** 是实验通过 HTTP 提出综合网络请求的工作主题。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-148">**Network Console** is the working title of an experiment to make synthetic network requests over HTTP.</span></span>  <span data-ttu-id="ec0ad-149">可以使用网络 **控制台实验** 发送 Web API 请求。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-149">You may use the **Network Console** experiment to send web API requests.</span></span>  

<span data-ttu-id="ec0ad-150">打开实验后，请确保重新启动 DevTools。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-150">After you turn on the experiment, ensure you restart the DevTools.</span></span>  <span data-ttu-id="ec0ad-151">若要使用 **网络控制台**，请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-151">To use the **Network Console**, complete the following steps.</span></span>  

1.  <span data-ttu-id="ec0ad-152">打开" **网络"** 窗格。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-152">Open the **Network** pane.</span></span>  
1.  <span data-ttu-id="ec0ad-153">查找要更改和重新发送的网络请求。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-153">Find the network request that you want to change and resend.</span></span>  
1.  <span data-ttu-id="ec0ad-154">打开上下文菜单 \ (右键单击\) ，然后选择编辑 **和重播**。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-154">Open the contextual menu \(right-click\), and choose **Edit and Replay**.</span></span>  
1.  <span data-ttu-id="ec0ad-155">当网络 **控制台打开** 时，编辑网络请求信息。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-155">When the **Network Console** opens, edit the network request information.</span></span>  
1.  <span data-ttu-id="ec0ad-156">选择 **"发送"。**</span><span class="sxs-lookup"><span data-stu-id="ec0ad-156">Choose **Send**.</span></span>  
    
:::image type="complex" source="../media/network-network-console.msft.png" alt-text="控制台箱中的网络控制台" lightbox="../media/network-network-console.msft.png":::
   <span data-ttu-id="ec0ad-158">**控制台箱\*\*\*\*中的网络**控制台</span><span class="sxs-lookup"><span data-stu-id="ec0ad-158">**Network Console** in the **Console** drawer</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 85 and later.  -->  

### Source Order Viewer  

<span data-ttu-id="ec0ad-159">**Source Order Viewer** 是显示网页源中元素顺序的实验。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-159">**Source Order Viewer** is an experiment that displays the order of elements in the webpage source.</span></span>  <span data-ttu-id="ec0ad-160">屏幕显示顺序可能与源的顺序不同，这会使屏幕阅读器和键盘用户混淆。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-160">The on-screen display order may differ from the order of the source, which confuses screen reader and keyboard users.</span></span>  <span data-ttu-id="ec0ad-161">使用 **Source Order Viewer** 实验查找屏幕显示顺序和源的顺序之间的差异。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-161">Use the **Source Order Viewer** experiment to find the differences between on-screen display order and the order of the source.</span></span>  

<span data-ttu-id="ec0ad-162">打开实验后，请确保重新启动 DevTools。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-162">After you turn on the experiment, ensure you restart the DevTools.</span></span>  <span data-ttu-id="ec0ad-163">若要使用 **Source Order Viewer** ，请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-163">To use **Source Order Viewer**, complete the following steps.</span></span>  

1.  <span data-ttu-id="ec0ad-164">打开 **"元素"** 工具。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-164">Open the **Elements** tool.</span></span>  
1.  <span data-ttu-id="ec0ad-165">打开 **"辅助功能"** 窗格， (底部\) 面板。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-165">Open the **Accessibility** pane in the drawer \(bottom\) panel.</span></span>  
1.  <span data-ttu-id="ec0ad-166">在部分 **Source Order Viewer** 下，选中" **显示源订单"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-166">Under the **Source Order Viewer** section, choose the **Show Source Order** checkbox.</span></span>  
1.  <span data-ttu-id="ec0ad-167">突出显示任何 HTML 元素以显示网页源中顺序的覆盖。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-167">Highlight any HTML element to display an overlay that the order in the webpage source.</span></span>  
    
:::image type="complex" source="../media/experiments-source-order-viewer.msft.png" alt-text=":::<span data-ttu-id="ec0ad-168">no-loc (源订单查看器) ：：： 在辅助功能窗格中" lightbox="。。/media/experiments-source-order-viewer.msft.png"：：： **Source Order Viewer** 在**辅助功能窗格中**</span><span class="sxs-lookup"><span data-stu-id="ec0ad-168">no-loc(Source Order Viewer)::: in the Accessibility pane" lightbox="../media/experiments-source-order-viewer.msft.png"::: **Source Order Viewer** in the **Accessibility** pane</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 86 and later.  -->  

### Enable Composited Layers in 3D View  

<span data-ttu-id="ec0ad-169">现在，你可以将 Layers 与 z 索引和文档对象模型 \ (DOM\) 一起可视化。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-169">You may now visualize Layers alongside z-indexes and the Document Object Model \(DOM\).</span></span>  <span data-ttu-id="ec0ad-170">此功能可帮助您在不经常切换上下文的情况下进行调试。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-170">This feature helps you debug without switching contexts as often.</span></span>  <span data-ttu-id="ec0ad-171">您确定减少上下文切换是一个主要的难点。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-171">You identified that reducing context-switching was a major pain point.</span></span>  <span data-ttu-id="ec0ad-172">并非始终清楚您编写的代码对 Web 应用有何影响。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-172">It is not always clear how the code you write affects your web app.</span></span>  <span data-ttu-id="ec0ad-173">为了获得全面的视觉调试体验，现在组合了 和 3D View 复合层。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-173">For a comprehensive visual debugging experience, the 3D View and Composited Layers are now combined.</span></span>  

<span data-ttu-id="ec0ad-174">打开实验后，请确保重新启动 DevTools。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-174">After you turn on the experiment, ensure you restart the DevTools.</span></span>  <span data-ttu-id="ec0ad-175">若要使用 **复合层**，请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-175">To use **Composited Layers**, complete the following steps.</span></span>  

1.  <span data-ttu-id="ec0ad-176">在"箱"上，选择 **3D View** 工具。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-176">On the drawer, choose the **3D View** tool.</span></span>  
1.  <span data-ttu-id="ec0ad-177">打开 **"复合层"** 窗格。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-177">Open the **Composited Layers** pane.</span></span>  
1.  <span data-ttu-id="ec0ad-178">将显示应用的所有绘制图层。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-178">All of the painted layers of the app are displayed.</span></span>  <span data-ttu-id="ec0ad-179">使用你自己的 Web 应用试用此功能。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-179">Try this feature with your own web apps.</span></span>  
    
:::image type="complex" source="../media/experiments-layers.msft.png" alt-text="复合层窗格" lightbox="../media/experiments-layers.msft.png":::
   <span data-ttu-id="ec0ad-181">**复合层** 窗格</span><span class="sxs-lookup"><span data-stu-id="ec0ad-181">**Composited Layers** pane</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 87 and later.  -->  

### Enable new Font Editor tool within the Styles pane  

<span data-ttu-id="ec0ad-182">现在，可以使用新的可视 [字体编辑器][DevtoolsInspectStylesEditFonts] 来编辑字体。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-182">You may now use the new visual [Font Editor][DevtoolsInspectStylesEditFonts] to edit fonts.</span></span>  <span data-ttu-id="ec0ad-183">使用它定义字体和字体特征。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-183">Use it define fonts and font characteristics.</span></span>  <span data-ttu-id="ec0ad-184">可视 **字体编辑器** 可帮助您完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-184">The visual **Font Editor** helps you complete the following actions.</span></span>  

*   <span data-ttu-id="ec0ad-185">在不同字体属性的单位之间切换</span><span class="sxs-lookup"><span data-stu-id="ec0ad-185">Switch between units for different font properties</span></span>  
*   <span data-ttu-id="ec0ad-186">在不同字体属性的关键字之间切换</span><span class="sxs-lookup"><span data-stu-id="ec0ad-186">Switch between keywords for different font properties</span></span>  
*   <span data-ttu-id="ec0ad-187">转换单位</span><span class="sxs-lookup"><span data-stu-id="ec0ad-187">Convert units</span></span>  
*   <span data-ttu-id="ec0ad-188">生成准确的 CSS 代码</span><span class="sxs-lookup"><span data-stu-id="ec0ad-188">Generate accurate CSS code</span></span>  
    
<span data-ttu-id="ec0ad-189">打开实验后，请确保重新启动 DevTools。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-189">After you turn on the experiment, ensure you restart the DevTools.</span></span>  <span data-ttu-id="ec0ad-190">若要使用新的可视化 **字体编辑器，** 请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-190">To use the new visual **Font Editor**, complete the following steps.</span></span>  

1.  <span data-ttu-id="ec0ad-191">打开 **"元素"** 工具。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-191">Open the **Elements** tool.</span></span>  
1.  <span data-ttu-id="ec0ad-192">打开 **"样式"** 窗格。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-192">Open the **Styles** pane.</span></span>  
1.  <span data-ttu-id="ec0ad-193">选择" **字体编辑器"** 图标。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-193">Choose the **Font Editor** icon.</span></span>  
    
<span data-ttu-id="ec0ad-194">有关新的可视字体编辑器 **的详细信息**，请导航到 [DevTools][DevtoolsInspectStylesEditFonts]的样式窗格中的编辑 CSS 字体样式和设置。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-194">For more information about the new visual **Font Editor**, navigate to [Edit CSS font styles and settings in the Styles pane in DevTools][DevtoolsInspectStylesEditFonts].</span></span>  

:::image type="complex" source="../media/font-editor-open.msft.png" alt-text="突出显示可视字体编辑器窗格" lightbox="../media/font-editor-open.msft.png":::
   <span data-ttu-id="ec0ad-196">突出显示可视 **字体编辑器** 窗格</span><span class="sxs-lookup"><span data-stu-id="ec0ad-196">The visual **Font Editor** pane is highlighted</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 89 and later.  -->  

### Enable new CSS Flexbox debugging features  

<span data-ttu-id="ec0ad-197">此实验性功能提供了许多新的可视化效果，可帮助你调试 CSS Flexbox 布局。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-197">This experimental feature provides many new visualizations to help you debug CSS Flexbox layouts.</span></span>  <span data-ttu-id="ec0ad-198">若要预览最新的实验功能， [请打开此实验](#turn-on-experimental-features) 并重新加载 DevTools。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-198">To preview the latest experimental features, [turn on this experiment](#turn-on-experimental-features) and reload DevTools.</span></span>  

#### <a name="display-persistent-overlays-on-flexbox-layouts-with-the-inspect-tool"></a><span data-ttu-id="ec0ad-199">使用 Inspect 工具在 Flexbox 布局上显示永久性覆盖</span><span class="sxs-lookup"><span data-stu-id="ec0ad-199">Display persistent overlays on Flexbox layouts with the Inspect tool</span></span>  

<span data-ttu-id="ec0ad-200">Inspect **工具** 提供了一种快速方法，通过将鼠标悬停在网站中的 CSS Flexbox 布局来标识和可视化它们。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-200">The **Inspect** tool provides a quick way to identify and visualize CSS Flexbox layouts in a website by hovering on them with the mouse.</span></span>  <span data-ttu-id="ec0ad-201">选择 **DevTools** (左上角的"检查 \ (检查 ![ ](../media/inspect-icon.msft.png) \) "图标。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-201">Choose the **Inspect** \(![Inspect](../media/inspect-icon.msft.png)\) icon in the top-left corner of DevTools.</span></span>  <span data-ttu-id="ec0ad-202">然后，在调试网站时，将鼠标悬停在弹性容器上，以显示弹性容器周围的轮廓。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-202">Then, while debugging the website, hover on a flex container to display outlines around the flex container.</span></span>  

:::image type="complex" source="../media/flexbox-hover.msft.png" alt-text="使用 Inspect 工具显示 Flexbox 容器" lightbox="../media/flexbox-hover.msft.png":::
   <span data-ttu-id="ec0ad-204">使用 Inspect 工具显示 Flexbox**容器**</span><span class="sxs-lookup"><span data-stu-id="ec0ad-204">Display Flexbox containers with the **Inspect** tool</span></span>  
:::image-end:::  

#### <a name="display-persistent-overlays-on-flexbox-layouts"></a><span data-ttu-id="ec0ad-205">在 Flexbox 布局上显示永久性覆盖</span><span class="sxs-lookup"><span data-stu-id="ec0ad-205">Display persistent overlays on Flexbox layouts</span></span>  

<span data-ttu-id="ec0ad-206">在 Microsoft Edge 版本 89 或更高版本中，实验 CSS Flexbox 功能还提供了在 Flexbox 布局上打开永久性覆盖的选项。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-206">In Microsoft Edge version 89 or later, the experimental CSS Flexbox feature also offers the option to turn on persistent overlays on Flexbox layouts.</span></span>  <span data-ttu-id="ec0ad-207">永久性覆盖具有以下优点。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-207">Persistent overlays provide the following benefits.</span></span>  

*   <span data-ttu-id="ec0ad-208">滚动、移动鼠标并使用 DevTools 的其他功能时，永久性覆盖在网页上仍然可见。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-208">Persistent overlays remain visible on the webpage as you scroll, move your mouse, and use other features of the DevTools.</span></span>
*   <span data-ttu-id="ec0ad-209">可以同时使用多个永久性覆盖，以便你可以一次查看多个 Flexbox 布局。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-209">Multiple persistent overlays may be used at the same time, to allow you to review several Flexbox layouts at once.</span></span>  
*   <span data-ttu-id="ec0ad-210">永久性覆盖提供颜色配置选项。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-210">Persistent overlays offer color configuration options.</span></span>  
    
<span data-ttu-id="ec0ad-211">若要切换 Flexbox 布局上的永久性覆盖，请使用下列操作之一。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-211">To toggle persistent overlays on Flexbox layout, use one of following actions.</span></span>  

*   <span data-ttu-id="ec0ad-212">选择 **"元素"** 工具的 DOM 树中显示的任意 Flexbox 容器旁边的 Flexbox **椭圆图标** 。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-212">Choose the **Flexbox** oval icon next to any Flexbox container displayed in the DOM tree of the **Elements** tool.</span></span>  
*   <span data-ttu-id="ec0ad-213">打开位于" **元素** "工具 **中的新布局** 面板，并选中要突出显示的每个 Flexbox 容器旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-213">Open the new **Layout** panel located in the **Elements** tool, and choose the checkbox next to each Flexbox container you want to highlight.</span></span>  
    
:::image type="complex" source="../media/flexbox-overlay.msft.png" alt-text="DevTools 中的弹性图标和布局面板" lightbox="../media/flexbox-overlay.msft.png":::
   <span data-ttu-id="ec0ad-215">DevTools **中的** 弹性图标和布局面板</span><span class="sxs-lookup"><span data-stu-id="ec0ad-215">Flex icons and **Layout** panel in DevTools</span></span>  
:::image-end:::  

#### <a name="configure-persistent-overlays"></a><span data-ttu-id="ec0ad-216">配置永久性覆盖</span><span class="sxs-lookup"><span data-stu-id="ec0ad-216">Configure persistent overlays</span></span>  

<span data-ttu-id="ec0ad-217">若要为 CSS 网格或 Flexbox 布局配置永久覆盖的选项，请使用"布局 **"** 窗格。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-217">To configure options for persistent overlays for CSS grids or Flexbox layouts, use the **Layout** pane.</span></span>  <span data-ttu-id="ec0ad-218">"**布局**"窗格位于"样式"\*\*\*\* 和"计算"窗格\*\*\*\* 旁边的"元素 **"工具**中。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-218">The **Layout** pane is located in the **Elements** tool next to the **Styles** and **Computed** panes.</span></span>  

:::image type="complex" source="../media/flexbox-layout.msft.png" alt-text="布局面板" lightbox="../media/flexbox-layout.msft.png":::
   <span data-ttu-id="ec0ad-220">布局面板</span><span class="sxs-lookup"><span data-stu-id="ec0ad-220">Layout panel</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 89 and later.  -->  

### Enable + button tab menus to open more tools  

<span data-ttu-id="ec0ad-221">现在，可以使用新的"更多工具"\ (\*\*\*\* `+` \) 图标打开更多工具。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-221">You may now open more tools using the new **More Tools** \(`+`\) icon.</span></span>  <span data-ttu-id="ec0ad-222">打开实验并重新加载 DevTools 后，在 DevTools 顶部的选项卡组右侧显示加号 **Enable + button tab menus to open more tools** `+` \ (\) 。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-222">After you turn on the **Enable + button tab menus to open more tools** experiment and reload DevTools, a plus sign \(`+`\) displays to the right of the tab group at the top of the DevTools.</span></span>  <span data-ttu-id="ec0ad-223">若要显示可添加到选项卡栏的其他工具的列表，请选择新的"更多工具"\ (\*\*\*\* `+` \) 图标。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-223">To display a list of other tools that you may add to the tab bar, choose the new **More Tools** \(`+`\) icon.</span></span>  

:::image type="complex" source="../media/experiments-more-tools-button.msft.png" alt-text="顶部窗格中的更多工具" lightbox="../media/experiments-more-tools-button.msft.png":::
   <span data-ttu-id="ec0ad-225">**顶部窗格中** 的更多工具</span><span class="sxs-lookup"><span data-stu-id="ec0ad-225">**More Tools** in the top pane</span></span>
:::image-end:::  

<!--Available in Microsoft Edge version 89 and later.  -->  

### Enable Welcome tab

<span data-ttu-id="ec0ad-226">此实验使用新的欢迎 **工具** 替换新增 **功能** 工具。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-226">This experiment replaces the **What's New** tool with the new **Welcome** tool.</span></span>  <span data-ttu-id="ec0ad-227">它显示以下内容的刷新设计。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-227">It displays a refreshed design for the following content.</span></span>  

*   <span data-ttu-id="ec0ad-228">指向开发人员文档的链接</span><span class="sxs-lookup"><span data-stu-id="ec0ad-228">Links to developer docs</span></span>  
*   <span data-ttu-id="ec0ad-229">最新功能</span><span class="sxs-lookup"><span data-stu-id="ec0ad-229">the latest features</span></span>  
*   <span data-ttu-id="ec0ad-230">发行说明</span><span class="sxs-lookup"><span data-stu-id="ec0ad-230">release notes</span></span>  
*   <span data-ttu-id="ec0ad-231">联系 Microsoft Edge DevTools 团队的选项</span><span class="sxs-lookup"><span data-stu-id="ec0ad-231">Option to contact the Microsoft Edge DevTools team</span></span>  
    
<span data-ttu-id="ec0ad-232">每次 **更新** Microsoft Edge 后，欢迎工具都会自动打开。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-232">The **Welcome** tool opens automatically after each update to Microsoft Edge.</span></span>  <span data-ttu-id="ec0ad-233">若要防止每次更新后显示**欢迎**工具，请清除"欢迎使用工具"标题\*\*\*\* 下每个更新后"打开"\*\*\*\* 选项卡旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-233">To prevent the display of the **Welcome** tool after each update, clear the checkbox next to **Open tab after each update** under the **Welcome** tool title.</span></span>  

<span data-ttu-id="ec0ad-234">如果你更喜欢原始的**新增功能**工具，请[导航到设置][DevtoolsCustomizeIndexSettings]  >  **实验**并删除 旁边的复选框 **Enable Welcome tab** 。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-234">If you prefer the original **What's New** tool, navigate to [Settings][DevtoolsCustomizeIndexSettings] > **Experiments** and remove the checkbox next to **Enable Welcome tab**.</span></span>  

:::image type="complex" source="../media/experiments-welcome.msft.png" alt-text="欢迎工具" lightbox="../media/experiments-welcome.msft.png":::
   <span data-ttu-id="ec0ad-236">**欢迎** 工具</span><span class="sxs-lookup"><span data-stu-id="ec0ad-236">**Welcome** tool</span></span>  
:::image-end:::  

<!--Available in Microsoft Edge version 89 and later.  -->  

## <a name="previous-experimental-features"></a><span data-ttu-id="ec0ad-237">以前的实验功能</span><span class="sxs-lookup"><span data-stu-id="ec0ad-237">Previous experimental features</span></span>  

*   <span data-ttu-id="ec0ad-238">[3D View][Devtools3dViewIndex] 现在可用，在 Microsoft Edge 版本 83 或更高版本中默认处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-238">[3D View][Devtools3dViewIndex] is now available and turned on by default in Microsoft Edge version 83 or later.</span></span>  
*   <span data-ttu-id="ec0ad-239">[Turn on support to move tabs between panels][DevtoolsCustomizeIndex] 现在可用，在 Microsoft Edge 版本 85 或更高版本中默认处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-239">[Turn on support to move tabs between panels][DevtoolsCustomizeIndex] is now available and turned on by default in Microsoft Edge version 85 or later.</span></span>  
*   <span data-ttu-id="ec0ad-240">[Match keyboard shortcuts in the DevTools to Microsoft Visual Studio Code][DevtoolsCustomizeShortcutsMatchKeyboardShortcutsDevtoolsMicrosoftVisualStudioCode] 现在可用，在 Microsoft Edge 版本 86 或更高版本中默认处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-240">[Match keyboard shortcuts in the DevTools to Microsoft Visual Studio Code][DevtoolsCustomizeShortcutsMatchKeyboardShortcutsDevtoolsMicrosoftVisualStudioCode] is now available and turned on by default in Microsoft Edge version 86 or later.</span></span>  
*   <span data-ttu-id="ec0ad-241">[Edit keyboard shortcuts for any action in the DevTools][DevtoolsCustomizeShortcutsEditKeyboardShortcutsForAnyActionDevtools] 现在可用，在 Microsoft Edge 版本 89 或更高版本中默认处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-241">[Edit keyboard shortcuts for any action in the DevTools][DevtoolsCustomizeShortcutsEditKeyboardShortcutsForAnyActionDevtools] is now available and turned on by default in Microsoft Edge version 89 or later.</span></span>  
*   <span data-ttu-id="ec0ad-242">[Turn on new CSS grid debugging features][DevtoolsCssGrid] 现在可用，在 Microsoft Edge 版本 89 或更高版本中默认处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-242">[Turn on new CSS grid debugging features][DevtoolsCssGrid] is now available and turned on by default in Microsoft Edge version 89 or later.</span></span>  
*   <span data-ttu-id="ec0ad-243">[Emulation: Support dual screen mode][DevtoolsDeviceModeDualScreenAndFoldables] 现在可用，在 Microsoft Edge 版本 90 或更高版本中默认处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-243">[Emulation: Support dual screen mode][DevtoolsDeviceModeDualScreenAndFoldables] is now available and turned on by default in Microsoft Edge version 90 or later.</span></span>  

## <a name="providing-feedback-on-experimental-features"></a><span data-ttu-id="ec0ad-244">提供有关实验性功能的反馈</span><span class="sxs-lookup"><span data-stu-id="ec0ad-244">Providing feedback on experimental features</span></span>  

<span data-ttu-id="ec0ad-245">提供有关 Microsoft Edge DevTools 实验或与 DevTools 相关的任何其他内容的反馈。</span><span class="sxs-lookup"><span data-stu-id="ec0ad-245">To provide feedback on Microsoft Edge DevTools experiments, or anything else related to DevTools.</span></span>  

*   <span data-ttu-id="ec0ad-246">使用 DevTools 中的 **"发送** 反馈"图标发送反馈</span><span class="sxs-lookup"><span data-stu-id="ec0ad-246">Send your feedback using the **Send Feedback** icon in the DevTools</span></span>  
*   <span data-ttu-id="ec0ad-247">向 [@EdgeDevTools][TwitterEdgedevtools] 发送推文</span><span class="sxs-lookup"><span data-stu-id="ec0ad-247">Tweet at [@EdgeDevTools][TwitterEdgedevtools]</span></span>  
    
:::image type="complex" source="../media/bing-devtools-send-feedback.msft.png" alt-text="Microsoft Edge DevTools 中的“发送反馈”图标" lightbox="../media/bing-devtools-send-feedback.msft.png":::
   <span data-ttu-id="ec0ad-249">Microsoft Edge DevTools 中的“**发送反馈**”图标</span><span class="sxs-lookup"><span data-stu-id="ec0ad-249">The **Send Feedback** icon in Microsoft Edge DevTools</span></span>  
:::image-end:::  

<!--  
## Getting in touch with the Microsoft Edge DevTools team  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  
-->  

<!-- links -->  

[Devtools3dViewIndex]: ../3d-view/index.md "：：：no-loc (3D 视图) ：：： |Microsoft Docs"  
[DevtoolsCssGrid]: ../css/grid.md "检查 Microsoft Edge DevTools |Microsoft Docs"  
[DevtoolsCustomizeIndex]: ../customize/index.md "自定义 Microsoft Edge DevTools |Microsoft Docs"  
[DevToolsCustomizeIndexSettings]: ../customize/index.md#settings "设置 - 自定义 Microsoft Edge DevTools | Microsoft Docs"  
[DevtoolsCustomizeShortcutsEditKeyboardShortcutsForAnyActionDevtools]: ../customize/shortcuts.md#edit-keyboard-shortcuts-for-any-action-in-the-devtools "：：：no-loc (编辑 DevTools 工具中任何操作) ：：： |Microsoft Docs"  
[DevtoolsCustomizeShortcutsMatchKeyboardShortcutsDevtoolsMicrosoftVisualStudioCode]: ../customize/shortcuts.md#match-keyboard-shortcuts-in-the-devtools-to-microsoft-visual-studio-code "：：：no-loc (将 DevTools 中的键盘快捷方式与 Microsoft Visual Studio Code) ：：： |Microsoft Docs"  
[DevtoolsDeviceModeIndexSimulateMobileViewport]: ../device-mode/index.md#simulate-a-mobile-viewport "在 Microsoft Edge DevTools 服务中通过设备模式模拟移动设备|Microsoft Edge"  
[DevtoolsInspectStylesEditFonts]: ../inspect-styles/edit-fonts.md "在 DevTools | 中的"样式"窗格中编辑 CSS 字体样式和|Microsoft Docs"  
[DevtoolsIssuesIndex]: ../issues/index.md "查找并修复 Microsoft Edge DevTools 问题工具的问题 | Microsoft Docs"  
[DevtoolsOpenIndex]: ../open/index.md "打开 Microsoft Edge DevTools | Microsoft Docs"  
[DevtoolsShortcutsIndex]: ../shortcuts/index.md "Microsoft Edge DevTools 键盘快捷方式|Microsoft Docs"  

[MicrosoftEdgeMain]: https://www.microsoft.com/edge "Microsoft Edge"  

[DevtoolsDeviceModeDualScreenAndFoldables]: ../device-mode/dual-screen-and-foldables.md "模拟 Microsoft Edge DevTools |Microsoft Docs"

[TwitterEdgedevtools]: https://www.twitter.com/EdgeDevTools "Microsoft Edge DevTools |Twitter"  

[WebhintMain]: https://webhint.io "webhint"  
