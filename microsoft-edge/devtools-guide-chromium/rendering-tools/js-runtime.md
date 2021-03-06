---
description: 使用 Microsoft Edge DevTools 内存面板识别成本高昂的函数。
title: 加速 JavaScript 运行时
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: 682001ae8d265b342e5d6e0725f9f8ac4e298cf8
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11397599"
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

# <a name="speed-up-javascript-runtime"></a><span data-ttu-id="3d418-104">加速 JavaScript 运行时</span><span class="sxs-lookup"><span data-stu-id="3d418-104">Speed up JavaScript runtime</span></span>  

<span data-ttu-id="3d418-105">使用"内存"面板标识 **成本高昂的** 函数。</span><span class="sxs-lookup"><span data-stu-id="3d418-105">Identify expensive functions using the **Memory** panel.</span></span>  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-heavy-bottom-up.msft.png" alt-text="示例配置文件" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-heavy-bottom-up.msft.png":::
   <span data-ttu-id="3d418-107">示例配置文件</span><span class="sxs-lookup"><span data-stu-id="3d418-107">Sample Profiles</span></span>  
:::image-end:::  

### <a name="summary"></a><span data-ttu-id="3d418-108">摘要</span><span class="sxs-lookup"><span data-stu-id="3d418-108">Summary</span></span>  

*   <span data-ttu-id="3d418-109">使用"内存"面板中的"分配采样"准确记录调用的函数以及每个函数 **所需的内存** 量。</span><span class="sxs-lookup"><span data-stu-id="3d418-109">Record exactly which functions were called and how much memory each requires with Allocation Sampling in the **Memory** panel.</span></span>  
*   <span data-ttu-id="3d418-110">将你的配置文件可视化为一个图表。</span><span class="sxs-lookup"><span data-stu-id="3d418-110">Visualize your profiles as a flame chart.</span></span>  
    
## <a name="record-a-sampling-profile"></a><span data-ttu-id="3d418-111">记录采样配置文件</span><span class="sxs-lookup"><span data-stu-id="3d418-111">Record a Sampling Profile</span></span>  

<span data-ttu-id="3d418-112">如果你注意到 JavaScript 中的 jank，请收集一个采样配置文件。</span><span class="sxs-lookup"><span data-stu-id="3d418-112">If you notice jank in your JavaScript, collect a Sampling Profile.</span></span>  <span data-ttu-id="3d418-113">采样配置文件显示运行时间在页面中函数的花费位置。</span><span class="sxs-lookup"><span data-stu-id="3d418-113">Sampling Profiles show where running time is spent on functions in your page.</span></span>  

1.  <span data-ttu-id="3d418-114">导航 **到** DevTools 的内存面板。</span><span class="sxs-lookup"><span data-stu-id="3d418-114">Navigate to the **Memory** panel of DevTools.</span></span>  
1.  <span data-ttu-id="3d418-115">选择 **"分配采样单** 选"按钮。</span><span class="sxs-lookup"><span data-stu-id="3d418-115">Choose the **Allocation sampling** radio button.</span></span>  
1.  <span data-ttu-id="3d418-116">选择 **"开始"。**</span><span class="sxs-lookup"><span data-stu-id="3d418-116">Choose **Start**.</span></span>  
1.  <span data-ttu-id="3d418-117">根据您尝试分析的内容，您可以刷新页面、与页面交互或仅让页面运行。</span><span class="sxs-lookup"><span data-stu-id="3d418-117">Depending on what you are trying to analyze, you may either refresh the page, interact with the page, or just let the page run.</span></span>  
1.  <span data-ttu-id="3d418-118">完成后 **，** 选择"停止"按钮。</span><span class="sxs-lookup"><span data-stu-id="3d418-118">Choose the **Stop** button when you are finished.</span></span>  
    
> [!NOTE]
> <span data-ttu-id="3d418-119">您还可以使用控制台实用程序 [API][DevtoolsConsoleUtilities] 从命令行记录和分组配置文件。</span><span class="sxs-lookup"><span data-stu-id="3d418-119">You may also use the [Console Utilities API][DevtoolsConsoleUtilities] to record and group profiles from the command line.</span></span>  

