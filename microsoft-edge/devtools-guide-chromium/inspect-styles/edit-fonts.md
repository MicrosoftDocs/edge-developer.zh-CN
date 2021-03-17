---
description: 了解如何使用 Microsoft Edge DevTools 中的"样式"窗格更改 CSS 字体样式和设置。
title: 在 DevTools 的"样式"窗格中编辑 CSS 字体样式和设置
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/11/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
no-loc:
- Enable new font editor tool within the Styles pane
ms.openlocfilehash: 5d9074ca65f9cb98662a1bc181f70ead4c4232e1
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439491"
---
# <a name="edit-css-font-styles-and-settings-in-the-styles-pane"></a>在"样式"窗格中编辑 CSS 字体样式和设置  

:::image type="icon" source="../media/experimental-tag-14px.msft.png":::

网页版式是用户体验的重要部分。  你想要确保你符合公司品牌准则，并且内容在各种设备上按预期方式显示。  文本必须易于使用大小和行高阅读。  用户可以调整字体大小以满足个人需求。  对于特定字体在用户设备上不可用的情况，你应该提供回退字体选项。  

CSS 提供对近期版式更好的支持。  数十种不同的 CSS 单位可用于定义文本的大小。  您还有一些影响字体大小、间距、行高和其他排版功能的 CSS 属性。  

为了在使用版式时更加轻松，可视化 **字体编辑器** 现在位于 **"样式"** 窗格中。  您可以更改字体设置，更改会立即呈现在浏览器中。  所有这些内容都无需深入了解 CSS。  

目前 **Enable new font editor tool within the Styles pane** 该功能是实验性的，你需要为 [Microsoft Edge 开发人员工具 启用它][DevtoolsExperimentalFeaturesIndexTurnOnExperimentalFeatures]。  

" **样式"窗格中** 的任何 CSS（字体定义或内联样式）都会自动显示打开可视"字体 **编辑器"的图标**。  若要打开可视字体 **编辑器，** 请选择" **字体编辑器"** 图标。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/font-editor-icon.msft.png" alt-text=""样式"窗格中用于编辑字体设置的图标" lightbox="../media/font-editor-icon.msft.png":::
         " **样式"窗格中** 用于编辑字体设置的图标  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/font-editor-open.msft.png" alt-text=""字体编辑器"在"样式"窗格顶部打开" lightbox="../media/font-editor-open.msft.png":::
         " **字体编辑器** "在"样式"窗格 **顶部** 打开  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

可视字体编辑器 **中所有字段** 都从"样式"窗格中的 CSS **中的值** 填充。  例如，定义在"样式"窗格中设置为 ，因此行高 `line-height` `160%` 文本字段将显示****，而单位 `160` 下拉列表显示 `%` 。  此外，还会自动设置滑块以匹配文本字段的值。  

字体 **编辑器由** 两部分组成：字体系列选择器和 CSS 属性编辑器。  

## <a name="the-font-family-selector"></a>字体系列选择器  

字体系列选择器是可视字体编辑器 **的上半部分**。  若要选择 CSS 规则的字体，在 CSS 编辑器中，使用 **字体系列** 选择器。  可以针对每个 CSS 规则选择主字体和回退字体。  

:::image type="complex" source="../media/font-editor-font-family.msft.png" alt-text="字体编辑器在"样式"窗格顶部打开，其中突出显示了"字体系列"选择器" lightbox="../media/font-editor-font-family.msft.png":::
   字体 **编辑器在** "样式" **窗格顶部打开** ，其中突出显示 **了"字体系列** "选择器  
:::image-end:::  

使用 **"字体系列** "下拉列表从字体列表中进行选择。  字体分为四个组。  

1.  计算字体，即样式窗格中样式表**提供的字体。**  
1.  系统字体，即当前操作系统上提供的字体。  
1.  常规字体系列，如 `serif` 或 `sans-serif` 。  
1.  全局值，如 `inherit` 、 `initial` 和 `unset` 。  
    
:::image type="complex" source="../media/font-editor-font-family-list.msft.png" alt-text="字体编辑器在"样式"窗格顶部打开，其中突出显示了"字体系列"选择器" lightbox="../media/font-editor-font-family-list.msft.png":::
   字体 **编辑器在** "样式" **窗格顶部打开** ，其中突出显示 **了"字体系列** "选择器  
:::image-end:::  

选择字体后，将显示另一个下拉菜单，供您选择回退字体。  你可以选择最多八种回退字体。  若要删除字体，请选择"删除 **字体系列"** 图标。  

<!--:::image type="complex" source="../media/font-editor-defining-fonts.msft.png" alt-text="The font editor with a defined list of fonts and fallback fonts" lightbox="../media/font-editor-defining-fonts.msft.png":::
   The **Font Editor** with a defined list of fonts and fallback fonts highlighted
:::image-end:::  -->

> [!NOTE]
> 如果选择字体系列全局值，将不会获得另一个下拉列表，因为 CSS 中没有回退。  

## <a name="the-css-properties-editor"></a>CSS 属性编辑器  

您可以在可视字体编辑器的下半部分更改 CSS **字体属性**。  可以使用任何 UI 控件更改字号、行高、字体粗细和字母间距。  所做的更改将立即在浏览器中应用。  

:::image type="complex" source="../media/font-editor-css-properties.msft.png" alt-text="字体编辑器在"样式"窗格顶部打开，其中突出显示了 CSS 属性" lightbox="../media/font-editor-css-properties.msft.png":::
   字体 **编辑器在** "样式" **窗格顶部打开** ，其中突出显示了 CSS 属性  
:::image-end:::  

您还可以使用可视字体编辑器 转换 CSS **单位**。  例如，您可以在 CSS 规则（其中字体大小滑块最初设置为****）上使用此工具 `16 pixels` 。  现在，使用单位下拉列表并选择值 `em` 。  `1 em`显示的 等于 `16 pixels` 。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/font-editor-setting-to-16px.msft.png" alt-text="将字体大小更改为 16 像素" lightbox="../media/font-editor-setting-to-16px.msft.png":::
         将字体大小更改为 `16 pixels`  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/font-editor-converted-to-em.msft.png" alt-text="打开"单位"下拉列表以转换为 em" lightbox="../media/font-editor-converted-to-em.msft.png":::
         打开要转换为的单位下拉列表 `em`  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

"单位"下拉列表提供所有可用的数值 CSS 单位。  字号、行高、字粗和间距都使用不同的单位。  当文本框具有焦点时，可以选择 和 `arrow up` `arrow down` 键来微调设置。  若要将滑块与键盘一同使用，请选择 `arrow left` 和 `arrow down` 键。  

CSS 属性编辑器还包括预设关键字。  若要使用预设关键字，请选择右侧 `Toggle Input Type` 图标。  UI 发生更改，并显示预设关键字下拉列表。  若要使用滑块和其他 UI 控件返回到 UI，请再次 `Toggle Input Type` 选择图标。  

:::image type="complex" source="../media/font-editor-preset-font-sizes.msft.png" alt-text="打开预设关键字界面" lightbox="../media/font-editor-preset-font-sizes.msft.png":::
   打开预设关键字界面  
:::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge 开发工具团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsIndex]: ../index.md "Microsoft Edge (Chromium) 开发人员工具 | Microsoft 文档"  
[DevtoolsExperimentalFeaturesIndex]: ../experimental-features/index.md "实验功能|Microsoft Docs"  
[DevtoolsExperimentalFeaturesIndexTurnOnExperimentalFeatures]: ../experimental-features/index.md#turn-on-experimental-features "打开实验性功能 - 实验|Microsoft Docs"  
