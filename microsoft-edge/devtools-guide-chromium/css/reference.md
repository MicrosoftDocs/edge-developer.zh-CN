---
description: 探索 Microsoft Edge DevTools 中用于查看和更改 CSS 的新工作流。
title: CSS 参考
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, 开发人员工具
ms.openlocfilehash: bddbf14e73f5c29bfd4757c9cd6d255f419c331f
ms.sourcegitcommit: 16e2f7232196a57a70b979bbf8b663774b7ddc20
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/25/2021
ms.locfileid: "11519329"
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

# <a name="css-reference"></a>CSS 参考  

在以下与查看和更改 CSS 相关的 Microsoft Edge DevTools 功能综合参考中发现新的工作流。  

若要了解基础知识，请导航到 [“查看和更改 CSS 入门”][DevToolsCSSGetStarted]。  

## <a name="choose-an-element"></a>选择元素  

DevTools **元素** 工具可用于一次查看或更改一个元素的 CSS。  所选元素在 **“DOM 树”** 上突出显示。  元素的样式显示在 **“样式”** 窗格中。  有关教程，请导航到 [查看元素的 CSS][DevToolsCSSGetStartedTutorial]。  

> [!NOTE]
> 下图中，**“DOM 树”** 中突出显示的 `h1` 元素就是所选元素。  在右侧的样式窗格中显示了元素的 **“样式”**。  在左侧，该元素在视区中突出显示，但只是因为当前在 **“DOM 树”** 中鼠标正悬停在它上方。  

:::image type="complex" source="../media/css-elements-styles-h1.msft.png" alt-text="所选元素的示例" lightbox="../media/css-elements-styles-h1.msft.png":::
   所选元素的示例  
:::image-end:::  

使用以下操作之一选择元素。  

*   在你的视区中，将鼠标悬停在元素上，打开上下文菜单 \(右键单击)，然后选择**检查**。  
*   在 DevTools 中，选择 **“选择元素”** \(![“选择元素”](../media/select-an-element-icon.msft.png)\) 或选择 `Control`+`Shift`+`C` \(Windows，Linux\) 或 `Command`+`Shift`+`C` \(macOS\)，然后在视区中选择该元素。  
*   在 DevTools 中，选择 **“DOM 树”** 中的元素。  
*   在 DevTools 中，运行一个查询 (如在 **控制台** 中的 `document.querySelector('p')`)，将鼠标悬停在结果上，打开上下文菜单 \(右键单击\)，然后选择 **“在元素面板上显示 “**。  

## <a name="view-css"></a>查看 CSS  

### <a name="view-the-external-stylesheet-where-a-rule-is-defined"></a>查看已定义规则的外部样式表  

在 **“样式”** 窗格中，选择 CSS 规则旁边的链接，以打开定义该规则的外部样式表。  样式表将在"源" **工具的** "编辑器" **窗格中** 打开。  

如果样式表缩小，请选择"编辑器"窗格**** 底部的"格式 ![ \ (格式 ](../media/format-icon.msft.png) **\) "** 按钮。  有关详细信息，请导航到[重新设置一个缩小的 JavaScript 文件与非常打印。][DevToolsJavascriptReferenceFormat]  

> [!NOTE]
> 在下图中，当你选择 `https://docs.microsoft.com/_themes/docs.theme/master/en-us/_themes/styles/b66bc881.site-ltr.css:2` 后，将会带你到定义了 `.content h1:first-of-type` CSS 规则的 `https://docs.microsoft.com/_themes/docs.theme/master/en-us/_themes/styles/b66bc881.site-ltr.css` 行2。  

<!--todo:  replace "Master" phrasing in code snippet, if possible.  -->  

:::image type="complex" source="../media/css-elements-styles-h1-highlight.msft.png" alt-text="查看定义规则的样式表" lightbox="../media/css-elements-styles-h1-highlight.msft.png":::
  查看定义规则的样式表  
:::image-end:::  

### <a name="view-only-the-css-that-is-actually-applied-to-an-element"></a>仅查看实际应用于元素的 CSS  

**“样式”** 面板显示应用于元素的所有规则，包括已覆盖声明。  当你对覆盖声明不感兴趣时，使用 **“计算”** 面板仅查看实际应用于元素的 CSS。  

