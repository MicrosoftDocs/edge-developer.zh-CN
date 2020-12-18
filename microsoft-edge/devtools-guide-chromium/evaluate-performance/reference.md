---
description: 有关在 Microsoft Edge DevTools 中记录和分析性能的所有方法的参考。
title: 性能分析引用
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: d5b6be92c1419ba880a94c62c3f586a740816622
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11230759"
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

# <span data-ttu-id="1c47c-104">性能分析引用</span><span class="sxs-lookup"><span data-stu-id="1c47c-104">Performance analysis reference</span></span>  

<span data-ttu-id="1c47c-105">此页面全面引用了与分析性能相关的 Microsoft Edge DevTools 功能。</span><span class="sxs-lookup"><span data-stu-id="1c47c-105">This page is a comprehensive reference of Microsoft Edge DevTools features related to analyzing performance.</span></span>  

<span data-ttu-id="1c47c-106">导航到 ["开始分析][DevtoolsEvaluatePerformanceGettingStarted] 运行时性能"教程，了解如何使用 [Microsoft Edge DevTools][MicrosoftEdgeDevTools]分析页面的性能。</span><span class="sxs-lookup"><span data-stu-id="1c47c-106">Navigate to [Get Started With Analyzing Runtime Performance][DevtoolsEvaluatePerformanceGettingStarted] for a guided tutorial on how to analyze the performance of a page using [Microsoft Edge DevTools][MicrosoftEdgeDevTools].</span></span>  

## <span data-ttu-id="1c47c-107">记录性能</span><span class="sxs-lookup"><span data-stu-id="1c47c-107">Record performance</span></span>  

### <span data-ttu-id="1c47c-108">记录运行时性能</span><span class="sxs-lookup"><span data-stu-id="1c47c-108">Record runtime performance</span></span>  

<span data-ttu-id="1c47c-109">当你想要分析页面运行时的性能（而不是加载）时，记录运行时性能。</span><span class="sxs-lookup"><span data-stu-id="1c47c-109">Record runtime performance when you want to analyze the performance of a page as it is running, as opposed to loading.</span></span>  

1.  <span data-ttu-id="1c47c-110">转到要分析的页面。</span><span class="sxs-lookup"><span data-stu-id="1c47c-110">Go to the page that you want to analyze.</span></span>  
1.  <span data-ttu-id="1c47c-111">在\*\*\*\* DevTools 中选择"性能"选项卡。</span><span class="sxs-lookup"><span data-stu-id="1c47c-111">Choose the **Performance** tab in DevTools.</span></span>  
1.  <span data-ttu-id="1c47c-112">Choose **Record** \ (![ Record icon ][ImageRecordIcon] \) .</span><span class="sxs-lookup"><span data-stu-id="1c47c-112">Choose **Record** \(![Record icon][ImageRecordIcon]\).</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-performance-record-highlight.msft.png" alt-text="记录" lightbox="../media/evaluate-performance-performance-record-highlight.msft.png":::
       **<span data-ttu-id="1c47c-114">记录</span><span class="sxs-lookup"><span data-stu-id="1c47c-114">Record</span></span>**  
    :::image-end:::  
    
1.  <span data-ttu-id="1c47c-115">与页面交互。</span><span class="sxs-lookup"><span data-stu-id="1c47c-115">Interact with the page.</span></span>  <span data-ttu-id="1c47c-116">DevTools 记录交互后发生的所有页面活动。</span><span class="sxs-lookup"><span data-stu-id="1c47c-116">DevTools records all page activity that occurs as a result of your interactions.</span></span>  
1.  <span data-ttu-id="1c47c-117">再次 **选择** "录制"或" **停止** "以停止录制。</span><span class="sxs-lookup"><span data-stu-id="1c47c-117">Choose **Record** again or choose **Stop** to stop recording.</span></span>  
    
### <span data-ttu-id="1c47c-118">记录加载性能</span><span class="sxs-lookup"><span data-stu-id="1c47c-118">Record load performance</span></span>  

<span data-ttu-id="1c47c-119">当你想要在页面加载时（而不是运行）分析其性能时，记录加载性能。</span><span class="sxs-lookup"><span data-stu-id="1c47c-119">Record load performance when you want to analyze the performance of a page as it is loading, as opposed to running.</span></span>  

1.  <span data-ttu-id="1c47c-120">转到要分析的页面。</span><span class="sxs-lookup"><span data-stu-id="1c47c-120">Go to the page that you want to analyze.</span></span>  
1.  <span data-ttu-id="1c47c-121">打开 **DevTools** 的性能面板。</span><span class="sxs-lookup"><span data-stu-id="1c47c-121">Open the **Performance** panel of DevTools.</span></span>  
1.  <span data-ttu-id="1c47c-122">Choose **Refresh page** \ (Refresh Page ![ ][ImageRefreshPageIcon] \) .</span><span class="sxs-lookup"><span data-stu-id="1c47c-122">Choose **Refresh page** \(![Refresh Page][ImageRefreshPageIcon]\).</span></span>  <span data-ttu-id="1c47c-123">DevTools 在页面刷新时记录性能指标，然后在加载完成后的几秒钟内自动停止录制。</span><span class="sxs-lookup"><span data-stu-id="1c47c-123">DevTools records performance metrics while the page refreshes and then automatically stops the recording a couple seconds after the load finishes.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-performance-refresh-button.msft.png" alt-text="刷新页面" lightbox="../media/evaluate-performance-performance-refresh-button.msft.png":::
       **<span data-ttu-id="1c47c-125">刷新页面</span><span class="sxs-lookup"><span data-stu-id="1c47c-125">Refresh page</span></span>**  
    :::image-end:::  
    
<span data-ttu-id="1c47c-126">DevTools 自动放大大部分活动发生的记录部分。</span><span class="sxs-lookup"><span data-stu-id="1c47c-126">DevTools automatically zooms in on the portion of the recording where most of the activity occurred.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-refreshed.msft.png" alt-text="页面加载录制" lightbox="../media/evaluate-performance-performance-refreshed.msft.png":::
   <span data-ttu-id="1c47c-128">页面加载录制</span><span class="sxs-lookup"><span data-stu-id="1c47c-128">A page-load recording</span></span>  
:::image-end:::  

### <span data-ttu-id="1c47c-129">录制时捕获屏幕截图</span><span class="sxs-lookup"><span data-stu-id="1c47c-129">Capture screenshots while recording</span></span>  

<span data-ttu-id="1c47c-130">打开" **屏幕截图"** 复选框，在录制时捕获每个帧的屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="1c47c-130">Turn on the **Screenshots** checkbox to capture a screenshot of every frame while recording.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-capture-screenshots-checkbox.msft.png" alt-text=""屏幕截图"复选框" lightbox="../media/evaluate-performance-performance-capture-screenshots-checkbox.msft.png":::
   <span data-ttu-id="1c47c-132">" **屏幕截图"** 复选框</span><span class="sxs-lookup"><span data-stu-id="1c47c-132">The **Screenshots** checkbox</span></span>  
:::image-end:::  

<span data-ttu-id="1c47c-133">导航 [到"查看屏幕截图](#view-a-screenshot) "，了解如何与屏幕截图进行交互。</span><span class="sxs-lookup"><span data-stu-id="1c47c-133">Navigate to [View a screenshot](#view-a-screenshot) to learn how to interact with screenshots.</span></span>  

### <span data-ttu-id="1c47c-134">录制时强制进行垃圾回收</span><span class="sxs-lookup"><span data-stu-id="1c47c-134">Force garbage collection while recording</span></span>  

<span data-ttu-id="1c47c-135">在录制页面时，选择"收集\*\*\*\* 垃圾"\ (![ 收集垃圾图标 ][ImageCollectGarbageIcon] \) 强制进行垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="1c47c-135">While you are recording a page, choose **Collect garbage** \(![Collect garbage icon][ImageCollectGarbageIcon]\) to force garbage collection.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-collect-garbage-button.msft.png" alt-text="收集垃圾" lightbox="../media/evaluate-performance-performance-collect-garbage-button.msft.png":::
   <span data-ttu-id="1c47c-137">收集垃圾</span><span class="sxs-lookup"><span data-stu-id="1c47c-137">Collect garbage</span></span>  
:::image-end:::  

### <span data-ttu-id="1c47c-138">显示录制设置</span><span class="sxs-lookup"><span data-stu-id="1c47c-138">Show recording settings</span></span>  

<span data-ttu-id="1c47c-139">Choose **Capture settings** \ (Capture settings ![ ][ImageCaptureSettingsIcon] \) to expose more settings related to how DevTools captures performance recordings.</span><span class="sxs-lookup"><span data-stu-id="1c47c-139">Choose **Capture settings** \(![Capture settings][ImageCaptureSettingsIcon]\) to expose more settings related to how DevTools captures performance recordings.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-capture-settings-button-open-drawer.msft.png" alt-text=""捕获设置"部分" lightbox="../media/evaluate-performance-performance-capture-settings-button-open-drawer.msft.png":::
   <span data-ttu-id="1c47c-141">" **捕获设置"** 部分</span><span class="sxs-lookup"><span data-stu-id="1c47c-141">The **Capture Settings** section</span></span>  
:::image-end:::  

### <span data-ttu-id="1c47c-142">禁用 JavaScript 示例</span><span class="sxs-lookup"><span data-stu-id="1c47c-142">Disable JavaScript samples</span></span>  

<span data-ttu-id="1c47c-143">默认情况下，录制 **的 Main** 部分显示录制期间调用的 JavaScript 函数的详细调用堆栈。</span><span class="sxs-lookup"><span data-stu-id="1c47c-143">By default, the **Main** section of a recording displays detailed call stacks of JavaScript functions that were called during the recording.</span></span>  <span data-ttu-id="1c47c-144">若要禁用这些调用堆栈，</span><span class="sxs-lookup"><span data-stu-id="1c47c-144">To disable these call stacks:</span></span>  

1.  <span data-ttu-id="1c47c-145">打开 **"捕获设置"** 菜单。</span><span class="sxs-lookup"><span data-stu-id="1c47c-145">Open the **Capture settings** menu.</span></span>  <span data-ttu-id="1c47c-146">导航到["显示录制设置"。](#show-recording-settings)</span><span class="sxs-lookup"><span data-stu-id="1c47c-146">Navigate to [Show recording settings](#show-recording-settings).</span></span>  
1.  <span data-ttu-id="1c47c-147">打开" **禁用 JavaScript 示例"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="1c47c-147">Turn on the **Disable JavaScript Samples** checkbox.</span></span>  
1.  <span data-ttu-id="1c47c-148">录制页面。</span><span class="sxs-lookup"><span data-stu-id="1c47c-148">Take a recording of the page.</span></span>  
    
<span data-ttu-id="1c47c-149">以下 2 个图显示禁用和启用 JavaScript 示例的区别。</span><span class="sxs-lookup"><span data-stu-id="1c47c-149">The following 2 figures display the difference between disabling and enabling JavaScript samples.</span></span>  <span data-ttu-id="1c47c-150">禁用 **采样** 时，录制的主节要短得多，因为它将省略所有 JavaScript 调用堆栈。</span><span class="sxs-lookup"><span data-stu-id="1c47c-150">The **Main** section of the recording is much shorter when sampling is disabled, because it omits all of the JavaScript call stacks.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-on.msft.png" alt-text="禁用 JS 示例时录制的示例" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-on.msft.png":::
         <span data-ttu-id="1c47c-152">禁用 JS 示例时录制的示例</span><span class="sxs-lookup"><span data-stu-id="1c47c-152">An example of a recording when JS samples are disabled</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off.msft.png" alt-text="JS 示例打开时录制的示例" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off.msft.png":::
         <span data-ttu-id="1c47c-154">JS 示例打开时录制的示例</span><span class="sxs-lookup"><span data-stu-id="1c47c-154">An example of a recording when JS samples are turned on</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::

### <span data-ttu-id="1c47c-155">录制时限制网络</span><span class="sxs-lookup"><span data-stu-id="1c47c-155">Throttle the network while recording</span></span>  

<span data-ttu-id="1c47c-156">在录制时限制网络：</span><span class="sxs-lookup"><span data-stu-id="1c47c-156">To throttle the network while recording:</span></span>  

1.  <span data-ttu-id="1c47c-157">打开 **"捕获设置"** 菜单。</span><span class="sxs-lookup"><span data-stu-id="1c47c-157">Open the **Capture settings** menu.</span></span>  <span data-ttu-id="1c47c-158">导航到["显示录制设置"。](#show-recording-settings)</span><span class="sxs-lookup"><span data-stu-id="1c47c-158">Navigate to [Show recording settings](#show-recording-settings).</span></span>  
1.  <span data-ttu-id="1c47c-159">将 **网络** 设置为所需的限制级别。</span><span class="sxs-lookup"><span data-stu-id="1c47c-159">Set **Network** to the desired level of throttling.</span></span>  
    
### <span data-ttu-id="1c47c-160">在录制时限制 CPU</span><span class="sxs-lookup"><span data-stu-id="1c47c-160">Throttle the CPU while recording</span></span>  

<span data-ttu-id="1c47c-161">在录制时限制 CPU：</span><span class="sxs-lookup"><span data-stu-id="1c47c-161">To throttle the CPU while recording:</span></span>  

1.  <span data-ttu-id="1c47c-162">打开 **"捕获设置"** 菜单。</span><span class="sxs-lookup"><span data-stu-id="1c47c-162">Open the **Capture settings** menu.</span></span>  <span data-ttu-id="1c47c-163">导航到["显示录制设置"。](#show-recording-settings)</span><span class="sxs-lookup"><span data-stu-id="1c47c-163">Navigate to [Show recording settings](#show-recording-settings).</span></span>  
1.  <span data-ttu-id="1c47c-164">将 **CPU** 设置为所需的限制级别。</span><span class="sxs-lookup"><span data-stu-id="1c47c-164">Set **CPU** to the desired level of throttling.</span></span>  
    
<span data-ttu-id="1c47c-165">限制与计算机的功能相关。</span><span class="sxs-lookup"><span data-stu-id="1c47c-165">Throttling is relative to the capabilities of your computer.</span></span>  <span data-ttu-id="1c47c-166">例如 **，2 倍速度较慢** 选项使 CPU 的运行速度比正常速度慢 2 倍。</span><span class="sxs-lookup"><span data-stu-id="1c47c-166">For example, the **2x slowdown** option makes your CPU operate 2 times slower than normal.</span></span>  <span data-ttu-id="1c47c-167">DevTools 不会真正模拟移动设备的 CPU，因为移动设备的体系结构与台式机和笔记本电脑的体系结构大为不同。</span><span class="sxs-lookup"><span data-stu-id="1c47c-167">DevTools do not truly simulate the CPUs of mobile devices, because the architecture of mobile devices is very different from that of desktops and laptops.</span></span>  

### <span data-ttu-id="1c47c-168">打开高级画图检测</span><span class="sxs-lookup"><span data-stu-id="1c47c-168">Turn on advanced paint instrumentation</span></span>  

<span data-ttu-id="1c47c-169">若要查看详细的绘制检测，请：</span><span class="sxs-lookup"><span data-stu-id="1c47c-169">To view detailed paint instrumentation:</span></span>  

1.  <span data-ttu-id="1c47c-170">打开 **"捕获设置"** 菜单。</span><span class="sxs-lookup"><span data-stu-id="1c47c-170">Open the **Capture settings** menu.</span></span>  <span data-ttu-id="1c47c-171">导航到["显示录制设置"。](#show-recording-settings)</span><span class="sxs-lookup"><span data-stu-id="1c47c-171">Navigate to [Show recording settings](#show-recording-settings).</span></span>  
1.  <span data-ttu-id="1c47c-172">选中" \*\*启用高级绘制检测 (慢速) \*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="1c47c-172">Check the **Enable advanced paint instrumentation (slow)** checkbox.</span></span>  

<span data-ttu-id="1c47c-173">若要了解如何与绘制信息进行交互，请导航到"[查看图层"和](#view-layers-information)"[查看绘制配置文件器"。](#view-paint-profiler)</span><span class="sxs-lookup"><span data-stu-id="1c47c-173">To learn how to interact with the paint information, navigate to [View layers](#view-layers-information) and [View paint profiler](#view-paint-profiler).</span></span>  

## <span data-ttu-id="1c47c-174">保存录制</span><span class="sxs-lookup"><span data-stu-id="1c47c-174">Save a recording</span></span>  

<span data-ttu-id="1c47c-175">若要保存录制，请打开上下文菜单 \ (右键单击\) ，然后选择"保存**配置文件"。**</span><span class="sxs-lookup"><span data-stu-id="1c47c-175">To save a recording, open the contextual menu \(right-click\), and choose **Save Profile**.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-save-profile.msft.png" alt-text="保存配置文件" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-save-profile.msft.png":::
   **<span data-ttu-id="1c47c-177">保存配置文件</span><span class="sxs-lookup"><span data-stu-id="1c47c-177">Save Profile</span></span>**  
:::image-end:::  

## <span data-ttu-id="1c47c-178">加载录制</span><span class="sxs-lookup"><span data-stu-id="1c47c-178">Load a recording</span></span>  

<span data-ttu-id="1c47c-179">若要加载录制，请打开上下文菜单 \ (右键单击\) ，然后选择"加载**配置文件"。**</span><span class="sxs-lookup"><span data-stu-id="1c47c-179">To load a recording, open the contextual menu \(right-click\), and choose **Load Profile**.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-load-profile.msft.png" alt-text="加载配置文件" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-load-profile.msft.png":::
   **<span data-ttu-id="1c47c-181">加载配置文件</span><span class="sxs-lookup"><span data-stu-id="1c47c-181">Load Profile</span></span>**  
:::image-end:::  

## <span data-ttu-id="1c47c-182">清除以前的录制</span><span class="sxs-lookup"><span data-stu-id="1c47c-182">Clear the previous recording</span></span>  

<span data-ttu-id="1c47c-183">录制后，按 **"** 清除录制"\ ("清除录制"图标 \) 以从"性能"面板 ![ ][ImageClearRecordingIcon] 中清除该\*\*\*\* 录制。</span><span class="sxs-lookup"><span data-stu-id="1c47c-183">After making a recording, press **Clear recording** \(![Clear recording icon][ImageClearRecordingIcon]\) to clear that recording from the **Performance** panel.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-clear-button.msft.png" alt-text="清除录制" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-clear-button.msft.png":::
   **<span data-ttu-id="1c47c-185">清除录制</span><span class="sxs-lookup"><span data-stu-id="1c47c-185">Clear recording</span></span>**  
:::image-end:::  

## <span data-ttu-id="1c47c-186">分析性能记录</span><span class="sxs-lookup"><span data-stu-id="1c47c-186">Analyze a performance recording</span></span>  

<span data-ttu-id="1c47c-187">记录[运行时性能或](#record-runtime-performance)[记录加载性能](#record-load-performance)后，性能面板\*\*\*\* 会提供大量数据，用于分析刚刚发生的情况的性能。</span><span class="sxs-lookup"><span data-stu-id="1c47c-187">After you [record runtime performance](#record-runtime-performance) or [record load performance](#record-load-performance), the **Performance** panel provides a lot of data for analyzing the performance of what just happened.</span></span>  

### <span data-ttu-id="1c47c-188">选择录音的一部分</span><span class="sxs-lookup"><span data-stu-id="1c47c-188">Select a portion of a recording</span></span>  

<span data-ttu-id="1c47c-189">将鼠标向左或向右拖动到 **"概述** "中，选择录制的一部分。</span><span class="sxs-lookup"><span data-stu-id="1c47c-189">Drag your mouse left or right across the **Overview** to select a portion of a recording.</span></span>  <span data-ttu-id="1c47c-190">概述**是**包含**FPS、CPU**和\*\*\*\*\*\*NET\*\*图表的部分。</span><span class="sxs-lookup"><span data-stu-id="1c47c-190">The **Overview** is the section that contains the **FPS**, **CPU**, and **NET** charts.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-zoom-highlighted.msft.png" alt-text="将鼠标拖动到"概述"中以缩放" lightbox="../media/evaluate-performance-performance-zoom-highlighted.msft.png":::
   <span data-ttu-id="1c47c-192">将鼠标拖动到 **"概述"中** 以缩放</span><span class="sxs-lookup"><span data-stu-id="1c47c-192">Drag the mouse across the **Overview** to zoom</span></span>  
:::image-end:::  

<span data-ttu-id="1c47c-193">若要使用键盘选择部分，</span><span class="sxs-lookup"><span data-stu-id="1c47c-193">To select a portion using the keyboard:</span></span>  

1.  <span data-ttu-id="1c47c-194">选择**主节或**它旁边的任何部分的背景，如**交互、\*\*\*\*网络**或**GPU。**</span><span class="sxs-lookup"><span data-stu-id="1c47c-194">Choose the background of the **Main** section, or any of the sections next to it, such as **Interactions**, **Network**, or **GPU**.</span></span>  <span data-ttu-id="1c47c-195">此键盘工作流仅在这些部分之一位于焦点时有效。</span><span class="sxs-lookup"><span data-stu-id="1c47c-195">This keyboard workflow only works when one of these sections is in focus.</span></span>  
1.  <span data-ttu-id="1c47c-196">分别使用 `W` `A` 、 、 `S` `D` 键进行放大、向左移动、缩小和向右移动。</span><span class="sxs-lookup"><span data-stu-id="1c47c-196">Use the `W`, `A`, `S`, `D` keys to zoom in, move left, zoom out, and move right, respectively.</span></span>  

<span data-ttu-id="1c47c-197">若要使用触控板选择部分，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="1c47c-197">To select a portion using a trackpad, complete the following actions.</span></span>  

1.  <span data-ttu-id="1c47c-198">将鼠标悬停在 **"概述"** 部分或" **详细信息"部分** 上。</span><span class="sxs-lookup"><span data-stu-id="1c47c-198">Hover your mouse over the **Overview** section or the **Details** section.</span></span>  <span data-ttu-id="1c47c-199">"**概述**"部分包含**FPS、CPU**和\*\*\*\* **NET**图表。</span><span class="sxs-lookup"><span data-stu-id="1c47c-199">The **Overview** section is the area containing the **FPS**, **CPU**, and **NET** charts.</span></span>  <span data-ttu-id="1c47c-200">"**详细信息**"部分是包含"主"\*\*\*\* 部分、"交互 **"** 部分等的区域。</span><span class="sxs-lookup"><span data-stu-id="1c47c-200">The **Details** section is the area containing the **Main** section, the **Interactions** section, and so on.</span></span>  
1.  <span data-ttu-id="1c47c-201">使用两个手指向上轻扫以缩小，向左轻扫向左移动，向下轻扫可放大，向右轻扫向右移动。</span><span class="sxs-lookup"><span data-stu-id="1c47c-201">Using two fingers, swipe up to zoom out, swipe left to move left, swipe down to zoom in, and swipe right to move right.</span></span>  

<span data-ttu-id="1c47c-202">若要在主节或任何选项中滚动\*\*\*\* 长图表，请选择并按住，同时向上和向下拖动。</span><span class="sxs-lookup"><span data-stu-id="1c47c-202">To scroll a long flame chart in the **Main** section or any of the neighbors, choose and hold while dragging up and down.</span></span>  <span data-ttu-id="1c47c-203">向左和向右拖动以移动所选录音的哪一部分。</span><span class="sxs-lookup"><span data-stu-id="1c47c-203">Drag left and right to move what portion of the recording is chosen.</span></span>  

### <span data-ttu-id="1c47c-204">搜索活动</span><span class="sxs-lookup"><span data-stu-id="1c47c-204">Search activities</span></span>  

<span data-ttu-id="1c47c-205">选择 `Control` + `F` \ (Windows、Linux\) 或 `Command` + `F` \ (macOS\) \*\*\*\* 以打开性能面板底部的搜索框。</span><span class="sxs-lookup"><span data-stu-id="1c47c-205">Select `Control`+`F` \(Windows, Linux\) or `Command`+`F` \(macOS\) to open the search box at the bottom of the **Performance** panel.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-search-regex.msft.png" alt-text="搜索框" lightbox="../media/evaluate-performance-performance-search-regex.msft.png":::
   <span data-ttu-id="1c47c-207">搜索框</span><span class="sxs-lookup"><span data-stu-id="1c47c-207">The search box</span></span>  
:::image-end:::  

<span data-ttu-id="1c47c-208">导航与查询匹配的活动：</span><span class="sxs-lookup"><span data-stu-id="1c47c-208">To navigate activities that match your query:</span></span>  

*   <span data-ttu-id="1c47c-209">使用上 **一** 个 \ (![ ][ImagePreviousIcon] \) **和 Next** \ (![ Next ][ImageNextIcon] \) 按钮。</span><span class="sxs-lookup"><span data-stu-id="1c47c-209">Use the **Previous** \(![Previous][ImagePreviousIcon]\) and **Next** \(![Next][ImageNextIcon]\) buttons.</span></span>  
*   <span data-ttu-id="1c47c-210">选择 `Shift` + `Enter` 以选择上一个或 `Enter` 选择下一个。</span><span class="sxs-lookup"><span data-stu-id="1c47c-210">Select `Shift`+`Enter` to select the previous or `Enter` to select the next.</span></span>  

<span data-ttu-id="1c47c-211">修改查询设置：</span><span class="sxs-lookup"><span data-stu-id="1c47c-211">To modify query settings:</span></span>  

*   <span data-ttu-id="1c47c-212">按 **区分大小写** \ (![ 区分大小写 ][ImageSearchCaseIcon] \) 使查询区分大小写。</span><span class="sxs-lookup"><span data-stu-id="1c47c-212">Press **Case sensitive** \(![Case sensitive][ImageSearchCaseIcon]\) to make the query case sensitive.</span></span>  
*   <span data-ttu-id="1c47c-213">按 **Regex** \ (![ Regex ][ImageSearchRegexIcon] \) 在查询中使用正则表达式。</span><span class="sxs-lookup"><span data-stu-id="1c47c-213">Press **Regex** \(![Regex][ImageSearchRegexIcon]\) to use a regular expression in your query.</span></span>  

<span data-ttu-id="1c47c-214">若要隐藏搜索框，请按 **Cancel**。</span><span class="sxs-lookup"><span data-stu-id="1c47c-214">To hide the search box, press **Cancel**.</span></span>  

### <span data-ttu-id="1c47c-215">查看主线程活动</span><span class="sxs-lookup"><span data-stu-id="1c47c-215">View main thread activity</span></span>  

<span data-ttu-id="1c47c-216">使用 **"主** "部分查看页面主线程上发生的活动。</span><span class="sxs-lookup"><span data-stu-id="1c47c-216">Use the **Main** section to view activity that occurred on the main thread of the page.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-main-zoomed.msft.png" alt-text="主要部分" lightbox="../media/evaluate-performance-performance-main-zoomed.msft.png":::
   <span data-ttu-id="1c47c-218">" **主** "部分</span><span class="sxs-lookup"><span data-stu-id="1c47c-218">The **Main** section</span></span>  
:::image-end:::  

<span data-ttu-id="1c47c-219">选择事件以在"摘要"选项卡中查看 **有关它** 的信息。 DevTools 概述了选定的事件。</span><span class="sxs-lookup"><span data-stu-id="1c47c-219">Choose an event to view more information about it in the **Summary** tab.  DevTools outlines the selected event.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-summary-me.msft.png" alt-text="有关"摘要"选项卡中的匿名函数详细信息" lightbox="../media/evaluate-performance-performance-summary-me.msft.png":::
   <span data-ttu-id="1c47c-221">有关"摘要 `anonymous` "选项卡中函数\*\*\*\* 详细信息</span><span class="sxs-lookup"><span data-stu-id="1c47c-221">More information about the `anonymous` function in the **Summary** tab</span></span>  
:::image-end:::  

<span data-ttu-id="1c47c-222">DevTools 表示包含图表的主线程活动。</span><span class="sxs-lookup"><span data-stu-id="1c47c-222">DevTools represents main thread activity with a flame chart.</span></span>  <span data-ttu-id="1c47c-223">x 轴表示一段时间的录制。</span><span class="sxs-lookup"><span data-stu-id="1c47c-223">The x-axis represents the recording over time.</span></span>  <span data-ttu-id="1c47c-224">Y 轴表示调用堆叠。</span><span class="sxs-lookup"><span data-stu-id="1c47c-224">The y-axis represents the call stack.</span></span>  <span data-ttu-id="1c47c-225">顶部的事件会导致其下方的事件。</span><span class="sxs-lookup"><span data-stu-id="1c47c-225">The events on top cause the events below it.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-main-flame-chart.msft.png" alt-text="绘制图表" lightbox="../media/evaluate-performance-performance-main-flame-chart.msft.png":::
   <span data-ttu-id="1c47c-227">绘制图表</span><span class="sxs-lookup"><span data-stu-id="1c47c-227">A flame chart</span></span>  
:::image-end:::  

<span data-ttu-id="1c47c-228">在上图中， `click` 一个事件导致第 `Function Call` `activitytabs.js` 53 行中发生。</span><span class="sxs-lookup"><span data-stu-id="1c47c-228">In the previous figure, a `click` event caused a `Function Call` in `activitytabs.js` on line 53.</span></span>  <span data-ttu-id="1c47c-229">在下面 `Function Call` ，查看匿名函数已运行。</span><span class="sxs-lookup"><span data-stu-id="1c47c-229">Below `Function Call`, review that an anonymous function was run.</span></span>  <span data-ttu-id="1c47c-230">请求的匿名函数 `a` ，请求的 `wait` ，请求的 `Minor GC` 。</span><span class="sxs-lookup"><span data-stu-id="1c47c-230">The anonymous function requested `a`, which requested `wait`, which requested `Minor GC`.</span></span>  

<span data-ttu-id="1c47c-231">DevTools 为脚本分配随机颜色。</span><span class="sxs-lookup"><span data-stu-id="1c47c-231">DevTools assigns scripts random colors.</span></span>  <span data-ttu-id="1c47c-232">在上图中，来自一个脚本的函数请求的颜色为浅绿色。</span><span class="sxs-lookup"><span data-stu-id="1c47c-232">In the previous figure, function requests from one script are colored light green.</span></span>  <span data-ttu-id="1c47c-233">来自另一个脚本的请求是彩色的。</span><span class="sxs-lookup"><span data-stu-id="1c47c-233">Requests from another script are colored beige.</span></span>  <span data-ttu-id="1c47c-234">深黄色表示脚本活动，紫色事件表示呈现活动。</span><span class="sxs-lookup"><span data-stu-id="1c47c-234">The darker yellow represents scripting activity, and the purple event represents rendering activity.</span></span>  <span data-ttu-id="1c47c-235">这些较深的黄色和紫色事件在所有录制中都是一致的。</span><span class="sxs-lookup"><span data-stu-id="1c47c-235">These darker yellow and purple events are consistent across all recordings.</span></span>  

<span data-ttu-id="1c47c-236">如果要隐藏 [JavaScript](#disable-javascript-samples) 请求的详细绘制图表，请导航到"禁用 JavaScript 示例"。</span><span class="sxs-lookup"><span data-stu-id="1c47c-236">Navigate to [Disable JavaScript samples](#disable-javascript-samples) if you want to hide the detailed flame chart of JavaScript requests.</span></span>  <span data-ttu-id="1c47c-237">禁用 JS 示例后，只显示上图等高级 `Event: click` `Function Call` `str` 事件。</span><span class="sxs-lookup"><span data-stu-id="1c47c-237">When JS samples are disabled, only high-level events such as `Event: click` and `Function Call` from the previous figure `str` displayed.</span></span>  

### <span data-ttu-id="1c47c-238">查看表中的活动</span><span class="sxs-lookup"><span data-stu-id="1c47c-238">View activities in a table</span></span>  

<span data-ttu-id="1c47c-239">录制页面后，无需仅依赖"主 **"部分来** 分析活动。</span><span class="sxs-lookup"><span data-stu-id="1c47c-239">After recording a page, you do not need to rely solely on the **Main** section to analyze activities.</span></span>  <span data-ttu-id="1c47c-240">DevTools 还提供了三种表格式视图，用于分析活动。</span><span class="sxs-lookup"><span data-stu-id="1c47c-240">DevTools also provides three tabular views for analyzing activities.</span></span>  <span data-ttu-id="1c47c-241">每个视图都提供对活动的不同视角：</span><span class="sxs-lookup"><span data-stu-id="1c47c-241">Each view gives you a different perspective on the activities:</span></span>  

*   <span data-ttu-id="1c47c-242">当要查看导致工作最多的根活动时，请使用"呼叫树 ["选项卡](#the-call-tree-tab)。</span><span class="sxs-lookup"><span data-stu-id="1c47c-242">When you want to view the root activities that cause the most work, use [the Call Tree tab](#the-call-tree-tab).</span></span>  
*   <span data-ttu-id="1c47c-243">当要查看直接花费最多时间的活动时，请使用"Bottom-Up [选项卡](#the-bottom-up-tab)。</span><span class="sxs-lookup"><span data-stu-id="1c47c-243">When you want to view the activities where the most time was directly spent, use [the Bottom-Up tab](#the-bottom-up-tab).</span></span>  
*   <span data-ttu-id="1c47c-244">当你想要按记录期间活动发生的顺序查看活动时，请使用"事件日志" [选项卡](#the-event-log-tab)。</span><span class="sxs-lookup"><span data-stu-id="1c47c-244">When you want to view the activities in the order in which they occurred during the recording, use [the Event Log tab](#the-event-log-tab).</span></span>  
    
> [!NOTE]
> <span data-ttu-id="1c47c-245">接下来的三个部分均引用同一演示。</span><span class="sxs-lookup"><span data-stu-id="1c47c-245">The next three sections all refer to the same demo.</span></span>  <span data-ttu-id="1c47c-246">在活动选项卡演示 [中自己运行演示][ActivityTabsDemo]。</span><span class="sxs-lookup"><span data-stu-id="1c47c-246">Run the demo yourself at [Activity Tabs Demo][ActivityTabsDemo].</span></span>  

#### <span data-ttu-id="1c47c-247">根活动</span><span class="sxs-lookup"><span data-stu-id="1c47c-247">Root activities</span></span>  

<span data-ttu-id="1c47c-248">下面是"呼叫树"选项卡\*\*\*\*、"底部向上"选项卡和"\*\*\*\* 事件日志"部分\*\*\*\* 中提到的根活动**概念的说明**。</span><span class="sxs-lookup"><span data-stu-id="1c47c-248">Here is an explanation of the **root activities** concept that is mentioned in the **Call Tree** tab, **Bottom-Up** tab, and **Event Log** sections.</span></span>  

<span data-ttu-id="1c47c-249">根活动是导致浏览器执行某些工作的活动。</span><span class="sxs-lookup"><span data-stu-id="1c47c-249">Root activities are those which cause the browser to do some work.</span></span>  <span data-ttu-id="1c47c-250">例如，当您选择网页时，浏览器将运行 `Event` 活动作为根活动。</span><span class="sxs-lookup"><span data-stu-id="1c47c-250">For example, when you choose a webpage, the browser runs an `Event` activity as the root activity.</span></span>  <span data-ttu-id="1c47c-251">`Event`这可能会导致处理程序运行，等等。</span><span class="sxs-lookup"><span data-stu-id="1c47c-251">That `Event` may cause a handler to run, and so on.</span></span>  

<span data-ttu-id="1c47c-252">在主节的绘制 **图中** ，根活动位于图表的顶部。</span><span class="sxs-lookup"><span data-stu-id="1c47c-252">In the flame chart of the **Main** section, root activities are at the top of the chart.</span></span>  <span data-ttu-id="1c47c-253">在" **呼叫树** "和" **事件日志** "选项卡中，根活动是顶级项目。</span><span class="sxs-lookup"><span data-stu-id="1c47c-253">In the **Call Tree** and **Event Log** tabs, root activities are the top-level items.</span></span>  

<span data-ttu-id="1c47c-254">导航到 ["呼叫树"选项卡](#the-call-tree-tab) ，查看根活动的示例。</span><span class="sxs-lookup"><span data-stu-id="1c47c-254">Navigate to [The Call Tree tab](#the-call-tree-tab) for an example of root activities.</span></span>  

#### <span data-ttu-id="1c47c-255">"呼叫树"选项卡</span><span class="sxs-lookup"><span data-stu-id="1c47c-255">The Call Tree tab</span></span>  

<span data-ttu-id="1c47c-256">使用 **"呼叫树** "选项卡可查看 [哪些根活动](#root-activities) 导致工作最多。</span><span class="sxs-lookup"><span data-stu-id="1c47c-256">Use the **Call Tree** tab to view which [root activities](#root-activities) cause the most work.</span></span>  

<span data-ttu-id="1c47c-257">" **呼叫树** "选项卡仅显示在录制的选定部分期间的活动。</span><span class="sxs-lookup"><span data-stu-id="1c47c-257">The **Call Tree** tab only displays activities during the selected portion of the recording.</span></span>  <span data-ttu-id="1c47c-258">导航 [到"选择录音的一部分](#select-a-portion-of-a-recording) "，了解如何选择部分。</span><span class="sxs-lookup"><span data-stu-id="1c47c-258">Navigate to [Select a portion of a recording](#select-a-portion-of-a-recording) to learn how to select portions.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-call-tree.msft.png" alt-text=""呼叫树"选项卡" lightbox="../media/evaluate-performance-performance-call-tree.msft.png":::
   <span data-ttu-id="1c47c-260">" **呼叫树"** 选项卡</span><span class="sxs-lookup"><span data-stu-id="1c47c-260">The **Call Tree** tab</span></span>  
:::image-end:::  

<span data-ttu-id="1c47c-261">在上图中，活动列中的顶级项目（如\*\*\*\* `Evaluate Script` 根 `Parse HTML` 活动）。</span><span class="sxs-lookup"><span data-stu-id="1c47c-261">In the previous figure, the top-level of items in the **Activity** column, such as `Evaluate Script` and `Parse HTML` are root activities.</span></span>  <span data-ttu-id="1c47c-262">嵌套表示调用堆栈。</span><span class="sxs-lookup"><span data-stu-id="1c47c-262">The nesting represents the call stack.</span></span>  <span data-ttu-id="1c47c-263">例如，在上图中 `Parse HTML` ，导致和 `Evaluate Script` `Compile Script` `(anonymous)` 。</span><span class="sxs-lookup"><span data-stu-id="1c47c-263">For example, in the previous figure, `Parse HTML` which caused `Evaluate Script` which caused `Compile Script` and `(anonymous)`.</span></span>  

<span data-ttu-id="1c47c-264">**"自** 用时间"表示直接在活动中花费的时间。</span><span class="sxs-lookup"><span data-stu-id="1c47c-264">**Self Time** represents the time directly spent in that activity.</span></span>  <span data-ttu-id="1c47c-265">**"总** 时间"表示该活动或任何子活动所花费的时间。</span><span class="sxs-lookup"><span data-stu-id="1c47c-265">**Total Time** represents the time spent in that activity or any of the children.</span></span>  

<span data-ttu-id="1c47c-266">选择 **"自时间**"、" **总**时间 **"或"活动** "按该列对表进行排序。</span><span class="sxs-lookup"><span data-stu-id="1c47c-266">Choose **Self Time**, **Total Time**, or **Activity** to sort the table by that column.</span></span>  

<span data-ttu-id="1c47c-267">使用 **"** 筛选器"文本框按活动名称筛选事件。</span><span class="sxs-lookup"><span data-stu-id="1c47c-267">Use the **Filter** text box to filter events by activity name.</span></span>  

<span data-ttu-id="1c47c-268">默认情况下，**分组菜单**设置为"无**分组"。**</span><span class="sxs-lookup"><span data-stu-id="1c47c-268">By default the **Grouping** menu is set to **No Grouping**.</span></span>  <span data-ttu-id="1c47c-269">使用 **"分组"** 菜单根据各种条件对活动表进行排序。</span><span class="sxs-lookup"><span data-stu-id="1c47c-269">Use the **Grouping** menu to sort the activity table based on various criteria.</span></span>  

<span data-ttu-id="1c47c-270">Choose **Show Heaviest Stack** \ (Show ![ Heaviest Stack ][ImageShowHeaviestStackIcon] \) to reveal another table to the right of the **Activity** table.</span><span class="sxs-lookup"><span data-stu-id="1c47c-270">Choose **Show Heaviest Stack** \(![Show Heaviest Stack][ImageShowHeaviestStackIcon]\) to reveal another table to the right of the **Activity** table.</span></span>  <span data-ttu-id="1c47c-271">选择一个活动以填充最 **重的 Stack** 表。</span><span class="sxs-lookup"><span data-stu-id="1c47c-271">Choose an activity to populate the **Heaviest Stack** table.</span></span>  <span data-ttu-id="1c47c-272">" **最重堆栈** "表显示所选活动的哪些子项运行时间最长。</span><span class="sxs-lookup"><span data-stu-id="1c47c-272">The **Heaviest Stack** table displays which children of the selected activity took the longest time to run.</span></span>  

#### <span data-ttu-id="1c47c-273">"Bottom-Up"选项卡</span><span class="sxs-lookup"><span data-stu-id="1c47c-273">The Bottom-Up tab</span></span>  

<span data-ttu-id="1c47c-274">使用 **"底部向上"** 选项卡可查看哪些活动在聚合中直接使用最多时间。</span><span class="sxs-lookup"><span data-stu-id="1c47c-274">Use the **Bottom-Up** tab to view which activities directly took up the most time in aggregate.</span></span>  

<span data-ttu-id="1c47c-275">The **Bottom-Up** tab only displays activities during the selected portion of the recording.</span><span class="sxs-lookup"><span data-stu-id="1c47c-275">The **Bottom-Up** tab only displays activities during the selected portion of the recording.</span></span>  <span data-ttu-id="1c47c-276">导航 [到"选择录音的一部分](#select-a-portion-of-a-recording) "，了解如何选择部分。</span><span class="sxs-lookup"><span data-stu-id="1c47c-276">Navigate to [Select a portion of a recording](#select-a-portion-of-a-recording) to learn how to select portions.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-bottoms-up.msft.png" alt-text=""Bottom-Up"选项卡" lightbox="../media/evaluate-performance-performance-bottoms-up.msft.png":::
   <span data-ttu-id="1c47c-278">" **下向上"** 选项卡</span><span class="sxs-lookup"><span data-stu-id="1c47c-278">The **Bottom-Up** tab</span></span>  
:::image-end:::  

<span data-ttu-id="1c47c-279">在 **上图** 的"主"部分绘制图表上，导航到几乎花费运行的所有时间 `Parse HTML` 。</span><span class="sxs-lookup"><span data-stu-id="1c47c-279">In the **Main** section flame chart of the previous figure, navigate to that almost practically all of the time was spent running `Parse HTML`.</span></span>  <span data-ttu-id="1c47c-280">上图的 **"下向上"** 选项卡中的顶部活动是 `Parse HTML` 。</span><span class="sxs-lookup"><span data-stu-id="1c47c-280">The top activity in the **Bottom-Up** tab of the previous figure is `Parse HTML`.</span></span>  <!--In the flame chart of the previous figure, the yellow below the calls to `wait` are actually thousands of `Minor GC` calls.  -->  <span data-ttu-id="1c47c-281">导航到 **"底部向上"** 选项卡，下一个最昂贵的活动是 `Layout` 。</span><span class="sxs-lookup"><span data-stu-id="1c47c-281">Navigate to the **Bottom-Up** tab, the next most expensive activity is `Layout`.</span></span>  

<span data-ttu-id="1c47c-282">" **自** 时间"列表示直接在活动（所有事件）中花费的聚合时间。</span><span class="sxs-lookup"><span data-stu-id="1c47c-282">The **Self Time** column represents the aggregated time spent directly in that activity, across all of the occurrences.</span></span>  

<span data-ttu-id="1c47c-283">" **总时间** "列表示该活动或任何子活动所花费的聚合时间。</span><span class="sxs-lookup"><span data-stu-id="1c47c-283">The **Total Time** column represents aggregated time spent in that activity or any of the children.</span></span>  

#### <span data-ttu-id="1c47c-284">"事件日志"选项卡</span><span class="sxs-lookup"><span data-stu-id="1c47c-284">The Event Log tab</span></span>  

<span data-ttu-id="1c47c-285">使用 **"事件日志** "选项卡按记录期间活动发生的顺序查看活动。</span><span class="sxs-lookup"><span data-stu-id="1c47c-285">Use the **Event Log** tab to view activities in the order in which they occurred during the recording.</span></span>  

<span data-ttu-id="1c47c-286">" **事件日志** "选项卡仅显示记录选定部分期间的活动。</span><span class="sxs-lookup"><span data-stu-id="1c47c-286">The **Event Log** tab only displays activities during the selected portion of the recording.</span></span>  <span data-ttu-id="1c47c-287">导航 [到"选择录音的一部分](#select-a-portion-of-a-recording) "，了解如何选择部分。</span><span class="sxs-lookup"><span data-stu-id="1c47c-287">Navigate to [Select a portion of a recording](#select-a-portion-of-a-recording) to learn how to select portions.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-event-log.msft.png" alt-text=""事件日志"选项卡" lightbox="../media/evaluate-performance-performance-event-log.msft.png":::
   <span data-ttu-id="1c47c-289">" **事件日志"** 选项卡</span><span class="sxs-lookup"><span data-stu-id="1c47c-289">The **Event Log** tab</span></span>  
:::image-end:::  

<span data-ttu-id="1c47c-290">" **开始时间** "列表示该活动的开始点（相对于录制的开始）。</span><span class="sxs-lookup"><span data-stu-id="1c47c-290">The **Start Time** column represents the point at which that activity started, relative to the start of the recording.</span></span>  <span data-ttu-id="1c47c-291">例如，上图中选定项目的开始时间意味着活动在 `175.7 ms` 录制开始后的 175.7 毫秒开始。</span><span class="sxs-lookup"><span data-stu-id="1c47c-291">For example, the start time of `175.7 ms` for the selected item in the previous figure means that activity started 175.7 ms after the recording started.</span></span>  

<span data-ttu-id="1c47c-292">" **自** 时间"列表示直接在活动中花费的时间。</span><span class="sxs-lookup"><span data-stu-id="1c47c-292">The **Self Time** column represents the time spent directly in that activity.</span></span>  

<span data-ttu-id="1c47c-293">**"总时间**"列表示直接在活动或任何子项中花费的时间。</span><span class="sxs-lookup"><span data-stu-id="1c47c-293">The **Total Time** columns represents time spent directly in that activity or in any of the children.</span></span>  

<span data-ttu-id="1c47c-294">选择 **"开始时间\*\*\*\*"、"** 自选\*\*\*\* 时间"或"总时间"按该列对表进行排序。</span><span class="sxs-lookup"><span data-stu-id="1c47c-294">Choose **Start Time**, **Self Time**, or **Total Time** to sort the table by that column.</span></span>

<span data-ttu-id="1c47c-295">使用 **"筛选器** "文本框按名称筛选活动。</span><span class="sxs-lookup"><span data-stu-id="1c47c-295">Use the **Filter** text box to filter activities by name.</span></span>  

<span data-ttu-id="1c47c-296">使用 **"持续时间** "菜单筛选出任何时间少于 1 毫秒或 15 毫秒的活动。</span><span class="sxs-lookup"><span data-stu-id="1c47c-296">Use the **Duration** menu to filter out any activities that took less than 1 ms or 15 ms.</span></span>  <span data-ttu-id="1c47c-297">默认情况下 **，"持续时间** "菜单设置为 **"** 全部"，这意味着将显示所有活动。</span><span class="sxs-lookup"><span data-stu-id="1c47c-297">By default the **Duration** menu is set to **All**, meaning all activities are shown.</span></span>  

<span data-ttu-id="1c47c-298">禁用 **"加载\*\*\*\*"、"脚本"、"\*\*\*\*呈现"** 或"**绘制**"复选框以筛选掉这些类别的所有活动。</span><span class="sxs-lookup"><span data-stu-id="1c47c-298">Disable the **Loading**, **Scripting**, **Rendering**, or **Painting** checkboxes to filter out all activities from those categories.</span></span>  

### <span data-ttu-id="1c47c-299">查看 GPU 活动</span><span class="sxs-lookup"><span data-stu-id="1c47c-299">View GPU activity</span></span>  

<span data-ttu-id="1c47c-300">在 GPU 部分查看 **GPU** 活动。</span><span class="sxs-lookup"><span data-stu-id="1c47c-300">View GPU activity in the **GPU** section.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-gpu-zoomed.msft.png" alt-text="GPU 部分" lightbox="../media/evaluate-performance-performance-gpu-zoomed.msft.png":::
   <span data-ttu-id="1c47c-302">**GPU**部分</span><span class="sxs-lookup"><span data-stu-id="1c47c-302">The **GPU** section</span></span>  
:::image-end:::  

### <span data-ttu-id="1c47c-303">查看栅格活动</span><span class="sxs-lookup"><span data-stu-id="1c47c-303">View raster activity</span></span>  

<span data-ttu-id="1c47c-304">查看 **"Raster"部分中的栅格** 活动。</span><span class="sxs-lookup"><span data-stu-id="1c47c-304">View raster activity in the **Raster** section.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-raster.msft.png" alt-text=""Raster"部分" lightbox="../media/evaluate-performance-performance-raster.msft.png":::
   <span data-ttu-id="1c47c-306">**"Raster"** 部分</span><span class="sxs-lookup"><span data-stu-id="1c47c-306">The **Raster** section</span></span>  
:::image-end:::  

### <span data-ttu-id="1c47c-307">查看交互</span><span class="sxs-lookup"><span data-stu-id="1c47c-307">View interactions</span></span>  

<span data-ttu-id="1c47c-308">使用 **"交互"** 部分查找和分析在录制过程中发生的用户交互。</span><span class="sxs-lookup"><span data-stu-id="1c47c-308">Use the **Interactions** section to find and analyze user interactions that happened during the recording.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-interactions-animation.msft.png" alt-text=""交互"部分" lightbox="../media/evaluate-performance-performance-interactions-animation.msft.png":::
   <span data-ttu-id="1c47c-310">" **交互"** 部分</span><span class="sxs-lookup"><span data-stu-id="1c47c-310">The **Interactions** section</span></span>  
:::image-end:::  

<span data-ttu-id="1c47c-311">交互底部的红线表示等待主线程所花的时间。</span><span class="sxs-lookup"><span data-stu-id="1c47c-311">A red line at the bottom of an interaction represents time spent waiting for the main thread.</span></span>  

<span data-ttu-id="1c47c-312">选择交互，在"摘要"选项卡中查看 **有关它** 的信息。</span><span class="sxs-lookup"><span data-stu-id="1c47c-312">Choose an interaction to view more information about it in the **Summary** tab.</span></span>  

### <span data-ttu-id="1c47c-313">分析每秒帧数 (FPS) </span><span class="sxs-lookup"><span data-stu-id="1c47c-313">Analyze frames per second (FPS)</span></span>  

<span data-ttu-id="1c47c-314">DevTools 提供了多种分析每秒帧数的方法：</span><span class="sxs-lookup"><span data-stu-id="1c47c-314">DevTools provides numerous ways to analyze frames per second:</span></span>  

*   <span data-ttu-id="1c47c-315">使用 [FPS 图表](#the-fps-chart) 获取在录制持续时间内 FPS 的概述。</span><span class="sxs-lookup"><span data-stu-id="1c47c-315">Use [the FPS chart](#the-fps-chart) to get an overview of FPS over the duration of the recording.</span></span>  
*   <span data-ttu-id="1c47c-316">使用 ["框架"](#the-frames-section) 部分查看特定帧所需要的时间。</span><span class="sxs-lookup"><span data-stu-id="1c47c-316">Use [the Frames section](#the-frames-section) to view how long a particular frame took.</span></span>  
*   <span data-ttu-id="1c47c-317">在 **页面运行时，使用 FPS** 指示器实时估计 FPS。</span><span class="sxs-lookup"><span data-stu-id="1c47c-317">Use the **FPS meter** for a realtime estimate of FPS as the page runs.</span></span>  <span data-ttu-id="1c47c-318">使用 FPS 指示器导航到"查看[每秒帧数"。](#view-frames-per-second-in-realtime-with-the-fps-meter)</span><span class="sxs-lookup"><span data-stu-id="1c47c-318">Navigate to [View frames per second in realtime with the FPS meter](#view-frames-per-second-in-realtime-with-the-fps-meter).</span></span>  
    
#### <span data-ttu-id="1c47c-319">FPS 图表</span><span class="sxs-lookup"><span data-stu-id="1c47c-319">The FPS chart</span></span>  

<span data-ttu-id="1c47c-320">**FPS**图表概述了在录制期间帧速率。</span><span class="sxs-lookup"><span data-stu-id="1c47c-320">The **FPS** chart provides an overview of the frame rate across the duration of a recording.</span></span>  <span data-ttu-id="1c47c-321">一般情况下，绿色条形越高，帧速率越好。</span><span class="sxs-lookup"><span data-stu-id="1c47c-321">In general, the higher the green bar, the better the frame rate.</span></span>  

<span data-ttu-id="1c47c-322">**FPS**图表上方的红色条是一条警告，指出帧速率下降得低到可能损害用户体验。</span><span class="sxs-lookup"><span data-stu-id="1c47c-322">A red bar above the **FPS** chart is a warning that the frame rate dropped so low that it probably harmed the user's experience.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-fps-highlight.msft.png" alt-text="FPS 图表" lightbox="../media/evaluate-performance-performance-fps-highlight.msft.png":::
   <span data-ttu-id="1c47c-324">**FPS**图表</span><span class="sxs-lookup"><span data-stu-id="1c47c-324">The **FPS** chart</span></span>  
:::image-end:::  

#### <span data-ttu-id="1c47c-325">"框架"部分</span><span class="sxs-lookup"><span data-stu-id="1c47c-325">The Frames section</span></span>  

<span data-ttu-id="1c47c-326">" **框架** "部分会准确告知你特定帧所需要的时间。</span><span class="sxs-lookup"><span data-stu-id="1c47c-326">The **Frames** section tells you exactly how long a particular frame took.</span></span>  

<span data-ttu-id="1c47c-327">将鼠标悬停在框架上，查看工具提示，详细了解它。</span><span class="sxs-lookup"><span data-stu-id="1c47c-327">Hover over a frame to view a tooltip with more information about it.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-frames-hover.msft.png" alt-text="将鼠标悬停在框架上" lightbox="../media/evaluate-performance-performance-frames-hover.msft.png":::
   <span data-ttu-id="1c47c-329">将鼠标悬停在框架上</span><span class="sxs-lookup"><span data-stu-id="1c47c-329">Hover over a frame</span></span>  
:::image-end:::  

<span data-ttu-id="1c47c-330">选择一个框架，在"摘要"选项卡中查看有关 **框架** 详细信息。 DevTools 以蓝色概述了选定的框架。</span><span class="sxs-lookup"><span data-stu-id="1c47c-330">Choose a frame to view more information about the frame in the **Summary** tab.  DevTools outlines the selected frame in blue.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-frames-summary.msft.png" alt-text="在"摘要"选项卡中查看框架" lightbox="../media/evaluate-performance-performance-frames-summary.msft.png":::
   <span data-ttu-id="1c47c-332">在"摘要"选项卡 **中查看** 框架</span><span class="sxs-lookup"><span data-stu-id="1c47c-332">View a frame in the **Summary** tab</span></span>  
:::image-end:::  

### <span data-ttu-id="1c47c-333">查看网络请求</span><span class="sxs-lookup"><span data-stu-id="1c47c-333">View network requests</span></span>  

<span data-ttu-id="1c47c-334">展开 **"网络** "部分以查看记录期间发生的网络请求的瀑布。</span><span class="sxs-lookup"><span data-stu-id="1c47c-334">Expand the **Network** section to view a waterfall of network requests that occurred during the recording.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-network.msft.png" alt-text=""网络"部分" lightbox="../media/evaluate-performance-performance-network.msft.png":::
   <span data-ttu-id="1c47c-336">" **网络"** 部分</span><span class="sxs-lookup"><span data-stu-id="1c47c-336">The **Network** section</span></span>  
:::image-end:::  

<span data-ttu-id="1c47c-337">请求按如下方式进行颜色编码：</span><span class="sxs-lookup"><span data-stu-id="1c47c-337">Requests are color-coded as follows:</span></span>  

*   <span data-ttu-id="1c47c-338">HTML：蓝色</span><span class="sxs-lookup"><span data-stu-id="1c47c-338">HTML: Blue</span></span>  
*   <span data-ttu-id="1c47c-339">CSS：紫色</span><span class="sxs-lookup"><span data-stu-id="1c47c-339">CSS: Purple</span></span>  
*   <span data-ttu-id="1c47c-340">JS：黄色</span><span class="sxs-lookup"><span data-stu-id="1c47c-340">JS: Yellow</span></span>  
*   <span data-ttu-id="1c47c-341">图像：绿色</span><span class="sxs-lookup"><span data-stu-id="1c47c-341">Images: Green</span></span>  
    
<span data-ttu-id="1c47c-342">选择一个请求，在"摘要"选项卡中查看**有关它**详细信息。 例如，在上图中，"摘要"\*\*\*\* 选项卡显示有关在"网络"部分选择的蓝色**请求详细信息。**</span><span class="sxs-lookup"><span data-stu-id="1c47c-342">Choose a request to view more information about it in the **Summary** tab.  For example, in the previous figure, the **Summary** tab is displaying more information about the blue request that is selected in the **Network** section.</span></span>  

<span data-ttu-id="1c47c-343">请求左上方的深蓝色正方形表示它是优先级较高的请求。</span><span class="sxs-lookup"><span data-stu-id="1c47c-343">A darker-blue square in the top-left of a request means it is a higher-priority request.</span></span>  <span data-ttu-id="1c47c-344">浅蓝色正方形表示较低的优先级。</span><span class="sxs-lookup"><span data-stu-id="1c47c-344">A lighter-blue square means lower-priority.</span></span>  <span data-ttu-id="1c47c-345">例如，在上图中，蓝色选定请求的优先级更高，其下方的绿色请求优先级较低。</span><span class="sxs-lookup"><span data-stu-id="1c47c-345">For example, in the previous figure, the blue, selected request is higher-priority, and the green one below it is lower-priority.</span></span>  

<span data-ttu-id="1c47c-346">在下图的第 1 部分中，请求表示为左侧的线条、中间带深色部分的条形图和浅色部分，以及右边的 `www.bing.com` 线条。</span><span class="sxs-lookup"><span data-stu-id="1c47c-346">In the 1st of the following figures, the request for `www.bing.com` is represented by a line on the left, a bar in the middle with a dark portion and a light portion, and a line on the right.</span></span>  <span data-ttu-id="1c47c-347">在下图的第 2 个中，显示了"网络"面板的"计时"\*\*\*\* 选项卡中相同请求**的相应**表示形式。</span><span class="sxs-lookup"><span data-stu-id="1c47c-347">In the 2nd of the following figures shows the corresponding representation of the same request in the **Timing** tab of the **Network** panel.</span></span>  <span data-ttu-id="1c47c-348">下面说明这两种表示形式如何相互映射：</span><span class="sxs-lookup"><span data-stu-id="1c47c-348">Here is how these two representations map to each other:</span></span>

*   <span data-ttu-id="1c47c-349">左边行是事件组的所有内容（ `Connection Start` 包含两者）。</span><span class="sxs-lookup"><span data-stu-id="1c47c-349">The left line is everything up to the `Connection Start` group of events, inclusive.</span></span>  <span data-ttu-id="1c47c-350">换句话说，它是之前的所有内容， `Request Sent` 独占。</span><span class="sxs-lookup"><span data-stu-id="1c47c-350">In other words, it is everything before `Request Sent`, exclusive.</span></span>  
*   <span data-ttu-id="1c47c-351">条形图的光线部分为 `Request Sent` and `Waiting (TTFB)` 。</span><span class="sxs-lookup"><span data-stu-id="1c47c-351">The light portion of the bar is `Request Sent` and `Waiting (TTFB)`.</span></span>  
*   <span data-ttu-id="1c47c-352">条形图的深色部分为 `Content Download` 。</span><span class="sxs-lookup"><span data-stu-id="1c47c-352">The dark portion of the bar is `Content Download`.</span></span>  
*   <span data-ttu-id="1c47c-353">正确的行实质上是等待主线程所花的时间。</span><span class="sxs-lookup"><span data-stu-id="1c47c-353">The right line is essentially time spent waiting for the main thread.</span></span>  <span data-ttu-id="1c47c-354">This is not represented in the **Timing** tab.</span><span class="sxs-lookup"><span data-stu-id="1c47c-354">This is not represented in the **Timing** tab.</span></span>  
    
:::row:::
   :::column span="":::
      :::image type="complex" source="../media/evaluate-performance-bing-performance-network.msft.png" alt-text="请求的线www.bing.com表示" lightbox="../media/evaluate-performance-bing-performance-network.msft.png":::
         <span data-ttu-id="1c47c-356">请求的线栏 `www.bing.com` 表示形式</span><span class="sxs-lookup"><span data-stu-id="1c47c-356">The line-bar representation of the `www.bing.com` request</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/evaluate-performance-bing-network-timing.msft.png" alt-text="网络工具" lightbox="../media/evaluate-performance-bing-network-timing.msft.png":::
         <span data-ttu-id="1c47c-358">网络**工具**</span><span class="sxs-lookup"><span data-stu-id="1c47c-358">The **Network** tool</span></span>  
<span data-ttu-id="1c47c-359">： ：：image-end：：：</span><span class="sxs-lookup"><span data-stu-id="1c47c-359">:     ::image-end:::</span></span>  
   :::column-end:::
:::row-end:::

### <span data-ttu-id="1c47c-360">查看内存指标</span><span class="sxs-lookup"><span data-stu-id="1c47c-360">View memory metrics</span></span>  

<span data-ttu-id="1c47c-361">打开" **内存"** 复选框以查看上次录制中的内存指标。</span><span class="sxs-lookup"><span data-stu-id="1c47c-361">Turn on the **Memory** checkbox to view memory metrics from the last recording.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-memory-highlight.msft.png" alt-text=""内存"复选框" lightbox="../media/evaluate-performance-performance-memory-highlight.msft.png":::
   <span data-ttu-id="1c47c-363">" **内存"** 复选框</span><span class="sxs-lookup"><span data-stu-id="1c47c-363">The **Memory** checkbox</span></span>  
:::image-end:::  

<span data-ttu-id="1c47c-364">DevTools**在"摘要**"选项卡上方显示新的**内存**图表。 NET 图表下方还有一**个新的图表，** 称为**HEAP。**</span><span class="sxs-lookup"><span data-stu-id="1c47c-364">DevTools displays a new **Memory** chart, above the **Summary** tab.  There is also a new chart below the **NET** chart, called **HEAP**.</span></span>  <span data-ttu-id="1c47c-365">**HEAP**图表提供与内存图表中**JS 堆**行**相同的**信息。</span><span class="sxs-lookup"><span data-stu-id="1c47c-365">The **HEAP** chart provides the same information as the **JS Heap** line in the **Memory** chart.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-memory-chart.msft.png" alt-text="内存指标" lightbox="../media/evaluate-performance-performance-memory-chart.msft.png":::
   <span data-ttu-id="1c47c-367">内存指标</span><span class="sxs-lookup"><span data-stu-id="1c47c-367">Memory metrics</span></span>  
:::image-end:::  

<span data-ttu-id="1c47c-368">图表上的彩色线条将映射到图表上方的彩色复选框。</span><span class="sxs-lookup"><span data-stu-id="1c47c-368">The colored lines on the chart map to the colored checkboxes above the chart.</span></span>  
<span data-ttu-id="1c47c-369">禁用复选框以在图表中隐藏该类别。</span><span class="sxs-lookup"><span data-stu-id="1c47c-369">Disable a checkbox to hide that category from the chart.</span></span>  

<span data-ttu-id="1c47c-370">该图表仅显示当前选定的录制区域。</span><span class="sxs-lookup"><span data-stu-id="1c47c-370">The chart only displays the region of the recording that is currently selected.</span></span>  <span data-ttu-id="1c47c-371">例如，在上图中，内存图表只\*\*\*\* 显示内存使用率，从 400 毫秒标记到 1750 毫秒标记。</span><span class="sxs-lookup"><span data-stu-id="1c47c-371">For example, in the previous figure, the **Memory** chart is only showing memory usage from around the 400 ms mark to the 1750 ms mark.</span></span>  

### <span data-ttu-id="1c47c-372">查看部分录制的持续时间</span><span class="sxs-lookup"><span data-stu-id="1c47c-372">View the duration of a portion of a recording</span></span>  

<span data-ttu-id="1c47c-373">分析网络或\*\*Main\*\*\*\*\*\* 等内容时，有时需要更精确地估计特定事件所经过的时日。</span><span class="sxs-lookup"><span data-stu-id="1c47c-373">When analyzing a section like **Network** or **Main**, sometimes you need a more precise estimate of how long certain events took.</span></span>  <span data-ttu-id="1c47c-374">按住 `Shift` 、选择并按住，然后向左或向右拖动以选择录制的一部分。</span><span class="sxs-lookup"><span data-stu-id="1c47c-374">Hold `Shift`, choose and hold, and drag left or right to select a portion of the recording.</span></span>  <span data-ttu-id="1c47c-375">在选择的底部，DevTools 显示该部分所使用时间。</span><span class="sxs-lookup"><span data-stu-id="1c47c-375">At the bottom of your selection, DevTools shows how long that portion took.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-main-duration.msft.png" alt-text="查看部分录制的持续时间" lightbox="../media/evaluate-performance-performance-main-duration.msft.png":::
   <span data-ttu-id="1c47c-377">查看部分录制的持续时间</span><span class="sxs-lookup"><span data-stu-id="1c47c-377">View the duration of a portion of a recording</span></span>  
:::image-end:::  

### <span data-ttu-id="1c47c-378">查看屏幕截图</span><span class="sxs-lookup"><span data-stu-id="1c47c-378">View a screenshot</span></span>  

<span data-ttu-id="1c47c-379">导航到 [录制时捕获屏幕截图](#capture-screenshots-while-recording) ，了解如何打开屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="1c47c-379">Navigate to [Capture screenshots while recording](#capture-screenshots-while-recording) to learn how to turn on screenshots.</span></span>  

<span data-ttu-id="1c47c-380">将鼠标悬停在 **"概述** "上可查看该页面在录制的这一时刻的外观的屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="1c47c-380">Hover over the **Overview** to view a screenshot of how the page looked during that moment of the recording.</span></span>  <span data-ttu-id="1c47c-381">概述**是**包含 CPU、FPS\*\*\*\* 和\*\*\*\* **NET**图表的部分。</span><span class="sxs-lookup"><span data-stu-id="1c47c-381">The **Overview** is the section that contains the **CPU**, **FPS**, and **NET** charts.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-screenshots-hover.msft.png" alt-text="查看屏幕截图" lightbox="../media/evaluate-performance-performance-screenshots-hover.msft.png":::
   <span data-ttu-id="1c47c-383">查看屏幕截图</span><span class="sxs-lookup"><span data-stu-id="1c47c-383">View a screenshot</span></span>  
:::image-end:::  

<span data-ttu-id="1c47c-384">您还可以通过选择"框架"部分中的框架 **来查看屏幕截图** 。</span><span class="sxs-lookup"><span data-stu-id="1c47c-384">You may also view screenshots by choosing a frame in the **Frames** section.</span></span>  <span data-ttu-id="1c47c-385">DevTools 在"摘要"选项卡中显示屏幕截图 **的较小** 版本。</span><span class="sxs-lookup"><span data-stu-id="1c47c-385">DevTools displays a small version of the screenshot in the **Summary** tab.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-summary-preview.msft.png" alt-text="查看"摘要"选项卡中的屏幕截图" lightbox="../media/evaluate-performance-performance-summary-preview.msft.png":::
   <span data-ttu-id="1c47c-387">查看"摘要" **选项卡中的** 屏幕截图</span><span class="sxs-lookup"><span data-stu-id="1c47c-387">View a screenshot in the **Summary** tab</span></span>  
:::image-end:::  

<span data-ttu-id="1c47c-388">在"摘要"选项卡 **中选择缩略图** ，放大屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="1c47c-388">Choose the thumbnail in the **Summary** tab to zoom in on the screenshot.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-summary-preview-select.msft.png" alt-text="放大"摘要"选项卡中的屏幕截图" lightbox="../media/evaluate-performance-performance-summary-preview-select.msft.png":::
   <span data-ttu-id="1c47c-390">放大"摘要"选项卡**中的屏幕截图**</span><span class="sxs-lookup"><span data-stu-id="1c47c-390">Zoom into a screenshot from the **Summary** tab</span></span>  
:::image-end:::  

### <span data-ttu-id="1c47c-391">查看图层信息</span><span class="sxs-lookup"><span data-stu-id="1c47c-391">View layers information</span></span>  

<span data-ttu-id="1c47c-392">若要查看有关帧的高级层信息，请执行：</span><span class="sxs-lookup"><span data-stu-id="1c47c-392">To view advanced layers information about a frame:</span></span>  

1.  <span data-ttu-id="1c47c-393">[打开高级画图检测](#turn-on-advanced-paint-instrumentation)。</span><span class="sxs-lookup"><span data-stu-id="1c47c-393">[Turn on advanced paint instrumentation](#turn-on-advanced-paint-instrumentation).</span></span>  
1.  <span data-ttu-id="1c47c-394">选择"框架" **部分中的** 图文框。</span><span class="sxs-lookup"><span data-stu-id="1c47c-394">Select a frame in the **Frames** section.</span></span>  <span data-ttu-id="1c47c-395">DevTools 在"事件日志"选项卡旁\*\*\*\* 的新"层"选项卡中显示有关**图层**的信息。</span><span class="sxs-lookup"><span data-stu-id="1c47c-395">DevTools displays information about the layers in the new **Layers** tab, next to the **Event Log** tab.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-layers-all.msft.png" alt-text=""层"窗格" lightbox="../media/evaluate-performance-layers-all.msft.png":::
       <span data-ttu-id="1c47c-397">" **层"** 窗格</span><span class="sxs-lookup"><span data-stu-id="1c47c-397">The **Layers** pane</span></span>  
    :::image-end:::  
    
<span data-ttu-id="1c47c-398">将鼠标悬停在图层上以在图表中突出显示它。</span><span class="sxs-lookup"><span data-stu-id="1c47c-398">Hover over a layer to highlight it in the diagram.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-frames-document-nav-bar-highlighted.msft.png" alt-text="突出显示图层" lightbox="../media/evaluate-performance-performance-frames-document-nav-bar-highlighted.msft.png":::
   <span data-ttu-id="1c47c-400">突出显示图层</span><span class="sxs-lookup"><span data-stu-id="1c47c-400">Highlight a layer</span></span>  
:::image-end:::  

<span data-ttu-id="1c47c-401">若要移动图表，</span><span class="sxs-lookup"><span data-stu-id="1c47c-401">To move the diagram:</span></span>  

*   <span data-ttu-id="1c47c-402">Choose **Pan Mode** \ (Pan Mode ![ ][ImagePanModeIcon] \) to move along the X and Y axes.</span><span class="sxs-lookup"><span data-stu-id="1c47c-402">Choose **Pan Mode** \(![Pan Mode][ImagePanModeIcon]\) to move along the X and Y axes.</span></span>  
*   <span data-ttu-id="1c47c-403">选择 **旋转模式** \ (![ 旋转模式 ][ImageRotateModeIcon] \) 沿 Z 轴旋转。</span><span class="sxs-lookup"><span data-stu-id="1c47c-403">Choose **Rotate Mode** \(![Rotate Mode][ImageRotateModeIcon]\) to rotate along the Z axis.</span></span>  
*   <span data-ttu-id="1c47c-404">Choose **Reset Transform** \ (Reset Transform ![ ][ImageResetTransformIcon] \) to reset the diagram to the original position.</span><span class="sxs-lookup"><span data-stu-id="1c47c-404">Choose **Reset Transform** \(![Reset Transform][ImageResetTransformIcon]\) to reset the diagram to the original position.</span></span>  
    
### <span data-ttu-id="1c47c-405">查看绘制探查器</span><span class="sxs-lookup"><span data-stu-id="1c47c-405">View paint profiler</span></span>  

<span data-ttu-id="1c47c-406">若要查看有关绘制事件的高级信息，</span><span class="sxs-lookup"><span data-stu-id="1c47c-406">To view advanced information about a paint event:</span></span>  

1.  <span data-ttu-id="1c47c-407">[打开](#turn-on-advanced-paint-instrumentation)。</span><span class="sxs-lookup"><span data-stu-id="1c47c-407">[Turn on](#turn-on-advanced-paint-instrumentation).</span></span>  
1.  <span data-ttu-id="1c47c-408">选择 **"主** "部分 **中的 Paint** 事件。</span><span class="sxs-lookup"><span data-stu-id="1c47c-408">Select a **Paint** event in the **Main** section.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-paint-profiler.msft.png" alt-text=""绘制配置文件器"选项卡" lightbox="../media/evaluate-performance-paint-profiler.msft.png":::
       <span data-ttu-id="1c47c-410">" **绘制配置文件器"** 选项卡</span><span class="sxs-lookup"><span data-stu-id="1c47c-410">The **Paint Profiler** tab</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="1c47c-411">使用 "渲染" 选项卡分析渲染性能</span><span class="sxs-lookup"><span data-stu-id="1c47c-411">Analyze rendering performance with the Rendering tab</span></span>  

<span data-ttu-id="1c47c-412">使用"呈现 **"** 选项卡的功能帮助可视化页面的呈现性能。</span><span class="sxs-lookup"><span data-stu-id="1c47c-412">Use the features of the **Rendering** tab to help visualize the rendering performance of your page.</span></span>  

<span data-ttu-id="1c47c-413">打开"呈现 **"** 选项卡：</span><span class="sxs-lookup"><span data-stu-id="1c47c-413">To open the **Rendering** tab:</span></span>  

1.  <span data-ttu-id="1c47c-414">[打开命令菜单][DevToolsCommandMenu]。</span><span class="sxs-lookup"><span data-stu-id="1c47c-414">[Open the Command Menu][DevToolsCommandMenu].</span></span>  
1.  <span data-ttu-id="1c47c-415">开始键入并选择 `Rendering` `Show Rendering` 。</span><span class="sxs-lookup"><span data-stu-id="1c47c-415">Start typing `Rendering` and select `Show Rendering`.</span></span>  <span data-ttu-id="1c47c-416">DevTools **在** DevTools 窗口底部显示"呈现"选项卡。</span><span class="sxs-lookup"><span data-stu-id="1c47c-416">DevTools displays the **Rendering** tab at the bottom of your DevTools window.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-console-drawer-rendering.msft.png" alt-text=""呈现"选项卡" lightbox="../media/evaluate-performance-console-drawer-rendering.msft.png":::
       <span data-ttu-id="1c47c-418">" **呈现"** 选项卡</span><span class="sxs-lookup"><span data-stu-id="1c47c-418">The **Rendering** tab</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="1c47c-419">使用 FPS 指示器实时查看每秒帧数</span><span class="sxs-lookup"><span data-stu-id="1c47c-419">View frames per second in realtime with the FPS meter</span></span>  

<span data-ttu-id="1c47c-420">**FPS 指示器**是显示在视口右上角的覆盖层。</span><span class="sxs-lookup"><span data-stu-id="1c47c-420">The **FPS meter** is an overlay that appears in the top-right corner of your viewport.</span></span>  <span data-ttu-id="1c47c-421">它在页面运行时提供 FPS 实时估计值。</span><span class="sxs-lookup"><span data-stu-id="1c47c-421">It provides a realtime estimate of FPS as the page runs.</span></span>  <span data-ttu-id="1c47c-422">打开 **FPS 指示器**：</span><span class="sxs-lookup"><span data-stu-id="1c47c-422">To open the **FPS meter**:</span></span>  

1.  <span data-ttu-id="1c47c-423">打开" **呈现"** 选项卡。 Na [使用"呈现"选项卡分析呈现性能](#analyze-rendering-performance-with-the-rendering-tab)。</span><span class="sxs-lookup"><span data-stu-id="1c47c-423">Open the **Rendering** tab.  Na [Analyze rendering performance with the Rendering tab](#analyze-rendering-performance-with-the-rendering-tab).</span></span>  
1.  <span data-ttu-id="1c47c-424">打开 **"FPS 指示器"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="1c47c-424">Turn on the **FPS Meter** checkbox.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-jank-console-rendering-frame-rate.msft.png" alt-text="FPS 计数" lightbox="../media/evaluate-performance-jank-console-rendering-frame-rate.msft.png":::
       <span data-ttu-id="1c47c-426">**FPS 指示器**</span><span class="sxs-lookup"><span data-stu-id="1c47c-426">The **FPS meter**</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="1c47c-427">使用画图闪烁实时查看绘制事件</span><span class="sxs-lookup"><span data-stu-id="1c47c-427">View painting events in realtime with Paint Flashing</span></span>  

<span data-ttu-id="1c47c-428">使用"画图闪烁"可实时查看页面上的所有绘制事件。</span><span class="sxs-lookup"><span data-stu-id="1c47c-428">Use Paint Flashing to get a realtime view of all paint events on the page.</span></span>  <span data-ttu-id="1c47c-429">只要重新绘制页面的一部分，DevTools 就会用绿色概括该部分。</span><span class="sxs-lookup"><span data-stu-id="1c47c-429">Whenever a part of the page gets re-painted, DevTools outlines that section in green.</span></span>  

<span data-ttu-id="1c47c-430">若要打开"画图闪烁"，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="1c47c-430">To turn on Paint Flashing, complete the following actions.</span></span>  

1.  <span data-ttu-id="1c47c-431">打开" **呈现"** 选项卡。 导航到 ["使用呈现"选项卡分析呈现性能](#analyze-rendering-performance-with-the-rendering-tab)。</span><span class="sxs-lookup"><span data-stu-id="1c47c-431">Open the **Rendering** tab.  Navigate to [Analyze rendering performance with the Rendering tab](#analyze-rendering-performance-with-the-rendering-tab).</span></span>  
1.  <span data-ttu-id="1c47c-432">打开" **画图闪烁"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="1c47c-432">Turn on the **Paint Flashing** checkbox.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-jank-console-rendering-paint-flashing.msft.png" alt-text="画笔闪烁" lightbox="../media/evaluate-performance-jank-console-rendering-paint-flashing.msft.png":::
       **<span data-ttu-id="1c47c-434">画笔闪烁</span><span class="sxs-lookup"><span data-stu-id="1c47c-434">Paint Flashing</span></span>**  
    :::image-end:::  
    
### <span data-ttu-id="1c47c-435">查看具有图层边框的图层覆盖</span><span class="sxs-lookup"><span data-stu-id="1c47c-435">View an overlay of layers with Layer Borders</span></span>  

<span data-ttu-id="1c47c-436">使用 **图层边框** 查看页面顶部的图层边框和磁贴的覆盖。</span><span class="sxs-lookup"><span data-stu-id="1c47c-436">Use **Layer Borders** to view an overlay of layer borders and tiles on top of the page.</span></span>  

<span data-ttu-id="1c47c-437">若要打开图层边框，请完成以下操作：</span><span class="sxs-lookup"><span data-stu-id="1c47c-437">To turn on Layer Borders, complete the following actions,</span></span>  

1.  <span data-ttu-id="1c47c-438">打开" **呈现"** 选项卡。 导航到 ["使用呈现"选项卡分析呈现性能](#analyze-rendering-performance-with-the-rendering-tab)。</span><span class="sxs-lookup"><span data-stu-id="1c47c-438">Open the **Rendering** tab.  Navigate to [Analyze rendering performance with the Rendering tab](#analyze-rendering-performance-with-the-rendering-tab).</span></span>  
1.  <span data-ttu-id="1c47c-439">打开" **图层边框"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="1c47c-439">Turn on the **Layer Borders** checkbox.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-devtools-console-rendering-layer-borders.msft.png" alt-text="层边框" lightbox="../media/evaluate-performance-devtools-console-rendering-layer-borders.msft.png":::
       **<span data-ttu-id="1c47c-441">层边框</span><span class="sxs-lookup"><span data-stu-id="1c47c-441">Layer Borders</span></span>**  
    :::image-end:::  
    
<span data-ttu-id="1c47c-442">导航到 [debug_colors.cc][ChromiumDebugColors] 中的注释，了解颜色编码的说明。</span><span class="sxs-lookup"><span data-stu-id="1c47c-442">Navigate to the comments in [debug_colors.cc][ChromiumDebugColors] for an explanation of the color-codings.</span></span>  

### <span data-ttu-id="1c47c-443">实时查找滚动性能问题</span><span class="sxs-lookup"><span data-stu-id="1c47c-443">Find scroll performance issues in realtime</span></span>  

<span data-ttu-id="1c47c-444">使用滚动性能问题可标识具有与滚动相关的事件侦听器的页面元素，这些元素可能会损害页面的性能。</span><span class="sxs-lookup"><span data-stu-id="1c47c-444">Use Scrolling Performance Issues to identify elements of the page that have event listeners related to scrolling that may harm the performance of the page.</span></span>  
<span data-ttu-id="1c47c-445">DevTools 以青色概述了可能存在问题的元素。</span><span class="sxs-lookup"><span data-stu-id="1c47c-445">DevTools outlines the potentially-problematic elements in teal.</span></span>  

<span data-ttu-id="1c47c-446">若要查看滚动性能问题，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="1c47c-446">To view scroll performance issues, complete the following actions.</span></span> 

1.  <span data-ttu-id="1c47c-447">打开" **呈现"** 选项卡。 导航到 ["使用呈现"选项卡分析呈现性能](#analyze-rendering-performance-with-the-rendering-tab)。</span><span class="sxs-lookup"><span data-stu-id="1c47c-447">Open the **Rendering** tab.  Navigate to [Analyze rendering performance with the Rendering tab](#analyze-rendering-performance-with-the-rendering-tab).</span></span>  
1.  <span data-ttu-id="1c47c-448">打开" **滚动性能问题"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="1c47c-448">Turn on the **Scrolling Performance Issues** checkbox.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-bing-console-drawer-rendering-scrolling-performance-issues.msft.png" alt-text="滚动性能问题指示非层视口约束的对象可能会损害滚动性能" lightbox="../media/evaluate-performance-bing-console-drawer-rendering-scrolling-performance-issues.msft.png":::
       <span data-ttu-id="1c47c-450">**滚动性能问题** 指示非层视口约束的对象可能会损害滚动性能</span><span class="sxs-lookup"><span data-stu-id="1c47c-450">**Scrolling Performance Issues** indicates that non-layer viewport-constrained objects may harm scroll performance</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="1c47c-451">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="1c47c-451">Getting in touch with the Microsoft Edge DevTools team</span></span>  

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

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 开发人员工具 |Microsoft Docs"  
[DevToolsCommandMenu]: ../command-menu/index.md#open-the-command-menu "打开命令菜单 - 使用 Microsoft Edge DevTools 命令菜单运行命令 |Microsoft Docs"  
[DevtoolsEvaluatePerformanceGettingStarted]: ./index.md "开始分析运行时性能 |Microsoft Docs"  

[ActivityTabsDemo]: https://microsoft-edge-chromium-devtools.glitch.me/perf/activitytabs.html "活动选项卡演示 |小故障"  

[ChromiumDebugColors]: https://cs.chromium.org/chromium/src/cc/debug/debug_colors.cc "debug_colors.cc - 代码搜索"  

> [!NOTE]
> <span data-ttu-id="1c47c-457">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="1c47c-457">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="1c47c-458">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/reference)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="1c47c-458">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/reference) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="1c47c-460">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="1c47c-460">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
