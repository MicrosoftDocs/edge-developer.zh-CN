---
description: 了解如何使用 Microsoft Edge DevTools 查看和更改页面的 CSS。
title: 查看和更改 CSS 入门
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: f055606ff6140652341627097e7fe7b270dc929c
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993063"
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

# <span data-ttu-id="3a9fc-104">查看和更改 CSS 入门</span><span class="sxs-lookup"><span data-stu-id="3a9fc-104">Get Started With Viewing And Changing CSS</span></span>  

<span data-ttu-id="3a9fc-105">完成这些交互式教程，了解有关使用 Microsoft Edge DevTools 查看和更改页面的 CSS 的基础知识。</span><span class="sxs-lookup"><span data-stu-id="3a9fc-105">Complete these interactive tutorials to learn the basics of viewing and changing the CSS for a page using Microsoft Edge DevTools.</span></span>  

## <span data-ttu-id="3a9fc-106">打开 CSS 示例</span><span class="sxs-lookup"><span data-stu-id="3a9fc-106">Open CSS Examples</span></span>  

1.  <span data-ttu-id="3a9fc-107">保留 `Control` \ (Windows \ ) 或 `Command` \ (macOS \ ) 并选择 " **CSS 示例** " 以在新窗口中打开。</span><span class="sxs-lookup"><span data-stu-id="3a9fc-107">Hold `Control` \(Windows\) or `Command` \(macOS\) and select **CSS Examples** to open in a new window.</span></span>  
    
    [<span data-ttu-id="3a9fc-108">CSS 示例</span><span class="sxs-lookup"><span data-stu-id="3a9fc-108">CSS Examples</span></span>][GlitchDevToolsCssExamples]  
    
    > [!NOTE]
    > <span data-ttu-id="3a9fc-109">如果要将 [DevTools 窗口停靠在][DevToolsCustomizePlacement] 的 (右侧，如下图 \ ) 中所示，请选择 " **自定义和控制 DevTools** " `...` 。</span><span class="sxs-lookup"><span data-stu-id="3a9fc-109">If you want to [dock your DevTools window][DevToolsCustomizePlacement] to the right of your viewport \(displayed in the following figure\), select **Customize and control DevTools** `...`.</span></span>  <span data-ttu-id="3a9fc-110">在 " **自定义和控制 DevTools** " 下拉菜单的 " **停靠侧** " 部分中，选择 " **停靠到右侧**"。</span><span class="sxs-lookup"><span data-stu-id="3a9fc-110">On the **Customize and control DevTools** drop-down menu, in the **Dock side** section, select **Dock to right**.</span></span>  
    
## <span data-ttu-id="3a9fc-111">查看元素的 CSS</span><span class="sxs-lookup"><span data-stu-id="3a9fc-111">View the CSS for an element</span></span>  

