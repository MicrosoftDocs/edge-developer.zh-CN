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
# <span data-ttu-id="c38f1-104">存储</span><span class="sxs-lookup"><span data-stu-id="c38f1-104">Storage</span></span>

<span data-ttu-id="c38f1-105">使用 **存储** 面板检查和管理各种本地缓存的数据，包括：</span><span class="sxs-lookup"><span data-stu-id="c38f1-105">Use the **Storage** panel to inspect and manage various locally cached data, including:</span></span>

 - <span data-ttu-id="c38f1-106">[Web 存储](#local-and-session-storage-managers) (*本地* 和 *会话* 存储) 键/值对</span><span class="sxs-lookup"><span data-stu-id="c38f1-106">[Web storage](#local-and-session-storage-managers) (*Local* and *Session* storage) key/values pairs</span></span>
 - <span data-ttu-id="c38f1-107">已[编制索引的数据库](#indexeddb-manager)结构化数据</span><span class="sxs-lookup"><span data-stu-id="c38f1-107">[Indexed DB](#indexeddb-manager) structured data</span></span>
 - <span data-ttu-id="c38f1-108">域的[cookie](#cookies-list)</span><span class="sxs-lookup"><span data-stu-id="c38f1-108">[Cookies](#cookies-list) for the domain</span></span>
 - <span data-ttu-id="c38f1-109">用于服务工作人员调试的[缓存](#cache-manager) (请求/响应对) </span><span class="sxs-lookup"><span data-stu-id="c38f1-109">[Cache](#cache-manager) (request/response pairs) for service worker debugging</span></span>

<span data-ttu-id="c38f1-110">展开这些类别中的任何类别，然后单击子条目以打开其 "资源管理器" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="c38f1-110">Expand any of those categories and click on a child entry to open its resource manager tab.</span></span>

## <span data-ttu-id="c38f1-111">本地和会话存储管理员</span><span class="sxs-lookup"><span data-stu-id="c38f1-111">Local and Session storage managers</span></span>

<span data-ttu-id="c38f1-112">使用 *本地存储管理器* 和 *会话存储管理器* 检查和管理页面的 web 存储。</span><span class="sxs-lookup"><span data-stu-id="c38f1-112">Use the *Local Storage manager* and *Session Storage manager* to inspect and manage the web storage for  your page.</span></span> 

<span data-ttu-id="c38f1-113">存储面板的[*资源选取器*](./debugger.md#resource-picker)中的 "**本地存储**" 和 "**会话存储**" 文件夹显示页面的来源列表。</span><span class="sxs-lookup"><span data-stu-id="c38f1-113">The **Local Storage** and **Session Storage** folders inside the Storage panel's [*Resource picker*](./debugger.md#resource-picker) display a list of origins for the page.</span></span> <span data-ttu-id="c38f1-114">选择其中一个框架可打开通过 [localStorage](https://developer.mozilla.org/docs/Web/API/Window/localStorage) 或 [sessionStorage](https://developer.mozilla.org/docs/Web/API/Window/sessionStorage)设置的当前键/值对的可编辑表，分别 (和/或直接从 DevTools [存储列表](#storage-list)) 设置。</span><span class="sxs-lookup"><span data-stu-id="c38f1-114">Selecting one of these frames opens up an editable table of the current key/value pairs set via [Window.localStorage](https://developer.mozilla.org/docs/Web/API/Window/localStorage) or [Window.sessionStorage](https://developer.mozilla.org/docs/Web/API/Window/sessionStorage), respectively (and/or set directly from the  DevTools [Storage list](#storage-list)).</span></span>

![DevTools Cookies 管理器](./media/storage_web_storage.png)

<span data-ttu-id="c38f1-116">从 " *本地存储* " 和 " *会话存储* " 选项卡，您可以：</span><span class="sxs-lookup"><span data-stu-id="c38f1-116">From the *Local Storage* and *Session Storage* tabs you can:</span></span>

 - <span data-ttu-id="c38f1-117">**刷新** (`Ctrl+F5`) [存储列表](#cookies-list) ，以查看给定域的当前键/值对集。</span><span class="sxs-lookup"><span data-stu-id="c38f1-117">**Refresh** (`Ctrl+F5`) the [storage list](#cookies-list) to see the current set of key/values pairs for the given domain.</span></span> <span data-ttu-id="c38f1-118"> (列表不会在脚本更新时自动刷新。 ) </span><span class="sxs-lookup"><span data-stu-id="c38f1-118">(The list does not auto-refresh upon script updates.)</span></span>
 - <span data-ttu-id="c38f1-119">模拟达到 Microsoft Edge web 存储**的存储限制**。</span><span class="sxs-lookup"><span data-stu-id="c38f1-119">**Simulate reaching the storage limit** for Microsoft Edge web storage.</span></span> <span data-ttu-id="c38f1-120">每个域和子域都有其自己的存储区域，但有一个组合的限制：</span><span class="sxs-lookup"><span data-stu-id="c38f1-120">Each domain and subdomain has its own storage area, however there is a combined limit:</span></span>
    - <span data-ttu-id="c38f1-121">**子域：** 最多 5 mb 的空间</span><span class="sxs-lookup"><span data-stu-id="c38f1-121">**Subdomains:** up to 5 MBs of space</span></span>
    - <span data-ttu-id="c38f1-122">**域：** 最多 10 mb 的空间</span><span class="sxs-lookup"><span data-stu-id="c38f1-122">**Domains:** up to 10 MBs of space</span></span>
    - <span data-ttu-id="c38f1-123">**所有域的总计：** 最高为 50 mb 的空间</span><span class="sxs-lookup"><span data-stu-id="c38f1-123">**Total for all domains:** up to 50 MBs of space</span></span>

   <span data-ttu-id="c38f1-124">一旦最后一个浏览器选项卡被关闭，会话存储就会被清除。</span><span class="sxs-lookup"><span data-stu-id="c38f1-124">Session storage is cleared as soon as the last browser tab referencing its origin is closed.</span></span> <span data-ttu-id="c38f1-125">本地存储项无限期地保留，直到通过页面以编程方式或由用户手动清除为止：</span><span class="sxs-lookup"><span data-stu-id="c38f1-125">Local storage entries persist indefinitely until cleared programmatically by the page or manually by the user:</span></span>

   <span data-ttu-id="c38f1-126">**设置**  > **清除浏览数据**  > **Cookie 和保存的网站数据**</span><span class="sxs-lookup"><span data-stu-id="c38f1-126">**Settings** > **Clear browsing data** > **Cookies and saved website data**</span></span>

![从 Microsoft Edge 设置面板中清除浏览数据](./media/settings_clear_browsing_data.png)

### <span data-ttu-id="c38f1-128">存储列表</span><span class="sxs-lookup"><span data-stu-id="c38f1-128">Storage list</span></span>

<span data-ttu-id="c38f1-129">从 *存储列表* 表中，您可以：</span><span class="sxs-lookup"><span data-stu-id="c38f1-129">From the *Storage list* table you can:</span></span>

 - <span data-ttu-id="c38f1-130">通过单击表中的任意一列名称来**检查和排序**键/值对。</span><span class="sxs-lookup"><span data-stu-id="c38f1-130">**Inspect and sort** your key/value pairs by clicking on either column name in the table.</span></span>
 - <span data-ttu-id="c38f1-131">通过在单元格中单击来**编辑**现有条目的*键*和*值*。</span><span class="sxs-lookup"><span data-stu-id="c38f1-131">**Edit** the *Key* and *Value* of an existing entry by clicking in the cell.</span></span>
 - <span data-ttu-id="c38f1-132">**删除** (`Del` 从右键单击上下文菜单选项中) 条目，然后单击 " *删除项目*"。</span><span class="sxs-lookup"><span data-stu-id="c38f1-132">**Delete** (`Del`) an entry from the right-click context menu option, *Delete item*.</span></span>
 - <span data-ttu-id="c38f1-133">通过单击表底部的空行**添加**新的键/值对。</span><span class="sxs-lookup"><span data-stu-id="c38f1-133">**Add** a new key/value pair by clicking on the empty row at the bottom of the table.</span></span>


### <span data-ttu-id="c38f1-134">快捷方式</span><span class="sxs-lookup"><span data-stu-id="c38f1-134">Shortcuts</span></span>

| <span data-ttu-id="c38f1-135">操作</span><span class="sxs-lookup"><span data-stu-id="c38f1-135">Action</span></span>              | <span data-ttu-id="c38f1-136">快捷方式</span><span class="sxs-lookup"><span data-stu-id="c38f1-136">Shortcut</span></span>      |
|:--------------------|:--------------|
| <span data-ttu-id="c38f1-137">刷新</span><span class="sxs-lookup"><span data-stu-id="c38f1-137">Refresh</span></span>             | `Ctrl` + `F5` |
| <span data-ttu-id="c38f1-138">删除项</span><span class="sxs-lookup"><span data-stu-id="c38f1-138">Delete item</span></span>         | `Del`         |
| <span data-ttu-id="c38f1-139">复制所选项目</span><span class="sxs-lookup"><span data-stu-id="c38f1-139">Copy selected items</span></span> | `Ctrl` + `C`  |
| <span data-ttu-id="c38f1-140">全选</span><span class="sxs-lookup"><span data-stu-id="c38f1-140">Select all</span></span>          | `Ctrl` + `A`  |


## <span data-ttu-id="c38f1-141">IndexedDB 管理器</span><span class="sxs-lookup"><span data-stu-id="c38f1-141">IndexedDB manager</span></span>

<span data-ttu-id="c38f1-142">使用 " **IndexedDB** " 选项卡检查和管理在客户端计算机上本地存储的结构化数据。</span><span class="sxs-lookup"><span data-stu-id="c38f1-142">Use the **IndexedDB** tab to inspect and manage the structured data stored locally on a client machine.</span></span> <span data-ttu-id="c38f1-143">具体说来，你可以检查/排序和刷新你的对象存储和索引，还可以删除单个键值条目。</span><span class="sxs-lookup"><span data-stu-id="c38f1-143">Specifically, you can inspect/sort and refresh your object stores and indices, and also delete individual key-value entries.</span></span>

> [!TIP]
> <span data-ttu-id="c38f1-144">你可以使用我们的 [音频混合器](https://developer.microsoft.com/microsoft-edge/testdrive/demos/audiomixer/) 演示在 Microsoft Edge DevTools 中测试驱动器 *IndexedDB 管理器* 。</span><span class="sxs-lookup"><span data-stu-id="c38f1-144">You can use our [Audio Mixer](https://developer.microsoft.com/microsoft-edge/testdrive/demos/audiomixer/) demo to test drive the *IndexedDB manager* in Microsoft Edge DevTools.</span></span>

<span data-ttu-id="c38f1-145">若要删除在 Microsoft Edge 中为当前用户存储的所有 IndexedDB 数据，请使用 Microsoft Edge *设置* 菜单：</span><span class="sxs-lookup"><span data-stu-id="c38f1-145">To delete all the IndexedDB data stored for the current user in Microsoft Edge, use the Microsoft Edge *Settings* menu:</span></span>

<span data-ttu-id="c38f1-146">**...** > **设置**  > **清除浏览数据**  > **Cookie 和保存的网站数据**</span><span class="sxs-lookup"><span data-stu-id="c38f1-146">**...** > **Settings** > **Clear browsing data** > **Cookies and saved website data**</span></span>

<span data-ttu-id="c38f1-147">调试器的[*资源选取器*](./debugger.md#resource-picker)中的**IndexedDB**文件夹显示由页面加载的资源的来源列表。</span><span class="sxs-lookup"><span data-stu-id="c38f1-147">The **IndexedDB** folder inside the Debugger's [*Resource picker*](./debugger.md#resource-picker) displays a list of origins from the resources loaded by the page.</span></span> <span data-ttu-id="c38f1-148">任何 IndexedDB (.IDB) 数据库将在原始位置列出，以及其对象存储。</span><span class="sxs-lookup"><span data-stu-id="c38f1-148">Any IndexedDB (IDB) databases will be listed under the origin, along with their object stores.</span></span> 

![DevTools IndexedDB manager](./media/storage_indexeddb.png)

### <span data-ttu-id="c38f1-150">IndexedDB 工具栏</span><span class="sxs-lookup"><span data-stu-id="c38f1-150">IndexedDB Toolbar</span></span>

<span data-ttu-id="c38f1-151">通过 *IndexedDB* 工具栏，您可以：</span><span class="sxs-lookup"><span data-stu-id="c38f1-151">From the *IndexedDB* toolbar you can:</span></span>

 - <span data-ttu-id="c38f1-152">**刷新** (`Ctrl+F5`) 可查看数据库的对象存储或索引中的当前条目。</span><span class="sxs-lookup"><span data-stu-id="c38f1-152">**Refresh** (`Ctrl+F5`) to see the current entries in the object store or index of your database.</span></span> <span data-ttu-id="c38f1-153">在对数据库进行更改后，IndexedDB 管理器不会自动刷新。</span><span class="sxs-lookup"><span data-stu-id="c38f1-153">The IndexedDB manager does not auto-refresh when changes are made to your database.</span></span>

### <span data-ttu-id="c38f1-154">对象存储项列表</span><span class="sxs-lookup"><span data-stu-id="c38f1-154">Object store entries list</span></span>

<span data-ttu-id="c38f1-155">从 " *对象存储* " 或 " *索引* " 表中，您可以：</span><span class="sxs-lookup"><span data-stu-id="c38f1-155">From the *Object store* or *Index* table you can:</span></span>

 - <span data-ttu-id="c38f1-156">通过单击表中的任意列名称来**检查和排序**键/值对。</span><span class="sxs-lookup"><span data-stu-id="c38f1-156">**Inspect and sort** your key-value pairs by clicking on any column name in the table.</span></span>
 - <span data-ttu-id="c38f1-157">**刷新** (`Ctrl+F5`) </span><span class="sxs-lookup"><span data-stu-id="c38f1-157">**Refresh** (`Ctrl+F5`)</span></span>
 - <span data-ttu-id="c38f1-158">**删除项目** (`Del`) 删除你的对象存储或索引中所选的条目。</span><span class="sxs-lookup"><span data-stu-id="c38f1-158">**Delete item** (`Del`) to remove the selected entry in your object store or index.</span></span> <span data-ttu-id="c38f1-159">您也可以从右键单击 [上下文菜单](#context-menu) 选项中执行此操作，然后单击 " *删除项目*"。</span><span class="sxs-lookup"><span data-stu-id="c38f1-159">You can also do this from the right-click [context menu](#context-menu) option, *Delete item*.</span></span>
 - <span data-ttu-id="c38f1-160">**将所选项目复制** (`Ctrl+C`) 将所选项目复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="c38f1-160">**Copy selected items** (`Ctrl+C`) to copy the selected item to your clipboard.</span></span> <span data-ttu-id="c38f1-161">您也可以通过右键单击 [上下文菜单](#context-menu) 选项执行此操作， *复制所选项目*。</span><span class="sxs-lookup"><span data-stu-id="c38f1-161">You can also do this from the right-click [context menu](#context-menu) option, *Copy selected item*.</span></span>
 - <span data-ttu-id="c38f1-162">**选择 "所有** (`Ctrl+A` ") 选择您的对象存储或索引中的所有条目。</span><span class="sxs-lookup"><span data-stu-id="c38f1-162">**Select all** (`Ctrl+A`) to select all the entries in your object store or index.</span></span> <span data-ttu-id="c38f1-163">您也可以通过右键单击 [上下文菜单](#context-menu) 选项执行此操作，然后 *选择 "全部*"。</span><span class="sxs-lookup"><span data-stu-id="c38f1-163">You can also do this from the right-click [context menu](#context-menu) option, *Select all*.</span></span>

<span data-ttu-id="c38f1-164">可对 *对象存储* 或 *索引* 表的列进行排序：</span><span class="sxs-lookup"><span data-stu-id="c38f1-164">The columns of the *Object store* or *Index* table are sortable:</span></span>

<span data-ttu-id="c38f1-165">列</span><span class="sxs-lookup"><span data-stu-id="c38f1-165">Column</span></span> | <span data-ttu-id="c38f1-166">描述</span><span class="sxs-lookup"><span data-stu-id="c38f1-166">Description</span></span>
:------------ | :-------------
<span data-ttu-id="c38f1-167">密钥</span><span class="sxs-lookup"><span data-stu-id="c38f1-167">Key</span></span> | <span data-ttu-id="c38f1-168">在循环访问对象存储时，键值对的名称 (与 *主键*) 相同;在循环访问索引时 (游标的当前键) 的索引键的名称</span><span class="sxs-lookup"><span data-stu-id="c38f1-168">Name of the key-value pair (same as *Primary Key*) when iterating over an object store; Name of the index key (cursor's current key) when iterating over an index</span></span>
<span data-ttu-id="c38f1-169">主键</span><span class="sxs-lookup"><span data-stu-id="c38f1-169">Primary Key</span></span> | <span data-ttu-id="c38f1-170">键/值对的名称 (查看 *MDN web 文档* 以了解有关 .idb [键](https://developer.mozilla.org/docs/Web/API/IndexedDB_API/Using_IndexedDB#Structuring_the_database) 的详细信息) </span><span class="sxs-lookup"><span data-stu-id="c38f1-170">Name of the key-value pair (see *MDN web docs* for more on IDB [keys](https://developer.mozilla.org/docs/Web/API/IndexedDB_API/Using_IndexedDB#Structuring_the_database))</span></span>
<span data-ttu-id="c38f1-171">Value</span><span class="sxs-lookup"><span data-stu-id="c38f1-171">Value</span></span> | <span data-ttu-id="c38f1-172">键/值对的值</span><span class="sxs-lookup"><span data-stu-id="c38f1-172">Value of the key-value pair</span></span>

<span data-ttu-id="c38f1-173">有关[IndexedDB 概念和用法](https://developer.mozilla.org/docs/Web/API/IndexedDB_API)的详细信息，请查看*MDN web 文档*。</span><span class="sxs-lookup"><span data-stu-id="c38f1-173">Check out *MDN web docs* for more on [IndexedDB concepts and usage](https://developer.mozilla.org/docs/Web/API/IndexedDB_API).</span></span>

### <span data-ttu-id="c38f1-174">上下文菜单</span><span class="sxs-lookup"><span data-stu-id="c38f1-174">Context menu</span></span>

<span data-ttu-id="c38f1-175">除了[ *IndexedDB*工具栏](#indexeddb-toolbar)，您还可以通过右键单击**上下文菜单**和/或键盘[快捷方式](#shortcuts)，在对象存储或索引中管理数据。</span><span class="sxs-lookup"><span data-stu-id="c38f1-175">In addition to the [*IndexedDB* toolbar](#indexeddb-toolbar), you can also manage your data in object stores or indices from the right-click **Context menu** and/or the keyboard [shortcuts](#shortcuts).</span></span>

### <span data-ttu-id="c38f1-176">快捷方式</span><span class="sxs-lookup"><span data-stu-id="c38f1-176">Shortcuts</span></span>

<span data-ttu-id="c38f1-177">操作</span><span class="sxs-lookup"><span data-stu-id="c38f1-177">Action</span></span> | <span data-ttu-id="c38f1-178">快捷方式</span><span class="sxs-lookup"><span data-stu-id="c38f1-178">Shortcut</span></span>
:------------ | :-------------
<span data-ttu-id="c38f1-179">刷新</span><span class="sxs-lookup"><span data-stu-id="c38f1-179">Refresh</span></span> | `Ctrl` + `F5`
<span data-ttu-id="c38f1-180">删除键值对</span><span class="sxs-lookup"><span data-stu-id="c38f1-180">Delete key-value pair</span></span> | `Del`
<span data-ttu-id="c38f1-181">复制所选项目</span><span class="sxs-lookup"><span data-stu-id="c38f1-181">Copy selected items</span></span> | `Ctrl` + `C`
<span data-ttu-id="c38f1-182">全选</span><span class="sxs-lookup"><span data-stu-id="c38f1-182">Select all</span></span> | `Ctrl` + `A`

## <span data-ttu-id="c38f1-183">Cookies 管理器</span><span class="sxs-lookup"><span data-stu-id="c38f1-183">Cookies manager</span></span>

<span data-ttu-id="c38f1-184">使用 *cookie 管理器* 检查和管理给定域的 cookie。</span><span class="sxs-lookup"><span data-stu-id="c38f1-184">Use the *Cookies manager* to inspect and manage the cookies for the given domain.</span></span> 

<span data-ttu-id="c38f1-185">调试器的[*资源选取器*](./debugger.md#resource-picker)中的**Cookies**文件夹显示由页面加载的资源的来源列表。</span><span class="sxs-lookup"><span data-stu-id="c38f1-185">The **Cookies** folder inside the Debugger's [*Resource picker*](./debugger.md#resource-picker) displays a list of origins from the resources loaded by the page.</span></span> <span data-ttu-id="c38f1-186">选择其中一个帧会打开一个表，其中包含由 [HTTP](https://developer.mozilla.org/docs/Web/HTTP/Cookies) 标头设置的当前 cookie 或通过带有 [Document cookie](https://developer.mozilla.org/docs/Web/API/Document/cookie)的脚本设置的当前 cookie。</span><span class="sxs-lookup"><span data-stu-id="c38f1-186">Selecting one of these frames opens up a table representing the current cookies set by either [HTTP](https://developer.mozilla.org/docs/Web/HTTP/Cookies) header or via script with [Document.cookie](https://developer.mozilla.org/docs/Web/API/Document/cookie).</span></span>

![DevTools Cookies 管理器](./media/storage_cookies.png)

<span data-ttu-id="c38f1-188">通过 " *Cookies* " 选项卡工具栏，您可以：</span><span class="sxs-lookup"><span data-stu-id="c38f1-188">From the *Cookies* tab toolbar you can:</span></span>

 - <span data-ttu-id="c38f1-189">**刷新** (`Ctrl+F5`) [cookie 列表](#cookies-list) ，以查看给定域的当前 cookie 集。</span><span class="sxs-lookup"><span data-stu-id="c38f1-189">**Refresh** (`Ctrl+F5`) the [Cookies list](#cookies-list) to see the current set of cookies for the given domain.</span></span> <span data-ttu-id="c38f1-190"> (列表不会自动刷新。 ) </span><span class="sxs-lookup"><span data-stu-id="c38f1-190">(The list does not auto-refresh.)</span></span>
 - <span data-ttu-id="c38f1-191">**删除** `Ctrl+Shift+Del` 当前页面路径的所有 cookie ()  (会话和永久) 。</span><span class="sxs-lookup"><span data-stu-id="c38f1-191">**Delete all cookies** (`Ctrl+Shift+Del`) (session and permanent) for the path of the current page.</span></span>
 - <span data-ttu-id="c38f1-192">**删除** `Ctrl+Del` 当前页面路径 () 的所有会话 cookie。</span><span class="sxs-lookup"><span data-stu-id="c38f1-192">**Delete all session cookies** (`Ctrl+Del`) for the path of the current page.</span></span>

<span data-ttu-id="c38f1-193">若要彻底清除您的*cookie 列表*，您可能需要从 "[**网络**](./network.md#toolbar)" 面板工具栏中**清除域的所有 cookie** 。</span><span class="sxs-lookup"><span data-stu-id="c38f1-193">To completely clear your *Cookies list*, you might need to **Clear all cookies for the domain** from the [**Network**](./network.md#toolbar) panel toolbar.</span></span>

### <span data-ttu-id="c38f1-194">Cookie 列表</span><span class="sxs-lookup"><span data-stu-id="c38f1-194">Cookies list</span></span>

<span data-ttu-id="c38f1-195">通过 *cookie 列表* 表，您可以：</span><span class="sxs-lookup"><span data-stu-id="c38f1-195">From the *Cookies list* table you can:</span></span>

 - <span data-ttu-id="c38f1-196">通过单击表中的任意列名称，对 cookie**进行检查和排序**。</span><span class="sxs-lookup"><span data-stu-id="c38f1-196">**Inspect and sort** your cookies by clicking on any column name in the table.</span></span>
 - <span data-ttu-id="c38f1-197">通过在单元格中单击来**编辑**现有 Cookie 的*名称*和*值*。</span><span class="sxs-lookup"><span data-stu-id="c38f1-197">**Edit** the *Name* and *Value* of an existing cookie by clicking in the cell.</span></span>
 - <span data-ttu-id="c38f1-198">**Delete** `Del` 从右键单击[上下文菜单](#context-menu)选项中删除 () Cookie，然后单击 "*删除 cookie*"。</span><span class="sxs-lookup"><span data-stu-id="c38f1-198">**Delete** (`Del`) a cookie from the right-click [context menu](#context-menu) option, *Delete cookie*.</span></span>
 - <span data-ttu-id="c38f1-199">通过单击表底部的空行为给定的\*域/路径\***添加**新的会话 cookie。</span><span class="sxs-lookup"><span data-stu-id="c38f1-199">**Add** a new session cookie for the given *Domain/Path* by clicking on the empty row at the bottom of the table.</span></span> <span data-ttu-id="c38f1-200">这仅适用于会话 cookie;具有特定到期日期) 的永久 cookie (必须通过传统方法进行设置。</span><span class="sxs-lookup"><span data-stu-id="c38f1-200">This only works for session cookies; permanent cookies (with specific expiry dates) must be set with traditional methods.</span></span> <span data-ttu-id="c38f1-201">根据页面位置自动填充 *域* 和 *路径* 值。</span><span class="sxs-lookup"><span data-stu-id="c38f1-201">The *Domain* and *Path* values are auto-filled according to the location of the page.</span></span>

<span data-ttu-id="c38f1-202">*Cookie 列表*的列是可排序的：</span><span class="sxs-lookup"><span data-stu-id="c38f1-202">The columns of the *Cookies list* are sortable:</span></span>

<span data-ttu-id="c38f1-203">列</span><span class="sxs-lookup"><span data-stu-id="c38f1-203">Column</span></span> | <span data-ttu-id="c38f1-204">描述</span><span class="sxs-lookup"><span data-stu-id="c38f1-204">Description</span></span>
:------------ | :-------------
<span data-ttu-id="c38f1-205">名称</span><span class="sxs-lookup"><span data-stu-id="c38f1-205">Name</span></span> | <span data-ttu-id="c38f1-206">Cookie 的名称</span><span class="sxs-lookup"><span data-stu-id="c38f1-206">Name of the cookie</span></span>
<span data-ttu-id="c38f1-207">Value</span><span class="sxs-lookup"><span data-stu-id="c38f1-207">Value</span></span> | <span data-ttu-id="c38f1-208">Cookie 的值</span><span class="sxs-lookup"><span data-stu-id="c38f1-208">Value of the cookie</span></span>
<span data-ttu-id="c38f1-209">域</span><span class="sxs-lookup"><span data-stu-id="c38f1-209">Domain</span></span> | <span data-ttu-id="c38f1-210">Cookie (的主机名可能为空) </span><span class="sxs-lookup"><span data-stu-id="c38f1-210">Host name of the cookie (may be empty)</span></span>
<span data-ttu-id="c38f1-211">路径</span><span class="sxs-lookup"><span data-stu-id="c38f1-211">Path</span></span> | <span data-ttu-id="c38f1-212">Cookie (的 URL 路径可能为空) </span><span class="sxs-lookup"><span data-stu-id="c38f1-212">URL path for the cookie (may be empty)</span></span>
<span data-ttu-id="c38f1-213">到期</span><span class="sxs-lookup"><span data-stu-id="c38f1-213">Expires</span></span> | <span data-ttu-id="c38f1-214">HTTP 日期时间戳形式的 cookie 的最长生存期。</span><span class="sxs-lookup"><span data-stu-id="c38f1-214">Maximum lifetime of the cookie as an HTTP-date timestamp.</span></span> <span data-ttu-id="c38f1-215">如果未 `Expires` 设置或，则将 `Max-Age` 该项视为 *会话* cookie。</span><span class="sxs-lookup"><span data-stu-id="c38f1-215">If no `Expires` or `Max-Age` was set, the entry is considered a *Session* cookie.</span></span>
<span data-ttu-id="c38f1-216">仅限 HTTP</span><span class="sxs-lookup"><span data-stu-id="c38f1-216">HTTP only</span></span> | <span data-ttu-id="c38f1-217">指示 cookie 是否已通过指令进行了设置 `HttpOnly` ，以指示它无法从 JavaScript 中访问</span><span class="sxs-lookup"><span data-stu-id="c38f1-217">Indicates if the cookie was set with `HttpOnly` directive, indicating that it is inaccessible from JavaScript</span></span>
<span data-ttu-id="c38f1-218">安全</span><span class="sxs-lookup"><span data-stu-id="c38f1-218">Secure</span></span> | <span data-ttu-id="c38f1-219">指示是否使用该指令设置 cookie `Secure` ，指示它将仅从使用 SSL 和 HTTPS 协议的请求发送到服务器。</span><span class="sxs-lookup"><span data-stu-id="c38f1-219">Indicates if the cookie was set with the `Secure` directive, indicating it will only be sent to the server from a request using SSL and the HTTPS protocol.</span></span>

<span data-ttu-id="c38f1-220">有关 cookie 属性的更多详细信息，请参阅**MDN web 文档**[集-cookie](https://developer.mozilla.org/docs/Web/HTTP/Headers/Set-Cookie)参考。</span><span class="sxs-lookup"><span data-stu-id="c38f1-220">See the **MDN web docs** [Set-Cookie](https://developer.mozilla.org/docs/Web/HTTP/Headers/Set-Cookie) reference for further details on cookie properties.</span></span>

### <span data-ttu-id="c38f1-221">上下文菜单</span><span class="sxs-lookup"><span data-stu-id="c38f1-221">Context menu</span></span>

<span data-ttu-id="c38f1-222">除了 " *Cookies* " 选项卡 [工具栏](#cookies-manager)，您还可以通过右键单击 **上下文菜单** 和/或键盘 [快捷方式](#shortcuts)管理您的 cookie。</span><span class="sxs-lookup"><span data-stu-id="c38f1-222">In addition to the *Cookies* tab [toolbar](#cookies-manager), you can also manage your cookies from the right-click **Context menu** and/or the keyboard [shortcuts](#shortcuts).</span></span>

### <span data-ttu-id="c38f1-223">快捷方式</span><span class="sxs-lookup"><span data-stu-id="c38f1-223">Shortcuts</span></span>

| <span data-ttu-id="c38f1-224">操作</span><span class="sxs-lookup"><span data-stu-id="c38f1-224">Action</span></span>                     | <span data-ttu-id="c38f1-225">快捷方式</span><span class="sxs-lookup"><span data-stu-id="c38f1-225">Shortcut</span></span>                 |
|:---------------------------|:-------------------------|
| <span data-ttu-id="c38f1-226">刷新</span><span class="sxs-lookup"><span data-stu-id="c38f1-226">Refresh</span></span>                    | `Ctrl` + `F5`            |
| <span data-ttu-id="c38f1-227">删除 cookie</span><span class="sxs-lookup"><span data-stu-id="c38f1-227">Delete cookie</span></span>              | `Del`                    |
| <span data-ttu-id="c38f1-228">删除所有 cookie</span><span class="sxs-lookup"><span data-stu-id="c38f1-228">Delete all cookies</span></span>         | `Ctrl` + `Shift` + `Del` |
| <span data-ttu-id="c38f1-229">删除所有会话 cookie</span><span class="sxs-lookup"><span data-stu-id="c38f1-229">Delete all session cookies</span></span> | `Ctrl` + `Del`           |
| <span data-ttu-id="c38f1-230">复制所选项目</span><span class="sxs-lookup"><span data-stu-id="c38f1-230">Copy selected items</span></span>        | `Ctrl` + `C`             |
| <span data-ttu-id="c38f1-231">全选</span><span class="sxs-lookup"><span data-stu-id="c38f1-231">Select all</span></span>                 | `Ctrl` + `A`             |

### <span data-ttu-id="c38f1-232">缓存管理器</span><span class="sxs-lookup"><span data-stu-id="c38f1-232">Cache manager</span></span>

<span data-ttu-id="c38f1-233">单击特定的缓存条目将打开服务辅助进程 **缓存** 管理器，您可以在其中检查和删除缓存项 (*请求* 和 *响应* 键/值对) ：</span><span class="sxs-lookup"><span data-stu-id="c38f1-233">Clicking on a specific cache entry will open up the service worker **Cache** manager, where you can inspect and optionally delete cache entries (*Request* and *Response* key/value pairs):</span></span>

![缓存管理器](./media/storage_cache.png)

### <span data-ttu-id="c38f1-235">快捷方式</span><span class="sxs-lookup"><span data-stu-id="c38f1-235">Shortcuts</span></span>

#### <span data-ttu-id="c38f1-236">缓存管理器</span><span class="sxs-lookup"><span data-stu-id="c38f1-236">Cache manager</span></span>

| <span data-ttu-id="c38f1-237">操作</span><span class="sxs-lookup"><span data-stu-id="c38f1-237">Action</span></span>              | <span data-ttu-id="c38f1-238">快捷方式</span><span class="sxs-lookup"><span data-stu-id="c38f1-238">Shortcut</span></span>      |
|:--------------------|:--------------|
| <span data-ttu-id="c38f1-239">刷新</span><span class="sxs-lookup"><span data-stu-id="c38f1-239">Refresh</span></span>             | `Ctrl` + `F5` |
| <span data-ttu-id="c38f1-240">删除项</span><span class="sxs-lookup"><span data-stu-id="c38f1-240">Delete item</span></span>         | `Del`         |
| <span data-ttu-id="c38f1-241">复制所选项目</span><span class="sxs-lookup"><span data-stu-id="c38f1-241">Copy selected items</span></span> | `Ctrl` + `C`  |
| <span data-ttu-id="c38f1-242">全选</span><span class="sxs-lookup"><span data-stu-id="c38f1-242">Select all</span></span>          | `Ctrl` + `A`  |
