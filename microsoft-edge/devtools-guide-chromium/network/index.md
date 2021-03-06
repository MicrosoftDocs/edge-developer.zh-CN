---
description: 有关 Microsoft Edge DevTools 中最受欢迎的网络相关功能的教程。
title: 检查 Microsoft Edge DevTools 中的网络活动
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 16b60716c91d2f4ce778f1fac37afc0e73e30ab6
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398656"
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

# <a name="inspect-network-activity-in-microsoft-edge-devtools"></a><span data-ttu-id="8feda-104">检查 Microsoft Edge DevTools 中的网络活动</span><span class="sxs-lookup"><span data-stu-id="8feda-104">Inspect network activity in Microsoft Edge DevTools</span></span>  

<span data-ttu-id="8feda-105">这是一个动手教程，介绍了一些最常用的 DevTools 功能，这些功能与检查页面的网络活动相关。</span><span class="sxs-lookup"><span data-stu-id="8feda-105">This is a hands-on tutorial of some of the most commonly-used DevTools features related to inspecting network activity for a page.</span></span>  

<span data-ttu-id="8feda-106">如果要浏览功能，请导航到"[网络参考"。][DevtoolsNetworkReference]</span><span class="sxs-lookup"><span data-stu-id="8feda-106">If you want to browse features, navigate to [Network Reference][DevtoolsNetworkReference].</span></span>  

<!--TODO: This entire section needs a Microsoft Edge DevTools re-write  -->

<!-- Read on, or watch the video version of this tutorial:  -->  

<!--
> [!VIDEO embed/e1gAyQuIFQo]  
-->

## <a name="when-to-use-the-network-panel"></a><span data-ttu-id="8feda-107">何时使用网络面板</span><span class="sxs-lookup"><span data-stu-id="8feda-107">When to use the Network panel</span></span>  

<span data-ttu-id="8feda-108">一般情况下，当您需要确保资源正在下载或上传时，请使用网络面板。</span><span class="sxs-lookup"><span data-stu-id="8feda-108">In general, use the Network panel when you need to make sure that resources are being downloaded or uploaded as expected.</span></span>  <span data-ttu-id="8feda-109">网络面板的最常见用例包括：</span><span class="sxs-lookup"><span data-stu-id="8feda-109">The most common use cases for the Network panel are:</span></span>  

*   <span data-ttu-id="8feda-110">确保资源上载或下载实际正在进行。</span><span class="sxs-lookup"><span data-stu-id="8feda-110">Making sure that resources are actually being uploaded or downloaded at all.</span></span>  
*   <span data-ttu-id="8feda-111">检查单个资源的属性，如 HTTP 标头、内容、大小等。</span><span class="sxs-lookup"><span data-stu-id="8feda-111">Inspecting the properties of an individual resource, such as the HTTP headers, content, size, and so on.</span></span>  
    
<span data-ttu-id="8feda-112">如果要寻找提高页面加载性能的方法，**请不要从网络\*\*\*\*工具**开始。</span><span class="sxs-lookup"><span data-stu-id="8feda-112">If you are looking for ways to improve page load performance, **do not** start with the **Network** tool.</span></span>  <span data-ttu-id="8feda-113">有许多类型的负载性能问题与网络活动不相关。</span><span class="sxs-lookup"><span data-stu-id="8feda-113">There are many types of load performance issues that are not related to network activity.</span></span>  <span data-ttu-id="8feda-114">从“审核”面板开始，因为它为你提供了有关改进页面的目标建议。</span><span class="sxs-lookup"><span data-stu-id="8feda-114">Start with the Audits panel because it gives you targeted suggestions on how to improve your page.</span></span>  <span data-ttu-id="8feda-115">导航到["优化网站速度"。][DevtoolsSpeedGetStarted]</span><span class="sxs-lookup"><span data-stu-id="8feda-115">Navigate to [Optimize Website Speed][DevtoolsSpeedGetStarted].</span></span>  

## <a name="open-the-network-panel"></a><span data-ttu-id="8feda-116">打开“网络”面板</span><span class="sxs-lookup"><span data-stu-id="8feda-116">Open the Network panel</span></span>  

<span data-ttu-id="8feda-117">若要在本教程中取得最大功能，请打开演示并试用演示页面上的功能。</span><span class="sxs-lookup"><span data-stu-id="8feda-117">To get the most out of this tutorial, open up the demo and try out the features on the demo page.</span></span>  

1.  <span data-ttu-id="8feda-118">打开 “[入门][GlitchNetworkGetStarted]”演示。</span><span class="sxs-lookup"><span data-stu-id="8feda-118">Open the [Get Started Demo][GlitchNetworkGetStarted].</span></span>  
    
    :::image type="complex" source="../media/network-glitch-inspect-network-activity-demo.msft.png" alt-text="演示" lightbox="../media/network-glitch-inspect-network-activity-demo.msft.png":::
       <span data-ttu-id="8feda-120">演示</span><span class="sxs-lookup"><span data-stu-id="8feda-120">The demo</span></span>  
    :::image-end:::  
    
    <!--You may prefer to move the demo to a separate window.  -->  
    
    <!--
    :::image type="complex" source="../media/network-tutorial/windows.msft.png" alt-text="The demo in one window and this tutorial in a different window" lightbox="../media/network-tutorial/windows.msft.png":::
       The demo in one window and this tutorial in a different window  
    :::image-end:::  
    -->
    
