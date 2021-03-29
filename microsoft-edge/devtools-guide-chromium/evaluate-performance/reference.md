---
description: 在 Microsoft Edge DevTools 中记录和分析性能所有方法的参考。
title: 性能分析引用
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: e7774dc0aab647b8cf2bf47699368fafe6c21d70
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: HT
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

# <a name="performance-analysis-reference"></a><span data-ttu-id="bef42-104">性能分析引用</span><span class="sxs-lookup"><span data-stu-id="bef42-104">Performance analysis reference</span></span>  

<span data-ttu-id="bef42-105">本页是与分析性能相关 Microsoft Edge DevTools 功能的综合参考。</span><span class="sxs-lookup"><span data-stu-id="bef42-105">This page is a comprehensive reference of Microsoft Edge DevTools features related to analyzing performance.</span></span>  

<span data-ttu-id="bef42-106">导航到 [“分析运行时性能入门”][DevtoolsEvaluatePerformanceGettingStarted]，以获得关于如何使用 [Microsoft Edge DevTools][MicrosoftEdgeDevTools] 分析页面性能的指导教程。</span><span class="sxs-lookup"><span data-stu-id="bef42-106">Navigate to [Get Started With Analyzing Runtime Performance][DevtoolsEvaluatePerformanceGettingStarted] for a guided tutorial on how to analyze the performance of a page using [Microsoft Edge DevTools][MicrosoftEdgeDevTools].</span></span>  

## <a name="record-performance"></a><span data-ttu-id="bef42-107">记录性能</span><span class="sxs-lookup"><span data-stu-id="bef42-107">Record performance</span></span>  

### <a name="record-runtime-performance"></a><span data-ttu-id="bef42-108">记录运行时性能</span><span class="sxs-lookup"><span data-stu-id="bef42-108">Record runtime performance</span></span>  

<span data-ttu-id="bef42-109">当你想在页面运行时 (而非加载时) 分析其性能时，将记录运行时性能。</span><span class="sxs-lookup"><span data-stu-id="bef42-109">Record runtime performance when you want to analyze the performance of a page as it is running, as opposed to loading.</span></span>  

1.  <span data-ttu-id="bef42-110">导航到要分析的页面。</span><span class="sxs-lookup"><span data-stu-id="bef42-110">Navigate to the page that you want to analyze.</span></span>  
1.  <span data-ttu-id="bef42-111">在 DevTools 中打开 **“性能”** 工具。</span><span class="sxs-lookup"><span data-stu-id="bef42-111">Open the **Performance** tool in DevTools.</span></span>  
1.  <span data-ttu-id="bef42-112">选择 **记录** \(![记录图标](../media/record-icon.msft.png)\)。</span><span class="sxs-lookup"><span data-stu-id="bef42-112">Choose **Record** \(![Record icon](../media/record-icon.msft.png)\).</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-performance-record-highlight.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-record-highlight.msft.png":::
       **<span data-ttu-id="bef42-114">Record</span><span class="sxs-lookup"><span data-stu-id="bef42-114">Record</span></span>**  
    :::image-end:::  
    
1.  <span data-ttu-id="bef42-115">与页面交互。</span><span class="sxs-lookup"><span data-stu-id="bef42-115">Interact with the page.</span></span>  <span data-ttu-id="bef42-116">DevTools 将记录由于交互而发生的所有页面活动。</span><span class="sxs-lookup"><span data-stu-id="bef42-116">DevTools records all page activity that occurs as a result of your interactions.</span></span>  
1.  <span data-ttu-id="bef42-117">再次选择 **“记录”** 或选择 **“停止”** 以停止录制。</span><span class="sxs-lookup"><span data-stu-id="bef42-117">Choose **Record** again or choose **Stop** to stop recording.</span></span>  
    
### <a name="record-load-performance"></a><span data-ttu-id="bef42-118">记录加载性能</span><span class="sxs-lookup"><span data-stu-id="bef42-118">Record load performance</span></span>  

<span data-ttu-id="bef42-119">当你想在页面加载时 (而非运行时) 分析其性能时，将记录加载时性能。</span><span class="sxs-lookup"><span data-stu-id="bef42-119">Record load performance when you want to analyze the performance of a page as it is loading, as opposed to running.</span></span>  

1.  <span data-ttu-id="bef42-120">导航到要分析的页面。</span><span class="sxs-lookup"><span data-stu-id="bef42-120">Navigate to the page that you want to analyze.</span></span>  
1.  <span data-ttu-id="bef42-121">打开 DevTools 的 **“性能”** 面板。</span><span class="sxs-lookup"><span data-stu-id="bef42-121">Open the **Performance** panel of DevTools.</span></span>  
1.  <span data-ttu-id="bef42-122">选择 **刷新网页** \(![刷新网页](../media/refresh-page-icon.msft.png)\)。</span><span class="sxs-lookup"><span data-stu-id="bef42-122">Choose **Refresh page** \(![Refresh Page](../media/refresh-page-icon.msft.png)\).</span></span>  <span data-ttu-id="bef42-123">DevTools 在页面刷新时记录性能指标，然后在加载完成后几秒钟自动停止记录。</span><span class="sxs-lookup"><span data-stu-id="bef42-123">DevTools records performance metrics while the page refreshes and then automatically stops the recording a couple seconds after the load finishes.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-performance-refresh-button.msft.png" alt-text="刷新页面" lightbox="../media/evaluate-performance-performance-refresh-button.msft.png":::
       **<span data-ttu-id="bef42-125">刷新页面</span><span class="sxs-lookup"><span data-stu-id="bef42-125">Refresh page</span></span>**  
    :::image-end:::  
    
<span data-ttu-id="bef42-126">DevTools 会自动放大大部分活动发生的记录部分。</span><span class="sxs-lookup"><span data-stu-id="bef42-126">DevTools automatically zooms in on the portion of the recording where most of the activity occurred.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-refreshed.msft.png" alt-text="页面加载录制" lightbox="../media/evaluate-performance-performance-refreshed.msft.png":::
   <span data-ttu-id="bef42-128">页面加载录制</span><span class="sxs-lookup"><span data-stu-id="bef42-128">A page-load recording</span></span>  
:::image-end:::  

### <a name="capture-screenshots-while-recording"></a><span data-ttu-id="bef42-129">录制时捕获屏幕截图</span><span class="sxs-lookup"><span data-stu-id="bef42-129">Capture screenshots while recording</span></span>  

<span data-ttu-id="bef42-130">打开 **“屏幕截图”** 复选框以捕获录制时每帧画面的屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="bef42-130">Turn on the **Screenshots** checkbox to capture a screenshot of every frame while recording.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-capture-screenshots-checkbox.msft.png" alt-text="屏幕截图复选框" lightbox="../media/evaluate-performance-performance-capture-screenshots-checkbox.msft.png":::
   <span data-ttu-id="bef42-132">**屏幕截图** 复选框</span><span class="sxs-lookup"><span data-stu-id="bef42-132">The **Screenshots** checkbox</span></span>  
:::image-end:::  

