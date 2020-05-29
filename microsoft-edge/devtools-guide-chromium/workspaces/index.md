---
title: 编辑具有工作区的文件
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/27/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 612e85b8b00a78a40e53ac5c33d187fdae174024
ms.sourcegitcommit: 5cdc1626d5581b79c0f2ac4ea62e7f1974ebfa57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2020
ms.locfileid: "10601848"
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







# <span data-ttu-id="e1a34-103">编辑具有工作区的文件</span><span class="sxs-lookup"><span data-stu-id="e1a34-103">Edit Files With Workspaces</span></span>   



> [!NOTE]
> <span data-ttu-id="e1a34-104">本教程的目标是提供有关设置和使用工作区的动手练习，以便你可以在自己的项目中使用工作区。</span><span class="sxs-lookup"><span data-stu-id="e1a34-104">The goal of this tutorial is to provide hands-on practice in setting up and using Workspaces, so that you are able to use Workspaces in your own projects.</span></span>  <span data-ttu-id="e1a34-105">你可以在启用工作区后将对源代码所做的更改保存在你的本地计算机上 DevTools 中。</span><span class="sxs-lookup"><span data-stu-id="e1a34-105">You are able to save the changes to the source code, on your local computer, that you made within DevTools after you enable Workspaces.</span></span>  

> [!CAUTION]
> <span data-ttu-id="e1a34-106">**先决条件**：在开始本教程之前，你应该知道如何：</span><span class="sxs-lookup"><span data-stu-id="e1a34-106">**Prerequisites**: Before beginning this tutorial, you should know how to:</span></span>  
> *   [<span data-ttu-id="e1a34-107">使用 HTML、CSS 和 JavaScript 构建网页</span><span class="sxs-lookup"><span data-stu-id="e1a34-107">Use HTML, CSS, and JavaScript to build a web page</span></span>][MDNWebGettingStarted]  
> *   [<span data-ttu-id="e1a34-108">使用 DevTools 对 CSS 进行基本更改</span><span class="sxs-lookup"><span data-stu-id="e1a34-108">Use DevTools to make basic changes to CSS</span></span>][DevToolsCssIndex]  
> *   [<span data-ttu-id="e1a34-109">运行本地 HTTP web 服务器</span><span class="sxs-lookup"><span data-stu-id="e1a34-109">Run a local HTTP web server</span></span>][MDNSimpleLocalHTTPServer]  

## <span data-ttu-id="e1a34-110">概述</span><span class="sxs-lookup"><span data-stu-id="e1a34-110">Overview</span></span>   

<span data-ttu-id="e1a34-111">工作区使你能够将在 Devtools 中所做的更改保存到计算机上同一文件的本地副本。</span><span class="sxs-lookup"><span data-stu-id="e1a34-111">Workspaces enable you to save a change that you make in Devtools to a local copy of the same file on your computer.</span></span>  <span data-ttu-id="e1a34-112">例如，假设：</span><span class="sxs-lookup"><span data-stu-id="e1a34-112">For example, suppose:</span></span>  

*   <span data-ttu-id="e1a34-113">您的桌面网站上有您的网站的源代码。</span><span class="sxs-lookup"><span data-stu-id="e1a34-113">You have the source code for your site on your desktop.</span></span>  
*   <span data-ttu-id="e1a34-114">您从源代码目录运行本地 web 服务器，以便可以在该网站上访问 `localhost:8080` 。</span><span class="sxs-lookup"><span data-stu-id="e1a34-114">You are running a local web server from the source code directory, so that the site is accessible at `localhost:8080`.</span></span>  
*   <span data-ttu-id="e1a34-115">您 `localhost:8080` 在 Microsoft Edge 中打开，并且您使用 DevTools 更改网站的 CSS。</span><span class="sxs-lookup"><span data-stu-id="e1a34-115">You opened `localhost:8080`  in Microsoft Edge, and you are using DevTools to change the CSS of the site.</span></span>  

<span data-ttu-id="e1a34-116">启用了工作区后，在 DevTools 内所做的 CSS 更改将保存到桌面上的源代码中。</span><span class="sxs-lookup"><span data-stu-id="e1a34-116">With Workspaces enabled, the CSS changes that you make within DevTools are saved to the source code on your desktop.</span></span>  

## <span data-ttu-id="e1a34-117">限制</span><span class="sxs-lookup"><span data-stu-id="e1a34-117">Limitations</span></span>   

<span data-ttu-id="e1a34-118">如果你使用的是新式框架，则可能会将你的源代码从易于维护的格式转换为尽可能快地运行的格式。</span><span class="sxs-lookup"><span data-stu-id="e1a34-118">If you are using a modern framework, it probably transforms your source code from a format that is easy to maintain into a format that is optimized to run as quickly as possible.</span></span>  
<span data-ttu-id="e1a34-119">工作区通常能够将经过优化的代码映射回原始源代码以及[源映射][TreehouseBlogSourceMaps]的帮助。</span><span class="sxs-lookup"><span data-stu-id="e1a34-119">Workspaces is usually able to map the optimized code back to your original source code with the help of [source maps][TreehouseBlogSourceMaps].</span></span>  <span data-ttu-id="e1a34-120">但是，在如何使用源映射的框架之间存在许多变化。</span><span class="sxs-lookup"><span data-stu-id="e1a34-120">But there is a lot of variation between frameworks over how they use source maps.</span></span>  <span data-ttu-id="e1a34-121">Devtools 只支持所有变体。</span><span class="sxs-lookup"><span data-stu-id="e1a34-121">Devtools simply does support all the variations.</span></span>  

