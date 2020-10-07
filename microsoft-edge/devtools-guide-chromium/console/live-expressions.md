---
description: If you find yourself typing the same JavaScript expressions into the Console repeatedly, try Live Expressions instead.
title: Watch JavaScript Expression Values In Real-Time With Live Expressions
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web development, f12 tools, devtools
ms.openlocfilehash: 6b66c44b77cd50bc0c1575e5eceb7c8d1a01b709
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993112"
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





# Watch JavaScript Expression Values In Real-Time With Live Expressions   

  

If you find yourself typing the same JavaScript expression in the Console repeatedly, you might find it easier to create a **Live Expression**.  With **Live Expressions** you type an expression once and then pin it to the top of your Console.  The value of the expression updates in near real-time.  

## Create a Live Expression   

1.  [Open the Console][DevToolsConsoleReferenceOpenConsole].  
1.  Click **Create Live Expression** \(![Create Live Expression][ImageCreateLiveExpressionIcon]\).  The **Live Expression** text box appears.  
    
    :::image type="complex" source="../media/console-create-live-expression.msft.png" alt-text="Typing document.activeElement into the Live Expression text box" lightbox="../media/console-create-live-expression.msft.png":::
       Typing `document.activeElement` into the **Live Expression** text box  
    :::image-end:::  
    
1.  Type `Control`+`Enter` \(Windows\) or `Command`+`Enter` \(macOS\) to save the expression, or click outside of the **Live Expression** text box.  

<!--todo: add reference open console (open the console) section when available  -->  

 



<!-- image links -->  

[ImageCreateLiveExpressionIcon]: ../media/create-live-expression-icon.msft.png  

<!-- links -->  

[DevToolsConsoleReferenceOpenConsole]: ./reference.md#open-the-console "Open the Console - Console Reference | Microsoft Docs"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/console/live-expressions)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
