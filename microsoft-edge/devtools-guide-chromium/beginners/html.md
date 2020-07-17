---
title: 初学者的 DevTools： HTML 和 DOM 入门
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/16/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: d992a6ca68de07c879ca8e319ee6c22782924a6b
ms.sourcegitcommit: a06c86ef7c69e1e400a0be5938449f3c4ba6ec72
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/16/2020
ms.locfileid: "10882728"
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

# <span data-ttu-id="00c55-103">初学者的 DevTools： HTML 和 DOM 入门</span><span class="sxs-lookup"><span data-stu-id="00c55-103">DevTools for beginners: Get started with HTML and the DOM</span></span>   

<span data-ttu-id="00c55-104">这是介绍 web 开发基础知识的一系列教程中的第一项。</span><span class="sxs-lookup"><span data-stu-id="00c55-104">This is the first in a series of tutorials that teach you the basics of web development.</span></span>  <span data-ttu-id="00c55-105">你还将了解一组名为 Microsoft Edge DevTools 的 web 开发人员工具，这些工具可以提高工作效率。</span><span class="sxs-lookup"><span data-stu-id="00c55-105">You will also learn about a set of web developer tools called Microsoft Edge DevTools that can increase your productivity.</span></span>  

<span data-ttu-id="00c55-106">在本特定教程中，你将了解有关 HTML 和 DOM 的信息。</span><span class="sxs-lookup"><span data-stu-id="00c55-106">In this particular tutorial, you learn about HTML and the DOM.</span></span>  <span data-ttu-id="00c55-107">HTML 是 web 开发的核心技术之一。</span><span class="sxs-lookup"><span data-stu-id="00c55-107">HTML is one of the core technologies of web development.</span></span>  <span data-ttu-id="00c55-108">它是用于控制网页的结构和内容的语言。</span><span class="sxs-lookup"><span data-stu-id="00c55-108">It is the language that controls the structure and content of webpages.</span></span>  <span data-ttu-id="00c55-109">DOM 还与网页的结构和内容相关，但稍后你将了解更多相关信息。</span><span class="sxs-lookup"><span data-stu-id="00c55-109">The DOM is also related to the structure and content of webpages, but you'll learn more about that later.</span></span>  

## <span data-ttu-id="00c55-110">目标</span><span class="sxs-lookup"><span data-stu-id="00c55-110">Goals</span></span>   

<span data-ttu-id="00c55-111">您将通过实际构建自己的网站来了解 web 开发。</span><span class="sxs-lookup"><span data-stu-id="00c55-111">You are going to learn web development by actually building your own website.</span></span>  <span data-ttu-id="00c55-112">当您完成*DevTools For 初学者*系列中的所有教程时，完成的网站将如下**图 1**所示。</span><span class="sxs-lookup"><span data-stu-id="00c55-112">By the time you complete all of the tutorials in the *DevTools for Beginners* series, your finished site will look like **Figure 1**.</span></span>  

> ##### <span data-ttu-id="00c55-113">图 1</span><span class="sxs-lookup"><span data-stu-id="00c55-113">Figure 1</span></span>  
> <span data-ttu-id="00c55-114">完成的网站</span><span class="sxs-lookup"><span data-stu-id="00c55-114">The finished site</span></span>  
> ![完成的网站][ImageHtmlFinished]  

<span data-ttu-id="00c55-116">本教程结束时，你将了解：</span><span class="sxs-lookup"><span data-stu-id="00c55-116">By the end of this tutorial, you will understand:</span></span>  

*   <span data-ttu-id="00c55-117">HTML 和 DOM 如何创建你在网页上看到的内容。</span><span class="sxs-lookup"><span data-stu-id="00c55-117">How HTML and the DOM create the content that you see on webpages.</span></span>  
*   <span data-ttu-id="00c55-118">Microsoft Edge DevTools 可如何帮助你体验 HTML 和 DOM 更改。</span><span class="sxs-lookup"><span data-stu-id="00c55-118">How Microsoft Edge DevTools can help you experiment with HTML and DOM changes.</span></span>  
*   <span data-ttu-id="00c55-119">HTML 和 DOM 之间的区别。</span><span class="sxs-lookup"><span data-stu-id="00c55-119">The difference between HTML and the DOM.</span></span>  

<span data-ttu-id="00c55-120">您还有一个真正的网站！</span><span class="sxs-lookup"><span data-stu-id="00c55-120">You'll also have a real website!</span></span>  <span data-ttu-id="00c55-121">你可以使用此网站主持你的简历或博客。</span><span class="sxs-lookup"><span data-stu-id="00c55-121">You can use this site to host your resume or blog.</span></span>  

## <span data-ttu-id="00c55-122">必备条件</span><span class="sxs-lookup"><span data-stu-id="00c55-122">Prerequisites</span></span>   

<span data-ttu-id="00c55-123">在尝试本教程之前，请完成以下先决条件：</span><span class="sxs-lookup"><span data-stu-id="00c55-123">Before attempting this tutorial, complete the following prerequisites:</span></span>  

