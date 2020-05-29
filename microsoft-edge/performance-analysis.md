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
# 性能分析

如果你不熟悉性能，请查看[F12 DevTools 指南](./devtools-guide.md)。
可使用内置于 Microsoft Edge 的[F12 工具](./devtools-guide.md)分析网站的常规性能。 它在浏览器中向[Windows 性能工具包](https://docs.microsoft.com/windows-hardware/test/wpt/index)提供类似（但更有限）的功能。



如果想要对浏览器性能进行更深入的分析，Microsoft Edge 团队将使用[Windows 性能工具包](https://docs.microsoft.com/windows-hardware/test/wpt/index)（WPT）。 WPT 由 Windows 团队创建，用于执行深入的计划性能分析。 它 straddles 网站 JavaScript 和 Microsoft Edge 本机代码之间的边界，允许在同一工具内查看二者。 WPT 可用于：
 - 测量软件完成工作所用的 CPU 时间
 - 计算软件分配的内存
 - 显示从远程服务器下载文件的详细信息
 - 度量帧速率。


若要开始使用 Windows 性能工具包分析你的网站，你首先需要下载[Windows 10 评估和部署工具包（ADK）](https://developer.microsoft.com/windows/hardware/windows-assessment-deployment-kit)。 在安装期间选择 " *Windows 性能工具包*" 选项：

![ADK 安装选项](./media/adk-installoptions.png)

下面我们将介绍如何记录和分析性能跟踪。 若要了解有关 Windows 性能工具包中包含的内容的详细信息，请查看完整的[WPT 文档](https://docs.microsoft.com/windows-hardware/test/wpt/index)。

## 录制跟踪
接下来，设置你的用户方案并准备使用 Windows 性能记录器收集跟踪。
下面介绍如何通过*Windows 性能记录器（WPR）* 分析 web 方案。

### 1. 准备环境以收集性能跟踪
尽可能多地关闭正在运行的程序，以避免即将录制的跟踪中的干扰。 理想情况下，运行的唯一软件将是 Windows 性能记录器（WPR）和浏览器。

### 2. 启动 Windows 性能记录器（WPR）并选择选项
启动 Windows 性能记录器并确保展开**更多选项**切换。 选择 "*边缘浏览器*" 和 " *HTML 响应*方案" 分析复选框。

![Windows 性能记录选项](./media/wprui-options.png)

#### 用于收集跟踪的提示和技巧
- 尝试保持后台活动最小为绝对必需。 后台进程可能会扭曲感知性能和实际性能特征，并影响结果。 理想情况下，浏览器和 WPR 旁边没有其他运行的应用程序。
- 确定你正在分析的方案，并尽量尽量使它们保持原子。 例如，如果您的网站在加载页面、滚动和选择表格中的内容时出现性能问题，请将问题划分为三个方案：
  - 页面加载（从导航开始到页面加载完成）
  - 滚动
  - 选择表格中的内容
- 如果方案涉及导航到网站，请考虑在 "关于" 部分中开始使用以下内容：空白。 起始于：空白将避免上一页的开销。 如果它涉及离开网站，请导航到 "关于：空白" 以完成方案。 这将使其他网站的噪音不在跟踪范围内，除非网站之间的特定交互是调查问题。

### 3. 录制方案
单击 "**开始**" 开始录制。 该工具将报告它所使用的缓冲区的大小，以帮助你预测生成的文件的大小。 执行要测量的用户方案，然后单击 "**保存**" 以停止录制并保存跟踪。 在完成方案后立即保存将有助于最大程度地减少跟踪文件的大小。

![Windows 性能记录开始](./media/wprui-recording.png)

WPR 工具将指示你的跟踪信息已成功保存：

![Windows 性能记录开始](./media/wprui-savecomplete.png)


## 分析跟踪
现在，你已收集了性能数据，你可以使用 Windows 性能分析器分析跟踪以查看可进行的优化。
下面介绍了如何分析 web 方案性能数据。

### 1. 打开 Windows 性能分析器（WPA）
启动 Windows 性能分析器并打开 `.etl` 要分析的文件（"**File**  >  **打开文件 ...**"）。

### 2. 加载符号并应用*HTML 分析*配置文件

>[!WARNING]
> 首次加载符号将需要较大的下载，并且将在典型的 internet 连接上花费大量时间。

从菜单中选择 "**跟踪**  >  **加载符号**"，加载您的符号。 这些符号将缓存到磁盘，将来的跟踪将更快地加载符号。

通过限制加载到 Microsoft Edge 和 web 应用主机，可以更快地加载符号。 选择 "**跟踪**"  >  **配置符号**，并将**加载设置**限制为 "仅" `MicrosoftEdgeCP.exe` 和 `WWAHost.exe` 。

![符号限制](./media/wpa-symbolrestrictions.png)

开始加载符号后，应用*Html 分析配置文件*（应用**配置**文件  >  **...**  > **浏览目录 ...**  > **HtmlResponsivenessAnalysis wpaProfile**）配置文件将加载几个图形和表以供分析。 对于几乎所有网站调查，我们建议从该配置文件开始。

![大图片](./media/wpa-bigpicture.png)


#### Html 响应分析配置文件
*Html 响应*分析配置文件提供四个选项卡：

**大图片**-这有助于确认没有意外的 CPU 活动源，并且浏览器确实使用了所有可用的资源。 检查你的 CPU 使用情况，并验证没有任何进程对 CPU 使用率（浏览器除外）进行重大贡献。

**帧分析**-此部分用于基本分析。 *Cpu 使用情况（属性化）* 图形可快速浏览负责 CPU 使用率的子系统。 分解*HTML UI 线程*上*CPU 使用率（取样）* 表中的示例有助于识别关键性能瓶颈。

**跟踪标记**-此部分显示来自浏览器（Microsoft Edge）的所有跟踪标记（包括*msWriteProfilerMark*），其中提供了测量代码的精确点。 若要查看*msWriteProfilerMark*跟踪，请向下滚动到 "*通用事件*" 图形，然后从下拉菜单中选择 " **HTML msWriteProfilerMark** "。

**线程延迟分析**-此选项卡通常由 Microsoft Edge 开发人员用于在一个线程被阻止并等待另一个线程时进行调查。 对于 web 开发人员来说，这种情况也可能会很有用。


### 3. 缩放以删除跟踪断开
你可以通过删除你的图表的空尾随*跟踪断开*部分来重点分析你的分析。 当前显示的任何图形：
 - 左键单击要调查的图表数据的开始
 - 按住、拖动和释放以选择所需区域
 - 右键单击并选择 "**缩放**"

缩放将应用于活动选项卡上的所有图形和图表。

![发布缩放](./media/wpa-postzoom.png)


### 4. 调查占用 CPU 周期的内容
 "**帧分析**" 选项卡中的 " **CPU 使用率（取样）** " 表是最有可能发生大多数分析的情况。 你可以展开各种进程以标识最密集的计算密集型 JavaScript 和浏览器代码。 通常，只有一位 JavaScript 负责性能问题，并且花时间优化它可能会产生显著的差异。

### 5. 深化到任何运行速度较慢的 JavaScript 代码
在方案中确定负责占用大部分时间的 JavaScript 时，可通过底部的 DOM 呼叫分析。 当许多顶级调用重新使用相同的 JavaScript 库时，此功能尤其有用。

首先 *，按进程、线程、活动、堆栈查看 CPU 使用率（取样）细目*。 单击 "**堆叠**" 列中的任意单元格。 按*Ctrl + F*并搜索*ExternalFunctionThunk*。

>[!NOTE] 
>这仅适用于已成功加载符号的情况。

![搜索 ExternalFunctionThunk](./media/wpa-externalfunctionthunk.png)

通过*ExternalFunctionThunk*调查任何行。 这是 Chakra JavaScript 引擎到 Microsoft Edge 引擎的接口。 它显示了从浏览器到执行 JavaScript 的代码桥。 右键单击行，然后选择 " **View Callees**  >  **按模块**查看 Callees" 以查看最长运行的浏览器引擎函数的加权列表。

![查看 Callees](./media/wpa-viewcallees.png)

若要标识调用特定 API 的所有 JavaScript，请右键单击它并选择 "按函数**查看调用方**"  >  **By Function** ，然后展开树以查看和比较相对权重。
