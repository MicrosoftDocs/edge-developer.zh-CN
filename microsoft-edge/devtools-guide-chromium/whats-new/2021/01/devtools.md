---
description: “新增功能”工具现在为“欢迎”，内含“样式”窗格中的可视字体编辑器、CSS 弹性框调试工具等。
title: DevTools 中的新增功能 (Microsoft Edge 89)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.localizationpriority: high
ms.openlocfilehash: ec14d802af52c0bb2e658549f48764279c787f47
ms.sourcegitcommit: de75fda30bb8964e9a184228d068b4402ec59c3e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2021
ms.locfileid: "11514366"
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
# <a name="whats-new-in-devtools-microsoft-edge-89"></a><span data-ttu-id="3f195-104">DevTools 中的新增功能 (Microsoft Edge 89)</span><span class="sxs-lookup"><span data-stu-id="3f195-104">What's New In DevTools (Microsoft Edge 89)</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/edge-whats-new-note.md)]  

## <a name="whats-new-is-now-welcome"></a><span data-ttu-id="3f195-105">“新增功能”工具现在为“欢迎”</span><span class="sxs-lookup"><span data-stu-id="3f195-105">What's New is now Welcome</span></span>  

<!--  Title: What's New is now Welcome  -->  
<!--  Subtitle: The What's New tool now has a new appearance and a new name:  Welcome -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

<span data-ttu-id="3f195-106">Microsoft Edge DevTools 中的“**新增功能**”工具现在具有新的外观和新名称：“**欢迎**”。</span><span class="sxs-lookup"><span data-stu-id="3f195-106">The **What's New** tool in the Microsoft Edge DevTools now has a new appearance and a new name:  **Welcome**.</span></span>  <span data-ttu-id="3f195-107">“**欢迎**”工具仍会显示最新的 DevTools 新闻和更新。</span><span class="sxs-lookup"><span data-stu-id="3f195-107">The **Welcome** tool still displays the latest DevTools news and updates.</span></span>  <span data-ttu-id="3f195-108">它现在还包括指向 Microsoft Edge DevTools 文档的链接、提交反馈的方式等。</span><span class="sxs-lookup"><span data-stu-id="3f195-108">It now also includes links to Microsoft Edge DevTools documentation, ways to submit feedback, and more.</span></span>  <span data-ttu-id="3f195-109">若要在每次更新 Microsoft Edge 后显示“**欢迎**”工具，请选中标题下的“**每次更新后打开选项卡**”旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="3f195-109">To display the **Welcome** tool after each update to Microsoft Edge, choose the checkbox next to **Open tab after each update** under the title.</span></span>  <span data-ttu-id="3f195-110">若要关闭“**欢迎**”工具，请选择选项卡标题右侧的 **X**。</span><span class="sxs-lookup"><span data-stu-id="3f195-110">To close the **Welcome** tool, choose the **X** on the right-side of the tab title.</span></span>  <span data-ttu-id="3f195-111">如果你更喜欢原来的“**新增功能**”工具，请导航至“[设置][DevtoolsCustomizeIndexSettings]” > “**试验**”，并取消选中“**启用‘欢迎’选项卡**”旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="3f195-111">If you prefer the original **What's New** tool, navigate to [Settings][DevtoolsCustomizeIndexSettings] > **Experiments** and remove the checkbox next to **Enable Welcome tab**.</span></span>  

:::image type="complex" source="../../media/2021/01/welcome-tool-whats-new-88.msft.png" alt-text="突出显示“欢迎”工具" lightbox="../../media/2021/01/welcome-tool-whats-new-88.msft.png":::
   <span data-ttu-id="3f195-113">突出显示“**欢迎**”工具</span><span class="sxs-lookup"><span data-stu-id="3f195-113">The **Welcome** tool is highlighted</span></span>  
:::image-end:::  

## <a name="visual-font-editor-in-the-styles-pane"></a><span data-ttu-id="3f195-114">“样式”窗格中的可视字体编辑器</span><span class="sxs-lookup"><span data-stu-id="3f195-114">Visual Font Editor in the Styles pane</span></span>  

<!--  Title: Visual font editor in the Styles pane  -->  
<!--  Subtitle: Visual font editor in the Styles pane -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

<span data-ttu-id="3f195-115">在 CSS 中处理字体时，请使用新的可视[字体编辑器][DevtoolsInspectStylesEditFonts]。</span><span class="sxs-lookup"><span data-stu-id="3f195-115">When you work with fonts in CSS, use the new visual [Font Editor][DevtoolsInspectStylesEditFonts].</span></span>  <span data-ttu-id="3f195-116">你可以定义回退字体，并使用滑块定义字体粗细、大小、行高和间距。</span><span class="sxs-lookup"><span data-stu-id="3f195-116">You may define fallback fonts, and use sliders to define font weight, size, line-height, and spacing.</span></span>  <span data-ttu-id="3f195-117">**字体编辑器**可帮助你完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="3f195-117">The **Font Editor** helps you complete the following actions.</span></span>  

*   <span data-ttu-id="3f195-118">在不同字体属性的单位之间切换</span><span class="sxs-lookup"><span data-stu-id="3f195-118">Switch between units for different font properties</span></span>  
*   <span data-ttu-id="3f195-119">在不同字体属性的关键字之间切换</span><span class="sxs-lookup"><span data-stu-id="3f195-119">Switch between keywords for different font properties</span></span>  
*   <span data-ttu-id="3f195-120">转换单位</span><span class="sxs-lookup"><span data-stu-id="3f195-120">Convert units</span></span>  
*   <span data-ttu-id="3f195-121">生成准确的 CSS 代码</span><span class="sxs-lookup"><span data-stu-id="3f195-121">Generate accurate CSS code</span></span>  
    
<span data-ttu-id="3f195-122">若要启用此试验，请导航至“[设置][DevtoolsCustomizeIndexSettings]” > “**试验**”，然后选中“**在‘样式’窗格中启用新的字体编辑器工具**”旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="3f195-122">To turn on this experiment, navigate to [Settings][DevtoolsCustomizeIndexSettings] > **Experiments** and choose the checkbox next to **Enable new Font Editor tools within Styles pane**.</span></span>  <span data-ttu-id="3f195-123">有关详细信息，请导航至“[在 DevTools 的‘样式’窗格中编辑 CSS 字体样式和设置][DevtoolsInspectStylesEditFonts]”。</span><span class="sxs-lookup"><span data-stu-id="3f195-123">For more information, navigate to [Edit CSS font styles and settings in the Styles pane in DevTools][DevtoolsInspectStylesEditFonts].</span></span>  <span data-ttu-id="3f195-124">若要在 Chromium 开源项目中查看此功能的历史记录，请导航至问题 [1093229][CR1093229]。</span><span class="sxs-lookup"><span data-stu-id="3f195-124">To review the history of this feature in the Chromium open-source project, navigate to Issue [1093229][CR1093229].</span></span>  

:::image type="complex" source="../../media/2021/01/visual-font-editor.msft.png" alt-text="可视字体编辑器在“样式”窗格中突出显示" lightbox="../../media/2021/01/visual-font-editor.msft.png":::
   <span data-ttu-id="3f195-126">可视**字体编辑器**在“**样式**”窗格中突出显示</span><span class="sxs-lookup"><span data-stu-id="3f195-126">The visual **Font editor** is highlighted in the **Styles** pane</span></span>  
:::image-end:::  

## <a name="css-flexbox-debugging-tools"></a><span data-ttu-id="3f195-127">CSS 弹性框调试工具</span><span class="sxs-lookup"><span data-stu-id="3f195-127">CSS Flexbox debugging tools</span></span>  

<span data-ttu-id="3f195-128">弹性框调试功能正在积极开发中。</span><span class="sxs-lookup"><span data-stu-id="3f195-128">Flexbox debugging features are in active development.</span></span>  <span data-ttu-id="3f195-129">若要启用以下两个功能的试验，请导航至“[设置][DevtoolsCustomizeIndexSettings]” > “**试验**”，然后选择“**启用新的 CSS 弹性框调试功能**”旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="3f195-129">To turn on the experiment for the following two features, navigate to [Settings][DevtoolsCustomizeIndexSettings] > **Experiments** and choose the checkbox next to **Enable new CSS Flexbox debugging features**.</span></span>  <span data-ttu-id="3f195-130">若要在 Chromium 开源项目中查看此功能的历史记录，请导航至问题 [1136394][CR1136394] 和 [1139949][CR1139949]。</span><span class="sxs-lookup"><span data-stu-id="3f195-130">To review the history of this feature in the Chromium open-source project, navigate to Issues [1136394][CR1136394] and [1139949][CR1139949].</span></span>  

### <a name="new-flexbox-flex-icon-helps-identify-and-display-flex-containers"></a><span data-ttu-id="3f195-131">新的弹性框 (flex) 图标有助于识别和显示 flex 容器</span><span class="sxs-lookup"><span data-stu-id="3f195-131">New Flexbox (flex) icon helps identify and display flex containers</span></span>  

<!--  Title: Display Flexbox containers with Flexbox (flex) icon  -->  
<!--  Subtitle: New Flexbox (flex) icon in the Elements tool help you identify Flexbox containers in your code.  When toggled, the adorner displays and hides outlines of the flex container to help you debug the layout -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

