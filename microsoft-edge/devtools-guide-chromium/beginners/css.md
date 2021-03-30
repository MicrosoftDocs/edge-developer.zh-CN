---
description: CSS 入门
title: 适用于初学者的 DevTools：CSS 入门
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， Web 开发， f12 工具， devtools
ms.openlocfilehash: 6a7135e144123917535e7c43e6a3cd608ec0c8a7
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439435"
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

# <a name="devtools-for-beginners-get-started-with-css"></a><span data-ttu-id="b9794-104">适用于初学者的 DevTools：CSS 入门</span><span class="sxs-lookup"><span data-stu-id="b9794-104">DevTools for beginners: Get started with CSS</span></span>  

<span data-ttu-id="b9794-105">本教程介绍如何使用 CSS 设置网页样式。</span><span class="sxs-lookup"><span data-stu-id="b9794-105">In this tutorial, you learn how to use CSS to style a web page.</span></span>  <span data-ttu-id="b9794-106">此外，还了解如何使用 Microsoft Edge DevTools 试验 CSS 更改。</span><span class="sxs-lookup"><span data-stu-id="b9794-106">You also learn how to use Microsoft Edge DevTools to experiment with CSS changes.</span></span>  

<span data-ttu-id="b9794-107">以下文章是一系列教程的第二个教程，这些教程将指导你 Web 开发和 Microsoft Edge DevTools 的基础知识。</span><span class="sxs-lookup"><span data-stu-id="b9794-107">The following article is the second tutorial in a series of tutorials that teaches you the basics of web development and Microsoft Edge DevTools.</span></span>  <span data-ttu-id="b9794-108">通过实际构建自己的网站，可以获得实践体验。</span><span class="sxs-lookup"><span data-stu-id="b9794-108">You gain hands-on experience by actually building your own website.</span></span>  <span data-ttu-id="b9794-109">在遵循第二个教程之前，不需要完成第一个教程。</span><span class="sxs-lookup"><span data-stu-id="b9794-109">You do not have to complete the first tutorial before following the second.</span></span>  <span data-ttu-id="b9794-110">[设置代码将](#set-up-your-code) 演示如何进行设置。</span><span class="sxs-lookup"><span data-stu-id="b9794-110">[Set up your code](#set-up-your-code) shows you how to get set up.</span></span>  

> [!NOTE]
> <span data-ttu-id="b9794-111">本教程专为绝对初学者设计，专注于 Web 开发 **的** 基础知识和使用 DevTools 进行 CSS 测试的基础知识。</span><span class="sxs-lookup"><span data-stu-id="b9794-111">This tutorial is designed for absolute beginners and focuses on both the **fundamentals of web development** and the basics of using DevTools to experiment with CSS.</span></span>  <span data-ttu-id="b9794-112">如果你需要一个仅侧重于 DevTools 的教程，请导航到查看和 [更改 CSS 入门][DevtoolsCssIndex]。</span><span class="sxs-lookup"><span data-stu-id="b9794-112">If you want a tutorial that only focuses on DevTools, navigate to [Get Started with Viewing and Changing CSS][DevtoolsCssIndex].</span></span>  

<span data-ttu-id="b9794-113">在本教程的开头，您的网站应如下图所示。</span><span class="sxs-lookup"><span data-stu-id="b9794-113">At the beginning of the tutorial, your site should look like the following figure.</span></span>  

:::image type="complex" source="../media/beginners-css-intro1.msft.png" alt-text="您的网站当前外观" lightbox="../media/beginners-css-intro1.msft.png":::
   <span data-ttu-id="b9794-115">您的网站当前外观</span><span class="sxs-lookup"><span data-stu-id="b9794-115">What your site currently looks like</span></span>  
:::image-end:::  

<span data-ttu-id="b9794-116">完成本教程后，网站应如下所示。</span><span class="sxs-lookup"><span data-stu-id="b9794-116">After you complete the tutorial, you site should look like the following figure.</span></span>  

:::image type="complex" source="../media/beginners-css-intro2.msft.png" alt-text="在本教程结束时，你的网站应该是什么样" lightbox="../media/beginners-css-intro2.msft.png":::
   <span data-ttu-id="b9794-118">在本教程结束时，你的网站应该是什么样</span><span class="sxs-lookup"><span data-stu-id="b9794-118">What your site should look like at the end of the tutorial</span></span>  
:::image-end:::  

## <a name="goals"></a><span data-ttu-id="b9794-119">目标</span><span class="sxs-lookup"><span data-stu-id="b9794-119">Goals</span></span>  

<span data-ttu-id="b9794-120">按照本教程可更好地了解以下概念和任务。</span><span class="sxs-lookup"><span data-stu-id="b9794-120">Follow this tutorial to better understand the following concepts and tasks.</span></span>  

*   <span data-ttu-id="b9794-121">如何使用 CSS 设置网页样式。</span><span class="sxs-lookup"><span data-stu-id="b9794-121">How to use CSS to style a web page.</span></span>  
*   <span data-ttu-id="b9794-122">如何使用 Microsoft Edge DevTools 对 CSS 进行试验。</span><span class="sxs-lookup"><span data-stu-id="b9794-122">How to use Microsoft Edge DevTools to experiment with CSS.</span></span>  
*   <span data-ttu-id="b9794-123">CSS 和 CSS 框架的区别。</span><span class="sxs-lookup"><span data-stu-id="b9794-123">The difference between CSS and CSS frameworks.</span></span>  

<span data-ttu-id="b9794-124">你正在构建一个真实网站。</span><span class="sxs-lookup"><span data-stu-id="b9794-124">You are building a real website.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="b9794-125">必备条件</span><span class="sxs-lookup"><span data-stu-id="b9794-125">Prerequisites</span></span>  

<span data-ttu-id="b9794-126">在尝试本教程之前，请完成以下先决条件。</span><span class="sxs-lookup"><span data-stu-id="b9794-126">Before attempting this tutorial, complete the following prerequisites.</span></span>  

*   <span data-ttu-id="b9794-127">完成 [HTML 和 DOM][DevtoolsBeginnersHtml] 入门或确保你了解 HTML 和 DOM，与本教程中介绍的内容类似。</span><span class="sxs-lookup"><span data-stu-id="b9794-127">Complete [Get Started with HTML and the DOM][DevtoolsBeginnersHtml] or make sure that you have an understanding of HTML and the DOM similar to what is taught in that tutorial.</span></span>  
*   <span data-ttu-id="b9794-128">下载 [Microsoft Edge][MicrosoftEdgeInsider] Web 浏览器。</span><span class="sxs-lookup"><span data-stu-id="b9794-128">Download the [Microsoft Edge][MicrosoftEdgeInsider] web browser.</span></span>  <span data-ttu-id="b9794-129">以下教程使用一组内置于 Microsoft Edge 中的 Web 开发工具（称为 Microsoft Edge DevTools）。</span><span class="sxs-lookup"><span data-stu-id="b9794-129">The following tutorial uses a set of web development tools, called the Microsoft Edge DevTools, that are built into Microsoft Edge.</span></span>  

## <a name="set-up-your-code"></a><span data-ttu-id="b9794-130">设置代码</span><span class="sxs-lookup"><span data-stu-id="b9794-130">Set up your code</span></span>  

<span data-ttu-id="b9794-131">若要创建网站，必须先完成以下操作以设置代码。</span><span class="sxs-lookup"><span data-stu-id="b9794-131">To create your site, you must first complete the following actions to set up your code.</span></span>  

> [!NOTE]
> <span data-ttu-id="b9794-132">如果已完成系列的第一个教程，请跳到下一部分。</span><span class="sxs-lookup"><span data-stu-id="b9794-132">If you have already completed the first tutorial in the series, skip to the next section.</span></span>  <span data-ttu-id="b9794-133">继续使用上一教程 HTML 和 [DOM 入门中的代码][DevtoolsBeginnersHtml]。</span><span class="sxs-lookup"><span data-stu-id="b9794-133">Continue using your code from the last tutorial, [Get Started with HTML and the DOM][DevtoolsBeginnersHtml].</span></span>  

1.  <span data-ttu-id="b9794-134">打开 [源代码][GlitchCookedAmphibianIndex]。</span><span class="sxs-lookup"><span data-stu-id="b9794-134">Open the [source code][GlitchCookedAmphibianIndex].</span></span>  <span data-ttu-id="b9794-135">浏览器的"焦点内"选项卡被引用为 **编辑选项卡**。</span><span class="sxs-lookup"><span data-stu-id="b9794-135">The in-focus tab of your browser is referenced as the **editing tab**.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-setup1.msft.png" alt-text="编辑选项卡" lightbox="../media/beginners-css-setup1.msft.png":::
       <span data-ttu-id="b9794-137">" **编辑"** 选项卡</span><span class="sxs-lookup"><span data-stu-id="b9794-137">The **editing** tab</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="b9794-138">选择 **"cooked-amphibian"。**</span><span class="sxs-lookup"><span data-stu-id="b9794-138">Choose **cooked-amphibian**.</span></span>  <span data-ttu-id="b9794-139">弹出一个菜单。</span><span class="sxs-lookup"><span data-stu-id="b9794-139">A menu pops up.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-setup2.msft.png" alt-text="项目选项菜单" lightbox="../media/beginners-css-setup2.msft.png":::
       <span data-ttu-id="b9794-141">项目选项菜单</span><span class="sxs-lookup"><span data-stu-id="b9794-141">The Project Options menu</span></span>  
    :::image-end:::  

1.  <span data-ttu-id="b9794-142">选择 **"重新混合项目"。**</span><span class="sxs-lookup"><span data-stu-id="b9794-142">Choose **Remix Project**.</span></span>  <span data-ttu-id="b9794-143">Glitch 将创建一个您可以编辑的项目副本。</span><span class="sxs-lookup"><span data-stu-id="b9794-143">Glitch creates a copy of the project that you are able to edit.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="b9794-144">Glitch 会为新项目生成随机名称。</span><span class="sxs-lookup"><span data-stu-id="b9794-144">Glitch generates a random name for the new project.</span></span>  
    
1.  <span data-ttu-id="b9794-145">选择 **"显示**"，然后选择 **"在新建窗口中"。**</span><span class="sxs-lookup"><span data-stu-id="b9794-145">Choose **Show** and choose **In a New Window**.</span></span>  <span data-ttu-id="b9794-146">打开另一个选项卡，其中显示网站实时视图。</span><span class="sxs-lookup"><span data-stu-id="b9794-146">Another tab opens with a live view of your site.</span></span>  <span data-ttu-id="b9794-147">浏览器的"焦点内"选项卡被引用为实时 **选项卡**。</span><span class="sxs-lookup"><span data-stu-id="b9794-147">The in-focus tab of your browser is referenced as the **live tab**.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-setup3.msft.png" alt-text="实时选项卡" lightbox="../media/beginners-css-setup3.msft.png":::
       <span data-ttu-id="b9794-149">实时 **选项卡**</span><span class="sxs-lookup"><span data-stu-id="b9794-149">The **live tab**</span></span>  
    :::image-end:::  

## <a name="understand-css"></a><span data-ttu-id="b9794-150">了解 CSS</span><span class="sxs-lookup"><span data-stu-id="b9794-150">Understand CSS</span></span>  

<span data-ttu-id="b9794-151">**CSS** 是决定网页布局和样式的计算机语言。</span><span class="sxs-lookup"><span data-stu-id="b9794-151">**CSS** is a computer language that determines the layout and styling of web pages.</span></span>  <span data-ttu-id="b9794-152">下图是带边框的段落。</span><span class="sxs-lookup"><span data-stu-id="b9794-152">The following figure is a paragraph with a border.</span></span>  

:::image type="complex" source="../media/beginners-css-red_paragraph.msft.png" alt-text="文本已使用 CSS 设置样式" lightbox="../media/beginners-css-red_paragraph.msft.png":::
   <span data-ttu-id="b9794-154">文本已使用 CSS 设置样式</span><span class="sxs-lookup"><span data-stu-id="b9794-154">The text has been styled with CSS</span></span>  
:::image-end:::  

<span data-ttu-id="b9794-155">以下代码段是用于创建上图中段落的 HTML 和 CSS 代码。</span><span class="sxs-lookup"><span data-stu-id="b9794-155">The following code snippet is the HTML and CSS code used to create the paragraph in the previous figure.</span></span>  

```html
<p style="border: 1px dashed red; padding: 5px;">
    This has been styled with CSS.
</p>
```  

`style="border: 1px dashed red; padding: 5px;"` <span data-ttu-id="b9794-156">可能看起来是全新的。</span><span class="sxs-lookup"><span data-stu-id="b9794-156">probably looks new to you.</span></span>  <span data-ttu-id="b9794-157">其余部分看起来应该很熟悉。</span><span class="sxs-lookup"><span data-stu-id="b9794-157">The rest should look familiar.</span></span>  <span data-ttu-id="b9794-158">如果没有，在尝试以下部分之前，请完成 HTML 和 [DOM][DevtoolsBeginnersHtml] 入门。</span><span class="sxs-lookup"><span data-stu-id="b9794-158">If not, complete [Get Started with HTML and the DOM][DevtoolsBeginnersHtml] before attempting the following sections.</span></span>  

## <a name="add-inline-styles"></a><span data-ttu-id="b9794-159">添加内联样式</span><span class="sxs-lookup"><span data-stu-id="b9794-159">Add inline styles</span></span>  

<span data-ttu-id="b9794-160">完成以下操作以使用 **内联样式** 将样式应用到单个元素。</span><span class="sxs-lookup"><span data-stu-id="b9794-160">Complete the following actions to use **inline styles** to apply styles to a single element.</span></span>  

1.  <span data-ttu-id="b9794-161">返回到编辑选项卡并打开`index.html`。</span><span class="sxs-lookup"><span data-stu-id="b9794-161">Go back to the editing tab and open `index.html`.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-inline1.msft.png" alt-text="index.html" lightbox="../media/beginners-css-inline1.msft.png":::
       <span data-ttu-id="b9794-163">在 `index.html` 编辑选项卡中打开</span><span class="sxs-lookup"><span data-stu-id="b9794-163">Open `index.html` in the editing tab</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="b9794-164">添加到 `style="background-color: aliceblue;"` 你的 `<nav>`。</span><span class="sxs-lookup"><span data-stu-id="b9794-164">Add `style="background-color: aliceblue;"` to your `<nav>`.</span></span>  <span data-ttu-id="b9794-165">在下面的代码块中，需要更改的第四行代码。</span><span class="sxs-lookup"><span data-stu-id="b9794-165">In the code block below, the fourth line of code is the one you need to change.</span></span>  <span data-ttu-id="b9794-166">其余代码就在这里，因此可以确保将新代码放在正确的位置。</span><span class="sxs-lookup"><span data-stu-id="b9794-166">The rest is just there, so you are able to ensure that you are putting the new code in the right place.</span></span>  
    
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
    
1.  <span data-ttu-id="b9794-167">若要显示更改，请导航到活动 **选项卡**。 分区的背景 `<nav>` 现在为蓝色。</span><span class="sxs-lookup"><span data-stu-id="b9794-167">To display the changes, navigate to the **live tab**.  The background of the `<nav>` section is now blue.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-inline2.msft.png" alt-text="主页和联系人链接背后的背景色现在为蓝色" lightbox="../media/beginners-css-inline2.msft.png":::
       <span data-ttu-id="b9794-169">现在，**主页**和**联系人**链接后面的背景颜色为蓝色</span><span class="sxs-lookup"><span data-stu-id="b9794-169">The background color behind the **Home** and **Contact** links is now blue</span></span>  
    :::image-end:::  
    
## <a name="re-use-styles-on-a-single-page-with-internal-stylesheets"></a><span data-ttu-id="b9794-170">在包含内部样式表的单个页面上重新使用样式</span><span class="sxs-lookup"><span data-stu-id="b9794-170">Re-use styles on a single page with internal stylesheets</span></span>  

<span data-ttu-id="b9794-171">在之前的代码段中，内联样式将样式应用于单个 `<p>` 标记。</span><span class="sxs-lookup"><span data-stu-id="b9794-171">In a previous code snippet, an inline style applied a style to a single `<p>` tag.</span></span>  

```html
<p style="border: 1px dashed red; padding: 5px;">
    This has been styled with CSS.
</p>
```  

<span data-ttu-id="b9794-172">如果您希望网页上的所有元素都以相同的方式设置样式 `<p>` ，应该如何？</span><span class="sxs-lookup"><span data-stu-id="b9794-172">What if you wanted all of the `<p>` elements on your webpage to be styled the same way?</span></span>  <span data-ttu-id="b9794-173">您必须将代码复制并粘贴到网站上 `<p>` 每个标记中。</span><span class="sxs-lookup"><span data-stu-id="b9794-173">You have to copy and paste the code into every single `<p>` tag on your site.</span></span>  <span data-ttu-id="b9794-174">这是一项大量的时间和精力。</span><span class="sxs-lookup"><span data-stu-id="b9794-174">That is a lot of time and effort.</span></span>  <span data-ttu-id="b9794-175">如果需要进行编辑，必须再次更改每个标记。</span><span class="sxs-lookup"><span data-stu-id="b9794-175">And, if you needed to make an edit, you have to change every tag again.</span></span>  <span data-ttu-id="b9794-176">完成以下操作以使用 **Internal 样式表** 编写 CSS 一次，以便它适用于多个元素。</span><span class="sxs-lookup"><span data-stu-id="b9794-176">Complete the following actions to use an **Internal stylesheet** to write your CSS once so that it applies to multiple elements.</span></span>  

1.  <span data-ttu-id="b9794-177">在活动选项卡中，选择 **"联系人"** 以导航到联系人页面。</span><span class="sxs-lookup"><span data-stu-id="b9794-177">In the live tab, choose **Contact** to navigate to the contact page.</span></span>  <span data-ttu-id="b9794-178">请注意 Home**和**Contact 的字体。</span><span class="sxs-lookup"><span data-stu-id="b9794-178">Notice the font of **Home** and **Contact**.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-internal1.msft.png" alt-text="联系人页" lightbox="../media/beginners-css-internal1.msft.png":::
       <span data-ttu-id="b9794-180">联系人页</span><span class="sxs-lookup"><span data-stu-id="b9794-180">The Contact page</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="b9794-181">在编辑器 **选项卡中，** 打开 `contact.html`。</span><span class="sxs-lookup"><span data-stu-id="b9794-181">In the **editor tab**, open `contact.html`.</span></span>  
1.  <span data-ttu-id="b9794-182">将以下代码添加到 `contact.html`。</span><span class="sxs-lookup"><span data-stu-id="b9794-182">Add the following code to `contact.html`.</span></span>  <span data-ttu-id="b9794-183">请记住，需要添加以 `<style>` 开始到 `</style>` 结尾的行。</span><span class="sxs-lookup"><span data-stu-id="b9794-183">Remember, the lines starting with `<style>` and ending with `</style>` are what you need to add.</span></span>  <span data-ttu-id="b9794-184">其他代码就在这里，以便你了解新代码的放入位置。</span><span class="sxs-lookup"><span data-stu-id="b9794-184">The other code is just there so you know where to put the new code.</span></span>  
    
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
    
1.  <span data-ttu-id="b9794-185">返回到实时 **选项卡**。</span><span class="sxs-lookup"><span data-stu-id="b9794-185">Go back to the **live tab**.</span></span>  
1.  <span data-ttu-id="b9794-186">选择 **联系人** 以返回联系人页面。</span><span class="sxs-lookup"><span data-stu-id="b9794-186">Choose **Contact** to go back to the contact page.</span></span>  <span data-ttu-id="b9794-187">**Home** 和 **"联系人** 字体已更改。</span><span class="sxs-lookup"><span data-stu-id="b9794-187">The font of **Home** and **Contact** has changed.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-internal2.msft.png" alt-text="主页和联系人链接的字体已更改" lightbox="../media/beginners-css-internal2.msft.png":::
       <span data-ttu-id="b9794-189">**家庭**和**联系人**链接的字体已更改</span><span class="sxs-lookup"><span data-stu-id="b9794-189">The font of the **Home** and **Contact** links has changed</span></span>  
    :::image-end:::  
    
### <a name="understand-internal-stylesheets"></a><span data-ttu-id="b9794-190">了解内部样式表</span><span class="sxs-lookup"><span data-stu-id="b9794-190">Understand internal stylesheets</span></span>  

<span data-ttu-id="b9794-191">内部样式表使用选择器应用 **样式**。</span><span class="sxs-lookup"><span data-stu-id="b9794-191">Internal stylesheets apply styles using **selectors**.</span></span>  <span data-ttu-id="b9794-192">选择器是可应用于一个或多个 HTML 元素的模式。</span><span class="sxs-lookup"><span data-stu-id="b9794-192">Selectors are patterns that may apply to one or more HTML elements.</span></span>  <span data-ttu-id="b9794-193">前面的代码段添加了以下样式。</span><span class="sxs-lookup"><span data-stu-id="b9794-193">The previous code snippet added the following style.</span></span>  

```html
<style>
    li a {
      font-family: 'Courier New', Courier, Serif;
    }
</style>
```  

`li a` <span data-ttu-id="b9794-194">是转换为"任何 `<li>` 包含元素的元素 `<a>` "的选择器。</span><span class="sxs-lookup"><span data-stu-id="b9794-194">is a selector that translates to "any `<li>` element that contains an `<a>` element".</span></span>  <span data-ttu-id="b9794-195">浏览器会更改 **“主页”** 和 **“联系人”** 链接的字体，因为每个标签组都与模式匹配。</span><span class="sxs-lookup"><span data-stu-id="b9794-195">The browser changes the font of the **Home** and **Contact** links because each of the tag groups match the pattern.</span></span>  

```html
<li><a href="/">Home</a></li>
<li><a href="/contact.html">Contact</a></li>
```  

`font-family: 'Courier New', Courier, serif` <span data-ttu-id="b9794-196">是**声明**。</span><span class="sxs-lookup"><span data-stu-id="b9794-196">is a **declaration**.</span></span>  <span data-ttu-id="b9794-197">声明由以下两部分组成。</span><span class="sxs-lookup"><span data-stu-id="b9794-197">A declaration is made of following two parts.</span></span>  

:::row:::
   :::column span="1":::
      **<span data-ttu-id="b9794-198">属性</span><span class="sxs-lookup"><span data-stu-id="b9794-198">property</span></span>**  
   :::column-end:::
   :::column span="1":::
      `font-family`  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="b9794-199">该属性介绍一种可更改元素样式的常规方式。</span><span class="sxs-lookup"><span data-stu-id="b9794-199">The property describes a general way that you are able to change the style of the element.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="b9794-200">value</span><span class="sxs-lookup"><span data-stu-id="b9794-200">value</span></span>**  
   :::column-end:::
   :::column span="1":::
      `'Courier New', Courier, serif`  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="b9794-201">该值准确描述了元素的样式应该如何更改。</span><span class="sxs-lookup"><span data-stu-id="b9794-201">The value describes exactly how the style of the element should change.</span></span>  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="b9794-202">例如， `font-family: 'Courier New', Courier, serif` 为浏览器提供以下指令："将匹配模式的元素的字体设置为 `li a` `'Courier New'`。</span><span class="sxs-lookup"><span data-stu-id="b9794-202">For example, `font-family: 'Courier New', Courier, serif` gives the browser the following instruction:  "Set the font of elements that match the pattern `li a` to `'Courier New'`.</span></span>  <span data-ttu-id="b9794-203">如果该字体不可用，请使用 `Courier`。</span><span class="sxs-lookup"><span data-stu-id="b9794-203">If that font is not available, use `Courier`.</span></span>  <span data-ttu-id="b9794-204">如果不可用，请使用 `serif`。</span><span class="sxs-lookup"><span data-stu-id="b9794-204">If that is not available, use `serif`."</span></span>  

### <a name="add-multiple-selectors-to-a-ruleset"></a><span data-ttu-id="b9794-205">向规则集添加多个选择器</span><span class="sxs-lookup"><span data-stu-id="b9794-205">Add multiple selectors to a ruleset</span></span>  

<span data-ttu-id="b9794-206">类似以下代码段的 CSS 代码块称为 **规则集**。</span><span class="sxs-lookup"><span data-stu-id="b9794-206">A block of CSS code like the following code snippet is called a **ruleset**.</span></span>  

```css
li a {
  font-family: 'Courier New', Courier, monospace;
}
```  

<span data-ttu-id="b9794-207">完成以下操作以使用逗号向规则集添加多个选择器。</span><span class="sxs-lookup"><span data-stu-id="b9794-207">Complete the following actions to use commas to add multiple selectors to a ruleset.</span></span>  

1.  <span data-ttu-id="b9794-208">在编辑器 **选项卡中，** 打开 `contact.html`。</span><span class="sxs-lookup"><span data-stu-id="b9794-208">In the **editor tab**, open `contact.html`.</span></span>  
1.  <span data-ttu-id="b9794-209">键入 `li a`类型`, h1` 后。</span><span class="sxs-lookup"><span data-stu-id="b9794-209">After `li a` type `, h1`.</span></span>  
    
    ```html
    <style>
        li a, h1 {
          font-family: 'Courier New', Courier, Serif;
        }
    </style>
    ```  
    
    <span data-ttu-id="b9794-210">前面的代码段指示浏览器设置元素样式的方式与设置与模式 `<h1>` 匹配的元素的样式相同 `li a`。</span><span class="sxs-lookup"><span data-stu-id="b9794-210">The previous code snippet tells the browser to style `<h1>` elements the same way that it styles elements that match the pattern `li a`.</span></span>  
    
1.  <span data-ttu-id="b9794-211">导航到实时 **选项卡**。</span><span class="sxs-lookup"><span data-stu-id="b9794-211">Navigate to the **live tab**.</span></span>  
1.  <span data-ttu-id="b9794-212">选择 **"联系人** "链接返回到联系人页面。</span><span class="sxs-lookup"><span data-stu-id="b9794-212">Choose the **Contact** link to go back to the contact page.</span></span>  <span data-ttu-id="b9794-213">现在， **联系我！**</span><span class="sxs-lookup"><span data-stu-id="b9794-213">Now, **Contact Me!**</span></span> <span data-ttu-id="b9794-214">具有与导航链接相同的字体。</span><span class="sxs-lookup"><span data-stu-id="b9794-214">has the same font as the navigation links.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-multiple1.msft.png" alt-text="文本联系我！  现在字体与主页和联系人链接相同" lightbox="../media/beginners-css-multiple1.msft.png":::
       <span data-ttu-id="b9794-217">文本" **联系我"！**</span><span class="sxs-lookup"><span data-stu-id="b9794-217">The text **Contact Me!**</span></span> <span data-ttu-id="b9794-218">现在字体与 **"主页"** 和 **"联系人"** 链接相同</span><span class="sxs-lookup"><span data-stu-id="b9794-218">now has the same font as the **Home** and **Contact** links</span></span>  
    :::image-end:::  
    
## <a name="experiment-with-devtools"></a><span data-ttu-id="b9794-219">使用 DevTools 进行试验</span><span class="sxs-lookup"><span data-stu-id="b9794-219">Experiment with DevTools</span></span>  

<span data-ttu-id="b9794-220">当你继续成为 Web 开发方面的专家时，你可能会发现 CSS 很复杂。</span><span class="sxs-lookup"><span data-stu-id="b9794-220">As you continue your journey to become an expert in web development, you may find that CSS is tricky.</span></span>  <span data-ttu-id="b9794-221">您可以编写一些 CSS，并期望它以一种方式显示，但浏览器会进行完全不同的操作。</span><span class="sxs-lookup"><span data-stu-id="b9794-221">You may write some CSS and expect it to display one way, but the browser does something completely different.</span></span>  <span data-ttu-id="b9794-222">通过 Microsoft Edge DevTools，可以轻松试验更改并立即显示更改对页面的影响。</span><span class="sxs-lookup"><span data-stu-id="b9794-222">Microsoft Edge DevTools makes it easy to experiment with changes and immediately display how the changes affect the page.</span></span>  

### <a name="add-a-declaration-to-an-existing-rulest-in-devtools"></a><span data-ttu-id="b9794-223">将声明添加到 DevTools 中的现有规则</span><span class="sxs-lookup"><span data-stu-id="b9794-223">Add a declaration to an existing rulest in DevTools</span></span>  

<span data-ttu-id="b9794-224">完成以下操作以对现有元素的样式进行访问，向现有规则集添加声明。</span><span class="sxs-lookup"><span data-stu-id="b9794-224">Complete the following actions to iterate on the style of an existing element, add a declaration to an existing ruleset.</span></span>  

1.  <span data-ttu-id="b9794-225">将鼠标悬停在**主页链接**上，打开上下文菜单 \(右键单击\) ，然后选择**检查**。</span><span class="sxs-lookup"><span data-stu-id="b9794-225">Hover on the **Home** link, open the contextual menu \(right-click\), and choose **Inspect**.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-add1.msft.png" alt-text="检查主页链接" lightbox="../media/beginners-css-add1.msft.png":::
       <span data-ttu-id="b9794-227">检查主页链接</span><span class="sxs-lookup"><span data-stu-id="b9794-227">Inspect the Home link</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="b9794-228">DevTools 将在页面旁边打开。</span><span class="sxs-lookup"><span data-stu-id="b9794-228">DevTools opens up alongside your page.</span></span>  <span data-ttu-id="b9794-229">代表"主页"链接的代码在 DOM 树中突出显示 `<a href="/">Home</a>` 为蓝色。</span><span class="sxs-lookup"><span data-stu-id="b9794-229">The code that represents the Home link, `<a href="/">Home</a>` is highlighted blue in the DOM Tree.</span></span>  <span data-ttu-id="b9794-230">[HTML和DOM入门][DevtoolsBeginnersHtml]应该熟悉代码片段和预览。</span><span class="sxs-lookup"><span data-stu-id="b9794-230">The code snippet and preview should be familiar from [Get Started with HTML and the DOM][DevtoolsBeginnersHtml].</span></span>  
    
    :::row:::
       :::column span="":::
          <span data-ttu-id="b9794-231">在下图中，`font-family: 'Courier New', Courier, serif`您先前添加的声明`contact.html`显示在DOM树下方的 **“样式”** 选项卡中。</span><span class="sxs-lookup"><span data-stu-id="b9794-231">In the following figure, the `font-family: 'Courier New', Courier, serif` declaration that you previously added to `contact.html` is displayed in the **Styles** tab below the DOM Tree.</span></span>  
          
          :::image type="complex" source="../media/beginners-css-add2.msft.png" alt-text="样式选项卡位于 DOM 树下方" lightbox="../media/beginners-css-add2.msft.png":::
             <span data-ttu-id="b9794-233">" **样式"** 选项卡位于 DOM 树下方</span><span class="sxs-lookup"><span data-stu-id="b9794-233">The **Styles** tab is below the DOM Tree</span></span>  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          <span data-ttu-id="b9794-234">如果 DevTools 窗口很宽，则样式选项卡位于 DOM 树的右侧。</span><span class="sxs-lookup"><span data-stu-id="b9794-234">If your DevTools window is wide, the Styles tab is to the right of the DOM Tree.</span></span>  
          
          :::image type="complex" source="../media/beginners-css-add3.msft.png" alt-text="样式选项卡位于 DOM 树的右侧" lightbox="../media/beginners-css-add3.msft.png":::
             <span data-ttu-id="b9794-236">" **样式** "选项卡位于 DOM 树的右侧</span><span class="sxs-lookup"><span data-stu-id="b9794-236">The **Styles** tab is to the right of the DOM Tree</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
1.  <span data-ttu-id="b9794-237">选择下面的空行 `font-family: 'Courier New', Courier, Serif` 添加新声明。</span><span class="sxs-lookup"><span data-stu-id="b9794-237">Choose the empty line below `font-family: 'Courier New', Courier, Serif` to add a new declaration.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-add4.msft.png" alt-text="添加新声明" lightbox="../media/beginners-css-add4.msft.png":::
       <span data-ttu-id="b9794-239">添加新声明</span><span class="sxs-lookup"><span data-stu-id="b9794-239">Add a new declaration</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="b9794-240">键入 `color` 并选择 `Enter`。</span><span class="sxs-lookup"><span data-stu-id="b9794-240">Type `color` and select `Enter`.</span></span>  <span data-ttu-id="b9794-241">键入时，自动完成 UI 会推荐选项。</span><span class="sxs-lookup"><span data-stu-id="b9794-241">The autocomplete UI suggests options as you type.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-add5.msft.png" alt-text="类型颜色" lightbox="../media/beginners-css-add5.msft.png":::
       <span data-ttu-id="b9794-243">类型</span><span class="sxs-lookup"><span data-stu-id="b9794-243">Type</span></span> `color`  
    :::image-end:::  
    
1.  <span data-ttu-id="b9794-244">键入 `magenta` 并选择 `Enter`。</span><span class="sxs-lookup"><span data-stu-id="b9794-244">Type `magenta` and select `Enter`.</span></span>  <span data-ttu-id="b9794-245">联系人页面上的所有文本现在都为洋红色。</span><span class="sxs-lookup"><span data-stu-id="b9794-245">All of the text on the contact page is now magenta.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-add6.msft.png" alt-text="类型洋红色" lightbox="../media/beginners-css-add6.msft.png":::
       <span data-ttu-id="b9794-247">类型</span><span class="sxs-lookup"><span data-stu-id="b9794-247">Type</span></span> `magenta`  
    :::image-end:::  
    
### <a name="edit-a-declaration-in-devtools"></a><span data-ttu-id="b9794-248">在 DevTools 中编辑声明</span><span class="sxs-lookup"><span data-stu-id="b9794-248">Edit a declaration in DevTools</span></span>  

<span data-ttu-id="b9794-249">完成以下操作以编辑 DevTools 中的现有声明。</span><span class="sxs-lookup"><span data-stu-id="b9794-249">Complete the following actions to edit existing declarations in DevTools.</span></span>  

1.  <span data-ttu-id="b9794-250">选择 旁边的洋红色正方形 `magenta`。</span><span class="sxs-lookup"><span data-stu-id="b9794-250">Choose the magenta square next to `magenta`.</span></span>  <span data-ttu-id="b9794-251">将弹出一个颜色选取器。</span><span class="sxs-lookup"><span data-stu-id="b9794-251">A color picker pops up.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-edit1.msft.png" alt-text="颜色选取器" lightbox="../media/beginners-css-edit1.msft.png":::
       <span data-ttu-id="b9794-253">颜色选取器</span><span class="sxs-lookup"><span data-stu-id="b9794-253">The Color Picker</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="b9794-254">使用颜色选取器将字体文本更改为您喜欢的颜色。</span><span class="sxs-lookup"><span data-stu-id="b9794-254">Use the color picker to change the font text to a color that you like.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-edit2.msft.png" alt-text="使用颜色选取器将字体颜色更改为紫色" lightbox="../media/beginners-css-edit2.msft.png":::
       <span data-ttu-id="b9794-256">使用颜色选取器将字体颜色更改为紫色</span><span class="sxs-lookup"><span data-stu-id="b9794-256">Change the font color to purple with the Color Picker</span></span>  
    :::image-end:::  
    
### <a name="add-a-new-ruleset-in-devtools"></a><span data-ttu-id="b9794-257">在 DevTools 中添加新规则集</span><span class="sxs-lookup"><span data-stu-id="b9794-257">Add a new ruleset in DevTools</span></span>  

<span data-ttu-id="b9794-258">完成以下操作以在 DevTools 中添加新的规则集。</span><span class="sxs-lookup"><span data-stu-id="b9794-258">Complete the following actions to add new rulesets in DevTools.</span></span>  

1.  <span data-ttu-id="b9794-259">Choose **New Style Rule** \(New Style Rule ![ ](../media/new-style-rule-icon.msft.png) \) which is next to **.cls**.</span><span class="sxs-lookup"><span data-stu-id="b9794-259">Choose **New Style Rule** \(![New Style Rule](../media/new-style-rule-icon.msft.png)\) which is next to **.cls**.</span></span>  <span data-ttu-id="b9794-260">空的规则集将显示为 `a` 选择器。</span><span class="sxs-lookup"><span data-stu-id="b9794-260">An empty ruleset appears with `a` as the selector.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-rule1.msft.png" alt-text="添加新规则" lightbox="../media/beginners-css-rule1.msft.png":::
       <span data-ttu-id="b9794-262">添加新规则</span><span class="sxs-lookup"><span data-stu-id="b9794-262">Add a new rule</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="b9794-263">用 `a:hover` 取代 `a`。</span><span class="sxs-lookup"><span data-stu-id="b9794-263">Replace `a` with `a:hover`.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-rule2.msft.png" alt-text="将 替换为 a：hover" lightbox="../media/beginners-css-rule2.msft.png":::
       <span data-ttu-id="b9794-265">将 `a` 替换为</span><span class="sxs-lookup"><span data-stu-id="b9794-265">Replace `a` with</span></span> `a:hover`  
    :::image-end:::  
    
    `:hover` <span data-ttu-id="b9794-266">是 **伪类**。</span><span class="sxs-lookup"><span data-stu-id="b9794-266">is a **pseudo-class**.</span></span>  <span data-ttu-id="b9794-267">对可能进入特殊状态的样式元素使用伪类。</span><span class="sxs-lookup"><span data-stu-id="b9794-267">Use pseudo-classes for style elements that may enter special states.</span></span>  <span data-ttu-id="b9794-268">例如， `a:hover` 仅在将鼠标悬停在某个元素上时，该样式才 `<a>` 生效。</span><span class="sxs-lookup"><span data-stu-id="b9794-268">For example, the `a:hover` style only takes effect when you are hovering over an `<a>` element.</span></span>  
    
1.  <span data-ttu-id="b9794-269">在括号之间选择以添加新声明。</span><span class="sxs-lookup"><span data-stu-id="b9794-269">Choose between the brackets to add a new declaration.</span></span>  
1.  <span data-ttu-id="b9794-270">键入 `background-color` 声明名称并选择 `Enter`。</span><span class="sxs-lookup"><span data-stu-id="b9794-270">Type `background-color` for the declaration name and select `Enter`.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-rule3.msft.png" alt-text="键入 background-color" lightbox="../media/beginners-css-rule3.msft.png":::
       <span data-ttu-id="b9794-272">类型</span><span class="sxs-lookup"><span data-stu-id="b9794-272">Type</span></span> `background-color`  
    :::image-end:::  
    
1.  <span data-ttu-id="b9794-273">键入 `green` 声明值并选择 `Enter`。</span><span class="sxs-lookup"><span data-stu-id="b9794-273">Type `green` for the declaration value and select `Enter`.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-rule4.msft.png" alt-text="类型绿色" lightbox="../media/beginners-css-rule4.msft.png":::
       <span data-ttu-id="b9794-275">类型</span><span class="sxs-lookup"><span data-stu-id="b9794-275">Type</span></span> `green`  
    :::image-end:::  
    
1.  <span data-ttu-id="b9794-276">将鼠标悬停在"主页 **"链接** 上。</span><span class="sxs-lookup"><span data-stu-id="b9794-276">Hover your mouse over the **Home** link.</span></span>  <span data-ttu-id="b9794-277">链接的背景变为绿色。</span><span class="sxs-lookup"><span data-stu-id="b9794-277">The background of the link turns green.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-rule5.msft.png" alt-text="将鼠标悬停在主页链接上以显示其绿色背景" lightbox="../media/beginners-css-rule5.msft.png":::
       <span data-ttu-id="b9794-279">将鼠标悬停在"主页"链接上以显示其绿色背景</span><span class="sxs-lookup"><span data-stu-id="b9794-279">Hover on the Home link to reveal its green background</span></span>  
    :::image-end:::  
    
## <a name="re-use-styles-across-pages-with-external-stylesheets"></a><span data-ttu-id="b9794-280">在具有外部样式表的页面中重新使用样式</span><span class="sxs-lookup"><span data-stu-id="b9794-280">Re-use styles across pages with external stylesheets</span></span>  

<span data-ttu-id="b9794-281">在上一步中，您将以下代码段作为内部样式表添加到 `contact.html`。</span><span class="sxs-lookup"><span data-stu-id="b9794-281">In a previous step, you added the following code snippet as an internal stylesheet to `contact.html`.</span></span>  

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

<span data-ttu-id="b9794-282">如果要以相同方式设置 `index.html` 样式，该做什么？</span><span class="sxs-lookup"><span data-stu-id="b9794-282">What if you wanted to style `index.html` the same way?</span></span>  <span data-ttu-id="b9794-283">如果您具有大量要应用样式的页面，应怎么做？</span><span class="sxs-lookup"><span data-stu-id="b9794-283">What if you had a large number of pages to which you wanted to apply your styles?</span></span>  <span data-ttu-id="b9794-284">您必须将内部样式表复制并粘贴到您的网站上的每个网页中。</span><span class="sxs-lookup"><span data-stu-id="b9794-284">You have to copy and paste the internal stylesheet into every single web page on your site.</span></span>  <span data-ttu-id="b9794-285">完成以下操作可添加 **外部样式表** ，以允许您编写 CSS 一次，并应用于多个页面。</span><span class="sxs-lookup"><span data-stu-id="b9794-285">Complete the following actions to add an **External stylesheet** to allow you to write your CSS once and apply it to multiple pages.</span></span>  

1.  <span data-ttu-id="b9794-286">首先，刷新实时选项卡以删除你在 DevTools 中所做的更改。</span><span class="sxs-lookup"><span data-stu-id="b9794-286">First, refresh the live tab to remove the changes that you made in DevTools.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-external1.msft.png" alt-text=" 刷新页面后，在 DevTools 中所做的更改将消失" lightbox="../media/beginners-css-external1.msft.png":::
        <span data-ttu-id="b9794-288">刷新页面后，在 DevTools 中所做的更改将消失</span><span class="sxs-lookup"><span data-stu-id="b9794-288">After you refresh the page, the changes that were made in DevTools are gone</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="b9794-289">返回到编辑器选项卡 **并** 打开 `contact.html`。</span><span class="sxs-lookup"><span data-stu-id="b9794-289">Go back to the **editor tab** and open `contact.html`.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-external2.msft.png" alt-text="contact.html" lightbox="../media/beginners-css-external2.msft.png":::
       <span data-ttu-id="b9794-291">contact.html</span><span class="sxs-lookup"><span data-stu-id="b9794-291">contact.html</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="b9794-292">删除`<style>`和`</style>` 之间的所有内容，包括`<style>`和`</style>`。</span><span class="sxs-lookup"><span data-stu-id="b9794-292">Delete everything between `<style>` and `</style>`, including `<style>` and `</style>`.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-external3.msft.png" alt-text="样式标记已删除" lightbox="../media/beginners-css-external3.msft.png":::
       <span data-ttu-id="b9794-294">样式标记已删除</span><span class="sxs-lookup"><span data-stu-id="b9794-294">The style tag has been removed</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="b9794-295">打开 `index.html` 并从 标记 `style="background-color: aliceblue;"` 中删除 `<nav>`。</span><span class="sxs-lookup"><span data-stu-id="b9794-295">Open `index.html` and remove `style="background-color: aliceblue;"` from the `<nav>` tag.</span></span>  <span data-ttu-id="b9794-296">现在，您已删除之前添加到网站的所有 CSS。</span><span class="sxs-lookup"><span data-stu-id="b9794-296">You have now removed all of the CSS that you previously added to your site.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-external4.msft.png" alt-text="内联样式已从导航元素中删除" lightbox="../media/beginners-css-external4.msft.png":::
       <span data-ttu-id="b9794-298">内联样式已从导航元素中删除</span><span class="sxs-lookup"><span data-stu-id="b9794-298">The inline style has been removed from the nav element</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="b9794-299">选择 **"新建文件"。**</span><span class="sxs-lookup"><span data-stu-id="b9794-299">Choose **New File**.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-external5.msft.png" alt-text="新建文件对话框" lightbox="../media/beginners-css-external5.msft.png":::
       <span data-ttu-id="b9794-301">"新建文件"对话框</span><span class="sxs-lookup"><span data-stu-id="b9794-301">The new file dialog</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="b9794-302">将 `cool-file.js` 替换为 `style.css` ，然后选择"**添加文件"。**</span><span class="sxs-lookup"><span data-stu-id="b9794-302">Replace `cool-file.js` with `style.css` and choose **Add File**.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-external6.msft.png" alt-text="Type style.css" lightbox="../media/beginners-css-external6.msft.png":::
       <span data-ttu-id="b9794-304">类型</span><span class="sxs-lookup"><span data-stu-id="b9794-304">Type</span></span> `style.css`  
    :::image-end:::  
    
1.  <span data-ttu-id="b9794-305">将以下代码段添加到 `style.css` 你的文件。</span><span class="sxs-lookup"><span data-stu-id="b9794-305">Add the following code snippet to your `style.css` file.</span></span>  
    
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
       <span data-ttu-id="b9794-307">将代码添加到</span><span class="sxs-lookup"><span data-stu-id="b9794-307">Add code to</span></span> `style.css`  
    :::image-end:::  
    
    <span data-ttu-id="b9794-308">确保已创建外部样式表。</span><span class="sxs-lookup"><span data-stu-id="b9794-308">Ensure that you have created an external stylesheet.</span></span> <span data-ttu-id="b9794-309">您的 HTML 不知道它是否存在。</span><span class="sxs-lookup"><span data-stu-id="b9794-309">Your HTML is not aware that it exists.</span></span>  
    
1.  <span data-ttu-id="b9794-310">打开 `index.html`。</span><span class="sxs-lookup"><span data-stu-id="b9794-310">Open `index.html`.</span></span>  
1.  <span data-ttu-id="b9794-311">添加到 `<link rel="stylesheet" href="style.css">` HTML。</span><span class="sxs-lookup"><span data-stu-id="b9794-311">Add `<link rel="stylesheet" href="style.css">` to your HTML.</span></span>  
    
    ```html
    <head>
        ...
        <meta name="viewport" content="width=device-width, initial-scale=1">
        <link rel="stylesheet" href="style.css">
    </head>
    ```  
    
    :::image type="complex" source="../media/beginners-css-external8.msft.png" alt-text="链接到 style.css" lightbox="../media/beginners-css-external8.msft.png":::
       <span data-ttu-id="b9794-313">链接到</span><span class="sxs-lookup"><span data-stu-id="b9794-313">Link to</span></span> `style.css`  
    :::image-end:::  
    
1.  <span data-ttu-id="b9794-314">打开 `contact.html` 文件，并添加链接。</span><span class="sxs-lookup"><span data-stu-id="b9794-314">Open the `contact.html` file and add the link there.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-external9.msft.png" alt-text="链接到 contact.html 中的 style.css" lightbox="../media/beginners-css-external9.msft.png":::
       <span data-ttu-id="b9794-316">链接到 `style.css`</span><span class="sxs-lookup"><span data-stu-id="b9794-316">Link to `style.css` in</span></span> `contact.html`  
    :::image-end:::  
    
1.  <span data-ttu-id="b9794-317">导航到实时 **选项卡**。 主页上一节和蓝色导航部分现在具有相同的字体。</span><span class="sxs-lookup"><span data-stu-id="b9794-317">Navigate to the **live tab**.  The home page now has the same font from the last section and a blue navigation section.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-external10.msft.png" alt-text="主页" lightbox="../media/beginners-css-external10.msft.png":::
       <span data-ttu-id="b9794-319">主页</span><span class="sxs-lookup"><span data-stu-id="b9794-319">The home page</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="b9794-320">选择 **"联系人** "链接以导航到联系人页面。</span><span class="sxs-lookup"><span data-stu-id="b9794-320">Choose the **Contact** link to navigate to the contact page.</span></span>  <span data-ttu-id="b9794-321">联系人页面的格式与主页的格式相同。</span><span class="sxs-lookup"><span data-stu-id="b9794-321">The contact page has the same formatting as the home page.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-external11.msft.png" alt-text="联系人页面" lightbox="../media/beginners-css-external11.msft.png":::
       <span data-ttu-id="b9794-323">联系人页面</span><span class="sxs-lookup"><span data-stu-id="b9794-323">The contact page</span></span>  
    :::image-end:::  
    
## <a name="use-a-css-framework"></a><span data-ttu-id="b9794-324">使用 CSS 框架</span><span class="sxs-lookup"><span data-stu-id="b9794-324">Use a CSS framework</span></span>  

<span data-ttu-id="b9794-325">**CSS 框架** 是由其他开发人员构建的样式集合，可更轻松地创建极具吸引力的网站。</span><span class="sxs-lookup"><span data-stu-id="b9794-325">**CSS frameworks** are collections of styles built by other developers that make it easier to create attractive web sites.</span></span>  <span data-ttu-id="b9794-326">框架提供了一组可以在页面元素上使用的样式，而不是自己定义样式。</span><span class="sxs-lookup"><span data-stu-id="b9794-326">Instead of defining styles yourself, a framework provides you a collection of styles that you are able to use on your page elements.</span></span>  

1.  <span data-ttu-id="b9794-327">复制以下代码：</span><span class="sxs-lookup"><span data-stu-id="b9794-327">Copy the following code:</span></span>  
    
    ```html
    <link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.1.1/css/bootstrap.min.css">
    ```  
    
1.  <span data-ttu-id="b9794-328">打开编辑选项卡，然后将代码粘贴到 `contact.html` 中。</span><span class="sxs-lookup"><span data-stu-id="b9794-328">Open the editing tab and paste the code into `contact.html`.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-framework1.msft.png" alt-text="链接到 contact.html 中的框架" lightbox="../media/beginners-css-framework1.msft.png":::
       <span data-ttu-id="b9794-330">中框架的链接</span><span class="sxs-lookup"><span data-stu-id="b9794-330">Link to the framework in</span></span> `contact.html`  
    :::image-end:::  
    
1.  <span data-ttu-id="b9794-331">打开 `index.html` 文件，并添加代码。</span><span class="sxs-lookup"><span data-stu-id="b9794-331">Open the `index.html` file and add the code there.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-framework2.msft.png" alt-text="链接到 index.html 中的框架" lightbox="../media/beginners-css-framework2.msft.png":::
       <span data-ttu-id="b9794-333">中框架的链接</span><span class="sxs-lookup"><span data-stu-id="b9794-333">Link to the framework in</span></span> `index.html`  
    :::image-end:::  
    
1.  <span data-ttu-id="b9794-334">返回到实时选项卡以查看更改。</span><span class="sxs-lookup"><span data-stu-id="b9794-334">Go back to the live tab to view your changes.</span></span>  <span data-ttu-id="b9794-335">虽然 `<nav>` 元素的背景色和 `<li>` 和 `<a>` 的字体相同，但其他元素的字体已更改。</span><span class="sxs-lookup"><span data-stu-id="b9794-335">While the background color of the `<nav>` element and the font of the `<li>` and `<a>` elements are the same, the font of the other elements has changed.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-framework3.msft.png" alt-text="主页上的一些字体由于框架而更改" lightbox="../media/beginners-css-framework3.msft.png":::
       <span data-ttu-id="b9794-337">主页上的一些字体由于框架而更改</span><span class="sxs-lookup"><span data-stu-id="b9794-337">Some of the font on the home page changed because of the framework</span></span>  
    :::image-end:::  
    
### <a name="use-a-class"></a><span data-ttu-id="b9794-338">使用类</span><span class="sxs-lookup"><span data-stu-id="b9794-338">Use a class</span></span>  

<span data-ttu-id="b9794-339">在上一部分中，你向网页添加了 Bootstrap，这更改了网站上某些元素的字体。</span><span class="sxs-lookup"><span data-stu-id="b9794-339">In the last section, you added Bootstrap to your web pages, which changed the fonts of some of the elements on your site.</span></span>  <span data-ttu-id="b9794-340">CSS 框架可帮助你使用非常少的代码对页面进行重大更改。</span><span class="sxs-lookup"><span data-stu-id="b9794-340">CSS frameworks help you make major changes to your page with very little code.</span></span>  <span data-ttu-id="b9794-341">完成以下操作以更改标头。</span><span class="sxs-lookup"><span data-stu-id="b9794-341">Complete the following actions to change your header.</span></span>  

1.  <span data-ttu-id="b9794-342">复制以下代码段。</span><span class="sxs-lookup"><span data-stu-id="b9794-342">Copy the following code snippet.</span></span>  
    
    ```html
    class="jumbotron jumbotron-fluid"  
    ```  
    
1.  <span data-ttu-id="b9794-343">将前面的代码段添加到 `<header>` 中的 标记 `index.html`。</span><span class="sxs-lookup"><span data-stu-id="b9794-343">Add the previous code snippet to your `<header>` tag in `index.html`.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-jumbotron1.msft.png" alt-text="在 index.html 中添加类" lightbox="../media/beginners-css-jumbotron1.msft.png":::
       <span data-ttu-id="b9794-345">在 中添加类</span><span class="sxs-lookup"><span data-stu-id="b9794-345">Add classes in</span></span> `index.html`  
    :::image-end:::  
    
1.  <span data-ttu-id="b9794-346">将代码添加到 `<header>` 中的 标记 `contact.html`。</span><span class="sxs-lookup"><span data-stu-id="b9794-346">Add the code to your `<header>` tag in `contact.html`.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-jumbotron2.msft.png" alt-text="在 contact.html 中添加类" lightbox="../media/beginners-css-jumbotron2.msft.png":::
       <span data-ttu-id="b9794-348">在 中添加类</span><span class="sxs-lookup"><span data-stu-id="b9794-348">Add classes in</span></span> `contact.html`  
    :::image-end:::  
    
1.  <span data-ttu-id="b9794-349">在实时选项卡中查看更改。 标题周围有一个大的灰色框。</span><span class="sxs-lookup"><span data-stu-id="b9794-349">View your changes in the live tab.  There is a big, grey box around your header.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-jumbotron3.msft.png" alt-text="页眉四周现在有一个大的灰色框" lightbox="../media/beginners-css-jumbotron3.msft.png":::
       <span data-ttu-id="b9794-351">页眉四周现在有一个大的灰色框</span><span class="sxs-lookup"><span data-stu-id="b9794-351">The header now has a big, grey box around it</span></span>  
    :::image-end:::  
    
### <a name="understand-classes"></a><span data-ttu-id="b9794-352">了解类</span><span class="sxs-lookup"><span data-stu-id="b9794-352">Understand classes</span></span>  

<span data-ttu-id="b9794-353">类使你可以将样式集合分配给任意元素。</span><span class="sxs-lookup"><span data-stu-id="b9794-353">Classes let you assign collections of styles to arbitrary elements.</span></span>  <span data-ttu-id="b9794-354">将下列代码片段设置为 `<header>` 属性后，将多个样式应用到 `class` 元素 `jumbotron`。</span><span class="sxs-lookup"><span data-stu-id="b9794-354">Use the following code snippet to apply several styles to the `<header>` element after you set the `class` attribute to `jumbotron`.</span></span>  

```css
.jumbotron {
  padding: 2rem 1rem;
  margin-bottom: 2rem;
  background-color: #e9ecef;
  border-radius: .3rem;
}
```  

<span data-ttu-id="b9794-355">类的一个优点是，它允许您将样式应用到所需的任何元素。</span><span class="sxs-lookup"><span data-stu-id="b9794-355">One advantage of a class is that it lets you apply styles to whatever elements you want.</span></span>  <span data-ttu-id="b9794-356">例如，假设你想要将某些元素的背景色设置为 `<p>` 紫色，而不是所有 `<p>` 元素。</span><span class="sxs-lookup"><span data-stu-id="b9794-356">For example, suppose you want to set the background color of some `<p>` elements to purple, but not all `<p>` elements.</span></span>  <span data-ttu-id="b9794-357">使用以下代码段定义类中的样式。</span><span class="sxs-lookup"><span data-stu-id="b9794-357">Use the following code snippet to define the style in a class.</span></span>  

```css
.custom-background {
  background-color: purple;
}
```  

<span data-ttu-id="b9794-358">接下来，将类仅 `<p>` 应用于要设置样式的元素。</span><span class="sxs-lookup"><span data-stu-id="b9794-358">Next, apply the class to only the `<p>` elements that you want to style.</span></span>  

```html
<p>The text is not purple.</p>
<p class="custom-background">The text is purple.</p>
<p>The text is not purple.</p>
<p class="custom-background">The text is purple.</p>
```  

### <a name="align-elements"></a><span data-ttu-id="b9794-359">对齐元素</span><span class="sxs-lookup"><span data-stu-id="b9794-359">Align elements</span></span>  

<span data-ttu-id="b9794-360">完成以下操作以引导并提供用于对齐元素的类。</span><span class="sxs-lookup"><span data-stu-id="b9794-360">Complete the following actions to bootstrap and provide classes for aligning elements.</span></span>  

1.  <span data-ttu-id="b9794-361">返回到编辑器选项卡并打开 `index.html`。</span><span class="sxs-lookup"><span data-stu-id="b9794-361">Go back to the editor tab and open `index.html`.</span></span>  
1.  <span data-ttu-id="b9794-362">添加到 `class="container-fluid"` 标记 `<body>`。</span><span class="sxs-lookup"><span data-stu-id="b9794-362">Add `class="container-fluid"` to your `<body>` tag.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-align1.msft.png" alt-text="添加容器流类" lightbox="../media/beginners-css-align1.msft.png":::
       <span data-ttu-id="b9794-364">添加 `container-fluid` 类</span><span class="sxs-lookup"><span data-stu-id="b9794-364">Add the `container-fluid` class</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="b9794-365">在 `<nav>` 中 `<main>` 包 `<div class="row">`元素。</span><span class="sxs-lookup"><span data-stu-id="b9794-365">Wrap your `<nav>` and `<main>` elements in `<div class="row">`.</span></span>  <span data-ttu-id="b9794-366">请务必在 `</div>` 之后 `</main>` 添加 ，以便正确关闭新标记。</span><span class="sxs-lookup"><span data-stu-id="b9794-366">Make sure to put `</div>` after `</main>` in order to properly close the new tag.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-align2.msft.png" alt-text="添加行" lightbox="../media/beginners-css-align2.msft.png":::
       <span data-ttu-id="b9794-368">添加行</span><span class="sxs-lookup"><span data-stu-id="b9794-368">Add a row</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="b9794-369">向 `class="col-3"` 标记添加 `<nav>` ， `class="col-9"` 添加到 `<main>` 标记。</span><span class="sxs-lookup"><span data-stu-id="b9794-369">Add `class="col-3"` to your `<nav>` tag and `class="col-9"` to your `<main>` tag.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-align3.msft.png" alt-text="添加 col-3 和 col-9 类" lightbox="../media/beginners-css-align3.msft.png":::
       <span data-ttu-id="b9794-371">添加 `col-3` 和 `col-9` 类</span><span class="sxs-lookup"><span data-stu-id="b9794-371">Add the `col-3` and `col-9` classes</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="b9794-372">在实时选项卡中查看更改。</span><span class="sxs-lookup"><span data-stu-id="b9794-372">View your changes in the live tab.</span></span>  
    
    :::image type="complex" source="../media/beginners-css-align4.msft.png" alt-text="导航内容现在位于主内容的左侧" lightbox="../media/beginners-css-align4.msft.png":::
       <span data-ttu-id="b9794-374">导航内容现在位于主内容的左侧</span><span class="sxs-lookup"><span data-stu-id="b9794-374">The nav content is now to the left of the main content</span></span>  
    :::image-end:::  
    
## <a name="next-steps"></a><span data-ttu-id="b9794-375">后续步骤</span><span class="sxs-lookup"><span data-stu-id="b9794-375">Next steps</span></span>  

<span data-ttu-id="b9794-376">恭喜，你已完成操作。</span><span class="sxs-lookup"><span data-stu-id="b9794-376">Congratulations, you are done.</span></span>  

*   <span data-ttu-id="b9794-377">更好地进行 Web 开发的最好办法就是构建更多网站。</span><span class="sxs-lookup"><span data-stu-id="b9794-377">The best way to get better at web development is to build more sites.</span></span>  <span data-ttu-id="b9794-378">不要担心中断内容。</span><span class="sxs-lookup"><span data-stu-id="b9794-378">Do not worry about breaking stuff.</span></span>  <span data-ttu-id="b9794-379">请一直玩得有趣，并尽可能学习。</span><span class="sxs-lookup"><span data-stu-id="b9794-379">Just have fun and learn as much as possible along the way.</span></span>  
*   <span data-ttu-id="b9794-380">若要了解有关设置网页样式的信息，请导航到 CSS [简介][MDNCssFirstSteps]。</span><span class="sxs-lookup"><span data-stu-id="b9794-380">To learn more about styling web pages, navigate to [Introduction to CSS][MDNCssFirstSteps].</span></span>  
*   <span data-ttu-id="b9794-381">若要深入了解如何使用 DevTools 尝试页面的 CSS，请导航到 ["开始查看和更改 CSS 管理][DevtoolsCssIndex]。</span><span class="sxs-lookup"><span data-stu-id="b9794-381">To learn more about how to use DevTools to experiment with the CSS of a page, navigate to [Get Started with Viewing and Changing CSS][DevtoolsCssIndex].</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="b9794-382">联系 Microsoft Edge 开发工具团队</span><span class="sxs-lookup"><span data-stu-id="b9794-382">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!--- links  --->  

[DevtoolsBeginnersHtml]: ./html.md "适用于初学者的 DevTools：HTML 和 DOM |Microsoft Docs"  
[DevtoolsCssIndex]: ../css/index.md "查看和更改 CSS 入门 | Microsoft 文档"  

[MicrosoftEdgeInsider]: https://www.microsoftedgeinsider.com "Microsoft Edge 预览体验成员"  

[GlitchCookedAmphibianIndex]: https://glitch.com/edit/#!/cooked-amphibian?path=index.html "index.html - 已准备的 amphibian |小故障"  

[MDNCssFirstSteps]: https://developer.mozilla.org/docs/Learn/CSS/Introduction_to_CSS "CSS 第一|MDN"  

> [!NOTE]
> <span data-ttu-id="b9794-388">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="b9794-388">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="b9794-389">原始页面 [此处](https://developers.google.com/web/tools/chrome-devtools/beginners/css) ，作者 [Katherine Jackson][KatherineJackson] \（技术作家 Intern，Chrome DevTools\）。</span><span class="sxs-lookup"><span data-stu-id="b9794-389">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/beginners/css) and is authored by [Katherine Jackson][KatherineJackson] \(Technical Writer Intern, Chrome DevTools\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="b9794-391">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="b9794-391">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[KatherineJackson]: https://developers.google.com/web/resources/contributors/katjackson  
