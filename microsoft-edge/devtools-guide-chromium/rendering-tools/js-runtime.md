---
description: 使用 Microsoft Edge DevTools 内存面板确定昂贵的功能。
title: 加速 JavaScript 运行时
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: 2151777c6a9f94408f48552839531c3534d3de36
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439736"
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

# <a name="speed-up-javascript-runtime"></a><span data-ttu-id="91afd-104">加速 JavaScript 运行时</span><span class="sxs-lookup"><span data-stu-id="91afd-104">Speed up JavaScript runtime</span></span>  

<span data-ttu-id="91afd-105">使用内存工具识别 **昂贵的** 函数。</span><span class="sxs-lookup"><span data-stu-id="91afd-105">Identify expensive functions using the **Memory** tool.</span></span>  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-heavy-bottom-up.msft.png" alt-text="示例配置文件" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-heavy-bottom-up.msft.png":::
   <span data-ttu-id="91afd-107">示例配置文件</span><span class="sxs-lookup"><span data-stu-id="91afd-107">Sample Profiles</span></span>  
:::image-end:::  

### <a name="summary"></a><span data-ttu-id="91afd-108">摘要</span><span class="sxs-lookup"><span data-stu-id="91afd-108">Summary</span></span>  

*   <span data-ttu-id="91afd-109">使用内存工具中的分配采样准确记录调用的函数以及每个函数 **所需的内存** 量。</span><span class="sxs-lookup"><span data-stu-id="91afd-109">Record exactly which functions were called and how much memory each requires with Allocation Sampling in the **Memory** tool.</span></span>  
*   <span data-ttu-id="91afd-110">将你的配置文件可视化为一个图表。</span><span class="sxs-lookup"><span data-stu-id="91afd-110">Visualize your profiles as a flame chart.</span></span>  
    
## <a name="record-a-sampling-profile"></a><span data-ttu-id="91afd-111">记录采样配置文件</span><span class="sxs-lookup"><span data-stu-id="91afd-111">Record a Sampling Profile</span></span>  

<span data-ttu-id="91afd-112">如果你注意到 JavaScript 中的 jank，请收集一个采样配置文件。</span><span class="sxs-lookup"><span data-stu-id="91afd-112">If you notice jank in your JavaScript, collect a Sampling Profile.</span></span>  <span data-ttu-id="91afd-113">采样配置文件显示运行时间在页面中函数的花费位置。</span><span class="sxs-lookup"><span data-stu-id="91afd-113">Sampling Profiles show where running time is spent on functions in your page.</span></span>  

1.  <span data-ttu-id="91afd-114">导航到 **DevTools** 的内存工具。</span><span class="sxs-lookup"><span data-stu-id="91afd-114">Navigate to the **Memory** tool of DevTools.</span></span>  
1.  <span data-ttu-id="91afd-115">选择" **分配采样"** 单选按钮。</span><span class="sxs-lookup"><span data-stu-id="91afd-115">Choose the **Allocation sampling** radio button.</span></span>  
1.  <span data-ttu-id="91afd-116">选择"**开始"。**</span><span class="sxs-lookup"><span data-stu-id="91afd-116">Choose **Start**.</span></span>  
1.  <span data-ttu-id="91afd-117">根据你尝试分析的内容，你可以刷新页面、与页面交互，或者只让页面运行。</span><span class="sxs-lookup"><span data-stu-id="91afd-117">Depending on what you are trying to analyze, you may either refresh the page, interact with the page, or just let the page run.</span></span>  
1.  <span data-ttu-id="91afd-118">完成后 **，选择** "停止"按钮。</span><span class="sxs-lookup"><span data-stu-id="91afd-118">Choose the **Stop** button when you are finished.</span></span>  
    
> [!NOTE]
> <span data-ttu-id="91afd-119">您还可以使用控制台实用程序 [API][DevtoolsConsoleUtilities] 从命令行记录和分组配置文件。</span><span class="sxs-lookup"><span data-stu-id="91afd-119">You may also use the [Console Utilities API][DevtoolsConsoleUtilities] to record and group profiles from the command line.</span></span>  

## <a name="view-sampling-profile"></a><span data-ttu-id="91afd-120">查看采样配置文件</span><span class="sxs-lookup"><span data-stu-id="91afd-120">View Sampling Profile</span></span>  

