---
description: “新增功能”工具现在为“欢迎”，内含“样式”窗格中的可视字体编辑器、CSS 弹性框调试工具等。
title: DevTools 中的新增功能 (Microsoft Edge 89)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.localizationpriority: high
ms.openlocfilehash: 9eb9f35427829dbe262b4c71d8ff5474b28eae77
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597153"
---
<!-- Copyright Jecelyn Yeen 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->  
# <a name="whats-new-in-devtools-microsoft-edge-89"></a>DevTools 中的新增功能 (Microsoft Edge 89)  

[!INCLUDE [contact DevTools team note](../../includes/edge-whats-new-note.md)]  

## <a name="whats-new-is-now-welcome"></a>“新增功能”工具现在为“欢迎”  

<!--  Title: What's New is now Welcome  -->  
<!--  Subtitle: The What's New tool now has a new appearance and a new name:  Welcome -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

Microsoft Edge DevTools 中的“**新增功能**”工具现在具有新的外观和新名称：“**欢迎**”。  “**欢迎**”工具仍会显示最新的 DevTools 新闻和更新。  它现在还包括指向 Microsoft Edge DevTools 文档的链接、提交反馈的方式等。  若要在每次更新 Microsoft Edge 后显示“**欢迎**”工具，请选中标题下的“**每次更新后打开选项卡**”旁边的复选框。  若要关闭“**欢迎**”工具，请选择选项卡标题右侧的 **X**。  如果你更喜欢原来的“**新增功能**”工具，请导航至“[设置][DevtoolsCustomizeIndexSettings]” > “**试验**”，并取消选中“**启用‘欢迎’选项卡**”旁边的复选框。  

:::image type="complex" source="../../media/2021/01/welcome-tool-whats-new-88.msft.png" alt-text="突出显示“欢迎”工具" lightbox="../../media/2021/01/welcome-tool-whats-new-88.msft.png":::
   突出显示“**欢迎**”工具  
:::image-end:::  

## <a name="visual-font-editor-in-the-styles-pane"></a>“样式”窗格中的可视字体编辑器  

<!--  Title: Visual font editor in the Styles pane  -->  
<!--  Subtitle: Visual font editor in the Styles pane -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

在 CSS 中处理字体时，请使用新的可视[字体编辑器][DevtoolsInspectStylesEditFonts]。  你可以定义回退字体，并使用滑块定义字体粗细、大小、行高和间距。  **字体编辑器**可帮助你完成以下操作。  

*   在不同字体属性的单位之间切换  
*   在不同字体属性的关键字之间切换  
*   转换单位  
*   生成准确的 CSS 代码  
    
若要启用此试验，请导航至“[设置][DevtoolsCustomizeIndexSettings]” > “**试验**”，然后选中“**在‘样式’窗格中启用新的字体编辑器工具**”旁边的复选框。  有关详细信息，请导航至“[在 DevTools 的‘样式’窗格中编辑 CSS 字体样式和设置][DevtoolsInspectStylesEditFonts]”。  若要在 Chromium 开源项目中查看此功能的历史记录，请导航至问题 [1093229][CR1093229]。  

:::image type="complex" source="../../media/2021/01/visual-font-editor.msft.png" alt-text="可视字体编辑器在“样式”窗格中突出显示" lightbox="../../media/2021/01/visual-font-editor.msft.png":::
   可视**字体编辑器**在“**样式**”窗格中突出显示  
:::image-end:::  

## <a name="css-flexbox-debugging-tools"></a>CSS 弹性框调试工具  

弹性框调试功能正在积极开发中。  若要启用以下两个功能的试验，请导航至“[设置][DevtoolsCustomizeIndexSettings]” > “**试验**”，然后选择“**启用新的 CSS 弹性框调试功能**”旁边的复选框。  若要在 Chromium 开源项目中查看此功能的历史记录，请导航至问题 [1136394][CR1136394] 和 [1139949][CR1139949]。  

### <a name="new-flexbox-flex-icon-helps-identify-and-display-flex-containers"></a>新的弹性框 (flex) 图标有助于识别和显示 flex 容器  

<!--  Title: Display Flexbox containers with Flexbox (flex) icon  -->  
<!--  Subtitle: New Flexbox (flex) icon in the Elements tool help you identify Flexbox containers in your code.  When toggled, the adorner displays and hides outlines of the flex container to help you debug the layout -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

在“**元素**”工具中，新的弹性框 (flex) 图标可帮助你识别代码中的弹性框容器。  选择弹性框 (flex) 图标可打开或关闭显示弹性框容器轮廓的覆盖效果。  可在“**布局**”窗格中自定义覆盖的颜色，其位于“**样式**”和“**已计算**”旁边。  

