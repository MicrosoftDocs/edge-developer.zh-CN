---
description: HTML 和 DOM 入门
title: 适合初学者的 DevTools：HTML 和 DOM 入门
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/01/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， web development， f12 tools， devtools， devtools for beginners， devtools HTML for beginners， devtools DOM for beginners， devtools html tutorial， devtools DOM tutorial， devtools document object model tutorial
ms.openlocfilehash: a049ec500e22f89db3ab1e966b55d89c2ad682fe
ms.sourcegitcommit: 8f37c931ecde4d58223113f7e3b42d37cc3df97f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2021
ms.locfileid: "11643472"
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
# <a name="devtools-for-beginners-get-started-with-html-and-the-dom"></a><span data-ttu-id="b04e0-104">适合初学者的 DevTools：HTML 和 DOM 入门</span><span class="sxs-lookup"><span data-stu-id="b04e0-104">DevTools for beginners: Get started with HTML and the DOM</span></span>  

<span data-ttu-id="b04e0-105">这是一系列教程中第一个介绍 Web 开发基础知识的教程。</span><span class="sxs-lookup"><span data-stu-id="b04e0-105">This is the first in a series of tutorials that teach you the basics of web development.</span></span> <span data-ttu-id="b04e0-106">了解一组 Web 开发人员工具（名为 Microsoft Edge DevTools）可能会提高工作效率。</span><span class="sxs-lookup"><span data-stu-id="b04e0-106">Learn about a set of web developer tools, named Microsoft Edge DevTools, that may increase your productivity.</span></span>  

<span data-ttu-id="b04e0-107">本教程介绍 HTML 和 [文档对象模型](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model) \ (DOM\) 。</span><span class="sxs-lookup"><span data-stu-id="b04e0-107">This tutorial describes HTML and the [Document Object Model](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model) \(DOM\).</span></span> <span data-ttu-id="b04e0-108">HTML 是 Web 开发的核心技术之一。</span><span class="sxs-lookup"><span data-stu-id="b04e0-108">HTML is one of the core technologies of web development.</span></span> <span data-ttu-id="b04e0-109">它是控制网页结构和内容的语言。</span><span class="sxs-lookup"><span data-stu-id="b04e0-109">It is the language that controls the structure and content of webpages.</span></span> <span data-ttu-id="b04e0-110">DOM 还与网页的结构和内容相关，我们稍后将了解相关内容。</span><span class="sxs-lookup"><span data-stu-id="b04e0-110">The DOM is also related to the structure and content of webpages, which we learn more about later.</span></span>

## <a name="goals"></a><span data-ttu-id="b04e0-111">目标</span><span class="sxs-lookup"><span data-stu-id="b04e0-111">Goals</span></span>  

<span data-ttu-id="b04e0-112">你将通过构建网站来学习 Web 开发。</span><span class="sxs-lookup"><span data-stu-id="b04e0-112">You're going to learn web development by building a website.</span></span>  <span data-ttu-id="b04e0-113">当你完成 **DevTools for Beginners** 系列的所有教程时，完成的网站可能如下图所示。</span><span class="sxs-lookup"><span data-stu-id="b04e0-113">By the time you complete all of the tutorials in the **DevTools for Beginners** series, your finished site may look like the following figure.</span></span>  

:::image type="complex" source="media/beginners-html-finished.msft.png" alt-text="完成的网站" lightbox="media/beginners-html-finished.msft.png":::
   <span data-ttu-id="b04e0-115">完成的网站</span><span class="sxs-lookup"><span data-stu-id="b04e0-115">The finished site</span></span>  
:::image-end:::  

<span data-ttu-id="b04e0-116">本教程结束时，你应该了解以下概念。</span><span class="sxs-lookup"><span data-stu-id="b04e0-116">By the end of this tutorial, you should understand the following concepts.</span></span>  

*   <span data-ttu-id="b04e0-117">HTML 和 DOM 如何创建网页上显示的内容。</span><span class="sxs-lookup"><span data-stu-id="b04e0-117">How HTML and the DOM create the content displayed on webpages.</span></span>  
*   <span data-ttu-id="b04e0-118">Microsoft Edge DevTools 如何帮助你试验 HTML 和 DOM 更改。</span><span class="sxs-lookup"><span data-stu-id="b04e0-118">How Microsoft Edge DevTools may help you experiment with HTML and DOM changes.</span></span>  
*   <span data-ttu-id="b04e0-119">HTML 和 DOM 的区别。</span><span class="sxs-lookup"><span data-stu-id="b04e0-119">The difference between HTML and the DOM.</span></span>  

