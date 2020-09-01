---
title: 加速 JavaScript 运行时
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 2f05ef2911c855df39d60fa732ff5f784ab49473
ms.sourcegitcommit: 1251c555c6b4db8ef8187ed94d8832fdb89d03b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2020
ms.locfileid: "10984845"
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





# <span data-ttu-id="225b9-103">加快 JavaScript 运行时</span><span class="sxs-lookup"><span data-stu-id="225b9-103">Speed up JavaScript runtime</span></span>   




<span data-ttu-id="225b9-104">使用 " **内存** " 面板识别昂贵的功能。</span><span class="sxs-lookup"><span data-stu-id="225b9-104">Identify expensive functions using the **Memory** panel.</span></span>  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-heavy-bottom-up.msft.png" alt-text="采样配置文件" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-heavy-bottom-up.msft.png":::
   <span data-ttu-id="225b9-106">采样配置文件</span><span class="sxs-lookup"><span data-stu-id="225b9-106">Sampling Profiles</span></span>  
:::image-end:::  

### <span data-ttu-id="225b9-107">摘要</span><span class="sxs-lookup"><span data-stu-id="225b9-107">Summary</span></span>  

*   <span data-ttu-id="225b9-108">准确记录所调用的函数和 **内存面板中的分配** 采样所需的内存量。</span><span class="sxs-lookup"><span data-stu-id="225b9-108">Record exactly which functions were called and how much memory each requires with Allocation Sampling in the **Memory** panel.</span></span>  
*   <span data-ttu-id="225b9-109">将配置文件可视化为火焰图表。</span><span class="sxs-lookup"><span data-stu-id="225b9-109">Visualize your profiles as a flame chart.</span></span>  
    
## <span data-ttu-id="225b9-110">录制采样配置文件</span><span class="sxs-lookup"><span data-stu-id="225b9-110">Record a Sampling Profile</span></span>  

<span data-ttu-id="225b9-111">如果注意到 jank 在 JavaScript 中，请收集采样档案。</span><span class="sxs-lookup"><span data-stu-id="225b9-111">If you notice jank in your JavaScript, collect a Sampling Profile.</span></span>  <span data-ttu-id="225b9-112">采样配置文件显示你的页面中的函数所用的运行时间。</span><span class="sxs-lookup"><span data-stu-id="225b9-112">Sampling Profiles show where running time is spent on functions in your page.</span></span>  

1.  <span data-ttu-id="225b9-113">转到 DevTools 的 " **内存** " 面板。</span><span class="sxs-lookup"><span data-stu-id="225b9-113">Go to the **Memory** panel of DevTools.</span></span>  
1.  <span data-ttu-id="225b9-114">选择 " **分配采样** " 单选按钮。</span><span class="sxs-lookup"><span data-stu-id="225b9-114">Select the **Allocation sampling** radio button.</span></span>  
1.  <span data-ttu-id="225b9-115">选择**开始**。</span><span class="sxs-lookup"><span data-stu-id="225b9-115">Select **Start**.</span></span>  
1.  <span data-ttu-id="225b9-116">根据你尝试分析的内容，你可以重新加载页面、与页面交互或仅让页面运行。</span><span class="sxs-lookup"><span data-stu-id="225b9-116">Depending on what you are trying to analyze, you may either reload the page, interact with the page, or just let the page run.</span></span>  
1.  <span data-ttu-id="225b9-117">完成后选择 " **停止** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="225b9-117">Select the **Stop** button when you are finished.</span></span>  
    
> [!NOTE]
> <span data-ttu-id="225b9-118">您也可以使用 [控制台实用工具 API][DevtoolsConsoleUtilities] 从命令行记录和分组配置文件。</span><span class="sxs-lookup"><span data-stu-id="225b9-118">You may also use the [Console Utilities API][DevtoolsConsoleUtilities] to record and group profiles from the command line.</span></span>  

## <span data-ttu-id="225b9-119">查看采样配置文件</span><span class="sxs-lookup"><span data-stu-id="225b9-119">View Sampling Profile</span></span>  

