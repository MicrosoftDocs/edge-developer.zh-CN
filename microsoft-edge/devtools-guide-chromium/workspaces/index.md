---
title: 使用工作区编辑文件
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/20/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 8a31dd9fbfe492cf8eaacc654f7d501925f730f2
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "10942182"
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

# <span data-ttu-id="b0011-103">使用工作区编辑文件</span><span class="sxs-lookup"><span data-stu-id="b0011-103">Edit files with Workspaces</span></span>  

> [!NOTE]
> <span data-ttu-id="b0011-104">本教程的目标是提供设置和使用工作区的实际实践，以便在你自己的项目中使用工作区。</span><span class="sxs-lookup"><span data-stu-id="b0011-104">The goal of this tutorial is to provide hands-on practice in setting up and using Workspaces, so that you are able to use Workspaces in your own projects.</span></span>  <span data-ttu-id="b0011-105">启用 Workspaces 后，可以保存对源代码（本地计算机上所做的源代码所做的更改）</span><span class="sxs-lookup"><span data-stu-id="b0011-105">You are able to save the changes to the source code, on your local computer, that you made within DevTools after you enable Workspaces.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="b0011-106">**先决条件**：开始此教程之前，你应知道如何执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="b0011-106">**Prerequisites**: Before beginning this tutorial, you should know how to perform the following actions.</span></span>  
> 
> *   [<span data-ttu-id="b0011-107">使用 html、CSS 和 JavaScript 构建网页</span><span class="sxs-lookup"><span data-stu-id="b0011-107">Use html, CSS, and JavaScript to build a web page</span></span>][MDNWebGettingStarted]  
> *   [<span data-ttu-id="b0011-108">使用 DevTools 对 CSS 进行基本更改</span><span class="sxs-lookup"><span data-stu-id="b0011-108">Use DevTools to make basic changes to CSS</span></span>][DevToolsCssIndex]  
> *   [<span data-ttu-id="b0011-109">运行本地 HTTP Web 服务器</span><span class="sxs-lookup"><span data-stu-id="b0011-109">Run a local HTTP web server</span></span>][MDNSimpleLocalHTTPServer]  

## <span data-ttu-id="b0011-110">概述</span><span class="sxs-lookup"><span data-stu-id="b0011-110">Overview</span></span>  

<span data-ttu-id="b0011-111">利用工作区，您可以将 Devtools 中的更改保存到计算机上的相同文件的本地副本中。</span><span class="sxs-lookup"><span data-stu-id="b0011-111">Workspaces enable you to save a change that you make in Devtools to a local copy of the same file on your computer.</span></span>  <span data-ttu-id="b0011-112">在本教程中，应在计算机上具有以下设置。</span><span class="sxs-lookup"><span data-stu-id="b0011-112">For this tutorial, you should have the following settings on your machine.</span></span>  

*   <span data-ttu-id="b0011-113">在桌面上具有网站的源代码。</span><span class="sxs-lookup"><span data-stu-id="b0011-113">You have the source code for your site on your desktop.</span></span>  
*   <span data-ttu-id="b0011-114">你运行的是源代码目录的本地 Web 服务器，以便网站可在访问 `localhost:8080` 。</span><span class="sxs-lookup"><span data-stu-id="b0011-114">You are running a local web server from the source code directory, so that the site is accessible at `localhost:8080`.</span></span>  
*   <span data-ttu-id="b0011-115">你在 `localhost:8080` Microsoft Edge 中打开并使用 DevTools 更改该网站的 CSS。</span><span class="sxs-lookup"><span data-stu-id="b0011-115">You opened `localhost:8080` in Microsoft Edge, and you are using DevTools to change the CSS of the site.</span></span>  

<span data-ttu-id="b0011-116">启用工作区后，在 DevTools 中进行的 CSS 更改会保存到桌面上的源代码中。</span><span class="sxs-lookup"><span data-stu-id="b0011-116">With Workspaces enabled, the CSS changes that you make within DevTools are saved to the source code on your desktop.</span></span>  

## <span data-ttu-id="b0011-117">限制</span><span class="sxs-lookup"><span data-stu-id="b0011-117">Limitations</span></span>  

