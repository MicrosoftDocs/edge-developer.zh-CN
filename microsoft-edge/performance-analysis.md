---
ms.assetid: 7a5f9fd0-90a9-43db-b271-178c06da5896
description: 使用 F12 开发人员工具分析网站的常规性能。
title: 性能分析
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/08/2017
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘、web 开发、html、css、javascript、开发人员
ms.openlocfilehash: 7bf71744298502c9edf8ee1262fceff5640bedf1
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564548"
---
# <span data-ttu-id="73fbd-104">性能分析</span><span class="sxs-lookup"><span data-stu-id="73fbd-104">Performance Analysis</span></span>

<span data-ttu-id="73fbd-105">如果你不熟悉性能，请查看[F12 DevTools 指南](./devtools-guide.md)。</span><span class="sxs-lookup"><span data-stu-id="73fbd-105">If you're new to performance, you should check out the [F12 DevTools guide](./devtools-guide.md).</span></span>
<span data-ttu-id="73fbd-106">可使用内置于 Microsoft Edge 的[F12 工具](./devtools-guide.md)分析网站的常规性能。</span><span class="sxs-lookup"><span data-stu-id="73fbd-106">The [F12 tools](./devtools-guide.md) built into Microsoft Edge can be used to analyze the general performance of a web site.</span></span> <span data-ttu-id="73fbd-107">它在浏览器中向[Windows 性能工具包](https://docs.microsoft.com/windows-hardware/test/wpt/index)提供类似（但更有限）的功能。</span><span class="sxs-lookup"><span data-stu-id="73fbd-107">It provides similar (but more limited) capabilities to the [Windows Performance Toolkit](https://docs.microsoft.com/windows-hardware/test/wpt/index) from right within the browser.</span></span>



<span data-ttu-id="73fbd-108">如果想要对浏览器性能进行更深入的分析，Microsoft Edge 团队将使用[Windows 性能工具包](https://docs.microsoft.com/windows-hardware/test/wpt/index)（WPT）。</span><span class="sxs-lookup"><span data-stu-id="73fbd-108">If you want a deeper analysis of browser performance, the Microsoft Edge team uses the [Windows Performance Toolkit](https://docs.microsoft.com/windows-hardware/test/wpt/index) (WPT).</span></span> <span data-ttu-id="73fbd-109">WPT 由 Windows 团队创建，用于执行深入的计划性能分析。</span><span class="sxs-lookup"><span data-stu-id="73fbd-109">WPT was created by the Windows team to conduct in-depth program performance analysis.</span></span> <span data-ttu-id="73fbd-110">它 straddles 网站 JavaScript 和 Microsoft Edge 本机代码之间的边界，允许在同一工具内查看二者。</span><span class="sxs-lookup"><span data-stu-id="73fbd-110">It straddles the boundaries between website JavaScript and Microsoft Edge native code, allowing both to be viewed within the same tool.</span></span> <span data-ttu-id="73fbd-111">WPT 可用于：</span><span class="sxs-lookup"><span data-stu-id="73fbd-111">WPT can be used to:</span></span>
 - <span data-ttu-id="73fbd-112">测量软件完成工作所用的 CPU 时间</span><span class="sxs-lookup"><span data-stu-id="73fbd-112">Measure CPU time taken for software to complete work</span></span>
 - <span data-ttu-id="73fbd-113">计算软件分配的内存</span><span class="sxs-lookup"><span data-stu-id="73fbd-113">Calculate the memory allocated by software</span></span>
 - <span data-ttu-id="73fbd-114">显示从远程服务器下载文件的详细信息</span><span class="sxs-lookup"><span data-stu-id="73fbd-114">Show the details of downloading files from remote servers</span></span>
 - <span data-ttu-id="73fbd-115">度量帧速率。</span><span class="sxs-lookup"><span data-stu-id="73fbd-115">Measure frame rate.</span></span>


<span data-ttu-id="73fbd-116">若要开始使用 Windows 性能工具包分析你的网站，你首先需要下载[Windows 10 评估和部署工具包（ADK）](https://developer.microsoft.com/windows/hardware/windows-assessment-deployment-kit)。</span><span class="sxs-lookup"><span data-stu-id="73fbd-116">To get started with using the Windows Performance Toolkit to analyze your website, you'll first need to download the [Windows 10 Assessment and Deployment Kit (ADK)](https://developer.microsoft.com/windows/hardware/windows-assessment-deployment-kit).</span></span> <span data-ttu-id="73fbd-117">在安装期间选择 " *Windows 性能工具包*" 选项：</span><span class="sxs-lookup"><span data-stu-id="73fbd-117">Select the *Windows Performance Toolkit* option during installation:</span></span>

![ADK 安装选项](./media/adk-installoptions.png)

<span data-ttu-id="73fbd-119">下面我们将介绍如何记录和分析性能跟踪。</span><span class="sxs-lookup"><span data-stu-id="73fbd-119">Here we'll cover how to record and analyze a performance trace.</span></span> <span data-ttu-id="73fbd-120">若要了解有关 Windows 性能工具包中包含的内容的详细信息，请查看完整的[WPT 文档](https://docs.microsoft.com/windows-hardware/test/wpt/index)。</span><span class="sxs-lookup"><span data-stu-id="73fbd-120">To learn more about what's included in the Windows Performance Toolkit, check out the full [WPT documentation](https://docs.microsoft.com/windows-hardware/test/wpt/index).</span></span>

## <span data-ttu-id="73fbd-121">录制跟踪</span><span class="sxs-lookup"><span data-stu-id="73fbd-121">Recording a trace</span></span>
<span data-ttu-id="73fbd-122">接下来，设置你的用户方案并准备使用 Windows 性能记录器收集跟踪。</span><span class="sxs-lookup"><span data-stu-id="73fbd-122">Next, set up your user scenario and prepare to gather a trace using Windows Performance Recorder.</span></span>
<span data-ttu-id="73fbd-123">下面介绍如何通过*Windows 性能记录器（WPR）* 分析 web 方案。</span><span class="sxs-lookup"><span data-stu-id="73fbd-123">Here's how to profile your web scenario with the *Windows Performance Recorder (WPR)*.</span></span>

### <span data-ttu-id="73fbd-124">1. 准备环境以收集性能跟踪</span><span class="sxs-lookup"><span data-stu-id="73fbd-124">1. Prepare your environment to gather a performance trace</span></span>
<span data-ttu-id="73fbd-125">尽可能多地关闭正在运行的程序，以避免即将录制的跟踪中的干扰。</span><span class="sxs-lookup"><span data-stu-id="73fbd-125">Shut down as many running programs as possible to avoid noise in the trace that you're about to record.</span></span> <span data-ttu-id="73fbd-126">理想情况下，运行的唯一软件将是 Windows 性能记录器（WPR）和浏览器。</span><span class="sxs-lookup"><span data-stu-id="73fbd-126">Ideally, the only running software will be Windows Performance Recorder (WPR) and the browser.</span></span>

### <span data-ttu-id="73fbd-127">2. 启动 Windows 性能记录器（WPR）并选择选项</span><span class="sxs-lookup"><span data-stu-id="73fbd-127">2. Launch Windows Performance Recorder (WPR) and select options</span></span>
<span data-ttu-id="73fbd-128">启动 Windows 性能记录器并确保展开**更多选项**切换。</span><span class="sxs-lookup"><span data-stu-id="73fbd-128">Launch the Windows Performance Recorder and ensure that **More options** toggle is expanded.</span></span> <span data-ttu-id="73fbd-129">选择 "*边缘浏览器*" 和 " *HTML 响应*方案" 分析复选框。</span><span class="sxs-lookup"><span data-stu-id="73fbd-129">Select the *Edge Browser* and *HTML Responsiveness* scenario analysis checkboxes.</span></span>

![Windows 性能记录选项](./media/wprui-options.png)

#### <span data-ttu-id="73fbd-131">用于收集跟踪的提示和技巧</span><span class="sxs-lookup"><span data-stu-id="73fbd-131">Tips and tricks for gathering traces</span></span>
- <span data-ttu-id="73fbd-132">尝试保持后台活动最小为绝对必需。</span><span class="sxs-lookup"><span data-stu-id="73fbd-132">Try to keep background activity to an absolute required minimum.</span></span> <span data-ttu-id="73fbd-133">后台进程可能会扭曲感知性能和实际性能特征，并影响结果。</span><span class="sxs-lookup"><span data-stu-id="73fbd-133">Background processes may skew both perceived performance and actual performance characteristics and affect the results.</span></span> <span data-ttu-id="73fbd-134">理想情况下，浏览器和 WPR 旁边没有其他运行的应用程序。</span><span class="sxs-lookup"><span data-stu-id="73fbd-134">Ideally there are no other running applications beside browser and WPR.</span></span>
- <span data-ttu-id="73fbd-135">确定你正在分析的方案，并尽量尽量使它们保持原子。</span><span class="sxs-lookup"><span data-stu-id="73fbd-135">Identify the scenarios you're analyzing and try to keep them as atomic as possible.</span></span> <span data-ttu-id="73fbd-136">例如，如果您的网站在加载页面、滚动和选择表格中的内容时出现性能问题，请将问题划分为三个方案：</span><span class="sxs-lookup"><span data-stu-id="73fbd-136">For example, if your site has performance problems when loading the page, scrolling, and selecting something in a table, separate the issues into three scenarios:</span></span>
  - <span data-ttu-id="73fbd-137">页面加载（从导航开始到页面加载完成）</span><span class="sxs-lookup"><span data-stu-id="73fbd-137">Page load (from start of navigation to page load complete)</span></span>
  - <span data-ttu-id="73fbd-138">滚动</span><span class="sxs-lookup"><span data-stu-id="73fbd-138">Scroll</span></span>
  - <span data-ttu-id="73fbd-139">选择表格中的内容</span><span class="sxs-lookup"><span data-stu-id="73fbd-139">Selecting something in the table</span></span>
- <span data-ttu-id="73fbd-140">如果方案涉及导航到网站，请考虑在 "关于" 部分中开始使用以下内容：空白。</span><span class="sxs-lookup"><span data-stu-id="73fbd-140">If a scenario involves navigating to a site, consider beginning the scenario at about:blank.</span></span> <span data-ttu-id="73fbd-141">起始于：空白将避免上一页的开销。</span><span class="sxs-lookup"><span data-stu-id="73fbd-141">Starting at about:blank will avoid the overhead of the previous page.</span></span> <span data-ttu-id="73fbd-142">如果它涉及离开网站，请导航到 "关于：空白" 以完成方案。</span><span class="sxs-lookup"><span data-stu-id="73fbd-142">If it involves navigating away from a site, navigate to about:blank to complete the scenario.</span></span> <span data-ttu-id="73fbd-143">这将使其他网站的噪音不在跟踪范围内，除非网站之间的特定交互是调查问题。</span><span class="sxs-lookup"><span data-stu-id="73fbd-143">This will keep the noise of other sites out of the trace unless the specific interaction between sites is the issue under investigation.</span></span>

### <span data-ttu-id="73fbd-144">3. 录制方案</span><span class="sxs-lookup"><span data-stu-id="73fbd-144">3. Record the scenario</span></span>
<span data-ttu-id="73fbd-145">单击 "**开始**" 开始录制。</span><span class="sxs-lookup"><span data-stu-id="73fbd-145">Click **Start** to begin recording.</span></span> <span data-ttu-id="73fbd-146">该工具将报告它所使用的缓冲区的大小，以帮助你预测生成的文件的大小。</span><span class="sxs-lookup"><span data-stu-id="73fbd-146">The tool will report the size of the buffer it is using to help you anticipate the size of the generated file.</span></span> <span data-ttu-id="73fbd-147">执行要测量的用户方案，然后单击 "**保存**" 以停止录制并保存跟踪。</span><span class="sxs-lookup"><span data-stu-id="73fbd-147">Perform the user scenario you want to measure, then click **Save** to stop the recording and save the trace.</span></span> <span data-ttu-id="73fbd-148">在完成方案后立即保存将有助于最大程度地减少跟踪文件的大小。</span><span class="sxs-lookup"><span data-stu-id="73fbd-148">Saving immediately after finishing your scenario will help minimize the size of the trace file.</span></span>

![Windows 性能记录开始](./media/wprui-recording.png)

<span data-ttu-id="73fbd-150">WPR 工具将指示你的跟踪信息已成功保存：</span><span class="sxs-lookup"><span data-stu-id="73fbd-150">The WPR tool will indicate that your trace information was saved successfully:</span></span>

![Windows 性能记录开始](./media/wprui-savecomplete.png)


## <span data-ttu-id="73fbd-152">分析跟踪</span><span class="sxs-lookup"><span data-stu-id="73fbd-152">Analyzing a trace</span></span>
<span data-ttu-id="73fbd-153">现在，你已收集了性能数据，你可以使用 Windows 性能分析器分析跟踪以查看可进行的优化。</span><span class="sxs-lookup"><span data-stu-id="73fbd-153">Now that you've gathered your performance data, you can analyze the trace using Windows Performance Analyzer to see what optimizations can be made.</span></span>
<span data-ttu-id="73fbd-154">下面介绍了如何分析 web 方案性能数据。</span><span class="sxs-lookup"><span data-stu-id="73fbd-154">Here's how to analyze your web scenario performance data.</span></span>

### <span data-ttu-id="73fbd-155">1. 打开 Windows 性能分析器（WPA）</span><span class="sxs-lookup"><span data-stu-id="73fbd-155">1. Open Windows Performance Analyzer (WPA)</span></span>
<span data-ttu-id="73fbd-156">启动 Windows 性能分析器并打开 `.etl` 要分析的文件（"**File**  >  **打开文件 ...**"）。</span><span class="sxs-lookup"><span data-stu-id="73fbd-156">Launch Windows Performance Analyzer and open the `.etl` file to be analyzed (**File** > **Open...**).</span></span>

### <span data-ttu-id="73fbd-157">2. 加载符号并应用*HTML 分析*配置文件</span><span class="sxs-lookup"><span data-stu-id="73fbd-157">2. Load symbols and apply the *HTML analysis* profile</span></span>

>[!WARNING]
> <span data-ttu-id="73fbd-158">首次加载符号将需要较大的下载，并且将在典型的 internet 连接上花费大量时间。</span><span class="sxs-lookup"><span data-stu-id="73fbd-158">Loading symbols for the first time will require a large download and will take a significant amount of time on a typical internet connection.</span></span>

<span data-ttu-id="73fbd-159">从菜单中选择 "**跟踪**  >  **加载符号**"，加载您的符号。</span><span class="sxs-lookup"><span data-stu-id="73fbd-159">Load your symbols by selecting **Trace** > **Load Symbols** from the menu.</span></span> <span data-ttu-id="73fbd-160">这些符号将缓存到磁盘，将来的跟踪将更快地加载符号。</span><span class="sxs-lookup"><span data-stu-id="73fbd-160">The symbols will be cached to disk and future traces will load symbols much faster.</span></span>

<span data-ttu-id="73fbd-161">通过限制加载到 Microsoft Edge 和 web 应用主机，可以更快地加载符号。</span><span class="sxs-lookup"><span data-stu-id="73fbd-161">You can load symbols significantly faster by restricting the loading to Microsoft Edge and the web apps host.</span></span> <span data-ttu-id="73fbd-162">选择 "**跟踪**"  >  **配置符号**，并将**加载设置**限制为 "仅" `MicrosoftEdgeCP.exe` 和 `WWAHost.exe` 。</span><span class="sxs-lookup"><span data-stu-id="73fbd-162">Select **Trace** > **Configure Symbols** and restrict the **Load Settings** to only `MicrosoftEdgeCP.exe` and `WWAHost.exe`.</span></span>

![符号限制](./media/wpa-symbolrestrictions.png)

<span data-ttu-id="73fbd-164">开始加载符号后，应用*Html 分析配置文件*（应用**配置**文件  >  **...**  > **浏览目录 ...**  > **HtmlResponsivenessAnalysis wpaProfile**）配置文件将加载几个图形和表以供分析。</span><span class="sxs-lookup"><span data-stu-id="73fbd-164">After symbols begin loading, apply the *Html Analysis Profile* (**Profiles** > **Apply...** > **Browse Catalog...** > **HtmlResponsivenessAnalysis.wpaProfile**) The profile will load several graphs and tables for your analysis.</span></span> <span data-ttu-id="73fbd-165">对于几乎所有网站调查，我们建议从该配置文件开始。</span><span class="sxs-lookup"><span data-stu-id="73fbd-165">For nearly all website investigations, we recommend starting with this profile.</span></span>

![大图片](./media/wpa-bigpicture.png)


#### <span data-ttu-id="73fbd-167">Html 响应分析配置文件</span><span class="sxs-lookup"><span data-stu-id="73fbd-167">The Html Responsiveness Analysis Profile</span></span>
<span data-ttu-id="73fbd-168">*Html 响应*分析配置文件提供四个选项卡：</span><span class="sxs-lookup"><span data-stu-id="73fbd-168">The *Html Responsiveness* analysis profile provides four tabs:</span></span>

<span data-ttu-id="73fbd-169">**大图片**-这有助于确认没有意外的 CPU 活动源，并且浏览器确实使用了所有可用的资源。</span><span class="sxs-lookup"><span data-stu-id="73fbd-169">**Big Picture** - This is useful for confirming that there are no unexpected sources of CPU activity and the browser is indeed using all available resources.</span></span> <span data-ttu-id="73fbd-170">检查你的 CPU 使用情况，并验证没有任何进程对 CPU 使用率（浏览器除外）进行重大贡献。</span><span class="sxs-lookup"><span data-stu-id="73fbd-170">Check your CPU usage and verify that no processes contribute significantly to CPU usage other than the browser.</span></span>

<span data-ttu-id="73fbd-171">**帧分析**-此部分用于基本分析。</span><span class="sxs-lookup"><span data-stu-id="73fbd-171">**Frame Analysis** - This section is used for basic analysis.</span></span> <span data-ttu-id="73fbd-172">*Cpu 使用情况（属性化）* 图形可快速浏览负责 CPU 使用率的子系统。</span><span class="sxs-lookup"><span data-stu-id="73fbd-172">The *CPU Usage (Attributed)* graph enables a quick glance for understanding of the subsystems responsible for CPU usage.</span></span> <span data-ttu-id="73fbd-173">分解*HTML UI 线程*上*CPU 使用率（取样）* 表中的示例有助于识别关键性能瓶颈。</span><span class="sxs-lookup"><span data-stu-id="73fbd-173">Breaking down the samples in the *CPU Usage (Sampled)* table on the *HTML UI Thread* is helpful for identifying critical performance bottlenecks.</span></span>

<span data-ttu-id="73fbd-174">**跟踪标记**-此部分显示来自浏览器（Microsoft Edge）的所有跟踪标记（包括*msWriteProfilerMark*），其中提供了测量代码的精确点。</span><span class="sxs-lookup"><span data-stu-id="73fbd-174">**Trace Markers** - This section shows all tracing markers coming from the browser (Microsoft Edge), including *msWriteProfilerMark*, which provides precise points for measuring code.</span></span> <span data-ttu-id="73fbd-175">若要查看*msWriteProfilerMark*跟踪，请向下滚动到 "*通用事件*" 图形，然后从下拉菜单中选择 " **HTML msWriteProfilerMark** "。</span><span class="sxs-lookup"><span data-stu-id="73fbd-175">To see *msWriteProfilerMark* tracing, scroll down to the  *Generic Events* graph and select **HTML msWriteProfilerMark** from the drop-down menu.</span></span>

<span data-ttu-id="73fbd-176">**线程延迟分析**-此选项卡通常由 Microsoft Edge 开发人员用于在一个线程被阻止并等待另一个线程时进行调查。</span><span class="sxs-lookup"><span data-stu-id="73fbd-176">**Thread Delay Analysis** - This tab is often used by Microsoft Edge developers to investigate when one thread is blocked and waiting on another.</span></span> <span data-ttu-id="73fbd-177">对于 web 开发人员来说，这种情况也可能会很有用。</span><span class="sxs-lookup"><span data-stu-id="73fbd-177">On rare occasions it might also be useful to web developers.</span></span>


### <span data-ttu-id="73fbd-178">3. 缩放以删除跟踪断开</span><span class="sxs-lookup"><span data-stu-id="73fbd-178">3. Zoom to remove trace rundown</span></span>
<span data-ttu-id="73fbd-179">你可以通过删除你的图表的空尾随*跟踪断开*部分来重点分析你的分析。</span><span class="sxs-lookup"><span data-stu-id="73fbd-179">You can focus your analysis by removing the empty trailing *Trace Rundown* sections of your graphs.</span></span> <span data-ttu-id="73fbd-180">当前显示的任何图形：</span><span class="sxs-lookup"><span data-stu-id="73fbd-180">From any of the graphs currently showing:</span></span>
 - <span data-ttu-id="73fbd-181">左键单击要调查的图表数据的开始</span><span class="sxs-lookup"><span data-stu-id="73fbd-181">Left-click at the start of the graph data you wish to investigate</span></span>
 - <span data-ttu-id="73fbd-182">按住、拖动和释放以选择所需区域</span><span class="sxs-lookup"><span data-stu-id="73fbd-182">Hold, drag and release to select the desired region</span></span>
 - <span data-ttu-id="73fbd-183">右键单击并选择 "**缩放**"</span><span class="sxs-lookup"><span data-stu-id="73fbd-183">Right-click and select **Zoom**</span></span>

<span data-ttu-id="73fbd-184">缩放将应用于活动选项卡上的所有图形和图表。</span><span class="sxs-lookup"><span data-stu-id="73fbd-184">The zoom will apply to all graphs and charts on the active tab.</span></span>

![发布缩放](./media/wpa-postzoom.png)


### <span data-ttu-id="73fbd-186">4. 调查占用 CPU 周期的内容</span><span class="sxs-lookup"><span data-stu-id="73fbd-186">4. Investigate what's taking up CPU cycles</span></span>
 <span data-ttu-id="73fbd-187">"**帧分析**" 选项卡中的 " **CPU 使用率（取样）** " 表是最有可能发生大多数分析的情况。</span><span class="sxs-lookup"><span data-stu-id="73fbd-187">The **CPU Usage (Sampled)** table in the **Frame Analysis** tab is where most of your analysis will likely happen.</span></span> <span data-ttu-id="73fbd-188">你可以展开各种进程以标识最密集的计算密集型 JavaScript 和浏览器代码。</span><span class="sxs-lookup"><span data-stu-id="73fbd-188">You can expand the various processes to identify the most compute intensive JavaScript and browser code.</span></span> <span data-ttu-id="73fbd-189">通常，只有一位 JavaScript 负责性能问题，并且花时间优化它可能会产生显著的差异。</span><span class="sxs-lookup"><span data-stu-id="73fbd-189">Often a single bit of JavaScript is responsible for a performance issue, and taking the time to optimize it can make a significant difference.</span></span>

### <span data-ttu-id="73fbd-190">5. 深化到任何运行速度较慢的 JavaScript 代码</span><span class="sxs-lookup"><span data-stu-id="73fbd-190">5. Drill into any slow-running JavaScript code</span></span>
<span data-ttu-id="73fbd-191">在方案中确定负责占用大部分时间的 JavaScript 时，可通过底部的 DOM 呼叫分析。</span><span class="sxs-lookup"><span data-stu-id="73fbd-191">Bottom up DOM call analysis can be useful for identifying the JavaScript responsible for taking up the majority of time during the scenario.</span></span> <span data-ttu-id="73fbd-192">当许多顶级调用重新使用相同的 JavaScript 库时，此功能尤其有用。</span><span class="sxs-lookup"><span data-stu-id="73fbd-192">This is especially helpful when many top level calls are re-using the same JavaScript libraries.</span></span>

<span data-ttu-id="73fbd-193">首先 *，按进程、线程、活动、堆栈查看 CPU 使用率（取样）细目*。</span><span class="sxs-lookup"><span data-stu-id="73fbd-193">Start by looking at *CPU Usage (Sampled) Breakdown by Process, Thread, Activity, Stack*.</span></span> <span data-ttu-id="73fbd-194">单击 "**堆叠**" 列中的任意单元格。</span><span class="sxs-lookup"><span data-stu-id="73fbd-194">Click on any cell in **Stack** column.</span></span> <span data-ttu-id="73fbd-195">按*Ctrl + F*并搜索*ExternalFunctionThunk*。</span><span class="sxs-lookup"><span data-stu-id="73fbd-195">Press *Ctrl+F* and search for *ExternalFunctionThunk*.</span></span>

>[!NOTE] 
><span data-ttu-id="73fbd-196">这仅适用于已成功加载符号的情况。</span><span class="sxs-lookup"><span data-stu-id="73fbd-196">This only works if you have successfully loaded symbols.</span></span>

![搜索 ExternalFunctionThunk](./media/wpa-externalfunctionthunk.png)

<span data-ttu-id="73fbd-198">通过*ExternalFunctionThunk*调查任何行。</span><span class="sxs-lookup"><span data-stu-id="73fbd-198">Investigate any lines with *ExternalFunctionThunk*.</span></span> <span data-ttu-id="73fbd-199">这是 Chakra JavaScript 引擎到 Microsoft Edge 引擎的接口。</span><span class="sxs-lookup"><span data-stu-id="73fbd-199">This is the interface from the Chakra JavaScript engine to the Microsoft Edge engine.</span></span> <span data-ttu-id="73fbd-200">它显示了从浏览器到执行 JavaScript 的代码桥。</span><span class="sxs-lookup"><span data-stu-id="73fbd-200">It shows where code bridges from the browser to JavaScript execution.</span></span> <span data-ttu-id="73fbd-201">右键单击行，然后选择 " **View Callees**  >  **按模块**查看 Callees" 以查看最长运行的浏览器引擎函数的加权列表。</span><span class="sxs-lookup"><span data-stu-id="73fbd-201">Right-click on the line and select **View Callees** > **By Module** to see a weighted list of longest running browser engine functions.</span></span>

![查看 Callees](./media/wpa-viewcallees.png)

<span data-ttu-id="73fbd-203">若要标识调用特定 API 的所有 JavaScript，请右键单击它并选择 "按函数**查看调用方**"  >  **By Function** ，然后展开树以查看和比较相对权重。</span><span class="sxs-lookup"><span data-stu-id="73fbd-203">To identify all the JavaScript calling a specific API, right-click on it and select **View Callers** > **By Function** and expand the tree to view and compare the relative weights.</span></span>
