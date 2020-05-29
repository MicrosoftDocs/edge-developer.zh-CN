---
title: 检查 Microsoft Edge DevTools 中的网络活动
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/30/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 267b0113e07085dd565a3ff3437a3fcac2dff9d7
ms.sourcegitcommit: 33663cd7838dddee86228dde469a5e9551bddb02
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/30/2020
ms.locfileid: "10611810"
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





# <span data-ttu-id="1fa10-103">检查 Microsoft Edge DevTools 中的网络活动</span><span class="sxs-lookup"><span data-stu-id="1fa10-103">Inspect Network Activity In Microsoft Edge DevTools</span></span>   



<span data-ttu-id="1fa10-104">这是与检查页面的网络活动相关的一些最常用的 DevTools 功能的实践教程。</span><span class="sxs-lookup"><span data-stu-id="1fa10-104">This is a hands-on tutorial of some of the most commonly-used DevTools features related to inspecting network activity for a page.</span></span>  

<span data-ttu-id="1fa10-105">如果想要浏览功能，请参阅[网络参考][DevtoolsNetworkReference]。</span><span class="sxs-lookup"><span data-stu-id="1fa10-105">See [Network Reference][DevtoolsNetworkReference] if you want to browse features instead.</span></span>  

<!--TODO: This entire section needs a Microsoft Edge DevTools re-write  -->

<!-- Read on, or watch the video version of this tutorial:  -->  

<!--
> [!VIDEO embed/e1gAyQuIFQo]  
-->

## <span data-ttu-id="1fa10-106">何时使用网络面板</span><span class="sxs-lookup"><span data-stu-id="1fa10-106">When to use the Network panel</span></span>   

<span data-ttu-id="1fa10-107">一般情况下，当你需要确保按预期下载或上载资源时，请使用 "网络" 面板。</span><span class="sxs-lookup"><span data-stu-id="1fa10-107">In general, use the Network panel when you need to make sure that resources are being downloaded or uploaded as expected.</span></span>  <span data-ttu-id="1fa10-108">网络面板最常见的使用案例是：</span><span class="sxs-lookup"><span data-stu-id="1fa10-108">The most common use cases for the Network panel are:</span></span>  

*   <span data-ttu-id="1fa10-109">确保实际上载或下载资源。</span><span class="sxs-lookup"><span data-stu-id="1fa10-109">Making sure that resources are actually being uploaded or downloaded at all.</span></span>  
*   <span data-ttu-id="1fa10-110">检查单个资源的属性，例如 HTTP 头、内容、大小等。</span><span class="sxs-lookup"><span data-stu-id="1fa10-110">Inspecting the properties of an individual resource, such as the HTTP headers, content, size, and so on.</span></span>  

<span data-ttu-id="1fa10-111">如果你正在寻找提高页面加载性能的**方法，请不要从**网络面板开始。</span><span class="sxs-lookup"><span data-stu-id="1fa10-111">If you are looking for ways to improve page load performance, **do not** start with the Network panel.</span></span>  <span data-ttu-id="1fa10-112">有许多类型的加载性能问题与网络活动无关。</span><span class="sxs-lookup"><span data-stu-id="1fa10-112">There are many types of load performance issues that are not related to network activity.</span></span>  <span data-ttu-id="1fa10-113">从 "审核" 面板开始，因为它为你提供了有关如何改进页面的目标建议。</span><span class="sxs-lookup"><span data-stu-id="1fa10-113">Start with the Audits panel because it gives you targeted suggestions on how to improve your page.</span></span>  <span data-ttu-id="1fa10-114">请参阅[优化网站速度][DevtoolsSpeedGetStarted]。</span><span class="sxs-lookup"><span data-stu-id="1fa10-114">See [Optimize Website Speed][DevtoolsSpeedGetStarted].</span></span>  

## <span data-ttu-id="1fa10-115">打开 "网络" 面板</span><span class="sxs-lookup"><span data-stu-id="1fa10-115">Open the Network panel</span></span>   

<span data-ttu-id="1fa10-116">若要充分利用本教程，请打开演示，然后尝试使用演示页面上的功能。</span><span class="sxs-lookup"><span data-stu-id="1fa10-116">To get the most out of this tutorial, open up the demo and try out the features on the demo page.</span></span>  

1.  <span data-ttu-id="1fa10-117">打开[入门演示][GlitchNetworkGetStarted]。</span><span class="sxs-lookup"><span data-stu-id="1fa10-117">Open the [Get Started Demo][GlitchNetworkGetStarted] .</span></span>  
    
    > ##### <span data-ttu-id="1fa10-118">图 1</span><span class="sxs-lookup"><span data-stu-id="1fa10-118">Figure 1</span></span>  
    > <span data-ttu-id="1fa10-119">演示</span><span class="sxs-lookup"><span data-stu-id="1fa10-119">The demo</span></span>  
    > ![演示][ImagesTutorialDemo]  
    
    <!--You may prefer to move the demo to a separate window.  -->  
    
    <!--
    > ##### old Figure 2  
    > The demo in one window and this tutorial in a different window  
    > ![The demo in one window and this tutorial in a different window][ImagesTutorialWindows]  -->

1.  <span data-ttu-id="1fa10-121">[Open DevTools][DevToolsOpen]通过按 `Control` + `Shift` + `J` \ （Windows \）或 `Command` + `Option` + `J` \ （macOS \）打开 DevTools。</span><span class="sxs-lookup"><span data-stu-id="1fa10-121">[Open DevTools][DevToolsOpen] by pressing `Control`+`Shift`+`J` \(Windows\) or `Command`+`Option`+`J` \(macOS\).</span></span>  <span data-ttu-id="1fa10-122">此时将打开 "**控制台**" 面板。</span><span class="sxs-lookup"><span data-stu-id="1fa10-122">The **Console** panel opens.</span></span>  
    
    > ##### <span data-ttu-id="1fa10-123">图 2</span><span class="sxs-lookup"><span data-stu-id="1fa10-123">Figure 2</span></span>  
    > <span data-ttu-id="1fa10-124">该控制台</span><span class="sxs-lookup"><span data-stu-id="1fa10-124">The Console</span></span>  
    > <span data-ttu-id="1fa10-125">![控制台][ImagesTutorialConsole]</span><span class="sxs-lookup"><span data-stu-id="1fa10-125">![The Console][ImagesTutorialConsole]</span></span>  
    
    <span data-ttu-id="1fa10-126">您可能希望将[DevTools 停靠在窗口底部][DevToolsCustomizePlacement]。</span><span class="sxs-lookup"><span data-stu-id="1fa10-126">You may prefer to [dock DevTools to the bottom of your window][DevToolsCustomizePlacement].</span></span>  
    
    > ##### <span data-ttu-id="1fa10-127">图 3</span><span class="sxs-lookup"><span data-stu-id="1fa10-127">Figure 3</span></span>  
    > <span data-ttu-id="1fa10-128">DevTools 停靠在窗口底部</span><span class="sxs-lookup"><span data-stu-id="1fa10-128">DevTools docked to the bottom of the window</span></span>  
    > <span data-ttu-id="1fa10-129">![DevTools 停靠在窗口底部][ImagesTutorialDocked]</span><span class="sxs-lookup"><span data-stu-id="1fa10-129">![DevTools docked to the bottom of the window][ImagesTutorialDocked]</span></span>  

1.  <span data-ttu-id="1fa10-130">选择 "**网络**" 选项卡。 "网络" 面板将打开。</span><span class="sxs-lookup"><span data-stu-id="1fa10-130">Select the **Network** tab.  The Network panel opens.</span></span>  
    
    > ##### <span data-ttu-id="1fa10-131">图 4</span><span class="sxs-lookup"><span data-stu-id="1fa10-131">Figure 4</span></span>  
    > <span data-ttu-id="1fa10-132">DevTools 停靠在窗口底部</span><span class="sxs-lookup"><span data-stu-id="1fa10-132">DevTools docked to the bottom of the window</span></span>  
    > <span data-ttu-id="1fa10-133">![DevTools 停靠在窗口底部][ImagesTutorialNetwork]</span><span class="sxs-lookup"><span data-stu-id="1fa10-133">![DevTools docked to the bottom of the window][ImagesTutorialNetwork]</span></span>  

<span data-ttu-id="1fa10-134">现在，网络面板为空。</span><span class="sxs-lookup"><span data-stu-id="1fa10-134">Right now the Network panel is empty.</span></span>  <span data-ttu-id="1fa10-135">DevTools 仅在打开网络活动后记录网络活动，并且自打开 DevTools 后未发生任何网络活动。</span><span class="sxs-lookup"><span data-stu-id="1fa10-135">DevTools only logs network activity after you open it and no network activity has occurred since you opened DevTools.</span></span>  

## <span data-ttu-id="1fa10-136">记录网络活动</span><span class="sxs-lookup"><span data-stu-id="1fa10-136">Log network activity</span></span>   

<span data-ttu-id="1fa10-137">要查看页面导致的网络活动，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="1fa10-137">To view the network activity that a page causes:</span></span>  

