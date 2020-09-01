---
title: 检查 Microsoft Edge DevTools 中的网络活动
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: cca9a45dae5ee845a219ef3f29c54a99e1ee904a
ms.sourcegitcommit: 1251c555c6b4db8ef8187ed94d8832fdb89d03b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2020
ms.locfileid: "10985543"
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





# <span data-ttu-id="de74d-103">检查 Microsoft Edge DevTools 中的网络活动</span><span class="sxs-lookup"><span data-stu-id="de74d-103">Inspect network activity in Microsoft Edge DevTools</span></span>   



<span data-ttu-id="de74d-104">这是与检查页面的网络活动相关的一些最常用的 DevTools 功能的实践教程。</span><span class="sxs-lookup"><span data-stu-id="de74d-104">This is a hands-on tutorial of some of the most commonly-used DevTools features related to inspecting network activity for a page.</span></span>  

<span data-ttu-id="de74d-105">如果想要浏览功能，请参阅 [网络参考][DevtoolsNetworkReference] 。</span><span class="sxs-lookup"><span data-stu-id="de74d-105">See [Network Reference][DevtoolsNetworkReference] if you want to browse features instead.</span></span>  

<!--TODO: This entire section needs a Microsoft Edge DevTools re-write  -->

<!-- Read on, or watch the video version of this tutorial:  -->  

<!--
> [!VIDEO embed/e1gAyQuIFQo]  
-->

## <span data-ttu-id="de74d-106">何时使用网络面板</span><span class="sxs-lookup"><span data-stu-id="de74d-106">When to use the Network panel</span></span>   

<span data-ttu-id="de74d-107">一般情况下，当你需要确保按预期下载或上载资源时，请使用 "网络" 面板。</span><span class="sxs-lookup"><span data-stu-id="de74d-107">In general, use the Network panel when you need to make sure that resources are being downloaded or uploaded as expected.</span></span>  <span data-ttu-id="de74d-108">网络面板最常见的使用案例是：</span><span class="sxs-lookup"><span data-stu-id="de74d-108">The most common use cases for the Network panel are:</span></span>  

*   <span data-ttu-id="de74d-109">确保实际上载或下载资源。</span><span class="sxs-lookup"><span data-stu-id="de74d-109">Making sure that resources are actually being uploaded or downloaded at all.</span></span>  
*   <span data-ttu-id="de74d-110">检查单个资源的属性，例如 HTTP 头、内容、大小等。</span><span class="sxs-lookup"><span data-stu-id="de74d-110">Inspecting the properties of an individual resource, such as the HTTP headers, content, size, and so on.</span></span>  
    
<span data-ttu-id="de74d-111">如果你正在寻找提高页面加载性能的 **方法，请不要从** 网络面板开始。</span><span class="sxs-lookup"><span data-stu-id="de74d-111">If you are looking for ways to improve page load performance, **do not** start with the Network panel.</span></span>  <span data-ttu-id="de74d-112">有许多类型的加载性能问题与网络活动无关。</span><span class="sxs-lookup"><span data-stu-id="de74d-112">There are many types of load performance issues that are not related to network activity.</span></span>  <span data-ttu-id="de74d-113">从 "审核" 面板开始，因为它为你提供了有关如何改进页面的目标建议。</span><span class="sxs-lookup"><span data-stu-id="de74d-113">Start with the Audits panel because it gives you targeted suggestions on how to improve your page.</span></span>  <span data-ttu-id="de74d-114">请参阅 [优化网站速度][DevtoolsSpeedGetStarted]。</span><span class="sxs-lookup"><span data-stu-id="de74d-114">See [Optimize Website Speed][DevtoolsSpeedGetStarted].</span></span>  

## <span data-ttu-id="de74d-115">打开 "网络" 面板</span><span class="sxs-lookup"><span data-stu-id="de74d-115">Open the Network panel</span></span>   

<span data-ttu-id="de74d-116">若要充分利用本教程，请打开演示，然后尝试使用演示页面上的功能。</span><span class="sxs-lookup"><span data-stu-id="de74d-116">To get the most out of this tutorial, open up the demo and try out the features on the demo page.</span></span>  

1.  <span data-ttu-id="de74d-117">打开 [入门演示][GlitchNetworkGetStarted]。</span><span class="sxs-lookup"><span data-stu-id="de74d-117">Open the [Get Started Demo][GlitchNetworkGetStarted].</span></span>  
    
    :::image type="complex" source="../media/network-glitch-inspect-network-activity-demo.msft.png" alt-text="演示" lightbox="../media/network-glitch-inspect-network-activity-demo.msft.png":::
       <span data-ttu-id="de74d-119">演示</span><span class="sxs-lookup"><span data-stu-id="de74d-119">The demo</span></span>  
    :::image-end:::  
    
    <!--You may prefer to move the demo to a separate window.  -->  
    
    <!--
    :::image type="complex" source="../media/network-tutorial/windows.msft.png" alt-text="The demo in one window and this tutorial in a different window" lightbox="../media/network-tutorial/windows.msft.png":::
       The demo in one window and this tutorial in a different window  
    :::image-end:::  
    -->
    
