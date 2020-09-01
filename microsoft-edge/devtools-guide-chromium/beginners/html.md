---
title: 初学者的 DevTools： HTML 和 DOM 入门
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 50dfd8595c270a2532f55b71307b42c3636bba3c
ms.sourcegitcommit: 1251c555c6b4db8ef8187ed94d8832fdb89d03b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2020
ms.locfileid: "10982978"
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

# <span data-ttu-id="38f43-103">初学者的 DevTools： HTML 和 DOM 入门</span><span class="sxs-lookup"><span data-stu-id="38f43-103">DevTools for beginners: Get started with HTML and the DOM</span></span>   

<span data-ttu-id="38f43-104">这是介绍 web 开发基础知识的一系列教程中的第一项。</span><span class="sxs-lookup"><span data-stu-id="38f43-104">This is the first in a series of tutorials that teach you the basics of web development.</span></span>  <span data-ttu-id="38f43-105">你还将了解一组名为 Microsoft Edge DevTools 的 web 开发人员工具，这些工具可以提高工作效率。</span><span class="sxs-lookup"><span data-stu-id="38f43-105">You will also learn about a set of web developer tools called Microsoft Edge DevTools that can increase your productivity.</span></span>  

<span data-ttu-id="38f43-106">在本特定教程中，你将了解有关 HTML 和 DOM 的信息。</span><span class="sxs-lookup"><span data-stu-id="38f43-106">In this particular tutorial, you learn about HTML and the DOM.</span></span>  <span data-ttu-id="38f43-107">HTML 是 web 开发的核心技术之一。</span><span class="sxs-lookup"><span data-stu-id="38f43-107">HTML is one of the core technologies of web development.</span></span>  <span data-ttu-id="38f43-108">它是用于控制网页的结构和内容的语言。</span><span class="sxs-lookup"><span data-stu-id="38f43-108">It is the language that controls the structure and content of webpages.</span></span>  <span data-ttu-id="38f43-109">DOM 还与网页的结构和内容相关，但稍后你将了解更多相关信息。</span><span class="sxs-lookup"><span data-stu-id="38f43-109">The DOM is also related to the structure and content of webpages, but you'll learn more about that later.</span></span>  

## <span data-ttu-id="38f43-110">目标</span><span class="sxs-lookup"><span data-stu-id="38f43-110">Goals</span></span>   

<span data-ttu-id="38f43-111">您将通过实际构建自己的网站来了解 web 开发。</span><span class="sxs-lookup"><span data-stu-id="38f43-111">You are going to learn web development by actually building your own website.</span></span>  <span data-ttu-id="38f43-112">当您完成 *DevTools For 初学者* 系列中的所有教程时，完成的网站将如下图所示。</span><span class="sxs-lookup"><span data-stu-id="38f43-112">By the time you complete all of the tutorials in the *DevTools for Beginners* series, your finished site will look like in the following figure.</span></span>  

:::image type="complex" source="../media/beginners-html-finished.msft.png" alt-text="完成的网站" lightbox="../media/beginners-html-finished.msft.png":::
   <span data-ttu-id="38f43-114">完成的网站</span><span class="sxs-lookup"><span data-stu-id="38f43-114">The finished site</span></span>  
:::image-end:::  

<span data-ttu-id="38f43-115">本教程结束时，你将了解：</span><span class="sxs-lookup"><span data-stu-id="38f43-115">By the end of this tutorial, you will understand:</span></span>  

*   <span data-ttu-id="38f43-116">HTML 和 DOM 如何创建你在网页上看到的内容。</span><span class="sxs-lookup"><span data-stu-id="38f43-116">How HTML and the DOM create the content that you see on webpages.</span></span>  
*   <span data-ttu-id="38f43-117">Microsoft Edge DevTools 可如何帮助你体验 HTML 和 DOM 更改。</span><span class="sxs-lookup"><span data-stu-id="38f43-117">How Microsoft Edge DevTools can help you experiment with HTML and DOM changes.</span></span>  
*   <span data-ttu-id="38f43-118">HTML 和 DOM 之间的区别。</span><span class="sxs-lookup"><span data-stu-id="38f43-118">The difference between HTML and the DOM.</span></span>  

<span data-ttu-id="38f43-119">您还有一个真正的网站！</span><span class="sxs-lookup"><span data-stu-id="38f43-119">You'll also have a real website!</span></span>  <span data-ttu-id="38f43-120">你可以使用此网站主持你的简历或博客。</span><span class="sxs-lookup"><span data-stu-id="38f43-120">You can use this site to host your resume or blog.</span></span>  

