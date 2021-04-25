---
description: 了解如何将 DevTools 中所做的更改保存到磁盘。
title: 使用工作区编辑文件
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: f00e2e42f73f7d03c858deaf020db683391ff1f2
ms.sourcegitcommit: 16e2f7232196a57a70b979bbf8b663774b7ddc20
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/25/2021
ms.locfileid: "11519420"
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

# <a name="edit-files-with-workspaces"></a><span data-ttu-id="56970-104">使用工作区编辑文件</span><span class="sxs-lookup"><span data-stu-id="56970-104">Edit files with Workspaces</span></span>  

<span data-ttu-id="56970-105">本教程提供设置和使用 Workspace 的动手实践。</span><span class="sxs-lookup"><span data-stu-id="56970-105">This tutorial provides hands-on practice in setting up and using a Workspace.</span></span>  <span data-ttu-id="56970-106">将文件添加到 Workspace 后，在 DevTools 中的源代码中所做的更改将保存在本地计算机上，并且在您刷新网页后将保留。</span><span class="sxs-lookup"><span data-stu-id="56970-106">After you add files to a Workspace, the changes that you make in your source code within DevTools are saved on your local computer, and are preserved after you refresh the webpage.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="56970-107">**先决条件**：在开始本教程之前，你应知道如何执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="56970-107">**Prerequisites**: Before beginning this tutorial, you should know how to perform the following actions.</span></span>  
> 
> *   [<span data-ttu-id="56970-108">使用 html、CSS 和 JavaScript 构建网页</span><span class="sxs-lookup"><span data-stu-id="56970-108">Use html, CSS, and JavaScript to build a web page</span></span>][MDNWebGettingStarted]  
> *   [<span data-ttu-id="56970-109">使用 DevTools 对 CSS 进行基本更改</span><span class="sxs-lookup"><span data-stu-id="56970-109">Use DevTools to make basic changes to CSS</span></span>][DevToolsCssIndex]  
> *   [<span data-ttu-id="56970-110">运行本地 HTTP Web 服务器</span><span class="sxs-lookup"><span data-stu-id="56970-110">Run a local HTTP web server</span></span>][MDNSimpleLocalHTTPServer]  

## <a name="overview"></a><span data-ttu-id="56970-111">概述</span><span class="sxs-lookup"><span data-stu-id="56970-111">Overview</span></span>  

<span data-ttu-id="56970-112">工作区使你可以将你在 Devtools 中更改的内容保存到计算机上同一文件的本地副本中。</span><span class="sxs-lookup"><span data-stu-id="56970-112">Workspaces enable you to save a change that you make in Devtools to a local copy of the same file on your computer.</span></span>  <span data-ttu-id="56970-113">对于本教程，计算机上应具有以下设置。</span><span class="sxs-lookup"><span data-stu-id="56970-113">For this tutorial, you should have the following settings on your machine.</span></span>  

*   <span data-ttu-id="56970-114">桌面上具有网站的源代码。</span><span class="sxs-lookup"><span data-stu-id="56970-114">You have the source code for your site on your desktop.</span></span>  
*   <span data-ttu-id="56970-115">您从源代码目录运行本地 Web 服务器，以便可从 访问网站 `localhost:8080` 。</span><span class="sxs-lookup"><span data-stu-id="56970-115">You are running a local web server from the source code directory, so that the site is accessible at `localhost:8080`.</span></span>  
*   <span data-ttu-id="56970-116">在 `localhost:8080` Microsoft Edge 中打开，并且使用 DevTools 更改网站的 CSS。</span><span class="sxs-lookup"><span data-stu-id="56970-116">You opened `localhost:8080` in Microsoft Edge, and you are using DevTools to change the CSS of the site.</span></span>  

<span data-ttu-id="56970-117">启用工作区后，在 DevTools 中所做的更改 CSS 将保存到桌面上的源代码中。</span><span class="sxs-lookup"><span data-stu-id="56970-117">With Workspaces enabled, the CSS changes that you make within DevTools are saved to the source code on your desktop.</span></span>  