<span data-ttu-id="b0011-118">如果你使用的是现代框架，它可能不会将源代码转换为易于维护的格式，该格式已尽可能快速运行。</span><span class="sxs-lookup"><span data-stu-id="b0011-118">If you are using a modern framework, it probably transforms your source code from a format that is easy to maintain into a format that is optimized to run as quickly as possible.</span></span>  

<span data-ttu-id="b0011-119">工作区通常能够借助源映射的帮助将优化的代码映射回原 [始源代码][TreehouseBlogSourceMaps]。</span><span class="sxs-lookup"><span data-stu-id="b0011-119">Workspaces is usually able to map the optimized code back to your original source code with the help of [source maps][TreehouseBlogSourceMaps].</span></span>  <span data-ttu-id="b0011-120">但是每个框架之间有许多差别，超过了每个位图的使用方式。</span><span class="sxs-lookup"><span data-stu-id="b0011-120">But there is a lot of variation between frameworks over how each uses source maps.</span></span>  <span data-ttu-id="b0011-121">Devtools 只支持所有变体。</span><span class="sxs-lookup"><span data-stu-id="b0011-121">Devtools simply does support all of the variations.</span></span>  

<span data-ttu-id="b0011-122">已知工作区不使用以下框架。</span><span class="sxs-lookup"><span data-stu-id="b0011-122">Workspaces is known to not work with the following framework.</span></span>  

*   <span data-ttu-id="b0011-123">创建回收应用</span><span class="sxs-lookup"><span data-stu-id="b0011-123">Create React App</span></span>  

    <!-- If you run into issues while using Workspaces with your framework of choice, or you get it working after some custom configuration, please [start a thread in the mailing list][AlphabetGroupsAlphabetBrowserDevTools] or [ask a question on Stack Overflow][StackOverflowAlphabetBrowserDevTools] to share your knowledge with the rest of the DevTools community.  -->  
    
## <span data-ttu-id="b0011-124">相关功能：本地覆盖</span><span class="sxs-lookup"><span data-stu-id="b0011-124">Related feature: Local overrides</span></span>  

<span data-ttu-id="b0011-125">**本地替代是另** 一个 DevTools 功能，它类似工作区。</span><span class="sxs-lookup"><span data-stu-id="b0011-125">**Local Overrides** is another DevTools feature that is similar to Workspaces.</span></span>  <span data-ttu-id="b0011-126">如果您试图对页面的更改进行更改，并且需要在页面加载中看到更改，但是不需更改使页面源代码映射到页面的源代码，请使用本地覆盖。</span><span class="sxs-lookup"><span data-stu-id="b0011-126">Use Local Overrides when you want to experiment with changes to a page, and you need to see the changes across page loads, but you do not care about mapping your changes to the source code of the page.</span></span>  

<!--Todo: add section when content is ready  -->  

## <span data-ttu-id="b0011-127">步骤 1：设置</span><span class="sxs-lookup"><span data-stu-id="b0011-127">Step 1: Set up</span></span>  

<span data-ttu-id="b0011-128">完成以下操作，以获得使用工作区的动手体验。</span><span class="sxs-lookup"><span data-stu-id="b0011-128">Complete the following actions, to get hands-on experience with Workspaces.</span></span>  

### <span data-ttu-id="b0011-129">设置演示</span><span class="sxs-lookup"><span data-stu-id="b0011-129">Set up the demo</span></span>  

1.  <span data-ttu-id="b0011-130">[打开演示][GlitchWorkspacesDemo]。</span><span class="sxs-lookup"><span data-stu-id="b0011-130">[Open the demo][GlitchWorkspacesDemo].</span></span>  <!--In the top-left of the editor, a randomly-generated project name is displayed.  -->  
    
    :::image type="complex" source="../media/workspaces-glitch-workspaces-demo-source.msft.png" alt-text="Glitch 项目" lightbox="../media/workspaces-glitch-workspaces-demo-source.msft.png":::
       <span data-ttu-id="b0011-132">Glitch 项目</span><span class="sxs-lookup"><span data-stu-id="b0011-132">A Glitch project</span></span>  
    :::image-end:::  
    
    <!--1.  Choose the project name.  -->  
    <!--1.  Select **Advanced Options** > **Download Project**.  
    
    :::image type="complex" source="../media/workspaces-glitch-advanced-options-download-project.msft.png" alt-text="The Download Project button" lightbox="../media/workspaces-glitch-advanced-options-download-project.msft.png":::
       The Download Project button  
    :::image-end:::  

    -->  
    <!--1.  Close the tab.  -->  
    <!--1.  Unzip the source code and move the unzipped `app` directory to your desktop.  For the rest of this tutorial the unzipped directory is referred to as `~/Desktop/app`.  -->  
    