*   <span data-ttu-id="00c55-124">如果您不熟悉 HTML，请阅读[html][MDNGettingStartedHtml]入门。</span><span class="sxs-lookup"><span data-stu-id="00c55-124">If you're unfamiliar with HTML, read [Getting Started with HTML][MDNGettingStartedHtml].</span></span>  
*   <span data-ttu-id="00c55-125">下载[Microsoft Edge][MicrosoftEdgeInsider] web 浏览器。</span><span class="sxs-lookup"><span data-stu-id="00c55-125">Download the [Microsoft Edge][MicrosoftEdgeInsider] web browser.</span></span>  <span data-ttu-id="00c55-126">本教程使用一组称为 Microsoft Edge DevTools 的 web 开发工具，这些工具内置于 Microsoft Edge 中。</span><span class="sxs-lookup"><span data-stu-id="00c55-126">This tutorial uses a set of web development tools, called the Microsoft Edge DevTools, that are built into Microsoft Edge.</span></span>  

## <span data-ttu-id="00c55-127">设置代码</span><span class="sxs-lookup"><span data-stu-id="00c55-127">Set up your code</span></span>   

<span data-ttu-id="00c55-128">您将在名为 "问题" 的联机代码编辑器中构建您的网站。</span><span class="sxs-lookup"><span data-stu-id="00c55-128">You're going to build your site in an online code editor called Glitch.</span></span>  

1.  <span data-ttu-id="00c55-129">打开[源代码][GlitchAlluringShockIndex]。</span><span class="sxs-lookup"><span data-stu-id="00c55-129">Open the [source code][GlitchAlluringShockIndex].</span></span>  <span data-ttu-id="00c55-130">此选项卡将在本教程的整个教程中称为 "**编辑器" 选项**卡。</span><span class="sxs-lookup"><span data-stu-id="00c55-130">This tab will be called the **editor tab** throughout this tutorial.</span></span>  
    > ##### <span data-ttu-id="00c55-131">图 2</span><span class="sxs-lookup"><span data-stu-id="00c55-131">Figure 2</span></span>  
    > <span data-ttu-id="00c55-132">"编辑器" 选项卡</span><span class="sxs-lookup"><span data-stu-id="00c55-132">The editor tab</span></span>  
    > !["编辑器" 选项卡][ImageHtmlSetup1]  

1.  <span data-ttu-id="00c55-134">单击 " **alluring"-电击**。</span><span class="sxs-lookup"><span data-stu-id="00c55-134">Click **alluring-shock**.</span></span>  <span data-ttu-id="00c55-135">将在左上角打开 "项目选项" 菜单。</span><span class="sxs-lookup"><span data-stu-id="00c55-135">The Project Options menu opens in the top-left corner.</span></span>  
    
    > #### <span data-ttu-id="00c55-136">图 3</span><span class="sxs-lookup"><span data-stu-id="00c55-136">Figure 3</span></span>  
    > <span data-ttu-id="00c55-137">"项目选项" 菜单</span><span class="sxs-lookup"><span data-stu-id="00c55-137">The Project Options menu</span></span>  
    > !["项目选项" 菜单][ImageHtmlSetup2]  
    
1.  <span data-ttu-id="00c55-139">单击 " **Remix Project**"。</span><span class="sxs-lookup"><span data-stu-id="00c55-139">Click **Remix Project**.</span></span>  <span data-ttu-id="00c55-140">问题创建可编辑的项目副本，并随机为项目生成新名称。</span><span class="sxs-lookup"><span data-stu-id="00c55-140">Glitch creates a copy of the project that you can edit and randomly generates a new name for the project.</span></span>  <span data-ttu-id="00c55-141">内容与以前的内容相同。</span><span class="sxs-lookup"><span data-stu-id="00c55-141">The content is the same as before.</span></span>  
    
    > ##### <span data-ttu-id="00c55-142">图 4</span><span class="sxs-lookup"><span data-stu-id="00c55-142">Figure 4</span></span>  
    > <span data-ttu-id="00c55-143">Remixed 项目</span><span class="sxs-lookup"><span data-stu-id="00c55-143">The remixed project</span></span>  
    > ![Remixed 项目][ImageHtmlSetup3]  
    
1.  <span data-ttu-id="00c55-145">如果您计划完成本系列中的下一个教程，请单击您的 GitHub 或 Facebook 帐户**登录**并登录问题。</span><span class="sxs-lookup"><span data-stu-id="00c55-145">If you plan on completing the next tutorial in this series, click **Sign In** and sign in to Glitch with your GitHub or Facebook account.</span></span>  <span data-ttu-id="00c55-146">如果您不登录，一旦关闭 "编辑" 选项卡，您将失去编辑此项目的功能。</span><span class="sxs-lookup"><span data-stu-id="00c55-146">If you don't sign in you will lose the ability to edit this project once you close the editing tab.</span></span>  
1.  <span data-ttu-id="00c55-147">单击 "**显示**"，然后**在新窗口中**选择。</span><span class="sxs-lookup"><span data-stu-id="00c55-147">Click **Show** and select **In a New Window**.</span></span>  <span data-ttu-id="00c55-148">将打开一个新的选项卡，显示实时页面。</span><span class="sxs-lookup"><span data-stu-id="00c55-148">A new tab opens, showing you the live page.</span></span>  <span data-ttu-id="00c55-149">此选项卡将在整个教程中称为 "**实时" 选项卡**。</span><span class="sxs-lookup"><span data-stu-id="00c55-149">This tab will be called the **live tab** throughout this tutorial.</span></span>  
    
    > ##### <span data-ttu-id="00c55-150">图 5</span><span class="sxs-lookup"><span data-stu-id="00c55-150">Figure 5</span></span>  
    > <span data-ttu-id="00c55-151">"实时" 选项卡</span><span class="sxs-lookup"><span data-stu-id="00c55-151">The live tab</span></span>  
    > !["实时" 选项卡][ImageHtmlSetup4]  
    
