---
description: 使用存储面板检查 Web 存储、IndexedDB、Cookie 和请求/响应缓存
title: DevTools - 存储
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， Web 开发， f12 工具， devtools， Web 存储， 本地存储， 会话存储， indexeddb， cookie， 服务工作器， 缓存
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 90a2e2fdb0f329c3d83f52beb9eba169bdd48520
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232113"
---
# 存储

使用 **存储** 面板检查和管理各种本地缓存的数据，包括：

 - [Web 存储](#local-and-session-storage-managers) (*会话* 存储 *) /* 值对
 - [已编制索引的 DB](#indexeddb-manager) 结构化数据
 - [域](#cookies-list) 的 Cookie
 - [缓存](#cache-manager) (工作器调试) /响应对

展开其中任何类别并单击子项以打开其资源管理器选项卡。

## 本地和会话存储管理器

使用 *本地存储管理器* 和 *会话存储管理器* 检查和管理页面的 Web 存储。 

存储**面板**的资源选取**器**内的本地存储和会话存储文件夹显示页面[**](./debugger.md#resource-picker)的源列表。 选择其中一个帧可打开通过[Window.localStorage](https://developer.mozilla.org/docs/Web/API/Window/localStorage)或[Window.sessionStorage](https://developer.mozilla.org/docs/Web/API/Window/sessionStorage)设置的当前键/值对的可编辑表，该表分别为 (和/或直接从 DevTools[](#storage-list)存储列表) 。

![DevTools 本地存储管理器](./media/storage_web_storage.png)

从 *"本地存储和**会话存储"* 选项卡中，您可以：

 - **刷新** () 列表，以查看给定域的当前 `Ctrl+F5` 键[](#cookies-list)/值对集。  (脚本更新时列表不自动刷新。) 
 - **模拟达到** Microsoft Edge Web 存储的存储限制。 每个域和子域都有自己的存储区域，但存在一个组合限制：
    - **子域：** 最多 5 个磁盘空间
    - **域：** 最多 10 个磁盘空间
    - **所有域总计：** 最多 50 个磁盘空间

   一旦关闭引用其源的最后一个浏览器选项卡，就会清除会话存储。 本地存储条目无限期保留，直到页面或用户手动以编程方式清除：

   **设置**  > **清除浏览数据**  > **Cookie 和保存的网站数据**

![从 Microsoft Edge 设置面板中清除浏览数据](./media/settings_clear_browsing_data.png)

### 存储列表

从 *存储列表* 表中，您可以：

 - **通过单击表中的** 任一列名称来检查键/值对并排序。
 - **通过***单击**单元格*编辑现有条目的键和值。
 - **从** () 上下文菜单选项"删除项目" `Del` 中删除 *条目*。
 - **单击** 表格底部的空行，添加新的键/值对。


### 快捷方式

| 操作              | 快捷方式      |
|:--------------------|:--------------|
| 刷新             | `Ctrl` + `F5` |
| 删除项         | `Del`         |
| 复制选定项目 | `Ctrl` + `C`  |
| 全选          | `Ctrl` + `A`  |


## IndexedDB 管理器

使用 **IndexedDB** 选项卡检查和管理存储在客户端计算机上的本地结构化数据。 具体来说，您可以检查/排序和刷新对象存储和索引，还可以删除单个键值条目。

> [!TIP]
> 可以使用我们的 [Audio Mixer](https://developer.microsoft.com/microsoft-edge/testdrive/demos/audiomixer/) 演示在 Microsoft Edge DevTools 中测试 *驱动 IndexedDB* 管理器。

若要删除为 Microsoft Edge 中的当前用户存储的所有 IndexedDB 数据，请使用"Microsoft Edge 设置 *"* 菜单：

**...** > **设置**  > **清除浏览数据**  > **Cookie 和保存的网站数据**

调试器的资源选取器内的**IndexedDB** [**](./debugger.md#resource-picker)文件夹显示页面加载的资源的来源列表。 任何 IndexedDB (IDB) 数据库都将在源及其对象存储下列出。 

![DevTools IndexedDB 管理器](./media/storage_indexeddb.png)

### IndexedDB 工具栏

从 *IndexedDB* 工具栏中，您可以：

 - **刷新** () 以查看数据库的对象 `Ctrl+F5` 存储或索引中的当前条目。 对数据库进行更改时，IndexedDB 管理器不会自动刷新。

### 对象存储条目列表

在 *"对象存储"或**"索引"* 表中，您可以：

 - **单击表中的** 任何列名称，检查键值对并排序。
 - **刷新** `Ctrl+F5` () 
 - **删除 () ，** 以删除对象存储或 `Del` 索引中的选定条目。 还可以从右键单击上下文菜单选项"删除[](#context-menu)项目 *"中完成此操作*。
 - **复制所选** `Ctrl+C` () ，将所选项目复制到剪贴板。 还可以从右键单击上下文菜单选项"复制[](#context-menu)所选项目 *"中完成此操作*。
 - **Select all** (`Ctrl+A`) to select all thentries in your object store or index. 还可以从右键单击上下文菜单选项"全[](#context-menu)选 *"中完成此操作*。

对象存储*或索引*表的列** 可排序：

列 | 描述
:------------ | :-------------
密钥 | 键值对的名称与 (*对象* 存储) 主键对的名称相同;在索引上 (时，) 当前键的名称
主键 | 键值对的名称，请参阅 *MDN (，* 详细了解 [IDB](https://developer.mozilla.org/docs/Web/API/IndexedDB_API/Using_IndexedDB#Structuring_the_database) 密钥) 
值 | 键值对的值

查看 *MDN Web 文档，* 了解有关 [IndexedDB 概念和用法的更多内容](https://developer.mozilla.org/docs/Web/API/IndexedDB_API)。

### 上下文菜单

除了[*IndexedDB*](#indexeddb-toolbar)工具栏之外，还可以从右键单击"上下文"菜单和/或键盘快捷方式管理对象存储或**** 索引[中的数据](#shortcuts)。

### 快捷方式

操作 | 快捷方式
:------------ | :-------------
刷新 | `Ctrl` + `F5`
删除键值对 | `Del`
复制选定项目 | `Ctrl` + `C`
全选 | `Ctrl` + `A`

## Cookie 管理器

使用 *Cookie 管理器* 检查和管理给定域的 Cookie。 

调试**器**的资源选取器内的 Cookie 文件夹[**](./debugger.md#resource-picker)显示页面加载的资源的来源列表。 选择其中一个帧将打开一个表，该表代表[HTTP](https://developer.mozilla.org/docs/Web/HTTP/Cookies)标头或通过[Document.cookie 脚本设置的当前 Cookie。](https://developer.mozilla.org/docs/Web/API/Document/cookie)

![DevTools Cookies 管理器](./media/storage_cookies.png)

在 *"Cookie"* 选项卡工具栏中，您可以：

 - **刷新** () Cookie `Ctrl+F5` [列表](#cookies-list) ，以查看给定域的当前 Cookie 集。  (列表不自动刷新.) 
 - **删除当前** ()  (的所有 cookie `Ctrl+Shift+Del` 和) 的永久 Cookie。
 - **删除当前页面** `Ctrl+Del` () 的所有会话 Cookie。

若要完全清除*Cookie 列表*，您可能需要从网络面板**** 工具栏中清除[**域的所有**](./network.md#toolbar)Cookie。

### Cookie 列表

从 *Cookie 列表* 表中，您可以：

 - **通过单击** 表中的任何列名称来检查 Cookie 并排序。
 - **在***单元格*中*单击*，编辑现有 Cookie 的名称和值。
 - **从** () 菜单选项"删除 Cookie"中删除 `Del` Cookie。 [](#context-menu) **
 - **单击** 表底部的空行，为给定的 *域/路径* 添加新的会话 Cookie。 这仅适用于会话 Cookie;具有特定 (日期的永久性) 必须使用传统方法进行设置。 域*和**路径*值根据页面的位置自动填充。

Cookie 列表的 *列可* 排序：

列 | 描述
:------------ | :-------------
名称 | Cookie 的名称
值 | Cookie 的值
域 | Cookie 主机名 (可能为空) 
路径 | Cookie 网站的 URL (可能为空) 
到期 | 作为 HTTP 日期时间戳的 Cookie 的最大生存期。 如果未 `Expires` 设置 `Max-Age` 或已设置，则条目将被视为 *会话* Cookie。
仅 HTTP | 指示 Cookie 是否设置有指令，指示无法通过 `HttpOnly` JavaScript 访问
安全 | 指示 Cookie 是否使用指令进行设置，指示它仅从使用 SSL 和 HTTPS 协议的请求 `Secure` 发送到服务器。

有关 Cookie 属性的更多详细信息，请参阅**MDN Web 文档**[集](https://developer.mozilla.org/docs/Web/HTTP/Headers/Set-Cookie)Cookie 参考。

### 上下文菜单

除了 *"Cookie"* 选项卡[工具栏](#cookies-manager)之外，您还可以从右键单击的"上下文"菜单和/或**** 键盘快捷方式管理[Cookie。](#shortcuts)

### 快捷方式

| 操作                     | 快捷方式                 |
|:---------------------------|:-------------------------|
| 刷新                    | `Ctrl` + `F5`            |
| 删除 Cookie              | `Del`                    |
| 删除所有 Cookie         | `Ctrl` + `Shift` + `Del` |
| 删除所有会话 Cookie | `Ctrl` + `Del`           |
| 复制选定项目        | `Ctrl` + `C`             |
| 全选                 | `Ctrl` + `A`             |

### 缓存管理器

单击特定缓存条目将打开服务工作线程缓存管理器，**** 您可以在其中检查和选择删除请求和响应 (/值对中的缓存) ： ** **

![缓存管理器](./media/storage_cache.png)

### 快捷方式

#### 缓存管理器

| 操作              | 快捷方式      |
|:--------------------|:--------------|
| 刷新             | `Ctrl` + `F5` |
| 删除项         | `Del`         |
| 复制选定项目 | `Ctrl` + `C`  |
| 全选          | `Ctrl` + `A`  |