<span data-ttu-id="e1a34-122">已知工作区不能与这些框架配合使用：</span><span class="sxs-lookup"><span data-stu-id="e1a34-122">Workspaces is known to not work with these frameworks:</span></span>  

*   <span data-ttu-id="e1a34-123">创建反应应用</span><span class="sxs-lookup"><span data-stu-id="e1a34-123">Create React App</span></span>  

<!-- If you run into issues while using Workspaces with your framework of choice, or you get it working after some custom configuration, please [start a thread in the mailing list][AlphabetGroupsAlphabetBrowserDevTools] or [ask a question on Stack Overflow][StackOverflowAlphabetBrowserDevTools] to share your knowledge with the rest of the DevTools community.  -->  

## <span data-ttu-id="e1a34-124">相关功能：本地覆盖</span><span class="sxs-lookup"><span data-stu-id="e1a34-124">Related feature: Local Overrides</span></span>   

<span data-ttu-id="e1a34-125">**本地重写**是另一个类似于工作区的 DevTools 功能。</span><span class="sxs-lookup"><span data-stu-id="e1a34-125">**Local Overrides** is another DevTools feature that is similar to Workspaces.</span></span>  <span data-ttu-id="e1a34-126">如果想要试验对页面所做的更改，并且需要在页面加载期间查看这些更改，但又不介意将更改映射到页面的源代码，请使用本地替代。</span><span class="sxs-lookup"><span data-stu-id="e1a34-126">Use Local Overrides when you want to experiment with changes to a page, and you need to see those changes across page loads, but you do not care about mapping your changes to the source code of the page.</span></span>  

<!--Todo: add section when content is ready  -->  

## <span data-ttu-id="e1a34-127">步骤1：设置</span><span class="sxs-lookup"><span data-stu-id="e1a34-127">Step 1: Setup</span></span>   

<span data-ttu-id="e1a34-128">完成本教程，获取有关工作区的实际体验。</span><span class="sxs-lookup"><span data-stu-id="e1a34-128">Complete this tutorial to get hands-on experience with Workspaces.</span></span>  

### <span data-ttu-id="e1a34-129">设置演示</span><span class="sxs-lookup"><span data-stu-id="e1a34-129">Set up the demo</span></span>   

1.  <span data-ttu-id="e1a34-130">[打开演示][GlitchWorkspacesDemo]。</span><span class="sxs-lookup"><span data-stu-id="e1a34-130">[Open the demo][GlitchWorkspacesDemo].</span></span>  <!--In the top-left of the editor, a randomly-generated project name is displayed.  -->  
    
    > ##### <span data-ttu-id="e1a34-131">图 1</span><span class="sxs-lookup"><span data-stu-id="e1a34-131">Figure 1</span></span>  
    > <span data-ttu-id="e1a34-132">![故障项目][ImageGlitchProject]</span><span class="sxs-lookup"><span data-stu-id="e1a34-132">A Glitch project ![A Glitch project][ImageGlitchProject]</span></span>  
    
    <!--1.  Click the project name.  -->
    <!--1.  Select **Advanced Options** > **Download Project**.  
    
    > ##### Figure 2  
    > The Download Project button  
    > ![The Download Project button][ImageDownloadProjectButton]  
    -->
    <!--1.  Close the tab.  -->
    <!--1.  Unzip the source code and move the unzipped `app` directory to your desktop.  For the rest of this tutorial this directory is referred to as `~/Desktop/app`.  -->  
    
1.  <span data-ttu-id="e1a34-133">`app`在桌面上创建目录。</span><span class="sxs-lookup"><span data-stu-id="e1a34-133">Create an `app` directory on your desktop.</span></span>  <span data-ttu-id="e1a34-134">在目录中保存文件的副本 `workspaces-demo` 。</span><span class="sxs-lookup"><span data-stu-id="e1a34-134">Save copies of the files in the `workspaces-demo` directory.</span></span>  <span data-ttu-id="e1a34-135">对于本教程的其余部分，此目录称为 `~/Desktop/app` 。</span><span class="sxs-lookup"><span data-stu-id="e1a34-135">For the rest of this tutorial this directory is referred to as `~/Desktop/app`.</span></span>  
1.  <span data-ttu-id="e1a34-136">在中启动本地 web 服务器 `~/Desktop/app` 。</span><span class="sxs-lookup"><span data-stu-id="e1a34-136">Start a local web server in `~/Desktop/app`.</span></span>  <span data-ttu-id="e1a34-137">下面是用于启动的一些示例代码 `SimpleHTTPServer` ，但你可能会使用所需的任何服务器。</span><span class="sxs-lookup"><span data-stu-id="e1a34-137">Below is some sample code for starting up `SimpleHTTPServer`, but you may use whatever server you prefer.</span></span>  
    
    ```bash
    cd ~/Desktop/app
    python -m SimpleHTTPServer # Python 2
    ```  
    
    ```bash
    cd ~/Desktop/app
    python -m http.server # Python 3
    ```  
    
