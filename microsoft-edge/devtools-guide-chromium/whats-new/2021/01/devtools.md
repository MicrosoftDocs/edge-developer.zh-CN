---
description: 现在欢迎使用新增功能工具、样式窗格中的可视化字体编辑器、CSS Flexbox 调试工具等。
title: 'Microsoft Edge 89 (DevTools 中的新增) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: 2722da0093b3ba6521b5190e61bb208e02a2041e
ms.sourcegitcommit: e29cd1c393fc1f433dba8c3d8f260b425ade63a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/13/2021
ms.locfileid: "11408337"
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
# <a name="whats-new-in-devtools-microsoft-edge-89"></a><span data-ttu-id="68abc-104">Microsoft Edge 89 开发人员工具中的 (新增) </span><span class="sxs-lookup"><span data-stu-id="68abc-104">What's New In DevTools (Microsoft Edge 89)</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/edge-whats-new-note.md)]  

## <a name="whats-new-is-now-welcome"></a><span data-ttu-id="68abc-105">新增功能现已欢迎使用</span><span class="sxs-lookup"><span data-stu-id="68abc-105">What's New is now Welcome</span></span>  

<!--  Title: What's New is now Welcome  -->  
<!--  Subtitle: The What's New tool now has a new appearance and a new name:  Welcome -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

<span data-ttu-id="68abc-106">Microsoft **Edge** DevTools 中的新增功能工具现在具有新外观和新名称：  **欢迎**使用。</span><span class="sxs-lookup"><span data-stu-id="68abc-106">The **What's New** tool in the Microsoft Edge DevTools now has a new appearance and a new name:  **Welcome**.</span></span>  <span data-ttu-id="68abc-107">欢迎 **工具** 仍显示最新的 DevTools 新闻和更新。</span><span class="sxs-lookup"><span data-stu-id="68abc-107">The **Welcome** tool still displays the latest DevTools news and updates.</span></span>  <span data-ttu-id="68abc-108">它现在还包括指向 Microsoft Edge DevTools 文档的链接、提交反馈的方式等。</span><span class="sxs-lookup"><span data-stu-id="68abc-108">It now also includes links to Microsoft Edge DevTools documentation, ways to submit feedback, and more.</span></span>  <span data-ttu-id="68abc-109">若要在 **Microsoft** Edge 每次更新后显示欢迎工具，请选中标题下每个更新后打开选项卡 **旁边的** 复选框。</span><span class="sxs-lookup"><span data-stu-id="68abc-109">To display the **Welcome** tool after each update to Microsoft Edge, choose the checkbox next to **Open tab after each update** under the title.</span></span>  <span data-ttu-id="68abc-110">若要关闭**欢迎工具**，请选择选项卡标题右边的**X。**</span><span class="sxs-lookup"><span data-stu-id="68abc-110">To close the **Welcome** tool, choose the **X** on the right-side of the tab title.</span></span>  <span data-ttu-id="68abc-111">如果你更喜欢原始的**新增**功能工具，请导航到设置实验[][DevtoolsCustomizeIndexSettings]并删除"  >  \*\*\*\* 启用欢迎"选项卡旁边的**复选框**。</span><span class="sxs-lookup"><span data-stu-id="68abc-111">If you prefer the original **What's New** tool, navigate to [Settings][DevtoolsCustomizeIndexSettings] > **Experiments** and remove the checkbox next to **Enable Welcome tab**.</span></span>  

:::image type="complex" source="../../media/2021/01/welcome-tool-whats-new-88.msft.png" alt-text="突出显示"欢迎"工具" lightbox="../../media/2021/01/welcome-tool-whats-new-88.msft.png":::
   <span data-ttu-id="68abc-113">突出显示 **"欢迎** "工具</span><span class="sxs-lookup"><span data-stu-id="68abc-113">The **Welcome** tool is highlighted</span></span>  
:::image-end:::  

## <a name="visual-font-editor-in-the-styles-pane"></a><span data-ttu-id="68abc-114">"样式"窗格中的可视化字体编辑器</span><span class="sxs-lookup"><span data-stu-id="68abc-114">Visual Font Editor in the Styles pane</span></span>  

<!--  Title: Visual font editor in the Styles pane  -->  
<!--  Subtitle: Visual font editor in the Styles pane -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

<span data-ttu-id="68abc-115">在 CSS 中处理字体时，请使用新的可视化 [字体编辑器][DevtoolsInspectStylesEditFonts]。</span><span class="sxs-lookup"><span data-stu-id="68abc-115">When you work with fonts in CSS, use the new visual [Font Editor][DevtoolsInspectStylesEditFonts].</span></span>  <span data-ttu-id="68abc-116">你可以定义回退字体，并使用滑块定义字体粗细、大小、行高和间距。</span><span class="sxs-lookup"><span data-stu-id="68abc-116">You may define fallback fonts, and use sliders to define font weight, size, line-height, and spacing.</span></span>  <span data-ttu-id="68abc-117">字体 **编辑器** 可帮助您完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="68abc-117">The **Font Editor** helps you complete the following actions.</span></span>  

*   <span data-ttu-id="68abc-118">在不同字体属性的单位之间切换</span><span class="sxs-lookup"><span data-stu-id="68abc-118">Switch between units for different font properties</span></span>  
*   <span data-ttu-id="68abc-119">在不同字体属性的关键字之间切换</span><span class="sxs-lookup"><span data-stu-id="68abc-119">Switch between keywords for different font properties</span></span>  
*   <span data-ttu-id="68abc-120">转换单位</span><span class="sxs-lookup"><span data-stu-id="68abc-120">Convert units</span></span>  
*   <span data-ttu-id="68abc-121">生成准确的 CSS 代码</span><span class="sxs-lookup"><span data-stu-id="68abc-121">Generate accurate CSS code</span></span>  
    
<span data-ttu-id="68abc-122">若要打开此实验，请[导航到"][DevtoolsCustomizeIndexSettings]设置实验"，然后选择"在样式窗格中启用新的  >  \*\*\*\*\*\*字体编辑器工具"旁边的复选框\*\*。</span><span class="sxs-lookup"><span data-stu-id="68abc-122">To turn on this experiment, navigate to [Settings][DevtoolsCustomizeIndexSettings] > **Experiments** and choose the checkbox next to **Enable new Font Editor tools within Styles pane**.</span></span>  <span data-ttu-id="68abc-123">有关详细信息，请导航到DevTools 的样式窗格中的编辑 [CSS 字体样式和设置][DevtoolsInspectStylesEditFonts]。</span><span class="sxs-lookup"><span data-stu-id="68abc-123">For more information, navigate to [Edit CSS font styles and settings in the Styles pane in DevTools][DevtoolsInspectStylesEditFonts].</span></span>  <span data-ttu-id="68abc-124">若要查看 Chromium 开源项目中此功能的历史记录，请导航到"问题[1093229"。][CR1093229]</span><span class="sxs-lookup"><span data-stu-id="68abc-124">To review the history of this feature in the Chromium open-source project, navigate to Issue [1093229][CR1093229].</span></span>  

:::image type="complex" source="../../media/2021/01/visual-font-editor.msft.png" alt-text="可视字体编辑器在"样式"窗格中突出显示" lightbox="../../media/2021/01/visual-font-editor.msft.png":::
   <span data-ttu-id="68abc-126">可视**字体编辑器**在"样式 **"窗格中突出显示**</span><span class="sxs-lookup"><span data-stu-id="68abc-126">The visual **Font editor** is highlighted in the **Styles** pane</span></span>  
:::image-end:::  

## <a name="css-flexbox-debugging-tools"></a><span data-ttu-id="68abc-127">CSS Flexbox 调试工具</span><span class="sxs-lookup"><span data-stu-id="68abc-127">CSS Flexbox debugging tools</span></span>  

<span data-ttu-id="68abc-128">Flexbox 调试功能正在积极开发中。</span><span class="sxs-lookup"><span data-stu-id="68abc-128">Flexbox debugging features are in active development.</span></span>  <span data-ttu-id="68abc-129">若要打开以下两项功能的实验，请导航到"设置[][DevtoolsCustomizeIndexSettings]实验"，然后选中"启用新的  >  \*\*\*\*\*\*CSS Flexbox 调试功能"旁边的复选框\*\*。</span><span class="sxs-lookup"><span data-stu-id="68abc-129">To turn on the experiment for the following two features, navigate to [Settings][DevtoolsCustomizeIndexSettings] > **Experiments** and choose the checkbox next to **Enable new CSS Flexbox debugging features**.</span></span>  <span data-ttu-id="68abc-130">若要查看 Chromium 开源项目中此功能的历史记录，请导航到"问题[1136394"][CR1136394]和["1139949"。][CR1139949]</span><span class="sxs-lookup"><span data-stu-id="68abc-130">To review the history of this feature in the Chromium open-source project, navigate to Issues [1136394][CR1136394] and [1139949][CR1139949].</span></span>  

### <a name="new-flexbox-flex-icon-helps-identify-and-display-flex-containers"></a><span data-ttu-id="68abc-131">新的 Flexbox (弹性) 图标可帮助标识和显示弹性容器</span><span class="sxs-lookup"><span data-stu-id="68abc-131">New Flexbox (flex) icon helps identify and display flex containers</span></span>  

<!--  Title: Display Flexbox containers with Flexbox (flex) icon  -->  
<!--  Subtitle: New Flexbox (flex) icon in the Elements tool help you identify Flexbox containers in your code.  When toggled, the adorner displays and hides outlines of the flex container to help you debug the layout -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