<span data-ttu-id="225b9-120">完成录制后，DevTools 会自动在 "**采样配置文件**" 下填入来自录制的数据的**内存**面板。</span><span class="sxs-lookup"><span data-stu-id="225b9-120">When you finish recording, DevTools automatically populates the **Memory** panel under **SAMPLING PROFILES** with the data from your recording.</span></span>  

<span data-ttu-id="225b9-121">默认视图为 " \*\*粗" ("自下而上" ) \*\*。</span><span class="sxs-lookup"><span data-stu-id="225b9-121">The default view is **Heavy \(Bottom Up\)**.</span></span>  <span data-ttu-id="225b9-122">此视图使你能够查看哪些函数对性能有最大影响，并检查这些函数的调用路径。</span><span class="sxs-lookup"><span data-stu-id="225b9-122">This view enables you to see which functions had the most impact on performance and examine the calling paths to those functions.</span></span>  

### <span data-ttu-id="225b9-123">更改排序顺序</span><span class="sxs-lookup"><span data-stu-id="225b9-123">Change sort order</span></span>   

<span data-ttu-id="225b9-124">若要更改排序顺序，请选择 " **焦点选定函数** \ (![ 焦点选定函数 \ ) 图标" 旁边的下拉菜单 ][ImageFocusIcon] ，然后选择下列选项之一。</span><span class="sxs-lookup"><span data-stu-id="225b9-124">To change the sorting order, select the dropdown menu next to the **focus selected function** \(![focus selected function][ImageFocusIcon]\) icon and then choose one of the following options.</span></span>

<span data-ttu-id="225b9-125">**图表**。</span><span class="sxs-lookup"><span data-stu-id="225b9-125">**Chart**.</span></span>  <span data-ttu-id="225b9-126">显示录制的按时间顺序的图表。</span><span class="sxs-lookup"><span data-stu-id="225b9-126">Displays a chronological chart of the recording.</span></span>  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart.msft.png" alt-text="火焰图" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart.msft.png":::
   <span data-ttu-id="225b9-128">火焰图</span><span class="sxs-lookup"><span data-stu-id="225b9-128">Flame chart</span></span>  
:::image-end:::  

<span data-ttu-id="225b9-129">\*\*粗 \ (下 ) \*\*。</span><span class="sxs-lookup"><span data-stu-id="225b9-129">**Heavy \(Bottom Up\)**.</span></span>  <span data-ttu-id="225b9-130">通过对性能的影响列出函数，并使你能够检查这些函数的调用路径。</span><span class="sxs-lookup"><span data-stu-id="225b9-130">Lists functions by impact on performance and enables you to examine the calling paths to the functions.</span></span>  <span data-ttu-id="225b9-131">这是默认视图。</span><span class="sxs-lookup"><span data-stu-id="225b9-131">This is the default view.</span></span>  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-heavy-bottom-up.msft.png" alt-text="粗图" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-heavy-bottom-up.msft.png":::
   <span data-ttu-id="225b9-133">粗图</span><span class="sxs-lookup"><span data-stu-id="225b9-133">Heavy chart</span></span>  
:::image-end:::  

<span data-ttu-id="225b9-134">\*\*树 \ (页首按 ) \*\*。</span><span class="sxs-lookup"><span data-stu-id="225b9-134">**Tree \(Top Down\)**.</span></span>  <span data-ttu-id="225b9-135">显示从调用堆栈顶部开始的调用结构的整体图片。</span><span class="sxs-lookup"><span data-stu-id="225b9-135">Shows an overall picture of the calling structure, starting at the top of the call stack.</span></span>  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-tree-top-down.msft.png" alt-text="树形图" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-tree-top-down.msft.png":::
   <span data-ttu-id="225b9-137">树形图</span><span class="sxs-lookup"><span data-stu-id="225b9-137">Tree chart</span></span>  
:::image-end:::  

### <span data-ttu-id="225b9-138">排除函数</span><span class="sxs-lookup"><span data-stu-id="225b9-138">Exclude functions</span></span>   

