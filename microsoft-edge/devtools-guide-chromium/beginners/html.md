---
description: HTML 和 DOM 入门
title: 适用于初学者的 DevTools：HTML 和 DOM 入门
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， Web 开发， f12 工具， devtools
ms.openlocfilehash: 6ca27b720a17928545712666e43495c4da2fb880
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11397927"
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

# <a name="devtools-for-beginners-get-started-with-html-and-the-dom"></a><span data-ttu-id="0b921-104">适用于初学者的 DevTools：HTML 和 DOM 入门</span><span class="sxs-lookup"><span data-stu-id="0b921-104">DevTools for beginners: Get started with HTML and the DOM</span></span>  

<span data-ttu-id="0b921-105">这是一系列教程中第一个介绍 Web 开发基础知识的教程。</span><span class="sxs-lookup"><span data-stu-id="0b921-105">This is the first in a series of tutorials that teach you the basics of web development.</span></span>  <span data-ttu-id="0b921-106">了解一组 Web 开发人员工具（名为 Microsoft Edge DevTools）可能会提高工作效率。</span><span class="sxs-lookup"><span data-stu-id="0b921-106">Learn about a set of web developer tools, named Microsoft Edge DevTools, that may increase your productivity.</span></span>  

<span data-ttu-id="0b921-107">在此特定教程中，你将了解 HTML 和 DOM。</span><span class="sxs-lookup"><span data-stu-id="0b921-107">In this particular tutorial, you learn about HTML and the DOM.</span></span>  <span data-ttu-id="0b921-108">HTML 是 Web 开发的核心技术之一。</span><span class="sxs-lookup"><span data-stu-id="0b921-108">HTML is one of the core technologies of web development.</span></span>  <span data-ttu-id="0b921-109">它是控制网页结构和内容的语言。</span><span class="sxs-lookup"><span data-stu-id="0b921-109">It is the language that controls the structure and content of webpages.</span></span>  <span data-ttu-id="0b921-110">DOM 还与网页的结构和内容相关，稍后将了解相关内容。</span><span class="sxs-lookup"><span data-stu-id="0b921-110">The DOM is also related to the structure and content of webpages, learn more about that later.</span></span>  

## <a name="goals"></a><span data-ttu-id="0b921-111">目标</span><span class="sxs-lookup"><span data-stu-id="0b921-111">Goals</span></span>  

<span data-ttu-id="0b921-112">你将通过实际构建自己的网站来学习 Web 开发。</span><span class="sxs-lookup"><span data-stu-id="0b921-112">You are going to learn web development by actually building your own website.</span></span>  <span data-ttu-id="0b921-113">在 **DevTools** for Beginners 系列中完成所有教程后，完成的网站可能如下图所示。</span><span class="sxs-lookup"><span data-stu-id="0b921-113">By the time you complete all of the tutorials in the **DevTools for Beginners** series, your finished site may look like the following figure.</span></span>  

:::image type="complex" source="../media/beginners-html-finished.msft.png" alt-text="已完成的网站" lightbox="../media/beginners-html-finished.msft.png":::
   <span data-ttu-id="0b921-115">已完成的网站</span><span class="sxs-lookup"><span data-stu-id="0b921-115">The finished site</span></span>  
:::image-end:::  

<span data-ttu-id="0b921-116">在本教程结束时，你应该了解以下主题。</span><span class="sxs-lookup"><span data-stu-id="0b921-116">By the end of this tutorial, you should understand the following topics.</span></span>  

*   <span data-ttu-id="0b921-117">HTML 和 DOM 如何创建网页上显示的内容。</span><span class="sxs-lookup"><span data-stu-id="0b921-117">How HTML and the DOM create the content that are displayed on webpages.</span></span>  
*   <span data-ttu-id="0b921-118">Microsoft Edge DevTools 如何帮助你试验 HTML 和 DOM 更改。</span><span class="sxs-lookup"><span data-stu-id="0b921-118">How Microsoft Edge DevTools may help you experiment with HTML and DOM changes.</span></span>  
*   <span data-ttu-id="0b921-119">HTML 和 DOM 的区别。</span><span class="sxs-lookup"><span data-stu-id="0b921-119">The difference between HTML and the DOM.</span></span>  

<span data-ttu-id="0b921-120">您还有一个真实的网站。</span><span class="sxs-lookup"><span data-stu-id="0b921-120">You also have a real website.</span></span>  <span data-ttu-id="0b921-121">您可以使用该网站托管简历或博客。</span><span class="sxs-lookup"><span data-stu-id="0b921-121">You may use the site to host your resume or blog.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="0b921-122">必备条件</span><span class="sxs-lookup"><span data-stu-id="0b921-122">Prerequisites</span></span>  

