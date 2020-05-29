---
title: 加快 JavaScript 运行时
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/30/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 0e198be3e1cef53590a24bfaa2382746ced299ed
ms.sourcegitcommit: 0342d99bf8d3212068890bab0e1e960afa507c02
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/30/2020
ms.locfileid: "10611869"
---
<!-- Copyright Kayce Basques and Meggin Kearney

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License. -->





# <span data-ttu-id="7e9b8-103">加快 JavaScript 运行时</span><span class="sxs-lookup"><span data-stu-id="7e9b8-103">Speed Up JavaScript Runtime</span></span>   




<span data-ttu-id="7e9b8-104">使用 "**内存**" 面板识别昂贵的功能。</span><span class="sxs-lookup"><span data-stu-id="7e9b8-104">Identify expensive functions using the **Memory** panel.</span></span>  

> ##### <span data-ttu-id="7e9b8-105">图 1</span><span class="sxs-lookup"><span data-stu-id="7e9b8-105">Figure 1</span></span>  
> <span data-ttu-id="7e9b8-106">采样配置文件</span><span class="sxs-lookup"><span data-stu-id="7e9b8-106">Sampling Profiles</span></span>  
> ![采样配置文件][ImageCpuProfile]  

### <span data-ttu-id="7e9b8-108">摘要</span><span class="sxs-lookup"><span data-stu-id="7e9b8-108">Summary</span></span>  

*   <span data-ttu-id="7e9b8-109">准确记录所调用的函数和**内存面板中的分配**采样所需的内存量。</span><span class="sxs-lookup"><span data-stu-id="7e9b8-109">Record exactly which functions were called and how much memory each requires with Allocation Sampling in the **Memory** panel.</span></span>  
*   <span data-ttu-id="7e9b8-110">将配置文件可视化为火焰图表。</span><span class="sxs-lookup"><span data-stu-id="7e9b8-110">Visualize your profiles as a flame chart.</span></span>  

## <span data-ttu-id="7e9b8-111">录制采样配置文件</span><span class="sxs-lookup"><span data-stu-id="7e9b8-111">Record a Sampling Profile</span></span>  

<span data-ttu-id="7e9b8-112">如果注意到 jank 在 JavaScript 中，请收集采样档案。</span><span class="sxs-lookup"><span data-stu-id="7e9b8-112">If you notice jank in your JavaScript, collect a Sampling Profile.</span></span>  <span data-ttu-id="7e9b8-113">采样配置文件显示你的页面中的函数所用的运行时间。</span><span class="sxs-lookup"><span data-stu-id="7e9b8-113">Sampling Profiles show where running time is spent on functions in your page.</span></span>  

1.  <span data-ttu-id="7e9b8-114">转到 DevTools 的 "**内存**" 面板。</span><span class="sxs-lookup"><span data-stu-id="7e9b8-114">Go to the **Memory** panel of DevTools.</span></span>  
1.  <span data-ttu-id="7e9b8-115">选择 "**分配采样**" 单选按钮。</span><span class="sxs-lookup"><span data-stu-id="7e9b8-115">Select the **Allocation sampling** radio button.</span></span>  
1.  <span data-ttu-id="7e9b8-116">选择**开始**。</span><span class="sxs-lookup"><span data-stu-id="7e9b8-116">Select **Start**.</span></span>  
1.  <span data-ttu-id="7e9b8-117">根据你尝试分析的内容，你可以重新加载页面、与页面交互或仅让页面运行。</span><span class="sxs-lookup"><span data-stu-id="7e9b8-117">Depending on what you are trying to analyze, you may either reload the page, interact with the page, or just let the page run.</span></span>  
1.  <span data-ttu-id="7e9b8-118">完成后选择 "**停止**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="7e9b8-118">Select the **Stop** button when you are finished.</span></span>  

