---
description: 了解如何使用 Microsoft Edge Tools 查看和更改页面的 CSS。
title: 查看和更改 CSS 入门
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: bc629286530e709bef0e04a671f1a0e56eee48ea
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564446"
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
# <a name="get-started-with-viewing-and-changing-css"></a><span data-ttu-id="0ba3d-104">查看和更改 CSS 入门</span><span class="sxs-lookup"><span data-stu-id="0ba3d-104">Get started with viewing and changing CSS</span></span>  

<span data-ttu-id="0ba3d-105">完成这些交互式教程，了解使用 DevTools 查看和更改页面 CSS Microsoft Edge基础知识。</span><span class="sxs-lookup"><span data-stu-id="0ba3d-105">Complete these interactive tutorials to learn the basics of viewing and changing the CSS for a page using Microsoft Edge DevTools.</span></span>  

## <a name="open-css-examples"></a><span data-ttu-id="0ba3d-106">Open CSS 示例</span><span class="sxs-lookup"><span data-stu-id="0ba3d-106">Open CSS Examples</span></span>  

1.  <span data-ttu-id="0ba3d-107">保留 `Control` \(Windows、Linux\) 或 `Command` \(macOS\) 并选择 **"CSS**示例"以在新窗口中打开。</span><span class="sxs-lookup"><span data-stu-id="0ba3d-107">Hold `Control` \(Windows, Linux\) or `Command` \(macOS\) and choose **CSS Examples** to open in a new window.</span></span>  
    
    [<span data-ttu-id="0ba3d-108">CSS 示例</span><span class="sxs-lookup"><span data-stu-id="0ba3d-108">CSS Examples</span></span>][GlitchDevToolsCssExamples]  
    
    > [!NOTE]
    > <span data-ttu-id="0ba3d-109">如果你想要将[DevTools][DevToolsCustomizePlacement]窗口停靠在下图\(中显示的视口 \) ，请选择"自定义和控制**DevTools"。** `...`</span><span class="sxs-lookup"><span data-stu-id="0ba3d-109">If you want to [dock your DevTools window][DevToolsCustomizePlacement] to the right of your viewport \(displayed in the following figure\), choose **Customize and control DevTools** `...`.</span></span>  <span data-ttu-id="0ba3d-110">在"**自定义和控制 DevTools"** 下拉菜单上的"扩展坞**侧**"部分中，选择"扩展**坞"以向右。**</span><span class="sxs-lookup"><span data-stu-id="0ba3d-110">On the **Customize and control DevTools** drop-down menu, in the **Dock side** section, choose **Dock to right**.</span></span>  
    
## <a name="view-the-css-for-an-element"></a><span data-ttu-id="0ba3d-111">查看元素的 CSS</span><span class="sxs-lookup"><span data-stu-id="0ba3d-111">View the CSS for an element</span></span>  

