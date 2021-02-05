---
description: 现在欢迎使用"新增功能"工具、"样式"窗格中的可视化字体编辑器、CSS Flexbox 调试工具等。
title: 'Microsoft Edge 89 (DevTools 中的新增) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/03/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: cfaee927d2d914cf0d816505ea2cf6b36a225d64
ms.sourcegitcommit: 12c30ad4ab2664d17c9b7e9d59d7a3cda60ff65c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2021
ms.locfileid: "11313135"
---
# Microsoft Edge 89 (DevTools 中的新增)   

[!INCLUDE [contact DevTools team note](../../includes/edge-whats-new-note.md)]  

## 现在欢迎使用新增功能  

<!--  Title: What's New is now Welcome  -->  
<!--  Subtitle: The What's New tool now has a new appearance and a new name:  Welcome -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

Microsoft **Edge** DevTools 中的新增功能工具现在具有新外观和新名称：  **欢迎**使用。  欢迎 **工具** 仍显示最新的 DevTools 新闻和更新。  它现在还包括指向 Microsoft Edge DevTools 文档的链接、提交反馈的方式等。  若要在 Microsoft Edge **每次更新** 后显示欢迎工具，请选中标题下每个更新后"打开"选项卡 **旁边的** 复选框。  若要关闭**欢迎**工具，请选择选项卡标题右边的**X。**  如果你更喜欢原始的新增**功能工具，** 请[导航到"][DevtoolsCustomizeIndexSettings]设置实验"并删除  >  ****"启用欢迎"**选项卡旁边的复选框**。  

:::image type="complex" source="../../media/2021/01/welcome-tool-whats-new-88.msft.png" alt-text="欢迎工具突出显示" lightbox="../../media/2021/01/welcome-tool-whats-new-88.msft.png":::
   欢迎 **工具** 突出显示  
:::image-end:::  

## "样式"窗格中的可视化字体编辑器  

<!--  Title: Visual font editor in the Styles pane  -->  
<!--  Subtitle: Visual font editor in the Styles pane -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

在 CSS 中处理字体时，请使用新的可视 [字体编辑器][DevtoolsInspectStylesEditFonts]。  你可以定义回退字体，并使用滑块定义字体粗细、大小、行高和间距。  字体 **编辑器** 可帮助您完成以下操作。  

*   在不同字体属性的单位之间切换  
*   在不同字体属性的关键字之间切换  
*   转换单位  
*   生成准确的 CSS 代码  
    
若要打开此实验，请[导航到"][DevtoolsCustomizeIndexSettings]设置实验"，并在"样式"窗格中选中"启用新  >  **** 字体编辑器工具"**旁边的复选框**。  有关详细信息，请导航到 DevTools 的"样式"窗格中的"编辑[CSS 字体样式和设置"。][DevtoolsInspectStylesEditFonts]  若要查看 Chromium 开放源代码项目中此功能的历史记录，请导航到"问题"[1093229][CR1093229]。  

:::image type="complex" source="../../media/2021/01/visual-font-editor.msft.png" alt-text="可视化字体编辑器在样式窗格中突出显示" lightbox="../../media/2021/01/visual-font-editor.msft.png":::
   可视化 **字体编辑器** 在" **样式"窗格中** 突出显示  
:::image-end:::  

## CSS Flexbox 调试工具  

Flexbox 调试功能正在积极开发中。  若要打开以下两项功能的实验，请导航到"设置[][DevtoolsCustomizeIndexSettings]实验"，并选中"启用新的 CSS 弹性框调试功能  >  ******"旁边的复选框**。  若要查看 Chromium 开放源代码项目中此功能的历史记录，请导航到"问题"[1136394][CR1136394] 和 [1139949][CR1139949]。  

### 新的 Flexbox (弹性) 图标有助于标识和显示弹性容器  

<!--  Title: Display Flexbox containers with Flexbox (flex) icon  -->  
<!--  Subtitle: New Flexbox (flex) icon in the Elements tool help you identify Flexbox containers in your code.  When toggled, the adorner displays and hides outlines of the flex container to help you debug the layout -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

在" **元素** "工具中，新的 Flexbox (flex) 图标可帮助您在代码中标识 Flexbox 容器。  Choose the Flexbox \ (flex\) icon to turn on or off the overlay effect that outlines a Flexbox container.  You may customize the color of the overlay in the **Layout** pane， which is located next to **Styles** and **Computed.**  

:::row:::
   :::column span="":::
      若要打开和关闭覆盖效果（概述了 Flexbox 容器，请选择 Flexbox \ (`flex` \) 图标。  
   :::column-end:::
   :::column span="":::
      You may customize the color of the overlay in the **Layout** pane next to **Styles** and **Computed.**  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-flex-container.msft.png" alt-text="Flexbox (弹性) 图标和网页突出显示" lightbox="../../media/2021/01/elements-flex-container.msft.png":::
         **突出显示的 Flexbox** \ (`flex` \) 图标和网页 :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-layout-flex-container.msft.png" alt-text="布局窗格中突出显示的弹性框覆盖" lightbox="../../media/2021/01/elements-layout-flex-container.msft.png":::
         "**布局"窗格中**突出显示的弹性框**覆盖**  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

### 当 Flexbox 布局使用 CSS 属性更改时显示对齐图标和网格线  

<!--  Title: Display alignment icons and gridlines for changes to Flexbox layouts from CSS properties  -->  
<!--  Subtitle:  CSS autocomplete in the Styles tool now displays icons next to Flexbox properties to help you review the effect a property has on your Flexbox layout -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

编辑 Flexbox 布局的 CSS 时，"样式"窗格中的**** CSS 自动完成现在会在相关的 Flexbox 属性旁边显示有用的图标。  若要尝试此新功能，请打开 **Elements** 工具并选择弹性容器。  然后，在"样式"窗格中添加或更改该 **容器上的** 属性。  

:::row:::
   :::column span="":::
      自动完成菜单现在显示指示对齐属性的效果的图标，如 `align-content` `align-items` 和 。  
   :::column-end:::
   :::column span="":::
      此外，DevTools 现在还显示一条指导线，帮助你更好地查看 `align-items` CSS 属性。  `gap`CSS 属性也受支持。  下图中 `gap` ，CSS 属性设置为并显示每个间隙 `gap: 12px;` 的填充模式。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-flex-container-align.msft.png" alt-text="突出显示的自动完成菜单用于以 align-" lightbox="../../media/2021/01/elements-flex-container-align.msft.png":::
         针对以 CSS 属性开始突出显示的"自动完成"菜单 `align-`  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-flex-container-align-items-center-gap-12px.msft.png" alt-text="CSS 属性和网页中的弹性框间隙突出显示" lightbox="../../media/2021/01/elements-flex-container-align-items-center-gap-12px.msft.png":::
         CSS 属性和网页中的 Flexbox `gap` 突出显示  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## 使用新的"更多工具"按钮快速添加工具  

<!--  Title: Add tools quickly with new More Tools button  -->  
<!--  Subtitle: A convenient way to open new tools in Microsoft Edge DevTools -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

现在，你具有在 Microsoft Edge DevTools 中打开更多工具的一种新方式。  打开此实验后，"更多工具****"图标 () 面板右侧显示 `+` 加号。  若要显示要添加到主面板的其他工具的列表，请选择"更多工具****"\ (\) `+` 图标。  若要打开此实验，请[导航到"][DevtoolsCustomizeIndexSettings]设置实验"，然后选择"启用 + 按钮"选项卡菜单旁边的复选框以  >  ******打开更多工具**。  

:::image type="complex" source="../../media/2021/01/more-tools.msft.png" alt-text="开发人员工具中突出显示的更多工具" lightbox="../../media/2021/01/more-tools.msft.png":::
   **开发人员工具** 中突出显示的更多工具  
:::image-end:::  

## 辅助技术现在宣布 CSS 建议的位置和计数  

<!--  Title: Assistive technologies now announce position and count of CSS suggestions  -->  
<!--  Subtitle: CSS suggestions are now easier to navigate using screen readers -->  

编辑 CSS 时，将获取功能下拉列表。  此功能不适用于辅助技术的用户，因为它在 Microsoft Edge 版本 89 中公布。  辅助技术的用户现在可以在"样式"窗格中导航 CSS**建议。**  在 Microsoft Edge 版本 88 及更早版本中，当用户在"样式"窗格中编辑 CSS 时浏览建议列表时，会公布辅助 `Suggestion` 技术。 ****  在 Microsoft Edge 版本 89 中，辅助技术的用户现在会听到当前建议的位置和计数。  每个建议在用户浏览建议列表时进行公布，如建议 3/5。  若要了解有关在 DevTools 中编写 CSS 的更多信息，请导航到["更改 CSS"。][DevtoolsCssReferenceChangeCss]  若要查看 Chromium 开放源代码项目中此功能的历史记录，请导航到"问题"[1157329][CR1157329]。  

<!--To view a video that displays and reads aloud several suggestions with this experiment turned on, navigate to [Voiceover announcing devtools options](https://youtu.be/9TcUpleEwwA) on YouTube.  -->  

打开此实验后，以下视频链接将显示并朗读多个建议。  

> [!VIDEO https://youtu.be/9TcUpleEwwA]  

## 模拟 Surface Duo 和 Samsung 一起折叠  

<!--  Title: Emulate new dual-screen and foldable devices  -->  
<!--  Subtitle: Test the appearance and feel of your website or app with Surface Duo and Samsung Galaxy Fold emulators -->  

在 Microsoft Edge 中的以下设备上测试网站或应用的外观。  

*   [Surface Duo][MicrosoftSurfaceDevicesSurfaceDuo]  
*   [三星百合][SamsungUsMobileGalaxyFold]  
    
打开**实验性 Web 平台功能**以访问新的[CSS 媒体][DualScreenWebCssMediaSpanning]屏幕跨越功能和[getWindowSegments JavaScript API。][DualScreenWebJavascriptGetwindowsegments]  导航到 `edge://flags` 实验性 Web 平台功能旁边的**标志并切换。**  为了帮助增强适用于双屏和可折叠设备的网站或应用，在模拟设备时使用以下 [功能][DevtoolsDeviceModeIndex]。  

*   [跨越，][DevtoolsDeviceModeDualScreenFoldablesTestingFoldableDualScreenDevices]即你的网站 \ (或 app\) 跨两个屏幕显示。  
*   [呈现接][DualScreenIntroductionHowToWorkWithSeam]层，这是两个屏幕之间的空间。  
    
若要查看 Chromium 开放源代码项目中此功能的历史记录，请导航到"问题"[1054281][CR1054281]。  

:::image type="complex" source="../../media/2021/01/emulate-surface-device-surface-duo.msft.png" alt-text="模拟双屏幕" lightbox="../../media/2021/01/emulate-surface-device-surface-duo.msft.png":::
   模拟双屏幕  
:::image-end:::  

## Microsoft Edge 开发人员工具Visual Studio 1.1.2 版  

Microsoft [Edge 开发人员][VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools] 工具 Visual Studio Code extension version 1.1.2 for Microsoft Visual Studio Code has the following changes since the previous release.  Microsoft Visual Studio 代码会自动更新扩展。  若要手动更新到版本 1.1.2，请导航到 [手动更新扩展][VisualstudioCodeDocsEditorExtensionGalleryUpdateExtensionManually]。  

*   向目标 **列表 \ (** #248 [\) ][GithubMicrosoftVscodeEdgeDevtoolsPull248]上的每个项目添加了"关闭实例"按钮  
*   从[][DevtoolsMain]84.0.522.63 到[85.0.564.40][DevtoolsWhatsNew85] \ (#235 [\) ][GithubMicrosoftVscodeEdgeDevtoolsPull235]  
*   将[Microsoft Edge 调试][VisualstudioMarketplaceMsjsdiagDebuggerMicrosoftEdge]器作为依赖项 \ (#233 \) [][GithubMicrosoftVscodeEdgeDevtoolsPull233]  
*   实现的用于更改扩展主题 \ (#229 [\) ][GithubMicrosoftVscodeEdgeDevtoolsPull229]  
    
你可以提交问题并参与 [vscode-edge-devtools GitHub 存储库上的扩展][GithubMicrosoftVscodeEdgeDevtools]。  

## 来自 Chromium 项目的公告  

[!INCLUDE [contact DevTools team note](../../includes/chromium-whats-new-note.md)]  

### 捕获视图之外的节点屏幕截图  

在 Microsoft Edge 版本 89 中，节点屏幕截图更加准确，即使节点中的内容在视口中不可见，也捕获整个节点。  在元素 **工具** 中，将鼠标悬停在某个元素上，打开上下文菜单 \ (右键单击\) ，然后选择"捕获 **"节点屏幕截图**。  若要查看 Chromium 开放源代码项目中此功能的历史记录，请导航到"问题"[1003629][CR1003629]。  

:::image type="complex" source="../../media/2021/01/capture-node-screenshot.msft.png" alt-text="在元素工具的上下文菜单上突出显示的捕获节点屏幕截图" lightbox="../../media/2021/01/capture-node-screenshot.msft.png":::
   **在元素工具** 的上下文菜单上突出显示 **的捕获节点** 屏幕截图  
:::image-end:::  

### 元素工具更新  

#### 支持强制使用 ：target CSS 状态  

你现在可以使用 DevTools 强制使用 [：target][MdnDocsWebCssTarget] CSS 伪类。  当唯一元素 \ (\) 具有与 URL 片段匹配的元素时，将触发伪 `:target` `id` 类。  例如 `http://www.example.com/index.html#section1` ，URL 将触发 HTML 元素 `:target` 上的伪类 `id="section1"` 。  若要尝试突出显示第 1 节的演示，请导航到 [CSS ：target 演示][GithubMicrosoftedgeDevtoolssamplesWhatsNew89TargetCssDemoHtmlSection1]。  若要查看 Chromium 开放源代码项目中此功能的历史记录，请导航到"问题"[1156628][CR1156628]。  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-styles-none-forced.msft.png" alt-text="突出显示的网页没有强制 CSS" lightbox="../../media/2021/01/elements-styles-none-forced.msft.png":::
         未强制 CSS 突出显示的网页  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-styles-target-forced.msft.png" alt-text="：target CSS 强制和网页突出显示" lightbox="../../media/2021/01/elements-styles-target-forced.msft.png":::
         `:target` CSS 强制和网页突出显示  
      :::image-end:::  
   :::column-end:::
:::row-end:::

#### 使用重复元素复制元素  

使用新的 **Duplicate 元素** 快捷方式克隆元素。  在元素 **工具** 中，将鼠标悬停在元素上，打开上下文菜单 \ (右键单击\) ，选择 **Duplicate 元素**。  在所选元素下创建一个新元素。  若要使用键盘快捷方式复制元素，请选择 `Shift` + `Alt` + `Down Arrow` \ (Windows/Linux\) 或 `Shift` + `Option` + `Down Arrow` \ (macOS\) 。  若要查看 Chromium 开放源代码项目中此功能的历史记录，请导航到"问题"[1150797][CR1150797]。  

:::image type="complex" source="../../media/2021/01/elements-duplicate-element.msft.png" alt-text="Duplicate 元素在元素工具中某个元素的上下文菜单中突出显示" lightbox="../../media/2021/01/elements-duplicate-element.msft.png":::
   Duplicate**元素**在"元素"工具中某个元素的**上下文菜单中突出显示**  
:::image-end:::  

#### 自定义 CSS 属性的颜色选取器  

" **样式"** 窗格现在显示自定义 CSS 属性的颜色选取器。  若要循环访问颜色值的 RGBA、HSLA 和 Hex 格式，请按住并选择 `Shift` 颜色选取器。  若要查看 Chromium 开放源代码项目中此功能的历史记录，请导航到"问题"[1147016][CR1147016]。  

:::image type="complex" source="../../media/2021/01/elements-styles-change-color-format.msft.png" alt-text="自定义 CSS 属性的颜色选取器" lightbox="../../media/2021/01/elements-styles-change-color-format.msft.png":::
   自定义 CSS 属性的颜色选取器  
:::image-end:::  

#### 复制 CSS 类和属性  

现在，可以使用上下文菜单中的一些新选项更快地复制 CSS 属性。  在" **元素** "工具中，选择一个元素。  若要复制该值，请在 **"** 样式"窗格中将鼠标悬停在 CSS 类或 CSS 属性上，打开上下文菜单 \ (右键单击\) ，然后选择复制选项。  

:::row:::
   :::column span="":::
      复制 CSS 类的选项。  
      
      | 选项 | 详细信息 |  
      |:--- |:--- |  
      | **复制选择器** | 复制当前选择器名称。 |  
      | **复制规则** | 复制当前选择器的规则。 |  
      | **复制所有声明** | 复制当前规则下的所有声明，包括无效和前缀属性。 |  
   :::column-end:::
   :::column span="":::
      复制 CSS 属性的选项。  
      
      | 选项 | 详细信息 |      
      |:--- |:--- |  
      | **复制声明** | 复制当前行的声明。 |  
      | **Copy 属性** | 复制当前行的属性。 |  
      | **复制值** | 复制当前行的值。 |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/copy-css-class.msft.png" alt-text="在上下文菜单中复制 CSS 类的选项" lightbox="../../media/2021/01/copy-css-class.msft.png":::
         在上下文菜单中复制 CSS 类的选项  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/copy-css-property-cropped.msft.png" alt-text="在上下文菜单中复制 CSS 属性的选项" lightbox="../../media/2021/01/copy-css-property.msft.png":::
         在上下文菜单中复制 CSS 属性的选项  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

若要查看 Chromium 开放源代码项目中此功能的历史记录，请导航到"问题"[1152391][CR1152391]。  

### Cookie 更新  

#### 显示 URL 解码 Cookie 的新选项  

现在，你可以选择在 Cookie 窗格中显示 URL 解码的 **Cookie** 值。  若要显示解码的 Cookie，请导航**到应用程序**Cookie 窗格，选择列表上的任何 Cookie，然后选择"显示  >  **** 已解码**的 URL"旁边的复选框**。  若要查看 Chromium 开放源代码项目中此功能的历史记录，请导航到"问题"[997625][CR997625]。  

:::image type="complex" source="../../media/2021/01/application-cookies-show-url-decoded.msft.png" alt-text="显示 URL 解码 Cookie 的选项" lightbox="../../media/2021/01/application-cookies-show-url-decoded.msft.png":::
   用于显示 URL 解码 Cookie 的选项  
:::image-end:::  

#### 筛选和清除可见的 Cookie  

在 Microsoft Edge 版本 88**** 或更早版本中，应用程序工具仅提供一种使用"清除所有 Cookie"按钮清除所有**Cookie**的方法。  在 Microsoft Edge 版本 89 中，你现在可以选择"清除筛选的 **Cookie"，** 以仅删除筛选的 Cookie。  若要筛选 Cookie，请导航到 **"应用程序**  >  **Cookie"，** 并在 **"筛选器**"文本框中键入。  若要删除显示的 Cookie，请选择" **清除筛选的 Cookie"** 按钮。  若要显示所有其他 Cookie，请清除筛选器文本。  若要查看 Chromium 开放源代码项目中此功能的历史记录，请导航到"问题"[978059][CR978059]。  

:::image type="complex" source="../../media/2021/01/application-cookies-clear-filtered-cookies.msft.png" alt-text="仅清除可见的 Cookie" lightbox="../../media/2021/01/application-cookies-clear-filtered-cookies.msft.png":::
   仅清除可见的 Cookie  
:::image-end:::  

#### 在存储窗格中清除第三方 Cookie 的新选项  

默认情况下，DevTools 现在仅清除第一方 Cookie。  若要仅清除网站数据和第一方 Cookie，请导航到 **"应用程序**存储"，  >  **** 然后选择"**清除网站数据"。**  

若要清除网站数据和所有 Cookie，请导航到**应用程序**  >  **存储**。  选中包含第三方**Cookie 旁边的**复选框，然后选择"**清除网站数据"。**  

若要查看 Chromium 开放源代码项目中此功能的历史记录，请导航到"问题"[1012337][CR1012337]。  

:::image type="complex" source="../../media/2021/01/application-storage-clear-site-data-including-third-party-cookies.msft.png" alt-text="清除第三方 Cookie 的选项" lightbox="../../media/2021/01/application-storage-clear-site-data-including-third-party-cookies.msft.png":::
   清除第三方 Cookie 的选项  
:::image-end:::  

### 网络工具更新  

#### 持久记录网络日志设置  

在 Microsoft Edge 版本 88 或更早版本中，DevTools 在网页刷新时重置记录网络日志设置。 ****  在 Microsoft Edge 版本 89 中，DevTools 现在保留 **记录网络日志** 设置。  若要查看 Chromium 开放源代码项目中此功能的历史记录，请导航到"问题"[1122580][CR1122580]。  

:::image type="complex" source="../../media/2021/01/network-log.msft.png" alt-text="记录网络日志" lightbox="../../media/2021/01/network-log.msft.png":::
   记录网络日志  
:::image-end:::  

#### 联机选项现在无限制选项  

网络仿真选项**Online**现已重命名为"无**限制"。**  若要查看 Chromium 开放源代码项目中此功能的历史记录，请导航到"问题"[1028078][CR1028078]。  

:::image type="complex" source="../../media/2021/01/network-no-throttling.msft.png" alt-text="无限制选项" lightbox="../../media/2021/01/network-no-throttling.msft.png":::
   **无限制** 选项  
:::image-end:::  

### 控制台工具、源工具和样式窗格中的新副本选项

#### 复制控制台和源工具中的对象  

现在可以在控制台和源工具 **中** 复制 **对象** 值。  使用大型对象时，复制对象值的能力非常有用。  若要查看 Chromium 开源项目中此功能的历史记录，请导航到"问题"[1148353][CR1148353] 和 [1149859][CR1149859]。  

:::row:::
   :::column span="":::
      在 **控制台工具** 中，将鼠标悬停在对象上，打开上下文菜单 \ (右键单击\) ，然后选择复制 **对象**。  
   :::column-end:::
   :::column span="":::
      在源**** 工具的断点上，将鼠标悬停在对象上，在对象**** 弹出窗口中突出显示对象，打开上下文菜单 \ (右键单击\) ，然后选择复制**对象**。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/console-copy-object.msft.png" alt-text="在控制台中复制对象" lightbox="../../media/2021/01/console-copy-object.msft.png":::
         在控制台中复制 **对象**  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/sources-breakpoint-object-copy-object.msft.png" alt-text="在源中复制对象" lightbox="../../media/2021/01/sources-breakpoint-object-copy-object.msft.png":::
         在源中复制 **对象**  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

#### 在"源"工具和"样式"窗格中复制文件名  

现在，可以使用上下文菜单复制文件名。  若要查看 Chromium 开放源代码项目中此功能的历史记录，请导航到"问题"[1155120][CR1155120]。  

:::row:::
   :::column span="":::
      在源**工具**中，将鼠标悬停在文件名上，打开上下文菜单 \ (右键单击\) ，然后选择"复制**文件名"。**  
   :::column-end:::
   :::column span="":::
      在"**样式**>中，将鼠标**** 悬停在文件名上，打开上下文菜单 \ (右键单击\) ，然后选择"复制**文件名"。**  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/sources-copy-file-name.msft.png" alt-text="复制源中的文件名" lightbox="../../media/2021/01/sources-copy-file-name.msft.png":::
         复制源中的 **文件名**  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-styles-copy-file-name.msft.png" alt-text="在样式窗格中复制文件名" lightbox="../../media/2021/01/elements-styles-copy-file-name.msft.png":::
         在"样式"窗格中 **复制** 文件名  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

### 帧详细信息更新  

#### 框架详细信息中的服务工作者信息  

DevTools 现在在父框架下列出一个专用服务工作者。  下图显示了服务工作者的详细信息。  若要显示服务工作者的详细信息，请导航到 **"应用程序**  >  **框架**  >  `top`  >  **服务**工作者"，然后选择一个服务工作者。  若要查看 Chromium 开放源代码项目中此功能的历史记录，请导航到"问题"[1122507][CR1122507]。  

:::image type="complex" source="../../media/2021/01/application-frames-service-workers-details.msft.png" alt-text="框架详细信息中的服务工作者信息" lightbox="../../media/2021/01/application-frames-service-workers-details.msft.png":::
   **框架** 详细信息中的 **服务工作者** 信息  
:::image-end:::  

#### 在帧详细信息中测量内存信息  

API `performance.measureMemory()` 状态现在显示在 **API** 可用性部分下。  新 `performance.measureMemory()` API 估计整个网页的内存使用率。  若要查看 Chromium 开放源代码项目中此功能的历史记录，请导航到"问题"[1139899][CR1139899]。  

:::image type="complex" source="../../media/2021/01/application-frames-measure-memory.msft.png" alt-text="测量内存" lightbox="../../media/2021/01/application-frames-measure-memory.msft.png":::
   测量内存  
:::image-end:::  

### 性能工具中丢弃的帧  

在性能 [工具中分析负载性能时，"][DevtoolsEvaluatePerformanceReferenceRecordLoadPerformance]框架 **"部分现在** 将丢弃的帧标记为红色。  若要显示帧速率，请将鼠标悬停在丢弃的帧上。  若要查看 Chromium 开放源代码项目中此功能的历史记录，请导航到"问题"[1075865][CR1075865]。  

:::image type="complex" source="../../media/2021/01/performance-frames-dropped-frames-red.msft.png" alt-text="丢弃的帧" lightbox="../../media/2021/01/performance-frames-dropped-frames-red.msft.png":::
   丢弃的帧  
:::image-end:::  

#### 新的颜色对比度计算 - APCA (高级感知对比度)   

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

APCA 高级感知对比度[算法 (APCA) ][GithubW3cSilverGuidelinesMethodsMethodFontCharacteristicContrastHtml]替换了颜色选取器中的[AA][W3cWaiWcag21QuickrefContrastMinimum] / [AAA][W3cWaiWcag21QuickrefContrastEnhanced]指南[对比率][DevtoolsAccessibilityReferenceViewContrastRatioTextElementColorPicker]。  APCA 是计算对比度的一种新方式。  它基于对颜色感知的新式研究。  与 AA/AAA 准则相比，APCA 更依赖于上下文。  对比度基于文本、颜色和上下文的以下空间属性计算。  

*   文本的空间属性，包括字体粗细和大小。  
*   颜色的空间属性，包括文本和背景之间的感知对比度。  
*   包含环境光、周围和预期用途的上下文的空间属性。  
    
若要打开此实验，请导航到[][DevtoolsCustomizeIndexSettings]"设置实验"，并选中"启用新的高级感知对比度算法 (APCA) 替换以前的对比度比率  >  ******和 AA/AAA 指南"旁边的复选框**。  若要查看 Chromium 开放源代码项目中此功能的历史记录，请导航到"问题"[1121900][CR1121900]。  

:::image type="complex" source="../../media/2021/01/advanced-perceptual-contrast-algorithm.msft.png" alt-text="颜色选取器中的 APCA" lightbox="../../media/2021/01/advanced-perceptual-contrast-algorithm.msft.png":::
   颜色选取器中的 APCA  
:::image-end:::  

## 下载 Microsoft Edge 预览频道  

如果你使用的是 Windows、Linux 或 macOS，请考虑使用 [Microsoft Edge][MicrosoftEdgePreviewChannels] 预览频道作为默认开发浏览器。  预览频道使你能够访问最新的 DevTools 功能。  

## 联系 Microsoft Edge DevTools 团队  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]

<!-- links -->  

[DevtoolsWhatsNew85]: ../../2020/06/devtools.md "Microsoft Edge 85 (DevTools 中的新增) |Microsoft Docs"  

[DevtoolsAccessibilityReferenceViewContrastRatioTextElementColorPicker]: /microsoft-edge/devtools-guide-chromium/accessibility/reference#view-the-contrast-ratio-of-a-text-element-in-the-color-picker "查看颜色选取器中的文本元素的对比度 - 辅助功能参考|Microsoft Docs"  
[DevtoolsCssReferenceChangeCss]: /microsoft-edge/devtools-guide-chromium/css/reference#change-css "更改 CSS - CSS |Microsoft Docs"  
[DevtoolsCustomizeIndexSettings]: /microsoft-edge/devtools-guide-chromium/customize/index#settings "设置 - 自定义 Microsoft Edge DevTools | Microsoft Docs"  
[DevtoolsCustomizeShortcuts]: microsoft-edge/devtools-guide-chromium/customize/shortcuts "自定义 Microsoft Edge DevTools |Microsoft Docs"  
[DevtoolsDeviceModeDualScreenFoldablesTestingFoldableDualScreenDevices]: /microsoft-edge/devtools-guide-chromium/device-mode/dual-screen-and-foldables#testing-on-foldable-and-dual-screen-devices "在可折叠和双屏幕设备上进行测试 - 模拟 Microsoft Edge DevTools |Microsoft Docs"  
[DevtoolsDeviceModeIndex]: /microsoft-edge/devtools-guide-chromium/device-mode/index "在 Microsoft Edge DevTools 中模拟移动设备 | Microsoft Docs"  
[DevtoolsDeviceModeIndexSimulateMobileViewport]: /microsoft-edge/devtools-guide-chromium/device-mode/index#simulate-a-mobile-viewport "模拟移动视口 - 模拟 Microsoft Edge DevTools |Microsoft Docs"  
[DevtoolsEvaluatePerformanceReferenceRecordLoadPerformance]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference#record-load-performance "记录负载性能 - 性能分析|Microsoft Docs"  
[DevtoolsInspectStylesEditFonts]: /microsoft-edge/devtools-guide-chromium/inspect-styles/edit-fonts "在 DevTools | 中的"样式"窗格中编辑 CSS 字体样式和|Microsoft Docs"  
[DevtoolsMain]: /microsoft-edge/devtools-guide-chromium/index "Microsoft Edge (Chromium) 开发人员工具概述|Microsoft Docs"  

[DualScreenIntroductionHowToWorkWithSeam]: /dual-screen/introduction#how-to-work-with-the-seam "如何使用设备 - 双屏幕设备简介|Microsoft Docs"  
[DualScreenWebCssMediaSpanning]: /dual-screen/web/css-media-spanning "用于双屏检测方法的 CSS 媒体屏幕|Microsoft Docs"  
[DualScreenWebJavascriptGetwindowsegments]: /dual-screen/web/javascript-getwindowsegments "适用于双屏幕设备的 getWindowSegments JavaScript API |Microsoft Docs"  

[GithubMicrosoftedgeDevtoolssamplesWhatsNew89TargetCssDemoHtmlSection1]: https://microsoftedge.github.io/DevToolsSamples/whats-new/89/target-css-demo.html#section-1 "第 1 部分 - 适用于 Microsoft Edge 89 (开发工具中的新增功能的目标) |GitHub"  
[GithubMicrosoftVscodeEdgeDevtools]: https://github.com/microsoft/vscode-edge-devtools "microsoft/vscode-edge-devtools |GitHub"  
[GithubMicrosoftVscodeEdgeDevtoolsPull229]: https://github.com/microsoft/vscode-edge-devtools/pull/229 "拉 229：在设置中实现下拉列表以更改主题|GitHub"  
[GithubMicrosoftVscodeEdgeDevtoolsPull233]: https://github.com/microsoft/vscode-edge-devtools/pull/233 "拉取 233：将适用于 Microsoft Edge 的调试器作为依赖项|GitHub"  
[GithubMicrosoftVscodeEdgeDevtoolsPull235]: https://github.com/microsoft/vscode-edge-devtools/pull/235 "拉取 235：将 Edge DevTools 版本升级到 85.0.564.40 |GitHub"  
[GithubMicrosoftVscodeEdgeDevtoolsPull248]: https://github.com/microsoft/vscode-edge-devtools/pull/248 "拉 248：将单个关闭按钮添加到实例面板|GitHub"  
[GithubW3cSilverGuidelinesMethodsMethodFontCharacteristicContrastHtml]: https://w3c.github.io/silver/guidelines/methods/Method-font-characteristic-contrast.html "选择字体特征和背景颜色以提供足够的对比度，以便可读性|W3C"  
[GithubW3cWebappsecTrustedTypesDistSpec]: https://w3c.github.io/webappsec-trusted-types/dist/spec  "受信任类型|W3C"  

[MicrosoftSurfaceDevicesSurfaceDuo]: https://www.microsoft.com/surface/devices/surface-duo "新的 Surface Duo |Microsoft"  

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download "Microsoft Edge 预览频道"  

[VisualstudioCodeDocsEditorExtensionGalleryUpdateExtensionManually]: https://code.visualstudio.com/docs/editor/extension-gallery#_update-an-extension-manually "手动更新扩展 - 扩展市场|Visual Studio代码"  

[VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools]: https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools "Microsoft Edge Tools for Visual Studio Code |Visual Studio市场"  
[VisualstudioMarketplaceMsjsdiagDebuggerMicrosoftEdge]: https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge "适用于 Microsoft Edge |Visual Studio市场"  

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium 漏洞"  

<!--[CR174309]: https://crbug.com/174309 "Issue 174309: DevTools: Allow to customize keyboard shortcuts/key bindings | Chromium bugs"  -->  
<!--[CR772558]: https://crbug.com/772558 "Issue 772558: DevTools: Update to latest version of Lighthouse | Chromium bugs"  -->  
[CR978059]："问题 978059：在筛选 Cookie 时删除它们，删除所有 Cookie，而不只是删除已筛选| https://crbug.com/978059 Chromium bug"  
[CR997625]：" https://crbug.com/997625 问题 997625：新功能|需要查看 Cookie 中 url 解码值的选项|Chromium bug"  
[CR1003629]："问题 https://crbug.com/1003629 1003629：捕获节点不再屏幕截图折叠下方节点。 |Chromium bug"  
[CR1012337]："问题 https://crbug.com/1012337 1012337：清除网站数据会破坏非 Google 网站上 Google 会话|Chromium bug"  
[CR1028078]："问题 https://crbug.com/1028078 1028078：联机和脱机在列表中彼此|Chromium bug"  
[CR1054281]：" https://crbug.com/1054281 问题 1054281：功能请求：DevTools 应模拟可折叠和双屏幕设备|Chromium bug"  
<!--[CR1073909]: https://crbug.com/1073909 "Issue 1073909: BLOCKED | Chromium bugs"  -->  
[CR1075865]：" https://crbug.com/1075865 问题 1075865：在 devtools 时间线中显示丢弃|Chromium bug"  
[CR1093229]：" https://crbug.com/1093229 问题 1093229：DevTools：提供专用的字样编辑器 UI |Chromium bug"  
[CR1121900]：" https://crbug.com/1121900 问题 1121900：DevTools：根据新规范更新对比度计算|Chromium bug"  
[CR1122507]：" https://crbug.com/1122507 问题 1122507：帧树视图中的 Surface 工作|Chromium bug"  
[CR1122580]：" https://crbug.com/1122580 问题 1122580：无法禁用重新加载时的网络|Chromium bug"  
<!--[CR1126824]: https://crbug.com/1126824 "Issue 1126824: ☂ Support Trust Token debugging in DevTools | Chromium bugs"  -->  
[CR1136394]：" https://crbug.com/1136394 问题 1136394：Flexbox 工具|Chromium bug"  
<!--[CR1137837]: https://crbug.com/1137837 "Issue 1137837: ☂ Improve Trusted Types support in DevTools | Chromium bugs"  -->  
[CR1139899]：" https://crbug.com/1139899 问题 1139899：报告帧详细信息视图中的 API |Chromium bug"  
[CR1139949]：" https://crbug.com/1139949 问题 1139949：Flexbox 覆盖|Chromium bug"  
<!--[CR1142804]: https://crbug.com/1142804 "Issue 1142804: Implement break-on-trusted-type-violation | Chromium bugs"  -->  
<!--[CR1144127]: https://crbug.com/1144127 "Issue 1144127: BLOCKED | Chromium bugs"  -->  
[CR1147016]：" https://crbug.com/1147016 问题 1147016：颜色选取器不显示在 var () 函数中。 |Chromium bug"  
[CR1148353]：" https://crbug.com/1148353 问题 1148353：功能请求：从 devtools 控制台文件复制|Chromium bug"  
[CR1149859]：" https://crbug.com/1149859 问题 1149859： [功能请求][控制台] 将复制对象添加到剪贴板项目到上下文菜单|Chromium bug"  
[CR1150797]：" https://crbug.com/1150797 问题 1150797：在元素面板菜单中添加重复元素上下文|Chromium bug"  
<!--[CR1150883]: https://crbug.com/1150883 "Issue 1150883: Remove TT messages from the console but keep underlining in the sources tab | Chromium bugs"  -->  
<!--[CR1152290]: https://crbug.com/1152290 "Issue 1152290: Devtools support for QuicTransport | Chromium bugs"  -->  
[CR1152391]：" https://crbug.com/1152391 问题 1152391：支持在样式面板中复制 CSS 上下文|Chromium bug"  
[CR1155120]：" https://crbug.com/1155120 问题 1155120：[FR]支持复制文件名和行号|Chromium bug"  
[CR1156628]：" https://crbug.com/1156628 问题 1156628：DevTools：添加对 ：target in force 元素状态功能|Chromium bug"  
[CR1157329]："问题 1157329：辅助功能 - 讲述人：讲述人未在"样式"选项卡中公布适用于代码的建议的计数 https://crbug.com/1157329 和|Chromium bug"  

[MdnDocsWebCssTarget]: https://developer.mozilla.org/docs/web/css/:target "：target |MDN"  

[SamsungUsMobileGalaxyFold]: https://www.samsung.com/us/mobile/galaxy-fold "百年百|美国三星"  

[W3cWaiWcag21QuickrefContrastEnhanced]: https://www.w3.org/WAI/WCAG21/quickref#contrast-enhanced "对比度 (增强) - 如何满足 WCAG (快速参考) |W3C"  
[W3cWaiWcag21QuickrefContrastMinimum]: https://www.w3.org/WAI/WCAG21/quickref#contrast-minimum "对比度 (最小) - 如何满足 WCAG (快速参考) |W3C"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于 [此处](https://developers.google.com/web/updates/2021/01/devtools/index)，并由 [Jecelyn Yeen][JecelynYeen] \（开发人员支持者，Chrome DevTools\）制作。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen

[SpanningPlaceholder]: link-t-b-d "跨域占位符"  
