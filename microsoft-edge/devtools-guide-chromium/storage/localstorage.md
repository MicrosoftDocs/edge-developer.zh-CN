---
description: 如何通过 "本地存储" 窗格和控制台查看和编辑 localStorage。
title: 查看和编辑 Microsoft Edge DevTools 的本地存储
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: aa5365d1764ea0db537ea24464f9c76441f05322
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993553"
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



本指南介绍如何使用 [Microsoft Edge DevTools][MicrosoftEdgeDevTools] 查看、编辑和删除 [localStorage][MDNWindowsLocalStorage] 键值对。  

## 查看 localStorage 键和值   

1.  选择 " **应用程序** " 选项卡以打开 " **应用程序** " 面板。  默认显示 **清单** 窗格。  
    
    :::image type="complex" source="../media/storage-application-manifest.msft.png" alt-text="清单窗格" lightbox="../media/storage-application-manifest.msft.png":::
       **清单**窗格  
    :::image-end:::  
    
1.  展开 " **本地存储** " 菜单。  
    
    :::image type="complex" source="../media/storage-application-local-storage.msft.png" alt-text="清单窗格" lightbox="../media/storage-application-local-storage.msft.png":::
       **本地存储**菜单  
    :::image-end:::  
    
1.  选择一个域以查看键/值对。  
    
    :::image type="complex" source="../media/storage-application-local-storage-view-key-value.msft.png" alt-text="清单窗格" lightbox="../media/storage-application-local-storage-view-key-value.msft.png":::
       `localStorage`域的键/值对 `https://www.bing.com`  
    :::image-end:::  
    
1.  选择表中的一行以查看表下方的查看器中的值。  
    
    :::image type="complex" source="../media/storage-application-local-storage-view-key-value-selected.msft.png" alt-text="清单窗格" lightbox="../media/storage-application-local-storage-view-key-value-selected.msft.png":::
       查看键的值 `eventLogQueue_Online`  
    :::image-end:::  
    
## 创建新的 localStorage 键值对   

1.  [查看 `localStorage` 域的键/值对](#view-localstorage-keys-and-values)。  
1.  双击表格的空白部分。  DevTools 将创建一个新行，并将光标焦点放在 **键** 列中。  
    
    :::image type="complex" source="../media/storage-application-local-storage-new-key-value.msft.png" alt-text="清单窗格" lightbox="../media/storage-application-local-storage-new-key-value.msft.png":::
       要在其中创建新的键值对的表格的空部分，请双击该部分。  
    :::image-end:::  
    
## 编辑 localStorage 键或值   

1.  [查看 `localStorage` 域的键/值对](#view-localstorage-keys-and-values)。  
1.  双击 " **键** " 或 " **值** " 列中的一个单元格以编辑该注册表项或值。  
    
    :::image type="complex" source="../media/storage-application-local-storage-edit-key-value.msft.png" alt-text="清单窗格" lightbox="../media/storage-application-local-storage-edit-key-value.msft.png":::
       编辑 `localStorage` 密钥  
    :::image-end:::  
    
## 删除 localStorage 键值对   

1.  [查看 `localStorage` 域的键/值对](#view-localstorage-keys-and-values)。  
1.  选择要删除的键/值对。  DevTools 突出显示蓝色以指示它已选中。  
1.  按下 `Delete` 键或单击 " **删除所选** 项 \" (" ![ 删除所选项 ][ImageDeleteIcon] \ ) "。  
    
## 删除 `localStorage` 域的所有键/值对   

1.  [查看 `localStorage` 域的键/值对](#view-localstorage-keys-and-values)。  
1.  选择 **"全部清除** " (![ 全部清除 ][ImageClearIcon] \ ) 。  
    
## 从控制台与 localStorage 交互   

由于您能够在 **控制台**中运行 JavaScript，并且由于 **控制台** 有权访问页面的 JavaScript 上下文，因此可以 `localStorage` 从 **控制台**进行交互。  

1.  如果要访问显示的页面以外的域的键/值对，请使用 **JavaScript 上下文** 菜单更改 **控制台** 的 JavaScript 上下文 `localStorage` 。  
    
    :::image type="complex" source="../media/storage-console-local-storage.msft.png" alt-text="清单窗格" lightbox="../media/storage-console-local-storage.msft.png":::
       更改控制台的 JavaScript 上下文  
    :::image-end:::  
    
1.  `localStorage`在控制台中运行表达式，与在 JavaScript 中执行的操作相同。  
    
    :::image type="complex" source="../media/storage-console-local-storage-interaction.msft.png" alt-text="清单窗格" lightbox="../media/storage-console-local-storage-interaction.msft.png":::
       `localStorage`从**控制台**进行交互  
    :::image-end:::  
    
<!--  
 


-->  

<!-- image links -->  

[ImageClearIcon]: ../media/clear-icon.msft.png  
[ImageDeleteIcon]: ../media/delete-icon.msft.png  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) 开发工具 |Microsoft 文档"  

[MDNWindowsLocalStorage]: https://developer.mozilla.org/docs/Web/API/Window/localStorage "LocalStorage |MDN"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/storage/localstorage)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
