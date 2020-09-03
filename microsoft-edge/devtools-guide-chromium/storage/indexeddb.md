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





# 通过 Microsoft Edge DevTools 查看和更改 IndexedDB 数据   

  

本指南介绍如何使用 [Microsoft Edge DevTools][MicrosoftEdgeDevTools] 查看和更改 [IndexedDB][MDNIndexedDBAPI] 数据。  它假定你熟悉 DevTools。  它还假定你熟悉 IndexedDB。  如果不是，请参阅 [使用 IndexedDB][MDNUsingIndexedDB]。  

## 查看 IndexedDB 数据   

1.  选择 " **应用程序** " 选项卡以打开 " **应用程序** " 面板。  默认情况下， **清单** 窗格是默认打开的。  
    
    :::image type="complex" source="../media/storage-application-manifest-empty.msft.png" alt-text="清单窗格" lightbox="../media/storage-application-manifest-empty.msft.png":::
       **清单**窗格  
    :::image-end:::  
    
1.  展开 " **IndexedDB** " 菜单以查看哪些数据库可用。  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb.msft.png" alt-text="IndexedDB 菜单" lightbox="../media/storage-application-storage-indexeddb.msft.png":::
       **IndexedDB**菜单  
    :::image-end:::  
    
    *   \ (![ 数据库图标 ][ImageDatabaseIcon] \ ) `notes - https://mdn.github.io` 表示数据库，其中 `notes` 是数据库的名称， `https://mdn.github.io` 是访问数据库的来源。  
    *   \ (![ 对象存储图标 ][ImageObjectStoreIcon] \ ) `notes` 是对象存储。  
    *   "**标题**" 和 "**正文**" 是[索引][MDNUsingIndexedDBUsingIndex]。  
    
    > [!NOTE]
    > **已知限制**  第三方数据库不可见。  例如，如果你使用将 `<iframe>` 广告嵌入到你的页面上，而你的广告网络使用 IndexedDB，则你的广告网络的 IndexedDB 数据将不可见。  请参阅 [问题 #943770][ChromiumIssue943770]。  
    
1.  选择一个数据库以查看原始版本号和版本号。  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db.msft.png" alt-text="Notes 数据库" lightbox="../media/storage-application-storage-indexeddb-notes_db.msft.png":::
       **Notes**数据库  
    :::image-end:::  
    
1.  选择一个对象存储以查看键/值对。  
    
    > [!NOTE]
    > IndexedDB 数据不会实时更新。  请参阅 [刷新 IndexedDB 数据](#refresh-indexeddb-data)。  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-notes_os.msft.png" alt-text="Notes 对象存储" lightbox="../media/storage-application-storage-indexeddb-notes_db-notes_os.msft.png":::
       **Notes**对象存储  
    :::image-end:::  
    
    *   **Total entries** 指对象存储中的键值对的总数。  
    *   "**密钥生成器" 值**是下一个可用键。  此字段仅在使用 [密钥生成器][MDNBasicConceptsKeyGenerator]时显示。  
    
1.  在 " **值** " 列中选择一个单元格以展开该值。  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-notes_os-edge-chromium.msft.png" alt-text="查看 IndexedDB 值" lightbox="../media/storage-application-storage-indexeddb-notes_db-notes_os-edge-chromium.msft.png":::
       查看 **IndexedDB** 值  
    :::image-end:::  
    
1.  选择下图中的 " **标题** " 或 " **正文** " 等索引，以便根据该索引的值对对象存储进行排序。  
   
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-notes_os-title.msft.png" alt-text="按索引对对象存储进行排序" lightbox="../media/storage-application-storage-indexeddb-notes_db-notes_os-title.msft.png":::
       按索引对对象存储进行排序  
    :::image-end:::  
    
## 刷新 IndexedDB 数据   

IndexedDB 不会实时更新 **应用程序** 面板中的值。  选择 " **刷新** \ (![ 刷新 ][ImageReloadIcon] \ ) 查看对象存储以刷新数据，或查看数据库，然后单击" **刷新数据库** "以刷新所有数据。  

:::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-notes_os-refresh-database.msft.png" alt-text="查看数据库" lightbox="../media/storage-application-storage-indexeddb-notes_db-notes_os-refresh-database.msft.png":::
   查看数据库  
:::image-end:::  

## 编辑 IndexedDB 数据   

IndexedDB 键和值不能通过 **应用程序** 面板进行编辑。  但是，由于 DevTools 有权访问页面上下文，因此你可能会在 DevTools 内运行 JavaScript 代码以编辑 IndexedDB 数据。  

### 用代码段编辑 IndexedDB 数据   

[代码段][DevtoolsJavascriptSnippets] 是在 DevTools 中存储和运行 JavaScript 代码块的一种方法。  运行代码段时，会将结果记录到 **控制台**。  你可以使用代码段来运行 JavaScript 代码以编辑 IndexedDB 数据库。  

:::image type="complex" source="../media/storage-sources-snippets-indexeddb-output.msft.png" alt-text="使用代码段与 IndexedDB 交互" lightbox="../media/storage-sources-snippets-indexeddb-output.msft.png":::
   使用代码段与 IndexedDB 交互  
:::image-end:::  

## 删除 IndexedDB 数据   

### 删除 IndexedDB 键值对   

1.  [查看 IndexedDB 对象存储](#view-indexeddb-data)。  
1.  选择要删除的键/值对。  DevTools 将突出显示它以指示它已选中。  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-notes_os2.msft.png" alt-text="选择一个键/值对以删除它" lightbox="../media/storage-application-storage-indexeddb-notes_db-notes_os2.msft.png":::
       选择一个键/值对以删除它  
    :::image-end:::  
    
1.  按下 `Delete` 键或单击 " **删除所选** 项 \" (" ![ 删除所选项 ][ImageDeleteIcon] \ ) "。  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-notes_os-delete-selected.msft.png" alt-text="删除键值对后，对象存储的外观" lightbox="../media/storage-application-storage-indexeddb-notes_db-notes_os-delete-selected.msft.png":::
       删除键值对后，对象存储的外观  
    :::image-end:::  
    
### 删除对象存储中的所有键/值对   

1.  [查看 IndexedDB 对象存储](#view-indexeddb-data)。  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-notes_os-clear-object-store.msft.png" alt-text="查看对象存储" lightbox="../media/storage-application-storage-indexeddb-notes_db-notes_os-clear-object-store.msft.png":::
       查看对象存储  
    :::image-end:::  
    
1.  选择 " **清除对象存储** \ (![ 清除对象存储 ][ImageClearIcon] \ ) "。  
    
### 删除 IndexedDB 数据库   

1.  查看要删除的[IndexedDB 数据库](#view-indexeddb-data)。  
1.  选择 " **删除数据库**"。  
    
    :::image type="complex" source="../media/storage-application-storage-indexeddb-notes_db-delete-database.msft.png" alt-text=""删除数据库" 按钮" lightbox="../media/storage-application-storage-indexeddb-notes_db-delete-database.msft.png":::
       " **删除数据库** " 按钮  
    :::image-end:::  
    
### 删除所有 IndexedDB 存储   

1.  打开 " **清除存储** " 窗格。  
1.  确保已启用 " **IndexedDB** " 复选框。  
1.  选择 " **清除网站数据**"。  
    
    :::image type="complex" source="../media/storage-application-clear-storage-indexeddb-clear-site-data.msft.png" alt-text=""清除存储" 窗格" lightbox="../media/storage-application-clear-storage-indexeddb-clear-site-data.msft.png":::
       " **清除存储** " 窗格  
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
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/storage/indexeddb)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
