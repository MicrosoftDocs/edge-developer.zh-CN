---
description: 如何通过应用程序面板和代码段查看和更改 IndexedDB 数据。
title: 通过 Microsoft Edge DevTools 查看和更改 IndexedDB 数据
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 6b1209ddcbfac305535d9d61e001441dbf61b6ec
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993560"
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





# <span data-ttu-id="f15ab-104">通过 Microsoft Edge DevTools 查看和更改 IndexedDB 数据</span><span class="sxs-lookup"><span data-stu-id="f15ab-104">View and change IndexedDB data with Microsoft Edge DevTools</span></span>   

  

<span data-ttu-id="f15ab-105">本指南介绍如何使用 [Microsoft Edge DevTools][MicrosoftEdgeDevTools] 查看和更改 [IndexedDB][MDNIndexedDBAPI] 数据。</span><span class="sxs-lookup"><span data-stu-id="f15ab-105">This guide shows you how to use [Microsoft Edge DevTools][MicrosoftEdgeDevTools] to view and change [IndexedDB][MDNIndexedDBAPI] data.</span></span>  <span data-ttu-id="f15ab-106">它假定你熟悉 DevTools。</span><span class="sxs-lookup"><span data-stu-id="f15ab-106">It assumes you are familiar with DevTools.</span></span>  <span data-ttu-id="f15ab-107">它还假定你熟悉 IndexedDB。</span><span class="sxs-lookup"><span data-stu-id="f15ab-107">It also assumes you are familiar with IndexedDB.</span></span>  <span data-ttu-id="f15ab-108">如果不是，请参阅 [使用 IndexedDB][MDNUsingIndexedDB]。</span><span class="sxs-lookup"><span data-stu-id="f15ab-108">If not, see [Using IndexedDB][MDNUsingIndexedDB].</span></span>  

## <span data-ttu-id="f15ab-109">查看 IndexedDB 数据</span><span class="sxs-lookup"><span data-stu-id="f15ab-109">View IndexedDB data</span></span>   