## <span data-ttu-id="38f43-121">必备条件</span><span class="sxs-lookup"><span data-stu-id="38f43-121">Prerequisites</span></span>   

<span data-ttu-id="38f43-122">在尝试本教程之前，请完成以下先决条件：</span><span class="sxs-lookup"><span data-stu-id="38f43-122">Before attempting this tutorial, complete the following prerequisites:</span></span>  

*   <span data-ttu-id="38f43-123">如果您不熟悉 HTML，请阅读 [html][MDNGettingStartedHtml]入门。</span><span class="sxs-lookup"><span data-stu-id="38f43-123">If you are unfamiliar with HTML, read [Getting Started with HTML][MDNGettingStartedHtml].</span></span>  
*   <span data-ttu-id="38f43-124">下载 [Microsoft Edge][MicrosoftEdgeInsider] web 浏览器。</span><span class="sxs-lookup"><span data-stu-id="38f43-124">Download the [Microsoft Edge][MicrosoftEdgeInsider] web browser.</span></span>  <span data-ttu-id="38f43-125">本教程使用一组称为 Microsoft Edge DevTools 的 web 开发工具，这些工具内置于 Microsoft Edge 中。</span><span class="sxs-lookup"><span data-stu-id="38f43-125">This tutorial uses a set of web development tools, called the Microsoft Edge DevTools, that are built into Microsoft Edge.</span></span>  

## <span data-ttu-id="38f43-126">设置代码</span><span class="sxs-lookup"><span data-stu-id="38f43-126">Set up your code</span></span>   

<span data-ttu-id="38f43-127">您将在名为 "问题" 的联机代码编辑器中构建您的网站。</span><span class="sxs-lookup"><span data-stu-id="38f43-127">You are going to build your site in an online code editor called Glitch.</span></span>  

1.  <span data-ttu-id="38f43-128">打开 [源代码][GlitchAlluringShockIndex]。</span><span class="sxs-lookup"><span data-stu-id="38f43-128">Open the [source code][GlitchAlluringShockIndex].</span></span>  <span data-ttu-id="38f43-129">此选项卡将在本教程的整个教程中称为 " **编辑器" 选项** 卡。</span><span class="sxs-lookup"><span data-stu-id="38f43-129">This tab will be called the **editor tab** throughout this tutorial.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-setup1.msft.png" alt-text=""编辑器" 选项卡" lightbox="../media/beginners-html-setup1.msft.png":::
       <span data-ttu-id="38f43-131">"编辑器" 选项卡</span><span class="sxs-lookup"><span data-stu-id="38f43-131">The editor tab</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="38f43-132">单击 " **alluring"-电击**。</span><span class="sxs-lookup"><span data-stu-id="38f43-132">Click **alluring-shock**.</span></span>  <span data-ttu-id="38f43-133">将在左上角打开 "项目选项" 菜单。</span><span class="sxs-lookup"><span data-stu-id="38f43-133">The Project Options menu opens in the top-left corner.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-setup2.msft.png" alt-text=""项目选项" 菜单" lightbox="../media/beginners-html-setup2.msft.png":::
       <span data-ttu-id="38f43-135">"项目选项" 菜单</span><span class="sxs-lookup"><span data-stu-id="38f43-135">The Project Options menu</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="38f43-136">单击 " **Remix Project**"。</span><span class="sxs-lookup"><span data-stu-id="38f43-136">Click **Remix Project**.</span></span>  <span data-ttu-id="38f43-137">问题创建可编辑的项目副本，并随机为项目生成新名称。</span><span class="sxs-lookup"><span data-stu-id="38f43-137">Glitch creates a copy of the project that you can edit and randomly generates a new name for the project.</span></span>  <span data-ttu-id="38f43-138">内容与以前的内容相同。</span><span class="sxs-lookup"><span data-stu-id="38f43-138">The content is the same as before.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-setup3.msft.png" alt-text="Remixed 项目" lightbox="../media/beginners-html-setup3.msft.png":::
       <span data-ttu-id="38f43-140">Remixed 项目</span><span class="sxs-lookup"><span data-stu-id="38f43-140">The remixed project</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="38f43-141">如果您计划完成本系列中的下一个教程，请单击您的 GitHub 或 Facebook 帐户 **登录** 并登录问题。</span><span class="sxs-lookup"><span data-stu-id="38f43-141">If you plan on completing the next tutorial in this series, click **Sign In** and sign in to Glitch with your GitHub or Facebook account.</span></span>  <span data-ttu-id="38f43-142">如果您不登录，一旦关闭 "编辑" 选项卡，您将失去编辑此项目的功能。</span><span class="sxs-lookup"><span data-stu-id="38f43-142">If you don't sign in you will lose the ability to edit this project once you close the editing tab.</span></span>  