<span data-ttu-id="0b921-123">在尝试本教程之前，请完成以下先决条件：</span><span class="sxs-lookup"><span data-stu-id="0b921-123">Before attempting this tutorial, complete the following prerequisites:</span></span>  

*   <span data-ttu-id="0b921-124">如果您不熟悉 HTML，请阅读 HTML [入门][MDNGettingStartedHtml]。</span><span class="sxs-lookup"><span data-stu-id="0b921-124">If you are unfamiliar with HTML, read [Getting Started with HTML][MDNGettingStartedHtml].</span></span>  
*   <span data-ttu-id="0b921-125">下载 [Microsoft Edge][MicrosoftEdgeInsider] Web 浏览器。</span><span class="sxs-lookup"><span data-stu-id="0b921-125">Download the [Microsoft Edge][MicrosoftEdgeInsider] web browser.</span></span>  <span data-ttu-id="0b921-126">本教程使用一组内置于 Microsoft Edge 中的 Web 开发工具（称为 Microsoft Edge DevTools）。</span><span class="sxs-lookup"><span data-stu-id="0b921-126">This tutorial uses a set of web development tools, called the Microsoft Edge DevTools, that are built into Microsoft Edge.</span></span>  

## <a name="set-up-your-code"></a><span data-ttu-id="0b921-127">设置代码</span><span class="sxs-lookup"><span data-stu-id="0b921-127">Set up your code</span></span>  

<span data-ttu-id="0b921-128">你将在名为 Glitch 的联机代码编辑器中生成网站。</span><span class="sxs-lookup"><span data-stu-id="0b921-128">You are going to build your site in an online code editor called Glitch.</span></span>  

1.  <span data-ttu-id="0b921-129">打开 [源代码][GlitchAlluringShockIndex]。</span><span class="sxs-lookup"><span data-stu-id="0b921-129">Open the [source code][GlitchAlluringShockIndex].</span></span>  <span data-ttu-id="0b921-130">此选项卡在本教程 **中称为"** 编辑器"选项卡。</span><span class="sxs-lookup"><span data-stu-id="0b921-130">This tab is called the **editor tab** throughout this tutorial.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-setup1.msft.png" alt-text="编辑器选项卡" lightbox="../media/beginners-html-setup1.msft.png":::
       <span data-ttu-id="0b921-132">编辑器选项卡</span><span class="sxs-lookup"><span data-stu-id="0b921-132">The editor tab</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="0b921-133">选择 **"启发式"。**</span><span class="sxs-lookup"><span data-stu-id="0b921-133">Choose **alluring-shock**.</span></span>  <span data-ttu-id="0b921-134">将在左上角打开"项目选项"菜单。</span><span class="sxs-lookup"><span data-stu-id="0b921-134">The Project Options menu opens in the top-left corner.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-setup2.msft.png" alt-text=""项目选项"菜单" lightbox="../media/beginners-html-setup2.msft.png":::
       <span data-ttu-id="0b921-136">"项目选项"菜单</span><span class="sxs-lookup"><span data-stu-id="0b921-136">The Project Options menu</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="0b921-137">选择 **"重新混合项目"。**</span><span class="sxs-lookup"><span data-stu-id="0b921-137">Choose **Remix Project**.</span></span>  <span data-ttu-id="0b921-138">小故障会创建一个可以编辑的项目副本，并随机为该项目生成一个新名称。</span><span class="sxs-lookup"><span data-stu-id="0b921-138">Glitch creates a copy of the project that you may edit and randomly generates a new name for the project.</span></span>  <span data-ttu-id="0b921-139">内容与之前相同。</span><span class="sxs-lookup"><span data-stu-id="0b921-139">The content is the same as before.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-setup3.msft.png" alt-text="重新混合的项目" lightbox="../media/beginners-html-setup3.msft.png":::
       <span data-ttu-id="0b921-141">重新混合的项目</span><span class="sxs-lookup"><span data-stu-id="0b921-141">The remixed project</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="0b921-142">如果你计划完成本系列中的下一个教程，请选择"登录"，\*\*\*\* 然后使用 GitHub 或 Facebook 帐户登录小故障。</span><span class="sxs-lookup"><span data-stu-id="0b921-142">If you plan on completing the next tutorial in this series, choose **Sign In** and sign into Glitch with your GitHub or Facebook account.</span></span>  <span data-ttu-id="0b921-143">如果选择不登录帐户，则关闭编辑选项卡后将失去编辑项目的能力。</span><span class="sxs-lookup"><span data-stu-id="0b921-143">If you choose to not sign into your account, you lose the ability to edit the project after you close the editing tab.</span></span>  
