---
description: 使用"网络"面板监视和配置文件页资源请求
title: DevTools - 网络
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， Web 开发， f12 工具， devtools， 网络， 加载时间， http， https， 浏览器缓存， HAR
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 261226c7210d978f11290816c81355bb0142dee9
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232492"
---
# Network

使用 **网络** 面板监视、检查和配置文件通过线路发送的请求和响应。 通过它，你可以：

 - [浏览页面提出的所有](#network-summary) 资源请求的记录
 - [测量新用户和](#summary-bar) 返回用户的网站的加载时间 
 - [检查页面和网络之间](#request-details) 交换的标头、邮件正文、参数和 Cookie
 - [确定在站点的加载时间](#timings) 导致瓶颈的网络事件

![Microsoft Edge DevTools 网络面板](./media/network.png)

## 网络摘要

打开 DevTools 时，网络分析默认打开。 来自活动浏览器选项卡的所有网络流量都记录在网络摘要列表中，即使你在不同的 DevTools 面板中工作，而不是 *网络*。

![进行中的网络分析指示器](./media/network_profile_indicator.png)

### 工具栏

工具栏提供用于分析和筛选页面的网络活动的控件。 

![网络探查器工具栏](./media/network_toolbar.png)

1. **开始/停止分析会话**：默认情况下，网络分析已打开，网络流量将记录在 [**网络分析器**](#network-request-list) 列表中。 你可以关闭网络捕获，并按"**** 停止 `Ctrl+E` () 按钮。

2. **导出为 HAR：** 可以将当前网络分析会话 () 为 JSON 格式的 HTTP 存档 (`Ctrl+S` HAR [) ](https://dvcs.w3.org/hg/webperf/raw-file/tip/specs/HAR/Overview.html) 文件。 

3. **内容类型筛选器**：按特定内容请求筛选网络请求列表 (文档、样式表、图像、脚本、 *媒体、字体、XHR、其他*) 。 默认情况下，将显示所有内容类型。

4. **Find**： Filter () list `Ctrl+F` by entry names (resource paths) containing a specified search string.

5. **始终从服务器刷新**：按下此按钮将强制从网络而不是浏览器缓存加载页面资源。 可以通过按从网络刷新页面一次 `Ctrl+F5` 。

6. **针对所有网络请求绕过**服务工作线程：禁用注册的服务工作者作为网络代理。 

7. 清除按钮

   - **清除缓存**：删除浏览器缓存中存储的所有 (并模拟在浏览器中加载页面的首次) 。
   - **清除 Cookie：** 删除给定域的所有 cookie (并模拟网站集的首次) 。
   - **导航时清除条目**：在页面导航时清除记录的流量。 默认情况下，此选项为打开状态。
   - **清除会话**：清除网络摘要列表中的所有 **网络请求** 条目。

### 网络请求列表

所有网络流量将记录到列表中 (，直到导航、手动清除或开发人员工具关闭) 。 单击任何条目将打开请求 [的更详细的视图](#request-details)。

![网络请求列表](./media/network_request_list.png)

网络请求列表包括以下信息： 

列 | 说明 
:------------ | :------------- 
**名称** | 请求的名称和 URL 路径
**协议** |  请求服务器的协议类型 (*如 HTTPS、HTTP/2*) 
**方法** |    [用于请求](https://developer.mozilla.org/docs/Web/HTTP/Methods) 的 HTTP 方法
**结果** |    [HTTP 响应状态](https://developer.mozilla.org/docs/Web/HTTP/Status)  代码
**内容类型** |  MIME 类型 ([请求的媒体](https://en.wikipedia.org/wiki/Media_type)) 
**已接收** | 未针对缓存响应 (服务器传递的响应大小) 
**时间** |  未为缓存的响应 (加载服务器响应) 
**发起人** | 负责启动请求请求的子系统 (分析器、重定向、 *脚本、其他*) 
**时间线** | 请求 (的网络事件的可视时间线，例如停止、解析 (*DNS) 、连接 (TCP) 、SSL、发送、等待 (TTFB) 、* 下载) 。 将鼠标悬停在图表上可更精细地细分网络[](#timings)) 。

### 摘要栏

网络面板底部的栏汇总了**** 网络分析会话期间 HTTP 网络错误、请求、传输的数据和加载时间的总次数 (即，自 DevTools 打开并记录网络流量) 。

![网络摘要栏](./media/network_summary_bar.png)

**已用** 时间是指从分析会话开始到从网络下载最后一个资源之间的时间。 从浏览器缓存获取的资源不会为此数字累算时间。 

**DOM** 加载时间是指从分析会话开始到 [触发 DOMContentLoaded](https://developer.mozilla.org/docs/Web/Events/DOMContentLoaded) 事件以指示页面文档的结构已加载和分析 (但不必是任何样式表、图像或子框架) 。

**** 页面加载时间是指从分析会话开始到触发加载事件以指示页面文档已完全[](https://developer.mozilla.org/docs/Web/Events/load)加载 (及其所有资源) 的时间。

## 请求详细信息

单击"网络摘要"列表中的[**任何**](#network-summary)条目将打开"请求详细信息[****](#request-details)"窗格，并包含以下每个选项卡中的详细信息。

![网络请求详细信息窗格](./media/network_request_details.png)

### 标题
显示 [发送到服务器](https://developer.mozilla.org/docs/Web/HTTP/Headers) 和从服务器接收的 HTTP 标头。 右键单击任何标题项，将其 `Ctrl+C` () 剪贴板。 也可以按住该键或选择所有项目，以多选 `Shift` `Ctrl+A` () 。

### 正文
显示正文数据 (（如果) 有效负载）。

图像内容随尺寸和大小数据一起显示。

文本内容显示在只读 (编辑器中，) 选项来设置缩小内容 **的格式，并** 打印和/或 **Word** 自动换行，以便于可读性。

![请求详细信息窗格的"正文"选项卡](./media/network_details_body.png)

### 参数
显示 GET 请求的查询字符串参数。 当 POST 请求的参数在标头中发送时，GET 请求会将它们包括在 URL 中。 它们在此处进行细分以便于阅读。

右键单击任何行以将其 `Ctrl+C` () 剪贴板。 也可以按住该键或选择所有项目，以多选 `Shift` `Ctrl+A` () 。

### Cookie
显示为键/值对发送或接收的 Cookie。

右键单击任何行以将其 `Ctrl+C` () 剪贴板。 也可以按住该键或选择所有项目，以多选 `Shift` `Ctrl+A` () 。

You can clear the stored cookie for the given domain from the [Toolbar](#network-summary) (**Clear cookies** button) . 

### 计时

The **Timings** tab provides a timeline of network events involved in the loading of the selected resource. 这类似于在网络请求列表的"日程表**"列中找到的信息[](#network-request-list)，还包括导致通过线路发送请求的事件，例如等待请求队列中的 (*Stalled*) 、DNS 解析和建立 TCP 连接所花的时间。 

![请求详细信息窗格的"计时"选项卡](./media/network_details_timings.png)

将指出重定向到其他资源/从其他资源重定向到其他资源，单击链接将在网络请求详细信息窗格中将焦点设置为 [该](#request details) 资源。

从缓存加载的资源不受网络延迟的影响，因此不会显示 *任何网络计时* 图表。

![从缓存加载的重定向资源](./media/network_details_timings_cache_redirect.png)

以下是你可能为给定资源看到的不同网络事件，按时间顺序排序：

#### 已停止

等待请求队列中的可用网络连接所花的时间。 对于 HTTP 1.0/1.1，Microsoft Edge 允许每个主机名 (6) TCP 连接。 

#### 解析 (DNS) 

在 DNS 或域名系统服务中查找资源的主机名 ([IP](https://en.wikipedia.org/wiki/Domain_Name_System)) 。

#### 连接 (TCP) 

建立 TCP 传输控制协议 ([连接](https://en.wikipedia.org/wiki/Transmission_Control_Protocol)) 的时间。

#### SSL

与主机的代理服务器 ([安全套接字层) ](https://en.wikipedia.org/wiki/Transport_Layer_Security) SSL [协议所](https://en.wikipedia.org/wiki/Proxy_server) 花的时间。

#### 发送

发送资源请求所花费的时间。

#### 等待 (TTFB) 

等待主机服务器响应的第一个字节 ("第一个字节的时间"或 *TTFB*) 。

#### 下载

从服务器读取响应所花的时间。

## 快捷方式

| 操作                         | 快捷方式     |
|:-------------------------------|:-------------|
| 启动/停止分析会话 | `Ctrl` + `E` |
| 导出为 HAR                  | `Ctrl` + `S` |
| 查找                           | `Ctrl` + `F` |
| 复制                           | `Ctrl` + `C` |

## 已知问题

### 网络集合代理启动失败。

如果看到以下错误消息： **网络收集** 代理在网络工具中启动失败，请按照以下步骤获取解决方法。

1. 按 `Windows Key`  +  `R` 。

2. 在"运行"对话框中，输入**services.msc。**
![known-issues-1](./media/known_issues_1.PNG)

3. 找到 **Microsoft (R) 诊断中心标准收集器服务** 并右键单击它。
![known-issues-2](./media/known_issues_2.PNG)

4. 重新启动 **Microsoft (R) 诊断中心标准收集器服务**。
![known-issues-3](./media/known_issues_3.PNG)

5. 关闭 Microsoft Edge 开发人员工具和选项卡。打开新选项卡，导航到页面，然后按 `F12` 。

6. 现在，应该会看到"网络"旁边的"**** 播放"锁屏提醒和网页的网络请求。
![known-issues-4](./media/known_issues_4-network.PNG)

是否仍遇到问题？ 请使用"发送反馈"图标 **向我们发送反馈** ！ 

![known-issues-5](./media/known_issues_5.PNG)

### 网络集合代理停止失败。

如果看到以下错误消息： **网络收集代理** 在网络工具中停止失败，请按照以下步骤获取解决方法。

1. 按 `Windows Key`  +  `R` 。

2. 在"运行"对话框中，输入**services.msc。**
![known-issues-1](./media/known_issues_1.PNG)

3. 找到 **Microsoft (R) 诊断中心标准收集器服务** 并右键单击它。
![known-issues-2](./media/known_issues_2.PNG)

4. 重新启动 **Microsoft (R) 诊断中心标准收集器服务**。
![known-issues-3](./media/known_issues_3.PNG)

5. 关闭 Microsoft Edge 开发人员工具和选项卡。打开新选项卡，导航到页面，然后按 `F12` 。

6. 现在，应该会看到"网络"旁边的"**** 播放"锁屏提醒和网页的网络请求。
![known-issues-4](./media/known_issues_4-network.PNG)

是否仍遇到问题？ 请使用"发送反馈"图标 **向我们发送反馈** ！ 

![known-issues-5](./media/known_issues_5.PNG)
