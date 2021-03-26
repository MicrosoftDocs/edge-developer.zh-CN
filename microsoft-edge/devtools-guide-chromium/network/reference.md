---
description: Microsoft Edge 开发人员工具网络面板功能的综合参考。
title: 网络分析参考
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: 94a7031763da1e540b4dab802358e5f200e0db4a
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439701"
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

# <a name="network-analysis-reference"></a>网络分析参考  

在此 Microsoft Edge 开发工具网络分析功能的全面参考中，探索分析页面加载方式的新方法。  

## <a name="record-network-requests"></a>记录网络请求  

默认情况下，只要开发人员工具处于打开状态，它就会在“**网络**”工具中记录所有网络请求。  

:::image type="complex" source="../media/network-network-panel.msft.png" alt-text="“网络”面板" lightbox="../media/network-network-panel.msft.png":::
   “**网络**”工具  
:::image-end:::  

### <a name="stop-recording-network-requests"></a>停止记录网络请求  

若要停止记录请求，请完成以下步骤。  

1.  在“**网络**”工具上，选择“**停止记录网络日志**（“![停止记录网络日志](../media/record-on-icon.msft.png)”）。  它变为灰色，表示开发人员工具不再记录请求。  
1.  当“**网络**”工具成为焦点时，选择 `Control`+`E`（Windows、Linux）或 `Command`+`E`(macOS)。  

### <a name="clear-requests"></a>清除请求  

在“**网络**”工具上选择“**清除**”（“![清除](../media/clear-requests-icon.msft.png)”），从“请求”表中清除所有请求。  

:::image type="complex" source="../media/network-network-clear-button.msft.png" alt-text="“清除”按钮" lightbox="../media/network-network-clear-button.msft.png":::
   “**清除**”按钮  
:::image-end:::  

### <a name="save-requests-across-page-loads"></a>跨页面加载保存请求  

若要跨页面加载保存请求，请在“**网络**”工具上启用“**保留日志**”复选框。  开发人员工具将保存所有请求，直到禁用“**保留日志**”。  

:::image type="complex" source="../media/network-network-preserve-log.msft.png" alt-text="“保留日志”复选框" lightbox="../media/network-network-preserve-log.msft.png":::
   “**保留日志**”复选框  
:::image-end:::  

### <a name="capture-screenshots-during-page-load"></a>在页面加载期间捕获屏幕截图  

捕获屏幕截图以分析在等待页面加载时为用户显示的内容。  

若要启用屏幕截图，请选择“**网络设置**”，然后在“**网络**”工具上，启用“**捕获屏幕截图**”复选框。  

在“**网络**”工具成为焦点时刷新页面以捕获屏幕截图。  

截图后，可通过以下方式与之交互。  

*   将鼠标悬停在屏幕截图上以显示截图的位置。  “**概述**”格上将显示一条黄线。  
*   选择屏幕的缩略图以过滤截图后发生的任何请求。  
*   双击缩略图可将其放大。  

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

## <a name="change-loading-behavior"></a>更改加载行为  

### <a name="emulate-a-first-time-visitor-by-disabling-the-browser-cache"></a>通过禁用浏览器缓存来模拟首次访问者  

要模拟首次用户体验你的网站的方式，请启用“**禁用缓存**”复选框。  开发工具禁用浏览器缓存。  此功能更准确地模拟了首次用户的体验，因为在重复访问时，请求是从浏览器缓存中获得的。  

:::image type="complex" source="../media/network-network-disable-cache-checkbox.msft.png" alt-text="“禁用缓存”复选框" lightbox="../media/network-network-disable-cache-checkbox.msft.png":::
   “**禁用缓存**”复选框  
:::image-end:::  

#### <a name="disable-the-browser-cache-from-the-network-conditions-drawer"></a>从“网络条件”抽屉中禁用浏览器缓存  

如果要在其他开发工具面板中工作时禁用缓存，请使用“网络条件”抽屉。  

1.  打开“**网络条件**”抽屉。  
1.  启用\（或关闭\）“**禁用缓存**”复选框。  

<!--todo: add network condition section when available -->  

### <a name="manually-clear-the-browser-cache"></a>手动清除浏览器缓存  

要随时手动清除浏览器缓存，请打开“请求”表中任意位置的上下文菜单\（右键单击\），然后选择“**清除浏览器缓存**”。  

