---
description: 了解在 Microsoft Edge DevTools 中查看和更改 CSS 的新工作流。
title: CSS 参考
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 707841901046db6a7e957771164ffb868900bdd8
ms.sourcegitcommit: 080759f68a0a158f10dc20d20c14e222ace1be84
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "11190010"
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

# CSS 参考  

在以下有关 Microsoft Edge DevTools 功能的完整参考中发现新工作流，这些功能与查看和更改 CSS 相关。  

请参阅 [查看和更改 CSS 开始][DevToolsCSSGetStarted] 了解基础知识。  

## 选择一个元素  

DevTools 的 " **元素** " 面板使你可以一次查看或更改一个元素的 CSS。  所选元素在 **DOM 树**中突出显示。  元素的样式显示在 " **样式** " 窗格中。  请参阅查看教程的 [元素的 CSS][DevToolsCSSGetStartedTutorial] 。  

> [!NOTE]
> 在下图中，在 `h1` **DOM 树** 中突出显示的元素是所选元素。  在右侧，元素的样式显示在 " **样式** " 窗格中。  在左侧，元素在视区中突出显示，但仅因为鼠标当前在 **DOM 树**中悬停在其上方。  

:::image type="complex" source="../media/css-elements-styles-h1.msft.png" alt-text="所选元素的示例" lightbox="../media/css-elements-styles-h1.msft.png":::
   所选元素的示例  
:::image-end:::  

使用下列操作之一选择一个元素。  