## <a name="limitations"></a><span data-ttu-id="56970-118">限制</span><span class="sxs-lookup"><span data-stu-id="56970-118">Limitations</span></span>  

<span data-ttu-id="56970-119">如果你使用的是新式框架，它可能会将源代码从易于维护的格式转换为经过优化以尽快运行的格式。</span><span class="sxs-lookup"><span data-stu-id="56970-119">If you are using a modern framework, it probably transforms your source code from a format that is easy to maintain into a format that is optimized to run as quickly as possible.</span></span>  

<span data-ttu-id="56970-120">工作区通常能够借助源映射 将优化的代码映射回原始 [源代码][TreehouseBlogSourceMaps]。</span><span class="sxs-lookup"><span data-stu-id="56970-120">Workspaces is usually able to map the optimized code back to your original source code with the help of [source maps][TreehouseBlogSourceMaps].</span></span>  <span data-ttu-id="56970-121">但在每个框架使用源映射时，框架之间有很多差异。</span><span class="sxs-lookup"><span data-stu-id="56970-121">But there is a lot of variation between frameworks over how each framework uses source maps.</span></span>  <span data-ttu-id="56970-122">Devtools 不支持所有变体。</span><span class="sxs-lookup"><span data-stu-id="56970-122">Devtools doesn't support all of the variations.</span></span>  

<span data-ttu-id="56970-123">工作区已知无法与以下框架一起工作。</span><span class="sxs-lookup"><span data-stu-id="56970-123">Workspaces is known to not work with the following framework.</span></span>  

*   <span data-ttu-id="56970-124">创建 React 应用</span><span class="sxs-lookup"><span data-stu-id="56970-124">Create React App</span></span>  

    <!-- If you run into issues while using Workspaces with your framework of choice, or you get it working after some custom configuration, please [start a thread in the mailing list][AlphabetGroupsAlphabetBrowserDevTools] or [ask a question on Stack Overflow][StackOverflowAlphabetBrowserDevTools] to share your knowledge with the rest of the DevTools community.  -->  
    
## <a name="related-feature-local-overrides"></a><span data-ttu-id="56970-125">相关功能：本地覆盖</span><span class="sxs-lookup"><span data-stu-id="56970-125">Related feature: Local overrides</span></span>  

<span data-ttu-id="56970-126">**本地覆盖** 是另一项类似于 Workspaces 的 DevTools 功能。</span><span class="sxs-lookup"><span data-stu-id="56970-126">**Local Overrides** is another DevTools feature that is similar to Workspaces.</span></span>  <span data-ttu-id="56970-127">当您想要尝试对网页所做的更改，并且需要跨网页加载显示更改，但您不关心将更改映射到网页的源代码时，请使用本地替代。</span><span class="sxs-lookup"><span data-stu-id="56970-127">Use Local Overrides when you want to experiment with changes to a webpage, and you need to display the changes across webpage loads, but you do not care about mapping your changes to the source code of the webpage.</span></span>  

<!--Todo: add section when content is ready  -->  

## <a name="step-1-set-up"></a><span data-ttu-id="56970-128">步骤 1：设置</span><span class="sxs-lookup"><span data-stu-id="56970-128">Step 1: Set up</span></span>  

<span data-ttu-id="56970-129">完成以下操作，获取工作区的动手体验。</span><span class="sxs-lookup"><span data-stu-id="56970-129">Complete the following actions, to get hands-on experience with Workspaces.</span></span>  

### <a name="set-up-the-demo"></a><span data-ttu-id="56970-130">设置演示</span><span class="sxs-lookup"><span data-stu-id="56970-130">Set up the demo</span></span>  

