---
description: Enable "Mark content scripts as Library code" from Settings > Framework Library Code.
title: Mark Content Scripts as Library Code
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web development, f12 tools, devtools
ms.openlocfilehash: 517e0a4e944f32d41451a0a5d9d7baa91ff97212
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10992790"
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

# Mark content scripts as Library code  

When using the **Sources** panel of Microsoft Edge DevTools to [step through code][DevToolsJavascriptStepThroughCode], sometimes you pause on code that you do not recognize.  You probably paused on code for one of the Microsoft Edge Extensions that you installed.  Complete the following steps to not pause on extension code.  

1.  Open DevTools, select **Customize and control DevTools** \(`...`\) and choose **Settings**.  You may also open **Settings** by selecting `F1`.  

1.  Select the **Library code** tab which opens the **Framework Library Code** section of **Settings**.  
1.  Enable the **Mark content scripts as Library code** checkbox.  
    
    :::image type="complex" source="../../media/javascript-settings-library-code-mark-content-scripts-library-code.msft.png" alt-text="Enable the Mark content scripts as Library code checkbox" lightbox="../../media/javascript-settings-library-code-mark-content-scripts-library-code.msft.png":::
       Enable the **Mark content scripts as Library code** checkbox  
    :::image-end:::  
    
## Getting in touch with the Microsoft Edge DevTools team  

[!INCLUDE [contact DevTools team note](../../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsJavascriptStepThroughCode]: ../index.md#step-4-step-through-the-code "Step 4: Step through the code - Get started with debugging JavaScript in Microsoft Edge DevTools | Microsoft Docs"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/javascript/guides/blackbox-chrome-extension-scripts)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