## <a name="view-sampling-profile"></a><span data-ttu-id="3d418-120">查看采样配置文件</span><span class="sxs-lookup"><span data-stu-id="3d418-120">View Sampling Profile</span></span>  

<span data-ttu-id="3d418-121">完成录制后，DevTools 会自动使用录制数据\*\*\*\* 填充 **"采样配置文件**"下的"内存"面板。</span><span class="sxs-lookup"><span data-stu-id="3d418-121">When you finish recording, DevTools automatically populates the **Memory** panel under **SAMPLING PROFILES** with the data from your recording.</span></span>  

<span data-ttu-id="3d418-122">默认视图为 Heavy \*\*\ (Bottom Up\) 。 \*\*</span><span class="sxs-lookup"><span data-stu-id="3d418-122">The default view is **Heavy \(Bottom Up\)**.</span></span>  <span data-ttu-id="3d418-123">此视图允许你查看哪些函数对性能影响最大，并检查每个函数的请求路径。</span><span class="sxs-lookup"><span data-stu-id="3d418-123">This view allows you to review which functions had the most impact on performance and examine the requesting path for each function.</span></span>  

### <a name="change-sort-order"></a><span data-ttu-id="3d418-124">更改排序顺序</span><span class="sxs-lookup"><span data-stu-id="3d418-124">Change sort order</span></span>  

<span data-ttu-id="3d418-125">若要更改排序顺序，请选择焦点选定函数 **\ (** 焦点选定函数 \) 图标旁边的下拉菜单，然后选择下列 ![ ][ImageFocusIcon] 选项之一。</span><span class="sxs-lookup"><span data-stu-id="3d418-125">To change the sorting order, select the dropdown menu next to the **focus selected function** \(![focus selected function][ImageFocusIcon]\) icon and then choose one of the following options.</span></span>

<span data-ttu-id="3d418-126">**图表**。</span><span class="sxs-lookup"><span data-stu-id="3d418-126">**Chart**.</span></span>  <span data-ttu-id="3d418-127">显示记录的时间顺序图表。</span><span class="sxs-lookup"><span data-stu-id="3d418-127">Displays a chronological chart of the recording.</span></span>  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart.msft.png" alt-text="饼图" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart.msft.png":::
   <span data-ttu-id="3d418-129">饼图</span><span class="sxs-lookup"><span data-stu-id="3d418-129">Flame chart</span></span>  
:::image-end:::  

<span data-ttu-id="3d418-130">\*\*粗 \ (下向上\) \*\*。</span><span class="sxs-lookup"><span data-stu-id="3d418-130">**Heavy \(Bottom Up\)**.</span></span>  <span data-ttu-id="3d418-131">根据对性能的影响列出函数，并使您能够检查函数的调用路径。</span><span class="sxs-lookup"><span data-stu-id="3d418-131">Lists functions by impact on performance and enables you to examine the calling paths to the functions.</span></span>  <span data-ttu-id="3d418-132">这是默认视图。</span><span class="sxs-lookup"><span data-stu-id="3d418-132">This is the default view.</span></span>  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-heavy-bottom-up.msft.png" alt-text="粗图表" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-heavy-bottom-up.msft.png":::
   <span data-ttu-id="3d418-134">粗图表</span><span class="sxs-lookup"><span data-stu-id="3d418-134">Heavy chart</span></span>  
:::image-end:::  

<span data-ttu-id="3d418-135">\*\*树 \ (Top Down\) \*\*。</span><span class="sxs-lookup"><span data-stu-id="3d418-135">**Tree \(Top Down\)**.</span></span>  <span data-ttu-id="3d418-136">显示调用结构的整体图片，从调用堆栈的顶部开始。</span><span class="sxs-lookup"><span data-stu-id="3d418-136">Shows an overall picture of the calling structure, starting at the top of the call stack.</span></span>  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-tree-top-down.msft.png" alt-text="树形图" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-tree-top-down.msft.png":::
   <span data-ttu-id="3d418-138">树形图</span><span class="sxs-lookup"><span data-stu-id="3d418-138">Tree chart</span></span>  
:::image-end:::  

### <a name="exclude-functions"></a><span data-ttu-id="3d418-139">排除函数</span><span class="sxs-lookup"><span data-stu-id="3d418-139">Exclude functions</span></span>  

