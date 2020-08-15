---
title: 初学者的 DevTools：开始使用 CSS
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/14/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 6e005f4107764a13934f0c8f3b3cde0ab9bf98c2
ms.sourcegitcommit: 054ad92f0b8f9a15da1e3aed32e8f4379b10860f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/15/2020
ms.locfileid: "10931592"
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

# <span data-ttu-id="8a575-103">初学者的 DevTools：开始使用 CSS</span><span class="sxs-lookup"><span data-stu-id="8a575-103">DevTools for beginners: Get started with CSS</span></span>  

<span data-ttu-id="8a575-104">在本教程中，你将了解如何使用 CSS 对网页进行样式。</span><span class="sxs-lookup"><span data-stu-id="8a575-104">In this tutorial, you learn how to use CSS to style a web page.</span></span>  <span data-ttu-id="8a575-105">你还将了解如何使用 Microsoft Edge DevTools 来试验 CSS 更改。</span><span class="sxs-lookup"><span data-stu-id="8a575-105">You also learn how to use Microsoft Edge DevTools to experiment with CSS changes.</span></span>  

<span data-ttu-id="8a575-106">以下文章是一系列教程中的第二个教程，可教你了解 web 开发和 Microsoft Edge DevTools 的基础知识。</span><span class="sxs-lookup"><span data-stu-id="8a575-106">The following article is the second tutorial in a series of tutorials that teaches you the basics of web development and Microsoft Edge DevTools.</span></span>  <span data-ttu-id="8a575-107">您可以通过实际构建自己的网站来获得实际体验。</span><span class="sxs-lookup"><span data-stu-id="8a575-107">You gain hands-on experience by actually building your own website.</span></span>  <span data-ttu-id="8a575-108">在下一步操作之前，不必完成第一个教程。</span><span class="sxs-lookup"><span data-stu-id="8a575-108">You do not have to complete the first tutorial before following the second.</span></span>  <span data-ttu-id="8a575-109">[设置代码](#set-up-your-code) 显示如何设置。</span><span class="sxs-lookup"><span data-stu-id="8a575-109">[Set up your code](#set-up-your-code) shows you how to get set up.</span></span>  

> [!NOTE]
> <span data-ttu-id="8a575-110">本教程适用于绝对初学者，重点介绍 **web 开发的基础知识** 和使用 DEVTOOLS 试验 CSS 的基础知识。</span><span class="sxs-lookup"><span data-stu-id="8a575-110">This tutorial is designed for absolute beginners and focuses on both the **fundamentals of web development** and the basics of using DevTools to experiment with CSS.</span></span>  <span data-ttu-id="8a575-111">如果你需要仅关注 DevTools 的教程，请参阅 [查看和更改 CSS 入门][DevtoolsCssIndex]。</span><span class="sxs-lookup"><span data-stu-id="8a575-111">If you want a tutorial that only focuses on DevTools, see [Get Started with Viewing and Changing CSS][DevtoolsCssIndex].</span></span>  

<span data-ttu-id="8a575-112">在教程的开头，您的网站应如下图所示。</span><span class="sxs-lookup"><span data-stu-id="8a575-112">At the beginning of the tutorial, your site should look like the following figure.</span></span>  

:::image type="complex" source="../media/beginners-css-intro1.msft.png" alt-text="网站的当前外观" lightbox="../media/beginners-css-intro1.msft.png":::
   <span data-ttu-id="8a575-114">网站的当前外观</span><span class="sxs-lookup"><span data-stu-id="8a575-114">What your site currently looks like</span></span>  
:::image-end:::  

<span data-ttu-id="8a575-115">完成教程后，您的网站应如下图所示。</span><span class="sxs-lookup"><span data-stu-id="8a575-115">After you complete the tutorial, you site should look like the following figure.</span></span>  

:::image type="complex" source="../media/beginners-css-intro2.msft.png" alt-text="您的网站在教程结束时应看起来是什么样子" lightbox="../media/beginners-css-intro2.msft.png":::
   <span data-ttu-id="8a575-117">您的网站在教程结束时应看起来是什么样子</span><span class="sxs-lookup"><span data-stu-id="8a575-117">What your site should look like at the end of the tutorial</span></span>  
:::image-end:::  

## <span data-ttu-id="8a575-118">目标</span><span class="sxs-lookup"><span data-stu-id="8a575-118">Goals</span></span>  

<span data-ttu-id="8a575-119">按照此教程更好地了解以下概念和任务。</span><span class="sxs-lookup"><span data-stu-id="8a575-119">Follow this tutorial to better understand the following concepts and tasks.</span></span>  

*   <span data-ttu-id="8a575-120">如何使用 CSS 对网页进行样式。</span><span class="sxs-lookup"><span data-stu-id="8a575-120">How to use CSS to style a web page.</span></span>  
*   <span data-ttu-id="8a575-121">如何使用 Microsoft Edge DevTools 来试验 CSS。</span><span class="sxs-lookup"><span data-stu-id="8a575-121">How to use Microsoft Edge DevTools to experiment with CSS.</span></span>  
*   <span data-ttu-id="8a575-122">CSS 和 CSS 框架之间的区别。</span><span class="sxs-lookup"><span data-stu-id="8a575-122">The difference between CSS and CSS frameworks.</span></span>  

<span data-ttu-id="8a575-123">您正在构建真正的网站。</span><span class="sxs-lookup"><span data-stu-id="8a575-123">You are building a real website.</span></span>  

## <span data-ttu-id="8a575-124">先决条件</span><span class="sxs-lookup"><span data-stu-id="8a575-124">Prerequisites</span></span>  

<span data-ttu-id="8a575-125">在尝试本教程之前，请完成以下先决条件。</span><span class="sxs-lookup"><span data-stu-id="8a575-125">Before attempting this tutorial, complete the following prerequisites.</span></span>  

*   <span data-ttu-id="8a575-126">完整 [入门 html 和 dom，][DevtoolsBeginnersHtml] 或者确保你对 HTML 和 dom 的理解与该教程中所讲授的内容类似。</span><span class="sxs-lookup"><span data-stu-id="8a575-126">Complete [Get Started with HTML and the DOM][DevtoolsBeginnersHtml] or make sure that you have an understanding of HTML and the DOM similar to what is taught in that tutorial.</span></span>  
*   <span data-ttu-id="8a575-127">下载 [Microsoft Edge][MicrosoftEdgeInsider] web 浏览器。</span><span class="sxs-lookup"><span data-stu-id="8a575-127">Download the [Microsoft Edge][MicrosoftEdgeInsider] web browser.</span></span>  <span data-ttu-id="8a575-128">以下教程使用一组称为 Microsoft Edge DevTools 的 web 开发工具，这些工具内置于 Microsoft Edge 中。</span><span class="sxs-lookup"><span data-stu-id="8a575-128">The following tutorial uses a set of web development tools, called the Microsoft Edge DevTools, that are built into Microsoft Edge.</span></span>  

## <span data-ttu-id="8a575-129">设置代码</span><span class="sxs-lookup"><span data-stu-id="8a575-129">Set up your code</span></span>  

<span data-ttu-id="8a575-130">若要创建网站，必须首先完成以下操作来设置代码。</span><span class="sxs-lookup"><span data-stu-id="8a575-130">To create your site, you must first complete the following actions to set up your code.</span></span>  

> [!NOTE]
> <span data-ttu-id="8a575-131">如果您已完成系列中的第一个教程，请跳至下一节。</span><span class="sxs-lookup"><span data-stu-id="8a575-131">If you have already completed the first tutorial in the series, skip to the next section.</span></span>  <span data-ttu-id="8a575-132">继续使用最后一个教程中的代码， [HTML 和 DOM 入门][DevtoolsBeginnersHtml]。</span><span class="sxs-lookup"><span data-stu-id="8a575-132">Continue using your code from the last tutorial, [Get Started with HTML and the DOM][DevtoolsBeginnersHtml].</span></span>  

1.  <span data-ttu-id="8a575-133">打开 [源代码][GlitchCookedAmphibianIndex]。</span><span class="sxs-lookup"><span data-stu-id="8a575-133">Open the [source code][GlitchCookedAmphibianIndex].</span></span>  <span data-ttu-id="8a575-134">浏览器的 "聚焦" 选项卡作为 " **编辑" 选项卡**进行引用。</span><span class="sxs-lookup"><span data-stu-id="8a575-134">The in-focus tab of your browser is referenced as the **editing tab**.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-setup1.msft.png" alt-text=""编辑" 选项卡" lightbox="../media/beginners-css-setup1.msft.png":::
       <span data-ttu-id="8a575-136">" **编辑** " 选项卡</span><span class="sxs-lookup"><span data-stu-id="8a575-136">The **editing** tab</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="8a575-137">选择 **cooked-amphibian**。</span><span class="sxs-lookup"><span data-stu-id="8a575-137">Choose **cooked-amphibian**.</span></span>  <span data-ttu-id="8a575-138">将弹出一个菜单。</span><span class="sxs-lookup"><span data-stu-id="8a575-138">A menu pops up.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-setup2.msft.png" alt-text=""项目选项" 菜单" lightbox="../media/beginners-css-setup2.msft.png":::
       <span data-ttu-id="8a575-140">"项目选项" 菜单</span><span class="sxs-lookup"><span data-stu-id="8a575-140">The Project Options menu</span></span>  
    :::image-end:::  

1.  <span data-ttu-id="8a575-141">选择 " **Remix Project**"。</span><span class="sxs-lookup"><span data-stu-id="8a575-141">Choose **Remix Project**.</span></span>  <span data-ttu-id="8a575-142">问题创建您可以编辑的项目副本。</span><span class="sxs-lookup"><span data-stu-id="8a575-142">Glitch creates a copy of the project that you are able to edit.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="8a575-143">故障为新项目生成一个随机名称。</span><span class="sxs-lookup"><span data-stu-id="8a575-143">Glitch generates a random name for the new project.</span></span>  
    
1.  <span data-ttu-id="8a575-144">**在新窗口中选择 "\*\*\*\*显示**并选择"。</span><span class="sxs-lookup"><span data-stu-id="8a575-144">Choose **Show** and select **In a New Window**.</span></span>  <span data-ttu-id="8a575-145">将打开另一个选项卡，其中包含您的网站的实时视图。</span><span class="sxs-lookup"><span data-stu-id="8a575-145">Another tab opens with a live view of your site.</span></span>  <span data-ttu-id="8a575-146">浏览器的 "聚焦" 选项卡作为 " **实时" 选项卡**进行引用。</span><span class="sxs-lookup"><span data-stu-id="8a575-146">The in-focus tab of your browser is referenced as the **live tab**.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-setup3.msft.png" alt-text=""实时" 选项卡" lightbox="../media/beginners-css-setup3.msft.png":::
       <span data-ttu-id="8a575-148">" **实时" 选项卡**</span><span class="sxs-lookup"><span data-stu-id="8a575-148">The **live tab**</span></span>  
    :::image-end:::  

## <span data-ttu-id="8a575-149">了解 CSS</span><span class="sxs-lookup"><span data-stu-id="8a575-149">Understand CSS</span></span>  

<span data-ttu-id="8a575-150">**CSS** 是确定网页布局和样式的计算机语言。</span><span class="sxs-lookup"><span data-stu-id="8a575-150">**CSS** is a computer language that determines the layout and styling of web pages.</span></span>  <span data-ttu-id="8a575-151">下图是带有边框的段落。</span><span class="sxs-lookup"><span data-stu-id="8a575-151">The following figure is a paragraph with a border.</span></span>  

:::image type="complex" source="../media/beginners-css-red_paragraph.msft.png" alt-text="文本已采用 CSS 样式" lightbox="../media/beginners-css-red_paragraph.msft.png":::
   <span data-ttu-id="8a575-153">文本已采用 CSS 样式</span><span class="sxs-lookup"><span data-stu-id="8a575-153">The text has been styled with CSS</span></span>  
:::image-end:::  

<span data-ttu-id="8a575-154">以下代码片段是用于创建上图中的段落的 HTML 和 CSS 代码。</span><span class="sxs-lookup"><span data-stu-id="8a575-154">The following code snippet is the HTML and CSS code used to create the paragraph in the previous figure.</span></span>  

```html
<p style="border: 1px dashed red; padding: 5px;">
    This has been styled with CSS.
</p>
```  

`style="border: 1px dashed red; padding: 5px;"` <span data-ttu-id="8a575-155">可能看起来很新。</span><span class="sxs-lookup"><span data-stu-id="8a575-155">probably looks new to you.</span></span>  <span data-ttu-id="8a575-156">其余内容应熟悉。</span><span class="sxs-lookup"><span data-stu-id="8a575-156">The rest should look familiar.</span></span>  <span data-ttu-id="8a575-157">如果不是，请先 [开始使用 HTML 和 DOM][DevtoolsBeginnersHtml] ，然后再尝试以下部分。</span><span class="sxs-lookup"><span data-stu-id="8a575-157">If not, complete [Get Started with HTML and the DOM][DevtoolsBeginnersHtml] before attempting the following sections.</span></span>  

## <span data-ttu-id="8a575-158">添加内联样式</span><span class="sxs-lookup"><span data-stu-id="8a575-158">Add inline styles</span></span>  

<span data-ttu-id="8a575-159">完成以下操作以使用 **嵌入式样式** 将样式应用到单个元素。</span><span class="sxs-lookup"><span data-stu-id="8a575-159">Complete the following actions to use **inline styles** to apply styles to a single element.</span></span>  

1.  <span data-ttu-id="8a575-160">返回到 "编辑" 选项卡并打开 `index.html` 。</span><span class="sxs-lookup"><span data-stu-id="8a575-160">Go back to the editing tab and open `index.html`.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-inline1.msft.png" alt-text="index.html" lightbox="../media/beginners-css-inline1.msft.png":::
       <span data-ttu-id="8a575-162">`index.html`在 "编辑" 选项卡中打开</span><span class="sxs-lookup"><span data-stu-id="8a575-162">Open `index.html` in the editing tab</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="8a575-163">添加 `style="background-color: aliceblue;"` 到您 `<nav>` 的。</span><span class="sxs-lookup"><span data-stu-id="8a575-163">Add `style="background-color: aliceblue;"` to your `<nav>`.</span></span>  <span data-ttu-id="8a575-164">在下面的代码块中，第四行代码是你需要更改的代码。</span><span class="sxs-lookup"><span data-stu-id="8a575-164">In the code block below, the fourth line of code is the one you need to change.</span></span>  <span data-ttu-id="8a575-165">剩下的就是这样，因此您可以确保将新代码放入正确的位置。</span><span class="sxs-lookup"><span data-stu-id="8a575-165">The rest is just there, so you are able to ensure that you are putting the new code in the right place.</span></span>  
    
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
    
1.  <span data-ttu-id="8a575-166">转到 " **实时" 选项卡** 以查看所做的更改！</span><span class="sxs-lookup"><span data-stu-id="8a575-166">Go to the **live tab** to see the changes!</span></span>  <span data-ttu-id="8a575-167">现在，该分区的背景 `<nav>` 为蓝色。</span><span class="sxs-lookup"><span data-stu-id="8a575-167">The background of the `<nav>` section is now blue.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-inline2.msft.png" alt-text=""主页" 和 "联系人" 链接后面的背景色现在为蓝色" lightbox="../media/beginners-css-inline2.msft.png":::
       <span data-ttu-id="8a575-169">" **主页** " 和 " **联系人** " 链接后面的背景色现在为蓝色</span><span class="sxs-lookup"><span data-stu-id="8a575-169">The background color behind the **Home** and **Contact** links is now blue</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="8a575-170">在具有内部样式表的单个页面上重新使用样式</span><span class="sxs-lookup"><span data-stu-id="8a575-170">Re-use styles on a single page with internal stylesheets</span></span>  

<span data-ttu-id="8a575-171">在前面的代码段中，内联样式将样式应用于单个 `<p>` 标记。</span><span class="sxs-lookup"><span data-stu-id="8a575-171">In a previous code snippet, an inline style applied a style to a single `<p>` tag.</span></span>  

```html
<p style="border: 1px dashed red; padding: 5px;">
    This has been styled with CSS.
</p>
```  

<span data-ttu-id="8a575-172">如果您希望您的 `<p>` 网页上的所有元素的样式设置方式相同，该怎么办？</span><span class="sxs-lookup"><span data-stu-id="8a575-172">What if you wanted all of the `<p>` elements on your webpage to be styled the same way?</span></span>  <span data-ttu-id="8a575-173">您必须将代码复制并粘贴到 `<p>` 您的网站上的每个标记中。</span><span class="sxs-lookup"><span data-stu-id="8a575-173">You would have to copy and paste the code into every single `<p>` tag on your site.</span></span>  <span data-ttu-id="8a575-174">这是大量的时间和精力。</span><span class="sxs-lookup"><span data-stu-id="8a575-174">That is a lot of time and effort.</span></span>  <span data-ttu-id="8a575-175">如果需要进行编辑，则必须再次更改每个标签。</span><span class="sxs-lookup"><span data-stu-id="8a575-175">And, if you needed to make an edit, you would have to change every tag again.</span></span>  <span data-ttu-id="8a575-176">完成以下操作以使用 **内部样式表** 编写 CSS 一次，以便它应用于多个元素。</span><span class="sxs-lookup"><span data-stu-id="8a575-176">Complete the following actions to use an **Internal stylesheet** to write your CSS once so that it applies to multiple elements.</span></span>  

1.  <span data-ttu-id="8a575-177">在 "实时" 选项卡中，选择 " **联系人** " 以转到 "联系人" 页面。</span><span class="sxs-lookup"><span data-stu-id="8a575-177">In the live tab, choose **Contact** to go to the contact page.</span></span>  <span data-ttu-id="8a575-178">请注意 " **家庭** " 和 " **联系人**" 的字体。</span><span class="sxs-lookup"><span data-stu-id="8a575-178">Notice the font of **Home** and **Contact**.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-internal1.msft.png" alt-text=""联系人" 页面" lightbox="../media/beginners-css-internal1.msft.png":::
       <span data-ttu-id="8a575-180">"联系人" 页面</span><span class="sxs-lookup"><span data-stu-id="8a575-180">The Contact page</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="8a575-181">在 " **编辑器" 选项卡**中，转到 `contact.html` 。</span><span class="sxs-lookup"><span data-stu-id="8a575-181">In the **editor tab**, go to `contact.html`.</span></span>  
1.  <span data-ttu-id="8a575-182">将以下代码添加到 `contact.html` 。</span><span class="sxs-lookup"><span data-stu-id="8a575-182">Add the following code to `contact.html`.</span></span>  <span data-ttu-id="8a575-183">请记住，"行" `<style>` 和 "结束" 行 `</style>` 是你需要添加的内容。</span><span class="sxs-lookup"><span data-stu-id="8a575-183">Remember, the lines starting with `<style>` and ending with `</style>` are what you need to add.</span></span>  <span data-ttu-id="8a575-184">其他代码就在这里，您知道在哪里放置新代码。</span><span class="sxs-lookup"><span data-stu-id="8a575-184">The other code is just there so you know where to put the new code.</span></span>  
    
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
    
1.  <span data-ttu-id="8a575-185">返回到 " **实时" 选项卡**。</span><span class="sxs-lookup"><span data-stu-id="8a575-185">Go back to the **live tab**.</span></span>  
1.  <span data-ttu-id="8a575-186">选择 " **联系人** " 以返回到联系人页。</span><span class="sxs-lookup"><span data-stu-id="8a575-186">Choose **Contact** to go back to the contact page.</span></span>  <span data-ttu-id="8a575-187">**家庭**和**联系人**的字体已更改。</span><span class="sxs-lookup"><span data-stu-id="8a575-187">The font of **Home** and **Contact** has changed.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-internal2.msft.png" alt-text="主页和联系人链接的字体已更改" lightbox="../media/beginners-css-internal2.msft.png":::
       <span data-ttu-id="8a575-189">**主页**和**联系人**链接的字体已更改</span><span class="sxs-lookup"><span data-stu-id="8a575-189">The font of the **Home** and **Contact** links has changed</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="8a575-190">了解内部样式表</span><span class="sxs-lookup"><span data-stu-id="8a575-190">Understand internal stylesheets</span></span>  

<span data-ttu-id="8a575-191">内部样式表使用 **选择器**应用样式。</span><span class="sxs-lookup"><span data-stu-id="8a575-191">Internal stylesheets apply styles using **selectors**.</span></span>  <span data-ttu-id="8a575-192">选择器是可应用于一个或多个 HTML 元素的模式。</span><span class="sxs-lookup"><span data-stu-id="8a575-192">Selectors are patterns that may apply to one or more HTML elements.</span></span>  <span data-ttu-id="8a575-193">上面的代码段添加了以下样式。</span><span class="sxs-lookup"><span data-stu-id="8a575-193">The previous code snippet added the following style.</span></span>  

```html
<style>
    li a {
      font-family: 'Courier New', Courier, Serif;
    }
</style>
```  

`li a` <span data-ttu-id="8a575-194">是转换为 " `<li>` 包含元素的任何元素" 的选择器 `<a>` 。</span><span class="sxs-lookup"><span data-stu-id="8a575-194">is a selector that translates to "any `<li>` element that contains an `<a>` element".</span></span>  <span data-ttu-id="8a575-195">浏览器将更改 " **主页** " 和 " **联系人** " 链接的字体，因为每个标记组都与模式匹配。</span><span class="sxs-lookup"><span data-stu-id="8a575-195">The browser changes the font of the **Home** and **Contact** links because each of the tag groups match the pattern.</span></span>  

```html
<li><a href="/">Home</a></li>
<li><a href="/contact.html">Contact</a></li>
```  

`font-family: 'Courier New', Courier, serif` <span data-ttu-id="8a575-196">是 **声明**。</span><span class="sxs-lookup"><span data-stu-id="8a575-196">is a **declaration**.</span></span>  <span data-ttu-id="8a575-197">声明由以下两个部分组成。</span><span class="sxs-lookup"><span data-stu-id="8a575-197">A declaration is made of following two parts.</span></span>  

:::row:::
   :::column span="1":::
      **<span data-ttu-id="8a575-198">属性</span><span class="sxs-lookup"><span data-stu-id="8a575-198">property</span></span>**  
   :::column-end:::
   :::column span="1":::
      `font-family`  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="8a575-199">该属性描述你可以更改元素样式的一般方式。</span><span class="sxs-lookup"><span data-stu-id="8a575-199">The property describes a general way that you are able to change the style of the element.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="8a575-200">值</span><span class="sxs-lookup"><span data-stu-id="8a575-200">value</span></span>**  
   :::column-end:::
   :::column span="1":::
      `'Courier New', Courier, serif`  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="8a575-201">该值确切描述元素样式应如何更改。</span><span class="sxs-lookup"><span data-stu-id="8a575-201">The value describes exactly how the style of the element should change.</span></span>  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="8a575-202">例如， `font-family: 'Courier New', Courier, serif` 为浏览器提供以下指令： "将匹配模式的元素的字体设置 `li a` 为 `'Courier New'` 。</span><span class="sxs-lookup"><span data-stu-id="8a575-202">For example, `font-family: 'Courier New', Courier, serif` gives the browser the following instruction:  "Set the font of elements that match the pattern `li a` to `'Courier New'`.</span></span>  <span data-ttu-id="8a575-203">如果该字体不可用，请使用 `Courier` 。</span><span class="sxs-lookup"><span data-stu-id="8a575-203">If that font is not available, use `Courier`.</span></span>  <span data-ttu-id="8a575-204">如果该功能不可用，请使用 `serif` 。</span><span class="sxs-lookup"><span data-stu-id="8a575-204">If that is not available, use `serif`."</span></span>  

### <span data-ttu-id="8a575-205">将多个选择器添加到规则集</span><span class="sxs-lookup"><span data-stu-id="8a575-205">Add multiple selectors to a ruleset</span></span>  

<span data-ttu-id="8a575-206">类似于下面所示的 CSS 代码块称为 " **规则集**"。</span><span class="sxs-lookup"><span data-stu-id="8a575-206">A block of CSS code like what you see below is called a **ruleset**.</span></span>  

```css
li a {
  font-family: 'Courier New', Courier, monospace;
}
```  

<span data-ttu-id="8a575-207">完成以下操作以使用逗号将多个选择器添加到规则集。</span><span class="sxs-lookup"><span data-stu-id="8a575-207">Complete the following actions to use commas to add multiple selectors to a ruleset.</span></span>  

1.  <span data-ttu-id="8a575-208">在 " **编辑器" 选项卡**中，打开 `contact.html` 。</span><span class="sxs-lookup"><span data-stu-id="8a575-208">In the **editor tab**, open `contact.html`.</span></span>  
1.  <span data-ttu-id="8a575-209">`li a`键入后 `, h1` 。</span><span class="sxs-lookup"><span data-stu-id="8a575-209">After `li a` type `, h1`.</span></span>  
    
    ```html
    <style>
        li a, h1 {
          font-family: 'Courier New', Courier, Serif;
        }
    </style>
    ```  
    
    <span data-ttu-id="8a575-210">上面的代码片段告诉浏览器对元素的样式与 `<h1>` 与模式匹配的元素的样式相同 `li a` 。</span><span class="sxs-lookup"><span data-stu-id="8a575-210">The previous code snippet tells the browser to style `<h1>` elements the same way that it styles elements that match the pattern `li a`.</span></span>  
    
1.  <span data-ttu-id="8a575-211">转到 " **实时" 选项卡**。</span><span class="sxs-lookup"><span data-stu-id="8a575-211">Go to the **live tab**.</span></span>  
1.  <span data-ttu-id="8a575-212">选择 **联系人** 链接返回到联系人页。</span><span class="sxs-lookup"><span data-stu-id="8a575-212">Choose the **Contact** link to go back to the contact page.</span></span>  <span data-ttu-id="8a575-213">现在，请 **与我联系！**</span><span class="sxs-lookup"><span data-stu-id="8a575-213">Now, **Contact Me!**</span></span> <span data-ttu-id="8a575-214">的字体与导航链接的字体相同。</span><span class="sxs-lookup"><span data-stu-id="8a575-214">has the same font as the navigation links.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-multiple1.msft.png" alt-text="文本与我联系！  现在与 "主页" 和 "联系人" 链接的字体相同" lightbox="../media/beginners-css-multiple1.msft.png":::
       <span data-ttu-id="8a575-217">文本 **与我联系！**</span><span class="sxs-lookup"><span data-stu-id="8a575-217">The text **Contact Me!**</span></span> <span data-ttu-id="8a575-218">现在与 " **主页** " 和 " **联系人** " 链接的字体相同</span><span class="sxs-lookup"><span data-stu-id="8a575-218">now has the same font as the **Home** and **Contact** links</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="8a575-219">试用 DevTools</span><span class="sxs-lookup"><span data-stu-id="8a575-219">Experiment with DevTools</span></span>  

<span data-ttu-id="8a575-220">随着您继续在 web 开发中成为专家，您可能会发现 CSS 非常棘手。</span><span class="sxs-lookup"><span data-stu-id="8a575-220">As you continue your journey to become an expert in web development, you may find that CSS is tricky.</span></span>  <span data-ttu-id="8a575-221">你可以编写一些 CSS，并希望它以一种方式显示，但浏览器执行完全不同的操作。</span><span class="sxs-lookup"><span data-stu-id="8a575-221">You may write some CSS and expect it to display one way, but the browser does something completely different.</span></span>  <span data-ttu-id="8a575-222">Microsoft Edge DevTools 使你可以轻松地体验更改，并立即查看更改对页面有何影响。</span><span class="sxs-lookup"><span data-stu-id="8a575-222">Microsoft Edge DevTools makes it easy to experiment with changes and immediately see how the changes affect the page.</span></span>  

### <span data-ttu-id="8a575-223">将声明添加到 DevTools 中的现有 rulest</span><span class="sxs-lookup"><span data-stu-id="8a575-223">Add a declaration to an existing rulest in DevTools</span></span>  

<span data-ttu-id="8a575-224">完成以下操作以循环访问现有元素的样式，将声明添加到现有规则集。</span><span class="sxs-lookup"><span data-stu-id="8a575-224">Complete the following actions to iterate on the style of an existing element, add a declaration to an existing ruleset.</span></span>  

1.  <span data-ttu-id="8a575-225">将鼠标悬停在 " **主页** " 链接上，打开上下文菜单 \ (右键单击 "\ ) "，然后选择 " **检查**"。</span><span class="sxs-lookup"><span data-stu-id="8a575-225">Hover on the **Home** link, open the contextual menu \(right-click\), and select **Inspect**.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-add1.msft.png" alt-text="检查 "主页" 链接" lightbox="../media/beginners-css-add1.msft.png":::
       <span data-ttu-id="8a575-227">检查 "主页" 链接</span><span class="sxs-lookup"><span data-stu-id="8a575-227">Inspect the Home link</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="8a575-228">DevTools 将在您的页面旁打开。</span><span class="sxs-lookup"><span data-stu-id="8a575-228">DevTools opens up alongside your page.</span></span>  <span data-ttu-id="8a575-229">表示 Home 链接的代码在 `<a href="/">Home</a>` DOM 树中突出显示为蓝色。</span><span class="sxs-lookup"><span data-stu-id="8a575-229">The code that represents the Home link, `<a href="/">Home</a>` is highlighted blue in the DOM Tree.</span></span>  <span data-ttu-id="8a575-230">代码片段和预览应熟悉 [HTML 和 DOM 入门][DevtoolsBeginnersHtml]。</span><span class="sxs-lookup"><span data-stu-id="8a575-230">The code snippet and preview should be familiar from [Get Started with HTML and the DOM][DevtoolsBeginnersHtml].</span></span>  
    
    :::row:::
       :::column span="":::
          <span data-ttu-id="8a575-231">下图中，在 `font-family: 'Courier New', Courier, serif` `contact.html` DOM 树下方的 " **样式** " 选项卡中显示了之前添加到的声明。</span><span class="sxs-lookup"><span data-stu-id="8a575-231">In the following figure, the `font-family: 'Courier New', Courier, serif` declaration that you previously added to `contact.html` is seen in the **Styles** tab below the DOM Tree.</span></span>  
          
          :::image type="complex" source="../media/beginners-css-add2.msft.png" alt-text=""样式" 选项卡位于 DOM 树的下方" lightbox="../media/beginners-css-add2.msft.png":::
             <span data-ttu-id="8a575-233">" **样式** " 选项卡位于 DOM 树的下方</span><span class="sxs-lookup"><span data-stu-id="8a575-233">The **Styles** tab is below the DOM Tree</span></span>  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          <span data-ttu-id="8a575-234">如果 DevTools 窗口是宽的，则 "样式" 选项卡位于 DOM 树的右侧。</span><span class="sxs-lookup"><span data-stu-id="8a575-234">If your DevTools window is wide, the Styles tab is to the right of the DOM Tree.</span></span>  
          
          :::image type="complex" source="../media/beginners-css-add3.msft.png" alt-text=""样式" 选项卡位于 DOM 树的右侧" lightbox="../media/beginners-css-add3.msft.png":::
             <span data-ttu-id="8a575-236">" **样式** " 选项卡位于 DOM 树的右侧</span><span class="sxs-lookup"><span data-stu-id="8a575-236">The **Styles** tab is to the right of the DOM Tree</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
1.  <span data-ttu-id="8a575-237">选择下面的空行 `font-family: 'Courier New', Courier, Serif` 以添加新声明。</span><span class="sxs-lookup"><span data-stu-id="8a575-237">Choose the empty line below `font-family: 'Courier New', Courier, Serif` to add a new declaration.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-add4.msft.png" alt-text="添加新声明" lightbox="../media/beginners-css-add4.msft.png":::
       <span data-ttu-id="8a575-239">添加新声明</span><span class="sxs-lookup"><span data-stu-id="8a575-239">Add a new declaration</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="8a575-240">键入 `color` 并选择 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="8a575-240">Type `color` and select `Enter`.</span></span>  <span data-ttu-id="8a575-241">"自动完成" UI 建议您键入时的选项。</span><span class="sxs-lookup"><span data-stu-id="8a575-241">The autocomplete UI suggests options as you type.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-add5.msft.png" alt-text="键入颜色" lightbox="../media/beginners-css-add5.msft.png":::
       <span data-ttu-id="8a575-243">类型</span><span class="sxs-lookup"><span data-stu-id="8a575-243">Type</span></span> `color`  
    :::image-end:::  
    
1.  <span data-ttu-id="8a575-244">键入 `magenta` 并选择 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="8a575-244">Type `magenta` and select `Enter`.</span></span>  <span data-ttu-id="8a575-245">"联系人" 页面上的所有文本现在均为 "洋红"。</span><span class="sxs-lookup"><span data-stu-id="8a575-245">All of the text on the contact page is now magenta.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-add6.msft.png" alt-text="键入洋红" lightbox="../media/beginners-css-add6.msft.png":::
       <span data-ttu-id="8a575-247">类型</span><span class="sxs-lookup"><span data-stu-id="8a575-247">Type</span></span> `magenta`  
    :::image-end:::  
    
### <span data-ttu-id="8a575-248">在 DevTools 中编辑声明</span><span class="sxs-lookup"><span data-stu-id="8a575-248">Edit a declaration in DevTools</span></span>  

<span data-ttu-id="8a575-249">完成以下操作以在 DevTools 中编辑现有声明。</span><span class="sxs-lookup"><span data-stu-id="8a575-249">Complete the following actions to edit existing declarations in DevTools.</span></span>  

1.  <span data-ttu-id="8a575-250">选择旁边的洋红色方块 `magenta` 。</span><span class="sxs-lookup"><span data-stu-id="8a575-250">Choose the magenta square next to `magenta`.</span></span>  <span data-ttu-id="8a575-251">将弹出一个颜色选取器。</span><span class="sxs-lookup"><span data-stu-id="8a575-251">A color picker pops up.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-edit1.msft.png" alt-text="颜色选取器" lightbox="../media/beginners-css-edit1.msft.png":::
       <span data-ttu-id="8a575-253">颜色选取器</span><span class="sxs-lookup"><span data-stu-id="8a575-253">The Color Picker</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="8a575-254">使用拾色器将字体文本更改为您喜欢的颜色。</span><span class="sxs-lookup"><span data-stu-id="8a575-254">Use the color picker to change the font text to a color that you like.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-edit2.msft.png" alt-text="通过拾色器将字体颜色更改为紫色" lightbox="../media/beginners-css-edit2.msft.png":::
       <span data-ttu-id="8a575-256">通过拾色器将字体颜色更改为紫色</span><span class="sxs-lookup"><span data-stu-id="8a575-256">Change the font color to purple with the Color Picker</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="8a575-257">在 DevTools 中添加新的规则集</span><span class="sxs-lookup"><span data-stu-id="8a575-257">Add a new ruleset in DevTools</span></span>  

<span data-ttu-id="8a575-258">完成以下操作以在 DevTools 中添加新的规则集。</span><span class="sxs-lookup"><span data-stu-id="8a575-258">Complete the following actions to add new rulesets in DevTools.</span></span>  

1.  <span data-ttu-id="8a575-259">选择 " **新建样式规则** \ (![ 新样式规则 ][ImageNewStyleRuleIcon] \ ) 它位于" **. cls**"旁边。</span><span class="sxs-lookup"><span data-stu-id="8a575-259">Choose **New Style Rule** \(![New Style Rule][ImageNewStyleRuleIcon]\) which is next to **.cls**.</span></span>  <span data-ttu-id="8a575-260">将显示一个包含选择器的空规则集 `a` 。</span><span class="sxs-lookup"><span data-stu-id="8a575-260">An empty ruleset appears with `a` as the selector.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-rule1.msft.png" alt-text="添加新规则" lightbox="../media/beginners-css-rule1.msft.png":::
       <span data-ttu-id="8a575-262">添加新规则</span><span class="sxs-lookup"><span data-stu-id="8a575-262">Add a new rule</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="8a575-263">用 `a:hover` 取代 `a`。</span><span class="sxs-lookup"><span data-stu-id="8a575-263">Replace `a` with `a:hover`.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-rule2.msft.png" alt-text="将 with a:hover 替换为" lightbox="../media/beginners-css-rule2.msft.png":::
       <span data-ttu-id="8a575-265">替换 `a` 为</span><span class="sxs-lookup"><span data-stu-id="8a575-265">Replace `a` with</span></span> `a:hover`  
    :::image-end:::  
    
    `:hover` <span data-ttu-id="8a575-266">是 **伪类**。</span><span class="sxs-lookup"><span data-stu-id="8a575-266">is a **pseudo-class**.</span></span>  <span data-ttu-id="8a575-267">对可能进入特殊状态的样式元素使用伪类。</span><span class="sxs-lookup"><span data-stu-id="8a575-267">Use pseudo-classes for style elements that may enter special states.</span></span>  <span data-ttu-id="8a575-268">例如， `a:hover` 仅当你将鼠标悬停在某个元素上方时，该样式才会生效 `<a>` 。</span><span class="sxs-lookup"><span data-stu-id="8a575-268">For example, the `a:hover` style only takes effect when you are hovering over an `<a>` element.</span></span>  
    
1.  <span data-ttu-id="8a575-269">在括号之间进行选择以添加新的声明。</span><span class="sxs-lookup"><span data-stu-id="8a575-269">Choose between the brackets to add a new declaration.</span></span>  
1.  <span data-ttu-id="8a575-270">键入 `background-color` 声明名称，然后选择 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="8a575-270">Type `background-color` for the declaration name and select `Enter`.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-rule3.msft.png" alt-text="键入背景色" lightbox="../media/beginners-css-rule3.msft.png":::
       <span data-ttu-id="8a575-272">类型</span><span class="sxs-lookup"><span data-stu-id="8a575-272">Type</span></span> `background-color`  
    :::image-end:::  
    
1.  <span data-ttu-id="8a575-273">`green`声明值的类型，然后选择 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="8a575-273">Type `green` for the declaration value and select `Enter`.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-rule4.msft.png" alt-text="键入绿色" lightbox="../media/beginners-css-rule4.msft.png":::
       <span data-ttu-id="8a575-275">类型</span><span class="sxs-lookup"><span data-stu-id="8a575-275">Type</span></span> `green`  
    :::image-end:::  
    
1.  <span data-ttu-id="8a575-276">将鼠标悬停在 " **开始** " 链接上。</span><span class="sxs-lookup"><span data-stu-id="8a575-276">Hover your mouse over the **Home** link.</span></span>  <span data-ttu-id="8a575-277">链接的背景变为绿色。</span><span class="sxs-lookup"><span data-stu-id="8a575-277">The background of the link turns green.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-rule5.msft.png" alt-text="将鼠标悬停在 Home 链接上以显示绿色背景" lightbox="../media/beginners-css-rule5.msft.png":::
       <span data-ttu-id="8a575-279">将鼠标悬停在 Home 链接上以显示绿色背景</span><span class="sxs-lookup"><span data-stu-id="8a575-279">Hover over the Home link to reveal its green background</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="8a575-280">跨页面使用外部样式表重新使用样式</span><span class="sxs-lookup"><span data-stu-id="8a575-280">Re-use styles across pages with external stylesheets</span></span>  

<span data-ttu-id="8a575-281">在上一步中，你将以下代码段添加为内部样式表 `contact.html` 。</span><span class="sxs-lookup"><span data-stu-id="8a575-281">In a previous step, you added the following code snippet as an internal stylesheet to `contact.html`.</span></span>  

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

<span data-ttu-id="8a575-282">如果你想要以 `index.html` 相同的方式设置样式，该怎么办？</span><span class="sxs-lookup"><span data-stu-id="8a575-282">What if you wanted to style `index.html` the same way?</span></span>  <span data-ttu-id="8a575-283">如果您有大量页面需要应用样式，该怎么办？</span><span class="sxs-lookup"><span data-stu-id="8a575-283">What if you had a large number of pages to which you wanted to apply your styles?</span></span>  <span data-ttu-id="8a575-284">您必须将内部样式表复制并粘贴到您的网站上的每一个网页中。</span><span class="sxs-lookup"><span data-stu-id="8a575-284">You would have to copy and paste the internal stylesheet into every single web page on your site.</span></span>  <span data-ttu-id="8a575-285">完成以下操作以添加 **外部样式表** ，以允许你编写 CSS 一次并将其应用于多个页面。</span><span class="sxs-lookup"><span data-stu-id="8a575-285">Complete the following actions to add an **External stylesheet** to allow you to write your CSS once and apply it to multiple pages.</span></span>  

1.  <span data-ttu-id="8a575-286">首先，重新加载 "实时" 选项卡以删除您在 DevTools 中所做的更改。</span><span class="sxs-lookup"><span data-stu-id="8a575-286">First, reload the live tab to remove the changes that you made in DevTools.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-external1.msft.png" alt-text=" 刷新页面后，在 DevTools 中所做的更改将不再存在" lightbox="../media/beginners-css-external1.msft.png":::
        <span data-ttu-id="8a575-288">刷新页面后，在 DevTools 中所做的更改将不再存在</span><span class="sxs-lookup"><span data-stu-id="8a575-288">After you refresh the page, the changes that were made in DevTools are gone</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="8a575-289">返回 " **编辑器" 选项卡** ，然后打开 `contact.html` 。</span><span class="sxs-lookup"><span data-stu-id="8a575-289">Go back to the **editor tab** and open `contact.html`.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-external2.msft.png" alt-text="contact.html" lightbox="../media/beginners-css-external2.msft.png":::
       <span data-ttu-id="8a575-291">contact.html</span><span class="sxs-lookup"><span data-stu-id="8a575-291">contact.html</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="8a575-292">删除与之间的所有内容 `<style>` `</style>` ，包括 `<style>` 和 `</style>` 。</span><span class="sxs-lookup"><span data-stu-id="8a575-292">Delete everything between `<style>` and `</style>`, including `<style>` and `</style>`.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-external3.msft.png" alt-text="已删除样式标记" lightbox="../media/beginners-css-external3.msft.png":::
       <span data-ttu-id="8a575-294">已删除样式标记</span><span class="sxs-lookup"><span data-stu-id="8a575-294">The style tag has been removed</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="8a575-295">转到 `index.html` 并 `style="background-color: aliceblue;"` 从标记中删除 `<nav>` 。</span><span class="sxs-lookup"><span data-stu-id="8a575-295">Go to `index.html` and remove `style="background-color: aliceblue;"` from the `<nav>` tag.</span></span>  <span data-ttu-id="8a575-296">您现在已删除以前添加到网站的所有 CSS。</span><span class="sxs-lookup"><span data-stu-id="8a575-296">You have now removed all of the CSS that you previously added to your site.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-external4.msft.png" alt-text="内联样式已从导航元素中删除" lightbox="../media/beginners-css-external4.msft.png":::
       <span data-ttu-id="8a575-298">内联样式已从导航元素中删除</span><span class="sxs-lookup"><span data-stu-id="8a575-298">The inline style has been removed from the nav element</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="8a575-299">选择 " **新建文件**"。</span><span class="sxs-lookup"><span data-stu-id="8a575-299">Choose **New File**.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-external5.msft.png" alt-text=""新建文件" 对话框" lightbox="../media/beginners-css-external5.msft.png":::
       <span data-ttu-id="8a575-301">"新建文件" 对话框</span><span class="sxs-lookup"><span data-stu-id="8a575-301">The new file dialog</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="8a575-302">替换 `cool-file.js` 为 `style.css` ，然后选择 " **添加文件**"。</span><span class="sxs-lookup"><span data-stu-id="8a575-302">Replace `cool-file.js` with `style.css` and choose **Add File**.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-external6.msft.png" alt-text="类型样式 .css" lightbox="../media/beginners-css-external6.msft.png":::
       <span data-ttu-id="8a575-304">类型</span><span class="sxs-lookup"><span data-stu-id="8a575-304">Type</span></span> `style.css`  
    :::image-end:::  
    
1.  <span data-ttu-id="8a575-305">将以下代码片段添加到 `style.css` 文件中。</span><span class="sxs-lookup"><span data-stu-id="8a575-305">Add the following code snippet to your `style.css` file.</span></span>  
    
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
       <span data-ttu-id="8a575-307">将代码添加到</span><span class="sxs-lookup"><span data-stu-id="8a575-307">Add code to</span></span> `style.css`  
    :::image-end:::  
    
    <span data-ttu-id="8a575-308">确保已创建外部样式表。</span><span class="sxs-lookup"><span data-stu-id="8a575-308">Ensure that you have created an external stylesheet.</span></span> <span data-ttu-id="8a575-309">你的 HTML 不知道它是否存在。</span><span class="sxs-lookup"><span data-stu-id="8a575-309">Your HTML is not aware that it exists.</span></span>  
    
1.  <span data-ttu-id="8a575-310">打开 `index.html`。</span><span class="sxs-lookup"><span data-stu-id="8a575-310">Open `index.html`.</span></span>  
1.  <span data-ttu-id="8a575-311">添加 `<link rel="stylesheet" href="style.css">` 到你的 HTML。</span><span class="sxs-lookup"><span data-stu-id="8a575-311">Add `<link rel="stylesheet" href="style.css">` to your HTML.</span></span>  
    
    ```html
    <head>
        ...
        <meta name="viewport" content="width=device-width, initial-scale=1">
        <link rel="stylesheet" href="style.css">
    </head>
    ```  
    
    :::image type="complex" source="../media/beginners-css-external8.msft.png" alt-text="链接到样式 .css" lightbox="../media/beginners-css-external8.msft.png":::
       <span data-ttu-id="8a575-313">链接到</span><span class="sxs-lookup"><span data-stu-id="8a575-313">Link to</span></span> `style.css`  
    :::image-end:::  
    
1.  <span data-ttu-id="8a575-314">打开 `contact.html` 文件并在其中添加链接。</span><span class="sxs-lookup"><span data-stu-id="8a575-314">Open the `contact.html` file and add the link there.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-external9.msft.png" alt-text="链接到 contact.html 中的 "css"" lightbox="../media/beginners-css-external9.msft.png":::
       <span data-ttu-id="8a575-316">链接到 `style.css`</span><span class="sxs-lookup"><span data-stu-id="8a575-316">Link to `style.css` in</span></span> `contact.html`  
    :::image-end:::  
    
1.  <span data-ttu-id="8a575-317">转到 " **实时" 选项卡**。 现在，主页的字体与上一节中的字体相同，并具有蓝色导航部分。</span><span class="sxs-lookup"><span data-stu-id="8a575-317">Go to the **live tab**.  The home page now has the same font from the last section and a blue navigation section.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-external10.msft.png" alt-text="主页" lightbox="../media/beginners-css-external10.msft.png":::
       <span data-ttu-id="8a575-319">主页</span><span class="sxs-lookup"><span data-stu-id="8a575-319">The home page</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="8a575-320">选择 **联系人** 链接转到 "联系人" 页面。</span><span class="sxs-lookup"><span data-stu-id="8a575-320">Choose the **Contact** link to go to the contact page.</span></span>  <span data-ttu-id="8a575-321">"联系人" 页面的格式与 "主页" 的格式相同。</span><span class="sxs-lookup"><span data-stu-id="8a575-321">The contact page has the same formatting as the home page.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-external11.msft.png" alt-text=""联系人" 页面" lightbox="../media/beginners-css-external11.msft.png":::
       <span data-ttu-id="8a575-323">"联系人" 页面</span><span class="sxs-lookup"><span data-stu-id="8a575-323">The contact page</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="8a575-324">使用 CSS 框架</span><span class="sxs-lookup"><span data-stu-id="8a575-324">Use a CSS framework</span></span>  

<span data-ttu-id="8a575-325">**CSS 框架** 是由其他开发者构建的样式的集合，可使创建引人注目的网站更容易。</span><span class="sxs-lookup"><span data-stu-id="8a575-325">**CSS frameworks** are collections of styles built by other developers that make it easier to create attractive web sites.</span></span>  <span data-ttu-id="8a575-326">框架提供了可在页面元素上使用的样式集合，而不是自己定义样式。</span><span class="sxs-lookup"><span data-stu-id="8a575-326">Instead of defining styles yourself, a framework provides you a collection of styles that you are able to use on your page elements.</span></span>  

1.  <span data-ttu-id="8a575-327">复制以下代码：</span><span class="sxs-lookup"><span data-stu-id="8a575-327">Copy the following code:</span></span>  
    
    ```html
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.1.1/css/bootstrap.min.css">
    ```  
    
1.  <span data-ttu-id="8a575-328">转到 "编辑" 选项卡，然后将代码粘贴到 `contact.html` 。</span><span class="sxs-lookup"><span data-stu-id="8a575-328">Go to the editing tab and paste the code into `contact.html`.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-framework1.msft.png" alt-text="链接到 contact.html 中的框架" lightbox="../media/beginners-css-framework1.msft.png":::
       <span data-ttu-id="8a575-330">链接到中的框架</span><span class="sxs-lookup"><span data-stu-id="8a575-330">Link to the framework in</span></span> `contact.html`  
    :::image-end:::  
    
1.  <span data-ttu-id="8a575-331">打开 `index.html` 文件并在其中添加代码。</span><span class="sxs-lookup"><span data-stu-id="8a575-331">Open the `index.html` file and add the code there.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-framework2.msft.png" alt-text="链接到 index.html 中的框架" lightbox="../media/beginners-css-framework2.msft.png":::
       <span data-ttu-id="8a575-333">链接到中的框架</span><span class="sxs-lookup"><span data-stu-id="8a575-333">Link to the framework in</span></span> `index.html`  
    :::image-end:::  
    
1.  <span data-ttu-id="8a575-334">返回到 "实时" 选项卡以查看所做的更改。</span><span class="sxs-lookup"><span data-stu-id="8a575-334">Go back to the live tab to view your changes.</span></span>  <span data-ttu-id="8a575-335">虽然元素的背景色 `<nav>` 和 `<li>` 和元素的字体 `<a>` 相同，但其他元素的字体已更改。</span><span class="sxs-lookup"><span data-stu-id="8a575-335">While the background color of the `<nav>` element and the font of the `<li>` and `<a>` elements are the same, the font of the other elements has changed.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-framework3.msft.png" alt-text="主页面上的某些字体因框架而发生更改" lightbox="../media/beginners-css-framework3.msft.png":::
       <span data-ttu-id="8a575-337">主页面上的某些字体因框架而发生更改</span><span class="sxs-lookup"><span data-stu-id="8a575-337">Some of the font on the home page changed because of the framework</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="8a575-338">使用类</span><span class="sxs-lookup"><span data-stu-id="8a575-338">Use a class</span></span>  

<span data-ttu-id="8a575-339">在最后一节中，你将引导数据库添加到网页，这将更改网站上某些元素的字体。</span><span class="sxs-lookup"><span data-stu-id="8a575-339">In the last section, you added Bootstrap to your web pages, which changed the fonts of some of the elements on your site.</span></span>  <span data-ttu-id="8a575-340">CSS 框架可帮助你通过非常少的代码对页面进行重大更改。</span><span class="sxs-lookup"><span data-stu-id="8a575-340">CSS frameworks help you make major changes to your page with very little code.</span></span>  <span data-ttu-id="8a575-341">完成以下操作以更改页眉。</span><span class="sxs-lookup"><span data-stu-id="8a575-341">Complete the following actions to change your header.</span></span>  

1.  <span data-ttu-id="8a575-342">复制以下代码片段。</span><span class="sxs-lookup"><span data-stu-id="8a575-342">Copy the following code snippet.</span></span>  
    
    ```html
    class="jumbotron jumbotron-fluid"  
    ```  
    
1.  <span data-ttu-id="8a575-343">将上一个代码段添加到 `<header>` 中的标记 `index.html` 。</span><span class="sxs-lookup"><span data-stu-id="8a575-343">Add the previous code snippet to your `<header>` tag in `index.html`.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-jumbotron1.msft.png" alt-text="在 index.html 中添加类" lightbox="../media/beginners-css-jumbotron1.msft.png":::
       <span data-ttu-id="8a575-345">将类添加到</span><span class="sxs-lookup"><span data-stu-id="8a575-345">Add classes in</span></span> `index.html`  
    :::image-end:::  
    
1.  <span data-ttu-id="8a575-346">将代码添加到 `<header>` 中的标记 `contact.html` 。</span><span class="sxs-lookup"><span data-stu-id="8a575-346">Add the code to your `<header>` tag in `contact.html`.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-jumbotron2.msft.png" alt-text="在 contact.html 中添加类" lightbox="../media/beginners-css-jumbotron2.msft.png":::
       <span data-ttu-id="8a575-348">将类添加到</span><span class="sxs-lookup"><span data-stu-id="8a575-348">Add classes in</span></span> `contact.html`  
    :::image-end:::  
    
1.  <span data-ttu-id="8a575-349">在 "实时" 选项卡中查看所做的更改。 页眉周围有一个大灰的框。</span><span class="sxs-lookup"><span data-stu-id="8a575-349">View your changes in the live tab.  There is a big, grey box around your header.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-jumbotron3.msft.png" alt-text="标题现在周围有一个大灰框" lightbox="../media/beginners-css-jumbotron3.msft.png":::
       <span data-ttu-id="8a575-351">标题现在周围有一个大灰框</span><span class="sxs-lookup"><span data-stu-id="8a575-351">The header now has a big, grey box around it</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="8a575-352">了解类</span><span class="sxs-lookup"><span data-stu-id="8a575-352">Understand classes</span></span>  

<span data-ttu-id="8a575-353">通过类，你可以将样式集合分配给任意元素。</span><span class="sxs-lookup"><span data-stu-id="8a575-353">Classes let you assign collections of styles to arbitrary elements.</span></span>  <span data-ttu-id="8a575-354">`<header>`将属性设置为后，使用以下代码片段对元素应用多个样式 `class` `jumbotron` 。</span><span class="sxs-lookup"><span data-stu-id="8a575-354">Use the following code snippet to apply several styles to the `<header>` element after you set the `class` attribute to `jumbotron`.</span></span>  

```css
.jumbotron {
  padding: 2rem 1rem;
  margin-bottom: 2rem;
  background-color: #e9ecef;
  border-radius: .3rem;
}
```  

<span data-ttu-id="8a575-355">类的一个优点是允许你将样式应用到所需的任何元素。</span><span class="sxs-lookup"><span data-stu-id="8a575-355">One advantage of a class is that it lets you apply styles to whatever elements you want.</span></span>  <span data-ttu-id="8a575-356">例如，假设你想要将某些元素的背景色设置 `<p>` 为紫色，而不是所有 `<p>` 元素。</span><span class="sxs-lookup"><span data-stu-id="8a575-356">For example, suppose you want to set the background color of some `<p>` elements to purple, but not all `<p>` elements.</span></span>  <span data-ttu-id="8a575-357">使用以下代码片段定义类中的样式。</span><span class="sxs-lookup"><span data-stu-id="8a575-357">Use the following code snippet to define the style in a class.</span></span>  

```css
.custom-background {
  background-color: purple;
}
```  

<span data-ttu-id="8a575-358">接下来，将该类应用于 `<p>` 要样式的元素。</span><span class="sxs-lookup"><span data-stu-id="8a575-358">Next, apply the class to only the `<p>` elements that you want to style.</span></span>  

```html
<p>The text is not purple.</p>
<p class="custom-background">The text is purple.</p>
<p>The text is not purple.</p>
<p class="custom-background">The text is purple.</p>
```  

### <span data-ttu-id="8a575-359">对齐元素</span><span class="sxs-lookup"><span data-stu-id="8a575-359">Align elements</span></span>  

<span data-ttu-id="8a575-360">完成以下操作以执行引导并提供用于对齐元素的类。</span><span class="sxs-lookup"><span data-stu-id="8a575-360">Complete the following actions to bootstrap and provide classes for aligning elements.</span></span>  

1.  <span data-ttu-id="8a575-361">返回 "编辑器" 选项卡，然后打开 `index.html` 。</span><span class="sxs-lookup"><span data-stu-id="8a575-361">Go back to the editor tab and open `index.html`.</span></span>  
1.  <span data-ttu-id="8a575-362">添加 `class="container-fluid"` 到您的 `<body>` 标签。</span><span class="sxs-lookup"><span data-stu-id="8a575-362">Add `class="container-fluid"` to your `<body>` tag.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-align1.msft.png" alt-text="添加容器流体类" lightbox="../media/beginners-css-align1.msft.png":::
       <span data-ttu-id="8a575-364">添加 `container-fluid` 类</span><span class="sxs-lookup"><span data-stu-id="8a575-364">Add the `container-fluid` class</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="8a575-365">将您的 `<nav>` 和 `<main>` 元素包装在中 `<div class="row">` 。</span><span class="sxs-lookup"><span data-stu-id="8a575-365">Wrap your `<nav>` and `<main>` elements in `<div class="row">`.</span></span>  <span data-ttu-id="8a575-366">请确保放 `</div>` `</main>` 在 "" 之后，才能正确关闭新标记。</span><span class="sxs-lookup"><span data-stu-id="8a575-366">Make sure to put `</div>` after `</main>` in order to properly close the new tag.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-align2.msft.png" alt-text="添加行" lightbox="../media/beginners-css-align2.msft.png":::
       <span data-ttu-id="8a575-368">添加行</span><span class="sxs-lookup"><span data-stu-id="8a575-368">Add a row</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="8a575-369">添加 `class="col-3"` 到您的 `<nav>` 标签和 `class="col-9"` `<main>` 标签。</span><span class="sxs-lookup"><span data-stu-id="8a575-369">Add `class="col-3"` to your `<nav>` tag and `class="col-9"` to your `<main>` tag.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-align3.msft.png" alt-text="添加列3和 col-9 类" lightbox="../media/beginners-css-align3.msft.png":::
       <span data-ttu-id="8a575-371">添加 `col-3` 和 `col-9` 类</span><span class="sxs-lookup"><span data-stu-id="8a575-371">Add the `col-3` and `col-9` classes</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="8a575-372">在 "实时" 选项卡中查看所做的更改。</span><span class="sxs-lookup"><span data-stu-id="8a575-372">View your changes in the live tab.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-align4.msft.png" alt-text="导航内容现在位于主要内容的左侧" lightbox="../media/beginners-css-align4.msft.png":::
       <span data-ttu-id="8a575-374">导航内容现在位于主要内容的左侧</span><span class="sxs-lookup"><span data-stu-id="8a575-374">The nav content is now to the left of the main content</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="8a575-375">后续步骤</span><span class="sxs-lookup"><span data-stu-id="8a575-375">Next steps</span></span>  

<span data-ttu-id="8a575-376">恭喜！您已完成。</span><span class="sxs-lookup"><span data-stu-id="8a575-376">Congratulations, you are done.</span></span>  

*   <span data-ttu-id="8a575-377">在 web 开发中获取更好的最佳方式是构建更多网站。</span><span class="sxs-lookup"><span data-stu-id="8a575-377">The best way to get better at web development is to build more sites.</span></span>  <span data-ttu-id="8a575-378">不要担心会破坏内容。</span><span class="sxs-lookup"><span data-stu-id="8a575-378">Do not worry about breaking stuff.</span></span>  <span data-ttu-id="8a575-379">只要有兴趣，您就可以轻松掌握。</span><span class="sxs-lookup"><span data-stu-id="8a575-379">Just have fun and learn as much as possible along the way.</span></span>  
*   <span data-ttu-id="8a575-380">若要了解有关设置网页样式的详细信息，请参阅 [CSS 简介][MDNCssFirstSteps]。</span><span class="sxs-lookup"><span data-stu-id="8a575-380">To learn more about styling web pages, see [Introduction to CSS][MDNCssFirstSteps].</span></span>  
*   <span data-ttu-id="8a575-381">若要了解有关如何使用 DevTools 来试验页面 CSS 的详细信息，请参阅 [查看和更改 Css 入门][DevtoolsCssIndex]。</span><span class="sxs-lookup"><span data-stu-id="8a575-381">To learn more about how to use DevTools to experiment with the CSS of a page, see [Get Started with Viewing and Changing CSS][DevtoolsCssIndex].</span></span>  

<!--- image links --->  

[ImageNewStyleRuleIcon]: ../media/new-style-rule-icon.msft.png  

<!--- links  --->  

[DevtoolsBeginnersHtml]: ./html.md "初学者的 DevTools： HTML 和 DOM 入门 |Microsoft 文档"  
[DevtoolsCssIndex]: ../css/index.md "开始使用查看和更改 CSS |Microsoft 文档"  

[MicrosoftEdgeInsider]: https://www.microsoftedgeinsider.com "Microsoft Edge 预览体验成员"  

[GlitchCookedAmphibianIndex]: https://glitch.com/edit/#!/cooked-amphibian?path=index.html "index.html-cooked-amphibian |故障"  

[MDNCssFirstSteps]: https://developer.mozilla.org/docs/Learn/CSS/Introduction_to_CSS "CSS 优先步骤 |MDN"  

> [!NOTE]
> <span data-ttu-id="8a575-387">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="8a575-387">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="8a575-388">原始页面位于 [此处](https://developers.google.com/web/tools/chrome-devtools/beginners/css) ，由 [Katherine 杰克逊][KatherineJackson] (技术编写器暂存，Chrome DevTools \ ) 。</span><span class="sxs-lookup"><span data-stu-id="8a575-388">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/beginners/css) and is authored by [Katherine Jackson][KatherineJackson] \(Technical Writer Intern, Chrome DevTools\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="8a575-390">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="8a575-390">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[KatherineJackson]: https://developers.google.com/web/resources/contributors/katjackson  
