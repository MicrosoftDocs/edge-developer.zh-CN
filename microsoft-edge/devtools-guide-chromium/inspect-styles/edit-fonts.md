---
description: 了解如何使用 Microsoft Edge 开发人员工具中的“样式”窗格更改 CSS 字体样式和设置。
title: 在开发人员工具的“样式”窗格中编辑 CSS 字体样式和设置
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/11/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, 开发人员工具
no-loc:
- Enable new font editor tool within the Styles pane
ms.openlocfilehash: 5d9074ca65f9cb98662a1bc181f70ead4c4232e1
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439491"
---
# <a name="edit-css-font-styles-and-settings-in-the-styles-pane"></a>在“样式”窗格中编辑 CSS 字体样式和设置  

:::image type="icon" source="../media/experimental-tag-14px.msft.png":::

网页版式是用户体验的重要组成部分。  你希望确保你符合企业品牌准则，并且你的内容在各种设备上按预期显示。  必须使用大小和线条高度让文本更易于阅读。  用户可调整字体大小来满足个人需求。  对于特定字体在用户设备上不可用的情况，应提供回退字体选项。  

近年来，CSS 为版式提供了更好的支持。  有数十种不同的 CSS 单位可用于定义文本大小。  你还可以使用多个 CSS 属性来影响字体大小、间距、线条高度和其他版式特性。  

为了在使用版式时更加轻松，可视“**字体编辑器**”现在位于“**样式**”窗格中。  你可以更改字体设置，更改会立即呈现在浏览器中。  所有这些内容都无需深入了解 CSS。  

当前，**Enable new font editor tool within the Styles pane** 功能处于试验阶段，你需要[为 Microsoft Edge 开发人员工具启用它][DevtoolsExperimentalFeaturesIndexTurnOnExperimentalFeatures]。  

“**样式**”窗格中的任何 CSS（字体定义或内嵌样式）都会自动显示一个图标，用于打开可视“**字体编辑器**”。  若要打开可视“**字体编辑器**”，请选择“**字体编辑器**”图标。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/font-editor-icon.msft.png" alt-text="样式窗格中用于编辑字体设置的图标" lightbox="../media/font-editor-icon.msft.png":::
         “**样式**”窗格中用于编辑字体设置的图标  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/font-editor-open.msft.png" alt-text="字体编辑器在样式窗格顶部打开" lightbox="../media/font-editor-open.msft.png":::
         “**字体编辑器**”在“**样式**”窗格顶部打开  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

可视“**字体编辑器**”中的所有字段都是根据“**样式**”窗格中的 CSS 值填充的。  例如，`line-height` 定义在“**样式**”窗格中设置为 `160%`，因此线条高度文本字段显示 `160`，而单位下拉列表显示 `%`。  此外，滑块会自动设置为与文本字段的值匹配。  

“**字体编辑器**”由两部分组成：“字体系列”选择器和“CSS 属性”编辑器。  

## <a name="the-font-family-selector"></a>“字体系列”选择器  

“字体系列”选择器位于可视“**字体编辑器**”的上部。  若要选择 CSS 规则的字体，请在 CSS 编辑器中使用“**字体系列**”选择器。  可为每个 CSS 规则选择主字体和回退字体。  

:::image type="complex" source="../media/font-editor-font-family.msft.png" alt-text="字体编辑器在样式窗格顶部打开，突出显示字体系列选择器" lightbox="../media/font-editor-font-family.msft.png":::
   “**字体编辑器**”在“**样式**”窗格顶部打开，突出显示“**字体系列**”选择器  
:::image-end:::  

使用“**字体系列**”下拉列表从字体列表中进行选择。  字体分为四组。  

1.  计算字体，即“**样式**”窗格的样式表中可用的字体。  
1.  系统字体，即当前操作系统上可用的字体。  
1.  常规字体系列，如 `serif` 或 `sans-serif`。  
1.  全局值，如 `inherit`、`initial` 和 `unset`。  
    
:::image type="complex" source="../media/font-editor-font-family-list.msft.png" alt-text="字体编辑器在样式窗格顶部打开，突出显示字体系列选择器" lightbox="../media/font-editor-font-family-list.msft.png":::
   “**字体编辑器**”在“**样式**”窗格顶部打开，突出显示“**字体系列**”选择器  
:::image-end:::  

在你选择字体后，系统将显示另一个下拉菜单供你选择回退字体。  最多可选择八种回退字体。  若要删除字体，请选择“**删除字体系列**”图标。  

<!--:::image type="complex" source="../media/font-editor-defining-fonts.msft.png" alt-text="The font editor with a defined list of fonts and fallback fonts" lightbox="../media/font-editor-defining-fonts.msft.png":::
   The **Font Editor** with a defined list of fonts and fallback fonts highlighted
:::image-end:::  -->

> [!NOTE]
> 如果为字体系列选择全局值，则不会再出现另一个下拉列表，因为 CSS 中没有该字体系列的回退字体。  

## <a name="the-css-properties-editor"></a>“CSS 属性”编辑器  

可在可视“**字体编辑器**”的下部更改 CSS 字体属性。  可使用任何用户界面控件更改字体大小、线条高度、字体粗细和字母间距。  所做的更改将立即在浏览器中应用。  

:::image type="complex" source="../media/font-editor-css-properties.msft.png" alt-text="字体编辑器在样式窗格顶部打开，突出显示 CSS 属性" lightbox="../media/font-editor-css-properties.msft.png":::
   “**字体编辑器**”在“**样式**”窗格顶部打开，突出显示 CSS 属性  
:::image-end:::  

也可使用可视“**字体编辑器**”转换 CSS 单位。  例如，可以在 CSS 规则上使用该工具，其中“**字体大小**”滑块最初设置为 `16 pixels`。  现在，使用单位下拉菜单并选择值 `em`。  显示的 `1 em` 等于 `16 pixels`。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/font-editor-setting-to-16px.msft.png" alt-text="将字体大小更改为 16 像素" lightbox="../media/font-editor-setting-to-16px.msft.png":::
         将字体大小更改为 `16 pixels`  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/font-editor-converted-to-em.msft.png" alt-text="打开单位下拉列表以转换为 em" lightbox="../media/font-editor-converted-to-em.msft.png":::
         打开单位下拉列表以转换为 `em`  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

单位下拉列表提供所有可用的数值 CSS 单位。  字体大小、线条高度、字体粗细和间距都使用不同的单位。  当文本框有焦点时，你可以选择 `arrow up` 和 `arrow down` 键微调设置。  若要将滑块与键盘配合使用，请选择 `arrow left` 和 `arrow down` 键。  

“CSS 属性”编辑器还包括预设关键字。  若要使用预设关键字，请在右侧选择 `Toggle Input Type` 图标。  用户界面将发生变化，并显示预设关键字的下拉列表。  若要使用滑块和其他用户界面控件返回用户界面，请再次选择 `Toggle Input Type` 图标。  

:::image type="complex" source="../media/font-editor-preset-font-sizes.msft.png" alt-text="打开预设关键字界面" lightbox="../media/font-editor-preset-font-sizes.msft.png":::
   打开预设关键字界面  
:::image-end:::  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge 开发人员工具团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsIndex]: ../index.md "Microsoft Edge (Chromium) 开发人员工具 | Microsoft Docs"  
[DevtoolsExperimentalFeaturesIndex]: ../experimental-features/index.md "试验功能 | Microsoft Docs"  
[DevtoolsExperimentalFeaturesIndexTurnOnExperimentalFeatures]: ../experimental-features/index.md#turn-on-experimental-features "打开试验功能 - 试验功能 | Microsoft Docs"  
