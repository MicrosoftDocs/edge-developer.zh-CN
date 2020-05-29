---
title: 初学者的 DevTools
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/18/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 0064f0427b6bd5689e888cccfe2c650492898bb2
ms.sourcegitcommit: 8bfa239274e7a4856b961b9cf163b08d96463c10
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2020
ms.locfileid: "10581592"
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

# <span data-ttu-id="ed964-103">初学者的 DevTools：开始使用 CSS</span><span class="sxs-lookup"><span data-stu-id="ed964-103">DevTools For Beginners: Get Started with CSS</span></span>   

<span data-ttu-id="ed964-104">在本教程中，你将了解如何使用 CSS 对网页进行样式。</span><span class="sxs-lookup"><span data-stu-id="ed964-104">In this tutorial, you learn how to use CSS to style a web page.</span></span>  <span data-ttu-id="ed964-105">你还将了解如何使用 Microsoft Edge DevTools 来试验 CSS 更改。</span><span class="sxs-lookup"><span data-stu-id="ed964-105">You also learn how to use Microsoft Edge DevTools to experiment with CSS changes.</span></span>  

<span data-ttu-id="ed964-106">这是一系列教程中的第二个教程，可教你了解 web 开发和 Microsoft Edge DevTools 的基础知识。</span><span class="sxs-lookup"><span data-stu-id="ed964-106">This is the second tutorial in a series of tutorials that teaches you the basics of web development and Microsoft Edge DevTools.</span></span>  <span data-ttu-id="ed964-107">您可以通过实际构建自己的网站来获得实际体验。</span><span class="sxs-lookup"><span data-stu-id="ed964-107">You gain hands-on experience by actually building your own website.</span></span>  <span data-ttu-id="ed964-108">在执行此操作之前，您无需完成第一个教程。</span><span class="sxs-lookup"><span data-stu-id="ed964-108">You don't have to complete the first tutorial before doing this one.</span></span>  <span data-ttu-id="ed964-109">您可以从这里开始。</span><span class="sxs-lookup"><span data-stu-id="ed964-109">You can start here.</span></span>  <span data-ttu-id="ed964-110">[设置代码](#set-up-your-code)显示如何设置。</span><span class="sxs-lookup"><span data-stu-id="ed964-110">[Set up your code](#set-up-your-code) shows you how to get set up.</span></span>  

> [!NOTE]
> <span data-ttu-id="ed964-111">本教程适用于绝对初学者，重点介绍**web 开发的基础知识**和使用 DEVTOOLS 试验 CSS 的基础知识。</span><span class="sxs-lookup"><span data-stu-id="ed964-111">This tutorial is designed for absolute beginners and focuses on both the **fundamentals of web development** and the basics of using DevTools to experiment with CSS.</span></span>  <span data-ttu-id="ed964-112">如果你需要仅关注 DevTools 的教程，请参阅[查看和更改 CSS 入门][DevtoolsCssIndex]。</span><span class="sxs-lookup"><span data-stu-id="ed964-112">If you want a tutorial that only focuses on DevTools, see [Get Started with Viewing and Changing CSS][DevtoolsCssIndex].</span></span>  

<span data-ttu-id="ed964-113">当前您的网站如下所示：</span><span class="sxs-lookup"><span data-stu-id="ed964-113">Currently your site looks like this:</span></span>  

> ##### <span data-ttu-id="ed964-114">图 1</span><span class="sxs-lookup"><span data-stu-id="ed964-114">Figure 1</span></span>  
> <span data-ttu-id="ed964-115">网站的当前外观</span><span class="sxs-lookup"><span data-stu-id="ed964-115">What your site currently looks like</span></span>  
> ![网站的当前外观][ImageCssIntro1]  

<span data-ttu-id="ed964-117">完成教程后，它将如下所示：</span><span class="sxs-lookup"><span data-stu-id="ed964-117">After completing the tutorial, it will look like this:</span></span>  

> ##### <span data-ttu-id="ed964-118">图 2</span><span class="sxs-lookup"><span data-stu-id="ed964-118">Figure 2</span></span>  
> <span data-ttu-id="ed964-119">网站在教程结束时的外观</span><span class="sxs-lookup"><span data-stu-id="ed964-119">What your site will look like at the end of the tutorial</span></span>  
> ![网站在教程结束时的外观][ImageCssIntro2]  

## <span data-ttu-id="ed964-121">目标</span><span class="sxs-lookup"><span data-stu-id="ed964-121">Goals</span></span>   

<span data-ttu-id="ed964-122">本教程结束时，你将了解：</span><span class="sxs-lookup"><span data-stu-id="ed964-122">By the end of this tutorial, you will understand:</span></span>  

*   <span data-ttu-id="ed964-123">如何使用 CSS 对网页进行样式。</span><span class="sxs-lookup"><span data-stu-id="ed964-123">How to use CSS to style a web page.</span></span>  
*   <span data-ttu-id="ed964-124">如何使用 Microsoft Edge DevTools 来试验 CSS。</span><span class="sxs-lookup"><span data-stu-id="ed964-124">How to use Microsoft Edge DevTools to experiment with CSS.</span></span>  
*   <span data-ttu-id="ed964-125">CSS 和 CSS 框架之间的区别。</span><span class="sxs-lookup"><span data-stu-id="ed964-125">The difference between CSS and CSS frameworks.</span></span>  

<span data-ttu-id="ed964-126">您还有一个真正的网站！</span><span class="sxs-lookup"><span data-stu-id="ed964-126">You'll also have a real website!</span></span>  

## <span data-ttu-id="ed964-127">必备条件</span><span class="sxs-lookup"><span data-stu-id="ed964-127">Prerequisites</span></span>   

<span data-ttu-id="ed964-128">在尝试本教程之前，请完成以下先决条件：</span><span class="sxs-lookup"><span data-stu-id="ed964-128">Before attempting this tutorial, complete the following prerequisites:</span></span>  

*   <span data-ttu-id="ed964-129">完整[入门 html 和 dom，][DevToolsBeginnersHtml]或者确保你对 HTML 和 dom 的理解类似于本教程中的教授。</span><span class="sxs-lookup"><span data-stu-id="ed964-129">Complete [Get Started with HTML and the DOM][DevToolsBeginnersHtml] or make sure that you have an understanding of HTML and the DOM similar to what's taught in that tutorial.</span></span>  
*   <span data-ttu-id="ed964-130">下载[Microsoft Edge][MicrosoftEdgeInsider] web 浏览器。</span><span class="sxs-lookup"><span data-stu-id="ed964-130">Download the [Microsoft Edge][MicrosoftEdgeInsider] web browser.</span></span>  <span data-ttu-id="ed964-131">本教程使用一组称为 Microsoft Edge DevTools 的 web 开发工具，这些工具内置于 Microsoft Edge 中。</span><span class="sxs-lookup"><span data-stu-id="ed964-131">This tutorial uses a set of web development tools, called the Microsoft Edge DevTools, that are built into Microsoft Edge.</span></span>  

## <span data-ttu-id="ed964-132">设置代码</span><span class="sxs-lookup"><span data-stu-id="ed964-132">Set up your code</span></span>   

<span data-ttu-id="ed964-133">为了开始创建您的网站，您需要设置代码：</span><span class="sxs-lookup"><span data-stu-id="ed964-133">In order to start creating your site, you need to set up your code:</span></span>  

1.  **<span data-ttu-id="ed964-134">如果您已完成本系列中的第一个教程，请跳过本部分！</span><span class="sxs-lookup"><span data-stu-id="ed964-134">If you have already completed the first tutorial in this series, skip this section!</span></span>  <span data-ttu-id="ed964-135">继续使用最后一个教程中的代码， [HTML 和 DOM 入门][DevToolsBeginnersHtml]。</span><span class="sxs-lookup"><span data-stu-id="ed964-135">Continue using your code from the last tutorial, [Get Started with HTML and the DOM][DevToolsBeginnersHtml].</span></span>**  
1.  <span data-ttu-id="ed964-136">打开[源代码][GlitchCookedAmphibianIndex]。</span><span class="sxs-lookup"><span data-stu-id="ed964-136">Open the [source code][GlitchCookedAmphibianIndex].</span></span>  <span data-ttu-id="ed964-137">浏览器的此选项卡将称为 "**编辑" 选项卡**。</span><span class="sxs-lookup"><span data-stu-id="ed964-137">This tab of your browser will be called the **editing tab**.</span></span>  
    
    > ##### <span data-ttu-id="ed964-138">图 3</span><span class="sxs-lookup"><span data-stu-id="ed964-138">Figure 3</span></span>  
    > <span data-ttu-id="ed964-139">"编辑" 选项卡</span><span class="sxs-lookup"><span data-stu-id="ed964-139">The editing tab</span></span>  
    > !["编辑" 选项卡][ImageCssSetup1]  
    
