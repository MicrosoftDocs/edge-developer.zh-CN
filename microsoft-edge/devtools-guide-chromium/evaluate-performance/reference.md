---
description: 有关在 Microsoft Edge DevTools 中记录和分析性能的所有方法的参考。
title: 性能分析引用
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: 181bc05fffbaef6a06bebcc5cb9ccfcc8e7de498
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398803"
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

此页面全面引用了与分析性能相关的 Microsoft Edge DevTools 功能。  

导航到 ["分析][DevtoolsEvaluatePerformanceGettingStarted] 运行时性能入门"，了解如何使用 [Microsoft Edge DevTools][MicrosoftEdgeDevTools]分析页面性能的指南教程。  

## <a name="record-performance"></a>记录性能  

### <a name="record-runtime-performance"></a>记录运行时性能  

在页面运行时运行时性能（而不是加载）时，记录运行时性能。  

1.  导航到要分析的页面。  
1.  在 DevTools **中打开** 性能工具。  
1.  Choose **Record** \ (![ Record icon ][ImageRecordIcon] \) .  
    
    :::image type="complex" source="../media/evaluate-performance-performance-record-highlight.msft.png" alt-text="记录" lightbox="../media/evaluate-performance-performance-record-highlight.msft.png":::
       **记录**  
    :::image-end:::  
    
1.  与页面交互。  DevTools 记录交互后发生的所有页面活动。  
1.  再次 **选择** "录制"或" **停止** "以停止录制。  
    
### <a name="record-load-performance"></a>记录加载性能  

在页面加载时（而不是运行时）要分析其性能时记录加载性能。  

1.  导航到要分析的页面。  
1.  打开 **DevTools** 的性能面板。  
1.  Choose **Refresh page** \ (Refresh Page ![ ][ImageRefreshPageIcon] \) .  DevTools 在页面刷新时记录性能指标，然后在加载完成后几秒钟自动停止录制。  
    
    :::image type="complex" source="../media/evaluate-performance-performance-refresh-button.msft.png" alt-text="刷新页面" lightbox="../media/evaluate-performance-performance-refresh-button.msft.png":::
       **刷新页面**  
    :::image-end:::  
    
DevTools 会自动放大大部分活动发生的记录部分。  

:::image type="complex" source="../media/evaluate-performance-performance-refreshed.msft.png" alt-text="页面加载录制" lightbox="../media/evaluate-performance-performance-refreshed.msft.png":::
   页面加载录制  
:::image-end:::  

### <a name="capture-screenshots-while-recording"></a>录制时捕获屏幕截图  

打开" **屏幕截图"** 复选框，在录制时捕获每个帧的屏幕截图。  

:::image type="complex" source="../media/evaluate-performance-performance-capture-screenshots-checkbox.msft.png" alt-text=""屏幕截图"复选框" lightbox="../media/evaluate-performance-performance-capture-screenshots-checkbox.msft.png":::
   " **屏幕截图"** 复选框  
:::image-end:::  

导航 [到"查看屏幕截图](#view-a-screenshot) "，了解如何与屏幕截图进行交互。  

### <a name="force-garbage-collection-while-recording"></a>在记录时强制进行垃圾回收  

录制页面时， **选择"收集** 垃圾 \ (收集垃圾图标 ![ ][ImageCollectGarbageIcon] \) 强制进行垃圾回收。  

:::image type="complex" source="../media/evaluate-performance-performance-collect-garbage-button.msft.png" alt-text="收集垃圾" lightbox="../media/evaluate-performance-performance-collect-garbage-button.msft.png":::
   收集垃圾  
:::image-end:::  

### <a name="show-recording-settings"></a>显示录制设置  

Choose **Capture settings** \ (Capture settings ![ ][ImageCaptureSettingsIcon] \) to expose more settings related to how DevTools captures performance recordings.  

:::image type="complex" source="../media/evaluate-performance-performance-capture-settings-button-open-drawer.msft.png" alt-text=""捕获设置"部分" lightbox="../media/evaluate-performance-performance-capture-settings-button-open-drawer.msft.png":::
   " **捕获设置"** 部分  
:::image-end:::  

### <a name="disable-javascript-samples"></a>禁用 JavaScript 示例  

默认情况下，录制 **的 Main** 部分显示录制期间调用的 JavaScript 函数的详细调用堆栈。  若要禁用这些调用堆栈，  

1.  打开 **"捕获设置"** 菜单。  导航到["显示录制设置"。](#show-recording-settings)  
1.  打开" **禁用 JavaScript 示例"** 复选框。  
1.  录制页面。  
    
以下 2 个图显示禁用和启用 JavaScript 示例的区别。  禁用 **采样** 时，录制的主节要短得多，因为它省略所有 JavaScript 调用堆栈。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-on.msft.png" alt-text="禁用 JS 示例时录制的示例" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-on.msft.png":::
         禁用 JS 示例时录制的示例  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off.msft.png" alt-text="打开 JS 示例时录制的示例" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off.msft.png":::
         打开 JS 示例时录制的示例  
      :::image-end:::  
   :::column-end:::
:::row-end:::

### <a name="throttle-the-network-while-recording"></a>在录制时限制网络  

若要在录制时限制网络，  

1.  打开 **"捕获设置"** 菜单。  导航到["显示录制设置"。](#show-recording-settings)  
1.  将 **网络** 设置为所需的限制级别。  
    
### <a name="throttle-the-cpu-while-recording"></a>在录制时限制 CPU  

若要在录制时限制 CPU：  

1.  打开 **"捕获设置"** 菜单。  导航到["显示录制设置"。](#show-recording-settings)  
1.  将 **CPU** 设置为所需的限制级别。  
    
限制与计算机的功能相关。  例如 **，2 倍** 减速选项使 CPU 的运行速度比正常速度慢 2 倍。  DevTools 不会真正模拟移动设备的 CPU，因为移动设备的体系结构与台式机和笔记本电脑的体系结构大为不同。  

### <a name="turn-on-advanced-paint-instrumentation"></a>打开高级绘制检测  

若要查看详细的绘制检测，请：  

1.  打开 **"捕获设置"** 菜单。  导航到["显示录制设置"。](#show-recording-settings)  
1.  选中" **启用高级绘制检测 (慢速) ** 复选框。  

若要了解如何与绘制信息进行交互，请导航到["查看图层"和](#view-layers-information)"[查看绘制探查器"。](#view-paint-profiler)  

## <a name="save-a-recording"></a>保存录制  

若要保存录制，请打开上下文菜单 \ (右键单击\) ，然后选择"保存**配置文件"。**  

:::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-save-profile.msft.png" alt-text="保存配置文件" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-save-profile.msft.png":::
   **保存配置文件**  
:::image-end:::  

## <a name="load-a-recording"></a>加载录制  

若要加载录制，请打开上下文菜单 \ (右键单击\) ，然后选择"加载**配置文件"。**  

:::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-load-profile.msft.png" alt-text="加载配置文件" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-load-profile.msft.png":::
   **加载配置文件**  
:::image-end:::  

## <a name="clear-the-previous-recording"></a>清除上一录制  

录制后，**选择"清除**录制" ("清除录制"图标 \) 以从"性能"面板中 ![ ][ImageClearRecordingIcon] 清除该录制****。  

:::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-clear-button.msft.png" alt-text="清除录制" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-clear-button.msft.png":::
   **清除录制**  
:::image-end:::  

## <a name="analyze-a-performance-recording"></a>分析性能记录  

记录[运行时性能](#record-runtime-performance)或[记录加载性能](#record-load-performance)后，性能面板**** 会提供大量数据，用于分析刚发生的情况的性能。  

### <a name="select-a-portion-of-a-recording"></a>选择录音的一部分  

将鼠标向左或向右拖动到 **"概述** "中，选择录音的一部分。  概述**是**包含**FPS、CPU**和******NET**图表的部分。  

:::image type="complex" source="../media/evaluate-performance-performance-zoom-highlighted.msft.png" alt-text="将鼠标拖动到"概述"中以缩放" lightbox="../media/evaluate-performance-performance-zoom-highlighted.msft.png":::
   将鼠标拖动到 **"概述"中** 以缩放  
:::image-end:::  

若要使用键盘选择部分，  

1.  选择主节的背景或**** 它旁边的任何部分，如**交互、****网络**或**GPU。**  此键盘工作流仅在其中一个部分聚焦时有效。  
1.  分别使用 ， 、 键进行放大、向左移动、缩小 `W` `A` `S` `D` 和向右移动。  

若要使用跟踪板选择部分，请完成以下操作。  

1.  将鼠标悬停在 **"** 概述"部分或" **详细信息"部分** 上。  "**概述**"部分包含**FPS、CPU**和**** **NET**图表。  "**详细信息**"部分是包含"主"**** 部分、"交互 **"** 部分等的区域。  
1.  使用两根手指向上轻扫以缩小，向左轻扫向左移动，向下轻扫可放大，向右轻扫向右移动。  

若要在主节或任何元素中滚动**** 长饼图，请选择并按住，同时向上和向下拖动。  向左和向右拖动以移动所选录制部分。  

### <a name="search-activities"></a>搜索活动  

选择 `Control` + `F` \ (Windows、Linux\) 或 `Command` + `F` \ (macOS\) **** 打开"性能"面板底部的搜索框。  

:::image type="complex" source="../media/evaluate-performance-performance-search-regex.msft.png" alt-text="搜索框" lightbox="../media/evaluate-performance-performance-search-regex.msft.png":::
   搜索框  
:::image-end:::  

若要导航与查询匹配的活动：  

*   使用上 **一** 个 \ (![ ][ImagePreviousIcon] \) **下** 一个 \ (![ ][ImageNextIcon] \) 按钮。  
*   选择 `Shift` + `Enter` 以选择上一个或 `Enter` 选择下一个。  

要修改查询设置，请执行：  

*   选择 **区分大小写** \ (![ 区分大小写 ][ImageSearchCaseIcon] \) 使查询区分大小写。  
*   Choose **Regex** \ (![ Regex ][ImageSearchRegexIcon] \) to use a regular expression in your query.  

若要隐藏搜索框，请选择"取消 **"。**  

### <a name="view-main-thread-activity"></a>查看主线程活动  

使用 **"主** "部分可查看页面主线程上发生的活动。  

:::image type="complex" source="../media/evaluate-performance-performance-main-zoomed.msft.png" alt-text="主要部分" lightbox="../media/evaluate-performance-performance-main-zoomed.msft.png":::
   **主要**部分  
:::image-end:::  

选择事件以查看"摘要"面板中有关 **它的信息** 。  DevTools 概述了所选事件。  

:::image type="complex" source="../media/evaluate-performance-performance-summary-me.msft.png" alt-text="有关"摘要"面板中的匿名函数详细信息" lightbox="../media/evaluate-performance-performance-summary-me.msft.png":::
   有关"摘要 `anonymous` "面板中函数**** 详细信息  
:::image-end:::  

DevTools 表示包含图表的主线程活动。  x 轴表示一段时间的录制。  Y 轴表示调用堆叠。  顶部的事件会导致其下方的事件。  

:::image type="complex" source="../media/evaluate-performance-performance-main-flame-chart.msft.png" alt-text="柱形图" lightbox="../media/evaluate-performance-performance-main-flame-chart.msft.png":::
   柱形图  
:::image-end:::  

在上图中， `click` 一个事件导致第 `Function Call` `activitytabs.js` 53 行中发生一个事件。  在下面 `Function Call` ，查看匿名函数已运行。  请求的匿名函数 `a` ，请求的 `wait` ，请求的 `Minor GC` 。  

DevTools 分配脚本随机颜色。  在上图中，来自一个脚本的函数请求的颜色为浅绿色。  来自另一个脚本的请求是彩色的浅色。  深黄色表示脚本活动，紫色事件表示呈现活动。  这些较深的黄色和紫色事件在所有录制中都是一致的。  

如果要 [隐藏 JavaScript](#disable-javascript-samples) 请求的详细图表，请导航到"禁用 JavaScript"示例。  禁用 JS 示例后，只显示上图等高级 `Event: choose` `Function Call` `str` 事件。  

### <a name="view-activities-in-a-table"></a>查看表中的活动  

录制页面后，无需仅依赖"主 **"部分来** 分析活动。  DevTools 还提供了三种表格式视图，用于分析活动。  每个视图都提供对活动的不同视角：  

*   当要查看导致工作最多的根活动时，请使用"呼叫树 ["](#the-call-tree-panel) 面板。  
*   当要查看直接花费时间最多的活动时，请使用" [下向上"](#the-bottom-up-panel) 面板。  
*   当您想要按记录期间活动发生的顺序查看活动时，请使用" [事件](#the-event-log-panel) 日志"面板。  
    
> [!NOTE]
> 接下来的三个部分均引用同一演示。  在活动选项卡 [演示中自己运行演示][ActivityTabsDemo]。  

#### <a name="root-activities"></a>根活动  

下面是"呼叫树"面板****、底部向上面板和事件日志面板**** 中提及的根活动******概念**的说明。  

根活动是导致浏览器执行某些工作的活动。  例如，当您选择网页时，浏览器将运行 `Event` 活动作为根活动。  `Event`这可能会导致处理程序运行，等等。  

在主节的图表上****，根活动位于图表的顶部。  在 **"呼叫树** "和" **事件日志** "面板中，根活动是顶级项目。  

导航到 ["呼叫树](#the-call-tree-panel) "面板，了解根活动示例。  

#### <a name="the-call-tree-panel"></a>呼叫树面板  

使用 **"呼叫树** "面板查看 [哪些根活动](#root-activities) 导致工作最多。  

呼叫 **树** 面板仅显示在录制的选定部分期间的活动。  导航 [到"选择录音的一部分](#select-a-portion-of-a-recording) "以了解如何选择部分。  

:::image type="complex" source="../media/evaluate-performance-performance-call-tree.msft.png" alt-text="呼叫树面板" lightbox="../media/evaluate-performance-performance-call-tree.msft.png":::
   呼叫 **树** 面板  
:::image-end:::  

在上图中，活动列中的顶级项目（如**** `Evaluate Script` 根 `Parse HTML` 活动）和根活动。  嵌套表示调用堆栈。  例如，在上图中 `Parse HTML` ，导致和 `Evaluate Script` `Compile Script` `(anonymous)` 的原因。  

**"自** 用时间"表示直接用于该活动的时间。  **总时间** 表示该活动或任何子项所花的时间。  

选择 **"自时间****"、"总**时间"或 **"活动**"按该列对表进行排序。  

使用 **"筛选器** "文本框按活动名称筛选事件。  

默认情况下，**分组菜单**设置为"**无分组"。**  使用 **"分组"** 菜单根据各种条件对活动表进行排序。  

Choose **Show Heaviest Stack** \ (Show ![ Heaviest Stack ][ImageShowHeaviestStackIcon] \) to reveal another table to the right of the **Activity** table.  选择一个活动以填充 **最重的 Stack** 表。  最 **重的 Stack** 表显示所选活动的哪些子项运行时间最长。  

#### <a name="the-bottom-up-panel"></a>Bottom-Up面板  

使用 **"从下向上"** 面板查看哪些活动直接在聚合中所花时间最多。  

底部 **向上面板** 仅显示在录制的选定部分期间的活动。  导航 [到"选择录音的一部分](#select-a-portion-of-a-recording) "以了解如何选择部分。  

:::image type="complex" source="../media/evaluate-performance-performance-bottoms-up.msft.png" alt-text="Bottom-Up面板" lightbox="../media/evaluate-performance-performance-bottoms-up.msft.png":::
   从**下向上面板**  
:::image-end:::  

在上 **图** 的"主节"图表上，导航到几乎花费运行的所有时间 `Parse HTML` 。  上图的 **"下** 向上"面板中的顶部活动是 `Parse HTML` 。  <!--In the flame chart of the previous figure, the yellow below the calls to `wait` are actually thousands of `Minor GC` calls.  -->  导航到 **"下向上"面板** ，下一个最昂贵的活动是 `Layout` 。  

" **自** 时间"列表示直接在活动（发生的所有事件）中花费的聚合时间。  

" **总时间** "列表示该活动或任何子项所花费的聚合时间。  

#### <a name="the-event-log-panel"></a>事件日志面板  

使用 **"事件** 日志"面板以记录期间活动发生的顺序查看活动。  

事件 **日志** 面板仅显示记录选定部分期间的活动。  导航 [到"选择录音的一部分](#select-a-portion-of-a-recording) "以了解如何选择部分。  

:::image type="complex" source="../media/evaluate-performance-performance-event-log.msft.png" alt-text="事件日志面板" lightbox="../media/evaluate-performance-performance-event-log.msft.png":::
   事件 **日志** 面板  
:::image-end:::  

" **开始时间** "列表示该活动的开始点，相对于录制的开始点。  例如，上图中选定项目的开始时间意味着活动在 `175.7 ms` 录制开始后的 175.7 毫秒开始。  

" **自** 时间"列表示直接用于该活动的时间。  

**"总时间**"列表示直接用于该活动或任何子项的时间。  

选择 **"开始时间****"、"****开始时间"或**"总时间"按该列对表进行排序。

使用 **"筛选器** "文本框按名称筛选活动。  

使用 **"持续时间** "菜单筛选出任何时间少于 1 毫秒或 15 毫秒的活动。  默认情况下 **，"持续时间** "菜单设置为 **"** 全部"，表示显示所有活动。  

禁用**加载**、**脚本、****呈现**或**绘制**复选框以筛选出这些类别的所有活动。  

### <a name="view-gpu-activity"></a>查看 GPU 活动  

在 GPU 部分查看 **GPU** 活动。  

:::image type="complex" source="../media/evaluate-performance-performance-gpu-zoomed.msft.png" alt-text="GPU 部分" lightbox="../media/evaluate-performance-performance-gpu-zoomed.msft.png":::
   **GPU**部分  
:::image-end:::  

### <a name="view-raster-activity"></a>查看栅格活动  

在"Raster"部分查看 **栅格** 活动。  

:::image type="complex" source="../media/evaluate-performance-performance-raster.msft.png" alt-text=""Raster"部分" lightbox="../media/evaluate-performance-performance-raster.msft.png":::
   **"Raster"** 部分  
:::image-end:::  

### <a name="view-interactions"></a>查看交互  

使用 **"交互"** 部分查找和分析在录制过程中发生的用户交互。  

:::image type="complex" source="../media/evaluate-performance-performance-interactions-animation.msft.png" alt-text=""交互"部分" lightbox="../media/evaluate-performance-performance-interactions-animation.msft.png":::
   " **交互"** 部分  
:::image-end:::  

交互底部的红线表示等待主线程所花的时间。  

选择交互以查看"摘要"面板中 **有关它的信息** 。  

### <a name="analyze-frames-per-second-fps"></a>分析每秒帧数 (FPS)   

DevTools 提供了多种分析每秒帧的方法：  

*   使用 [FPS 图表](#the-fps-chart) 获取在录制期间 FPS 的概述。  
*   使用 ["框架"](#the-frames-section) 部分查看特定帧所需要的时间。  
*   在 **页面运行时，使用 FPS** 指示器对 FPS 进行实时估计。  使用 FPS 指示器实时导航到"查看[每秒帧数"。](#view-frames-per-second-in-realtime-with-the-fps-meter)  
    
#### <a name="the-fps-chart"></a>FPS 图表  

**FPS**图表提供在录制期间帧速率的概述。  通常，绿色条形越高，帧速率越好。  

**FPS**图表上方的红色条是一条警告，指出帧速率下降得低到可能损害用户体验。  

:::image type="complex" source="../media/evaluate-performance-performance-fps-highlight.msft.png" alt-text="FPS 图表" lightbox="../media/evaluate-performance-performance-fps-highlight.msft.png":::
   **FPS** 图表  
:::image-end:::  

#### <a name="the-frames-section"></a>"框架"部分  

" **框架** "部分将告知你特定帧所使用时间。  

将鼠标悬停在框架上，查看工具提示，并详细了解它。  

:::image type="complex" source="../media/evaluate-performance-performance-frames-hover.msft.png" alt-text="鼠标悬停在框架上" lightbox="../media/evaluate-performance-performance-frames-hover.msft.png":::
   鼠标悬停在框架上  
:::image-end:::  

选择一个框架，在"摘要"面板中查看有关 **帧详细信息** 。  DevTools 将所选框架以蓝色分级显示。  

:::image type="complex" source="../media/evaluate-performance-performance-frames-summary.msft.png" alt-text="在"摘要"面板中查看框架" lightbox="../media/evaluate-performance-performance-frames-summary.msft.png":::
   在"摘要" **面板中查看** 框架  
:::image-end:::  

### <a name="view-network-requests"></a>查看网络请求  

展开 **"网络** "部分以查看记录期间发生的网络请求的瀑布。  

:::image type="complex" source="../media/evaluate-performance-performance-network.msft.png" alt-text=""网络"部分" lightbox="../media/evaluate-performance-performance-network.msft.png":::
   " **网络"** 部分  
:::image-end:::  

请求按如下方式进行颜色编码：  

*   HTML：蓝色  
*   CSS：紫色  
*   JS：黄色  
*   图像：绿色  
    
选择一个请求，在"摘要"面板中查看 **有关它详细信息** 。  例如，在上图中，"摘要"**** 面板显示有关在"网络"部分选择的蓝色**请求详细信息。**  

请求左上方的深蓝色正方形表示它是优先级较高的请求。  浅蓝色正方形表示优先级较低。  例如，在上图中，选择的蓝色请求的优先级更高，其下方的绿色请求优先级较低。  

在下图的第 1 个部分中，请求表示为左侧的线条、中间带深色部分的条形图和浅色部分，以及右侧 `www.bing.com` 线条。  下图的第 2 个显示了网络工具的"计时"面板中相同请求**的相应**表示形式。 ****  下面说明这两种表示形式如何相互映射：

*   左侧行是事件组 `Connection Start` （包含此事件）的所有内容。  换句话说，它是之前的所有内容， `Request Sent` 独占。  
*   条形图的光线部分为 `Request Sent` 和 `Waiting (TTFB)` 。  
*   条形图的深色部分是 `Content Download` 。  
*   正确的行实质上是等待主线程所花的时间。  This is not represented in the **Timing** panel.  
    
:::row:::
   :::column span="":::
      :::image type="complex" source="../media/evaluate-performance-bing-performance-network.msft.png" alt-text="请求的线www.bing.com表示形式" lightbox="../media/evaluate-performance-bing-performance-network.msft.png":::
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

打开" **内存"** 复选框以查看上次录制中的内存指标。  

:::image type="complex" source="../media/evaluate-performance-performance-memory-highlight.msft.png" alt-text=""内存"复选框" lightbox="../media/evaluate-performance-performance-memory-highlight.msft.png":::
   " **内存"** 复选框  
:::image-end:::  

DevTools 在" **摘要"** 面板上方显示新的 **内存** 图表。  NET 图表下方还有一**个新的图表，** 称为**HEAP。**  **HEAP**图表提供与内存图表中**JS 堆**行**相同的**信息。  

:::image type="complex" source="../media/evaluate-performance-performance-memory-chart.msft.png" alt-text="内存指标" lightbox="../media/evaluate-performance-performance-memory-chart.msft.png":::
   内存指标  
:::image-end:::  

图表上的彩色线条映射到图表上方的彩色复选框。  
禁用复选框以在图表中隐藏该类别。  

图表仅显示当前选定的录制区域。  例如，在上图中，内存图表只**** 显示从 400 毫秒标记到 1750 毫秒标记的内存使用量。  

### <a name="view-the-duration-of-a-portion-of-a-recording"></a>查看部分录制的持续时间  

分析网络或**Main****** 等节时，有时需要更准确的特定事件估计时间。  按住 `Shift` 、选择并按住，然后向左或向右拖动以选择录制的一部分。  在选择的底部，DevTools 显示该部分所需要时间。  

:::image type="complex" source="../media/evaluate-performance-performance-main-duration.msft.png" alt-text="查看部分录制的持续时间" lightbox="../media/evaluate-performance-performance-main-duration.msft.png":::
   查看部分录制的持续时间  
:::image-end:::  

### <a name="view-a-screenshot"></a>查看屏幕截图  

导航到 [录制时捕获屏幕截图](#capture-screenshots-while-recording) ，了解如何打开屏幕截图。  

将鼠标 **悬停在"概述** "上可查看页面在录制期间的外观的屏幕截图。  概述**是**包含 CPU、FPS**** 和**** **NET**图表的部分。  

:::image type="complex" source="../media/evaluate-performance-performance-screenshots-hover.msft.png" alt-text="查看屏幕截图" lightbox="../media/evaluate-performance-performance-screenshots-hover.msft.png":::
   查看屏幕截图  
:::image-end:::  

您还可以通过选择"框架"部分中的框架 **来查看屏幕截图** 。  DevTools 在"摘要"面板中显示小 **版本的屏幕截图** 。  

:::image type="complex" source="../media/evaluate-performance-performance-summary-preview.msft.png" alt-text="在"摘要"面板中查看屏幕截图" lightbox="../media/evaluate-performance-performance-summary-preview.msft.png":::
   在"摘要"面板 **中查看** 屏幕截图  
:::image-end:::  

选择"摘要 **"面板中的缩略图** 以放大屏幕截图。  

:::image type="complex" source="../media/evaluate-performance-performance-summary-preview-select.msft.png" alt-text="从"摘要"面板中放大屏幕截图" lightbox="../media/evaluate-performance-performance-summary-preview-select.msft.png":::
   从"摘要"面板**中放大屏幕截图**  
:::image-end:::  

### <a name="view-layers-information"></a>查看图层信息  

若要查看有关帧的高级层信息，请执行：  

1.  [打开高级画图检测](#turn-on-advanced-paint-instrumentation)。  
1.  在"框架"部分中 **选择** 一个图文框。  DevTools 在"事件日志"面板旁**** 的新"层"面板中显示有关**图层**的信息。  
    
    :::image type="complex" source="../media/evaluate-performance-layers-all.msft.png" alt-text=""层"窗格" lightbox="../media/evaluate-performance-layers-all.msft.png":::
       " **层"** 窗格  
    :::image-end:::  
    
将鼠标悬停在一个图层上，以在图表中突出显示它。  

:::image type="complex" source="../media/evaluate-performance-performance-frames-document-nav-bar-highlighted.msft.png" alt-text="突出显示图层" lightbox="../media/evaluate-performance-performance-frames-document-nav-bar-highlighted.msft.png":::
   突出显示图层  
:::image-end:::  

若要移动图表，请：  

*   选择 **"平移** 模式 (![ 平移模式 ][ImagePanModeIcon] \) 沿 X 和 Y 轴移动。  
*   选择 **旋转模式** \ (![ 旋转模式 ][ImageRotateModeIcon] \) 沿 Z 轴旋转。  
*   Choose **Reset Transform** \ (Reset Transform ![ ][ImageResetTransformIcon] \) to reset the diagram to the original position.  
    
### <a name="view-paint-profiler"></a>查看绘制探查器  

若要查看有关绘制事件的高级信息，请：  

1.  [打开](#turn-on-advanced-paint-instrumentation)。  
1.  在" **主** "部分 **选择"绘制"** 事件。  
    
    :::image type="complex" source="../media/evaluate-performance-paint-profiler.msft.png" alt-text=""绘制探查器"面板" lightbox="../media/evaluate-performance-paint-profiler.msft.png":::
       " **绘制探查器"** 面板  
    :::image-end:::  
    
## <a name="analyze-rendering-performance-with-the-rendering-tool"></a>使用呈现工具分析呈现性能  

使用呈现面板 **的功能** 帮助可视化页面的呈现性能。  

若要打开 **呈现工具** ，请执行以下操作：  

1.  [打开命令菜单][DevToolsCommandMenu]。  
1.  开始键入并选择 `Rendering` `Show Rendering` 。  DevTools **在** DevTools 窗口底部显示呈现工具。  
    
    :::image type="complex" source="../media/evaluate-performance-console-drawer-rendering.msft.png" alt-text="呈现工具" lightbox="../media/evaluate-performance-console-drawer-rendering.msft.png":::
       呈现**工具**  
    :::image-end:::  
    
### <a name="view-frames-per-second-in-realtime-with-the-fps-meter"></a>使用 FPS 指示器实时查看每秒帧数  

**FPS 指示器**是显示在视口右上角的覆盖层。  它在页面运行时提供 FPS 实时估计值。  打开 **FPS 指示器**：  

1.  打开 **呈现** 工具。  [使用呈现工具分析呈现性能](#analyze-rendering-performance-with-the-rendering-tool)。  
1.  打开 **"FPS 指示器"** 复选框。  
    
    :::image type="complex" source="../media/evaluate-performance-jank-console-rendering-frame-rate.msft.png" alt-text="FPS 计数" lightbox="../media/evaluate-performance-jank-console-rendering-frame-rate.msft.png":::
       **FPS 计数**  
    :::image-end:::  
    
### <a name="view-painting-events-in-realtime-with-paint-flashing"></a>使用"画图闪烁"实时查看绘制事件  

使用"画图闪烁"获取页面上所有绘制事件的真实视图。  只要重新绘制页面的一部分，DevTools 就会用绿色概括该部分。  

若要打开"画图闪烁"，请完成以下操作。  

1.  打开 **呈现** 工具。  导航到 [使用呈现工具分析呈现性能](#analyze-rendering-performance-with-the-rendering-tool)。  
1.  打开" **画图闪烁"** 复选框。  
    
    :::image type="complex" source="../media/evaluate-performance-jank-console-rendering-paint-flashing.msft.png" alt-text="画笔闪烁" lightbox="../media/evaluate-performance-jank-console-rendering-paint-flashing.msft.png":::
       **画笔闪烁**  
    :::image-end:::  
    
### <a name="view-an-overlay-of-layers-with-layer-borders"></a>使用图层边框查看覆盖层  

使用 **图层边框** 查看页面顶部的图层边框和磁贴的覆盖。  

若要打开图层边框，请完成以下操作：  

1.  打开 **呈现** 工具。  导航到 [使用呈现工具分析呈现性能](#analyze-rendering-performance-with-the-rendering-tool)。  
1.  打开" **图层边框"** 复选框。  
    
    :::image type="complex" source="../media/evaluate-performance-devtools-console-rendering-layer-borders.msft.png" alt-text="图层边框" lightbox="../media/evaluate-performance-devtools-console-rendering-layer-borders.msft.png":::
       **图层边框**  
    :::image-end:::  
    
导航到 [debug_colors.cc][ChromiumDebugColors] 中的注释，了解颜色编码的说明。  

### <a name="find-scroll-performance-issues-in-realtime"></a>实时查找滚动性能问题  

使用滚动性能问题可标识具有与滚动相关的事件侦听器的页面元素，这些元素可能会损害页面的性能。  
DevTools 以青色概述了可能存在问题的元素。  

若要查看滚动性能问题，请完成以下操作。 

1.  打开 **呈现** 工具。  导航到 [使用呈现工具分析呈现性能](#analyze-rendering-performance-with-the-rendering-tool)。  
1.  打开" **滚动性能问题"** 复选框。  
    
    :::image type="complex" source="../media/evaluate-performance-bing-console-drawer-rendering-scrolling-performance-issues.msft.png" alt-text="滚动性能问题指示不受层视口约束的对象可能会损害滚动性能" lightbox="../media/evaluate-performance-bing-console-drawer-rendering-scrolling-performance-issues.msft.png":::
       **滚动性能问题** 指示不受层视口约束的对象可能会损害滚动性能  
    :::image-end:::  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge 开发工具团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageCaptureSettingsIcon]: ../media/capture-settings-icon.msft.png  
[ImageClearRecordingIcon]: ../media/clear-recording-icon.msft.png  
[ImageCollectGarbageIcon]: ../media/collect-garbage-icon.msft.png  
[ImageNextIcon]: ../media/next-icon.msft.png  
[ImagePanModeIcon]: ../media/pan-mode-icon.msft.png  
[ImagePreviousIcon]: ../media/previous-icon.msft.png  
[ImageRecordIcon]: ../media/record-icon.msft.png
[ImageRefreshPageIcon]: ../media/refresh-page-icon.msft.png  
[ImageResetTransformIcon]: ../media/reset-transform-icon.msft.png  
[ImageRotateModeIcon]: ../media/rotate-mode-icon.msft.png  
[ImageSearchCaseIcon]: ../media/search-case-icon.msft.png  
[ImageSearchRegexIcon]: ../media/search-regex-icon.msft.png  
[ImageShowHeaviestStackIcon]: ../media/show-heaviest-stack-icon.msft.png  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 开发人员工具|Microsoft Docs"  
[DevToolsCommandMenu]: ../command-menu/index.md#open-the-command-menu "打开命令菜单 - 使用 Microsoft Edge DevTools 命令菜单运行|Microsoft Docs"  
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
