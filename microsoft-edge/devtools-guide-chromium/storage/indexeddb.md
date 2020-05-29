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





# 通过 Microsoft Edge DevTools 查看和更改 IndexedDB 数据   

  

本指南介绍如何使用[Microsoft Edge DevTools][MicrosoftEdgeDevTools]查看和更改[IndexedDB][MDNIndexedDBAPI]数据。  它假定你熟悉 DevTools。  它还假定你熟悉 IndexedDB。  如果不是，请参阅[使用 IndexedDB][MDNUsingIndexedDB]。  

## 查看 IndexedDB 数据   

1.  选择 "**应用程序**" 选项卡以打开 "**应用程序**" 面板。  默认情况下，**清单**窗格是默认打开的。  
    
    > ##### 图 1  
    > 清单窗格  
    > ![清单窗格][ImageManifest]  

1.  展开 " **IndexedDB** " 菜单以查看哪些数据库可用。  
    
    > ##### 图 2  
    > **IndexedDB**菜单  
    > ![IndexedDB 菜单][ImageIndexedDBMenu]  
    
    *   ![数据库图标 ][ImageDatabaseIcon] `notes - https://mdn.github.io` 表示数据库，其中 `notes` 是数据库的名称， `https://mdn.github.io` 是访问数据库的来源。  
    *   ![对象存储图标 ][ImageObjectStoreIcon] `notes` 是一个对象存储。  
    *   "**标题**" 和 "**正文**" 是[索引][MDNUsingIndexedDBUsingIndex]。  
    
    > [!NOTE]
    > **已知限制** 第三方数据库不可见。  例如，如果你使用将 `<iframe>` 广告嵌入到你的页面上，而你的广告网络使用 IndexedDB，则你的广告网络的 IndexedDB 数据将不可见。  请参阅[问题 #943770][ChromiumIssue943770]。  
    
1.  选择一个数据库以查看原始版本号和版本号。  
    
    > ##### 图 3  
    > **Notes**数据库  
    > ![Notes 数据库][ImageIndexedDBDatabase]  
    
1.  选择一个对象存储以查看键/值对。  
    
    > [!NOTE]
    > IndexedDB 数据不会实时更新。  请参阅[刷新 IndexedDB 数据](#refresh-indexeddb-data)。  
    
    > ##### 图 4  
    > **Notes**对象存储  
    > ![Notes 对象存储][ImageIndexedDBObjectStore]  

    *   **Total entries**指对象存储中的键值对的总数。  
    *   "**密钥生成器" 值**是下一个可用键。  此字段仅在使用[密钥生成器][MDNBasicConceptsKeyGenerator]时显示。  

1.  在 "**值**" 列中选择一个单元格以展开该值。  
    
    > ##### 图 5  
    > 查看 IndexedDB 值  
    > ![查看 IndexedDB 值][ImageIndexedBDValue]  
    
1.  选择[图](#figure-6)中的 "**标题**" 或 "**正文**" 等索引，以便根据该索引的值对对象存储进行排序。  
   
    > ##### 图 6  
    > 按**标题**键按字母顺序排序的对象存储  
    > ![按索引对对象存储进行排序][ImageIndexedDBIndex]  

## 刷新 IndexedDB 数据   

IndexedDB 不会实时更新**应用程序**面板中的值。  选择**Refresh** ![ ][ImageReloadIcon] "查看对象存储" 时刷新 "刷新" 以刷新数据，或查看数据库，然后单击 "**刷新数据库**" 以刷新所有数据。  

> ##### 图 7  
> 查看数据库  
> ![查看数据库][ImageIndexedDBDatabase2]  

## 编辑 IndexedDB 数据   

IndexedDB 键和值不能通过**应用程序**面板进行编辑。  但是，由于 DevTools 有权访问页面上下文，因此你可能会在 DevTools 内运行 JavaScript 代码以编辑 IndexedDB 数据。  

### 用代码段编辑 IndexedDB 数据   

[代码段][DevtoolsJavascriptSnippets]是在 DevTools 中存储和运行 JavaScript 代码块的一种方法。  运行代码段时，会将结果记录到**控制台**。  你可以使用代码段来运行 JavaScript 代码以编辑 IndexedDB 数据库。  

> ##### 图 8  
> 使用代码段与 IndexedDB 交互  
> ![使用代码段与 IndexedDB 交互][ImageIndexedDBSnippet]  

## 删除 IndexedDB 数据   

### 删除 IndexedDB 键值对   

1.  [查看 IndexedDB 对象存储](#view-indexeddb-data)。  
1.  选择要删除的键/值对。  DevTools 将突出显示它以指示它已选中。  
    
    > ##### 图 9  
    > 选择键/值对以删除它  
    > ![选择键/值对以删除它][ImageIndexedDBKeyValuePair]  

1.  按下 `Delete` 键或单击 "**删除**所选 ![ 删除" ][ImageDeleteIcon] 。  
    
    > ##### 图 10  
    > 删除键值对后，对象存储的外观  
    > ![删除键值对后，对象存储的外观][ImageIndexedDBKeyValuePairDeleted]  

### 删除对象存储中的所有键/值对   

1.  [查看 IndexedDB 对象存储](#view-indexeddb-data)。  
    
    > ##### 图 11  
    > 查看对象存储  
    > ![查看对象存储][ImageIndexedDBObjectStore]  

1.  选择 "**清除对象存储**" ![ 清除对象存储 ][ImageClearIcon] 。  

### 删除 IndexedDB 数据库   

1.  查看要删除的[IndexedDB 数据库](#view-indexeddb-data)。  
1.  选择 "**删除数据库**"。  
    
    > ##### 图 12  
    > "**删除数据库**" 按钮  
    > !["删除数据库" 按钮][ImageIndexedDBDatabase]  

### 删除所有 IndexedDB 存储   

1.  打开 "**清除存储**" 窗格。  

1.  确保已启用 " **IndexedDB** " 复选框。  

1.  选择 "**清除网站数据**"。  
    
    > ##### 图 13  
    > "清除**存储**" 窗格- ![ "清除存储" 窗格][ImageIndexedDBClearStorage]  

 



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
> 此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/storage/indexeddb)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools \ & Lighthouse \）创作。  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
