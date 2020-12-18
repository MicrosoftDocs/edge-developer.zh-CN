---
description: Microsoft Edge DevTools 网络面板功能的综合参考。
title: 网络分析参考
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/17/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: c600197ffa0e415fe42aecc704a523d1b23f8260
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11230752"
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

# 网络分析参考  

在此 Microsoft Edge DevTools 网络分析功能的全面参考中，发现分析页面加载方式的新增方法。  

## 记录网络请求  

默认情况下，DevTools 在网络面板中记录所有网络**** 请求，只要 DevTools 打开。  

:::image type="complex" source="../media/network-network-panel.msft.png" alt-text="网络面板" lightbox="../media/network-network-panel.msft.png":::
   网络**面板**  
:::image-end:::  

### 停止记录网络请求  

若要停止录制请求，请完成以下步骤。  

1.  在" **网络** "面板上，选择"停止 **录制网络** 日志\ (![ 停止录制网络日志 ][ImageRecordOnIcon] \) 。  它将变为灰色，以指示 DevTools 不再录制请求。  
1.  在网络 (焦点时，选择 `Control` + `E` \ (Windows、Linux\) 或 `Command` + `E` \ (macOS\) 。 ****  

### 清除请求  

在 **"网络** (选择"清除) "以清除"请求" ![ ][ImageClearIcon] 表中的所有请求。 ****  

:::image type="complex" source="../media/network-network-clear-button.msft.png" alt-text=""清除"按钮" lightbox="../media/network-network-clear-button.msft.png":::
   " **清除"** 按钮  
:::image-end:::  

### 跨页面加载保存请求  

若要跨页面加载保存请求，在"网络****"面板上，打开"保留**日志"** 复选框。  DevTools 保存所有请求，直到禁用 **保留日志**。  

:::image type="complex" source="../media/network-network-preserve-log.msft.png" alt-text=""保留日志"复选框" lightbox="../media/network-network-preserve-log.msft.png":::
   " **保留日志"** 复选框  
:::image-end:::  

### 在页面加载期间捕获屏幕截图  

捕获屏幕截图，以分析在等待页面加载时为用户显示的内容。  

若要启用屏幕截图，请选择 **"网络设置**"，在"**** 网络"面板上，打开"捕获屏幕截图 **"** 复选框。  

在网络面板聚焦时**** 刷新页面以捕获屏幕截图。  

捕获屏幕截图后，可以按照以下方式与其交互。  

*   将鼠标悬停在屏幕截图上可显示捕获该屏幕截图的点。  在"概述"窗格中显示一条 **黄色** 线条。  
*   选择屏幕的缩略图以筛选出捕获屏幕截图后发生的任何请求。  
*   双击缩略图可放大它。  

:::image type="complex" source="../media/network-network-screenshot-hover.msft.png" alt-text="将鼠标悬停在屏幕截图上" lightbox="../media/network-network-screenshot-hover.msft.png":::
   将鼠标悬停在屏幕截图上  
:::image-end:::  

<!--  ### Replay XHR request  -->

<!--  To replay an XHR request, hover on the request in the Requests table, open the contextual menu \(right-click\), and choose **Replay XHR**.  -->

<!--  
:::image type="complex" source="../media/network-replay-xhr.msft.png" alt-text="Choose Replay XHR" lightbox="../media/network-replay-xhr.msft.png":::
   Choose Replay XHR  
:::image-end:::  
-->  

## 更改加载行为  

### 通过禁用浏览器缓存模拟第一次访问者  

若要模拟首次用户访问网站时的体验，请打开"禁用 **缓存"** 复选框。  DevTools 禁用浏览器缓存。  此功能可以更准确地模拟第一次用户体验，因为请求在重复访问时从浏览器缓存提供。  

:::image type="complex" source="../media/network-network-disable-cache-checkbox.msft.png" alt-text=""禁用缓存"复选框" lightbox="../media/network-network-disable-cache-checkbox.msft.png":::
   " **禁用缓存"** 复选框  
:::image-end:::  

#### 从"网络条件"箱禁用浏览器缓存  

如果要在其他 DevTools 面板中操作时禁用缓存，请使用"网络条件"箱。  

1.  打开 **"网络条件"** 箱。  
1.  打开\ (或关闭\) **禁用缓存复选框** 。  

<!--todo: add network condition section when available -->  

### 手动清除浏览器缓存  

若要随时手动清除浏览器缓存，请打开上下文菜单 \ (右键单击\) 请求表中的任意位置，然后选择 **"清除浏览器缓存"。**  

:::image type="complex" source="../media/network-network-clear-browser-cache.msft.png" alt-text="选择"清除浏览器缓存"" lightbox="../media/network-network-clear-browser-cache.msft.png":::
   选择 **"清除浏览器缓存"**  
