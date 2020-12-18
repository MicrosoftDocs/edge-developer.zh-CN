---
description: 如何使用本地存储窗格和控制台查看和编辑 localStorage。
title: 使用 Microsoft Edge DevTools 查看和编辑本地存储
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: c68f11b8ba2c10a0792f10acf5c5ededf2ad8e8d
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11231186"
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

# 使用 Microsoft Edge DevTools 查看和编辑本地存储  

本指南演示如何使用 [Microsoft Edge DevTools][MicrosoftEdgeDevTools] 查看、编辑和删除 [localStorage][MDNWindowsLocalStorage] 键值对。  

## 查看 localStorage 键和值  

1.  选择 **"应用程序"** 选项卡以打开 **应用程序** 工具。  默认情况下 **显示** 清单窗格。  
    
    :::image type="complex" source="../media/storage-application-manifest.msft.png" alt-text="清单窗格" lightbox="../media/storage-application-manifest.msft.png":::
       清单**窗格**  
    :::image-end:::  
    
1.  展开 **"本地存储"** 菜单。  
    
    :::image type="complex" source="../media/storage-application-local-storage.msft.png" alt-text=""本地存储"菜单" lightbox="../media/storage-application-local-storage.msft.png":::
       " **本地存储"** 菜单  
    :::image-end:::  
    
1.  选择一个域以查看键值对。  
    
    :::image type="complex" source="../media/storage-application-local-storage-view-key-value.msft.png" alt-text="域的 localStorage 键值 https://www.bing.com 对" lightbox="../media/storage-application-local-storage-view-key-value.msft.png":::
       `localStorage`域的键值 `https://www.bing.com` 对  
    :::image-end:::  
    
1.  选择表的一行以查看表下方的查看器中的值。  
    
    :::image type="complex" source="../media/storage-application-local-storage-view-key-value-selected.msft.png" alt-text="查看键eventLogQueue_Online值" lightbox="../media/storage-application-local-storage-view-key-value-selected.msft.png":::
       查看键 `eventLogQueue_Online` 的值  
    :::image-end:::  
    
## 创建新的 localStorage 键值对  

1.  [查看域的 localStorage 键值对](#view-localstorage-keys-and-values)。  
1.  双击表格的空部分。  DevTools 创建一个新行，并焦点在键列中 **的** 光标。  
    
    :::image type="complex" source="../media/storage-application-local-storage-new-key-value.msft.png" alt-text="要双击以创建新的键值对的表的空部分" lightbox="../media/storage-application-local-storage-new-key-value.msft.png":::
       要双击以创建新的键值对的表的空部分  
    :::image-end:::  
    
## 编辑 localStorage 键或值  

1.  [查看域的 localStorage 键值对](#view-localstorage-keys-and-values)。  
1.  双击"键"或"值****"**列中的单元格**以编辑该键或值。  
    
    :::image type="complex" source="../media/storage-application-local-storage-edit-key-value.msft.png" alt-text="编辑 localStorage 密钥" lightbox="../media/storage-application-local-storage-edit-key-value.msft.png":::
       编辑 `localStorage` 密钥  
    :::image-end:::  
    
## 删除 localStorage 键值对  

1.  [查看 `localStorage` 域的键值对](#view-localstorage-keys-and-values)。  
1.  选择要删除的键值对。  DevTools 突出显示蓝色以指示已选中。  
1.  Select the `Delete` key or choose Delete **Selected** \ (Delete ![ Selected ][ImageDeleteIcon] \) .  
    
## 删除 `localStorage` 域的所有键值对  

1.  [查看 `localStorage` 域的键值对](#view-localstorage-keys-and-values)。  
1.  Choose **Clear All** \ (Clear All ![ ][ImageClearIcon] \) .  
    
## 从控制台与 localStorage 交互  

由于可以在控制台中运行 JavaScript，并且**** 由于控制台可以访问页面的**** JavaScript 上下文，因此可以与控制台 `localStorage` **进行交互**。  

1.  如果要访问显示的页面外域的键值对，请使用**JavaScript**上下文菜单更改控制台的 JavaScript**** `localStorage` 上下文。  
    
    :::image type="complex" source="../media/storage-console-local-storage.msft.png" alt-text="更改控制台的 JavaScript 上下文" lightbox="../media/storage-console-local-storage.msft.png":::
       更改控制台的 JavaScript 上下文  
    :::image-end:::  
    
1.  在 `localStorage` 控制台中运行表达式，与在 JavaScript 中运行一样。  
    
    :::image type="complex" source="../media/storage-console-local-storage-interaction.msft.png" alt-text="从控制台与 localStorage 交互" lightbox="../media/storage-console-local-storage-interaction.msft.png":::
       从控制台 `localStorage` **进行交互**  
    :::image-end:::  
    
## 联系 Microsoft Edge DevTools 团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageClearIcon]: ../media/clear-icon.msft.png  
[ImageDeleteIcon]: ../media/delete-icon.msft.png  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 开发人员工具 |Microsoft Docs"  

[MDNWindowsLocalStorage]: https://developer.mozilla.org/docs/Web/API/Window/localStorage "Window.localStorage |MDN"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/storage/localstorage)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
