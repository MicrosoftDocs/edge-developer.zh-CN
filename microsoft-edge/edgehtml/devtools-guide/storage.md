---
description: 使用存储面板检查 Web 存储、IndexedDB、Cookie 和请求/响应缓存
title: 存储|DevTools
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/03/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， Web 开发， f12 工具， devtools， Web 存储， 本地存储， 会话存储， indexeddb， cookie， 服务工作器， 缓存
ms.custom: seodec18
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 3e970ae0d8ca3a43a309eff7b77400aa3ced5b21
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398894"
---
# <a name="storage"></a>存储

使用 **存储** 面板检查和管理各种本地缓存的数据，包括：  

*   [Web 存储](#local-and-session-storage-managers) \ (本地和会话存储\) 键/值对  
*   [已编制索引的 DB](#indexeddb-manager) 结构化数据  
*   [域](#cookies-list) 的 Cookie  
*   [缓存](#cache-manager) \ (请求/响应对\) 服务工作器调试  

展开其中任何类别并单击子项以打开其资源管理器选项卡。  

## <a name="local-and-session-storage-managers"></a>本地和会话存储管理器  

使用本地存储管理器和会话存储管理器检查和管理页面的 Web 存储。  

存储**面板****的资源选取**器内的本地存储和会话存储[文件夹](./debugger.md#resource-picker)显示页面的源列表。  选择其中一个帧可打开通过[Window.localStorage](https://developer.mozilla.org/docs/Web/API/Window/localStorage)或[Window.sessionStorage](https://developer.mozilla.org/docs/Web/API/Window/sessionStorage)设置的当前键/值对的可编辑表，分别 \ (和/或直接从 DevTools 存储[](#storage-list)列表 \) 设置。  

![DevTools 存储管理器](./media/storage_web_storage.png)  

从"本地存储和会话存储"选项卡中，您可以：  

*   **刷新**\ (`Ctrl+F5` \) ，以查看给定[](#cookies-list)域的当前键/值对集。  \ (脚本更新时列表不自动刷新。\)   
*   **模拟达到**  Microsoft Edge Web 存储的存储限制。  每个域和子域都有自己的存储区域，但存在一个组合限制：  
    *   **子域**：最多 5 个磁盘空间  
    *   **域**：最多 10 个磁盘空间  
    *   **所有域总计**：最多 50 个磁盘空间  

   一旦关闭引用其源的最后一个浏览器选项卡，将清除会话存储。  本地存储条目无限期保留，直到页面或用户手动以编程方式清除：  

   **设置**  > **清除浏览数据**  > **Cookie 和保存的网站数据**  

![从"Microsoft Edge 设置"面板中清除浏览数据](./media/settings_clear_browsing_data.png)  

### <a name="storage-list"></a>存储列表  

从存储列表表中，您可以：  

*   **通过单击表中的** 任一 `key/value` 列名称检查对并排序。  
*   **在** `Key` 单元格 `Value` 中单击，编辑现有条目的和。  
*   **删除** \ (\) 右键单击上下文菜单选项"删除项目"中的 `Del` **条目**。  
*   **通过** 单击表 `key/value` 底部的空行添加新对。  

### <a name="shortcuts"></a>快捷方式

| 操作 | 快捷方式 |  
|:--- |:--- |  
| 刷新 | `Ctrl`+`F5` |  
| 删除项 | `Del` |  
| 复制所选项目 | `Ctrl`+`C` |  
| 全选 | `Ctrl`+`A` |  

## <a name="indexeddb-manager"></a>IndexedDB 管理器  

使用 **IndexedDB** 选项卡检查和管理本地存储在客户端计算机上的结构化数据。  具体来说，您可以检查/排序和刷新对象存储和索引，还可以删除单个键值条目。  

> [!TIP]
> 可以使用我们的 [Audio Mixer](https://developer.microsoft.com/microsoft-edge/testdrive/demos/audiomixer/) 演示在 Microsoft Edge DevTools 中测试 *驱动 IndexedDB* 管理器。  

若要删除为 Microsoft Edge 中的当前用户存储的所有 IndexedDB 数据，请使用"Microsoft Edge 设置 **"** 菜单：  

**...** > **设置**  > **清除浏览数据**  > **Cookie 和保存的网站数据**  

调试器的资源选取器内的文件夹显示页面加载的资源中的源 `IndexedDB` 列表。 [](./debugger.md#resource-picker)  任何 IndexedDB \ (IDB\) 数据库都将在源及其对象存储下列出。  

![DevTools IndexedDB 管理器](./media/storage_indexeddb.png)  

### <a name="indexeddb-toolbar"></a>IndexedDB 工具栏  

从 IndexedDB 工具栏中，您可以：  

*   **刷新**\ (\) 以查看数据库的对象 `Ctrl` + `F5` 存储或索引中的当前条目。  对数据库进行更改时，IndexedDB 管理器不会自动刷新。  

### <a name="object-store-entries-list"></a>对象存储条目列表  

从对象存储或索引表中，您可以：  

*   **通过单击表中的** 任何列名来检查键值对并排序。  
*   **刷新**\ (`Ctrl` + `F5` \)   
*   **删除项目** \ (`Del` \) 删除对象存储或索引中的选定条目。  还可以从右键单击上下文菜单选项"删除[](#context-menu)项目 **"中完成此操作**。  
*   **复制选定项目**\ (`Ctrl` + `C` \) 以将所选项目复制到剪贴板。  您还可以从右键单击上下文菜单选项复制所选[](#context-menu)项目**来完成此操作**。  
*   **选择所有**\ (\) 以选择对象存储或 `Ctrl` + `A` 索引中的所有条目。  还可以从右键单击上下文菜单选项"全[](#context-menu)选 **"来完成此操作**。  

对象存储或索引表的列可排序：  

| 列 | 说明 |  
|:--- |:--- |  
| 密钥 | 键值对 \ (在对象存储上 **) 主键**\) 的名称相同;在索引上进行 (时，索引键 \) 光标的当前键\名称 |  
| 主键 | 键值对的名称 \ (有关[IDB](https://developer.mozilla.org/docs/Web/API/IndexedDB_API/Using_IndexedDB#Structuring_the_database)**** 键 \)  |  
| Value | 键值对的值 |  

有关[IndexedDB](https://developer.mozilla.org/docs/Web/API/IndexedDB_API)概念和用法的更多内容，请查看*MDN* Web 文档。  

### <a name="context-menu"></a>上下文菜单  

除了[*IndexedDB*](#indexeddb-toolbar)工具栏之外，还可以从右键单击"上下文"菜单和/或键盘快捷方式管理对象存储或**** 索引[中的数据](#shortcuts)。  

### <a name="shortcuts"></a>快捷方式

| 操作 | 快捷方式 |  
|:--- |:--- |  
| 刷新 | `Ctrl`+`F5` |  
| 删除键值对 | `Del` |  
| 复制所选项目 | `Ctrl`+`C` |  
| 全选 | `Ctrl +`A' |  

## <a name="cookies-manager"></a>Cookie 管理器  

使用 Cookie 管理器检查和管理给定域的 Cookie。  

调试器的资源选取器内的文件夹显示页面加载的资源中的源 `Cookies` 列表。 [](./debugger.md#resource-picker)  选择其中一个框架将打开一个表，该表代表[HTTP](https://developer.mozilla.org/docs/Web/HTTP/Cookies)标头或通过[Document.cookie 脚本设置的当前 Cookie。](https://developer.mozilla.org/docs/Web/API/Document/cookie)  

![DevTools Cookies 管理器](./media/storage_cookies.png)  

在"Cookie"选项卡工具栏中，您可以：  

*   **刷新**\ (\) Cookie 列表以查看给定域 `Ctrl` + `F5` 的当前 Cookie 集。 [](#cookies-list)  \ (列表不自动刷新。\)   
*   **删除当前**页面路径的所有 cookie \ (`Ctrl` + `Shift` + `Del` \) \ (\) 和 permanent\) 。  
*   **删除当前页面**路径的所有会话 cookie \ (`Ctrl` + `Del` \) \) 。  

若要完全清除 Cookie 列表，您可能需要从网络面板**** 工具栏中清除[域的所有](./network.md#toolbar)Cookie。  

### <a name="cookies-list"></a>Cookie 列表  

从 Cookie 列表表中，您可以：  

*   **单击表中的** 任何列名称，检查 Cookie 并排序。  
*   **在** `Name` 单元格 `Value` 中单击，编辑现有 Cookie 的和。  
*   **删除**\ (\) 右键单击上下文菜单选项中的 `Del` [](#context-menu) `Delete cookie` Cookie。  
*   **单击** 表底部的空行，为给定内容添加新的会话 `Domain/Path` Cookie。  这仅适用于会话 Cookie;必须使用传统 (设置具有特定到期日期的永久 cookie\) 。  And `Domain` `Path` 值根据页面的位置自动填充。  

Cookie 列表的列可排序：

| 列 | 说明 |  
| :--- | :--- |  
| 名称 | Cookie 的名称 |  
| Value | Cookie 的值 |  
| 域 | Cookie \ (的主机名可能为空\)  |  
| 路径 | Cookie \ (的 URL 路径可能为空\)  |  
| 到期 | 作为 HTTP 日期时间戳的 Cookie 的最大生存期。  如果未 `Expires` 设置 `Max-Age` 或未设置，则条目将被视为会话 Cookie。  |  
| 仅 HTTP | 指示 Cookie 是否使用指令进行设置，指示无法从 `HttpOnly` JavaScript 访问该 Cookie |  
| 安全 | 指示 Cookie 是否与指令一起设置，指示它只会从使用 SSL 和 HTTPS 协议的请求发送到 `Secure` 服务器。  |  

有关 Cookie 属性的更多详细信息，请参阅**MDN Web 文档**[集-Cookie](https://developer.mozilla.org/docs/Web/HTTP/Headers/Set-Cookie)参考。  

### <a name="context-menu"></a>上下文菜单  

除了 Cookie 选项卡工具栏之外[](#cookies-manager)，您还可以从右键单击"上下文"菜单和/或键盘**** 快捷方式管理[Cookie。](#shortcuts)  

### <a name="shortcuts"></a>快捷方式  

| 操作 | 快捷方式 |  
|:--- |:--- |  
| 刷新 | `Ctrl`+`F5` |  
| 删除 Cookie | `Del` |  
| 删除所有 Cookie | `Ctrl`+`Shift`+`Del` |  
| 删除所有会话 Cookie | `Ctrl`+`Del` |  
| 复制所选项目 | `Ctrl`+`C` |  
| 全选 | `Ctrl`+`A` |  

### <a name="cache-manager"></a>缓存管理器  

单击特定缓存条目将打开服务工作缓存管理器，您可以在**** 其中检查并选择性地删除缓存条目 \ (`Request` 和 `Response` 键/值对\) ：  

![缓存管理器](./media/storage_cache.png)  

### <a name="shortcuts"></a>快捷方式  

#### <a name="cache-manager"></a>缓存管理器  

| 操作 | 快捷方式 |  
|:--- |:--- |  
| 刷新 | `Ctrl`+`F5` |  
| 删除项 | `Del` |  
| 复制所选项目 | `Ctrl`+`C` |  
| 全选 | `Ctrl`+`A` |  