1.  <span data-ttu-id="0b921-144">选择 **"显示**"，**然后选择"新建窗口"。**</span><span class="sxs-lookup"><span data-stu-id="0b921-144">Choose **Show** and choose **In a New Window**.</span></span>  <span data-ttu-id="0b921-145">将打开一个新选项卡，显示实时页面。</span><span class="sxs-lookup"><span data-stu-id="0b921-145">A new tab opens, showing you the live page.</span></span>  <span data-ttu-id="0b921-146">此选项卡在本教程 **中称为实时** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="0b921-146">This tab is called the **live tab** throughout this tutorial.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-setup4.msft.png" alt-text="实时选项卡" lightbox="../media/beginners-html-setup4.msft.png":::
       <span data-ttu-id="0b921-148">实时选项卡</span><span class="sxs-lookup"><span data-stu-id="0b921-148">The live tab</span></span>  
    :::image-end:::  
    
## <a name="add-content"></a><span data-ttu-id="0b921-149">添加内容</span><span class="sxs-lookup"><span data-stu-id="0b921-149">Add content</span></span>  

<span data-ttu-id="0b921-150">你的网站相当空。</span><span class="sxs-lookup"><span data-stu-id="0b921-150">Your site is pretty empty.</span></span>  <span data-ttu-id="0b921-151">按照以下步骤向其中添加一些内容。</span><span class="sxs-lookup"><span data-stu-id="0b921-151">Follow the steps below to add some content to it.</span></span>  

1.  <span data-ttu-id="0b921-152">在 **编辑器选项卡中**，替换为 `<!-- You're "About Me" will go here.  -->` `<h1>About Me</h1>` 。</span><span class="sxs-lookup"><span data-stu-id="0b921-152">In the **editor tab**, replace `<!-- You're "About Me" will go here.  -->` with `<h1>About Me</h1>`.</span></span>  
    
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
          :::image type="complex" source="../media/beginners-html-add1.msft.png" alt-text="新代码在编辑器选项卡中突出显示" lightbox="../media/beginners-html-add1.msft.png":::
             <span data-ttu-id="0b921-154">新代码在编辑器选项卡中突出显示</span><span class="sxs-lookup"><span data-stu-id="0b921-154">The new code is highlighted in the editor tab</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::
    
1.  <span data-ttu-id="0b921-155">查看动态选项卡 **中的更改**。 文本 `About Me` 在页面上可见。</span><span class="sxs-lookup"><span data-stu-id="0b921-155">View your changes in the **live tab**.  The text `About Me` is visible on the page.</span></span>  <span data-ttu-id="0b921-156">文本大于周围文本，因为 `<h1>` 元素表示节标题。</span><span class="sxs-lookup"><span data-stu-id="0b921-156">The text larger than the surrounding text, because the `<h1>` element represents a section heading.</span></span>  <span data-ttu-id="0b921-157">Web 浏览器自动对字体大小较大的标题进行样式设置。</span><span class="sxs-lookup"><span data-stu-id="0b921-157">Your web browser automatically styles headings in larger font sizes.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-add2.msft.png" alt-text="新标题显示在活动选项卡中" lightbox="../media/beginners-html-add2.msft.png":::
       <span data-ttu-id="0b921-159">新标题显示在活动选项卡中</span><span class="sxs-lookup"><span data-stu-id="0b921-159">The new heading is visible in the live tab</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="0b921-160">返回到编辑器 **选项卡中**，插入下面 `<p>I am learning HTML.  Recent accomplishments:</p>` 您刚刚放在的行 `<h1>About Me</h1>` 上。</span><span class="sxs-lookup"><span data-stu-id="0b921-160">Back in the **editor tab**, insert `<p>I am learning HTML.  Recent accomplishments:</p>` on the line below where you just put `<h1>About Me</h1>`.</span></span>  
    
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
          :::image type="complex" source="../media/beginners-html-add3.msft.png" alt-text="更新后的代码在编辑器选项卡中突出显示" lightbox="../media/beginners-html-add3.msft.png":::
             <span data-ttu-id="0b921-162">更新后的代码在编辑器选项卡中突出显示</span><span class="sxs-lookup"><span data-stu-id="0b921-162">The updated code is highlighted in the editor tab</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::
    