:::row:::
   :::column span="":::
      若要打开和关闭显示弹性框容器轮廓的覆盖效果，请选择弹性框 (`flex`) 图标。  
   :::column-end:::
   :::column span="":::
      可在“**布局**”窗格中的“**样式**”和“**已计算**”旁边自定义覆盖的颜色。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-flex-container.msft.png" alt-text="弹性框 (flex) 图标和网页突出显示" lightbox="../../media/2021/01/elements-flex-container.msft.png":::
         **弹性框** (`flex`) 图标和网页突出显示 :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-layout-flex-container.msft.png" alt-text="“布局”窗格中突出显示的弹性框覆盖" lightbox="../../media/2021/01/elements-layout-flex-container.msft.png":::
         “**布局**”窗格中突出显示的**弹性框覆盖**  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

### <a name="display-alignment-icons-and-visual-guides-when-flexbox-layouts-change-using-css-properties"></a>使用 CSS 属性更改弹性框布局时显示对齐图标和可视化向导  

<!--  Title: Display alignment icons and visual guides for changes to Flexbox layouts from CSS properties  -->  
<!--  Subtitle:  CSS autocomplete in the Styles tool now displays icons next to Flexbox properties to help you review the effect a property has on your Flexbox layout -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

当你编辑弹性框布局的 CSS 时，“**样式**”窗格中的 CSS 自动完成现在会在相关弹性框属性旁边显示有用的图标。  若要尝试此新功能，请打开“**元素**”工具并选择一个 flex 容器。  然后在“**样式**”窗格中添加或更改该容器上的属性。  

:::row:::
   :::column span="":::
      自动完成菜单现在显示指示对齐属性效果的图标，例如 `align-content` 和 `align-items`。  
   :::column-end:::
   :::column span="":::
      此外，DevTools 现在还会显示一条指导线，帮助你更好地查看 `align-items` CSS 属性。  `gap` CSS 属性也受支持。  在下图中，`gap` CSS 属性设置为 `gap: 12px;`，并显示每个间隙的阴影图案。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-flex-container-align.msft.png" alt-text="突出显示以 align- 开头的 CSS 属性的“自动完成”菜单" lightbox="../../media/2021/01/elements-flex-container-align.msft.png":::
         突出显示以以下内容开头的 CSS 属性的“自动完成”菜单 `align-`  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-flex-container-align-items-center-gap-12px.msft.png" alt-text="CSS 属性和网页中的弹性框间隙突出显示" lightbox="../../media/2021/01/elements-flex-container-align-items-center-gap-12px.msft.png":::
         CSS 属性和网页中的弹性框 `gap` 突出显示  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="add-tools-quickly-with-new-more-tools-button"></a>使用新的“更多工具”按钮快速添加工具  

<!--  Title: Add tools quickly with new More Tools button  -->  
<!--  Subtitle: A convenient way to open new tools in Microsoft Edge DevTools -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

现在，你有了一种在 Microsoft Edge DevTools 中打开更多工具的新方法。  在打开此试验后，“**更多工具**”图标将在主面板右侧显示为加号 (`+`)。  若要显示要添加到主面板的其他工具的列表，请选择“**更多工具**”\(`+`\) 图标。  若要启用此试验，请导航至“[设置][DevtoolsCustomizeIndexSettings]” > “**试验**”，然后选中“**启用 + 按钮选项卡菜单以打开更多工具**”旁边的复选框。  

:::image type="complex" source="../../media/2021/01/more-tools.msft.png" alt-text="DevTools 中突出显示“更多工具”" lightbox="../../media/2021/01/more-tools.msft.png":::
   DevTools 中突出显示“**更多工具**”  
:::image-end:::  

## <a name="assistive-technologies-now-announce-position-and-count-of-css-suggestions"></a>辅助技术现在显示 CSS 建议的位置和计数  

<!--  Title: Assistive technologies now announce position and count of CSS suggestions  -->  
<!--  Subtitle: CSS suggestions are now easier to navigate using screen readers -->  

编辑 CSS 时，你将获得功能的下拉列表。  辅助技术用户无法使用此功能，因为它是在 Microsoft Edge 版本 89 中公布的。  辅助技术用户现在可以在“**样式**”窗格中浏览 CSS 建议。  在 Microsoft Edge 版本 88 及更早版本中，辅助技术公布了 `Suggestion`，因为用户在“**导航**”窗格中编辑 CSS 时浏览了建议列表。  在 Microsoft Edge 版本 89 中，辅助技术用户现在可以听到当前建议的位置和计数。  当用户浏览建议列表时，每条建议都会公布，例如建议 3/5。  若要了解有关在 DevTools 中编写 CSS 的详细信息，请导航至“[更改 CSS][DevtoolsCssReferenceChangeCss]”。  若要在 Chromium 开源项目中查看此功能的历史记录，请导航至问题 [1157329][CR1157329]。  

