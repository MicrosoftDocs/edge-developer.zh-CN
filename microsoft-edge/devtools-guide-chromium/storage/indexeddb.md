---
description: 如何使用应用程序面板和代码段查看和更改 IndexedDB 数据。
title: 使用 Microsoft Edge DevTools 查看和更改 IndexedDB 数据
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 719348067b1343ca3d7781737fa6441f92ad7ba1
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439708"
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

# <a name="view-and-change-indexeddb-data-with-microsoft-edge-devtools"></a><span data-ttu-id="ad78c-104">使用 Microsoft Edge DevTools 查看和更改 IndexedDB 数据</span><span class="sxs-lookup"><span data-stu-id="ad78c-104">View and change IndexedDB data with Microsoft Edge DevTools</span></span>  

<span data-ttu-id="ad78c-105">本指南演示如何使用 [Microsoft Edge DevTools][MicrosoftEdgeDevTools] 查看和更改 [IndexedDB][MDNIndexedDBAPI] 数据。</span><span class="sxs-lookup"><span data-stu-id="ad78c-105">This guide shows you how to use [Microsoft Edge DevTools][MicrosoftEdgeDevTools] to view and change [IndexedDB][MDNIndexedDBAPI] data.</span></span>  <span data-ttu-id="ad78c-106">本文假定你熟悉 DevTools。</span><span class="sxs-lookup"><span data-stu-id="ad78c-106">It assumes you are familiar with DevTools.</span></span>  <span data-ttu-id="ad78c-107">本文还假定你熟悉 IndexedDB。</span><span class="sxs-lookup"><span data-stu-id="ad78c-107">It also assumes you are familiar with IndexedDB.</span></span>  <span data-ttu-id="ad78c-108">如果没有，导航到“[使用 IndexedDB][MDNUsingIndexedDB]”。</span><span class="sxs-lookup"><span data-stu-id="ad78c-108">If not, navigate to [Using IndexedDB][MDNUsingIndexedDB].</span></span>  

## <a name="view-indexeddb-data"></a><span data-ttu-id="ad78c-109">查看 IndexedDB 数据</span><span class="sxs-lookup"><span data-stu-id="ad78c-109">View IndexedDB data</span></span>  