1.  <span data-ttu-id="e1a34-138">在 Microsoft Edge 中打开一个选项卡，然后转到本地托管的网站版本。</span><span class="sxs-lookup"><span data-stu-id="e1a34-138">Open a tab in Microsoft Edge and go to locally-hosted version of the site.</span></span>  <span data-ttu-id="e1a34-139">你应该能够使用诸如或之类的 URL 访问它 `localhost:8080` `http://0.0.0.0:8080` 。</span><span class="sxs-lookup"><span data-stu-id="e1a34-139">You should be able to access it using a URL like `localhost:8080` or `http://0.0.0.0:8080`.</span></span>  <span data-ttu-id="e1a34-140">确切的[端口号][WikiPortURLs]可能不同。</span><span class="sxs-lookup"><span data-stu-id="e1a34-140">The exact [port number][WikiPortURLs] may be different.</span></span>  
    
    > ##### <span data-ttu-id="e1a34-141">图 2</span><span class="sxs-lookup"><span data-stu-id="e1a34-141">Figure 2</span></span>  
    > <span data-ttu-id="e1a34-142">演示</span><span class="sxs-lookup"><span data-stu-id="e1a34-142">The demo</span></span>  
    > <span data-ttu-id="e1a34-143">![演示][ImageDemo]</span><span class="sxs-lookup"><span data-stu-id="e1a34-143">![The demo][ImageDemo]</span></span>  

### <span data-ttu-id="e1a34-144">设置 DevTools</span><span class="sxs-lookup"><span data-stu-id="e1a34-144">Set up DevTools</span></span>   

1.  <span data-ttu-id="e1a34-145">按 `Control` + `Shift` + `J` \ （Windows \）或 `Command` + `Option` + `J` \ （macOS \）打开 DevTools 的**控制台**面板。</span><span class="sxs-lookup"><span data-stu-id="e1a34-145">Press `Control`+`Shift`+`J` \(Windows\) or `Command`+`Option`+`J` \(macOS\) to open the **Console** panel of DevTools.</span></span>  
    
    > ##### <span data-ttu-id="e1a34-146">图 3</span><span class="sxs-lookup"><span data-stu-id="e1a34-146">Figure 3</span></span>  
    > <span data-ttu-id="e1a34-147">**控制台**面板</span><span class="sxs-lookup"><span data-stu-id="e1a34-147">The **Console** panel</span></span>  
    > <span data-ttu-id="e1a34-148">![控制台面板][ImageConsolePanel]</span><span class="sxs-lookup"><span data-stu-id="e1a34-148">![The Console panel][ImageConsolePanel]</span></span>  

1.  <span data-ttu-id="e1a34-149">单击 "**源**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="e1a34-149">Click the **Sources** tab.</span></span>  
1.  <span data-ttu-id="e1a34-150">单击 "**文件系统**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="e1a34-150">Click the **Filesystem** tab.</span></span>  
    
    > ##### <span data-ttu-id="e1a34-151">图 4</span><span class="sxs-lookup"><span data-stu-id="e1a34-151">Figure 4</span></span>  
    > <span data-ttu-id="e1a34-152">"**文件系统**" 选项卡</span><span class="sxs-lookup"><span data-stu-id="e1a34-152">The **Filesystem** tab</span></span>  
    > <span data-ttu-id="e1a34-153">![文件系统选项卡][ImageFilesystem]</span><span class="sxs-lookup"><span data-stu-id="e1a34-153">![The Filesystem tab][ImageFilesystem]</span></span>  

1.  <span data-ttu-id="e1a34-154">单击 "**将文件夹添加到工作区**"。</span><span class="sxs-lookup"><span data-stu-id="e1a34-154">Click **Add Folder To Workspace**.</span></span>  
1.  <span data-ttu-id="e1a34-155">选择 `~/Desktop/app` 。</span><span class="sxs-lookup"><span data-stu-id="e1a34-155">Select `~/Desktop/app`.</span></span>  
1.  <span data-ttu-id="e1a34-156">单击 "**允许**" 以授予 DevTools 读取和写入目录的权限。</span><span class="sxs-lookup"><span data-stu-id="e1a34-156">Click **Allow** to give DevTools permission to read and write to the directory.</span></span>  
    <span data-ttu-id="e1a34-157">在 "**文件系统**" 选项卡中，"，" 旁边有一个绿点 `index.html` `script.js` `styles.css` 。</span><span class="sxs-lookup"><span data-stu-id="e1a34-157">In the **Filesystem** tab, there is now a green dot next to `index.html`, `script.js`, and `styles.css`.</span></span>  <span data-ttu-id="e1a34-158">这些绿色圆点意味着 DevTools 已建立了页面的网络资源与中的文件之间的映射 `~/Desktop/app` 。</span><span class="sxs-lookup"><span data-stu-id="e1a34-158">These green dots mean that DevTools has established a mapping between the network resources of the page, and the files in `~/Desktop/app`.</span></span>  
    
    > ##### <span data-ttu-id="e1a34-159">图 5</span><span class="sxs-lookup"><span data-stu-id="e1a34-159">Figure 5</span></span>  
    > <span data-ttu-id="e1a34-160">"**文件系统**" 选项卡现在显示本地文件和网络文件之间的映射</span><span class="sxs-lookup"><span data-stu-id="e1a34-160">The **Filesystem** tab now shows a mapping between the local files and the network ones</span></span>  
    > <span data-ttu-id="e1a34-161">![文件系统选项卡现在显示本地文件和网络文件之间的映射][ImageMapping]</span><span class="sxs-lookup"><span data-stu-id="e1a34-161">![The Filesystem tab now shows a mapping between the local files and the network ones][ImageMapping]</span></span>  

