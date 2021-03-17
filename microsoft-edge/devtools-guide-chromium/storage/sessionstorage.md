---
description: 如何使用会话存储窗格和控制台查看和编辑 sessionStorage。
title: 使用 Microsoft Edge DevTools 查看和编辑会话存储
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: 0168b01fd01071ebd19bd211c6d947ae006d778c
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439659"
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

# <a name="view-and-edit-session-storage-with-microsoft-edge-devtools"></a>使用 Microsoft Edge DevTools 查看和编辑会话存储  

本指南演示如何使用 [Microsoft Edge DevTools][MicrosoftEdgeDevTools] 查看、编辑和删除 [sessionStorage][MDNSessionStorage] 键值对。  

## <a name="view-sessionstorage-keys-and-values"></a>查看 sessionStorage 键和值  

1.  选择" **应用程序"** 选项卡以打开 **"应用程序"** 工具。  默认情况下 **显示** 清单面板。  
    
    :::image type="complex" source="../media/storage-application-manifest.msft.png" alt-text="清单窗格" lightbox="../media/storage-application-manifest.msft.png":::
       清单**窗格**  
    :::image-end:::  
    
1.  展开" **会话存储"** 菜单。  
    
    :::image type="complex" source="../media/storage-application-storage-session-storage.msft.png" alt-text="会话存储菜单" lightbox="../media/storage-application-storage-session-storage.msft.png":::
       会话 **存储** 菜单  
    :::image-end:::  
    
1.  选择一个域以查看键值对。  
    
    :::image type="complex" source="../media/storage-application-storage-session-storage-domain.msft.png" alt-text="sessionStorage 键值对" lightbox="../media/storage-application-storage-session-storage-domain.msft.png":::
       `sessionStorage`键值对  
    :::image-end:::  
    
1.  选择表格的一行以查看表格下方的查看器中的值。  
    
    :::image type="complex" source="../media/storage-application-storage-session-storage-domain-key-value-selected.msft.png" alt-text="查看 x-sid 键的值" lightbox="../media/storage-application-storage-session-storage-domain-key-value-selected.msft.png":::
       查看键 `x-sid` 的值  
    :::image-end:::  
    
## <a name="create-a-new-sessionstorage-key-value-pair"></a>创建新的 sessionStorage 键值对  

1.  [查看域的 sessionStorage 键值对](#view-sessionstorage-keys-and-values)。  
1.  双击表格的空部分。  DevTools 创建一个新行，并焦点在键列中 **的** 光标。  
    
    :::image type="complex" source="../media/storage-application-storage-session-storage-domain-key-value-new.msft.png" alt-text="要双击以创建新的键值对的表的空部分" lightbox="../media/storage-application-storage-session-storage-domain-key-value-new.msft.png":::
       要双击以创建新的键值对的表的空部分  
    :::image-end:::  
    
## <a name="edit-sessionstorage-keys-or-values"></a>编辑 sessionStorage 键或值  

1.  [查看域的 sessionStorage 键值对](#view-sessionstorage-keys-and-values)。  
1.  双击"键"或"值****"**列中的单元格**以编辑该键或值。  
    
    :::image type="complex" source="../media/storage-application-storage-session-storage-domain-key-value-edit.msft.png" alt-text="编辑 sessionStorage 键" lightbox="../media/storage-application-storage-session-storage-domain-key-value-edit.msft.png":::
       编辑 `sessionStorage` 密钥  
    :::image-end:::  
    
## <a name="delete-sessionstorage-key-value-pairs"></a>删除 sessionStorage 键值对  

1.  [查看 `sessionStorage` 域的键值对](#view-sessionstorage-keys-and-values)。  
1.  选择要删除的键值对。  DevTools 突出显示蓝色以指示已选中。  
1.  选择该 `Delete` 键或选择****"删除所选 \ (![ 删除所选 ](../media/delete-icon.msft.png) \) "。  
    
## <a name="delete-all-sessionstorage-key-value-pairs-for-a-domain"></a>删除域的所有 sessionStorage 键值对  

1.  [查看 `sessionStorage` 域的键值对](#view-sessionstorage-keys-and-values)。  
1.  Choose **Clear All** \ (Clear All ![ ](../media/clear-icon.msft.png) \) .  
    
## <a name="interact-with-sessionstorage-from-the-console"></a>从控制台与 sessionStorage 交互  

由于你可能在控制台中运行 JavaScript，并且由于**控制台**可以访问页面的 JavaScript 上下文，因此可以与控制台**** `sessionStorage` **进行交互**。  

1.  如果要访问除你位于的页面外的其他域的键值对，**** 请使用**JavaScript**上下文菜单更改控制台的 JavaScript `sessionStorage` 上下文。  
    
    :::image type="complex" source="../media/storage-console-domain-selection.msft.png" alt-text="更改控制台的 JavaScript 上下文" lightbox="../media/storage-console-domain-selection.msft.png":::
       更改控制台的 JavaScript **上下文**  
    :::image-end:::  
    
1.  在控制台 `sessionStorage` 中 **运行表达式**，与 JavaScript 相同。  
    
    :::image type="complex" source="../media/storage-console-session-storage-keys.msft.png" alt-text="从控制台与 sessionStorage 交互" lightbox="../media/storage-console-session-storage-keys.msft.png":::
       从控制台 `sessionStorage` **进行交互**  
    :::image-end:::  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge 开发工具团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 开发人员工具|Microsoft Docs"  

[MDNSessionStorage]: https://developer.mozilla.org/docs/Web/API/Window/sessionStorage "Window.sessionStorage |MDN"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/storage/sessionstorage)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
