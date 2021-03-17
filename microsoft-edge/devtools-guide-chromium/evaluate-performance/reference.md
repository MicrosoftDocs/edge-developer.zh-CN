---
description: 有关在 Microsoft Edge DevTools 中记录和分析性能的所有方法的参考。
title: 性能分析引用
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: e7774dc0aab647b8cf2bf47699368fafe6c21d70
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439687"
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

# <a name="performance-analysis-reference"></a><span data-ttu-id="d3100-104">性能分析引用</span><span class="sxs-lookup"><span data-stu-id="d3100-104">Performance analysis reference</span></span>  

<span data-ttu-id="d3100-105">本页全面引用了与分析性能相关的 Microsoft Edge DevTools 功能。</span><span class="sxs-lookup"><span data-stu-id="d3100-105">This page is a comprehensive reference of Microsoft Edge DevTools features related to analyzing performance.</span></span>  

<span data-ttu-id="d3100-106">导航到 [开始分析][DevtoolsEvaluatePerformanceGettingStarted] 运行时性能，获取有关如何使用 [Microsoft Edge DevTools][MicrosoftEdgeDevTools]分析页面性能的引导教程。</span><span class="sxs-lookup"><span data-stu-id="d3100-106">Navigate to [Get Started With Analyzing Runtime Performance][DevtoolsEvaluatePerformanceGettingStarted] for a guided tutorial on how to analyze the performance of a page using [Microsoft Edge DevTools][MicrosoftEdgeDevTools].</span></span>  

## <a name="record-performance"></a><span data-ttu-id="d3100-107">记录性能</span><span class="sxs-lookup"><span data-stu-id="d3100-107">Record performance</span></span>  

### <a name="record-runtime-performance"></a><span data-ttu-id="d3100-108">记录运行时性能</span><span class="sxs-lookup"><span data-stu-id="d3100-108">Record runtime performance</span></span>  

<span data-ttu-id="d3100-109">当你想要分析页面运行时的性能（而不是加载）时，请记录运行时性能。</span><span class="sxs-lookup"><span data-stu-id="d3100-109">Record runtime performance when you want to analyze the performance of a page as it is running, as opposed to loading.</span></span>  

1.  <span data-ttu-id="d3100-110">导航到要分析的页面。</span><span class="sxs-lookup"><span data-stu-id="d3100-110">Navigate to the page that you want to analyze.</span></span>  
1.  <span data-ttu-id="d3100-111">在\*\*\*\* DevTools 中打开性能工具。</span><span class="sxs-lookup"><span data-stu-id="d3100-111">Open the **Performance** tool in DevTools.</span></span>  
1.  <span data-ttu-id="d3100-112">Choose **Record** \ (![ Record icon ](../media/record-icon.msft.png) \) .</span><span class="sxs-lookup"><span data-stu-id="d3100-112">Choose **Record** \(![Record icon](../media/record-icon.msft.png)\).</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-performance-record-highlight.msft.png" alt-text="记录" lightbox="../media/evaluate-performance-performance-record-highlight.msft.png":::
       **<span data-ttu-id="d3100-114">记录</span><span class="sxs-lookup"><span data-stu-id="d3100-114">Record</span></span>**  
    :::image-end:::  
    
1.  <span data-ttu-id="d3100-115">与页面交互。</span><span class="sxs-lookup"><span data-stu-id="d3100-115">Interact with the page.</span></span>  <span data-ttu-id="d3100-116">DevTools 记录交互后发生的所有页面活动。</span><span class="sxs-lookup"><span data-stu-id="d3100-116">DevTools records all page activity that occurs as a result of your interactions.</span></span>  
1.  <span data-ttu-id="d3100-117">再次 **选择"录制** "或" **停止** "以停止录制。</span><span class="sxs-lookup"><span data-stu-id="d3100-117">Choose **Record** again or choose **Stop** to stop recording.</span></span>  
    
### <a name="record-load-performance"></a><span data-ttu-id="d3100-118">记录加载性能</span><span class="sxs-lookup"><span data-stu-id="d3100-118">Record load performance</span></span>  

<span data-ttu-id="d3100-119">在页面加载时（而不是运行时）要分析其性能时记录加载性能。</span><span class="sxs-lookup"><span data-stu-id="d3100-119">Record load performance when you want to analyze the performance of a page as it is loading, as opposed to running.</span></span>  

1.  <span data-ttu-id="d3100-120">导航到要分析的页面。</span><span class="sxs-lookup"><span data-stu-id="d3100-120">Navigate to the page that you want to analyze.</span></span>  
1.  <span data-ttu-id="d3100-121">打开\*\*\*\* DevTools 的性能面板。</span><span class="sxs-lookup"><span data-stu-id="d3100-121">Open the **Performance** panel of DevTools.</span></span>  
1.  <span data-ttu-id="d3100-122">Choose **Refresh page** \ (Refresh Page ![ ](../media/refresh-page-icon.msft.png) \) .</span><span class="sxs-lookup"><span data-stu-id="d3100-122">Choose **Refresh page** \(![Refresh Page](../media/refresh-page-icon.msft.png)\).</span></span>  <span data-ttu-id="d3100-123">DevTools 在页面刷新时记录性能指标，然后在加载完成后的几秒钟内自动停止录制。</span><span class="sxs-lookup"><span data-stu-id="d3100-123">DevTools records performance metrics while the page refreshes and then automatically stops the recording a couple seconds after the load finishes.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-performance-refresh-button.msft.png" alt-text="刷新页面" lightbox="../media/evaluate-performance-performance-refresh-button.msft.png":::
       **<span data-ttu-id="d3100-125">刷新页面</span><span class="sxs-lookup"><span data-stu-id="d3100-125">Refresh page</span></span>**  
    :::image-end:::  
    
<span data-ttu-id="d3100-126">DevTools 自动放大大部分活动发生的记录部分。</span><span class="sxs-lookup"><span data-stu-id="d3100-126">DevTools automatically zooms in on the portion of the recording where most of the activity occurred.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-refreshed.msft.png" alt-text="页面加载录制" lightbox="../media/evaluate-performance-performance-refreshed.msft.png":::
   <span data-ttu-id="d3100-128">页面加载录制</span><span class="sxs-lookup"><span data-stu-id="d3100-128">A page-load recording</span></span>  
:::image-end:::  

### <a name="capture-screenshots-while-recording"></a><span data-ttu-id="d3100-129">录制时捕获屏幕截图</span><span class="sxs-lookup"><span data-stu-id="d3100-129">Capture screenshots while recording</span></span>  

<span data-ttu-id="d3100-130">打开" **屏幕截图"** 复选框以捕获录制时每个帧的屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="d3100-130">Turn on the **Screenshots** checkbox to capture a screenshot of every frame while recording.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-capture-screenshots-checkbox.msft.png" alt-text=""屏幕截图"复选框" lightbox="../media/evaluate-performance-performance-capture-screenshots-checkbox.msft.png":::
   <span data-ttu-id="d3100-132">" **屏幕截图"** 复选框</span><span class="sxs-lookup"><span data-stu-id="d3100-132">The **Screenshots** checkbox</span></span>  
:::image-end:::  