1.  <span data-ttu-id="56970-131">[打开演示][GlitchWorkspacesDemo]。</span><span class="sxs-lookup"><span data-stu-id="56970-131">[Open the demo][GlitchWorkspacesDemo].</span></span>  <!--In the top-left of the editor, a randomly-generated project name is displayed.  -->  
    
    :::image type="complex" source="../media/workspaces-glitch-workspaces-demo-source.msft.png" alt-text="小故障项目" lightbox="../media/workspaces-glitch-workspaces-demo-source.msft.png":::
       <span data-ttu-id="56970-133">小故障项目</span><span class="sxs-lookup"><span data-stu-id="56970-133">A Glitch project</span></span>  
    :::image-end:::  
    
    <!--1.  Choose the project name.  -->  
    <!--1.  Choose **Advanced Options** > **Download Project**.  
    
    :::image type="complex" source="../media/workspaces-glitch-advanced-options-download-project.msft.png" alt-text="The Download Project button" lightbox="../media/workspaces-glitch-advanced-options-download-project.msft.png":::
       The Download Project button  
    :::image-end:::  

    -->  
    <!--1.  Close the tab.  -->  
    <!--1.  Unzip the source code and move the unzipped `app` directory to your desktop.  For the rest of this tutorial the unzipped directory is referred to as `~/Desktop/app`.  -->  
    
1.  <span data-ttu-id="56970-134">在 `app` 桌面上创建目录。</span><span class="sxs-lookup"><span data-stu-id="56970-134">Create an `app` directory on your desktop.</span></span>  <span data-ttu-id="56970-135">将文件副本从目录 `workspaces-demo` 保存到 `app` 目录。</span><span class="sxs-lookup"><span data-stu-id="56970-135">Save copies of the files from the `workspaces-demo` directory to the `app` directory.</span></span>  <span data-ttu-id="56970-136">在本教程的其余部分中，目录称为 `~/Desktop/app` 。</span><span class="sxs-lookup"><span data-stu-id="56970-136">For the rest of the tutorial, the directory is referred to as `~/Desktop/app`.</span></span>  
1.  <span data-ttu-id="56970-137">在 中启动本地 Web 服务器 `~/Desktop/app` 。</span><span class="sxs-lookup"><span data-stu-id="56970-137">Start a local web server in `~/Desktop/app`.</span></span>  <span data-ttu-id="56970-138">下面是一些用于启动的示例代码 `SimpleHTTPServer` ，但您可以使用您喜欢的任何服务器。</span><span class="sxs-lookup"><span data-stu-id="56970-138">Below is some sample code for starting up `SimpleHTTPServer`, but you may use whatever server you prefer.</span></span>  
    
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
    
1.  <span data-ttu-id="56970-139">在 Microsoft Edge 中打开一个选项卡，然后导航到本地托管的站点版本。</span><span class="sxs-lookup"><span data-stu-id="56970-139">Open a tab in Microsoft Edge and navigate to locally-hosted version of the site.</span></span>  <span data-ttu-id="56970-140">你应该能够使用 URL（如 或 ） `localhost:8080` 访问 `http://0.0.0.0:8080` 它。</span><span class="sxs-lookup"><span data-stu-id="56970-140">You should be able to access it using a URL like `localhost:8080` or `http://0.0.0.0:8080`.</span></span>  <span data-ttu-id="56970-141">确切的 [端口号][WikiPortURLs] 可能不同。</span><span class="sxs-lookup"><span data-stu-id="56970-141">The exact [port number][WikiPortURLs] may be different.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo.msft.png" alt-text="演示" lightbox="../media/workspaces-workspaces-demo.msft.png":::
       <span data-ttu-id="56970-143">演示</span><span class="sxs-lookup"><span data-stu-id="56970-143">The demo</span></span>  
    :::image-end:::  
    
### <a name="set-up-devtools"></a><span data-ttu-id="56970-144">设置 DevTools</span><span class="sxs-lookup"><span data-stu-id="56970-144">Set up DevTools</span></span>  

1.  <span data-ttu-id="56970-145">选择 `Control` + `Shift` + `J` \ (Windows、Linux\) 或 `Command` + `Option` + `J` \ (macOS\) 打开 DevTools\*\*\*\* 的控制台面板。</span><span class="sxs-lookup"><span data-stu-id="56970-145">Select `Control`+`Shift`+`J` \(Windows, Linux\) or `Command`+`Option`+`J` \(macOS\) to open the **Console** panel of DevTools.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-console.msft.png" alt-text="控制台面板" lightbox="../media/workspaces-workspaces-demo-console.msft.png":::
       <span data-ttu-id="56970-147">控制台**面板**</span><span class="sxs-lookup"><span data-stu-id="56970-147">The **Console** panel</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="56970-148">导航到 **"源"** 工具。</span><span class="sxs-lookup"><span data-stu-id="56970-148">Navigate to the **Sources** tool.</span></span>  
