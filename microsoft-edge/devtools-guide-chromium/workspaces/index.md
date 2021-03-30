---
description: 了解如何将 DevTools 中所做的更改保存到磁盘。
title: 使用工作区编辑文件
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: 17f9ced15dbacd62c9ffe40e4af889925a8155fb
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11399244"
---
<!-- Copyright Kayce Basques 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->  

# <a name="edit-files-with-workspaces"></a><span data-ttu-id="63627-104">使用工作区编辑文件</span><span class="sxs-lookup"><span data-stu-id="63627-104">Edit files with Workspaces</span></span>  

> [!NOTE]
> <span data-ttu-id="63627-105">本教程的目标是提供设置和使用工作区的动手实践，以便可以在自己的项目中使用工作区。</span><span class="sxs-lookup"><span data-stu-id="63627-105">The goal of this tutorial is to provide hands-on practice in setting up and using Workspaces, so that you are able to use Workspaces in your own projects.</span></span>  <span data-ttu-id="63627-106">在启用工作区后，可以在本地计算机上保存对开发人员Tools 中源代码所做的更改。</span><span class="sxs-lookup"><span data-stu-id="63627-106">You are able to save the changes to the source code, on your local computer, that you made within DevTools after you enable Workspaces.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="63627-107">**先决条件：** 在开始本教程之前，你应该知道如何执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="63627-107">**Prerequisites**: Before beginning this tutorial, you should know how to perform the following actions.</span></span>  
> 
> *   [<span data-ttu-id="63627-108">使用 html、CSS 和 JavaScript 生成网页</span><span class="sxs-lookup"><span data-stu-id="63627-108">Use html, CSS, and JavaScript to build a web page</span></span>][MDNWebGettingStarted]  
> *   [<span data-ttu-id="63627-109">使用 DevTools 对 CSS 进行基本更改</span><span class="sxs-lookup"><span data-stu-id="63627-109">Use DevTools to make basic changes to CSS</span></span>][DevToolsCssIndex]  
> *   [<span data-ttu-id="63627-110">运行本地 HTTP Web 服务器</span><span class="sxs-lookup"><span data-stu-id="63627-110">Run a local HTTP web server</span></span>][MDNSimpleLocalHTTPServer]  

## <a name="overview"></a><span data-ttu-id="63627-111">概述</span><span class="sxs-lookup"><span data-stu-id="63627-111">Overview</span></span>  

<span data-ttu-id="63627-112">工作区使您能够将你在 Devtools 中做出更改保存到计算机上同一文件的本地副本。</span><span class="sxs-lookup"><span data-stu-id="63627-112">Workspaces enable you to save a change that you make in Devtools to a local copy of the same file on your computer.</span></span>  <span data-ttu-id="63627-113">对于本教程，计算机上应具有以下设置。</span><span class="sxs-lookup"><span data-stu-id="63627-113">For this tutorial, you should have the following settings on your machine.</span></span>  

*   <span data-ttu-id="63627-114">桌面上具有网站的源代码。</span><span class="sxs-lookup"><span data-stu-id="63627-114">You have the source code for your site on your desktop.</span></span>  
*   <span data-ttu-id="63627-115">您从源代码目录运行本地 Web 服务器，以便可从中访问该网站 `localhost:8080` 。</span><span class="sxs-lookup"><span data-stu-id="63627-115">You are running a local web server from the source code directory, so that the site is accessible at `localhost:8080`.</span></span>  
*   <span data-ttu-id="63627-116">你在 `localhost:8080` Microsoft Edge 中打开，并且正在使用 DevTools 更改网站的 CSS。</span><span class="sxs-lookup"><span data-stu-id="63627-116">You opened `localhost:8080` in Microsoft Edge, and you are using DevTools to change the CSS of the site.</span></span>  

<span data-ttu-id="63627-117">启用 Workspaces 后，你在 DevTools 中所做的更改将保存到桌面上的源代码中。</span><span class="sxs-lookup"><span data-stu-id="63627-117">With Workspaces enabled, the CSS changes that you make within DevTools are saved to the source code on your desktop.</span></span>  

## <a name="limitations"></a><span data-ttu-id="63627-118">限制</span><span class="sxs-lookup"><span data-stu-id="63627-118">Limitations</span></span>  

