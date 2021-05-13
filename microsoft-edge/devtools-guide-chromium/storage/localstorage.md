---
description: 如何使用“本地存储”窗格和控制台查看和编辑 localStorage。
title: 使用 Microsoft Edge DevTools 查看和编辑本地存储
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge，web 开发，f12 工具，devtools
ms.openlocfilehash: 5088a1b9d7ab2b92051d099e76b8b07bbd5db5f8
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2021
ms.locfileid: "11565048"
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
# <a name="view-and-edit-local-storage-with-microsoft-edge-devtools"></a>使用 Microsoft Edge DevTools 查看和编辑本地存储  

本指南演示如何使用 [Microsoft Edge DevTools][MicrosoftEdgeDevTools] 查看、编辑和删除 [localStorage][MDNWindowsLocalStorage] 键值对。  

## <a name="view-localstorage-keys-and-values"></a>查看 localStorage 键和值  

1.  选择“**应用程序**”选项卡以打开“**应用程序**”工具。  “**清单**”窗格默认显示。  
    
    :::image type="complex" source="../media/storage-application-manifest.msft.png" alt-text="“清单”窗格" lightbox="../media/storage-application-manifest.msft.png":::
       “**清单**”窗格  
    :::image-end:::  
    
1.  展开“**本地存储**”菜单。  
    
    :::image type="complex" source="../media/storage-application-local-storage.msft.png" alt-text="“本地存储”菜单" lightbox="../media/storage-application-local-storage.msft.png":::
       “**本地存储**”菜单  
    :::image-end:::  
    
1.  选择域以查看键值对。  
    
    :::image type="complex" source="../media/storage-application-local-storage-view-key-value.msft.png" alt-text="https://www.bing.com域的 localStorage 键值对" lightbox="../media/storage-application-local-storage-view-key-value.msft.png":::
       `https://www.bing.com`域的`localStorage`键值对  
    :::image-end:::  
    
1.  选择表的行以查看该表下方查看器中的值。  
    
    :::image type="complex" source="../media/storage-application-local-storage-view-key-value-selected.msft.png" alt-text="查看 eventLogQueue_Online 键的值" lightbox="../media/storage-application-local-storage-view-key-value-selected.msft.png":::
       查看`eventLogQueue_Online`键的值  
    :::image-end:::  
    
## <a name="create-a-new-localstorage-key-value-pair"></a>创建新的 localStorage 键值对  

1.  [查看域的 localStorage 键值对](#view-localstorage-keys-and-values)。  
1.  双击表的空白部分。  DevTools 将新建行，并将光标停留在**键**列。  
    
    :::image type="complex" source="../media/storage-application-local-storage-new-key-value.msft.png" alt-text="为了新建键值对要双击的表的空白部分" lightbox="../media/storage-application-local-storage-new-key-value.msft.png":::
       双击表的空白部分以创建新键值对  
    :::image-end:::  
    
## <a name="edit-localstorage-keys-or-values"></a>编辑 localStorage 键或值  

1.  [查看域的 localStorage 键值对](#view-localstorage-keys-and-values)。  
1.  双击“**键**”或“**值**”列中的单元格以编辑该键或值。  
    
    :::image type="complex" source="../media/storage-application-local-storage-edit-key-value.msft.png" alt-text="编辑 localStorage 键" lightbox="../media/storage-application-local-storage-edit-key-value.msft.png":::
       编辑`localStorage`键  
    :::image-end:::  
    
## <a name="delete-localstorage-key-value-pairs"></a>删除 localStorage 键值对  

1.  [查看域的`localStorage`键值对](#view-localstorage-keys-and-values)。  
1.  选择要删除的键值对。  DevTools 会以蓝色将其突出显示以表示其已选中。  
1.  选择`Delete`键或选择“**删除所选**”\(“![删除所选](../media/delete-icon.msft.png)”\)。  
    
## <a name="delete-all-localstorage-key-value-pairs-for-a-domain"></a>删除域的所有`localStorage`键值对  

1.  [查看域的`localStorage`键值对](#view-localstorage-keys-and-values)。  
1.  选择“**全部清除**”\(“![全部清除](../media/clear-icon.msft.png)”\)。  
    
## <a name="interact-with-localstorage-from-the-console"></a>通过控制台与 localStorage 交互  

由于可以在**控制台**中运行 JavaScript，并且由于**控制台**可以访问页面的 JavaScript 上下文，因此可以通过**控制台**与`localStorage`交互。  

1.  如果要访问除了显示页面以外域的`localStorage`键值对，使用“**JavaScript 上下文**”菜单更改**控制台**的 JavaScript 上下文。  
    
    :::image type="complex" source="../media/storage-console-local-storage.msft.png" alt-text="更改控制台的 JavaScript 上下文" lightbox="../media/storage-console-local-storage.msft.png":::
       更改控制台的 JavaScript 上下文  
    :::image-end:::  
    
1.  在控制台中运行`localStorage`表达式，与在 JavaScript 中一样。  
    
    :::image type="complex" source="../media/storage-console-local-storage-interaction.msft.png" alt-text="通过控制台与 localStorage 交互" lightbox="../media/storage-console-local-storage-interaction.msft.png":::
       通过**控制台**与`localStorage`交互  
    :::image-end:::  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge DevTools 团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 开发人员工具| Microsoft Docs"  

[MDNWindowsLocalStorage]: https://developer.mozilla.org/docs/Web/API/Window/localStorage "Window.localStorage | MDN"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/storage/localstorage)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