<span data-ttu-id="68abc-132">在" **元素** "工具中，新的 Flexbox (flex) 图标可帮助你在代码中标识 Flexbox 容器。</span><span class="sxs-lookup"><span data-stu-id="68abc-132">In the **Elements** tool, the new Flexbox (flex) icon helps you identify Flexbox containers in your code.</span></span>  <span data-ttu-id="68abc-133">选择 Flexbox \ (flex\) 图标可打开或关闭分级显示 Flexbox 容器的覆盖效果。</span><span class="sxs-lookup"><span data-stu-id="68abc-133">Choose the Flexbox \(flex\) icon to turn on or off the overlay effect that outlines a Flexbox container.</span></span>  <span data-ttu-id="68abc-134">You may customize the color of the overlay in the **Layout** pane， which is next to **Styles** and **Computed**.</span><span class="sxs-lookup"><span data-stu-id="68abc-134">You may customize the color of the overlay in the **Layout** pane, which is located next to **Styles** and **Computed**.</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="68abc-135">若要打开和关闭覆盖层效果，该效果会大纲显示 Flexbox 容器，请选择 Flexbox \ (`flex` \) 图标。</span><span class="sxs-lookup"><span data-stu-id="68abc-135">To turn on and off the overlay effect that outlines the Flexbox container, choose the Flexbox \(`flex`\) icon.</span></span>  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="68abc-136">You may customize the color of the overlay in the **Layout** pane next to **Styles** and **Computed**.</span><span class="sxs-lookup"><span data-stu-id="68abc-136">You may customize the color of the overlay in the **Layout** pane next to **Styles** and **Computed**.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-flex-container.msft.png" alt-text="Flexbox (弹性) 图标和网页突出显示" lightbox="../../media/2021/01/elements-flex-container.msft.png":::
         <span data-ttu-id="68abc-138">突出显示 **的 Flexbox** \ (`flex` \) 图标和网页</span><span class="sxs-lookup"><span data-stu-id="68abc-138">The **Flexbox** \(`flex`\) icon and webpage highlighted</span></span> :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-layout-flex-container.msft.png" alt-text=""布局"窗格中突出显示的 Flexbox 覆盖" lightbox="../../media/2021/01/elements-layout-flex-container.msft.png":::
         <span data-ttu-id="68abc-140">"**布局"窗格中**突出显示的 Flexbox**覆盖**</span><span class="sxs-lookup"><span data-stu-id="68abc-140">The **Flexbox overlays** highlighted in the **Layout** pane</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

### <a name="display-alignment-icons-and-gridlines-when-flexbox-layouts-change-using-css-properties"></a><span data-ttu-id="68abc-141">当 Flexbox 布局使用 CSS 属性更改时显示对齐图标和网格线</span><span class="sxs-lookup"><span data-stu-id="68abc-141">Display alignment icons and gridlines when Flexbox layouts change using CSS properties</span></span>  

<!--  Title: Display alignment icons and gridlines for changes to Flexbox layouts from CSS properties  -->  
<!--  Subtitle:  CSS autocomplete in the Styles tool now displays icons next to Flexbox properties to help you review the effect a property has on your Flexbox layout -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

<span data-ttu-id="68abc-142">编辑 Flexbox 布局的 CSS 时，"样式"窗格中的\*\*\*\* CSS 自动完成现在会在相关的 Flexbox 属性旁边显示有用的图标。</span><span class="sxs-lookup"><span data-stu-id="68abc-142">When you edit CSS for your Flexbox layout, CSS autocompletes in the **Styles** pane now displays helpful icons next to relevant Flexbox properties.</span></span>  <span data-ttu-id="68abc-143">若要试用此新功能，请打开 **"元素** "工具并选择弹性容器。</span><span class="sxs-lookup"><span data-stu-id="68abc-143">To try this new feature, open the **Elements** tool and select a flex container.</span></span>  <span data-ttu-id="68abc-144">然后在"样式"窗格中添加或更改该容器 **上的** 属性。</span><span class="sxs-lookup"><span data-stu-id="68abc-144">Then add or change a property on that container in the **Styles** pane.</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="68abc-145">自动完成菜单现在显示指示对齐属性（如 和 ）的效果的 `align-content` 图标 `align-items` 。</span><span class="sxs-lookup"><span data-stu-id="68abc-145">The autocomplete menu now displays icons that indicate the effect of alignment properties such as `align-content` and `align-items`.</span></span>  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="68abc-146">此外，DevTools 现在还显示了一条指导线，可帮助你更好地查看 `align-items` CSS 属性。</span><span class="sxs-lookup"><span data-stu-id="68abc-146">Additionally, DevTools now displays a guiding line to help you better review the `align-items` CSS property.</span></span>  <span data-ttu-id="68abc-147">`gap`CSS 属性也受支持。</span><span class="sxs-lookup"><span data-stu-id="68abc-147">The `gap` CSS property is supported as well.</span></span>  <span data-ttu-id="68abc-148">在下图中，CSS 属性设置为 ，并显示每个间隙的 `gap` `gap: 12px;` 间隔模式。</span><span class="sxs-lookup"><span data-stu-id="68abc-148">In the following figure, the `gap` CSS property is set to `gap: 12px;` and the hatching pattern for each gap is displayed.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-flex-container-align.msft.png" alt-text=""自动完成"菜单针对以 align-" lightbox="../../media/2021/01/elements-flex-container-align.msft.png":::
         <span data-ttu-id="68abc-150">"自动完成"菜单针对以</span><span class="sxs-lookup"><span data-stu-id="68abc-150">Autocomplete menu highlighted for CSS properties that start with</span></span> `align-`  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-flex-container-align-items-center-gap-12px.msft.png" alt-text="CSS 属性和网页中的弹性框间隙突出显示" lightbox="../../media/2021/01/elements-flex-container-align-items-center-gap-12px.msft.png":::
         <span data-ttu-id="68abc-152">CSS 属性和网页中的 Flexbox `gap` 突出显示</span><span class="sxs-lookup"><span data-stu-id="68abc-152">Flexbox `gap` in CSS properties and webpage highlighted</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="add-tools-quickly-with-new-more-tools-button"></a><span data-ttu-id="68abc-153">使用新的"更多工具"按钮快速添加工具</span><span class="sxs-lookup"><span data-stu-id="68abc-153">Add tools quickly with new More Tools button</span></span>  

<!--  Title: Add tools quickly with new More Tools button  -->  
<!--  Subtitle: A convenient way to open new tools in Microsoft Edge DevTools -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

<span data-ttu-id="68abc-154">你现在有一种在 Microsoft Edge DevTools 中打开更多工具的新方式。</span><span class="sxs-lookup"><span data-stu-id="68abc-154">You now have a new way to open more tools in the Microsoft Edge DevTools.</span></span>  <span data-ttu-id="68abc-155">打开此实验后，"更多工具\*\*\*\*"图标将显示为主 () 右侧 `+` 显示的加号。</span><span class="sxs-lookup"><span data-stu-id="68abc-155">After you turn on this experiment, the **More Tools** icon displays as a plus sign (`+`) to the right of the main panel.</span></span>  <span data-ttu-id="68abc-156">若要显示要添加到主面板的其他工具的列表，请选择"更多 **工具"\ (** `+` \) 图标。</span><span class="sxs-lookup"><span data-stu-id="68abc-156">To display a list of other tools to add to the main panel, choose the **More Tools** \(`+`\) icon.</span></span>  <span data-ttu-id="68abc-157">若要打开此实验，请[导航到设置][DevtoolsCustomizeIndexSettings]实验，然后选择启用 + 按钮选项卡菜单旁边的复选框以  >  \*\*\*\*\*\*打开更多工具\*\*。</span><span class="sxs-lookup"><span data-stu-id="68abc-157">To turn on this experiment, navigate to [Settings][DevtoolsCustomizeIndexSettings] > **Experiments**, and then choose the checkbox next to **Enable + button tab menus to open more tools**.</span></span>  

:::image type="complex" source="../../media/2021/01/more-tools.msft.png" alt-text="DevTools 中突出显示的更多工具" lightbox="../../media/2021/01/more-tools.msft.png":::
   <span data-ttu-id="68abc-159">**DevTools** 中突出显示的更多工具</span><span class="sxs-lookup"><span data-stu-id="68abc-159">**More Tools** highlighted in DevTools</span></span>  
:::image-end:::  

## <a name="assistive-technologies-now-announce-position-and-count-of-css-suggestions"></a><span data-ttu-id="68abc-160">辅助技术现在宣布 CSS 建议的位置和计数</span><span class="sxs-lookup"><span data-stu-id="68abc-160">Assistive technologies now announce position and count of CSS suggestions</span></span>  

<!--  Title: Assistive technologies now announce position and count of CSS suggestions  -->  
<!--  Subtitle: CSS suggestions are now easier to navigate using screen readers -->  

<span data-ttu-id="68abc-161">编辑 CSS 时，会获得一组功能。</span><span class="sxs-lookup"><span data-stu-id="68abc-161">When you edit CSS, you get a dropdown of features.</span></span>  <span data-ttu-id="68abc-162">此功能对辅助技术的用户不可用，因为它在 Microsoft Edge 版本 89 中公布。</span><span class="sxs-lookup"><span data-stu-id="68abc-162">This feature was not available to users of assistive technologies, since it is announced in Microsoft Edge version 89.</span></span>  <span data-ttu-id="68abc-163">辅助技术的用户现在可以在"样式"窗格中导航 CSS**建议。**</span><span class="sxs-lookup"><span data-stu-id="68abc-163">A user of assistive technologies may now navigate CSS suggestions in the **Styles** pane.</span></span>  <span data-ttu-id="68abc-164">在 Microsoft Edge 版本 88 及更早版本中，当用户在"样式"窗格中编辑 CSS 时浏览建议列表时，宣布使用辅助 `Suggestion` 技术。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="68abc-164">In Microsoft Edge version 88 and earlier, assistive technology announced `Suggestion` as a user navigated through the list of suggestions when editing CSS in the **Styles** pane.</span></span>  <span data-ttu-id="68abc-165">在 Microsoft Edge 版本 89 中，辅助技术的用户现在会听到当前建议的位置和计数。</span><span class="sxs-lookup"><span data-stu-id="68abc-165">In Microsoft Edge version 89, a user of assistive technology now hears the position and count of the current suggestion.</span></span>  <span data-ttu-id="68abc-166">每个建议在用户浏览建议列表时进行公布，如建议 3/5。</span><span class="sxs-lookup"><span data-stu-id="68abc-166">Each suggestion is announced as the user navigates through the list of suggestions, such as Suggestion 3 of 5.</span></span>  <span data-ttu-id="68abc-167">若要了解有关在 DevTools 中编写 CSS 有关详细信息，请导航到"[更改 CSS"。][DevtoolsCssReferenceChangeCss]</span><span class="sxs-lookup"><span data-stu-id="68abc-167">To learn more about writing CSS in the DevTools, navigate to [Change CSS][DevtoolsCssReferenceChangeCss].</span></span>  <span data-ttu-id="68abc-168">若要查看 Chromium 开源项目中此功能的历史记录，请导航到"问题[1157329"。][CR1157329]</span><span class="sxs-lookup"><span data-stu-id="68abc-168">To review the history of this feature in the Chromium open-source project, navigate to Issue [1157329][CR1157329].</span></span>  