1.  <span data-ttu-id="de74d-120">[Open DevTools][DevToolsOpen]按 `Control` + `Shift` + `J` \ (Windows \ ) 或 `Command` + `Option` + `J` \ (macOS \ ) 打开 DevTools。</span><span class="sxs-lookup"><span data-stu-id="de74d-120">[Open DevTools][DevToolsOpen] by pressing `Control`+`Shift`+`J` \(Windows\) or `Command`+`Option`+`J` \(macOS\).</span></span>  <span data-ttu-id="de74d-121">此时将打开 " **控制台** " 面板。</span><span class="sxs-lookup"><span data-stu-id="de74d-121">The **Console** panel opens.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-console.msft.png" alt-text="该控制台" lightbox="../media/network-glitch-console.msft.png":::
       <span data-ttu-id="de74d-123">该 **控制台**</span><span class="sxs-lookup"><span data-stu-id="de74d-123">The **Console**</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="de74d-124">您可能希望将 [DevTools 停靠在窗口底部][DevToolsCustomizePlacement]。</span><span class="sxs-lookup"><span data-stu-id="de74d-124">You may prefer to [dock DevTools to the bottom of your window][DevToolsCustomizePlacement].</span></span>  
    
    :::image type="complex" source="../media/network-glitch-console-bottom.msft.png" alt-text="DevTools 停靠在窗口底部" lightbox="../media/network-glitch-console-bottom.msft.png":::
       <span data-ttu-id="de74d-126">DevTools 停靠在窗口底部</span><span class="sxs-lookup"><span data-stu-id="de74d-126">DevTools docked to the bottom of the window</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="de74d-127">选择 " **网络** " 选项卡。 "网络" 面板将打开。</span><span class="sxs-lookup"><span data-stu-id="de74d-127">Select the **Network** tab.  The Network panel opens.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-bottom.msft.png" alt-text="DevTools 停靠在窗口底部" lightbox="../media/network-glitch-network-bottom.msft.png":::
       <span data-ttu-id="de74d-129">DevTools 停靠在窗口底部</span><span class="sxs-lookup"><span data-stu-id="de74d-129">DevTools docked to the bottom of the window</span></span>  
    :::image-end:::  
    
<span data-ttu-id="de74d-130">现在，网络面板为空。</span><span class="sxs-lookup"><span data-stu-id="de74d-130">Right now the Network panel is empty.</span></span>  <span data-ttu-id="de74d-131">DevTools 仅在打开网络活动后记录网络活动，并且自打开 DevTools 后未发生任何网络活动。</span><span class="sxs-lookup"><span data-stu-id="de74d-131">DevTools only logs network activity after you open it and no network activity has occurred since you opened DevTools.</span></span>  

## <span data-ttu-id="de74d-132">记录网络活动</span><span class="sxs-lookup"><span data-stu-id="de74d-132">Log network activity</span></span>   

<span data-ttu-id="de74d-133">要查看页面导致的网络活动，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="de74d-133">To view the network activity that a page causes:</span></span>  

1.  <span data-ttu-id="de74d-134">重新加载页面。</span><span class="sxs-lookup"><span data-stu-id="de74d-134">Reload the page.</span></span>  <span data-ttu-id="de74d-135">"网络" 面板将在 **网络日志**中记录所有网络活动。</span><span class="sxs-lookup"><span data-stu-id="de74d-135">The Network panel logs all network activity in the **Network Log**.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network.msft.png" alt-text="网络日志" lightbox="../media/network-glitch-network.msft.png":::
       <span data-ttu-id="de74d-137">**网络日志**</span><span class="sxs-lookup"><span data-stu-id="de74d-137">The **Network Log**</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="de74d-138">**网络日志**的每一行表示一个资源。</span><span class="sxs-lookup"><span data-stu-id="de74d-138">Each row of the **Network Log** represents a resource.</span></span>  <span data-ttu-id="de74d-139">默认情况下，资源按时间顺序列出。</span><span class="sxs-lookup"><span data-stu-id="de74d-139">By default the resources are listed chronologically.</span></span>  <span data-ttu-id="de74d-140">顶部资源通常是主 HTML 文档。</span><span class="sxs-lookup"><span data-stu-id="de74d-140">The top resource is usually the main HTML document.</span></span>  <span data-ttu-id="de74d-141">最底层的资源是最后请求的内容。</span><span class="sxs-lookup"><span data-stu-id="de74d-141">The bottom resource is whatever was requested last.</span></span>  
    
    <span data-ttu-id="de74d-142">每列表示有关资源的信息。</span><span class="sxs-lookup"><span data-stu-id="de74d-142">Each column represents information about a resource.</span></span>  <span data-ttu-id="de74d-143">在上图中，显示默认列。</span><span class="sxs-lookup"><span data-stu-id="de74d-143">In the previous figure the default columns are displayed.</span></span>  

    *   <span data-ttu-id="de74d-144">**状态**。</span><span class="sxs-lookup"><span data-stu-id="de74d-144">**Status**.</span></span>  <span data-ttu-id="de74d-145">用于响应的 HTTP 状态代码。</span><span class="sxs-lookup"><span data-stu-id="de74d-145">The HTTP status code for response.</span></span>  
    *   <span data-ttu-id="de74d-146">**类型**。</span><span class="sxs-lookup"><span data-stu-id="de74d-146">**Type**.</span></span>  <span data-ttu-id="de74d-147">资源类型。</span><span class="sxs-lookup"><span data-stu-id="de74d-147">The resource type.</span></span>  
    *   <span data-ttu-id="de74d-148">**启动器**。</span><span class="sxs-lookup"><span data-stu-id="de74d-148">**Initiator**.</span></span>  <span data-ttu-id="de74d-149">资源请求的原因。</span><span class="sxs-lookup"><span data-stu-id="de74d-149">The cause of the resource request.</span></span>  <span data-ttu-id="de74d-150">选择 "发起方" 列中的链接将转到导致请求的源代码。</span><span class="sxs-lookup"><span data-stu-id="de74d-150">Selecting a link in the Initiator column takes you to the source code that caused the request.</span></span>  
    *   <span data-ttu-id="de74d-151">**时间**。</span><span class="sxs-lookup"><span data-stu-id="de74d-151">**Time**.</span></span>  <span data-ttu-id="de74d-152">请求的持续时间。</span><span class="sxs-lookup"><span data-stu-id="de74d-152">The duration of the request.</span></span>  
    *   <span data-ttu-id="de74d-153">**瀑布**图。</span><span class="sxs-lookup"><span data-stu-id="de74d-153">**Waterfall**.</span></span>  <span data-ttu-id="de74d-154">请求的不同阶段的图形表示形式。</span><span class="sxs-lookup"><span data-stu-id="de74d-154">A graphical representation of the different stages of the request.</span></span>  <span data-ttu-id="de74d-155">将鼠标悬停在瀑布上以查看细目。</span><span class="sxs-lookup"><span data-stu-id="de74d-155">Hover over a Waterfall to see a breakdown.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="de74d-156">网络日志上方的图形称为概述。</span><span class="sxs-lookup"><span data-stu-id="de74d-156">The graph above the Network Log is called the Overview.</span></span>  <span data-ttu-id="de74d-157">您将不使用本教程中的概述图形，因此您可以将其隐藏。</span><span class="sxs-lookup"><span data-stu-id="de74d-157">You will not use the Overview graph in this tutorial, so you may hide it.</span></span>  <span data-ttu-id="de74d-158">请参阅 [隐藏概述窗格][DevtoolsReferenceHideOverview]。</span><span class="sxs-lookup"><span data-stu-id="de74d-158">See [Hide the Overview pane][DevtoolsReferenceHideOverview].</span></span>
    