:::image-end:::  

### 脱机模拟  

名为"渐进 Web 应用"[][DevtoolsProgressiveWebApps]的新 Web 应用类在服务工作者的帮助下脱机**工作**。  你可能会发现，在生成此类应用时，快速模拟没有数据连接的设备会很有用。  

<!--[ServiceWorkers]: /web/fundamentals/getting-started/primers/service-workers  -->

选择 **"联机**"下拉菜单，在 **"预设**"下搜索，然后选择****"脱机"以模拟脱机网络体验。  

:::image type="complex" source="../media/network-network-offline-dropdown.msft.png" alt-text=""脱机"下拉菜单" lightbox="../media/network-network-offline-dropdown.msft.png":::
   " **脱机** "下拉菜单  
:::image-end:::  

### 模拟慢速网络连接  

从"联机"下拉菜单中模拟慢速 3G、快速 3G 和其他连接速度。 ****  

:::image type="complex" source="../media/network-network-throttling-menu.msft.png" alt-text=""限制"下拉菜单" lightbox="../media/network-network-throttling-menu.msft.png":::
   " **限制"** 下拉菜单  
:::image-end:::  

你可以选择不同的预设，如慢速 3G 或快速 3G。  若要添加自己的自定义预设，请打开限制菜单，然后选择"**自定义**  >  **添加"。**  

DevTools 在"网络"选项卡旁边**** 显示一个警告图标，提醒你已启用限制。  

#### 模拟来自"网络条件"箱的慢速网络连接  

如果要在其他 DevTools 面板中工作时限制网络连接，请使用"网络条件"箱。  

1.  打开 **"网络条件"** 箱。  
1.  从限制菜单中 **选择连接** 速度。  

<!--todo: add network condition section when available -->  

### 手动清除浏览器 Cookie  

若要随时手动清除浏览器 Cookie，请将鼠标悬停在"请求"表中的任意位置，打开上下文菜单 \ (右键单击\) ，然后选择"清除浏览器**Cookie"。**  

:::image type="complex" source="../media/network-network-clear-browser-cookies.msft.png" alt-text="选择"清除浏览器 Cookie"" lightbox="../media/network-network-clear-browser-cookies.msft.png":::
   选择 **"清除浏览器 Cookie"**  
:::image-end:::  

### 覆盖用户代理  

若要手动覆盖用户代理，请使用以下步骤。  

1.  打开 **"网络条件"** 箱。  
1.  关闭"自动 **选择"** 复选框。  
1.  从菜单中选择用户代理选项，或在文本框中输入自定义选项。  

<!--todo: add network condition section when available -->  

## 筛选请求  

### 按属性筛选请求  

使用 **"** 筛选器"文本框按属性（如请求的域或大小）筛选请求。  