1.  <span data-ttu-id="b0011-133">在 `app` 桌面上创建目录。</span><span class="sxs-lookup"><span data-stu-id="b0011-133">Create an `app` directory on your desktop.</span></span>  <span data-ttu-id="b0011-134">将文件的副本从目录 `workspaces-demo` 保存到 `app` 目录。</span><span class="sxs-lookup"><span data-stu-id="b0011-134">Save copies of the files from the `workspaces-demo` directory to the `app` directory.</span></span>  <span data-ttu-id="b0011-135">对于教程的其余部分，该目录称为 `~/Desktop/app` ：</span><span class="sxs-lookup"><span data-stu-id="b0011-135">For the rest of the tutorial, the directory is referred to as `~/Desktop/app`.</span></span>  
1.  <span data-ttu-id="b0011-136">启动本地 Web 服务器 `~/Desktop/app` 。</span><span class="sxs-lookup"><span data-stu-id="b0011-136">Start a local web server in `~/Desktop/app`.</span></span>  <span data-ttu-id="b0011-137">以下是一些示例代码，用于起起 `SimpleHTTPServer` ，你可以使用你喜欢的几个服务器。</span><span class="sxs-lookup"><span data-stu-id="b0011-137">Below is some sample code for starting up `SimpleHTTPServer`, but you may use whatever server you prefer.</span></span>  
    
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
    
1.  <span data-ttu-id="b0011-138">在 Microsoft Edge 中打开选项卡，转到该网站的本地托管版本。</span><span class="sxs-lookup"><span data-stu-id="b0011-138">Open a tab in Microsoft Edge and go to locally-hosted version of the site.</span></span>  <span data-ttu-id="b0011-139">你应当能够使用您的 URL 或以下 URL `localhost:8080` 访问它 `http://0.0.0.0:8080` 。</span><span class="sxs-lookup"><span data-stu-id="b0011-139">You should be able to access it using a URL like `localhost:8080` or `http://0.0.0.0:8080`.</span></span>  <span data-ttu-id="b0011-140">确实的端口 [号可能][WikiPortURLs] 不同。</span><span class="sxs-lookup"><span data-stu-id="b0011-140">The exact [port number][WikiPortURLs] may be different.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo.msft.png" alt-text="演示版" lightbox="../media/workspaces-workspaces-demo.msft.png":::
       <span data-ttu-id="b0011-142">演示版</span><span class="sxs-lookup"><span data-stu-id="b0011-142">The demo</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="b0011-143">设置 DevTools</span><span class="sxs-lookup"><span data-stu-id="b0011-143">Set up DevTools</span></span>  

1.  <span data-ttu-id="b0011-144">选择 `Control` + `Shift` + `J` \ (Windows\) 或 `Command` + `Option` + `J` \ (macOS\) 以打开 DevTools 的控制台面板。 **Console**</span><span class="sxs-lookup"><span data-stu-id="b0011-144">Select `Control`+`Shift`+`J` \(Windows\) or `Command`+`Option`+`J` \(macOS\) to open the **Console** panel of DevTools.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-console.msft.png" alt-text="主机面板" lightbox="../media/workspaces-workspaces-demo-console.msft.png":::
       <span data-ttu-id="b0011-146">**主机面**板</span><span class="sxs-lookup"><span data-stu-id="b0011-146">The **Console** panel</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="b0011-147">选择" **源"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="b0011-147">Choose the **Sources** tab.</span></span>  
