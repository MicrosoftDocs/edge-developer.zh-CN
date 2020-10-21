---
description: 在 Microsoft Edge DevTools 中记录和分析性能的所有方法的参考。
title: 性能分析引用
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: d135f83273842a1e128df0bb346f0f126e2fbe8d
ms.sourcegitcommit: 99eee78698dc95b2a3fa638a5b063ef449899cda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/20/2020
ms.locfileid: "11125137"
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

# <span data-ttu-id="4d10e-104">性能分析引用</span><span class="sxs-lookup"><span data-stu-id="4d10e-104">Performance analysis reference</span></span>  

<span data-ttu-id="4d10e-105">此页面是与分析性能相关的 Microsoft Edge DevTools 功能的完整参考。</span><span class="sxs-lookup"><span data-stu-id="4d10e-105">This page is a comprehensive reference of Microsoft Edge DevTools features related to analyzing performance.</span></span>  

<span data-ttu-id="4d10e-106">导航到 [分析运行时性能][DevtoolsEvaluatePerformanceGettingStarted] 以了解如何使用 [Microsoft Edge DevTools][MicrosoftEdgeDevTools]分析页面性能的引导式教程。</span><span class="sxs-lookup"><span data-stu-id="4d10e-106">Navigate to [Get Started With Analyzing Runtime Performance][DevtoolsEvaluatePerformanceGettingStarted] for a guided tutorial on how to analyze the performance of a page using [Microsoft Edge DevTools][MicrosoftEdgeDevTools].</span></span>  

## <span data-ttu-id="4d10e-107">记录性能</span><span class="sxs-lookup"><span data-stu-id="4d10e-107">Record performance</span></span>  

### <span data-ttu-id="4d10e-108">记录运行时性能</span><span class="sxs-lookup"><span data-stu-id="4d10e-108">Record runtime performance</span></span>  

<span data-ttu-id="4d10e-109">当您希望分析页面的性能（相对于加载）时，请记录运行时性能。</span><span class="sxs-lookup"><span data-stu-id="4d10e-109">Record runtime performance when you want to analyze the performance of a page as it is running, as opposed to loading.</span></span>  

1.  <span data-ttu-id="4d10e-110">转到要分析的页面。</span><span class="sxs-lookup"><span data-stu-id="4d10e-110">Go to the page that you want to analyze.</span></span>  
1.  <span data-ttu-id="4d10e-111">单击 "DevTools" 中的 " **性能** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="4d10e-111">Click the **Performance** tab in DevTools.</span></span>  
1.  <span data-ttu-id="4d10e-112">选择 " **记录** \ (![ 记录" 图标 ][ImageRecordIcon] \ ) 。</span><span class="sxs-lookup"><span data-stu-id="4d10e-112">Choose **Record** \(![Record icon][ImageRecordIcon]\).</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-performance-record-highlight.msft.png" alt-text="记录" lightbox="../media/evaluate-performance-performance-record-highlight.msft.png":::
       **<span data-ttu-id="4d10e-114">记录</span><span class="sxs-lookup"><span data-stu-id="4d10e-114">Record</span></span>**  
    :::image-end:::  
    
1.  <span data-ttu-id="4d10e-115">与页面交互。</span><span class="sxs-lookup"><span data-stu-id="4d10e-115">Interact with the page.</span></span>  <span data-ttu-id="4d10e-116">DevTools 记录作为交互的结果而发生的所有页面活动。</span><span class="sxs-lookup"><span data-stu-id="4d10e-116">DevTools records all page activity that occurs as a result of your interactions.</span></span>  
1.  <span data-ttu-id="4d10e-117">再次选择 " **录制** " 或选择 " **停止** " 停止录制。</span><span class="sxs-lookup"><span data-stu-id="4d10e-117">Choose **Record** again or choose **Stop** to stop recording.</span></span>  
    
### <span data-ttu-id="4d10e-118">记录加载性能</span><span class="sxs-lookup"><span data-stu-id="4d10e-118">Record load performance</span></span>  

<span data-ttu-id="4d10e-119">当你希望在加载时分析页面性能（而不是运行）时，请记录加载性能。</span><span class="sxs-lookup"><span data-stu-id="4d10e-119">Record load performance when you want to analyze the performance of a page as it is loading, as opposed to running.</span></span>  

1.  <span data-ttu-id="4d10e-120">转到要分析的页面。</span><span class="sxs-lookup"><span data-stu-id="4d10e-120">Go to the page that you want to analyze.</span></span>  
1.  <span data-ttu-id="4d10e-121">打开 DevTools 的 **性能** 面板。</span><span class="sxs-lookup"><span data-stu-id="4d10e-121">Open the **Performance** panel of DevTools.</span></span>  
1.  <span data-ttu-id="4d10e-122">选择 " **刷新页面** \ (![ 刷新" 页面 ][ImageRefreshPageIcon] \ ) 。</span><span class="sxs-lookup"><span data-stu-id="4d10e-122">Choose **Refresh page** \(![Refresh Page][ImageRefreshPageIcon]\).</span></span>  <span data-ttu-id="4d10e-123">DevTools 在页面刷新时记录性能指标，然后在加载完成后的几秒钟内自动停止录制。</span><span class="sxs-lookup"><span data-stu-id="4d10e-123">DevTools records performance metrics while the page refreshes and then automatically stops the recording a couple seconds after the load finishes.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-performance-refresh-button.msft.png" alt-text="记录" lightbox="../media/evaluate-performance-performance-refresh-button.msft.png":::
       **<span data-ttu-id="4d10e-125">刷新页面</span><span class="sxs-lookup"><span data-stu-id="4d10e-125">Refresh page</span></span>**  
    :::image-end:::  
    
<span data-ttu-id="4d10e-126">DevTools 会自动放大大部分活动发生的录制部分。</span><span class="sxs-lookup"><span data-stu-id="4d10e-126">DevTools automatically zooms in on the portion of the recording where most of the activity occurred.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-refreshed.msft.png" alt-text="记录" lightbox="../media/evaluate-performance-performance-refreshed.msft.png":::
   <span data-ttu-id="4d10e-128">页面加载录制</span><span class="sxs-lookup"><span data-stu-id="4d10e-128">A page-load recording</span></span>  
:::image-end:::  

### <span data-ttu-id="4d10e-129">录制时捕获屏幕截图</span><span class="sxs-lookup"><span data-stu-id="4d10e-129">Capture screenshots while recording</span></span>  

<span data-ttu-id="4d10e-130">启用 " **屏幕截图** " 复选框，以便在录制时捕获每个帧的屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="4d10e-130">Enable the **Screenshots** checkbox to capture a screenshot of every frame while recording.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-capture-screenshots-checkbox.msft.png" alt-text="记录" lightbox="../media/evaluate-performance-performance-capture-screenshots-checkbox.msft.png":::
   <span data-ttu-id="4d10e-132">" **屏幕截图** " 复选框</span><span class="sxs-lookup"><span data-stu-id="4d10e-132">The **Screenshots** checkbox</span></span>  
:::image-end:::  