<span data-ttu-id="68abc-169">若要查看在打开此实验时显示和朗读多个建议的视频，请导航到 ["Voiceover"，](https://youtu.be/9TcUpleEwwA) 宣布 YouTube 上的开发工具选项。</span><span class="sxs-lookup"><span data-stu-id="68abc-169">To view a video that displays and reads aloud several suggestions with this experiment turned on, navigate to [Voiceover announcing devtools options](https://youtu.be/9TcUpleEwwA) on YouTube.</span></span>  

:::image type="complex" source="../../media/2021/01/announce-css-suggestion.msft.png" alt-text=""样式"窗格中突出显示的建议" lightbox="../../media/2021/01/announce-css-suggestion.msft.png":::
   <span data-ttu-id="68abc-171">" `suggestion` 样式"窗格中 **突出显示** 的列表</span><span class="sxs-lookup"><span data-stu-id="68abc-171">The `suggestion` list highlighted in the **Styles** pane</span></span>  
:::image-end:::  

## <a name="emulate-surface-duo-and-samsung-galaxy-fold"></a><span data-ttu-id="68abc-172">模拟 Surface Duo 和 Samsung 为 Fold</span><span class="sxs-lookup"><span data-stu-id="68abc-172">Emulate Surface Duo and Samsung Galaxy Fold</span></span>  

<!--  Title: Emulate new dual-screen and foldable devices  -->  
<!--  Subtitle: Test the appearance and feel of your website or app with Surface Duo and Samsung Galaxy Fold emulators -->  

<span data-ttu-id="68abc-173">在 Microsoft Edge 中的以下设备上测试网站或应用的外观。</span><span class="sxs-lookup"><span data-stu-id="68abc-173">Test the appearance of your website or app on the following devices in Microsoft Edge.</span></span>  

*   [<span data-ttu-id="68abc-174">Surface Duo</span><span class="sxs-lookup"><span data-stu-id="68abc-174">Surface Duo</span></span>][MicrosoftSurfaceDevicesSurfaceDuo]  
*   [<span data-ttu-id="68abc-175">三星百合</span><span class="sxs-lookup"><span data-stu-id="68abc-175">Samsung Galaxy Fold</span></span>][SamsungUsMobileGalaxyFold]  
    
<span data-ttu-id="68abc-176">打开实验**性 Web 平台功能**以访问新的[CSS 媒体屏幕][DualScreenWebCssMediaSpanning]跨越功能和[getWindowSegments JavaScript API。][DualScreenWebJavascriptGetwindowsegments]</span><span class="sxs-lookup"><span data-stu-id="68abc-176">Turn on **Experimental Web Platform features** to access the new [CSS media screen-spanning feature][DualScreenWebCssMediaSpanning] and [getWindowSegments JavaScript API][DualScreenWebJavascriptGetwindowsegments].</span></span>  <span data-ttu-id="68abc-177">导航到 `edge://flags` "实验性 Web 平台功能"旁边的 **标志并切换该标志**。</span><span class="sxs-lookup"><span data-stu-id="68abc-177">Navigate to `edge://flags` and toggle the flag next to **Experimental Web Platform features**.</span></span>  <span data-ttu-id="68abc-178">为了帮助增强用于双屏和可折叠设备的网站或应用，在模拟设备时使用以下 [功能][DevtoolsDeviceModeIndex]。</span><span class="sxs-lookup"><span data-stu-id="68abc-178">To help enhance your website or app for the dual-screen and foldable devices, use the following features when [emulating the device][DevtoolsDeviceModeIndex].</span></span>  

*   <span data-ttu-id="68abc-179">[跨区][DevtoolsDeviceModeDualScreenFoldablesTestingFoldableDualScreenDevices]，即你的网站 \ (或 app\) 显示在两个屏幕上时。</span><span class="sxs-lookup"><span data-stu-id="68abc-179">[Spanning][DevtoolsDeviceModeDualScreenFoldablesTestingFoldableDualScreenDevices], which is when your website \(or app\) appears across both screens.</span></span>  
*   <span data-ttu-id="68abc-180">[呈现接层][DualScreenIntroductionHowToWorkWithSeam]，这是两个屏幕之间的空间。</span><span class="sxs-lookup"><span data-stu-id="68abc-180">[Rendering the seam][DualScreenIntroductionHowToWorkWithSeam], which is the space between the two screens.</span></span>  
    
<span data-ttu-id="68abc-181">若要查看 Chromium 开放源代码项目中此功能的历史记录，请导航到"问题[1054281"。][CR1054281]</span><span class="sxs-lookup"><span data-stu-id="68abc-181">To review the history of this feature in the Chromium open-source project, navigate to Issue [1054281][CR1054281].</span></span>  

:::image type="complex" source="../../media/2021/01/emulate-surface-device-surface-duo.msft.png" alt-text="模拟双屏" lightbox="../../media/2021/01/emulate-surface-device-surface-duo.msft.png":::
   <span data-ttu-id="68abc-183">模拟双屏</span><span class="sxs-lookup"><span data-stu-id="68abc-183">Emulate dual-screen</span></span>  
:::image-end:::  

## <a name="microsoft-edge-developer-tools-for-visual-studio-code-version-112"></a><span data-ttu-id="68abc-184">Microsoft Edge 开发人员工具Visual Studio 1.1.2 版</span><span class="sxs-lookup"><span data-stu-id="68abc-184">Microsoft Edge Developer Tools for Visual Studio Code version 1.1.2</span></span>  

<span data-ttu-id="68abc-185">Microsoft [Edge 开发人员工具 for Visual Studio Code][VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools] extension version 1.1.2 for Microsoft Visual Studio Code 自上一版本起具有以下更改。</span><span class="sxs-lookup"><span data-stu-id="68abc-185">The [Microsoft Edge Developer Tools for Visual Studio Code][VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools] extension version 1.1.2 for Microsoft Visual Studio Code has the following changes since the previous release.</span></span>  <span data-ttu-id="68abc-186">Microsoft Visual Studio 代码将自动更新扩展。</span><span class="sxs-lookup"><span data-stu-id="68abc-186">Microsoft Visual Studio Code updates extensions automatically.</span></span>  <span data-ttu-id="68abc-187">若要手动更新到版本 1.1.2，请导航到"[手动更新扩展"。][VisualstudioCodeDocsEditorExtensionGalleryUpdateExtensionManually]</span><span class="sxs-lookup"><span data-stu-id="68abc-187">To manually update to version 1.1.2, navigate to [Update an extension manually][VisualstudioCodeDocsEditorExtensionGalleryUpdateExtensionManually].</span></span>  

