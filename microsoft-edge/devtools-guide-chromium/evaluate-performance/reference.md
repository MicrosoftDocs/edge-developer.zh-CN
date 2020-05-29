---
title: 性能分析参考
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/29/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: acd6e3e68f89096cf80c08f0d0c3430ab31eaec1
ms.sourcegitcommit: 50991a04c18283a8890ae33fcc3491c0476c7684
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/30/2020
ms.locfileid: "10611746"
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







# <span data-ttu-id="54edc-103">性能分析参考</span><span class="sxs-lookup"><span data-stu-id="54edc-103">Performance Analysis Reference</span></span>   



<span data-ttu-id="54edc-104">此页面是与分析性能相关的 Microsoft Edge DevTools 功能的完整参考。</span><span class="sxs-lookup"><span data-stu-id="54edc-104">This page is a comprehensive reference of Microsoft Edge DevTools features related to analyzing performance.</span></span>  

<span data-ttu-id="54edc-105">有关如何使用[Microsoft Edge DevTools][MicrosoftEdgeDevTools]分析页面性能的引导式教程，请参阅[分析运行时性能开始][DevtoolsEvaluatePerformanceGettingStarted]。</span><span class="sxs-lookup"><span data-stu-id="54edc-105">See [Get Started With Analyzing Runtime Performance][DevtoolsEvaluatePerformanceGettingStarted] for a guided tutorial on how to analyze the performance of a page using [Microsoft Edge DevTools][MicrosoftEdgeDevTools].</span></span>  

## <span data-ttu-id="54edc-106">记录性能</span><span class="sxs-lookup"><span data-stu-id="54edc-106">Record performance</span></span>   

### <span data-ttu-id="54edc-107">记录运行时性能</span><span class="sxs-lookup"><span data-stu-id="54edc-107">Record runtime performance</span></span>   

<span data-ttu-id="54edc-108">当您希望分析页面的性能（相对于加载）时，请记录运行时性能。</span><span class="sxs-lookup"><span data-stu-id="54edc-108">Record runtime performance when you want to analyze the performance of a page as it is running, as opposed to loading.</span></span>  

1.  <span data-ttu-id="54edc-109">转到要分析的页面。</span><span class="sxs-lookup"><span data-stu-id="54edc-109">Go to the page that you want to analyze.</span></span>  
1.  <span data-ttu-id="54edc-110">单击 "DevTools" 中的 "**性能**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="54edc-110">Click the **Performance** tab in DevTools.</span></span>  
1.  <span data-ttu-id="54edc-111">单击 "**录制** ![ 记录" ][ImageRecordIcon] 。</span><span class="sxs-lookup"><span data-stu-id="54edc-111">Click **Record** ![Record][ImageRecordIcon].</span></span>  
    
    > ##### <span data-ttu-id="54edc-112">图 1</span><span class="sxs-lookup"><span data-stu-id="54edc-112">Figure 1</span></span>  
    > **<span data-ttu-id="54edc-113">记录</span><span class="sxs-lookup"><span data-stu-id="54edc-113">Record</span></span>**  
    > ![记录][ImageRecord]  

1.  <span data-ttu-id="54edc-115">与页面交互。</span><span class="sxs-lookup"><span data-stu-id="54edc-115">Interact with the page.</span></span>  <span data-ttu-id="54edc-116">DevTools 记录作为交互的结果而发生的所有页面活动。</span><span class="sxs-lookup"><span data-stu-id="54edc-116">DevTools records all page activity that occurs as a result of your interactions.</span></span>  
1.  <span data-ttu-id="54edc-117">再次单击 "**录制**" 或单击 "**停止**" 停止录制。</span><span class="sxs-lookup"><span data-stu-id="54edc-117">Click **Record** again or click **Stop** to stop recording.</span></span>  

### <span data-ttu-id="54edc-118">记录加载性能</span><span class="sxs-lookup"><span data-stu-id="54edc-118">Record load performance</span></span>   

<span data-ttu-id="54edc-119">当你希望在加载时分析页面性能（而不是运行）时，请记录加载性能。</span><span class="sxs-lookup"><span data-stu-id="54edc-119">Record load performance when you want to analyze the performance of a page as it is loading, as opposed to running.</span></span>  

1.  <span data-ttu-id="54edc-120">转到要分析的页面。</span><span class="sxs-lookup"><span data-stu-id="54edc-120">Go to the page that you want to analyze.</span></span>  
1.  <span data-ttu-id="54edc-121">打开 DevTools 的**性能**面板。</span><span class="sxs-lookup"><span data-stu-id="54edc-121">Open the **Performance** panel of DevTools.</span></span>  
1.  <span data-ttu-id="54edc-122">单击 "**刷新页面** ![ 刷新页面" ][ImageRefreshPageIcon] 。</span><span class="sxs-lookup"><span data-stu-id="54edc-122">Click **Refresh page** ![Refresh Page][ImageRefreshPageIcon].</span></span>  <span data-ttu-id="54edc-123">DevTools 在页面刷新时记录性能指标，然后在加载完成后的几秒钟内自动停止录制。</span><span class="sxs-lookup"><span data-stu-id="54edc-123">DevTools records performance metrics while the page refreshes and then automatically stops the recording a couple seconds after the load finishes.</span></span>  
    
    > ##### <span data-ttu-id="54edc-124">图 2</span><span class="sxs-lookup"><span data-stu-id="54edc-124">Figure 2</span></span>  
    > **<span data-ttu-id="54edc-125">刷新页面</span><span class="sxs-lookup"><span data-stu-id="54edc-125">Refresh page</span></span>**  
    > ![刷新页面][ImageRefreshPage]  

<span data-ttu-id="54edc-127">DevTools 会自动放大大部分活动发生的录制部分。</span><span class="sxs-lookup"><span data-stu-id="54edc-127">DevTools automatically zooms in on the portion of the recording where most of the activity occurred.</span></span>  

> ##### <span data-ttu-id="54edc-128">图 3</span><span class="sxs-lookup"><span data-stu-id="54edc-128">Figure 3</span></span>  
> <span data-ttu-id="54edc-129">页面加载录制</span><span class="sxs-lookup"><span data-stu-id="54edc-129">A page-load recording</span></span>  
> ![页面加载录制][ImageLoadRecording]  

### <span data-ttu-id="54edc-131">录制时捕获屏幕截图</span><span class="sxs-lookup"><span data-stu-id="54edc-131">Capture screenshots while recording</span></span>   

<span data-ttu-id="54edc-132">启用 "**屏幕截图**" 复选框，以便在录制时捕获每个帧的屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="54edc-132">Enable the **Screenshots** checkbox to capture a screenshot of every frame while recording.</span></span>  

> ##### <span data-ttu-id="54edc-133">图 4</span><span class="sxs-lookup"><span data-stu-id="54edc-133">Figure 4</span></span>  
> <span data-ttu-id="54edc-134">"**屏幕截图**" 复选框</span><span class="sxs-lookup"><span data-stu-id="54edc-134">The **Screenshots** checkbox</span></span>  
> !["屏幕截图" 复选框][ImageScreenshots]  

<span data-ttu-id="54edc-136">请参阅[查看屏幕截图](#view-a-screenshot)，了解如何与屏幕截图交互。</span><span class="sxs-lookup"><span data-stu-id="54edc-136">See [View a screenshot](#view-a-screenshot) to learn how to interact with screenshots.</span></span>  

### <span data-ttu-id="54edc-137">录制时强制垃圾回收</span><span class="sxs-lookup"><span data-stu-id="54edc-137">Force garbage collection while recording</span></span>   

<span data-ttu-id="54edc-138">录制页面时，请单击 "**收集垃圾**回收 ![ 垃圾" ][ImageCollectGarbageIcon] 以强制进行垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="54edc-138">While you are recording a page, click **Collect garbage** ![Collect garbage][ImageCollectGarbageIcon] to force garbage collection.</span></span>  

> ##### <span data-ttu-id="54edc-139">图 5</span><span class="sxs-lookup"><span data-stu-id="54edc-139">Figure 5</span></span>  
> <span data-ttu-id="54edc-140">收集垃圾</span><span class="sxs-lookup"><span data-stu-id="54edc-140">Collect garbage</span></span>  
> ![收集垃圾][ImageCollectGarbage]  

### <span data-ttu-id="54edc-142">显示录制设置</span><span class="sxs-lookup"><span data-stu-id="54edc-142">Show recording settings</span></span>   

<span data-ttu-id="54edc-143">单击 "**捕获设置** ![ 捕获设置" ][ImageCaptureSettingsIcon] 以显示有关 DevTools 如何捕获性能录制的更多设置。</span><span class="sxs-lookup"><span data-stu-id="54edc-143">Click **Capture settings** ![Capture settings][ImageCaptureSettingsIcon] to expose more settings related to how DevTools captures performance recordings.</span></span>  

> ##### <span data-ttu-id="54edc-144">图 6</span><span class="sxs-lookup"><span data-stu-id="54edc-144">Figure 6</span></span>  
> <span data-ttu-id="54edc-145">"**捕获设置**" 部分</span><span class="sxs-lookup"><span data-stu-id="54edc-145">The **Capture settings** section</span></span>  
> !["捕获设置" 部分][ImageCaptureSettings]  

### <span data-ttu-id="54edc-147">禁用 JavaScript 示例</span><span class="sxs-lookup"><span data-stu-id="54edc-147">Disable JavaScript samples</span></span>   

<span data-ttu-id="54edc-148">默认情况下，录制的**主要**部分显示在录制期间调用的 JavaScript 函数的详细调用堆栈。</span><span class="sxs-lookup"><span data-stu-id="54edc-148">By default, the **Main** section of a recording displays detailed call stacks of JavaScript functions that were called during the recording.</span></span>  <span data-ttu-id="54edc-149">要禁用这些调用堆栈，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="54edc-149">To disable these call stacks:</span></span>  

