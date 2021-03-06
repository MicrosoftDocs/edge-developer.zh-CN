---
description: 打开控制台，创建 Live Expression，将表达式设置为 document.activeElement。
title: 跟踪哪些元素有焦点
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: 3f3e59c4ee6f10b8e162f30efbff337ca2beec8d
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398313"
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

# <a name="track-which-element-has-focus"></a>跟踪哪些元素有焦点  

假设您正在测试页面的键盘导航辅助功能。  当使用键导航页面时，焦点圈有时会消失，因为具有焦点 `Tab` 的元素已被隐藏。  

完成以下操作以跟踪 DevTools 中的聚焦元素。  

1.  打开 **控制台**。  
1.  Choose **Create Live Expression** \ (Create Live Expression ![ ][ImageCreateIcon] \) .  
    
    :::image type="complex" source="../media/accessibility-console-create-live-expression-empty.msft.png" alt-text="创建动态表达式" lightbox="../media/accessibility-console-create-live-expression-empty.msft.png":::
       创建动态表达式  
    :::image-end:::  
    
1.  键入 `document.activeElement`。  
1.  选择要保存的 **Live Expression** UI 外部。  
    
下面显示 `document.activeElement` 的值是表达式的结果。  

由于该表达式始终表示聚焦元素，因此你现在有一种方法可以始终跟踪哪个元素具有焦点。  

*   将鼠标悬停在结果上以突出显示视区中聚焦的元素。  
*   将鼠标悬停在结果上，打开上下文菜单 \ (右键单击\) ，然后选择"元素中的展示****"面板以显示"元素"工具上的 DOM 树**中的**元素。  
*   将鼠标悬停在结果上，打开上下文菜单 \ (右键单击\) ，然后选择"存储"**** 作为全局变量以创建对可以在控制台中使用的节点的变量**引用**。  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge 开发工具团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageCreateIcon]: ../media/create-live-expression-icon.msft.png  

<!-- links -->  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/accessibility/focus)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
