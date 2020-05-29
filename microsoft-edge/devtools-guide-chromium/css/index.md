---
title: 查看和更改 CSS 入门
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/27/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 85fceaa44b0143a82ca8f66ef8c63e1a9275dcd8
ms.sourcegitcommit: 5cdc1626d5581b79c0f2ac4ea62e7f1974ebfa57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2020
ms.locfileid: "10601815"
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





# <span data-ttu-id="d5b61-103">查看和更改 CSS 入门</span><span class="sxs-lookup"><span data-stu-id="d5b61-103">Get Started With Viewing And Changing CSS</span></span>   



<span data-ttu-id="d5b61-104">完成这些交互式教程，了解有关使用 Microsoft Edge DevTools 查看和更改页面的 CSS 的基础知识。</span><span class="sxs-lookup"><span data-stu-id="d5b61-104">Complete these interactive tutorials to learn the basics of viewing and changing the CSS for a page using Microsoft Edge DevTools.</span></span>  

## <span data-ttu-id="d5b61-105">打开 CSS 示例</span><span class="sxs-lookup"><span data-stu-id="d5b61-105">Open CSS Examples</span></span>  

1.  <span data-ttu-id="d5b61-106">保留 `Control` \ （Windows \）或 `Command` \ （macOS \），然后单击 " **CSS 示例**" 以在新窗口中打开。</span><span class="sxs-lookup"><span data-stu-id="d5b61-106">Hold `Control` \(Windows\) or `Command` \(macOS\) and click **CSS Examples** to open in a new window.</span></span>  
    
    [<span data-ttu-id="d5b61-107">CSS 示例</span><span class="sxs-lookup"><span data-stu-id="d5b61-107">CSS Examples</span></span>][GlitchDevToolsCssExamples]  

