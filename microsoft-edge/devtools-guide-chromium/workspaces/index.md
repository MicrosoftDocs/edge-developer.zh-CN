---
title: 编辑具有工作区的文件
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/14/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 6971dd96a0d2f32700a8d791f7debfc816887387
ms.sourcegitcommit: 054ad92f0b8f9a15da1e3aed32e8f4379b10860f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/15/2020
ms.locfileid: "10931229"
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

# <span data-ttu-id="643a9-103">编辑具有工作区的文件</span><span class="sxs-lookup"><span data-stu-id="643a9-103">Edit files with Workspaces</span></span>  

> [!NOTE]
> <span data-ttu-id="643a9-104">本教程的目标是提供有关设置和使用工作区的动手练习，以便你可以在自己的项目中使用工作区。</span><span class="sxs-lookup"><span data-stu-id="643a9-104">The goal of this tutorial is to provide hands-on practice in setting up and using Workspaces, so that you are able to use Workspaces in your own projects.</span></span>  <span data-ttu-id="643a9-105">你可以在启用工作区后将对源代码所做的更改保存在你的本地计算机上 DevTools 中。</span><span class="sxs-lookup"><span data-stu-id="643a9-105">You are able to save the changes to the source code, on your local computer, that you made within DevTools after you enable Workspaces.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="643a9-106">**先决条件**：在开始本教程之前，你应该知道如何执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="643a9-106">**Prerequisites**: Before beginning this tutorial, you should know how to perform the following actions.</span></span>  
> 
> *   [<span data-ttu-id="643a9-107">使用 html、CSS 和 JavaScript 构建网页</span><span class="sxs-lookup"><span data-stu-id="643a9-107">Use html, CSS, and JavaScript to build a web page</span></span>][MDNWebGettingStarted]  
> *   [<span data-ttu-id="643a9-108">使用 DevTools 对 CSS 进行基本更改</span><span class="sxs-lookup"><span data-stu-id="643a9-108">Use DevTools to make basic changes to CSS</span></span>][DevToolsCssIndex]  
> *   [<span data-ttu-id="643a9-109">运行本地 HTTP web 服务器</span><span class="sxs-lookup"><span data-stu-id="643a9-109">Run a local HTTP web server</span></span>][MDNSimpleLocalHTTPServer]  

## <span data-ttu-id="643a9-110">概述</span><span class="sxs-lookup"><span data-stu-id="643a9-110">Overview</span></span>  

<span data-ttu-id="643a9-111">工作区使你能够将在 Devtools 中所做的更改保存到计算机上同一文件的本地副本。</span><span class="sxs-lookup"><span data-stu-id="643a9-111">Workspaces enable you to save a change that you make in Devtools to a local copy of the same file on your computer.</span></span>  <span data-ttu-id="643a9-112">对于本教程，你的计算机上应具有以下设置。</span><span class="sxs-lookup"><span data-stu-id="643a9-112">For this tutorial, you should have the following settings on your machine.</span></span>  

*   <span data-ttu-id="643a9-113">您的桌面网站上有您的网站的源代码。</span><span class="sxs-lookup"><span data-stu-id="643a9-113">You have the source code for your site on your desktop.</span></span>  
*   <span data-ttu-id="643a9-114">您从源代码目录运行本地 web 服务器，以便可以在该网站上访问 `localhost:8080` 。</span><span class="sxs-lookup"><span data-stu-id="643a9-114">You are running a local web server from the source code directory, so that the site is accessible at `localhost:8080`.</span></span>  
*   <span data-ttu-id="643a9-115">您 `localhost:8080` 在 Microsoft Edge 中打开，并且您使用 DevTools 更改网站的 CSS。</span><span class="sxs-lookup"><span data-stu-id="643a9-115">You opened `localhost:8080` in Microsoft Edge, and you are using DevTools to change the CSS of the site.</span></span>  

<span data-ttu-id="643a9-116">启用了工作区后，在 DevTools 内所做的 CSS 更改将保存到桌面上的源代码中。</span><span class="sxs-lookup"><span data-stu-id="643a9-116">With Workspaces enabled, the CSS changes that you make within DevTools are saved to the source code on your desktop.</span></span>  

