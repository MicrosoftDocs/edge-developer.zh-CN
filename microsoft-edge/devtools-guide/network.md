---
description: 使用 "网络" 面板监视和分析页面资源请求
title: DevTools-网络
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge，web 开发，f12 工具，devtools，网络，加载时间，http，https，浏览器缓存，HAR
ms.custom: seodec18
ms.openlocfilehash: 0b190f5163f9b7a9f9920877a94577177053e4f6
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563463"
---
# Network

使用 " **网络** " 面板监控、检查和分析通过线路发送的请求和响应。 有了它，您可以：

 - 浏览该页发出的[所有资源请求的记录](#network-summary)
 - 为新用户和返回的用户[测量您的网站的加载时间](#summary-bar) 
 - 检查页面和网络之间交换[的标题、邮件正文、参数和 cookie](#request-details)
 - 在你的网站的加载时间内[识别导致瓶颈的网络事件](#timings)

![Microsoft Edge DevTools 网络面板](./media/network.png)

## 网络摘要

打开 DevTools 时，默认情况下，网络分析处于打开状态。 即使在与 *网络*不同的 DevTools 面板中工作时，你的活动浏览器选项卡中的所有网络流量都将记录在 "网络摘要" 列表中。

![正在进行的网络分析指示器](./media/network_profile_indicator.png)

### 工具栏

工具栏提供用于分析和筛选页面的网络活动的控件。 

![网络探查器工具栏](./media/network_toolbar.png)

1. **启动/停止分析会话**：默认情况下，网络分析处于打开状态，网络流量将记录在 [**网络探查器**](#network-request-list) 列表中。 你可以通过 " **停止** () " 按钮关闭网络捕获 `Ctrl+E` 。

2. **导出为 HAR**：您可以将当前的网络分析会话保存 (`Ctrl+S`) 作为 JSON 格式的 [HTTP 存档 (HAR) ](https://dvcs.w3.org/hg/webperf/raw-file/tip/specs/HAR/Overview.html) 文件。 

3. **内容类型筛选**器：按特定内容请求筛选网络请求列表 (*文档、样式表、图像、脚本、媒体、字体、XHR、其他*) 。 默认情况下，显示所有内容类型。

4. **查找**：筛选 (`Ctrl+F`) 包含指定搜索字符串) 资源路径 (资源名称的网络请求列表。

5. **始终从服务器刷新**：按下此按钮将强制从网络加载页面资源，而不是浏览器缓存。 您可以通过按一次即可从网络刷新页面 `Ctrl+F5` 。

6. **跳过所有网络请求的服务工作人员**：将已注册的服务工作人员禁用为网络代理。 

7. 清除按钮

   - **清除缓存**：删除浏览器缓存中存储的所有资源 (并模拟加载页面) 的首次体验。
   - **清除 cookie**：删除给定域 (的所有 cookie，并模拟网站) 的首次体验。
   - **清除导航上的条目**：在页面导航时清除录制的流量。 默认情况下，此项处于打开状态。
   - **清除会话**：从 " **网络摘要** " 列表中清除所有网络请求条目。

### 网络请求列表

所有网络流量都将记录到列表中 (直到在导航、手动清除或 DevTools 关闭) 之前将其清除。 单击任何条目都将打开 [该请求的更详细视图](#request-details)。

![网络请求列表](./media/network_request_list.png)

网络请求列表包含以下信息： 

列 | 描述 
:------------ | :------------- 
**名称** | 请求的名称和 URL 路径
**协议** |  请求的协议类型 (如 *HTTPS、HTTP/2*) 
**方法** |    用于请求的[HTTP 方法](https://developer.mozilla.org/docs/Web/HTTP/Methods)
**结果** |    [HTTP 响应状态](https://developer.mozilla.org/docs/Web/HTTP/Status)  代码
**内容类型** |   ([MIME 类型](https://en.wikipedia.org/wiki/Media_type)) 请求的媒体类型
**已接收** | 服务器发送的响应的大小 (不会为缓存的响应进行计算) 
**时间** |  加载服务器响应的时间 (未针对缓存的响应进行计算) 
**启动** | 负责启动请求的子系统 (*，如分析程序、重定向、脚本、其他*) 
**时间线** | 请求的网络事件的可视化日程表 (例如已 *停止、解析 (DNS) 、连接 (TCP) 、SSL、发送、等待 (TTFB) 、下载*) 。 将鼠标悬停在图表上可提供网络 [网络计时](#timings)) 的粒度明细。

### 摘要栏

**网络**面板底部的栏汇总了网络性能分析会话期间 HTTP 网络错误、请求、传输和加载时间的总数 (也就是说，由于 DevTools 已打开并记录网络流量) 。

![网络摘要栏](./media/network_summary_bar.png)

**经过的时间** 表示分析会话开始与最后一个资源从网络下载之间的时间之间的时间。 从浏览器缓存中获取的资源不会计入此数字的时间。 

**DOM 加载时间** 表示分析会话开始与触发 [DOMContentLoaded](https://developer.mozilla.org/docs/Web/Events/DOMContentLoaded) 事件之间的时间，以指示页面文档的结构已加载并分析 (，但不一定任何样式表、图像或 subframes) 。

"**页面加载时间**" 指的是分析会话开始与触发[加载](https://developer.mozilla.org/docs/Web/Events/load)事件之间的时间，以指示页面文档 (并且已完全加载其所有资源) 。

## 请求详细信息

单击 " [**网络摘要**](#network-summary) " 列表中的任何条目将在 " [**请求详细信息**](#request-details) " 窗格中打开以下每个选项卡中的详细信息。

![网络请求详细信息窗格](./media/network_request_details.png)

### 标题
显示发送到服务器或从服务器接收的 [HTTP 标头](https://developer.mozilla.org/docs/Web/HTTP/Headers) 。 右键单击任意标题条目可将其复制 (`Ctrl+C`) 剪贴板。 你还可以通过按住 `Shift` 键或选择 "所有 (") 来选择多个条目 `Ctrl+A` 。

### 正文
如果可用) 请求和响应负载，则显示正文数据 (。

图像内容与尺寸和大小数据一起显示。

文本内容显示在 (只读) 编辑器中，其中包含使用 **整齐打印** 和/或换 **行** 设置 minified 内容格式的选项，以便更轻松地提高可读性。

!["请求详细信息" 窗格的 "正文" 选项卡](./media/network_details_body.png)

### 参数
显示获取请求的查询字符串参数。 在标头中发送 POST 请求的参数时，GET 请求将其包含在 URL 中。 我们将在此处分解，以便更容易阅读。

右键单击任意行以将其复制 (`Ctrl+C`) 剪贴板。 你还可以通过按住 `Shift` 键或选择 "所有 (") 来选择多个条目 `Ctrl+A` 。

### Cookie
显示作为键/值对发送或接收的 cookie。

右键单击任意行以将其复制 (`Ctrl+C`) 剪贴板。 你还可以通过按住 `Shift` 键或选择 "所有 (") 来选择多个条目 `Ctrl+A` 。

你可以从 [工具栏](#network-summary) 中清除所存储的域的 cookie (" **清除 cookie** " 按钮) 。 

### 计时

" **计时** " 选项卡提供加载所选资源所涉及的网络事件的时间线。 这类似于在 "[网络请求" 列表](#network-request-list)的 "*时间线*" 列中找到的信息，但还包括针对通过线路发送的请求所导致的事件，例如在请求队列中等待的时间 (*停止*) 、DNS 解析以及建立 TCP 连接。 

![请求详细信息窗格的 "计时" 选项卡](./media/network_details_timings.png)

将注明对其他资源的重定向，然后单击该链接即可将焦点设置到 "网络 [请求详细信息](#request details) " 窗格中的该资源。

从缓存中加载的资源不受网络延迟的影响，因此不会显示网络 *计时* 图表。

![从缓存加载的重定向资源](./media/network_details_timings_cache_redirect.png)

下面是你可能会看到的给定资源的不同网络事件，按时间顺序排列：

#### 停止

等待请求队列中的可用网络连接所用的时间。 对于 HTTP 1.0/1.1，Microsoft Edge 允许最多6个 (6) 每个主机名的同时 TCP 连接。 

#### 解析 (DNS) 

在 DNS ([域名系统](https://en.wikipedia.org/wiki/Domain_Name_System)) 中查找资源的主机名的 IP 地址所花费的时间。

#### 连接 (TCP) 

建立 TCP ([传输控制协议](https://en.wikipedia.org/wiki/Transmission_Control_Protocol)) 连接所花费的时间。

#### SSL

与主机的[代理服务器](https://en.wikipedia.org/wiki/Proxy_server)协商 SSL ([安全套接字层](https://en.wikipedia.org/wiki/Transport_Layer_Security)) 连接所用的时间。

#### 给

发送资源请求所用的时间。

#### 正在等待 (TTFB) 

等待主机服务器响应的第一个字节所用的时间 ( "到首字节的时间" 或 " *TTFB*) "。

#### 下载

从服务器读取响应所花费的时间。

## 快捷方式

| 操作                         | 快捷方式     |
|:-------------------------------|:-------------|
| 开始/停止分析会话 | `Ctrl` + `E` |
| 导出为 HAR                  | `Ctrl` + `S` |
| 查找                           | `Ctrl` + `F` |
| 复制                           | `Ctrl` + `C` |

## 已知问题

### 网络收集代理无法启动。

如果您看到此错误消息： **网络收集代理无法** 在网络工具中启动，请按照以下步骤进行解决。

1. 按 `Windows Key`  +  `R` 。

2. 在 "运行" 对话框中，输入 **services.msc**。
![已知问题-1](./media/known_issues_1.PNG)

3. 找到 **Microsoft (R) 诊断中心标准收集器服务** ，然后右键单击它。
![已知问题-2](./media/known_issues_2.PNG)

4. 重新启动 **Microsoft (R) 诊断中心标准收集器服务**。
![已知问题-3](./media/known_issues_3.PNG)

5. 关闭 Microsoft Edge 开发人员工具和选项卡。打开新选项卡，导航到您的页面，然后按 `F12` 。

6. 现在，你应该可以在 **网络** 和你的网页的网络请求旁边看到一个播放标记。
![已知问题-4](./media/known_issues_4-network.PNG)

仍遇到问题？ 请使用 " **发送反馈** " 图标向我们发送您的反馈！ 

![已知问题-5](./media/known_issues_5.PNG)

### 网络收集代理无法停止。

如果您看到此错误消息： **网络收集代理无法** 在网络工具中停止，请按照以下步骤进行解决。

1. 按 `Windows Key`  +  `R` 。

2. 在 "运行" 对话框中，输入 **services.msc**。
![已知问题-1](./media/known_issues_1.PNG)

3. 找到 **Microsoft (R) 诊断中心标准收集器服务** ，然后右键单击它。
![已知问题-2](./media/known_issues_2.PNG)

4. 重新启动 **Microsoft (R) 诊断中心标准收集器服务**。
![已知问题-3](./media/known_issues_3.PNG)

5. 关闭 Microsoft Edge 开发人员工具和选项卡。打开新选项卡，导航到您的页面，然后按 `F12` 。

6. 现在，你应该可以在 **网络** 和你的网页的网络请求旁边看到一个播放标记。
![已知问题-4](./media/known_issues_4-network.PNG)

仍遇到问题？ 请使用 " **发送反馈** " 图标向我们发送您的反馈！ 

![已知问题-5](./media/known_issues_5.PNG)