<span data-ttu-id="63627-119">如果你使用的是新式框架，它可能会将源代码从易于维护的格式转换为经过优化以尽快运行的格式。</span><span class="sxs-lookup"><span data-stu-id="63627-119">If you are using a modern framework, it probably transforms your source code from a format that is easy to maintain into a format that is optimized to run as quickly as possible.</span></span>  

<span data-ttu-id="63627-120">工作区通常能够在源映射的帮助下将优化的代码映射回原始 [源代码][TreehouseBlogSourceMaps]。</span><span class="sxs-lookup"><span data-stu-id="63627-120">Workspaces is usually able to map the optimized code back to your original source code with the help of [source maps][TreehouseBlogSourceMaps].</span></span>  <span data-ttu-id="63627-121">但是，在框架之间，每个框架使用源映射时存在很大差异。</span><span class="sxs-lookup"><span data-stu-id="63627-121">But there is a lot of variation between frameworks over how each uses source maps.</span></span>  <span data-ttu-id="63627-122">Devtools 仅支持所有变体。</span><span class="sxs-lookup"><span data-stu-id="63627-122">Devtools simply does support all of the variations.</span></span>  

<span data-ttu-id="63627-123">工作区已知无法与以下框架一起工作。</span><span class="sxs-lookup"><span data-stu-id="63627-123">Workspaces is known to not work with the following framework.</span></span>  

*   <span data-ttu-id="63627-124">创建 React 应用</span><span class="sxs-lookup"><span data-stu-id="63627-124">Create React App</span></span>  

    <!-- If you run into issues while using Workspaces with your framework of choice, or you get it working after some custom configuration, please [start a thread in the mailing list][AlphabetGroupsAlphabetBrowserDevTools] or [ask a question on Stack Overflow][StackOverflowAlphabetBrowserDevTools] to share your knowledge with the rest of the DevTools community.  -->  
    
## <a name="related-feature-local-overrides"></a><span data-ttu-id="63627-125">相关功能：本地替代</span><span class="sxs-lookup"><span data-stu-id="63627-125">Related feature: Local overrides</span></span>  

<span data-ttu-id="63627-126">**本地覆盖** 是另一个类似于 Workspaces 的 DevTools 功能。</span><span class="sxs-lookup"><span data-stu-id="63627-126">**Local Overrides** is another DevTools feature that is similar to Workspaces.</span></span>  <span data-ttu-id="63627-127">当您要尝试对网页所做的更改，并且需要跨网页加载显示更改，但您不关心将更改映射到网页的源代码时，请使用本地覆盖。</span><span class="sxs-lookup"><span data-stu-id="63627-127">Use Local Overrides when you want to experiment with changes to a webpage, and you need to display the changes across webpage loads, but you do not care about mapping your changes to the source code of the webpage.</span></span>  

<!--Todo: add section when content is ready  -->  

## <a name="step-1-set-up"></a><span data-ttu-id="63627-128">步骤 1：设置</span><span class="sxs-lookup"><span data-stu-id="63627-128">Step 1: Set up</span></span>  

<span data-ttu-id="63627-129">完成以下操作，获取工作区的动手体验。</span><span class="sxs-lookup"><span data-stu-id="63627-129">Complete the following actions, to get hands-on experience with Workspaces.</span></span>  

### <a name="set-up-the-demo"></a><span data-ttu-id="63627-130">设置演示</span><span class="sxs-lookup"><span data-stu-id="63627-130">Set up the demo</span></span>  

1.  <span data-ttu-id="63627-131">[打开演示][GlitchWorkspacesDemo]。</span><span class="sxs-lookup"><span data-stu-id="63627-131">[Open the demo][GlitchWorkspacesDemo].</span></span>  <!--In the top-left of the editor, a randomly-generated project name is displayed.  -->  
    
    :::image type="complex" source="../media/workspaces-glitch-workspaces-demo-source.msft.png" alt-text="小故障项目" lightbox="../media/workspaces-glitch-workspaces-demo-source.msft.png":::
       <span data-ttu-id="63627-133">小故障项目</span><span class="sxs-lookup"><span data-stu-id="63627-133">A Glitch project</span></span>  
    :::image-end:::  
    
    <!--1.  Choose the project name.  -->  
    <!--1.  Choose **Advanced Options** > **Download Project**.  
    
    :::image type="complex" source="../media/workspaces-glitch-advanced-options-download-project.msft.png" alt-text="The Download Project button" lightbox="../media/workspaces-glitch-advanced-options-download-project.msft.png":::
       The Download Project button  
    :::image-end:::  

    -->  
    <!--1.  Close the tab.  -->  
    <!--1.  Unzip the source code and move the unzipped `app` directory to your desktop.  For the rest of this tutorial the unzipped directory is referred to as `~/Desktop/app`.  -->  
    