*   <span data-ttu-id="68abc-188">向目标 **列表** \ (\#248 \) 上的每个项目添加了" [关闭][GithubMicrosoftVscodeEdgeDevtoolsPull248]实例"按钮</span><span class="sxs-lookup"><span data-stu-id="68abc-188">Added a **Close instance** button to each item on the target list \([#248][GithubMicrosoftVscodeEdgeDevtoolsPull248]\)</span></span>  
*   <span data-ttu-id="68abc-189">从[][DevtoolsMain]84.0.522.63 到[85.0.564.40][DevtoolsWhatsNew85] \ (#235 [\) ][GithubMicrosoftVscodeEdgeDevtoolsPull235]</span><span class="sxs-lookup"><span data-stu-id="68abc-189">Bumped [Microsoft Edge DevTools][DevtoolsMain] version from 84.0.522.63 to [85.0.564.40][DevtoolsWhatsNew85] \([#235][GithubMicrosoftVscodeEdgeDevtoolsPull235]\)</span></span>  
*   <span data-ttu-id="68abc-190">将[Microsoft Edge 调试][VisualstudioMarketplaceMsjsdiagDebuggerMicrosoftEdge]器作为依赖项 \ (#233 \) [][GithubMicrosoftVscodeEdgeDevtoolsPull233]</span><span class="sxs-lookup"><span data-stu-id="68abc-190">Included [Debugger for Microsoft Edge][VisualstudioMarketplaceMsjsdiagDebuggerMicrosoftEdge] as a dependency  \([#233][GithubMicrosoftVscodeEdgeDevtoolsPull233]\)</span></span>  
*   <span data-ttu-id="68abc-191">用于更改扩展主题 \ (#229 [\) ][GithubMicrosoftVscodeEdgeDevtoolsPull229]</span><span class="sxs-lookup"><span data-stu-id="68abc-191">Implemented settings option to change extension themes \([#229][GithubMicrosoftVscodeEdgeDevtoolsPull229]\)</span></span>  
    
<span data-ttu-id="68abc-192">你可以提交问题并参与 [vscode-edge-devtools GitHub 存储库上的扩展][GithubMicrosoftVscodeEdgeDevtools]。</span><span class="sxs-lookup"><span data-stu-id="68abc-192">You may file issues and contribute to the extension on the [vscode-edge-devtools GitHub repo][GithubMicrosoftVscodeEdgeDevtools].</span></span>  

## <a name="announcements-from-the-chromium-project"></a><span data-ttu-id="68abc-193">来自 Chromium 项目的公告</span><span class="sxs-lookup"><span data-stu-id="68abc-193">Announcements from the Chromium project</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/chromium-whats-new-note.md)]  

### <a name="capture-node-screenshot-beyond-viewport"></a><span data-ttu-id="68abc-194">捕获视图之外的节点屏幕截图</span><span class="sxs-lookup"><span data-stu-id="68abc-194">Capture node screenshot beyond viewport</span></span>  

<span data-ttu-id="68abc-195">在 Microsoft Edge 版本 89 中，节点屏幕截图更为准确，即使节点中的内容在视口中不可见，也捕获完整节点。</span><span class="sxs-lookup"><span data-stu-id="68abc-195">In Microsoft Edge version 89, node screenshots are more accurate, capturing the full node even if content from the node is not visible in the viewport.</span></span>  <span data-ttu-id="68abc-196">在"**元素**"工具中，将鼠标悬停在元素上，打开上下文菜单 \ (右键单击\) ，然后选择"捕获节点屏幕截图 **"。**</span><span class="sxs-lookup"><span data-stu-id="68abc-196">In the **Elements** tool, hover  on an element, open the contextual menu \(right-click\), and choose **Capture node screenshot**.</span></span>  <span data-ttu-id="68abc-197">若要查看 Chromium 开放源代码项目中此功能的历史记录，请导航到"问题[1003629"。][CR1003629]</span><span class="sxs-lookup"><span data-stu-id="68abc-197">To review the history of this feature in the Chromium open-source project, navigate to Issue [1003629][CR1003629].</span></span>  

:::image type="complex" source="../../media/2021/01/capture-node-screenshot.msft.png" alt-text="在"元素"工具的上下文菜单上突出显示的捕获节点屏幕截图" lightbox="../../media/2021/01/capture-node-screenshot.msft.png":::
   <span data-ttu-id="68abc-199">**在"元素"** 工具的上下文菜单上突出显示的捕获 **节点** 屏幕截图</span><span class="sxs-lookup"><span data-stu-id="68abc-199">**Capture node screenshot** highlighted on the context menu in the **Elements** tool</span></span>  
:::image-end:::  

### <a name="elements-tool-updates"></a><span data-ttu-id="68abc-200">元素工具更新</span><span class="sxs-lookup"><span data-stu-id="68abc-200">Elements tool updates</span></span>  

#### <a name="support-forcing-the-target-css-state"></a><span data-ttu-id="68abc-201">支持强制使用 ：target CSS 状态</span><span class="sxs-lookup"><span data-stu-id="68abc-201">Support forcing the :target CSS state</span></span>  

<span data-ttu-id="68abc-202">你现在可以使用 DevTools 强制使用 [：target][MdnDocsWebCssTarget] CSS 伪类。</span><span class="sxs-lookup"><span data-stu-id="68abc-202">You may now use DevTools to force the [:target][MdnDocsWebCssTarget] CSS pseudo-class.</span></span>  <span data-ttu-id="68abc-203">当唯一元素 \ (\) 具有与 URL 片段匹配的 时，将触发伪 `:target` `id` 类。</span><span class="sxs-lookup"><span data-stu-id="68abc-203">The `:target` pseudo-class is triggered when a unique element \(the target element\) has an `id` that matches a fragment of the URL.</span></span>  <span data-ttu-id="68abc-204">例如，URL 使用 触发 HTML 元素上的伪 `http://www.example.com/index.html#section1` `:target` 类 `id="section1"` 。</span><span class="sxs-lookup"><span data-stu-id="68abc-204">For example, the `http://www.example.com/index.html#section1` URL triggers the `:target` pseudo-class on an HTML element with `id="section1"`.</span></span>  <span data-ttu-id="68abc-205">若要试用突出显示部分 1 的演示，请导航到 [CSS ：target demo][GithubMicrosoftedgeDevtoolssamplesWhatsNew89TargetCssDemoHtmlSection1]。</span><span class="sxs-lookup"><span data-stu-id="68abc-205">To try a demo with section 1 highlighted, navigate to [CSS :target demo][GithubMicrosoftedgeDevtoolssamplesWhatsNew89TargetCssDemoHtmlSection1].</span></span>  <span data-ttu-id="68abc-206">若要查看 Chromium 开放源代码项目中此功能的历史记录，请导航到"问题[1156628"。][CR1156628]</span><span class="sxs-lookup"><span data-stu-id="68abc-206">To review the history of this feature in the Chromium open-source project, navigate to Issue [1156628][CR1156628].</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-styles-none-forced.msft.png" alt-text="未强制 CSS 突出显示的网页" lightbox="../../media/2021/01/elements-styles-none-forced.msft.png":::
         <span data-ttu-id="68abc-208">未强制 CSS 突出显示的网页</span><span class="sxs-lookup"><span data-stu-id="68abc-208">Webpage highlighted with no forced CSS</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-styles-target-forced.msft.png" alt-text="：target CSS 强制和网页突出显示" lightbox="../../media/2021/01/elements-styles-target-forced.msft.png":::
         `:target` <span data-ttu-id="68abc-210">CSS 强制和网页突出显示</span><span class="sxs-lookup"><span data-stu-id="68abc-210">CSS forced and webpage highlighted</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::

#### <a name="use-duplicate-elements-to-copy-elements"></a><span data-ttu-id="68abc-211">使用 Duplicate 元素复制元素</span><span class="sxs-lookup"><span data-stu-id="68abc-211">Use Duplicate elements to copy elements</span></span>  

<span data-ttu-id="68abc-212">使用新的 **Duplicate 元素** 快捷方式可克隆元素。</span><span class="sxs-lookup"><span data-stu-id="68abc-212">Use the new **Duplicate element** shortcut to clone an element.</span></span>  <span data-ttu-id="68abc-213">在"**元素**"工具中，将鼠标悬停在元素上，打开上下文菜单 \ (右键单击\) ，选择 **"复制元素"。**</span><span class="sxs-lookup"><span data-stu-id="68abc-213">In the **Elements** tool, hover on an element, open the contextual menu \(right-click\), choose **Duplicate element**.</span></span>  <span data-ttu-id="68abc-214">在所选元素下创建一个新元素。</span><span class="sxs-lookup"><span data-stu-id="68abc-214">A new element is created under the selected element.</span></span>  <span data-ttu-id="68abc-215">若要使用键盘快捷方式复制元素，请选择 `Shift` + `Alt` + `Down Arrow` \ (Windows/Linux\) 或 `Shift` + `Option` + `Down Arrow` \ (macOS\) 。</span><span class="sxs-lookup"><span data-stu-id="68abc-215">To duplicate the element with a keyboard shortcut, select `Shift`+`Alt`+`Down Arrow` \(Windows/Linux\) or `Shift`+`Option`+`Down Arrow` \(macOS\).</span></span>  <span data-ttu-id="68abc-216">若要查看 Chromium 开放源代码项目中此功能的历史记录，请导航到"问题[1150797"。][CR1150797]</span><span class="sxs-lookup"><span data-stu-id="68abc-216">To review the history of this feature in the Chromium open-source project, navigate to Issue [1150797][CR1150797].</span></span>  

:::image type="complex" source="../../media/2021/01/elements-duplicate-element.msft.png" alt-text="Duplicate 元素在"元素"工具中元素的上下文菜单中突出显示" lightbox="../../media/2021/01/elements-duplicate-element.msft.png":::
   <span data-ttu-id="68abc-218">Duplicate**元素**在"元素"工具中元素的**上下文菜单中突出显示**</span><span class="sxs-lookup"><span data-stu-id="68abc-218">The **Duplicate element** is highlighted in the context menu on an element in the **Elements** tool</span></span>  
:::image-end:::  

#### <a name="color-pickers-for-custom-css-properties"></a><span data-ttu-id="68abc-219">自定义 CSS 属性的颜色选取器</span><span class="sxs-lookup"><span data-stu-id="68abc-219">Color pickers for custom CSS properties</span></span>  

<span data-ttu-id="68abc-220">" **样式** "窗格现在显示自定义 CSS 属性的颜色选取器。</span><span class="sxs-lookup"><span data-stu-id="68abc-220">The **Styles** pane now displays color pickers for custom CSS properties.</span></span>  <span data-ttu-id="68abc-221">若要循环浏览颜色值的 RGBA、HSLA 和 Hex 格式，请按住并选择 `Shift` 颜色选取器。</span><span class="sxs-lookup"><span data-stu-id="68abc-221">To cycle through the RGBA, HSLA, and Hex formats of the color value, hold `Shift` and choose the color picker.</span></span>  <span data-ttu-id="68abc-222">若要查看 Chromium 开放源代码项目中此功能的历史记录，请导航到"问题[1147016"。][CR1147016]</span><span class="sxs-lookup"><span data-stu-id="68abc-222">To review the history of this feature in the Chromium open-source project, navigate to Issue [1147016][CR1147016].</span></span>  

:::image type="complex" source="../../media/2021/01/elements-styles-change-color-format.msft.png" alt-text="自定义 CSS 属性的颜色选取器" lightbox="../../media/2021/01/elements-styles-change-color-format.msft.png":::
   <span data-ttu-id="68abc-224">自定义 CSS 属性的颜色选取器</span><span class="sxs-lookup"><span data-stu-id="68abc-224">Color pickers for custom CSS properties</span></span>  
:::image-end:::  

#### <a name="copy-css-classes-and-properties"></a><span data-ttu-id="68abc-225">复制 CSS 类和属性</span><span class="sxs-lookup"><span data-stu-id="68abc-225">Copy CSS classes and properties</span></span>  