1.  <span data-ttu-id="38f43-143">单击 " **显示** "，然后 **在新窗口中**选择。</span><span class="sxs-lookup"><span data-stu-id="38f43-143">Click **Show** and select **In a New Window**.</span></span>  <span data-ttu-id="38f43-144">将打开一个新的选项卡，显示实时页面。</span><span class="sxs-lookup"><span data-stu-id="38f43-144">A new tab opens, showing you the live page.</span></span>  <span data-ttu-id="38f43-145">此选项卡将在整个教程中称为 " **实时" 选项卡** 。</span><span class="sxs-lookup"><span data-stu-id="38f43-145">This tab will be called the **live tab** throughout this tutorial.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-setup4.msft.png" alt-text=""实时" 选项卡" lightbox="../media/beginners-html-setup4.msft.png":::
       <span data-ttu-id="38f43-147">"实时" 选项卡</span><span class="sxs-lookup"><span data-stu-id="38f43-147">The live tab</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="38f43-148">添加内容</span><span class="sxs-lookup"><span data-stu-id="38f43-148">Add content</span></span>   

<span data-ttu-id="38f43-149">您的网站非常空。</span><span class="sxs-lookup"><span data-stu-id="38f43-149">Your site is pretty empty.</span></span>  <span data-ttu-id="38f43-150">请按照以下步骤将一些内容添加到！</span><span class="sxs-lookup"><span data-stu-id="38f43-150">Follow the steps below to add some content to it!</span></span>  

1.  <span data-ttu-id="38f43-151">在 " **编辑器" 选项卡**中，"替换 `<!-- You're "About Me" will go here.  -->` 为" `<h1>About Me</h1>` 。</span><span class="sxs-lookup"><span data-stu-id="38f43-151">In the **editor tab**, replace `<!-- You're "About Me" will go here.  -->` with `<h1>About Me</h1>`.</span></span>  
    
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
          :::image type="complex" source="../media/beginners-html-add1.msft.png" alt-text="新代码在 "编辑器" 选项卡中突出显示" lightbox="../media/beginners-html-add1.msft.png":::
             <span data-ttu-id="38f43-153">新代码在 "编辑器" 选项卡中突出显示</span><span class="sxs-lookup"><span data-stu-id="38f43-153">The new code is highlighted in the editor tab</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::
    
1.  <span data-ttu-id="38f43-154">在 " **实时" 选项卡**中查看所做的更改。 文本 `About Me` 显示在页面上。</span><span class="sxs-lookup"><span data-stu-id="38f43-154">View your changes in the **live tab**.  The text `About Me` is visible on the page.</span></span>  <span data-ttu-id="38f43-155">它比其余文本更大，因为该 `<h1>` 元素表示节标题。</span><span class="sxs-lookup"><span data-stu-id="38f43-155">It's larger than the rest of the text, because the `<h1>` element represents a section heading.</span></span>  <span data-ttu-id="38f43-156">Web 浏览器会自动以较大字体调整标题样式。</span><span class="sxs-lookup"><span data-stu-id="38f43-156">Your web browser automatically styles headings in larger font sizes.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-add2.msft.png" alt-text="新标题在 "实时" 选项卡中可见" lightbox="../media/beginners-html-add2.msft.png":::
       <span data-ttu-id="38f43-158">新标题在 "实时" 选项卡中可见</span><span class="sxs-lookup"><span data-stu-id="38f43-158">The new heading is visible in the live tab</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="38f43-159">返回到 " **编辑器" 选项卡**，在 `<p>I am learning HTML.  Recent accomplishments:</p>` 您刚放置的位置下方的行中插入 `<h1>About Me</h1>` 。</span><span class="sxs-lookup"><span data-stu-id="38f43-159">Back in the **editor tab**, insert `<p>I am learning HTML.  Recent accomplishments:</p>` on the line below where you just put `<h1>About Me</h1>`.</span></span>  
    
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
          :::image type="complex" source="../media/beginners-html-add3.msft.png" alt-text="新代码在 "编辑器" 选项卡中突出显示" lightbox="../media/beginners-html-add3.msft.png":::
             <span data-ttu-id="38f43-161">新代码在 "编辑器" 选项卡中突出显示</span><span class="sxs-lookup"><span data-stu-id="38f43-161">The new code is highlighted in the editor tab</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::
    