<span data-ttu-id="b04e0-120">您还将具有一个工作网站。</span><span class="sxs-lookup"><span data-stu-id="b04e0-120">You will also have a working website.</span></span> <span data-ttu-id="b04e0-121">您可以使用该网站来承载简历或博客。</span><span class="sxs-lookup"><span data-stu-id="b04e0-121">You may use the site to host your resume or blog.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="b04e0-122">必备条件</span><span class="sxs-lookup"><span data-stu-id="b04e0-122">Prerequisites</span></span>  

<span data-ttu-id="b04e0-123">在尝试本教程之前，请完成以下先决条件：</span><span class="sxs-lookup"><span data-stu-id="b04e0-123">Before attempting this tutorial, complete the following prerequisites:</span></span>  

*   <span data-ttu-id="b04e0-124">如果不熟悉 HTML，请阅读 [HTML 文档入门][MDNGettingStartedHtml]。</span><span class="sxs-lookup"><span data-stu-id="b04e0-124">If you are unfamiliar with HTML, read [Getting Started with HTML][MDNGettingStartedHtml].</span></span>  
*   <span data-ttu-id="b04e0-125">下载 [Microsoft Edge][MicrosoftEdgeInsider] Web 浏览器。</span><span class="sxs-lookup"><span data-stu-id="b04e0-125">Download the [Microsoft Edge][MicrosoftEdgeInsider] web browser.</span></span>  <span data-ttu-id="b04e0-126">本教程使用一组内置于 Microsoft Edge 中的 Web 开发工具（称为 Microsoft Edge DevTools）。</span><span class="sxs-lookup"><span data-stu-id="b04e0-126">This tutorial uses a set of web development tools, called the Microsoft Edge DevTools, that are built into Microsoft Edge.</span></span>  

## <a name="set-up-your-code"></a><span data-ttu-id="b04e0-127">设置代码</span><span class="sxs-lookup"><span data-stu-id="b04e0-127">Set up your code</span></span>  

<span data-ttu-id="b04e0-128">你将在 Glitch Online 代码编辑器中构建一个网站。</span><span class="sxs-lookup"><span data-stu-id="b04e0-128">You are going to build a site in the Glitch online code editor.</span></span>  

1.  <span data-ttu-id="b04e0-129">打开 [源代码][GlitchAlluringShockIndex]。</span><span class="sxs-lookup"><span data-stu-id="b04e0-129">Open the [source code][GlitchAlluringShockIndex].</span></span> <span data-ttu-id="b04e0-130">在本教程中，此选项卡称为" **编辑器"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="b04e0-130">This tab is called the **editor tab** throughout this tutorial.</span></span>  
    
    :::image type="complex" source="media/beginners-html-setup1.msft.png" alt-text="编辑器选项卡" lightbox="media/beginners-html-setup1.msft.png":::
       <span data-ttu-id="b04e0-132">编辑器选项卡</span><span class="sxs-lookup"><span data-stu-id="b04e0-132">The editor tab</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="b04e0-133">选择 **"启发式"。**</span><span class="sxs-lookup"><span data-stu-id="b04e0-133">Choose **alluring-shock**.</span></span> <span data-ttu-id="b04e0-134">"Project**选项"** 菜单将打开。</span><span class="sxs-lookup"><span data-stu-id="b04e0-134">The **Project Options** menu opens.</span></span>  
    
    :::image type="complex" source="media/beginners-html-setup2.msft.png" alt-text="项目选项菜单" lightbox="media/beginners-html-setup2.msft.png":::
       <span data-ttu-id="b04e0-136">项目选项菜单</span><span class="sxs-lookup"><span data-stu-id="b04e0-136">The Project Options menu</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="b04e0-137">选择 **"重新混合项目"。**</span><span class="sxs-lookup"><span data-stu-id="b04e0-137">Choose **Remix Project**.</span></span> <span data-ttu-id="b04e0-138">Glitch 会创建一个可以编辑的项目副本，并随机为该项目生成一个新名称。</span><span class="sxs-lookup"><span data-stu-id="b04e0-138">Glitch creates a copy of the project that you may edit and randomly generates a new name for the project.</span></span> <span data-ttu-id="b04e0-139">内容与之前相同。</span><span class="sxs-lookup"><span data-stu-id="b04e0-139">The content is the same as before.</span></span>  
    
    :::image type="complex" source="media/beginners-html-setup3.msft.png" alt-text="重新混合的项目" lightbox="media/beginners-html-setup3.msft.png":::
       <span data-ttu-id="b04e0-141">重新混合的项目</span><span class="sxs-lookup"><span data-stu-id="b04e0-141">The remixed project</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="b04e0-142">如果计划完成本系列中的下一教程，请选择"使用 Facebook、GitHub或 Google 帐户登录小故障"; \*\*\*\* 或向自己发送一个神奇链接。</span><span class="sxs-lookup"><span data-stu-id="b04e0-142">If you plan to complete the next tutorial in this series, choose **Sign In** to Glitch using your Facebook, GitHub, or Google account; or email yourself a magic link.</span></span> <span data-ttu-id="b04e0-143">如果选择不登录帐户，则关闭编辑器选项卡后无法编辑项目。</span><span class="sxs-lookup"><span data-stu-id="b04e0-143">If you choose not to sign in to an account, you cannot edit the project after closing the editor tab.</span></span>