1.  <span data-ttu-id="8feda-121">若要[打开 DevTools，][DevToolsOpen]请选择 `Control` + `Shift` + `J` \ (Windows、Linux\) 或 `Command` + `Option` + `J` \ (macOS\) 。</span><span class="sxs-lookup"><span data-stu-id="8feda-121">To [Open DevTools][DevToolsOpen], select `Control`+`Shift`+`J` \(Windows, Linux\) or `Command`+`Option`+`J` \(macOS\).</span></span>  <span data-ttu-id="8feda-122">将 **打开控制台** 工具。</span><span class="sxs-lookup"><span data-stu-id="8feda-122">The **Console** tool opens.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-console.msft.png" alt-text="控制台" lightbox="../media/network-glitch-console.msft.png":::
       <span data-ttu-id="8feda-124">**控制台**</span><span class="sxs-lookup"><span data-stu-id="8feda-124">The **Console**</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="8feda-125">你可能更喜欢将 [DevTools 停靠到窗口底部][DevToolsCustomizePlacement]。</span><span class="sxs-lookup"><span data-stu-id="8feda-125">You may prefer to [dock DevTools to the bottom of your window][DevToolsCustomizePlacement].</span></span>  
    
    :::image type="complex" source="../media/network-glitch-console-bottom.msft.png" alt-text="停靠在窗口底部的 DevTools" lightbox="../media/network-glitch-console-bottom.msft.png":::
       <span data-ttu-id="8feda-127">停靠在窗口底部的 DevTools</span><span class="sxs-lookup"><span data-stu-id="8feda-127">DevTools docked to the bottom of the window</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="8feda-128">打开 **"网络"** 工具。</span><span class="sxs-lookup"><span data-stu-id="8feda-128">Open the **Network** tool.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-bottom.msft.png" alt-text="固定到窗口底部的 DevTools 中的控制台工具" lightbox="../media/network-glitch-network-bottom.msft.png":::
       <span data-ttu-id="8feda-130">固定到窗口底部的 DevTools 中的**控制台**工具</span><span class="sxs-lookup"><span data-stu-id="8feda-130">**Console** tool in the DevTools docked to the bottom of the window</span></span>  
    :::image-end:::  
    
<span data-ttu-id="8feda-131">现在， **网络** 工具为空。</span><span class="sxs-lookup"><span data-stu-id="8feda-131">Right now the **Network** tool is empty.</span></span>  <span data-ttu-id="8feda-132">DevTools 仅在打开网络活动后记录网络活动，自打开 DevTools 后未发生网络活动。</span><span class="sxs-lookup"><span data-stu-id="8feda-132">DevTools only logs network activity after you open it and no network activity has occurred since you opened DevTools.</span></span>  

## <a name="log-network-activity"></a><span data-ttu-id="8feda-133">记录网络活动</span><span class="sxs-lookup"><span data-stu-id="8feda-133">Log network activity</span></span>  

<span data-ttu-id="8feda-134">查看页面导致的网络活动：</span><span class="sxs-lookup"><span data-stu-id="8feda-134">To view the network activity that a page causes:</span></span>  

1.  <span data-ttu-id="8feda-135">刷新网页。</span><span class="sxs-lookup"><span data-stu-id="8feda-135">Refresh the webpage.</span></span>  <span data-ttu-id="8feda-136">网络面板在**网络日志**中记录所有网络活动。</span><span class="sxs-lookup"><span data-stu-id="8feda-136">The Network panel logs all network activity in the **Network Log**.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network.msft.png" alt-text="网络日志" lightbox="../media/network-glitch-network.msft.png":::
       <span data-ttu-id="8feda-138">**网络日志**</span><span class="sxs-lookup"><span data-stu-id="8feda-138">The **Network Log**</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="8feda-139">**网络日志**的每一行表示一个资源。</span><span class="sxs-lookup"><span data-stu-id="8feda-139">Each row of the **Network Log** represents a resource.</span></span>  <span data-ttu-id="8feda-140">默认情况下，按时间顺序列出资源。</span><span class="sxs-lookup"><span data-stu-id="8feda-140">By default the resources are listed chronologically.</span></span>  <span data-ttu-id="8feda-141">顶部资源通常是主 HTML 文档。</span><span class="sxs-lookup"><span data-stu-id="8feda-141">The top resource is usually the main HTML document.</span></span>  <span data-ttu-id="8feda-142">底部资源是最后请求的任何资源。</span><span class="sxs-lookup"><span data-stu-id="8feda-142">The bottom resource is whatever was requested last.</span></span>  
    
    <span data-ttu-id="8feda-143">每个列表示有关资源的信息。</span><span class="sxs-lookup"><span data-stu-id="8feda-143">Each column represents information about a resource.</span></span>  <span data-ttu-id="8feda-144">在上图中，将显示默认列。</span><span class="sxs-lookup"><span data-stu-id="8feda-144">In the previous figure the default columns are displayed.</span></span>  

    *   <span data-ttu-id="8feda-145">**状态**。</span><span class="sxs-lookup"><span data-stu-id="8feda-145">**Status**.</span></span>  <span data-ttu-id="8feda-146">响应的 HTTP 状态代码。</span><span class="sxs-lookup"><span data-stu-id="8feda-146">The HTTP status code for response.</span></span>  
    *   <span data-ttu-id="8feda-147">**类型**。</span><span class="sxs-lookup"><span data-stu-id="8feda-147">**Type**.</span></span>  <span data-ttu-id="8feda-148">资源类型。</span><span class="sxs-lookup"><span data-stu-id="8feda-148">The resource type.</span></span>  
    *   <span data-ttu-id="8feda-149">**发起程序**。</span><span class="sxs-lookup"><span data-stu-id="8feda-149">**Initiator**.</span></span>  <span data-ttu-id="8feda-150">资源请求的原因。</span><span class="sxs-lookup"><span data-stu-id="8feda-150">The cause of the resource request.</span></span>  <span data-ttu-id="8feda-151">CHoosing a link in the Initiator column takes you to the source code thatcaused the request.</span><span class="sxs-lookup"><span data-stu-id="8feda-151">CHoosing a link in the Initiator column takes you to the source code that caused the request.</span></span>  
    *   <span data-ttu-id="8feda-152">**时间**。</span><span class="sxs-lookup"><span data-stu-id="8feda-152">**Time**.</span></span>  <span data-ttu-id="8feda-153">请求的持续时间。</span><span class="sxs-lookup"><span data-stu-id="8feda-153">The duration of the request.</span></span>  
    *   <span data-ttu-id="8feda-154">**粘滞键**。</span><span class="sxs-lookup"><span data-stu-id="8feda-154">**Waterfall**.</span></span>  <span data-ttu-id="8feda-155">请求的不同阶段的图形表示形式。</span><span class="sxs-lookup"><span data-stu-id="8feda-155">A graphical representation of the different stages of the request.</span></span>  <span data-ttu-id="8feda-156">若要显示细目，请将鼠标悬停在瀑布上。</span><span class="sxs-lookup"><span data-stu-id="8feda-156">To display a breakdown, hover on a Waterfall.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="8feda-157">网络日志上方的图形称为“概述”。</span><span class="sxs-lookup"><span data-stu-id="8feda-157">The graph above the Network Log is called the Overview.</span></span>  <span data-ttu-id="8feda-158">本教程中不会使用概述图，因此可以隐藏它。</span><span class="sxs-lookup"><span data-stu-id="8feda-158">You will not use the Overview graph in this tutorial, so you may hide it.</span></span>  <span data-ttu-id="8feda-159">导航到 ["隐藏概述"窗格][DevtoolsReferenceHideOverview]。</span><span class="sxs-lookup"><span data-stu-id="8feda-159">Navigate to [Hide the Overview pane][DevtoolsReferenceHideOverview].</span></span>
    