1.  <span data-ttu-id="38f43-162">在 " **实时" 选项卡**中查看您的更改。</span><span class="sxs-lookup"><span data-stu-id="38f43-162">View your change in the **live tab**.</span></span>  
1.  <span data-ttu-id="38f43-163">返回到 " **编辑器" 选项卡**，添加你的成就列表：</span><span class="sxs-lookup"><span data-stu-id="38f43-163">Back in the **editor tab**, add a list of your accomplishments:</span></span>  
    
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
          :::image type="complex" source="../media/beginners-html-add4.msft.png" alt-text="新代码在 "编辑器" 选项卡中突出显示" lightbox="../media/beginners-html-add4.msft.png":::
             <span data-ttu-id="38f43-165">新代码在 "编辑器" 选项卡中突出显示</span><span class="sxs-lookup"><span data-stu-id="38f43-165">The new code is highlighted in the editor tab</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
1.  <span data-ttu-id="38f43-166">再次返回 " **实时" 选项卡** ，确保新内容正确显示。</span><span class="sxs-lookup"><span data-stu-id="38f43-166">Again, go back to the **live tab** to make sure that the new content is displaying correctly.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-add5.msft.png" alt-text="新列表在 "实时" 选项卡中可见" lightbox="../media/beginners-html-add5.msft.png":::
       <span data-ttu-id="38f43-168">新列表在 "实时" 选项卡中可见</span><span class="sxs-lookup"><span data-stu-id="38f43-168">The new list is visible in the live tab</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="38f43-169">在 Microsoft Edge DevTools 中试用内容更改</span><span class="sxs-lookup"><span data-stu-id="38f43-169">Experiment with content changes in Microsoft Edge DevTools</span></span>   

<span data-ttu-id="38f43-170">如果你正在开发一个包含大量 HTML 的大型页面，你可以想像，在 "编辑器" 选项卡和 "实时" 选项卡之间来回切换以查看你的更改，尤其是当你不确定要在页面上放置哪些内容时。</span><span class="sxs-lookup"><span data-stu-id="38f43-170">If you were developing a big page with a lot of HTML, you can imagine that it might be somewhat tedious to go back-and-forth between the editor tab and the live tab hundreds of times in order to see your changes, especially if you weren't sure what exactly to put on the page.</span></span>  <span data-ttu-id="38f43-171">Microsoft Edge DevTools 可帮助你在不离开 "实时" 选项卡的情况下试用内容更改。</span><span class="sxs-lookup"><span data-stu-id="38f43-171">Microsoft Edge DevTools can help you experiment with content changes without ever leaving the live tab.</span></span>  

### <span data-ttu-id="38f43-172">了解 HTML 和 DOM 之间的区别</span><span class="sxs-lookup"><span data-stu-id="38f43-172">Learn the difference between HTML and the DOM</span></span>   

<span data-ttu-id="38f43-173">开始从 Microsoft Edge DevTools 编辑内容之前，了解 HTML 和 DOM 之间的区别很有帮助。</span><span class="sxs-lookup"><span data-stu-id="38f43-173">Before you start editing your content from Microsoft Edge DevTools, it's helpful to understand the difference between HTML and the DOM.</span></span>  <span data-ttu-id="38f43-174">例如，学习的最佳方式是：</span><span class="sxs-lookup"><span data-stu-id="38f43-174">The best way to learn is by example:</span></span>  

1.  <span data-ttu-id="38f43-175">转到 " **实时" 选项卡**。 在页面底部看到文本 `A new element!?!` 。</span><span class="sxs-lookup"><span data-stu-id="38f43-175">Go to the **live tab**.  At the bottom of your page you see the text `A new element!?!`.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-dom1.msft.png" alt-text="在页面底部，新元素的文本!?! 可以看到" lightbox="../media/beginners-html-dom1.msft.png":::
       <span data-ttu-id="38f43-178">在页面底部，新元素的文本!?!</span><span class="sxs-lookup"><span data-stu-id="38f43-178">At the bottom of the page the text A new element!?!</span></span> <span data-ttu-id="38f43-179">可以看到</span><span class="sxs-lookup"><span data-stu-id="38f43-179">can be seen</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="38f43-180">返回到 " **编辑器" 选项卡** ，然后尝试在中查找此文本 `index.html` 。</span><span class="sxs-lookup"><span data-stu-id="38f43-180">Go back to the **editor tab** and try to find this text in `index.html`.</span></span>  <span data-ttu-id="38f43-181">不在这里！</span><span class="sxs-lookup"><span data-stu-id="38f43-181">It's not there!</span></span>  
    
    :::image type="complex" source="../media/beginners-html-dom2.msft.png" alt-text="新元素!?! 的神秘文本 在 index.html 中找不到任何地方" lightbox="../media/beginners-html-dom2.msft.png":::
       <span data-ttu-id="38f43-184">`A new element!?!`无法在中找到神秘的文本</span><span class="sxs-lookup"><span data-stu-id="38f43-184">The mystery text `A new element!?!` is nowhere to be found in</span></span> `index.html`  
    :::image-end:::  
    