## <span data-ttu-id="e1a34-162">步骤2：将 CSS 更改保存到磁盘</span><span class="sxs-lookup"><span data-stu-id="e1a34-162">Step 2: Save a CSS change to disk</span></span>   

1.  <span data-ttu-id="e1a34-163">打开 `styles.css`。</span><span class="sxs-lookup"><span data-stu-id="e1a34-163">Open `styles.css`.</span></span>  
    
    > [!NOTE]
    ><span data-ttu-id="e1a34-164">`color`元素的属性 `h1` 设置为 `fuchsia` 。</span><span class="sxs-lookup"><span data-stu-id="e1a34-164">The `color` property of `h1` elements is set to `fuchsia`.</span></span>
    
    > ##### <span data-ttu-id="e1a34-165">图 6</span><span class="sxs-lookup"><span data-stu-id="e1a34-165">Figure 6</span></span>  
    > <span data-ttu-id="e1a34-166">`styles.css`在文本编辑器中查看</span><span class="sxs-lookup"><span data-stu-id="e1a34-166">Viewing `styles.css` in a text editor</span></span>  
    > <span data-ttu-id="e1a34-167">![在文本编辑器中查看样式 .css][ImageStylesFuchsia]</span><span class="sxs-lookup"><span data-stu-id="e1a34-167">![Viewing styles.css in a text editor][ImageStylesFuchsia]</span></span>  


1.  <span data-ttu-id="e1a34-168">单击 "**元素**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="e1a34-168">Click the **Elements** tab.</span></span>  
1.  <span data-ttu-id="e1a34-169">将元素的属性值更改 `color` `<h1>` 为你的常用颜色。</span><span class="sxs-lookup"><span data-stu-id="e1a34-169">Change the value of the `color` property of the `<h1>` element to your favorite color.</span></span>  
    <span data-ttu-id="e1a34-170">请记住，你需要单击 `<h1>` **DOM 树**中的元素，才能在 "**样式**" 窗格中查看应用到它的 CSS 规则。</span><span class="sxs-lookup"><span data-stu-id="e1a34-170">Remember that you need to click the `<h1>` element in the **DOM Tree** in order to see the CSS rules applied to it in the **Styles** pane.</span></span>  <span data-ttu-id="e1a34-171">旁边的绿色圆点 `styles.css:1` 表示你所做的任何更改都将映射到 `~/Desktop/app/styles.css` 。</span><span class="sxs-lookup"><span data-stu-id="e1a34-171">The green dot next to `styles.css:1` means that any change that you make are mapped to `~/Desktop/app/styles.css`.</span></span>  
    
    > ##### <span data-ttu-id="e1a34-172">图 7</span><span class="sxs-lookup"><span data-stu-id="e1a34-172">Figure 7</span></span>  
    > <span data-ttu-id="e1a34-173">文件链接的绿色指示器</span><span class="sxs-lookup"><span data-stu-id="e1a34-173">The green indicator that the file is linked</span></span>  
    > <span data-ttu-id="e1a34-174">![文件链接的绿色指示器][ImageStylesGreen]</span><span class="sxs-lookup"><span data-stu-id="e1a34-174">![The green indicator that the file is linked][ImageStylesGreen]</span></span>  

1.  <span data-ttu-id="e1a34-175">`styles.css`再次在文本编辑器中打开。</span><span class="sxs-lookup"><span data-stu-id="e1a34-175">Open `styles.css` in a text editor again.</span></span>  <span data-ttu-id="e1a34-176">该 `color` 属性现在设置为你的常用颜色。</span><span class="sxs-lookup"><span data-stu-id="e1a34-176">The `color` property is now set to your favorite color.</span></span>  
1.  <span data-ttu-id="e1a34-177">重新加载页面。</span><span class="sxs-lookup"><span data-stu-id="e1a34-177">Reload the page.</span></span>  <span data-ttu-id="e1a34-178">元素的颜色 `<h1>` 仍设置为你的常用颜色。</span><span class="sxs-lookup"><span data-stu-id="e1a34-178">The color of the `<h1>` element is still set to your favorite color.</span></span>  <span data-ttu-id="e1a34-179">这是因为当你进行更改时，DevTools 将更改保存到了磁盘。</span><span class="sxs-lookup"><span data-stu-id="e1a34-179">This works because when you made the change, DevTools saved the change to disk.</span></span>  <span data-ttu-id="e1a34-180">然后，当你重新加载页面时，你的本地服务器从磁盘向修改的文件副本提供服务。</span><span class="sxs-lookup"><span data-stu-id="e1a34-180">And then, when you reloaded the page, your local server served the modified copy of the file from disk.</span></span>  

