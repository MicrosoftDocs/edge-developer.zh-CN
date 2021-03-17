---
description: 如果您发现自己在控制台中重复键入相同的 JavaScript 表达式，请尝试 Live Expressions。
title: 使用 Live Expressions 实时观看 JavaScript 表达式值
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: af920de1c395489dc09b83f3cc0f24814c4f5cbe
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439224"
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

# <a name="watch-javascript-expression-values-in-real-time-with-live-expressions"></a>使用 Live Expressions 实时观看 JavaScript 表达式值  

如果你发现自己在控制台中重复键入相同的 JavaScript 表达式，你可能会发现创建 Live **Expression**更容易。  使用 **Live Expressions，** 键入表达式一次，然后将其固定到控制台顶部。  表达式的值几乎实时更新。  

## <a name="create-a-live-expression"></a>创建实时表达式  

1.  [打开控制台][DevToolsConsoleReferenceOpenConsole]。  
1.  Choose **Create Live Expression** \ (Create Live Expression ![ ](../media/create-live-expression-icon.msft.png) \) .  将显示 **"Live Expression"** 文本框。  
    
    :::image type="complex" source="../media/console-create-live-expression.msft.png" alt-text="在 Live Expression 文本框中键入 document.activeElement" lightbox="../media/console-create-live-expression.msft.png":::
       在 `document.activeElement` Live **Expression 文本框中** 键入内容  
    :::image-end:::  
    
1.  选择 `Control` + `Enter` \ (Windows、Linux\) 或 `Command` + `Enter` \ (macOS\) **** 保存表达式，或在 Live Expression 文本框外部选择。  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge 开发工具团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsConsoleReferenceOpenConsole]: ./reference.md#open-the-console "打开控制台 - 控制台|Microsoft Docs"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/console/live-expressions)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
