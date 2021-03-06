---
description: CSS 入门
title: 适用于初学者的 DevTools：CSS 入门
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， Web 开发， f12 工具， devtools
ms.openlocfilehash: 7aa33c339a7d130265660e4a4af6f50dde7e3e90
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398397"
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

# <a name="devtools-for-beginners-get-started-with-css"></a><span data-ttu-id="6a8cb-104">适用于初学者的 DevTools：CSS 入门</span><span class="sxs-lookup"><span data-stu-id="6a8cb-104">DevTools for beginners: Get started with CSS</span></span>  

<span data-ttu-id="6a8cb-105">本教程介绍如何使用 CSS 设置网页样式。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-105">In this tutorial, you learn how to use CSS to style a web page.</span></span>  <span data-ttu-id="6a8cb-106">此外，还了解如何使用 Microsoft Edge DevTools 试验 CSS 更改。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-106">You also learn how to use Microsoft Edge DevTools to experiment with CSS changes.</span></span>  

<span data-ttu-id="6a8cb-107">以下文章是一系列教程的第二个教程，该教程将指导你 Web 开发和 Microsoft Edge DevTools 的基础知识。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-107">The following article is the second tutorial in a series of tutorials that teaches you the basics of web development and Microsoft Edge DevTools.</span></span>  <span data-ttu-id="6a8cb-108">通过实际构建自己的网站，你可以获得实践体验。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-108">You gain hands-on experience by actually building your own website.</span></span>  <span data-ttu-id="6a8cb-109">在学习第二个教程之前，不需要完成第一个教程。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-109">You do not have to complete the first tutorial before following the second.</span></span>  <span data-ttu-id="6a8cb-110">[设置代码将](#set-up-your-code) 演示如何进行设置。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-110">[Set up your code](#set-up-your-code) shows you how to get set up.</span></span>  

> [!NOTE]
> <span data-ttu-id="6a8cb-111">本教程专为完全初学者设计，重点介绍 **Web** 开发基础知识和使用 DevTools 试验 CSS 的基础知识。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-111">This tutorial is designed for absolute beginners and focuses on both the **fundamentals of web development** and the basics of using DevTools to experiment with CSS.</span></span>  <span data-ttu-id="6a8cb-112">如果你需要一个仅侧重于 DevTools 的教程，请导航到"查看和更改 CSS 入门["。][DevtoolsCssIndex]</span><span class="sxs-lookup"><span data-stu-id="6a8cb-112">If you want a tutorial that only focuses on DevTools, navigate to [Get Started with Viewing and Changing CSS][DevtoolsCssIndex].</span></span>  

<span data-ttu-id="6a8cb-113">在本教程的开头，您的网站应如下所示。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-113">At the beginning of the tutorial, your site should look like the following figure.</span></span>  

:::image type="complex" source="../media/beginners-css-intro1.msft.png" alt-text="网站当前的外观" lightbox="../media/beginners-css-intro1.msft.png":::
   <span data-ttu-id="6a8cb-115">网站当前的外观</span><span class="sxs-lookup"><span data-stu-id="6a8cb-115">What your site currently looks like</span></span>  
:::image-end:::  

<span data-ttu-id="6a8cb-116">完成本教程后，网站应如下所示。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-116">After you complete the tutorial, you site should look like the following figure.</span></span>  

:::image type="complex" source="../media/beginners-css-intro2.msft.png" alt-text="你的网站在本教程末尾应的外观" lightbox="../media/beginners-css-intro2.msft.png":::
   <span data-ttu-id="6a8cb-118">你的网站在本教程末尾应的外观</span><span class="sxs-lookup"><span data-stu-id="6a8cb-118">What your site should look like at the end of the tutorial</span></span>  
:::image-end:::  

## <a name="goals"></a><span data-ttu-id="6a8cb-119">目标</span><span class="sxs-lookup"><span data-stu-id="6a8cb-119">Goals</span></span>  

<span data-ttu-id="6a8cb-120">按照本教程更好地了解以下概念和任务。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-120">Follow this tutorial to better understand the following concepts and tasks.</span></span>  

*   <span data-ttu-id="6a8cb-121">如何使用 CSS 设置网页样式。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-121">How to use CSS to style a web page.</span></span>  
*   <span data-ttu-id="6a8cb-122">如何使用 Microsoft Edge DevTools 试验 CSS。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-122">How to use Microsoft Edge DevTools to experiment with CSS.</span></span>  
*   <span data-ttu-id="6a8cb-123">CSS 和 CSS 框架的区别。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-123">The difference between CSS and CSS frameworks.</span></span>  

<span data-ttu-id="6a8cb-124">你正在构建一个真实的网站。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-124">You are building a real website.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="6a8cb-125">必备条件</span><span class="sxs-lookup"><span data-stu-id="6a8cb-125">Prerequisites</span></span>  

<span data-ttu-id="6a8cb-126">在尝试本教程之前，请完成以下先决条件。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-126">Before attempting this tutorial, complete the following prerequisites.</span></span>  

*   <span data-ttu-id="6a8cb-127">完成 [HTML 和 DOM][DevtoolsBeginnersHtml] 入门，或确保你了解 HTML 和 DOM，与本教程中介绍的内容类似。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-127">Complete [Get Started with HTML and the DOM][DevtoolsBeginnersHtml] or make sure that you have an understanding of HTML and the DOM similar to what is taught in that tutorial.</span></span>  
*   <span data-ttu-id="6a8cb-128">下载 [Microsoft Edge][MicrosoftEdgeInsider] Web 浏览器。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-128">Download the [Microsoft Edge][MicrosoftEdgeInsider] web browser.</span></span>  <span data-ttu-id="6a8cb-129">以下教程使用一组内置于 Microsoft Edge 中的 Web 开发工具，称为 Microsoft Edge DevTools。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-129">The following tutorial uses a set of web development tools, called the Microsoft Edge DevTools, that are built into Microsoft Edge.</span></span>  

## <a name="set-up-your-code"></a><span data-ttu-id="6a8cb-130">设置代码</span><span class="sxs-lookup"><span data-stu-id="6a8cb-130">Set up your code</span></span>  

<span data-ttu-id="6a8cb-131">若要创建网站，必须先完成以下操作以设置代码。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-131">To create your site, you must first complete the following actions to set up your code.</span></span>  

> [!NOTE]
> <span data-ttu-id="6a8cb-132">如果已完成系列的第一个教程，请跳到下一节。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-132">If you have already completed the first tutorial in the series, skip to the next section.</span></span>  <span data-ttu-id="6a8cb-133">继续使用上一教程中的代码，即 [HTML 和 DOM 入门][DevtoolsBeginnersHtml]。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-133">Continue using your code from the last tutorial, [Get Started with HTML and the DOM][DevtoolsBeginnersHtml].</span></span>  

1.  <span data-ttu-id="6a8cb-134">打开 [源代码][GlitchCookedAmphibianIndex]。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-134">Open the [source code][GlitchCookedAmphibianIndex].</span></span>  <span data-ttu-id="6a8cb-135">浏览器的"焦点内"选项卡被引用为 **编辑选项卡**。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-135">The in-focus tab of your browser is referenced as the **editing tab**.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-setup1.msft.png" alt-text="编辑选项卡" lightbox="../media/beginners-css-setup1.msft.png":::
       <span data-ttu-id="6a8cb-137">编辑**选项卡**</span><span class="sxs-lookup"><span data-stu-id="6a8cb-137">The **editing** tab</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="6a8cb-138">Choose **cooked-amphibian**.</span><span class="sxs-lookup"><span data-stu-id="6a8cb-138">Choose **cooked-amphibian**.</span></span>  <span data-ttu-id="6a8cb-139">弹出菜单。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-139">A menu pops up.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-setup2.msft.png" alt-text=""项目选项"菜单" lightbox="../media/beginners-css-setup2.msft.png":::
       <span data-ttu-id="6a8cb-141">"项目选项"菜单</span><span class="sxs-lookup"><span data-stu-id="6a8cb-141">The Project Options menu</span></span>  
    :::image-end:::  

1.  <span data-ttu-id="6a8cb-142">选择 **"重新混合项目"。**</span><span class="sxs-lookup"><span data-stu-id="6a8cb-142">Choose **Remix Project**.</span></span>  <span data-ttu-id="6a8cb-143">小故障将创建您能够编辑的项目的副本。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-143">Glitch creates a copy of the project that you are able to edit.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="6a8cb-144">小故障为新项目生成随机名称。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-144">Glitch generates a random name for the new project.</span></span>  
    
1.  <span data-ttu-id="6a8cb-145">选择 **"显示**"，**然后选择"新建窗口"。**</span><span class="sxs-lookup"><span data-stu-id="6a8cb-145">Choose **Show** and choose **In a New Window**.</span></span>  <span data-ttu-id="6a8cb-146">另一个选项卡将打开，其中显示网站实时视图。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-146">Another tab opens with a live view of your site.</span></span>  <span data-ttu-id="6a8cb-147">浏览器的"焦点内"选项卡被引用为实时 **选项卡**。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-147">The in-focus tab of your browser is referenced as the **live tab**.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-setup3.msft.png" alt-text="实时选项卡" lightbox="../media/beginners-css-setup3.msft.png":::
       <span data-ttu-id="6a8cb-149">实时 **选项卡**</span><span class="sxs-lookup"><span data-stu-id="6a8cb-149">The **live tab**</span></span>  
    :::image-end:::  

## <a name="understand-css"></a><span data-ttu-id="6a8cb-150">了解 CSS</span><span class="sxs-lookup"><span data-stu-id="6a8cb-150">Understand CSS</span></span>  

<span data-ttu-id="6a8cb-151">**CSS** 是一种计算机语言，用于确定网页的布局和样式。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-151">**CSS** is a computer language that determines the layout and styling of web pages.</span></span>  <span data-ttu-id="6a8cb-152">下图是带边框的段落。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-152">The following figure is a paragraph with a border.</span></span>  

:::image type="complex" source="../media/beginners-css-red_paragraph.msft.png" alt-text="文本已使用 CSS 设置样式" lightbox="../media/beginners-css-red_paragraph.msft.png":::
   <span data-ttu-id="6a8cb-154">文本已使用 CSS 设置样式</span><span class="sxs-lookup"><span data-stu-id="6a8cb-154">The text has been styled with CSS</span></span>  
:::image-end:::  

<span data-ttu-id="6a8cb-155">下面的代码段是用于创建上图中的段落的 HTML 和 CSS 代码。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-155">The following code snippet is the HTML and CSS code used to create the paragraph in the previous figure.</span></span>  

```html
<p style="border: 1px dashed red; padding: 5px;">
    This has been styled with CSS.
</p>
```  

`style="border: 1px dashed red; padding: 5px;"` <span data-ttu-id="6a8cb-156">可能看起来是全新的。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-156">probably looks new to you.</span></span>  <span data-ttu-id="6a8cb-157">其余部分看起来应该很熟悉。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-157">The rest should look familiar.</span></span>  <span data-ttu-id="6a8cb-158">如果没有，请 [完成 HTML 和 DOM][DevtoolsBeginnersHtml] 入门，然后再尝试以下部分。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-158">If not, complete [Get Started with HTML and the DOM][DevtoolsBeginnersHtml] before attempting the following sections.</span></span>  

## <a name="add-inline-styles"></a><span data-ttu-id="6a8cb-159">添加内联样式</span><span class="sxs-lookup"><span data-stu-id="6a8cb-159">Add inline styles</span></span>  

<span data-ttu-id="6a8cb-160">完成以下操作以使用 **内联样式将** 样式应用于单个元素。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-160">Complete the following actions to use **inline styles** to apply styles to a single element.</span></span>  

1.  <span data-ttu-id="6a8cb-161">返回到编辑选项卡并打开 `index.html` 。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-161">Go back to the editing tab and open `index.html`.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-inline1.msft.png" alt-text="index.html" lightbox="../media/beginners-css-inline1.msft.png":::
       <span data-ttu-id="6a8cb-163">在 `index.html` 编辑选项卡中打开</span><span class="sxs-lookup"><span data-stu-id="6a8cb-163">Open `index.html` in the editing tab</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="6a8cb-164">添加到 `style="background-color: aliceblue;"` 你的 `<nav>` 。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-164">Add `style="background-color: aliceblue;"` to your `<nav>`.</span></span>  <span data-ttu-id="6a8cb-165">在下面的代码块中，需要更改第四行代码。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-165">In the code block below, the fourth line of code is the one you need to change.</span></span>  <span data-ttu-id="6a8cb-166">其余代码就在这里，因此可以确保将新代码放在正确的位置。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-166">The rest is just there, so you are able to ensure that you are putting the new code in the right place.</span></span>  
    
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
    
1.  <span data-ttu-id="6a8cb-167">若要显示更改，请导航到活动 **选项卡**。 分区的背景现在 `<nav>` 为蓝色。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-167">To display the changes, navigate to the **live tab**.  The background of the `<nav>` section is now blue.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-inline2.msft.png" alt-text=""主页"和"联系人"链接背后的背景色现在为蓝色" lightbox="../media/beginners-css-inline2.msft.png":::
       <span data-ttu-id="6a8cb-169">"主页" **和"联系人** "链接 **背后的背景色** 现在为蓝色</span><span class="sxs-lookup"><span data-stu-id="6a8cb-169">The background color behind the **Home** and **Contact** links is now blue</span></span>  
    :::image-end:::  
    
## <a name="re-use-styles-on-a-single-page-with-internal-stylesheets"></a><span data-ttu-id="6a8cb-170">在包含内部样式表的单个页面上重新使用样式</span><span class="sxs-lookup"><span data-stu-id="6a8cb-170">Re-use styles on a single page with internal stylesheets</span></span>  

<span data-ttu-id="6a8cb-171">在以前的代码段中，内联样式将样式应用于单个 `<p>` 标记。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-171">In a previous code snippet, an inline style applied a style to a single `<p>` tag.</span></span>  

```html
<p style="border: 1px dashed red; padding: 5px;">
    This has been styled with CSS.
</p>
```  

<span data-ttu-id="6a8cb-172">如果希望网页上的所有元素都以相同方式设置样式 `<p>` ，该做什么？</span><span class="sxs-lookup"><span data-stu-id="6a8cb-172">What if you wanted all of the `<p>` elements on your webpage to be styled the same way?</span></span>  <span data-ttu-id="6a8cb-173">您必须将代码复制并粘贴到网站上 `<p>` 每个标记中。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-173">You have to copy and paste the code into every single `<p>` tag on your site.</span></span>  <span data-ttu-id="6a8cb-174">这是一项大量的时间和精力。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-174">That is a lot of time and effort.</span></span>  <span data-ttu-id="6a8cb-175">如果需要进行编辑，必须再次更改每个标记。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-175">And, if you needed to make an edit, you have to change every tag again.</span></span>  <span data-ttu-id="6a8cb-176">完成以下操作以使用内部样式 **表** 编写 CSS 一次，以便应用于多个元素。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-176">Complete the following actions to use an **Internal stylesheet** to write your CSS once so that it applies to multiple elements.</span></span>  

1.  <span data-ttu-id="6a8cb-177">在活动选项卡中，选择 **"联系人"** 以导航到联系人页面。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-177">In the live tab, choose **Contact** to navigate to the contact page.</span></span>  <span data-ttu-id="6a8cb-178">请注意"主页" **和** "联系人 **"的字体**。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-178">Notice the font of **Home** and **Contact**.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-internal1.msft.png" alt-text=""联系人"页" lightbox="../media/beginners-css-internal1.msft.png":::
       <span data-ttu-id="6a8cb-180">"联系人"页</span><span class="sxs-lookup"><span data-stu-id="6a8cb-180">The Contact page</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="6a8cb-181">在 **编辑器选项卡中**，打开 `contact.html` 。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-181">In the **editor tab**, open `contact.html`.</span></span>  
1.  <span data-ttu-id="6a8cb-182">将以下代码添加到 `contact.html` 。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-182">Add the following code to `contact.html`.</span></span>  <span data-ttu-id="6a8cb-183">请记住，需要添加以开始 `<style>` 和结尾 `</style>` 的行。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-183">Remember, the lines starting with `<style>` and ending with `</style>` are what you need to add.</span></span>  <span data-ttu-id="6a8cb-184">其他代码就在这里，以便你知道在何处放入新代码。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-184">The other code is just there so you know where to put the new code.</span></span>  
    
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
    
1.  <span data-ttu-id="6a8cb-185">返回到实时 **选项卡**。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-185">Go back to the **live tab**.</span></span>  
1.  <span data-ttu-id="6a8cb-186">选择 **"** 联系人"返回到联系人页面。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-186">Choose **Contact** to go back to the contact page.</span></span>  <span data-ttu-id="6a8cb-187">"主页 **"和** " **联系人"的** 字体已更改。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-187">The font of **Home** and **Contact** has changed.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-internal2.msft.png" alt-text=""主页"和"联系人"链接的字体已更改" lightbox="../media/beginners-css-internal2.msft.png":::
       <span data-ttu-id="6a8cb-189">"主页" **和** " **联系人"链接的** 字体已更改</span><span class="sxs-lookup"><span data-stu-id="6a8cb-189">The font of the **Home** and **Contact** links has changed</span></span>  
    :::image-end:::  
    
### <a name="understand-internal-stylesheets"></a><span data-ttu-id="6a8cb-190">了解内部样式表</span><span class="sxs-lookup"><span data-stu-id="6a8cb-190">Understand internal stylesheets</span></span>  

<span data-ttu-id="6a8cb-191">内部样式表使用选择器应用 **样式**。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-191">Internal stylesheets apply styles using **selectors**.</span></span>  <span data-ttu-id="6a8cb-192">选择器是可能应用于一个或多个 HTML 元素的模式。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-192">Selectors are patterns that may apply to one or more HTML elements.</span></span>  <span data-ttu-id="6a8cb-193">前面的代码段添加了以下样式。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-193">The previous code snippet added the following style.</span></span>  

```html
<style>
    li a {
      font-family: 'Courier New', Courier, Serif;
    }
</style>
```  

`li a` <span data-ttu-id="6a8cb-194">是一个转换为" `<li>` 包含元素的任何元素 `<a>` "的选择器。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-194">is a selector that translates to "any `<li>` element that contains an `<a>` element".</span></span>  <span data-ttu-id="6a8cb-195">浏览器更改"主页"和"\*\*\*\* 联系人 **"** 链接的字体，因为每个标记组都匹配模式。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-195">The browser changes the font of the **Home** and **Contact** links because each of the tag groups match the pattern.</span></span>  

```html
<li><a href="/">Home</a></li>
<li><a href="/contact.html">Contact</a></li>
```  

`font-family: 'Courier New', Courier, serif` <span data-ttu-id="6a8cb-196">是一个 **声明**。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-196">is a **declaration**.</span></span>  <span data-ttu-id="6a8cb-197">声明由以下两部分组成。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-197">A declaration is made of following two parts.</span></span>  

:::row:::
   :::column span="1":::
      **<span data-ttu-id="6a8cb-198">property</span><span class="sxs-lookup"><span data-stu-id="6a8cb-198">property</span></span>**  
   :::column-end:::
   :::column span="1":::
      `font-family`  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="6a8cb-199">该属性描述一种能够更改元素样式的常规方法。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-199">The property describes a general way that you are able to change the style of the element.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="6a8cb-200">值</span><span class="sxs-lookup"><span data-stu-id="6a8cb-200">value</span></span>**  
   :::column-end:::
   :::column span="1":::
      `'Courier New', Courier, serif`  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="6a8cb-201">该值准确描述了元素的样式应该如何更改。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-201">The value describes exactly how the style of the element should change.</span></span>  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="6a8cb-202">例如， `font-family: 'Courier New', Courier, serif` 为浏览器提供以下指令："将匹配模式的元素的字体设置为 `li a` `'Courier New'` 。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-202">For example, `font-family: 'Courier New', Courier, serif` gives the browser the following instruction:  "Set the font of elements that match the pattern `li a` to `'Courier New'`.</span></span>  <span data-ttu-id="6a8cb-203">如果该字体不可用，请使用 `Courier` 。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-203">If that font is not available, use `Courier`.</span></span>  <span data-ttu-id="6a8cb-204">如果不可用，请使用 `serif` 。"</span><span class="sxs-lookup"><span data-stu-id="6a8cb-204">If that is not available, use `serif`."</span></span>  

### <a name="add-multiple-selectors-to-a-ruleset"></a><span data-ttu-id="6a8cb-205">向规则集添加多个选择器</span><span class="sxs-lookup"><span data-stu-id="6a8cb-205">Add multiple selectors to a ruleset</span></span>  

<span data-ttu-id="6a8cb-206">类似以下代码段的 CSS 代码块称为 **规则集**。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-206">A block of CSS code like the following code snippet is called a **ruleset**.</span></span>  

```css
li a {
  font-family: 'Courier New', Courier, monospace;
}
```  

<span data-ttu-id="6a8cb-207">完成以下操作以使用逗号将多个选择器添加到规则集。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-207">Complete the following actions to use commas to add multiple selectors to a ruleset.</span></span>  

1.  <span data-ttu-id="6a8cb-208">在 **编辑器选项卡中**，打开 `contact.html` 。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-208">In the **editor tab**, open `contact.html`.</span></span>  
1.  <span data-ttu-id="6a8cb-209">键入 `li a` `, h1` 后 。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-209">After `li a` type `, h1`.</span></span>  
    
    ```html
    <style>
        li a, h1 {
          font-family: 'Courier New', Courier, Serif;
        }
    </style>
    ```  
    
    <span data-ttu-id="6a8cb-210">前面的代码段指示浏览器设置元素样式的方式与设置 `<h1>` 与模式匹配的元素的样式相同 `li a` 。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-210">The previous code snippet tells the browser to style `<h1>` elements the same way that it styles elements that match the pattern `li a`.</span></span>  
    
1.  <span data-ttu-id="6a8cb-211">导航到 **活动选项卡**。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-211">Navigate to the **live tab**.</span></span>  
1.  <span data-ttu-id="6a8cb-212">选择 **"联系人** "链接返回到联系人页面。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-212">Choose the **Contact** link to go back to the contact page.</span></span>  <span data-ttu-id="6a8cb-213">现在， **联系我！**</span><span class="sxs-lookup"><span data-stu-id="6a8cb-213">Now, **Contact Me!**</span></span> <span data-ttu-id="6a8cb-214">具有与导航链接相同的字体。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-214">has the same font as the navigation links.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-multiple1.msft.png" alt-text="文本"联系我"  <span data-ttu-id="6a8cb-216">现在具有与"主页"和"联系人"链接相同的字体</span><span class="sxs-lookup"><span data-stu-id="6a8cb-216">now has the same font as the Home and Contact links</span></span>" lightbox="../media/beginners-css-multiple1.msft.png":::
       <span data-ttu-id="6a8cb-217">文本" **联系我"**</span><span class="sxs-lookup"><span data-stu-id="6a8cb-217">The text **Contact Me!**</span></span> <span data-ttu-id="6a8cb-218">现在具有与"主页"和 **"联系人** " **链接相同的** 字体</span><span class="sxs-lookup"><span data-stu-id="6a8cb-218">now has the same font as the **Home** and **Contact** links</span></span>  
    :::image-end:::  
    
## <a name="experiment-with-devtools"></a><span data-ttu-id="6a8cb-219">使用 DevTools 进行试验</span><span class="sxs-lookup"><span data-stu-id="6a8cb-219">Experiment with DevTools</span></span>  

<span data-ttu-id="6a8cb-220">当你继续成为 Web 开发专家的旅程时，你可能会发现 CSS 很棘手。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-220">As you continue your journey to become an expert in web development, you may find that CSS is tricky.</span></span>  <span data-ttu-id="6a8cb-221">你可以编写一些 CSS，并期望它以一种方式显示，但浏览器会进行完全不同的操作。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-221">You may write some CSS and expect it to display one way, but the browser does something completely different.</span></span>  <span data-ttu-id="6a8cb-222">通过 Microsoft Edge DevTools，可以轻松试验更改并立即显示更改对页面的影响。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-222">Microsoft Edge DevTools makes it easy to experiment with changes and immediately display how the changes affect the page.</span></span>  

### <a name="add-a-declaration-to-an-existing-rulest-in-devtools"></a><span data-ttu-id="6a8cb-223">将声明添加到 DevTools 中的现有规则</span><span class="sxs-lookup"><span data-stu-id="6a8cb-223">Add a declaration to an existing rulest in DevTools</span></span>  

<span data-ttu-id="6a8cb-224">完成以下操作以对现有元素的样式进行轮访问，向现有规则集添加声明。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-224">Complete the following actions to iterate on the style of an existing element, add a declaration to an existing ruleset.</span></span>  

1.  <span data-ttu-id="6a8cb-225">悬停在"主页 **"** 链接上，打开上下文菜单 \ (右键单击\) ，然后选择"检查 **"。**</span><span class="sxs-lookup"><span data-stu-id="6a8cb-225">Hover on the **Home** link, open the contextual menu \(right-click\), and choose **Inspect**.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-add1.msft.png" alt-text="检查"主页"链接" lightbox="../media/beginners-css-add1.msft.png":::
       <span data-ttu-id="6a8cb-227">检查"主页"链接</span><span class="sxs-lookup"><span data-stu-id="6a8cb-227">Inspect the Home link</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="6a8cb-228">DevTools 将随页面一起打开。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-228">DevTools opens up alongside your page.</span></span>  <span data-ttu-id="6a8cb-229">表示"主页"链接的代码在 `<a href="/">Home</a>` DOM 树中突出显示为蓝色。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-229">The code that represents the Home link, `<a href="/">Home</a>` is highlighted blue in the DOM Tree.</span></span>  <span data-ttu-id="6a8cb-230">代码段和预览应该熟悉 HTML 和 [DOM][DevtoolsBeginnersHtml]入门。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-230">The code snippet and preview should be familiar from [Get Started with HTML and the DOM][DevtoolsBeginnersHtml].</span></span>  
    
    :::row:::
       :::column span="":::
          <span data-ttu-id="6a8cb-231">下图中，您之前添加到的声明显示在 `font-family: 'Courier New', Courier, serif` `contact.html` DOM 树下方的 **"** 样式"选项卡中。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-231">In the following figure, the `font-family: 'Courier New', Courier, serif` declaration that you previously added to `contact.html` is displayed in the **Styles** tab below the DOM Tree.</span></span>  
          
          :::image type="complex" source="../media/beginners-css-add2.msft.png" alt-text=""样式"选项卡位于 DOM 树下方" lightbox="../media/beginners-css-add2.msft.png":::
             <span data-ttu-id="6a8cb-233">" **样式"** 选项卡位于 DOM 树下方</span><span class="sxs-lookup"><span data-stu-id="6a8cb-233">The **Styles** tab is below the DOM Tree</span></span>  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          <span data-ttu-id="6a8cb-234">如果 DevTools 窗口很宽，则"样式"选项卡位于 DOM 树的右侧。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-234">If your DevTools window is wide, the Styles tab is to the right of the DOM Tree.</span></span>  
          
          :::image type="complex" source="../media/beginners-css-add3.msft.png" alt-text=""样式"选项卡位于 DOM 树的右侧" lightbox="../media/beginners-css-add3.msft.png":::
             <span data-ttu-id="6a8cb-236">" **样式** "选项卡位于 DOM 树的右侧</span><span class="sxs-lookup"><span data-stu-id="6a8cb-236">The **Styles** tab is to the right of the DOM Tree</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
1.  <span data-ttu-id="6a8cb-237">选择下面的空行 `font-family: 'Courier New', Courier, Serif` 以添加新声明。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-237">Choose the empty line below `font-family: 'Courier New', Courier, Serif` to add a new declaration.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-add4.msft.png" alt-text="添加新声明" lightbox="../media/beginners-css-add4.msft.png":::
       <span data-ttu-id="6a8cb-239">添加新声明</span><span class="sxs-lookup"><span data-stu-id="6a8cb-239">Add a new declaration</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="6a8cb-240">键入 `color` 并选择 `Enter`。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-240">Type `color` and select `Enter`.</span></span>  <span data-ttu-id="6a8cb-241">键入时，自动完成 UI 会推荐选项。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-241">The autocomplete UI suggests options as you type.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-add5.msft.png" alt-text="类型颜色" lightbox="../media/beginners-css-add5.msft.png":::
       <span data-ttu-id="6a8cb-243">类型</span><span class="sxs-lookup"><span data-stu-id="6a8cb-243">Type</span></span> `color`  
    :::image-end:::  
    
1.  <span data-ttu-id="6a8cb-244">键入 `magenta` 并选择 `Enter`。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-244">Type `magenta` and select `Enter`.</span></span>  <span data-ttu-id="6a8cb-245">联系人页面上的所有文本现在都为洋红色。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-245">All of the text on the contact page is now magenta.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-add6.msft.png" alt-text="类型洋红色" lightbox="../media/beginners-css-add6.msft.png":::
       <span data-ttu-id="6a8cb-247">类型</span><span class="sxs-lookup"><span data-stu-id="6a8cb-247">Type</span></span> `magenta`  
    :::image-end:::  
    
### <a name="edit-a-declaration-in-devtools"></a><span data-ttu-id="6a8cb-248">在 DevTools 中编辑声明</span><span class="sxs-lookup"><span data-stu-id="6a8cb-248">Edit a declaration in DevTools</span></span>  

<span data-ttu-id="6a8cb-249">完成以下操作以编辑 DevTools 中的现有声明。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-249">Complete the following actions to edit existing declarations in DevTools.</span></span>  

1.  <span data-ttu-id="6a8cb-250">选择旁边的洋红色正方形 `magenta` 。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-250">Choose the magenta square next to `magenta`.</span></span>  <span data-ttu-id="6a8cb-251">颜色选取器弹出。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-251">A color picker pops up.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-edit1.msft.png" alt-text="颜色选取器" lightbox="../media/beginners-css-edit1.msft.png":::
       <span data-ttu-id="6a8cb-253">颜色选取器</span><span class="sxs-lookup"><span data-stu-id="6a8cb-253">The Color Picker</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="6a8cb-254">使用颜色选取器将字体文本更改为您喜欢的颜色。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-254">Use the color picker to change the font text to a color that you like.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-edit2.msft.png" alt-text="使用颜色选取器将字体颜色更改为紫色" lightbox="../media/beginners-css-edit2.msft.png":::
       <span data-ttu-id="6a8cb-256">使用颜色选取器将字体颜色更改为紫色</span><span class="sxs-lookup"><span data-stu-id="6a8cb-256">Change the font color to purple with the Color Picker</span></span>  
    :::image-end:::  
    
### <a name="add-a-new-ruleset-in-devtools"></a><span data-ttu-id="6a8cb-257">在 DevTools 中添加新的规则集</span><span class="sxs-lookup"><span data-stu-id="6a8cb-257">Add a new ruleset in DevTools</span></span>  

<span data-ttu-id="6a8cb-258">完成以下操作以在 DevTools 中添加新的规则集。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-258">Complete the following actions to add new rulesets in DevTools.</span></span>  

1.  <span data-ttu-id="6a8cb-259">Choose **New Style Rule** \ (New Style Rule ![ ][ImageNewStyleRuleIcon] \) which is next to **.cls**.</span><span class="sxs-lookup"><span data-stu-id="6a8cb-259">Choose **New Style Rule** \(![New Style Rule][ImageNewStyleRuleIcon]\) which is next to **.cls**.</span></span>  <span data-ttu-id="6a8cb-260">空的规则集显示为 `a` 选择器。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-260">An empty ruleset appears with `a` as the selector.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-rule1.msft.png" alt-text="添加新规则" lightbox="../media/beginners-css-rule1.msft.png":::
       <span data-ttu-id="6a8cb-262">添加新规则</span><span class="sxs-lookup"><span data-stu-id="6a8cb-262">Add a new rule</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="6a8cb-263">用 `a:hover` 取代 `a`。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-263">Replace `a` with `a:hover`.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-rule2.msft.png" alt-text="将 a 替换为 a：hover" lightbox="../media/beginners-css-rule2.msft.png":::
       <span data-ttu-id="6a8cb-265">替换为 `a`</span><span class="sxs-lookup"><span data-stu-id="6a8cb-265">Replace `a` with</span></span> `a:hover`  
    :::image-end:::  
    
    `:hover` <span data-ttu-id="6a8cb-266">是 **伪类**。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-266">is a **pseudo-class**.</span></span>  <span data-ttu-id="6a8cb-267">对可能进入特殊状态样式元素使用伪类。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-267">Use pseudo-classes for style elements that may enter special states.</span></span>  <span data-ttu-id="6a8cb-268">例如， `a:hover` 样式仅在将鼠标悬停在元素上时 `<a>` 生效。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-268">For example, the `a:hover` style only takes effect when you are hovering over an `<a>` element.</span></span>  
    
1.  <span data-ttu-id="6a8cb-269">在括号之间选择以添加新声明。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-269">Choose between the brackets to add a new declaration.</span></span>  
1.  <span data-ttu-id="6a8cb-270">键入 `background-color` 声明名称并选择 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-270">Type `background-color` for the declaration name and select `Enter`.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-rule3.msft.png" alt-text="键入背景色" lightbox="../media/beginners-css-rule3.msft.png":::
       <span data-ttu-id="6a8cb-272">类型</span><span class="sxs-lookup"><span data-stu-id="6a8cb-272">Type</span></span> `background-color`  
    :::image-end:::  
    
1.  <span data-ttu-id="6a8cb-273">键入 `green` 声明值并选择 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-273">Type `green` for the declaration value and select `Enter`.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-rule4.msft.png" alt-text="键入绿色" lightbox="../media/beginners-css-rule4.msft.png":::
       <span data-ttu-id="6a8cb-275">类型</span><span class="sxs-lookup"><span data-stu-id="6a8cb-275">Type</span></span> `green`  
    :::image-end:::  
    
1.  <span data-ttu-id="6a8cb-276">将鼠标悬停在"主页 **"链接** 上。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-276">Hover your mouse over the **Home** link.</span></span>  <span data-ttu-id="6a8cb-277">链接的背景变为绿色。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-277">The background of the link turns green.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-rule5.msft.png" alt-text="将鼠标悬停在"主页"链接上以显示其绿色背景" lightbox="../media/beginners-css-rule5.msft.png":::
       <span data-ttu-id="6a8cb-279">将鼠标悬停在"主页"链接上以显示其绿色背景</span><span class="sxs-lookup"><span data-stu-id="6a8cb-279">Hover on the Home link to reveal its green background</span></span>  
    :::image-end:::  
    
## <a name="re-use-styles-across-pages-with-external-stylesheets"></a><span data-ttu-id="6a8cb-280">在具有外部样式表的页面之间重新使用样式</span><span class="sxs-lookup"><span data-stu-id="6a8cb-280">Re-use styles across pages with external stylesheets</span></span>  

<span data-ttu-id="6a8cb-281">在上一步中，您将以下代码段作为内部样式表添加到 `contact.html` 。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-281">In a previous step, you added the following code snippet as an internal stylesheet to `contact.html`.</span></span>  

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

<span data-ttu-id="6a8cb-282">如果要以相同方式 `index.html` 设置样式，该做什么？</span><span class="sxs-lookup"><span data-stu-id="6a8cb-282">What if you wanted to style `index.html` the same way?</span></span>  <span data-ttu-id="6a8cb-283">如果您具有大量要应用样式的页面，该做什么？</span><span class="sxs-lookup"><span data-stu-id="6a8cb-283">What if you had a large number of pages to which you wanted to apply your styles?</span></span>  <span data-ttu-id="6a8cb-284">您必须将内部样式表复制并粘贴到您的网站上的每个网页中。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-284">You have to copy and paste the internal stylesheet into every single web page on your site.</span></span>  <span data-ttu-id="6a8cb-285">完成以下操作以添加 **外部** 样式表，以允许您编写 CSS 一次，并应用到多个页面。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-285">Complete the following actions to add an **External stylesheet** to allow you to write your CSS once and apply it to multiple pages.</span></span>  

1.  <span data-ttu-id="6a8cb-286">首先，刷新实时选项卡以删除你在 DevTools 中所做的更改。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-286">First, refresh the live tab to remove the changes that you made in DevTools.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-external1.msft.png" alt-text=" 刷新页面后，在 DevTools 中所做的更改将消失" lightbox="../media/beginners-css-external1.msft.png":::
        <span data-ttu-id="6a8cb-288">刷新页面后，在 DevTools 中所做的更改将消失</span><span class="sxs-lookup"><span data-stu-id="6a8cb-288">After you refresh the page, the changes that were made in DevTools are gone</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="6a8cb-289">返回到编辑器 **选项卡并** 打开 `contact.html` 。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-289">Go back to the **editor tab** and open `contact.html`.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-external2.msft.png" alt-text="contact.html" lightbox="../media/beginners-css-external2.msft.png":::
       <span data-ttu-id="6a8cb-291">contact.html</span><span class="sxs-lookup"><span data-stu-id="6a8cb-291">contact.html</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="6a8cb-292">删除与 `<style>` 之间、包括 `</style>` 和 `<style>` 之间的所有内容 `</style>` 。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-292">Delete everything between `<style>` and `</style>`, including `<style>` and `</style>`.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-external3.msft.png" alt-text="样式标记已删除" lightbox="../media/beginners-css-external3.msft.png":::
       <span data-ttu-id="6a8cb-294">样式标记已删除</span><span class="sxs-lookup"><span data-stu-id="6a8cb-294">The style tag has been removed</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="6a8cb-295">打开 `index.html` 并 `style="background-color: aliceblue;"` 删除 `<nav>` 标记。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-295">Open `index.html` and remove `style="background-color: aliceblue;"` from the `<nav>` tag.</span></span>  <span data-ttu-id="6a8cb-296">现在，您已删除之前添加到网站的所有 CSS。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-296">You have now removed all of the CSS that you previously added to your site.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-external4.msft.png" alt-text="内联样式已从导航元素中删除" lightbox="../media/beginners-css-external4.msft.png":::
       <span data-ttu-id="6a8cb-298">内联样式已从导航元素中删除</span><span class="sxs-lookup"><span data-stu-id="6a8cb-298">The inline style has been removed from the nav element</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="6a8cb-299">选择 **"新建文件"。**</span><span class="sxs-lookup"><span data-stu-id="6a8cb-299">Choose **New File**.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-external5.msft.png" alt-text="新文件对话框" lightbox="../media/beginners-css-external5.msft.png":::
       <span data-ttu-id="6a8cb-301">新文件对话框</span><span class="sxs-lookup"><span data-stu-id="6a8cb-301">The new file dialog</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="6a8cb-302">替换为 `cool-file.js` 并选择 `style.css` **"添加文件"。**</span><span class="sxs-lookup"><span data-stu-id="6a8cb-302">Replace `cool-file.js` with `style.css` and choose **Add File**.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-external6.msft.png" alt-text="Type style.css" lightbox="../media/beginners-css-external6.msft.png":::
       <span data-ttu-id="6a8cb-304">类型</span><span class="sxs-lookup"><span data-stu-id="6a8cb-304">Type</span></span> `style.css`  
    :::image-end:::  
    
1.  <span data-ttu-id="6a8cb-305">将以下代码段添加到 `style.css` 文件。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-305">Add the following code snippet to your `style.css` file.</span></span>  
    
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
    
    :::image type="complex" source="../media/beginners-css-external7.msft.png" alt-text="将代码添加到 style.css" lightbox="../media/beginners-css-external7.msft.png":::
       <span data-ttu-id="6a8cb-307">将代码添加到</span><span class="sxs-lookup"><span data-stu-id="6a8cb-307">Add code to</span></span> `style.css`  
    :::image-end:::  
    
    <span data-ttu-id="6a8cb-308">确保您已创建外部样式表。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-308">Ensure that you have created an external stylesheet.</span></span> <span data-ttu-id="6a8cb-309">您的 HTML 不知道它是否存在。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-309">Your HTML is not aware that it exists.</span></span>  
    
1.  <span data-ttu-id="6a8cb-310">打开 `index.html`。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-310">Open `index.html`.</span></span>  
1.  <span data-ttu-id="6a8cb-311">添加到 `<link rel="stylesheet" href="style.css">` HTML。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-311">Add `<link rel="stylesheet" href="style.css">` to your HTML.</span></span>  
    
    ```html
    <head>
        ...
        <meta name="viewport" content="width=device-width, initial-scale=1">
        <link rel="stylesheet" href="style.css">
    </head>
    ```  
    
    :::image type="complex" source="../media/beginners-css-external8.msft.png" alt-text="链接到 style.css" lightbox="../media/beginners-css-external8.msft.png":::
       <span data-ttu-id="6a8cb-313">链接到</span><span class="sxs-lookup"><span data-stu-id="6a8cb-313">Link to</span></span> `style.css`  
    :::image-end:::  
    
1.  <span data-ttu-id="6a8cb-314">打开 `contact.html` 文件并添加链接。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-314">Open the `contact.html` file and add the link there.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-external9.msft.png" alt-text="链接到 contact.html 中的 style.css" lightbox="../media/beginners-css-external9.msft.png":::
       <span data-ttu-id="6a8cb-316">链接到 `style.css` in</span><span class="sxs-lookup"><span data-stu-id="6a8cb-316">Link to `style.css` in</span></span> `contact.html`  
    :::image-end:::  
    
1.  <span data-ttu-id="6a8cb-317">导航到 **活动选项卡**。 主页上一节和蓝色导航部分现在具有相同的字体。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-317">Navigate to the **live tab**.  The home page now has the same font from the last section and a blue navigation section.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-external10.msft.png" alt-text="主页" lightbox="../media/beginners-css-external10.msft.png":::
       <span data-ttu-id="6a8cb-319">主页</span><span class="sxs-lookup"><span data-stu-id="6a8cb-319">The home page</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="6a8cb-320">选择 **"联系人** "链接以导航到联系人页面。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-320">Choose the **Contact** link to navigate to the contact page.</span></span>  <span data-ttu-id="6a8cb-321">联系人页面的格式与主页的格式相同。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-321">The contact page has the same formatting as the home page.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-external11.msft.png" alt-text="联系人页面" lightbox="../media/beginners-css-external11.msft.png":::
       <span data-ttu-id="6a8cb-323">联系人页面</span><span class="sxs-lookup"><span data-stu-id="6a8cb-323">The contact page</span></span>  
    :::image-end:::  
    
## <a name="use-a-css-framework"></a><span data-ttu-id="6a8cb-324">使用 CSS 框架</span><span class="sxs-lookup"><span data-stu-id="6a8cb-324">Use a CSS framework</span></span>  

<span data-ttu-id="6a8cb-325">**CSS 框架** 是由其他开发人员构建的样式集合，可更轻松地创建极具吸引力的网站。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-325">**CSS frameworks** are collections of styles built by other developers that make it easier to create attractive web sites.</span></span>  <span data-ttu-id="6a8cb-326">框架提供了一组可以在页面元素上使用的样式，而不是自己定义样式。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-326">Instead of defining styles yourself, a framework provides you a collection of styles that you are able to use on your page elements.</span></span>  

1.  <span data-ttu-id="6a8cb-327">复制以下代码：</span><span class="sxs-lookup"><span data-stu-id="6a8cb-327">Copy the following code:</span></span>  
    
    ```html
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.1.1/css/bootstrap.min.css">
    ```  
    
1.  <span data-ttu-id="6a8cb-328">打开编辑选项卡，然后将代码粘贴到 `contact.html` 。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-328">Open the editing tab and paste the code into `contact.html`.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-framework1.msft.png" alt-text="指向 contact.html 中的框架的链接" lightbox="../media/beginners-css-framework1.msft.png":::
       <span data-ttu-id="6a8cb-330">链接到</span><span class="sxs-lookup"><span data-stu-id="6a8cb-330">Link to the framework in</span></span> `contact.html`  
    :::image-end:::  
    
1.  <span data-ttu-id="6a8cb-331">打开 `index.html` 文件并添加代码。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-331">Open the `index.html` file and add the code there.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-framework2.msft.png" alt-text="指向 index.html 中的框架的链接" lightbox="../media/beginners-css-framework2.msft.png":::
       <span data-ttu-id="6a8cb-333">链接到</span><span class="sxs-lookup"><span data-stu-id="6a8cb-333">Link to the framework in</span></span> `index.html`  
    :::image-end:::  
    
1.  <span data-ttu-id="6a8cb-334">返回到实时选项卡以查看更改。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-334">Go back to the live tab to view your changes.</span></span>  <span data-ttu-id="6a8cb-335">虽然元素的背景颜色与 and 元素的字体相同，但其他元素的 `<nav>` `<li>` `<a>` 字体已更改。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-335">While the background color of the `<nav>` element and the font of the `<li>` and `<a>` elements are the same, the font of the other elements has changed.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-framework3.msft.png" alt-text="主页上的一些字体因框架而更改" lightbox="../media/beginners-css-framework3.msft.png":::
       <span data-ttu-id="6a8cb-337">主页上的一些字体因框架而更改</span><span class="sxs-lookup"><span data-stu-id="6a8cb-337">Some of the font on the home page changed because of the framework</span></span>  
    :::image-end:::  
    
### <a name="use-a-class"></a><span data-ttu-id="6a8cb-338">使用类</span><span class="sxs-lookup"><span data-stu-id="6a8cb-338">Use a class</span></span>  

<span data-ttu-id="6a8cb-339">在上一节中，你向网页添加了 Bootstrap，这更改了网站上某些元素的字体。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-339">In the last section, you added Bootstrap to your web pages, which changed the fonts of some of the elements on your site.</span></span>  <span data-ttu-id="6a8cb-340">CSS 框架可帮助你使用非常少的代码对页面进行重大更改。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-340">CSS frameworks help you make major changes to your page with very little code.</span></span>  <span data-ttu-id="6a8cb-341">完成以下操作以更改标头。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-341">Complete the following actions to change your header.</span></span>  

1.  <span data-ttu-id="6a8cb-342">复制以下代码段。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-342">Copy the following code snippet.</span></span>  
    
    ```html
    class="jumbotron jumbotron-fluid"  
    ```  
    
1.  <span data-ttu-id="6a8cb-343">将前面的代码段添加到 `<header>` 您的标记中 `index.html` 。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-343">Add the previous code snippet to your `<header>` tag in `index.html`.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-jumbotron1.msft.png" alt-text="在 index.html 中添加类" lightbox="../media/beginners-css-jumbotron1.msft.png":::
       <span data-ttu-id="6a8cb-345">将类添加到</span><span class="sxs-lookup"><span data-stu-id="6a8cb-345">Add classes in</span></span> `index.html`  
    :::image-end:::  
    
1.  <span data-ttu-id="6a8cb-346">将代码添加到 `<header>` 您的标记中 `contact.html` 。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-346">Add the code to your `<header>` tag in `contact.html`.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-jumbotron2.msft.png" alt-text="在 contact.html 中添加类" lightbox="../media/beginners-css-jumbotron2.msft.png":::
       <span data-ttu-id="6a8cb-348">将类添加到</span><span class="sxs-lookup"><span data-stu-id="6a8cb-348">Add classes in</span></span> `contact.html`  
    :::image-end:::  
    
1.  <span data-ttu-id="6a8cb-349">在实时选项卡中查看更改。 标题周围有一个大的灰色框。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-349">View your changes in the live tab.  There is a big, grey box around your header.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-jumbotron3.msft.png" alt-text="标题现在四周有一个大的灰色框" lightbox="../media/beginners-css-jumbotron3.msft.png":::
       <span data-ttu-id="6a8cb-351">标题现在四周有一个大的灰色框</span><span class="sxs-lookup"><span data-stu-id="6a8cb-351">The header now has a big, grey box around it</span></span>  
    :::image-end:::  
    
### <a name="understand-classes"></a><span data-ttu-id="6a8cb-352">了解类</span><span class="sxs-lookup"><span data-stu-id="6a8cb-352">Understand classes</span></span>  

<span data-ttu-id="6a8cb-353">类使你可以将样式集合分配给任意元素。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-353">Classes let you assign collections of styles to arbitrary elements.</span></span>  <span data-ttu-id="6a8cb-354">将属性设置为后，使用以下代码段将多个样式应用到 `<header>` `class` 元素 `jumbotron` 。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-354">Use the following code snippet to apply several styles to the `<header>` element after you set the `class` attribute to `jumbotron`.</span></span>  

```css
.jumbotron {
  padding: 2rem 1rem;
  margin-bottom: 2rem;
  background-color: #e9ecef;
  border-radius: .3rem;
}
```  

<span data-ttu-id="6a8cb-355">类的一个优点是，它允许您将样式应用于所需的任何元素。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-355">One advantage of a class is that it lets you apply styles to whatever elements you want.</span></span>  <span data-ttu-id="6a8cb-356">例如，假设你想要将某些元素的背景色设置为 `<p>` 紫色，但不是所有 `<p>` 元素。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-356">For example, suppose you want to set the background color of some `<p>` elements to purple, but not all `<p>` elements.</span></span>  <span data-ttu-id="6a8cb-357">使用以下代码段定义类中的样式。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-357">Use the following code snippet to define the style in a class.</span></span>  

```css
.custom-background {
  background-color: purple;
}
```  

<span data-ttu-id="6a8cb-358">接下来，将类仅应用于 `<p>` 要设置样式的元素。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-358">Next, apply the class to only the `<p>` elements that you want to style.</span></span>  

```html
<p>The text is not purple.</p>
<p class="custom-background">The text is purple.</p>
<p>The text is not purple.</p>
<p class="custom-background">The text is purple.</p>
```  

### <a name="align-elements"></a><span data-ttu-id="6a8cb-359">对齐元素</span><span class="sxs-lookup"><span data-stu-id="6a8cb-359">Align elements</span></span>  

<span data-ttu-id="6a8cb-360">完成以下操作以引导并提供用于对齐元素的类。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-360">Complete the following actions to bootstrap and provide classes for aligning elements.</span></span>  

1.  <span data-ttu-id="6a8cb-361">返回到编辑器选项卡并打开 `index.html` 。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-361">Go back to the editor tab and open `index.html`.</span></span>  
1.  <span data-ttu-id="6a8cb-362">添加到 `class="container-fluid"` 标记 `<body>` 。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-362">Add `class="container-fluid"` to your `<body>` tag.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-align1.msft.png" alt-text="添加容器流类" lightbox="../media/beginners-css-align1.msft.png":::
       <span data-ttu-id="6a8cb-364">添加 `container-fluid` 类</span><span class="sxs-lookup"><span data-stu-id="6a8cb-364">Add the `container-fluid` class</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="6a8cb-365">将你的 `<nav>` 和 `<main>` 元素包装在 `<div class="row">` .</span><span class="sxs-lookup"><span data-stu-id="6a8cb-365">Wrap your `<nav>` and `<main>` elements in `<div class="row">`.</span></span>  <span data-ttu-id="6a8cb-366">请务必放在 `</div>` 后 `</main>` ，以便正确关闭新标记。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-366">Make sure to put `</div>` after `</main>` in order to properly close the new tag.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-align2.msft.png" alt-text="添加行" lightbox="../media/beginners-css-align2.msft.png":::
       <span data-ttu-id="6a8cb-368">添加行</span><span class="sxs-lookup"><span data-stu-id="6a8cb-368">Add a row</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="6a8cb-369">添加到 `class="col-3"` 标记 `<nav>` 和 `class="col-9"` `<main>` 标记。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-369">Add `class="col-3"` to your `<nav>` tag and `class="col-9"` to your `<main>` tag.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-align3.msft.png" alt-text="添加 col-3 和 col-9 类" lightbox="../media/beginners-css-align3.msft.png":::
       <span data-ttu-id="6a8cb-371">添加 `col-3` and `col-9` 类</span><span class="sxs-lookup"><span data-stu-id="6a8cb-371">Add the `col-3` and `col-9` classes</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="6a8cb-372">在实时选项卡中查看更改。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-372">View your changes in the live tab.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-align4.msft.png" alt-text="导航内容现在位于主内容的左侧" lightbox="../media/beginners-css-align4.msft.png":::
       <span data-ttu-id="6a8cb-374">导航内容现在位于主内容的左侧</span><span class="sxs-lookup"><span data-stu-id="6a8cb-374">The nav content is now to the left of the main content</span></span>  
    :::image-end:::  
    
## <a name="next-steps"></a><span data-ttu-id="6a8cb-375">后续步骤</span><span class="sxs-lookup"><span data-stu-id="6a8cb-375">Next steps</span></span>  

<span data-ttu-id="6a8cb-376">恭喜！你已完成。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-376">Congratulations, you are done.</span></span>  

*   <span data-ttu-id="6a8cb-377">更好地进行 Web 开发的最佳方法就是生成更多网站。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-377">The best way to get better at web development is to build more sites.</span></span>  <span data-ttu-id="6a8cb-378">不要担心破坏内容。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-378">Do not worry about breaking stuff.</span></span>  <span data-ttu-id="6a8cb-379">只需在一边玩得一样有趣，然后尽可能学习。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-379">Just have fun and learn as much as possible along the way.</span></span>  
*   <span data-ttu-id="6a8cb-380">若要了解有关设置网页样式的信息，请导航到 [CSS 简介][MDNCssFirstSteps]。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-380">To learn more about styling web pages, navigate to [Introduction to CSS][MDNCssFirstSteps].</span></span>  
*   <span data-ttu-id="6a8cb-381">若要了解有关如何使用 DevTools 试验页面 CSS 的信息，请导航到"查看和更改 CSS 入门["。][DevtoolsCssIndex]</span><span class="sxs-lookup"><span data-stu-id="6a8cb-381">To learn more about how to use DevTools to experiment with the CSS of a page, navigate to [Get Started with Viewing and Changing CSS][DevtoolsCssIndex].</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="6a8cb-382">联系 Microsoft Edge 开发工具团队</span><span class="sxs-lookup"><span data-stu-id="6a8cb-382">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!--- image links --->  

[ImageNewStyleRuleIcon]: ../media/new-style-rule-icon.msft.png  

<!--- links  --->  

[DevtoolsBeginnersHtml]: ./html.md "适用于初学者的 DevTools：HTML 和 DOM |Microsoft Docs"  
[DevtoolsCssIndex]: ../css/index.md "查看和更改 CSS 入门 | Microsoft 文档"  

[MicrosoftEdgeInsider]: https://www.microsoftedgeinsider.com "Microsoft Edge 预览体验成员"  

[GlitchCookedAmphibianIndex]: https://glitch.com/edit/#!/cooked-amphibian?path=index.html "index.html - 已|小故障"  

[MDNCssFirstSteps]: https://developer.mozilla.org/docs/Learn/CSS/Introduction_to_CSS "CSS 第一|MDN"  

> [!NOTE]
> <span data-ttu-id="6a8cb-388">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-388">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="6a8cb-389">原始页面位于 [此处，](https://developers.google.com/web/tools/chrome-devtools/beginners/css) 由一名技术编写器 ([Chrome][KatherineJackson] DevTools\) 。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-389">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/beginners/css) and is authored by [Katherine Jackson][KatherineJackson] \(Technical Writer Intern, Chrome DevTools\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="6a8cb-391">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="6a8cb-391">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[KatherineJackson]: https://developers.google.com/web/resources/contributors/katjackson  