> [!NOTE]
> <span data-ttu-id="d5b61-108">如果要将[DevTools 窗口停靠][DevToolsCustomizePlacement]在视区的右侧 \ （如[图 1](#figure-1)\），请单击 "**自定义和控制 DevTools** " `...` 。</span><span class="sxs-lookup"><span data-stu-id="d5b61-108">If you want to [dock your DevTools window][DevToolsCustomizePlacement] to the right of your viewport \(displayed in [Figure 1](#figure-1)\), click **Customize and control DevTools** `...`.</span></span>  <span data-ttu-id="d5b61-109">在 "**自定义和控制 DevTools** " 下拉菜单的 "**停靠侧**" 部分中，选择 "**停靠到右侧**"。</span><span class="sxs-lookup"><span data-stu-id="d5b61-109">On the **Customize and control DevTools** drop-down menu, in the **Dock side** section, select **Dock to right**.</span></span>  
    
## <span data-ttu-id="d5b61-110">查看元素的 CSS</span><span class="sxs-lookup"><span data-stu-id="d5b61-110">View the CSS for an element</span></span>   

1.  <span data-ttu-id="d5b61-111">[打开 CSS 示例](#open-css-examples)。</span><span class="sxs-lookup"><span data-stu-id="d5b61-111">[Open CSS Examples](#open-css-examples).</span></span>  
1.  <span data-ttu-id="d5b61-112">右键单击 `Inspect Me!` 文本，然后选择 "**检查**"。</span><span class="sxs-lookup"><span data-stu-id="d5b61-112">Right-click the `Inspect Me!` text and select **Inspect**.</span></span>  
    1.  <span data-ttu-id="d5b61-113">在 DevTools 中，在 "**元素**" 面板上的 " **DOM 树**" 选项卡中 `Inspect Me!` 突出显示该元素。</span><span class="sxs-lookup"><span data-stu-id="d5b61-113">In DevTools, on the **Elements** panel, in the **DOM Tree** tab, the `Inspect Me!` element is highlighted.</span></span>  
        
        > ##### <span data-ttu-id="d5b61-114">图 1</span><span class="sxs-lookup"><span data-stu-id="d5b61-114">Figure 1</span></span>  
        > <span data-ttu-id="d5b61-115">在**DOM 树**中突出显示已检查的元素</span><span class="sxs-lookup"><span data-stu-id="d5b61-115">The inspected element is highlighted in the **DOM Tree**</span></span>  
        > ![在 DOM 树中突出显示已检查的元素][ImageInspect]  
        
    1.  <span data-ttu-id="d5b61-117">在 `Inspect Me!` 元素中，找到属性的值 `data-message` 并复制它。</span><span class="sxs-lookup"><span data-stu-id="d5b61-117">In the `Inspect Me!` element, find the value of the `data-message` attribute and copy it.</span></span>  
1.  <span data-ttu-id="d5b61-118">在页面上的 "**值 `data-message` ：** " 文本框中，输入值。</span><span class="sxs-lookup"><span data-stu-id="d5b61-118">On the page, in the **Value of `data-message`:** textbox, enter the value.</span></span>  
1.  <span data-ttu-id="d5b61-119">右键单击 `Inspect Me!` 文本，然后选择 "**检查**"。</span><span class="sxs-lookup"><span data-stu-id="d5b61-119">Right-click the `Inspect Me!` text and select **Inspect**.</span></span>  
    
    1.  <span data-ttu-id="d5b61-120">在 DevTools 中的 "**元素**" 面板上，选择 "**样式**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="d5b61-120">In DevTools, on the **Elements** panel, select the **Styles** tab.</span></span>  
    1.  <span data-ttu-id="d5b61-121">在 "**样式**" 选项卡中， `Inspect Me!` 突出显示该元素。</span><span class="sxs-lookup"><span data-stu-id="d5b61-121">In the **Styles** tab, the `Inspect Me!` element is highlighted.</span></span>  
    1.  <span data-ttu-id="d5b61-122">在 `Inspect Me!` 元素中，找到 " `aloha` 类规则"。</span><span class="sxs-lookup"><span data-stu-id="d5b61-122">In the `Inspect Me!` element, find the `aloha` class rule.</span></span>  
        
        > [!NOTE]
        > <span data-ttu-id="d5b61-123">你将看到此规则，因为它应用于该 `Inspect Me!` 元素。</span><span class="sxs-lookup"><span data-stu-id="d5b61-123">You see this rule because it is being applied to the `Inspect Me!` element.</span></span>  
        
    1.  <span data-ttu-id="d5b61-124">在 `aloha` 类中，查找样式的值 `padding` 并复制它。</span><span class="sxs-lookup"><span data-stu-id="d5b61-124">In the `aloha` class, find the value for the `padding` style and copy it.</span></span>  
        
        > ##### <span data-ttu-id="d5b61-125">图 2</span><span class="sxs-lookup"><span data-stu-id="d5b61-125">Figure 2</span></span>  
        > <span data-ttu-id="d5b61-126">应用于所选元素的 CSS 类（如 `aloha` ）将显示在 "**样式**" 选项卡中</span><span class="sxs-lookup"><span data-stu-id="d5b61-126">CSS classes being applied to the selected element, such as `aloha`, are displayed in the **Styles** tab</span></span>  
        > ![应用于已检查元素的 CSS 类在 "样式" 选项卡中突出显示][ImageAloha]  
        
1.  <span data-ttu-id="d5b61-128">在页面上的 "**值 `padding` ：** " 文本框中，输入值。</span><span class="sxs-lookup"><span data-stu-id="d5b61-128">On the page, in the **Value of `padding`:** textbox, enter the value.</span></span>  

## <span data-ttu-id="d5b61-129">向元素添加 CSS 声明</span><span class="sxs-lookup"><span data-stu-id="d5b61-129">Add a CSS declaration to an element</span></span>   

<span data-ttu-id="d5b61-130">当你想要将 CSS 声明更改或添加到元素时，请使用 "**样式**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="d5b61-130">Use the **Styles** tab when you want to change or add CSS declarations to an element.</span></span>  

> [!NOTE]
> <span data-ttu-id="d5b61-131">在执行此操作之前，请先完成[查看元素教程的 CSS](#view-the-css-for-an-element) 。</span><span class="sxs-lookup"><span data-stu-id="d5b61-131">Complete the [View the CSS for an element](#view-the-css-for-an-element) tutorial before doing this one.</span></span>  

1.  <span data-ttu-id="d5b61-132">[打开 CSS 示例](#open-css-examples)。</span><span class="sxs-lookup"><span data-stu-id="d5b61-132">[Open CSS Examples](#open-css-examples).</span></span>  
1.  <span data-ttu-id="d5b61-133">右键单击 `Add A Background Color To Me!` 文本，然后选择 "**检查**"。</span><span class="sxs-lookup"><span data-stu-id="d5b61-133">Right-click the `Add A Background Color To Me!` text and select **Inspect**.</span></span>  
1.  <span data-ttu-id="d5b61-134">单击 `element.style` "**样式**" 选项卡顶部附近的。</span><span class="sxs-lookup"><span data-stu-id="d5b61-134">Click `element.style` near the top of the **Styles** tab.</span></span>  
1.  <span data-ttu-id="d5b61-135">键入 `background-color` ，然后按 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="d5b61-135">Type `background-color` and press `Enter`.</span></span>  
1.  <span data-ttu-id="d5b61-136">键入 `honeydew` ，然后按 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="d5b61-136">Type `honeydew` and press `Enter`.</span></span>  <span data-ttu-id="d5b61-137">在**DOM 树**中，应看到已对元素应用了内联样式声明。</span><span class="sxs-lookup"><span data-stu-id="d5b61-137">In the **DOM Tree** you should see that an inline style declaration was applied to the element.</span></span>  

> ##### <span data-ttu-id="d5b61-138">图 3</span><span class="sxs-lookup"><span data-stu-id="d5b61-138">Figure 3</span></span>  
> <span data-ttu-id="d5b61-139">已 `background-color:honeydew` 使用 `element.style` "**样式**" 选项卡部分将声明应用到元素</span><span class="sxs-lookup"><span data-stu-id="d5b61-139">The `background-color:honeydew` declaration has been applied to the element using the `element.style` section of the **Styles** tab</span></span>  
> ![使用 "样式" 选项卡将 CSS 声明添加到元素][ImageDeclaration]  

## <span data-ttu-id="d5b61-141">向元素添加 CSS 类</span><span class="sxs-lookup"><span data-stu-id="d5b61-141">Add a CSS class to an element</span></span>   

<span data-ttu-id="d5b61-142">使用 "**样式**" 选项卡查看在将 CSS 类应用到元素或从元素中删除时元素的外观。</span><span class="sxs-lookup"><span data-stu-id="d5b61-142">Use the **Styles** tab to see how an element looks when a CSS class is applied to or removed from an element.</span></span>  

> [!NOTE]
> <span data-ttu-id="d5b61-143">在执行此操作之前，请先完成[查看元素教程的 CSS](#view-the-css-for-an-element) 。</span><span class="sxs-lookup"><span data-stu-id="d5b61-143">Complete the [View the CSS for an element](#view-the-css-for-an-element) tutorial before doing this one.</span></span>  

1.  <span data-ttu-id="d5b61-144">[打开 CSS 示例](#open-css-examples)。</span><span class="sxs-lookup"><span data-stu-id="d5b61-144">[Open CSS Examples](#open-css-examples).</span></span>  
1.  <span data-ttu-id="d5b61-145">右键单击该 `Add A Class To Me!` 元素，然后选择 "**检查**"。</span><span class="sxs-lookup"><span data-stu-id="d5b61-145">Right-click the `Add A Class To Me!` element and select **Inspect**.</span></span>  
1.  <span data-ttu-id="d5b61-146">单击 " **. cls**。</span><span class="sxs-lookup"><span data-stu-id="d5b61-146">Click **.cls**.</span></span>  <span data-ttu-id="d5b61-147">DevTools 将显示一个文本框，你可以在其中将类添加到所选元素。</span><span class="sxs-lookup"><span data-stu-id="d5b61-147">DevTools reveals a text box where you may add classes to the selected element.</span></span>  
1.  <span data-ttu-id="d5b61-148">`color_me`在 "**添加新类**" 文本框中键入，然后按 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="d5b61-148">Type `color_me` in the **Add new class** text box and then press `Enter`.</span></span>  <span data-ttu-id="d5b61-149">"**添加新类**" 文本框下方将显示一个复选框，您可以在其中打开和关闭类。</span><span class="sxs-lookup"><span data-stu-id="d5b61-149">A checkbox appears below the **Add new class** text box, where you may toggle the class on and off.</span></span>  <span data-ttu-id="d5b61-150">如果 `Add A Class To Me!` 元素应用了任何其他类，你也可以在此处进行切换。</span><span class="sxs-lookup"><span data-stu-id="d5b61-150">If the `Add A Class To Me!` element has any other classes applied to it, you are also able to toggle each from here.</span></span>  

> ##### <span data-ttu-id="d5b61-151">图 4</span><span class="sxs-lookup"><span data-stu-id="d5b61-151">Figure 4</span></span>  
> <span data-ttu-id="d5b61-152">`color_me`该类已使用 "**样式**" 选项卡的 " **cls** " 部分应用于元素</span><span class="sxs-lookup"><span data-stu-id="d5b61-152">The `color_me` class has been applied to the element using the **.cls** section of the **Styles** tab</span></span>  
> ![将 color_me 类应用于元素][ImageApplyClass]  

## <span data-ttu-id="d5b61-154">向类添加伪状态</span><span class="sxs-lookup"><span data-stu-id="d5b61-154">Add a pseudostate to a class</span></span>   

<span data-ttu-id="d5b61-155">使用 "**样式**" 选项卡将 CSS 伪状态永久应用到元素。</span><span class="sxs-lookup"><span data-stu-id="d5b61-155">Use the **Styles** tab to permanently apply a CSS pseudostate to an element.</span></span>  <span data-ttu-id="d5b61-156">DevTools 支持 `:active` 、 `:focus` 、 `:hover` 和 `:visited` 。</span><span class="sxs-lookup"><span data-stu-id="d5b61-156">DevTools supports `:active`, `:focus`, `:hover`, and `:visited`.</span></span>  

> [!NOTE]
> <span data-ttu-id="d5b61-157">在执行此操作之前，请先完成[查看元素教程的 CSS](#view-the-css-for-an-element) 。</span><span class="sxs-lookup"><span data-stu-id="d5b61-157">Complete the [View the CSS for an element](#view-the-css-for-an-element) tutorial before doing this one.</span></span>  

1.  <span data-ttu-id="d5b61-158">[打开 CSS 示例](#open-css-examples)。</span><span class="sxs-lookup"><span data-stu-id="d5b61-158">[Open CSS Examples](#open-css-examples).</span></span>  
1.  <span data-ttu-id="d5b61-159">将鼠标悬停在 `Hover Over Me!` 文本上。</span><span class="sxs-lookup"><span data-stu-id="d5b61-159">Hover over the `Hover Over Me!` text.</span></span>  <span data-ttu-id="d5b61-160">背景色更改。</span><span class="sxs-lookup"><span data-stu-id="d5b61-160">The background color changes.</span></span>  
1.  <span data-ttu-id="d5b61-161">右键单击 `Hover Over Me!` 文本，然后选择 "**检查**"。</span><span class="sxs-lookup"><span data-stu-id="d5b61-161">Right-click the `Hover Over Me!` text and select **Inspect**.</span></span>  
1.  <span data-ttu-id="d5b61-162">在 "**样式**" 选项卡中，单击 **： hov**。</span><span class="sxs-lookup"><span data-stu-id="d5b61-162">In the **Styles** tab, click **:hov**.</span></span>  
1.  <span data-ttu-id="d5b61-163">选中 **： "悬停**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="d5b61-163">Check the **:hover** checkbox.</span></span>  <span data-ttu-id="d5b61-164">背景色会像以前一样更改，即使你实际上不是悬停在该元素上也是如此。</span><span class="sxs-lookup"><span data-stu-id="d5b61-164">The background color changes like before, even though you are not actually hovering over the element.</span></span>  

> ##### <span data-ttu-id="d5b61-165">图 5</span><span class="sxs-lookup"><span data-stu-id="d5b61-165">Figure 5</span></span>  
> <span data-ttu-id="d5b61-166">`:hover`在元素上切换伪状态</span><span class="sxs-lookup"><span data-stu-id="d5b61-166">Toggling the `:hover` pseudostate on an element</span></span>  
> ![切换元素上的悬停伪状态][ImageSetHover]  

## <span data-ttu-id="d5b61-168">更改元素的尺寸</span><span class="sxs-lookup"><span data-stu-id="d5b61-168">Change the dimensions of an element</span></span>   

<span data-ttu-id="d5b61-169">使用 "**样式**" 选项卡中的 **"方框模型**" 交互式图表更改元素的宽度、高度、填充、边距或边框长度。</span><span class="sxs-lookup"><span data-stu-id="d5b61-169">Use the **Box Model** interactive diagram in the **Styles** tab to change the width, height, padding, margin, or border length of an element.</span></span>  

> [!NOTE]
> <span data-ttu-id="d5b61-170">在执行此操作之前，请先完成[查看元素教程的 CSS](#view-the-css-for-an-element) 。</span><span class="sxs-lookup"><span data-stu-id="d5b61-170">Complete the [View the CSS for an element](#view-the-css-for-an-element) tutorial before doing this one.</span></span>  

1.  <span data-ttu-id="d5b61-171">[打开 CSS 示例](#open-css-examples)。</span><span class="sxs-lookup"><span data-stu-id="d5b61-171">[Open CSS Examples](#open-css-examples).</span></span>  
1.  <span data-ttu-id="d5b61-172">右键单击该 `Change My Margin!` 元素，然后选择 "**检查**"。</span><span class="sxs-lookup"><span data-stu-id="d5b61-172">Right-click the `Change My Margin!` element and select **Inspect**.</span></span>  
1.  <span data-ttu-id="d5b61-173">在 "**样式**" 选项卡中的 "**方框模型**" 图表中，将鼠标悬停在**填充**上。</span><span class="sxs-lookup"><span data-stu-id="d5b61-173">In the **Box Model** diagram in the **Styles** tab, hover over **padding**.</span></span>  <span data-ttu-id="d5b61-174">元素的填充在视区中突出显示。</span><span class="sxs-lookup"><span data-stu-id="d5b61-174">The padding of an element is highlighted in the viewport.</span></span>  

    > [!NOTE]
    > <span data-ttu-id="d5b61-175">根据 DevTools 窗口的大小，可能需要滚动到 "**样式**" 选项卡底部才能看到 "**方框模型**"。</span><span class="sxs-lookup"><span data-stu-id="d5b61-175">Depending on the size of your DevTools window, you may need to scroll to the bottom of the **Styles** tab to see the **Box Model**.</span></span>  

1.  <span data-ttu-id="d5b61-176">双击**框模型**中的左边距，它当前具有 `-` 表示元素没有左边距的值。</span><span class="sxs-lookup"><span data-stu-id="d5b61-176">Double-click the left margin in the **Box Model**, which currently has a value of `-` meaning that the element does not have a left-margin.</span></span>  
1.  <span data-ttu-id="d5b61-177">键入 `100px` ，然后按 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="d5b61-177">Type `100px` and press `Enter`.</span></span>  <span data-ttu-id="d5b61-178">**Box 模型**默认为像素，但它还接受其他值，如 `25%` 或 `10vw` 。</span><span class="sxs-lookup"><span data-stu-id="d5b61-178">The **Box Model** defaults to pixels, but it also accepts other values, such as `25%`, or `10vw`.</span></span>  

> ##### <span data-ttu-id="d5b61-179">图 6</span><span class="sxs-lookup"><span data-stu-id="d5b61-179">Figure 6</span></span>  
> <span data-ttu-id="d5b61-180">将鼠标悬停在元素的填充上</span><span class="sxs-lookup"><span data-stu-id="d5b61-180">Hovering over the padding of the element</span></span>  
> ![将鼠标悬停在元素的填充上][ImageShowPadding]  

> ##### <span data-ttu-id="d5b61-182">图 7</span><span class="sxs-lookup"><span data-stu-id="d5b61-182">Figure 7</span></span>  
> <span data-ttu-id="d5b61-183">更改元素的左边距</span><span class="sxs-lookup"><span data-stu-id="d5b61-183">Changing the left-margin of the element</span></span>  
> ![更改元素的左边距][ImageChangeMargin]  

 



<!-- image links -->  

[ImageInspect]: /microsoft-edge/devtools-guide-chromium/media/css-elements-inspect-me.msft.png "图1：在 DOM 树中突出显示已检查的元素"  
[ImageAloha]: /microsoft-edge/devtools-guide-chromium/media/css-elements-inspect-me-styles.msft.png "图2：应用到已检查元素的 CSS 类在 "样式" 选项卡中突出显示"  
[ImageDeclaration]: /microsoft-edge/devtools-guide-chromium/media/css-elements-add-background-color-to-me-styles-p.msft.png "图3：使用 "样式" 选项卡将 CSS 声明添加到元素"  
[ImageApplyClass]: /microsoft-edge/devtools-guide-chromium/media/css-elements-add-a-class-to-me-styles-cls.msft.png "图4：将 color_me 类应用到元素"  
[ImageSetHover]: /microsoft-edge/devtools-guide-chromium/media/css-elements-hover-over-me-styles-hov-hover.msft.png "图5：切换元素上的悬停伪状态"  
[ImageShowPadding]: /microsoft-edge/devtools-guide-chromium/media/css-elements-change-my-margin-styles-padding.msft.png "图6：将鼠标悬停在元素的填充上"  
[ImageChangeMargin]: /microsoft-edge/devtools-guide-chromium/media/css-elements-change-my-margin-styles-margin-edit.msft.png "图7：更改元素的左边距"  

<!-- links -->  

[DevToolsCustomizePlacement]: /microsoft-edge/devtools-guide-chromium/customize/placement "更改 Microsoft Edge DevTools 位置（"取消停靠"、"停靠到底部"、"停靠到左侧"）"  

[GlitchDevToolsCssExamples]: https://microsoft-edge-chromium-devtools.glitch.me/static/css/examples/ecma.html "CSS 示例-Microsoft Edge （Chromium） DevTools |故障"  

> [!NOTE]
> <span data-ttu-id="d5b61-194">此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="d5b61-194">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="d5b61-195">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/css/index)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools \ & Lighthouse \）创作。</span><span class="sxs-lookup"><span data-stu-id="d5b61-195">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/css/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
<span data-ttu-id="d5b61-197">此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="d5b61-197">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
