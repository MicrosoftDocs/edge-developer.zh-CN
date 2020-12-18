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
# <span data-ttu-id="88e15-104">存储</span><span class="sxs-lookup"><span data-stu-id="88e15-104">Storage</span></span>

<span data-ttu-id="88e15-105">使用 **存储** 面板检查和管理各种本地缓存的数据，包括：</span><span class="sxs-lookup"><span data-stu-id="88e15-105">Use the **Storage** panel to inspect and manage various locally cached data, including:</span></span>

 - <span data-ttu-id="88e15-106">[Web 存储](#local-and-session-storage-managers) (*会话* 存储 *) /* 值对</span><span class="sxs-lookup"><span data-stu-id="88e15-106">[Web storage](#local-and-session-storage-managers) (*Local* and *Session* storage) key/values pairs</span></span>
 - <span data-ttu-id="88e15-107">[已编制索引的 DB](#indexeddb-manager) 结构化数据</span><span class="sxs-lookup"><span data-stu-id="88e15-107">[Indexed DB](#indexeddb-manager) structured data</span></span>
 - <span data-ttu-id="88e15-108">[域](#cookies-list) 的 Cookie</span><span class="sxs-lookup"><span data-stu-id="88e15-108">[Cookies](#cookies-list) for the domain</span></span>
 - <span data-ttu-id="88e15-109">[缓存](#cache-manager) (工作器调试) /响应对</span><span class="sxs-lookup"><span data-stu-id="88e15-109">[Cache](#cache-manager) (request/response pairs) for service worker debugging</span></span>

<span data-ttu-id="88e15-110">展开其中任何类别并单击子项以打开其资源管理器选项卡。</span><span class="sxs-lookup"><span data-stu-id="88e15-110">Expand any of those categories and click on a child entry to open its resource manager tab.</span></span>

## <span data-ttu-id="88e15-111">本地和会话存储管理器</span><span class="sxs-lookup"><span data-stu-id="88e15-111">Local and Session storage managers</span></span>

<span data-ttu-id="88e15-112">使用 *本地存储管理器* 和 *会话存储管理器* 检查和管理页面的 Web 存储。</span><span class="sxs-lookup"><span data-stu-id="88e15-112">Use the *Local Storage manager* and *Session Storage manager* to inspect and manage the web storage for  your page.</span></span> 

<span data-ttu-id="88e15-113">存储**面板**的资源选取**器**内的本地存储和会话存储文件夹显示页面[\*\*](./debugger.md#resource-picker)的源列表。</span><span class="sxs-lookup"><span data-stu-id="88e15-113">The **Local Storage** and **Session Storage** folders inside the Storage panel's [*Resource picker*](./debugger.md#resource-picker) display a list of origins for the page.</span></span> <span data-ttu-id="88e15-114">选择其中一个帧可打开通过[Window.localStorage](https://developer.mozilla.org/docs/Web/API/Window/localStorage)或[Window.sessionStorage](https://developer.mozilla.org/docs/Web/API/Window/sessionStorage)设置的当前键/值对的可编辑表，该表分别为 (和/或直接从 DevTools[](#storage-list)存储列表) 。</span><span class="sxs-lookup"><span data-stu-id="88e15-114">Selecting one of these frames opens up an editable table of the current key/value pairs set via [Window.localStorage](https://developer.mozilla.org/docs/Web/API/Window/localStorage) or [Window.sessionStorage](https://developer.mozilla.org/docs/Web/API/Window/sessionStorage), respectively (and/or set directly from the  DevTools [Storage list](#storage-list)).</span></span>

![DevTools 本地存储管理器](./media/storage_web_storage.png)

<span data-ttu-id="88e15-116">从 *"本地存储和\*\*会话存储"* 选项卡中，您可以：</span><span class="sxs-lookup"><span data-stu-id="88e15-116">From the *Local Storage* and *Session Storage* tabs you can:</span></span>

 - <span data-ttu-id="88e15-117">**刷新** () 列表，以查看给定域的当前 `Ctrl+F5` 键[](#cookies-list)/值对集。</span><span class="sxs-lookup"><span data-stu-id="88e15-117">**Refresh** (`Ctrl+F5`) the [storage list](#cookies-list) to see the current set of key/values pairs for the given domain.</span></span> <span data-ttu-id="88e15-118"> (脚本更新时列表不自动刷新。) </span><span class="sxs-lookup"><span data-stu-id="88e15-118">(The list does not auto-refresh upon script updates.)</span></span>
 - <span data-ttu-id="88e15-119">**模拟达到** Microsoft Edge Web 存储的存储限制。</span><span class="sxs-lookup"><span data-stu-id="88e15-119">**Simulate reaching the storage limit** for Microsoft Edge web storage.</span></span> <span data-ttu-id="88e15-120">每个域和子域都有自己的存储区域，但存在一个组合限制：</span><span class="sxs-lookup"><span data-stu-id="88e15-120">Each domain and subdomain has its own storage area, however there is a combined limit:</span></span>
    - <span data-ttu-id="88e15-121">**子域：** 最多 5 个磁盘空间</span><span class="sxs-lookup"><span data-stu-id="88e15-121">**Subdomains:** up to 5 MBs of space</span></span>
    - <span data-ttu-id="88e15-122">**域：** 最多 10 个磁盘空间</span><span class="sxs-lookup"><span data-stu-id="88e15-122">**Domains:** up to 10 MBs of space</span></span>
    - <span data-ttu-id="88e15-123">**所有域总计：** 最多 50 个磁盘空间</span><span class="sxs-lookup"><span data-stu-id="88e15-123">**Total for all domains:** up to 50 MBs of space</span></span>

   <span data-ttu-id="88e15-124">一旦关闭引用其源的最后一个浏览器选项卡，就会清除会话存储。</span><span class="sxs-lookup"><span data-stu-id="88e15-124">Session storage is cleared as soon as the last browser tab referencing its origin is closed.</span></span> <span data-ttu-id="88e15-125">本地存储条目无限期保留，直到页面或用户手动以编程方式清除：</span><span class="sxs-lookup"><span data-stu-id="88e15-125">Local storage entries persist indefinitely until cleared programmatically by the page or manually by the user:</span></span>

   <span data-ttu-id="88e15-126">**设置**  > **清除浏览数据**  > **Cookie 和保存的网站数据**</span><span class="sxs-lookup"><span data-stu-id="88e15-126">**Settings** > **Clear browsing data** > **Cookies and saved website data**</span></span>

![从 Microsoft Edge 设置面板中清除浏览数据](./media/settings_clear_browsing_data.png)

### <span data-ttu-id="88e15-128">存储列表</span><span class="sxs-lookup"><span data-stu-id="88e15-128">Storage list</span></span>

<span data-ttu-id="88e15-129">从 *存储列表* 表中，您可以：</span><span class="sxs-lookup"><span data-stu-id="88e15-129">From the *Storage list* table you can:</span></span>

 - <span data-ttu-id="88e15-130">**通过单击表中的** 任一列名称来检查键/值对并排序。</span><span class="sxs-lookup"><span data-stu-id="88e15-130">**Inspect and sort** your key/value pairs by clicking on either column name in the table.</span></span>
 - <span data-ttu-id="88e15-131">**通过\*\*\*单击**单元格\*编辑现有条目的键和值。</span><span class="sxs-lookup"><span data-stu-id="88e15-131">**Edit** the *Key* and *Value* of an existing entry by clicking in the cell.</span></span>
 - <span data-ttu-id="88e15-132">**从** () 上下文菜单选项"删除项目" `Del` 中删除 *条目*。</span><span class="sxs-lookup"><span data-stu-id="88e15-132">**Delete** (`Del`) an entry from the right-click context menu option, *Delete item*.</span></span>
 - <span data-ttu-id="88e15-133">**单击** 表格底部的空行，添加新的键/值对。</span><span class="sxs-lookup"><span data-stu-id="88e15-133">**Add** a new key/value pair by clicking on the empty row at the bottom of the table.</span></span>


### <span data-ttu-id="88e15-134">快捷方式</span><span class="sxs-lookup"><span data-stu-id="88e15-134">Shortcuts</span></span>

| <span data-ttu-id="88e15-135">操作</span><span class="sxs-lookup"><span data-stu-id="88e15-135">Action</span></span>              | <span data-ttu-id="88e15-136">快捷方式</span><span class="sxs-lookup"><span data-stu-id="88e15-136">Shortcut</span></span>      |
|:--------------------|:--------------|
| <span data-ttu-id="88e15-137">刷新</span><span class="sxs-lookup"><span data-stu-id="88e15-137">Refresh</span></span>             | `Ctrl` + `F5` |
| <span data-ttu-id="88e15-138">删除项</span><span class="sxs-lookup"><span data-stu-id="88e15-138">Delete item</span></span>         | `Del`         |
| <span data-ttu-id="88e15-139">复制选定项目</span><span class="sxs-lookup"><span data-stu-id="88e15-139">Copy selected items</span></span> | `Ctrl` + `C`  |
| <span data-ttu-id="88e15-140">全选</span><span class="sxs-lookup"><span data-stu-id="88e15-140">Select all</span></span>          | `Ctrl` + `A`  |


## <span data-ttu-id="88e15-141">IndexedDB 管理器</span><span class="sxs-lookup"><span data-stu-id="88e15-141">IndexedDB manager</span></span>

<span data-ttu-id="88e15-142">使用 **IndexedDB** 选项卡检查和管理存储在客户端计算机上的本地结构化数据。</span><span class="sxs-lookup"><span data-stu-id="88e15-142">Use the **IndexedDB** tab to inspect and manage the structured data stored locally on a client machine.</span></span> <span data-ttu-id="88e15-143">具体来说，您可以检查/排序和刷新对象存储和索引，还可以删除单个键值条目。</span><span class="sxs-lookup"><span data-stu-id="88e15-143">Specifically, you can inspect/sort and refresh your object stores and indices, and also delete individual key-value entries.</span></span>

> [!TIP]
> <span data-ttu-id="88e15-144">可以使用我们的 [Audio Mixer](https://developer.microsoft.com/microsoft-edge/testdrive/demos/audiomixer/) 演示在 Microsoft Edge DevTools 中测试 *驱动 IndexedDB* 管理器。</span><span class="sxs-lookup"><span data-stu-id="88e15-144">You can use our [Audio Mixer](https://developer.microsoft.com/microsoft-edge/testdrive/demos/audiomixer/) demo to test drive the *IndexedDB manager* in Microsoft Edge DevTools.</span></span>

<span data-ttu-id="88e15-145">若要删除为 Microsoft Edge 中的当前用户存储的所有 IndexedDB 数据，请使用"Microsoft Edge 设置 *"* 菜单：</span><span class="sxs-lookup"><span data-stu-id="88e15-145">To delete all the IndexedDB data stored for the current user in Microsoft Edge, use the Microsoft Edge *Settings* menu:</span></span>

<span data-ttu-id="88e15-146">**...** > **设置**  > **清除浏览数据**  > **Cookie 和保存的网站数据**</span><span class="sxs-lookup"><span data-stu-id="88e15-146">**...** > **Settings** > **Clear browsing data** > **Cookies and saved website data**</span></span>

<span data-ttu-id="88e15-147">调试器的资源选取器内的**IndexedDB** [\*\*](./debugger.md#resource-picker)文件夹显示页面加载的资源的来源列表。</span><span class="sxs-lookup"><span data-stu-id="88e15-147">The **IndexedDB** folder inside the Debugger's [*Resource picker*](./debugger.md#resource-picker) displays a list of origins from the resources loaded by the page.</span></span> <span data-ttu-id="88e15-148">任何 IndexedDB (IDB) 数据库都将在源及其对象存储下列出。</span><span class="sxs-lookup"><span data-stu-id="88e15-148">Any IndexedDB (IDB) databases will be listed under the origin, along with their object stores.</span></span> 

![DevTools IndexedDB 管理器](./media/storage_indexeddb.png)

### <span data-ttu-id="88e15-150">IndexedDB 工具栏</span><span class="sxs-lookup"><span data-stu-id="88e15-150">IndexedDB Toolbar</span></span>

<span data-ttu-id="88e15-151">从 *IndexedDB* 工具栏中，您可以：</span><span class="sxs-lookup"><span data-stu-id="88e15-151">From the *IndexedDB* toolbar you can:</span></span>

 - <span data-ttu-id="88e15-152">**刷新** () 以查看数据库的对象 `Ctrl+F5` 存储或索引中的当前条目。</span><span class="sxs-lookup"><span data-stu-id="88e15-152">**Refresh** (`Ctrl+F5`) to see the current entries in the object store or index of your database.</span></span> <span data-ttu-id="88e15-153">对数据库进行更改时，IndexedDB 管理器不会自动刷新。</span><span class="sxs-lookup"><span data-stu-id="88e15-153">The IndexedDB manager does not auto-refresh when changes are made to your database.</span></span>

### <span data-ttu-id="88e15-154">对象存储条目列表</span><span class="sxs-lookup"><span data-stu-id="88e15-154">Object store entries list</span></span>

<span data-ttu-id="88e15-155">在 *"对象存储"或\*\*"索引"* 表中，您可以：</span><span class="sxs-lookup"><span data-stu-id="88e15-155">From the *Object store* or *Index* table you can:</span></span>

 - <span data-ttu-id="88e15-156">**单击表中的** 任何列名称，检查键值对并排序。</span><span class="sxs-lookup"><span data-stu-id="88e15-156">**Inspect and sort** your key-value pairs by clicking on any column name in the table.</span></span>
 - <span data-ttu-id="88e15-157">**刷新** `Ctrl+F5` () </span><span class="sxs-lookup"><span data-stu-id="88e15-157">**Refresh** (`Ctrl+F5`)</span></span>
 - <span data-ttu-id="88e15-158">**删除 () ，** 以删除对象存储或 `Del` 索引中的选定条目。</span><span class="sxs-lookup"><span data-stu-id="88e15-158">**Delete item** (`Del`) to remove the selected entry in your object store or index.</span></span> <span data-ttu-id="88e15-159">还可以从右键单击上下文菜单选项"删除[](#context-menu)项目 *"中完成此操作*。</span><span class="sxs-lookup"><span data-stu-id="88e15-159">You can also do this from the right-click [context menu](#context-menu) option, *Delete item*.</span></span>
 - <span data-ttu-id="88e15-160">**复制所选** `Ctrl+C` () ，将所选项目复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="88e15-160">**Copy selected items** (`Ctrl+C`) to copy the selected item to your clipboard.</span></span> <span data-ttu-id="88e15-161">还可以从右键单击上下文菜单选项"复制[](#context-menu)所选项目 *"中完成此操作*。</span><span class="sxs-lookup"><span data-stu-id="88e15-161">You can also do this from the right-click [context menu](#context-menu) option, *Copy selected item*.</span></span>
 - <span data-ttu-id="88e15-162">**Select all** (`Ctrl+A`) to select all thentries in your object store or index.</span><span class="sxs-lookup"><span data-stu-id="88e15-162">**Select all** (`Ctrl+A`) to select all the entries in your object store or index.</span></span> <span data-ttu-id="88e15-163">还可以从右键单击上下文菜单选项"全[](#context-menu)选 *"中完成此操作*。</span><span class="sxs-lookup"><span data-stu-id="88e15-163">You can also do this from the right-click [context menu](#context-menu) option, *Select all*.</span></span>

<span data-ttu-id="88e15-164">对象存储*或索引*表的列\*\* 可排序：</span><span class="sxs-lookup"><span data-stu-id="88e15-164">The columns of the *Object store* or *Index* table are sortable:</span></span>

<span data-ttu-id="88e15-165">列</span><span class="sxs-lookup"><span data-stu-id="88e15-165">Column</span></span> | <span data-ttu-id="88e15-166">描述</span><span class="sxs-lookup"><span data-stu-id="88e15-166">Description</span></span>
:------------ | :-------------
<span data-ttu-id="88e15-167">密钥</span><span class="sxs-lookup"><span data-stu-id="88e15-167">Key</span></span> | <span data-ttu-id="88e15-168">键值对的名称与 (*对象* 存储) 主键对的名称相同;在索引上 (时，) 当前键的名称</span><span class="sxs-lookup"><span data-stu-id="88e15-168">Name of the key-value pair (same as *Primary Key*) when iterating over an object store; Name of the index key (cursor's current key) when iterating over an index</span></span>
<span data-ttu-id="88e15-169">主键</span><span class="sxs-lookup"><span data-stu-id="88e15-169">Primary Key</span></span> | <span data-ttu-id="88e15-170">键值对的名称，请参阅 *MDN (，* 详细了解 [IDB](https://developer.mozilla.org/docs/Web/API/IndexedDB_API/Using_IndexedDB#Structuring_the_database) 密钥) </span><span class="sxs-lookup"><span data-stu-id="88e15-170">Name of the key-value pair (see *MDN web docs* for more on IDB [keys](https://developer.mozilla.org/docs/Web/API/IndexedDB_API/Using_IndexedDB#Structuring_the_database))</span></span>
<span data-ttu-id="88e15-171">值</span><span class="sxs-lookup"><span data-stu-id="88e15-171">Value</span></span> | <span data-ttu-id="88e15-172">键值对的值</span><span class="sxs-lookup"><span data-stu-id="88e15-172">Value of the key-value pair</span></span>

<span data-ttu-id="88e15-173">查看 *MDN Web 文档，* 了解有关 [IndexedDB 概念和用法的更多内容](https://developer.mozilla.org/docs/Web/API/IndexedDB_API)。</span><span class="sxs-lookup"><span data-stu-id="88e15-173">Check out *MDN web docs* for more on [IndexedDB concepts and usage](https://developer.mozilla.org/docs/Web/API/IndexedDB_API).</span></span>

### <span data-ttu-id="88e15-174">上下文菜单</span><span class="sxs-lookup"><span data-stu-id="88e15-174">Context menu</span></span>

<span data-ttu-id="88e15-175">除了[*IndexedDB*](#indexeddb-toolbar)工具栏之外，还可以从右键单击"上下文"菜单和/或键盘快捷方式管理对象存储或\*\*\*\* 索引[中的数据](#shortcuts)。</span><span class="sxs-lookup"><span data-stu-id="88e15-175">In addition to the [*IndexedDB* toolbar](#indexeddb-toolbar), you can also manage your data in object stores or indices from the right-click **Context menu** and/or the keyboard [shortcuts](#shortcuts).</span></span>

### <span data-ttu-id="88e15-176">快捷方式</span><span class="sxs-lookup"><span data-stu-id="88e15-176">Shortcuts</span></span>

<span data-ttu-id="88e15-177">操作</span><span class="sxs-lookup"><span data-stu-id="88e15-177">Action</span></span> | <span data-ttu-id="88e15-178">快捷方式</span><span class="sxs-lookup"><span data-stu-id="88e15-178">Shortcut</span></span>
:------------ | :-------------
<span data-ttu-id="88e15-179">刷新</span><span class="sxs-lookup"><span data-stu-id="88e15-179">Refresh</span></span> | `Ctrl` + `F5`
<span data-ttu-id="88e15-180">删除键值对</span><span class="sxs-lookup"><span data-stu-id="88e15-180">Delete key-value pair</span></span> | `Del`
<span data-ttu-id="88e15-181">复制选定项目</span><span class="sxs-lookup"><span data-stu-id="88e15-181">Copy selected items</span></span> | `Ctrl` + `C`
<span data-ttu-id="88e15-182">全选</span><span class="sxs-lookup"><span data-stu-id="88e15-182">Select all</span></span> | `Ctrl` + `A`

## <span data-ttu-id="88e15-183">Cookie 管理器</span><span class="sxs-lookup"><span data-stu-id="88e15-183">Cookies manager</span></span>

<span data-ttu-id="88e15-184">使用 *Cookie 管理器* 检查和管理给定域的 Cookie。</span><span class="sxs-lookup"><span data-stu-id="88e15-184">Use the *Cookies manager* to inspect and manage the cookies for the given domain.</span></span> 

<span data-ttu-id="88e15-185">调试**器**的资源选取器内的 Cookie 文件夹[\*\*](./debugger.md#resource-picker)显示页面加载的资源的来源列表。</span><span class="sxs-lookup"><span data-stu-id="88e15-185">The **Cookies** folder inside the Debugger's [*Resource picker*](./debugger.md#resource-picker) displays a list of origins from the resources loaded by the page.</span></span> <span data-ttu-id="88e15-186">选择其中一个帧将打开一个表，该表代表[HTTP](https://developer.mozilla.org/docs/Web/HTTP/Cookies)标头或通过[Document.cookie 脚本设置的当前 Cookie。](https://developer.mozilla.org/docs/Web/API/Document/cookie)</span><span class="sxs-lookup"><span data-stu-id="88e15-186">Selecting one of these frames opens up a table representing the current cookies set by either [HTTP](https://developer.mozilla.org/docs/Web/HTTP/Cookies) header or via script with [Document.cookie](https://developer.mozilla.org/docs/Web/API/Document/cookie).</span></span>

![DevTools Cookies 管理器](./media/storage_cookies.png)

<span data-ttu-id="88e15-188">在 *"Cookie"* 选项卡工具栏中，您可以：</span><span class="sxs-lookup"><span data-stu-id="88e15-188">From the *Cookies* tab toolbar you can:</span></span>

 - <span data-ttu-id="88e15-189">**刷新** () Cookie `Ctrl+F5` [列表](#cookies-list) ，以查看给定域的当前 Cookie 集。</span><span class="sxs-lookup"><span data-stu-id="88e15-189">**Refresh** (`Ctrl+F5`) the [Cookies list](#cookies-list) to see the current set of cookies for the given domain.</span></span> <span data-ttu-id="88e15-190"> (列表不自动刷新.) </span><span class="sxs-lookup"><span data-stu-id="88e15-190">(The list does not auto-refresh.)</span></span>
 - <span data-ttu-id="88e15-191">**删除当前** ()  (的所有 cookie `Ctrl+Shift+Del` 和) 的永久 Cookie。</span><span class="sxs-lookup"><span data-stu-id="88e15-191">**Delete all cookies** (`Ctrl+Shift+Del`) (session and permanent) for the path of the current page.</span></span>
 - <span data-ttu-id="88e15-192">**删除当前页面** `Ctrl+Del` () 的所有会话 Cookie。</span><span class="sxs-lookup"><span data-stu-id="88e15-192">**Delete all session cookies** (`Ctrl+Del`) for the path of the current page.</span></span>

<span data-ttu-id="88e15-193">若要完全清除*Cookie 列表*，您可能需要从网络面板\*\*\*\* 工具栏中清除[**域的所有**](./network.md#toolbar)Cookie。</span><span class="sxs-lookup"><span data-stu-id="88e15-193">To completely clear your *Cookies list*, you might need to **Clear all cookies for the domain** from the [**Network**](./network.md#toolbar) panel toolbar.</span></span>

### <span data-ttu-id="88e15-194">Cookie 列表</span><span class="sxs-lookup"><span data-stu-id="88e15-194">Cookies list</span></span>

<span data-ttu-id="88e15-195">从 *Cookie 列表* 表中，您可以：</span><span class="sxs-lookup"><span data-stu-id="88e15-195">From the *Cookies list* table you can:</span></span>

 - <span data-ttu-id="88e15-196">**通过单击** 表中的任何列名称来检查 Cookie 并排序。</span><span class="sxs-lookup"><span data-stu-id="88e15-196">**Inspect and sort** your cookies by clicking on any column name in the table.</span></span>
 - <span data-ttu-id="88e15-197">\**在\*\*\*单元格*中*单击*，编辑现有 Cookie 的名称和值。</span><span class="sxs-lookup"><span data-stu-id="88e15-197">**Edit** the *Name* and *Value* of an existing cookie by clicking in the cell.</span></span>
 - <span data-ttu-id="88e15-198">**从** () 菜单选项"删除 Cookie"中删除 `Del` Cookie。 [](#context-menu) \*\*</span><span class="sxs-lookup"><span data-stu-id="88e15-198">**Delete** (`Del`) a cookie from the right-click [context menu](#context-menu) option, *Delete cookie*.</span></span>
 - <span data-ttu-id="88e15-199">**单击** 表底部的空行，为给定的 *域/路径* 添加新的会话 Cookie。</span><span class="sxs-lookup"><span data-stu-id="88e15-199">**Add** a new session cookie for the given *Domain/Path* by clicking on the empty row at the bottom of the table.</span></span> <span data-ttu-id="88e15-200">这仅适用于会话 Cookie;具有特定 (日期的永久性) 必须使用传统方法进行设置。</span><span class="sxs-lookup"><span data-stu-id="88e15-200">This only works for session cookies; permanent cookies (with specific expiry dates) must be set with traditional methods.</span></span> <span data-ttu-id="88e15-201">域*和\*\*路径*值根据页面的位置自动填充。</span><span class="sxs-lookup"><span data-stu-id="88e15-201">The *Domain* and *Path* values are auto-filled according to the location of the page.</span></span>

<span data-ttu-id="88e15-202">Cookie 列表的 *列可* 排序：</span><span class="sxs-lookup"><span data-stu-id="88e15-202">The columns of the *Cookies list* are sortable:</span></span>

<span data-ttu-id="88e15-203">列</span><span class="sxs-lookup"><span data-stu-id="88e15-203">Column</span></span> | <span data-ttu-id="88e15-204">描述</span><span class="sxs-lookup"><span data-stu-id="88e15-204">Description</span></span>
:------------ | :-------------
<span data-ttu-id="88e15-205">名称</span><span class="sxs-lookup"><span data-stu-id="88e15-205">Name</span></span> | <span data-ttu-id="88e15-206">Cookie 的名称</span><span class="sxs-lookup"><span data-stu-id="88e15-206">Name of the cookie</span></span>
<span data-ttu-id="88e15-207">值</span><span class="sxs-lookup"><span data-stu-id="88e15-207">Value</span></span> | <span data-ttu-id="88e15-208">Cookie 的值</span><span class="sxs-lookup"><span data-stu-id="88e15-208">Value of the cookie</span></span>
<span data-ttu-id="88e15-209">域</span><span class="sxs-lookup"><span data-stu-id="88e15-209">Domain</span></span> | <span data-ttu-id="88e15-210">Cookie 主机名 (可能为空) </span><span class="sxs-lookup"><span data-stu-id="88e15-210">Host name of the cookie (may be empty)</span></span>
<span data-ttu-id="88e15-211">路径</span><span class="sxs-lookup"><span data-stu-id="88e15-211">Path</span></span> | <span data-ttu-id="88e15-212">Cookie 网站的 URL (可能为空) </span><span class="sxs-lookup"><span data-stu-id="88e15-212">URL path for the cookie (may be empty)</span></span>
<span data-ttu-id="88e15-213">到期</span><span class="sxs-lookup"><span data-stu-id="88e15-213">Expires</span></span> | <span data-ttu-id="88e15-214">作为 HTTP 日期时间戳的 Cookie 的最大生存期。</span><span class="sxs-lookup"><span data-stu-id="88e15-214">Maximum lifetime of the cookie as an HTTP-date timestamp.</span></span> <span data-ttu-id="88e15-215">如果未 `Expires` 设置 `Max-Age` 或已设置，则条目将被视为 *会话* Cookie。</span><span class="sxs-lookup"><span data-stu-id="88e15-215">If no `Expires` or `Max-Age` was set, the entry is considered a *Session* cookie.</span></span>
<span data-ttu-id="88e15-216">仅 HTTP</span><span class="sxs-lookup"><span data-stu-id="88e15-216">HTTP only</span></span> | <span data-ttu-id="88e15-217">指示 Cookie 是否设置有指令，指示无法通过 `HttpOnly` JavaScript 访问</span><span class="sxs-lookup"><span data-stu-id="88e15-217">Indicates if the cookie was set with `HttpOnly` directive, indicating that it is inaccessible from JavaScript</span></span>
<span data-ttu-id="88e15-218">安全</span><span class="sxs-lookup"><span data-stu-id="88e15-218">Secure</span></span> | <span data-ttu-id="88e15-219">指示 Cookie 是否使用指令进行设置，指示它仅从使用 SSL 和 HTTPS 协议的请求 `Secure` 发送到服务器。</span><span class="sxs-lookup"><span data-stu-id="88e15-219">Indicates if the cookie was set with the `Secure` directive, indicating it will only be sent to the server from a request using SSL and the HTTPS protocol.</span></span>

<span data-ttu-id="88e15-220">有关 Cookie 属性的更多详细信息，请参阅**MDN Web 文档**[集](https://developer.mozilla.org/docs/Web/HTTP/Headers/Set-Cookie)Cookie 参考。</span><span class="sxs-lookup"><span data-stu-id="88e15-220">See the **MDN web docs** [Set-Cookie](https://developer.mozilla.org/docs/Web/HTTP/Headers/Set-Cookie) reference for further details on cookie properties.</span></span>

### <span data-ttu-id="88e15-221">上下文菜单</span><span class="sxs-lookup"><span data-stu-id="88e15-221">Context menu</span></span>

<span data-ttu-id="88e15-222">除了 *"Cookie"* 选项卡[工具栏](#cookies-manager)之外，您还可以从右键单击的"上下文"菜单和/或\*\*\*\* 键盘快捷方式管理[Cookie。](#shortcuts)</span><span class="sxs-lookup"><span data-stu-id="88e15-222">In addition to the *Cookies* tab [toolbar](#cookies-manager), you can also manage your cookies from the right-click **Context menu** and/or the keyboard [shortcuts](#shortcuts).</span></span>

### <span data-ttu-id="88e15-223">快捷方式</span><span class="sxs-lookup"><span data-stu-id="88e15-223">Shortcuts</span></span>

| <span data-ttu-id="88e15-224">操作</span><span class="sxs-lookup"><span data-stu-id="88e15-224">Action</span></span>                     | <span data-ttu-id="88e15-225">快捷方式</span><span class="sxs-lookup"><span data-stu-id="88e15-225">Shortcut</span></span>                 |
|:---------------------------|:-------------------------|
| <span data-ttu-id="88e15-226">刷新</span><span class="sxs-lookup"><span data-stu-id="88e15-226">Refresh</span></span>                    | `Ctrl` + `F5`            |
| <span data-ttu-id="88e15-227">删除 Cookie</span><span class="sxs-lookup"><span data-stu-id="88e15-227">Delete cookie</span></span>              | `Del`                    |
| <span data-ttu-id="88e15-228">删除所有 Cookie</span><span class="sxs-lookup"><span data-stu-id="88e15-228">Delete all cookies</span></span>         | `Ctrl` + `Shift` + `Del` |
| <span data-ttu-id="88e15-229">删除所有会话 Cookie</span><span class="sxs-lookup"><span data-stu-id="88e15-229">Delete all session cookies</span></span> | `Ctrl` + `Del`           |
| <span data-ttu-id="88e15-230">复制选定项目</span><span class="sxs-lookup"><span data-stu-id="88e15-230">Copy selected items</span></span>        | `Ctrl` + `C`             |
| <span data-ttu-id="88e15-231">全选</span><span class="sxs-lookup"><span data-stu-id="88e15-231">Select all</span></span>                 | `Ctrl` + `A`             |

### <span data-ttu-id="88e15-232">缓存管理器</span><span class="sxs-lookup"><span data-stu-id="88e15-232">Cache manager</span></span>

<span data-ttu-id="88e15-233">单击特定缓存条目将打开服务工作线程缓存管理器，\*\*\*\* 您可以在其中检查和选择删除请求和响应 (/值对中的缓存) ： \*\* \*\*</span><span class="sxs-lookup"><span data-stu-id="88e15-233">Clicking on a specific cache entry will open up the service worker **Cache** manager, where you can inspect and optionally delete cache entries (*Request* and *Response* key/value pairs):</span></span>

![缓存管理器](./media/storage_cache.png)

### <span data-ttu-id="88e15-235">快捷方式</span><span class="sxs-lookup"><span data-stu-id="88e15-235">Shortcuts</span></span>

#### <span data-ttu-id="88e15-236">缓存管理器</span><span class="sxs-lookup"><span data-stu-id="88e15-236">Cache manager</span></span>

| <span data-ttu-id="88e15-237">操作</span><span class="sxs-lookup"><span data-stu-id="88e15-237">Action</span></span>              | <span data-ttu-id="88e15-238">快捷方式</span><span class="sxs-lookup"><span data-stu-id="88e15-238">Shortcut</span></span>      |
|:--------------------|:--------------|
| <span data-ttu-id="88e15-239">刷新</span><span class="sxs-lookup"><span data-stu-id="88e15-239">Refresh</span></span>             | `Ctrl` + `F5` |
| <span data-ttu-id="88e15-240">删除项</span><span class="sxs-lookup"><span data-stu-id="88e15-240">Delete item</span></span>         | `Del`         |
| <span data-ttu-id="88e15-241">复制选定项目</span><span class="sxs-lookup"><span data-stu-id="88e15-241">Copy selected items</span></span> | `Ctrl` + `C`  |
| <span data-ttu-id="88e15-242">全选</span><span class="sxs-lookup"><span data-stu-id="88e15-242">Select all</span></span>          | `Ctrl` + `A`  |
