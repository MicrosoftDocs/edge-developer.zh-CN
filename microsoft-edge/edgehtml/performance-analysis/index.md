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
# 性能分析  

如果你对性能没有了解，你应该查看 [F12 DevTools 指南](../devtools-guide/index.md)。
内置于 Microsoft Edge 中的 [F12](../devtools-guide/index.md) 工具可用于分析网站的一般性能。  它提供与 (类似的 [) ，](/windows-hardware/test/wpt/index) 但从浏览器Toolkit Windows Performance Toolkit功能会受到限制。  

如果你想要更深入地分析浏览器性能，Microsoft Edge 团队将使用 [Windows Performance Toolkit](/windows-hardware/test/wpt/index) (WPT) 。  WPT 由 Windows 团队创建，以执行深入计划性能分析。  它跨越网站 JavaScript 和 Microsoft Edge 本机代码之间的边界，允许在同一工具中查看这两者。  WPT 可用于：  

*   测量软件完成工作的 CPU 时间  
*   计算软件分配的内存  
*   显示从远程服务器下载文件的详细信息  
*   测量帧速率。  

若要开始使用 Windows Performance Toolkit分析你的网站，你首先需要下载 Windows 10 评估和部署工具包 ([ADK) 。 ](https://developer.microsoft.com/windows/hardware/windows-assessment-deployment-kit)  在 *安装期间Toolkit* Windows Performance Toolkit选项：  

![ADK 安装选项](./media/adk-installoptions.png)  

下面我们将介绍如何记录和分析性能跟踪。  
若要了解有关 Windows Performance Toolkit中包含的内容，请查看完整的 [WPT 文档](/windows-hardware/test/wpt/index)。  

## 记录跟踪  

接下来，设置用户方案并准备使用 Windows Performance Recorder 收集跟踪。  
下面介绍如何使用 Windows Performance Recorder (*WPR *) 。  

### 1. 准备环境以收集性能跟踪  

关闭尽可能多的正在运行的程序，以避免跟踪中出现要录制的噪音。  理想情况下，唯一运行的软件是 Windows Performance Recorder (WPR) 浏览器。  

### 2. 启动 Windows Performance Recorder (WPR) 并选择选项  

启动 Windows Performance Recorder 并确保展开 **更多** 选项切换。  选中 *"边缘浏览器"* 和 *"HTML 响应情况* 分析"复选框。  

![Windows 性能记录选项](./media/wprui-options.png)  

#### 收集跟踪的提示和技巧  

*   尝试将后台活动保持为所需的绝对最小值。  后台进程可能会扭曲感知的性能和实际性能特征，并影响结果。  理想情况下，浏览器和 WPR 旁边没有其他正在运行的应用程序。  
*   确定你正在分析的方案，并尽量将它们保持为原子。  例如，如果您的网站在加载页面、滚动和选择表格中的内容时遇到性能问题，请将问题分为三种方案：  
    *   页面加载 (导航开始到页面加载完成)   
    *   滚动  
    *   在表中选择内容  
*   如果方案涉及导航到网站，请考虑从大约：空白开始方案。  从 about：blank 开始可以避免上一页的开销。  如果涉及离开网站，请导航到 about：blank 以完成方案。  这将阻止跟踪其他网站的噪音，除非网站之间的特定交互是正在调查的问题。  

### 3. 记录方案  

单击 **"** 开始"开始录制。  该工具将报告它使用的缓冲区大小，以帮助你预测生成的文件的大小。  执行要测量的用户方案，然后单击"保存"停止**** 录制并保存跟踪。  在完成方案后立即保存将有助于最大程度地减小跟踪文件的大小。  

![Windows 性能记录开始 - 录制](./media/wprui-recording.png)  

WPR 工具将指示跟踪信息已成功保存：  

![Windows Performance Record Start - 保存完成](./media/wprui-savecomplete.png)  

## 分析跟踪  

现在，你已收集性能数据，可以使用 Windows 性能分析器分析跟踪，以查看可以进行哪些优化。  
下面将了解如何分析 Web 方案性能数据。  

### 1. 打开 Windows Performance Analyzer (WPA)   

启动 Windows 性能分析器，然后打开要分析 (`.etl` **文件**  >  **打开...**) 。  

### 2. 加载符号并应用 *HTML 分析* 配置文件  

> [!WARNING]
> 首次加载符号需要大量下载，并且需要大量时间连接到典型的 Internet 连接。  

通过从菜单中选择 **"跟踪**  >  **加载符号"加载**符号。  符号将缓存到磁盘，并且将来的跟踪将更快地加载符号。  

通过限制对 Microsoft Edge 和 Web 应用主机的加载，可以显著加快符号的加载速度。  选择 **"**  >  **跟踪配置符号**"，将 **"加载设置"** 限制为仅 `MicrosoftEdgeCP.exe` 和 `WWAHost.exe` 。  

![符号限制](./media/wpa-symbolrestrictions.png)  

符号开始加载后，应用*Html 分析配置文件* (**配置文件**  >  **应用...**  > **浏览目录...**  > **HtmlResponsivenessAnalysis.wpaProfile**)   
该配置文件将加载多个图表和表格以用于分析。  对于几乎所有网站调查，我们建议从此配置文件开始。  

![大图](./media/wpa-bigpicture.png)  

#### Html 响应分析配置文件  

*Html 响应分析*配置文件提供四个选项卡：  

**大** 图 - 这可用于确认没有意外的 CPU 活动源，并且浏览器确实使用了所有可用资源。  检查 CPU 使用率，并验证除浏览器外没有任何进程对 CPU 使用率产生显著影响。  

**帧分析** - 此部分用于基本分析。  通过 *" (属性 *) 的 CPU 使用率图，可以快速了解负责 CPU 使用率的子系统。  在*HTML UI*线程上分解 CPU 使用率 (*示例*) 有助于识别关键性能瓶颈。  

**跟踪标记** - 此部分显示来自浏览器 (Microsoft Edge) 的所有跟踪标记，包括 *msWriteProfilerMark，* 它提供用于测量代码的精确点。  To see *msWriteProfilerMark* tracing， scroll down to the  *Generic Events* graph and select **HTML msWriteProfilerMark** from the drop-down menu.  

**线程延迟分析** - Microsoft Edge 开发人员通常使用此选项卡调查一个线程被阻止并等待另一个线程的时间。  在极少数情况下，它也可能对 Web 开发人员有用。  

### 3. 缩放以删除跟踪运行  

通过删除图形的空尾随 *跟踪运行部分，可以* 专注于分析。  从当前显示的任何图形：  
*   在你希望调查的图形数据的开始处单击  
*   按住、拖动并释放以选择所需区域  
*   右键单击并选择 **"缩放"**  

缩放将应用于活动选项卡上的所有图形和图表。  

![Post Zoom](./media/wpa-postzoom.png)  

### 4. 调查占用 CPU 周期的是什么  

 "**帧 (") **中的"已采样的 CPU 使用率****"表是大部分分析可能发生的地方。  可以展开各种进程，以确定计算密集型 JavaScript 和浏览器代码。  通常，一位 JavaScript 负责性能问题，花时间优化它可能会带来显著差异。  

### 5. 深入了解任何运行缓慢的 JavaScript 代码  

底部向上 DOM 调用分析可用于标识负责在方案期间多数时间采用的时间的 JavaScript。  当许多顶级调用使用相同的 JavaScript 库时，这尤其有用。  

首先查看按进程 *、线程、 (、堆栈) 采样的*CPU 使用率。  单击 Stack 列中 **的任何单元格** 。  按 *Ctrl+F* 并搜索 *ExternalFunctionThunk*。  

> [!NOTE] 
> 这仅在成功加载符号时有效。  

![搜索 ExternalFunctionThunk](./media/wpa-externalfunctionthunk.png)  

使用 *ExternalFunctionThunk 调查任何行*。  这是从 Chakra JavaScript 引擎到 Microsoft Edge 引擎的接口。  它显示了从浏览器到 JavaScript 执行的代码桥接位置。  右键单击该行并选择 **"** 按模块查看呼叫者"以查看运行时间最长的浏览器引擎功能的  >  **** 加权列表。  

![查看被叫者](./media/wpa-viewcallees.png)  

要标识调用特定 API 的所有 JavaScript，请右键单击它并选择****"按函数查看调用方"，然后展开树以查看和  >  **** 比较相对权重。  
