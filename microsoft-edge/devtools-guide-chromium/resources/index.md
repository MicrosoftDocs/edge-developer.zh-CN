---
description: 按帧、域、类型或其他条件组织资源。
title: 通过 Microsoft Edge DevTools 查看页面资源
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 4f90927cc4044c722d9a62ab4b0427aa2753e4c5
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993588"
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





# <span data-ttu-id="2fee2-104">通过 Microsoft Edge DevTools 查看页面资源</span><span class="sxs-lookup"><span data-stu-id="2fee2-104">View page resources with Microsoft Edge DevTools</span></span>   

  

<span data-ttu-id="2fee2-105">本指南将教你如何使用 Microsoft Edge DevTools 查看网页的资源。</span><span class="sxs-lookup"><span data-stu-id="2fee2-105">This guide teaches you how to use Microsoft Edge DevTools to view the resources of a web page.</span></span>  <span data-ttu-id="2fee2-106">资源是页面需要正确显示的文件。</span><span class="sxs-lookup"><span data-stu-id="2fee2-106">Resources are the files that a page needs in order to display correctly.</span></span>  <span data-ttu-id="2fee2-107">资源示例包括 CSS、JavaScript 和 HTML 文件以及图像。</span><span class="sxs-lookup"><span data-stu-id="2fee2-107">Examples of resources include CSS, JavaScript, and HTML files, as well as images.</span></span>  

<span data-ttu-id="2fee2-108">本指南假定你熟悉 [web 开发][MDNLearnWebDevelopment] 和 [Microsoft Edge DevTools][MicrosoftEdgeDevTools]的基础知识。</span><span class="sxs-lookup"><span data-stu-id="2fee2-108">This guide assumes that you are familiar with the basics of [web development][MDNLearnWebDevelopment] and [Microsoft Edge DevTools][MicrosoftEdgeDevTools].</span></span>  

## <span data-ttu-id="2fee2-109">打开资源</span><span class="sxs-lookup"><span data-stu-id="2fee2-109">Open resources</span></span>   

<span data-ttu-id="2fee2-110">当您知道要检查的资源的名称时，" **命令" 菜单** 将提供打开资源的快速方法。</span><span class="sxs-lookup"><span data-stu-id="2fee2-110">When you know the name of the resource that you want to inspect, the **Command Menu** provides a fast way of opening the resource.</span></span>  

1.  <span data-ttu-id="2fee2-111">按 `Control` + `P` \ (Windows \ ) 或 `Command` + `P` \ (macOS \ ) 。</span><span class="sxs-lookup"><span data-stu-id="2fee2-111">Press `Control`+`P` \(Windows\) or `Command`+`P` \(macOS\).</span></span>  <span data-ttu-id="2fee2-112">" **打开文件** " 对话框随即打开。</span><span class="sxs-lookup"><span data-stu-id="2fee2-112">The **Open File** dialog opens.</span></span>  
    
    :::image type="complex" source="../media/resources-command-menu-empty.msft.png" alt-text=""打开文件" 对话框" lightbox="../media/resources-command-menu-empty.msft.png":::
       <span data-ttu-id="2fee2-114">" **打开文件** " 对话框</span><span class="sxs-lookup"><span data-stu-id="2fee2-114">The **Open File** dialog</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="2fee2-115">从下拉列表中选择文件，或者开始键入文件名，然后按 `Enter` 一次 "自动完成" 框中突出显示正确的文件。</span><span class="sxs-lookup"><span data-stu-id="2fee2-115">Select the file from the dropdown, or start typing the filename and press `Enter` once the correct file is highlighted in the autocomplete box.</span></span>  
    
    :::image type="complex" source="../media/resources-command-menu-file-search.msft.png" alt-text="在 "打开文件" 对话框中键入文件名" lightbox="../media/resources-command-menu-file-search.msft.png":::
       <span data-ttu-id="2fee2-117">在 " **打开文件** " 对话框中键入文件名</span><span class="sxs-lookup"><span data-stu-id="2fee2-117">Type a filename in the **Open File** dialog</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="2fee2-118">在 "网络" 面板中打开资源</span><span class="sxs-lookup"><span data-stu-id="2fee2-118">Open resources in the Network panel</span></span>   

<span data-ttu-id="2fee2-119">请参阅 [检查资源的详细信息][DevtoolsNetworkInspectDetailsResource]。</span><span class="sxs-lookup"><span data-stu-id="2fee2-119">See [Inspect the details of a resource][DevtoolsNetworkInspectDetailsResource].</span></span>  

:::image type="complex" source="../media/resources-network-response.msft.png" alt-text="在 "网络" 面板中检查资源" lightbox="../media/resources-network-response.msft.png":::
   <span data-ttu-id="2fee2-121">在 " **网络** " 面板中检查资源</span><span class="sxs-lookup"><span data-stu-id="2fee2-121">Inspect a resource in the **Network** panel</span></span>  
