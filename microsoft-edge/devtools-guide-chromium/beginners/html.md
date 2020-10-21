---
description: HTML 和 DOM 入门
title: 初学者的 DevTools： HTML 和 DOM 入门
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: f17b68845ef746fa2612cdf4d02cc7e1003baabb
ms.sourcegitcommit: 99eee78698dc95b2a3fa638a5b063ef449899cda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/20/2020
ms.locfileid: "11125298"
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

# <span data-ttu-id="f2d30-104">初学者的 DevTools： HTML 和 DOM 入门</span><span class="sxs-lookup"><span data-stu-id="f2d30-104">DevTools for beginners: Get started with HTML and the DOM</span></span>  

<span data-ttu-id="f2d30-105">这是介绍 web 开发基础知识的一系列教程中的第一项。</span><span class="sxs-lookup"><span data-stu-id="f2d30-105">This is the first in a series of tutorials that teach you the basics of web development.</span></span>  <span data-ttu-id="f2d30-106">你还将了解一组名为 Microsoft Edge DevTools 的 web 开发人员工具，这些工具可以提高工作效率。</span><span class="sxs-lookup"><span data-stu-id="f2d30-106">You will also learn about a set of web developer tools called Microsoft Edge DevTools that can increase your productivity.</span></span>  

<span data-ttu-id="f2d30-107">在本特定教程中，你将了解有关 HTML 和 DOM 的信息。</span><span class="sxs-lookup"><span data-stu-id="f2d30-107">In this particular tutorial, you learn about HTML and the DOM.</span></span>  <span data-ttu-id="f2d30-108">HTML 是 web 开发的核心技术之一。</span><span class="sxs-lookup"><span data-stu-id="f2d30-108">HTML is one of the core technologies of web development.</span></span>  <span data-ttu-id="f2d30-109">它是用于控制网页的结构和内容的语言。</span><span class="sxs-lookup"><span data-stu-id="f2d30-109">It is the language that controls the structure and content of webpages.</span></span>  <span data-ttu-id="f2d30-110">DOM 还与网页的结构和内容相关，但稍后你将了解更多相关信息。</span><span class="sxs-lookup"><span data-stu-id="f2d30-110">The DOM is also related to the structure and content of webpages, but you'll learn more about that later.</span></span>  

## <span data-ttu-id="f2d30-111">目标</span><span class="sxs-lookup"><span data-stu-id="f2d30-111">Goals</span></span>  

<span data-ttu-id="f2d30-112">您将通过实际构建自己的网站来了解 web 开发。</span><span class="sxs-lookup"><span data-stu-id="f2d30-112">You are going to learn web development by actually building your own website.</span></span>  <span data-ttu-id="f2d30-113">当您完成 *DevTools For 初学者* 系列中的所有教程时，完成的网站将如下图所示。</span><span class="sxs-lookup"><span data-stu-id="f2d30-113">By the time you complete all of the tutorials in the *DevTools for Beginners* series, your finished site will look like in the following figure.</span></span>  

:::image type="complex" source="../media/beginners-html-finished.msft.png" alt-text="完成的网站" lightbox="../media/beginners-html-finished.msft.png":::
   <span data-ttu-id="f2d30-115">完成的网站</span><span class="sxs-lookup"><span data-stu-id="f2d30-115">The finished site</span></span>  
:::image-end:::  

<span data-ttu-id="f2d30-116">本教程结束时，你将了解：</span><span class="sxs-lookup"><span data-stu-id="f2d30-116">By the end of this tutorial, you will understand:</span></span>  

*   <span data-ttu-id="f2d30-117">HTML 和 DOM 如何创建你在网页上看到的内容。</span><span class="sxs-lookup"><span data-stu-id="f2d30-117">How HTML and the DOM create the content that you see on webpages.</span></span>  
*   <span data-ttu-id="f2d30-118">Microsoft Edge DevTools 可如何帮助你体验 HTML 和 DOM 更改。</span><span class="sxs-lookup"><span data-stu-id="f2d30-118">How Microsoft Edge DevTools can help you experiment with HTML and DOM changes.</span></span>  
*   <span data-ttu-id="f2d30-119">HTML 和 DOM 之间的区别。</span><span class="sxs-lookup"><span data-stu-id="f2d30-119">The difference between HTML and the DOM.</span></span>  

<span data-ttu-id="f2d30-120">您还有一个真正的网站！</span><span class="sxs-lookup"><span data-stu-id="f2d30-120">You'll also have a real website!</span></span>  <span data-ttu-id="f2d30-121">你可以使用此网站主持你的简历或博客。</span><span class="sxs-lookup"><span data-stu-id="f2d30-121">You can use this site to host your resume or blog.</span></span>  

## <span data-ttu-id="f2d30-122">必备条件</span><span class="sxs-lookup"><span data-stu-id="f2d30-122">Prerequisites</span></span>  

