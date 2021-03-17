---
description: 有关在 Microsoft Edge DevTools 中记录和分析性能的所有方法的参考。
title: 性能分析引用
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: e7774dc0aab647b8cf2bf47699368fafe6c21d70
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: MT
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

# <a name="performance-analysis-reference"></a>性能分析引用  

本页全面引用了与分析性能相关的 Microsoft Edge DevTools 功能。  

导航到 [开始分析][DevtoolsEvaluatePerformanceGettingStarted] 运行时性能，获取有关如何使用 [Microsoft Edge DevTools][MicrosoftEdgeDevTools]分析页面性能的引导教程。  

## <a name="record-performance"></a>记录性能  

### <a name="record-runtime-performance"></a>记录运行时性能  

当你想要分析页面运行时的性能（而不是加载）时，请记录运行时性能。  

1.  导航到要分析的页面。  
1.  在**** DevTools 中打开性能工具。  
1.  Choose **Record** \ (![ Record icon ](../media/record-icon.msft.png) \) .  
    
    :::image type="complex" source="../media/evaluate-performance-performance-record-highlight.msft.png" alt-text="记录" lightbox="../media/evaluate-performance-performance-record-highlight.msft.png":::
       **记录**  
    :::image-end:::  
    
1.  与页面交互。  DevTools 记录交互后发生的所有页面活动。  
1.  再次 **选择"录制** "或" **停止** "以停止录制。  
    
### <a name="record-load-performance"></a>记录加载性能  

在页面加载时（而不是运行时）要分析其性能时记录加载性能。  

1.  导航到要分析的页面。  
1.  打开**** DevTools 的性能面板。  
1.  Choose **Refresh page** \ (Refresh Page ![ ](../media/refresh-page-icon.msft.png) \) .  DevTools 在页面刷新时记录性能指标，然后在加载完成后的几秒钟内自动停止录制。  
    
    :::image type="complex" source="../media/evaluate-performance-performance-refresh-button.msft.png" alt-text="刷新页面" lightbox="../media/evaluate-performance-performance-refresh-button.msft.png":::
       **刷新页面**  
    :::image-end:::  
    
DevTools 自动放大大部分活动发生的记录部分。  

:::image type="complex" source="../media/evaluate-performance-performance-refreshed.msft.png" alt-text="页面加载录制" lightbox="../media/evaluate-performance-performance-refreshed.msft.png":::
   页面加载录制  
:::image-end:::  

### <a name="capture-screenshots-while-recording"></a>录制时捕获屏幕截图  

打开" **屏幕截图"** 复选框以捕获录制时每个帧的屏幕截图。  

:::image type="complex" source="../media/evaluate-performance-performance-capture-screenshots-checkbox.msft.png" alt-text=""屏幕截图"复选框" lightbox="../media/evaluate-performance-performance-capture-screenshots-checkbox.msft.png":::
   " **屏幕截图"** 复选框  
:::image-end:::  