## <span data-ttu-id="00c55-153">添加内容</span><span class="sxs-lookup"><span data-stu-id="00c55-153">Add content</span></span>   

<span data-ttu-id="00c55-154">您的网站非常空。</span><span class="sxs-lookup"><span data-stu-id="00c55-154">Your site is pretty empty.</span></span>  <span data-ttu-id="00c55-155">请按照以下步骤将一些内容添加到！</span><span class="sxs-lookup"><span data-stu-id="00c55-155">Follow the steps below to add some content to it!</span></span>  

1.  <span data-ttu-id="00c55-156">在 "**编辑器" 选项卡**中，"替换 `<!-- You're "About Me" will go here.  -->` 为" `<h1>About Me</h1>` 。</span><span class="sxs-lookup"><span data-stu-id="00c55-156">In the **editor tab**, replace `<!-- You're "About Me" will go here.  -->` with `<h1>About Me</h1>`.</span></span>  
    
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
    
    > ##### <span data-ttu-id="00c55-157">图 6</span><span class="sxs-lookup"><span data-stu-id="00c55-157">Figure 6</span></span>  
    > <span data-ttu-id="00c55-158">新代码在 "编辑器" 选项卡中突出显示</span><span class="sxs-lookup"><span data-stu-id="00c55-158">The new code is highlighted in the editor tab</span></span>  
    > ![新代码在 "编辑器" 选项卡中突出显示][ImageHtmlAdd1]  
    
1.  <span data-ttu-id="00c55-160">在 "**实时" 选项卡**中查看所做的更改。 文本 `About Me` 显示在页面上。</span><span class="sxs-lookup"><span data-stu-id="00c55-160">View your changes in the **live tab**.  The text `About Me` is visible on the page.</span></span>  <span data-ttu-id="00c55-161">它比其余文本更大，因为该 `<h1>` 元素表示节标题。</span><span class="sxs-lookup"><span data-stu-id="00c55-161">It's larger than the rest of the text, because the `<h1>` element represents a section heading.</span></span>  <span data-ttu-id="00c55-162">Web 浏览器会自动以较大字体调整标题样式。</span><span class="sxs-lookup"><span data-stu-id="00c55-162">Your web browser automatically styles headings in larger font sizes.</span></span>  
    
    > ##### <span data-ttu-id="00c55-163">图 7</span><span class="sxs-lookup"><span data-stu-id="00c55-163">Figure 7</span></span>  
    > <span data-ttu-id="00c55-164">新标题在 "实时" 选项卡中可见</span><span class="sxs-lookup"><span data-stu-id="00c55-164">The new heading is visible in the live tab</span></span>  
    > ![新标题在 "实时" 选项卡中可见][ImageHtmlAdd2]  
    
1.  <span data-ttu-id="00c55-166">返回到 "**编辑器" 选项卡**，在 `<p>I am learning HTML.  Recent accomplishments:</p>` 您刚放置的位置下方的行中插入 `<h1>About Me</h1>` 。</span><span class="sxs-lookup"><span data-stu-id="00c55-166">Back in the **editor tab**, insert `<p>I am learning HTML.  Recent accomplishments:</p>` on the line below where you just put `<h1>About Me</h1>`.</span></span>  
    
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

    > ##### <span data-ttu-id="00c55-167">图 8</span><span class="sxs-lookup"><span data-stu-id="00c55-167">Figure 8</span></span>  
    > <span data-ttu-id="00c55-168">新代码在 "编辑器" 选项卡中突出显示</span><span class="sxs-lookup"><span data-stu-id="00c55-168">The new code is highlighted in the editor tab</span></span>  
    > ![新代码在 "编辑器" 选项卡中突出显示][ImageHtmlAdd3]  
    
1.  <span data-ttu-id="00c55-170">在 "**实时" 选项卡**中查看您的更改。</span><span class="sxs-lookup"><span data-stu-id="00c55-170">View your change in the **live tab**.</span></span>  
1.  <span data-ttu-id="00c55-171">返回到 "**编辑器" 选项卡**，添加你的成就列表：</span><span class="sxs-lookup"><span data-stu-id="00c55-171">Back in the **editor tab**, add a list of your accomplishments:</span></span>  
    
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
    
    > ##### <span data-ttu-id="00c55-172">图 9</span><span class="sxs-lookup"><span data-stu-id="00c55-172">Figure 9</span></span>  
    > <span data-ttu-id="00c55-173">新代码在 "编辑器" 选项卡中突出显示</span><span class="sxs-lookup"><span data-stu-id="00c55-173">The new code is highlighted in the editor tab</span></span>  
    > ![新代码在 "编辑器" 选项卡中突出显示][ImageHtmlAdd4]  
    