1.  <span data-ttu-id="38f43-185">返回到 " **实时" 选项卡**，右键单击 `A new element!?!` ，然后选择 " **检查**"。</span><span class="sxs-lookup"><span data-stu-id="38f43-185">Go back to the **live tab**, right-click `A new element!?!`, and select **Inspect**.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-dom3.msft.png" alt-text="检查某些文本" lightbox="../media/beginners-html-dom3.msft.png":::
       <span data-ttu-id="38f43-187">检查某些文本</span><span class="sxs-lookup"><span data-stu-id="38f43-187">Inspecting some text</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="38f43-188">DevTools 将在您的页面旁打开。</span><span class="sxs-lookup"><span data-stu-id="38f43-188">DevTools opens up alongside your page.</span></span>  `<div>A new element!?!</div>` <span data-ttu-id="38f43-189">将突出显示蓝色。</span><span class="sxs-lookup"><span data-stu-id="38f43-189">is highlighted blue.</span></span>  <span data-ttu-id="38f43-190">虽然 DevTools 中的此结构看起来像是 HTML，但实际上它是 **DOM 树**。</span><span class="sxs-lookup"><span data-stu-id="38f43-190">Although this structure in DevTools looks like your HTML, it is actually the **DOM Tree**.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-dom4.msft.png" alt-text="DevTools 在页面旁打开" lightbox="../media/beginners-html-dom4.msft.png":::
       <span data-ttu-id="38f43-192">DevTools 在页面旁打开</span><span class="sxs-lookup"><span data-stu-id="38f43-192">DevTools is open alongside the page</span></span>  
    :::image-end:::  
    
<span data-ttu-id="38f43-193">加载页面时，浏览器将获取 HTML 以创建页面的 *初始* 内容。</span><span class="sxs-lookup"><span data-stu-id="38f43-193">When your page loads, the browser takes your HTML to create the *initial* content of the page.</span></span>  <span data-ttu-id="38f43-194">DOM 表示页面的 *当前* 内容，它可能会随着时间的推移而更改。</span><span class="sxs-lookup"><span data-stu-id="38f43-194">The DOM represents the *current* content of the page, which can change over time.</span></span>  <span data-ttu-id="38f43-195">`<div>A new element!?!</div>`由于 HTML 底部的标记，可将神秘的内容添加到页面中 `<script src="new.js"></script>` 。</span><span class="sxs-lookup"><span data-stu-id="38f43-195">The mysterious `<div>A new element!?!</div>` content is added to your page because of the `<script src="new.js"></script>` tag at the bottom of your HTML.</span></span>  <span data-ttu-id="38f43-196">此标记会导致运行某些 JavaScript 代码。</span><span class="sxs-lookup"><span data-stu-id="38f43-196">This tag causes some JavaScript code to run.</span></span>  <span data-ttu-id="38f43-197">在后面的教程中，你将了解有关 JavaScript 的详细信息，但现在将其视为可更改你的页面内容的编程语言。</span><span class="sxs-lookup"><span data-stu-id="38f43-197">You'll learn more about JavaScript in a later tutorial, but for now think of it as a programming language that can change the content of your page.</span></span>  <span data-ttu-id="38f43-198">在此特定情况下，JavaScript 代码将添加 `<div>A new element!?!</div>` 到您的页面。</span><span class="sxs-lookup"><span data-stu-id="38f43-198">In this particular case, JavaScript code adds `<div>A new element!?!</div>` to your page.</span></span>  <span data-ttu-id="38f43-199">这就是您的实时页面（而不是 HTML）中显示此神秘文本的原因。</span><span class="sxs-lookup"><span data-stu-id="38f43-199">That is why this mystery text is visible on your live page, but not in your HTML.</span></span>  

