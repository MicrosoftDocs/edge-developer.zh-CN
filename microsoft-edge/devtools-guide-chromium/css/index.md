---
description: 了解如何使用 Microsoft Edge DevTools 查看和更改页面的 CSS。
title: 查看和更改 CSS 入门
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: b3d19d34f329fec7a3903fb37e8be3558ba4d31d
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11399090"
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

# <a name="get-started-with-viewing-and-changing-css"></a>查看和更改 CSS 入门  

完成这些交互式教程，了解使用 Microsoft Edge DevTools 查看和更改页面 CSS 的基础知识。  

## <a name="open-css-examples"></a>打开 CSS 示例  

1.  按住 `Control` \ (Windows、Linux\) 或 `Command` \ (macOS\) ，然后选择 **CSS** 示例以在新窗口中打开。  
    
    [CSS 示例][GlitchDevToolsCssExamples]  
    
    > [!NOTE]
    > 如果你想要将[DevTools][DevToolsCustomizePlacement]窗口停靠在视口 \ (显示在下图\) 右侧，请选择"自定义和控制**DevTools"。** `...`  On the **Customize and control DevTools drop-down** menu， in the Dock side **section，** choose **Dock to right.**  
    
## <a name="view-the-css-for-an-element"></a>查看元素的 CSS  