1.  <span data-ttu-id="ad78c-110">选择“**应用程序**”选项卡以打开**应用程序**工具。</span><span class="sxs-lookup"><span data-stu-id="ad78c-110">Choose the **Application** tab to open the **Application** tool.</span></span>  <span data-ttu-id="ad78c-111">“**清单**”窗格通常默认打开。</span><span class="sxs-lookup"><span data-stu-id="ad78c-111">The **Manifest** pane usually opens by default.</span></span>  
    
    :::image type="complex" source="../media/storage-application-manifest-empty.msft.png" alt-text="“清单”窗格" lightbox="../media/storage-application-manifest-empty.msft.png":::
       <span data-ttu-id="ad78c-113">“**清单**”窗格</span><span class="sxs-lookup"><span data-stu-id="ad78c-113">The **Manifest** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="ad78c-114">展开 “**IndexedDB**” 菜单，查看哪些数据库可用。</span><span class="sxs-lookup"><span data-stu-id="ad78c-114">Expand the **IndexedDB** menu to review which databases are available.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb.msft.png" alt-text="“IndexedDB”菜单" lightbox="../media/storage-application-storage-indexeddb.msft.png":::
       <span data-ttu-id="ad78c-116">“**IndexedDB**” 菜单</span><span class="sxs-lookup"><span data-stu-id="ad78c-116">The **IndexedDB** menu</span></span>  
    :::image-end:::  
    
    *   <span data-ttu-id="ad78c-117">\(![Database icon](../media/database-icon.msft.png)\) `notes - https://mdn.github.io` 表示一个数据库，其中`notes`是数据库的名称，`https://mdn.github.io`是访问数据库的来源。</span><span class="sxs-lookup"><span data-stu-id="ad78c-117">\(![Database icon](../media/database-icon.msft.png)\) `notes - https://mdn.github.io` represents a database, where `notes` is the name of the database and `https://mdn.github.io` is the origin that accesses the database.</span></span>  
    *   <span data-ttu-id="ad78c-118">\(![Object Store icon](../media/object-store-icon.msft.png)\) `notes` 是一个对象存储。</span><span class="sxs-lookup"><span data-stu-id="ad78c-118">\(![Object Store icon](../media/object-store-icon.msft.png)\) `notes` is an object store.</span></span>  
    *   <span data-ttu-id="ad78c-119">**标题**和 **正文**是[索引][MDNUsingIndexedDBUsingIndex]。</span><span class="sxs-lookup"><span data-stu-id="ad78c-119">**title** and **body** are [indexes][MDNUsingIndexedDBUsingIndex].</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="ad78c-120">**已知限制**  第三方数据库不可见。</span><span class="sxs-lookup"><span data-stu-id="ad78c-120">**Known Limitation**  Third-party databases are not visible.</span></span>  <span data-ttu-id="ad78c-121">例如，如果使用`<iframe>`在页面上嵌入广告，并且广告网络使用 IndexedDB，则广告网络的 IndexedDB 数据将不可见。</span><span class="sxs-lookup"><span data-stu-id="ad78c-121">For example, if you use an `<iframe>` to embed an ad on your page, and your ad network uses IndexedDB, the IndexedDB data for your ad network is not be visible.</span></span>  <span data-ttu-id="ad78c-122">导航到 [issue #943770][ChromiumIssue943770]。</span><span class="sxs-lookup"><span data-stu-id="ad78c-122">Navigate to [issue #943770][ChromiumIssue943770].</span></span>  
    
1.  <span data-ttu-id="ad78c-123">选择一个数据库查看来源和版本号。</span><span class="sxs-lookup"><span data-stu-id="ad78c-123">Choose a database to review the origin and version number.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db.msft.png" alt-text="备注数据库" lightbox="../media/storage-application-storage-indexeddb-notes_db.msft.png":::
       <span data-ttu-id="ad78c-125">**备注**数据库</span><span class="sxs-lookup"><span data-stu-id="ad78c-125">The **notes** database</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="ad78c-126">选择对象存储查看键值对。</span><span class="sxs-lookup"><span data-stu-id="ad78c-126">Choose an object store to review the key-value pairs.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="ad78c-127">IndexedDB 数据不会实时更新。</span><span class="sxs-lookup"><span data-stu-id="ad78c-127">IndexedDB data does not update in real-time.</span></span>  <span data-ttu-id="ad78c-128">导航到“[刷新 IndexedDB 数据](#refresh-indexeddb-data)”。</span><span class="sxs-lookup"><span data-stu-id="ad78c-128">Navigate to [Refresh IndexedDB data](#refresh-indexeddb-data).</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-notes_os.msft.png" alt-text="备注对象存储" lightbox="../media/storage-application-storage-indexeddb-notes_db-notes_os.msft.png":::
       <span data-ttu-id="ad78c-130">**备注**对象存储</span><span class="sxs-lookup"><span data-stu-id="ad78c-130">The **notes** object store</span></span>  
    :::image-end:::  
    
    *   <span data-ttu-id="ad78c-131">**总条目数**是对象存储中键值对的总数。</span><span class="sxs-lookup"><span data-stu-id="ad78c-131">**Total entries** is the total number of key-value pairs in the object store.</span></span>  
    *   <span data-ttu-id="ad78c-132">**密钥生成器值**是下一个可用密钥。</span><span class="sxs-lookup"><span data-stu-id="ad78c-132">**Key generator value** is the next available key.</span></span>  <span data-ttu-id="ad78c-133">此字段仅在使用[密钥生成器][MDNBasicConceptsKeyGenerator]时显示。</span><span class="sxs-lookup"><span data-stu-id="ad78c-133">The field is only shown when using [key generators][MDNBasicConceptsKeyGenerator].</span></span>  
    
1.  <span data-ttu-id="ad78c-134">选择“**值**”列的单元格以展开该值。</span><span class="sxs-lookup"><span data-stu-id="ad78c-134">Choose a cell in the **Value** column to expand the value.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-notes_os-edge-chromium.msft.png" alt-text="查看 IndexedDB 值" lightbox="../media/storage-application-storage-indexeddb-notes_db-notes_os-edge-chromium.msft.png":::
       <span data-ttu-id="ad78c-136">查看 **IndexedDB** 值</span><span class="sxs-lookup"><span data-stu-id="ad78c-136">View an **IndexedDB** value</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="ad78c-137">选择一个索引（如下图的**标题**或**正文**）以根据该索引的值对对象存储排序。</span><span class="sxs-lookup"><span data-stu-id="ad78c-137">Choose an index, such as **title** or **body** in the following figure, to sort the object store according to the values of that index.</span></span>  
   
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-notes_os-title.msft.png" alt-text="按索引对对象存储排序" lightbox="../media/storage-application-storage-indexeddb-notes_db-notes_os-title.msft.png":::
       <span data-ttu-id="ad78c-139">按索引对对象存储排序</span><span class="sxs-lookup"><span data-stu-id="ad78c-139">Sort an object store by an index</span></span>  
    :::image-end:::  
    
## <a name="refresh-indexeddb-data"></a><span data-ttu-id="ad78c-140">刷新 IndexedDB 数据</span><span class="sxs-lookup"><span data-stu-id="ad78c-140">Refresh IndexedDB data</span></span>  

<span data-ttu-id="ad78c-141">**应用程序**工具中的 IndexedDB 值不会实时更新。</span><span class="sxs-lookup"><span data-stu-id="ad78c-141">IndexedDB values in the **Application** tool do not update in real-time.</span></span>  <span data-ttu-id="ad78c-142">查看对象存储时，选择“**刷新**”\(“![刷新](../media/reload-icon.msft.png)”\)以刷新数据，或在查看数据库时，选择“**刷新数据库**”以刷新全部数据。</span><span class="sxs-lookup"><span data-stu-id="ad78c-142">Choose **Refresh** \(![Refresh](../media/reload-icon.msft.png)\) when viewing an object store to refresh the data, or view a database and choose **Refresh database** to refresh all data.</span></span>  

:::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-notes_os-refresh-database.msft.png" alt-text="查看数据库" lightbox="../media/storage-application-storage-indexeddb-notes_db-notes_os-refresh-database.msft.png":::
   <span data-ttu-id="ad78c-144">查看数据库</span><span class="sxs-lookup"><span data-stu-id="ad78c-144">View a database</span></span>  
:::image-end:::  

## <a name="edit-indexeddb-data"></a><span data-ttu-id="ad78c-145">编辑 IndexedDB 数据</span><span class="sxs-lookup"><span data-stu-id="ad78c-145">Edit IndexedDB data</span></span>  

<span data-ttu-id="ad78c-146">无法通过**应用程序**工具编辑 IndexedDB 键和值。</span><span class="sxs-lookup"><span data-stu-id="ad78c-146">IndexedDB keys and values are not editable from the **Application** tool.</span></span>  <span data-ttu-id="ad78c-147">但是，由于 DevTools 可以访问页面上下文，因此你可以在 DevTools 中运行 JavaScript 代码来编辑 IndexedDB 数据。</span><span class="sxs-lookup"><span data-stu-id="ad78c-147">Since DevTools has access to page context, however, you may run JavaScript code within DevTools to edit IndexedDB data.</span></span>  

### <a name="edit-indexeddb-data-with-snippets"></a><span data-ttu-id="ad78c-148">使用代码段编辑 IndexedDB 数据</span><span class="sxs-lookup"><span data-stu-id="ad78c-148">Edit IndexedDB data with Snippets</span></span>  

<span data-ttu-id="ad78c-149">[代码段][DevtoolsJavascriptSnippets]是一种在 DevTools 中存储和运行 JavaScript 代码的方法。</span><span class="sxs-lookup"><span data-stu-id="ad78c-149">[Snippets][DevtoolsJavascriptSnippets] are a way to store and run blocks of JavaScript code within DevTools.</span></span>  <span data-ttu-id="ad78c-150">运行代码段时，结果将记录到**控制台**。</span><span class="sxs-lookup"><span data-stu-id="ad78c-150">When you run a Snippet, the result is logged to the **Console**.</span></span>  <span data-ttu-id="ad78c-151">可以使用代码段运行 JavaScript 代码来编辑 IndexedDB 数据库。</span><span class="sxs-lookup"><span data-stu-id="ad78c-151">You may use a Snippet to run JavaScript code to edit an IndexedDB database.</span></span>  

:::image type="complex" source="../media/storage-sources-snippets-indexeddb-output.msft.png" alt-text="使用代码段与 IndexedDB 交互" lightbox="../media/storage-sources-snippets-indexeddb-output.msft.png":::
   <span data-ttu-id="ad78c-153">使用代码段与 IndexedDB 交互</span><span class="sxs-lookup"><span data-stu-id="ad78c-153">Use a Snippet to interact with IndexedDB</span></span>  
:::image-end:::  

## <a name="delete-indexeddb-data"></a><span data-ttu-id="ad78c-154">删除 IndexedDB 数据</span><span class="sxs-lookup"><span data-stu-id="ad78c-154">Delete IndexedDB data</span></span>  

### <a name="delete-an-indexeddb-key-value-pair"></a><span data-ttu-id="ad78c-155">删除 IndexedDB 键值对</span><span class="sxs-lookup"><span data-stu-id="ad78c-155">Delete an IndexedDB key-value pair</span></span>  

1.  <span data-ttu-id="ad78c-156">[查看 IndexedDB 对象存储](#view-indexeddb-data)。</span><span class="sxs-lookup"><span data-stu-id="ad78c-156">[View an IndexedDB object store](#view-indexeddb-data).</span></span>  
1.  <span data-ttu-id="ad78c-157">选择要删除的键值对。</span><span class="sxs-lookup"><span data-stu-id="ad78c-157">Choose the key-value pair that you want to delete.</span></span>  <span data-ttu-id="ad78c-158">DevTools 突出显示它以指示已选中。</span><span class="sxs-lookup"><span data-stu-id="ad78c-158">DevTools highlights it to indicate that it is selected.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-notes_os2.msft.png" alt-text="选择键值对以将其删除" lightbox="../media/storage-application-storage-indexeddb-notes_db-notes_os2.msft.png":::
       <span data-ttu-id="ad78c-160">选择键值对以将其删除</span><span class="sxs-lookup"><span data-stu-id="ad78c-160">Choose a key-value pair in order to delete it</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="ad78c-161">选择`Delete`键或选择“**删除所选**”\(“![删除所选](../media/delete-icon.msft.png)”\)。</span><span class="sxs-lookup"><span data-stu-id="ad78c-161">Select the `Delete` key or choose **Delete Selected** \(![Delete Selected](../media/delete-icon.msft.png)\).</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-notes_os-delete-selected.msft.png" alt-text="删除键值对后对象存储的外观" lightbox="../media/storage-application-storage-indexeddb-notes_db-notes_os-delete-selected.msft.png":::
       <span data-ttu-id="ad78c-163">删除键值对后对象存储的外观</span><span class="sxs-lookup"><span data-stu-id="ad78c-163">How the object store looks after the key-value pair has been deleted</span></span>  
    :::image-end:::  
    
### <a name="delete-all-key-value-pairs-in-an-object-store"></a><span data-ttu-id="ad78c-164">删除对象存储中所有键值对</span><span class="sxs-lookup"><span data-stu-id="ad78c-164">Delete all key-value pairs in an object store</span></span>  

1.  <span data-ttu-id="ad78c-165">[查看 IndexedDB 对象存储](#view-indexeddb-data)。</span><span class="sxs-lookup"><span data-stu-id="ad78c-165">[View an IndexedDB object store](#view-indexeddb-data).</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-notes_os-clear-object-store.msft.png" alt-text="查看对象存储" lightbox="../media/storage-application-storage-indexeddb-notes_db-notes_os-clear-object-store.msft.png":::
       <span data-ttu-id="ad78c-167">查看对象存储</span><span class="sxs-lookup"><span data-stu-id="ad78c-167">View an object store</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="ad78c-168">选择“**清除对象存储**”\(“![清除对象存储](../media/clear-icon.msft.png)”\)。</span><span class="sxs-lookup"><span data-stu-id="ad78c-168">Choose **Clear object store** \(![Clear object store](../media/clear-icon.msft.png)\).</span></span>  
    
### <a name="delete-an-indexeddb-database"></a><span data-ttu-id="ad78c-169">删除 IndexedDB 数据库</span><span class="sxs-lookup"><span data-stu-id="ad78c-169">Delete an IndexedDB database</span></span>  

1.  <span data-ttu-id="ad78c-170">[查看要删除的 IndexedDB 数据库](#view-indexeddb-data)。</span><span class="sxs-lookup"><span data-stu-id="ad78c-170">[View the IndexedDB database](#view-indexeddb-data) that you want to delete.</span></span>  
1.  <span data-ttu-id="ad78c-171">选择“**删除数据库**”。</span><span class="sxs-lookup"><span data-stu-id="ad78c-171">Choose **Delete database**.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-delete-database.msft.png" alt-text="“删除数据库”按钮" lightbox="../media/storage-application-storage-indexeddb-notes_db-delete-database.msft.png":::
       <span data-ttu-id="ad78c-173">“**删除数据库**”按钮</span><span class="sxs-lookup"><span data-stu-id="ad78c-173">The **Delete database** button</span></span>  
    :::image-end:::  
    
### <a name="delete-all-indexeddb-storage"></a><span data-ttu-id="ad78c-174">删除所有 IndexedDB 存储</span><span class="sxs-lookup"><span data-stu-id="ad78c-174">Delete all IndexedDB storage</span></span>  

1.  <span data-ttu-id="ad78c-175">打开“**清除存储**”窗格。</span><span class="sxs-lookup"><span data-stu-id="ad78c-175">Open the **Clear storage** pane.</span></span>  
1.  <span data-ttu-id="ad78c-176">确保已启用 **IndexedDB** 复选框。</span><span class="sxs-lookup"><span data-stu-id="ad78c-176">Make sure that the **IndexedDB** checkbox is enabled.</span></span>  
1.  <span data-ttu-id="ad78c-177">选择“**清除网站数据**”。</span><span class="sxs-lookup"><span data-stu-id="ad78c-177">Choose **Clear site data**.</span></span>  
    
    :::image type="complex" source="../media/storage-application-clear-storage-indexeddb-clear-site-data.msft.png" alt-text="“清除存储”窗格" lightbox="../media/storage-application-clear-storage-indexeddb-clear-site-data.msft.png":::
       <span data-ttu-id="ad78c-179">“**清除存储**”窗格</span><span class="sxs-lookup"><span data-stu-id="ad78c-179">The **Clear storage** pane</span></span>  
    :::image-end:::  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="ad78c-180">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="ad78c-180">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 开发人员工具 | Microsoft Docs"  
[DevtoolsJavascriptSnippets]: ../javascript/snippets.md "使用 Microsoft Edge DevTools 在任意页面上运行 JavaScript 代码段 | Microsoft Docs"  

[ChromiumIssue943770]: https://crbug.com/943770 "943770 - DevTools:显示 iframe IndexedDB 数据库 - chromium - Monorail"  

[MDNBasicConceptsKeyGenerator]: https://developer.mozilla.org/docs/Web/API/IndexedDB_API/Basic_Concepts_Behind_IndexedDB#gloss_keygenerator "密钥生成器 - 基本概念 | MDN"  
[MDNIndexedDBAPI]: https://developer.mozilla.org/docs/Web/API/IndexedDB_API "IndexedDB API | MDN"  
[MDNUsingIndexedDB]: https://developer.mozilla.org/docs/Web/API/IndexedDB_API/Using_IndexedDB "使用 IndexedDB | MDN"  
[MDNUsingIndexedDBUsingIndex]: https://developer.mozilla.org/docs/Web/API/IndexedDB_API/Using_IndexedDB#Using_an_index "使用索引 - 使用 IndexedDB | MDN"  

> [!NOTE]
> <span data-ttu-id="ad78c-188">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="ad78c-188">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="ad78c-189">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/storage/indexeddb)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="ad78c-189">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/storage/indexeddb) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="ad78c-191">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="ad78c-191">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
