---
description: Open the Command Menu and run the "Disable JavaScript" command.
title: Disable JavaScript With Microsoft Edge DevTools
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web development, f12 tools, devtools
ms.openlocfilehash: de756e04c91768c49eed50debce97ae91fdaa3bd
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10992797"
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

# Disable JavaScript With Microsoft Edge DevTools  

Complete the following actions to see how a web page looks and behaves when JavaScript is disabled.  

1.  [Open Microsoft Edge DevTools][DevToolsOpen].  
1.  Press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the **Command Menu**.  
    
    :::image type="complex" source="../media/javascript-console-command.msft.png" alt-text="The Command Menu" lightbox="../media/javascript-console-command.msft.png":::
       The **Command Menu**  
    :::image-end:::  
    
1.  Start typing `javascript`, select **Disable JavaScript**, and then press `Enter` to run the command.  JavaScript is now disabled.  
    
    :::image type="complex" source="../media/javascript-console-command-javascript.msft.png" alt-text="The Command Menu" lightbox="../media/javascript-console-command-javascript.msft.png":::
       Select **Disable JavaScript** in the **Command Menu**  
    :::image-end:::  
    
    The yellow warning icon next to **Sources** reminds you that JavaScript is disabled.  
    
    :::image type="complex" source="../media/javascript-console-javascript-disabled-warning.msft.png" alt-text="The Command Menu" lightbox="../media/javascript-console-javascript-disabled-warning.msft.png":::
       The warning icon next to **Sources**  
    :::image-end:::  
    
JavaScript remains disabled in the tab for as long as you have DevTools open.  

You may want to reload the page to see if and how the page depends on JavaScript while loading.  

To re-enable JavaScript, complete the following actions.  

*   Open the **Command Menu** again and run the `Enable JavaScript` command.  
*   Close DevTools.  

## Getting in touch with the Microsoft Edge DevTools team  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsOpen]: ../open.md "Open Microsoft Edge DevTools | Microsoft Docs"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/javascript/disable)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
