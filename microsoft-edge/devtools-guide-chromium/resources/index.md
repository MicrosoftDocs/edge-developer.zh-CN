---
description: 按框架、域、类型或其他条件组织资源。
title: 使用 Microsoft Edge DevTools 查看页面资源
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: 75063b23f23c25ff4fe2e7f6e044a2de9a7b1ccd
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398222"
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

# <a name="view-page-resources-with-microsoft-edge-devtools"></a><span data-ttu-id="03ddd-104">使用 Microsoft Edge DevTools 查看页面资源</span><span class="sxs-lookup"><span data-stu-id="03ddd-104">View page resources with Microsoft Edge DevTools</span></span>  

<span data-ttu-id="03ddd-105">本指南指导你如何使用 Microsoft Edge DevTools 查看网页的资源。</span><span class="sxs-lookup"><span data-stu-id="03ddd-105">This guide teaches you how to use Microsoft Edge DevTools to view the resources of a web page.</span></span>  <span data-ttu-id="03ddd-106">资源是页面正确显示所需的文件。</span><span class="sxs-lookup"><span data-stu-id="03ddd-106">Resources are the files that a page needs in order to display correctly.</span></span>  <span data-ttu-id="03ddd-107">资源示例包括 CSS、JavaScript 和 HTML 文件以及图像。</span><span class="sxs-lookup"><span data-stu-id="03ddd-107">Examples of resources include CSS, JavaScript, and HTML files, as well as images.</span></span>  

<span data-ttu-id="03ddd-108">本指南假定你熟悉 Web 开发和 Microsoft Edge [][MDNLearnWebDevelopment] [DevTools 的基础知识][MicrosoftEdgeDevTools]。</span><span class="sxs-lookup"><span data-stu-id="03ddd-108">This guide assumes that you are familiar with the basics of [web development][MDNLearnWebDevelopment] and [Microsoft Edge DevTools][MicrosoftEdgeDevTools].</span></span>  

## <a name="open-resources"></a><span data-ttu-id="03ddd-109">打开资源</span><span class="sxs-lookup"><span data-stu-id="03ddd-109">Open resources</span></span>  

<span data-ttu-id="03ddd-110">当您知道要检查的资源的名称时，命令菜单提供了一种快速打开\*\*\*\* 资源的方法。</span><span class="sxs-lookup"><span data-stu-id="03ddd-110">When you know the name of the resource that you want to inspect, the **Command Menu** provides a fast way of opening the resource.</span></span>  

1.  <span data-ttu-id="03ddd-111">选择 `Control` + `P` \ (Windows、Linux\) `Command` + `P` 或 \ (macOS\) 。</span><span class="sxs-lookup"><span data-stu-id="03ddd-111">Select `Control`+`P` \(Windows, Linux\) or `Command`+`P` \(macOS\).</span></span>  <span data-ttu-id="03ddd-112">将 **打开"打开文件** "对话框。</span><span class="sxs-lookup"><span data-stu-id="03ddd-112">The **Open File** dialog opens.</span></span>  
    
    :::image type="complex" source="../media/resources-command-menu-empty.msft.png" alt-text="打开文件对话框" lightbox="../media/resources-command-menu-empty.msft.png":::
       <span data-ttu-id="03ddd-114">" **打开文件"** 对话框</span><span class="sxs-lookup"><span data-stu-id="03ddd-114">The **Open File** dialog</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="03ddd-115">从下拉列表中选择文件，或开始键入文件名，在自动完成框中突出显示正确的文件后 `Enter` 选择。</span><span class="sxs-lookup"><span data-stu-id="03ddd-115">Choose the file from the dropdown, or start typing the filename and select `Enter` once the correct file is highlighted in the autocomplete box.</span></span>  
    
    :::image type="complex" source="../media/resources-command-menu-file-search.msft.png" alt-text="在打开文件对话框中键入文件名" lightbox="../media/resources-command-menu-file-search.msft.png":::
       <span data-ttu-id="03ddd-117">在"打开文件"对话框中 **键入** 文件名</span><span class="sxs-lookup"><span data-stu-id="03ddd-117">Type a filename in the **Open File** dialog</span></span>  
    :::image-end:::  
    