1.  <span data-ttu-id="8feda-160">打开 DevTools 后，它会在网络日志中记录网络活动。</span><span class="sxs-lookup"><span data-stu-id="8feda-160">After you open DevTools, it records network activity in the Network Log.</span></span>  
    <span data-ttu-id="8feda-161">若要演示这一点，请首先查看**网络日志** 的底部，并记下上一次活动。</span><span class="sxs-lookup"><span data-stu-id="8feda-161">To demonstrate this, first look at the bottom of the **Network Log** and make a mental note of the last activity.</span></span>  
1.  <span data-ttu-id="8feda-162">现在，在演示中选择“**获取数据**”按钮。</span><span class="sxs-lookup"><span data-stu-id="8feda-162">Now, select the **Get Data** button in the demo.</span></span>  
1.  <span data-ttu-id="8feda-163">再次查看**网络日志** 的底部。</span><span class="sxs-lookup"><span data-stu-id="8feda-163">Look at the bottom of the **Network Log** again.</span></span>  <span data-ttu-id="8feda-164">将显示一个名为 `getstarted.json` 的新资源。</span><span class="sxs-lookup"><span data-stu-id="8feda-164">A new resource named `getstarted.json` is displayed.</span></span>  <span data-ttu-id="8feda-165">若要使网页请求文件，请选择" **获取数据"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="8feda-165">To cause the webpage to request the file, choose the **Get Data** button.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-new-resource.msft.png" alt-text="网络日志中的新资源" lightbox="../media/network-glitch-network-new-resource.msft.png":::
       <span data-ttu-id="8feda-167">**网络日志**中的新资源</span><span class="sxs-lookup"><span data-stu-id="8feda-167">A new resource in the **Network Log**</span></span>  
    :::image-end:::  
    
## <a name="show-more-information"></a><span data-ttu-id="8feda-168">显示详细信息</span><span class="sxs-lookup"><span data-stu-id="8feda-168">Show more information</span></span>  

<span data-ttu-id="8feda-169">网络日志的列是可配置的。</span><span class="sxs-lookup"><span data-stu-id="8feda-169">The columns of the Network Log are configurable.</span></span>  <span data-ttu-id="8feda-170">您可以隐藏您未使用的列。</span><span class="sxs-lookup"><span data-stu-id="8feda-170">You may hide columns that you are not using.</span></span>  
<span data-ttu-id="8feda-171">默认情况下，还有许多列处于隐藏状态，您可能会发现这些列很有用。</span><span class="sxs-lookup"><span data-stu-id="8feda-171">There are also many columns that are hidden by default which you may find useful.</span></span>  

1.  <span data-ttu-id="8feda-172">将鼠标悬停在网络日志表的标题上，打开上下文菜单 \ (右键单击\) ，然后选择 **"域"。**</span><span class="sxs-lookup"><span data-stu-id="8feda-172">Hover on the header of the Network Log table, open the contextual menu \(right-click\), and choose **Domain**.</span></span>  <span data-ttu-id="8feda-173">现在将显示每个资源的域。</span><span class="sxs-lookup"><span data-stu-id="8feda-173">The domain of each resource is now shown.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-edit-column.msft.png" alt-text="启用“域”列" lightbox="../media/network-glitch-network-edit-column.msft.png":::
       <span data-ttu-id="8feda-175">启用“域”列</span><span class="sxs-lookup"><span data-stu-id="8feda-175">Enable the Domain column</span></span>  
    :::image-end:::  
    
    > [!TIP]
    > <span data-ttu-id="8feda-176">若要查看资源的完整 URL，请将鼠标悬停在"名称"列中 **的** 单元格上。</span><span class="sxs-lookup"><span data-stu-id="8feda-176">To review the full URL of a resource, hover on the cell in the **Name** column.</span></span>  
    
## <a name="simulate-a-slower-network-connection"></a><span data-ttu-id="8feda-177">模拟较慢的网络连接</span><span class="sxs-lookup"><span data-stu-id="8feda-177">Simulate a slower network connection</span></span>  

<span data-ttu-id="8feda-178">用于构建站点的计算机的网络连接可能比用户的移动设备的网络连接速度快。</span><span class="sxs-lookup"><span data-stu-id="8feda-178">The network connection of the computer that you use to build sites is probably faster than the network connections of the mobile devices of your users.</span></span>  <span data-ttu-id="8feda-179">通过限制页面，可以更好地了解页面在移动设备上加载所花的时间。</span><span class="sxs-lookup"><span data-stu-id="8feda-179">By throttling the page, you get a better idea of how long a page takes to load on a mobile device.</span></span>  

