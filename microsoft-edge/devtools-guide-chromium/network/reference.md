---
title: 网络分析参考
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: ec8969fbf7b54512f00120ac4a253b952c55768f
ms.sourcegitcommit: 0048eb692d49eab4755c0c3ef6866e6a9122d579
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/01/2020
ms.locfileid: "10844017"
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

了解在 Microsoft Edge DevTools 网络分析功能的这一全面参考中，分析页面加载方式的新方法。  

<!--
> [!NOTE]
> This reference is based on Microsoft Edge 58.  If you use another version of Microsoft Edge, the UI, and features of DevTools may be different.  Check `edge://help` to see what version of Microsoft Edge you are running.  
-->

## 记录网络请求  

默认情况下，DevTools 将在网络面板中记录所有网络请求，只要 DevTools 已打开。  

:::image type="complex" source="../media/network-network-panel.msft.png" alt-text="网络面板" lightbox="../media/network-network-panel.msft.png":::
   图1：**网络**面板  
:::image-end:::  

### 停止记录网络请求  

若要停止录制请求，请完成以下步骤。  

1.  选择 "**停止录制网络日志**" ![ 停止 ][ImageRecordOnIcon] 在**网络**面板上记录网络日志。  它将变为灰色，指示 DevTools 不再录制请求。  
1.  `Control` + `E` 在 "网络" 面板处于聚焦状态时，按 \ （Windows \）或 `Command` + `E` \ （macOS \）。 **Network**  

### 清除请求  

**Clear** ![ ][ImageClearIcon] 在 "网络" 面板上选择 "清除清除"，清除 "请求" 表中的所有请求。  

:::image type="complex" source="../media/network-network-clear-button.msft.png" alt-text="清除 按钮" lightbox="../media/network-network-clear-button.msft.png":::
   图2： "**清除**" 按钮  
:::image-end:::  

### 跨页面加载保存请求  

若要在每个页面加载期间保存请求，请选中 "网络" 面板上的 "**保留日志**" 复选框。  DevTools 将保存所有请求，直到你禁用**保留日志**。  

:::image type="complex" source="../media/network-network-preserve-log.msft.png" alt-text="保留日志 复选框" lightbox="../media/network-network-preserve-log.msft.png":::
   图3： "**保留日志**" 复选框  
:::image-end:::  

### 在页面加载期间捕获屏幕截图  

捕获屏幕截图，分析用户在等待页面加载时看到的内容。  

若要启用屏幕截图，请选择 "**网络设置**"，然后选择**网络**面板上的 "**捕获屏幕截图**" 复选框  

在 "**网络**" 面板处于焦点时刷新页面以捕获屏幕截图。  

捕获屏幕截图后，可通过以下方式与之交互。  

*   将鼠标悬停在屏幕截图上以查看捕获该屏幕截图的位置。  "**概述**" 窗格上将显示一个黄色线条。  
*   选择屏幕的缩略图，以筛选出捕获屏幕截图后发生的任何请求。  
*   双击缩略图以放大缩略图。  

:::image type="complex" source="../media/network-network-screenshot-hover.msft.png" alt-text="将鼠标悬停在屏幕截图上" lightbox="../media/network-network-screenshot-hover.msft.png":::
   图4：将鼠标悬停在屏幕截图上  
:::image-end:::  

<!--  ### Replay XHR request  -->

<!--  To replay an XHR request, hover on the request in the Requests table, open the contextual menu \(right-click\), and select **Replay XHR**.  -->

<!--  
:::image type="complex" source="../media/network-replay-xhr.msft.png" alt-text="Selecting Replay XHR" lightbox="../media/network-replay-xhr.msft.png":::
   Old Figure 5:  Selecting Replay XHR  
:::image-end:::  
-->  

## 更改加载行为  

### 通过禁用浏览器缓存来模拟首次访问者  

若要模拟首次用户体验你的网站的情况，请选中 "**禁用缓存**" 复选框。  DevTools 禁用浏览器缓存。  这将更准确地模拟第一次用户的体验，因为在重复访问时从浏览器缓存提供请求。  

:::image type="complex" source="../media/network-network-disable-cache-checkbox.msft.png" alt-text="禁用缓存 复选框" lightbox="../media/network-network-disable-cache-checkbox.msft.png":::
   图5： "**禁用缓存**" 复选框  