1.  <span data-ttu-id="56970-149">在左侧 **导航器** (窗格中 **，) "文件系统"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="56970-149">In the **Navigator** pane (on the left), choose the **Filesystem** tab.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-sources-filesystem.msft.png" alt-text=""文件系统"选项卡" lightbox="../media/workspaces-workspaces-demo-sources-filesystem.msft.png":::
       <span data-ttu-id="56970-151">" **文件系统"** 选项卡</span><span class="sxs-lookup"><span data-stu-id="56970-151">The **Filesystem** tab</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="56970-152">选择 **"将文件夹添加到工作区"。**</span><span class="sxs-lookup"><span data-stu-id="56970-152">Choose **Add Folder To Workspace**.</span></span>  
1.  <span data-ttu-id="56970-153">键入 `~/Desktop/app`。</span><span class="sxs-lookup"><span data-stu-id="56970-153">Type `~/Desktop/app`.</span></span>  
1.  <span data-ttu-id="56970-154">选择 **"** 允许"以授予 DevTools 读取和写入目录的权限。</span><span class="sxs-lookup"><span data-stu-id="56970-154">Choose **Allow** to give DevTools permission to read and write to the directory.</span></span>  
    <span data-ttu-id="56970-155">在" **文件系统"** 选项卡中，现在，、 和 旁边将出现 `index.html` `script.js` 一个绿色点 `styles.css` 。</span><span class="sxs-lookup"><span data-stu-id="56970-155">In the **Filesystem** tab, a green dot now appears next to `index.html`, `script.js`, and `styles.css`.</span></span>  <span data-ttu-id="56970-156">绿色点表示 DevTools 已建立页面的网络资源与 中的文件之间的映射 `~/Desktop/app` 。</span><span class="sxs-lookup"><span data-stu-id="56970-156">A green dot indicates that DevTools has established a mapping between a network resource of the page, and the file in `~/Desktop/app`.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-sources-filesystem-folder.msft.png" alt-text=""文件系统"选项卡现在指示本地文件和网络文件之间的映射" lightbox="../media/workspaces-workspaces-demo-sources-filesystem-folder.msft.png":::
       <span data-ttu-id="56970-158">" **文件系统** "选项卡现在指示本地文件和网络文件之间的映射</span><span class="sxs-lookup"><span data-stu-id="56970-158">The **Filesystem** tab now indicates a mapping between the local files and the network ones</span></span>  
    :::image-end:::  
    
## <a name="step-2-save-a-css-change-to-disk"></a><span data-ttu-id="56970-159">步骤 2：将 CSS 更改保存到磁盘</span><span class="sxs-lookup"><span data-stu-id="56970-159">Step 2: Save a CSS change to disk</span></span>  

1.  <span data-ttu-id="56970-160">打开 `styles.css`。</span><span class="sxs-lookup"><span data-stu-id="56970-160">Open `styles.css`.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="56970-161">`color`元素的 `h1` 属性设置为 `fuchsia` 。</span><span class="sxs-lookup"><span data-stu-id="56970-161">The `color` property of `h1` elements is set to `fuchsia`.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-sources-filesystem-css.msft.png" alt-text="在文本编辑器中查看 styles.css" lightbox="../media/workspaces-workspaces-demo-sources-filesystem-css.msft.png":::
       <span data-ttu-id="56970-163">在 `styles.css` 文本编辑器中查看</span><span class="sxs-lookup"><span data-stu-id="56970-163">View `styles.css` in a text editor</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="56970-164">选择“**元素**”工具。</span><span class="sxs-lookup"><span data-stu-id="56970-164">Choose the **Elements** tool.</span></span>  
