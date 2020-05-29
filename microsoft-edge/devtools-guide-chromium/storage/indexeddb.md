---
title: 通过 Microsoft Edge DevTools 查看和更改 IndexedDB 数据
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/30/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 4eca78dcd92048d75f8488fddc7b210da68690df
ms.sourcegitcommit: ad68bfbb355f6cfdaaf6612b77ea3985d4d6a58b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/01/2020
ms.locfileid: "10612086"
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





# <span data-ttu-id="656b7-103">通过 Microsoft Edge DevTools 查看和更改 IndexedDB 数据</span><span class="sxs-lookup"><span data-stu-id="656b7-103">View And Change IndexedDB Data With Microsoft Edge DevTools</span></span>   

  

<span data-ttu-id="656b7-104">本指南介绍如何使用[Microsoft Edge DevTools][MicrosoftEdgeDevTools]查看和更改[IndexedDB][MDNIndexedDBAPI]数据。</span><span class="sxs-lookup"><span data-stu-id="656b7-104">This guide shows you how to use [Microsoft Edge DevTools][MicrosoftEdgeDevTools] to view and change [IndexedDB][MDNIndexedDBAPI] data.</span></span>  <span data-ttu-id="656b7-105">它假定你熟悉 DevTools。</span><span class="sxs-lookup"><span data-stu-id="656b7-105">It assumes you are familiar with DevTools.</span></span>  <span data-ttu-id="656b7-106">它还假定你熟悉 IndexedDB。</span><span class="sxs-lookup"><span data-stu-id="656b7-106">It also assumes you are familiar with IndexedDB.</span></span>  <span data-ttu-id="656b7-107">如果不是，请参阅[使用 IndexedDB][MDNUsingIndexedDB]。</span><span class="sxs-lookup"><span data-stu-id="656b7-107">If not, see [Using IndexedDB][MDNUsingIndexedDB].</span></span>  

## <span data-ttu-id="656b7-108">查看 IndexedDB 数据</span><span class="sxs-lookup"><span data-stu-id="656b7-108">View IndexedDB data</span></span>   

1.  <span data-ttu-id="656b7-109">选择 "**应用程序**" 选项卡以打开 "**应用程序**" 面板。</span><span class="sxs-lookup"><span data-stu-id="656b7-109">Select the **Application** tab to open the **Application** panel.</span></span>  <span data-ttu-id="656b7-110">默认情况下，**清单**窗格是默认打开的。</span><span class="sxs-lookup"><span data-stu-id="656b7-110">The **Manifest** pane usually opens by default.</span></span>  
    
    > ##### <span data-ttu-id="656b7-111">图 1</span><span class="sxs-lookup"><span data-stu-id="656b7-111">Figure 1</span></span>  
    > <span data-ttu-id="656b7-112">清单窗格</span><span class="sxs-lookup"><span data-stu-id="656b7-112">The Manifest pane</span></span>  
    > ![清单窗格][ImageManifest]  

