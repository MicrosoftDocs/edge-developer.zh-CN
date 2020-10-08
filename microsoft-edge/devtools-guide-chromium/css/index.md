---
description: 了解如何使用 Microsoft Edge DevTools 查看和更改页面的 CSS。
title: 查看和更改 CSS 入门
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: f055606ff6140652341627097e7fe7b270dc929c
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993063"
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

1.  保留 `Control` \ (Windows \ ) 或 `Command` \ (macOS \ ) 并选择 " **CSS 示例** " 以在新窗口中打开。  
    
    [CSS 示例][GlitchDevToolsCssExamples]  
    
    > [!NOTE]
    > 如果要将 [DevTools 窗口停靠在][DevToolsCustomizePlacement] 的 (右侧，如下图 \ ) 中所示，请选择 " **自定义和控制 DevTools** " `...` 。  在 " **自定义和控制 DevTools** " 下拉菜单的 " **停靠侧** " 部分中，选择 " **停靠到右侧**"。  
    
## 查看元素的 CSS  

1.  [打开 CSS 示例](#open-css-examples)。  
1.  将鼠标悬停在 `Inspect Me!` 文本上，打开上下文菜单 \ (右键单击 "\ ) "，然后选择 " **检查**"。  
    1.  在 DevTools 中，在 " **元素** " 面板上的 " **DOM 树** " 选项卡中 `Inspect Me!` 突出显示该元素。  
        
        :::image type="complex" source="../media/css-elements-inspect-me.msft.png" alt-text="在 DOM 树中突出显示已检查的元素" lightbox="../media/css-elements-inspect-me.msft.png":::
           图1：在**DOM 树**中突出显示已检查的元素  
        :::image-end:::  
        
    1.  在 `Inspect Me!` 元素中，找到属性的值 `data-message` 并复制它。  
1.  在页面上的 " **值 `data-message` ：** " 文本框中，输入值。  
1.  将鼠标悬停在 `Inspect Me!` 文本上，打开上下文菜单 \ (右键单击 "\ ) "，然后选择 " **检查**"。  
    1.  在 DevTools 中的 " **元素** " 面板上，选择 " **样式** " 选项卡。  
    1.  在 " **样式** " 选项卡中， `Inspect Me!` 突出显示该元素。  
    1.  在 `Inspect Me!` 元素中，找到 " `aloha` 类规则"。  
        
        > [!NOTE]
        > 你将看到此规则，因为它应用于该 `Inspect Me!` 元素。  
        
    1.  在 `aloha` 类中，查找样式的值 `padding` 并复制它。  
        
        :::image type="complex" source="../media/css-elements-inspect-me-styles.msft.png" alt-text="在 DOM 树中突出显示已检查的元素" lightbox="../media/css-elements-inspect-me-styles.msft.png":::
           图2：应用到所选元素（如）的 CSS 类 `aloha` 显示在 " **样式** " 选项卡中  
        :::image-end:::  
        
1.  在页面上的 " **值 `padding` ：** " 文本框中，输入值。  

## 向元素添加 CSS 声明  

当你想要将 CSS 声明更改或添加到元素时，请使用 " **样式** " 选项卡。  

> [!NOTE]
> 在执行此操作之前，请先完成 [查看元素教程的 CSS](#view-the-css-for-an-element) 。  

1.  [打开 CSS 示例](#open-css-examples)。  
1.  将鼠标悬停在 `Add A Background Color To Me!` 文本上，打开上下文菜单 \ (右键单击 "\ ) "，然后选择 " **检查**"。  
1.  选择 `element.style` " **样式** " 选项卡顶部附近的。  
1.  键入 `background-color` ，然后按 `Enter` 。  
1.  键入 `honeydew` ，然后按 `Enter` 。  在 **DOM 树** 中，应看到已对元素应用了内联样式声明。  
    
    :::image type="complex" source="../media/css-elements-add-background-color-to-me-styles-p.msft.png" alt-text="在 DOM 树中突出显示已检查的元素" lightbox="../media/css-elements-add-background-color-to-me-styles-p.msft.png":::
       图3： `background-color:honeydew` 使用 `element.style` " **样式** " 选项卡部分对元素应用了声明  
    :::image-end:::  
    
## 向元素添加 CSS 类  

使用 " **样式** " 选项卡查看在将 CSS 类应用到元素或从元素中删除时元素的外观。  

> [!NOTE]
> 在执行此操作之前，请先完成 [查看元素教程的 CSS](#view-the-css-for-an-element) 。  

1.  [打开 CSS 示例](#open-css-examples)。  
1.  将鼠标悬停在 `Add A Class To Me!` 文本上，打开上下文菜单 \ (右键单击 "\ ) "，然后选择 " **检查**"。  
1.  选择 **. cls**。  DevTools 将显示一个文本框，你可以在其中将类添加到所选元素。  
1.  `color_me`在 "**添加新类**" 文本框中键入，然后按 `Enter` 。  " **添加新类** " 文本框下方将显示一个复选框，您可以在其中打开和关闭类。  如果 `Add A Class To Me!` 元素应用了任何其他类，你也可以在此处进行切换。  
    
    :::image type="complex" source="../media/css-elements-add-a-class-to-me-styles-cls.msft.png" alt-text="在 DOM 树中突出显示已检查的元素" lightbox="../media/css-elements-add-a-class-to-me-styles-cls.msft.png":::
       图4： `color_me` 使用 "**样式**" 选项卡的 " **cls** " 部分将类应用于元素  
    :::image-end:::  
    
## 向类添加伪状态  

使用 " **样式** " 选项卡将 CSS 伪状态永久应用到元素。  DevTools 支持 `:active` 、 `:focus` 、 `:hover` 和 `:visited` 。  

> [!NOTE]
> 在执行此操作之前，请先完成 [查看元素教程的 CSS](#view-the-css-for-an-element) 。  

1.  [打开 CSS 示例](#open-css-examples)。  
1.  将鼠标悬停在 `Hover Over Me!` 文本上。  背景色更改。  
1.  将鼠标悬停在 `Hover Over Me!` 文本上，打开上下文菜单 \ (右键单击 "\ ) "，然后选择 " **检查**"。  
1.  在 " **样式** " 选项卡中，选择 **： hov**。  
1.  选中 **： "悬停** " 复选框。  背景色会像以前一样更改，即使你实际上不是悬停在该元素上也是如此。  
    
    :::image type="complex" source="../media/css-elements-hover-over-me-styles-hov-hover.msft.png" alt-text="在 DOM 树中突出显示已检查的元素" lightbox="../media/css-elements-hover-over-me-styles-hov-hover.msft.png":::
       图5：切换 `:hover` 元素上的伪状态  
    :::image-end:::  
    
## 更改元素的尺寸  

使用 "**样式**" 选项卡中的 **"方框模型**" 交互式图表更改元素的宽度、高度、填充、边距或边框长度。  

> [!NOTE]
> 在执行此操作之前，请先完成 [查看元素教程的 CSS](#view-the-css-for-an-element) 。  

1.  [打开 CSS 示例](#open-css-examples)。  
1.  将鼠标悬停在 `Change My Margin!` 文本上，打开上下文菜单 \ (右键单击 "\ ) "，然后选择 " **检查**"。  
1.  在 "**样式**" 选项卡中的 "**方框模型**" 图表中，将鼠标悬停在**填充**上。  元素的填充在视区中突出显示。  

    > [!NOTE]
    > 根据 DevTools 窗口的大小，可能需要滚动到 " **样式** " 选项卡底部才能看到 " **方框模型**"。  

1.  双击 **框模型**中的左边距，它当前具有 `-` 表示元素没有左边距的值。  
1.  键入 `100px` ，然后按 `Enter` 。  **Box 模型**默认为像素，但它还接受其他值，如 `25%` 或 `10vw` 。  
    
    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/css-elements-change-my-margin-styles-padding.msft.png" alt-text="在 DOM 树中突出显示已检查的元素" lightbox="../media/css-elements-change-my-margin-styles-padding.msft.png":::
             图6：将鼠标悬停在元素的填充上  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/css-elements-change-my-margin-styles-margin-edit.msft.png" alt-text="在 DOM 树中突出显示已检查的元素" lightbox="../media/css-elements-change-my-margin-styles-margin-edit.msft.png":::
             图7：更改元素的左边距  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
## 调试媒体查询  

[媒体查询][MDNUsingMediaGueries] 是一种使 web 产品对每个用户的配置设置所做更改做出反应的方式。  最重要的用例是根据视区的尺寸为你的产品提供不同的 CSS 布局。  当有更多的屏幕空间时，使用单独的布局可为移动设备和多列布局提供一列式布局。  

如果要调试或测试在 CSS 中定义的媒体查询，请使用以下步骤。  

1.  打开 "开发工具"，然后选择左上角的 "**切换设备" 工具栏**图标，或者按 `Ctrl` + `Shift` + `M` `Cmd` + `Shift` + `M` macOS \ ) 上的 \ (。  
    
    :::image type="complex" source="../media/css-elements-media-queries-open-device-toolbar.msft.png" alt-text="在 DOM 树中突出显示已检查的元素" lightbox="../media/css-elements-media-queries-open-device-toolbar.msft.png":::
       图8：打开 "设备" 工具栏  
    :::image-end:::  
    
1.  在 "设备" 工具栏打开的情况下，选择 `...` 右上角的菜单，然后选择 " **查看媒体查询**"。  您应在表示不同媒体查询的页面的显示上方看到颜色条。  
    
    :::image type="complex" source="../media/css-elements-media-queries-showing-mq.msft.png" alt-text="在 DOM 树中突出显示已检查的元素" lightbox="../media/css-elements-media-queries-showing-mq.msft.png":::
       图9：在 "设备" 工具栏中显示媒体查询  
    :::image-end:::  
    
1.  将鼠标悬停在条形图上的边界上可查看不同媒体查询的值。 选择 "每个" 以调整网页的大小以匹配。  
    
    :::image type="complex" source="../media/css-elements-media-queries-select-bar.msft.png" alt-text="在 DOM 树中突出显示已检查的元素" lightbox="../media/css-elements-media-queries-select-bar.msft.png":::
       图10：从预览栏选择媒体查询  
    :::image-end:::  
    
1.  若要调试媒体查询并在编辑器中打开 CSS 文件， `Sources` 请将鼠标悬停在任意条形图段上，打开上下文菜单 \ (右键单击 "\ ) "，然后选择 `reveal in source code` 。  
    
    :::image type="complex" source="../media/css-elements-media-queries-reveal-in-sources.msft.png" alt-text="在 DOM 树中突出显示已检查的元素" lightbox="../media/css-elements-media-queries-reveal-in-sources.msft.png":::
       图11：在源代码编辑器中泄漏媒体查询  
    :::image-end:::  
    
<!-- links -->  

[ DevToolsCustomizePlacement]: /microsoft-edge/devtools-guide-chromium/customize/placement  "更改 Microsoft Edge 开发人员工具的放置位置（取消停靠、停靠至底部、停靠至左）"   

[GlitchDevToolsCssExamples]: https://microsoft-edge-chromium-devtools.glitch.me/static/css/examples/ecma.html "CSS 示例-Microsoft Edge (Chromium) DevTools |故障"  

[MDNUsingMediaGueries]: https://developer.mozilla.org/docs/Web/CSS/Media_Queries/Using_media_queries "使用媒体查询 |MDN"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/css/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