1.  <span data-ttu-id="8feda-180">选择 **"限制"** 下拉列表，默认设置为 **"联机** "。</span><span class="sxs-lookup"><span data-stu-id="8feda-180">Choose the **Throttling** dropdown, which is set to **Online** by default.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-throttling.msft.png" alt-text="启用限制" lightbox="../media/network-glitch-network-throttling.msft.png":::
       <span data-ttu-id="8feda-182">启用限制</span><span class="sxs-lookup"><span data-stu-id="8feda-182">Enable throttling</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="8feda-183">选择“**慢速 3G**”。</span><span class="sxs-lookup"><span data-stu-id="8feda-183">Choose **Slow 3G**.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-throttling-slow-3g.msft.png" alt-text="选择慢速 3G" lightbox="../media/network-glitch-network-throttling-slow-3g.msft.png":::
       <span data-ttu-id="8feda-185">选择慢速 3G</span><span class="sxs-lookup"><span data-stu-id="8feda-185">Choose Slow 3G</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="8feda-186">长按**Reload** \(![Reload][ImageRefreshIcon]\) ，然后选择“**空缓存和硬重新加载**”。</span><span class="sxs-lookup"><span data-stu-id="8feda-186">Long-press **Reload** \(![Reload][ImageRefreshIcon]\) and then choose **Empty Cache And Hard Reload**.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-empty-cache-and-hard-reset.msft.png" alt-text="空缓存和硬重新加载" lightbox="../media/network-glitch-empty-cache-and-hard-reset.msft.png":::
       **<span data-ttu-id="8feda-188">空缓存和硬重新加载</span><span class="sxs-lookup"><span data-stu-id="8feda-188">Empty Cache And Hard Reload</span></span>**  
    :::image-end:::  
    
    <span data-ttu-id="8feda-189">在重复访问时，浏览器通常会从[缓存][MDNHTTPCache]中提供一些文件，从而加快页面加载速度。</span><span class="sxs-lookup"><span data-stu-id="8feda-189">On repeat visits, the browser usually serves some files from the [cache][MDNHTTPCache], which speeds up the page load.</span></span>  <span data-ttu-id="8feda-190">**空缓存和硬重新加载** 会强制浏览器访问所有资源的网络。</span><span class="sxs-lookup"><span data-stu-id="8feda-190">**Empty Cache And Hard Reload** forces the browser to go the network for all resources.</span></span>  <span data-ttu-id="8feda-191">使用它来显示第一次访问者如何体验页面加载。</span><span class="sxs-lookup"><span data-stu-id="8feda-191">Use it to display how a first-time visitor experiences a page load.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="8feda-192">**空缓存和硬重新加载**工作流仅在 DevTools 打开时可用。</span><span class="sxs-lookup"><span data-stu-id="8feda-192">The **Empty Cache And Hard Reload** workflow is only available when DevTools is open.</span></span>  
    
## <a name="capture-screenshots"></a><span data-ttu-id="8feda-193">捕获屏幕截图</span><span class="sxs-lookup"><span data-stu-id="8feda-193">Capture screenshots</span></span>  

<span data-ttu-id="8feda-194">屏幕截图显示网页在加载时的外观。</span><span class="sxs-lookup"><span data-stu-id="8feda-194">Screenshots display how a webpage looks over time while it loads.</span></span>  

