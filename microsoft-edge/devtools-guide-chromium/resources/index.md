---
title: 通过 Microsoft Edge DevTools 查看页面资源
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/30/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 0977d0a9132c19742c3337f9dc0c3e1240508a3d
ms.sourcegitcommit: 4c24edbd1c591914cb4109511534851570a614cb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/30/2020
ms.locfileid: "10611915"
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





# <span data-ttu-id="6eabf-103">通过 Microsoft Edge DevTools 查看页面资源</span><span class="sxs-lookup"><span data-stu-id="6eabf-103">View Page Resources With Microsoft Edge DevTools</span></span>   

  

<span data-ttu-id="6eabf-104">本指南将教你如何使用 Microsoft Edge DevTools 查看网页的资源。</span><span class="sxs-lookup"><span data-stu-id="6eabf-104">This guide teaches you how to use Microsoft Edge DevTools to view the resources of a web page.</span></span>  <span data-ttu-id="6eabf-105">资源是页面需要正确显示的文件。</span><span class="sxs-lookup"><span data-stu-id="6eabf-105">Resources are the files that a page needs in order to display correctly.</span></span>  <span data-ttu-id="6eabf-106">资源示例包括 CSS、JavaScript 和 HTML 文件以及图像。</span><span class="sxs-lookup"><span data-stu-id="6eabf-106">Examples of resources include CSS, JavaScript, and HTML files, as well as images.</span></span>  

<span data-ttu-id="6eabf-107">本指南假定你熟悉[web 开发][MDNLearnWebDevelopment]和[Microsoft Edge DevTools][MicrosoftEdgeDevTools]的基础知识。</span><span class="sxs-lookup"><span data-stu-id="6eabf-107">This guide assumes that you are familiar with the basics of [web development][MDNLearnWebDevelopment] and [Microsoft Edge DevTools][MicrosoftEdgeDevTools].</span></span>  

## <span data-ttu-id="6eabf-108">打开资源</span><span class="sxs-lookup"><span data-stu-id="6eabf-108">Open resources</span></span>   

<span data-ttu-id="6eabf-109">当您知道要检查的资源的名称时，"**命令" 菜单**将提供打开资源的快速方法。</span><span class="sxs-lookup"><span data-stu-id="6eabf-109">When you know the name of the resource that you want to inspect, the **Command Menu** provides a fast way of opening the resource.</span></span>  

1.  <span data-ttu-id="6eabf-110">按 `Control` + `P` \ （Windows \）或 `Command` + `P` \ （macOS \）。</span><span class="sxs-lookup"><span data-stu-id="6eabf-110">Press `Control`+`P` \(Windows\) or `Command`+`P` \(macOS\).</span></span>  <span data-ttu-id="6eabf-111">"**打开文件**" 对话框随即打开。</span><span class="sxs-lookup"><span data-stu-id="6eabf-111">The **Open File** dialog opens.</span></span>  
    
    > ##### <span data-ttu-id="6eabf-112">图 1</span><span class="sxs-lookup"><span data-stu-id="6eabf-112">Figure 1</span></span>  
    > <span data-ttu-id="6eabf-113">"**打开文件**" 对话框</span><span class="sxs-lookup"><span data-stu-id="6eabf-113">The **Open File** dialog</span></span>  
    > !["打开文件" 对话框][ImageOpenFile]  
    
1.  <span data-ttu-id="6eabf-115">从下拉列表中选择文件，或者开始键入文件名，然后按 `Enter` 一次 "自动完成" 框中突出显示正确的文件。</span><span class="sxs-lookup"><span data-stu-id="6eabf-115">Select the file from the dropdown, or start typing the filename and press `Enter` once the correct file is highlighted in the autocomplete box.</span></span>  
    
    > ##### <span data-ttu-id="6eabf-116">图 2</span><span class="sxs-lookup"><span data-stu-id="6eabf-116">Figure 2</span></span>  
    > <span data-ttu-id="6eabf-117">在 "**打开文件**" 对话框中键入文件名</span><span class="sxs-lookup"><span data-stu-id="6eabf-117">Typing a filename in the **Open File** dialog</span></span>  
    > ![在 "打开文件" 对话框中键入文件名][ImageFileSearch]  
    
### <span data-ttu-id="6eabf-119">在 "网络" 面板中打开资源</span><span class="sxs-lookup"><span data-stu-id="6eabf-119">Open resources in the Network panel</span></span>   