## <span data-ttu-id="643a9-117">限制</span><span class="sxs-lookup"><span data-stu-id="643a9-117">Limitations</span></span>  

<span data-ttu-id="643a9-118">如果你使用的是新式框架，则可能会将你的源代码从易于维护的格式转换为尽可能快地运行的格式。</span><span class="sxs-lookup"><span data-stu-id="643a9-118">If you are using a modern framework, it probably transforms your source code from a format that is easy to maintain into a format that is optimized to run as quickly as possible.</span></span>  

<span data-ttu-id="643a9-119">工作区通常能够将经过优化的代码映射回原始源代码以及 [源映射][TreehouseBlogSourceMaps]的帮助。</span><span class="sxs-lookup"><span data-stu-id="643a9-119">Workspaces is usually able to map the optimized code back to your original source code with the help of [source maps][TreehouseBlogSourceMaps].</span></span>  <span data-ttu-id="643a9-120">但是，在每个框架间使用源映射的方式之间存在许多变化。</span><span class="sxs-lookup"><span data-stu-id="643a9-120">But there is a lot of variation between frameworks over how each uses source maps.</span></span>  <span data-ttu-id="643a9-121">Devtools 只支持所有变体。</span><span class="sxs-lookup"><span data-stu-id="643a9-121">Devtools simply does support all of the variations.</span></span>  

<span data-ttu-id="643a9-122">适用于以下框架的工作区已知不起作用。</span><span class="sxs-lookup"><span data-stu-id="643a9-122">Workspaces is known to not work with the following framework.</span></span>  

*   <span data-ttu-id="643a9-123">创建反应应用</span><span class="sxs-lookup"><span data-stu-id="643a9-123">Create React App</span></span>  
    
    <!-- If you run into issues while using Workspaces with your framework of choice, or you get it working after some custom configuration, please [start a thread in the mailing list][AlphabetGroupsAlphabetBrowserDevTools] or [ask a question on Stack Overflow][StackOverflowAlphabetBrowserDevTools] to share your knowledge with the rest of the DevTools community.  -->  
    
## <span data-ttu-id="643a9-124">相关功能：本地覆盖</span><span class="sxs-lookup"><span data-stu-id="643a9-124">Related feature: Local overrides</span></span>  

<span data-ttu-id="643a9-125">**本地重写** 是另一个类似于工作区的 DevTools 功能。</span><span class="sxs-lookup"><span data-stu-id="643a9-125">**Local Overrides** is another DevTools feature that is similar to Workspaces.</span></span>  <span data-ttu-id="643a9-126">如果想要试验对页面所做的更改，并且需要在页面加载期间查看更改，但又不介意将更改映射到页面的源代码，请使用本地替代。</span><span class="sxs-lookup"><span data-stu-id="643a9-126">Use Local Overrides when you want to experiment with changes to a page, and you need to see the changes across page loads, but you do not care about mapping your changes to the source code of the page.</span></span>  

<!--Todo: add section when content is ready  -->  

## <span data-ttu-id="643a9-127">步骤1：设置</span><span class="sxs-lookup"><span data-stu-id="643a9-127">Step 1: Set up</span></span>  

<span data-ttu-id="643a9-128">完成以下操作，获取工作区的实际体验。</span><span class="sxs-lookup"><span data-stu-id="643a9-128">Complete the following actions, to get hands-on experience with Workspaces.</span></span>  

### <span data-ttu-id="643a9-129">设置演示</span><span class="sxs-lookup"><span data-stu-id="643a9-129">Set up the demo</span></span>  