1.  <span data-ttu-id="56970-165">将 元素的 `color` 属性值 `<h1>` 更改为你最喜爱的颜色。</span><span class="sxs-lookup"><span data-stu-id="56970-165">Change the value of the `color` property of the `<h1>` element to your favorite color.</span></span>  
    <span data-ttu-id="56970-166">请记住，您需要选择 DOM 树中的 元素，才能在"样式"窗格中显示应用于它的 `<h1>` CSS\*\*\*\* 规则。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="56970-166">Remember that you need to choose the `<h1>` element in the **DOM Tree** in order to display the CSS rules applied to it in the **Styles** pane.</span></span>  <span data-ttu-id="56970-167">旁边是绿色 `styles.css:1` 点，表示你进行的任何更改都映射到 `~/Desktop/app/styles.css` 。</span><span class="sxs-lookup"><span data-stu-id="56970-167">The green dot next to `styles.css:1` means that any change that you make are mapped to `~/Desktop/app/styles.css`.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-elements-styles-css.msft.png" alt-text="文件链接的绿色指示器" lightbox="../media/workspaces-workspaces-demo-elements-styles-css.msft.png":::
       <span data-ttu-id="56970-169">文件链接的绿色指示器</span><span class="sxs-lookup"><span data-stu-id="56970-169">The green indicator that the file is linked</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="56970-170">再次 `styles.css` 在文本编辑器中打开。</span><span class="sxs-lookup"><span data-stu-id="56970-170">Open `styles.css` in a text editor again.</span></span>  <span data-ttu-id="56970-171">`color`属性现在设置为你最喜爱的颜色。</span><span class="sxs-lookup"><span data-stu-id="56970-171">The `color` property is now set to your favorite color.</span></span>  
1.  <span data-ttu-id="56970-172">刷新页面。</span><span class="sxs-lookup"><span data-stu-id="56970-172">Refresh the page.</span></span>  <span data-ttu-id="56970-173">元素的颜色 `<h1>` 仍设置为你最喜爱的颜色。</span><span class="sxs-lookup"><span data-stu-id="56970-173">The color of the `<h1>` element is still set to your favorite color.</span></span>  <span data-ttu-id="56970-174">更改将在整个刷新中保留，因为进行更改时 DevTools 将更改保存到磁盘。</span><span class="sxs-lookup"><span data-stu-id="56970-174">The change remains across a refresh, because when you made the change DevTools saved the change to disk.</span></span>  <span data-ttu-id="56970-175">然后，在刷新页面时，本地服务器从磁盘提供文件的修改副本。</span><span class="sxs-lookup"><span data-stu-id="56970-175">And then, when you refreshed the page, your local server served the modified copy of the file from disk.</span></span>  
    
## <a name="step-3-save-an-html-change-to-disk"></a><span data-ttu-id="56970-176">步骤 3：将 HTML 更改保存到磁盘</span><span class="sxs-lookup"><span data-stu-id="56970-176">Step 3: Save an HTML change to disk</span></span>  

### <a name="change-html-from-the-elements-panel"></a><span data-ttu-id="56970-177">从元素面板更改 HTML</span><span class="sxs-lookup"><span data-stu-id="56970-177">Change HTML from the Elements Panel</span></span>  

<span data-ttu-id="56970-178">你可以从元素面板对 html 进行更改，但是对 DOM 树的更改不会保存到磁盘，并且仅影响当前浏览器会话。</span><span class="sxs-lookup"><span data-stu-id="56970-178">You may make changes to the html from the Element Panel, but your changes to the DOM tree are not saved to disk and only effect the current browser session.</span></span>  

<span data-ttu-id="56970-179">DOM 树不是 html。</span><span class="sxs-lookup"><span data-stu-id="56970-179">The DOM tree is not html.</span></span>  

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

### <a name="change-html-from-the-sources-tool"></a><span data-ttu-id="56970-180">从"源"工具更改 HTML</span><span class="sxs-lookup"><span data-stu-id="56970-180">Change HTML from the Sources tool</span></span>  