若要在启用此试验的情况下查看显示和朗读多条建议的视频，请导航至 YouTube 上的“[Voiceover 公布 devtools 选项](https://youtu.be/9TcUpleEwwA)”。  

:::image type="complex" source="../../media/2021/01/announce-css-suggestion.msft.png" alt-text="“样式”窗格中突出显示建议" lightbox="../../media/2021/01/announce-css-suggestion.msft.png":::
   “**样式**”窗格中突出显示 `suggestion` 列表  
:::image-end:::  

## <a name="emulate-surface-duo-and-samsung-galaxy-fold"></a>模拟 Surface Duo 和 Samsung Galaxy Fold  

<!--  Title: Emulate new dual-screen and foldable devices  -->  
<!--  Subtitle: Test the appearance and feel of your website or app with Surface Duo and Samsung Galaxy Fold emulators -->  

在以下设备上的 Microsoft Edge 中测试你的网站或应用的外观。  

*   [Surface Duo][MicrosoftSurfaceDevicesSurfaceDuo]  
*   [Samsung Galaxy Fold][SamsungUsMobileGalaxyFold]  
    
启用“**试验 Web 平台功能**”以访问新的 [CSS 媒体屏幕跨越功能][DualScreenWebCssMediaSpanning]和 [getWindowSegments JavaScript API][DualScreenWebJavascriptGetwindowsegments]。  导航至 `edge://flags`，然后切换“**试验 Web 平台功能**”旁边的标记。  为帮助增强用于双屏幕和可折叠设备的网站或应用，请在[模拟设备][DevtoolsDeviceModeIndex]时使用以下功能。  

*   [跨越][DevtoolsDeviceModeDualScreenFoldablesTestFoldableDualScreenDevices]，即你的网站（或应用）跨两个屏幕显示。  
*   [呈现接缝][DualScreenIntroductionHowToWorkWithSeam]，即两个屏幕之间的空间。  
    
若要在 Chromium 开源项目中查看此功能的历史记录，请导航至问题 [1054281][CR1054281]。  

:::image type="complex" source="../../media/2021/01/emulate-surface-device-surface-duo.msft.png" alt-text="模拟双屏幕" lightbox="../../media/2021/01/emulate-surface-device-surface-duo.msft.png":::
   模拟双屏幕  
:::image-end:::  

## <a name="microsoft-edge-developer-tools-for-visual-studio-code-version-112"></a>Microsoft Edge Developer Tools for Visual Studio Code 1.1.2 版  

适用于 Microsoft Visual Studio Code 的 [Microsoft Edge Developer Tools for Visual Studio Code][VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools] 扩展版本 1.1.2 自上一个版本以来有以下更改。  Microsoft Visual Studio Code 会自动更新扩展。  若要手动更新到版本 1.1.2，请导航至“[手动更新扩展][VisualstudioCodeDocsEditorExtensionGalleryUpdateExtensionManually]”。  

*   为目标列表上的每个项目添加了“**关闭实例**”按钮 ([#248][GithubMicrosoftVscodeEdgeDevtoolsPull248])  
*   将 [Microsoft Edge DevTools][DevtoolsIndex] 版本从 84.0.522.63 升级到 [85.0.564.40][DevtoolsWhatsNew85] ([#235][GithubMicrosoftVscodeEdgeDevtoolsPull235])  
*   将 [Microsoft Edge 调试程序][VisualstudioMarketplaceMsjsdiagDebuggerMicrosoftEdge]作为依赖项包括在内 ([#233][GithubMicrosoftVscodeEdgeDevtoolsPull233])  
*   已实施设置选项以更改扩展主题 ([#229][GithubMicrosoftVscodeEdgeDevtoolsPull229])  
    
你可以在 [vscode-edge-devtools GitHub repo][GithubMicrosoftVscodeEdgeDevtools] 上提交问题并参与提升扩展。  

## <a name="announcements-from-the-chromium-project"></a>来自 Chromium 项目的公告  

[!INCLUDE [contact DevTools team note](../../includes/chromium-whats-new-note.md)]  

### <a name="capture-node-screenshot-beyond-viewport"></a>捕获视区以外的节点屏幕截图  

在 Microsoft Edge 版本 89 中，节点屏幕截图更为准确，即使节点中的内容在视区中不可见，也能捕获完整节点。  在“**元素**”工具中，将鼠标悬停在某个元素上，打开上下文菜单（右键单击），然后选择“**捕获节点屏幕**”。  若要在 Chromium 开源项目中查看此功能的历史记录，请导航至问题 [1003629][CR1003629]。  

:::image type="complex" source="../../media/2021/01/capture-node-screenshot.msft.png" alt-text="“元素”工具中的上下文菜单上突出显示“捕获节点屏幕截图”" lightbox="../../media/2021/01/capture-node-screenshot.msft.png":::
   “**元素**”工具中的上下文菜单上突出显示“**捕获节点屏幕截图**”  
:::image-end:::  

### <a name="elements-tool-updates"></a>“元素”工具更新  

#### <a name="support-forcing-the-target-css-state"></a>支持强制 :target CSS 状态  

现在可使用 DevTools 强制 [:target][MdnDocsWebCssTarget] CSS 伪类。  当唯一元素（目标元素）具有与 URL 片段匹配的 `id` 时，将触发 `:target` 伪类。  例如，`http://www.example.com/index.html#section1` URL 在带有 `id="section1"` 的 HTML 元素上触发 `:target` 伪类。  若要尝试突出显示了第 1 部分的演示，请导航至“[CSS :target 演示][GithubMicrosoftedgeDevtoolssamplesWhatsNew89TargetCssDemoHtmlSection1]”。  若要在 Chromium 开源项目中查看此功能的历史记录，请导航至问题 [1156628][CR1156628]。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-styles-none-forced.msft.png" alt-text="突出显示网页，未强制 CSS" lightbox="../../media/2021/01/elements-styles-none-forced.msft.png":::
         突出显示网页，未强制 CSS  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-styles-target-forced.msft.png" alt-text="已强制 :target CSS 且突出显示网页" lightbox="../../media/2021/01/elements-styles-target-forced.msft.png":::
         `:target` 已强制 CSS 且突出显示网页  
      :::image-end:::  
   :::column-end:::
:::row-end:::

#### <a name="use-duplicate-elements-to-copy-elements"></a>使用“复制元素”复制元素  

使用新的“**复制元素**”快捷方式克隆元素。  在“**元素**”工具中，将鼠标悬停在某个元素上，打开上下文菜单（右键单击），然后选择“**复制元素**”。  将在选定元素下创建一个新元素。  若要使用键盘快捷方式复制元素，请选择“`Shift`+`Alt`+`Down Arrow`”(Windows/Linux) 或“`Shift`+`Option`+`Down Arrow`”(macOS)。  若要在 Chromium 开源项目中查看此功能的历史记录，请导航至问题 [1150797][CR1150797]。  

:::image type="complex" source="../../media/2021/01/elements-duplicate-element.msft.png" alt-text="“复制元素”在“元素”工具中某个元素的上下文菜单中突出显示" lightbox="../../media/2021/01/elements-duplicate-element.msft.png":::
   “**复制元素**”在“**元素**”工具中某个元素的上下文菜单中突出显示  
:::image-end:::  

#### <a name="color-pickers-for-custom-css-properties"></a>自定义 CSS 属性的颜色选取器  

“**样式**”窗格现在显示自定义 CSS 属性的颜色选取器。  若要循环浏览颜色值的 RGBA、HSLA 和 Hex 格式，请按住 `Shift` 并选择颜色选取器。  若要在 Chromium 开源项目中查看此功能的历史记录，请导航至问题 [1147016][CR1147016]。  

:::image type="complex" source="../../media/2021/01/elements-styles-change-color-format.msft.png" alt-text="自定义 CSS 属性的颜色选取器" lightbox="../../media/2021/01/elements-styles-change-color-format.msft.png":::
   自定义 CSS 属性的颜色选取器  
:::image-end:::  

#### <a name="copy-css-classes-and-properties"></a>复制 CSS 类和属性  

现在，你可以通过上下文菜单中的几个新选项更快地复制 CSS 属性。  在“**元素**”工具中，选择一个元素。  若要复制值，请在“**样式**”窗格中，将鼠标悬停在 CSS 类或 CSS 属性上，打开上下文菜单（右键单击），然后选择复制选项。  

:::row:::
   :::column span="":::
      CSS 类的复制选项。  
      
      | 选项 | 详细信息 |  
      |:--- |:--- |  
      | **复制选择器** | 复制当前选择器名称。 |  
      | **复制规则** | 复制当前选择器的规则。 |  
      | **复制所有声明** | 复制当前规则下的所有声明，包括无效和有前缀的属性。 |  
   :::column-end:::
   :::column span="":::
      CSS 属性的复制选项。  
      
      | 选项 | 详细信息 |      
      |:--- |:--- |  
      | **复制声明** | 复制当前行的声明。 |  
      | **复制属性** | 复制当前行的属性。 |  
      | **复制值** | 复制当前行的值。 |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/copy-css-class.msft.png" alt-text="上下文菜单中 CSS 类的复制选项" lightbox="../../media/2021/01/copy-css-class.msft.png":::
         上下文菜单中 CSS 类的复制选项  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/copy-css-property-cropped.msft.png" alt-text="上下文菜单中 CSS 属性的复制选项" lightbox="../../media/2021/01/copy-css-property.msft.png":::
         上下文菜单中 CSS 属性的复制选项  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

若要在 Chromium 开源项目中查看此功能的历史记录，请导航至问题 [1152391][CR1152391]。  

### <a name="cookies-updates"></a>Cookie 更新  

#### <a name="new-option-to-display-url-decoded-cookies"></a>用于显示 URL 解码的 Cookie 的新选项  

现在，你可以选择在“**Cookie**”窗格中显示 URL 解码的 Cookie 值。  若要显示解码的 Cookie，请导航至“**应用程序**” > “**Cookie**”窗格，选择列表中的任何 Cookie，然后选中“**显示解码的 URL**”旁边的复选框。  若要在 Chromium 开源项目中查看此功能的历史记录，请导航至问题 [997625][CR997625]。  

:::image type="complex" source="../../media/2021/01/application-cookies-show-url-decoded.msft.png" alt-text="用于显示 URL 解码的 Cookie 的选项" lightbox="../../media/2021/01/application-cookies-show-url-decoded.msft.png":::
   用于显示 URL 解码的 Cookie 的选项  
:::image-end:::  

#### <a name="filter-and-clear-visible-cookies"></a>筛选和清除可见的 Cookie  

在 Microsoft Edge 版本 88 或更早版本中，“**应用程序**”工具只提供了一种使用“**清除所有 Cookie**”按钮清除所有 Cookie 的方法。  在 Microsoft Edge 版本 89 中，现在可以选择“**清除筛选的 Cookie**”以便仅删除筛选的 Cookie。  若要筛选 Cookie，请导航至“**应用程序**” > “**Cookie**”，然后在“**筛选器**”文本框中键入。  若要删除显示的 Cookie，请选择“**清除筛选的 Cookie**”按钮。  若要显示所有其他 Cookie，请清除筛选器文本。  若要在 Chromium 开源项目中查看此功能的历史记录，请导航至问题 [978059][CR978059]。  

:::image type="complex" source="../../media/2021/01/application-cookies-clear-filtered-cookies.msft.png" alt-text="仅清除可见的 Cookie" lightbox="../../media/2021/01/application-cookies-clear-filtered-cookies.msft.png":::
   仅清除可见的 Cookie  
:::image-end:::  

#### <a name="new-option-to-clear-third-party-cookies-in-the-storage-pane"></a>“存储”窗格中用于清除第三方 Cookie 的新选项  

默认情况下，DevTools 现在仅清除第一方 Cookie。  若要仅清除网站数据和第一方 Cookie，请导航至“**应用程序**” > “**存储**”，然后选择“**清除网站数据**”。  

若要清除网站数据和所有 Cookie，请导航至“**应用程序**” > “**存储**”。  选择“**包括第三方 Cookie**”旁边的复选框，然后选择“**清除网站数据**”。  

若要在 Chromium 开源项目中查看此功能的历史记录，请导航至问题 [1012337][CR1012337]。  

:::image type="complex" source="../../media/2021/01/application-storage-clear-site-data-including-third-party-cookies.msft.png" alt-text="用于清除第三方 Cookie 的选项" lightbox="../../media/2021/01/application-storage-clear-site-data-including-third-party-cookies.msft.png":::
   用于清除第三方 Cookie 的选项  
:::image-end:::  

### <a name="network-tool-updates"></a>网络工具更新  

#### <a name="persist-record-network-log-setting"></a>保留“记录网络日志”设置  

在 Microsoft Edge 版本 88 或更早版本中，当网页刷新时，DevTools 将重置“**记录网络日志**”设置。  在 Microsoft Edge 版本 89 中，DevTools 现在将保留“**记录网络日志**”设置。  若要在 Chromium 开源项目中查看此功能的历史记录，请导航至问题 [1122580][CR1122580]。  

:::image type="complex" source="../../media/2021/01/network-log.msft.png" alt-text="记录网络日志" lightbox="../../media/2021/01/network-log.msft.png":::
   记录网络日志  
:::image-end:::  

#### <a name="online-option-is-now-no-throttling-option"></a>“联机”选项现在是“无限制”选项  

网络模拟选项“**联机**”现已重命名为“**无限制**”。  若要在 Chromium 开源项目中查看此功能的历史记录，请导航至问题 [1028078][CR1028078]。  

:::image type="complex" source="../../media/2021/01/network-no-throttling.msft.png" alt-text="“无限制”选项" lightbox="../../media/2021/01/network-no-throttling.msft.png":::
   “**无限制**”选项  
:::image-end:::  

### <a name="new-copy-options-in-the-console-tool-sources-tool-and-styles-pane"></a>“控制台”工具、“源”工具和“样式”窗格中新的复制选项

#### <a name="copy-object-in-the-console-and-sources-tool"></a>在“控制台”和“源”工具中复制对象  

现在，你可以在“**控制台**”和“**源**”工具中复制对象值。  复制对象值的能力在处理大型对象时很有用。  若要在 Chromium 开源项目中查看此功能的历史记录，请导航至问题 [1148353][CR1148353] 和 [1149859][CR1149859]。  

:::row:::
   :::column span="":::
      在“**控制台**”工具中，将鼠标悬停在某个对象上，打开上下文菜单（右键单击），然后选择“**复制对象**”。  
   :::column-end:::
   :::column span="":::
      在“**源**”工具中，在断点处，将鼠标悬停在某个对象上，在“**对象**”弹出窗口中突出显示某个对象，打开上下文菜单（右键单击），然后选择“**复制对象**”。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/console-copy-object.msft.png" alt-text="在“控制台”中复制对象" lightbox="../../media/2021/01/console-copy-object.msft.png":::
         在“**控制台**”中复制对象  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/sources-breakpoint-object-copy-object.msft.png" alt-text="在“源”中复制对象" lightbox="../../media/2021/01/sources-breakpoint-object-copy-object.msft.png":::
         在“**源**”中复制对象  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

#### <a name="copy-file-name-in-the-sources-tool-and-styles-pane"></a>在“源”工具和“样式”窗格中复制文件名  

现在，你可以使用上下文菜单复制文件名。  若要在 Chromium 开源项目中查看此功能的历史记录，请导航至问题 [1155120][CR1155120]。  

:::row:::
   :::column span="":::
      在“**源**”工具中，将鼠标悬停在某个文件名上，打开上下文菜单（右键单击），然后选择“**复制文件名**”。  
   :::column-end:::
   :::column span="":::
      在“**元素**”工具 >“**样式**”窗格中，将鼠标悬停在某个文件名上，打开上下文菜单（右键单击），然后选择“**复制文件名**”。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/sources-copy-file-name.msft.png" alt-text="在“源”中复制文件名" lightbox="../../media/2021/01/sources-copy-file-name.msft.png":::
         在“**源**”中复制文件名  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-styles-copy-file-name.msft.png" alt-text="在“样式”窗格中复制文件名" lightbox="../../media/2021/01/elements-styles-copy-file-name.msft.png":::
         在“**样式**”窗格中复制文件名  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

### <a name="updates-to-frame-details"></a>帧详细信息更新  

#### <a name="service-workers-information-in-frame-details"></a>帧详细信息中的服务工作进程信息  

DevTools 现在在父帧下列出一个专用的服务工作进程。  下图显示了服务工作进程的详细信息。  若要显示服务工作进程详细信息，请导航至“**应用程序**” > “**帧**” > `top` > “**服务工作进程**”，然后选择一个服务工作进程。  若要在 Chromium 开源项目中查看此功能的历史记录，请导航至问题 [1122507][CR1122507]。  

:::image type="complex" source="../../media/2021/01/application-frames-service-workers-details.msft.png" alt-text="帧详细信息中的服务工作进程信息" lightbox="../../media/2021/01/application-frames-service-workers-details.msft.png":::
   **帧**详细信息中的**服务工作进程**信息  
:::image-end:::  

#### <a name="measure-memory-information-in-frame-details"></a>帧详细信息中的“测量内存”信息  

`performance.measureMemory()` API 状态现在显示在“**API 可用性**”部分下。  新的 `performance.measureMemory()` API 估计整个网页的内存使用情况。  若要在 Chromium 开源项目中查看此功能的历史记录，请导航至问题 [1139899][CR1139899]。  

:::image type="complex" source="../../media/2021/01/application-frames-measure-memory.msft.png" alt-text="测量内存" lightbox="../../media/2021/01/application-frames-measure-memory.msft.png":::
   测量内存  
:::image-end:::  

### <a name="dropped-frames-in-the-performance-tool"></a>“性能”工具中丢弃的帧  

当你[在“性能”工具中分析负载性能][DevtoolsEvaluatePerformanceReferenceRecordLoadPerformance]时，“**帧**”部分现在会将丢弃的帧标记为红色。  若要显示帧速率，请将鼠标悬停在丢弃的帧上。  若要在 Chromium 开源项目中查看此功能的历史记录，请导航至问题 [1075865][CR1075865]。  

:::image type="complex" source="../../media/2021/01/performance-frames-dropped-frames-red.msft.png" alt-text="丢弃的帧" lightbox="../../media/2021/01/performance-frames-dropped-frames-red.msft.png":::
   丢弃的帧  
:::image-end:::  

#### <a name="new-color-contrast-calculation---advanced-perceptual-contrast-algorithm-apca"></a>新的颜色对比度计算 - 高级感知对比度算法 (APCA)  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

[高级感知对比度算法 (APCA)][GithubW3cSilverGuidelinesMethodsMethodFontCharacteristicContrastHtml] 取代了[颜色选取器][DevtoolsAccessibilityReferenceViewContrastRatioTextElementColorPicker]中的 [AA][W3cWaiWcag21QuickrefContrastMinimum]/[AAA][W3cWaiWcag21QuickrefContrastEnhanced] 准则对比率。  APCA 是一种计算对比度的新方法。  它基于对颜色感知的新式研究。  与 AA/AAA 准则相比，APCA 更依赖于上下文。  对比度是根据文本、颜色和上下文的以下空间属性计算的。  

*   文本的空间属性，包括字体粗细和大小。  
*   颜色的空间属性，包括文本和背景之间的感知对比度。  
*   上下文的空间属性，包括环境光线、周围环境和预期用途。  
    
若要启用此试验，请导航至“[设置][DevtoolsCustomizeIndexSettings]” > “**试验**”，然后选中“**启用新的高级感知对比度算法 (APCA) 以替换以前的对比率和 AA/AAA 准则**”旁边的复选框。  若要在 Chromium 开源项目中查看此功能的历史记录，请导航至问题 [1121900][CR1121900]。  

:::image type="complex" source="../../media/2021/01/advanced-perceptual-contrast-algorithm.msft.png" alt-text="颜色选取器中的 APCA" lightbox="../../media/2021/01/advanced-perceptual-contrast-algorithm.msft.png":::
   颜色选取器中的 APCA  
:::image-end:::  

## <a name="download-the-microsoft-edge-preview-channels"></a>下载 Microsoft Edge 预览频道  

如果你使用的是 Windows、Linux 或 macOS，请考虑使用 [ Microsoft Edge 预览频道][MicrosoftEdgePreviewChannels]作为默认开发浏览器。  预览频道使你能够访问最新的 DevTools 功能。  

## <a name="getting-in-touch-with-microsoft-edge-devtools-team"></a>联系 Microsoft Edge DevTools 团队  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]

<!-- links -->  

[DevtoolsWhatsNew85]: ../../2020/06/devtools.md "DevTools 中的新增功能 (Microsoft Edge 85) | Microsoft Docs"  

[DevtoolsAccessibilityReferenceViewContrastRatioTextElementColorPicker]: ../../../accessibility/color-picker.md "使用颜色选取器来测试文本颜色|Microsoft Docs"  
[DevtoolsCssReferenceChangeCss]: ../../../css/reference.md#change-css "更改 CSS - CSS 参考 |Microsoft Docs"  
[DevtoolsCustomizeIndexSettings]: ../../../customize/index.md#settings "设置 - 自定义 Microsoft Edge DevTools | Microsoft Docs"  
[DevtoolsCustomizeShortcuts]: ../../../customize/shortcuts.md "自定义 Microsoft Edge DevTools 中的键盘快捷方式 | Microsoft Docs"  
[DevtoolsDeviceModeDualScreenFoldablesTestFoldableDualScreenDevices]: ../../../device-mode/dual-screen-and-foldables.md#test-on-foldable-and-dual-screen-devices "在可折叠和双屏幕设备上进行测试 - 在 Microsoft Edge DevTools 中模拟双屏幕和可折叠设备 | Microsoft Docs"  
[DevtoolsDeviceModeIndex]: ../../../device-mode/index.md "在 Microsoft Edge 开发人员工具中模拟移动设备 | Microsoft Docs"  
[DevtoolsDeviceModeIndexSimulateMobileViewport]: ../../../device-mode/index.md#simulate-a-mobile-viewport "模拟移动视区 - 在 Microsoft Edge DevTools 中模拟移动设备 | Microsoft Docs"  
[DevtoolsEvaluatePerformanceReferenceRecordLoadPerformance]: ../../../evaluate-performance/reference.md#record-load-performance "记录负载性能 - 性能分析参考 | Microsoft Docs"  
[DevtoolsIndex]: ../../../index.md "Microsoft Edge (Chromium) 开发人员工具概述|Microsoft Docs"  
[DevtoolsInspectStylesEditFonts]: ../../../inspect-styles/edit-fonts.md "在 DevTools 的“样式”窗格中编辑 CSS 字体样式和设置 | Microsoft Docs"  

[DualScreenIntroductionHowToWorkWithSeam]: /dual-screen/introduction#how-to-work-with-the-seam "如何处理接缝 - 双屏幕设备简介| Microsoft Docs"  
[DualScreenWebCssMediaSpanning]: /dual-screen/web/css-media-spanning "用于双屏幕检测的 CSS 媒体屏幕跨越功能 | Microsoft Docs"  
[DualScreenWebJavascriptGetwindowsegments]: /dual-screen/web/javascript-getwindowsegments "适用于双屏幕设备的 getWindowSegments JavaScript AP | Microsoft Docs"  

[GithubMicrosoftedgeDevtoolssamplesWhatsNew89TargetCssDemoHtmlSection1]: https://microsoftedge.github.io/DevToolsSamples/whats-new/89/target-css-demo.html#section-1 "第 1 部分 - DevTools 中“新增功能”的 CSS :target 演示 (Microsoft Edge 89) | GitHub"  
[GithubMicrosoftVscodeEdgeDevtools]: https://github.com/microsoft/vscode-edge-devtools "microsoft/vscode-edge-devtools | GitHub"  
[GithubMicrosoftVscodeEdgeDevtoolsPull229]: https://github.com/microsoft/vscode-edge-devtools/pull/229 "拉取 229：在设置中实现下拉列表以更改主题 | GitHub"  
[GithubMicrosoftVscodeEdgeDevtoolsPull233]: https://github.com/microsoft/vscode-edge-devtools/pull/233 "拉取 233：包括 Microsoft Edge 调试程序作为依赖项 | GitHub"  
[GithubMicrosoftVscodeEdgeDevtoolsPull235]: https://github.com/microsoft/vscode-edge-devtools/pull/235 "拉取 235：将 Edge DevTools 版本升级到 85.0.564.40 |GitHub"  
[GithubMicrosoftVscodeEdgeDevtoolsPull248]: https://github.com/microsoft/vscode-edge-devtools/pull/248 "拉取 248：将单个关闭按钮添加到实例面板 | GitHub"  
[GithubW3cSilverGuidelinesMethodsMethodFontCharacteristicContrastHtml]: https://w3c.github.io/silver/guidelines/methods/Method-font-characteristic-contrast.html "选择字体特征和背景色以提供足够的对比度以方便阅读 | W3C"  
[GithubW3cWebappsecTrustedTypesDistSpec]: https://w3c.github.io/webappsec-trusted-types/dist/spec  "受信任的类型 | W3C"  

[MicrosoftSurfaceDevicesSurfaceDuo]: https://www.microsoft.com/surface/devices/surface-duo "新的 Surface Duo | Microsoft"  

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download "Microsoft Edge 预览频道"  

[VisualstudioCodeDocsEditorExtensionGalleryUpdateExtensionManually]: https://code.visualstudio.com/docs/editor/extension-gallery#_update-an-extension-manually "手动更新扩展 - Extension Marketplace | Visual Studio Code"  

[VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools]: https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools "Microsoft Edge Tools for Visual Studio Code | Visual Studio Marketplace"  
[VisualstudioMarketplaceMsjsdiagDebuggerMicrosoftEdge]: https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge " Microsoft Edge 调试程序 | Visual Studio Marketplace"  

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium bug"  
[CR978059]: https://crbug.com/978059 "问题 978059：筛选 Cookie 后删除它们，删除所有 Cookie，而不仅仅是筛选的 Cookie | Chromium bug"  
[CR997625]: https://crbug.com/997625 "问题 997625：新功能请求 | 需要用于查看 Cookie 中的 URL 解码值的选项 | Chromium bug"  
[CR1003629]: https://crbug.com/1003629 "问题 1003629：捕获节点不再对折叠下方的节点进行屏幕截图。| Chromium bug"  
[CR1012337]: https://crbug.com/1012337 "问题 1012337：清除网站数据会破坏非 Google 网站上 Google 会话 | Chromium bug"  
[CR1028078]: https://crbug.com/1028078 "问题 1028078：在列表中将“联机”和“脱机”并排放置 | Chromium bug"  
[CR1054281]: https://crbug.com/1054281 "问题 1054281：功能请求：DevTools 应模拟可折叠和双屏幕设备 | Chromium bug"  
[CR1075865]: https://crbug.com/1075865 "问题 1075865：在 devtools 日程表中显示丢弃的帧 | Chromium bug"  
[CR1093229]: https://crbug.com/1093229 "问题 1093229：DevTools：提供专用的字样编辑器 UI | Chromium bug"  
[CR1121900]: https://crbug.com/1121900 "问题 1121900：DevTools：根据新规范更新对比度计算逻辑 | Chromium bug"  
[CR1122507]: https://crbug.com/1122507 "问题 1122507：帧树视图中的 Surface 工作线程信息 | Chromium bug"  
[CR1122580]: https://crbug.com/1122580 "问题 1122580：重载时无法禁用网络记录 | Chromium bug"  
[CR1136394]: https://crbug.com/1136394 "问题 1136394：弹性框工具 |Chromium bug"  
[CR1139899]: https://crbug.com/1139899 "问题 1139899：在帧详细信息视图中报告封闭的 API 的可用性 | Chromium bug"  
[CR1139949]: https://crbug.com/1139949 "问题 1139949：弹性框覆盖 | Chromium bug"  
[CR1147016]: https://crbug.com/1147016 "问题 1147016：颜色选取器未显示在 var() 函数中。| Chromium bug"  
[CR1148353]: https://crbug.com/1148353 "问题 1148353：功能请求：从 devtools 控制台复制对象 | Chromium bug"  
[CR1149859]: https://crbug.com/1149859 "问题 1149859：[功能请求][控制台] 将复制对象添加到剪贴板项目以及上下文菜单 | Chromium bug"  
[CR1150797]: https://crbug.com/1150797 "问题 1150797：在“元素”面板中添加“复制元素”上下文菜单 | Chromium bug"  
[CR1152391]: https://crbug.com/1152391 "问题 1152391：支持“样式”面板中的“复制 CSS”上下文菜单 | Chromium bug"  
[CR1155120]: https://crbug.com/1155120 "问题 1155120：[FR]支持复制文件名和行号 | Chromium bug"  
[CR1156628]: https://crbug.com/1156628 "问题 1156628：DevTools：在强制元素状态功能中添加对 :target 的支持 | Chromium bug"  
[CR1157329]: https://crbug.com/1157329 "问题 1157329：辅助功能 - 讲述人：讲述人不会在“样式”选项卡中公布适用于代码的建议的计数和位置 | Chromium bug"  

[MdnDocsWebCssTarget]: https://developer.mozilla.org/docs/web/css/:target ":target | MDN"  

[SamsungUsMobileGalaxyFold]: https://www.samsung.com/us/mobile/galaxy-fold "Galaxy Fold | Samsung US"  

[W3cWaiWcag21QuickrefContrastEnhanced]: https://www.w3.org/WAI/WCAG21/quickref#contrast-enhanced "对比度（增强）- 如何满足 WCAG 的要求（快速参考）|W3C"  
[W3cWaiWcag21QuickrefContrastMinimum]: https://www.w3.org/WAI/WCAG21/quickref#contrast-minimum "对比度（最低）- 如何满足 WCAG 的要求（快速参考）|W3C"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于 [此处](https://developer.chrome.com/blog/new-in-devtools-89)，并由 [Jecelyn Yeen][JecelynYeen] \（开发人员支持者，Chrome DevTools\）制作。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors#jecelyn-yeen

[SpanningPlaceholder]: link-t-b-d "跨区占位符"  