<span data-ttu-id="68abc-226">现在，您可以使用上下文菜单中的一些新选项更快地复制 CSS 属性。</span><span class="sxs-lookup"><span data-stu-id="68abc-226">You may now copy CSS properties quicker with a few new options in the contextual menu.</span></span>  <span data-ttu-id="68abc-227">在" **元素"** 工具中，选择一个元素。</span><span class="sxs-lookup"><span data-stu-id="68abc-227">In the **Elements** tool, choose an element.</span></span>  <span data-ttu-id="68abc-228">若要复制值，请在"样式\*\*\*\*"窗格中，将鼠标悬停在 CSS 类或 CSS 属性上，打开上下文菜单 \ (右键单击\) ，然后选择复制选项。</span><span class="sxs-lookup"><span data-stu-id="68abc-228">To copy the value, in the **Styles** pane, hover on a CSS class or a CSS property, open a contextual menu \(right-click\), and choose the copy option.</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="68abc-229">复制 CSS 类的选项。</span><span class="sxs-lookup"><span data-stu-id="68abc-229">Copy options for a CSS class.</span></span>  
      
      | <span data-ttu-id="68abc-230">选项</span><span class="sxs-lookup"><span data-stu-id="68abc-230">Option</span></span> | <span data-ttu-id="68abc-231">详细信息</span><span class="sxs-lookup"><span data-stu-id="68abc-231">Details</span></span> |  
      |:--- |:--- |  
      | **<span data-ttu-id="68abc-232">复制选择器</span><span class="sxs-lookup"><span data-stu-id="68abc-232">Copy selector</span></span>** | <span data-ttu-id="68abc-233">复制当前选择器名称。</span><span class="sxs-lookup"><span data-stu-id="68abc-233">Copy the current selector name.</span></span> |  
      | **<span data-ttu-id="68abc-234">复制规则</span><span class="sxs-lookup"><span data-stu-id="68abc-234">Copy rule</span></span>** | <span data-ttu-id="68abc-235">复制当前选择器的规则。</span><span class="sxs-lookup"><span data-stu-id="68abc-235">Copy the rule of the current selector.</span></span> |  
      | **<span data-ttu-id="68abc-236">复制所有声明</span><span class="sxs-lookup"><span data-stu-id="68abc-236">Copy all declarations</span></span>** | <span data-ttu-id="68abc-237">复制当前规则下的所有声明，包括无效和前缀属性。</span><span class="sxs-lookup"><span data-stu-id="68abc-237">Copy all declarations under the current rule, including non-valid and prefixed properties.</span></span> |  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="68abc-238">复制 CSS 属性的选项。</span><span class="sxs-lookup"><span data-stu-id="68abc-238">Copy options for a CSS property.</span></span>  
      
      | <span data-ttu-id="68abc-239">选项</span><span class="sxs-lookup"><span data-stu-id="68abc-239">Option</span></span> | <span data-ttu-id="68abc-240">详细信息</span><span class="sxs-lookup"><span data-stu-id="68abc-240">Details</span></span> |      
      |:--- |:--- |  
      | **<span data-ttu-id="68abc-241">复制声明</span><span class="sxs-lookup"><span data-stu-id="68abc-241">Copy declaration</span></span>** | <span data-ttu-id="68abc-242">复制当前行的声明。</span><span class="sxs-lookup"><span data-stu-id="68abc-242">Copy the declaration of the current line.</span></span> |  
      | **<span data-ttu-id="68abc-243">Copy 属性</span><span class="sxs-lookup"><span data-stu-id="68abc-243">Copy property</span></span>** | <span data-ttu-id="68abc-244">复制当前行的属性。</span><span class="sxs-lookup"><span data-stu-id="68abc-244">Copy the property of the current line.</span></span> |  
      | **<span data-ttu-id="68abc-245">复制值</span><span class="sxs-lookup"><span data-stu-id="68abc-245">Copy value</span></span>** | <span data-ttu-id="68abc-246">复制当前行的值。</span><span class="sxs-lookup"><span data-stu-id="68abc-246">Copy the value of the current line.</span></span> |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/copy-css-class.msft.png" alt-text="复制上下文菜单中 CSS 类的选项" lightbox="../../media/2021/01/copy-css-class.msft.png":::
         <span data-ttu-id="68abc-248">复制上下文菜单中 CSS 类的选项</span><span class="sxs-lookup"><span data-stu-id="68abc-248">Copy options for a CSS class in the contextual menu</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/copy-css-property-cropped.msft.png" alt-text="复制上下文菜单中 CSS 属性的选项" lightbox="../../media/2021/01/copy-css-property.msft.png":::
         <span data-ttu-id="68abc-250">复制上下文菜单中 CSS 属性的选项</span><span class="sxs-lookup"><span data-stu-id="68abc-250">Copy options for a CSS property in the contextual menu</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="68abc-251">若要查看 Chromium 开放源代码项目中此功能的历史记录，请导航到"问题[1152391"。][CR1152391]</span><span class="sxs-lookup"><span data-stu-id="68abc-251">To review the history of this feature in the Chromium open-source project, navigate to Issue [1152391][CR1152391].</span></span>  

### <a name="cookies-updates"></a><span data-ttu-id="68abc-252">Cookie 更新</span><span class="sxs-lookup"><span data-stu-id="68abc-252">Cookies updates</span></span>  

#### <a name="new-option-to-display-url-decoded-cookies"></a><span data-ttu-id="68abc-253">显示 URL 解码 Cookie 的新选项</span><span class="sxs-lookup"><span data-stu-id="68abc-253">New option to display URL-decoded cookies</span></span>  

<span data-ttu-id="68abc-254">现在，你可以选择在"Cookie"窗格中显示 URL 解码的 **Cookie 值** 。</span><span class="sxs-lookup"><span data-stu-id="68abc-254">You may now opt to display the URL-decoded cookies value in the **Cookies** pane.</span></span>  <span data-ttu-id="68abc-255">若要显示解码的 Cookie，请导航\*\*\*\* 到"应用程序 Cookie"窗格，选择列表上的任何 Cookie，然后选择"显示  >  \*\*\*\* 已解码**的 URL"旁边的复选框**。</span><span class="sxs-lookup"><span data-stu-id="68abc-255">To display the decoded cookie, navigate to **Application** > **Cookies** pane, choose any cookie on the list, and choose the checkbox next to **Show URL decoded**.</span></span>  <span data-ttu-id="68abc-256">若要查看 Chromium 开放源代码项目中此功能的历史记录，请导航到"问题[997625"。][CR997625]</span><span class="sxs-lookup"><span data-stu-id="68abc-256">To review the history of this feature in the Chromium open-source project, navigate to Issue [997625][CR997625].</span></span>  

:::image type="complex" source="../../media/2021/01/application-cookies-show-url-decoded.msft.png" alt-text="用于显示 URL 解码的 Cookie 的选项" lightbox="../../media/2021/01/application-cookies-show-url-decoded.msft.png":::
   <span data-ttu-id="68abc-258">用于显示 URL 解码的 Cookie 的选项</span><span class="sxs-lookup"><span data-stu-id="68abc-258">Option to display URL decoded cookies</span></span>  
:::image-end:::  

#### <a name="filter-and-clear-visible-cookies"></a><span data-ttu-id="68abc-259">筛选和清除可见的 Cookie</span><span class="sxs-lookup"><span data-stu-id="68abc-259">Filter and clear visible cookies</span></span>  

<span data-ttu-id="68abc-260">在 Microsoft Edge 版本 88\*\*\*\* 或更早版本中，应用程序工具仅提供了一种使用"清除所有 Cookie"按钮清除所有**Cookie**的方法。</span><span class="sxs-lookup"><span data-stu-id="68abc-260">In Microsoft Edge version 88 or earlier, the **Application** tool only provided a way to clear all cookies with the **Clear all cookies** button.</span></span>  <span data-ttu-id="68abc-261">在 Microsoft Edge 版本 89 中，现在可以选择"清除筛选的 **Cookie"，** 以仅删除筛选的 Cookie。</span><span class="sxs-lookup"><span data-stu-id="68abc-261">In Microsoft Edge version 89, you may now choose **Clear filtered cookies** to delete only the filtered cookies.</span></span>  <span data-ttu-id="68abc-262">若要筛选 Cookie，请导航到 **"应用程序**  >  **Cookie"，** 并在"**筛选器**"文本框中键入 。</span><span class="sxs-lookup"><span data-stu-id="68abc-262">To filter cookies, navigate to **Application** > **Cookies**, and type in the **Filter** textbox.</span></span>  <span data-ttu-id="68abc-263">若要删除显示的 Cookie，请选择" **清除筛选的 Cookie"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="68abc-263">To delete the displayed cookies, choose the **Clear filtered cookies** button.</span></span>  <span data-ttu-id="68abc-264">若要显示所有其他 Cookie，请清除筛选器文本。</span><span class="sxs-lookup"><span data-stu-id="68abc-264">To display all other cookies, clear the filter text.</span></span>  <span data-ttu-id="68abc-265">若要查看 Chromium 开放源代码项目中此功能的历史记录，请导航到"问题[978059"。][CR978059]</span><span class="sxs-lookup"><span data-stu-id="68abc-265">To review the history of this feature in the Chromium open-source project, navigate to Issue [978059][CR978059].</span></span>  

:::image type="complex" source="../../media/2021/01/application-cookies-clear-filtered-cookies.msft.png" alt-text="仅清除可见的 Cookie" lightbox="../../media/2021/01/application-cookies-clear-filtered-cookies.msft.png":::
   <span data-ttu-id="68abc-267">仅清除可见的 Cookie</span><span class="sxs-lookup"><span data-stu-id="68abc-267">Clear only visible cookies</span></span>  
:::image-end:::  

#### <a name="new-option-to-clear-third-party-cookies-in-the-storage-pane"></a><span data-ttu-id="68abc-268">在"存储"窗格中清除第三方 Cookie 的新选项</span><span class="sxs-lookup"><span data-stu-id="68abc-268">New option to clear third-party cookies in the Storage pane</span></span>  

<span data-ttu-id="68abc-269">默认情况下，DevTools 现在仅清除第一方 Cookie。</span><span class="sxs-lookup"><span data-stu-id="68abc-269">DevTools now clear only first-party cookies by default.</span></span>  <span data-ttu-id="68abc-270">若要仅清除网站数据和第一方 Cookie，请导航到"**应用程序**存储  >  \*\*\*\*"，然后选择"**清除网站数据"。**</span><span class="sxs-lookup"><span data-stu-id="68abc-270">To clear website data and first-party cookies only, navigate to **Application** > **Storage**, and then choose **Clear site data**.</span></span>  

<span data-ttu-id="68abc-271">若要清除网站数据和所有 Cookie，请导航到"**应用程序存储**  >  **"。**</span><span class="sxs-lookup"><span data-stu-id="68abc-271">To clear website data and all cookies, navigate to **Application** > **Storage**.</span></span>  <span data-ttu-id="68abc-272">选中包含第三方**Cookie 旁边的**复选框，然后选择"清除**站点数据"。**</span><span class="sxs-lookup"><span data-stu-id="68abc-272">Choose the checkbox next to **including third-party cookies**, and then choose **Clear site data**.</span></span>  