<span data-ttu-id="91afd-121">完成录制后，DevTools 会自动使用录制的数据\*\*\*\* 填充 **"采样配置文件**"下的"内存"面板。</span><span class="sxs-lookup"><span data-stu-id="91afd-121">When you finish recording, DevTools automatically populates the **Memory** panel under **SAMPLING PROFILES** with the data from your recording.</span></span>  

<span data-ttu-id="91afd-122">默认视图为 \*\*"粗 (从下向上\) "。 \*\*</span><span class="sxs-lookup"><span data-stu-id="91afd-122">The default view is **Heavy \(Bottom Up\)**.</span></span>  <span data-ttu-id="91afd-123">此视图允许您查看哪些函数对性能影响最大，并检查每个函数的请求路径。</span><span class="sxs-lookup"><span data-stu-id="91afd-123">This view allows you to review which functions had the most impact on performance and examine the requesting path for each function.</span></span>  

### <a name="change-sort-order"></a><span data-ttu-id="91afd-124">更改排序顺序</span><span class="sxs-lookup"><span data-stu-id="91afd-124">Change sort order</span></span>  

<span data-ttu-id="91afd-125">若要更改排序顺序，请选择焦点选定函数 **\ (** 焦点选定函数 \) 图标旁边的下拉菜单，然后选择下列 ![ ](../media/focus-icon.msft.png) 选项之一。</span><span class="sxs-lookup"><span data-stu-id="91afd-125">To change the sorting order, select the dropdown menu next to the **focus selected function** \(![focus selected function](../media/focus-icon.msft.png)\) icon and then choose one of the following options.</span></span>

<span data-ttu-id="91afd-126">**图表**。</span><span class="sxs-lookup"><span data-stu-id="91afd-126">**Chart**.</span></span>  <span data-ttu-id="91afd-127">显示记录的时间顺序图表。</span><span class="sxs-lookup"><span data-stu-id="91afd-127">Displays a chronological chart of the recording.</span></span>  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart.msft.png" alt-text="饼图" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart.msft.png":::
   <span data-ttu-id="91afd-129">饼图</span><span class="sxs-lookup"><span data-stu-id="91afd-129">Flame chart</span></span>  
:::image-end:::  

<span data-ttu-id="91afd-130">\*\*粗 \ (Bottom Up\) \*\*。</span><span class="sxs-lookup"><span data-stu-id="91afd-130">**Heavy \(Bottom Up\)**.</span></span>  <span data-ttu-id="91afd-131">根据对性能的影响列出函数，并使您能够检查函数的调用路径。</span><span class="sxs-lookup"><span data-stu-id="91afd-131">Lists functions by impact on performance and enables you to examine the calling paths to the functions.</span></span>  <span data-ttu-id="91afd-132">这是默认视图。</span><span class="sxs-lookup"><span data-stu-id="91afd-132">This is the default view.</span></span>  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-heavy-bottom-up.msft.png" alt-text="粗图表" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-heavy-bottom-up.msft.png":::
   <span data-ttu-id="91afd-134">粗图表</span><span class="sxs-lookup"><span data-stu-id="91afd-134">Heavy chart</span></span>  
:::image-end:::  

<span data-ttu-id="91afd-135">\*\*树 \ (Top Down\) \*\*。</span><span class="sxs-lookup"><span data-stu-id="91afd-135">**Tree \(Top Down\)**.</span></span>  <span data-ttu-id="91afd-136">显示调用结构的整体图片，从调用堆栈的顶部开始。</span><span class="sxs-lookup"><span data-stu-id="91afd-136">Shows an overall picture of the calling structure, starting at the top of the call stack.</span></span>  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-tree-top-down.msft.png" alt-text="树形图" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-tree-top-down.msft.png":::
   <span data-ttu-id="91afd-138">树形图</span><span class="sxs-lookup"><span data-stu-id="91afd-138">Tree chart</span></span>  
:::image-end:::  

### <a name="exclude-functions"></a><span data-ttu-id="91afd-139">排除函数</span><span class="sxs-lookup"><span data-stu-id="91afd-139">Exclude functions</span></span>  