## <span data-ttu-id="e1a34-181">步骤3：将 HTML 更改保存到磁盘</span><span class="sxs-lookup"><span data-stu-id="e1a34-181">Step 3: Save an HTML change to disk</span></span>   

### <span data-ttu-id="e1a34-182">更改 "元素" 面板中的 HTML</span><span class="sxs-lookup"><span data-stu-id="e1a34-182">Change HTML from the Elements Panel</span></span>  

<span data-ttu-id="e1a34-183">你可以更改 "元素" 面板中的 HTML，但对 DOM 树所做的更改不会保存到磁盘，并且只会影响当前浏览器会话。</span><span class="sxs-lookup"><span data-stu-id="e1a34-183">You may make changes to the HTML from the Element Panel, but your changes to the DOM tree are not saved to disk and only effect the current browser session.</span></span>  
<span data-ttu-id="e1a34-184">DOM 树不是 HTML。</span><span class="sxs-lookup"><span data-stu-id="e1a34-184">The DOM tree is not HTML.</span></span>  

<!--### Try changing HTML from the Elements panel   

> [!WARNING]
> The workflow that you are about to try does not work.  You are trying it now so that you do not waste time later trying to figure out why it is not working.  

1.  Click the **Elements** tab.  
1.  Double click the text content of the `h1` element, which says `Workspaces Demo`, and replace it with `I ❤️  Cake`.  
    
    > ##### Old Figure 9  
    > Attempting to change HTML from the **DOM Tree** of the **Elements** panel  
    > ![Attempting to change HTML from the DOM Tree of the Elements panel][ImageElementsCake]  

1.  Open `~/Desktop/app/index.html` in a text editor.  The change that you just made does not appear.  
1.  Reload the page.  The page reverts to its original title.  

#### Optional: Why it is not working   

