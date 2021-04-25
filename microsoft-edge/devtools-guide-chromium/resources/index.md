---
description: 按帧、域、类型或其他条件组织资源。
title: 使用 Microsoft Edge DevTools 查看页面资源
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 818b93c1c07a93baa8972a530871d20446fd687f
ms.sourcegitcommit: 16e2f7232196a57a70b979bbf8b663774b7ddc20
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/25/2021
ms.locfileid: "11519441"
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

# <a name="view-page-resources-with-microsoft-edge-devtools"></a><span data-ttu-id="67451-104">使用 Microsoft Edge DevTools 查看页面资源</span><span class="sxs-lookup"><span data-stu-id="67451-104">View page resources with Microsoft Edge DevTools</span></span>  

<span data-ttu-id="67451-105">本指南指导你如何使用 Microsoft Edge DevTools 查看网页的资源。</span><span class="sxs-lookup"><span data-stu-id="67451-105">This guide teaches you how to use Microsoft Edge DevTools to view the resources of a web page.</span></span>  <span data-ttu-id="67451-106">资源是页面为了正确显示而需要的文件。</span><span class="sxs-lookup"><span data-stu-id="67451-106">Resources are the files that a page needs in order to display correctly.</span></span>  <span data-ttu-id="67451-107">资源示例包括 CSS、JavaScript 和 HTML 文件以及图像。</span><span class="sxs-lookup"><span data-stu-id="67451-107">Examples of resources include CSS, JavaScript, and HTML files, as well as images.</span></span>  

<span data-ttu-id="67451-108">本指南假定你熟悉 Web 开发和 Microsoft Edge [][MDNLearnWebDevelopment] [DevTools][MicrosoftEdgeDevTools]的基础知识。</span><span class="sxs-lookup"><span data-stu-id="67451-108">This guide assumes that you are familiar with the basics of [web development][MDNLearnWebDevelopment] and [Microsoft Edge DevTools][MicrosoftEdgeDevTools].</span></span>  

## <a name="open-resources"></a><span data-ttu-id="67451-109">打开资源</span><span class="sxs-lookup"><span data-stu-id="67451-109">Open resources</span></span>  

<span data-ttu-id="67451-110">当您知道要检查的资源的名称时，"命令菜单"提供了一种\*\*\*\* 快速打开资源的方法。</span><span class="sxs-lookup"><span data-stu-id="67451-110">When you know the name of the resource that you want to inspect, the **Command Menu** provides a fast way of opening the resource.</span></span>  

1.  <span data-ttu-id="67451-111">选择 `Control`+`P`（Windows、Linux）或 `Command`+`P` (macOS)。</span><span class="sxs-lookup"><span data-stu-id="67451-111">Select `Control`+`P` \(Windows, Linux\) or `Command`+`P` \(macOS\).</span></span>  <span data-ttu-id="67451-112">将 **打开"打开文件** "对话框。</span><span class="sxs-lookup"><span data-stu-id="67451-112">The **Open File** dialog opens.</span></span>  
    
    :::image type="complex" source="../media/resources-command-menu-empty.msft.png" alt-text=""打开文件"对话框" lightbox="../media/resources-command-menu-empty.msft.png":::
       <span data-ttu-id="67451-114">" **打开文件"** 对话框</span><span class="sxs-lookup"><span data-stu-id="67451-114">The **Open File** dialog</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="67451-115">从下拉列表中选择文件，或开始键入文件名，在自动完成框中突出显示正确的文件后 `Enter` 选择。</span><span class="sxs-lookup"><span data-stu-id="67451-115">Choose the file from the dropdown, or start typing the filename and select `Enter` once the correct file is highlighted in the autocomplete box.</span></span>  
    
    :::image type="complex" source="../media/resources-command-menu-file-search.msft.png" alt-text="在"打开文件"对话框中键入文件名" lightbox="../media/resources-command-menu-file-search.msft.png":::
       <span data-ttu-id="67451-117">在"打开文件" **对话框中键入** 文件名</span><span class="sxs-lookup"><span data-stu-id="67451-117">Type a filename in the **Open File** dialog</span></span>  
    :::image-end:::  
    
