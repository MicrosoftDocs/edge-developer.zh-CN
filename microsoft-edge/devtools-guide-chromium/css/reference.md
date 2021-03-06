---
description: 发现用于查看和更改 Microsoft Edge DevTools 中的 CSS 的新工作流。
title: CSS 参考
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: a99cf46c4c0a6c6f14892268a30f8aab471e919d
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11399139"
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

在下面的 Microsoft Edge DevTools 功能全面参考中发现与查看和更改 CSS 相关的新工作流。  

若要了解基础知识，请导航到"[查看和更改 CSS 入门"。][DevToolsCSSGetStarted]  

## <a name="choose-an-element"></a>选择元素  

DevTools 的元素工具允许你一次查看或更改一个元素的 CSS。 ****  选定元素在 **DOM 树中突出显示**。  元素的样式显示在" **样式"窗格中** 。  对于教程，导航到["查看元素的 CSS"。][DevToolsCSSGetStartedTutorial]  

> [!NOTE]
> 下图中，DOM 树中突出显示的元素 `h1` 是所选**** 元素。  在右侧，元素的样式显示在" **样式"窗格中** 。  在左侧，该元素在视口中突出显示，但仅仅是因为鼠标当前正在 DOM 树中悬停在 **该元素上**。  

:::image type="complex" source="../media/css-elements-styles-h1.msft.png" alt-text="选定元素的示例" lightbox="../media/css-elements-styles-h1.msft.png":::
   选定元素的示例  
:::image-end:::  

使用以下操作之一选择元素。  

*   在视口中，将鼠标悬停在元素上，打开上下文菜单 \ (右键单击\) ，然后选择"检查 **"。**  
*   在 DevTools 中，选择元素**\ (** 选择元素 \) 或选择 ![ ][ImageSelectAnElementIcon] `Control` + `Shift` + `C` \ (Windows、Linux\) 或 `Command` + `Shift` + `C` \ (macOS\) ，然后选择视口中的元素。  
*   在 DevTools 中，选择 **DOM 树中的元素**。  
*   在 DevTools 中，像在控制台中一样运行查询，将鼠标悬停在结果上，打开上下文菜单 `document.querySelector('p')` \ (右键单击\) ，然后选择"**** 元素"面板中的"展示 **"。**  

## <a name="view-css"></a>查看 CSS  

### <a name="view-the-external-stylesheet-where-a-rule-is-defined"></a>查看定义规则的外部样式表  

在 **"样式** "窗格中，选择 CSS 规则旁边的链接以打开定义该规则的外部样式表。  

如果样式表被缩小，导航到使 [缩小的文件可读][DevToolsJavascriptReferenceFormat]。  

> [!NOTE]
> 在下图中，选择后您将进入 CSS 规则定义的第 `https://docs.microsoft.com/_themes/docs.theme/master/en-us/_themes/styles/b66bc881.site-ltr.css:2` 2 `https://docs.microsoft.com/_themes/docs.theme/master/en-us/_themes/styles/b66bc881.site-ltr.css` `.content h1:first-of-type` 行。  

<!--todo:  replace "Master" phrasing in code snippet, if possible.  -->  

:::image type="complex" source="../media/css-elements-styles-h1-highlight.msft.png" alt-text="查看定义规则的样式表" lightbox="../media/css-elements-styles-h1-highlight.msft.png":::
  查看定义规则的样式表  
:::image-end:::  

### <a name="view-only-the-css-that-is-actually-applied-to-an-element"></a>仅查看实际应用于元素的 CSS  

" **样式** "面板显示应用于元素的所有规则，包括已被覆盖的声明。  如果对替代声明不感兴趣，请使用计算面板仅查看实际应用于**** 元素的 CSS。  