<span data-ttu-id="f2d30-123">在尝试本教程之前，请完成以下先决条件：</span><span class="sxs-lookup"><span data-stu-id="f2d30-123">Before attempting this tutorial, complete the following prerequisites:</span></span>  

*   <span data-ttu-id="f2d30-124">如果您不熟悉 HTML，请阅读 [html][MDNGettingStartedHtml]入门。</span><span class="sxs-lookup"><span data-stu-id="f2d30-124">If you are unfamiliar with HTML, read [Getting Started with HTML][MDNGettingStartedHtml].</span></span>  
*   <span data-ttu-id="f2d30-125">下载 [Microsoft Edge][MicrosoftEdgeInsider] web 浏览器。</span><span class="sxs-lookup"><span data-stu-id="f2d30-125">Download the [Microsoft Edge][MicrosoftEdgeInsider] web browser.</span></span>  <span data-ttu-id="f2d30-126">本教程使用一组称为 Microsoft Edge DevTools 的 web 开发工具，这些工具内置于 Microsoft Edge 中。</span><span class="sxs-lookup"><span data-stu-id="f2d30-126">This tutorial uses a set of web development tools, called the Microsoft Edge DevTools, that are built into Microsoft Edge.</span></span>  

## <span data-ttu-id="f2d30-127">设置代码</span><span class="sxs-lookup"><span data-stu-id="f2d30-127">Set up your code</span></span>  

<span data-ttu-id="f2d30-128">您将在名为 "问题" 的联机代码编辑器中构建您的网站。</span><span class="sxs-lookup"><span data-stu-id="f2d30-128">You are going to build your site in an online code editor called Glitch.</span></span>  

1.  <span data-ttu-id="f2d30-129">打开 [源代码][GlitchAlluringShockIndex]。</span><span class="sxs-lookup"><span data-stu-id="f2d30-129">Open the [source code][GlitchAlluringShockIndex].</span></span>  <span data-ttu-id="f2d30-130">此选项卡将在本教程的整个教程中称为 " **编辑器" 选项** 卡。</span><span class="sxs-lookup"><span data-stu-id="f2d30-130">This tab will be called the **editor tab** throughout this tutorial.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-setup1.msft.png" alt-text="完成的网站" lightbox="../media/beginners-html-setup1.msft.png":::
       <span data-ttu-id="f2d30-132">"编辑器" 选项卡</span><span class="sxs-lookup"><span data-stu-id="f2d30-132">The editor tab</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="f2d30-133">选择 **alluring-电击**。</span><span class="sxs-lookup"><span data-stu-id="f2d30-133">Choose **alluring-shock**.</span></span>  <span data-ttu-id="f2d30-134">将在左上角打开 "项目选项" 菜单。</span><span class="sxs-lookup"><span data-stu-id="f2d30-134">The Project Options menu opens in the top-left corner.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-setup2.msft.png" alt-text="完成的网站" lightbox="../media/beginners-html-setup2.msft.png":::
       <span data-ttu-id="f2d30-136">"项目选项" 菜单</span><span class="sxs-lookup"><span data-stu-id="f2d30-136">The Project Options menu</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="f2d30-137">选择 " **Remix Project**"。</span><span class="sxs-lookup"><span data-stu-id="f2d30-137">Choose **Remix Project**.</span></span>  <span data-ttu-id="f2d30-138">问题创建可编辑的项目副本，并随机为项目生成新名称。</span><span class="sxs-lookup"><span data-stu-id="f2d30-138">Glitch creates a copy of the project that you can edit and randomly generates a new name for the project.</span></span>  <span data-ttu-id="f2d30-139">内容与以前的内容相同。</span><span class="sxs-lookup"><span data-stu-id="f2d30-139">The content is the same as before.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-setup3.msft.png" alt-text="完成的网站" lightbox="../media/beginners-html-setup3.msft.png":::
       <span data-ttu-id="f2d30-141">Remixed 项目</span><span class="sxs-lookup"><span data-stu-id="f2d30-141">The remixed project</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="f2d30-142">如果你计划完成本系列中的下一个教程，请选择你的 GitHub 或 Facebook 帐户 **登录** 并登录问题。</span><span class="sxs-lookup"><span data-stu-id="f2d30-142">If you plan on completing the next tutorial in this series, choose **Sign In** and sign in to Glitch with your GitHub or Facebook account.</span></span>  <span data-ttu-id="f2d30-143">如果您不登录，一旦关闭 "编辑" 选项卡，您将失去编辑此项目的功能。</span><span class="sxs-lookup"><span data-stu-id="f2d30-143">If you don't sign in you will lose the ability to edit this project once you close the editing tab.</span></span>  
