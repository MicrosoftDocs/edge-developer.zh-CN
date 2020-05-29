---
description: 使用存储面板检查 web 存储、IndexedDB、cookie 和请求/响应缓存
title: DevTools-存储
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools、web 存储、本地存储、会话存储、indexeddb、cookie、服务工作人员、缓存
ms.custom: seodec18
ms.openlocfilehash: 8de6e1f90f86fa09b116646918c6be1d8cfb0a72
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563454"
---
# 存储

使用**存储**面板检查和管理各种本地缓存的数据，包括：

 - [Web 存储](#local-and-session-storage-managers)（*本地*和*会话*存储）键/值对
 - 已[编制索引的数据库](#indexeddb-manager)结构化数据
 - 域的[cookie](#cookies-list)
 - 服务工作人员调试的[缓存](#cache-manager)（请求/响应对）

展开这些类别中的任何类别，然后单击子条目以打开其 "资源管理器" 选项卡。

## 本地和会话存储管理员

使用*本地存储管理器*和*会话存储管理器*检查和管理页面的 web 存储。 

存储面板的[*资源选取器*](./debugger.md#resource-picker)中的 "**本地存储**" 和 "**会话存储**" 文件夹显示页面的来源列表。 选择其中一个框架会打开一个可编辑的当前键/值对的表，这些表是通过[localStorage](https://developer.mozilla.org/docs/Web/API/Window/localStorage)或[sessionStorage](https://developer.mozilla.org/docs/Web/API/Window/sessionStorage)（和/或直接从 DevTools[存储列表](#storage-list)）设置的。

![DevTools Cookies 管理器](./media/storage_web_storage.png)

从 "*本地存储*" 和 "*会话存储*" 选项卡，您可以：

 - **刷新**（ `Ctrl+F5` ）[存储列表](#cookies-list)以查看给定域的当前键/值对集。 （脚本更新时，列表不会自动刷新。）
 - 模拟达到 Microsoft Edge web 存储**的存储限制**。 每个域和子域都有其自己的存储区域，但有一个组合的限制：
    - **子域：** 最多 5 mb 的空间
    - **域：** 最多 10 mb 的空间
    - **所有域的总计：** 最高为 50 mb 的空间

   一旦最后一个浏览器选项卡被关闭，会话存储就会被清除。 本地存储项无限期地保留，直到通过页面以编程方式或由用户手动清除为止：

   **设置**  > **清除浏览数据**  > **Cookie 和保存的网站数据**

![从 Microsoft Edge 设置面板中清除浏览数据](./media/settings_clear_browsing_data.png)

### 存储列表

从*存储列表*表中，您可以：

 - 通过单击表中的任意一列名称来**检查和排序**键/值对。
 - 通过在单元格中单击来**编辑**现有条目的*键*和*值*。
 - **Delete** （ `Del` ）右键单击上下文菜单选项中的条目，然后单击 "*删除项目*"。
 - 通过单击表底部的空行**添加**新的键/值对。


### 指向

| 操作              | 快捷方式      |
|:--------------------|:--------------|
| 刷新             | `Ctrl` + `F5` |
| 删除项         | `Del`         |
| 复制所选项目 | `Ctrl` + `C`  |
| 全选          | `Ctrl` + `A`  |


## IndexedDB 管理器

使用 " **IndexedDB** " 选项卡检查和管理在客户端计算机上本地存储的结构化数据。 具体说来，你可以检查/排序和刷新你的对象存储和索引，还可以删除单个键值条目。

> [!TIP]
> 你可以使用我们的[音频混合器](https://developer.microsoft.com/microsoft-edge/testdrive/demos/audiomixer/)演示在 Microsoft Edge DevTools 中测试驱动器*IndexedDB 管理器*。

若要删除在 Microsoft Edge 中为当前用户存储的所有 IndexedDB 数据，请使用 Microsoft Edge*设置*菜单：

**...** > **设置**  > **清除浏览数据**  > **Cookie 和保存的网站数据**

调试器的[*资源选取器*](./debugger.md#resource-picker)中的**IndexedDB**文件夹显示由页面加载的资源的来源列表。 任何 IndexedDB （.IDB）数据库将在原始位置列出，以及其对象存储。 

![DevTools IndexedDB manager](./media/storage_indexeddb.png)

### IndexedDB 工具栏

通过*IndexedDB*工具栏，您可以：

 - **刷新**（ `Ctrl+F5` ）可查看数据库的对象存储或索引中的当前条目。 在对数据库进行更改后，IndexedDB 管理器不会自动刷新。

### 对象存储项列表

从 "*对象存储*" 或 "*索引*" 表中，您可以：

 - 通过单击表中的任意列名称来**检查和排序**键/值对。
 - **Refresh** （ `Ctrl+F5` ）
 - **删除项目**（ `Del` ）以删除你的对象存储或索引中所选的条目。 您也可以从右键单击[上下文菜单](#context-menu)选项中执行此操作，然后单击 "*删除项目*"。
 - **复制所选项目**（ `Ctrl+C` ）以将所选项目复制到剪贴板。 您也可以通过右键单击[上下文菜单](#context-menu)选项执行此操作，*复制所选项目*。
 - **选择**"全部 `Ctrl+A` " （）以选择您的对象存储或索引中的所有条目。 您也可以通过右键单击[上下文菜单](#context-menu)选项执行此操作，然后*选择 "全部*"。

可对*对象存储*或*索引*表的列进行排序：

列 | 描述
:------------ | :-------------
密钥 | 循环访问对象存储时的键值对的名称（与*主键*相同）;循环访问索引时索引键（游标的当前键）的名称
主键 | 键值对的名称（有关[有关 .idb 的](https://developer.mozilla.org/docs/Web/API/IndexedDB_API/Using_IndexedDB#Structuring_the_database)详细信息，请参阅*MDN web 文档*）
Value | 键/值对的值

有关[IndexedDB 概念和用法](https://developer.mozilla.org/docs/Web/API/IndexedDB_API)的详细信息，请查看*MDN web 文档*。

### 上下文菜单

除了[ *IndexedDB*工具栏](#indexeddb-toolbar)，您还可以通过右键单击**上下文菜单**和/或键盘[快捷方式](#shortcuts)，在对象存储或索引中管理数据。

### 指向

操作 | 快捷方式
:------------ | :-------------
刷新 | `Ctrl` + `F5`
删除键值对 | `Del`
复制所选项目 | `Ctrl` + `C`
全选 | `Ctrl` + `A`

## Cookies 管理器

使用*cookie 管理器*检查和管理给定域的 cookie。 

调试器的[*资源选取器*](./debugger.md#resource-picker)中的**Cookies**文件夹显示由页面加载的资源的来源列表。 选择其中一个帧会打开一个表，其中包含由[HTTP](https://developer.mozilla.org/docs/Web/HTTP/Cookies)标头设置的当前 cookie 或通过带有[Document cookie](https://developer.mozilla.org/docs/Web/API/Document/cookie)的脚本设置的当前 cookie。

![DevTools Cookies 管理器](./media/storage_cookies.png)

通过 " *Cookies* " 选项卡工具栏，您可以：

 - **刷新**（ `Ctrl+F5` ） [cookie 列表](#cookies-list)以查看给定域的当前 cookie 集。 （列表不会自动刷新。）
 - 删除当前页面路径的**所有 cookie** （ `Ctrl+Shift+Del` ）（会话和永久）。
 - 删除当前页面路径的**所有会话 cookie** （ `Ctrl+Del` ）。

若要彻底清除您的*cookie 列表*，您可能需要从 "[**网络**](./network.md#toolbar)" 面板工具栏中**清除域的所有 cookie** 。

### Cookie 列表

通过*cookie 列表*表，您可以：

 - 通过单击表中的任意列名称，对 cookie**进行检查和排序**。
 - 通过在单元格中单击来**编辑**现有 Cookie 的*名称*和*值*。
 - **Delete** `Del` 从右键单击[上下文菜单](#context-menu)选项中删除（） cookie，*删除 cookie*。
 - 通过单击表底部的空行为给定的*域/路径***添加**新的会话 cookie。 这仅适用于会话 cookie;永久 cookie （具有特定到期日期）必须用传统方法进行设置。 根据页面位置自动填充*域*和*路径*值。

*Cookie 列表*的列是可排序的：

列 | 描述
:------------ | :-------------
名称 | Cookie 的名称
Value | Cookie 的值
域 | Cookie 的主机名（可能为空）
路径 | Cookie 的 URL 路径（可能为空）
到期 | HTTP 日期时间戳形式的 cookie 的最长生存期。 如果未 `Expires` 设置或，则将 `Max-Age` 该项视为*会话*cookie。
仅限 HTTP | 指示 cookie 是否已通过指令进行了设置 `HttpOnly` ，以指示它无法从 JavaScript 中访问
安全 | 指示是否使用该指令设置 cookie `Secure` ，指示它将仅从使用 SSL 和 HTTPS 协议的请求发送到服务器。

有关 cookie 属性的更多详细信息，请参阅**MDN web 文档**[集-cookie](https://developer.mozilla.org/docs/Web/HTTP/Headers/Set-Cookie)参考。

### 上下文菜单

除了 " *Cookies* " 选项卡[工具栏](#cookies-manager)，您还可以通过右键单击**上下文菜单**和/或键盘[快捷方式](#shortcuts)管理您的 cookie。

### 指向

| 操作                     | 快捷方式                 |
|:---------------------------|:-------------------------|
| 刷新                    | `Ctrl` + `F5`            |
| 删除 cookie              | `Del`                    |
| 删除所有 cookie         | `Ctrl` + `Shift` + `Del` |
| 删除所有会话 cookie | `Ctrl` + `Del`           |
| 复制所选项目        | `Ctrl` + `C`             |
| 全选                 | `Ctrl` + `A`             |

### 缓存管理器

单击特定的缓存条目将打开服务工作人员**缓存**管理器，您可以在其中检查和删除缓存条目（*请求*和*响应*键/值对）：

![缓存管理器](./media/storage_cache.png)

### 指向

#### 缓存管理器

| 操作              | 快捷方式      |
|:--------------------|:--------------|
| 刷新             | `Ctrl` + `F5` |
| 删除项         | `Del`         |
| 复制所选项目 | `Ctrl` + `C`  |
| 全选          | `Ctrl` + `A`  |