1.  <span data-ttu-id="63627-134">在 `app` 桌面上创建目录。</span><span class="sxs-lookup"><span data-stu-id="63627-134">Create an `app` directory on your desktop.</span></span>  <span data-ttu-id="63627-135">将目录中的文件副本 `workspaces-demo` 保存到 `app` 目录中。</span><span class="sxs-lookup"><span data-stu-id="63627-135">Save copies of the files from the `workspaces-demo` directory to the `app` directory.</span></span>  <span data-ttu-id="63627-136">对于本教程的其余部分，目录称为 `~/Desktop/app` 。</span><span class="sxs-lookup"><span data-stu-id="63627-136">For the rest of the tutorial, the directory is referred to as `~/Desktop/app`.</span></span>  
1.  <span data-ttu-id="63627-137">在 中启动本地 Web 服务器 `~/Desktop/app` 。</span><span class="sxs-lookup"><span data-stu-id="63627-137">Start a local web server in `~/Desktop/app`.</span></span>  <span data-ttu-id="63627-138">下面是一些用于启动的示例代码，但 `SimpleHTTPServer` 您可以使用您喜欢的任何服务器。</span><span class="sxs-lookup"><span data-stu-id="63627-138">Below is some sample code for starting up `SimpleHTTPServer`, but you may use whatever server you prefer.</span></span>  
    
    :::row:::
       :::column span="":::
          ```bash
          cd ~/Desktop/app
          python -m SimpleHTTPServer # Python 2
          ```  
       :::column-end:::  
       :::column span="":::
          ```bash
          cd ~/Desktop/app
          python -m http.server # Python 3
          ```  
       :::column-end:::
    :::row-end:::  
    
1.  <span data-ttu-id="63627-139">在 Microsoft Edge 中打开一个选项卡，然后导航到本地托管的网站版本。</span><span class="sxs-lookup"><span data-stu-id="63627-139">Open a tab in Microsoft Edge and navigate to locally-hosted version of the site.</span></span>  <span data-ttu-id="63627-140">你应该能够使用 URL（如 或 `localhost:8080` ）来访问 `http://0.0.0.0:8080` 它。</span><span class="sxs-lookup"><span data-stu-id="63627-140">You should be able to access it using a URL like `localhost:8080` or `http://0.0.0.0:8080`.</span></span>  <span data-ttu-id="63627-141">确切的 [端口号][WikiPortURLs] 可能不同。</span><span class="sxs-lookup"><span data-stu-id="63627-141">The exact [port number][WikiPortURLs] may be different.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo.msft.png" alt-text="演示" lightbox="../media/workspaces-workspaces-demo.msft.png":::
       <span data-ttu-id="63627-143">演示</span><span class="sxs-lookup"><span data-stu-id="63627-143">The demo</span></span>  
    :::image-end:::  
    
### <a name="set-up-devtools"></a><span data-ttu-id="63627-144">设置 DevTools</span><span class="sxs-lookup"><span data-stu-id="63627-144">Set up DevTools</span></span>  

1.  <span data-ttu-id="63627-145">选择 `Control` + `Shift` + `J` \ (Windows、Linux\) 或 `Command` + `Option` + `J` \ (macOS\) 打开 DevTools\*\*\*\* 的控制台面板。</span><span class="sxs-lookup"><span data-stu-id="63627-145">Select `Control`+`Shift`+`J` \(Windows, Linux\) or `Command`+`Option`+`J` \(macOS\) to open the **Console** panel of DevTools.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-console.msft.png" alt-text="控制台面板" lightbox="../media/workspaces-workspaces-demo-console.msft.png":::
       <span data-ttu-id="63627-147">控制台**面板**</span><span class="sxs-lookup"><span data-stu-id="63627-147">The **Console** panel</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="63627-148">选择 **"源"** 工具。</span><span class="sxs-lookup"><span data-stu-id="63627-148">Choose the **Sources** tool.</span></span>  