1.  <span data-ttu-id="f2d30-144">**在新窗口中选择 "\*\*\*\*显示**"，然后选择。</span><span class="sxs-lookup"><span data-stu-id="f2d30-144">Choose **Show** and choose **In a New Window**.</span></span>  <span data-ttu-id="f2d30-145">将打开一个新的选项卡，显示实时页面。</span><span class="sxs-lookup"><span data-stu-id="f2d30-145">A new tab opens, showing you the live page.</span></span>  <span data-ttu-id="f2d30-146">此选项卡将在整个教程中称为 " **实时" 选项卡** 。</span><span class="sxs-lookup"><span data-stu-id="f2d30-146">This tab will be called the **live tab** throughout this tutorial.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-setup4.msft.png" alt-text="完成的网站" lightbox="../media/beginners-html-setup4.msft.png":::
       <span data-ttu-id="f2d30-148">"实时" 选项卡</span><span class="sxs-lookup"><span data-stu-id="f2d30-148">The live tab</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="f2d30-149">添加内容</span><span class="sxs-lookup"><span data-stu-id="f2d30-149">Add content</span></span>  

<span data-ttu-id="f2d30-150">您的网站非常空。</span><span class="sxs-lookup"><span data-stu-id="f2d30-150">Your site is pretty empty.</span></span>  <span data-ttu-id="f2d30-151">请按照以下步骤将一些内容添加到！</span><span class="sxs-lookup"><span data-stu-id="f2d30-151">Follow the steps below to add some content to it!</span></span>  

1.  <span data-ttu-id="f2d30-152">在 " **编辑器" 选项卡**中，"替换 `<!-- You're "About Me" will go here.  -->` 为" `<h1>About Me</h1>` 。</span><span class="sxs-lookup"><span data-stu-id="f2d30-152">In the **editor tab**, replace `<!-- You're "About Me" will go here.  -->` with `<h1>About Me</h1>`.</span></span>  
    
    :::row:::
       :::column span="":::
          ```html
          ...
              ...
              <body>
                  <p> Your site!</p>
                  <main>
                      <h1>About Me</h1>
                  </main>
                  ...
              ...
          ...
          ```  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/beginners-html-add1.msft.png" alt-text="完成的网站" lightbox="../media/beginners-html-add1.msft.png":::
             <span data-ttu-id="f2d30-154">新代码在 "编辑器" 选项卡中突出显示</span><span class="sxs-lookup"><span data-stu-id="f2d30-154">The new code is highlighted in the editor tab</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::
    
1.  <span data-ttu-id="f2d30-155">在 " **实时" 选项卡**中查看所做的更改。 文本 `About Me` 显示在页面上。</span><span class="sxs-lookup"><span data-stu-id="f2d30-155">View your changes in the **live tab**.  The text `About Me` is visible on the page.</span></span>  <span data-ttu-id="f2d30-156">它比其余文本更大，因为该 `<h1>` 元素表示节标题。</span><span class="sxs-lookup"><span data-stu-id="f2d30-156">It's larger than the rest of the text, because the `<h1>` element represents a section heading.</span></span>  <span data-ttu-id="f2d30-157">Web 浏览器会自动以较大字体调整标题样式。</span><span class="sxs-lookup"><span data-stu-id="f2d30-157">Your web browser automatically styles headings in larger font sizes.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-add2.msft.png" alt-text="完成的网站" lightbox="../media/beginners-html-add2.msft.png":::
       <span data-ttu-id="f2d30-159">新标题在 "实时" 选项卡中可见</span><span class="sxs-lookup"><span data-stu-id="f2d30-159">The new heading is visible in the live tab</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="f2d30-160">返回到 " **编辑器" 选项卡**，在 `<p>I am learning HTML.  Recent accomplishments:</p>` 您刚放置的位置下方的行中插入 `<h1>About Me</h1>` 。</span><span class="sxs-lookup"><span data-stu-id="f2d30-160">Back in the **editor tab**, insert `<p>I am learning HTML.  Recent accomplishments:</p>` on the line below where you just put `<h1>About Me</h1>`.</span></span>  
    
    :::row:::
       :::column span="":::
          ```html
          ...
              ...
              <body>
                  <p> Your site!</p>
                  <main>
                      <h1>About Me</h1>
                      <p>I am learning web development.  Recent accomplishments:</p>
                  </main>
                  ...
              ...
          ...
          ```  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/beginners-html-add3.msft.png" alt-text="完成的网站" lightbox="../media/beginners-html-add3.msft.png":::
             <span data-ttu-id="f2d30-162">已更新的代码在 "编辑器" 选项卡中突出显示</span><span class="sxs-lookup"><span data-stu-id="f2d30-162">The updated code is highlighted in the editor tab</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::
    