<span data-ttu-id="6eabf-120">请参阅[检查资源的详细信息][DevtoolsNetworkInspectDetailsResource]。</span><span class="sxs-lookup"><span data-stu-id="6eabf-120">See [Inspect the details of a resource][DevtoolsNetworkInspectDetailsResource].</span></span>  

> ##### <span data-ttu-id="6eabf-121">图 3</span><span class="sxs-lookup"><span data-stu-id="6eabf-121">Figure 3</span></span>  
> <span data-ttu-id="6eabf-122">在网络面板中检查资源</span><span class="sxs-lookup"><span data-stu-id="6eabf-122">Inspecting a resource in the Network panel</span></span>  
> ![在网络面板中检查资源][ImageNetworkResponse]  

### <span data-ttu-id="6eabf-124">从其他面板中的 "网络" 面板中显示资源</span><span class="sxs-lookup"><span data-stu-id="6eabf-124">Reveal resources in the Network panel from other panels</span></span>   

<span data-ttu-id="6eabf-125">下面的[浏览资源](#browse-resources)部分介绍了如何从 DevTools UI 的各个部分查看资源。</span><span class="sxs-lookup"><span data-stu-id="6eabf-125">The [Browse resources](#browse-resources) section below shows you how to view resources from various parts of the DevTools UI.</span></span>  <span data-ttu-id="6eabf-126">如果您想要在 "**网络**" 面板中检查资源，请右键单击该资源，然后**在 "网络" 面板中选择 "显示**"。</span><span class="sxs-lookup"><span data-stu-id="6eabf-126">If you ever want to inspect a resource in the **Network** panel, right-click the resource and select **Reveal in Network panel**.</span></span>  

> ##### <span data-ttu-id="6eabf-127">图 4</span><span class="sxs-lookup"><span data-stu-id="6eabf-127">Figure 4</span></span>  
> <span data-ttu-id="6eabf-128">"**在网络中显示**" 选项</span><span class="sxs-lookup"><span data-stu-id="6eabf-128">The **Reveal in Network panel** option</span></span>  
> ![在网络面板中显示][ImageRevealNetwork]  

## <span data-ttu-id="6eabf-130">浏览资源</span><span class="sxs-lookup"><span data-stu-id="6eabf-130">Browse resources</span></span>   

### <span data-ttu-id="6eabf-131">浏览网络面板中的资源</span><span class="sxs-lookup"><span data-stu-id="6eabf-131">Browse resources in the Network panel</span></span>   

<span data-ttu-id="6eabf-132">请参阅[记录网络活动][DevtoolsNetworkLogActivity]。</span><span class="sxs-lookup"><span data-stu-id="6eabf-132">See [Log network activity][DevtoolsNetworkLogActivity].</span></span>  

> ##### <span data-ttu-id="6eabf-133">图 5</span><span class="sxs-lookup"><span data-stu-id="6eabf-133">Figure 5</span></span>  
> <span data-ttu-id="6eabf-134">网络日志中的页面资源</span><span class="sxs-lookup"><span data-stu-id="6eabf-134">Page resources in the Network Log</span></span>  
> ![网络日志中的页面资源][ImageNetworkLog]  

### <span data-ttu-id="6eabf-136">按目录浏览</span><span class="sxs-lookup"><span data-stu-id="6eabf-136">Browse by directory</span></span>   

<span data-ttu-id="6eabf-137">若要查看按目录组织的页面资源，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6eabf-137">To view the resources of a page organized by directory:</span></span>  

1.  <span data-ttu-id="6eabf-138">单击 "**源**" 选项卡以打开 "**源**" 面板。</span><span class="sxs-lookup"><span data-stu-id="6eabf-138">Click the **Sources** tab to open the **Sources** panel.</span></span>  
1.  <span data-ttu-id="6eabf-139">单击 "**页面**" 选项卡以显示页面的资源。</span><span class="sxs-lookup"><span data-stu-id="6eabf-139">Click the **Page** tab to show the resources of the page.</span></span>  <span data-ttu-id="6eabf-140">**页面**窗格随即打开。</span><span class="sxs-lookup"><span data-stu-id="6eabf-140">The **Page** pane opens.</span></span>  
    
    > ##### <span data-ttu-id="6eabf-141">图 6</span><span class="sxs-lookup"><span data-stu-id="6eabf-141">Figure 6</span></span>  
    > <span data-ttu-id="6eabf-142">**页面**窗格</span><span class="sxs-lookup"><span data-stu-id="6eabf-142">The **Page** pane</span></span>  
    > ![页面窗格][ImagePage]  
    
    <span data-ttu-id="6eabf-144">下面是[图 6](#figure-6)中不明显的项的细目：</span><span class="sxs-lookup"><span data-stu-id="6eabf-144">Here is a breakdown of the non-obvious items in [Figure 6](#figure-6):</span></span>  
    
    | <span data-ttu-id="6eabf-145">页面项目</span><span class="sxs-lookup"><span data-stu-id="6eabf-145">Page item</span></span> | <span data-ttu-id="6eabf-146">描述</span><span class="sxs-lookup"><span data-stu-id="6eabf-146">Description</span></span> |  
    |:--- |:--- |  
    | `top` | <span data-ttu-id="6eabf-147">主文档[浏览上下文][MDNInlineFrame]。</span><span class="sxs-lookup"><span data-stu-id="6eabf-147">The main document [browsing context][MDNInlineFrame].</span></span> |  
    | `airhorner.com` | <span data-ttu-id="6eabf-148">域。</span><span class="sxs-lookup"><span data-stu-id="6eabf-148">The domain.</span></span>  <span data-ttu-id="6eabf-149">嵌套在它下方的所有资源都来自该域。</span><span class="sxs-lookup"><span data-stu-id="6eabf-149">All resources nested under it come from that domain.</span></span>  <span data-ttu-id="6eabf-150">例如，文件的完整 URL `comlink.global.j` 可能 `https://airhorner.com/scripts/comlink.global.js` 。</span><span class="sxs-lookup"><span data-stu-id="6eabf-150">For example, the full URL of the `comlink.global.j` file is probably `https://airhorner.com/scripts/comlink.global.js`.</span></span> |  
    | `scripts` | <span data-ttu-id="6eabf-151">目录。</span><span class="sxs-lookup"><span data-stu-id="6eabf-151">A directory.</span></span> |  
    | `(index)` | <span data-ttu-id="6eabf-152">主 HTML 文档。</span><span class="sxs-lookup"><span data-stu-id="6eabf-152">The main HTML document.</span></span> |  
    | `sw.js` | <span data-ttu-id="6eabf-153">服务工作运行时上下文。</span><span class="sxs-lookup"><span data-stu-id="6eabf-153">A service worker runtime context.</span></span> |  
    
1.  <span data-ttu-id="6eabf-154">单击某个资源以在**编辑器**中查看它。</span><span class="sxs-lookup"><span data-stu-id="6eabf-154">Click a resource to view it in the **Editor**.</span></span>  
    
    > ##### <span data-ttu-id="6eabf-155">图 7</span><span class="sxs-lookup"><span data-stu-id="6eabf-155">Figure 7</span></span>  
    > <span data-ttu-id="6eabf-156">在**编辑器**中查看文件</span><span class="sxs-lookup"><span data-stu-id="6eabf-156">Viewing a file in the **Editor**</span></span>  
    > ![在编辑器中查看文件][ImageSourcesView]  
    
### <span data-ttu-id="6eabf-158">按文件名浏览</span><span class="sxs-lookup"><span data-stu-id="6eabf-158">Browse by filename</span></span>   

<span data-ttu-id="6eabf-159">默认情况下，**页面**窗格按目录对资源进行分组。</span><span class="sxs-lookup"><span data-stu-id="6eabf-159">By default the **Page** pane groups resources by directory.</span></span>  <span data-ttu-id="6eabf-160">若要禁用此分组并以简单列表的形式查看每个域的资源，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6eabf-160">To disable this grouping and view the resources for each domain as a flat list:</span></span>  

1.  <span data-ttu-id="6eabf-161">打开**页面**窗格。</span><span class="sxs-lookup"><span data-stu-id="6eabf-161">Open the **Page** pane.</span></span>  <span data-ttu-id="6eabf-162">请参阅[按目录浏览](#browse-by-directory)。</span><span class="sxs-lookup"><span data-stu-id="6eabf-162">See [Browse by directory](#browse-by-directory).</span></span>  
1.  <span data-ttu-id="6eabf-163">单击 "**更多选项**" `...` ，然后禁用 "**按文件夹分组**"。</span><span class="sxs-lookup"><span data-stu-id="6eabf-163">Click **More Options** `...` and disable **Group By Folder**.</span></span>  
    
    > ##### <span data-ttu-id="6eabf-164">图 8</span><span class="sxs-lookup"><span data-stu-id="6eabf-164">Figure 8</span></span>  
    > <span data-ttu-id="6eabf-165">"**按文件夹分组**" 选项</span><span class="sxs-lookup"><span data-stu-id="6eabf-165">The **Group By Folder** option</span></span>  
    > !["按文件夹分组" 选项][ImageGroupByFolder]  
    
    <span data-ttu-id="6eabf-167">按文件类型对资源进行组织。</span><span class="sxs-lookup"><span data-stu-id="6eabf-167">Resources are organized by file type.</span></span>  <span data-ttu-id="6eabf-168">在每个文件类型中，资源按字母顺序排列。</span><span class="sxs-lookup"><span data-stu-id="6eabf-168">Within each file type the resources are organized alphabetically.</span></span>  
    
    > ##### <span data-ttu-id="6eabf-169">图 9</span><span class="sxs-lookup"><span data-stu-id="6eabf-169">Figure 9</span></span>  
    > <span data-ttu-id="6eabf-170">禁用 "**按文件夹分组**" 后的**页面**窗格</span><span class="sxs-lookup"><span data-stu-id="6eabf-170">The **Page** pane after disabling **Group By Folder**</span></span>  
    > ![禁用 "按文件夹分组" 后的页面窗格][ImageFileNames]  
    
### <span data-ttu-id="6eabf-172">按文件类型浏览</span><span class="sxs-lookup"><span data-stu-id="6eabf-172">Browse by file type</span></span>   

<span data-ttu-id="6eabf-173">根据文件类型将资源组合在一起：</span><span class="sxs-lookup"><span data-stu-id="6eabf-173">To group resources together based on their file type:</span></span>  

1.  <span data-ttu-id="6eabf-174">单击 "**应用程序**" 选项卡。 将打开 "**应用程序**" 面板。</span><span class="sxs-lookup"><span data-stu-id="6eabf-174">Click the **Application** tab.  The **Application** panel opens.</span></span>  <span data-ttu-id="6eabf-175">默认情况下，**清单**窗格通常首先打开。</span><span class="sxs-lookup"><span data-stu-id="6eabf-175">By default the **Manifest** pane usually opens first.</span></span>  
    
    > ##### <span data-ttu-id="6eabf-176">图 10</span><span class="sxs-lookup"><span data-stu-id="6eabf-176">Figure 10</span></span>  
    > <span data-ttu-id="6eabf-177">**应用程序**面板</span><span class="sxs-lookup"><span data-stu-id="6eabf-177">The **Application** panel</span></span>  
    > ![应用程序面板][ImageApplication]  
    
1.  <span data-ttu-id="6eabf-179">向下滚动到 "**框架**" 窗格。</span><span class="sxs-lookup"><span data-stu-id="6eabf-179">Scroll down to the **Frames** pane.</span></span>  
    
    > ##### <span data-ttu-id="6eabf-180">图 11</span><span class="sxs-lookup"><span data-stu-id="6eabf-180">Figure 11</span></span>  
    > <span data-ttu-id="6eabf-181">"**框架**" 窗格</span><span class="sxs-lookup"><span data-stu-id="6eabf-181">The **Frames** pane</span></span>  
    > !["框架" 窗格][ImageFrames]  
    
1.  <span data-ttu-id="6eabf-183">展开感兴趣的分区。</span><span class="sxs-lookup"><span data-stu-id="6eabf-183">Expand the sections in which you are interested.</span></span>  
1.  <span data-ttu-id="6eabf-184">单击资源进行查看。</span><span class="sxs-lookup"><span data-stu-id="6eabf-184">Click a resource to view it.</span></span>  
    
    > ##### <span data-ttu-id="6eabf-185">图 12</span><span class="sxs-lookup"><span data-stu-id="6eabf-185">Figure 12</span></span>  
    > <span data-ttu-id="6eabf-186">在 "**应用程序**" 面板中查看资源</span><span class="sxs-lookup"><span data-stu-id="6eabf-186">Viewing a resource in the **Application** panel</span></span>  
    > ![在 "应用程序" 面板中查看资源][ImageApplicationView]  

#### <span data-ttu-id="6eabf-188">通过 "网络" 面板中的类型浏览文件</span><span class="sxs-lookup"><span data-stu-id="6eabf-188">Browse files by type in the Network panel</span></span>   

<span data-ttu-id="6eabf-189">请参阅[按资源类型筛选][DevtoolsNetworkFilterByResourceType]。</span><span class="sxs-lookup"><span data-stu-id="6eabf-189">See [Filter by resource type][DevtoolsNetworkFilterByResourceType].</span></span>  

> ##### <span data-ttu-id="6eabf-190">图 13</span><span class="sxs-lookup"><span data-stu-id="6eabf-190">Figure 13</span></span>  
> <span data-ttu-id="6eabf-191">在网络日志中筛选 CSS</span><span class="sxs-lookup"><span data-stu-id="6eabf-191">Filtering for CSS in the Network Log</span></span>  
> ![在网络日志中筛选 CSS][ImageCSS]  

<!--  -->  



<!-- image links -->  

[ImageOpenFile]: /microsoft-edge/devtools-guide-chromium/media/resources-command-menu-empty.msft.png "图1： "打开文件" 对话框"  
[ImageFileSearch]: /microsoft-edge/devtools-guide-chromium/media/resources-command-menu-file-search.msft.png "图2：在 "打开文件" 对话框中键入文件名"  
[ImageNetworkResponse]: /microsoft-edge/devtools-guide-chromium/media/resources-network-response.msft.png "图3：在 * * 网络 * * 面板中检查资源"  
[ImageRevealNetwork]: /microsoft-edge/devtools-guide-chromium/media/resources-sources-page-reveal-in-network-panel.msft.png "图4：在网络面板中显示"  
[ImageNetworkLog]: /microsoft-edge/devtools-guide-chromium/media/resources-network-resources.msft.png "图5：网络日志中的页面资源"  
[ImagePage]: /microsoft-edge/devtools-guide-chromium/media/resources-sources-page-empty.msft.png "图6：页面窗格"  
[ImageSourcesView]: /microsoft-edge/devtools-guide-chromium/media/resources-sources-page-resource.msft.png "图7：在编辑器中查看文件"  
[ImageGroupByFolder]: /microsoft-edge/devtools-guide-chromium/media/resources-sources-page-resource-group-by-folder.msft.png "图8： "按文件夹分组" 选项"  
[ImageFileNames]: /microsoft-edge/devtools-guide-chromium/media/resources-sources-page-resources-empty-not-grouped-by-folder.msft.png "图9：禁用 "按文件夹分组" 后的页面窗格"  
[ImageApplication]: /microsoft-edge/devtools-guide-chromium/media/resources-application-mainfest-airhorner.msft.png "图10：应用程序面板"  
[ImageFrames]: /microsoft-edge/devtools-guide-chromium/media/resources-application-mainfest-airhorner-frames-expanded.msft.png "图11： "框架" 窗格"  
[ImageApplicationView]: /microsoft-edge/devtools-guide-chromium/media/resources-application-mainfest-airhorner-expanded-resources.msft.png "图12：在 "应用程序" 面板中查看资源"  
[ImageCSS]: /microsoft-edge/devtools-guide-chromium/media/resources-network-resources-filter-css.msft.png "图13：在网络日志中筛选 CSS"  

<!-- links -->  

[MicrosoftEdgeDevTools]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge （Chromium）开发人员工具"  
[DevtoolsNetworkFilterByResourceType]: /microsoft-edge/devtools-guide-chromium/network/index#filter-by-resource-type "按资源类型筛选-在 Microsoft Edge DevTools 中检查网络活动"  
[DevtoolsNetworkInspectDetailsResource]: /microsoft-edge/devtools-guide-chromium/network/index#inspect-the-details-of-the-resource "检查 Microsoft Edge DevTools 中资源检查网络活动的详细信息"  
[DevtoolsNetworkLogActivity]: /microsoft-edge/devtools-guide-chromium/network/index#log-network-activity "日志网络活动-在 Microsoft Edge DevTools 中检查网络活动"  

[MDNInlineFrame]: https://developer.mozilla.org/docs/Web/HTML/Element/iframe "<iframe>：嵌入式框架元素 |MDN"  
[MDNLearnWebDevelopment]: https://developer.mozilla.org/docs/Learn "了解 web 开发 |MDN"  

> [!NOTE]
> <span data-ttu-id="6eabf-212">此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="6eabf-212">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="6eabf-213">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/resources/index)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools \ & Lighthouse \）创作。</span><span class="sxs-lookup"><span data-stu-id="6eabf-213">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/resources/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
<span data-ttu-id="6eabf-215">此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="6eabf-215">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