### <span data-ttu-id="38f43-200">编辑 DOM</span><span class="sxs-lookup"><span data-stu-id="38f43-200">Edit the DOM</span></span>   

<span data-ttu-id="38f43-201">如果想要快速试用内容更改而又不离开 "实时" 选项卡，请尝试 DevTools。</span><span class="sxs-lookup"><span data-stu-id="38f43-201">If you want to quickly experiment with content changes without ever leaving the live tab, try DevTools.</span></span>  

1.  <span data-ttu-id="38f43-202">在 DevTools 中，右键单击 `Your site!` 并选择 " **编辑为 HTML**"。</span><span class="sxs-lookup"><span data-stu-id="38f43-202">In DevTools, right-click `Your site!` and select **Edit as HTML**.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-edit1.msft.png" alt-text="将节点编辑为 HTML" lightbox="../media/beginners-html-edit1.msft.png":::
       <span data-ttu-id="38f43-204">将节点编辑为 HTML</span><span class="sxs-lookup"><span data-stu-id="38f43-204">Editing the node as HTML</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="38f43-205">替换 `<p>Your site!</p>` 为以下代码。</span><span class="sxs-lookup"><span data-stu-id="38f43-205">Replace `<p>Your site!</p>` with the code below.</span></span>  
    
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
          :::image type="complex" source="../media/beginners-html-edit2.msft.png" alt-text="将节点编辑为 HTML" lightbox="../media/beginners-html-edit2.msft.png":::
             <span data-ttu-id="38f43-207">将节点编辑为 HTML</span><span class="sxs-lookup"><span data-stu-id="38f43-207">Editing the node as HTML</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
1.  <span data-ttu-id="38f43-208">按 `Control` + `Enter` \ (Windows \ ) 或 `Command` + `Enter` \ (macOS \ ) 保存所做的更改，或在框外单击。</span><span class="sxs-lookup"><span data-stu-id="38f43-208">Press `Control`+`Enter` \(Windows\) or `Command`+`Enter` \(macOS\) to save your changes, or click outside of the box.</span></span>  <span data-ttu-id="38f43-209">您的更改会自动显示在您的页面的实时视图中。</span><span class="sxs-lookup"><span data-stu-id="38f43-209">Your changes automatically show up in the live view of your page.</span></span>  <span data-ttu-id="38f43-210">文本已 `Your site!` 替换为新内容。</span><span class="sxs-lookup"><span data-stu-id="38f43-210">The text `Your site!` has been replaced with the new content.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-edit3.msft.png" alt-text="新内容将立即显示在页面上" lightbox="../media/beginners-html-edit3.msft.png":::
       <span data-ttu-id="38f43-212">新内容将立即显示在页面上</span><span class="sxs-lookup"><span data-stu-id="38f43-212">The new content shows up immediately on the page</span></span>  
    :::image-end:::  
    
<span data-ttu-id="38f43-213">此工作流仅适用于试用内容更改。</span><span class="sxs-lookup"><span data-stu-id="38f43-213">This workflow is only good for experimenting with content changes.</span></span>  <span data-ttu-id="38f43-214">如果重新加载页面或关闭选项卡，所做的更改将永久消失。</span><span class="sxs-lookup"><span data-stu-id="38f43-214">If you reload the page or close the tab, your changes will be gone forever.</span></span>  <span data-ttu-id="38f43-215">如果您使用的是此工作流，而您想要保存所做的更改，您需要手动将这些更改复制到您的 HTML 中。</span><span class="sxs-lookup"><span data-stu-id="38f43-215">If you're using this workflow and you want to save your changes, you need to manually copy those changes over to your HTML.</span></span>  <span data-ttu-id="38f43-216">接下来的几个部分介绍了一些可用于更改 DOM 树内容的更多方法。</span><span class="sxs-lookup"><span data-stu-id="38f43-216">The next couple of sections show you some more ways that you can change content from the DOM Tree.</span></span>  

## <span data-ttu-id="38f43-217">重新排序节点</span><span class="sxs-lookup"><span data-stu-id="38f43-217">Reorder nodes</span></span>   

<span data-ttu-id="38f43-218">你还可以更改 DOM 节点的顺序。</span><span class="sxs-lookup"><span data-stu-id="38f43-218">You can also change the order of DOM nodes.</span></span>  <span data-ttu-id="38f43-219">例如，在网页上，导航菜单位于底部附近。</span><span class="sxs-lookup"><span data-stu-id="38f43-219">For example, on your web page the navigation menu is near the bottom.</span></span>  <span data-ttu-id="38f43-220">将其移动到顶部：</span><span class="sxs-lookup"><span data-stu-id="38f43-220">To move it to the top:</span></span>  