1.  <span data-ttu-id="b0011-148">选择" **文件系统"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="b0011-148">Choose the **Filesystem** tab.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-sources-filesystem.msft.png" alt-text=""文件系统"选项卡" lightbox="../media/workspaces-workspaces-demo-sources-filesystem.msft.png":::
       <span data-ttu-id="b0011-150">" **文件系统"** 选项卡</span><span class="sxs-lookup"><span data-stu-id="b0011-150">The **Filesystem** tab</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="b0011-151">选择 **"将文件夹添加到工作区**"。</span><span class="sxs-lookup"><span data-stu-id="b0011-151">Choose **Add Folder To Workspace**.</span></span>  
1.  <span data-ttu-id="b0011-152">键入 `~/Desktop/app`。</span><span class="sxs-lookup"><span data-stu-id="b0011-152">Type `~/Desktop/app`.</span></span>  
1.  <span data-ttu-id="b0011-153">选择 **"允** 许"授予 DevTools 同步同步和写入目录的权限。</span><span class="sxs-lookup"><span data-stu-id="b0011-153">Choose **Allow** to give DevTools permission to read and write to the directory.</span></span>  
    <span data-ttu-id="b0011-154">在" **文件系统"** 选项卡中，旁边有绿点， `index.html` 此标记出 `script.js` 来 `styles.css` 。</span><span class="sxs-lookup"><span data-stu-id="b0011-154">In the **Filesystem** tab, there is now a green dot next to `index.html`, `script.js`, and `styles.css`.</span></span>  <span data-ttu-id="b0011-155">这些绿色点意味着 DevTools 已在页面的网络资源和其中的文件之间建立了映射 `~/Desktop/app` 。</span><span class="sxs-lookup"><span data-stu-id="b0011-155">These green dots mean that DevTools has established a mapping between the network resources of the page, and the files in `~/Desktop/app`.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-sources-filesystem-folder.msft.png" alt-text=""文件系统"选项卡现在显示本地文件与网络之间的映射" lightbox="../media/workspaces-workspaces-demo-sources-filesystem-folder.msft.png":::
       <span data-ttu-id="b0011-157">" **文件系统** "选项卡现在显示本地文件与网络之间的映射</span><span class="sxs-lookup"><span data-stu-id="b0011-157">The **Filesystem** tab now shows a mapping between the local files and the network ones</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="b0011-158">步骤 2：保存 CSS 更改为光盘</span><span class="sxs-lookup"><span data-stu-id="b0011-158">Step 2: Save a CSS change to disk</span></span>  

1.  <span data-ttu-id="b0011-159">打开 `styles.css`。</span><span class="sxs-lookup"><span data-stu-id="b0011-159">Open `styles.css`.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="b0011-160">`color`元素 `h1` 的属性设置为 `fuchsia` ：</span><span class="sxs-lookup"><span data-stu-id="b0011-160">The `color` property of `h1` elements is set to `fuchsia`.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-sources-filesystem-css.msft.png" alt-text="在文本编辑器中查看 styles.css" lightbox="../media/workspaces-workspaces-demo-sources-filesystem-css.msft.png":::
       <span data-ttu-id="b0011-162">在 `styles.css` 文本编辑器中查看</span><span class="sxs-lookup"><span data-stu-id="b0011-162">View `styles.css` in a text editor</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="b0011-163">选择" **元素"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="b0011-163">Choose the **Elements** tab.</span></span>  
1.  <span data-ttu-id="b0011-164">将该元素 `color` 的属性 `<h1>` 值更改为你喜藏的颜色。</span><span class="sxs-lookup"><span data-stu-id="b0011-164">Change the value of the `color` property of the `<h1>` element to your favorite color.</span></span>  
    <span data-ttu-id="b0011-165">请记住，你需要在 `<h1>` **DOM 对** 该元素进行选择，才能在"样式"窗格中查看应用于它 **的** CSS 规则。</span><span class="sxs-lookup"><span data-stu-id="b0011-165">Remember that you need to choose the `<h1>` element in the **DOM Tree** in order to see the CSS rules applied to it in the **Styles** pane.</span></span>  <span data-ttu-id="b0011-166">旁边的绿点 `styles.css:1` 表示你所做的任何更改都映射到 `~/Desktop/app/styles.css` 了。</span><span class="sxs-lookup"><span data-stu-id="b0011-166">The green dot next to `styles.css:1` means that any change that you make are mapped to `~/Desktop/app/styles.css`.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-elements-styles-css.msft.png" alt-text="链接文件的绿色指示器" lightbox="../media/workspaces-workspaces-demo-elements-styles-css.msft.png":::
       <span data-ttu-id="b0011-168">链接文件的绿色指示器</span><span class="sxs-lookup"><span data-stu-id="b0011-168">The green indicator that the file is linked</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="b0011-169">再次 `styles.css` 在文本编辑器中打开。</span><span class="sxs-lookup"><span data-stu-id="b0011-169">Open `styles.css` in a text editor again.</span></span>  <span data-ttu-id="b0011-170">`color`属性现已设置为收藏的颜色。</span><span class="sxs-lookup"><span data-stu-id="b0011-170">The `color` property is now set to your favorite color.</span></span>  