1.  <span data-ttu-id="8feda-195">Choose \ (![ Network settings ][ImageSettingsIcon] \) and turn on the Capture **screenshots** checkbox.</span><span class="sxs-lookup"><span data-stu-id="8feda-195">Choose \(![Network settings][ImageSettingsIcon]\) and turn on the **Capture screenshots** checkbox.</span></span>
1.  <span data-ttu-id="8feda-196">使用空缓存和 **硬重新加载工作流再次刷新** 页面。</span><span class="sxs-lookup"><span data-stu-id="8feda-196">Refresh the page again using the **Empty Cache And Hard Reload** workflow.</span></span>  <span data-ttu-id="8feda-197">如果需要 [有关操作方式](#simulate-a-slower-network-connection) 的提醒，请导航到"模拟较慢的连接"。</span><span class="sxs-lookup"><span data-stu-id="8feda-197">Navigate to [Simulate a slower connection](#simulate-a-slower-network-connection) if you need a reminder on how to do this.</span></span>  
    <span data-ttu-id="8feda-198">"屏幕截图"面板提供了页面在加载过程中查看各个点的缩略图。</span><span class="sxs-lookup"><span data-stu-id="8feda-198">The Screenshots panel provides thumbnails of how the page looked at various points during the loading process.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-screenshots.msft.png" alt-text="页面加载的屏幕截图" lightbox="../media/network-glitch-network-screenshots.msft.png":::
       <span data-ttu-id="8feda-200">页面加载的屏幕截图</span><span class="sxs-lookup"><span data-stu-id="8feda-200">Screenshots of the page load</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="8feda-201">选择第一个缩略图。</span><span class="sxs-lookup"><span data-stu-id="8feda-201">Choose the first thumbnail.</span></span>  <span data-ttu-id="8feda-202">DevTools 显示当时发生的网络活动。</span><span class="sxs-lookup"><span data-stu-id="8feda-202">DevTools shows you what network activity was occurring at that moment in time.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-screenshots-first.msft.png" alt-text="第一张屏幕截图期间发生的网络活动" lightbox="../media/network-glitch-network-screenshots-first.msft.png":::
       <span data-ttu-id="8feda-204">第一张屏幕截图期间发生的网络活动</span><span class="sxs-lookup"><span data-stu-id="8feda-204">The network activity that was happening during the first screenshot</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="8feda-205">Choose \ (![ Network settings ][ImageSettingsIcon] \) and turn off the **Capture screenshots** checkbox to close the Screenshots pane.</span><span class="sxs-lookup"><span data-stu-id="8feda-205">Choose \(![Network settings][ImageSettingsIcon]\) again and turn off the **Capture screenshots** checkbox to close the Screenshots pane.</span></span>
1.  <span data-ttu-id="8feda-206">再次刷新页面。</span><span class="sxs-lookup"><span data-stu-id="8feda-206">Refresh the page again.</span></span>  
    
## <a name="inspect-the-details-of-the-resource"></a><span data-ttu-id="8feda-207">检查资源的详细信息</span><span class="sxs-lookup"><span data-stu-id="8feda-207">Inspect the details of the resource</span></span>  

<span data-ttu-id="8feda-208">选择资源以了解有关它的信息。</span><span class="sxs-lookup"><span data-stu-id="8feda-208">Choose a resource to learn more information about it.</span></span>  <span data-ttu-id="8feda-209">立即尝试：</span><span class="sxs-lookup"><span data-stu-id="8feda-209">Try it now:</span></span>  

1.  <span data-ttu-id="8feda-210">选择 `getstarted.html` 。</span><span class="sxs-lookup"><span data-stu-id="8feda-210">Choose `getstarted.html`.</span></span>  <span data-ttu-id="8feda-211">将显示 **"标题** "面板。</span><span class="sxs-lookup"><span data-stu-id="8feda-211">The **Headers** panel is shown.</span></span>  <span data-ttu-id="8feda-212">使用此面板检查 HTTP 标头。</span><span class="sxs-lookup"><span data-stu-id="8feda-212">Use this panel to inspect HTTP headers.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-resources-headers.msft.png" alt-text=""标题"面板" lightbox="../media/network-glitch-network-resources-headers.msft.png":::
       <span data-ttu-id="8feda-214">" **标题"** 面板</span><span class="sxs-lookup"><span data-stu-id="8feda-214">The **Headers** panel</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="8feda-215">选择 **"预览"** 面板。</span><span class="sxs-lookup"><span data-stu-id="8feda-215">Choose the **Preview** panel.</span></span>  <span data-ttu-id="8feda-216">显示 HTML 的基本呈现。</span><span class="sxs-lookup"><span data-stu-id="8feda-216">A basic rendering of the HTML is shown.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-resources-preview.msft.png" alt-text=""预览"面板" lightbox="../media/network-glitch-network-resources-preview.msft.png":::
       <span data-ttu-id="8feda-218">" **预览"** 面板</span><span class="sxs-lookup"><span data-stu-id="8feda-218">The **Preview** panel</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="8feda-219">当 API 以 HTML 格式返回错误代码时，面板非常有用。</span><span class="sxs-lookup"><span data-stu-id="8feda-219">The panel is helpful when an API returns an error code in HTML.</span></span>  <span data-ttu-id="8feda-220">您可能会发现，读取呈现的 HTML 比 HTML 源代码更容易，在检查图像时也更容易阅读。</span><span class="sxs-lookup"><span data-stu-id="8feda-220">You may find it easier to read the rendered HTML than the HTML source code, or when you inspect images.</span></span>  

1.  <span data-ttu-id="8feda-221">选择 **"响应"** 面板。</span><span class="sxs-lookup"><span data-stu-id="8feda-221">Choose the **Response** panel.</span></span>  <span data-ttu-id="8feda-222">将显示 HTML 源代码。</span><span class="sxs-lookup"><span data-stu-id="8feda-222">The HTML source code is shown.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-resources-response.msft.png" alt-text="响应面板" lightbox="../media/network-glitch-network-resources-response.msft.png":::
       <span data-ttu-id="8feda-224">响应**面板**</span><span class="sxs-lookup"><span data-stu-id="8feda-224">The **Response** panel</span></span>  
    :::image-end:::  
    
    > [!TIP]
    > <span data-ttu-id="8feda-225">缩小文件时，选择响应面板底部的"格式**\ (** ![ 格式 ][ImageFormatIcon] \) "\*\*\*\* 按钮，以重新格式化文件内容，实现可读性。</span><span class="sxs-lookup"><span data-stu-id="8feda-225">When a file is minified, choose the **Format** \(![Format][ImageFormatIcon]\) button at the bottom of the **Response** panel to re-format the contents of the file for readability.</span></span>  
    
1.  <span data-ttu-id="8feda-226">选择 **"计时"** 面板。</span><span class="sxs-lookup"><span data-stu-id="8feda-226">Choose the **Timing** panel.</span></span>  <span data-ttu-id="8feda-227">将显示资源的网络活动细目。</span><span class="sxs-lookup"><span data-stu-id="8feda-227">A breakdown of the network activity for the resource is displayed.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-resources-timing.msft.png" alt-text="计时面板" lightbox="../media/network-glitch-network-resources-timing.msft.png":::
       <span data-ttu-id="8feda-229">计时**面板**</span><span class="sxs-lookup"><span data-stu-id="8feda-229">The **Timing** panel</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="8feda-230">选择**关闭** \(![关闭][ImageCloseIcon]\)以再次查看网络日志。</span><span class="sxs-lookup"><span data-stu-id="8feda-230">Choose **Close** \(![Close][ImageCloseIcon]\) to view the Network Log again.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-resources-close-tabs.msft.png" alt-text="关闭按钮" lightbox="../media/network-glitch-network-resources-close-tabs.msft.png":::
       <span data-ttu-id="8feda-232">“**关闭**”按钮</span><span class="sxs-lookup"><span data-stu-id="8feda-232">The **Close** button</span></span>  
    :::image-end:::  
    
## <a name="search-network-headers-and-responses"></a><span data-ttu-id="8feda-233">搜索网络标头和响应</span><span class="sxs-lookup"><span data-stu-id="8feda-233">Search network headers and responses</span></span>  

<span data-ttu-id="8feda-234">当您需要搜索特定字符串或正则表达式的所有资源的 HTTP 标头和响应时，请使用“**搜索**”窗格。</span><span class="sxs-lookup"><span data-stu-id="8feda-234">Use the **Search** pane when you need to search the HTTP headers and responses of all resources for a certain string or regular expression.</span></span>  

<span data-ttu-id="8feda-235">例如，假设你想要验证你的资源是否使用了合理的**缓存策略**。</span><span class="sxs-lookup"><span data-stu-id="8feda-235">For example, suppose you want to verify that your resources are using reasonable **cache policies**.</span></span>  

<!--TODO: add cache policies section when available  -->

1.  <span data-ttu-id="8feda-236">选择**搜索** \(![搜索][ImageSearchIcon]\)。</span><span class="sxs-lookup"><span data-stu-id="8feda-236">Choose **Search** \(![Search][ImageSearchIcon]\).</span></span>  <span data-ttu-id="8feda-237">搜索窗格将打开到网络日志的左侧。</span><span class="sxs-lookup"><span data-stu-id="8feda-237">The Search pane opens to the left of the Network log.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-search-empty.msft.png" alt-text="“搜索”窗格" lightbox="../media/network-glitch-network-search-empty.msft.png":::
       <span data-ttu-id="8feda-239">“**搜索**”窗格</span><span class="sxs-lookup"><span data-stu-id="8feda-239">The **Search** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="8feda-240">键入 `Cache-Control` 并选择 `Enter`。</span><span class="sxs-lookup"><span data-stu-id="8feda-240">Type `Cache-Control` and select `Enter`.</span></span>  <span data-ttu-id="8feda-241">“搜索”窗格列出它在资源标头或内容 `Cache-Control` 中查找到的所有实例。</span><span class="sxs-lookup"><span data-stu-id="8feda-241">The Search pane lists all instances of `Cache-Control` that it finds in resource headers or content.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-search-cache-control.msft.png" alt-text="搜索的 Cache-Control" lightbox="../media/network-glitch-network-search-cache-control.msft.png":::
       <span data-ttu-id="8feda-243">以下项的搜索结果</span><span class="sxs-lookup"><span data-stu-id="8feda-243">Search results for</span></span> `Cache-Control`  
    :::image-end:::  
    
1.  <span data-ttu-id="8feda-244">选择一个结果以查看找到结果的资源。</span><span class="sxs-lookup"><span data-stu-id="8feda-244">Choose a result to view the resource in which the result was found.</span></span>  <span data-ttu-id="8feda-245">如果要查看资源的详细信息，请选择直接转到它的结果。</span><span class="sxs-lookup"><span data-stu-id="8feda-245">If you are looking at the details of the resource, select a result to go directly to it.</span></span>  <span data-ttu-id="8feda-246">例如，如果在标头中找到了该查询，则 **"标题"** 面板将打开。</span><span class="sxs-lookup"><span data-stu-id="8feda-246">For example, if the query was found in a header, the **Headers** panel opens.</span></span>   <span data-ttu-id="8feda-247">如果在内容中找到了查询，则" **响应"** 面板将打开。</span><span class="sxs-lookup"><span data-stu-id="8feda-247">If the query was found in content, the **Response** panel opens.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-search-cache-control-headers-response-headers.msft.png" alt-text="在"标题"面板中突出显示的搜索结果" lightbox="../media/network-glitch-network-search-cache-control-headers-response-headers.msft.png":::
       <span data-ttu-id="8feda-249">在"标题"面板 **中突出显示的** 搜索结果</span><span class="sxs-lookup"><span data-stu-id="8feda-249">A search result highlighted in the **Headers** panel</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="8feda-250">关闭"搜索"窗格和 **"标题"** 面板。</span><span class="sxs-lookup"><span data-stu-id="8feda-250">Close the Search pane and the **Headers** panel.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-search-close.msft.png" alt-text="关闭按钮" lightbox="../media/network-glitch-network-search-close.msft.png":::
       <span data-ttu-id="8feda-252">**关闭**按钮</span><span class="sxs-lookup"><span data-stu-id="8feda-252">The **Close** buttons</span></span>  
    :::image-end:::  
    
## <a name="filter-resources"></a><span data-ttu-id="8feda-253">筛选资源</span><span class="sxs-lookup"><span data-stu-id="8feda-253">Filter resources</span></span>  

<span data-ttu-id="8feda-254">DevTools 提供了许多工作流，用于筛选出与当前任务不相关的资源。</span><span class="sxs-lookup"><span data-stu-id="8feda-254">DevTools provides numerous workflows for filtering out resources that are not relevant to the task at hand.</span></span>  

:::image type="complex" source="../media/network-glitch-network-filter-empty.msft.png" alt-text="“筛选器”工具栏" lightbox="../media/network-glitch-network-filter-empty.msft.png":::
   <span data-ttu-id="8feda-256">“**筛选器**”工具栏</span><span class="sxs-lookup"><span data-stu-id="8feda-256">The **Filters** toolbar</span></span>  
:::image-end:::  

<span data-ttu-id="8feda-257">默认情况下 **，** 筛选器工具栏应打开。</span><span class="sxs-lookup"><span data-stu-id="8feda-257">The **Filters** toolbar should be turned on by default.</span></span>  <span data-ttu-id="8feda-258">如果不是：</span><span class="sxs-lookup"><span data-stu-id="8feda-258">If not:</span></span>  

1.  <span data-ttu-id="8feda-259">选择**筛选器** \(![筛选器][ImageFilterIcon]\)来显示它。</span><span class="sxs-lookup"><span data-stu-id="8feda-259">Choose **Filter** \(![Filter][ImageFilterIcon]\) to show it.</span></span>  
    
### <a name="filter-by-string-regular-expression-or-property"></a><span data-ttu-id="8feda-260">按字符串、正则表达式或属性筛选</span><span class="sxs-lookup"><span data-stu-id="8feda-260">Filter by string, regular expression, or property</span></span>  

<span data-ttu-id="8feda-261">“**筛选器**”文本框支持许多不同类型的筛选。</span><span class="sxs-lookup"><span data-stu-id="8feda-261">The **Filter** text box supports many different types of filtering.</span></span>  

1.  <span data-ttu-id="8feda-262">键入 `png` 到“**筛选器**”文本框。</span><span class="sxs-lookup"><span data-stu-id="8feda-262">Type `png` into the **Filter** text box.</span></span>  <span data-ttu-id="8feda-263">只显示包含文本 `png` 的文件。</span><span class="sxs-lookup"><span data-stu-id="8feda-263">Only the files that contain the text `png` are shown.</span></span>  <span data-ttu-id="8feda-264">在这种情况下，与筛选器匹配的唯一文件是 PNG 图像。</span><span class="sxs-lookup"><span data-stu-id="8feda-264">In this case the only files that match the filter are the PNG images.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-filter-png.msft.png" alt-text="字符串筛选器" lightbox="../media/network-glitch-network-filter-png.msft.png":::
       <span data-ttu-id="8feda-266">字符串筛选器</span><span class="sxs-lookup"><span data-stu-id="8feda-266">A string filter</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="8feda-267">键入 `/.*\.[cj]s+$/`。</span><span class="sxs-lookup"><span data-stu-id="8feda-267">Type `/.*\.[cj]s+$/`.</span></span>  <span data-ttu-id="8feda-268">DevTools 会筛选出文件名不以 `j` 或 `c` 结尾、后跟 1 个或多个 `s` 字符的任何资源。</span><span class="sxs-lookup"><span data-stu-id="8feda-268">DevTools filters out any resource with a filename that does not end with a `j` or a `c` followed by 1 or more `s` characters.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-filter-regex.msft.png" alt-text="正则表达式筛选器" lightbox="../media/network-glitch-network-filter-regex.msft.png":::
       <span data-ttu-id="8feda-270">正则表达式筛选器</span><span class="sxs-lookup"><span data-stu-id="8feda-270">A regular expression filter</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="8feda-271">键入 `-main.css`。</span><span class="sxs-lookup"><span data-stu-id="8feda-271">Type `-main.css`.</span></span>  <span data-ttu-id="8feda-272">DevTools 筛选器出 `main.css`。</span><span class="sxs-lookup"><span data-stu-id="8feda-272">DevTools filters out `main.css`.</span></span>  <span data-ttu-id="8feda-273">如果有任何文件与模式匹配，则还会筛选出 tit。</span><span class="sxs-lookup"><span data-stu-id="8feda-273">If any file matches the pattern, tit is also filtered out.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-filter-negative-statement.msft.png" alt-text="负筛选器" lightbox="../media/network-glitch-network-filter-negative-statement.msft.png":::
       <span data-ttu-id="8feda-275">负筛选器</span><span class="sxs-lookup"><span data-stu-id="8feda-275">A negative filter</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="8feda-276">键入 `domain:cdn.glitch.com` 到“**筛选器**”文本框。</span><span class="sxs-lookup"><span data-stu-id="8feda-276">Type `domain:cdn.glitch.com` into the **Filter** text box.</span></span>  <span data-ttu-id="8feda-277">DevTools 筛选出 URL 不匹配此域的任何资源。</span><span class="sxs-lookup"><span data-stu-id="8feda-277">DevTools filters out any resource with a URL that does not match this domain.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-filter-property-value.msft.png" alt-text="属性筛选器" lightbox="../media/network-glitch-network-filter-property-value.msft.png":::
       <span data-ttu-id="8feda-279">属性筛选器</span><span class="sxs-lookup"><span data-stu-id="8feda-279">A property filter</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="8feda-280">对于可筛选属性的完整列表，导航到 [按属性筛选请求][DevtoolsReferenceProperty]。</span><span class="sxs-lookup"><span data-stu-id="8feda-280">For the full list of filterable properties, navigate to [Filter requests by properties][DevtoolsReferenceProperty].</span></span>  
    
1.  <span data-ttu-id="8feda-281">清除任何文本的“**筛选器**”文本框。</span><span class="sxs-lookup"><span data-stu-id="8feda-281">Clear the **Filter** text box of any text.</span></span>  
    
### <a name="filter-by-resource-type"></a><span data-ttu-id="8feda-282">按资源类型筛选</span><span class="sxs-lookup"><span data-stu-id="8feda-282">Filter by resource type</span></span>  

<span data-ttu-id="8feda-283">若要专注于某些类型的文件，如样式表：</span><span class="sxs-lookup"><span data-stu-id="8feda-283">To focus in on a certain type of file, such as stylesheets:</span></span>  

1.  <span data-ttu-id="8feda-284">选择**CSS**。</span><span class="sxs-lookup"><span data-stu-id="8feda-284">Choose **CSS**.</span></span>  <span data-ttu-id="8feda-285">所有其他文件类型都筛选掉。</span><span class="sxs-lookup"><span data-stu-id="8feda-285">All other file types are filtered out.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-filter-file-type-css.msft.png" alt-text="只显示 CSS 文件" lightbox="../media/network-glitch-network-filter-file-type-css.msft.png":::
       <span data-ttu-id="8feda-287">只显示 CSS 文件</span><span class="sxs-lookup"><span data-stu-id="8feda-287">Show CSS files only</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="8feda-288">若要同时显示脚本，请选择并按住 `Control` \ (Windows、Linux\) 或 `Command` \ (macOS\) ，然后选择**JS。**</span><span class="sxs-lookup"><span data-stu-id="8feda-288">To also display scripts, select and hold `Control` \(Windows, Linux\) or `Command` \(macOS\) and then choose **JS**.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-filter-file-type-css-js.msft.png" alt-text="只显示 CSS 和 JS 文件" lightbox="../media/network-glitch-network-filter-file-type-css-js.msft.png":::
       <span data-ttu-id="8feda-290">只显示 CSS 和 JS 文件</span><span class="sxs-lookup"><span data-stu-id="8feda-290">Show CSS and JS files only</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="8feda-291">若要删除筛选器并再次显示所有资源，请选择"**全部"。**</span><span class="sxs-lookup"><span data-stu-id="8feda-291">To remove the filters and display all resources again, choose **All**.</span></span>  
    
<span data-ttu-id="8feda-292">对于其他筛选工作流，导航到 ["筛选"请求][DevtoolsNetworkReferenceFilter]。</span><span class="sxs-lookup"><span data-stu-id="8feda-292">For other filtering workflows, navigate to [Filter requests][DevtoolsNetworkReferenceFilter].</span></span>  

## <a name="block-requests"></a><span data-ttu-id="8feda-293">阻止请求</span><span class="sxs-lookup"><span data-stu-id="8feda-293">Block requests</span></span>  

<span data-ttu-id="8feda-294">当某些页面资源不可用时，页面的外观和行为如何？</span><span class="sxs-lookup"><span data-stu-id="8feda-294">How does a page look and behave when some of the page resources are not available?</span></span>  <span data-ttu-id="8feda-295">它是完全失败，还是仍有点功能？</span><span class="sxs-lookup"><span data-stu-id="8feda-295">Does it fail completely, or is it still somewhat functional?</span></span>  <span data-ttu-id="8feda-296">阻止查找请求：</span><span class="sxs-lookup"><span data-stu-id="8feda-296">Block requests to find out:</span></span>  

1.  <span data-ttu-id="8feda-297">选择 `Control`+`Shift`+`P` \(Windows、Linux\) 或 `Command`+`Shift`+`P` \(macOS\) 打开**命令菜单**。</span><span class="sxs-lookup"><span data-stu-id="8feda-297">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\) to open the **Command Menu**.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-cli-empty.msft.png" alt-text="命令菜单" lightbox="../media/network-glitch-network-cli-empty.msft.png":::
       <span data-ttu-id="8feda-299">**命令菜单**</span><span class="sxs-lookup"><span data-stu-id="8feda-299">The **Command Menu**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="8feda-300">键入 `block`，选择“**显示请求阻止**”，然后选择 `Enter`。</span><span class="sxs-lookup"><span data-stu-id="8feda-300">Type `block`, choose **Show Request Blocking**, and select `Enter`.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-cli-block.msft.png" alt-text="显示请求阻止" lightbox="../media/network-glitch-network-cli-block.msft.png":::
       **<span data-ttu-id="8feda-302">显示请求阻止</span><span class="sxs-lookup"><span data-stu-id="8feda-302">Show Request Blocking</span></span>**  
    :::image-end:::  
    
