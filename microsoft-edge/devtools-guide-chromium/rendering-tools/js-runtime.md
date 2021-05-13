---
description: 使用 Microsoft Edge DevTools 内存面板识别内存占用大的函数。
title: 加速 JavaScript 运行时
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge，web 开发，f12 工具，devtools
ms.openlocfilehash: bbac00ab46e205fb692cc3de3e5f08ba854b0911
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2021
ms.locfileid: "11565083"
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
# <a name="speed-up-javascript-runtime"></a><span data-ttu-id="76bf1-104">加速 JavaScript 运行时</span><span class="sxs-lookup"><span data-stu-id="76bf1-104">Speed up JavaScript runtime</span></span>  

<span data-ttu-id="76bf1-105">使用**内存**工具识别内存占用大的函数。</span><span class="sxs-lookup"><span data-stu-id="76bf1-105">Identify expensive functions using the **Memory** tool.</span></span>  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-heavy-bottom-up.msft.png" alt-text="示例配置文件" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-heavy-bottom-up.msft.png":::
   <span data-ttu-id="76bf1-107">示例配置文件</span><span class="sxs-lookup"><span data-stu-id="76bf1-107">Sample Profiles</span></span>  
:::image-end:::  

### <a name="summary"></a><span data-ttu-id="76bf1-108">摘要</span><span class="sxs-lookup"><span data-stu-id="76bf1-108">Summary</span></span>  

*   <span data-ttu-id="76bf1-109">使用**内存**工具中的分配采样准确记录调用了哪些函数以及每个函数所需的内存。</span><span class="sxs-lookup"><span data-stu-id="76bf1-109">Record exactly which functions were called and how much memory each requires with Allocation Sampling in the **Memory** tool.</span></span>  
*   <span data-ttu-id="76bf1-110">将配置文件可视化为火焰图。</span><span class="sxs-lookup"><span data-stu-id="76bf1-110">Visualize your profiles as a flame chart.</span></span>  
    
## <a name="record-a-sampling-profile"></a><span data-ttu-id="76bf1-111">记录采样配置文件</span><span class="sxs-lookup"><span data-stu-id="76bf1-111">Record a Sampling Profile</span></span>  

<span data-ttu-id="76bf1-112">如果在 JavaScript 中发现垃圾，请收集采样配置文件。</span><span class="sxs-lookup"><span data-stu-id="76bf1-112">If you notice jank in your JavaScript, collect a Sampling Profile.</span></span>  <span data-ttu-id="76bf1-113">采样配置文件会显示页面中函数花费的运行时间。</span><span class="sxs-lookup"><span data-stu-id="76bf1-113">Sampling Profiles show where running time is spent on functions in your page.</span></span>  

1.  <span data-ttu-id="76bf1-114">导航到 DevTools 的**内存**工具。</span><span class="sxs-lookup"><span data-stu-id="76bf1-114">Navigate to the **Memory** tool of DevTools.</span></span>  
1.  <span data-ttu-id="76bf1-115">选择“**分配采样**”按钮。</span><span class="sxs-lookup"><span data-stu-id="76bf1-115">Choose the **Allocation sampling** radio button.</span></span>  
1.  <span data-ttu-id="76bf1-116">选择“**开始”**</span><span class="sxs-lookup"><span data-stu-id="76bf1-116">Choose **Start**.</span></span>  
1.  <span data-ttu-id="76bf1-117">根据你尝试分析的内容，可以刷新页面、与页面交互，或者只让页面运行。</span><span class="sxs-lookup"><span data-stu-id="76bf1-117">Depending on what you are trying to analyze, you may either refresh the page, interact with the page, or just let the page run.</span></span>  
1.  <span data-ttu-id="76bf1-118">完成后，选择“**停止**”。</span><span class="sxs-lookup"><span data-stu-id="76bf1-118">Choose the **Stop** button when you are finished.</span></span>  
    
> [!NOTE]
> <span data-ttu-id="76bf1-119">还可以使用[控制台实用程序 API][DevtoolsConsoleUtilities] 记录和分组命令行的配置文件。</span><span class="sxs-lookup"><span data-stu-id="76bf1-119">You may also use the [Console Utilities API][DevtoolsConsoleUtilities] to record and group profiles from the command line.</span></span>  