1.  [选择元素](#choose-an-element)。  
1.  导航到 **“元素”** 工具中的 **“计算”** 面板。  

> [!NOTE]
> 在宽的 DevTools 窗口中，**“计算”** 面板不存在。  **“计算”** 面板中的内容会在 **“样式”** 面板中显示。  

继承的属性不透明。  若要显示所有继承的值，请选中 **“显示所有”** 复选框。  

> [!NOTE]
> 下图中，**“计算”** 面板显示应用于当前所选 `h1` 元素的 CSS 属性。  

:::image type="complex" source="../media/css-elements-computed-h1.msft.png" alt-text="“计算”面板" lightbox="../media/css-elements-computed-h1.msft.png":::
   **“计算”** 面板  
:::image-end:::  

### <a name="view-css-properties-in-alphabetical-order"></a>按字母顺序查看 CSS 属性  

使用 **“计算”** 面板。  导航到 [仅查看实际应用于元素的 CSS](#view-only-the-css-that-is-actually-applied-to-an-element)。  

### <a name="view-inherited-css-properties"></a>查看继承的 CSS 属性  

选中 **“计算”** 面板中的 **“显示所有”** 复选框。  导航到 [仅查看实际应用于元素的 CSS](#view-only-the-css-that-is-actually-applied-to-an-element)。  

### <a name="view-the-box-model-for-an-element"></a>查看元素的框模型  

若要查看元素的 [框模型][MDNBoxModel]，请导航到 **“样式”** 面板。  如果 DevTools 窗口较窄，则 **框模型** 图位于面板的底部。  

选择并编辑值以更改值。  

> [!NOTE]
> 下图中，**“样式”** 面板中的 **“框模型”** 图显示当前所选 `h1` 元素的框模型。  

:::image type="complex" source="../media/css-elements-styles-h1-2.msft.png" alt-text="框模型图" lightbox="../media/css-elements-styles-h1-2.msft.png":::
   **“框模型”** 图  
:::image-end:::  

### <a name="search-and-filter-the-css-of-an-element"></a>搜索和筛选元素的 CSS  

使用 **“样式”** 和 **“计算”** 面板上的 **“过滤器”** 文本框来搜索特定的 CSS 属性或值。  

若要在 **“计算”** 面板中同时搜索继承属性，请选中 **“全部显示”** 复选框。  

> [!NOTE]
> 下图中，筛选 **“样式”** 面板为只显示包含搜索查询的 `color` 规则。  

:::image type="complex" source="../media/css-elements-styles-filter-color.msft.png" alt-text="筛选“样式”面板" lightbox="../media/css-elements-styles-filter-color.msft.png":::
   筛选 **“样式”** 面板  
:::image-end:::  

> [!NOTE]
> 下图中，筛选 **“计算”** 面板以仅显示包含搜索查询 `100%` 的声明。  

:::image type="complex" source="../media/css-elements-computed-filter-100.msft.png" alt-text="筛选 “计算” 面板" lightbox="../media/css-elements-computed-filter-100.msft.png":::
   筛选 **“计算”** 面板  
:::image-end:::  

### <a name="toggle-a-pseudo-class"></a>切换伪类  

完成以下操作以切换如 `:active`、`:focus`、`:hover` 或 `:visited` 的伪类。  

1.  [选择元素](#choose-an-element)。  
1.  在 **“元素”** 工具上，导航到 **“样式”** 面板。  
1.  选择 **:hov**。  
1.  勾选要启用的伪类。  

> [!NOTE]
> 下图中，切换 `:hover` 伪类。  在视区中验证 `background-color: cornflowerblue` 声明是否正应用于该元素上，即使该元素实际上并未悬停。  

:::image type="complex" source="../media/css-elements-styles-hov-hover.msft.png" alt-text="切换 :hover 伪类" lightbox="../media/css-elements-styles-hov-hover.msft.png":::
   切换 `:hover` 伪类  
:::image-end:::  

对于交互式教程，请导航到 [“向类添加伪静态”][DevToolsCSSGetStartedAddPseudoState]。  

### <a name="view-a-page-in-print-mode"></a>在打印模式下查看页面  

在打印模式下完成以下操作以查看页面。  

1.  [打开“命令”菜单][DevToolsCommandMenu]。  
1.  开始键入 `Rendering` 并选择 `Show Rendering`。  
1.  对于 **“模拟 CSS 媒体”** 下拉菜单中，请选择 **打印**。  

### <a name="view-used-and-unused-css-with-the-coverage-tool"></a>使用覆盖工具查看已使用和未使用的 CSS  

**“覆盖”** 工具显示页面实际使用 CSS。  

1.  在 DevTools 处于焦点时，选择 `Control`+`Shift`+`P` \(Windows，Linux\) 或 `Command`+`Shift`+`P` \(macOS\) 时 [打开命令菜单][DevToolsCommandMenu]。  
1.  开始键入 `coverage` 并选择 **“显示范围”**。  出现 **“覆盖”** 工具。  
    
    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/css-console-command-menu-coverage.msft.png" alt-text="从命令菜单中打开 “覆盖” 工具" lightbox="../media/css-console-command-menu-coverage.msft.png":::
             从 **“命令”** 菜单中打开 **“覆盖”** 工具  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/css-console-qs-coverage-empty.msft.png" alt-text="“覆盖”工具" lightbox="../media/css-console-qs-coverage-empty.msft.png":::
             **覆盖**工具  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
1.  选择 **“开始仪表覆盖并刷新页面”** \(![开始仪表覆盖并刷新页面](../media/refresh-icon.msft.png)\)。  页面将刷新，**“覆盖”** 工具将提供浏览器加载的每个文件中使用多少 CSS \(和 JavaScript\) 的概述。  绿色表示已使用的 CSS。  红色表示未使用的 CSS。  
    
    :::image type="complex" source="../media/css-console-qs-coverage-run.msft.png" alt-text="已使用的和未使用的 CSS (和JavaScript) 的概述" lightbox="../media/css-console-qs-coverage-run.msft.png":::
       已使用的和未使用的 CSS \(和JavaScript\) 的概述  
    :::image-end:::  

1.  若要显示已使用 CSS 的逐行分类，请选择 CSS 文件。  
    
    > [!NOTE]
    > 在下图中， `b66bc881.site-ltr.css` 的 145 至 147 行和 149 至 151 行未使用，而 163 至 166 行已使用。  
    
    :::image type="complex" source="../media/css-sources-css-coverage.msft.png" alt-text="已使用和未使用 CSS 的逐行细目" lightbox="../media/css-sources-css-coverage.msft.png":::
       已使用和未使用 CSS 的逐行细目  
    :::image-end:::  
    
### <a name="force-print-preview-mode"></a>强制打印预览模式  

导航到 [“强制 DevTools 进入打印预览模式”][DevToolsCssPrintPreview]。  

## <a name="change-css"></a>更改 CSS  

<!-- todo s/CSS declaration/declaration/ -->  

### <a name="add-a-css-declaration-to-an-element"></a>向元素添加 CSS 声明  

声明顺序会影响元素的样式，请使用以下列表来帮助以不同方式添加声明。  

*   [添加内联声明](#add-an-inline-declaration)。  相当于向元素的 HTML 添加 `style` 属性。  
*   [向“样式规则”添加声明](#add-a-declaration-to-a-style-rule)。  

**该使用什么工作流?** 多数情况下，可能需要使用内联声明工作流。  内联声明具有比外部声明更高的特定性，因此内联工作流可确保更改在预期元素中生效。  有关特定性详细信息，请导航到 [“选择器类型”][MDNSelectorTypes]。  

如果要调试任何元素样式，并且需要专门测试在不同位置定义声明时的情况，请使用其他工作流。  

#### <a name="add-an-inline-declaration"></a>添加内联声明  

完成以下操作以添加内联声明。  

1.  [选择元素](#choose-an-element)。  
1.  在 **“样式”** 窗格中，选择 **element.style** 的括号。  光标聚焦，以允许输入文本。  
1.  输入属性名称，然后选择 `Enter`。  
1.  为该属性输入有效值，然后选择 `Enter`。  在 **DOM 树** 中，验证 `style` 属性是否已添加到元素中。  

> [!NOTE]
> 下图中，`margin-top` 和 `background-color` 属性已应用于所选元素。  在 **DOM 树** 验证声明是否反映在元素的 `style` 属性中。  

:::image type="complex" source="../media/css-elements-styles-margin-top-background-color.msft.png" alt-text="添加内联声明" lightbox="../media/css-elements-styles-margin-top-background-color.msft.png":::
   添加内联声明  
:::image-end:::  

#### <a name="add-a-declaration-to-a-style-rule"></a>向样式规则添加声明  

完成以下操作以将声明添加到现有样式规则中。  

1.  [选择元素](#choose-an-element)。  
1.  在 **“样式”** 窗格中，选择要添加声明的样式规则括号。  光标聚焦，以允许输入文本。  
1.  输入属性名称，然后选择 `Enter`。  
1.  为该属性输入有效值，然后选择 `Enter`。  

:::image type="complex" source="../media/css-elements-styles-border-bottom-style.msft.png" alt-text="正在向样式规则添加声明" lightbox="../media/css-elements-styles-border-bottom-style.msft.png":::
   将 `border-bottom-style:groove` 声明添加到样式规则  
:::image-end:::  

### <a name="change-a-declaration-name-or-value"></a>更改声明名称或值  

选择并编辑声明的名称或值以对其进行更改。  对于通过 `0.1`、`1`、`10` 或 `100` 单位以快速递增或递减值的快捷方式，请导航到 [“使用键盘快捷方式更改声明值”](#change-declaration-values-with-keyboard-shortcuts)。  

:::image type="complex" source="../media/css-elements-styles-border-bottom-style-dropdown.msft.png" alt-text="更改声明值" lightbox="../media/css-elements-styles-border-bottom-style-dropdown.msft.png":::
   更改 `border-bottom-style` 声明值  
:::image-end:::  

### <a name="change-declaration-values-with-keyboard-shortcuts"></a>使用键盘快捷方式更改声明值  

编辑声明的值时，可以使用以下键盘快捷方式将该值增加特定的数量。  

*   选择`Alt`+`Up` \(Windows，Linux\) 或 `Option`+`Up` \(macOS\) 按 `0.1` 增量。  
*   选择 `Up` 按 `1` 改变数值，如果当前值介于 `-1` 和 `1` 之间则按 `0.1` 改变。  
*   选择 `Shift`+`Up` 按 `10` 增量。  
*   选择 `Shift`+`Page Up` \(Windows，Linux\) 或 `Shift`+`Command`+`Up` \(macOS\) 按 `100` 增量。  

缩量也可以。  只要把上面提到的 `Up` 的每个实例都换成 `Down` 即可。  

### <a name="add-a-class-to-an-element"></a>向元素添加类  

完成以下操作以向元素添加类。  

1.  在 ** DOM 树** 中 [选择元素](#choose-an-element)。  
1.  选择 **.cls**。  
1.  在 **“添加新类”** 文本框中输入类的名称。  
1.  选择 `Enter`。  

:::image type="complex" source="../media/css-elements-styles-filter-classes.msft.png" alt-text="“元素课堂”窗格" lightbox="../media/css-elements-styles-filter-classes.msft.png":::
   **“元素课堂”** 窗格  
:::image-end:::  

### <a name="toggle-a-class"></a>切换类  

完成以下操作以启用或禁用元素上的类。  

1.  在 ** DOM 树** 中 [选择元素](#choose-an-element)。  
1.  打开 **“元素类”** 窗格。  导航到 [向元素添加类](#add-a-class-to-an-element)。  在 **“添加新类”** 文本框下方是应用于特定元素的所有类。  
1.  切换要打开或关闭类旁边的复选框。  

### <a name="add-a-style-rule"></a>添加样式规则  

完成以下操作以添加新样式规则。  

1.  [选择元素](#choose-an-element)。  
1.  选择 **“新样式规则”** \(![新样式规则](../media/new-style-rule-icon.msft.png)\)。  DevTools 在 **element.style** 规则下方插入新规则。  

> [!NOTE]
> 下图中，DevTools 在选择 **“新样式规则”** 后添加 `h1.devsite-page-title` 样式规则。  

:::image type="complex" source="../media/css-elements-styles-style-new.msft.png" alt-text="添加新的样式规则" lightbox="../media/css-elements-styles-style-new.msft.png":::
   添加新的样式规则  
:::image-end:::  

#### <a name="choose-which-stylesheet-to-add-a-rule-to"></a>选择要添加规则的样式表  

[添加新样式规则](#add-a-style-rule)时，选择并按住 **“新样式规则”** \(![新样式规则](../media/new-style-rule-icon.msft.png)\) 以选择要添加样式规则的样式表。  

:::image type="complex" source="../media/css-elements-styles-style-new-select-existing.msft.png" alt-text="选择样式表" lightbox="../media/css-elements-styles-style-new-select-existing.msft.png":::
   选择样式表  
:::image-end:::  

#### <a name="add-a-style-rule-to-a-specific-location"></a>向特定位置添加样式规则  

完成以下操作以将样式规则添加到 **“样式“** 面板的特定位置。  

1.  将鼠标悬停在要添加新样式规则正上方的样式规则上。  
1.  [显示 **“更多操作”** 工具栏](#reveal-the-more-actions-toolbar)。  
1.  选择 **插入“样式规则”** \(![在图标下方插入样式规则](../media/new-style-rule-icon.msft.png)\)。  

:::image type="complex" source="../media/css-elements-styles-insert-style-rule-below.msft.png" alt-text="在下方插入样式规则" lightbox="../media/css-elements-styles-insert-style-rule-below.msft.png":::
   **在下方插入样式规则**  
:::image-end:::  

### <a name="reveal-the-more-actions-toolbar"></a>显示“更多操作”工具栏  

通过 **“更多操作”** 工具栏，可执行以下操作。  

*   直接在所关注样式规则下面插入样式规则。  
*   向所关注的样式规则添加`background-color`、`color`、`box-shadow` 或 `text-shadow` 声明。  

完成以下操作以显示 **“更多操作”** 工具栏。  

1.  在 **“样式”** 面板中，将鼠标悬停在样式规则上。  在样式规则部分的右下角显示 **“更多操作”** \(`...`\)。  
    
    > [!NOTE]
    > 下图中，将鼠标悬停在 `.header-holder.has-default-focus` 样式规则上，在样式规则部分的右下方会显示出 **“更多操作”**。  
    
    :::image type="complex" source="../media/css-elements-styles-new-rule-styles.msft.png" alt-text="显示“更多操作”" lightbox="../media/css-elements-styles-new-rule-styles.msft.png":::
       显示 **“更多操作”** \(`...`\)  
    :::image-end:::  
    
1.  将鼠标停留在 **“更多行动”** \(`...`\) 上，可以看到上面提到的操作。  
    
    > [!NOTE]
    > 将鼠标悬停在 **“更多动作“** 上，就会显示出 **“下方插入样式规则”** 操作。  
    
    :::image type="complex" source="../media/css-elements-styles-rule-more-options-insert-style-rule-below.msft.png" alt-text="“更多操作”工具栏" lightbox="../media/css-elements-styles-rule-more-options-insert-style-rule-below.msft.png":::
       **“更多操作”** 工具栏  
    :::image-end:::  
    
### <a name="toggle-a-declaration"></a>切换声明  

完成下面的操作来切换单个声明的开启 (或关闭)。  

1.  [选择元素](#choose-an-element)。  
1.  在 **“样式”** 窗格中，将鼠标悬停在定义声明的规则上。  每个声明旁边将显示复选框。  
1.  选中 \(或取消选中\) 声明旁边的复选框。  取消选中声明时，DevTools 会将它划掉，表示它不再是活跃。  

> [!NOTE]
> 下图中，当前选中元素的 `margin-top` 属性已关闭。  

:::image type="complex" source="../media/css-elements-styles-rule-deactivated.msft.png" alt-text="切换声明" lightbox="../media/css-elements-styles-rule-deactivated.msft.png":::
   切换声明  
:::image-end:::  

### <a name="add-a-background-color-declaration"></a>添加背景色声明  

完成以下操作，向元素添加 `background-color` 声明。  

1.  将鼠标悬停在要添加 `background-color` 声明的样式规则上。  
1.  [显示 **“更多操作”** 工具栏](#reveal-the-more-actions-toolbar)。  
1.  选择 **“添加背景色”** \(![添加背景色图标](../media/add-background-color-icon.msft.png)\)。  

:::image type="complex" source="../media/css-elements-styles-rule-add-background-color.msft.png" alt-text="背景色" lightbox="../media/css-elements-styles-rule-add-background-color.msft.png":::
   **背景色**  
:::image-end:::  

### <a name="add-a-color-declaration"></a>添加颜色声明  

完成以下操作，向元素添加 `color` 声明。  

1.  将鼠标悬停在要添加 `color` 声明的样式规则上。  
1.  [显示 **“更多操作”** 工具栏](#reveal-the-more-actions-toolbar)。  
1.  选择 **“添加颜色”** \(![添加颜色图标](../media/add-color-icon.msft.png)\)。  

:::image type="complex" source="../media/css-elements-styles-rule-add-color.msft.png" alt-text="添加颜色" lightbox="../media/css-elements-styles-rule-add-color.msft.png":::
   **添加颜色**  
:::image-end:::  

### <a name="add-a-box-shadow-declaration"></a>添加框阴影声明  

完成以下操作以向元素添加 `box-shadow` 声明。  

1.  将鼠标悬停在要添加 `box-shadow` 声明的样式规则上。  
1.  [显示 **“更多操作”** 工具栏](#reveal-the-more-actions-toolbar)。  
1.  选择 **添加狂阴影** \(![添加框阴影图标](../media/add-box-shadow-icon.msft.png)\)。  

:::image type="complex" source="../media/css-elements-styles-rule-add-box-shadow.msft.png" alt-text="添加框阴影" lightbox="../media/css-elements-styles-rule-add-box-shadow.msft.png":::
   **添加框阴影**  
:::image-end:::  

### <a name="add-a-text-shadow-declaration"></a>添加文本阴影声明  

完成以下操作，向元素添加 `text-shadow` 声明。  

1.  将鼠标悬停在要添加 `text-shadow` 声明的样式规则上。  
1.  [显示 **“更多操作”** 工具栏](#reveal-the-more-actions-toolbar)。  
1.  选择 **“添加文本阴影”** \(![添加文本阴影图标](../media/add-text-shadow-icon.msft.png)\)。  

:::image type="complex" source="../media/css-elements-styles-rule-add-text-shadow.msft.png" alt-text="添加文字阴影" lightbox="../media/css-elements-styles-rule-add-text-shadow.msft.png":::
   **添加文字阴影**  
:::image-end:::  

### <a name="change-colors-with-the-color-picker"></a>使用颜色选取器更改颜色  

**颜色选取器** 为更改 `color` 和 `background-color` 声明提供 GUI。  

完成以下操作以打开 **“颜色选取器”**。  

1.  [选择元素](#choose-an-element)。  
1.  在 **“样式”** 面板中，找到 `color`、`background-color` 或要更改的类似声明。  在 `color`、`background-color` 或类似值左侧有个颜色预览的小方块。  
    
    > [!NOTE]
    > 下图中，`rgba(0, 0, 0, 0.7)` 左侧的小方块是该颜色的预览。  
    
    :::image type="complex" source="../media/css-elements-styles-rule-overlay-color-box.msft.png" alt-text="颜色预览" lightbox="../media/css-elements-styles-rule-overlay-color-box.msft.png":::
       颜色预览  
    :::image-end:::  
    
1.  选择预览以打开 **颜色选取器**。  
    
    :::image type="complex" source="../media/css-elements-styles-rule-color-picker.msft.png" alt-text="颜色选取器" lightbox="../media/css-elements-styles-rule-color-picker.msft.png":::
       **颜色选取器**  
    :::image-end:::  
    
下图和列表介绍了了每个 **颜色选取器** 的 UI 元素。  

:::image type="complex" source="../media/css-elements-styles-rule-color-picker-annotated.msft.png" alt-text="颜色选取器，已批注" lightbox="../media/css-elements-styles-rule-color-picker-annotated.msft.png":::
   **颜色选取器**，已批注  
:::image-end:::  

:::row:::
   :::column span="1":::
      1  
   :::column-end:::
   :::column span="1":::
      **色调**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      2  
   :::column-end:::
   :::column span="1":::
      **取色器**  
   :::column-end:::
   :::column span="2":::
      有关详细信息，请导航到 [用“取色器“在页面上打样着色](#sample-a-color-off-the-page-with-the-eyedropper)。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      3  
   :::column-end:::
   :::column span="1":::
      **复制到剪贴板**  
   :::column-end:::
   :::column span="2":::
      将 **“显示值”** 复制到剪贴板。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      4  
   :::column-end:::
   :::column span="1":::
      **显示值**  
   :::column-end:::
   :::column span="2":::
      颜色的 RGBA、HSLA 或十六进制表示形式。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      5  
   :::column-end:::
   :::column span="1":::
      **调色板**  
   :::column-end:::
   :::column span="2":::
      选择其中一个方块以更改该方块的颜色。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      6  
   :::column-end:::
   :::column span="1":::
      **色调**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      7  
   :::column-end:::
   :::column span="1":::
      **不透明度**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      8  
   :::column-end:::
   :::column span="1":::
      **显示值切换器**  
   :::column-end:::
   :::column span="2":::
      在当前颜色的 RGBA、HSLA 和十六进制表示形式之间切换。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      9  
   :::column-end:::
   :::column span="1":::
      **调色板切换器**  
   :::column-end:::
   :::column span="2":::
      在 [“材质设计调色板”][MaterialDesignColorSystem]、“自定义调色板”或“页面颜色调色板”之间切换。  DevTools 根据在样式表中所找到的颜色来生成页面调色板。  
   :::column-end:::
:::row-end:::  

#### <a name="sample-a-color-off-the-page-with-the-eyedropper"></a>用“取色器“在页面上打样着色  

打开 **“颜色选取器”** 时，**“取色器”** \(![取色器](../media/eyedropper-icon.msft.png)\) 默认打开。  完成以下操作，可将页面上的所选颜色改为其他颜色。  

1.  将鼠标悬停在视区中的目标颜色上。  
1.  选择以确认。  
    
    > [!NOTE]
    > 下图中，**“颜色选取器”** 显示接近黑色的电流 `rgba(0,0,0,0.7)` 颜色值。  特定的颜色应该更改为在你选择后变为当前视区中高亮的黑色版本。  
    
    :::image type="complex" source="../media/css-color-picker-eye-dropper.msft.png" alt-text="使用取色器" lightbox="../media/css-color-picker-eye-dropper.msft.png":::
       使用取色器  
    :::image-end:::  
    
<!--todo:  add the section on the Angle clock section for What's New 88.  -->  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge 开发工具团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsCommandMenu]: ../command-menu/index.md "使用 Microsoft Edge 开发工具命令菜单运行命令 | Microsoft Docs"  
[DevToolsCSSGetStarted]: ../css/index.md "查看和更改 CSS 入门 | Microsoft 文档 | Microsoft Docs"  
[DevToolsCSSGetStartedAddPseudoState]: ../css/index.md#add-a-pseudostate-to-a-class " 向类添加伪状态 - 查看和更改 CSS 入门 | Microsoft Docs"  
[DevToolsCSSGetStartedTutorial]: ../css/index.md#view-the-css-for-an-element "查看元素的 CSS - 查看和更改 CSS 入门 | Microsoft Docs"  
[DevToolsCssPrintPreview]: ../css/print-preview.md "强制 Microsoft Edge DevTools 进入打印预览模式(CSS 打印媒体类型) | Microsoft Docs"  
[DevToolsJavascriptReferenceFormat]: ../javascript/reference.md#reformat-a-minified-javascript-file-with-pretty-print "重新设置缩小的 JavaScript 文件，并采用非常打印的字体 - 使用调试器|Microsoft Docs"  

[MaterialDesignColorSystem]: https://material.io/guidelines/style/color.html#color-color-palette "颜色系统 - 材料设计"  
[MDNBoxModel]: https://developer.mozilla.org/docs/Learn/CSS/Introduction_to_CSS/Box_model "框模型 | MDN"  
[MDNSelectorTypes]: https://developer.mozilla.org/docs/Web/CSS/Specificity#Selector_Types "选择器类型 - 特异性 | MDN"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/css/reference)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  