> [!NOTE]
> <span data-ttu-id="7e9b8-119">您也可以使用[控制台实用工具 API][DevtoolsConsoleUtilities]从命令行记录和分组配置文件。</span><span class="sxs-lookup"><span data-stu-id="7e9b8-119">You may also use the [Console Utilities API][DevtoolsConsoleUtilities] to record and group profiles from the command line.</span></span>  

## <span data-ttu-id="7e9b8-120">查看采样配置文件</span><span class="sxs-lookup"><span data-stu-id="7e9b8-120">View Sampling Profile</span></span>  

<span data-ttu-id="7e9b8-121">完成录制后，DevTools 会自动在 "**采样配置文件**" 下填入来自录制的数据的**内存**面板。</span><span class="sxs-lookup"><span data-stu-id="7e9b8-121">When you finish recording, DevTools automatically populates the **Memory** panel under **SAMPLING PROFILES** with the data from your recording.</span></span>  

<span data-ttu-id="7e9b8-122">默认视图为**厚粗（下图）**。</span><span class="sxs-lookup"><span data-stu-id="7e9b8-122">The default view is **Heavy \(Bottom Up\)**.</span></span>  <span data-ttu-id="7e9b8-123">此视图使你能够查看哪些函数对性能有最大影响，并检查这些函数的调用路径。</span><span class="sxs-lookup"><span data-stu-id="7e9b8-123">This view enables you to see which functions had the most impact on performance and examine the calling paths to those functions.</span></span>  

### <span data-ttu-id="7e9b8-124">更改排序顺序</span><span class="sxs-lookup"><span data-stu-id="7e9b8-124">Change sort order</span></span>   

<span data-ttu-id="7e9b8-125">若要更改排序顺序，请选择 "**焦点选定函数** ![ 焦点所选函数" 图标旁边的下拉菜单 ][ImageFocusIcon] ，然后选择下列选项之一。</span><span class="sxs-lookup"><span data-stu-id="7e9b8-125">To change the sorting order, select the dropdown menu next to the **focus selected function** ![focus selected function][ImageFocusIcon] icon and then choose one of the following options.</span></span>

<span data-ttu-id="7e9b8-126">**图表**。</span><span class="sxs-lookup"><span data-stu-id="7e9b8-126">**Chart**.</span></span>  <span data-ttu-id="7e9b8-127">显示录制的按时间顺序的图表。</span><span class="sxs-lookup"><span data-stu-id="7e9b8-127">Displays a chronological chart of the recording.</span></span>  

> ##### <span data-ttu-id="7e9b8-128">图 2</span><span class="sxs-lookup"><span data-stu-id="7e9b8-128">Figure 2</span></span>  
> <span data-ttu-id="7e9b8-129">火焰图</span><span class="sxs-lookup"><span data-stu-id="7e9b8-129">Flame chart</span></span>  
> ![火焰图][ImageFlameChart]  

<span data-ttu-id="7e9b8-131">**粗 \ （下图）**。</span><span class="sxs-lookup"><span data-stu-id="7e9b8-131">**Heavy \(Bottom Up\)**.</span></span>  <span data-ttu-id="7e9b8-132">通过对性能的影响列出函数，并使你能够检查这些函数的调用路径。</span><span class="sxs-lookup"><span data-stu-id="7e9b8-132">Lists functions by impact on performance and enables you to examine the calling paths to the functions.</span></span>  <span data-ttu-id="7e9b8-133">这是默认视图。</span><span class="sxs-lookup"><span data-stu-id="7e9b8-133">This is the default view.</span></span>  

> ##### <span data-ttu-id="7e9b8-134">图 3</span><span class="sxs-lookup"><span data-stu-id="7e9b8-134">Figure 3</span></span>  
> <span data-ttu-id="7e9b8-135">粗图</span><span class="sxs-lookup"><span data-stu-id="7e9b8-135">Heavy chart</span></span>  
> ![粗图][ImageHeavyChart]  

