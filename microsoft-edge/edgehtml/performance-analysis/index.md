---
description: 使用 F12 开发人员工具分析网站的一般性能。
title: 性能分析
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
ms.assetid: 7a5f9fd0-90a9-43db-b271-178c06da5896
keywords: edge， Web 开发， html， css， javascript， 开发人员
ms.date: 12/15/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: e585d07ebae547319c16b6eea579ad26ffb84ce3
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232510"
---
# <span data-ttu-id="4f0f4-104">性能分析</span><span class="sxs-lookup"><span data-stu-id="4f0f4-104">Performance Analysis</span></span>  

<span data-ttu-id="4f0f4-105">如果你对性能没有了解，你应该查看 [F12 DevTools 指南](../devtools-guide/index.md)。</span><span class="sxs-lookup"><span data-stu-id="4f0f4-105">If you're new to performance, you should check out the [F12 DevTools guide](../devtools-guide/index.md).</span></span>
<span data-ttu-id="4f0f4-106">内置于 Microsoft Edge 中的 [F12](../devtools-guide/index.md) 工具可用于分析网站的一般性能。</span><span class="sxs-lookup"><span data-stu-id="4f0f4-106">The [F12 tools](../devtools-guide/index.md) built into Microsoft Edge can be used to analyze the general performance of a web site.</span></span>  <span data-ttu-id="4f0f4-107">它提供与 (类似的 [) ，](/windows-hardware/test/wpt/index) 但从浏览器Toolkit Windows Performance Toolkit功能会受到限制。</span><span class="sxs-lookup"><span data-stu-id="4f0f4-107">It provides similar (but more limited) capabilities to the [Windows Performance Toolkit](/windows-hardware/test/wpt/index) from right within the browser.</span></span>  

<span data-ttu-id="4f0f4-108">如果你想要更深入地分析浏览器性能，Microsoft Edge 团队将使用 [Windows Performance Toolkit](/windows-hardware/test/wpt/index) (WPT) 。</span><span class="sxs-lookup"><span data-stu-id="4f0f4-108">If you want a deeper analysis of browser performance, the Microsoft Edge team uses the [Windows Performance Toolkit](/windows-hardware/test/wpt/index) (WPT).</span></span>  <span data-ttu-id="4f0f4-109">WPT 由 Windows 团队创建，以执行深入计划性能分析。</span><span class="sxs-lookup"><span data-stu-id="4f0f4-109">WPT was created by the Windows team to conduct in-depth program performance analysis.</span></span>  <span data-ttu-id="4f0f4-110">它跨越网站 JavaScript 和 Microsoft Edge 本机代码之间的边界，允许在同一工具中查看这两者。</span><span class="sxs-lookup"><span data-stu-id="4f0f4-110">It straddles the boundaries between website JavaScript and Microsoft Edge native code, allowing both to be viewed within the same tool.</span></span>  <span data-ttu-id="4f0f4-111">WPT 可用于：</span><span class="sxs-lookup"><span data-stu-id="4f0f4-111">WPT can be used to:</span></span>  

*   <span data-ttu-id="4f0f4-112">测量软件完成工作的 CPU 时间</span><span class="sxs-lookup"><span data-stu-id="4f0f4-112">Measure CPU time taken for software to complete work</span></span>  
*   <span data-ttu-id="4f0f4-113">计算软件分配的内存</span><span class="sxs-lookup"><span data-stu-id="4f0f4-113">Calculate the memory allocated by software</span></span>  
*   <span data-ttu-id="4f0f4-114">显示从远程服务器下载文件的详细信息</span><span class="sxs-lookup"><span data-stu-id="4f0f4-114">Show the details of downloading files from remote servers</span></span>  
*   <span data-ttu-id="4f0f4-115">测量帧速率。</span><span class="sxs-lookup"><span data-stu-id="4f0f4-115">Measure frame rate.</span></span>  

