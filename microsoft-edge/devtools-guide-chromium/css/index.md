---
title: 查看和更改 CSS 入门
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/27/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 85fceaa44b0143a82ca8f66ef8c63e1a9275dcd8
ms.sourcegitcommit: 5cdc1626d5581b79c0f2ac4ea62e7f1974ebfa57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2020
ms.locfileid: "10601815"
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





# 查看和更改 CSS 入门   



完成这些交互式教程，了解有关使用 Microsoft Edge DevTools 查看和更改页面的 CSS 的基础知识。  

## 打开 CSS 示例  

1.  保留 `Control` \ （Windows \）或 `Command` \ （macOS \），然后单击 " **CSS 示例**" 以在新窗口中打开。  
    
    [CSS 示例][GlitchDevToolsCssExamples]  

> [!NOTE]
> 如果要将[DevTools 窗口停靠][DevToolsCustomizePlacement]在视区的右侧 \ （如[图 1](#figure-1)\），请单击 "**自定义和控制 DevTools** " `...` 。  在 "**自定义和控制 DevTools** " 下拉菜单的 "**停靠侧**" 部分中，选择 "**停靠到右侧**"。  
    
## 查看元素的 CSS   

1.  [打开 CSS 示例](#open-css-examples)。  
1.  右键单击 `Inspect Me!` 文本，然后选择 "**检查**"。  
    1.  在 DevTools 中，在 "**元素**" 面板上的 " **DOM 树**" 选项卡中 `Inspect Me!` 突出显示该元素。  
        
        > ##### 图 1  
        > 在**DOM 树**中突出显示已检查的元素  
        > ![在 DOM 树中突出显示已检查的元素][ImageInspect]  
        
    1.  在 `Inspect Me!` 元素中，找到属性的值 `data-message` 并复制它。  
1.  在页面上的 "**值 `data-message` ：** " 文本框中，输入值。  
1.  右键单击 `Inspect Me!` 文本，然后选择 "**检查**"。  
    
    1.  在 DevTools 中的 "**元素**" 面板上，选择 "**样式**" 选项卡。  
    1.  在 "**样式**" 选项卡中， `Inspect Me!` 突出显示该元素。  
    1.  在 `Inspect Me!` 元素中，找到 " `aloha` 类规则"。  
        
        > [!NOTE]
        > 你将看到此规则，因为它应用于该 `Inspect Me!` 元素。  
        
    1.  在 `aloha` 类中，查找样式的值 `padding` 并复制它。  
        
        > ##### 图 2  
        > 应用于所选元素的 CSS 类（如 `aloha` ）将显示在 "**样式**" 选项卡中  
        > ![应用于已检查元素的 CSS 类在 "样式" 选项卡中突出显示][ImageAloha]  
        
1.  在页面上的 "**值 `padding` ：** " 文本框中，输入值。  

## 向元素添加 CSS 声明   

当你想要将 CSS 声明更改或添加到元素时，请使用 "**样式**" 选项卡。  

> [!NOTE]
> 在执行此操作之前，请先完成[查看元素教程的 CSS](#view-the-css-for-an-element) 。  

1.  [打开 CSS 示例](#open-css-examples)。  
1.  右键单击 `Add A Background Color To Me!` 文本，然后选择 "**检查**"。  
1.  单击 `element.style` "**样式**" 选项卡顶部附近的。  
1.  键入 `background-color` ，然后按 `Enter` 。  
1.  键入 `honeydew` ，然后按 `Enter` 。  在**DOM 树**中，应看到已对元素应用了内联样式声明。  

> ##### 图 3  
> 已 `background-color:honeydew` 使用 `element.style` "**样式**" 选项卡部分将声明应用到元素  
> ![使用 "样式" 选项卡将 CSS 声明添加到元素][ImageDeclaration]  

## 向元素添加 CSS 类   

使用 "**样式**" 选项卡查看在将 CSS 类应用到元素或从元素中删除时元素的外观。  

> [!NOTE]
> 在执行此操作之前，请先完成[查看元素教程的 CSS](#view-the-css-for-an-element) 。  

1.  [打开 CSS 示例](#open-css-examples)。  
1.  右键单击该 `Add A Class To Me!` 元素，然后选择 "**检查**"。  
1.  单击 " **. cls**。  DevTools 将显示一个文本框，你可以在其中将类添加到所选元素。  
1.  `color_me`在 "**添加新类**" 文本框中键入，然后按 `Enter` 。  "**添加新类**" 文本框下方将显示一个复选框，您可以在其中打开和关闭类。  如果 `Add A Class To Me!` 元素应用了任何其他类，你也可以在此处进行切换。  

> ##### 图 4  
> `color_me`该类已使用 "**样式**" 选项卡的 " **cls** " 部分应用于元素  
> ![将 color_me 类应用于元素][ImageApplyClass]  

## 向类添加伪状态   

使用 "**样式**" 选项卡将 CSS 伪状态永久应用到元素。  DevTools 支持 `:active` 、 `:focus` 、 `:hover` 和 `:visited` 。  

> [!NOTE]
> 在执行此操作之前，请先完成[查看元素教程的 CSS](#view-the-css-for-an-element) 。  

1.  [打开 CSS 示例](#open-css-examples)。  
1.  将鼠标悬停在 `Hover Over Me!` 文本上。  背景色更改。  
1.  右键单击 `Hover Over Me!` 文本，然后选择 "**检查**"。  
1.  在 "**样式**" 选项卡中，单击 **： hov**。  
1.  选中 **： "悬停**" 复选框。  背景色会像以前一样更改，即使你实际上不是悬停在该元素上也是如此。  

> ##### 图 5  
> `:hover`在元素上切换伪状态  
> ![切换元素上的悬停伪状态][ImageSetHover]  

## 更改元素的尺寸   

使用 "**样式**" 选项卡中的 **"方框模型**" 交互式图表更改元素的宽度、高度、填充、边距或边框长度。  

> [!NOTE]
> 在执行此操作之前，请先完成[查看元素教程的 CSS](#view-the-css-for-an-element) 。  

1.  [打开 CSS 示例](#open-css-examples)。  
1.  右键单击该 `Change My Margin!` 元素，然后选择 "**检查**"。  
1.  在 "**样式**" 选项卡中的 "**方框模型**" 图表中，将鼠标悬停在**填充**上。  元素的填充在视区中突出显示。  

    > [!NOTE]
    > 根据 DevTools 窗口的大小，可能需要滚动到 "**样式**" 选项卡底部才能看到 "**方框模型**"。  

1.  双击**框模型**中的左边距，它当前具有 `-` 表示元素没有左边距的值。  
1.  键入 `100px` ，然后按 `Enter` 。  **Box 模型**默认为像素，但它还接受其他值，如 `25%` 或 `10vw` 。  

> ##### 图 6  
> 将鼠标悬停在元素的填充上  
> ![将鼠标悬停在元素的填充上][ImageShowPadding]  

> ##### 图 7  
> 更改元素的左边距  
> ![更改元素的左边距][ImageChangeMargin]  

 



<!-- image links -->  

[ImageInspect]: /microsoft-edge/devtools-guide-chromium/media/css-elements-inspect-me.msft.png "图1：在 DOM 树中突出显示已检查的元素"  
[ImageAloha]: /microsoft-edge/devtools-guide-chromium/media/css-elements-inspect-me-styles.msft.png "图2：应用到已检查元素的 CSS 类在 "样式" 选项卡中突出显示"  
[ImageDeclaration]: /microsoft-edge/devtools-guide-chromium/media/css-elements-add-background-color-to-me-styles-p.msft.png "图3：使用 "样式" 选项卡将 CSS 声明添加到元素"  
[ImageApplyClass]: /microsoft-edge/devtools-guide-chromium/media/css-elements-add-a-class-to-me-styles-cls.msft.png "图4：将 color_me 类应用到元素"  
[ImageSetHover]: /microsoft-edge/devtools-guide-chromium/media/css-elements-hover-over-me-styles-hov-hover.msft.png "图5：切换元素上的悬停伪状态"  
[ImageShowPadding]: /microsoft-edge/devtools-guide-chromium/media/css-elements-change-my-margin-styles-padding.msft.png "图6：将鼠标悬停在元素的填充上"  
[ImageChangeMargin]: /microsoft-edge/devtools-guide-chromium/media/css-elements-change-my-margin-styles-margin-edit.msft.png "图7：更改元素的左边距"  

<!-- links -->  

[DevToolsCustomizePlacement]: /microsoft-edge/devtools-guide-chromium/customize/placement "更改 Microsoft Edge DevTools 位置（"取消停靠"、"停靠到底部"、"停靠到左侧"）"  

[GlitchDevToolsCssExamples]: https://microsoft-edge-chromium-devtools.glitch.me/static/css/examples/ecma.html "CSS 示例-Microsoft Edge （Chromium） DevTools |故障"  

> [!NOTE]
> 此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/css/index)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools \ & Lighthouse \）创作。  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