1.  <span data-ttu-id="f2d30-163">在 " **实时" 选项卡**中查看您的更改。</span><span class="sxs-lookup"><span data-stu-id="f2d30-163">View your change in the **live tab**.</span></span>  
1.  <span data-ttu-id="f2d30-164">返回到 " **编辑器" 选项卡**，添加你的成就列表：</span><span class="sxs-lookup"><span data-stu-id="f2d30-164">Back in the **editor tab**, add a list of your accomplishments:</span></span>  
    
    :::row:::
       :::column span="":::
          ```html
          ...
              ...
                  ...
                  <p>I am learning web development.  Recent accomplishments:</p>
                  <ul>
                      <li>Learned how to set up my code in Glitch.</li>
                      <li>Added content to my HTML.</li>
                      <li>TODO: Learn how to use Microsoft Edge DevTools to experiment with content changes.</li>
                      <li>TODO: Learn the difference between HTML and the DOM.</li>
                  </ul>
                  ...
              ...
          ...
          ```  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/beginners-html-add4.msft.png" alt-text="完成的网站" lightbox="../media/beginners-html-add4.msft.png":::
             <span data-ttu-id="f2d30-166">已更新的代码也会在 "编辑器" 选项卡中突出显示</span><span class="sxs-lookup"><span data-stu-id="f2d30-166">The updated code is also highlighted in the editor tab</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
1.  <span data-ttu-id="f2d30-167">再次返回 " **实时" 选项卡** ，确保新内容正确显示。</span><span class="sxs-lookup"><span data-stu-id="f2d30-167">Again, go back to the **live tab** to make sure that the new content is displaying correctly.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-add5.msft.png" alt-text="完成的网站" lightbox="../media/beginners-html-add5.msft.png":::
       <span data-ttu-id="f2d30-169">新列表在 "实时" 选项卡中可见</span><span class="sxs-lookup"><span data-stu-id="f2d30-169">The new list is visible in the live tab</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="f2d30-170">在 Microsoft Edge DevTools 中试用内容更改</span><span class="sxs-lookup"><span data-stu-id="f2d30-170">Experiment with content changes in Microsoft Edge DevTools</span></span>  

<span data-ttu-id="f2d30-171">如果你正在开发一个包含大量 HTML 的大型页面，你可以想像，在 "编辑器" 选项卡和 "实时" 选项卡之间来回切换以查看你的更改，尤其是当你不确定要在页面上放置哪些内容时。</span><span class="sxs-lookup"><span data-stu-id="f2d30-171">If you were developing a big page with a lot of HTML, you can imagine that it might be somewhat tedious to go back-and-forth between the editor tab and the live tab hundreds of times in order to see your changes, especially if you weren't sure what exactly to put on the page.</span></span>  <span data-ttu-id="f2d30-172">Microsoft Edge DevTools 可帮助你在不离开 "实时" 选项卡的情况下试用内容更改。</span><span class="sxs-lookup"><span data-stu-id="f2d30-172">Microsoft Edge DevTools can help you experiment with content changes without ever leaving the live tab.</span></span>  

### <span data-ttu-id="f2d30-173">了解 HTML 和 DOM 之间的区别</span><span class="sxs-lookup"><span data-stu-id="f2d30-173">Learn the difference between HTML and the DOM</span></span>  

<span data-ttu-id="f2d30-174">开始从 Microsoft Edge DevTools 编辑内容之前，了解 HTML 和 DOM 之间的区别很有帮助。</span><span class="sxs-lookup"><span data-stu-id="f2d30-174">Before you start editing your content from Microsoft Edge DevTools, it's helpful to understand the difference between HTML and the DOM.</span></span>  <span data-ttu-id="f2d30-175">例如，学习的最佳方式是：</span><span class="sxs-lookup"><span data-stu-id="f2d30-175">The best way to learn is by example:</span></span>  

1.  <span data-ttu-id="f2d30-176">转到 " **实时" 选项卡**。 在页面底部看到文本 `A new element!?!` 。</span><span class="sxs-lookup"><span data-stu-id="f2d30-176">Go to the **live tab**.  At the bottom of your page you see the text `A new element!?!`.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-dom1.msft.png" alt-text="完成的网站" lightbox="../media/beginners-html-dom1.msft.png":::
       <span data-ttu-id="f2d30-179">在页面底部，新元素的文本!?!</span><span class="sxs-lookup"><span data-stu-id="f2d30-179">At the bottom of the page the text A new element!?!</span></span> <span data-ttu-id="f2d30-180">可以看到</span><span class="sxs-lookup"><span data-stu-id="f2d30-180">can be seen</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="f2d30-181">返回到 " **编辑器" 选项卡** ，然后尝试在中查找此文本 `index.html` 。</span><span class="sxs-lookup"><span data-stu-id="f2d30-181">Go back to the **editor tab** and try to find this text in `index.html`.</span></span>  <span data-ttu-id="f2d30-182">不在这里！</span><span class="sxs-lookup"><span data-stu-id="f2d30-182">It's not there!</span></span>  
    
    :::image type="complex" source="../media/beginners-html-dom2.msft.png" alt-text="完成的网站" lightbox="../media/beginners-html-dom2.msft.png":::
       <span data-ttu-id="f2d30-185">`A new element!?!`无法在中找到神秘的文本</span><span class="sxs-lookup"><span data-stu-id="f2d30-185">The mystery text `A new element!?!` is nowhere to be found in</span></span> `index.html`  
    :::image-end:::  
    