1.  [选择一个元素](#choose-an-element)。  
1.  导航到 **"元素"工具** 中的"计算 **"** 面板。  

> [!NOTE]
> 在宽的 DevTools 窗口中， **计算面板不存在** 。  计算面板**的内容显示在"** 样式"**面板上。**  

继承的属性不透明。  若要显示所有继承的值，请选中 **"全部显示"** 复选框。  

> [!NOTE]
> 下图中， **计算面板显示** 应用于当前选定元素的 CSS `h1` 属性。  

:::image type="complex" source="../media/css-elements-computed-h1.msft.png" alt-text="计算面板" lightbox="../media/css-elements-computed-h1.msft.png":::
   计算**面板**  
:::image-end:::  

### <a name="view-css-properties-in-alphabetical-order"></a>按字母顺序查看 CSS 属性  

使用 **计算面板** 。  导航[到"仅查看实际应用于元素的 CSS"。](#view-only-the-css-that-is-actually-applied-to-an-element)  

### <a name="view-inherited-css-properties"></a>查看继承的 CSS 属性  

选中" **计算"面板** 中的"全部 **显示"** 复选框。  导航[到"仅查看实际应用于元素的 CSS"。](#view-only-the-css-that-is-actually-applied-to-an-element)  

### <a name="view-the-box-model-for-an-element"></a>查看元素的框模型  

若要查看 [元素的框][MDNBoxModel] 模型，请导航到 **"样式"** 面板。  如果你的 DevTools 窗口较窄****，则方框模型图位于面板的底部。  

选择并编辑值以更改值。  

> [!NOTE]
> 下图中，"样式" **面板中的** "方框模型 **"图表显示了** 当前选定元素的框 `h1` 模型。  

:::image type="complex" source="../media/css-elements-styles-h1-2.msft.png" alt-text="方框模型图" lightbox="../media/css-elements-styles-h1-2.msft.png":::
   方框 **模型** 图  
:::image-end:::  

### <a name="search-and-filter-the-css-of-an-element"></a>搜索和筛选元素的 CSS  

使用 **"** 样式"和"计算****"面板**上的**"筛选器"文本框搜索特定的 CSS 属性或值。  

若要在计算面板中搜索继承的属性 **，请** 选中"全部 **显示"** 复选框。  

> [!NOTE]
> 在下图中，将筛选 **样式** 面板，以只显示包含搜索查询的规则 `color` 。  

:::image type="complex" source="../media/css-elements-styles-filter-color.msft.png" alt-text="筛选"样式"面板" lightbox="../media/css-elements-styles-filter-color.msft.png":::
   筛选 **"样式"** 面板  
:::image-end:::  

> [!NOTE]
> 在下图中，将 **筛选计算** 面板，以只显示包含搜索查询的声明 `100%` 。  

:::image type="complex" source="../media/css-elements-computed-filter-100.msft.png" alt-text="筛选计算面板" lightbox="../media/css-elements-computed-filter-100.msft.png":::
   筛选 **计算** 面板  
:::image-end:::  

### <a name="toggle-a-pseudo-class"></a>切换伪类  

完成以下操作以切换伪类，如 `:active` 、 `:focus` 或 `:hover` `:visited` 。  

1.  [选择一个元素](#choose-an-element)。  
1.  在" **元素** "工具上，导航到 **"样式"** 面板。  
1.  Choose **：hov**.  
1.  检查要启用的伪类。  

> [!NOTE]
> 在下图中，切换 `:hover` 伪类。  在视口中验证声明是否应用于元素，即使该元素实际上 `background-color: cornflowerblue` 并未悬停在上方。  

:::image type="complex" source="../media/css-elements-styles-hov-hover.msft.png" alt-text="切换 ：hover 伪类" lightbox="../media/css-elements-styles-hov-hover.msft.png":::
   切换 `:hover` 伪类  
:::image-end:::  

对于交互式教程，导航到 [将伪状态添加到类][DevToolsCSSGetStartedAddPseudoState]。  

### <a name="view-a-page-in-print-mode"></a>在打印模式下查看页面  

完成以下操作以在打印模式下查看页面。  

1.  [打开命令菜单][DevToolsCommandMenu]。  
1.  开始键入并选择 `Rendering` `Show Rendering` 。  
1.  对于"**模拟 CSS 媒体**"下拉列表，选择 **"打印"。**  

### <a name="view-used-and-unused-css-with-the-coverage-tool"></a>使用"覆盖"工具查看已用和未使用的 CSS  

" **覆盖** "工具显示页面实际使用的 CSS。  

1.  选择 `Control` + `Shift` + `P` \ (Windows、Linux\) 或 `Command` + `Shift` + `P` \ (macOS\) 而 DevTools[][DevToolsCommandMenu]将打开命令菜单。  
1.  开始键入并选择 `coverage` "**显示覆盖"。**  将显示 **"覆盖** "工具。  
    
    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/css-console-command-menu-coverage.msft.png" alt-text="从命令菜单中打开"覆盖"工具" lightbox="../media/css-console-command-menu-coverage.msft.png":::
             从 **命令菜单中** 打开"覆盖 **"工具**  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          :::image type="complex" source="../media/css-console-qs-coverage-empty.msft.png" alt-text="覆盖工具" lightbox="../media/css-console-qs-coverage-empty.msft.png":::
             覆盖**工具**  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
1.  选择 **"开始检测范围"并刷新** 页面 \ (![ 开始检测范围并刷新 ][ImageRefreshIcon] 页面 \) 。  页面刷新和 **覆盖** 工具概述了浏览器加载的每个文件 (CSS \ (和 JavaScript\) 。  绿色表示使用的 CSS。  红色表示未使用的 CSS。  
    
    :::image type="complex" source="../media/css-console-qs-coverage-run.msft.png" alt-text="使用和未使用 CSS (JavaScript) 概述" lightbox="../media/css-console-qs-coverage-run.msft.png":::
       使用和未使用 CSS \ (JavaScript\) 的概述  
    :::image-end:::  

1.  若要显示使用 CSS 的行细分，请选择 CSS 文件。  
    
    > [!NOTE]
    > 下图中未使用第 145 至 147 行以及 149 到 151 行，而使用 `b66bc881.site-ltr.css` 第 163 至 166 行。  
    
    :::image type="complex" source="../media/css-sources-css-coverage.msft.png" alt-text="已使用和未使用的 CSS 的行细分" lightbox="../media/css-sources-css-coverage.msft.png":::
       已使用和未使用的 CSS 的行细分  
    :::image-end:::  
    
### <a name="force-print-preview-mode"></a>强制打印预览模式  

导航到 [强制 DevTools 进入打印预览模式][DevToolsCssPrintPreview]。  

## <a name="change-css"></a>更改 CSS  

<!-- todo s/CSS declaration/declaration/ -->  

### <a name="add-a-css-declaration-to-an-element"></a>将 CSS 声明添加到元素  

声明的顺序会影响元素的样式，请使用以下列表来帮助以不同方式添加声明。  

*   [添加内联声明](#add-an-inline-declaration)。  相当于将 `style` 属性添加到元素的 HTML。  
*   [向样式规则添加声明](#add-a-declaration-to-a-style-rule)。  

**您应使用什么工作流？** 在大多数情况下，你可能想要使用内联声明工作流。  内联声明比外部声明具有更高的特定性，因此内联工作流可确保更改在预期元素中生效。  有关特定性详细信息，请导航到选择 [器类型][MDNSelectorTypes]。  

如果要调试元素的任何样式，并且需要专门测试在不同位置定义声明时会发生什么情况，请使用其他工作流。  

#### <a name="add-an-inline-declaration"></a>添加内联声明  

完成以下操作以添加内嵌声明。  

1.  [选择一个元素](#choose-an-element)。  
1.  在 **"样式** "窗格中，在 **element.style** 节的括号之间选择。  光标聚焦，允许您输入文本。  
1.  输入属性名称并选择 `Enter` 。  
1.  输入该属性的有效值并选择 `Enter` 。  在 **DOM 树中**，验证 `style` 属性已添加到元素中。  

> [!NOTE]
> 下图中 `margin-top` ，and `background-color` 属性已应用于所选元素。  在 **DOM 树** 中，验证声明是否反映在 `style` 元素的属性中。  

:::image type="complex" source="../media/css-elements-styles-margin-top-background-color.msft.png" alt-text="添加内联声明" lightbox="../media/css-elements-styles-margin-top-background-color.msft.png":::
   添加内联声明  
:::image-end:::  

#### <a name="add-a-declaration-to-a-style-rule"></a>向样式规则添加声明  

完成以下操作以将声明添加到现有样式规则。  

1.  [选择一个元素](#choose-an-element)。  
1.  在 **"样式** "窗格中，在要添加声明的样式规则的括号之间选择。  光标聚焦，允许您输入文本。  
1.  输入属性名称并选择 `Enter` 。  
1.  输入该属性的有效值并选择 `Enter` 。  

:::image type="complex" source="../media/css-elements-styles-border-bottom-style.msft.png" alt-text="向样式规则添加声明" lightbox="../media/css-elements-styles-border-bottom-style.msft.png":::
   将 `border-bottom-style:groove` 声明添加到样式规则  
:::image-end:::  

### <a name="change-a-declaration-name-or-value"></a>更改声明名称或值  

选择并编辑声明的名称或值以更改它。  对于通过 、、或 单位快速递增或缩小值的快捷方式，请导航到使用键盘快捷方式更改 `0.1` `1` `10` `100` [声明值](#change-declaration-values-with-keyboard-shortcuts)。  

:::image type="complex" source="../media/css-elements-styles-border-bottom-style-dropdown.msft.png" alt-text="更改声明的值" lightbox="../media/css-elements-styles-border-bottom-style-dropdown.msft.png":::
   更改声明 `border-bottom-style` 的值  
:::image-end:::  

### <a name="change-declaration-values-with-keyboard-shortcuts"></a>使用键盘快捷方式更改声明值  

在编辑声明的值时，可以使用以下键盘快捷方式将该值增加特定量。  

*   选择 `Alt` + `Up` \ (Windows、Linux\) 或 `Option` + `Up` \ (macOS\) 递增 `0.1` 。  
*   选择以更改值，如果当前值介于和之间，则按或 `Up` `1` `0.1` `-1` 按更改 `1` 。  
*   选择 `Shift` + `Up` 以递增。 `10`  
*   选择 `Shift` + `Page Up` \ (Windows、Linux\) 或 `Shift` + `Command` + `Up` \ (macOS\) 将值递增 `100` 。  

减分也有效。  只需将上述每个 `Up` 实例替换为 `Down` 。  

### <a name="add-a-class-to-an-element"></a>向元素添加类  

完成以下操作以向元素中添加类。  

1.  [选择 DOM](#choose-an-element) 树 **中的元素**。  
1.  选择 **.cls**。  
1.  在"添加新类"文本框中 **输入类** 的名称。  
1.  选择 `Enter`。  

:::image type="complex" source="../media/css-elements-styles-filter-classes.msft.png" alt-text=""元素类"窗格" lightbox="../media/css-elements-styles-filter-classes.msft.png":::
   " **元素类"** 窗格  
:::image-end:::  

### <a name="toggle-a-class"></a>切换类  

完成以下操作以启用或禁用元素上的类。  

1.  [选择 DOM](#choose-an-element) 树 **中的元素**。  
1.  打开 **"元素类"** 窗格。  导航 [到向元素添加类](#add-a-class-to-an-element)。  在 **"添加新类** "文本框下方是应用于特定元素的所有类。  
1.  切换要打开或关闭的类旁边的复选框。  

### <a name="add-a-style-rule"></a>添加样式规则  

完成以下操作以添加新的样式规则。  

1.  [选择一个元素](#choose-an-element)。  
1.  Choose **New Style Rule** \ (New Style Rule ![ ][ImageNewStyleRuleIcon] \) .  DevTools 在 **element.style** 规则下插入一个新规则。  

> [!NOTE]
> 下图中，在选择"新建样式规则"后，DevTools `h1.devsite-page-title` **会添加样式规则**。  

:::image type="complex" source="../media/css-elements-styles-style-new.msft.png" alt-text="添加新的样式规则" lightbox="../media/css-elements-styles-style-new.msft.png":::
   添加新的样式规则  
:::image-end:::  

#### <a name="choose-which-stylesheet-to-add-a-rule-to"></a>选择要向哪个样式表添加规则  

添加新[样式规则](#add-a-style-rule)时，选择并保留"新建**** 样式规则"\ ("新建样式规则"\) 以选择要向哪个样式表 ![ ][ImageNewStyleRuleIcon] 添加样式规则。  

:::image type="complex" source="../media/css-elements-styles-style-new-select-existing.msft.png" alt-text="选择样式表" lightbox="../media/css-elements-styles-style-new-select-existing.msft.png":::
   选择样式表  
:::image-end:::  

#### <a name="add-a-style-rule-to-a-specific-location"></a>将样式规则添加到特定位置  

完成以下操作，将样式规则添加到"样式" **面板中的特定** 位置。  

1.  将鼠标悬停在要添加新样式规则的正上方的样式规则上。  
1.  [显示 **"更多操作"** 工具栏](#reveal-the-more-actions-toolbar)。  
1.  Choose **Insert Style Rule below** \ (Insert Style Rule Below icon ![ ][ImageNewStyleRuleIcon] \) .  

:::image type="complex" source="../media/css-elements-styles-insert-style-rule-below.msft.png" alt-text="在下方插入样式规则" lightbox="../media/css-elements-styles-insert-style-rule-below.msft.png":::
   **在下方插入样式规则**  
:::image-end:::  

### <a name="reveal-the-more-actions-toolbar"></a>显示"更多操作"工具栏  

" **更多操作** "工具栏允许您执行以下操作。  

*   将样式规则插入到你关注的规则正下方。  
*   将 `background-color` 、 `color` `box-shadow` 或声明 `text-shadow` 添加到你关注样式规则。  

完成以下操作以显示"更多 **操作"** 工具栏。  

1.  在 **"样式** "面板中，将鼠标悬停在样式规则上。  **样式** 规则 (右下角显示更多操作 `...` \) \) 。  
    
    > [!NOTE]
    > 下图中，将鼠标悬停在样式规则上，"更多操作"在样式规则节的右下 `.header-holder.has-default-focus` 角显示。 ****  
    
    :::image type="complex" source="../media/css-elements-styles-new-rule-styles.msft.png" alt-text="显示更多操作" lightbox="../media/css-elements-styles-new-rule-styles.msft.png":::
       显示 **更多操作** \ (`...` \)   
    :::image-end:::  
    
1.  将鼠标 **悬停在"** 更多操作" (`...` \) 可显示上述操作。  
    
    > [!NOTE]
    > 将 **鼠标悬** 停在"更多操作"上后，"插入样式规则下方 **"操作将显示**。  
    
    :::image type="complex" source="../media/css-elements-styles-rule-more-options-insert-style-rule-below.msft.png" alt-text=""更多操作"工具栏" lightbox="../media/css-elements-styles-rule-more-options-insert-style-rule-below.msft.png":::
       " **更多操作"** 工具栏  
    :::image-end:::  
    
### <a name="toggle-a-declaration"></a>切换声明  

完成 folllwoing 操作以在 \ (或 off\) 上切换单个) 。  

1.  [选择一个元素](#choose-an-element)。  
1.  在 **"样式** "窗格中，将鼠标悬停在定义声明的规则上。  每个声明旁边将出现一个复选框。  
1.  选中\ (或取消选中\) 声明旁边的复选框。  取消选中声明时，DevTools 会交叉它以指示它不再处于活动状态。  

> [!NOTE]
> 下图中， `margin-top` 当前选定元素的属性已关闭。  

:::image type="complex" source="../media/css-elements-styles-rule-deactivated.msft.png" alt-text="切换声明" lightbox="../media/css-elements-styles-rule-deactivated.msft.png":::
   切换声明  
:::image-end:::  

### <a name="add-a-background-color-declaration"></a>添加背景色声明  

完成以下操作以向元素 `background-color` 添加声明。  

1.  将鼠标悬停在要添加声明的样式 `background-color` 规则上。  
1.  [显示 **"更多操作"** 工具栏](#reveal-the-more-actions-toolbar)。  
1.  Choose **Add Background Color** \ (Add Background Color icon ![ ][ImageAddBackgroundColorIcon] \) .  

:::image type="complex" source="../media/css-elements-styles-rule-add-background-color.msft.png" alt-text="添加背景色" lightbox="../media/css-elements-styles-rule-add-background-color.msft.png":::
   **添加背景色**  
:::image-end:::  

### <a name="add-a-color-declaration"></a>添加颜色声明  

完成以下操作以向元素 `color` 添加声明。  

1.  将鼠标悬停在要添加声明的样式 `color` 规则上。  
1.  [显示 **"更多操作"** 工具栏](#reveal-the-more-actions-toolbar)。  
1.  Choose **Add Color** \ (Add Color icon ![ ][ImageAddColorIcon] \) .  

:::image type="complex" source="../media/css-elements-styles-rule-add-color.msft.png" alt-text="添加颜色" lightbox="../media/css-elements-styles-rule-add-color.msft.png":::
   **添加颜色**  
:::image-end:::  

### <a name="add-a-box-shadow-declaration"></a>添加框阴影声明  

完成以下操作以向元素 `box-shadow` 添加声明。  

1.  将鼠标悬停在要添加声明的样式 `box-shadow` 规则上。  
1.  [显示 **"更多操作"** 工具栏](#reveal-the-more-actions-toolbar)。  
1.  Choose **Add Box Shadow** \ (Add Box Shadow icon ![ ][ImageAddBoxShadowIcon] \) .  

:::image type="complex" source="../media/css-elements-styles-rule-add-box-shadow.msft.png" alt-text="添加方框阴影" lightbox="../media/css-elements-styles-rule-add-box-shadow.msft.png":::
   **添加方框阴影**  
:::image-end:::  

### <a name="add-a-text-shadow-declaration"></a>添加文本阴影声明  

完成以下操作以向元素 `text-shadow` 添加声明。  

1.  将鼠标悬停在要添加声明的样式 `text-shadow` 规则上。  
1.  [显示 **"更多操作"** 工具栏](#reveal-the-more-actions-toolbar)。  
1.  Choose **Add Text Shadow** \ (Add Text Shadow icon ![ ][ImageAddTextShadowIcon] \) .  

:::image type="complex" source="../media/css-elements-styles-rule-add-text-shadow.msft.png" alt-text="添加文本阴影" lightbox="../media/css-elements-styles-rule-add-text-shadow.msft.png":::
   **添加文本阴影**  
:::image-end:::  

### <a name="change-colors-with-the-color-picker"></a>使用颜色选取器更改颜色  

颜色 **选取器** 提供用于更改和声明 `color` 的 `background-color` GUI。  

完成以下操作以打开 **颜色选取器**。  

1.  [选择一个元素](#choose-an-element)。  
1.  在 **"样式** "面板中，查找要更改的 `color` 、 `background-color` 或类似的声明。  在 ， 或类似的值左侧，有一个小正方形 `color` `background-color` ，这是颜色的预览。  
    
    > [!NOTE]
    > 下图中左侧的小正方形是该颜色的 `rgba(0, 0, 0, 0.7)` 预览。  
    
    :::image type="complex" source="../media/css-elements-styles-rule-overlay-color-box.msft.png" alt-text="颜色预览" lightbox="../media/css-elements-styles-rule-overlay-color-box.msft.png":::
       颜色预览  
    :::image-end:::  
    
1.  选择预览以打开 **颜色选取器**。  
    
    :::image type="complex" source="../media/css-elements-styles-rule-color-picker.msft.png" alt-text="颜色选取器" lightbox="../media/css-elements-styles-rule-color-picker.msft.png":::
       颜色 **选取器**  
    :::image-end:::  
    
下图和列表颜色选取器的每个 UI **元素的反函数**。  

:::image type="complex" source="../media/css-elements-styles-rule-color-picker-annotated.msft.png" alt-text="带有批注的颜色选取器" lightbox="../media/css-elements-styles-rule-color-picker-annotated.msft.png":::
   颜色 **选取器**，已批注  
:::image-end:::  

:::row:::
   :::column span="1":::
      1  
   :::column-end:::
   :::column span="1":::
      **底纹**  
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
      **目视器**  
   :::column-end:::
   :::column span="2":::
      有关详细信息，请导航到使用目视器在页面上 [采样颜色](#sample-a-color-off-the-page-with-the-eyedropper)。  
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
      将 **显示值复制到** 剪贴板。  
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
      选择其中一个正方形以将颜色更改为该正方形。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      6  
   :::column-end:::
   :::column span="1":::
      **Hue**  
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
      8  
   :::column-end:::
   :::column span="1":::
      **显示值切换器**  
   :::column-end:::
   :::column span="2":::
      在当前颜色的 RGBA、HSLA 和十六进制表示形式之间进行切换。  
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
      在" [材料设计"调色板][MaterialDesignColorSystem]、自定义调色板或页面调色板之间进行切换。  DevTools 基于它在样式表找到的颜色生成页面调色板。  
   :::column-end:::
:::row-end:::  

#### <a name="sample-a-color-off-the-page-with-the-eyedropper"></a>使用目视器在页面上采样颜色  

打开颜色选取器**** 时，目视器**\ (** 目) ![ ][ImageEyedropperIcon] \) 默认为打开状态。  完成以下操作，将所选颜色更改为页面上的一些其他颜色。  

1.  将鼠标悬停在视区中的目标颜色上。  
1.  选择确认。  
    
    > [!NOTE]
    > 下图中，颜色选取器 **显示的当前** 颜色值接近 `rgba(0,0,0,0.7)` 黑色。  选择后，特定颜色应更改为当前在视口中突出显示的黑色版本。  
    
    :::image type="complex" source="../media/css-color-picker-eye-dropper.msft.png" alt-text="使用目视器" lightbox="../media/css-color-picker-eye-dropper.msft.png":::
       使用目视器  
    :::image-end:::  
    
<!--todo:  add the section on the Angle clock section for What's New 88.  -->  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge 开发工具团队  

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

[DevToolsCommandMenu]: ../command-menu/index.md "使用 Microsoft Edge 开发工具命令菜单运行命令"  
[DevToolsCSSGetStarted]: ../css/index.md "查看和更改 CSS 入门 | Microsoft 文档"  
[DevToolsCSSGetStartedAddPseudoState]: ../css/index.md#add-a-pseudostate-to-a-class "向类添加伪状态 - 开始查看和更改 CSS |Microsoft Docs"  
[DevToolsCSSGetStartedTutorial]: ../css/index.md#view-the-css-for-an-element "查看元素的 CSS - 开始查看和更改 CSS |Microsoft Docs"  
[DevToolsCssPrintPreview]: ../css/print-preview.md "强制 Microsoft Edge DevTools 进入打印预览模式 (CSS 打印媒体类型) |Microsoft Docs"  
[DevToolsJavascriptReferenceFormat]: ../javascript/reference.md#make-a-minified-file-readable "使缩小文件可读 - JavaScript 调试参考|Microsoft Docs"  

[MaterialDesignColorSystem]: https://material.io/guidelines/style/color.html#color-color-palette "颜色系统 - 材料设计"  
[MDNBoxModel]: https://developer.mozilla.org/docs/Learn/CSS/Introduction_to_CSS/Box_model "方框模型|MDN"  
[MDNSelectorTypes]: https://developer.mozilla.org/docs/Web/CSS/Specificity#Selector_Types "选择器类型 - 特定|MDN"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/css/reference)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  