## <a name="view-sampling-profile"></a><span data-ttu-id="76bf1-120">查看采样配置文件</span><span class="sxs-lookup"><span data-stu-id="76bf1-120">View Sampling Profile</span></span>  

<span data-ttu-id="76bf1-121">记录完成后，DevTools 会使用记录的数据自动填充**采样配置文件**下的**内存**面板。</span><span class="sxs-lookup"><span data-stu-id="76bf1-121">When you finish recording, DevTools automatically populates the **Memory** panel under **SAMPLING PROFILES** with the data from your recording.</span></span>  

<span data-ttu-id="76bf1-122">默认视图为**走势图\（自下而上\）**。</span><span class="sxs-lookup"><span data-stu-id="76bf1-122">The default view is **Heavy \(Bottom Up\)**.</span></span>  <span data-ttu-id="76bf1-123">使用该视图允可以查看哪些函数对性能影响最大，并检查每个函数的请求路径。</span><span class="sxs-lookup"><span data-stu-id="76bf1-123">This view allows you to review which functions had the most impact on performance and examine the requesting path for each function.</span></span>  

### <a name="change-sort-order"></a><span data-ttu-id="76bf1-124">更改排序顺序</span><span class="sxs-lookup"><span data-stu-id="76bf1-124">Change sort order</span></span>  

<span data-ttu-id="76bf1-125">若要更改排序顺序，请选择“**聚焦定函数**”\（![聚焦选定函数](../media/focus-icon.msft.png)\）图标旁边的下拉菜单，然后从下列选项中选择一个。</span><span class="sxs-lookup"><span data-stu-id="76bf1-125">To change the sorting order, select the dropdown menu next to the **focus selected function** \(![focus selected function](../media/focus-icon.msft.png)\) icon and then choose one of the following options.</span></span>

<span data-ttu-id="76bf1-126">**图表**。</span><span class="sxs-lookup"><span data-stu-id="76bf1-126">**Chart**.</span></span>  <span data-ttu-id="76bf1-127">显示记录的时序图。</span><span class="sxs-lookup"><span data-stu-id="76bf1-127">Displays a chronological chart of the recording.</span></span>  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart.msft.png" alt-text="火焰图" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart.msft.png":::
   <span data-ttu-id="76bf1-129">火焰图</span><span class="sxs-lookup"><span data-stu-id="76bf1-129">Flame chart</span></span>  
:::image-end:::  

<span data-ttu-id="76bf1-130">**走势图\（自下而上\）**。</span><span class="sxs-lookup"><span data-stu-id="76bf1-130">**Heavy \(Bottom Up\)**.</span></span>  <span data-ttu-id="76bf1-131">根据对性能的影响列出函数，并使你能够检查函数的调用路径。</span><span class="sxs-lookup"><span data-stu-id="76bf1-131">Lists functions by impact on performance and enables you to examine the calling paths to the functions.</span></span>  <span data-ttu-id="76bf1-132">这是默认视图。</span><span class="sxs-lookup"><span data-stu-id="76bf1-132">This is the default view.</span></span>  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-heavy-bottom-up.msft.png" alt-text="走势图" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-heavy-bottom-up.msft.png":::
   <span data-ttu-id="76bf1-134">走势图</span><span class="sxs-lookup"><span data-stu-id="76bf1-134">Heavy chart</span></span>  
:::image-end:::  

<span data-ttu-id="76bf1-135">**树状视图\（自上而下\）**。</span><span class="sxs-lookup"><span data-stu-id="76bf1-135">**Tree \(Top Down\)**.</span></span>  <span data-ttu-id="76bf1-136">显示调用结构的整体图片，从调用堆栈的顶部开始。</span><span class="sxs-lookup"><span data-stu-id="76bf1-136">Shows an overall picture of the calling structure, starting at the top of the call stack.</span></span>  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-tree-top-down.msft.png" alt-text="树状图" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-tree-top-down.msft.png":::
   <span data-ttu-id="76bf1-138">树状图</span><span class="sxs-lookup"><span data-stu-id="76bf1-138">Tree chart</span></span>  
:::image-end:::  

### <a name="exclude-functions"></a><span data-ttu-id="76bf1-139">排除函数</span><span class="sxs-lookup"><span data-stu-id="76bf1-139">Exclude functions</span></span>  