<span data-ttu-id="91afd-140">若要从采样配置文件中排除函数，请选择该函数，然后选择排除选定函数 **\ (** 排除所选函数 ![ ](../media/exclude-icon.msft.png) \) 按钮。</span><span class="sxs-lookup"><span data-stu-id="91afd-140">To exclude a function from your Sampling Profile, choose it and then choose the **exclude selected function** \(![exclude selected function](../media/exclude-icon.msft.png)\) button.</span></span>  <span data-ttu-id="91afd-141">已排除函数 \ (child\) 的请求函数 \ (parent\) 将收取分配给已排除函数 \ (child\) 的分配内存。</span><span class="sxs-lookup"><span data-stu-id="91afd-141">The requesting function \(parent\) of the excluded function \(child\) is charged with the allocated memory assigned to the excluded function \(child\).</span></span>  

<span data-ttu-id="91afd-142">Choose the **restore all functions** \ (restore all functions ![ ](../media/restore-icon.msft.png) \) button to restore all excluded functions back into the recording.</span><span class="sxs-lookup"><span data-stu-id="91afd-142">Choose the **restore all functions** \(![restore all functions](../media/restore-icon.msft.png)\) button to restore all excluded functions back into the recording.</span></span>  

## <a name="view-sampling-profile-as-chart"></a><span data-ttu-id="91afd-143">以图表模式查看采样配置文件</span><span class="sxs-lookup"><span data-stu-id="91afd-143">View Sampling Profile as Chart</span></span>  

<span data-ttu-id="91afd-144">"图表"视图提供一段时间取样配置文件的直观表示形式。</span><span class="sxs-lookup"><span data-stu-id="91afd-144">The Chart view provides a visual representation of the Sampling Profile over time.</span></span>  