1.  <span data-ttu-id="0ba3d-112">[打开 CSS 示例](#open-css-examples)。</span><span class="sxs-lookup"><span data-stu-id="0ba3d-112">[Open CSS Examples](#open-css-examples).</span></span>  
1.  <span data-ttu-id="0ba3d-113">将鼠标悬停在 `Inspect Me!` 文本上，打开上下文菜单 \(右键单击\) ，然后选择"检查 **"。**</span><span class="sxs-lookup"><span data-stu-id="0ba3d-113">Hover on the `Inspect Me!` text, open the contextual menu \(right-click\), and choose **Inspect**.</span></span>  
    1.  <span data-ttu-id="0ba3d-114">在 DevTools 中，在 **"元素** "工具的 **"DOM 树** "面板中， `Inspect Me!` 元素突出显示。</span><span class="sxs-lookup"><span data-stu-id="0ba3d-114">In DevTools, on the **Elements** tool, in the **DOM Tree** panel, the `Inspect Me!` element is highlighted.</span></span>  
        
        :::image type="complex" source="../media/css-elements-inspect-me.msft.png" alt-text="检查的元素在 DOM 树中突出显示" lightbox="../media/css-elements-inspect-me.msft.png":::
           <span data-ttu-id="0ba3d-116">检查的元素在 DOM 树 **中突出显示**</span><span class="sxs-lookup"><span data-stu-id="0ba3d-116">The inspected element is highlighted in the **DOM Tree**</span></span>  
        :::image-end:::  
        
    1.  <span data-ttu-id="0ba3d-117">在 `Inspect Me!` 元素中，找到 属性的值 `data-message` 并复制它。</span><span class="sxs-lookup"><span data-stu-id="0ba3d-117">In the `Inspect Me!` element, find the value of the `data-message` attribute and copy it.</span></span>  
1.  <span data-ttu-id="0ba3d-118">在页面上的" \*\*值 `data-message` \*\* "文本框中，输入值。</span><span class="sxs-lookup"><span data-stu-id="0ba3d-118">On the page, in the **Value of `data-message`:** textbox, enter the value.</span></span>  
1.  <span data-ttu-id="0ba3d-119">将鼠标悬停在 `Inspect Me!` 文本上，打开上下文菜单 \(右键单击\) ，然后选择"检查 **"。**</span><span class="sxs-lookup"><span data-stu-id="0ba3d-119">Hover on the `Inspect Me!` text, open the contextual menu \(right-click\), and choose **Inspect**.</span></span>  
    1.  <span data-ttu-id="0ba3d-120">在 DevTools 中的" **元素** "工具上，选择 **"样式"** 面板。</span><span class="sxs-lookup"><span data-stu-id="0ba3d-120">In DevTools, on the **Elements** tool, select the **Styles** panel.</span></span>  
    1.  <span data-ttu-id="0ba3d-121">在 **"样式"** 面板中， `Inspect Me!` 元素突出显示。</span><span class="sxs-lookup"><span data-stu-id="0ba3d-121">In the **Styles** panel, the `Inspect Me!` element is highlighted.</span></span>  
    1.  <span data-ttu-id="0ba3d-122">在 `Inspect Me!` 元素中，查找 `aloha` 类规则。</span><span class="sxs-lookup"><span data-stu-id="0ba3d-122">In the `Inspect Me!` element, find the `aloha` class rule.</span></span>  
        
        > [!NOTE]
        > <span data-ttu-id="0ba3d-123">显示此规则，因为它将应用于 `Inspect Me!` 元素。</span><span class="sxs-lookup"><span data-stu-id="0ba3d-123">This rule is displayed, because it is being applied to the `Inspect Me!` element.</span></span>  
        
    1.  <span data-ttu-id="0ba3d-124">在 `aloha` 类中，查找样式的值 `padding` 并复制它。</span><span class="sxs-lookup"><span data-stu-id="0ba3d-124">In the `aloha` class, find the value for the `padding` style and copy it.</span></span>  
        
        :::image type="complex" source="../media/css-elements-inspect-me-styles.msft.png" alt-text="CSS 类应用于检查的元素在样式面板中突出显示" lightbox="../media/css-elements-inspect-me-styles.msft.png":::
           <span data-ttu-id="0ba3d-126">CSS 类应用于选定的元素，例如 ， `aloha` 显示在" **样式"** 面板中</span><span class="sxs-lookup"><span data-stu-id="0ba3d-126">CSS classes is applied to the selected element, such as `aloha`, are displayed in the **Styles** panel</span></span>  
        :::image-end:::  
        
1.  <span data-ttu-id="0ba3d-127">在页面上的" \*\*值 `padding` \*\* "文本框中，输入值。</span><span class="sxs-lookup"><span data-stu-id="0ba3d-127">On the page, in the **Value of `padding`:** textbox, enter the value.</span></span>  

## <a name="add-a-css-declaration-to-an-element"></a><span data-ttu-id="0ba3d-128">向元素添加 CSS 声明</span><span class="sxs-lookup"><span data-stu-id="0ba3d-128">Add a CSS declaration to an element</span></span>  

<span data-ttu-id="0ba3d-129">当您 **要更改** CSS 声明或将 CSS 声明添加到元素时，请使用"样式"面板。</span><span class="sxs-lookup"><span data-stu-id="0ba3d-129">Use the **Styles** panel when you want to change or add CSS declarations to an element.</span></span>  

> [!NOTE]
> <span data-ttu-id="0ba3d-130">完成 [查看元素的 CSS](#view-the-css-for-an-element) 教程，然后再执行此操作。</span><span class="sxs-lookup"><span data-stu-id="0ba3d-130">Complete the [View the CSS for an element](#view-the-css-for-an-element) tutorial before doing this one.</span></span>  

1.  <span data-ttu-id="0ba3d-131">[打开 CSS 示例](#open-css-examples)。</span><span class="sxs-lookup"><span data-stu-id="0ba3d-131">[Open CSS Examples](#open-css-examples).</span></span>  
1.  <span data-ttu-id="0ba3d-132">将鼠标悬停在 `Add A Background Color To Me!` 文本上，打开上下文菜单 \(右键单击\) ，然后选择"检查 **"。**</span><span class="sxs-lookup"><span data-stu-id="0ba3d-132">Hover on the `Add A Background Color To Me!` text, open the contextual menu \(right-click\), and choose **Inspect**.</span></span>  
1.  <span data-ttu-id="0ba3d-133">选择 `element.style` "样式"面板 **顶部** 附近的选项。</span><span class="sxs-lookup"><span data-stu-id="0ba3d-133">Choose `element.style` near the top of the **Styles** panel.</span></span>  
1.  <span data-ttu-id="0ba3d-134">键入 `background-color` 并选择 `Enter`。</span><span class="sxs-lookup"><span data-stu-id="0ba3d-134">Type `background-color` and select `Enter`.</span></span>  
1.  <span data-ttu-id="0ba3d-135">键入 `honeydew` 并选择 `Enter`。</span><span class="sxs-lookup"><span data-stu-id="0ba3d-135">Type `honeydew` and select `Enter`.</span></span>  <span data-ttu-id="0ba3d-136">在 **DOM 树中**，将显示应用于元素的内联样式声明。</span><span class="sxs-lookup"><span data-stu-id="0ba3d-136">In the **DOM Tree**, an inline style declaration applied to the element is displayed.</span></span>  
    
    :::image type="complex" source="../media/css-elements-add-background-color-to-me-styles-p.msft.png" alt-text="使用样式面板向 元素添加 CSS 声明" lightbox="../media/css-elements-add-background-color-to-me-styles-p.msft.png":::
       <span data-ttu-id="0ba3d-138">使用 `background-color:honeydew` "样式"面板的 部分 `element.style` 将声明 **应用于** 元素</span><span class="sxs-lookup"><span data-stu-id="0ba3d-138">The `background-color:honeydew` declaration is applied to the element using the `element.style` section of the **Styles** panel</span></span>  
    :::image-end:::  
    
## <a name="add-a-css-class-to-an-element"></a><span data-ttu-id="0ba3d-139">将 CSS 类添加到元素</span><span class="sxs-lookup"><span data-stu-id="0ba3d-139">Add a CSS class to an element</span></span>  

<span data-ttu-id="0ba3d-140">若要显示 CSS 类应用于某个元素或将其从元素中删除时元素的外观，请导航到" **样式"** 面板。</span><span class="sxs-lookup"><span data-stu-id="0ba3d-140">To display how an element looks when a CSS class is applied to or removed from an element, navigate to the **Styles** panel.</span></span>  

> [!NOTE]
> <span data-ttu-id="0ba3d-141">完成 [查看元素的 CSS](#view-the-css-for-an-element) 教程，然后再执行此操作。</span><span class="sxs-lookup"><span data-stu-id="0ba3d-141">Complete the [View the CSS for an element](#view-the-css-for-an-element) tutorial before doing this one.</span></span>  

1.  <span data-ttu-id="0ba3d-142">[打开 CSS 示例](#open-css-examples)。</span><span class="sxs-lookup"><span data-stu-id="0ba3d-142">[Open CSS Examples](#open-css-examples).</span></span>  
1.  <span data-ttu-id="0ba3d-143">将鼠标悬停在 `Add A Class To Me!` 文本上，打开上下文菜单 \(右键单击\) ，然后选择"检查 **"。**</span><span class="sxs-lookup"><span data-stu-id="0ba3d-143">Hover on the `Add A Class To Me!` text, open the contextual menu \(right-click\), and choose **Inspect**.</span></span>  
1.  <span data-ttu-id="0ba3d-144">选择 **.cls**。</span><span class="sxs-lookup"><span data-stu-id="0ba3d-144">Choose **.cls**.</span></span>  <span data-ttu-id="0ba3d-145">DevTools 显示一个文本框，你可以将类添加到所选元素。</span><span class="sxs-lookup"><span data-stu-id="0ba3d-145">DevTools reveals a text box where you may add classes to the selected element.</span></span>  
1.  <span data-ttu-id="0ba3d-146">在 `color_me` "添加新 **类"** 文本框中键入 ，然后选择 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="0ba3d-146">Type `color_me` in the **Add new class** text box and then select `Enter`.</span></span>  <span data-ttu-id="0ba3d-147">"添加新 **类"文本框** 下方将出现一个复选框，可在其中打开和关闭该类。</span><span class="sxs-lookup"><span data-stu-id="0ba3d-147">A checkbox appears below the **Add new class** text box, where you may toggle the class on and off.</span></span>  <span data-ttu-id="0ba3d-148">如果 `Add A Class To Me!` 元素应用了任何其他类，则还可以在此处切换每个类。</span><span class="sxs-lookup"><span data-stu-id="0ba3d-148">If the `Add A Class To Me!` element has any other classes applied to it, you are also able to toggle each from here.</span></span>  
    
    :::image type="complex" source="../media/css-elements-add-a-class-to-me-styles-cls.msft.png" alt-text="将 color_me 类应用到 元素" lightbox="../media/css-elements-add-a-class-to-me-styles-cls.msft.png":::
       <span data-ttu-id="0ba3d-150">类 `color_me` 使用"样式"面板的 **.cls**部分应用到元素\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="0ba3d-150">The `color_me` class is applied to the element using the **.cls** section of the **Styles** panel</span></span>  
    :::image-end:::  
    
## <a name="add-a-pseudostate-to-a-class"></a><span data-ttu-id="0ba3d-151">向类添加伪状态</span><span class="sxs-lookup"><span data-stu-id="0ba3d-151">Add a pseudostate to a class</span></span>  

<span data-ttu-id="0ba3d-152">使用 **"样式** "面板将 CSS 伪状态永久应用到元素。</span><span class="sxs-lookup"><span data-stu-id="0ba3d-152">Use the **Styles** panel to permanently apply a CSS pseudostate to an element.</span></span>  <span data-ttu-id="0ba3d-153">DevTools `:active` 支持 、 `:focus` 、 和 `:hover` `:visited` 。</span><span class="sxs-lookup"><span data-stu-id="0ba3d-153">DevTools supports `:active`, `:focus`, `:hover`, and `:visited`.</span></span>  

> [!NOTE]
> <span data-ttu-id="0ba3d-154">完成 [查看元素的 CSS](#view-the-css-for-an-element) 教程，然后再执行此操作。</span><span class="sxs-lookup"><span data-stu-id="0ba3d-154">Complete the [View the CSS for an element](#view-the-css-for-an-element) tutorial before doing this one.</span></span>  

1.  <span data-ttu-id="0ba3d-155">[打开 CSS 示例](#open-css-examples)。</span><span class="sxs-lookup"><span data-stu-id="0ba3d-155">[Open CSS Examples](#open-css-examples).</span></span>  
1.  <span data-ttu-id="0ba3d-156">将鼠标悬停在 `Hover Over Me!` 文本上。</span><span class="sxs-lookup"><span data-stu-id="0ba3d-156">Hover on the `Hover Over Me!` text.</span></span>  <span data-ttu-id="0ba3d-157">背景色更改。</span><span class="sxs-lookup"><span data-stu-id="0ba3d-157">The background color changes.</span></span>  
1.  <span data-ttu-id="0ba3d-158">将鼠标悬停在 `Hover Over Me!` 文本上，打开上下文菜单 \(右键单击\) ，然后选择"检查 **"。**</span><span class="sxs-lookup"><span data-stu-id="0ba3d-158">Hover on the `Hover Over Me!` text, open the contextual menu \(right-click\), and choose **Inspect**.</span></span>  
1.  <span data-ttu-id="0ba3d-159">在"**样式"** 面板中，选择 **"：hov"。**</span><span class="sxs-lookup"><span data-stu-id="0ba3d-159">In the **Styles** panel, choose **:hov**.</span></span>  
1.  <span data-ttu-id="0ba3d-160">选中 **"：hover"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="0ba3d-160">Check the **:hover** checkbox.</span></span>  <span data-ttu-id="0ba3d-161">背景颜色会像以前一样更改，即使你实际上并未将鼠标悬停在元素上。</span><span class="sxs-lookup"><span data-stu-id="0ba3d-161">The background color changes like before, even though you are not actually hovering over the element.</span></span>  
    
    :::image type="complex" source="../media/css-elements-hover-over-me-styles-hov-hover.msft.png" alt-text="切换元素上的悬停伪状态" lightbox="../media/css-elements-hover-over-me-styles-hov-hover.msft.png":::
       <span data-ttu-id="0ba3d-163">切换 `:hover` 元素上的伪状态</span><span class="sxs-lookup"><span data-stu-id="0ba3d-163">Toggle the `:hover` pseudostate on an element</span></span>  
    :::image-end:::  
    
## <a name="change-the-dimensions-of-an-element"></a><span data-ttu-id="0ba3d-164">更改元素的维度</span><span class="sxs-lookup"><span data-stu-id="0ba3d-164">Change the dimensions of an element</span></span>  

<span data-ttu-id="0ba3d-165">使用 **"样式** " **面板中的"** 方框模型"交互式图表可更改元素的宽度、高度、填充、边距或边框长度。</span><span class="sxs-lookup"><span data-stu-id="0ba3d-165">Use the **Box Model** interactive diagram in the **Styles** panel to change the width, height, padding, margin, or border length of an element.</span></span>  

> [!NOTE]
> <span data-ttu-id="0ba3d-166">完成 [查看元素的 CSS](#view-the-css-for-an-element) 教程，然后再执行此操作。</span><span class="sxs-lookup"><span data-stu-id="0ba3d-166">Complete the [View the CSS for an element](#view-the-css-for-an-element) tutorial before doing this one.</span></span>  

1.  <span data-ttu-id="0ba3d-167">[打开 CSS 示例](#open-css-examples)。</span><span class="sxs-lookup"><span data-stu-id="0ba3d-167">[Open CSS Examples](#open-css-examples).</span></span>  
1.  <span data-ttu-id="0ba3d-168">将鼠标悬停在 `Change My Margin!` 文本上，打开上下文菜单 \(右键单击\) ，然后选择"检查 **"。**</span><span class="sxs-lookup"><span data-stu-id="0ba3d-168">Hover on the `Change My Margin!` text, open the contextual menu \(right-click\), and choose **Inspect**.</span></span>  
1.  <span data-ttu-id="0ba3d-169">在" **样式"** 面板的"方框模型 **"** 图表中，将鼠标悬停在 **填充上**。</span><span class="sxs-lookup"><span data-stu-id="0ba3d-169">In the **Box Model** diagram in the **Styles** panel, hover on **padding**.</span></span>  <span data-ttu-id="0ba3d-170">元素的填充在视口中突出显示。</span><span class="sxs-lookup"><span data-stu-id="0ba3d-170">The padding of an element is highlighted in the viewport.</span></span>  

    > [!NOTE]
    > <span data-ttu-id="0ba3d-171">根据 DevTools 窗口的大小，可能需要滚动到"样式"面板的底部以显示 **"方框模型"。** \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="0ba3d-171">Depending on the size of your DevTools window, you may need to scroll to the bottom of the **Styles** panel to display the **Box Model**.</span></span>  

1.  <span data-ttu-id="0ba3d-172">双击"方框模型"中的左边距\*\*\*\*，当前具有表示元素 `-` 没有左边距的值。</span><span class="sxs-lookup"><span data-stu-id="0ba3d-172">Double-click the left margin in the **Box Model**, which currently has a value of `-` meaning that the element does not have a left-margin.</span></span>  
1.  <span data-ttu-id="0ba3d-173">键入 `100px` 并选择 `Enter`。</span><span class="sxs-lookup"><span data-stu-id="0ba3d-173">Type `100px` and select `Enter`.</span></span>  <span data-ttu-id="0ba3d-174">方框 **模型** 默认为像素，但它也接受其他值，如 `25%` 或 `10vw` 。</span><span class="sxs-lookup"><span data-stu-id="0ba3d-174">The **Box Model** defaults to pixels, but it also accepts other values, such as `25%`, or `10vw`.</span></span>  
    
    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/css-elements-change-my-margin-styles-padding.msft.png" alt-text="将鼠标悬停在元素的填充上" lightbox="../media/css-elements-change-my-margin-styles-padding.msft.png":::
             <span data-ttu-id="0ba3d-176">将鼠标悬停在元素的填充上</span><span class="sxs-lookup"><span data-stu-id="0ba3d-176">Hover on the padding of the element</span></span>  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/css-elements-change-my-margin-styles-margin-edit.msft.png" alt-text="更改元素的左边距" lightbox="../media/css-elements-change-my-margin-styles-margin-edit.msft.png":::
             <span data-ttu-id="0ba3d-178">更改元素的左边距</span><span class="sxs-lookup"><span data-stu-id="0ba3d-178">Change the left-margin of the element</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
## <a name="debugging-media-queries"></a><span data-ttu-id="0ba3d-179">调试媒体查询</span><span class="sxs-lookup"><span data-stu-id="0ba3d-179">Debugging Media Queries</span></span>  

<span data-ttu-id="0ba3d-180">[媒体查询][MDNUsingMediaGueries] 是一种使 Web 产品对每个用户的配置设置更改做出反应的方法。</span><span class="sxs-lookup"><span data-stu-id="0ba3d-180">[Media Queries][MDNUsingMediaGueries] are a way to make your web product react to changes in the configuration settings for each user.</span></span>  <span data-ttu-id="0ba3d-181">最重要的用例是，根据视口尺寸为产品提供不同的 CSS 布局。</span><span class="sxs-lookup"><span data-stu-id="0ba3d-181">The most significant use case is to provide your product a different CSS layout depending on the dimensions of the viewport.</span></span>  <span data-ttu-id="0ba3d-182">当有更多的屏幕空间可用时，使用单独的布局允许移动设备和多列布局使用单列布局。</span><span class="sxs-lookup"><span data-stu-id="0ba3d-182">Using separate layouts allows for a one-column layout for mobile devices and multi-column layouts when there is more screen estate available.</span></span>  

<span data-ttu-id="0ba3d-183">如果要调试或测试在 CSS 中定义的媒体查询，请使用以下步骤。</span><span class="sxs-lookup"><span data-stu-id="0ba3d-183">If you want to debug or test the Media Queries you defined in your CSS, use the following steps.</span></span>  

1.  <span data-ttu-id="0ba3d-184">打开开发人员工具并选择左上方第\*\*\*\* 二个"切换设备"工具栏图标，或在 `Ctrl` + `Shift` + `M` `Cmd` + `Shift` + `M` macOS\(选择 \) 。</span><span class="sxs-lookup"><span data-stu-id="0ba3d-184">Open the developer tools and select the **Toggle device toolbar** icon second on the top-left, or select `Ctrl`+`Shift`+`M` \(`Cmd`+`Shift`+`M` on macOS\).</span></span>  
    
    :::image type="complex" source="../media/css-elements-media-queries-open-device-toolbar.msft.png" alt-text="打开设备工具栏" lightbox="../media/css-elements-media-queries-open-device-toolbar.msft.png":::
       <span data-ttu-id="0ba3d-186">打开设备工具栏</span><span class="sxs-lookup"><span data-stu-id="0ba3d-186">Open the device toolbar</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="0ba3d-187">打开设备工具栏后，选择右上方的菜单， `...` 然后选择"**查看媒体查询"。**</span><span class="sxs-lookup"><span data-stu-id="0ba3d-187">With the device toolbar open, select the `...` menu on the top-right and choose **View Media Queries**.</span></span>  <span data-ttu-id="0ba3d-188">网页上方显示的彩色条代表不同的媒体查询。</span><span class="sxs-lookup"><span data-stu-id="0ba3d-188">The colored bars displayed above the webpage represent the different media queries.</span></span>  
    
    :::image type="complex" source="../media/css-elements-media-queries-showing-mq.msft.png" alt-text="在设备工具栏中显示媒体查询" lightbox="../media/css-elements-media-queries-showing-mq.msft.png":::
       <span data-ttu-id="0ba3d-190">在设备工具栏中显示媒体查询</span><span class="sxs-lookup"><span data-stu-id="0ba3d-190">Show Media Queries in Device Toolbar</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="0ba3d-191">将鼠标悬停在条形的边界上，以显示不同媒体查询的值。</span><span class="sxs-lookup"><span data-stu-id="0ba3d-191">Hover on the boundaries in the bars to display the values of the different media queries.</span></span>  <span data-ttu-id="0ba3d-192">选择每个页面以调整网页大小以匹配。</span><span class="sxs-lookup"><span data-stu-id="0ba3d-192">Choose each to resize the web page to match.</span></span>  
    
    :::image type="complex" source="../media/css-elements-media-queries-select-bar.msft.png" alt-text="从预览栏中选择媒体查询" lightbox="../media/css-elements-media-queries-select-bar.msft.png":::
       <span data-ttu-id="0ba3d-194">从预览栏中选择媒体查询</span><span class="sxs-lookup"><span data-stu-id="0ba3d-194">Choose Media Query from preview bar</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="0ba3d-195">若要调试媒体查询，并打开编辑器中的 CSS 文件;将鼠标悬停在任何栏分段上，打开上下文菜单 `Sources` \(右键单击\) ，然后选择 `reveal in source code` 。</span><span class="sxs-lookup"><span data-stu-id="0ba3d-195">To debug media queries and open the CSS file in the `Sources` editor; hover on any of the bar segments, open the contextual menu \(right-click\), and select `reveal in source code`.</span></span>  
    
    :::image type="complex" source="../media/css-elements-media-queries-reveal-in-sources.msft.png" alt-text="在源编辑器中显示媒体查询" lightbox="../media/css-elements-media-queries-reveal-in-sources.msft.png":::
       <span data-ttu-id="0ba3d-197">在源编辑器中显示媒体查询</span><span class="sxs-lookup"><span data-stu-id="0ba3d-197">Reveal Media Queries in Sources Editor</span></span>  
    :::image-end:::  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="0ba3d-198">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="0ba3d-198">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[ DevToolsCustomizePlacement]: /microsoft-edge/devtools-guide-chromium/customize/placement  "更改 Microsoft Edge 开发人员工具的放置位置（取消停靠、停靠至底部、停靠至左）" 
[DevToolsCustomizePlacement]: /microsoft-edge/devtools-guide-chromium/customize/placement "Change Microsoft Edge DevTools Placement (Undock, Dock To Bottom, Dock To Left)"  

[GlitchDevToolsCssExamples]: https://microsoft-edge-chromium-devtools.glitch.me/static/css/examples/ecma.html "CSS 示例 - Microsoft Edge (Chromium) DevTools |小故障"  

[MDNUsingMediaGueries]: https://developer.mozilla.org/docs/Web/CSS/Media_Queries/Using_media_queries "使用媒体查询|MDN"  

> [!NOTE]
> <span data-ttu-id="0ba3d-202">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="0ba3d-202">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="0ba3d-203">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/css/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="0ba3d-203">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/css/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="0ba3d-205">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="0ba3d-205">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