<span data-ttu-id="3d418-140">若要从采样配置文件中排除函数，请选择该函数，然后选择排除选定函数 **\ (** 排除所选函数 ![ ][ImageExcludeIcon] \) 按钮。</span><span class="sxs-lookup"><span data-stu-id="3d418-140">To exclude a function from your Sampling Profile, select it and then select the **exclude selected function** \(![exclude selected function][ImageExcludeIcon]\) button.</span></span>  <span data-ttu-id="3d418-141">已排除函数 \ (child\) 的请求函数 \ (child\) 由分配给排除函数 \ (child\) 的已分配内存收费。</span><span class="sxs-lookup"><span data-stu-id="3d418-141">The requesting function \(parent\) of the excluded function \(child\) is charged with the allocated memory assigned to the excluded function \(child\).</span></span>  

<span data-ttu-id="3d418-142">选择 **"还原所有函数** " (还原所有函数 \) 按钮，以将所有排除的函数 ![ ][ImageRestoreIcon] 还原回录制中。</span><span class="sxs-lookup"><span data-stu-id="3d418-142">Choose the **restore all functions** \(![restore all functions][ImageRestoreIcon]\) button to restore all excluded functions back into the recording.</span></span>  

## <a name="view-sampling-profile-as-chart"></a><span data-ttu-id="3d418-143">以图表模式查看采样配置文件</span><span class="sxs-lookup"><span data-stu-id="3d418-143">View Sampling Profile as Chart</span></span>  

<span data-ttu-id="3d418-144">"图表"视图提供一段时间的采样配置文件的直观表示形式。</span><span class="sxs-lookup"><span data-stu-id="3d418-144">The Chart view provides a visual representation of the Sampling Profile over time.</span></span>  

