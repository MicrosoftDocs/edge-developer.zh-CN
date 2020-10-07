---
description: Open the "Rendering" tab and select "Emulate CSS media" > "print".
title: Force Microsoft Edge DevTools Into Print Preview Mode (CSS Print Media Type)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web development, f12 tools, devtools
ms.openlocfilehash: 1b71135c5ed2d86903b76e659434ee2125985a24
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993049"
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





# Force Microsoft Edge DevTools into Print Preview mode (CSS Print Media Type)   



The [print media query][MDNUsingMediaQueries] controls how your page looks when printed.  To force your page into print preview mode:  

1.  Press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the **Command Menu**.  
    
    :::image type="complex" source="../media/css-console-command-menu-rendering.msft.png" alt-text="The Command Menu" lightbox="../media/css-console-command-menu-rendering.msft.png":::
       The **Command Menu**  
    :::image-end:::  
    
1.  Type `rendering`, select **Show Rendering**, and then press `Enter`.  
1.  Under **Emulate CSS media** select **print**.  
    
    :::image type="complex" source="../media/css-elements-styles-qs-rendering-emulate-css-media-print.msft.png" alt-text="The Command Menu" lightbox="../media/css-elements-styles-qs-rendering-emulate-css-media-print.msft.png":::
       Print preview mode  
    :::image-end:::  
    
From here, you can view and change your CSS, like any other web page.  See [Get Started With Viewing And Changing CSS][DevToolsCSSGetStarted].  

<!--  
 


-->  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) Developer tools | Microsoft Docs"  
[DevToolsCSSGetStarted]: ./index.md "Get started with viewing and changing CSS | Microsoft Docs"  

[MDNUsingMediaQueries]: https://developer.mozilla.org/docs/Web/CSS/Media_Queries/Using_media_queries "Using media queries | MDN"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/css/print-preview)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
