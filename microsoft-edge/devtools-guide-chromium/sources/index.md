---
description: 使用"源"工具查看、修改和调试服务器返回的 JavaScript，并检查包含当前网页的资源。  若要将"源"工具用作开发环境，请向 Workspace 中添加源文件。
title: 源工具概述
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/11/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: d3ef49bf986d8827216bd0bc183e45806aa0a2c3
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564712"
---
# <a name="sources-tool-overview"></a><span data-ttu-id="cbe76-105">源工具概述</span><span class="sxs-lookup"><span data-stu-id="cbe76-105">Sources tool overview</span></span>  

<span data-ttu-id="cbe76-106">使用 **"** 源"工具查看、修改和调试前端 JavaScript 代码，并检查包含当前网页的资源。</span><span class="sxs-lookup"><span data-stu-id="cbe76-106">Use the **Sources** tool to view, modify, and debug front-end JavaScript code, and to inspect the resources that make up the current webpage.</span></span>  <span data-ttu-id="cbe76-107">" **源** "工具具有三个窗格：</span><span class="sxs-lookup"><span data-stu-id="cbe76-107">The **Sources** tool has three panes:</span></span>  

| <span data-ttu-id="cbe76-108">窗格</span><span class="sxs-lookup"><span data-stu-id="cbe76-108">Pane</span></span> | <span data-ttu-id="cbe76-109">操作</span><span class="sxs-lookup"><span data-stu-id="cbe76-109">Actions</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="cbe76-110">**导航器** 窗格</span><span class="sxs-lookup"><span data-stu-id="cbe76-110">**Navigator** pane</span></span> | <span data-ttu-id="cbe76-111">在从服务器返回的资源之间导航以构建当前网页。</span><span class="sxs-lookup"><span data-stu-id="cbe76-111">Navigate among the resources that are returned from the server to construct the current webpage.</span></span>  <span data-ttu-id="cbe76-112">选择文件、图像和其他资源，并查看其路径。</span><span class="sxs-lookup"><span data-stu-id="cbe76-112">Select files, images, and other resources, and view their paths.</span></span>  <span data-ttu-id="cbe76-113">（可选）设置本地 Workspace 以将更改直接保存到源文件。</span><span class="sxs-lookup"><span data-stu-id="cbe76-113">Optionally, set up a local Workspace to save changes directly to source files.</span></span>  |  
| <span data-ttu-id="cbe76-114">**编辑器** 窗格</span><span class="sxs-lookup"><span data-stu-id="cbe76-114">**Editor** pane</span></span> | <span data-ttu-id="cbe76-115">查看从服务器返回的 JavaScript、HTML、CSS 和其他文件。</span><span class="sxs-lookup"><span data-stu-id="cbe76-115">View JavaScript, HTML, CSS, and other files that are returned from the server.</span></span>  <span data-ttu-id="cbe76-116">对 JavaScript 或 CSS 进行实验性编辑。</span><span class="sxs-lookup"><span data-stu-id="cbe76-116">Make experimental edits to JavaScript or CSS.</span></span>  <span data-ttu-id="cbe76-117">在刷新页面之前，所做的更改将一直保留;如果使用 Workspaces 保存到本地文件，则页面刷新后将保留所做的更改。</span><span class="sxs-lookup"><span data-stu-id="cbe76-117">Your changes are preserved until you refresh the page, or are preserved after page refresh if you save to a local file with Workspaces.</span></span>  <span data-ttu-id="cbe76-118">使用 Workspaces 或 Overrides 时，也可以编辑 HTML 文件。</span><span class="sxs-lookup"><span data-stu-id="cbe76-118">When you use Workspaces or Overrides, you can edit HTML files as well.</span></span>  |  
| <span data-ttu-id="cbe76-119">**调试器** 窗格</span><span class="sxs-lookup"><span data-stu-id="cbe76-119">**Debugger** pane</span></span> | <span data-ttu-id="cbe76-120">使用 JavaScript 调试器设置断点、暂停运行 JavaScript，并逐步执行代码，包括你进行的任何编辑，同时观察你指定的任何 JavaScript 表达式。</span><span class="sxs-lookup"><span data-stu-id="cbe76-120">Use the JavaScript Debugger to set breakpoints, pause running JavaScript, and step through the code, including any edits you have made, while watching any JavaScript expressions you specify.</span></span>  <span data-ttu-id="cbe76-121">观察并手动更改当前代码行范围内变量的值。</span><span class="sxs-lookup"><span data-stu-id="cbe76-121">Watch and manually change the values of variables that are in-scope for the current line of code.</span></span>  |  

<span data-ttu-id="cbe76-122">下图显示了导航器窗格\*\*\*\*，其中突出显示了 DevTools 左上角的红色框，右上角突出显示了"编辑器"\*\*\*\* 窗格，底部突出显示了"**调试器**"窗格。</span><span class="sxs-lookup"><span data-stu-id="cbe76-122">The following figure shows the **Navigator** pane highlighted with a red box in the upper left corner of DevTools, the **Editor** pane highlighted in the upper right, and the **Debugger** pane highlighted on the bottom.</span></span>  <span data-ttu-id="cbe76-123">最左侧是浏览器窗口的主要部分，显示呈现的网页灰显，因为调试程序暂停在断点上：</span><span class="sxs-lookup"><span data-stu-id="cbe76-123">On the far left side is the main part of the browser window, showing the rendered webpage grayed-out because the debugger is paused on a breakpoint:</span></span>

:::image type="complex" source="../media/sources-panes-narrow-layout.msft.png" alt-text="源工具的窗格，布局较窄" lightbox="../media/sources-panes-narrow-layout.msft.png":::
   <span data-ttu-id="cbe76-125">"源"工具的窗格，布局较窄</span><span class="sxs-lookup"><span data-stu-id="cbe76-125">The panes of the Sources tool, in narrow layout</span></span>  
:::image-end:::  

<span data-ttu-id="cbe76-126">当 DevTools 宽时， **调试** 器窗格放置在右侧，并包括 **作用域** 和 **监视**：</span><span class="sxs-lookup"><span data-stu-id="cbe76-126">When DevTools is wide, the **Debugger** pane is placed on the right, and includes **Scope** and **Watch**:</span></span>  

:::image type="complex" source="../media/sources-panes-wide-layout.msft.png" alt-text="导航、查看、编辑和调试服务器返回的 JavaScript" lightbox="../media/sources-panes-wide-layout.msft.png":::
   <span data-ttu-id="cbe76-128">导航、查看、编辑和调试服务器返回的 JavaScript</span><span class="sxs-lookup"><span data-stu-id="cbe76-128">Navigate, view, edit, and debug JavaScript returned by the server</span></span>  
:::image-end:::  

<span data-ttu-id="cbe76-129">若要最大化"源"工具的大小，请取消停靠"DevTools"到单独的窗口，并可以选择将"DevTools"窗口移动到单独的监视器。</span><span class="sxs-lookup"><span data-stu-id="cbe76-129">To maximize the size of the Sources tool, undock DevTools into a separate window, and optionally move the DevTools window to a separate monitor.</span></span>  <span data-ttu-id="cbe76-130">请参阅[Change Microsoft Edge DevTools placement (Undock， Dock to bottom， Dock to left) ][DevToolsCustomizePlacement].</span><span class="sxs-lookup"><span data-stu-id="cbe76-130">See [Change Microsoft Edge DevTools placement (Undock, Dock to bottom, Dock to left)][DevToolsCustomizePlacement].</span></span>