1.  <span data-ttu-id="f2d30-186">返回到 " **实时" 选项卡**，右键单击 `A new element!?!` ，然后选择 " **检查**"。</span><span class="sxs-lookup"><span data-stu-id="f2d30-186">Go back to the **live tab**, right-click `A new element!?!`, and choose **Inspect**.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-dom3.msft.png" alt-text="完成的网站" lightbox="../media/beginners-html-dom3.msft.png":::
       <span data-ttu-id="f2d30-188">检查某些文本</span><span class="sxs-lookup"><span data-stu-id="f2d30-188">Inspecting some text</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="f2d30-189">DevTools 将在您的页面旁打开。</span><span class="sxs-lookup"><span data-stu-id="f2d30-189">DevTools opens up alongside your page.</span></span>  `<div>A new element!?!</div>` <span data-ttu-id="f2d30-190">将突出显示蓝色。</span><span class="sxs-lookup"><span data-stu-id="f2d30-190">is highlighted blue.</span></span>  <span data-ttu-id="f2d30-191">虽然 DevTools 中的此结构看起来像是 HTML，但实际上它是 **DOM 树**。</span><span class="sxs-lookup"><span data-stu-id="f2d30-191">Although this structure in DevTools looks like your HTML, it is actually the **DOM Tree**.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-dom4.msft.png" alt-text="完成的网站" lightbox="../media/beginners-html-dom4.msft.png":::
       <span data-ttu-id="f2d30-193">DevTools 在页面旁打开</span><span class="sxs-lookup"><span data-stu-id="f2d30-193">DevTools is open alongside the page</span></span>  
    :::image-end:::  
    
<span data-ttu-id="f2d30-194">加载页面时，浏览器将获取 HTML 以创建页面的 *初始* 内容。</span><span class="sxs-lookup"><span data-stu-id="f2d30-194">When your page loads, the browser takes your HTML to create the *initial* content of the page.</span></span>  <span data-ttu-id="f2d30-195">DOM 表示页面的 *当前* 内容，它可能会随着时间的推移而更改。</span><span class="sxs-lookup"><span data-stu-id="f2d30-195">The DOM represents the *current* content of the page, which can change over time.</span></span>  <span data-ttu-id="f2d30-196">`<div>A new element!?!</div>`由于 HTML 底部的标记，可将神秘的内容添加到页面中 `<script src="new.js"></script>` 。</span><span class="sxs-lookup"><span data-stu-id="f2d30-196">The mysterious `<div>A new element!?!</div>` content is added to your page because of the `<script src="new.js"></script>` tag at the bottom of your HTML.</span></span>  <span data-ttu-id="f2d30-197">此标记会导致运行某些 JavaScript 代码。</span><span class="sxs-lookup"><span data-stu-id="f2d30-197">This tag causes some JavaScript code to run.</span></span>  <span data-ttu-id="f2d30-198">在后面的教程中，你将了解有关 JavaScript 的详细信息，但现在将其视为可更改你的页面内容的编程语言。</span><span class="sxs-lookup"><span data-stu-id="f2d30-198">You'll learn more about JavaScript in a later tutorial, but for now think of it as a programming language that can change the content of your page.</span></span>  <span data-ttu-id="f2d30-199">在此特定情况下，JavaScript 代码将添加 `<div>A new element!?!</div>` 到您的页面。</span><span class="sxs-lookup"><span data-stu-id="f2d30-199">In this particular case, JavaScript code adds `<div>A new element!?!</div>` to your page.</span></span>  <span data-ttu-id="f2d30-200">这就是您的实时页面（而不是 HTML）中显示此神秘文本的原因。</span><span class="sxs-lookup"><span data-stu-id="f2d30-200">That is why this mystery text is visible on your live page, but not in your HTML.</span></span>  

### <span data-ttu-id="f2d30-201">编辑 DOM</span><span class="sxs-lookup"><span data-stu-id="f2d30-201">Edit the DOM</span></span>  

<span data-ttu-id="f2d30-202">如果想要快速试用内容更改而又不离开 "实时" 选项卡，请尝试 DevTools。</span><span class="sxs-lookup"><span data-stu-id="f2d30-202">If you want to quickly experiment with content changes without ever leaving the live tab, try DevTools.</span></span>  

