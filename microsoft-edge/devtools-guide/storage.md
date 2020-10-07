---
description: Use the Storage panel to inspect your web storage, IndexedDB, cookies, and request/response caches
title: DevTools - Storage
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web development, f12 tools, devtools, web storage, local storage, session storage, indexeddb, cookies, service worker, cache
ms.custom: seodec18
ms.openlocfilehash: 8de6e1f90f86fa09b116646918c6be1d8cfb0a72
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563454"
---
# <span data-ttu-id="244b5-104">Storage</span><span class="sxs-lookup"><span data-stu-id="244b5-104">Storage</span></span>

<span data-ttu-id="244b5-105">Use the **Storage** panel to inspect and manage various locally cached data, including:</span><span class="sxs-lookup"><span data-stu-id="244b5-105">Use the **Storage** panel to inspect and manage various locally cached data, including:</span></span>

 - <span data-ttu-id="244b5-106">[Web storage](#local-and-session-storage-managers) (*Local* and *Session* storage) key/values pairs</span><span class="sxs-lookup"><span data-stu-id="244b5-106">[Web storage](#local-and-session-storage-managers) (*Local* and *Session* storage) key/values pairs</span></span>
 - <span data-ttu-id="244b5-107">[Indexed DB](#indexeddb-manager) structured data</span><span class="sxs-lookup"><span data-stu-id="244b5-107">[Indexed DB](#indexeddb-manager) structured data</span></span>
 - <span data-ttu-id="244b5-108">[Cookies](#cookies-list) for the domain</span><span class="sxs-lookup"><span data-stu-id="244b5-108">[Cookies](#cookies-list) for the domain</span></span>
 - <span data-ttu-id="244b5-109">[Cache](#cache-manager) (request/response pairs) for service worker debugging</span><span class="sxs-lookup"><span data-stu-id="244b5-109">[Cache](#cache-manager) (request/response pairs) for service worker debugging</span></span>

<span data-ttu-id="244b5-110">Expand any of those categories and click on a child entry to open its resource manager tab.</span><span class="sxs-lookup"><span data-stu-id="244b5-110">Expand any of those categories and click on a child entry to open its resource manager tab.</span></span>

## <span data-ttu-id="244b5-111">Local and Session storage managers</span><span class="sxs-lookup"><span data-stu-id="244b5-111">Local and Session storage managers</span></span>

<span data-ttu-id="244b5-112">Use the *Local Storage manager* and *Session Storage manager* to inspect and manage the web storage for  your page.</span><span class="sxs-lookup"><span data-stu-id="244b5-112">Use the *Local Storage manager* and *Session Storage manager* to inspect and manage the web storage for  your page.</span></span> 

<span data-ttu-id="244b5-113">The **Local Storage** and **Session Storage** folders inside the Storage panel's [*Resource picker*](./debugger.md#resource-picker) display a list of origins for the page.</span><span class="sxs-lookup"><span data-stu-id="244b5-113">The **Local Storage** and **Session Storage** folders inside the Storage panel's [*Resource picker*](./debugger.md#resource-picker) display a list of origins for the page.</span></span> <span data-ttu-id="244b5-114">Selecting one of these frames opens up an editable table of the current key/value pairs set via [Window.localStorage](https://developer.mozilla.org/docs/Web/API/Window/localStorage) or [Window.sessionStorage](https://developer.mozilla.org/docs/Web/API/Window/sessionStorage), respectively (and/or set directly from the  DevTools [Storage list](#storage-list)).</span><span class="sxs-lookup"><span data-stu-id="244b5-114">Selecting one of these frames opens up an editable table of the current key/value pairs set via [Window.localStorage](https://developer.mozilla.org/docs/Web/API/Window/localStorage) or [Window.sessionStorage](https://developer.mozilla.org/docs/Web/API/Window/sessionStorage), respectively (and/or set directly from the  DevTools [Storage list](#storage-list)).</span></span>

![DevTools Cookies manager](./media/storage_web_storage.png)

<span data-ttu-id="244b5-116">From the *Local Storage* and *Session Storage* tabs you can:</span><span class="sxs-lookup"><span data-stu-id="244b5-116">From the *Local Storage* and *Session Storage* tabs you can:</span></span>

 - <span data-ttu-id="244b5-117">**Refresh** (`Ctrl+F5`) the [storage list](#cookies-list) to see the current set of key/values pairs for the given domain.</span><span class="sxs-lookup"><span data-stu-id="244b5-117">**Refresh** (`Ctrl+F5`) the [storage list](#cookies-list) to see the current set of key/values pairs for the given domain.</span></span> <span data-ttu-id="244b5-118">(The list does not auto-refresh upon script updates.)</span><span class="sxs-lookup"><span data-stu-id="244b5-118">(The list does not auto-refresh upon script updates.)</span></span>
 - <span data-ttu-id="244b5-119">**Simulate reaching the storage limit** for Microsoft Edge web storage.</span><span class="sxs-lookup"><span data-stu-id="244b5-119">**Simulate reaching the storage limit** for Microsoft Edge web storage.</span></span> <span data-ttu-id="244b5-120">Each domain and subdomain has its own storage area, however there is a combined limit:</span><span class="sxs-lookup"><span data-stu-id="244b5-120">Each domain and subdomain has its own storage area, however there is a combined limit:</span></span>
    - <span data-ttu-id="244b5-121">**Subdomains:** up to 5 MBs of space</span><span class="sxs-lookup"><span data-stu-id="244b5-121">**Subdomains:** up to 5 MBs of space</span></span>
    - <span data-ttu-id="244b5-122">**Domains:** up to 10 MBs of space</span><span class="sxs-lookup"><span data-stu-id="244b5-122">**Domains:** up to 10 MBs of space</span></span>
    - <span data-ttu-id="244b5-123">**Total for all domains:** up to 50 MBs of space</span><span class="sxs-lookup"><span data-stu-id="244b5-123">**Total for all domains:** up to 50 MBs of space</span></span>

   <span data-ttu-id="244b5-124">Session storage is cleared as soon as the last browser tab referencing its origin is closed.</span><span class="sxs-lookup"><span data-stu-id="244b5-124">Session storage is cleared as soon as the last browser tab referencing its origin is closed.</span></span> <span data-ttu-id="244b5-125">Local storage entries persist indefinitely until cleared programmatically by the page or manually by the user:</span><span class="sxs-lookup"><span data-stu-id="244b5-125">Local storage entries persist indefinitely until cleared programmatically by the page or manually by the user:</span></span>

   <span data-ttu-id="244b5-126">**Settings** > **Clear browsing data** > **Cookies and saved website data**</span><span class="sxs-lookup"><span data-stu-id="244b5-126">**Settings** > **Clear browsing data** > **Cookies and saved website data**</span></span>

![Clear browsing data from the Microsoft Edge Settings panel](./media/settings_clear_browsing_data.png)

### <span data-ttu-id="244b5-128">Storage list</span><span class="sxs-lookup"><span data-stu-id="244b5-128">Storage list</span></span>

<span data-ttu-id="244b5-129">From the *Storage list* table you can:</span><span class="sxs-lookup"><span data-stu-id="244b5-129">From the *Storage list* table you can:</span></span>

 - <span data-ttu-id="244b5-130">**Inspect and sort** your key/value pairs by clicking on either column name in the table.</span><span class="sxs-lookup"><span data-stu-id="244b5-130">**Inspect and sort** your key/value pairs by clicking on either column name in the table.</span></span>
 - <span data-ttu-id="244b5-131">**Edit** the *Key* and *Value* of an existing entry by clicking in the cell.</span><span class="sxs-lookup"><span data-stu-id="244b5-131">**Edit** the *Key* and *Value* of an existing entry by clicking in the cell.</span></span>
 - <span data-ttu-id="244b5-132">**Delete** (`Del`) an entry from the right-click context menu option, *Delete item*.</span><span class="sxs-lookup"><span data-stu-id="244b5-132">**Delete** (`Del`) an entry from the right-click context menu option, *Delete item*.</span></span>
 - <span data-ttu-id="244b5-133">**Add** a new key/value pair by clicking on the empty row at the bottom of the table.</span><span class="sxs-lookup"><span data-stu-id="244b5-133">**Add** a new key/value pair by clicking on the empty row at the bottom of the table.</span></span>


### <span data-ttu-id="244b5-134">Shortcuts</span><span class="sxs-lookup"><span data-stu-id="244b5-134">Shortcuts</span></span>

| <span data-ttu-id="244b5-135">Action</span><span class="sxs-lookup"><span data-stu-id="244b5-135">Action</span></span>              | <span data-ttu-id="244b5-136">Shortcut</span><span class="sxs-lookup"><span data-stu-id="244b5-136">Shortcut</span></span>      |
|:--------------------|:--------------|
| <span data-ttu-id="244b5-137">Refresh</span><span class="sxs-lookup"><span data-stu-id="244b5-137">Refresh</span></span>             | `Ctrl` + `F5` |
| <span data-ttu-id="244b5-138">Delete item</span><span class="sxs-lookup"><span data-stu-id="244b5-138">Delete item</span></span>         | `Del`         |
| <span data-ttu-id="244b5-139">Copy selected items</span><span class="sxs-lookup"><span data-stu-id="244b5-139">Copy selected items</span></span> | `Ctrl` + `C`  |
| <span data-ttu-id="244b5-140">Select all</span><span class="sxs-lookup"><span data-stu-id="244b5-140">Select all</span></span>          | `Ctrl` + `A`  |


## <span data-ttu-id="244b5-141">IndexedDB manager</span><span class="sxs-lookup"><span data-stu-id="244b5-141">IndexedDB manager</span></span>

<span data-ttu-id="244b5-142">Use the **IndexedDB** tab to inspect and manage the structured data stored locally on a client machine.</span><span class="sxs-lookup"><span data-stu-id="244b5-142">Use the **IndexedDB** tab to inspect and manage the structured data stored locally on a client machine.</span></span> <span data-ttu-id="244b5-143">Specifically, you can inspect/sort and refresh your object stores and indices, and also delete individual key-value entries.</span><span class="sxs-lookup"><span data-stu-id="244b5-143">Specifically, you can inspect/sort and refresh your object stores and indices, and also delete individual key-value entries.</span></span>

> [!TIP]
> <span data-ttu-id="244b5-144">You can use our [Audio Mixer](https://developer.microsoft.com/microsoft-edge/testdrive/demos/audiomixer/) demo to test drive the *IndexedDB manager* in Microsoft Edge DevTools.</span><span class="sxs-lookup"><span data-stu-id="244b5-144">You can use our [Audio Mixer](https://developer.microsoft.com/microsoft-edge/testdrive/demos/audiomixer/) demo to test drive the *IndexedDB manager* in Microsoft Edge DevTools.</span></span>

<span data-ttu-id="244b5-145">To delete all the IndexedDB data stored for the current user in Microsoft Edge, use the Microsoft Edge *Settings* menu:</span><span class="sxs-lookup"><span data-stu-id="244b5-145">To delete all the IndexedDB data stored for the current user in Microsoft Edge, use the Microsoft Edge *Settings* menu:</span></span>

<span data-ttu-id="244b5-146">**...** > **Settings** > **Clear browsing data** > **Cookies and saved website data**</span><span class="sxs-lookup"><span data-stu-id="244b5-146">**...** > **Settings** > **Clear browsing data** > **Cookies and saved website data**</span></span>

<span data-ttu-id="244b5-147">The **IndexedDB** folder inside the Debugger's [*Resource picker*](./debugger.md#resource-picker) displays a list of origins from the resources loaded by the page.</span><span class="sxs-lookup"><span data-stu-id="244b5-147">The **IndexedDB** folder inside the Debugger's [*Resource picker*](./debugger.md#resource-picker) displays a list of origins from the resources loaded by the page.</span></span> <span data-ttu-id="244b5-148">Any IndexedDB (IDB) databases will be listed under the origin, along with their object stores.</span><span class="sxs-lookup"><span data-stu-id="244b5-148">Any IndexedDB (IDB) databases will be listed under the origin, along with their object stores.</span></span> 

![DevTools IndexedDB manager](./media/storage_indexeddb.png)

### <span data-ttu-id="244b5-150">IndexedDB Toolbar</span><span class="sxs-lookup"><span data-stu-id="244b5-150">IndexedDB Toolbar</span></span>

<span data-ttu-id="244b5-151">From the *IndexedDB* toolbar you can:</span><span class="sxs-lookup"><span data-stu-id="244b5-151">From the *IndexedDB* toolbar you can:</span></span>

 - <span data-ttu-id="244b5-152">**Refresh** (`Ctrl+F5`) to see the current entries in the object store or index of your database.</span><span class="sxs-lookup"><span data-stu-id="244b5-152">**Refresh** (`Ctrl+F5`) to see the current entries in the object store or index of your database.</span></span> <span data-ttu-id="244b5-153">The IndexedDB manager does not auto-refresh when changes are made to your database.</span><span class="sxs-lookup"><span data-stu-id="244b5-153">The IndexedDB manager does not auto-refresh when changes are made to your database.</span></span>

### <span data-ttu-id="244b5-154">Object store entries list</span><span class="sxs-lookup"><span data-stu-id="244b5-154">Object store entries list</span></span>

<span data-ttu-id="244b5-155">From the *Object store* or *Index* table you can:</span><span class="sxs-lookup"><span data-stu-id="244b5-155">From the *Object store* or *Index* table you can:</span></span>

 - <span data-ttu-id="244b5-156">**Inspect and sort** your key-value pairs by clicking on any column name in the table.</span><span class="sxs-lookup"><span data-stu-id="244b5-156">**Inspect and sort** your key-value pairs by clicking on any column name in the table.</span></span>
 - <span data-ttu-id="244b5-157">**Refresh** (`Ctrl+F5`)</span><span class="sxs-lookup"><span data-stu-id="244b5-157">**Refresh** (`Ctrl+F5`)</span></span>
 - <span data-ttu-id="244b5-158">**Delete item** (`Del`) to remove the selected entry in your object store or index.</span><span class="sxs-lookup"><span data-stu-id="244b5-158">**Delete item** (`Del`) to remove the selected entry in your object store or index.</span></span> <span data-ttu-id="244b5-159">You can also do this from the right-click [context menu](#context-menu) option, *Delete item*.</span><span class="sxs-lookup"><span data-stu-id="244b5-159">You can also do this from the right-click [context menu](#context-menu) option, *Delete item*.</span></span>
 - <span data-ttu-id="244b5-160">**Copy selected items** (`Ctrl+C`) to copy the selected item to your clipboard.</span><span class="sxs-lookup"><span data-stu-id="244b5-160">**Copy selected items** (`Ctrl+C`) to copy the selected item to your clipboard.</span></span> <span data-ttu-id="244b5-161">You can also do this from the right-click [context menu](#context-menu) option, *Copy selected item*.</span><span class="sxs-lookup"><span data-stu-id="244b5-161">You can also do this from the right-click [context menu](#context-menu) option, *Copy selected item*.</span></span>
 - <span data-ttu-id="244b5-162">**Select all** (`Ctrl+A`) to select all the entries in your object store or index.</span><span class="sxs-lookup"><span data-stu-id="244b5-162">**Select all** (`Ctrl+A`) to select all the entries in your object store or index.</span></span> <span data-ttu-id="244b5-163">You can also do this from the right-click [context menu](#context-menu) option, *Select all*.</span><span class="sxs-lookup"><span data-stu-id="244b5-163">You can also do this from the right-click [context menu](#context-menu) option, *Select all*.</span></span>

<span data-ttu-id="244b5-164">The columns of the *Object store* or *Index* table are sortable:</span><span class="sxs-lookup"><span data-stu-id="244b5-164">The columns of the *Object store* or *Index* table are sortable:</span></span>

<span data-ttu-id="244b5-165">Column</span><span class="sxs-lookup"><span data-stu-id="244b5-165">Column</span></span> | <span data-ttu-id="244b5-166">Description</span><span class="sxs-lookup"><span data-stu-id="244b5-166">Description</span></span>
:------------ | :-------------
<span data-ttu-id="244b5-167">Key</span><span class="sxs-lookup"><span data-stu-id="244b5-167">Key</span></span> | <span data-ttu-id="244b5-168">Name of the key-value pair (same as *Primary Key*) when iterating over an object store; Name of the index key (cursor's current key) when iterating over an index</span><span class="sxs-lookup"><span data-stu-id="244b5-168">Name of the key-value pair (same as *Primary Key*) when iterating over an object store; Name of the index key (cursor's current key) when iterating over an index</span></span>
<span data-ttu-id="244b5-169">Primary Key</span><span class="sxs-lookup"><span data-stu-id="244b5-169">Primary Key</span></span> | <span data-ttu-id="244b5-170">Name of the key-value pair (see *MDN web docs* for more on IDB [keys](https://developer.mozilla.org/docs/Web/API/IndexedDB_API/Using_IndexedDB#Structuring_the_database))</span><span class="sxs-lookup"><span data-stu-id="244b5-170">Name of the key-value pair (see *MDN web docs* for more on IDB [keys](https://developer.mozilla.org/docs/Web/API/IndexedDB_API/Using_IndexedDB#Structuring_the_database))</span></span>
<span data-ttu-id="244b5-171">Value</span><span class="sxs-lookup"><span data-stu-id="244b5-171">Value</span></span> | <span data-ttu-id="244b5-172">Value of the key-value pair</span><span class="sxs-lookup"><span data-stu-id="244b5-172">Value of the key-value pair</span></span>

<span data-ttu-id="244b5-173">Check out *MDN web docs* for more on [IndexedDB concepts and usage](https://developer.mozilla.org/docs/Web/API/IndexedDB_API).</span><span class="sxs-lookup"><span data-stu-id="244b5-173">Check out *MDN web docs* for more on [IndexedDB concepts and usage](https://developer.mozilla.org/docs/Web/API/IndexedDB_API).</span></span>

### <span data-ttu-id="244b5-174">Context menu</span><span class="sxs-lookup"><span data-stu-id="244b5-174">Context menu</span></span>

<span data-ttu-id="244b5-175">In addition to the [*IndexedDB* toolbar](#indexeddb-toolbar), you can also manage your data in object stores or indices from the right-click **Context menu** and/or the keyboard [shortcuts](#shortcuts).</span><span class="sxs-lookup"><span data-stu-id="244b5-175">In addition to the [*IndexedDB* toolbar](#indexeddb-toolbar), you can also manage your data in object stores or indices from the right-click **Context menu** and/or the keyboard [shortcuts](#shortcuts).</span></span>

### <span data-ttu-id="244b5-176">Shortcuts</span><span class="sxs-lookup"><span data-stu-id="244b5-176">Shortcuts</span></span>

<span data-ttu-id="244b5-177">Action</span><span class="sxs-lookup"><span data-stu-id="244b5-177">Action</span></span> | <span data-ttu-id="244b5-178">Shortcut</span><span class="sxs-lookup"><span data-stu-id="244b5-178">Shortcut</span></span>
:------------ | :-------------
<span data-ttu-id="244b5-179">Refresh</span><span class="sxs-lookup"><span data-stu-id="244b5-179">Refresh</span></span> | `Ctrl` + `F5`
<span data-ttu-id="244b5-180">Delete key-value pair</span><span class="sxs-lookup"><span data-stu-id="244b5-180">Delete key-value pair</span></span> | `Del`
<span data-ttu-id="244b5-181">Copy selected items</span><span class="sxs-lookup"><span data-stu-id="244b5-181">Copy selected items</span></span> | `Ctrl` + `C`
<span data-ttu-id="244b5-182">Select all</span><span class="sxs-lookup"><span data-stu-id="244b5-182">Select all</span></span> | `Ctrl` + `A`

## <span data-ttu-id="244b5-183">Cookies manager</span><span class="sxs-lookup"><span data-stu-id="244b5-183">Cookies manager</span></span>

<span data-ttu-id="244b5-184">Use the *Cookies manager* to inspect and manage the cookies for the given domain.</span><span class="sxs-lookup"><span data-stu-id="244b5-184">Use the *Cookies manager* to inspect and manage the cookies for the given domain.</span></span> 

<span data-ttu-id="244b5-185">The **Cookies** folder inside the Debugger's [*Resource picker*](./debugger.md#resource-picker) displays a list of origins from the resources loaded by the page.</span><span class="sxs-lookup"><span data-stu-id="244b5-185">The **Cookies** folder inside the Debugger's [*Resource picker*](./debugger.md#resource-picker) displays a list of origins from the resources loaded by the page.</span></span> <span data-ttu-id="244b5-186">Selecting one of these frames opens up a table representing the current cookies set by either [HTTP](https://developer.mozilla.org/docs/Web/HTTP/Cookies) header or via script with [Document.cookie](https://developer.mozilla.org/docs/Web/API/Document/cookie).</span><span class="sxs-lookup"><span data-stu-id="244b5-186">Selecting one of these frames opens up a table representing the current cookies set by either [HTTP](https://developer.mozilla.org/docs/Web/HTTP/Cookies) header or via script with [Document.cookie](https://developer.mozilla.org/docs/Web/API/Document/cookie).</span></span>

![DevTools Cookies manager](./media/storage_cookies.png)

<span data-ttu-id="244b5-188">From the *Cookies* tab toolbar you can:</span><span class="sxs-lookup"><span data-stu-id="244b5-188">From the *Cookies* tab toolbar you can:</span></span>

 - <span data-ttu-id="244b5-189">**Refresh** (`Ctrl+F5`) the [Cookies list](#cookies-list) to see the current set of cookies for the given domain.</span><span class="sxs-lookup"><span data-stu-id="244b5-189">**Refresh** (`Ctrl+F5`) the [Cookies list](#cookies-list) to see the current set of cookies for the given domain.</span></span> <span data-ttu-id="244b5-190">(The list does not auto-refresh.)</span><span class="sxs-lookup"><span data-stu-id="244b5-190">(The list does not auto-refresh.)</span></span>
 - <span data-ttu-id="244b5-191">**Delete all cookies** (`Ctrl+Shift+Del`) (session and permanent) for the path of the current page.</span><span class="sxs-lookup"><span data-stu-id="244b5-191">**Delete all cookies** (`Ctrl+Shift+Del`) (session and permanent) for the path of the current page.</span></span>
 - <span data-ttu-id="244b5-192">**Delete all session cookies** (`Ctrl+Del`) for the path of the current page.</span><span class="sxs-lookup"><span data-stu-id="244b5-192">**Delete all session cookies** (`Ctrl+Del`) for the path of the current page.</span></span>

<span data-ttu-id="244b5-193">To completely clear your *Cookies list*, you might need to **Clear all cookies for the domain** from the [**Network**](./network.md#toolbar) panel toolbar.</span><span class="sxs-lookup"><span data-stu-id="244b5-193">To completely clear your *Cookies list*, you might need to **Clear all cookies for the domain** from the [**Network**](./network.md#toolbar) panel toolbar.</span></span>

### <span data-ttu-id="244b5-194">Cookies list</span><span class="sxs-lookup"><span data-stu-id="244b5-194">Cookies list</span></span>

<span data-ttu-id="244b5-195">From the *Cookies list* table you can:</span><span class="sxs-lookup"><span data-stu-id="244b5-195">From the *Cookies list* table you can:</span></span>

 - <span data-ttu-id="244b5-196">**Inspect and sort** your cookies by clicking on any column name in the table.</span><span class="sxs-lookup"><span data-stu-id="244b5-196">**Inspect and sort** your cookies by clicking on any column name in the table.</span></span>
 - <span data-ttu-id="244b5-197">**Edit** the *Name* and *Value* of an existing cookie by clicking in the cell.</span><span class="sxs-lookup"><span data-stu-id="244b5-197">**Edit** the *Name* and *Value* of an existing cookie by clicking in the cell.</span></span>
 - <span data-ttu-id="244b5-198">**Delete** (`Del`) a cookie from the right-click [context menu](#context-menu) option, *Delete cookie*.</span><span class="sxs-lookup"><span data-stu-id="244b5-198">**Delete** (`Del`) a cookie from the right-click [context menu](#context-menu) option, *Delete cookie*.</span></span>
 - <span data-ttu-id="244b5-199">**Add** a new session cookie for the given *Domain/Path* by clicking on the empty row at the bottom of the table.</span><span class="sxs-lookup"><span data-stu-id="244b5-199">**Add** a new session cookie for the given *Domain/Path* by clicking on the empty row at the bottom of the table.</span></span> <span data-ttu-id="244b5-200">This only works for session cookies; permanent cookies (with specific expiry dates) must be set with traditional methods.</span><span class="sxs-lookup"><span data-stu-id="244b5-200">This only works for session cookies; permanent cookies (with specific expiry dates) must be set with traditional methods.</span></span> <span data-ttu-id="244b5-201">The *Domain* and *Path* values are auto-filled according to the location of the page.</span><span class="sxs-lookup"><span data-stu-id="244b5-201">The *Domain* and *Path* values are auto-filled according to the location of the page.</span></span>

<span data-ttu-id="244b5-202">The columns of the *Cookies list* are sortable:</span><span class="sxs-lookup"><span data-stu-id="244b5-202">The columns of the *Cookies list* are sortable:</span></span>

<span data-ttu-id="244b5-203">Column</span><span class="sxs-lookup"><span data-stu-id="244b5-203">Column</span></span> | <span data-ttu-id="244b5-204">描述</span><span class="sxs-lookup"><span data-stu-id="244b5-204">Description</span></span>
:------------ | :-------------
<span data-ttu-id="244b5-205">Name</span><span class="sxs-lookup"><span data-stu-id="244b5-205">Name</span></span> | <span data-ttu-id="244b5-206">Name of the cookie</span><span class="sxs-lookup"><span data-stu-id="244b5-206">Name of the cookie</span></span>
<span data-ttu-id="244b5-207">Value</span><span class="sxs-lookup"><span data-stu-id="244b5-207">Value</span></span> | <span data-ttu-id="244b5-208">Value of the cookie</span><span class="sxs-lookup"><span data-stu-id="244b5-208">Value of the cookie</span></span>
<span data-ttu-id="244b5-209">Domain</span><span class="sxs-lookup"><span data-stu-id="244b5-209">Domain</span></span> | <span data-ttu-id="244b5-210">Host name of the cookie (may be empty)</span><span class="sxs-lookup"><span data-stu-id="244b5-210">Host name of the cookie (may be empty)</span></span>
<span data-ttu-id="244b5-211">Path</span><span class="sxs-lookup"><span data-stu-id="244b5-211">Path</span></span> | <span data-ttu-id="244b5-212">URL path for the cookie (may be empty)</span><span class="sxs-lookup"><span data-stu-id="244b5-212">URL path for the cookie (may be empty)</span></span>
<span data-ttu-id="244b5-213">Expires</span><span class="sxs-lookup"><span data-stu-id="244b5-213">Expires</span></span> | <span data-ttu-id="244b5-214">Maximum lifetime of the cookie as an HTTP-date timestamp.</span><span class="sxs-lookup"><span data-stu-id="244b5-214">Maximum lifetime of the cookie as an HTTP-date timestamp.</span></span> <span data-ttu-id="244b5-215">If no `Expires` or `Max-Age` was set, the entry is considered a *Session* cookie.</span><span class="sxs-lookup"><span data-stu-id="244b5-215">If no `Expires` or `Max-Age` was set, the entry is considered a *Session* cookie.</span></span>
<span data-ttu-id="244b5-216">HTTP only</span><span class="sxs-lookup"><span data-stu-id="244b5-216">HTTP only</span></span> | <span data-ttu-id="244b5-217">Indicates if the cookie was set with `HttpOnly` directive, indicating that it is inaccessible from JavaScript</span><span class="sxs-lookup"><span data-stu-id="244b5-217">Indicates if the cookie was set with `HttpOnly` directive, indicating that it is inaccessible from JavaScript</span></span>
<span data-ttu-id="244b5-218">Secure</span><span class="sxs-lookup"><span data-stu-id="244b5-218">Secure</span></span> | <span data-ttu-id="244b5-219">Indicates if the cookie was set with the `Secure` directive, indicating it will only be sent to the server from a request using SSL and the HTTPS protocol.</span><span class="sxs-lookup"><span data-stu-id="244b5-219">Indicates if the cookie was set with the `Secure` directive, indicating it will only be sent to the server from a request using SSL and the HTTPS protocol.</span></span>

<span data-ttu-id="244b5-220">See the **MDN web docs** [Set-Cookie](https://developer.mozilla.org/docs/Web/HTTP/Headers/Set-Cookie) reference for further details on cookie properties.</span><span class="sxs-lookup"><span data-stu-id="244b5-220">See the **MDN web docs** [Set-Cookie](https://developer.mozilla.org/docs/Web/HTTP/Headers/Set-Cookie) reference for further details on cookie properties.</span></span>

### <span data-ttu-id="244b5-221">Context menu</span><span class="sxs-lookup"><span data-stu-id="244b5-221">Context menu</span></span>

<span data-ttu-id="244b5-222">In addition to the *Cookies* tab [toolbar](#cookies-manager), you can also manage your cookies from the right-click **Context menu** and/or the keyboard [shortcuts](#shortcuts).</span><span class="sxs-lookup"><span data-stu-id="244b5-222">In addition to the *Cookies* tab [toolbar](#cookies-manager), you can also manage your cookies from the right-click **Context menu** and/or the keyboard [shortcuts](#shortcuts).</span></span>

### <span data-ttu-id="244b5-223">Shortcuts</span><span class="sxs-lookup"><span data-stu-id="244b5-223">Shortcuts</span></span>

| <span data-ttu-id="244b5-224">Action</span><span class="sxs-lookup"><span data-stu-id="244b5-224">Action</span></span>                     | <span data-ttu-id="244b5-225">Shortcut</span><span class="sxs-lookup"><span data-stu-id="244b5-225">Shortcut</span></span>                 |
|:---------------------------|:-------------------------|
| <span data-ttu-id="244b5-226">Refresh</span><span class="sxs-lookup"><span data-stu-id="244b5-226">Refresh</span></span>                    | `Ctrl` + `F5`            |
| <span data-ttu-id="244b5-227">Delete cookie</span><span class="sxs-lookup"><span data-stu-id="244b5-227">Delete cookie</span></span>              | `Del`                    |
| <span data-ttu-id="244b5-228">Delete all cookies</span><span class="sxs-lookup"><span data-stu-id="244b5-228">Delete all cookies</span></span>         | `Ctrl` + `Shift` + `Del` |
| <span data-ttu-id="244b5-229">Delete all session cookies</span><span class="sxs-lookup"><span data-stu-id="244b5-229">Delete all session cookies</span></span> | `Ctrl` + `Del`           |
| <span data-ttu-id="244b5-230">Copy selected items</span><span class="sxs-lookup"><span data-stu-id="244b5-230">Copy selected items</span></span>        | `Ctrl` + `C`             |
| <span data-ttu-id="244b5-231">Select all</span><span class="sxs-lookup"><span data-stu-id="244b5-231">Select all</span></span>                 | `Ctrl` + `A`             |

### <span data-ttu-id="244b5-232">Cache manager</span><span class="sxs-lookup"><span data-stu-id="244b5-232">Cache manager</span></span>

<span data-ttu-id="244b5-233">Clicking on a specific cache entry will open up the service worker **Cache** manager, where you can inspect and optionally delete cache entries (*Request* and *Response* key/value pairs):</span><span class="sxs-lookup"><span data-stu-id="244b5-233">Clicking on a specific cache entry will open up the service worker **Cache** manager, where you can inspect and optionally delete cache entries (*Request* and *Response* key/value pairs):</span></span>

![Cache manager](./media/storage_cache.png)

### <span data-ttu-id="244b5-235">Shortcuts</span><span class="sxs-lookup"><span data-stu-id="244b5-235">Shortcuts</span></span>

#### <span data-ttu-id="244b5-236">Cache manager</span><span class="sxs-lookup"><span data-stu-id="244b5-236">Cache manager</span></span>

| <span data-ttu-id="244b5-237">Action</span><span class="sxs-lookup"><span data-stu-id="244b5-237">Action</span></span>              | <span data-ttu-id="244b5-238">Shortcut</span><span class="sxs-lookup"><span data-stu-id="244b5-238">Shortcut</span></span>      |
|:--------------------|:--------------|
| <span data-ttu-id="244b5-239">Refresh</span><span class="sxs-lookup"><span data-stu-id="244b5-239">Refresh</span></span>             | `Ctrl` + `F5` |
| <span data-ttu-id="244b5-240">Delete item</span><span class="sxs-lookup"><span data-stu-id="244b5-240">Delete item</span></span>         | `Del`         |
| <span data-ttu-id="244b5-241">Copy selected items</span><span class="sxs-lookup"><span data-stu-id="244b5-241">Copy selected items</span></span> | `Ctrl` + `C`  |
| <span data-ttu-id="244b5-242">Select all</span><span class="sxs-lookup"><span data-stu-id="244b5-242">Select all</span></span>          | `Ctrl` + `A`  |