<span data-ttu-id="4f0f4-116">若要开始使用 Windows Performance Toolkit分析你的网站，你首先需要下载 Windows 10 评估和部署工具包 ([ADK) 。 ](https://developer.microsoft.com/windows/hardware/windows-assessment-deployment-kit)</span><span class="sxs-lookup"><span data-stu-id="4f0f4-116">To get started with using the Windows Performance Toolkit to analyze your website, you'll first need to download the [Windows 10 Assessment and Deployment Kit (ADK)](https://developer.microsoft.com/windows/hardware/windows-assessment-deployment-kit).</span></span>  <span data-ttu-id="4f0f4-117">在 *安装期间Toolkit* Windows Performance Toolkit选项：</span><span class="sxs-lookup"><span data-stu-id="4f0f4-117">Select the *Windows Performance Toolkit* option during installation:</span></span>  

![ADK 安装选项](./media/adk-installoptions.png)  

<span data-ttu-id="4f0f4-119">下面我们将介绍如何记录和分析性能跟踪。</span><span class="sxs-lookup"><span data-stu-id="4f0f4-119">Here we'll cover how to record and analyze a performance trace.</span></span>  
<span data-ttu-id="4f0f4-120">若要了解有关 Windows Performance Toolkit中包含的内容，请查看完整的 [WPT 文档](/windows-hardware/test/wpt/index)。</span><span class="sxs-lookup"><span data-stu-id="4f0f4-120">To learn more about what's included in the Windows Performance Toolkit, check out the full [WPT documentation](/windows-hardware/test/wpt/index).</span></span>  

## <span data-ttu-id="4f0f4-121">记录跟踪</span><span class="sxs-lookup"><span data-stu-id="4f0f4-121">Recording a trace</span></span>  

<span data-ttu-id="4f0f4-122">接下来，设置用户方案并准备使用 Windows Performance Recorder 收集跟踪。</span><span class="sxs-lookup"><span data-stu-id="4f0f4-122">Next, set up your user scenario and prepare to gather a trace using Windows Performance Recorder.</span></span>  
<span data-ttu-id="4f0f4-123">下面介绍如何使用 Windows Performance Recorder (\*WPR \*) 。</span><span class="sxs-lookup"><span data-stu-id="4f0f4-123">Here's how to profile your web scenario with the *Windows Performance Recorder (WPR)*.</span></span>  

### <span data-ttu-id="4f0f4-124">1. 准备环境以收集性能跟踪</span><span class="sxs-lookup"><span data-stu-id="4f0f4-124">1.  Prepare your environment to gather a performance trace</span></span>  

<span data-ttu-id="4f0f4-125">关闭尽可能多的正在运行的程序，以避免跟踪中出现要录制的噪音。</span><span class="sxs-lookup"><span data-stu-id="4f0f4-125">Shut down as many running programs as possible to avoid noise in the trace that you're about to record.</span></span>  <span data-ttu-id="4f0f4-126">理想情况下，唯一运行的软件是 Windows Performance Recorder (WPR) 浏览器。</span><span class="sxs-lookup"><span data-stu-id="4f0f4-126">Ideally, the only running software will be Windows Performance Recorder (WPR) and the browser.</span></span>  

### <span data-ttu-id="4f0f4-127">2. 启动 Windows Performance Recorder (WPR) 并选择选项</span><span class="sxs-lookup"><span data-stu-id="4f0f4-127">2.  Launch Windows Performance Recorder (WPR) and select options</span></span>  

<span data-ttu-id="4f0f4-128">启动 Windows Performance Recorder 并确保展开 **更多** 选项切换。</span><span class="sxs-lookup"><span data-stu-id="4f0f4-128">Launch the Windows Performance Recorder and ensure that **More options** toggle is expanded.</span></span>  <span data-ttu-id="4f0f4-129">选中 *"边缘浏览器"* 和 *"HTML 响应情况* 分析"复选框。</span><span class="sxs-lookup"><span data-stu-id="4f0f4-129">Select the *Edge Browser* and *HTML Responsiveness* scenario analysis checkboxes.</span></span>  

![Windows 性能记录选项](./media/wprui-options.png)  

#### <span data-ttu-id="4f0f4-131">收集跟踪的提示和技巧</span><span class="sxs-lookup"><span data-stu-id="4f0f4-131">Tips and tricks for gathering traces</span></span>  

*   <span data-ttu-id="4f0f4-132">尝试将后台活动保持为所需的绝对最小值。</span><span class="sxs-lookup"><span data-stu-id="4f0f4-132">Try to keep background activity to an absolute required minimum.</span></span>  <span data-ttu-id="4f0f4-133">后台进程可能会扭曲感知的性能和实际性能特征，并影响结果。</span><span class="sxs-lookup"><span data-stu-id="4f0f4-133">Background processes may skew both perceived performance and actual performance characteristics and affect the results.</span></span>  <span data-ttu-id="4f0f4-134">理想情况下，浏览器和 WPR 旁边没有其他正在运行的应用程序。</span><span class="sxs-lookup"><span data-stu-id="4f0f4-134">Ideally there are no other running applications beside browser and WPR.</span></span>  
*   <span data-ttu-id="4f0f4-135">确定你正在分析的方案，并尽量将它们保持为原子。</span><span class="sxs-lookup"><span data-stu-id="4f0f4-135">Identify the scenarios you're analyzing and try to keep them as atomic as possible.</span></span>  <span data-ttu-id="4f0f4-136">例如，如果您的网站在加载页面、滚动和选择表格中的内容时遇到性能问题，请将问题分为三种方案：</span><span class="sxs-lookup"><span data-stu-id="4f0f4-136">For example, if your site has performance problems when loading the page, scrolling, and selecting something in a table, separate the issues into three scenarios:</span></span>  
    *   <span data-ttu-id="4f0f4-137">页面加载 (导航开始到页面加载完成) </span><span class="sxs-lookup"><span data-stu-id="4f0f4-137">Page load (from start of navigation to page load complete)</span></span>  
    *   <span data-ttu-id="4f0f4-138">滚动</span><span class="sxs-lookup"><span data-stu-id="4f0f4-138">Scroll</span></span>  
    *   <span data-ttu-id="4f0f4-139">在表中选择内容</span><span class="sxs-lookup"><span data-stu-id="4f0f4-139">Selecting something in the table</span></span>  
*   <span data-ttu-id="4f0f4-140">如果方案涉及导航到网站，请考虑从大约：空白开始方案。</span><span class="sxs-lookup"><span data-stu-id="4f0f4-140">If a scenario involves navigating to a site, consider beginning the scenario at about:blank.</span></span>  <span data-ttu-id="4f0f4-141">从 about：blank 开始可以避免上一页的开销。</span><span class="sxs-lookup"><span data-stu-id="4f0f4-141">Starting at about:blank will avoid the overhead of the previous page.</span></span>  <span data-ttu-id="4f0f4-142">如果涉及离开网站，请导航到 about：blank 以完成方案。</span><span class="sxs-lookup"><span data-stu-id="4f0f4-142">If it involves navigating away from a site, navigate to about:blank to complete the scenario.</span></span>  <span data-ttu-id="4f0f4-143">这将阻止跟踪其他网站的噪音，除非网站之间的特定交互是正在调查的问题。</span><span class="sxs-lookup"><span data-stu-id="4f0f4-143">This will keep the noise of other sites out of the trace unless the specific interaction between sites is the issue under investigation.</span></span>  

### <span data-ttu-id="4f0f4-144">3. 记录方案</span><span class="sxs-lookup"><span data-stu-id="4f0f4-144">3.  Record the scenario</span></span>  

<span data-ttu-id="4f0f4-145">单击 **"** 开始"开始录制。</span><span class="sxs-lookup"><span data-stu-id="4f0f4-145">Click **Start** to begin recording.</span></span>  <span data-ttu-id="4f0f4-146">该工具将报告它使用的缓冲区大小，以帮助你预测生成的文件的大小。</span><span class="sxs-lookup"><span data-stu-id="4f0f4-146">The tool will report the size of the buffer it is using to help you anticipate the size of the generated file.</span></span>  <span data-ttu-id="4f0f4-147">执行要测量的用户方案，然后单击"保存"停止 录制并保存跟踪。</span><span class="sxs-lookup"><span data-stu-id="4f0f4-147">Perform the user scenario you want to measure, then click **Save** to stop the recording and save the trace.</span></span>  <span data-ttu-id="4f0f4-148">在完成方案后立即保存将有助于最大程度地减小跟踪文件的大小。</span><span class="sxs-lookup"><span data-stu-id="4f0f4-148">Saving immediately after finishing your scenario will help minimize the size of the trace file.</span></span>  

![Windows 性能记录开始 - 录制](./media/wprui-recording.png)  

<span data-ttu-id="4f0f4-150">WPR 工具将指示跟踪信息已成功保存：</span><span class="sxs-lookup"><span data-stu-id="4f0f4-150">The WPR tool will indicate that your trace information was saved successfully:</span></span>  

![Windows Performance Record Start - 保存完成](./media/wprui-savecomplete.png)  

## <span data-ttu-id="4f0f4-152">分析跟踪</span><span class="sxs-lookup"><span data-stu-id="4f0f4-152">Analyzing a trace</span></span>  

<span data-ttu-id="4f0f4-153">现在，你已收集性能数据，可以使用 Windows 性能分析器分析跟踪，以查看可以进行哪些优化。</span><span class="sxs-lookup"><span data-stu-id="4f0f4-153">Now that you've gathered your performance data, you can analyze the trace using Windows Performance Analyzer to see what optimizations can be made.</span></span>  
<span data-ttu-id="4f0f4-154">下面将了解如何分析 Web 方案性能数据。</span><span class="sxs-lookup"><span data-stu-id="4f0f4-154">Here's how to analyze your web scenario performance data.</span></span>  

### <span data-ttu-id="4f0f4-155">1. 打开 Windows Performance Analyzer (WPA) </span><span class="sxs-lookup"><span data-stu-id="4f0f4-155">1.  Open Windows Performance Analyzer (WPA)</span></span>  

<span data-ttu-id="4f0f4-156">启动 Windows 性能分析器，然后打开要分析 (`.etl` **文件**  >  **打开...**) 。</span><span class="sxs-lookup"><span data-stu-id="4f0f4-156">Launch Windows Performance Analyzer and open the `.etl` file to be analyzed (**File** > **Open...**).</span></span>  

### <span data-ttu-id="4f0f4-157">2. 加载符号并应用 *HTML 分析* 配置文件</span><span class="sxs-lookup"><span data-stu-id="4f0f4-157">2.  Load symbols and apply the *HTML analysis* profile</span></span>  

> [!WARNING]
> <span data-ttu-id="4f0f4-158">首次加载符号需要大量下载，并且需要大量时间连接到典型的 Internet 连接。</span><span class="sxs-lookup"><span data-stu-id="4f0f4-158">Loading symbols for the first time will require a large download and will take a significant amount of time on a typical internet connection.</span></span>  

<span data-ttu-id="4f0f4-159">通过从菜单中选择 **"跟踪**  >  **加载符号"加载**符号。</span><span class="sxs-lookup"><span data-stu-id="4f0f4-159">Load your symbols by selecting **Trace** > **Load Symbols** from the menu.</span></span>  <span data-ttu-id="4f0f4-160">符号将缓存到磁盘，并且将来的跟踪将更快地加载符号。</span><span class="sxs-lookup"><span data-stu-id="4f0f4-160">The symbols will be cached to disk and future traces will load symbols much faster.</span></span>  

<span data-ttu-id="4f0f4-161">通过限制对 Microsoft Edge 和 Web 应用主机的加载，可以显著加快符号的加载速度。</span><span class="sxs-lookup"><span data-stu-id="4f0f4-161">You can load symbols significantly faster by restricting the loading to Microsoft Edge and the web apps host.</span></span>  <span data-ttu-id="4f0f4-162">选择 **"**  >  **跟踪配置符号**"，将 **"加载设置"** 限制为仅 `MicrosoftEdgeCP.exe` 和 `WWAHost.exe` 。</span><span class="sxs-lookup"><span data-stu-id="4f0f4-162">Select **Trace** > **Configure Symbols** and restrict the **Load Settings** to only `MicrosoftEdgeCP.exe` and `WWAHost.exe`.</span></span>  

![符号限制](./media/wpa-symbolrestrictions.png)  

<span data-ttu-id="4f0f4-164">符号开始加载后，应用*Html 分析配置文件* (**配置文件**  >  **应用...**  > **浏览目录...**  > **HtmlResponsivenessAnalysis.wpaProfile**) </span><span class="sxs-lookup"><span data-stu-id="4f0f4-164">After symbols begin loading, apply the *Html Analysis Profile* (**Profiles** > **Apply...** > **Browse Catalog...** > **HtmlResponsivenessAnalysis.wpaProfile**)</span></span>  
<span data-ttu-id="4f0f4-165">该配置文件将加载多个图表和表格以用于分析。</span><span class="sxs-lookup"><span data-stu-id="4f0f4-165">The profile will load several graphs and tables for your analysis.</span></span>  <span data-ttu-id="4f0f4-166">对于几乎所有网站调查，我们建议从此配置文件开始。</span><span class="sxs-lookup"><span data-stu-id="4f0f4-166">For nearly all website investigations, we recommend starting with this profile.</span></span>  

![大图](./media/wpa-bigpicture.png)  

#### <span data-ttu-id="4f0f4-168">Html 响应分析配置文件</span><span class="sxs-lookup"><span data-stu-id="4f0f4-168">The Html Responsiveness Analysis Profile</span></span>  

<span data-ttu-id="4f0f4-169">*Html 响应分析*配置文件提供四个选项卡：</span><span class="sxs-lookup"><span data-stu-id="4f0f4-169">The *Html Responsiveness* analysis profile provides four tabs:</span></span>  

<span data-ttu-id="4f0f4-170">**大** 图 - 这可用于确认没有意外的 CPU 活动源，并且浏览器确实使用了所有可用资源。</span><span class="sxs-lookup"><span data-stu-id="4f0f4-170">**Big Picture** - This is useful for confirming that there are no unexpected sources of CPU activity and the browser is indeed using all available resources.</span></span>  <span data-ttu-id="4f0f4-171">检查 CPU 使用率，并验证除浏览器外没有任何进程对 CPU 使用率产生显著影响。</span><span class="sxs-lookup"><span data-stu-id="4f0f4-171">Check your CPU usage and verify that no processes contribute significantly to CPU usage other than the browser.</span></span>  

<span data-ttu-id="4f0f4-172">**帧分析** - 此部分用于基本分析。</span><span class="sxs-lookup"><span data-stu-id="4f0f4-172">**Frame Analysis** - This section is used for basic analysis.</span></span>  <span data-ttu-id="4f0f4-173">通过 \*" (属性 \*) 的 CPU 使用率图，可以快速了解负责 CPU 使用率的子系统。</span><span class="sxs-lookup"><span data-stu-id="4f0f4-173">The *CPU Usage (Attributed)* graph enables a quick glance for understanding of the subsystems responsible for CPU usage.</span></span>  <span data-ttu-id="4f0f4-174">在*HTML UI*线程上分解 CPU 使用率 (*示例*) 有助于识别关键性能瓶颈。</span><span class="sxs-lookup"><span data-stu-id="4f0f4-174">Breaking down the samples in the *CPU Usage (Sampled)* table on the *HTML UI Thread* is helpful for identifying critical performance bottlenecks.</span></span>  

<span data-ttu-id="4f0f4-175">**跟踪标记** - 此部分显示来自浏览器 (Microsoft Edge) 的所有跟踪标记，包括 *msWriteProfilerMark，* 它提供用于测量代码的精确点。</span><span class="sxs-lookup"><span data-stu-id="4f0f4-175">**Trace Markers** - This section shows all tracing markers coming from the browser (Microsoft Edge), including *msWriteProfilerMark*, which provides precise points for measuring code.</span></span>  <span data-ttu-id="4f0f4-176">To see *msWriteProfilerMark* tracing， scroll down to the  *Generic Events* graph and select **HTML msWriteProfilerMark** from the drop-down menu.</span><span class="sxs-lookup"><span data-stu-id="4f0f4-176">To see *msWriteProfilerMark* tracing, scroll down to the  *Generic Events* graph and select **HTML msWriteProfilerMark** from the drop-down menu.</span></span>  

<span data-ttu-id="4f0f4-177">**线程延迟分析** - Microsoft Edge 开发人员通常使用此选项卡调查一个线程被阻止并等待另一个线程的时间。</span><span class="sxs-lookup"><span data-stu-id="4f0f4-177">**Thread Delay Analysis** - This tab is often used by Microsoft Edge developers to investigate when one thread is blocked and waiting on another.</span></span>  <span data-ttu-id="4f0f4-178">在极少数情况下，它也可能对 Web 开发人员有用。</span><span class="sxs-lookup"><span data-stu-id="4f0f4-178">On rare occasions it might also be useful to web developers.</span></span>  

### <span data-ttu-id="4f0f4-179">3. 缩放以删除跟踪运行</span><span class="sxs-lookup"><span data-stu-id="4f0f4-179">3.  Zoom to remove trace rundown</span></span>  

<span data-ttu-id="4f0f4-180">通过删除图形的空尾随 *跟踪运行部分，可以* 专注于分析。</span><span class="sxs-lookup"><span data-stu-id="4f0f4-180">You can focus your analysis by removing the empty trailing *Trace Rundown* sections of your graphs.</span></span>  <span data-ttu-id="4f0f4-181">从当前显示的任何图形：</span><span class="sxs-lookup"><span data-stu-id="4f0f4-181">From any of the graphs currently showing:</span></span>  
*   <span data-ttu-id="4f0f4-182">在你希望调查的图形数据的开始处单击</span><span class="sxs-lookup"><span data-stu-id="4f0f4-182">Left-click at the start of the graph data you wish to investigate</span></span>  
*   <span data-ttu-id="4f0f4-183">按住、拖动并释放以选择所需区域</span><span class="sxs-lookup"><span data-stu-id="4f0f4-183">Hold, drag and release to select the desired region</span></span>  
*   <span data-ttu-id="4f0f4-184">右键单击并选择 **"缩放"**</span><span class="sxs-lookup"><span data-stu-id="4f0f4-184">Right-click and select **Zoom**</span></span>  

<span data-ttu-id="4f0f4-185">缩放将应用于活动选项卡上的所有图形和图表。</span><span class="sxs-lookup"><span data-stu-id="4f0f4-185">The zoom will apply to all graphs and charts on the active tab.</span></span>  

![Post Zoom](./media/wpa-postzoom.png)  

### <span data-ttu-id="4f0f4-187">4. 调查占用 CPU 周期的是什么</span><span class="sxs-lookup"><span data-stu-id="4f0f4-187">4.  Investigate what's taking up CPU cycles</span></span>  

 <span data-ttu-id="4f0f4-188">"帧 (") 中的"已采样的 CPU 使用率"表是大部分分析可能发生的地方。</span><span class="sxs-lookup"><span data-stu-id="4f0f4-188">The **CPU Usage (Sampled)** table in the **Frame Analysis** tab is where most of your analysis will likely happen.</span></span>  <span data-ttu-id="4f0f4-189">可以展开各种进程，以确定计算密集型 JavaScript 和浏览器代码。</span><span class="sxs-lookup"><span data-stu-id="4f0f4-189">You can expand the various processes to identify the most compute intensive JavaScript and browser code.</span></span>  <span data-ttu-id="4f0f4-190">通常，一位 JavaScript 负责性能问题，花时间优化它可能会带来显著差异。</span><span class="sxs-lookup"><span data-stu-id="4f0f4-190">Often a single bit of JavaScript is responsible for a performance issue, and taking the time to optimize it can make a significant difference.</span></span>  