1.  <span data-ttu-id="00c55-175">再次返回 "**实时" 选项卡**，确保新内容正确显示。</span><span class="sxs-lookup"><span data-stu-id="00c55-175">Again, go back to the **live tab** to make sure that the new content is displaying correctly.</span></span>  
    
    > ##### <span data-ttu-id="00c55-176">图 10</span><span class="sxs-lookup"><span data-stu-id="00c55-176">Figure 10</span></span>  
    > <span data-ttu-id="00c55-177">新列表在 "实时" 选项卡中可见</span><span class="sxs-lookup"><span data-stu-id="00c55-177">The new list is visible in the live tab</span></span>  
    > ![新列表在 "实时" 选项卡中可见][ImageHtmlAdd5]  
    
## <span data-ttu-id="00c55-179">在 Microsoft Edge DevTools 中试用内容更改</span><span class="sxs-lookup"><span data-stu-id="00c55-179">Experiment with content changes in Microsoft Edge DevTools</span></span>   

<span data-ttu-id="00c55-180">如果你正在开发一个包含大量 HTML 的大型页面，你可以想像，在 "编辑器" 选项卡和 "实时" 选项卡之间来回切换以查看你的更改，尤其是当你不确定要在页面上放置哪些内容时。</span><span class="sxs-lookup"><span data-stu-id="00c55-180">If you were developing a big page with a lot of HTML, you can imagine that it might be somewhat tedious to go back-and-forth between the editor tab and the live tab hundreds of times in order to see your changes, especially if you weren't sure what exactly to put on the page.</span></span>  <span data-ttu-id="00c55-181">Microsoft Edge DevTools 可帮助你在不离开 "实时" 选项卡的情况下试用内容更改。</span><span class="sxs-lookup"><span data-stu-id="00c55-181">Microsoft Edge DevTools can help you experiment with content changes without ever leaving the live tab.</span></span>  

### <span data-ttu-id="00c55-182">了解 HTML 和 DOM 之间的区别</span><span class="sxs-lookup"><span data-stu-id="00c55-182">Learn the difference between HTML and the DOM</span></span>   

<span data-ttu-id="00c55-183">开始从 Microsoft Edge DevTools 编辑内容之前，了解 HTML 和 DOM 之间的区别很有帮助。</span><span class="sxs-lookup"><span data-stu-id="00c55-183">Before you start editing your content from Microsoft Edge DevTools, it's helpful to understand the difference between HTML and the DOM.</span></span>  <span data-ttu-id="00c55-184">例如，学习的最佳方式是：</span><span class="sxs-lookup"><span data-stu-id="00c55-184">The best way to learn is by example:</span></span>  

1.  <span data-ttu-id="00c55-185">转到 "**实时" 选项卡**。 在页面底部看到文本 `A new element!?!` 。</span><span class="sxs-lookup"><span data-stu-id="00c55-185">Go to the **live tab**.  At the bottom of your page you see the text `A new element!?!`.</span></span>  
    
    > ###### <span data-ttu-id="00c55-186">图 11</span><span class="sxs-lookup"><span data-stu-id="00c55-186">Figure 11</span></span>  
    > <span data-ttu-id="00c55-187">在页面底部 `A new element!?!` 可以看到文本</span><span class="sxs-lookup"><span data-stu-id="00c55-187">At the bottom of the page the text `A new element!?!` can be seen</span></span>  
    > ![在页面底部，新元素的文本!?!][ImageHtmlDom1]  
    
1.  <span data-ttu-id="00c55-190">返回到 "**编辑器" 选项卡**，然后尝试在中查找此文本 `index.html` 。</span><span class="sxs-lookup"><span data-stu-id="00c55-190">Go back to the **editor tab** and try to find this text in `index.html`.</span></span>  <span data-ttu-id="00c55-191">不在这里！</span><span class="sxs-lookup"><span data-stu-id="00c55-191">It's not there!</span></span>  
    
    > ##### <span data-ttu-id="00c55-192">图 12</span><span class="sxs-lookup"><span data-stu-id="00c55-192">Figure 12</span></span>  
    > <span data-ttu-id="00c55-193">`A new element!?!`无法在中找到神秘的文本</span><span class="sxs-lookup"><span data-stu-id="00c55-193">The mystery text `A new element!?!` is nowhere to be found in</span></span> `index.html`  
    > ![新元素!?! 的神秘文本][ImageHtmlDom2]  
    
