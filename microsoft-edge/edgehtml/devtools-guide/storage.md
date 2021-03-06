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
# <a name="storage"></a><span data-ttu-id="ce2d2-104">存储</span><span class="sxs-lookup"><span data-stu-id="ce2d2-104">Storage</span></span>

<span data-ttu-id="ce2d2-105">使用 **存储** 面板检查和管理各种本地缓存的数据，包括：</span><span class="sxs-lookup"><span data-stu-id="ce2d2-105">Use the **Storage** panel to inspect and manage various locally cached data, including:</span></span>  

*   <span data-ttu-id="ce2d2-106">[Web 存储](#local-and-session-storage-managers) \ (本地和会话存储\) 键/值对</span><span class="sxs-lookup"><span data-stu-id="ce2d2-106">[Web storage](#local-and-session-storage-managers) \(Local and Session storage\) key/values pairs</span></span>  
*   <span data-ttu-id="ce2d2-107">[已编制索引的 DB](#indexeddb-manager) 结构化数据</span><span class="sxs-lookup"><span data-stu-id="ce2d2-107">[Indexed DB](#indexeddb-manager) structured data</span></span>  
*   <span data-ttu-id="ce2d2-108">[域](#cookies-list) 的 Cookie</span><span class="sxs-lookup"><span data-stu-id="ce2d2-108">[Cookies](#cookies-list) for the domain</span></span>  
*   <span data-ttu-id="ce2d2-109">[缓存](#cache-manager) \ (请求/响应对\) 服务工作器调试</span><span class="sxs-lookup"><span data-stu-id="ce2d2-109">[Cache](#cache-manager) \(request/response pairs\) for service worker debugging</span></span>  

<span data-ttu-id="ce2d2-110">展开其中任何类别并单击子项以打开其资源管理器选项卡。</span><span class="sxs-lookup"><span data-stu-id="ce2d2-110">Expand any of those categories and click on a child entry to open its resource manager tab.</span></span>  

## <a name="local-and-session-storage-managers"></a><span data-ttu-id="ce2d2-111">本地和会话存储管理器</span><span class="sxs-lookup"><span data-stu-id="ce2d2-111">Local and Session storage managers</span></span>  

<span data-ttu-id="ce2d2-112">使用本地存储管理器和会话存储管理器检查和管理页面的 Web 存储。</span><span class="sxs-lookup"><span data-stu-id="ce2d2-112">Use the Local Storage manager and Session Storage manager to inspect and manage the web storage for your page.</span></span>  

<span data-ttu-id="ce2d2-113">存储**面板\*\*\*\*的资源选取**器内的本地存储和会话存储[文件夹](./debugger.md#resource-picker)显示页面的源列表。</span><span class="sxs-lookup"><span data-stu-id="ce2d2-113">The **Local Storage** and **Session Storage** folders inside the Storage panel's [Resource picker](./debugger.md#resource-picker) display a list of origins for the page.</span></span>  <span data-ttu-id="ce2d2-114">选择其中一个帧可打开通过[Window.localStorage](https://developer.mozilla.org/docs/Web/API/Window/localStorage)或[Window.sessionStorage](https://developer.mozilla.org/docs/Web/API/Window/sessionStorage)设置的当前键/值对的可编辑表，分别 \ (和/或直接从 DevTools 存储[](#storage-list)列表 \) 设置。</span><span class="sxs-lookup"><span data-stu-id="ce2d2-114">Selecting one of these frames opens up an editable table of the current key/value pairs set via [Window.localStorage](https://developer.mozilla.org/docs/Web/API/Window/localStorage) or [Window.sessionStorage](https://developer.mozilla.org/docs/Web/API/Window/sessionStorage), respectively \(and/or set directly from the  DevTools [Storage list](#storage-list)\).</span></span>  

![DevTools 存储管理器](./media/storage_web_storage.png)  

<span data-ttu-id="ce2d2-116">从"本地存储和会话存储"选项卡中，您可以：</span><span class="sxs-lookup"><span data-stu-id="ce2d2-116">From the Local Storage and Session Storage tabs you can:</span></span>  

*   <span data-ttu-id="ce2d2-117">**刷新**\ (`Ctrl+F5` \) ，以查看给定[](#cookies-list)域的当前键/值对集。</span><span class="sxs-lookup"><span data-stu-id="ce2d2-117">**Refresh** \(`Ctrl+F5`\) the [storage list](#cookies-list) to see the current set of key/values pairs for the given domain.</span></span>  <span data-ttu-id="ce2d2-118">\ (脚本更新时列表不自动刷新。\) </span><span class="sxs-lookup"><span data-stu-id="ce2d2-118">\(The list does not auto-refresh upon script updates.\)</span></span>  
*   <span data-ttu-id="ce2d2-119">**模拟达到**  Microsoft Edge Web 存储的存储限制。</span><span class="sxs-lookup"><span data-stu-id="ce2d2-119">**Simulate reaching the storage limit**  for Microsoft Edge web storage.</span></span>  <span data-ttu-id="ce2d2-120">每个域和子域都有自己的存储区域，但存在一个组合限制：</span><span class="sxs-lookup"><span data-stu-id="ce2d2-120">Each domain and subdomain has its own storage area, however there is a combined limit:</span></span>  
    *   <span data-ttu-id="ce2d2-121">**子域**：最多 5 个磁盘空间</span><span class="sxs-lookup"><span data-stu-id="ce2d2-121">**Subdomains**:  up to 5 MBs of space</span></span>  
    *   <span data-ttu-id="ce2d2-122">**域**：最多 10 个磁盘空间</span><span class="sxs-lookup"><span data-stu-id="ce2d2-122">**Domains**:  up to 10 MBs of space</span></span>  
    *   <span data-ttu-id="ce2d2-123">**所有域总计**：最多 50 个磁盘空间</span><span class="sxs-lookup"><span data-stu-id="ce2d2-123">**Total for all domains**:  up to 50 MBs of space</span></span>  

   <span data-ttu-id="ce2d2-124">一旦关闭引用其源的最后一个浏览器选项卡，将清除会话存储。</span><span class="sxs-lookup"><span data-stu-id="ce2d2-124">Session storage is cleared as soon as the last browser tab referencing its origin is closed.</span></span>  <span data-ttu-id="ce2d2-125">本地存储条目无限期保留，直到页面或用户手动以编程方式清除：</span><span class="sxs-lookup"><span data-stu-id="ce2d2-125">Local storage entries persist indefinitely until cleared programmatically by the page or manually by the user:</span></span>  

   <span data-ttu-id="ce2d2-126">**设置**  > **清除浏览数据**  > **Cookie 和保存的网站数据**</span><span class="sxs-lookup"><span data-stu-id="ce2d2-126">**Settings** > **Clear browsing data** > **Cookies and saved website data**</span></span>  

![从"Microsoft Edge 设置"面板中清除浏览数据](./media/settings_clear_browsing_data.png)  

### <a name="storage-list"></a><span data-ttu-id="ce2d2-128">存储列表</span><span class="sxs-lookup"><span data-stu-id="ce2d2-128">Storage list</span></span>  

<span data-ttu-id="ce2d2-129">从存储列表表中，您可以：</span><span class="sxs-lookup"><span data-stu-id="ce2d2-129">From the Storage list table you can:</span></span>  

*   <span data-ttu-id="ce2d2-130">**通过单击表中的** 任一 `key/value` 列名称检查对并排序。</span><span class="sxs-lookup"><span data-stu-id="ce2d2-130">**Inspect and sort** your `key/value` pairs by clicking on either column name in the table.</span></span>  
*   <span data-ttu-id="ce2d2-131">**在** `Key` 单元格 `Value` 中单击，编辑现有条目的和。</span><span class="sxs-lookup"><span data-stu-id="ce2d2-131">**Edit** the `Key` and `Value` of an existing entry by clicking in the cell.</span></span>  
*   <span data-ttu-id="ce2d2-132">**删除** \ (\) 右键单击上下文菜单选项"删除项目"中的 `Del` **条目**。</span><span class="sxs-lookup"><span data-stu-id="ce2d2-132">**Delete** \(`Del`\) an entry from the right-click context menu option, **Delete item**.</span></span>  
*   <span data-ttu-id="ce2d2-133">**通过** 单击表 `key/value` 底部的空行添加新对。</span><span class="sxs-lookup"><span data-stu-id="ce2d2-133">**Add** a new `key/value` pair by clicking on the empty row at the bottom of the table.</span></span>  

### <a name="shortcuts"></a><span data-ttu-id="ce2d2-134">快捷方式</span><span class="sxs-lookup"><span data-stu-id="ce2d2-134">Shortcuts</span></span>

| <span data-ttu-id="ce2d2-135">操作</span><span class="sxs-lookup"><span data-stu-id="ce2d2-135">Action</span></span> | <span data-ttu-id="ce2d2-136">快捷方式</span><span class="sxs-lookup"><span data-stu-id="ce2d2-136">Shortcut</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="ce2d2-137">刷新</span><span class="sxs-lookup"><span data-stu-id="ce2d2-137">Refresh</span></span> | `Ctrl`+`F5` |  
| <span data-ttu-id="ce2d2-138">删除项</span><span class="sxs-lookup"><span data-stu-id="ce2d2-138">Delete item</span></span> | `Del` |  
| <span data-ttu-id="ce2d2-139">复制所选项目</span><span class="sxs-lookup"><span data-stu-id="ce2d2-139">Copy selected items</span></span> | `Ctrl`+`C` |  
| <span data-ttu-id="ce2d2-140">全选</span><span class="sxs-lookup"><span data-stu-id="ce2d2-140">Select all</span></span> | `Ctrl`+`A` |  

## <a name="indexeddb-manager"></a><span data-ttu-id="ce2d2-141">IndexedDB 管理器</span><span class="sxs-lookup"><span data-stu-id="ce2d2-141">IndexedDB manager</span></span>  

<span data-ttu-id="ce2d2-142">使用 **IndexedDB** 选项卡检查和管理本地存储在客户端计算机上的结构化数据。</span><span class="sxs-lookup"><span data-stu-id="ce2d2-142">Use the **IndexedDB** tab to inspect and manage the structured data stored locally on a client machine.</span></span>  <span data-ttu-id="ce2d2-143">具体来说，您可以检查/排序和刷新对象存储和索引，还可以删除单个键值条目。</span><span class="sxs-lookup"><span data-stu-id="ce2d2-143">Specifically, you can inspect/sort and refresh your object stores and indices, and also delete individual key-value entries.</span></span>  

> [!TIP]
> <span data-ttu-id="ce2d2-144">可以使用我们的 [Audio Mixer](https://developer.microsoft.com/microsoft-edge/testdrive/demos/audiomixer/) 演示在 Microsoft Edge DevTools 中测试 *驱动 IndexedDB* 管理器。</span><span class="sxs-lookup"><span data-stu-id="ce2d2-144">You can use our [Audio Mixer](https://developer.microsoft.com/microsoft-edge/testdrive/demos/audiomixer/) demo to test drive the *IndexedDB manager* in Microsoft Edge DevTools.</span></span>  

<span data-ttu-id="ce2d2-145">若要删除为 Microsoft Edge 中的当前用户存储的所有 IndexedDB 数据，请使用"Microsoft Edge 设置 **"** 菜单：</span><span class="sxs-lookup"><span data-stu-id="ce2d2-145">To delete all the IndexedDB data stored for the current user in Microsoft Edge, use the Microsoft Edge **Settings** menu:</span></span>  

<span data-ttu-id="ce2d2-146">**...** > **设置**  > **清除浏览数据**  > **Cookie 和保存的网站数据**</span><span class="sxs-lookup"><span data-stu-id="ce2d2-146">**...** > **Settings** > **Clear browsing data** > **Cookies and saved website data**</span></span>  

<span data-ttu-id="ce2d2-147">调试器的资源选取器内的文件夹显示页面加载的资源中的源 `IndexedDB` 列表。 [](./debugger.md#resource-picker)</span><span class="sxs-lookup"><span data-stu-id="ce2d2-147">The `IndexedDB` folder inside the Debugger's [Resource picker](./debugger.md#resource-picker) displays a list of origins from the resources loaded by the page.</span></span>  <span data-ttu-id="ce2d2-148">任何 IndexedDB \ (IDB\) 数据库都将在源及其对象存储下列出。</span><span class="sxs-lookup"><span data-stu-id="ce2d2-148">Any IndexedDB \(IDB\) databases will be listed under the origin, along with their object stores.</span></span>  

![DevTools IndexedDB 管理器](./media/storage_indexeddb.png)  

### <a name="indexeddb-toolbar"></a><span data-ttu-id="ce2d2-150">IndexedDB 工具栏</span><span class="sxs-lookup"><span data-stu-id="ce2d2-150">IndexedDB Toolbar</span></span>  

<span data-ttu-id="ce2d2-151">从 IndexedDB 工具栏中，您可以：</span><span class="sxs-lookup"><span data-stu-id="ce2d2-151">From the IndexedDB toolbar you can:</span></span>  

*   <span data-ttu-id="ce2d2-152">**刷新**\ (\) 以查看数据库的对象 `Ctrl` + `F5` 存储或索引中的当前条目。</span><span class="sxs-lookup"><span data-stu-id="ce2d2-152">**Refresh** \(`Ctrl`+`F5`\) to see the current entries in the object store or index of your database.</span></span>  <span data-ttu-id="ce2d2-153">对数据库进行更改时，IndexedDB 管理器不会自动刷新。</span><span class="sxs-lookup"><span data-stu-id="ce2d2-153">The IndexedDB manager does not auto-refresh when changes are made to your database.</span></span>  

### <a name="object-store-entries-list"></a><span data-ttu-id="ce2d2-154">对象存储条目列表</span><span class="sxs-lookup"><span data-stu-id="ce2d2-154">Object store entries list</span></span>  

<span data-ttu-id="ce2d2-155">从对象存储或索引表中，您可以：</span><span class="sxs-lookup"><span data-stu-id="ce2d2-155">From the Object store or Index table you can:</span></span>  

*   <span data-ttu-id="ce2d2-156">**通过单击表中的** 任何列名来检查键值对并排序。</span><span class="sxs-lookup"><span data-stu-id="ce2d2-156">**Inspect and sort** your key-value pairs by clicking on any column name in the table.</span></span>  
*   <span data-ttu-id="ce2d2-157">**刷新**\ (`Ctrl` + `F5` \) </span><span class="sxs-lookup"><span data-stu-id="ce2d2-157">**Refresh** \(`Ctrl`+`F5`\)</span></span>  
*   <span data-ttu-id="ce2d2-158">**删除项目** \ (`Del` \) 删除对象存储或索引中的选定条目。</span><span class="sxs-lookup"><span data-stu-id="ce2d2-158">**Delete item** \(`Del`\) to remove the selected entry in your object store or index.</span></span>  <span data-ttu-id="ce2d2-159">还可以从右键单击上下文菜单选项"删除[](#context-menu)项目 **"中完成此操作**。</span><span class="sxs-lookup"><span data-stu-id="ce2d2-159">You can also do this from the right-click [context menu](#context-menu) option, **Delete item**.</span></span>  
*   <span data-ttu-id="ce2d2-160">**复制选定项目**\ (`Ctrl` + `C` \) 以将所选项目复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="ce2d2-160">**Copy selected items** \(`Ctrl`+`C`\) to copy the selected item to your clipboard.</span></span>  <span data-ttu-id="ce2d2-161">您还可以从右键单击上下文菜单选项复制所选[](#context-menu)项目**来完成此操作**。</span><span class="sxs-lookup"><span data-stu-id="ce2d2-161">You can also do this from the right-click [context menu](#context-menu) option, **Copy selected item**.</span></span>  
*   <span data-ttu-id="ce2d2-162">**选择所有**\ (\) 以选择对象存储或 `Ctrl` + `A` 索引中的所有条目。</span><span class="sxs-lookup"><span data-stu-id="ce2d2-162">**Select all** \(`Ctrl`+`A`\) to select all the entries in your object store or index.</span></span>  <span data-ttu-id="ce2d2-163">还可以从右键单击上下文菜单选项"全[](#context-menu)选 **"来完成此操作**。</span><span class="sxs-lookup"><span data-stu-id="ce2d2-163">You can also do this from the right-click [context menu](#context-menu) option, **Select all**.</span></span>  

<span data-ttu-id="ce2d2-164">对象存储或索引表的列可排序：</span><span class="sxs-lookup"><span data-stu-id="ce2d2-164">The columns of the Object store or Index table are sortable:</span></span>  

| <span data-ttu-id="ce2d2-165">列</span><span class="sxs-lookup"><span data-stu-id="ce2d2-165">Column</span></span> | <span data-ttu-id="ce2d2-166">说明</span><span class="sxs-lookup"><span data-stu-id="ce2d2-166">Description</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="ce2d2-167">密钥</span><span class="sxs-lookup"><span data-stu-id="ce2d2-167">Key</span></span> | <span data-ttu-id="ce2d2-168">键值对 \ (在对象存储上 **) 主键**\) 的名称相同;在索引上进行 (时，索引键 \) 光标的当前键\名称</span><span class="sxs-lookup"><span data-stu-id="ce2d2-168">Name of the key-value pair \(same as **Primary Key**\) when iterating over an object store; Name of the index key \(cursor's current key\) when iterating over an index</span></span> |  
| <span data-ttu-id="ce2d2-169">主键</span><span class="sxs-lookup"><span data-stu-id="ce2d2-169">Primary Key</span></span> | <span data-ttu-id="ce2d2-170">键值对的名称 \ (有关[IDB](https://developer.mozilla.org/docs/Web/API/IndexedDB_API/Using_IndexedDB#Structuring_the_database)\*\*\*\* 键 \) </span><span class="sxs-lookup"><span data-stu-id="ce2d2-170">Name of the key-value pair \(see **MDN web docs** for more on IDB [keys](https://developer.mozilla.org/docs/Web/API/IndexedDB_API/Using_IndexedDB#Structuring_the_database)\)</span></span> |  
| <span data-ttu-id="ce2d2-171">Value</span><span class="sxs-lookup"><span data-stu-id="ce2d2-171">Value</span></span> | <span data-ttu-id="ce2d2-172">键值对的值</span><span class="sxs-lookup"><span data-stu-id="ce2d2-172">Value of the key-value pair</span></span> |  

<span data-ttu-id="ce2d2-173">有关[IndexedDB](https://developer.mozilla.org/docs/Web/API/IndexedDB_API)概念和用法的更多内容，请查看*MDN* Web 文档。</span><span class="sxs-lookup"><span data-stu-id="ce2d2-173">Check out *MDN web docs* for more on [IndexedDB concepts and usage](https://developer.mozilla.org/docs/Web/API/IndexedDB_API).</span></span>  

### <a name="context-menu"></a><span data-ttu-id="ce2d2-174">上下文菜单</span><span class="sxs-lookup"><span data-stu-id="ce2d2-174">Context menu</span></span>  

<span data-ttu-id="ce2d2-175">除了[*IndexedDB*](#indexeddb-toolbar)工具栏之外，还可以从右键单击"上下文"菜单和/或键盘快捷方式管理对象存储或\*\*\*\* 索引[中的数据](#shortcuts)。</span><span class="sxs-lookup"><span data-stu-id="ce2d2-175">In addition to the [*IndexedDB* toolbar](#indexeddb-toolbar), you can also manage your data in object stores or indices from the right-click **Context menu** and/or the keyboard [shortcuts](#shortcuts).</span></span>  

### <a name="shortcuts"></a><span data-ttu-id="ce2d2-176">快捷方式</span><span class="sxs-lookup"><span data-stu-id="ce2d2-176">Shortcuts</span></span>

| <span data-ttu-id="ce2d2-177">操作</span><span class="sxs-lookup"><span data-stu-id="ce2d2-177">Action</span></span> | <span data-ttu-id="ce2d2-178">快捷方式</span><span class="sxs-lookup"><span data-stu-id="ce2d2-178">Shortcut</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="ce2d2-179">刷新</span><span class="sxs-lookup"><span data-stu-id="ce2d2-179">Refresh</span></span> | `Ctrl`+`F5` |  
| <span data-ttu-id="ce2d2-180">删除键值对</span><span class="sxs-lookup"><span data-stu-id="ce2d2-180">Delete key-value pair</span></span> | `Del` |  
| <span data-ttu-id="ce2d2-181">复制所选项目</span><span class="sxs-lookup"><span data-stu-id="ce2d2-181">Copy selected items</span></span> | `Ctrl`+`C` |  
| <span data-ttu-id="ce2d2-182">全选</span><span class="sxs-lookup"><span data-stu-id="ce2d2-182">Select all</span></span> | `Ctrl +`<span data-ttu-id="ce2d2-183">A'</span><span class="sxs-lookup"><span data-stu-id="ce2d2-183">A\`</span></span> |  

## <a name="cookies-manager"></a><span data-ttu-id="ce2d2-184">Cookie 管理器</span><span class="sxs-lookup"><span data-stu-id="ce2d2-184">Cookies manager</span></span>  

<span data-ttu-id="ce2d2-185">使用 Cookie 管理器检查和管理给定域的 Cookie。</span><span class="sxs-lookup"><span data-stu-id="ce2d2-185">Use the Cookies manager to inspect and manage the cookies for the given domain.</span></span>  

<span data-ttu-id="ce2d2-186">调试器的资源选取器内的文件夹显示页面加载的资源中的源 `Cookies` 列表。 [](./debugger.md#resource-picker)</span><span class="sxs-lookup"><span data-stu-id="ce2d2-186">The `Cookies` folder inside the Debugger's [Resource picker](./debugger.md#resource-picker) displays a list of origins from the resources loaded by the page.</span></span>  <span data-ttu-id="ce2d2-187">选择其中一个框架将打开一个表，该表代表[HTTP](https://developer.mozilla.org/docs/Web/HTTP/Cookies)标头或通过[Document.cookie 脚本设置的当前 Cookie。](https://developer.mozilla.org/docs/Web/API/Document/cookie)</span><span class="sxs-lookup"><span data-stu-id="ce2d2-187">Selecting one of these frames opens up a table representing the current cookies set by either [HTTP](https://developer.mozilla.org/docs/Web/HTTP/Cookies) header or via script with [Document.cookie](https://developer.mozilla.org/docs/Web/API/Document/cookie).</span></span>  

![DevTools Cookies 管理器](./media/storage_cookies.png)  

<span data-ttu-id="ce2d2-189">在"Cookie"选项卡工具栏中，您可以：</span><span class="sxs-lookup"><span data-stu-id="ce2d2-189">From the Cookies tab toolbar you can:</span></span>  

*   <span data-ttu-id="ce2d2-190">**刷新**\ (\) Cookie 列表以查看给定域 `Ctrl` + `F5` 的当前 Cookie 集。 [](#cookies-list)</span><span class="sxs-lookup"><span data-stu-id="ce2d2-190">**Refresh** \(`Ctrl`+`F5`\) the [Cookies list](#cookies-list) to see the current set of cookies for the given domain.</span></span>  <span data-ttu-id="ce2d2-191">\ (列表不自动刷新。\) </span><span class="sxs-lookup"><span data-stu-id="ce2d2-191">\(The list does not auto-refresh.\)</span></span>  
*   <span data-ttu-id="ce2d2-192">**删除当前**页面路径的所有 cookie \ (`Ctrl` + `Shift` + `Del` \) \ (\) 和 permanent\) 。</span><span class="sxs-lookup"><span data-stu-id="ce2d2-192">**Delete all cookies** \(`Ctrl`+`Shift`+`Del`\) \(session and permanent\) for the path of the current page.</span></span>  
*   <span data-ttu-id="ce2d2-193">**删除当前页面**路径的所有会话 cookie \ (`Ctrl` + `Del` \) \) 。</span><span class="sxs-lookup"><span data-stu-id="ce2d2-193">**Delete all session cookies** \(`Ctrl`+`Del`\) for the path of the current page.</span></span>  

<span data-ttu-id="ce2d2-194">若要完全清除 Cookie 列表，您可能需要从网络面板\*\*\*\* 工具栏中清除[域的所有](./network.md#toolbar)Cookie。</span><span class="sxs-lookup"><span data-stu-id="ce2d2-194">To completely clear your Cookies list, you might need to **Clear all cookies for the domain** from the [Network](./network.md#toolbar) panel toolbar.</span></span>  

### <a name="cookies-list"></a><span data-ttu-id="ce2d2-195">Cookie 列表</span><span class="sxs-lookup"><span data-stu-id="ce2d2-195">Cookies list</span></span>  

<span data-ttu-id="ce2d2-196">从 Cookie 列表表中，您可以：</span><span class="sxs-lookup"><span data-stu-id="ce2d2-196">From the Cookies list table you can:</span></span>  

*   <span data-ttu-id="ce2d2-197">**单击表中的** 任何列名称，检查 Cookie 并排序。</span><span class="sxs-lookup"><span data-stu-id="ce2d2-197">**Inspect and sort** your cookies by clicking on any column name in the table.</span></span>  
*   <span data-ttu-id="ce2d2-198">**在** `Name` 单元格 `Value` 中单击，编辑现有 Cookie 的和。</span><span class="sxs-lookup"><span data-stu-id="ce2d2-198">**Edit** the `Name` and `Value` of an existing cookie by clicking in the cell.</span></span>  
*   <span data-ttu-id="ce2d2-199">**删除**\ (\) 右键单击上下文菜单选项中的 `Del` [](#context-menu) `Delete cookie` Cookie。</span><span class="sxs-lookup"><span data-stu-id="ce2d2-199">**Delete** \(`Del`\) a cookie from the right-click [context menu](#context-menu) option, `Delete cookie`.</span></span>  
*   <span data-ttu-id="ce2d2-200">**单击** 表底部的空行，为给定内容添加新的会话 `Domain/Path` Cookie。</span><span class="sxs-lookup"><span data-stu-id="ce2d2-200">**Add** a new session cookie for the given `Domain/Path` by clicking on the empty row at the bottom of the table.</span></span>  <span data-ttu-id="ce2d2-201">这仅适用于会话 Cookie;必须使用传统 (设置具有特定到期日期的永久 cookie\) 。</span><span class="sxs-lookup"><span data-stu-id="ce2d2-201">This only works for session cookies; permanent cookies \(with specific expiry dates\) must be set with traditional methods.</span></span>  <span data-ttu-id="ce2d2-202">And `Domain` `Path` 值根据页面的位置自动填充。</span><span class="sxs-lookup"><span data-stu-id="ce2d2-202">The `Domain` and `Path` values are auto-filled according to the location of the page.</span></span>  

<span data-ttu-id="ce2d2-203">Cookie 列表的列可排序：</span><span class="sxs-lookup"><span data-stu-id="ce2d2-203">The columns of the Cookies list are sortable:</span></span>

| <span data-ttu-id="ce2d2-204">列</span><span class="sxs-lookup"><span data-stu-id="ce2d2-204">Column</span></span> | <span data-ttu-id="ce2d2-205">说明</span><span class="sxs-lookup"><span data-stu-id="ce2d2-205">Description</span></span> |  
| :--- | :--- |  
| <span data-ttu-id="ce2d2-206">名称</span><span class="sxs-lookup"><span data-stu-id="ce2d2-206">Name</span></span> | <span data-ttu-id="ce2d2-207">Cookie 的名称</span><span class="sxs-lookup"><span data-stu-id="ce2d2-207">Name of the cookie</span></span> |  
| <span data-ttu-id="ce2d2-208">Value</span><span class="sxs-lookup"><span data-stu-id="ce2d2-208">Value</span></span> | <span data-ttu-id="ce2d2-209">Cookie 的值</span><span class="sxs-lookup"><span data-stu-id="ce2d2-209">Value of the cookie</span></span> |  
| <span data-ttu-id="ce2d2-210">域</span><span class="sxs-lookup"><span data-stu-id="ce2d2-210">Domain</span></span> | <span data-ttu-id="ce2d2-211">Cookie \ (的主机名可能为空\) </span><span class="sxs-lookup"><span data-stu-id="ce2d2-211">Host name of the cookie \(may be empty\)</span></span> |  
| <span data-ttu-id="ce2d2-212">路径</span><span class="sxs-lookup"><span data-stu-id="ce2d2-212">Path</span></span> | <span data-ttu-id="ce2d2-213">Cookie \ (的 URL 路径可能为空\) </span><span class="sxs-lookup"><span data-stu-id="ce2d2-213">URL path for the cookie \(may be empty\)</span></span> |  
| <span data-ttu-id="ce2d2-214">到期</span><span class="sxs-lookup"><span data-stu-id="ce2d2-214">Expires</span></span> | <span data-ttu-id="ce2d2-215">作为 HTTP 日期时间戳的 Cookie 的最大生存期。</span><span class="sxs-lookup"><span data-stu-id="ce2d2-215">Maximum lifetime of the cookie as an HTTP-date timestamp.</span></span>  <span data-ttu-id="ce2d2-216">如果未 `Expires` 设置 `Max-Age` 或未设置，则条目将被视为会话 Cookie。</span><span class="sxs-lookup"><span data-stu-id="ce2d2-216">If no `Expires` or `Max-Age` was set, the entry is considered a Session cookie.</span></span>  |  
| <span data-ttu-id="ce2d2-217">仅 HTTP</span><span class="sxs-lookup"><span data-stu-id="ce2d2-217">HTTP only</span></span> | <span data-ttu-id="ce2d2-218">指示 Cookie 是否使用指令进行设置，指示无法从 `HttpOnly` JavaScript 访问该 Cookie</span><span class="sxs-lookup"><span data-stu-id="ce2d2-218">Indicates if the cookie was set with `HttpOnly` directive, indicating that it is inaccessible from JavaScript</span></span> |  
| <span data-ttu-id="ce2d2-219">安全</span><span class="sxs-lookup"><span data-stu-id="ce2d2-219">Secure</span></span> | <span data-ttu-id="ce2d2-220">指示 Cookie 是否与指令一起设置，指示它只会从使用 SSL 和 HTTPS 协议的请求发送到 `Secure` 服务器。</span><span class="sxs-lookup"><span data-stu-id="ce2d2-220">Indicates if the cookie was set with the `Secure` directive, indicating it will only be sent to the server from a request using SSL and the HTTPS protocol.</span></span>  |  

<span data-ttu-id="ce2d2-221">有关 Cookie 属性的更多详细信息，请参阅**MDN Web 文档**[集-Cookie](https://developer.mozilla.org/docs/Web/HTTP/Headers/Set-Cookie)参考。</span><span class="sxs-lookup"><span data-stu-id="ce2d2-221">See the **MDN web docs** [Set-Cookie](https://developer.mozilla.org/docs/Web/HTTP/Headers/Set-Cookie) reference for further details on cookie properties.</span></span>  

### <a name="context-menu"></a><span data-ttu-id="ce2d2-222">上下文菜单</span><span class="sxs-lookup"><span data-stu-id="ce2d2-222">Context menu</span></span>  

<span data-ttu-id="ce2d2-223">除了 Cookie 选项卡工具栏之外[](#cookies-manager)，您还可以从右键单击"上下文"菜单和/或键盘\*\*\*\* 快捷方式管理[Cookie。](#shortcuts)</span><span class="sxs-lookup"><span data-stu-id="ce2d2-223">In addition to the Cookies tab [toolbar](#cookies-manager), you can also manage your cookies from the right-click **Context menu** and/or the keyboard [shortcuts](#shortcuts).</span></span>  

### <a name="shortcuts"></a><span data-ttu-id="ce2d2-224">快捷方式</span><span class="sxs-lookup"><span data-stu-id="ce2d2-224">Shortcuts</span></span>  

| <span data-ttu-id="ce2d2-225">操作</span><span class="sxs-lookup"><span data-stu-id="ce2d2-225">Action</span></span> | <span data-ttu-id="ce2d2-226">快捷方式</span><span class="sxs-lookup"><span data-stu-id="ce2d2-226">Shortcut</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="ce2d2-227">刷新</span><span class="sxs-lookup"><span data-stu-id="ce2d2-227">Refresh</span></span> | `Ctrl`+`F5` |  
| <span data-ttu-id="ce2d2-228">删除 Cookie</span><span class="sxs-lookup"><span data-stu-id="ce2d2-228">Delete cookie</span></span> | `Del` |  
| <span data-ttu-id="ce2d2-229">删除所有 Cookie</span><span class="sxs-lookup"><span data-stu-id="ce2d2-229">Delete all cookies</span></span> | `Ctrl`+`Shift`+`Del` |  
| <span data-ttu-id="ce2d2-230">删除所有会话 Cookie</span><span class="sxs-lookup"><span data-stu-id="ce2d2-230">Delete all session cookies</span></span> | `Ctrl`+`Del` |  
| <span data-ttu-id="ce2d2-231">复制所选项目</span><span class="sxs-lookup"><span data-stu-id="ce2d2-231">Copy selected items</span></span> | `Ctrl`+`C` |  
| <span data-ttu-id="ce2d2-232">全选</span><span class="sxs-lookup"><span data-stu-id="ce2d2-232">Select all</span></span> | `Ctrl`+`A` |  

### <a name="cache-manager"></a><span data-ttu-id="ce2d2-233">缓存管理器</span><span class="sxs-lookup"><span data-stu-id="ce2d2-233">Cache manager</span></span>  

<span data-ttu-id="ce2d2-234">单击特定缓存条目将打开服务工作缓存管理器，您可以在\*\*\*\* 其中检查并选择性地删除缓存条目 \ (`Request` 和 `Response` 键/值对\) ：</span><span class="sxs-lookup"><span data-stu-id="ce2d2-234">Clicking on a specific cache entry will open up the service worker **Cache** manager, where you can inspect and optionally delete cache entries \(`Request` and `Response` key/value pairs\):</span></span>  

![缓存管理器](./media/storage_cache.png)  

### <a name="shortcuts"></a><span data-ttu-id="ce2d2-236">快捷方式</span><span class="sxs-lookup"><span data-stu-id="ce2d2-236">Shortcuts</span></span>  

#### <a name="cache-manager"></a><span data-ttu-id="ce2d2-237">缓存管理器</span><span class="sxs-lookup"><span data-stu-id="ce2d2-237">Cache manager</span></span>  

| <span data-ttu-id="ce2d2-238">操作</span><span class="sxs-lookup"><span data-stu-id="ce2d2-238">Action</span></span> | <span data-ttu-id="ce2d2-239">快捷方式</span><span class="sxs-lookup"><span data-stu-id="ce2d2-239">Shortcut</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="ce2d2-240">刷新</span><span class="sxs-lookup"><span data-stu-id="ce2d2-240">Refresh</span></span> | `Ctrl`+`F5` |  
| <span data-ttu-id="ce2d2-241">删除项</span><span class="sxs-lookup"><span data-stu-id="ce2d2-241">Delete item</span></span> | `Del` |  
| <span data-ttu-id="ce2d2-242">复制所选项目</span><span class="sxs-lookup"><span data-stu-id="ce2d2-242">Copy selected items</span></span> | `Ctrl`+`C` |  
| <span data-ttu-id="ce2d2-243">全选</span><span class="sxs-lookup"><span data-stu-id="ce2d2-243">Select all</span></span> | `Ctrl`+`A` |  