<span data-ttu-id="68abc-273">若要查看 Chromium 开源项目中此功能的历史记录，请导航到"问题[1012337"。][CR1012337]</span><span class="sxs-lookup"><span data-stu-id="68abc-273">To review the history of this feature in the Chromium open-source project, navigate to Issue [1012337][CR1012337].</span></span>  

:::image type="complex" source="../../media/2021/01/application-storage-clear-site-data-including-third-party-cookies.msft.png" alt-text="用于清除第三方 Cookie 的选项" lightbox="../../media/2021/01/application-storage-clear-site-data-including-third-party-cookies.msft.png":::
   <span data-ttu-id="68abc-275">用于清除第三方 Cookie 的选项</span><span class="sxs-lookup"><span data-stu-id="68abc-275">Option to clear third-party cookies</span></span>  
:::image-end:::  

### <a name="network-tool-updates"></a><span data-ttu-id="68abc-276">网络工具更新</span><span class="sxs-lookup"><span data-stu-id="68abc-276">Network tool updates</span></span>  

#### <a name="persist-record-network-log-setting"></a><span data-ttu-id="68abc-277">持久记录网络日志设置</span><span class="sxs-lookup"><span data-stu-id="68abc-277">Persist Record network log setting</span></span>  

<span data-ttu-id="68abc-278">在 Microsoft Edge 版本 88 或更早版本中，DevTools 在网页刷新 **时** 重置"记录网络日志"设置。</span><span class="sxs-lookup"><span data-stu-id="68abc-278">In Microsoft Edge version 88 or earlier, DevTools reset the **Record network log** setting when a webpage refreshes.</span></span>  <span data-ttu-id="68abc-279">在 Microsoft Edge 版本 89 中，DevTools 现在保留 **"记录网络日志"** 设置。</span><span class="sxs-lookup"><span data-stu-id="68abc-279">In Microsoft Edge version 89, DevTools now persist the **Record network log** setting.</span></span>  <span data-ttu-id="68abc-280">若要查看 Chromium 开放源代码项目中此功能的历史记录，请导航到"问题[1122580"。][CR1122580]</span><span class="sxs-lookup"><span data-stu-id="68abc-280">To review the history of this feature in the Chromium open-source project, navigate to Issue [1122580][CR1122580].</span></span>  

:::image type="complex" source="../../media/2021/01/network-log.msft.png" alt-text="记录网络日志" lightbox="../../media/2021/01/network-log.msft.png":::
   <span data-ttu-id="68abc-282">记录网络日志</span><span class="sxs-lookup"><span data-stu-id="68abc-282">Record network log</span></span>  
:::image-end:::  

#### <a name="online-option-is-now-no-throttling-option"></a><span data-ttu-id="68abc-283">联机选项现在为"无限制"选项</span><span class="sxs-lookup"><span data-stu-id="68abc-283">Online option is now No throttling option</span></span>  

<span data-ttu-id="68abc-284">网络模拟选项**Online**现已重命名为"**无限制"。**</span><span class="sxs-lookup"><span data-stu-id="68abc-284">The network emulation option **Online** is now renamed to **No Throttling**.</span></span>  <span data-ttu-id="68abc-285">若要查看 Chromium 开放源代码项目中此功能的历史记录，请导航到"问题[1028078"。][CR1028078]</span><span class="sxs-lookup"><span data-stu-id="68abc-285">To review the history of this feature in the Chromium open-source project, navigate to Issue [1028078][CR1028078].</span></span>  

:::image type="complex" source="../../media/2021/01/network-no-throttling.msft.png" alt-text="无限制选项" lightbox="../../media/2021/01/network-no-throttling.msft.png":::
   <span data-ttu-id="68abc-287">**无限制** 选项</span><span class="sxs-lookup"><span data-stu-id="68abc-287">**No throttling** option</span></span>  
:::image-end:::  

### <a name="new-copy-options-in-the-console-tool-sources-tool-and-styles-pane"></a><span data-ttu-id="68abc-288">控制台工具、"源"工具和"样式"窗格中的新复制选项</span><span class="sxs-lookup"><span data-stu-id="68abc-288">New copy options in the Console tool, Sources tool, and Styles pane</span></span>

#### <a name="copy-object-in-the-console-and-sources-tool"></a><span data-ttu-id="68abc-289">复制控制台和源工具中的对象</span><span class="sxs-lookup"><span data-stu-id="68abc-289">Copy object in the Console and Sources tool</span></span>  

<span data-ttu-id="68abc-290">现在，你可以复制控制台和源 **工具** 中的 **对象** 值。</span><span class="sxs-lookup"><span data-stu-id="68abc-290">You may now copy object values in the **Console** and **Sources** tools.</span></span>  <span data-ttu-id="68abc-291">复制对象值的能力在使用大型对象时很有用。</span><span class="sxs-lookup"><span data-stu-id="68abc-291">The ability to copy object values is useful when working with large objects.</span></span>  <span data-ttu-id="68abc-292">若要查看 Chromium 开放源代码项目中此功能的历史记录，请导航到"问题[1148353"][CR1148353]和["1149859"。][CR1149859]</span><span class="sxs-lookup"><span data-stu-id="68abc-292">To review the history of this feature in the Chromium open-source project, navigate to Issues [1148353][CR1148353] and [1149859][CR1149859].</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="68abc-293">在 **控制台工具** 中，将鼠标悬停在对象上，打开上下文菜单 \ (右键单击\) ，然后选择复制 **对象**。</span><span class="sxs-lookup"><span data-stu-id="68abc-293">In the **Console** tool, hover on an object, open the contextual menu \(right-click\), and then choose **Copy object**.</span></span>  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="68abc-294">在"\*\*\*\* 源"工具中的断点上，将鼠标悬停在对象上的"\*\*\*\* 对象"弹出窗口中，突出显示一个对象，打开上下文菜单 \ (右键单击\) ，然后选择"复制对象"。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="68abc-294">In the **Sources** tool, on a breakpoint, hover on an object, in the **Object** popup window, highlight an object, open the contextual menu \(right-click\), and then choose **Copy object**.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/console-copy-object.msft.png" alt-text="在控制台中复制对象" lightbox="../../media/2021/01/console-copy-object.msft.png":::
         <span data-ttu-id="68abc-296">在控制台中复制 **对象**</span><span class="sxs-lookup"><span data-stu-id="68abc-296">Copy object in the **Console**</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/sources-breakpoint-object-copy-object.msft.png" alt-text="在源中复制对象" lightbox="../../media/2021/01/sources-breakpoint-object-copy-object.msft.png":::
         <span data-ttu-id="68abc-298">在源中复制 **对象**</span><span class="sxs-lookup"><span data-stu-id="68abc-298">Copy object in **Sources**</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

#### <a name="copy-file-name-in-the-sources-tool-and-styles-pane"></a><span data-ttu-id="68abc-299">复制"源"工具和"样式"窗格中的文件名</span><span class="sxs-lookup"><span data-stu-id="68abc-299">Copy file name in the Sources tool and Styles pane</span></span>  

<span data-ttu-id="68abc-300">现在，可以使用上下文菜单复制文件名。</span><span class="sxs-lookup"><span data-stu-id="68abc-300">You may now copy a file name using the contextual menu.</span></span>  <span data-ttu-id="68abc-301">若要查看 Chromium 开源项目中此功能的历史记录，请导航到"问题[1155120"。][CR1155120]</span><span class="sxs-lookup"><span data-stu-id="68abc-301">To review the history of this feature in the Chromium open-source project, navigate to Issues [1155120][CR1155120].</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="68abc-302">在"**源**"工具中，将鼠标悬停在文件名上，打开上下文菜单 \ (右键单击\) ，然后选择"复制**文件名"。**</span><span class="sxs-lookup"><span data-stu-id="68abc-302">In the **Sources** tool, hover on a file name, open the contextual menu \(right-click\), and then choose **Copy file name**.</span></span>  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="68abc-303">在"**元素**>样式"窗格中，\*\*\*\* 将鼠标悬停在文件名上，打开上下文菜单 \ (右键单击\) ，然后选择"复制**文件名"。**</span><span class="sxs-lookup"><span data-stu-id="68abc-303">In the **Elements** tool > **Styles** pane, hover on a file name, open the contextual menu \(right-click\), and then choose **Copy file name**.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/sources-copy-file-name.msft.png" alt-text="复制源中的文件名" lightbox="../../media/2021/01/sources-copy-file-name.msft.png":::
         <span data-ttu-id="68abc-305">复制源中的 **文件名**</span><span class="sxs-lookup"><span data-stu-id="68abc-305">Copy file name in **Sources**</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-styles-copy-file-name.msft.png" alt-text="在"样式"窗格中复制文件名" lightbox="../../media/2021/01/elements-styles-copy-file-name.msft.png":::
         <span data-ttu-id="68abc-307">在"样式"窗格中 **复制** 文件名</span><span class="sxs-lookup"><span data-stu-id="68abc-307">Copy file name in **Styles** pane</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

### <a name="updates-to-frame-details"></a><span data-ttu-id="68abc-308">帧详细信息更新</span><span class="sxs-lookup"><span data-stu-id="68abc-308">Updates to Frame details</span></span>  

#### <a name="service-workers-information-in-frame-details"></a><span data-ttu-id="68abc-309">框架详细信息中的服务工作人员信息</span><span class="sxs-lookup"><span data-stu-id="68abc-309">Service Workers information in Frame details</span></span>  