1.  <span data-ttu-id="643a9-130">[打开演示][GlitchWorkspacesDemo]。</span><span class="sxs-lookup"><span data-stu-id="643a9-130">[Open the demo][GlitchWorkspacesDemo].</span></span>  <!--In the top-left of the editor, a randomly-generated project name is displayed.  -->  
    
    :::image type="complex" source="../media/workspaces-glitch-workspaces-demo-source.msft.png" alt-text="故障项目" lightbox="../media/workspaces-glitch-workspaces-demo-source.msft.png":::
       <span data-ttu-id="643a9-132">故障项目</span><span class="sxs-lookup"><span data-stu-id="643a9-132">A Glitch project</span></span>  
    :::image-end:::  
    
    <!--1.  Choose the project name.  -->  
    <!--1.  Select **Advanced Options** > **Download Project**.  
    
    :::image type="complex" source="../media/workspaces-glitch-advanced-options-download-project.msft.png" alt-text="The Download Project button" lightbox="../media/workspaces-glitch-advanced-options-download-project.msft.png":::
       The Download Project button  
    :::image-end:::  

    -->  
    <!--1.  Close the tab.  -->  
    <!--1.  Unzip the source code and move the unzipped `app` directory to your desktop.  For the rest of this tutorial the unzipped  directory is referred to as `~/Desktop/app`.  -->  
    
1.  <span data-ttu-id="643a9-133">`app`在桌面上创建目录。</span><span class="sxs-lookup"><span data-stu-id="643a9-133">Create an `app` directory on your desktop.</span></span>  <span data-ttu-id="643a9-134">将目录中的文件副本保存 `workspaces-demo` 到 `app` 目录。</span><span class="sxs-lookup"><span data-stu-id="643a9-134">Save copies of the files from the `workspaces-demo` directory to the `app` directory.</span></span>  <span data-ttu-id="643a9-135">对于教程的其余部分，目录称为 `~/Desktop/app` 。</span><span class="sxs-lookup"><span data-stu-id="643a9-135">For the rest of the tutorial ,the directory is referred to as `~/Desktop/app`.</span></span>  
1.  <span data-ttu-id="643a9-136">在中启动本地 web 服务器 `~/Desktop/app` 。</span><span class="sxs-lookup"><span data-stu-id="643a9-136">Start a local web server in `~/Desktop/app`.</span></span>  <span data-ttu-id="643a9-137">下面是用于启动的一些示例代码 `SimpleHTTPServer` ，但你可能会使用所需的任何服务器。</span><span class="sxs-lookup"><span data-stu-id="643a9-137">Below is some sample code for starting up `SimpleHTTPServer`, but you may use whatever server you prefer.</span></span>  
    
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
    
1.  <span data-ttu-id="643a9-138">在 Microsoft Edge 中打开一个选项卡，然后转到本地托管的网站版本。</span><span class="sxs-lookup"><span data-stu-id="643a9-138">Open a tab in Microsoft Edge and go to locally-hosted version of the site.</span></span>  <span data-ttu-id="643a9-139">你应该能够使用诸如或之类的 URL 访问它 `localhost:8080` `http://0.0.0.0:8080` 。</span><span class="sxs-lookup"><span data-stu-id="643a9-139">You should be able to access it using a URL like `localhost:8080` or `http://0.0.0.0:8080`.</span></span>  <span data-ttu-id="643a9-140">确切的 [端口号][WikiPortURLs] 可能不同。</span><span class="sxs-lookup"><span data-stu-id="643a9-140">The exact [port number][WikiPortURLs] may be different.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo.msft.png" alt-text="演示" lightbox="../media/workspaces-workspaces-demo.msft.png":::
       <span data-ttu-id="643a9-142">演示</span><span class="sxs-lookup"><span data-stu-id="643a9-142">The demo</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="643a9-143">设置 DevTools</span><span class="sxs-lookup"><span data-stu-id="643a9-143">Set up DevTools</span></span>  

1.  <span data-ttu-id="643a9-144">选择 `Control` + `Shift` + `J` \ (Windows \ ) 或 `Command` + `Option` + `J` \ (macOS \ ) 打开 DevTools 的**控制台**面板。</span><span class="sxs-lookup"><span data-stu-id="643a9-144">Select `Control`+`Shift`+`J` \(Windows\) or `Command`+`Option`+`J` \(macOS\) to open the **Console** panel of DevTools.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-console.msft.png" alt-text="控制台面板" lightbox="../media/workspaces-workspaces-demo-console.msft.png":::
       <span data-ttu-id="643a9-146">**控制台**面板</span><span class="sxs-lookup"><span data-stu-id="643a9-146">The **Console** panel</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="643a9-147">选择 " **源** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="643a9-147">Choose the **Sources** tab.</span></span>  