1.  <span data-ttu-id="b0011-171">刷新页面。</span><span class="sxs-lookup"><span data-stu-id="b0011-171">Refresh the page.</span></span>  <span data-ttu-id="b0011-172">元素的 `<h1>` 颜色仍设置为你最喜去的颜色。</span><span class="sxs-lookup"><span data-stu-id="b0011-172">The color of the `<h1>` element is still set to your favorite color.</span></span>  <span data-ttu-id="b0011-173">更改将保留在刷新周围，因为当您使更改 DevTools 保存到了视频台时。</span><span class="sxs-lookup"><span data-stu-id="b0011-173">The change remains across a refresh, because when you made the change DevTools saved the change to disk.</span></span>  <span data-ttu-id="b0011-174">然后，刷新页面时，本地服务器已从盘修改了该文件的副本。</span><span class="sxs-lookup"><span data-stu-id="b0011-174">And then, when you refreshed the page, your local server served the modified copy of the file from disk.</span></span>  
    
## <span data-ttu-id="b0011-175">步骤 3：将 HTML 更改保存到光盘</span><span class="sxs-lookup"><span data-stu-id="b0011-175">Step 3: Save an HTML change to disk</span></span>  

### <span data-ttu-id="b0011-176">从"元素面板"中更改 HTML</span><span class="sxs-lookup"><span data-stu-id="b0011-176">Change HTML from the Elements Panel</span></span>  

<span data-ttu-id="b0011-177">你可能会从"元素面板"更改 html，但是对 DOM 的更改不会保存到文件盘，只会有当前的浏览器会话生效。</span><span class="sxs-lookup"><span data-stu-id="b0011-177">You may make changes to the html from the Element Panel, but your changes to the DOM tree are not saved to disk and only effect the current browser session.</span></span>  

<span data-ttu-id="b0011-178">DOM 的项目不是 HTML 的。</span><span class="sxs-lookup"><span data-stu-id="b0011-178">The DOM tree is not html.</span></span>  

<!--### Try changing HTML from the Elements panel  

> [!WARNING]
> The workflow that you are about to try does not work.  You are trying it now so that you do not waste time later trying to figure out why it is not working.  

1.  Choose the **Elements** tab.  
1.  Choose and edit the text content of the `h1` element, which says `Workspaces Demo`, and replace it with `I ❤️  Cake`.  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-change-h1.msft.png" alt-text="Attempt to change html from the DOM Tree of the Elements panel" lightbox="../media/workspaces-workspaces-demo-change-h1.msft.png":::
       Attempt to change html from the DOM Tree of the **Elements** panel  
    :::image-end:::  
    
1.  Open `~/Desktop/app/index.html` in a text editor.  The change that you just made does not appear.  
1.  Refresh the page.  The page reverts to the original title.  
    
#### Optional: Why it is not working  