1.  <span data-ttu-id="63627-149">选择 **"文件系统"** 面板。</span><span class="sxs-lookup"><span data-stu-id="63627-149">Choose the **Filesystem** panel.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-sources-filesystem.msft.png" alt-text="文件系统面板" lightbox="../media/workspaces-workspaces-demo-sources-filesystem.msft.png":::
       <span data-ttu-id="63627-151">**文件系统**面板</span><span class="sxs-lookup"><span data-stu-id="63627-151">The **Filesystem** panel</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="63627-152">选择 **"将文件夹添加到工作区"。**</span><span class="sxs-lookup"><span data-stu-id="63627-152">Choose **Add Folder To Workspace**.</span></span>  
1.  <span data-ttu-id="63627-153">键入 `~/Desktop/app`。</span><span class="sxs-lookup"><span data-stu-id="63627-153">Type `~/Desktop/app`.</span></span>  
1.  <span data-ttu-id="63627-154">Choose **Allow** to give DevTools permission to read and write to the directory.</span><span class="sxs-lookup"><span data-stu-id="63627-154">Choose **Allow** to give DevTools permission to read and write to the directory.</span></span>  
    <span data-ttu-id="63627-155">在 **Filesystem** 面板中，现在 ，和 旁边有一个 `index.html` 绿色 `script.js` 点 `styles.css` 。</span><span class="sxs-lookup"><span data-stu-id="63627-155">In the **Filesystem** panel, there is now a green dot next to `index.html`, `script.js`, and `styles.css`.</span></span>  <span data-ttu-id="63627-156">这些绿色点表示 DevTools 已建立页面的网络资源和中文件之间的映射 `~/Desktop/app` 。</span><span class="sxs-lookup"><span data-stu-id="63627-156">These green dots mean that DevTools has established a mapping between the network resources of the page, and the files in `~/Desktop/app`.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-sources-filesystem-folder.msft.png" alt-text="Filesystem 面板现在显示本地文件和网络文件之间的映射" lightbox="../media/workspaces-workspaces-demo-sources-filesystem-folder.msft.png":::
       <span data-ttu-id="63627-158">**Filesystem**面板现在显示本地文件和网络文件之间的映射</span><span class="sxs-lookup"><span data-stu-id="63627-158">The **Filesystem** panel now shows a mapping between the local files and the network ones</span></span>  
    :::image-end:::  
    
## <a name="step-2-save-a-css-change-to-disk"></a><span data-ttu-id="63627-159">步骤 2：将 CSS 更改保存到磁盘</span><span class="sxs-lookup"><span data-stu-id="63627-159">Step 2: Save a CSS change to disk</span></span>  

1.  <span data-ttu-id="63627-160">打开 `styles.css`。</span><span class="sxs-lookup"><span data-stu-id="63627-160">Open `styles.css`.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="63627-161">元素 `color` 的属性 `h1` 设置为 `fuchsia` 。</span><span class="sxs-lookup"><span data-stu-id="63627-161">The `color` property of `h1` elements is set to `fuchsia`.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-sources-filesystem-css.msft.png" alt-text="在文本编辑器中查看 styles.css" lightbox="../media/workspaces-workspaces-demo-sources-filesystem-css.msft.png":::
       <span data-ttu-id="63627-163">在 `styles.css` 文本编辑器中查看</span><span class="sxs-lookup"><span data-stu-id="63627-163">View `styles.css` in a text editor</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="63627-164">选择 **"元素"** 工具。</span><span class="sxs-lookup"><span data-stu-id="63627-164">Choose the **Elements** tool.</span></span>  
1.  <span data-ttu-id="63627-165">将元素的 `color` 属性值 `<h1>` 更改为你最喜爱的颜色。</span><span class="sxs-lookup"><span data-stu-id="63627-165">Change the value of the `color` property of the `<h1>` element to your favorite color.</span></span>  
    <span data-ttu-id="63627-166">请记住，您需要选择 DOM 树中的元素，才能在"样式"窗格中显示应用于该元素的 `<h1>` CSS\*\*\*\* 规则。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="63627-166">Remember that you need to choose the `<h1>` element in the **DOM Tree** in order to display the CSS rules applied to it in the **Styles** pane.</span></span>  <span data-ttu-id="63627-167">旁边的绿色点表示你进行的任何更改 `styles.css:1` 都映射到 `~/Desktop/app/styles.css` 。</span><span class="sxs-lookup"><span data-stu-id="63627-167">The green dot next to `styles.css:1` means that any change that you make are mapped to `~/Desktop/app/styles.css`.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-elements-styles-css.msft.png" alt-text="文件链接的绿色指示器" lightbox="../media/workspaces-workspaces-demo-elements-styles-css.msft.png":::
       <span data-ttu-id="63627-169">文件链接的绿色指示器</span><span class="sxs-lookup"><span data-stu-id="63627-169">The green indicator that the file is linked</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="63627-170">在 `styles.css` 文本编辑器中再次打开。</span><span class="sxs-lookup"><span data-stu-id="63627-170">Open `styles.css` in a text editor again.</span></span>  <span data-ttu-id="63627-171">属性 `color` 现在设置为你最喜爱的颜色。</span><span class="sxs-lookup"><span data-stu-id="63627-171">The `color` property is now set to your favorite color.</span></span>  
