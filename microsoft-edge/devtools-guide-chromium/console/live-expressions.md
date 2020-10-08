---
description: 如果您发现自己重复在控制台中键入相同的 JavaScript 表达式，请尝试改用实时表达式。
title: 实时监视 JavaScript 表达式值和实时表达式
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
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





# 实时监视 JavaScript 表达式值和实时表达式   

  

如果您发现自己在控制台中重复键入相同的 JavaScript 表达式，您可能会发现创建 **实时表达式**变得更容易。  使用 **实时表达式** ，您只需要键入一个表达式，然后将其固定到您的控制台顶部。  表达式的值几乎实时更新。  

## 创建实时表达式   

1.  [打开控制台][DevToolsConsoleReferenceOpenConsole]。  
1.  单击 " **创建实时表达式** \ (![ 创建实时表达式 ][ImageCreateLiveExpressionIcon] \ ) "。  将显示 " **活动表达式** " 文本框。  
    
    :::image type="complex" source="../media/console-create-live-expression.msft.png" alt-text="在 &quot;活动表达式&quot; 文本框中键入 activeElement" lightbox="../media/console-create-live-expression.msft.png":::
       `document.activeElement`在 "**活动表达式**" 文本框中键入  
    :::image-end:::  
    
1.  键入 `Control` + `Enter` \ (Windows \ ) 或 `Command` + `Enter` \ (macOS \ ) 保存表达式，或在 "**实时表达式**" 文本框外单击。  

<!--todo: add reference open console (open the console) section when available  -->  

 



<!-- image links -->  

[ImageCreateLiveExpressionIcon]: ../media/create-live-expression-icon.msft.png  

<!-- links -->  

[DevToolsConsoleReferenceOpenConsole]: ./reference.md#open-the-console "打开控制台-控制台参考 |Microsoft 文档"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/console/live-expressions)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