1.  <span data-ttu-id="8feda-303">选择 **添加模式** \(![添加模式][ImageAddIcon]\)。</span><span class="sxs-lookup"><span data-stu-id="8feda-303">Choose **Add Pattern** \(![Add Pattern][ImageAddIcon]\).</span></span>  
1.  <span data-ttu-id="8feda-304">键入 `main.css`。</span><span class="sxs-lookup"><span data-stu-id="8feda-304">Type `main.css`.</span></span>  
    
    :::image type="complex" source="../media/network-glitch-network-cli-block-add-pattern.msft.png" alt-text="阻止 main.css" lightbox="../media/network-glitch-network-cli-block-add-pattern.msft.png":::
       <span data-ttu-id="8feda-306">阻止</span><span class="sxs-lookup"><span data-stu-id="8feda-306">Blocking</span></span> `main.css`  
    :::image-end:::  
    
1.  <span data-ttu-id="8feda-307">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="8feda-307">Choose **Add**.</span></span>  
1.  <span data-ttu-id="8feda-308">刷新页面。</span><span class="sxs-lookup"><span data-stu-id="8feda-308">Refresh the page.</span></span>  <span data-ttu-id="8feda-309">与预期一样，页面的样式会稍微混乱，因为主样式表已被阻止。</span><span class="sxs-lookup"><span data-stu-id="8feda-309">As expected, the styling of the page is slightly messed up because the main stylesheet has been blocked.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="8feda-310">网络日志中的 `main.css` 行。</span><span class="sxs-lookup"><span data-stu-id="8feda-310">The `main.css` row in the Network Log.</span></span>  <span data-ttu-id="8feda-311">红色文本表示资源已被阻止。</span><span class="sxs-lookup"><span data-stu-id="8feda-311">The red text means that the resource was blocked.</span></span>
    
    :::image type="complex" source="../media/network-glitch-network-cli-block-main-css.msft.png" alt-text="main.css 已被阻止" lightbox="../media/network-glitch-network-cli-block-main-css.msft.png":::
       `main.css` <span data-ttu-id="8feda-313">已被阻止</span><span class="sxs-lookup"><span data-stu-id="8feda-313">has been blocked</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="8feda-314">取消选中“**启用请求阻止**” 复选框。</span><span class="sxs-lookup"><span data-stu-id="8feda-314">Deselect the **Enable request blocking** checkbox.</span></span>  