1.  <span data-ttu-id="ed964-141">单击 " **cooked-amphibian**"。</span><span class="sxs-lookup"><span data-stu-id="ed964-141">Click **cooked-amphibian**.</span></span>  <span data-ttu-id="ed964-142">将弹出一个菜单。</span><span class="sxs-lookup"><span data-stu-id="ed964-142">A menu pops up.</span></span>  
    
    > ##### <span data-ttu-id="ed964-143">图 4</span><span class="sxs-lookup"><span data-stu-id="ed964-143">Figure 4</span></span>  
    > <span data-ttu-id="ed964-144">"项目选项" 菜单</span><span class="sxs-lookup"><span data-stu-id="ed964-144">The Project Options menu</span></span>  
    > !["项目选项" 菜单][ImageCssSetup2]  

1.  <span data-ttu-id="ed964-146">单击 " **Remix Project**"。</span><span class="sxs-lookup"><span data-stu-id="ed964-146">Click **Remix Project**.</span></span>  <span data-ttu-id="ed964-147">问题创建可编辑的项目副本。</span><span class="sxs-lookup"><span data-stu-id="ed964-147">Glitch creates a copy of the project that you can edit.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="ed964-148">故障为新项目生成一个随机名称。</span><span class="sxs-lookup"><span data-stu-id="ed964-148">Glitch generates a random name for the new project.</span></span>  
    
1.  <span data-ttu-id="ed964-149">单击 "**显示**"，然后**在新窗口中**选择。</span><span class="sxs-lookup"><span data-stu-id="ed964-149">Click **Show** and select **In a New Window**.</span></span>  <span data-ttu-id="ed964-150">将打开另一个选项卡，其中包含您的网站的实时视图。</span><span class="sxs-lookup"><span data-stu-id="ed964-150">Another tab opens with a live view of your site.</span></span>  <span data-ttu-id="ed964-151">浏览器的此选项卡将称为 "**实时" 选项卡**。</span><span class="sxs-lookup"><span data-stu-id="ed964-151">This tab of your browser will be called the **live tab**.</span></span>  
    
    > ##### <span data-ttu-id="ed964-152">图 5</span><span class="sxs-lookup"><span data-stu-id="ed964-152">Figure 5</span></span>  
    > <span data-ttu-id="ed964-153">"实时" 选项卡</span><span class="sxs-lookup"><span data-stu-id="ed964-153">The live tab</span></span>  
    > !["实时" 选项卡][ImageCssSetup3]  

## <span data-ttu-id="ed964-155">了解 CSS</span><span class="sxs-lookup"><span data-stu-id="ed964-155">Understand CSS</span></span>   

<span data-ttu-id="ed964-156">**CSS**是确定网页布局和样式的计算机语言。</span><span class="sxs-lookup"><span data-stu-id="ed964-156">**CSS** is a computer language that determines the layout and styling of web pages.</span></span>  <span data-ttu-id="ed964-157">例如，下面是带有边框的段落：</span><span class="sxs-lookup"><span data-stu-id="ed964-157">For example, here is a paragraph with a border:</span></span>  

> ##### <span data-ttu-id="ed964-158">图 6</span><span class="sxs-lookup"><span data-stu-id="ed964-158">Figure 6</span></span>  
> <span data-ttu-id="ed964-159">此功能已设置了 CSS 样式</span><span class="sxs-lookup"><span data-stu-id="ed964-159">This has been styled with CSS</span></span>  
> ![此功能已设置了 CSS 样式][ImageCssStyled]  

<span data-ttu-id="ed964-161">下面是用于创建该段落的 HTML 和 CSS 代码：</span><span class="sxs-lookup"><span data-stu-id="ed964-161">Here is the HTML and CSS code used to create that paragraph:</span></span>  

```html
<p style="border: 1px dashed red; padding: 5px;">
    This has been styled with CSS.
</p>
```  

`style="border: 1px dashed red; padding: 5px;"` <span data-ttu-id="ed964-162">可能看起来很新。</span><span class="sxs-lookup"><span data-stu-id="ed964-162">probably looks new to you.</span></span>  <span data-ttu-id="ed964-163">其余内容应熟悉。</span><span class="sxs-lookup"><span data-stu-id="ed964-163">The rest should look familiar.</span></span>  <span data-ttu-id="ed964-164">如果不是，请在尝试本教程之前完成有关[HTML 和 DOM 的入门][DevToolsBeginnersHtml]。</span><span class="sxs-lookup"><span data-stu-id="ed964-164">If not, complete [Get Started with HTML and the DOM][DevToolsBeginnersHtml] before attempting this tutorial.</span></span>  

## <span data-ttu-id="ed964-165">添加内联样式</span><span class="sxs-lookup"><span data-stu-id="ed964-165">Add inline styles</span></span>   

<span data-ttu-id="ed964-166">如果要将样式应用于单个元素，请使用**内联样式**。</span><span class="sxs-lookup"><span data-stu-id="ed964-166">Use **inline styles** when you want to apply styles to a single element.</span></span>  <span data-ttu-id="ed964-167">立即试用：</span><span class="sxs-lookup"><span data-stu-id="ed964-167">Try it now:</span></span>  

1.  <span data-ttu-id="ed964-168">返回到 "编辑" 选项卡并打开 `index.html` 。</span><span class="sxs-lookup"><span data-stu-id="ed964-168">Go back to the editing tab and open `index.html`.</span></span>  
    
    > ##### <span data-ttu-id="ed964-169">图 7</span><span class="sxs-lookup"><span data-stu-id="ed964-169">Figure 7</span></span>  
    > `index.html`  
    > ![index.html][ImageCssInline1]  

1.  <span data-ttu-id="ed964-171">添加 `style="background-color: aliceblue;"` 到您 `<nav>` 的。</span><span class="sxs-lookup"><span data-stu-id="ed964-171">Add `style="background-color: aliceblue;"` to your `<nav>`.</span></span>  <span data-ttu-id="ed964-172">在下面的代码块中，第四行代码是你需要更改的代码。</span><span class="sxs-lookup"><span data-stu-id="ed964-172">In the code block below, the fourth line of code is the one you need to change.</span></span>  <span data-ttu-id="ed964-173">剩下的只是这样，您就可以确保将新代码放在正确的位置。</span><span class="sxs-lookup"><span data-stu-id="ed964-173">The rest is just there so you can be sure that you're putting the new code in the right place.</span></span>  
    
    ```html
    ...
        ...
            <header>
                <p>Welcome to my site!</p>
            </header>
            <nav style="background-color: aliceblue;">
                <ul>
                    <li><a href="/">Home</a></li>
                    ...
                ...
            ...
        ...
    ...
    ```  

1.  <span data-ttu-id="ed964-174">转到 "**实时" 选项卡**以查看所做的更改！</span><span class="sxs-lookup"><span data-stu-id="ed964-174">Go to the **live tab** to see the changes!</span></span>  <span data-ttu-id="ed964-175">现在，该分区的背景 `<nav>` 为蓝色。</span><span class="sxs-lookup"><span data-stu-id="ed964-175">The background of the `<nav>` section is now blue.</span></span>  
    
    > ##### <span data-ttu-id="ed964-176">图 8</span><span class="sxs-lookup"><span data-stu-id="ed964-176">Figure 8</span></span>  
    > <span data-ttu-id="ed964-177">"主页" 和 "联系人" 链接后面的背景色现在为蓝色</span><span class="sxs-lookup"><span data-stu-id="ed964-177">The background color behind the Home and Contact links is now blue</span></span>  
    > !["主页" 和 "联系人" 链接后面的背景色现在为蓝色][ImageCssInline2]  

## <span data-ttu-id="ed964-179">在具有内部样式表的单个页面上重新使用样式</span><span class="sxs-lookup"><span data-stu-id="ed964-179">Re-use styles on a single page with internal stylesheets</span></span>   

<span data-ttu-id="ed964-180">以前，你看到了一种将样式应用于单个标记的内联样式， `<p>` 如下所示：</span><span class="sxs-lookup"><span data-stu-id="ed964-180">Earlier, you saw an inline style that applied a style to a single `<p>` tag like this:</span></span>  

```html
<p style="border: 1px dashed red; padding: 5px;">
    This has been styled with CSS.
</p>
```  

<span data-ttu-id="ed964-181">如果您希望您的 `<p>` 网页上的所有元素的样式设置方式相同，该怎么办？</span><span class="sxs-lookup"><span data-stu-id="ed964-181">What if you wanted all of the `<p>` elements on your webpage to be styled the same way?</span></span>  <span data-ttu-id="ed964-182">您必须将代码复制并粘贴到 `<p>` 您的网站上的每个标记中。</span><span class="sxs-lookup"><span data-stu-id="ed964-182">You'd have to copy and paste the code into every single `<p>` tag on your site.</span></span>  <span data-ttu-id="ed964-183">这是很多时间和精力。</span><span class="sxs-lookup"><span data-stu-id="ed964-183">That's a lot of time and effort.</span></span>  <span data-ttu-id="ed964-184">如果需要进行编辑，则必须再次更改每个标签。</span><span class="sxs-lookup"><span data-stu-id="ed964-184">And, if you needed to make an edit, you'd have to change every tag again.</span></span>  <span data-ttu-id="ed964-185">**内部样式表**允许你编写一次 CSS，以便它应用于多个元素。</span><span class="sxs-lookup"><span data-stu-id="ed964-185">**Internal stylesheets** allow you to write your CSS once so that it applies to multiple elements.</span></span>  <span data-ttu-id="ed964-186">立即试用：</span><span class="sxs-lookup"><span data-stu-id="ed964-186">Try it now:</span></span>  