<span data-ttu-id="d3100-133">导航 [到查看屏幕截图](#view-a-screenshot) ，了解如何与屏幕截图进行交互。</span><span class="sxs-lookup"><span data-stu-id="d3100-133">Navigate to [View a screenshot](#view-a-screenshot) to learn how to interact with screenshots.</span></span>  

### <a name="force-garbage-collection-while-recording"></a><span data-ttu-id="d3100-134">在记录时强制进行垃圾回收</span><span class="sxs-lookup"><span data-stu-id="d3100-134">Force garbage collection while recording</span></span>  

<span data-ttu-id="d3100-135">在记录页面时，选择"收集垃圾回收 **\ (** 收集垃圾图标 ![ ](../media/collect-garbage-icon.msft.png) \) 以强制进行垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="d3100-135">While you are recording a page, choose **Collect garbage** \(![Collect garbage icon](../media/collect-garbage-icon.msft.png)\) to force garbage collection.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-collect-garbage-button.msft.png" alt-text="收集垃圾" lightbox="../media/evaluate-performance-performance-collect-garbage-button.msft.png":::
   <span data-ttu-id="d3100-137">收集垃圾</span><span class="sxs-lookup"><span data-stu-id="d3100-137">Collect garbage</span></span>  
:::image-end:::  

### <a name="show-recording-settings"></a><span data-ttu-id="d3100-138">显示录制设置</span><span class="sxs-lookup"><span data-stu-id="d3100-138">Show recording settings</span></span>  

<span data-ttu-id="d3100-139">Choose **Capture settings** \ (Capture settings ![ ](../media/capture-settings-icon.msft.png) \) to expose more settings related to how DevTools capture performance recordings.</span><span class="sxs-lookup"><span data-stu-id="d3100-139">Choose **Capture settings** \(![Capture settings](../media/capture-settings-icon.msft.png)\) to expose more settings related to how DevTools captures performance recordings.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-capture-settings-button-open-drawer.msft.png" alt-text=""捕获设置"部分" lightbox="../media/evaluate-performance-performance-capture-settings-button-open-drawer.msft.png":::
   <span data-ttu-id="d3100-141">" **捕获设置"** 部分</span><span class="sxs-lookup"><span data-stu-id="d3100-141">The **Capture Settings** section</span></span>  
:::image-end:::  

### <a name="disable-javascript-samples"></a><span data-ttu-id="d3100-142">禁用 JavaScript 示例</span><span class="sxs-lookup"><span data-stu-id="d3100-142">Disable JavaScript samples</span></span>  

<span data-ttu-id="d3100-143">默认情况下，录制 **的 Main** 部分显示录制期间调用的 JavaScript 函数的详细调用堆栈。</span><span class="sxs-lookup"><span data-stu-id="d3100-143">By default, the **Main** section of a recording displays detailed call stacks of JavaScript functions that were called during the recording.</span></span>  <span data-ttu-id="d3100-144">若要禁用这些调用堆栈：</span><span class="sxs-lookup"><span data-stu-id="d3100-144">To disable these call stacks:</span></span>  

1.  <span data-ttu-id="d3100-145">打开" **捕获设置"** 菜单。</span><span class="sxs-lookup"><span data-stu-id="d3100-145">Open the **Capture settings** menu.</span></span>  <span data-ttu-id="d3100-146">导航到["显示录制设置"。](#show-recording-settings)</span><span class="sxs-lookup"><span data-stu-id="d3100-146">Navigate to [Show recording settings](#show-recording-settings).</span></span>  
1.  <span data-ttu-id="d3100-147">打开" **禁用 JavaScript 示例"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="d3100-147">Turn on the **Disable JavaScript Samples** checkbox.</span></span>  
1.  <span data-ttu-id="d3100-148">录制页面。</span><span class="sxs-lookup"><span data-stu-id="d3100-148">Take a recording of the page.</span></span>  
    
<span data-ttu-id="d3100-149">以下 2 个图显示禁用和启用 JavaScript 示例的区别。</span><span class="sxs-lookup"><span data-stu-id="d3100-149">The following 2 figures display the difference between disabling and enabling JavaScript samples.</span></span>  <span data-ttu-id="d3100-150">当 **禁用** 采样时，录制的 Main 部分要短得多，因为它省略了所有 JavaScript 调用堆栈。</span><span class="sxs-lookup"><span data-stu-id="d3100-150">The **Main** section of the recording is much shorter when sampling is disabled, because it omits all of the JavaScript call stacks.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-on.msft.png" alt-text="禁用 JS 示例时录制的示例" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-on.msft.png":::
         <span data-ttu-id="d3100-152">禁用 JS 示例时录制的示例</span><span class="sxs-lookup"><span data-stu-id="d3100-152">An example of a recording when JS samples are disabled</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off.msft.png" alt-text="启用 JS 示例时的记录示例" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off.msft.png":::
         <span data-ttu-id="d3100-154">启用 JS 示例时的记录示例</span><span class="sxs-lookup"><span data-stu-id="d3100-154">An example of a recording when JS samples are turned on</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::

### <a name="throttle-the-network-while-recording"></a><span data-ttu-id="d3100-155">录制时限制网络</span><span class="sxs-lookup"><span data-stu-id="d3100-155">Throttle the network while recording</span></span>  

<span data-ttu-id="d3100-156">在录制时限制网络：</span><span class="sxs-lookup"><span data-stu-id="d3100-156">To throttle the network while recording:</span></span>  

1.  <span data-ttu-id="d3100-157">打开" **捕获设置"** 菜单。</span><span class="sxs-lookup"><span data-stu-id="d3100-157">Open the **Capture settings** menu.</span></span>  <span data-ttu-id="d3100-158">导航到["显示录制设置"。](#show-recording-settings)</span><span class="sxs-lookup"><span data-stu-id="d3100-158">Navigate to [Show recording settings](#show-recording-settings).</span></span>  
1.  <span data-ttu-id="d3100-159">将 **"** 网络"设置为所需的限制级别。</span><span class="sxs-lookup"><span data-stu-id="d3100-159">Set **Network** to the desired level of throttling.</span></span>  
    
### <a name="throttle-the-cpu-while-recording"></a><span data-ttu-id="d3100-160">在录制时限制 CPU</span><span class="sxs-lookup"><span data-stu-id="d3100-160">Throttle the CPU while recording</span></span>  

<span data-ttu-id="d3100-161">在录制时限制 CPU：</span><span class="sxs-lookup"><span data-stu-id="d3100-161">To throttle the CPU while recording:</span></span>  

1.  <span data-ttu-id="d3100-162">打开" **捕获设置"** 菜单。</span><span class="sxs-lookup"><span data-stu-id="d3100-162">Open the **Capture settings** menu.</span></span>  <span data-ttu-id="d3100-163">导航到["显示录制设置"。](#show-recording-settings)</span><span class="sxs-lookup"><span data-stu-id="d3100-163">Navigate to [Show recording settings](#show-recording-settings).</span></span>  
1.  <span data-ttu-id="d3100-164">将 **CPU** 设置为所需的限制级别。</span><span class="sxs-lookup"><span data-stu-id="d3100-164">Set **CPU** to the desired level of throttling.</span></span>  
    
<span data-ttu-id="d3100-165">限制与计算机的功能相关。</span><span class="sxs-lookup"><span data-stu-id="d3100-165">Throttling is relative to the capabilities of your computer.</span></span>  <span data-ttu-id="d3100-166">例如， **速度较慢的 2 倍** 选项使 CPU 运行速度比正常速度慢 2 倍。</span><span class="sxs-lookup"><span data-stu-id="d3100-166">For example, the **2x slowdown** option makes your CPU operate 2 times slower than normal.</span></span>  <span data-ttu-id="d3100-167">DevTools 不会真正模拟移动设备的 CPU，因为移动设备的体系结构与台式机和笔记本电脑的体系结构完全不同。</span><span class="sxs-lookup"><span data-stu-id="d3100-167">DevTools do not truly simulate the CPUs of mobile devices, because the architecture of mobile devices is very different from that of desktops and laptops.</span></span>  

### <a name="turn-on-advanced-paint-instrumentation"></a><span data-ttu-id="d3100-168">打开高级画图检测</span><span class="sxs-lookup"><span data-stu-id="d3100-168">Turn on advanced paint instrumentation</span></span>  

<span data-ttu-id="d3100-169">查看详细的画图检测：</span><span class="sxs-lookup"><span data-stu-id="d3100-169">To view detailed paint instrumentation:</span></span>  

1.  <span data-ttu-id="d3100-170">打开" **捕获设置"** 菜单。</span><span class="sxs-lookup"><span data-stu-id="d3100-170">Open the **Capture settings** menu.</span></span>  <span data-ttu-id="d3100-171">导航到["显示录制设置"。](#show-recording-settings)</span><span class="sxs-lookup"><span data-stu-id="d3100-171">Navigate to [Show recording settings](#show-recording-settings).</span></span>  
1.  <span data-ttu-id="d3100-172">选中" \*\*启用高级画图检测 (慢速) \*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="d3100-172">Check the **Enable advanced paint instrumentation (slow)** checkbox.</span></span>  

<span data-ttu-id="d3100-173">若要了解如何与画图信息进行交互，请[导航到"](#view-layers-information)查看图层"和"[查看画图探查器"。](#view-paint-profiler)</span><span class="sxs-lookup"><span data-stu-id="d3100-173">To learn how to interact with the paint information, navigate to [View layers](#view-layers-information) and [View paint profiler](#view-paint-profiler).</span></span>  

## <a name="save-a-recording"></a><span data-ttu-id="d3100-174">保存录制</span><span class="sxs-lookup"><span data-stu-id="d3100-174">Save a recording</span></span>  

<span data-ttu-id="d3100-175">若要保存录制，请打开上下文菜单 \ (右键单击\) ，然后选择"保存**配置文件"。**</span><span class="sxs-lookup"><span data-stu-id="d3100-175">To save a recording, open the contextual menu \(right-click\), and choose **Save Profile**.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-save-profile.msft.png" alt-text="保存配置文件" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-save-profile.msft.png":::
   **<span data-ttu-id="d3100-177">保存配置文件</span><span class="sxs-lookup"><span data-stu-id="d3100-177">Save Profile</span></span>**  
:::image-end:::  

## <a name="load-a-recording"></a><span data-ttu-id="d3100-178">加载录制</span><span class="sxs-lookup"><span data-stu-id="d3100-178">Load a recording</span></span>  

<span data-ttu-id="d3100-179">若要加载录制，请打开上下文菜单 \ (右键单击\) ，然后选择加载 **配置文件**。</span><span class="sxs-lookup"><span data-stu-id="d3100-179">To load a recording, open the contextual menu \(right-click\), and choose **Load Profile**.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-load-profile.msft.png" alt-text="加载配置文件" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-load-profile.msft.png":::
   **<span data-ttu-id="d3100-181">加载配置文件</span><span class="sxs-lookup"><span data-stu-id="d3100-181">Load Profile</span></span>**  
:::image-end:::  

## <a name="clear-the-previous-recording"></a><span data-ttu-id="d3100-182">清除上一个录制</span><span class="sxs-lookup"><span data-stu-id="d3100-182">Clear the previous recording</span></span>  

<span data-ttu-id="d3100-183">录制后，**选择"清除**录制 \ (清除录制"图标 \) 以从"性能"面板 ![ ](../media/clear-recording-icon.msft.png) 中清除\*\*\*\* 该录制。</span><span class="sxs-lookup"><span data-stu-id="d3100-183">After making a recording, choose **Clear recording** \(![Clear recording icon](../media/clear-recording-icon.msft.png)\) to clear that recording from the **Performance** panel.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-clear-button.msft.png" alt-text="清除录制" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-clear-button.msft.png":::
   **<span data-ttu-id="d3100-185">清除录制</span><span class="sxs-lookup"><span data-stu-id="d3100-185">Clear recording</span></span>**  
:::image-end:::  

## <a name="analyze-a-performance-recording"></a><span data-ttu-id="d3100-186">分析性能记录</span><span class="sxs-lookup"><span data-stu-id="d3100-186">Analyze a performance recording</span></span>  

<span data-ttu-id="d3100-187">记录[运行时性能或](#record-runtime-performance)[记录加载性能](#record-load-performance)后，性能面板\*\*\*\* 会提供许多数据，用于分析刚发生的情况的性能。</span><span class="sxs-lookup"><span data-stu-id="d3100-187">After you [record runtime performance](#record-runtime-performance) or [record load performance](#record-load-performance), the **Performance** panel provides a lot of data for analyzing the performance of what just happened.</span></span>  

### <a name="select-a-portion-of-a-recording"></a><span data-ttu-id="d3100-188">选择录音的一部分</span><span class="sxs-lookup"><span data-stu-id="d3100-188">Select a portion of a recording</span></span>  

<span data-ttu-id="d3100-189">将鼠标向左或向右拖动到 **"** 概述"中，选择录音的一部分。</span><span class="sxs-lookup"><span data-stu-id="d3100-189">Drag your mouse left or right across the **Overview** to select a portion of a recording.</span></span>  <span data-ttu-id="d3100-190">概述**是**包含**FPS、CPU**和\*\*\*\*\*\*NET\*\*图表的部分。</span><span class="sxs-lookup"><span data-stu-id="d3100-190">The **Overview** is the section that contains the **FPS**, **CPU**, and **NET** charts.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-zoom-highlighted.msft.png" alt-text="将鼠标拖动到概述中以缩放" lightbox="../media/evaluate-performance-performance-zoom-highlighted.msft.png":::
   <span data-ttu-id="d3100-192">将鼠标拖动到 **概述中** 以缩放</span><span class="sxs-lookup"><span data-stu-id="d3100-192">Drag the mouse across the **Overview** to zoom</span></span>  
:::image-end:::  

<span data-ttu-id="d3100-193">若要使用键盘选择部分：</span><span class="sxs-lookup"><span data-stu-id="d3100-193">To select a portion using the keyboard:</span></span>  

1.  <span data-ttu-id="d3100-194">选择"**主"部分**或它旁边的任何部分的背景，例如"**交互\*\*\*\*"、"网络**"或 **"GPU"。**</span><span class="sxs-lookup"><span data-stu-id="d3100-194">Choose the background of the **Main** section, or any of the sections next to it, such as **Interactions**, **Network**, or **GPU**.</span></span>  <span data-ttu-id="d3100-195">此键盘工作流仅在这些部分之一成为焦点时有效。</span><span class="sxs-lookup"><span data-stu-id="d3100-195">This keyboard workflow only works when one of these sections is in focus.</span></span>  
1.  <span data-ttu-id="d3100-196">分别 `W` 使用 `A` 、键 `S` `D` 进行放大、向左移动、缩小和向右移动。</span><span class="sxs-lookup"><span data-stu-id="d3100-196">Use the `W`, `A`, `S`, `D` keys to zoom in, move left, zoom out, and move right, respectively.</span></span>  

<span data-ttu-id="d3100-197">若要使用跟踪板选择部分，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="d3100-197">To select a portion using a trackpad, complete the following actions.</span></span>  

1.  <span data-ttu-id="d3100-198">将鼠标悬停在"概述 **"部分** 或" **详细信息"部分** 上。</span><span class="sxs-lookup"><span data-stu-id="d3100-198">Hover your mouse over the **Overview** section or the **Details** section.</span></span>  <span data-ttu-id="d3100-199">"**概述**"部分是包含**FPS、CPU\*\*\*\*\*\* 和**NET\*\*图表的区域。</span><span class="sxs-lookup"><span data-stu-id="d3100-199">The **Overview** section is the area containing the **FPS**, **CPU**, and **NET** charts.</span></span>  <span data-ttu-id="d3100-200">" **详细信息** "部分是包含 **"** 主"部分、" **交互"** 部分等的区域。</span><span class="sxs-lookup"><span data-stu-id="d3100-200">The **Details** section is the area containing the **Main** section, the **Interactions** section, and so on.</span></span>  
1.  <span data-ttu-id="d3100-201">使用两根手指向上轻扫以缩小，向左轻扫向左移动，向下轻扫可放大，向右轻扫可向右移动。</span><span class="sxs-lookup"><span data-stu-id="d3100-201">Using two fingers, swipe up to zoom out, swipe left to move left, swipe down to zoom in, and swipe right to move right.</span></span>  

<span data-ttu-id="d3100-202">若要在"主"部分或任何元素\*\*\*\* 中滚动长形图表，请选择并按住，同时向上和向下拖动。</span><span class="sxs-lookup"><span data-stu-id="d3100-202">To scroll a long flame chart in the **Main** section or any of the neighbors, choose and hold while dragging up and down.</span></span>  <span data-ttu-id="d3100-203">向左和向右拖动以移动所选录音的哪一部分。</span><span class="sxs-lookup"><span data-stu-id="d3100-203">Drag left and right to move what portion of the recording is chosen.</span></span>  

### <a name="search-activities"></a><span data-ttu-id="d3100-204">搜索活动</span><span class="sxs-lookup"><span data-stu-id="d3100-204">Search activities</span></span>  

<span data-ttu-id="d3100-205">选择 `Control` + `F` \ (Windows、Linux\) 或 `Command` + `F` \ (macOS\) \*\*\*\* 打开"性能"面板底部的搜索框。</span><span class="sxs-lookup"><span data-stu-id="d3100-205">Select `Control`+`F` \(Windows, Linux\) or `Command`+`F` \(macOS\) to open the search box at the bottom of the **Performance** panel.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-search-regex.msft.png" alt-text="搜索框" lightbox="../media/evaluate-performance-performance-search-regex.msft.png":::
   <span data-ttu-id="d3100-207">搜索框</span><span class="sxs-lookup"><span data-stu-id="d3100-207">The search box</span></span>  
:::image-end:::  

<span data-ttu-id="d3100-208">导航与查询匹配的活动：</span><span class="sxs-lookup"><span data-stu-id="d3100-208">To navigate activities that match your query:</span></span>  

*   <span data-ttu-id="d3100-209">使用上 **一** 个 \ (![ ](../media/previous-icon.msft.png) \) **和 下** 一个 \ (![ ](../media/next-icon.msft.png) \) 按钮。</span><span class="sxs-lookup"><span data-stu-id="d3100-209">Use the **Previous** \(![Previous](../media/previous-icon.msft.png)\) and **Next** \(![Next](../media/next-icon.msft.png)\) buttons.</span></span>  
*   <span data-ttu-id="d3100-210">选择 `Shift` + `Enter` 以选择上一个或 `Enter` 选择下一个。</span><span class="sxs-lookup"><span data-stu-id="d3100-210">Select `Shift`+`Enter` to select the previous or `Enter` to select the next.</span></span>  

<span data-ttu-id="d3100-211">修改查询设置：</span><span class="sxs-lookup"><span data-stu-id="d3100-211">To modify query settings:</span></span>  

*   <span data-ttu-id="d3100-212">选择 **"区分大小写** \ (![ 区分大小写 ](../media/search-case-icon.msft.png) \) "使查询区分大小写。</span><span class="sxs-lookup"><span data-stu-id="d3100-212">Choose **Case sensitive** \(![Case sensitive](../media/search-case-icon.msft.png)\) to make the query case sensitive.</span></span>  
*   <span data-ttu-id="d3100-213">Choose **Regex** \ (![ Regex ](../media/search-regex-icon.msft.png) \) to use a regular expression in your query.</span><span class="sxs-lookup"><span data-stu-id="d3100-213">Choose **Regex** \(![Regex](../media/search-regex-icon.msft.png)\) to use a regular expression in your query.</span></span>  

<span data-ttu-id="d3100-214">若要隐藏搜索框，请选择"取消 **"。**</span><span class="sxs-lookup"><span data-stu-id="d3100-214">To hide the search box, choose **Cancel**.</span></span>  

### <a name="view-main-thread-activity"></a><span data-ttu-id="d3100-215">查看主线程活动</span><span class="sxs-lookup"><span data-stu-id="d3100-215">View main thread activity</span></span>  

<span data-ttu-id="d3100-216">使用 **"主** "部分查看页面主线程上发生的活动。</span><span class="sxs-lookup"><span data-stu-id="d3100-216">Use the **Main** section to view activity that occurred on the main thread of the page.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-main-zoomed.msft.png" alt-text="主要部分" lightbox="../media/evaluate-performance-performance-main-zoomed.msft.png":::
   <span data-ttu-id="d3100-218">**主要**部分</span><span class="sxs-lookup"><span data-stu-id="d3100-218">The **Main** section</span></span>  
:::image-end:::  

<span data-ttu-id="d3100-219">在"摘要"面板中选择一个事件以查看其 **详细信息** 。</span><span class="sxs-lookup"><span data-stu-id="d3100-219">Choose an event to view more information about it in the **Summary** panel.</span></span>  <span data-ttu-id="d3100-220">DevTools 概述了选定的事件。</span><span class="sxs-lookup"><span data-stu-id="d3100-220">DevTools outlines the selected event.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-summary-me.msft.png" alt-text="有关"摘要"面板中的匿名函数详细信息" lightbox="../media/evaluate-performance-performance-summary-me.msft.png":::
   <span data-ttu-id="d3100-222">有关"摘要 `anonymous` "面板中的 **函数** 详细信息</span><span class="sxs-lookup"><span data-stu-id="d3100-222">More information about the `anonymous` function in the **Summary** panel</span></span>  
:::image-end:::  

<span data-ttu-id="d3100-223">DevTools 表示包含图表的主线程活动。</span><span class="sxs-lookup"><span data-stu-id="d3100-223">DevTools represents main thread activity with a flame chart.</span></span>  <span data-ttu-id="d3100-224">x 轴表示一段时间的录制。</span><span class="sxs-lookup"><span data-stu-id="d3100-224">The x-axis represents the recording over time.</span></span>  <span data-ttu-id="d3100-225">Y 轴表示调用堆叠。</span><span class="sxs-lookup"><span data-stu-id="d3100-225">The y-axis represents the call stack.</span></span>  <span data-ttu-id="d3100-226">顶部的事件会导致其下方的事件。</span><span class="sxs-lookup"><span data-stu-id="d3100-226">The events on top cause the events below it.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-main-flame-chart.msft.png" alt-text="柱形图" lightbox="../media/evaluate-performance-performance-main-flame-chart.msft.png":::
   <span data-ttu-id="d3100-228">柱形图</span><span class="sxs-lookup"><span data-stu-id="d3100-228">A flame chart</span></span>  
:::image-end:::  

<span data-ttu-id="d3100-229">在上图中，事件导致 第 `click` `Function Call` `activitytabs.js` 53 行中的 。</span><span class="sxs-lookup"><span data-stu-id="d3100-229">In the previous figure, a `click` event caused a `Function Call` in `activitytabs.js` on line 53.</span></span>  <span data-ttu-id="d3100-230">在下面 `Function Call` ，查看匿名函数已运行。</span><span class="sxs-lookup"><span data-stu-id="d3100-230">Below `Function Call`, review that an anonymous function was run.</span></span>  <span data-ttu-id="d3100-231">匿名函数请求 `a` ，它请求 `wait` ，它请求 `Minor GC` 。</span><span class="sxs-lookup"><span data-stu-id="d3100-231">The anonymous function requested `a`, which requested `wait`, which requested `Minor GC`.</span></span>  

<span data-ttu-id="d3100-232">DevTools 分配脚本随机颜色。</span><span class="sxs-lookup"><span data-stu-id="d3100-232">DevTools assigns scripts random colors.</span></span>  <span data-ttu-id="d3100-233">在上图中，来自一个脚本的函数请求为浅绿色。</span><span class="sxs-lookup"><span data-stu-id="d3100-233">In the previous figure, function requests from one script are colored light green.</span></span>  <span data-ttu-id="d3100-234">来自另一个脚本的请求是彩色的。</span><span class="sxs-lookup"><span data-stu-id="d3100-234">Requests from another script are colored beige.</span></span>  <span data-ttu-id="d3100-235">深黄色表示脚本活动，紫色事件表示呈现活动。</span><span class="sxs-lookup"><span data-stu-id="d3100-235">The darker yellow represents scripting activity, and the purple event represents rendering activity.</span></span>  <span data-ttu-id="d3100-236">这些较深的黄色和紫色事件在所有录制中都是一致的。</span><span class="sxs-lookup"><span data-stu-id="d3100-236">These darker yellow and purple events are consistent across all recordings.</span></span>  

<span data-ttu-id="d3100-237">如果要隐藏 [JavaScript](#disable-javascript-samples) 请求的详细隐藏图表，请导航到"禁用 JavaScript 示例"。</span><span class="sxs-lookup"><span data-stu-id="d3100-237">Navigate to [Disable JavaScript samples](#disable-javascript-samples) if you want to hide the detailed flame chart of JavaScript requests.</span></span>  <span data-ttu-id="d3100-238">禁用 JS 示例后，只显示上图中的和 `Event: choose` `Function Call` 等高级 `str` 事件。</span><span class="sxs-lookup"><span data-stu-id="d3100-238">When JS samples are disabled, only high-level events such as `Event: choose` and `Function Call` from the previous figure `str` displayed.</span></span>  

### <a name="view-activities-in-a-table"></a><span data-ttu-id="d3100-239">查看表中的活动</span><span class="sxs-lookup"><span data-stu-id="d3100-239">View activities in a table</span></span>  

<span data-ttu-id="d3100-240">录制页面后，无需仅依赖 **Main** 部分来分析活动。</span><span class="sxs-lookup"><span data-stu-id="d3100-240">After recording a page, you do not need to rely solely on the **Main** section to analyze activities.</span></span>  <span data-ttu-id="d3100-241">DevTools 还提供了三种表格视图，用于分析活动。</span><span class="sxs-lookup"><span data-stu-id="d3100-241">DevTools also provides three tabular views for analyzing activities.</span></span>  <span data-ttu-id="d3100-242">每个视图都提供对活动的不同视角：</span><span class="sxs-lookup"><span data-stu-id="d3100-242">Each view gives you a different perspective on the activities:</span></span>  

*   <span data-ttu-id="d3100-243">当要查看导致工作最多的根活动时，请使用" [呼叫树"](#the-call-tree-panel) 面板。</span><span class="sxs-lookup"><span data-stu-id="d3100-243">When you want to view the root activities that cause the most work, use the [Call Tree](#the-call-tree-panel) panel.</span></span>  
*   <span data-ttu-id="d3100-244">当要查看直接花费时间最多的活动时，请使用 ["底部向上](#the-bottom-up-panel) "面板。</span><span class="sxs-lookup"><span data-stu-id="d3100-244">When you want to view the activities where the most time was directly spent, use the [Bottom-Up](#the-bottom-up-panel) panel.</span></span>  
*   <span data-ttu-id="d3100-245">当您想要按记录期间活动发生的顺序查看活动时，请使用"事件 [日志"](#the-event-log-panel) 面板。</span><span class="sxs-lookup"><span data-stu-id="d3100-245">When you want to view the activities in the order in which they occurred during the recording, use the [Event Log](#the-event-log-panel) panel.</span></span>  
    
> [!NOTE]
> <span data-ttu-id="d3100-246">接下来的三个部分都指同一演示。</span><span class="sxs-lookup"><span data-stu-id="d3100-246">The next three sections all refer to the same demo.</span></span>  <span data-ttu-id="d3100-247">在"活动选项卡演示 ["中，自己运行演示][ActivityTabsDemo]。</span><span class="sxs-lookup"><span data-stu-id="d3100-247">Run the demo yourself at [Activity Tabs Demo][ActivityTabsDemo].</span></span>  

#### <a name="root-activities"></a><span data-ttu-id="d3100-248">根活动</span><span class="sxs-lookup"><span data-stu-id="d3100-248">Root activities</span></span>  

<span data-ttu-id="d3100-249">下面是"呼叫树"面板\*\*\*\*、"底部向上"面板和"\*\*\*\* 事件日志"面板\*\*\*\* 中提及的根活动**概念**的说明。</span><span class="sxs-lookup"><span data-stu-id="d3100-249">Here is an explanation of the **root activities** concept that is mentioned in the **Call Tree** panel, **Bottom-Up** panel, and **Event Log** panel.</span></span>  

<span data-ttu-id="d3100-250">根活动是导致浏览器执行某些工作的活动。</span><span class="sxs-lookup"><span data-stu-id="d3100-250">Root activities are those which cause the browser to do some work.</span></span>  <span data-ttu-id="d3100-251">例如，当您选择一个网页时，浏览器 `Event` 将运行一个活动作为根活动。</span><span class="sxs-lookup"><span data-stu-id="d3100-251">For example, when you choose a webpage, the browser runs an `Event` activity as the root activity.</span></span>  <span data-ttu-id="d3100-252">`Event`这可能会导致处理程序运行，等等。</span><span class="sxs-lookup"><span data-stu-id="d3100-252">That `Event` may cause a handler to run, and so on.</span></span>  

<span data-ttu-id="d3100-253">在主节的 **绘制图中，** 根活动位于图表顶部。</span><span class="sxs-lookup"><span data-stu-id="d3100-253">In the flame chart of the **Main** section, root activities are at the top of the chart.</span></span>  <span data-ttu-id="d3100-254">在 **"呼叫树** "和" **事件日志** "面板中，根活动是顶级项目。</span><span class="sxs-lookup"><span data-stu-id="d3100-254">In the **Call Tree** and **Event Log** panels, root activities are the top-level items.</span></span>  

<span data-ttu-id="d3100-255">导航到" [呼叫树](#the-call-tree-panel) "面板，查看根活动的示例。</span><span class="sxs-lookup"><span data-stu-id="d3100-255">Navigate to the [Call Tree](#the-call-tree-panel) panel for an example of root activities.</span></span>  

#### <a name="the-call-tree-panel"></a><span data-ttu-id="d3100-256">呼叫树面板</span><span class="sxs-lookup"><span data-stu-id="d3100-256">The Call Tree panel</span></span>  

<span data-ttu-id="d3100-257">使用 **"呼叫树** "面板查看 [哪些根活动](#root-activities) 导致工作最多。</span><span class="sxs-lookup"><span data-stu-id="d3100-257">Use the **Call Tree** panel to view which [root activities](#root-activities) cause the most work.</span></span>  

<span data-ttu-id="d3100-258">" **呼叫树** "面板仅显示在录制的选定部分期间的活动。</span><span class="sxs-lookup"><span data-stu-id="d3100-258">The **Call Tree** panel only displays activities during the selected portion of the recording.</span></span>  <span data-ttu-id="d3100-259">导航 [到"选择录音的一部分](#select-a-portion-of-a-recording) "，了解如何选择部分。</span><span class="sxs-lookup"><span data-stu-id="d3100-259">Navigate to [Select a portion of a recording](#select-a-portion-of-a-recording) to learn how to select portions.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-call-tree.msft.png" alt-text="呼叫树面板" lightbox="../media/evaluate-performance-performance-call-tree.msft.png":::
   <span data-ttu-id="d3100-261">呼叫 **树** 面板</span><span class="sxs-lookup"><span data-stu-id="d3100-261">The **Call Tree** panel</span></span>  
:::image-end:::  

<span data-ttu-id="d3100-262">在上图中，"活动"列中的顶级项目（如\*\*\*\* 和 `Evaluate Script` `Parse HTML` ）是根活动。</span><span class="sxs-lookup"><span data-stu-id="d3100-262">In the previous figure, the top-level of items in the **Activity** column, such as `Evaluate Script` and `Parse HTML` are root activities.</span></span>  <span data-ttu-id="d3100-263">嵌套表示调用堆栈。</span><span class="sxs-lookup"><span data-stu-id="d3100-263">The nesting represents the call stack.</span></span>  <span data-ttu-id="d3100-264">例如，在上图中 `Parse HTML` ，它导致了 和 `Evaluate Script` `Compile Script` `(anonymous)` 。</span><span class="sxs-lookup"><span data-stu-id="d3100-264">For example, in the previous figure, `Parse HTML` which caused `Evaluate Script` which caused `Compile Script` and `(anonymous)`.</span></span>  

<span data-ttu-id="d3100-265">**Self Time** 表示直接在活动上花费的时间。</span><span class="sxs-lookup"><span data-stu-id="d3100-265">**Self Time** represents the time directly spent in that activity.</span></span>  <span data-ttu-id="d3100-266">**"总** 时间"表示该活动或任何子活动所花费的时间。</span><span class="sxs-lookup"><span data-stu-id="d3100-266">**Total Time** represents the time spent in that activity or any of the children.</span></span>  

<span data-ttu-id="d3100-267">选择 **"自时间\*\*\*\*"、"总**时间 **"或"活动**"按该列对表进行排序。</span><span class="sxs-lookup"><span data-stu-id="d3100-267">Choose **Self Time**, **Total Time**, or **Activity** to sort the table by that column.</span></span>  

<span data-ttu-id="d3100-268">使用 **"筛选器** "文本框按活动名称筛选事件。</span><span class="sxs-lookup"><span data-stu-id="d3100-268">Use the **Filter** text box to filter events by activity name.</span></span>  

<span data-ttu-id="d3100-269">默认情况下 **，"分组"** 菜单设置为"**无分组"。**</span><span class="sxs-lookup"><span data-stu-id="d3100-269">By default the **Grouping** menu is set to **No Grouping**.</span></span>  <span data-ttu-id="d3100-270">使用 **"分组"** 菜单根据各种条件对活动表进行排序。</span><span class="sxs-lookup"><span data-stu-id="d3100-270">Use the **Grouping** menu to sort the activity table based on various criteria.</span></span>  

<span data-ttu-id="d3100-271">Choose **Show Heaviest Stack** \ (Show ![ Heaviest Stack ](../media/show-heaviest-stack-icon.msft.png) \) to reveal another table to the right of the **Activity** table.</span><span class="sxs-lookup"><span data-stu-id="d3100-271">Choose **Show Heaviest Stack** \(![Show Heaviest Stack](../media/show-heaviest-stack-icon.msft.png)\) to reveal another table to the right of the **Activity** table.</span></span>  <span data-ttu-id="d3100-272">选择一个活动以填充 **最重的 Stack** 表。</span><span class="sxs-lookup"><span data-stu-id="d3100-272">Choose an activity to populate the **Heaviest Stack** table.</span></span>  <span data-ttu-id="d3100-273">The **Heaviest Stack** table displays which children of the selected activity took the longest time to run.</span><span class="sxs-lookup"><span data-stu-id="d3100-273">The **Heaviest Stack** table displays which children of the selected activity took the longest time to run.</span></span>  

#### <a name="the-bottom-up-panel"></a><span data-ttu-id="d3100-274">"Bottom-Up面板</span><span class="sxs-lookup"><span data-stu-id="d3100-274">The Bottom-Up panel</span></span>  

<span data-ttu-id="d3100-275">使用 **"底部向上"** 面板查看哪些活动在聚合中直接时间最多。</span><span class="sxs-lookup"><span data-stu-id="d3100-275">Use the **Bottom-Up** panel to view which activities directly took up the most time in aggregate.</span></span>  

<span data-ttu-id="d3100-276">The **Bottom-Up** panel only displays activities during the selected portion of the recording.</span><span class="sxs-lookup"><span data-stu-id="d3100-276">The **Bottom-Up** panel only displays activities during the selected portion of the recording.</span></span>  <span data-ttu-id="d3100-277">导航 [到"选择录音的一部分](#select-a-portion-of-a-recording) "，了解如何选择部分。</span><span class="sxs-lookup"><span data-stu-id="d3100-277">Navigate to [Select a portion of a recording](#select-a-portion-of-a-recording) to learn how to select portions.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-bottoms-up.msft.png" alt-text=""Bottom-Up面板" lightbox="../media/evaluate-performance-performance-bottoms-up.msft.png":::
   <span data-ttu-id="d3100-279">从**下向上面板**</span><span class="sxs-lookup"><span data-stu-id="d3100-279">The **Bottom-Up** panel</span></span>  
:::image-end:::  

<span data-ttu-id="d3100-280">在上 **图** 的主节绘制图中，导航到几乎所有运行所花的时间 `Parse HTML` 。</span><span class="sxs-lookup"><span data-stu-id="d3100-280">In the **Main** section flame chart of the previous figure, navigate to that almost practically all of the time was spent running `Parse HTML`.</span></span>  <span data-ttu-id="d3100-281">上图的 **"底部向上"** 面板中的顶部活动是 `Parse HTML` 。</span><span class="sxs-lookup"><span data-stu-id="d3100-281">The top activity in the **Bottom-Up** panel of the previous figure is `Parse HTML`.</span></span>  <!--In the flame chart of the previous figure, the yellow below the calls to `wait` are actually thousands of `Minor GC` calls.  -->  <span data-ttu-id="d3100-282">导航到 **"底部向上"面板** ，下一个成本最大的活动是 `Layout` 。</span><span class="sxs-lookup"><span data-stu-id="d3100-282">Navigate to the **Bottom-Up** panel, the next most expensive activity is `Layout`.</span></span>  

<span data-ttu-id="d3100-283">" **自时间** "列表示直接在活动（在所有事件之间）花费的聚合时间。</span><span class="sxs-lookup"><span data-stu-id="d3100-283">The **Self Time** column represents the aggregated time spent directly in that activity, across all of the occurrences.</span></span>  

<span data-ttu-id="d3100-284">" **总时间** "列表示该活动或任何子活动所花费的聚合时间。</span><span class="sxs-lookup"><span data-stu-id="d3100-284">The **Total Time** column represents aggregated time spent in that activity or any of the children.</span></span>  

#### <a name="the-event-log-panel"></a><span data-ttu-id="d3100-285">"事件日志"面板</span><span class="sxs-lookup"><span data-stu-id="d3100-285">The Event Log panel</span></span>  

<span data-ttu-id="d3100-286">使用 **"事件** 日志"面板以记录期间活动发生的顺序查看活动。</span><span class="sxs-lookup"><span data-stu-id="d3100-286">Use the **Event Log** panel to view activities in the order in which they occurred during the recording.</span></span>  

<span data-ttu-id="d3100-287">" **事件日志** "面板仅显示在记录的选定部分期间的活动。</span><span class="sxs-lookup"><span data-stu-id="d3100-287">The **Event Log** panel only displays activities during the selected portion of the recording.</span></span>  <span data-ttu-id="d3100-288">导航 [到"选择录音的一部分](#select-a-portion-of-a-recording) "，了解如何选择部分。</span><span class="sxs-lookup"><span data-stu-id="d3100-288">Navigate to [Select a portion of a recording](#select-a-portion-of-a-recording) to learn how to select portions.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-event-log.msft.png" alt-text=""事件日志"面板" lightbox="../media/evaluate-performance-performance-event-log.msft.png":::
   <span data-ttu-id="d3100-290">" **事件日志"** 面板</span><span class="sxs-lookup"><span data-stu-id="d3100-290">The **Event Log** panel</span></span>  
:::image-end:::  

<span data-ttu-id="d3100-291">" **开始时间** "列表示该活动的开始点（相对于录制的开始位置）。</span><span class="sxs-lookup"><span data-stu-id="d3100-291">The **Start Time** column represents the point at which that activity started, relative to the start of the recording.</span></span>  <span data-ttu-id="d3100-292">例如，上图中选定项目的开始时间意味着活动在 `175.7 ms` 录制开始后 175.7 毫秒开始。</span><span class="sxs-lookup"><span data-stu-id="d3100-292">For example, the start time of `175.7 ms` for the selected item in the previous figure means that activity started 175.7 ms after the recording started.</span></span>  

<span data-ttu-id="d3100-293">" **自时间** "列表示直接在活动上花费的时间。</span><span class="sxs-lookup"><span data-stu-id="d3100-293">The **Self Time** column represents the time spent directly in that activity.</span></span>  

<span data-ttu-id="d3100-294">" **总时间** "列表示直接用于该活动或任何子活动的时间。</span><span class="sxs-lookup"><span data-stu-id="d3100-294">The **Total Time** columns represents time spent directly in that activity or in any of the children.</span></span>  

<span data-ttu-id="d3100-295">选择 **"开始时间"、"** 开始时间"**或"** 总时间"按该列对表进行排序。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="d3100-295">Choose **Start Time**, **Self Time**, or **Total Time** to sort the table by that column.</span></span>

<span data-ttu-id="d3100-296">使用" **筛选器** "文本框按名称筛选活动。</span><span class="sxs-lookup"><span data-stu-id="d3100-296">Use the **Filter** text box to filter activities by name.</span></span>  

<span data-ttu-id="d3100-297">使用" **持续时间** "菜单筛选出时间少于 1 毫秒或 15 毫秒的任何活动。</span><span class="sxs-lookup"><span data-stu-id="d3100-297">Use the **Duration** menu to filter out any activities that took less than 1 ms or 15 ms.</span></span>  <span data-ttu-id="d3100-298">默认情况下 **，"持续时间"** 菜单设置为 **"** 全部"，这意味着将显示所有活动。</span><span class="sxs-lookup"><span data-stu-id="d3100-298">By default the **Duration** menu is set to **All**, meaning all activities are shown.</span></span>  

<span data-ttu-id="d3100-299">禁用 **"加载**、**脚本、** 呈现\*\*\*\* 或**绘制**"复选框以筛选掉这些类别中的所有活动。</span><span class="sxs-lookup"><span data-stu-id="d3100-299">Disable the **Loading**, **Scripting**, **Rendering**, or **Painting** checkboxes to filter out all activities from those categories.</span></span>  

### <a name="view-gpu-activity"></a><span data-ttu-id="d3100-300">查看 GPU 活动</span><span class="sxs-lookup"><span data-stu-id="d3100-300">View GPU activity</span></span>  

<span data-ttu-id="d3100-301">在 GPU 部分查看 **GPU** 活动。</span><span class="sxs-lookup"><span data-stu-id="d3100-301">View GPU activity in the **GPU** section.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-gpu-zoomed.msft.png" alt-text="GPU 部分" lightbox="../media/evaluate-performance-performance-gpu-zoomed.msft.png":::
   <span data-ttu-id="d3100-303">**GPU**部分</span><span class="sxs-lookup"><span data-stu-id="d3100-303">The **GPU** section</span></span>  
:::image-end:::  

### <a name="view-raster-activity"></a><span data-ttu-id="d3100-304">查看栅格活动</span><span class="sxs-lookup"><span data-stu-id="d3100-304">View raster activity</span></span>  

<span data-ttu-id="d3100-305">查看 **"Raster"部分中的"Raster"** 活动。</span><span class="sxs-lookup"><span data-stu-id="d3100-305">View raster activity in the **Raster** section.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-raster.msft.png" alt-text=""Raster"部分" lightbox="../media/evaluate-performance-performance-raster.msft.png":::
   <span data-ttu-id="d3100-307">**"Raster"** 部分</span><span class="sxs-lookup"><span data-stu-id="d3100-307">The **Raster** section</span></span>  
:::image-end:::  

### <a name="view-interactions"></a><span data-ttu-id="d3100-308">查看交互</span><span class="sxs-lookup"><span data-stu-id="d3100-308">View interactions</span></span>  

<span data-ttu-id="d3100-309">使用 **"交互"** 部分查找和分析在录制过程中发生的用户交互。</span><span class="sxs-lookup"><span data-stu-id="d3100-309">Use the **Interactions** section to find and analyze user interactions that happened during the recording.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-interactions-animation.msft.png" alt-text=""交互"部分" lightbox="../media/evaluate-performance-performance-interactions-animation.msft.png":::
   <span data-ttu-id="d3100-311">" **交互"** 部分</span><span class="sxs-lookup"><span data-stu-id="d3100-311">The **Interactions** section</span></span>  
:::image-end:::  

<span data-ttu-id="d3100-312">交互底部的红线表示等待主线程所花的时间。</span><span class="sxs-lookup"><span data-stu-id="d3100-312">A red line at the bottom of an interaction represents time spent waiting for the main thread.</span></span>  

<span data-ttu-id="d3100-313">在"摘要"面板中选择一个交互以查看其 **详细信息** 。</span><span class="sxs-lookup"><span data-stu-id="d3100-313">Choose an interaction to view more information about it in the **Summary** panel.</span></span>  

### <a name="analyze-frames-per-second-fps"></a><span data-ttu-id="d3100-314">分析每秒帧数 (FPS) </span><span class="sxs-lookup"><span data-stu-id="d3100-314">Analyze frames per second (FPS)</span></span>  

<span data-ttu-id="d3100-315">DevTools 提供了多种分析每秒帧的方法：</span><span class="sxs-lookup"><span data-stu-id="d3100-315">DevTools provides numerous ways to analyze frames per second:</span></span>  

*   <span data-ttu-id="d3100-316">使用 [FPS 图表](#the-fps-chart) 获取录制持续时间内 FPS 的概述。</span><span class="sxs-lookup"><span data-stu-id="d3100-316">Use [the FPS chart](#the-fps-chart) to get an overview of FPS over the duration of the recording.</span></span>  
*   <span data-ttu-id="d3100-317">使用 ["框架"](#the-frames-section) 部分查看特定帧所间隔的时间。</span><span class="sxs-lookup"><span data-stu-id="d3100-317">Use [the Frames section](#the-frames-section) to view how long a particular frame took.</span></span>  
*   <span data-ttu-id="d3100-318">在页面 **运行时，使用 FPS** 指示器实时估计 FPS。</span><span class="sxs-lookup"><span data-stu-id="d3100-318">Use the **FPS meter** for a realtime estimate of FPS as the page runs.</span></span>  <span data-ttu-id="d3100-319">导航到 [使用 FPS 指示器实时查看每秒帧数](#view-frames-per-second-in-realtime-with-the-fps-meter)。</span><span class="sxs-lookup"><span data-stu-id="d3100-319">Navigate to [View frames per second in realtime with the FPS meter](#view-frames-per-second-in-realtime-with-the-fps-meter).</span></span>  
    
#### <a name="the-fps-chart"></a><span data-ttu-id="d3100-320">FPS 图表</span><span class="sxs-lookup"><span data-stu-id="d3100-320">The FPS chart</span></span>  

<span data-ttu-id="d3100-321">**FPS**图表概述了录音持续时间中的帧速率。</span><span class="sxs-lookup"><span data-stu-id="d3100-321">The **FPS** chart provides an overview of the frame rate across the duration of a recording.</span></span>  <span data-ttu-id="d3100-322">通常，绿色条形越高，帧速率越好。</span><span class="sxs-lookup"><span data-stu-id="d3100-322">In general, the higher the green bar, the better the frame rate.</span></span>  

<span data-ttu-id="d3100-323">FPS 图表上方\*\*\*\* 的红色条是一条警告，指出帧速率下降得过低，可能损害用户体验。</span><span class="sxs-lookup"><span data-stu-id="d3100-323">A red bar above the **FPS** chart is a warning that the frame rate dropped so low that it probably harmed the user's experience.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-fps-highlight.msft.png" alt-text="FPS 图表" lightbox="../media/evaluate-performance-performance-fps-highlight.msft.png":::
   <span data-ttu-id="d3100-325">**FPS** 图表</span><span class="sxs-lookup"><span data-stu-id="d3100-325">The **FPS** chart</span></span>  
:::image-end:::  

#### <a name="the-frames-section"></a><span data-ttu-id="d3100-326">框架部分</span><span class="sxs-lookup"><span data-stu-id="d3100-326">The Frames section</span></span>  

<span data-ttu-id="d3100-327">帧 **部分** 会告知你特定帧所使用时间。</span><span class="sxs-lookup"><span data-stu-id="d3100-327">The **Frames** section tells you exactly how long a particular frame took.</span></span>  

<span data-ttu-id="d3100-328">将鼠标悬停在框架上，查看工具提示，详细了解它。</span><span class="sxs-lookup"><span data-stu-id="d3100-328">Hover on a frame to view a tooltip with more information about it.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-frames-hover.msft.png" alt-text="鼠标悬停在框架上" lightbox="../media/evaluate-performance-performance-frames-hover.msft.png":::
   <span data-ttu-id="d3100-330">鼠标悬停在框架上</span><span class="sxs-lookup"><span data-stu-id="d3100-330">Hover on a frame</span></span>  
:::image-end:::  

<span data-ttu-id="d3100-331">在摘要面板中选择一个帧以查看有关 **帧详细信息** 。</span><span class="sxs-lookup"><span data-stu-id="d3100-331">Choose a frame to view more information about the frame in the **Summary** panel.</span></span>  <span data-ttu-id="d3100-332">DevTools 将所选框架分级为蓝色。</span><span class="sxs-lookup"><span data-stu-id="d3100-332">DevTools outlines the selected frame in blue.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-frames-summary.msft.png" alt-text="在摘要面板中查看帧" lightbox="../media/evaluate-performance-performance-frames-summary.msft.png":::
   <span data-ttu-id="d3100-334">在摘要面板 **中查看** 帧</span><span class="sxs-lookup"><span data-stu-id="d3100-334">View a frame in the **Summary** panel</span></span>  
:::image-end:::  

### <a name="view-network-requests"></a><span data-ttu-id="d3100-335">查看网络请求</span><span class="sxs-lookup"><span data-stu-id="d3100-335">View network requests</span></span>  

<span data-ttu-id="d3100-336">展开 **"网络** "部分以查看记录期间发生的网络请求的瀑布。</span><span class="sxs-lookup"><span data-stu-id="d3100-336">Expand the **Network** section to view a waterfall of network requests that occurred during the recording.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-network.msft.png" alt-text=""网络"部分" lightbox="../media/evaluate-performance-performance-network.msft.png":::
   <span data-ttu-id="d3100-338">" **网络"** 部分</span><span class="sxs-lookup"><span data-stu-id="d3100-338">The **Network** section</span></span>  
:::image-end:::  

<span data-ttu-id="d3100-339">请求按如下方式进行颜色编码：</span><span class="sxs-lookup"><span data-stu-id="d3100-339">Requests are color-coded as follows:</span></span>  

*   <span data-ttu-id="d3100-340">HTML：蓝色</span><span class="sxs-lookup"><span data-stu-id="d3100-340">HTML: Blue</span></span>  
*   <span data-ttu-id="d3100-341">CSS：紫色</span><span class="sxs-lookup"><span data-stu-id="d3100-341">CSS: Purple</span></span>  
*   <span data-ttu-id="d3100-342">JS：Yellow</span><span class="sxs-lookup"><span data-stu-id="d3100-342">JS: Yellow</span></span>  
*   <span data-ttu-id="d3100-343">图像：绿色</span><span class="sxs-lookup"><span data-stu-id="d3100-343">Images: Green</span></span>  
    
<span data-ttu-id="d3100-344">在"摘要"面板中选择一个请求以查看其 **详细信息** 。</span><span class="sxs-lookup"><span data-stu-id="d3100-344">Choose a request to view more information about it in the **Summary** panel.</span></span>  <span data-ttu-id="d3100-345">例如，在上图中，"摘要"\*\*\*\* 面板显示有关在"网络"部分选择的蓝色**请求详细信息。**</span><span class="sxs-lookup"><span data-stu-id="d3100-345">For example, in the previous figure, the **Summary** panel is displaying more information about the blue request that is selected in the **Network** section.</span></span>  

<span data-ttu-id="d3100-346">请求左上方的深蓝色正方形表示它是优先级较高的请求。</span><span class="sxs-lookup"><span data-stu-id="d3100-346">A darker-blue square in the top-left of a request means it is a higher-priority request.</span></span>  <span data-ttu-id="d3100-347">浅蓝色正方形表示较低的优先级。</span><span class="sxs-lookup"><span data-stu-id="d3100-347">A lighter-blue square means lower-priority.</span></span>  <span data-ttu-id="d3100-348">例如，在上图中，蓝色选定请求的优先级更高，而其下方的绿色请求优先级较低。</span><span class="sxs-lookup"><span data-stu-id="d3100-348">For example, in the previous figure, the blue, selected request is higher-priority, and the green one below it is lower-priority.</span></span>  

<span data-ttu-id="d3100-349">在下图的第 1 部分中，请求表示为 左侧的行、中间带深色部分的条形和浅色部分，以及右边的 `www.bing.com` 线条。</span><span class="sxs-lookup"><span data-stu-id="d3100-349">In the 1st of the following figures, the request for `www.bing.com` is represented by a line on the left, a bar in the middle with a dark portion and a light portion, and a line on the right.</span></span>  <span data-ttu-id="d3100-350">在下图的第 2 个中，显示了"网络"工具的"计时"\*\*\*\* 面板中相同请求的相应**表示**形式。</span><span class="sxs-lookup"><span data-stu-id="d3100-350">In the 2nd of the following figures shows the corresponding representation of the same request in the **Timing** panel of the **Network** tool.</span></span>  <span data-ttu-id="d3100-351">下面说明这两种表示形式如何相互映射：</span><span class="sxs-lookup"><span data-stu-id="d3100-351">Here is how these two representations map to each other:</span></span>

*   <span data-ttu-id="d3100-352">左边行是事件组 `Connection Start` （包括这组事件）的所有内容。</span><span class="sxs-lookup"><span data-stu-id="d3100-352">The left line is everything up to the `Connection Start` group of events, inclusive.</span></span>  <span data-ttu-id="d3100-353">换句话说，它是之前的所有内容， `Request Sent` 不包括 。</span><span class="sxs-lookup"><span data-stu-id="d3100-353">In other words, it is everything before `Request Sent`, exclusive.</span></span>  
*   <span data-ttu-id="d3100-354">栏的光线部分为 `Request Sent` 和 `Waiting (TTFB)` 。</span><span class="sxs-lookup"><span data-stu-id="d3100-354">The light portion of the bar is `Request Sent` and `Waiting (TTFB)`.</span></span>  
*   <span data-ttu-id="d3100-355">该栏的深色部分是 `Content Download` 。</span><span class="sxs-lookup"><span data-stu-id="d3100-355">The dark portion of the bar is `Content Download`.</span></span>  
*   <span data-ttu-id="d3100-356">正确的行实质上是等待主线程所花的时间。</span><span class="sxs-lookup"><span data-stu-id="d3100-356">The right line is essentially time spent waiting for the main thread.</span></span>  <span data-ttu-id="d3100-357">"计时"面板中未 **显示** 此行为。</span><span class="sxs-lookup"><span data-stu-id="d3100-357">This is not represented in the **Timing** panel.</span></span>  
    
:::row:::
   :::column span="":::
      :::image type="complex" source="../media/evaluate-performance-bing-performance-network.msft.png" alt-text="请求的线 www.bing.com 表示" lightbox="../media/evaluate-performance-bing-performance-network.msft.png":::
         <span data-ttu-id="d3100-359">请求的线栏 `www.bing.com` 表示形式</span><span class="sxs-lookup"><span data-stu-id="d3100-359">The line-bar representation of the `www.bing.com` request</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/evaluate-performance-bing-network-timing.msft.png" alt-text="网络工具" lightbox="../media/evaluate-performance-bing-network-timing.msft.png":::
         <span data-ttu-id="d3100-361">网络**工具**</span><span class="sxs-lookup"><span data-stu-id="d3100-361">The **Network** tool</span></span>  
<span data-ttu-id="d3100-362">： ：：image-end：：：</span><span class="sxs-lookup"><span data-stu-id="d3100-362">:     ::image-end:::</span></span>  
   :::column-end:::
:::row-end:::

### <a name="view-memory-metrics"></a><span data-ttu-id="d3100-363">查看内存指标</span><span class="sxs-lookup"><span data-stu-id="d3100-363">View memory metrics</span></span>  

<span data-ttu-id="d3100-364">打开" **内存"** 复选框以查看上一次录制中的内存指标。</span><span class="sxs-lookup"><span data-stu-id="d3100-364">Turn on the **Memory** checkbox to view memory metrics from the last recording.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-memory-highlight.msft.png" alt-text=""内存"复选框" lightbox="../media/evaluate-performance-performance-memory-highlight.msft.png":::
   <span data-ttu-id="d3100-366">" **内存"** 复选框</span><span class="sxs-lookup"><span data-stu-id="d3100-366">The **Memory** checkbox</span></span>  
:::image-end:::  

<span data-ttu-id="d3100-367">DevTools 在摘要 **面板** 上方显示新的 **内存** 图表。</span><span class="sxs-lookup"><span data-stu-id="d3100-367">DevTools displays a new **Memory** chart, above the **Summary** panel.</span></span>  <span data-ttu-id="d3100-368">NET 图表下方还有一**个新的图表，** 称为**HEAP。**</span><span class="sxs-lookup"><span data-stu-id="d3100-368">There is also a new chart below the **NET** chart, called **HEAP**.</span></span>  <span data-ttu-id="d3100-369">**HEAP**图表提供的信息与"内存"图表中**的 JS 堆\*\*\*\*行相同**。</span><span class="sxs-lookup"><span data-stu-id="d3100-369">The **HEAP** chart provides the same information as the **JS Heap** line in the **Memory** chart.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-memory-chart.msft.png" alt-text="内存指标" lightbox="../media/evaluate-performance-performance-memory-chart.msft.png":::
   <span data-ttu-id="d3100-371">内存指标</span><span class="sxs-lookup"><span data-stu-id="d3100-371">Memory metrics</span></span>  
:::image-end:::  

<span data-ttu-id="d3100-372">图表上的彩色线条映射到图表上方的彩色复选框。</span><span class="sxs-lookup"><span data-stu-id="d3100-372">The colored lines on the chart map to the colored checkboxes above the chart.</span></span>  
<span data-ttu-id="d3100-373">禁用复选框以在图表中隐藏该类别。</span><span class="sxs-lookup"><span data-stu-id="d3100-373">Disable a checkbox to hide that category from the chart.</span></span>  

<span data-ttu-id="d3100-374">该图表仅显示当前选中的录制区域。</span><span class="sxs-lookup"><span data-stu-id="d3100-374">The chart only displays the region of the recording that is currently selected.</span></span>  <span data-ttu-id="d3100-375">例如，在上图中，"内存"\*\*\*\* 图表只显示从 400 毫秒标记到 1750 毫秒标记周围的内存使用量。</span><span class="sxs-lookup"><span data-stu-id="d3100-375">For example, in the previous figure, the **Memory** chart is only showing memory usage from around the 400 ms mark to the 1750 ms mark.</span></span>  

### <a name="view-the-duration-of-a-portion-of-a-recording"></a><span data-ttu-id="d3100-376">查看录制的一部分的持续时间</span><span class="sxs-lookup"><span data-stu-id="d3100-376">View the duration of a portion of a recording</span></span>  

<span data-ttu-id="d3100-377">分析网络或**主\*\*\*\*等**部分时，有时你需要更精确地估计特定事件所经过的。</span><span class="sxs-lookup"><span data-stu-id="d3100-377">When analyzing a section like **Network** or **Main**, sometimes you need a more precise estimate of how long certain events took.</span></span>  <span data-ttu-id="d3100-378">按住 `Shift` 、选择并按住，然后向左或向右拖动以选择录音的一部分。</span><span class="sxs-lookup"><span data-stu-id="d3100-378">Hold `Shift`, choose and hold, and drag left or right to select a portion of the recording.</span></span>  <span data-ttu-id="d3100-379">在选择的底部，DevTools 显示该部分所用时间。</span><span class="sxs-lookup"><span data-stu-id="d3100-379">At the bottom of your selection, DevTools shows how long that portion took.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-main-duration.msft.png" alt-text="查看录制的一部分的持续时间" lightbox="../media/evaluate-performance-performance-main-duration.msft.png":::
   <span data-ttu-id="d3100-381">查看录制的一部分的持续时间</span><span class="sxs-lookup"><span data-stu-id="d3100-381">View the duration of a portion of a recording</span></span>  
:::image-end:::  

### <a name="view-a-screenshot"></a><span data-ttu-id="d3100-382">查看屏幕截图</span><span class="sxs-lookup"><span data-stu-id="d3100-382">View a screenshot</span></span>  

<span data-ttu-id="d3100-383">导航到 [录制时捕获](#capture-screenshots-while-recording) 屏幕截图，了解如何打开屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="d3100-383">Navigate to [Capture screenshots while recording](#capture-screenshots-while-recording) to learn how to turn on screenshots.</span></span>  

<span data-ttu-id="d3100-384">将鼠标 **悬停在"概述** "上可查看该页面在录制期间的外观的屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="d3100-384">Hover on the **Overview** to view a screenshot of how the page looked during that moment of the recording.</span></span>  <span data-ttu-id="d3100-385">概述**是**包含 CPU、FPS\*\*\*\* 和\*\*\*\* **NET**图表的部分。</span><span class="sxs-lookup"><span data-stu-id="d3100-385">The **Overview** is the section that contains the **CPU**, **FPS**, and **NET** charts.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-screenshots-hover.msft.png" alt-text="查看屏幕截图" lightbox="../media/evaluate-performance-performance-screenshots-hover.msft.png":::
   <span data-ttu-id="d3100-387">查看屏幕截图</span><span class="sxs-lookup"><span data-stu-id="d3100-387">View a screenshot</span></span>  
:::image-end:::  

<span data-ttu-id="d3100-388">您还可以通过选择"框架"部分中的图文 **框** 来查看屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="d3100-388">You may also view screenshots by choosing a frame in the **Frames** section.</span></span>  <span data-ttu-id="d3100-389">DevTools 在摘要面板中显示屏幕截图 **的小** 版本。</span><span class="sxs-lookup"><span data-stu-id="d3100-389">DevTools displays a small version of the screenshot in the **Summary** panel.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-summary-preview.msft.png" alt-text="在摘要面板中查看屏幕截图" lightbox="../media/evaluate-performance-performance-summary-preview.msft.png":::
   <span data-ttu-id="d3100-391">在摘要面板**中查看屏幕截图**</span><span class="sxs-lookup"><span data-stu-id="d3100-391">View a screenshot in the **Summary** panel</span></span>  
:::image-end:::  

<span data-ttu-id="d3100-392">在"摘要" **面板中选择缩略图** 以放大屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="d3100-392">Choose the thumbnail in the **Summary** panel to zoom in on the screenshot.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-summary-preview-select.msft.png" alt-text="从摘要面板放大屏幕截图" lightbox="../media/evaluate-performance-performance-summary-preview-select.msft.png":::
   <span data-ttu-id="d3100-394">从摘要面板放大**屏幕截图**</span><span class="sxs-lookup"><span data-stu-id="d3100-394">Zoom into a screenshot from the **Summary** panel</span></span>  
:::image-end:::  

### <a name="view-layers-information"></a><span data-ttu-id="d3100-395">查看图层信息</span><span class="sxs-lookup"><span data-stu-id="d3100-395">View layers information</span></span>  

<span data-ttu-id="d3100-396">查看有关帧的高级层信息：</span><span class="sxs-lookup"><span data-stu-id="d3100-396">To view advanced layers information about a frame:</span></span>  

1.  <span data-ttu-id="d3100-397">[打开高级画图检测](#turn-on-advanced-paint-instrumentation)。</span><span class="sxs-lookup"><span data-stu-id="d3100-397">[Turn on advanced paint instrumentation](#turn-on-advanced-paint-instrumentation).</span></span>  
1.  <span data-ttu-id="d3100-398">选择"框架" **部分中的** 框架。</span><span class="sxs-lookup"><span data-stu-id="d3100-398">Choose a frame in the **Frames** section.</span></span>  <span data-ttu-id="d3100-399">DevTools 在"事件日志"面板旁\*\*\*\* 的新"层"面板中显示有关**图层**的信息。</span><span class="sxs-lookup"><span data-stu-id="d3100-399">DevTools displays information about the layers in the new **Layers** panel, next to the **Event Log** panel.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-layers-all.msft.png" alt-text=""层"窗格" lightbox="../media/evaluate-performance-layers-all.msft.png":::
       <span data-ttu-id="d3100-401">" **层"** 窗格</span><span class="sxs-lookup"><span data-stu-id="d3100-401">The **Layers** pane</span></span>  
    :::image-end:::  
    
<span data-ttu-id="d3100-402">将鼠标悬停在图层上以在图表中突出显示它。</span><span class="sxs-lookup"><span data-stu-id="d3100-402">Hover on a layer to highlight it in the diagram.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-frames-document-nav-bar-highlighted.msft.png" alt-text="突出显示图层" lightbox="../media/evaluate-performance-performance-frames-document-nav-bar-highlighted.msft.png":::
   <span data-ttu-id="d3100-404">突出显示图层</span><span class="sxs-lookup"><span data-stu-id="d3100-404">Highlight a layer</span></span>  
:::image-end:::  

<span data-ttu-id="d3100-405">移动图表：</span><span class="sxs-lookup"><span data-stu-id="d3100-405">To move the diagram:</span></span>  

*   <span data-ttu-id="d3100-406">选择 **平移模式** \ (![ 平移模式 ](../media/pan-mode-icon.msft.png) \) 沿 X 和 Y 轴移动。</span><span class="sxs-lookup"><span data-stu-id="d3100-406">Choose **Pan Mode** \(![Pan Mode](../media/pan-mode-icon.msft.png)\) to move along the X and Y axes.</span></span>  
*   <span data-ttu-id="d3100-407">选择 **旋转模式** \ (![ 旋转模式 ](../media/rotate-mode-icon.msft.png) \) 沿 Z 轴旋转。</span><span class="sxs-lookup"><span data-stu-id="d3100-407">Choose **Rotate Mode** \(![Rotate Mode](../media/rotate-mode-icon.msft.png)\) to rotate along the Z axis.</span></span>  
*   <span data-ttu-id="d3100-408">Choose **Reset Transform** \ (Reset Transform ![ ](../media/reset-transform-icon.msft.png) \) to reset the diagram to the original position.</span><span class="sxs-lookup"><span data-stu-id="d3100-408">Choose **Reset Transform** \(![Reset Transform](../media/reset-transform-icon.msft.png)\) to reset the diagram to the original position.</span></span>  
    
### <a name="view-paint-profiler"></a><span data-ttu-id="d3100-409">查看画图探查器</span><span class="sxs-lookup"><span data-stu-id="d3100-409">View paint profiler</span></span>  

<span data-ttu-id="d3100-410">查看有关绘制事件的高级信息：</span><span class="sxs-lookup"><span data-stu-id="d3100-410">To view advanced information about a paint event:</span></span>  

1.  <span data-ttu-id="d3100-411">[打开 。](#turn-on-advanced-paint-instrumentation)</span><span class="sxs-lookup"><span data-stu-id="d3100-411">[Turn on](#turn-on-advanced-paint-instrumentation).</span></span>  
1.  <span data-ttu-id="d3100-412">在" **主"** 部分选择 **"绘制"** 事件。</span><span class="sxs-lookup"><span data-stu-id="d3100-412">Choose a **Paint** event in the **Main** section.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-paint-profiler.msft.png" alt-text="画图探查器面板" lightbox="../media/evaluate-performance-paint-profiler.msft.png":::
       <span data-ttu-id="d3100-414">画 **图探查器** 面板</span><span class="sxs-lookup"><span data-stu-id="d3100-414">The **Paint Profiler** panel</span></span>  
    :::image-end:::  
    
## <a name="analyze-rendering-performance-with-the-rendering-tool"></a><span data-ttu-id="d3100-415">使用呈现工具分析呈现性能</span><span class="sxs-lookup"><span data-stu-id="d3100-415">Analyze rendering performance with the Rendering tool</span></span>  

<span data-ttu-id="d3100-416">使用"呈现" **面板的功能** 帮助可视化页面的呈现性能。</span><span class="sxs-lookup"><span data-stu-id="d3100-416">Use the features of the **Rendering** panel to help visualize the rendering performance of your page.</span></span>  

<span data-ttu-id="d3100-417">打开呈现 **工具** ：</span><span class="sxs-lookup"><span data-stu-id="d3100-417">To open the **Rendering** tool:</span></span>  

1.  <span data-ttu-id="d3100-418">[打开命令菜单][DevToolsCommandMenu]。</span><span class="sxs-lookup"><span data-stu-id="d3100-418">[Open the Command Menu][DevToolsCommandMenu].</span></span>  
1.  <span data-ttu-id="d3100-419">开始键入并选择 `Rendering` `Show Rendering` 。</span><span class="sxs-lookup"><span data-stu-id="d3100-419">Start typing `Rendering` and select `Show Rendering`.</span></span>  <span data-ttu-id="d3100-420">DevTools **在** DevTools 窗口底部显示呈现工具。</span><span class="sxs-lookup"><span data-stu-id="d3100-420">DevTools displays the **Rendering** tool at the bottom of your DevTools window.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-console-drawer-rendering.msft.png" alt-text="呈现工具" lightbox="../media/evaluate-performance-console-drawer-rendering.msft.png":::
       <span data-ttu-id="d3100-422">**呈现**工具</span><span class="sxs-lookup"><span data-stu-id="d3100-422">The **Rendering** tool</span></span>  
    :::image-end:::  
    
### <a name="view-frames-per-second-in-realtime-with-the-fps-meter"></a><span data-ttu-id="d3100-423">使用 FPS 指示器实时查看每秒帧数</span><span class="sxs-lookup"><span data-stu-id="d3100-423">View frames per second in realtime with the FPS meter</span></span>  

<span data-ttu-id="d3100-424">**FPS 指示器**是显示在视口右上角的覆盖层。</span><span class="sxs-lookup"><span data-stu-id="d3100-424">The **FPS meter** is an overlay that appears in the top-right corner of your viewport.</span></span>  <span data-ttu-id="d3100-425">它在页面运行时提供 FPS 实时估计值。</span><span class="sxs-lookup"><span data-stu-id="d3100-425">It provides a realtime estimate of FPS as the page runs.</span></span>  <span data-ttu-id="d3100-426">打开 **FPS 指示器**：</span><span class="sxs-lookup"><span data-stu-id="d3100-426">To open the **FPS meter**:</span></span>  

1.  <span data-ttu-id="d3100-427">打开 **呈现工具** 。</span><span class="sxs-lookup"><span data-stu-id="d3100-427">Open the **Rendering** tool.</span></span>  <span data-ttu-id="d3100-428">[使用呈现工具 分析呈现性能](#analyze-rendering-performance-with-the-rendering-tool)。</span><span class="sxs-lookup"><span data-stu-id="d3100-428">[Analyze rendering performance with the Rendering tool](#analyze-rendering-performance-with-the-rendering-tool).</span></span>  
1.  <span data-ttu-id="d3100-429">打开 **"FPS 指示器"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="d3100-429">Turn on the **FPS Meter** checkbox.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-jank-console-rendering-frame-rate.msft.png" alt-text="FPS 计数" lightbox="../media/evaluate-performance-jank-console-rendering-frame-rate.msft.png":::
       <span data-ttu-id="d3100-431">**FPS 计数**</span><span class="sxs-lookup"><span data-stu-id="d3100-431">The **FPS meter**</span></span>  
    :::image-end:::  
    
### <a name="view-painting-events-in-realtime-with-paint-flashing"></a><span data-ttu-id="d3100-432">使用画图闪烁实时查看绘制事件</span><span class="sxs-lookup"><span data-stu-id="d3100-432">View painting events in realtime with Paint Flashing</span></span>  

<span data-ttu-id="d3100-433">使用画图闪烁获取页面上所有绘制事件实时视图。</span><span class="sxs-lookup"><span data-stu-id="d3100-433">Use Paint Flashing to get a realtime view of all paint events on the page.</span></span>  <span data-ttu-id="d3100-434">只要重新绘制页面的一部分，DevTools 就会用绿色概括该部分。</span><span class="sxs-lookup"><span data-stu-id="d3100-434">Whenever a part of the page gets re-painted, DevTools outlines that section in green.</span></span>  

<span data-ttu-id="d3100-435">若要打开画图闪烁，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="d3100-435">To turn on Paint Flashing, complete the following actions.</span></span>  

1.  <span data-ttu-id="d3100-436">打开 **呈现工具** 。</span><span class="sxs-lookup"><span data-stu-id="d3100-436">Open the **Rendering** tool.</span></span>  <span data-ttu-id="d3100-437">导航到 [使用呈现工具 分析呈现性能](#analyze-rendering-performance-with-the-rendering-tool)。</span><span class="sxs-lookup"><span data-stu-id="d3100-437">Navigate to [Analyze rendering performance with the Rendering tool](#analyze-rendering-performance-with-the-rendering-tool).</span></span>  
1.  <span data-ttu-id="d3100-438">打开" **画图闪烁"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="d3100-438">Turn on the **Paint Flashing** checkbox.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-jank-console-rendering-paint-flashing.msft.png" alt-text="画图闪烁" lightbox="../media/evaluate-performance-jank-console-rendering-paint-flashing.msft.png":::
       **<span data-ttu-id="d3100-440">画图闪烁</span><span class="sxs-lookup"><span data-stu-id="d3100-440">Paint Flashing</span></span>**  
    :::image-end:::  
    
### <a name="view-an-overlay-of-layers-with-layer-borders"></a><span data-ttu-id="d3100-441">使用图层边框查看图层的覆盖</span><span class="sxs-lookup"><span data-stu-id="d3100-441">View an overlay of layers with Layer Borders</span></span>  

<span data-ttu-id="d3100-442">使用 **图层边框** 查看页面顶部的图层边框和磁贴的覆盖。</span><span class="sxs-lookup"><span data-stu-id="d3100-442">Use **Layer Borders** to view an overlay of layer borders and tiles on top of the page.</span></span>  

<span data-ttu-id="d3100-443">若要打开"层边框"，请完成以下操作：</span><span class="sxs-lookup"><span data-stu-id="d3100-443">To turn on Layer Borders, complete the following actions,</span></span>  

1.  <span data-ttu-id="d3100-444">打开 **呈现工具** 。</span><span class="sxs-lookup"><span data-stu-id="d3100-444">Open the **Rendering** tool.</span></span>  <span data-ttu-id="d3100-445">导航到 [使用呈现工具 分析呈现性能](#analyze-rendering-performance-with-the-rendering-tool)。</span><span class="sxs-lookup"><span data-stu-id="d3100-445">Navigate to [Analyze rendering performance with the Rendering tool](#analyze-rendering-performance-with-the-rendering-tool).</span></span>  
1.  <span data-ttu-id="d3100-446">打开" **图层边框"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="d3100-446">Turn on the **Layer Borders** checkbox.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-devtools-console-rendering-layer-borders.msft.png" alt-text="层边框" lightbox="../media/evaluate-performance-devtools-console-rendering-layer-borders.msft.png":::
       **<span data-ttu-id="d3100-448">层边框</span><span class="sxs-lookup"><span data-stu-id="d3100-448">Layer Borders</span></span>**  
    :::image-end:::  
    
<span data-ttu-id="d3100-449">导航到 [debug_colors.cc][ChromiumDebugColors] 中的注释，了解颜色编码的说明。</span><span class="sxs-lookup"><span data-stu-id="d3100-449">Navigate to the comments in [debug_colors.cc][ChromiumDebugColors] for an explanation of the color-codings.</span></span>  

### <a name="find-scroll-performance-issues-in-realtime"></a><span data-ttu-id="d3100-450">实时查找滚动性能问题</span><span class="sxs-lookup"><span data-stu-id="d3100-450">Find scroll performance issues in realtime</span></span>  

<span data-ttu-id="d3100-451">使用滚动性能问题可标识具有与滚动相关的事件侦听器的页面元素，这些元素可能会损害页面的性能。</span><span class="sxs-lookup"><span data-stu-id="d3100-451">Use Scrolling Performance Issues to identify elements of the page that have event listeners related to scrolling that may harm the performance of the page.</span></span>  
<span data-ttu-id="d3100-452">DevTools 以青色概述了可能存在问题的元素。</span><span class="sxs-lookup"><span data-stu-id="d3100-452">DevTools outlines the potentially-problematic elements in teal.</span></span>  

<span data-ttu-id="d3100-453">若要查看滚动性能问题，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="d3100-453">To view scroll performance issues, complete the following actions.</span></span> 

1.  <span data-ttu-id="d3100-454">打开 **呈现工具** 。</span><span class="sxs-lookup"><span data-stu-id="d3100-454">Open the **Rendering** tool.</span></span>  <span data-ttu-id="d3100-455">导航到 [使用呈现工具 分析呈现性能](#analyze-rendering-performance-with-the-rendering-tool)。</span><span class="sxs-lookup"><span data-stu-id="d3100-455">Navigate to [Analyze rendering performance with the Rendering tool](#analyze-rendering-performance-with-the-rendering-tool).</span></span>  
1.  <span data-ttu-id="d3100-456">打开" **滚动性能问题"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="d3100-456">Turn on the **Scrolling Performance Issues** checkbox.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-bing-console-drawer-rendering-scrolling-performance-issues.msft.png" alt-text="滚动性能问题指示非层视口约束的对象可能会损害滚动性能" lightbox="../media/evaluate-performance-bing-console-drawer-rendering-scrolling-performance-issues.msft.png":::
       <span data-ttu-id="d3100-458">**滚动性能问题** 指示非层视口约束的对象可能会损害滚动性能</span><span class="sxs-lookup"><span data-stu-id="d3100-458">**Scrolling Performance Issues** indicates that non-layer viewport-constrained objects may harm scroll performance</span></span>  
    :::image-end:::  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="d3100-459">联系 Microsoft Edge 开发工具团队</span><span class="sxs-lookup"><span data-stu-id="d3100-459">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 开发人员工具|Microsoft Docs"  
[DevToolsCommandMenu]: ../command-menu/index.md#open-the-command-menu "打开"命令菜单 - 使用 Microsoft Edge DevTools 命令菜单"菜单运行|Microsoft Docs"  
[DevtoolsEvaluatePerformanceGettingStarted]: ./index.md "开始分析运行时性能|Microsoft Docs"  

[ActivityTabsDemo]: https://microsoft-edge-chromium-devtools.glitch.me/perf/activitytabs.html "活动选项卡演示|小故障"  

[ChromiumDebugColors]: https://cs.chromium.org/chromium/src/cc/debug/debug_colors.cc "debug_colors.cc - 代码搜索"  

> [!NOTE]
> <span data-ttu-id="d3100-465">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="d3100-465">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="d3100-466">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/reference)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="d3100-466">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/reference) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="d3100-468">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="d3100-468">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