1.  <span data-ttu-id="643a9-148">选择 " **文件系统** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="643a9-148">Choose the **Filesystem** tab.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-sources-filesystem.msft.png" alt-text=""文件系统" 选项卡" lightbox="../media/workspaces-workspaces-demo-sources-filesystem.msft.png":::
       <span data-ttu-id="643a9-150">" **文件系统** " 选项卡</span><span class="sxs-lookup"><span data-stu-id="643a9-150">The **Filesystem** tab</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="643a9-151">选择 " **将文件夹添加到工作区**"。</span><span class="sxs-lookup"><span data-stu-id="643a9-151">Choose **Add Folder To Workspace**.</span></span>  
1.  <span data-ttu-id="643a9-152">Enter `~/Desktop/app` 。</span><span class="sxs-lookup"><span data-stu-id="643a9-152">Enter `~/Desktop/app`.</span></span>  
1.  <span data-ttu-id="643a9-153">选择 " **允许** " 以授予 DevTools 读取和写入目录的权限。</span><span class="sxs-lookup"><span data-stu-id="643a9-153">Choose **Allow** to give DevTools permission to read and write to the directory.</span></span>  
    <span data-ttu-id="643a9-154">在 " **文件系统** " 选项卡中，"，" 旁边有一个绿点 `index.html` `script.js` `styles.css` 。</span><span class="sxs-lookup"><span data-stu-id="643a9-154">In the **Filesystem** tab, there is now a green dot next to `index.html`, `script.js`, and `styles.css`.</span></span>  <span data-ttu-id="643a9-155">这些绿色圆点意味着 DevTools 已建立了页面的网络资源与中的文件之间的映射 `~/Desktop/app` 。</span><span class="sxs-lookup"><span data-stu-id="643a9-155">These green dots mean that DevTools has established a mapping between the network resources of the page, and the files in `~/Desktop/app`.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-sources-filesystem-folder.msft.png" alt-text=""文件系统" 选项卡现在显示本地文件和网络文件之间的映射" lightbox="../media/workspaces-workspaces-demo-sources-filesystem-folder.msft.png":::
       <span data-ttu-id="643a9-157">" **文件系统** " 选项卡现在显示本地文件和网络文件之间的映射</span><span class="sxs-lookup"><span data-stu-id="643a9-157">The **Filesystem** tab now shows a mapping between the local files and the network ones</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="643a9-158">步骤2：将 CSS 更改保存到磁盘</span><span class="sxs-lookup"><span data-stu-id="643a9-158">Step 2: Save a CSS change to disk</span></span>  

1.  <span data-ttu-id="643a9-159">打开 `styles.css`。</span><span class="sxs-lookup"><span data-stu-id="643a9-159">Open `styles.css`.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="643a9-160">`color`元素的属性 `h1` 设置为 `fuchsia` 。</span><span class="sxs-lookup"><span data-stu-id="643a9-160">The `color` property of `h1` elements is set to `fuchsia`.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-sources-filesystem-css.msft.png" alt-text="在文本编辑器中查看样式" lightbox="../media/workspaces-workspaces-demo-sources-filesystem-css.msft.png":::
       <span data-ttu-id="643a9-162">`styles.css`在文本编辑器中查看</span><span class="sxs-lookup"><span data-stu-id="643a9-162">View `styles.css` in a text editor</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="643a9-163">选择 " **元素** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="643a9-163">Choose the **Elements** tab.</span></span>  
