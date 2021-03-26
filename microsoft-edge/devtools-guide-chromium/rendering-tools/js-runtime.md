---
description: 使用 Microsoft Edge DevTools 内存面板识别内存占用大的函数。
title: 加速 JavaScript 运行时
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge，web 开发，f12 工具，devtools
ms.openlocfilehash: 2151777c6a9f94408f48552839531c3534d3de36
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: HT
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

# <a name="speed-up-javascript-runtime"></a>加速 JavaScript 运行时  

使用**内存**工具识别内存占用大的函数。  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-heavy-bottom-up.msft.png" alt-text="示例配置文件" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-heavy-bottom-up.msft.png":::
   示例配置文件  
:::image-end:::  

### <a name="summary"></a>摘要  

*   使用**内存**工具中的分配采样准确记录调用了哪些函数以及每个函数所需的内存。  
*   将配置文件可视化为火焰图。  
    
## <a name="record-a-sampling-profile"></a>记录采样配置文件  

如果在 JavaScript 中发现垃圾，请收集采样配置文件。  采样配置文件会显示页面中函数花费的运行时间。  

1.  导航到 DevTools 的**内存**工具。  
1.  选择“**分配采样**”按钮。  
1.  选择“**开始”**  
1.  根据你尝试分析的内容，可以刷新页面、与页面交互，或者只让页面运行。  
1.  完成后，选择“**停止**”。  
    
> [!NOTE]
> 还可以使用[控制台实用程序 API][DevtoolsConsoleUtilities] 记录和分组命令行的配置文件。  

## <a name="view-sampling-profile"></a>查看采样配置文件  

记录完成后，DevTools 会使用记录的数据自动填充**采样配置文件**下的**内存**面板。  

默认视图为**走势图\（自下而上\）**。  使用该视图允可以查看哪些函数对性能影响最大，并检查每个函数的请求路径。  

### <a name="change-sort-order"></a>更改排序顺序  

若要更改排序顺序，请选择“**聚焦定函数**”\（![聚焦选定函数](../media/focus-icon.msft.png)\）图标旁边的下拉菜单，然后从下列选项中选择一个。

**图表**。  显示记录的时序图。  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart.msft.png" alt-text="火焰图" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart.msft.png":::
   火焰图  
:::image-end:::  

**走势图\（自下而上\）**。  根据对性能的影响列出函数，并使你能够检查函数的调用路径。  这是默认视图。  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-heavy-bottom-up.msft.png" alt-text="走势图" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-heavy-bottom-up.msft.png":::
   走势图  
:::image-end:::  

**树状视图\（自上而下\）**。  显示调用结构的整体图片，从调用堆栈的顶部开始。  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-tree-top-down.msft.png" alt-text="树状图" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-tree-top-down.msft.png":::
   树状图  
:::image-end:::  

### <a name="exclude-functions"></a>排除函数  

若要从采样配置文件中排除函数，请选择该函数，然后选择“**排除所选函数**”\（![排除所选函数](../media/exclude-icon.msft.png)\）按钮。  已排除函数\（子级\）的请求函数\（父级\）将占用分配给已排除函数\（子级\）的分配内存。  

选择“**还原全部函数**”\（还原全部函数![ ](../media/restore-icon.msft.png)\）按钮将所有已排除函数还原到记录中。  

## <a name="view-sampling-profile-as-chart"></a>以图表模式查看采样配置文件  

图表视图能直观表示随时间变化的取样配置文件。  

[记录采样配置文件](#record-a-sampling-profile)后，将[排序顺序更改](#change-sort-order)为**图表**，以使用火焰图查看记录。  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart.msft.png" alt-text="火焰图视图" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart.msft.png":::
   火焰图视图  
:::image-end:::  

火焰图图表拆分为两个部分。  

| 索引 | 部分 | 描述 |  
| --- |:--- |:--- |  
| 1 | 概述 | 整个记录的鸟瞰图。  条形图的高度对应调用堆栈的深度。  因此，条形图越高，调用堆栈越深。  |  
| 2 | 调用堆栈 | 这是在记录过程中调用的函数的深入视图。  水平轴为时间，垂直轴为调用堆栈。  堆栈是自上而下组织的。  因此，顶部的函数调用它下面的函数，以此类推。  |  

函数颜色随机。  与其他面板中使用的颜色没有任何关联。  然而，函数在整个调用中的颜色都是相同的，这样你就可以观察到每个运行时的模式。  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-highlighted.msft.png" alt-text="带批注的火焰图" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-highlighted.msft.png":::
   带批注的火焰图  
:::image-end:::  

较高的调用堆栈不一定重要，它只是意味着调用了许多函数。  但较宽的条形图意味着函数完成时间花费很长。  这些都是需要优化的候选项。  

### <a name="zoom-in-on-specific-parts-of-recording"></a>放大记录的特定部分  

在概览上选择、按住并左右拖动鼠标，以放大调用堆栈的特定部分。  放大后，调用堆栈自动显示所选记录的部分。  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-zoomed.msft.png" alt-text="已放大的图表" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-zoomed.msft.png":::
   已放大的图表  
:::image-end:::  

### <a name="view-function-details"></a>查看函数详细信息  

选择函数以查看在**源**工具中的定义。  

将鼠标悬停在函数上可显示名称和计时数据。  将提供以下信息。  

| 详情 | 描述 |  
|:--- |:--- |  
| **名称** | 函数的名称。  |  
| **自身大小** | 函数当前调用的大小，只包括函数中的语句。  |  
| **总大小** | 该函数当前调用及其调用过的任何函数的大小。  |  
| **URL** | 函数定义的位置以 `base.js:261` 的形式表示，其中 `base.js` 是定义函数的文件的名称，而 `261` 是定义的行号。  |  
<!--*   **Aggregated self time**.  Aggregate time for all invocations of the function across the recording, not including functions called by this function.  -->  
<!--*   **Aggregated total time**.  Aggregate total time for all invocations of the function, including functions called by this function.  -->  
<!--*   **Not optimized**.  If the profiler has detected a potential optimization for the function it lists it here.  -->  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-hover.msft.png" alt-text="使用图表查看函数详细信息" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-hover.msft.png":::
   使用图表查看函数详细信息  
:::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge DevTools 团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsConsoleUtilities]: ../console/utilities.md "控制台实用程序 API 参考 | Microsoft Docs"  
[DevtoolsConsoleUtilitiesProfile]: ../console/utilities.md#profile "配置文件 - 控制台实用程序 API 参考 | Microsoft Docs"  
[DevtoolsConsoleUtilitiesProfileEnd]: ../console/utilities.md#profileend "profileEnd - 控制台实用程序 API 参考 | Microsoft Docs"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> [此处](https://developers.google.com/web/tools/chrome-devtools/rendering-tools/js-execution)可以找到原始页面，由 [Kayce Basques][KayceBasques] \（技术写作人员，Chrome DevTools \& Lighthouse\）和 [Meggin Kearney][MegginKearney] \（技术写作人员\）编写。  

[![知识共享许可协议][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