## <a name="conclusion"></a><span data-ttu-id="8feda-315">总结</span><span class="sxs-lookup"><span data-stu-id="8feda-315">Conclusion</span></span>  

<span data-ttu-id="8feda-316">恭喜，你已完成本教程。</span><span class="sxs-lookup"><span data-stu-id="8feda-316">Congratulations, you have completed the tutorial.</span></span>  <span data-ttu-id="8feda-317">现在，你已了解如何在\*\*\*\* Microsoft Edge DevTools 中使用网络工具！</span><span class="sxs-lookup"><span data-stu-id="8feda-317">You now know how to use the **Network** tool in the Microsoft Edge DevTools!</span></span>

<span data-ttu-id="8feda-318">导航到“[网络参考][DevtoolsNetworkReference]”以发现与检查网络活动相关的更多 DevTools 功能。</span><span class="sxs-lookup"><span data-stu-id="8feda-318">Navigate to the [Network Reference][DevtoolsNetworkReference] to discover more DevTools features related to inspecting network activity.</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="8feda-319">与 Microsoft Edge 开发人员工具团队联系</span><span class="sxs-lookup"><span data-stu-id="8feda-319">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

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

[DevToolsCustomizePlacement]: ../customize/placement.md "更改 Microsoft Edge DevTools 放置 | Microsoft Docs"  
[DevtoolsNetworkReference]: ./reference.md "网络分析参考 | Microsoft Docs"
[DevtoolsNetworkReferenceFilter]: ./reference.md#filter-requests "筛选器请求 - 网络分析参考 | Microsoft Docs"  
[DevtoolsReferenceHideOverview]: ./reference.md#hide-the-overview-pane "隐藏“概述”窗格 - 网络分析参考 | Microsoft Docs"
[DevtoolsReferenceProperty]: ./reference.md#filter-requests-by-properties "按属性筛选请求 - 网络分析参考 | Microsoft Docs"
[DevToolsOpen]: ../open/index.md "打开 Microsoft Edge DevTools | Microsoft Docs"  
[DevtoolsSpeedGetStarted]: ../speed/get-started.md "使用 Microsoft Edge DevTools 优化网站速度 | Microsoft Docs"  

[GlitchNetworkGetStarted]: https://microsoft-edge-chromium-devtools.glitch.me/static/network/getstarted.html "检查网络活动演示 | 小故障"  

[MDNHTTPCache]: https://developer.mozilla.org/docs/Web/HTTP/Caching "HTTP 缓存 | MDN"  

> [!NOTE]
> <span data-ttu-id="8feda-329">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="8feda-329">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="8feda-330">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/network/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="8feda-330">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/network/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="8feda-332">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="8feda-332">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