<span data-ttu-id="68abc-310">DevTools 现在在父框架下列出专用服务工作器。</span><span class="sxs-lookup"><span data-stu-id="68abc-310">DevTools now lists a dedicated service worker under the parent frame.</span></span>  <span data-ttu-id="68abc-311">下图显示了服务工作者的详细信息。</span><span class="sxs-lookup"><span data-stu-id="68abc-311">In the following figure, service worker details are displayed.</span></span>  <span data-ttu-id="68abc-312">若要显示服务工作线程的详细信息，请导航到"**应用程序**框架  >  \*\*\*\*  >  `top`  >  **服务**工作者"，然后选择一个服务工作线程。</span><span class="sxs-lookup"><span data-stu-id="68abc-312">To display the service worker details, navigate to **Application** > **Frames** > `top` > **Service Workers** and then choose a service worker.</span></span>  <span data-ttu-id="68abc-313">若要查看 Chromium 开源项目中此功能的历史记录，请导航到"问题[1122507"。][CR1122507]</span><span class="sxs-lookup"><span data-stu-id="68abc-313">To review the history of this feature in the Chromium open-source project, navigate to Issue [1122507][CR1122507].</span></span>  

:::image type="complex" source="../../media/2021/01/application-frames-service-workers-details.msft.png" alt-text="框架详细信息中的服务工作人员信息" lightbox="../../media/2021/01/application-frames-service-workers-details.msft.png":::
   <span data-ttu-id="68abc-315">**框架详细信息** 中的服务 **工作人员** 信息</span><span class="sxs-lookup"><span data-stu-id="68abc-315">**Service Workers** information in the **Frames** details</span></span>  
:::image-end:::  

#### <a name="measure-memory-information-in-frame-details"></a><span data-ttu-id="68abc-316">在帧详细信息中测量内存信息</span><span class="sxs-lookup"><span data-stu-id="68abc-316">Measure Memory information in Frame details</span></span>  

<span data-ttu-id="68abc-317">API `performance.measureMemory()` 状态现在显示在 **API** 可用性部分下。</span><span class="sxs-lookup"><span data-stu-id="68abc-317">The `performance.measureMemory()` API status is now displayed under the **API availability** section.</span></span>  <span data-ttu-id="68abc-318">新 `performance.measureMemory()` API 估计了整个网页的内存使用率。</span><span class="sxs-lookup"><span data-stu-id="68abc-318">The new `performance.measureMemory()` API estimates the memory usage of the entire webpage.</span></span>  <span data-ttu-id="68abc-319">若要查看 Chromium 开放源代码项目中此功能的历史记录，请导航到"问题[1139899"。][CR1139899]</span><span class="sxs-lookup"><span data-stu-id="68abc-319">To review the history of this feature in the Chromium open-source project, navigate to Issue [1139899][CR1139899].</span></span>  

:::image type="complex" source="../../media/2021/01/application-frames-measure-memory.msft.png" alt-text="测量内存" lightbox="../../media/2021/01/application-frames-measure-memory.msft.png":::
   <span data-ttu-id="68abc-321">测量内存</span><span class="sxs-lookup"><span data-stu-id="68abc-321">Measure Memory</span></span>  
:::image-end:::  

### <a name="dropped-frames-in-the-performance-tool"></a><span data-ttu-id="68abc-322">性能工具中丢弃的帧</span><span class="sxs-lookup"><span data-stu-id="68abc-322">Dropped frames in the Performance tool</span></span>  

<span data-ttu-id="68abc-323">在性能 [工具中分析负载性能时][DevtoolsEvaluatePerformanceReferenceRecordLoadPerformance]，"框架 **"部分现在** 将丢弃的帧标记为红色。</span><span class="sxs-lookup"><span data-stu-id="68abc-323">When you [analyze load performance in the Performance tool][DevtoolsEvaluatePerformanceReferenceRecordLoadPerformance], the **Frames** section now marks dropped frames as red.</span></span>  <span data-ttu-id="68abc-324">若要显示帧速率，请将鼠标悬停在一个丢弃的帧上。</span><span class="sxs-lookup"><span data-stu-id="68abc-324">To display the frame rate, hover on a dropped frame.</span></span>  <span data-ttu-id="68abc-325">若要查看 Chromium 开源项目中此功能的历史记录，请导航到"问题[1075865"。][CR1075865]</span><span class="sxs-lookup"><span data-stu-id="68abc-325">To review the history of this feature in the Chromium open-source project, navigate to Issue [1075865][CR1075865].</span></span>  

:::image type="complex" source="../../media/2021/01/performance-frames-dropped-frames-red.msft.png" alt-text="丢弃的帧" lightbox="../../media/2021/01/performance-frames-dropped-frames-red.msft.png":::
   <span data-ttu-id="68abc-327">丢弃的帧</span><span class="sxs-lookup"><span data-stu-id="68abc-327">Dropped frames</span></span>  
:::image-end:::  

#### <a name="new-color-contrast-calculation---advanced-perceptual-contrast-algorithm-apca"></a><span data-ttu-id="68abc-328">新颜色对比度计算 - 高级感知对比度算法 (APCA) </span><span class="sxs-lookup"><span data-stu-id="68abc-328">New color contrast calculation - Advanced Perceptual Contrast Algorithm (APCA)</span></span>  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

<span data-ttu-id="68abc-329">APCA 高级感知对比度算法[ (APCA][GithubW3cSilverGuidelinesMethodsMethodFontCharacteristicContrastHtml]) 替换了颜色选取器中的[AA][W3cWaiWcag21QuickrefContrastMinimum] / [AAA][W3cWaiWcag21QuickrefContrastEnhanced]指南[对比率][DevtoolsAccessibilityReferenceViewContrastRatioTextElementColorPicker]。</span><span class="sxs-lookup"><span data-stu-id="68abc-329">The [Advanced Perceptual Contrast Algorithm (APCA)][GithubW3cSilverGuidelinesMethodsMethodFontCharacteristicContrastHtml] replaces the [AA][W3cWaiWcag21QuickrefContrastMinimum]/[AAA][W3cWaiWcag21QuickrefContrastEnhanced] guidelines contrast ratio in the [Color Picker][DevtoolsAccessibilityReferenceViewContrastRatioTextElementColorPicker].</span></span>  <span data-ttu-id="68abc-330">APCA 是计算对比度的一种新方式。</span><span class="sxs-lookup"><span data-stu-id="68abc-330">APCA is a new way to compute contrast.</span></span>  <span data-ttu-id="68abc-331">它基于对颜色感知的新式研究。</span><span class="sxs-lookup"><span data-stu-id="68abc-331">It is based on modern research on color perception.</span></span>  <span data-ttu-id="68abc-332">与 AA/AAA 准则相比，APCA 更依赖于上下文。</span><span class="sxs-lookup"><span data-stu-id="68abc-332">Compared to AA/AAA guidelines, APCA is more context-dependent.</span></span>  <span data-ttu-id="68abc-333">对比度根据文本、颜色和上下文的以下空间属性计算。</span><span class="sxs-lookup"><span data-stu-id="68abc-333">The contrast is calculated based on the following spatial properties of the text, color, and context.</span></span>  

*   <span data-ttu-id="68abc-334">文本的空间属性，包括字体粗细和大小。</span><span class="sxs-lookup"><span data-stu-id="68abc-334">Spatial properties of text that include font weight and size.</span></span>  
*   <span data-ttu-id="68abc-335">包含文本和背景之间感知对比度的颜色的空间属性。</span><span class="sxs-lookup"><span data-stu-id="68abc-335">Spatial properties of color that include perceived contrast between text and background.</span></span>  
*   <span data-ttu-id="68abc-336">包含环境光、周围环境和预期用途的上下文的空间属性。</span><span class="sxs-lookup"><span data-stu-id="68abc-336">Spatial properties of context that include ambient light, surroundings, and intended purpose.</span></span>  
    
<span data-ttu-id="68abc-337">若要打开此实验，请导航到[][DevtoolsCustomizeIndexSettings]设置实验，并选中启用新的高级感知对比度算法 (APCA) 替换以前的对比度比率和  >  \*\*\*\*\*\*AA/AAA 指南旁边的复选框\*\*。</span><span class="sxs-lookup"><span data-stu-id="68abc-337">To turn on this experiment, navigate to [Settings][DevtoolsCustomizeIndexSettings] > **Experiments**  and choose the checkbox next to **Enable new Advanced Perceptual Contrast Algorithm (APCA) replacing previous contrast ratio and AA/AAA guidelines**.</span></span>  <span data-ttu-id="68abc-338">若要查看 Chromium 开放源代码项目中此功能的历史记录，请导航到"问题[1121900"。][CR1121900]</span><span class="sxs-lookup"><span data-stu-id="68abc-338">To review the history of this feature in the Chromium open-source project, navigate to Issue [1121900][CR1121900].</span></span>  

:::image type="complex" source="../../media/2021/01/advanced-perceptual-contrast-algorithm.msft.png" alt-text="颜色选取器中的 APCA" lightbox="../../media/2021/01/advanced-perceptual-contrast-algorithm.msft.png":::
   <span data-ttu-id="68abc-340">颜色选取器中的 APCA</span><span class="sxs-lookup"><span data-stu-id="68abc-340">APCA in the Color Picker</span></span>  
:::image-end:::  

## <a name="download-the-microsoft-edge-preview-channels"></a><span data-ttu-id="68abc-341">下载 Microsoft Edge 预览频道</span><span class="sxs-lookup"><span data-stu-id="68abc-341">Download the Microsoft Edge preview channels</span></span>  

<span data-ttu-id="68abc-342">如果你使用的是 Windows、Linux 或 macOS，请考虑使用 [Microsoft Edge 预览][MicrosoftEdgePreviewChannels] 通道作为默认开发浏览器。</span><span class="sxs-lookup"><span data-stu-id="68abc-342">If you are on Windows, Linux, or macOS, consider using the [Microsoft Edge preview channels][MicrosoftEdgePreviewChannels] as your default development browser.</span></span>  <span data-ttu-id="68abc-343">预览频道使你能够访问最新的 DevTools 功能。</span><span class="sxs-lookup"><span data-stu-id="68abc-343">The preview channels give you access to the latest DevTools features.</span></span>  

## <a name="getting-in-touch-with-microsoft-edge-devtools-team"></a><span data-ttu-id="68abc-344">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="68abc-344">Getting in touch with Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]

<!-- links -->  

[DevtoolsWhatsNew85]: ../../2020/06/devtools.md "Microsoft Edge 85 (开发工具中的新增) |Microsoft Docs"  