1.  <span data-ttu-id="643a9-164">将元素的属性值更改 `color` `<h1>` 为你的常用颜色。</span><span class="sxs-lookup"><span data-stu-id="643a9-164">Change the value of the `color` property of the `<h1>` element to your favorite color.</span></span>  
    <span data-ttu-id="643a9-165">请记住，你需要在 `<h1>` **DOM 树** 中选择元素，才能在 " **样式** " 窗格中查看应用到它的 CSS 规则。</span><span class="sxs-lookup"><span data-stu-id="643a9-165">Remember that you need to choose the `<h1>` element in the **DOM Tree** in order to see the CSS rules applied to it in the **Styles** pane.</span></span>  <span data-ttu-id="643a9-166">旁边的绿色圆点 `styles.css:1` 表示你所做的任何更改都将映射到 `~/Desktop/app/styles.css` 。</span><span class="sxs-lookup"><span data-stu-id="643a9-166">The green dot next to `styles.css:1` means that any change that you make are mapped to `~/Desktop/app/styles.css`.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-elements-styles-css.msft.png" alt-text="文件链接的绿色指示器" lightbox="../media/workspaces-workspaces-demo-elements-styles-css.msft.png":::
       <span data-ttu-id="643a9-168">文件链接的绿色指示器</span><span class="sxs-lookup"><span data-stu-id="643a9-168">The green indicator that the file is linked</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="643a9-169">`styles.css`再次在文本编辑器中打开。</span><span class="sxs-lookup"><span data-stu-id="643a9-169">Open `styles.css` in a text editor again.</span></span>  <span data-ttu-id="643a9-170">该 `color` 属性现在设置为你的常用颜色。</span><span class="sxs-lookup"><span data-stu-id="643a9-170">The `color` property is now set to your favorite color.</span></span>  
1.  <span data-ttu-id="643a9-171">刷新页面。</span><span class="sxs-lookup"><span data-stu-id="643a9-171">Refresh the page.</span></span>  <span data-ttu-id="643a9-172">元素的颜色 `<h1>` 仍设置为你的常用颜色。</span><span class="sxs-lookup"><span data-stu-id="643a9-172">The color of the `<h1>` element is still set to your favorite color.</span></span>  <span data-ttu-id="643a9-173">在刷新时进行更改，因为当你进行更改时 DevTools 将更改保存到磁盘。</span><span class="sxs-lookup"><span data-stu-id="643a9-173">The change across a refresh, because when you made the change DevTools saved the change to disk.</span></span>  <span data-ttu-id="643a9-174">然后，当你刷新页面时，你的本地服务器从磁盘向修改后的文件副本提供服务。</span><span class="sxs-lookup"><span data-stu-id="643a9-174">And then, when you refreshed the page, your local server served the modified copy of the file from disk.</span></span>  
    
## <span data-ttu-id="643a9-175">步骤3：将 HTML 更改保存到磁盘</span><span class="sxs-lookup"><span data-stu-id="643a9-175">Step 3: Save an HTML change to disk</span></span>  

### <span data-ttu-id="643a9-176">更改 "元素" 面板中的 HTML</span><span class="sxs-lookup"><span data-stu-id="643a9-176">Change HTML from the Elements Panel</span></span>  

<span data-ttu-id="643a9-177">你可以更改 "元素" 面板中的 html，但对 DOM 树所做的更改不会保存到磁盘，并且只会影响当前浏览器会话。</span><span class="sxs-lookup"><span data-stu-id="643a9-177">You may make changes to the html from the Element Panel, but your changes to the DOM tree are not saved to disk and only effect the current browser session.</span></span>  

<span data-ttu-id="643a9-178">DOM 树不是 html。</span><span class="sxs-lookup"><span data-stu-id="643a9-178">The DOM tree is not html.</span></span>  

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

### <span data-ttu-id="643a9-179">从 "源" 面板更改 HTML</span><span class="sxs-lookup"><span data-stu-id="643a9-179">Change HTML from the Sources panel</span></span>  

<span data-ttu-id="643a9-180">如果要保存对页面的 html 所做的更改，请使用 " **源** " 面板执行此操作。</span><span class="sxs-lookup"><span data-stu-id="643a9-180">If you want to save a change to the html of the page, do it using the **Sources** panel.</span></span>  