1.  [打开 CSS 示例](#open-css-examples)。  
1.  将鼠标悬停在文本上，打开上下文菜单 `Inspect Me!` \ (右键单击\) ，然后选择"检查 **"。**  
    1.  在 DevTools 中的 **"元素** "工具的 **"DOM** 树"面板中， `Inspect Me!` 突出显示元素。  
        
        :::image type="complex" source="../media/css-elements-inspect-me.msft.png" alt-text="检查的元素在 DOM 树中突出显示" lightbox="../media/css-elements-inspect-me.msft.png":::
           检查的元素在 **DOM 树中突出显示**  
        :::image-end:::  
        
    1.  在 `Inspect Me!` 元素中，查找属性的值 `data-message` 并复制它。  
1.  在页面上：文本框 **的值 `data-message` ** 中，输入值。  
1.  将鼠标悬停在文本上，打开上下文菜单 `Inspect Me!` \ (右键单击\) ，然后选择"检查 **"。**  
    1.  在 DevTools 中的 **"元素** "工具上，选择 **"样式"** 面板。  
    1.  在 **"样式** "面板 `Inspect Me!` 中，突出显示元素。  
    1.  在 `Inspect Me!` 元素中，查找 `aloha` 类规则。  
        
        > [!NOTE]
        > 显示此规则，因为它将应用于 `Inspect Me!` 元素。  
        
    1.  在 `aloha` 类中，查找样式的值 `padding` 并复制它。  
        
        :::image type="complex" source="../media/css-elements-inspect-me-styles.msft.png" alt-text="CSS 类应用于已检查的元素在"样式"面板中突出显示" lightbox="../media/css-elements-inspect-me-styles.msft.png":::
           CSS 类应用于选定的元素，例如 `aloha` ，显示在 **样式面板** 中  
        :::image-end:::  
        
1.  在页面上：文本框 **的值 `padding` ** 中，输入值。  

## <a name="add-a-css-declaration-to-an-element"></a>向元素添加 CSS 声明  

当您要 **更改** CSS 声明或将 CSS 声明添加到元素时，请使用"样式"面板。  

> [!NOTE]
> 完成[此教程之前查看元素的 CSS。](#view-the-css-for-an-element)  

1.  [打开 CSS 示例](#open-css-examples)。  
1.  将鼠标悬停在文本上，打开上下文菜单 `Add A Background Color To Me!` \ (右键单击\) ，然后选择"检查 **"。**  
1.  选择 `element.style` "样式"面板 **顶部** 附近。  
1.  键入 `background-color` 并选择 `Enter`。  
1.  键入 `honeydew` 并选择 `Enter`。  在 **DOM 树**中，将显示应用于元素的内联样式声明。  
    
    :::image type="complex" source="../media/css-elements-add-background-color-to-me-styles-p.msft.png" alt-text="使用"样式"面板向元素添加 CSS 声明" lightbox="../media/css-elements-add-background-color-to-me-styles-p.msft.png":::
       使用 `background-color:honeydew` "样式"面板部分将声明应用于 `element.style` **** 元素  
    :::image-end:::  
    
## <a name="add-a-css-class-to-an-element"></a>将 CSS 类添加到元素  

若要显示 CSS 类应用于元素或从元素中删除某个元素时元素的外观，请导航到 **"样式"** 面板。  

> [!NOTE]
> 完成[此教程之前查看元素的 CSS。](#view-the-css-for-an-element)  

1.  [打开 CSS 示例](#open-css-examples)。  
1.  将鼠标悬停在文本上，打开上下文菜单 `Add A Class To Me!` \ (右键单击\) ，然后选择"检查 **"。**  
1.  选择 **.cls**。  DevTools 显示一个文本框，您可以在其中向所选元素添加类。  
1.  在 `color_me` " **添加新类"** 文本框中键入，然后选择 `Enter` 。  "添加新 **类"文本框** 下方将出现一个复选框，可在其中打开和关闭该类。  如果 `Add A Class To Me!` 元素应用了任何其他类，则还可以在此处切换每个类。  
    
    :::image type="complex" source="../media/css-elements-add-a-class-to-me-styles-cls.msft.png" alt-text="将 color_me 类应用于元素" lightbox="../media/css-elements-add-a-class-to-me-styles-cls.msft.png":::
       该类 `color_me` 使用"样式"面板的 **.cls**部分应用于元素****  
    :::image-end:::  
    
## <a name="add-a-pseudostate-to-a-class"></a>向类添加伪状态  

使用 **"样式** "面板将 CSS 伪状态永久应用于元素。  DevTools 支持 `:active` 、 `:focus` 和 `:hover` `:visited` 。  

> [!NOTE]
> 完成[此教程之前查看元素的 CSS。](#view-the-css-for-an-element)  

1.  [打开 CSS 示例](#open-css-examples)。  
1.  将鼠标悬停在 `Hover Over Me!` 文本上。  背景色更改。  
1.  将鼠标悬停在文本上，打开上下文菜单 `Hover Over Me!` \ (右键单击\) ，然后选择"检查 **"。**  
1.  在 **"样式"** 面板中，选择 **：hov**。  
1.  选中 **：hover** 复选框。  背景颜色会像以前一样更改，即使你实际上并未将鼠标悬停在元素上。  
    
    :::image type="complex" source="../media/css-elements-hover-over-me-styles-hov-hover.msft.png" alt-text="切换元素上的悬停伪状态" lightbox="../media/css-elements-hover-over-me-styles-hov-hover.msft.png":::
       切换 `:hover` 元素上的伪状态  
    :::image-end:::  
    
## <a name="change-the-dimensions-of-an-element"></a>更改元素的维度  

使用 **"样式**"面板中的"方框**** 模型"交互式图表可更改元素的宽度、高度、填充、边距或边框长度。  

> [!NOTE]
> 完成[此教程之前查看元素的 CSS。](#view-the-css-for-an-element)  

1.  [打开 CSS 示例](#open-css-examples)。  
1.  将鼠标悬停在文本上，打开上下文菜单 `Change My Margin!` \ (右键单击\) ，然后选择"检查 **"。**  
1.  在 **"样式"** 面板的" **框模型** "图表中，将鼠标悬停在 **填充上**。  元素填充在视口中突出显示。  

    > [!NOTE]
    > 根据 DevTools 窗口的大小，可能需要滚动到"样式"面板的底部以显示**框模型**。 ****  

1.  双击"方框模型"中的左边距****，当前具有一个表示元素没有左边距 `-` 的值。  
1.  键入 `100px` 并选择 `Enter`。  框 **模型** 默认为像素，但它也接受其他值，如 ， 或 `25%` `10vw` 。  
    
    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/css-elements-change-my-margin-styles-padding.msft.png" alt-text="将鼠标悬停在元素的填充上" lightbox="../media/css-elements-change-my-margin-styles-padding.msft.png":::
             将鼠标悬停在元素的填充上  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/css-elements-change-my-margin-styles-margin-edit.msft.png" alt-text="更改元素的左边距" lightbox="../media/css-elements-change-my-margin-styles-margin-edit.msft.png":::
             更改元素的左边距  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
## <a name="debugging-media-queries"></a>调试媒体查询  

[媒体查询][MDNUsingMediaGueries] 是使 Web 产品对每个用户的配置设置更改做出响应的一种方式。  最重要的用例是，根据视区尺寸，为产品提供不同的 CSS 布局。  当可用的屏幕空间更多时，使用单独的布局可支持移动设备的一列布局和多列布局。  

如果要调试或测试在 CSS 中定义的媒体查询，请使用以下步骤。  

1.  打开开发人员工具，选择左上方**** 第二个切换设备工具栏图标，或选择 macOS 上的 `Ctrl` + `Shift` + `M` \ (\) 。 `Cmd` + `Shift` + `M`  
    
    :::image type="complex" source="../media/css-elements-media-queries-open-device-toolbar.msft.png" alt-text="打开设备工具栏" lightbox="../media/css-elements-media-queries-open-device-toolbar.msft.png":::
       打开设备工具栏  
    :::image-end:::  
    
1.  在设备工具栏打开后，选择右上方的菜单， `...` 然后选择 **"查看媒体查询"。**  网页上方显示的彩色条形图表示不同的媒体查询。  
    
    :::image type="complex" source="../media/css-elements-media-queries-showing-mq.msft.png" alt-text="在设备工具栏中显示媒体查询" lightbox="../media/css-elements-media-queries-showing-mq.msft.png":::
       在设备工具栏中显示媒体查询  
    :::image-end:::  
    
1.  将鼠标悬停在栏的边界上，以显示不同媒体查询的值。  选择每个选项可调整要匹配的网页的大小。  
    
    :::image type="complex" source="../media/css-elements-media-queries-select-bar.msft.png" alt-text="从预览栏中选择媒体查询" lightbox="../media/css-elements-media-queries-select-bar.msft.png":::
       从预览栏中选择媒体查询  
    :::image-end:::  
    
1.  若要调试媒体查询，并打开编辑器中的 CSS 文件;请将鼠标悬停在任何条形区段上，打开上下文菜单 `Sources` \ (右键单击\) ，然后选择 `reveal in source code` 。  
    
    :::image type="complex" source="../media/css-elements-media-queries-reveal-in-sources.msft.png" alt-text="在源编辑器中显示媒体查询" lightbox="../media/css-elements-media-queries-reveal-in-sources.msft.png":::
       在源编辑器中显示媒体查询  
    :::image-end:::  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge 开发工具团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[ DevToolsCustomizePlacement]: /microsoft-edge/devtools-guide-chromium/customize/placement  "更改 Microsoft Edge 开发人员工具的放置位置（取消停靠、停靠至底部、停靠至左）"   

[GlitchDevToolsCssExamples]: https://microsoft-edge-chromium-devtools.glitch.me/static/css/examples/ecma.html "CSS 示例 - Microsoft Edge (Chromium) DevTools |小故障"  

[MDNUsingMediaGueries]: https://developer.mozilla.org/docs/Web/CSS/Media_Queries/Using_media_queries "使用媒体查询|MDN"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/css/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
