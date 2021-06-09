---
description: 打开控制台，创建一个动态表达式，然后将表达式设置为document.activeElement。
title: 跟踪哪些元素有焦点
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge,web 开发,f12 工具,开发工具
ms.openlocfilehash: 2fd53caccefefb0b0bce4b5c82f30632e11a3cb6
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597109"
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

假设正在测试页面的键盘导航辅助功能。  使用`Tab`键浏览页面时，聚焦环有时会消失，因为具有焦点的元素被隐藏。  

若要跟踪 DevTools 中聚焦的元素：

1.  打开“**控制台**”。  
1.  Choose **Create live expression** \ (Create live expression ![ ](../media/create-live-expression-icon.msft.png) \) .  
    
    :::image type="complex" source="../media/accessibility-console-create-live-expression-empty.msft.png" alt-text="创建动态表达式" lightbox="../media/accessibility-console-create-live-expression-empty.msft.png":::
       创建动态表达式  
    :::image-end:::  
    
1.  键入 `document.activeElement`。  
1.  若要保存表达式，请选择活动表达式外部。
    
`document.activeElement` 下面显示的值是表达式的结果。  

由于该表达式始终代表着焦点的元素，因此现在可以始终跟踪哪个元素具有焦点。  

*   将鼠标悬停在结果上，以在视区中突出显示焦点元素。  
*   将鼠标悬停在结果上，打开上下文菜单 \(右键单击\) ，然后选择“**在元素面板显示**”以在“**元素**”工具上显示 DOM 树中的元素。  
*   将鼠标悬停在结果上，打开上下文菜单 \(右键单击\)，然后选择“**存储为全局变量**”，以创建对可以在**控制台**中所使用节点的变量引用。  


## <a name="see-also"></a>另请参阅

*  [分析边栏菜单中键盘焦点的缺失](test-analyze-no-focus-indicator.md)


## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge 开发工具团队

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  


<!-- links -->  
> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/accessibility/focus)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