1.  <span data-ttu-id="00c55-196">返回到 "**实时" 选项卡**，右键单击 `A new element!?!` ，然后选择 "**检查**"。</span><span class="sxs-lookup"><span data-stu-id="00c55-196">Go back to the **live tab**, right-click `A new element!?!`, and select **Inspect**.</span></span>  
    
    > ##### <span data-ttu-id="00c55-197">图 13</span><span class="sxs-lookup"><span data-stu-id="00c55-197">Figure 13</span></span>  
    > <span data-ttu-id="00c55-198">检查某些文本</span><span class="sxs-lookup"><span data-stu-id="00c55-198">Inspecting some text</span></span>  
    > ![检查某些文本][ImageHtmlDom3]  
    
    <span data-ttu-id="00c55-200">DevTools 将在您的页面旁打开。</span><span class="sxs-lookup"><span data-stu-id="00c55-200">DevTools opens up alongside your page.</span></span>  `<div>A new element!?!</div>` <span data-ttu-id="00c55-201">将突出显示蓝色。</span><span class="sxs-lookup"><span data-stu-id="00c55-201">is highlighted blue.</span></span>  <span data-ttu-id="00c55-202">虽然 DevTools 中的此结构看起来像是 HTML，但实际上它是**DOM 树**。</span><span class="sxs-lookup"><span data-stu-id="00c55-202">Although this structure in DevTools looks like your HTML, it is actually the **DOM Tree**.</span></span>  
    
    > ##### <span data-ttu-id="00c55-203">图 14</span><span class="sxs-lookup"><span data-stu-id="00c55-203">Figure 14</span></span>  
    > <span data-ttu-id="00c55-204">DevTools 在页面旁打开</span><span class="sxs-lookup"><span data-stu-id="00c55-204">DevTools is open alongside the page</span></span>  
    > ![DevTools 在页面旁打开][ImageHtmlDom4]  
    
<span data-ttu-id="00c55-206">加载页面时，浏览器将获取 HTML 以创建页面的*初始*内容。</span><span class="sxs-lookup"><span data-stu-id="00c55-206">When your page loads, the browser takes your HTML to create the *initial* content of the page.</span></span>  <span data-ttu-id="00c55-207">DOM 表示页面的*当前*内容，它可能会随着时间的推移而更改。</span><span class="sxs-lookup"><span data-stu-id="00c55-207">The DOM represents the *current* content of the page, which can change over time.</span></span>  <span data-ttu-id="00c55-208">`<div>A new element!?!</div>`由于 HTML 底部的标记，可将神秘的内容添加到页面中 `<script src="new.js"></script>` 。</span><span class="sxs-lookup"><span data-stu-id="00c55-208">The mysterious `<div>A new element!?!</div>` content is added to your page because of the `<script src="new.js"></script>` tag at the bottom of your HTML.</span></span>  <span data-ttu-id="00c55-209">此标记会导致运行某些 JavaScript 代码。</span><span class="sxs-lookup"><span data-stu-id="00c55-209">This tag causes some JavaScript code to run.</span></span>  <span data-ttu-id="00c55-210">在后面的教程中，你将了解有关 JavaScript 的详细信息，但现在将其视为可更改你的页面内容的编程语言。</span><span class="sxs-lookup"><span data-stu-id="00c55-210">You'll learn more about JavaScript in a later tutorial, but for now think of it as a programming language that can change the content of your page.</span></span>  <span data-ttu-id="00c55-211">在此特定情况下，JavaScript 代码将添加 `<div>A new element!?!</div>` 到您的页面。</span><span class="sxs-lookup"><span data-stu-id="00c55-211">In this particular case, JavaScript code adds `<div>A new element!?!</div>` to your page.</span></span>  <span data-ttu-id="00c55-212">这就是您的实时页面（而不是 HTML）中显示此神秘文本的原因。</span><span class="sxs-lookup"><span data-stu-id="00c55-212">That is why this mystery text is visible on your live page, but not in your HTML.</span></span>  

### <span data-ttu-id="00c55-213">编辑 DOM</span><span class="sxs-lookup"><span data-stu-id="00c55-213">Edit the DOM</span></span>   

<span data-ttu-id="00c55-214">如果想要快速试用内容更改而又不离开 "实时" 选项卡，请尝试 DevTools。</span><span class="sxs-lookup"><span data-stu-id="00c55-214">If you want to quickly experiment with content changes without ever leaving the live tab, try DevTools.</span></span>  

1.  <span data-ttu-id="00c55-215">在 DevTools 中，右键单击 `Your site!` 并选择 "**编辑为 HTML**"。</span><span class="sxs-lookup"><span data-stu-id="00c55-215">In DevTools, right-click `Your site!` and select **Edit as HTML**.</span></span>  

    > ##### <span data-ttu-id="00c55-216">图 15</span><span class="sxs-lookup"><span data-stu-id="00c55-216">Figure 15</span></span>  
    > <span data-ttu-id="00c55-217">将节点编辑为 HTML</span><span class="sxs-lookup"><span data-stu-id="00c55-217">Editing the node as HTML</span></span>  
    > ![将节点编辑为 HTML][ImageHtmlEdit1]  
    
1.  <span data-ttu-id="00c55-219">替换 `<p>Your site!</p>` 为以下代码。</span><span class="sxs-lookup"><span data-stu-id="00c55-219">Replace `<p>Your site!</p>` with the code below.</span></span>  
    
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
    
    > ##### <span data-ttu-id="00c55-220">图 16</span><span class="sxs-lookup"><span data-stu-id="00c55-220">Figure 16</span></span>  
    > <span data-ttu-id="00c55-221">将节点编辑为 HTML</span><span class="sxs-lookup"><span data-stu-id="00c55-221">Editing the node as HTML</span></span>  
    > ![将节点编辑为 HTML][ImageHtmlEdit2]  
    
