---
title: 查看和编辑 Microsoft Edge DevTools 的本地存储
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/30/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: f7e187662aec8231f2cc4e99baab1b4b8e2048ad
ms.sourcegitcommit: ad68bfbb355f6cfdaaf6612b77ea3985d4d6a58b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/01/2020
ms.locfileid: "10612009"
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





# 查看和编辑 Microsoft Edge DevTools 的本地存储   



本指南介绍如何使用[Microsoft Edge DevTools][MicrosoftEdgeDevTools]查看、编辑和删除 [`localStorage`][MDNWindowsLocalStorage] 键值对。  

## 查看 localStorage 键和值   

1.  选择 "**应用程序**" 选项卡以打开 "**应用程序**" 面板。  默认显示**清单**窗格。  
    
    > ##### 图 1  
    > 清单窗格  
    > ![清单窗格][ImageManifest]  

1.  展开 "**本地存储**" 菜单。  
    
    > ##### 图 2  
    > "**本地存储**" 菜单显示两个域： `https://business.bing.com` 和 `https://www.bing.com`  
    > ![本地存储菜单][ImageLocalStorageMenu]  

1.  选择一个域以查看键/值对。  
    
    > ##### 图 3  
    > `localStorage`域的键/值对 `https://www.bing.com`  
    > ![域的 localStorage 键值对 https://www.bing.com][ImageLocalStorage]  

1.  选择表中的一行以查看表下方的查看器中的值。  
    
    > ##### 图 4  
    > 查看键的值 `eventLogQueue_Online`  
    > ![查看 eventLogQueue_Online 项的值][ImageLocalStorageViewer]  

## 创建新的 `localStorage` 键/值对   

1.  [查看 `localStorage` 域的键/值对](#view-localstorage-keys-and-values)。  
1.  双击表格的空白部分。  DevTools 将创建一个新行，并将光标焦点放在**键**列中。  
    
    > ##### 图 5  
    > 要在其中创建新的键值对的表格的空部分，请双击该部分。  
    > ![要在其中创建新的键值对的表格的空部分，请双击该部分。][ImageLocalStorageCreate]  

## 编辑 `localStorage` 键或值   

1.  [查看 `localStorage` 域的键/值对](#view-localstorage-keys-and-values)。  
1.  双击 "**键**" 或 "**值**" 列中的一个单元格以编辑该注册表项或值。  
    
    > ##### 图 6  
    > 编辑 `localStorage` 密钥  
    > ![编辑 localStorage 键][ImageLocalStorageEdit]  

## 删除 `localStorage` 键值对   

1.  [查看 `localStorage` 域的键/值对](#view-localstorage-keys-and-values)。  
1.  选择要删除的键/值对。  DevTools 突出显示蓝色以指示它已选中。  

1.  按下 `Delete` 键或单击 "**删除**所选 ![ 删除" ][ImageDeleteIcon] 。  

## 删除 `localStorage` 域的所有键/值对   

1.  [查看 `localStorage` 域的键/值对](#view-localstorage-keys-and-values)。  

1.  选择 "**全部**清除" ![ ][ImageClearIcon] 。  

## `localStorage`从控制台进行交互   

由于您能够在**控制台**中运行 JavaScript，并且由于**控制台**有权访问页面的 JavaScript 上下文，因此可以 `localStorage` 从**控制台**进行交互。  

1.  如果要访问显示的页面以外的域的键/值对，请使用**JavaScript 上下文**菜单更改**控制台**的 JavaScript 上下文 `localStorage` 。  
    
    > ##### 图 7  
    > 更改**控制台**的 JavaScript 上下文  
    > ![更改控制台的 JavaScript 上下文][ImageJSContext]  

1.  `localStorage`在控制台中运行表达式，与在 JavaScript 中执行的操作相同。  
    
    > ##### 图 8  
    > `localStorage`从**控制台**进行交互  
    > ![从控制台与 localStorage 交互][ImageLocalStorageConsole]  

 



<!-- image links -->  

[ImageClearIcon]: /microsoft-edge/devtools-guide-chromium/media/clear-icon.msft.png  
[ImageDeleteIcon]: /microsoft-edge/devtools-guide-chromium/media/delete-icon.msft.png  

[ImageManifest]: /microsoft-edge/devtools-guide-chromium/media/storage-application-manifest.msft.png "图1：清单窗格"  
[ImageLocalStorageMenu]: /microsoft-edge/devtools-guide-chromium/media/storage-application-local-storage.msft.png "图2：本地存储菜单"  
[ImageLocalStorage]: /microsoft-edge/devtools-guide-chromium/media/storage-application-local-storage-view-key-value.msft.png "图3：域的 localStorage 键值对 https://www.bing.com"  
[ImageLocalStorageViewer]: /microsoft-edge/devtools-guide-chromium/media/storage-application-local-storage-view-key-value-selected.msft.png "图4：查看 eventLogQueue_Online 项的值"  
[ImageLocalStorageCreate]: /microsoft-edge/devtools-guide-chromium/media/storage-application-local-storage-new-key-value.msft.png "图5：要双击的表格的空部分，以便创建新的键值对"  
[ImageLocalStorageEdit]: /microsoft-edge/devtools-guide-chromium/media/storage-application-local-storage-edit-key-value.msft.png "图6：编辑 localStorage 键"  
[ImageJSContext]: /microsoft-edge/devtools-guide-chromium/media/storage-console-local-storage.msft.png "图7：更改控制台的 JavaScript 上下文"  
[ImageLocalStorageConsole]: /microsoft-edge/devtools-guide-chromium/media/storage-console-local-storage-interaction.msft.png "图8：从控制台与 localStorage 交互"  

<!-- links -->  

[MicrosoftEdgeDevTools]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge （Chromium）开发人员工具"  

[MDNWindowsLocalStorage]: https://developer.mozilla.org/docs/Web/API/Window/localStorage "LocalStorage |MDN"  

> [!NOTE]
> 此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/storage/localstorage)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools \ & Lighthouse \）创作。  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