<span data-ttu-id="225b9-139">若要从采样配置文件中排除某个函数，请选择该函数以将其选中，然后选择 " **排除所选函数** \" (" ![ 排除所选函数 ][ImageExcludeIcon] \ ) " 图标。</span><span class="sxs-lookup"><span data-stu-id="225b9-139">To exclude a function from your Sampling Profile, select it to select it and then select the **exclude selected function** \(![exclude selected function][ImageExcludeIcon]\) icon.</span></span>  <span data-ttu-id="225b9-140">已排除的函数 \ (子 ) 的请求函数 \ (parent ) 已分配分配给已排除函数 \ (子 ) 的分配内存。</span><span class="sxs-lookup"><span data-stu-id="225b9-140">The requesting function \(parent\) of the excluded function \(child\) is charged with the allocated memory assigned to the excluded function \(child\).</span></span>  

<span data-ttu-id="225b9-141">选择 " **还原所有函数** \ (![ 还原所有函数 ][ImageRestoreIcon] \ ) " 图标将所有已排除的函数还原到录制中。</span><span class="sxs-lookup"><span data-stu-id="225b9-141">Select the **restore all functions** \(![restore all functions][ImageRestoreIcon]\) icon to restore all excluded functions back into the recording.</span></span>  

## <span data-ttu-id="225b9-142">以图表形式查看采样配置文件</span><span class="sxs-lookup"><span data-stu-id="225b9-142">View Sampling Profile as Chart</span></span>   

<span data-ttu-id="225b9-143">"图表" 视图提供了一段时间内采样配置文件的可视化表示形式。</span><span class="sxs-lookup"><span data-stu-id="225b9-143">The Chart view provides a visual representation of the Sampling Profile over time.</span></span>  