:::image type="complex" source="../media/network-network-clear-browser-cache.msft.png" alt-text="选择“清除浏览器缓存”" lightbox="../media/network-network-clear-browser-cache.msft.png":::
   选择“**清除浏览器缓存**”  
:::image-end:::  

### <a name="emulate-offline"></a>模拟脱机  

一种称为“[渐进式 Web 应用][DevtoolsProgressiveWebApps]”的新 web 应用程序，，可在**服务人员**的帮助下脱机运行。  在构建这种类型的应用程序时，快速模拟没有数据连接的设备可能会很有用。  

<!--[ServiceWorkers]: /web/fundamentals/getting-started/primers/service-workers  -->

选择“**联机**”下拉菜单，在“**预设**”下搜索，然后选择“**脱机**”以模拟脱机网络体验。  

:::image type="complex" source="../media/network-network-offline-dropdown.msft.png" alt-text="“脱机”下拉菜单" lightbox="../media/network-network-offline-dropdown.msft.png":::
   “**脱机**”下拉菜单  
:::image-end:::  

### <a name="emulate-slow-network-connections"></a>模拟慢速网络连接  

从“**在线**”下拉菜单中模拟慢速 3G、快速 3G 和其他连接速度。  

:::image type="complex" source="../media/network-network-throttling-menu.msft.png" alt-text="“限制”下拉菜单" lightbox="../media/network-network-throttling-menu.msft.png":::
   “**限制**”下拉菜单  
:::image-end:::  

可以选择不同的预设，如慢速 3G 或快速 3G。  若要添加自定义预设，请打开“限制”菜单，然后选择“**自定义**” > “**添加**”。  

开发人员工具会在“**网络**”工具旁边显示一个警告图标，提醒已启用限制。  

#### <a name="emulate-slow-network-connections-from-the-network-conditions-drawer"></a>从“网络条件”抽屉模拟慢速网络连接  

如果要在其他开发工具面板中工作时限制网络连接，请使用“网络条件”抽屉。  

1.  打开“**网络条件**”抽屉。  
1.  从“**限制**”菜单中选择连接速度。  

<!--todo: add network condition section when available -->  

### <a name="manually-clear-browser-cookies"></a>手动清除浏览器 Cookie  

若要随时手动清除浏览器 Cookie，请将鼠标悬停在“请求”表中的任意位置，打开上下文菜单\（右键单击\），然后选择“**清除浏览器 Cookie**”。  

:::image type="complex" source="../media/network-network-clear-browser-cookies.msft.png" alt-text="选择“清除浏览器 Cookie”" lightbox="../media/network-network-clear-browser-cookies.msft.png":::
   选择“**清除浏览器 Cookie**”  
:::image-end:::  

### <a name="override-the-user-agent"></a>替代用户代理  

要手动替代用户代理，请使用以下步骤。  

1.  打开“**网络条件**”抽屉。  
1.  关闭“**自动选择**”复选框。  
1.  从菜单中选择用户代理选项，或在文本框中输入自定义选项。  

<!--todo: add network condition section when available -->  

## <a name="filter-requests"></a>筛选请求  

### <a name="filter-requests-by-properties"></a>按属性筛选请求  

使用“**筛选器**”本框按属性（如请求的域或大小）筛选请求。  