1.  <span data-ttu-id="b04e0-144">选择 **"**  \>  **在新建窗口中显示"。**</span><span class="sxs-lookup"><span data-stu-id="b04e0-144">Choose **Show** \> **In a New Window**.</span></span>  <span data-ttu-id="b04e0-145">将打开一个新选项卡，显示实时页面。</span><span class="sxs-lookup"><span data-stu-id="b04e0-145">A new tab opens, showing the live page.</span></span> <span data-ttu-id="b04e0-146">在本教程中，此选项卡称为实时 **选项卡**。</span><span class="sxs-lookup"><span data-stu-id="b04e0-146">This tab is called the **live tab** throughout this tutorial.</span></span>  
    
    :::image type="complex" source="media/beginners-html-setup4.msft.png" alt-text="实时选项卡" lightbox="media/beginners-html-setup4.msft.png":::
       <span data-ttu-id="b04e0-148">实时选项卡</span><span class="sxs-lookup"><span data-stu-id="b04e0-148">The live tab</span></span>  
    :::image-end:::  
    
## <a name="add-content"></a><span data-ttu-id="b04e0-149">添加内容</span><span class="sxs-lookup"><span data-stu-id="b04e0-149">Add content</span></span>  

<span data-ttu-id="b04e0-150">您的网站需要更多信息。</span><span class="sxs-lookup"><span data-stu-id="b04e0-150">Your site needs more information.</span></span> <span data-ttu-id="b04e0-151">完成以下步骤以添加一些内容。</span><span class="sxs-lookup"><span data-stu-id="b04e0-151">Complete the following steps to add some content.</span></span>  

1. <span data-ttu-id="b04e0-152">在" **编辑器"选项卡**，将 `<!-- You're "About Me" will go here.  -->` 替换 `<h1>About Me</h1>`。</span><span class="sxs-lookup"><span data-stu-id="b04e0-152">In the **editor tab**, replace `<!-- You're "About Me" will go here.  -->` with `<h1>About Me</h1>`.</span></span>  
    
    ```html
        ...
        <body>
            <p> Your site!</p>
                <main>
                    <h1>About Me</h1>
                </main>
        ...
    ```  
    
    :::image type="complex" source="media/beginners-html-add1.msft.png" alt-text="新代码在编辑器选项卡中突出显示" lightbox="media/beginners-html-add1.msft.png":::
        <span data-ttu-id="b04e0-154">新代码在编辑器选项卡中突出显示</span><span class="sxs-lookup"><span data-stu-id="b04e0-154">The new code is highlighted in the editor tab</span></span>  
    :::image-end:::  
    
1. <span data-ttu-id="b04e0-155">在实时选项卡 **中查看更改**。文本 `About Me` 在页面上可见。</span><span class="sxs-lookup"><span data-stu-id="b04e0-155">View your changes in the **live tab**. The text `About Me` is visible on the page.</span></span> <span data-ttu-id="b04e0-156">文本大于周围文本，因为 `<h1>` 元素表示"标题 1"。</span><span class="sxs-lookup"><span data-stu-id="b04e0-156">The text is larger than the surrounding text because the `<h1>` element represents a Heading 1.</span></span>  <span data-ttu-id="b04e0-157">Web 浏览器自动为标题设置更大字体的样式。</span><span class="sxs-lookup"><span data-stu-id="b04e0-157">Your web browser automatically styles headings in larger font sizes.</span></span>  
    
    :::image type="complex" source="media/beginners-html-add2.msft.png" alt-text="新标题显示在活动选项卡中" lightbox="media/beginners-html-add2.msft.png":::
       <span data-ttu-id="b04e0-159">新标题显示在活动选项卡中</span><span class="sxs-lookup"><span data-stu-id="b04e0-159">The new heading is visible in the live tab</span></span>  
    :::image-end:::  
    