1.  <span data-ttu-id="54edc-150">打开 "**捕获设置**" 菜单。</span><span class="sxs-lookup"><span data-stu-id="54edc-150">Open the **Capture settings** menu.</span></span>  <span data-ttu-id="54edc-151">请参阅[显示录制设置](#show-recording-settings)。</span><span class="sxs-lookup"><span data-stu-id="54edc-151">See [Show recording settings](#show-recording-settings).</span></span>  
1.  <span data-ttu-id="54edc-152">启用 "**禁用 JavaScript 示例**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="54edc-152">Enable the **Disable JavaScript Samples** checkbox.</span></span>  
1.  <span data-ttu-id="54edc-153">记录页面。</span><span class="sxs-lookup"><span data-stu-id="54edc-153">Take a recording of the page.</span></span>  

<span data-ttu-id="54edc-154">[图 7](#figure-7)和[图 8](#figure-8)显示了禁用和启用 JavaScript 示例之间的区别。</span><span class="sxs-lookup"><span data-stu-id="54edc-154">[Figure 7](#figure-7) and [Figure 8](#figure-8) show the difference between disabling and enabling JavaScript samples.</span></span>  <span data-ttu-id="54edc-155">在禁用采样时，录制的**主要**部分会更短，因为它省略了所有 JavaScript 调用堆栈。</span><span class="sxs-lookup"><span data-stu-id="54edc-155">The **Main** section of the recording is much shorter when sampling is disabled, because it omits all of the JavaScript call stacks.</span></span>  

> ##### <span data-ttu-id="54edc-156">图 7</span><span class="sxs-lookup"><span data-stu-id="54edc-156">Figure 7</span></span>  
> <span data-ttu-id="54edc-157">禁用 JS 示例时录制的示例</span><span class="sxs-lookup"><span data-stu-id="54edc-157">An example of a recording when JS samples are disabled</span></span>  
> ![禁用 JS 示例时录制的示例][ImageJSSamplesDisabled]  

> ##### <span data-ttu-id="54edc-159">图 8</span><span class="sxs-lookup"><span data-stu-id="54edc-159">Figure 8</span></span>  
> <span data-ttu-id="54edc-160">启用 JS 示例时录制的示例</span><span class="sxs-lookup"><span data-stu-id="54edc-160">An example of a recording when JS samples are enabled</span></span>  
> ![启用 JS 示例时录制的示例][ImageJSSamplesEnabled]  

### <span data-ttu-id="54edc-162">录制时阻止网络</span><span class="sxs-lookup"><span data-stu-id="54edc-162">Throttle the network while recording</span></span>   

<span data-ttu-id="54edc-163">要在录制时阻止网络，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="54edc-163">To throttle the network while recording:</span></span>  

1.  <span data-ttu-id="54edc-164">打开 "**捕获设置**" 菜单。</span><span class="sxs-lookup"><span data-stu-id="54edc-164">Open the **Capture settings** menu.</span></span>  <span data-ttu-id="54edc-165">请参阅[显示录制设置](#show-recording-settings)。</span><span class="sxs-lookup"><span data-stu-id="54edc-165">See [Show recording settings](#show-recording-settings).</span></span>  
1.  <span data-ttu-id="54edc-166">将 "**网络**" 设置为所需的带宽限制级别。</span><span class="sxs-lookup"><span data-stu-id="54edc-166">Set **Network** to the desired level of throttling.</span></span>  

### <span data-ttu-id="54edc-167">在录制时调节 CPU</span><span class="sxs-lookup"><span data-stu-id="54edc-167">Throttle the CPU while recording</span></span>   

<span data-ttu-id="54edc-168">要在录制时调节 CPU，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="54edc-168">To throttle the CPU while recording:</span></span>  

1.  <span data-ttu-id="54edc-169">打开 "**捕获设置**" 菜单。</span><span class="sxs-lookup"><span data-stu-id="54edc-169">Open the **Capture settings** menu.</span></span>  <span data-ttu-id="54edc-170">请参阅[显示录制设置](#show-recording-settings)。</span><span class="sxs-lookup"><span data-stu-id="54edc-170">See [Show recording settings](#show-recording-settings).</span></span>  
1.  <span data-ttu-id="54edc-171">将**CPU**设置为所需的带宽限制级别。</span><span class="sxs-lookup"><span data-stu-id="54edc-171">Set **CPU** to the desired level of throttling.</span></span>  

<span data-ttu-id="54edc-172">"限制" 相对于计算机的功能。</span><span class="sxs-lookup"><span data-stu-id="54edc-172">Throttling is relative to the capabilities of your computer.</span></span>  <span data-ttu-id="54edc-173">例如， **2x 减速**选项使 CPU 的运行速度比正常速度慢2倍。</span><span class="sxs-lookup"><span data-stu-id="54edc-173">For example, the **2x slowdown** option makes your CPU operate 2 times slower than normal.</span></span>  <span data-ttu-id="54edc-174">DevTools 不会真正模拟移动设备的 Cpu，因为移动设备的体系结构与台式计算机和笔记本电脑的体系结构截然不同。</span><span class="sxs-lookup"><span data-stu-id="54edc-174">DevTools do not truly simulate the CPUs of mobile devices, because the architecture of mobile devices is very different from that of desktops and laptops.</span></span>  

### <span data-ttu-id="54edc-175">启用高级画图工具</span><span class="sxs-lookup"><span data-stu-id="54edc-175">Enable advanced paint instrumentation</span></span>   

<span data-ttu-id="54edc-176">查看详细的画图工具：</span><span class="sxs-lookup"><span data-stu-id="54edc-176">To view detailed paint instrumentation:</span></span>  

1.  <span data-ttu-id="54edc-177">打开 "**捕获设置**" 菜单。</span><span class="sxs-lookup"><span data-stu-id="54edc-177">Open the **Capture settings** menu.</span></span>  <span data-ttu-id="54edc-178">请参阅[显示录制设置](#show-recording-settings)。</span><span class="sxs-lookup"><span data-stu-id="54edc-178">See [Show recording settings](#show-recording-settings).</span></span>  
1.  <span data-ttu-id="54edc-179">选中 "**启用高级画图工具（慢）** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="54edc-179">Check the **Enable advanced paint instrumentation (slow)** checkbox.</span></span>  

<span data-ttu-id="54edc-180">若要了解如何与画图信息交互，请参阅[查看图层](#view-layers-information)和[查看画图探查器](#view-paint-profiler)。</span><span class="sxs-lookup"><span data-stu-id="54edc-180">To learn how to interact with the paint information, see [View layers](#view-layers-information) and [View paint profiler](#view-paint-profiler).</span></span>  

## <span data-ttu-id="54edc-181">保存录制</span><span class="sxs-lookup"><span data-stu-id="54edc-181">Save a recording</span></span>   

<span data-ttu-id="54edc-182">若要保存录制，请右键单击，然后选择 "**保存配置文件**"。</span><span class="sxs-lookup"><span data-stu-id="54edc-182">To save a recording, right-click and select **Save Profile**.</span></span>  

> ##### <span data-ttu-id="54edc-183">图 9</span><span class="sxs-lookup"><span data-stu-id="54edc-183">Figure 9</span></span>  
> **<span data-ttu-id="54edc-184">保存配置文件</span><span class="sxs-lookup"><span data-stu-id="54edc-184">Save Profile</span></span>**  
> ![保存配置文件][ImageSaveProfile]  

## <span data-ttu-id="54edc-186">加载录制</span><span class="sxs-lookup"><span data-stu-id="54edc-186">Load a recording</span></span>   

<span data-ttu-id="54edc-187">若要加载录制，请右键单击，然后选择 "**加载配置文件**"。</span><span class="sxs-lookup"><span data-stu-id="54edc-187">To load a recording, right-click and select **Load Profile**.</span></span>  

> ##### <span data-ttu-id="54edc-188">图 10</span><span class="sxs-lookup"><span data-stu-id="54edc-188">Figure 10</span></span>  
> **<span data-ttu-id="54edc-189">加载配置文件</span><span class="sxs-lookup"><span data-stu-id="54edc-189">Load Profile</span></span>**  
> ![加载配置文件][ImageLoadProfile]  

## <span data-ttu-id="54edc-191">清除上一个录制</span><span class="sxs-lookup"><span data-stu-id="54edc-191">Clear the previous recording</span></span>   

<span data-ttu-id="54edc-192">录制后，按 "**清除**录制 ![ " 清除录制 ][ImageClearRecordingIcon] 以从 "**性能**" 面板中清除该录制内容。</span><span class="sxs-lookup"><span data-stu-id="54edc-192">After making a recording, press **Clear recording** ![Clear recording][ImageClearRecordingIcon] to clear that recording from the **Performance** panel.</span></span>  

> ##### <span data-ttu-id="54edc-193">图 11</span><span class="sxs-lookup"><span data-stu-id="54edc-193">Figure 11</span></span>  
> <span data-ttu-id="54edc-194">清除录制</span><span class="sxs-lookup"><span data-stu-id="54edc-194">Clear recording</span></span>  
> ![清除录制][ImageClearRecording]  

## <span data-ttu-id="54edc-196">分析性能记录</span><span class="sxs-lookup"><span data-stu-id="54edc-196">Analyze a performance recording</span></span>   

<span data-ttu-id="54edc-197">在[记录运行时性能](#record-runtime-performance)或[记录加载性能](#record-load-performance)后，"**性能**" 面板会提供大量数据来分析所发生的情况的性能。</span><span class="sxs-lookup"><span data-stu-id="54edc-197">After you [record runtime performance](#record-runtime-performance) or [record load performance](#record-load-performance), the **Performance** panel provides a lot of data for analyzing the performance of what just happened.</span></span>  

### <span data-ttu-id="54edc-198">选择部分录制</span><span class="sxs-lookup"><span data-stu-id="54edc-198">Select a portion of a recording</span></span>   

<span data-ttu-id="54edc-199">在**概述**中向左或向右拖动鼠标，选择部分录制。</span><span class="sxs-lookup"><span data-stu-id="54edc-199">Drag your mouse left or right across the **Overview** to select a portion of a recording.</span></span>  <span data-ttu-id="54edc-200">**概述**是包含**FPS**、 **CPU**和**网络**图表的部分。</span><span class="sxs-lookup"><span data-stu-id="54edc-200">The **Overview** is the section that contains the **FPS**, **CPU**, and **NET** charts.</span></span>  

> ##### <span data-ttu-id="54edc-201">图 12</span><span class="sxs-lookup"><span data-stu-id="54edc-201">Figure 12</span></span>  
> <span data-ttu-id="54edc-202">在概述中拖动鼠标以缩放</span><span class="sxs-lookup"><span data-stu-id="54edc-202">Dragging the mouse across the Overview to zoom</span></span>  
> ![在概述中拖动鼠标以缩放][ImageZoom]  

<span data-ttu-id="54edc-204">要使用键盘选择某个部分，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="54edc-204">To select a portion using the keyboard:</span></span>  

1.  <span data-ttu-id="54edc-205">单击**主**节的背景，或单击它旁边的任何部分（如**交互**、**网络**或**GPU**）。</span><span class="sxs-lookup"><span data-stu-id="54edc-205">Click on the background of the **Main** section, or any of the sections next to it, such as **Interactions**, **Network**, or **GPU**.</span></span>  <span data-ttu-id="54edc-206">只有当其中一个分区处于焦点时，此键盘工作流才有效。</span><span class="sxs-lookup"><span data-stu-id="54edc-206">This keyboard workflow only works when one of these sections is in focus.</span></span>  
1.  <span data-ttu-id="54edc-207">使用 `W` 、 `A` 、 `S` 、 `D` 键进行放大、向左移动、缩小和向右移动。</span><span class="sxs-lookup"><span data-stu-id="54edc-207">Use the `W`, `A`, `S`, `D` keys to zoom in, move left, zoom out, and move right, respectively.</span></span>  

<span data-ttu-id="54edc-208">若要使用触控板选择部分，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="54edc-208">To select a portion using a trackpad:</span></span>  

1.  <span data-ttu-id="54edc-209">将鼠标悬停在 "**概述**" 部分或 "**详细信息**" 部分。</span><span class="sxs-lookup"><span data-stu-id="54edc-209">Hover your mouse over the **Overview** section or the **Details** section.</span></span>  <span data-ttu-id="54edc-210">"**概述**" 部分是包含 " **FPS**"、" **CPU**" 和 "**网络**" 图表的区域。</span><span class="sxs-lookup"><span data-stu-id="54edc-210">The **Overview** section is the area containing the **FPS**, **CPU**, and **NET** charts.</span></span>  <span data-ttu-id="54edc-211">"**详细信息**" 部分是包含**主要**部分、"**交互**" 部分等的区域。</span><span class="sxs-lookup"><span data-stu-id="54edc-211">The **Details** section is the area containing the **Main** section, the **Interactions** section, and so on.</span></span>  
1.  <span data-ttu-id="54edc-212">使用两根手指，向上轻扫以缩小，向左轻扫可向左移动，向下轻扫以放大，向右轻扫以向右移动。</span><span class="sxs-lookup"><span data-stu-id="54edc-212">Using two fingers, swipe up to zoom out, swipe left to move left, swipe down to zoom in, and swipe right to move right.</span></span>  

<span data-ttu-id="54edc-213">若要在**主**分区或任何邻居中滚动较长的火焰图表，请单击并按住鼠标上下拖动。</span><span class="sxs-lookup"><span data-stu-id="54edc-213">To scroll a long flame chart in the **Main** section or any of the neighbors, click and hold while dragging up and down.</span></span>  <span data-ttu-id="54edc-214">向左和向右拖动以移动所选录制部分。</span><span class="sxs-lookup"><span data-stu-id="54edc-214">Drag left and right to move what portion of the recording is selected.</span></span>  

### <span data-ttu-id="54edc-215">搜索活动</span><span class="sxs-lookup"><span data-stu-id="54edc-215">Search activities</span></span>   

<span data-ttu-id="54edc-216">按 `Control` + `F` \ （Windows \）或 `Command` + `F` \ （macOS \）打开 "**性能**" 面板底部的 "搜索" 框。</span><span class="sxs-lookup"><span data-stu-id="54edc-216">Press `Control`+`F` \(Windows\) or `Command`+`F` \(macOS\) to open the search box at the bottom of the **Performance** panel.</span></span>  

> ##### <span data-ttu-id="54edc-217">图 13</span><span class="sxs-lookup"><span data-stu-id="54edc-217">Figure 13</span></span>  
> <span data-ttu-id="54edc-218">在窗口底部的 "搜索" 框中使用 regex 查找以 ... 开头的任何活动</span><span class="sxs-lookup"><span data-stu-id="54edc-218">Using regex in the search box at the bottom of the window to find any activity that begins with</span></span> `E`  
> ![搜索框][ImageSearch]  

<span data-ttu-id="54edc-220">若要导航与查询匹配的活动，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="54edc-220">To navigate activities that match your query:</span></span>  

*   <span data-ttu-id="54edc-221">使用**前面**的 "上一个" 和 "下一个" ![ ][ImagePreviousIcon] **Next** ![ ][ImageNextIcon] 按钮。</span><span class="sxs-lookup"><span data-stu-id="54edc-221">Use the **Previous** ![Previous][ImagePreviousIcon] and **Next** ![Next][ImageNextIcon] buttons.</span></span>  
*   <span data-ttu-id="54edc-222">按下 `Shift` + `Enter` 选择 "上一 `Enter` 步" 或选择下一个。</span><span class="sxs-lookup"><span data-stu-id="54edc-222">Press `Shift`+`Enter` to select the previous or `Enter` to select the next.</span></span>  

<span data-ttu-id="54edc-223">修改查询设置：</span><span class="sxs-lookup"><span data-stu-id="54edc-223">To modify query settings:</span></span>  

*   <span data-ttu-id="54edc-224">按**大小**写区分大小 ![ 写 ][ImageSearchCaseIcon] 以使查询区分大小写。</span><span class="sxs-lookup"><span data-stu-id="54edc-224">Press **Case sensitive** ![Case sensitive][ImageSearchCaseIcon] to make the query case sensitive.</span></span>  
*   <span data-ttu-id="54edc-225">按**regex** ![ regex ][ImageSearchRegexIcon] 在查询中使用正则表达式。</span><span class="sxs-lookup"><span data-stu-id="54edc-225">Press **Regex** ![Regex][ImageSearchRegexIcon] to use a regular expression in your query.</span></span>  

<span data-ttu-id="54edc-226">若要隐藏搜索框，请按 "**取消**"。</span><span class="sxs-lookup"><span data-stu-id="54edc-226">To hide the search box, press **Cancel**.</span></span>  

### <span data-ttu-id="54edc-227">查看主线程活动</span><span class="sxs-lookup"><span data-stu-id="54edc-227">View main thread activity</span></span>   

<span data-ttu-id="54edc-228">使用**主**部分查看在页面的主线程上发生的活动。</span><span class="sxs-lookup"><span data-stu-id="54edc-228">Use the **Main** section to view activity that occurred on the main thread of the page.</span></span>  

> ##### <span data-ttu-id="54edc-229">图 14</span><span class="sxs-lookup"><span data-stu-id="54edc-229">Figure 14</span></span>  
> <span data-ttu-id="54edc-230">**主要**部分</span><span class="sxs-lookup"><span data-stu-id="54edc-230">The **Main** section</span></span>  
> ![主要部分][ImageMain]  

<span data-ttu-id="54edc-232">单击事件可在 "**摘要**" 选项卡中查看有关它的详细信息。 DevTools 概述所选事件。</span><span class="sxs-lookup"><span data-stu-id="54edc-232">Click on an event to view more information about it in the **Summary** tab.  DevTools outlines the selected event.</span></span>  

> ##### <span data-ttu-id="54edc-233">图 15</span><span class="sxs-lookup"><span data-stu-id="54edc-233">Figure 15</span></span>  
> <span data-ttu-id="54edc-234">有关 `anonymous` "**摘要**" 选项卡中的函数的详细信息</span><span class="sxs-lookup"><span data-stu-id="54edc-234">More information about the `anonymous` function in the **Summary** tab</span></span>  
> ![有关 "摘要" 选项卡中的匿名函数的详细信息][ImageMainEventSummary]  

<span data-ttu-id="54edc-236">DevTools 表示带有火焰图表的主线程活动。</span><span class="sxs-lookup"><span data-stu-id="54edc-236">DevTools represents main thread activity with a flame chart.</span></span>  <span data-ttu-id="54edc-237">X 轴表示一段时间内的录制。</span><span class="sxs-lookup"><span data-stu-id="54edc-237">The x-axis represents the recording over time.</span></span>  <span data-ttu-id="54edc-238">Y 轴表示调用堆栈。</span><span class="sxs-lookup"><span data-stu-id="54edc-238">The y-axis represents the call stack.</span></span>  <span data-ttu-id="54edc-239">顶部的事件会导致其下方的事件。</span><span class="sxs-lookup"><span data-stu-id="54edc-239">The events on top cause the events below it.</span></span>  

> ##### <span data-ttu-id="54edc-240">图 16</span><span class="sxs-lookup"><span data-stu-id="54edc-240">Figure 16</span></span>  
> <span data-ttu-id="54edc-241">**主**部分中的火焰图</span><span class="sxs-lookup"><span data-stu-id="54edc-241">A flame chart in the **Main** section</span></span>  
> ![火焰图][ImageFlameChart]  

<span data-ttu-id="54edc-243">在[图 16](#figure-16)中， `click` 事件导致 `Function Call` `activitytabs.js` 行53上出现 a。</span><span class="sxs-lookup"><span data-stu-id="54edc-243">In [Figure 16](#figure-16), a `click` event caused a `Function Call` in `activitytabs.js` on line 53.</span></span>  <span data-ttu-id="54edc-244">`Function Call`你将看到调用了一个匿名函数。</span><span class="sxs-lookup"><span data-stu-id="54edc-244">Below `Function Call` you see that an anonymous function was called.</span></span>  <span data-ttu-id="54edc-245">调用了称为的匿名函数 `a` `wait` `Minor GC` 。</span><span class="sxs-lookup"><span data-stu-id="54edc-245">The anonymous function called `a`, which called `wait`, which called `Minor GC`.</span></span>  

<span data-ttu-id="54edc-246">DevTools 分配脚本随机颜色。</span><span class="sxs-lookup"><span data-stu-id="54edc-246">DevTools assigns scripts random colors.</span></span>  <span data-ttu-id="54edc-247">在[图 16](#figure-16)中，一个脚本的函数调用的颜色为浅绿色。</span><span class="sxs-lookup"><span data-stu-id="54edc-247">In [Figure 16](#figure-16), function calls from one script are colored light green.</span></span>  <span data-ttu-id="54edc-248">来自另一个脚本的通话的颜色为米色。</span><span class="sxs-lookup"><span data-stu-id="54edc-248">Calls from another script are colored beige.</span></span>  <span data-ttu-id="54edc-249">较深的黄色表示脚本活动，紫色事件表示呈现活动。</span><span class="sxs-lookup"><span data-stu-id="54edc-249">The darker yellow represents scripting activity, and the purple event represents rendering activity.</span></span>  <span data-ttu-id="54edc-250">这些较暗的黄色和紫色事件在所有录制中保持一致。</span><span class="sxs-lookup"><span data-stu-id="54edc-250">These darker yellow and purple events are consistent across all recordings.</span></span>  

<span data-ttu-id="54edc-251">如果想要隐藏 JavaScript 调用的详细火焰图表，请参阅[禁用 javascript 示例](#disable-javascript-samples)。</span><span class="sxs-lookup"><span data-stu-id="54edc-251">See [Disable JavaScript samples](#disable-javascript-samples) if you want to hide the detailed flame chart of JavaScript calls.</span></span>  <span data-ttu-id="54edc-252">如果已禁用 JS 示例，则只能查看 `Event: click` `Function Call` [图 16](#figure-16)中的高级别事件，例如和。</span><span class="sxs-lookup"><span data-stu-id="54edc-252">When JS samples are disabled, you only see high-level events such as `Event: click` and `Function Call` from [Figure 16](#figure-16).</span></span>  

### <span data-ttu-id="54edc-253">查看表中的活动</span><span class="sxs-lookup"><span data-stu-id="54edc-253">View activities in a table</span></span>   

<span data-ttu-id="54edc-254">录制页面后，不需要仅依赖**主要**部分来分析活动。</span><span class="sxs-lookup"><span data-stu-id="54edc-254">After recording a page, you do not need to rely solely on the **Main** section to analyze activities.</span></span>  <span data-ttu-id="54edc-255">DevTools 还提供了用于分析活动的三个表格视图。</span><span class="sxs-lookup"><span data-stu-id="54edc-255">DevTools also provides three tabular views for analyzing activities.</span></span>  <span data-ttu-id="54edc-256">每个视图为您提供了不同的活动视角：</span><span class="sxs-lookup"><span data-stu-id="54edc-256">Each view gives you a different perspective on the activities:</span></span>  

*   <span data-ttu-id="54edc-257">当您想要查看导致大部分工作的根活动时，请使用["**调用树**" 选项卡](#the-call-tree-tab)。</span><span class="sxs-lookup"><span data-stu-id="54edc-257">When you want to view the root activities that cause the most work, use [the **Call Tree** tab](#the-call-tree-tab).</span></span>  
*   <span data-ttu-id="54edc-258">当您想要查看最常被直接花费的时间的活动时，请使用["**下**" 选项卡](#the-bottom-up-tab)。</span><span class="sxs-lookup"><span data-stu-id="54edc-258">When you want to view the activities where the most time was directly spent, use [the **Bottom-Up** tab](#the-bottom-up-tab).</span></span>  
*   <span data-ttu-id="54edc-259">如果要按录制期间的顺序查看活动，请使用["**事件日志**" 选项卡](#the-event-log-tab)。</span><span class="sxs-lookup"><span data-stu-id="54edc-259">When you want to view the activities in the order in which they occurred during the recording, use [the **Event Log** tab](#the-event-log-tab).</span></span>  

> [!NOTE]
> <span data-ttu-id="54edc-260">接下来的三个部分都是指同一演示。</span><span class="sxs-lookup"><span data-stu-id="54edc-260">The next three sections all refer to the same demo.</span></span>  <span data-ttu-id="54edc-261">在 "[活动" 选项卡演示][ActivityTabsDemo]中自行运行演示。</span><span class="sxs-lookup"><span data-stu-id="54edc-261">Run the demo yourself at [Activity Tabs Demo][ActivityTabsDemo].</span></span>  

#### <span data-ttu-id="54edc-262">根活动</span><span class="sxs-lookup"><span data-stu-id="54edc-262">Root activities</span></span>   

<span data-ttu-id="54edc-263">下面是 "**调用树**" 选项卡、"**下移至**" 选项卡和 "**事件日志**" 部分中提及的**根活动**概念的说明。</span><span class="sxs-lookup"><span data-stu-id="54edc-263">Here is an explanation of the **root activities** concept that is mentioned in the **Call Tree** tab, **Bottom-Up** tab, and **Event Log** sections.</span></span>  

<span data-ttu-id="54edc-264">根活动是导致浏览器执行某些工作的操作。</span><span class="sxs-lookup"><span data-stu-id="54edc-264">Root activities are those which cause the browser to do some work.</span></span>  <span data-ttu-id="54edc-265">例如，当您单击页面时，浏览器会将 `Event` 活动作为根活动触发。</span><span class="sxs-lookup"><span data-stu-id="54edc-265">For example, when you click a page, the browser fires an `Event` activity as the root activity.</span></span>  <span data-ttu-id="54edc-266">这 `Event` 可能会导致处理程序运行，依此类推。</span><span class="sxs-lookup"><span data-stu-id="54edc-266">That `Event` might cause a handler to run, and so on.</span></span>  

<span data-ttu-id="54edc-267">在**主**区域的火焰图表中，根活动位于图表顶部。</span><span class="sxs-lookup"><span data-stu-id="54edc-267">In the flame chart of the **Main** section, root activities are at the top of the chart.</span></span>  <span data-ttu-id="54edc-268">在 "**调用树**" 和 "**事件日志**" 选项卡中，根活动是顶级项目。</span><span class="sxs-lookup"><span data-stu-id="54edc-268">In the **Call Tree** and **Event Log** tabs, root activities are the top-level items.</span></span>  

<span data-ttu-id="54edc-269">有关根活动的示例，请参阅["调用树" 选项卡](#the-call-tree-tab)。</span><span class="sxs-lookup"><span data-stu-id="54edc-269">See [The Call Tree tab](#the-call-tree-tab) for an example of root activities.</span></span>  

#### <span data-ttu-id="54edc-270">"调用树" 选项卡</span><span class="sxs-lookup"><span data-stu-id="54edc-270">The Call Tree tab</span></span>   

<span data-ttu-id="54edc-271">使用 "**调用树**" 选项卡查看哪些[根活动](#root-activities)导致最大的工作。</span><span class="sxs-lookup"><span data-stu-id="54edc-271">Use the **Call Tree** tab to view which [root activities](#root-activities) cause the most work.</span></span>  

<span data-ttu-id="54edc-272">"**调用树**" 选项卡仅在录制的选定部分中显示活动。</span><span class="sxs-lookup"><span data-stu-id="54edc-272">The **Call Tree** tab only displays activities during the selected portion of the recording.</span></span>  <span data-ttu-id="54edc-273">请参阅[选择部分录制](#select-a-portion-of-a-recording)内容，了解如何选择部分内容。</span><span class="sxs-lookup"><span data-stu-id="54edc-273">See [Select a portion of a recording](#select-a-portion-of-a-recording) to learn how to select portions.</span></span>  

> ##### <span data-ttu-id="54edc-274">图 17</span><span class="sxs-lookup"><span data-stu-id="54edc-274">Figure 17</span></span>  
> <span data-ttu-id="54edc-275">"**调用树**" 选项卡</span><span class="sxs-lookup"><span data-stu-id="54edc-275">The **Call Tree** tab</span></span>  
> !["调用树" 选项卡][ImageCallTree]  

<span data-ttu-id="54edc-277">在[图 17](#figure-17)中，"**活动**" 列中的项目的顶级级别，例如 " `Evaluate Script` 根活动" 和 " `Parse HTML` 是根活动"。</span><span class="sxs-lookup"><span data-stu-id="54edc-277">In [Figure 17](#figure-17), the top-level of items in the **Activity** column, such as `Evaluate Script` and `Parse HTML` are root activities.</span></span>  <span data-ttu-id="54edc-278">嵌套表示调用堆栈。</span><span class="sxs-lookup"><span data-stu-id="54edc-278">The nesting represents the call stack.</span></span>  <span data-ttu-id="54edc-279">例如，如[图 17](#figure-17)所示，导致出现 `Parse HTML` `Evaluate Script` `Compile Script` 和 `(anonymous)` 。</span><span class="sxs-lookup"><span data-stu-id="54edc-279">For example, in [Figure 17](#figure-17), `Parse HTML` which caused `Evaluate Script` which caused `Compile Script` and `(anonymous)`.</span></span>  

<span data-ttu-id="54edc-280">**自我时间**表示该活动直接花费的时间。</span><span class="sxs-lookup"><span data-stu-id="54edc-280">**Self Time** represents the time directly spent in that activity.</span></span>  <span data-ttu-id="54edc-281">"**总时间**" 表示该活动或任何子活动所花费的时间。</span><span class="sxs-lookup"><span data-stu-id="54edc-281">**Total Time** represents the time spent in that activity or any of the children.</span></span>  

<span data-ttu-id="54edc-282">单击 "**自时间**"、"**总时间**" 或 "**活动**"，按该列对表格进行排序。</span><span class="sxs-lookup"><span data-stu-id="54edc-282">Click **Self Time**, **Total Time**, or **Activity** to sort the table by that column.</span></span>  

<span data-ttu-id="54edc-283">使用 "**筛选**" 文本框按活动名称筛选事件。</span><span class="sxs-lookup"><span data-stu-id="54edc-283">Use the **Filter** text box to filter events by activity name.</span></span>  

<span data-ttu-id="54edc-284">默认情况下，"**分组**" 菜单设置为 "**无分组**"。</span><span class="sxs-lookup"><span data-stu-id="54edc-284">By default the **Grouping** menu is set to **No Grouping**.</span></span>  <span data-ttu-id="54edc-285">使用 "**分组**" 菜单基于各种条件对活动表进行排序。</span><span class="sxs-lookup"><span data-stu-id="54edc-285">Use the **Grouping** menu to sort the activity table based on various criteria.</span></span>  

<span data-ttu-id="54edc-286">单击 "**显示**最繁忙 ![ 的堆栈 ][ImageShowHeaviestStackIcon] " 显示最大的堆栈，将另一个表显示在**活动**表的右侧。</span><span class="sxs-lookup"><span data-stu-id="54edc-286">Click **Show Heaviest Stack** ![Show Heaviest Stack][ImageShowHeaviestStackIcon] to reveal another table to the right of the **Activity** table.</span></span>  <span data-ttu-id="54edc-287">单击活动以填充最大的**堆栈**表。</span><span class="sxs-lookup"><span data-stu-id="54edc-287">Click on an activity to populate the **Heaviest Stack** table.</span></span>  <span data-ttu-id="54edc-288">"最**繁忙的堆栈**" 表显示所选活动的哪些子元素运行时间最长。</span><span class="sxs-lookup"><span data-stu-id="54edc-288">The **Heaviest Stack** table shows you which children of the selected activity took the longest time to run.</span></span>  

#### <span data-ttu-id="54edc-289">"下" 选项卡</span><span class="sxs-lookup"><span data-stu-id="54edc-289">The Bottom-Up tab</span></span>   

<span data-ttu-id="54edc-290">使用 "**下**" 选项卡查看哪些活动直接占用总时间。</span><span class="sxs-lookup"><span data-stu-id="54edc-290">Use the **Bottom-Up** tab to view which activities directly took up the most time in aggregate.</span></span>  

<span data-ttu-id="54edc-291">**自下而上**的选项卡仅显示录制的选定部分中的活动。</span><span class="sxs-lookup"><span data-stu-id="54edc-291">The **Bottom-Up** tab only displays activities during the selected portion of the recording.</span></span>  <span data-ttu-id="54edc-292">请参阅[选择部分录制](#select-a-portion-of-a-recording)内容，了解如何选择部分内容。</span><span class="sxs-lookup"><span data-stu-id="54edc-292">See [Select a portion of a recording](#select-a-portion-of-a-recording) to learn how to select portions.</span></span>  

> ##### <span data-ttu-id="54edc-293">图18</span><span class="sxs-lookup"><span data-stu-id="54edc-293">Figure 18</span></span>  
> <span data-ttu-id="54edc-294">"**下**" 选项卡</span><span class="sxs-lookup"><span data-stu-id="54edc-294">The **Bottom-Up** tab</span></span>  
> !["下" 选项卡][ImageBottomUp]  

<span data-ttu-id="54edc-296">在[图 18](#figure-18)的 "**主要**" 部分的 "火焰" 部分中，查看几乎几乎没有运行所有时间 `Parse HTML` 。</span><span class="sxs-lookup"><span data-stu-id="54edc-296">In the **Main** section flame chart of [Figure 18](#figure-18), see that almost practically all of the time was spent running `Parse HTML`.</span></span>  <span data-ttu-id="54edc-297">[图 18](#figure-18)的 "**下**" 选项卡中的最高活动是 `Parse HTML` 。</span><span class="sxs-lookup"><span data-stu-id="54edc-297">The top activity in the **Bottom-Up** tab of [Figure 18](#figure-18) is `Parse HTML`.</span></span>  <!--In the flame chart of [Figure 18](#figure-18), the yellow below the calls to `wait` are actually thousands of `Minor GC` calls.  -->  <span data-ttu-id="54edc-298">请参阅下一个最昂贵的活动（在 "**下**" 选项卡中） `Layout` 。</span><span class="sxs-lookup"><span data-stu-id="54edc-298">See in the **Bottom-Up** tab, the next most expensive activity is `Layout`.</span></span>  

<span data-ttu-id="54edc-299">"**自时间**" 列表示在该活动中直接占用的所有事件的总时间。</span><span class="sxs-lookup"><span data-stu-id="54edc-299">The **Self Time** column represents the aggregated time spent directly in that activity, across all of the occurrences.</span></span>  

<span data-ttu-id="54edc-300">"**总时间**" 列表示该活动或任何子活动所用的聚合时间。</span><span class="sxs-lookup"><span data-stu-id="54edc-300">The **Total Time** column represents aggregated time spent in that activity or any of the children.</span></span>  

#### <span data-ttu-id="54edc-301">"事件日志" 选项卡</span><span class="sxs-lookup"><span data-stu-id="54edc-301">The Event Log tab</span></span>   

<span data-ttu-id="54edc-302">使用 "**事件日志**" 选项卡，按录制过程中发生的顺序查看活动。</span><span class="sxs-lookup"><span data-stu-id="54edc-302">Use the **Event Log** tab to view activities in the order in which they occurred during the recording.</span></span>  

<span data-ttu-id="54edc-303">"**事件日志**" 选项卡仅显示录制的选定部分中的活动。</span><span class="sxs-lookup"><span data-stu-id="54edc-303">The **Event Log** tab only displays activities during the selected portion of the recording.</span></span>  <span data-ttu-id="54edc-304">请参阅[选择部分录制](#select-a-portion-of-a-recording)内容，了解如何选择部分内容。</span><span class="sxs-lookup"><span data-stu-id="54edc-304">See [Select a portion of a recording](#select-a-portion-of-a-recording) to learn how to select portions.</span></span>  

> ##### <span data-ttu-id="54edc-305">图19</span><span class="sxs-lookup"><span data-stu-id="54edc-305">Figure 19</span></span>  
> <span data-ttu-id="54edc-306">"**事件日志**" 选项卡</span><span class="sxs-lookup"><span data-stu-id="54edc-306">The **Event Log** tab</span></span>  
> !["事件日志" 选项卡][ImageEventLog]  

<span data-ttu-id="54edc-308">"**开始时间**" 列表示活动开始的点，相对于录制的开始时间。</span><span class="sxs-lookup"><span data-stu-id="54edc-308">The **Start Time** column represents the point at which that activity started, relative to the start of the recording.</span></span>  <span data-ttu-id="54edc-309">例如， `175.7 ms` [图 19](#figure-19)中所选项目的开始时间表示活动在录制开始后启动175.7 毫秒。</span><span class="sxs-lookup"><span data-stu-id="54edc-309">For example, the start time of `175.7 ms` for the selected item in [Figure 19](#figure-19) means that activity started 175.7 ms after the recording started.</span></span>  

<span data-ttu-id="54edc-310">"**自时间**" 列表示直接在该活动中花费的时间。</span><span class="sxs-lookup"><span data-stu-id="54edc-310">The **Self Time** column represents the time spent directly in that activity.</span></span>  

<span data-ttu-id="54edc-311">"**总时间**" 列表示直接在该活动或任何子活动中所花费的时间。</span><span class="sxs-lookup"><span data-stu-id="54edc-311">The **Total Time** columns represents time spent directly in that activity or in any of the children.</span></span>  

<span data-ttu-id="54edc-312">单击 "**开始时间**"、"**自时间**" 或 "**总时间**"，按该列对表格进行排序。</span><span class="sxs-lookup"><span data-stu-id="54edc-312">Click **Start Time**, **Self Time**, or **Total Time** to sort the table by that column.</span></span>

<span data-ttu-id="54edc-313">使用 "**筛选**" 文本框按名称筛选活动。</span><span class="sxs-lookup"><span data-stu-id="54edc-313">Use the **Filter** text box to filter activities by name.</span></span>  

<span data-ttu-id="54edc-314">使用 "**工期**" 菜单筛选出所有时间不超过1毫秒或15毫秒的活动。</span><span class="sxs-lookup"><span data-stu-id="54edc-314">Use the **Duration** menu to filter out any activities that took less than 1 ms or 15 ms.</span></span>  <span data-ttu-id="54edc-315">默认情况下，"**持续时间**" 菜单设置为 "**全部**"，表示显示所有活动。</span><span class="sxs-lookup"><span data-stu-id="54edc-315">By default the **Duration** menu is set to **All**, meaning all activities are shown.</span></span>  

<span data-ttu-id="54edc-316">禁用**加载**、**脚本**、**呈现**或**绘制**复选框，以筛选出这些类别中的所有活动。</span><span class="sxs-lookup"><span data-stu-id="54edc-316">Disable the **Loading**, **Scripting**, **Rendering**, or **Painting** checkboxes to filter out all activities from those categories.</span></span>  

### <span data-ttu-id="54edc-317">查看 GPU 活动</span><span class="sxs-lookup"><span data-stu-id="54edc-317">View GPU activity</span></span>   

<span data-ttu-id="54edc-318">查看**gpu**部分中的 gpu 活动。</span><span class="sxs-lookup"><span data-stu-id="54edc-318">View GPU activity in the **GPU** section.</span></span>  

> ##### <span data-ttu-id="54edc-319">图20</span><span class="sxs-lookup"><span data-stu-id="54edc-319">Figure 20</span></span>  
> <span data-ttu-id="54edc-320">**GPU**部分</span><span class="sxs-lookup"><span data-stu-id="54edc-320">The **GPU** section</span></span>  
> ![GPU 部分][ImageGpu]  

### <span data-ttu-id="54edc-322">查看光栅活动</span><span class="sxs-lookup"><span data-stu-id="54edc-322">View raster activity</span></span>   

<span data-ttu-id="54edc-323">查看**光栅**区中的 "光栅" 活动。</span><span class="sxs-lookup"><span data-stu-id="54edc-323">View raster activity in the **Raster** section.</span></span>  

> ##### <span data-ttu-id="54edc-324">图21</span><span class="sxs-lookup"><span data-stu-id="54edc-324">Figure 21</span></span>  
> <span data-ttu-id="54edc-325">"**光栅**" 部分</span><span class="sxs-lookup"><span data-stu-id="54edc-325">The **Raster** section</span></span>  
> !["光栅" 部分][ImageRaster]  

### <span data-ttu-id="54edc-327">查看交互</span><span class="sxs-lookup"><span data-stu-id="54edc-327">View interactions</span></span>   

<span data-ttu-id="54edc-328">使用 "**交互**" 部分查找和分析录制期间发生的用户交互。</span><span class="sxs-lookup"><span data-stu-id="54edc-328">Use the **Interactions** section to find and analyze user interactions that happened during the recording.</span></span>  

> ##### <span data-ttu-id="54edc-329">图22</span><span class="sxs-lookup"><span data-stu-id="54edc-329">Figure 22</span></span>  
> <span data-ttu-id="54edc-330">"**交互**" 部分</span><span class="sxs-lookup"><span data-stu-id="54edc-330">The **Interactions** section</span></span>  
> !["交互" 部分][ImageInteractions]  

<span data-ttu-id="54edc-332">交互底部的红线表示等待主线程所用的时间。</span><span class="sxs-lookup"><span data-stu-id="54edc-332">A red line at the bottom of an interaction represents time spent waiting for the main thread.</span></span>  

<span data-ttu-id="54edc-333">单击交互以在 "**摘要**" 选项卡中查看有关它的详细信息。</span><span class="sxs-lookup"><span data-stu-id="54edc-333">Click an interaction to view more information about it in the **Summary** tab.</span></span>  

### <span data-ttu-id="54edc-334">分析每秒帧数（FPS）</span><span class="sxs-lookup"><span data-stu-id="54edc-334">Analyze frames per second (FPS)</span></span>   

<span data-ttu-id="54edc-335">DevTools 提供多种方法来分析每秒帧数：</span><span class="sxs-lookup"><span data-stu-id="54edc-335">DevTools provides numerous ways to analyze frames per second:</span></span>  

*   <span data-ttu-id="54edc-336">使用[ **fps**图](#the-fps-chart)大致了解录制期间的 FPS。</span><span class="sxs-lookup"><span data-stu-id="54edc-336">Use [the **FPS** chart](#the-fps-chart) to get an overview of FPS over the duration of the recording.</span></span>  
*   <span data-ttu-id="54edc-337">使用["**框架**" 部分](#the-frames-section)可查看特定帧所用时间。</span><span class="sxs-lookup"><span data-stu-id="54edc-337">Use [the **Frames** section](#the-frames-section) to view how long a particular frame took.</span></span>  
*   <span data-ttu-id="54edc-338">当页面运行时，使用**fps 计量**器以实时估计 fps。</span><span class="sxs-lookup"><span data-stu-id="54edc-338">Use the **FPS meter** for a realtime estimate of FPS as the page runs.</span></span>  <span data-ttu-id="54edc-339">请参阅以[FPS 计量器实时查看每秒帧数](#view-frames-per-second-in-realtime-with-the-fps-meter)。</span><span class="sxs-lookup"><span data-stu-id="54edc-339">See [View frames per second in realtime with the FPS meter](#view-frames-per-second-in-realtime-with-the-fps-meter).</span></span>  

#### <span data-ttu-id="54edc-340">FPS 图表</span><span class="sxs-lookup"><span data-stu-id="54edc-340">The FPS chart</span></span>   

<span data-ttu-id="54edc-341">**FPS**图表提供整个录制期间的帧速率的概览。</span><span class="sxs-lookup"><span data-stu-id="54edc-341">The **FPS** chart provides an overview of the frame rate across the duration of a recording.</span></span>  <span data-ttu-id="54edc-342">通常情况下，绿色条越高，帧速率越好。</span><span class="sxs-lookup"><span data-stu-id="54edc-342">In general, the higher the green bar, the better the frame rate.</span></span>  

<span data-ttu-id="54edc-343">**FPS**图表上方的红色条是一条警告，表明帧速率降低的可能会损坏用户的体验。</span><span class="sxs-lookup"><span data-stu-id="54edc-343">A red bar above the **FPS** chart is a warning that the frame rate dropped so low that it probably harmed the user's experience.</span></span>  

> ##### <span data-ttu-id="54edc-344">图23</span><span class="sxs-lookup"><span data-stu-id="54edc-344">Figure 23</span></span>  
> <span data-ttu-id="54edc-345">FPS 图表</span><span class="sxs-lookup"><span data-stu-id="54edc-345">The FPS chart</span></span>  
> ![FPS 图表][ImageFpsChart]  

#### <span data-ttu-id="54edc-347">"框架" 部分</span><span class="sxs-lookup"><span data-stu-id="54edc-347">The Frames section</span></span>   

<span data-ttu-id="54edc-348">"**框架**" 部分告诉你特定帧所花时间的确切时间。</span><span class="sxs-lookup"><span data-stu-id="54edc-348">The **Frames** section tells you exactly how long a particular frame took.</span></span>  

<span data-ttu-id="54edc-349">将鼠标悬停在框架上方以查看工具提示，了解有关它的详细信息。</span><span class="sxs-lookup"><span data-stu-id="54edc-349">Hover over a frame to view a tooltip with more information about it.</span></span>  

> ##### <span data-ttu-id="54edc-350">图24</span><span class="sxs-lookup"><span data-stu-id="54edc-350">Figure 24</span></span>  
> <span data-ttu-id="54edc-351">将鼠标悬停在框架上</span><span class="sxs-lookup"><span data-stu-id="54edc-351">Hovering over a frame</span></span>  
> ![将鼠标悬停在框架上][ImageFramesSection]  

<span data-ttu-id="54edc-353">单击框架可在 "**摘要**" 选项卡中查看有关该帧的详细信息。 DevTools 以蓝色显示所选帧的轮廓。</span><span class="sxs-lookup"><span data-stu-id="54edc-353">Click on a frame to view even more information about the frame in the **Summary** tab.  DevTools outlines the selected frame in blue.</span></span>  

> ##### <span data-ttu-id="54edc-354">图25</span><span class="sxs-lookup"><span data-stu-id="54edc-354">Figure 25</span></span>  
> <span data-ttu-id="54edc-355">在 "**摘要**" 选项卡中查看框架</span><span class="sxs-lookup"><span data-stu-id="54edc-355">Viewing a frame in the **Summary** tab</span></span>  
> ![在 "摘要" 选项卡中查看框架][ImageFrameSummary]  

### <span data-ttu-id="54edc-357">查看网络请求</span><span class="sxs-lookup"><span data-stu-id="54edc-357">View network requests</span></span>   

<span data-ttu-id="54edc-358">展开 "**网络**" 部分，查看录制期间出现的网络请求的瀑布。</span><span class="sxs-lookup"><span data-stu-id="54edc-358">Expand the **Network** section to view a waterfall of network requests that occurred during the recording.</span></span>  

> ##### <span data-ttu-id="54edc-359">图26</span><span class="sxs-lookup"><span data-stu-id="54edc-359">Figure 26</span></span>  
> <span data-ttu-id="54edc-360">"**网络**" 部分</span><span class="sxs-lookup"><span data-stu-id="54edc-360">The **Network** section</span></span>  
> !["网络" 部分][ImageNetworkRequest]  

<span data-ttu-id="54edc-362">请求按如下方式进行颜色编码：</span><span class="sxs-lookup"><span data-stu-id="54edc-362">Requests are color-coded as follows:</span></span>  

*   <span data-ttu-id="54edc-363">HTML： Blue</span><span class="sxs-lookup"><span data-stu-id="54edc-363">HTML: Blue</span></span>  
*   <span data-ttu-id="54edc-364">CSS：紫色</span><span class="sxs-lookup"><span data-stu-id="54edc-364">CSS: Purple</span></span>  
*   <span data-ttu-id="54edc-365">JS：黄色</span><span class="sxs-lookup"><span data-stu-id="54edc-365">JS: Yellow</span></span>  
*   <span data-ttu-id="54edc-366">图像：绿色</span><span class="sxs-lookup"><span data-stu-id="54edc-366">Images: Green</span></span>  

<span data-ttu-id="54edc-367">单击请求可在 "**摘要**" 选项卡中查看有关它的详细信息。 例如，在[图 26](#figure-26)中，"**摘要**" 选项卡显示有关 "**网络**" 部分中所选蓝色请求的详细信息。</span><span class="sxs-lookup"><span data-stu-id="54edc-367">Click on a request to view more information about it in the **Summary** tab.  For example, in [Figure 26](#figure-26) the **Summary** tab is displaying more information about the blue request that is selected in the **Network** section.</span></span>  

<span data-ttu-id="54edc-368">请求左上角的蓝色正方形表示它是优先级较高的请求。</span><span class="sxs-lookup"><span data-stu-id="54edc-368">A darker-blue square in the top-left of a request means it is a higher-priority request.</span></span>  <span data-ttu-id="54edc-369">较浅的蓝色正方形意味着优先级较低。</span><span class="sxs-lookup"><span data-stu-id="54edc-369">A lighter-blue square means lower-priority.</span></span>  <span data-ttu-id="54edc-370">例如，在[图 26](#figure-26)中，所选请求的优先级较高，其下方的绿色为较低优先级。</span><span class="sxs-lookup"><span data-stu-id="54edc-370">For example, in [Figure 26](#figure-26) the blue, selected request is higher-priority, and the green one below it is lower-priority.</span></span>  

<span data-ttu-id="54edc-371">在[图 27](#figure-27)中，请求由 `www.bing.com` 左侧的一条线、中间有一个深色部分和一个浅色部分以及右侧的线条表示。</span><span class="sxs-lookup"><span data-stu-id="54edc-371">In [Figure 27](#figure-27), the request for `www.bing.com` is represented by a line on the left, a bar in the middle with a dark portion and a light portion, and a line on the right.</span></span>  <span data-ttu-id="54edc-372">[图 28](#figure-28)显示了 "**网络**" 面板的 "**计时**" 选项卡中相同请求的对应表示形式。</span><span class="sxs-lookup"><span data-stu-id="54edc-372">[Figure 28](#figure-28) shows the corresponding representation of the same request in the **Timing** tab of the **Network** panel.</span></span>  <span data-ttu-id="54edc-373">下面介绍这两种表示形式如何相互映射：</span><span class="sxs-lookup"><span data-stu-id="54edc-373">Here is how these two representations map to each other:</span></span>

*   <span data-ttu-id="54edc-374">左侧线条是所有 `Connection Start` 事件组中的所有内容，包括一组事件。</span><span class="sxs-lookup"><span data-stu-id="54edc-374">The left line is everything up to the `Connection Start` group of events, inclusive.</span></span>  <span data-ttu-id="54edc-375">换句话说，它是在独占之前的所有内容 `Request Sent` 。</span><span class="sxs-lookup"><span data-stu-id="54edc-375">In other words, it is everything before `Request Sent`, exclusive.</span></span>  
*   <span data-ttu-id="54edc-376">条的灯部分为 `Request Sent` 和 `Waiting (TTFB)` 。</span><span class="sxs-lookup"><span data-stu-id="54edc-376">The light portion of the bar is `Request Sent` and `Waiting (TTFB)`.</span></span>  
*   <span data-ttu-id="54edc-377">条的深色部分为 `Content Download` 。</span><span class="sxs-lookup"><span data-stu-id="54edc-377">The dark portion of the bar is `Content Download`.</span></span>  
*   <span data-ttu-id="54edc-378">右线实质上是等待主线程所用的时间。</span><span class="sxs-lookup"><span data-stu-id="54edc-378">The right line is essentially time spent waiting for the main thread.</span></span>  <span data-ttu-id="54edc-379">这不在 "**计时**" 选项卡中表示。</span><span class="sxs-lookup"><span data-stu-id="54edc-379">This is not represented in the **Timing** tab.</span></span>  

> ##### <span data-ttu-id="54edc-380">图27</span><span class="sxs-lookup"><span data-stu-id="54edc-380">Figure 27</span></span>  
> <span data-ttu-id="54edc-381">请求的行条形图表示形式 `www.bing.com`</span><span class="sxs-lookup"><span data-stu-id="54edc-381">The line-bar representation of the `www.bing.com` request</span></span>  
> ![Www.bing.com 请求的行条形图表示形式][ImageLineBar]  

> ##### <span data-ttu-id="54edc-383">图28</span><span class="sxs-lookup"><span data-stu-id="54edc-383">Figure 28</span></span>  
> <span data-ttu-id="54edc-384">请求的**计时**选项卡表示形式 `www.bing.com`</span><span class="sxs-lookup"><span data-stu-id="54edc-384">The **Timing** tab representation of the `www.bing.com` request</span></span>  
> !["网络" 部分][ImageTiming]  

### <span data-ttu-id="54edc-386">查看内存度量值</span><span class="sxs-lookup"><span data-stu-id="54edc-386">View memory metrics</span></span>   

<span data-ttu-id="54edc-387">启用 "**内存**" 复选框以查看上次录制中的内存指标。</span><span class="sxs-lookup"><span data-stu-id="54edc-387">Enable the **Memory** checkbox to view memory metrics from the last recording.</span></span>  

> ##### <span data-ttu-id="54edc-388">图29</span><span class="sxs-lookup"><span data-stu-id="54edc-388">Figure 29</span></span>  
> <span data-ttu-id="54edc-389">"**内存**" 复选框</span><span class="sxs-lookup"><span data-stu-id="54edc-389">The **Memory** checkbox</span></span>  
> !["内存" 复选框][ImageMemory]  

<span data-ttu-id="54edc-391">DevTools 将在 "**摘要**" 选项卡上方显示一个新的 "**内存**" 图表。 **NET**图表下方还有一个新图表，称为**堆**。</span><span class="sxs-lookup"><span data-stu-id="54edc-391">DevTools displays a new **Memory** chart, above the **Summary** tab.  There is also a new chart below the **NET** chart, called **HEAP**.</span></span>  <span data-ttu-id="54edc-392">**堆**图表提供的信息与**内存**图表中的**JS 堆**行相同。</span><span class="sxs-lookup"><span data-stu-id="54edc-392">The **HEAP** chart provides the same information as the **JS Heap** line in the **Memory** chart.</span></span>  

> ##### <span data-ttu-id="54edc-393">图30</span><span class="sxs-lookup"><span data-stu-id="54edc-393">Figure 30</span></span>  
> <span data-ttu-id="54edc-394">内存指标，在 "**摘要**" 选项卡上方</span><span class="sxs-lookup"><span data-stu-id="54edc-394">Memory metrics, above the **Summary** tab</span></span>  
> ![内存指标][ImageMemoryMetrics]  

<span data-ttu-id="54edc-396">图表上的彩色线条将映射到图表上方的彩色复选框。</span><span class="sxs-lookup"><span data-stu-id="54edc-396">The colored lines on the chart map to the colored checkboxes above the chart.</span></span>  
<span data-ttu-id="54edc-397">禁用复选框以从图表中隐藏该类别。</span><span class="sxs-lookup"><span data-stu-id="54edc-397">Disable a checkbox to hide that category from the chart.</span></span>  

<span data-ttu-id="54edc-398">图表仅显示当前所选录制的区域。</span><span class="sxs-lookup"><span data-stu-id="54edc-398">The chart only displays the region of the recording that is currently selected.</span></span>  <span data-ttu-id="54edc-399">例如，在[图 30](#figure-30)中，**内存**图表仅显示 400 ms 标记到 1750 ms 标记之间的内存使用。</span><span class="sxs-lookup"><span data-stu-id="54edc-399">For example, in [Figure 30](#figure-30), the **Memory** chart is only showing memory usage from around the 400 ms mark to the 1750 ms mark.</span></span>  

### <span data-ttu-id="54edc-400">查看部分录制的持续时间</span><span class="sxs-lookup"><span data-stu-id="54edc-400">View the duration of a portion of a recording</span></span>   

<span data-ttu-id="54edc-401">分析类似于**网络**或**主**分区的分区时，有时需要对特定事件所花费的时间进行更精确的估计。</span><span class="sxs-lookup"><span data-stu-id="54edc-401">When analyzing a section like **Network** or **Main**, sometimes you need a more precise estimate of how long certain events took.</span></span>  <span data-ttu-id="54edc-402">按住 `Shift` ，单击并按住，然后向左或向右拖动以选择部分录制。</span><span class="sxs-lookup"><span data-stu-id="54edc-402">Hold `Shift`, click and hold, and drag left or right to select a portion of the recording.</span></span>  <span data-ttu-id="54edc-403">在所选内容的底部，DevTools 显示该部分花费的时间。</span><span class="sxs-lookup"><span data-stu-id="54edc-403">At the bottom of your selection, DevTools shows how long that portion took.</span></span>  

> ##### <span data-ttu-id="54edc-404">图31</span><span class="sxs-lookup"><span data-stu-id="54edc-404">Figure 31</span></span>  
> <span data-ttu-id="54edc-405">`9.47ms`所选部分底部的时间戳表示该部分所花费的时间。</span><span class="sxs-lookup"><span data-stu-id="54edc-405">The `9.47ms` timestamp at the bottom of the selected portion indicates how long that portion took</span></span>  
> ![查看部分录制的持续时间][ImageDuration]  

### <span data-ttu-id="54edc-407">查看屏幕截图</span><span class="sxs-lookup"><span data-stu-id="54edc-407">View a screenshot</span></span>   

<span data-ttu-id="54edc-408">请参阅[在录制时捕获屏幕截图](#capture-screenshots-while-recording)，了解如何启用屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="54edc-408">See [Capture screenshots while recording](#capture-screenshots-while-recording) to learn how to enable screenshots.</span></span>  

<span data-ttu-id="54edc-409">将鼠标悬停在**概述**上以查看屏幕的屏幕截图，了解在录制期间如何查看页面。</span><span class="sxs-lookup"><span data-stu-id="54edc-409">Hover over the **Overview** to view a screenshot of how the page looked during that moment of the recording.</span></span>  <span data-ttu-id="54edc-410">**概述**是包含**CPU**、 **FPS**和**NET**图表的部分。</span><span class="sxs-lookup"><span data-stu-id="54edc-410">The **Overview** is the section that contains the **CPU**, **FPS**, and **NET** charts.</span></span>  

> ##### <span data-ttu-id="54edc-411">图32</span><span class="sxs-lookup"><span data-stu-id="54edc-411">Figure 32</span></span>  
> <span data-ttu-id="54edc-412">查看屏幕截图</span><span class="sxs-lookup"><span data-stu-id="54edc-412">Viewing a screenshot</span></span>  
> ![查看屏幕截图][ImageViewScreenshot]  

<span data-ttu-id="54edc-414">您也可以通过单击 "**框架**" 部分中的帧来查看屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="54edc-414">You may also view screenshots by clicking a frame in the **Frames** section.</span></span>  <span data-ttu-id="54edc-415">DevTools 在 "**摘要**" 选项卡中显示小版本的屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="54edc-415">DevTools displays a small version of the screenshot in the **Summary** tab.</span></span>  

> ##### <span data-ttu-id="54edc-416">图33</span><span class="sxs-lookup"><span data-stu-id="54edc-416">Figure 33</span></span>  
> <span data-ttu-id="54edc-417">单击 " `233.9ms` **框架**" 部分中的帧后，将在 "**摘要**" 选项卡中显示该帧的屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="54edc-417">After clicking the `233.9ms` frame in the **Frames** section, the screenshot for that frame is displayed in the **Summary** tab</span></span>  
> ![在 "摘要" 选项卡中查看屏幕截图][ImageFrameScreenshotSummary]  

<span data-ttu-id="54edc-419">单击 "**摘要**" 选项卡中的缩略图以放大屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="54edc-419">Click the thumbnail in the **Summary** tab to zoom in on the screenshot.</span></span>  

> ##### <span data-ttu-id="54edc-420">图34</span><span class="sxs-lookup"><span data-stu-id="54edc-420">Figure 34</span></span>  
> <span data-ttu-id="54edc-421">单击 "**摘要**" 选项卡中的缩略图后，DevTools 将放大屏幕截图</span><span class="sxs-lookup"><span data-stu-id="54edc-421">After clicking the thumbnail in the **Summary** tab, DevTools zooms in on the screenshot</span></span>  
> ![从 "摘要" 选项卡放大屏幕截图][ImageFrameScreenshotZoom]  

### <span data-ttu-id="54edc-423">查看层信息</span><span class="sxs-lookup"><span data-stu-id="54edc-423">View layers information</span></span>   

<span data-ttu-id="54edc-424">要查看有关框架的高级图层信息，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="54edc-424">To view advanced layers information about a frame:</span></span>  

1.  <span data-ttu-id="54edc-425">[启用高级画图工具](#enable-advanced-paint-instrumentation)。</span><span class="sxs-lookup"><span data-stu-id="54edc-425">[Enable advanced paint instrumentation](#enable-advanced-paint-instrumentation).</span></span>  
1.  <span data-ttu-id="54edc-426">在 "**框架**" 部分中选择一个帧。</span><span class="sxs-lookup"><span data-stu-id="54edc-426">Select a frame in the **Frames** section.</span></span>  <span data-ttu-id="54edc-427">DevTools 显示 "新建**图层**" 选项卡上 "**事件日志**" 选项卡旁边的图层的信息。</span><span class="sxs-lookup"><span data-stu-id="54edc-427">DevTools displays information about the layers in the new **Layers** tab, next to the **Event Log** tab.</span></span>  
    
    > ##### <span data-ttu-id="54edc-428">图35</span><span class="sxs-lookup"><span data-stu-id="54edc-428">Figure 35</span></span>  
    > <span data-ttu-id="54edc-429">"**图层**" 窗格</span><span class="sxs-lookup"><span data-stu-id="54edc-429">The **Layers** pane</span></span>  
    > !["图层" 窗格][ImageLayers]  
    
<span data-ttu-id="54edc-431">将鼠标悬停在某个图层上，将其在图表中突出显示。</span><span class="sxs-lookup"><span data-stu-id="54edc-431">Hover over a layer to highlight it in the diagram.</span></span>  

> ##### <span data-ttu-id="54edc-432">图36</span><span class="sxs-lookup"><span data-stu-id="54edc-432">Figure 36</span></span>  
> <span data-ttu-id="54edc-433">突出显示图层 **#39**</span><span class="sxs-lookup"><span data-stu-id="54edc-433">Highlighting layer **#39**</span></span>  
> ![突出显示图层][ImageLayerHover]  

<span data-ttu-id="54edc-435">若要移动图表，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="54edc-435">To move the diagram:</span></span>  

*   <span data-ttu-id="54edc-436">单击 "**平移模式** ![ 平移模式 ][ImagePanModeIcon] " 沿 X 轴和 Y 轴移动。</span><span class="sxs-lookup"><span data-stu-id="54edc-436">Click **Pan Mode** ![Pan Mode][ImagePanModeIcon] to move along the X and Y axes.</span></span>  
*   <span data-ttu-id="54edc-437">单击 "**旋转模式** ![ 旋转模式 ][ImageRotateModeIcon] " 沿 Z 轴旋转。</span><span class="sxs-lookup"><span data-stu-id="54edc-437">Click **Rotate Mode** ![Rotate Mode][ImageRotateModeIcon] to rotate along the Z axis.</span></span>  
*   <span data-ttu-id="54edc-438">单击 "**重置转换** ![ 重置转换" ][ImageResetTransformIcon] 以将图表重置为原始位置。</span><span class="sxs-lookup"><span data-stu-id="54edc-438">Click **Reset Transform** ![Reset Transform][ImageResetTransformIcon] to reset the diagram to the original position.</span></span>  

### <span data-ttu-id="54edc-439">查看画图档案器</span><span class="sxs-lookup"><span data-stu-id="54edc-439">View paint profiler</span></span>   

<span data-ttu-id="54edc-440">若要查看有关画图事件的高级信息，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="54edc-440">To view advanced information about a paint event:</span></span>  

1.  <span data-ttu-id="54edc-441">[启用高级画图工具](#enable-advanced-paint-instrumentation)。</span><span class="sxs-lookup"><span data-stu-id="54edc-441">[Enable advanced paint instrumentation](#enable-advanced-paint-instrumentation).</span></span>  
1.  <span data-ttu-id="54edc-442">在 "**主要**" 部分中选择一个**绘制**事件。</span><span class="sxs-lookup"><span data-stu-id="54edc-442">Select a **Paint** event in the **Main** section.</span></span>  
    
    > ##### <span data-ttu-id="54edc-443">图37</span><span class="sxs-lookup"><span data-stu-id="54edc-443">Figure 37</span></span>  
    > <span data-ttu-id="54edc-444">"**画图" 事件探查器**选项卡</span><span class="sxs-lookup"><span data-stu-id="54edc-444">The **Paint Profiler** tab</span></span>  
    > !["画图" 事件探查器选项卡][ImagePaintProfiler]  
    
## <span data-ttu-id="54edc-446">通过 "渲染" 选项卡分析渲染性能</span><span class="sxs-lookup"><span data-stu-id="54edc-446">Analyze rendering performance with the Rendering tab</span></span>   

<span data-ttu-id="54edc-447">使用 "**呈现**" 选项卡的功能来帮助可视化页面的呈现性能。</span><span class="sxs-lookup"><span data-stu-id="54edc-447">Use the features of the **Rendering** tab to help visualize the rendering performance of your page.</span></span>  

<span data-ttu-id="54edc-448">若要打开 "**呈现**" 选项卡：</span><span class="sxs-lookup"><span data-stu-id="54edc-448">To open the **Rendering** tab:</span></span>  

1.  <span data-ttu-id="54edc-449">[打开 "命令" 菜单][DevToolsCommandMenu]。</span><span class="sxs-lookup"><span data-stu-id="54edc-449">[Open the Command Menu][DevToolsCommandMenu].</span></span>  
1.  <span data-ttu-id="54edc-450">开始键入 `Rendering` 并选择 `Show Rendering` 。</span><span class="sxs-lookup"><span data-stu-id="54edc-450">Start typing `Rendering` and select `Show Rendering`.</span></span>  <span data-ttu-id="54edc-451">DevTools 显示 DevTools 窗口底部的 "**呈现**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="54edc-451">DevTools displays the **Rendering** tab at the bottom of your DevTools window.</span></span>  
    
    > ##### <span data-ttu-id="54edc-452">图38</span><span class="sxs-lookup"><span data-stu-id="54edc-452">Figure 38</span></span>  
    > <span data-ttu-id="54edc-453">"**呈现**" 选项卡</span><span class="sxs-lookup"><span data-stu-id="54edc-453">The **Rendering** tab</span></span>  
    > !["呈现" 选项卡][ImageRenderingTab]  
    
### <span data-ttu-id="54edc-455">以 FPS 计量器实时查看每秒帧数</span><span class="sxs-lookup"><span data-stu-id="54edc-455">View frames per second in realtime with the FPS meter</span></span>   

<span data-ttu-id="54edc-456">**FPS 指示器**是出现在视区右上角的覆盖图。</span><span class="sxs-lookup"><span data-stu-id="54edc-456">The **FPS meter** is an overlay that appears in the top-right corner of your viewport.</span></span>  <span data-ttu-id="54edc-457">它在页面运行时提供对 FPS 的实时估计。</span><span class="sxs-lookup"><span data-stu-id="54edc-457">It provides a realtime estimate of FPS as the page runs.</span></span>  <span data-ttu-id="54edc-458">要打开**FPS 指示器**，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="54edc-458">To open the **FPS meter**:</span></span>  

1.  <span data-ttu-id="54edc-459">打开 "**呈现**" 选项卡。 请参阅[用渲染选项卡分析渲染性能](#analyze-rendering-performance-with-the-rendering-tab)。</span><span class="sxs-lookup"><span data-stu-id="54edc-459">Open the **Rendering** tab.  See [Analyze rendering performance with the Rendering tab](#analyze-rendering-performance-with-the-rendering-tab).</span></span>  
1.  <span data-ttu-id="54edc-460">启用 " **FPS 指示器**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="54edc-460">Enable the **FPS Meter** checkbox.</span></span>  
    
    > ##### <span data-ttu-id="54edc-461">图39</span><span class="sxs-lookup"><span data-stu-id="54edc-461">Figure 39</span></span>  
    > <span data-ttu-id="54edc-462">FPS 指示器</span><span class="sxs-lookup"><span data-stu-id="54edc-462">The FPS meter</span></span>  
    > ![FPS 指示器][ImageFpsMeter]  
    
### <span data-ttu-id="54edc-464">通过画图闪烁实时查看绘图事件</span><span class="sxs-lookup"><span data-stu-id="54edc-464">View painting events in realtime with Paint Flashing</span></span>   

<span data-ttu-id="54edc-465">使用 "绘画闪烁" 获取页面上的所有绘制事件的实时视图。</span><span class="sxs-lookup"><span data-stu-id="54edc-465">Use Paint Flashing to get a realtime view of all paint events on the page.</span></span>  <span data-ttu-id="54edc-466">只要重新绘制了页面的一部分，DevTools 将以绿色显示该部分。</span><span class="sxs-lookup"><span data-stu-id="54edc-466">Whenever a part of the page gets re-painted, DevTools outlines that section in green.</span></span>  

<span data-ttu-id="54edc-467">启用画图闪烁：</span><span class="sxs-lookup"><span data-stu-id="54edc-467">To enable Paint Flashing:</span></span>  

1.  <span data-ttu-id="54edc-468">打开 "**呈现**" 选项卡。 请参阅[用渲染选项卡分析渲染性能](#analyze-rendering-performance-with-the-rendering-tab)。</span><span class="sxs-lookup"><span data-stu-id="54edc-468">Open the **Rendering** tab.  See [Analyze rendering performance with the Rendering tab](#analyze-rendering-performance-with-the-rendering-tab).</span></span>  
1.  <span data-ttu-id="54edc-469">启用 "**绘画闪烁**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="54edc-469">Enable the **Paint Flashing** checkbox.</span></span>  
    
    > ##### <span data-ttu-id="54edc-470">图40</span><span class="sxs-lookup"><span data-stu-id="54edc-470">Figure 40</span></span>  
    > **<span data-ttu-id="54edc-471">绘画闪烁</span><span class="sxs-lookup"><span data-stu-id="54edc-471">Paint Flashing</span></span>**  
    > ![绘画闪烁][ImagePaintFlashing]  
    
### <span data-ttu-id="54edc-473">查看带有图层边框的图层叠加</span><span class="sxs-lookup"><span data-stu-id="54edc-473">View an overlay of layers with Layer Borders</span></span>   

<span data-ttu-id="54edc-474">使用**图层边框**查看图层边框和图块在页面顶部的覆盖图。</span><span class="sxs-lookup"><span data-stu-id="54edc-474">Use **Layer Borders** to view an overlay of layer borders and tiles on top of the page.</span></span>  

<span data-ttu-id="54edc-475">要启用图层边框，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="54edc-475">To enable Layer Borders:</span></span>  

1.  <span data-ttu-id="54edc-476">打开 "**呈现**" 选项卡。 请参阅[用渲染选项卡分析渲染性能](#analyze-rendering-performance-with-the-rendering-tab)。</span><span class="sxs-lookup"><span data-stu-id="54edc-476">Open the **Rendering** tab.  See [Analyze rendering performance with the Rendering tab](#analyze-rendering-performance-with-the-rendering-tab).</span></span>  
1.  <span data-ttu-id="54edc-477">启用 "**图层边框**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="54edc-477">Enable the **Layer Borders** checkbox.</span></span>  
    
    > ##### <span data-ttu-id="54edc-478">图41</span><span class="sxs-lookup"><span data-stu-id="54edc-478">Figure 41</span></span>  
    > **<span data-ttu-id="54edc-479">图层边框</span><span class="sxs-lookup"><span data-stu-id="54edc-479">Layer Borders</span></span>**  
    > ![图层边框][ImageLayerBorders]  
    
<span data-ttu-id="54edc-481">有关颜色 codings 的说明，请参阅中的批注 [`debug_colors.cc`][ChromiumDebugColors] 。</span><span class="sxs-lookup"><span data-stu-id="54edc-481">See the comments in [`debug_colors.cc`][ChromiumDebugColors] for an explanation of the color-codings.</span></span>  

### <span data-ttu-id="54edc-482">查找实时滚动性能问题</span><span class="sxs-lookup"><span data-stu-id="54edc-482">Find scroll performance issues in realtime</span></span>   

<span data-ttu-id="54edc-483">使用滚动性能问题来标识页面中具有与滚动相关的事件侦听器的元素，这些事件侦听器可能会损害页面的性能。</span><span class="sxs-lookup"><span data-stu-id="54edc-483">Use Scrolling Performance Issues to identify elements of the page that have event listeners related to scrolling that may harm the performance of the page.</span></span>  
<span data-ttu-id="54edc-484">DevTools 概述了蓝色的有问题的元素。</span><span class="sxs-lookup"><span data-stu-id="54edc-484">DevTools outlines the potentially-problematic elements in teal.</span></span>  

<span data-ttu-id="54edc-485">要查看滚动性能问题，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="54edc-485">To view scroll performance issues:</span></span>  

1.  <span data-ttu-id="54edc-486">打开 "**呈现**" 选项卡。 请参阅[用渲染选项卡分析渲染性能](#analyze-rendering-performance-with-the-rendering-tab)。</span><span class="sxs-lookup"><span data-stu-id="54edc-486">Open the **Rendering** tab.  See [Analyze rendering performance with the Rendering tab](#analyze-rendering-performance-with-the-rendering-tab).</span></span>  
1.  <span data-ttu-id="54edc-487">启用 "**滚动性能问题**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="54edc-487">Enable the **Scrolling Performance Issues** checkbox.</span></span>  
 
    > ##### <span data-ttu-id="54edc-488">图42</span><span class="sxs-lookup"><span data-stu-id="54edc-488">Figure 42</span></span>  
    > <span data-ttu-id="54edc-489">**滚动性能问题**表示非层视区约束的对象可能会损害滚动性能</span><span class="sxs-lookup"><span data-stu-id="54edc-489">**Scrolling Performance Issues** indicates that non-layer viewport-constrained objects may harm scroll performance</span></span>  
    > ![滚动性能问题表示非层视区约束的对象可能会损害滚动性能][ImageScrollingPerformanceIssues]  
    

<!--    -->  



<!-- image links -->  

[ImageCaptureSettingsIcon]: /microsoft-edge/devtools-guide-chromium/media/capture-settings-icon.msft.png  
[ImageClearRecordingIcon]: /microsoft-edge/devtools-guide-chromium/media/clear-recording-icon.msft.png  
[ImageCollectGarbageIcon]: /microsoft-edge/devtools-guide-chromium/media/collect-garbage-icon.msft.png  
[ImageNextIcon]: /microsoft-edge/devtools-guide-chromium/media/next-icon.msft.png  
[ImagePanModeIcon]: /microsoft-edge/devtools-guide-chromium/media/pan-mode-icon.msft.png  
[ImagePreviousIcon]: /microsoft-edge/devtools-guide-chromium/media/previous-icon.msft.png  
[ImageRecordIcon]: /microsoft-edge/devtools-guide-chromium/media/record-icon.msft.png
[ImageRefreshPageIcon]: /microsoft-edge/devtools-guide-chromium/media/refresh-page-icon.msft.png  
[ImageResetTransformIcon]: /microsoft-edge/devtools-guide-chromium/media/reset-transform-icon.msft.png  
[ImageRotateModeIcon]: /microsoft-edge/devtools-guide-chromium/media/rotate-mode-icon.msft.png  
[ImageSearchCaseIcon]: /microsoft-edge/devtools-guide-chromium/media/search-case-icon.msft.png  
[ImageSearchRegexIcon]: /microsoft-edge/devtools-guide-chromium/media/search-regex-icon.msft.png  
[ImageShowHeaviestStackIcon]: /microsoft-edge/devtools-guide-chromium/media/show-heaviest-stack-icon.msft.png  

[ImageRecord]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-record-highlight.msft.png "图1：记录"  
[ImageRefreshPage]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-refresh-button.msft.png "图2：刷新页面"  
[ImageLoadRecording]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-refreshed.msft.png "图3：页面加载录制"  
[ImageScreenshots]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-capture-screenshots-checkbox.msft.png "图4： "屏幕截图" 复选框"  
[ImageCollectGarbage]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-collect-garbage-button.msft.png "图5：收集垃圾"  
[ImageCaptureSettings]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-capture-settings-button-open-drawer.msft.png "图6： "捕获设置" 部分"  
[ImageJSSamplesDisabled]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-on.msft.png "图7：在禁用 JS 样本时录制的示例"  
[ImageJSSamplesEnabled]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off.msft.png "图8：启用了 JS 样本时录制的示例"  
[ImageSaveProfile]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-save-profile.msft.png "图9：保存配置文件"  
[ImageLoadProfile]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-load-profile.msft.png "图10：加载配置文件"  
[ImageClearRecording]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-clear-button.msft.png "图11：清除录制"  
[ImageZoom]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-zoom-highlighted.msft.png "图12：在概述中拖动鼠标以缩放"  
[ImageSearch]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-search-regex.msft.png "图13： "搜索" 框"  
[ImageMain]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-main-zoomed.msft.png "图14：主要部分"  
[ImageMainEventSummary]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-summary-me.msft.png "图15：有关 "摘要" 选项卡中的匿名函数的详细信息"  
[ImageFlameChart]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-main-flame-chart.msft.png "图16：火焰图"  
[ImageCallTree]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-call-tree.msft.png "图17： "调用树" 选项卡"  
[ImageBottomUp]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-bottoms-up.msft.png "图18：自下而上的选项卡"  
[ImageEventLog]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-event-log.msft.png "图19： "事件日志" 选项卡"  
[ImageGpu]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-gpu-zoomed.msft.png "图20： GPU 部分"  
[ImageRaster]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-raster.msft.png "图21： "光栅" 部分"  
[ImageInteractions]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-interactions-animation.msft.png "图22： "交互" 部分"  
[ImageFpsChart]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-fps-highlight.msft.png "图23： FPS 图表"  
[ImageFramesSection]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-frames-hover.msft.png "图24：将鼠标悬停在框架上"  
[ImageFrameSummary]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-frames-summary.msft.png "图25：在 "摘要" 选项卡中查看帧"  
[ImageNetworkRequest]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-network.msft.png "图26： "网络" 部分"  
[ImageLineBar]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-bing-performance-network.msft.png "图27： www.bing.com 请求的行条形图表示形式"  
[ImageTiming]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-bing-network-timing.msft.png "图28： "网络" 部分"  
[ImageMemory]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-memory-highlight.msft.png "图29： "内存" 复选框"  
[ImageMemoryMetrics]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-memory-chart.msft.png "图30：内存指标"  
[ImageDuration]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-main-duration.msft.png "图31：查看部分录制的持续时间"  
[ImageViewScreenshot]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-screenshots-hover.msft.png "图32：查看屏幕截图"  
[ImageFrameScreenshotSummary]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-summary-preview.msft.png "图33：在 "摘要" 选项卡中查看屏幕截图"  
[ImageFrameScreenshotZoom]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-summary-preview-select.msft.png "图34：放大 "摘要" 选项卡上的屏幕截图"  
[ImageLayers]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-layers-all.msft.png "图35： "层" 窗格"  
[ImageLayerHover]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-frames-document-nav-bar-highlighted.msft.png "图36：突出显示图层"  
[ImagePaintProfiler]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-paint-profiler.msft.png "图37： "画图" 事件探查器选项卡"  
[ImageRenderingTab]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-console-drawer-rendering.msft.png "图38： "呈现" 选项卡"  
[ImageFpsMeter]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-jank-console-rendering-frame-rate.msft.png "图39： FPS 指示器"  
[ImagePaintFlashing]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-jank-console-rendering-paint-flashing.msft.png "图40：绘画闪烁"  
[ImageLayerBorders]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-devtools-console-rendering-layer-borders.msft.png "图41：图层边框"  
[ImageScrollingPerformanceIssues]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-bing-console-drawer-rendering-scrolling-performance-issues.msft.png "图42：滚动性能问题指示非层视区约束的对象可能会损害滚动性能"  

<!-- links -->  

[MicrosoftEdgeDevTools]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge （Chromium）开发人员工具"  
[DevToolsCommandMenu]: /microsoft-edge/devtools-guide-chromium/command-menu/index#open-the-command-menu "通过 Microsoft Edge DevTools "命令" 菜单打开命令菜单-运行命令"  
[DevtoolsEvaluatePerformanceGettingStarted]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/index "分析运行时性能入门"  

[ActivityTabsDemo]: https://microsoft-edge-chromium-devtools.glitch.me/perf/activitytabs.html "活动选项卡演示"  

[ChromiumDebugColors]: https://cs.chromium.org/chromium/src/cc/debug/debug_colors.cc "debug_colors 抄送-代码搜索"  

> [!NOTE]
> <span data-ttu-id="54edc-538">此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="54edc-538">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="54edc-539">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/reference)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools \ & Lighthouse \）创作。</span><span class="sxs-lookup"><span data-stu-id="54edc-539">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/reference) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
<span data-ttu-id="54edc-541">此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="54edc-541">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