1.  <span data-ttu-id="ed964-187">在 "实时" 选项卡中，单击 "**联系人**" 以转到联系人页。</span><span class="sxs-lookup"><span data-stu-id="ed964-187">In the live tab, click **Contact** to go to the contact page.</span></span>  <span data-ttu-id="ed964-188">请注意 "**家庭**" 和 "**联系人**" 的字体。</span><span class="sxs-lookup"><span data-stu-id="ed964-188">Notice the font of **Home** and **Contact**.</span></span>  
    
    > ##### <span data-ttu-id="ed964-189">图 9</span><span class="sxs-lookup"><span data-stu-id="ed964-189">Figure 9</span></span>  
    > <span data-ttu-id="ed964-190">"联系人" 页面</span><span class="sxs-lookup"><span data-stu-id="ed964-190">The Contact page</span></span>  
    > !["联系人" 页面][ImageCssInternal1]  

1.  <span data-ttu-id="ed964-192">在 "**编辑器" 选项卡**中，转到 `contact.html` 。</span><span class="sxs-lookup"><span data-stu-id="ed964-192">In the **editor tab**, go to `contact.html`.</span></span>  
1.  <span data-ttu-id="ed964-193">将以下代码添加到 `contact.html` 。</span><span class="sxs-lookup"><span data-stu-id="ed964-193">Add the following code to `contact.html`.</span></span>  <span data-ttu-id="ed964-194">请记住，"行" `<style>` 和 "结束" 行 `</style>` 是你需要添加的内容。</span><span class="sxs-lookup"><span data-stu-id="ed964-194">Remember, the lines starting with `<style>` and ending with `</style>` are what you need to add.</span></span>  <span data-ttu-id="ed964-195">其他代码就在这里，您知道在哪里放置新代码。</span><span class="sxs-lookup"><span data-stu-id="ed964-195">The other code is just there so you know where to put the new code.</span></span>  
    
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
    
1.  <span data-ttu-id="ed964-196">返回到 "**实时" 选项卡**。</span><span class="sxs-lookup"><span data-stu-id="ed964-196">Go back to the **live tab**.</span></span>  
1.  <span data-ttu-id="ed964-197">单击 "**联系人**" 返回到联系人页。</span><span class="sxs-lookup"><span data-stu-id="ed964-197">Click **Contact** to go back to the contact page.</span></span>  <span data-ttu-id="ed964-198">**家庭**和**联系人**的字体已更改。</span><span class="sxs-lookup"><span data-stu-id="ed964-198">The font of **Home** and **Contact** has changed.</span></span>  
    
    > ##### <span data-ttu-id="ed964-199">图 10</span><span class="sxs-lookup"><span data-stu-id="ed964-199">Figure 10</span></span>  
    > <span data-ttu-id="ed964-200">主页和联系人链接的字体已更改</span><span class="sxs-lookup"><span data-stu-id="ed964-200">The font of the Home and Contact links has changed</span></span>  
    > ![主页和联系人链接的字体已更改][ImageCssInternal2]  
    
### <span data-ttu-id="ed964-202">了解内部样式表</span><span class="sxs-lookup"><span data-stu-id="ed964-202">Understand internal stylesheets</span></span>   

<span data-ttu-id="ed964-203">内部样式表使用**选择器**应用样式。</span><span class="sxs-lookup"><span data-stu-id="ed964-203">Internal stylesheets apply styles using **selectors**.</span></span>  <span data-ttu-id="ed964-204">选择器是可应用于一个或多个 HTML 元素的模式。</span><span class="sxs-lookup"><span data-stu-id="ed964-204">Selectors are patterns that may apply to one or more HTML elements.</span></span>  <span data-ttu-id="ed964-205">例如，在前面的代码中：</span><span class="sxs-lookup"><span data-stu-id="ed964-205">For example, in the previous code:</span></span>  

```html
...
    ...
        ...
        <style>
            li a {
              font-family: 'Courier New', Courier, Serif;
            }
        </style>
        ...
    ...
...
```  

`li a` <span data-ttu-id="ed964-206">是转换为 "任何包含" 的选择器 `<li>` `<a>` 。</span><span class="sxs-lookup"><span data-stu-id="ed964-206">is a selector that translates to "any `<li>` that contains an `<a>`".</span></span>  <span data-ttu-id="ed964-207">浏览器将更改 "**主页**" 和 "**联系人**" 链接的字体，因为它们与此模式匹配。</span><span class="sxs-lookup"><span data-stu-id="ed964-207">The browser changes the font of the **Home** and **Contact** links because they match this pattern.</span></span>  

```html
...
    ...
        ...
            ...
                <li><a href="/">Home</a></li>
                <li><a href="/contact.html">Contact</a></li>
                ...
            ...
        ...
    ...
...
```  

`font-family: 'Courier New', Courier, serif` <span data-ttu-id="ed964-208">是**声明**。</span><span class="sxs-lookup"><span data-stu-id="ed964-208">is a **declaration**.</span></span>  <span data-ttu-id="ed964-209">声明由两部分组成：**属性**和**值**。</span><span class="sxs-lookup"><span data-stu-id="ed964-209">A declaration is made of two parts: a **property** and a **value**.</span></span>  `font-family` <span data-ttu-id="ed964-210">是属性， `'Courier New', Courier, serif` 它是该属性的值。</span><span class="sxs-lookup"><span data-stu-id="ed964-210">is the property, and `'Courier New', Courier, serif` is the value of that property.</span></span>  <span data-ttu-id="ed964-211">该属性描述了你可以更改元素的样式的常规方式，而值显示了它应如何更改。</span><span class="sxs-lookup"><span data-stu-id="ed964-211">The property describes a general way that you can change the element's style, and the value says how exactly it should change.</span></span>  <span data-ttu-id="ed964-212">例如， `font-family: 'Courier New', Courier, serif` 向浏览器提供此指令： "将与模式匹配的元素的字体设置 `li a` 为 `'Courier New'` 。</span><span class="sxs-lookup"><span data-stu-id="ed964-212">For example, `font-family: 'Courier New', Courier, serif` gives the browser this instruction:  "Set the font of elements that match the pattern `li a` to `'Courier New'`.</span></span>  <span data-ttu-id="ed964-213">如果该字体不可用，请使用 `Courier` 。</span><span class="sxs-lookup"><span data-stu-id="ed964-213">If that font isn't available, use `Courier`.</span></span>  <span data-ttu-id="ed964-214">如果该功能不可用，请使用 `serif` 。</span><span class="sxs-lookup"><span data-stu-id="ed964-214">If that isn't available, use `serif`."</span></span>  

### <span data-ttu-id="ed964-215">将多个选择器添加到规则集</span><span class="sxs-lookup"><span data-stu-id="ed964-215">Add multiple selectors to a ruleset</span></span>   

<span data-ttu-id="ed964-216">类似于下面所示的 CSS 代码块称为 "**规则集**"。</span><span class="sxs-lookup"><span data-stu-id="ed964-216">A block of CSS code like what you see below is called a **ruleset**.</span></span>  

```css
li a {
  font-family: 'Courier New', Courier, monospace;
}
```  

<span data-ttu-id="ed964-217">使用逗号将多个选择器添加到规则集。</span><span class="sxs-lookup"><span data-stu-id="ed964-217">Use commas to add multiple selectors to a ruleset.</span></span>  <span data-ttu-id="ed964-218">立即试用：</span><span class="sxs-lookup"><span data-stu-id="ed964-218">Try it now:</span></span>  

1.  <span data-ttu-id="ed964-219">在 "**编辑器" 选项卡**中，打开 `contact.html` 。</span><span class="sxs-lookup"><span data-stu-id="ed964-219">In the **editor tab**, open `contact.html`.</span></span>  
1.  <span data-ttu-id="ed964-220">`li a`键入后 `, h1` 。</span><span class="sxs-lookup"><span data-stu-id="ed964-220">After `li a` type `, h1`.</span></span>  

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

    <span data-ttu-id="ed964-221">这将告知浏览器对 `<h1>` 元素样式的样式与与模式匹配的元素的样式一样 `li a` 。</span><span class="sxs-lookup"><span data-stu-id="ed964-221">This tells the browser to style `<h1>` elements the same way that it styles elements that match the pattern `li a`.</span></span>  
    