1.  <span data-ttu-id="0b921-163">查看动态选项卡 **中的更改**。</span><span class="sxs-lookup"><span data-stu-id="0b921-163">View your change in the **live tab**.</span></span>  
1.  <span data-ttu-id="0b921-164">返回编辑器 **选项卡**，添加你的成就列表：</span><span class="sxs-lookup"><span data-stu-id="0b921-164">Back in the **editor tab**, add a list of your accomplishments:</span></span>  
    
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
          :::image type="complex" source="../media/beginners-html-add4.msft.png" alt-text="更新后的代码也会在编辑器选项卡中突出显示" lightbox="../media/beginners-html-add4.msft.png":::
             <span data-ttu-id="0b921-166">更新后的代码也会在编辑器选项卡中突出显示</span><span class="sxs-lookup"><span data-stu-id="0b921-166">The updated code is also highlighted in the editor tab</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
1.  <span data-ttu-id="0b921-167">同样，返回到实时 **选项卡** 以确保新内容正确显示。</span><span class="sxs-lookup"><span data-stu-id="0b921-167">Again, go back to the **live tab** to make sure that the new content is displaying correctly.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-add5.msft.png" alt-text="新列表在活动选项卡中可见" lightbox="../media/beginners-html-add5.msft.png":::
       <span data-ttu-id="0b921-169">新列表在活动选项卡中可见</span><span class="sxs-lookup"><span data-stu-id="0b921-169">The new list is visible in the live tab</span></span>  
    :::image-end:::  
    
## <a name="experiment-with-content-changes-in-microsoft-edge-devtools"></a><span data-ttu-id="0b921-170">在 Microsoft Edge DevTools 中试验内容更改</span><span class="sxs-lookup"><span data-stu-id="0b921-170">Experiment with content changes in Microsoft Edge DevTools</span></span>  

<span data-ttu-id="0b921-171">如果要开发一个包含大量 HTML 的大页面，那么在编辑器选项卡和动态选项卡之间来回切换数百次以显示更改会有点繁琐，尤其是在不确定该页面上具体要放入哪些内容时。</span><span class="sxs-lookup"><span data-stu-id="0b921-171">If you were developing a big page with a lot of HTML, it is somewhat tedious to go back-and-forth between the editor tab and the live tab hundreds of times in order to display your changes, especially if you are unsure what exactly to put on the page.</span></span>  <span data-ttu-id="0b921-172">Microsoft Edge DevTools 可帮助你试验内容更改，而无需离开实时 **选项卡**。</span><span class="sxs-lookup"><span data-stu-id="0b921-172">Microsoft Edge DevTools helps you experiment with content changes without ever leaving the **live tab**.</span></span>  

### <a name="learn-the-difference-between-html-and-the-dom"></a><span data-ttu-id="0b921-173">了解 HTML 和 DOM 的区别</span><span class="sxs-lookup"><span data-stu-id="0b921-173">Learn the difference between HTML and the DOM</span></span>  

<span data-ttu-id="0b921-174">在开始从 Microsoft Edge DevTools 编辑内容之前，您应了解 HTML 和 DOM 的区别。</span><span class="sxs-lookup"><span data-stu-id="0b921-174">Before you start editing your content from Microsoft Edge DevTools, you should understand the difference between HTML and the DOM.</span></span>  <span data-ttu-id="0b921-175">学习最好的方法就是通过示例：</span><span class="sxs-lookup"><span data-stu-id="0b921-175">The best way to learn is by example:</span></span>  

1.  <span data-ttu-id="0b921-176">导航到 **活动选项卡**。 在页面底部显示 `A new element!?!` 文本。</span><span class="sxs-lookup"><span data-stu-id="0b921-176">Navigate to the **live tab**.  At the bottom of your page, the text `A new element!?!` is displayed.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-dom1.msft.png" alt-text="在页面底部，文本 A 新元素!?! 显示" lightbox="../media/beginners-html-dom1.msft.png":::
       <span data-ttu-id="0b921-179">在页面底部显示 `A new element!?!` 文本</span><span class="sxs-lookup"><span data-stu-id="0b921-179">At the bottom of the page the text `A new element!?!` is displayed</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="0b921-180">返回到编辑器 **选项卡，** 并尝试在 中查找文本 `index.html` 。</span><span class="sxs-lookup"><span data-stu-id="0b921-180">Go back to the **editor tab** and try to find the text in `index.html`.</span></span>  <span data-ttu-id="0b921-181">文本不存在。</span><span class="sxs-lookup"><span data-stu-id="0b921-181">The text is not there.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-dom2.msft.png" alt-text="格式文本 A 新元素!?! 在 index.html 中index.htm" lightbox="../media/beginners-html-dom2.msft.png":::
       <span data-ttu-id="0b921-184">可以在以下 `A new element!?!` 内容中找到该文本：</span><span class="sxs-lookup"><span data-stu-id="0b921-184">The mystery text `A new element!?!` is nowhere to be found in</span></span> `index.html`  
    :::image-end:::  
    