<span data-ttu-id="91afd-145">录制[采样配置文件后](#record-a-sampling-profile)，将排序顺序更改为图表，以作为[饼图](#change-sort-order)**查看记录**。</span><span class="sxs-lookup"><span data-stu-id="91afd-145">After you [record a Sampling Profile](#record-a-sampling-profile), view the recording as a flame chart by [changing the sort order](#change-sort-order) to **Chart**.</span></span>  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart.msft.png" alt-text="饼图视图" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart.msft.png":::
   <span data-ttu-id="91afd-147">饼图视图</span><span class="sxs-lookup"><span data-stu-id="91afd-147">Flame chart view</span></span>  
:::image-end:::  

<span data-ttu-id="91afd-148">图表拆分为两个部分。</span><span class="sxs-lookup"><span data-stu-id="91afd-148">The flame chart is split into two parts.</span></span>  

| <span data-ttu-id="91afd-149">index</span><span class="sxs-lookup"><span data-stu-id="91afd-149">index</span></span> | <span data-ttu-id="91afd-150">部件</span><span class="sxs-lookup"><span data-stu-id="91afd-150">Part</span></span> | <span data-ttu-id="91afd-151">描述</span><span class="sxs-lookup"><span data-stu-id="91afd-151">Description</span></span> |  
| --- |:--- |:--- |  
| <span data-ttu-id="91afd-152">1</span><span class="sxs-lookup"><span data-stu-id="91afd-152">1</span></span> | <span data-ttu-id="91afd-153">概述</span><span class="sxs-lookup"><span data-stu-id="91afd-153">Overview</span></span> | <span data-ttu-id="91afd-154">整个录制的鸟瞰图。</span><span class="sxs-lookup"><span data-stu-id="91afd-154">A birds-eye view of the entire recording.</span></span>  <span data-ttu-id="91afd-155">条形的高度与调用堆栈的深度相对应。</span><span class="sxs-lookup"><span data-stu-id="91afd-155">The height of the bars correspond to the depth of the call stack.</span></span>  <span data-ttu-id="91afd-156">因此，条形越深，调用堆栈越深。</span><span class="sxs-lookup"><span data-stu-id="91afd-156">So, the higher the bar, the deeper the call stack.</span></span>  |  
| <span data-ttu-id="91afd-157">2</span><span class="sxs-lookup"><span data-stu-id="91afd-157">2</span></span> | <span data-ttu-id="91afd-158">调用堆栈</span><span class="sxs-lookup"><span data-stu-id="91afd-158">Call Stacks</span></span> | <span data-ttu-id="91afd-159">这是在录制过程中调用的函数的深入视图。</span><span class="sxs-lookup"><span data-stu-id="91afd-159">This is an in-depth view of the functions that were called during the recording.</span></span>  <span data-ttu-id="91afd-160">水平轴为时间，垂直轴为调用堆栈。</span><span class="sxs-lookup"><span data-stu-id="91afd-160">The horizontal axis is time and vertical axis is the call stack.</span></span>  <span data-ttu-id="91afd-161">堆栈从上到下组织。</span><span class="sxs-lookup"><span data-stu-id="91afd-161">The stacks are organized top-down.</span></span>  <span data-ttu-id="91afd-162">因此，顶部的 函数调用它下面的函数，等等。</span><span class="sxs-lookup"><span data-stu-id="91afd-162">So, the function on top called the one below it, and so on.</span></span>  |  

<span data-ttu-id="91afd-163">函数随机着色。</span><span class="sxs-lookup"><span data-stu-id="91afd-163">Functions are colored randomly.</span></span>  <span data-ttu-id="91afd-164">与其他面板中使用的颜色没有任何关联。</span><span class="sxs-lookup"><span data-stu-id="91afd-164">There is no correlation to the colors used in the other panels.</span></span>  <span data-ttu-id="91afd-165">但是，函数在调用中始终使用相同的颜色，以便你可以观察每个运行时中的模式。</span><span class="sxs-lookup"><span data-stu-id="91afd-165">However, functions are always colored the same across invocations so that you may observe patterns in each runtime.</span></span>  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-highlighted.msft.png" alt-text="批注的柱形图" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-highlighted.msft.png":::
   <span data-ttu-id="91afd-167">批注的柱形图</span><span class="sxs-lookup"><span data-stu-id="91afd-167">Annotated flame chart</span></span>  
:::image-end:::  

<span data-ttu-id="91afd-168">高调用堆栈不一定重要，它只是意味着调用了许多函数。</span><span class="sxs-lookup"><span data-stu-id="91afd-168">A tall call stack is not necessarily significant, it just means that a lot of functions were called.</span></span>  <span data-ttu-id="91afd-169">但宽栏意味着函数需要很长时间才能完成。</span><span class="sxs-lookup"><span data-stu-id="91afd-169">But a wide bar means that a function took a long time to complete.</span></span>  <span data-ttu-id="91afd-170">这些是优化的候选项。</span><span class="sxs-lookup"><span data-stu-id="91afd-170">These are candidates for optimization.</span></span>  

### <a name="zoom-in-on-specific-parts-of-recording"></a><span data-ttu-id="91afd-171">放大录制的特定部分</span><span class="sxs-lookup"><span data-stu-id="91afd-171">Zoom in on specific parts of recording</span></span>  

<span data-ttu-id="91afd-172">在概述中选择、按住和拖动鼠标，以放大调用堆栈的特定部分。</span><span class="sxs-lookup"><span data-stu-id="91afd-172">Choose, hold, and drag your mouse left and right across the overview to zoom in on particular parts of the call stack.</span></span>  <span data-ttu-id="91afd-173">缩放后，调用堆栈自动显示所选录制的部分。</span><span class="sxs-lookup"><span data-stu-id="91afd-173">After you zoom, the call stack automatically displays the portion of the recording that you selected.</span></span>  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-zoomed.msft.png" alt-text="图表已缩放" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-zoomed.msft.png":::
   <span data-ttu-id="91afd-175">图表已缩放</span><span class="sxs-lookup"><span data-stu-id="91afd-175">Chart zoomed</span></span>  
:::image-end:::  

### <a name="view-function-details"></a><span data-ttu-id="91afd-176">查看函数详细信息</span><span class="sxs-lookup"><span data-stu-id="91afd-176">View function details</span></span>  

<span data-ttu-id="91afd-177">选择一个函数以查看"源"工具 **中** 的定义。</span><span class="sxs-lookup"><span data-stu-id="91afd-177">Choose a function to view the definition in the **Sources** tool.</span></span>  

<span data-ttu-id="91afd-178">将鼠标悬停在函数上可显示名称和计时数据。</span><span class="sxs-lookup"><span data-stu-id="91afd-178">Hover on a function to display the name and timing data.</span></span>  <span data-ttu-id="91afd-179">提供了以下信息。</span><span class="sxs-lookup"><span data-stu-id="91afd-179">The following information is provided.</span></span>  

| <span data-ttu-id="91afd-180">详细信息</span><span class="sxs-lookup"><span data-stu-id="91afd-180">Detail</span></span> | <span data-ttu-id="91afd-181">描述</span><span class="sxs-lookup"><span data-stu-id="91afd-181">Description</span></span> |  
|:--- |:--- |  
| **<span data-ttu-id="91afd-182">名称</span><span class="sxs-lookup"><span data-stu-id="91afd-182">Name</span></span>** | <span data-ttu-id="91afd-183">函数的名称。</span><span class="sxs-lookup"><span data-stu-id="91afd-183">The name of the function.</span></span>  |  
| **<span data-ttu-id="91afd-184">自大小</span><span class="sxs-lookup"><span data-stu-id="91afd-184">Self size</span></span>** | <span data-ttu-id="91afd-185">函数的当前调用的大小，仅包括函数中的语句。</span><span class="sxs-lookup"><span data-stu-id="91afd-185">The size of the current invocation of the function, including only the statements in the function.</span></span>  |  
| **<span data-ttu-id="91afd-186">总大小</span><span class="sxs-lookup"><span data-stu-id="91afd-186">Total size</span></span>** | <span data-ttu-id="91afd-187">此函数的当前调用及其调用的任何函数的大小。</span><span class="sxs-lookup"><span data-stu-id="91afd-187">The size of the current invocation of this function and any functions that it called.</span></span>  |  
| **<span data-ttu-id="91afd-188">URL</span><span class="sxs-lookup"><span data-stu-id="91afd-188">URL</span></span>** | <span data-ttu-id="91afd-189">函数定义的位置，其形式为 ，其中 是定义函数的文件的名称， `base.js:261` `base.js` `261` 也是定义的行号。</span><span class="sxs-lookup"><span data-stu-id="91afd-189">The location of the function definition in the form of `base.js:261` where `base.js` is the name of the file where the function is defined and `261` is the line number of the definition.</span></span>  |  
<!--*   **Aggregated self time**.  Aggregate time for all invocations of the function across the recording, not including functions called by this function.  -->  
<!--*   **Aggregated total time**.  Aggregate total time for all invocations of the function, including functions called by this function.  -->  
<!--*   **Not optimized**.  If the profiler has detected a potential optimization for the function it lists it here.  -->  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-hover.msft.png" alt-text="在图表中查看函数详细信息" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-hover.msft.png":::
   <span data-ttu-id="91afd-191">在图表中查看函数详细信息</span><span class="sxs-lookup"><span data-stu-id="91afd-191">View functions details in chart</span></span>  
:::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="91afd-192">联系 Microsoft Edge 开发工具团队</span><span class="sxs-lookup"><span data-stu-id="91afd-192">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsConsoleUtilities]: ../console/utilities.md "控制台实用程序 API 参考|Microsoft Docs"  
[DevtoolsConsoleUtilitiesProfile]: ../console/utilities.md#profile "配置文件 - 控制台实用程序 API 参考|Microsoft Docs"  
[DevtoolsConsoleUtilitiesProfileEnd]: ../console/utilities.md#profileend "profileEnd - 控制台实用程序 API |Microsoft Docs"  

> [!NOTE]
> <span data-ttu-id="91afd-196">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="91afd-196">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="91afd-197">原始页面位于此处，[](https://developers.google.com/web/tools/chrome-devtools/rendering-tools/js-execution)由位于此处的一位用户创作，作者为：一名技术撰稿人： (技术撰稿人、Chrome DevTools \& Lighthouse\) 和[Meggin Kearney][MegginKearney] \ (Tech Writer\) 。 [][KayceBasques]</span><span class="sxs-lookup"><span data-stu-id="91afd-197">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/rendering-tools/js-execution) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\) and [Meggin Kearney][MegginKearney] \(Tech Writer\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="91afd-199">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="91afd-199">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