1.  <span data-ttu-id="00c55-223">按 `Control` + `Enter` \ （Windows \）或 `Command` + `Enter` \ （macOS \）保存所做的更改，或在框外单击。</span><span class="sxs-lookup"><span data-stu-id="00c55-223">Press `Control`+`Enter` \(Windows\) or `Command`+`Enter` \(macOS\) to save your changes, or click outside of the box.</span></span>  <span data-ttu-id="00c55-224">您的更改会自动显示在您的页面的实时视图中。</span><span class="sxs-lookup"><span data-stu-id="00c55-224">Your changes automatically show up in the live view of your page.</span></span>  <span data-ttu-id="00c55-225">文本已 `Your site!` 替换为新内容。</span><span class="sxs-lookup"><span data-stu-id="00c55-225">The text `Your site!` has been replaced with the new content.</span></span>  
    
    > ##### <span data-ttu-id="00c55-226">图 17</span><span class="sxs-lookup"><span data-stu-id="00c55-226">Figure 17</span></span>  
    > <span data-ttu-id="00c55-227">新内容将立即显示在页面上</span><span class="sxs-lookup"><span data-stu-id="00c55-227">The new content shows up immediately on the page</span></span>  
    > ![新内容将立即显示在页面上][ImageHtmlEdit3]  
    
<span data-ttu-id="00c55-229">此工作流仅适用于试用内容更改。</span><span class="sxs-lookup"><span data-stu-id="00c55-229">This workflow is only good for experimenting with content changes.</span></span>  <span data-ttu-id="00c55-230">如果重新加载页面或关闭选项卡，所做的更改将永久消失。</span><span class="sxs-lookup"><span data-stu-id="00c55-230">If you reload the page or close the tab, your changes will be gone forever.</span></span>  <span data-ttu-id="00c55-231">如果您使用的是此工作流，而您想要保存所做的更改，您需要手动将这些更改复制到您的 HTML 中。</span><span class="sxs-lookup"><span data-stu-id="00c55-231">If you're using this workflow and you want to save your changes, you need to manually copy those changes over to your HTML.</span></span>  <span data-ttu-id="00c55-232">接下来的几个部分介绍了一些可用于更改 DOM 树内容的更多方法。</span><span class="sxs-lookup"><span data-stu-id="00c55-232">The next couple of sections show you some more ways that you can change content from the DOM Tree.</span></span>  

## <span data-ttu-id="00c55-233">重新排序节点</span><span class="sxs-lookup"><span data-stu-id="00c55-233">Reorder nodes</span></span>   

<span data-ttu-id="00c55-234">你还可以更改 DOM 节点的顺序。</span><span class="sxs-lookup"><span data-stu-id="00c55-234">You can also change the order of DOM nodes.</span></span>  <span data-ttu-id="00c55-235">例如，在网页上，导航菜单位于底部附近。</span><span class="sxs-lookup"><span data-stu-id="00c55-235">For example, on your web page the navigation menu is near the bottom.</span></span>  <span data-ttu-id="00c55-236">将其移动到顶部：</span><span class="sxs-lookup"><span data-stu-id="00c55-236">To move it to the top:</span></span>  

1.  <span data-ttu-id="00c55-237">`<nav>`在 DevTools 的**DOM 树**中查找节点。</span><span class="sxs-lookup"><span data-stu-id="00c55-237">Find the `<nav>` node in the **DOM Tree** of DevTools.</span></span>  
    
    > ##### <span data-ttu-id="00c55-238">图18</span><span class="sxs-lookup"><span data-stu-id="00c55-238">Figure 18</span></span>  
    > <span data-ttu-id="00c55-239">导航节点在 DevTools 中突出显示蓝色</span><span class="sxs-lookup"><span data-stu-id="00c55-239">The nav node is highlighted blue in DevTools</span></span>  
    > ![导航节点在 DevTools 中突出显示蓝色][ImageHtmlReorder1]  
    
1.  <span data-ttu-id="00c55-241">将 `<nav>` 节点拖到顶部，使其成为节点下方的第一个子级 `<body>` 。</span><span class="sxs-lookup"><span data-stu-id="00c55-241">Drag the `<nav>` node to the top, so that it's the first child below the `<body>` node.</span></span>  
    > ##### <span data-ttu-id="00c55-242">图19</span><span class="sxs-lookup"><span data-stu-id="00c55-242">Figure 19</span></span>  
    > <span data-ttu-id="00c55-243">将导航节点拖动到顶部</span><span class="sxs-lookup"><span data-stu-id="00c55-243">Dragging the nav node to the top</span></span>  
    > ![将导航节点拖动到顶部][ImageHtmlReorder2]  
    
    <span data-ttu-id="00c55-245">`<nav>`现在，节点显示在您的页面顶部。</span><span class="sxs-lookup"><span data-stu-id="00c55-245">The `<nav>` node is now displaying at the top of your page.</span></span>  
    
    > ##### <span data-ttu-id="00c55-246">图20</span><span class="sxs-lookup"><span data-stu-id="00c55-246">Figure 20</span></span>  
    > <span data-ttu-id="00c55-247">导航节点位于页面顶部</span><span class="sxs-lookup"><span data-stu-id="00c55-247">The nav node is at the top of the page</span></span>  
    > ![导航节点位于页面顶部][ImageHtmlReorder3]  
    