<span data-ttu-id="56970-181">如果要保存对网页的 HTML 更改， **请使用"源** "工具。</span><span class="sxs-lookup"><span data-stu-id="56970-181">If you want to save a change to the HTML of the webpage, use the **Sources** tool.</span></span>  

1.  <span data-ttu-id="56970-182">导航到 **"源"** 工具。</span><span class="sxs-lookup"><span data-stu-id="56970-182">Navigate to the **Sources** tool.</span></span>  
1.  <span data-ttu-id="56970-183">在左侧 **导航器** (窗格中，) " **页面"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="56970-183">In the **Navigator** pane (on the left), choose the **Page** tab.</span></span>  
1.  <span data-ttu-id="56970-184">选择\*\* (索引) 。 \*\*</span><span class="sxs-lookup"><span data-stu-id="56970-184">Choose **(index)**.</span></span>  <span data-ttu-id="56970-185">将打开页面的 HTML。</span><span class="sxs-lookup"><span data-stu-id="56970-185">The HTML for the page opens.</span></span>  
1.  <span data-ttu-id="56970-186">将`<h1>Workspaces Demo</h1>`替换为`<h1>I ❤️  Cake</h1>`。</span><span class="sxs-lookup"><span data-stu-id="56970-186">Replace `<h1>Workspaces Demo</h1>` with `<h1>I ❤️  Cake</h1>`.</span></span>  <span data-ttu-id="56970-187">查看下图。</span><span class="sxs-lookup"><span data-stu-id="56970-187">Review the following figure.</span></span>  
1.  <span data-ttu-id="56970-188">选择 `Control` + `S` \ (Windows、Linux\) 或 `Command` + `S` \ (macOS\) 保存更改。</span><span class="sxs-lookup"><span data-stu-id="56970-188">Select `Control`+`S` \(Windows, Linux\) or `Command`+`S` \(macOS\) to save the change.</span></span>  
1.  <span data-ttu-id="56970-189">刷新页面。</span><span class="sxs-lookup"><span data-stu-id="56970-189">Refresh the page.</span></span>  <span data-ttu-id="56970-190">`<h1>`刷新页面后，元素将继续显示新文本。</span><span class="sxs-lookup"><span data-stu-id="56970-190">The `<h1>` element continues to display the new text after the page is refreshed.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-sources-page-h1.msft.png" alt-text="从"源"工具更改 HTML" lightbox="../media/workspaces-workspaces-demo-sources-page-h1.msft.png":::
       <span data-ttu-id="56970-192">从"源"工具 **更改** HTML</span><span class="sxs-lookup"><span data-stu-id="56970-192">Change HTML from the **Sources** tool</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="56970-193">打开 `~/Desktop/app/index.html`。</span><span class="sxs-lookup"><span data-stu-id="56970-193">Open `~/Desktop/app/index.html`.</span></span>  <span data-ttu-id="56970-194">元素 `<h1>` 包含新文本。</span><span class="sxs-lookup"><span data-stu-id="56970-194">The `<h1>` element contains the new text.</span></span>  
    
## <a name="step-4-save-a-javascript-change-to-disk"></a><span data-ttu-id="56970-195">步骤 4：将 JavaScript 更改保存到磁盘</span><span class="sxs-lookup"><span data-stu-id="56970-195">Step 4: Save a JavaScript change to disk</span></span>  

<span data-ttu-id="56970-196">使用 DevTools 的代码编辑器的主要位置是 **源** 工具。</span><span class="sxs-lookup"><span data-stu-id="56970-196">The main place to use the code editor of DevTools is the **Sources** tool.</span></span>  <span data-ttu-id="56970-197">但有时你需要在编辑文件时访问其他工具，如**元素**工具或控制台面板。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="56970-197">But sometimes you need to access other tools, such as the **Elements** tool or the **Console** panel, while editing files.</span></span>  <span data-ttu-id="56970-198">当 **任何** 工具打开时，快速源工具仅为你提供 **源** 工具中的编辑器。</span><span class="sxs-lookup"><span data-stu-id="56970-198">The **Quick Source** tool gives you just the editor from the **Sources** tool, while any tool is open.</span></span>  