1.  <span data-ttu-id="0b921-185">返回到实时**选项卡**，悬停在 `A new element!?!` 上，打开上下文菜单 \ (右键单击\) ，然后选择"检查 **"。**</span><span class="sxs-lookup"><span data-stu-id="0b921-185">Go back to the **live tab**, hover on `A new element!?!`, open the contextual menu \(right-click\), and choose **Inspect**.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-dom3.msft.png" alt-text="检查某些文本" lightbox="../media/beginners-html-dom3.msft.png":::
       <span data-ttu-id="0b921-187">检查某些文本</span><span class="sxs-lookup"><span data-stu-id="0b921-187">Inspecting some text</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="0b921-188">DevTools 将随页面一起打开。</span><span class="sxs-lookup"><span data-stu-id="0b921-188">DevTools opens up alongside your page.</span></span>  `<div>A new element!?!</div>` <span data-ttu-id="0b921-189">突出显示为蓝色。</span><span class="sxs-lookup"><span data-stu-id="0b921-189">is highlighted blue.</span></span>  <span data-ttu-id="0b921-190">尽管 DevTools 中的此结构看起来像你的 HTML，但它实际上是 **DOM 树**。</span><span class="sxs-lookup"><span data-stu-id="0b921-190">Although this structure in DevTools looks like your HTML, it is actually the **DOM Tree**.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-dom4.msft.png" alt-text="DevTools 与页面一起打开" lightbox="../media/beginners-html-dom4.msft.png":::
       <span data-ttu-id="0b921-192">DevTools 与页面一起打开</span><span class="sxs-lookup"><span data-stu-id="0b921-192">DevTools is open alongside the page</span></span>  
    :::image-end:::  
    
<span data-ttu-id="0b921-193">加载页面时，浏览器会采用 HTML 来创建 *页面* 的初始内容。</span><span class="sxs-lookup"><span data-stu-id="0b921-193">When your page loads, the browser takes your HTML to create the *initial* content of the page.</span></span>  <span data-ttu-id="0b921-194">DOM 表示 *页面的当前* 内容，可能会随着时间的推移而更改。</span><span class="sxs-lookup"><span data-stu-id="0b921-194">The DOM represents the *current* content of the page, which may change over time.</span></span>  <span data-ttu-id="0b921-195">由于 HTML 底部的标记，这一神奇内容将添加到 `<div>A new element!?!</div>` `<script src="new.js"></script>` 页面。</span><span class="sxs-lookup"><span data-stu-id="0b921-195">The mysterious `<div>A new element!?!</div>` content is added to your page because of the `<script src="new.js"></script>` tag at the bottom of your HTML.</span></span>  <span data-ttu-id="0b921-196">此标记会导致某些 JavaScript 代码运行。</span><span class="sxs-lookup"><span data-stu-id="0b921-196">This tag causes some JavaScript code to run.</span></span>  <span data-ttu-id="0b921-197">在稍后的教程中了解有关 JavaScript 的信息，但现在认为它是可能会更改页面内容的编程语言。</span><span class="sxs-lookup"><span data-stu-id="0b921-197">Learn more about JavaScript in a later tutorial, but for now think of it as a programming language that may change the content of your page.</span></span>  <span data-ttu-id="0b921-198">在此特定情况下，JavaScript 代码 `<div>A new element!?!</div>` 将添加到页面。</span><span class="sxs-lookup"><span data-stu-id="0b921-198">In this particular case, JavaScript code adds `<div>A new element!?!</div>` to your page.</span></span>  <span data-ttu-id="0b921-199">这就是为什么此神奇文本在实时页面上可见，但在 HTML 中不可见的原因。</span><span class="sxs-lookup"><span data-stu-id="0b921-199">That is why this mystery text is visible on your live page, but not in your HTML.</span></span>  

### <a name="edit-the-dom"></a><span data-ttu-id="0b921-200">编辑 DOM</span><span class="sxs-lookup"><span data-stu-id="0b921-200">Edit the DOM</span></span>  

<span data-ttu-id="0b921-201">如果你想要在不离开实时选项卡的情况下快速试验内容更改，请尝试使用 DevTools。</span><span class="sxs-lookup"><span data-stu-id="0b921-201">If you want to quickly experiment with content changes without ever leaving the live tab, try DevTools.</span></span>  

