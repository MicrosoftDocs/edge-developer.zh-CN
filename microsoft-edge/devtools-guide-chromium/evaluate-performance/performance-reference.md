---
description: "\"日程表事件\" 模式显示录制时触发的所有事件。  使用日程表事件参考了解有关每个日程表事件类型的详细信息。"
title: 时间线事件参考
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 624035636e2231cf1f3cd1e2ba0fdda7e2e4fa00
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10992846"
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





# 时间线事件参考   




"日程表事件" 模式显示录制时触发的所有事件。  使用日程表事件参考了解有关每个日程表事件类型的详细信息。  

## 常用日程表事件属性  

某些详细信息存在于所有类型的事件中，而有些仅适用于某些事件类型。  本部分列出了不同事件类型的常见属性。  以下事件类型的参考中列出了特定于某些事件类型的属性。  

| 属性 | 何时显示 |  
|:--- |:--- |  
| 总时间 | 对于包含 **嵌套事件**的事件，每个事件类别所花的时间。 |  
| 调用堆栈 | 对于包含 **子事件**的事件，每个事件类别所花的时间。 |  
| CPU 时间 | 录制事件花费的 CPU 时间。 |  
| 详细信息 | 有关事件的其他详细信息。 |  
| Duration \ (时间戳 \ )  | 事件与所有子元素的完全相同的时间时间戳是事件发生的时间，相对于录制开始的时间。 |  
| 自我时间 | 事件在没有任何子级的情况下花费的时间。 |  
| 使用的堆大小 | 在记录事件时应用程序使用的内存量，增量 \ (+/\ ) 在上次取样后使用的堆大小发生变化。 |  

<!--todo: add nested and child events (timelinetool) section when available -->  

## 加载事件  

此部分列出了属于加载类别及其属性的事件。  

| 事件 | 描述 |  
|:--- |:--- |  
| 分析 HTML |  Microsoft Edge 运行了 HTML 分析算法。 |  
| 完成加载 |  网络请求已完成。 |  
| 接收数据 |  已收到请求的数据。  有一个或多个接收数据事件。 |  
| 接收答复 |  来自请求的初始 HTTP 响应。 |  
| 发送请求 |  已发送网络请求。 |  

### 加载事件属性  

| 属性 | 描述 |  
|:--- |:--- |  
| 资源 | 所请求的资源的 URL。 |  
| 预览 | 仅预览所请求的资源 \ (图像 \ ) 。 |  
| 请求方法 | 用于请求 \ (的 HTTP 方法 `GET` `POST` ，例如 \ ) 。 |  
| 状态代码 | HTTP 响应代码。 |  
| MIME 类型 | 所请求资源的 MIME 类型。 |  
| 编码数据长度 | 请求的资源的长度（以字节为单位）。 |  

## 脚本事件  

此部分列出了属于脚本类别及其属性的事件。  