1.  <span data-ttu-id="de74d-159">打开 DevTools 后，它将在网络日志中记录网络活动。</span><span class="sxs-lookup"><span data-stu-id="de74d-159">After you open DevTools, it records network activity in the Network Log.</span></span>  
    <span data-ttu-id="de74d-160">若要演示此操作，请首先查看 **网络日志** 的底部，并注意最后一个活动。</span><span class="sxs-lookup"><span data-stu-id="de74d-160">To demonstrate this, first look at the bottom of the **Network Log** and make a mental note of the last activity.</span></span>  
1.  <span data-ttu-id="de74d-161">现在，选择演示中的 " **获取数据** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="de74d-161">Now, select the **Get Data** button in the demo.</span></span>  
1.  <span data-ttu-id="de74d-162">再次查看 **网络日志** 的底部。</span><span class="sxs-lookup"><span data-stu-id="de74d-162">Look at the bottom of the **Network Log** again.</span></span>  <span data-ttu-id="de74d-163">你应该会看到一个名为 `getstarted.json` 的新资源。</span><span class="sxs-lookup"><span data-stu-id="de74d-163">You should see a new resource called `getstarted.json`.</span></span>  <span data-ttu-id="de74d-164">选择 " **获取数据** " 按钮导致页面请求该文件。</span><span class="sxs-lookup"><span data-stu-id="de74d-164">Selecting the **Get Data** button caused the page to request this file.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-new-resource.msft.png" alt-text="网络日志中的新资源" lightbox="../media/network-glitch-network-new-resource.msft.png":::
       <span data-ttu-id="de74d-166">**网络日志**中的新资源</span><span class="sxs-lookup"><span data-stu-id="de74d-166">A new resource in the **Network Log**</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="de74d-167">显示详细信息</span><span class="sxs-lookup"><span data-stu-id="de74d-167">Show more information</span></span>   

<span data-ttu-id="de74d-168">网络日志的列是可配置的。</span><span class="sxs-lookup"><span data-stu-id="de74d-168">The columns of the Network Log are configurable.</span></span>  <span data-ttu-id="de74d-169">您可以隐藏未使用的列。</span><span class="sxs-lookup"><span data-stu-id="de74d-169">You may hide columns that you are not using.</span></span>  
<span data-ttu-id="de74d-170">默认情况下，在默认情况下会隐藏许多列，您可能会发现这些列很有用。</span><span class="sxs-lookup"><span data-stu-id="de74d-170">There are also many columns that are hidden by default which you may find useful.</span></span>  

1.  <span data-ttu-id="de74d-171">右键单击网络日志表的标题，然后选择 " **域**"。</span><span class="sxs-lookup"><span data-stu-id="de74d-171">Right-click the header of the Network Log table and select **Domain**.</span></span>  <span data-ttu-id="de74d-172">现在显示了每个资源的域。</span><span class="sxs-lookup"><span data-stu-id="de74d-172">The domain of each resource is now shown.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-edit-column.msft.png" alt-text="启用 "域" 列" lightbox="../media/network-glitch-network-edit-column.msft.png":::
       <span data-ttu-id="de74d-174">启用 "域" 列</span><span class="sxs-lookup"><span data-stu-id="de74d-174">Enable the Domain column</span></span>  
    :::image-end:::  
    
    > [!TIP]
    > <span data-ttu-id="de74d-175">通过将鼠标悬停在 " **名称** " 列中的单元格上，查看资源的完整 URL。</span><span class="sxs-lookup"><span data-stu-id="de74d-175">See the full URL of a resource by hovering over the cell in the **Name** column.</span></span>  
    
## <span data-ttu-id="de74d-176">模拟速度较慢的网络连接</span><span class="sxs-lookup"><span data-stu-id="de74d-176">Simulate a slower network connection</span></span>   

<span data-ttu-id="de74d-177">用于构建网站的计算机的网络连接可能比用户移动设备的网络连接速度更快。</span><span class="sxs-lookup"><span data-stu-id="de74d-177">The network connection of the computer that you use to build sites is probably faster than the network connections of the mobile devices of your users.</span></span>  <span data-ttu-id="de74d-178">通过限制页面，可以更好地了解页面在移动设备上的加载时间。</span><span class="sxs-lookup"><span data-stu-id="de74d-178">By throttling the page, you get a better idea of how long a page takes to load on a mobile device.</span></span>  

