---
description: CSS 入门
title: 初学者的 DevTools：开始使用 CSS
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: fe87b4f840c6d9dde3cdf6455700161ea8d8d31e
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993301"
---
<!-- Copyright Katherine Jackson 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->

# <span data-ttu-id="fdd9a-104">初学者的 DevTools：开始使用 CSS</span><span class="sxs-lookup"><span data-stu-id="fdd9a-104">DevTools for beginners: Get started with CSS</span></span>  

<span data-ttu-id="fdd9a-105">在本教程中，你将了解如何使用 CSS 对网页进行样式。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-105">In this tutorial, you learn how to use CSS to style a web page.</span></span>  <span data-ttu-id="fdd9a-106">你还将了解如何使用 Microsoft Edge DevTools 来试验 CSS 更改。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-106">You also learn how to use Microsoft Edge DevTools to experiment with CSS changes.</span></span>  

<span data-ttu-id="fdd9a-107">以下文章是一系列教程中的第二个教程，可教你了解 web 开发和 Microsoft Edge DevTools 的基础知识。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-107">The following article is the second tutorial in a series of tutorials that teaches you the basics of web development and Microsoft Edge DevTools.</span></span>  <span data-ttu-id="fdd9a-108">您可以通过实际构建自己的网站来获得实际体验。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-108">You gain hands-on experience by actually building your own website.</span></span>  <span data-ttu-id="fdd9a-109">在下一步操作之前，不必完成第一个教程。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-109">You do not have to complete the first tutorial before following the second.</span></span>  <span data-ttu-id="fdd9a-110">[设置代码](#set-up-your-code) 显示如何设置。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-110">[Set up your code](#set-up-your-code) shows you how to get set up.</span></span>  

> [!NOTE]
> <span data-ttu-id="fdd9a-111">本教程适用于绝对初学者，重点介绍 **web 开发的基础知识** 和使用 DEVTOOLS 试验 CSS 的基础知识。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-111">This tutorial is designed for absolute beginners and focuses on both the **fundamentals of web development** and the basics of using DevTools to experiment with CSS.</span></span>  <span data-ttu-id="fdd9a-112">如果你需要仅关注 DevTools 的教程，请参阅 [查看和更改 CSS 入门][DevtoolsCssIndex]。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-112">If you want a tutorial that only focuses on DevTools, see [Get Started with Viewing and Changing CSS][DevtoolsCssIndex].</span></span>  

<span data-ttu-id="fdd9a-113">在教程的开头，您的网站应如下图所示。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-113">At the beginning of the tutorial, your site should look like the following figure.</span></span>  

:::image type="complex" source="../media/beginners-css-intro1.msft.png" alt-text="网站的当前外观" lightbox="../media/beginners-css-intro1.msft.png":::
   <span data-ttu-id="fdd9a-115">网站的当前外观</span><span class="sxs-lookup"><span data-stu-id="fdd9a-115">What your site currently looks like</span></span>  
:::image-end:::  

<span data-ttu-id="fdd9a-116">完成教程后，您的网站应如下图所示。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-116">After you complete the tutorial, you site should look like the following figure.</span></span>  

:::image type="complex" source="../media/beginners-css-intro2.msft.png" alt-text="您的网站在教程结束时应看起来是什么样子" lightbox="../media/beginners-css-intro2.msft.png":::
   <span data-ttu-id="fdd9a-118">您的网站在教程结束时应看起来是什么样子</span><span class="sxs-lookup"><span data-stu-id="fdd9a-118">What your site should look like at the end of the tutorial</span></span>  
:::image-end:::  

## <span data-ttu-id="fdd9a-119">目标</span><span class="sxs-lookup"><span data-stu-id="fdd9a-119">Goals</span></span>  

<span data-ttu-id="fdd9a-120">按照此教程更好地了解以下概念和任务。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-120">Follow this tutorial to better understand the following concepts and tasks.</span></span>  

*   <span data-ttu-id="fdd9a-121">如何使用 CSS 对网页进行样式。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-121">How to use CSS to style a web page.</span></span>  
*   <span data-ttu-id="fdd9a-122">如何使用 Microsoft Edge DevTools 来试验 CSS。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-122">How to use Microsoft Edge DevTools to experiment with CSS.</span></span>  
*   <span data-ttu-id="fdd9a-123">CSS 和 CSS 框架之间的区别。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-123">The difference between CSS and CSS frameworks.</span></span>  

<span data-ttu-id="fdd9a-124">您正在构建真正的网站。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-124">You are building a real website.</span></span>  

## <span data-ttu-id="fdd9a-125">必备条件</span><span class="sxs-lookup"><span data-stu-id="fdd9a-125">Prerequisites</span></span>  

<span data-ttu-id="fdd9a-126">在尝试本教程之前，请完成以下先决条件。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-126">Before attempting this tutorial, complete the following prerequisites.</span></span>  

*   <span data-ttu-id="fdd9a-127">完整 [入门 html 和 dom，][DevtoolsBeginnersHtml] 或者确保你对 HTML 和 dom 的理解与该教程中所讲授的内容类似。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-127">Complete [Get Started with HTML and the DOM][DevtoolsBeginnersHtml] or make sure that you have an understanding of HTML and the DOM similar to what is taught in that tutorial.</span></span>  
*   <span data-ttu-id="fdd9a-128">下载 [Microsoft Edge][MicrosoftEdgeInsider] web 浏览器。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-128">Download the [Microsoft Edge][MicrosoftEdgeInsider] web browser.</span></span>  <span data-ttu-id="fdd9a-129">以下教程使用一组称为 Microsoft Edge DevTools 的 web 开发工具，这些工具内置于 Microsoft Edge 中。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-129">The following tutorial uses a set of web development tools, called the Microsoft Edge DevTools, that are built into Microsoft Edge.</span></span>  

## <span data-ttu-id="fdd9a-130">设置代码</span><span class="sxs-lookup"><span data-stu-id="fdd9a-130">Set up your code</span></span>  

<span data-ttu-id="fdd9a-131">若要创建网站，必须首先完成以下操作来设置代码。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-131">To create your site, you must first complete the following actions to set up your code.</span></span>  

> [!NOTE]
> <span data-ttu-id="fdd9a-132">如果您已完成系列中的第一个教程，请跳至下一节。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-132">If you have already completed the first tutorial in the series, skip to the next section.</span></span>  <span data-ttu-id="fdd9a-133">继续使用最后一个教程中的代码， [HTML 和 DOM 入门][DevtoolsBeginnersHtml]。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-133">Continue using your code from the last tutorial, [Get Started with HTML and the DOM][DevtoolsBeginnersHtml].</span></span>  

1.  <span data-ttu-id="fdd9a-134">打开 [源代码][GlitchCookedAmphibianIndex]。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-134">Open the [source code][GlitchCookedAmphibianIndex].</span></span>  <span data-ttu-id="fdd9a-135">浏览器的 "聚焦" 选项卡作为 " **编辑" 选项卡**进行引用。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-135">The in-focus tab of your browser is referenced as the **editing tab**.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-setup1.msft.png" alt-text=""编辑" 选项卡" lightbox="../media/beginners-css-setup1.msft.png":::
       <span data-ttu-id="fdd9a-137">" **编辑** " 选项卡</span><span class="sxs-lookup"><span data-stu-id="fdd9a-137">The **editing** tab</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="fdd9a-138">选择 **cooked-amphibian**。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-138">Choose **cooked-amphibian**.</span></span>  <span data-ttu-id="fdd9a-139">将弹出一个菜单。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-139">A menu pops up.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-setup2.msft.png" alt-text=""项目选项" 菜单" lightbox="../media/beginners-css-setup2.msft.png":::
       <span data-ttu-id="fdd9a-141">"项目选项" 菜单</span><span class="sxs-lookup"><span data-stu-id="fdd9a-141">The Project Options menu</span></span>  
    :::image-end:::  

1.  <span data-ttu-id="fdd9a-142">选择 " **Remix Project**"。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-142">Choose **Remix Project**.</span></span>  <span data-ttu-id="fdd9a-143">问题创建您可以编辑的项目副本。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-143">Glitch creates a copy of the project that you are able to edit.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="fdd9a-144">故障为新项目生成一个随机名称。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-144">Glitch generates a random name for the new project.</span></span>  
    
1.  <span data-ttu-id="fdd9a-145">**在新窗口中选择 "\*\*\*\*显示**并选择"。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-145">Choose **Show** and select **In a New Window**.</span></span>  <span data-ttu-id="fdd9a-146">将打开另一个选项卡，其中包含您的网站的实时视图。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-146">Another tab opens with a live view of your site.</span></span>  <span data-ttu-id="fdd9a-147">浏览器的 "聚焦" 选项卡作为 " **实时" 选项卡**进行引用。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-147">The in-focus tab of your browser is referenced as the **live tab**.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-setup3.msft.png" alt-text=""实时" 选项卡" lightbox="../media/beginners-css-setup3.msft.png":::
       <span data-ttu-id="fdd9a-149">" **实时" 选项卡**</span><span class="sxs-lookup"><span data-stu-id="fdd9a-149">The **live tab**</span></span>  
    :::image-end:::  

## <span data-ttu-id="fdd9a-150">了解 CSS</span><span class="sxs-lookup"><span data-stu-id="fdd9a-150">Understand CSS</span></span>  

<span data-ttu-id="fdd9a-151">**CSS** 是确定网页布局和样式的计算机语言。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-151">**CSS** is a computer language that determines the layout and styling of web pages.</span></span>  <span data-ttu-id="fdd9a-152">下图是带有边框的段落。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-152">The following figure is a paragraph with a border.</span></span>  

:::image type="complex" source="../media/beginners-css-red_paragraph.msft.png" alt-text="文本已采用 CSS 样式" lightbox="../media/beginners-css-red_paragraph.msft.png":::
   <span data-ttu-id="fdd9a-154">文本已采用 CSS 样式</span><span class="sxs-lookup"><span data-stu-id="fdd9a-154">The text has been styled with CSS</span></span>  
:::image-end:::  

<span data-ttu-id="fdd9a-155">以下代码片段是用于创建上图中的段落的 HTML 和 CSS 代码。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-155">The following code snippet is the HTML and CSS code used to create the paragraph in the previous figure.</span></span>  

```html
<p style="border: 1px dashed red; padding: 5px;">
    This has been styled with CSS.
</p>
```  

`style="border: 1px dashed red; padding: 5px;"` <span data-ttu-id="fdd9a-156">可能看起来很新。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-156">probably looks new to you.</span></span>  <span data-ttu-id="fdd9a-157">其余内容应熟悉。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-157">The rest should look familiar.</span></span>  <span data-ttu-id="fdd9a-158">如果不是，请先 [开始使用 HTML 和 DOM][DevtoolsBeginnersHtml] ，然后再尝试以下部分。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-158">If not, complete [Get Started with HTML and the DOM][DevtoolsBeginnersHtml] before attempting the following sections.</span></span>  

## <span data-ttu-id="fdd9a-159">添加内联样式</span><span class="sxs-lookup"><span data-stu-id="fdd9a-159">Add inline styles</span></span>  

<span data-ttu-id="fdd9a-160">完成以下操作以使用 **嵌入式样式** 将样式应用到单个元素。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-160">Complete the following actions to use **inline styles** to apply styles to a single element.</span></span>  

1.  <span data-ttu-id="fdd9a-161">返回到 "编辑" 选项卡并打开 `index.html` 。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-161">Go back to the editing tab and open `index.html`.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-inline1.msft.png" alt-text="index.html" lightbox="../media/beginners-css-inline1.msft.png":::
       <span data-ttu-id="fdd9a-163">`index.html`在 "编辑" 选项卡中打开</span><span class="sxs-lookup"><span data-stu-id="fdd9a-163">Open `index.html` in the editing tab</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="fdd9a-164">添加 `style="background-color: aliceblue;"` 到您 `<nav>` 的。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-164">Add `style="background-color: aliceblue;"` to your `<nav>`.</span></span>  <span data-ttu-id="fdd9a-165">在下面的代码块中，第四行代码是你需要更改的代码。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-165">In the code block below, the fourth line of code is the one you need to change.</span></span>  <span data-ttu-id="fdd9a-166">剩下的就是这样，因此您可以确保将新代码放入正确的位置。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-166">The rest is just there, so you are able to ensure that you are putting the new code in the right place.</span></span>  
    
    ```html
    <header>
        <p>Welcome to my site!</p>
    </header>
    <nav style="background-color: aliceblue;">
        <ul>
            <li><a href="/">Home</a></li>
            ...
        ...
    ...
    ```  
    
1.  <span data-ttu-id="fdd9a-167">转到 " **实时" 选项卡** 以查看所做的更改！</span><span class="sxs-lookup"><span data-stu-id="fdd9a-167">Go to the **live tab** to see the changes!</span></span>  <span data-ttu-id="fdd9a-168">现在，该分区的背景 `<nav>` 为蓝色。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-168">The background of the `<nav>` section is now blue.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-inline2.msft.png" alt-text=""主页" 和 "联系人" 链接后面的背景色现在为蓝色" lightbox="../media/beginners-css-inline2.msft.png":::
       <span data-ttu-id="fdd9a-170">" **主页** " 和 " **联系人** " 链接后面的背景色现在为蓝色</span><span class="sxs-lookup"><span data-stu-id="fdd9a-170">The background color behind the **Home** and **Contact** links is now blue</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="fdd9a-171">在具有内部样式表的单个页面上重新使用样式</span><span class="sxs-lookup"><span data-stu-id="fdd9a-171">Re-use styles on a single page with internal stylesheets</span></span>  

<span data-ttu-id="fdd9a-172">在前面的代码段中，内联样式将样式应用于单个 `<p>` 标记。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-172">In a previous code snippet, an inline style applied a style to a single `<p>` tag.</span></span>  

```html
<p style="border: 1px dashed red; padding: 5px;">
    This has been styled with CSS.
</p>
```  

<span data-ttu-id="fdd9a-173">如果您希望您的 `<p>` 网页上的所有元素的样式设置方式相同，该怎么办？</span><span class="sxs-lookup"><span data-stu-id="fdd9a-173">What if you wanted all of the `<p>` elements on your webpage to be styled the same way?</span></span>  <span data-ttu-id="fdd9a-174">您必须将代码复制并粘贴到 `<p>` 您的网站上的每个标记中。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-174">You would have to copy and paste the code into every single `<p>` tag on your site.</span></span>  <span data-ttu-id="fdd9a-175">这是大量的时间和精力。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-175">That is a lot of time and effort.</span></span>  <span data-ttu-id="fdd9a-176">如果需要进行编辑，则必须再次更改每个标签。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-176">And, if you needed to make an edit, you would have to change every tag again.</span></span>  <span data-ttu-id="fdd9a-177">完成以下操作以使用 **内部样式表** 编写 CSS 一次，以便它应用于多个元素。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-177">Complete the following actions to use an **Internal stylesheet** to write your CSS once so that it applies to multiple elements.</span></span>  

1.  <span data-ttu-id="fdd9a-178">在 "实时" 选项卡中，选择 " **联系人** " 以转到 "联系人" 页面。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-178">In the live tab, choose **Contact** to go to the contact page.</span></span>  <span data-ttu-id="fdd9a-179">请注意 " **家庭** " 和 " **联系人**" 的字体。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-179">Notice the font of **Home** and **Contact**.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-internal1.msft.png" alt-text=""联系人" 页面" lightbox="../media/beginners-css-internal1.msft.png":::
       <span data-ttu-id="fdd9a-181">"联系人" 页面</span><span class="sxs-lookup"><span data-stu-id="fdd9a-181">The Contact page</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="fdd9a-182">在 " **编辑器" 选项卡**中，转到 `contact.html` 。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-182">In the **editor tab**, go to `contact.html`.</span></span>  
1.  <span data-ttu-id="fdd9a-183">将以下代码添加到 `contact.html` 。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-183">Add the following code to `contact.html`.</span></span>  <span data-ttu-id="fdd9a-184">请记住，"行" `<style>` 和 "结束" 行 `</style>` 是你需要添加的内容。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-184">Remember, the lines starting with `<style>` and ending with `</style>` are what you need to add.</span></span>  <span data-ttu-id="fdd9a-185">其他代码就在这里，您知道在哪里放置新代码。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-185">The other code is just there so you know where to put the new code.</span></span>  
    
    ```html
    ...
        <head>
            ...
            <meta name="viewport" content="width=device-width, initial-scale=1">
            <style>
                li a {
                  font-family: 'Courier New', Courier, Serif;
                }
            </style>
            ...
        </head>
        ...
    ...
    ```  
    
1.  <span data-ttu-id="fdd9a-186">返回到 " **实时" 选项卡**。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-186">Go back to the **live tab**.</span></span>  
1.  <span data-ttu-id="fdd9a-187">选择 " **联系人** " 以返回到联系人页。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-187">Choose **Contact** to go back to the contact page.</span></span>  <span data-ttu-id="fdd9a-188">**家庭**和**联系人**的字体已更改。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-188">The font of **Home** and **Contact** has changed.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-internal2.msft.png" alt-text="主页和联系人链接的字体已更改" lightbox="../media/beginners-css-internal2.msft.png":::
       <span data-ttu-id="fdd9a-190">**主页**和**联系人**链接的字体已更改</span><span class="sxs-lookup"><span data-stu-id="fdd9a-190">The font of the **Home** and **Contact** links has changed</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="fdd9a-191">了解内部样式表</span><span class="sxs-lookup"><span data-stu-id="fdd9a-191">Understand internal stylesheets</span></span>  

<span data-ttu-id="fdd9a-192">内部样式表使用 **选择器**应用样式。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-192">Internal stylesheets apply styles using **selectors**.</span></span>  <span data-ttu-id="fdd9a-193">选择器是可应用于一个或多个 HTML 元素的模式。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-193">Selectors are patterns that may apply to one or more HTML elements.</span></span>  <span data-ttu-id="fdd9a-194">上面的代码段添加了以下样式。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-194">The previous code snippet added the following style.</span></span>  

```html
<style>
    li a {
      font-family: 'Courier New', Courier, Serif;
    }
</style>
```  

`li a` <span data-ttu-id="fdd9a-195">是转换为 " `<li>` 包含元素的任何元素" 的选择器 `<a>` 。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-195">is a selector that translates to "any `<li>` element that contains an `<a>` element".</span></span>  <span data-ttu-id="fdd9a-196">浏览器将更改 " **主页** " 和 " **联系人** " 链接的字体，因为每个标记组都与模式匹配。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-196">The browser changes the font of the **Home** and **Contact** links because each of the tag groups match the pattern.</span></span>  

```html
<li><a href="/">Home</a></li>
<li><a href="/contact.html">Contact</a></li>
```  

`font-family: 'Courier New', Courier, serif` <span data-ttu-id="fdd9a-197">是 **声明**。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-197">is a **declaration**.</span></span>  <span data-ttu-id="fdd9a-198">声明由以下两个部分组成。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-198">A declaration is made of following two parts.</span></span>  

:::row:::
   :::column span="1":::
      **<span data-ttu-id="fdd9a-199">属性</span><span class="sxs-lookup"><span data-stu-id="fdd9a-199">property</span></span>**  
   :::column-end:::
   :::column span="1":::
      `font-family`  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="fdd9a-200">该属性描述你可以更改元素样式的一般方式。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-200">The property describes a general way that you are able to change the style of the element.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="fdd9a-201">值</span><span class="sxs-lookup"><span data-stu-id="fdd9a-201">value</span></span>**  
   :::column-end:::
   :::column span="1":::
      `'Courier New', Courier, serif`  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="fdd9a-202">该值确切描述元素样式应如何更改。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-202">The value describes exactly how the style of the element should change.</span></span>  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="fdd9a-203">例如， `font-family: 'Courier New', Courier, serif` 为浏览器提供以下指令： "将匹配模式的元素的字体设置 `li a` 为 `'Courier New'` 。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-203">For example, `font-family: 'Courier New', Courier, serif` gives the browser the following instruction:  "Set the font of elements that match the pattern `li a` to `'Courier New'`.</span></span>  <span data-ttu-id="fdd9a-204">如果该字体不可用，请使用 `Courier` 。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-204">If that font is not available, use `Courier`.</span></span>  <span data-ttu-id="fdd9a-205">如果该功能不可用，请使用 `serif` 。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-205">If that is not available, use `serif`."</span></span>  

### <span data-ttu-id="fdd9a-206">将多个选择器添加到规则集</span><span class="sxs-lookup"><span data-stu-id="fdd9a-206">Add multiple selectors to a ruleset</span></span>  

<span data-ttu-id="fdd9a-207">类似于下面所示的 CSS 代码块称为 " **规则集**"。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-207">A block of CSS code like what you see below is called a **ruleset**.</span></span>  

```css
li a {
  font-family: 'Courier New', Courier, monospace;
}
```  

<span data-ttu-id="fdd9a-208">完成以下操作以使用逗号将多个选择器添加到规则集。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-208">Complete the following actions to use commas to add multiple selectors to a ruleset.</span></span>  

1.  <span data-ttu-id="fdd9a-209">在 " **编辑器" 选项卡**中，打开 `contact.html` 。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-209">In the **editor tab**, open `contact.html`.</span></span>  
1.  <span data-ttu-id="fdd9a-210">`li a`键入后 `, h1` 。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-210">After `li a` type `, h1`.</span></span>  
    
    ```html
    <style>
        li a, h1 {
          font-family: 'Courier New', Courier, Serif;
        }
    </style>
    ```  
    
    <span data-ttu-id="fdd9a-211">上面的代码片段告诉浏览器对元素的样式与 `<h1>` 与模式匹配的元素的样式相同 `li a` 。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-211">The previous code snippet tells the browser to style `<h1>` elements the same way that it styles elements that match the pattern `li a`.</span></span>  
    
1.  <span data-ttu-id="fdd9a-212">转到 " **实时" 选项卡**。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-212">Go to the **live tab**.</span></span>  
1.  <span data-ttu-id="fdd9a-213">选择 **联系人** 链接返回到联系人页。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-213">Choose the **Contact** link to go back to the contact page.</span></span>  <span data-ttu-id="fdd9a-214">现在，请 **与我联系！**</span><span class="sxs-lookup"><span data-stu-id="fdd9a-214">Now, **Contact Me!**</span></span> <span data-ttu-id="fdd9a-215">的字体与导航链接的字体相同。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-215">has the same font as the navigation links.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-multiple1.msft.png" alt-text="文本与我联系！  现在与 "主页" 和 "联系人" 链接的字体相同" lightbox="../media/beginners-css-multiple1.msft.png":::
       <span data-ttu-id="fdd9a-218">文本 **与我联系！**</span><span class="sxs-lookup"><span data-stu-id="fdd9a-218">The text **Contact Me!**</span></span> <span data-ttu-id="fdd9a-219">现在与 " **主页** " 和 " **联系人** " 链接的字体相同</span><span class="sxs-lookup"><span data-stu-id="fdd9a-219">now has the same font as the **Home** and **Contact** links</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="fdd9a-220">试用 DevTools</span><span class="sxs-lookup"><span data-stu-id="fdd9a-220">Experiment with DevTools</span></span>  

<span data-ttu-id="fdd9a-221">随着您继续在 web 开发中成为专家，您可能会发现 CSS 非常棘手。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-221">As you continue your journey to become an expert in web development, you may find that CSS is tricky.</span></span>  <span data-ttu-id="fdd9a-222">你可以编写一些 CSS，并希望它以一种方式显示，但浏览器执行完全不同的操作。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-222">You may write some CSS and expect it to display one way, but the browser does something completely different.</span></span>  <span data-ttu-id="fdd9a-223">Microsoft Edge DevTools 使你可以轻松地体验更改，并立即查看更改对页面有何影响。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-223">Microsoft Edge DevTools makes it easy to experiment with changes and immediately see how the changes affect the page.</span></span>  

### <span data-ttu-id="fdd9a-224">将声明添加到 DevTools 中的现有 rulest</span><span class="sxs-lookup"><span data-stu-id="fdd9a-224">Add a declaration to an existing rulest in DevTools</span></span>  

<span data-ttu-id="fdd9a-225">完成以下操作以循环访问现有元素的样式，将声明添加到现有规则集。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-225">Complete the following actions to iterate on the style of an existing element, add a declaration to an existing ruleset.</span></span>  

1.  <span data-ttu-id="fdd9a-226">将鼠标悬停在 " **主页** " 链接上，打开上下文菜单 \ (右键单击 "\ ) "，然后选择 " **检查**"。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-226">Hover on the **Home** link, open the contextual menu \(right-click\), and select **Inspect**.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-add1.msft.png" alt-text="检查 "主页" 链接" lightbox="../media/beginners-css-add1.msft.png":::
       <span data-ttu-id="fdd9a-228">检查 "主页" 链接</span><span class="sxs-lookup"><span data-stu-id="fdd9a-228">Inspect the Home link</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="fdd9a-229">DevTools 将在您的页面旁打开。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-229">DevTools opens up alongside your page.</span></span>  <span data-ttu-id="fdd9a-230">表示 Home 链接的代码在 `<a href="/">Home</a>` DOM 树中突出显示为蓝色。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-230">The code that represents the Home link, `<a href="/">Home</a>` is highlighted blue in the DOM Tree.</span></span>  <span data-ttu-id="fdd9a-231">代码片段和预览应熟悉 [HTML 和 DOM 入门][DevtoolsBeginnersHtml]。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-231">The code snippet and preview should be familiar from [Get Started with HTML and the DOM][DevtoolsBeginnersHtml].</span></span>  
    
    :::row:::
       :::column span="":::
          <span data-ttu-id="fdd9a-232">下图中，在 `font-family: 'Courier New', Courier, serif` `contact.html` DOM 树下方的 " **样式** " 选项卡中显示了之前添加到的声明。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-232">In the following figure, the `font-family: 'Courier New', Courier, serif` declaration that you previously added to `contact.html` is seen in the **Styles** tab below the DOM Tree.</span></span>  
          
          :::image type="complex" source="../media/beginners-css-add2.msft.png" alt-text=""样式" 选项卡位于 DOM 树的下方" lightbox="../media/beginners-css-add2.msft.png":::
             <span data-ttu-id="fdd9a-234">" **样式** " 选项卡位于 DOM 树的下方</span><span class="sxs-lookup"><span data-stu-id="fdd9a-234">The **Styles** tab is below the DOM Tree</span></span>  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          <span data-ttu-id="fdd9a-235">如果 DevTools 窗口是宽的，则 "样式" 选项卡位于 DOM 树的右侧。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-235">If your DevTools window is wide, the Styles tab is to the right of the DOM Tree.</span></span>  
          
          :::image type="complex" source="../media/beginners-css-add3.msft.png" alt-text=""样式" 选项卡位于 DOM 树的右侧" lightbox="../media/beginners-css-add3.msft.png":::
             <span data-ttu-id="fdd9a-237">" **样式** " 选项卡位于 DOM 树的右侧</span><span class="sxs-lookup"><span data-stu-id="fdd9a-237">The **Styles** tab is to the right of the DOM Tree</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
1.  <span data-ttu-id="fdd9a-238">选择下面的空行 `font-family: 'Courier New', Courier, Serif` 以添加新声明。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-238">Choose the empty line below `font-family: 'Courier New', Courier, Serif` to add a new declaration.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-add4.msft.png" alt-text="添加新声明" lightbox="../media/beginners-css-add4.msft.png":::
       <span data-ttu-id="fdd9a-240">添加新声明</span><span class="sxs-lookup"><span data-stu-id="fdd9a-240">Add a new declaration</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="fdd9a-241">键入 `color` 并选择 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-241">Type `color` and select `Enter`.</span></span>  <span data-ttu-id="fdd9a-242">"自动完成" UI 建议您键入时的选项。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-242">The autocomplete UI suggests options as you type.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-add5.msft.png" alt-text="键入颜色" lightbox="../media/beginners-css-add5.msft.png":::
       <span data-ttu-id="fdd9a-244">类型</span><span class="sxs-lookup"><span data-stu-id="fdd9a-244">Type</span></span> `color`  
    :::image-end:::  
    
1.  <span data-ttu-id="fdd9a-245">键入 `magenta` 并选择 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-245">Type `magenta` and select `Enter`.</span></span>  <span data-ttu-id="fdd9a-246">"联系人" 页面上的所有文本现在均为 "洋红"。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-246">All of the text on the contact page is now magenta.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-add6.msft.png" alt-text="键入洋红" lightbox="../media/beginners-css-add6.msft.png":::
       <span data-ttu-id="fdd9a-248">类型</span><span class="sxs-lookup"><span data-stu-id="fdd9a-248">Type</span></span> `magenta`  
    :::image-end:::  
    
### <span data-ttu-id="fdd9a-249">在 DevTools 中编辑声明</span><span class="sxs-lookup"><span data-stu-id="fdd9a-249">Edit a declaration in DevTools</span></span>  

<span data-ttu-id="fdd9a-250">完成以下操作以在 DevTools 中编辑现有声明。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-250">Complete the following actions to edit existing declarations in DevTools.</span></span>  

1.  <span data-ttu-id="fdd9a-251">选择旁边的洋红色方块 `magenta` 。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-251">Choose the magenta square next to `magenta`.</span></span>  <span data-ttu-id="fdd9a-252">将弹出一个颜色选取器。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-252">A color picker pops up.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-edit1.msft.png" alt-text="颜色选取器" lightbox="../media/beginners-css-edit1.msft.png":::
       <span data-ttu-id="fdd9a-254">颜色选取器</span><span class="sxs-lookup"><span data-stu-id="fdd9a-254">The Color Picker</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="fdd9a-255">使用拾色器将字体文本更改为您喜欢的颜色。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-255">Use the color picker to change the font text to a color that you like.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-edit2.msft.png" alt-text="通过拾色器将字体颜色更改为紫色" lightbox="../media/beginners-css-edit2.msft.png":::
       <span data-ttu-id="fdd9a-257">通过拾色器将字体颜色更改为紫色</span><span class="sxs-lookup"><span data-stu-id="fdd9a-257">Change the font color to purple with the Color Picker</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="fdd9a-258">在 DevTools 中添加新的规则集</span><span class="sxs-lookup"><span data-stu-id="fdd9a-258">Add a new ruleset in DevTools</span></span>  

<span data-ttu-id="fdd9a-259">完成以下操作以在 DevTools 中添加新的规则集。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-259">Complete the following actions to add new rulesets in DevTools.</span></span>  

1.  <span data-ttu-id="fdd9a-260">选择 " **新建样式规则** \ (![ 新样式规则 ][ImageNewStyleRuleIcon] \ ) 它位于" **. cls**"旁边。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-260">Choose **New Style Rule** \(![New Style Rule][ImageNewStyleRuleIcon]\) which is next to **.cls**.</span></span>  <span data-ttu-id="fdd9a-261">将显示一个包含选择器的空规则集 `a` 。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-261">An empty ruleset appears with `a` as the selector.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-rule1.msft.png" alt-text="添加新规则" lightbox="../media/beginners-css-rule1.msft.png":::
       <span data-ttu-id="fdd9a-263">添加新规则</span><span class="sxs-lookup"><span data-stu-id="fdd9a-263">Add a new rule</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="fdd9a-264">用 `a:hover` 取代 `a`。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-264">Replace `a` with `a:hover`.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-rule2.msft.png" alt-text="将 with a:hover 替换为" lightbox="../media/beginners-css-rule2.msft.png":::
       <span data-ttu-id="fdd9a-266">替换 `a` 为</span><span class="sxs-lookup"><span data-stu-id="fdd9a-266">Replace `a` with</span></span> `a:hover`  
    :::image-end:::  
    
    `:hover` <span data-ttu-id="fdd9a-267">是 **伪类**。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-267">is a **pseudo-class**.</span></span>  <span data-ttu-id="fdd9a-268">对可能进入特殊状态的样式元素使用伪类。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-268">Use pseudo-classes for style elements that may enter special states.</span></span>  <span data-ttu-id="fdd9a-269">例如， `a:hover` 仅当你将鼠标悬停在某个元素上方时，该样式才会生效 `<a>` 。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-269">For example, the `a:hover` style only takes effect when you are hovering over an `<a>` element.</span></span>  
    
1.  <span data-ttu-id="fdd9a-270">在括号之间进行选择以添加新的声明。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-270">Choose between the brackets to add a new declaration.</span></span>  
1.  <span data-ttu-id="fdd9a-271">键入 `background-color` 声明名称，然后选择 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-271">Type `background-color` for the declaration name and select `Enter`.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-rule3.msft.png" alt-text="键入背景色" lightbox="../media/beginners-css-rule3.msft.png":::
       <span data-ttu-id="fdd9a-273">类型</span><span class="sxs-lookup"><span data-stu-id="fdd9a-273">Type</span></span> `background-color`  
    :::image-end:::  
    
1.  <span data-ttu-id="fdd9a-274">`green`声明值的类型，然后选择 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-274">Type `green` for the declaration value and select `Enter`.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-rule4.msft.png" alt-text="键入绿色" lightbox="../media/beginners-css-rule4.msft.png":::
       <span data-ttu-id="fdd9a-276">类型</span><span class="sxs-lookup"><span data-stu-id="fdd9a-276">Type</span></span> `green`  
    :::image-end:::  
    
1.  <span data-ttu-id="fdd9a-277">将鼠标悬停在 " **开始** " 链接上。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-277">Hover your mouse over the **Home** link.</span></span>  <span data-ttu-id="fdd9a-278">链接的背景变为绿色。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-278">The background of the link turns green.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-rule5.msft.png" alt-text="将鼠标悬停在 Home 链接上以显示绿色背景" lightbox="../media/beginners-css-rule5.msft.png":::
       <span data-ttu-id="fdd9a-280">将鼠标悬停在 Home 链接上以显示绿色背景</span><span class="sxs-lookup"><span data-stu-id="fdd9a-280">Hover over the Home link to reveal its green background</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="fdd9a-281">跨页面使用外部样式表重新使用样式</span><span class="sxs-lookup"><span data-stu-id="fdd9a-281">Re-use styles across pages with external stylesheets</span></span>  

<span data-ttu-id="fdd9a-282">在上一步中，你将以下代码段添加为内部样式表 `contact.html` 。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-282">In a previous step, you added the following code snippet as an internal stylesheet to `contact.html`.</span></span>  

```html
...
    ...
        ...
        <style>
            li a, h1 {
              font-family: 'Courier New', Courier, Serif;
            }
        </style>
        ...
    ...
...
```  

<span data-ttu-id="fdd9a-283">如果你想要以 `index.html` 相同的方式设置样式，该怎么办？</span><span class="sxs-lookup"><span data-stu-id="fdd9a-283">What if you wanted to style `index.html` the same way?</span></span>  <span data-ttu-id="fdd9a-284">如果您有大量页面需要应用样式，该怎么办？</span><span class="sxs-lookup"><span data-stu-id="fdd9a-284">What if you had a large number of pages to which you wanted to apply your styles?</span></span>  <span data-ttu-id="fdd9a-285">您必须将内部样式表复制并粘贴到您的网站上的每一个网页中。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-285">You would have to copy and paste the internal stylesheet into every single web page on your site.</span></span>  <span data-ttu-id="fdd9a-286">完成以下操作以添加 **外部样式表** ，以允许你编写 CSS 一次并将其应用于多个页面。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-286">Complete the following actions to add an **External stylesheet** to allow you to write your CSS once and apply it to multiple pages.</span></span>  

1.  <span data-ttu-id="fdd9a-287">首先，重新加载 "实时" 选项卡以删除您在 DevTools 中所做的更改。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-287">First, reload the live tab to remove the changes that you made in DevTools.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-external1.msft.png" alt-text=" 刷新页面后，在 DevTools 中所做的更改将不再存在" lightbox="../media/beginners-css-external1.msft.png":::
        <span data-ttu-id="fdd9a-289">刷新页面后，在 DevTools 中所做的更改将不再存在</span><span class="sxs-lookup"><span data-stu-id="fdd9a-289">After you refresh the page, the changes that were made in DevTools are gone</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="fdd9a-290">返回 " **编辑器" 选项卡** ，然后打开 `contact.html` 。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-290">Go back to the **editor tab** and open `contact.html`.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-external2.msft.png" alt-text="contact.html" lightbox="../media/beginners-css-external2.msft.png":::
       <span data-ttu-id="fdd9a-292">contact.html</span><span class="sxs-lookup"><span data-stu-id="fdd9a-292">contact.html</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="fdd9a-293">删除与之间的所有内容 `<style>` `</style>` ，包括 `<style>` 和 `</style>` 。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-293">Delete everything between `<style>` and `</style>`, including `<style>` and `</style>`.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-external3.msft.png" alt-text="已删除样式标记" lightbox="../media/beginners-css-external3.msft.png":::
       <span data-ttu-id="fdd9a-295">已删除样式标记</span><span class="sxs-lookup"><span data-stu-id="fdd9a-295">The style tag has been removed</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="fdd9a-296">转到 `index.html` 并 `style="background-color: aliceblue;"` 从标记中删除 `<nav>` 。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-296">Go to `index.html` and remove `style="background-color: aliceblue;"` from the `<nav>` tag.</span></span>  <span data-ttu-id="fdd9a-297">您现在已删除以前添加到网站的所有 CSS。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-297">You have now removed all of the CSS that you previously added to your site.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-external4.msft.png" alt-text="内联样式已从导航元素中删除" lightbox="../media/beginners-css-external4.msft.png":::
       <span data-ttu-id="fdd9a-299">内联样式已从导航元素中删除</span><span class="sxs-lookup"><span data-stu-id="fdd9a-299">The inline style has been removed from the nav element</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="fdd9a-300">选择 " **新建文件**"。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-300">Choose **New File**.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-external5.msft.png" alt-text=""新建文件" 对话框" lightbox="../media/beginners-css-external5.msft.png":::
       <span data-ttu-id="fdd9a-302">"新建文件" 对话框</span><span class="sxs-lookup"><span data-stu-id="fdd9a-302">The new file dialog</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="fdd9a-303">替换 `cool-file.js` 为 `style.css` ，然后选择 " **添加文件**"。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-303">Replace `cool-file.js` with `style.css` and choose **Add File**.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-external6.msft.png" alt-text="类型样式 .css" lightbox="../media/beginners-css-external6.msft.png":::
       <span data-ttu-id="fdd9a-305">类型</span><span class="sxs-lookup"><span data-stu-id="fdd9a-305">Type</span></span> `style.css`  
    :::image-end:::  
    
1.  <span data-ttu-id="fdd9a-306">将以下代码片段添加到 `style.css` 文件中。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-306">Add the following code snippet to your `style.css` file.</span></span>  
    
    ```css
    li a, h1 {
      font-family: 'Courier New', Courier, Serif;
    }
    a:hover {
      background-color: green;
    }
    nav {
      background-color: aliceblue;
    }
    ```  
    
    :::image type="complex" source="../media/beginners-css-external7.msft.png" alt-text="将代码添加到样式 .css" lightbox="../media/beginners-css-external7.msft.png":::
       <span data-ttu-id="fdd9a-308">将代码添加到</span><span class="sxs-lookup"><span data-stu-id="fdd9a-308">Add code to</span></span> `style.css`  
    :::image-end:::  
    
    <span data-ttu-id="fdd9a-309">确保已创建外部样式表。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-309">Ensure that you have created an external stylesheet.</span></span> <span data-ttu-id="fdd9a-310">你的 HTML 不知道它是否存在。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-310">Your HTML is not aware that it exists.</span></span>  
    
1.  <span data-ttu-id="fdd9a-311">打开 `index.html`。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-311">Open `index.html`.</span></span>  
1.  <span data-ttu-id="fdd9a-312">添加 `<link rel="stylesheet" href="style.css">` 到你的 HTML。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-312">Add `<link rel="stylesheet" href="style.css">` to your HTML.</span></span>  
    
    ```html
    <head>
        ...
        <meta name="viewport" content="width=device-width, initial-scale=1">
        <link rel="stylesheet" href="style.css">
    </head>
    ```  
    
    :::image type="complex" source="../media/beginners-css-external8.msft.png" alt-text="链接到样式 .css" lightbox="../media/beginners-css-external8.msft.png":::
       <span data-ttu-id="fdd9a-314">链接到</span><span class="sxs-lookup"><span data-stu-id="fdd9a-314">Link to</span></span> `style.css`  
    :::image-end:::  
    
1.  <span data-ttu-id="fdd9a-315">打开 `contact.html` 文件并在其中添加链接。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-315">Open the `contact.html` file and add the link there.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-external9.msft.png" alt-text="链接到 contact.html 中的 "css"" lightbox="../media/beginners-css-external9.msft.png":::
       <span data-ttu-id="fdd9a-317">链接到 `style.css`</span><span class="sxs-lookup"><span data-stu-id="fdd9a-317">Link to `style.css` in</span></span> `contact.html`  
    :::image-end:::  
    
1.  <span data-ttu-id="fdd9a-318">转到 " **实时" 选项卡**。 现在，主页的字体与上一节中的字体相同，并具有蓝色导航部分。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-318">Go to the **live tab**.  The home page now has the same font from the last section and a blue navigation section.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-external10.msft.png" alt-text="主页" lightbox="../media/beginners-css-external10.msft.png":::
       <span data-ttu-id="fdd9a-320">主页</span><span class="sxs-lookup"><span data-stu-id="fdd9a-320">The home page</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="fdd9a-321">选择 **联系人** 链接转到 "联系人" 页面。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-321">Choose the **Contact** link to go to the contact page.</span></span>  <span data-ttu-id="fdd9a-322">"联系人" 页面的格式与 "主页" 的格式相同。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-322">The contact page has the same formatting as the home page.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-external11.msft.png" alt-text=""联系人" 页面" lightbox="../media/beginners-css-external11.msft.png":::
       <span data-ttu-id="fdd9a-324">"联系人" 页面</span><span class="sxs-lookup"><span data-stu-id="fdd9a-324">The contact page</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="fdd9a-325">使用 CSS 框架</span><span class="sxs-lookup"><span data-stu-id="fdd9a-325">Use a CSS framework</span></span>  

<span data-ttu-id="fdd9a-326">**CSS 框架** 是由其他开发者构建的样式的集合，可使创建引人注目的网站更容易。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-326">**CSS frameworks** are collections of styles built by other developers that make it easier to create attractive web sites.</span></span>  <span data-ttu-id="fdd9a-327">框架提供了可在页面元素上使用的样式集合，而不是自己定义样式。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-327">Instead of defining styles yourself, a framework provides you a collection of styles that you are able to use on your page elements.</span></span>  

1.  <span data-ttu-id="fdd9a-328">复制以下代码：</span><span class="sxs-lookup"><span data-stu-id="fdd9a-328">Copy the following code:</span></span>  
    
    ```html
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.1.1/css/bootstrap.min.css">
    ```  
    
1.  <span data-ttu-id="fdd9a-329">转到 "编辑" 选项卡，然后将代码粘贴到 `contact.html` 。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-329">Go to the editing tab and paste the code into `contact.html`.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-framework1.msft.png" alt-text="链接到 contact.html 中的框架" lightbox="../media/beginners-css-framework1.msft.png":::
       <span data-ttu-id="fdd9a-331">链接到中的框架</span><span class="sxs-lookup"><span data-stu-id="fdd9a-331">Link to the framework in</span></span> `contact.html`  
    :::image-end:::  
    
1.  <span data-ttu-id="fdd9a-332">打开 `index.html` 文件并在其中添加代码。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-332">Open the `index.html` file and add the code there.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-framework2.msft.png" alt-text="链接到 index.html 中的框架" lightbox="../media/beginners-css-framework2.msft.png":::
       <span data-ttu-id="fdd9a-334">链接到中的框架</span><span class="sxs-lookup"><span data-stu-id="fdd9a-334">Link to the framework in</span></span> `index.html`  
    :::image-end:::  
    
1.  <span data-ttu-id="fdd9a-335">返回到 "实时" 选项卡以查看所做的更改。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-335">Go back to the live tab to view your changes.</span></span>  <span data-ttu-id="fdd9a-336">虽然元素的背景色 `<nav>` 和 `<li>` 和元素的字体 `<a>` 相同，但其他元素的字体已更改。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-336">While the background color of the `<nav>` element and the font of the `<li>` and `<a>` elements are the same, the font of the other elements has changed.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-framework3.msft.png" alt-text="主页面上的某些字体因框架而发生更改" lightbox="../media/beginners-css-framework3.msft.png":::
       <span data-ttu-id="fdd9a-338">主页面上的某些字体因框架而发生更改</span><span class="sxs-lookup"><span data-stu-id="fdd9a-338">Some of the font on the home page changed because of the framework</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="fdd9a-339">使用类</span><span class="sxs-lookup"><span data-stu-id="fdd9a-339">Use a class</span></span>  

<span data-ttu-id="fdd9a-340">在最后一节中，你将引导数据库添加到网页，这将更改网站上某些元素的字体。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-340">In the last section, you added Bootstrap to your web pages, which changed the fonts of some of the elements on your site.</span></span>  <span data-ttu-id="fdd9a-341">CSS 框架可帮助你通过非常少的代码对页面进行重大更改。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-341">CSS frameworks help you make major changes to your page with very little code.</span></span>  <span data-ttu-id="fdd9a-342">完成以下操作以更改页眉。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-342">Complete the following actions to change your header.</span></span>  

1.  <span data-ttu-id="fdd9a-343">复制以下代码片段。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-343">Copy the following code snippet.</span></span>  
    
    ```html
    class="jumbotron jumbotron-fluid"  
    ```  
    
1.  <span data-ttu-id="fdd9a-344">将上一个代码段添加到 `<header>` 中的标记 `index.html` 。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-344">Add the previous code snippet to your `<header>` tag in `index.html`.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-jumbotron1.msft.png" alt-text="在 index.html 中添加类" lightbox="../media/beginners-css-jumbotron1.msft.png":::
       <span data-ttu-id="fdd9a-346">将类添加到</span><span class="sxs-lookup"><span data-stu-id="fdd9a-346">Add classes in</span></span> `index.html`  
    :::image-end:::  
    
1.  <span data-ttu-id="fdd9a-347">将代码添加到 `<header>` 中的标记 `contact.html` 。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-347">Add the code to your `<header>` tag in `contact.html`.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-jumbotron2.msft.png" alt-text="在 contact.html 中添加类" lightbox="../media/beginners-css-jumbotron2.msft.png":::
       <span data-ttu-id="fdd9a-349">将类添加到</span><span class="sxs-lookup"><span data-stu-id="fdd9a-349">Add classes in</span></span> `contact.html`  
    :::image-end:::  
    
1.  <span data-ttu-id="fdd9a-350">在 "实时" 选项卡中查看所做的更改。 页眉周围有一个大灰的框。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-350">View your changes in the live tab.  There is a big, grey box around your header.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-jumbotron3.msft.png" alt-text="标题现在周围有一个大灰框" lightbox="../media/beginners-css-jumbotron3.msft.png":::
       <span data-ttu-id="fdd9a-352">标题现在周围有一个大灰框</span><span class="sxs-lookup"><span data-stu-id="fdd9a-352">The header now has a big, grey box around it</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="fdd9a-353">了解类</span><span class="sxs-lookup"><span data-stu-id="fdd9a-353">Understand classes</span></span>  

<span data-ttu-id="fdd9a-354">通过类，你可以将样式集合分配给任意元素。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-354">Classes let you assign collections of styles to arbitrary elements.</span></span>  <span data-ttu-id="fdd9a-355">`<header>`将属性设置为后，使用以下代码片段对元素应用多个样式 `class` `jumbotron` 。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-355">Use the following code snippet to apply several styles to the `<header>` element after you set the `class` attribute to `jumbotron`.</span></span>  

```css
.jumbotron {
  padding: 2rem 1rem;
  margin-bottom: 2rem;
  background-color: #e9ecef;
  border-radius: .3rem;
}
```  

<span data-ttu-id="fdd9a-356">类的一个优点是允许你将样式应用到所需的任何元素。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-356">One advantage of a class is that it lets you apply styles to whatever elements you want.</span></span>  <span data-ttu-id="fdd9a-357">例如，假设你想要将某些元素的背景色设置 `<p>` 为紫色，而不是所有 `<p>` 元素。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-357">For example, suppose you want to set the background color of some `<p>` elements to purple, but not all `<p>` elements.</span></span>  <span data-ttu-id="fdd9a-358">使用以下代码片段定义类中的样式。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-358">Use the following code snippet to define the style in a class.</span></span>  

```css
.custom-background {
  background-color: purple;
}
```  

<span data-ttu-id="fdd9a-359">接下来，将该类应用于 `<p>` 要样式的元素。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-359">Next, apply the class to only the `<p>` elements that you want to style.</span></span>  

```html
<p>The text is not purple.</p>
<p class="custom-background">The text is purple.</p>
<p>The text is not purple.</p>
<p class="custom-background">The text is purple.</p>
```  

### <span data-ttu-id="fdd9a-360">对齐元素</span><span class="sxs-lookup"><span data-stu-id="fdd9a-360">Align elements</span></span>  

<span data-ttu-id="fdd9a-361">完成以下操作以执行引导并提供用于对齐元素的类。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-361">Complete the following actions to bootstrap and provide classes for aligning elements.</span></span>  

1.  <span data-ttu-id="fdd9a-362">返回 "编辑器" 选项卡，然后打开 `index.html` 。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-362">Go back to the editor tab and open `index.html`.</span></span>  
1.  <span data-ttu-id="fdd9a-363">添加 `class="container-fluid"` 到您的 `<body>` 标签。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-363">Add `class="container-fluid"` to your `<body>` tag.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-align1.msft.png" alt-text="添加容器流体类" lightbox="../media/beginners-css-align1.msft.png":::
       <span data-ttu-id="fdd9a-365">添加 `container-fluid` 类</span><span class="sxs-lookup"><span data-stu-id="fdd9a-365">Add the `container-fluid` class</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="fdd9a-366">将您的 `<nav>` 和 `<main>` 元素包装在中 `<div class="row">` 。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-366">Wrap your `<nav>` and `<main>` elements in `<div class="row">`.</span></span>  <span data-ttu-id="fdd9a-367">请确保放 `</div>` `</main>` 在 "" 之后，才能正确关闭新标记。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-367">Make sure to put `</div>` after `</main>` in order to properly close the new tag.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-align2.msft.png" alt-text="添加行" lightbox="../media/beginners-css-align2.msft.png":::
       <span data-ttu-id="fdd9a-369">添加行</span><span class="sxs-lookup"><span data-stu-id="fdd9a-369">Add a row</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="fdd9a-370">添加 `class="col-3"` 到您的 `<nav>` 标签和 `class="col-9"` `<main>` 标签。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-370">Add `class="col-3"` to your `<nav>` tag and `class="col-9"` to your `<main>` tag.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-align3.msft.png" alt-text="添加列3和 col-9 类" lightbox="../media/beginners-css-align3.msft.png":::
       <span data-ttu-id="fdd9a-372">添加 `col-3` 和 `col-9` 类</span><span class="sxs-lookup"><span data-stu-id="fdd9a-372">Add the `col-3` and `col-9` classes</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="fdd9a-373">在 "实时" 选项卡中查看所做的更改。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-373">View your changes in the live tab.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-align4.msft.png" alt-text="导航内容现在位于主要内容的左侧" lightbox="../media/beginners-css-align4.msft.png":::
       <span data-ttu-id="fdd9a-375">导航内容现在位于主要内容的左侧</span><span class="sxs-lookup"><span data-stu-id="fdd9a-375">The nav content is now to the left of the main content</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="fdd9a-376">后续步骤</span><span class="sxs-lookup"><span data-stu-id="fdd9a-376">Next steps</span></span>  

<span data-ttu-id="fdd9a-377">恭喜！您已完成。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-377">Congratulations, you are done.</span></span>  

*   <span data-ttu-id="fdd9a-378">在 web 开发中获取更好的最佳方式是构建更多网站。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-378">The best way to get better at web development is to build more sites.</span></span>  <span data-ttu-id="fdd9a-379">不要担心会破坏内容。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-379">Do not worry about breaking stuff.</span></span>  <span data-ttu-id="fdd9a-380">只要有兴趣，您就可以轻松掌握。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-380">Just have fun and learn as much as possible along the way.</span></span>  
*   <span data-ttu-id="fdd9a-381">若要了解有关设置网页样式的详细信息，请参阅 [CSS 简介][MDNCssFirstSteps]。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-381">To learn more about styling web pages, see [Introduction to CSS][MDNCssFirstSteps].</span></span>  
*   <span data-ttu-id="fdd9a-382">若要了解有关如何使用 DevTools 来试验页面 CSS 的详细信息，请参阅 [查看和更改 Css 入门][DevtoolsCssIndex]。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-382">To learn more about how to use DevTools to experiment with the CSS of a page, see [Get Started with Viewing and Changing CSS][DevtoolsCssIndex].</span></span>  

<!--- image links --->  

[ImageNewStyleRuleIcon]: ../media/new-style-rule-icon.msft.png  

<!--- links  --->  

[DevtoolsBeginnersHtml]: ./html.md "初学者的 DevTools： HTML 和 DOM 入门 |Microsoft 文档"  
[DevtoolsCssIndex]: ../css/index.md "开始使用查看和更改 CSS |Microsoft 文档"  

[MicrosoftEdgeInsider]: https://www.microsoftedgeinsider.com "Microsoft Edge 预览体验成员"  

[GlitchCookedAmphibianIndex]: https://glitch.com/edit/#!/cooked-amphibian?path=index.html "index.html-cooked-amphibian |故障"  

[MDNCssFirstSteps]: https://developer.mozilla.org/docs/Learn/CSS/Introduction_to_CSS "CSS 优先步骤 |MDN"  

> [!NOTE]
> <span data-ttu-id="fdd9a-388">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-388">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="fdd9a-389">原始页面位于 [此处](https://developers.google.com/web/tools/chrome-devtools/beginners/css) ，由 [Katherine 杰克逊][KatherineJackson] (技术编写器暂存，Chrome DevTools \ ) 。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-389">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/beginners/css) and is authored by [Katherine Jackson][KatherineJackson] \(Technical Writer Intern, Chrome DevTools\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="fdd9a-391">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="fdd9a-391">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[KatherineJackson]: https://developers.google.com/web/resources/contributors/katjackson  