1.  <span data-ttu-id="ed964-222">转到 "**实时" 选项卡**。</span><span class="sxs-lookup"><span data-stu-id="ed964-222">Go to the **live tab**.</span></span>  
1.  <span data-ttu-id="ed964-223">单击**联系人**链接返回到联系人页。</span><span class="sxs-lookup"><span data-stu-id="ed964-223">Click the **Contact** link to go back to the contact page.</span></span>  <span data-ttu-id="ed964-224">现在，请**与我联系！**</span><span class="sxs-lookup"><span data-stu-id="ed964-224">Now, **Contact Me!**</span></span> <span data-ttu-id="ed964-225">的字体与导航链接的字体相同。</span><span class="sxs-lookup"><span data-stu-id="ed964-225">has the same font as the navigation links.</span></span>  
    
    > ##### <span data-ttu-id="ed964-226">图 11</span><span class="sxs-lookup"><span data-stu-id="ed964-226">Figure 11</span></span>  
    > <span data-ttu-id="ed964-227">文本 "联系我！"</span><span class="sxs-lookup"><span data-stu-id="ed964-227">The text 'Contact Me!'</span></span> <span data-ttu-id="ed964-228">现在与 "主页" 和 "联系人" 链接的字体相同</span><span class="sxs-lookup"><span data-stu-id="ed964-228">now has the same font as the Home and Contact links</span></span>  
    > ![文本与我联系！][ImageCssMultiple1]  

## <span data-ttu-id="ed964-231">试用 DevTools</span><span class="sxs-lookup"><span data-stu-id="ed964-231">Experiment with DevTools</span></span>   

<span data-ttu-id="ed964-232">在你继续迁移到主 web 开发时，你会发现 CSS 可能会很难。</span><span class="sxs-lookup"><span data-stu-id="ed964-232">As you continue your journey to master web development, you'll find that CSS can be tricky.</span></span>  <span data-ttu-id="ed964-233">你将编写一些 CSS，并希望它以一种方式显示，但浏览器执行完全不同的操作。</span><span class="sxs-lookup"><span data-stu-id="ed964-233">You'll write some CSS and expect it to display one way, but the browser does something completely different.</span></span>  <span data-ttu-id="ed964-234">Microsoft Edge DevTools 使你可以轻松地体验更改，并立即查看这些更改对页面的影响。</span><span class="sxs-lookup"><span data-stu-id="ed964-234">Microsoft Edge DevTools makes it easy to experiment with changes and immediately see how those changes affect the page.</span></span>  

### <span data-ttu-id="ed964-235">将声明添加到 DevTools 中的现有 rulest</span><span class="sxs-lookup"><span data-stu-id="ed964-235">Add a declaration to an existing rulest in DevTools</span></span>   

<span data-ttu-id="ed964-236">当你希望循环访问现有元素的样式时，请将声明添加到现有的规则集。</span><span class="sxs-lookup"><span data-stu-id="ed964-236">When you want to iterate on the style of an existing element, add a declaration to an existing ruleset.</span></span>  <span data-ttu-id="ed964-237">立即试用：</span><span class="sxs-lookup"><span data-stu-id="ed964-237">Try it now:</span></span>  

1.  <span data-ttu-id="ed964-238">右键单击 "**主页**" 链接，然后选择 "**检查**"。</span><span class="sxs-lookup"><span data-stu-id="ed964-238">Right-click the **Home** link and select **Inspect**.</span></span>  
    
    > ##### <span data-ttu-id="ed964-239">图 12</span><span class="sxs-lookup"><span data-stu-id="ed964-239">Figure 12</span></span>  
    > <span data-ttu-id="ed964-240">检查主链接</span><span class="sxs-lookup"><span data-stu-id="ed964-240">Inspecting the Home link</span></span>  
    > ![检查主链接][ImageCssAdd1]  
    
    <span data-ttu-id="ed964-242">DevTools 将在您的页面旁打开。</span><span class="sxs-lookup"><span data-stu-id="ed964-242">DevTools opens up alongside your page.</span></span>  <span data-ttu-id="ed964-243">表示 Home 链接的代码在 `<a href="/">Home</a>` DOM 树中突出显示为蓝色。</span><span class="sxs-lookup"><span data-stu-id="ed964-243">The code that represents the Home link, `<a href="/">Home</a>` is highlighted blue in the DOM Tree.</span></span>  <span data-ttu-id="ed964-244">应熟悉[HTML 和 DOM 入门][DevToolsBeginnersHtml]。</span><span class="sxs-lookup"><span data-stu-id="ed964-244">This should be familiar from [Get Started with HTML and the DOM][DevToolsBeginnersHtml].</span></span>  <span data-ttu-id="ed964-245">在 DOM 树下方的 "**样式**" 选项卡中，你可以看到 `font-family: 'Courier New', Courier, serif` 你之前添加到的声明 `contact.html` 。</span><span class="sxs-lookup"><span data-stu-id="ed964-245">In the **Styles** tab below the DOM Tree you can see the `font-family: 'Courier New', Courier, serif` declaration that you added to `contact.html` earlier.</span></span>  
    
    > ##### <span data-ttu-id="ed964-246">图 13</span><span class="sxs-lookup"><span data-stu-id="ed964-246">Figure 13</span></span>  
    > <span data-ttu-id="ed964-247">"样式" 选项卡位于 DOM 树的下方</span><span class="sxs-lookup"><span data-stu-id="ed964-247">The Styles tab is below the DOM Tree</span></span>  
    > !["样式" 选项卡位于 DOM 树的下方][ImageCssAdd2]  
    
    <span data-ttu-id="ed964-249">如果 DevTools 窗口是宽的，则 "样式" 选项卡位于 DOM 树的右侧。</span><span class="sxs-lookup"><span data-stu-id="ed964-249">If your DevTools window is wide, the Styles tab is to the right of the DOM Tree.</span></span>  
    
    > ##### <span data-ttu-id="ed964-250">图 14</span><span class="sxs-lookup"><span data-stu-id="ed964-250">Figure 14</span></span>  
    > <span data-ttu-id="ed964-251">"样式" 选项卡位于 DOM 树的右侧</span><span class="sxs-lookup"><span data-stu-id="ed964-251">The Styles tab is to the right of the DOM Tree</span></span>  
    > !["样式" 选项卡位于 DOM 树的右侧][ImageCssAdd3]  
    
1.  <span data-ttu-id="ed964-253">单击下面的空白 `font-family: 'Courier New', Courier, Serif` 以添加新声明。</span><span class="sxs-lookup"><span data-stu-id="ed964-253">Click the whitespace below `font-family: 'Courier New', Courier, Serif` to add a new declaration.</span></span>  
    
    > ##### <span data-ttu-id="ed964-254">图 15</span><span class="sxs-lookup"><span data-stu-id="ed964-254">Figure 15</span></span>  
    > <span data-ttu-id="ed964-255">添加新声明</span><span class="sxs-lookup"><span data-stu-id="ed964-255">Adding a new declaration</span></span>  
    > ![添加新声明][ImageCssAdd4]  
    
1.  <span data-ttu-id="ed964-257">键入 `color` ，然后按 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="ed964-257">Type `color` and then press `Enter`.</span></span>  <span data-ttu-id="ed964-258">"自动完成" UI 建议您键入时的选项。</span><span class="sxs-lookup"><span data-stu-id="ed964-258">The autocomplete UI suggests options as you type.</span></span>  
    
    > ##### <span data-ttu-id="ed964-259">图 16</span><span class="sxs-lookup"><span data-stu-id="ed964-259">Figure 16</span></span>  
    > <span data-ttu-id="ed964-260">键入</span><span class="sxs-lookup"><span data-stu-id="ed964-260">Typing</span></span> `color`  
    > ![键入颜色][ImageCssAdd5]  

1.  <span data-ttu-id="ed964-262">键入 `magenta` ，然后 `Enter` 再次按。</span><span class="sxs-lookup"><span data-stu-id="ed964-262">Type `magenta` and then press `Enter` again.</span></span>  <span data-ttu-id="ed964-263">"联系人" 页面上的所有文本现在均为 "洋红"。</span><span class="sxs-lookup"><span data-stu-id="ed964-263">All of the text on the contact page is now magenta.</span></span>  
    
    > ##### <span data-ttu-id="ed964-264">图 17</span><span class="sxs-lookup"><span data-stu-id="ed964-264">Figure 17</span></span>  
    > <span data-ttu-id="ed964-265">键入</span><span class="sxs-lookup"><span data-stu-id="ed964-265">Typing</span></span> `magenta`  
    > ![键入洋红][ImageCssAdd6]  
    
### <span data-ttu-id="ed964-267">在 DevTools 中编辑声明</span><span class="sxs-lookup"><span data-stu-id="ed964-267">Edit a declaration in DevTools</span></span>   

<span data-ttu-id="ed964-268">您也可以在 DevTools 中编辑现有声明。</span><span class="sxs-lookup"><span data-stu-id="ed964-268">You can also edit existing declarations in DevTools.</span></span>  <span data-ttu-id="ed964-269">立即试用：</span><span class="sxs-lookup"><span data-stu-id="ed964-269">Try it now:</span></span>  

1.  <span data-ttu-id="ed964-270">单击旁边的洋红色方块 `magenta` 。</span><span class="sxs-lookup"><span data-stu-id="ed964-270">Click the magenta square next to `magenta`.</span></span>  <span data-ttu-id="ed964-271">将弹出一个颜色选取器。</span><span class="sxs-lookup"><span data-stu-id="ed964-271">A color picker pops up.</span></span>  
    
    > ##### <span data-ttu-id="ed964-272">图18</span><span class="sxs-lookup"><span data-stu-id="ed964-272">Figure 18</span></span>  
    > <span data-ttu-id="ed964-273">颜色选取器</span><span class="sxs-lookup"><span data-stu-id="ed964-273">The Color Picker</span></span>  
    > ![颜色选取器][ImageCssEdit1]  
    