1.  <span data-ttu-id="de74d-179">选择 " **限制** " 下拉列表，默认设置为 " **联机** "。</span><span class="sxs-lookup"><span data-stu-id="de74d-179">Select the **Throttling** dropdown, which is set to **Online** by default.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-throttling.msft.png" alt-text="启用限制" lightbox="../media/network-glitch-network-throttling.msft.png":::
       <span data-ttu-id="de74d-181">启用限制</span><span class="sxs-lookup"><span data-stu-id="de74d-181">Enable throttling</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="de74d-182">选择 " **慢速 3g**"。</span><span class="sxs-lookup"><span data-stu-id="de74d-182">Select **Slow 3G**.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-throttling-slow-3g.msft.png" alt-text="选择慢速3G" lightbox="../media/network-glitch-network-throttling-slow-3g.msft.png":::
       <span data-ttu-id="de74d-184">选择慢速3G</span><span class="sxs-lookup"><span data-stu-id="de74d-184">Select Slow 3G</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="de74d-185">长按 **重新加载** \ (![ 重装 ][ImageRefreshIcon] \ ) 然后选择 " **清空缓存" 和 "硬重新加载**"。</span><span class="sxs-lookup"><span data-stu-id="de74d-185">Long-press **Reload** \(![Reload][ImageRefreshIcon]\) and then select **Empty Cache And Hard Reload**.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-empty-cache-and-hard-reset.msft.png" alt-text="清空缓存和硬重载" lightbox="../media/network-glitch-empty-cache-and-hard-reset.msft.png":::
       **<span data-ttu-id="de74d-187">清空缓存和硬重载</span><span class="sxs-lookup"><span data-stu-id="de74d-187">Empty Cache And Hard Reload</span></span>**  
    :::image-end:::  
    
    <span data-ttu-id="de74d-188">在重复访问时，浏览器通常会从 [缓存][MDNHTTPCache]中处理某些文件，从而加速页面加载。</span><span class="sxs-lookup"><span data-stu-id="de74d-188">On repeat visits, the browser usually serves some files from the [cache][MDNHTTPCache], which speeds up the page load.</span></span>  <span data-ttu-id="de74d-189">**清空缓存和硬重新加载** 会强制浏览器为所有资源访问网络。</span><span class="sxs-lookup"><span data-stu-id="de74d-189">**Empty Cache And Hard Reload** forces the browser to go the network for all resources.</span></span>  <span data-ttu-id="de74d-190">如果你想要了解第一次访问者体验页面加载的方式，这很有帮助。</span><span class="sxs-lookup"><span data-stu-id="de74d-190">This is helpful when you want to see how a first-time visitor experiences a page load.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="de74d-191">只有在 DevTools 处于打开状态时， **空缓存和硬加载** 工作流才可用。</span><span class="sxs-lookup"><span data-stu-id="de74d-191">The **Empty Cache And Hard Reload** workflow is only available when DevTools is open.</span></span>  
    
## <span data-ttu-id="de74d-192">捕获屏幕截图</span><span class="sxs-lookup"><span data-stu-id="de74d-192">Capture screenshots</span></span>   

<span data-ttu-id="de74d-193">屏幕截图使你可以查看页面在加载时如何在一段时间内查看。</span><span class="sxs-lookup"><span data-stu-id="de74d-193">Screenshots let you see how a page looked over time while it was loading.</span></span>  