<span data-ttu-id="225b9-144">[录制采样配置文件](#record-a-sampling-profile)后，通过将[排序顺序更改](#change-sort-order)为**图表**，可将录制查看为火焰图表。</span><span class="sxs-lookup"><span data-stu-id="225b9-144">After you [record a Sampling Profile](#record-a-sampling-profile), view the recording as a flame chart by [changing the sort order](#change-sort-order) to **Chart**.</span></span>  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart.msft.png" alt-text="火焰图表视图" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart.msft.png":::
   <span data-ttu-id="225b9-146">火焰图表视图</span><span class="sxs-lookup"><span data-stu-id="225b9-146">Flame chart view</span></span>  
:::image-end:::  

<span data-ttu-id="225b9-147">火焰图分成两部分。</span><span class="sxs-lookup"><span data-stu-id="225b9-147">The flame chart is split into two parts.</span></span>  

| | <span data-ttu-id="225b9-148">部件</span><span class="sxs-lookup"><span data-stu-id="225b9-148">Part</span></span> | <span data-ttu-id="225b9-149">描述</span><span class="sxs-lookup"><span data-stu-id="225b9-149">Description</span></span> |  
| --- |:--- |:--- |  
| <span data-ttu-id="225b9-150">raid-1</span><span class="sxs-lookup"><span data-stu-id="225b9-150">1</span></span> | <span data-ttu-id="225b9-151">概述</span><span class="sxs-lookup"><span data-stu-id="225b9-151">Overview</span></span> | <span data-ttu-id="225b9-152">整个录制的鸟瞰视图。</span><span class="sxs-lookup"><span data-stu-id="225b9-152">A birds-eye view of the entire recording.</span></span>  <span data-ttu-id="225b9-153">条形图的高度对应于调用堆栈的深度。</span><span class="sxs-lookup"><span data-stu-id="225b9-153">The height of the bars correspond to the depth of the call stack.</span></span>  <span data-ttu-id="225b9-154">因此，栏越高，调用堆栈越深。</span><span class="sxs-lookup"><span data-stu-id="225b9-154">So, the higher the bar, the deeper the call stack.</span></span>  |  
| <span data-ttu-id="225b9-155">ppls-2</span><span class="sxs-lookup"><span data-stu-id="225b9-155">2</span></span> | <span data-ttu-id="225b9-156">调用堆栈</span><span class="sxs-lookup"><span data-stu-id="225b9-156">Call Stacks</span></span> | <span data-ttu-id="225b9-157">这是在录制期间调用的函数的深入视图。</span><span class="sxs-lookup"><span data-stu-id="225b9-157">This is an in-depth view of the functions that were called during the recording.</span></span>  <span data-ttu-id="225b9-158">水平轴为时间，垂直轴为调用堆栈。</span><span class="sxs-lookup"><span data-stu-id="225b9-158">The horizontal axis is time and vertical axis is the call stack.</span></span>  <span data-ttu-id="225b9-159">堆叠按从上到下排列。</span><span class="sxs-lookup"><span data-stu-id="225b9-159">The stacks are organized top-down.</span></span>  <span data-ttu-id="225b9-160">因此，函数顶部称为该函数，依此类推。</span><span class="sxs-lookup"><span data-stu-id="225b9-160">So, the function on top called the one below it, and so on.</span></span>  |  

<span data-ttu-id="225b9-161">函数会随机着色。</span><span class="sxs-lookup"><span data-stu-id="225b9-161">Functions are colored randomly.</span></span>  <span data-ttu-id="225b9-162">与其他面板中使用的颜色没有关联。</span><span class="sxs-lookup"><span data-stu-id="225b9-162">There is no correlation to the colors used in the other panels.</span></span>  <span data-ttu-id="225b9-163">但是，函数在调用中始终具有相同的颜色，以便你可以在每个运行时中查看模式。</span><span class="sxs-lookup"><span data-stu-id="225b9-163">However, functions are always colored the same across invocations so that you are able to see patterns in each runtime.</span></span>  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-highlighted.msft.png" alt-text="已标注的火焰图表" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-highlighted.msft.png":::
   <span data-ttu-id="225b9-165">已标注的火焰图表</span><span class="sxs-lookup"><span data-stu-id="225b9-165">Annotated flame chart</span></span>  
:::image-end:::  

<span data-ttu-id="225b9-166">高调用堆栈不一定很重要，它只意味着调用了大量函数。</span><span class="sxs-lookup"><span data-stu-id="225b9-166">A tall call stack is not necessarily significant, it just means that a lot of functions were called.</span></span>  <span data-ttu-id="225b9-167">但宽条表示某个函数需要很长时间才能完成。</span><span class="sxs-lookup"><span data-stu-id="225b9-167">But a wide bar means that a function took a long time to complete.</span></span>  <span data-ttu-id="225b9-168">这些是优化的候选项。</span><span class="sxs-lookup"><span data-stu-id="225b9-168">These are candidates for optimization.</span></span>  

### <span data-ttu-id="225b9-169">放大录制的特定部分</span><span class="sxs-lookup"><span data-stu-id="225b9-169">Zoom in on specific parts of recording</span></span>   

<span data-ttu-id="225b9-170">选择、按住，然后在概述中向左和向右拖动鼠标，以放大调用堆栈的特定部分。</span><span class="sxs-lookup"><span data-stu-id="225b9-170">Select, hold, and drag your mouse left and right across the overview to zoom in on particular parts of the call stack.</span></span>  <span data-ttu-id="225b9-171">缩放后，调用堆栈自动显示所选录制部分。</span><span class="sxs-lookup"><span data-stu-id="225b9-171">After you zoom, the call stack automatically displays the portion of the recording that you selected.</span></span>  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-zoomed.msft.png" alt-text="缩放图表" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-zoomed.msft.png":::
   <span data-ttu-id="225b9-173">缩放图表</span><span class="sxs-lookup"><span data-stu-id="225b9-173">Chart zoomed</span></span>  
:::image-end:::  

### <span data-ttu-id="225b9-174">查看函数详细信息</span><span class="sxs-lookup"><span data-stu-id="225b9-174">View function details</span></span>   

<span data-ttu-id="225b9-175">选择一个函数以在 " **源** " 面板中查看定义。</span><span class="sxs-lookup"><span data-stu-id="225b9-175">Select on a function to view the definition in the **Sources** panel.</span></span>  

<span data-ttu-id="225b9-176">将鼠标悬停在函数上以显示名称和计时数据。</span><span class="sxs-lookup"><span data-stu-id="225b9-176">Hover over a function to display the name and timing data.</span></span>  <span data-ttu-id="225b9-177">提供以下信息。</span><span class="sxs-lookup"><span data-stu-id="225b9-177">The following information is provided.</span></span>  

| <span data-ttu-id="225b9-178">资料</span><span class="sxs-lookup"><span data-stu-id="225b9-178">Detail</span></span> | <span data-ttu-id="225b9-179">描述</span><span class="sxs-lookup"><span data-stu-id="225b9-179">Description</span></span> |  
|:--- |:--- |  
| **<span data-ttu-id="225b9-180">名称</span><span class="sxs-lookup"><span data-stu-id="225b9-180">Name</span></span>** | <span data-ttu-id="225b9-181">函数的名称。</span><span class="sxs-lookup"><span data-stu-id="225b9-181">The name of the function.</span></span>  |  
| **<span data-ttu-id="225b9-182">自大小</span><span class="sxs-lookup"><span data-stu-id="225b9-182">Self size</span></span>** | <span data-ttu-id="225b9-183">函数的当前调用的大小，包括函数中的语句。</span><span class="sxs-lookup"><span data-stu-id="225b9-183">The size of the current invocation of the function, including only the statements in the function.</span></span>  |  
| **<span data-ttu-id="225b9-184">总大小</span><span class="sxs-lookup"><span data-stu-id="225b9-184">Total size</span></span>** | <span data-ttu-id="225b9-185">此函数及其调用的任何函数的当前调用的大小。</span><span class="sxs-lookup"><span data-stu-id="225b9-185">The size of the current invocation of this function and any functions that it called.</span></span>  |  
| **<span data-ttu-id="225b9-186">URL</span><span class="sxs-lookup"><span data-stu-id="225b9-186">URL</span></span>** | <span data-ttu-id="225b9-187">函数定义在 where 的形式的位置 `base.js:261` `base.js` 是定义函数的文件的名称，并且 `261` 是定义的行号。</span><span class="sxs-lookup"><span data-stu-id="225b9-187">The location of the function definition in the form of `base.js:261` where `base.js` is the name of the file where the function is defined and `261` is the line number of the definition.</span></span>  |  
<!--*   **Aggregated self time**.  Aggregate time for all invocations of the function across the recording, not including functions called by this function.  -->  
<!--*   **Aggregated total time**.  Aggregate total time for all invocations of the function, including functions called by this function.  -->  
<!--*   **Not optimized**.  If the profiler has detected a potential optimization for the function it lists it here.  -->  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-hover.msft.png" alt-text="查看图表中的函数详细信息" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-hover.msft.png":::
   <span data-ttu-id="225b9-189">查看图表中的函数详细信息</span><span class="sxs-lookup"><span data-stu-id="225b9-189">Viewing functions details in chart</span></span>  
:::image-end:::  

<!--  
## Feedback   


-->  

<!-- image links -->  

[ImageExcludeIcon]: ../media/exclude-icon.msft.png  
[ImageFocusIcon]: ../media/focus-icon.msft.png  
[ImageRestoreIcon]: ../media/restore-icon.msft.png  

<!-- links -->  

[DevtoolsConsoleUtilities]: ../console/utilities.md "控制台实用工具 API 参考 |Microsoft 文档"  
[DevtoolsConsoleUtilitiesProfile]: ../console/utilities.md#profile "配置文件-控制台实用工具 API 参考 |Microsoft 文档"  
[DevtoolsConsoleUtilitiesProfileEnd]: ../console/utilities.md#profileend "profileEnd-控制台实用工具 API 参考 |Microsoft 文档"  

> [!NOTE]
> <span data-ttu-id="225b9-193">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="225b9-193">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="225b9-194">原始页面可在 [此处](https://developers.google.com/web/tools/chrome-devtools/rendering-tools/js-execution) 找到，并由 [Kayce Basques][KayceBasques] (技术作者、Chrome DevTools \ & Lighthouse \ ) 和 [Meggin Kearney][MegginKearney] \ (技术作者 \ ) 创作。</span><span class="sxs-lookup"><span data-stu-id="225b9-194">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/rendering-tools/js-execution) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\) and [Meggin Kearney][MegginKearney] \(Tech Writer\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="225b9-196">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="225b9-196">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
