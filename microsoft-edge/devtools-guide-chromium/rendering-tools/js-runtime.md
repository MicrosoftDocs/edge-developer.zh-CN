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

# <a name="speed-up-javascript-runtime"></a>加速 JavaScript 运行时  

使用"内存"面板标识 **成本高昂的** 函数。  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-heavy-bottom-up.msft.png" alt-text="示例配置文件" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-heavy-bottom-up.msft.png":::
   示例配置文件  
:::image-end:::  

### <a name="summary"></a>摘要  

*   使用"内存"面板中的"分配采样"准确记录调用的函数以及每个函数 **所需的内存** 量。  
*   将你的配置文件可视化为一个图表。  
    
## <a name="record-a-sampling-profile"></a>记录采样配置文件  

如果你注意到 JavaScript 中的 jank，请收集一个采样配置文件。  采样配置文件显示运行时间在页面中函数的花费位置。  

1.  导航 **到** DevTools 的内存面板。  
1.  选择 **"分配采样单** 选"按钮。  
1.  选择 **"开始"。**  
1.  根据您尝试分析的内容，您可以刷新页面、与页面交互或仅让页面运行。  
1.  完成后 **，** 选择"停止"按钮。  
    
> [!NOTE]
> 您还可以使用控制台实用程序 [API][DevtoolsConsoleUtilities] 从命令行记录和分组配置文件。  

## <a name="view-sampling-profile"></a>查看采样配置文件  

完成录制后，DevTools 会自动使用录制数据**** 填充 **"采样配置文件**"下的"内存"面板。  

默认视图为 Heavy **\ (Bottom Up\) 。 **  此视图允许你查看哪些函数对性能影响最大，并检查每个函数的请求路径。  

### <a name="change-sort-order"></a>更改排序顺序  

若要更改排序顺序，请选择焦点选定函数 **\ (** 焦点选定函数 \) 图标旁边的下拉菜单，然后选择下列 ![ ][ImageFocusIcon] 选项之一。

**图表**。  显示记录的时间顺序图表。  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart.msft.png" alt-text="饼图" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart.msft.png":::
   饼图  
:::image-end:::  

**粗 \ (下向上\) **。  根据对性能的影响列出函数，并使您能够检查函数的调用路径。  这是默认视图。  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-heavy-bottom-up.msft.png" alt-text="粗图表" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-heavy-bottom-up.msft.png":::
   粗图表  
:::image-end:::  

**树 \ (Top Down\) **。  显示调用结构的整体图片，从调用堆栈的顶部开始。  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-tree-top-down.msft.png" alt-text="树形图" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-tree-top-down.msft.png":::
   树形图  
:::image-end:::  

### <a name="exclude-functions"></a>排除函数  

若要从采样配置文件中排除函数，请选择该函数，然后选择排除选定函数 **\ (** 排除所选函数 ![ ][ImageExcludeIcon] \) 按钮。  已排除函数 \ (child\) 的请求函数 \ (child\) 由分配给排除函数 \ (child\) 的已分配内存收费。  

选择 **"还原所有函数** " (还原所有函数 \) 按钮，以将所有排除的函数 ![ ][ImageRestoreIcon] 还原回录制中。  

## <a name="view-sampling-profile-as-chart"></a>以图表模式查看采样配置文件  

"图表"视图提供一段时间的采样配置文件的直观表示形式。  

录制[采样配置文件后](#record-a-sampling-profile)，通过更改图表的排序顺序来查看记录作为[](#change-sort-order)一个饼**图**。  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart.msft.png" alt-text="饼图视图" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart.msft.png":::
   饼图视图  
:::image-end:::  

柱形图分为两部分。  

| index | 部件 | 说明 |  
| --- |:--- |:--- |  
| 1 | 概述 | 整个录制的鸟瞰图。  栏的高度对应于调用堆栈的深度。  因此，条形越高，调用堆栈越深。  |  
| 2 | 调用堆栈 | 这是在录制过程中调用的函数的深入视图。  水平轴为时间，垂直轴为调用堆栈。  堆栈从上到下进行组织。  因此，顶部的函数调用它下面的函数，等等。  |  

函数随机着色。  与其他面板中使用的颜色没有任何关联。  但是，函数在调用中始终具有相同的颜色，以便你可以观察每个运行时中的模式。  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-highlighted.msft.png" alt-text="批注的柱形图" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-highlighted.msft.png":::
   批注的柱形图  
:::image-end:::  

高调用堆栈不一定重要，它只是意味着调用了许多函数。  但宽条意味着函数需要很长时间才能完成。  这些是优化的候选项。  

### <a name="zoom-in-on-specific-parts-of-recording"></a>放大录制的特定部分  

在概述中选择、按住和拖动鼠标以放大调用堆栈的特定部分。  缩放后，调用堆栈自动显示所选录制的部分。  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-zoomed.msft.png" alt-text="图表缩放" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-zoomed.msft.png":::
   图表缩放  
:::image-end:::  

### <a name="view-function-details"></a>查看函数详细信息  

选择一个函数以查看"源"面板 **中** 的定义。  

将鼠标悬停在函数上可显示名称和计时数据。  提供了以下信息。  

| 详细信息 | 说明 |  
|:--- |:--- |  
| **名称** | 函数的名称。  |  
| **自调整大小** | 函数的当前调用大小，仅包括函数中的语句。  |  
| **总大小** | 此函数的当前调用及其调用的任何函数的大小。  |  
| **URL** | 函数定义的位置，其形式为定义函数的文件的名称，以及定义的行 `base.js:261` `base.js` `261` 号。  |  
<!--*   **Aggregated self time**.  Aggregate time for all invocations of the function across the recording, not including functions called by this function.  -->  
<!--*   **Aggregated total time**.  Aggregate total time for all invocations of the function, including functions called by this function.  -->  
<!--*   **Not optimized**.  If the profiler has detected a potential optimization for the function it lists it here.  -->  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-hover.msft.png" alt-text="在图表中查看函数详细信息" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-hover.msft.png":::
   在图表中查看函数详细信息  
:::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge 开发工具团队  

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
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于此处，[](https://developers.google.com/web/tools/chrome-devtools/rendering-tools/js-execution)由[一位（][KayceBasques]该链接人）\ (Technical Writer、Chrome DevTools \& Lighthouse\) 和[Meggin Kearney][MegginKearney] \ (Tech Writer\) 创作。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