<span data-ttu-id="3d418-145">录制[采样配置文件后](#record-a-sampling-profile)，通过更改图表的排序顺序来查看记录作为[](#change-sort-order)一个饼**图**。</span><span class="sxs-lookup"><span data-stu-id="3d418-145">After you [record a Sampling Profile](#record-a-sampling-profile), view the recording as a flame chart by [changing the sort order](#change-sort-order) to **Chart**.</span></span>  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart.msft.png" alt-text="饼图视图" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart.msft.png":::
   <span data-ttu-id="3d418-147">饼图视图</span><span class="sxs-lookup"><span data-stu-id="3d418-147">Flame chart view</span></span>  
:::image-end:::  

<span data-ttu-id="3d418-148">柱形图分为两部分。</span><span class="sxs-lookup"><span data-stu-id="3d418-148">The flame chart is split into two parts.</span></span>  

| <span data-ttu-id="3d418-149">index</span><span class="sxs-lookup"><span data-stu-id="3d418-149">index</span></span> | <span data-ttu-id="3d418-150">部件</span><span class="sxs-lookup"><span data-stu-id="3d418-150">Part</span></span> | <span data-ttu-id="3d418-151">说明</span><span class="sxs-lookup"><span data-stu-id="3d418-151">Description</span></span> |  
| --- |:--- |:--- |  
| <span data-ttu-id="3d418-152">1</span><span class="sxs-lookup"><span data-stu-id="3d418-152">1</span></span> | <span data-ttu-id="3d418-153">概述</span><span class="sxs-lookup"><span data-stu-id="3d418-153">Overview</span></span> | <span data-ttu-id="3d418-154">整个录制的鸟瞰图。</span><span class="sxs-lookup"><span data-stu-id="3d418-154">A birds-eye view of the entire recording.</span></span>  <span data-ttu-id="3d418-155">栏的高度对应于调用堆栈的深度。</span><span class="sxs-lookup"><span data-stu-id="3d418-155">The height of the bars correspond to the depth of the call stack.</span></span>  <span data-ttu-id="3d418-156">因此，条形越高，调用堆栈越深。</span><span class="sxs-lookup"><span data-stu-id="3d418-156">So, the higher the bar, the deeper the call stack.</span></span>  |  
| <span data-ttu-id="3d418-157">2</span><span class="sxs-lookup"><span data-stu-id="3d418-157">2</span></span> | <span data-ttu-id="3d418-158">调用堆栈</span><span class="sxs-lookup"><span data-stu-id="3d418-158">Call Stacks</span></span> | <span data-ttu-id="3d418-159">这是在录制过程中调用的函数的深入视图。</span><span class="sxs-lookup"><span data-stu-id="3d418-159">This is an in-depth view of the functions that were called during the recording.</span></span>  <span data-ttu-id="3d418-160">水平轴为时间，垂直轴为调用堆栈。</span><span class="sxs-lookup"><span data-stu-id="3d418-160">The horizontal axis is time and vertical axis is the call stack.</span></span>  <span data-ttu-id="3d418-161">堆栈从上到下进行组织。</span><span class="sxs-lookup"><span data-stu-id="3d418-161">The stacks are organized top-down.</span></span>  <span data-ttu-id="3d418-162">因此，顶部的函数调用它下面的函数，等等。</span><span class="sxs-lookup"><span data-stu-id="3d418-162">So, the function on top called the one below it, and so on.</span></span>  |  

<span data-ttu-id="3d418-163">函数随机着色。</span><span class="sxs-lookup"><span data-stu-id="3d418-163">Functions are colored randomly.</span></span>  <span data-ttu-id="3d418-164">与其他面板中使用的颜色没有任何关联。</span><span class="sxs-lookup"><span data-stu-id="3d418-164">There is no correlation to the colors used in the other panels.</span></span>  <span data-ttu-id="3d418-165">但是，函数在调用中始终具有相同的颜色，以便你可以观察每个运行时中的模式。</span><span class="sxs-lookup"><span data-stu-id="3d418-165">However, functions are always colored the same across invocations so that you may observe patterns in each runtime.</span></span>  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-highlighted.msft.png" alt-text="批注的柱形图" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-highlighted.msft.png":::
   <span data-ttu-id="3d418-167">批注的柱形图</span><span class="sxs-lookup"><span data-stu-id="3d418-167">Annotated flame chart</span></span>  
:::image-end:::  

<span data-ttu-id="3d418-168">高调用堆栈不一定重要，它只是意味着调用了许多函数。</span><span class="sxs-lookup"><span data-stu-id="3d418-168">A tall call stack is not necessarily significant, it just means that a lot of functions were called.</span></span>  <span data-ttu-id="3d418-169">但宽条意味着函数需要很长时间才能完成。</span><span class="sxs-lookup"><span data-stu-id="3d418-169">But a wide bar means that a function took a long time to complete.</span></span>  <span data-ttu-id="3d418-170">这些是优化的候选项。</span><span class="sxs-lookup"><span data-stu-id="3d418-170">These are candidates for optimization.</span></span>  

### <a name="zoom-in-on-specific-parts-of-recording"></a><span data-ttu-id="3d418-171">放大录制的特定部分</span><span class="sxs-lookup"><span data-stu-id="3d418-171">Zoom in on specific parts of recording</span></span>  

<span data-ttu-id="3d418-172">在概述中选择、按住和拖动鼠标以放大调用堆栈的特定部分。</span><span class="sxs-lookup"><span data-stu-id="3d418-172">Choose, hold, and drag your mouse left and right across the overview to zoom in on particular parts of the call stack.</span></span>  <span data-ttu-id="3d418-173">缩放后，调用堆栈自动显示所选录制的部分。</span><span class="sxs-lookup"><span data-stu-id="3d418-173">After you zoom, the call stack automatically displays the portion of the recording that you selected.</span></span>  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-zoomed.msft.png" alt-text="图表缩放" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-zoomed.msft.png":::
   <span data-ttu-id="3d418-175">图表缩放</span><span class="sxs-lookup"><span data-stu-id="3d418-175">Chart zoomed</span></span>  
:::image-end:::  

### <a name="view-function-details"></a><span data-ttu-id="3d418-176">查看函数详细信息</span><span class="sxs-lookup"><span data-stu-id="3d418-176">View function details</span></span>  

<span data-ttu-id="3d418-177">选择一个函数以查看"源"面板 **中** 的定义。</span><span class="sxs-lookup"><span data-stu-id="3d418-177">Choose a function to view the definition in the **Sources** panel.</span></span>  

<span data-ttu-id="3d418-178">将鼠标悬停在函数上可显示名称和计时数据。</span><span class="sxs-lookup"><span data-stu-id="3d418-178">Hover on a function to display the name and timing data.</span></span>  <span data-ttu-id="3d418-179">提供了以下信息。</span><span class="sxs-lookup"><span data-stu-id="3d418-179">The following information is provided.</span></span>  

| <span data-ttu-id="3d418-180">详细信息</span><span class="sxs-lookup"><span data-stu-id="3d418-180">Detail</span></span> | <span data-ttu-id="3d418-181">说明</span><span class="sxs-lookup"><span data-stu-id="3d418-181">Description</span></span> |  
|:--- |:--- |  
| **<span data-ttu-id="3d418-182">名称</span><span class="sxs-lookup"><span data-stu-id="3d418-182">Name</span></span>** | <span data-ttu-id="3d418-183">函数的名称。</span><span class="sxs-lookup"><span data-stu-id="3d418-183">The name of the function.</span></span>  |  
| **<span data-ttu-id="3d418-184">自调整大小</span><span class="sxs-lookup"><span data-stu-id="3d418-184">Self size</span></span>** | <span data-ttu-id="3d418-185">函数的当前调用大小，仅包括函数中的语句。</span><span class="sxs-lookup"><span data-stu-id="3d418-185">The size of the current invocation of the function, including only the statements in the function.</span></span>  |  
| **<span data-ttu-id="3d418-186">总大小</span><span class="sxs-lookup"><span data-stu-id="3d418-186">Total size</span></span>** | <span data-ttu-id="3d418-187">此函数的当前调用及其调用的任何函数的大小。</span><span class="sxs-lookup"><span data-stu-id="3d418-187">The size of the current invocation of this function and any functions that it called.</span></span>  |  
| **<span data-ttu-id="3d418-188">URL</span><span class="sxs-lookup"><span data-stu-id="3d418-188">URL</span></span>** | <span data-ttu-id="3d418-189">函数定义的位置，其形式为定义函数的文件的名称，以及定义的行 `base.js:261` `base.js` `261` 号。</span><span class="sxs-lookup"><span data-stu-id="3d418-189">The location of the function definition in the form of `base.js:261` where `base.js` is the name of the file where the function is defined and `261` is the line number of the definition.</span></span>  |  
<!--*   **Aggregated self time**.  Aggregate time for all invocations of the function across the recording, not including functions called by this function.  -->  
<!--*   **Aggregated total time**.  Aggregate total time for all invocations of the function, including functions called by this function.  -->  
<!--*   **Not optimized**.  If the profiler has detected a potential optimization for the function it lists it here.  -->  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-hover.msft.png" alt-text="在图表中查看函数详细信息" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-hover.msft.png":::
   <span data-ttu-id="3d418-191">在图表中查看函数详细信息</span><span class="sxs-lookup"><span data-stu-id="3d418-191">View functions details in chart</span></span>  
:::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="3d418-192">联系 Microsoft Edge 开发工具团队</span><span class="sxs-lookup"><span data-stu-id="3d418-192">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageExcludeIcon]: ../media/exclude-icon.msft.png  
[ImageFocusIcon]: ../media/focus-icon.msft.png  
[ImageRestoreIcon]: ../media/restore-icon.msft.png  

<!-- links -->  

[DevtoolsConsoleUtilities]: ../console/utilities.md "控制台实用工具 API 参考|Microsoft Docs"  
[DevtoolsConsoleUtilitiesProfile]: ../console/utilities.md#profile "配置文件 - 控制台实用工具 API 参考|Microsoft Docs"  
[DevtoolsConsoleUtilitiesProfileEnd]: ../console/utilities.md#profileend "profileEnd - 控制台实用工具 API 参考|Microsoft Docs"  

> [!NOTE]
> <span data-ttu-id="3d418-196">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="3d418-196">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="3d418-197">原始页面位于此处，[](https://developers.google.com/web/tools/chrome-devtools/rendering-tools/js-execution)由[一位（][KayceBasques]该链接人）\ (Technical Writer、Chrome DevTools \& Lighthouse\) 和[Meggin Kearney][MegginKearney] \ (Tech Writer\) 创作。</span><span class="sxs-lookup"><span data-stu-id="3d418-197">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/rendering-tools/js-execution) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\) and [Meggin Kearney][MegginKearney] \(Tech Writer\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="3d418-199">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="3d418-199">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