如果未显示文本框，"筛选器 **"窗格可能** 处于隐藏状态。  
有关详细信息，请导航到" [隐藏筛选器"窗格](#hide-the-filters-pane)。  

:::image type="complex" source="../media/network-network-filters-textbox.msft.png" alt-text=""筛选器"文本框" lightbox="../media/network-network-filters-textbox.msft.png":::
   " **筛选器** "文本框  
:::image-end:::  

通过用空格分隔每个属性，可以同时使用多个属性。  例如， `mime-type:image/png larger-than:1K` 显示大于 1 KB 的所有 PNG。  多属性筛选器等效于 `AND` 操作。  `OR` 操作当前不受支持。  

受支持的属性的完整列表。  

| 属性 | 详细信息 |  
|:--- | :--- |  
| `domain` | 仅显示来自指定域的资源。  可以使用通配符 \ (`*` \) 包含多个域。  例如， `*.com` 显示以 . `.com`  DevTools 使用找到的所有域填充自动完成下拉菜单。 |  
| `has-response-header` | 显示包含指定 HTTP 响应标头的资源。  DevTools 使用找到的所有响应标头填充自动完成下拉列表。 |  
| `is` | 用于 `is:running` 查找 `WebSocket` 资源。 |  
| `larger-than` | 以字节为单位显示大于指定大小的资源。  设置值 `1000` 等效于设置值 `1k` 。 |  
| `method` | 显示通过指定的 HTTP 方法类型检索的资源。  DevTools 使用找到的所有 HTTP 方法填充下拉列表。 |  
| `mime-type` | 显示指定 MIME 类型的资源。  DevTools 使用找到的所有 MIME 类型填充下拉列表。 |  
| `mixed-content` | 显示所有混合内容资源 \ (\) 或只显示当前显示的 `mixed-content:all` \ (`mixed-content:displayed` \) 。 |  
| `scheme` | 显示通过未受保护的 HTTP \ (`scheme:http` \) 或受保护的 HTTPS \ (`scheme:https` \) 检索的资源。 |  
| `set-cookie-domain` | 显示具有与指定值匹配的属性的标头 `Set-Cookie` `Domain` 的资源。  DevTools 使用找到的所有 Cookie 域填充自动完成。 |  
| `set-cookie-name` | 显示具有与指定 `Set-Cookie` 值匹配的名称的标题的资源。  DevTools 使用找到的所有 Cookie 名称填充自动完成。 |  
| `set-cookie-value` | 显示标题具有与指定 `Set-Cookie` 值匹配的值的资源。  DevTools 使用找到的所有 Cookie 值填充自动完成。 |  
| `status-code` | 显示与特定 HTTP 状态代码匹配的资源。  DevTools 使用找到的所有状态代码填充自动完成下拉菜单。 |  

### 按类型筛选请求  

若要按请求类型筛选请求，请选择"网络"面板上的以下按钮 **之** 一。  

:::row:::
   :::column span="1":::
      **XHR**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **JS**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **CSS**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **Img**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **Media**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **字体**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **Doc**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **WS**  
   :::column-end:::
   :::column span="2":::
      WebSocket。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **清单**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **Other**  
   :::column-end:::
   :::column span="2":::
      任何其他类型未列出。  
   :::column-end:::
:::row-end:::  

如果未显示按钮，则 **可能会隐藏"筛选器** "窗格。  
有关详细信息，请导航到" [隐藏筛选器"窗格](#hide-the-filters-pane)。  

若要同时启用多个类型筛选器，请按住 `Control` \ (Windows、Linux\) 或 `Command` \ (macOS\) ，然后选择。  

:::image type="complex" source="../media/network-network-type-filters.msft.png" alt-text="使用类型筛选器显示 JS、CSS 和文档资源" lightbox="../media/network-network-type-filters.msft.png":::
   使用类型筛选器显示 JS、CSS 和文档资源  
:::image-end:::  

### 按时间筛选请求  

选择并向左或向右拖动"概述****"窗格，以仅显示该时间帧内处于活动状态的请求。  筛选器包含。  将显示突出显示时间内处于活动状态的任何请求。  

:::image type="complex" source="../media/network-network-overview-filter.msft.png" alt-text="筛选出在 300 毫秒左右处于非活动状态的任何请求" lightbox="../media/network-network-overview-filter.msft.png":::
   筛选出在 300 毫秒左右处于非活动状态的任何请求  
:::image-end:::  

### 隐藏数据 URL  

[数据 URL][MDNHTTPDataURIs] 是嵌入到其他文档中的小文件。  在"请求"表中显示的任何以数据 URL 开头 `data:` 的请求都是数据 URL。  

若要隐藏请求，请关闭"隐藏 **数据 URL"** 复选框。  

:::image type="complex" source="../media/network-network-hide-data-urls.msft.png" alt-text=""隐藏数据 URL"复选框" lightbox="../media/network-network-hide-data-urls.msft.png":::
   " **隐藏数据 URL"** 复选框  
:::image-end:::  

## 对请求进行排序  

默认情况下，Requests 表中的请求按启动时间排序，但您可以使用其他条件对表进行排序。  

### 按列排序  

选择"请求"中任何列的标题，以按该列对请求进行排序。  

### 按活动阶段排序  

若要更改瀑布对请求的排序方式，请将鼠标悬停在请求表的标题上，打开上下文菜单 \ (右键单击\) ，将鼠标悬停在瀑布上，然后选择下列**** 选项之一。  

:::row:::
   :::column span="1":::
      **开始时间**  
   :::column-end:::
   :::column span="2":::
      启动的第一个请求位于顶部。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **响应时间**  
   :::column-end:::
   :::column span="2":::
      开始下载的第一个请求位于顶部。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **结束时间**  
   :::column-end:::
   :::column span="2":::
      完成的第一个请求位于顶部。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **总持续时间**  
   :::column-end:::
   :::column span="2":::
      具有最短连接设置和请求或响应的请求位于顶部。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **延迟**  
   :::column-end:::
   :::column span="2":::
      等待响应最短时间的请求位于顶部。  
   :::column-end:::
:::row-end:::  

这些说明假定每个选项的排名从最短到最长。  选择" **瀑布"列** 的标题以反转顺序。  

:::image type="complex" source="../media/network-network-waterfall-total-duration.msft.png" alt-text="按总持续时间对瀑布进行排序" lightbox="../media/network-network-waterfall-total-duration.msft.png":::
   按总持续时间 \ (对瀑布进行排序 每个栏的较浅部分是等待的时间，而较暗的部分是下载字节\)   
:::image-end:::  

## 分析请求  

只要 DevTools 打开，它将记录网络面板中 **的所有** 请求。  
使用"网络"面板分析请求。  

### 显示请求日志  

使用 Requests 表可显示打开 DevTools 时所提出所有请求的日志。  若要显示有关每个项目的详细信息，请选择或将鼠标悬停在请求上。  

:::image type="complex" source="../media/network-network-requests-table.msft.png" alt-text="Requests 表" lightbox="../media/network-network-requests-table.msft.png":::
   Requests 表  
:::image-end:::  

默认情况下，Requests 表将显示以下列。  

:::row:::
   :::column span="1":::
      **名称**  
   :::column-end:::
   :::column span="2":::
      资源的文件名或标识符。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **状态**  
   :::column-end:::
   :::column span="2":::
      HTTP 状态代码。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **类型**  
   :::column-end:::
   :::column span="2":::
      所请求资源的 MIME 类型。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **发起人**  
   :::column-end:::
   :::column span="2":::
      以下对象或进程启动请求。  
      
      *   **分析程序**  Microsoft Edge 的 HTML 分析程序。  
      *   **重定向**  HTTP 重定向。  
      *   **脚本**  JavaScript 函数。  
      *   **其他**  一些其他过程或操作，例如使用链接导航到页面或在地址栏中输入 URL。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **大小**  
   :::column-end:::
   :::column span="2":::
      服务器提供的响应标头和响应正文的组合大小。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **时间**  
   :::column-end:::
   :::column span="2":::
      从请求开始到响应中最后一个字节的接收的总持续时间。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [瀑布](#display-the-timing-relationship-of-requests)  
   :::column-end:::
   :::column span="2":::
      每个请求的活动的直观细分。  
   :::column-end:::
:::row-end:::  

#### 添加或删除列  

将鼠标悬停在 Requests 表的标题上，打开上下文菜单 \ (右键单击\) ，然后选择一个选项来隐藏或显示它。  当前显示的选项在每个项目旁边都有选中标记。  

:::image type="complex" source="../media/network-network-requests-add-column.msft.png" alt-text="向"请求"表添加列" lightbox="../media/network-network-requests-add-column.msft.png":::
   向"请求"表添加列  
:::image-end:::  

#### 添加自定义列  

若要向 Requests 表添加自定义列，请将鼠标悬停在 Requests 表的标题上，打开上下文菜单 \ (右键单击\) ，然后选择"响应标头**** 管理  >  **标头**列"。  

:::image type="complex" source="../media/network-network-requests-add-custom.msft.png" alt-text="向"请求"表添加自定义列" lightbox="../media/network-network-requests-add-custom.msft.png":::
   向"请求"表添加自定义列  
:::image-end:::  

### 显示请求的计时关系  

使用瀑布显示请求的计时关系。  
瀑布的默认组织使用请求的开始时间。  
因此，距离左侧较远的请求在较右边的请求之前启动。  

若要查看对瀑布进行排序的不同方法，请导航到按 [活动阶段排序](#sort-by-activity-phase)。  

:::image type="complex" source="../media/network-network-requests-waterfall.msft.png" alt-text="请求窗格的"瀑布"列" lightbox="../media/network-network-requests-waterfall.msft.png":::
   请求窗格的"瀑布 **"** 列  
:::image-end:::  

<!-- ### Analyze the frames of a WebSocket Connection  -->

<!--To review the frames of a WebSocket connection, use the following steps.  

1.  Choose the URL of the WebSocket connection, under the **Name** column of the Requests table.  
1.  Choose the **Frames** tab.  The table shows the last 100 frames.  

To refresh the table, re-choose the name of the WebSocket connection under the **Name** column of the Requests table.  -->

<!--
:::image type="complex" source="../media/network-frames.msft.png" alt-text="The Frames tab" lightbox="../media/network-frames.msft.png":::
   The **Frames** tab  
:::image-end:::  
-->

<!--The table contains the following three columns.  

*   **Data**.  The message payload.  If the message is plain text, it is displayed here.  For binary opcodes, this column displays the name and code of the opcode.  The following opcodes are supported: Continuation Frame, Binary Frame, Connection Close Frame, Ping Frame, and Pong Frame.  
*   **Length**.  The length of the message payload, in bytes.  
*   **Time**.  The time when the message was received or sent.  -->

<!--Messages are color-coded according to each type.  

*   Outgoing text messages are light-green.  
*   Incoming text messages are white.  
*   WebSocket opcodes are light-yellow.  
*   Errors are light-red.  -->

### 显示响应正文的预览  

若要显示响应正文的预览，请使用以下步骤。  

1.  在"请求"表的"名称" **列下** 选择请求的 URL。  
1.  选择 **"预览"** 选项卡。  

"预览"选项卡对显示图像非常有用。  

:::image type="complex" source="../media/network-network-resources-preview.msft.png" alt-text="“预览”选项卡" lightbox="../media/network-network-resources-preview.msft.png":::
   “**预览**”选项卡  
:::image-end:::  

### 显示响应正文  

若要向请求显示响应正文，请使用以下步骤。  

1.  在"请求"表的"名称" **列下** 选择请求的 URL。  
1.  选择" **响应"** 选项卡。  

:::image type="complex" source="../media/network-network-resources-response.msft.png" alt-text="“响应”选项卡" lightbox="../media/network-network-resources-response.msft.png":::
   “**响应**” 选项卡  
:::image-end:::  

### 显示 HTTP 标头  

若要显示有关请求的 HTTP 标头数据，请使用以下步骤。  

1.  在"请求"表的"名称" **列下** 选择请求的 URL。  
1.  选择 **"标题"** 选项卡。  

:::image type="complex" source="../media/network-resources-headers.msft.png" alt-text="“标头”选项卡" lightbox="../media/network-resources-headers.msft.png":::
   “**标头**”选项卡  
:::image-end:::  

#### 显示 HTTP 标头源  

默认情况下，"标题"选项卡按字母顺序显示标题名称。  若要按接收的顺序显示 HTTP 头名称，请使用以下步骤。  

1.  打开 **您** 感兴趣的请求的"标题"选项卡。  有关详细信息，请导航到["显示 HTTP 标头"。](#display-http-headers)  
1.  选择 **"请求**标头"或"响应头 **"部分****旁边的**视图源。  

### 显示查询字符串参数  

若要以可读格式显示 URL 的查询字符串参数，请使用以下步骤。  

1.  打开 **您** 感兴趣的请求的"标题"选项卡。  有关详细信息，请导航到["显示 HTTP 标头"。](#display-http-headers)  
1.  转到" **查询字符串参数"** 部分。  

:::image type="complex" source="../media/network-network-resources-headers-query-string-parameters.msft.png" alt-text=""查询字符串参数"部分" lightbox="../media/network-network-resources-headers-query-string-parameters.msft.png":::
   " **查询字符串参数"** 部分  
:::image-end:::  

#### 显示查询字符串参数源  

若要显示请求的查询字符串参数源，请使用以下步骤。  

1.  转到"查询字符串参数"部分。  有关详细信息，请导航到["显示查询字符串参数"。](#display-query-string-parameters)  
1.  选择 **视图源**。  

#### 显示 URL 编码的查询字符串参数  

若要以可读格式显示查询字符串参数，但保留编码，请使用以下步骤。  

1.  转到"查询字符串参数"部分。  有关详细信息，请导航到["显示查询字符串参数"。](#display-query-string-parameters)  
1.  选择**编码的视图 URL。**  

### 显示 Cookie  

若要显示请求的 HTTP 标头中发送的 Cookie，请使用以下步骤。  

1.  在"请求"表的"名称" **列下** 选择请求的 URL。  
1.  选择 **"Cookie"** 选项卡。  

<!--For more information about each of the columns, navigate to [Fields][ManageDataCookiesFields].  -->  

<!--[ManageDataCookiesFields]: manage-data/cookies#fields  -->  
<!--TODO: add link when section is available -->  

:::image type="complex" source="../media/network-network-resources-cookies.msft.png" alt-text=""Cookie"选项卡" lightbox="../media/network-network-resources-cookies.msft.png":::
   "Cookie"选项卡  
:::image-end:::  

### 显示请求的时间细分  

若要显示请求的时间细分，请使用以下步骤。  

1.  在"请求"表的"名称" **列下** 选择请求的 URL。  
1.  选择 **"计时"** 选项卡。  

若要更快地访问数据，请导航到"[预览计时细分"。](#preview-a-timing-breakdown)  

有关"计时"选项卡中可能显示的每个阶段详细信息，请导航到**** 说明的"计时["细分阶段](#timing-breakdown-phases-explained)。  

:::image type="complex" source="../media/network-network-resources-timing.msft.png" alt-text="“计时”选项卡" lightbox="../media/network-network-resources-timing.msft.png":::
   “**计时**”选项卡  
:::image-end:::  

有关每个阶段详细信息。  

有关访问屏幕详细信息，请导航到"[显示计时细分"。](#display-the-timing-breakdown-of-a-request)  

#### 预览计时细分  

若要显示请求的时间细分预览，在"请求"表的 **"瀑布** "列中，将鼠标悬停在请求的条目上。  

若要详细了解如何在不悬停的情况下访问数据，请导航到"[显示请求的时间细分"。](#display-the-timing-breakdown-of-a-request)  

:::image type="complex" source="../media/network-network-resources-waterfall-hover.msft.png" alt-text=">预览请求的时间细分" lightbox="../media/network-network-resources-waterfall-hover.msft.png":::
   预览请求的时间细分  
:::image-end:::  

#### 说明的时间细分阶段  

有关"计时"选项卡中可能显示 **的每个阶段详细信息** 。  

:::row:::
   :::column span="1":::
      **排队**  
   :::column-end:::
   :::column span="2":::
      当以下任一项为真时，浏览器将队列请求排成队列。  
      
      *   存在更高优先级的请求。  
      *   为同一源打开了六个 TCP 连接，这是限制。  仅适用于 HTTP/1.0 和 HTTP/1.1。  
      *   浏览器在磁盘缓存中简要分配空间。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **已停止**  
   :::column-end:::
   :::column span="2":::
      请求因队列中所述的任何原因 **而停止**。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **DNS 查找**  
   :::column-end:::
   :::column span="2":::
      浏览器正在解析请求的 IP 地址。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **初始连接**  
   :::column-end:::
   :::column span="2":::
      浏览器建立包括 TCP 握手、TCP 重试和协商安全套接字层在内的连接。
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **代理协商**  
   :::column-end:::
   :::column span="2":::
      浏览器正在与代理服务器协商 [请求][WikiProxyServer]。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **发送的请求**  
   :::column-end:::
   :::column span="2":::
      正在发送请求。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **ServiceWorker 准备**  
   :::column-end:::
   :::column span="2":::
      浏览器正在启动服务工作进程。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **对 ServiceWorker 的请求**  
   :::column-end:::
   :::column span="2":::
      请求将发送给服务工作者。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **等待 \ (TTFB\) **  
   :::column-end:::
   :::column span="2":::
      浏览器正在等待响应的第一个字节。  TTFB 代表第一个字节的时间。  此时间包括一次延迟往返以及服务器准备响应所花时间。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **内容下载**  
   :::column-end:::
   :::column span="2":::
      浏览器正在接收响应。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **接收推送**  
   :::column-end:::
   :::column span="2":::
      浏览器通过 HTTP/2 服务器推送接收此响应的数据。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **读取推送**  
   :::column-end:::
   :::column span="2":::
      浏览器正在读取之前收到的本地数据。  
   :::column-end:::
:::row-end:::  

### 显示发起方和依赖项  

若要显示请求的发起方和依赖项，请将 `Shift` 鼠标悬停在请求表中的请求上。  DevTools 颜色：发起人以绿色显示，依赖关系显示为红色。  

:::image type="complex" source="../media/network-network-resources-initiators-dependencies.msft.png" alt-text="显示请求的发起方和依赖项" lightbox="../media/network-network-resources-initiators-dependencies.msft.png":::
   显示请求的发起方和依赖项  
:::image-end:::  

当 Requests 表按时间顺序排序时，如果将鼠标悬停在行上，则它前面的行将显示一个绿色请求。  绿色请求是依赖项的发起者。  如果前一行上显示另一个绿色请求，则较高的请求是发起者发起人。  以此类推。  

### 显示加载事件  

DevTools 在网络面板上的 `DOMContentLoaded` 多个 `load` 位置显示和事件的计时。 ****  事件 `DOMContentLoaded` 的颜色为蓝色， `load` 事件为红色。  

:::image type="complex" source="../media/network-network-requests-load-events.msft.png" alt-text="DOMContentLoaded 和"网络"面板上的加载事件的位置" lightbox="../media/network-network-requests-load-events.msft.png":::
   "网络" `DOMContentLoaded` 面板 `load` 上和事件的位置****  
:::image-end:::  

### 显示请求总数  

"摘要"窗格中的"网络"面板底部**** 列出了请求**总数**。  

> [!CAUTION]
> 此数字仅跟踪自 DevTools 打开后记录的请求。  如果在打开 DevTools 之前发生了其他请求，则这些请求不会计算在内。  

:::image type="complex" source="../media/network-network-total-requests.msft.png" alt-text="自打开 DevTools 以来的请求总数" lightbox="../media/network-network-total-requests.msft.png":::
   自打开 DevTools 以来的请求总数  
:::image-end:::  

### 显示总下载大小  

请求的总下载大小在网络面板底部的"摘要"******窗格中列出。**  

> [!CAUTION]
> 此数字仅跟踪自 DevTools 打开后记录的请求。  如果在打开 DevTools 之前发生了其他请求，则以前的请求不会计算在内。  

:::image type="complex" source="../media/network-network-total-download-size.msft.png" alt-text="请求的总下载大小" lightbox="../media/network-network-total-download-size.msft.png":::
   请求的总下载大小  
:::image-end:::  

若要验证浏览器取消压缩每个项目后资源的大小，请导航以显示资源的未压缩 [大小](#display-the-uncompressed-size-of-a-resource)。  

### 显示导致请求的堆栈跟踪  

JavaScript 语句请求资源后，将鼠标悬停在 **发起** 方列上，以显示导致请求的堆栈跟踪。  

<!-- [codepen.io/contoso/pen/yLBrOWa?editors=0010#0](https://codepen.io/contoso/pen/yLBrOWa?editors=0010#0) -->  

<!--
```javascript
function init() {
  getData();
}

function getData() {
  fetch('https:/httpbin.org/get?message=hi');
}

init();
```  
-->  

:::image type="complex" source="../media/network-network-requests-initiator-stack.msft.png" alt-text="导致资源请求的堆栈跟踪" lightbox="../media/network-network-requests-initiator-stack.msft.png":::
   导致资源请求的堆栈跟踪  
:::image-end:::  

### 显示资源的未压缩大小  

打开" **使用大型请求行"** 复选框，然后查看"大小" **列的底部值** 。  

:::image type="complex" source="../media/network-network-requests-uncompressed-compare.msft.png" alt-text="未压缩资源的示例" lightbox="../media/network-network-requests-uncompressed-compare.msft.png":::
   未压缩资源的示例 \ (通过网络发送的文件的压缩大小为 `jquery-3.3.1.min.js` `29.9 KB` `84.9 KB` \)   
:::image-end:::  

## 导出请求数据  

### 将所有网络请求保存到 HAR 文件  

若要将所有网络请求保存到 HAR 文件，请完成以下步骤。  

1.  将鼠标悬停在 Requests 表中的任何请求上，然后打开上下文菜单 \ (右键单击\) 。  
1.  选择 **"保存为具有内容的 HAR"。**  DevTools 将打开 DevTools 后发生的所有请求保存到 HAR 文件中。  无法筛选请求。  您也无法保存单个请求。  

保存 HAR 文件后，你可以将其导入回 DevTools 进行分析。  只需将 HAR 文件拖放到 Requests 表中。  
<!--For more information, navigate to also [HAR Analyzer][HARAnalyzer].  -->  

<!--[HARAnalyzer]: https://toolbox.alphabetapps.com/apps/har_analyzer  -->  
<!--Todo: add section link when content is available  -->  

:::image type="complex" source="../media/network-network-requests-save-har-content.msft.png" alt-text="选择"将内容另存为 HAR"" lightbox="../media/network-network-requests-save-har-content.msft.png":::
   选择 **"将内容另存为 HAR"**  
:::image-end:::  

### 将一个或多个请求复制到剪贴板  

在"**** 请求"表的"名称"列下，将鼠标悬停在请求上，打开上下文菜单 \ (右键单击\) ，将鼠标悬**** 停在"复制"上，然后选择下列选项之一。  

| 名称 | 详细信息 |  
|:--- |:--- |  
| **复制链接地址** | 将请求的 URL 复制到剪贴板。 |  
| **复制响应** | 将响应正文复制到剪贴板。 |  
| **复制为提取** | &nbsp; |  
| **复制为 cURL** | 将请求复制为 cURL 命令。 |  
| **全部复制为提取** | &nbsp; |  
| **全部复制为 cURL** | 复制所有请求作为 cURL 命令链。 |  
| **全部复制为 HAR** | 复制所有请求作为 HAR 数据。 |  

<!--
:::row:::
   :::column span="1":::
      **Copy Link Address**  
   :::column-end:::
   :::column span="2":::
      Copy the URL of the request to the clipboard.  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **Copy Response**  
   :::column-end:::
   :::column span="2":::
      Copy the response body to the clipboard.  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **Copy as Fetch**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **Copy as cURL**  
   :::column-end:::
   :::column span="2":::
      Copy the request as a cURL command.  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **Copy All as Fetch**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **Copy All as cURL**  
   :::column-end:::
   :::column span="2":::
      Copy all requests as a chain of cURL commands.  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **Copy All as HAR**  
   :::column-end:::
   :::column span="2":::
      Copy all requests as HAR data.  
   :::column-end:::
:::row-end:::  
-->  

:::image type="complex" source="../media/network-network-requests-copy-response.msft.png" alt-text="选择"复制响应"" lightbox="../media/network-network-requests-copy-response.msft.png":::
   选择 **"复制响应"**  
:::image-end:::  

### 将格式化的响应 JSON 复制到剪贴板  

选择网络请求并导航到 **"标题"** 窗格。  若要复制响应的 JSON 值，请导航**** 到"请求负载"，将鼠标悬停在 JSON 响应内容上，打开上下文菜单 \ (右键单击\) ，然后选择"复制**值**"。  

:::row:::
   :::column span="":::
        :::image type="complex" source="../media/network-header-copy-property-value.msft.png" alt-text="在上下文菜单中复制值" lightbox="../media/network-header-copy-property-value.msft.png":::
          **在上下文菜单中** 复制值  
        :::image-end:::  
   :::column-end:::
   :::column span="":::
        :::image type="complex" source="../media/network-header-paste-property-value.msft.png" alt-text="Visual Studio格式响应 JSON 的代码" lightbox="../media/network-header-paste-property-value.msft.png":::
          将格式化的响应 JSON 粘贴到Visual Studio代码  
        :::image-end:::  
   :::column-end:::
:::row-end:::  

### 将属性值从网络请求复制到剪贴板  

若要将属性值从网络请求复制到剪贴板，请完成以下操作。  

1.  打开 **"标题"** 窗格。  
1.  打开以下标题部分之一。  
    *   请求有效负载 \ (JSON\)   
    *   表单数据  
    *   查询字符串参数  
    *   请求标头  
    *   响应标头  
1.  打开上下文菜单 \ (右键单击\) > **复制值**。  现在，您可以将该值粘贴到任何编辑器中以查看它。  
    
## 更改网络面板的布局  

可以展开或折叠网络面板 UI **的各个部分** ，以重点关注重要信息。  

### 隐藏"筛选器"窗格  

默认情况下，DevTools 显示" **筛选器"** 窗格。  
Choose **Filter** \ (![ Filter ][ImageFilterIcon] \) to hide it.  

:::image type="complex" source="../media/network-network-resources-hide-filters-button.msft.png" alt-text=""隐藏筛选器"按钮" lightbox="../media/network-network-resources-hide-filters-button.msft.png":::
   "隐藏筛选器"按钮  
:::image-end:::  

### 使用大型请求行  

在网络请求表中需要更多空格时，请使用大行。  使用大行时，某些列还会提供一些详细信息。  例如，Size 列 **的底部值为请求** 的未压缩大小。  

:::image type="complex" source="../media/network-network-requests-large-request-rows.msft.png" alt-text=""请求"窗格中大型请求行的示例" lightbox="../media/network-network-requests-large-request-rows.msft.png":::
   "请求"窗格中大型请求 **行** 的示例  
:::image-end:::  

若要启用大行，请打开"使用 **大型请求行"** 复选框。  

:::image type="complex" source="../media/network-network-requests-use-large-request-rows-on.msft.png" alt-text=""使用大型请求行"复选框" lightbox="../media/network-network-requests-use-large-request-rows-on.msft.png":::
   " **使用大型请求行"** 复选框  
:::image-end:::  

### 隐藏"概述"窗格  

默认情况下，DevTools 显示 **"概述"** 窗格。  若要隐藏它，请关闭"显示 **概述"** 复选框。  

:::image type="complex" source="../media/network-network-requests-show-overview-off.msft.png" alt-text=""显示概述"复选框" lightbox="../media/network-network-requests-show-overview-off.msft.png":::
   " **显示概述"** 复选框  
:::image-end:::  

## 联系 Microsoft Edge DevTools 团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageCaptureScreenshotsIcon]: ../media/capture-screenshots-icon.msft.png  
[ImageClearIcon]: ../media/clear-requests-icon.msft.png  
[ImageFilterIcon]: ../media/filter-icon.msft.png  
[ImageHideIcon]: ../media/hide-overview-icon.msft.png  
[ImageLargeResourceRowsIcon]: ../media/large-resource-rows-button-icon.msft.png  
[ImageRecordOnIcon]: ../media/record-on-icon.msft.png  

<!-- links -->  

[DevtoolsProgressiveWebApps]: ../progressive-web-apps/index.md "调试渐进式 Web 应用 |Microsoft Docs"  

<!--[NetworkConditions]: /microsoft-edge/devtools-guide-chromium/network/network-conditions "Optimize Performance Under Varying Network Conditions | Microsoft Docs"  -->  

[MDNHTTPDataURIs]: https://developer.mozilla.org/docs/Web/HTTP/Basics_of_HTTP/Data_URIs "数据 URL |MDN"  

[WikiProxyServer]: https://en.wikipedia.org/wiki/Proxy_server "代理服务器 - Wikipedia"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/network/reference)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