> [!NOTE]
> This section describes why the workflow from [Try changing HTML from the Elements panel](#try-changing-html-from-the-elements-panel) does not work.  You should skip this section if you do not care why.  

*   The tree of nodes that you see on the **Elements** panel represents the [DOM][MDNWebAPIsDOM] of the page.  
*   To display a page, a browser fetches HTML over the network, parses the HTML, and then converts it into a tree of DOM nodes.  
*   If the page has any JavaScript, that JavaScript may add, delete, or change DOM nodes.  CSS may change the DOM, too, using the [`content`][MDNCSSContent] property.  
*   The browser eventually uses the DOM to determine what content it should present to browser users.  
*   Therefore, the final state of the page that users see may be very different from the HTML that the browser fetched.  
*   This makes it difficult for DevTools to resolve where a change made in the **Elements** panel should be saved, because the DOM is affected by HTML, JavaScript, and CSS.  

In short, the **DOM Tree** `!==` HTML.  
-->
### <span data-ttu-id="e1a34-185">从 "源" 面板更改 HTML</span><span class="sxs-lookup"><span data-stu-id="e1a34-185">Change HTML from the Sources panel</span></span>   

<span data-ttu-id="e1a34-186">如果要保存对页面的 HTML 所做的更改，请使用 "**源**" 面板执行此操作。</span><span class="sxs-lookup"><span data-stu-id="e1a34-186">If you want to save a change to the HTML of the page, do it using the **Sources** panel.</span></span>  

1.  <span data-ttu-id="e1a34-187">单击 "**源**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="e1a34-187">Click the **Sources** tab.</span></span>  
1.  <span data-ttu-id="e1a34-188">单击 "**页面**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="e1a34-188">Click the **Page** tab.</span></span>  
1.  <span data-ttu-id="e1a34-189">单击 " **（索引）**"。</span><span class="sxs-lookup"><span data-stu-id="e1a34-189">Click **(index)**.</span></span>  <span data-ttu-id="e1a34-190">将打开页面的 HTML。</span><span class="sxs-lookup"><span data-stu-id="e1a34-190">The HTML for the page opens.</span></span>  
1.  <span data-ttu-id="e1a34-191">用 `<h1>I ❤️  Cake</h1>` 取代 `<h1>Workspaces Demo</h1>`。</span><span class="sxs-lookup"><span data-stu-id="e1a34-191">Replace `<h1>Workspaces Demo</h1>` with `<h1>I ❤️  Cake</h1>`.</span></span>  <span data-ttu-id="e1a34-192">请参阅[图 8](#figure-8)。</span><span class="sxs-lookup"><span data-stu-id="e1a34-192">See [Figure 8](#figure-8).</span></span>  
1.  <span data-ttu-id="e1a34-193">按 `Control` + `S` \ （Windows \）或 `Command` + `S` \ （macOS \）保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="e1a34-193">Press `Control`+`S` \(Windows\) or `Command`+`S` \(macOS\) to save the change.</span></span>  
1.  <span data-ttu-id="e1a34-194">重新加载页面。</span><span class="sxs-lookup"><span data-stu-id="e1a34-194">Reload the page.</span></span>  <span data-ttu-id="e1a34-195">该 `<h1>` 元素仍显示新文本。</span><span class="sxs-lookup"><span data-stu-id="e1a34-195">The `<h1>` element is still displaying the new text.</span></span>  
    
    > ##### <span data-ttu-id="e1a34-196">图 8</span><span class="sxs-lookup"><span data-stu-id="e1a34-196">Figure 8</span></span>  
    > <span data-ttu-id="e1a34-197">第12行已设置为</span><span class="sxs-lookup"><span data-stu-id="e1a34-197">Line 12 has been set to</span></span> `I ❤️  Cake`  
    > <span data-ttu-id="e1a34-198">![从 "源" 面板更改 HTML][ImageSourcesCakeHTML]</span><span class="sxs-lookup"><span data-stu-id="e1a34-198">![Changing HTML from the Sources panel][ImageSourcesCakeHTML]</span></span>  

1.  <span data-ttu-id="e1a34-199">打开 `~/Desktop/app/index.html`。</span><span class="sxs-lookup"><span data-stu-id="e1a34-199">Open `~/Desktop/app/index.html`.</span></span>  <span data-ttu-id="e1a34-200">`<h1>`元素包含新文本。</span><span class="sxs-lookup"><span data-stu-id="e1a34-200">The `<h1>` element contains the new text.</span></span>  

## <span data-ttu-id="e1a34-201">步骤4：将 JavaScript 更改保存到磁盘</span><span class="sxs-lookup"><span data-stu-id="e1a34-201">Step 4: Save a JavaScript change to disk</span></span>   

<span data-ttu-id="e1a34-202">"**源**" 面板也是对 JavaScript 进行更改的位置。</span><span class="sxs-lookup"><span data-stu-id="e1a34-202">The **Sources** panel is also the place to make changes to JavaScript.</span></span>  <span data-ttu-id="e1a34-203">但有时你需要在对网站进行更改时访问其他面板，如 "**元素**" 面板或 "**控制台**" 面板。</span><span class="sxs-lookup"><span data-stu-id="e1a34-203">But sometimes you need to access other panels, such as the **Elements** panel or the **Console** panel, while making changes to your site.</span></span>  <span data-ttu-id="e1a34-204">有一种方法可使 "**源**" 面板与其他面板一起打开。</span><span class="sxs-lookup"><span data-stu-id="e1a34-204">There is a way to have the **Sources** panel open alongside other panels.</span></span>  

1.  <span data-ttu-id="e1a34-205">单击 "**元素**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="e1a34-205">Click the **Elements** tab.</span></span>  
1.  <span data-ttu-id="e1a34-206">按 `Control` + `Shift` + `P` \ （Windows \）或 `Command` + `Shift` + `P` \ （macOS \）。</span><span class="sxs-lookup"><span data-stu-id="e1a34-206">Press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\).</span></span>  <span data-ttu-id="e1a34-207">此时将打开 "**命令" 菜单**。</span><span class="sxs-lookup"><span data-stu-id="e1a34-207">The **Command Menu** opens.</span></span>  
1.  <span data-ttu-id="e1a34-208">键入 `QS` ，然后选择 "**显示快速源**"。</span><span class="sxs-lookup"><span data-stu-id="e1a34-208">Type `QS`, then select **Show Quick Source**.</span></span>  <span data-ttu-id="e1a34-209">在 DevTools 窗口的底部，现在有一个 "**快速源**" 选项卡。 该选项卡显示的内容 `index.html` ，这是您在 "**源**" 面板中编辑的最后一个文件。</span><span class="sxs-lookup"><span data-stu-id="e1a34-209">At the bottom of your DevTools window there is now a **Quick Source** tab.  The tab is displaying the contents of `index.html`, which is the last file you edited in the **Sources** panel.</span></span>  <span data-ttu-id="e1a34-210">"**快速源**" 选项卡从 "**源**" 面板提供编辑器，以便您可以在打开其他面板时编辑文件。</span><span class="sxs-lookup"><span data-stu-id="e1a34-210">The **Quick Source** tab gives you the editor from the **Sources** panel, so that you are able to edit files while having other panels open.</span></span>  
    
    > ##### <span data-ttu-id="e1a34-211">图 9</span><span class="sxs-lookup"><span data-stu-id="e1a34-211">Figure 9</span></span>  
    > <span data-ttu-id="e1a34-212">使用 "**命令" 菜单**打开 "**快速源**" 选项卡</span><span class="sxs-lookup"><span data-stu-id="e1a34-212">Opening the **Quick Source** tab using the **Command Menu**</span></span>  
    > <span data-ttu-id="e1a34-213">![使用命令菜单打开 "快速源" 选项卡][ImageCommandMenuQuickSource]</span><span class="sxs-lookup"><span data-stu-id="e1a34-213">![Opening the Quick Source tab using Command Menu][ImageCommandMenuQuickSource]</span></span>  

1.  <span data-ttu-id="e1a34-214">按 `Control` + `P` \ （Windows \）或 `Command` + `P` \ （macOS \）打开 "**打开文件**" 对话框。</span><span class="sxs-lookup"><span data-stu-id="e1a34-214">Press `Control`+`P` \(Windows\) or `Command`+`P` \(macOS\) to open the **Open File** dialog.</span></span>  <span data-ttu-id="e1a34-215">请参阅[图 10](#figure-10)。</span><span class="sxs-lookup"><span data-stu-id="e1a34-215">See [Figure 10](#figure-10).</span></span>  
1.  <span data-ttu-id="e1a34-216">键入 `script` ，然后选择 "**应用/脚本 .js**"。</span><span class="sxs-lookup"><span data-stu-id="e1a34-216">Type `script`, then select **app/script.js**.</span></span>  
    
    > ##### <span data-ttu-id="e1a34-217">图 10</span><span class="sxs-lookup"><span data-stu-id="e1a34-217">Figure 10</span></span>  
    > <span data-ttu-id="e1a34-218">`script.js`使用 "**打开文件**" 对话框打开</span><span class="sxs-lookup"><span data-stu-id="e1a34-218">Opening `script.js` using the **Open File** dialog</span></span>  
    > <span data-ttu-id="e1a34-219">![打开 script 使用 "打开文件" 对话框][ImageOpenFileDialog]</span><span class="sxs-lookup"><span data-stu-id="e1a34-219">![Opening script.js using the Open File dialog][ImageOpenFileDialog]</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="e1a34-220">`Save Changes To Disk With Workspaces`演示中的链接会定期设置样式。</span><span class="sxs-lookup"><span data-stu-id="e1a34-220">The `Save Changes To Disk With Workspaces` link in the demo is styled regularly.</span></span>  
    
1.  <span data-ttu-id="e1a34-221">使用 "**快速源**" 选项卡将以下代码添加到**script**的底部。</span><span class="sxs-lookup"><span data-stu-id="e1a34-221">Add the following code to the bottom of **script.js** using the **Quick Source** tab.</span></span>  
    
    ```javascript
    console.log('greetings from script.js');
    document.querySelector('a').style = 'font-style:italic';
    ```  
    
1.  <span data-ttu-id="e1a34-222">按 `Control` + `S` \ （Windows \）或 `Command` + `S` \ （macOS \）保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="e1a34-222">Press `Control`+`S` \(Windows\) or `Command`+`S` \(macOS\) to save the change.</span></span>  
1.  <span data-ttu-id="e1a34-223">重新加载页面。</span><span class="sxs-lookup"><span data-stu-id="e1a34-223">Reload the page.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="e1a34-224">页面上的链接现在为斜体。</span><span class="sxs-lookup"><span data-stu-id="e1a34-224">The link on the page is now italic.</span></span>
    
    > ##### <span data-ttu-id="e1a34-225">图 11</span><span class="sxs-lookup"><span data-stu-id="e1a34-225">Figure 11</span></span>  
    > <span data-ttu-id="e1a34-226">页面上的链接现在为斜体</span><span class="sxs-lookup"><span data-stu-id="e1a34-226">The link on the page is now italic</span></span>  
    > <span data-ttu-id="e1a34-227">![页面上的链接现在为斜体][ImageScriptItalic]</span><span class="sxs-lookup"><span data-stu-id="e1a34-227">![The link on the page is now italic][ImageScriptItalic]</span></span>  

## <span data-ttu-id="e1a34-228">后续步骤</span><span class="sxs-lookup"><span data-stu-id="e1a34-228">Next steps</span></span>   

<span data-ttu-id="e1a34-229">使用在本教程中了解到的功能在您自己的项目中设置工作区。</span><span class="sxs-lookup"><span data-stu-id="e1a34-229">Use what you have learned in this tutorial to set up Workspaces in your own project.</span></span>  <!-- If you run into any issues or are able to get it working after some custom configuration, please [start a thread in the mailing list][AlphabetGroupsAlphabetBrowserDevTools] or [ask a question on Stack Overflow][StackOverflowAlphabetBrowserDevTools] to share your knowledge with the rest of the DevTools community.  -->

 <!--  -->



<!-- 
If you have more feedback on these topics or anything else, please use any of the channels below:
*   [Mailing List][AlphabetGroupsAlphabetBrowserDevTools]  
*   [Twitter][TwitterAlphabetBrowserDevTools]  
-->

<!-- image links -->  

[ImageGlitchProject]: /microsoft-edge/devtools-guide-chromium/media/workspaces-glitch-workspaces-demo-source.msft.png "图1：具有随机生成的名称的故障项目"  
<!--[ImageDownloadProjectButton]: /microsoft-edge/devtools-guide-chromium/media/workspaces-glitch-advanced-options-download-project.msft.png "old Figure 2: The Download Project button"  -->  
<span data-ttu-id="e1a34-231">[ImageDemo]：/microsoft-edge/devtools-guide-chromium/media/workspaces-workspaces-demo.msft.png "图2：" 演示 "</span><span class="sxs-lookup"><span data-stu-id="e1a34-231">[ImageDemo]: /microsoft-edge/devtools-guide-chromium/media/workspaces-workspaces-demo.msft.png "Figure 2: The demo"</span></span>  
<span data-ttu-id="e1a34-232">[ImageConsolePanel]：/microsoft-edge/devtools-guide-chromium/media/workspaces-workspaces-demo-console.msft.png "图3：控制台面板"</span><span class="sxs-lookup"><span data-stu-id="e1a34-232">[ImageConsolePanel]: /microsoft-edge/devtools-guide-chromium/media/workspaces-workspaces-demo-console.msft.png "Figure 3: The Console panel"</span></span>  
<span data-ttu-id="e1a34-233">[ImageFilesystem]：/microsoft-edge/devtools-guide-chromium/media/workspaces-workspaces-demo-sources-filesystem.msft.png "图4： Filesystem 选项卡"</span><span class="sxs-lookup"><span data-stu-id="e1a34-233">[ImageFilesystem]: /microsoft-edge/devtools-guide-chromium/media/workspaces-workspaces-demo-sources-filesystem.msft.png "Figure 4: The Filesystem tab"</span></span>  
<span data-ttu-id="e1a34-234">[ImageMapping]：/microsoft-edge/devtools-guide-chromium/media/workspaces-workspaces-demo-sources-filesystem-folder.msft.png "图5： Filesystem 选项卡现在显示本地文件和网络文件之间的映射"</span><span class="sxs-lookup"><span data-stu-id="e1a34-234">[ImageMapping]: /microsoft-edge/devtools-guide-chromium/media/workspaces-workspaces-demo-sources-filesystem-folder.msft.png "Figure 5: The Filesystem tab now shows a mapping between the local files and the network ones"</span></span>  
<span data-ttu-id="e1a34-235">[ImageStylesFuchsia]：/microsoft-edge/devtools-guide-chromium/media/workspaces-workspaces-demo-sources-filesystem-css.msft.png "图6：在文本编辑器中查看样式 .css"</span><span class="sxs-lookup"><span data-stu-id="e1a34-235">[ImageStylesFuchsia]: /microsoft-edge/devtools-guide-chromium/media/workspaces-workspaces-demo-sources-filesystem-css.msft.png "Figure 6: Viewing styles.css in a text editor"</span></span>  
<span data-ttu-id="e1a34-236">[ImageStylesGreen]：/microsoft-edge/devtools-guide-chromium/media/workspaces-workspaces-demo-elements-styles-css.msft.png "图7：文件链接的绿色指示器"</span><span class="sxs-lookup"><span data-stu-id="e1a34-236">[ImageStylesGreen]: /microsoft-edge/devtools-guide-chromium/media/workspaces-workspaces-demo-elements-styles-css.msft.png "Figure 7: The green indicator that the file is linked"</span></span>  
<span data-ttu-id="e1a34-237">[ImageSourcesCakeHTML]：/microsoft-edge/devtools-guide-chromium/media/workspaces-workspaces-demo-sources-page-h1.msft.png "图8：从" 源 "面板更改 HTML"</span><span class="sxs-lookup"><span data-stu-id="e1a34-237">[ImageSourcesCakeHTML]: /microsoft-edge/devtools-guide-chromium/media/workspaces-workspaces-demo-sources-page-h1.msft.png "Figure 8: Changing HTML from the Sources panel"</span></span>  
<!--[ImageElementsCake]: /microsoft-edge/devtools-guide-chromium/media/workspaces-workspaces-demo-change-h1.msft.png "Old Figure 9: Attempting to change HTML from the DOM Tree of the Elements panel"  -->  
<span data-ttu-id="e1a34-238">[ImageCommandMenuQuickSource]：/microsoft-edge/devtools-guide-chromium/media/workspaces-workspaces-demo-search-show-quick-source.msft.png "图9：使用命令菜单打开" 快速源 "选项卡</span><span class="sxs-lookup"><span data-stu-id="e1a34-238">[ImageCommandMenuQuickSource]: /microsoft-edge/devtools-guide-chromium/media/workspaces-workspaces-demo-search-show-quick-source.msft.png "Figure 9: Opening the Quick Source tab using Command Menu"</span></span>  
<span data-ttu-id="e1a34-239">[ImageOpenFileDialog]：/microsoft-edge/devtools-guide-chromium/media/workspaces-workspaces-demo-search-script.msft.png "图10：使用" 打开文件 "对话框打开 script</span><span class="sxs-lookup"><span data-stu-id="e1a34-239">[ImageOpenFileDialog]: /microsoft-edge/devtools-guide-chromium/media/workspaces-workspaces-demo-search-script.msft.png "Figure 10: Opening script.js using the Open File dialog"</span></span>  
<span data-ttu-id="e1a34-240">[ImageScriptItalic]：/microsoft-edge/devtools-guide-chromium/media/workspaces-workspaces-demo-elements-styles-quick-source-script.msft.png "图11：页面上的链接现在为斜体"</span><span class="sxs-lookup"><span data-stu-id="e1a34-240">[ImageScriptItalic]: /microsoft-edge/devtools-guide-chromium/media/workspaces-workspaces-demo-elements-styles-quick-source-script.msft.png "Figure 11: The link on the page is now italic"</span></span>  

<!-- links -->  

[DevToolsCssIndex]: /microsoft-edge/devtools-guide-chromium/css/index "查看和更改 CSS 入门"  

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

[WikiPortURLs]: https://en.wikipedia.org/wiki/Port_(computer_networking)#Use_in_URLs "端口 \ （计算机网络 \）-维基百科"  

> [!NOTE]
> <span data-ttu-id="e1a34-249">此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="e1a34-249">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="e1a34-250">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/workspaces/index)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools \ & Lighthouse \）创作。</span><span class="sxs-lookup"><span data-stu-id="e1a34-250">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/workspaces/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
<span data-ttu-id="e1a34-252">此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="e1a34-252">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
