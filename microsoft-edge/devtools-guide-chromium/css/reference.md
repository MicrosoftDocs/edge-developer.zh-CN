---
title: CSS 参考
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/27/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 005d2650a1633d49a8c6c2550c4b2c0c2e3f3be6
ms.sourcegitcommit: 5cdc1626d5581b79c0f2ac4ea62e7f1974ebfa57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2020
ms.locfileid: "10601844"
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



在此完整参考 Microsoft Edge DevTools 与查看和更改 CSS 相关的功能中发现新工作流。  

请参阅[查看和更改 CSS 开始][DevToolsCSSGetStarted]了解基础知识。  

## 选择一个元素   

DevTools 的 "**元素**" 面板使你可以一次查看或更改一个元素的 CSS。  所选元素在**DOM 树**中突出显示。  元素的样式显示在 "**样式**" 窗格中。  请参阅查看教程的[元素的 CSS][DevToolsCSSGetStartedTutorial] 。  

> [!NOTE]
> 在[图 1](#figure-1)中，在 `h1` **DOM 树**中突出显示的元素是所选元素。  在右侧，元素的样式显示在 "**样式**" 窗格中。  在左侧，元素在视区中突出显示，但仅因为鼠标当前在**DOM 树**中悬停在其上方。  

> ##### 图 1  
> 所选元素的示例  
> ![所选元素的示例][ImageSelectedElement]  

有多种方法可用于选择元素：  

*   在视区中，右键单击元素，然后选择 "**检查**"。  
*   在 DevTools 中，单击 "**选择元素**"， ![ 选择一个元素 ][ImageSelectAnElementIcon] 或按 `Control` + `Shift` + `C` \ （Windows \）或 `Command` + `Shift` + `C` \ （macOS \），然后单击视区中的元素。  
*   在 DevTools 中，单击**DOM 树**中的元素。  
*   在 DevTools 中，运行一个如 `document.querySelector('p')` 在**控制台**中的查询，右键单击结果，然后选择 **"在元素中显示" 面板**。  

## 查看 CSS   

### 查看定义规则的外部样式表   

在 "**样式**" 窗格中，单击 CSS 规则旁边的链接以打开定义该规则的外部样式表。  

如果样式表是 minified，请参阅[使 minified 文件易于阅读][DevToolsJavascriptReferenceFormat]。  

> [!NOTE]
> 在[图 2](#figure-2)中，单击 `https://docs.microsoft.com/_themes/docs.theme/master/en-us/_themes/styles/b66bc881.site-ltr.css:2` "转到" 第2行 `https://docs.microsoft.com/_themes/docs.theme/master/en-us/_themes/styles/b66bc881.site-ltr.css` ，其中 `.content h1:first-of-type` 定义了 CSS 规则。  

> ##### 图 2  
> 查看定义规则的样式表  
> ![查看定义规则的样式表][ImageViewRuleStylesheet]  

### 仅查看实际应用到元素的 CSS   

"**样式**" 选项卡显示适用于元素的所有规则，包括已重写的声明。  当你对替代声明不感兴趣时，请使用 "**计算**" 选项卡仅查看实际应用于元素的 CSS。  

1.  [选择一个元素](#select-an-element)。  
1.  转到 "**元素**" 面板中的 "**计算**" 选项卡。  

> [!NOTE]
> 在宽 DevTools 窗口中，**计算**的选项卡不存在。  **计算**的选项卡的内容显示在 "**样式**" 选项卡上。  

继承的属性是不透明的。  选中 "**全部显示**" 复选框以查看所有继承值。  

> [!NOTE]
> 在[图 3](#figure-3)中，"**计算**" 选项卡显示了应用于当前所选元素的 CSS 属性 `h1` 。  

> ##### 图 3  
> **计算**选项卡  
> ![计算选项卡][ImageComputedTab]  

### 按字母顺序查看 CSS 属性   

使用 "**计算**" 选项卡。 请参阅[仅查看实际应用到元素的 CSS](#view-only-the-css-that-is-actually-applied-to-an-element)。  

### 查看继承的 CSS 属性   

选中 "**计算**" 选项卡中的 "**全部显示**" 复选框。 请参阅[仅查看实际应用到元素的 CSS](#view-only-the-css-that-is-actually-applied-to-an-element)。  

### 查看元素的 box 模型   

若要查看元素[的方框模型][MDNBoxModel]，请转到 "**样式**" 选项卡。 如果 DevTools 窗口较窄，则**框模型**图位于选项卡的底部。  

若要更改值，请双击它。  

> [!NOTE]
> 在[图 4](#figure-4)中，"**样式**" 选项卡中的**方框模型**图显示了当前所选元素的框模型 `h1` 。  

> ##### 图 4  
> **方框模型**图  
> ![方框模型图][ImageBoxModel]  

### 搜索和筛选元素的 CSS   

使用 "**样式**" 和 "**计算**" 选项卡上的 "**筛选器**" 文本框搜索特定的 CSS 属性或值。  

若要同时在 "**计算**" 选项卡中搜索继承的属性，请选中 "**全部显示**" 复选框。  

> [!NOTE]
> 在[图 5](#figure-5)中，筛选 "**样式**" 选项卡以仅显示包含搜索查询的规则 `color` 。  

> ##### 图 5  
> 筛选 "**样式**" 选项卡  
> ![筛选 "样式" 选项卡][ImageStylesFilter]  

> [!NOTE]
> 在[图 6](#figure-6)中，"**计算**" 选项卡已筛选为仅显示包含 "搜索" 查询的声明 `100%` 。  

> ##### 图 6  
> 筛选**计算**的选项卡  
> ![筛选计算的选项卡][ImageComputerFilter]  

### 切换伪类   

若要切换伪类（如、、 `:active` 或），请 `:focus` `:hover` `:visited` 执行以下操作：  

1.  [选择一个元素](#select-an-element)。  
1.  在 "**元素**" 面板上，转到 "**样式**" 选项卡。  
1.  单击 **： hov**。  
1.  检查要启用的伪类。  

> [!NOTE]
> 在[图 7](#figure-7)中，切换 `:hover` 伪类。  在视区中，验证 `background-color: cornflowerblue` 是否将声明应用于该元素，即使该元素实际上不是悬停在该元素上。  

> ##### 图 7  
> 切换 `:hover` 伪类  
> ![切换：悬停伪类][ImagePseudoClass]  

有关交互式教程，请参阅[向类添加伪][DevToolsCSSGetStartedAddPseudoState]状态。 

### 在打印模式下查看页面   

若要以打印模式查看页面，请执行以下操作：  

1.  [打开 "命令" 菜单][DevToolsCommandMenu]。  
1.  开始键入 `Rendering` 并选择 `Show Rendering` 。  
1.  对于 "**模拟 CSS 媒体**" 下拉列表，选择 "**打印**"。  

### 使用 "覆盖范围" 选项卡查看使用和未使用的 CSS   

"覆盖范围" 选项卡显示页面实际使用的 CSS。  

1.  `Control` + `Shift` + `P` 当 DevTools 处于焦点时，按 \ （Windows \）或 `Command` + `Shift` + `P` \ （macOS \）打开 "命令" 菜单。  
1.  开始键入 `coverage` ，然后选择 "**显示覆盖率**"。  将显示 "覆盖范围" 选项卡。  
    
    > ##### 图 8  
    > 从 "命令" 菜单打开 "覆盖范围" 选项卡  
    > ![从 "命令" 菜单打开 "覆盖范围" 选项卡][ImageCommandMenu]  
    
    > ##### 图 9  
    > "覆盖范围" 选项卡  
    > !["覆盖范围" 选项卡][ImageCoverageEmpty]  
    
1.  单击 "**开始检测覆盖率" 并刷新页面 "** ![ 开始检测覆盖率" 并刷新页面 ][ImageRefreshIcon] 。  页面刷新和 "覆盖率" 选项卡提供浏览器加载的每个文件中使用的 CSS \ （和 JavaScript \）的概述。  绿色表示使用的 CSS。  红色表示未使用的 CSS。  
    
    > ##### 图 10  
    > 有关使用和未使用的 CSS （和 JavaScript）数量的概述  
    > ![有关使用和未使用的 CSS （和 JavaScript）数量的概述][ImageCoverageOverview]  

1.  单击一个 CSS 文件以查看逐行分解它所使用的 CSS。  
    
    > [!NOTE]
    > 在[图 11](#figure-11)中，145到147和149到 151 `b66bc881.site-ltr.css` 未使用，而使用行163到166。  
    
    > ##### 图 11  
    > 已使用和未使用的 CSS 的逐行划分  
    > ![已使用和未使用的 CSS 的逐行划分][ImageCoverageDetail]  
    
### 强制打印预览模式   

请参阅[强制 DevTools 进入打印预览模式][DevToolsCssPrintPreview]。  

## 更改 CSS   

<!-- todo s/CSS declaration/declaration/ -->  

### 向元素添加 CSS 声明   

由于声明的顺序影响元素的样式，因此你可以采用不同的方式添加声明：  

*   [添加内联声明](#add-an-inline-declaration)。  等效于将 `style` 属性添加到元素的 HTML。  
*   [将声明添加到样式规则](#add-a-declaration-to-a-style-rule)。  

**应该使用哪个工作流？** 在大多数情况下，你可能希望使用内联声明工作流。  内联声明具有比外部声明更高的形式，因此内联工作流可确保所做的更改在元素中按预期效果生效。  有关详细信息，请参阅[选择器类型][MDNSelectorTypes]。  

如果你正在调试元素的任何样式，并且你需要专门测试在不同位置定义声明时所发生的情况，请使用其他工作流。  

#### 添加内联声明   

要添加内联声明，请执行以下操作：  

1.  [选择一个元素](#select-an-element)。  
1.  在 "**样式**" 窗格中，在元素的方括号之间单击 **。 "样式**" 部分。  光标焦点，允许您输入文本。  
1.  输入属性名称，然后按 `Enter` 。  
1.  输入该属性的有效值，然后按 `Enter` 。  在**DOM 树**中，验证是否已将某个 `style` 属性添加到该元素。  

> [!NOTE]
> 在[图 12](#figure-12)中，"" `margin-top` 和 "属性" `background-color` 已应用于所选元素。  在**DOM 树**中，验证声明是否反映在元素的 `style` 属性中。  

> ##### 图 12  
> 添加内联声明  
> ![添加内联声明][ImageInlineDeclarations]  

#### 将声明添加到样式规则   

将声明添加到现有样式规则：  

1.  [选择一个元素](#select-an-element)。  
1.  在 "**样式**" 窗格中，单击要向其中添加声明的样式规则的方括号。  光标焦点，允许您输入文本。  
1.  输入属性名称，然后按 `Enter` 。  
1.  输入该属性的有效值，然后按 `Enter` 。  

> ##### 图 13  
> 将 `border-bottom-style:groove` 声明添加到样式规则  
> ![将声明添加到样式规则][ImageAddDeclarationExistingRule]  

### 更改声明名称或值   

双击声明的名称或值以对其进行更改。  请参阅使用快捷键的[键盘快捷方式更改声明值](#change-declaration-values-with-keyboard-shortcuts)，快速将值按 `0.1` 、、 `1` `10` 或单位递减或递减 `100` 。  

> ##### 图 14  
> 更改的值 `border-bottom-style`  
> ![更改声明的值][ImageAddDeclarationExistingRule2]  

### 通过键盘快捷方式更改声明值   

编辑声明的值时，可以使用以下键盘快捷方式按固定量增加值：  

*   按 `Alt` + `Up` \ （Windows \）或 `Option` + `Up` \ （macOS \）递增 `0.1` 。  
*   按下 `Up` 以更改值 `1` ，或者 `0.1` 如果当前值介于和之间，则 `-1` 按 `1` 。  
*   按 " `Shift` + `Up` 增加方式" `10` 。  
*   按 `Shift` + `Page Up` \ （Windows \）或 `Shift` + `Command` + `Up` \ （macOS \）将值增加 `100` 。  

减量也有效。  只需将上面提及的每个实例替换 `Up` 为 `Down` 。  

### 向元素添加类   

要向元素添加类，请执行以下操作：  

1.  在**DOM 树**中[选择该元素](#select-an-element)。  
1.  单击 " **. cls**。  
1.  在 "**添加新类**" 文本框中输入类的名称。  
1.  按 `Enter` 。  

> ##### 图 15  
> "**元素类**" 窗格  
> !["元素类" 窗格][ImageElementClasses]  

### 切换类   

启用或禁用元素上的类：  

1.  在**DOM 树**中[选择该元素](#select-an-element)。  
1.  打开 "**元素类**" 窗格。  请参阅[向元素添加类](#add-a-class-to-an-element)。  在 "**添加新类**" 文本框下方是应用于此元素的所有类。  
1.  切换要启用或禁用的类旁边的复选框。  

### 添加样式规则   

要添加新的样式规则，请执行以下操作：  

1.  [选择一个元素](#select-an-element)。  
1.  单击 "**新建样式规则**" ![ 新样式规则 ][ImageNewStyleRuleIcon] 。  DevTools 在元素下方插入新规则 **。 style**规则。  

> [!NOTE]
> 在[图 16](#figure-16)中，DevTools 在 `h1.devsite-page-title` 单击 "**新建样式规则**" 后添加样式规则。  

> ##### 图 16  
> 添加新样式规则  
> ![添加新样式规则][ImageStyleRule]  

#### 选择要向其添加规则的样式表   

[添加新样式规则](#add-a-style-rule)时，单击并按住**新的样式规则** ![ 新样式规则， ][ImageNewStyleRuleIcon] 选择要向其添加样式规则的样式表。  

> ##### 图 17  
> 选择样式表  
> ![选择样式表][ImageChooseStylesheet]  

#### 将样式规则添加到特定位置   

若要将样式规则添加到 "**样式**" 选项卡中的特定位置，请执行以下操作：  

1.  将鼠标悬停在要添加新样式规则的正上方的样式规则上。  
1.  [显示 "**更多操作**" 工具栏](#reveal-the-more-actions-toolbar)。  
1.  单击下方的 "插入**样式规则**" 下方 ![ 的 "插入样式规则" ][ImageNewStyleRuleIcon] 。  

> ##### 图18  
> **在下方插入样式规则**  
> ![在下方插入样式规则][ImageInsertStyleRuleBelow]  

### 显示 "更多操作" 工具栏   

"**更多操作**" 工具栏使您能够：  

*   直接在你的重点所在的下插入样式规则。  
*   向 `background-color` `color` `box-shadow` 你关注的样式规则添加、、或 `text-shadow` 声明。  

要显示 "**更多操作**" 工具栏，请执行以下操作：  

1.  在 "**样式**" 选项卡中，将鼠标悬停在样式规则上。  **更多操作** `...`显示在样式规则部分的右下角。  
    
    > [!NOTE]
    > 在[图 19](#figure-19)中，将鼠标悬停在样式规则上，并显示 " `.header-holder.has-default-focus` 样式规则" 部分右下角的 "**更多操作**"。  
    
    > ##### 图19  
    > 泄漏**更多操作**  
    > ![泄漏更多操作][ImageRevealMore]  
    
1.  将鼠标悬停在**更多操作**上 `...` 以显示上述操作。  
    
    > [!NOTE]
    > 将鼠标悬停在**更多操作**之后，将显示 "**下方的插入样式规则**" 操作。  
    
    > ##### 图20  
    > "**更多操作**" 工具栏  
    > !["更多操作" 工具栏][ImageInsertStyleRuleBelow2]  
    
### 切换声明   

若要打开或关闭单个声明，请执行以下操作：  

1.  [选择一个元素](#select-an-element)。  
1.  在 "**样式**" 窗格中，将鼠标悬停在定义声明的规则上方。  复选框显示在每个声明的旁边。  
1.  选中或取消选中声明旁边的复选框。  取消选中某个声明后，DevTools 将其置于外，以指示它不再处于活动状态。  

> [!NOTE]
> 在[图 21](#figure-21)中， `margin-top` 当前所选元素的属性已关闭。  

> ##### 图21  
> 切换声明  
> ![切换声明][ImageToggleDeclaration]  

### 添加背景色声明   

若要向 `background-color` 元素添加声明，请执行以下操作：  

1.  将鼠标悬停在要向其添加声明的样式规则上 `background-color` 。  
1.  [显示 "**更多操作**" 工具栏](#reveal-the-more-actions-toolbar)。  
1.  单击 "**添加背景色**" ![ 添加背景色 ][ImageAddBackgroundColorIcon] 。  

> ##### 图22  
> **添加背景色**  
> ![添加背景色][ImageAddBackgroundColor]  

### 添加颜色声明   

若要向 `color` 元素添加声明，请执行以下操作：  

1.  将鼠标悬停在要向其添加声明的样式规则上 `color` 。  
1.  [显示 "**更多操作**" 工具栏](#reveal-the-more-actions-toolbar)。  
1.  单击 "**添加颜色**" " ![ 添加颜色" ][ImageAddColorIcon] 。  

> ##### 图23  
> **添加颜色**  
> ![添加颜色][ImageAddColor]  

### 添加 box-阴影声明   

若要向 `box-shadow` 元素添加声明，请执行以下操作：  

1.  将鼠标悬停在要向其添加声明的样式规则上 `box-shadow` 。  
1.  [显示 "**更多操作**" 工具栏](#reveal-the-more-actions-toolbar)。  
1.  单击 "**添加框阴影** ![ 添加框阴影" ][ImageAddBoxShadowIcon] 。  

> ##### 图24  
> **添加框阴影**  
> ![添加框阴影][ImageAddBoxShadow]  

### 添加文本阴影声明   

若要向 `text-shadow` 元素添加声明，请执行以下操作：  

1.  将鼠标悬停在要向其添加声明的样式规则上 `text-shadow` 。  
1.  [显示 "**更多操作**" 工具栏](#reveal-the-more-actions-toolbar)。  
1.  单击 "**添加文本阴影**" ![ 添加文本阴影 ][ImageAddTextShadowIcon] 。  

> ##### 图25  
> **添加文本阴影**  
> ![添加文本阴影][ImageAddTextShadow]  

### 通过拾色器更改颜色   

**颜色选取器**提供了用于更改 `color` 和声明的 GUI `background-color` 。  

要打开**拾色器**，请执行以下操作：  

1.  [选择一个元素](#select-an-element)。  
1.  在 "**样式**" 选项卡中，找到 `color` `background-color` 要更改的、或类似的声明。  在 " `color` 、" `background-color` 或 "类似" 值的左侧，有一个小方块，它是颜色的预览。  
    
    > [!NOTE]
    > 在[图 26](#figure-26)中，左侧的小方块 `rgba(0, 0, 0, 0.7)` 是该颜色的预览。  
    
    > ##### 图26  
    > 颜色预览  
    > ![颜色预览][ImageColorPreview]  
    
1.  单击预览以打开**颜色选取器**。  
    
    > ##### 图27  
    > **颜色选取器**  
    > ![颜色选取器][ImageColorPicker]  
    
下面是对**颜色选取器**的每个 UI 元素的说明：  

> ##### 图28  
> 颜色选取器，批注  
> ![颜色选取器，批注][ImageColorPickerAnnotated]  

1.  **底纹**。  
1.  **吸管**。  请参阅[使用取色器在页面上示例颜色](#sample-a-color-off-the-page-with-the-eyedropper)。  
1.  **复制到剪贴板**。  将**显示值**复制到剪贴板。  
1.  **显示值**。  颜色的 RGBA、HSLA 或十六进制表示形式。  
1.  **调色板**。  单击其中一个方框以更改该正方形的颜色。  
1.  **色调**。  
1.  **Opacity**。  
1.  **显示值切换**器。  在当前颜色的 RGBA、HSLA 和十六进制表示形式之间切换。  
1.  **调色板切换**器。  在[材料设计调色板][MaterialDesignColorSystem]、自定义调色板或页面颜色调色板之间切换。  DevTools 基于在样式表中找到的颜色生成页面调色板。  

#### 使用滴管对页面进行颜色取样   

打开 "**颜色选取器**" 时，默认情况下，"**滴管**" ![ 取色器 ][ImageEyedropperIcon] 处于打开状态。  若要将所选颜色更改为页面上的其他颜色，请执行以下操作：  

1.  将鼠标悬停在视区中的目标颜色上。  
1.  单击以确认。  
    
    > [!NOTE]
    > 在[图 29](#figure-29)中，**颜色选取器**显示当前颜色值 `rgba(0,0,0,0.7)` ，它接近黑色。  单击黑色后，此颜色应更改为当前在视区中突出显示的黑色。  
    
    > ##### 图29  
    > 使用取色器  
    > ![使用取色器][ImageUsingEyedropper]  
    
 



<!-- image links -->  

[ImageAddBackgroundColorIcon]: /microsoft-edge/devtools-guide-chromium/media/add-background-color-icon.msft.png  
[ImageAddBoxShadowIcon]: /microsoft-edge/devtools-guide-chromium/media/add-box-shadow-icon.msft.png  
[ImageAddColorIcon]: /microsoft-edge/devtools-guide-chromium/media/add-color-icon.msft.png  
[ImageAddTextShadowIcon]: /microsoft-edge/devtools-guide-chromium/media/add-text-shadow-icon.msft.png  
[ImageEyedropperIcon]: /microsoft-edge/devtools-guide-chromium/media/eyedropper-icon.msft.png  
[ImageNewStyleRuleIcon]: /microsoft-edge/devtools-guide-chromium/media/new-style-rule-icon.msft.png  
[ImageRefreshIcon]: /microsoft-edge/devtools-guide-chromium/media/refresh-icon.msft.png  
[ImageSelectAnElementIcon]: /microsoft-edge/devtools-guide-chromium/media/select-an-element-icon.msft.png  

[ImageSelectedElement]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-h1.msft.png "图1：所选元素的示例"  
[ImageViewRuleStylesheet]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-h1-highlight.msft.png "图2：查看定义规则的样式表"  
[ImageComputedTab]: /microsoft-edge/devtools-guide-chromium/media/css-elements-computed-h1.msft.png "图3：计算的选项卡"  
[ImageBoxModel]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-h1-2.msft.png "图4：方框模型图"  
[ImageStylesFilter]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-filter-color.msft.png "图5：筛选 "样式" 选项卡"  
[ImageComputerFilter]: /microsoft-edge/devtools-guide-chromium/media/css-elements-computed-filter-100.msft.png "图6：筛选计算的选项卡"  
[ImagePseudoClass]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-hov-hover.msft.png "图7：切换：悬停伪类"  
[ImageCommandMenu]: /microsoft-edge/devtools-guide-chromium/media/css-console-command-menu-coverage.msft.png "图8：从 "命令" 菜单打开 "覆盖范围" 选项卡"  
[ImageCoverageEmpty]: /microsoft-edge/devtools-guide-chromium/media/css-console-qs-coverage-empty.msft.png "图9： "覆盖范围" 选项卡"  
[ImageCoverageOverview]: /microsoft-edge/devtools-guide-chromium/media/css-console-qs-coverage-run.msft.png "图10：使用和未使用过多少 CSS （和 JavaScript）的概述"  
[ImageCoverageDetail]: /microsoft-edge/devtools-guide-chromium/media/css-sources-css-coverage.msft.png "图11：已使用和未使用的 CSS 的逐行划分"  
[ImageInlineDeclarations]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-margin-top-background-color.msft.png "图12：添加内联声明"  
[ImageAddDeclarationExistingRule]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-border-bottom-style.msft.png "图13：将声明添加到样式规则"  
[ImageAddDeclarationExistingRule2]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-border-bottom-style-dropdown.msft.png "图14：更改声明的值"  
[ImageElementClasses]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-filter-classes.msft.png "图15： "元素类" 窗格"  
[ImageStyleRule]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-style-new.msft.png "图16：添加新样式规则"  
[ImageChooseStylesheet]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-style-new-select-exisiting.msft.png "图17：选择样式表"  
[ImageInsertStyleRuleBelow]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-insert-style-rule-below.msft.png "图18：在下方插入样式规则"  
[ImageRevealMore]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-new-rule-styles.msft.png "图19：泄漏更多操作"  
[ImageInsertStyleRuleBelow2]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-rule-more-options-insert-style-rule-below.msft.png "图20： "更多操作" 工具栏"  
[ImageToggleDeclaration]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-rule-deactivated.msft.png "图21：切换声明"  
[ImageAddBackgroundColor]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-rule-add-background-color.msft.png "图22：添加背景色"  
[ImageAddColor]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-rule-add-color.msft.png "图23：添加颜色"  
[ImageAddBoxShadow]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-rule-add-box-shadow.msft.png "图24：添加框阴影"  
[ImageAddTextShadow]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-rule-add-text-shadow.msft.png "图25：添加文本阴影"  
[ImageColorPreview]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-rule-overlay-color-box.msft.png "图26：颜色预览"  
[ImageColorPicker]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-rule-color-picker.msft.png "图27：颜色选取器"  
[ImageColorPickerAnnotated]: /microsoft-edge/devtools-guide-chromium/media/css-elements-styles-rule-color-picker-annotated.msft.png "图28：颜色选取器，已批注"  
[ImageUsingEyedropper]: /microsoft-edge/devtools-guide-chromium/media/css-color-picker-eye-dropper.msft.png "图29：使用取色器"  

<!-- links -->  

[DevToolsCommandMenu]: /microsoft-edge/devtools-guide-chromium/command-menu/index "通过 Microsoft Edge DevTools 命令菜单运行命令"  
[DevToolsCSSGetStarted]: /microsoft-edge/devtools-guide-chromium/css/index "查看和更改 CSS 入门"  
[DevToolsCSSGetStartedAddPseudoState]: /microsoft-edge/devtools-guide-chromium/css/index#add-a-pseudostate-to-a-class "向课堂添加伪状态-查看和更改 CSS 入门"  
[DevToolsCSSGetStartedTutorial]: /microsoft-edge/devtools-guide-chromium/css/index#view-the-css-for-an-element "查看元素的 CSS-如何查看和更改 CSS 入门"  
[DevToolsCssPrintPreview]: /microsoft-edge/devtools-guide-chromium/css/print-preview "强制 Microsoft Edge DevTools 进入打印预览模式（CSS 打印媒体类型）"  
[DevToolsJavascriptReferenceFormat]: /microsoft-edge/devtools-guide-chromium/javascript/reference#make-a-minified-file-readable "使 minified 文件易于阅读-JavaScript 调试参考"  

[MaterialDesignColorSystem]: https://material.io/guidelines/style/color.html#color-color-palette "颜色系统-材料设计"  
[MDNBoxModel]: https://developer.mozilla.org/docs/Learn/CSS/Introduction_to_CSS/Box_model "方框模型 |MDN"  
[MDNSelectorTypes]: https://developer.mozilla.org/docs/Web/CSS/Specificity#Selector_Types "选择器类型-"自由" |MDN"  

> [!NOTE]
> 此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/css/reference)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools \ & Lighthouse \）创作。  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