1.  <span data-ttu-id="f2d30-203">在 DevTools 中，右键单击 `Your site!` ，然后选择 " **编辑为 HTML**"。</span><span class="sxs-lookup"><span data-stu-id="f2d30-203">In DevTools, right-click `Your site!` and choose **Edit as HTML**.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-edit1.msft.png" alt-text="完成的网站" lightbox="../media/beginners-html-edit1.msft.png":::
       <span data-ttu-id="f2d30-205">将节点编辑为 HTML</span><span class="sxs-lookup"><span data-stu-id="f2d30-205">Editing the node as HTML</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="f2d30-206">替换 `<p>Your site!</p>` 为以下代码。</span><span class="sxs-lookup"><span data-stu-id="f2d30-206">Replace `<p>Your site!</p>` with the code below.</span></span>  
    
    :::row:::
       :::column span="":::
          ```html
          ...
              ...
                  ...
                  <header>
                      <p><b>Welcome to my site!</b></p>
                      <button>Download my resume</button>
                  </header>
                  ...
              ...
          ...
          ```  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/beginners-html-edit2.msft.png" alt-text="完成的网站" lightbox="../media/beginners-html-edit2.msft.png":::
             <span data-ttu-id="f2d30-208">以 HTML 格式更新节点</span><span class="sxs-lookup"><span data-stu-id="f2d30-208">Updating the node as HTML</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
1.  <span data-ttu-id="f2d30-209">选择 `Control` + `Enter` \ (Windows、Linux \ ) 或 `Command` + `Enter` \ (macOS \ ) 保存所做的更改，或在框外单击。</span><span class="sxs-lookup"><span data-stu-id="f2d30-209">Select `Control`+`Enter` \(Windows, Linux\) or `Command`+`Enter` \(macOS\) to save your changes, or click outside of the box.</span></span>  <span data-ttu-id="f2d30-210">您的更改会自动显示在您的页面的实时视图中。</span><span class="sxs-lookup"><span data-stu-id="f2d30-210">Your changes automatically show up in the live view of your page.</span></span>  <span data-ttu-id="f2d30-211">文本已 `Your site!` 替换为新内容。</span><span class="sxs-lookup"><span data-stu-id="f2d30-211">The text `Your site!` has been replaced with the new content.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-edit3.msft.png" alt-text="完成的网站" lightbox="../media/beginners-html-edit3.msft.png":::
       <span data-ttu-id="f2d30-213">新内容将立即显示在页面上</span><span class="sxs-lookup"><span data-stu-id="f2d30-213">The new content shows up immediately on the page</span></span>  
    :::image-end:::  
    
<span data-ttu-id="f2d30-214">此工作流仅适用于试用内容更改。</span><span class="sxs-lookup"><span data-stu-id="f2d30-214">This workflow is only good for experimenting with content changes.</span></span>  <span data-ttu-id="f2d30-215">如果重新加载页面或关闭选项卡，所做的更改将永久消失。</span><span class="sxs-lookup"><span data-stu-id="f2d30-215">If you reload the page or close the tab, your changes will be gone forever.</span></span>  <span data-ttu-id="f2d30-216">如果您使用的是此工作流，而您想要保存所做的更改，您需要手动将这些更改复制到您的 HTML 中。</span><span class="sxs-lookup"><span data-stu-id="f2d30-216">If you're using this workflow and you want to save your changes, you need to manually copy those changes over to your HTML.</span></span>  <span data-ttu-id="f2d30-217">接下来的几个部分介绍了一些可用于更改 DOM 树内容的更多方法。</span><span class="sxs-lookup"><span data-stu-id="f2d30-217">The next couple of sections show you some more ways that you can change content from the DOM Tree.</span></span>  

## <span data-ttu-id="f2d30-218">重新排序节点</span><span class="sxs-lookup"><span data-stu-id="f2d30-218">Reorder nodes</span></span>  

<span data-ttu-id="f2d30-219">你还可以更改 DOM 节点的顺序。</span><span class="sxs-lookup"><span data-stu-id="f2d30-219">You can also change the order of DOM nodes.</span></span>  <span data-ttu-id="f2d30-220">例如，在网页上，导航菜单位于底部附近。</span><span class="sxs-lookup"><span data-stu-id="f2d30-220">For example, on your web page the navigation menu is near the bottom.</span></span>  <span data-ttu-id="f2d30-221">将其移动到顶部：</span><span class="sxs-lookup"><span data-stu-id="f2d30-221">To move it to the top:</span></span>  