1. <span data-ttu-id="b04e0-160">返回到编辑器 **选项卡中**，插入 `<p>I am learning web development. Recent accomplishments:</p>` 下面的行  `<h1>About Me</h1>` 。</span><span class="sxs-lookup"><span data-stu-id="b04e0-160">Back in the **editor tab**, insert `<p>I am learning web development. Recent accomplishments:</p>` on the line below  `<h1>About Me</h1>`.</span></span>  
    
    ```html
    ...
        <body>
            <p> Your site!</p>
                <main>
                    <h1>About Me</h1>
                    <p>I am learning web development. Recent accomplishments:</p>
                </main>
    ...
    ```  

    :::image type="complex" source="media/beginners-html-add3.msft.png" alt-text="更新后的代码在编辑器选项卡中突出显示" lightbox="media/beginners-html-add3.msft.png":::
        <span data-ttu-id="b04e0-162">更新后的代码在编辑器选项卡中突出显示</span><span class="sxs-lookup"><span data-stu-id="b04e0-162">The updated code is highlighted in the editor tab</span></span>  
    :::image-end:::  
    
1. <span data-ttu-id="b04e0-163">在实时选项卡 **中查看更改**。</span><span class="sxs-lookup"><span data-stu-id="b04e0-163">View your change in the **live tab**.</span></span>

1. <span data-ttu-id="b04e0-164">返回到编辑器 **选项卡**，使用下面的代码添加你的成就列表。</span><span class="sxs-lookup"><span data-stu-id="b04e0-164">Back in the **editor tab**, add a list of your accomplishments using the following code.</span></span>
    
    ```html
    ...
    <p>I am learning web development.  Recent accomplishments:</p>
        <ul>
            <li>Learned how to set up my code in Glitch.</li>
            <li>Added content to my HTML.</li>
            <li>TODO: Learn how to use Microsoft Edge DevTools to experiment with content changes.</li>
            <li>TODO: Learn the difference between HTML and the DOM.</li>
        </ul>
    ...
    ```  

    :::image type="complex" source="media/beginners-html-add4.msft.png" alt-text="更新后的代码还会在编辑器选项卡中突出显示" lightbox="media/beginners-html-add4.msft.png":::
        <span data-ttu-id="b04e0-166">更新后的代码还会在编辑器选项卡中突出显示</span><span class="sxs-lookup"><span data-stu-id="b04e0-166">The updated code is also highlighted in the editor tab</span></span>  
    :::image-end:::  

1. <span data-ttu-id="b04e0-167">查看 **实时选项卡** 以确保新内容正确显示。</span><span class="sxs-lookup"><span data-stu-id="b04e0-167">View the **live tab** to make sure that the new content displays correctly.</span></span>  
    
    :::image type="complex" source="media/beginners-html-add5.msft.png" alt-text="新列表在活动选项卡中可见" lightbox="media/beginners-html-add5.msft.png":::
       <span data-ttu-id="b04e0-169">新列表在活动选项卡中可见</span><span class="sxs-lookup"><span data-stu-id="b04e0-169">The new list is visible in the live tab</span></span>  
    :::image-end:::  
    
## <a name="experiment-with-content-changes-in-microsoft-edge-devtools"></a><span data-ttu-id="b04e0-170">在 Microsoft Edge DevTools 中试验内容更改</span><span class="sxs-lookup"><span data-stu-id="b04e0-170">Experiment with content changes in Microsoft Edge DevTools</span></span>  

<span data-ttu-id="b04e0-171">如果要开发包含大量 HTML 的页面，在编辑器选项卡和实时选项卡之间来回切换以查看更改将变得繁琐。</span><span class="sxs-lookup"><span data-stu-id="b04e0-171">If you are developing a page with a lot of HTML, it becomes tedious to go back-and-forth between the editor tab and the live tab to see your changes.</span></span> <span data-ttu-id="b04e0-172">Microsoft Edge DevTools 可帮助你尝试内容更改，而无需离开实时 **选项卡**。</span><span class="sxs-lookup"><span data-stu-id="b04e0-172">Microsoft Edge DevTools helps you experiment with content changes without ever leaving the **live tab**.</span></span>  

### <a name="learn-the-difference-between-html-and-the-dom"></a><span data-ttu-id="b04e0-173">了解 HTML 和 DOM 的区别</span><span class="sxs-lookup"><span data-stu-id="b04e0-173">Learn the difference between HTML and the DOM</span></span>  

<span data-ttu-id="b04e0-174">在编辑 DevTools Microsoft Edge内容之前，让我们了解 HTML 和 DOM 的区别。</span><span class="sxs-lookup"><span data-stu-id="b04e0-174">Before editing content from Microsoft Edge DevTools, let's understand the difference between HTML and the DOM.</span></span> <span data-ttu-id="b04e0-175">继续执行以下步骤以从示例中学习。</span><span class="sxs-lookup"><span data-stu-id="b04e0-175">Proceed with the following steps to learn from an example.</span></span>