<span data-ttu-id="76bf1-140">若要从采样配置文件中排除函数，请选择该函数，然后选择“**排除所选函数**”\（![排除所选函数](../media/exclude-icon.msft.png)\）按钮。</span><span class="sxs-lookup"><span data-stu-id="76bf1-140">To exclude a function from your Sampling Profile, choose it and then choose the **exclude selected function** \(![exclude selected function](../media/exclude-icon.msft.png)\) button.</span></span>  <span data-ttu-id="76bf1-141">已排除函数\（子级\）的请求函数\（父级\）将占用分配给已排除函数\（子级\）的分配内存。</span><span class="sxs-lookup"><span data-stu-id="76bf1-141">The requesting function \(parent\) of the excluded function \(child\) is charged with the allocated memory assigned to the excluded function \(child\).</span></span>  

<span data-ttu-id="76bf1-142">选择“**还原全部函数**”\（还原全部函数![ ](../media/restore-icon.msft.png)\）按钮将所有已排除函数还原到记录中。</span><span class="sxs-lookup"><span data-stu-id="76bf1-142">Choose the **restore all functions** \(![restore all functions](../media/restore-icon.msft.png)\) button to restore all excluded functions back into the recording.</span></span>  

## <a name="view-sampling-profile-as-chart"></a><span data-ttu-id="76bf1-143">以图表模式查看采样配置文件</span><span class="sxs-lookup"><span data-stu-id="76bf1-143">View Sampling Profile as Chart</span></span>  

<span data-ttu-id="76bf1-144">图表视图能直观表示随时间变化的取样配置文件。</span><span class="sxs-lookup"><span data-stu-id="76bf1-144">The Chart view provides a visual representation of the Sampling Profile over time.</span></span>  