如果未显示文本框，则“**筛选器**”窗格可能已隐藏。  
有关详细信息，请导航到[“隐藏筛选器”窗格](#hide-the-filters-pane)。  

:::image type="complex" source="../media/network-network-filters-textbox.msft.png" alt-text="“筛选器”文本框" lightbox="../media/network-network-filters-textbox.msft.png":::
   “**筛选器**”文本框  
:::image-end:::  

用空格分隔每个属性，可以同时使用多个属性。  例如，`mime-type:image/png larger-than:1K` 显示大于 1 KB 的所有 PNG。  多属性筛选器相当于 `AND` 操作。  `OR` 当前不支持操作。  

支持属性的完整列表。  

| 属性 | 详细信息 |  
|:--- | :--- |  
| `domain` | 仅显示指定域中的资源。  可以使用通配符\ (`*`\) 包含多个域。  例如，`*.com` 显示以 `.com` 结尾的所有域名中的资源。  开发工具在自动完成下拉菜单中填充找到的所有域。 |  
| `has-response-header` | 显示包含指定 HTTP 响应头的资源。  开发工具用找到的所有响应头填充“自动完成”下拉列表。 |  
| `is` | 用 `is:running` 查找 `WebSocket` 资源。 |  
| `larger-than` | 以字节为单位显示大于指定大小的资源。  将值设置为 `1000` 相当于将值设置为 `1k`。 |  
| `method` | 显示通过指定的 HTTP 方法类型检索的资源。  开发工具用找到的所有 HTTP 方法填充下拉列表。 |  
| `mime-type` | 显示指定 MIME 类型的资源。  开发工具用找到的所有 MIME 类型填充下拉列表。 |  
| `mixed-content` | 显示所有混合内容资源 \(`mixed-content:all`\) 或仅显示当前显示的内容资源 \(`mixed-content:displayed`\)。 |  
| `scheme` | 显示通过未受保护的 HTTP \(`scheme:http`\) 或受保护的 HTTPS \(`scheme:https`\) 检索的资源。 |  
| `set-cookie-domain` | 显示具有与指定值匹配的 `Domain` 属性的 `Set-Cookie` 标头的资源。  开发工具用找到的所有 Cookie 域填充“自动完成”。 |  
| `set-cookie-name` | 显示具有名称与指定值匹配的 `Set-Cookie` 标头的资源。  开发工具用找到的所有 Cookie 名称填充“自动完成”。 |  
| `set-cookie-value` | 显示具有值与指定值匹配的 `Set-Cookie` 标头的资源。  开发工具用找到的所有 Cookie 值填充“自动完成”。 |  
| `status-code` | 显示与特定 HTTP 状态代码匹配的资源。  开发工具用找到的所有状态代码填充“自动完成”下拉菜单。 |  

### <a name="filter-requests-by-type"></a>按类型筛选请求  

若要按请求类型筛选请求，请选择“**网络**”工具上的以下按钮之一。  

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
      **Manifest**  
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
      未列出的任何其他类型。  
   :::column-end:::
:::row-end:::  

如果按钮不显示，则“**筛选器**”窗格可能会隐藏。  
有关详细信息，请导航到[“隐藏筛选器”窗格](#hide-the-filters-pane)。  

要同时启用多个类型筛选器，请按住 `Control` \(Windows、Linux\) 或 `Command` \(macOS\)，然后选择。  

:::image type="complex" source="../media/network-network-type-filters.msft.png" alt-text="使用类型筛选器来显示 JS、CSS 和文档资源" lightbox="../media/network-network-type-filters.msft.png":::
   使用类型筛选器来显示 JS、CSS 和文档资源  
:::image-end:::  

### <a name="filter-requests-by-time"></a>按时间筛选请求  

在“**概述**”窗格中选择并向左或向右拖动，以仅显示在该时间段内处于活动状态的请求。  筛选器为非独占。  将显示在突出显示的时间内处于活动状态的任何请求。  

:::image type="complex" source="../media/network-network-overview-filter.msft.png" alt-text="筛选出处于非活动状态约 300 毫秒的所有请求" lightbox="../media/network-network-overview-filter.msft.png":::
   筛选出处于非活动状态约 300 毫秒的所有请求  
:::image-end:::  

### <a name="hide-data-urls"></a>隐藏数据 URL  

[数据 URL][MDNHTTPDataURIs] 是嵌入到其他文档中的小文件。  任何显示在“请求”表中以 `data:` 开头的请求都是数据 URL。  

若要隐藏请求，请关闭“**隐藏数据 URL**”复选框。  

:::image type="complex" source="../media/network-network-hide-data-urls.msft.png" alt-text="“隐藏数据 URL”复选框" lightbox="../media/network-network-hide-data-urls.msft.png":::
   “**隐藏数据 URL**”复选框  
:::image-end:::  

## <a name="sort-requests"></a>排序请求  

默认情况下，“请求”表中的请求按启动时间排序，但可使用其他条件对表进行排序。  

### <a name="sort-by-column"></a>按列排序  

选择“请求”中任何列的标题以按该列对请求进行排序。  

### <a name="sort-by-activity-phase"></a>按活动阶段排序  

要更改瀑布对请求的排序方式，请将鼠标悬停在“请求”表的标题上，打开上下文菜单 \（右键单击\），将鼠标悬停在“**瀑布**”上，然后选择以下选项之一。  

:::row:::
   :::column span="1":::
      **开始时间**  
   :::column-end:::
   :::column span="2":::
      启动的首个请求位于顶部。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **响应时间**  
   :::column-end:::
   :::column span="2":::
      开始下载的首个请求位于顶部。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **结束时间**  
   :::column-end:::
   :::column span="2":::
      完成的首个请求在顶部。  
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
      等待响应时间最短的请求位于顶部。  
   :::column-end:::
:::row-end:::  

这些描述假设每个选项按最短到最长进行排列。  选择“**瀑布**”列的标题以反转顺序。  

:::image type="complex" source="../media/network-network-waterfall-total-duration.msft.png" alt-text="按总持续时间排序“瀑布”" lightbox="../media/network-network-waterfall-total-duration.msft.png":::
   按总持续时间对瀑布进行排序\（每栏中较浅的部分是等待时间，较深的部分是下载字节的时间\）  
:::image-end:::  

## <a name="analyze-requests"></a>分析请求  

只要开发人员工具处于打开状态，它就会在“**网络**”工具中记录所有请求。  
使用“网络”面板分析请求。  

### <a name="display-a-log-of-requests"></a>显示请求日志  

使用“请求”表可以显示开发工具打开时发出的所有请求的日志。  若要显示有关每个项目的详细信息，请选择或将鼠标悬停在请求上。  

:::image type="complex" source="../media/network-network-requests-table.msft.png" alt-text="“请求”表" lightbox="../media/network-network-requests-table.msft.png":::
   “请求”表  
:::image-end:::  

默认情况下，“请求”表显示以下列。  

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
      请求资源的 MIME 类型。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **发起程序**  
   :::column-end:::
   :::column span="2":::
      以下对象或进程启动请求。  
      
      *   **分析程序** Microsoft Edge 的 HTML 分析程序。  
      *   **重定向**  HTTP 重定向。  
      *   **脚本**  JavaScript 函数。  
      *   **其他** 其他一些过程或操作，例如使用链接导航到页面或在地址栏中输入 URL。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **大小**  
   :::column-end:::
   :::column span="2":::
      服务器传递的响应头和响应正文的组合大小。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **时间**  
   :::column-end:::
   :::column span="2":::
      从请求开始到收到响应中最后一个字节的总持续时间。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [瀑布](#display-the-timing-relationship-of-requests)  
   :::column-end:::
   :::column span="2":::
      每个请求的活动的可视细分。  
   :::column-end:::
:::row-end:::  

#### <a name="add-or-remove-columns"></a>添加或删除列  

将鼠标悬停在“请求”表的标题上，打开上下文菜单 \（右键单击\），然后选择选项来隐藏或显示它。  当前显示的选项旁边都有复选标记。  

:::image type="complex" source="../media/network-network-requests-add-column.msft.png" alt-text="向“请求”表中添加列" lightbox="../media/network-network-requests-add-column.msft.png":::
   向“请求”表中添加列  
:::image-end:::  

#### <a name="add-custom-columns"></a>添加自定义列  

要向“请求”表中添加自定义列，请将鼠标悬停在“请求”表的标题上，打开上下文菜单\（右键单击\），然后选择“**响应标题**” > “**管理标题列**”。  

:::image type="complex" source="../media/network-network-requests-add-custom.msft.png" alt-text="向“请求”表添加自定义列" lightbox="../media/network-network-requests-add-custom.msft.png":::
   向“请求”表添加自定义列  
:::image-end:::  

### <a name="display-the-timing-relationship-of-requests"></a>显示请求的计时关系  

使用瀑布显示请求的计时关系。  
默认情况下，瀑布是按请求的开始时间进行组织的。  
因此，最左边的请求比最右边的请求更早开始。  

要查看对瀑布进行排序的不同方法，请导航到“[按活动阶段排序](#sort-by-activity-phase)”。  

:::image type="complex" source="../media/network-network-requests-waterfall.msft.png" alt-text="“请求”窗格的“瀑布”列。" lightbox="../media/network-network-requests-waterfall.msft.png":::
   “**请求**”窗格的“瀑布”列。  
:::image-end:::  

<!-- ### Analyze the frames of a WebSocket Connection  -->

<!--To review the frames of a WebSocket connection, use the following steps.  

1.  Choose the URL of the WebSocket connection, under the **Name** column of the Requests table.  
1.  Choose the **Frames** panel.  The table shows the last 100 frames.  

To refresh the table, re-choose the name of the WebSocket connection under the **Name** column of the Requests table.  -->

<!--
:::image type="complex" source="../media/network-frames.msft.png" alt-text="The Frames panel" lightbox="../media/network-frames.msft.png":::
   The **Frames** panel  
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

### <a name="display-a-preview-of-a-response-body"></a>显示响应正文的预览  

若要显示响应正文的预览，请使用以下步骤。  

1.  在“请求”表的“**名称**”列下，选择请求的 URL。  
1.  选择“**预览**”面板。  

“预览”选项卡在显示图像时最有用。  

:::image type="complex" source="../media/network-network-resources-preview.msft.png" alt-text="“预览”面板" lightbox="../media/network-network-resources-preview.msft.png":::
   “**预览**”面板  
:::image-end:::  

### <a name="display-a-response-body"></a>显示响应正文  

要显示请求的响应主体，请使用以下步骤。  

1.  在“请求”表的“**名称**”列下，选择请求的 URL。  
1.  选择“**响应**”面板。  

:::image type="complex" source="../media/network-network-resources-response.msft.png" alt-text="“响应”面板" lightbox="../media/network-network-resources-response.msft.png":::
   “**响应**”面板  
:::image-end:::  

### <a name="display-http-headers"></a>显示 HTTP 标头  

要显示有关请求的 HTTP 标头数据，请使用以下步骤。  

1.  在“请求”表的“**名称**”列下，选择请求的 URL。  
1.  选择“**标头**”面板。  

:::image type="complex" source="../media/network-resources-headers.msft.png" alt-text="“标头”面板" lightbox="../media/network-resources-headers.msft.png":::
   “**标头**”面板  
:::image-end:::  

#### <a name="display-http-header-source"></a>显示 HTTP 标头源  

默认情况下，“**标头**”面板按字母顺序显示标头名称。  若要按接收的顺序显示 HTTP 标头名称，请使用以下步骤。  

1.  打开感兴趣的请求的“**标头**”面板。  有关详细信息，请导航到“[显示 HTTP 标头](#display-http-headers)”。  
1.  单击“**请求标题**”或“**响应标题**”部分旁边的**查看源**。  

### <a name="display-query-string-parameters"></a>显示查询字符串参数  

若要以可读格式显示 URL 的查询字符串参数，请使用以下步骤。  

1.  打开感兴趣的请求的“**标头**”面板。  有关详细信息，请导航到“[显示 HTTP 标头](#display-http-headers)”。  
1.  导航到“**查询字符串参数**”部分。  

:::image type="complex" source="../media/network-network-resources-headers-query-string-parameters.msft.png" alt-text="“查询字符串参数”部分" lightbox="../media/network-network-resources-headers-query-string-parameters.msft.png":::
   “**查询字符串参数**”部分  
:::image-end:::  

#### <a name="display-query-string-parameters-source"></a>显示查询字符串参数源  

若要显示请求的查询字符串参数源，请使用以下步骤。  

1.  导航到“查询字符串参数”部分。  有关详细信息，请导航到“[显示查询字符串参数](#display-query-string-parameters)”。  
1.  选择“**查看源**”。  

#### <a name="display-url-encoded-query-string-parameters"></a>显示 URL 编码的查询字符串参数  

若要以可读格式显示查询字符串参数，但保留编码，请使用以下步骤。  

1.  导航到“查询字符串参数”部分。  有关详细信息，请导航到“[显示查询字符串参数](#display-query-string-parameters)”。  
1.  选择**查看 URL 编码**。  

### <a name="display-cookies"></a>显示 Cookie  

若要显示请求的 HTTP 标头中发送的 Cookie，请使用以下步骤。  

1.  在“请求”表的“**名称**”列下，选择请求的 URL。  
1.  选择“**Cookie**”面板。  

<!--For more information about each of the columns, navigate to [Fields][ManageDataCookiesFields].  -->  

<!--[ManageDataCookiesFields]: manage-data/cookies#fields  -->  
<!--TODO: add link when section is available -->  

:::image type="complex" source="../media/network-network-resources-cookies.msft.png" alt-text="“Cookie”面板" lightbox="../media/network-network-resources-cookies.msft.png":::
   “Cookie”面板  
:::image-end:::  

### <a name="display-the-timing-breakdown-of-a-request"></a>显示请求的计时细分  

若要显示请求的计时细分，请使用以下步骤。  

1.  在“请求”表的“**名称**”列下，选择请求的 URL。  
1.  选择“**计时**”面板。  

若要更快地访问数据，请导航到“[预览计时细分](#preview-a-timing-breakdown)”。  

有关“**计时**”面板中可能显示的各阶段详细信息，请导航到“[计时细分阶段说明](#timing-breakdown-phases-explained)”。  

:::image type="complex" source="../media/network-network-resources-timing.msft.png" alt-text="“计时”面板" lightbox="../media/network-network-resources-timing.msft.png":::
   “**计时**”面板  
:::image-end:::  

有关各阶段的更多信息。  

有关访问视图的详细信息，请导航至“[显示计时明细](#display-the-timing-breakdown-of-a-request)”。  

#### <a name="preview-a-timing-breakdown"></a>预览计时细分  

要显示请求的计时细分预览，请在“请求”表的“**瀑布**”列中，将鼠标悬停在请求的条目上。  

有关如何在不悬停的情况下访问数据的详细信息，请导航至“[显示请求的计时细分](#display-the-timing-breakdown-of-a-request)”。  

:::image type="complex" source="../media/network-network-resources-waterfall-hover.msft.png" alt-text="> 预览请求的计时细分" lightbox="../media/network-network-resources-waterfall-hover.msft.png":::
   预览请求的计时细分  
:::image-end:::  

#### <a name="timing-breakdown-phases-explained"></a>计时细分阶段说明  

有关“**计时**”面板中可能显示的各阶段的详细信息。  

:::row:::
   :::column span="1":::
      **排队**  
   :::column-end:::
   :::column span="2":::
      浏览器在以下情况下将请求排队。  
      
      *   存在更高优先级的请求。  
      *   已为同一来源打开了六个（上限）TCP 连接。  仅适用于 HTTP/1.0 和 HTTP/1.1。  
      *   浏览器正在磁盘缓存中短暂分配空间。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **停止**  
   :::column-end:::
   :::column span="2":::
      该请求可能由于“**排队**”中描述的任何原因而停止。  
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
      浏览器正在建立包括 TCP 握手/重试的连接和协商安全套接字层。
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **代理协商**  
   :::column-end:::
   :::column span="2":::
      浏览器正在与[代理服务器][WikiProxyServer]协商请求。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **已发送请求**  
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
      **向 ServiceWorker 请求**  
   :::column-end:::
   :::column span="2":::
      请求正在发送到服务工作进程。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **等待中 (TTFB)**  
   :::column-end:::
   :::column span="2":::
      浏览器正在等待响应的首个字节。  TTFB 代表到首个字节的时间。  此计时包括一次往返延迟和服务器准备响应所用的时间。  
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
      浏览器正在通过 HTTP/2 服务器推送接收此响应的数据。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **读取推送**  
   :::column-end:::
   :::column span="2":::
      浏览器正在读取以前接收的本地数据。  
   :::column-end:::
:::row-end:::  

### <a name="display-initiators-and-dependencies"></a>显示发起程序和依赖项  

若要显示请求的发起程序和依赖项，请按住 `Shift` 并将鼠标悬停在“请求”表中的请求上。  开发工具颜色：发起程序显示为绿色，依赖项显示为红色。  

:::image type="complex" source="../media/network-network-resources-initiators-dependencies.msft.png" alt-text="显示请求的发起程序和依赖项" lightbox="../media/network-network-resources-initiators-dependencies.msft.png":::
   显示请求的发起程序和依赖项  
:::image-end:::  

当“请求”表按时间顺序排列时，如果将鼠标悬停在某一行上，则它前面的行将显示绿色请求。  绿色请求是依赖项的发起程序。  如果在此之上还有另一个绿色请求，则该更高的请求是发起程序的发起程序。  等等。  

### <a name="display-load-events"></a>显示加载事件  

开发人员工具在“**网络**”工具的多个位置显示 `DOMContentLoaded` 和 `load` 事件的计时。  `DOMContentLoaded` 事件颜色为蓝色，`load` 事件颜色为红色。  

:::image type="complex" source="../media/network-network-requests-load-events.msft.png" alt-text="“网络”面板上 DOMContentLoaded 和加载事件的位置" lightbox="../media/network-network-requests-load-events.msft.png":::
   “**网络**”工具上 `DOMContentLoaded` 和 `load` 事件的位置  
:::image-end:::  

### <a name="display-the-total-number-of-requests"></a>显示请求总数  

请求总数列在“**网络**”工具底部的“**摘要**”窗格中。  

> [!CAUTION]
> 此数字仅跟踪自打开开发人员工具以来记录的请求。  如果在打开开发工具之前发生了其他请求，则不计算这些请求。  

:::image type="complex" source="../media/network-network-total-requests.msft.png" alt-text="自打开开发工具以来的请求总数" lightbox="../media/network-network-total-requests.msft.png":::
   自打开开发工具以来的请求总数  
:::image-end:::  

### <a name="display-the-total-download-size"></a>显示总下载大小  

请求的总下载大小列在“**网络**”工具底部的“**摘要**”窗格中。  

> [!CAUTION]
> 此数字仅跟踪自打开开发人员工具以来记录的请求。  如果在打开开发工具之前发生了其他请求，则不计算以前的请求。  

:::image type="complex" source="../media/network-network-total-download-size.msft.png" alt-text="请求的总下载大小" lightbox="../media/network-network-total-download-size.msft.png":::
   请求的总下载大小  
:::image-end:::  

若要在浏览器解压缩每个项目后验证资源的大小，请导航到“[显示资源的未压缩大小](#display-the-uncompressed-size-of-a-resource)”。  

### <a name="display-the-stack-trace-that-caused-a-request"></a>显示导致请求的堆栈跟踪  

JavaScript 语句请求资源后，将鼠标悬停在“**发起程序**”列上以显示请求之前的堆栈跟踪。  

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

### <a name="display-the-uncompressed-size-of-a-resource"></a>显示资源的未压缩大小  

启用“**使用大请求行**”复选框，然后查看“**大小**”列的底部值。  

:::image type="complex" source="../media/network-network-requests-uncompressed-compare.msft.png" alt-text="未压缩资源的示例" lightbox="../media/network-network-requests-uncompressed-compare.msft.png":::
   未压缩资源的示例\（通过网络发送的 `jquery-3.3.1.min.js` 文件的压缩大小为 `29.9 KB`，而未压缩大小为`84.9 KB`\）  
:::image-end:::  

## <a name="export-requests-data"></a>导出请求数据  

### <a name="save-all-network-requests-to-a-har-file"></a>将所有网络请求保存到 HAR 文件  

若要将所有网络请求保存到 HAR 文件，请完成以下步骤。  

1.  将鼠标悬停在“请求”表中的任何请求上，然后打开上下文菜单\（右键单击\）。  
1.  选择“**另存为具有内容的 HAR**”。  开发工具将自打开开发工具以来发生的所有请求保存到 HAR 文件中。  无法筛选请求。  也无法保存一个请求。  

保存 HAR 文件后，可以将其导入开发工具进行分析。  只需将 HAR 文件拖放到“请求”表中。  
<!--For more information, navigate to also [HAR Analyzer][HARAnalyzer].  -->  

<!--[HARAnalyzer]: https://toolbox.alphabetapps.com/apps/har_analyzer  -->  
<!--Todo: add section link when content is available  -->  

:::image type="complex" source="../media/network-network-requests-save-har-content.msft.png" alt-text="选择“另存为具有内容的 HAR”" lightbox="../media/network-network-requests-save-har-content.msft.png":::
   选择“**另存为具有内容的 HAR**”  
:::image-end:::  

### <a name="copy-one-or-more-requests-to-the-clipboard"></a>将一个或多个请求复制到剪贴板  

在“请求”表的“**名称**”列下，将鼠标悬停在请求上，打开上下文菜单 \（右键单击\），将鼠标悬停在“**复制**”上，然后选择以下选项之一。  

| 名称 | 详细信息 |  
|:--- |:--- |  
| **复制链接地址** | 将请求的 URL 复制到剪贴板。 |  
| **复制响应** | 将响应正文复制到剪贴板。 |  
| **复制为 Fetch** | &nbsp; |  
| **复制为 cURL** | 将请求复制为 cURL 命令。 |  
| **全部复制为 Fetch** | &nbsp; |  
| **全部复制为 cURL** | 将所有请求复制为一系列 cURL 命令。 |  
| **全部复制为 HAR** | 将所有请求复制为 HAR 数据。 |  

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

:::image type="complex" source="../media/network-network-requests-copy-response.msft.png" alt-text="选择“复制响应”" lightbox="../media/network-network-requests-copy-response.msft.png":::
   选择“**复制响应**”  
:::image-end:::  

### <a name="copy-formatted-response-json-to-the-clipboard"></a>将格式化响应 JSON 复制到剪贴板  

选择网络请求并导航到“**标头**”窗格。  要复制响应的 JSON 值，请导航到 **“请求”有效负载**，将鼠标悬停在 JSON 响应内容上，打开上下文菜单\（右键单击\），然后选择“**复制值**”。  

:::row:::
   :::column span="":::
        :::image type="complex" source="../media/network-header-copy-property-value.msft.png" alt-text="复制上下文菜单中的值" lightbox="../media/network-header-copy-property-value.msft.png":::
          上下文菜单中的“**复制值**”  
        :::image-end:::  
   :::column-end:::
   :::column span="":::
        :::image type="complex" source="../media/network-header-paste-property-value.msft.png" alt-text="具有格式化响应 JSON 的 Microsoft Visual Studio Code" lightbox="../media/network-header-paste-property-value.msft.png":::
          在 Microsoft Visual Studio Code 中粘贴格式化响应 JSON  
        :::image-end:::  
   :::column-end:::
:::row-end:::  

### <a name="copy-property-values-from-network-requests-to-your-clipboard"></a>将属性值从网络请求复制到剪贴板  

要将属性值从网络请求复制到剪贴板，请完成以下操作。  

1.  打开“**标头**”窗格。  
1.  打开以下其中一个标头部分。  
    *   请求有效负载 \(JSON\)  
    *   窗体数据  
    *   查询字符串参数  
    *   请求标头  
    *   响应标头  
1.  打开上下文菜单（右键单击）>“**复制值**”。  现在可以将该值粘贴到任何编辑器中以查看它。  
    
## <a name="change-the-layout-of-the-network-panel"></a>更改“网络”面板的布局  

可以展开或折叠“**网络**”工具用户界面的各部分，以集中重要信息。  

### <a name="hide-the-filters-pane"></a>隐藏“筛选器”窗格  

默认情况下，开发工具显示“**筛选器**”窗格。  
选择**筛选器** \(![筛选器](../media/filter-icon.msft.png)\)来隐藏它。  

:::image type="complex" source="../media/network-network-resources-hide-filters-button.msft.png" alt-text="“隐藏筛选器”按钮" lightbox="../media/network-network-resources-hide-filters-button.msft.png":::
   “隐藏筛选器”按钮  
:::image-end:::  

### <a name="use-large-request-rows"></a>使用大请求行  

如需网络请求表中有更多空白，请使用大行。  在使用大行时，有些列还提供了更多的信息。  例如，“**大小**”列的底部值是请求的未压缩大小。  

:::image type="complex" source="../media/network-network-requests-large-request-rows.msft.png" alt-text="“请求”窗格中大请求行的示例" lightbox="../media/network-network-requests-large-request-rows.msft.png":::
   “**请求**”窗格中大请求行的示例  
:::image-end:::  

要启用大行，请启用“**使用大请求行**”复选框。  

:::image type="complex" source="../media/network-network-requests-use-large-request-rows-on.msft.png" alt-text="“使用大请求行”复选框" lightbox="../media/network-network-requests-use-large-request-rows-on.msft.png":::
   “**使用大请求行**”复选框  
:::image-end:::  

### <a name="hide-the-overview-pane"></a>隐藏概述窗格  

默认情况下，开发工具显示“**概述**”窗格。  若要隐藏它，请关闭“**显示概述**”复选框。  

:::image type="complex" source="../media/network-network-requests-show-overview-off.msft.png" alt-text="“显示概述”复选框" lightbox="../media/network-network-requests-show-overview-off.msft.png":::
   “**显示概述**”复选框  
:::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge 开发工具团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsProgressiveWebApps]: ../progressive-web-apps/index.md "调试渐进式 Web 应用 | Microsoft Docs"  

<!--[NetworkConditions]: /microsoft-edge/devtools-guide-chromium/network/network-conditions "Optimize Performance Under Varying Network Conditions | Microsoft Docs"  -->  

[MDNHTTPDataURIs]: https://developer.mozilla.org/docs/Web/HTTP/Basics_of_HTTP/Data_URIs "数据 URL | MDN"  

[WikiProxyServer]: https://en.wikipedia.org/wiki/Proxy_server "代理服务器 - 维基百科"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/network/reference)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