[DevtoolsAccessibilityReferenceViewContrastRatioTextElementColorPicker]: /microsoft-edge/devtools-guide-chromium/accessibility/reference#view-the-contrast-ratio-of-a-text-element-in-the-color-picker "查看颜色选取器中的文本元素的对比率 - 辅助功能参考|Microsoft Docs"  
[DevtoolsCssReferenceChangeCss]: /microsoft-edge/devtools-guide-chromium/css/reference#change-css "更改 CSS - CSS |Microsoft Docs"  
[DevtoolsCustomizeIndexSettings]: /microsoft-edge/devtools-guide-chromium/customize/index#settings "设置 - 自定义 Microsoft Edge DevTools | Microsoft Docs"  
[DevtoolsCustomizeShortcuts]: microsoft-edge/devtools-guide-chromium/customize/shortcuts "自定义 Microsoft Edge DevTools 工具中的键盘|Microsoft Docs"  
[DevtoolsDeviceModeDualScreenFoldablesTestingFoldableDualScreenDevices]: /microsoft-edge/devtools-guide-chromium/device-mode/dual-screen-and-foldables#testing-on-foldable-and-dual-screen-devices "在可折叠和双屏幕设备上进行测试 - 在 Microsoft Edge DevTools 设备上模拟双屏幕和可折叠|Microsoft Docs"  
[DevtoolsDeviceModeIndex]: /microsoft-edge/devtools-guide-chromium/device-mode/index "在 Microsoft Edge DevTools 中模拟移动设备 | Microsoft Docs"  
[DevtoolsDeviceModeIndexSimulateMobileViewport]: /microsoft-edge/devtools-guide-chromium/device-mode/index#simulate-a-mobile-viewport "模拟移动视区 - 模拟 Microsoft Edge DevTools |Microsoft Docs"  
[DevtoolsEvaluatePerformanceReferenceRecordLoadPerformance]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference#record-load-performance "记录负载性能 - 性能分析|Microsoft Docs"  
[DevtoolsInspectStylesEditFonts]: /microsoft-edge/devtools-guide-chromium/inspect-styles/edit-fonts "在 DevTools | 中的"样式"窗格中编辑 CSS 字体样式和|Microsoft Docs"  
[DevtoolsMain]: /microsoft-edge/devtools-guide-chromium/index "Microsoft Edge (Chromium) 开发人员工具概述|Microsoft Docs"  

[DualScreenIntroductionHowToWorkWithSeam]: /dual-screen/introduction#how-to-work-with-the-seam "如何使用设备 - 双屏幕设备应用|Microsoft Docs"  
[DualScreenWebCssMediaSpanning]: /dual-screen/web/css-media-spanning "用于双屏检测方法的 CSS 媒体屏幕跨越|Microsoft Docs"  
[DualScreenWebJavascriptGetwindowsegments]: /dual-screen/web/javascript-getwindowsegments "适用于双屏幕设备的 getWindowSegments JavaScript API |Microsoft Docs"  

[GithubMicrosoftedgeDevtoolssamplesWhatsNew89TargetCssDemoHtmlSection1]: https://microsoftedge.github.io/DevToolsSamples/whats-new/89/target-css-demo.html#section-1 "第 1 部分 - Microsoft Edge 89 (中的新增功能 CSS ：target) |GitHub"  
[GithubMicrosoftVscodeEdgeDevtools]: https://github.com/microsoft/vscode-edge-devtools "microsoft/vscode-edge-devtools |GitHub"  
[GithubMicrosoftVscodeEdgeDevtoolsPull229]: https://github.com/microsoft/vscode-edge-devtools/pull/229 "拉 229：在设置中实现下拉列表以更改主题|GitHub"  
[GithubMicrosoftVscodeEdgeDevtoolsPull233]: https://github.com/microsoft/vscode-edge-devtools/pull/233 "拉 233：将 Microsoft Edge 调试器作为依赖项|GitHub"  
[GithubMicrosoftVscodeEdgeDevtoolsPull235]: https://github.com/microsoft/vscode-edge-devtools/pull/235 "Pull 235：将 Edge DevTools 版本升级到 85.0.564.40 |GitHub"  
[GithubMicrosoftVscodeEdgeDevtoolsPull248]: https://github.com/microsoft/vscode-edge-devtools/pull/248 "拉 248：将单个关闭按钮添加到实例面板|GitHub"  
[GithubW3cSilverGuidelinesMethodsMethodFontCharacteristicContrastHtml]: https://w3c.github.io/silver/guidelines/methods/Method-font-characteristic-contrast.html "选择字体特征和背景颜色以提供足够的对比度，以便可读性|W3C"  
[GithubW3cWebappsecTrustedTypesDistSpec]: https://w3c.github.io/webappsec-trusted-types/dist/spec  "受信任类型|W3C"  

[MicrosoftSurfaceDevicesSurfaceDuo]: https://www.microsoft.com/surface/devices/surface-duo "新 Surface Duo |Microsoft"  

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download "Microsoft Edge 预览频道"  

[VisualstudioCodeDocsEditorExtensionGalleryUpdateExtensionManually]: https://code.visualstudio.com/docs/editor/extension-gallery#_update-an-extension-manually "手动更新扩展 - 扩展市场|Visual Studio 代码"  

[VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools]: https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools "Microsoft Edge 代码Visual Studio工具|Visual Studio Marketplace"  
[VisualstudioMarketplaceMsjsdiagDebuggerMicrosoftEdge]: https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge "适用于 Microsoft Edge |Visual Studio Marketplace"  

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium Bug"  
[CR978059]: https://crbug.com/978059 "问题 978059：在筛选 Cookie 时删除它们，删除所有 Cookie，而不只是删除筛选的|Chromium Bug"  
[CR997625]: https://crbug.com/997625 "问题 997625：新功能|需要查看 Cookie 中的 url 解码值的选项|Chromium Bug"  
[CR1003629]: https://crbug.com/1003629 "问题 1003629：捕获节点不再对折叠下方的节点进行屏幕截图。|Chromium Bug"  
[CR1012337]: https://crbug.com/1012337 "问题 1012337：清除网站数据会销毁非 Google 网站上 Google |Chromium Bug"  
[CR1028078]: https://crbug.com/1028078 "问题 1028078：联机和脱机在列表中彼此|Chromium Bug"  
[CR1054281]: https://crbug.com/1054281 "问题 1054281：功能请求：DevTools 应模拟可折叠和双屏幕设备|Chromium Bug"  
[CR1075865]: https://crbug.com/1075865 "问题 1075865：在开发工具时间线中显示丢弃|Chromium Bug"  
[CR1093229]: https://crbug.com/1093229 "问题 1093229：DevTools：提供专用的字样编辑器 UI |Chromium Bug"  
[CR1121900]: https://crbug.com/1121900 "问题 1121900：DevTools：根据新规范更新对比度计算|Chromium Bug"  
[CR1122507]: https://crbug.com/1122507 "问题 1122507：框架树视图中的 Surface 工作线程信息 | Chromium 漏洞"  
[CR1122580]: https://crbug.com/1122580 "问题 1122580：重载时无法禁用网络|Chromium Bug"  
[CR1136394]: https://crbug.com/1136394 "问题 1136394：Flexbox 工具 | Chromium 漏洞"  
[CR1139899]: https://crbug.com/1139899 "问题 1139899：在框架详细信息视图中报告封闭的 API 的可用性 | Chromium 漏洞"  
[CR1139949]: https://crbug.com/1139949 "问题 1139949：弹性框覆盖|Chromium Bug"  
[CR1147016]: https://crbug.com/1147016 "问题 1147016：颜色选取器不显示在 var () 函数中。|Chromium Bug"  
[CR1148353]: https://crbug.com/1148353 "问题 1148353：功能请求：从开发工具控制台控制台复制|Chromium Bug"  
[CR1149859]: https://crbug.com/1149859 "问题 1149859：[功能请求][控制台]将复制对象添加到剪贴板项到上下文菜单|Chromium Bug"  
[CR1150797]: https://crbug.com/1150797 "问题 1150797：在元素面板菜单中添加重复元素|Chromium Bug"  
[CR1152391]: https://crbug.com/1152391 "问题 1152391：支持将 CSS 上下文菜单复制到样式面板|Chromium Bug"  
[CR1155120]: https://crbug.com/1155120 "问题 1155120：[FR]支持复制文件名和行号|Chromium Bug"  
[CR1156628]: https://crbug.com/1156628 "问题 1156628：DevTools：添加对 ：target in force 元素状态功能|Chromium Bug"  
[CR1157329]: https://crbug.com/1157329 "问题 1157329：辅助功能 - 讲述人：讲述人不会在"样式"选项卡的"列表"中公布适用于代码的建议|Chromium Bug"  

[MdnDocsWebCssTarget]: https://developer.mozilla.org/docs/web/css/:target "：target |MDN"  

[SamsungUsMobileGalaxyFold]: https://www.samsung.com/us/mobile/galaxy-fold "百合|Samsung US"  

[W3cWaiWcag21QuickrefContrastEnhanced]: https://www.w3.org/WAI/WCAG21/quickref#contrast-enhanced "对比度 (增强) - 如何满足 WCAG (快速参考) |W3C"  
[W3cWaiWcag21QuickrefContrastMinimum]: https://www.w3.org/WAI/WCAG21/quickref#contrast-minimum "对比度 (最低) - 如何满足 WCAG (快速参考) |W3C"  

> [!NOTE]
> <span data-ttu-id="68abc-399">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="68abc-399">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="68abc-400">原始页面位于 [此处](https://developers.google.com/web/updates/2021/01/devtools/index)，并由 [Jecelyn Yeen][JecelynYeen] \（开发人员支持者，Chrome DevTools\）制作。</span><span class="sxs-lookup"><span data-stu-id="68abc-400">The original page is found [here](https://developers.google.com/web/updates/2021/01/devtools/index) and is authored by [Jecelyn Yeen][JecelynYeen] \(Developer advocate, Chrome DevTools\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="68abc-402">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="68abc-402">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen

[SpanningPlaceholder]: link-t-b-d "跨区占位符"  