> [!NOTE]
> This section describes why the workflow from [Try changing html from the Elements panel](#try-changing-html-from-the-elements-panel) does not work.  You should skip this section if you do not care why.  

*   The tree of nodes that you see on the **Elements** panel represents the [DOM][MDNWebAPIsDOM] of the page.  
*   To display a page, a browser fetches html over the network, parses the html, and then converts it into a tree of DOM nodes.  
*   If the page has any JavaScript, that JavaScript may add, delete, or change DOM nodes.  CSS may change the DOM, too, using the [`content`][MDNCSSContent] property.  
*   The browser eventually uses the DOM to determine what content it should present to browser users.  
*   Therefore, the final state of the page that users see may be very different from the html that the browser fetched.  
*   This makes it difficult for DevTools to resolve where a change made in the **Elements** panel should be saved, because the DOM is affected by HTML, JavaScript, and CSS.  

In short, the **DOM Tree** `!==` HTML.  
-->  

### <span data-ttu-id="b0011-179">从"源"面板更改 HTML</span><span class="sxs-lookup"><span data-stu-id="b0011-179">Change HTML from the Sources panel</span></span>  

<span data-ttu-id="b0011-180">如果要保存对页面的 html 的更改，可使用"源"面 **板进行** 操作。</span><span class="sxs-lookup"><span data-stu-id="b0011-180">If you want to save a change to the html of the page, do it using the **Sources** panel.</span></span>  

1.  <span data-ttu-id="b0011-181">选择" **源"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="b0011-181">Choose the **Sources** tab.</span></span>  
1.  <span data-ttu-id="b0011-182">选择" **页"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="b0011-182">Choose the **Page** tab.</span></span>  
1.  <span data-ttu-id="b0011-183">从\*\* (索) 。 \*\*</span><span class="sxs-lookup"><span data-stu-id="b0011-183">Choose **(index)**.</span></span>  <span data-ttu-id="b0011-184">此时将打开该页面的 HTML。</span><span class="sxs-lookup"><span data-stu-id="b0011-184">The HTML for the page opens.</span></span>  
1.  <span data-ttu-id="b0011-185">用 `<h1>I ❤️  Cake</h1>` 取代 `<h1>Workspaces Demo</h1>`。</span><span class="sxs-lookup"><span data-stu-id="b0011-185">Replace `<h1>Workspaces Demo</h1>` with `<h1>I ❤️  Cake</h1>`.</span></span>  <span data-ttu-id="b0011-186">参见下图。</span><span class="sxs-lookup"><span data-stu-id="b0011-186">See the following figure.</span></span>  
1.  <span data-ttu-id="b0011-187">选择 `Control` + `S` \ (Windows\) 或 `Command` + `S` \ (macOS\) 以保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="b0011-187">Select `Control`+`S` \(Windows\) or `Command`+`S` \(macOS\) to save the change.</span></span>  
1.  <span data-ttu-id="b0011-188">刷新页面。</span><span class="sxs-lookup"><span data-stu-id="b0011-188">Refresh the page.</span></span>  <span data-ttu-id="b0011-189">元素 `<h1>` 仍然显示新文本。</span><span class="sxs-lookup"><span data-stu-id="b0011-189">The `<h1>` element is still displaying the new text.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-sources-page-h1.msft.png" alt-text="从"源"面板更改 HTML" lightbox="../media/workspaces-workspaces-demo-sources-page-h1.msft.png":::
       <span data-ttu-id="b0011-191">从"源" **面板更改** HTML</span><span class="sxs-lookup"><span data-stu-id="b0011-191">Change HTML from the **Sources** panel</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="b0011-192">打开 `~/Desktop/app/index.html`。</span><span class="sxs-lookup"><span data-stu-id="b0011-192">Open `~/Desktop/app/index.html`.</span></span>  <span data-ttu-id="b0011-193">元素 `<h1>` 包含新的文本。</span><span class="sxs-lookup"><span data-stu-id="b0011-193">The `<h1>` element contains the new text.</span></span>  
    
## <span data-ttu-id="b0011-194">步骤 4：将 JavaScript 更改保存到该面盘</span><span class="sxs-lookup"><span data-stu-id="b0011-194">Step 4: Save a JavaScript change to disk</span></span>  

<span data-ttu-id="b0011-195">" **源"** 面板也是对 JavaScript 进行更改的位置。</span><span class="sxs-lookup"><span data-stu-id="b0011-195">The **Sources** panel is also the place to make changes to JavaScript.</span></span>  <span data-ttu-id="b0011-196">但有时，在对网站进行更改时，您需要访问其他面**Elements**板，如元素面板**Console**或主机面板。</span><span class="sxs-lookup"><span data-stu-id="b0011-196">But sometimes you need to access other panels, such as the **Elements** panel or the **Console** panel, while making changes to your site.</span></span>  <span data-ttu-id="b0011-197">可通过一种方法将 **"源"面板** 与其他面板一起打开。</span><span class="sxs-lookup"><span data-stu-id="b0011-197">There is a way to have the **Sources** panel open alongside other panels.</span></span>  

1.  <span data-ttu-id="b0011-198">选择" **元素"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="b0011-198">Choose the **Elements** tab.</span></span>  
1.  <span data-ttu-id="b0011-199">选择 `Control` + `Shift` + `P` \ (Windows\) 或 `Command` + `Shift` + `P` \ (macOS\) 。</span><span class="sxs-lookup"><span data-stu-id="b0011-199">Select `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\).</span></span>  <span data-ttu-id="b0011-200">此 **时将打开** 命令菜单。</span><span class="sxs-lookup"><span data-stu-id="b0011-200">The **Command Menu** opens.</span></span>  
1.  <span data-ttu-id="b0011-201">键入 `QS` ，然后选择" **显示快速源**"。</span><span class="sxs-lookup"><span data-stu-id="b0011-201">Type `QS`, then select **Show Quick Source**.</span></span>  <span data-ttu-id="b0011-202">在"开发工具"窗口底部，现在有一个"快速 **源"** 选项卡。 该选项卡显示内容，该选项卡 `index.html` 是你在源面板中编辑过 **的最后** 一个文件。</span><span class="sxs-lookup"><span data-stu-id="b0011-202">At the bottom of your DevTools window there is now a **Quick Source** tab.  The tab is displaying the contents of `index.html`, which is the last file you edited in the **Sources** panel.</span></span>  <span data-ttu-id="b0011-203">通过 **"快速** 来源"选项卡可从"源"面 **板向** 你提供编辑器，以便你能够在打开其他面板的同时编辑文件。</span><span class="sxs-lookup"><span data-stu-id="b0011-203">The **Quick Source** tab gives you the editor from the **Sources** panel, so that you are able to edit files while having other panels open.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-search-show-quick-source.msft.png" alt-text="使用命令菜单打开"快速源"选项卡" lightbox="../media/workspaces-workspaces-demo-search-show-quick-source.msft.png":::
       <span data-ttu-id="b0011-205">使用命令 **菜单打开** "快速源 **"选项卡**</span><span class="sxs-lookup"><span data-stu-id="b0011-205">Open the **Quick Source** tab using **Command Menu**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="b0011-206">选择 `Control` + `P` \ (Windows\) 或 `Command` + `P` \ (macOS\) 以打开 **"打开文件"** 对话框。</span><span class="sxs-lookup"><span data-stu-id="b0011-206">Select `Control`+`P` \(Windows\) or `Command`+`P` \(macOS\) to open the **Open File** dialog.</span></span>  <span data-ttu-id="b0011-207">参见下图。</span><span class="sxs-lookup"><span data-stu-id="b0011-207">See the following figure.</span></span>  
1.  <span data-ttu-id="b0011-208">键入 `script` ，然后选择\*\*应用/script.js。 \*\*</span><span class="sxs-lookup"><span data-stu-id="b0011-208">Type `script`, then select **app/script.js**.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-search-script.msft.png" alt-text="使用script.js"打开文件"对话框打开文件" lightbox="../media/workspaces-workspaces-demo-search-script.msft.png":::
       <span data-ttu-id="b0011-210">使用 `script.js` "打开**文件"对话框打开**</span><span class="sxs-lookup"><span data-stu-id="b0011-210">Open `script.js` using the **Open File** dialog</span></span>  
    :::image-end:::  
    
    > [!NOTE]
    > <span data-ttu-id="b0011-211">`Save Changes To Disk With Workspaces`演示中的链接定期设置格式。</span><span class="sxs-lookup"><span data-stu-id="b0011-211">The `Save Changes To Disk With Workspaces` link in the demo is styled regularly.</span></span>  
    
1.  <span data-ttu-id="b0011-212">使用"快速源"选项卡将 \*\* 下列script.js\*\* 添加到 **联系人的底** 部。</span><span class="sxs-lookup"><span data-stu-id="b0011-212">Add the following code to the bottom of **script.js** using the **Quick Source** tab.</span></span>  
    
    ```javascript
    console.log('greetings from script.js');
    document.querySelector('a').style = 'font-style:italic';
    ```  
    
1.  <span data-ttu-id="b0011-213">选择 `Control` + `S` \ (Windows\) 或 `Command` + `S` \ (macOS\) 以保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="b0011-213">Select `Control`+`S` \(Windows\) or `Command`+`S` \(macOS\) to save the change.</span></span>  
1.  <span data-ttu-id="b0011-214">刷新页面。</span><span class="sxs-lookup"><span data-stu-id="b0011-214">Refresh the page.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="b0011-215">页面上的链接现在将被斜体。</span><span class="sxs-lookup"><span data-stu-id="b0011-215">The link on the page is now italicized.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-elements-styles-quick-source-script.msft.png" alt-text="现在即可将页面上的链接斜体" lightbox="../media/workspaces-workspaces-demo-elements-styles-quick-source-script.msft.png":::
       <span data-ttu-id="b0011-217">现在即可将页面上的链接斜体</span><span class="sxs-lookup"><span data-stu-id="b0011-217">The link on the page is now italicized</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="b0011-218">后续步骤</span><span class="sxs-lookup"><span data-stu-id="b0011-218">Next steps</span></span>  

<span data-ttu-id="b0011-219">使用本教程中学到的产品在你自己的项目中设置工作区。</span><span class="sxs-lookup"><span data-stu-id="b0011-219">Use what you have learned in this tutorial to set up Workspaces in your own project.</span></span>  <!-- If you run into any issues or are able to get it working after some custom configuration, please [start a thread in the mailing list][AlphabetGroupsAlphabetBrowserDevTools] or [ask a question on Stack Overflow][StackOverflowAlphabetBrowserDevTools] to share your knowledge with the rest of the DevTools community.  -->  

<!--  
If you have more feedback on the topics or anything else, please use any of the channels below:  

*   [Mailing List][AlphabetGroupsAlphabetBrowserDevTools]  
*   [Twitter][TwitterAlphabetBrowserDevTools]  
    -->  

<!-- links -->  

[DevToolsCssIndex]: ../css/index.md "查看和更改 CSS 入门 |Microsoft 文档"  

<!--[LocalOverrides]: ../whats-new/2018/01/devtools#overrides -->  

<!--[AlphabetGroupsAlphabetBrowserDevTools]: https://groups.alphabet.com/forum/#!forum/alphabet-browser-developer-tools "Alphabet Browser DevTools - Alphabet Groups"  -->  

[GlitchWorkspacesDemo]: https://glitch.com/edit/#!/microsoft-edge-chromium-devtools?path=workspaces-demo/index.html:1:0 "Workspaces 演示文件 |Glitch"  

[MDNCSSContent]: https://developer.mozilla.org/docs/Web/CSS/content "内容 - CSS：级集样式表 |MDN"  
[MDNWebGettingStarted]: https://developer.mozilla.org/docs/Learn/Getting_started_with_the_web "Web | 入门 |MDN"  
[MDNSimpleLocalHTTPServer]: https://developer.mozilla.org/docs/Learn/Common_questions/set_up_a_local_testing_server#Running_a_simple_local_HTTP_server "运行简单的本地 HTTP 服务器 |MDN"  
[MDNWebAPIsDOM]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model/Introduction "DOM 简介 - Web API |MDN"  

<!--[StackOverflowAlphabetBrowserDevTools]: https://stackoverflow.com/questions/ask?tags=alphabet-browser-devtools "Alphabet Browser DevTools - Stack Overflow"  -->

[TreehouseBlogSourceMaps]: https://blog.teamtreehouse.com/introduction-source-maps "源地图简介 |Treehouse 博客"  

<!-- [TwitterAlphabetBrowserDevTools]: https://twitter.com/alphabetbrowserdevtools "Alphabet Browser DevTools \(@AlphabetBrowserDevTools\) | Twitter"  -->

[WikiPortURLs]: https://en.wikipedia.org/wiki/Port_(computer_networking)#Use_in_URLs "端口 \ (计算机网络\) - 维网"  

> [!NOTE]
> <span data-ttu-id="b0011-228">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="b0011-228">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="b0011-229">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/workspaces/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="b0011-229">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/workspaces/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="b0011-231">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="b0011-231">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