1.  <span data-ttu-id="0b921-202">在 DevTools 中，悬停在上，打开上下文菜单 `Your site!` \ (右键单击\) ，然后选择"编辑**为 HTML"。**</span><span class="sxs-lookup"><span data-stu-id="0b921-202">In DevTools, hover on `Your site!`, open the contextual menu \(right-click\), and choose **Edit as HTML**.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-edit1.msft.png" alt-text="将节点编辑为 HTML" lightbox="../media/beginners-html-edit1.msft.png":::
       <span data-ttu-id="0b921-204">将节点编辑为 HTML</span><span class="sxs-lookup"><span data-stu-id="0b921-204">Editing the node as HTML</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="0b921-205">替换为 `<p>Your site!</p>` 下面的代码。</span><span class="sxs-lookup"><span data-stu-id="0b921-205">Replace `<p>Your site!</p>` with the code below.</span></span>  
    
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
          :::image type="complex" source="../media/beginners-html-edit2.msft.png" alt-text="将节点更新为 HTML" lightbox="../media/beginners-html-edit2.msft.png":::
             <span data-ttu-id="0b921-207">将节点更新为 HTML</span><span class="sxs-lookup"><span data-stu-id="0b921-207">Updating the node as HTML</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
1.  <span data-ttu-id="0b921-208">选择 `Control` + `Enter` \ (Windows、Linux\) 或 `Command` + `Enter` \ (macOS\) 保存更改，或在框外选择。</span><span class="sxs-lookup"><span data-stu-id="0b921-208">Select `Control`+`Enter` \(Windows, Linux\) or `Command`+`Enter` \(macOS\) to save your changes, or choose outside of the box.</span></span>  <span data-ttu-id="0b921-209">你的更改会自动显示在页面实时视图中。</span><span class="sxs-lookup"><span data-stu-id="0b921-209">Your changes automatically show up in the live view of your page.</span></span>  <span data-ttu-id="0b921-210">文本 `Your site!` 已替换为新内容。</span><span class="sxs-lookup"><span data-stu-id="0b921-210">The text `Your site!` has been replaced with the new content.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-edit3.msft.png" alt-text="新内容会立即显示在页面上" lightbox="../media/beginners-html-edit3.msft.png":::
       <span data-ttu-id="0b921-212">新内容会立即显示在页面上</span><span class="sxs-lookup"><span data-stu-id="0b921-212">The new content shows up immediately on the page</span></span>  
    :::image-end:::  
    
<span data-ttu-id="0b921-213">此工作流仅适用于试验内容更改。</span><span class="sxs-lookup"><span data-stu-id="0b921-213">This workflow is only good for experimenting with content changes.</span></span>  <span data-ttu-id="0b921-214">如果刷新页面或关闭选项卡，更改将永久消失。</span><span class="sxs-lookup"><span data-stu-id="0b921-214">If you refresh the page or close the tab, your changes are gone forever.</span></span>  <span data-ttu-id="0b921-215">如果使用此工作流并且想要保存更改，则需要手动将这些更改复制到 HTML 中。</span><span class="sxs-lookup"><span data-stu-id="0b921-215">If you're using this workflow and you want to save your changes, you need to manually copy those changes over to your HTML.</span></span>  <span data-ttu-id="0b921-216">接下来的几节将介绍一些从 DOM 树更改内容的其他方法。</span><span class="sxs-lookup"><span data-stu-id="0b921-216">The next couple of sections show you some more ways that you may change content from the DOM Tree.</span></span>  

## <a name="reorder-nodes"></a><span data-ttu-id="0b921-217">对节点重新排序</span><span class="sxs-lookup"><span data-stu-id="0b921-217">Reorder nodes</span></span>  

<span data-ttu-id="0b921-218">您还可以更改 DOM 节点的顺序。</span><span class="sxs-lookup"><span data-stu-id="0b921-218">You may also change the order of DOM nodes.</span></span>  <span data-ttu-id="0b921-219">例如，在网页上，导航菜单靠近底部。</span><span class="sxs-lookup"><span data-stu-id="0b921-219">For example, on your web page the navigation menu is near the bottom.</span></span>  <span data-ttu-id="0b921-220">若要将其移动到顶部：</span><span class="sxs-lookup"><span data-stu-id="0b921-220">To move it to the top:</span></span>  