1.  <span data-ttu-id="f15ab-110">选择 " **应用程序** " 选项卡以打开 " **应用程序** " 面板。</span><span class="sxs-lookup"><span data-stu-id="f15ab-110">Select the **Application** tab to open the **Application** panel.</span></span>  <span data-ttu-id="f15ab-111">默认情况下， **清单** 窗格是默认打开的。</span><span class="sxs-lookup"><span data-stu-id="f15ab-111">The **Manifest** pane usually opens by default.</span></span>  
    
    :::image type="complex" source="../media/storage-application-manifest-empty.msft.png" alt-text="清单窗格" lightbox="../media/storage-application-manifest-empty.msft.png":::
       <span data-ttu-id="f15ab-113">**清单**窗格</span><span class="sxs-lookup"><span data-stu-id="f15ab-113">The **Manifest** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="f15ab-114">展开 " **IndexedDB** " 菜单以查看哪些数据库可用。</span><span class="sxs-lookup"><span data-stu-id="f15ab-114">Expand the **IndexedDB** menu to see which databases are available.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb.msft.png" alt-text="清单窗格" lightbox="../media/storage-application-storage-indexeddb.msft.png":::
       <span data-ttu-id="f15ab-116">**IndexedDB**菜单</span><span class="sxs-lookup"><span data-stu-id="f15ab-116">The **IndexedDB** menu</span></span>  
    :::image-end:::  
    
    *   <span data-ttu-id="f15ab-117">\ (![ 数据库图标 ][ImageDatabaseIcon] \ ) `notes - https://mdn.github.io` 表示数据库，其中 `notes` 是数据库的名称， `https://mdn.github.io` 是访问数据库的来源。</span><span class="sxs-lookup"><span data-stu-id="f15ab-117">\(![Database icon][ImageDatabaseIcon]\) `notes - https://mdn.github.io` represents a database, where `notes` is the name of the database and `https://mdn.github.io` is the origin that accesses the database.</span></span>  
    *   <span data-ttu-id="f15ab-118">\ (![ 对象存储图标 ][ImageObjectStoreIcon] \ ) `notes` 是对象存储。</span><span class="sxs-lookup"><span data-stu-id="f15ab-118">\(![Object Store icon][ImageObjectStoreIcon]\) `notes` is an object store.</span></span>  
    *   <span data-ttu-id="f15ab-119">"**标题**" 和 "**正文**" 是[索引][MDNUsingIndexedDBUsingIndex]。</span><span class="sxs-lookup"><span data-stu-id="f15ab-119">**title** and **body** are [indexes][MDNUsingIndexedDBUsingIndex].</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="f15ab-120">**已知限制**  第三方数据库不可见。</span><span class="sxs-lookup"><span data-stu-id="f15ab-120">**Known Limitation**  Third-party databases are not visible.</span></span>  <span data-ttu-id="f15ab-121">例如，如果你使用将 `<iframe>` 广告嵌入到你的页面上，而你的广告网络使用 IndexedDB，则你的广告网络的 IndexedDB 数据将不可见。</span><span class="sxs-lookup"><span data-stu-id="f15ab-121">For example, if you use an `<iframe>` to embed an ad on your page, and your ad network uses IndexedDB, the IndexedDB data for your ad network is not be visible.</span></span>  <span data-ttu-id="f15ab-122">请参阅 [问题 #943770][ChromiumIssue943770]。</span><span class="sxs-lookup"><span data-stu-id="f15ab-122">See [issue #943770][ChromiumIssue943770].</span></span>  
    
1.  <span data-ttu-id="f15ab-123">选择一个数据库以查看原始版本号和版本号。</span><span class="sxs-lookup"><span data-stu-id="f15ab-123">Select a database to see the origin and version number.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db.msft.png" alt-text="清单窗格" lightbox="../media/storage-application-storage-indexeddb-notes_db.msft.png":::
       <span data-ttu-id="f15ab-125">**Notes**数据库</span><span class="sxs-lookup"><span data-stu-id="f15ab-125">The **notes** database</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="f15ab-126">选择一个对象存储以查看键/值对。</span><span class="sxs-lookup"><span data-stu-id="f15ab-126">Select an object store to see the key-value pairs.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="f15ab-127">IndexedDB 数据不会实时更新。</span><span class="sxs-lookup"><span data-stu-id="f15ab-127">IndexedDB data does not update in real-time.</span></span>  <span data-ttu-id="f15ab-128">请参阅 [刷新 IndexedDB 数据](#refresh-indexeddb-data)。</span><span class="sxs-lookup"><span data-stu-id="f15ab-128">See [Refresh IndexedDB data](#refresh-indexeddb-data).</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-notes_os.msft.png" alt-text="清单窗格" lightbox="../media/storage-application-storage-indexeddb-notes_db-notes_os.msft.png":::
       <span data-ttu-id="f15ab-130">**Notes**对象存储</span><span class="sxs-lookup"><span data-stu-id="f15ab-130">The **notes** object store</span></span>  
    :::image-end:::  
    
    *   <span data-ttu-id="f15ab-131">**Total entries** 指对象存储中的键值对的总数。</span><span class="sxs-lookup"><span data-stu-id="f15ab-131">**Total entries** is the total number of key-value pairs in the object store.</span></span>  
    *   <span data-ttu-id="f15ab-132">"**密钥生成器" 值**是下一个可用键。</span><span class="sxs-lookup"><span data-stu-id="f15ab-132">**Key generator value** is the next available key.</span></span>  <span data-ttu-id="f15ab-133">此字段仅在使用 [密钥生成器][MDNBasicConceptsKeyGenerator]时显示。</span><span class="sxs-lookup"><span data-stu-id="f15ab-133">This field is only shown when using [key generators][MDNBasicConceptsKeyGenerator].</span></span>  
    
1.  <span data-ttu-id="f15ab-134">在 " **值** " 列中选择一个单元格以展开该值。</span><span class="sxs-lookup"><span data-stu-id="f15ab-134">Select a cell in the **Value** column to expand that value.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-notes_os-edge-chromium.msft.png" alt-text="清单窗格" lightbox="../media/storage-application-storage-indexeddb-notes_db-notes_os-edge-chromium.msft.png":::
       <span data-ttu-id="f15ab-136">查看 **IndexedDB** 值</span><span class="sxs-lookup"><span data-stu-id="f15ab-136">View an **IndexedDB** value</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="f15ab-137">选择下图中的 " **标题** " 或 " **正文** " 等索引，以便根据该索引的值对对象存储进行排序。</span><span class="sxs-lookup"><span data-stu-id="f15ab-137">Select an index, such as **title** or **body** in the following figure, to sort the object store according to the values of that index.</span></span>  
   
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-notes_os-title.msft.png" alt-text="清单窗格" lightbox="../media/storage-application-storage-indexeddb-notes_db-notes_os-title.msft.png":::
       <span data-ttu-id="f15ab-139">按索引对对象存储进行排序</span><span class="sxs-lookup"><span data-stu-id="f15ab-139">Sort an object store by an index</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="f15ab-140">刷新 IndexedDB 数据</span><span class="sxs-lookup"><span data-stu-id="f15ab-140">Refresh IndexedDB data</span></span>   

<span data-ttu-id="f15ab-141">IndexedDB 不会实时更新 **应用程序** 面板中的值。</span><span class="sxs-lookup"><span data-stu-id="f15ab-141">IndexedDB values in the **Application** panel do not update in real-time.</span></span>  <span data-ttu-id="f15ab-142">选择 " **刷新** \ (![ 刷新 ][ImageReloadIcon] \ ) 查看对象存储以刷新数据，或查看数据库，然后单击" **刷新数据库** "以刷新所有数据。</span><span class="sxs-lookup"><span data-stu-id="f15ab-142">Select **Refresh** \(![Refresh][ImageReloadIcon]\) when viewing an object store to refresh the data, or view a database and click **Refresh database** to refresh all data.</span></span>  

:::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-notes_os-refresh-database.msft.png" alt-text="清单窗格" lightbox="../media/storage-application-storage-indexeddb-notes_db-notes_os-refresh-database.msft.png":::
   <span data-ttu-id="f15ab-144">查看数据库</span><span class="sxs-lookup"><span data-stu-id="f15ab-144">View a database</span></span>  
:::image-end:::  

## <span data-ttu-id="f15ab-145">编辑 IndexedDB 数据</span><span class="sxs-lookup"><span data-stu-id="f15ab-145">Edit IndexedDB data</span></span>   

<span data-ttu-id="f15ab-146">IndexedDB 键和值不能通过 **应用程序** 面板进行编辑。</span><span class="sxs-lookup"><span data-stu-id="f15ab-146">IndexedDB keys and values are not editable from the **Application** panel.</span></span>  <span data-ttu-id="f15ab-147">但是，由于 DevTools 有权访问页面上下文，因此你可能会在 DevTools 内运行 JavaScript 代码以编辑 IndexedDB 数据。</span><span class="sxs-lookup"><span data-stu-id="f15ab-147">Since DevTools has access to page context, however, you may run JavaScript code within DevTools to edit IndexedDB data.</span></span>  

### <span data-ttu-id="f15ab-148">用代码段编辑 IndexedDB 数据</span><span class="sxs-lookup"><span data-stu-id="f15ab-148">Edit IndexedDB data with Snippets</span></span>   

<span data-ttu-id="f15ab-149">[代码段][DevtoolsJavascriptSnippets] 是在 DevTools 中存储和运行 JavaScript 代码块的一种方法。</span><span class="sxs-lookup"><span data-stu-id="f15ab-149">[Snippets][DevtoolsJavascriptSnippets] are a way to store and run blocks of JavaScript code within DevTools.</span></span>  <span data-ttu-id="f15ab-150">运行代码段时，会将结果记录到 **控制台**。</span><span class="sxs-lookup"><span data-stu-id="f15ab-150">When you run a Snippet, the result is logged to the **Console**.</span></span>  <span data-ttu-id="f15ab-151">你可以使用代码段来运行 JavaScript 代码以编辑 IndexedDB 数据库。</span><span class="sxs-lookup"><span data-stu-id="f15ab-151">You may use a Snippet to run JavaScript code to edit an IndexedDB database.</span></span>  

:::image type="complex" source="../media/storage-sources-snippets-indexeddb-output.msft.png" alt-text="清单窗格" lightbox="../media/storage-sources-snippets-indexeddb-output.msft.png":::
   <span data-ttu-id="f15ab-153">使用代码段与 IndexedDB 交互</span><span class="sxs-lookup"><span data-stu-id="f15ab-153">Use a Snippet to interact with IndexedDB</span></span>  
:::image-end:::  

## <span data-ttu-id="f15ab-154">删除 IndexedDB 数据</span><span class="sxs-lookup"><span data-stu-id="f15ab-154">Delete IndexedDB data</span></span>   

### <span data-ttu-id="f15ab-155">删除 IndexedDB 键值对</span><span class="sxs-lookup"><span data-stu-id="f15ab-155">Delete an IndexedDB key-value pair</span></span>   

1.  <span data-ttu-id="f15ab-156">[查看 IndexedDB 对象存储](#view-indexeddb-data)。</span><span class="sxs-lookup"><span data-stu-id="f15ab-156">[View an IndexedDB object store](#view-indexeddb-data).</span></span>  
1.  <span data-ttu-id="f15ab-157">选择要删除的键/值对。</span><span class="sxs-lookup"><span data-stu-id="f15ab-157">Select the key-value pair that you want to delete.</span></span>  <span data-ttu-id="f15ab-158">DevTools 将突出显示它以指示它已选中。</span><span class="sxs-lookup"><span data-stu-id="f15ab-158">DevTools highlights it to indicate that it is selected.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-notes_os2.msft.png" alt-text="清单窗格" lightbox="../media/storage-application-storage-indexeddb-notes_db-notes_os2.msft.png":::
       <span data-ttu-id="f15ab-160">选择一个键/值对以删除它</span><span class="sxs-lookup"><span data-stu-id="f15ab-160">Select a key-value pair in order to delete it</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="f15ab-161">按下 `Delete` 键或单击 " **删除所选** 项 \" (" ![ 删除所选项 ][ImageDeleteIcon] \ ) "。</span><span class="sxs-lookup"><span data-stu-id="f15ab-161">Press the `Delete` key or click **Delete Selected** \(![Delete Selected][ImageDeleteIcon]\).</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-notes_os-delete-selected.msft.png" alt-text="清单窗格" lightbox="../media/storage-application-storage-indexeddb-notes_db-notes_os-delete-selected.msft.png":::
       <span data-ttu-id="f15ab-163">删除键值对后，对象存储的外观</span><span class="sxs-lookup"><span data-stu-id="f15ab-163">How the object store looks after the key-value pair has been deleted</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="f15ab-164">删除对象存储中的所有键/值对</span><span class="sxs-lookup"><span data-stu-id="f15ab-164">Delete all key-value pairs in an object store</span></span>   

1.  <span data-ttu-id="f15ab-165">[查看 IndexedDB 对象存储](#view-indexeddb-data)。</span><span class="sxs-lookup"><span data-stu-id="f15ab-165">[View an IndexedDB object store](#view-indexeddb-data).</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-notes_os-clear-object-store.msft.png" alt-text="清单窗格" lightbox="../media/storage-application-storage-indexeddb-notes_db-notes_os-clear-object-store.msft.png":::
       <span data-ttu-id="f15ab-167">查看对象存储</span><span class="sxs-lookup"><span data-stu-id="f15ab-167">View an object store</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="f15ab-168">选择 " **清除对象存储** \ (![ 清除对象存储 ][ImageClearIcon] \ ) "。</span><span class="sxs-lookup"><span data-stu-id="f15ab-168">Select **Clear object store** \(![Clear object store][ImageClearIcon]\).</span></span>  
    
### <span data-ttu-id="f15ab-169">删除 IndexedDB 数据库</span><span class="sxs-lookup"><span data-stu-id="f15ab-169">Delete an IndexedDB database</span></span>   

1.  <span data-ttu-id="f15ab-170">查看要删除的[IndexedDB 数据库](#view-indexeddb-data)。</span><span class="sxs-lookup"><span data-stu-id="f15ab-170">[View the IndexedDB database](#view-indexeddb-data) that you want to delete.</span></span>  
1.  <span data-ttu-id="f15ab-171">选择 " **删除数据库**"。</span><span class="sxs-lookup"><span data-stu-id="f15ab-171">Select **Delete database**.</span></span>  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-delete-database.msft.png" alt-text="清单窗格" lightbox="../media/storage-application-storage-indexeddb-notes_db-delete-database.msft.png":::
       <span data-ttu-id="f15ab-173">" **删除数据库** " 按钮</span><span class="sxs-lookup"><span data-stu-id="f15ab-173">The **Delete database** button</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="f15ab-174">删除所有 IndexedDB 存储</span><span class="sxs-lookup"><span data-stu-id="f15ab-174">Delete all IndexedDB storage</span></span>   

1.  <span data-ttu-id="f15ab-175">打开 " **清除存储** " 窗格。</span><span class="sxs-lookup"><span data-stu-id="f15ab-175">Open the **Clear storage** pane.</span></span>  
1.  <span data-ttu-id="f15ab-176">确保已启用 " **IndexedDB** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="f15ab-176">Make sure that the **IndexedDB** checkbox is enabled.</span></span>  
1.  <span data-ttu-id="f15ab-177">选择 " **清除网站数据**"。</span><span class="sxs-lookup"><span data-stu-id="f15ab-177">Select **Clear site data**.</span></span>  
    
    :::image type="complex" source="../media/storage-application-clear-storage-indexeddb-clear-site-data.msft.png" alt-text="清单窗格" lightbox="../media/storage-application-clear-storage-indexeddb-clear-site-data.msft.png":::
       <span data-ttu-id="f15ab-179">" **清除存储** " 窗格</span><span class="sxs-lookup"><span data-stu-id="f15ab-179">The **Clear storage** pane</span></span>  
    :::image-end:::  
    
<!--  
 


-->  

<!-- image links -->  

[ImageClearIcon]: ../media/clear-icon.msft.png  
[ImageDatabaseIcon]: ../media/database-icon.msft.png  
[ImageDeleteIcon]: ../media/delete-icon.msft.png  
[ImageObjectStoreIcon]: ../media/object-store-icon.msft.png  
[ImageReloadIcon]: ../media/reload-icon.msft.png  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) 开发工具 |Microsoft 文档"  
[DevtoolsJavascriptSnippets]: ../javascript/snippets.md "在具有 Microsoft Edge DevTools 的任何页面上运行 JavaScript 片段 |Microsoft 文档"  

[ChromiumIssue943770]: https://crbug.com/943770 "943770-DevTools： Show iframe IndexedDB 数据库-chromium-Monorail"  

[MDNBasicConceptsKeyGenerator]: https://developer.mozilla.org/docs/Web/API/IndexedDB_API/Basic_Concepts_Behind_IndexedDB#gloss_keygenerator "密钥生成器-基本概念 |MDN"  
[MDNIndexedDBAPI]: https://developer.mozilla.org/docs/Web/API/IndexedDB_API "IndexedDB API |MDN"  
[MDNUsingIndexedDB]: https://developer.mozilla.org/docs/Web/API/IndexedDB_API/Using_IndexedDB "使用 IndexedDB |MDN"  
[MDNUsingIndexedDBUsingIndex]: https://developer.mozilla.org/docs/Web/API/IndexedDB_API/Using_IndexedDB#Using_an_index "使用索引-使用 IndexedDB |MDN"  

> [!NOTE]
> <span data-ttu-id="f15ab-187">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="f15ab-187">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="f15ab-188">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/storage/indexeddb)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="f15ab-188">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/storage/indexeddb) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="f15ab-190">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="f15ab-190">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