1.  <span data-ttu-id="63627-172">刷新页面。</span><span class="sxs-lookup"><span data-stu-id="63627-172">Refresh the page.</span></span>  <span data-ttu-id="63627-173">元素的颜色 `<h1>` 仍设置为你最喜爱的颜色。</span><span class="sxs-lookup"><span data-stu-id="63627-173">The color of the `<h1>` element is still set to your favorite color.</span></span>  <span data-ttu-id="63627-174">更改将在整个刷新中保留，因为进行更改时 DevTools 将更改保存到磁盘。</span><span class="sxs-lookup"><span data-stu-id="63627-174">The change remains across a refresh, because when you made the change DevTools saved the change to disk.</span></span>  <span data-ttu-id="63627-175">然后，刷新页面时，本地服务器从磁盘提供文件的修改副本。</span><span class="sxs-lookup"><span data-stu-id="63627-175">And then, when you refreshed the page, your local server served the modified copy of the file from disk.</span></span>  
    
## <a name="step-3-save-an-html-change-to-disk"></a><span data-ttu-id="63627-176">步骤 3：将 HTML 更改保存到磁盘</span><span class="sxs-lookup"><span data-stu-id="63627-176">Step 3: Save an HTML change to disk</span></span>  

### <a name="change-html-from-the-elements-panel"></a><span data-ttu-id="63627-177">从元素面板更改 HTML</span><span class="sxs-lookup"><span data-stu-id="63627-177">Change HTML from the Elements Panel</span></span>  

<span data-ttu-id="63627-178">你可以从元素面板对 html 进行更改，但是对 DOM 树所做的更改不会保存到磁盘，并且只影响当前浏览器会话。</span><span class="sxs-lookup"><span data-stu-id="63627-178">You may make changes to the html from the Element Panel, but your changes to the DOM tree are not saved to disk and only effect the current browser session.</span></span>  

<span data-ttu-id="63627-179">DOM 树不是 html。</span><span class="sxs-lookup"><span data-stu-id="63627-179">The DOM tree is not html.</span></span>  

<!--### Try changing HTML from the Elements panel  

> [!WARNING]
> The workflow that you are about to try does not work.  You are trying it now so that you do not waste time later trying to figure out why it is not working.  

1.  Choose the **Elements** tool.  
1.  Choose and edit the text content of the `h1` element, which says `Workspaces Demo`, and replace it with `I ❤️  Cake`.  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-change-h1.msft.png" alt-text="Attempt to change html from the DOM Tree of the Elements panel" lightbox="../media/workspaces-workspaces-demo-change-h1.msft.png":::
       Attempt to change html from the DOM Tree of the **Elements** tool  
    :::image-end:::  
    
1.  Open `~/Desktop/app/index.html` in a text editor.  The change that you just made does not appear.  
1.  Refresh the page.  The page reverts to the original title.  
    
#### Optional: Why it is not working  