<span data-ttu-id="3f195-132">在“**元素**”工具中，新的弹性框 (flex) 图标可帮助你识别代码中的弹性框容器。</span><span class="sxs-lookup"><span data-stu-id="3f195-132">In the **Elements** tool, the new Flexbox (flex) icon helps you identify Flexbox containers in your code.</span></span>  <span data-ttu-id="3f195-133">选择弹性框 (flex) 图标可打开或关闭显示弹性框容器轮廓的覆盖效果。</span><span class="sxs-lookup"><span data-stu-id="3f195-133">Choose the Flexbox \(flex\) icon to turn on or off the overlay effect that outlines a Flexbox container.</span></span>  <span data-ttu-id="3f195-134">可在“**布局**”窗格中自定义覆盖的颜色，其位于“**样式**”和“**已计算**”旁边。</span><span class="sxs-lookup"><span data-stu-id="3f195-134">You may customize the color of the overlay in the **Layout** pane, which is located next to **Styles** and **Computed**.</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="3f195-135">若要打开和关闭显示弹性框容器轮廓的覆盖效果，请选择弹性框 (`flex`) 图标。</span><span class="sxs-lookup"><span data-stu-id="3f195-135">To turn on and off the overlay effect that outlines the Flexbox container, choose the Flexbox \(`flex`\) icon.</span></span>  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="3f195-136">可在“**布局**”窗格中的“**样式**”和“**已计算**”旁边自定义覆盖的颜色。</span><span class="sxs-lookup"><span data-stu-id="3f195-136">You may customize the color of the overlay in the **Layout** pane next to **Styles** and **Computed**.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-flex-container.msft.png" alt-text="弹性框 (flex) 图标和网页突出显示" lightbox="../../media/2021/01/elements-flex-container.msft.png":::
         <span data-ttu-id="3f195-138">**弹性框** (`flex`) 图标和网页突出显示</span><span class="sxs-lookup"><span data-stu-id="3f195-138">The **Flexbox** \(`flex`\) icon and webpage highlighted</span></span> :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-layout-flex-container.msft.png" alt-text="“布局”窗格中突出显示的弹性框覆盖" lightbox="../../media/2021/01/elements-layout-flex-container.msft.png":::
         <span data-ttu-id="3f195-140">“**布局**”窗格中突出显示的**弹性框覆盖**</span><span class="sxs-lookup"><span data-stu-id="3f195-140">The **Flexbox overlays** highlighted in the **Layout** pane</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

### <a name="display-alignment-icons-and-visual-guides-when-flexbox-layouts-change-using-css-properties"></a><span data-ttu-id="3f195-141">使用 CSS 属性更改弹性框布局时显示对齐图标和可视化向导</span><span class="sxs-lookup"><span data-stu-id="3f195-141">Display alignment icons and visual guides when Flexbox layouts change using CSS properties</span></span>  

<!--  Title: Display alignment icons and visual guides for changes to Flexbox layouts from CSS properties  -->  
<!--  Subtitle:  CSS autocomplete in the Styles tool now displays icons next to Flexbox properties to help you review the effect a property has on your Flexbox layout -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

<span data-ttu-id="3f195-142">当你编辑弹性框布局的 CSS 时，“**样式**”窗格中的 CSS 自动完成现在会在相关弹性框属性旁边显示有用的图标。</span><span class="sxs-lookup"><span data-stu-id="3f195-142">When you edit CSS for your Flexbox layout, CSS autocompletes in the **Styles** pane now displays helpful icons next to relevant Flexbox properties.</span></span>  <span data-ttu-id="3f195-143">若要尝试此新功能，请打开“**元素**”工具并选择一个 flex 容器。</span><span class="sxs-lookup"><span data-stu-id="3f195-143">To try this new feature, open the **Elements** tool and select a flex container.</span></span>  <span data-ttu-id="3f195-144">然后在“**样式**”窗格中添加或更改该容器上的属性。</span><span class="sxs-lookup"><span data-stu-id="3f195-144">Then add or change a property on that container in the **Styles** pane.</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="3f195-145">自动完成菜单现在显示指示对齐属性效果的图标，例如 `align-content` 和 `align-items`。</span><span class="sxs-lookup"><span data-stu-id="3f195-145">The autocomplete menu now displays icons that indicate the effect of alignment properties such as `align-content` and `align-items`.</span></span>  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="3f195-146">此外，DevTools 现在还会显示一条指导线，帮助你更好地查看 `align-items` CSS 属性。</span><span class="sxs-lookup"><span data-stu-id="3f195-146">Additionally, DevTools now displays a guiding line to help you better review the `align-items` CSS property.</span></span>  <span data-ttu-id="3f195-147">`gap` CSS 属性也受支持。</span><span class="sxs-lookup"><span data-stu-id="3f195-147">The `gap` CSS property is supported as well.</span></span>  <span data-ttu-id="3f195-148">在下图中，`gap` CSS 属性设置为 `gap: 12px;`，并显示每个间隙的阴影图案。</span><span class="sxs-lookup"><span data-stu-id="3f195-148">In the following figure, the `gap` CSS property is set to `gap: 12px;` and the hatching pattern for each gap is displayed.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-flex-container-align.msft.png" alt-text="突出显示以 align- 开头的 CSS 属性的“自动完成”菜单" lightbox="../../media/2021/01/elements-flex-container-align.msft.png":::
         <span data-ttu-id="3f195-150">突出显示以以下内容开头的 CSS 属性的“自动完成”菜单</span><span class="sxs-lookup"><span data-stu-id="3f195-150">Autocomplete menu highlighted for CSS properties that start with</span></span> `align-`  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-flex-container-align-items-center-gap-12px.msft.png" alt-text="CSS 属性和网页中的弹性框间隙突出显示" lightbox="../../media/2021/01/elements-flex-container-align-items-center-gap-12px.msft.png":::
         <span data-ttu-id="3f195-152">CSS 属性和网页中的弹性框 `gap` 突出显示</span><span class="sxs-lookup"><span data-stu-id="3f195-152">Flexbox `gap` in CSS properties and webpage highlighted</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="add-tools-quickly-with-new-more-tools-button"></a><span data-ttu-id="3f195-153">使用新的“更多工具”按钮快速添加工具</span><span class="sxs-lookup"><span data-stu-id="3f195-153">Add tools quickly with new More Tools button</span></span>  

<!--  Title: Add tools quickly with new More Tools button  -->  
<!--  Subtitle: A convenient way to open new tools in Microsoft Edge DevTools -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

<span data-ttu-id="3f195-154">现在，你有了一种在 Microsoft Edge DevTools 中打开更多工具的新方法。</span><span class="sxs-lookup"><span data-stu-id="3f195-154">You now have a new way to open more tools in the Microsoft Edge DevTools.</span></span>  <span data-ttu-id="3f195-155">在打开此试验后，“**更多工具**”图标将在主面板右侧显示为加号 (`+`)。</span><span class="sxs-lookup"><span data-stu-id="3f195-155">After you turn on this experiment, the **More Tools** icon displays as a plus sign (`+`) to the right of the main panel.</span></span>  <span data-ttu-id="3f195-156">若要显示要添加到主面板的其他工具的列表，请选择“**更多工具**”\(`+`\) 图标。</span><span class="sxs-lookup"><span data-stu-id="3f195-156">To display a list of other tools to add to the main panel, choose the **More Tools** \(`+`\) icon.</span></span>  <span data-ttu-id="3f195-157">若要启用此试验，请导航至“[设置][DevtoolsCustomizeIndexSettings]” > “**试验**”，然后选中“**启用 + 按钮选项卡菜单以打开更多工具**”旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="3f195-157">To turn on this experiment, navigate to [Settings][DevtoolsCustomizeIndexSettings] > **Experiments**, and then choose the checkbox next to **Enable + button tab menus to open more tools**.</span></span>  

:::image type="complex" source="../../media/2021/01/more-tools.msft.png" alt-text="DevTools 中突出显示“更多工具”" lightbox="../../media/2021/01/more-tools.msft.png":::
   <span data-ttu-id="3f195-159">DevTools 中突出显示“**更多工具**”</span><span class="sxs-lookup"><span data-stu-id="3f195-159">**More Tools** highlighted in DevTools</span></span>  
:::image-end:::  

## <a name="assistive-technologies-now-announce-position-and-count-of-css-suggestions"></a><span data-ttu-id="3f195-160">辅助技术现在显示 CSS 建议的位置和计数</span><span class="sxs-lookup"><span data-stu-id="3f195-160">Assistive technologies now announce position and count of CSS suggestions</span></span>  

<!--  Title: Assistive technologies now announce position and count of CSS suggestions  -->  
<!--  Subtitle: CSS suggestions are now easier to navigate using screen readers -->  

<span data-ttu-id="3f195-161">编辑 CSS 时，你将获得功能的下拉列表。</span><span class="sxs-lookup"><span data-stu-id="3f195-161">When you edit CSS, you get a dropdown of features.</span></span>  <span data-ttu-id="3f195-162">辅助技术用户无法使用此功能，因为它是在 Microsoft Edge 版本 89 中公布的。</span><span class="sxs-lookup"><span data-stu-id="3f195-162">This feature was not available to users of assistive technologies, since it is announced in Microsoft Edge version 89.</span></span>  <span data-ttu-id="3f195-163">辅助技术用户现在可以在“**样式**”窗格中浏览 CSS 建议。</span><span class="sxs-lookup"><span data-stu-id="3f195-163">A user of assistive technologies may now navigate CSS suggestions in the **Styles** pane.</span></span>  <span data-ttu-id="3f195-164">在 Microsoft Edge 版本 88 及更早版本中，辅助技术公布了 `Suggestion`，因为用户在“**导航**”窗格中编辑 CSS 时浏览了建议列表。</span><span class="sxs-lookup"><span data-stu-id="3f195-164">In Microsoft Edge version 88 and earlier, assistive technology announced `Suggestion` as a user navigated through the list of suggestions when editing CSS in the **Styles** pane.</span></span>  <span data-ttu-id="3f195-165">在 Microsoft Edge 版本 89 中，辅助技术用户现在可以听到当前建议的位置和计数。</span><span class="sxs-lookup"><span data-stu-id="3f195-165">In Microsoft Edge version 89, a user of assistive technology now hears the position and count of the current suggestion.</span></span>  <span data-ttu-id="3f195-166">当用户浏览建议列表时，每条建议都会公布，例如建议 3/5。</span><span class="sxs-lookup"><span data-stu-id="3f195-166">Each suggestion is announced as the user navigates through the list of suggestions, such as Suggestion 3 of 5.</span></span>  <span data-ttu-id="3f195-167">若要了解有关在 DevTools 中编写 CSS 的详细信息，请导航至“[更改 CSS][DevtoolsCssReferenceChangeCss]”。</span><span class="sxs-lookup"><span data-stu-id="3f195-167">To learn more about writing CSS in the DevTools, navigate to [Change CSS][DevtoolsCssReferenceChangeCss].</span></span>  <span data-ttu-id="3f195-168">若要在 Chromium 开源项目中查看此功能的历史记录，请导航至问题 [1157329][CR1157329]。</span><span class="sxs-lookup"><span data-stu-id="3f195-168">To review the history of this feature in the Chromium open-source project, navigate to Issue [1157329][CR1157329].</span></span>  