1.  <span data-ttu-id="38f43-221">`<nav>`在 DevTools 的**DOM 树**中查找节点。</span><span class="sxs-lookup"><span data-stu-id="38f43-221">Find the `<nav>` node in the **DOM Tree** of DevTools.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-reorder1.msft.png" alt-text="导航节点在 DevTools 中突出显示蓝色" lightbox="../media/beginners-html-reorder1.msft.png":::
       <span data-ttu-id="38f43-223">导航节点在 DevTools 中突出显示蓝色</span><span class="sxs-lookup"><span data-stu-id="38f43-223">The nav node is highlighted blue in DevTools</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="38f43-224">将 `<nav>` 节点拖到顶部，使其成为节点下方的第一个子级 `<body>` 。</span><span class="sxs-lookup"><span data-stu-id="38f43-224">Drag the `<nav>` node to the top, so that it's the first child below the `<body>` node.</span></span>  
    
    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/beginners-html-reorder2.msft.png" alt-text="将导航节点拖动到顶部" lightbox="../media/beginners-html-reorder2.msft.png":::
             <span data-ttu-id="38f43-226">将导航节点拖动到顶部</span><span class="sxs-lookup"><span data-stu-id="38f43-226">Dragging the nav node to the top</span></span>  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          <span data-ttu-id="38f43-227">`<nav>`现在，节点显示在您的页面顶部。</span><span class="sxs-lookup"><span data-stu-id="38f43-227">The `<nav>` node is now displaying at the top of your page.</span></span>  
          
          :::image type="complex" source="../media/beginners-html-reorder3.msft.png" alt-text="导航节点位于页面顶部" lightbox="../media/beginners-html-reorder3.msft.png":::
             <span data-ttu-id="38f43-229">导航节点位于页面顶部</span><span class="sxs-lookup"><span data-stu-id="38f43-229">The nav node is at the top of the page</span></span>  
          :::image-end:::  
       :::column-end:::
   :::row-end:::  
    
### <span data-ttu-id="38f43-230">删除节点</span><span class="sxs-lookup"><span data-stu-id="38f43-230">Delete a node</span></span>   

<span data-ttu-id="38f43-231">您也可以从 DOM 树中删除节点。</span><span class="sxs-lookup"><span data-stu-id="38f43-231">You can also remove nodes from the DOM Tree.</span></span>  

1.  <span data-ttu-id="38f43-232">在 **DOM 树**中，单击 `<div>A new element!?!</div>` 。</span><span class="sxs-lookup"><span data-stu-id="38f43-232">In the **DOM Tree**, click `<div>A new element!?!</div>`.</span></span>  <span data-ttu-id="38f43-233">DevTools 突出显示节点蓝色。</span><span class="sxs-lookup"><span data-stu-id="38f43-233">DevTools highlights the node blue.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-delete1.msft.png" alt-text="选择要删除的节点" lightbox="../media/beginners-html-delete1.msft.png":::
       <span data-ttu-id="38f43-235">选择要删除的节点</span><span class="sxs-lookup"><span data-stu-id="38f43-235">Selecting the node to be deleted</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="38f43-236">按 `Delete` 键盘上的键。</span><span class="sxs-lookup"><span data-stu-id="38f43-236">Press the `Delete` key on your keyboard.</span></span>  <span data-ttu-id="38f43-237">将 `<div>A new element!?!</div>` 从您的 DOM 树中删除该节点。</span><span class="sxs-lookup"><span data-stu-id="38f43-237">The `<div>A new element!?!</div>` node is removed from your DOM Tree.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-delete2.msft.png" alt-text="该节点已被删除" lightbox="../media/beginners-html-delete2.msft.png":::
       <span data-ttu-id="38f43-239">该节点已被删除</span><span class="sxs-lookup"><span data-stu-id="38f43-239">The node has been deleted</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="38f43-240">复制更改</span><span class="sxs-lookup"><span data-stu-id="38f43-240">Copy your changes</span></span>   

<span data-ttu-id="38f43-241">即将完成。</span><span class="sxs-lookup"><span data-stu-id="38f43-241">You're almost done.</span></span>  <span data-ttu-id="38f43-242">你已在 DevTools 中对页面进行了一些更改，但这些更改尚未保存到你的源代码。</span><span class="sxs-lookup"><span data-stu-id="38f43-242">You've made a few changes to your page in DevTools, but they're not yet saved to your source code.</span></span>  