> [!NOTE]
> This section describes why the workflow from [Try changing html from the Elements panel](#try-changing-html-from-the-elements-panel) does not work.  You should skip this section if you do not care why.  

*   The tree of nodes that are displayed on the **Elements** tool represents the [DOM][MDNWebAPIsDOM] of the page.  
*   To display a page, a browser fetches html over the network, parses the html, and then converts it into a tree of DOM nodes.  
*   If the page has any JavaScript, that JavaScript may add, delete, or change DOM nodes.  CSS may change the DOM, too, using the [`content`][MDNCSSContent] property.  
*   The browser eventually uses the DOM to determine what content it should present to browser users.  
*   Therefore, the final state of the webpage displayed for users may be very different from the html that the browser fetched.  
*   This makes it difficult for DevTools to resolve where a change made in the **Elements** tool should be saved, because the DOM is affected by HTML, JavaScript, and CSS.  

In short, the **DOM Tree** `!==` HTML.  
-->  

### <a name="change-html-from-the-sources-panel"></a><span data-ttu-id="63627-180">从"源"面板更改 HTML</span><span class="sxs-lookup"><span data-stu-id="63627-180">Change HTML from the Sources panel</span></span>  

<span data-ttu-id="63627-181">如果要保存对页面 html 的更改，则使用"源"**面板执行。**</span><span class="sxs-lookup"><span data-stu-id="63627-181">If you want to save a change to the html of the page, do it using the **Sources** panel.</span></span>  

1.  <span data-ttu-id="63627-182">选择 **"源"** 工具。</span><span class="sxs-lookup"><span data-stu-id="63627-182">Choose the **Sources** tool.</span></span>  
1.  <span data-ttu-id="63627-183">选择 **"页面"** 面板。</span><span class="sxs-lookup"><span data-stu-id="63627-183">Choose the **Page** panel.</span></span>  
1.  <span data-ttu-id="63627-184">选择\*\* (索引) 。 \*\*</span><span class="sxs-lookup"><span data-stu-id="63627-184">Choose **(index)**.</span></span>  <span data-ttu-id="63627-185">将打开页面的 HTML。</span><span class="sxs-lookup"><span data-stu-id="63627-185">The HTML for the page opens.</span></span>  
1.  <span data-ttu-id="63627-186">用 `<h1>I ❤️  Cake</h1>` 取代 `<h1>Workspaces Demo</h1>`。</span><span class="sxs-lookup"><span data-stu-id="63627-186">Replace `<h1>Workspaces Demo</h1>` with `<h1>I ❤️  Cake</h1>`.</span></span>  <span data-ttu-id="63627-187">查看下图。</span><span class="sxs-lookup"><span data-stu-id="63627-187">Review the following figure.</span></span>  
1.  <span data-ttu-id="63627-188">选择 `Control` + `S` \ (Windows、Linux\) 或 `Command` + `S` \ (macOS\) 保存更改。</span><span class="sxs-lookup"><span data-stu-id="63627-188">Select `Control`+`S` \(Windows, Linux\) or `Command`+`S` \(macOS\) to save the change.</span></span>  
1.  <span data-ttu-id="63627-189">刷新页面。</span><span class="sxs-lookup"><span data-stu-id="63627-189">Refresh the page.</span></span>  <span data-ttu-id="63627-190">该 `<h1>` 元素仍在显示新文本。</span><span class="sxs-lookup"><span data-stu-id="63627-190">The `<h1>` element is still displaying the new text.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-sources-page-h1.msft.png" alt-text="从源面板更改 HTML" lightbox="../media/workspaces-workspaces-demo-sources-page-h1.msft.png":::
       <span data-ttu-id="63627-192">从"源" **面板更改** HTML</span><span class="sxs-lookup"><span data-stu-id="63627-192">Change HTML from the **Sources** panel</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="63627-193">打开 `~/Desktop/app/index.html`。</span><span class="sxs-lookup"><span data-stu-id="63627-193">Open `~/Desktop/app/index.html`.</span></span>  <span data-ttu-id="63627-194">元素 `<h1>` 包含新文本。</span><span class="sxs-lookup"><span data-stu-id="63627-194">The `<h1>` element contains the new text.</span></span>  
    
## <a name="step-4-save-a-javascript-change-to-disk"></a><span data-ttu-id="63627-195">步骤 4：将 JavaScript 更改保存到磁盘</span><span class="sxs-lookup"><span data-stu-id="63627-195">Step 4: Save a JavaScript change to disk</span></span>  

<span data-ttu-id="63627-196">源 **面板** 也是对 JavaScript 进行更改的位置。</span><span class="sxs-lookup"><span data-stu-id="63627-196">The **Sources** panel is also the place to make changes to JavaScript.</span></span>  <span data-ttu-id="63627-197">但有时，你需要访问其他面板，如 **元素** 工具或 **控制台** 面板，同时对网站进行更改。</span><span class="sxs-lookup"><span data-stu-id="63627-197">But sometimes you need to access other panels, such as the **Elements** tool or the **Console** panel, while making changes to your site.</span></span>  <span data-ttu-id="63627-198">有一种方法可以与其他面板一\*\*\*\* 起打开"源"面板。</span><span class="sxs-lookup"><span data-stu-id="63627-198">There is a way to have the **Sources** panel open alongside other panels.</span></span>  

1.  <span data-ttu-id="63627-199">选择 **"元素"** 工具。</span><span class="sxs-lookup"><span data-stu-id="63627-199">Choose the **Elements** tool.</span></span>  
1.  <span data-ttu-id="63627-200">选择 `Control` + `Shift` + `P` \ (Windows、Linux\) `Command` + `Shift` + `P` 或 \ (macOS\) 。</span><span class="sxs-lookup"><span data-stu-id="63627-200">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\).</span></span>  <span data-ttu-id="63627-201">命令 **菜单** 将打开。</span><span class="sxs-lookup"><span data-stu-id="63627-201">The **Command Menu** opens.</span></span>  
1.  <span data-ttu-id="63627-202">键入 `QS` ，然后选择"**显示快速源"。**</span><span class="sxs-lookup"><span data-stu-id="63627-202">Type `QS`, then choose **Show Quick Source**.</span></span>  <span data-ttu-id="63627-203">在 DevTools 窗口底部，现在有一个 **快速源** 面板。</span><span class="sxs-lookup"><span data-stu-id="63627-203">At the bottom of your DevTools window there is now a **Quick Source** panel.</span></span>  <span data-ttu-id="63627-204">面板显示内容，这是你在"源"面板中编辑的最后 `index.html` **一** 个文件。</span><span class="sxs-lookup"><span data-stu-id="63627-204">The panel is displaying the contents of `index.html`, which is the last file you edited in the **Sources** panel.</span></span>  <span data-ttu-id="63627-205">快速**源**面板提供了"源"面板中的编辑器\*\*\*\*，以便您可以在打开其他面板的同时编辑文件。</span><span class="sxs-lookup"><span data-stu-id="63627-205">The **Quick Source** panel gives you the editor from the **Sources** panel, so that you are able to edit files while having other panels open.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-search-show-quick-source.msft.png" alt-text="使用命令菜单打开快速源面板" lightbox="../media/workspaces-workspaces-demo-search-show-quick-source.msft.png":::
       <span data-ttu-id="63627-207">使用 **命令菜单打开快速** 源 **面板**</span><span class="sxs-lookup"><span data-stu-id="63627-207">Open the **Quick Source** panel using **Command Menu**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="63627-208">选择 `Control` + `P` \ (Windows、Linux\) 或 `Command` + `P` \ (macOS\) 打开 **"打开文件"** 对话框。</span><span class="sxs-lookup"><span data-stu-id="63627-208">Select `Control`+`P` \(Windows, Linux\) or `Command`+`P` \(macOS\) to open the **Open File** dialog.</span></span>  <span data-ttu-id="63627-209">查看下图。</span><span class="sxs-lookup"><span data-stu-id="63627-209">Review the following figure.</span></span>  
