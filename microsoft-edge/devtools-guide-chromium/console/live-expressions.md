---
title: 实时监视 JavaScript 表达式值和实时表达式
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/24/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: c388e44ca5507dd88ad9ad7b7ee985e658dfc569
ms.sourcegitcommit: 5cdc1626d5581b79c0f2ac4ea62e7f1974ebfa57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2020
ms.locfileid: "10601738"
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





# 实时监视 JavaScript 表达式值和实时表达式   

  

如果您发现自己在控制台中重复键入相同的 JavaScript 表达式，您可能会发现创建**实时表达式**变得更容易。  使用**实时表达式**，您只需要键入一个表达式，然后将其固定到您的控制台顶部。  表达式的值几乎实时更新。  

## 创建实时表达式   

1.  [打开控制台][DevToolsConsoleReferenceOpenConsole]。  
1.  单击 "**创建实时表达式**" ![ 创建实时表达式 ][ImageCreateLiveExpressionIcon] 。  将显示 "**活动表达式**" 文本框。  
    
    > ##### 图 1  
    > `document.activeElement`在 "**活动表达式**" 文本框中键入  
    > ![在 "活动表达式" 文本框中键入 activeElement][ImageLiveExpressionTextbox]  
    
1.  键入 `Control` + `Enter` \ （Windows \）或 `Command` + `Enter` \ （macOS \）保存表达式，或单击 "**实时表达式**" 文本框外部。  

<!--todo: add reference open console (open the console) section when available  -->  

 



<!-- image links -->  

[ImageCreateLiveExpressionIcon]: /microsoft-edge/devtools-guide-chromium/media/create-live-expression-icon.msft.png  

[ImageLiveExpressionTextbox]: /microsoft-edge/devtools-guide-chromium/media/console-create-live-expression.msft.png "图1：在 "活动表达式" 文本框中键入 activeElement"  

<!-- links -->  

[DevToolsConsoleReferenceOpenConsole]: /microsoft-edge/devtools-guide-chromium/console/reference#open-the-console "打开控制台参考"  

> [!NOTE]
> 此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/console/live-expressions)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools \ & Lighthouse \）创作。  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