<span data-ttu-id="4d10e-133">导航到 " [查看屏幕截图](#view-a-screenshot) " 以了解如何与屏幕截图交互。</span><span class="sxs-lookup"><span data-stu-id="4d10e-133">Navigate to [View a screenshot](#view-a-screenshot) to learn how to interact with screenshots.</span></span>  

### <span data-ttu-id="4d10e-134">录制时强制垃圾回收</span><span class="sxs-lookup"><span data-stu-id="4d10e-134">Force garbage collection while recording</span></span>  

<span data-ttu-id="4d10e-135">录制页面时，请选择 " **收集垃圾** \ (![ 收集垃圾图标 ][ImageCollectGarbageIcon] \ ) " 以强制垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="4d10e-135">While you are recording a page, choose **Collect garbage** \(![Collect garbage icon][ImageCollectGarbageIcon]\) to force garbage collection.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-collect-garbage-button.msft.png" alt-text="记录" lightbox="../media/evaluate-performance-performance-collect-garbage-button.msft.png":::
   <span data-ttu-id="4d10e-137">收集垃圾</span><span class="sxs-lookup"><span data-stu-id="4d10e-137">Collect garbage</span></span>  
:::image-end:::  

### <span data-ttu-id="4d10e-138">显示录制设置</span><span class="sxs-lookup"><span data-stu-id="4d10e-138">Show recording settings</span></span>  

<span data-ttu-id="4d10e-139">选择 " **捕获设置** \ (![ 捕获设置 ][ImageCaptureSettingsIcon] \ ) " 以公开有关 DevTools 如何捕获性能录制的更多设置。</span><span class="sxs-lookup"><span data-stu-id="4d10e-139">Choose **Capture settings** \(![Capture settings][ImageCaptureSettingsIcon]\) to expose more settings related to how DevTools captures performance recordings.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-capture-settings-button-open-drawer.msft.png" alt-text="记录" lightbox="../media/evaluate-performance-performance-capture-settings-button-open-drawer.msft.png":::
   <span data-ttu-id="4d10e-141">" **捕获设置** " 部分</span><span class="sxs-lookup"><span data-stu-id="4d10e-141">The **Capture Settings** section</span></span>  
:::image-end:::  

### <span data-ttu-id="4d10e-142">禁用 JavaScript 示例</span><span class="sxs-lookup"><span data-stu-id="4d10e-142">Disable JavaScript samples</span></span>  

<span data-ttu-id="4d10e-143">默认情况下，录制的 **主要** 部分显示在录制期间调用的 JavaScript 函数的详细调用堆栈。</span><span class="sxs-lookup"><span data-stu-id="4d10e-143">By default, the **Main** section of a recording displays detailed call stacks of JavaScript functions that were called during the recording.</span></span>  <span data-ttu-id="4d10e-144">要禁用这些调用堆栈，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="4d10e-144">To disable these call stacks:</span></span>  

1.  <span data-ttu-id="4d10e-145">打开 " **捕获设置** " 菜单。</span><span class="sxs-lookup"><span data-stu-id="4d10e-145">Open the **Capture settings** menu.</span></span>  <span data-ttu-id="4d10e-146">导航到 " [显示录制设置](#show-recording-settings)"。</span><span class="sxs-lookup"><span data-stu-id="4d10e-146">Navigate to [Show recording settings](#show-recording-settings).</span></span>  
1.  <span data-ttu-id="4d10e-147">启用 " **禁用 JavaScript 示例** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="4d10e-147">Enable the **Disable JavaScript Samples** checkbox.</span></span>  
1.  <span data-ttu-id="4d10e-148">记录页面。</span><span class="sxs-lookup"><span data-stu-id="4d10e-148">Take a recording of the page.</span></span>  
    
<span data-ttu-id="4d10e-149">以下2个图显示了禁用和启用 JavaScript 示例之间的区别。</span><span class="sxs-lookup"><span data-stu-id="4d10e-149">The following 2 figures display the difference between disabling and enabling JavaScript samples.</span></span>  <span data-ttu-id="4d10e-150">在禁用采样时，录制的 **主要** 部分会更短，因为它省略了所有 JavaScript 调用堆栈。</span><span class="sxs-lookup"><span data-stu-id="4d10e-150">The **Main** section of the recording is much shorter when sampling is disabled, because it omits all of the JavaScript call stacks.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-on.msft.png" alt-text="记录" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-on.msft.png":::
         <span data-ttu-id="4d10e-152">禁用 JS 示例时录制的示例</span><span class="sxs-lookup"><span data-stu-id="4d10e-152">An example of a recording when JS samples are disabled</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off.msft.png" alt-text="记录" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off.msft.png":::
         <span data-ttu-id="4d10e-154">启用 JS 示例时录制的示例</span><span class="sxs-lookup"><span data-stu-id="4d10e-154">An example of a recording when JS samples are enabled</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::

### <span data-ttu-id="4d10e-155">录制时阻止网络</span><span class="sxs-lookup"><span data-stu-id="4d10e-155">Throttle the network while recording</span></span>  

<span data-ttu-id="4d10e-156">要在录制时阻止网络，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="4d10e-156">To throttle the network while recording:</span></span>  

1.  <span data-ttu-id="4d10e-157">打开 " **捕获设置** " 菜单。</span><span class="sxs-lookup"><span data-stu-id="4d10e-157">Open the **Capture settings** menu.</span></span>  <span data-ttu-id="4d10e-158">导航到 " [显示录制设置](#show-recording-settings)"。</span><span class="sxs-lookup"><span data-stu-id="4d10e-158">Navigate to [Show recording settings](#show-recording-settings).</span></span>  
1.  <span data-ttu-id="4d10e-159">将 " **网络** " 设置为所需的带宽限制级别。</span><span class="sxs-lookup"><span data-stu-id="4d10e-159">Set **Network** to the desired level of throttling.</span></span>  
    
### <span data-ttu-id="4d10e-160">在录制时调节 CPU</span><span class="sxs-lookup"><span data-stu-id="4d10e-160">Throttle the CPU while recording</span></span>  

<span data-ttu-id="4d10e-161">要在录制时调节 CPU，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="4d10e-161">To throttle the CPU while recording:</span></span>  

1.  <span data-ttu-id="4d10e-162">打开 " **捕获设置** " 菜单。</span><span class="sxs-lookup"><span data-stu-id="4d10e-162">Open the **Capture settings** menu.</span></span>  <span data-ttu-id="4d10e-163">导航到 " [显示录制设置](#show-recording-settings)"。</span><span class="sxs-lookup"><span data-stu-id="4d10e-163">Navigate to [Show recording settings](#show-recording-settings).</span></span>  
1.  <span data-ttu-id="4d10e-164">将 **CPU** 设置为所需的带宽限制级别。</span><span class="sxs-lookup"><span data-stu-id="4d10e-164">Set **CPU** to the desired level of throttling.</span></span>  
    
<span data-ttu-id="4d10e-165">"限制" 相对于计算机的功能。</span><span class="sxs-lookup"><span data-stu-id="4d10e-165">Throttling is relative to the capabilities of your computer.</span></span>  <span data-ttu-id="4d10e-166">例如， **2x 减速** 选项使 CPU 的运行速度比正常速度慢2倍。</span><span class="sxs-lookup"><span data-stu-id="4d10e-166">For example, the **2x slowdown** option makes your CPU operate 2 times slower than normal.</span></span>  <span data-ttu-id="4d10e-167">DevTools 不会真正模拟移动设备的 Cpu，因为移动设备的体系结构与台式计算机和笔记本电脑的体系结构截然不同。</span><span class="sxs-lookup"><span data-stu-id="4d10e-167">DevTools do not truly simulate the CPUs of mobile devices, because the architecture of mobile devices is very different from that of desktops and laptops.</span></span>  

### <span data-ttu-id="4d10e-168">启用高级画图工具</span><span class="sxs-lookup"><span data-stu-id="4d10e-168">Enable advanced paint instrumentation</span></span>  

<span data-ttu-id="4d10e-169">查看详细的画图工具：</span><span class="sxs-lookup"><span data-stu-id="4d10e-169">To view detailed paint instrumentation:</span></span>  

1.  <span data-ttu-id="4d10e-170">打开 " **捕获设置** " 菜单。</span><span class="sxs-lookup"><span data-stu-id="4d10e-170">Open the **Capture settings** menu.</span></span>  <span data-ttu-id="4d10e-171">导航到 " [显示录制设置](#show-recording-settings)"。</span><span class="sxs-lookup"><span data-stu-id="4d10e-171">Navigate to [Show recording settings](#show-recording-settings).</span></span>  
1.  <span data-ttu-id="4d10e-172">选中 " \*\*启用高级画图检测" (慢速) \*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="4d10e-172">Check the **Enable advanced paint instrumentation (slow)** checkbox.</span></span>  

<span data-ttu-id="4d10e-173">若要了解如何与画图信息交互，请导航到 " [视图图层](#view-layers-information) " 和 " [查看画图" 探查器](#view-paint-profiler)。</span><span class="sxs-lookup"><span data-stu-id="4d10e-173">To learn how to interact with the paint information, navigate to [View layers](#view-layers-information) and [View paint profiler](#view-paint-profiler).</span></span>  

## <span data-ttu-id="4d10e-174">保存录制</span><span class="sxs-lookup"><span data-stu-id="4d10e-174">Save a recording</span></span>  

<span data-ttu-id="4d10e-175">若要保存录制，请右键单击，然后选择 " **保存配置文件**"。</span><span class="sxs-lookup"><span data-stu-id="4d10e-175">To save a recording, right-click and choose **Save Profile**.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-save-profile.msft.png" alt-text="记录" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-save-profile.msft.png":::
   **<span data-ttu-id="4d10e-177">保存配置文件</span><span class="sxs-lookup"><span data-stu-id="4d10e-177">Save Profile</span></span>**  
:::image-end:::  

## <span data-ttu-id="4d10e-178">加载录制</span><span class="sxs-lookup"><span data-stu-id="4d10e-178">Load a recording</span></span>  

<span data-ttu-id="4d10e-179">若要加载录制，请右键单击，然后选择 " **加载配置文件**"。</span><span class="sxs-lookup"><span data-stu-id="4d10e-179">To load a recording, right-click and choose **Load Profile**.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-load-profile.msft.png" alt-text="记录" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-load-profile.msft.png":::
   **<span data-ttu-id="4d10e-181">加载配置文件</span><span class="sxs-lookup"><span data-stu-id="4d10e-181">Load Profile</span></span>**  
:::image-end:::  

## <span data-ttu-id="4d10e-182">清除上一个录制</span><span class="sxs-lookup"><span data-stu-id="4d10e-182">Clear the previous recording</span></span>  

<span data-ttu-id="4d10e-183">录制完毕后，请按 " **清除录制** \ (![ 清除录制" 图标 ][ImageClearRecordingIcon] \ ) 清除 " **性能** " 面板中的录制。</span><span class="sxs-lookup"><span data-stu-id="4d10e-183">After making a recording, press **Clear recording** \(![Clear recording icon][ImageClearRecordingIcon]\) to clear that recording from the **Performance** panel.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-clear-button.msft.png" alt-text="记录" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-clear-button.msft.png":::
   **<span data-ttu-id="4d10e-185">清除录制</span><span class="sxs-lookup"><span data-stu-id="4d10e-185">Clear recording</span></span>**  
:::image-end:::  

## <span data-ttu-id="4d10e-186">分析性能记录</span><span class="sxs-lookup"><span data-stu-id="4d10e-186">Analyze a performance recording</span></span>  

<span data-ttu-id="4d10e-187">在 [记录运行时性能](#record-runtime-performance) 或 [记录加载性能](#record-load-performance)后，" **性能** " 面板会提供大量数据来分析所发生的情况的性能。</span><span class="sxs-lookup"><span data-stu-id="4d10e-187">After you [record runtime performance](#record-runtime-performance) or [record load performance](#record-load-performance), the **Performance** panel provides a lot of data for analyzing the performance of what just happened.</span></span>  

### <span data-ttu-id="4d10e-188">选择部分录制</span><span class="sxs-lookup"><span data-stu-id="4d10e-188">Select a portion of a recording</span></span>  

<span data-ttu-id="4d10e-189">在 **概述** 中向左或向右拖动鼠标，选择部分录制。</span><span class="sxs-lookup"><span data-stu-id="4d10e-189">Drag your mouse left or right across the **Overview** to select a portion of a recording.</span></span>  <span data-ttu-id="4d10e-190">**概述**是包含**FPS**、 **CPU**和**网络**图表的部分。</span><span class="sxs-lookup"><span data-stu-id="4d10e-190">The **Overview** is the section that contains the **FPS**, **CPU**, and **NET** charts.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-zoom-highlighted.msft.png" alt-text="记录" lightbox="../media/evaluate-performance-performance-zoom-highlighted.msft.png":::
   <span data-ttu-id="4d10e-192">在 **概览** 上拖动鼠标以缩放</span><span class="sxs-lookup"><span data-stu-id="4d10e-192">Drag the mouse across the **Overview** to zoom</span></span>  
:::image-end:::  

<span data-ttu-id="4d10e-193">要使用键盘选择某个部分，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="4d10e-193">To select a portion using the keyboard:</span></span>  

1.  <span data-ttu-id="4d10e-194">单击 **主** 节的背景，或单击它旁边的任何部分（如 **交互**、 **网络**或 **GPU**）。</span><span class="sxs-lookup"><span data-stu-id="4d10e-194">Click on the background of the **Main** section, or any of the sections next to it, such as **Interactions**, **Network**, or **GPU**.</span></span>  <span data-ttu-id="4d10e-195">只有当其中一个分区处于焦点时，此键盘工作流才有效。</span><span class="sxs-lookup"><span data-stu-id="4d10e-195">This keyboard workflow only works when one of these sections is in focus.</span></span>  
1.  <span data-ttu-id="4d10e-196">使用 `W` 、 `A` 、 `S` 、 `D` 键进行放大、向左移动、缩小和向右移动。</span><span class="sxs-lookup"><span data-stu-id="4d10e-196">Use the `W`, `A`, `S`, `D` keys to zoom in, move left, zoom out, and move right, respectively.</span></span>  

<span data-ttu-id="4d10e-197">若要使用触控板选择部分，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="4d10e-197">To select a portion using a trackpad:</span></span>  

1.  <span data-ttu-id="4d10e-198">将鼠标悬停在 " **概述** " 部分或 " **详细信息** " 部分。</span><span class="sxs-lookup"><span data-stu-id="4d10e-198">Hover your mouse over the **Overview** section or the **Details** section.</span></span>  <span data-ttu-id="4d10e-199">" **概述** " 部分是包含 " **FPS**"、" **CPU**" 和 " **网络** " 图表的区域。</span><span class="sxs-lookup"><span data-stu-id="4d10e-199">The **Overview** section is the area containing the **FPS**, **CPU**, and **NET** charts.</span></span>  <span data-ttu-id="4d10e-200">" **详细信息** " 部分是包含 **主要** 部分、" **交互** " 部分等的区域。</span><span class="sxs-lookup"><span data-stu-id="4d10e-200">The **Details** section is the area containing the **Main** section, the **Interactions** section, and so on.</span></span>  
1.  <span data-ttu-id="4d10e-201">使用两根手指，向上轻扫以缩小，向左轻扫可向左移动，向下轻扫以放大，向右轻扫以向右移动。</span><span class="sxs-lookup"><span data-stu-id="4d10e-201">Using two fingers, swipe up to zoom out, swipe left to move left, swipe down to zoom in, and swipe right to move right.</span></span>  

<span data-ttu-id="4d10e-202">若要在 **主** 分区或任何邻居中滚动较长的火焰图表，请单击并按住鼠标上下拖动。</span><span class="sxs-lookup"><span data-stu-id="4d10e-202">To scroll a long flame chart in the **Main** section or any of the neighbors, click and hold while dragging up and down.</span></span>  <span data-ttu-id="4d10e-203">向左和向右拖动以移动所选录制部分。</span><span class="sxs-lookup"><span data-stu-id="4d10e-203">Drag left and right to move what portion of the recording is selected.</span></span>  

### <span data-ttu-id="4d10e-204">搜索活动</span><span class="sxs-lookup"><span data-stu-id="4d10e-204">Search activities</span></span>  

<span data-ttu-id="4d10e-205">选择 `Control` + `F` \ (Windows、Linux \ ) 或 `Command` + `F` \ (macOS \ ) 以打开 "**性能**" 面板底部的 "搜索" 框。</span><span class="sxs-lookup"><span data-stu-id="4d10e-205">Select `Control`+`F` \(Windows, Linux\) or `Command`+`F` \(macOS\) to open the search box at the bottom of the **Performance** panel.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-search-regex.msft.png" alt-text="记录" lightbox="../media/evaluate-performance-performance-search-regex.msft.png":::
   <span data-ttu-id="4d10e-207">搜索框</span><span class="sxs-lookup"><span data-stu-id="4d10e-207">The search box</span></span>  
:::image-end:::  

<span data-ttu-id="4d10e-208">若要导航与查询匹配的活动，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="4d10e-208">To navigate activities that match your query:</span></span>  

*   <span data-ttu-id="4d10e-209">使用 **以前** 的 \ (![ 上一个 \ ][ImagePreviousIcon] ) 和 **下一个** \ (![ 下一个 ][ImageNextIcon] \ ) 按钮。</span><span class="sxs-lookup"><span data-stu-id="4d10e-209">Use the **Previous** \(![Previous][ImagePreviousIcon]\) and **Next** \(![Next][ImageNextIcon]\) buttons.</span></span>  
*   <span data-ttu-id="4d10e-210">选择 `Shift` + `Enter` 以选择 "上一个" 或 `Enter` 选择下一个。</span><span class="sxs-lookup"><span data-stu-id="4d10e-210">Select `Shift`+`Enter` to select the previous or `Enter` to select the next.</span></span>  

<span data-ttu-id="4d10e-211">修改查询设置：</span><span class="sxs-lookup"><span data-stu-id="4d10e-211">To modify query settings:</span></span>  

*   <span data-ttu-id="4d10e-212">按 "区分 **大小** 写" (区分 ![ 大小写 ][ImageSearchCaseIcon] \ ) 以使查询区分大小写。</span><span class="sxs-lookup"><span data-stu-id="4d10e-212">Press **Case sensitive** \(![Case sensitive][ImageSearchCaseIcon]\) to make the query case sensitive.</span></span>  
*   <span data-ttu-id="4d10e-213">按 **regex** \ (![ Regex ][ImageSearchRegexIcon] \ ) 在查询中使用正则表达式。</span><span class="sxs-lookup"><span data-stu-id="4d10e-213">Press **Regex** \(![Regex][ImageSearchRegexIcon]\) to use a regular expression in your query.</span></span>  

<span data-ttu-id="4d10e-214">若要隐藏搜索框，请按 " **取消**"。</span><span class="sxs-lookup"><span data-stu-id="4d10e-214">To hide the search box, press **Cancel**.</span></span>  

### <span data-ttu-id="4d10e-215">查看主线程活动</span><span class="sxs-lookup"><span data-stu-id="4d10e-215">View main thread activity</span></span>  

<span data-ttu-id="4d10e-216">使用 **主** 部分查看在页面的主线程上发生的活动。</span><span class="sxs-lookup"><span data-stu-id="4d10e-216">Use the **Main** section to view activity that occurred on the main thread of the page.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-main-zoomed.msft.png" alt-text="记录" lightbox="../media/evaluate-performance-performance-main-zoomed.msft.png":::
   <span data-ttu-id="4d10e-218">**主要**部分</span><span class="sxs-lookup"><span data-stu-id="4d10e-218">The **Main** section</span></span>  
:::image-end:::  

<span data-ttu-id="4d10e-219">单击事件可在 " **摘要** " 选项卡中查看有关它的详细信息。 DevTools 概述所选事件。</span><span class="sxs-lookup"><span data-stu-id="4d10e-219">Click on an event to view more information about it in the **Summary** tab.  DevTools outlines the selected event.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-summary-me.msft.png" alt-text="记录" lightbox="../media/evaluate-performance-performance-summary-me.msft.png":::
   <span data-ttu-id="4d10e-221">有关 `anonymous` " **摘要** " 选项卡中的函数的详细信息</span><span class="sxs-lookup"><span data-stu-id="4d10e-221">More information about the `anonymous` function in the **Summary** tab</span></span>  
:::image-end:::  

<span data-ttu-id="4d10e-222">DevTools 表示带有火焰图表的主线程活动。</span><span class="sxs-lookup"><span data-stu-id="4d10e-222">DevTools represents main thread activity with a flame chart.</span></span>  <span data-ttu-id="4d10e-223">X 轴表示一段时间内的录制。</span><span class="sxs-lookup"><span data-stu-id="4d10e-223">The x-axis represents the recording over time.</span></span>  <span data-ttu-id="4d10e-224">Y 轴表示调用堆叠。</span><span class="sxs-lookup"><span data-stu-id="4d10e-224">The y-axis represents the call stack.</span></span>  <span data-ttu-id="4d10e-225">顶部的事件会导致其下方的事件。</span><span class="sxs-lookup"><span data-stu-id="4d10e-225">The events on top cause the events below it.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-main-flame-chart.msft.png" alt-text="记录" lightbox="../media/evaluate-performance-performance-main-flame-chart.msft.png":::
   <span data-ttu-id="4d10e-227">火焰图</span><span class="sxs-lookup"><span data-stu-id="4d10e-227">A flame chart</span></span>  
:::image-end:::  

<span data-ttu-id="4d10e-228">在上图中， `click` 事件导致 `Function Call` `activitytabs.js` 行53上出现 a。</span><span class="sxs-lookup"><span data-stu-id="4d10e-228">In the previous figure, a `click` event caused a `Function Call` in `activitytabs.js` on line 53.</span></span>  <span data-ttu-id="4d10e-229">`Function Call`你将看到调用了一个匿名函数。</span><span class="sxs-lookup"><span data-stu-id="4d10e-229">Below `Function Call` you see that an anonymous function was called.</span></span>  <span data-ttu-id="4d10e-230">调用了称为的匿名函数 `a` `wait` `Minor GC` 。</span><span class="sxs-lookup"><span data-stu-id="4d10e-230">The anonymous function called `a`, which called `wait`, which called `Minor GC`.</span></span>  

<span data-ttu-id="4d10e-231">DevTools 分配脚本随机颜色。</span><span class="sxs-lookup"><span data-stu-id="4d10e-231">DevTools assigns scripts random colors.</span></span>  <span data-ttu-id="4d10e-232">在上图中，一个脚本的函数调用的颜色为浅绿色。</span><span class="sxs-lookup"><span data-stu-id="4d10e-232">In the previous figure, function calls from one script are colored light green.</span></span>  <span data-ttu-id="4d10e-233">来自另一个脚本的通话的颜色为米色。</span><span class="sxs-lookup"><span data-stu-id="4d10e-233">Calls from another script are colored beige.</span></span>  <span data-ttu-id="4d10e-234">较深的黄色表示脚本活动，紫色事件表示呈现活动。</span><span class="sxs-lookup"><span data-stu-id="4d10e-234">The darker yellow represents scripting activity, and the purple event represents rendering activity.</span></span>  <span data-ttu-id="4d10e-235">这些较暗的黄色和紫色事件在所有录制中保持一致。</span><span class="sxs-lookup"><span data-stu-id="4d10e-235">These darker yellow and purple events are consistent across all recordings.</span></span>  

<span data-ttu-id="4d10e-236">如果想要隐藏 JavaScript 调用的详细火焰图表，请导航到 " [禁用 javascript 示例](#disable-javascript-samples) "。</span><span class="sxs-lookup"><span data-stu-id="4d10e-236">Navigate to [Disable JavaScript samples](#disable-javascript-samples) if you want to hide the detailed flame chart of JavaScript calls.</span></span>  <span data-ttu-id="4d10e-237">如果禁用了 JS 示例，则只能查看 `Event: click` `Function Call` 上图中的高级事件，例如和。</span><span class="sxs-lookup"><span data-stu-id="4d10e-237">When JS samples are disabled, you only see high-level events such as `Event: click` and `Function Call` from the previous figure.</span></span>  

### <span data-ttu-id="4d10e-238">查看表中的活动</span><span class="sxs-lookup"><span data-stu-id="4d10e-238">View activities in a table</span></span>  

<span data-ttu-id="4d10e-239">录制页面后，不需要仅依赖 **主要** 部分来分析活动。</span><span class="sxs-lookup"><span data-stu-id="4d10e-239">After recording a page, you do not need to rely solely on the **Main** section to analyze activities.</span></span>  <span data-ttu-id="4d10e-240">DevTools 还提供了用于分析活动的三个表格视图。</span><span class="sxs-lookup"><span data-stu-id="4d10e-240">DevTools also provides three tabular views for analyzing activities.</span></span>  <span data-ttu-id="4d10e-241">每个视图为您提供了不同的活动视角：</span><span class="sxs-lookup"><span data-stu-id="4d10e-241">Each view gives you a different perspective on the activities:</span></span>  

*   <span data-ttu-id="4d10e-242">当您想要查看导致大部分工作的根活动时，请使用 ["调用树" 选项卡](#the-call-tree-tab)。</span><span class="sxs-lookup"><span data-stu-id="4d10e-242">When you want to view the root activities that cause the most work, use [the Call Tree tab](#the-call-tree-tab).</span></span>  
*   <span data-ttu-id="4d10e-243">当您想要查看最常被直接花费的时间的活动时，请使用 ["Bottom-Up" 选项卡](#the-bottom-up-tab)。</span><span class="sxs-lookup"><span data-stu-id="4d10e-243">When you want to view the activities where the most time was directly spent, use [the Bottom-Up tab](#the-bottom-up-tab).</span></span>  
*   <span data-ttu-id="4d10e-244">如果要按录制期间的顺序查看活动，请使用 ["事件日志" 选项卡](#the-event-log-tab)。</span><span class="sxs-lookup"><span data-stu-id="4d10e-244">When you want to view the activities in the order in which they occurred during the recording, use [the Event Log tab](#the-event-log-tab).</span></span>  
    
> [!NOTE]
> <span data-ttu-id="4d10e-245">接下来的三个部分都是指同一演示。</span><span class="sxs-lookup"><span data-stu-id="4d10e-245">The next three sections all refer to the same demo.</span></span>  <span data-ttu-id="4d10e-246">在 " [活动" 选项卡演示][ActivityTabsDemo]中自行运行演示。</span><span class="sxs-lookup"><span data-stu-id="4d10e-246">Run the demo yourself at [Activity Tabs Demo][ActivityTabsDemo].</span></span>  

#### <span data-ttu-id="4d10e-247">根活动</span><span class="sxs-lookup"><span data-stu-id="4d10e-247">Root activities</span></span>  

<span data-ttu-id="4d10e-248">下面是 "**调用树**" 选项卡、"**下移至**" 选项卡和 "**事件日志**" 部分中提及的**根活动**概念的说明。</span><span class="sxs-lookup"><span data-stu-id="4d10e-248">Here is an explanation of the **root activities** concept that is mentioned in the **Call Tree** tab, **Bottom-Up** tab, and **Event Log** sections.</span></span>  

<span data-ttu-id="4d10e-249">根活动是导致浏览器执行某些工作的操作。</span><span class="sxs-lookup"><span data-stu-id="4d10e-249">Root activities are those which cause the browser to do some work.</span></span>  <span data-ttu-id="4d10e-250">例如，当您单击页面时，浏览器会将 `Event` 活动作为根活动触发。</span><span class="sxs-lookup"><span data-stu-id="4d10e-250">For example, when you click a page, the browser fires an `Event` activity as the root activity.</span></span>  <span data-ttu-id="4d10e-251">这 `Event` 可能会导致处理程序运行，依此类推。</span><span class="sxs-lookup"><span data-stu-id="4d10e-251">That `Event` might cause a handler to run, and so on.</span></span>  

<span data-ttu-id="4d10e-252">在 **主** 区域的火焰图表中，根活动位于图表顶部。</span><span class="sxs-lookup"><span data-stu-id="4d10e-252">In the flame chart of the **Main** section, root activities are at the top of the chart.</span></span>  <span data-ttu-id="4d10e-253">在 " **调用树** " 和 " **事件日志** " 选项卡中，根活动是顶级项目。</span><span class="sxs-lookup"><span data-stu-id="4d10e-253">In the **Call Tree** and **Event Log** tabs, root activities are the top-level items.</span></span>  

<span data-ttu-id="4d10e-254">导航到 ["调用树" 选项卡](#the-call-tree-tab) ，查看根活动的示例。</span><span class="sxs-lookup"><span data-stu-id="4d10e-254">Navigate to [The Call Tree tab](#the-call-tree-tab) for an example of root activities.</span></span>  

#### <span data-ttu-id="4d10e-255">"调用树" 选项卡</span><span class="sxs-lookup"><span data-stu-id="4d10e-255">The Call Tree tab</span></span>  

<span data-ttu-id="4d10e-256">使用 " **调用树** " 选项卡查看哪些 [根活动](#root-activities) 导致最大的工作。</span><span class="sxs-lookup"><span data-stu-id="4d10e-256">Use the **Call Tree** tab to view which [root activities](#root-activities) cause the most work.</span></span>  

<span data-ttu-id="4d10e-257">" **调用树** " 选项卡仅在录制的选定部分中显示活动。</span><span class="sxs-lookup"><span data-stu-id="4d10e-257">The **Call Tree** tab only displays activities during the selected portion of the recording.</span></span>  <span data-ttu-id="4d10e-258">导航以 [选择录制部分](#select-a-portion-of-a-recording) ，了解如何选择部分内容。</span><span class="sxs-lookup"><span data-stu-id="4d10e-258">Navigate to [Select a portion of a recording](#select-a-portion-of-a-recording) to learn how to select portions.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-call-tree.msft.png" alt-text="记录" lightbox="../media/evaluate-performance-performance-call-tree.msft.png":::
   <span data-ttu-id="4d10e-260">" **调用树** " 选项卡</span><span class="sxs-lookup"><span data-stu-id="4d10e-260">The **Call Tree** tab</span></span>  
:::image-end:::  

<span data-ttu-id="4d10e-261">在上图中，" **活动** " 列中的项目的顶级级别，例如 "" 和 "" `Evaluate Script` `Parse HTML` 根活动。</span><span class="sxs-lookup"><span data-stu-id="4d10e-261">In the previous figure, the top-level of items in the **Activity** column, such as `Evaluate Script` and `Parse HTML` are root activities.</span></span>  <span data-ttu-id="4d10e-262">嵌套表示调用堆栈。</span><span class="sxs-lookup"><span data-stu-id="4d10e-262">The nesting represents the call stack.</span></span>  <span data-ttu-id="4d10e-263">例如，在上图中， `Parse HTML` 这导致 `Evaluate Script` 了导致的 `Compile Script` 和 `(anonymous)` 。</span><span class="sxs-lookup"><span data-stu-id="4d10e-263">For example, in the previous figure, `Parse HTML` which caused `Evaluate Script` which caused `Compile Script` and `(anonymous)`.</span></span>  

<span data-ttu-id="4d10e-264">**自我时间** 表示该活动直接花费的时间。</span><span class="sxs-lookup"><span data-stu-id="4d10e-264">**Self Time** represents the time directly spent in that activity.</span></span>  <span data-ttu-id="4d10e-265">"**总时间**" 表示该活动或任何子活动所花费的时间。</span><span class="sxs-lookup"><span data-stu-id="4d10e-265">**Total Time** represents the time spent in that activity or any of the children.</span></span>  

<span data-ttu-id="4d10e-266">选择 " **自时间**"、" **总时间**" 或 " **活动** "，按该列对表格进行排序。</span><span class="sxs-lookup"><span data-stu-id="4d10e-266">Choose **Self Time**, **Total Time**, or **Activity** to sort the table by that column.</span></span>  

<span data-ttu-id="4d10e-267">使用 " **筛选** " 文本框按活动名称筛选事件。</span><span class="sxs-lookup"><span data-stu-id="4d10e-267">Use the **Filter** text box to filter events by activity name.</span></span>  

<span data-ttu-id="4d10e-268">默认情况下，" **分组** " 菜单设置为 " **无分组**"。</span><span class="sxs-lookup"><span data-stu-id="4d10e-268">By default the **Grouping** menu is set to **No Grouping**.</span></span>  <span data-ttu-id="4d10e-269">使用 " **分组** " 菜单基于各种条件对活动表进行排序。</span><span class="sxs-lookup"><span data-stu-id="4d10e-269">Use the **Grouping** menu to sort the activity table based on various criteria.</span></span>  

<span data-ttu-id="4d10e-270">选择 "显示最大的 **堆栈** \ (显示最大 ![ ][ImageShowHeaviestStackIcon] 的堆栈 \" ) ，将另一个表显示在 **活动** 表的右侧。</span><span class="sxs-lookup"><span data-stu-id="4d10e-270">Choose **Show Heaviest Stack** \(![Show Heaviest Stack][ImageShowHeaviestStackIcon]\) to reveal another table to the right of the **Activity** table.</span></span>  <span data-ttu-id="4d10e-271">单击活动以填充最大的 **堆栈** 表。</span><span class="sxs-lookup"><span data-stu-id="4d10e-271">Click on an activity to populate the **Heaviest Stack** table.</span></span>  <span data-ttu-id="4d10e-272">"最 **繁忙的堆栈** " 表显示所选活动的哪些子元素运行时间最长。</span><span class="sxs-lookup"><span data-stu-id="4d10e-272">The **Heaviest Stack** table shows you which children of the selected activity took the longest time to run.</span></span>  

#### <span data-ttu-id="4d10e-273">"Bottom-Up" 选项卡</span><span class="sxs-lookup"><span data-stu-id="4d10e-273">The Bottom-Up tab</span></span>  

<span data-ttu-id="4d10e-274">使用 " **下** " 选项卡查看哪些活动直接占用总时间。</span><span class="sxs-lookup"><span data-stu-id="4d10e-274">Use the **Bottom-Up** tab to view which activities directly took up the most time in aggregate.</span></span>  

<span data-ttu-id="4d10e-275">**自下而上**的选项卡仅显示录制的选定部分中的活动。</span><span class="sxs-lookup"><span data-stu-id="4d10e-275">The **Bottom-Up** tab only displays activities during the selected portion of the recording.</span></span>  <span data-ttu-id="4d10e-276">导航以 [选择录制部分](#select-a-portion-of-a-recording) ，了解如何选择部分内容。</span><span class="sxs-lookup"><span data-stu-id="4d10e-276">Navigate to [Select a portion of a recording](#select-a-portion-of-a-recording) to learn how to select portions.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-bottoms-up.msft.png" alt-text="记录" lightbox="../media/evaluate-performance-performance-bottoms-up.msft.png":::
   <span data-ttu-id="4d10e-278">" **下** " 选项卡</span><span class="sxs-lookup"><span data-stu-id="4d10e-278">The **Bottom-Up** tab</span></span>  
:::image-end:::  

<span data-ttu-id="4d10e-279">**在上图的第一**节火焰图表中，导航到几乎几乎几乎所有时间都在运行 `Parse HTML` 。</span><span class="sxs-lookup"><span data-stu-id="4d10e-279">In the **Main** section flame chart of the previous figure, navigate to that almost practically all of the time was spent running `Parse HTML`.</span></span>  <span data-ttu-id="4d10e-280">上图的 " **下** 一步" 选项卡中的顶部活动是 `Parse HTML` 。</span><span class="sxs-lookup"><span data-stu-id="4d10e-280">The top activity in the **Bottom-Up** tab of the previous figure is `Parse HTML`.</span></span>  <!--In the flame chart of the previous figure, the yellow below the calls to `wait` are actually thousands of `Minor GC` calls.  -->  <span data-ttu-id="4d10e-281">导航到 " **下** 一步" 选项卡，下一个开销最高的活动是 `Layout` 。</span><span class="sxs-lookup"><span data-stu-id="4d10e-281">Navigate to in the **Bottom-Up** tab, the next most expensive activity is `Layout`.</span></span>  

<span data-ttu-id="4d10e-282">" **自时间** " 列表示在该活动中直接占用的所有事件的总时间。</span><span class="sxs-lookup"><span data-stu-id="4d10e-282">The **Self Time** column represents the aggregated time spent directly in that activity, across all of the occurrences.</span></span>  

<span data-ttu-id="4d10e-283">" **总时间** " 列表示该活动或任何子活动所用的聚合时间。</span><span class="sxs-lookup"><span data-stu-id="4d10e-283">The **Total Time** column represents aggregated time spent in that activity or any of the children.</span></span>  

#### <span data-ttu-id="4d10e-284">"事件日志" 选项卡</span><span class="sxs-lookup"><span data-stu-id="4d10e-284">The Event Log tab</span></span>  

<span data-ttu-id="4d10e-285">使用 " **事件日志** " 选项卡，按录制过程中发生的顺序查看活动。</span><span class="sxs-lookup"><span data-stu-id="4d10e-285">Use the **Event Log** tab to view activities in the order in which they occurred during the recording.</span></span>  

<span data-ttu-id="4d10e-286">" **事件日志** " 选项卡仅显示录制的选定部分中的活动。</span><span class="sxs-lookup"><span data-stu-id="4d10e-286">The **Event Log** tab only displays activities during the selected portion of the recording.</span></span>  <span data-ttu-id="4d10e-287">导航以 [选择录制部分](#select-a-portion-of-a-recording) ，了解如何选择部分内容。</span><span class="sxs-lookup"><span data-stu-id="4d10e-287">Navigate to [Select a portion of a recording](#select-a-portion-of-a-recording) to learn how to select portions.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-event-log.msft.png" alt-text="记录" lightbox="../media/evaluate-performance-performance-event-log.msft.png":::
   <span data-ttu-id="4d10e-289">" **事件日志** " 选项卡</span><span class="sxs-lookup"><span data-stu-id="4d10e-289">The **Event Log** tab</span></span>  
:::image-end:::  

<span data-ttu-id="4d10e-290">" **开始时间** " 列表示活动开始的点，相对于录制的开始时间。</span><span class="sxs-lookup"><span data-stu-id="4d10e-290">The **Start Time** column represents the point at which that activity started, relative to the start of the recording.</span></span>  <span data-ttu-id="4d10e-291">例如， `175.7 ms` 上图中所选项目的开始时间表示活动在录制开始后开始175.7 毫秒。</span><span class="sxs-lookup"><span data-stu-id="4d10e-291">For example, the start time of `175.7 ms` for the selected item in the previous figure means that activity started 175.7 ms after the recording started.</span></span>  

<span data-ttu-id="4d10e-292">" **自时间** " 列表示直接在该活动中花费的时间。</span><span class="sxs-lookup"><span data-stu-id="4d10e-292">The **Self Time** column represents the time spent directly in that activity.</span></span>  

<span data-ttu-id="4d10e-293">" **总时间** " 列表示直接在该活动或任何子活动中所花费的时间。</span><span class="sxs-lookup"><span data-stu-id="4d10e-293">The **Total Time** columns represents time spent directly in that activity or in any of the children.</span></span>  

<span data-ttu-id="4d10e-294">选择 " **开始时间**"、" **自时间**" 或 " **总时间** "，按该列对表格进行排序。</span><span class="sxs-lookup"><span data-stu-id="4d10e-294">Choose **Start Time**, **Self Time**, or **Total Time** to sort the table by that column.</span></span>

<span data-ttu-id="4d10e-295">使用 " **筛选** " 文本框按名称筛选活动。</span><span class="sxs-lookup"><span data-stu-id="4d10e-295">Use the **Filter** text box to filter activities by name.</span></span>  

<span data-ttu-id="4d10e-296">使用 " **工期** " 菜单筛选出所有时间不超过1毫秒或15毫秒的活动。</span><span class="sxs-lookup"><span data-stu-id="4d10e-296">Use the **Duration** menu to filter out any activities that took less than 1 ms or 15 ms.</span></span>  <span data-ttu-id="4d10e-297">默认情况下，" **持续时间** " 菜单设置为 " **全部**"，表示显示所有活动。</span><span class="sxs-lookup"><span data-stu-id="4d10e-297">By default the **Duration** menu is set to **All**, meaning all activities are shown.</span></span>  

<span data-ttu-id="4d10e-298">禁用 **加载**、 **脚本**、 **呈现**或 **绘制** 复选框，以筛选出这些类别中的所有活动。</span><span class="sxs-lookup"><span data-stu-id="4d10e-298">Disable the **Loading**, **Scripting**, **Rendering**, or **Painting** checkboxes to filter out all activities from those categories.</span></span>  

### <span data-ttu-id="4d10e-299">查看 GPU 活动</span><span class="sxs-lookup"><span data-stu-id="4d10e-299">View GPU activity</span></span>  

<span data-ttu-id="4d10e-300">查看 **gpu** 部分中的 gpu 活动。</span><span class="sxs-lookup"><span data-stu-id="4d10e-300">View GPU activity in the **GPU** section.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-gpu-zoomed.msft.png" alt-text="记录" lightbox="../media/evaluate-performance-performance-gpu-zoomed.msft.png":::
   <span data-ttu-id="4d10e-302">**GPU**部分</span><span class="sxs-lookup"><span data-stu-id="4d10e-302">The **GPU** section</span></span>  
:::image-end:::  

### <span data-ttu-id="4d10e-303">查看光栅活动</span><span class="sxs-lookup"><span data-stu-id="4d10e-303">View raster activity</span></span>  

<span data-ttu-id="4d10e-304">查看 **光栅** 区中的 "光栅" 活动。</span><span class="sxs-lookup"><span data-stu-id="4d10e-304">View raster activity in the **Raster** section.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-raster.msft.png" alt-text="记录" lightbox="../media/evaluate-performance-performance-raster.msft.png":::
   <span data-ttu-id="4d10e-306">" **光栅** " 部分</span><span class="sxs-lookup"><span data-stu-id="4d10e-306">The **Raster** section</span></span>  
:::image-end:::  

### <span data-ttu-id="4d10e-307">查看交互</span><span class="sxs-lookup"><span data-stu-id="4d10e-307">View interactions</span></span>  

<span data-ttu-id="4d10e-308">使用 " **交互** " 部分查找和分析录制期间发生的用户交互。</span><span class="sxs-lookup"><span data-stu-id="4d10e-308">Use the **Interactions** section to find and analyze user interactions that happened during the recording.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-interactions-animation.msft.png" alt-text="记录" lightbox="../media/evaluate-performance-performance-interactions-animation.msft.png":::
   <span data-ttu-id="4d10e-310">" **交互** " 部分</span><span class="sxs-lookup"><span data-stu-id="4d10e-310">The **Interactions** section</span></span>  
:::image-end:::  

<span data-ttu-id="4d10e-311">交互底部的红线表示等待主线程所用的时间。</span><span class="sxs-lookup"><span data-stu-id="4d10e-311">A red line at the bottom of an interaction represents time spent waiting for the main thread.</span></span>  

<span data-ttu-id="4d10e-312">单击交互以在 " **摘要** " 选项卡中查看有关它的详细信息。</span><span class="sxs-lookup"><span data-stu-id="4d10e-312">Click an interaction to view more information about it in the **Summary** tab.</span></span>  

### <span data-ttu-id="4d10e-313"> (FPS) 分析每秒帧数</span><span class="sxs-lookup"><span data-stu-id="4d10e-313">Analyze frames per second (FPS)</span></span>  

<span data-ttu-id="4d10e-314">DevTools 提供多种方法来分析每秒帧数：</span><span class="sxs-lookup"><span data-stu-id="4d10e-314">DevTools provides numerous ways to analyze frames per second:</span></span>  

*   <span data-ttu-id="4d10e-315">使用 [fps 图](#the-fps-chart) 大致了解录制期间的 FPS。</span><span class="sxs-lookup"><span data-stu-id="4d10e-315">Use [the FPS chart](#the-fps-chart) to get an overview of FPS over the duration of the recording.</span></span>  
*   <span data-ttu-id="4d10e-316">使用 ["框架" 部分](#the-frames-section) 可查看特定帧所用时间。</span><span class="sxs-lookup"><span data-stu-id="4d10e-316">Use [the Frames section](#the-frames-section) to view how long a particular frame took.</span></span>  
*   <span data-ttu-id="4d10e-317">当页面运行时，使用 **fps 计量** 器以实时估计 fps。</span><span class="sxs-lookup"><span data-stu-id="4d10e-317">Use the **FPS meter** for a realtime estimate of FPS as the page runs.</span></span>  <span data-ttu-id="4d10e-318">导航到 ["每秒查看帧数" 和 "FPS" 计量](#view-frames-per-second-in-realtime-with-the-fps-meter)器。</span><span class="sxs-lookup"><span data-stu-id="4d10e-318">Navigate to [View frames per second in realtime with the FPS meter](#view-frames-per-second-in-realtime-with-the-fps-meter).</span></span>  
    
#### <span data-ttu-id="4d10e-319">FPS 图表</span><span class="sxs-lookup"><span data-stu-id="4d10e-319">The FPS chart</span></span>  

<span data-ttu-id="4d10e-320">**FPS**图表提供整个录制期间的帧速率的概览。</span><span class="sxs-lookup"><span data-stu-id="4d10e-320">The **FPS** chart provides an overview of the frame rate across the duration of a recording.</span></span>  <span data-ttu-id="4d10e-321">通常情况下，绿色条越高，帧速率越好。</span><span class="sxs-lookup"><span data-stu-id="4d10e-321">In general, the higher the green bar, the better the frame rate.</span></span>  

<span data-ttu-id="4d10e-322">**FPS**图表上方的红色条是一条警告，表明帧速率降低的可能会损坏用户的体验。</span><span class="sxs-lookup"><span data-stu-id="4d10e-322">A red bar above the **FPS** chart is a warning that the frame rate dropped so low that it probably harmed the user's experience.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-fps-highlight.msft.png" alt-text="记录" lightbox="../media/evaluate-performance-performance-fps-highlight.msft.png":::
   <span data-ttu-id="4d10e-324">**FPS**图表</span><span class="sxs-lookup"><span data-stu-id="4d10e-324">The **FPS** chart</span></span>  
:::image-end:::  

#### <span data-ttu-id="4d10e-325">"框架" 部分</span><span class="sxs-lookup"><span data-stu-id="4d10e-325">The Frames section</span></span>  

<span data-ttu-id="4d10e-326">" **框架** " 部分告诉你特定帧所花时间的确切时间。</span><span class="sxs-lookup"><span data-stu-id="4d10e-326">The **Frames** section tells you exactly how long a particular frame took.</span></span>  

<span data-ttu-id="4d10e-327">将鼠标悬停在框架上方以查看工具提示，了解有关它的详细信息。</span><span class="sxs-lookup"><span data-stu-id="4d10e-327">Hover over a frame to view a tooltip with more information about it.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-frames-hover.msft.png" alt-text="记录" lightbox="../media/evaluate-performance-performance-frames-hover.msft.png":::
   <span data-ttu-id="4d10e-329">将鼠标悬停在框架上</span><span class="sxs-lookup"><span data-stu-id="4d10e-329">Hover over a frame</span></span>  
:::image-end:::  

<span data-ttu-id="4d10e-330">单击框架可在 " **摘要** " 选项卡中查看有关该帧的详细信息。 DevTools 以蓝色显示所选帧的轮廓。</span><span class="sxs-lookup"><span data-stu-id="4d10e-330">Click on a frame to view even more information about the frame in the **Summary** tab.  DevTools outlines the selected frame in blue.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-frames-summary.msft.png" alt-text="记录" lightbox="../media/evaluate-performance-performance-frames-summary.msft.png":::
   <span data-ttu-id="4d10e-332">在 " **摘要** " 选项卡中查看框架</span><span class="sxs-lookup"><span data-stu-id="4d10e-332">View a frame in the **Summary** tab</span></span>  
:::image-end:::  

### <span data-ttu-id="4d10e-333">查看网络请求</span><span class="sxs-lookup"><span data-stu-id="4d10e-333">View network requests</span></span>  

<span data-ttu-id="4d10e-334">展开 " **网络** " 部分，查看录制期间出现的网络请求的瀑布。</span><span class="sxs-lookup"><span data-stu-id="4d10e-334">Expand the **Network** section to view a waterfall of network requests that occurred during the recording.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-network.msft.png" alt-text="记录" lightbox="../media/evaluate-performance-performance-network.msft.png":::
   <span data-ttu-id="4d10e-336">" **网络** " 部分</span><span class="sxs-lookup"><span data-stu-id="4d10e-336">The **Network** section</span></span>  
:::image-end:::  

<span data-ttu-id="4d10e-337">请求按如下方式进行颜色编码：</span><span class="sxs-lookup"><span data-stu-id="4d10e-337">Requests are color-coded as follows:</span></span>  

*   <span data-ttu-id="4d10e-338">HTML： Blue</span><span class="sxs-lookup"><span data-stu-id="4d10e-338">HTML: Blue</span></span>  
*   <span data-ttu-id="4d10e-339">CSS：紫色</span><span class="sxs-lookup"><span data-stu-id="4d10e-339">CSS: Purple</span></span>  
*   <span data-ttu-id="4d10e-340">JS：黄色</span><span class="sxs-lookup"><span data-stu-id="4d10e-340">JS: Yellow</span></span>  
*   <span data-ttu-id="4d10e-341">图像：绿色</span><span class="sxs-lookup"><span data-stu-id="4d10e-341">Images: Green</span></span>  
    
<span data-ttu-id="4d10e-342">单击请求可在 " **摘要** " 选项卡中查看有关它的详细信息。 例如，在上图中，" **摘要** " 选项卡显示有关 " **网络** " 部分中所选蓝色请求的详细信息。</span><span class="sxs-lookup"><span data-stu-id="4d10e-342">Click on a request to view more information about it in the **Summary** tab.  For example, in the previous figure, the **Summary** tab is displaying more information about the blue request that is selected in the **Network** section.</span></span>  

<span data-ttu-id="4d10e-343">请求左上角的蓝色正方形表示它是优先级较高的请求。</span><span class="sxs-lookup"><span data-stu-id="4d10e-343">A darker-blue square in the top-left of a request means it is a higher-priority request.</span></span>  <span data-ttu-id="4d10e-344">较浅的蓝色正方形意味着优先级较低。</span><span class="sxs-lookup"><span data-stu-id="4d10e-344">A lighter-blue square means lower-priority.</span></span>  <span data-ttu-id="4d10e-345">例如，在上图中，蓝色的选定请求的优先级较高，其下方的绿色为较低优先级。</span><span class="sxs-lookup"><span data-stu-id="4d10e-345">For example, in the previous figure, the blue, selected request is higher-priority, and the green one below it is lower-priority.</span></span>  

<span data-ttu-id="4d10e-346">在下面的第1个数字中，请求由 `www.bing.com` 左侧的一行、中间有一个深色部分和一个浅色部分以及右侧的线条表示。</span><span class="sxs-lookup"><span data-stu-id="4d10e-346">In the 1st of the following figures, the request for `www.bing.com` is represented by a line on the left, a bar in the middle with a dark portion and a light portion, and a line on the right.</span></span>  <span data-ttu-id="4d10e-347">在下图的第二个图中显示了 "**网络**" 面板的 "**计时**" 选项卡中相同请求的对应表示形式。</span><span class="sxs-lookup"><span data-stu-id="4d10e-347">In the 2nd of the following figures shows the corresponding representation of the same request in the **Timing** tab of the **Network** panel.</span></span>  <span data-ttu-id="4d10e-348">下面介绍这两种表示形式如何相互映射：</span><span class="sxs-lookup"><span data-stu-id="4d10e-348">Here is how these two representations map to each other:</span></span>

*   <span data-ttu-id="4d10e-349">左侧线条是所有 `Connection Start` 事件组中的所有内容，包括一组事件。</span><span class="sxs-lookup"><span data-stu-id="4d10e-349">The left line is everything up to the `Connection Start` group of events, inclusive.</span></span>  <span data-ttu-id="4d10e-350">换句话说，它是在独占之前的所有内容 `Request Sent` 。</span><span class="sxs-lookup"><span data-stu-id="4d10e-350">In other words, it is everything before `Request Sent`, exclusive.</span></span>  
*   <span data-ttu-id="4d10e-351">条的灯部分为 `Request Sent` 和 `Waiting (TTFB)` 。</span><span class="sxs-lookup"><span data-stu-id="4d10e-351">The light portion of the bar is `Request Sent` and `Waiting (TTFB)`.</span></span>  
*   <span data-ttu-id="4d10e-352">条的深色部分为 `Content Download` 。</span><span class="sxs-lookup"><span data-stu-id="4d10e-352">The dark portion of the bar is `Content Download`.</span></span>  
*   <span data-ttu-id="4d10e-353">右线实质上是等待主线程所用的时间。</span><span class="sxs-lookup"><span data-stu-id="4d10e-353">The right line is essentially time spent waiting for the main thread.</span></span>  <span data-ttu-id="4d10e-354">这不在 " **计时** " 选项卡中表示。</span><span class="sxs-lookup"><span data-stu-id="4d10e-354">This is not represented in the **Timing** tab.</span></span>  
    
:::row:::
   :::column span="":::
      :::image type="complex" source="../media/evaluate-performance-bing-performance-network.msft.png" alt-text="记录" lightbox="../media/evaluate-performance-bing-performance-network.msft.png":::
         <span data-ttu-id="4d10e-356">请求的行条形图表示形式 `www.bing.com`</span><span class="sxs-lookup"><span data-stu-id="4d10e-356">The line-bar representation of the `www.bing.com` request</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/evaluate-performance-bing-network-timing.msft.png" alt-text="记录" lightbox="../media/evaluate-performance-bing-network-timing.msft.png":::
         <span data-ttu-id="4d10e-358">**网络**工具</span><span class="sxs-lookup"><span data-stu-id="4d10e-358">The **Network** tool</span></span>  
<span data-ttu-id="4d10e-359">：：：图像结束：：：</span><span class="sxs-lookup"><span data-stu-id="4d10e-359">:     ::image-end:::</span></span>  
   :::column-end:::
:::row-end:::

### <span data-ttu-id="4d10e-360">查看内存度量值</span><span class="sxs-lookup"><span data-stu-id="4d10e-360">View memory metrics</span></span>  

<span data-ttu-id="4d10e-361">启用 " **内存** " 复选框以查看上次录制中的内存指标。</span><span class="sxs-lookup"><span data-stu-id="4d10e-361">Enable the **Memory** checkbox to view memory metrics from the last recording.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-memory-highlight.msft.png" alt-text="记录" lightbox="../media/evaluate-performance-performance-memory-highlight.msft.png":::
   <span data-ttu-id="4d10e-363">" **内存** " 复选框</span><span class="sxs-lookup"><span data-stu-id="4d10e-363">The **Memory** checkbox</span></span>  
:::image-end:::  

<span data-ttu-id="4d10e-364">DevTools 将在 "**摘要**" 选项卡上方显示一个新的 "**内存**" 图表。 **NET**图表下方还有一个新图表，称为**堆**。</span><span class="sxs-lookup"><span data-stu-id="4d10e-364">DevTools displays a new **Memory** chart, above the **Summary** tab.  There is also a new chart below the **NET** chart, called **HEAP**.</span></span>  <span data-ttu-id="4d10e-365">**堆**图表提供的信息与**内存**图表中的**JS 堆**行相同。</span><span class="sxs-lookup"><span data-stu-id="4d10e-365">The **HEAP** chart provides the same information as the **JS Heap** line in the **Memory** chart.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-memory-chart.msft.png" alt-text="记录" lightbox="../media/evaluate-performance-performance-memory-chart.msft.png":::
   <span data-ttu-id="4d10e-367">内存指标</span><span class="sxs-lookup"><span data-stu-id="4d10e-367">Memory metrics</span></span>  
:::image-end:::  

<span data-ttu-id="4d10e-368">图表上的彩色线条将映射到图表上方的彩色复选框。</span><span class="sxs-lookup"><span data-stu-id="4d10e-368">The colored lines on the chart map to the colored checkboxes above the chart.</span></span>  
<span data-ttu-id="4d10e-369">禁用复选框以从图表中隐藏该类别。</span><span class="sxs-lookup"><span data-stu-id="4d10e-369">Disable a checkbox to hide that category from the chart.</span></span>  

<span data-ttu-id="4d10e-370">图表仅显示当前所选录制的区域。</span><span class="sxs-lookup"><span data-stu-id="4d10e-370">The chart only displays the region of the recording that is currently selected.</span></span>  <span data-ttu-id="4d10e-371">例如，在上图中，" **内存** " 图表仅显示 400 ms 标记到 1750 ms 标记之间的内存使用。</span><span class="sxs-lookup"><span data-stu-id="4d10e-371">For example, in the previous figure, the **Memory** chart is only showing memory usage from around the 400 ms mark to the 1750 ms mark.</span></span>  

### <span data-ttu-id="4d10e-372">查看部分录制的持续时间</span><span class="sxs-lookup"><span data-stu-id="4d10e-372">View the duration of a portion of a recording</span></span>  

<span data-ttu-id="4d10e-373">分析类似于 **网络** 或 **主**分区的分区时，有时需要对特定事件所花费的时间进行更精确的估计。</span><span class="sxs-lookup"><span data-stu-id="4d10e-373">When analyzing a section like **Network** or **Main**, sometimes you need a more precise estimate of how long certain events took.</span></span>  <span data-ttu-id="4d10e-374">按住 `Shift` ，单击并按住，然后向左或向右拖动以选择部分录制。</span><span class="sxs-lookup"><span data-stu-id="4d10e-374">Hold `Shift`, click and hold, and drag left or right to select a portion of the recording.</span></span>  <span data-ttu-id="4d10e-375">在所选内容的底部，DevTools 显示该部分花费的时间。</span><span class="sxs-lookup"><span data-stu-id="4d10e-375">At the bottom of your selection, DevTools shows how long that portion took.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-main-duration.msft.png" alt-text="记录" lightbox="../media/evaluate-performance-performance-main-duration.msft.png":::
   <span data-ttu-id="4d10e-377">查看部分录制的持续时间</span><span class="sxs-lookup"><span data-stu-id="4d10e-377">View the duration of a portion of a recording</span></span>  
:::image-end:::  

### <span data-ttu-id="4d10e-378">查看屏幕截图</span><span class="sxs-lookup"><span data-stu-id="4d10e-378">View a screenshot</span></span>  

<span data-ttu-id="4d10e-379">[在录制时导航到 "捕获屏幕截图](#capture-screenshots-while-recording)"，了解如何启用屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="4d10e-379">Navigate to [Capture screenshots while recording](#capture-screenshots-while-recording) to learn how to enable screenshots.</span></span>  

<span data-ttu-id="4d10e-380">将鼠标悬停在 **概述** 上以查看屏幕的屏幕截图，了解在录制期间如何查看页面。</span><span class="sxs-lookup"><span data-stu-id="4d10e-380">Hover over the **Overview** to view a screenshot of how the page looked during that moment of the recording.</span></span>  <span data-ttu-id="4d10e-381">**概述**是包含**CPU**、 **FPS**和**NET**图表的部分。</span><span class="sxs-lookup"><span data-stu-id="4d10e-381">The **Overview** is the section that contains the **CPU**, **FPS**, and **NET** charts.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-screenshots-hover.msft.png" alt-text="记录" lightbox="../media/evaluate-performance-performance-screenshots-hover.msft.png":::
   <span data-ttu-id="4d10e-383">查看屏幕截图</span><span class="sxs-lookup"><span data-stu-id="4d10e-383">View a screenshot</span></span>  
:::image-end:::  

<span data-ttu-id="4d10e-384">您也可以通过单击 " **框架** " 部分中的帧来查看屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="4d10e-384">You may also view screenshots by clicking a frame in the **Frames** section.</span></span>  <span data-ttu-id="4d10e-385">DevTools 在 " **摘要** " 选项卡中显示小版本的屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="4d10e-385">DevTools displays a small version of the screenshot in the **Summary** tab.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-summary-preview.msft.png" alt-text="记录" lightbox="../media/evaluate-performance-performance-summary-preview.msft.png":::
   <span data-ttu-id="4d10e-387">在 " **摘要** " 选项卡中查看屏幕截图</span><span class="sxs-lookup"><span data-stu-id="4d10e-387">View a screenshot in the **Summary** tab</span></span>  
:::image-end:::  

<span data-ttu-id="4d10e-388">单击 " **摘要** " 选项卡中的缩略图以放大屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="4d10e-388">Click the thumbnail in the **Summary** tab to zoom in on the screenshot.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-summary-preview-select.msft.png" alt-text="记录" lightbox="../media/evaluate-performance-performance-summary-preview-select.msft.png":::
   <span data-ttu-id="4d10e-390">从 " **摘要** " 选项卡放大显示屏幕截图</span><span class="sxs-lookup"><span data-stu-id="4d10e-390">Zoom into a screenshot from the **Summary** tab</span></span>  
:::image-end:::  

### <span data-ttu-id="4d10e-391">查看层信息</span><span class="sxs-lookup"><span data-stu-id="4d10e-391">View layers information</span></span>  

<span data-ttu-id="4d10e-392">要查看有关框架的高级图层信息，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="4d10e-392">To view advanced layers information about a frame:</span></span>  

1.  <span data-ttu-id="4d10e-393">[启用高级画图工具](#enable-advanced-paint-instrumentation)。</span><span class="sxs-lookup"><span data-stu-id="4d10e-393">[Enable advanced paint instrumentation](#enable-advanced-paint-instrumentation).</span></span>  
1.  <span data-ttu-id="4d10e-394">在 " **框架** " 部分中选择一个帧。</span><span class="sxs-lookup"><span data-stu-id="4d10e-394">Select a frame in the **Frames** section.</span></span>  <span data-ttu-id="4d10e-395">DevTools 显示 "新建 **图层** " 选项卡上 " **事件日志** " 选项卡旁边的图层的信息。</span><span class="sxs-lookup"><span data-stu-id="4d10e-395">DevTools displays information about the layers in the new **Layers** tab, next to the **Event Log** tab.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-layers-all.msft.png" alt-text="记录" lightbox="../media/evaluate-performance-layers-all.msft.png":::
       <span data-ttu-id="4d10e-397">" **图层** " 窗格</span><span class="sxs-lookup"><span data-stu-id="4d10e-397">The **Layers** pane</span></span>  
    :::image-end:::  
    
<span data-ttu-id="4d10e-398">将鼠标悬停在某个图层上，将其在图表中突出显示。</span><span class="sxs-lookup"><span data-stu-id="4d10e-398">Hover over a layer to highlight it in the diagram.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-frames-document-nav-bar-highlighted.msft.png" alt-text="记录" lightbox="../media/evaluate-performance-performance-frames-document-nav-bar-highlighted.msft.png":::
   <span data-ttu-id="4d10e-400">突出显示图层</span><span class="sxs-lookup"><span data-stu-id="4d10e-400">Highlight a layer</span></span>  
:::image-end:::  

<span data-ttu-id="4d10e-401">若要移动图表，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="4d10e-401">To move the diagram:</span></span>  

*   <span data-ttu-id="4d10e-402">选择 " **平移模式** \ (![ 平移模式 ][ImagePanModeIcon] \ ) " 沿 X 轴和 Y 轴移动。</span><span class="sxs-lookup"><span data-stu-id="4d10e-402">Choose **Pan Mode** \(![Pan Mode][ImagePanModeIcon]\) to move along the X and Y axes.</span></span>  
*   <span data-ttu-id="4d10e-403">选择 " **旋转模式** \ (![ 旋转模式 \ ) " ][ImageRotateModeIcon] 沿 Z 轴旋转。</span><span class="sxs-lookup"><span data-stu-id="4d10e-403">Choose **Rotate Mode** \(![Rotate Mode][ImageRotateModeIcon]\) to rotate along the Z axis.</span></span>  
*   <span data-ttu-id="4d10e-404">选择 " **重置转换** \ (![ 重置转换 \" ][ImageResetTransformIcon] ) 将图表重置为原始位置。</span><span class="sxs-lookup"><span data-stu-id="4d10e-404">Choose **Reset Transform** \(![Reset Transform][ImageResetTransformIcon]\) to reset the diagram to the original position.</span></span>  
    
### <span data-ttu-id="4d10e-405">查看画图档案器</span><span class="sxs-lookup"><span data-stu-id="4d10e-405">View paint profiler</span></span>  

<span data-ttu-id="4d10e-406">若要查看有关画图事件的高级信息，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="4d10e-406">To view advanced information about a paint event:</span></span>  

1.  <span data-ttu-id="4d10e-407">[启用高级画图工具](#enable-advanced-paint-instrumentation)。</span><span class="sxs-lookup"><span data-stu-id="4d10e-407">[Enable advanced paint instrumentation](#enable-advanced-paint-instrumentation).</span></span>  
1.  <span data-ttu-id="4d10e-408">在 "**主要**" 部分中选择一个**绘制**事件。</span><span class="sxs-lookup"><span data-stu-id="4d10e-408">Select a **Paint** event in the **Main** section.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-paint-profiler.msft.png" alt-text="记录" lightbox="../media/evaluate-performance-paint-profiler.msft.png":::
       <span data-ttu-id="4d10e-410">" **画图" 事件探查器** 选项卡</span><span class="sxs-lookup"><span data-stu-id="4d10e-410">The **Paint Profiler** tab</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="4d10e-411">使用 "渲染" 选项卡分析渲染性能</span><span class="sxs-lookup"><span data-stu-id="4d10e-411">Analyze rendering performance with the Rendering tab</span></span>  

<span data-ttu-id="4d10e-412">使用 " **呈现** " 选项卡的功能来帮助可视化页面的呈现性能。</span><span class="sxs-lookup"><span data-stu-id="4d10e-412">Use the features of the **Rendering** tab to help visualize the rendering performance of your page.</span></span>  

<span data-ttu-id="4d10e-413">若要打开 " **呈现** " 选项卡：</span><span class="sxs-lookup"><span data-stu-id="4d10e-413">To open the **Rendering** tab:</span></span>  

1.  <span data-ttu-id="4d10e-414">[打开 "命令" 菜单][DevToolsCommandMenu]。</span><span class="sxs-lookup"><span data-stu-id="4d10e-414">[Open the Command Menu][DevToolsCommandMenu].</span></span>  
1.  <span data-ttu-id="4d10e-415">开始键入 `Rendering` 并选择 `Show Rendering` 。</span><span class="sxs-lookup"><span data-stu-id="4d10e-415">Start typing `Rendering` and select `Show Rendering`.</span></span>  <span data-ttu-id="4d10e-416">DevTools 显示 DevTools 窗口底部的 " **呈现** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="4d10e-416">DevTools displays the **Rendering** tab at the bottom of your DevTools window.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-console-drawer-rendering.msft.png" alt-text="记录" lightbox="../media/evaluate-performance-console-drawer-rendering.msft.png":::
       <span data-ttu-id="4d10e-418">" **呈现** " 选项卡</span><span class="sxs-lookup"><span data-stu-id="4d10e-418">The **Rendering** tab</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="4d10e-419">以 FPS 计量器实时查看每秒帧数</span><span class="sxs-lookup"><span data-stu-id="4d10e-419">View frames per second in realtime with the FPS meter</span></span>  

<span data-ttu-id="4d10e-420">**FPS 指示器**是出现在视区右上角的覆盖图。</span><span class="sxs-lookup"><span data-stu-id="4d10e-420">The **FPS meter** is an overlay that appears in the top-right corner of your viewport.</span></span>  <span data-ttu-id="4d10e-421">它在页面运行时提供对 FPS 的实时估计。</span><span class="sxs-lookup"><span data-stu-id="4d10e-421">It provides a realtime estimate of FPS as the page runs.</span></span>  <span data-ttu-id="4d10e-422">要打开 **FPS 指示器**，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="4d10e-422">To open the **FPS meter**:</span></span>  

1.  <span data-ttu-id="4d10e-423">打开 " **呈现** " 选项卡。 Na [通过 "渲染" 选项卡分析渲染性能](#analyze-rendering-performance-with-the-rendering-tab)。</span><span class="sxs-lookup"><span data-stu-id="4d10e-423">Open the **Rendering** tab.  Na [Analyze rendering performance with the Rendering tab](#analyze-rendering-performance-with-the-rendering-tab).</span></span>  
1.  <span data-ttu-id="4d10e-424">启用 " **FPS 指示器** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="4d10e-424">Enable the **FPS Meter** checkbox.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-jank-console-rendering-frame-rate.msft.png" alt-text="记录" lightbox="../media/evaluate-performance-jank-console-rendering-frame-rate.msft.png":::
       <span data-ttu-id="4d10e-426">**FPS 指示器**</span><span class="sxs-lookup"><span data-stu-id="4d10e-426">The **FPS meter**</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="4d10e-427">通过画图闪烁实时查看绘图事件</span><span class="sxs-lookup"><span data-stu-id="4d10e-427">View painting events in realtime with Paint Flashing</span></span>  

<span data-ttu-id="4d10e-428">使用 "绘画闪烁" 获取页面上的所有绘制事件的实时视图。</span><span class="sxs-lookup"><span data-stu-id="4d10e-428">Use Paint Flashing to get a realtime view of all paint events on the page.</span></span>  <span data-ttu-id="4d10e-429">只要重新绘制了页面的一部分，DevTools 将以绿色显示该部分。</span><span class="sxs-lookup"><span data-stu-id="4d10e-429">Whenever a part of the page gets re-painted, DevTools outlines that section in green.</span></span>  

<span data-ttu-id="4d10e-430">启用画图闪烁：</span><span class="sxs-lookup"><span data-stu-id="4d10e-430">To enable Paint Flashing:</span></span>  

1.  <span data-ttu-id="4d10e-431">打开 " **呈现** " 选项卡。 导航到 ["呈现" 选项卡上的 "分析渲染性能"](#analyze-rendering-performance-with-the-rendering-tab)。</span><span class="sxs-lookup"><span data-stu-id="4d10e-431">Open the **Rendering** tab.  Navigate to [Analyze rendering performance with the Rendering tab](#analyze-rendering-performance-with-the-rendering-tab).</span></span>  
1.  <span data-ttu-id="4d10e-432">启用 " **绘画闪烁** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="4d10e-432">Enable the **Paint Flashing** checkbox.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-jank-console-rendering-paint-flashing.msft.png" alt-text="记录" lightbox="../media/evaluate-performance-jank-console-rendering-paint-flashing.msft.png":::
       **<span data-ttu-id="4d10e-434">绘画闪烁</span><span class="sxs-lookup"><span data-stu-id="4d10e-434">Paint Flashing</span></span>**  
    :::image-end:::  
    
### <span data-ttu-id="4d10e-435">查看带有图层边框的图层叠加</span><span class="sxs-lookup"><span data-stu-id="4d10e-435">View an overlay of layers with Layer Borders</span></span>  

<span data-ttu-id="4d10e-436">使用 **图层边框** 查看图层边框和图块在页面顶部的覆盖图。</span><span class="sxs-lookup"><span data-stu-id="4d10e-436">Use **Layer Borders** to view an overlay of layer borders and tiles on top of the page.</span></span>  

<span data-ttu-id="4d10e-437">要启用图层边框，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="4d10e-437">To enable Layer Borders:</span></span>  

1.  <span data-ttu-id="4d10e-438">打开 " **呈现** " 选项卡。 导航到 ["呈现" 选项卡上的 "分析渲染性能"](#analyze-rendering-performance-with-the-rendering-tab)。</span><span class="sxs-lookup"><span data-stu-id="4d10e-438">Open the **Rendering** tab.  Navigate to [Analyze rendering performance with the Rendering tab](#analyze-rendering-performance-with-the-rendering-tab).</span></span>  
1.  <span data-ttu-id="4d10e-439">启用 " **图层边框** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="4d10e-439">Enable the **Layer Borders** checkbox.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-devtools-console-rendering-layer-borders.msft.png" alt-text="记录" lightbox="../media/evaluate-performance-devtools-console-rendering-layer-borders.msft.png":::
       **<span data-ttu-id="4d10e-441">图层边框</span><span class="sxs-lookup"><span data-stu-id="4d10e-441">Layer Borders</span></span>**  
    :::image-end:::  
    
<span data-ttu-id="4d10e-442">导航到 [debug_colors][ChromiumDebugColors] 中的批注，查看 codings 的说明。</span><span class="sxs-lookup"><span data-stu-id="4d10e-442">Navigate to the comments in [debug_colors.cc][ChromiumDebugColors] for an explanation of the color-codings.</span></span>  

### <span data-ttu-id="4d10e-443">查找实时滚动性能问题</span><span class="sxs-lookup"><span data-stu-id="4d10e-443">Find scroll performance issues in realtime</span></span>  

<span data-ttu-id="4d10e-444">使用滚动性能问题来标识页面中具有与滚动相关的事件侦听器的元素，这些事件侦听器可能会损害页面的性能。</span><span class="sxs-lookup"><span data-stu-id="4d10e-444">Use Scrolling Performance Issues to identify elements of the page that have event listeners related to scrolling that may harm the performance of the page.</span></span>  
<span data-ttu-id="4d10e-445">DevTools 概述了蓝色的有问题的元素。</span><span class="sxs-lookup"><span data-stu-id="4d10e-445">DevTools outlines the potentially-problematic elements in teal.</span></span>  

<span data-ttu-id="4d10e-446">要查看滚动性能问题，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="4d10e-446">To view scroll performance issues:</span></span>  

1.  <span data-ttu-id="4d10e-447">打开 " **呈现** " 选项卡。 导航到 ["呈现" 选项卡上的 "分析渲染性能"](#analyze-rendering-performance-with-the-rendering-tab)。</span><span class="sxs-lookup"><span data-stu-id="4d10e-447">Open the **Rendering** tab.  Navigate to [Analyze rendering performance with the Rendering tab](#analyze-rendering-performance-with-the-rendering-tab).</span></span>  
1.  <span data-ttu-id="4d10e-448">启用 " **滚动性能问题** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="4d10e-448">Enable the **Scrolling Performance Issues** checkbox.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-bing-console-drawer-rendering-scrolling-performance-issues.msft.png" alt-text="记录" lightbox="../media/evaluate-performance-bing-console-drawer-rendering-scrolling-performance-issues.msft.png":::
       <span data-ttu-id="4d10e-450">**滚动性能问题** 表示非层视区约束的对象可能会损害滚动性能</span><span class="sxs-lookup"><span data-stu-id="4d10e-450">**Scrolling Performance Issues** indicates that non-layer viewport-constrained objects may harm scroll performance</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="4d10e-451">与 Microsoft Edge 开发人员工具团队联系</span><span class="sxs-lookup"><span data-stu-id="4d10e-451">Getting in touch with the Microsoft Edge DevTools team</span></span>  

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

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) 开发工具 |Microsoft 文档"  
[DevToolsCommandMenu]: ../command-menu/index.md#open-the-command-menu "通过 Microsoft Edge DevTools "命令" 菜单打开命令菜单-运行命令 |Microsoft 文档"  
[DevtoolsEvaluatePerformanceGettingStarted]: ./index.md "分析运行时性能的入门 |Microsoft 文档"  

[ActivityTabsDemo]: https://microsoft-edge-chromium-devtools.glitch.me/perf/activitytabs.html "活动选项卡演示 |故障"  

[ChromiumDebugColors]: https://cs.chromium.org/chromium/src/cc/debug/debug_colors.cc "debug_colors 抄送-代码搜索"  

> [!NOTE]
> <span data-ttu-id="4d10e-457">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="4d10e-457">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="4d10e-458">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/reference)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="4d10e-458">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/reference) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="4d10e-460">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="4d10e-460">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