1.  <span data-ttu-id="38f43-243">刷新 **"实时" 选项卡**。 您在 DOM 树中所做的更改将消失。</span><span class="sxs-lookup"><span data-stu-id="38f43-243">Refresh your **live tab**.  The changes that you made in the DOM Tree disappear.</span></span>  <span data-ttu-id="38f43-244">特别是，文本 `Your site!` 返回页首，文本 `A new element!?!` 返回到底部的文本。</span><span class="sxs-lookup"><span data-stu-id="38f43-244">In particular, the text `Your site!` returns to the top of the page, and the text `A new element!?!` returns to the bottom.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-copy1.msft.png" alt-text="您所做的更改已丢失" lightbox="../media/beginners-html-copy1.msft.png":::
       <span data-ttu-id="38f43-246">您所做的更改已丢失</span><span class="sxs-lookup"><span data-stu-id="38f43-246">The changes that you've made are gone</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="38f43-247">复制下面的代码。</span><span class="sxs-lookup"><span data-stu-id="38f43-247">Copy the code below.</span></span>  
    
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
    
1.  <span data-ttu-id="38f43-248">返回到 " **编辑器" 选项卡** ，并将您的 `index.html` 文件内容替换为您刚复制的代码。</span><span class="sxs-lookup"><span data-stu-id="38f43-248">Go back to the **editor tab** and replace the contents of your `index.html` file with the code that you just copied.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-copy2.msft.png" alt-text="index.html 文件的外观" lightbox="../media/beginners-html-copy2.msft.png":::
       <span data-ttu-id="38f43-250">文件的 `index.html` 外观</span><span class="sxs-lookup"><span data-stu-id="38f43-250">How your `index.html` file should look</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="38f43-251">后续步骤</span><span class="sxs-lookup"><span data-stu-id="38f43-251">Next steps</span></span>   

*   <span data-ttu-id="38f43-252">完成本系列中的下一个教程 " [开始使用 CSS][DevToolsBeginnersCss]"，了解如何在 Microsoft Edge DevTools 中对页面进行样式更改并试验样式更改。</span><span class="sxs-lookup"><span data-stu-id="38f43-252">Complete the next tutorial in this series, [Get Started with CSS][DevToolsBeginnersCss], to learn how to style your page and experiment with style changes in Microsoft Edge DevTools.</span></span>  
*   <span data-ttu-id="38f43-253">阅读 [对 dom 的介绍][MDNIntroductionDom] ，了解有关 DOM 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="38f43-253">Read [Introduction to the DOM][MDNIntroductionDom] to learn more about the DOM.</span></span>  
*   <span data-ttu-id="38f43-254">查看类似 [于 Web 开发简介][CourseraIntroductionToWebDevelopment] 的课程，以获得更多动手的 web 开发体验。</span><span class="sxs-lookup"><span data-stu-id="38f43-254">Check out a course like [Introduction to Web Development][CourseraIntroductionToWebDevelopment] to get more hands-on web development experience.</span></span>  

<!--- links --->  

[DevToolsBeginnersCss]: ./css.md "初学者的 DevTools：开始使用 CSS |Microsoft 文档"  

[MicrosoftEdgeInsider]: https://www.microsoftedgeinsider.com "Microsoft Edge 预览体验成员"  

[CourseraIntroductionToWebDevelopment]: https://www.coursera.org/learn/web-development "Web 开发简介 |Coursera"  

[GlitchAlluringShockIndex]: https://glitch.com/edit/#!/alluring-shock?path=index.html "index.html alluring-电击 |故障"  

[MDNGettingStartedHtml]: https://developer.mozilla.org/docs/Learn/HTML/Introduction_to_HTML/Getting_started "HTML | 入门MDN"  
[MDNIntroductionDom]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model/Introduction "DOM 简介 |MDN"  

> [!NOTE]
> <span data-ttu-id="38f43-261">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="38f43-261">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="38f43-262">原始页面位于 [此处](https://developers.google.com/web/tools/chrome-devtools/beginners/html) ，由 [Katherine 杰克逊][KatherineJackson] (技术编写器暂存，Chrome DevTools \ ) 。</span><span class="sxs-lookup"><span data-stu-id="38f43-262">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/beginners/html) and is authored by [Katherine Jackson][KatherineJackson] \(Technical Writer Intern, Chrome DevTools\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="38f43-264">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="38f43-264">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[KatherineJackson]: https://developers.google.com/web/resources/contributors/katjackson  