:::image-end:::  

#### 从网络条件抽屉中禁用浏览器缓存  

如果想要在其他 DevTools 面板中工作时禁用缓存，请使用网络条件抽屉。  

1.  打开**网络条件**抽屉。  
1.  选中或取消选中 "**禁用缓存**" 复选框。  

<!--todo: add network condition section when available -->  

### 手动清除浏览器缓存  

若要随时手动清除浏览器缓存，请在 "请求" 表中的任意位置打开上下文菜单 \ （右键单击 \），然后选择 "**清除浏览器缓存**"。  

:::image type="complex" source="../media/network-network-clear-browser-cache.msft.png" alt-text="选择 清除浏览器缓存" lightbox="../media/network-network-clear-browser-cache.msft.png":::
   图6：选择 "**清除浏览器缓存**"  
:::image-end:::  

### 模拟脱机  

新的 web 应用类（名为 "[渐进式 Web 应用][DevtoolsProgressiveWebApps]"）使用**服务工作人员**帮助脱机工作。  你可能会发现，在你构建此类型的应用时，快速模拟没有数据连接的设备非常有用。  

<!--[ServiceWorkers]: /web/fundamentals/getting-started/primers/service-workers  -->

选择 "**联机**" 下拉菜单，在 "**预置**" 下搜索，然后选择 "**脱机**" 以模拟完全脱机的网络体验。  

:::image type="complex" source="../media/network-network-offline-dropdown.msft.png" alt-text="脱机 下拉菜单" lightbox="../media/network-network-offline-dropdown.msft.png":::
   图7：**脱机**下拉菜单  
:::image-end:::  

### 模拟慢速网络连接  

从 "**联机**" 下拉菜单中模拟慢速3G、快速3g 和其他连接速度。  

:::image type="complex" source="../media/network-network-throttling-menu.msft.png" alt-text="限制下拉菜单" lightbox="../media/network-network-throttling-menu.msft.png":::
   图8：**限制**下拉菜单  
:::image-end:::  

您可以从各种预设（如低速3G 或快速3G）中进行选择。  您也可以通过打开 "限制" 菜单并选择 "**自定义**添加" 来添加自己的自定义预设  >  **Add**。  

DevTools 将在 "**网络**" 选项卡旁显示一个警告图标，提醒你已启用限制。  

#### 从网络条件抽屉中模拟慢速网络连接  

如果您希望在其他 DevTools 面板中工作时限制网络连接，请使用网络条件抽屉。  

1.  打开**网络条件**抽屉。  
1.  从 "**限制**" 菜单中选择所需的连接速度。  

<!--todo: add network condition section when available -->  

### 手动清除浏览器 cookie  

若要随时手动清除浏览器 cookie，请在 "请求" 表中的任意位置打开上下文菜单 \ （右键单击 \），然后选择 "**清除浏览器 cookie**"。  

:::image type="complex" source="../media/network-network-clear-browser-cookies.msft.png" alt-text="选择 清除浏览器 Cookie" lightbox="../media/network-network-clear-browser-cookies.msft.png":::
   图9：选择 "**清除浏览器 cookie** "  
:::image-end:::  

### 替代用户代理  

要手动替代用户代理，请执行以下操作：  

1.  打开**网络条件**抽屉。  
1.  取消选中 "**自动**"。  
1.  从菜单中选择用户代理选项，或在文本框中输入自定义选项。  

<!--todo: add network condition section when available -->  

## 筛选请求  

### 按属性筛选请求  

使用 "**筛选**" 文本框筛选按属性（如请求的域或大小）的请求。  