1.  <span data-ttu-id="656b7-114">展开 " **IndexedDB** " 菜单以查看哪些数据库可用。</span><span class="sxs-lookup"><span data-stu-id="656b7-114">Expand the **IndexedDB** menu to see which databases are available.</span></span>  
    
    > ##### <span data-ttu-id="656b7-115">图 2</span><span class="sxs-lookup"><span data-stu-id="656b7-115">Figure 2</span></span>  
    > <span data-ttu-id="656b7-116">**IndexedDB**菜单</span><span class="sxs-lookup"><span data-stu-id="656b7-116">The **IndexedDB** menu</span></span>  
    > ![IndexedDB 菜单][ImageIndexedDBMenu]  
    
    *   ![<span data-ttu-id="656b7-118">数据库图标 ][ImageDatabaseIcon] `notes - https://mdn.github.io` 表示数据库，其中 `notes` 是数据库的名称， `https://mdn.github.io` 是访问数据库的来源。</span><span class="sxs-lookup"><span data-stu-id="656b7-118">Database icon][ImageDatabaseIcon] `notes - https://mdn.github.io` represents a database, where `notes` is the name of the database and `https://mdn.github.io` is the origin that accesses the database.</span></span>  
    *   ![<span data-ttu-id="656b7-119">对象存储图标 ][ImageObjectStoreIcon] `notes` 是一个对象存储。</span><span class="sxs-lookup"><span data-stu-id="656b7-119">Object Store icon][ImageObjectStoreIcon] `notes` is an object store.</span></span>  
    *   <span data-ttu-id="656b7-120">"**标题**" 和 "**正文**" 是[索引][MDNUsingIndexedDBUsingIndex]。</span><span class="sxs-lookup"><span data-stu-id="656b7-120">**title** and **body** are [indexes][MDNUsingIndexedDBUsingIndex].</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="656b7-121">**已知限制** 第三方数据库不可见。</span><span class="sxs-lookup"><span data-stu-id="656b7-121">**Known Limitation**  Third-party databases are not visible.</span></span>  <span data-ttu-id="656b7-122">例如，如果你使用将 `<iframe>` 广告嵌入到你的页面上，而你的广告网络使用 IndexedDB，则你的广告网络的 IndexedDB 数据将不可见。</span><span class="sxs-lookup"><span data-stu-id="656b7-122">For example, if you use an `<iframe>` to embed an ad on your page, and your ad network uses IndexedDB, the IndexedDB data for your ad network is not be visible.</span></span>  <span data-ttu-id="656b7-123">请参阅[问题 #943770][ChromiumIssue943770]。</span><span class="sxs-lookup"><span data-stu-id="656b7-123">See [issue #943770][ChromiumIssue943770].</span></span>  
    
1.  <span data-ttu-id="656b7-124">选择一个数据库以查看原始版本号和版本号。</span><span class="sxs-lookup"><span data-stu-id="656b7-124">Select a database to see the origin and version number.</span></span>  
    
    > ##### <span data-ttu-id="656b7-125">图 3</span><span class="sxs-lookup"><span data-stu-id="656b7-125">Figure 3</span></span>  
    > <span data-ttu-id="656b7-126">**Notes**数据库</span><span class="sxs-lookup"><span data-stu-id="656b7-126">The **notes** database</span></span>  
    > ![Notes 数据库][ImageIndexedDBDatabase]  
    
1.  <span data-ttu-id="656b7-128">选择一个对象存储以查看键/值对。</span><span class="sxs-lookup"><span data-stu-id="656b7-128">Select an object store to see the key-value pairs.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="656b7-129">IndexedDB 数据不会实时更新。</span><span class="sxs-lookup"><span data-stu-id="656b7-129">IndexedDB data does not update in real-time.</span></span>  <span data-ttu-id="656b7-130">请参阅[刷新 IndexedDB 数据](#refresh-indexeddb-data)。</span><span class="sxs-lookup"><span data-stu-id="656b7-130">See [Refresh IndexedDB data](#refresh-indexeddb-data).</span></span>  
    
    > ##### <span data-ttu-id="656b7-131">图 4</span><span class="sxs-lookup"><span data-stu-id="656b7-131">Figure 4</span></span>  
    > <span data-ttu-id="656b7-132">**Notes**对象存储</span><span class="sxs-lookup"><span data-stu-id="656b7-132">The **notes** object store</span></span>  
    > ![Notes 对象存储][ImageIndexedDBObjectStore]  

    *   <span data-ttu-id="656b7-134">**Total entries**指对象存储中的键值对的总数。</span><span class="sxs-lookup"><span data-stu-id="656b7-134">**Total entries** is the total number of key-value pairs in the object store.</span></span>  
    *   <span data-ttu-id="656b7-135">"**密钥生成器" 值**是下一个可用键。</span><span class="sxs-lookup"><span data-stu-id="656b7-135">**Key generator value** is the next available key.</span></span>  <span data-ttu-id="656b7-136">此字段仅在使用[密钥生成器][MDNBasicConceptsKeyGenerator]时显示。</span><span class="sxs-lookup"><span data-stu-id="656b7-136">This field is only shown when using [key generators][MDNBasicConceptsKeyGenerator].</span></span>  

1.  <span data-ttu-id="656b7-137">在 "**值**" 列中选择一个单元格以展开该值。</span><span class="sxs-lookup"><span data-stu-id="656b7-137">Select a cell in the **Value** column to expand that value.</span></span>  
    
    > ##### <span data-ttu-id="656b7-138">图 5</span><span class="sxs-lookup"><span data-stu-id="656b7-138">Figure 5</span></span>  
    > <span data-ttu-id="656b7-139">查看 IndexedDB 值</span><span class="sxs-lookup"><span data-stu-id="656b7-139">Viewing an IndexedDB value</span></span>  
    > ![查看 IndexedDB 值][ImageIndexedBDValue]  
    
1.  <span data-ttu-id="656b7-141">选择[图](#figure-6)中的 "**标题**" 或 "**正文**" 等索引，以便根据该索引的值对对象存储进行排序。</span><span class="sxs-lookup"><span data-stu-id="656b7-141">Select an index, such as **title** or **body** in [Figure 6](#figure-6), to sort the object store according to the values of that index.</span></span>  
   
    > ##### <span data-ttu-id="656b7-142">图 6</span><span class="sxs-lookup"><span data-stu-id="656b7-142">Figure 6</span></span>  
    > <span data-ttu-id="656b7-143">按**标题**键按字母顺序排序的对象存储</span><span class="sxs-lookup"><span data-stu-id="656b7-143">An object store that is sorted alphabetically according to the **title** key</span></span>  
    > ![按索引对对象存储进行排序][ImageIndexedDBIndex]  

## <span data-ttu-id="656b7-145">刷新 IndexedDB 数据</span><span class="sxs-lookup"><span data-stu-id="656b7-145">Refresh IndexedDB data</span></span>   

<span data-ttu-id="656b7-146">IndexedDB 不会实时更新**应用程序**面板中的值。</span><span class="sxs-lookup"><span data-stu-id="656b7-146">IndexedDB values in the **Application** panel do not update in real-time.</span></span>  <span data-ttu-id="656b7-147">选择**Refresh** ![ ][ImageReloadIcon] "查看对象存储" 时刷新 "刷新" 以刷新数据，或查看数据库，然后单击 "**刷新数据库**" 以刷新所有数据。</span><span class="sxs-lookup"><span data-stu-id="656b7-147">Select **Refresh** ![Refresh][ImageReloadIcon] when viewing an object store to refresh the data, or view a database and click **Refresh database** to refresh all data.</span></span>  

> ##### <span data-ttu-id="656b7-148">图 7</span><span class="sxs-lookup"><span data-stu-id="656b7-148">Figure 7</span></span>  
> <span data-ttu-id="656b7-149">查看数据库</span><span class="sxs-lookup"><span data-stu-id="656b7-149">Viewing a database</span></span>  
> ![查看数据库][ImageIndexedDBDatabase2]  

## <span data-ttu-id="656b7-151">编辑 IndexedDB 数据</span><span class="sxs-lookup"><span data-stu-id="656b7-151">Edit IndexedDB data</span></span>   

<span data-ttu-id="656b7-152">IndexedDB 键和值不能通过**应用程序**面板进行编辑。</span><span class="sxs-lookup"><span data-stu-id="656b7-152">IndexedDB keys and values are not editable from the **Application** panel.</span></span>  <span data-ttu-id="656b7-153">但是，由于 DevTools 有权访问页面上下文，因此你可能会在 DevTools 内运行 JavaScript 代码以编辑 IndexedDB 数据。</span><span class="sxs-lookup"><span data-stu-id="656b7-153">Since DevTools has access to page context, however, you may run JavaScript code within DevTools to edit IndexedDB data.</span></span>  

### <span data-ttu-id="656b7-154">用代码段编辑 IndexedDB 数据</span><span class="sxs-lookup"><span data-stu-id="656b7-154">Edit IndexedDB data with Snippets</span></span>   

<span data-ttu-id="656b7-155">[代码段][DevtoolsJavascriptSnippets]是在 DevTools 中存储和运行 JavaScript 代码块的一种方法。</span><span class="sxs-lookup"><span data-stu-id="656b7-155">[Snippets][DevtoolsJavascriptSnippets] are a way to store and run blocks of JavaScript code within DevTools.</span></span>  <span data-ttu-id="656b7-156">运行代码段时，会将结果记录到**控制台**。</span><span class="sxs-lookup"><span data-stu-id="656b7-156">When you run a Snippet, the result is logged to the **Console**.</span></span>  <span data-ttu-id="656b7-157">你可以使用代码段来运行 JavaScript 代码以编辑 IndexedDB 数据库。</span><span class="sxs-lookup"><span data-stu-id="656b7-157">You may use a Snippet to run JavaScript code to edit an IndexedDB database.</span></span>  

> ##### <span data-ttu-id="656b7-158">图 8</span><span class="sxs-lookup"><span data-stu-id="656b7-158">Figure 8</span></span>  
> <span data-ttu-id="656b7-159">使用代码段与 IndexedDB 交互</span><span class="sxs-lookup"><span data-stu-id="656b7-159">Using a Snippet to interact with IndexedDB</span></span>  
> ![使用代码段与 IndexedDB 交互][ImageIndexedDBSnippet]  

## <span data-ttu-id="656b7-161">删除 IndexedDB 数据</span><span class="sxs-lookup"><span data-stu-id="656b7-161">Delete IndexedDB data</span></span>   

### <span data-ttu-id="656b7-162">删除 IndexedDB 键值对</span><span class="sxs-lookup"><span data-stu-id="656b7-162">Delete an IndexedDB key-value pair</span></span>   

1.  <span data-ttu-id="656b7-163">[查看 IndexedDB 对象存储](#view-indexeddb-data)。</span><span class="sxs-lookup"><span data-stu-id="656b7-163">[View an IndexedDB object store](#view-indexeddb-data).</span></span>  
1.  <span data-ttu-id="656b7-164">选择要删除的键/值对。</span><span class="sxs-lookup"><span data-stu-id="656b7-164">Select the key-value pair that you want to delete.</span></span>  <span data-ttu-id="656b7-165">DevTools 将突出显示它以指示它已选中。</span><span class="sxs-lookup"><span data-stu-id="656b7-165">DevTools highlights it to indicate that it is selected.</span></span>  
    
    > ##### <span data-ttu-id="656b7-166">图 9</span><span class="sxs-lookup"><span data-stu-id="656b7-166">Figure 9</span></span>  
    > <span data-ttu-id="656b7-167">选择键/值对以删除它</span><span class="sxs-lookup"><span data-stu-id="656b7-167">Selecting a key-value pair in order to delete it</span></span>  
    > ![选择键/值对以删除它][ImageIndexedDBKeyValuePair]  

1.  <span data-ttu-id="656b7-169">按下 `Delete` 键或单击 "**删除**所选 ![ 删除" ][ImageDeleteIcon] 。</span><span class="sxs-lookup"><span data-stu-id="656b7-169">Press the `Delete` key or click **Delete Selected** ![Delete Selected][ImageDeleteIcon].</span></span>  
    
    > ##### <span data-ttu-id="656b7-170">图 10</span><span class="sxs-lookup"><span data-stu-id="656b7-170">Figure 10</span></span>  
    > <span data-ttu-id="656b7-171">删除键值对后，对象存储的外观</span><span class="sxs-lookup"><span data-stu-id="656b7-171">How the object store looks after the key-value pair has been deleted</span></span>  
    > ![删除键值对后，对象存储的外观][ImageIndexedDBKeyValuePairDeleted]  

### <span data-ttu-id="656b7-173">删除对象存储中的所有键/值对</span><span class="sxs-lookup"><span data-stu-id="656b7-173">Delete all key-value pairs in an object store</span></span>   

1.  <span data-ttu-id="656b7-174">[查看 IndexedDB 对象存储](#view-indexeddb-data)。</span><span class="sxs-lookup"><span data-stu-id="656b7-174">[View an IndexedDB object store](#view-indexeddb-data).</span></span>  
    
    > ##### <span data-ttu-id="656b7-175">图 11</span><span class="sxs-lookup"><span data-stu-id="656b7-175">Figure 11</span></span>  
    > <span data-ttu-id="656b7-176">查看对象存储</span><span class="sxs-lookup"><span data-stu-id="656b7-176">Viewing an object store</span></span>  
    > ![查看对象存储][ImageIndexedDBObjectStore]  

1.  <span data-ttu-id="656b7-178">选择 "**清除对象存储**" ![ 清除对象存储 ][ImageClearIcon] 。</span><span class="sxs-lookup"><span data-stu-id="656b7-178">Select **Clear object store** ![Clear object store][ImageClearIcon].</span></span>  

### <span data-ttu-id="656b7-179">删除 IndexedDB 数据库</span><span class="sxs-lookup"><span data-stu-id="656b7-179">Delete an IndexedDB database</span></span>   

1.  <span data-ttu-id="656b7-180">查看要删除的[IndexedDB 数据库](#view-indexeddb-data)。</span><span class="sxs-lookup"><span data-stu-id="656b7-180">[View the IndexedDB database](#view-indexeddb-data) that you want to delete.</span></span>  
1.  <span data-ttu-id="656b7-181">选择 "**删除数据库**"。</span><span class="sxs-lookup"><span data-stu-id="656b7-181">Select **Delete database**.</span></span>  
    
    > ##### <span data-ttu-id="656b7-182">图 12</span><span class="sxs-lookup"><span data-stu-id="656b7-182">Figure 12</span></span>  
    > <span data-ttu-id="656b7-183">"**删除数据库**" 按钮</span><span class="sxs-lookup"><span data-stu-id="656b7-183">The **Delete database** button</span></span>  
    > !["删除数据库" 按钮][ImageIndexedDBDatabase]  

### <span data-ttu-id="656b7-185">删除所有 IndexedDB 存储</span><span class="sxs-lookup"><span data-stu-id="656b7-185">Delete all IndexedDB storage</span></span>   

1.  <span data-ttu-id="656b7-186">打开 "**清除存储**" 窗格。</span><span class="sxs-lookup"><span data-stu-id="656b7-186">Open the **Clear storage** pane.</span></span>  

1.  <span data-ttu-id="656b7-187">确保已启用 " **IndexedDB** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="656b7-187">Make sure that the **IndexedDB** checkbox is enabled.</span></span>  

1.  <span data-ttu-id="656b7-188">选择 "**清除网站数据**"。</span><span class="sxs-lookup"><span data-stu-id="656b7-188">Select **Clear site data**.</span></span>  
    
    > ##### <span data-ttu-id="656b7-189">图 13</span><span class="sxs-lookup"><span data-stu-id="656b7-189">Figure 13</span></span>  
    > <span data-ttu-id="656b7-190">"清除**存储**" 窗格- ![ "清除存储" 窗格][ImageIndexedDBClearStorage]</span><span class="sxs-lookup"><span data-stu-id="656b7-190">The **Clear storage** pane ![The Clear storage pane][ImageIndexedDBClearStorage]</span></span>  

 



<!-- image links -->  

[ImageClearIcon]: /microsoft-edge/devtools-guide-chromium/media/clear-icon.msft.png  
[ImageDatabaseIcon]: /microsoft-edge/devtools-guide-chromium/media/database-icon.msft.png  
[ImageDeleteIcon]: /microsoft-edge/devtools-guide-chromium/media/delete-icon.msft.png  
[ImageObjectStoreIcon]: /microsoft-edge/devtools-guide-chromium/media/object-store-icon.msft.png  
[ImageReloadIcon]: /microsoft-edge/devtools-guide-chromium/media/reload-icon.msft.png  

[ImageManifest]: /microsoft-edge/devtools-guide-chromium/media/storage-application-manifest-empty.msft.png "图1：清单窗格"  
[ImageIndexedDBMenu]: /microsoft-edge/devtools-guide-chromium/media/storage-application-storage-indexeddb.msft.png "图2： IndexedDB 菜单"  
[ImageIndexedDBDatabase]: /microsoft-edge/devtools-guide-chromium/media/storage-application-storage-indexeddb-notes_db.msft.png "图3： notes_db 数据库"  
[ImageIndexedDBObjectStore]: /microsoft-edge/devtools-guide-chromium/media/storage-application-storage-indexeddb-notes_db-notes_os.msft.png "图4： notes_os 对象存储"  
[ImageIndexedBDValue]: /microsoft-edge/devtools-guide-chromium/media/storage-application-storage-indexeddb-notes_db-notes_os-edge-chromium.msft.png "图5：查看 IndexedDB 值"  
[ImageIndexedDBIndex]: /microsoft-edge/devtools-guide-chromium/media/storage-application-storage-indexeddb-notes_db-notes_os-title.msft.png "图6：按索引对对象存储进行排序"  
[ImageIndexedDBDatabase2]: /microsoft-edge/devtools-guide-chromium/media/storage-application-storage-indexeddb-notes_db-notes_os-refresh-database.msft.png "图7：查看数据库"  
[ImageIndexedDBSnippet]: /microsoft-edge/devtools-guide-chromium/media/storage-sources-snippets-indexeddb-output.msft.png "图8：使用代码段与 IndexedDB 交互"  
[ImageIndexedDBKeyValuePair]: /microsoft-edge/devtools-guide-chromium/media/storage-application-storage-indexeddb-notes_db-notes_os2.msft.png "图9：选择键/值对以删除它"  
[ImageIndexedDBKeyValuePairDeleted]: /microsoft-edge/devtools-guide-chromium/media/storage-application-storage-indexeddb-notes_db-notes_os-delete-selected.msft.png "图10：删除键值对后对象存储的外观"  
[ImageIndexedDBObjectStore]: /microsoft-edge/devtools-guide-chromium/media/storage-application-storage-indexeddb-notes_db-notes_os-clear-object-store.msft.png "图11：查看对象存储"  
[ImageIndexedDBDatabase]: /microsoft-edge/devtools-guide-chromium/media/storage-application-storage-indexeddb-notes_db-delete-database.msft.png "图12： "删除数据库" 按钮"  
[ImageIndexedDBClearStorage]: /microsoft-edge/devtools-guide-chromium/media/storage-application-clear-storage-indexeddb-clear-site-data.msft.png "图13： "清除存储" 窗格"  

<!-- links -->  

[MicrosoftEdgeDevTools]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge （Chromium）开发人员工具"  
[DevtoolsJavascriptSnippets]: /microsoft-edge/devtools-guide-chromium/javascript/snippets "在具有 Microsoft Edge DevTools 的任何页面上运行 JavaScript 片段"  

[ChromiumIssue943770]: https://crbug.com/943770 "943770-DevTools： Show iframe IndexedDB 数据库-chromium-Monorail"  

[MDNBasicConceptsKeyGenerator]: https://developer.mozilla.org/docs/Web/API/IndexedDB_API/Basic_Concepts_Behind_IndexedDB#gloss_keygenerator "密钥生成器-基本概念 |MDN"  
[MDNIndexedDBAPI]: https://developer.mozilla.org/docs/Web/API/IndexedDB_API "IndexedDB API |MDN"  
[MDNUsingIndexedDB]: https://developer.mozilla.org/docs/Web/API/IndexedDB_API/Using_IndexedDB "使用 IndexedDB |MDN"  
[MDNUsingIndexedDBUsingIndex]: https://developer.mozilla.org/docs/Web/API/IndexedDB_API/Using_IndexedDB#Using_an_index "使用索引-使用 IndexedDB |MDN"  

> [!NOTE]
> <span data-ttu-id="656b7-211">此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="656b7-211">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="656b7-212">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/storage/indexeddb)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools \ & Lighthouse \）创作。</span><span class="sxs-lookup"><span data-stu-id="656b7-212">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/storage/indexeddb) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
<span data-ttu-id="656b7-214">此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="656b7-214">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
