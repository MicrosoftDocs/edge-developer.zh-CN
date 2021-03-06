---
description: 时间线事件模式显示录制时触发的所有事件。  使用时间线事件引用了解有关每个时间线事件类型更多信息。
title: 时间线事件引用
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: 2a166c9eebc980682fa872e5ee8d213f2058b384
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398663"
---
<!-- Copyright Meggin Kearney and Flavio Copes

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->

# <a name="timeline-event-reference"></a>时间线事件引用  

时间线事件模式显示录制时触发的所有事件。  使用时间线事件引用了解有关每个时间线事件类型更多信息。  

## <a name="common-timeline-event-properties"></a>常见时间线事件属性  

某些详细信息存在于所有类型的事件中，而有些仅适用于特定事件类型。  本节列出了不同事件类型通用的属性。  特定于特定事件类型的属性在后续事件类型的引用中列出。  

| 属性 | 何时显示 |  
|:--- |:--- |  
| 聚合时间 | 对于具有 **嵌套事件的事件**，每类事件所花时间。 |  
| 调用堆栈 | 对于具有 **子事件的事件**，每类事件所花时间。 |  
| CPU 时间 | 记录的事件占用的 CPU 时间。 |  
| 详细信息 | 有关事件的其他详细信息。 |  
| Duration \ (at time-stamp\)  | 事件及其所有子项完成所用时间;时间戳是事件发生的时间，相对于录制开始的时间。 |  
| 自用时间 | 事件在没有其任何子项的情况下所用时间。 |  
| 已使用的堆大小 | 记录事件时应用程序使用的内存量，以及自上次采样以来使用的堆大小的增量 \ (+/-\) 变化量。 |  

<!--todo: add nested and child events (timelinetool) section when available -->  

## <a name="loading-events"></a>加载事件  

本节列出了属于"正在加载"类别的事件及其属性。  

| 事件 | 说明 |  
|:--- |:--- |  
| 分析 HTML |  Microsoft Edge 运行 HTML 分析算法。 |  
| 完成加载 |  网络请求已完成。 |  
| 接收数据 |  已接收请求的数据。  有一个或多个接收数据事件。 |  
| 接收响应 |  来自请求的初始 HTTP 响应。 |  
| 发送请求 |  已发送网络请求。 |  

### <a name="loading-event-properties"></a>加载事件属性  

| 属性 | 说明 |  
|:--- |:--- |  
| 资源 | 所请求资源的 URL。 |  
| 预览 | 仅预览请求的资源 \ (\) 。 |  
| Request 方法 | 用于请求 \ (`GET` 或 `POST` ，例如\) 。 |  
| 状态代码 | HTTP 响应代码。 |  
| MIME 类型 | 所请求资源的 MIME 类型。 |  
| 编码数据长度 | 请求的资源长度（以字节为单位）。 |  

## <a name="scripting-events"></a>脚本事件  

本节列出了属于脚本类别及其属性的事件。  

| 事件 | 说明 |  
|:--- |:--- |  
| 触发动画帧 | 触发的计划动画帧及其回调处理程序已调用。 |  
| 取消动画帧 |  已取消计划的动画帧。 |  
| GC 事件 |  发生垃圾回收。 |  
| DOMContentLoaded |  [DOMContentLoaded 事件][MDNWindowDOMContentLoadedEvent]由浏览器触发。  加载和分析页面的所有 DOM 内容时，将触发此事件。 |  
| 评估脚本 | 已评估脚本。 |  
| 事件 | JavaScript 事件 \ (例如 `mousedown` ，或 `key` \) 。 |  
| 函数调用 | 仅在浏览器进入 JavaScript 引擎\ (时，才出现顶级 JavaScript 函数调用) 。 |  
| 安装计时器 | 计时器是使用[setInterval () ][MDNWindowOrWorkerGlobalScopeSetInterval][或 setTimeout () 。 ][MDNWindowOrWorkerGlobalScopeSetTimeout] |  
| 请求动画帧 | 安排 `requestAnimationFrame()` 新帧的呼叫。 |  
| 删除计时器 | 已清除以前创建的计时器。 |  
| 时间 |  一个称为 [console.time () ][ConsoleApiTime]。 |  
| 时间结束 | 一个称为 [console.timeEnd () ][ConsoleApiTimeEnd]。 |  
| 计时器触发 | 使用 或 计划触发的 `setInterval()` 计时器 `setTimeout()` 。 |  
| XHR 就绪状态更改 | XMLHTTPRequest 的就绪状态已更改。 |  
| XHR 加载 | 已完成 `XMLHTTPRequest` 加载。 |  