<span data-ttu-id="bef42-133">导航到 [查看屏幕截图](#view-a-screenshot) 了解如何与屏幕截图进行交互。</span><span class="sxs-lookup"><span data-stu-id="bef42-133">Navigate to [View a screenshot](#view-a-screenshot) to learn how to interact with screenshots.</span></span>  

### <a name="force-garbage-collection-while-recording"></a><span data-ttu-id="bef42-134">录制时强制收集垃圾</span><span class="sxs-lookup"><span data-stu-id="bef42-134">Force garbage collection while recording</span></span>  

<span data-ttu-id="bef42-135">录制页面时，选择 **“回收垃圾”** \(![“回收垃圾图标”](../media/collect-garbage-icon.msft.png)\) 以强制回收垃圾。</span><span class="sxs-lookup"><span data-stu-id="bef42-135">While you are recording a page, choose **Collect garbage** \(![Collect garbage icon](../media/collect-garbage-icon.msft.png)\) to force garbage collection.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-collect-garbage-button.msft.png" alt-text="回收垃圾" lightbox="../media/evaluate-performance-performance-collect-garbage-button.msft.png":::
   <span data-ttu-id="bef42-137">回收垃圾</span><span class="sxs-lookup"><span data-stu-id="bef42-137">Collect garbage</span></span>  
:::image-end:::  

### <a name="show-recording-settings"></a><span data-ttu-id="bef42-138">显示录制设置</span><span class="sxs-lookup"><span data-stu-id="bef42-138">Show recording settings</span></span>  

<span data-ttu-id="bef42-139">选择 **“捕获设置”** \(![捕获设置](../media/capture-settings-icon.msft.png)\) 就可以看到更多与 DevTools 如何捕获性能记录相关的设置。</span><span class="sxs-lookup"><span data-stu-id="bef42-139">Choose **Capture settings** \(![Capture settings](../media/capture-settings-icon.msft.png)\) to expose more settings related to how DevTools captures performance recordings.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-capture-settings-button-open-drawer.msft.png" alt-text=""捕获设置"部分" lightbox="../media/evaluate-performance-performance-capture-settings-button-open-drawer.msft.png":::
   <span data-ttu-id="bef42-141">**“捕获设置”** 部分</span><span class="sxs-lookup"><span data-stu-id="bef42-141">The **Capture Settings** section</span></span>  
:::image-end:::  

### <a name="disable-javascript-samples"></a><span data-ttu-id="bef42-142">禁用 JavaScript 示例</span><span class="sxs-lookup"><span data-stu-id="bef42-142">Disable JavaScript samples</span></span>  

<span data-ttu-id="bef42-143">默认情况下，录制的 **主** 部分会显示录音期间调用的 JavaScript 函数的详细调用栈。</span><span class="sxs-lookup"><span data-stu-id="bef42-143">By default, the **Main** section of a recording displays detailed call stacks of JavaScript functions that were called during the recording.</span></span>  <span data-ttu-id="bef42-144">禁用以下调用堆栈:</span><span class="sxs-lookup"><span data-stu-id="bef42-144">To disable these call stacks:</span></span>  

1.  <span data-ttu-id="bef42-145">打开 **“捕获设置”** 菜单。</span><span class="sxs-lookup"><span data-stu-id="bef42-145">Open the **Capture settings** menu.</span></span>  <span data-ttu-id="bef42-146">导航到 [“显示录制设置”](#show-recording-settings)。</span><span class="sxs-lookup"><span data-stu-id="bef42-146">Navigate to [Show recording settings](#show-recording-settings).</span></span>  
1.  <span data-ttu-id="bef42-147">打开 **“禁用 JavaScript 示例”** 复选框。</span><span class="sxs-lookup"><span data-stu-id="bef42-147">Turn on the **Disable JavaScript Samples** checkbox.</span></span>  
1.  <span data-ttu-id="bef42-148">记录页面。</span><span class="sxs-lookup"><span data-stu-id="bef42-148">Take a recording of the page.</span></span>  
    
<span data-ttu-id="bef42-149">以下 2 张图显示了禁用和启用 JavaScript 样本的区别。</span><span class="sxs-lookup"><span data-stu-id="bef42-149">The following 2 figures display the difference between disabling and enabling JavaScript samples.</span></span>  <span data-ttu-id="bef42-150">当禁用取样时，录音的**主**部分要短得多，因为它省略了所有的 JavaScript 调用堆栈。</span><span class="sxs-lookup"><span data-stu-id="bef42-150">The **Main** section of the recording is much shorter when sampling is disabled, because it omits all of the JavaScript call stacks.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-on.msft.png" alt-text="禁用 JS 示例时的录制示例" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-on.msft.png":::
         <span data-ttu-id="bef42-152">禁用 JS 示例时的录制示例</span><span class="sxs-lookup"><span data-stu-id="bef42-152">An example of a recording when JS samples are disabled</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off.msft.png" alt-text="启用 JS 示例时的录制示例" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off.msft.png":::
         <span data-ttu-id="bef42-154">启用 JS 示例时的录制示例</span><span class="sxs-lookup"><span data-stu-id="bef42-154">An example of a recording when JS samples are turned on</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::

### <a name="throttle-the-network-while-recording"></a><span data-ttu-id="bef42-155">在录制时限制网络</span><span class="sxs-lookup"><span data-stu-id="bef42-155">Throttle the network while recording</span></span>  

<span data-ttu-id="bef42-156">若要在录制时限制网络:</span><span class="sxs-lookup"><span data-stu-id="bef42-156">To throttle the network while recording:</span></span>  

1.  <span data-ttu-id="bef42-157">打开 **“捕获设置”** 菜单。</span><span class="sxs-lookup"><span data-stu-id="bef42-157">Open the **Capture settings** menu.</span></span>  <span data-ttu-id="bef42-158">导航到 [“显示录制设置”](#show-recording-settings)。</span><span class="sxs-lookup"><span data-stu-id="bef42-158">Navigate to [Show recording settings](#show-recording-settings).</span></span>  
1.  <span data-ttu-id="bef42-159">将 **“网络”** 设置为所需的限制级别。</span><span class="sxs-lookup"><span data-stu-id="bef42-159">Set **Network** to the desired level of throttling.</span></span>  
    
### <a name="throttle-the-cpu-while-recording"></a><span data-ttu-id="bef42-160">录制时限制 CPU</span><span class="sxs-lookup"><span data-stu-id="bef42-160">Throttle the CPU while recording</span></span>  

<span data-ttu-id="bef42-161">若要在录制时限制 CPU:</span><span class="sxs-lookup"><span data-stu-id="bef42-161">To throttle the CPU while recording:</span></span>  

1.  <span data-ttu-id="bef42-162">打开 **“捕获设置”** 菜单。</span><span class="sxs-lookup"><span data-stu-id="bef42-162">Open the **Capture settings** menu.</span></span>  <span data-ttu-id="bef42-163">导航到 [“显示录制设置”](#show-recording-settings)。</span><span class="sxs-lookup"><span data-stu-id="bef42-163">Navigate to [Show recording settings](#show-recording-settings).</span></span>  
1.  <span data-ttu-id="bef42-164">将 **“CPU”** 设置为所需的限制级别。</span><span class="sxs-lookup"><span data-stu-id="bef42-164">Set **CPU** to the desired level of throttling.</span></span>  
    
<span data-ttu-id="bef42-165">限制是相对于计算机的功能而言的。</span><span class="sxs-lookup"><span data-stu-id="bef42-165">Throttling is relative to the capabilities of your computer.</span></span>  <span data-ttu-id="bef42-166">例如，**两倍减速** 选项使 CPU 运行速度比正常情况下慢两倍。</span><span class="sxs-lookup"><span data-stu-id="bef42-166">For example, the **2x slowdown** option makes your CPU operate 2 times slower than normal.</span></span>  <span data-ttu-id="bef42-167">DevTools 并不能真正模拟移动设备的 CPU，因为移动设备的体系结构与台式机和笔记本电脑的体系结构截然不同。</span><span class="sxs-lookup"><span data-stu-id="bef42-167">DevTools do not truly simulate the CPUs of mobile devices, because the architecture of mobile devices is very different from that of desktops and laptops.</span></span>  

### <a name="turn-on-advanced-paint-instrumentation"></a><span data-ttu-id="bef42-168">启用高级画图检测工具</span><span class="sxs-lookup"><span data-stu-id="bef42-168">Turn on advanced paint instrumentation</span></span>  

<span data-ttu-id="bef42-169">查看详细画图检测工具:</span><span class="sxs-lookup"><span data-stu-id="bef42-169">To view detailed paint instrumentation:</span></span>  

1.  <span data-ttu-id="bef42-170">打开 **“捕获设置”** 菜单。</span><span class="sxs-lookup"><span data-stu-id="bef42-170">Open the **Capture settings** menu.</span></span>  <span data-ttu-id="bef42-171">导航到 [“显示录制设置”](#show-recording-settings)。</span><span class="sxs-lookup"><span data-stu-id="bef42-171">Navigate to [Show recording settings](#show-recording-settings).</span></span>  
1.  <span data-ttu-id="bef42-172">选中 **“启用画图检测工具 (慢速)”** 复选框。</span><span class="sxs-lookup"><span data-stu-id="bef42-172">Check the **Enable advanced paint instrumentation (slow)** checkbox.</span></span>  

<span data-ttu-id="bef42-173">若要了解如何与画图信息交互，请导航到 [“视图图层”](#view-layers-information) 和 [“视图绘制探查器”](#view-paint-profiler)。</span><span class="sxs-lookup"><span data-stu-id="bef42-173">To learn how to interact with the paint information, navigate to [View layers](#view-layers-information) and [View paint profiler](#view-paint-profiler).</span></span>  

## <a name="save-a-recording"></a><span data-ttu-id="bef42-174">保存录制内容</span><span class="sxs-lookup"><span data-stu-id="bef42-174">Save a recording</span></span>  

<span data-ttu-id="bef42-175">若要保存录制文件，请打开上下文菜单 \(右键单击\)，然后选择 **“保存配置文件”**。</span><span class="sxs-lookup"><span data-stu-id="bef42-175">To save a recording, open the contextual menu \(right-click\), and choose **Save Profile**.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-save-profile.msft.png" alt-text="保存配置文件" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-save-profile.msft.png":::
   **<span data-ttu-id="bef42-177">保存配置文件</span><span class="sxs-lookup"><span data-stu-id="bef42-177">Save Profile</span></span>**  
:::image-end:::  

## <a name="load-a-recording"></a><span data-ttu-id="bef42-178">加载录制</span><span class="sxs-lookup"><span data-stu-id="bef42-178">Load a recording</span></span>  

<span data-ttu-id="bef42-179">若要加载录制文件，请打开上下文菜单 \(右键单击\)，然后选择 **“加载配置文件”**。</span><span class="sxs-lookup"><span data-stu-id="bef42-179">To load a recording, open the contextual menu \(right-click\), and choose **Load Profile**.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-load-profile.msft.png" alt-text="加载配置文件" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-load-profile.msft.png":::
   **<span data-ttu-id="bef42-181">加载配置文件</span><span class="sxs-lookup"><span data-stu-id="bef42-181">Load Profile</span></span>**  
:::image-end:::  

## <a name="clear-the-previous-recording"></a><span data-ttu-id="bef42-182">清除上一记录</span><span class="sxs-lookup"><span data-stu-id="bef42-182">Clear the previous recording</span></span>  

<span data-ttu-id="bef42-183">录制后，选择 **清除录制** \(![清除录制图标](../media/clear-recording-icon.msft.png)\) 以从 **性能** 面板中清除录制。</span><span class="sxs-lookup"><span data-stu-id="bef42-183">After making a recording, choose **Clear recording** \(![Clear recording icon](../media/clear-recording-icon.msft.png)\) to clear that recording from the **Performance** panel.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-clear-button.msft.png" alt-text="清除录制" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-clear-button.msft.png":::
   **<span data-ttu-id="bef42-185">清除录制</span><span class="sxs-lookup"><span data-stu-id="bef42-185">Clear recording</span></span>**  
:::image-end:::  

## <a name="analyze-a-performance-recording"></a><span data-ttu-id="bef42-186">分析性能录制</span><span class="sxs-lookup"><span data-stu-id="bef42-186">Analyze a performance recording</span></span>  

<span data-ttu-id="bef42-187">在 [录制运行性能](#record-runtime-performance) 或 [录制加载性能](#record-load-performance) 之后， **性能** 面板将提供许多数据以分析刚发生的操作的性能。</span><span class="sxs-lookup"><span data-stu-id="bef42-187">After you [record runtime performance](#record-runtime-performance) or [record load performance](#record-load-performance), the **Performance** panel provides a lot of data for analyzing the performance of what just happened.</span></span>  

### <a name="select-a-portion-of-a-recording"></a><span data-ttu-id="bef42-188">选择录制的一部分</span><span class="sxs-lookup"><span data-stu-id="bef42-188">Select a portion of a recording</span></span>  

<span data-ttu-id="bef42-189">在 **“概述”** 上向左或向右拖动鼠标，以选择一段录音的一部分。</span><span class="sxs-lookup"><span data-stu-id="bef42-189">Drag your mouse left or right across the **Overview** to select a portion of a recording.</span></span>  <span data-ttu-id="bef42-190">**概述** 是包含 **FPS**、**CPU** 和 **NET** 图表的部分。</span><span class="sxs-lookup"><span data-stu-id="bef42-190">The **Overview** is the section that contains the **FPS**, **CPU**, and **NET** charts.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-zoom-highlighted.msft.png" alt-text="拖动鼠标在“概述”上进行缩放" lightbox="../media/evaluate-performance-performance-zoom-highlighted.msft.png":::
   <span data-ttu-id="bef42-192">将鼠标悬停在 **“概述”** 上进行缩放</span><span class="sxs-lookup"><span data-stu-id="bef42-192">Drag the mouse across the **Overview** to zoom</span></span>  
:::image-end:::  

<span data-ttu-id="bef42-193">若要使用键盘选择一部分:</span><span class="sxs-lookup"><span data-stu-id="bef42-193">To select a portion using the keyboard:</span></span>  

1.  <span data-ttu-id="bef42-194">选择 **主** 部分的背景或它旁边的任何分区，例如 **交互**、 **网络**或 **GPU**。</span><span class="sxs-lookup"><span data-stu-id="bef42-194">Choose the background of the **Main** section, or any of the sections next to it, such as **Interactions**, **Network**, or **GPU**.</span></span>  <span data-ttu-id="bef42-195">此键盘工作流仅在其中一个分区为焦点时有效。</span><span class="sxs-lookup"><span data-stu-id="bef42-195">This keyboard workflow only works when one of these sections is in focus.</span></span>  
1.  <span data-ttu-id="bef42-196">使用 `W`、`A`、`S`、`D` 键分别进行放大、向左移动、缩小和向右移动。</span><span class="sxs-lookup"><span data-stu-id="bef42-196">Use the `W`, `A`, `S`, `D` keys to zoom in, move left, zoom out, and move right, respectively.</span></span>  

<span data-ttu-id="bef42-197">若要使用触控板选择一部分，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="bef42-197">To select a portion using a trackpad, complete the following actions.</span></span>  

1.  <span data-ttu-id="bef42-198">将鼠标悬停在 **“概述”** 部分或 **“详细信息”** 上。</span><span class="sxs-lookup"><span data-stu-id="bef42-198">Hover your mouse over the **Overview** section or the **Details** section.</span></span>  <span data-ttu-id="bef42-199">**概述** 部分是包含 **FPS**、**CPU** 和 **NET** 图表的区域。</span><span class="sxs-lookup"><span data-stu-id="bef42-199">The **Overview** section is the area containing the **FPS**, **CPU**, and **NET** charts.</span></span>  <span data-ttu-id="bef42-200">**详细信息** 部分是包含 **主** 部分、**交互** 部分等的区域。</span><span class="sxs-lookup"><span data-stu-id="bef42-200">The **Details** section is the area containing the **Main** section, the **Interactions** section, and so on.</span></span>  
1.  <span data-ttu-id="bef42-201">使用两根手指，向上轻扫进行缩小，向左轻扫向左移动，向下轻扫进行放大，向右轻扫向右移动。</span><span class="sxs-lookup"><span data-stu-id="bef42-201">Using two fingers, swipe up to zoom out, swipe left to move left, swipe down to zoom in, and swipe right to move right.</span></span>  

<span data-ttu-id="bef42-202">若要在 **主** 区域或任何一个邻区滚动长火焰图，请选择并按住鼠标同时上下拖动。</span><span class="sxs-lookup"><span data-stu-id="bef42-202">To scroll a long flame chart in the **Main** section or any of the neighbors, choose and hold while dragging up and down.</span></span>  <span data-ttu-id="bef42-203">向左和向右拖动，移动录音中所选的部分。</span><span class="sxs-lookup"><span data-stu-id="bef42-203">Drag left and right to move what portion of the recording is chosen.</span></span>  

### <a name="search-activities"></a><span data-ttu-id="bef42-204">搜索活动</span><span class="sxs-lookup"><span data-stu-id="bef42-204">Search activities</span></span>  

<span data-ttu-id="bef42-205">选择 `Control`+`F` \(Windows，Linux\) 或 `Command`+`F` \(macOS\) 以打开**性能**面板底部的搜索框。</span><span class="sxs-lookup"><span data-stu-id="bef42-205">Select `Control`+`F` \(Windows, Linux\) or `Command`+`F` \(macOS\) to open the search box at the bottom of the **Performance** panel.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-search-regex.msft.png" alt-text="搜索框" lightbox="../media/evaluate-performance-performance-search-regex.msft.png":::
   <span data-ttu-id="bef42-207">搜索框</span><span class="sxs-lookup"><span data-stu-id="bef42-207">The search box</span></span>  
:::image-end:::  

<span data-ttu-id="bef42-208">导航与查询匹配的活动:</span><span class="sxs-lookup"><span data-stu-id="bef42-208">To navigate activities that match your query:</span></span>  

*   <span data-ttu-id="bef42-209">使用 **上一步** \(![上一步](../media/previous-icon.msft.png)\) 和 **下一步** \(![下一步](../media/next-icon.msft.png)\) 按钮。</span><span class="sxs-lookup"><span data-stu-id="bef42-209">Use the **Previous** \(![Previous](../media/previous-icon.msft.png)\) and **Next** \(![Next](../media/next-icon.msft.png)\) buttons.</span></span>  
*   <span data-ttu-id="bef42-210">选择 `Shift`+`Enter` 来选择上一步或 `Enter` 来选择下一步。</span><span class="sxs-lookup"><span data-stu-id="bef42-210">Select `Shift`+`Enter` to select the previous or `Enter` to select the next.</span></span>  

<span data-ttu-id="bef42-211">修改查询设置:</span><span class="sxs-lookup"><span data-stu-id="bef42-211">To modify query settings:</span></span>  

*   <span data-ttu-id="bef42-212">选择 **区分大小写** \(![区分大小写](../media/search-case-icon.msft.png)\)，使查询区分大小写。</span><span class="sxs-lookup"><span data-stu-id="bef42-212">Choose **Case sensitive** \(![Case sensitive](../media/search-case-icon.msft.png)\) to make the query case sensitive.</span></span>  
*   <span data-ttu-id="bef42-213">选择 **正则表达式** \(![正则表达式](../media/search-regex-icon.msft.png)\) ，在查询中使用正则表达式。</span><span class="sxs-lookup"><span data-stu-id="bef42-213">Choose **Regex** \(![Regex](../media/search-regex-icon.msft.png)\) to use a regular expression in your query.</span></span>  

<span data-ttu-id="bef42-214">若要隐藏搜索框，请选择 **“取消”**。</span><span class="sxs-lookup"><span data-stu-id="bef42-214">To hide the search box, choose **Cancel**.</span></span>  

### <a name="view-main-thread-activity"></a><span data-ttu-id="bef42-215">查看主线程活动</span><span class="sxs-lookup"><span data-stu-id="bef42-215">View main thread activity</span></span>  

<span data-ttu-id="bef42-216">使用 **主** 部分查看出现在页面主线程上的活动。</span><span class="sxs-lookup"><span data-stu-id="bef42-216">Use the **Main** section to view activity that occurred on the main thread of the page.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-main-zoomed.msft.png" alt-text="主要部分" lightbox="../media/evaluate-performance-performance-main-zoomed.msft.png":::
   <span data-ttu-id="bef42-218">**主要**部分</span><span class="sxs-lookup"><span data-stu-id="bef42-218">The **Main** section</span></span>  
:::image-end:::  

<span data-ttu-id="bef42-219">选择一个事件以在 **“摘要”** 面板中查看更多相关信息。</span><span class="sxs-lookup"><span data-stu-id="bef42-219">Choose an event to view more information about it in the **Summary** panel.</span></span>  <span data-ttu-id="bef42-220">DevTools 概括了所选事件。</span><span class="sxs-lookup"><span data-stu-id="bef42-220">DevTools outlines the selected event.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-summary-me.msft.png" alt-text="更多关于摘要面板中匿名函数的信息。" lightbox="../media/evaluate-performance-performance-summary-me.msft.png":::
   <span data-ttu-id="bef42-222">更多关于 **“摘要”** 面板中的 `anonymous` 功能的信息</span><span class="sxs-lookup"><span data-stu-id="bef42-222">More information about the `anonymous` function in the **Summary** panel</span></span>  
:::image-end:::  

<span data-ttu-id="bef42-223">DevTools 使用火焰图表示主线程活动。</span><span class="sxs-lookup"><span data-stu-id="bef42-223">DevTools represents main thread activity with a flame chart.</span></span>  <span data-ttu-id="bef42-224">x 轴表示一段时间内的记录。</span><span class="sxs-lookup"><span data-stu-id="bef42-224">The x-axis represents the recording over time.</span></span>  <span data-ttu-id="bef42-225">Y 轴表示调用堆叠。</span><span class="sxs-lookup"><span data-stu-id="bef42-225">The y-axis represents the call stack.</span></span>  <span data-ttu-id="bef42-226">顶部事件将导致其下方事件。</span><span class="sxs-lookup"><span data-stu-id="bef42-226">The events on top cause the events below it.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-main-flame-chart.msft.png" alt-text="火焰图" lightbox="../media/evaluate-performance-performance-main-flame-chart.msft.png":::
   <span data-ttu-id="bef42-228">火焰图</span><span class="sxs-lookup"><span data-stu-id="bef42-228">A flame chart</span></span>  
:::image-end:::  

<span data-ttu-id="bef42-229">在上一图中，`click` 事件在 53 行的 `activitytabs.js` 中造成了 `Function Call`。</span><span class="sxs-lookup"><span data-stu-id="bef42-229">In the previous figure, a `click` event caused a `Function Call` in `activitytabs.js` on line 53.</span></span>  <span data-ttu-id="bef42-230">在 `Function Call` 下面，查看匿名函数运行。</span><span class="sxs-lookup"><span data-stu-id="bef42-230">Below `Function Call`, review that an anonymous function was run.</span></span>  <span data-ttu-id="bef42-231">匿名函数请求 `Minor GC`的请求 `wait`的请求 `a`。</span><span class="sxs-lookup"><span data-stu-id="bef42-231">The anonymous function requested `a`, which requested `wait`, which requested `Minor GC`.</span></span>  

<span data-ttu-id="bef42-232">DevTools 为脚本随机分配颜色。</span><span class="sxs-lookup"><span data-stu-id="bef42-232">DevTools assigns scripts random colors.</span></span>  <span data-ttu-id="bef42-233">在上图中，请求来自脚本的函数请求染成为浅绿色。</span><span class="sxs-lookup"><span data-stu-id="bef42-233">In the previous figure, function requests from one script are colored light green.</span></span>  <span data-ttu-id="bef42-234">来自另一个脚本的请求以米色表示。</span><span class="sxs-lookup"><span data-stu-id="bef42-234">Requests from another script are colored beige.</span></span>  <span data-ttu-id="bef42-235">深黄色代表脚本活动，紫色事件代表渲染活动。</span><span class="sxs-lookup"><span data-stu-id="bef42-235">The darker yellow represents scripting activity, and the purple event represents rendering activity.</span></span>  <span data-ttu-id="bef42-236">这些深黄色和紫色事件在所有记录中都是一致的。</span><span class="sxs-lookup"><span data-stu-id="bef42-236">These darker yellow and purple events are consistent across all recordings.</span></span>  

<span data-ttu-id="bef42-237">若要隐藏 JavaScript 请求的详细火焰图，请导航到 [禁用 JavaScript 事例](#disable-javascript-samples)。</span><span class="sxs-lookup"><span data-stu-id="bef42-237">Navigate to [Disable JavaScript samples](#disable-javascript-samples) if you want to hide the detailed flame chart of JavaScript requests.</span></span>  <span data-ttu-id="bef42-238">禁用 JS 示例时，只显示上图中 `str` 中的 `Event: choose` 和 `Function Call` 等高级事件。</span><span class="sxs-lookup"><span data-stu-id="bef42-238">When JS samples are disabled, only high-level events such as `Event: choose` and `Function Call` from the previous figure `str` displayed.</span></span>  

### <a name="view-activities-in-a-table"></a><span data-ttu-id="bef42-239">查看表格中的活动</span><span class="sxs-lookup"><span data-stu-id="bef42-239">View activities in a table</span></span>  

<span data-ttu-id="bef42-240">录制页面后，无需仅依靠 **“主”** 部分来分析活动。</span><span class="sxs-lookup"><span data-stu-id="bef42-240">After recording a page, you do not need to rely solely on the **Main** section to analyze activities.</span></span>  <span data-ttu-id="bef42-241">DevTools 还提供了三种用于分析活动的表格视图。</span><span class="sxs-lookup"><span data-stu-id="bef42-241">DevTools also provides three tabular views for analyzing activities.</span></span>  <span data-ttu-id="bef42-242">每个视图提供对待活动的不同视角:</span><span class="sxs-lookup"><span data-stu-id="bef42-242">Each view gives you a different perspective on the activities:</span></span>  

*   <span data-ttu-id="bef42-243">当想查看导致最多工作的根活动时，请使用 [“调用树”](#the-call-tree-panel) 面板。</span><span class="sxs-lookup"><span data-stu-id="bef42-243">When you want to view the root activities that cause the most work, use the [Call Tree](#the-call-tree-panel) panel.</span></span>  
*   <span data-ttu-id="bef42-244">当想查看直接花费时间最多的活动时，请使用 [“自下而上”](#the-bottom-up-panel) 面板。</span><span class="sxs-lookup"><span data-stu-id="bef42-244">When you want to view the activities where the most time was directly spent, use the [Bottom-Up](#the-bottom-up-panel) panel.</span></span>  
*   <span data-ttu-id="bef42-245">当想按照记录期间发生的顺序查看活动时，请使用 [“事件日志”](#the-event-log-panel) 面板。</span><span class="sxs-lookup"><span data-stu-id="bef42-245">When you want to view the activities in the order in which they occurred during the recording, use the [Event Log](#the-event-log-panel) panel.</span></span>  
    
> [!NOTE]
> <span data-ttu-id="bef42-246">接下来的三个部分均指向相同的演示。</span><span class="sxs-lookup"><span data-stu-id="bef42-246">The next three sections all refer to the same demo.</span></span>  <span data-ttu-id="bef42-247">在 [“活动选项卡演示”][ActivityTabsDemo] 中自己运行演示。</span><span class="sxs-lookup"><span data-stu-id="bef42-247">Run the demo yourself at [Activity Tabs Demo][ActivityTabsDemo].</span></span>  

#### <a name="root-activities"></a><span data-ttu-id="bef42-248">根活动</span><span class="sxs-lookup"><span data-stu-id="bef42-248">Root activities</span></span>  

<span data-ttu-id="bef42-249">下面就 **“调用树”** 面板、**“自下而上”** 面板和 **“事件日志”** 面板中提到的 **“根活动”** 概念进行说明。</span><span class="sxs-lookup"><span data-stu-id="bef42-249">Here is an explanation of the **root activities** concept that is mentioned in the **Call Tree** panel, **Bottom-Up** panel, and **Event Log** panel.</span></span>  

<span data-ttu-id="bef42-250">根活动是指那些导致浏览器执行的一些操作。</span><span class="sxs-lookup"><span data-stu-id="bef42-250">Root activities are those which cause the browser to do some work.</span></span>  <span data-ttu-id="bef42-251">例如，选择网页时，浏览器将运行 `Event` 活动作为根活动。</span><span class="sxs-lookup"><span data-stu-id="bef42-251">For example, when you choose a webpage, the browser runs an `Event` activity as the root activity.</span></span>  <span data-ttu-id="bef42-252">`Event` 可能会导致处理程序运行等。</span><span class="sxs-lookup"><span data-stu-id="bef42-252">That `Event` may cause a handler to run, and so on.</span></span>  

<span data-ttu-id="bef42-253">在 **主** 部分的火焰图中，根活动位于图表顶部。</span><span class="sxs-lookup"><span data-stu-id="bef42-253">In the flame chart of the **Main** section, root activities are at the top of the chart.</span></span>  <span data-ttu-id="bef42-254">在 **“调用树”** 和 **“活动日志”** 面板中，根活动是顶级项目。</span><span class="sxs-lookup"><span data-stu-id="bef42-254">In the **Call Tree** and **Event Log** panels, root activities are the top-level items.</span></span>  

<span data-ttu-id="bef42-255">导航到 [“调用树”](#the-call-tree-panel) 面板，查看根活动示例。</span><span class="sxs-lookup"><span data-stu-id="bef42-255">Navigate to the [Call Tree](#the-call-tree-panel) panel for an example of root activities.</span></span>  

#### <a name="the-call-tree-panel"></a><span data-ttu-id="bef42-256">“调用树”面板</span><span class="sxs-lookup"><span data-stu-id="bef42-256">The Call Tree panel</span></span>  

<span data-ttu-id="bef42-257">使用 **“呼叫树”** 查看哪些 [“根活动”](#root-activities) 导致的工作量最大。</span><span class="sxs-lookup"><span data-stu-id="bef42-257">Use the **Call Tree** panel to view which [root activities](#root-activities) cause the most work.</span></span>  

<span data-ttu-id="bef42-258">**“呼叫树”** 面板仅在录制的选定部分期间显示活动。</span><span class="sxs-lookup"><span data-stu-id="bef42-258">The **Call Tree** panel only displays activities during the selected portion of the recording.</span></span>  <span data-ttu-id="bef42-259">导航到 [“请选择记录的一部分”](#select-a-portion-of-a-recording) 以了解如何选择部分。</span><span class="sxs-lookup"><span data-stu-id="bef42-259">Navigate to [Select a portion of a recording](#select-a-portion-of-a-recording) to learn how to select portions.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-call-tree.msft.png" alt-text="“调用树”面板" lightbox="../media/evaluate-performance-performance-call-tree.msft.png":::
   <span data-ttu-id="bef42-261">**“调用树”** 面板</span><span class="sxs-lookup"><span data-stu-id="bef42-261">The **Call Tree** panel</span></span>  
:::image-end:::  

<span data-ttu-id="bef42-262">在上图中，**“活动”** 列中的顶级项目，如 `Evaluate Script` 和 `Parse HTML` 是根活动。</span><span class="sxs-lookup"><span data-stu-id="bef42-262">In the previous figure, the top-level of items in the **Activity** column, such as `Evaluate Script` and `Parse HTML` are root activities.</span></span>  <span data-ttu-id="bef42-263">嵌套表示调用堆栈。</span><span class="sxs-lookup"><span data-stu-id="bef42-263">The nesting represents the call stack.</span></span>  <span data-ttu-id="bef42-264">例如，在上图中，导致 `Compile Script` 和 `(anonymous)` 的 `Evaluate Script` 的 `Parse HTML`。</span><span class="sxs-lookup"><span data-stu-id="bef42-264">For example, in the previous figure, `Parse HTML` which caused `Evaluate Script` which caused `Compile Script` and `(anonymous)`.</span></span>  

<span data-ttu-id="bef42-265">**“自我时间”** 表示直接用于该活动的时间。</span><span class="sxs-lookup"><span data-stu-id="bef42-265">**Self Time** represents the time directly spent in that activity.</span></span>  <span data-ttu-id="bef42-266">**“总时间”** 表示花在该活动或任何子项上的时间。</span><span class="sxs-lookup"><span data-stu-id="bef42-266">**Total Time** represents the time spent in that activity or any of the children.</span></span>  

<span data-ttu-id="bef42-267">选择 **“自我时间”**、**“总时间”** 或 **“活动”**，按该列对表进行排序。</span><span class="sxs-lookup"><span data-stu-id="bef42-267">Choose **Self Time**, **Total Time**, or **Activity** to sort the table by that column.</span></span>  

<span data-ttu-id="bef42-268">使用 **“筛选器”** 文本框按活动名称筛选事件。</span><span class="sxs-lookup"><span data-stu-id="bef42-268">Use the **Filter** text box to filter events by activity name.</span></span>  

<span data-ttu-id="bef42-269">默认情况下，**“分组”** 菜单设置为 **“无分组”**。</span><span class="sxs-lookup"><span data-stu-id="bef42-269">By default the **Grouping** menu is set to **No Grouping**.</span></span>  <span data-ttu-id="bef42-270">使用 **“分组”** 菜单，根据各种条件对活动表进行排序。</span><span class="sxs-lookup"><span data-stu-id="bef42-270">Use the **Grouping** menu to sort the activity table based on various criteria.</span></span>  

<span data-ttu-id="bef42-271">选择 **“显示最重堆叠** \(![显示最重堆叠](../media/show-heaviest-stack-icon.msft.png)\) 以显示 **“活动“** 表右侧的另一个表。</span><span class="sxs-lookup"><span data-stu-id="bef42-271">Choose **Show Heaviest Stack** \(![Show Heaviest Stack](../media/show-heaviest-stack-icon.msft.png)\) to reveal another table to the right of the **Activity** table.</span></span>  <span data-ttu-id="bef42-272">选择一个活动来填充 **最重堆叠** 表。</span><span class="sxs-lookup"><span data-stu-id="bef42-272">Choose an activity to populate the **Heaviest Stack** table.</span></span>  <span data-ttu-id="bef42-273">**“最重堆栈”** 表显示所选活动的子项需要最长的运行时间。</span><span class="sxs-lookup"><span data-stu-id="bef42-273">The **Heaviest Stack** table displays which children of the selected activity took the longest time to run.</span></span>  

#### <a name="the-bottom-up-panel"></a><span data-ttu-id="bef42-274">“自下而上”面板</span><span class="sxs-lookup"><span data-stu-id="bef42-274">The Bottom-Up panel</span></span>  

<span data-ttu-id="bef42-275">使用 **“自下而上”** 面板查看直接采用聚合时间的活动。</span><span class="sxs-lookup"><span data-stu-id="bef42-275">Use the **Bottom-Up** panel to view which activities directly took up the most time in aggregate.</span></span>  

<span data-ttu-id="bef42-276">**“自下向上”** 面板仅在录制的选定部分期间显示活动。</span><span class="sxs-lookup"><span data-stu-id="bef42-276">The **Bottom-Up** panel only displays activities during the selected portion of the recording.</span></span>  <span data-ttu-id="bef42-277">导航到 [“请选择记录的一部分”](#select-a-portion-of-a-recording) 以了解如何选择部分。</span><span class="sxs-lookup"><span data-stu-id="bef42-277">Navigate to [Select a portion of a recording](#select-a-portion-of-a-recording) to learn how to select portions.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-bottoms-up.msft.png" alt-text="“自下而上”面板" lightbox="../media/evaluate-performance-performance-bottoms-up.msft.png":::
   <span data-ttu-id="bef42-279">**“自下而上”** 面板</span><span class="sxs-lookup"><span data-stu-id="bef42-279">The **Bottom-Up** panel</span></span>  
:::image-end:::  

<span data-ttu-id="bef42-280">在前图的 **主** 分区火焰图中，导航到几乎实践上所有时间都花费在运行 `Parse HTML` 上。</span><span class="sxs-lookup"><span data-stu-id="bef42-280">In the **Main** section flame chart of the previous figure, navigate to that almost practically all of the time was spent running `Parse HTML`.</span></span>  <span data-ttu-id="bef42-281">前图中 **“自下而上”** 面板中最上面的活动是 `Parse HTML`。</span><span class="sxs-lookup"><span data-stu-id="bef42-281">The top activity in the **Bottom-Up** panel of the previous figure is `Parse HTML`.</span></span>  <!--In the flame chart of the previous figure, the yellow below the calls to `wait` are actually thousands of `Minor GC` calls.  -->  <span data-ttu-id="bef42-282">导航到 **“自下向上”** 面板，接下来最昂贵的活动是 `Layout`。</span><span class="sxs-lookup"><span data-stu-id="bef42-282">Navigate to the **Bottom-Up** panel, the next most expensive activity is `Layout`.</span></span>  

<span data-ttu-id="bef42-283">**“自我时间”** 列表示跨越发生的所有直接用于该活动的聚合时间。</span><span class="sxs-lookup"><span data-stu-id="bef42-283">The **Self Time** column represents the aggregated time spent directly in that activity, across all of the occurrences.</span></span>  

<span data-ttu-id="bef42-284">**“总时间”** 列表示花在该活动或任何子项上的聚合时间。</span><span class="sxs-lookup"><span data-stu-id="bef42-284">The **Total Time** column represents aggregated time spent in that activity or any of the children.</span></span>  

#### <a name="the-event-log-panel"></a><span data-ttu-id="bef42-285">事件日志面板</span><span class="sxs-lookup"><span data-stu-id="bef42-285">The Event Log panel</span></span>  

<span data-ttu-id="bef42-286">使用 **“事件日志”** 面板按记录期间发生的顺序查看活动。</span><span class="sxs-lookup"><span data-stu-id="bef42-286">Use the **Event Log** panel to view activities in the order in which they occurred during the recording.</span></span>  

<span data-ttu-id="bef42-287">**“事件日志”** 面板仅显示录制的选定部分期间的活动。</span><span class="sxs-lookup"><span data-stu-id="bef42-287">The **Event Log** panel only displays activities during the selected portion of the recording.</span></span>  <span data-ttu-id="bef42-288">导航到 [“请选择记录的一部分”](#select-a-portion-of-a-recording) 以了解如何选择部分。</span><span class="sxs-lookup"><span data-stu-id="bef42-288">Navigate to [Select a portion of a recording](#select-a-portion-of-a-recording) to learn how to select portions.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-event-log.msft.png" alt-text="事件日志面板" lightbox="../media/evaluate-performance-performance-event-log.msft.png":::
   <span data-ttu-id="bef42-290">**事件日志** 面板</span><span class="sxs-lookup"><span data-stu-id="bef42-290">The **Event Log** panel</span></span>  
:::image-end:::  

<span data-ttu-id="bef42-291">**“开始时间”** 列表示活动开始时与录制开始相对的点。</span><span class="sxs-lookup"><span data-stu-id="bef42-291">The **Start Time** column represents the point at which that activity started, relative to the start of the recording.</span></span>  <span data-ttu-id="bef42-292">例如，上图中所选项目 `175.7 ms` 的开始时间意味着录制开始 175.7 毫秒后活动开始。</span><span class="sxs-lookup"><span data-stu-id="bef42-292">For example, the start time of `175.7 ms` for the selected item in the previous figure means that activity started 175.7 ms after the recording started.</span></span>  

<span data-ttu-id="bef42-293">**“自我时间”** 列表示直接用于该活动的时间。</span><span class="sxs-lookup"><span data-stu-id="bef42-293">The **Self Time** column represents the time spent directly in that activity.</span></span>  

<span data-ttu-id="bef42-294">**“总时间”** 列表示直接用于该活动或任何子项中的时间。</span><span class="sxs-lookup"><span data-stu-id="bef42-294">The **Total Time** columns represents time spent directly in that activity or in any of the children.</span></span>  

<span data-ttu-id="bef42-295">选择 **“开始时间”**、**“自我时间”** 或 **“总时间”** 按该列对表进行排序。</span><span class="sxs-lookup"><span data-stu-id="bef42-295">Choose **Start Time**, **Self Time**, or **Total Time** to sort the table by that column.</span></span>

<span data-ttu-id="bef42-296">使用 **“筛选”** 文本框按名称筛选活动。</span><span class="sxs-lookup"><span data-stu-id="bef42-296">Use the **Filter** text box to filter activities by name.</span></span>  

<span data-ttu-id="bef42-297">使用 **“持续时间”** 菜单筛选出所有耗时少于 1 毫秒或 15 毫秒的活动。</span><span class="sxs-lookup"><span data-stu-id="bef42-297">Use the **Duration** menu to filter out any activities that took less than 1 ms or 15 ms.</span></span>  <span data-ttu-id="bef42-298">默认情况下，**“持续时间”** 菜单设置为 **“全部”**，这意味着会显示所有活动。</span><span class="sxs-lookup"><span data-stu-id="bef42-298">By default the **Duration** menu is set to **All**, meaning all activities are shown.</span></span>  

<span data-ttu-id="bef42-299">禁用 **加载**、 **脚本**、 **渲染**或 **绘制** 复选框以筛选这些类别中的所有活动。</span><span class="sxs-lookup"><span data-stu-id="bef42-299">Disable the **Loading**, **Scripting**, **Rendering**, or **Painting** checkboxes to filter out all activities from those categories.</span></span>  

### <a name="view-gpu-activity"></a><span data-ttu-id="bef42-300">查看 GPU 活动</span><span class="sxs-lookup"><span data-stu-id="bef42-300">View GPU activity</span></span>  

<span data-ttu-id="bef42-301">在 **GPU** 部分查看 GPU 活动。</span><span class="sxs-lookup"><span data-stu-id="bef42-301">View GPU activity in the **GPU** section.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-gpu-zoomed.msft.png" alt-text="GPU 部分" lightbox="../media/evaluate-performance-performance-gpu-zoomed.msft.png":::
   <span data-ttu-id="bef42-303">**GPU** 部分</span><span class="sxs-lookup"><span data-stu-id="bef42-303">The **GPU** section</span></span>  
:::image-end:::  

### <a name="view-raster-activity"></a><span data-ttu-id="bef42-304">查看光栅活动</span><span class="sxs-lookup"><span data-stu-id="bef42-304">View raster activity</span></span>  

<span data-ttu-id="bef42-305">在**光栅** 部分中查看光栅活动。</span><span class="sxs-lookup"><span data-stu-id="bef42-305">View raster activity in the **Raster** section.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-raster.msft.png" alt-text="“光栅”部分" lightbox="../media/evaluate-performance-performance-raster.msft.png":::
   <span data-ttu-id="bef42-307">**“光栅”** 部分</span><span class="sxs-lookup"><span data-stu-id="bef42-307">The **Raster** section</span></span>  
:::image-end:::  

### <a name="view-interactions"></a><span data-ttu-id="bef42-308">查看交互</span><span class="sxs-lookup"><span data-stu-id="bef42-308">View interactions</span></span>  

<span data-ttu-id="bef42-309">使用 **“交互”** 部分查找和分析在录制期间发生的用户交互。</span><span class="sxs-lookup"><span data-stu-id="bef42-309">Use the **Interactions** section to find and analyze user interactions that happened during the recording.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-interactions-animation.msft.png" alt-text="“交互”部分" lightbox="../media/evaluate-performance-performance-interactions-animation.msft.png":::
   <span data-ttu-id="bef42-311">**“交互”** 部分</span><span class="sxs-lookup"><span data-stu-id="bef42-311">The **Interactions** section</span></span>  
:::image-end:::  

<span data-ttu-id="bef42-312">交互底部的红线表示等待主线程所花费的时间。</span><span class="sxs-lookup"><span data-stu-id="bef42-312">A red line at the bottom of an interaction represents time spent waiting for the main thread.</span></span>  

<span data-ttu-id="bef42-313">选择一个交互以在 **“摘要”** 面板中查看更多相关信息。</span><span class="sxs-lookup"><span data-stu-id="bef42-313">Choose an interaction to view more information about it in the **Summary** panel.</span></span>  

### <a name="analyze-frames-per-second-fps"></a><span data-ttu-id="bef42-314">分析每秒帧数 (FPS)</span><span class="sxs-lookup"><span data-stu-id="bef42-314">Analyze frames per second (FPS)</span></span>  

<span data-ttu-id="bef42-315">DevTools 提供了许多方法，以分析每秒帧数:</span><span class="sxs-lookup"><span data-stu-id="bef42-315">DevTools provides numerous ways to analyze frames per second:</span></span>  

*   <span data-ttu-id="bef42-316">使用 [FPS 图](#the-fps-chart) 在录制期间获取 FPS 的概述。</span><span class="sxs-lookup"><span data-stu-id="bef42-316">Use [the FPS chart](#the-fps-chart) to get an overview of FPS over the duration of the recording.</span></span>  
*   <span data-ttu-id="bef42-317">使用 [帧部分](#the-frames-section) 查看特定帧所需的时间。</span><span class="sxs-lookup"><span data-stu-id="bef42-317">Use [the Frames section](#the-frames-section) to view how long a particular frame took.</span></span>  
*   <span data-ttu-id="bef42-318">在页面运行时，使用 **FPS 计数** 来实时估计 FPS。</span><span class="sxs-lookup"><span data-stu-id="bef42-318">Use the **FPS meter** for a realtime estimate of FPS as the page runs.</span></span>  <span data-ttu-id="bef42-319">导航到 [使用 FPS 计数实时查看每秒帧数](#view-frames-per-second-in-realtime-with-the-fps-meter)。</span><span class="sxs-lookup"><span data-stu-id="bef42-319">Navigate to [View frames per second in realtime with the FPS meter](#view-frames-per-second-in-realtime-with-the-fps-meter).</span></span>  
    
#### <a name="the-fps-chart"></a><span data-ttu-id="bef42-320">FPS 图表</span><span class="sxs-lookup"><span data-stu-id="bef42-320">The FPS chart</span></span>  

<span data-ttu-id="bef42-321">**FPS** 图表提供整个录制期间的帧率概况。</span><span class="sxs-lookup"><span data-stu-id="bef42-321">The **FPS** chart provides an overview of the frame rate across the duration of a recording.</span></span>  <span data-ttu-id="bef42-322">一般来说，绿条越高，帧率越好。</span><span class="sxs-lookup"><span data-stu-id="bef42-322">In general, the higher the green bar, the better the frame rate.</span></span>  

<span data-ttu-id="bef42-323">**FPS** 图上方的红色条形是警告，说明帧率降得太低，很可能会损害用户的体验。</span><span class="sxs-lookup"><span data-stu-id="bef42-323">A red bar above the **FPS** chart is a warning that the frame rate dropped so low that it probably harmed the user's experience.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-fps-highlight.msft.png" alt-text="FPS 图表" lightbox="../media/evaluate-performance-performance-fps-highlight.msft.png":::
   <span data-ttu-id="bef42-325">**FPS** 图表</span><span class="sxs-lookup"><span data-stu-id="bef42-325">The **FPS** chart</span></span>  
:::image-end:::  

#### <a name="the-frames-section"></a><span data-ttu-id="bef42-326">”帧“ 部分</span><span class="sxs-lookup"><span data-stu-id="bef42-326">The Frames section</span></span>  

<span data-ttu-id="bef42-327">**“帧”** 部分会准确告知特定帧所需的时间。</span><span class="sxs-lookup"><span data-stu-id="bef42-327">The **Frames** section tells you exactly how long a particular frame took.</span></span>  

<span data-ttu-id="bef42-328">将鼠标悬停在帧上，可以查看有关该帧的更多信息的工具提示。</span><span class="sxs-lookup"><span data-stu-id="bef42-328">Hover on a frame to view a tooltip with more information about it.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-frames-hover.msft.png" alt-text="鼠标悬停在框架上" lightbox="../media/evaluate-performance-performance-frames-hover.msft.png":::
   <span data-ttu-id="bef42-330">鼠标悬停在框架上</span><span class="sxs-lookup"><span data-stu-id="bef42-330">Hover on a frame</span></span>  
:::image-end:::  

<span data-ttu-id="bef42-331">选择帧以在 **“摘要”** 面板中查看更多有关帧的信息。</span><span class="sxs-lookup"><span data-stu-id="bef42-331">Choose a frame to view more information about the frame in the **Summary** panel.</span></span>  <span data-ttu-id="bef42-332">DevTools 用蓝色勾勒出所选框架的轮廓。</span><span class="sxs-lookup"><span data-stu-id="bef42-332">DevTools outlines the selected frame in blue.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-frames-summary.msft.png" alt-text="在 “摘要” 面板中查看帧" lightbox="../media/evaluate-performance-performance-frames-summary.msft.png":::
   <span data-ttu-id="bef42-334">在 **“摘要”** 面板中查看帧</span><span class="sxs-lookup"><span data-stu-id="bef42-334">View a frame in the **Summary** panel</span></span>  
:::image-end:::  

### <a name="view-network-requests"></a><span data-ttu-id="bef42-335">查看网络请求</span><span class="sxs-lookup"><span data-stu-id="bef42-335">View network requests</span></span>  

<span data-ttu-id="bef42-336">展开 **“网络”** 部分，以查看录制期间发生的网络请求瀑布图。</span><span class="sxs-lookup"><span data-stu-id="bef42-336">Expand the **Network** section to view a waterfall of network requests that occurred during the recording.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-network.msft.png" alt-text="“网络”部分" lightbox="../media/evaluate-performance-performance-network.msft.png":::
   <span data-ttu-id="bef42-338">**“网络”** 部分</span><span class="sxs-lookup"><span data-stu-id="bef42-338">The **Network** section</span></span>  
:::image-end:::  

<span data-ttu-id="bef42-339">请求的颜色编码如下:</span><span class="sxs-lookup"><span data-stu-id="bef42-339">Requests are color-coded as follows:</span></span>  

*   <span data-ttu-id="bef42-340">HTML: 蓝色</span><span class="sxs-lookup"><span data-stu-id="bef42-340">HTML: Blue</span></span>  
*   <span data-ttu-id="bef42-341">CSS: 紫色</span><span class="sxs-lookup"><span data-stu-id="bef42-341">CSS: Purple</span></span>  
*   <span data-ttu-id="bef42-342">JS: 黄色</span><span class="sxs-lookup"><span data-stu-id="bef42-342">JS: Yellow</span></span>  
*   <span data-ttu-id="bef42-343">图像: 绿色</span><span class="sxs-lookup"><span data-stu-id="bef42-343">Images: Green</span></span>  
    
<span data-ttu-id="bef42-344">选择一个请求以在 **“摘要”** 面板中查看更多相关信息。</span><span class="sxs-lookup"><span data-stu-id="bef42-344">Choose a request to view more information about it in the **Summary** panel.</span></span>  <span data-ttu-id="bef42-345">例如，在上图中，**“摘要”** 正在显示更多关于在 **“网络”** 部分选择的蓝色请求的信息。</span><span class="sxs-lookup"><span data-stu-id="bef42-345">For example, in the previous figure, the **Summary** panel is displaying more information about the blue request that is selected in the **Network** section.</span></span>  

<span data-ttu-id="bef42-346">在请求的左上方有一个深蓝色的方块，意味着它是一个优先级较高的请求。</span><span class="sxs-lookup"><span data-stu-id="bef42-346">A darker-blue square in the top-left of a request means it is a higher-priority request.</span></span>  <span data-ttu-id="bef42-347">浅蓝色的方块表示优先级较低。</span><span class="sxs-lookup"><span data-stu-id="bef42-347">A lighter-blue square means lower-priority.</span></span>  <span data-ttu-id="bef42-348">比如上图中，蓝色所选的请求是优先级较高的，而下方绿色的请求为优先级较低的。</span><span class="sxs-lookup"><span data-stu-id="bef42-348">For example, in the previous figure, the blue, selected request is higher-priority, and the green one below it is lower-priority.</span></span>  

<span data-ttu-id="bef42-349">在下图中的第1个图中，`www.bing.com` 的要求用左边的一条线表示，中间是有暗部和亮部的条形，右边是一条线。</span><span class="sxs-lookup"><span data-stu-id="bef42-349">In the 1st of the following figures, the request for `www.bing.com` is represented by a line on the left, a bar in the middle with a dark portion and a light portion, and a line on the right.</span></span>  <span data-ttu-id="bef42-350">在下面的第2个数字中，显示了同一请求在 **“网络”** 工具的 **“计时”** 面板中的相应表示。</span><span class="sxs-lookup"><span data-stu-id="bef42-350">In the 2nd of the following figures shows the corresponding representation of the same request in the **Timing** panel of the **Network** tool.</span></span>  <span data-ttu-id="bef42-351">下面是这两种表示形式如何相互映射:</span><span class="sxs-lookup"><span data-stu-id="bef42-351">Here is how these two representations map to each other:</span></span>

*   <span data-ttu-id="bef42-352">左行是到事件的 `Connection Start` 组的所有内容 (包括)。</span><span class="sxs-lookup"><span data-stu-id="bef42-352">The left line is everything up to the `Connection Start` group of events, inclusive.</span></span>  <span data-ttu-id="bef42-353">换言之，它是 `Request Sent` 之前的所有内容 (独占)。</span><span class="sxs-lookup"><span data-stu-id="bef42-353">In other words, it is everything before `Request Sent`, exclusive.</span></span>  
*   <span data-ttu-id="bef42-354">条形图的浅部分为 `Request Sent` 和 `Waiting (TTFB)`。</span><span class="sxs-lookup"><span data-stu-id="bef42-354">The light portion of the bar is `Request Sent` and `Waiting (TTFB)`.</span></span>  
*   <span data-ttu-id="bef42-355">条形图的深色部分为 `Content Download`。</span><span class="sxs-lookup"><span data-stu-id="bef42-355">The dark portion of the bar is `Content Download`.</span></span>  
*   <span data-ttu-id="bef42-356">右行基本上是等待主线程所花的时间。</span><span class="sxs-lookup"><span data-stu-id="bef42-356">The right line is essentially time spent waiting for the main thread.</span></span>  <span data-ttu-id="bef42-357">这未在 **“计时”** 中表示。</span><span class="sxs-lookup"><span data-stu-id="bef42-357">This is not represented in the **Timing** panel.</span></span>  
    
:::row:::
   :::column span="":::
      :::image type="complex" source="../media/evaluate-performance-bing-performance-network.msft.png" alt-text="www.bing.com 请求的行条表示" lightbox="../media/evaluate-performance-bing-performance-network.msft.png":::
         <span data-ttu-id="bef42-359">`www.bing.com` 请求的行条表示</span><span class="sxs-lookup"><span data-stu-id="bef42-359">The line-bar representation of the `www.bing.com` request</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/evaluate-performance-bing-network-timing.msft.png" alt-text="网络工具" lightbox="../media/evaluate-performance-bing-network-timing.msft.png":::
         <span data-ttu-id="bef42-361">**网络** 工具</span><span class="sxs-lookup"><span data-stu-id="bef42-361">The **Network** tool</span></span>  
<span data-ttu-id="bef42-362">:     ::image-end:::</span><span class="sxs-lookup"><span data-stu-id="bef42-362">:     ::image-end:::</span></span>  
   :::column-end:::
:::row-end:::

### <a name="view-memory-metrics"></a><span data-ttu-id="bef42-363">查看内存指标</span><span class="sxs-lookup"><span data-stu-id="bef42-363">View memory metrics</span></span>  

<span data-ttu-id="bef42-364">打开 **“内存”** 复选框以查看上次记录中的内存指标。</span><span class="sxs-lookup"><span data-stu-id="bef42-364">Turn on the **Memory** checkbox to view memory metrics from the last recording.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-memory-highlight.msft.png" alt-text="内存复选框" lightbox="../media/evaluate-performance-performance-memory-highlight.msft.png":::
   <span data-ttu-id="bef42-366">**“内存”** 复选框</span><span class="sxs-lookup"><span data-stu-id="bef42-366">The **Memory** checkbox</span></span>  
:::image-end:::  

<span data-ttu-id="bef42-367">DevTools 在 **“摘要”** 面板上方显示新的 **“内存”** 图表。</span><span class="sxs-lookup"><span data-stu-id="bef42-367">DevTools displays a new **Memory** chart, above the **Summary** panel.</span></span>  <span data-ttu-id="bef42-368">**NET** 图表下方还有一个新的图表，称为 **“HEAP”**。</span><span class="sxs-lookup"><span data-stu-id="bef42-368">There is also a new chart below the **NET** chart, called **HEAP**.</span></span>  <span data-ttu-id="bef42-369">**“HEAP”** 图表提供的信息与 **“内存”** 表中的 **“JS Heap”** 行相同。</span><span class="sxs-lookup"><span data-stu-id="bef42-369">The **HEAP** chart provides the same information as the **JS Heap** line in the **Memory** chart.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-memory-chart.msft.png" alt-text="内存指标" lightbox="../media/evaluate-performance-performance-memory-chart.msft.png":::
   <span data-ttu-id="bef42-371">内存指标</span><span class="sxs-lookup"><span data-stu-id="bef42-371">Memory metrics</span></span>  
:::image-end:::  

<span data-ttu-id="bef42-372">图表上的彩色线条会映射到图表上方的彩色复选框上。</span><span class="sxs-lookup"><span data-stu-id="bef42-372">The colored lines on the chart map to the colored checkboxes above the chart.</span></span>  
<span data-ttu-id="bef42-373">禁用复选框以在图表中隐藏该类别。</span><span class="sxs-lookup"><span data-stu-id="bef42-373">Disable a checkbox to hide that category from the chart.</span></span>  

<span data-ttu-id="bef42-374">图表只显示当前选择的记录区域。</span><span class="sxs-lookup"><span data-stu-id="bef42-374">The chart only displays the region of the recording that is currently selected.</span></span>  <span data-ttu-id="bef42-375">例如，在上一个图中， **内存** 图表仅显示从 400 毫秒标记上下到 1750 毫秒标记左右的内存使用情况。</span><span class="sxs-lookup"><span data-stu-id="bef42-375">For example, in the previous figure, the **Memory** chart is only showing memory usage from around the 400 ms mark to the 1750 ms mark.</span></span>  

### <a name="view-the-duration-of-a-portion-of-a-recording"></a><span data-ttu-id="bef42-376">查看部分录制的持续时间</span><span class="sxs-lookup"><span data-stu-id="bef42-376">View the duration of a portion of a recording</span></span>  

<span data-ttu-id="bef42-377">当分析像 **网络** 或者 **主** 这样的部分时，有时你需要更精确地估计某些事件花了多长时间。</span><span class="sxs-lookup"><span data-stu-id="bef42-377">When analyzing a section like **Network** or **Main**, sometimes you need a more precise estimate of how long certain events took.</span></span>  <span data-ttu-id="bef42-378">按住 `Shift`，选择并按住，然后向左或向右拖动以选择录音的一部分。</span><span class="sxs-lookup"><span data-stu-id="bef42-378">Hold `Shift`, choose and hold, and drag left or right to select a portion of the recording.</span></span>  <span data-ttu-id="bef42-379">在所选内容底部，DevTools 显示该部分所话费的时间。</span><span class="sxs-lookup"><span data-stu-id="bef42-379">At the bottom of your selection, DevTools shows how long that portion took.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-main-duration.msft.png" alt-text="查看部分录制的持续时间" lightbox="../media/evaluate-performance-performance-main-duration.msft.png":::
   <span data-ttu-id="bef42-381">查看部分录制的持续时间</span><span class="sxs-lookup"><span data-stu-id="bef42-381">View the duration of a portion of a recording</span></span>  
:::image-end:::  

### <a name="view-a-screenshot"></a><span data-ttu-id="bef42-382">查看屏幕截图</span><span class="sxs-lookup"><span data-stu-id="bef42-382">View a screenshot</span></span>  

<span data-ttu-id="bef42-383">导航到 [“录制时捕捉屏幕截图”](#capture-screenshots-while-recording)，了解如何开启屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="bef42-383">Navigate to [Capture screenshots while recording](#capture-screenshots-while-recording) to learn how to turn on screenshots.</span></span>  

<span data-ttu-id="bef42-384">将鼠标悬停在 **“概述”**，可以查看该记录短片的页面截图。</span><span class="sxs-lookup"><span data-stu-id="bef42-384">Hover on the **Overview** to view a screenshot of how the page looked during that moment of the recording.</span></span>  <span data-ttu-id="bef42-385">**“概述”** 是包含 **CPU**、**FPS** 和 **NET** 图表的部分。</span><span class="sxs-lookup"><span data-stu-id="bef42-385">The **Overview** is the section that contains the **CPU**, **FPS**, and **NET** charts.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-screenshots-hover.msft.png" alt-text="查看屏幕截图" lightbox="../media/evaluate-performance-performance-screenshots-hover.msft.png":::
   <span data-ttu-id="bef42-387">查看屏幕截图</span><span class="sxs-lookup"><span data-stu-id="bef42-387">View a screenshot</span></span>  
:::image-end:::  

<span data-ttu-id="bef42-388">还可以在 **“框架”** 部分选择一个框架来查看屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="bef42-388">You may also view screenshots by choosing a frame in the **Frames** section.</span></span>  <span data-ttu-id="bef42-389">DevTools 在 **“摘要”** 面板中显示小版本的截图。</span><span class="sxs-lookup"><span data-stu-id="bef42-389">DevTools displays a small version of the screenshot in the **Summary** panel.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-summary-preview.msft.png" alt-text="在“摘要”面板中查看屏幕截图" lightbox="../media/evaluate-performance-performance-summary-preview.msft.png":::
   <span data-ttu-id="bef42-391">在 **“摘要”** 面板中查看屏幕截图</span><span class="sxs-lookup"><span data-stu-id="bef42-391">View a screenshot in the **Summary** panel</span></span>  
:::image-end:::  

<span data-ttu-id="bef42-392">在 **“摘要”** 面板中选择缩略图来放大截图。</span><span class="sxs-lookup"><span data-stu-id="bef42-392">Choose the thumbnail in the **Summary** panel to zoom in on the screenshot.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-summary-preview-select.msft.png" alt-text="从“摘要”面板中放大屏幕截图" lightbox="../media/evaluate-performance-performance-summary-preview-select.msft.png":::
   <span data-ttu-id="bef42-394">从 **“摘要”** 面板中放大屏幕截图</span><span class="sxs-lookup"><span data-stu-id="bef42-394">Zoom into a screenshot from the **Summary** panel</span></span>  
:::image-end:::  

### <a name="view-layers-information"></a><span data-ttu-id="bef42-395">查看图层信息</span><span class="sxs-lookup"><span data-stu-id="bef42-395">View layers information</span></span>  

<span data-ttu-id="bef42-396">查看框架的高级图层信息:</span><span class="sxs-lookup"><span data-stu-id="bef42-396">To view advanced layers information about a frame:</span></span>  

1.  <span data-ttu-id="bef42-397">[启用高级画图检测工具](#turn-on-advanced-paint-instrumentation)。</span><span class="sxs-lookup"><span data-stu-id="bef42-397">[Turn on advanced paint instrumentation](#turn-on-advanced-paint-instrumentation).</span></span>  
1.  <span data-ttu-id="bef42-398">在 **“框架”** 部分选择一个框架。</span><span class="sxs-lookup"><span data-stu-id="bef42-398">Choose a frame in the **Frames** section.</span></span>  <span data-ttu-id="bef42-399">DevTools 将在 **“事件日志”** 面板旁边的新 **“图层”** 面板中显示关于图层的信息。</span><span class="sxs-lookup"><span data-stu-id="bef42-399">DevTools displays information about the layers in the new **Layers** panel, next to the **Event Log** panel.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-layers-all.msft.png" alt-text="“图层”窗格" lightbox="../media/evaluate-performance-layers-all.msft.png":::
       <span data-ttu-id="bef42-401">**“图层”** 窗格</span><span class="sxs-lookup"><span data-stu-id="bef42-401">The **Layers** pane</span></span>  
    :::image-end:::  
    
<span data-ttu-id="bef42-402">将鼠标悬停在图层上，在图中高亮显示。</span><span class="sxs-lookup"><span data-stu-id="bef42-402">Hover on a layer to highlight it in the diagram.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-frames-document-nav-bar-highlighted.msft.png" alt-text="突出显示图层" lightbox="../media/evaluate-performance-performance-frames-document-nav-bar-highlighted.msft.png":::
   <span data-ttu-id="bef42-404">突出显示图层</span><span class="sxs-lookup"><span data-stu-id="bef42-404">Highlight a layer</span></span>  
:::image-end:::  

<span data-ttu-id="bef42-405">若要移动图表:</span><span class="sxs-lookup"><span data-stu-id="bef42-405">To move the diagram:</span></span>  

*   <span data-ttu-id="bef42-406">选择 **“平移模式”** \(![“平移模式”](../media/pan-mode-icon.msft.png)\) 沿 X 轴和 Y 轴移动。</span><span class="sxs-lookup"><span data-stu-id="bef42-406">Choose **Pan Mode** \(![Pan Mode](../media/pan-mode-icon.msft.png)\) to move along the X and Y axes.</span></span>  
*   <span data-ttu-id="bef42-407">选择 **“旋转模式”** \(![“旋转模式”](../media/rotate-mode-icon.msft.png)\) 沿 Z 轴旋转。</span><span class="sxs-lookup"><span data-stu-id="bef42-407">Choose **Rotate Mode** \(![Rotate Mode](../media/rotate-mode-icon.msft.png)\) to rotate along the Z axis.</span></span>  
*   <span data-ttu-id="bef42-408">选择 **“重置转换”** \(![“重置转换”](../media/reset-transform-icon.msft.png)\) 可以将图重置到原始位置。</span><span class="sxs-lookup"><span data-stu-id="bef42-408">Choose **Reset Transform** \(![Reset Transform](../media/reset-transform-icon.msft.png)\) to reset the diagram to the original position.</span></span>  
    
### <a name="view-paint-profiler"></a><span data-ttu-id="bef42-409">查看绘图探查器</span><span class="sxs-lookup"><span data-stu-id="bef42-409">View paint profiler</span></span>  

<span data-ttu-id="bef42-410">查看有关绘图事件的高级信息:</span><span class="sxs-lookup"><span data-stu-id="bef42-410">To view advanced information about a paint event:</span></span>  

1.  <span data-ttu-id="bef42-411">[打开](#turn-on-advanced-paint-instrumentation)。</span><span class="sxs-lookup"><span data-stu-id="bef42-411">[Turn on](#turn-on-advanced-paint-instrumentation).</span></span>  
1.  <span data-ttu-id="bef42-412">在 **主** 部分选择 **绘图** 事件。</span><span class="sxs-lookup"><span data-stu-id="bef42-412">Choose a **Paint** event in the **Main** section.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-paint-profiler.msft.png" alt-text="“绘图探查器”面板" lightbox="../media/evaluate-performance-paint-profiler.msft.png":::
       <span data-ttu-id="bef42-414">**“绘图探查器”** 面板</span><span class="sxs-lookup"><span data-stu-id="bef42-414">The **Paint Profiler** panel</span></span>  
    :::image-end:::  
    
## <a name="analyze-rendering-performance-with-the-rendering-tool"></a><span data-ttu-id="bef42-415">使用 "渲染" 工具分析渲染性能</span><span class="sxs-lookup"><span data-stu-id="bef42-415">Analyze rendering performance with the Rendering tool</span></span>  

<span data-ttu-id="bef42-416">使用 **“渲染”** 面板的功能来帮助可视化页面的渲染性能。</span><span class="sxs-lookup"><span data-stu-id="bef42-416">Use the features of the **Rendering** panel to help visualize the rendering performance of your page.</span></span>  

<span data-ttu-id="bef42-417">若要打开 **“渲染”** 工具:</span><span class="sxs-lookup"><span data-stu-id="bef42-417">To open the **Rendering** tool:</span></span>  

1.  <span data-ttu-id="bef42-418">[打开“命令”菜单][DevToolsCommandMenu]。</span><span class="sxs-lookup"><span data-stu-id="bef42-418">[Open the Command Menu][DevToolsCommandMenu].</span></span>  
1.  <span data-ttu-id="bef42-419">开始键入 `Rendering` 并选择 `Show Rendering`。</span><span class="sxs-lookup"><span data-stu-id="bef42-419">Start typing `Rendering` and select `Show Rendering`.</span></span>  <span data-ttu-id="bef42-420">DevTools 会在 DevTools 窗口的底部显示**渲染**工具。</span><span class="sxs-lookup"><span data-stu-id="bef42-420">DevTools displays the **Rendering** tool at the bottom of your DevTools window.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-console-drawer-rendering.msft.png" alt-text="渲染工具" lightbox="../media/evaluate-performance-console-drawer-rendering.msft.png":::
       <span data-ttu-id="bef42-422">**渲染** 工具</span><span class="sxs-lookup"><span data-stu-id="bef42-422">The **Rendering** tool</span></span>  
    :::image-end:::  
    
### <a name="view-frames-per-second-in-realtime-with-the-fps-meter"></a><span data-ttu-id="bef42-423">使用 FPS 计数实时查看每秒帧数。</span><span class="sxs-lookup"><span data-stu-id="bef42-423">View frames per second in realtime with the FPS meter</span></span>  

<span data-ttu-id="bef42-424">**FPS 计数** 是出现在视区右上角的叠加。</span><span class="sxs-lookup"><span data-stu-id="bef42-424">The **FPS meter** is an overlay that appears in the top-right corner of your viewport.</span></span>  <span data-ttu-id="bef42-425">它提供了页面运行时 FPS 的实时估计。</span><span class="sxs-lookup"><span data-stu-id="bef42-425">It provides a realtime estimate of FPS as the page runs.</span></span>  <span data-ttu-id="bef42-426">若要打开 **FPS 计数**:</span><span class="sxs-lookup"><span data-stu-id="bef42-426">To open the **FPS meter**:</span></span>  

1.  <span data-ttu-id="bef42-427">打开 **渲染** 工具。</span><span class="sxs-lookup"><span data-stu-id="bef42-427">Open the **Rendering** tool.</span></span>  <span data-ttu-id="bef42-428">[使用 “渲染” 工具分析渲染性能](#analyze-rendering-performance-with-the-rendering-tool)。</span><span class="sxs-lookup"><span data-stu-id="bef42-428">[Analyze rendering performance with the Rendering tool](#analyze-rendering-performance-with-the-rendering-tool).</span></span>  
1.  <span data-ttu-id="bef42-429">打开 **FPS 计数** 复选框。</span><span class="sxs-lookup"><span data-stu-id="bef42-429">Turn on the **FPS Meter** checkbox.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-jank-console-rendering-frame-rate.msft.png" alt-text="FPS 计数" lightbox="../media/evaluate-performance-jank-console-rendering-frame-rate.msft.png":::
       <span data-ttu-id="bef42-431">**FPS 计数**</span><span class="sxs-lookup"><span data-stu-id="bef42-431">The **FPS meter**</span></span>  
    :::image-end:::  
    
### <a name="view-painting-events-in-realtime-with-paint-flashing"></a><span data-ttu-id="bef42-432">使用“画图闪烁”实时查看画图事件</span><span class="sxs-lookup"><span data-stu-id="bef42-432">View painting events in realtime with Paint Flashing</span></span>  

<span data-ttu-id="bef42-433">使用“画图闪烁”可实时查看页面上的所有画图事件。</span><span class="sxs-lookup"><span data-stu-id="bef42-433">Use Paint Flashing to get a realtime view of all paint events on the page.</span></span>  <span data-ttu-id="bef42-434">每当重新绘制页面的一部分时，DevTools 就会用绿色勾勒出该部分的轮廓。</span><span class="sxs-lookup"><span data-stu-id="bef42-434">Whenever a part of the page gets re-painted, DevTools outlines that section in green.</span></span>  

<span data-ttu-id="bef42-435">若要打开“画图闪烁”，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="bef42-435">To turn on Paint Flashing, complete the following actions.</span></span>  

1.  <span data-ttu-id="bef42-436">打开 **渲染** 工具。</span><span class="sxs-lookup"><span data-stu-id="bef42-436">Open the **Rendering** tool.</span></span>  <span data-ttu-id="bef42-437">导航到 [使用“绘制”工具分析绘制性能](#analyze-rendering-performance-with-the-rendering-tool)。</span><span class="sxs-lookup"><span data-stu-id="bef42-437">Navigate to [Analyze rendering performance with the Rendering tool](#analyze-rendering-performance-with-the-rendering-tool).</span></span>  
1.  <span data-ttu-id="bef42-438">启用 **“画图闪烁”** 复选框。</span><span class="sxs-lookup"><span data-stu-id="bef42-438">Turn on the **Paint Flashing** checkbox.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-jank-console-rendering-paint-flashing.msft.png" alt-text="绘画闪烁" lightbox="../media/evaluate-performance-jank-console-rendering-paint-flashing.msft.png":::
       **<span data-ttu-id="bef42-440">绘画闪烁</span><span class="sxs-lookup"><span data-stu-id="bef42-440">Paint Flashing</span></span>**  
    :::image-end:::  
    
### <a name="view-an-overlay-of-layers-with-layer-borders"></a><span data-ttu-id="bef42-441">使用 “图层边框” 查看图层的叠加</span><span class="sxs-lookup"><span data-stu-id="bef42-441">View an overlay of layers with Layer Borders</span></span>  

<span data-ttu-id="bef42-442">使用 **“图层边框”** 可查看页面顶部的图层边框和图块的叠加。</span><span class="sxs-lookup"><span data-stu-id="bef42-442">Use **Layer Borders** to view an overlay of layer borders and tiles on top of the page.</span></span>  

<span data-ttu-id="bef42-443">若要打开“图层边框”，请完成以下操作，</span><span class="sxs-lookup"><span data-stu-id="bef42-443">To turn on Layer Borders, complete the following actions,</span></span>  

1.  <span data-ttu-id="bef42-444">打开 **渲染** 工具。</span><span class="sxs-lookup"><span data-stu-id="bef42-444">Open the **Rendering** tool.</span></span>  <span data-ttu-id="bef42-445">导航到 [使用“绘制”工具分析绘制性能](#analyze-rendering-performance-with-the-rendering-tool)。</span><span class="sxs-lookup"><span data-stu-id="bef42-445">Navigate to [Analyze rendering performance with the Rendering tool](#analyze-rendering-performance-with-the-rendering-tool).</span></span>  
1.  <span data-ttu-id="bef42-446">打开 **“图层边框”** 复选框。</span><span class="sxs-lookup"><span data-stu-id="bef42-446">Turn on the **Layer Borders** checkbox.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-devtools-console-rendering-layer-borders.msft.png" alt-text="图层边框" lightbox="../media/evaluate-performance-devtools-console-rendering-layer-borders.msft.png":::
       **<span data-ttu-id="bef42-448">图层边框</span><span class="sxs-lookup"><span data-stu-id="bef42-448">Layer Borders</span></span>**  
    :::image-end:::  
    
<span data-ttu-id="bef42-449">导航到 [debug_colors.cc][ChromiumDebugColors] 中的批注，了解颜色编码的说明。</span><span class="sxs-lookup"><span data-stu-id="bef42-449">Navigate to the comments in [debug_colors.cc][ChromiumDebugColors] for an explanation of the color-codings.</span></span>  

### <a name="find-scroll-performance-issues-in-realtime"></a><span data-ttu-id="bef42-450">实时查找滚动性能问题</span><span class="sxs-lookup"><span data-stu-id="bef42-450">Find scroll performance issues in realtime</span></span>  

<span data-ttu-id="bef42-451">使用滚动性能问题来识别页面中具有与滚动相关的事件监听器的元素，这些元素可能会损害页面的性能。</span><span class="sxs-lookup"><span data-stu-id="bef42-451">Use Scrolling Performance Issues to identify elements of the page that have event listeners related to scrolling that may harm the performance of the page.</span></span>  
<span data-ttu-id="bef42-452">DevTools 概述了茶色中潜在的问题元素。</span><span class="sxs-lookup"><span data-stu-id="bef42-452">DevTools outlines the potentially-problematic elements in teal.</span></span>  

<span data-ttu-id="bef42-453">若要查看滚动性能问题，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="bef42-453">To view scroll performance issues, complete the following actions.</span></span> 

1.  <span data-ttu-id="bef42-454">打开 **渲染** 工具。</span><span class="sxs-lookup"><span data-stu-id="bef42-454">Open the **Rendering** tool.</span></span>  <span data-ttu-id="bef42-455">导航到 [使用“绘制”工具分析绘制性能](#analyze-rendering-performance-with-the-rendering-tool)。</span><span class="sxs-lookup"><span data-stu-id="bef42-455">Navigate to [Analyze rendering performance with the Rendering tool](#analyze-rendering-performance-with-the-rendering-tool).</span></span>  
1.  <span data-ttu-id="bef42-456">打开 **“滚动性能问题”** 复选框。</span><span class="sxs-lookup"><span data-stu-id="bef42-456">Turn on the **Scrolling Performance Issues** checkbox.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-bing-console-drawer-rendering-scrolling-performance-issues.msft.png" alt-text="滚动性能问题表明，非层视区的限制对象可能会损害滚动性能" lightbox="../media/evaluate-performance-bing-console-drawer-rendering-scrolling-performance-issues.msft.png":::
       <span data-ttu-id="bef42-458">**“滚动性能问题”** 表明，非层视区的限制对象可能会损害滚动性能</span><span class="sxs-lookup"><span data-stu-id="bef42-458">**Scrolling Performance Issues** indicates that non-layer viewport-constrained objects may harm scroll performance</span></span>  
    :::image-end:::  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="bef42-459">联系 Microsoft Edge 开发工具团队</span><span class="sxs-lookup"><span data-stu-id="bef42-459">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 开发人员工具 | Microsoft 文档"  
[DevToolsCommandMenu]: ../command-menu/index.md#open-the-command-menu "使用 Microsoft Edge DevTools 命令菜单运行命令 | Microsoft Docs"  
[DevtoolsEvaluatePerformanceGettingStarted]: ./index.md "开始分析运行时性能 | Microsoft Docs"  

[ActivityTabsDemo]: https://microsoft-edge-chromium-devtools.glitch.me/perf/activitytabs.html "活动选项卡演示 | 故障"  

[ChromiumDebugColors]: https://cs.chromium.org/chromium/src/cc/debug/debug_colors.cc "debug_colors.cc - 代码搜索"  

> [!NOTE]
> <span data-ttu-id="bef42-465">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="bef42-465">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="bef42-466">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/reference)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="bef42-466">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/reference) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="bef42-468">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="bef42-468">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
