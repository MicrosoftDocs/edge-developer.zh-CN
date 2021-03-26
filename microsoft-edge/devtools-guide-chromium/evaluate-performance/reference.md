---
description: 在 Microsoft Edge DevTools 中记录和分析性能所有方法的参考。
title: 性能分析引用
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: e7774dc0aab647b8cf2bf47699368fafe6c21d70
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: HT
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

本页是与分析性能相关 Microsoft Edge DevTools 功能的综合参考。  

导航到 [“分析运行时性能入门”][DevtoolsEvaluatePerformanceGettingStarted]，以获得关于如何使用 [Microsoft Edge DevTools][MicrosoftEdgeDevTools] 分析页面性能的指导教程。  

## <a name="record-performance"></a>记录性能  

### <a name="record-runtime-performance"></a>记录运行时性能  

当你想在页面运行时 (而非加载时) 分析其性能时，将记录运行时性能。  

1.  导航到要分析的页面。  
1.  在 DevTools 中打开 **“性能”** 工具。  
1.  选择 **记录** \(![记录图标](../media/record-icon.msft.png)\)。  
    
    :::image type="complex" source="../media/evaluate-performance-performance-record-highlight.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-record-highlight.msft.png":::
       **Record**  
    :::image-end:::  
    
1.  与页面交互。  DevTools 将记录由于交互而发生的所有页面活动。  
1.  再次选择 **“记录”** 或选择 **“停止”** 以停止录制。  
    
### <a name="record-load-performance"></a>记录加载性能  

当你想在页面加载时 (而非运行时) 分析其性能时，将记录加载时性能。  

1.  导航到要分析的页面。  
1.  打开 DevTools 的 **“性能”** 面板。  
1.  选择 **刷新网页** \(![刷新网页](../media/refresh-page-icon.msft.png)\)。  DevTools 在页面刷新时记录性能指标，然后在加载完成后几秒钟自动停止记录。  
    
    :::image type="complex" source="../media/evaluate-performance-performance-refresh-button.msft.png" alt-text="刷新页面" lightbox="../media/evaluate-performance-performance-refresh-button.msft.png":::
       **刷新页面**  
    :::image-end:::  
    
DevTools 会自动放大大部分活动发生的记录部分。  

:::image type="complex" source="../media/evaluate-performance-performance-refreshed.msft.png" alt-text="页面加载录制" lightbox="../media/evaluate-performance-performance-refreshed.msft.png":::
   页面加载录制  
:::image-end:::  

### <a name="capture-screenshots-while-recording"></a>录制时捕获屏幕截图  

打开 **“屏幕截图”** 复选框以捕获录制时每帧画面的屏幕截图。  

:::image type="complex" source="../media/evaluate-performance-performance-capture-screenshots-checkbox.msft.png" alt-text="屏幕截图复选框" lightbox="../media/evaluate-performance-performance-capture-screenshots-checkbox.msft.png":::
   **屏幕截图** 复选框  
:::image-end:::  