### <a name="open-resources-in-the-network-tool"></a><span data-ttu-id="67451-118">在"网络"工具中打开资源</span><span class="sxs-lookup"><span data-stu-id="67451-118">Open resources in the Network tool</span></span>  

<span data-ttu-id="67451-119">导航 [到检查资源的详细信息][DevtoolsNetworkInspectDetailsResource]。</span><span class="sxs-lookup"><span data-stu-id="67451-119">Navigate to [Inspect the details of a resource][DevtoolsNetworkInspectDetailsResource].</span></span>  

:::image type="complex" source="../media/resources-network-response.msft.png" alt-text="检查网络工具中的资源" lightbox="../media/resources-network-response.msft.png":::
   <span data-ttu-id="67451-121">检查网络工具 **中的** 资源</span><span class="sxs-lookup"><span data-stu-id="67451-121">Inspect a resource in the **Network** tool</span></span>  
:::image-end:::  

### <a name="reveal-resources-in-the-network-tool-from-other-panels"></a><span data-ttu-id="67451-122">显示来自其他面板的网络工具中的资源</span><span class="sxs-lookup"><span data-stu-id="67451-122">Reveal resources in the Network tool from other panels</span></span>  

<span data-ttu-id="67451-123">下面的 ["](#browse-resources) 浏览资源"部分显示如何查看来自 DevTools UI 各个部分的资源。</span><span class="sxs-lookup"><span data-stu-id="67451-123">The [Browse resources](#browse-resources) section below shows you how to view resources from various parts of the DevTools UI.</span></span>  <span data-ttu-id="67451-124">如果你曾经想要在网络工具中检查资源，\*\*\*\* 请将鼠标悬停在资源上，打开上下文菜单 \ (右键单击\) ，然后选择"网络"面板中的"**展示"。**</span><span class="sxs-lookup"><span data-stu-id="67451-124">If you ever want to inspect a resource in the **Network** tool,  hover on the resource, open the contextual menu \(right-click\), and choose **Reveal in Network panel**.</span></span>  

:::image type="complex" source="../media/resources-sources-page-reveal-in-network-panel.msft.png" alt-text=""网络"面板中的"展示"" lightbox="../media/resources-sources-page-reveal-in-network-panel.msft.png":::
   **<span data-ttu-id="67451-126">"网络"面板中的"展示"</span><span class="sxs-lookup"><span data-stu-id="67451-126">Reveal in Network panel</span></span>**  
:::image-end:::  

## <a name="browse-resources"></a><span data-ttu-id="67451-127">浏览资源</span><span class="sxs-lookup"><span data-stu-id="67451-127">Browse resources</span></span>  

### <a name="browse-resources-in-the-network-panel"></a><span data-ttu-id="67451-128">浏览"网络"面板中的资源</span><span class="sxs-lookup"><span data-stu-id="67451-128">Browse resources in the Network panel</span></span>  

<span data-ttu-id="67451-129">导航到 [记录网络][DevtoolsNetworkLogActivity]。</span><span class="sxs-lookup"><span data-stu-id="67451-129">Navigate to [Log network activity][DevtoolsNetworkLogActivity].</span></span>  

:::image type="complex" source="../media/resources-network-resources.msft.png" alt-text="网络日志中的页面资源" lightbox="../media/resources-network-resources.msft.png":::
   <span data-ttu-id="67451-131">网络日志中 **的页面** 资源</span><span class="sxs-lookup"><span data-stu-id="67451-131">Page resources in the **Network** Log</span></span>  
:::image-end:::  

### <a name="browse-by-directory"></a><span data-ttu-id="67451-132">按目录浏览</span><span class="sxs-lookup"><span data-stu-id="67451-132">Browse by directory</span></span>  

<span data-ttu-id="67451-133">查看按目录组织的网页的资源：</span><span class="sxs-lookup"><span data-stu-id="67451-133">To view the resources of a webpage organized by directory:</span></span>  

1.  <span data-ttu-id="67451-134">打开 DevTools。</span><span class="sxs-lookup"><span data-stu-id="67451-134">Open DevTools.</span></span>
1.  <span data-ttu-id="67451-135">选择 **"源**"工具，然后在左上角的\*\*\*\*"导航器"窗格中，选择"**页面"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="67451-135">Choose the **Sources** tool, and then in the **Navigator** pane in the upper left, choose the **Page** tab.</span></span>
1.  <span data-ttu-id="67451-136">Choose the **More options** (...) button to the right of the **Page** tab， and then choose Group **by folder**.</span><span class="sxs-lookup"><span data-stu-id="67451-136">Choose the **More options** (...) button to the right of the **Page** tab, and then choose **Group by folder**.</span></span>
    
    :::image type="complex" source="../media/resources-sources-page-empty.msft.png" alt-text=""源"工具的"导航器"窗格中的"页面"选项卡" lightbox="../media/resources-sources-page-empty.msft.png":::
       <span data-ttu-id="67451-138">" **源** "工具的"导航 **器"** 窗格中的" **页面"** 选项卡</span><span class="sxs-lookup"><span data-stu-id="67451-138">The **Page** tab in the **Navigator** pane of the **Sources** tool</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="67451-139">下面细目了上图中的不明显项。</span><span class="sxs-lookup"><span data-stu-id="67451-139">Here is a breakdown of the non-obvious items in the previous figure.</span></span>  
    
    | <span data-ttu-id="67451-140">页面项</span><span class="sxs-lookup"><span data-stu-id="67451-140">Page item</span></span> | <span data-ttu-id="67451-141">描述</span><span class="sxs-lookup"><span data-stu-id="67451-141">Description</span></span> |  
    |:--- |:--- |  
    | `top` | <span data-ttu-id="67451-142">主文档 [浏览上下文][MDNInlineFrame]。</span><span class="sxs-lookup"><span data-stu-id="67451-142">The main document [browsing context][MDNInlineFrame].</span></span> |  
    | `airhorner.com` | <span data-ttu-id="67451-143">域。</span><span class="sxs-lookup"><span data-stu-id="67451-143">The domain.</span></span>  <span data-ttu-id="67451-144">嵌套在它下的所有资源都来自该域。</span><span class="sxs-lookup"><span data-stu-id="67451-144">All resources nested under it come from that domain.</span></span>  <span data-ttu-id="67451-145">例如，文件的完整 URL `comlink.global.j` 可能是 `https://airhorner.com/scripts/comlink.global.js` 。</span><span class="sxs-lookup"><span data-stu-id="67451-145">For example, the full URL of the `comlink.global.j` file is probably `https://airhorner.com/scripts/comlink.global.js`.</span></span> |  
    | `scripts` | <span data-ttu-id="67451-146">目录。</span><span class="sxs-lookup"><span data-stu-id="67451-146">A directory.</span></span> |  
    | `(index)` | <span data-ttu-id="67451-147">主 HTML 文档。</span><span class="sxs-lookup"><span data-stu-id="67451-147">The main HTML document.</span></span> |  
    | `sw.js` | <span data-ttu-id="67451-148">服务工作线程运行时上下文。</span><span class="sxs-lookup"><span data-stu-id="67451-148">A service worker runtime context.</span></span> |  
    
1.  <span data-ttu-id="67451-149">选择一个资源，在编辑器中查看 **它**。</span><span class="sxs-lookup"><span data-stu-id="67451-149">Choose a resource to view it in the **Editor**.</span></span>  
    
    :::image type="complex" source="../media/resources-sources-page-resource.msft.png" alt-text="在编辑器中查看文件" lightbox="../media/resources-sources-page-resource.msft.png":::
       <span data-ttu-id="67451-151">在编辑器中查看 **文件**</span><span class="sxs-lookup"><span data-stu-id="67451-151">View a file in the **Editor**</span></span>  
    :::image-end:::  
    
### <a name="browse-by-filename"></a><span data-ttu-id="67451-152">按文件名浏览</span><span class="sxs-lookup"><span data-stu-id="67451-152">Browse by filename</span></span>  

<span data-ttu-id="67451-153">默认情况下，" **页面"** 选项卡按目录对资源进行分组。</span><span class="sxs-lookup"><span data-stu-id="67451-153">By default, the **Page** tab groups resources by directory.</span></span>  <span data-ttu-id="67451-154">若要将每个域的资源显示为一个简单列表，而不是按目录分组：</span><span class="sxs-lookup"><span data-stu-id="67451-154">To display the resources for each domain as a flat list, instead of grouping them by directory:</span></span>

1.  <span data-ttu-id="67451-155">导航到 **"源"** 工具。</span><span class="sxs-lookup"><span data-stu-id="67451-155">Navigate to the **Sources** tool.</span></span>  
1.  <span data-ttu-id="67451-156">在左侧 **导航器** (窗格中，) " **页面"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="67451-156">In the **Navigator** pane (on the left), choose the **Page** tab.</span></span>  
1.  <span data-ttu-id="67451-157">选择 **"更多选项** `...` "，然后清除"按文件夹 **分组"旁边的选中标记**。</span><span class="sxs-lookup"><span data-stu-id="67451-157">Choose **More options** `...` and then clear the checkmark next to **Group by folder**.</span></span>  
    
    :::image type="complex" source="../media/resources-sources-page-resource-group-by-folder.msft.png" alt-text=""按文件夹分组"选项" lightbox="../media/resources-sources-page-resource-group-by-folder.msft.png":::
       <span data-ttu-id="67451-159">" **按文件夹分组"** 选项</span><span class="sxs-lookup"><span data-stu-id="67451-159">The **Group by folder** option</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="67451-160">资源按文件类型进行组织。</span><span class="sxs-lookup"><span data-stu-id="67451-160">Resources are organized by file type.</span></span>  <span data-ttu-id="67451-161">在每个文件类型内，资源按字母顺序进行组织。</span><span class="sxs-lookup"><span data-stu-id="67451-161">Within each file type, the resources are organized alphabetically.</span></span>  

    :::image type="complex" source="../media/resources-sources-page-resources-empty-not-grouped-by-folder.msft.png" alt-text="清除"按文件夹分组"复选框后的"页面"选项卡" lightbox="../media/resources-sources-page-resources-empty-not-grouped-by-folder.msft.png":::
       <span data-ttu-id="67451-163">清除 **"** 按文件夹分组"复选框后的"页面 **"** 选项卡</span><span class="sxs-lookup"><span data-stu-id="67451-163">The **Page** tab after clearing the **Group by folder** check mark</span></span>  
    :::image-end:::  
    
### <a name="browse-by-file-type"></a><span data-ttu-id="67451-164">按文件类型浏览</span><span class="sxs-lookup"><span data-stu-id="67451-164">Browse by file type</span></span>  

<span data-ttu-id="67451-165">根据资源文件类型将资源分组在一起：</span><span class="sxs-lookup"><span data-stu-id="67451-165">To group resources together based on their file type:</span></span>  

1.  <span data-ttu-id="67451-166">选择" **应用程序"** 选项卡。 应用程序 **工具** 将打开。</span><span class="sxs-lookup"><span data-stu-id="67451-166">Choose the **Application** tab.  The **Application** tool opens.</span></span>  <span data-ttu-id="67451-167">默认情况下， **清单窗格** 通常先打开。</span><span class="sxs-lookup"><span data-stu-id="67451-167">By default the **Manifest** pane usually opens first.</span></span>  
    
    :::image type="complex" source="../media/resources-application-mainfest-airhorner.msft.png" alt-text="应用程序工具" lightbox="../media/resources-application-mainfest-airhorner.msft.png":::
       <span data-ttu-id="67451-169">**应用程序**工具</span><span class="sxs-lookup"><span data-stu-id="67451-169">The **Application** tool</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="67451-170">向下滚动到"框架 **"** 窗格。</span><span class="sxs-lookup"><span data-stu-id="67451-170">Scroll down to the **Frames** pane.</span></span>  
    
    :::image type="complex" source="../media/resources-application-mainfest-airhorner-frames-expanded.msft.png" alt-text=""框架"窗格" lightbox="../media/resources-application-mainfest-airhorner-frames-expanded.msft.png":::
       <span data-ttu-id="67451-172">" **框架"** 窗格</span><span class="sxs-lookup"><span data-stu-id="67451-172">The **Frames** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="67451-173">展开您感兴趣的部分。</span><span class="sxs-lookup"><span data-stu-id="67451-173">Expand the sections in which you are interested.</span></span>  
1.  <span data-ttu-id="67451-174">选择一个资源进行查看。</span><span class="sxs-lookup"><span data-stu-id="67451-174">Choose a resource to view it.</span></span>  
    
    :::image type="complex" source="../media/resources-application-mainfest-airhorner-expanded-resources.msft.png" alt-text="在"应用程序"面板中查看资源" lightbox="../media/resources-application-mainfest-airhorner-expanded-resources.msft.png":::
       <span data-ttu-id="67451-176">在"应用程序"面板 **中查看** 资源</span><span class="sxs-lookup"><span data-stu-id="67451-176">View a resource in the **Application** panel</span></span>  
    :::image-end:::  
    
#### <a name="browse-files-by-type-in-the-network-panel"></a><span data-ttu-id="67451-177">在"网络"面板中按类型浏览文件</span><span class="sxs-lookup"><span data-stu-id="67451-177">Browse files by type in the Network panel</span></span>  

<span data-ttu-id="67451-178">导航到["按资源类型筛选"。][DevtoolsNetworkFilterByResourceType]</span><span class="sxs-lookup"><span data-stu-id="67451-178">Navigate to [Filter by resource type][DevtoolsNetworkFilterByResourceType].</span></span>  

:::image type="complex" source="../media/resources-network-resources-filter-css.msft.png" alt-text="在网络日志中筛选 CSS" lightbox="../media/resources-network-resources-filter-css.msft.png":::
   <span data-ttu-id="67451-180">在网络 **日志中筛选** CSS</span><span class="sxs-lookup"><span data-stu-id="67451-180">Filter for CSS in the **Network** Log</span></span>  
:::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="67451-181">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="67451-181">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 开发人员工具 | Microsoft 文档"  
[DevtoolsNetworkFilterByResourceType]: ../network/index.md#filter-by-resource-type "按资源类型筛选 - 检查 Microsoft Edge DevTools |Microsoft Docs"  
[DevtoolsNetworkInspectDetailsResource]: ../network/index.md#inspect-the-details-of-the-resource "检查资源的详细信息 - 检查 Microsoft Edge DevTools |Microsoft Docs"  
[DevtoolsNetworkLogActivity]: ../network/index.md#log-network-activity "记录网络活动 - 检查 Microsoft Edge DevTools |Microsoft Docs"  

[MDNInlineFrame]: https://developer.mozilla.org/docs/Web/HTML/Element/iframe "<iframe>：内联 Frame 元素|MDN"  
[MDNLearnWebDevelopment]: https://developer.mozilla.org/docs/Learn "了解 Web 开发|MDN"  

> [!NOTE]
> <span data-ttu-id="67451-188">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="67451-188">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="67451-189">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/resources/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="67451-189">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/resources/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="67451-191">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="67451-191">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
