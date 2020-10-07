---
description: How to view and edit sessionStorage with the Session Storage pane and the Console.
title: View And Edit Session Storage With Microsoft Edge DevTools
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web development, f12 tools, devtools
ms.openlocfilehash: 24fca3fd3a068f3b2ffbe4ec1c23e6b80b968953
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993546"
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





# View and edit Session Storage with Microsoft Edge DevTools   

  

This guide shows you how to use [Microsoft Edge DevTools][MicrosoftEdgeDevTools] to view, edit, and delete [`sessionStorage`][MDNSessionStorage] key-value pairs.  

## View sessionStorage keys and values   

1.  Select the **Application** tab to open the **Application** panel.  The **Manifest** pane is shown by default.  
    
    :::image type="complex" source="../media/storage-application-manifest.msft.png" alt-text="The Manifest pane" lightbox="../media/storage-application-manifest.msft.png":::
       The **Manifest** pane  
    :::image-end:::  
    
1.  Expand the **Session Storage** menu.  
    
    :::image type="complex" source="../media/storage-application-storage-session-storage.msft.png" alt-text="The Manifest pane" lightbox="../media/storage-application-storage-session-storage.msft.png":::
       The **Session Storage** Menu  
    :::image-end:::  
    
1.  Select a domain to view the key-value pairs.  
    
    :::image type="complex" source="../media/storage-application-storage-session-storage-domain.msft.png" alt-text="The Manifest pane" lightbox="../media/storage-application-storage-session-storage-domain.msft.png":::
       The `sessionStorage` key-value pairs  
    :::image-end:::  
    
1.  Select a row of the table to view the value in the viewer below the table.  
    
    :::image type="complex" source="../media/storage-application-storage-session-storage-domain-key-value-selected.msft.png" alt-text="The Manifest pane" lightbox="../media/storage-application-storage-session-storage-domain-key-value-selected.msft.png":::
       View the value of the `x-sid` key  
    :::image-end:::  
    
## Create a new sessionStorage key-value pair   

1.  [View the `sessionStorage` key-value pairs of a domain](#view-sessionstorage-keys-and-values).  
1.  Double-click the empty part of the table.  DevTools creates a new row and focuses your cursor in the **Key** column.  
    
    :::image type="complex" source="../media/storage-application-storage-session-storage-domain-key-value-new.msft.png" alt-text="The Manifest pane" lightbox="../media/storage-application-storage-session-storage-domain-key-value-new.msft.png":::
       The empty part of the table to double-click in order to create a new key-value pair  
    :::image-end:::  
    
## Edit sessionStorage keys or values   

1.  [View the `sessionStorage` key-value pairs of a domain](#view-sessionstorage-keys-and-values).  
1.  Double-click a cell in the **Key** or **Value** column to edit that key or value.  
    
    :::image type="complex" source="../media/storage-application-storage-session-storage-domain-key-value-edit.msft.png" alt-text="The Manifest pane" lightbox="../media/storage-application-storage-session-storage-domain-key-value-edit.msft.png":::
       Edit a `sessionStorage` key  
    :::image-end:::  
    
## Delete sessionStorage key-value pairs   

1.  [View the `sessionStorage` key-value pairs of a domain](#view-sessionstorage-keys-and-values).  
1.  Select the key-value pair that you want to delete.  DevTools highlights it blue to indicate that it is selected.  
1.  Press the `Delete` key or click **Delete Selected** \(![Delete Selected][ImageDeleteIcon]\).  
    
## Delete all sessionStorage key-value pairs for a domain   

1.  [View the `sessionStorage` key-value pairs of a domain](#view-sessionstorage-keys-and-values).  
1.  Select **Clear All** \(![Clear All][ImageClearIcon]\).  
    
## Interact with sessionStorage from the Console   

Since you can run JavaScript in the **Console**, and since the **Console** has access to the JavaScript contexts of the page, it is possible to interact with `sessionStorage` from the **Console**.  

1.  Use the **JavaScript contexts** menu to change the JavaScript context of the **Console** if you want to access the `sessionStorage` key-value pairs of a domain other than the page you are on.  
    
    :::image type="complex" source="../media/storage-console-domain-selection.msft.png" alt-text="The Manifest pane" lightbox="../media/storage-console-domain-selection.msft.png":::
       Change the JavaScript context of the Console  
    :::image-end:::  
    
1.  Run your `sessionStorage` expressions in the Console, the same as you would in your JavaScript.  
    
    :::image type="complex" source="../media/storage-console-session-storage-keys.msft.png" alt-text="The Manifest pane" lightbox="../media/storage-console-session-storage-keys.msft.png":::
       Interact with `sessionStorage` from the **Console**  
    :::image-end:::  
    
<!--  
   

  
-->  

<!-- image links -->  

[ImageClearIcon]: ../media/clear-icon.msft.png  
[ImageDeleteIcon]: ../media/delete-icon.msft.png  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) Developer tools | Microsoft Docs"  

[MDNSessionStorage]: https://developer.mozilla.org/docs/Web/API/Window/sessionStorage "Window.sessionStorage | MDN"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/storage/sessionstorage)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