导航 [到查看屏幕截图](#view-a-screenshot) ，了解如何与屏幕截图进行交互。  

### <a name="force-garbage-collection-while-recording"></a>在记录时强制进行垃圾回收  

在记录页面时，选择"收集垃圾回收 **\ (** 收集垃圾图标 ![ ](../media/collect-garbage-icon.msft.png) \) 以强制进行垃圾回收。  

:::image type="complex" source="../media/evaluate-performance-performance-collect-garbage-button.msft.png" alt-text="收集垃圾" lightbox="../media/evaluate-performance-performance-collect-garbage-button.msft.png":::
   收集垃圾  
:::image-end:::  

### <a name="show-recording-settings"></a>显示录制设置  

Choose **Capture settings** \ (Capture settings ![ ](../media/capture-settings-icon.msft.png) \) to expose more settings related to how DevTools capture performance recordings.  

:::image type="complex" source="../media/evaluate-performance-performance-capture-settings-button-open-drawer.msft.png" alt-text=""捕获设置"部分" lightbox="../media/evaluate-performance-performance-capture-settings-button-open-drawer.msft.png":::
   " **捕获设置"** 部分  
:::image-end:::  

### <a name="disable-javascript-samples"></a>禁用 JavaScript 示例  

默认情况下，录制 **的 Main** 部分显示录制期间调用的 JavaScript 函数的详细调用堆栈。  若要禁用这些调用堆栈：  

1.  打开" **捕获设置"** 菜单。  导航到["显示录制设置"。](#show-recording-settings)  
1.  打开" **禁用 JavaScript 示例"** 复选框。  
1.  录制页面。  
    
以下 2 个图显示禁用和启用 JavaScript 示例的区别。  当 **禁用** 采样时，录制的 Main 部分要短得多，因为它省略了所有 JavaScript 调用堆栈。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-on.msft.png" alt-text="禁用 JS 示例时录制的示例" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-on.msft.png":::
         禁用 JS 示例时录制的示例  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off.msft.png" alt-text="启用 JS 示例时的记录示例" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off.msft.png":::
         启用 JS 示例时的记录示例  
      :::image-end:::  
   :::column-end:::
:::row-end:::

### <a name="throttle-the-network-while-recording"></a>录制时限制网络  

在录制时限制网络：  

1.  打开" **捕获设置"** 菜单。  导航到["显示录制设置"。](#show-recording-settings)  
1.  将 **"** 网络"设置为所需的限制级别。  
    
### <a name="throttle-the-cpu-while-recording"></a>在录制时限制 CPU  

在录制时限制 CPU：  

1.  打开" **捕获设置"** 菜单。  导航到["显示录制设置"。](#show-recording-settings)  
1.  将 **CPU** 设置为所需的限制级别。  
    
限制与计算机的功能相关。  例如， **速度较慢的 2 倍** 选项使 CPU 运行速度比正常速度慢 2 倍。  DevTools 不会真正模拟移动设备的 CPU，因为移动设备的体系结构与台式机和笔记本电脑的体系结构完全不同。  

### <a name="turn-on-advanced-paint-instrumentation"></a>打开高级画图检测  

查看详细的画图检测：  

1.  打开" **捕获设置"** 菜单。  导航到["显示录制设置"。](#show-recording-settings)  
1.  选中" **启用高级画图检测 (慢速) ** 复选框。  

若要了解如何与画图信息进行交互，请[导航到"](#view-layers-information)查看图层"和"[查看画图探查器"。](#view-paint-profiler)  

## <a name="save-a-recording"></a>保存录制  

若要保存录制，请打开上下文菜单 \ (右键单击\) ，然后选择"保存**配置文件"。**  

:::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-save-profile.msft.png" alt-text="保存配置文件" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-save-profile.msft.png":::
   **保存配置文件**  
:::image-end:::  

## <a name="load-a-recording"></a>加载录制  

若要加载录制，请打开上下文菜单 \ (右键单击\) ，然后选择加载 **配置文件**。  

:::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-load-profile.msft.png" alt-text="加载配置文件" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-load-profile.msft.png":::
   **加载配置文件**  
:::image-end:::  

## <a name="clear-the-previous-recording"></a>清除上一个录制  

录制后，**选择"清除**录制 \ (清除录制"图标 \) 以从"性能"面板 ![ ](../media/clear-recording-icon.msft.png) 中清除**** 该录制。  

:::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-clear-button.msft.png" alt-text="清除录制" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-clear-button.msft.png":::
   **清除录制**  
:::image-end:::  

## <a name="analyze-a-performance-recording"></a>分析性能记录  

记录[运行时性能或](#record-runtime-performance)[记录加载性能](#record-load-performance)后，性能面板**** 会提供许多数据，用于分析刚发生的情况的性能。  

### <a name="select-a-portion-of-a-recording"></a>选择录音的一部分  

将鼠标向左或向右拖动到 **"** 概述"中，选择录音的一部分。  概述**是**包含**FPS、CPU**和******NET**图表的部分。  

:::image type="complex" source="../media/evaluate-performance-performance-zoom-highlighted.msft.png" alt-text="将鼠标拖动到概述中以缩放" lightbox="../media/evaluate-performance-performance-zoom-highlighted.msft.png":::
   将鼠标拖动到 **概述中** 以缩放  
:::image-end:::  

若要使用键盘选择部分：  

1.  选择"**主"部分**或它旁边的任何部分的背景，例如"**交互****"、"网络**"或 **"GPU"。**  此键盘工作流仅在这些部分之一成为焦点时有效。  
1.  分别 `W` 使用 `A` 、键 `S` `D` 进行放大、向左移动、缩小和向右移动。  

若要使用跟踪板选择部分，请完成以下操作。  

1.  将鼠标悬停在"概述 **"部分** 或" **详细信息"部分** 上。  "**概述**"部分是包含**FPS、CPU****** 和**NET**图表的区域。  " **详细信息** "部分是包含 **"** 主"部分、" **交互"** 部分等的区域。  
1.  使用两根手指向上轻扫以缩小，向左轻扫向左移动，向下轻扫可放大，向右轻扫可向右移动。  

若要在"主"部分或任何元素**** 中滚动长形图表，请选择并按住，同时向上和向下拖动。  向左和向右拖动以移动所选录音的哪一部分。  

### <a name="search-activities"></a>搜索活动  

选择 `Control` + `F` \ (Windows、Linux\) 或 `Command` + `F` \ (macOS\) **** 打开"性能"面板底部的搜索框。  

:::image type="complex" source="../media/evaluate-performance-performance-search-regex.msft.png" alt-text="搜索框" lightbox="../media/evaluate-performance-performance-search-regex.msft.png":::
   搜索框  
:::image-end:::  

导航与查询匹配的活动：  

*   使用上 **一** 个 \ (![ ](../media/previous-icon.msft.png) \) **和 下** 一个 \ (![ ](../media/next-icon.msft.png) \) 按钮。  
*   选择 `Shift` + `Enter` 以选择上一个或 `Enter` 选择下一个。  

修改查询设置：  

*   选择 **"区分大小写** \ (![ 区分大小写 ](../media/search-case-icon.msft.png) \) "使查询区分大小写。  
*   Choose **Regex** \ (![ Regex ](../media/search-regex-icon.msft.png) \) to use a regular expression in your query.  

若要隐藏搜索框，请选择"取消 **"。**  

### <a name="view-main-thread-activity"></a>查看主线程活动  

使用 **"主** "部分查看页面主线程上发生的活动。  

:::image type="complex" source="../media/evaluate-performance-performance-main-zoomed.msft.png" alt-text="主要部分" lightbox="../media/evaluate-performance-performance-main-zoomed.msft.png":::
   **主要**部分  
:::image-end:::  

在"摘要"面板中选择一个事件以查看其 **详细信息** 。  DevTools 概述了选定的事件。  

:::image type="complex" source="../media/evaluate-performance-performance-summary-me.msft.png" alt-text="有关"摘要"面板中的匿名函数详细信息" lightbox="../media/evaluate-performance-performance-summary-me.msft.png":::
   有关"摘要 `anonymous` "面板中的 **函数** 详细信息  
:::image-end:::  

DevTools 表示包含图表的主线程活动。  x 轴表示一段时间的录制。  Y 轴表示调用堆叠。  顶部的事件会导致其下方的事件。  

:::image type="complex" source="../media/evaluate-performance-performance-main-flame-chart.msft.png" alt-text="柱形图" lightbox="../media/evaluate-performance-performance-main-flame-chart.msft.png":::
   柱形图  
:::image-end:::  

在上图中，事件导致 第 `click` `Function Call` `activitytabs.js` 53 行中的 。  在下面 `Function Call` ，查看匿名函数已运行。  匿名函数请求 `a` ，它请求 `wait` ，它请求 `Minor GC` 。  

DevTools 分配脚本随机颜色。  在上图中，来自一个脚本的函数请求为浅绿色。  来自另一个脚本的请求是彩色的。  深黄色表示脚本活动，紫色事件表示呈现活动。  这些较深的黄色和紫色事件在所有录制中都是一致的。  

如果要隐藏 [JavaScript](#disable-javascript-samples) 请求的详细隐藏图表，请导航到"禁用 JavaScript 示例"。  禁用 JS 示例后，只显示上图中的和 `Event: choose` `Function Call` 等高级 `str` 事件。  

### <a name="view-activities-in-a-table"></a>查看表中的活动  

录制页面后，无需仅依赖 **Main** 部分来分析活动。  DevTools 还提供了三种表格视图，用于分析活动。  每个视图都提供对活动的不同视角：  

*   当要查看导致工作最多的根活动时，请使用" [呼叫树"](#the-call-tree-panel) 面板。  
*   当要查看直接花费时间最多的活动时，请使用 ["底部向上](#the-bottom-up-panel) "面板。  
*   当您想要按记录期间活动发生的顺序查看活动时，请使用"事件 [日志"](#the-event-log-panel) 面板。  
    
> [!NOTE]
> 接下来的三个部分都指同一演示。  在"活动选项卡演示 ["中，自己运行演示][ActivityTabsDemo]。  

#### <a name="root-activities"></a>根活动  

下面是"呼叫树"面板****、"底部向上"面板和"**** 事件日志"面板**** 中提及的根活动**概念**的说明。  

根活动是导致浏览器执行某些工作的活动。  例如，当您选择一个网页时，浏览器 `Event` 将运行一个活动作为根活动。  `Event`这可能会导致处理程序运行，等等。  

在主节的 **绘制图中，** 根活动位于图表顶部。  在 **"呼叫树** "和" **事件日志** "面板中，根活动是顶级项目。  

导航到" [呼叫树](#the-call-tree-panel) "面板，查看根活动的示例。  

#### <a name="the-call-tree-panel"></a>呼叫树面板  

使用 **"呼叫树** "面板查看 [哪些根活动](#root-activities) 导致工作最多。  

" **呼叫树** "面板仅显示在录制的选定部分期间的活动。  导航 [到"选择录音的一部分](#select-a-portion-of-a-recording) "，了解如何选择部分。  

:::image type="complex" source="../media/evaluate-performance-performance-call-tree.msft.png" alt-text="呼叫树面板" lightbox="../media/evaluate-performance-performance-call-tree.msft.png":::
   呼叫 **树** 面板  
:::image-end:::  

在上图中，"活动"列中的顶级项目（如**** 和 `Evaluate Script` `Parse HTML` ）是根活动。  嵌套表示调用堆栈。  例如，在上图中 `Parse HTML` ，它导致了 和 `Evaluate Script` `Compile Script` `(anonymous)` 。  

**Self Time** 表示直接在活动上花费的时间。  **"总** 时间"表示该活动或任何子活动所花费的时间。  

选择 **"自时间****"、"总**时间 **"或"活动**"按该列对表进行排序。  

使用 **"筛选器** "文本框按活动名称筛选事件。  

默认情况下 **，"分组"** 菜单设置为"**无分组"。**  使用 **"分组"** 菜单根据各种条件对活动表进行排序。  

Choose **Show Heaviest Stack** \ (Show ![ Heaviest Stack ](../media/show-heaviest-stack-icon.msft.png) \) to reveal another table to the right of the **Activity** table.  选择一个活动以填充 **最重的 Stack** 表。  The **Heaviest Stack** table displays which children of the selected activity took the longest time to run.  

#### <a name="the-bottom-up-panel"></a>"Bottom-Up面板  

使用 **"底部向上"** 面板查看哪些活动在聚合中直接时间最多。  

The **Bottom-Up** panel only displays activities during the selected portion of the recording.  导航 [到"选择录音的一部分](#select-a-portion-of-a-recording) "，了解如何选择部分。  

:::image type="complex" source="../media/evaluate-performance-performance-bottoms-up.msft.png" alt-text=""Bottom-Up面板" lightbox="../media/evaluate-performance-performance-bottoms-up.msft.png":::
   从**下向上面板**  
:::image-end:::  

在上 **图** 的主节绘制图中，导航到几乎所有运行所花的时间 `Parse HTML` 。  上图的 **"底部向上"** 面板中的顶部活动是 `Parse HTML` 。  <!--In the flame chart of the previous figure, the yellow below the calls to `wait` are actually thousands of `Minor GC` calls.  -->  导航到 **"底部向上"面板** ，下一个成本最大的活动是 `Layout` 。  

" **自时间** "列表示直接在活动（在所有事件之间）花费的聚合时间。  

" **总时间** "列表示该活动或任何子活动所花费的聚合时间。  

#### <a name="the-event-log-panel"></a>"事件日志"面板  

使用 **"事件** 日志"面板以记录期间活动发生的顺序查看活动。  

" **事件日志** "面板仅显示在记录的选定部分期间的活动。  导航 [到"选择录音的一部分](#select-a-portion-of-a-recording) "，了解如何选择部分。  

:::image type="complex" source="../media/evaluate-performance-performance-event-log.msft.png" alt-text=""事件日志"面板" lightbox="../media/evaluate-performance-performance-event-log.msft.png":::
   " **事件日志"** 面板  
:::image-end:::  

" **开始时间** "列表示该活动的开始点（相对于录制的开始位置）。  例如，上图中选定项目的开始时间意味着活动在 `175.7 ms` 录制开始后 175.7 毫秒开始。  

" **自时间** "列表示直接在活动上花费的时间。  

" **总时间** "列表示直接用于该活动或任何子活动的时间。  

选择 **"开始时间"、"** 开始时间"**或"** 总时间"按该列对表进行排序。 ****

使用" **筛选器** "文本框按名称筛选活动。  

使用" **持续时间** "菜单筛选出时间少于 1 毫秒或 15 毫秒的任何活动。  默认情况下 **，"持续时间"** 菜单设置为 **"** 全部"，这意味着将显示所有活动。  

禁用 **"加载**、**脚本、** 呈现**** 或**绘制**"复选框以筛选掉这些类别中的所有活动。  

### <a name="view-gpu-activity"></a>查看 GPU 活动  

在 GPU 部分查看 **GPU** 活动。  

:::image type="complex" source="../media/evaluate-performance-performance-gpu-zoomed.msft.png" alt-text="GPU 部分" lightbox="../media/evaluate-performance-performance-gpu-zoomed.msft.png":::
   **GPU**部分  
:::image-end:::  

### <a name="view-raster-activity"></a>查看栅格活动  

查看 **"Raster"部分中的"Raster"** 活动。  

:::image type="complex" source="../media/evaluate-performance-performance-raster.msft.png" alt-text=""Raster"部分" lightbox="../media/evaluate-performance-performance-raster.msft.png":::
   **"Raster"** 部分  
:::image-end:::  

### <a name="view-interactions"></a>查看交互  

使用 **"交互"** 部分查找和分析在录制过程中发生的用户交互。  

:::image type="complex" source="../media/evaluate-performance-performance-interactions-animation.msft.png" alt-text=""交互"部分" lightbox="../media/evaluate-performance-performance-interactions-animation.msft.png":::
   " **交互"** 部分  
:::image-end:::  

交互底部的红线表示等待主线程所花的时间。  

在"摘要"面板中选择一个交互以查看其 **详细信息** 。  

### <a name="analyze-frames-per-second-fps"></a>分析每秒帧数 (FPS)   

DevTools 提供了多种分析每秒帧的方法：  

*   使用 [FPS 图表](#the-fps-chart) 获取录制持续时间内 FPS 的概述。  
*   使用 ["框架"](#the-frames-section) 部分查看特定帧所间隔的时间。  
*   在页面 **运行时，使用 FPS** 指示器实时估计 FPS。  导航到 [使用 FPS 指示器实时查看每秒帧数](#view-frames-per-second-in-realtime-with-the-fps-meter)。  
    
#### <a name="the-fps-chart"></a>FPS 图表  

**FPS**图表概述了录音持续时间中的帧速率。  通常，绿色条形越高，帧速率越好。  

FPS 图表上方**** 的红色条是一条警告，指出帧速率下降得过低，可能损害用户体验。  

:::image type="complex" source="../media/evaluate-performance-performance-fps-highlight.msft.png" alt-text="FPS 图表" lightbox="../media/evaluate-performance-performance-fps-highlight.msft.png":::
   **FPS** 图表  
:::image-end:::  

#### <a name="the-frames-section"></a>框架部分  

帧 **部分** 会告知你特定帧所使用时间。  

将鼠标悬停在框架上，查看工具提示，详细了解它。  

:::image type="complex" source="../media/evaluate-performance-performance-frames-hover.msft.png" alt-text="鼠标悬停在框架上" lightbox="../media/evaluate-performance-performance-frames-hover.msft.png":::
   鼠标悬停在框架上  
:::image-end:::  

在摘要面板中选择一个帧以查看有关 **帧详细信息** 。  DevTools 将所选框架分级为蓝色。  

:::image type="complex" source="../media/evaluate-performance-performance-frames-summary.msft.png" alt-text="在摘要面板中查看帧" lightbox="../media/evaluate-performance-performance-frames-summary.msft.png":::
   在摘要面板 **中查看** 帧  
:::image-end:::  

### <a name="view-network-requests"></a>查看网络请求  

展开 **"网络** "部分以查看记录期间发生的网络请求的瀑布。  

:::image type="complex" source="../media/evaluate-performance-performance-network.msft.png" alt-text=""网络"部分" lightbox="../media/evaluate-performance-performance-network.msft.png":::
   " **网络"** 部分  
:::image-end:::  

请求按如下方式进行颜色编码：  

*   HTML：蓝色  
*   CSS：紫色  
*   JS：Yellow  
*   图像：绿色  
    
在"摘要"面板中选择一个请求以查看其 **详细信息** 。  例如，在上图中，"摘要"**** 面板显示有关在"网络"部分选择的蓝色**请求详细信息。**  

请求左上方的深蓝色正方形表示它是优先级较高的请求。  浅蓝色正方形表示较低的优先级。  例如，在上图中，蓝色选定请求的优先级更高，而其下方的绿色请求优先级较低。  

在下图的第 1 部分中，请求表示为 左侧的行、中间带深色部分的条形和浅色部分，以及右边的 `www.bing.com` 线条。  在下图的第 2 个中，显示了"网络"工具的"计时"**** 面板中相同请求的相应**表示**形式。  下面说明这两种表示形式如何相互映射：

*   左边行是事件组 `Connection Start` （包括这组事件）的所有内容。  换句话说，它是之前的所有内容， `Request Sent` 不包括 。  
*   栏的光线部分为 `Request Sent` 和 `Waiting (TTFB)` 。  
*   该栏的深色部分是 `Content Download` 。  
*   正确的行实质上是等待主线程所花的时间。  "计时"面板中未 **显示** 此行为。  
    
:::row:::
   :::column span="":::
      :::image type="complex" source="../media/evaluate-performance-bing-performance-network.msft.png" alt-text="请求的线 www.bing.com 表示" lightbox="../media/evaluate-performance-bing-performance-network.msft.png":::
         请求的线栏 `www.bing.com` 表示形式  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/evaluate-performance-bing-network-timing.msft.png" alt-text="网络工具" lightbox="../media/evaluate-performance-bing-network-timing.msft.png":::
         网络**工具**  
： ：：image-end：：：  
   :::column-end:::
:::row-end:::

### <a name="view-memory-metrics"></a>查看内存指标  

打开" **内存"** 复选框以查看上一次录制中的内存指标。  

:::image type="complex" source="../media/evaluate-performance-performance-memory-highlight.msft.png" alt-text=""内存"复选框" lightbox="../media/evaluate-performance-performance-memory-highlight.msft.png":::
   " **内存"** 复选框  
:::image-end:::  

DevTools 在摘要 **面板** 上方显示新的 **内存** 图表。  NET 图表下方还有一**个新的图表，** 称为**HEAP。**  **HEAP**图表提供的信息与"内存"图表中**的 JS 堆****行相同**。  

:::image type="complex" source="../media/evaluate-performance-performance-memory-chart.msft.png" alt-text="内存指标" lightbox="../media/evaluate-performance-performance-memory-chart.msft.png":::
   内存指标  
:::image-end:::  

图表上的彩色线条映射到图表上方的彩色复选框。  
禁用复选框以在图表中隐藏该类别。  

该图表仅显示当前选中的录制区域。  例如，在上图中，"内存"**** 图表只显示从 400 毫秒标记到 1750 毫秒标记周围的内存使用量。  

### <a name="view-the-duration-of-a-portion-of-a-recording"></a>查看录制的一部分的持续时间  

分析网络或**主****等**部分时，有时你需要更精确地估计特定事件所经过的。  按住 `Shift` 、选择并按住，然后向左或向右拖动以选择录音的一部分。  在选择的底部，DevTools 显示该部分所用时间。  

:::image type="complex" source="../media/evaluate-performance-performance-main-duration.msft.png" alt-text="查看录制的一部分的持续时间" lightbox="../media/evaluate-performance-performance-main-duration.msft.png":::
   查看录制的一部分的持续时间  
:::image-end:::  

### <a name="view-a-screenshot"></a>查看屏幕截图  

导航到 [录制时捕获](#capture-screenshots-while-recording) 屏幕截图，了解如何打开屏幕截图。  

将鼠标 **悬停在"概述** "上可查看该页面在录制期间的外观的屏幕截图。  概述**是**包含 CPU、FPS**** 和**** **NET**图表的部分。  

:::image type="complex" source="../media/evaluate-performance-performance-screenshots-hover.msft.png" alt-text="查看屏幕截图" lightbox="../media/evaluate-performance-performance-screenshots-hover.msft.png":::
   查看屏幕截图  
:::image-end:::  

您还可以通过选择"框架"部分中的图文 **框** 来查看屏幕截图。  DevTools 在摘要面板中显示屏幕截图 **的小** 版本。  

:::image type="complex" source="../media/evaluate-performance-performance-summary-preview.msft.png" alt-text="在摘要面板中查看屏幕截图" lightbox="../media/evaluate-performance-performance-summary-preview.msft.png":::
   在摘要面板**中查看屏幕截图**  
:::image-end:::  

在"摘要" **面板中选择缩略图** 以放大屏幕截图。  

:::image type="complex" source="../media/evaluate-performance-performance-summary-preview-select.msft.png" alt-text="从摘要面板放大屏幕截图" lightbox="../media/evaluate-performance-performance-summary-preview-select.msft.png":::
   从摘要面板放大**屏幕截图**  
:::image-end:::  

### <a name="view-layers-information"></a>查看图层信息  

查看有关帧的高级层信息：  

1.  [打开高级画图检测](#turn-on-advanced-paint-instrumentation)。  
1.  选择"框架" **部分中的** 框架。  DevTools 在"事件日志"面板旁**** 的新"层"面板中显示有关**图层**的信息。  
    
    :::image type="complex" source="../media/evaluate-performance-layers-all.msft.png" alt-text=""层"窗格" lightbox="../media/evaluate-performance-layers-all.msft.png":::
       " **层"** 窗格  
    :::image-end:::  
    
将鼠标悬停在图层上以在图表中突出显示它。  

:::image type="complex" source="../media/evaluate-performance-performance-frames-document-nav-bar-highlighted.msft.png" alt-text="突出显示图层" lightbox="../media/evaluate-performance-performance-frames-document-nav-bar-highlighted.msft.png":::
   突出显示图层  
:::image-end:::  

移动图表：  

*   选择 **平移模式** \ (![ 平移模式 ](../media/pan-mode-icon.msft.png) \) 沿 X 和 Y 轴移动。  
*   选择 **旋转模式** \ (![ 旋转模式 ](../media/rotate-mode-icon.msft.png) \) 沿 Z 轴旋转。  
*   Choose **Reset Transform** \ (Reset Transform ![ ](../media/reset-transform-icon.msft.png) \) to reset the diagram to the original position.  
    
### <a name="view-paint-profiler"></a>查看画图探查器  

查看有关绘制事件的高级信息：  

1.  [打开 。](#turn-on-advanced-paint-instrumentation)  
1.  在" **主"** 部分选择 **"绘制"** 事件。  
    
    :::image type="complex" source="../media/evaluate-performance-paint-profiler.msft.png" alt-text="画图探查器面板" lightbox="../media/evaluate-performance-paint-profiler.msft.png":::
       画 **图探查器** 面板  
    :::image-end:::  
    
## <a name="analyze-rendering-performance-with-the-rendering-tool"></a>使用呈现工具分析呈现性能  

使用"呈现" **面板的功能** 帮助可视化页面的呈现性能。  

打开呈现 **工具** ：  

1.  [打开命令菜单][DevToolsCommandMenu]。  
1.  开始键入并选择 `Rendering` `Show Rendering` 。  DevTools **在** DevTools 窗口底部显示呈现工具。  
    
    :::image type="complex" source="../media/evaluate-performance-console-drawer-rendering.msft.png" alt-text="呈现工具" lightbox="../media/evaluate-performance-console-drawer-rendering.msft.png":::
       **呈现**工具  
    :::image-end:::  
    
### <a name="view-frames-per-second-in-realtime-with-the-fps-meter"></a>使用 FPS 指示器实时查看每秒帧数  

**FPS 指示器**是显示在视口右上角的覆盖层。  它在页面运行时提供 FPS 实时估计值。  打开 **FPS 指示器**：  

1.  打开 **呈现工具** 。  [使用呈现工具 分析呈现性能](#analyze-rendering-performance-with-the-rendering-tool)。  
1.  打开 **"FPS 指示器"** 复选框。  
    
    :::image type="complex" source="../media/evaluate-performance-jank-console-rendering-frame-rate.msft.png" alt-text="FPS 计数" lightbox="../media/evaluate-performance-jank-console-rendering-frame-rate.msft.png":::
       **FPS 计数**  
    :::image-end:::  
    
### <a name="view-painting-events-in-realtime-with-paint-flashing"></a>使用画图闪烁实时查看绘制事件  

使用画图闪烁获取页面上所有绘制事件实时视图。  只要重新绘制页面的一部分，DevTools 就会用绿色概括该部分。  

若要打开画图闪烁，请完成以下操作。  

1.  打开 **呈现工具** 。  导航到 [使用呈现工具 分析呈现性能](#analyze-rendering-performance-with-the-rendering-tool)。  
1.  打开" **画图闪烁"** 复选框。  
    
    :::image type="complex" source="../media/evaluate-performance-jank-console-rendering-paint-flashing.msft.png" alt-text="画图闪烁" lightbox="../media/evaluate-performance-jank-console-rendering-paint-flashing.msft.png":::
       **画图闪烁**  
    :::image-end:::  
    
### <a name="view-an-overlay-of-layers-with-layer-borders"></a>使用图层边框查看图层的覆盖  

使用 **图层边框** 查看页面顶部的图层边框和磁贴的覆盖。  

若要打开"层边框"，请完成以下操作：  

1.  打开 **呈现工具** 。  导航到 [使用呈现工具 分析呈现性能](#analyze-rendering-performance-with-the-rendering-tool)。  
1.  打开" **图层边框"** 复选框。  
    
    :::image type="complex" source="../media/evaluate-performance-devtools-console-rendering-layer-borders.msft.png" alt-text="层边框" lightbox="../media/evaluate-performance-devtools-console-rendering-layer-borders.msft.png":::
       **层边框**  
    :::image-end:::  
    
导航到 [debug_colors.cc][ChromiumDebugColors] 中的注释，了解颜色编码的说明。  

### <a name="find-scroll-performance-issues-in-realtime"></a>实时查找滚动性能问题  

使用滚动性能问题可标识具有与滚动相关的事件侦听器的页面元素，这些元素可能会损害页面的性能。  
DevTools 以青色概述了可能存在问题的元素。  

若要查看滚动性能问题，请完成以下操作。 

1.  打开 **呈现工具** 。  导航到 [使用呈现工具 分析呈现性能](#analyze-rendering-performance-with-the-rendering-tool)。  
1.  打开" **滚动性能问题"** 复选框。  
    
    :::image type="complex" source="../media/evaluate-performance-bing-console-drawer-rendering-scrolling-performance-issues.msft.png" alt-text="滚动性能问题指示非层视口约束的对象可能会损害滚动性能" lightbox="../media/evaluate-performance-bing-console-drawer-rendering-scrolling-performance-issues.msft.png":::
       **滚动性能问题** 指示非层视口约束的对象可能会损害滚动性能  
    :::image-end:::  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge 开发工具团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 开发人员工具|Microsoft Docs"  
[DevToolsCommandMenu]: ../command-menu/index.md#open-the-command-menu "打开"命令菜单 - 使用 Microsoft Edge DevTools 命令菜单"菜单运行|Microsoft Docs"  
[DevtoolsEvaluatePerformanceGettingStarted]: ./index.md "开始分析运行时性能|Microsoft Docs"  

[ActivityTabsDemo]: https://microsoft-edge-chromium-devtools.glitch.me/perf/activitytabs.html "活动选项卡演示|小故障"  

[ChromiumDebugColors]: https://cs.chromium.org/chromium/src/cc/debug/debug_colors.cc "debug_colors.cc - 代码搜索"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/reference)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
