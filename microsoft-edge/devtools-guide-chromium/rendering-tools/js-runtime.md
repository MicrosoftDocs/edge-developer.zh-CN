---
description: 使用 Microsoft Edge DevTools 内存面板识别昂贵的函数。
title: 加速 JavaScript 运行时
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: f3cf0440579865495f4afc8b1ae4e3940af7b04f
ms.sourcegitcommit: 99eee78698dc95b2a3fa638a5b063ef449899cda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/20/2020
ms.locfileid: "11125354"
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

# 加速 JavaScript 运行时  

使用 " **内存** " 面板识别昂贵的功能。  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-heavy-bottom-up.msft.png" alt-text="示例配置文件" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-heavy-bottom-up.msft.png":::
   示例配置文件  
:::image-end:::  

### 摘要  

*   准确记录所调用的函数和 **内存面板中的分配** 采样所需的内存量。  
*   将配置文件可视化为火焰图表。  
    
## 录制采样配置文件  

如果注意到 jank 在 JavaScript 中，请收集采样档案。  采样配置文件显示你的页面中的函数所用的运行时间。  

1.  转到 DevTools 的 " **内存** " 面板。  
1.  选择 " **分配采样** " 单选按钮。  
1.  选择 " **开始**"。  
1.  根据你尝试分析的内容，你可以重新加载页面、与页面交互或仅让页面运行。  
1.  完成后选择 " **停止** " 按钮。  
    
> [!NOTE]
> 您也可以使用 [控制台实用工具 API][DevtoolsConsoleUtilities] 从命令行记录和分组配置文件。  

## 查看采样配置文件  

完成录制后，DevTools 会自动在 "**采样配置文件**" 下填入来自录制的数据的**内存**面板。  

默认视图为 " **粗" ("自下而上" ) **。  此视图使你能够查看哪些函数对性能有最大影响，并检查这些函数的调用路径。  

### 更改排序顺序  

若要更改排序顺序，请选择 " **焦点选定函数** \ (![ 焦点选定函数 \ ) 图标" 旁边的下拉菜单 ][ImageFocusIcon] ，然后选择下列选项之一。

**图表**。  显示录制的按时间顺序的图表。  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart.msft.png" alt-text="示例配置文件" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart.msft.png":::
   火焰图  
:::image-end:::  

**粗 \ (下 ) **。  通过对性能的影响列出函数，并使你能够检查这些函数的调用路径。  这是默认视图。  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-heavy-bottom-up.msft.png" alt-text="示例配置文件" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-heavy-bottom-up.msft.png":::
   粗图  
:::image-end:::  

**树 \ (页首按 ) **。  显示从调用堆栈顶部开始的调用结构的整体图片。  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-tree-top-down.msft.png" alt-text="示例配置文件" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-tree-top-down.msft.png":::
   树形图  
:::image-end:::  

### 排除函数  

若要从采样配置文件中排除某个函数，请将其选中，然后选择 " **排除所选函数** \" (" ![ 排除所选函数 ][ImageExcludeIcon] \ ) " 按钮。  已排除的函数 \ (子 ) 的请求函数 \ (parent ) 已分配分配给已排除函数 \ (子 ) 的分配内存。  

选择 " **还原所有函数** \ (![ 还原所有函数 ][ImageRestoreIcon] \ ) " 按钮将所有已排除的函数还原到录制中。  

## 以图表形式查看采样配置文件  

"图表" 视图提供了一段时间内采样配置文件的可视化表示形式。  

[录制采样配置文件](#record-a-sampling-profile)后，通过将[排序顺序更改](#change-sort-order)为**图表**，可将录制查看为火焰图表。  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart.msft.png" alt-text="示例配置文件" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart.msft.png":::
   火焰图表视图  
:::image-end:::  

火焰图分成两部分。  

| 食指 | 部件 | 描述 |  
| --- |:--- |:--- |  
| raid-1 | 概述 | 整个录制的鸟瞰视图。  条形图的高度对应于调用堆栈的深度。  因此，栏越高，调用堆栈越深。  |  
| ppls-2 | 调用堆栈 | 这是在录制期间调用的函数的深入视图。  水平轴为时间，垂直轴为调用堆栈。  堆叠按从上到下排列。  因此，函数顶部称为该函数，依此类推。  |  

函数会随机着色。  与其他面板中使用的颜色没有关联。  但是，函数在调用中始终具有相同的颜色，以便你可以在每个运行时中查看模式。  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-highlighted.msft.png" alt-text="示例配置文件" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-highlighted.msft.png":::
   已标注的火焰图表  
:::image-end:::  

高调用堆栈不一定很重要，它只意味着调用了大量函数。  但宽条表示某个函数需要很长时间才能完成。  这些是优化的候选项。  

### 放大录制的特定部分  

选择、按住，然后在概述中向左和向右拖动鼠标，以放大调用堆栈的特定部分。  缩放后，调用堆栈自动显示所选录制部分。  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-zoomed.msft.png" alt-text="示例配置文件" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-zoomed.msft.png":::
   缩放图表  
:::image-end:::  

### 查看函数详细信息  

选择一个函数以在 " **源** " 面板中查看定义。  

将鼠标悬停在函数上以显示名称和计时数据。  提供以下信息。  

| 资料 | 描述 |  
|:--- |:--- |  
| **名称** | 函数的名称。  |  
| **自大小** | 函数的当前调用的大小，包括函数中的语句。  |  
| **总大小** | 此函数及其调用的任何函数的当前调用的大小。  |  
| **URL** | 函数定义在 where 的形式的位置 `base.js:261` `base.js` 是定义函数的文件的名称，并且 `261` 是定义的行号。  |  
<!--*   **Aggregated self time**.  Aggregate time for all invocations of the function across the recording, not including functions called by this function.  -->  
<!--*   **Aggregated total time**.  Aggregate total time for all invocations of the function, including functions called by this function.  -->  
<!--*   **Not optimized**.  If the profiler has detected a potential optimization for the function it lists it here.  -->  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-hover.msft.png" alt-text="示例配置文件" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-hover.msft.png":::
   在图表中查看函数的详细信息  
:::image-end:::  

## 与 Microsoft Edge 开发人员工具团队联系  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageExcludeIcon]: ../media/exclude-icon.msft.png  
[ImageFocusIcon]: ../media/focus-icon.msft.png  
[ImageRestoreIcon]: ../media/restore-icon.msft.png  

<!-- links -->  

[DevtoolsConsoleUtilities]: ../console/utilities.md "控制台实用工具 API 参考 |Microsoft 文档"  
[DevtoolsConsoleUtilitiesProfile]: ../console/utilities.md#profile "配置文件-控制台实用工具 API 参考 |Microsoft 文档"  
[DevtoolsConsoleUtilitiesProfileEnd]: ../console/utilities.md#profileend "profileEnd-控制台实用工具 API 参考 |Microsoft 文档"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面可在 [此处](https://developers.google.com/web/tools/chrome-devtools/rendering-tools/js-execution) 找到，并由 [Kayce Basques][KayceBasques] (技术作者、Chrome DevTools \ & Lighthouse \ ) 和 [Meggin Kearney][MegginKearney] \ (技术作者 \ ) 创作。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