如果看不到文本框，则 "筛选器" 窗格可能已隐藏。  
请参阅[隐藏筛选器窗格](#hide-the-filters-pane)。  

:::image type="complex" source="../media/network-network-filters-textbox.msft.png" alt-text="筛选器 文本框" lightbox="../media/network-network-filters-textbox.msft.png":::
   图10： "**筛选**" 文本框  
:::image-end:::  

你可以通过使用空格分隔每个属性来同时使用多个属性。  例如， `mime-type:image/png larger-than:1K` 显示大于 1 kb 的所有 PNGs。  这些多属性筛选器等效于 `AND` 操作。  `OR` 当前不支持操作。  

受支持的属性的完整列表。  

| 属性 | 详细信息 |  
|:--- | :--- |  
| `domain` | 仅显示指定域中的资源。  您可以使用通配符 \ （ `*` \）包含多个域。  例如， `*.com` 显示所有以结尾的域名的资源 `.com` 。  DevTools 将填充 "自动完成" 下拉菜单，其中包含它遇到的所有域。 |  
| `has-response-header` | 显示包含指定的 HTTP 响应标头的资源。  DevTools 将填充 "自动完成" 下拉列表，其中包含已遇到的所有响应标题。 |  
| `is` | 用于 `is:running` 查找 `WebSocket` 资源。 |  
| `larger-than` | 显示大于指定大小的资源（以字节为单位）。  设置值 `1000` 等效于将值设置为 `1k` 。 |  
| `method` | 显示通过指定的 HTTP 方法类型检索的资源。  DevTools 将用它遇到的所有 HTTP 方法填充下拉列表。 |  
| `mime-type` | 显示指定 MIME 类型的资源。  DevTools 将用遇到的所有 MIME 类型填充下拉列表。 |  
| `mixed-content` | 显示所有混合内容资源 \ （ `mixed-content:all` \）或仅显示当前显示的所有混合内容资源 \ （ `mixed-content:displayed` \）。 |  
| `scheme` | 显示通过未受保护的 HTTP \ （ `scheme:http` \）或受保护的 HTTPS \ （ `scheme:https` \）检索的资源。 |  
| `set-cookie-domain` | 显示具有 `Set-Cookie` 与指定值匹配的属性的标题的资源 `Domain` 。  DevTools 将填充所遇到的所有 cookie 域的自动完成功能。 |  
| `set-cookie-name` | 显示具有 `Set-Cookie` 与指定值匹配的名称的标题的资源。  DevTools 将用遇到的所有 cookie 名称填充记忆式键入。 |  
| `set-cookie-value` | 显示具有与 `Set-Cookie` 指定值匹配的值的标题的资源。  DevTools 将用遇到的所有 cookie 值填充记忆式键入。 |  
| `status-code` | 仅显示 HTTP 状态代码与指定代码匹配的资源。  DevTools 将填充 "自动完成" 下拉菜单，其中包含遇到的所有状态代码。 |  

### 按类型筛选请求  

若要按请求类型筛选请求，请选择 "网络" 面板上的**XHR**、 **JS**、 **CSS**、 **Img**、**媒体**、**字体**、**文档**、 **WS** \ （WebSocket \）、**清单**或**其他**\ （此处未列出的任何其他类型 \）按钮。  

如果看不到这些按钮，则 "筛选器" 窗格可能处于隐藏状态。  
请参阅[隐藏筛选器窗格](#hide-the-filters-pane)。  

若要同时启用多个类型筛选器，请按住 `Control` \ （Windows \）或 `Command` \ （macOS \），然后选择。  

:::image type="complex" source="../media/network-network-type-filters.msft.png" alt-text="使用类型筛选器显示 JS、CSS 和文档资源" lightbox="../media/network-network-type-filters.msft.png":::
   图11：使用类型筛选器显示 JS、CSS 和文档资源  
:::image-end:::  

### 按时间筛选请求  

在 "概述" 窗格中选择并向左或向右拖动，以仅显示在该时间范围内处于活动状态的请求。  筛选器是包含的。  显示在突出显示的时间内处于活动状态的任何请求。  

:::image type="complex" source="../media/network-network-overview-filter.msft.png" alt-text="筛选出在300ms 周围处于非活动状态的任何请求" lightbox="../media/network-network-overview-filter.msft.png":::
   图12：筛选出在300ms 周围处于非活动状态的任何请求  
:::image-end:::  

### 隐藏数据 Url  

[数据 url][MDNHTTPDataURIs]是嵌入到其他文档中的小文件。  在 "请求" 表中看到的以数据 URL 开头的任何请求 `data:` 。  

选中 "**隐藏数据 url** " 复选框以隐藏请求。  

:::image type="complex" source="../media/network-network-hide-data-urls.msft.png" alt-text="隐藏数据 Url 复选框" lightbox="../media/network-network-hide-data-urls.msft.png":::
   图13： "**隐藏数据 Url** " 复选框  
:::image-end:::  

## 排序请求  

默认情况下，请求表中的请求按初始时间排序，但你可以使用其他条件对表进行排序。  

### 按列排序  

选择请求中的任何列的标题，对该列的请求进行排序。  

### 按活动阶段排序  

若要更改瀑布对请求的排序方式，请将鼠标悬停在 "请求" 表的标题上，打开上下文菜单 \ （右键单击 \），将鼠标悬停在**瀑布**上，然后选择下列选项之一。  

*   **开始时间**。  启动的第一个请求位于顶部。  
*   **响应时间**。  开始下载的第一个请求位于顶部。  
*   **结束时间**。  第一个已完成的请求位于顶部。  
*   **总工期**。  具有最短连接设置和请求/响应的请求位于顶部。  
*   **延迟**。  等待响应时间最短的请求位于最前面。  

这些说明假定每个各自的选项均按最短到最长的排序。  选择**瀑布**栏的标题将反转顺序。  

:::image type="complex" source="../media/network-network-waterfall-total-duration.msft.png" alt-text="按总工期对瀑布图进行排序" lightbox="../media/network-network-waterfall-total-duration.msft.png":::
   图14：按总工期对瀑布图进行排序 \ （每个条形图的较亮部分是等待的时间，较暗的部分是下载字节所花费的时间）  
:::image-end:::  

## 分析请求  

只要 DevTools 打开，它就会在 "网络" 面板中记录所有请求。  
使用 "网络" 面板分析请求。  

### 查看请求日志  

使用 "请求" 表查看在 DevTools 打开时发出的所有请求的日志。  选择或悬停的请求将显示有关每个项目的详细信息。  

:::image type="complex" source="../media/network-network-requests-table.msft.png" alt-text="请求表" lightbox="../media/network-network-requests-table.msft.png":::
   图15：请求表  
:::image-end:::  

"请求" 表默认情况下显示以下列。  

*   **名称**。  资源的文件名或标识符。  
*   **状态**。  HTTP 状态代码。  
*   **类型**。  所请求的资源的 MIME 类型。  
*   **启动器**。  以下对象或进程启动请求：  
    *   **分析器**。  Microsoft Edge 的 HTML 分析程序。  
    *   **重定向**。  HTTP 重定向。  
    *   **脚本**。  JavaScript 函数。  
    *   **其他**。  某些其他进程或操作，例如通过链接导航到页面或在地址栏中输入 URL。  
*   **大小**。  由服务器发送的响应标题和响应正文的合并大小。  
*   **时间**。  从请求开始到响应中最后一个字节的接收的总持续时间。  
*   [**瀑布**](#view-the-timing-of-requests-in-relation-to-one-another)图。  每个请求的活动的可视化细目。  

#### 添加或删除列  

将鼠标悬停在 "请求" 表的标题上，打开上下文菜单 \ （右键单击 \），然后选择一个选项以隐藏或显示它。  当前显示的选项在每个项目旁边都有复选标记。  

:::image type="complex" source="../media/network-network-requests-add-column.msft.png" alt-text="将列添加到 请求 表" lightbox="../media/network-network-requests-add-column.msft.png":::
   图16：向请求表添加列  
:::image-end:::  

#### 添加自定义列  

若要向 "请求" 表添加自定义列，请将鼠标悬停在 "请求" 表的标题上，打开上下文菜单 \ （右键单击 \），然后选择 "**响应标题**" "  >  **管理标题列**"。  

:::image type="complex" source="../media/network-network-requests-add-custom.msft.png" alt-text="向请求表添加自定义列" lightbox="../media/network-network-requests-add-custom.msft.png":::
   图17：向请求表添加自定义列  
:::image-end:::  

### 查看请求之间的相对计时  

使用瀑布图查看请求相对于另一个时间的计时。  
默认情况下，瀑布图按请求的开始时间进行组织。  
因此，比右侧更远的时间开始向左的请求更远。  

请参阅 "[按活动排序" 阶段](#sort-by-activity-phase)以查看可对瀑布图进行排序的不同方式。  

:::image type="complex" source="../media/network-network-requests-waterfall.msft.png" alt-text="请求 窗格的瀑布栏" lightbox="../media/network-network-requests-waterfall.msft.png":::
   图18： "**请求**" 窗格的 "瀑布图" 列  
:::image-end:::  

<!-- ### Analyze the frames of a WebSocket Connection  -->

<!--To view the frames of a WebSocket connection:  

1.  Select the URL of the WebSocket connection, under the **Name** column of the Requests table.  
1.  Select the **Frames** tab.  The table shows the last 100 frames.  

To refresh the table, re-select the name of the WebSocket connection under the **Name** column of the Requests table.  -->

<!--
:::image type="complex" source="../media/network-frames.msft.png" alt-text="The Frames tab" lightbox="../media/network-frames.msft.png":::
   Old Figure 20:  The **Frames** tab  
:::image-end:::  
-->

<!--The table contains three columns:  

*   **Data**.  The message payload.  If the message is plain text, it is displayed here.  For binary opcodes, this column displays the name and code of the opcode.  The following opcodes are supported: Continuation Frame, Binary Frame, Connection Close Frame, Ping Frame, and Pong Frame.  
*   **Length**.  The length of the message payload, in bytes.  
*   **Time**.  The time when the message was received or sent.  -->

<!--Messages are color-coded according to their type:  

*   Outgoing text messages are light-green.  
*   Incoming text messages are white.  
*   WebSocket opcodes are light-yellow.  
*   Errors are light-red.  -->

### 查看答复正文的预览  

若要查看响应正文的预览，请执行以下操作：  

1.  在 "请求" 表的 "**名称**" 列下，选择请求的 URL。  
1.  选择 "**预览**" 选项卡。  

此选项卡最适用于查看图像。  

:::image type="complex" source="../media/network-network-resources-preview.msft.png" alt-text="预览 选项卡" lightbox="../media/network-network-resources-preview.msft.png":::
   图19： "**预览**" 选项卡  
:::image-end:::  

### 查看答复正文  

要查看请求的响应正文，请执行以下操作：  

1.  在 "请求" 表的 "**名称**" 列下，选择请求的 URL。  
1.  选择 "**响应**" 选项卡。  

:::image type="complex" source="../media/network-network-resources-response.msft.png" alt-text="响应 选项卡" lightbox="../media/network-network-resources-response.msft.png":::
   图20： "**响应**" 选项卡  
:::image-end:::  

### 查看 HTTP 标头  

查看有关请求的 HTTP 头数据：  

1.  在 "请求" 表的 "**名称**" 列下，选择请求的 URL。  
1.  选择 "**页眉**" 选项卡。  

:::image type="complex" source="../media/network-resources-headers.msft.png" alt-text="页眉 选项卡" lightbox="../media/network-resources-headers.msft.png":::
   图21： "**页眉**" 选项卡  
:::image-end:::  

#### 查看 HTTP 域名源  

默认情况下，"页眉" 选项卡按字母顺序显示标题名称。  若要按接收的顺序查看 HTTP 标头名称，请执行以下操作：  

1.  打开您感兴趣的请求的 "**标题**" 选项卡。  请参阅[查看 HTTP 标头](#view-http-headers)。  
1.  选择 "**请求标头**" 或 "**响应标题**" 部分旁边的 "**查看源**"。  

### 查看查询字符串参数  

若要以可读的格式查看 URL 的查询字符串参数，请执行以下操作：  

1.  打开您感兴趣的请求的 "**标题**" 选项卡。  请参阅[查看 HTTP 标头](#view-http-headers)。  
1.  转到 "**查询字符串参数**" 部分。  

:::image type="complex" source="../media/network-network-resources-headers-query-string-parameters.msft.png" alt-text="查询字符串参数 部分" lightbox="../media/network-network-resources-headers-query-string-parameters.msft.png":::
   图22： "**查询字符串参数**" 部分  
:::image-end:::  

#### 查看查询字符串参数源  

要查看请求的查询字符串参数源，请执行以下操作：  

1.  转到 "查询字符串参数" 部分。  请参阅[查看查询字符串参数](#view-query-string-parameters)。  
1.  选择 "**查看源**"。  

#### 查看 URL 编码查询字符串参数  

以人类可读格式查看查询字符串参数，但保留编码：  

1.  转到 "查询字符串参数" 部分。  请参阅[查看查询字符串参数](#view-query-string-parameters)。  
1.  选择 "**查看 URL 编码**"。  

### 查看 cookie  

若要查看在请求的 HTTP 头中发送的 cookie，请执行以下操作：  

1.  在 "请求" 表的 "**名称**" 列下，选择请求的 URL。  
1.  选择 " **cookie** " 选项卡。  

<!--See [Fields][ManageDataCookiesFields] for a description of each of the columns.  -->

<!--[ManageDataCookiesFields]: manage-data/cookies#fields  -->
<!--TODO: add link when section is available -->

:::image type="complex" source="../media/network-network-resources-cookies.msft.png" alt-text="Cookie 选项卡" lightbox="../media/network-network-resources-cookies.msft.png":::
   图23： "Cookies" 选项卡  
:::image-end:::  

### 查看请求的计时细目  

要查看请求的计时细目，请执行以下操作：  

1.  在 "请求" 表的 "**名称**" 列下，选择请求的 URL。  
1.  选择 "**计时**" 选项卡。  

请参阅[预览计时细目](#preview-a-timing-breakdown)以获得更快的访问此数据的方式。  

有关你在 "计时" 选项卡中看到的每个阶段的详细信息，请参阅[介绍的计时分解阶段](#timing-breakdown-phases-explained)。  

:::image type="complex" source="../media/network-network-resources-timing.msft.png" alt-text="计时 选项卡" lightbox="../media/network-network-resources-timing.msft.png":::
   图24： "**计时**" 选项卡  
:::image-end:::  

有关每个阶段的详细信息。  

请参阅[查看计时细目](#view-the-timing-breakdown-of-a-request)以了解另一种访问此视图的方式。  

#### 预览计时细目  

若要查看请求的计时分解的预览，请将鼠标悬停在 "请求" 表的 "**瀑布**图" 列中请求的条目上。  

请参阅[查看请求的计时细目](#view-the-timing-breakdown-of-a-request)以了解访问不需要悬停的数据的方式。  

:::image type="complex" source="../media/network-network-resources-waterfall-hover.msft.png" alt-text="> 预览请求的计时细目" lightbox="../media/network-network-resources-waterfall-hover.msft.png":::
   图25：预览请求的计时细目  
:::image-end:::  

#### 已解释的计时分解阶段  

有关你可能会在 "**计时**" 选项卡中看到的每个阶段的详细信息。  

*   **排队**。  浏览器在以下情况中对请求进行排队：  
    *   优先级较高的请求。  
    *   已为此来源打开6个 TCP 连接，这是限制。  仅适用于 HTTP/1.0 和 HTTP/1.1。  
    *   浏览器在磁盘缓存中短暂分配空间。  
*   **停止**。  由于 "**排队**" 中所述的任何原因，请求可能停止。  
*   **DNS 查找**。  浏览器正在解析请求的 IP 地址。  
*   **初始连接**。  浏览器正在建立连接，包括 TCP 握手、TCP 重试和协商 SSL。
*   **代理协商**。  浏览器正使用[代理服务器][WikiProxyServer]协商请求。  
*   **请求已发送**。  正在发送请求。  
*   **ServiceWorker 准备**。  浏览器正在启动服务工作人员。  
*   **对 ServiceWorker 的请求**。  请求将发送给服务工作人员。  
*   **等待 \ （TTFB \）**。  浏览器正在等待响应的第一个字节。  TTFB 代表第一个字节的时间。  此计时包括延迟的1次往返行程以及服务器准备响应的时间。  
*   **内容下载**。  浏览器正在接收响应。  
*   **接收推送**。  浏览器正在通过 HTTP/2 服务器推送接收此响应的数据。  
*   **正在读取推送**。  浏览器正在读取以前收到的本地数据。  

### 查看启动器和相关性  

若要查看请求的发起程序和依赖关系，请 `Shift` 在请求表中保留并悬停请求。  DevTools 颜色：启动器显示为绿色，相关性显示为红色。  

:::image type="complex" source="../media/network-network-resources-initiators-dependencies.msft.png" alt-text="查看请求的发起人和相关性" lightbox="../media/network-network-resources-initiators-dependencies.msft.png":::
   图26：查看请求的启动器和相关性  
:::image-end:::  

当请求表按时间顺序排序时，悬停的第一个绿色请求上方是依赖项的发起程序。  如果在上面显示了另一个绿色请求，则该请求是发起方的发起方。  以此类推。  

### 查看加载事件  

DevTools 显示 `DOMContentLoaded` `load` 网络面板上多个位置的和事件的计时。  `DOMContentLoaded`事件颜色为蓝色， `load` 事件为红色。  

:::image type="complex" source="../media/network-network-requests-load-events.msft.png" alt-text="DOMContentLoaded 和加载事件在网络面板上的位置" lightbox="../media/network-network-requests-load-events.msft.png":::
   图27： " `DOMContentLoaded` `load` 网络" 面板上的和事件的位置  
:::image-end:::  

### 查看请求总数  

请求总数将列在 "摘要" 窗格中的 "网络" 面板底部。  

> [!CAUTION]
> 此号码仅跟踪自 DevTools 打开以来已记录的请求。  如果在 DevTools 打开之前发生了其他请求，则不会对这些请求进行计数。  

:::image type="complex" source="../media/network-network-total-requests.msft.png" alt-text="自 DevTools 打开以来的请求总数" lightbox="../media/network-network-total-requests.msft.png":::
   图28：自 DevTools 打开以来的请求总数  
:::image-end:::  

### 查看总下载大小  

请求的总下载大小列在 "摘要" 窗格中的 "网络" 面板底部。  

> [!CAUTION]
> 此号码仅跟踪自 DevTools 打开以来已记录的请求。  如果在 DevTools 打开之前发生了其他请求，则不会对以前的请求进行计数。  

:::image type="complex" source="../media/network-network-total-download-size.msft.png" alt-text="请求的总下载大小" lightbox="../media/network-network-total-download-size.msft.png":::
   图29：请求的总下载大小  
:::image-end:::  

请参阅[查看资源的未压缩大小](#view-the-uncompressed-size-of-a-resource)，以查看浏览器 uncompresses 每个项目后的大资源。  

### 查看导致请求的堆栈跟踪  

在 JavaScript 语句请求资源后，将鼠标悬停在**发起程序**列上以查看该请求的最后一个堆栈跟踪。  

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

:::image type="complex" source="../media/network-network-requests-initiator-stack.msft.png" alt-text="堆栈跟踪导致资源请求" lightbox="../media/network-network-requests-initiator-stack.msft.png":::
   图30：导致资源请求的堆栈跟踪  
:::image-end:::  

### 查看资源的未压缩大小  

选中 "**使用大型请求行**" 复选框，然后查看 "**大小**" 列的底部值。  

:::image type="complex" source="../media/network-network-requests-uncompressed-compare.msft.png" alt-text="未压缩资源的示例" lightbox="../media/network-network-requests-uncompressed-compare.msft.png":::
   图31：解压缩的资源的示例 \ （ `jquery-3.3.1.min.js` 通过网络发送的文件的压缩大小是 `29.9 KB` ，未压缩的大小为 `84.9 KB` \）  
:::image-end:::  

## 导出请求数据  

### 将所有网络请求保存到 HAR 文件  

若要将所有网络请求保存到 HAR 文件，请完成以下步骤。  

1.  将鼠标悬停在 "请求" 表中的任何请求上，然后打开上下文菜单 \ （右键单击 \）。  
1.  选择 "**另存为 HAR 和内容**"。  DevTools 将打开 DevTools 后出现的所有请求保存到 HAR 文件。  无法筛选请求，或仅保存单个请求。  

保存 HAR 文件后，可将其导入 DevTools 进行分析。  只需将 HAR 文件拖放到 "请求" 表中。  
<!--See also [HAR Analyzer][HARAnalyzer].  -->  

<!--[HARAnalyzer]: https://toolbox.alphabetapps.com/apps/har_analyzer  -->  
<!--Todo: add section link when content is available  -->  

:::image type="complex" source="../media/network-network-requests-save-har-content.msft.png" alt-text="选择 另存为 HAR 和内容" lightbox="../media/network-network-requests-save-har-content.msft.png":::
   图32：选择 "**另存为 HAR 和内容**"  
:::image-end:::  

### 将一个或多个请求复制到剪贴板  

在 "请求" 表的 "**名称**" 列下，将鼠标悬停在请求上，打开上下文菜单 \ （右键单击 \），将鼠标悬停在 "**复制**" 上，然后选择下列选项之一。  

*   **复制链接地址**。  将请求的 URL 复制到剪贴板。  
*   **复制响应**。  将响应正文复制到剪贴板。  
*   **复制为提取**。  
*   **复制为卷曲**。  将请求复制为卷曲命令。  
*   **全部复制为 "提取**"。  
*   **全部复制为卷曲**。  将所有请求复制为一个卷曲命令链。  
*   **全部复制为 HAR**。  将所有请求复制到 HAR 数据。  

:::image type="complex" source="../media/network-network-requests-copy-response.msft.png" alt-text="选择 复制响应" lightbox="../media/network-network-requests-copy-response.msft.png":::
   图33：选择 "**复制响应**"  
:::image-end:::  

## 更改网络面板的布局  

你可以展开或折叠 "网络面板" UI 的各个部分以重点介绍重要信息。  

### 隐藏 "筛选器" 窗格  

默认情况下，DevTools 显示 "**筛选器" 窗格**。  
选择 "**筛选** ![ 筛选" ][ImageFilterIcon] 以将其隐藏。  

:::image type="complex" source="../media/network-network-resources-hide-filters-button.msft.png" alt-text="隐藏筛选器 按钮" lightbox="../media/network-network-resources-hide-filters-button.msft.png":::
   图34： "隐藏筛选器" 按钮  
:::image-end:::  

### 使用大型请求行  

如果需要在网络请求表中有更多的空格，请使用较大的行。  在使用较大的行时，某些列还提供了一些更多的信息。  例如， **Size**列的底部值是请求的未压缩大小。  

:::image type="complex" source="../media/network-network-requests-large-request-rows.msft.png" alt-text="请求窗格中的大型请求行的示例" lightbox="../media/network-network-requests-large-request-rows.msft.png":::
   图35： "**请求**" 窗格中的大型请求行的示例  
:::image-end:::  

选中 "**使用大请求行**" 复选框以启用大行。  

:::image type="complex" source="../media/network-network-requests-use-large-request-rows-on.msft.png" alt-text="使用大请求行 复选框" lightbox="../media/network-network-requests-use-large-request-rows-on.msft.png":::
   图36： "**使用大型请求行**" 复选框  
:::image-end:::  

### 隐藏 "概述" 窗格  

默认情况下，DevTools 显示 "**概述" 窗格**。  取消选中 "**显示概述**" 复选框以将其隐藏。  

:::image type="complex" source="../media/network-network-requests-show-overview-off.msft.png" alt-text=""显示概述" 复选框" lightbox="../media/network-network-requests-show-overview-off.msft.png":::
   图37： "**显示概述**" 复选框  
:::image-end:::  

<!-- image links -->  

[ImageCaptureScreenshotsIcon]: ../media/capture-screenshots-icon.msft.png  
[ImageClearIcon]: ../media/clear-requests-icon.msft.png  
[ImageFilterIcon]: ../media/filter-icon.msft.png  
[ImageHideIcon]: ../media/hide-overview-icon.msft.png  
[ImageLargeResourceRowsIcon]: ../media/large-resource-rows-button-icon.msft.png  
[ImageRecordOnIcon]: ../media/record-on-icon.msft.png  

<!-- links -->  

[DevtoolsProgressiveWebApps]: /microsoft-edge/devtools-guide-chromium/network/progressive-web-apps "调试渐进式 Web 应用"  

<!--[NetworkConditions]: /microsoft-edge/devtools-guide-chromium/network/network-conditions "Optimize Performance Under Varying Network Conditions"  -->  

[MDNHTTPDataURIs]: https://developer.mozilla.org/docs/Web/HTTP/Basics_of_HTTP/Data_URIs "数据 Url |MDN"  

[WikiProxyServer]: https://en.wikipedia.org/wiki/Proxy_server "代理服务器-维基百科"  

> [!NOTE]
> 此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/network/reference)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools \ & Lighthouse \）创作。  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
