---
title: 跟踪哪个元素具有焦点
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/18/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: a1bcb7e97357d1348b363ecd4842d1b6a78feb45
ms.sourcegitcommit: 8bfa239274e7a4856b961b9cf163b08d96463c10
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2020
ms.locfileid: "10581529"
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





# 跟踪哪个元素具有焦点   



假设你要测试页面的键盘导航辅助功能。  当在页面 `Tab` 上导航键时，焦点圆圈有时会消失，因为具有焦点的元素已隐藏。  在 DevTools 中跟踪重点元素：  

1.  打开**控制台**。  
1.  单击 "**创建实时表达式**" ![ 创建实时表达式 ][ImageCreateIcon] 。  

    > ##### 图 1  
    > 创建**实时表达式**  
    > ![创建实时表达式][ImageLiveExpression]  
    
1.  键入 `document.activeElement`。
1.  在要保存的**实时表达式**UI 外部单击。

下面看到的值 `document.activeElement` 是表达式的结果。  
由于该表达式始终表示焦点元素，因此你现在可以始终跟踪哪个元素具有焦点。  

*   将鼠标悬停在结果上以突出显示视区中的焦点元素。  
*   右键单击结果，然后在 **"元素" 面板中选择 "显示**"，以在 "**元素**" 面板上的 DOM 树中显示该元素。  
*   右键单击结果，然后选择 "**存储为全局变量**"，创建对可以在**控制台**中使用的节点的变量引用。  

<!--## Feedback   -->  



<!-- image links -->  

[ImageCreateIcon]: /microsoft-edge/devtools-guide-chromium/media/create-live-expression-icon.msft.png  

[ImageLiveExpression]: /microsoft-edge/devtools-guide-chromium/media/accessibility-console-create-live-expression-empty.msft.png "图1：创建实时表达式"  

<!-- links -->  

> [!NOTE]
> 此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/accessibility/focus)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools & Lighthouse \）创作。  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