### <span data-ttu-id="00c55-249">删除节点</span><span class="sxs-lookup"><span data-stu-id="00c55-249">Delete a node</span></span>   

<span data-ttu-id="00c55-250">您也可以从 DOM 树中删除节点。</span><span class="sxs-lookup"><span data-stu-id="00c55-250">You can also remove nodes from the DOM Tree.</span></span>  

1.  <span data-ttu-id="00c55-251">在**DOM 树**中，单击 `<div>A new element!?!</div>` 。</span><span class="sxs-lookup"><span data-stu-id="00c55-251">In the **DOM Tree**, click `<div>A new element!?!</div>`.</span></span>  <span data-ttu-id="00c55-252">DevTools 突出显示节点蓝色。</span><span class="sxs-lookup"><span data-stu-id="00c55-252">DevTools highlights the node blue.</span></span>  
    
    > ##### <span data-ttu-id="00c55-253">图21</span><span class="sxs-lookup"><span data-stu-id="00c55-253">Figure 21</span></span>  
    > <span data-ttu-id="00c55-254">选择要删除的节点</span><span class="sxs-lookup"><span data-stu-id="00c55-254">Selecting the node to be deleted</span></span>  
    > ![选择要删除的节点][ImageHtmlDelete1]  
    
1.  <span data-ttu-id="00c55-256">按 `Delete` 键盘上的键。</span><span class="sxs-lookup"><span data-stu-id="00c55-256">Press the `Delete` key on your keyboard.</span></span>  <span data-ttu-id="00c55-257">将 `<div>A new element!?!</div>` 从您的 DOM 树中删除该节点。</span><span class="sxs-lookup"><span data-stu-id="00c55-257">The `<div>A new element!?!</div>` node is removed from your DOM Tree.</span></span>  
    
    > ##### <span data-ttu-id="00c55-258">图22</span><span class="sxs-lookup"><span data-stu-id="00c55-258">Figure 22</span></span>  
    > <span data-ttu-id="00c55-259">该节点已被删除</span><span class="sxs-lookup"><span data-stu-id="00c55-259">The node has been deleted</span></span>  
    > ![该节点已被删除][ImageHtmlDelete2]  
    
## <span data-ttu-id="00c55-261">复制更改</span><span class="sxs-lookup"><span data-stu-id="00c55-261">Copy your changes</span></span>   

<span data-ttu-id="00c55-262">即将完成。</span><span class="sxs-lookup"><span data-stu-id="00c55-262">You're almost done.</span></span>  <span data-ttu-id="00c55-263">你已在 DevTools 中对页面进行了一些更改，但这些更改尚未保存到你的源代码。</span><span class="sxs-lookup"><span data-stu-id="00c55-263">You've made a few changes to your page in DevTools, but they're not yet saved to your source code.</span></span>  

1.  <span data-ttu-id="00c55-264">刷新 **"实时" 选项卡**。 您在 DOM 树中所做的更改将消失。</span><span class="sxs-lookup"><span data-stu-id="00c55-264">Refresh your **live tab**.  The changes that you made in the DOM Tree disappear.</span></span>  <span data-ttu-id="00c55-265">特别是，文本 `Your site!` 返回页首，文本 `A new element!?!` 返回到底部的文本。</span><span class="sxs-lookup"><span data-stu-id="00c55-265">In particular, the text `Your site!` returns to the top of the page, and the text `A new element!?!` returns to the bottom.</span></span>  
    
    > ##### <span data-ttu-id="00c55-266">图23</span><span class="sxs-lookup"><span data-stu-id="00c55-266">Figure 23</span></span>  
    > <span data-ttu-id="00c55-267">您所做的更改已丢失</span><span class="sxs-lookup"><span data-stu-id="00c55-267">The changes that you've made are gone</span></span>  
    > ![您所做的更改已丢失][ImageHtmlCopy1]  

1.  <span data-ttu-id="00c55-269">复制下面的代码。</span><span class="sxs-lookup"><span data-stu-id="00c55-269">Copy the code below.</span></span>  
    
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
      
1.  <span data-ttu-id="00c55-270">返回到 "**编辑器" 选项卡**，并将您的 `index.html` 文件内容替换为您刚复制的代码。</span><span class="sxs-lookup"><span data-stu-id="00c55-270">Go back to the **editor tab** and replace the contents of your `index.html` file with the code that you just copied.</span></span>  
    
    > ##### <span data-ttu-id="00c55-271">图24</span><span class="sxs-lookup"><span data-stu-id="00c55-271">Figure 24</span></span>  
    > <span data-ttu-id="00c55-272">文件的 `index.html` 外观</span><span class="sxs-lookup"><span data-stu-id="00c55-272">How your `index.html` file should look</span></span>  
    > ![index.html 文件的外观][ImageHtmlCopy2]  
    
## <span data-ttu-id="00c55-274">后续步骤</span><span class="sxs-lookup"><span data-stu-id="00c55-274">Next steps</span></span>   