1.  <span data-ttu-id="63627-210">键入 `script` ，然后选择\*\*应用/script.js。 \*\*</span><span class="sxs-lookup"><span data-stu-id="63627-210">Type `script`, then choose **app/script.js**.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-search-script.msft.png" alt-text="使用script.js打开文件对话框打开" lightbox="../media/workspaces-workspaces-demo-search-script.msft.png":::
       <span data-ttu-id="63627-212">使用 `script.js` "打开 **文件"对话框** 打开</span><span class="sxs-lookup"><span data-stu-id="63627-212">Open `script.js` using the **Open File** dialog</span></span>  
    :::image-end:::  
    
    > [!NOTE]
    > <span data-ttu-id="63627-213">演示 `Save Changes To Disk With Workspaces` 中的链接会定期设置样式。</span><span class="sxs-lookup"><span data-stu-id="63627-213">The `Save Changes To Disk With Workspaces` link in the demo is styled regularly.</span></span>  
    
1.  <span data-ttu-id="63627-214">使用"快速源"**面板script.js下面的\*\*\*\*代码。**</span><span class="sxs-lookup"><span data-stu-id="63627-214">Add the following code to the bottom of **script.js** using the **Quick Source** panel.</span></span>  
    
    ```javascript
    console.log('greetings from script.js');
    document.querySelector('a').style = 'font-style:italic';
    ```  
    