1.  <span data-ttu-id="643a9-181">选择 " **源** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="643a9-181">Choose the **Sources** tab.</span></span>  
1.  <span data-ttu-id="643a9-182">选择 " **页面** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="643a9-182">Choose the **Page** tab.</span></span>  
1.  <span data-ttu-id="643a9-183">选择 " \*\* (索引") \*\*。</span><span class="sxs-lookup"><span data-stu-id="643a9-183">Choose **(index)**.</span></span>  <span data-ttu-id="643a9-184">将打开页面的 HTML。</span><span class="sxs-lookup"><span data-stu-id="643a9-184">The HTML for the page opens.</span></span>  
1.  <span data-ttu-id="643a9-185">用 `<h1>I ❤️  Cake</h1>` 取代 `<h1>Workspaces Demo</h1>`。</span><span class="sxs-lookup"><span data-stu-id="643a9-185">Replace `<h1>Workspaces Demo</h1>` with `<h1>I ❤️  Cake</h1>`.</span></span>  <span data-ttu-id="643a9-186">请参阅下图。</span><span class="sxs-lookup"><span data-stu-id="643a9-186">See the following figure.</span></span>  
1.  <span data-ttu-id="643a9-187">选择 `Control` + `S` \ (Windows \ ) 或 `Command` + `S` \ (macOS \ ) 保存更改。</span><span class="sxs-lookup"><span data-stu-id="643a9-187">Select `Control`+`S` \(Windows\) or `Command`+`S` \(macOS\) to save the change.</span></span>  
1.  <span data-ttu-id="643a9-188">刷新页面。</span><span class="sxs-lookup"><span data-stu-id="643a9-188">Refresh the page.</span></span>  <span data-ttu-id="643a9-189">该 `<h1>` 元素仍显示新文本。</span><span class="sxs-lookup"><span data-stu-id="643a9-189">The `<h1>` element is still displaying the new text.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-sources-page-h1.msft.png" alt-text="从 "源" 面板更改 HTML" lightbox="../media/workspaces-workspaces-demo-sources-page-h1.msft.png":::
       <span data-ttu-id="643a9-191">第12行设置为</span><span class="sxs-lookup"><span data-stu-id="643a9-191">Line 12 is set to</span></span> `I ❤️  Cake`  
    :::image-end:::  
    
1.  <span data-ttu-id="643a9-192">打开 `~/Desktop/app/index.html`。</span><span class="sxs-lookup"><span data-stu-id="643a9-192">Open `~/Desktop/app/index.html`.</span></span>  <span data-ttu-id="643a9-193">`<h1>`元素包含新文本。</span><span class="sxs-lookup"><span data-stu-id="643a9-193">The `<h1>` element contains the new text.</span></span>  
    
## <span data-ttu-id="643a9-194">步骤4：将 JavaScript 更改保存到磁盘</span><span class="sxs-lookup"><span data-stu-id="643a9-194">Step 4: Save a JavaScript change to disk</span></span>  

<span data-ttu-id="643a9-195">" **源** " 面板也是对 JavaScript 进行更改的位置。</span><span class="sxs-lookup"><span data-stu-id="643a9-195">The **Sources** panel is also the place to make changes to JavaScript.</span></span>  <span data-ttu-id="643a9-196">但有时你需要在对网站进行更改时访问其他面板，如 " **元素** " 面板或 " **控制台** " 面板。</span><span class="sxs-lookup"><span data-stu-id="643a9-196">But sometimes you need to access other panels, such as the **Elements** panel or the **Console** panel, while making changes to your site.</span></span>  <span data-ttu-id="643a9-197">有一种方法可使 " **源** " 面板与其他面板一起打开。</span><span class="sxs-lookup"><span data-stu-id="643a9-197">There is a way to have the **Sources** panel open alongside other panels.</span></span>  