<span data-ttu-id="3f195-169">若要在启用此试验的情况下查看显示和朗读多条建议的视频，请导航至 YouTube 上的“[Voiceover 公布 devtools 选项](https://youtu.be/9TcUpleEwwA)”。</span><span class="sxs-lookup"><span data-stu-id="3f195-169">To view a video that displays and reads aloud several suggestions with this experiment turned on, navigate to [Voiceover announcing devtools options](https://youtu.be/9TcUpleEwwA) on YouTube.</span></span>  

:::image type="complex" source="../../media/2021/01/announce-css-suggestion.msft.png" alt-text="“样式”窗格中突出显示建议" lightbox="../../media/2021/01/announce-css-suggestion.msft.png":::
   <span data-ttu-id="3f195-171">“**样式**”窗格中突出显示 `suggestion` 列表</span><span class="sxs-lookup"><span data-stu-id="3f195-171">The `suggestion` list highlighted in the **Styles** pane</span></span>  
:::image-end:::  

## <a name="emulate-surface-duo-and-samsung-galaxy-fold"></a><span data-ttu-id="3f195-172">模拟 Surface Duo 和 Samsung Galaxy Fold</span><span class="sxs-lookup"><span data-stu-id="3f195-172">Emulate Surface Duo and Samsung Galaxy Fold</span></span>  

<!--  Title: Emulate new dual-screen and foldable devices  -->  
<!--  Subtitle: Test the appearance and feel of your website or app with Surface Duo and Samsung Galaxy Fold emulators -->  

<span data-ttu-id="3f195-173">在以下设备上的 Microsoft Edge 中测试你的网站或应用的外观。</span><span class="sxs-lookup"><span data-stu-id="3f195-173">Test the appearance of your website or app on the following devices in Microsoft Edge.</span></span>  

*   [<span data-ttu-id="3f195-174">Surface Duo</span><span class="sxs-lookup"><span data-stu-id="3f195-174">Surface Duo</span></span>][MicrosoftSurfaceDevicesSurfaceDuo]  
*   [<span data-ttu-id="3f195-175">Samsung Galaxy Fold</span><span class="sxs-lookup"><span data-stu-id="3f195-175">Samsung Galaxy Fold</span></span>][SamsungUsMobileGalaxyFold]  
    
<span data-ttu-id="3f195-176">启用“**试验 Web 平台功能**”以访问新的 [CSS 媒体屏幕跨越功能][DualScreenWebCssMediaSpanning]和 [getWindowSegments JavaScript API][DualScreenWebJavascriptGetwindowsegments]。</span><span class="sxs-lookup"><span data-stu-id="3f195-176">Turn on **Experimental Web Platform features** to access the new [CSS media screen-spanning feature][DualScreenWebCssMediaSpanning] and [getWindowSegments JavaScript API][DualScreenWebJavascriptGetwindowsegments].</span></span>  <span data-ttu-id="3f195-177">导航至 `edge://flags`，然后切换“**试验 Web 平台功能**”旁边的标记。</span><span class="sxs-lookup"><span data-stu-id="3f195-177">Navigate to `edge://flags` and toggle the flag next to **Experimental Web Platform features**.</span></span>  <span data-ttu-id="3f195-178">为帮助增强用于双屏幕和可折叠设备的网站或应用，请在[模拟设备][DevtoolsDeviceModeIndex]时使用以下功能。</span><span class="sxs-lookup"><span data-stu-id="3f195-178">To help enhance your website or app for the dual-screen and foldable devices, use the following features when [emulating the device][DevtoolsDeviceModeIndex].</span></span>  

*   <span data-ttu-id="3f195-179">[跨越][DevtoolsDeviceModeDualScreenFoldablesTestingFoldableDualScreenDevices]，即你的网站（或应用）跨两个屏幕显示。</span><span class="sxs-lookup"><span data-stu-id="3f195-179">[Spanning][DevtoolsDeviceModeDualScreenFoldablesTestingFoldableDualScreenDevices], which is when your website \(or app\) appears across both screens.</span></span>  
*   <span data-ttu-id="3f195-180">[呈现接缝][DualScreenIntroductionHowToWorkWithSeam]，即两个屏幕之间的空间。</span><span class="sxs-lookup"><span data-stu-id="3f195-180">[Rendering the seam][DualScreenIntroductionHowToWorkWithSeam], which is the space between the two screens.</span></span>  
    
<span data-ttu-id="3f195-181">若要在 Chromium 开源项目中查看此功能的历史记录，请导航至问题 [1054281][CR1054281]。</span><span class="sxs-lookup"><span data-stu-id="3f195-181">To review the history of this feature in the Chromium open-source project, navigate to Issue [1054281][CR1054281].</span></span>  

:::image type="complex" source="../../media/2021/01/emulate-surface-device-surface-duo.msft.png" alt-text="模拟双屏幕" lightbox="../../media/2021/01/emulate-surface-device-surface-duo.msft.png":::
   <span data-ttu-id="3f195-183">模拟双屏幕</span><span class="sxs-lookup"><span data-stu-id="3f195-183">Emulate dual-screen</span></span>  
:::image-end:::  

## <a name="microsoft-edge-developer-tools-for-visual-studio-code-version-112"></a><span data-ttu-id="3f195-184">Microsoft Edge Developer Tools for Visual Studio Code 1.1.2 版</span><span class="sxs-lookup"><span data-stu-id="3f195-184">Microsoft Edge Developer Tools for Visual Studio Code version 1.1.2</span></span>  

<span data-ttu-id="3f195-185">适用于 Microsoft Visual Studio Code 的 [Microsoft Edge Developer Tools for Visual Studio Code][VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools] 扩展版本 1.1.2 自上一个版本以来有以下更改。</span><span class="sxs-lookup"><span data-stu-id="3f195-185">The [Microsoft Edge Developer Tools for Visual Studio Code][VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools] extension version 1.1.2 for Microsoft Visual Studio Code has the following changes since the previous release.</span></span>  <span data-ttu-id="3f195-186">Microsoft Visual Studio Code 会自动更新扩展。</span><span class="sxs-lookup"><span data-stu-id="3f195-186">Microsoft Visual Studio Code updates extensions automatically.</span></span>  <span data-ttu-id="3f195-187">若要手动更新到版本 1.1.2，请导航至“[手动更新扩展][VisualstudioCodeDocsEditorExtensionGalleryUpdateExtensionManually]”。</span><span class="sxs-lookup"><span data-stu-id="3f195-187">To manually update to version 1.1.2, navigate to [Update an extension manually][VisualstudioCodeDocsEditorExtensionGalleryUpdateExtensionManually].</span></span>  

*   <span data-ttu-id="3f195-188">为目标列表上的每个项目添加了“**关闭实例**”按钮 ([#248][GithubMicrosoftVscodeEdgeDevtoolsPull248])</span><span class="sxs-lookup"><span data-stu-id="3f195-188">Added a **Close instance** button to each item on the target list \([#248][GithubMicrosoftVscodeEdgeDevtoolsPull248]\)</span></span>  
*   <span data-ttu-id="3f195-189">将 [Microsoft Edge DevTools][DevtoolsMain] 版本从 84.0.522.63 升级到 [85.0.564.40][DevtoolsWhatsNew85] ([#235][GithubMicrosoftVscodeEdgeDevtoolsPull235])</span><span class="sxs-lookup"><span data-stu-id="3f195-189">Bumped [Microsoft Edge DevTools][DevtoolsMain] version from 84.0.522.63 to [85.0.564.40][DevtoolsWhatsNew85] \([#235][GithubMicrosoftVscodeEdgeDevtoolsPull235]\)</span></span>  
*   <span data-ttu-id="3f195-190">将 [Microsoft Edge 调试程序][VisualstudioMarketplaceMsjsdiagDebuggerMicrosoftEdge]作为依赖项包括在内 ([#233][GithubMicrosoftVscodeEdgeDevtoolsPull233])</span><span class="sxs-lookup"><span data-stu-id="3f195-190">Included [Debugger for Microsoft Edge][VisualstudioMarketplaceMsjsdiagDebuggerMicrosoftEdge] as a dependency  \([#233][GithubMicrosoftVscodeEdgeDevtoolsPull233]\)</span></span>  
*   <span data-ttu-id="3f195-191">已实施设置选项以更改扩展主题 ([#229][GithubMicrosoftVscodeEdgeDevtoolsPull229])</span><span class="sxs-lookup"><span data-stu-id="3f195-191">Implemented settings option to change extension themes \([#229][GithubMicrosoftVscodeEdgeDevtoolsPull229]\)</span></span>  
    
<span data-ttu-id="3f195-192">你可以在 [vscode-edge-devtools GitHub repo][GithubMicrosoftVscodeEdgeDevtools] 上提交问题并参与提升扩展。</span><span class="sxs-lookup"><span data-stu-id="3f195-192">You may file issues and contribute to the extension on the [vscode-edge-devtools GitHub repo][GithubMicrosoftVscodeEdgeDevtools].</span></span>  

## <a name="announcements-from-the-chromium-project"></a><span data-ttu-id="3f195-193">来自 Chromium 项目的公告</span><span class="sxs-lookup"><span data-stu-id="3f195-193">Announcements from the Chromium project</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/chromium-whats-new-note.md)]  

### <a name="capture-node-screenshot-beyond-viewport"></a><span data-ttu-id="3f195-194">捕获视区以外的节点屏幕截图</span><span class="sxs-lookup"><span data-stu-id="3f195-194">Capture node screenshot beyond viewport</span></span>  

<span data-ttu-id="3f195-195">在 Microsoft Edge 版本 89 中，节点屏幕截图更为准确，即使节点中的内容在视区中不可见，也能捕获完整节点。</span><span class="sxs-lookup"><span data-stu-id="3f195-195">In Microsoft Edge version 89, node screenshots are more accurate, capturing the full node even if content from the node is not visible in the viewport.</span></span>  <span data-ttu-id="3f195-196">在“**元素**”工具中，将鼠标悬停在某个元素上，打开上下文菜单（右键单击），然后选择“**捕获节点屏幕**”。</span><span class="sxs-lookup"><span data-stu-id="3f195-196">In the **Elements** tool, hover  on an element, open the contextual menu \(right-click\), and choose **Capture node screenshot**.</span></span>  <span data-ttu-id="3f195-197">若要在 Chromium 开源项目中查看此功能的历史记录，请导航至问题 [1003629][CR1003629]。</span><span class="sxs-lookup"><span data-stu-id="3f195-197">To review the history of this feature in the Chromium open-source project, navigate to Issue [1003629][CR1003629].</span></span>  

:::image type="complex" source="../../media/2021/01/capture-node-screenshot.msft.png" alt-text="“元素”工具中的上下文菜单上突出显示“捕获节点屏幕截图”" lightbox="../../media/2021/01/capture-node-screenshot.msft.png":::
   <span data-ttu-id="3f195-199">“**元素**”工具中的上下文菜单上突出显示“**捕获节点屏幕截图**”</span><span class="sxs-lookup"><span data-stu-id="3f195-199">**Capture node screenshot** highlighted on the context menu in the **Elements** tool</span></span>  
:::image-end:::  

### <a name="elements-tool-updates"></a><span data-ttu-id="3f195-200">“元素”工具更新</span><span class="sxs-lookup"><span data-stu-id="3f195-200">Elements tool updates</span></span>  

#### <a name="support-forcing-the-target-css-state"></a><span data-ttu-id="3f195-201">支持强制 :target CSS 状态</span><span class="sxs-lookup"><span data-stu-id="3f195-201">Support forcing the :target CSS state</span></span>  

<span data-ttu-id="3f195-202">现在可使用 DevTools 强制 [:target][MdnDocsWebCssTarget] CSS 伪类。</span><span class="sxs-lookup"><span data-stu-id="3f195-202">You may now use DevTools to force the [:target][MdnDocsWebCssTarget] CSS pseudo-class.</span></span>  <span data-ttu-id="3f195-203">当唯一元素（目标元素）具有与 URL 片段匹配的 `id` 时，将触发 `:target` 伪类。</span><span class="sxs-lookup"><span data-stu-id="3f195-203">The `:target` pseudo-class is triggered when a unique element \(the target element\) has an `id` that matches a fragment of the URL.</span></span>  <span data-ttu-id="3f195-204">例如，`http://www.example.com/index.html#section1` URL 在带有 `id="section1"` 的 HTML 元素上触发 `:target` 伪类。</span><span class="sxs-lookup"><span data-stu-id="3f195-204">For example, the `http://www.example.com/index.html#section1` URL triggers the `:target` pseudo-class on an HTML element with `id="section1"`.</span></span>  <span data-ttu-id="3f195-205">若要尝试突出显示了第 1 部分的演示，请导航至“[CSS :target 演示][GithubMicrosoftedgeDevtoolssamplesWhatsNew89TargetCssDemoHtmlSection1]”。</span><span class="sxs-lookup"><span data-stu-id="3f195-205">To try a demo with section 1 highlighted, navigate to [CSS :target demo][GithubMicrosoftedgeDevtoolssamplesWhatsNew89TargetCssDemoHtmlSection1].</span></span>  <span data-ttu-id="3f195-206">若要在 Chromium 开源项目中查看此功能的历史记录，请导航至问题 [1156628][CR1156628]。</span><span class="sxs-lookup"><span data-stu-id="3f195-206">To review the history of this feature in the Chromium open-source project, navigate to Issue [1156628][CR1156628].</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-styles-none-forced.msft.png" alt-text="突出显示网页，未强制 CSS" lightbox="../../media/2021/01/elements-styles-none-forced.msft.png":::
         <span data-ttu-id="3f195-208">突出显示网页，未强制 CSS</span><span class="sxs-lookup"><span data-stu-id="3f195-208">Webpage highlighted with no forced CSS</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-styles-target-forced.msft.png" alt-text="已强制 :target CSS 且突出显示网页" lightbox="../../media/2021/01/elements-styles-target-forced.msft.png":::
         `:target` <span data-ttu-id="3f195-210">已强制 CSS 且突出显示网页</span><span class="sxs-lookup"><span data-stu-id="3f195-210">CSS forced and webpage highlighted</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::

#### <a name="use-duplicate-elements-to-copy-elements"></a><span data-ttu-id="3f195-211">使用“复制元素”复制元素</span><span class="sxs-lookup"><span data-stu-id="3f195-211">Use Duplicate elements to copy elements</span></span>  

<span data-ttu-id="3f195-212">使用新的“**复制元素**”快捷方式克隆元素。</span><span class="sxs-lookup"><span data-stu-id="3f195-212">Use the new **Duplicate element** shortcut to clone an element.</span></span>  <span data-ttu-id="3f195-213">在“**元素**”工具中，将鼠标悬停在某个元素上，打开上下文菜单（右键单击），然后选择“**复制元素**”。</span><span class="sxs-lookup"><span data-stu-id="3f195-213">In the **Elements** tool, hover on an element, open the contextual menu \(right-click\), choose **Duplicate element**.</span></span>  <span data-ttu-id="3f195-214">将在选定元素下创建一个新元素。</span><span class="sxs-lookup"><span data-stu-id="3f195-214">A new element is created under the selected element.</span></span>  <span data-ttu-id="3f195-215">若要使用键盘快捷方式复制元素，请选择“`Shift`+`Alt`+`Down Arrow`”(Windows/Linux) 或“`Shift`+`Option`+`Down Arrow`”(macOS)。</span><span class="sxs-lookup"><span data-stu-id="3f195-215">To duplicate the element with a keyboard shortcut, select `Shift`+`Alt`+`Down Arrow` \(Windows/Linux\) or `Shift`+`Option`+`Down Arrow` \(macOS\).</span></span>  <span data-ttu-id="3f195-216">若要在 Chromium 开源项目中查看此功能的历史记录，请导航至问题 [1150797][CR1150797]。</span><span class="sxs-lookup"><span data-stu-id="3f195-216">To review the history of this feature in the Chromium open-source project, navigate to Issue [1150797][CR1150797].</span></span>  

:::image type="complex" source="../../media/2021/01/elements-duplicate-element.msft.png" alt-text="“复制元素”在“元素”工具中某个元素的上下文菜单中突出显示" lightbox="../../media/2021/01/elements-duplicate-element.msft.png":::
   <span data-ttu-id="3f195-218">“**复制元素**”在“**元素**”工具中某个元素的上下文菜单中突出显示</span><span class="sxs-lookup"><span data-stu-id="3f195-218">The **Duplicate element** is highlighted in the context menu on an element in the **Elements** tool</span></span>  
:::image-end:::  

#### <a name="color-pickers-for-custom-css-properties"></a><span data-ttu-id="3f195-219">自定义 CSS 属性的颜色选取器</span><span class="sxs-lookup"><span data-stu-id="3f195-219">Color pickers for custom CSS properties</span></span>  

<span data-ttu-id="3f195-220">“**样式**”窗格现在显示自定义 CSS 属性的颜色选取器。</span><span class="sxs-lookup"><span data-stu-id="3f195-220">The **Styles** pane now displays color pickers for custom CSS properties.</span></span>  <span data-ttu-id="3f195-221">若要循环浏览颜色值的 RGBA、HSLA 和 Hex 格式，请按住 `Shift` 并选择颜色选取器。</span><span class="sxs-lookup"><span data-stu-id="3f195-221">To cycle through the RGBA, HSLA, and Hex formats of the color value, hold `Shift` and choose the color picker.</span></span>  <span data-ttu-id="3f195-222">若要在 Chromium 开源项目中查看此功能的历史记录，请导航至问题 [1147016][CR1147016]。</span><span class="sxs-lookup"><span data-stu-id="3f195-222">To review the history of this feature in the Chromium open-source project, navigate to Issue [1147016][CR1147016].</span></span>  

:::image type="complex" source="../../media/2021/01/elements-styles-change-color-format.msft.png" alt-text="自定义 CSS 属性的颜色选取器" lightbox="../../media/2021/01/elements-styles-change-color-format.msft.png":::
   <span data-ttu-id="3f195-224">自定义 CSS 属性的颜色选取器</span><span class="sxs-lookup"><span data-stu-id="3f195-224">Color pickers for custom CSS properties</span></span>  
:::image-end:::  

#### <a name="copy-css-classes-and-properties"></a><span data-ttu-id="3f195-225">复制 CSS 类和属性</span><span class="sxs-lookup"><span data-stu-id="3f195-225">Copy CSS classes and properties</span></span>  

<span data-ttu-id="3f195-226">现在，你可以通过上下文菜单中的几个新选项更快地复制 CSS 属性。</span><span class="sxs-lookup"><span data-stu-id="3f195-226">You may now copy CSS properties quicker with a few new options in the contextual menu.</span></span>  <span data-ttu-id="3f195-227">在“**元素**”工具中，选择一个元素。</span><span class="sxs-lookup"><span data-stu-id="3f195-227">In the **Elements** tool, choose an element.</span></span>  <span data-ttu-id="3f195-228">若要复制值，请在“**样式**”窗格中，将鼠标悬停在 CSS 类或 CSS 属性上，打开上下文菜单（右键单击），然后选择复制选项。</span><span class="sxs-lookup"><span data-stu-id="3f195-228">To copy the value, in the **Styles** pane, hover on a CSS class or a CSS property, open a contextual menu \(right-click\), and choose the copy option.</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="3f195-229">CSS 类的复制选项。</span><span class="sxs-lookup"><span data-stu-id="3f195-229">Copy options for a CSS class.</span></span>  
      
      | <span data-ttu-id="3f195-230">选项</span><span class="sxs-lookup"><span data-stu-id="3f195-230">Option</span></span> | <span data-ttu-id="3f195-231">详细信息</span><span class="sxs-lookup"><span data-stu-id="3f195-231">Details</span></span> |  
      |:--- |:--- |  
      | **<span data-ttu-id="3f195-232">复制选择器</span><span class="sxs-lookup"><span data-stu-id="3f195-232">Copy selector</span></span>** | <span data-ttu-id="3f195-233">复制当前选择器名称。</span><span class="sxs-lookup"><span data-stu-id="3f195-233">Copy the current selector name.</span></span> |  
      | **<span data-ttu-id="3f195-234">复制规则</span><span class="sxs-lookup"><span data-stu-id="3f195-234">Copy rule</span></span>** | <span data-ttu-id="3f195-235">复制当前选择器的规则。</span><span class="sxs-lookup"><span data-stu-id="3f195-235">Copy the rule of the current selector.</span></span> |  
      | **<span data-ttu-id="3f195-236">复制所有声明</span><span class="sxs-lookup"><span data-stu-id="3f195-236">Copy all declarations</span></span>** | <span data-ttu-id="3f195-237">复制当前规则下的所有声明，包括无效和有前缀的属性。</span><span class="sxs-lookup"><span data-stu-id="3f195-237">Copy all declarations under the current rule, including non-valid and prefixed properties.</span></span> |  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="3f195-238">CSS 属性的复制选项。</span><span class="sxs-lookup"><span data-stu-id="3f195-238">Copy options for a CSS property.</span></span>  
      
      | <span data-ttu-id="3f195-239">选项</span><span class="sxs-lookup"><span data-stu-id="3f195-239">Option</span></span> | <span data-ttu-id="3f195-240">详细信息</span><span class="sxs-lookup"><span data-stu-id="3f195-240">Details</span></span> |      
      |:--- |:--- |  
      | **<span data-ttu-id="3f195-241">复制声明</span><span class="sxs-lookup"><span data-stu-id="3f195-241">Copy declaration</span></span>** | <span data-ttu-id="3f195-242">复制当前行的声明。</span><span class="sxs-lookup"><span data-stu-id="3f195-242">Copy the declaration of the current line.</span></span> |  
      | **<span data-ttu-id="3f195-243">复制属性</span><span class="sxs-lookup"><span data-stu-id="3f195-243">Copy property</span></span>** | <span data-ttu-id="3f195-244">复制当前行的属性。</span><span class="sxs-lookup"><span data-stu-id="3f195-244">Copy the property of the current line.</span></span> |  
      | **<span data-ttu-id="3f195-245">复制值</span><span class="sxs-lookup"><span data-stu-id="3f195-245">Copy value</span></span>** | <span data-ttu-id="3f195-246">复制当前行的值。</span><span class="sxs-lookup"><span data-stu-id="3f195-246">Copy the value of the current line.</span></span> |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/copy-css-class.msft.png" alt-text="上下文菜单中 CSS 类的复制选项" lightbox="../../media/2021/01/copy-css-class.msft.png":::
         <span data-ttu-id="3f195-248">上下文菜单中 CSS 类的复制选项</span><span class="sxs-lookup"><span data-stu-id="3f195-248">Copy options for a CSS class in the contextual menu</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/copy-css-property-cropped.msft.png" alt-text="上下文菜单中 CSS 属性的复制选项" lightbox="../../media/2021/01/copy-css-property.msft.png":::
         <span data-ttu-id="3f195-250">上下文菜单中 CSS 属性的复制选项</span><span class="sxs-lookup"><span data-stu-id="3f195-250">Copy options for a CSS property in the contextual menu</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="3f195-251">若要在 Chromium 开源项目中查看此功能的历史记录，请导航至问题 [1152391][CR1152391]。</span><span class="sxs-lookup"><span data-stu-id="3f195-251">To review the history of this feature in the Chromium open-source project, navigate to Issue [1152391][CR1152391].</span></span>  

### <a name="cookies-updates"></a><span data-ttu-id="3f195-252">Cookie 更新</span><span class="sxs-lookup"><span data-stu-id="3f195-252">Cookies updates</span></span>  

#### <a name="new-option-to-display-url-decoded-cookies"></a><span data-ttu-id="3f195-253">用于显示 URL 解码的 Cookie 的新选项</span><span class="sxs-lookup"><span data-stu-id="3f195-253">New option to display URL-decoded cookies</span></span>  

<span data-ttu-id="3f195-254">现在，你可以选择在“**Cookie**”窗格中显示 URL 解码的 Cookie 值。</span><span class="sxs-lookup"><span data-stu-id="3f195-254">You may now opt to display the URL-decoded cookies value in the **Cookies** pane.</span></span>  <span data-ttu-id="3f195-255">若要显示解码的 Cookie，请导航至“**应用程序**” > “**Cookie**”窗格，选择列表中的任何 Cookie，然后选中“**显示解码的 URL**”旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="3f195-255">To display the decoded cookie, navigate to **Application** > **Cookies** pane, choose any cookie on the list, and choose the checkbox next to **Show URL decoded**.</span></span>  <span data-ttu-id="3f195-256">若要在 Chromium 开源项目中查看此功能的历史记录，请导航至问题 [997625][CR997625]。</span><span class="sxs-lookup"><span data-stu-id="3f195-256">To review the history of this feature in the Chromium open-source project, navigate to Issue [997625][CR997625].</span></span>  

:::image type="complex" source="../../media/2021/01/application-cookies-show-url-decoded.msft.png" alt-text="用于显示 URL 解码的 Cookie 的选项" lightbox="../../media/2021/01/application-cookies-show-url-decoded.msft.png":::
   <span data-ttu-id="3f195-258">用于显示 URL 解码的 Cookie 的选项</span><span class="sxs-lookup"><span data-stu-id="3f195-258">Option to display URL decoded cookies</span></span>  
:::image-end:::  

#### <a name="filter-and-clear-visible-cookies"></a><span data-ttu-id="3f195-259">筛选和清除可见的 Cookie</span><span class="sxs-lookup"><span data-stu-id="3f195-259">Filter and clear visible cookies</span></span>  

<span data-ttu-id="3f195-260">在 Microsoft Edge 版本 88 或更早版本中，“**应用程序**”工具只提供了一种使用“**清除所有 Cookie**”按钮清除所有 Cookie 的方法。</span><span class="sxs-lookup"><span data-stu-id="3f195-260">In Microsoft Edge version 88 or earlier, the **Application** tool only provided a way to clear all cookies with the **Clear all cookies** button.</span></span>  <span data-ttu-id="3f195-261">在 Microsoft Edge 版本 89 中，现在可以选择“**清除筛选的 Cookie**”以便仅删除筛选的 Cookie。</span><span class="sxs-lookup"><span data-stu-id="3f195-261">In Microsoft Edge version 89, you may now choose **Clear filtered cookies** to delete only the filtered cookies.</span></span>  <span data-ttu-id="3f195-262">若要筛选 Cookie，请导航至“**应用程序**” > “**Cookie**”，然后在“**筛选器**”文本框中键入。</span><span class="sxs-lookup"><span data-stu-id="3f195-262">To filter cookies, navigate to **Application** > **Cookies**, and type in the **Filter** textbox.</span></span>  <span data-ttu-id="3f195-263">若要删除显示的 Cookie，请选择“**清除筛选的 Cookie**”按钮。</span><span class="sxs-lookup"><span data-stu-id="3f195-263">To delete the displayed cookies, choose the **Clear filtered cookies** button.</span></span>  <span data-ttu-id="3f195-264">若要显示所有其他 Cookie，请清除筛选器文本。</span><span class="sxs-lookup"><span data-stu-id="3f195-264">To display all other cookies, clear the filter text.</span></span>  <span data-ttu-id="3f195-265">若要在 Chromium 开源项目中查看此功能的历史记录，请导航至问题 [978059][CR978059]。</span><span class="sxs-lookup"><span data-stu-id="3f195-265">To review the history of this feature in the Chromium open-source project, navigate to Issue [978059][CR978059].</span></span>  

:::image type="complex" source="../../media/2021/01/application-cookies-clear-filtered-cookies.msft.png" alt-text="仅清除可见的 Cookie" lightbox="../../media/2021/01/application-cookies-clear-filtered-cookies.msft.png":::
   <span data-ttu-id="3f195-267">仅清除可见的 Cookie</span><span class="sxs-lookup"><span data-stu-id="3f195-267">Clear only visible cookies</span></span>  
:::image-end:::  

#### <a name="new-option-to-clear-third-party-cookies-in-the-storage-pane"></a><span data-ttu-id="3f195-268">“存储”窗格中用于清除第三方 Cookie 的新选项</span><span class="sxs-lookup"><span data-stu-id="3f195-268">New option to clear third-party cookies in the Storage pane</span></span>  

<span data-ttu-id="3f195-269">默认情况下，DevTools 现在仅清除第一方 Cookie。</span><span class="sxs-lookup"><span data-stu-id="3f195-269">DevTools now clear only first-party cookies by default.</span></span>  <span data-ttu-id="3f195-270">若要仅清除网站数据和第一方 Cookie，请导航至“**应用程序**” > “**存储**”，然后选择“**清除网站数据**”。</span><span class="sxs-lookup"><span data-stu-id="3f195-270">To clear website data and first-party cookies only, navigate to **Application** > **Storage**, and then choose **Clear site data**.</span></span>  

<span data-ttu-id="3f195-271">若要清除网站数据和所有 Cookie，请导航至“**应用程序**” > “**存储**”。</span><span class="sxs-lookup"><span data-stu-id="3f195-271">To clear website data and all cookies, navigate to **Application** > **Storage**.</span></span>  <span data-ttu-id="3f195-272">选择“**包括第三方 Cookie**”旁边的复选框，然后选择“**清除网站数据**”。</span><span class="sxs-lookup"><span data-stu-id="3f195-272">Choose the checkbox next to **including third-party cookies**, and then choose **Clear site data**.</span></span>  

<span data-ttu-id="3f195-273">若要在 Chromium 开源项目中查看此功能的历史记录，请导航至问题 [1012337][CR1012337]。</span><span class="sxs-lookup"><span data-stu-id="3f195-273">To review the history of this feature in the Chromium open-source project, navigate to Issue [1012337][CR1012337].</span></span>  

:::image type="complex" source="../../media/2021/01/application-storage-clear-site-data-including-third-party-cookies.msft.png" alt-text="用于清除第三方 Cookie 的选项" lightbox="../../media/2021/01/application-storage-clear-site-data-including-third-party-cookies.msft.png":::
   <span data-ttu-id="3f195-275">用于清除第三方 Cookie 的选项</span><span class="sxs-lookup"><span data-stu-id="3f195-275">Option to clear third-party cookies</span></span>  
:::image-end:::  

### <a name="network-tool-updates"></a><span data-ttu-id="3f195-276">网络工具更新</span><span class="sxs-lookup"><span data-stu-id="3f195-276">Network tool updates</span></span>  

#### <a name="persist-record-network-log-setting"></a><span data-ttu-id="3f195-277">保留“记录网络日志”设置</span><span class="sxs-lookup"><span data-stu-id="3f195-277">Persist Record network log setting</span></span>  

<span data-ttu-id="3f195-278">在 Microsoft Edge 版本 88 或更早版本中，当网页刷新时，DevTools 将重置“**记录网络日志**”设置。</span><span class="sxs-lookup"><span data-stu-id="3f195-278">In Microsoft Edge version 88 or earlier, DevTools reset the **Record network log** setting when a webpage refreshes.</span></span>  <span data-ttu-id="3f195-279">在 Microsoft Edge 版本 89 中，DevTools 现在将保留“**记录网络日志**”设置。</span><span class="sxs-lookup"><span data-stu-id="3f195-279">In Microsoft Edge version 89, DevTools now persist the **Record network log** setting.</span></span>  <span data-ttu-id="3f195-280">若要在 Chromium 开源项目中查看此功能的历史记录，请导航至问题 [1122580][CR1122580]。</span><span class="sxs-lookup"><span data-stu-id="3f195-280">To review the history of this feature in the Chromium open-source project, navigate to Issue [1122580][CR1122580].</span></span>  

:::image type="complex" source="../../media/2021/01/network-log.msft.png" alt-text="记录网络日志" lightbox="../../media/2021/01/network-log.msft.png":::
   <span data-ttu-id="3f195-282">记录网络日志</span><span class="sxs-lookup"><span data-stu-id="3f195-282">Record network log</span></span>  
:::image-end:::  

#### <a name="online-option-is-now-no-throttling-option"></a><span data-ttu-id="3f195-283">“联机”选项现在是“无限制”选项</span><span class="sxs-lookup"><span data-stu-id="3f195-283">Online option is now No throttling option</span></span>  

<span data-ttu-id="3f195-284">网络模拟选项“**联机**”现已重命名为“**无限制**”。</span><span class="sxs-lookup"><span data-stu-id="3f195-284">The network emulation option **Online** is now renamed to **No Throttling**.</span></span>  <span data-ttu-id="3f195-285">若要在 Chromium 开源项目中查看此功能的历史记录，请导航至问题 [1028078][CR1028078]。</span><span class="sxs-lookup"><span data-stu-id="3f195-285">To review the history of this feature in the Chromium open-source project, navigate to Issue [1028078][CR1028078].</span></span>  

:::image type="complex" source="../../media/2021/01/network-no-throttling.msft.png" alt-text="“无限制”选项" lightbox="../../media/2021/01/network-no-throttling.msft.png":::
   <span data-ttu-id="3f195-287">“**无限制**”选项</span><span class="sxs-lookup"><span data-stu-id="3f195-287">**No throttling** option</span></span>  
:::image-end:::  

### <a name="new-copy-options-in-the-console-tool-sources-tool-and-styles-pane"></a><span data-ttu-id="3f195-288">“控制台”工具、“源”工具和“样式”窗格中新的复制选项</span><span class="sxs-lookup"><span data-stu-id="3f195-288">New copy options in the Console tool, Sources tool, and Styles pane</span></span>

#### <a name="copy-object-in-the-console-and-sources-tool"></a><span data-ttu-id="3f195-289">在“控制台”和“源”工具中复制对象</span><span class="sxs-lookup"><span data-stu-id="3f195-289">Copy object in the Console and Sources tool</span></span>  

<span data-ttu-id="3f195-290">现在，你可以在“**控制台**”和“**源**”工具中复制对象值。</span><span class="sxs-lookup"><span data-stu-id="3f195-290">You may now copy object values in the **Console** and **Sources** tools.</span></span>  <span data-ttu-id="3f195-291">复制对象值的能力在处理大型对象时很有用。</span><span class="sxs-lookup"><span data-stu-id="3f195-291">The ability to copy object values is useful when working with large objects.</span></span>  <span data-ttu-id="3f195-292">若要在 Chromium 开源项目中查看此功能的历史记录，请导航至问题 [1148353][CR1148353] 和 [1149859][CR1149859]。</span><span class="sxs-lookup"><span data-stu-id="3f195-292">To review the history of this feature in the Chromium open-source project, navigate to Issues [1148353][CR1148353] and [1149859][CR1149859].</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="3f195-293">在“**控制台**”工具中，将鼠标悬停在某个对象上，打开上下文菜单（右键单击），然后选择“**复制对象**”。</span><span class="sxs-lookup"><span data-stu-id="3f195-293">In the **Console** tool, hover on an object, open the contextual menu \(right-click\), and then choose **Copy object**.</span></span>  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="3f195-294">在“**源**”工具中，在断点处，将鼠标悬停在某个对象上，在“**对象**”弹出窗口中突出显示某个对象，打开上下文菜单（右键单击），然后选择“**复制对象**”。</span><span class="sxs-lookup"><span data-stu-id="3f195-294">In the **Sources** tool, on a breakpoint, hover on an object, in the **Object** popup window, highlight an object, open the contextual menu \(right-click\), and then choose **Copy object**.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/console-copy-object.msft.png" alt-text="在“控制台”中复制对象" lightbox="../../media/2021/01/console-copy-object.msft.png":::
         <span data-ttu-id="3f195-296">在“**控制台**”中复制对象</span><span class="sxs-lookup"><span data-stu-id="3f195-296">Copy object in the **Console**</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/sources-breakpoint-object-copy-object.msft.png" alt-text="在“源”中复制对象" lightbox="../../media/2021/01/sources-breakpoint-object-copy-object.msft.png":::
         <span data-ttu-id="3f195-298">在“**源**”中复制对象</span><span class="sxs-lookup"><span data-stu-id="3f195-298">Copy object in **Sources**</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

#### <a name="copy-file-name-in-the-sources-tool-and-styles-pane"></a><span data-ttu-id="3f195-299">在“源”工具和“样式”窗格中复制文件名</span><span class="sxs-lookup"><span data-stu-id="3f195-299">Copy file name in the Sources tool and Styles pane</span></span>  

<span data-ttu-id="3f195-300">现在，你可以使用上下文菜单复制文件名。</span><span class="sxs-lookup"><span data-stu-id="3f195-300">You may now copy a file name using the contextual menu.</span></span>  <span data-ttu-id="3f195-301">若要在 Chromium 开源项目中查看此功能的历史记录，请导航至问题 [1155120][CR1155120]。</span><span class="sxs-lookup"><span data-stu-id="3f195-301">To review the history of this feature in the Chromium open-source project, navigate to Issues [1155120][CR1155120].</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="3f195-302">在“**源**”工具中，将鼠标悬停在某个文件名上，打开上下文菜单（右键单击），然后选择“**复制文件名**”。</span><span class="sxs-lookup"><span data-stu-id="3f195-302">In the **Sources** tool, hover on a file name, open the contextual menu \(right-click\), and then choose **Copy file name**.</span></span>  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="3f195-303">在“**元素**”工具 >“**样式**”窗格中，将鼠标悬停在某个文件名上，打开上下文菜单（右键单击），然后选择“**复制文件名**”。</span><span class="sxs-lookup"><span data-stu-id="3f195-303">In the **Elements** tool > **Styles** pane, hover on a file name, open the contextual menu \(right-click\), and then choose **Copy file name**.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/sources-copy-file-name.msft.png" alt-text="在“源”中复制文件名" lightbox="../../media/2021/01/sources-copy-file-name.msft.png":::
         <span data-ttu-id="3f195-305">在“**源**”中复制文件名</span><span class="sxs-lookup"><span data-stu-id="3f195-305">Copy file name in **Sources**</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-styles-copy-file-name.msft.png" alt-text="在“样式”窗格中复制文件名" lightbox="../../media/2021/01/elements-styles-copy-file-name.msft.png":::
         <span data-ttu-id="3f195-307">在“**样式**”窗格中复制文件名</span><span class="sxs-lookup"><span data-stu-id="3f195-307">Copy file name in **Styles** pane</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

### <a name="updates-to-frame-details"></a><span data-ttu-id="3f195-308">帧详细信息更新</span><span class="sxs-lookup"><span data-stu-id="3f195-308">Updates to Frame details</span></span>  

#### <a name="service-workers-information-in-frame-details"></a><span data-ttu-id="3f195-309">帧详细信息中的服务工作进程信息</span><span class="sxs-lookup"><span data-stu-id="3f195-309">Service Workers information in Frame details</span></span>  

<span data-ttu-id="3f195-310">DevTools 现在在父帧下列出一个专用的服务工作进程。</span><span class="sxs-lookup"><span data-stu-id="3f195-310">DevTools now lists a dedicated service worker under the parent frame.</span></span>  <span data-ttu-id="3f195-311">下图显示了服务工作进程的详细信息。</span><span class="sxs-lookup"><span data-stu-id="3f195-311">In the following figure, service worker details are displayed.</span></span>  <span data-ttu-id="3f195-312">若要显示服务工作进程详细信息，请导航至“**应用程序**” > “**帧**” > `top` > “**服务工作进程**”，然后选择一个服务工作进程。</span><span class="sxs-lookup"><span data-stu-id="3f195-312">To display the service worker details, navigate to **Application** > **Frames** > `top` > **Service Workers** and then choose a service worker.</span></span>  <span data-ttu-id="3f195-313">若要在 Chromium 开源项目中查看此功能的历史记录，请导航至问题 [1122507][CR1122507]。</span><span class="sxs-lookup"><span data-stu-id="3f195-313">To review the history of this feature in the Chromium open-source project, navigate to Issue [1122507][CR1122507].</span></span>  

:::image type="complex" source="../../media/2021/01/application-frames-service-workers-details.msft.png" alt-text="帧详细信息中的服务工作进程信息" lightbox="../../media/2021/01/application-frames-service-workers-details.msft.png":::
   <span data-ttu-id="3f195-315">**帧**详细信息中的**服务工作进程**信息</span><span class="sxs-lookup"><span data-stu-id="3f195-315">**Service Workers** information in the **Frames** details</span></span>  
:::image-end:::  

#### <a name="measure-memory-information-in-frame-details"></a><span data-ttu-id="3f195-316">帧详细信息中的“测量内存”信息</span><span class="sxs-lookup"><span data-stu-id="3f195-316">Measure Memory information in Frame details</span></span>  

<span data-ttu-id="3f195-317">`performance.measureMemory()` API 状态现在显示在“**API 可用性**”部分下。</span><span class="sxs-lookup"><span data-stu-id="3f195-317">The `performance.measureMemory()` API status is now displayed under the **API availability** section.</span></span>  <span data-ttu-id="3f195-318">新的 `performance.measureMemory()` API 估计整个网页的内存使用情况。</span><span class="sxs-lookup"><span data-stu-id="3f195-318">The new `performance.measureMemory()` API estimates the memory usage of the entire webpage.</span></span>  <span data-ttu-id="3f195-319">若要在 Chromium 开源项目中查看此功能的历史记录，请导航至问题 [1139899][CR1139899]。</span><span class="sxs-lookup"><span data-stu-id="3f195-319">To review the history of this feature in the Chromium open-source project, navigate to Issue [1139899][CR1139899].</span></span>  

:::image type="complex" source="../../media/2021/01/application-frames-measure-memory.msft.png" alt-text="测量内存" lightbox="../../media/2021/01/application-frames-measure-memory.msft.png":::
   <span data-ttu-id="3f195-321">测量内存</span><span class="sxs-lookup"><span data-stu-id="3f195-321">Measure Memory</span></span>  
:::image-end:::  

### <a name="dropped-frames-in-the-performance-tool"></a><span data-ttu-id="3f195-322">“性能”工具中丢弃的帧</span><span class="sxs-lookup"><span data-stu-id="3f195-322">Dropped frames in the Performance tool</span></span>  

<span data-ttu-id="3f195-323">当你[在“性能”工具中分析负载性能][DevtoolsEvaluatePerformanceReferenceRecordLoadPerformance]时，“**帧**”部分现在会将丢弃的帧标记为红色。</span><span class="sxs-lookup"><span data-stu-id="3f195-323">When you [analyze load performance in the Performance tool][DevtoolsEvaluatePerformanceReferenceRecordLoadPerformance], the **Frames** section now marks dropped frames as red.</span></span>  <span data-ttu-id="3f195-324">若要显示帧速率，请将鼠标悬停在丢弃的帧上。</span><span class="sxs-lookup"><span data-stu-id="3f195-324">To display the frame rate, hover on a dropped frame.</span></span>  <span data-ttu-id="3f195-325">若要在 Chromium 开源项目中查看此功能的历史记录，请导航至问题 [1075865][CR1075865]。</span><span class="sxs-lookup"><span data-stu-id="3f195-325">To review the history of this feature in the Chromium open-source project, navigate to Issue [1075865][CR1075865].</span></span>  

:::image type="complex" source="../../media/2021/01/performance-frames-dropped-frames-red.msft.png" alt-text="丢弃的帧" lightbox="../../media/2021/01/performance-frames-dropped-frames-red.msft.png":::
   <span data-ttu-id="3f195-327">丢弃的帧</span><span class="sxs-lookup"><span data-stu-id="3f195-327">Dropped frames</span></span>  
:::image-end:::  

#### <a name="new-color-contrast-calculation---advanced-perceptual-contrast-algorithm-apca"></a><span data-ttu-id="3f195-328">新的颜色对比度计算 - 高级感知对比度算法 (APCA)</span><span class="sxs-lookup"><span data-stu-id="3f195-328">New color contrast calculation - Advanced Perceptual Contrast Algorithm (APCA)</span></span>  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

<span data-ttu-id="3f195-329">[高级感知对比度算法 (APCA)][GithubW3cSilverGuidelinesMethodsMethodFontCharacteristicContrastHtml] 取代了[颜色选取器][DevtoolsAccessibilityReferenceViewContrastRatioTextElementColorPicker]中的 [AA][W3cWaiWcag21QuickrefContrastMinimum]/[AAA][W3cWaiWcag21QuickrefContrastEnhanced] 准则对比率。</span><span class="sxs-lookup"><span data-stu-id="3f195-329">The [Advanced Perceptual Contrast Algorithm (APCA)][GithubW3cSilverGuidelinesMethodsMethodFontCharacteristicContrastHtml] replaces the [AA][W3cWaiWcag21QuickrefContrastMinimum]/[AAA][W3cWaiWcag21QuickrefContrastEnhanced] guidelines contrast ratio in the [Color Picker][DevtoolsAccessibilityReferenceViewContrastRatioTextElementColorPicker].</span></span>  <span data-ttu-id="3f195-330">APCA 是一种计算对比度的新方法。</span><span class="sxs-lookup"><span data-stu-id="3f195-330">APCA is a new way to compute contrast.</span></span>  <span data-ttu-id="3f195-331">它基于对颜色感知的新式研究。</span><span class="sxs-lookup"><span data-stu-id="3f195-331">It is based on modern research on color perception.</span></span>  <span data-ttu-id="3f195-332">与 AA/AAA 准则相比，APCA 更依赖于上下文。</span><span class="sxs-lookup"><span data-stu-id="3f195-332">Compared to AA/AAA guidelines, APCA is more context-dependent.</span></span>  <span data-ttu-id="3f195-333">对比度是根据文本、颜色和上下文的以下空间属性计算的。</span><span class="sxs-lookup"><span data-stu-id="3f195-333">The contrast is calculated based on the following spatial properties of the text, color, and context.</span></span>  

*   <span data-ttu-id="3f195-334">文本的空间属性，包括字体粗细和大小。</span><span class="sxs-lookup"><span data-stu-id="3f195-334">Spatial properties of text that include font weight and size.</span></span>  
*   <span data-ttu-id="3f195-335">颜色的空间属性，包括文本和背景之间的感知对比度。</span><span class="sxs-lookup"><span data-stu-id="3f195-335">Spatial properties of color that include perceived contrast between text and background.</span></span>  
*   <span data-ttu-id="3f195-336">上下文的空间属性，包括环境光线、周围环境和预期用途。</span><span class="sxs-lookup"><span data-stu-id="3f195-336">Spatial properties of context that include ambient light, surroundings, and intended purpose.</span></span>  
    
<span data-ttu-id="3f195-337">若要启用此试验，请导航至“[设置][DevtoolsCustomizeIndexSettings]” > “**试验**”，然后选中“**启用新的高级感知对比度算法 (APCA) 以替换以前的对比率和 AA/AAA 准则**”旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="3f195-337">To turn on this experiment, navigate to [Settings][DevtoolsCustomizeIndexSettings] > **Experiments**  and choose the checkbox next to **Enable new Advanced Perceptual Contrast Algorithm (APCA) replacing previous contrast ratio and AA/AAA guidelines**.</span></span>  <span data-ttu-id="3f195-338">若要在 Chromium 开源项目中查看此功能的历史记录，请导航至问题 [1121900][CR1121900]。</span><span class="sxs-lookup"><span data-stu-id="3f195-338">To review the history of this feature in the Chromium open-source project, navigate to Issue [1121900][CR1121900].</span></span>  

:::image type="complex" source="../../media/2021/01/advanced-perceptual-contrast-algorithm.msft.png" alt-text="颜色选取器中的 APCA" lightbox="../../media/2021/01/advanced-perceptual-contrast-algorithm.msft.png":::
   <span data-ttu-id="3f195-340">颜色选取器中的 APCA</span><span class="sxs-lookup"><span data-stu-id="3f195-340">APCA in the Color Picker</span></span>  
:::image-end:::  

## <a name="download-the-microsoft-edge-preview-channels"></a><span data-ttu-id="3f195-341">下载 Microsoft Edge 预览频道</span><span class="sxs-lookup"><span data-stu-id="3f195-341">Download the Microsoft Edge preview channels</span></span>  

<span data-ttu-id="3f195-342">如果你使用的是 Windows、Linux 或 macOS，请考虑使用 [ Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels]作为默认开发浏览器。</span><span class="sxs-lookup"><span data-stu-id="3f195-342">If you are on Windows, Linux, or macOS, consider using the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] as your default development browser.</span></span>  <span data-ttu-id="3f195-343">预览频道使你能够访问最新的 DevTools 功能。</span><span class="sxs-lookup"><span data-stu-id="3f195-343">The preview channels give you access to the latest DevTools features.</span></span>  

## <a name="getting-in-touch-with-microsoft-edge-devtools-team"></a><span data-ttu-id="3f195-344">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="3f195-344">Getting in touch with Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]

<!-- links -->  

[DevtoolsWhatsNew85]: ../../2020/06/devtools.md "DevTools 中的新增功能 (Microsoft Edge 85) | Microsoft Docs"  

[DevtoolsAccessibilityReferenceViewContrastRatioTextElementColorPicker]: /microsoft-edge/devtools-guide-chromium/accessibility/reference#view-the-contrast-ratio-of-a-text-element-in-the-color-picker "查看颜色选取器中的文本元素的对比率 - 辅助功能参考 | Microsoft Docs"  
[DevtoolsCssReferenceChangeCss]: /microsoft-edge/devtools-guide-chromium/css/reference#change-css "更改 CSS - CSS 参考 |Microsoft Docs"  
[DevtoolsCustomizeIndexSettings]: /microsoft-edge/devtools-guide-chromium/customize/index#settings "设置 - 自定义 Microsoft Edge DevTools | Microsoft Docs"  
[DevtoolsCustomizeShortcuts]: microsoft-edge/devtools-guide-chromium/customize/shortcuts "自定义 Microsoft Edge DevTools 中的键盘快捷方式 | Microsoft Docs"  
[DevtoolsDeviceModeDualScreenFoldablesTestingFoldableDualScreenDevices]: /microsoft-edge/devtools-guide-chromium/device-mode/dual-screen-and-foldables#testing-on-foldable-and-dual-screen-devices "在可折叠和双屏幕设备上进行测试 - 在 Microsoft Edge DevTools 中模拟双屏幕和可折叠设备 | Microsoft Docs"  
[DevtoolsDeviceModeIndex]: /microsoft-edge/devtools-guide-chromium/device-mode/index "在 Microsoft Edge DevTools 中模拟移动设备 | Microsoft Docs"  
[DevtoolsDeviceModeIndexSimulateMobileViewport]: /microsoft-edge/devtools-guide-chromium/device-mode/index#simulate-a-mobile-viewport "模拟移动视区 - 在 Microsoft Edge DevTools 中模拟移动设备 | Microsoft Docs"  
[DevtoolsEvaluatePerformanceReferenceRecordLoadPerformance]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference#record-load-performance "记录负载性能 - 性能分析参考 | Microsoft Docs"  
[DevtoolsInspectStylesEditFonts]: /microsoft-edge/devtools-guide-chromium/inspect-styles/edit-fonts "在 DevTools 的“样式”窗格中编辑 CSS 字体样式和设置 | Microsoft Docs"  
[DevtoolsMain]: /microsoft-edge/devtools-guide-chromium/index "Microsoft Edge (Chromium) 开发人员工具概述 | Microsoft Docs"  

[DualScreenIntroductionHowToWorkWithSeam]: /dual-screen/introduction#how-to-work-with-the-seam "如何处理接缝 - 双屏幕设备简介| Microsoft Docs"  
[DualScreenWebCssMediaSpanning]: /dual-screen/web/css-media-spanning "用于双屏幕检测的 CSS 媒体屏幕跨越功能 | Microsoft Docs"  
[DualScreenWebJavascriptGetwindowsegments]: /dual-screen/web/javascript-getwindowsegments "适用于双屏幕设备的 getWindowSegments JavaScript AP | Microsoft Docs"  

[GithubMicrosoftedgeDevtoolssamplesWhatsNew89TargetCssDemoHtmlSection1]: https://microsoftedge.github.io/DevToolsSamples/whats-new/89/target-css-demo.html#section-1 "第 1 部分 - DevTools 中“新增功能”的 CSS :target 演示 (Microsoft Edge 89) | GitHub"  
[GithubMicrosoftVscodeEdgeDevtools]: https://github.com/microsoft/vscode-edge-devtools "microsoft/vscode-edge-devtools | GitHub"  
[GithubMicrosoftVscodeEdgeDevtoolsPull229]: https://github.com/microsoft/vscode-edge-devtools/pull/229 "拉取 229：在设置中实现下拉列表以更改主题 | GitHub"  
[GithubMicrosoftVscodeEdgeDevtoolsPull233]: https://github.com/microsoft/vscode-edge-devtools/pull/233 "拉取 233：包括 Microsoft Edge 调试程序作为依赖项 | GitHub"  
[GithubMicrosoftVscodeEdgeDevtoolsPull235]: https://github.com/microsoft/vscode-edge-devtools/pull/235 "拉取 235：将 Edge DevTools 版本升级到 85.0.564.40 |GitHub"  
[GithubMicrosoftVscodeEdgeDevtoolsPull248]: https://github.com/microsoft/vscode-edge-devtools/pull/248 "拉取 248：将单个关闭按钮添加到实例面板 | GitHub"  
[GithubW3cSilverGuidelinesMethodsMethodFontCharacteristicContrastHtml]: https://w3c.github.io/silver/guidelines/methods/Method-font-characteristic-contrast.html "选择字体特征和背景色以提供足够的对比度以方便阅读 | W3C"  
[GithubW3cWebappsecTrustedTypesDistSpec]: https://w3c.github.io/webappsec-trusted-types/dist/spec  "受信任的类型 | W3C"  

[MicrosoftSurfaceDevicesSurfaceDuo]: https://www.microsoft.com/surface/devices/surface-duo "新的 Surface Duo | Microsoft"  

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download "Microsoft Edge 预览频道"  

[VisualstudioCodeDocsEditorExtensionGalleryUpdateExtensionManually]: https://code.visualstudio.com/docs/editor/extension-gallery#_update-an-extension-manually "手动更新扩展 - Extension Marketplace | Visual Studio Code"  

[VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools]: https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools "Microsoft Edge Tools for Visual Studio Code | Visual Studio Marketplace"  
[VisualstudioMarketplaceMsjsdiagDebuggerMicrosoftEdge]: https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge " Microsoft Edge 调试程序 | Visual Studio Marketplace"  

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium bug"  
[CR978059]: https://crbug.com/978059 "问题 978059：筛选 Cookie 后删除它们，删除所有 Cookie，而不仅仅是筛选的 Cookie | Chromium bug"  
[CR997625]: https://crbug.com/997625 "问题 997625：新功能请求 | 需要用于查看 Cookie 中的 URL 解码值的选项 | Chromium bug"  
[CR1003629]: https://crbug.com/1003629 "问题 1003629：捕获节点不再对折叠下方的节点进行屏幕截图。| Chromium bug"  
[CR1012337]: https://crbug.com/1012337 "问题 1012337：清除网站数据会破坏非 Google 网站上 Google 会话 | Chromium bug"  
[CR1028078]: https://crbug.com/1028078 "问题 1028078：在列表中将“联机”和“脱机”并排放置 | Chromium bug"  
[CR1054281]: https://crbug.com/1054281 "问题 1054281：功能请求：DevTools 应模拟可折叠和双屏幕设备 | Chromium bug"  
[CR1075865]: https://crbug.com/1075865 "问题 1075865：在 devtools 日程表中显示丢弃的帧 | Chromium bug"  
[CR1093229]: https://crbug.com/1093229 "问题 1093229：DevTools：提供专用的字样编辑器 UI | Chromium bug"  
[CR1121900]: https://crbug.com/1121900 "问题 1121900：DevTools：根据新规范更新对比度计算逻辑 | Chromium bug"  
[CR1122507]: https://crbug.com/1122507 "问题 1122507：帧树视图中的 Surface 工作线程信息 | Chromium bug"  
[CR1122580]: https://crbug.com/1122580 "问题 1122580：重载时无法禁用网络记录 | Chromium bug"  
[CR1136394]: https://crbug.com/1136394 "问题 1136394：弹性框工具 |Chromium bug"  
[CR1139899]: https://crbug.com/1139899 "问题 1139899：在帧详细信息视图中报告封闭的 API 的可用性 | Chromium bug"  
[CR1139949]: https://crbug.com/1139949 "问题 1139949：弹性框覆盖 | Chromium bug"  
[CR1147016]: https://crbug.com/1147016 "问题 1147016：颜色选取器未显示在 var() 函数中。| Chromium bug"  
[CR1148353]: https://crbug.com/1148353 "问题 1148353：功能请求：从 devtools 控制台复制对象 | Chromium bug"  
[CR1149859]: https://crbug.com/1149859 "问题 1149859：[功能请求][控制台] 将复制对象添加到剪贴板项目以及上下文菜单 | Chromium bug"  
[CR1150797]: https://crbug.com/1150797 "问题 1150797：在“元素”面板中添加“复制元素”上下文菜单 | Chromium bug"  
[CR1152391]: https://crbug.com/1152391 "问题 1152391：支持“样式”面板中的“复制 CSS”上下文菜单 | Chromium bug"  
[CR1155120]: https://crbug.com/1155120 "问题 1155120：[FR]支持复制文件名和行号 | Chromium bug"  
[CR1156628]: https://crbug.com/1156628 "问题 1156628：DevTools：在强制元素状态功能中添加对 :target 的支持 | Chromium bug"  
[CR1157329]: https://crbug.com/1157329 "问题 1157329：辅助功能 - 讲述人：讲述人不会在“样式”选项卡中公布适用于代码的建议的计数和位置 | Chromium bug"  

[MdnDocsWebCssTarget]: https://developer.mozilla.org/docs/web/css/:target ":target | MDN"  

[SamsungUsMobileGalaxyFold]: https://www.samsung.com/us/mobile/galaxy-fold "Galaxy Fold | Samsung US"  

[W3cWaiWcag21QuickrefContrastEnhanced]: https://www.w3.org/WAI/WCAG21/quickref#contrast-enhanced "对比度（增强）- 如何满足 WCAG 的要求（快速参考）|W3C"  
[W3cWaiWcag21QuickrefContrastMinimum]: https://www.w3.org/WAI/WCAG21/quickref#contrast-minimum "对比度（最低）- 如何满足 WCAG 的要求（快速参考）|W3C"  

> [!NOTE]
> <span data-ttu-id="3f195-399">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="3f195-399">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="3f195-400">原始页面位于 [此处](https://developer.chrome.com/blog/new-in-devtools-89)，并由 [Jecelyn Yeen][JecelynYeen] \（开发人员支持者，Chrome DevTools\）制作。</span><span class="sxs-lookup"><span data-stu-id="3f195-400">The original page is found [here](https://developer.chrome.com/blog/new-in-devtools-89) and is authored by [Jecelyn Yeen][JecelynYeen] \(Developer advocate, Chrome DevTools\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="3f195-402">此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="3f195-402">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen

[SpanningPlaceholder]: link-t-b-d "跨区占位符"  