1.  <span data-ttu-id="ed964-275">使用拾色器将字体文本更改为您喜欢的颜色。</span><span class="sxs-lookup"><span data-stu-id="ed964-275">Use the color picker to change the font text to a color that you like.</span></span>  
    
    > ##### <span data-ttu-id="ed964-276">图19</span><span class="sxs-lookup"><span data-stu-id="ed964-276">Figure 19</span></span>  
    > <span data-ttu-id="ed964-277">通过颜色选取器将字体颜色更改为紫色</span><span class="sxs-lookup"><span data-stu-id="ed964-277">Changing the font color to purple with the Color Picker</span></span>  
    > ![通过颜色选取器将字体颜色更改为紫色][ImageCssEdit2]  

### <span data-ttu-id="ed964-279">在 DevTools 中添加新的规则集</span><span class="sxs-lookup"><span data-stu-id="ed964-279">Add a new ruleset in DevTools</span></span>   

<span data-ttu-id="ed964-280">你还可以在 DevTools 中添加新的规则集。</span><span class="sxs-lookup"><span data-stu-id="ed964-280">You can also add new rulesets in DevTools.</span></span>  <span data-ttu-id="ed964-281">立即试用：</span><span class="sxs-lookup"><span data-stu-id="ed964-281">Try it now:</span></span>  

1.  <span data-ttu-id="ed964-282">单击 "**新建样式规则**" 下的 "新建 ![ 样式规则" ][ImageNewStyleRuleIcon] **。**</span><span class="sxs-lookup"><span data-stu-id="ed964-282">Click **New Style Rule** ![New Style Rule][ImageNewStyleRuleIcon] which is next to **.cls**.</span></span>  <span data-ttu-id="ed964-283">将显示一个包含选择器的空规则集 `a` 。</span><span class="sxs-lookup"><span data-stu-id="ed964-283">An empty ruleset appears with `a` as the selector.</span></span>  
    
    > ##### <span data-ttu-id="ed964-284">图20</span><span class="sxs-lookup"><span data-stu-id="ed964-284">Figure 20</span></span>  
    > <span data-ttu-id="ed964-285">添加新规则</span><span class="sxs-lookup"><span data-stu-id="ed964-285">Adding a new rule</span></span>  
    > ![添加新规则][ImageCssRule1]  
    
1.  <span data-ttu-id="ed964-287">用 `a:hover` 取代 `a`。</span><span class="sxs-lookup"><span data-stu-id="ed964-287">Replace `a` with `a:hover`.</span></span>  
    
    > ##### <span data-ttu-id="ed964-288">图21</span><span class="sxs-lookup"><span data-stu-id="ed964-288">Figure 21</span></span>  
    > <span data-ttu-id="ed964-289">替换 `a` 为</span><span class="sxs-lookup"><span data-stu-id="ed964-289">Replacing `a` with</span></span> `a:hover`  
    > ![将 with a:hover 替换为][ImageCssRule2]  
    
    `:hover` <span data-ttu-id="ed964-291">是**伪类**。</span><span class="sxs-lookup"><span data-stu-id="ed964-291">is a **pseudo-class**.</span></span>  <span data-ttu-id="ed964-292">当元素进入特殊状态时，使用伪类对元素进行样式。</span><span class="sxs-lookup"><span data-stu-id="ed964-292">Use pseudo-classes to style elements when they enter special states.</span></span>  <span data-ttu-id="ed964-293">例如， `a:hover` 只有当你将鼠标悬停在某个元素上时，该样式才会生效 `<a>` 。</span><span class="sxs-lookup"><span data-stu-id="ed964-293">For example, the `a:hover` style only takes effect when you're hovering over an `<a>` element.</span></span>  
    
1.  <span data-ttu-id="ed964-294">在括号之间单击以添加新的声明。</span><span class="sxs-lookup"><span data-stu-id="ed964-294">Click between the brackets to add a new declaration.</span></span>  
1.  <span data-ttu-id="ed964-295">键入 `background-color` 声明名称，然后按 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="ed964-295">Type `background-color` for the declaration name and then press `Enter`.</span></span>  
    
    > ##### <span data-ttu-id="ed964-296">图22</span><span class="sxs-lookup"><span data-stu-id="ed964-296">Figure 22</span></span>  
    > <span data-ttu-id="ed964-297">键入</span><span class="sxs-lookup"><span data-stu-id="ed964-297">Typing</span></span> `background-color`  
    > ![键入背景色][ImageCssRule3]  
    
1.  <span data-ttu-id="ed964-299">键入 `green` 声明值，然后按 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="ed964-299">Type `green` for the declaration value and then press `Enter`.</span></span>  
    
    > ##### <span data-ttu-id="ed964-300">图23</span><span class="sxs-lookup"><span data-stu-id="ed964-300">Figure 23</span></span>  
    > <span data-ttu-id="ed964-301">键入</span><span class="sxs-lookup"><span data-stu-id="ed964-301">Typing</span></span> `green`  
    > ![键入绿色][ImageCssRule4]  
    
1.  <span data-ttu-id="ed964-303">将鼠标悬停在 "**开始**" 链接上。</span><span class="sxs-lookup"><span data-stu-id="ed964-303">Hover your mouse over the **Home** link.</span></span>  <span data-ttu-id="ed964-304">链接的背景变为绿色。</span><span class="sxs-lookup"><span data-stu-id="ed964-304">The background of the link turns green.</span></span>  
    
    > ##### <span data-ttu-id="ed964-305">图24</span><span class="sxs-lookup"><span data-stu-id="ed964-305">Figure 24</span></span>  
    > <span data-ttu-id="ed964-306">将鼠标悬停在 Home 链接上以显示绿色背景</span><span class="sxs-lookup"><span data-stu-id="ed964-306">Hovering over the Home link to reveal its green background</span></span>  
    > ![将鼠标悬停在 Home 链接上以显示绿色背景][ImageCssRule5]  
    
## <span data-ttu-id="ed964-308">跨页面使用外部样式表重新使用样式</span><span class="sxs-lookup"><span data-stu-id="ed964-308">Re-use styles across pages with external stylesheets</span></span>   

<span data-ttu-id="ed964-309">之前，您已将此内部样式表添加到 `contact.html` ：</span><span class="sxs-lookup"><span data-stu-id="ed964-309">Earlier you added this internal stylesheet to `contact.html`:</span></span>  

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

<span data-ttu-id="ed964-310">如果你想要以 `index.html` 相同的方式设置样式，该怎么办？</span><span class="sxs-lookup"><span data-stu-id="ed964-310">What if you wanted to style `index.html` the same way?</span></span>  <span data-ttu-id="ed964-311">如果您有*一千*个页面，并且想要将这些样式应用到所有这些页面，该怎么办？</span><span class="sxs-lookup"><span data-stu-id="ed964-311">What if you had a *thousand* pages and you wanted to apply these styles to all of them?</span></span>  <span data-ttu-id="ed964-312">您必须将此内部样式表复制并粘贴到您的网站上的每一个网页中。</span><span class="sxs-lookup"><span data-stu-id="ed964-312">You'd have to copy and paste this internal stylesheet into every single web page on your site.</span></span>  <span data-ttu-id="ed964-313">**外部样式表**允许你在将 CSS 应用到多个页面后编写它。</span><span class="sxs-lookup"><span data-stu-id="ed964-313">**External stylesheets** allow you to write your CSS once yet apply it to multiple pages.</span></span>  <span data-ttu-id="ed964-314">立即试用：</span><span class="sxs-lookup"><span data-stu-id="ed964-314">Try it now:</span></span>  

1.  <span data-ttu-id="ed964-315">首先，重新加载 "实时" 选项卡以删除您在 DevTools 中所做的更改。</span><span class="sxs-lookup"><span data-stu-id="ed964-315">First, reload the live tab to remove the changes that you made in DevTools.</span></span>  
    
    > ##### <span data-ttu-id="ed964-316">图25</span><span class="sxs-lookup"><span data-stu-id="ed964-316">Figure 25</span></span>  
    >  <span data-ttu-id="ed964-317">重新加载页面后，DevTools 中所做的更改已丢失</span><span class="sxs-lookup"><span data-stu-id="ed964-317">After reloading the page the changes that were made in DevTools are gone</span></span>  
    > ![ <span data-ttu-id="ed964-318">重新加载页面后，DevTools 中所做的更改已丢失</span><span class="sxs-lookup"><span data-stu-id="ed964-318">After reloading the page the changes that were made in DevTools are gone</span></span>][ImageCssExternal01]  
    
1.  <span data-ttu-id="ed964-319">返回 "**编辑器" 选项卡**，然后打开 `contact.html` 。</span><span class="sxs-lookup"><span data-stu-id="ed964-319">Go back to the **editor tab** and open `contact.html`.</span></span>  
    
    > ##### <span data-ttu-id="ed964-320">图26</span><span class="sxs-lookup"><span data-stu-id="ed964-320">Figure 26</span></span>  
    > `contact.html`  
    > ![联系 .html][ImageCssExternal02]  
    