导航到 [查看屏幕截图](#view-a-screenshot) 了解如何与屏幕截图进行交互。  

### <a name="force-garbage-collection-while-recording"></a>录制时强制收集垃圾  

录制页面时，选择 **“回收垃圾”** \ (![“回收垃圾图标”](../media/collect-garbage-icon.msft.png)\) 以强制回收垃圾。  

:::image type="complex" source="../media/evaluate-performance-performance-collect-garbage-button.msft.png" alt-text="回收垃圾" lightbox="../media/evaluate-performance-performance-collect-garbage-button.msft.png":::
   回收垃圾  
:::image-end:::  

### <a name="show-recording-settings"></a>显示录制设置  

选择 **“捕获设置”** \(![捕获设置](../media/capture-settings-icon.msft.png)\) 就可以看到更多与 DevTools 如何捕获性能记录相关的设置。  

:::image type="complex" source="../media/evaluate-performance-performance-capture-settings-button-open-drawer.msft.png" alt-text=""捕获设置"部分" lightbox="../media/evaluate-performance-performance-capture-settings-button-open-drawer.msft.png":::
   **“捕获设置”** 部分  
:::image-end:::  

### <a name="disable-javascript-samples"></a>禁用 JavaScript 示例  

默认情况下，录制的 **主** 部分会显示录音期间调用的 JavaScript 函数的详细调用栈。  禁用以下调用堆栈:  

1.  打开 **“捕获设置”** 菜单。  导航到 [“显示录制设置”](#show-recording-settings)。  
1.  打开 **“禁用 JavaScript 示例”** 复选框。  
1.  记录页面。  
    
以下 2 张图显示了禁用和启用 JavaScript 样本的区别。  当禁用取样时，录音的**主**部分要短得多，因为它省略了所有的 JavaScript 调用堆栈。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-on.msft.png" alt-text="禁用 JS 示例时的录制示例" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-on.msft.png":::
         禁用 JS 示例时的录制示例  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off.msft.png" alt-text="启用 JS 示例时的录制示例" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off.msft.png":::
         启用 JS 示例时的录制示例  
      :::image-end:::  
   :::column-end:::
:::row-end:::

### <a name="throttle-the-network-while-recording"></a>在录制时限制网络  

若要在录制时限制网络:  

1.  打开 **“捕获设置”** 菜单。  导航到 [“显示录制设置”](#show-recording-settings)。  
1.  将 **“网络”** 设置为所需的限制级别。  
    
### <a name="throttle-the-cpu-while-recording"></a>录制时限制 CPU  

若要在录制时限制 CPU:  

1.  打开 **“捕获设置”** 菜单。  导航到 [“显示录制设置”](#show-recording-settings)。  
1.  将 **“CPU”** 设置为所需的限制级别。  
    
限制是相对于计算机的功能而言的。  例如，**两倍减速** 选项使 CPU 运行速度比正常情况下慢两倍。  DevTools 并不能真正模拟移动设备的 CPU，因为移动设备的体系结构与台式机和笔记本电脑的体系结构截然不同。  

### <a name="turn-on-advanced-paint-instrumentation"></a>启用高级画图检测工具  

查看详细画图检测工具:  

1.  打开 **“捕获设置”** 菜单。  导航到 [“显示录制设置”](#show-recording-settings)。  
1.  选中 **“启用画图检测工具 (慢速)”** 复选框。  

若要了解如何与画图信息交互，请导航到 [“视图图层”](#view-layers-information) 和 [“视图绘制探查器”](#view-paint-profiler)。  

## <a name="save-a-recording"></a>保存录制内容  

若要保存录制文件，请打开上下文菜单 \(右键单击\)，然后选择 **“保存配置文件”**。  

:::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-save-profile.msft.png" alt-text="保存配置文件" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-save-profile.msft.png":::
   **保存配置文件**  
:::image-end:::  

## <a name="load-a-recording"></a>加载录制  

若要加载录制文件，请打开上下文菜单 \(右键单击\)，然后选择 **“加载配置文件”**。  

:::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-load-profile.msft.png" alt-text="加载配置文件" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-load-profile.msft.png":::
   **加载配置文件**  
:::image-end:::  

## <a name="clear-the-previous-recording"></a>清除上一记录  

录制后，选择 **清除录制** \(![清除录制图标](../media/clear-recording-icon.msft.png)\) 以从 **性能** 面板中清除录制。  

:::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-clear-button.msft.png" alt-text="清除录制" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-clear-button.msft.png":::
   **清除录制**  
:::image-end:::  

## <a name="analyze-a-performance-recording"></a>分析性能录制  

在 [录制运行性能](#record-runtime-performance) 或 [录制加载性能](#record-load-performance) 之后， **性能** 面板将提供许多数据以分析刚发生的操作的性能。  

### <a name="select-a-portion-of-a-recording"></a>选择录制的一部分  

在 **“概述”** 上向左或向右拖动鼠标，以选择一段录音的一部分。  **概述** 是包含 **FPS**、**CPU** 和 **NET** 图表的部分。  

:::image type="complex" source="../media/evaluate-performance-performance-zoom-highlighted.msft.png" alt-text="拖动鼠标在“概述”上进行缩放" lightbox="../media/evaluate-performance-performance-zoom-highlighted.msft.png":::
   将鼠标悬停在 **“概述”** 上进行缩放  
:::image-end:::  

若要使用键盘选择一部分:  

1.  选择 **主** 部分的背景或它旁边的任何分区，例如 **交互**、 **网络**或 **GPU**。  此键盘工作流仅在其中一个分区为焦点时有效。  
1.  使用 `W`、`A`、`S`、`D` 键分别进行放大、向左移动、缩小和向右移动。  

若要使用触控板选择一部分，请完成以下操作。  

1.  将鼠标悬停在 **“概述”** 部分或 **“详细信息”** 上。  **概述** 部分是包含 **FPS**、**CPU** 和 **NET** 图表的区域。  **详细信息** 部分是包含 **主** 部分、**交互** 部分等的区域。  
1.  使用两根手指，向上轻扫进行缩小，向左轻扫向左移动，向下轻扫进行放大，向右轻扫向右移动。  

若要在 **主** 区域或任何一个邻区滚动长火焰图，请选择并按住鼠标同时上下拖动。  向左和向右拖动，移动录音中所选的部分。  

### <a name="search-activities"></a>搜索活动  

选择 `Control`+`F` \(Windows，Linux\) 或 `Command`+`F` \(macOS\) 以打开**性能**面板底部的搜索框。  

:::image type="complex" source="../media/evaluate-performance-performance-search-regex.msft.png" alt-text="搜索框" lightbox="../media/evaluate-performance-performance-search-regex.msft.png":::
   搜索框  
:::image-end:::  

导航与查询匹配的活动:  

*   使用 **上一步** \(![上一步](../media/previous-icon.msft.png)\) 和 **下一步** \(![下一步](../media/next-icon.msft.png)\) 按钮。  
*   选择 `Shift`+`Enter` 来选择上一步或 `Enter` 来选择下一步。  

修改查询设置:  

*   选择 **区分大小写** \(![区分大小写](../media/search-case-icon.msft.png)\)，使查询区分大小写。  
*   选择 **正则表达式** \(![正则表达式](../media/search-regex-icon.msft.png)\) ，在查询中使用正则表达式。  

若要隐藏搜索框，请选择 **“取消”**。  

### <a name="view-main-thread-activity"></a>查看主线程活动  

使用 **主** 部分查看出现在页面主线程上的活动。  

:::image type="complex" source="../media/evaluate-performance-performance-main-zoomed.msft.png" alt-text="主要部分" lightbox="../media/evaluate-performance-performance-main-zoomed.msft.png":::
   **主要**部分  
:::image-end:::  

选择一个事件以在 **“摘要”** 面板中查看更多相关信息。  DevTools 概括了所选事件。  

:::image type="complex" source="../media/evaluate-performance-performance-summary-me.msft.png" alt-text="更多关于摘要面板中匿名函数的信息。" lightbox="../media/evaluate-performance-performance-summary-me.msft.png":::
   更多关于 **“摘要”** 面板中的 `anonymous` 功能的信息  
:::image-end:::  

DevTools 使用火焰图表示主线程活动。  x 轴表示一段时间内的记录。  Y 轴表示调用堆叠。  顶部事件将导致其下方事件。  

:::image type="complex" source="../media/evaluate-performance-performance-main-flame-chart.msft.png" alt-text="火焰图" lightbox="../media/evaluate-performance-performance-main-flame-chart.msft.png":::
   火焰图  
:::image-end:::  

在上一图中，`click` 事件在 53 行的 `activitytabs.js` 中造成了 `Function Call`。  在 `Function Call` 下面，查看匿名函数运行。  匿名函数请求 `Minor GC`的请求 `wait`的请求 `a`。  

DevTools 为脚本随机分配颜色。  在上图中，请求来自脚本的函数请求染成为浅绿色。  来自另一个脚本的请求以米色表示。  深黄色代表脚本活动，紫色事件代表渲染活动。  这些深黄色和紫色事件在所有记录中都是一致的。  

若要隐藏 JavaScript 请求的详细火焰图，请导航到 [禁用 JavaScript 事例](#disable-javascript-samples)。  禁用 JS 示例时，只显示上图中 `str` 中的 `Event: choose` 和 `Function Call` 等高级事件。  

### <a name="view-activities-in-a-table"></a>查看表格中的活动  

录制页面后，无需仅依靠 **“主”** 部分来分析活动。  DevTools 还提供了三种用于分析活动的表格视图。  每个视图提供对待活动的不同视角:  

*   当想查看导致最多工作的根活动时，请使用 [“调用树”](#the-call-tree-panel) 面板。  
*   当想查看直接花费时间最多的活动时，请使用 [“自下而上”](#the-bottom-up-panel) 面板。  
*   当想按照记录期间发生的顺序查看活动时，请使用 [“事件日志”](#the-event-log-panel) 面板。  
    
> [!NOTE]
> 接下来的三个部分均指向相同的演示。  在 [“活动选项卡演示”][ActivityTabsDemo] 中自己运行演示。  

#### <a name="root-activities"></a>根活动  

下面就 **“调用树”** 面板、**“自下而上”** 面板和 **“事件日志”** 面板中提到的 **“根活动”** 概念进行说明。  

根活动是指那些导致浏览器执行的一些操作。  例如，选择网页时，浏览器将运行 `Event` 活动作为根活动。  `Event` 可能会导致处理程序运行等。  

在 **主** 部分的火焰图中，根活动位于图表顶部。  在 **“调用树”** 和 **“活动日志”** 面板中，根活动是顶级项目。  

导航到 [“调用树”](#the-call-tree-panel) 面板，查看根活动示例。  

#### <a name="the-call-tree-panel"></a>“调用树”面板  

使用 **“呼叫树”** 查看哪些 [“根活动”](#root-activities) 导致的工作量最大。  

**“呼叫树”** 面板仅在录制的选定部分期间显示活动。  导航到 [“请选择记录的一部分”](#select-a-portion-of-a-recording) 以了解如何选择部分。  

:::image type="complex" source="../media/evaluate-performance-performance-call-tree.msft.png" alt-text="“调用树”面板" lightbox="../media/evaluate-performance-performance-call-tree.msft.png":::
   **“调用树”** 面板  
:::image-end:::  

在上图中，**“活动”** 列中的顶级项目，如 `Evaluate Script` 和 `Parse HTML` 是根活动。  嵌套表示调用堆栈。  例如，在上图中，导致 `Compile Script` 和 `(anonymous)` 的 `Evaluate Script` 的 `Parse HTML`。  

**“自我时间”** 表示直接用于该活动的时间。  **“总时间”** 表示花在该活动或任何子项上的时间。  

选择 **“自我时间”**、**“总时间”** 或 **“活动”**，按该列对表进行排序。  

使用 **“筛选器”** 文本框按活动名称筛选事件。  

默认情况下，**“分组”** 菜单设置为 **“无分组”**。  使用 **“分组”** 菜单，根据各种条件对活动表进行排序。  

选择 **“显示最重堆叠** \(![显示最重堆叠](../media/show-heaviest-stack-icon.msft.png)\) 以显示 **“活动“** 表右侧的另一个表。  选择一个活动来填充 **最重堆叠** 表。  **“最重堆栈”** 表显示所选活动的子项需要最长的运行时间。  

#### <a name="the-bottom-up-panel"></a>“自下而上”面板  

使用 **“自下而上”** 面板查看直接采用聚合时间的活动。  

**“自下向上”** 面板仅在录制的选定部分期间显示活动。  导航到 [“请选择记录的一部分”](#select-a-portion-of-a-recording) 以了解如何选择部分。  

:::image type="complex" source="../media/evaluate-performance-performance-bottoms-up.msft.png" alt-text="“自下而上”面板" lightbox="../media/evaluate-performance-performance-bottoms-up.msft.png":::
   **“自下而上”** 面板  
:::image-end:::  

在前图的 **主** 分区火焰图中，导航到几乎实践上所有时间都花费在运行 `Parse HTML` 上。  前图中 **“自下而上”** 面板中最上面的活动是 `Parse HTML`。  <!--In the flame chart of the previous figure, the yellow below the calls to `wait` are actually thousands of `Minor GC` calls.  -->  导航到 **“自下向上”** 面板，接下来最昂贵的活动是 `Layout`。  

**“自我时间”** 列表示跨越发生的所有直接用于该活动的聚合时间。  

**“总时间”** 列表示花在该活动或任何子项上的聚合时间。  

#### <a name="the-event-log-panel"></a>事件日志面板  

使用 **“事件日志”** 面板按记录期间发生的顺序查看活动。  

**“事件日志”** 面板仅显示录制的选定部分期间的活动。  导航到 [“请选择记录的一部分”](#select-a-portion-of-a-recording) 以了解如何选择部分。  

:::image type="complex" source="../media/evaluate-performance-performance-event-log.msft.png" alt-text="事件日志面板" lightbox="../media/evaluate-performance-performance-event-log.msft.png":::
   **事件日志** 面板  
:::image-end:::  

**“开始时间”** 列表示活动开始时与录制开始相对的点。  例如，上图中所选项目 `175.7 ms` 的开始时间意味着录制开始 175.7 毫秒后活动开始。  

**“自我时间”** 列表示直接用于该活动的时间。  

**“总时间”** 列表示直接用于该活动或任何子项中的时间。  

选择 **“开始时间”**、**“自我时间”** 或 **“总时间”** 按该列对表进行排序。

使用 **“筛选”** 文本框按名称筛选活动。  

使用 **“持续时间”** 菜单筛选出所有耗时少于 1 毫秒或 15 毫秒的活动。  默认情况下，**“持续时间”** 菜单设置为 **“全部”**，这意味着会显示所有活动。  

禁用 **加载**、 **脚本**、 **渲染**或 **绘制** 复选框以筛选这些类别中的所有活动。  

### <a name="view-gpu-activity"></a>查看 GPU 活动  

在 **GPU** 部分查看 GPU 活动。  

:::image type="complex" source="../media/evaluate-performance-performance-gpu-zoomed.msft.png" alt-text="GPU 部分" lightbox="../media/evaluate-performance-performance-gpu-zoomed.msft.png":::
   **GPU** 部分  
:::image-end:::  

### <a name="view-raster-activity"></a>查看光栅活动  

在**光栅** 部分中查看光栅活动。  

:::image type="complex" source="../media/evaluate-performance-performance-raster.msft.png" alt-text="“光栅”部分" lightbox="../media/evaluate-performance-performance-raster.msft.png":::
   **“光栅”** 部分  
:::image-end:::  

### <a name="view-interactions"></a>查看交互  

使用 **“交互”** 部分查找和分析在录制期间发生的用户交互。  

:::image type="complex" source="../media/evaluate-performance-performance-interactions-animation.msft.png" alt-text="“交互”部分" lightbox="../media/evaluate-performance-performance-interactions-animation.msft.png":::
   **“交互”** 部分  
:::image-end:::  

交互底部的红线表示等待主线程所花费的时间。  

选择一个交互以在 **“摘要”** 面板中查看更多相关信息。  

### <a name="analyze-frames-per-second-fps"></a>分析每秒帧数 (FPS)  

DevTools 提供了许多方法，以分析每秒帧数:  

*   使用 [FPS 图](#the-fps-chart) 在录制期间获取 FPS 的概述。  
*   使用 [帧部分](#the-frames-section) 查看特定帧所需的时间。  
*   在页面运行时，使用 **FPS 计数** 来实时估计 FPS。  导航到 [使用 FPS 计数实时查看每秒帧数](#view-frames-per-second-in-realtime-with-the-fps-meter)。  
    
#### <a name="the-fps-chart"></a>FPS 图表  

**FPS** 图表提供整个录制期间的帧率概况。  一般来说，绿条越高，帧率越好。  

**FPS** 图上方的红色条形是警告，说明帧率降得太低，很可能会损害用户的体验。  

:::image type="complex" source="../media/evaluate-performance-performance-fps-highlight.msft.png" alt-text="FPS 图表" lightbox="../media/evaluate-performance-performance-fps-highlight.msft.png":::
   **FPS** 图表  
:::image-end:::  

#### <a name="the-frames-section"></a>”帧“ 部分  

**“帧”** 部分会准确告知特定帧所需的时间。  

将鼠标悬停在帧上，可以查看有关该帧的更多信息的工具提示。  

:::image type="complex" source="../media/evaluate-performance-performance-frames-hover.msft.png" alt-text="鼠标悬停在框架上" lightbox="../media/evaluate-performance-performance-frames-hover.msft.png":::
   鼠标悬停在框架上  
:::image-end:::  

选择帧以在 **“摘要”** 面板中查看更多有关帧的信息。  DevTools 用蓝色勾勒出所选框架的轮廓。  

:::image type="complex" source="../media/evaluate-performance-performance-frames-summary.msft.png" alt-text="在 “摘要” 面板中查看帧" lightbox="../media/evaluate-performance-performance-frames-summary.msft.png":::
   在 **“摘要”** 面板中查看帧  
:::image-end:::  

### <a name="view-network-requests"></a>查看网络请求  

展开 **“网络”** 部分，以查看录制期间发生的网络请求瀑布图。  

:::image type="complex" source="../media/evaluate-performance-performance-network.msft.png" alt-text="“网络”部分" lightbox="../media/evaluate-performance-performance-network.msft.png":::
   **“网络”** 部分  
:::image-end:::  

请求的颜色编码如下:  

*   HTML: 蓝色  
*   CSS: 紫色  
*   JS: 黄色  
*   图像: 绿色  
    
选择一个请求以在 **“摘要”** 面板中查看更多相关信息。  例如，在上图中，**“摘要”** 正在显示更多关于在 **“网络”** 部分选择的蓝色请求的信息。  

在请求的左上方有一个深蓝色的方块，意味着它是一个优先级较高的请求。  浅蓝色的方块表示优先级较低。  比如上图中，蓝色所选的请求是优先级较高的，而下方绿色的请求为优先级较低的。  

在下图中的第1个图中，`www.bing.com` 的要求用左边的一条线表示，中间是有暗部和亮部的条形，右边是一条线。  在下面的第2个数字中，显示了同一请求在 **“网络”** 工具的 **“计时”** 面板中的相应表示。  下面是这两种表示形式如何相互映射:

*   左行是到事件的 `Connection Start` 组的所有内容 (包括)。  换言之，它是 `Request Sent` 之前的所有内容 (独占)。  
*   条形图的浅部分为 `Request Sent` 和 `Waiting (TTFB)`。  
*   条形图的深色部分为 `Content Download`。  
*   右行基本上是等待主线程所花的时间。  这未在 **“计时”** 中表示。  
    
:::row:::
   :::column span="":::
      :::image type="complex" source="../media/evaluate-performance-bing-performance-network.msft.png" alt-text="www.bing.com 请求的行条表示" lightbox="../media/evaluate-performance-bing-performance-network.msft.png":::
         `www.bing.com` 请求的行条表示  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/evaluate-performance-bing-network-timing.msft.png" alt-text="网络工具" lightbox="../media/evaluate-performance-bing-network-timing.msft.png":::
         **网络** 工具  
:     ::image-end:::  
   :::column-end:::
:::row-end:::

### <a name="view-memory-metrics"></a>查看内存指标  

打开 **“内存”** 复选框以查看上次记录中的内存指标。  

:::image type="complex" source="../media/evaluate-performance-performance-memory-highlight.msft.png" alt-text="内存复选框" lightbox="../media/evaluate-performance-performance-memory-highlight.msft.png":::
   **“内存”** 复选框  
:::image-end:::  

DevTools 在 **“摘要”** 面板上方显示新的 **“内存”** 图表。  **NET** 图表下方还有一个新的图表，称为 **“HEAP”**。  **“HEAP”** 图表提供的信息与 **“内存”** 表中的 **“JS Heap”** 行相同。  

:::image type="complex" source="../media/evaluate-performance-performance-memory-chart.msft.png" alt-text="内存指标" lightbox="../media/evaluate-performance-performance-memory-chart.msft.png":::
   内存指标  
:::image-end:::  

图表上的彩色线条会映射到图表上方的彩色复选框上。  
禁用复选框以在图表中隐藏该类别。  

图表只显示当前选择的记录区域。  例如，在上一个图中， **内存** 图表仅显示从 400 毫秒标记上下到 1750 毫秒标记左右的内存使用情况。  

### <a name="view-the-duration-of-a-portion-of-a-recording"></a>查看部分录制的持续时间  

当分析像 **网络** 或者 **主** 这样的部分时，有时你需要更精确地估计某些事件花了多长时间。  按住 `Shift`，选择并按住，然后向左或向右拖动以选择录音的一部分。  在所选内容底部，DevTools 显示该部分所话费的时间。  

:::image type="complex" source="../media/evaluate-performance-performance-main-duration.msft.png" alt-text="查看部分录制的持续时间" lightbox="../media/evaluate-performance-performance-main-duration.msft.png":::
   查看部分录制的持续时间  
:::image-end:::  

### <a name="view-a-screenshot"></a>查看屏幕截图  

导航到 [“录制时捕捉屏幕截图”](#capture-screenshots-while-recording)，了解如何开启屏幕截图。  

将鼠标悬停在 **“概述”**，可以查看该记录短片的页面截图。  **“概述”** 是包含 **CPU**、**FPS** 和 **NET** 图表的部分。  

:::image type="complex" source="../media/evaluate-performance-performance-screenshots-hover.msft.png" alt-text="查看屏幕截图" lightbox="../media/evaluate-performance-performance-screenshots-hover.msft.png":::
   查看屏幕截图  
:::image-end:::  

还可以在 **“框架”** 部分选择一个框架来查看屏幕截图。  DevTools 在 **“摘要”** 面板中显示小版本的截图。  

:::image type="complex" source="../media/evaluate-performance-performance-summary-preview.msft.png" alt-text="在“摘要”面板中查看屏幕截图" lightbox="../media/evaluate-performance-performance-summary-preview.msft.png":::
   在 **“摘要”** 面板中查看屏幕截图  
:::image-end:::  

在 **“摘要”** 面板中选择缩略图来放大截图。  

:::image type="complex" source="../media/evaluate-performance-performance-summary-preview-select.msft.png" alt-text="从“摘要”面板中放大屏幕截图" lightbox="../media/evaluate-performance-performance-summary-preview-select.msft.png":::
   从 **“摘要”** 面板中放大屏幕截图  
:::image-end:::  

### <a name="view-layers-information"></a>查看图层信息  

查看框架的高级图层信息:  

1.  [启用高级画图检测工具](#turn-on-advanced-paint-instrumentation)。  
1.  在 **“框架”** 部分选择一个框架。  DevTools 将在 **“事件日志”** 面板旁边的新 **“图层”** 面板中显示关于图层的信息。  
    
    :::image type="complex" source="../media/evaluate-performance-layers-all.msft.png" alt-text="“图层”窗格" lightbox="../media/evaluate-performance-layers-all.msft.png":::
       **“图层”** 窗格  
    :::image-end:::  
    
将鼠标悬停在图层上，在图中高亮显示。  

:::image type="complex" source="../media/evaluate-performance-performance-frames-document-nav-bar-highlighted.msft.png" alt-text="突出显示图层" lightbox="../media/evaluate-performance-performance-frames-document-nav-bar-highlighted.msft.png":::
   突出显示图层  
:::image-end:::  

若要移动图表:  

*   选择 **“平移模式”** \(![“平移模式”](../media/pan-mode-icon.msft.png)\) 沿 X 轴和 Y 轴移动。  
*   选择 **“旋转模式”** \(![“旋转模式”](../media/rotate-mode-icon.msft.png)\) 沿 Z 轴旋转。  
*   选择 **“重置转换”** \(![“重置转换”](../media/reset-transform-icon.msft.png)\) 可以将图重置到原始位置。  
    
### <a name="view-paint-profiler"></a>查看绘图探查器  

查看有关绘图事件的高级信息:  

1.  [打开](#turn-on-advanced-paint-instrumentation)。  
1.  在 **主** 部分选择 **绘图** 事件。  
    
    :::image type="complex" source="../media/evaluate-performance-paint-profiler.msft.png" alt-text="“绘图探查器”面板" lightbox="../media/evaluate-performance-paint-profiler.msft.png":::
       **“绘图探查器”** 面板  
    :::image-end:::  
    
## <a name="analyze-rendering-performance-with-the-rendering-tool"></a>使用 "渲染" 工具分析渲染性能  

使用 **“渲染”** 面板的功能来帮助可视化页面的渲染性能。  

若要打开 **“渲染”** 工具:  

1.  [打开“命令”菜单][DevToolsCommandMenu]。  
1.  开始键入 `Rendering` 并选择 `Show Rendering`。  DevTools 会在 DevTools 窗口的底部显示**渲染**工具。  
    
    :::image type="complex" source="../media/evaluate-performance-console-drawer-rendering.msft.png" alt-text="渲染工具" lightbox="../media/evaluate-performance-console-drawer-rendering.msft.png":::
       **渲染** 工具  
    :::image-end:::  
    
### <a name="view-frames-per-second-in-realtime-with-the-fps-meter"></a>使用 FPS 计数实时查看每秒帧数。  

**FPS 计数** 是出现在视区右上角的叠加。  它提供了页面运行时 FPS 的实时估计。  若要打开 **FPS 计数**:  

1.  打开 **渲染** 工具。  [使用 “渲染” 工具分析渲染性能](#analyze-rendering-performance-with-the-rendering-tool)。  
1.  打开 **FPS 计数** 复选框。  
    
    :::image type="complex" source="../media/evaluate-performance-jank-console-rendering-frame-rate.msft.png" alt-text="FPS 计数" lightbox="../media/evaluate-performance-jank-console-rendering-frame-rate.msft.png":::
       **FPS 计数**  
    :::image-end:::  
    
### <a name="view-painting-events-in-realtime-with-paint-flashing"></a>使用“画图闪烁”实时查看画图事件  

使用“画图闪烁”可实时查看页面上的所有画图事件。  每当重新绘制页面的一部分时，DevTools 就会用绿色勾勒出该部分的轮廓。  

若要打开“画图闪烁”，请完成以下操作。  

1.  打开 **渲染** 工具。  导航到 [使用“绘制”工具分析绘制性能](#analyze-rendering-performance-with-the-rendering-tool)。  
1.  启用 **“画图闪烁”** 复选框。  
    
    :::image type="complex" source="../media/evaluate-performance-jank-console-rendering-paint-flashing.msft.png" alt-text="绘画闪烁" lightbox="../media/evaluate-performance-jank-console-rendering-paint-flashing.msft.png":::
       **绘画闪烁**  
    :::image-end:::  
    
### <a name="view-an-overlay-of-layers-with-layer-borders"></a>使用 “图层边框” 查看图层的叠加  

使用 **“图层边框”** 可查看页面顶部的图层边框和图块的叠加。  

若要打开“图层边框”，请完成以下操作，  

1.  打开 **渲染** 工具。  导航到 [使用“绘制”工具分析绘制性能](#analyze-rendering-performance-with-the-rendering-tool)。  
1.  打开 **“图层边框”** 复选框。  
    
    :::image type="complex" source="../media/evaluate-performance-devtools-console-rendering-layer-borders.msft.png" alt-text="图层边框" lightbox="../media/evaluate-performance-devtools-console-rendering-layer-borders.msft.png":::
       **图层边框**  
    :::image-end:::  
    
导航到 [debug_colors.cc][ChromiumDebugColors] 中的批注，了解颜色编码的说明。  

### <a name="find-scroll-performance-issues-in-realtime"></a>实时查找滚动性能问题  

使用滚动性能问题来识别页面中具有与滚动相关的事件监听器的元素，这些元素可能会损害页面的性能。  
DevTools 概述了茶色中潜在的问题元素。  

若要查看滚动性能问题，请完成以下操作。 

1.  打开 **渲染** 工具。  导航到 [使用“绘制”工具分析绘制性能](#analyze-rendering-performance-with-the-rendering-tool)。  
1.  打开 **“滚动性能问题”** 复选框。  
    
    :::image type="complex" source="../media/evaluate-performance-bing-console-drawer-rendering-scrolling-performance-issues.msft.png" alt-text="滚动性能问题表明，非层视区的限制对象可能会损害滚动性能" lightbox="../media/evaluate-performance-bing-console-drawer-rendering-scrolling-performance-issues.msft.png":::
       **“滚动性能问题”** 表明，非层视区的限制对象可能会损害滚动性能  
    :::image-end:::  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge 开发工具团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 开发人员工具 | Microsoft 文档"  
[DevToolsCommandMenu]: ../command-menu/index.md#open-the-command-menu "使用 Microsoft Edge DevTools 命令菜单运行命令 | Microsoft Docs"  
[DevtoolsEvaluatePerformanceGettingStarted]: ./index.md "开始分析运行时性能 | Microsoft Docs"  

[ActivityTabsDemo]: https://microsoft-edge-chromium-devtools.glitch.me/perf/activitytabs.html "活动选项卡演示 | 故障"  

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