1.  <span data-ttu-id="de74d-194">选择 \ (![ 网络设置 ][ImageSettingsIcon] \ ) 并选择 " **捕获屏幕截图** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="de74d-194">Select \(![Network settings][ImageSettingsIcon]\) and select the **Capture screenshots** checkbox.</span></span>
1.  <span data-ttu-id="de74d-195">通过 **空缓存和硬重装** 工作流重新加载页面。</span><span class="sxs-lookup"><span data-stu-id="de74d-195">Reload the page again via the **Empty Cache And Hard Reload** workflow.</span></span>  <span data-ttu-id="de74d-196">如果需要有关如何执行此操作的提醒，请参阅 [模拟低速连接](#simulate-a-slower-network-connection) 。</span><span class="sxs-lookup"><span data-stu-id="de74d-196">See [Simulate a slower connection](#simulate-a-slower-network-connection) if you need a reminder on how to do this.</span></span>  
    <span data-ttu-id="de74d-197">"屏幕截图" 窗格提供在加载过程中如何在不同点查看页面的缩略图。</span><span class="sxs-lookup"><span data-stu-id="de74d-197">The Screenshots pane provides thumbnails of how the page looked at various points during the loading process.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-screenshots.msft.png" alt-text="页面加载的屏幕截图" lightbox="../media/network-glitch-network-screenshots.msft.png":::
       <span data-ttu-id="de74d-199">页面加载的屏幕截图</span><span class="sxs-lookup"><span data-stu-id="de74d-199">Screenshots of the page load</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="de74d-200">选择第一个缩略图。</span><span class="sxs-lookup"><span data-stu-id="de74d-200">Select the first thumbnail.</span></span>  <span data-ttu-id="de74d-201">DevTools 显示当时正在发生的网络活动。</span><span class="sxs-lookup"><span data-stu-id="de74d-201">DevTools shows you what network activity was occurring at that moment in time.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-screenshots-first.msft.png" alt-text="第一个屏幕截图期间发生的网络活动" lightbox="../media/network-glitch-network-screenshots-first.msft.png":::
       <span data-ttu-id="de74d-203">第一个屏幕截图期间发生的网络活动</span><span class="sxs-lookup"><span data-stu-id="de74d-203">The network activity that was happening during the first screenshot</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="de74d-204">再次选择 \ (![ 网络设置 ][ImageSettingsIcon] \ ) 并取消选中 " **捕获屏幕截图** " 复选框以关闭屏幕截图窗格。</span><span class="sxs-lookup"><span data-stu-id="de74d-204">Select \(![Network settings][ImageSettingsIcon]\) again and deselect the **Capture screenshots** checkbox to close the Screenshots pane.</span></span>
1.  <span data-ttu-id="de74d-205">重新加载页面。</span><span class="sxs-lookup"><span data-stu-id="de74d-205">Reload the page again.</span></span>  
    
## <span data-ttu-id="de74d-206">检查资源的详细信息</span><span class="sxs-lookup"><span data-stu-id="de74d-206">Inspect the details of the resource</span></span>   

<span data-ttu-id="de74d-207">选择资源以了解有关它的详细信息。</span><span class="sxs-lookup"><span data-stu-id="de74d-207">Select a resource to learn more information about it.</span></span>  <span data-ttu-id="de74d-208">立即试用：</span><span class="sxs-lookup"><span data-stu-id="de74d-208">Try it now:</span></span>  

1.  <span data-ttu-id="de74d-209">选择 `getstarted.html` 。</span><span class="sxs-lookup"><span data-stu-id="de74d-209">Select `getstarted.html`.</span></span>  <span data-ttu-id="de74d-210">显示 " **标题** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="de74d-210">The **Headers** tab is shown.</span></span>  <span data-ttu-id="de74d-211">使用此选项卡检查 HTTP 头。</span><span class="sxs-lookup"><span data-stu-id="de74d-211">Use this tab to inspect HTTP headers.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-resources-headers.msft.png" alt-text=""页眉" 选项卡" lightbox="../media/network-glitch-network-resources-headers.msft.png":::
       <span data-ttu-id="de74d-213">" **页眉** " 选项卡</span><span class="sxs-lookup"><span data-stu-id="de74d-213">The **Headers** tab</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="de74d-214">选择 " **预览** " 选项卡。 显示 HTML 的基本呈现。</span><span class="sxs-lookup"><span data-stu-id="de74d-214">Select the **Preview** tab.  A basic rendering of the HTML is shown.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-resources-preview.msft.png" alt-text=""预览" 选项卡" lightbox="../media/network-glitch-network-resources-preview.msft.png":::
       <span data-ttu-id="de74d-216">" **预览** " 选项卡</span><span class="sxs-lookup"><span data-stu-id="de74d-216">The **Preview** tab</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="de74d-217">当 API 返回 HTML 中的错误代码时，此选项卡很有帮助。</span><span class="sxs-lookup"><span data-stu-id="de74d-217">This tab is helpful when an API returns an error code in HTML.</span></span>  <span data-ttu-id="de74d-218">您可能会发现，阅读呈现的 HTML 比 HTML 源代码或检查图像更容易。</span><span class="sxs-lookup"><span data-stu-id="de74d-218">You may find it easier to read the rendered HTML than the HTML source code, or when you inspect images.</span></span>  

1.  <span data-ttu-id="de74d-219">选择 " **响应** " 选项卡。 将显示 HTML 源代码。</span><span class="sxs-lookup"><span data-stu-id="de74d-219">Select the **Response** tab.  The HTML source code is shown.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-resources-response.msft.png" alt-text=""响应" 选项卡" lightbox="../media/network-glitch-network-resources-response.msft.png":::
       <span data-ttu-id="de74d-221">" **响应** " 选项卡</span><span class="sxs-lookup"><span data-stu-id="de74d-221">The **Response** tab</span></span>  
    :::image-end:::  
    
    > [!TIP]
    > <span data-ttu-id="de74d-222">当文件为 minified 时，选择**Format** ![ ][ImageFormatIcon] "**响应**" 选项卡底部的 "格式 \ (格式 \ ) " 按钮可重新设置文件内容的格式，以提高可读性。</span><span class="sxs-lookup"><span data-stu-id="de74d-222">When a file is minified, selecting the **Format** \(![Format][ImageFormatIcon]\) button at the bottom of the **Response** tab re-formats the contents of the file for readability.</span></span>  
    
1.  <span data-ttu-id="de74d-223">选择 " **计时** " 选项卡。 将显示此资源的网络活动细目。</span><span class="sxs-lookup"><span data-stu-id="de74d-223">Select the **Timing** tab.  A breakdown of the network activity for this resource is shown.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-resources-timing.msft.png" alt-text=""计时" 选项卡" lightbox="../media/network-glitch-network-resources-timing.msft.png":::
       <span data-ttu-id="de74d-225">" **计时** " 选项卡</span><span class="sxs-lookup"><span data-stu-id="de74d-225">The **Timing** tab</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="de74d-226">选择 " **关闭** \ (![ 关闭 ][ImageCloseIcon] \ ) " 再次查看网络日志。</span><span class="sxs-lookup"><span data-stu-id="de74d-226">Select **Close** \(![Close][ImageCloseIcon]\) to view the Network Log again.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-resources-close-tabs.msft.png" alt-text=""关闭" 按钮" lightbox="../media/network-glitch-network-resources-close-tabs.msft.png":::
       <span data-ttu-id="de74d-228">" **关闭** " 按钮</span><span class="sxs-lookup"><span data-stu-id="de74d-228">The **Close** button</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="de74d-229">搜索网络标题和响应</span><span class="sxs-lookup"><span data-stu-id="de74d-229">Search network headers and responses</span></span>   

<span data-ttu-id="de74d-230">当你需要在 HTTP 头和所有资源的响应中搜索特定字符串或正则表达式的响应时，请使用 " **搜索** " 窗格。</span><span class="sxs-lookup"><span data-stu-id="de74d-230">Use the **Search** pane when you need to search the HTTP headers and responses of all resources for a certain string or regular expression.</span></span>  

<span data-ttu-id="de74d-231">例如，假设你想要验证你的资源是否使用了合理的 **缓存策略**。</span><span class="sxs-lookup"><span data-stu-id="de74d-231">For example, suppose you want to verify that your resources are using reasonable **cache policies**.</span></span>  

<!--TODO: add cache policies section when available  -->

1.  <span data-ttu-id="de74d-232">选择 " **搜索** \ (![ 搜索 ][ImageSearchIcon] \ ) "。</span><span class="sxs-lookup"><span data-stu-id="de74d-232">Select **Search** \(![Search][ImageSearchIcon]\).</span></span>  <span data-ttu-id="de74d-233">"搜索" 窗格将在网络日志的左侧打开。</span><span class="sxs-lookup"><span data-stu-id="de74d-233">The Search pane opens to the left of the Network log.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-search-empty.msft.png" alt-text=""搜索" 窗格" lightbox="../media/network-glitch-network-search-empty.msft.png":::
       <span data-ttu-id="de74d-235">" **搜索** " 窗格</span><span class="sxs-lookup"><span data-stu-id="de74d-235">The **Search** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="de74d-236">键入 `Cache-Control` ，然后按 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="de74d-236">Type `Cache-Control` and press `Enter`.</span></span>  <span data-ttu-id="de74d-237">"搜索" 窗格 `Cache-Control` 会列出它在 "资源标题" 或 "内容" 中找到的所有实例。</span><span class="sxs-lookup"><span data-stu-id="de74d-237">The Search pane lists all instances of `Cache-Control` that it finds in resource headers or content.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-search-cache-control.msft.png" alt-text="缓存控制的搜索结果" lightbox="../media/network-glitch-network-search-cache-control.msft.png":::
       <span data-ttu-id="de74d-239">以下项的搜索结果</span><span class="sxs-lookup"><span data-stu-id="de74d-239">Search results for</span></span> `Cache-Control`  
    :::image-end:::  
    
1.  <span data-ttu-id="de74d-240">选择一个结果以查看在其中找到结果的资源。</span><span class="sxs-lookup"><span data-stu-id="de74d-240">Select a result to view the resource in which the result was found.</span></span>  <span data-ttu-id="de74d-241">如果要查看资源的详细信息，请选择要直接转到该资源的结果。</span><span class="sxs-lookup"><span data-stu-id="de74d-241">If you are looking at the details of the resource, select a result to go directly to it.</span></span>  <span data-ttu-id="de74d-242">例如，如果在页眉中找到查询，则 "页眉" 选项卡将打开。</span><span class="sxs-lookup"><span data-stu-id="de74d-242">For example, if the query was found in a header, the Headers tab opens.</span></span>   <span data-ttu-id="de74d-243">如果在内容中找到查询，将打开 " **响应** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="de74d-243">If the query was found in content, the **Response** tab opens.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-search-cache-control-headers-response-headers.msft.png" alt-text=""页眉" 选项卡中突出显示的搜索结果" lightbox="../media/network-glitch-network-search-cache-control-headers-response-headers.msft.png":::
       <span data-ttu-id="de74d-245">" **页眉** " 选项卡中突出显示的搜索结果</span><span class="sxs-lookup"><span data-stu-id="de74d-245">A search result highlighted in the **Headers** tab</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="de74d-246">关闭 "搜索" 窗格和 "标题" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="de74d-246">Close the Search pane and the Headers tab.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-search-close.msft.png" alt-text=""关闭" 按钮" lightbox="../media/network-glitch-network-search-close.msft.png":::
       <span data-ttu-id="de74d-248">" **关闭** " 按钮</span><span class="sxs-lookup"><span data-stu-id="de74d-248">The **Close** buttons</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="de74d-249">筛选资源</span><span class="sxs-lookup"><span data-stu-id="de74d-249">Filter resources</span></span>   

<span data-ttu-id="de74d-250">DevTools 提供了大量工作流，用于筛选出与手边的任务无关的资源。</span><span class="sxs-lookup"><span data-stu-id="de74d-250">DevTools provides numerous workflows for filtering out resources that are not relevant to the task at hand.</span></span>  

:::image type="complex" source="../media/network-glitch-network-filter-empty.msft.png" alt-text=""筛选器" 工具栏" lightbox="../media/network-glitch-network-filter-empty.msft.png":::
   <span data-ttu-id="de74d-252">" **筛选器** " 工具栏</span><span class="sxs-lookup"><span data-stu-id="de74d-252">The **Filters** toolbar</span></span>  
:::image-end:::  

<span data-ttu-id="de74d-253">默认情况下，应启用 " **筛选器** " 工具栏。</span><span class="sxs-lookup"><span data-stu-id="de74d-253">The **Filters** toolbar should be enabled by default.</span></span>  <span data-ttu-id="de74d-254">如果未执行此操作：</span><span class="sxs-lookup"><span data-stu-id="de74d-254">If not:</span></span>  

1.  <span data-ttu-id="de74d-255">选择 " **筛选** \ (![ 筛选器 \ ) " ][ImageFilterIcon] 以显示它。</span><span class="sxs-lookup"><span data-stu-id="de74d-255">Select **Filter** \(![Filter][ImageFilterIcon]\) to show it.</span></span>  
    