1.  <span data-ttu-id="1fa10-138">重新加载页面。</span><span class="sxs-lookup"><span data-stu-id="1fa10-138">Reload the page.</span></span>  <span data-ttu-id="1fa10-139">"网络" 面板将在**网络日志**中记录所有网络活动。</span><span class="sxs-lookup"><span data-stu-id="1fa10-139">The Network panel logs all network activity in the **Network Log**.</span></span>  
    
    > ##### <span data-ttu-id="1fa10-140">图 5</span><span class="sxs-lookup"><span data-stu-id="1fa10-140">Figure 5</span></span>  
    > <span data-ttu-id="1fa10-141">网络日志</span><span class="sxs-lookup"><span data-stu-id="1fa10-141">The Network Log</span></span>  
    > <span data-ttu-id="1fa10-142">![网络日志][ImagesTutorialLog]</span><span class="sxs-lookup"><span data-stu-id="1fa10-142">![The Network Log][ImagesTutorialLog]</span></span>  
    
    <span data-ttu-id="1fa10-143">**网络日志**的每一行表示一个资源。</span><span class="sxs-lookup"><span data-stu-id="1fa10-143">Each row of the **Network Log** represents a resource.</span></span>  <span data-ttu-id="1fa10-144">默认情况下，资源按时间顺序列出。</span><span class="sxs-lookup"><span data-stu-id="1fa10-144">By default the resources are listed chronologically.</span></span>  <span data-ttu-id="1fa10-145">顶部资源通常是主 HTML 文档。</span><span class="sxs-lookup"><span data-stu-id="1fa10-145">The top resource is usually the main HTML document.</span></span>  <span data-ttu-id="1fa10-146">最底层的资源是最后请求的内容。</span><span class="sxs-lookup"><span data-stu-id="1fa10-146">The bottom resource is whatever was requested last.</span></span>  
    
    <span data-ttu-id="1fa10-147">每列表示有关资源的信息。</span><span class="sxs-lookup"><span data-stu-id="1fa10-147">Each column represents information about a resource.</span></span>  <span data-ttu-id="1fa10-148">[**图 6**](#figure-6)显示了默认列：</span><span class="sxs-lookup"><span data-stu-id="1fa10-148">[**Figure 6**](#figure-6) shows the default columns:</span></span>  

    *   <span data-ttu-id="1fa10-149">**状态**。</span><span class="sxs-lookup"><span data-stu-id="1fa10-149">**Status**.</span></span>  <span data-ttu-id="1fa10-150">用于响应的 HTTP 状态代码。</span><span class="sxs-lookup"><span data-stu-id="1fa10-150">The HTTP status code for response.</span></span>  
    *   <span data-ttu-id="1fa10-151">**类型**。</span><span class="sxs-lookup"><span data-stu-id="1fa10-151">**Type**.</span></span>  <span data-ttu-id="1fa10-152">资源类型。</span><span class="sxs-lookup"><span data-stu-id="1fa10-152">The resource type.</span></span>  
    *   <span data-ttu-id="1fa10-153">**启动器**。</span><span class="sxs-lookup"><span data-stu-id="1fa10-153">**Initiator**.</span></span>  <span data-ttu-id="1fa10-154">资源请求的原因。</span><span class="sxs-lookup"><span data-stu-id="1fa10-154">The cause of the resource request.</span></span>  <span data-ttu-id="1fa10-155">选择 "发起方" 列中的链接将转到导致请求的源代码。</span><span class="sxs-lookup"><span data-stu-id="1fa10-155">Selecting a link in the Initiator column takes you to the source code that caused the request.</span></span>  
    *   <span data-ttu-id="1fa10-156">**时间**。</span><span class="sxs-lookup"><span data-stu-id="1fa10-156">**Time**.</span></span>  <span data-ttu-id="1fa10-157">请求的持续时间。</span><span class="sxs-lookup"><span data-stu-id="1fa10-157">The duration of the request.</span></span>  
    *   <span data-ttu-id="1fa10-158">**瀑布**图。</span><span class="sxs-lookup"><span data-stu-id="1fa10-158">**Waterfall**.</span></span>  <span data-ttu-id="1fa10-159">请求的不同阶段的图形表示形式。</span><span class="sxs-lookup"><span data-stu-id="1fa10-159">A graphical representation of the different stages of the request.</span></span>  
        <span data-ttu-id="1fa10-160">将鼠标悬停在瀑布上以查看细目。</span><span class="sxs-lookup"><span data-stu-id="1fa10-160">Hover over a Waterfall to see a breakdown.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="1fa10-161">网络日志上方的图形称为概述。</span><span class="sxs-lookup"><span data-stu-id="1fa10-161">The graph above the Network Log is called the Overview.</span></span>  <span data-ttu-id="1fa10-162">您将不使用本教程中的概述图形，因此您可以将其隐藏。</span><span class="sxs-lookup"><span data-stu-id="1fa10-162">You will not use the Overview graph in this tutorial, so you may hide it.</span></span>  <span data-ttu-id="1fa10-163">请参阅[隐藏概述窗格][DevtoolsReferenceHideOverview]。</span><span class="sxs-lookup"><span data-stu-id="1fa10-163">See [Hide the Overview pane][DevtoolsReferenceHideOverview].</span></span>
        
1.  <span data-ttu-id="1fa10-164">打开 DevTools 后，它将在网络日志中记录网络活动。</span><span class="sxs-lookup"><span data-stu-id="1fa10-164">After you open DevTools, it records network activity in the Network Log.</span></span>  
    <span data-ttu-id="1fa10-165">若要演示此操作，请首先查看**网络日志**的底部，并注意最后一个活动。</span><span class="sxs-lookup"><span data-stu-id="1fa10-165">To demonstrate this, first look at the bottom of the **Network Log** and make a mental note of the last activity.</span></span>  
1.  <span data-ttu-id="1fa10-166">现在，选择演示中的 "**获取数据**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="1fa10-166">Now, select the **Get Data** button in the demo.</span></span>  
1.  <span data-ttu-id="1fa10-167">再次查看**网络日志**的底部。</span><span class="sxs-lookup"><span data-stu-id="1fa10-167">Look at the bottom of the **Network Log** again.</span></span>  <span data-ttu-id="1fa10-168">你应该会看到一个名为 `getstarted.json` 的新资源。</span><span class="sxs-lookup"><span data-stu-id="1fa10-168">You should see a new resource called `getstarted.json`.</span></span>  <span data-ttu-id="1fa10-169">选择 "**获取数据**" 按钮导致页面请求该文件。</span><span class="sxs-lookup"><span data-stu-id="1fa10-169">Selecting the **Get Data** button caused the page to request this file.</span></span>  
    
    > ##### <span data-ttu-id="1fa10-170">图 6</span><span class="sxs-lookup"><span data-stu-id="1fa10-170">Figure 6</span></span>  
    > <span data-ttu-id="1fa10-171">网络日志中的新资源</span><span class="sxs-lookup"><span data-stu-id="1fa10-171">A new resource in the Network Log</span></span>  
    > <span data-ttu-id="1fa10-172">![网络日志中的新资源][ImagesTutorialRuntime]</span><span class="sxs-lookup"><span data-stu-id="1fa10-172">![A new resource in the Network Log][ImagesTutorialRuntime]</span></span>  

## <span data-ttu-id="1fa10-173">显示详细信息</span><span class="sxs-lookup"><span data-stu-id="1fa10-173">Show more information</span></span>   

<span data-ttu-id="1fa10-174">网络日志的列是可配置的。</span><span class="sxs-lookup"><span data-stu-id="1fa10-174">The columns of the Network Log are configurable.</span></span>  <span data-ttu-id="1fa10-175">您可以隐藏未使用的列。</span><span class="sxs-lookup"><span data-stu-id="1fa10-175">You may hide columns that you are not using.</span></span>  
<span data-ttu-id="1fa10-176">默认情况下，在默认情况下会隐藏许多列，您可能会发现这些列很有用。</span><span class="sxs-lookup"><span data-stu-id="1fa10-176">There are also many columns that are hidden by default which you may find useful.</span></span>  

1.  <span data-ttu-id="1fa10-177">右键单击网络日志表的标题，然后选择 "**域**"。</span><span class="sxs-lookup"><span data-stu-id="1fa10-177">Right-click the header of the Network Log table and select **Domain**.</span></span>  <span data-ttu-id="1fa10-178">现在显示了每个资源的域。</span><span class="sxs-lookup"><span data-stu-id="1fa10-178">The domain of each resource is now shown.</span></span>  
    
    > ##### <span data-ttu-id="1fa10-179">图 7</span><span class="sxs-lookup"><span data-stu-id="1fa10-179">Figure 7</span></span>  
    > <span data-ttu-id="1fa10-180">启用 "域" 列</span><span class="sxs-lookup"><span data-stu-id="1fa10-180">Enabling the Domain column</span></span>  
    > <span data-ttu-id="1fa10-181">![启用 "域" 列][ImagesTutorialDomain]</span><span class="sxs-lookup"><span data-stu-id="1fa10-181">![Enabling the Domain column][ImagesTutorialDomain]</span></span>  
    
    > [!TIP]
    > <span data-ttu-id="1fa10-182">通过将鼠标悬停在 "**名称**" 列中的单元格上，查看资源的完整 URL。</span><span class="sxs-lookup"><span data-stu-id="1fa10-182">See the full URL of a resource by hovering over the cell in the **Name** column.</span></span>  

## <span data-ttu-id="1fa10-183">模拟速度较慢的网络连接</span><span class="sxs-lookup"><span data-stu-id="1fa10-183">Simulate a slower network connection</span></span>   

<span data-ttu-id="1fa10-184">用于构建网站的计算机的网络连接可能比用户移动设备的网络连接速度更快。</span><span class="sxs-lookup"><span data-stu-id="1fa10-184">The network connection of the computer that you use to build sites is probably faster than the network connections of the mobile devices of your users.</span></span>  <span data-ttu-id="1fa10-185">通过限制页面，可以更好地了解页面在移动设备上的加载时间。</span><span class="sxs-lookup"><span data-stu-id="1fa10-185">By throttling the page, you get a better idea of how long a page takes to load on a mobile device.</span></span>  

1.  <span data-ttu-id="1fa10-186">选择 "**限制**" 下拉列表，默认设置为 "**联机**"。</span><span class="sxs-lookup"><span data-stu-id="1fa10-186">Select the **Throttling** dropdown, which is set to **Online** by default.</span></span>  
    
    > ##### <span data-ttu-id="1fa10-187">图 8</span><span class="sxs-lookup"><span data-stu-id="1fa10-187">Figure 8</span></span>  
    > <span data-ttu-id="1fa10-188">启用限制</span><span class="sxs-lookup"><span data-stu-id="1fa10-188">Enabling throttling</span></span>  
    > <span data-ttu-id="1fa10-189">![启用带宽限制][ImagesTutorialThrottling]</span><span class="sxs-lookup"><span data-stu-id="1fa10-189">![Enabling throttling][ImagesTutorialThrottling]</span></span>  
    
1.  <span data-ttu-id="1fa10-190">选择 "**慢速 3g**"。</span><span class="sxs-lookup"><span data-stu-id="1fa10-190">Select **Slow 3G**.</span></span>  
    
    > ##### <span data-ttu-id="1fa10-191">图 9</span><span class="sxs-lookup"><span data-stu-id="1fa10-191">Figure 9</span></span>  
    > <span data-ttu-id="1fa10-192">选择慢速3G</span><span class="sxs-lookup"><span data-stu-id="1fa10-192">Selecting Slow 3G</span></span>  
    > <span data-ttu-id="1fa10-193">![选择慢速 3G][ImagesTutorialSlow3G]</span><span class="sxs-lookup"><span data-stu-id="1fa10-193">![Selecting Slow 3G][ImagesTutorialSlow3G]</span></span>  
    
1.  <span data-ttu-id="1fa10-194">长按 "**重新**加载" ![ ][ImageRefreshIcon] ，然后选择 "**清空缓存" 和 "硬重载**"。</span><span class="sxs-lookup"><span data-stu-id="1fa10-194">Long-press **Reload** ![Reload][ImageRefreshIcon] and then select **Empty Cache And Hard Reload**.</span></span>  
    
    > ##### <span data-ttu-id="1fa10-195">图 10</span><span class="sxs-lookup"><span data-stu-id="1fa10-195">Figure 10</span></span>  
    > <span data-ttu-id="1fa10-196">清空缓存和硬重载</span><span class="sxs-lookup"><span data-stu-id="1fa10-196">Empty Cache And Hard Reload</span></span>  
    > <span data-ttu-id="1fa10-197">![清空缓存和硬重装][ImagesTutorialHardReload]</span><span class="sxs-lookup"><span data-stu-id="1fa10-197">![Empty Cache And Hard Reload][ImagesTutorialHardReload]</span></span>  
    
    <span data-ttu-id="1fa10-198">在重复访问时，浏览器通常会从[缓存][MDNHTTPCache]中处理某些文件，从而加速页面加载。</span><span class="sxs-lookup"><span data-stu-id="1fa10-198">On repeat visits, the browser usually serves some files from the [cache][MDNHTTPCache] , which speeds up the page load.</span></span>  <span data-ttu-id="1fa10-199">**清空缓存和硬重新加载**会强制浏览器为所有资源访问网络。</span><span class="sxs-lookup"><span data-stu-id="1fa10-199">**Empty Cache And Hard Reload** forces the browser to go the network for all resources.</span></span>  <span data-ttu-id="1fa10-200">如果你想要了解第一次访问者体验页面加载的方式，这很有帮助。</span><span class="sxs-lookup"><span data-stu-id="1fa10-200">This is helpful when you want to see how a first-time visitor experiences a page load.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="1fa10-201">只有在 DevTools 处于打开状态时，**空缓存和硬加载**工作流才可用。</span><span class="sxs-lookup"><span data-stu-id="1fa10-201">The **Empty Cache And Hard Reload** workflow is only available when DevTools is open.</span></span>  

## <span data-ttu-id="1fa10-202">捕获屏幕截图</span><span class="sxs-lookup"><span data-stu-id="1fa10-202">Capture screenshots</span></span>   

<span data-ttu-id="1fa10-203">屏幕截图使你可以查看页面在加载时如何在一段时间内查看。</span><span class="sxs-lookup"><span data-stu-id="1fa10-203">Screenshots let you see how a page looked over time while it was loading.</span></span>  

1.  <span data-ttu-id="1fa10-204">选择 ![ "网络设置 ][ImageSettingsIcon] "，然后选择 "**捕获屏幕截图**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="1fa10-204">Select ![Network settings][ImageSettingsIcon] and select the **Capture screenshots** checkbox.</span></span>
1.  <span data-ttu-id="1fa10-205">通过**空缓存和硬重装**工作流重新加载页面。</span><span class="sxs-lookup"><span data-stu-id="1fa10-205">Reload the page again via the **Empty Cache And Hard Reload** workflow.</span></span>  <span data-ttu-id="1fa10-206">如果需要有关如何执行此操作的提醒，请参阅[模拟低速连接](#simulate-a-slower-network-connection)。</span><span class="sxs-lookup"><span data-stu-id="1fa10-206">See [Simulate a slower connection](#simulate-a-slower-network-connection) if you need a reminder on how to do this.</span></span>  
    <span data-ttu-id="1fa10-207">"屏幕截图" 窗格提供在加载过程中如何在不同点查看页面的缩略图。</span><span class="sxs-lookup"><span data-stu-id="1fa10-207">The Screenshots pane provides thumbnails of how the page looked at various points during the loading process.</span></span>  
    
    > ##### <span data-ttu-id="1fa10-208">图 11</span><span class="sxs-lookup"><span data-stu-id="1fa10-208">Figure 11</span></span>  
    > <span data-ttu-id="1fa10-209">页面加载的屏幕截图</span><span class="sxs-lookup"><span data-stu-id="1fa10-209">Screenshots of the page load</span></span>  
    > <span data-ttu-id="1fa10-210">![页面加载的屏幕截图][ImagesTutorialAllScreenshots]</span><span class="sxs-lookup"><span data-stu-id="1fa10-210">![Screenshots of the page load][ImagesTutorialAllScreenshots]</span></span>  

1.  <span data-ttu-id="1fa10-211">选择第一个缩略图。</span><span class="sxs-lookup"><span data-stu-id="1fa10-211">Select the first thumbnail.</span></span>  <span data-ttu-id="1fa10-212">DevTools 显示当时正在发生的网络活动。</span><span class="sxs-lookup"><span data-stu-id="1fa10-212">DevTools shows you what network activity was occurring at that moment in time.</span></span>  
    
    > ##### <span data-ttu-id="1fa10-213">图 12</span><span class="sxs-lookup"><span data-stu-id="1fa10-213">Figure 12</span></span>  
    > <span data-ttu-id="1fa10-214">第一个屏幕截图期间发生的网络活动</span><span class="sxs-lookup"><span data-stu-id="1fa10-214">The network activity that was happening during the first screenshot</span></span>  
    > <span data-ttu-id="1fa10-215">![第一屏幕截图中发生的网络活动][ImagesTutorialFirstScreenshot]</span><span class="sxs-lookup"><span data-stu-id="1fa10-215">![The network activity that was happening during the first screenshot][ImagesTutorialFirstScreenshot]</span></span>  

1.  <span data-ttu-id="1fa10-216">![再次选择 "网络设置 ][ImageSettingsIcon] "，然后取消选中 "**捕获屏幕截图**" 复选框以关闭屏幕截图窗格。</span><span class="sxs-lookup"><span data-stu-id="1fa10-216">Select ![Network settings][ImageSettingsIcon] again and deselect the **Capture screenshots** checkbox to close the Screenshots pane.</span></span>
1.  <span data-ttu-id="1fa10-217">重新加载页面。</span><span class="sxs-lookup"><span data-stu-id="1fa10-217">Reload the page again.</span></span>  

## <span data-ttu-id="1fa10-218">检查资源的详细信息</span><span class="sxs-lookup"><span data-stu-id="1fa10-218">Inspect the details of the resource</span></span>   

<span data-ttu-id="1fa10-219">选择资源以了解有关它的详细信息。</span><span class="sxs-lookup"><span data-stu-id="1fa10-219">Select a resource to learn more information about it.</span></span>  <span data-ttu-id="1fa10-220">立即试用：</span><span class="sxs-lookup"><span data-stu-id="1fa10-220">Try it now:</span></span>  

1.  <span data-ttu-id="1fa10-221">选择 `getstarted.html` 。</span><span class="sxs-lookup"><span data-stu-id="1fa10-221">Select `getstarted.html`.</span></span>  <span data-ttu-id="1fa10-222">显示 "**标题**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="1fa10-222">The **Headers** tab is shown.</span></span>  <span data-ttu-id="1fa10-223">使用此选项卡检查 HTTP 头。</span><span class="sxs-lookup"><span data-stu-id="1fa10-223">Use this tab to inspect HTTP headers.</span></span>  
    
    > ##### <span data-ttu-id="1fa10-224">图 13</span><span class="sxs-lookup"><span data-stu-id="1fa10-224">Figure 13</span></span>  
    > <span data-ttu-id="1fa10-225">"页眉" 选项卡</span><span class="sxs-lookup"><span data-stu-id="1fa10-225">The Headers tab</span></span>  
    > <span data-ttu-id="1fa10-226">![标题选项卡][ImagesTutorialHeaders]</span><span class="sxs-lookup"><span data-stu-id="1fa10-226">![The Headers tab][ImagesTutorialHeaders]</span></span>  
    
1.  <span data-ttu-id="1fa10-227">选择 "**预览**" 选项卡。 显示 HTML 的基本呈现。</span><span class="sxs-lookup"><span data-stu-id="1fa10-227">Select the **Preview** tab.  A basic rendering of the HTML is shown.</span></span>  
    
    > ##### <span data-ttu-id="1fa10-228">图 14</span><span class="sxs-lookup"><span data-stu-id="1fa10-228">Figure 14</span></span>  
    > <span data-ttu-id="1fa10-229">"预览" 选项卡</span><span class="sxs-lookup"><span data-stu-id="1fa10-229">The Preview tab</span></span>  
    > <span data-ttu-id="1fa10-230">![预览选项卡][ImagesTutorialPreview]</span><span class="sxs-lookup"><span data-stu-id="1fa10-230">![The Preview tab][ImagesTutorialPreview]</span></span>  

     <span data-ttu-id="1fa10-231">当 API 返回 HTML 中的错误代码时，此选项卡很有帮助。</span><span class="sxs-lookup"><span data-stu-id="1fa10-231">This tab is helpful when an API returns an error code in HTML.</span></span>  <span data-ttu-id="1fa10-232">您可能会发现，阅读呈现的 HTML 比 HTML 源代码或检查图像更容易。</span><span class="sxs-lookup"><span data-stu-id="1fa10-232">You may find it easier to read the rendered HTML than the HTML source code, or when you inspect images.</span></span>  

1.  <span data-ttu-id="1fa10-233">选择 "**响应**" 选项卡。 将显示 HTML 源代码。</span><span class="sxs-lookup"><span data-stu-id="1fa10-233">Select the **Response** tab.  The HTML source code is shown.</span></span>  
    
    > ##### <span data-ttu-id="1fa10-234">图 15</span><span class="sxs-lookup"><span data-stu-id="1fa10-234">Figure 15</span></span>  
    > <span data-ttu-id="1fa10-235">"响应" 选项卡</span><span class="sxs-lookup"><span data-stu-id="1fa10-235">The Response tab</span></span>  
    > <span data-ttu-id="1fa10-236">![响应选项卡][ImagesTutorialResponse]</span><span class="sxs-lookup"><span data-stu-id="1fa10-236">![The Response tab][ImagesTutorialResponse]</span></span>  
    
    > [!TIP]
    > <span data-ttu-id="1fa10-237">当文件 minified 时，选择**Format** ![ ][ImageFormatIcon] "**响应**" 选项卡底部的 "格式设置" 按钮可重新设置文件内容的格式，以便于阅读。</span><span class="sxs-lookup"><span data-stu-id="1fa10-237">When a file is minified, selecting the **Format** ![Format][ImageFormatIcon] button at the bottom of the **Response** tab re-formats the contents of the file for readability.</span></span>  

1.  <span data-ttu-id="1fa10-238">选择 "**计时**" 选项卡。 将显示此资源的网络活动细目。</span><span class="sxs-lookup"><span data-stu-id="1fa10-238">Select the **Timing** tab.  A breakdown of the network activity for this resource is shown.</span></span>  
    
    > ##### <span data-ttu-id="1fa10-239">图 16</span><span class="sxs-lookup"><span data-stu-id="1fa10-239">Figure 16</span></span>  
    > <span data-ttu-id="1fa10-240">"计时" 选项卡</span><span class="sxs-lookup"><span data-stu-id="1fa10-240">The Timing tab</span></span>  
    > <span data-ttu-id="1fa10-241">![计时选项卡][ImagesTutorialTiming]</span><span class="sxs-lookup"><span data-stu-id="1fa10-241">![The Timing tab][ImagesTutorialTiming]</span></span>  

1.  <span data-ttu-id="1fa10-242">选择 "**关闭** ![ 关闭 ][ImageCloseIcon] " 再次查看网络日志。</span><span class="sxs-lookup"><span data-stu-id="1fa10-242">Select **Close** ![Close][ImageCloseIcon] to view the Network Log again.</span></span>  
    
    > ##### <span data-ttu-id="1fa10-243">图 17</span><span class="sxs-lookup"><span data-stu-id="1fa10-243">Figure 17</span></span>  
    > <span data-ttu-id="1fa10-244">"关闭" 按钮</span><span class="sxs-lookup"><span data-stu-id="1fa10-244">The Close button</span></span>  
    > <span data-ttu-id="1fa10-245">![关闭按钮][ImagesTutorialCloseTiming]</span><span class="sxs-lookup"><span data-stu-id="1fa10-245">![The Close button][ImagesTutorialCloseTiming]</span></span>  

## <span data-ttu-id="1fa10-246">搜索网络标题和响应</span><span class="sxs-lookup"><span data-stu-id="1fa10-246">Search network headers and responses</span></span>   

<span data-ttu-id="1fa10-247">当你需要在 HTTP 头和所有资源的响应中搜索特定字符串或正则表达式的响应时，请使用 "**搜索**" 窗格。</span><span class="sxs-lookup"><span data-stu-id="1fa10-247">Use the **Search** pane when you need to search the HTTP headers and responses of all resources for a certain string or regular expression.</span></span>  

<span data-ttu-id="1fa10-248">例如，假设你想要验证你的资源是否使用了合理的**缓存策略**。</span><span class="sxs-lookup"><span data-stu-id="1fa10-248">For example, suppose you want to verify that your resources are using reasonable **cache policies**.</span></span>  

<!--TODO: add cache policies section when available  -->

1.  <span data-ttu-id="1fa10-249">选择 "**搜索** ![ 搜索" ][ImageSearchIcon] 。</span><span class="sxs-lookup"><span data-stu-id="1fa10-249">Select **Search** ![Search][ImageSearchIcon].</span></span>  <span data-ttu-id="1fa10-250">"搜索" 窗格将在网络日志的左侧打开。</span><span class="sxs-lookup"><span data-stu-id="1fa10-250">The Search pane opens to the left of the Network log.</span></span>  
    
    > ##### <span data-ttu-id="1fa10-251">图18</span><span class="sxs-lookup"><span data-stu-id="1fa10-251">Figure 18</span></span>  
    > <span data-ttu-id="1fa10-252">"搜索" 窗格</span><span class="sxs-lookup"><span data-stu-id="1fa10-252">The Search pane</span></span>  
    > <span data-ttu-id="1fa10-253">![搜索窗格][ImagesTutorialSearch]</span><span class="sxs-lookup"><span data-stu-id="1fa10-253">![The Search pane][ImagesTutorialSearch]</span></span>  

1.  <span data-ttu-id="1fa10-254">键入 `Cache-Control` ，然后按 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="1fa10-254">Type `Cache-Control` and press `Enter`.</span></span>  <span data-ttu-id="1fa10-255">"搜索" 窗格 `Cache-Control` 会列出它在 "资源标题" 或 "内容" 中找到的所有实例。</span><span class="sxs-lookup"><span data-stu-id="1fa10-255">The Search pane lists all instances of `Cache-Control` that it finds in resource headers or content.</span></span>  
    
    > ##### <span data-ttu-id="1fa10-256">图19</span><span class="sxs-lookup"><span data-stu-id="1fa10-256">Figure 19</span></span>  
    > <span data-ttu-id="1fa10-257">以下项的搜索结果</span><span class="sxs-lookup"><span data-stu-id="1fa10-257">Search results for</span></span> `Cache-Control`  
    > <span data-ttu-id="1fa10-258">![缓存控制的搜索结果][ImagesTutorialResults]</span><span class="sxs-lookup"><span data-stu-id="1fa10-258">![Search results for Cache-Control][ImagesTutorialResults]</span></span>  

1.  <span data-ttu-id="1fa10-259">选择一个结果以查看在其中找到结果的资源。</span><span class="sxs-lookup"><span data-stu-id="1fa10-259">Select a result to view the resource in which the result was found.</span></span>  <span data-ttu-id="1fa10-260">如果要查看资源的详细信息，请选择要直接转到该资源的结果。</span><span class="sxs-lookup"><span data-stu-id="1fa10-260">If you are looking at the details of the resource, select a result to go directly to it.</span></span>  <span data-ttu-id="1fa10-261">例如，如果在页眉中找到查询，则 "页眉" 选项卡将打开。</span><span class="sxs-lookup"><span data-stu-id="1fa10-261">For example, if the query was found in a header, the Headers tab opens.</span></span>   <span data-ttu-id="1fa10-262">如果在内容中找到查询，将打开 "**响应**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="1fa10-262">If the query was found in content, the **Response** tab opens.</span></span>  
    
    > ##### <span data-ttu-id="1fa10-263">图20</span><span class="sxs-lookup"><span data-stu-id="1fa10-263">Figure 20</span></span>  
    > <span data-ttu-id="1fa10-264">"页眉" 选项卡中突出显示的搜索结果</span><span class="sxs-lookup"><span data-stu-id="1fa10-264">A search result highlighted in the Headers tab</span></span>  
    > <span data-ttu-id="1fa10-265">![标题选项卡中突出显示的搜索结果][ImagesTutorialCache]</span><span class="sxs-lookup"><span data-stu-id="1fa10-265">![A search result highlighted in the Headers tab][ImagesTutorialCache]</span></span>  
    
1.  <span data-ttu-id="1fa10-266">关闭 "搜索" 窗格和 "标题" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="1fa10-266">Close the Search pane and the Headers tab.</span></span>  
    
    > ##### <span data-ttu-id="1fa10-267">图21</span><span class="sxs-lookup"><span data-stu-id="1fa10-267">Figure 21</span></span>  
    > <span data-ttu-id="1fa10-268">"关闭" 按钮</span><span class="sxs-lookup"><span data-stu-id="1fa10-268">The Close buttons</span></span>  
    > <span data-ttu-id="1fa10-269">![关闭按钮][ImagesTutorialCloseButtons]</span><span class="sxs-lookup"><span data-stu-id="1fa10-269">![The Close buttons][ImagesTutorialCloseButtons]</span></span>  
    
## <span data-ttu-id="1fa10-270">筛选资源</span><span class="sxs-lookup"><span data-stu-id="1fa10-270">Filter resources</span></span>   

<span data-ttu-id="1fa10-271">DevTools 提供了大量工作流，用于筛选出与手边的任务无关的资源。</span><span class="sxs-lookup"><span data-stu-id="1fa10-271">DevTools provides numerous workflows for filtering out resources that are not relevant to the task at hand.</span></span>  

> ##### <span data-ttu-id="1fa10-272">图22</span><span class="sxs-lookup"><span data-stu-id="1fa10-272">Figure 22</span></span>  
> <span data-ttu-id="1fa10-273">"筛选器" 工具栏</span><span class="sxs-lookup"><span data-stu-id="1fa10-273">The Filters toolbar</span></span>  
> <span data-ttu-id="1fa10-274">![筛选器工具栏][ImagesTutorialFilters]</span><span class="sxs-lookup"><span data-stu-id="1fa10-274">![The Filters toolbar][ImagesTutorialFilters]</span></span>  

<span data-ttu-id="1fa10-275">默认情况下，应启用 "**筛选器**" 工具栏。</span><span class="sxs-lookup"><span data-stu-id="1fa10-275">The **Filters** toolbar should be enabled by default.</span></span>  <span data-ttu-id="1fa10-276">如果未执行此操作：</span><span class="sxs-lookup"><span data-stu-id="1fa10-276">If not:</span></span>  

1.  <span data-ttu-id="1fa10-277">选择 "**筛选** ![ 筛选器" ][ImageFilterIcon] 以显示它。</span><span class="sxs-lookup"><span data-stu-id="1fa10-277">Select **Filter** ![Filter][ImageFilterIcon] to show it.</span></span>  

### <span data-ttu-id="1fa10-278">按字符串、正则表达式或属性筛选</span><span class="sxs-lookup"><span data-stu-id="1fa10-278">Filter by string, regular expression, or property</span></span>   

<span data-ttu-id="1fa10-279">**筛选**文本框支持许多不同类型的筛选。</span><span class="sxs-lookup"><span data-stu-id="1fa10-279">The **Filter** text box supports many different types of filtering.</span></span>  

1.  <span data-ttu-id="1fa10-280">在 `png` "**筛选器**" 文本框中键入内容。</span><span class="sxs-lookup"><span data-stu-id="1fa10-280">Type `png` into the **Filter** text box.</span></span>  <span data-ttu-id="1fa10-281">仅显示包含文本的文件 `png` 。</span><span class="sxs-lookup"><span data-stu-id="1fa10-281">Only the files that contain the text `png` are shown.</span></span>  <span data-ttu-id="1fa10-282">在这种情况下，只有与筛选器匹配的文件才是 PNG 图像。</span><span class="sxs-lookup"><span data-stu-id="1fa10-282">In this case the only files that match the filter are the PNG images.</span></span>  
    
    > ##### <span data-ttu-id="1fa10-283">图23</span><span class="sxs-lookup"><span data-stu-id="1fa10-283">Figure 23</span></span>  
    > <span data-ttu-id="1fa10-284">字符串筛选器</span><span class="sxs-lookup"><span data-stu-id="1fa10-284">A string filter</span></span>  
    > <span data-ttu-id="1fa10-285">![字符串筛选器][ImagesTutorialPNG]</span><span class="sxs-lookup"><span data-stu-id="1fa10-285">![A string filter][ImagesTutorialPNG]</span></span>  

1.  <span data-ttu-id="1fa10-286">键入 `/.*\.[cj]s+$/`。</span><span class="sxs-lookup"><span data-stu-id="1fa10-286">Type `/.*\.[cj]s+$/`.</span></span>  <span data-ttu-id="1fa10-287">DevTools 筛选出文件名不以 a `j` 或 `c` 后跟1或更多字符结尾的任何资源 `s` 。</span><span class="sxs-lookup"><span data-stu-id="1fa10-287">DevTools filters out any resource with a filename that does not end with a `j` or a `c` followed by 1 or more `s` characters.</span></span>  
    
    > ##### <span data-ttu-id="1fa10-288">图24</span><span class="sxs-lookup"><span data-stu-id="1fa10-288">Figure 24</span></span>  
    > <span data-ttu-id="1fa10-289">正则表达式筛选</span><span class="sxs-lookup"><span data-stu-id="1fa10-289">A regular expression filter</span></span>  
    > <span data-ttu-id="1fa10-290">![正则表达式筛选器][ImagesTutorialRegEx]</span><span class="sxs-lookup"><span data-stu-id="1fa10-290">![A regular expression filter][ImagesTutorialRegEx]</span></span>  
    
1.  <span data-ttu-id="1fa10-291">键入 `-main.css`。</span><span class="sxs-lookup"><span data-stu-id="1fa10-291">Type `-main.css`.</span></span>  <span data-ttu-id="1fa10-292">DevTools 筛选器 `main.css` 。</span><span class="sxs-lookup"><span data-stu-id="1fa10-292">DevTools filters out `main.css`.</span></span>  <span data-ttu-id="1fa10-293">如果任何其他文件与模式匹配，它们也将被筛选掉。</span><span class="sxs-lookup"><span data-stu-id="1fa10-293">If any other file matched the pattern they would also be filtered out.</span></span>  
    
    > ##### <span data-ttu-id="1fa10-294">图25</span><span class="sxs-lookup"><span data-stu-id="1fa10-294">Figure 25</span></span>  
    > <span data-ttu-id="1fa10-295">负滤波器</span><span class="sxs-lookup"><span data-stu-id="1fa10-295">A negative filter</span></span>  
    > <span data-ttu-id="1fa10-296">![负筛选][ImagesTutorialNegative]</span><span class="sxs-lookup"><span data-stu-id="1fa10-296">![A negative filter][ImagesTutorialNegative]</span></span>  
    
1.  <span data-ttu-id="1fa10-297">在 `domain:cdn.glitch.com` "**筛选器**" 文本框中键入内容。</span><span class="sxs-lookup"><span data-stu-id="1fa10-297">Type `domain:cdn.glitch.com` into the **Filter** text box.</span></span>  <span data-ttu-id="1fa10-298">DevTools 筛选出具有与此域不匹配的 URL 的任何资源。</span><span class="sxs-lookup"><span data-stu-id="1fa10-298">DevTools filters out any resource with a URL that does not match this domain.</span></span>  
    
    > ##### <span data-ttu-id="1fa10-299">图26</span><span class="sxs-lookup"><span data-stu-id="1fa10-299">Figure 26</span></span>  
    > <span data-ttu-id="1fa10-300">属性筛选器</span><span class="sxs-lookup"><span data-stu-id="1fa10-300">A property filter</span></span>  
    > <span data-ttu-id="1fa10-301">![属性筛选器][ImagesTutorialProperty]</span><span class="sxs-lookup"><span data-stu-id="1fa10-301">![A property filter][ImagesTutorialProperty]</span></span>  

    <span data-ttu-id="1fa10-302">有关筛选属性的完整列表，请参阅[筛选请求][DevtoolsReferenceProperty]。</span><span class="sxs-lookup"><span data-stu-id="1fa10-302">See [Filter requests by properties][DevtoolsReferenceProperty] for the full list of filterable properties.</span></span>  
    
    
1.  <span data-ttu-id="1fa10-303">清除任何文本的 "**筛选器**" 文本框。</span><span class="sxs-lookup"><span data-stu-id="1fa10-303">Clear the **Filter** text box of any text.</span></span>  

### <span data-ttu-id="1fa10-304">按资源类型筛选</span><span class="sxs-lookup"><span data-stu-id="1fa10-304">Filter by resource type</span></span>   

<span data-ttu-id="1fa10-305">关注特定类型的文件，例如样式表：</span><span class="sxs-lookup"><span data-stu-id="1fa10-305">To focus in on a certain type of file, such as stylesheets:</span></span>  

1.  <span data-ttu-id="1fa10-306">选择 " **CSS**"。</span><span class="sxs-lookup"><span data-stu-id="1fa10-306">Select **CSS**.</span></span>  <span data-ttu-id="1fa10-307">将筛选出所有其他文件类型。</span><span class="sxs-lookup"><span data-stu-id="1fa10-307">All other file types are filtered out.</span></span>  
    
    > ##### <span data-ttu-id="1fa10-308">图27</span><span class="sxs-lookup"><span data-stu-id="1fa10-308">Figure 27</span></span>  
    > <span data-ttu-id="1fa10-309">仅显示 CSS 文件</span><span class="sxs-lookup"><span data-stu-id="1fa10-309">Showing CSS files only</span></span>  
    > <span data-ttu-id="1fa10-310">![仅显示 CSS 文件][ImagesTutorialCSS]</span><span class="sxs-lookup"><span data-stu-id="1fa10-310">![Showing CSS files only][ImagesTutorialCSS]</span></span>  
    
1.  <span data-ttu-id="1fa10-311">若要查看脚本，请保留 `Control` \ （Windows \）或 `Command` \ （macOS \），然后选择 " **JS**"。</span><span class="sxs-lookup"><span data-stu-id="1fa10-311">To also see scripts, hold `Control` \(Windows\) or `Command` \(macOS\) and then select **JS**.</span></span>  
    
    > ##### <span data-ttu-id="1fa10-312">图28</span><span class="sxs-lookup"><span data-stu-id="1fa10-312">Figure 28</span></span>  
    > <span data-ttu-id="1fa10-313">仅显示 CSS 和 JS 文件</span><span class="sxs-lookup"><span data-stu-id="1fa10-313">Showing CSS and JS files only</span></span>  
    > <span data-ttu-id="1fa10-314">![仅显示 CSS 和 JS 文件][ImagesTutorialCSSJS]</span><span class="sxs-lookup"><span data-stu-id="1fa10-314">![Showing CSS and JS files only][ImagesTutorialCSSJS]</span></span>  
    
1.  <span data-ttu-id="1fa10-315">选择 "**全部**" 以删除筛选器并再次查看所有资源。</span><span class="sxs-lookup"><span data-stu-id="1fa10-315">Select **All** to remove the filters and see all resources again.</span></span>  

<span data-ttu-id="1fa10-316">请参阅[筛选请求][DevtoolsNetworkReferenceFilter]以获取其他筛选工作流。</span><span class="sxs-lookup"><span data-stu-id="1fa10-316">See [Filter requests][DevtoolsNetworkReferenceFilter] for other filtering workflows.</span></span>  

## <span data-ttu-id="1fa10-317">阻止请求</span><span class="sxs-lookup"><span data-stu-id="1fa10-317">Block requests</span></span>   

<span data-ttu-id="1fa10-318">当某些页面资源不可用时，页面的外观和行为</span><span class="sxs-lookup"><span data-stu-id="1fa10-318">How does a page look and behave when some of the page resources are not available?</span></span>  <span data-ttu-id="1fa10-319">它是否完全失败，或者是否仍有运行？</span><span class="sxs-lookup"><span data-stu-id="1fa10-319">Does it fail completely, or is it still somewhat functional?</span></span>  <span data-ttu-id="1fa10-320">阻止请求以查明：</span><span class="sxs-lookup"><span data-stu-id="1fa10-320">Block requests to find out:</span></span>  

1.  <span data-ttu-id="1fa10-321">按 `Control` + `Shift` + `P` \ （Windows \）或 `Command` + `Shift` + `P` \ （macOS \）打开 "**命令" 菜单**。</span><span class="sxs-lookup"><span data-stu-id="1fa10-321">Press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the **Command Menu**.</span></span>  
    
    > ##### <span data-ttu-id="1fa10-322">图29</span><span class="sxs-lookup"><span data-stu-id="1fa10-322">Figure 29</span></span>  
    > <span data-ttu-id="1fa10-323">命令菜单</span><span class="sxs-lookup"><span data-stu-id="1fa10-323">The Command Menu</span></span>  
    > <span data-ttu-id="1fa10-324">![命令菜单][ImagesTutorialCommandMenu]</span><span class="sxs-lookup"><span data-stu-id="1fa10-324">![The Command Menu][ImagesTutorialCommandMenu]</span></span>  
    
1.  <span data-ttu-id="1fa10-325">键入 `block` ，选择 "**显示请求阻止**"，然后按 `Enter` 。</span><span class="sxs-lookup"><span data-stu-id="1fa10-325">Type `block`, select **Show Request Blocking**, and press `Enter`.</span></span>  
    
    > ##### <span data-ttu-id="1fa10-326">图30</span><span class="sxs-lookup"><span data-stu-id="1fa10-326">Figure 30</span></span>  
    > <span data-ttu-id="1fa10-327">显示请求阻止</span><span class="sxs-lookup"><span data-stu-id="1fa10-327">Show Request Blocking</span></span>  
    > <span data-ttu-id="1fa10-328">![显示请求阻止][ImagesTutorialBlock]</span><span class="sxs-lookup"><span data-stu-id="1fa10-328">![Show Request Blocking][ImagesTutorialBlock]</span></span>  

1.  <span data-ttu-id="1fa10-329">选择 "**添加图案**" " ![ 添加图案" ][ImageAddIcon] 。</span><span class="sxs-lookup"><span data-stu-id="1fa10-329">Select **Add Pattern** ![Add Pattern][ImageAddIcon].</span></span>  
1.  <span data-ttu-id="1fa10-330">键入 `main.css`。</span><span class="sxs-lookup"><span data-stu-id="1fa10-330">Type `main.css`.</span></span>  
    
    > ##### <span data-ttu-id="1fa10-331">图31</span><span class="sxs-lookup"><span data-stu-id="1fa10-331">Figure 31</span></span>  
    > <span data-ttu-id="1fa10-332">阻止</span><span class="sxs-lookup"><span data-stu-id="1fa10-332">Blocking</span></span> `main.css`  
    > <span data-ttu-id="1fa10-333">![阻止主 .css][ImagesTutorialAddBlock]</span><span class="sxs-lookup"><span data-stu-id="1fa10-333">![Blocking main.css][ImagesTutorialAddBlock]</span></span>  
    
1.  <span data-ttu-id="1fa10-334">选择**添加**。</span><span class="sxs-lookup"><span data-stu-id="1fa10-334">Select **Add**.</span></span>  
1.  <span data-ttu-id="1fa10-335">重新加载页面。</span><span class="sxs-lookup"><span data-stu-id="1fa10-335">Reload the page.</span></span>  <span data-ttu-id="1fa10-336">正常情况下，页面的样式会略微 messed，因为主样式表已被阻止。</span><span class="sxs-lookup"><span data-stu-id="1fa10-336">As expected, the styling of the page is slightly messed up because the main stylesheet has been blocked.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="1fa10-337">`main.css`网络日志中的行。</span><span class="sxs-lookup"><span data-stu-id="1fa10-337">The `main.css` row in the Network Log.</span></span>  <span data-ttu-id="1fa10-338">红色文本表示资源已被阻止。</span><span class="sxs-lookup"><span data-stu-id="1fa10-338">The red text means that the resource was blocked.</span></span>
    
    > ##### <span data-ttu-id="1fa10-339">图32</span><span class="sxs-lookup"><span data-stu-id="1fa10-339">Figure 32</span></span>  
    > `main.css` <span data-ttu-id="1fa10-340">已被阻止</span><span class="sxs-lookup"><span data-stu-id="1fa10-340">has been blocked</span></span>  
    > <span data-ttu-id="1fa10-341">![已阻止主页 .css][ImagesTutorialBlockedStyles]</span><span class="sxs-lookup"><span data-stu-id="1fa10-341">![main.css has been blocked][ImagesTutorialBlockedStyles]</span></span>  

1.  <span data-ttu-id="1fa10-342">取消选中 "**启用请求阻止**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="1fa10-342">Deselect the **Enable request blocking** checkbox.</span></span>  

## <span data-ttu-id="1fa10-343">总结</span><span class="sxs-lookup"><span data-stu-id="1fa10-343">Conclusion</span></span>  

<span data-ttu-id="1fa10-344">恭喜，你已完成教程。</span><span class="sxs-lookup"><span data-stu-id="1fa10-344">Congratulations, you have completed the tutorial.</span></span>  <span data-ttu-id="1fa10-345">您现在知道如何在 Microsoft Edge DevTools 中使用 "网络" 面板！</span><span class="sxs-lookup"><span data-stu-id="1fa10-345">You now know how to use the Network panel in the Microsoft Edge DevTools!</span></span>






<span data-ttu-id="1fa10-346">查看[网络参考][DevtoolsNetworkReference]以发现更多与检查网络活动相关的 DevTools 功能。</span><span class="sxs-lookup"><span data-stu-id="1fa10-346">Check out the [Network Reference][DevtoolsNetworkReference] to discover more DevTools features related to inspecting network activity.</span></span>  

 



<!-- image links -->  

[ImageAddIcon]: /microsoft-edge/devtools-guide-chromium/media/add-icon.msft.png  
[ImageCloseIcon]: /microsoft-edge/devtools-guide-chromium/media/close-icon.msft.png  
[ImageFilterIcon]: /microsoft-edge/devtools-guide-chromium/media/filter-icon.msft.png  
[ImageFormatIcon]: /microsoft-edge/devtools-guide-chromium/media/format-icon.msft.png  
[ImageRefreshIcon]: /microsoft-edge/devtools-guide-chromium/media/refresh-icon.msft.png  
[ImageScreenshotsIcon]: /microsoft-edge/devtools-guide-chromium/media/screenshots-icon.msft.png  
[ImageSearchIcon]: /microsoft-edge/devtools-guide-chromium/media/search-icon.msft.png  
[ImageSettingsIcon]: /microsoft-edge/devtools-guide-chromium/media/settings-icon.msft.png

[ImagesTutorialDemo]: /microsoft-edge/devtools-guide-chromium/media/network-glitch-inspect-network-activity-demo.msft.png "图1：演示"  
<!--[ImagesTutorialWindows]: /microsoft-edge/devtools-guide-chromium/media/network-tutorial/windows.msft.png " old Figure 2: The demo in one window and this tutorial in a different window"  -->  
<span data-ttu-id="1fa10-348">[ImagesTutorialConsole]：/microsoft-edge/devtools-guide-chromium/media/network-glitch-console.msft.png "图2：控制台"</span><span class="sxs-lookup"><span data-stu-id="1fa10-348">[ImagesTutorialConsole]: /microsoft-edge/devtools-guide-chromium/media/network-glitch-console.msft.png "Figure 2: The Console"</span></span>  
<span data-ttu-id="1fa10-349">[ImagesTutorialDocked]：/microsoft-edge/devtools-guide-chromium/media/network-glitch-console-bottom.msft.png "图3： DevTools 停靠在窗口底部"</span><span class="sxs-lookup"><span data-stu-id="1fa10-349">[ImagesTutorialDocked]: /microsoft-edge/devtools-guide-chromium/media/network-glitch-console-bottom.msft.png "Figure 3: DevTools docked to the bottom of the window"</span></span>  
<span data-ttu-id="1fa10-350">[ImagesTutorialNetwork]：/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-bottom.msft.png "图4： DevTools 停靠在窗口底部"</span><span class="sxs-lookup"><span data-stu-id="1fa10-350">[ImagesTutorialNetwork]: /microsoft-edge/devtools-guide-chromium/media/network-glitch-network-bottom.msft.png "Figure 4: DevTools docked to the bottom of the window"</span></span>  
<span data-ttu-id="1fa10-351">[ImagesTutorialLog]：/microsoft-edge/devtools-guide-chromium/media/network-glitch-network.msft.png "图5：网络日志"</span><span class="sxs-lookup"><span data-stu-id="1fa10-351">[ImagesTutorialLog]: /microsoft-edge/devtools-guide-chromium/media/network-glitch-network.msft.png "Figure 5: The Network Log"</span></span>  
<span data-ttu-id="1fa10-352">[ImagesTutorialRuntime]：/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-new-resource.msft.png "图6：网络日志中的新资源"</span><span class="sxs-lookup"><span data-stu-id="1fa10-352">[ImagesTutorialRuntime]: /microsoft-edge/devtools-guide-chromium/media/network-glitch-network-new-resource.msft.png "Figure 6: A new resource in the Network Log"</span></span>  
<span data-ttu-id="1fa10-353">[ImagesTutorialDomain]：/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-edit-column.msft.png "图7：启用域列"</span><span class="sxs-lookup"><span data-stu-id="1fa10-353">[ImagesTutorialDomain]: /microsoft-edge/devtools-guide-chromium/media/network-glitch-network-edit-column.msft.png "Figure 7: Enabling the Domain column"</span></span>  
<span data-ttu-id="1fa10-354">[ImagesTutorialThrottling]：/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-throttling.msft.png "图8：启用限制"</span><span class="sxs-lookup"><span data-stu-id="1fa10-354">[ImagesTutorialThrottling]: /microsoft-edge/devtools-guide-chromium/media/network-glitch-network-throttling.msft.png "Figure 8: Enabling throttling"</span></span>  
<span data-ttu-id="1fa10-355">[ImagesTutorialSlow3G]：/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-throttling-slow-3g.msft.png "图9：选择慢速 3G"</span><span class="sxs-lookup"><span data-stu-id="1fa10-355">[ImagesTutorialSlow3G]: /microsoft-edge/devtools-guide-chromium/media/network-glitch-network-throttling-slow-3g.msft.png "Figure 9: Selecting Slow 3G"</span></span>  
<span data-ttu-id="1fa10-356">[ImagesTutorialHardReload]：/microsoft-edge/devtools-guide-chromium/media/network-glitch-empty-cache-and-hard-reset.msft.png "图10：清空缓存和硬重新加载"</span><span class="sxs-lookup"><span data-stu-id="1fa10-356">[ImagesTutorialHardReload]: /microsoft-edge/devtools-guide-chromium/media/network-glitch-empty-cache-and-hard-reset.msft.png "Figure 10: Empty Cache And Hard Reload"</span></span>  
<span data-ttu-id="1fa10-357">[ImagesTutorialAllScreenshots]：/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-screenshots.msft.png "图11：页面加载的屏幕截图"</span><span class="sxs-lookup"><span data-stu-id="1fa10-357">[ImagesTutorialAllScreenshots]: /microsoft-edge/devtools-guide-chromium/media/network-glitch-network-screenshots.msft.png "Figure 11: Screenshots of the page load"</span></span>  
<span data-ttu-id="1fa10-358">[ImagesTutorialFirstScreenshot]：/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-screenshots-first.msft.png "图12：在第一个屏幕截图期间发生的网络活动"</span><span class="sxs-lookup"><span data-stu-id="1fa10-358">[ImagesTutorialFirstScreenshot]: /microsoft-edge/devtools-guide-chromium/media/network-glitch-network-screenshots-first.msft.png "Figure 12: The network activity that was happening during the first screenshot"</span></span>  
<span data-ttu-id="1fa10-359">[ImagesTutorialHeaders]：/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-resources-headers.msft.png "图13：标题" 选项卡 "</span><span class="sxs-lookup"><span data-stu-id="1fa10-359">[ImagesTutorialHeaders]: /microsoft-edge/devtools-guide-chromium/media/network-glitch-network-resources-headers.msft.png "Figure 13: The Headers tab"</span></span>  
<span data-ttu-id="1fa10-360">[ImagesTutorialPreview]：/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-resources-preview.msft.png "图14：" 预览 "选项卡"</span><span class="sxs-lookup"><span data-stu-id="1fa10-360">[ImagesTutorialPreview]: /microsoft-edge/devtools-guide-chromium/media/network-glitch-network-resources-preview.msft.png "Figure 14: The Preview tab"</span></span>  
<span data-ttu-id="1fa10-361">[ImagesTutorialResponse]：/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-resources-response.msft.png "图15：" 响应 "选项卡"</span><span class="sxs-lookup"><span data-stu-id="1fa10-361">[ImagesTutorialResponse]: /microsoft-edge/devtools-guide-chromium/media/network-glitch-network-resources-response.msft.png "Figure 15: The Response tab"</span></span>  
<span data-ttu-id="1fa10-362">[ImagesTutorialTiming]：/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-resources-timing.msft.png "图16：" 计时 "选项卡"</span><span class="sxs-lookup"><span data-stu-id="1fa10-362">[ImagesTutorialTiming]: /microsoft-edge/devtools-guide-chromium/media/network-glitch-network-resources-timing.msft.png "Figure 16: The Timing tab"</span></span>  
<span data-ttu-id="1fa10-363">[ImagesTutorialCloseTiming]：/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-resources-close-tabs.msft.png "图17： ' 关闭 ' 按钮"</span><span class="sxs-lookup"><span data-stu-id="1fa10-363">[ImagesTutorialCloseTiming]: /microsoft-edge/devtools-guide-chromium/media/network-glitch-network-resources-close-tabs.msft.png "Figure 17: The Close button"</span></span>  
<span data-ttu-id="1fa10-364">[ImagesTutorialSearch]：/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-search-empty.msft.png "图18：搜索窗格"</span><span class="sxs-lookup"><span data-stu-id="1fa10-364">[ImagesTutorialSearch]: /microsoft-edge/devtools-guide-chromium/media/network-glitch-network-search-empty.msft.png "Figure 18: The Search pane"</span></span>  
<span data-ttu-id="1fa10-365">[ImagesTutorialResults]：/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-search-cache-control.msft.png "图19：用于缓存控制的搜索结果"</span><span class="sxs-lookup"><span data-stu-id="1fa10-365">[ImagesTutorialResults]: /microsoft-edge/devtools-guide-chromium/media/network-glitch-network-search-cache-control.msft.png "Figure 19: Search results for Cache-Control"</span></span>  
<span data-ttu-id="1fa10-366">[ImagesTutorialCache]：/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-search-cache-control-headers-response-headers.msft.png "图20：" 页眉 "选项卡中突出显示的搜索结果</span><span class="sxs-lookup"><span data-stu-id="1fa10-366">[ImagesTutorialCache]: /microsoft-edge/devtools-guide-chromium/media/network-glitch-network-search-cache-control-headers-response-headers.msft.png "Figure 20: A search result highlighted in the Headers tab"</span></span>  
<span data-ttu-id="1fa10-367">[ImagesTutorialCloseButtons]：/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-search-close.msft.png "图21：关闭按钮"</span><span class="sxs-lookup"><span data-stu-id="1fa10-367">[ImagesTutorialCloseButtons]: /microsoft-edge/devtools-guide-chromium/media/network-glitch-network-search-close.msft.png "Figure 21: The Close buttons"</span></span>  
<span data-ttu-id="1fa10-368">[ImagesTutorialFilters]：/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-filter-empty.msft.png "图22：筛选器工具栏"</span><span class="sxs-lookup"><span data-stu-id="1fa10-368">[ImagesTutorialFilters]: /microsoft-edge/devtools-guide-chromium/media/network-glitch-network-filter-empty.msft.png "Figure 22: The Filters toolbar"</span></span>  
<span data-ttu-id="1fa10-369">[ImagesTutorialPNG]：/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-filter-png.msft.png "图23：字符串筛选器"</span><span class="sxs-lookup"><span data-stu-id="1fa10-369">[ImagesTutorialPNG]: /microsoft-edge/devtools-guide-chromium/media/network-glitch-network-filter-png.msft.png "Figure 23: A string filter"</span></span>  
<span data-ttu-id="1fa10-370">[ImagesTutorialRegEx]：/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-filter-regex.msft.png "图24：正则表达式筛选器"</span><span class="sxs-lookup"><span data-stu-id="1fa10-370">[ImagesTutorialRegEx]: /microsoft-edge/devtools-guide-chromium/media/network-glitch-network-filter-regex.msft.png "Figure 24: A regular expression filter"</span></span>  
<span data-ttu-id="1fa10-371">[ImagesTutorialNegative]：/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-filter-negative-statement.msft.png "图25：否定筛选器"</span><span class="sxs-lookup"><span data-stu-id="1fa10-371">[ImagesTutorialNegative]: /microsoft-edge/devtools-guide-chromium/media/network-glitch-network-filter-negative-statement.msft.png "Figure 25: A negative filter"</span></span>  
<span data-ttu-id="1fa10-372">[ImagesTutorialProperty]：/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-filter-property-value.msft.png "图26：属性筛选器"</span><span class="sxs-lookup"><span data-stu-id="1fa10-372">[ImagesTutorialProperty]: /microsoft-edge/devtools-guide-chromium/media/network-glitch-network-filter-property-value.msft.png "Figure 26: A property filter"</span></span>  
<span data-ttu-id="1fa10-373">[ImagesTutorialCSS]：/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-filter-file-type-css.msft.png "图27：仅显示 CSS 文件"</span><span class="sxs-lookup"><span data-stu-id="1fa10-373">[ImagesTutorialCSS]: /microsoft-edge/devtools-guide-chromium/media/network-glitch-network-filter-file-type-css.msft.png "Figure 27: Showing CSS files only"</span></span>  
<span data-ttu-id="1fa10-374">[ImagesTutorialCSSJS]：/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-filter-file-type-css-js.msft.png "图28：仅显示 CSS 和 JS 文件"</span><span class="sxs-lookup"><span data-stu-id="1fa10-374">[ImagesTutorialCSSJS]: /microsoft-edge/devtools-guide-chromium/media/network-glitch-network-filter-file-type-css-js.msft.png "Figure 28: Showing CSS and JS files only"</span></span>  
<span data-ttu-id="1fa10-375">[ImagesTutorialCommandMenu]：/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-cli-empty.msft.png "图29：命令菜单"</span><span class="sxs-lookup"><span data-stu-id="1fa10-375">[ImagesTutorialCommandMenu]: /microsoft-edge/devtools-guide-chromium/media/network-glitch-network-cli-empty.msft.png "Figure 29: The Command Menu"</span></span>  
<span data-ttu-id="1fa10-376">[ImagesTutorialBlock]：/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-cli-block.msft.png "图30：显示请求阻止"</span><span class="sxs-lookup"><span data-stu-id="1fa10-376">[ImagesTutorialBlock]: /microsoft-edge/devtools-guide-chromium/media/network-glitch-network-cli-block.msft.png "Figure 30: Show Request Blocking"</span></span>  
<span data-ttu-id="1fa10-377">[ImagesTutorialAddBlock]：/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-cli-block-add-pattern.msft.png "图31：阻止主 css"</span><span class="sxs-lookup"><span data-stu-id="1fa10-377">[ImagesTutorialAddBlock]: /microsoft-edge/devtools-guide-chromium/media/network-glitch-network-cli-block-add-pattern.msft.png "Figure 31: Blocking main.css"</span></span>  
<span data-ttu-id="1fa10-378">[ImagesTutorialBlockedStyles]：/microsoft-edge/devtools-guide-chromium/media/network-glitch-network-cli-block-main-css.msft.png "图32： main .css 已被阻止"</span><span class="sxs-lookup"><span data-stu-id="1fa10-378">[ImagesTutorialBlockedStyles]: /microsoft-edge/devtools-guide-chromium/media/network-glitch-network-cli-block-main-css.msft.png "Figure 32: main.css has been blocked"</span></span>  

<!-- links -->  


<!--[CachePolicies]: ../../../web/tools/lighthouse/audits/cache-policy ""  -->  

[DevToolsCustomizePlacement]: /microsoft-edge/devtools-guide-chromium/customize/placement "更改 Microsoft Edge DevTools 位置（"取消停靠"、"停靠到底部"、"停靠到左侧"）"  
[DevtoolsNetworkReference]: /microsoft-edge/devtools-guide-chromium/network/reference "网络分析参考"
[DevtoolsNetworkReferenceFilter]: /microsoft-edge/devtools-guide-chromium/network/reference#filter-requests "筛选请求-网络分析参考"  
[DevtoolsReferenceHideOverview]: /microsoft-edge/devtools-guide-chromium/network/reference#hide-the-overview-pane "隐藏 "概述" 窗格-网络分析参考"
[DevtoolsReferenceProperty]: /microsoft-edge/devtools-guide-chromium/network/reference#filter-requests-by-properties "按属性过滤请求-网络分析参考"
[DevToolsOpen]: /microsoft-edge/devtools-guide-chromium/open "打开 Microsoft Edge DevTools"  
[DevtoolsSpeedGetStarted]: /microsoft-edge/devtools-guide-chromium/speed/get-started "通过 Microsoft Edge DevTools 优化网站速度"  

[GlitchNetworkGetStarted]: https://microsoft-edge-chromium-devtools.glitch.me/static/network/getstarted.html "检查网络活动演示"  

[MDNHTTPCache]: https://developer.mozilla.org/docs/Web/HTTP/Caching "HTTP 缓存 |MDN"  

> [!NOTE]
> <span data-ttu-id="1fa10-388">此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="1fa10-388">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="1fa10-389">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/network/index)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools \ & Lighthouse \）创作。</span><span class="sxs-lookup"><span data-stu-id="1fa10-389">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/network/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
<span data-ttu-id="1fa10-391">此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="1fa10-391">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
