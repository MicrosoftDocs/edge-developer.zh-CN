---
description: 现在欢迎使用"新增功能"工具、"样式"窗格中的可视化字体编辑器、CSS Flexbox 调试工具等。
title: 'Microsoft Edge 89 (DevTools 中的新增) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/03/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: cfaee927d2d914cf0d816505ea2cf6b36a225d64
ms.sourcegitcommit: 12c30ad4ab2664d17c9b7e9d59d7a3cda60ff65c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2021
ms.locfileid: "11313135"
---
# <span data-ttu-id="1ca3d-104">Microsoft Edge 89 (DevTools 中的新增) </span><span class="sxs-lookup"><span data-stu-id="1ca3d-104">What's New In DevTools (Microsoft Edge 89)</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/edge-whats-new-note.md)]  

## <span data-ttu-id="1ca3d-105">现在欢迎使用新增功能</span><span class="sxs-lookup"><span data-stu-id="1ca3d-105">What's New is now Welcome</span></span>  

<!--  Title: What's New is now Welcome  -->  
<!--  Subtitle: The What's New tool now has a new appearance and a new name:  Welcome -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

<span data-ttu-id="1ca3d-106">Microsoft **Edge** DevTools 中的新增功能工具现在具有新外观和新名称：  **欢迎**使用。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-106">The **What's New** tool in the Microsoft Edge DevTools now has a new appearance and a new name:  **Welcome**.</span></span>  <span data-ttu-id="1ca3d-107">欢迎 **工具** 仍显示最新的 DevTools 新闻和更新。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-107">The **Welcome** tool still displays the latest DevTools news and updates.</span></span>  <span data-ttu-id="1ca3d-108">它现在还包括指向 Microsoft Edge DevTools 文档的链接、提交反馈的方式等。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-108">It now also includes links to Microsoft Edge DevTools documentation, ways to submit feedback, and more.</span></span>  <span data-ttu-id="1ca3d-109">若要在 Microsoft Edge **每次更新** 后显示欢迎工具，请选中标题下每个更新后"打开"选项卡 **旁边的** 复选框。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-109">To display the **Welcome** tool after each update to Microsoft Edge, choose the checkbox next to **Open tab after each update** under the title.</span></span>  <span data-ttu-id="1ca3d-110">若要关闭**欢迎**工具，请选择选项卡标题右边的**X。**</span><span class="sxs-lookup"><span data-stu-id="1ca3d-110">To close the **Welcome** tool, choose the **X** on the right-side of the tab title.</span></span>  <span data-ttu-id="1ca3d-111">如果你更喜欢原始的新增**功能工具，** 请[导航到"][DevtoolsCustomizeIndexSettings]设置实验"并删除  >  \*\*\*\*"启用欢迎"**选项卡旁边的复选框**。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-111">If you prefer the original **What's New** tool, navigate to [Settings][DevtoolsCustomizeIndexSettings] > **Experiments** and remove the checkbox next to **Enable Welcome tab**.</span></span>  

:::image type="complex" source="../../media/2021/01/welcome-tool-whats-new-88.msft.png" alt-text="欢迎工具突出显示" lightbox="../../media/2021/01/welcome-tool-whats-new-88.msft.png":::
   <span data-ttu-id="1ca3d-113">欢迎 **工具** 突出显示</span><span class="sxs-lookup"><span data-stu-id="1ca3d-113">The **Welcome** tool is highlighted</span></span>  
:::image-end:::  

## <span data-ttu-id="1ca3d-114">"样式"窗格中的可视化字体编辑器</span><span class="sxs-lookup"><span data-stu-id="1ca3d-114">Visual Font Editor in the Styles pane</span></span>  

<!--  Title: Visual font editor in the Styles pane  -->  
<!--  Subtitle: Visual font editor in the Styles pane -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

<span data-ttu-id="1ca3d-115">在 CSS 中处理字体时，请使用新的可视 [字体编辑器][DevtoolsInspectStylesEditFonts]。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-115">When you work with fonts in CSS, use the new visual [Font Editor][DevtoolsInspectStylesEditFonts].</span></span>  <span data-ttu-id="1ca3d-116">你可以定义回退字体，并使用滑块定义字体粗细、大小、行高和间距。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-116">You may define fallback fonts, and use sliders to define font weight, size, line-height, and spacing.</span></span>  <span data-ttu-id="1ca3d-117">字体 **编辑器** 可帮助您完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-117">The **Font Editor** helps you complete the following actions.</span></span>  

*   <span data-ttu-id="1ca3d-118">在不同字体属性的单位之间切换</span><span class="sxs-lookup"><span data-stu-id="1ca3d-118">Switch between units for different font properties</span></span>  
*   <span data-ttu-id="1ca3d-119">在不同字体属性的关键字之间切换</span><span class="sxs-lookup"><span data-stu-id="1ca3d-119">Switch between keywords for different font properties</span></span>  
*   <span data-ttu-id="1ca3d-120">转换单位</span><span class="sxs-lookup"><span data-stu-id="1ca3d-120">Convert units</span></span>  
*   <span data-ttu-id="1ca3d-121">生成准确的 CSS 代码</span><span class="sxs-lookup"><span data-stu-id="1ca3d-121">Generate accurate CSS code</span></span>  
    
<span data-ttu-id="1ca3d-122">若要打开此实验，请[导航到"][DevtoolsCustomizeIndexSettings]设置实验"，并在"样式"窗格中选中"启用新  >  \*\*\*\* 字体编辑器工具"**旁边的复选框**。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-122">To turn on this experiment, navigate to [Settings][DevtoolsCustomizeIndexSettings] > **Experiments** and choose the checkbox next to **Enable new Font Editor tools within Styles pane**.</span></span>  <span data-ttu-id="1ca3d-123">有关详细信息，请导航到 DevTools 的"样式"窗格中的"编辑[CSS 字体样式和设置"。][DevtoolsInspectStylesEditFonts]</span><span class="sxs-lookup"><span data-stu-id="1ca3d-123">For more information, navigate to [Edit CSS font styles and settings in the Styles pane in DevTools][DevtoolsInspectStylesEditFonts].</span></span>  <span data-ttu-id="1ca3d-124">若要查看 Chromium 开放源代码项目中此功能的历史记录，请导航到"问题"[1093229][CR1093229]。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-124">To review the history of this feature in the Chromium open-source project, navigate to Issue [1093229][CR1093229].</span></span>  

:::image type="complex" source="../../media/2021/01/visual-font-editor.msft.png" alt-text="可视化字体编辑器在"样式"窗格中突出显示" lightbox="../../media/2021/01/visual-font-editor.msft.png":::
   <span data-ttu-id="1ca3d-126">可视化 **字体编辑器** 在" **样式"窗格中** 突出显示</span><span class="sxs-lookup"><span data-stu-id="1ca3d-126">The visual **Font editor** is highlighted in the **Styles** pane</span></span>  
:::image-end:::  

## <span data-ttu-id="1ca3d-127">CSS Flexbox 调试工具</span><span class="sxs-lookup"><span data-stu-id="1ca3d-127">CSS Flexbox debugging tools</span></span>  

<span data-ttu-id="1ca3d-128">Flexbox 调试功能正在积极开发中。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-128">Flexbox debugging features are in active development.</span></span>  <span data-ttu-id="1ca3d-129">若要打开以下两项功能的实验，请导航到"设置[][DevtoolsCustomizeIndexSettings]实验"，并选中"启用新的 CSS 弹性框调试功能  >  \*\*\*\*\*\*"旁边的复选框\*\*。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-129">To turn on the experiment for the following two features, navigate to [Settings][DevtoolsCustomizeIndexSettings] > **Experiments** and choose the checkbox next to **Enable new CSS Flexbox debugging features**.</span></span>  <span data-ttu-id="1ca3d-130">若要查看 Chromium 开放源代码项目中此功能的历史记录，请导航到"问题"[1136394][CR1136394] 和 [1139949][CR1139949]。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-130">To review the history of this feature in the Chromium open-source project, navigate to Issues [1136394][CR1136394] and [1139949][CR1139949].</span></span>  

### <span data-ttu-id="1ca3d-131">新的 Flexbox (弹性) 图标有助于标识和显示弹性容器</span><span class="sxs-lookup"><span data-stu-id="1ca3d-131">New Flexbox (flex) icon help identify and display flex containers</span></span>  

<!--  Title: Display Flexbox containers with Flexbox (flex) icon  -->  
<!--  Subtitle: New Flexbox (flex) icon in the Elements tool help you identify Flexbox containers in your code.  When toggled, the adorner displays and hides outlines of the flex container to help you debug the layout -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

<span data-ttu-id="1ca3d-132">在" **元素** "工具中，新的 Flexbox (flex) 图标可帮助您在代码中标识 Flexbox 容器。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-132">In the **Elements** tool, the new Flexbox (flex) icon helps you identify Flexbox containers in your code.</span></span>  <span data-ttu-id="1ca3d-133">Choose the Flexbox \ (flex\) icon to turn on or off the overlay effect that outlines a Flexbox container.</span><span class="sxs-lookup"><span data-stu-id="1ca3d-133">Choose the Flexbox \(flex\) icon to turn on or off the overlay effect that outlines a Flexbox container.</span></span>  <span data-ttu-id="1ca3d-134">You may customize the color of the overlay in the **Layout** pane， which is located next to **Styles** and **Computed.**</span><span class="sxs-lookup"><span data-stu-id="1ca3d-134">You may customize the color of the overlay in the **Layout** pane, which is located next to **Styles** and **Computed**.</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="1ca3d-135">若要打开和关闭覆盖效果（概述了 Flexbox 容器，请选择 Flexbox \ (`flex` \) 图标。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-135">To turn on and off the overlay effect that outlines the Flexbox container, choose the Flexbox \(`flex`\) icon.</span></span>  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="1ca3d-136">You may customize the color of the overlay in the **Layout** pane next to **Styles** and **Computed.**</span><span class="sxs-lookup"><span data-stu-id="1ca3d-136">You may customize the color of the overlay in the **Layout** pane next to **Styles** and **Computed**.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-flex-container.msft.png" alt-text="Flexbox (弹性) 图标和网页突出显示" lightbox="../../media/2021/01/elements-flex-container.msft.png":::
         <span data-ttu-id="1ca3d-138">**突出显示的 Flexbox** \ (`flex` \) 图标和网页</span><span class="sxs-lookup"><span data-stu-id="1ca3d-138">The **Flexbox** \(`flex`\) icon and webpage highlighted</span></span> :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-layout-flex-container.msft.png" alt-text=""布局"窗格中突出显示的弹性框覆盖" lightbox="../../media/2021/01/elements-layout-flex-container.msft.png":::
         <span data-ttu-id="1ca3d-140">"**布局"窗格中**突出显示的弹性框**覆盖**</span><span class="sxs-lookup"><span data-stu-id="1ca3d-140">The **Flexbox overlays** highlighted in the **Layout** pane</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

### <span data-ttu-id="1ca3d-141">当 Flexbox 布局使用 CSS 属性更改时显示对齐图标和网格线</span><span class="sxs-lookup"><span data-stu-id="1ca3d-141">Display alignment icons and gridlines when Flexbox layouts change using CSS properties</span></span>  

<!--  Title: Display alignment icons and gridlines for changes to Flexbox layouts from CSS properties  -->  
<!--  Subtitle:  CSS autocomplete in the Styles tool now displays icons next to Flexbox properties to help you review the effect a property has on your Flexbox layout -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

<span data-ttu-id="1ca3d-142">编辑 Flexbox 布局的 CSS 时，"样式"窗格中的\*\*\*\* CSS 自动完成现在会在相关的 Flexbox 属性旁边显示有用的图标。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-142">When you edit CSS for your Flexbox layout, CSS autocompletes in the **Styles** pane now displays helpful icons next to relevant Flexbox properties.</span></span>  <span data-ttu-id="1ca3d-143">若要尝试此新功能，请打开 **Elements** 工具并选择弹性容器。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-143">To try this new feature, open the **Elements** tool and select a flex container.</span></span>  <span data-ttu-id="1ca3d-144">然后，在"样式"窗格中添加或更改该 **容器上的** 属性。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-144">Then add or change a property on that container in the **Styles** pane.</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="1ca3d-145">自动完成菜单现在显示指示对齐属性的效果的图标，如 `align-content` `align-items` 和 。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-145">The autocomplete menu now displays icons that indicate the effect of alignment properties such as `align-content` and `align-items`.</span></span>  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="1ca3d-146">此外，DevTools 现在还显示一条指导线，帮助你更好地查看 `align-items` CSS 属性。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-146">Additionally, DevTools now displays a guiding line to help you better review the `align-items` CSS property.</span></span>  <span data-ttu-id="1ca3d-147">`gap`CSS 属性也受支持。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-147">The `gap` CSS property is supported as well.</span></span>  <span data-ttu-id="1ca3d-148">下图中 `gap` ，CSS 属性设置为并显示每个间隙 `gap: 12px;` 的填充模式。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-148">In the following figure, the `gap` CSS property is set to `gap: 12px;` and the hatching pattern for each gap is displayed.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-flex-container-align.msft.png" alt-text="突出显示的自动完成菜单用于以 align-" lightbox="../../media/2021/01/elements-flex-container-align.msft.png":::
         <span data-ttu-id="1ca3d-150">针对以 CSS 属性开始突出显示的"自动完成"菜单</span><span class="sxs-lookup"><span data-stu-id="1ca3d-150">Autocomplete menu highlighted for CSS properties that start with</span></span> `align-`  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-flex-container-align-items-center-gap-12px.msft.png" alt-text="CSS 属性和网页中的弹性框间隙突出显示" lightbox="../../media/2021/01/elements-flex-container-align-items-center-gap-12px.msft.png":::
         <span data-ttu-id="1ca3d-152">CSS 属性和网页中的 Flexbox `gap` 突出显示</span><span class="sxs-lookup"><span data-stu-id="1ca3d-152">Flexbox `gap` in CSS properties and webpage highlighted</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <span data-ttu-id="1ca3d-153">使用新的"更多工具"按钮快速添加工具</span><span class="sxs-lookup"><span data-stu-id="1ca3d-153">Add tools quickly with new More Tools button</span></span>  

<!--  Title: Add tools quickly with new More Tools button  -->  
<!--  Subtitle: A convenient way to open new tools in Microsoft Edge DevTools -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

<span data-ttu-id="1ca3d-154">现在，你具有在 Microsoft Edge DevTools 中打开更多工具的一种新方式。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-154">You now have a new way to open more tools in the Microsoft Edge DevTools.</span></span>  <span data-ttu-id="1ca3d-155">打开此实验后，"更多工具\*\*\*\*"图标 () 面板右侧显示 `+` 加号。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-155">After you turn on this experiment, the **More Tools** icon displays as a plus sign (`+`) to the right of the main panel.</span></span>  <span data-ttu-id="1ca3d-156">若要显示要添加到主面板的其他工具的列表，请选择"更多工具\*\*\*\*"\ (\) `+` 图标。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-156">To display a list of other tools to add to the main panel, choose the **More Tools** \(`+`\) icon.</span></span>  <span data-ttu-id="1ca3d-157">若要打开此实验，请[导航到"][DevtoolsCustomizeIndexSettings]设置实验"，然后选择"启用 + 按钮"选项卡菜单旁边的复选框以  >  \*\*\*\*\*\*打开更多工具\*\*。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-157">To turn on this experiment, navigate to [Settings][DevtoolsCustomizeIndexSettings] > **Experiments**, and then choose the checkbox next to **Enable + button tab menus to open more tools**.</span></span>  

:::image type="complex" source="../../media/2021/01/more-tools.msft.png" alt-text="开发人员工具中突出显示的更多工具" lightbox="../../media/2021/01/more-tools.msft.png":::
   <span data-ttu-id="1ca3d-159">**开发人员工具** 中突出显示的更多工具</span><span class="sxs-lookup"><span data-stu-id="1ca3d-159">**More Tools** highlighted in DevTools</span></span>  
:::image-end:::  

## <span data-ttu-id="1ca3d-160">辅助技术现在宣布 CSS 建议的位置和计数</span><span class="sxs-lookup"><span data-stu-id="1ca3d-160">Assistive technologies now announce position and count of CSS suggestions</span></span>  

<!--  Title: Assistive technologies now announce position and count of CSS suggestions  -->  
<!--  Subtitle: CSS suggestions are now easier to navigate using screen readers -->  

<span data-ttu-id="1ca3d-161">编辑 CSS 时，将获取功能下拉列表。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-161">When you edit CSS, you get a dropdown of features.</span></span>  <span data-ttu-id="1ca3d-162">此功能不适用于辅助技术的用户，因为它在 Microsoft Edge 版本 89 中公布。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-162">This feature was not available to users of assistive technologies, since it is announced in Microsoft Edge version 89.</span></span>  <span data-ttu-id="1ca3d-163">辅助技术的用户现在可以在"样式"窗格中导航 CSS**建议。**</span><span class="sxs-lookup"><span data-stu-id="1ca3d-163">A user of assistive technologies may now navigate CSS suggestions in the **Styles** pane.</span></span>  <span data-ttu-id="1ca3d-164">在 Microsoft Edge 版本 88 及更早版本中，当用户在"样式"窗格中编辑 CSS 时浏览建议列表时，会公布辅助 `Suggestion` 技术。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="1ca3d-164">In Microsoft Edge version 88 and earlier, assistive technology announced `Suggestion` as a user navigated through the list of suggestions when editing CSS in the **Styles** pane.</span></span>  <span data-ttu-id="1ca3d-165">在 Microsoft Edge 版本 89 中，辅助技术的用户现在会听到当前建议的位置和计数。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-165">In Microsoft Edge version 89, a user of assistive technology now hears the position and count of the current suggestion.</span></span>  <span data-ttu-id="1ca3d-166">每个建议在用户浏览建议列表时进行公布，如建议 3/5。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-166">Each suggestion is announced as the user navigates through the list of suggestions, such as Suggestion 3 of 5.</span></span>  <span data-ttu-id="1ca3d-167">若要了解有关在 DevTools 中编写 CSS 的更多信息，请导航到["更改 CSS"。][DevtoolsCssReferenceChangeCss]</span><span class="sxs-lookup"><span data-stu-id="1ca3d-167">To learn more about writing CSS in the DevTools, navigate to [Change CSS][DevtoolsCssReferenceChangeCss].</span></span>  <span data-ttu-id="1ca3d-168">若要查看 Chromium 开放源代码项目中此功能的历史记录，请导航到"问题"[1157329][CR1157329]。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-168">To review the history of this feature in the Chromium open-source project, navigate to Issue [1157329][CR1157329].</span></span>  

<!--To view a video that displays and reads aloud several suggestions with this experiment turned on, navigate to [Voiceover announcing devtools options](https://youtu.be/9TcUpleEwwA) on YouTube.  -->  

<span data-ttu-id="1ca3d-169">打开此实验后，以下视频链接将显示并朗读多个建议。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-169">The following video link displays and reads aloud several suggestions with this experiment turned on.</span></span>  

> [!VIDEO https://youtu.be/9TcUpleEwwA]  

## <span data-ttu-id="1ca3d-170">模拟 Surface Duo 和 Samsung 一起折叠</span><span class="sxs-lookup"><span data-stu-id="1ca3d-170">Emulate Surface Duo and Samsung Galaxy Fold</span></span>  

<!--  Title: Emulate new dual-screen and foldable devices  -->  
<!--  Subtitle: Test the appearance and feel of your website or app with Surface Duo and Samsung Galaxy Fold emulators -->  

<span data-ttu-id="1ca3d-171">在 Microsoft Edge 中的以下设备上测试网站或应用的外观。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-171">Test the appearance of your website or app on the following devices in Microsoft Edge.</span></span>  

*   [<span data-ttu-id="1ca3d-172">Surface Duo</span><span class="sxs-lookup"><span data-stu-id="1ca3d-172">Surface Duo</span></span>][MicrosoftSurfaceDevicesSurfaceDuo]  
*   [<span data-ttu-id="1ca3d-173">三星百合</span><span class="sxs-lookup"><span data-stu-id="1ca3d-173">Samsung Galaxy Fold</span></span>][SamsungUsMobileGalaxyFold]  
    
<span data-ttu-id="1ca3d-174">打开**实验性 Web 平台功能**以访问新的[CSS 媒体][DualScreenWebCssMediaSpanning]屏幕跨越功能和[getWindowSegments JavaScript API。][DualScreenWebJavascriptGetwindowsegments]</span><span class="sxs-lookup"><span data-stu-id="1ca3d-174">Turn on **Experimental Web Platform features** to access the new [CSS media screen-spanning feature][DualScreenWebCssMediaSpanning] and [getWindowSegments JavaScript API][DualScreenWebJavascriptGetwindowsegments].</span></span>  <span data-ttu-id="1ca3d-175">导航到 `edge://flags` 实验性 Web 平台功能旁边的**标志并切换。**</span><span class="sxs-lookup"><span data-stu-id="1ca3d-175">Navigate to `edge://flags` and toggle the flag next to **Experimental Web Platform features**.</span></span>  <span data-ttu-id="1ca3d-176">为了帮助增强适用于双屏和可折叠设备的网站或应用，在模拟设备时使用以下 [功能][DevtoolsDeviceModeIndex]。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-176">To help enhance your website or app for the dual-screen and foldable devices, use the following features when [emulating the device][DevtoolsDeviceModeIndex].</span></span>  

*   <span data-ttu-id="1ca3d-177">[跨越，][DevtoolsDeviceModeDualScreenFoldablesTestingFoldableDualScreenDevices]即你的网站 \ (或 app\) 跨两个屏幕显示。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-177">[Spanning][DevtoolsDeviceModeDualScreenFoldablesTestingFoldableDualScreenDevices], which is when your website \(or app\) appears across both screens.</span></span>  
*   <span data-ttu-id="1ca3d-178">[呈现接][DualScreenIntroductionHowToWorkWithSeam]层，这是两个屏幕之间的空间。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-178">[Rendering the seam][DualScreenIntroductionHowToWorkWithSeam], which is the space between the two screens.</span></span>  
    
<span data-ttu-id="1ca3d-179">若要查看 Chromium 开放源代码项目中此功能的历史记录，请导航到"问题"[1054281][CR1054281]。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-179">To review the history of this feature in the Chromium open-source project, navigate to Issue [1054281][CR1054281].</span></span>  

:::image type="complex" source="../../media/2021/01/emulate-surface-device-surface-duo.msft.png" alt-text="模拟双屏幕" lightbox="../../media/2021/01/emulate-surface-device-surface-duo.msft.png":::
   <span data-ttu-id="1ca3d-181">模拟双屏幕</span><span class="sxs-lookup"><span data-stu-id="1ca3d-181">Emulate dual-screen</span></span>  
:::image-end:::  

## <span data-ttu-id="1ca3d-182">Microsoft Edge 开发人员工具Visual Studio 1.1.2 版</span><span class="sxs-lookup"><span data-stu-id="1ca3d-182">Microsoft Edge Developer Tools for Visual Studio Code version 1.1.2</span></span>  

<span data-ttu-id="1ca3d-183">Microsoft [Edge 开发人员][VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools] 工具 Visual Studio Code extension version 1.1.2 for Microsoft Visual Studio Code has the following changes since the previous release.</span><span class="sxs-lookup"><span data-stu-id="1ca3d-183">The [Microsoft Edge Developer Tools for Visual Studio Code][VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools] extension version 1.1.2 for Microsoft Visual Studio Code has the following changes since the previous release.</span></span>  <span data-ttu-id="1ca3d-184">Microsoft Visual Studio 代码会自动更新扩展。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-184">Microsoft Visual Studio Code updates extensions automatically.</span></span>  <span data-ttu-id="1ca3d-185">若要手动更新到版本 1.1.2，请导航到 [手动更新扩展][VisualstudioCodeDocsEditorExtensionGalleryUpdateExtensionManually]。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-185">To manually update to version 1.1.2, navigate to [Update an extension manually][VisualstudioCodeDocsEditorExtensionGalleryUpdateExtensionManually].</span></span>  

*   <span data-ttu-id="1ca3d-186">向目标 **列表 \ (** #248 [\) ][GithubMicrosoftVscodeEdgeDevtoolsPull248]上的每个项目添加了"关闭实例"按钮</span><span class="sxs-lookup"><span data-stu-id="1ca3d-186">Added a **Close instance** button to each item on the target list \([#248][GithubMicrosoftVscodeEdgeDevtoolsPull248]\)</span></span>  
*   <span data-ttu-id="1ca3d-187">从[][DevtoolsMain]84.0.522.63 到[85.0.564.40][DevtoolsWhatsNew85] \ (#235 [\) ][GithubMicrosoftVscodeEdgeDevtoolsPull235]</span><span class="sxs-lookup"><span data-stu-id="1ca3d-187">Bumped [Microsoft Edge DevTools][DevtoolsMain] version from 84.0.522.63 to [85.0.564.40][DevtoolsWhatsNew85] \([#235][GithubMicrosoftVscodeEdgeDevtoolsPull235]\)</span></span>  
*   <span data-ttu-id="1ca3d-188">将[Microsoft Edge 调试][VisualstudioMarketplaceMsjsdiagDebuggerMicrosoftEdge]器作为依赖项 \ (#233 \) [][GithubMicrosoftVscodeEdgeDevtoolsPull233]</span><span class="sxs-lookup"><span data-stu-id="1ca3d-188">Included [Debugger for Microsoft Edge][VisualstudioMarketplaceMsjsdiagDebuggerMicrosoftEdge] as a dependency  \([#233][GithubMicrosoftVscodeEdgeDevtoolsPull233]\)</span></span>  
*   <span data-ttu-id="1ca3d-189">实现的用于更改扩展主题 \ (#229 [\) ][GithubMicrosoftVscodeEdgeDevtoolsPull229]</span><span class="sxs-lookup"><span data-stu-id="1ca3d-189">Implemented settings option to change extension themes \([#229][GithubMicrosoftVscodeEdgeDevtoolsPull229]\)</span></span>  
    
<span data-ttu-id="1ca3d-190">你可以提交问题并参与 [vscode-edge-devtools GitHub 存储库上的扩展][GithubMicrosoftVscodeEdgeDevtools]。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-190">You may file issues and contribute to the extension on the [vscode-edge-devtools GitHub repo][GithubMicrosoftVscodeEdgeDevtools].</span></span>  

## <span data-ttu-id="1ca3d-191">来自 Chromium 项目的公告</span><span class="sxs-lookup"><span data-stu-id="1ca3d-191">Announcements from the Chromium project</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/chromium-whats-new-note.md)]  

### <span data-ttu-id="1ca3d-192">捕获视图之外的节点屏幕截图</span><span class="sxs-lookup"><span data-stu-id="1ca3d-192">Capture node screenshot beyond viewport</span></span>  

<span data-ttu-id="1ca3d-193">在 Microsoft Edge 版本 89 中，节点屏幕截图更加准确，即使节点中的内容在视口中不可见，也捕获整个节点。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-193">In Microsoft Edge version 89, node screenshots are more accurate, capturing the full node even if content from the node is not visible in the viewport.</span></span>  <span data-ttu-id="1ca3d-194">在元素 **工具** 中，将鼠标悬停在某个元素上，打开上下文菜单 \ (右键单击\) ，然后选择"捕获 **"节点屏幕截图**。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-194">In the **Elements** tool, hover  on an element, open the contextual menu \(right-click\), and choose **Capture node screenshot**.</span></span>  <span data-ttu-id="1ca3d-195">若要查看 Chromium 开放源代码项目中此功能的历史记录，请导航到"问题"[1003629][CR1003629]。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-195">To review the history of this feature in the Chromium open-source project, navigate to Issue [1003629][CR1003629].</span></span>  

:::image type="complex" source="../../media/2021/01/capture-node-screenshot.msft.png" alt-text="在元素工具的上下文菜单上突出显示的捕获节点屏幕截图" lightbox="../../media/2021/01/capture-node-screenshot.msft.png":::
   <span data-ttu-id="1ca3d-197">**在元素工具** 的上下文菜单上突出显示 **的捕获节点** 屏幕截图</span><span class="sxs-lookup"><span data-stu-id="1ca3d-197">**Capture node screenshot** highlighted on the context menu in the **Elements** tool</span></span>  
:::image-end:::  

### <span data-ttu-id="1ca3d-198">元素工具更新</span><span class="sxs-lookup"><span data-stu-id="1ca3d-198">Elements tool updates</span></span>  

#### <span data-ttu-id="1ca3d-199">支持强制使用 ：target CSS 状态</span><span class="sxs-lookup"><span data-stu-id="1ca3d-199">Support forcing the :target CSS state</span></span>  

<span data-ttu-id="1ca3d-200">你现在可以使用 DevTools 强制使用 [：target][MdnDocsWebCssTarget] CSS 伪类。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-200">You may now use DevTools to force the [:target][MdnDocsWebCssTarget] CSS pseudo-class.</span></span>  <span data-ttu-id="1ca3d-201">当唯一元素 \ (\) 具有与 URL 片段匹配的元素时，将触发伪 `:target` `id` 类。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-201">The `:target` pseudo-class is triggered when a unique element \(the target element\) has an `id` that matches a fragment of the URL.</span></span>  <span data-ttu-id="1ca3d-202">例如 `http://www.example.com/index.html#section1` ，URL 将触发 HTML 元素 `:target` 上的伪类 `id="section1"` 。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-202">For example, the `http://www.example.com/index.html#section1` URL triggers the `:target` pseudo-class on an HTML element with `id="section1"`.</span></span>  <span data-ttu-id="1ca3d-203">若要尝试突出显示第 1 节的演示，请导航到 [CSS ：target 演示][GithubMicrosoftedgeDevtoolssamplesWhatsNew89TargetCssDemoHtmlSection1]。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-203">To try a demo with section 1 highlighted, navigate to [CSS :target demo][GithubMicrosoftedgeDevtoolssamplesWhatsNew89TargetCssDemoHtmlSection1].</span></span>  <span data-ttu-id="1ca3d-204">若要查看 Chromium 开放源代码项目中此功能的历史记录，请导航到"问题"[1156628][CR1156628]。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-204">To review the history of this feature in the Chromium open-source project, navigate to Issue [1156628][CR1156628].</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-styles-none-forced.msft.png" alt-text="突出显示的网页没有强制 CSS" lightbox="../../media/2021/01/elements-styles-none-forced.msft.png":::
         <span data-ttu-id="1ca3d-206">未强制 CSS 突出显示的网页</span><span class="sxs-lookup"><span data-stu-id="1ca3d-206">Webpage highlighted with no forced CSS</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-styles-target-forced.msft.png" alt-text="：target CSS 强制和网页突出显示" lightbox="../../media/2021/01/elements-styles-target-forced.msft.png":::
         `:target` <span data-ttu-id="1ca3d-208">CSS 强制和网页突出显示</span><span class="sxs-lookup"><span data-stu-id="1ca3d-208">CSS forced and webpage highlighted</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::

#### <span data-ttu-id="1ca3d-209">使用重复元素复制元素</span><span class="sxs-lookup"><span data-stu-id="1ca3d-209">Use Duplicate elements to copy elements</span></span>  

<span data-ttu-id="1ca3d-210">使用新的 **Duplicate 元素** 快捷方式克隆元素。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-210">Use the new **Duplicate element** shortcut to clone an element.</span></span>  <span data-ttu-id="1ca3d-211">在元素 **工具** 中，将鼠标悬停在元素上，打开上下文菜单 \ (右键单击\) ，选择 **Duplicate 元素**。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-211">In the **Elements** tool, hover on an element, open the contextual menu \(right-click\), choose **Duplicate element**.</span></span>  <span data-ttu-id="1ca3d-212">在所选元素下创建一个新元素。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-212">A new element is created under the selected element.</span></span>  <span data-ttu-id="1ca3d-213">若要使用键盘快捷方式复制元素，请选择 `Shift` + `Alt` + `Down Arrow` \ (Windows/Linux\) 或 `Shift` + `Option` + `Down Arrow` \ (macOS\) 。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-213">To duplicate the element with a keyboard shortcut, select `Shift`+`Alt`+`Down Arrow` \(Windows/Linux\) or `Shift`+`Option`+`Down Arrow` \(macOS\).</span></span>  <span data-ttu-id="1ca3d-214">若要查看 Chromium 开放源代码项目中此功能的历史记录，请导航到"问题"[1150797][CR1150797]。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-214">To review the history of this feature in the Chromium open-source project, navigate to Issue [1150797][CR1150797].</span></span>  

:::image type="complex" source="../../media/2021/01/elements-duplicate-element.msft.png" alt-text="Duplicate 元素在"元素"工具中某个元素的上下文菜单中突出显示" lightbox="../../media/2021/01/elements-duplicate-element.msft.png":::
   <span data-ttu-id="1ca3d-216">Duplicate**元素**在"元素"工具中某个元素的**上下文菜单中突出显示**</span><span class="sxs-lookup"><span data-stu-id="1ca3d-216">The **Duplicate element** is highlighted in the context menu on an element in the **Elements** tool</span></span>  
:::image-end:::  

#### <span data-ttu-id="1ca3d-217">自定义 CSS 属性的颜色选取器</span><span class="sxs-lookup"><span data-stu-id="1ca3d-217">Color pickers for custom CSS properties</span></span>  

<span data-ttu-id="1ca3d-218">" **样式"** 窗格现在显示自定义 CSS 属性的颜色选取器。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-218">The **Styles** pane now displays color pickers for custom CSS properties.</span></span>  <span data-ttu-id="1ca3d-219">若要循环访问颜色值的 RGBA、HSLA 和 Hex 格式，请按住并选择 `Shift` 颜色选取器。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-219">To cycle through the RGBA, HSLA, and Hex formats of the color value, hold `Shift` and choose the color picker.</span></span>  <span data-ttu-id="1ca3d-220">若要查看 Chromium 开放源代码项目中此功能的历史记录，请导航到"问题"[1147016][CR1147016]。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-220">To review the history of this feature in the Chromium open-source project, navigate to Issue [1147016][CR1147016].</span></span>  

:::image type="complex" source="../../media/2021/01/elements-styles-change-color-format.msft.png" alt-text="自定义 CSS 属性的颜色选取器" lightbox="../../media/2021/01/elements-styles-change-color-format.msft.png":::
   <span data-ttu-id="1ca3d-222">自定义 CSS 属性的颜色选取器</span><span class="sxs-lookup"><span data-stu-id="1ca3d-222">Color pickers for custom CSS properties</span></span>  
:::image-end:::  

#### <span data-ttu-id="1ca3d-223">复制 CSS 类和属性</span><span class="sxs-lookup"><span data-stu-id="1ca3d-223">Copy CSS classes and properties</span></span>  

<span data-ttu-id="1ca3d-224">现在，可以使用上下文菜单中的一些新选项更快地复制 CSS 属性。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-224">You may now copy CSS properties quicker with a few new options in the contextual menu.</span></span>  <span data-ttu-id="1ca3d-225">在" **元素** "工具中，选择一个元素。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-225">In the **Elements** tool, choose an element.</span></span>  <span data-ttu-id="1ca3d-226">若要复制该值，请在 **"** 样式"窗格中将鼠标悬停在 CSS 类或 CSS 属性上，打开上下文菜单 \ (右键单击\) ，然后选择复制选项。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-226">To copy the value, in the **Styles** pane, hover on a CSS class or a CSS property, open a contextual menu \(right-click\), and choose the copy option.</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="1ca3d-227">复制 CSS 类的选项。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-227">Copy options for a CSS class.</span></span>  
      
      | <span data-ttu-id="1ca3d-228">选项</span><span class="sxs-lookup"><span data-stu-id="1ca3d-228">Option</span></span> | <span data-ttu-id="1ca3d-229">详细信息</span><span class="sxs-lookup"><span data-stu-id="1ca3d-229">Details</span></span> |  
      |:--- |:--- |  
      | **<span data-ttu-id="1ca3d-230">复制选择器</span><span class="sxs-lookup"><span data-stu-id="1ca3d-230">Copy selector</span></span>** | <span data-ttu-id="1ca3d-231">复制当前选择器名称。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-231">Copy the current selector name.</span></span> |  
      | **<span data-ttu-id="1ca3d-232">复制规则</span><span class="sxs-lookup"><span data-stu-id="1ca3d-232">Copy rule</span></span>** | <span data-ttu-id="1ca3d-233">复制当前选择器的规则。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-233">Copy the rule of the current selector.</span></span> |  
      | **<span data-ttu-id="1ca3d-234">复制所有声明</span><span class="sxs-lookup"><span data-stu-id="1ca3d-234">Copy all declarations</span></span>** | <span data-ttu-id="1ca3d-235">复制当前规则下的所有声明，包括无效和前缀属性。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-235">Copy all declarations under the current rule, including non-valid and prefixed properties.</span></span> |  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="1ca3d-236">复制 CSS 属性的选项。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-236">Copy options for a CSS property.</span></span>  
      
      | <span data-ttu-id="1ca3d-237">选项</span><span class="sxs-lookup"><span data-stu-id="1ca3d-237">Option</span></span> | <span data-ttu-id="1ca3d-238">详细信息</span><span class="sxs-lookup"><span data-stu-id="1ca3d-238">Details</span></span> |      
      |:--- |:--- |  
      | **<span data-ttu-id="1ca3d-239">复制声明</span><span class="sxs-lookup"><span data-stu-id="1ca3d-239">Copy declaration</span></span>** | <span data-ttu-id="1ca3d-240">复制当前行的声明。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-240">Copy the declaration of the current line.</span></span> |  
      | **<span data-ttu-id="1ca3d-241">Copy 属性</span><span class="sxs-lookup"><span data-stu-id="1ca3d-241">Copy property</span></span>** | <span data-ttu-id="1ca3d-242">复制当前行的属性。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-242">Copy the property of the current line.</span></span> |  
      | **<span data-ttu-id="1ca3d-243">复制值</span><span class="sxs-lookup"><span data-stu-id="1ca3d-243">Copy value</span></span>** | <span data-ttu-id="1ca3d-244">复制当前行的值。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-244">Copy the value of the current line.</span></span> |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/copy-css-class.msft.png" alt-text="在上下文菜单中复制 CSS 类的选项" lightbox="../../media/2021/01/copy-css-class.msft.png":::
         <span data-ttu-id="1ca3d-246">在上下文菜单中复制 CSS 类的选项</span><span class="sxs-lookup"><span data-stu-id="1ca3d-246">Copy options for a CSS class in the contextual menu</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/copy-css-property-cropped.msft.png" alt-text="在上下文菜单中复制 CSS 属性的选项" lightbox="../../media/2021/01/copy-css-property.msft.png":::
         <span data-ttu-id="1ca3d-248">在上下文菜单中复制 CSS 属性的选项</span><span class="sxs-lookup"><span data-stu-id="1ca3d-248">Copy options for a CSS property in the contextual menu</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="1ca3d-249">若要查看 Chromium 开放源代码项目中此功能的历史记录，请导航到"问题"[1152391][CR1152391]。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-249">To review the history of this feature in the Chromium open-source project, navigate to Issue [1152391][CR1152391].</span></span>  

### <span data-ttu-id="1ca3d-250">Cookie 更新</span><span class="sxs-lookup"><span data-stu-id="1ca3d-250">Cookies updates</span></span>  

#### <span data-ttu-id="1ca3d-251">显示 URL 解码 Cookie 的新选项</span><span class="sxs-lookup"><span data-stu-id="1ca3d-251">New option to display URL-decoded cookies</span></span>  

<span data-ttu-id="1ca3d-252">现在，你可以选择在 Cookie 窗格中显示 URL 解码的 **Cookie** 值。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-252">You may now opt to display the URL-decoded cookies value in the **Cookies** pane.</span></span>  <span data-ttu-id="1ca3d-253">若要显示解码的 Cookie，请导航**到应用程序**Cookie 窗格，选择列表上的任何 Cookie，然后选择"显示  >  \*\*\*\* 已解码**的 URL"旁边的复选框**。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-253">To display the decoded cookie, navigate to **Application** > **Cookies** pane, choose any cookie on the list, and choose the checkbox next to **Show URL decoded**.</span></span>  <span data-ttu-id="1ca3d-254">若要查看 Chromium 开放源代码项目中此功能的历史记录，请导航到"问题"[997625][CR997625]。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-254">To review the history of this feature in the Chromium open-source project, navigate to Issue [997625][CR997625].</span></span>  

:::image type="complex" source="../../media/2021/01/application-cookies-show-url-decoded.msft.png" alt-text="显示 URL 解码 Cookie 的选项" lightbox="../../media/2021/01/application-cookies-show-url-decoded.msft.png":::
   <span data-ttu-id="1ca3d-256">用于显示 URL 解码 Cookie 的选项</span><span class="sxs-lookup"><span data-stu-id="1ca3d-256">Option to display URL decoded cookies</span></span>  
:::image-end:::  

#### <span data-ttu-id="1ca3d-257">筛选和清除可见的 Cookie</span><span class="sxs-lookup"><span data-stu-id="1ca3d-257">Filter and clear visible cookies</span></span>  

<span data-ttu-id="1ca3d-258">在 Microsoft Edge 版本 88\*\*\*\* 或更早版本中，应用程序工具仅提供一种使用"清除所有 Cookie"按钮清除所有**Cookie**的方法。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-258">In Microsoft Edge version 88 or earlier, the **Application** tool only provided a way to clear all cookies with the **Clear all cookies** button.</span></span>  <span data-ttu-id="1ca3d-259">在 Microsoft Edge 版本 89 中，你现在可以选择"清除筛选的 **Cookie"，** 以仅删除筛选的 Cookie。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-259">In Microsoft Edge version 89, you may now choose **Clear filtered cookies** to delete only the filtered cookies.</span></span>  <span data-ttu-id="1ca3d-260">若要筛选 Cookie，请导航到 **"应用程序**  >  **Cookie"，** 并在 **"筛选器**"文本框中键入。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-260">To filter cookies, navigate to **Application** > **Cookies**, and type in the **Filter** textbox.</span></span>  <span data-ttu-id="1ca3d-261">若要删除显示的 Cookie，请选择" **清除筛选的 Cookie"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-261">To delete the displayed cookies, choose the **Clear filtered cookies** button.</span></span>  <span data-ttu-id="1ca3d-262">若要显示所有其他 Cookie，请清除筛选器文本。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-262">To display all other cookies, clear the filter text.</span></span>  <span data-ttu-id="1ca3d-263">若要查看 Chromium 开放源代码项目中此功能的历史记录，请导航到"问题"[978059][CR978059]。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-263">To review the history of this feature in the Chromium open-source project, navigate to Issue [978059][CR978059].</span></span>  

:::image type="complex" source="../../media/2021/01/application-cookies-clear-filtered-cookies.msft.png" alt-text="仅清除可见的 Cookie" lightbox="../../media/2021/01/application-cookies-clear-filtered-cookies.msft.png":::
   <span data-ttu-id="1ca3d-265">仅清除可见的 Cookie</span><span class="sxs-lookup"><span data-stu-id="1ca3d-265">Clear only visible cookies</span></span>  
:::image-end:::  

#### <span data-ttu-id="1ca3d-266">在存储窗格中清除第三方 Cookie 的新选项</span><span class="sxs-lookup"><span data-stu-id="1ca3d-266">New option to clear third-party cookies in the Storage pane</span></span>  

<span data-ttu-id="1ca3d-267">默认情况下，DevTools 现在仅清除第一方 Cookie。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-267">DevTools now clear only first-party cookies by default.</span></span>  <span data-ttu-id="1ca3d-268">若要仅清除网站数据和第一方 Cookie，请导航到 **"应用程序**存储"，  >  \*\*\*\* 然后选择"**清除网站数据"。**</span><span class="sxs-lookup"><span data-stu-id="1ca3d-268">To clear website data and first-party cookies only, navigate to **Application** > **Storage**, and then choose **Clear site data**.</span></span>  

<span data-ttu-id="1ca3d-269">若要清除网站数据和所有 Cookie，请导航到**应用程序**  >  **存储**。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-269">To clear website data and all cookies, navigate to **Application** > **Storage**.</span></span>  <span data-ttu-id="1ca3d-270">选中包含第三方**Cookie 旁边的**复选框，然后选择"**清除网站数据"。**</span><span class="sxs-lookup"><span data-stu-id="1ca3d-270">Choose the checkbox next to **including third-party cookies**, and then choose **Clear site data**.</span></span>  

<span data-ttu-id="1ca3d-271">若要查看 Chromium 开放源代码项目中此功能的历史记录，请导航到"问题"[1012337][CR1012337]。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-271">To review the history of this feature in the Chromium open-source project, navigate to Issue [1012337][CR1012337].</span></span>  

:::image type="complex" source="../../media/2021/01/application-storage-clear-site-data-including-third-party-cookies.msft.png" alt-text="清除第三方 Cookie 的选项" lightbox="../../media/2021/01/application-storage-clear-site-data-including-third-party-cookies.msft.png":::
   <span data-ttu-id="1ca3d-273">清除第三方 Cookie 的选项</span><span class="sxs-lookup"><span data-stu-id="1ca3d-273">Option to clear third-party cookies</span></span>  
:::image-end:::  

### <span data-ttu-id="1ca3d-274">网络工具更新</span><span class="sxs-lookup"><span data-stu-id="1ca3d-274">Network tool updates</span></span>  

#### <span data-ttu-id="1ca3d-275">持久记录网络日志设置</span><span class="sxs-lookup"><span data-stu-id="1ca3d-275">Persist Record network log setting</span></span>  

<span data-ttu-id="1ca3d-276">在 Microsoft Edge 版本 88 或更早版本中，DevTools 在网页刷新时重置记录网络日志设置。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="1ca3d-276">In Microsoft Edge version 88 or earlier, DevTools reset the **Record network log** setting when a webpage refreshes.</span></span>  <span data-ttu-id="1ca3d-277">在 Microsoft Edge 版本 89 中，DevTools 现在保留 **记录网络日志** 设置。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-277">In Microsoft Edge version 89, DevTools now persist the **Record network log** setting.</span></span>  <span data-ttu-id="1ca3d-278">若要查看 Chromium 开放源代码项目中此功能的历史记录，请导航到"问题"[1122580][CR1122580]。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-278">To review the history of this feature in the Chromium open-source project, navigate to Issue [1122580][CR1122580].</span></span>  

:::image type="complex" source="../../media/2021/01/network-log.msft.png" alt-text="记录网络日志" lightbox="../../media/2021/01/network-log.msft.png":::
   <span data-ttu-id="1ca3d-280">记录网络日志</span><span class="sxs-lookup"><span data-stu-id="1ca3d-280">Record network log</span></span>  
:::image-end:::  

#### <span data-ttu-id="1ca3d-281">联机选项现在无限制选项</span><span class="sxs-lookup"><span data-stu-id="1ca3d-281">Online option is now No throttling option</span></span>  

<span data-ttu-id="1ca3d-282">网络仿真选项**Online**现已重命名为"无**限制"。**</span><span class="sxs-lookup"><span data-stu-id="1ca3d-282">The network emulation option **Online** is now renamed to **No Throttling**.</span></span>  <span data-ttu-id="1ca3d-283">若要查看 Chromium 开放源代码项目中此功能的历史记录，请导航到"问题"[1028078][CR1028078]。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-283">To review the history of this feature in the Chromium open-source project, navigate to Issue [1028078][CR1028078].</span></span>  

:::image type="complex" source="../../media/2021/01/network-no-throttling.msft.png" alt-text="无限制选项" lightbox="../../media/2021/01/network-no-throttling.msft.png":::
   <span data-ttu-id="1ca3d-285">**无限制** 选项</span><span class="sxs-lookup"><span data-stu-id="1ca3d-285">**No throttling** option</span></span>  
:::image-end:::  

### <span data-ttu-id="1ca3d-286">控制台工具、源工具和样式窗格中的新副本选项</span><span class="sxs-lookup"><span data-stu-id="1ca3d-286">New copy options in the Console tool, Sources tool, and Styles pane</span></span>

#### <span data-ttu-id="1ca3d-287">复制控制台和源工具中的对象</span><span class="sxs-lookup"><span data-stu-id="1ca3d-287">Copy object in the Console and Sources tool</span></span>  

<span data-ttu-id="1ca3d-288">现在可以在控制台和源工具 **中** 复制 **对象** 值。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-288">You may now copy object values in the **Console** and **Sources** tools.</span></span>  <span data-ttu-id="1ca3d-289">使用大型对象时，复制对象值的能力非常有用。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-289">The ability to copy object values is useful when working with large objects.</span></span>  <span data-ttu-id="1ca3d-290">若要查看 Chromium 开源项目中此功能的历史记录，请导航到"问题"[1148353][CR1148353] 和 [1149859][CR1149859]。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-290">To review the history of this feature in the Chromium open-source project, navigate to Issues [1148353][CR1148353] and [1149859][CR1149859].</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="1ca3d-291">在 **控制台工具** 中，将鼠标悬停在对象上，打开上下文菜单 \ (右键单击\) ，然后选择复制 **对象**。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-291">In the **Console** tool, hover on an object, open the contextual menu \(right-click\), and then choose **Copy object**.</span></span>  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="1ca3d-292">在源\*\*\*\* 工具的断点上，将鼠标悬停在对象上，在对象\*\*\*\* 弹出窗口中突出显示对象，打开上下文菜单 \ (右键单击\) ，然后选择复制**对象**。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-292">In the **Sources** tool, on a breakpoint, hover on an object, in the **Object** popup window, highlight an object, open the contextual menu \(right-click\), and then choose **Copy object**.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/console-copy-object.msft.png" alt-text="在控制台中复制对象" lightbox="../../media/2021/01/console-copy-object.msft.png":::
         <span data-ttu-id="1ca3d-294">在控制台中复制 **对象**</span><span class="sxs-lookup"><span data-stu-id="1ca3d-294">Copy object in the **Console**</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/sources-breakpoint-object-copy-object.msft.png" alt-text="在源中复制对象" lightbox="../../media/2021/01/sources-breakpoint-object-copy-object.msft.png":::
         <span data-ttu-id="1ca3d-296">在源中复制 **对象**</span><span class="sxs-lookup"><span data-stu-id="1ca3d-296">Copy object in **Sources**</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

#### <span data-ttu-id="1ca3d-297">在"源"工具和"样式"窗格中复制文件名</span><span class="sxs-lookup"><span data-stu-id="1ca3d-297">Copy file name in the Sources tool and Styles pane</span></span>  

<span data-ttu-id="1ca3d-298">现在，可以使用上下文菜单复制文件名。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-298">You may now copy a file name using the contextual menu.</span></span>  <span data-ttu-id="1ca3d-299">若要查看 Chromium 开放源代码项目中此功能的历史记录，请导航到"问题"[1155120][CR1155120]。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-299">To review the history of this feature in the Chromium open-source project, navigate to Issues [1155120][CR1155120].</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="1ca3d-300">在源**工具**中，将鼠标悬停在文件名上，打开上下文菜单 \ (右键单击\) ，然后选择"复制**文件名"。**</span><span class="sxs-lookup"><span data-stu-id="1ca3d-300">In the **Sources** tool, hover on a file name, open the contextual menu \(right-click\), and then choose **Copy file name**.</span></span>  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="1ca3d-301">在"**样式**>中，将鼠标\*\*\*\* 悬停在文件名上，打开上下文菜单 \ (右键单击\) ，然后选择"复制**文件名"。**</span><span class="sxs-lookup"><span data-stu-id="1ca3d-301">In the **Elements** tool > **Styles** pane, hover on a file name, open the contextual menu \(right-click\), and then choose **Copy file name**.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/sources-copy-file-name.msft.png" alt-text="复制源中的文件名" lightbox="../../media/2021/01/sources-copy-file-name.msft.png":::
         <span data-ttu-id="1ca3d-303">复制源中的 **文件名**</span><span class="sxs-lookup"><span data-stu-id="1ca3d-303">Copy file name in **Sources**</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-styles-copy-file-name.msft.png" alt-text="在"样式"窗格中复制文件名" lightbox="../../media/2021/01/elements-styles-copy-file-name.msft.png":::
         <span data-ttu-id="1ca3d-305">在"样式"窗格中 **复制** 文件名</span><span class="sxs-lookup"><span data-stu-id="1ca3d-305">Copy file name in **Styles** pane</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

### <span data-ttu-id="1ca3d-306">帧详细信息更新</span><span class="sxs-lookup"><span data-stu-id="1ca3d-306">Updates to Frame details</span></span>  

#### <span data-ttu-id="1ca3d-307">框架详细信息中的服务工作者信息</span><span class="sxs-lookup"><span data-stu-id="1ca3d-307">Service Workers information in Frame details</span></span>  

<span data-ttu-id="1ca3d-308">DevTools 现在在父框架下列出一个专用服务工作者。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-308">DevTools now lists a dedicated service worker under the parent frame.</span></span>  <span data-ttu-id="1ca3d-309">下图显示了服务工作者的详细信息。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-309">In the following figure, service worker details are displayed.</span></span>  <span data-ttu-id="1ca3d-310">若要显示服务工作者的详细信息，请导航到 **"应用程序**  >  **框架**  >  `top`  >  **服务**工作者"，然后选择一个服务工作者。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-310">To display the service worker details, navigate to **Application** > **Frames** > `top` > **Service Workers** and then choose a service worker.</span></span>  <span data-ttu-id="1ca3d-311">若要查看 Chromium 开放源代码项目中此功能的历史记录，请导航到"问题"[1122507][CR1122507]。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-311">To review the history of this feature in the Chromium open-source project, navigate to Issue [1122507][CR1122507].</span></span>  

:::image type="complex" source="../../media/2021/01/application-frames-service-workers-details.msft.png" alt-text="框架详细信息中的服务工作者信息" lightbox="../../media/2021/01/application-frames-service-workers-details.msft.png":::
   <span data-ttu-id="1ca3d-313">**框架** 详细信息中的 **服务工作者** 信息</span><span class="sxs-lookup"><span data-stu-id="1ca3d-313">**Service Workers** information in the **Frames** details</span></span>  
:::image-end:::  

#### <span data-ttu-id="1ca3d-314">在帧详细信息中测量内存信息</span><span class="sxs-lookup"><span data-stu-id="1ca3d-314">Measure Memory information in Frame details</span></span>  

<span data-ttu-id="1ca3d-315">API `performance.measureMemory()` 状态现在显示在 **API** 可用性部分下。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-315">The `performance.measureMemory()` API status is now displayed under the **API availability** section.</span></span>  <span data-ttu-id="1ca3d-316">新 `performance.measureMemory()` API 估计整个网页的内存使用率。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-316">The new `performance.measureMemory()` API estimates the memory usage of the entire webpage.</span></span>  <span data-ttu-id="1ca3d-317">若要查看 Chromium 开放源代码项目中此功能的历史记录，请导航到"问题"[1139899][CR1139899]。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-317">To review the history of this feature in the Chromium open-source project, navigate to Issue [1139899][CR1139899].</span></span>  

:::image type="complex" source="../../media/2021/01/application-frames-measure-memory.msft.png" alt-text="测量内存" lightbox="../../media/2021/01/application-frames-measure-memory.msft.png":::
   <span data-ttu-id="1ca3d-319">测量内存</span><span class="sxs-lookup"><span data-stu-id="1ca3d-319">Measure Memory</span></span>  
:::image-end:::  

### <span data-ttu-id="1ca3d-320">性能工具中丢弃的帧</span><span class="sxs-lookup"><span data-stu-id="1ca3d-320">Dropped frames in the Performance tool</span></span>  

<span data-ttu-id="1ca3d-321">在性能 [工具中分析负载性能时，"][DevtoolsEvaluatePerformanceReferenceRecordLoadPerformance]框架 **"部分现在** 将丢弃的帧标记为红色。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-321">When you [analyze load performance in the Performance tool][DevtoolsEvaluatePerformanceReferenceRecordLoadPerformance], the **Frames** section now marks dropped frames as red.</span></span>  <span data-ttu-id="1ca3d-322">若要显示帧速率，请将鼠标悬停在丢弃的帧上。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-322">To display the frame rate, hover on a dropped frame.</span></span>  <span data-ttu-id="1ca3d-323">若要查看 Chromium 开放源代码项目中此功能的历史记录，请导航到"问题"[1075865][CR1075865]。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-323">To review the history of this feature in the Chromium open-source project, navigate to Issue [1075865][CR1075865].</span></span>  

:::image type="complex" source="../../media/2021/01/performance-frames-dropped-frames-red.msft.png" alt-text="丢弃的帧" lightbox="../../media/2021/01/performance-frames-dropped-frames-red.msft.png":::
   <span data-ttu-id="1ca3d-325">丢弃的帧</span><span class="sxs-lookup"><span data-stu-id="1ca3d-325">Dropped frames</span></span>  
:::image-end:::  

#### <span data-ttu-id="1ca3d-326">新的颜色对比度计算 - APCA (高级感知对比度) </span><span class="sxs-lookup"><span data-stu-id="1ca3d-326">New color contrast calculation - Advanced Perceptual Contrast Algorithm (APCA)</span></span>  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

<span data-ttu-id="1ca3d-327">APCA 高级感知对比度[算法 (APCA) ][GithubW3cSilverGuidelinesMethodsMethodFontCharacteristicContrastHtml]替换了颜色选取器中的[AA][W3cWaiWcag21QuickrefContrastMinimum] / [AAA][W3cWaiWcag21QuickrefContrastEnhanced]指南[对比率][DevtoolsAccessibilityReferenceViewContrastRatioTextElementColorPicker]。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-327">The [Advanced Perceptual Contrast Algorithm (APCA)][GithubW3cSilverGuidelinesMethodsMethodFontCharacteristicContrastHtml] replaces the [AA][W3cWaiWcag21QuickrefContrastMinimum]/[AAA][W3cWaiWcag21QuickrefContrastEnhanced] guidelines contrast ratio in the [Color Picker][DevtoolsAccessibilityReferenceViewContrastRatioTextElementColorPicker].</span></span>  <span data-ttu-id="1ca3d-328">APCA 是计算对比度的一种新方式。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-328">APCA is a new way to compute contrast.</span></span>  <span data-ttu-id="1ca3d-329">它基于对颜色感知的新式研究。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-329">It is based on modern research on color perception.</span></span>  <span data-ttu-id="1ca3d-330">与 AA/AAA 准则相比，APCA 更依赖于上下文。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-330">Compared to AA/AAA guidelines, APCA is more context-dependent.</span></span>  <span data-ttu-id="1ca3d-331">对比度基于文本、颜色和上下文的以下空间属性计算。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-331">The contrast is calculated based on the following spatial properties of the text, color, and context.</span></span>  

*   <span data-ttu-id="1ca3d-332">文本的空间属性，包括字体粗细和大小。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-332">Spatial properties of text that include font weight and size.</span></span>  
*   <span data-ttu-id="1ca3d-333">颜色的空间属性，包括文本和背景之间的感知对比度。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-333">Spatial properties of color that include perceived contrast between text and background.</span></span>  
*   <span data-ttu-id="1ca3d-334">包含环境光、周围和预期用途的上下文的空间属性。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-334">Spatial properties of context that include ambient light, surroundings, and intended purpose.</span></span>  
    
<span data-ttu-id="1ca3d-335">若要打开此实验，请导航到[][DevtoolsCustomizeIndexSettings]"设置实验"，并选中"启用新的高级感知对比度算法 (APCA) 替换以前的对比度比率  >  \*\*\*\*\*\*和 AA/AAA 指南"旁边的复选框\*\*。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-335">To turn on this experiment, navigate to [Settings][DevtoolsCustomizeIndexSettings] > **Experiments**  and choose the checkbox next to **Enable new Advanced Perceptual Contrast Algorithm (APCA) replacing previous contrast ratio and AA/AAA guidelines**.</span></span>  <span data-ttu-id="1ca3d-336">若要查看 Chromium 开放源代码项目中此功能的历史记录，请导航到"问题"[1121900][CR1121900]。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-336">To review the history of this feature in the Chromium open-source project, navigate to Issue [1121900][CR1121900].</span></span>  

:::image type="complex" source="../../media/2021/01/advanced-perceptual-contrast-algorithm.msft.png" alt-text="颜色选取器中的 APCA" lightbox="../../media/2021/01/advanced-perceptual-contrast-algorithm.msft.png":::
   <span data-ttu-id="1ca3d-338">颜色选取器中的 APCA</span><span class="sxs-lookup"><span data-stu-id="1ca3d-338">APCA in the Color Picker</span></span>  
:::image-end:::  

## <span data-ttu-id="1ca3d-339">下载 Microsoft Edge 预览频道</span><span class="sxs-lookup"><span data-stu-id="1ca3d-339">Download the Microsoft Edge preview channels</span></span>  

<span data-ttu-id="1ca3d-340">如果你使用的是 Windows、Linux 或 macOS，请考虑使用 [Microsoft Edge][MicrosoftEdgePreviewChannels] 预览频道作为默认开发浏览器。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-340">If you are on Windows, Linux, or macOS, consider using the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] as your default development browser.</span></span>  <span data-ttu-id="1ca3d-341">预览频道使你能够访问最新的 DevTools 功能。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-341">The preview channels give you access to the latest DevTools features.</span></span>  

## <span data-ttu-id="1ca3d-342">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="1ca3d-342">Getting in touch with Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]

<!-- links -->  

[DevtoolsWhatsNew85]: ../../2020/06/devtools.md "Microsoft Edge 85 (DevTools 中的新增) |Microsoft Docs"  

[DevtoolsAccessibilityReferenceViewContrastRatioTextElementColorPicker]: /microsoft-edge/devtools-guide-chromium/accessibility/reference#view-the-contrast-ratio-of-a-text-element-in-the-color-picker "查看颜色选取器中的文本元素的对比度 - 辅助功能参考|Microsoft Docs"  
[DevtoolsCssReferenceChangeCss]: /microsoft-edge/devtools-guide-chromium/css/reference#change-css "更改 CSS - CSS |Microsoft Docs"  
[DevtoolsCustomizeIndexSettings]: /microsoft-edge/devtools-guide-chromium/customize/index#settings "设置 - 自定义 Microsoft Edge DevTools | Microsoft Docs"  
[DevtoolsCustomizeShortcuts]: microsoft-edge/devtools-guide-chromium/customize/shortcuts "自定义 Microsoft Edge DevTools |Microsoft Docs"  
[DevtoolsDeviceModeDualScreenFoldablesTestingFoldableDualScreenDevices]: /microsoft-edge/devtools-guide-chromium/device-mode/dual-screen-and-foldables#testing-on-foldable-and-dual-screen-devices "在可折叠和双屏幕设备上进行测试 - 模拟 Microsoft Edge DevTools |Microsoft Docs"  
[DevtoolsDeviceModeIndex]: /microsoft-edge/devtools-guide-chromium/device-mode/index "在 Microsoft Edge DevTools 中模拟移动设备 | Microsoft Docs"  
[DevtoolsDeviceModeIndexSimulateMobileViewport]: /microsoft-edge/devtools-guide-chromium/device-mode/index#simulate-a-mobile-viewport "模拟移动视口 - 模拟 Microsoft Edge DevTools |Microsoft Docs"  
[DevtoolsEvaluatePerformanceReferenceRecordLoadPerformance]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference#record-load-performance "记录负载性能 - 性能分析|Microsoft Docs"  
[DevtoolsInspectStylesEditFonts]: /microsoft-edge/devtools-guide-chromium/inspect-styles/edit-fonts "在 DevTools | 中的"样式"窗格中编辑 CSS 字体样式和|Microsoft Docs"  
[DevtoolsMain]: /microsoft-edge/devtools-guide-chromium/index "Microsoft Edge (Chromium) 开发人员工具概述|Microsoft Docs"  

[DualScreenIntroductionHowToWorkWithSeam]: /dual-screen/introduction#how-to-work-with-the-seam "如何使用设备 - 双屏幕设备简介|Microsoft Docs"  
[DualScreenWebCssMediaSpanning]: /dual-screen/web/css-media-spanning "用于双屏检测方法的 CSS 媒体屏幕|Microsoft Docs"  
[DualScreenWebJavascriptGetwindowsegments]: /dual-screen/web/javascript-getwindowsegments "适用于双屏幕设备的 getWindowSegments JavaScript API |Microsoft Docs"  

[GithubMicrosoftedgeDevtoolssamplesWhatsNew89TargetCssDemoHtmlSection1]: https://microsoftedge.github.io/DevToolsSamples/whats-new/89/target-css-demo.html#section-1 "第 1 部分 - 适用于 Microsoft Edge 89 (开发工具中的新增功能的目标) |GitHub"  
[GithubMicrosoftVscodeEdgeDevtools]: https://github.com/microsoft/vscode-edge-devtools "microsoft/vscode-edge-devtools |GitHub"  
[GithubMicrosoftVscodeEdgeDevtoolsPull229]: https://github.com/microsoft/vscode-edge-devtools/pull/229 "拉 229：在设置中实现下拉列表以更改主题|GitHub"  
[GithubMicrosoftVscodeEdgeDevtoolsPull233]: https://github.com/microsoft/vscode-edge-devtools/pull/233 "拉取 233：将适用于 Microsoft Edge 的调试器作为依赖项|GitHub"  
[GithubMicrosoftVscodeEdgeDevtoolsPull235]: https://github.com/microsoft/vscode-edge-devtools/pull/235 "拉取 235：将 Edge DevTools 版本升级到 85.0.564.40 |GitHub"  
[GithubMicrosoftVscodeEdgeDevtoolsPull248]: https://github.com/microsoft/vscode-edge-devtools/pull/248 "拉 248：将单个关闭按钮添加到实例面板|GitHub"  
[GithubW3cSilverGuidelinesMethodsMethodFontCharacteristicContrastHtml]: https://w3c.github.io/silver/guidelines/methods/Method-font-characteristic-contrast.html "选择字体特征和背景颜色以提供足够的对比度，以便可读性|W3C"  
[GithubW3cWebappsecTrustedTypesDistSpec]: https://w3c.github.io/webappsec-trusted-types/dist/spec  "受信任类型|W3C"  

[MicrosoftSurfaceDevicesSurfaceDuo]: https://www.microsoft.com/surface/devices/surface-duo "新的 Surface Duo |Microsoft"  

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download "Microsoft Edge 预览频道"  

[VisualstudioCodeDocsEditorExtensionGalleryUpdateExtensionManually]: https://code.visualstudio.com/docs/editor/extension-gallery#_update-an-extension-manually "手动更新扩展 - 扩展市场|Visual Studio代码"  

[VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools]: https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools "Microsoft Edge Tools for Visual Studio Code |Visual Studio市场"  
[VisualstudioMarketplaceMsjsdiagDebuggerMicrosoftEdge]: https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge "适用于 Microsoft Edge |Visual Studio市场"  

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium 漏洞"  

<!--[CR174309]: https://crbug.com/174309 "Issue 174309: DevTools: Allow to customize keyboard shortcuts/key bindings | Chromium bugs"  -->  
<!--[CR772558]: https://crbug.com/772558 "Issue 772558: DevTools: Update to latest version of Lighthouse | Chromium bugs"  -->  
<span data-ttu-id="1ca3d-371">[CR978059]："问题 978059：在筛选 Cookie 时删除它们，删除所有 Cookie，而不只是删除已筛选| https://crbug.com/978059 Chromium bug"</span><span class="sxs-lookup"><span data-stu-id="1ca3d-371">[CR978059]: https://crbug.com/978059 "Issue 978059: Deleting cookies when filtering them, delete all the cookies not just the filtered ones | Chromium bugs"</span></span>  
<span data-ttu-id="1ca3d-372">[CR997625]：" https://crbug.com/997625 问题 997625：新功能|需要查看 Cookie 中 url 解码值的选项|Chromium bug"</span><span class="sxs-lookup"><span data-stu-id="1ca3d-372">[CR997625]: https://crbug.com/997625 "Issue 997625: New Feature Req | Need option to see url-decoded value in cookies | Chromium bugs"</span></span>  
<span data-ttu-id="1ca3d-373">[CR1003629]："问题 https://crbug.com/1003629 1003629：捕获节点不再屏幕截图折叠下方节点。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-373">[CR1003629]: https://crbug.com/1003629 "Issue 1003629: Capture Node does not screenshot the node below the fold anymore.</span></span> <span data-ttu-id="1ca3d-374">|Chromium bug"</span><span class="sxs-lookup"><span data-stu-id="1ca3d-374">| Chromium bugs"</span></span>  
<span data-ttu-id="1ca3d-375">[CR1012337]："问题 https://crbug.com/1012337 1012337：清除网站数据会破坏非 Google 网站上 Google 会话|Chromium bug"</span><span class="sxs-lookup"><span data-stu-id="1ca3d-375">[CR1012337]: https://crbug.com/1012337 "Issue 1012337: Clear Site Data destroys Google session on non-Google sites | Chromium bugs"</span></span>  
<span data-ttu-id="1ca3d-376">[CR1028078]："问题 https://crbug.com/1028078 1028078：联机和脱机在列表中彼此|Chromium bug"</span><span class="sxs-lookup"><span data-stu-id="1ca3d-376">[CR1028078]: https://crbug.com/1028078 "Issue 1028078: Put Online and Offline next to each other in the list | Chromium bugs"</span></span>  
<span data-ttu-id="1ca3d-377">[CR1054281]：" https://crbug.com/1054281 问题 1054281：功能请求：DevTools 应模拟可折叠和双屏幕设备|Chromium bug"</span><span class="sxs-lookup"><span data-stu-id="1ca3d-377">[CR1054281]: https://crbug.com/1054281 "Issue 1054281: Feature Request: DevTools should emulate foldable and dual-screen devices | Chromium bugs"</span></span>  
<!--[CR1073909]: https://crbug.com/1073909 "Issue 1073909: BLOCKED | Chromium bugs"  -->  
<span data-ttu-id="1ca3d-378">[CR1075865]：" https://crbug.com/1075865 问题 1075865：在 devtools 时间线中显示丢弃|Chromium bug"</span><span class="sxs-lookup"><span data-stu-id="1ca3d-378">[CR1075865]: https://crbug.com/1075865 "Issue 1075865: Show dropped frames in devtools timeline | Chromium bugs"</span></span>  
<span data-ttu-id="1ca3d-379">[CR1093229]：" https://crbug.com/1093229 问题 1093229：DevTools：提供专用的字样编辑器 UI |Chromium bug"</span><span class="sxs-lookup"><span data-stu-id="1ca3d-379">[CR1093229]: https://crbug.com/1093229 "Issue 1093229: DevTools: offer a specialized typeface editor UI | Chromium bugs"</span></span>  
<span data-ttu-id="1ca3d-380">[CR1121900]：" https://crbug.com/1121900 问题 1121900：DevTools：根据新规范更新对比度计算|Chromium bug"</span><span class="sxs-lookup"><span data-stu-id="1ca3d-380">[CR1121900]: https://crbug.com/1121900 "Issue 1121900: DevTools: update contrast calculation logic per new spec | Chromium bugs"</span></span>  
<span data-ttu-id="1ca3d-381">[CR1122507]：" https://crbug.com/1122507 问题 1122507：帧树视图中的 Surface 工作|Chromium bug"</span><span class="sxs-lookup"><span data-stu-id="1ca3d-381">[CR1122507]: https://crbug.com/1122507 "Issue 1122507: Surface worker information in frame tree view | Chromium bugs"</span></span>  
<span data-ttu-id="1ca3d-382">[CR1122580]：" https://crbug.com/1122580 问题 1122580：无法禁用重新加载时的网络|Chromium bug"</span><span class="sxs-lookup"><span data-stu-id="1ca3d-382">[CR1122580]: https://crbug.com/1122580 "Issue 1122580: Impossible to disable network recording on reload | Chromium bugs"</span></span>  
<!--[CR1126824]: https://crbug.com/1126824 "Issue 1126824: ☂ Support Trust Token debugging in DevTools | Chromium bugs"  -->  
<span data-ttu-id="1ca3d-383">[CR1136394]：" https://crbug.com/1136394 问题 1136394：Flexbox 工具|Chromium bug"</span><span class="sxs-lookup"><span data-stu-id="1ca3d-383">[CR1136394]: https://crbug.com/1136394 "Issue 1136394: Flexbox tooling | Chromium bugs"</span></span>  
<!--[CR1137837]: https://crbug.com/1137837 "Issue 1137837: ☂ Improve Trusted Types support in DevTools | Chromium bugs"  -->  
<span data-ttu-id="1ca3d-384">[CR1139899]：" https://crbug.com/1139899 问题 1139899：报告帧详细信息视图中的 API |Chromium bug"</span><span class="sxs-lookup"><span data-stu-id="1ca3d-384">[CR1139899]: https://crbug.com/1139899 "Issue 1139899: Report gated API availability in frame details view | Chromium bugs"</span></span>  
<span data-ttu-id="1ca3d-385">[CR1139949]：" https://crbug.com/1139949 问题 1139949：Flexbox 覆盖|Chromium bug"</span><span class="sxs-lookup"><span data-stu-id="1ca3d-385">[CR1139949]: https://crbug.com/1139949 "Issue 1139949: Flexbox overlay | Chromium bugs"</span></span>  
<!--[CR1142804]: https://crbug.com/1142804 "Issue 1142804: Implement break-on-trusted-type-violation | Chromium bugs"  -->  
<!--[CR1144127]: https://crbug.com/1144127 "Issue 1144127: BLOCKED | Chromium bugs"  -->  
<span data-ttu-id="1ca3d-386">[CR1147016]：" https://crbug.com/1147016 问题 1147016：颜色选取器不显示在 var () 函数中。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-386">[CR1147016]: https://crbug.com/1147016 "Issue 1147016: The color picker is not displayed in the var() function.</span></span> <span data-ttu-id="1ca3d-387">|Chromium bug"</span><span class="sxs-lookup"><span data-stu-id="1ca3d-387">| Chromium bugs"</span></span>  
<span data-ttu-id="1ca3d-388">[CR1148353]：" https://crbug.com/1148353 问题 1148353：功能请求：从 devtools 控制台文件复制|Chromium bug"</span><span class="sxs-lookup"><span data-stu-id="1ca3d-388">[CR1148353]: https://crbug.com/1148353 "Issue 1148353: Feature Request: Copy Object from the devtools console | Chromium bugs"</span></span>  
<span data-ttu-id="1ca3d-389">[CR1149859]：" https://crbug.com/1149859 问题 1149859： [功能请求][控制台] 将复制对象添加到剪贴板项目到上下文菜单|Chromium bug"</span><span class="sxs-lookup"><span data-stu-id="1ca3d-389">[CR1149859]: https://crbug.com/1149859 "Issue 1149859: [feature request][Console] add copy object to clipboard item to contextual menu | Chromium bugs"</span></span>  
<span data-ttu-id="1ca3d-390">[CR1150797]：" https://crbug.com/1150797 问题 1150797：在元素面板菜单中添加重复元素上下文|Chromium bug"</span><span class="sxs-lookup"><span data-stu-id="1ca3d-390">[CR1150797]: https://crbug.com/1150797 "Issue 1150797: Add Duplicate element context menu in Element panel | Chromium bugs"</span></span>  
<!--[CR1150883]: https://crbug.com/1150883 "Issue 1150883: Remove TT messages from the console but keep underlining in the sources tab | Chromium bugs"  -->  
<!--[CR1152290]: https://crbug.com/1152290 "Issue 1152290: Devtools support for QuicTransport | Chromium bugs"  -->  
<span data-ttu-id="1ca3d-391">[CR1152391]：" https://crbug.com/1152391 问题 1152391：支持在样式面板中复制 CSS 上下文|Chromium bug"</span><span class="sxs-lookup"><span data-stu-id="1ca3d-391">[CR1152391]: https://crbug.com/1152391 "Issue 1152391: Support for copy CSS context menu in styles panel | Chromium bugs"</span></span>  
<span data-ttu-id="1ca3d-392">[CR1155120]：" https://crbug.com/1155120 问题 1155120：[FR]支持复制文件名和行号|Chromium bug"</span><span class="sxs-lookup"><span data-stu-id="1ca3d-392">[CR1155120]: https://crbug.com/1155120 "Issue 1155120: [FR]Support copy file name and line number | Chromium bugs"</span></span>  
<span data-ttu-id="1ca3d-393">[CR1156628]：" https://crbug.com/1156628 问题 1156628：DevTools：添加对 ：target in force 元素状态功能|Chromium bug"</span><span class="sxs-lookup"><span data-stu-id="1ca3d-393">[CR1156628]: https://crbug.com/1156628 "Issue 1156628: DevTools: add support for :target in force element state feature | Chromium bugs"</span></span>  
<span data-ttu-id="1ca3d-394">[CR1157329]："问题 1157329：辅助功能 - 讲述人：讲述人未在"样式"选项卡中公布适用于代码的建议的计数 https://crbug.com/1157329 和|Chromium bug"</span><span class="sxs-lookup"><span data-stu-id="1ca3d-394">[CR1157329]: https://crbug.com/1157329 "Issue 1157329: Accessibility - Narrator: Narrator is not announcing the count and position for suggestions available for code in Styles tab | Chromium bugs"</span></span>  

[MdnDocsWebCssTarget]: https://developer.mozilla.org/docs/web/css/:target "：target |MDN"  

[SamsungUsMobileGalaxyFold]: https://www.samsung.com/us/mobile/galaxy-fold "百年百|美国三星"  

[W3cWaiWcag21QuickrefContrastEnhanced]: https://www.w3.org/WAI/WCAG21/quickref#contrast-enhanced "对比度 (增强) - 如何满足 WCAG (快速参考) |W3C"  
[W3cWaiWcag21QuickrefContrastMinimum]: https://www.w3.org/WAI/WCAG21/quickref#contrast-minimum "对比度 (最小) - 如何满足 WCAG (快速参考) |W3C"  

> [!NOTE]
> <span data-ttu-id="1ca3d-399">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-399">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="1ca3d-400">原始页面位于 [此处](https://developers.google.com/web/updates/2021/01/devtools/index)，并由 [Jecelyn Yeen][JecelynYeen] \（开发人员支持者，Chrome DevTools\）制作。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-400">The original page is found [here](https://developers.google.com/web/updates/2021/01/devtools/index) and is authored by [Jecelyn Yeen][JecelynYeen] \(Developer advocate, Chrome DevTools\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="1ca3d-402">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="1ca3d-402">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen

[SpanningPlaceholder]: link-t-b-d "跨域占位符"  