### <span data-ttu-id="de74d-256">按字符串、正则表达式或属性筛选</span><span class="sxs-lookup"><span data-stu-id="de74d-256">Filter by string, regular expression, or property</span></span>   

<span data-ttu-id="de74d-257">**筛选**文本框支持许多不同类型的筛选。</span><span class="sxs-lookup"><span data-stu-id="de74d-257">The **Filter** text box supports many different types of filtering.</span></span>  

1.  <span data-ttu-id="de74d-258">在 `png` " **筛选器** " 文本框中键入内容。</span><span class="sxs-lookup"><span data-stu-id="de74d-258">Type `png` into the **Filter** text box.</span></span>  <span data-ttu-id="de74d-259">仅显示包含文本的文件 `png` 。</span><span class="sxs-lookup"><span data-stu-id="de74d-259">Only the files that contain the text `png` are shown.</span></span>  <span data-ttu-id="de74d-260">在这种情况下，只有与筛选器匹配的文件才是 PNG 图像。</span><span class="sxs-lookup"><span data-stu-id="de74d-260">In this case the only files that match the filter are the PNG images.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-filter-png.msft.png" alt-text="字符串筛选器" lightbox="../media/network-glitch-network-filter-png.msft.png":::
       <span data-ttu-id="de74d-262">字符串筛选器</span><span class="sxs-lookup"><span data-stu-id="de74d-262">A string filter</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="de74d-263">键入 `/.*\.[cj]s+$/`。</span><span class="sxs-lookup"><span data-stu-id="de74d-263">Type `/.*\.[cj]s+$/`.</span></span>  <span data-ttu-id="de74d-264">DevTools 筛选出文件名不以 a `j` 或 `c` 后跟1或更多字符结尾的任何资源 `s` 。</span><span class="sxs-lookup"><span data-stu-id="de74d-264">DevTools filters out any resource with a filename that does not end with a `j` or a `c` followed by 1 or more `s` characters.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-filter-regex.msft.png" alt-text="正则表达式筛选" lightbox="../media/network-glitch-network-filter-regex.msft.png":::
       <span data-ttu-id="de74d-266">正则表达式筛选</span><span class="sxs-lookup"><span data-stu-id="de74d-266">A regular expression filter</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="de74d-267">键入 `-main.css`。</span><span class="sxs-lookup"><span data-stu-id="de74d-267">Type `-main.css`.</span></span>  <span data-ttu-id="de74d-268">DevTools 筛选器 `main.css` 。</span><span class="sxs-lookup"><span data-stu-id="de74d-268">DevTools filters out `main.css`.</span></span>  <span data-ttu-id="de74d-269">如果任何其他文件与模式匹配，它们也将被筛选掉。</span><span class="sxs-lookup"><span data-stu-id="de74d-269">If any other file matched the pattern they would also be filtered out.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-filter-negative-statement.msft.png" alt-text="负滤波器" lightbox="../media/network-glitch-network-filter-negative-statement.msft.png":::
       <span data-ttu-id="de74d-271">负滤波器</span><span class="sxs-lookup"><span data-stu-id="de74d-271">A negative filter</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="de74d-272">在 `domain:cdn.glitch.com` " **筛选器** " 文本框中键入内容。</span><span class="sxs-lookup"><span data-stu-id="de74d-272">Type `domain:cdn.glitch.com` into the **Filter** text box.</span></span>  <span data-ttu-id="de74d-273">DevTools 筛选出具有与此域不匹配的 URL 的任何资源。</span><span class="sxs-lookup"><span data-stu-id="de74d-273">DevTools filters out any resource with a URL that does not match this domain.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-filter-property-value.msft.png" alt-text="属性筛选器" lightbox="../media/network-glitch-network-filter-property-value.msft.png":::
       <span data-ttu-id="de74d-275">属性筛选器</span><span class="sxs-lookup"><span data-stu-id="de74d-275">A property filter</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="de74d-276">有关筛选属性的完整列表，请参阅 [筛选请求][DevtoolsReferenceProperty] 。</span><span class="sxs-lookup"><span data-stu-id="de74d-276">See [Filter requests by properties][DevtoolsReferenceProperty] for the full list of filterable properties.</span></span>  
    