1.  <span data-ttu-id="3a9fc-112">[打开 CSS 示例](#open-css-examples)。</span><span class="sxs-lookup"><span data-stu-id="3a9fc-112">[Open CSS Examples](#open-css-examples).</span></span>  
1.  <span data-ttu-id="3a9fc-113">将鼠标悬停在 `Inspect Me!` 文本上，打开上下文菜单 \ (右键单击 "\ ) "，然后选择 " **检查**"。</span><span class="sxs-lookup"><span data-stu-id="3a9fc-113">Hover on the `Inspect Me!` text, open the contextual menu \(right-click\), and select **Inspect**.</span></span>  
    1.  <span data-ttu-id="3a9fc-114">在 DevTools 中，在 " **元素** " 面板上的 " **DOM 树** " 选项卡中 `Inspect Me!` 突出显示该元素。</span><span class="sxs-lookup"><span data-stu-id="3a9fc-114">In DevTools, on the **Elements** panel, in the **DOM Tree** tab, the `Inspect Me!` element is highlighted.</span></span>  
        
        :::image type="complex" source="../media/css-elements-inspect-me.msft.png" alt-text="在 DOM 树中突出显示已检查的元素" lightbox="../media/css-elements-inspect-me.msft.png":::
           <span data-ttu-id="3a9fc-116">图1：在**DOM 树**中突出显示已检查的元素</span><span class="sxs-lookup"><span data-stu-id="3a9fc-116">Figure 1:  The inspected element is highlighted in the **DOM Tree**</span></span>  
        :::image-end:::  
        
    1.  <span data-ttu-id="3a9fc-117">在 `Inspect Me!` 元素中，找到属性的值 `data-message` 并复制它。</span><span class="sxs-lookup"><span data-stu-id="3a9fc-117">In the `Inspect Me!` element, find the value of the `data-message` attribute and copy it.</span></span>  
1.  <span data-ttu-id="3a9fc-118">在页面上的 " **值 `data-message` ：** " 文本框中，输入值。</span><span class="sxs-lookup"><span data-stu-id="3a9fc-118">On the page, in the **Value of `data-message`:** textbox, enter the value.</span></span>  
1.  <span data-ttu-id="3a9fc-119">将鼠标悬停在 `Inspect Me!` 文本上，打开上下文菜单 \ (右键单击 "\ ) "，然后选择 " **检查**"。</span><span class="sxs-lookup"><span data-stu-id="3a9fc-119">Hover on the `Inspect Me!` text, open the contextual menu \(right-click\), and select **Inspect**.</span></span>  
    1.  <span data-ttu-id="3a9fc-120">在 DevTools 中的 " **元素** " 面板上，选择 " **样式** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="3a9fc-120">In DevTools, on the **Elements** panel, select the **Styles** tab.</span></span>  
    1.  <span data-ttu-id="3a9fc-121">在 " **样式** " 选项卡中， `Inspect Me!` 突出显示该元素。</span><span class="sxs-lookup"><span data-stu-id="3a9fc-121">In the **Styles** tab, the `Inspect Me!` element is highlighted.</span></span>  
    1.  <span data-ttu-id="3a9fc-122">在 `Inspect Me!` 元素中，找到 " `aloha` 类规则"。</span><span class="sxs-lookup"><span data-stu-id="3a9fc-122">In the `Inspect Me!` element, find the `aloha` class rule.</span></span>  
        
        > [!NOTE]
        > <span data-ttu-id="3a9fc-123">你将看到此规则，因为它应用于该 `Inspect Me!` 元素。</span><span class="sxs-lookup"><span data-stu-id="3a9fc-123">You see this rule because it is being applied to the `Inspect Me!` element.</span></span>  
        
    1.  <span data-ttu-id="3a9fc-124">在 `aloha` 类中，查找样式的值 `padding` 并复制它。</span><span class="sxs-lookup"><span data-stu-id="3a9fc-124">In the `aloha` class, find the value for the `padding` style and copy it.</span></span>  
        
        :::image type="complex" source="../media/css-elements-inspect-me-styles.msft.png" alt-text="应用于已检查元素的 CSS 类在 "样式" 选项卡中突出显示" lightbox="../media/css-elements-inspect-me-styles.msft.png":::
           <span data-ttu-id="3a9fc-126">图2：应用到所选元素（如）的 CSS 类 `aloha` 显示在 " **样式** " 选项卡中</span><span class="sxs-lookup"><span data-stu-id="3a9fc-126">Figure 2:  CSS classes being applied to the selected element, such as `aloha`, are displayed in the **Styles** tab</span></span>  
        :::image-end:::  
        
1.  <span data-ttu-id="3a9fc-127">在页面上的 " **值 `padding` ：** " 文本框中，输入值。</span><span class="sxs-lookup"><span data-stu-id="3a9fc-127">On the page, in the **Value of `padding`:** textbox, enter the value.</span></span>  

## <span data-ttu-id="3a9fc-128">向元素添加 CSS 声明</span><span class="sxs-lookup"><span data-stu-id="3a9fc-128">Add a CSS declaration to an element</span></span>  

<span data-ttu-id="3a9fc-129">当你想要将 CSS 声明更改或添加到元素时，请使用 " **样式** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="3a9fc-129">Use the **Styles** tab when you want to change or add CSS declarations to an element.</span></span>  

> [!NOTE]
> <span data-ttu-id="3a9fc-130">在执行此操作之前，请先完成 [查看元素教程的 CSS](#view-the-css-for-an-element) 。</span><span class="sxs-lookup"><span data-stu-id="3a9fc-130">Complete the [View the CSS for an element](#view-the-css-for-an-element) tutorial before doing this one.</span></span>  

1.  <span data-ttu-id="3a9fc-131">[打开 CSS 示例](#open-css-examples)。</span><span class="sxs-lookup"><span data-stu-id="3a9fc-131">[Open CSS Examples](#open-css-examples).</span></span>  
1.  <span data-ttu-id="3a9fc-132">将鼠标悬停在 `Add A Background Color To Me!` 文本上，打开上下文菜单 \ (右键单击 "\ ) "，然后选择 " **检查**"。</span><span class="sxs-lookup"><span data-stu-id="3a9fc-132">Hover on the `Add A Background Color To Me!` text, open the contextual menu \(right-click\), and select **Inspect**.</span></span>  
1.  <span data-ttu-id="3a9fc-133">选择 `element.style` " **样式** " 选项卡顶部附近的。</span><span class="sxs-lookup"><span data-stu-id="3a9fc-133">Select `element.style` near the top of the **Styles** tab.</span></span>  
1.  <span data-ttu-id="3a9fc-134">键入 `background-color` ，然后按 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="3a9fc-134">Type `background-color` and press `Enter`.</span></span>  
1.  <span data-ttu-id="3a9fc-135">键入 `honeydew` ，然后按 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="3a9fc-135">Type `honeydew` and press `Enter`.</span></span>  <span data-ttu-id="3a9fc-136">在 **DOM 树** 中，应看到已对元素应用了内联样式声明。</span><span class="sxs-lookup"><span data-stu-id="3a9fc-136">In the **DOM Tree** you should see that an inline style declaration was applied to the element.</span></span>  
    
    :::image type="complex" source="../media/css-elements-add-background-color-to-me-styles-p.msft.png" alt-text="使用 "样式" 选项卡将 CSS 声明添加到元素" lightbox="../media/css-elements-add-background-color-to-me-styles-p.msft.png":::
       <span data-ttu-id="3a9fc-138">图3： `background-color:honeydew` 使用 `element.style` " **样式** " 选项卡部分对元素应用了声明</span><span class="sxs-lookup"><span data-stu-id="3a9fc-138">Figure 3:  The `background-color:honeydew` declaration has been applied to the element using the `element.style` section of the **Styles** tab</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="3a9fc-139">向元素添加 CSS 类</span><span class="sxs-lookup"><span data-stu-id="3a9fc-139">Add a CSS class to an element</span></span>  

<span data-ttu-id="3a9fc-140">使用 " **样式** " 选项卡查看在将 CSS 类应用到元素或从元素中删除时元素的外观。</span><span class="sxs-lookup"><span data-stu-id="3a9fc-140">Use the **Styles** tab to see how an element looks when a CSS class is applied to or removed from an element.</span></span>  

> [!NOTE]
> <span data-ttu-id="3a9fc-141">在执行此操作之前，请先完成 [查看元素教程的 CSS](#view-the-css-for-an-element) 。</span><span class="sxs-lookup"><span data-stu-id="3a9fc-141">Complete the [View the CSS for an element](#view-the-css-for-an-element) tutorial before doing this one.</span></span>  

1.  <span data-ttu-id="3a9fc-142">[打开 CSS 示例](#open-css-examples)。</span><span class="sxs-lookup"><span data-stu-id="3a9fc-142">[Open CSS Examples](#open-css-examples).</span></span>  
1.  <span data-ttu-id="3a9fc-143">将鼠标悬停在 `Add A Class To Me!` 文本上，打开上下文菜单 \ (右键单击 "\ ) "，然后选择 " **检查**"。</span><span class="sxs-lookup"><span data-stu-id="3a9fc-143">Hover on the `Add A Class To Me!` text, open the contextual menu \(right-click\), and select **Inspect**.</span></span>  
1.  <span data-ttu-id="3a9fc-144">选择 **. cls**。</span><span class="sxs-lookup"><span data-stu-id="3a9fc-144">Select **.cls**.</span></span>  <span data-ttu-id="3a9fc-145">DevTools 将显示一个文本框，你可以在其中将类添加到所选元素。</span><span class="sxs-lookup"><span data-stu-id="3a9fc-145">DevTools reveals a text box where you may add classes to the selected element.</span></span>  
1.  <span data-ttu-id="3a9fc-146">`color_me`在 "**添加新类**" 文本框中键入，然后按 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="3a9fc-146">Type `color_me` in the **Add new class** text box and then press `Enter`.</span></span>  <span data-ttu-id="3a9fc-147">" **添加新类** " 文本框下方将显示一个复选框，您可以在其中打开和关闭类。</span><span class="sxs-lookup"><span data-stu-id="3a9fc-147">A checkbox appears below the **Add new class** text box, where you may toggle the class on and off.</span></span>  <span data-ttu-id="3a9fc-148">如果 `Add A Class To Me!` 元素应用了任何其他类，你也可以在此处进行切换。</span><span class="sxs-lookup"><span data-stu-id="3a9fc-148">If the `Add A Class To Me!` element has any other classes applied to it, you are also able to toggle each from here.</span></span>  
    
    :::image type="complex" source="../media/css-elements-add-a-class-to-me-styles-cls.msft.png" alt-text="将 color_me 类应用于元素" lightbox="../media/css-elements-add-a-class-to-me-styles-cls.msft.png":::
       <span data-ttu-id="3a9fc-150">图4： `color_me` 使用 "**样式**" 选项卡的 " **cls** " 部分将类应用于元素</span><span class="sxs-lookup"><span data-stu-id="3a9fc-150">Figure 4:  The `color_me` class has been applied to the element using the **.cls** section of the **Styles** tab</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="3a9fc-151">向类添加伪状态</span><span class="sxs-lookup"><span data-stu-id="3a9fc-151">Add a pseudostate to a class</span></span>  

<span data-ttu-id="3a9fc-152">使用 " **样式** " 选项卡将 CSS 伪状态永久应用到元素。</span><span class="sxs-lookup"><span data-stu-id="3a9fc-152">Use the **Styles** tab to permanently apply a CSS pseudostate to an element.</span></span>  <span data-ttu-id="3a9fc-153">DevTools 支持 `:active` 、 `:focus` 、 `:hover` 和 `:visited` 。</span><span class="sxs-lookup"><span data-stu-id="3a9fc-153">DevTools supports `:active`, `:focus`, `:hover`, and `:visited`.</span></span>  

> [!NOTE]
> <span data-ttu-id="3a9fc-154">在执行此操作之前，请先完成 [查看元素教程的 CSS](#view-the-css-for-an-element) 。</span><span class="sxs-lookup"><span data-stu-id="3a9fc-154">Complete the [View the CSS for an element](#view-the-css-for-an-element) tutorial before doing this one.</span></span>  

1.  <span data-ttu-id="3a9fc-155">[打开 CSS 示例](#open-css-examples)。</span><span class="sxs-lookup"><span data-stu-id="3a9fc-155">[Open CSS Examples](#open-css-examples).</span></span>  
1.  <span data-ttu-id="3a9fc-156">将鼠标悬停在 `Hover Over Me!` 文本上。</span><span class="sxs-lookup"><span data-stu-id="3a9fc-156">Hover over the `Hover Over Me!` text.</span></span>  <span data-ttu-id="3a9fc-157">背景色更改。</span><span class="sxs-lookup"><span data-stu-id="3a9fc-157">The background color changes.</span></span>  
1.  <span data-ttu-id="3a9fc-158">将鼠标悬停在 `Hover Over Me!` 文本上，打开上下文菜单 \ (右键单击 "\ ) "，然后选择 " **检查**"。</span><span class="sxs-lookup"><span data-stu-id="3a9fc-158">Hover on the `Hover Over Me!` text, open the contextual menu \(right-click\), and select **Inspect**.</span></span>  
1.  <span data-ttu-id="3a9fc-159">在 " **样式** " 选项卡中，选择 **： hov**。</span><span class="sxs-lookup"><span data-stu-id="3a9fc-159">In the **Styles** tab, select **:hov**.</span></span>  
1.  <span data-ttu-id="3a9fc-160">选中 **： "悬停** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="3a9fc-160">Check the **:hover** checkbox.</span></span>  <span data-ttu-id="3a9fc-161">背景色会像以前一样更改，即使你实际上不是悬停在该元素上也是如此。</span><span class="sxs-lookup"><span data-stu-id="3a9fc-161">The background color changes like before, even though you are not actually hovering over the element.</span></span>  
    
    :::image type="complex" source="../media/css-elements-hover-over-me-styles-hov-hover.msft.png" alt-text="切换元素上的悬停伪状态" lightbox="../media/css-elements-hover-over-me-styles-hov-hover.msft.png":::
       <span data-ttu-id="3a9fc-163">图5：切换 `:hover` 元素上的伪状态</span><span class="sxs-lookup"><span data-stu-id="3a9fc-163">Figure 5:  Toggling the `:hover` pseudostate on an element</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="3a9fc-164">更改元素的尺寸</span><span class="sxs-lookup"><span data-stu-id="3a9fc-164">Change the dimensions of an element</span></span>  

<span data-ttu-id="3a9fc-165">使用 "**样式**" 选项卡中的 **"方框模型**" 交互式图表更改元素的宽度、高度、填充、边距或边框长度。</span><span class="sxs-lookup"><span data-stu-id="3a9fc-165">Use the **Box Model** interactive diagram in the **Styles** tab to change the width, height, padding, margin, or border length of an element.</span></span>  

> [!NOTE]
> <span data-ttu-id="3a9fc-166">在执行此操作之前，请先完成 [查看元素教程的 CSS](#view-the-css-for-an-element) 。</span><span class="sxs-lookup"><span data-stu-id="3a9fc-166">Complete the [View the CSS for an element](#view-the-css-for-an-element) tutorial before doing this one.</span></span>  

1.  <span data-ttu-id="3a9fc-167">[打开 CSS 示例](#open-css-examples)。</span><span class="sxs-lookup"><span data-stu-id="3a9fc-167">[Open CSS Examples](#open-css-examples).</span></span>  
1.  <span data-ttu-id="3a9fc-168">将鼠标悬停在 `Change My Margin!` 文本上，打开上下文菜单 \ (右键单击 "\ ) "，然后选择 " **检查**"。</span><span class="sxs-lookup"><span data-stu-id="3a9fc-168">Hover on the `Change My Margin!` text, open the contextual menu \(right-click\), and select **Inspect**.</span></span>  
1.  <span data-ttu-id="3a9fc-169">在 "**样式**" 选项卡中的 "**方框模型**" 图表中，将鼠标悬停在**填充**上。</span><span class="sxs-lookup"><span data-stu-id="3a9fc-169">In the **Box Model** diagram in the **Styles** tab, hover over **padding**.</span></span>  <span data-ttu-id="3a9fc-170">元素的填充在视区中突出显示。</span><span class="sxs-lookup"><span data-stu-id="3a9fc-170">The padding of an element is highlighted in the viewport.</span></span>  

    > [!NOTE]
    > <span data-ttu-id="3a9fc-171">根据 DevTools 窗口的大小，可能需要滚动到 " **样式** " 选项卡底部才能看到 " **方框模型**"。</span><span class="sxs-lookup"><span data-stu-id="3a9fc-171">Depending on the size of your DevTools window, you may need to scroll to the bottom of the **Styles** tab to see the **Box Model**.</span></span>  

1.  <span data-ttu-id="3a9fc-172">双击 **框模型**中的左边距，它当前具有 `-` 表示元素没有左边距的值。</span><span class="sxs-lookup"><span data-stu-id="3a9fc-172">Double-click the left margin in the **Box Model**, which currently has a value of `-` meaning that the element does not have a left-margin.</span></span>  
1.  <span data-ttu-id="3a9fc-173">键入 `100px` ，然后按 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="3a9fc-173">Type `100px` and press `Enter`.</span></span>  <span data-ttu-id="3a9fc-174">**Box 模型**默认为像素，但它还接受其他值，如 `25%` 或 `10vw` 。</span><span class="sxs-lookup"><span data-stu-id="3a9fc-174">The **Box Model** defaults to pixels, but it also accepts other values, such as `25%`, or `10vw`.</span></span>  
    
    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/css-elements-change-my-margin-styles-padding.msft.png" alt-text="将鼠标悬停在元素的填充上" lightbox="../media/css-elements-change-my-margin-styles-padding.msft.png":::
             <span data-ttu-id="3a9fc-176">图6：将鼠标悬停在元素的填充上</span><span class="sxs-lookup"><span data-stu-id="3a9fc-176">Figure 6:  Hovering over the padding of the element</span></span>  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/css-elements-change-my-margin-styles-margin-edit.msft.png" alt-text="更改元素的左边距" lightbox="../media/css-elements-change-my-margin-styles-margin-edit.msft.png":::
             <span data-ttu-id="3a9fc-178">图7：更改元素的左边距</span><span class="sxs-lookup"><span data-stu-id="3a9fc-178">Figure 7:  Changing the left-margin of the element</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
## <span data-ttu-id="3a9fc-179">调试媒体查询</span><span class="sxs-lookup"><span data-stu-id="3a9fc-179">Debugging Media Queries</span></span>  

<span data-ttu-id="3a9fc-180">[媒体查询][MDNUsingMediaGueries] 是一种使 web 产品对每个用户的配置设置所做更改做出反应的方式。</span><span class="sxs-lookup"><span data-stu-id="3a9fc-180">[Media Queries][MDNUsingMediaGueries] are a way to make your web product react to changes in the configuration settings for each user.</span></span>  <span data-ttu-id="3a9fc-181">最重要的用例是根据视区的尺寸为你的产品提供不同的 CSS 布局。</span><span class="sxs-lookup"><span data-stu-id="3a9fc-181">The most significant use case is to provide your product a different CSS layout depending on the dimensions of the viewport.</span></span>  <span data-ttu-id="3a9fc-182">当有更多的屏幕空间时，使用单独的布局可为移动设备和多列布局提供一列式布局。</span><span class="sxs-lookup"><span data-stu-id="3a9fc-182">Using separate layouts allows for a one-column layout for mobile devices and multi-column layouts when there is more screen estate available.</span></span>  

<span data-ttu-id="3a9fc-183">如果要调试或测试在 CSS 中定义的媒体查询，请使用以下步骤。</span><span class="sxs-lookup"><span data-stu-id="3a9fc-183">If you want to debug or test the Media Queries you defined in your CSS, use the following steps.</span></span>  

1.  <span data-ttu-id="3a9fc-184">打开 "开发工具"，然后选择左上角的 "**切换设备" 工具栏**图标，或者按 `Ctrl` + `Shift` + `M` `Cmd` + `Shift` + `M` macOS \ ) 上的 \ (。</span><span class="sxs-lookup"><span data-stu-id="3a9fc-184">Open the developer tools and select the **Toggle device toolbar** icon second on the top-left, or press `Ctrl`+`Shift`+`M` \(`Cmd`+`Shift`+`M` on macOS\).</span></span>  
    
    :::image type="complex" source="../media/css-elements-media-queries-open-device-toolbar.msft.png" alt-text="打开设备工具栏" lightbox="../media/css-elements-media-queries-open-device-toolbar.msft.png":::
       <span data-ttu-id="3a9fc-186">图8：打开 "设备" 工具栏</span><span class="sxs-lookup"><span data-stu-id="3a9fc-186">Figure 8:  Opening the device toolbar</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="3a9fc-187">在 "设备" 工具栏打开的情况下，选择 `...` 右上角的菜单，然后选择 " **查看媒体查询**"。</span><span class="sxs-lookup"><span data-stu-id="3a9fc-187">With the device toolbar open, select the `...` menu on the top-right and select **View Media Queries**.</span></span>  <span data-ttu-id="3a9fc-188">您应在表示不同媒体查询的页面的显示上方看到颜色条。</span><span class="sxs-lookup"><span data-stu-id="3a9fc-188">You should see colored bars above the display of the page that represent the different media queries.</span></span>  
    
    :::image type="complex" source="../media/css-elements-media-queries-showing-mq.msft.png" alt-text="在 "设备" 工具栏中显示媒体查询" lightbox="../media/css-elements-media-queries-showing-mq.msft.png":::
       <span data-ttu-id="3a9fc-190">图9：在 "设备" 工具栏中显示媒体查询</span><span class="sxs-lookup"><span data-stu-id="3a9fc-190">Figure 9:  Showing Media Queries in Device Toolbar</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="3a9fc-191">将鼠标悬停在条形图上的边界上可查看不同媒体查询的值。</span><span class="sxs-lookup"><span data-stu-id="3a9fc-191">Hover over the boundaries in the bars to see the values of the different media queries.</span></span> <span data-ttu-id="3a9fc-192">选择 "每个" 以调整网页的大小以匹配。</span><span class="sxs-lookup"><span data-stu-id="3a9fc-192">Select each to resize the web page to match.</span></span>  
    
    :::image type="complex" source="../media/css-elements-media-queries-select-bar.msft.png" alt-text="从预览栏中选择媒体查询" lightbox="../media/css-elements-media-queries-select-bar.msft.png":::
       <span data-ttu-id="3a9fc-194">图10：从预览栏选择媒体查询</span><span class="sxs-lookup"><span data-stu-id="3a9fc-194">Figure 10:  Selecting Media Query from preview bar</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="3a9fc-195">若要调试媒体查询并在编辑器中打开 CSS 文件， `Sources` 请将鼠标悬停在任意条形图段上，打开上下文菜单 \ (右键单击 "\ ) "，然后选择 `reveal in source code` 。</span><span class="sxs-lookup"><span data-stu-id="3a9fc-195">To debug media queries and open the CSS file in the `Sources` editor; hover on any of the bar segments, open the contextual menu \(right-click\), and select `reveal in source code`.</span></span>  
    
    :::image type="complex" source="../media/css-elements-media-queries-reveal-in-sources.msft.png" alt-text="在源代码编辑器中泄漏媒体查询" lightbox="../media/css-elements-media-queries-reveal-in-sources.msft.png":::
       <span data-ttu-id="3a9fc-197">图11：在源代码编辑器中泄漏媒体查询</span><span class="sxs-lookup"><span data-stu-id="3a9fc-197">Figure 11:  Revealing Media Queries in Sources Editor</span></span>  
    :::image-end:::  
    
<!-- links -->  

[ DevToolsCustomizePlacement]: /microsoft-edge/devtools-guide-chromium/customize/placement  "更改 Microsoft Edge 开发人员工具的放置位置（取消停靠、停靠至底部、停靠至左）" 
[DevToolsCustomizePlacement]: /microsoft-edge/devtools-guide-chromium/customize/placement "Change Microsoft Edge DevTools Placement (Undock, Dock To Bottom, Dock To Left)"  

[GlitchDevToolsCssExamples]: https://microsoft-edge-chromium-devtools.glitch.me/static/css/examples/ecma.html "CSS 示例-Microsoft Edge (Chromium) DevTools |故障"  

[MDNUsingMediaGueries]: https://developer.mozilla.org/docs/Web/CSS/Media_Queries/Using_media_queries "使用媒体查询 |MDN"  

> [!NOTE]
> <span data-ttu-id="3a9fc-201">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="3a9fc-201">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="3a9fc-202">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/css/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="3a9fc-202">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/css/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="3a9fc-204">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="3a9fc-204">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
