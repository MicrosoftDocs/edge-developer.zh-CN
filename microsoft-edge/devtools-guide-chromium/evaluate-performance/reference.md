---
description: 有关在 Microsoft Edge DevTools 中记录和分析性能的所有方法的参考。
title: 性能分析引用
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: 181bc05fffbaef6a06bebcc5cb9ccfcc8e7de498
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398803"
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

# <a name="performance-analysis-reference"></a><span data-ttu-id="e98f4-104">性能分析引用</span><span class="sxs-lookup"><span data-stu-id="e98f4-104">Performance analysis reference</span></span>  

<span data-ttu-id="e98f4-105">此页面全面引用了与分析性能相关的 Microsoft Edge DevTools 功能。</span><span class="sxs-lookup"><span data-stu-id="e98f4-105">This page is a comprehensive reference of Microsoft Edge DevTools features related to analyzing performance.</span></span>  

<span data-ttu-id="e98f4-106">导航到 ["分析][DevtoolsEvaluatePerformanceGettingStarted] 运行时性能入门"，了解如何使用 [Microsoft Edge DevTools][MicrosoftEdgeDevTools]分析页面性能的指南教程。</span><span class="sxs-lookup"><span data-stu-id="e98f4-106">Navigate to [Get Started With Analyzing Runtime Performance][DevtoolsEvaluatePerformanceGettingStarted] for a guided tutorial on how to analyze the performance of a page using [Microsoft Edge DevTools][MicrosoftEdgeDevTools].</span></span>  

## <a name="record-performance"></a><span data-ttu-id="e98f4-107">记录性能</span><span class="sxs-lookup"><span data-stu-id="e98f4-107">Record performance</span></span>  

### <a name="record-runtime-performance"></a><span data-ttu-id="e98f4-108">记录运行时性能</span><span class="sxs-lookup"><span data-stu-id="e98f4-108">Record runtime performance</span></span>  

<span data-ttu-id="e98f4-109">在页面运行时运行时性能（而不是加载）时，记录运行时性能。</span><span class="sxs-lookup"><span data-stu-id="e98f4-109">Record runtime performance when you want to analyze the performance of a page as it is running, as opposed to loading.</span></span>  

1.  <span data-ttu-id="e98f4-110">导航到要分析的页面。</span><span class="sxs-lookup"><span data-stu-id="e98f4-110">Navigate to the page that you want to analyze.</span></span>  
1.  <span data-ttu-id="e98f4-111">在 DevTools **中打开** 性能工具。</span><span class="sxs-lookup"><span data-stu-id="e98f4-111">Open the **Performance** tool in DevTools.</span></span>  
1.  <span data-ttu-id="e98f4-112">Choose **Record** \ (![ Record icon ][ImageRecordIcon] \) .</span><span class="sxs-lookup"><span data-stu-id="e98f4-112">Choose **Record** \(![Record icon][ImageRecordIcon]\).</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-performance-record-highlight.msft.png" alt-text="记录" lightbox="../media/evaluate-performance-performance-record-highlight.msft.png":::
       **<span data-ttu-id="e98f4-114">记录</span><span class="sxs-lookup"><span data-stu-id="e98f4-114">Record</span></span>**  
    :::image-end:::  
    
1.  <span data-ttu-id="e98f4-115">与页面交互。</span><span class="sxs-lookup"><span data-stu-id="e98f4-115">Interact with the page.</span></span>  <span data-ttu-id="e98f4-116">DevTools 记录交互后发生的所有页面活动。</span><span class="sxs-lookup"><span data-stu-id="e98f4-116">DevTools records all page activity that occurs as a result of your interactions.</span></span>  
1.  <span data-ttu-id="e98f4-117">再次 **选择** "录制"或" **停止** "以停止录制。</span><span class="sxs-lookup"><span data-stu-id="e98f4-117">Choose **Record** again or choose **Stop** to stop recording.</span></span>  
    
### <a name="record-load-performance"></a><span data-ttu-id="e98f4-118">记录加载性能</span><span class="sxs-lookup"><span data-stu-id="e98f4-118">Record load performance</span></span>  

<span data-ttu-id="e98f4-119">在页面加载时（而不是运行时）要分析其性能时记录加载性能。</span><span class="sxs-lookup"><span data-stu-id="e98f4-119">Record load performance when you want to analyze the performance of a page as it is loading, as opposed to running.</span></span>  

1.  <span data-ttu-id="e98f4-120">导航到要分析的页面。</span><span class="sxs-lookup"><span data-stu-id="e98f4-120">Navigate to the page that you want to analyze.</span></span>  
1.  <span data-ttu-id="e98f4-121">打开 **DevTools** 的性能面板。</span><span class="sxs-lookup"><span data-stu-id="e98f4-121">Open the **Performance** panel of DevTools.</span></span>  
1.  <span data-ttu-id="e98f4-122">Choose **Refresh page** \ (Refresh Page ![ ][ImageRefreshPageIcon] \) .</span><span class="sxs-lookup"><span data-stu-id="e98f4-122">Choose **Refresh page** \(![Refresh Page][ImageRefreshPageIcon]\).</span></span>  <span data-ttu-id="e98f4-123">DevTools 在页面刷新时记录性能指标，然后在加载完成后几秒钟自动停止录制。</span><span class="sxs-lookup"><span data-stu-id="e98f4-123">DevTools records performance metrics while the page refreshes and then automatically stops the recording a couple seconds after the load finishes.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-performance-refresh-button.msft.png" alt-text="刷新页面" lightbox="../media/evaluate-performance-performance-refresh-button.msft.png":::
       **<span data-ttu-id="e98f4-125">刷新页面</span><span class="sxs-lookup"><span data-stu-id="e98f4-125">Refresh page</span></span>**  
    :::image-end:::  
    
<span data-ttu-id="e98f4-126">DevTools 会自动放大大部分活动发生的记录部分。</span><span class="sxs-lookup"><span data-stu-id="e98f4-126">DevTools automatically zooms in on the portion of the recording where most of the activity occurred.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-refreshed.msft.png" alt-text="页面加载录制" lightbox="../media/evaluate-performance-performance-refreshed.msft.png":::
   <span data-ttu-id="e98f4-128">页面加载录制</span><span class="sxs-lookup"><span data-stu-id="e98f4-128">A page-load recording</span></span>  
:::image-end:::  

### <a name="capture-screenshots-while-recording"></a><span data-ttu-id="e98f4-129">录制时捕获屏幕截图</span><span class="sxs-lookup"><span data-stu-id="e98f4-129">Capture screenshots while recording</span></span>  

<span data-ttu-id="e98f4-130">打开" **屏幕截图"** 复选框，在录制时捕获每个帧的屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="e98f4-130">Turn on the **Screenshots** checkbox to capture a screenshot of every frame while recording.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-capture-screenshots-checkbox.msft.png" alt-text=""屏幕截图"复选框" lightbox="../media/evaluate-performance-performance-capture-screenshots-checkbox.msft.png":::
   <span data-ttu-id="e98f4-132">" **屏幕截图"** 复选框</span><span class="sxs-lookup"><span data-stu-id="e98f4-132">The **Screenshots** checkbox</span></span>  
:::image-end:::  

<span data-ttu-id="e98f4-133">导航 [到"查看屏幕截图](#view-a-screenshot) "，了解如何与屏幕截图进行交互。</span><span class="sxs-lookup"><span data-stu-id="e98f4-133">Navigate to [View a screenshot](#view-a-screenshot) to learn how to interact with screenshots.</span></span>  

### <a name="force-garbage-collection-while-recording"></a><span data-ttu-id="e98f4-134">在记录时强制进行垃圾回收</span><span class="sxs-lookup"><span data-stu-id="e98f4-134">Force garbage collection while recording</span></span>  

<span data-ttu-id="e98f4-135">录制页面时， **选择"收集** 垃圾 \ (收集垃圾图标 ![ ][ImageCollectGarbageIcon] \) 强制进行垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="e98f4-135">While you are recording a page, choose **Collect garbage** \(![Collect garbage icon][ImageCollectGarbageIcon]\) to force garbage collection.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-collect-garbage-button.msft.png" alt-text="收集垃圾" lightbox="../media/evaluate-performance-performance-collect-garbage-button.msft.png":::
   <span data-ttu-id="e98f4-137">收集垃圾</span><span class="sxs-lookup"><span data-stu-id="e98f4-137">Collect garbage</span></span>  
:::image-end:::  

### <a name="show-recording-settings"></a><span data-ttu-id="e98f4-138">显示录制设置</span><span class="sxs-lookup"><span data-stu-id="e98f4-138">Show recording settings</span></span>  

<span data-ttu-id="e98f4-139">Choose **Capture settings** \ (Capture settings ![ ][ImageCaptureSettingsIcon] \) to expose more settings related to how DevTools captures performance recordings.</span><span class="sxs-lookup"><span data-stu-id="e98f4-139">Choose **Capture settings** \(![Capture settings][ImageCaptureSettingsIcon]\) to expose more settings related to how DevTools captures performance recordings.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-capture-settings-button-open-drawer.msft.png" alt-text=""捕获设置"部分" lightbox="../media/evaluate-performance-performance-capture-settings-button-open-drawer.msft.png":::
   <span data-ttu-id="e98f4-141">" **捕获设置"** 部分</span><span class="sxs-lookup"><span data-stu-id="e98f4-141">The **Capture Settings** section</span></span>  
:::image-end:::  

### <a name="disable-javascript-samples"></a><span data-ttu-id="e98f4-142">禁用 JavaScript 示例</span><span class="sxs-lookup"><span data-stu-id="e98f4-142">Disable JavaScript samples</span></span>  

<span data-ttu-id="e98f4-143">默认情况下，录制 **的 Main** 部分显示录制期间调用的 JavaScript 函数的详细调用堆栈。</span><span class="sxs-lookup"><span data-stu-id="e98f4-143">By default, the **Main** section of a recording displays detailed call stacks of JavaScript functions that were called during the recording.</span></span>  <span data-ttu-id="e98f4-144">若要禁用这些调用堆栈，</span><span class="sxs-lookup"><span data-stu-id="e98f4-144">To disable these call stacks:</span></span>  

1.  <span data-ttu-id="e98f4-145">打开 **"捕获设置"** 菜单。</span><span class="sxs-lookup"><span data-stu-id="e98f4-145">Open the **Capture settings** menu.</span></span>  <span data-ttu-id="e98f4-146">导航到["显示录制设置"。](#show-recording-settings)</span><span class="sxs-lookup"><span data-stu-id="e98f4-146">Navigate to [Show recording settings](#show-recording-settings).</span></span>  
1.  <span data-ttu-id="e98f4-147">打开" **禁用 JavaScript 示例"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="e98f4-147">Turn on the **Disable JavaScript Samples** checkbox.</span></span>  
1.  <span data-ttu-id="e98f4-148">录制页面。</span><span class="sxs-lookup"><span data-stu-id="e98f4-148">Take a recording of the page.</span></span>  
    
<span data-ttu-id="e98f4-149">以下 2 个图显示禁用和启用 JavaScript 示例的区别。</span><span class="sxs-lookup"><span data-stu-id="e98f4-149">The following 2 figures display the difference between disabling and enabling JavaScript samples.</span></span>  <span data-ttu-id="e98f4-150">禁用 **采样** 时，录制的主节要短得多，因为它省略所有 JavaScript 调用堆栈。</span><span class="sxs-lookup"><span data-stu-id="e98f4-150">The **Main** section of the recording is much shorter when sampling is disabled, because it omits all of the JavaScript call stacks.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-on.msft.png" alt-text="禁用 JS 示例时录制的示例" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-on.msft.png":::
         <span data-ttu-id="e98f4-152">禁用 JS 示例时录制的示例</span><span class="sxs-lookup"><span data-stu-id="e98f4-152">An example of a recording when JS samples are disabled</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off.msft.png" alt-text="打开 JS 示例时录制的示例" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off.msft.png":::
         <span data-ttu-id="e98f4-154">打开 JS 示例时录制的示例</span><span class="sxs-lookup"><span data-stu-id="e98f4-154">An example of a recording when JS samples are turned on</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::

### <a name="throttle-the-network-while-recording"></a><span data-ttu-id="e98f4-155">在录制时限制网络</span><span class="sxs-lookup"><span data-stu-id="e98f4-155">Throttle the network while recording</span></span>  

<span data-ttu-id="e98f4-156">若要在录制时限制网络，</span><span class="sxs-lookup"><span data-stu-id="e98f4-156">To throttle the network while recording:</span></span>  

1.  <span data-ttu-id="e98f4-157">打开 **"捕获设置"** 菜单。</span><span class="sxs-lookup"><span data-stu-id="e98f4-157">Open the **Capture settings** menu.</span></span>  <span data-ttu-id="e98f4-158">导航到["显示录制设置"。](#show-recording-settings)</span><span class="sxs-lookup"><span data-stu-id="e98f4-158">Navigate to [Show recording settings](#show-recording-settings).</span></span>  
1.  <span data-ttu-id="e98f4-159">将 **网络** 设置为所需的限制级别。</span><span class="sxs-lookup"><span data-stu-id="e98f4-159">Set **Network** to the desired level of throttling.</span></span>  
    
### <a name="throttle-the-cpu-while-recording"></a><span data-ttu-id="e98f4-160">在录制时限制 CPU</span><span class="sxs-lookup"><span data-stu-id="e98f4-160">Throttle the CPU while recording</span></span>  

<span data-ttu-id="e98f4-161">若要在录制时限制 CPU：</span><span class="sxs-lookup"><span data-stu-id="e98f4-161">To throttle the CPU while recording:</span></span>  

1.  <span data-ttu-id="e98f4-162">打开 **"捕获设置"** 菜单。</span><span class="sxs-lookup"><span data-stu-id="e98f4-162">Open the **Capture settings** menu.</span></span>  <span data-ttu-id="e98f4-163">导航到["显示录制设置"。](#show-recording-settings)</span><span class="sxs-lookup"><span data-stu-id="e98f4-163">Navigate to [Show recording settings](#show-recording-settings).</span></span>  
1.  <span data-ttu-id="e98f4-164">将 **CPU** 设置为所需的限制级别。</span><span class="sxs-lookup"><span data-stu-id="e98f4-164">Set **CPU** to the desired level of throttling.</span></span>  
    
<span data-ttu-id="e98f4-165">限制与计算机的功能相关。</span><span class="sxs-lookup"><span data-stu-id="e98f4-165">Throttling is relative to the capabilities of your computer.</span></span>  <span data-ttu-id="e98f4-166">例如 **，2 倍** 减速选项使 CPU 的运行速度比正常速度慢 2 倍。</span><span class="sxs-lookup"><span data-stu-id="e98f4-166">For example, the **2x slowdown** option makes your CPU operate 2 times slower than normal.</span></span>  <span data-ttu-id="e98f4-167">DevTools 不会真正模拟移动设备的 CPU，因为移动设备的体系结构与台式机和笔记本电脑的体系结构大为不同。</span><span class="sxs-lookup"><span data-stu-id="e98f4-167">DevTools do not truly simulate the CPUs of mobile devices, because the architecture of mobile devices is very different from that of desktops and laptops.</span></span>  

### <a name="turn-on-advanced-paint-instrumentation"></a><span data-ttu-id="e98f4-168">打开高级绘制检测</span><span class="sxs-lookup"><span data-stu-id="e98f4-168">Turn on advanced paint instrumentation</span></span>  

<span data-ttu-id="e98f4-169">若要查看详细的绘制检测，请：</span><span class="sxs-lookup"><span data-stu-id="e98f4-169">To view detailed paint instrumentation:</span></span>  

1.  <span data-ttu-id="e98f4-170">打开 **"捕获设置"** 菜单。</span><span class="sxs-lookup"><span data-stu-id="e98f4-170">Open the **Capture settings** menu.</span></span>  <span data-ttu-id="e98f4-171">导航到["显示录制设置"。](#show-recording-settings)</span><span class="sxs-lookup"><span data-stu-id="e98f4-171">Navigate to [Show recording settings](#show-recording-settings).</span></span>  
1.  <span data-ttu-id="e98f4-172">选中" \*\*启用高级绘制检测 (慢速) \*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="e98f4-172">Check the **Enable advanced paint instrumentation (slow)** checkbox.</span></span>  

<span data-ttu-id="e98f4-173">若要了解如何与绘制信息进行交互，请导航到["查看图层"和](#view-layers-information)"[查看绘制探查器"。](#view-paint-profiler)</span><span class="sxs-lookup"><span data-stu-id="e98f4-173">To learn how to interact with the paint information, navigate to [View layers](#view-layers-information) and [View paint profiler](#view-paint-profiler).</span></span>  

## <a name="save-a-recording"></a><span data-ttu-id="e98f4-174">保存录制</span><span class="sxs-lookup"><span data-stu-id="e98f4-174">Save a recording</span></span>  

<span data-ttu-id="e98f4-175">若要保存录制，请打开上下文菜单 \ (右键单击\) ，然后选择"保存**配置文件"。**</span><span class="sxs-lookup"><span data-stu-id="e98f4-175">To save a recording, open the contextual menu \(right-click\), and choose **Save Profile**.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-save-profile.msft.png" alt-text="保存配置文件" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-save-profile.msft.png":::
   **<span data-ttu-id="e98f4-177">保存配置文件</span><span class="sxs-lookup"><span data-stu-id="e98f4-177">Save Profile</span></span>**  
:::image-end:::  

## <a name="load-a-recording"></a><span data-ttu-id="e98f4-178">加载录制</span><span class="sxs-lookup"><span data-stu-id="e98f4-178">Load a recording</span></span>  

<span data-ttu-id="e98f4-179">若要加载录制，请打开上下文菜单 \ (右键单击\) ，然后选择"加载**配置文件"。**</span><span class="sxs-lookup"><span data-stu-id="e98f4-179">To load a recording, open the contextual menu \(right-click\), and choose **Load Profile**.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-load-profile.msft.png" alt-text="加载配置文件" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-load-profile.msft.png":::
   **<span data-ttu-id="e98f4-181">加载配置文件</span><span class="sxs-lookup"><span data-stu-id="e98f4-181">Load Profile</span></span>**  
:::image-end:::  

## <a name="clear-the-previous-recording"></a><span data-ttu-id="e98f4-182">清除上一录制</span><span class="sxs-lookup"><span data-stu-id="e98f4-182">Clear the previous recording</span></span>  

<span data-ttu-id="e98f4-183">录制后，**选择"清除**录制" ("清除录制"图标 \) 以从"性能"面板中 ![ ][ImageClearRecordingIcon] 清除该录制\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e98f4-183">After making a recording, choose **Clear recording** \(![Clear recording icon][ImageClearRecordingIcon]\) to clear that recording from the **Performance** panel.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-clear-button.msft.png" alt-text="清除录制" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-clear-button.msft.png":::
   **<span data-ttu-id="e98f4-185">清除录制</span><span class="sxs-lookup"><span data-stu-id="e98f4-185">Clear recording</span></span>**  
:::image-end:::  

## <a name="analyze-a-performance-recording"></a><span data-ttu-id="e98f4-186">分析性能记录</span><span class="sxs-lookup"><span data-stu-id="e98f4-186">Analyze a performance recording</span></span>  

<span data-ttu-id="e98f4-187">记录[运行时性能](#record-runtime-performance)或[记录加载性能](#record-load-performance)后，性能面板\*\*\*\* 会提供大量数据，用于分析刚发生的情况的性能。</span><span class="sxs-lookup"><span data-stu-id="e98f4-187">After you [record runtime performance](#record-runtime-performance) or [record load performance](#record-load-performance), the **Performance** panel provides a lot of data for analyzing the performance of what just happened.</span></span>  

### <a name="select-a-portion-of-a-recording"></a><span data-ttu-id="e98f4-188">选择录音的一部分</span><span class="sxs-lookup"><span data-stu-id="e98f4-188">Select a portion of a recording</span></span>  

<span data-ttu-id="e98f4-189">将鼠标向左或向右拖动到 **"概述** "中，选择录音的一部分。</span><span class="sxs-lookup"><span data-stu-id="e98f4-189">Drag your mouse left or right across the **Overview** to select a portion of a recording.</span></span>  <span data-ttu-id="e98f4-190">概述**是**包含**FPS、CPU**和\*\*\*\*\*\*NET\*\*图表的部分。</span><span class="sxs-lookup"><span data-stu-id="e98f4-190">The **Overview** is the section that contains the **FPS**, **CPU**, and **NET** charts.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-zoom-highlighted.msft.png" alt-text="将鼠标拖动到"概述"中以缩放" lightbox="../media/evaluate-performance-performance-zoom-highlighted.msft.png":::
   <span data-ttu-id="e98f4-192">将鼠标拖动到 **"概述"中** 以缩放</span><span class="sxs-lookup"><span data-stu-id="e98f4-192">Drag the mouse across the **Overview** to zoom</span></span>  
:::image-end:::  

<span data-ttu-id="e98f4-193">若要使用键盘选择部分，</span><span class="sxs-lookup"><span data-stu-id="e98f4-193">To select a portion using the keyboard:</span></span>  

1.  <span data-ttu-id="e98f4-194">选择主节的背景或\*\*\*\* 它旁边的任何部分，如**交互、\*\*\*\*网络**或**GPU。**</span><span class="sxs-lookup"><span data-stu-id="e98f4-194">Choose the background of the **Main** section, or any of the sections next to it, such as **Interactions**, **Network**, or **GPU**.</span></span>  <span data-ttu-id="e98f4-195">此键盘工作流仅在其中一个部分聚焦时有效。</span><span class="sxs-lookup"><span data-stu-id="e98f4-195">This keyboard workflow only works when one of these sections is in focus.</span></span>  
1.  <span data-ttu-id="e98f4-196">分别使用 ， 、 键进行放大、向左移动、缩小 `W` `A` `S` `D` 和向右移动。</span><span class="sxs-lookup"><span data-stu-id="e98f4-196">Use the `W`, `A`, `S`, `D` keys to zoom in, move left, zoom out, and move right, respectively.</span></span>  

<span data-ttu-id="e98f4-197">若要使用跟踪板选择部分，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="e98f4-197">To select a portion using a trackpad, complete the following actions.</span></span>  

1.  <span data-ttu-id="e98f4-198">将鼠标悬停在 **"** 概述"部分或" **详细信息"部分** 上。</span><span class="sxs-lookup"><span data-stu-id="e98f4-198">Hover your mouse over the **Overview** section or the **Details** section.</span></span>  <span data-ttu-id="e98f4-199">"**概述**"部分包含**FPS、CPU**和\*\*\*\* **NET**图表。</span><span class="sxs-lookup"><span data-stu-id="e98f4-199">The **Overview** section is the area containing the **FPS**, **CPU**, and **NET** charts.</span></span>  <span data-ttu-id="e98f4-200">"**详细信息**"部分是包含"主"\*\*\*\* 部分、"交互 **"** 部分等的区域。</span><span class="sxs-lookup"><span data-stu-id="e98f4-200">The **Details** section is the area containing the **Main** section, the **Interactions** section, and so on.</span></span>  
1.  <span data-ttu-id="e98f4-201">使用两根手指向上轻扫以缩小，向左轻扫向左移动，向下轻扫可放大，向右轻扫向右移动。</span><span class="sxs-lookup"><span data-stu-id="e98f4-201">Using two fingers, swipe up to zoom out, swipe left to move left, swipe down to zoom in, and swipe right to move right.</span></span>  

<span data-ttu-id="e98f4-202">若要在主节或任何元素中滚动\*\*\*\* 长饼图，请选择并按住，同时向上和向下拖动。</span><span class="sxs-lookup"><span data-stu-id="e98f4-202">To scroll a long flame chart in the **Main** section or any of the neighbors, choose and hold while dragging up and down.</span></span>  <span data-ttu-id="e98f4-203">向左和向右拖动以移动所选录制部分。</span><span class="sxs-lookup"><span data-stu-id="e98f4-203">Drag left and right to move what portion of the recording is chosen.</span></span>  

### <a name="search-activities"></a><span data-ttu-id="e98f4-204">搜索活动</span><span class="sxs-lookup"><span data-stu-id="e98f4-204">Search activities</span></span>  

<span data-ttu-id="e98f4-205">选择 `Control` + `F` \ (Windows、Linux\) 或 `Command` + `F` \ (macOS\) \*\*\*\* 打开"性能"面板底部的搜索框。</span><span class="sxs-lookup"><span data-stu-id="e98f4-205">Select `Control`+`F` \(Windows, Linux\) or `Command`+`F` \(macOS\) to open the search box at the bottom of the **Performance** panel.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-search-regex.msft.png" alt-text="搜索框" lightbox="../media/evaluate-performance-performance-search-regex.msft.png":::
   <span data-ttu-id="e98f4-207">搜索框</span><span class="sxs-lookup"><span data-stu-id="e98f4-207">The search box</span></span>  
:::image-end:::  

<span data-ttu-id="e98f4-208">若要导航与查询匹配的活动：</span><span class="sxs-lookup"><span data-stu-id="e98f4-208">To navigate activities that match your query:</span></span>  

*   <span data-ttu-id="e98f4-209">使用上 **一** 个 \ (![ ][ImagePreviousIcon] \) **下** 一个 \ (![ ][ImageNextIcon] \) 按钮。</span><span class="sxs-lookup"><span data-stu-id="e98f4-209">Use the **Previous** \(![Previous][ImagePreviousIcon]\) and **Next** \(![Next][ImageNextIcon]\) buttons.</span></span>  
*   <span data-ttu-id="e98f4-210">选择 `Shift` + `Enter` 以选择上一个或 `Enter` 选择下一个。</span><span class="sxs-lookup"><span data-stu-id="e98f4-210">Select `Shift`+`Enter` to select the previous or `Enter` to select the next.</span></span>  

<span data-ttu-id="e98f4-211">要修改查询设置，请执行：</span><span class="sxs-lookup"><span data-stu-id="e98f4-211">To modify query settings:</span></span>  

*   <span data-ttu-id="e98f4-212">选择 **区分大小写** \ (![ 区分大小写 ][ImageSearchCaseIcon] \) 使查询区分大小写。</span><span class="sxs-lookup"><span data-stu-id="e98f4-212">Choose **Case sensitive** \(![Case sensitive][ImageSearchCaseIcon]\) to make the query case sensitive.</span></span>  
*   <span data-ttu-id="e98f4-213">Choose **Regex** \ (![ Regex ][ImageSearchRegexIcon] \) to use a regular expression in your query.</span><span class="sxs-lookup"><span data-stu-id="e98f4-213">Choose **Regex** \(![Regex][ImageSearchRegexIcon]\) to use a regular expression in your query.</span></span>  

<span data-ttu-id="e98f4-214">若要隐藏搜索框，请选择"取消 **"。**</span><span class="sxs-lookup"><span data-stu-id="e98f4-214">To hide the search box, choose **Cancel**.</span></span>  

### <a name="view-main-thread-activity"></a><span data-ttu-id="e98f4-215">查看主线程活动</span><span class="sxs-lookup"><span data-stu-id="e98f4-215">View main thread activity</span></span>  

<span data-ttu-id="e98f4-216">使用 **"主** "部分可查看页面主线程上发生的活动。</span><span class="sxs-lookup"><span data-stu-id="e98f4-216">Use the **Main** section to view activity that occurred on the main thread of the page.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-main-zoomed.msft.png" alt-text="主要部分" lightbox="../media/evaluate-performance-performance-main-zoomed.msft.png":::
   <span data-ttu-id="e98f4-218">**主要**部分</span><span class="sxs-lookup"><span data-stu-id="e98f4-218">The **Main** section</span></span>  
:::image-end:::  

<span data-ttu-id="e98f4-219">选择事件以查看"摘要"面板中有关 **它的信息** 。</span><span class="sxs-lookup"><span data-stu-id="e98f4-219">Choose an event to view more information about it in the **Summary** panel.</span></span>  <span data-ttu-id="e98f4-220">DevTools 概述了所选事件。</span><span class="sxs-lookup"><span data-stu-id="e98f4-220">DevTools outlines the selected event.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-summary-me.msft.png" alt-text="有关"摘要"面板中的匿名函数详细信息" lightbox="../media/evaluate-performance-performance-summary-me.msft.png":::
   <span data-ttu-id="e98f4-222">有关"摘要 `anonymous` "面板中函数\*\*\*\* 详细信息</span><span class="sxs-lookup"><span data-stu-id="e98f4-222">More information about the `anonymous` function in the **Summary** panel</span></span>  
:::image-end:::  

<span data-ttu-id="e98f4-223">DevTools 表示包含图表的主线程活动。</span><span class="sxs-lookup"><span data-stu-id="e98f4-223">DevTools represents main thread activity with a flame chart.</span></span>  <span data-ttu-id="e98f4-224">x 轴表示一段时间的录制。</span><span class="sxs-lookup"><span data-stu-id="e98f4-224">The x-axis represents the recording over time.</span></span>  <span data-ttu-id="e98f4-225">Y 轴表示调用堆叠。</span><span class="sxs-lookup"><span data-stu-id="e98f4-225">The y-axis represents the call stack.</span></span>  <span data-ttu-id="e98f4-226">顶部的事件会导致其下方的事件。</span><span class="sxs-lookup"><span data-stu-id="e98f4-226">The events on top cause the events below it.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-main-flame-chart.msft.png" alt-text="柱形图" lightbox="../media/evaluate-performance-performance-main-flame-chart.msft.png":::
   <span data-ttu-id="e98f4-228">柱形图</span><span class="sxs-lookup"><span data-stu-id="e98f4-228">A flame chart</span></span>  
:::image-end:::  

<span data-ttu-id="e98f4-229">在上图中， `click` 一个事件导致第 `Function Call` `activitytabs.js` 53 行中发生一个事件。</span><span class="sxs-lookup"><span data-stu-id="e98f4-229">In the previous figure, a `click` event caused a `Function Call` in `activitytabs.js` on line 53.</span></span>  <span data-ttu-id="e98f4-230">在下面 `Function Call` ，查看匿名函数已运行。</span><span class="sxs-lookup"><span data-stu-id="e98f4-230">Below `Function Call`, review that an anonymous function was run.</span></span>  <span data-ttu-id="e98f4-231">请求的匿名函数 `a` ，请求的 `wait` ，请求的 `Minor GC` 。</span><span class="sxs-lookup"><span data-stu-id="e98f4-231">The anonymous function requested `a`, which requested `wait`, which requested `Minor GC`.</span></span>  

<span data-ttu-id="e98f4-232">DevTools 分配脚本随机颜色。</span><span class="sxs-lookup"><span data-stu-id="e98f4-232">DevTools assigns scripts random colors.</span></span>  <span data-ttu-id="e98f4-233">在上图中，来自一个脚本的函数请求的颜色为浅绿色。</span><span class="sxs-lookup"><span data-stu-id="e98f4-233">In the previous figure, function requests from one script are colored light green.</span></span>  <span data-ttu-id="e98f4-234">来自另一个脚本的请求是彩色的浅色。</span><span class="sxs-lookup"><span data-stu-id="e98f4-234">Requests from another script are colored beige.</span></span>  <span data-ttu-id="e98f4-235">深黄色表示脚本活动，紫色事件表示呈现活动。</span><span class="sxs-lookup"><span data-stu-id="e98f4-235">The darker yellow represents scripting activity, and the purple event represents rendering activity.</span></span>  <span data-ttu-id="e98f4-236">这些较深的黄色和紫色事件在所有录制中都是一致的。</span><span class="sxs-lookup"><span data-stu-id="e98f4-236">These darker yellow and purple events are consistent across all recordings.</span></span>  

<span data-ttu-id="e98f4-237">如果要 [隐藏 JavaScript](#disable-javascript-samples) 请求的详细图表，请导航到"禁用 JavaScript"示例。</span><span class="sxs-lookup"><span data-stu-id="e98f4-237">Navigate to [Disable JavaScript samples](#disable-javascript-samples) if you want to hide the detailed flame chart of JavaScript requests.</span></span>  <span data-ttu-id="e98f4-238">禁用 JS 示例后，只显示上图等高级 `Event: choose` `Function Call` `str` 事件。</span><span class="sxs-lookup"><span data-stu-id="e98f4-238">When JS samples are disabled, only high-level events such as `Event: choose` and `Function Call` from the previous figure `str` displayed.</span></span>  

### <a name="view-activities-in-a-table"></a><span data-ttu-id="e98f4-239">查看表中的活动</span><span class="sxs-lookup"><span data-stu-id="e98f4-239">View activities in a table</span></span>  

<span data-ttu-id="e98f4-240">录制页面后，无需仅依赖"主 **"部分来** 分析活动。</span><span class="sxs-lookup"><span data-stu-id="e98f4-240">After recording a page, you do not need to rely solely on the **Main** section to analyze activities.</span></span>  <span data-ttu-id="e98f4-241">DevTools 还提供了三种表格式视图，用于分析活动。</span><span class="sxs-lookup"><span data-stu-id="e98f4-241">DevTools also provides three tabular views for analyzing activities.</span></span>  <span data-ttu-id="e98f4-242">每个视图都提供对活动的不同视角：</span><span class="sxs-lookup"><span data-stu-id="e98f4-242">Each view gives you a different perspective on the activities:</span></span>  

*   <span data-ttu-id="e98f4-243">当要查看导致工作最多的根活动时，请使用"呼叫树 ["](#the-call-tree-panel) 面板。</span><span class="sxs-lookup"><span data-stu-id="e98f4-243">When you want to view the root activities that cause the most work, use the [Call Tree](#the-call-tree-panel) panel.</span></span>  
*   <span data-ttu-id="e98f4-244">当要查看直接花费时间最多的活动时，请使用" [下向上"](#the-bottom-up-panel) 面板。</span><span class="sxs-lookup"><span data-stu-id="e98f4-244">When you want to view the activities where the most time was directly spent, use the [Bottom-Up](#the-bottom-up-panel) panel.</span></span>  
*   <span data-ttu-id="e98f4-245">当您想要按记录期间活动发生的顺序查看活动时，请使用" [事件](#the-event-log-panel) 日志"面板。</span><span class="sxs-lookup"><span data-stu-id="e98f4-245">When you want to view the activities in the order in which they occurred during the recording, use the [Event Log](#the-event-log-panel) panel.</span></span>  
    
> [!NOTE]
> <span data-ttu-id="e98f4-246">接下来的三个部分均引用同一演示。</span><span class="sxs-lookup"><span data-stu-id="e98f4-246">The next three sections all refer to the same demo.</span></span>  <span data-ttu-id="e98f4-247">在活动选项卡 [演示中自己运行演示][ActivityTabsDemo]。</span><span class="sxs-lookup"><span data-stu-id="e98f4-247">Run the demo yourself at [Activity Tabs Demo][ActivityTabsDemo].</span></span>  

#### <a name="root-activities"></a><span data-ttu-id="e98f4-248">根活动</span><span class="sxs-lookup"><span data-stu-id="e98f4-248">Root activities</span></span>  

<span data-ttu-id="e98f4-249">下面是"呼叫树"面板\*\*\*\*、底部向上面板和事件日志面板\*\*\*\* 中提及的根活动\*\*\*\*\*\*概念\*\*的说明。</span><span class="sxs-lookup"><span data-stu-id="e98f4-249">Here is an explanation of the **root activities** concept that is mentioned in the **Call Tree** panel, **Bottom-Up** panel, and **Event Log** panel.</span></span>  

<span data-ttu-id="e98f4-250">根活动是导致浏览器执行某些工作的活动。</span><span class="sxs-lookup"><span data-stu-id="e98f4-250">Root activities are those which cause the browser to do some work.</span></span>  <span data-ttu-id="e98f4-251">例如，当您选择网页时，浏览器将运行 `Event` 活动作为根活动。</span><span class="sxs-lookup"><span data-stu-id="e98f4-251">For example, when you choose a webpage, the browser runs an `Event` activity as the root activity.</span></span>  <span data-ttu-id="e98f4-252">`Event`这可能会导致处理程序运行，等等。</span><span class="sxs-lookup"><span data-stu-id="e98f4-252">That `Event` may cause a handler to run, and so on.</span></span>  

<span data-ttu-id="e98f4-253">在主节的图表上\*\*\*\*，根活动位于图表的顶部。</span><span class="sxs-lookup"><span data-stu-id="e98f4-253">In the flame chart of the **Main** section, root activities are at the top of the chart.</span></span>  <span data-ttu-id="e98f4-254">在 **"呼叫树** "和" **事件日志** "面板中，根活动是顶级项目。</span><span class="sxs-lookup"><span data-stu-id="e98f4-254">In the **Call Tree** and **Event Log** panels, root activities are the top-level items.</span></span>  

<span data-ttu-id="e98f4-255">导航到 ["呼叫树](#the-call-tree-panel) "面板，了解根活动示例。</span><span class="sxs-lookup"><span data-stu-id="e98f4-255">Navigate to the [Call Tree](#the-call-tree-panel) panel for an example of root activities.</span></span>  

#### <a name="the-call-tree-panel"></a><span data-ttu-id="e98f4-256">呼叫树面板</span><span class="sxs-lookup"><span data-stu-id="e98f4-256">The Call Tree panel</span></span>  

<span data-ttu-id="e98f4-257">使用 **"呼叫树** "面板查看 [哪些根活动](#root-activities) 导致工作最多。</span><span class="sxs-lookup"><span data-stu-id="e98f4-257">Use the **Call Tree** panel to view which [root activities](#root-activities) cause the most work.</span></span>  

<span data-ttu-id="e98f4-258">呼叫 **树** 面板仅显示在录制的选定部分期间的活动。</span><span class="sxs-lookup"><span data-stu-id="e98f4-258">The **Call Tree** panel only displays activities during the selected portion of the recording.</span></span>  <span data-ttu-id="e98f4-259">导航 [到"选择录音的一部分](#select-a-portion-of-a-recording) "以了解如何选择部分。</span><span class="sxs-lookup"><span data-stu-id="e98f4-259">Navigate to [Select a portion of a recording](#select-a-portion-of-a-recording) to learn how to select portions.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-call-tree.msft.png" alt-text="呼叫树面板" lightbox="../media/evaluate-performance-performance-call-tree.msft.png":::
   <span data-ttu-id="e98f4-261">呼叫 **树** 面板</span><span class="sxs-lookup"><span data-stu-id="e98f4-261">The **Call Tree** panel</span></span>  
:::image-end:::  

<span data-ttu-id="e98f4-262">在上图中，活动列中的顶级项目（如\*\*\*\* `Evaluate Script` 根 `Parse HTML` 活动）和根活动。</span><span class="sxs-lookup"><span data-stu-id="e98f4-262">In the previous figure, the top-level of items in the **Activity** column, such as `Evaluate Script` and `Parse HTML` are root activities.</span></span>  <span data-ttu-id="e98f4-263">嵌套表示调用堆栈。</span><span class="sxs-lookup"><span data-stu-id="e98f4-263">The nesting represents the call stack.</span></span>  <span data-ttu-id="e98f4-264">例如，在上图中 `Parse HTML` ，导致和 `Evaluate Script` `Compile Script` `(anonymous)` 的原因。</span><span class="sxs-lookup"><span data-stu-id="e98f4-264">For example, in the previous figure, `Parse HTML` which caused `Evaluate Script` which caused `Compile Script` and `(anonymous)`.</span></span>  

<span data-ttu-id="e98f4-265">**"自** 用时间"表示直接用于该活动的时间。</span><span class="sxs-lookup"><span data-stu-id="e98f4-265">**Self Time** represents the time directly spent in that activity.</span></span>  <span data-ttu-id="e98f4-266">**总时间** 表示该活动或任何子项所花的时间。</span><span class="sxs-lookup"><span data-stu-id="e98f4-266">**Total Time** represents the time spent in that activity or any of the children.</span></span>  

<span data-ttu-id="e98f4-267">选择 **"自时间\*\*\*\*"、"总**时间"或 **"活动**"按该列对表进行排序。</span><span class="sxs-lookup"><span data-stu-id="e98f4-267">Choose **Self Time**, **Total Time**, or **Activity** to sort the table by that column.</span></span>  

<span data-ttu-id="e98f4-268">使用 **"筛选器** "文本框按活动名称筛选事件。</span><span class="sxs-lookup"><span data-stu-id="e98f4-268">Use the **Filter** text box to filter events by activity name.</span></span>  

<span data-ttu-id="e98f4-269">默认情况下，**分组菜单**设置为"**无分组"。**</span><span class="sxs-lookup"><span data-stu-id="e98f4-269">By default the **Grouping** menu is set to **No Grouping**.</span></span>  <span data-ttu-id="e98f4-270">使用 **"分组"** 菜单根据各种条件对活动表进行排序。</span><span class="sxs-lookup"><span data-stu-id="e98f4-270">Use the **Grouping** menu to sort the activity table based on various criteria.</span></span>  

<span data-ttu-id="e98f4-271">Choose **Show Heaviest Stack** \ (Show ![ Heaviest Stack ][ImageShowHeaviestStackIcon] \) to reveal another table to the right of the **Activity** table.</span><span class="sxs-lookup"><span data-stu-id="e98f4-271">Choose **Show Heaviest Stack** \(![Show Heaviest Stack][ImageShowHeaviestStackIcon]\) to reveal another table to the right of the **Activity** table.</span></span>  <span data-ttu-id="e98f4-272">选择一个活动以填充 **最重的 Stack** 表。</span><span class="sxs-lookup"><span data-stu-id="e98f4-272">Choose an activity to populate the **Heaviest Stack** table.</span></span>  <span data-ttu-id="e98f4-273">最 **重的 Stack** 表显示所选活动的哪些子项运行时间最长。</span><span class="sxs-lookup"><span data-stu-id="e98f4-273">The **Heaviest Stack** table displays which children of the selected activity took the longest time to run.</span></span>  

#### <a name="the-bottom-up-panel"></a><span data-ttu-id="e98f4-274">Bottom-Up面板</span><span class="sxs-lookup"><span data-stu-id="e98f4-274">The Bottom-Up panel</span></span>  

<span data-ttu-id="e98f4-275">使用 **"从下向上"** 面板查看哪些活动直接在聚合中所花时间最多。</span><span class="sxs-lookup"><span data-stu-id="e98f4-275">Use the **Bottom-Up** panel to view which activities directly took up the most time in aggregate.</span></span>  

<span data-ttu-id="e98f4-276">底部 **向上面板** 仅显示在录制的选定部分期间的活动。</span><span class="sxs-lookup"><span data-stu-id="e98f4-276">The **Bottom-Up** panel only displays activities during the selected portion of the recording.</span></span>  <span data-ttu-id="e98f4-277">导航 [到"选择录音的一部分](#select-a-portion-of-a-recording) "以了解如何选择部分。</span><span class="sxs-lookup"><span data-stu-id="e98f4-277">Navigate to [Select a portion of a recording](#select-a-portion-of-a-recording) to learn how to select portions.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-bottoms-up.msft.png" alt-text="Bottom-Up面板" lightbox="../media/evaluate-performance-performance-bottoms-up.msft.png":::
   <span data-ttu-id="e98f4-279">从**下向上面板**</span><span class="sxs-lookup"><span data-stu-id="e98f4-279">The **Bottom-Up** panel</span></span>  
:::image-end:::  

<span data-ttu-id="e98f4-280">在上 **图** 的"主节"图表上，导航到几乎花费运行的所有时间 `Parse HTML` 。</span><span class="sxs-lookup"><span data-stu-id="e98f4-280">In the **Main** section flame chart of the previous figure, navigate to that almost practically all of the time was spent running `Parse HTML`.</span></span>  <span data-ttu-id="e98f4-281">上图的 **"下** 向上"面板中的顶部活动是 `Parse HTML` 。</span><span class="sxs-lookup"><span data-stu-id="e98f4-281">The top activity in the **Bottom-Up** panel of the previous figure is `Parse HTML`.</span></span>  <!--In the flame chart of the previous figure, the yellow below the calls to `wait` are actually thousands of `Minor GC` calls.  -->  <span data-ttu-id="e98f4-282">导航到 **"下向上"面板** ，下一个最昂贵的活动是 `Layout` 。</span><span class="sxs-lookup"><span data-stu-id="e98f4-282">Navigate to the **Bottom-Up** panel, the next most expensive activity is `Layout`.</span></span>  

<span data-ttu-id="e98f4-283">" **自** 时间"列表示直接在活动（发生的所有事件）中花费的聚合时间。</span><span class="sxs-lookup"><span data-stu-id="e98f4-283">The **Self Time** column represents the aggregated time spent directly in that activity, across all of the occurrences.</span></span>  

<span data-ttu-id="e98f4-284">" **总时间** "列表示该活动或任何子项所花费的聚合时间。</span><span class="sxs-lookup"><span data-stu-id="e98f4-284">The **Total Time** column represents aggregated time spent in that activity or any of the children.</span></span>  

#### <a name="the-event-log-panel"></a><span data-ttu-id="e98f4-285">事件日志面板</span><span class="sxs-lookup"><span data-stu-id="e98f4-285">The Event Log panel</span></span>  

<span data-ttu-id="e98f4-286">使用 **"事件** 日志"面板以记录期间活动发生的顺序查看活动。</span><span class="sxs-lookup"><span data-stu-id="e98f4-286">Use the **Event Log** panel to view activities in the order in which they occurred during the recording.</span></span>  

<span data-ttu-id="e98f4-287">事件 **日志** 面板仅显示记录选定部分期间的活动。</span><span class="sxs-lookup"><span data-stu-id="e98f4-287">The **Event Log** panel only displays activities during the selected portion of the recording.</span></span>  <span data-ttu-id="e98f4-288">导航 [到"选择录音的一部分](#select-a-portion-of-a-recording) "以了解如何选择部分。</span><span class="sxs-lookup"><span data-stu-id="e98f4-288">Navigate to [Select a portion of a recording](#select-a-portion-of-a-recording) to learn how to select portions.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-event-log.msft.png" alt-text="事件日志面板" lightbox="../media/evaluate-performance-performance-event-log.msft.png":::
   <span data-ttu-id="e98f4-290">事件 **日志** 面板</span><span class="sxs-lookup"><span data-stu-id="e98f4-290">The **Event Log** panel</span></span>  
:::image-end:::  

<span data-ttu-id="e98f4-291">" **开始时间** "列表示该活动的开始点，相对于录制的开始点。</span><span class="sxs-lookup"><span data-stu-id="e98f4-291">The **Start Time** column represents the point at which that activity started, relative to the start of the recording.</span></span>  <span data-ttu-id="e98f4-292">例如，上图中选定项目的开始时间意味着活动在 `175.7 ms` 录制开始后的 175.7 毫秒开始。</span><span class="sxs-lookup"><span data-stu-id="e98f4-292">For example, the start time of `175.7 ms` for the selected item in the previous figure means that activity started 175.7 ms after the recording started.</span></span>  

<span data-ttu-id="e98f4-293">" **自** 时间"列表示直接用于该活动的时间。</span><span class="sxs-lookup"><span data-stu-id="e98f4-293">The **Self Time** column represents the time spent directly in that activity.</span></span>  

<span data-ttu-id="e98f4-294">**"总时间**"列表示直接用于该活动或任何子项的时间。</span><span class="sxs-lookup"><span data-stu-id="e98f4-294">The **Total Time** columns represents time spent directly in that activity or in any of the children.</span></span>  

<span data-ttu-id="e98f4-295">选择 **"开始时间\*\*\*\*"、"\*\*\*\*开始时间"或**"总时间"按该列对表进行排序。</span><span class="sxs-lookup"><span data-stu-id="e98f4-295">Choose **Start Time**, **Self Time**, or **Total Time** to sort the table by that column.</span></span>

<span data-ttu-id="e98f4-296">使用 **"筛选器** "文本框按名称筛选活动。</span><span class="sxs-lookup"><span data-stu-id="e98f4-296">Use the **Filter** text box to filter activities by name.</span></span>  

<span data-ttu-id="e98f4-297">使用 **"持续时间** "菜单筛选出任何时间少于 1 毫秒或 15 毫秒的活动。</span><span class="sxs-lookup"><span data-stu-id="e98f4-297">Use the **Duration** menu to filter out any activities that took less than 1 ms or 15 ms.</span></span>  <span data-ttu-id="e98f4-298">默认情况下 **，"持续时间** "菜单设置为 **"** 全部"，表示显示所有活动。</span><span class="sxs-lookup"><span data-stu-id="e98f4-298">By default the **Duration** menu is set to **All**, meaning all activities are shown.</span></span>  

<span data-ttu-id="e98f4-299">禁用**加载**、**脚本、\*\*\*\*呈现**或**绘制**复选框以筛选出这些类别的所有活动。</span><span class="sxs-lookup"><span data-stu-id="e98f4-299">Disable the **Loading**, **Scripting**, **Rendering**, or **Painting** checkboxes to filter out all activities from those categories.</span></span>  

### <a name="view-gpu-activity"></a><span data-ttu-id="e98f4-300">查看 GPU 活动</span><span class="sxs-lookup"><span data-stu-id="e98f4-300">View GPU activity</span></span>  

<span data-ttu-id="e98f4-301">在 GPU 部分查看 **GPU** 活动。</span><span class="sxs-lookup"><span data-stu-id="e98f4-301">View GPU activity in the **GPU** section.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-gpu-zoomed.msft.png" alt-text="GPU 部分" lightbox="../media/evaluate-performance-performance-gpu-zoomed.msft.png":::
   <span data-ttu-id="e98f4-303">**GPU**部分</span><span class="sxs-lookup"><span data-stu-id="e98f4-303">The **GPU** section</span></span>  
:::image-end:::  

### <a name="view-raster-activity"></a><span data-ttu-id="e98f4-304">查看栅格活动</span><span class="sxs-lookup"><span data-stu-id="e98f4-304">View raster activity</span></span>  

<span data-ttu-id="e98f4-305">在"Raster"部分查看 **栅格** 活动。</span><span class="sxs-lookup"><span data-stu-id="e98f4-305">View raster activity in the **Raster** section.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-raster.msft.png" alt-text=""Raster"部分" lightbox="../media/evaluate-performance-performance-raster.msft.png":::
   <span data-ttu-id="e98f4-307">**"Raster"** 部分</span><span class="sxs-lookup"><span data-stu-id="e98f4-307">The **Raster** section</span></span>  
:::image-end:::  

### <a name="view-interactions"></a><span data-ttu-id="e98f4-308">查看交互</span><span class="sxs-lookup"><span data-stu-id="e98f4-308">View interactions</span></span>  

<span data-ttu-id="e98f4-309">使用 **"交互"** 部分查找和分析在录制过程中发生的用户交互。</span><span class="sxs-lookup"><span data-stu-id="e98f4-309">Use the **Interactions** section to find and analyze user interactions that happened during the recording.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-interactions-animation.msft.png" alt-text=""交互"部分" lightbox="../media/evaluate-performance-performance-interactions-animation.msft.png":::
   <span data-ttu-id="e98f4-311">" **交互"** 部分</span><span class="sxs-lookup"><span data-stu-id="e98f4-311">The **Interactions** section</span></span>  
:::image-end:::  

<span data-ttu-id="e98f4-312">交互底部的红线表示等待主线程所花的时间。</span><span class="sxs-lookup"><span data-stu-id="e98f4-312">A red line at the bottom of an interaction represents time spent waiting for the main thread.</span></span>  

<span data-ttu-id="e98f4-313">选择交互以查看"摘要"面板中 **有关它的信息** 。</span><span class="sxs-lookup"><span data-stu-id="e98f4-313">Choose an interaction to view more information about it in the **Summary** panel.</span></span>  

### <a name="analyze-frames-per-second-fps"></a><span data-ttu-id="e98f4-314">分析每秒帧数 (FPS) </span><span class="sxs-lookup"><span data-stu-id="e98f4-314">Analyze frames per second (FPS)</span></span>  

<span data-ttu-id="e98f4-315">DevTools 提供了多种分析每秒帧的方法：</span><span class="sxs-lookup"><span data-stu-id="e98f4-315">DevTools provides numerous ways to analyze frames per second:</span></span>  

*   <span data-ttu-id="e98f4-316">使用 [FPS 图表](#the-fps-chart) 获取在录制期间 FPS 的概述。</span><span class="sxs-lookup"><span data-stu-id="e98f4-316">Use [the FPS chart](#the-fps-chart) to get an overview of FPS over the duration of the recording.</span></span>  
*   <span data-ttu-id="e98f4-317">使用 ["框架"](#the-frames-section) 部分查看特定帧所需要的时间。</span><span class="sxs-lookup"><span data-stu-id="e98f4-317">Use [the Frames section](#the-frames-section) to view how long a particular frame took.</span></span>  
*   <span data-ttu-id="e98f4-318">在 **页面运行时，使用 FPS** 指示器对 FPS 进行实时估计。</span><span class="sxs-lookup"><span data-stu-id="e98f4-318">Use the **FPS meter** for a realtime estimate of FPS as the page runs.</span></span>  <span data-ttu-id="e98f4-319">使用 FPS 指示器实时导航到"查看[每秒帧数"。](#view-frames-per-second-in-realtime-with-the-fps-meter)</span><span class="sxs-lookup"><span data-stu-id="e98f4-319">Navigate to [View frames per second in realtime with the FPS meter](#view-frames-per-second-in-realtime-with-the-fps-meter).</span></span>  
    
#### <a name="the-fps-chart"></a><span data-ttu-id="e98f4-320">FPS 图表</span><span class="sxs-lookup"><span data-stu-id="e98f4-320">The FPS chart</span></span>  

<span data-ttu-id="e98f4-321">**FPS**图表提供在录制期间帧速率的概述。</span><span class="sxs-lookup"><span data-stu-id="e98f4-321">The **FPS** chart provides an overview of the frame rate across the duration of a recording.</span></span>  <span data-ttu-id="e98f4-322">通常，绿色条形越高，帧速率越好。</span><span class="sxs-lookup"><span data-stu-id="e98f4-322">In general, the higher the green bar, the better the frame rate.</span></span>  

<span data-ttu-id="e98f4-323">**FPS**图表上方的红色条是一条警告，指出帧速率下降得低到可能损害用户体验。</span><span class="sxs-lookup"><span data-stu-id="e98f4-323">A red bar above the **FPS** chart is a warning that the frame rate dropped so low that it probably harmed the user's experience.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-fps-highlight.msft.png" alt-text="FPS 图表" lightbox="../media/evaluate-performance-performance-fps-highlight.msft.png":::
   <span data-ttu-id="e98f4-325">**FPS** 图表</span><span class="sxs-lookup"><span data-stu-id="e98f4-325">The **FPS** chart</span></span>  
:::image-end:::  

#### <a name="the-frames-section"></a><span data-ttu-id="e98f4-326">"框架"部分</span><span class="sxs-lookup"><span data-stu-id="e98f4-326">The Frames section</span></span>  

<span data-ttu-id="e98f4-327">" **框架** "部分将告知你特定帧所使用时间。</span><span class="sxs-lookup"><span data-stu-id="e98f4-327">The **Frames** section tells you exactly how long a particular frame took.</span></span>  

<span data-ttu-id="e98f4-328">将鼠标悬停在框架上，查看工具提示，并详细了解它。</span><span class="sxs-lookup"><span data-stu-id="e98f4-328">Hover on a frame to view a tooltip with more information about it.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-frames-hover.msft.png" alt-text="鼠标悬停在框架上" lightbox="../media/evaluate-performance-performance-frames-hover.msft.png":::
   <span data-ttu-id="e98f4-330">鼠标悬停在框架上</span><span class="sxs-lookup"><span data-stu-id="e98f4-330">Hover on a frame</span></span>  
:::image-end:::  

<span data-ttu-id="e98f4-331">选择一个框架，在"摘要"面板中查看有关 **帧详细信息** 。</span><span class="sxs-lookup"><span data-stu-id="e98f4-331">Choose a frame to view more information about the frame in the **Summary** panel.</span></span>  <span data-ttu-id="e98f4-332">DevTools 将所选框架以蓝色分级显示。</span><span class="sxs-lookup"><span data-stu-id="e98f4-332">DevTools outlines the selected frame in blue.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-frames-summary.msft.png" alt-text="在"摘要"面板中查看框架" lightbox="../media/evaluate-performance-performance-frames-summary.msft.png":::
   <span data-ttu-id="e98f4-334">在"摘要" **面板中查看** 框架</span><span class="sxs-lookup"><span data-stu-id="e98f4-334">View a frame in the **Summary** panel</span></span>  
:::image-end:::  

### <a name="view-network-requests"></a><span data-ttu-id="e98f4-335">查看网络请求</span><span class="sxs-lookup"><span data-stu-id="e98f4-335">View network requests</span></span>  

<span data-ttu-id="e98f4-336">展开 **"网络** "部分以查看记录期间发生的网络请求的瀑布。</span><span class="sxs-lookup"><span data-stu-id="e98f4-336">Expand the **Network** section to view a waterfall of network requests that occurred during the recording.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-network.msft.png" alt-text=""网络"部分" lightbox="../media/evaluate-performance-performance-network.msft.png":::
   <span data-ttu-id="e98f4-338">" **网络"** 部分</span><span class="sxs-lookup"><span data-stu-id="e98f4-338">The **Network** section</span></span>  
:::image-end:::  

<span data-ttu-id="e98f4-339">请求按如下方式进行颜色编码：</span><span class="sxs-lookup"><span data-stu-id="e98f4-339">Requests are color-coded as follows:</span></span>  

*   <span data-ttu-id="e98f4-340">HTML：蓝色</span><span class="sxs-lookup"><span data-stu-id="e98f4-340">HTML: Blue</span></span>  
*   <span data-ttu-id="e98f4-341">CSS：紫色</span><span class="sxs-lookup"><span data-stu-id="e98f4-341">CSS: Purple</span></span>  
*   <span data-ttu-id="e98f4-342">JS：黄色</span><span class="sxs-lookup"><span data-stu-id="e98f4-342">JS: Yellow</span></span>  
*   <span data-ttu-id="e98f4-343">图像：绿色</span><span class="sxs-lookup"><span data-stu-id="e98f4-343">Images: Green</span></span>  
    
<span data-ttu-id="e98f4-344">选择一个请求，在"摘要"面板中查看 **有关它详细信息** 。</span><span class="sxs-lookup"><span data-stu-id="e98f4-344">Choose a request to view more information about it in the **Summary** panel.</span></span>  <span data-ttu-id="e98f4-345">例如，在上图中，"摘要"\*\*\*\* 面板显示有关在"网络"部分选择的蓝色**请求详细信息。**</span><span class="sxs-lookup"><span data-stu-id="e98f4-345">For example, in the previous figure, the **Summary** panel is displaying more information about the blue request that is selected in the **Network** section.</span></span>  

<span data-ttu-id="e98f4-346">请求左上方的深蓝色正方形表示它是优先级较高的请求。</span><span class="sxs-lookup"><span data-stu-id="e98f4-346">A darker-blue square in the top-left of a request means it is a higher-priority request.</span></span>  <span data-ttu-id="e98f4-347">浅蓝色正方形表示优先级较低。</span><span class="sxs-lookup"><span data-stu-id="e98f4-347">A lighter-blue square means lower-priority.</span></span>  <span data-ttu-id="e98f4-348">例如，在上图中，选择的蓝色请求的优先级更高，其下方的绿色请求优先级较低。</span><span class="sxs-lookup"><span data-stu-id="e98f4-348">For example, in the previous figure, the blue, selected request is higher-priority, and the green one below it is lower-priority.</span></span>  

<span data-ttu-id="e98f4-349">在下图的第 1 个部分中，请求表示为左侧的线条、中间带深色部分的条形图和浅色部分，以及右侧 `www.bing.com` 线条。</span><span class="sxs-lookup"><span data-stu-id="e98f4-349">In the 1st of the following figures, the request for `www.bing.com` is represented by a line on the left, a bar in the middle with a dark portion and a light portion, and a line on the right.</span></span>  <span data-ttu-id="e98f4-350">下图的第 2 个显示了网络工具的"计时"面板中相同请求**的相应**表示形式。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="e98f4-350">In the 2nd of the following figures shows the corresponding representation of the same request in the **Timing** panel of the **Network** tool.</span></span>  <span data-ttu-id="e98f4-351">下面说明这两种表示形式如何相互映射：</span><span class="sxs-lookup"><span data-stu-id="e98f4-351">Here is how these two representations map to each other:</span></span>

*   <span data-ttu-id="e98f4-352">左侧行是事件组 `Connection Start` （包含此事件）的所有内容。</span><span class="sxs-lookup"><span data-stu-id="e98f4-352">The left line is everything up to the `Connection Start` group of events, inclusive.</span></span>  <span data-ttu-id="e98f4-353">换句话说，它是之前的所有内容， `Request Sent` 独占。</span><span class="sxs-lookup"><span data-stu-id="e98f4-353">In other words, it is everything before `Request Sent`, exclusive.</span></span>  
*   <span data-ttu-id="e98f4-354">条形图的光线部分为 `Request Sent` 和 `Waiting (TTFB)` 。</span><span class="sxs-lookup"><span data-stu-id="e98f4-354">The light portion of the bar is `Request Sent` and `Waiting (TTFB)`.</span></span>  
*   <span data-ttu-id="e98f4-355">条形图的深色部分是 `Content Download` 。</span><span class="sxs-lookup"><span data-stu-id="e98f4-355">The dark portion of the bar is `Content Download`.</span></span>  
*   <span data-ttu-id="e98f4-356">正确的行实质上是等待主线程所花的时间。</span><span class="sxs-lookup"><span data-stu-id="e98f4-356">The right line is essentially time spent waiting for the main thread.</span></span>  <span data-ttu-id="e98f4-357">This is not represented in the **Timing** panel.</span><span class="sxs-lookup"><span data-stu-id="e98f4-357">This is not represented in the **Timing** panel.</span></span>  
    
:::row:::
   :::column span="":::
      :::image type="complex" source="../media/evaluate-performance-bing-performance-network.msft.png" alt-text="请求的线www.bing.com表示形式" lightbox="../media/evaluate-performance-bing-performance-network.msft.png":::
         <span data-ttu-id="e98f4-359">请求的线栏 `www.bing.com` 表示形式</span><span class="sxs-lookup"><span data-stu-id="e98f4-359">The line-bar representation of the `www.bing.com` request</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/evaluate-performance-bing-network-timing.msft.png" alt-text="网络工具" lightbox="../media/evaluate-performance-bing-network-timing.msft.png":::
         <span data-ttu-id="e98f4-361">网络**工具**</span><span class="sxs-lookup"><span data-stu-id="e98f4-361">The **Network** tool</span></span>  
<span data-ttu-id="e98f4-362">： ：：image-end：：：</span><span class="sxs-lookup"><span data-stu-id="e98f4-362">:     ::image-end:::</span></span>  
   :::column-end:::
:::row-end:::

### <a name="view-memory-metrics"></a><span data-ttu-id="e98f4-363">查看内存指标</span><span class="sxs-lookup"><span data-stu-id="e98f4-363">View memory metrics</span></span>  

<span data-ttu-id="e98f4-364">打开" **内存"** 复选框以查看上次录制中的内存指标。</span><span class="sxs-lookup"><span data-stu-id="e98f4-364">Turn on the **Memory** checkbox to view memory metrics from the last recording.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-memory-highlight.msft.png" alt-text=""内存"复选框" lightbox="../media/evaluate-performance-performance-memory-highlight.msft.png":::
   <span data-ttu-id="e98f4-366">" **内存"** 复选框</span><span class="sxs-lookup"><span data-stu-id="e98f4-366">The **Memory** checkbox</span></span>  
:::image-end:::  

<span data-ttu-id="e98f4-367">DevTools 在" **摘要"** 面板上方显示新的 **内存** 图表。</span><span class="sxs-lookup"><span data-stu-id="e98f4-367">DevTools displays a new **Memory** chart, above the **Summary** panel.</span></span>  <span data-ttu-id="e98f4-368">NET 图表下方还有一**个新的图表，** 称为**HEAP。**</span><span class="sxs-lookup"><span data-stu-id="e98f4-368">There is also a new chart below the **NET** chart, called **HEAP**.</span></span>  <span data-ttu-id="e98f4-369">**HEAP**图表提供与内存图表中**JS 堆**行**相同的**信息。</span><span class="sxs-lookup"><span data-stu-id="e98f4-369">The **HEAP** chart provides the same information as the **JS Heap** line in the **Memory** chart.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-memory-chart.msft.png" alt-text="内存指标" lightbox="../media/evaluate-performance-performance-memory-chart.msft.png":::
   <span data-ttu-id="e98f4-371">内存指标</span><span class="sxs-lookup"><span data-stu-id="e98f4-371">Memory metrics</span></span>  
:::image-end:::  

<span data-ttu-id="e98f4-372">图表上的彩色线条映射到图表上方的彩色复选框。</span><span class="sxs-lookup"><span data-stu-id="e98f4-372">The colored lines on the chart map to the colored checkboxes above the chart.</span></span>  
<span data-ttu-id="e98f4-373">禁用复选框以在图表中隐藏该类别。</span><span class="sxs-lookup"><span data-stu-id="e98f4-373">Disable a checkbox to hide that category from the chart.</span></span>  

<span data-ttu-id="e98f4-374">图表仅显示当前选定的录制区域。</span><span class="sxs-lookup"><span data-stu-id="e98f4-374">The chart only displays the region of the recording that is currently selected.</span></span>  <span data-ttu-id="e98f4-375">例如，在上图中，内存图表只\*\*\*\* 显示从 400 毫秒标记到 1750 毫秒标记的内存使用量。</span><span class="sxs-lookup"><span data-stu-id="e98f4-375">For example, in the previous figure, the **Memory** chart is only showing memory usage from around the 400 ms mark to the 1750 ms mark.</span></span>  

### <a name="view-the-duration-of-a-portion-of-a-recording"></a><span data-ttu-id="e98f4-376">查看部分录制的持续时间</span><span class="sxs-lookup"><span data-stu-id="e98f4-376">View the duration of a portion of a recording</span></span>  

<span data-ttu-id="e98f4-377">分析网络或\*\*Main\*\*\*\*\*\* 等节时，有时需要更准确的特定事件估计时间。</span><span class="sxs-lookup"><span data-stu-id="e98f4-377">When analyzing a section like **Network** or **Main**, sometimes you need a more precise estimate of how long certain events took.</span></span>  <span data-ttu-id="e98f4-378">按住 `Shift` 、选择并按住，然后向左或向右拖动以选择录制的一部分。</span><span class="sxs-lookup"><span data-stu-id="e98f4-378">Hold `Shift`, choose and hold, and drag left or right to select a portion of the recording.</span></span>  <span data-ttu-id="e98f4-379">在选择的底部，DevTools 显示该部分所需要时间。</span><span class="sxs-lookup"><span data-stu-id="e98f4-379">At the bottom of your selection, DevTools shows how long that portion took.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-main-duration.msft.png" alt-text="查看部分录制的持续时间" lightbox="../media/evaluate-performance-performance-main-duration.msft.png":::
   <span data-ttu-id="e98f4-381">查看部分录制的持续时间</span><span class="sxs-lookup"><span data-stu-id="e98f4-381">View the duration of a portion of a recording</span></span>  
:::image-end:::  

### <a name="view-a-screenshot"></a><span data-ttu-id="e98f4-382">查看屏幕截图</span><span class="sxs-lookup"><span data-stu-id="e98f4-382">View a screenshot</span></span>  

<span data-ttu-id="e98f4-383">导航到 [录制时捕获屏幕截图](#capture-screenshots-while-recording) ，了解如何打开屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="e98f4-383">Navigate to [Capture screenshots while recording](#capture-screenshots-while-recording) to learn how to turn on screenshots.</span></span>  

<span data-ttu-id="e98f4-384">将鼠标 **悬停在"概述** "上可查看页面在录制期间的外观的屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="e98f4-384">Hover on the **Overview** to view a screenshot of how the page looked during that moment of the recording.</span></span>  <span data-ttu-id="e98f4-385">概述**是**包含 CPU、FPS\*\*\*\* 和\*\*\*\* **NET**图表的部分。</span><span class="sxs-lookup"><span data-stu-id="e98f4-385">The **Overview** is the section that contains the **CPU**, **FPS**, and **NET** charts.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-screenshots-hover.msft.png" alt-text="查看屏幕截图" lightbox="../media/evaluate-performance-performance-screenshots-hover.msft.png":::
   <span data-ttu-id="e98f4-387">查看屏幕截图</span><span class="sxs-lookup"><span data-stu-id="e98f4-387">View a screenshot</span></span>  
:::image-end:::  

<span data-ttu-id="e98f4-388">您还可以通过选择"框架"部分中的框架 **来查看屏幕截图** 。</span><span class="sxs-lookup"><span data-stu-id="e98f4-388">You may also view screenshots by choosing a frame in the **Frames** section.</span></span>  <span data-ttu-id="e98f4-389">DevTools 在"摘要"面板中显示小 **版本的屏幕截图** 。</span><span class="sxs-lookup"><span data-stu-id="e98f4-389">DevTools displays a small version of the screenshot in the **Summary** panel.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-summary-preview.msft.png" alt-text="在"摘要"面板中查看屏幕截图" lightbox="../media/evaluate-performance-performance-summary-preview.msft.png":::
   <span data-ttu-id="e98f4-391">在"摘要"面板 **中查看** 屏幕截图</span><span class="sxs-lookup"><span data-stu-id="e98f4-391">View a screenshot in the **Summary** panel</span></span>  
:::image-end:::  

<span data-ttu-id="e98f4-392">选择"摘要 **"面板中的缩略图** 以放大屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="e98f4-392">Choose the thumbnail in the **Summary** panel to zoom in on the screenshot.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-summary-preview-select.msft.png" alt-text="从"摘要"面板中放大屏幕截图" lightbox="../media/evaluate-performance-performance-summary-preview-select.msft.png":::
   <span data-ttu-id="e98f4-394">从"摘要"面板**中放大屏幕截图**</span><span class="sxs-lookup"><span data-stu-id="e98f4-394">Zoom into a screenshot from the **Summary** panel</span></span>  
:::image-end:::  

### <a name="view-layers-information"></a><span data-ttu-id="e98f4-395">查看图层信息</span><span class="sxs-lookup"><span data-stu-id="e98f4-395">View layers information</span></span>  

<span data-ttu-id="e98f4-396">若要查看有关帧的高级层信息，请执行：</span><span class="sxs-lookup"><span data-stu-id="e98f4-396">To view advanced layers information about a frame:</span></span>  

1.  <span data-ttu-id="e98f4-397">[打开高级画图检测](#turn-on-advanced-paint-instrumentation)。</span><span class="sxs-lookup"><span data-stu-id="e98f4-397">[Turn on advanced paint instrumentation](#turn-on-advanced-paint-instrumentation).</span></span>  
1.  <span data-ttu-id="e98f4-398">在"框架"部分中 **选择** 一个图文框。</span><span class="sxs-lookup"><span data-stu-id="e98f4-398">Choose a frame in the **Frames** section.</span></span>  <span data-ttu-id="e98f4-399">DevTools 在"事件日志"面板旁\*\*\*\* 的新"层"面板中显示有关**图层**的信息。</span><span class="sxs-lookup"><span data-stu-id="e98f4-399">DevTools displays information about the layers in the new **Layers** panel, next to the **Event Log** panel.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-layers-all.msft.png" alt-text=""层"窗格" lightbox="../media/evaluate-performance-layers-all.msft.png":::
       <span data-ttu-id="e98f4-401">" **层"** 窗格</span><span class="sxs-lookup"><span data-stu-id="e98f4-401">The **Layers** pane</span></span>  
    :::image-end:::  
    
<span data-ttu-id="e98f4-402">将鼠标悬停在一个图层上，以在图表中突出显示它。</span><span class="sxs-lookup"><span data-stu-id="e98f4-402">Hover on a layer to highlight it in the diagram.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-frames-document-nav-bar-highlighted.msft.png" alt-text="突出显示图层" lightbox="../media/evaluate-performance-performance-frames-document-nav-bar-highlighted.msft.png":::
   <span data-ttu-id="e98f4-404">突出显示图层</span><span class="sxs-lookup"><span data-stu-id="e98f4-404">Highlight a layer</span></span>  
:::image-end:::  

<span data-ttu-id="e98f4-405">若要移动图表，请：</span><span class="sxs-lookup"><span data-stu-id="e98f4-405">To move the diagram:</span></span>  

*   <span data-ttu-id="e98f4-406">选择 **"平移** 模式 (![ 平移模式 ][ImagePanModeIcon] \) 沿 X 和 Y 轴移动。</span><span class="sxs-lookup"><span data-stu-id="e98f4-406">Choose **Pan Mode** \(![Pan Mode][ImagePanModeIcon]\) to move along the X and Y axes.</span></span>  
*   <span data-ttu-id="e98f4-407">选择 **旋转模式** \ (![ 旋转模式 ][ImageRotateModeIcon] \) 沿 Z 轴旋转。</span><span class="sxs-lookup"><span data-stu-id="e98f4-407">Choose **Rotate Mode** \(![Rotate Mode][ImageRotateModeIcon]\) to rotate along the Z axis.</span></span>  
*   <span data-ttu-id="e98f4-408">Choose **Reset Transform** \ (Reset Transform ![ ][ImageResetTransformIcon] \) to reset the diagram to the original position.</span><span class="sxs-lookup"><span data-stu-id="e98f4-408">Choose **Reset Transform** \(![Reset Transform][ImageResetTransformIcon]\) to reset the diagram to the original position.</span></span>  
    
### <a name="view-paint-profiler"></a><span data-ttu-id="e98f4-409">查看绘制探查器</span><span class="sxs-lookup"><span data-stu-id="e98f4-409">View paint profiler</span></span>  

<span data-ttu-id="e98f4-410">若要查看有关绘制事件的高级信息，请：</span><span class="sxs-lookup"><span data-stu-id="e98f4-410">To view advanced information about a paint event:</span></span>  

1.  <span data-ttu-id="e98f4-411">[打开](#turn-on-advanced-paint-instrumentation)。</span><span class="sxs-lookup"><span data-stu-id="e98f4-411">[Turn on](#turn-on-advanced-paint-instrumentation).</span></span>  
1.  <span data-ttu-id="e98f4-412">在" **主** "部分 **选择"绘制"** 事件。</span><span class="sxs-lookup"><span data-stu-id="e98f4-412">Choose a **Paint** event in the **Main** section.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-paint-profiler.msft.png" alt-text=""绘制探查器"面板" lightbox="../media/evaluate-performance-paint-profiler.msft.png":::
       <span data-ttu-id="e98f4-414">" **绘制探查器"** 面板</span><span class="sxs-lookup"><span data-stu-id="e98f4-414">The **Paint Profiler** panel</span></span>  
    :::image-end:::  
    
## <a name="analyze-rendering-performance-with-the-rendering-tool"></a><span data-ttu-id="e98f4-415">使用呈现工具分析呈现性能</span><span class="sxs-lookup"><span data-stu-id="e98f4-415">Analyze rendering performance with the Rendering tool</span></span>  

<span data-ttu-id="e98f4-416">使用呈现面板 **的功能** 帮助可视化页面的呈现性能。</span><span class="sxs-lookup"><span data-stu-id="e98f4-416">Use the features of the **Rendering** panel to help visualize the rendering performance of your page.</span></span>  

<span data-ttu-id="e98f4-417">若要打开 **呈现工具** ，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e98f4-417">To open the **Rendering** tool:</span></span>  

1.  <span data-ttu-id="e98f4-418">[打开命令菜单][DevToolsCommandMenu]。</span><span class="sxs-lookup"><span data-stu-id="e98f4-418">[Open the Command Menu][DevToolsCommandMenu].</span></span>  
1.  <span data-ttu-id="e98f4-419">开始键入并选择 `Rendering` `Show Rendering` 。</span><span class="sxs-lookup"><span data-stu-id="e98f4-419">Start typing `Rendering` and select `Show Rendering`.</span></span>  <span data-ttu-id="e98f4-420">DevTools **在** DevTools 窗口底部显示呈现工具。</span><span class="sxs-lookup"><span data-stu-id="e98f4-420">DevTools displays the **Rendering** tool at the bottom of your DevTools window.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-console-drawer-rendering.msft.png" alt-text="呈现工具" lightbox="../media/evaluate-performance-console-drawer-rendering.msft.png":::
       <span data-ttu-id="e98f4-422">呈现**工具**</span><span class="sxs-lookup"><span data-stu-id="e98f4-422">The **Rendering** tool</span></span>  
    :::image-end:::  
    
### <a name="view-frames-per-second-in-realtime-with-the-fps-meter"></a><span data-ttu-id="e98f4-423">使用 FPS 指示器实时查看每秒帧数</span><span class="sxs-lookup"><span data-stu-id="e98f4-423">View frames per second in realtime with the FPS meter</span></span>  

<span data-ttu-id="e98f4-424">**FPS 指示器**是显示在视口右上角的覆盖层。</span><span class="sxs-lookup"><span data-stu-id="e98f4-424">The **FPS meter** is an overlay that appears in the top-right corner of your viewport.</span></span>  <span data-ttu-id="e98f4-425">它在页面运行时提供 FPS 实时估计值。</span><span class="sxs-lookup"><span data-stu-id="e98f4-425">It provides a realtime estimate of FPS as the page runs.</span></span>  <span data-ttu-id="e98f4-426">打开 **FPS 指示器**：</span><span class="sxs-lookup"><span data-stu-id="e98f4-426">To open the **FPS meter**:</span></span>  

1.  <span data-ttu-id="e98f4-427">打开 **呈现** 工具。</span><span class="sxs-lookup"><span data-stu-id="e98f4-427">Open the **Rendering** tool.</span></span>  <span data-ttu-id="e98f4-428">[使用呈现工具分析呈现性能](#analyze-rendering-performance-with-the-rendering-tool)。</span><span class="sxs-lookup"><span data-stu-id="e98f4-428">[Analyze rendering performance with the Rendering tool](#analyze-rendering-performance-with-the-rendering-tool).</span></span>  
1.  <span data-ttu-id="e98f4-429">打开 **"FPS 指示器"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="e98f4-429">Turn on the **FPS Meter** checkbox.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-jank-console-rendering-frame-rate.msft.png" alt-text="FPS 计数" lightbox="../media/evaluate-performance-jank-console-rendering-frame-rate.msft.png":::
       <span data-ttu-id="e98f4-431">**FPS 计数**</span><span class="sxs-lookup"><span data-stu-id="e98f4-431">The **FPS meter**</span></span>  
    :::image-end:::  
    
### <a name="view-painting-events-in-realtime-with-paint-flashing"></a><span data-ttu-id="e98f4-432">使用"画图闪烁"实时查看绘制事件</span><span class="sxs-lookup"><span data-stu-id="e98f4-432">View painting events in realtime with Paint Flashing</span></span>  

<span data-ttu-id="e98f4-433">使用"画图闪烁"获取页面上所有绘制事件的真实视图。</span><span class="sxs-lookup"><span data-stu-id="e98f4-433">Use Paint Flashing to get a realtime view of all paint events on the page.</span></span>  <span data-ttu-id="e98f4-434">只要重新绘制页面的一部分，DevTools 就会用绿色概括该部分。</span><span class="sxs-lookup"><span data-stu-id="e98f4-434">Whenever a part of the page gets re-painted, DevTools outlines that section in green.</span></span>  

<span data-ttu-id="e98f4-435">若要打开"画图闪烁"，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="e98f4-435">To turn on Paint Flashing, complete the following actions.</span></span>  

1.  <span data-ttu-id="e98f4-436">打开 **呈现** 工具。</span><span class="sxs-lookup"><span data-stu-id="e98f4-436">Open the **Rendering** tool.</span></span>  <span data-ttu-id="e98f4-437">导航到 [使用呈现工具分析呈现性能](#analyze-rendering-performance-with-the-rendering-tool)。</span><span class="sxs-lookup"><span data-stu-id="e98f4-437">Navigate to [Analyze rendering performance with the Rendering tool](#analyze-rendering-performance-with-the-rendering-tool).</span></span>  
1.  <span data-ttu-id="e98f4-438">打开" **画图闪烁"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="e98f4-438">Turn on the **Paint Flashing** checkbox.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-jank-console-rendering-paint-flashing.msft.png" alt-text="画笔闪烁" lightbox="../media/evaluate-performance-jank-console-rendering-paint-flashing.msft.png":::
       **<span data-ttu-id="e98f4-440">画笔闪烁</span><span class="sxs-lookup"><span data-stu-id="e98f4-440">Paint Flashing</span></span>**  
    :::image-end:::  
    
### <a name="view-an-overlay-of-layers-with-layer-borders"></a><span data-ttu-id="e98f4-441">使用图层边框查看覆盖层</span><span class="sxs-lookup"><span data-stu-id="e98f4-441">View an overlay of layers with Layer Borders</span></span>  

<span data-ttu-id="e98f4-442">使用 **图层边框** 查看页面顶部的图层边框和磁贴的覆盖。</span><span class="sxs-lookup"><span data-stu-id="e98f4-442">Use **Layer Borders** to view an overlay of layer borders and tiles on top of the page.</span></span>  

<span data-ttu-id="e98f4-443">若要打开图层边框，请完成以下操作：</span><span class="sxs-lookup"><span data-stu-id="e98f4-443">To turn on Layer Borders, complete the following actions,</span></span>  

1.  <span data-ttu-id="e98f4-444">打开 **呈现** 工具。</span><span class="sxs-lookup"><span data-stu-id="e98f4-444">Open the **Rendering** tool.</span></span>  <span data-ttu-id="e98f4-445">导航到 [使用呈现工具分析呈现性能](#analyze-rendering-performance-with-the-rendering-tool)。</span><span class="sxs-lookup"><span data-stu-id="e98f4-445">Navigate to [Analyze rendering performance with the Rendering tool](#analyze-rendering-performance-with-the-rendering-tool).</span></span>  
1.  <span data-ttu-id="e98f4-446">打开" **图层边框"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="e98f4-446">Turn on the **Layer Borders** checkbox.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-devtools-console-rendering-layer-borders.msft.png" alt-text="图层边框" lightbox="../media/evaluate-performance-devtools-console-rendering-layer-borders.msft.png":::
       **<span data-ttu-id="e98f4-448">图层边框</span><span class="sxs-lookup"><span data-stu-id="e98f4-448">Layer Borders</span></span>**  
    :::image-end:::  
    
<span data-ttu-id="e98f4-449">导航到 [debug_colors.cc][ChromiumDebugColors] 中的注释，了解颜色编码的说明。</span><span class="sxs-lookup"><span data-stu-id="e98f4-449">Navigate to the comments in [debug_colors.cc][ChromiumDebugColors] for an explanation of the color-codings.</span></span>  

### <a name="find-scroll-performance-issues-in-realtime"></a><span data-ttu-id="e98f4-450">实时查找滚动性能问题</span><span class="sxs-lookup"><span data-stu-id="e98f4-450">Find scroll performance issues in realtime</span></span>  

<span data-ttu-id="e98f4-451">使用滚动性能问题可标识具有与滚动相关的事件侦听器的页面元素，这些元素可能会损害页面的性能。</span><span class="sxs-lookup"><span data-stu-id="e98f4-451">Use Scrolling Performance Issues to identify elements of the page that have event listeners related to scrolling that may harm the performance of the page.</span></span>  
<span data-ttu-id="e98f4-452">DevTools 以青色概述了可能存在问题的元素。</span><span class="sxs-lookup"><span data-stu-id="e98f4-452">DevTools outlines the potentially-problematic elements in teal.</span></span>  

<span data-ttu-id="e98f4-453">若要查看滚动性能问题，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="e98f4-453">To view scroll performance issues, complete the following actions.</span></span> 

1.  <span data-ttu-id="e98f4-454">打开 **呈现** 工具。</span><span class="sxs-lookup"><span data-stu-id="e98f4-454">Open the **Rendering** tool.</span></span>  <span data-ttu-id="e98f4-455">导航到 [使用呈现工具分析呈现性能](#analyze-rendering-performance-with-the-rendering-tool)。</span><span class="sxs-lookup"><span data-stu-id="e98f4-455">Navigate to [Analyze rendering performance with the Rendering tool](#analyze-rendering-performance-with-the-rendering-tool).</span></span>  
1.  <span data-ttu-id="e98f4-456">打开" **滚动性能问题"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="e98f4-456">Turn on the **Scrolling Performance Issues** checkbox.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-bing-console-drawer-rendering-scrolling-performance-issues.msft.png" alt-text="滚动性能问题指示不受层视口约束的对象可能会损害滚动性能" lightbox="../media/evaluate-performance-bing-console-drawer-rendering-scrolling-performance-issues.msft.png":::
       <span data-ttu-id="e98f4-458">**滚动性能问题** 指示不受层视口约束的对象可能会损害滚动性能</span><span class="sxs-lookup"><span data-stu-id="e98f4-458">**Scrolling Performance Issues** indicates that non-layer viewport-constrained objects may harm scroll performance</span></span>  
    :::image-end:::  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="e98f4-459">联系 Microsoft Edge 开发工具团队</span><span class="sxs-lookup"><span data-stu-id="e98f4-459">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageCaptureSettingsIcon]: ../media/capture-settings-icon.msft.png  
[ImageClearRecordingIcon]: ../media/clear-recording-icon.msft.png  
[ImageCollectGarbageIcon]: ../media/collect-garbage-icon.msft.png  
[ImageNextIcon]: ../media/next-icon.msft.png  
[ImagePanModeIcon]: ../media/pan-mode-icon.msft.png  
[ImagePreviousIcon]: ../media/previous-icon.msft.png  
[ImageRecordIcon]: ../media/record-icon.msft.png
[ImageRefreshPageIcon]: ../media/refresh-page-icon.msft.png  
[ImageResetTransformIcon]: ../media/reset-transform-icon.msft.png  
[ImageRotateModeIcon]: ../media/rotate-mode-icon.msft.png  
[ImageSearchCaseIcon]: ../media/search-case-icon.msft.png  
[ImageSearchRegexIcon]: ../media/search-regex-icon.msft.png  
[ImageShowHeaviestStackIcon]: ../media/show-heaviest-stack-icon.msft.png  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 开发人员工具|Microsoft Docs"  
[DevToolsCommandMenu]: ../command-menu/index.md#open-the-command-menu "打开命令菜单 - 使用 Microsoft Edge DevTools 命令菜单运行|Microsoft Docs"  
[DevtoolsEvaluatePerformanceGettingStarted]: ./index.md "开始分析运行时性能|Microsoft Docs"  

[ActivityTabsDemo]: https://microsoft-edge-chromium-devtools.glitch.me/perf/activitytabs.html "活动选项卡演示|小故障"  

[ChromiumDebugColors]: https://cs.chromium.org/chromium/src/cc/debug/debug_colors.cc "debug_colors.cc - 代码搜索"  

> [!NOTE]
> <span data-ttu-id="e98f4-465">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="e98f4-465">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="e98f4-466">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/reference)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="e98f4-466">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/reference) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="e98f4-468">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="e98f4-468">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