1.  <span data-ttu-id="de74d-277">清除任何文本的 " **筛选器** " 文本框。</span><span class="sxs-lookup"><span data-stu-id="de74d-277">Clear the **Filter** text box of any text.</span></span>  
    
### <span data-ttu-id="de74d-278">按资源类型筛选</span><span class="sxs-lookup"><span data-stu-id="de74d-278">Filter by resource type</span></span>   

<span data-ttu-id="de74d-279">关注特定类型的文件，例如样式表：</span><span class="sxs-lookup"><span data-stu-id="de74d-279">To focus in on a certain type of file, such as stylesheets:</span></span>  

1.  <span data-ttu-id="de74d-280">选择 " **CSS**"。</span><span class="sxs-lookup"><span data-stu-id="de74d-280">Select **CSS**.</span></span>  <span data-ttu-id="de74d-281">将筛选出所有其他文件类型。</span><span class="sxs-lookup"><span data-stu-id="de74d-281">All other file types are filtered out.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-filter-file-type-css.msft.png" alt-text="仅显示 CSS 文件" lightbox="../media/network-glitch-network-filter-file-type-css.msft.png":::
       <span data-ttu-id="de74d-283">仅显示 CSS 文件</span><span class="sxs-lookup"><span data-stu-id="de74d-283">Show CSS files only</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="de74d-284">若要查看脚本，请按住 `Control` (Windows \ ) 或 `Command` \ (macOS \ ) ，然后选择 " **JS**"。</span><span class="sxs-lookup"><span data-stu-id="de74d-284">To also see scripts, hold `Control` \(Windows\) or `Command` \(macOS\) and then select **JS**.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-filter-file-type-css-js.msft.png" alt-text="仅显示 CSS 和 JS 文件" lightbox="../media/network-glitch-network-filter-file-type-css-js.msft.png":::
       <span data-ttu-id="de74d-286">仅显示 CSS 和 JS 文件</span><span class="sxs-lookup"><span data-stu-id="de74d-286">Show CSS and JS files only</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="de74d-287">选择 " **全部** " 以删除筛选器并再次查看所有资源。</span><span class="sxs-lookup"><span data-stu-id="de74d-287">Select **All** to remove the filters and see all resources again.</span></span>  
    
<span data-ttu-id="de74d-288">请参阅 [筛选请求][DevtoolsNetworkReferenceFilter] 以获取其他筛选工作流。</span><span class="sxs-lookup"><span data-stu-id="de74d-288">See [Filter requests][DevtoolsNetworkReferenceFilter] for other filtering workflows.</span></span>  

## <span data-ttu-id="de74d-289">阻止请求</span><span class="sxs-lookup"><span data-stu-id="de74d-289">Block requests</span></span>   

<span data-ttu-id="de74d-290">当某些页面资源不可用时，页面的外观和行为</span><span class="sxs-lookup"><span data-stu-id="de74d-290">How does a page look and behave when some of the page resources are not available?</span></span>  <span data-ttu-id="de74d-291">它是否完全失败，或者是否仍有运行？</span><span class="sxs-lookup"><span data-stu-id="de74d-291">Does it fail completely, or is it still somewhat functional?</span></span>  <span data-ttu-id="de74d-292">阻止请求以查明：</span><span class="sxs-lookup"><span data-stu-id="de74d-292">Block requests to find out:</span></span>  

1.  <span data-ttu-id="de74d-293">按 `Control` + `Shift` + `P` \ (Windows \ ) 或 `Command` + `Shift` + `P` \ (macOS \ ) 打开 "**命令" 菜单**。</span><span class="sxs-lookup"><span data-stu-id="de74d-293">Press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the **Command Menu**.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-cli-empty.msft.png" alt-text="命令菜单" lightbox="../media/network-glitch-network-cli-empty.msft.png":::
       <span data-ttu-id="de74d-295">**命令菜单**</span><span class="sxs-lookup"><span data-stu-id="de74d-295">The **Command Menu**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="de74d-296">键入 `block` ，选择 " **显示请求阻止**"，然后按 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="de74d-296">Type `block`, select **Show Request Blocking**, and press `Enter`.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-cli-block.msft.png" alt-text="显示请求阻止" lightbox="../media/network-glitch-network-cli-block.msft.png":::
       **<span data-ttu-id="de74d-298">显示请求阻止</span><span class="sxs-lookup"><span data-stu-id="de74d-298">Show Request Blocking</span></span>**  
    :::image-end:::  
    