:::image-end:::  

### <span data-ttu-id="2fee2-122">从其他面板中的 "网络" 面板中显示资源</span><span class="sxs-lookup"><span data-stu-id="2fee2-122">Reveal resources in the Network panel from other panels</span></span>   

<span data-ttu-id="2fee2-123">下面的 [浏览资源](#browse-resources) 部分介绍了如何从 DevTools UI 的各个部分查看资源。</span><span class="sxs-lookup"><span data-stu-id="2fee2-123">The [Browse resources](#browse-resources) section below shows you how to view resources from various parts of the DevTools UI.</span></span>  <span data-ttu-id="2fee2-124">如果您想要在 " **网络** " 面板中检查资源，请右键单击该资源，然后 **在 "网络" 面板中选择 "显示**"。</span><span class="sxs-lookup"><span data-stu-id="2fee2-124">If you ever want to inspect a resource in the **Network** panel, right-click the resource and select **Reveal in Network panel**.</span></span>  

:::image type="complex" source="../media/resources-sources-page-reveal-in-network-panel.msft.png" alt-text="在网络面板中显示" lightbox="../media/resources-sources-page-reveal-in-network-panel.msft.png":::
   **<span data-ttu-id="2fee2-126">在网络面板中显示</span><span class="sxs-lookup"><span data-stu-id="2fee2-126">Reveal in Network panel</span></span>**  
:::image-end:::  

## <span data-ttu-id="2fee2-127">浏览资源</span><span class="sxs-lookup"><span data-stu-id="2fee2-127">Browse resources</span></span>   

### <span data-ttu-id="2fee2-128">浏览网络面板中的资源</span><span class="sxs-lookup"><span data-stu-id="2fee2-128">Browse resources in the Network panel</span></span>   

<span data-ttu-id="2fee2-129">请参阅 [记录网络活动][DevtoolsNetworkLogActivity]。</span><span class="sxs-lookup"><span data-stu-id="2fee2-129">See [Log network activity][DevtoolsNetworkLogActivity].</span></span>  

:::image type="complex" source="../media/resources-network-resources.msft.png" alt-text="网络日志中的页面资源" lightbox="../media/resources-network-resources.msft.png":::
   <span data-ttu-id="2fee2-131">**网络**日志中的页面资源</span><span class="sxs-lookup"><span data-stu-id="2fee2-131">Page resources in the **Network** Log</span></span>  
:::image-end:::  

### <span data-ttu-id="2fee2-132">按目录浏览</span><span class="sxs-lookup"><span data-stu-id="2fee2-132">Browse by directory</span></span>   

<span data-ttu-id="2fee2-133">若要查看按目录组织的页面资源，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="2fee2-133">To view the resources of a page organized by directory:</span></span>  

1.  <span data-ttu-id="2fee2-134">单击 " **源** " 选项卡以打开 " **源** " 面板。</span><span class="sxs-lookup"><span data-stu-id="2fee2-134">Click the **Sources** tab to open the **Sources** panel.</span></span>  
1.  <span data-ttu-id="2fee2-135">单击 " **页面** " 选项卡以显示页面的资源。</span><span class="sxs-lookup"><span data-stu-id="2fee2-135">Click the **Page** tab to show the resources of the page.</span></span>  <span data-ttu-id="2fee2-136">**页面**窗格随即打开。</span><span class="sxs-lookup"><span data-stu-id="2fee2-136">The **Page** pane opens.</span></span>  
    
    :::image type="complex" source="../media/resources-sources-page-empty.msft.png" alt-text="页面窗格" lightbox="../media/resources-sources-page-empty.msft.png":::
       <span data-ttu-id="2fee2-138">**页面**窗格</span><span class="sxs-lookup"><span data-stu-id="2fee2-138">The **Page** pane</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="2fee2-139">下面是上图中不明显的项目的细目。</span><span class="sxs-lookup"><span data-stu-id="2fee2-139">Here is a breakdown of the non-obvious items in the previous figure.</span></span>  
    
    | <span data-ttu-id="2fee2-140">页面项目</span><span class="sxs-lookup"><span data-stu-id="2fee2-140">Page item</span></span> | <span data-ttu-id="2fee2-141">描述</span><span class="sxs-lookup"><span data-stu-id="2fee2-141">Description</span></span> |  
    |:--- |:--- |  
    | `top` | <span data-ttu-id="2fee2-142">主文档 [浏览上下文][MDNInlineFrame]。</span><span class="sxs-lookup"><span data-stu-id="2fee2-142">The main document [browsing context][MDNInlineFrame].</span></span> |  
    | `airhorner.com` | <span data-ttu-id="2fee2-143">域。</span><span class="sxs-lookup"><span data-stu-id="2fee2-143">The domain.</span></span>  <span data-ttu-id="2fee2-144">嵌套在它下方的所有资源都来自该域。</span><span class="sxs-lookup"><span data-stu-id="2fee2-144">All resources nested under it come from that domain.</span></span>  <span data-ttu-id="2fee2-145">例如，文件的完整 URL `comlink.global.j` 可能 `https://airhorner.com/scripts/comlink.global.js` 。</span><span class="sxs-lookup"><span data-stu-id="2fee2-145">For example, the full URL of the `comlink.global.j` file is probably `https://airhorner.com/scripts/comlink.global.js`.</span></span> |  
    | `scripts` | <span data-ttu-id="2fee2-146">目录。</span><span class="sxs-lookup"><span data-stu-id="2fee2-146">A directory.</span></span> |  
    | `(index)` | <span data-ttu-id="2fee2-147">主 HTML 文档。</span><span class="sxs-lookup"><span data-stu-id="2fee2-147">The main HTML document.</span></span> |  
    | `sw.js` | <span data-ttu-id="2fee2-148">服务工作运行时上下文。</span><span class="sxs-lookup"><span data-stu-id="2fee2-148">A service worker runtime context.</span></span> |  
    
1.  <span data-ttu-id="2fee2-149">单击某个资源以在 **编辑器**中查看它。</span><span class="sxs-lookup"><span data-stu-id="2fee2-149">Click a resource to view it in the **Editor**.</span></span>  
    
    :::image type="complex" source="../media/resources-sources-page-resource.msft.png" alt-text="在编辑器中查看文件" lightbox="../media/resources-sources-page-resource.msft.png":::
       <span data-ttu-id="2fee2-151">在**编辑器**中查看文件</span><span class="sxs-lookup"><span data-stu-id="2fee2-151">View a file in the **Editor**</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="2fee2-152">按文件名浏览</span><span class="sxs-lookup"><span data-stu-id="2fee2-152">Browse by filename</span></span>   

<span data-ttu-id="2fee2-153">默认情况下， **页面** 窗格按目录对资源进行分组。</span><span class="sxs-lookup"><span data-stu-id="2fee2-153">By default the **Page** pane groups resources by directory.</span></span>  <span data-ttu-id="2fee2-154">若要禁用此分组并以简单列表的形式查看每个域的资源，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="2fee2-154">To disable this grouping and view the resources for each domain as a flat list:</span></span>  

1.  <span data-ttu-id="2fee2-155">打开 **页面** 窗格。</span><span class="sxs-lookup"><span data-stu-id="2fee2-155">Open the **Page** pane.</span></span>  <span data-ttu-id="2fee2-156">请参阅 [按目录浏览](#browse-by-directory)。</span><span class="sxs-lookup"><span data-stu-id="2fee2-156">See [Browse by directory](#browse-by-directory).</span></span>  
1.  <span data-ttu-id="2fee2-157">单击 " **更多选项**" `...` ，然后禁用 " **按文件夹分组**"。</span><span class="sxs-lookup"><span data-stu-id="2fee2-157">Click **More Options** `...` and disable **Group By Folder**.</span></span>  
    
    :::image type="complex" source="../media/resources-sources-page-resource-group-by-folder.msft.png" alt-text=""按文件夹分组" 选项" lightbox="../media/resources-sources-page-resource-group-by-folder.msft.png":::
       <span data-ttu-id="2fee2-159">" **按文件夹分组** " 选项</span><span class="sxs-lookup"><span data-stu-id="2fee2-159">The **Group By Folder** option</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="2fee2-160">按文件类型对资源进行组织。</span><span class="sxs-lookup"><span data-stu-id="2fee2-160">Resources are organized by file type.</span></span>  <span data-ttu-id="2fee2-161">在每个文件类型中，资源按字母顺序排列。</span><span class="sxs-lookup"><span data-stu-id="2fee2-161">Within each file type the resources are organized alphabetically.</span></span>  
    
    :::image type="complex" source="../media/resources-sources-page-resources-empty-not-grouped-by-folder.msft.png" alt-text="禁用 "按文件夹分组" 后的页面窗格" lightbox="../media/resources-sources-page-resources-empty-not-grouped-by-folder.msft.png":::
       <span data-ttu-id="2fee2-163">禁用 "**按文件夹分组**" 后的**页面**窗格</span><span class="sxs-lookup"><span data-stu-id="2fee2-163">The **Page** pane after disabling **Group By Folder**</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="2fee2-164">按文件类型浏览</span><span class="sxs-lookup"><span data-stu-id="2fee2-164">Browse by file type</span></span>   

<span data-ttu-id="2fee2-165">根据文件类型将资源组合在一起：</span><span class="sxs-lookup"><span data-stu-id="2fee2-165">To group resources together based on their file type:</span></span>  

1.  <span data-ttu-id="2fee2-166">单击 " **应用程序** " 选项卡。 将打开 " **应用程序** " 面板。</span><span class="sxs-lookup"><span data-stu-id="2fee2-166">Click the **Application** tab.  The **Application** panel opens.</span></span>  <span data-ttu-id="2fee2-167">默认情况下， **清单** 窗格通常首先打开。</span><span class="sxs-lookup"><span data-stu-id="2fee2-167">By default the **Manifest** pane usually opens first.</span></span>  
    
    :::image type="complex" source="../media/resources-application-mainfest-airhorner.msft.png" alt-text="应用程序面板" lightbox="../media/resources-application-mainfest-airhorner.msft.png":::
       <span data-ttu-id="2fee2-169">**应用程序**面板</span><span class="sxs-lookup"><span data-stu-id="2fee2-169">The **Application** panel</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="2fee2-170">向下滚动到 " **框架** " 窗格。</span><span class="sxs-lookup"><span data-stu-id="2fee2-170">Scroll down to the **Frames** pane.</span></span>  
    
    :::image type="complex" source="../media/resources-application-mainfest-airhorner-frames-expanded.msft.png" alt-text=""框架" 窗格" lightbox="../media/resources-application-mainfest-airhorner-frames-expanded.msft.png":::
       <span data-ttu-id="2fee2-172">" **框架** " 窗格</span><span class="sxs-lookup"><span data-stu-id="2fee2-172">The **Frames** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="2fee2-173">展开感兴趣的分区。</span><span class="sxs-lookup"><span data-stu-id="2fee2-173">Expand the sections in which you are interested.</span></span>  
1.  <span data-ttu-id="2fee2-174">单击资源进行查看。</span><span class="sxs-lookup"><span data-stu-id="2fee2-174">Click a resource to view it.</span></span>  
    
    :::image type="complex" source="../media/resources-application-mainfest-airhorner-expanded-resources.msft.png" alt-text="在 "应用程序" 面板中查看资源" lightbox="../media/resources-application-mainfest-airhorner-expanded-resources.msft.png":::
       <span data-ttu-id="2fee2-176">在 " **应用程序** " 面板中查看资源</span><span class="sxs-lookup"><span data-stu-id="2fee2-176">View a resource in the **Application** panel</span></span>  
    :::image-end:::  
    
#### <span data-ttu-id="2fee2-177">通过 "网络" 面板中的类型浏览文件</span><span class="sxs-lookup"><span data-stu-id="2fee2-177">Browse files by type in the Network panel</span></span>   

<span data-ttu-id="2fee2-178">请参阅 [按资源类型筛选][DevtoolsNetworkFilterByResourceType]。</span><span class="sxs-lookup"><span data-stu-id="2fee2-178">See [Filter by resource type][DevtoolsNetworkFilterByResourceType].</span></span>  

:::image type="complex" source="../media/resources-network-resources-filter-css.msft.png" alt-text="在网络日志中筛选 CSS" lightbox="../media/resources-network-resources-filter-css.msft.png":::
   <span data-ttu-id="2fee2-180">在 **网络** 日志中筛选 CSS</span><span class="sxs-lookup"><span data-stu-id="2fee2-180">Filter for CSS in the **Network** Log</span></span>  
:::image-end:::  

<!--  
  


-->  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) 开发工具 |Microsoft 文档"  
[DevtoolsNetworkFilterByResourceType]: ../network/index.md#filter-by-resource-type "按资源类型筛选-检查 Microsoft Edge DevTools 中的网络活动 |Microsoft 文档"  
[DevtoolsNetworkInspectDetailsResource]: ../network/index.md#inspect-the-details-of-the-resource "检查 Microsoft Edge DevTools | 中的资源检查网络活动的详细信息 |Microsoft 文档"  
[DevtoolsNetworkLogActivity]: ../network/index.md#log-network-activity "记录网络活动-在 Microsoft Edge DevTools 中检查网络活动 |Microsoft 文档"  

[MDNInlineFrame]: https://developer.mozilla.org/docs/Web/HTML/Element/iframe "<iframe>：嵌入式框架元素 |MDN"  
[MDNLearnWebDevelopment]: https://developer.mozilla.org/docs/Learn "了解 web 开发 |MDN"  

> [!NOTE]
> <span data-ttu-id="2fee2-187">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="2fee2-187">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="2fee2-188">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/resources/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="2fee2-188">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/resources/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="2fee2-190">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="2fee2-190">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