*   <span data-ttu-id="00c55-275">完成本系列中的下一个教程 "[开始使用 CSS][DevToolsBeginnersCss]"，了解如何在 Microsoft Edge DevTools 中对页面进行样式更改并试验样式更改。</span><span class="sxs-lookup"><span data-stu-id="00c55-275">Complete the next tutorial in this series, [Get Started with CSS][DevToolsBeginnersCss], to learn how to style your page and experiment with style changes in Microsoft Edge DevTools.</span></span>  
*   <span data-ttu-id="00c55-276">阅读[对 dom 的介绍][MDNIntroductionDom]，了解有关 DOM 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="00c55-276">Read [Introduction to the DOM][MDNIntroductionDom] to learn more about the DOM.</span></span>  
*   <span data-ttu-id="00c55-277">查看类似[于 Web 开发简介][CourseraIntroductionToWebDevelopment]的课程，以获得更多动手的 web 开发体验。</span><span class="sxs-lookup"><span data-stu-id="00c55-277">Check out a course like [Introduction to Web Development][CourseraIntroductionToWebDevelopment] to get more hands-on web development experience.</span></span>  

<!--- image links --->  

[ImageHtmlFinished]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-finished.msft.png "图1：完成的网站"  
[ImageHtmlSetup1]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-setup1.msft.png "图2： "编辑器" 选项卡"  
[ImageHtmlSetup2]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-setup2.msft.png "图3： "项目选项" 菜单"  
[ImageHtmlSetup3]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-setup3.msft.png "图4： remixed 项目"  
[ImageHtmlSetup4]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-setup4.msft.png "图5： "实时" 选项卡"  
[ImageHtmlAdd1]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-add1.msft.png "图6：新代码在 "编辑器" 选项卡中突出显示"  
[ImageHtmlAdd2]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-add2.msft.png "图7：新标题在 "实时" 选项卡中可见"  
[ImageHtmlAdd3]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-add3.msft.png "图8：新代码在 "编辑器" 选项卡中突出显示"  
[ImageHtmlAdd4]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-add4.msft.png "图9：新代码在 "编辑器" 选项卡中突出显示"  
[ImageHtmlAdd5]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-add5.msft.png "图10：新列表在 "实时" 选项卡中可见"  
[ImageHtmlDom1]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-dom1.msft.png "图11：在页面底部!?! 新元素的文本可以看到"  
[ImageHtmlDom2]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-dom2.msft.png "图12：神秘的文本新元素!?!在 index.html 中找不到任何地方"  
[ImageHtmlDom3]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-dom3.msft.png "图13：检查某些文本"  
[ImageHtmlDom4]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-dom4.msft.png "图14： DevTools 在页面旁打开"  
[ImageHtmlEdit1]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-edit1.msft.png "图15：以 HTML 格式编辑节点"  
[ImageHtmlEdit2]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-edit2.msft.png "图16：以 HTML 格式编辑节点"  
[ImageHtmlEdit3]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-edit3.msft.png "图17：新内容将立即显示在页面上"  
[ImageHtmlReorder1]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-reorder1.msft.png "图18：导航节点在 DevTools 中突出显示蓝色"  
[ImageHtmlReorder2]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-reorder2.msft.png "图19：将导航节点拖动到顶部"  
[ImageHtmlReorder3]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-reorder3.msft.png "图20：导航节点位于页面顶部"  
[ImageHtmlDelete1]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-delete1.msft.png "图21：选择要删除的节点"  
[ImageHtmlDelete2]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-delete2.msft.png "图22：节点已被删除"  
[ImageHtmlCopy1]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-copy1.msft.png "图23：您所做的更改已丢失"  
[ImageHtmlCopy2]: /microsoft-edge/devtools-guide-chromium/media/beginners-html-copy2.msft.png "图24： index.html 文件的外观"  

<!--- links --->  

[DevToolsBeginnersCss]: /microsoft-edge/devtools-guide-chromium/beginners/css "初学者的 DevTools：开始使用 CSS"  

[MicrosoftEdgeInsider]: https://www.microsoftedgeinsider.com "Microsoft Edge 预览体验成员"  

[CourseraIntroductionToWebDevelopment]: https://www.coursera.org/learn/web-development "Web 开发简介 |Coursera"  

[GlitchAlluringShockIndex]: https://glitch.com/edit/#!/alluring-shock?path=index.html "index.html alluring-电击 |故障"  

[MDNGettingStartedHtml]: https://developer.mozilla.org/docs/Learn/HTML/Introduction_to_HTML/Getting_started "HTML | 入门MDN"  
[MDNIntroductionDom]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model/Introduction "DOM 简介 |MDN"  

> [!NOTE]
> <span data-ttu-id="00c55-308">此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="00c55-308">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="00c55-309">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/beginners/html)，由[Katherine 杰克逊][KatherineJackson]（技术作者暂存，Chrome DevTools \）创作。</span><span class="sxs-lookup"><span data-stu-id="00c55-309">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/beginners/html) and is authored by [Katherine Jackson][KatherineJackson] \(Technical Writer Intern, Chrome DevTools\).</span></span>  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
<span data-ttu-id="00c55-311">此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="00c55-311">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[KatherineJackson]: https://developers.google.com/web/resources/contributors/katjackson  