1.  <span data-ttu-id="63627-215">选择 `Control` + `S` \ (Windows、Linux\) 或 `Command` + `S` \ (macOS\) 保存更改。</span><span class="sxs-lookup"><span data-stu-id="63627-215">Select `Control`+`S` \(Windows, Linux\) or `Command`+`S` \(macOS\) to save the change.</span></span>  
1.  <span data-ttu-id="63627-216">刷新页面。</span><span class="sxs-lookup"><span data-stu-id="63627-216">Refresh the page.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="63627-217">页面上的链接现在为 italicized。</span><span class="sxs-lookup"><span data-stu-id="63627-217">The link on the page is now italicized.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-elements-styles-quick-source-script.msft.png" alt-text="页面上的链接现在为 italicized" lightbox="../media/workspaces-workspaces-demo-elements-styles-quick-source-script.msft.png":::
       <span data-ttu-id="63627-219">页面上的链接现在为 italicized</span><span class="sxs-lookup"><span data-stu-id="63627-219">The link on the page is now italicized</span></span>  
    :::image-end:::  
    
## <a name="next-steps"></a><span data-ttu-id="63627-220">后续步骤</span><span class="sxs-lookup"><span data-stu-id="63627-220">Next steps</span></span>  

<span data-ttu-id="63627-221">使用本教程中学到的内容在您自己的项目中设置工作区。</span><span class="sxs-lookup"><span data-stu-id="63627-221">Use what you have learned in this tutorial to set up Workspaces in your own project.</span></span>  <!-- If you run into any issues or are able to get it working after some custom configuration, please [start a thread in the mailing list][AlphabetGroupsAlphabetBrowserDevTools] or [ask a question on Stack Overflow][StackOverflowAlphabetBrowserDevTools] to share your knowledge with the rest of the DevTools community.  -->  

<!--  
If you have more feedback on the topics or anything else, please use any of the channels below:  

*   [Mailing List][AlphabetGroupsAlphabetBrowserDevTools]  
*   [Twitter][TwitterAlphabetBrowserDevTools]  -->  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="63627-222">联系 Microsoft Edge 开发工具团队</span><span class="sxs-lookup"><span data-stu-id="63627-222">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsCssIndex]: ../css/index.md "开始查看和更改 CSS |Microsoft Docs"  

<!--[LocalOverrides]: ../whats-new/2018/01/devtools#overrides -->  

<!--[AlphabetGroupsAlphabetBrowserDevTools]: https://groups.alphabet.com/forum/#!forum/alphabet-browser-developer-tools "Alphabet Browser DevTools - Alphabet Groups"  -->  

[GlitchWorkspacesDemo]: https://glitch.com/edit/#!/microsoft-edge-chromium-devtools?path=workspaces-demo/index.html:1:0 "工作区演示文件|小故障"  

[MDNCSSContent]: https://developer.mozilla.org/docs/Web/CSS/content "内容 - CSS：级联样式表|MDN"  
[MDNWebGettingStarted]: https://developer.mozilla.org/docs/Learn/Getting_started_with_the_web "Web 应用程序入门|MDN"  
[MDNSimpleLocalHTTPServer]: https://developer.mozilla.org/docs/Learn/Common_questions/set_up_a_local_testing_server#Running_a_simple_local_HTTP_server "运行简单的本地 HTTP 服务器|MDN"  
[MDNWebAPIsDOM]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model/Introduction "DOM 简介 - Web API |MDN"  

<!--[StackOverflowAlphabetBrowserDevTools]: https://stackoverflow.com/questions/ask?tags=alphabet-browser-devtools "Alphabet Browser DevTools - Stack Overflow"  -->

[TreehouseBlogSourceMaps]: https://blog.teamtreehouse.com/introduction-source-maps "源地图视图|Treehouse 博客"  

<!-- [TwitterAlphabetBrowserDevTools]: https://twitter.com/alphabetbrowserdevtools "Alphabet Browser DevTools \(@AlphabetBrowserDevTools\) | Twitter"  -->

[WikiPortURLs]: https://en.wikipedia.org/wiki/Port_(computer_networking)#Use_in_URLs "Port \ (computer networking\) - Wikipedia"  

> [!NOTE]
> <span data-ttu-id="63627-231">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="63627-231">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="63627-232">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/workspaces/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="63627-232">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/workspaces/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="63627-234">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="63627-234">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