<span data-ttu-id="56970-199">若要与其他工具一起打开 DevTools 代码编辑器，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="56970-199">To open the DevTools code editor alongside other tools, do the following:</span></span>  

1.  <span data-ttu-id="56970-200">导航到 **"元素"** 工具。</span><span class="sxs-lookup"><span data-stu-id="56970-200">Navigate to the **Elements** tool.</span></span>  
1.  <span data-ttu-id="56970-201">选择 `Control` + `Shift` + `P` \(Windows、Linux\) 或 `Command` + `Shift` + `P` \(macOS\)。</span><span class="sxs-lookup"><span data-stu-id="56970-201">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\).</span></span>  <span data-ttu-id="56970-202">命令 **菜单将** 打开。</span><span class="sxs-lookup"><span data-stu-id="56970-202">The **Command Menu** opens.</span></span>  
1.  <span data-ttu-id="56970-203">键入 `Quick Source` ，然后选择"显示**快速源"。**</span><span class="sxs-lookup"><span data-stu-id="56970-203">Type `Quick Source`, and then choose **Show Quick Source**.</span></span>  <span data-ttu-id="56970-204">在"DevTools"窗口底部，将显示"\*\*\*\* 快速源"工具，其中显示 的内容，这是你在"源"工具中编辑的最后 `index.html` **一**个文件。</span><span class="sxs-lookup"><span data-stu-id="56970-204">At the bottom of the DevTools window, the **Quick Source** tool appears, displaying the contents of `index.html`, which is the last file you edited in the **Sources** tool.</span></span>    
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-search-show-quick-source.msft.png" alt-text="使用命令菜单打开快速源工具" lightbox="../media/workspaces-workspaces-demo-search-show-quick-source.msft.png":::
       <span data-ttu-id="56970-206">使用 **命令菜单** 打开快速 **源工具**</span><span class="sxs-lookup"><span data-stu-id="56970-206">Open the **Quick Source** tool by using the **Command Menu**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="56970-207">选择 `Control` + `P` \ (Windows、Linux\) 或 `Command` + `P` \ (macOS\) 打开 **"打开文件"** 对话框。</span><span class="sxs-lookup"><span data-stu-id="56970-207">Select `Control`+`P` \(Windows, Linux\) or `Command`+`P` \(macOS\) to open the **Open File** dialog.</span></span>  <span data-ttu-id="56970-208">查看下图。</span><span class="sxs-lookup"><span data-stu-id="56970-208">Review the following figure.</span></span>  
1.  <span data-ttu-id="56970-209">键入 `script` ，然后选择 \*\*"app/script.js"。 \*\*</span><span class="sxs-lookup"><span data-stu-id="56970-209">Type `script`, then choose **app/script.js**.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-search-script.msft.png" alt-text="使用script.js文件"对话框打开文件" lightbox="../media/workspaces-workspaces-demo-search-script.msft.png":::
       <span data-ttu-id="56970-211">使用 `script.js` "打开 **文件"对话框** 打开</span><span class="sxs-lookup"><span data-stu-id="56970-211">Open `script.js` using the **Open File** dialog</span></span>  
    :::image-end:::  
    
    > [!NOTE]
    > <span data-ttu-id="56970-212">该 `Save Changes To Disk With Workspaces` 演示中的链接会定期设置样式。</span><span class="sxs-lookup"><span data-stu-id="56970-212">The `Save Changes To Disk With Workspaces` link in the demo is styled regularly.</span></span>  
    
1.  <span data-ttu-id="56970-213">使用快速源工具将以下**代码script.js\*\*\*\*库的底部**。</span><span class="sxs-lookup"><span data-stu-id="56970-213">Add the following code to the bottom of **script.js** using the **Quick Source** tool.</span></span>  
    
    ```javascript
    console.log('greetings from script.js');
    document.querySelector('a').style = 'font-style:italic';
    ```  
    