<span data-ttu-id="cbe76-131">若要加载上面显示的调试演示网页，请参阅下面的使用 [调试器的基本](#the-basic-approach-to-using-a-debugger)方法。</span><span class="sxs-lookup"><span data-stu-id="cbe76-131">To load the debugging demo webpage that's shown above, see [The basic approach to using a debugger](#the-basic-approach-to-using-a-debugger), below.</span></span>

## <a name="using-the-navigator-pane-to-select-files"></a><span data-ttu-id="cbe76-132">使用导航器窗格选择文件</span><span class="sxs-lookup"><span data-stu-id="cbe76-132">Using the Navigator pane to select files</span></span>

<span data-ttu-id="cbe76-133">使用 **左侧\(** 导航器窗格 \) 导航从服务器返回的资源之间导航以构建当前网页。</span><span class="sxs-lookup"><span data-stu-id="cbe76-133">Use the **Navigator** pane \(on the left\) to navigate among the resources that are returned from the server to construct the current webpage.</span></span>  <span data-ttu-id="cbe76-134">选择文件、图像和其他资源，并查看其路径。</span><span class="sxs-lookup"><span data-stu-id="cbe76-134">Select files, images, and other resources, and view their paths.</span></span>  

:::image type="complex" source="../media/navigator-pane.msft.png" alt-text="导航器窗格" lightbox="../media/navigator-pane.msft.png":::
   <span data-ttu-id="cbe76-136">导航 **器** 窗格</span><span class="sxs-lookup"><span data-stu-id="cbe76-136">The **Navigator** pane</span></span>
:::image-end:::  

<span data-ttu-id="cbe76-137">若要访问导航器窗格的任何隐藏选项卡，请选择"更多选项卡 ![ ](../media/more-tabs-icon.msft.png) \(**更多选项卡**\) "。</span><span class="sxs-lookup"><span data-stu-id="cbe76-137">To access any hidden tabs of the Navigator pane, select ![More tabs](../media/more-tabs-icon.msft.png) \(**More tabs**\).</span></span>

<span data-ttu-id="cbe76-138">以下子部分涵盖导航器窗格：</span><span class="sxs-lookup"><span data-stu-id="cbe76-138">The following subsections cover the Navigator pane:</span></span>  

*   [<span data-ttu-id="cbe76-139">使用"页面"选项卡浏览构建当前网页的资源</span><span class="sxs-lookup"><span data-stu-id="cbe76-139">Using the Page tab to explore resources that construct the current webpage</span></span>](#using-the-page-tab-to-explore-resources-that-construct-the-current-webpage)  
*   [<span data-ttu-id="cbe76-140">使用"文件系统"选项卡定义本地 Workspace</span><span class="sxs-lookup"><span data-stu-id="cbe76-140">Using the Filesystem tab to define a local Workspace</span></span>](#using-the-filesystem-tab-to-define-a-local-workspace)  
*   [<span data-ttu-id="cbe76-141">使用"覆盖"选项卡覆盖包含本地文件的服务器文件</span><span class="sxs-lookup"><span data-stu-id="cbe76-141">Using the Overrides tab to override server files with local files</span></span>](#using-the-overrides-tab-to-override-server-files-with-local-files)  
*   [<span data-ttu-id="cbe76-142">将"内容脚本"选项卡用于Microsoft Edge扩展</span><span class="sxs-lookup"><span data-stu-id="cbe76-142">Using the Content scripts tab for Microsoft Edge extensions</span></span>](#using-the-content-scripts-tab-for-microsoft-edge-extensions)  
*   [<span data-ttu-id="cbe76-143">使用"代码段"选项卡在任何页面上运行 JavaScript 代码段</span><span class="sxs-lookup"><span data-stu-id="cbe76-143">Using the Snippets tab to run JavaScript code snippets on any page</span></span>](#using-the-snippets-tab-to-run-javascript-code-snippets-on-any-webpage)  
*   [<span data-ttu-id="cbe76-144">使用命令菜单打开文件</span><span class="sxs-lookup"><span data-stu-id="cbe76-144">Using the Command Menu to open files</span></span>](#using-the-command-menu-to-open-files)  
    
### <a name="using-the-page-tab-to-explore-resources-that-construct-the-current-webpage"></a><span data-ttu-id="cbe76-145">使用"页面"选项卡浏览构建当前网页的资源</span><span class="sxs-lookup"><span data-stu-id="cbe76-145">Using the Page tab to explore resources that construct the current webpage</span></span>

<span data-ttu-id="cbe76-146">使用**导航**器窗格的"\*\*\*\* 页面"选项卡浏览从服务器返回的文件系统以构建当前网页。</span><span class="sxs-lookup"><span data-stu-id="cbe76-146">Use the **Page** tab of the **Navigator** pane to explore the file system that's returned from the server to construct the current webpage.</span></span>  <span data-ttu-id="cbe76-147">选择要查看、编辑和调试的 JavaScript 文件。</span><span class="sxs-lookup"><span data-stu-id="cbe76-147">Select a JavaScript file to view, edit, and debug it.</span></span>  <span data-ttu-id="cbe76-148">" **页面** "选项卡列出了页面已加载的所有资源。</span><span class="sxs-lookup"><span data-stu-id="cbe76-148">The **Page** tab lists all of the resources that the page has loaded.</span></span>

:::image type="complex" source="../media/sources-page-tab.msft.png" alt-text="源工具的导航器窗格中的页面选项卡" lightbox="../media/sources-page-tab.msft.png":::
   <span data-ttu-id="cbe76-150">" **源** "工具的"导航 **器"** 窗格中的" **页面"** 选项卡</span><span class="sxs-lookup"><span data-stu-id="cbe76-150">The **Page** tab in the **Navigator** pane of the **Sources** tool</span></span>
:::image-end:::  

<span data-ttu-id="cbe76-151">若要在"编辑器"窗格中 **显示** 文件，请在"页面"选项卡 **中选择** 一个文件。 对于图像，将显示图像的预览。</span><span class="sxs-lookup"><span data-stu-id="cbe76-151">To display a file in the **Editor** pane, select a file in the **Page** tab.  For an image, a preview of the image is displayed.</span></span>  
<span data-ttu-id="cbe76-152">若要显示资源的 URL 或路径，请将鼠标悬停在资源上。</span><span class="sxs-lookup"><span data-stu-id="cbe76-152">To display the URL or path for a resource, hover over the resource.</span></span>  
<span data-ttu-id="cbe76-153">若要将文件加载到浏览器的新选项卡中，或显示其他操作，请右键单击文件名。</span><span class="sxs-lookup"><span data-stu-id="cbe76-153">To load a file into a new tab of the browser, or to display other actions, right-click on the file name.</span></span>  

#### <a name="icons-in-the-page-tab"></a><span data-ttu-id="cbe76-154">"页面"选项卡中的图标</span><span class="sxs-lookup"><span data-stu-id="cbe76-154">Icons in the Page tab</span></span>

<span data-ttu-id="cbe76-155">" **页面** "选项卡使用下列图标：</span><span class="sxs-lookup"><span data-stu-id="cbe76-155">The **Page** tab uses the following icons:</span></span>  

*   <span data-ttu-id="cbe76-156">窗口 **图标** 与标签一起表示主 `top` 文档框架，即 [HTML 框架][W3CHtml4Frames]。</span><span class="sxs-lookup"><span data-stu-id="cbe76-156">The **window** icon, along with the label `top`, represents the main document frame, which is an [HTML frame][W3CHtml4Frames].</span></span>  
*   <span data-ttu-id="cbe76-157">云 **图标** 表示原 [点][WhatwgHtmlSpecMulitpageOriginHtmlOrigin]。</span><span class="sxs-lookup"><span data-stu-id="cbe76-157">The **cloud** icon represents an [origin][WhatwgHtmlSpecMulitpageOriginHtmlOrigin].</span></span>  
*   <span data-ttu-id="cbe76-158">文件夹 **图标** 表示目录。</span><span class="sxs-lookup"><span data-stu-id="cbe76-158">The **folder** icon represents a directory.</span></span>  
*   <span data-ttu-id="cbe76-159">页面 **图标** 表示资源。</span><span class="sxs-lookup"><span data-stu-id="cbe76-159">The **page** icon represents a resource.</span></span>  
    
#### <a name="group-files-by-folder-or-as-a-flat-list"></a><span data-ttu-id="cbe76-160">按文件夹或文件夹对文件进行分组简单列表</span><span class="sxs-lookup"><span data-stu-id="cbe76-160">Group files by folder or as a flat list</span></span>

<span data-ttu-id="cbe76-161">" **页面** "选项卡显示按服务器和目录分组的文件或资源，或作为简单列表。</span><span class="sxs-lookup"><span data-stu-id="cbe76-161">The **Page** tab displays files or resources grouped by server and directory, or as a flat list.</span></span>

<span data-ttu-id="cbe76-162">若要更改资源的分组时间，请进行配置：</span><span class="sxs-lookup"><span data-stu-id="cbe76-162">To change how resources are grouped:</span></span>

1.  <span data-ttu-id="cbe76-163">在左侧\导航器窗格 \(上的选项卡旁边，) ... **\(** **更多**选项 \) 按钮。</span><span class="sxs-lookup"><span data-stu-id="cbe76-163">Next to the tabs on the Navigator pane \(on the left\), select the **...** \(**More options**\) button.</span></span>  <span data-ttu-id="cbe76-164">将显示菜单。</span><span class="sxs-lookup"><span data-stu-id="cbe76-164">A menu appears.</span></span>  
1.  <span data-ttu-id="cbe76-165">选择或清除" **按文件夹分组"** 选项。</span><span class="sxs-lookup"><span data-stu-id="cbe76-165">Select or clear the **Group by folder** option.</span></span>  
    
### <a name="using-the-filesystem-tab-to-define-a-local-workspace"></a><span data-ttu-id="cbe76-166">使用"文件系统"选项卡定义本地 Workspace</span><span class="sxs-lookup"><span data-stu-id="cbe76-166">Using the Filesystem tab to define a local Workspace</span></span>

<span data-ttu-id="cbe76-167">使用导航**器**窗格的"文件系统\*\*\*\*"选项卡将文件添加到工作区，以便你在 DevTools 中所做的更改保存到本地文件系统。</span><span class="sxs-lookup"><span data-stu-id="cbe76-167">Use the **Filesystem** tab of the **Navigator** pane to add files to a Workspace, so that changes you make in DevTools get saved to your local file system.</span></span>  
<span data-ttu-id="cbe76-168">Workspace 中的文件在整个 DevTools 中由文件名旁边的绿色点指示。</span><span class="sxs-lookup"><span data-stu-id="cbe76-168">A file that's in a Workspace is indicated by a green dot next to the file name, throughout DevTools.</span></span>  

:::image type="complex" source="../media/sources-filesystem-tab.msft.png" alt-text="工作区的文件系统选项卡" lightbox="../media/sources-filesystem-tab.msft.png":::
   <span data-ttu-id="cbe76-170">工作区 **的"** 文件系统"选项卡</span><span class="sxs-lookup"><span data-stu-id="cbe76-170">The **Filesystem** tab, for a Workspace</span></span>
:::image-end:::  

<span data-ttu-id="cbe76-171">默认情况下，在"源"工具中编辑文件时\*\*\*\*，刷新网页时将放弃所做的更改。</span><span class="sxs-lookup"><span data-stu-id="cbe76-171">By default, when you edit a file in the **Sources** tool, your changes are discarded when you refresh the webpage.</span></span>  <span data-ttu-id="cbe76-172">**Sources**工具使用 Web 服务器返回的前端资源的副本。</span><span class="sxs-lookup"><span data-stu-id="cbe76-172">The **Sources** tool works with a copy of the front-end resources that are returned by the web server.</span></span>  <span data-ttu-id="cbe76-173">修改服务器返回的这些前端文件时，更改不会保留，因为您未更改源文件。</span><span class="sxs-lookup"><span data-stu-id="cbe76-173">When you modify these front-end files that are returned by the server, the changes don't persist, because you didn't change the source files.</span></span>  <span data-ttu-id="cbe76-174">您还需要在实际源代码中应用您的编辑，然后重新部署到服务器。</span><span class="sxs-lookup"><span data-stu-id="cbe76-174">You need to also apply your edits in your actual source code, and then re-deploy to the server.</span></span>  
<span data-ttu-id="cbe76-175">相比之下，使用 Workspace 时，刷新网页时，对前端代码所做的更改将保留。</span><span class="sxs-lookup"><span data-stu-id="cbe76-175">In contrast, when you use a Workspace, changes that you make to your front-end code are preserved when you refresh the webpage.</span></span>  <span data-ttu-id="cbe76-176">对于 Workspace，当您编辑服务器返回的前端代码时，"源"工具还会将编辑应用于本地源代码。</span><span class="sxs-lookup"><span data-stu-id="cbe76-176">With a Workspace, when you edit the front-end code that's returned by the server, the Sources tool also applies your edits to your local source code.</span></span>  <span data-ttu-id="cbe76-177">然后，对于其他用户查看更改，只需将已更改的源文件重新部署到服务器。</span><span class="sxs-lookup"><span data-stu-id="cbe76-177">Then for other users to see your changes, you only need to redeploy your changed source files to the server.</span></span>  
<span data-ttu-id="cbe76-178">如果服务器返回的 JavaScript 代码与本地 JavaScript 源代码相同，工作区可正常工作。</span><span class="sxs-lookup"><span data-stu-id="cbe76-178">Workspaces work well when the JavaScript code that's returned by the server is the same as your local JavaScript source code.</span></span>  <span data-ttu-id="cbe76-179">当工作流涉及源代码转换（如缩小或 [TypeScript][TypescriptlangMain] 编译）时，工作区不能正常工作。</span><span class="sxs-lookup"><span data-stu-id="cbe76-179">Workspaces don't work as well when your workflow involves transformations on your source code, such as minification or [TypeScript][TypescriptlangMain] compilation.</span></span>  

<span data-ttu-id="cbe76-180">有关详细信息，请参阅教程使用 [Workspaces 编辑文件][DevtoolsGuideChromiumWorkspacesIndex]。</span><span class="sxs-lookup"><span data-stu-id="cbe76-180">For more information, see the tutorial [Edit files with Workspaces][DevtoolsGuideChromiumWorkspacesIndex].</span></span>

### <a name="using-the-overrides-tab-to-override-server-files-with-local-files"></a><span data-ttu-id="cbe76-181">使用"覆盖"选项卡覆盖包含本地文件的服务器文件</span><span class="sxs-lookup"><span data-stu-id="cbe76-181">Using the Overrides tab to override server files with local files</span></span>

<span data-ttu-id="cbe76-182">使用**导航器**窗格的"替代\*\*\*\*"选项卡可覆盖页面资源 \(例如 images\) 本地文件夹中的文件。</span><span class="sxs-lookup"><span data-stu-id="cbe76-182">Use the **Overrides** tab of the **Navigator** pane to override page assets \(such as images\) with files from a local folder.</span></span>  
<span data-ttu-id="cbe76-183">此选项卡中的项目会覆盖服务器发送到浏览器的内容，即使服务器已发送资产。</span><span class="sxs-lookup"><span data-stu-id="cbe76-183">Items in this tab override what the server sends to the browser, even after the server has sent the assets.</span></span>  

:::image type="complex" source="../media/overrides-tab.msft.png" alt-text="导航器窗格的替代选项卡" lightbox="../media/overrides-tab.msft.png":::
   <span data-ttu-id="cbe76-185">导航 **器** 窗格的" **替代"** 选项卡</span><span class="sxs-lookup"><span data-stu-id="cbe76-185">The **Overrides** tab of the **Navigator** pane</span></span>
:::image-end:::  

<span data-ttu-id="cbe76-186">替代 **功能** 类似于工作区。</span><span class="sxs-lookup"><span data-stu-id="cbe76-186">The **Overrides** feature is similar to Workspaces.</span></span>  <span data-ttu-id="cbe76-187">当您要尝试对网页所做的更改，并且需要在刷新网页后保留更改，但您不关心将更改映射到网页的源代码时，请使用 Overrides。</span><span class="sxs-lookup"><span data-stu-id="cbe76-187">Use Overrides when you want to experiment with changes to a webpage, and you need to keep the changes after you refresh the webpage, but you don't care about mapping your changes to the source code of the webpage.</span></span>  

<span data-ttu-id="cbe76-188">覆盖服务器返回的文件的文件在整个 DevTools 中由文件名旁边的紫色点指示。</span><span class="sxs-lookup"><span data-stu-id="cbe76-188">A file that overrides a file that is returned by the server is indicated by a purple dot next to the file name, throughout DevTools.</span></span>

#### <a name="see-also"></a><span data-ttu-id="cbe76-189">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cbe76-189">See also</span></span>

*   [<span data-ttu-id="cbe76-190">使用 DevTools 使用本地副本替代Microsoft Edge资源</span><span class="sxs-lookup"><span data-stu-id="cbe76-190">Override webpage resources with local copies using Microsoft Edge DevTools</span></span>][DevtoolsJavascriptOverrides]  
*   [<span data-ttu-id="cbe76-191">将预处理的代码映射到源代码</span><span class="sxs-lookup"><span data-stu-id="cbe76-191">Map preprocessed code to source code</span></span>][DevToolsJavaScriptSourceMaps]  
    
### <a name="using-the-content-scripts-tab-for-microsoft-edge-extensions"></a><span data-ttu-id="cbe76-192">将"内容脚本"选项卡用于Microsoft Edge扩展</span><span class="sxs-lookup"><span data-stu-id="cbe76-192">Using the Content scripts tab for Microsoft Edge extensions</span></span>

<span data-ttu-id="cbe76-193">使用**导航器**窗格的"内容\*\*\*\* 脚本"选项卡查看已安装的扩展Microsoft Edge加载的任何内容脚本。</span><span class="sxs-lookup"><span data-stu-id="cbe76-193">Use the **Content scripts** tab of the **Navigator** pane to view any content scripts that were loaded by a Microsoft Edge extension that you installed.</span></span>  

:::image type="complex" source="../media/content-scripts-tab.msft.png" alt-text="导航器窗格的内容脚本选项卡" lightbox="../media/content-scripts-tab.msft.png":::
   <span data-ttu-id="cbe76-195">导航 **器** 窗格的"内容 **脚本"** 选项卡</span><span class="sxs-lookup"><span data-stu-id="cbe76-195">The **Content scripts** tab of the **Navigator** pane</span></span>
:::image-end:::  

<span data-ttu-id="cbe76-196">当调试程序进入你无法识别的代码时，你可能希望将代码标记为库代码，以避免单步执行该代码。</span><span class="sxs-lookup"><span data-stu-id="cbe76-196">When the debugger steps into code that you don't recognize, you might want to mark that code as Library code, to avoid stepping into that code.</span></span>  <span data-ttu-id="cbe76-197">请参阅 [将内容脚本标记为库代码][DevToolsJavaScriptGuidesMarkContentScriptsLibraryCode]。</span><span class="sxs-lookup"><span data-stu-id="cbe76-197">See [Mark content scripts as Library code][DevToolsJavaScriptGuidesMarkContentScriptsLibraryCode].</span></span>

#### <a name="see-also"></a><span data-ttu-id="cbe76-198">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cbe76-198">See also</span></span>

*   [<span data-ttu-id="cbe76-199">内容脚本</span><span class="sxs-lookup"><span data-stu-id="cbe76-199">Content scripts</span></span>][MdnAddOnsWebextensionsContentScripts]  
*   [<span data-ttu-id="cbe76-200">创建扩展教程第 2 部分</span><span class="sxs-lookup"><span data-stu-id="cbe76-200">Create an extension tutorial Part 2</span></span>][ExtensionsChromiumGetstartPart2ContentScripts]  
    
### <a name="using-the-snippets-tab-to-run-javascript-code-snippets-on-any-webpage"></a><span data-ttu-id="cbe76-201">使用"代码段"选项卡在任何网页上运行 JavaScript 代码段</span><span class="sxs-lookup"><span data-stu-id="cbe76-201">Using the Snippets tab to run JavaScript code snippets on any webpage</span></span>

<span data-ttu-id="cbe76-202">使用**导航器**窗格的"代码\*\*\*\* 段"选项卡创建和保存 JavaScript 代码段，以便您可以在任何网页上轻松运行这些代码段。</span><span class="sxs-lookup"><span data-stu-id="cbe76-202">Use the **Snippets** tab of the **Navigator** pane to create and save JavaScript code snippets, so that you can easily run these snippets on any webpage.</span></span>

:::image type="complex" source="../media/snippet.msft.png" alt-text="将 jQuery 库插入网页的代码段" lightbox="../media/snippet.msft.png":::
   <span data-ttu-id="cbe76-204">将 jQuery 库插入网页的代码段</span><span class="sxs-lookup"><span data-stu-id="cbe76-204">A Snippet that inserts the jQuery library into a webpage</span></span>  
:::image-end:::  

<span data-ttu-id="cbe76-205">例如，假设您经常在 **控制台**中输入以下代码，以将 jQuery 库插入页面，以便可以从控制台运行 jQuery **命令**：</span><span class="sxs-lookup"><span data-stu-id="cbe76-205">For example, suppose you frequently enter the following code in the **Console**, to insert the jQuery library into a page so that you can run jQuery commands from the **Console**:</span></span>  

```javascript
let script = document.createElement('script');
script.src = 'https://code.jquery.com/jquery-3.2.1.min.js';
script.crossOrigin = 'anonymous';
script.integrity = 'sha256-hwg4gsxgFZhOsEEamdOYGBf13FyQuiTwlAQgxVSNgt4=';
document.head.appendChild(script);
```  

<span data-ttu-id="cbe76-206">相反，您可以将此代码保存在 **代码** 段中，然后随时轻松地运行它。</span><span class="sxs-lookup"><span data-stu-id="cbe76-206">Instead, you can save this code in a **Snippet** and then easily run it whenever you need to.</span></span>  <span data-ttu-id="cbe76-207">选择 `Ctrl` + `S` \(Windows/Linux\) 或 `Command` + `S` \(macOS\) 时，DevTools 会将**代码段**保存到文件系统。</span><span class="sxs-lookup"><span data-stu-id="cbe76-207">When you select `Ctrl`+`S` \(Windows/Linux\) or `Command`+`S` \(macOS\), DevTools saves the **Snippet** to your file system.</span></span>  

<span data-ttu-id="cbe76-208">有多种方法可以运行代码段：</span><span class="sxs-lookup"><span data-stu-id="cbe76-208">There are multiple ways to run a Snippet:</span></span>  

*   <span data-ttu-id="cbe76-209">在 **导航器窗格中** ，选择" **代码** 段"选项卡，然后选择代码段文件将其打开。</span><span class="sxs-lookup"><span data-stu-id="cbe76-209">In the **Navigator** pane, select the **Snippets** tab, and then select the snippets file to open it.</span></span>  <span data-ttu-id="cbe76-210">然后在编辑器窗格的底部，选择运行 **\(** ![ 运行按钮 ](../media/run-snippet-icon.msft.png) \) 。</span><span class="sxs-lookup"><span data-stu-id="cbe76-210">Then at the bottom of the Editor pane, select **Run** \(![The Run button](../media/run-snippet-icon.msft.png)\).</span></span>  
*   <span data-ttu-id="cbe76-211">当 DevTools 具有焦点时，选择 `Ctrl` + `P` \(Windows/Linux\) 或 `Command` + `P` \(macOS\) 打开命令[菜单][DevToolsCommandMenuIndex] `!` ，然后键入 。</span><span class="sxs-lookup"><span data-stu-id="cbe76-211">When DevTools has focus, select `Ctrl`+`P` \(Windows/Linux\) or `Command`+`P` \(macOS\) to open the [Command Menu][DevToolsCommandMenuIndex], and then type `!`.</span></span>  
    
<span data-ttu-id="cbe76-212">代码段 类似于小书签。</span><span class="sxs-lookup"><span data-stu-id="cbe76-212">Snippets are similar to bookmarklets.</span></span>

#### <a name="see-also"></a><span data-ttu-id="cbe76-213">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cbe76-213">See also</span></span>

*   [<span data-ttu-id="cbe76-214">使用 Microsoft Edge DevTools 在任何网页上运行 JavaScript 代码片段</span><span class="sxs-lookup"><span data-stu-id="cbe76-214">Run snippets of JavaScript on any webpage with Microsoft Edge DevTools</span></span>][DevtoolsGuideChromiumJavascriptSnippets]  
    
### <a name="using-the-command-menu-to-open-files"></a><span data-ttu-id="cbe76-215">使用命令菜单打开文件</span><span class="sxs-lookup"><span data-stu-id="cbe76-215">Using the Command Menu to open files</span></span>

<span data-ttu-id="cbe76-216">若要打开文件，除了使用"源"工具\*\*\*\* 中的"导航器"窗格\*\*\*\* 外，还可以在 DevTools 中的任何位置使用命令菜单。</span><span class="sxs-lookup"><span data-stu-id="cbe76-216">To open a file, in addition to using the **Navigator** pane within the **Sources** tool, you can use the Command Menu from anywhere within DevTools.</span></span>

*   <span data-ttu-id="cbe76-217">在 DevTools 中的任何位置，在 `Ctrl` + `P` Windows/Linux 或 `Command` + `P` macOS 上选择。</span><span class="sxs-lookup"><span data-stu-id="cbe76-217">From anywhere in DevTools, select `Ctrl`+`P` on Windows/Linux or `Command`+`P` on macOS.</span></span>  <span data-ttu-id="cbe76-218">将显示"命令菜单"，并列出"源"工具的"导航器"\*\*\*\* 窗格选项卡上**的所有**资源。</span><span class="sxs-lookup"><span data-stu-id="cbe76-218">The Command Menu appears, and lists all the resources that are in the tabs of the **Navigator** pane of the **Sources** tool.</span></span>  
*   <span data-ttu-id="cbe76-219">或者，在"源"工具中\*\*\*\*"导航器"窗格的\*\*\*\* 选项卡旁边，选择 **"...** \(**更多选项**\) "按钮，然后选择"打开**文件"。**</span><span class="sxs-lookup"><span data-stu-id="cbe76-219">Or, next to the tabs of the **Navigator** pane in the **Sources** tool, select the **...** \(**More options**\) button, and then select **Open File**.</span></span>  

<span data-ttu-id="cbe76-220">若要显示并选取所有文件.js，请键入 `.js` 。</span><span class="sxs-lookup"><span data-stu-id="cbe76-220">To display and pick from a list of all .js files, type `.js`.</span></span>

:::image type="complex" source="../media/sources-command-menu-to-open-file.msft.png" alt-text="使用命令菜单打开文件" lightbox="../media/sources-command-menu-to-open-file.msft.png":::
   <span data-ttu-id="cbe76-222">使用命令菜单打开文件</span><span class="sxs-lookup"><span data-stu-id="cbe76-222">Opening a file by using the Command Menu</span></span>
:::image-end:::

<span data-ttu-id="cbe76-223">如果键入 `?` ，则命令菜单将显示几个命令，包括 **... 打开文件**。</span><span class="sxs-lookup"><span data-stu-id="cbe76-223">If you type `?`, the Command Menu shows several commands, including **...  Open file**.</span></span>  <span data-ttu-id="cbe76-224">如果选择清除 `Backspace` "命令菜单"，将显示文件列表。</span><span class="sxs-lookup"><span data-stu-id="cbe76-224">If you select `Backspace` to clear the Command Menu, a list of files is shown.</span></span>

<span data-ttu-id="cbe76-225">有关详细信息，请参阅 Run [commands with the Microsoft Edge DevTools Command Menu][DevToolsCommandMenuIndex]。</span><span class="sxs-lookup"><span data-stu-id="cbe76-225">For more information, see [Run commands with the Microsoft Edge DevTools Command Menu][DevToolsCommandMenuIndex].</span></span>

## <a name="using-the-editor-pane-to-view-or-edit-files"></a><span data-ttu-id="cbe76-226">使用编辑器窗格查看或编辑文件</span><span class="sxs-lookup"><span data-stu-id="cbe76-226">Using the Editor pane to view or edit files</span></span>

<span data-ttu-id="cbe76-227">使用 **"** 编辑器"窗格查看从服务器返回的前端文件，以撰写当前网页，包括 JavaScript、HTML、CSS 和图像文件。</span><span class="sxs-lookup"><span data-stu-id="cbe76-227">Use the **Editor** pane to view the front-end files that are returned from the server to compose the current webpage, including JavaScript, HTML, CSS, and image files.</span></span>  <span data-ttu-id="cbe76-228">在编辑器窗格中编辑前端文件时，DevTools 将更新网页以运行修改后的代码。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="cbe76-228">When you edit the front-end files in the **Editor** pane, DevTools updates the webpage to run the modified code.</span></span>  

:::image type="complex" source="../media/editor-pane.msft.png" alt-text="源工具中的编辑器窗格" lightbox="../media/editor-pane.msft.png":::
   <span data-ttu-id="cbe76-230">" **源** "工具中的" **编辑器"** 窗格</span><span class="sxs-lookup"><span data-stu-id="cbe76-230">The **Editor** pane in the **Sources** tool</span></span>  
:::image-end:::

<span data-ttu-id="cbe76-231">" **编辑器** "窗格对各种文件类型的支持级别如下：</span><span class="sxs-lookup"><span data-stu-id="cbe76-231">The **Editor** pane has the following level of support for various file types:</span></span>  

| <span data-ttu-id="cbe76-232">文件类型</span><span class="sxs-lookup"><span data-stu-id="cbe76-232">File Type</span></span> | <span data-ttu-id="cbe76-233">支持的操作</span><span class="sxs-lookup"><span data-stu-id="cbe76-233">Supported Actions</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="cbe76-234">JavaScript</span><span class="sxs-lookup"><span data-stu-id="cbe76-234">JavaScript</span></span> | <span data-ttu-id="cbe76-235">查看、编辑和调试。</span><span class="sxs-lookup"><span data-stu-id="cbe76-235">View, edit, and debug.</span></span>  |  
| <span data-ttu-id="cbe76-236">CSS</span><span class="sxs-lookup"><span data-stu-id="cbe76-236">CSS</span></span> | <span data-ttu-id="cbe76-237">查看和编辑。</span><span class="sxs-lookup"><span data-stu-id="cbe76-237">View and edit.</span></span>  |  
| <span data-ttu-id="cbe76-238">HTML</span><span class="sxs-lookup"><span data-stu-id="cbe76-238">HTML</span></span> | <span data-ttu-id="cbe76-239">查看和编辑。</span><span class="sxs-lookup"><span data-stu-id="cbe76-239">View and edit.</span></span>  |  
| <span data-ttu-id="cbe76-240">Images</span><span class="sxs-lookup"><span data-stu-id="cbe76-240">Images</span></span> | <span data-ttu-id="cbe76-241">“查看”。</span><span class="sxs-lookup"><span data-stu-id="cbe76-241">View.</span></span>  |  

<span data-ttu-id="cbe76-242">默认情况下，刷新网页时将放弃编辑。</span><span class="sxs-lookup"><span data-stu-id="cbe76-242">By default, edits are discarded when you refresh the webpage.</span></span>  <span data-ttu-id="cbe76-243">若要了解如何将更改保存到文件系统，请参阅上面的使用"文件系统"选项卡[定义本地 Workspace。](#using-the-filesystem-tab-to-define-a-local-workspace)</span><span class="sxs-lookup"><span data-stu-id="cbe76-243">For information about how to save the changes to your file system, see [Using the Filesystem tab to define a local Workspace](#using-the-filesystem-tab-to-define-a-local-workspace), above.</span></span>

<span data-ttu-id="cbe76-244">以下子部分涵盖"编辑器"窗格：</span><span class="sxs-lookup"><span data-stu-id="cbe76-244">The following subsections cover the Editor pane:</span></span>  

*   [<span data-ttu-id="cbe76-245">编辑 JavaScript 文件</span><span class="sxs-lookup"><span data-stu-id="cbe76-245">Editing a JavaScript file</span></span>](#editing-a-javascript-file)  
*   [<span data-ttu-id="cbe76-246">使用非常打印重新格式化缩小的 JavaScript 文件</span><span class="sxs-lookup"><span data-stu-id="cbe76-246">Reformatting a minified JavaScript file with pretty-print</span></span>](#reformatting-a-minified-javascript-file-with-pretty-print)  
*   [<span data-ttu-id="cbe76-247">将缩小代码映射到源代码以显示可读代码</span><span class="sxs-lookup"><span data-stu-id="cbe76-247">Mapping minified code to your source code to show readable code</span></span>](#mapping-minified-code-to-your-source-code-to-show-readable-code)  
*   [<span data-ttu-id="cbe76-248">从源代码转换到编译的前端代码</span><span class="sxs-lookup"><span data-stu-id="cbe76-248">Transformations from source code to compiled front-end code</span></span>](#transformations-from-source-code-to-compiled-front-end-code)  
*   [<span data-ttu-id="cbe76-249">编辑 CSS 文件</span><span class="sxs-lookup"><span data-stu-id="cbe76-249">Editing a CSS file</span></span>](#editing-a-css-file)  
*   [<span data-ttu-id="cbe76-250">编辑 HTML 文件</span><span class="sxs-lookup"><span data-stu-id="cbe76-250">Editing an HTML file</span></span>](#editing-an-html-file)  
*   [<span data-ttu-id="cbe76-251">访问行号或函数</span><span class="sxs-lookup"><span data-stu-id="cbe76-251">Going to a line number or function</span></span>](#going-to-a-line-number-or-function)  
*   [<span data-ttu-id="cbe76-252">使用不同的工具时显示源文件</span><span class="sxs-lookup"><span data-stu-id="cbe76-252">Displaying source files when using a different tool</span></span>](#displaying-source-files-when-using-a-different-tool)  
    
### <a name="editing-a-javascript-file"></a><span data-ttu-id="cbe76-253">编辑 JavaScript 文件</span><span class="sxs-lookup"><span data-stu-id="cbe76-253">Editing a JavaScript file</span></span>

<span data-ttu-id="cbe76-254">若要在 DevTools 中编辑 JavaScript\*\*\*\* 文件，请使用"源"工具中的"编辑器 **"** 窗格。</span><span class="sxs-lookup"><span data-stu-id="cbe76-254">To edit a JavaScript file in DevTools, use the **Editor** pane, within the **Sources** tool.</span></span>

:::image type="complex" source="../media/editing-js-in-editor-pane.msft.png" alt-text="在编辑器窗格中编辑 JavaScript" lightbox="../media/editing-js-in-editor-pane.msft.png":::
   <span data-ttu-id="cbe76-256">在 **编辑器** 窗格中编辑 JavaScript</span><span class="sxs-lookup"><span data-stu-id="cbe76-256">Editing JavaScript in the **Editor** pane</span></span>  
:::image-end:::

<span data-ttu-id="cbe76-257">若要将文件加载到编辑器窗格中，请使用左侧\导航\*\*\*\* 器窗格中的" ("选项卡) 。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="cbe76-257">To load a file into the Editor pane, use the **Page** tab in the **Navigator** pane \(on the left\).</span></span>  <span data-ttu-id="cbe76-258">或使用命令菜单\*\*\*\*，如下所示：在 DevTools 的右上角，选择"自定义和控制**DevTools** \(`...` \) "，然后选择"打开**文件"。**</span><span class="sxs-lookup"><span data-stu-id="cbe76-258">Or use the **Command Menu**, as follows: in the upper right of DevTools, select **Customize and control DevTools** \(`...`\) and then select **Open File**.</span></span>

#### <a name="save-and-undo"></a><span data-ttu-id="cbe76-259">保存和撤消</span><span class="sxs-lookup"><span data-stu-id="cbe76-259">Save and Undo</span></span>

<span data-ttu-id="cbe76-260">若要使 JavaScript 更改生效，请选择 `Ctrl` + `S`\(Windows、Linux\) 或 `Command` + `S`\(macOS\)。</span><span class="sxs-lookup"><span data-stu-id="cbe76-260">For JavaScript changes to take effect, select `Ctrl`+`S` \(Windows, Linux\) or `Command`+`S` \(macOS\).</span></span>  

<span data-ttu-id="cbe76-261">如果更改文件，文件名旁边将出现一个星号。</span><span class="sxs-lookup"><span data-stu-id="cbe76-261">If you change a file, an asterisk appears next to the file name.</span></span>  

*   <span data-ttu-id="cbe76-262">若要保存更改，请在 `Ctrl` + `S` Windows/Linux 或 `Command` + `S` macOS 上选择。</span><span class="sxs-lookup"><span data-stu-id="cbe76-262">To save changes, select `Ctrl`+`S` on Windows/Linux or `Command`+`S` on macOS.</span></span>  
*   <span data-ttu-id="cbe76-263">若要撤消更改，请在 `Ctrl` + `Z` Windows/Linux 或 `Command` + `Z` macOS 上选择。</span><span class="sxs-lookup"><span data-stu-id="cbe76-263">To undo a change, select `Ctrl`+`Z` on Windows/Linux or `Command`+`Z` on macOS.</span></span>  
    
<span data-ttu-id="cbe76-264">默认情况下，刷新网页时将放弃您的编辑。</span><span class="sxs-lookup"><span data-stu-id="cbe76-264">By default, your edits are discarded when you refresh the webpage.</span></span>  <span data-ttu-id="cbe76-265">若要详细了解如何在本地文件系统中保存更改，请参阅使用 [Workspaces 编辑文件][DevtoolsGuideChromiumWorkspacesIndex]。</span><span class="sxs-lookup"><span data-stu-id="cbe76-265">For more information about how to save the changes in your local file system, see [Edit files with Workspaces][DevtoolsGuideChromiumWorkspacesIndex].</span></span>

#### <a name="find-and-replace"></a><span data-ttu-id="cbe76-266">查找和替换</span><span class="sxs-lookup"><span data-stu-id="cbe76-266">Find and Replace</span></span>

<span data-ttu-id="cbe76-267">若要在当前文件中查找文本，请选择"编辑器"\*\*\*\* 窗格赋予其焦点，然后在 `Ctrl` + `F` Windows/Linux 或 `Command` + `F` macOS 上选择。</span><span class="sxs-lookup"><span data-stu-id="cbe76-267">To find text in the current file, select the **Editor** pane to give it focus, and then select `Ctrl`+`F` on Windows/Linux, or `Command`+`F` on macOS.</span></span>  

:::image type="complex" source="../media/find-replace.msft.png" alt-text="在源工具的编辑器窗格中查找和替换" lightbox="../media/find-replace.msft.png":::
   <span data-ttu-id="cbe76-269">**在\*\*\*\*"源"** 工具**的"编辑器**"窗格中查找和**替换**</span><span class="sxs-lookup"><span data-stu-id="cbe76-269">**Find** and **Replace**, in the **Editor** pane of the **Sources** tool</span></span>
:::image-end:::

<span data-ttu-id="cbe76-270">若要查找和替换文本，请选择"\*\*\*\* 查找"文本框左侧的"替换 \(**A-\>B**\) "**按钮**。</span><span class="sxs-lookup"><span data-stu-id="cbe76-270">To find and replace text, select the **Replace** \(**A-\>B**\) button to the left of the **Find** textbox.</span></span>  <span data-ttu-id="cbe76-271">查看 **可** 编辑 (时，>**A-\>B**\) 按钮出现。</span><span class="sxs-lookup"><span data-stu-id="cbe76-271">The **Replace** \(**A-\>B**\) button appears when viewing an editable file.</span></span>

#### <a name="showing-the-changes-you-made"></a><span data-ttu-id="cbe76-272">显示所做的更改</span><span class="sxs-lookup"><span data-stu-id="cbe76-272">Showing the changes you made</span></span>

<span data-ttu-id="cbe76-273">To review the changes you made to a file， right-click in the **Editor** pane and then select **Local Modifications**.</span><span class="sxs-lookup"><span data-stu-id="cbe76-273">To review the changes you made to a file, right-click in the **Editor** pane and then select **Local Modifications**.</span></span>

<span data-ttu-id="cbe76-274">The **Drawer** opens at the bottom of DevTools， showing your changes within the **Changes** tab.</span><span class="sxs-lookup"><span data-stu-id="cbe76-274">The **Drawer** opens at the bottom of DevTools, showing your changes within the **Changes** tab.</span></span>

:::image type="complex" source="../media/local-modifications.msft.png" alt-text="在箱的更改选项卡中显示本地修改" lightbox="../media/local-modifications.msft.png":::
   <span data-ttu-id="cbe76-276">在 **"箱"** 的"更改 **"选项卡** 中显示本地 **修改**</span><span class="sxs-lookup"><span data-stu-id="cbe76-276">Showing **Local Modifications**, in the **Changes** tab of the **Drawer**</span></span>
:::image-end:::

#### <a name="changes-inside-a-function-take-effect"></a><span data-ttu-id="cbe76-277">函数中的更改生效</span><span class="sxs-lookup"><span data-stu-id="cbe76-277">Changes inside a function take effect</span></span>

<span data-ttu-id="cbe76-278">DevTools 不会重新运行脚本，因此唯一生效的 JavaScript 更改是你在函数内所做的更改。</span><span class="sxs-lookup"><span data-stu-id="cbe76-278">DevTools doesn't re-run a script, so the only JavaScript changes that take effect are changes that you make within functions.</span></span>  <span data-ttu-id="cbe76-279">例如，在下图中，我们向服务器返回的 JavaScript 添加了以下代码：</span><span class="sxs-lookup"><span data-stu-id="cbe76-279">For example, in the following figure, we added the following code to the JavaScript that is returned by the server:</span></span>  
*   <span data-ttu-id="cbe76-280">我们在任何函数 `console.log('A')` 之外添加了 语句。</span><span class="sxs-lookup"><span data-stu-id="cbe76-280">We added the statement `console.log('A')` outside of any function.</span></span>  
*   <span data-ttu-id="cbe76-281">我们在 函数 `console.log('B')` 中添加了 `onClick` 语句。</span><span class="sxs-lookup"><span data-stu-id="cbe76-281">We added the statement `console.log('B')` inside an `onClick` function.</span></span>  
<span data-ttu-id="cbe76-282">然后保存更改，在窗体中输入数字，然后选择窗体按钮以发送窗体。</span><span class="sxs-lookup"><span data-stu-id="cbe76-282">We then saved the changes, entered numbers into the form, and then selected the form button to send the form.</span></span>  

<span data-ttu-id="cbe76-283">提交表单（位于全局范围）后，不会运行，但在函数内，会运行 ， `console.log('A')` `console.log('B')` `onClick` 输出 `B` 到控制台：</span><span class="sxs-lookup"><span data-stu-id="cbe76-283">After submitting the form, `console.log('A')`, which is at global scope, doesn't run, but `console.log('B')`, inside an `onClick` function, does run, outputting `B` to the Console:</span></span>

:::image type="complex" source="../media/edit-js.msft.png" alt-text="全局范围 JavaScript 未重新运行" lightbox="../media/edit-js.msft.png":::
   <span data-ttu-id="cbe76-285">全局范围 JavaScript 未重新运行</span><span class="sxs-lookup"><span data-stu-id="cbe76-285">Global-scope JavaScript is not re-run</span></span>  
:::image-end:::

### <a name="reformatting-a-minified-javascript-file-with-pretty-print"></a><span data-ttu-id="cbe76-286">使用非常打印重新格式化缩小的 JavaScript 文件</span><span class="sxs-lookup"><span data-stu-id="cbe76-286">Reformatting a minified JavaScript file with pretty-print</span></span>

<span data-ttu-id="cbe76-287">若要使用"花式打印"重新设置文件的格式，使其可读，请在"编辑器\*\*\*\*"窗格底部选择"真字打印"按钮 ![ \(Format ](../media/format-icon.msft.png) \) （显示为大括号）。</span><span class="sxs-lookup"><span data-stu-id="cbe76-287">To use pretty-print to reformat a file to make it readable, select the **Pretty print** button \(![Format](../media/format-icon.msft.png)\), which is shown as braces, at the bottom of the Editor pane.</span></span>  <span data-ttu-id="cbe76-288">或者，如果 **"编辑器"** 窗格顶部显示"非常打印"按钮，您可以选择该按钮。</span><span class="sxs-lookup"><span data-stu-id="cbe76-288">Or, if a **Pretty-print** button appears at the top of the Editor pane, you can select that button.</span></span>

:::image type="complex" source="../media/minified.msft.png" alt-text="彩色打印按钮" lightbox="../media/minified.msft.png":::
   <span data-ttu-id="cbe76-290">" **彩色打印"** 按钮</span><span class="sxs-lookup"><span data-stu-id="cbe76-290">The **Pretty print** button</span></span>  
:::image-end:::  

<span data-ttu-id="cbe76-291">重新格式化的文件显示在新选项卡中， `:formatted` 并附加到文件名后面。</span><span class="sxs-lookup"><span data-stu-id="cbe76-291">The reformatted file appears in a new tab, with `:formatted` appended to the file name.</span></span>  <span data-ttu-id="cbe76-292">重新格式化的代码是只读的。</span><span class="sxs-lookup"><span data-stu-id="cbe76-292">The reformatted code is read-only.</span></span>  

:::image type="complex" source="../media/pretty-printed.msft.png" alt-text="用 JavaScript 文件重新格式化 (的) 非常打印的字体" lightbox="../media/pretty-printed.msft.png":::
   <span data-ttu-id="cbe76-294">一个非常打印的 \(格式化\) JavaScript 文件</span><span class="sxs-lookup"><span data-stu-id="cbe76-294">A pretty-printed \(reformatted\) JavaScript file</span></span>  
:::image-end:::  

<span data-ttu-id="cbe76-295">若要使重新格式化的文件滚动到在缩小文件中选择的代码：</span><span class="sxs-lookup"><span data-stu-id="cbe76-295">To make the reformatted file scroll to the code that you select in the minified file:</span></span>  

1.  <span data-ttu-id="cbe76-296">如果已重新格式化的文件选项卡已打开，请关闭它。</span><span class="sxs-lookup"><span data-stu-id="cbe76-296">If the reformatted file tab is open, close it.</span></span>  
1.  <span data-ttu-id="cbe76-297">在"编辑器"窗格中的缩小文件中选择一些代码。</span><span class="sxs-lookup"><span data-stu-id="cbe76-297">Select some code in the minified file in the Editor pane.</span></span>
1.  <span data-ttu-id="cbe76-298">选择 **"彩色打印"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="cbe76-298">Select the **Pretty print** button.</span></span>  
     
<span data-ttu-id="cbe76-299">格式化的代码显示在新选项卡中，并滚动到所选的代码。</span><span class="sxs-lookup"><span data-stu-id="cbe76-299">The formatted code appears in a new tab, scrolled to the code that you selected.</span></span>

<span data-ttu-id="cbe76-300">有关详细信息，请参阅使用非常打印 [重新设置缩小的 JavaScript 文件][DevToolsJavaScriptReferenceReformat]。</span><span class="sxs-lookup"><span data-stu-id="cbe76-300">For more information, see [Reformat a minified JavaScript file with pretty-print][DevToolsJavaScriptReferenceReformat].</span></span>  

### <a name="mapping-minified-code-to-your-source-code-to-show-readable-code"></a><span data-ttu-id="cbe76-301">将缩小代码映射到源代码以显示可读代码</span><span class="sxs-lookup"><span data-stu-id="cbe76-301">Mapping minified code to your source code to show readable code</span></span>

<span data-ttu-id="cbe76-302">来自预处理器的源映射会导致 DevTools 加载原始 JavaScript 源文件以及服务器返回的缩小的转换后的 JavaScript 文件。</span><span class="sxs-lookup"><span data-stu-id="cbe76-302">Source maps from preprocessors cause DevTools to load your original JavaScript source files in addition to your minified, transformed JavaScript files that are returned by the server.</span></span>  <span data-ttu-id="cbe76-303">然后，在设置断点并逐步执行代码时查看原始源文件。</span><span class="sxs-lookup"><span data-stu-id="cbe76-303">You then view your original source files while you set breakpoints and step through code.</span></span>  <span data-ttu-id="cbe76-304">同时，Microsoft Edge运行缩小代码。</span><span class="sxs-lookup"><span data-stu-id="cbe76-304">Meanwhile, Microsoft Edge is actually running your minified code.</span></span>  

<span data-ttu-id="cbe76-305">在 **"编辑器**"窗格中，如果右键单击 JavaScript 文件，然后选择\*\*\*\*"添加源映射"，将出现一个弹出框，包含"源**映射 URL"** 文本框和"添加 **"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="cbe76-305">In the **Editor** pane, if you right-click a JavaScript file and then select **Add source map**, a popup box appears, with a **Source map URL** textbox and an **Add** button.</span></span>

<span data-ttu-id="cbe76-306">即使组合、缩小或编译前端代码，源映射方法也保持其可读和可调试性。</span><span class="sxs-lookup"><span data-stu-id="cbe76-306">The source-mapping approach keeps your front-end code human-readable and debuggable even after you combine, minify, or compile it.</span></span>
<span data-ttu-id="cbe76-307">有关详细信息，请参阅 [将预处理的代码映射到源代码][DevToolsJavaScriptSourceMaps]。</span><span class="sxs-lookup"><span data-stu-id="cbe76-307">For more information, see [Map preprocessed code to source code][DevToolsJavaScriptSourceMaps].</span></span>

### <a name="transformations-from-source-code-to-compiled-front-end-code"></a><span data-ttu-id="cbe76-308">从源代码转换到编译的前端代码</span><span class="sxs-lookup"><span data-stu-id="cbe76-308">Transformations from source code to compiled front-end code</span></span>

<span data-ttu-id="cbe76-309">如果使用转换 JavaScript 文件（如 React）的框架，则本地源 JavaScript 可能不同于服务器返回的前端 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="cbe76-309">If you use a framework that transforms your JavaScript files, such as React, your local source JavaScript might be different than the front-end JavaScript that's returned by the server.</span></span>  <span data-ttu-id="cbe76-310">此方案不支持工作区，但在此方案中支持源代码映射。</span><span class="sxs-lookup"><span data-stu-id="cbe76-310">Workspaces aren't supported in this scenario, but source code mapping is supported in this scenario.</span></span>  

<span data-ttu-id="cbe76-311">在开发环境中，服务器可能包括源地图和原始或 `.ts` `.jsx` 用于React。</span><span class="sxs-lookup"><span data-stu-id="cbe76-311">In a development environment, your server might include your source maps and your original `.ts` or `.jsx` files for React.</span></span>  <span data-ttu-id="cbe76-312">源 **工具** 显示这些文件，但不允许编辑这些文件。</span><span class="sxs-lookup"><span data-stu-id="cbe76-312">The **Sources** tool displays these files, but doesn't allow you to edit these files.</span></span>  <span data-ttu-id="cbe76-313">当你设置断点并使用调试器时，DevTools 将显示原始或文件，但实际上是分步调试 `.ts` `.jsx` JavaScript 文件缩小版本。</span><span class="sxs-lookup"><span data-stu-id="cbe76-313">When you set breakpoints and use the debugger, DevTools displays your original `.ts` or `.jsx` files, but actually steps-through the minified version of your JavaScript files.</span></span>

<span data-ttu-id="cbe76-314">在此方案中， **源** 工具可用于检查和逐步执行从服务器返回的转换的前端 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="cbe76-314">In this scenario, the **Sources** tool is useful for inspecting and stepping-through the transformed, front-end JavaScript that's returned from the server.</span></span>  <span data-ttu-id="cbe76-315">使用调试器定义 Watch 表达式，并使用控制台输入 JavaScript 表达式以操作范围内的数据。</span><span class="sxs-lookup"><span data-stu-id="cbe76-315">Use the debugger to define Watch expressions, and use the Console to enter JavaScript expressions to manipulate data that's in-scope.</span></span>

### <a name="editing-a-css-file"></a><span data-ttu-id="cbe76-316">编辑 CSS 文件</span><span class="sxs-lookup"><span data-stu-id="cbe76-316">Editing a CSS file</span></span>

<span data-ttu-id="cbe76-317">在 DevTools 中编辑 CSS 的方法有两种：</span><span class="sxs-lookup"><span data-stu-id="cbe76-317">There are two ways to edit CSS in DevTools:</span></span>  

*   <span data-ttu-id="cbe76-318">在 **"元素** "工具中，通过用户界面控件一次处理一个 CSS 设置。</span><span class="sxs-lookup"><span data-stu-id="cbe76-318">In the **Elements** tool, you work with one CSS setting at a time, through user interface controls.</span></span>  <span data-ttu-id="cbe76-319">在大多数情况下，建议使用此方法。</span><span class="sxs-lookup"><span data-stu-id="cbe76-319">This approach is recommended in most cases.</span></span>  <span data-ttu-id="cbe76-320">有关详细信息，请参阅"样式"窗格中[的"编辑 CSS 字体样式和设置"。][DevToolsInspectStylesEditFonts]</span><span class="sxs-lookup"><span data-stu-id="cbe76-320">For more information, see [Edit CSS font styles and settings in the Styles pane][DevToolsInspectStylesEditFonts].</span></span>  
*   <span data-ttu-id="cbe76-321">在 **"源** "工具中，使用文本编辑器。</span><span class="sxs-lookup"><span data-stu-id="cbe76-321">In the **Sources** tool, you use a text editor.</span></span>  
    
<span data-ttu-id="cbe76-322">源工具支持直接编辑 CSS 文件。</span><span class="sxs-lookup"><span data-stu-id="cbe76-322">The Sources tool supports directly editing a CSS file.</span></span>  <span data-ttu-id="cbe76-323">例如，如果编辑教程"使用 [工作区][DevtoolsGuideChromiumWorkspacesIndex] 编辑文件"中的 CSS 文件以匹配下面的样式规则，则呈现的网页左上角的元素将更改 `H1` 为绿色：</span><span class="sxs-lookup"><span data-stu-id="cbe76-323">For example, if you edit the CSS file from the tutorial [Edit files with Workspaces][DevtoolsGuideChromiumWorkspacesIndex] to match the style rule below, the `H1` element in the upper left of the rendered webpage changes to green:</span></span>

```css
h1 {
  color: green;
}  
```  

:::image type="complex" source="../media/edit-css.msft.png" alt-text="编辑编辑器窗格中的 CSS 以将 H1 标题的文本颜色更改为绿色" lightbox="../media/edit-css.msft.png":::
   <span data-ttu-id="cbe76-325">编辑编辑器窗格中 **的** CSS 以将标题的文本 `H1` 颜色更改为绿色</span><span class="sxs-lookup"><span data-stu-id="cbe76-325">Edit CSS in the **Editor** pane to change the text color of the `H1` heading to green</span></span>  
:::image-end:::  

<span data-ttu-id="cbe76-326">CSS 更改会立即生效;无需手动保存更改。</span><span class="sxs-lookup"><span data-stu-id="cbe76-326">CSS changes take effect immediately; you don't need to manually save the changes.</span></span>

#### <a name="see-also"></a><span data-ttu-id="cbe76-327">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cbe76-327">See also</span></span>  

*   [<span data-ttu-id="cbe76-328">在“样式”窗格中编辑 CSS 字体样式和设置</span><span class="sxs-lookup"><span data-stu-id="cbe76-328">Edit CSS font styles and settings in the Styles pane</span></span>][DevToolsInspectStylesEditFonts]  
*   <span data-ttu-id="cbe76-329">[适用于初学者的 DevTools：CSS 入门][DevToolsBeginnersCss] - 教程</span><span class="sxs-lookup"><span data-stu-id="cbe76-329">[DevTools for beginners: Get started with CSS][DevToolsBeginnersCss] - tutorial</span></span>  
    
### <a name="editing-an-html-file"></a><span data-ttu-id="cbe76-330">编辑 HTML 文件</span><span class="sxs-lookup"><span data-stu-id="cbe76-330">Editing an HTML file</span></span>

<span data-ttu-id="cbe76-331">在 DevTools 中编辑 HTML 的方法有两种：</span><span class="sxs-lookup"><span data-stu-id="cbe76-331">There are two ways to edit HTML in DevTools:</span></span>  

*   <span data-ttu-id="cbe76-332">在 **"元素** "工具中，通过用户界面控件一次处理一个 HTML 元素。</span><span class="sxs-lookup"><span data-stu-id="cbe76-332">In the **Elements** tool, you work with one HTML element at a time, through user interface controls.</span></span>  
*   <span data-ttu-id="cbe76-333">在 **"源** "工具中，使用文本编辑器。</span><span class="sxs-lookup"><span data-stu-id="cbe76-333">In the **Sources** tool, you use a text editor.</span></span>  
    
:::image type="complex" source="../media/sources-html-editor.msft.png" alt-text="源工具的 HTML 编辑器" lightbox="../media/sources-html-editor.msft.png":::
   <span data-ttu-id="cbe76-335">源 **工具的** HTML 编辑器</span><span class="sxs-lookup"><span data-stu-id="cbe76-335">The HTML editor of the **Sources** tool</span></span>
:::image-end:::  

<span data-ttu-id="cbe76-336">与 JavaScript 或 CSS 文件不同，无法在"源"工具中直接编辑 Web 服务器返回的 HTML 文件。</span><span class="sxs-lookup"><span data-stu-id="cbe76-336">Unlike a JavaScript or CSS file, an HTML file that is returned by the web server cannot be directly edited in the Sources tool.</span></span>  <span data-ttu-id="cbe76-337">若要使用"源"工具的编辑器编辑 HTML 文件，HTML 文件必须位于"工作区"或" **替代"** 选项卡上。 请参阅当前文章的以下子部分：</span><span class="sxs-lookup"><span data-stu-id="cbe76-337">To edit an HTML file using the Editor of the Sources tool, the HTML file must be in a Workspace or on the **Overrides** tab.  See these subsections of the current article:</span></span>  

*   [<span data-ttu-id="cbe76-338">使用"文件系统"选项卡定义本地 Workspace</span><span class="sxs-lookup"><span data-stu-id="cbe76-338">Using the Filesystem tab to define a local Workspace</span></span>](#using-the-filesystem-tab-to-define-a-local-workspace)  
*   [<span data-ttu-id="cbe76-339">使用"覆盖"选项卡覆盖包含本地文件的服务器文件</span><span class="sxs-lookup"><span data-stu-id="cbe76-339">Using the Overrides tab to override server files with local files</span></span>](#using-the-overrides-tab-to-override-server-files-with-local-files)  
   
<span data-ttu-id="cbe76-340">若要保存更改，请在 `Ctrl` + `S` Windows/Linux 或 `Command` + `S` macOS 上选择。</span><span class="sxs-lookup"><span data-stu-id="cbe76-340">To save changes, select `Ctrl`+`S` on Windows/Linux or `Command`+`S` on macOS.</span></span>  <span data-ttu-id="cbe76-341">编辑后的文件标有星号。</span><span class="sxs-lookup"><span data-stu-id="cbe76-341">An edited file is marked by an asterisk.</span></span>  
<span data-ttu-id="cbe76-342">若要查找文本，请在 `Ctrl` + `F` Windows/Linux 或 `Command` + `F` macOS 上选择。</span><span class="sxs-lookup"><span data-stu-id="cbe76-342">To find text, select `Ctrl`+`F` on Windows/Linux or `Command`+`F` on macOS.</span></span>  
<span data-ttu-id="cbe76-343">若要撤消编辑，请在 `Ctrl` + `Z` Windows/Linux 或 `Command` + `Z` macOS 上选择。</span><span class="sxs-lookup"><span data-stu-id="cbe76-343">To undo an edit, select `Ctrl`+`Z` on Windows/Linux or `Command`+`Z` on macOS.</span></span>  
<span data-ttu-id="cbe76-344">若要在编辑 HTML 文件时查看其他命令，请在"编辑器"窗格中右键单击 HTML 文件。</span><span class="sxs-lookup"><span data-stu-id="cbe76-344">To view other commands while editing an HTML file, in the Editor pane, right-click the HTML file.</span></span>  
<span data-ttu-id="cbe76-345">您还可以使用 HTML 编辑器（而不是 DevTools）编辑 HTML。</span><span class="sxs-lookup"><span data-stu-id="cbe76-345">You can also edit HTML by using an HTML editor, rather than DevTools.</span></span>  <span data-ttu-id="cbe76-346">例如，文章 [DevTools for beginners： Get started with HTML and the DOM][DevToolsBeginnersHtml] uses a website that enables HTML editing within the webpage.</span><span class="sxs-lookup"><span data-stu-id="cbe76-346">For example, the article [DevTools for beginners: Get started with HTML and the DOM][DevToolsBeginnersHtml] uses a website that enables HTML editing within the webpage.</span></span>  

### <a name="going-to-a-line-number-or-function"></a><span data-ttu-id="cbe76-347">访问行号或函数</span><span class="sxs-lookup"><span data-stu-id="cbe76-347">Going to a line number or function</span></span>

<span data-ttu-id="cbe76-348">若要转到在编辑器窗格中打开的文件中行号或符号 \(如函数名称\) ，可以使用命令菜单，而不是滚动整个文件。</span><span class="sxs-lookup"><span data-stu-id="cbe76-348">To go to a line number or symbol \(such as a function name\) in the file which is open in the Editor pane, you can use the Command Menu, rather than scrolling through the file.</span></span>

1.  <span data-ttu-id="cbe76-349">在 **导航器窗格中** ，选择省略号 \(`...` \) \(**更多选项**\) ，然后选择打开 **文件**。</span><span class="sxs-lookup"><span data-stu-id="cbe76-349">In the **Navigator** pane, select the ellipses \(`...`\) \(**More options**\), and then select **Open File**.</span></span>  <span data-ttu-id="cbe76-350">将显示"命令菜单"。</span><span class="sxs-lookup"><span data-stu-id="cbe76-350">The Command Menu appears.</span></span>  
1.  <span data-ttu-id="cbe76-351">键入下列字符之一：</span><span class="sxs-lookup"><span data-stu-id="cbe76-351">Type one of the following characters:</span></span>  
     
| <span data-ttu-id="cbe76-352">Character</span><span class="sxs-lookup"><span data-stu-id="cbe76-352">Character</span></span> | <span data-ttu-id="cbe76-353">命令名称</span><span class="sxs-lookup"><span data-stu-id="cbe76-353">Command name</span></span> | <span data-ttu-id="cbe76-354">用途</span><span class="sxs-lookup"><span data-stu-id="cbe76-354">Purpose</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="cbe76-355">\:</span><span class="sxs-lookup"><span data-stu-id="cbe76-355">\:</span></span> | **<span data-ttu-id="cbe76-356">转到行</span><span class="sxs-lookup"><span data-stu-id="cbe76-356">Go to line</span></span>** | <span data-ttu-id="cbe76-357">转到行号。</span><span class="sxs-lookup"><span data-stu-id="cbe76-357">Go to a line number.</span></span>  |  
| \@ | **<span data-ttu-id="cbe76-358">转到符号</span><span class="sxs-lookup"><span data-stu-id="cbe76-358">Go to symbol</span></span>** | <span data-ttu-id="cbe76-359">转到函数。</span><span class="sxs-lookup"><span data-stu-id="cbe76-359">Go to a function.</span></span>  <span data-ttu-id="cbe76-360">键入 时，命令菜单会列出在"编辑器"窗格中打开的 `@` JavaScript 文件中找到的函数。</span><span class="sxs-lookup"><span data-stu-id="cbe76-360">When you type `@`, the Command Menu lists the functions that are found in the JavaScript file which is open in the Editor pane.</span></span>  |  
   
<span data-ttu-id="cbe76-361">有关详细信息，请参阅 Run [commands with the Microsoft Edge DevTools Command Menu][DevToolsCommandMenuIndex]。</span><span class="sxs-lookup"><span data-stu-id="cbe76-361">For more information, see [Run commands with the Microsoft Edge DevTools Command Menu][DevToolsCommandMenuIndex].</span></span>

### <a name="displaying-source-files-when-using-a-different-tool"></a><span data-ttu-id="cbe76-362">使用不同的工具时显示源文件</span><span class="sxs-lookup"><span data-stu-id="cbe76-362">Displaying source files when using a different tool</span></span>

<span data-ttu-id="cbe76-363">在 DevTools 中查看源文件的主要位置是源**工具。**</span><span class="sxs-lookup"><span data-stu-id="cbe76-363">The main place to view source files in the DevTools is within the **Sources** tool.</span></span>  <span data-ttu-id="cbe76-364">但有时，你需要在查看或编辑源文件时访问其他\*\*\*\* 工具，\*\*\*\* 如元素或控制台。</span><span class="sxs-lookup"><span data-stu-id="cbe76-364">But sometimes you need to access other tools, such as **Elements** or **Console**, while viewing or editing your source files.</span></span>  <span data-ttu-id="cbe76-365">使用 **"箱"中的** "快速源 ["工具][DevtoolsCustomizeIndexDrawer]。</span><span class="sxs-lookup"><span data-stu-id="cbe76-365">Use the **Quick Sources** tool in the [Drawer][DevtoolsCustomizeIndexDrawer].</span></span>  

1.  <span data-ttu-id="cbe76-366">选择除"源"工具 **外** 的其他工具，如 **"元素"** 工具。</span><span class="sxs-lookup"><span data-stu-id="cbe76-366">Select a tool other than the **Sources** tool, such as the **Elements** tool.</span></span>  
1.  <span data-ttu-id="cbe76-367">选择 `Ctrl` + `Shift` + `P` \(Windows、Linux\) 或 `Command` + `Shift` + `P` \(macOS\)。</span><span class="sxs-lookup"><span data-stu-id="cbe76-367">Select `Ctrl`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\).</span></span>  <span data-ttu-id="cbe76-368">命令菜单将打开。</span><span class="sxs-lookup"><span data-stu-id="cbe76-368">The Command Menu opens.</span></span>  
1.  <span data-ttu-id="cbe76-369">键入 `Quick Source` ，然后选择"显示**快速源"。**</span><span class="sxs-lookup"><span data-stu-id="cbe76-369">Type `Quick Source`, and then select **Show Quick Source**.</span></span>  <span data-ttu-id="cbe76-370">在"DevTools"窗口的底部，将显示"箱"，并选中 **"快速源"** 面板。</span><span class="sxs-lookup"><span data-stu-id="cbe76-370">At the bottom of the DevTools window, the Drawer appears, with the **Quick Source** panel selected.</span></span>  <span data-ttu-id="cbe76-371">快速**源**面板包含你在源工具中编辑的最后一个文件，\*\*\*\* 该文件位于 DevTools 代码编辑器的精简版本中。</span><span class="sxs-lookup"><span data-stu-id="cbe76-371">The **Quick Source** panel contains the last file you edited in the **Sources** tool, within a compact version of the DevTools code editor.</span></span>  
1.  <span data-ttu-id="cbe76-372">选择 `Ctrl` + `P` \(Windows、Linux\) 或 `Command` + `P` \(macOS\) 打开 **"打开文件"** 对话框。</span><span class="sxs-lookup"><span data-stu-id="cbe76-372">Select `Ctrl`+`P` \(Windows, Linux\) or `Command`+`P` \(macOS\) to open the **Open File** dialog.</span></span>  
    
## <a name="using-the-debugger-pane-to-debug-javascript-code"></a><span data-ttu-id="cbe76-373">使用调试器窗格调试 JavaScript 代码</span><span class="sxs-lookup"><span data-stu-id="cbe76-373">Using the Debugger pane to debug JavaScript code</span></span>

<span data-ttu-id="cbe76-374">使用 JavaScript 调试程序逐步调试服务器返回的 JavaScript 代码。</span><span class="sxs-lookup"><span data-stu-id="cbe76-374">Use the JavaScript debugger to step through the JavaScript code that's returned by the server.</span></span>  
<span data-ttu-id="cbe76-375">调试程序包括调试器\*\*\*\* 窗格，以及你在编辑器窗格中的代码行上设置的**断**点。</span><span class="sxs-lookup"><span data-stu-id="cbe76-375">The debugger includes the **Debugger** pane, along with breakpoints that you set on lines of code in the **Editor** pane.</span></span>

<span data-ttu-id="cbe76-376">借助调试器，你可以逐步调试代码，同时观察你指定的任何 JavaScript 表达式。</span><span class="sxs-lookup"><span data-stu-id="cbe76-376">With the debugger, you step through the code, while watching any JavaScript expressions you specify.</span></span>  <span data-ttu-id="cbe76-377">观察并手动更改变量值，并自动显示当前语句范围内哪些变量。</span><span class="sxs-lookup"><span data-stu-id="cbe76-377">Watch and manually change variable values, and automatically show which variables are in-scope for the current statement.</span></span>

:::image type="complex" source="../media/sources-paused-breakpoint-highlight-debug-pane.msft.png" alt-text="源工具的调试器窗格" lightbox="../media/sources-paused-breakpoint-highlight-debug-pane.msft.png":::
   <span data-ttu-id="cbe76-379">**"源"** 工具的"**调试器"** 窗格</span><span class="sxs-lookup"><span data-stu-id="cbe76-379">The **Debugger** pane of the **Sources** tool</span></span>  
:::image-end:::  

<span data-ttu-id="cbe76-380">调试器支持标准调试操作，例如：</span><span class="sxs-lookup"><span data-stu-id="cbe76-380">The debugger supports standard debugging actions, such as:</span></span>  

*   <span data-ttu-id="cbe76-381">设置断点以暂停代码。</span><span class="sxs-lookup"><span data-stu-id="cbe76-381">Setting breakpoints, to pause code.</span></span>  
*   <span data-ttu-id="cbe76-382">逐步执行代码。</span><span class="sxs-lookup"><span data-stu-id="cbe76-382">Stepping through code.</span></span>  
*   <span data-ttu-id="cbe76-383">查看和编辑属性和变量。</span><span class="sxs-lookup"><span data-stu-id="cbe76-383">Viewing and editing properties and variables.</span></span>  
*   <span data-ttu-id="cbe76-384">监视 JavaScript 表达式的值。</span><span class="sxs-lookup"><span data-stu-id="cbe76-384">Watching the values of JavaScript expressions.</span></span>  
*   <span data-ttu-id="cbe76-385">查看调用堆栈\(函数调用的顺序\) 。</span><span class="sxs-lookup"><span data-stu-id="cbe76-385">Viewing the call stack\(the sequence of function calls so far\).</span></span>  
    
<span data-ttu-id="cbe76-386">DevTools 中的调试器旨在外观、感觉和工作，如[Visual Studio Code][VisualStudioCodeDocsEditorDebugging]中的调试器[Visual Studio。][VisualStudioDebuggerNavigatingThroughCodeWithTheDebugger]</span><span class="sxs-lookup"><span data-stu-id="cbe76-386">The debugger in DevTools is designed to look, feel, and work like [the debugger in Visual Studio Code][VisualStudioCodeDocsEditorDebugging] and [the debugger in Visual Studio][VisualStudioDebuggerNavigatingThroughCodeWithTheDebugger].</span></span>

<span data-ttu-id="cbe76-387">以下小节包括调试：</span><span class="sxs-lookup"><span data-stu-id="cbe76-387">The following subsections cover debugging:</span></span>  

*   [<span data-ttu-id="cbe76-388">使用调试器的基本方法</span><span class="sxs-lookup"><span data-stu-id="cbe76-388">The basic approach to using a debugger</span></span>](#the-basic-approach-to-using-a-debugger)  
*   [<span data-ttu-id="cbe76-389">调试器监视和作用域比 console.log 的优点</span><span class="sxs-lookup"><span data-stu-id="cbe76-389">Advantages of the debugger's Watch and Scope over console.log</span></span>](#advantages-of-the-debuggers-watch-and-scope-over-consolelog)  
*   [<span data-ttu-id="cbe76-390">直接从Visual Studio Code调试</span><span class="sxs-lookup"><span data-stu-id="cbe76-390">Debug from Visual Studio Code directly</span></span>](#debug-from-visual-studio-code-directly)  
*   [<span data-ttu-id="cbe76-391">有关调试的文章</span><span class="sxs-lookup"><span data-stu-id="cbe76-391">Articles about debugging</span></span>](#articles-about-debugging)  
    
### <a name="the-basic-approach-to-using-a-debugger"></a><span data-ttu-id="cbe76-392">使用调试器的基本方法</span><span class="sxs-lookup"><span data-stu-id="cbe76-392">The basic approach to using a debugger</span></span>

<span data-ttu-id="cbe76-393">若要对 JavaScript 代码进行故障排除，可以在" `console.log()` 编辑器"窗格中 **插入** 语句。</span><span class="sxs-lookup"><span data-stu-id="cbe76-393">To troubleshoot JavaScript code, you can insert `console.log()` statements in the **Editor** pane.</span></span>  <span data-ttu-id="cbe76-394">另一种更强大的方法是使用 DevTools Microsoft Edge调试器。</span><span class="sxs-lookup"><span data-stu-id="cbe76-394">Another, more powerful approach is to use the debugger of Microsoft Edge DevTools.</span></span>  <span data-ttu-id="cbe76-395">熟悉调试器方法后，使用调试器实际上可以比 `console.log()` 更简单。</span><span class="sxs-lookup"><span data-stu-id="cbe76-395">Using a debugger can actually be simpler than `console.log()`, once you're familiar with the debugger approach.</span></span>

<span data-ttu-id="cbe76-396">若要在网页上使用调试器，通常设置断点，然后从网页发送表单，如下所示：</span><span class="sxs-lookup"><span data-stu-id="cbe76-396">To use a debugger on a webpage, you typically set a breakpoint and then send a form from the webpage, as follows:</span></span>

1.  <span data-ttu-id="cbe76-397">在浏览器的新选项卡中打开网页。</span><span class="sxs-lookup"><span data-stu-id="cbe76-397">Open the webpage in a new tab of the browser.</span></span>  <span data-ttu-id="cbe76-398">例如，在一个新选项卡中打开此表单网页[：Demo： 入门使用 DevTools Microsoft Edge (Chromium) JavaScript。][GlitchMicrosoftEdgeChromiumDevtoolsDebugJsGetStarted]</span><span class="sxs-lookup"><span data-stu-id="cbe76-398">For example, open this form webpage in a new tab: [Demo: Get Started Debugging JavaScript with Microsoft Edge (Chromium) DevTools][GlitchMicrosoftEdgeChromiumDevtoolsDebugJsGetStarted].</span></span>  
1.  <span data-ttu-id="cbe76-399">选择 `F12` 以打开 **"DevTools"** 窗口，然后选择"源 **"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="cbe76-399">Select `F12` to open the **DevTools** window, and then select the **Sources** tab.</span></span>  
1.  <span data-ttu-id="cbe76-400">在导航**器**窗格 \(左侧\) ，选择"页面"选项卡，然后选择 JavaScript\*\*\*\* 文件，例如 `get-started.js` 。</span><span class="sxs-lookup"><span data-stu-id="cbe76-400">In the **Navigator** pane \(on the left\), select the **Page** tab, and then select the JavaScript file, such as `get-started.js`.</span></span>  
1.  <span data-ttu-id="cbe76-401">在 **"编辑器** "窗格中，选择可疑代码行附近的行号，以在该行上设置断点。</span><span class="sxs-lookup"><span data-stu-id="cbe76-401">In the **Editor** pane, select a line number near a suspect line of code, to set a breakpoint on that line.</span></span>  <span data-ttu-id="cbe76-402">在下图中，在 行 上设置了断点 `var sum = addend1 + addend2;` 。</span><span class="sxs-lookup"><span data-stu-id="cbe76-402">In the figure below, a breakpoint is set on the line `var sum = addend1 + addend2;`.</span></span>  
1.  <span data-ttu-id="cbe76-403">在网页中，输入值并提交表单。</span><span class="sxs-lookup"><span data-stu-id="cbe76-403">In the webpage, enter values and submit the form.</span></span>  <span data-ttu-id="cbe76-404">例如，输入数字，如 `5` 和 `1` ，然后选择按钮添加数字 **1 和数字 2**。</span><span class="sxs-lookup"><span data-stu-id="cbe76-404">For example, enter numbers, such as `5` and `1`, then select the button **Add Number 1 and Number 2**.</span></span>  
    
    <span data-ttu-id="cbe76-405">调试程序运行 JavaScript 代码，然后在断点处暂停。</span><span class="sxs-lookup"><span data-stu-id="cbe76-405">The debugger runs the JavaScript code and then pauses at the breakpoint.</span></span>  <span data-ttu-id="cbe76-406">调试程序现在进入暂停模式，因此你可以检查范围内属性的值，并逐步执行代码。</span><span class="sxs-lookup"><span data-stu-id="cbe76-406">The debugger is now in Paused mode, so you can inspect the values of the properties that are in-scope, and step through the code.</span></span>  
    
    :::image type="complex" source="../media/sources-paused-breakpoint-highlights.msft.png" alt-text="进入调试器暂停模式" lightbox="../media/sources-paused-breakpoint-highlights.msft.png":::
        <span data-ttu-id="cbe76-408">进入调试器暂停模式</span><span class="sxs-lookup"><span data-stu-id="cbe76-408">Entering Paused mode of the debugger</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="cbe76-409">在上图中，我们添加了 Watch 表达式和 ，并跨 `sum` `typeof sum` 断点添加了两行。</span><span class="sxs-lookup"><span data-stu-id="cbe76-409">In the above figure, we added the Watch expressions `sum` and `typeof sum`, and stepped two lines past the breakpoint.</span></span>  
    
1.  <span data-ttu-id="cbe76-410">检查"范围"窗格中 **的值，** 其中显示当前断点范围内的所有变量或属性及其值。</span><span class="sxs-lookup"><span data-stu-id="cbe76-410">Examine the values in the **Scope** pane, which shows all variables or properties that are in-scope for the current breakpoint, and their values.</span></span>  <span data-ttu-id="cbe76-411">或者，在"监视"窗格中 **添加** 表达式。</span><span class="sxs-lookup"><span data-stu-id="cbe76-411">Or, add expressions in the **Watch** pane.</span></span>  <span data-ttu-id="cbe76-412">这些表达式与在语句中编写以调试代码 `console.log` 的表达式相同。</span><span class="sxs-lookup"><span data-stu-id="cbe76-412">These expressions are the same expressions that you would write within a `console.log` statement to debug your code.</span></span>  <span data-ttu-id="cbe76-413">若要运行 JavaScript 命令以操作当前上下文中的数据，请使用 **控制台**。</span><span class="sxs-lookup"><span data-stu-id="cbe76-413">To run JavaScript commands to manipulate data in the current context, use the **Console**.</span></span>  <span data-ttu-id="cbe76-414">若要打开控制台，请选择 `Esc` 。</span><span class="sxs-lookup"><span data-stu-id="cbe76-414">To open the console, select `Esc`.</span></span>  
1.  <span data-ttu-id="cbe76-415">使用调试器窗格顶部的控件（如 Step **\(**`F9` \) ）逐步调试代码。</span><span class="sxs-lookup"><span data-stu-id="cbe76-415">Step through the code by using the controls at the top of the **Debugger** pane, such as **Step** \(`F9`\).</span></span>
    
#### <a name="see-also"></a><span data-ttu-id="cbe76-416">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cbe76-416">See also</span></span>

*   <span data-ttu-id="cbe76-417">[JavaScript 调试入门][DevtoolsGuideChromiumJavascriptIndex] - 使用包含一些表单控件的现有简单网页的教程。</span><span class="sxs-lookup"><span data-stu-id="cbe76-417">[Get started with debugging JavaScript][DevtoolsGuideChromiumJavascriptIndex] - a tutorial using an existing, simple webpage that contains a few form controls.</span></span>
    
### <a name="advantages-of-the-debuggers-watch-and-scope-over-consolelog"></a><span data-ttu-id="cbe76-418">调试器监视和作用域比控制台\.log 的优点</span><span class="sxs-lookup"><span data-stu-id="cbe76-418">Advantages of the debugger\'s Watch and Scope over console\.log</span></span>  

<span data-ttu-id="cbe76-419">这三种方法是等效的：</span><span class="sxs-lookup"><span data-stu-id="cbe76-419">These three approaches are equivalent:</span></span>

*   <span data-ttu-id="cbe76-420">临时添加 语句 `console.log(sum)` 和 `console.log(typeof sum)` 代码，其中 `sum` 位于范围内。</span><span class="sxs-lookup"><span data-stu-id="cbe76-420">Temporarily adding the statements `console.log(sum)` and `console.log(typeof sum)` in the code, where `sum` is in-scope.</span></span>  
*   <span data-ttu-id="cbe76-421">当调试器暂停在作用域内时，在 `sum` `console.log(typeof sum)` DevTools\*\*\*\* 的控制台窗格中发出 `sum` 语句。</span><span class="sxs-lookup"><span data-stu-id="cbe76-421">Issuing the statements `sum` and `console.log(typeof sum)` in the **Console** pane of the DevTools, when the debugger is paused where `sum` is in-scope.</span></span>  
*   <span data-ttu-id="cbe76-422">设置 **监视表达式** `sum` 和 `typeof sum` 调试 **器窗格中** 的 。</span><span class="sxs-lookup"><span data-stu-id="cbe76-422">Setting the **Watch** expressions `sum` and `typeof sum` in the **Debugger** pane.</span></span>  
    
<span data-ttu-id="cbe76-423">当变量在范围内时，其值将自动显示在调试器窗格的"范围"部分，并且也会覆盖在计算位置的" `sum` `sum` 编辑器"\*\*\*\*\*\*\*\* `sum` 窗格中。</span><span class="sxs-lookup"><span data-stu-id="cbe76-423">When the variable `sum` is in-scope, `sum` and its value are automatically shown in the **Scope** section of the **Debugger** pane, and are also overlaid in the Editor pane where `sum` is calculated.</span></span>  <span data-ttu-id="cbe76-424">因此，您可能不需要为 定义 Watch 表达式 `sum` 。</span><span class="sxs-lookup"><span data-stu-id="cbe76-424">So you probably wouldn't need to define a Watch expression for `sum`.</span></span>

<span data-ttu-id="cbe76-425">调试程序提供比语句更丰富、更灵活的显示 `console.log` 和环境。</span><span class="sxs-lookup"><span data-stu-id="cbe76-425">The debugger gives a richer, more flexible display and environment than a `console.log` statement.</span></span>  <span data-ttu-id="cbe76-426">例如，在调试器中，在逐步调试代码时，可以显示和更改所有当前定义的属性和变量的值。</span><span class="sxs-lookup"><span data-stu-id="cbe76-426">For example, in the debugger, as you step through the code, you can display and change the values of all currently defined properties and variables.</span></span>  <span data-ttu-id="cbe76-427">还可以在控制台中发出 JavaScript\*\*\*\* 语句，例如更改作用域内数组中的值。</span><span class="sxs-lookup"><span data-stu-id="cbe76-427">You can also issue JavaScript statements in the **Console**, such as to change values in an array that's in-scope.</span></span>  <span data-ttu-id="cbe76-428">\(若要显示控制台，请选择 **Esc**.\) </span><span class="sxs-lookup"><span data-stu-id="cbe76-428">\(To display the Console, select **Esc**.\)</span></span>

<span data-ttu-id="cbe76-429">刷新网页时，将保留断点和监视表达式。</span><span class="sxs-lookup"><span data-stu-id="cbe76-429">Breakpoints and Watch expressions are preserved when you refresh the webpage.</span></span>

### <a name="debug-from-visual-studio-code-directly"></a><span data-ttu-id="cbe76-430">直接从Visual Studio Code调试</span><span class="sxs-lookup"><span data-stu-id="cbe76-430">Debug from Visual Studio Code directly</span></span>

<span data-ttu-id="cbe76-431">若要使用功能更加完整的 Visual Studio Code 调试程序，而不是使用 DevTools 调试器，请使用**Microsoft Edge Tools for VS Code** extension for Visual Studio Code。</span><span class="sxs-lookup"><span data-stu-id="cbe76-431">To use the more full-featured debugger of Visual Studio Code instead of the DevTools debugger, use the **Microsoft Edge Tools for VS Code** extension for Visual Studio Code.</span></span>

:::image type="complex" source="../media/microsoft-edge-tools-for-vs-code-extension.msft.png" alt-text="Microsoft Edge工具VS Code扩展Visual Studio Code" lightbox="../media/microsoft-edge-tools-for-vs-code-extension.msft.png":::
   <span data-ttu-id="cbe76-433">Microsoft Edge**工具VS Code**扩展Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="cbe76-433">The **Microsoft Edge Tools for VS Code** extension for Visual Studio Code</span></span>  
:::image-end:::  

<span data-ttu-id="cbe76-434">此扩展提供对开发人员工具**的元素**Microsoft Edge\*\*\*\* 网络工具的访问，从 Microsoft Visual Studio Code。</span><span class="sxs-lookup"><span data-stu-id="cbe76-434">This extension provides access to the **Elements** and **Network** tools of Microsoft Edge DevTools, from within Microsoft Visual Studio Code.</span></span>  

<span data-ttu-id="cbe76-435">有关详细信息，请参阅 Visual Studio Code[概述][VisualStudioCodeIndex]和 GitHub 自述Microsoft Edge开发人员[工具Visual Studio Code。][GithubMicrosoftVscodeEdgeDevtools]</span><span class="sxs-lookup"><span data-stu-id="cbe76-435">For more information, see [Visual Studio Code overview][VisualStudioCodeIndex] and the GitHub Readme page, [Microsoft Edge Developer Tools for Visual Studio Code][GithubMicrosoftVscodeEdgeDevtools].</span></span>

### <a name="articles-about-debugging"></a><span data-ttu-id="cbe76-436">有关调试的文章</span><span class="sxs-lookup"><span data-stu-id="cbe76-436">Articles about debugging</span></span>

<span data-ttu-id="cbe76-437">以下文章涵盖调试 **器** 窗格和断点：</span><span class="sxs-lookup"><span data-stu-id="cbe76-437">The following articles cover the **Debugger** pane and breakpoints:</span></span>

*   <span data-ttu-id="cbe76-438">[在开发人员工具][DevtoolsGuideChromiumJavascriptIndex]中Microsoft Edge JavaScript 入门 - 使用现有简单项目 (屏幕截图\) 的教程 \) 。</span><span class="sxs-lookup"><span data-stu-id="cbe76-438">[Get started with debugging JavaScript in Microsoft Edge DevTools][DevtoolsGuideChromiumJavascriptIndex] - A tutorial \(with screen captures\), using an existing, simple project.</span></span>  
*   <span data-ttu-id="cbe76-439">[使用调试器功能][DevToolsJavaScriptReference] - 如何使用调试器设置断点、逐步调试代码、查看和修改变量值、观看 JavaScript 表达式以及查看调用堆栈。</span><span class="sxs-lookup"><span data-stu-id="cbe76-439">[Use the debugger features][DevToolsJavaScriptReference] - How to use the debugger to set breakpoints, step through code, view and modify variable values, watch JavaScript expressions, and view the call stack.</span></span>  
*   <span data-ttu-id="cbe76-440">[使用断点暂停代码][DevToolsJavaScriptBreakpoints] - 如何在调试器中设置基本和专用断点。</span><span class="sxs-lookup"><span data-stu-id="cbe76-440">[Pause your code with breakpoints][DevToolsJavaScriptBreakpoints] - How to set basic and specialized breakpoints in the debugger.</span></span>  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="cbe76-441">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="cbe76-441">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsBeginnersCss]: ../beginners/css.md "适用于初学者的 DevTools：CSS |Microsoft Docs"  
[DevToolsBeginnersHtml]: ../beginners/html.md "适合初学者的 DevTools：HTML 和 DOM |Microsoft Docs"  
[DevToolsCommandMenuIndex]: ../command-menu/index.md "使用 Microsoft Edge DevTools 命令菜单运行命令 | Microsoft Docs"   
[DevtoolsCustomizeIndexDrawer]: ../customize/index.md#drawer "设置 - 自定义 Microsoft Edge 开发工具 | Microsoft Docs"  
[DevToolsCustomizePlacement]: ../customize/placement.md "将Microsoft Edge DevTools 放置 (Undock，将扩展坞更改为底部，将扩展坞更改为左侧) |Microsoft Docs"  
[DevtoolsGuideChromiumJavascriptIndex]: ../javascript/index.md "在 Microsoft Edge 开发人员工具中调试 JavaScript 入门 | Microsoft Docs"  
[DevtoolsGuideChromiumJavascriptSnippets]: ../javascript/snippets.md "使用 DevTools 工具在任意网页上Microsoft Edge JavaScript |Microsoft Docs"  
[DevtoolsGuideChromiumWorkspacesIndex]: ../workspaces/index.md "使用工作区列表编辑|Microsoft Docs"  
[DevToolsInspectStylesEditFonts]: ../inspect-styles/edit-fonts.md "在&quot;样式&quot;窗格中编辑 CSS 字体样式|Microsoft Docs"  
[DevToolsJavaScriptBreakpoints]: ../javascript/breakpoints.md "使用断点或断点暂停|Microsoft Docs"  
[DevToolsJavaScriptGuidesMarkContentScriptsLibraryCode]: ../javascript/guides/mark-content-scripts-library-code.md "将内容脚本标记为库代码|Microsoft Docs"  
[DevtoolsJavascriptOverrides]: ../javascript/overrides.md "使用 Microsoft Edge DevTools 应用替代具有本地副本的网页|Microsoft Docs"  
[DevToolsJavaScriptReference]: ../javascript/reference.md "使用调试器功能|Microsoft Docs"  
[DevToolsJavaScriptReferenceReformat]: ../javascript/reference.md#reformat-a-minified-javascript-file-with-pretty-print "重新设置缩小的 JavaScript 文件，并采用非常打印的字体 - 使用调试器|Microsoft Docs"  
[DevToolsJavaScriptSourceMaps]: ../javascript/source-maps.md "将预处理的代码映射到源代码|Microsoft Docs"  
[VisualStudioCodeIndex]: ../../visual-studio-code/index.md "Visual Studio Code概述|Microsoft Docs"  
[ExtensionsChromiumGetstartPart2ContentScripts]: ../../extensions-chromium/getting-started/part2-content-scripts.md "创建扩展教程第 2 部分|Microsoft Docs"  

[VisualStudioDebuggerNavigatingThroughCodeWithTheDebugger]: /visualstudio/debugger/navigating-through-code-with-the-debugger "使用调试器工具Visual Studio代码|Microsoft Docs"  

[VisualStudioCodeDocsEditorDebugging]: https://code.visualstudio.com/docs/editor/debugging "调试|Visual Studio Code"  

[GithubMicrosoftVscodeEdgeDevtools]: https://github.com/microsoft/vscode-edge-devtools "Microsoft Edge开发人员工具Visual Studio Code |GitHub"  

[GlitchMicrosoftEdgeChromiumDevtoolsDebugJsGetStarted]: https://microsoft-edge-chromium-devtools.glitch.me/debug-js/get-started.html "演示：入门开发人员工具Microsoft Edge (Chromium) 调试 JavaScript |Microsoft Docs"  

[WhatwgHtmlSpecMulitpageOriginHtmlOrigin]: https://html.spec.whatwg.org/multipage/origin.html#origin "源 | HTML Standard"  

[MdnAddOnsWebextensionsContentScripts]: https://developer.mozilla.org/Add-ons/WebExtensions/Content_scripts "内容脚本|MDN"  

[TypescriptlangMain]: https://www.typescriptlang.org "TypeScript"  

[W3CHtml4Frames]: https://w3.org/TR/html401/present/frames.html "框架 | W3C"  

> [!NOTE]
> <span data-ttu-id="cbe76-467">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="cbe76-467">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="cbe76-468">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/sources)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="cbe76-468">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/sources) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="cbe76-470">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="cbe76-470">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  

<!--todo: needs an accessibility review to replace "view", "see", and "look" with "display", exception is "see also" headings -->  

<!--todo: need a consistency review to replace all UI interactions with "choose" and all keyboard interactions with "select" -->  