| 事件 | 描述 |  
|:--- |:--- |  
| 激发的动画帧 | 引发计划动画帧，并调用其回调处理程序。 |  
| 取消动画帧 |  已取消计划的动画帧。 |  
| GC 事件 |  发生垃圾回收。 |  
| DOMContentLoaded |  浏览器激发了 [DOMContentLoaded 事件][MDNWindowDOMContentLoadedEvent] 。  当已加载和分析页面的所有 DOM 内容时，将引发此事件。 |  
| 计算脚本 | 已评估脚本。 |  
| 事件 | JavaScript 事件 \ (例如、 `mousedown` 或 `key` \ ) 。 |  
| 函数调用 | 执行了顶级 JavaScript 函数调用 \ (仅当浏览器输入 JavaScript 引擎 \ ) 时才出现。 |  
| 安装计时器 | 已使用 SetInterval 创建了计时器， [ ( # B1 ][MDNWindowOrWorkerGlobalScopeSetInterval] 或 [SetTimeout ( # B3 ][MDNWindowOrWorkerGlobalScopeSetTimeout]。 |  
| 请求动画帧 | `requestAnimationFrame()`通话安排了一个新帧。 |  
| 删除计时器 | 以前创建的计时器已清除。 |  
| 时间 |  名为 console 的脚本 [。时间 ( # B1 ][ConsoleApiTime]。 |  
| 结束时间 | 名为 [timeEnd ( # B1 ][ConsoleApiTimeEnd]的脚本。 |  
| 计时器已激发 | 通过 or 计划引发的计时器 `setInterval()` `setTimeout()` 。 |  
| XHR 准备状态更改 | XMLHTTPRequest 的准备状态已更改。 |  
| XHR 负载 | `XMLHTTPRequest`已完成加载。 |  

### 脚本事件属性  

| 属性 | 描述 |  
|:--- |:--- |  
| 计时器 ID | 计时器 ID。 |  
| 超时 | 计时器指定的超时值。 |  
| 播放 | 指定计时器是否重复的布尔值。 |  
| 函数调用 | 已调用的函数。 |  

## 呈现事件  

此部分列出了属于呈现类别及其属性的事件。  

| 事件 | 描述 |  
|:--- |:--- |  
| 使布局无效 | DOM 更改使页面布局失效。 |  
| 布局 | 已完成页面布局。 |  
| 重新计算样式 | Microsoft Edge 重新计算的元素样式。 |  
| 滚动 | 已滚动嵌套视图的内容。 |  

### 呈现事件属性  

| 属性 | 描述 |  
|:--- |:--- |  
| 布局无效 | 对于布局记录，导致布局失效的代码的堆栈跟踪。 |  
| 需要布局的节点 | 对于布局记录，在 relayout 开始之前标记为需要布局的节点数。  这些节点通常是由开发人员代码无效的节点，还包括指向 relayout 根的路径。 |  
| 布局树大小 | 对于布局记录，relayout 根节点下的节点总数 (Microsoft Edge 启动 relayout \ ) 的节点。 |  
| 布局范围 | 可能的值为 `Partial` \ (重新布局边界是 DOM \ ) 的一部分 `Whole document` 。 |  
| 受影响的元素 | 对于重新计算样式记录，受样式重新计算影响的元素数。 |  
| 样式无效 | 对于 "重新计算" 样式记录，提供导致样式无效的代码的堆栈跟踪。 |  

## 绘制事件  

此部分列出了属于 Painting 类别及其属性的事件。  

| 事件 | 描述 |  
|:--- |:--- |  
| 复合图层 | Microsoft Edge 呈现引擎的合成图像图层。 |  
| 图像解码 | 图像资源已解码。 |  
| 图像调整大小 | 从其本机尺寸调整图像大小。 |  
| 画图 | 复合图层已绘制到显示区域。  将鼠标悬停在 "画图" 记录上将突出显示已更新的显示区域。 |  

### 绘制事件属性  

| 属性 | 说明 |  
|:--- |:--- |  
| 位置 | 对于画图事件，绘制矩形的 x 和 y 坐标。 |  
| 三维 | 对于 "画图" 事件，即绘制区域的高度和宽度。 |  

 



<!-- image links -->  

<!-- links -->

[ConsoleApiTime]: /microsoft-edge/devtools-guide-chromium/console/api#time "时间-控制台 API 参考"  
[ConsoleApiTimeEnd]: /microsoft-edge/devtools-guide-chromium/console/api#timeend "timeEnd-控制台 API 参考"  
<!--[EvaluatePerformanceTimelineTool]: timeline-tool "How to Use the Timeline Tool"  -->

[MDNWindowDOMContentLoadedEvent]: https://developer.mozilla.org/docs/Web/Events/DOMContentLoaded "窗口： DOMContentLoaded 事件 |MDN"  
[MDNWindowOrWorkerGlobalScopeSetInterval]: https://developer.mozilla.org/docs/Web/API/WindowTimers/setInterval "WindowOrWorkerGlobalScope setInterval ( # A1 |MDN"  
[MDNWindowOrWorkerGlobalScopeSetTimeout]: https://developer.mozilla.org/docs/Web/API/WindowTimers/setTimeout "WindowOrWorkerGlobalScope setTimeout ( # A1 |MDN"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面可在 [此处](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/performance-reference) 找到，并由 [Meggin Kearney][MegginKearney] (技术作者 \ ) 和 [Flavio Copes][FlavioCopes] (完全堆栈开发人员 \ ) 创作。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
[FlavioCopes]: https://developers.google.com/web/resources/contributors/flaviocopes  