1.  <span data-ttu-id="56970-214">选择 `Control` + `S` \ (Windows、Linux\) 或 `Command` + `S` \ (macOS\) 保存更改。</span><span class="sxs-lookup"><span data-stu-id="56970-214">Select `Control`+`S` \(Windows, Linux\) or `Command`+`S` \(macOS\) to save the change.</span></span>  
1.  <span data-ttu-id="56970-215">刷新页面。</span><span class="sxs-lookup"><span data-stu-id="56970-215">Refresh the page.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="56970-216">页面上的链接现在为 italicized。</span><span class="sxs-lookup"><span data-stu-id="56970-216">The link on the page is now italicized.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-elements-styles-quick-source-script.msft.png" alt-text="页面上的链接现在为 italicized" lightbox="../media/workspaces-workspaces-demo-elements-styles-quick-source-script.msft.png":::
       <span data-ttu-id="56970-218">页面上的链接现在为 italicized</span><span class="sxs-lookup"><span data-stu-id="56970-218">The link on the page is now italicized</span></span>  
    :::image-end:::  
    
## <a name="next-steps"></a><span data-ttu-id="56970-219">后续步骤</span><span class="sxs-lookup"><span data-stu-id="56970-219">Next steps</span></span>  

<span data-ttu-id="56970-220">使用本教程中学到的内容在你自己的项目中设置工作区。</span><span class="sxs-lookup"><span data-stu-id="56970-220">Use what you have learned in this tutorial to set up Workspaces in your own project.</span></span>  <!-- If you run into any issues or are able to get it working after some custom configuration, please [start a thread in the mailing list][AlphabetGroupsAlphabetBrowserDevTools] or [ask a question on Stack Overflow][StackOverflowAlphabetBrowserDevTools] to share your knowledge with the rest of the DevTools community.  -->  

<!--  
If you have more feedback on the topics or anything else, please use any of the channels below:  

*   [Mailing List][AlphabetGroupsAlphabetBrowserDevTools]  
*   [Twitter][TwitterAlphabetBrowserDevTools]  -->  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="56970-221">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="56970-221">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsCssIndex]: ../css/index.md "开始查看和更改 CSS |Microsoft Docs"  

<!--[LocalOverrides]: ../whats-new/2018/01/devtools#overrides -->  

<!--[AlphabetGroupsAlphabetBrowserDevTools]: https://groups.alphabet.com/forum/#!forum/alphabet-browser-developer-tools "Alphabet Browser DevTools - Alphabet Groups"  -->  

[GlitchWorkspacesDemo]: https://glitch.com/edit/#!/microsoft-edge-chromium-devtools?path=workspaces-demo/index.html:1:0 "Workspaces 演示|小故障"  

[MDNCSSContent]: https://developer.mozilla.org/docs/Web/CSS/content "内容 - CSS：级联样式表|MDN"  
[MDNWebGettingStarted]: https://developer.mozilla.org/docs/Learn/Getting_started_with_the_web "Web 应用程序|MDN"  
[MDNSimpleLocalHTTPServer]: https://developer.mozilla.org/docs/Learn/Common_questions/set_up_a_local_testing_server#Running_a_simple_local_HTTP_server "运行简单的本地 HTTP 服务器|MDN"  
[MDNWebAPIsDOM]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model/Introduction "DOM 简介 - Web API |MDN"  

<!--[StackOverflowAlphabetBrowserDevTools]: https://stackoverflow.com/questions/ask?tags=alphabet-browser-devtools "Alphabet Browser DevTools - Stack Overflow"  -->

[TreehouseBlogSourceMaps]: https://blog.teamtreehouse.com/introduction-source-maps "源地图简介|Treehouse 博客"  

<!-- [TwitterAlphabetBrowserDevTools]: https://twitter.com/alphabetbrowserdevtools "Alphabet Browser DevTools \(@AlphabetBrowserDevTools\) | Twitter"  -->

[WikiPortURLs]: https://en.wikipedia.org/wiki/Port_(computer_networking)#Use_in_URLs "Port \ (computer networking\) - Wikipedia"  

> [!NOTE]
> <span data-ttu-id="56970-230">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="56970-230">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="56970-231">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/workspaces/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="56970-231">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/workspaces/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="56970-233">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="56970-233">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