<span data-ttu-id="7e9b8-137">**树 \ （从上向下）**。</span><span class="sxs-lookup"><span data-stu-id="7e9b8-137">**Tree \(Top Down\)**.</span></span>  <span data-ttu-id="7e9b8-138">显示从调用堆栈顶部开始的调用结构的整体图片。</span><span class="sxs-lookup"><span data-stu-id="7e9b8-138">Shows an overall picture of the calling structure, starting at the top of the call stack.</span></span>  

> ##### <span data-ttu-id="7e9b8-139">图 4</span><span class="sxs-lookup"><span data-stu-id="7e9b8-139">Figure 4</span></span>  
> <span data-ttu-id="7e9b8-140">树形图</span><span class="sxs-lookup"><span data-stu-id="7e9b8-140">Tree chart</span></span>  
> ![树形图][ImageTreeChart]  

### <span data-ttu-id="7e9b8-142">排除函数</span><span class="sxs-lookup"><span data-stu-id="7e9b8-142">Exclude functions</span></span>   

<span data-ttu-id="7e9b8-143">若要从采样配置文件中排除某个函数，请选择该函数以将其选中，然后选择 "**排除所选函数**" " ![ 排除所选函数" ][ImageExcludeIcon] 图标。</span><span class="sxs-lookup"><span data-stu-id="7e9b8-143">To exclude a function from your Sampling Profile, select it to select it and then select the **exclude selected function** ![exclude selected function][ImageExcludeIcon] icon.</span></span>  <span data-ttu-id="7e9b8-144">已排除的函数 \ （子元素 \）的请求函数 \ （parent）将按分配给已排除函数 \ （子）的分配内存进行计费。</span><span class="sxs-lookup"><span data-stu-id="7e9b8-144">The requesting function \(parent\) of the excluded function \(child\) is charged with the allocated memory assigned to the excluded function \(child\).</span></span>  

<span data-ttu-id="7e9b8-145">选择 "**还原所有函数**" " ![ 还原所有函数" ][ImageRestoreIcon] 图标，将所有排除的函数还原到录制中。</span><span class="sxs-lookup"><span data-stu-id="7e9b8-145">Select the **restore all functions** ![restore all functions][ImageRestoreIcon] icon to restore all excluded functions back into the recording.</span></span>  

## <span data-ttu-id="7e9b8-146">以图表形式查看采样配置文件</span><span class="sxs-lookup"><span data-stu-id="7e9b8-146">View Sampling Profile as Chart</span></span>   

<span data-ttu-id="7e9b8-147">"图表" 视图提供了一段时间内采样配置文件的可视化表示形式。</span><span class="sxs-lookup"><span data-stu-id="7e9b8-147">The Chart view provides a visual representation of the Sampling Profile over time.</span></span>  