1.  <span data-ttu-id="0b921-221">在 `<nav>` DevTools **的 DOM 树** 中查找节点。</span><span class="sxs-lookup"><span data-stu-id="0b921-221">Find the `<nav>` node in the **DOM Tree** of DevTools.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-reorder1.msft.png" alt-text="导航节点在 DevTools 中突出显示为蓝色" lightbox="../media/beginners-html-reorder1.msft.png":::
       <span data-ttu-id="0b921-223">导航节点在 DevTools 中突出显示为蓝色</span><span class="sxs-lookup"><span data-stu-id="0b921-223">The nav node is highlighted blue in DevTools</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="0b921-224">将 `<nav>` 节点拖动到顶部，以便节点是节点的第一个 `<body>` 子节点。</span><span class="sxs-lookup"><span data-stu-id="0b921-224">Drag the `<nav>` node to the top, so that the node is the first child of the `<body>` node.</span></span>  
    
    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/beginners-html-reorder2.msft.png" alt-text="将导航节点拖动到顶部" lightbox="../media/beginners-html-reorder2.msft.png":::
             <span data-ttu-id="0b921-226">将导航节点拖动到顶部</span><span class="sxs-lookup"><span data-stu-id="0b921-226">Dragging the nav node to the top</span></span>  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          <span data-ttu-id="0b921-227">`<nav>`节点现在显示在页面顶部。</span><span class="sxs-lookup"><span data-stu-id="0b921-227">The `<nav>` node is now displaying at the top of your page.</span></span>  
          
          :::image type="complex" source="../media/beginners-html-reorder3.msft.png" alt-text="导航节点位于页面顶部" lightbox="../media/beginners-html-reorder3.msft.png":::
             <span data-ttu-id="0b921-229">导航节点位于页面顶部</span><span class="sxs-lookup"><span data-stu-id="0b921-229">The nav node is at the top of the page</span></span>  
          :::image-end:::  
       :::column-end:::
   :::row-end:::  
    
### <a name="delete-a-node"></a><span data-ttu-id="0b921-230">删除节点</span><span class="sxs-lookup"><span data-stu-id="0b921-230">Delete a node</span></span>  

<span data-ttu-id="0b921-231">您还可以从 DOM 树中删除节点。</span><span class="sxs-lookup"><span data-stu-id="0b921-231">You may also remove nodes from the DOM Tree.</span></span>  

1.  <span data-ttu-id="0b921-232">在 **DOM 树中**，选择 `<div>A new element!?!</div>` 。</span><span class="sxs-lookup"><span data-stu-id="0b921-232">In the **DOM Tree**, choose `<div>A new element!?!</div>`.</span></span>  <span data-ttu-id="0b921-233">DevTools 突出显示节点蓝色。</span><span class="sxs-lookup"><span data-stu-id="0b921-233">DevTools highlights the node blue.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-delete1.msft.png" alt-text="选择要删除的节点" lightbox="../media/beginners-html-delete1.msft.png":::
       <span data-ttu-id="0b921-235">选择要删除的节点</span><span class="sxs-lookup"><span data-stu-id="0b921-235">Choose the node to be deleted</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="0b921-236">选择 `Delete` 键盘上的键。</span><span class="sxs-lookup"><span data-stu-id="0b921-236">Select the `Delete` key on your keyboard.</span></span>  <span data-ttu-id="0b921-237">将从 `<div>A new element!?!</div>` DOM 树中删除节点。</span><span class="sxs-lookup"><span data-stu-id="0b921-237">The `<div>A new element!?!</div>` node is removed from your DOM Tree.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-delete2.msft.png" alt-text="节点已删除" lightbox="../media/beginners-html-delete2.msft.png":::
       <span data-ttu-id="0b921-239">节点已删除</span><span class="sxs-lookup"><span data-stu-id="0b921-239">The node has been deleted</span></span>  
    :::image-end:::  
    
## <a name="copy-your-changes"></a><span data-ttu-id="0b921-240">复制更改</span><span class="sxs-lookup"><span data-stu-id="0b921-240">Copy your changes</span></span>  

<span data-ttu-id="0b921-241">你几乎已完成。</span><span class="sxs-lookup"><span data-stu-id="0b921-241">You're almost done.</span></span>  <span data-ttu-id="0b921-242">你已对 DevTools 中的页面进行了一些更改，但尚未保存到源代码中。</span><span class="sxs-lookup"><span data-stu-id="0b921-242">You've made a few changes to your page in DevTools, but they're not yet saved to your source code.</span></span>  