1.  <span data-ttu-id="f2d30-222">`<nav>`在 DevTools 的**DOM 树**中查找节点。</span><span class="sxs-lookup"><span data-stu-id="f2d30-222">Find the `<nav>` node in the **DOM Tree** of DevTools.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-reorder1.msft.png" alt-text="完成的网站" lightbox="../media/beginners-html-reorder1.msft.png":::
       <span data-ttu-id="f2d30-224">导航节点在 DevTools 中突出显示蓝色</span><span class="sxs-lookup"><span data-stu-id="f2d30-224">The nav node is highlighted blue in DevTools</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="f2d30-225">将 `<nav>` 节点拖到顶部，使其成为节点下方的第一个子级 `<body>` 。</span><span class="sxs-lookup"><span data-stu-id="f2d30-225">Drag the `<nav>` node to the top, so that it's the first child below the `<body>` node.</span></span>  
    
    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/beginners-html-reorder2.msft.png" alt-text="完成的网站" lightbox="../media/beginners-html-reorder2.msft.png":::
             <span data-ttu-id="f2d30-227">将导航节点拖动到顶部</span><span class="sxs-lookup"><span data-stu-id="f2d30-227">Dragging the nav node to the top</span></span>  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          <span data-ttu-id="f2d30-228">`<nav>`现在，节点显示在您的页面顶部。</span><span class="sxs-lookup"><span data-stu-id="f2d30-228">The `<nav>` node is now displaying at the top of your page.</span></span>  
          
          :::image type="complex" source="../media/beginners-html-reorder3.msft.png" alt-text="完成的网站" lightbox="../media/beginners-html-reorder3.msft.png":::
             <span data-ttu-id="f2d30-230">导航节点位于页面顶部</span><span class="sxs-lookup"><span data-stu-id="f2d30-230">The nav node is at the top of the page</span></span>  
          :::image-end:::  
       :::column-end:::
   :::row-end:::  
    
### <span data-ttu-id="f2d30-231">删除节点</span><span class="sxs-lookup"><span data-stu-id="f2d30-231">Delete a node</span></span>  

<span data-ttu-id="f2d30-232">您也可以从 DOM 树中删除节点。</span><span class="sxs-lookup"><span data-stu-id="f2d30-232">You can also remove nodes from the DOM Tree.</span></span>  

1.  <span data-ttu-id="f2d30-233">在 **DOM 树**中，单击 `<div>A new element!?!</div>` 。</span><span class="sxs-lookup"><span data-stu-id="f2d30-233">In the **DOM Tree**, click `<div>A new element!?!</div>`.</span></span>  <span data-ttu-id="f2d30-234">DevTools 突出显示节点蓝色。</span><span class="sxs-lookup"><span data-stu-id="f2d30-234">DevTools highlights the node blue.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-delete1.msft.png" alt-text="完成的网站" lightbox="../media/beginners-html-delete1.msft.png":::
       <span data-ttu-id="f2d30-236">选择要删除的节点</span><span class="sxs-lookup"><span data-stu-id="f2d30-236">Selecting the node to be deleted</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="f2d30-237">按 `Delete` 键盘上的键。</span><span class="sxs-lookup"><span data-stu-id="f2d30-237">Press the `Delete` key on your keyboard.</span></span>  <span data-ttu-id="f2d30-238">将 `<div>A new element!?!</div>` 从您的 DOM 树中删除该节点。</span><span class="sxs-lookup"><span data-stu-id="f2d30-238">The `<div>A new element!?!</div>` node is removed from your DOM Tree.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-delete2.msft.png" alt-text="完成的网站" lightbox="../media/beginners-html-delete2.msft.png":::
       <span data-ttu-id="f2d30-240">该节点已被删除</span><span class="sxs-lookup"><span data-stu-id="f2d30-240">The node has been deleted</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="f2d30-241">复制更改</span><span class="sxs-lookup"><span data-stu-id="f2d30-241">Copy your changes</span></span>  

<span data-ttu-id="f2d30-242">即将完成。</span><span class="sxs-lookup"><span data-stu-id="f2d30-242">You're almost done.</span></span>  <span data-ttu-id="f2d30-243">你已在 DevTools 中对页面进行了一些更改，但这些更改尚未保存到你的源代码。</span><span class="sxs-lookup"><span data-stu-id="f2d30-243">You've made a few changes to your page in DevTools, but they're not yet saved to your source code.</span></span>  