<span data-ttu-id="7e9b8-148">[录制采样配置文件](#record-a-sampling-profile)后，通过将[排序顺序更改](#change-sort-order)为**图表**，可将录制查看为火焰图表。</span><span class="sxs-lookup"><span data-stu-id="7e9b8-148">After you [record a Sampling Profile](#record-a-sampling-profile), view the recording as a flame chart by [changing the sort order](#change-sort-order) to **Chart**.</span></span>  

> ##### <span data-ttu-id="7e9b8-149">图 5</span><span class="sxs-lookup"><span data-stu-id="7e9b8-149">Figure 5</span></span>  
> <span data-ttu-id="7e9b8-150">火焰图表视图</span><span class="sxs-lookup"><span data-stu-id="7e9b8-150">Flame chart view</span></span>  
> ![火焰图表视图][ImageFlameChartView]  

<span data-ttu-id="7e9b8-152">火焰图分成两部分。</span><span class="sxs-lookup"><span data-stu-id="7e9b8-152">The flame chart is split into two parts.</span></span>  

| | <span data-ttu-id="7e9b8-153">部件</span><span class="sxs-lookup"><span data-stu-id="7e9b8-153">Part</span></span> | <span data-ttu-id="7e9b8-154">描述</span><span class="sxs-lookup"><span data-stu-id="7e9b8-154">Description</span></span> |  
| --- |:--- |:--- |  
| <span data-ttu-id="7e9b8-155">raid-1</span><span class="sxs-lookup"><span data-stu-id="7e9b8-155">1</span></span> | <span data-ttu-id="7e9b8-156">概述</span><span class="sxs-lookup"><span data-stu-id="7e9b8-156">Overview</span></span> | <span data-ttu-id="7e9b8-157">整个录制的鸟瞰视图。</span><span class="sxs-lookup"><span data-stu-id="7e9b8-157">A birds-eye view of the entire recording.</span></span>  <span data-ttu-id="7e9b8-158">条形图的高度对应于调用堆栈的深度。</span><span class="sxs-lookup"><span data-stu-id="7e9b8-158">The height of the bars correspond to the depth of the call stack.</span></span>  <span data-ttu-id="7e9b8-159">因此，栏越高，调用堆栈越深。</span><span class="sxs-lookup"><span data-stu-id="7e9b8-159">So, the higher the bar, the deeper the call stack.</span></span>  |  
| <span data-ttu-id="7e9b8-160">ppls-2</span><span class="sxs-lookup"><span data-stu-id="7e9b8-160">2</span></span> | <span data-ttu-id="7e9b8-161">调用堆栈</span><span class="sxs-lookup"><span data-stu-id="7e9b8-161">Call Stacks</span></span> | <span data-ttu-id="7e9b8-162">这是在录制期间调用的函数的深入视图。</span><span class="sxs-lookup"><span data-stu-id="7e9b8-162">This is an in-depth view of the functions that were called during the recording.</span></span>  <span data-ttu-id="7e9b8-163">水平轴为时间，垂直轴为调用堆栈。</span><span class="sxs-lookup"><span data-stu-id="7e9b8-163">The horizontal axis is time and vertical axis is the call stack.</span></span>  <span data-ttu-id="7e9b8-164">堆叠按从上到下排列。</span><span class="sxs-lookup"><span data-stu-id="7e9b8-164">The stacks are organized top-down.</span></span>  <span data-ttu-id="7e9b8-165">因此，函数顶部称为该函数，依此类推。</span><span class="sxs-lookup"><span data-stu-id="7e9b8-165">So, the function on top called the one below it, and so on.</span></span>  |  

<span data-ttu-id="7e9b8-166">函数会随机着色。</span><span class="sxs-lookup"><span data-stu-id="7e9b8-166">Functions are colored randomly.</span></span>  <span data-ttu-id="7e9b8-167">与其他面板中使用的颜色没有关联。</span><span class="sxs-lookup"><span data-stu-id="7e9b8-167">There is no correlation to the colors used in the other panels.</span></span>  <span data-ttu-id="7e9b8-168">但是，函数在调用中始终具有相同的颜色，以便你可以在每个运行时中查看模式。</span><span class="sxs-lookup"><span data-stu-id="7e9b8-168">However, functions are always colored the same across invocations so that you are able to see patterns in each runtime.</span></span>  

> ##### <span data-ttu-id="7e9b8-169">图 6</span><span class="sxs-lookup"><span data-stu-id="7e9b8-169">Figure 6</span></span>  
> <span data-ttu-id="7e9b8-170">已标注的火焰图表</span><span class="sxs-lookup"><span data-stu-id="7e9b8-170">Annotated flame chart</span></span>  
> ![已标注的火焰图表][ImageAnnotatedFlameChart]  

<span data-ttu-id="7e9b8-172">高调用堆栈不一定很重要，它只意味着调用了大量函数。</span><span class="sxs-lookup"><span data-stu-id="7e9b8-172">A tall call stack is not necessarily significant, it just means that a lot of functions were called.</span></span>  <span data-ttu-id="7e9b8-173">但宽条表示某个函数需要很长时间才能完成。</span><span class="sxs-lookup"><span data-stu-id="7e9b8-173">But a wide bar means that a function took a long time to complete.</span></span>  <span data-ttu-id="7e9b8-174">这些是优化的候选项。</span><span class="sxs-lookup"><span data-stu-id="7e9b8-174">These are candidates for optimization.</span></span>  

### <span data-ttu-id="7e9b8-175">放大录制的特定部分</span><span class="sxs-lookup"><span data-stu-id="7e9b8-175">Zoom in on specific parts of recording</span></span>   

<span data-ttu-id="7e9b8-176">选择、按住，然后在概述中向左和向右拖动鼠标，以放大调用堆栈的特定部分。</span><span class="sxs-lookup"><span data-stu-id="7e9b8-176">Select, hold, and drag your mouse left and right across the overview to zoom in on particular parts of the call stack.</span></span>  <span data-ttu-id="7e9b8-177">缩放后，调用堆栈自动显示所选录制部分。</span><span class="sxs-lookup"><span data-stu-id="7e9b8-177">After you zoom, the call stack automatically displays the portion of the recording that you selected.</span></span>  

> ##### <span data-ttu-id="7e9b8-178">图 7</span><span class="sxs-lookup"><span data-stu-id="7e9b8-178">Figure 7</span></span>  
> <span data-ttu-id="7e9b8-179">缩放图表</span><span class="sxs-lookup"><span data-stu-id="7e9b8-179">Chart zoomed</span></span>  
> ![缩放图表][ImageFlameChartZoomed]  

### <span data-ttu-id="7e9b8-181">查看函数详细信息</span><span class="sxs-lookup"><span data-stu-id="7e9b8-181">View function details</span></span>   

<span data-ttu-id="7e9b8-182">选择一个函数以在 "**源**" 面板中查看定义。</span><span class="sxs-lookup"><span data-stu-id="7e9b8-182">Select on a function to view the definition in the **Sources** panel.</span></span>  

<span data-ttu-id="7e9b8-183">将鼠标悬停在函数上以显示名称和计时数据。</span><span class="sxs-lookup"><span data-stu-id="7e9b8-183">Hover over a function to display the name and timing data.</span></span>  <span data-ttu-id="7e9b8-184">提供以下信息。</span><span class="sxs-lookup"><span data-stu-id="7e9b8-184">The following information is provided.</span></span>  

| <span data-ttu-id="7e9b8-185">资料</span><span class="sxs-lookup"><span data-stu-id="7e9b8-185">Detail</span></span> | <span data-ttu-id="7e9b8-186">说明</span><span class="sxs-lookup"><span data-stu-id="7e9b8-186">Description</span></span> |  
|:--- |:--- |  
| **<span data-ttu-id="7e9b8-187">名称</span><span class="sxs-lookup"><span data-stu-id="7e9b8-187">Name</span></span>** | <span data-ttu-id="7e9b8-188">函数的名称。</span><span class="sxs-lookup"><span data-stu-id="7e9b8-188">The name of the function.</span></span>  |  
| **<span data-ttu-id="7e9b8-189">自大小</span><span class="sxs-lookup"><span data-stu-id="7e9b8-189">Self size</span></span>** | <span data-ttu-id="7e9b8-190">函数的当前调用的大小，包括函数中的语句。</span><span class="sxs-lookup"><span data-stu-id="7e9b8-190">The size of the current invocation of the function, including only the statements in the function.</span></span>  |  
| **<span data-ttu-id="7e9b8-191">总大小</span><span class="sxs-lookup"><span data-stu-id="7e9b8-191">Total size</span></span>** | <span data-ttu-id="7e9b8-192">此函数及其调用的任何函数的当前调用的大小。</span><span class="sxs-lookup"><span data-stu-id="7e9b8-192">The size of the current invocation of this function and any functions that it called.</span></span>  |  
| **<span data-ttu-id="7e9b8-193">URL</span><span class="sxs-lookup"><span data-stu-id="7e9b8-193">URL</span></span>** | <span data-ttu-id="7e9b8-194">函数定义在 where 的形式的位置 `base.js:261` `base.js` 是定义函数的文件的名称，并且 `261` 是定义的行号。</span><span class="sxs-lookup"><span data-stu-id="7e9b8-194">The location of the function definition in the form of `base.js:261` where `base.js` is the name of the file where the function is defined and `261` is the line number of the definition.</span></span>  |  
<!--*   **Aggregated self time**.  Aggregate time for all invocations of the function across the recording, not including functions called by this function.  -->  
<!--*   **Aggregated total time**.  Aggregate total time for all invocations of the function, including functions called by this function.  -->  
<!--*   **Not optimized**.  If the profiler has detected a potential optimization for the function it lists it here.  -->  

> ##### <span data-ttu-id="7e9b8-195">图 8</span><span class="sxs-lookup"><span data-stu-id="7e9b8-195">Figure 8</span></span>  
> <span data-ttu-id="7e9b8-196">查看图表中的函数详细信息</span><span class="sxs-lookup"><span data-stu-id="7e9b8-196">Viewing functions details in chart</span></span>  
> ![查看图表中的函数详细信息][ImageFunctionsDetails]  

<!--## Feedback   -->  



<!-- image links -->  

[ImageExcludeIcon]: /microsoft-edge/devtools-guide-chromium/media/exclude-icon.msft.png  
[ImageFocusIcon]: /microsoft-edge/devtools-guide-chromium/media/images/focus-icon.msft.png  
[ImageRestoreIcon]: /microsoft-edge/devtools-guide-chromium/media/images/restore-icon.msft.png  

[ImageCpuProfile]: /microsoft-edge/devtools-guide-chromium/media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-heavy-bottom-up.msft.png "图1：采样配置文件"  
[ImageFlameChart]: /microsoft-edge/devtools-guide-chromium/media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart.msft.png "图2：火焰图"  
[ImageHeavyChart]: /microsoft-edge/devtools-guide-chromium/media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-heavy-bottom-up.msft.png "图3：厚图"  
[ImageTreeChart]: /microsoft-edge/devtools-guide-chromium/media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-tree-top-down.msft.png "图4：树形图"  
[ImageFlameChartView]: /microsoft-edge/devtools-guide-chromium/media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart.msft.png "图5：火焰图表视图"  
[ImageAnnotatedFlameChart]: /microsoft-edge/devtools-guide-chromium/media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-highlighted.msft.png "图6：带批注的火焰图表"  
[ImageFlameChartZoomed]: /microsoft-edge/devtools-guide-chromium/media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-zoomed.msft.png "图7：缩放图表"  
[ImageFunctionsDetails]: /microsoft-edge/devtools-guide-chromium/media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-hover.msft.png "图8：在图表中查看函数的详细信息"  

<!-- links -->  

[DevtoolsConsoleUtilities]: /microsoft-edge/devtools-guide-chromium/console/utilities "控制台实用工具 API 参考"  
[DevtoolsConsoleUtilitiesProfile]: /microsoft-edge/devtools-guide-chromium/console/utilities#profile "配置文件-控制台实用工具 API 参考"  
[DevtoolsConsoleUtilitiesProfileEnd]: /microsoft-edge/devtools-guide-chromium/console/utilities#profileend "profileEnd-控制台实用工具 API 参考"  

> [!NOTE]
> <span data-ttu-id="7e9b8-209">此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="7e9b8-209">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="7e9b8-210">原始页面可在[此处](https://developers.google.com/web/tools/chrome-devtools/rendering-tools/js-execution)找到，并由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools & Lighthouse \）和[Meggin Kearney][MegginKearney] \ （技术作者 \）创作。</span><span class="sxs-lookup"><span data-stu-id="7e9b8-210">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/rendering-tools/js-execution) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools & Lighthouse\) and [Meggin Kearney][MegginKearney] \(Tech Writer\).</span></span>  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
<span data-ttu-id="7e9b8-212">此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="7e9b8-212">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