### <a name="open-resources-in-the-network-tool"></a><span data-ttu-id="03ddd-118">在"网络"工具中打开资源</span><span class="sxs-lookup"><span data-stu-id="03ddd-118">Open resources in the Network tool</span></span>  

<span data-ttu-id="03ddd-119">导航[到"检查资源的详细信息"。][DevtoolsNetworkInspectDetailsResource]</span><span class="sxs-lookup"><span data-stu-id="03ddd-119">Navigate to [Inspect the details of a resource][DevtoolsNetworkInspectDetailsResource].</span></span>  

:::image type="complex" source="../media/resources-network-response.msft.png" alt-text="检查网络工具中的资源" lightbox="../media/resources-network-response.msft.png":::
   <span data-ttu-id="03ddd-121">检查网络工具 **中的** 资源</span><span class="sxs-lookup"><span data-stu-id="03ddd-121">Inspect a resource in the **Network** tool</span></span>  
:::image-end:::  

### <a name="reveal-resources-in-the-network-tool-from-other-panels"></a><span data-ttu-id="03ddd-122">显示来自其他面板的网络工具中的资源</span><span class="sxs-lookup"><span data-stu-id="03ddd-122">Reveal resources in the Network tool from other panels</span></span>  

<span data-ttu-id="03ddd-123">下面的 ["](#browse-resources) 浏览资源"部分显示如何查看来自 DevTools UI 的各个部分的资源。</span><span class="sxs-lookup"><span data-stu-id="03ddd-123">The [Browse resources](#browse-resources) section below shows you how to view resources from various parts of the DevTools UI.</span></span>  <span data-ttu-id="03ddd-124">如果你曾经想要检查**网络**工具中的资源，请将鼠标悬停在资源上，打开上下文菜单 \ (右键单击\) ，然后选择"网络"面板中的"展示 **"。**</span><span class="sxs-lookup"><span data-stu-id="03ddd-124">If you ever want to inspect a resource in the **Network** tool,  hover on the resource, open the contextual menu \(right-click\), and choose **Reveal in Network panel**.</span></span>  

:::image type="complex" source="../media/resources-sources-page-reveal-in-network-panel.msft.png" alt-text="在网络面板中显示" lightbox="../media/resources-sources-page-reveal-in-network-panel.msft.png":::
   **<span data-ttu-id="03ddd-126">"在网络"面板中显示</span><span class="sxs-lookup"><span data-stu-id="03ddd-126">Reveal in Network panel</span></span>**  
:::image-end:::  

## <a name="browse-resources"></a><span data-ttu-id="03ddd-127">浏览资源</span><span class="sxs-lookup"><span data-stu-id="03ddd-127">Browse resources</span></span>  

### <a name="browse-resources-in-the-network-panel"></a><span data-ttu-id="03ddd-128">在"网络"面板中浏览资源</span><span class="sxs-lookup"><span data-stu-id="03ddd-128">Browse resources in the Network panel</span></span>  

<span data-ttu-id="03ddd-129">导航到["记录网络活动"。][DevtoolsNetworkLogActivity]</span><span class="sxs-lookup"><span data-stu-id="03ddd-129">Navigate to [Log network activity][DevtoolsNetworkLogActivity].</span></span>  

:::image type="complex" source="../media/resources-network-resources.msft.png" alt-text="网络日志中的页面资源" lightbox="../media/resources-network-resources.msft.png":::
   <span data-ttu-id="03ddd-131">网络日志中 **的页面** 资源</span><span class="sxs-lookup"><span data-stu-id="03ddd-131">Page resources in the **Network** Log</span></span>  
:::image-end:::  

### <a name="browse-by-directory"></a><span data-ttu-id="03ddd-132">按目录浏览</span><span class="sxs-lookup"><span data-stu-id="03ddd-132">Browse by directory</span></span>  

<span data-ttu-id="03ddd-133">若要查看按目录组织的页面的资源，</span><span class="sxs-lookup"><span data-stu-id="03ddd-133">To view the resources of a page organized by directory:</span></span>  

1.  <span data-ttu-id="03ddd-134">选择 **"源** "工具打开"源 **"** 面板。</span><span class="sxs-lookup"><span data-stu-id="03ddd-134">Choose the **Sources** tool to open the **Sources** panel.</span></span>  
1.  <span data-ttu-id="03ddd-135">选择 **"页面** "面板以显示页面的资源。</span><span class="sxs-lookup"><span data-stu-id="03ddd-135">Choose the **Page** panel to show the resources of the page.</span></span>  <span data-ttu-id="03ddd-136">将 **打开"页面** "窗格。</span><span class="sxs-lookup"><span data-stu-id="03ddd-136">The **Page** pane opens.</span></span>  
    
    :::image type="complex" source="../media/resources-sources-page-empty.msft.png" alt-text="页面窗格" lightbox="../media/resources-sources-page-empty.msft.png":::
       <span data-ttu-id="03ddd-138">" **页面"** 面板</span><span class="sxs-lookup"><span data-stu-id="03ddd-138">The **Page** panel</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="03ddd-139">下面对上图中的不明显项进行细分。</span><span class="sxs-lookup"><span data-stu-id="03ddd-139">Here is a breakdown of the non-obvious items in the previous figure.</span></span>  
    
    | <span data-ttu-id="03ddd-140">页面项</span><span class="sxs-lookup"><span data-stu-id="03ddd-140">Page item</span></span> | <span data-ttu-id="03ddd-141">说明</span><span class="sxs-lookup"><span data-stu-id="03ddd-141">Description</span></span> |  
    |:--- |:--- |  
    | `top` | <span data-ttu-id="03ddd-142">主文档 [浏览上下文][MDNInlineFrame]。</span><span class="sxs-lookup"><span data-stu-id="03ddd-142">The main document [browsing context][MDNInlineFrame].</span></span> |  
    | `airhorner.com` | <span data-ttu-id="03ddd-143">域。</span><span class="sxs-lookup"><span data-stu-id="03ddd-143">The domain.</span></span>  <span data-ttu-id="03ddd-144">嵌套在它下的所有资源都来自该域。</span><span class="sxs-lookup"><span data-stu-id="03ddd-144">All resources nested under it come from that domain.</span></span>  <span data-ttu-id="03ddd-145">例如，文件的完整 URL `comlink.global.j` 可能是 `https://airhorner.com/scripts/comlink.global.js` 。</span><span class="sxs-lookup"><span data-stu-id="03ddd-145">For example, the full URL of the `comlink.global.j` file is probably `https://airhorner.com/scripts/comlink.global.js`.</span></span> |  
    | `scripts` | <span data-ttu-id="03ddd-146">目录。</span><span class="sxs-lookup"><span data-stu-id="03ddd-146">A directory.</span></span> |  
    | `(index)` | <span data-ttu-id="03ddd-147">主 HTML 文档。</span><span class="sxs-lookup"><span data-stu-id="03ddd-147">The main HTML document.</span></span> |  
    | `sw.js` | <span data-ttu-id="03ddd-148">服务工作线程运行时上下文。</span><span class="sxs-lookup"><span data-stu-id="03ddd-148">A service worker runtime context.</span></span> |  
    
1.  <span data-ttu-id="03ddd-149">选择一个资源，在编辑器中查看 **它**。</span><span class="sxs-lookup"><span data-stu-id="03ddd-149">Choose a resource to view it in the **Editor**.</span></span>  
    
    :::image type="complex" source="../media/resources-sources-page-resource.msft.png" alt-text="在编辑器中查看文件" lightbox="../media/resources-sources-page-resource.msft.png":::
       <span data-ttu-id="03ddd-151">在编辑器中查看 **文件**</span><span class="sxs-lookup"><span data-stu-id="03ddd-151">View a file in the **Editor**</span></span>  
    :::image-end:::  
    
### <a name="browse-by-filename"></a><span data-ttu-id="03ddd-152">按文件名浏览</span><span class="sxs-lookup"><span data-stu-id="03ddd-152">Browse by filename</span></span>  

<span data-ttu-id="03ddd-153">默认情况下， **页面面板** 按目录对资源进行分组。</span><span class="sxs-lookup"><span data-stu-id="03ddd-153">By default the **Page** panel groups resources by directory.</span></span>  <span data-ttu-id="03ddd-154">若要禁用此分组并查看每个域的资源，请简单列表：</span><span class="sxs-lookup"><span data-stu-id="03ddd-154">To disable this grouping and view the resources for each domain as a flat list:</span></span>  

1.  <span data-ttu-id="03ddd-155">打开 **"页面"** 面板。</span><span class="sxs-lookup"><span data-stu-id="03ddd-155">Open the **Page** panel.</span></span>  <span data-ttu-id="03ddd-156">导航到["按目录浏览"。](#browse-by-directory)</span><span class="sxs-lookup"><span data-stu-id="03ddd-156">Navigate to [Browse by directory](#browse-by-directory).</span></span>  
1.  <span data-ttu-id="03ddd-157">选择 **"更多选项** `...` "并禁用 **"按文件夹分组"。**</span><span class="sxs-lookup"><span data-stu-id="03ddd-157">Choose **More Options** `...` and disable **Group By Folder**.</span></span>  
    
    :::image type="complex" source="../media/resources-sources-page-resource-group-by-folder.msft.png" alt-text="按文件夹分组选项" lightbox="../media/resources-sources-page-resource-group-by-folder.msft.png":::
       <span data-ttu-id="03ddd-159">" **按文件夹分组"** 选项</span><span class="sxs-lookup"><span data-stu-id="03ddd-159">The **Group By Folder** option</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="03ddd-160">资源按文件类型组织。</span><span class="sxs-lookup"><span data-stu-id="03ddd-160">Resources are organized by file type.</span></span>  <span data-ttu-id="03ddd-161">在每个文件类型中，资源按字母顺序组织。</span><span class="sxs-lookup"><span data-stu-id="03ddd-161">Within each file type the resources are organized alphabetically.</span></span>  
    
    :::image type="complex" source="../media/resources-sources-page-resources-empty-not-grouped-by-folder.msft.png" alt-text="禁用按文件夹分组后的页面面板" lightbox="../media/resources-sources-page-resources-empty-not-grouped-by-folder.msft.png":::
       <span data-ttu-id="03ddd-163">禁用 **"** 按文件夹分组" **后的页面面板**</span><span class="sxs-lookup"><span data-stu-id="03ddd-163">The **Page** panel after disabling **Group By Folder**</span></span>  
    :::image-end:::  
    
### <a name="browse-by-file-type"></a><span data-ttu-id="03ddd-164">按文件类型浏览</span><span class="sxs-lookup"><span data-stu-id="03ddd-164">Browse by file type</span></span>  

<span data-ttu-id="03ddd-165">若要根据资源的文件类型将资源分组在一起：</span><span class="sxs-lookup"><span data-stu-id="03ddd-165">To group resources together based on their file type:</span></span>  

1.  <span data-ttu-id="03ddd-166">选择 **"应用程序"** 选项卡。 应用程序 **工具** 将打开。</span><span class="sxs-lookup"><span data-stu-id="03ddd-166">Choose the **Application** tab.  The **Application** tool opens.</span></span>  <span data-ttu-id="03ddd-167">默认情况下， **清单窗格** 通常先打开。</span><span class="sxs-lookup"><span data-stu-id="03ddd-167">By default the **Manifest** pane usually opens first.</span></span>  
    
    :::image type="complex" source="../media/resources-application-mainfest-airhorner.msft.png" alt-text="应用程序工具" lightbox="../media/resources-application-mainfest-airhorner.msft.png":::
       <span data-ttu-id="03ddd-169">应用程序**工具**</span><span class="sxs-lookup"><span data-stu-id="03ddd-169">The **Application** tool</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="03ddd-170">向下滚动到" **框架"** 窗格。</span><span class="sxs-lookup"><span data-stu-id="03ddd-170">Scroll down to the **Frames** pane.</span></span>  
    
    :::image type="complex" source="../media/resources-application-mainfest-airhorner-frames-expanded.msft.png" alt-text="框架窗格" lightbox="../media/resources-application-mainfest-airhorner-frames-expanded.msft.png":::
       <span data-ttu-id="03ddd-172">框架**窗格**</span><span class="sxs-lookup"><span data-stu-id="03ddd-172">The **Frames** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="03ddd-173">展开感兴趣的部分。</span><span class="sxs-lookup"><span data-stu-id="03ddd-173">Expand the sections in which you are interested.</span></span>  
1.  <span data-ttu-id="03ddd-174">选择一个资源进行查看。</span><span class="sxs-lookup"><span data-stu-id="03ddd-174">Choose a resource to view it.</span></span>  
    
    :::image type="complex" source="../media/resources-application-mainfest-airhorner-expanded-resources.msft.png" alt-text="在"应用程序"面板中查看资源" lightbox="../media/resources-application-mainfest-airhorner-expanded-resources.msft.png":::
       <span data-ttu-id="03ddd-176">在"应用程序"面板 **中查看** 资源</span><span class="sxs-lookup"><span data-stu-id="03ddd-176">View a resource in the **Application** panel</span></span>  
    :::image-end:::  
    
#### <a name="browse-files-by-type-in-the-network-panel"></a><span data-ttu-id="03ddd-177">在"网络"面板中按类型浏览文件</span><span class="sxs-lookup"><span data-stu-id="03ddd-177">Browse files by type in the Network panel</span></span>  

<span data-ttu-id="03ddd-178">按资源[类型导航到"筛选"。][DevtoolsNetworkFilterByResourceType]</span><span class="sxs-lookup"><span data-stu-id="03ddd-178">Navigate to [Filter by resource type][DevtoolsNetworkFilterByResourceType].</span></span>  

:::image type="complex" source="../media/resources-network-resources-filter-css.msft.png" alt-text="在网络日志中筛选 CSS" lightbox="../media/resources-network-resources-filter-css.msft.png":::
   <span data-ttu-id="03ddd-180">在网络日志中 **筛选** CSS</span><span class="sxs-lookup"><span data-stu-id="03ddd-180">Filter for CSS in the **Network** Log</span></span>  
:::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="03ddd-181">联系 Microsoft Edge 开发工具团队</span><span class="sxs-lookup"><span data-stu-id="03ddd-181">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 开发人员工具|Microsoft Docs"  
[DevtoolsNetworkFilterByResourceType]: ../network/index.md#filter-by-resource-type "按资源类型筛选 - 检查 Microsoft Edge DevTools |Microsoft Docs"  
[DevtoolsNetworkInspectDetailsResource]: ../network/index.md#inspect-the-details-of-the-resource "检查资源的详细信息 - 检查 Microsoft Edge DevTools |Microsoft Docs"  
[DevtoolsNetworkLogActivity]: ../network/index.md#log-network-activity "记录网络活动 - 检查 Microsoft Edge DevTools |Microsoft Docs"  

[MDNInlineFrame]: https://developer.mozilla.org/docs/Web/HTML/Element/iframe "<iframe>：Inline Frame 元素|MDN"  
[MDNLearnWebDevelopment]: https://developer.mozilla.org/docs/Learn "了解 Web |MDN"  

> [!NOTE]
> <span data-ttu-id="03ddd-188">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="03ddd-188">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="03ddd-189">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/resources/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="03ddd-189">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/resources/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="03ddd-191">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="03ddd-191">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