### <span data-ttu-id="4f0f4-191">5. 深入了解任何运行缓慢的 JavaScript 代码</span><span class="sxs-lookup"><span data-stu-id="4f0f4-191">5.  Drill into any slow-running JavaScript code</span></span>  

<span data-ttu-id="4f0f4-192">底部向上 DOM 调用分析可用于标识负责在方案期间多数时间采用的时间的 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="4f0f4-192">Bottom up DOM call analysis can be useful for identifying the JavaScript responsible for taking up the majority of time during the scenario.</span></span>  <span data-ttu-id="4f0f4-193">当许多顶级调用使用相同的 JavaScript 库时，这尤其有用。</span><span class="sxs-lookup"><span data-stu-id="4f0f4-193">This is especially helpful when many top level calls are re-using the same JavaScript libraries.</span></span>  

<span data-ttu-id="4f0f4-194">首先查看按进程 *、线程、 (、堆栈) 采样的*CPU 使用率。</span><span class="sxs-lookup"><span data-stu-id="4f0f4-194">Start by looking at *CPU Usage (Sampled) Breakdown by Process, Thread, Activity, Stack*.</span></span>  <span data-ttu-id="4f0f4-195">单击 Stack 列中 **的任何单元格** 。</span><span class="sxs-lookup"><span data-stu-id="4f0f4-195">Click on any cell in **Stack** column.</span></span>  <span data-ttu-id="4f0f4-196">按 *Ctrl+F* 并搜索 *ExternalFunctionThunk*。</span><span class="sxs-lookup"><span data-stu-id="4f0f4-196">Press *Ctrl+F* and search for *ExternalFunctionThunk*.</span></span>  