1.  <span data-ttu-id="ed964-322">删除与之间的所有内容 `<style>` `</style>` ，包括 `<style>` 和 `</style>` 。</span><span class="sxs-lookup"><span data-stu-id="ed964-322">Delete everything between `<style>` and `</style>`, including `<style>` and `</style>`.</span></span>  
    
    > ##### <span data-ttu-id="ed964-323">图27</span><span class="sxs-lookup"><span data-stu-id="ed964-323">Figure 27</span></span>  
    > <span data-ttu-id="ed964-324">已删除样式标记</span><span class="sxs-lookup"><span data-stu-id="ed964-324">The style tag has been removed</span></span>  
    > ![已删除样式标记][ImageCssExternal03]  
    
1.  <span data-ttu-id="ed964-326">转到 `index.html` 并 `style="background-color: aliceblue;"` 从标记中删除 `<nav>` 。</span><span class="sxs-lookup"><span data-stu-id="ed964-326">Go to `index.html` and remove `style="background-color: aliceblue;"` from the `<nav>` tag.</span></span>  <span data-ttu-id="ed964-327">您现在已删除以前添加到网站的所有 CSS。</span><span class="sxs-lookup"><span data-stu-id="ed964-327">You have now removed all of the CSS that you previously added to your site.</span></span>  
    
    > ##### <span data-ttu-id="ed964-328">图28</span><span class="sxs-lookup"><span data-stu-id="ed964-328">Figure 28</span></span>  
    > <span data-ttu-id="ed964-329">内联样式已从导航元素中删除</span><span class="sxs-lookup"><span data-stu-id="ed964-329">The inline style has been removed from the nav element</span></span>  
    > ![内联样式已从导航元素中删除][ImageCssExternal04]  

1.  <span data-ttu-id="ed964-331">单击 "**新建文件**"。</span><span class="sxs-lookup"><span data-stu-id="ed964-331">Click **New File**.</span></span>  
    
    > ##### <span data-ttu-id="ed964-332">图29</span><span class="sxs-lookup"><span data-stu-id="ed964-332">Figure 29</span></span>  
    > <span data-ttu-id="ed964-333">"新建文件" 对话框</span><span class="sxs-lookup"><span data-stu-id="ed964-333">The new file dialog</span></span>  
    > !["新建文件" 对话框][ImageCssExternal05]  
    
1.  <span data-ttu-id="ed964-335">替换 `cool-file.js` 为 `style.css` ，然后单击 "**添加文件**"。</span><span class="sxs-lookup"><span data-stu-id="ed964-335">Replace `cool-file.js` with `style.css` and then click **Add File**.</span></span>  
    
    > ##### <span data-ttu-id="ed964-336">图30</span><span class="sxs-lookup"><span data-stu-id="ed964-336">Figure 30</span></span>  
    > <span data-ttu-id="ed964-337">键入</span><span class="sxs-lookup"><span data-stu-id="ed964-337">Typing</span></span> `style.css`  
    > ![键入样式 .css][ImageCssExternal06]  
    
1.  <span data-ttu-id="ed964-339">将此代码粘贴到 `style.css` ：</span><span class="sxs-lookup"><span data-stu-id="ed964-339">Paste this code into `style.css`:</span></span>  
    
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
    
    > ##### <span data-ttu-id="ed964-340">图31</span><span class="sxs-lookup"><span data-stu-id="ed964-340">Figure 31</span></span>  
    > <span data-ttu-id="ed964-341">将代码添加到</span><span class="sxs-lookup"><span data-stu-id="ed964-341">Adding code to</span></span> `style.css`  
    > ![将代码添加到 style][ImageCssExternal07]  
    
    <span data-ttu-id="ed964-343">此时，你已创建了一个外部样式表，但你的 HTML 不知道它是否存在。</span><span class="sxs-lookup"><span data-stu-id="ed964-343">At this point, you have created an external stylesheet, but your HTML doesn't know that it exists, yet.</span></span>  
    
1.  <span data-ttu-id="ed964-344">打开 `index.html`。</span><span class="sxs-lookup"><span data-stu-id="ed964-344">Open `index.html`.</span></span>  
1.  <span data-ttu-id="ed964-345">添加 `<link rel="stylesheet" href="style.css">` 到你的 HTML。</span><span class="sxs-lookup"><span data-stu-id="ed964-345">Add `<link rel="stylesheet" href="style.css">` to your HTML.</span></span>  
    
    ```html
    ...
        <head>
            ...
            <meta name="viewport" content="width=device-width, initial-scale=1">
            <link rel="stylesheet" href="style.css">
        </head>
        ...
    ...
    ```  

    > ##### <span data-ttu-id="ed964-346">图32</span><span class="sxs-lookup"><span data-stu-id="ed964-346">Figure 32</span></span>  
    > <span data-ttu-id="ed964-347">链接到</span><span class="sxs-lookup"><span data-stu-id="ed964-347">Linking to</span></span> `style.css`  
    > ![链接到样式 .css][ImageCssExternal08]  

1.  <span data-ttu-id="ed964-349">转到此处 `contact.html` 并添加链接。</span><span class="sxs-lookup"><span data-stu-id="ed964-349">Go to `contact.html` and add the link there, too.</span></span>  
    
    > ##### <span data-ttu-id="ed964-350">图33</span><span class="sxs-lookup"><span data-stu-id="ed964-350">Figure 33</span></span>  
    > <span data-ttu-id="ed964-351">链接到 `style.css`</span><span class="sxs-lookup"><span data-stu-id="ed964-351">Linking to `style.css` in</span></span> `contact.html`  
    > ![链接到 "style" 中的 ".css"。 html][ImageCssExternal09]  

1.  <span data-ttu-id="ed964-353">转到 "**实时" 选项卡**。 现在，主页的字体与上一节中的字体相同，并具有蓝色导航部分。</span><span class="sxs-lookup"><span data-stu-id="ed964-353">Go to the **live tab**.  The home page now has the same font from the last section and a blue navigation section.</span></span>  
    
    > ##### <span data-ttu-id="ed964-354">图34</span><span class="sxs-lookup"><span data-stu-id="ed964-354">Figure 34</span></span>  
    > <span data-ttu-id="ed964-355">主页</span><span class="sxs-lookup"><span data-stu-id="ed964-355">The home page</span></span>  
    > ![主页][ImageCssExternal10]  
    
1.  <span data-ttu-id="ed964-357">单击**联系人**链接转到 "联系人" 页面。</span><span class="sxs-lookup"><span data-stu-id="ed964-357">Click the **Contact** link to go to the contact page.</span></span>  <span data-ttu-id="ed964-358">"联系人" 页面的格式与 "主页" 的格式相同。</span><span class="sxs-lookup"><span data-stu-id="ed964-358">The contact page has the same formatting as the home page.</span></span>  
    
    > ##### <span data-ttu-id="ed964-359">图35</span><span class="sxs-lookup"><span data-stu-id="ed964-359">Figure 35</span></span>  
    > <span data-ttu-id="ed964-360">"联系人" 页面</span><span class="sxs-lookup"><span data-stu-id="ed964-360">The contact page</span></span>  
    > !["联系人" 页面][ImageCssExternal11]  
    
## <span data-ttu-id="ed964-362">使用 CSS 框架</span><span class="sxs-lookup"><span data-stu-id="ed964-362">Use a CSS framework</span></span>   

<span data-ttu-id="ed964-363">**CSS 框架**是由其他开发者构建的样式的集合，可使创建引人注目的网站更容易。</span><span class="sxs-lookup"><span data-stu-id="ed964-363">**CSS frameworks** are collections of styles built by other developers that make it easier to create attractive web sites.</span></span>  <span data-ttu-id="ed964-364">框架为你提供可在页面元素上使用的样式集合，而不是自己定义样式。</span><span class="sxs-lookup"><span data-stu-id="ed964-364">Instead of defining styles yourself, a framework gives you a collection of styles that you can use on your page elements.</span></span>  

1.  <span data-ttu-id="ed964-365">复制以下代码：</span><span class="sxs-lookup"><span data-stu-id="ed964-365">Copy the following code:</span></span>  
    
    ```html
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.1.1/css/bootstrap.min.css">
    ```  
    
1.  <span data-ttu-id="ed964-366">转到 "编辑" 选项卡，然后将代码粘贴到 `contact.html` 。</span><span class="sxs-lookup"><span data-stu-id="ed964-366">Go to the editing tab and paste the code into `contact.html`.</span></span>  
    
    > ##### <span data-ttu-id="ed964-367">图36</span><span class="sxs-lookup"><span data-stu-id="ed964-367">Figure 36</span></span>  
    > <span data-ttu-id="ed964-368">链接到中的框架</span><span class="sxs-lookup"><span data-stu-id="ed964-368">Linking to the framework in</span></span> `contact.html`  
    > ![链接到 contact 中的框架][ImageCssFramework1]  
    