1.  <span data-ttu-id="0b921-243">刷新你的 **实时选项卡**。 在 DOM 树中所做的更改将消失。</span><span class="sxs-lookup"><span data-stu-id="0b921-243">Refresh your **live tab**.  The changes that you made in the DOM Tree disappear.</span></span>  <span data-ttu-id="0b921-244">特别是，文本返回到页面顶部，文本 `Your site!` `A new element!?!` 返回底部。</span><span class="sxs-lookup"><span data-stu-id="0b921-244">In particular, the text `Your site!` returns to the top of the page, and the text `A new element!?!` returns to the bottom.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-copy1.msft.png" alt-text="你所做的更改已消失" lightbox="../media/beginners-html-copy1.msft.png":::
       <span data-ttu-id="0b921-246">你所做的更改已消失</span><span class="sxs-lookup"><span data-stu-id="0b921-246">The changes that you've made are gone</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="0b921-247">复制下面的代码。</span><span class="sxs-lookup"><span data-stu-id="0b921-247">Copy the code below.</span></span>  
    
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
    
1.  <span data-ttu-id="0b921-248">返回到编辑器 **选项卡** ，将文件内容 `index.html` 替换为刚复制的代码。</span><span class="sxs-lookup"><span data-stu-id="0b921-248">Go back to the **editor tab** and replace the contents of your `index.html` file with the code that you just copied.</span></span>  
    
    :::image type="complex" source="../media/beginners-html-copy2.msft.png" alt-text="index.html 文件的外观" lightbox="../media/beginners-html-copy2.msft.png":::
       <span data-ttu-id="0b921-250">文件 `index.html` 的外观</span><span class="sxs-lookup"><span data-stu-id="0b921-250">How your `index.html` file should look</span></span>  
    :::image-end:::  
    
## <a name="next-steps"></a><span data-ttu-id="0b921-251">后续步骤</span><span class="sxs-lookup"><span data-stu-id="0b921-251">Next steps</span></span>  

*   <span data-ttu-id="0b921-252">完成本系列中的下一个教程 ["CSS][DevToolsBeginnersCss]入门"，了解如何设置页面样式，以及如何在 Microsoft Edge DevTools 中试验样式更改。</span><span class="sxs-lookup"><span data-stu-id="0b921-252">Complete the next tutorial in this series, [Get Started with CSS][DevToolsBeginnersCss], to learn how to style your page and experiment with style changes in Microsoft Edge DevTools.</span></span>  
*   <span data-ttu-id="0b921-253">阅读 [DOM 简介][MDNIntroductionDom] ，详细了解 DOM。</span><span class="sxs-lookup"><span data-stu-id="0b921-253">Read [Introduction to the DOM][MDNIntroductionDom] to learn more about the DOM.</span></span>  
*   <span data-ttu-id="0b921-254">查看 Web 开发 [简介等][CourseraIntroductionToWebDevelopment] 课程，获取更多动手 Web 开发体验。</span><span class="sxs-lookup"><span data-stu-id="0b921-254">Check out a course like [Introduction to Web Development][CourseraIntroductionToWebDevelopment] to get more hands-on web development experience.</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="0b921-255">联系 Microsoft Edge 开发工具团队</span><span class="sxs-lookup"><span data-stu-id="0b921-255">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!--- links --->  

[DevToolsBeginnersCss]: ./css.md "适用于初学者的 DevTools：CSS |Microsoft Docs"  

[MicrosoftEdgeInsider]: https://www.microsoftedgeinsider.com "Microsoft Edge 预览体验成员"  

[CourseraIntroductionToWebDevelopment]: https://www.coursera.org/learn/web-development "Web 开发|Coursera"  

[GlitchAlluringShockIndex]: https://glitch.com/edit/#!/alluring-shock?path=index.html "index.html - 启发式|小故障"  

[MDNGettingStartedHtml]: https://developer.mozilla.org/docs/Learn/HTML/Introduction_to_HTML/Getting_started "HTML 应用程序入门|MDN"  
[MDNIntroductionDom]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model/Introduction "DOM |MDN"  

> [!NOTE]
> <span data-ttu-id="0b921-262">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="0b921-262">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="0b921-263">原始页面位于 [此处，](https://developers.google.com/web/tools/chrome-devtools/beginners/html) 由一名技术编写器 ([Chrome][KatherineJackson] DevTools\) 。</span><span class="sxs-lookup"><span data-stu-id="0b921-263">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/beginners/html) and is authored by [Katherine Jackson][KatherineJackson] \(Technical Writer Intern, Chrome DevTools\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="0b921-265">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="0b921-265">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[KatherineJackson]: https://developers.google.com/web/resources/contributors/katjackson  