1. <span data-ttu-id="b04e0-176">导航到实时 **选项卡**。在页面底部，将显示 `A new element!?!` 文本。</span><span class="sxs-lookup"><span data-stu-id="b04e0-176">Navigate to the **live tab**. At the bottom of your page, the text `A new element!?!` displays.</span></span>  

    <!--
        :::image type="complex" source="media/beginners-html-dom1.msft.png" alt-text="At the bottom of the page the text A new element!?! displays" lightbox="media/beginners-html-dom1.msft.png":::
        At the bottom of the page the text `A new element!?!` is displays  
        :::image-end:::
    -->
    
1. <span data-ttu-id="b04e0-177">打开 **编辑器选项卡** ，并尝试在 中查找文本 `index.html` 。</span><span class="sxs-lookup"><span data-stu-id="b04e0-177">Open the **editor tab** and try to find the text in `index.html`.</span></span> <span data-ttu-id="b04e0-178">文本不会在此视图中显示。</span><span class="sxs-lookup"><span data-stu-id="b04e0-178">The text does not display in this view.</span></span>  

    <!--
        :::image type="complex" source="media/beginners-html-dom2.msft.png" alt-text="The mystery text A new element!?! is not found in index.html" lightbox="media/beginners-html-dom2.msft.png":::
        The mystery text `A new element!?!` is not found in `index.html`  
        :::image-end:::
    -->

1. <span data-ttu-id="b04e0-179">打开实时**选项卡**，将鼠标悬停在 上，右 `A new element!?!` 键单击 (上下文菜单，然后选择) 检查 **"。**</span><span class="sxs-lookup"><span data-stu-id="b04e0-179">Open the **live tab**, hover over `A new element!?!`, open the contextual menu (right-click) and then choose **Inspect**.</span></span>  
    
    :::image type="complex" source="media/beginners-html-dom3.msft.png" alt-text="检查某些文本" lightbox="media/beginners-html-dom3.msft.png":::
       <span data-ttu-id="b04e0-181">检查某些文本</span><span class="sxs-lookup"><span data-stu-id="b04e0-181">Inspecting some text</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="b04e0-182">DevTools 将在页面旁边打开。</span><span class="sxs-lookup"><span data-stu-id="b04e0-182">DevTools opens up alongside your page.</span></span> `<div>A new element!?!</div>` <span data-ttu-id="b04e0-183">突出显示。</span><span class="sxs-lookup"><span data-stu-id="b04e0-183">is highlighted.</span></span> <span data-ttu-id="b04e0-184">尽管 DevTools 中的此结构类似于 HTML，但它是 **DOM 树**。</span><span class="sxs-lookup"><span data-stu-id="b04e0-184">Although this structure in DevTools looks like HTML, it is the **DOM Tree**.</span></span>  
    
    :::image type="complex" source="media/beginners-html-dom4.msft.png" alt-text="DevTools 与页面一起打开" lightbox="media/beginners-html-dom4.msft.png":::
       <span data-ttu-id="b04e0-186">DevTools 与页面一起打开</span><span class="sxs-lookup"><span data-stu-id="b04e0-186">DevTools is open alongside the page</span></span>  
    :::image-end:::  
    
<span data-ttu-id="b04e0-187">加载页面时，浏览器使用 HTML 创建页面的初始内容。</span><span class="sxs-lookup"><span data-stu-id="b04e0-187">When your page loads, the browser uses the HTML to create the initial content of the page.</span></span> <span data-ttu-id="b04e0-188">DOM 表示 页面 的当前内容，可能会随着时间的推移而更改。</span><span class="sxs-lookup"><span data-stu-id="b04e0-188">The DOM represents the current content of the page, which may change over time.</span></span> 

<span data-ttu-id="b04e0-189">由于 HTML 底部的 标记，内容 `<div>A new element!?!</div>` `<script src="new.js"></script>` 将添加到页面。</span><span class="sxs-lookup"><span data-stu-id="b04e0-189">The `<div>A new element!?!</div>` content is added to your page because of the `<script src="new.js"></script>` tag at the bottom of your HTML.</span></span> <span data-ttu-id="b04e0-190">此标记会导致某些 JavaScript 代码运行。</span><span class="sxs-lookup"><span data-stu-id="b04e0-190">This tag causes some JavaScript code to run.</span></span> <span data-ttu-id="b04e0-191">在稍后的教程 中了解有关 JavaScript [的更多内容](../javascript/index.md)。</span><span class="sxs-lookup"><span data-stu-id="b04e0-191">Learn more about JavaScript in a [later tutorial](../javascript/index.md).</span></span>