### <a name="scripting-event-properties"></a>脚本事件属性  

| 属性 | 说明 |  
|:--- |:--- |  
| 计时器 ID | 计时器 ID。 |  
| 超时 | 计时器指定的超时。 |  
| 重复 | 指定计时器是否重复的布尔值。 |  
| 函数调用 | 已调用的函数。 |  

## <a name="rendering-events"></a>呈现事件  

本节列出了属于"呈现"类别及其属性的事件。  

| 事件 | 说明 |  
|:--- |:--- |  
| 无效布局 | 页面布局因 DOM 更改而失效。 |  
| 布局 | 已完成页面布局。 |  
| 重新计算样式 | Microsoft Edge 重新计算的元素样式。 |  
| 滚动 | 已滚动嵌套视图的内容。 |  

### <a name="rendering-event-properties"></a>呈现事件属性  

| 属性 | 说明 |  
|:--- |:--- |  
| 布局无效 | 对于布局记录，是导致布局失效的代码堆栈跟踪。 |  
| 需要布局的节点 | 对于布局记录，是中继启动前标记为需要布局的节点数。  这些节点通常是开发人员代码失效的节点，以及中继根的向上路径。 |  
| 布局树大小 | 对于布局记录，中继根 \ (Microsoft Edge 启动中继的节点下的节点总数) 。 |  
| 布局范围 | 可能的值是 \ (重新布局边界是 `Partial` DOM\) 或 的一部分 `Whole document` 。 |  
| 受影响的元素 | 对于"重新计算样式"记录，为受样式重新计算影响的元素数。 |  
| 样式失效 | 对于重新计算样式记录，提供导致样式无效的代码的堆栈跟踪。 |  

## <a name="painting-events"></a>绘制事件  

本节列出了属于"绘图"类别及其属性的事件。  

| 事件 | 说明 |  
|:--- |:--- |  
| 复合层 | Microsoft Edge 呈现引擎的复合图像层。 |  
| 图像解码 | 已解码图像资源。 |  
| 图像调整大小 | 图像已调整其本机尺寸的大小。 |  
| 画图 | 复合层已绘制到屏幕的一个区域。  将鼠标悬停在"画图"记录上会突出显示已更新的屏幕区域。 |  

### <a name="painting-event-properties"></a>绘制事件属性  

| 属性 | 说明 |  
|:--- |:--- |  
| 位置 | 对于 Paint 事件，绘制矩形的 x 和 y 坐标。 |  
| 维度 | 对于 Paint 事件，绘制区域的高度和宽度。 |  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge 开发工具团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->

[ConsoleApiTime]: /microsoft-edge/devtools-guide-chromium/console/api#time "time - 控制台 API 参考"  
[ConsoleApiTimeEnd]: /microsoft-edge/devtools-guide-chromium/console/api#timeend "timeEnd - 控制台 API 参考"  
<!--[EvaluatePerformanceTimelineTool]: timeline-tool "How to Use the Timeline Tool"  -->

[MDNWindowDOMContentLoadedEvent]: https://developer.mozilla.org/docs/Web/Events/DOMContentLoaded "窗口：DOMContentLoaded 事件|MDN"  
[MDNWindowOrWorkerGlobalScopeSetInterval]: https://developer.mozilla.org/docs/Web/API/WindowTimers/setInterval "WindowOrWorkerGlobalScope.setInterval () |MDN"  
[MDNWindowOrWorkerGlobalScopeSetTimeout]: https://developer.mozilla.org/docs/Web/API/WindowTimers/setTimeout "WindowOrWorkerGlobalScope.setTimeout () |MDN"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于此处，[](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/performance-reference)由[Meggin Kearney][MegginKearney] \ (Tech Writer\) 和[Flavio 管理][FlavioCopes]程序 \ (Full Stack Developer\) 创作。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
[FlavioCopes]: https://developers.google.com/web/resources/contributors/flaviocopes  