1.  <span data-ttu-id="ed964-370">将代码粘贴到 `index.html` 中。</span><span class="sxs-lookup"><span data-stu-id="ed964-370">Paste the code into `index.html`, as well.</span></span>  
    
    > ##### <span data-ttu-id="ed964-371">图37</span><span class="sxs-lookup"><span data-stu-id="ed964-371">Figure 37</span></span>  
    > <span data-ttu-id="ed964-372">链接到中的框架</span><span class="sxs-lookup"><span data-stu-id="ed964-372">Linking to the framework in</span></span> `index.html`  
    > ![链接到索引 html 中的框架][ImageCssFramework2]  
    
1.  <span data-ttu-id="ed964-374">返回到 "实时" 选项卡以查看所做的更改。</span><span class="sxs-lookup"><span data-stu-id="ed964-374">Go back to the live tab to view your changes.</span></span>  <span data-ttu-id="ed964-375">虽然元素的背景色 `<nav>` 和元素的字体 `li a` 相同，但其他元素的字体已更改。</span><span class="sxs-lookup"><span data-stu-id="ed964-375">While the background color of the `<nav>` and the font of the `li a` elements are the same, the font of the other elements has changed.</span></span>  
    
    > ##### <span data-ttu-id="ed964-376">图38</span><span class="sxs-lookup"><span data-stu-id="ed964-376">Figure 38</span></span>  
    > <span data-ttu-id="ed964-377">主页上的某些字体因框架而发生更改</span><span class="sxs-lookup"><span data-stu-id="ed964-377">Some of the font on the home page has changed because of the framework</span></span>  
    > ![主页上的某些字体因框架而发生更改][ImageCssFramework3]  

### <span data-ttu-id="ed964-379">使用类</span><span class="sxs-lookup"><span data-stu-id="ed964-379">Use a class</span></span>   

<span data-ttu-id="ed964-380">在最后一节中，你将引导数据库添加到网页，这将更改网站上某些元素的字体。</span><span class="sxs-lookup"><span data-stu-id="ed964-380">In the last section, you added Bootstrap to your web pages, which changed the fonts of some of the elements on your site.</span></span>  <span data-ttu-id="ed964-381">CSS 框架可帮助你通过非常少的代码对页面进行重大更改。</span><span class="sxs-lookup"><span data-stu-id="ed964-381">CSS frameworks can help you make major changes to your page with very little code.</span></span>  <span data-ttu-id="ed964-382">通过更改页眉立即试用：</span><span class="sxs-lookup"><span data-stu-id="ed964-382">Try it now by changing your header:</span></span>  

1.  <span data-ttu-id="ed964-383">复制此代码：</span><span class="sxs-lookup"><span data-stu-id="ed964-383">Copy this code:</span></span>  
    
    ```html
    class="jumbotron jumbotron-fluid"  
    ```  
    
1.  <span data-ttu-id="ed964-384">将此代码添加到 `<header>` 中的标签 `index.html` 。</span><span class="sxs-lookup"><span data-stu-id="ed964-384">Add this code to your `<header>` tag in `index.html`.</span></span>  
    
    > ##### <span data-ttu-id="ed964-385">图39</span><span class="sxs-lookup"><span data-stu-id="ed964-385">Figure 39</span></span>  
    > <span data-ttu-id="ed964-386">添加类</span><span class="sxs-lookup"><span data-stu-id="ed964-386">Adding classes in</span></span> `index.html`  
    > ![在索引 html 中添加类][ImageCssJumbotron1]  
    
1.  <span data-ttu-id="ed964-388">将代码添加到您 `<header>` 的标签 `contact.html` 。</span><span class="sxs-lookup"><span data-stu-id="ed964-388">Add the code to your `<header>` tag in `contact.html`, too.</span></span>  
    
    > ##### <span data-ttu-id="ed964-389">图40</span><span class="sxs-lookup"><span data-stu-id="ed964-389">Figure 40</span></span>  
    > <span data-ttu-id="ed964-390">添加类</span><span class="sxs-lookup"><span data-stu-id="ed964-390">Adding classes in</span></span> `contact.html`  
    > ![将课堂添加到 contact. html][ImageCssJumbotron2]  
    
1.  <span data-ttu-id="ed964-392">在 "实时" 选项卡中查看所做的更改。 现在，您的页眉周围有一个大灰的框。</span><span class="sxs-lookup"><span data-stu-id="ed964-392">View your changes in the live tab.  There's a big, grey box around your header now.</span></span>  
    
    > ##### <span data-ttu-id="ed964-393">图41</span><span class="sxs-lookup"><span data-stu-id="ed964-393">Figure 41</span></span>  
    > <span data-ttu-id="ed964-394">标题现在周围有一个大灰框</span><span class="sxs-lookup"><span data-stu-id="ed964-394">The header now has a big, grey box around it</span></span>  
    > ![标题现在周围有一个大灰框][ImageCssJumbotron3]  
    
### <span data-ttu-id="ed964-396">了解类</span><span class="sxs-lookup"><span data-stu-id="ed964-396">Understand classes</span></span>   

<span data-ttu-id="ed964-397">通过类，你可以将样式集合分配给任意元素。</span><span class="sxs-lookup"><span data-stu-id="ed964-397">Classes let you assign collections of styles to arbitrary elements.</span></span>  <span data-ttu-id="ed964-398">例如，将 `class` 标记的属性设置 `<header>` 为对 `jumbotron` 它们应用以下样式：</span><span class="sxs-lookup"><span data-stu-id="ed964-398">For example, setting the `class` attribute of the `<header>` tags to `jumbotron` applied the following styles to them:</span></span>  

```css
.jumbotron {
  padding: 2rem 1rem;
  margin-bottom: 2rem;
  background-color: #e9ecef;
  border-radius: .3rem;
}
```  

<span data-ttu-id="ed964-399">类的一个优点是，它们允许你将样式应用到所需的任何元素。</span><span class="sxs-lookup"><span data-stu-id="ed964-399">One advantage of classes is that they let you apply styles to whatever elements you want.</span></span>  <span data-ttu-id="ed964-400">例如，假设你想要将*某些*元素的背景色设置 `<p>` 为紫色，而不是*所有*元素。</span><span class="sxs-lookup"><span data-stu-id="ed964-400">For example, suppose you want to set the background color of *some* `<p>` elements to purple, but not *all* of them.</span></span>  <span data-ttu-id="ed964-401">可以在类中定义样式：</span><span class="sxs-lookup"><span data-stu-id="ed964-401">You could define the style in a class:</span></span>  

```css
.custom-background {
  background-color: purple;
}
```  

<span data-ttu-id="ed964-402">然后将该类应用于 `<p>` 要样式的元素：</span><span class="sxs-lookup"><span data-stu-id="ed964-402">And then apply the class to only the `<p>` elements that you want to style:</span></span>  

```html
...
    ...
        ...
        <p>This won't be purple.</p>
        <p class="custom-background">This will be purple.</p>
        <p>This won't be purple.</p>
        <p class="custom-background">This will be purple.</p>
        ...
    ...
...
```  

### <span data-ttu-id="ed964-403">对齐元素</span><span class="sxs-lookup"><span data-stu-id="ed964-403">Align elements</span></span>   

<span data-ttu-id="ed964-404">"引导" 还提供用于对齐元素的类。</span><span class="sxs-lookup"><span data-stu-id="ed964-404">Bootstrap also provides classes for aligning elements.</span></span>  <span data-ttu-id="ed964-405">立即试用：</span><span class="sxs-lookup"><span data-stu-id="ed964-405">Try it now:</span></span>  

1.  <span data-ttu-id="ed964-406">返回 "编辑器" 选项卡，然后打开 `index.html` 。</span><span class="sxs-lookup"><span data-stu-id="ed964-406">Go back to the editor tab and open `index.html`.</span></span>  
1.  <span data-ttu-id="ed964-407">添加 `class="container-fluid"` 到您的 `<body>` 标签。</span><span class="sxs-lookup"><span data-stu-id="ed964-407">Add `class="container-fluid"` to your `<body>` tag.</span></span>  
    
    > ##### <span data-ttu-id="ed964-408">图42</span><span class="sxs-lookup"><span data-stu-id="ed964-408">Figure 42</span></span>  
    > <span data-ttu-id="ed964-409">添加 `container-fluid` 类</span><span class="sxs-lookup"><span data-stu-id="ed964-409">Adding the `container-fluid` class</span></span>  
    > ![添加容器流体类][ImageCssAlign1]  

1.  <span data-ttu-id="ed964-411">将您的 `<nav>` 和 `<main>` 元素包装在中 `<div class="row">` 。</span><span class="sxs-lookup"><span data-stu-id="ed964-411">Wrap your `<nav>` and `<main>` elements in `<div class="row">`.</span></span>  <span data-ttu-id="ed964-412">请确保放 `</div>` `</main>` 在 "" 之后，才能正确关闭新标记。</span><span class="sxs-lookup"><span data-stu-id="ed964-412">Make sure to put `</div>` after `</main>` in order to properly close the new tag.</span></span>  
    
    > ##### <span data-ttu-id="ed964-413">图43</span><span class="sxs-lookup"><span data-stu-id="ed964-413">Figure 43</span></span>  
    > <span data-ttu-id="ed964-414">添加行</span><span class="sxs-lookup"><span data-stu-id="ed964-414">Adding a row</span></span>  
    > ![添加行][ImageCssAlign2]  
    