<span data-ttu-id="b04e0-192">现在，请看做可能会更改页面内容的脚本语言。</span><span class="sxs-lookup"><span data-stu-id="b04e0-192">For now, think of it as a scripting language that may change the content of your page.</span></span> <span data-ttu-id="b04e0-193">在这种情况下，JavaScript 代码将 `<div>A new element!?!</div>` 添加到你的页面。</span><span class="sxs-lookup"><span data-stu-id="b04e0-193">In this case, JavaScript code adds `<div>A new element!?!</div>` to your page.</span></span> <span data-ttu-id="b04e0-194">这就是此文本显示在活动选项卡 **中** 而不是 HTML 中的原因。</span><span class="sxs-lookup"><span data-stu-id="b04e0-194">That is why this text is displayed in the **live** tab, but not in the HTML.</span></span>  

### <a name="edit-the-dom"></a><span data-ttu-id="b04e0-195">编辑 DOM</span><span class="sxs-lookup"><span data-stu-id="b04e0-195">Edit the DOM</span></span>  

<span data-ttu-id="b04e0-196">如果你想要在不离开动态选项卡的情况下快速试验内容更改，请尝试使用 DevTools。</span><span class="sxs-lookup"><span data-stu-id="b04e0-196">If you want to quickly experiment with content changes without ever leaving the live tab, try DevTools.</span></span>  