<span data-ttu-id="76bf1-145">[记录采样配置文件](#record-a-sampling-profile)后，将[排序顺序更改](#change-sort-order)为**图表**，以使用火焰图查看记录。</span><span class="sxs-lookup"><span data-stu-id="76bf1-145">After you [record a Sampling Profile](#record-a-sampling-profile), view the recording as a flame chart by [changing the sort order](#change-sort-order) to **Chart**.</span></span>  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart.msft.png" alt-text="火焰图视图" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart.msft.png":::
   <span data-ttu-id="76bf1-147">火焰图视图</span><span class="sxs-lookup"><span data-stu-id="76bf1-147">Flame chart view</span></span>  
:::image-end:::  

<span data-ttu-id="76bf1-148">火焰图图表拆分为两个部分。</span><span class="sxs-lookup"><span data-stu-id="76bf1-148">The flame chart is split into two parts.</span></span>  

| <span data-ttu-id="76bf1-149">索引</span><span class="sxs-lookup"><span data-stu-id="76bf1-149">index</span></span> | <span data-ttu-id="76bf1-150">部分</span><span class="sxs-lookup"><span data-stu-id="76bf1-150">Part</span></span> | <span data-ttu-id="76bf1-151">描述</span><span class="sxs-lookup"><span data-stu-id="76bf1-151">Description</span></span> |  
| --- |:--- |:--- |  
| <span data-ttu-id="76bf1-152">1</span><span class="sxs-lookup"><span data-stu-id="76bf1-152">1</span></span> | <span data-ttu-id="76bf1-153">概述</span><span class="sxs-lookup"><span data-stu-id="76bf1-153">Overview</span></span> | <span data-ttu-id="76bf1-154">整个记录的鸟瞰图。</span><span class="sxs-lookup"><span data-stu-id="76bf1-154">A birds-eye view of the entire recording.</span></span>  <span data-ttu-id="76bf1-155">条形图的高度对应调用堆栈的深度。</span><span class="sxs-lookup"><span data-stu-id="76bf1-155">The height of the bars correspond to the depth of the call stack.</span></span>  <span data-ttu-id="76bf1-156">因此，条形图越高，调用堆栈越深。</span><span class="sxs-lookup"><span data-stu-id="76bf1-156">So, the higher the bar, the deeper the call stack.</span></span>  |  
| <span data-ttu-id="76bf1-157">2</span><span class="sxs-lookup"><span data-stu-id="76bf1-157">2</span></span> | <span data-ttu-id="76bf1-158">调用堆栈</span><span class="sxs-lookup"><span data-stu-id="76bf1-158">Call Stacks</span></span> | <span data-ttu-id="76bf1-159">这是在记录过程中调用的函数的深入视图。</span><span class="sxs-lookup"><span data-stu-id="76bf1-159">This is an in-depth view of the functions that were called during the recording.</span></span>  <span data-ttu-id="76bf1-160">水平轴为时间，垂直轴为调用堆栈。</span><span class="sxs-lookup"><span data-stu-id="76bf1-160">The horizontal axis is time and vertical axis is the call stack.</span></span>  <span data-ttu-id="76bf1-161">堆栈是自上而下组织的。</span><span class="sxs-lookup"><span data-stu-id="76bf1-161">The stacks are organized top-down.</span></span>  <span data-ttu-id="76bf1-162">因此，顶部的函数调用它下面的函数，以此类推。</span><span class="sxs-lookup"><span data-stu-id="76bf1-162">So, the function on top called the one below it, and so on.</span></span>  |  

<span data-ttu-id="76bf1-163">函数颜色随机。</span><span class="sxs-lookup"><span data-stu-id="76bf1-163">Functions are colored randomly.</span></span>  <span data-ttu-id="76bf1-164">与其他面板中使用的颜色没有任何关联。</span><span class="sxs-lookup"><span data-stu-id="76bf1-164">There is no correlation to the colors used in the other panels.</span></span>  <span data-ttu-id="76bf1-165">然而，函数在整个调用中的颜色都是相同的，这样你就可以观察到每个运行时的模式。</span><span class="sxs-lookup"><span data-stu-id="76bf1-165">However, functions are always colored the same across invocations so that you may observe patterns in each runtime.</span></span>  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-highlighted.msft.png" alt-text="带批注的火焰图" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-highlighted.msft.png":::
   <span data-ttu-id="76bf1-167">带批注的火焰图</span><span class="sxs-lookup"><span data-stu-id="76bf1-167">Annotated flame chart</span></span>  
:::image-end:::  

<span data-ttu-id="76bf1-168">较高的调用堆栈不一定重要，它只是意味着调用了许多函数。</span><span class="sxs-lookup"><span data-stu-id="76bf1-168">A tall call stack is not necessarily significant, it just means that a lot of functions were called.</span></span>  <span data-ttu-id="76bf1-169">但较宽的条形图意味着函数完成时间花费很长。</span><span class="sxs-lookup"><span data-stu-id="76bf1-169">But a wide bar means that a function took a long time to complete.</span></span>  <span data-ttu-id="76bf1-170">这些都是需要优化的候选项。</span><span class="sxs-lookup"><span data-stu-id="76bf1-170">These are candidates for optimization.</span></span>  

### <a name="zoom-in-on-specific-parts-of-recording"></a><span data-ttu-id="76bf1-171">放大记录的特定部分</span><span class="sxs-lookup"><span data-stu-id="76bf1-171">Zoom in on specific parts of recording</span></span>  

<span data-ttu-id="76bf1-172">在概览上选择、按住并左右拖动鼠标，以放大调用堆栈的特定部分。</span><span class="sxs-lookup"><span data-stu-id="76bf1-172">Choose, hold, and drag your mouse left and right across the overview to zoom in on particular parts of the call stack.</span></span>  <span data-ttu-id="76bf1-173">放大后，调用堆栈自动显示所选记录的部分。</span><span class="sxs-lookup"><span data-stu-id="76bf1-173">After you zoom, the call stack automatically displays the portion of the recording that you selected.</span></span>  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-zoomed.msft.png" alt-text="已放大的图表" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-zoomed.msft.png":::
   <span data-ttu-id="76bf1-175">已放大的图表</span><span class="sxs-lookup"><span data-stu-id="76bf1-175">Chart zoomed</span></span>  
:::image-end:::  

### <a name="view-function-details"></a><span data-ttu-id="76bf1-176">查看函数详细信息</span><span class="sxs-lookup"><span data-stu-id="76bf1-176">View function details</span></span>  

<span data-ttu-id="76bf1-177">选择函数以查看在**源**工具中的定义。</span><span class="sxs-lookup"><span data-stu-id="76bf1-177">Choose a function to view the definition in the **Sources** tool.</span></span>  

<span data-ttu-id="76bf1-178">将鼠标悬停在函数上可显示名称和计时数据。</span><span class="sxs-lookup"><span data-stu-id="76bf1-178">Hover on a function to display the name and timing data.</span></span>  <span data-ttu-id="76bf1-179">将提供以下信息。</span><span class="sxs-lookup"><span data-stu-id="76bf1-179">The following information is provided.</span></span>  

| <span data-ttu-id="76bf1-180">详情</span><span class="sxs-lookup"><span data-stu-id="76bf1-180">Detail</span></span> | <span data-ttu-id="76bf1-181">描述</span><span class="sxs-lookup"><span data-stu-id="76bf1-181">Description</span></span> |  
|:--- |:--- |  
| **<span data-ttu-id="76bf1-182">名称</span><span class="sxs-lookup"><span data-stu-id="76bf1-182">Name</span></span>** | <span data-ttu-id="76bf1-183">函数的名称。</span><span class="sxs-lookup"><span data-stu-id="76bf1-183">The name of the function.</span></span>  |  
| **<span data-ttu-id="76bf1-184">自身大小</span><span class="sxs-lookup"><span data-stu-id="76bf1-184">Self size</span></span>** | <span data-ttu-id="76bf1-185">函数当前调用的大小，只包括函数中的语句。</span><span class="sxs-lookup"><span data-stu-id="76bf1-185">The size of the current invocation of the function, including only the statements in the function.</span></span>  |  
| **<span data-ttu-id="76bf1-186">总大小</span><span class="sxs-lookup"><span data-stu-id="76bf1-186">Total size</span></span>** | <span data-ttu-id="76bf1-187">该函数当前调用及其调用过的任何函数的大小。</span><span class="sxs-lookup"><span data-stu-id="76bf1-187">The size of the current invocation of this function and any functions that it called.</span></span>  |  
| **<span data-ttu-id="76bf1-188">URL</span><span class="sxs-lookup"><span data-stu-id="76bf1-188">URL</span></span>** | <span data-ttu-id="76bf1-189">函数定义的位置以 `base.js:261` 的形式表示，其中 `base.js` 是定义函数的文件的名称，而 `261` 是定义的行号。</span><span class="sxs-lookup"><span data-stu-id="76bf1-189">The location of the function definition in the form of `base.js:261` where `base.js` is the name of the file where the function is defined and `261` is the line number of the definition.</span></span>  |  
<!--*   **Aggregated self time**.  Aggregate time for all invocations of the function across the recording, not including functions called by this function.  -->  
<!--*   **Aggregated total time**.  Aggregate total time for all invocations of the function, including functions called by this function.  -->  
<!--*   **Not optimized**.  If the profiler has detected a potential optimization for the function it lists it here.  -->  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-hover.msft.png" alt-text="使用图表查看函数详细信息" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-hover.msft.png":::
   <span data-ttu-id="76bf1-191">使用图表查看函数详细信息</span><span class="sxs-lookup"><span data-stu-id="76bf1-191">View functions details in chart</span></span>  
:::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="76bf1-192">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="76bf1-192">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsConsoleUtilities]: ../console/utilities.md "控制台实用程序 API 参考 | Microsoft Docs"  
[DevtoolsConsoleUtilitiesProfile]: ../console/utilities.md#profile "配置文件 - 控制台实用程序 API 参考 | Microsoft Docs"  
[DevtoolsConsoleUtilitiesProfileEnd]: ../console/utilities.md#profileend "profileEnd - 控制台实用程序 API 参考 | Microsoft Docs"  

> [!NOTE]
> <span data-ttu-id="76bf1-196">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="76bf1-196">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="76bf1-197">[此处](https://developers.google.com/web/tools/chrome-devtools/rendering-tools/js-execution)可以找到原始页面，由 [Kayce Basques][KayceBasques] \（技术写作人员，Chrome DevTools \& Lighthouse\）和 [Meggin Kearney][MegginKearney] \（技术写作人员\）编写。</span><span class="sxs-lookup"><span data-stu-id="76bf1-197">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/rendering-tools/js-execution) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\) and [Meggin Kearney][MegginKearney] \(Tech Writer\).</span></span>  

[![知识共享许可协议][CCby4Image]][CCA4IL]  
<span data-ttu-id="76bf1-199">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="76bf1-199">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
[MegginKearney]: https://developers.google.com/web/resources/contributors#meggin-kearney  