1.  <span data-ttu-id="643a9-198">选择 " **元素** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="643a9-198">Choose the **Elements** tab.</span></span>  
1.  <span data-ttu-id="643a9-199">选择 `Control` + `Shift` + `P` \ (Windows \ ) 或 `Command` + `Shift` + `P` \ (macOS \ ) 。</span><span class="sxs-lookup"><span data-stu-id="643a9-199">Select `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\).</span></span>  <span data-ttu-id="643a9-200">此时将打开 " **命令" 菜单** 。</span><span class="sxs-lookup"><span data-stu-id="643a9-200">The **Command Menu** opens.</span></span>  
1.  <span data-ttu-id="643a9-201">键入 `QS` ，然后选择 " **显示快速源**"。</span><span class="sxs-lookup"><span data-stu-id="643a9-201">Type `QS`, then select **Show Quick Source**.</span></span>  <span data-ttu-id="643a9-202">在 DevTools 窗口的底部，现在有一个 " **快速源** " 选项卡。 该选项卡显示的内容 `index.html` ，这是您在 " **源** " 面板中编辑的最后一个文件。</span><span class="sxs-lookup"><span data-stu-id="643a9-202">At the bottom of your DevTools window there is now a **Quick Source** tab.  The tab is displaying the contents of `index.html`, which is the last file you edited in the **Sources** panel.</span></span>  <span data-ttu-id="643a9-203">" **快速源** " 选项卡从 " **源** " 面板提供编辑器，以便您可以在打开其他面板时编辑文件。</span><span class="sxs-lookup"><span data-stu-id="643a9-203">The **Quick Source** tab gives you the editor from the **Sources** panel, so that you are able to edit files while having other panels open.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-search-show-quick-source.msft.png" alt-text="使用 "命令" 菜单打开 "快速源" 选项卡" lightbox="../media/workspaces-workspaces-demo-search-show-quick-source.msft.png":::
       <span data-ttu-id="643a9-205">使用 "**命令" 菜单**打开 "**快速源**" 选项卡</span><span class="sxs-lookup"><span data-stu-id="643a9-205">Open the **Quick Source** tab using **Command Menu**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="643a9-206">选择 `Control` + `P` \ (Windows \ ) 或 `Command` + `P` \ (macOS \ ) 打开 "**打开文件**" 对话框。</span><span class="sxs-lookup"><span data-stu-id="643a9-206">Select `Control`+`P` \(Windows\) or `Command`+`P` \(macOS\) to open the **Open File** dialog.</span></span>  <span data-ttu-id="643a9-207">请参阅下图。</span><span class="sxs-lookup"><span data-stu-id="643a9-207">See the following figure.</span></span>  
1.  <span data-ttu-id="643a9-208">键入 `script` ，然后选择 " **应用/script.js**"。</span><span class="sxs-lookup"><span data-stu-id="643a9-208">Type `script`, then select **app/script.js**.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-search-script.msft.png" alt-text="使用 "打开文件" 对话框打开 script.js" lightbox="../media/workspaces-workspaces-demo-search-script.msft.png":::
       <span data-ttu-id="643a9-210">`script.js`使用 "**打开文件**" 对话框打开</span><span class="sxs-lookup"><span data-stu-id="643a9-210">Open `script.js` using the **Open File** dialog</span></span>  
    :::image-end:::  
    
    > [!NOTE]
    > <span data-ttu-id="643a9-211">`Save Changes To Disk With Workspaces`演示中的链接会定期设置样式。</span><span class="sxs-lookup"><span data-stu-id="643a9-211">The `Save Changes To Disk With Workspaces` link in the demo is styled regularly.</span></span>  
    
1.  <span data-ttu-id="643a9-212">使用 "**快速源**" 选项卡将以下代码添加到**script.js**底部。</span><span class="sxs-lookup"><span data-stu-id="643a9-212">Add the following code to the bottom of **script.js** using the **Quick Source** tab.</span></span>  
    
    ```javascript
    console.log('greetings from script.js');
    document.querySelector('a').style = 'font-style:italic';
    ```  
    
1.  <span data-ttu-id="643a9-213">选择 `Control` + `S` \ (Windows \ ) 或 `Command` + `S` \ (macOS \ ) 保存更改。</span><span class="sxs-lookup"><span data-stu-id="643a9-213">Select `Control`+`S` \(Windows\) or `Command`+`S` \(macOS\) to save the change.</span></span>  
1.  <span data-ttu-id="643a9-214">刷新页面。</span><span class="sxs-lookup"><span data-stu-id="643a9-214">Refresh the page.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="643a9-215">页面上的链接现在为斜体。</span><span class="sxs-lookup"><span data-stu-id="643a9-215">The link on the page is now italicized.</span></span>  
    
    :::image type="complex" source="../media/workspaces-workspaces-demo-elements-styles-quick-source-script.msft.png" alt-text="页面上的链接现在为斜体" lightbox="../media/workspaces-workspaces-demo-elements-styles-quick-source-script.msft.png":::
       <span data-ttu-id="643a9-217">页面上的链接现在为斜体</span><span class="sxs-lookup"><span data-stu-id="643a9-217">The link on the page is now italicized</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="643a9-218">后续步骤</span><span class="sxs-lookup"><span data-stu-id="643a9-218">Next steps</span></span>  

<span data-ttu-id="643a9-219">使用在本教程中了解到的功能在您自己的项目中设置工作区。</span><span class="sxs-lookup"><span data-stu-id="643a9-219">Use what you have learned in this tutorial to set up Workspaces in your own project.</span></span>  <!-- If you run into any issues or are able to get it working after some custom configuration, please [start a thread in the mailing list][AlphabetGroupsAlphabetBrowserDevTools] or [ask a question on Stack Overflow][StackOverflowAlphabetBrowserDevTools] to share your knowledge with the rest of the DevTools community.  -->  

<!--  
If you have more feedback on the topics or anything else, please use any of the channels below:  

*   [Mailing List][AlphabetGroupsAlphabetBrowserDevTools]  
*   [Twitter][TwitterAlphabetBrowserDevTools]  
    -->  

<!-- links -->  

[DevToolsCssIndex]: ../css/index.md "开始使用查看和更改 CSS |Microsoft 文档"  

<!--[LocalOverrides]: ../whats-new/2018/01/devtools#overrides -->  

<!--[AlphabetGroupsAlphabetBrowserDevTools]: https://groups.alphabet.com/forum/#!forum/alphabet-browser-developer-tools "Alphabet Browser DevTools - Alphabet Groups"  -->  

[GlitchWorkspacesDemo]: https://glitch.com/edit/#!/microsoft-edge-chromium-devtools?path=workspaces-demo/index.html:1:0 "工作区演示文件 |故障"  

[MDNCSSContent]: https://developer.mozilla.org/docs/Web/CSS/content "内容-CSS：级联样式表 |MDN"  
[MDNWebGettingStarted]: https://developer.mozilla.org/docs/Learn/Getting_started_with_the_web "Web 入门 |MDN"  
[MDNSimpleLocalHTTPServer]: https://developer.mozilla.org/docs/Learn/Common_questions/set_up_a_local_testing_server#Running_a_simple_local_HTTP_server "运行一个简单的本地 HTTP 服务器 |MDN"  
[MDNWebAPIsDOM]: https://developer.mozilla.org/docs/Web/API/Document_Object_Model/Introduction "DOM-Web Api 简介 |MDN"  

<!--[StackOverflowAlphabetBrowserDevTools]: https://stackoverflow.com/questions/ask?tags=alphabet-browser-devtools "Alphabet Browser DevTools - Stack Overflow"  -->

[TreehouseBlogSourceMaps]: https://blog.teamtreehouse.com/introduction-source-maps "源地图简介 |Treehouse 博客"  

<!-- [TwitterAlphabetBrowserDevTools]: https://twitter.com/alphabetbrowserdevtools "Alphabet Browser DevTools \(@AlphabetBrowserDevTools\) | Twitter"  -->

[WikiPortURLs]: https://en.wikipedia.org/wiki/Port_(computer_networking)#Use_in_URLs "端口 \ (计算机网络 \ ) -维基百科"  

> [!NOTE]
> <span data-ttu-id="643a9-228">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="643a9-228">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="643a9-229">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/workspaces/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="643a9-229">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/workspaces/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="643a9-231">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="643a9-231">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