1.  <span data-ttu-id="f2d30-244">刷新 **"实时" 选项卡**。 您在 DOM 树中所做的更改将消失。</span><span class="sxs-lookup"><span data-stu-id="f2d30-244">Refresh your **live tab**.  The changes that you made in the DOM Tree disappear.</span></span>  <span data-ttu-id="f2d30-245">特别是，文本 `Your site!` 返回页首，文本 `A new element!?!` 返回到底部的文本。</span><span class="sxs-lookup"><span data-stu-id="f2d30-245">In particular, the text `Your site!` returns to the top of the page, and the text `A new element!?!` returns to the bottom.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-copy1.msft.png" alt-text="完成的网站" lightbox="../media/beginners-html-copy1.msft.png":::
       <span data-ttu-id="f2d30-247">您所做的更改已丢失</span><span class="sxs-lookup"><span data-stu-id="f2d30-247">The changes that you've made are gone</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="f2d30-248">复制下面的代码。</span><span class="sxs-lookup"><span data-stu-id="f2d30-248">Copy the code below.</span></span>  
    
    ```html
    <!DOCTYPE html>
    <html lang="en">
        <head>
            <meta charset="utf-8">
            <meta http-equiv="X-UA-Compatible" content="IE=edge">
            <meta name="viewport" content="width=device-width, initial-scale=1">
        </head>
        <body>
            <header>
                <p>Welcome to my site!</p>
            </header>
            <nav>
                <ul>
                    <li><a href="/">Home</a></li>
                    <li><a href="/contact.html">Contact</a></li>
                </ul>
            </nav>
            <main>
                <h1>About Me</h1>
                <p>I am learning web development.  Recent accomplishments:</p>
                <ul>
                    <li>Learned how to set up my code in Glitch.</li>
                    <li>Added content to my HTML.</li>
                    <li>Learned how to use Microsoft Edge DevTools to experiment with content changes.</li>
                    <li>Learned the difference between HTML and the DOM.</li>
                </ul>
            </main>
        </body>
    </html>
    ```  
    
1.  <span data-ttu-id="f2d30-249">返回到 " **编辑器" 选项卡** ，并将您的 `index.html` 文件内容替换为您刚复制的代码。</span><span class="sxs-lookup"><span data-stu-id="f2d30-249">Go back to the **editor tab** and replace the contents of your `index.html` file with the code that you just copied.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-copy2.msft.png" alt-text="完成的网站" lightbox="../media/beginners-html-copy2.msft.png":::
       <span data-ttu-id="f2d30-251">文件的 `index.html` 外观</span><span class="sxs-lookup"><span data-stu-id="f2d30-251">How your `index.html` file should look</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="f2d30-252">后续步骤</span><span class="sxs-lookup"><span data-stu-id="f2d30-252">Next steps</span></span>  

*   <span data-ttu-id="f2d30-253">完成本系列中的下一个教程 " [开始使用 CSS][DevToolsBeginnersCss]"，了解如何在 Microsoft Edge DevTools 中对页面进行样式更改并试验样式更改。</span><span class="sxs-lookup"><span data-stu-id="f2d30-253">Complete the next tutorial in this series, [Get Started with CSS][DevToolsBeginnersCss], to learn how to style your page and experiment with style changes in Microsoft Edge DevTools.</span></span>  
*   <span data-ttu-id="f2d30-254">阅读 [对 dom 的介绍][MDNIntroductionDom] ，了解有关 DOM 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f2d30-254">Read [Introduction to the DOM][MDNIntroductionDom] to learn more about the DOM.</span></span>  
*   <span data-ttu-id="f2d30-255">查看类似 [于 Web 开发简介][CourseraIntroductionToWebDevelopment] 的课程，以获得更多动手的 web 开发体验。</span><span class="sxs-lookup"><span data-stu-id="f2d30-255">Check out a course like [Introduction to Web Development][CourseraIntroductionToWebDevelopment] to get more hands-on web development experience.</span></span>  

## <span data-ttu-id="f2d30-256">与 Microsoft Edge 开发人员工具团队联系</span><span class="sxs-lookup"><span data-stu-id="f2d30-256">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!--- links --->  

[DevToolsBeginnersCss]: ./css.md "初学者的 DevTools：开始使用 CSS |Microsoft 文档"  

[MicrosoftEdgeInsider]: https://www.microsoftedgeinsider.com "Microsoft Edge 预览体验成员"  

[CourseraIntroductionToWebDevelopment]: https://www.coursera.org/learn/web-development "Web 开发简介 |Coursera"  

[GlitchAlluringShockIndex]: https://glitch.com/edit/#!/alluring-shock?path=index.html "index.html alluring-电击 |故障"  

[MDNGettingStartedHtml]: https://developer.mozilla.org/docs/Learn/HTML/Introduction_to_HTML/Getting_started "HTML | 入门MDN"  
[MDNIntroductionDom]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model/Introduction "DOM 简介 |MDN"  

> [!NOTE]
> <span data-ttu-id="f2d30-263">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="f2d30-263">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="f2d30-264">原始页面位于 [此处](https://developers.google.com/web/tools/chrome-devtools/beginners/html) ，由 [Katherine 杰克逊][KatherineJackson] (技术编写器暂存，Chrome DevTools \ ) 。</span><span class="sxs-lookup"><span data-stu-id="f2d30-264">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/beginners/html) and is authored by [Katherine Jackson][KatherineJackson] \(Technical Writer Intern, Chrome DevTools\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="f2d30-266">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="f2d30-266">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[KatherineJackson]: https://developers.google.com/web/resources/contributors/katjackson  