*   在视区中，将鼠标悬停在元素上，打开上下文菜单 \ (右键单击 "\ ) "，然后选择 " **检查**"。  
*   在 DevTools 中，选择 "**选择元素**\ (![ 选择元素 ][ImageSelectAnElementIcon] \ ) 或选择 `Control` + `Shift` + `C` \ (Windows、Linux \ ) 或 `Command` + `Shift` + `C` \ (macOS \ ) "，然后选择视区中的元素。  
*   在 DevTools 中，选择 **DOM 树**中的元素。  
*   在 DevTools 中，运行一个如 `document.querySelector('p')` 在 **控制台**中的查询，将鼠标悬停在结果上，打开上下文菜单 \ (右键单击 "\ ) "，然后选择 **"在元素中显示" 面板**。  

## 查看 CSS  

### 查看定义规则的外部样式表  

在 " **样式** " 窗格中，选择 CSS 规则旁边的链接以打开定义该规则的外部样式表。  

如果样式表是 minified，请导航以 [使 minified 文件易于阅读][DevToolsJavascriptReferenceFormat]。  

> [!NOTE]
> 在下图中，选择 " `https://docs.microsoft.com/_themes/docs.theme/master/en-us/_themes/styles/b66bc881.site-ltr.css:2` 转到" 第2行 `https://docs.microsoft.com/_themes/docs.theme/master/en-us/_themes/styles/b66bc881.site-ltr.css` ，其中 `.content h1:first-of-type` 定义了 CSS 规则。  

<!--todo:  replace "Master" phrasing in code snippet, if possible.  -->  

:::image type="complex" source="../media/css-elements-styles-h1-highlight.msft.png" alt-text="查看定义规则的样式表" lightbox="../media/css-elements-styles-h1-highlight.msft.png":::
  查看定义规则的样式表  
:::image-end:::  

### 仅查看实际应用到元素的 CSS  

" **样式** " 选项卡显示适用于元素的所有规则，包括已重写的声明。  当你对替代声明不感兴趣时，请使用 " **计算** " 选项卡仅查看实际应用于元素的 CSS。  

1.  [选择一个元素](#select-an-element)。  
1.  转到 "**元素**" 面板中的 "**计算**" 选项卡。  

> [!NOTE]
> 在宽 DevTools 窗口中， **计算** 的选项卡不存在。  **计算**的选项卡的内容显示在 "**样式**" 选项卡上。  

继承的属性是不透明的。  选中 " **全部显示** " 复选框以查看所有继承值。  

> [!NOTE]
> 在下图中，" **计算** " 选项卡显示应用于当前所选元素的 CSS 属性 `h1` 。  

:::image type="complex" source="../media/css-elements-computed-h1.msft.png" alt-text="计算选项卡" lightbox="../media/css-elements-computed-h1.msft.png":::
   **计算**选项卡  
:::image-end:::  

### 按字母顺序查看 CSS 属性  

使用 " **计算** " 选项卡。 请参阅 [仅查看实际应用到元素的 CSS](#view-only-the-css-that-is-actually-applied-to-an-element)。  

### 查看继承的 CSS 属性  

选中 "**计算**" 选项卡中的 "**全部显示**" 复选框。 请参阅[仅查看实际应用到元素的 CSS](#view-only-the-css-that-is-actually-applied-to-an-element)。  

### 查看元素的 box 模型  

若要查看元素 [的方框模型][MDNBoxModel] ，请转到 " **样式** " 选项卡。 如果 DevTools 窗口较窄，则 **框模型** 图位于选项卡的底部。  

选择并编辑值以更改值。  

> [!NOTE]
> 在下图中，"**样式**" 选项卡中的 "**方框模型**" 图显示了当前所选元素的框模型 `h1` 。  

:::image type="complex" source="../media/css-elements-styles-h1-2.msft.png" alt-text="方框模型图" lightbox="../media/css-elements-styles-h1-2.msft.png":::
   **方框模型**图  
:::image-end:::  

### 搜索和筛选元素的 CSS  

使用 "**样式**" 和 "**计算**" 选项卡上的 "**筛选器**" 文本框搜索特定的 CSS 属性或值。  

若要同时在 " **计算** " 选项卡中搜索继承的属性，请选中 " **全部显示** " 复选框。  

> [!NOTE]
> 在下图中，筛选 " **样式** " 选项卡以仅显示包含搜索查询的规则 `color` 。  

:::image type="complex" source="../media/css-elements-styles-filter-color.msft.png" alt-text="筛选 "样式" 选项卡" lightbox="../media/css-elements-styles-filter-color.msft.png":::
   筛选 " **样式** " 选项卡  
:::image-end:::  

> [!NOTE]
> 在下图中，" **计算** " 选项卡将筛选为仅显示包含 "搜索" 查询的声明 `100%` 。  

:::image type="complex" source="../media/css-elements-computed-filter-100.msft.png" alt-text="筛选计算的选项卡" lightbox="../media/css-elements-computed-filter-100.msft.png":::
   筛选 **计算** 的选项卡  
:::image-end:::  

### 切换伪类  

完成以下操作，以切换伪类 `:active` ，如、 `:focus` 、 `:hover` 或 `:visited` 。  

1.  [选择一个元素](#select-an-element)。  
1.  在 " **元素** " 面板上，转到 " **样式** " 选项卡。  
1.  选择 **： hov**。  
1.  检查要启用的伪类。  

> [!NOTE]
> 在下图中，切换 `:hover` 伪类。  在视区中，验证 `background-color: cornflowerblue` 是否将声明应用于该元素，即使该元素实际上不是悬停在该元素上。  

:::image type="complex" source="../media/css-elements-styles-hov-hover.msft.png" alt-text="切换：悬停伪类" lightbox="../media/css-elements-styles-hov-hover.msft.png":::
   切换 `:hover` 伪类  
:::image-end:::  

对于交互式教程，请导航到 [将伪状态添加到类][DevToolsCSSGetStartedAddPseudoState]。  

### 在打印模式下查看页面  

完成以下操作以在打印模式下查看页面。  

1.  [打开 "命令" 菜单][DevToolsCommandMenu]。  
1.  开始键入 `Rendering` 并选择 `Show Rendering` 。  
1.  对于 " **模拟 CSS 媒体** " 下拉列表，选择 " **打印**"。  

### 使用 "覆盖范围" 选项卡查看使用和未使用的 CSS  

"覆盖范围" 选项卡显示页面实际使用的 CSS。  

1.  选择 `Control` + `Shift` + `P` \ (Windows、Linux \ ) 或 `Command` + `Shift` + `P` \ (macOS \ ) 当 DevTools 处于焦点时[打开 "命令" 菜单][DevToolsCommandMenu]。  
1.  开始键入 `coverage` ，然后选择 " **显示覆盖率**"。  将显示 "覆盖范围" 选项卡。  
    
    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/css-console-command-menu-coverage.msft.png" alt-text="从 "命令" 菜单打开 "覆盖范围" 选项卡" lightbox="../media/css-console-command-menu-coverage.msft.png":::
             从 "**命令" 菜单**打开 "**覆盖范围**" 选项卡  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/css-console-qs-coverage-empty.msft.png" alt-text=""覆盖范围" 选项卡" lightbox="../media/css-console-qs-coverage-empty.msft.png":::
             " **覆盖范围** " 选项卡  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
1.  选择 " **开始检测覆盖率" 并刷新页面** \ (" ![ 开始检测覆盖率" 并刷新页面 ][ImageRefreshIcon] \ ) 。  页面刷新，"覆盖率" 选项卡提供浏览器加载的每个文件中使用的 CSS \ (和 JavaScript ) 的概述。  绿色表示使用的 CSS。  红色表示未使用的 CSS。  
    
    :::image type="complex" source="../media/css-console-qs-coverage-run.msft.png" alt-text="有关使用和未使用的 CSS (和 JavaScript) 数量的概述" lightbox="../media/css-console-qs-coverage-run.msft.png":::
       有关使用和未使用的 CSS \ (和 JavaScript \ ) 多少的概述  
    :::image-end:::  

1.  选择一个 CSS 文件以查看逐行分解它所使用的 CSS。  
    
    > [!NOTE]
    > 在下图中，行145到147和149到 151 `b66bc881.site-ltr.css` 未使用，而使用行163到166。  
    
    :::image type="complex" source="../media/css-sources-css-coverage.msft.png" alt-text="已使用和未使用的 CSS 的逐行划分" lightbox="../media/css-sources-css-coverage.msft.png":::
       已使用和未使用的 CSS 的逐行划分  
    :::image-end:::  
    
### 强制打印预览模式  

请参阅 [强制 DevTools 进入打印预览模式][DevToolsCssPrintPreview]。  

## 更改 CSS  

<!-- todo s/CSS declaration/declaration/ -->  

### 向元素添加 CSS 声明  

声明顺序影响元素的样式，使用以下列表可帮助你以不同的方式添加声明。  

*   [添加内联声明](#add-an-inline-declaration)。  等效于将 `style` 属性添加到元素的 HTML。  
*   [将声明添加到样式规则](#add-a-declaration-to-a-style-rule)。  

**应该使用哪个工作流？** 在大多数情况下，你可能希望使用内联声明工作流。  内联声明具有比外部声明更高的程度，因此内联工作流可确保所做的更改会在你的预期元素中生效。  有关具体程度的详细信息，请导航到 [选择器类型][MDNSelectorTypes]。  

如果你正在调试元素的任何样式，并且你需要专门测试在不同位置定义声明时所发生的情况，请使用其他工作流。  

#### 添加内联声明  

完成以下操作以添加内联声明。  

1.  [选择一个元素](#select-an-element)。  
1.  在 " **样式** " 窗格中，选择元素的方括号 **。 "样式** " 部分。  光标焦点，允许您输入文本。  
1.  输入属性名称，然后选择 `Enter` 。  
1.  输入该属性的有效值，然后选择 `Enter` 。  在 **DOM 树**中，验证是否已将某个 `style` 属性添加到该元素。  

> [!NOTE]
> 在下图中，"" `margin-top` 和 " `background-color` 属性" 已应用于所选元素。  在 **DOM 树** 中，验证声明是否反映在元素的 `style` 属性中。  

:::image type="complex" source="../media/css-elements-styles-margin-top-background-color.msft.png" alt-text="添加内联声明" lightbox="../media/css-elements-styles-margin-top-background-color.msft.png":::
   添加内联声明  
:::image-end:::  

#### 将声明添加到样式规则  

完成以下操作以将声明添加到现有样式规则。  

1.  [选择一个元素](#select-an-element)。  
1.  在 " **样式** " 窗格中，选择要向其中添加声明的样式规则的括号。  光标焦点，允许您输入文本。  
1.  输入属性名称，然后选择 `Enter` 。  
1.  输入该属性的有效值，然后选择 `Enter` 。  

:::image type="complex" source="../media/css-elements-styles-border-bottom-style.msft.png" alt-text="将声明添加到样式规则" lightbox="../media/css-elements-styles-border-bottom-style.msft.png":::
   将 `border-bottom-style:groove` 声明添加到样式规则  
:::image-end:::  

### 更改声明名称或值  

选择并编辑声明的名称或值，以对其进行更改。  请参阅使用快捷键的 [键盘快捷方式更改声明值](#change-declaration-values-with-keyboard-shortcuts) ，快速将值按 `0.1` 、、 `1` `10` 或单位递减或递减 `100` 。  

:::image type="complex" source="../media/css-elements-styles-border-bottom-style-dropdown.msft.png" alt-text="更改声明的值" lightbox="../media/css-elements-styles-border-bottom-style-dropdown.msft.png":::
   更改声明的值 `border-bottom-style`  
:::image-end:::  

### 通过键盘快捷方式更改声明值  

编辑声明的值时，可以使用以下键盘快捷方式将值增加一个特定的量。  

*   选择 `Alt` + `Up` \ (Windows、Linux \ ) 或 `Option` + `Up` \ (macOS \ ) 递增 `0.1` 。  
*   选择 `Up` 以更改值 `1` ，或者 `0.1` 如果当前值介于和之间，则选择此值 `-1` `1` 。  
*   选择 " `Shift` + `Up` 增加方式" `10` 。  
*   选择 `Shift` + `Page Up` \ (Windows、Linux \ ) 或 `Shift` + `Command` + `Up` \ (macOS \ ) 将值增加 `100` 。  

减量也有效。  只需将上面提及的每个实例替换 `Up` 为 `Down` 。  

### 向元素添加类  

完成以下操作以将类添加到元素。  

1.  在**DOM 树**中[选择该元素](#select-an-element)。  
1.  选择 **. cls**。  
1.  在 " **添加新类** " 文本框中输入类的名称。  
1.  选择 `Enter` 。  

:::image type="complex" source="../media/css-elements-styles-filter-classes.msft.png" alt-text=""元素类" 窗格" lightbox="../media/css-elements-styles-filter-classes.msft.png":::
   " **元素类** " 窗格  
:::image-end:::  

### 切换类  

完成以下操作以在元素上启用或禁用类。  

1.  在**DOM 树**中[选择该元素](#select-an-element)。  
1.  打开 " **元素类** " 窗格。  请参阅 [向元素添加类](#add-a-class-to-an-element)。  在 " **添加新类** " 文本框下方是应用于特定元素的所有类。  
1.  切换要启用或禁用的类旁边的复选框。  

### 添加样式规则  

完成以下操作以添加新的样式规则。  

1.  [选择一个元素](#select-an-element)。  
1.  选择 " **新建样式规则** \ (![ 新样式规则 ][ImageNewStyleRuleIcon] \ ) "。  DevTools 在元素下方插入新规则 **。 style** 规则。  

> [!NOTE]
> 在下图中，DevTools 将添加 `h1.devsite-page-title` 样式规则，然后选择 " **新建样式规则**"。  

:::image type="complex" source="../media/css-elements-styles-style-new.msft.png" alt-text="添加新样式规则" lightbox="../media/css-elements-styles-style-new.msft.png":::
   添加新样式规则  
:::image-end:::  

#### 选择要向其添加规则的样式表  

[添加新样式规则](#add-a-style-rule)时，选择并保留**新的样式**规则 \ (" ![ 新建样式规则 \ ) "，选择要向 ][ImageNewStyleRuleIcon] 其添加样式规则的样式表。  

:::image type="complex" source="../media/css-elements-styles-style-new-select-existing.msft.png" alt-text="选择样式表" lightbox="../media/css-elements-styles-style-new-select-existing.msft.png":::
   选择样式表  
:::image-end:::  

#### 将样式规则添加到特定位置  

完成以下操作，将样式规则添加到 " **样式** " 选项卡中的特定位置。  

1.  将鼠标悬停在要添加新样式规则的正上方的样式规则上。  
1.  [显示 " **更多操作** " 工具栏](#reveal-the-more-actions-toolbar)。  
1.  选择 **下方的 "插入样式规则** \ (" ![ 下的 "插入样式规则" 图标 ][ImageNewStyleRuleIcon] \ ) 。  

:::image type="complex" source="../media/css-elements-styles-insert-style-rule-below.msft.png" alt-text="在下方插入样式规则" lightbox="../media/css-elements-styles-insert-style-rule-below.msft.png":::
   **在下方插入样式规则**  
:::image-end:::  

### 显示 "更多操作" 工具栏  

" **更多操作** " 工具栏使您可以执行以下操作。  

*   直接在你的重点所在的下插入样式规则。  
*   向 `background-color` `color` `box-shadow` 你关注的样式规则添加、、或 `text-shadow` 声明。  

完成以下操作以显示 " **更多操作** " 工具栏。  

1.  在 " **样式** " 选项卡中，将鼠标悬停在样式规则上。  **More Actions** `...` "样式规则" 部分右下角显示了 "更多操作 \ (\ ) "。  
    
    > [!NOTE]
    > 在下图中，将鼠标悬停在 `.header-holder.has-default-focus` 样式规则上方，并显示 "样式规则" 部分右下角的 " **更多操作** "。  
    
    :::image type="complex" source="../media/css-elements-styles-new-rule-styles.msft.png" alt-text="显示更多操作" lightbox="../media/css-elements-styles-new-rule-styles.msft.png":::
       显示 **更多操作** \ (`...` \ )   
    :::image-end:::  
    
1.  将鼠标悬停在 " **更多操作** " 上 \ (`...` \ ) 以显示上述操作。  
    
    > [!NOTE]
    > 将鼠标悬停在**更多操作**之后，将显示 "**下方的插入样式规则**" 操作。  
    
    :::image type="complex" source="../media/css-elements-styles-rule-more-options-insert-style-rule-below.msft.png" alt-text=""更多操作" 工具栏" lightbox="../media/css-elements-styles-rule-more-options-insert-style-rule-below.msft.png":::
       " **更多操作** " 工具栏  
    :::image-end:::  
    
### 切换声明  

完成 folllwoing 操作以切换 \ (或 off \ ) 上的单个声明。  

1.  [选择一个元素](#select-an-element)。  
1.  在 " **样式** " 窗格中，将鼠标悬停在定义声明的规则上方。  每个声明旁边都会显示一个复选框。  
1.  选中 \ (或取消选中 \ ) 声明旁边的复选框。  取消选中某个声明后，DevTools 将其置于外，以指示它不再处于活动状态。  

> [!NOTE]
> 下图中， `margin-top` 当前所选元素的属性已关闭。  

:::image type="complex" source="../media/css-elements-styles-rule-deactivated.msft.png" alt-text="切换声明" lightbox="../media/css-elements-styles-rule-deactivated.msft.png":::
   切换声明  
:::image-end:::  

### 添加背景色声明  

完成以下操作以将声明添加 `background-color` 到元素。  

1.  将鼠标悬停在要向其添加声明的样式规则上 `background-color` 。  
1.  [显示 " **更多操作** " 工具栏](#reveal-the-more-actions-toolbar)。  
1.  选择 " **添加背景色** \ (![ 添加背景颜色" 图标 ][ImageAddBackgroundColorIcon] \ ) 。  

:::image type="complex" source="../media/css-elements-styles-rule-add-background-color.msft.png" alt-text="添加背景色" lightbox="../media/css-elements-styles-rule-add-background-color.msft.png":::
   **添加背景色**  
:::image-end:::  

### 添加颜色声明  

完成以下操作以将声明添加 `color` 到元素。  

1.  将鼠标悬停在要向其添加声明的样式规则上 `color` 。  
1.  [显示 " **更多操作** " 工具栏](#reveal-the-more-actions-toolbar)。  
1.  选择 " **添加颜色** \" (" ![ 添加颜色" 图标 ][ImageAddColorIcon] \ ) 。  

:::image type="complex" source="../media/css-elements-styles-rule-add-color.msft.png" alt-text="添加颜色" lightbox="../media/css-elements-styles-rule-add-color.msft.png":::
   **添加颜色**  
:::image-end:::  

### 添加 box-阴影声明  

完成以下操作以将声明添加 `box-shadow` 到元素。  

1.  将鼠标悬停在要向其添加声明的样式规则上 `box-shadow` 。  
1.  [显示 " **更多操作** " 工具栏](#reveal-the-more-actions-toolbar)。  
1.  选择 **"添加框阴影** \ (![ 添加框阴影图标 ][ImageAddBoxShadowIcon] \ ) "。  

:::image type="complex" source="../media/css-elements-styles-rule-add-box-shadow.msft.png" alt-text="添加框阴影" lightbox="../media/css-elements-styles-rule-add-box-shadow.msft.png":::
   **添加框阴影**  
:::image-end:::  

### 添加文本阴影声明  

完成以下操作以将声明添加 `text-shadow` 到元素。  

1.  将鼠标悬停在要向其添加声明的样式规则上 `text-shadow` 。  
1.  [显示 " **更多操作** " 工具栏](#reveal-the-more-actions-toolbar)。  
1.  选择 " **添加文本阴影** \ (![ 添加文字阴影图标 ][ImageAddTextShadowIcon] \ ) "。  

:::image type="complex" source="../media/css-elements-styles-rule-add-text-shadow.msft.png" alt-text="添加文本阴影" lightbox="../media/css-elements-styles-rule-add-text-shadow.msft.png":::
   **添加文本阴影**  
:::image-end:::  

### 使用颜色选取器更改颜色  

**颜色选取器**提供了用于更改 `color` 和声明的 GUI `background-color` 。  

完成以下操作以打开 " **拾色器**"。  

1.  [选择一个元素](#select-an-element)。  
1.  在 " **样式** " 选项卡中，找到 `color` `background-color` 要更改的、或类似的声明。  在 " `color` 、" `background-color` 或 "类似" 值的左侧，有一个小方块，它是颜色的预览。  
    
    > [!NOTE]
    > 在下图中，左侧的小方块 `rgba(0, 0, 0, 0.7)` 是该颜色的预览。  
    
    :::image type="complex" source="../media/css-elements-styles-rule-overlay-color-box.msft.png" alt-text="颜色预览" lightbox="../media/css-elements-styles-rule-overlay-color-box.msft.png":::
       颜色预览  
    :::image-end:::  
    
1.  选择 "预览" 以打开 " **颜色选取器**"。  
    
    :::image type="complex" source="../media/css-elements-styles-rule-color-picker.msft.png" alt-text="颜色选取器" lightbox="../media/css-elements-styles-rule-color-picker.msft.png":::
       **颜色选取器**  
    :::image-end:::  
    
下图，并列出了 **颜色选取器**的每个 UI 元素的 descries。  

:::image type="complex" source="../media/css-elements-styles-rule-color-picker-annotated.msft.png" alt-text="颜色选取器，批注" lightbox="../media/css-elements-styles-rule-color-picker-annotated.msft.png":::
   **颜色选取器**，批注  
:::image-end:::  

:::row:::
   :::column span="1":::
      raid-1  
   :::column-end:::
   :::column span="1":::
      **阴影**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      ppls-2  
   :::column-end:::
   :::column span="1":::
      **变成**  
   :::column-end:::
   :::column span="2":::
      有关详细信息，请 [使用取色](#sample-a-color-off-the-page-with-the-eyedropper)器导航到页面上的颜色示例。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      三维空间  
   :::column-end:::
   :::column span="1":::
      **复制到剪贴板**  
   :::column-end:::
   :::column span="2":::
      将 **显示值** 复制到剪贴板。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      第  
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
      级  
   :::column-end:::
   :::column span="1":::
      **调色板**  
   :::column-end:::
   :::column span="2":::
      选择其中一个方框将颜色更改为该正方形。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      型  
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
      **Opacity**  
   :::column-end:::
   :::column span="2":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      个  
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
      db-9  
   :::column-end:::
   :::column span="1":::
      **调色板切换器**  
   :::column-end:::
   :::column span="2":::
      在 [材料设计调色板][MaterialDesignColorSystem]、自定义调色板或页面颜色调色板之间切换。  DevTools 基于在样式表中找到的颜色生成页面调色板。  
   :::column-end:::
:::row-end:::  

#### 使用滴管对页面进行颜色取样  

打开 " **颜色选取器**" 时，默认情况下， **取色** 器 \ (![ 吸管 ][ImageEyedropperIcon] \ ) 处于打开状态。  完成以下操作以将所选颜色更改为页面上的其他颜色。  

1.  将鼠标悬停在视区中的目标颜色上。  
1.  选择 "确认"。  
    
    > [!NOTE]
    > 在下图中， **颜色选取器** 显示当前颜色值 `rgba(0,0,0,0.7)` ，它接近黑色。  选择特定颜色后，该特定颜色应更改为当前在视区中突出显示的黑色版本。  
    
    :::image type="complex" source="../media/css-color-picker-eye-dropper.msft.png" alt-text="使用取色器" lightbox="../media/css-color-picker-eye-dropper.msft.png":::
       使用取色器  
    :::image-end:::  
    
## 与 Microsoft Edge 开发人员工具团队联系  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageAddBackgroundColorIcon]: ../media/add-background-color-icon.msft.png  
[ImageAddBoxShadowIcon]: ../media/add-box-shadow-icon.msft.png  
[ImageAddColorIcon]: ../media/add-color-icon.msft.png  
[ImageAddTextShadowIcon]: ../media/add-text-shadow-icon.msft.png  
[ImageEyedropperIcon]: ../media/eyedropper-icon.msft.png  
[ImageNewStyleRuleIcon]: ../media/new-style-rule-icon.msft.png  
[ImageRefreshIcon]: ../media/refresh-icon.msft.png  
[ImageSelectAnElementIcon]: ../media/select-an-element-icon.msft.png  

<!-- links -->  

[DevToolsCommandMenu]: ../command-menu/index.md "通过 Microsoft Edge DevTools 命令菜单运行命令 |Microsoft 文档"  
[DevToolsCSSGetStarted]: ../css/index.md "开始使用查看和更改 CSS |Microsoft 文档"  
[DevToolsCSSGetStartedAddPseudoState]: ../css/index.md#add-a-pseudostate-to-a-class "向课堂添加伪状态-开始查看和更改 CSS |Microsoft 文档"  
[DevToolsCSSGetStartedTutorial]: ../css/index.md#view-the-css-for-an-element "查看元素的 CSS-开始使用查看和更改 CSS |Microsoft 文档"  
[DevToolsCssPrintPreview]: ../css/print-preview.md "强制 Microsoft Edge DevTools 进入打印预览模式 (CSS 打印媒体类型) |Microsoft 文档"  
[DevToolsJavascriptReferenceFormat]: ../javascript/reference.md#make-a-minified-file-readable "使 minified 文件可读-JavaScript 调试参考 |Microsoft 文档"  

[MaterialDesignColorSystem]: https://material.io/guidelines/style/color.html#color-color-palette "颜色系统-材料设计"  
[MDNBoxModel]: https://developer.mozilla.org/docs/Learn/CSS/Introduction_to_CSS/Box_model "方框模型 |MDN"  
[MDNSelectorTypes]: https://developer.mozilla.org/docs/Web/CSS/Specificity#Selector_Types "选择器类型-"自由" |MDN"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/css/reference)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  