1.  <span data-ttu-id="ed964-416">添加 `class="col-3"` 到您的 `<nav>` 标签和 `class="col-9"` `<main>` 标签。</span><span class="sxs-lookup"><span data-stu-id="ed964-416">Add `class="col-3"` to your `<nav>` tag and `class="col-9"` to your `<main>` tag.</span></span>  
    
    > ##### <span data-ttu-id="ed964-417">图44</span><span class="sxs-lookup"><span data-stu-id="ed964-417">Figure 44</span></span>  
    > <span data-ttu-id="ed964-418">添加 `col-3` 和 `col-9` 类</span><span class="sxs-lookup"><span data-stu-id="ed964-418">Adding the `col-3` and `col-9` classes</span></span>  
    > ![添加列3和 col-9 类][ImageCssAlign3]  
    
1.  <span data-ttu-id="ed964-420">在 "实时" 选项卡中查看所做的更改。</span><span class="sxs-lookup"><span data-stu-id="ed964-420">View your changes in the live tab.</span></span>  
    
    > ##### <span data-ttu-id="ed964-421">图45</span><span class="sxs-lookup"><span data-stu-id="ed964-421">Figure 45</span></span>  
    > <span data-ttu-id="ed964-422">导航内容现在位于主要内容的左侧</span><span class="sxs-lookup"><span data-stu-id="ed964-422">The nav content is now to the left of the main content</span></span>  
    > ![导航内容现在位于主要内容的左侧][ImageCssAlign4]  
    
## <span data-ttu-id="ed964-424">后续步骤</span><span class="sxs-lookup"><span data-stu-id="ed964-424">Next steps</span></span>   

<span data-ttu-id="ed964-425">恭喜你！</span><span class="sxs-lookup"><span data-stu-id="ed964-425">Congratulations!</span></span>  <span data-ttu-id="ed964-426">操作完成！</span><span class="sxs-lookup"><span data-stu-id="ed964-426">You're done!</span></span>  

*   <span data-ttu-id="ed964-427">在 web 开发中获取更好的最佳方式是构建更多网站。</span><span class="sxs-lookup"><span data-stu-id="ed964-427">The best way to get better at web development is to build more sites.</span></span>  <span data-ttu-id="ed964-428">不必担心会破坏内容。</span><span class="sxs-lookup"><span data-stu-id="ed964-428">Don't worry about breaking stuff.</span></span>  <span data-ttu-id="ed964-429">只要有兴趣，您就可以很方便地学习。</span><span class="sxs-lookup"><span data-stu-id="ed964-429">Just have fun and learn as much as you can along the way.</span></span>  
*   <span data-ttu-id="ed964-430">查看[CSS 简介][MDNCssFirstSteps]，了解有关设置网页样式的详细信息。</span><span class="sxs-lookup"><span data-stu-id="ed964-430">Check out [Introduction to CSS][MDNCssFirstSteps] to learn lots more about styling web pages.</span></span>  
*   <span data-ttu-id="ed964-431">[开始查看和更改 CSS][DevtoolsCssIndex]教程，了解如何使用 DevTools 体验页面的 css 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="ed964-431">Work through our [Get Started with Viewing and Changing CSS][DevtoolsCssIndex] tutorial to learn more about how you can use DevTools to experiment with a page's CSS.</span></span>  

<!--- image links --->  

[ImageNewStyleRuleIcon]: /microsoft-edge/devtools-guide-chromium/media/new-style-rule-icon.msft.png  

[ImageCssIntro1]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-intro1.msft.png "图1：网站的当前外观"  
[ImageCssIntro2]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-intro2.msft.png "图2：你的网站将在教程末尾显示的内容"  
[ImageCssSetup1]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-setup1.msft.png "图3： "编辑" 选项卡"  
[ImageCssSetup2]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-setup2.msft.png "图4： "项目选项" 菜单"  
[ImageCssSetup3]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-setup3.msft.png "图5： "实时" 选项卡"  
[ImageCssStyled]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-red_paragraph.msft.png "图6：已通过 CSS 设置了样式"  
[ImageCssInline1]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-inline1.msft.png "图7：索引 html"  
[ImageCssInline2]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-inline2.msft.png "图8： "主页" 和 "联系人" 链接背后的背景色现在为蓝色"  
[ImageCssInternal1]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-internal1.msft.png "图9：联系人页"  
[ImageCssInternal2]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-internal2.msft.png "图10：主页和联系人链接的字体已更改"  
[ImageCssMultiple1]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-multiple1.msft.png "图11：文本 "联系我们！" 现在的字体与 "家庭" 和 "联系人" 链接的字体相同"  
[ImageCssAdd1]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-add1.msft.png "图12：检查主页链接"  
[ImageCssAdd2]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-add2.msft.png "图13： "样式" 选项卡位于 DOM 树下方"  
[ImageCssAdd3]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-add3.msft.png "图14： "样式" 选项卡位于 DOM 树的右侧"  
[ImageCssAdd4]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-add4.msft.png "图15：添加新声明"
[ImageCssAdd5]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-add5.msft.png "图16：键入颜色"  
[ImageCssAdd6]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-add6.msft.png "图17：键入洋红色"  
[ImageCssEdit1]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-edit1.msft.png "图18：颜色选取器"  
[ImageCssEdit2]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-edit2.msft.png "图19：通过拾色器将字体颜色更改为紫色"  
[ImageCssRule1]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-rule1.msft.png "图20：添加新规则"  
[ImageCssRule2]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-rule2.msft.png "图21：将 with a:hover 替换为"  
[ImageCssRule3]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-rule3.msft.png "图22：键入背景色"  
[ImageCssRule4]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-rule4.msft.png "图23：键入绿色"  
[ImageCssRule5]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-rule5.msft.png "图24：将鼠标悬停在 "主页" 链接上以显示其绿色背景"  
[ImageCssExternal01]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-external1.msft.png "图25：重新加载页面后，在 DevTools 中所做的更改已丢失"  
[ImageCssExternal02]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-external2.msft.png "图26：联系 .html"  
[ImageCssExternal03]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-external3.msft.png "图27：已删除样式标记"  
[ImageCssExternal04]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-external4.msft.png "图28：已从导航元素中删除嵌入式样式"  
[ImageCssExternal05]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-external5.msft.png "图29： "新建文件" 对话框"  
[ImageCssExternal06]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-external6.msft.png "图30：键入样式 .css"  
[ImageCssExternal07]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-external7.msft.png "图31：将代码添加到样式 .css"  
[ImageCssExternal08]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-external8.msft.png "图32：链接到样式 .css"  
[ImageCssExternal09]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-external9.msft.png "图33：链接到 "style" 中的 "css""  
[ImageCssExternal10]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-external10.msft.png "图34：主页"  
[ImageCssExternal11]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-external11.msft.png "图35：联系人页面"  
[ImageCssFramework1]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-framework1.msft.png "图36：链接到 contact for .html 中的框架"  
[ImageCssFramework2]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-framework2.msft.png "图37：在 index for html 中链接到框架"  
[ImageCssFramework3]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-framework3.msft.png "图38：主页上的某些字体因框架而发生更改"  
[ImageCssJumbotron1]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-jumbotron1.msft.png "图39：在索引 html 中添加类"  
[ImageCssJumbotron2]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-jumbotron2.msft.png "图40：在 contact for .html 中添加类"  
[ImageCssJumbotron3]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-jumbotron3.msft.png "图41：标题现在周围有一个大灰框"  
[ImageCssAlign1]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-align1.msft.png "图42：添加容器流体类"  
[ImageCssAlign2]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-align2.msft.png "图43：添加行"  
[ImageCssAlign3]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-align3.msft.png "图44：添加列3和 col-9 类"  
[ImageCssAlign4]: /microsoft-edge/devtools-guide-chromium/media/beginners-css-align4.msft.png "图45：导航内容现在位于主内容的左侧"  

<!--- links  --->  

[DevToolsBeginnersHtml]: html.md "初学者的 DevTools： HTML 和 DOM 入门"  
[DevtoolsCssIndex]: ../css/index.md "查看和更改 CSS 入门"  

[MicrosoftEdgeInsider]: https://www.microsoftedgeinsider.com "Microsoft Edge 预览体验成员"  

[GlitchCookedAmphibianIndex]: https://glitch.com/edit/#!/cooked-amphibian?path=index.html "index-cooked-amphibian |故障"  

[MDNCssFirstSteps]: https://developer.mozilla.org/docs/Learn/CSS/Introduction_to_CSS "CSS 优先步骤 |MDN"  

> [!NOTE]
> <span data-ttu-id="ed964-482">此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="ed964-482">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="ed964-483">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/beginners/css)，由[Katherine 杰克逊][KatherineJackson]（技术作者暂存，Chrome DevTools \）创作。</span><span class="sxs-lookup"><span data-stu-id="ed964-483">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/beginners/css) and is authored by [Katherine Jackson][KatherineJackson] \(Technical Writer Intern, Chrome DevTools\).</span></span>  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
<span data-ttu-id="ed964-485">此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="ed964-485">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[KatherineJackson]: https://developers.google.com/web/resources/contributors/katjackson  