1.  <span data-ttu-id="b04e0-197">在 DevTools 中，将鼠标悬停在 上，打开上下文菜单 (右键单击") `Your site!` 并选择"编辑**为 HTML"。**</span><span class="sxs-lookup"><span data-stu-id="b04e0-197">In DevTools, hover over `Your site!`, open the contextual menu (right-click) and choose **Edit as HTML**.</span></span>  
    
1.  <span data-ttu-id="b04e0-198">将 `<p>Your site!</p>` 替换为以下代码。</span><span class="sxs-lookup"><span data-stu-id="b04e0-198">Replace `<p>Your site!</p>` with the following code.</span></span>  

```html
    ...
    <header>
        <p><b>Welcome to my site!</b></p>
        <button>Download my resume</button>
    </header>
    ...
```  

:::image type="complex" source="media/beginners-html-edit2.msft.png" alt-text="将节点更新为 HTML" lightbox="media/beginners-html-edit2.msft.png":::
    <span data-ttu-id="b04e0-200">将节点更新为 HTML</span><span class="sxs-lookup"><span data-stu-id="b04e0-200">Updating the node as HTML</span></span>  
<span data-ttu-id="b04e0-201">：：image-end：：：</span><span class="sxs-lookup"><span data-stu-id="b04e0-201">::image-end:::</span></span>  

1.  <span data-ttu-id="b04e0-202">选择 `Control` + `Enter` \ (Windows、Linux\) 或 `Command` + `Enter` \ (macOS\) 保存更改，或在框外选择。</span><span class="sxs-lookup"><span data-stu-id="b04e0-202">Select `Control`+`Enter` \(Windows, Linux\) or `Command`+`Enter` \(macOS\) to save your changes, or select outside the box.</span></span> <span data-ttu-id="b04e0-203">更改将自动显示在页面实时视图中。</span><span class="sxs-lookup"><span data-stu-id="b04e0-203">Your changes automatically show up in the live view of your page.</span></span> <span data-ttu-id="b04e0-204">文本 `Your site!` 已替换为新内容。</span><span class="sxs-lookup"><span data-stu-id="b04e0-204">The text `Your site!` has been replaced with the new content.</span></span>  
    
    :::image type="complex" source="media/beginners-html-edit3.msft.png" alt-text="新内容会立即显示在页面上" lightbox="media/beginners-html-edit3.msft.png":::
       <span data-ttu-id="b04e0-206">新内容会立即显示在页面上</span><span class="sxs-lookup"><span data-stu-id="b04e0-206">The new content shows up immediately on the page</span></span>  
    :::image-end:::  
    
<span data-ttu-id="b04e0-207">此工作流仅适用于试验内容更改。</span><span class="sxs-lookup"><span data-stu-id="b04e0-207">This workflow is only suitable for experimenting with content changes.</span></span> <span data-ttu-id="b04e0-208">如果刷新页面或关闭选项卡，更改将丢失。</span><span class="sxs-lookup"><span data-stu-id="b04e0-208">If you refresh the page or close the tab, your changes are lost.</span></span> <span data-ttu-id="b04e0-209">如果要保存更改，请手动将代码复制到 HTML 文件中。</span><span class="sxs-lookup"><span data-stu-id="b04e0-209">If you want to save your changes, manually copy the code to your HTML file.</span></span> <span data-ttu-id="b04e0-210">接下来的几节将介绍从 DOM 树更改内容的更多方法。</span><span class="sxs-lookup"><span data-stu-id="b04e0-210">The next couple of sections show you some more ways to change content from the DOM Tree.</span></span>  

## <a name="reorder-nodes"></a><span data-ttu-id="b04e0-211">对节点重新排序</span><span class="sxs-lookup"><span data-stu-id="b04e0-211">Reorder nodes</span></span>

<span data-ttu-id="b04e0-212">您还可以更改 DOM 节点的顺序。</span><span class="sxs-lookup"><span data-stu-id="b04e0-212">You may also change the order of DOM nodes.</span></span> <span data-ttu-id="b04e0-213">例如，在网页上，导航菜单靠近底部。</span><span class="sxs-lookup"><span data-stu-id="b04e0-213">For example, on your web page the navigation menu is near the bottom.</span></span> <span data-ttu-id="b04e0-214">若要将其移动到顶部，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="b04e0-214">To move it to the top, perform the following steps.</span></span>  

1.  <span data-ttu-id="b04e0-215">在 DevTools `<nav>` DOM 树 **中** 节点。</span><span class="sxs-lookup"><span data-stu-id="b04e0-215">Find the `<nav>` node in the **DOM Tree** of DevTools.</span></span>  
    
    :::image type="complex" source="media/beginners-html-reorder1.msft.png" alt-text="导航节点在 DevTools 中突出显示" lightbox="media/beginners-html-reorder1.msft.png":::
       <span data-ttu-id="b04e0-217">导航节点在 DevTools 中突出显示</span><span class="sxs-lookup"><span data-stu-id="b04e0-217">The nav node is highlighted in DevTools</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="b04e0-218">将 `<nav>` 节点拖动到顶部，以便节点是节点后的第一个 `<body>` 子节点。</span><span class="sxs-lookup"><span data-stu-id="b04e0-218">Drag the `<nav>` node to the top, so that the node is the first child after the `<body>` node.</span></span>  
    
    :::image type="complex" source="media/beginners-html-reorder3.msft.png" alt-text="导航节点位于页面顶部" lightbox="media/beginners-html-reorder3.msft.png":::
        <span data-ttu-id="b04e0-220">导航节点位于页面顶部</span><span class="sxs-lookup"><span data-stu-id="b04e0-220">The nav node is at the top of the page</span></span>  
    :::image-end:::  
    
### <a name="delete-a-node"></a><span data-ttu-id="b04e0-221">删除节点</span><span class="sxs-lookup"><span data-stu-id="b04e0-221">Delete a node</span></span>

<span data-ttu-id="b04e0-222">您还可以从 DOM 树中删除节点。</span><span class="sxs-lookup"><span data-stu-id="b04e0-222">You may also remove nodes from the DOM Tree.</span></span> <span data-ttu-id="b04e0-223">执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="b04e0-223">Perform the following steps.</span></span>

1.  <span data-ttu-id="b04e0-224">在 **DOM 树**中，选择 `<div>A new element!?!</div>`。</span><span class="sxs-lookup"><span data-stu-id="b04e0-224">In the **DOM Tree**, choose `<div>A new element!?!</div>`.</span></span> <span data-ttu-id="b04e0-225">DevTools 突出显示节点。</span><span class="sxs-lookup"><span data-stu-id="b04e0-225">DevTools highlights the node.</span></span> 
    
1.  <span data-ttu-id="b04e0-226">选择 `Delete` 键盘上的键。</span><span class="sxs-lookup"><span data-stu-id="b04e0-226">Select the `Delete` key on your keyboard.</span></span>  <span data-ttu-id="b04e0-227">将从 `<div>A new element!?!</div>` DOM 树中删除节点。</span><span class="sxs-lookup"><span data-stu-id="b04e0-227">The `<div>A new element!?!</div>` node is removed from the DOM Tree.</span></span>  
    
    :::image type="complex" source="media/beginners-html-delete2.msft.png" alt-text="节点已删除" lightbox="media/beginners-html-delete2.msft.png":::
       <span data-ttu-id="b04e0-229">节点已删除</span><span class="sxs-lookup"><span data-stu-id="b04e0-229">The node has been deleted</span></span>  
    :::image-end:::  
    
## <a name="copy-your-changes"></a><span data-ttu-id="b04e0-230">复制更改</span><span class="sxs-lookup"><span data-stu-id="b04e0-230">Copy your changes</span></span>  

<span data-ttu-id="b04e0-231">你已接近完成。</span><span class="sxs-lookup"><span data-stu-id="b04e0-231">You're almost done.</span></span> <span data-ttu-id="b04e0-232">你在 DevTools 中对页面进行了一些更改，但它们不会保存到源代码中。</span><span class="sxs-lookup"><span data-stu-id="b04e0-232">You made a few changes to the page in DevTools, but they're not saved to your source code.</span></span>  

1.  <span data-ttu-id="b04e0-233">刷新活动 **选项卡**。在 DOM 树中所做的更改将消失。</span><span class="sxs-lookup"><span data-stu-id="b04e0-233">Refresh the **live tab**. The changes that you made in the DOM Tree disappear.</span></span> <span data-ttu-id="b04e0-234">具体而言，文本 `Your site!` 返回页首，文本 `A new element!?!` 返回页面底部。</span><span class="sxs-lookup"><span data-stu-id="b04e0-234">In particular, the text `Your site!` returns to the top of the page, and the text `A new element!?!` returns to the bottom.</span></span>  
    
    :::image type="complex" source="media/beginners-html-copy1.msft.png" alt-text="你所做的更改已消失" lightbox="media/beginners-html-copy1.msft.png":::
       <span data-ttu-id="b04e0-236">你所做的更改已消失</span><span class="sxs-lookup"><span data-stu-id="b04e0-236">The changes that you made are gone</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="b04e0-237">复制以下代码。</span><span class="sxs-lookup"><span data-stu-id="b04e0-237">Copy the following code.</span></span>  
    
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
    
1.  <span data-ttu-id="b04e0-238">返回到编辑器 **选项卡** ，将文件内容 `index.html` 替换为复制的代码。</span><span class="sxs-lookup"><span data-stu-id="b04e0-238">Go back to the **editor tab** and replace the content of your `index.html` file with the code that you copied.</span></span>  
    
    :::image type="complex" source="media/beginners-html-copy2.msft.png" alt-text="index.html 文件的外观" lightbox="media/beginners-html-copy2.msft.png":::
       <span data-ttu-id="b04e0-240">文件 `index.html` 的外观</span><span class="sxs-lookup"><span data-stu-id="b04e0-240">How your `index.html` file should look</span></span>  
    :::image-end:::  
    
## <a name="next-steps"></a><span data-ttu-id="b04e0-241">后续步骤</span><span class="sxs-lookup"><span data-stu-id="b04e0-241">Next steps</span></span>  

*   <span data-ttu-id="b04e0-242">完成本系列的下一个教程[CSS入门][DevToolsBeginnersCss]，以了解如何设置页面样式并尝试在Microsoft Edge DevTools中进行样式更改。</span><span class="sxs-lookup"><span data-stu-id="b04e0-242">Complete the next tutorial in this series, [Get Started with CSS][DevToolsBeginnersCss], to learn how to style your page and experiment with style changes in Microsoft Edge DevTools.</span></span>  
*   <span data-ttu-id="b04e0-243">阅读 [DOM 简介][MDNIntroductionDom] ，详细了解 DOM。</span><span class="sxs-lookup"><span data-stu-id="b04e0-243">Read [Introduction to the DOM][MDNIntroductionDom] to learn more about the DOM.</span></span>  
*   <span data-ttu-id="b04e0-244">有关更多动手 Web 开发体验 [，][CourseraIntroductionToWebDevelopment] 请查看 Web 开发简介等课程。</span><span class="sxs-lookup"><span data-stu-id="b04e0-244">Check out a course like [Introduction to Web Development][CourseraIntroductionToWebDevelopment] for more hands-on web development experience.</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="b04e0-245">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="b04e0-245">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!--- links --->  

[DevToolsBeginnersCss]: ./css.md "适用于初学者的 DevTools：CSS |Microsoft Docs"  

[MicrosoftEdgeInsider]: https://www.microsoftedgeinsider.com "Microsoft Edge 预览体验成员"  

[CourseraIntroductionToWebDevelopment]: https://www.coursera.org/learn/web-development "Web 开发类简介 | Coursera"  

[GlitchAlluringShockIndex]: https://glitch.com/edit/#!/alluring-shock?path=index.html "index.html - 启发式|小故障"  

[MDNGettingStartedHtml]: https://developer.mozilla.org/docs/Learn/HTML/Introduction_to_HTML/Getting_started "HTML 应用程序入门|MDN"  
[MDNIntroductionDom]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model/Introduction "DOM 简介 | MDN"  

> [!NOTE]
> <span data-ttu-id="b04e0-252">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="b04e0-252">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="b04e0-253">原始页面位于 [此处](https://developers.google.com/web/tools/chrome-devtools/beginners/html) ，作者为 [Katherine Writer][KatherineJackson] \ (Technical Writer，Chrome DevTools\) 。</span><span class="sxs-lookup"><span data-stu-id="b04e0-253">The original page was found [here](https://developers.google.com/web/tools/chrome-devtools/beginners/html) and was authored by [Katherine Jackson][KatherineJackson] \(Technical Writer Intern, Chrome DevTools\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="b04e0-255">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="b04e0-255">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
[KatherineJackson]: https://developers.google.com/web/resources/contributors  