> [!NOTE] 
> <span data-ttu-id="4f0f4-197">这仅在成功加载符号时有效。</span><span class="sxs-lookup"><span data-stu-id="4f0f4-197">This only works if you have successfully loaded symbols.</span></span>  

![搜索 ExternalFunctionThunk](./media/wpa-externalfunctionthunk.png)  

<span data-ttu-id="4f0f4-199">使用 *ExternalFunctionThunk 调查任何行*。</span><span class="sxs-lookup"><span data-stu-id="4f0f4-199">Investigate any lines with *ExternalFunctionThunk*.</span></span>  <span data-ttu-id="4f0f4-200">这是从 Chakra JavaScript 引擎到 Microsoft Edge 引擎的接口。</span><span class="sxs-lookup"><span data-stu-id="4f0f4-200">This is the interface from the Chakra JavaScript engine to the Microsoft Edge engine.</span></span>  <span data-ttu-id="4f0f4-201">它显示了从浏览器到 JavaScript 执行的代码桥接位置。</span><span class="sxs-lookup"><span data-stu-id="4f0f4-201">It shows where code bridges from the browser to JavaScript execution.</span></span>  <span data-ttu-id="4f0f4-202">右键单击该行并选择 **"** 按模块查看呼叫者"以查看运行时间最长的浏览器引擎功能的  >   加权列表。</span><span class="sxs-lookup"><span data-stu-id="4f0f4-202">Right-click on the line and select **View Callees** > **By Module** to see a weighted list of longest running browser engine functions.</span></span>  

![查看被叫者](./media/wpa-viewcallees.png)  

<span data-ttu-id="4f0f4-204">要标识调用特定 API 的所有 JavaScript，请右键单击它并选择"按函数查看调用方"，然后展开树以查看和  >   比较相对权重。</span><span class="sxs-lookup"><span data-stu-id="4f0f4-204">To identify all the JavaScript calling a specific API, right-click on it and select **View Callers** > **By Function** and expand the tree to view and compare the relative weights.</span></span>  