1.  <span data-ttu-id="de74d-299">选择 " **添加模式** \ (![ 添加模式 ][ImageAddIcon] \ ) "。</span><span class="sxs-lookup"><span data-stu-id="de74d-299">Select **Add Pattern** \(![Add Pattern][ImageAddIcon]\).</span></span>  
1.  <span data-ttu-id="de74d-300">键入 `main.css`。</span><span class="sxs-lookup"><span data-stu-id="de74d-300">Type `main.css`.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-cli-block-add-pattern.msft.png" alt-text="阻止主 css" lightbox="../media/network-glitch-network-cli-block-add-pattern.msft.png":::
       <span data-ttu-id="de74d-302">阻止</span><span class="sxs-lookup"><span data-stu-id="de74d-302">Blocking</span></span> `main.css`  
    :::image-end:::  
    
1.  <span data-ttu-id="de74d-303">选择**添加**。</span><span class="sxs-lookup"><span data-stu-id="de74d-303">Select **Add**.</span></span>  
1.  <span data-ttu-id="de74d-304">重新加载页面。</span><span class="sxs-lookup"><span data-stu-id="de74d-304">Reload the page.</span></span>  <span data-ttu-id="de74d-305">正常情况下，页面的样式会略微 messed，因为主样式表已被阻止。</span><span class="sxs-lookup"><span data-stu-id="de74d-305">As expected, the styling of the page is slightly messed up because the main stylesheet has been blocked.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="de74d-306">`main.css`网络日志中的行。</span><span class="sxs-lookup"><span data-stu-id="de74d-306">The `main.css` row in the Network Log.</span></span>  <span data-ttu-id="de74d-307">红色文本表示资源已被阻止。</span><span class="sxs-lookup"><span data-stu-id="de74d-307">The red text means that the resource was blocked.</span></span>
    
    :::image type="complex" source="../media/network-glitch-network-cli-block-main-css.msft.png" alt-text="已阻止主 .css" lightbox="../media/network-glitch-network-cli-block-main-css.msft.png":::
       `main.css` <span data-ttu-id="de74d-309">已被阻止</span><span class="sxs-lookup"><span data-stu-id="de74d-309">has been blocked</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="de74d-310">取消选中 " **启用请求阻止** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="de74d-310">Deselect the **Enable request blocking** checkbox.</span></span>  

## <span data-ttu-id="de74d-311">总结</span><span class="sxs-lookup"><span data-stu-id="de74d-311">Conclusion</span></span>  

<span data-ttu-id="de74d-312">恭喜，你已完成教程。</span><span class="sxs-lookup"><span data-stu-id="de74d-312">Congratulations, you have completed the tutorial.</span></span>  <span data-ttu-id="de74d-313">您现在知道如何在 Microsoft Edge DevTools 中使用 " **网络** " 面板！</span><span class="sxs-lookup"><span data-stu-id="de74d-313">You now know how to use the **Network** panel in the Microsoft Edge DevTools!</span></span>

<!--




-->  

<span data-ttu-id="de74d-314">查看 [网络参考][DevtoolsNetworkReference] 以发现更多与检查网络活动相关的 DevTools 功能。</span><span class="sxs-lookup"><span data-stu-id="de74d-314">Check out the [Network Reference][DevtoolsNetworkReference] to discover more DevTools features related to inspecting network activity.</span></span>  

<!--  
 


-->  

<!-- image links -->  

[ImageAddIcon]: ../media/add-icon.msft.png  
[ImageCloseIcon]: ../media/close-icon.msft.png  
[ImageFilterIcon]: ../media/filter-icon.msft.png  
[ImageFormatIcon]: ../media/format-icon.msft.png  
[ImageRefreshIcon]: ../media/refresh-icon.msft.png  
[ImageScreenshotsIcon]: ../media/screenshots-icon.msft.png  
[ImageSearchIcon]: ../media/search-icon.msft.png  
[ImageSettingsIcon]: ../media/settings-icon.msft.png

<!-- links -->  

<!--[CachePolicies]: ../../../web/tools/lighthouse/audits/cache-policy ""  -->  

[DevToolsCustomizePlacement]: ../customize/placement.md "更改 Microsoft Edge DevTools 位置 |Microsoft 文档"  
[DevtoolsNetworkReference]: ./reference.md "网络分析参考 |Microsoft 文档"
[DevtoolsNetworkReferenceFilter]: ./reference.md#filter-requests "筛选请求-网络分析参考 |Microsoft 文档"  
[DevtoolsReferenceHideOverview]: ./reference.md#hide-the-overview-pane "隐藏 "概述" 窗格-网络分析参考 |Microsoft 文档"
[DevtoolsReferenceProperty]: ./reference.md#filter-requests-by-properties "按属性筛选请求-网络分析参考 |Microsoft 文档"
[DevToolsOpen]: ../open.md "打开 Microsoft Edge DevTools |Microsoft 文档"  
[DevtoolsSpeedGetStarted]: ../speed/get-started.md "通过 Microsoft Edge DevTools 优化网站速度 |Microsoft 文档"  

[GlitchNetworkGetStarted]: https://microsoft-edge-chromium-devtools.glitch.me/static/network/getstarted.html "检查网络活动演示 |故障"  

[MDNHTTPCache]: https://developer.mozilla.org/docs/Web/HTTP/Caching "HTTP 缓存 |MDN"  

> [!NOTE]
> <span data-ttu-id="de74d-324">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="de74d-324">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="de74d-325">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/network/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="de74d-325">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/network/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="de74d-327">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="de74d-327">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
