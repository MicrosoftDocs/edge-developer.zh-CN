---
description: 现在欢迎使用新增功能工具、样式窗格中的可视化字体编辑器、CSS Flexbox 调试工具等。
title: 'Microsoft Edge 89 (DevTools 中的新增) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: 2722da0093b3ba6521b5190e61bb208e02a2041e
ms.sourcegitcommit: e29cd1c393fc1f433dba8c3d8f260b425ade63a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/13/2021
ms.locfileid: "11408337"
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
# <a name="whats-new-in-devtools-microsoft-edge-89"></a>Microsoft Edge 89 开发人员工具中的 (新增)   

[!INCLUDE [contact DevTools team note](../../includes/edge-whats-new-note.md)]  

## <a name="whats-new-is-now-welcome"></a>新增功能现已欢迎使用  

<!--  Title: What's New is now Welcome  -->  
<!--  Subtitle: The What's New tool now has a new appearance and a new name:  Welcome -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

Microsoft **Edge** DevTools 中的新增功能工具现在具有新外观和新名称：  **欢迎**使用。  欢迎 **工具** 仍显示最新的 DevTools 新闻和更新。  它现在还包括指向 Microsoft Edge DevTools 文档的链接、提交反馈的方式等。  若要在 **Microsoft** Edge 每次更新后显示欢迎工具，请选中标题下每个更新后打开选项卡 **旁边的** 复选框。  若要关闭**欢迎工具**，请选择选项卡标题右边的**X。**  如果你更喜欢原始的**新增**功能工具，请导航到设置实验[][DevtoolsCustomizeIndexSettings]并删除"  >  **** 启用欢迎"选项卡旁边的**复选框**。  

:::image type="complex" source="../../media/2021/01/welcome-tool-whats-new-88.msft.png" alt-text="突出显示"欢迎"工具" lightbox="../../media/2021/01/welcome-tool-whats-new-88.msft.png":::
   突出显示 **"欢迎** "工具  
:::image-end:::  

## <a name="visual-font-editor-in-the-styles-pane"></a>"样式"窗格中的可视化字体编辑器  

<!--  Title: Visual font editor in the Styles pane  -->  
<!--  Subtitle: Visual font editor in the Styles pane -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

在 CSS 中处理字体时，请使用新的可视化 [字体编辑器][DevtoolsInspectStylesEditFonts]。  你可以定义回退字体，并使用滑块定义字体粗细、大小、行高和间距。  字体 **编辑器** 可帮助您完成以下操作。  

*   在不同字体属性的单位之间切换  
*   在不同字体属性的关键字之间切换  
*   转换单位  
*   生成准确的 CSS 代码  
    
若要打开此实验，请[导航到"][DevtoolsCustomizeIndexSettings]设置实验"，然后选择"在样式窗格中启用新的  >  ******字体编辑器工具"旁边的复选框**。  有关详细信息，请导航到DevTools 的样式窗格中的编辑 [CSS 字体样式和设置][DevtoolsInspectStylesEditFonts]。  若要查看 Chromium 开源项目中此功能的历史记录，请导航到"问题[1093229"。][CR1093229]  

:::image type="complex" source="../../media/2021/01/visual-font-editor.msft.png" alt-text="可视字体编辑器在"样式"窗格中突出显示" lightbox="../../media/2021/01/visual-font-editor.msft.png":::
   可视**字体编辑器**在"样式 **"窗格中突出显示**  
:::image-end:::  

## <a name="css-flexbox-debugging-tools"></a>CSS Flexbox 调试工具  

Flexbox 调试功能正在积极开发中。  若要打开以下两项功能的实验，请导航到"设置[][DevtoolsCustomizeIndexSettings]实验"，然后选中"启用新的  >  ******CSS Flexbox 调试功能"旁边的复选框**。  若要查看 Chromium 开源项目中此功能的历史记录，请导航到"问题[1136394"][CR1136394]和["1139949"。][CR1139949]  

### <a name="new-flexbox-flex-icon-helps-identify-and-display-flex-containers"></a>新的 Flexbox (弹性) 图标可帮助标识和显示弹性容器  

<!--  Title: Display Flexbox containers with Flexbox (flex) icon  -->  
<!--  Subtitle: New Flexbox (flex) icon in the Elements tool help you identify Flexbox containers in your code.  When toggled, the adorner displays and hides outlines of the flex container to help you debug the layout -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

在" **元素** "工具中，新的 Flexbox (flex) 图标可帮助你在代码中标识 Flexbox 容器。  选择 Flexbox \ (flex\) 图标可打开或关闭分级显示 Flexbox 容器的覆盖效果。  You may customize the color of the overlay in the **Layout** pane， which is next to **Styles** and **Computed**.  

:::row:::
   :::column span="":::
      若要打开和关闭覆盖层效果，该效果会大纲显示 Flexbox 容器，请选择 Flexbox \ (`flex` \) 图标。  
   :::column-end:::
   :::column span="":::
      You may customize the color of the overlay in the **Layout** pane next to **Styles** and **Computed**.  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-flex-container.msft.png" alt-text="Flexbox (弹性) 图标和网页突出显示" lightbox="../../media/2021/01/elements-flex-container.msft.png":::
         突出显示 **的 Flexbox** \ (`flex` \) 图标和网页 :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-layout-flex-container.msft.png" alt-text=""布局"窗格中突出显示的 Flexbox 覆盖" lightbox="../../media/2021/01/elements-layout-flex-container.msft.png":::
         "**布局"窗格中**突出显示的 Flexbox**覆盖**  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

### <a name="display-alignment-icons-and-gridlines-when-flexbox-layouts-change-using-css-properties"></a>当 Flexbox 布局使用 CSS 属性更改时显示对齐图标和网格线  

<!--  Title: Display alignment icons and gridlines for changes to Flexbox layouts from CSS properties  -->  
<!--  Subtitle:  CSS autocomplete in the Styles tool now displays icons next to Flexbox properties to help you review the effect a property has on your Flexbox layout -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

编辑 Flexbox 布局的 CSS 时，"样式"窗格中的**** CSS 自动完成现在会在相关的 Flexbox 属性旁边显示有用的图标。  若要试用此新功能，请打开 **"元素** "工具并选择弹性容器。  然后在"样式"窗格中添加或更改该容器 **上的** 属性。  

:::row:::
   :::column span="":::
      自动完成菜单现在显示指示对齐属性（如 和 ）的效果的 `align-content` 图标 `align-items` 。  
   :::column-end:::
   :::column span="":::
      此外，DevTools 现在还显示了一条指导线，可帮助你更好地查看 `align-items` CSS 属性。  `gap`CSS 属性也受支持。  在下图中，CSS 属性设置为 ，并显示每个间隙的 `gap` `gap: 12px;` 间隔模式。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-flex-container-align.msft.png" alt-text=""自动完成"菜单针对以 align-" lightbox="../../media/2021/01/elements-flex-container-align.msft.png":::
         "自动完成"菜单针对以 `align-`  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-flex-container-align-items-center-gap-12px.msft.png" alt-text="CSS 属性和网页中的弹性框间隙突出显示" lightbox="../../media/2021/01/elements-flex-container-align-items-center-gap-12px.msft.png":::
         CSS 属性和网页中的 Flexbox `gap` 突出显示  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

## <a name="add-tools-quickly-with-new-more-tools-button"></a>使用新的"更多工具"按钮快速添加工具  

<!--  Title: Add tools quickly with new More Tools button  -->  
<!--  Subtitle: A convenient way to open new tools in Microsoft Edge DevTools -->  

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

你现在有一种在 Microsoft Edge DevTools 中打开更多工具的新方式。  打开此实验后，"更多工具****"图标将显示为主 () 右侧 `+` 显示的加号。  若要显示要添加到主面板的其他工具的列表，请选择"更多 **工具"\ (** `+` \) 图标。  若要打开此实验，请[导航到设置][DevtoolsCustomizeIndexSettings]实验，然后选择启用 + 按钮选项卡菜单旁边的复选框以  >  ******打开更多工具**。  

:::image type="complex" source="../../media/2021/01/more-tools.msft.png" alt-text="DevTools 中突出显示的更多工具" lightbox="../../media/2021/01/more-tools.msft.png":::
   **DevTools** 中突出显示的更多工具  
:::image-end:::  

## <a name="assistive-technologies-now-announce-position-and-count-of-css-suggestions"></a>辅助技术现在宣布 CSS 建议的位置和计数  

<!--  Title: Assistive technologies now announce position and count of CSS suggestions  -->  
<!--  Subtitle: CSS suggestions are now easier to navigate using screen readers -->  

编辑 CSS 时，会获得一组功能。  此功能对辅助技术的用户不可用，因为它在 Microsoft Edge 版本 89 中公布。  辅助技术的用户现在可以在"样式"窗格中导航 CSS**建议。**  在 Microsoft Edge 版本 88 及更早版本中，当用户在"样式"窗格中编辑 CSS 时浏览建议列表时，宣布使用辅助 `Suggestion` 技术。 ****  在 Microsoft Edge 版本 89 中，辅助技术的用户现在会听到当前建议的位置和计数。  每个建议在用户浏览建议列表时进行公布，如建议 3/5。  若要了解有关在 DevTools 中编写 CSS 有关详细信息，请导航到"[更改 CSS"。][DevtoolsCssReferenceChangeCss]  若要查看 Chromium 开源项目中此功能的历史记录，请导航到"问题[1157329"。][CR1157329]  

若要查看在打开此实验时显示和朗读多个建议的视频，请导航到 ["Voiceover"，](https://youtu.be/9TcUpleEwwA) 宣布 YouTube 上的开发工具选项。  

:::image type="complex" source="../../media/2021/01/announce-css-suggestion.msft.png" alt-text=""样式"窗格中突出显示的建议" lightbox="../../media/2021/01/announce-css-suggestion.msft.png":::
   " `suggestion` 样式"窗格中 **突出显示** 的列表  
:::image-end:::  

## <a name="emulate-surface-duo-and-samsung-galaxy-fold"></a>模拟 Surface Duo 和 Samsung 为 Fold  

<!--  Title: Emulate new dual-screen and foldable devices  -->  
<!--  Subtitle: Test the appearance and feel of your website or app with Surface Duo and Samsung Galaxy Fold emulators -->  

在 Microsoft Edge 中的以下设备上测试网站或应用的外观。  

*   [Surface Duo][MicrosoftSurfaceDevicesSurfaceDuo]  
*   [三星百合][SamsungUsMobileGalaxyFold]  
    
打开实验**性 Web 平台功能**以访问新的[CSS 媒体屏幕][DualScreenWebCssMediaSpanning]跨越功能和[getWindowSegments JavaScript API。][DualScreenWebJavascriptGetwindowsegments]  导航到 `edge://flags` "实验性 Web 平台功能"旁边的 **标志并切换该标志**。  为了帮助增强用于双屏和可折叠设备的网站或应用，在模拟设备时使用以下 [功能][DevtoolsDeviceModeIndex]。  

*   [跨区][DevtoolsDeviceModeDualScreenFoldablesTestingFoldableDualScreenDevices]，即你的网站 \ (或 app\) 显示在两个屏幕上时。  
*   [呈现接层][DualScreenIntroductionHowToWorkWithSeam]，这是两个屏幕之间的空间。  
    
若要查看 Chromium 开放源代码项目中此功能的历史记录，请导航到"问题[1054281"。][CR1054281]  

:::image type="complex" source="../../media/2021/01/emulate-surface-device-surface-duo.msft.png" alt-text="模拟双屏" lightbox="../../media/2021/01/emulate-surface-device-surface-duo.msft.png":::
   模拟双屏  
:::image-end:::  

## <a name="microsoft-edge-developer-tools-for-visual-studio-code-version-112"></a>Microsoft Edge 开发人员工具Visual Studio 1.1.2 版  

Microsoft [Edge 开发人员工具 for Visual Studio Code][VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools] extension version 1.1.2 for Microsoft Visual Studio Code 自上一版本起具有以下更改。  Microsoft Visual Studio 代码将自动更新扩展。  若要手动更新到版本 1.1.2，请导航到"[手动更新扩展"。][VisualstudioCodeDocsEditorExtensionGalleryUpdateExtensionManually]  

*   向目标 **列表** \ (\#248 \) 上的每个项目添加了" [关闭][GithubMicrosoftVscodeEdgeDevtoolsPull248]实例"按钮  
*   从[][DevtoolsMain]84.0.522.63 到[85.0.564.40][DevtoolsWhatsNew85] \ (#235 [\) ][GithubMicrosoftVscodeEdgeDevtoolsPull235]  
*   将[Microsoft Edge 调试][VisualstudioMarketplaceMsjsdiagDebuggerMicrosoftEdge]器作为依赖项 \ (#233 \) [][GithubMicrosoftVscodeEdgeDevtoolsPull233]  
*   用于更改扩展主题 \ (#229 [\) ][GithubMicrosoftVscodeEdgeDevtoolsPull229]  
    
你可以提交问题并参与 [vscode-edge-devtools GitHub 存储库上的扩展][GithubMicrosoftVscodeEdgeDevtools]。  

## <a name="announcements-from-the-chromium-project"></a>来自 Chromium 项目的公告  

[!INCLUDE [contact DevTools team note](../../includes/chromium-whats-new-note.md)]  

### <a name="capture-node-screenshot-beyond-viewport"></a>捕获视图之外的节点屏幕截图  

在 Microsoft Edge 版本 89 中，节点屏幕截图更为准确，即使节点中的内容在视口中不可见，也捕获完整节点。  在"**元素**"工具中，将鼠标悬停在元素上，打开上下文菜单 \ (右键单击\) ，然后选择"捕获节点屏幕截图 **"。**  若要查看 Chromium 开放源代码项目中此功能的历史记录，请导航到"问题[1003629"。][CR1003629]  

:::image type="complex" source="../../media/2021/01/capture-node-screenshot.msft.png" alt-text="在"元素"工具的上下文菜单上突出显示的捕获节点屏幕截图" lightbox="../../media/2021/01/capture-node-screenshot.msft.png":::
   **在"元素"** 工具的上下文菜单上突出显示的捕获 **节点** 屏幕截图  
:::image-end:::  

### <a name="elements-tool-updates"></a>元素工具更新  

#### <a name="support-forcing-the-target-css-state"></a>支持强制使用 ：target CSS 状态  

你现在可以使用 DevTools 强制使用 [：target][MdnDocsWebCssTarget] CSS 伪类。  当唯一元素 \ (\) 具有与 URL 片段匹配的 时，将触发伪 `:target` `id` 类。  例如，URL 使用 触发 HTML 元素上的伪 `http://www.example.com/index.html#section1` `:target` 类 `id="section1"` 。  若要试用突出显示部分 1 的演示，请导航到 [CSS ：target demo][GithubMicrosoftedgeDevtoolssamplesWhatsNew89TargetCssDemoHtmlSection1]。  若要查看 Chromium 开放源代码项目中此功能的历史记录，请导航到"问题[1156628"。][CR1156628]  

:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-styles-none-forced.msft.png" alt-text="未强制 CSS 突出显示的网页" lightbox="../../media/2021/01/elements-styles-none-forced.msft.png":::
         未强制 CSS 突出显示的网页  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-styles-target-forced.msft.png" alt-text="：target CSS 强制和网页突出显示" lightbox="../../media/2021/01/elements-styles-target-forced.msft.png":::
         `:target` CSS 强制和网页突出显示  
      :::image-end:::  
   :::column-end:::
:::row-end:::

#### <a name="use-duplicate-elements-to-copy-elements"></a>使用 Duplicate 元素复制元素  

使用新的 **Duplicate 元素** 快捷方式可克隆元素。  在"**元素**"工具中，将鼠标悬停在元素上，打开上下文菜单 \ (右键单击\) ，选择 **"复制元素"。**  在所选元素下创建一个新元素。  若要使用键盘快捷方式复制元素，请选择 `Shift` + `Alt` + `Down Arrow` \ (Windows/Linux\) 或 `Shift` + `Option` + `Down Arrow` \ (macOS\) 。  若要查看 Chromium 开放源代码项目中此功能的历史记录，请导航到"问题[1150797"。][CR1150797]  

:::image type="complex" source="../../media/2021/01/elements-duplicate-element.msft.png" alt-text="Duplicate 元素在"元素"工具中元素的上下文菜单中突出显示" lightbox="../../media/2021/01/elements-duplicate-element.msft.png":::
   Duplicate**元素**在"元素"工具中元素的**上下文菜单中突出显示**  
:::image-end:::  

#### <a name="color-pickers-for-custom-css-properties"></a>自定义 CSS 属性的颜色选取器  

" **样式** "窗格现在显示自定义 CSS 属性的颜色选取器。  若要循环浏览颜色值的 RGBA、HSLA 和 Hex 格式，请按住并选择 `Shift` 颜色选取器。  若要查看 Chromium 开放源代码项目中此功能的历史记录，请导航到"问题[1147016"。][CR1147016]  

:::image type="complex" source="../../media/2021/01/elements-styles-change-color-format.msft.png" alt-text="自定义 CSS 属性的颜色选取器" lightbox="../../media/2021/01/elements-styles-change-color-format.msft.png":::
   自定义 CSS 属性的颜色选取器  
:::image-end:::  

#### <a name="copy-css-classes-and-properties"></a>复制 CSS 类和属性  

现在，您可以使用上下文菜单中的一些新选项更快地复制 CSS 属性。  在" **元素"** 工具中，选择一个元素。  若要复制值，请在"样式****"窗格中，将鼠标悬停在 CSS 类或 CSS 属性上，打开上下文菜单 \ (右键单击\) ，然后选择复制选项。  

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
      :::image type="complex" source="../../media/2021/01/copy-css-class.msft.png" alt-text="复制上下文菜单中 CSS 类的选项" lightbox="../../media/2021/01/copy-css-class.msft.png":::
         复制上下文菜单中 CSS 类的选项  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/copy-css-property-cropped.msft.png" alt-text="复制上下文菜单中 CSS 属性的选项" lightbox="../../media/2021/01/copy-css-property.msft.png":::
         复制上下文菜单中 CSS 属性的选项  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

若要查看 Chromium 开放源代码项目中此功能的历史记录，请导航到"问题[1152391"。][CR1152391]  

### <a name="cookies-updates"></a>Cookie 更新  

#### <a name="new-option-to-display-url-decoded-cookies"></a>显示 URL 解码 Cookie 的新选项  

现在，你可以选择在"Cookie"窗格中显示 URL 解码的 **Cookie 值** 。  若要显示解码的 Cookie，请导航**** 到"应用程序 Cookie"窗格，选择列表上的任何 Cookie，然后选择"显示  >  **** 已解码**的 URL"旁边的复选框**。  若要查看 Chromium 开放源代码项目中此功能的历史记录，请导航到"问题[997625"。][CR997625]  

:::image type="complex" source="../../media/2021/01/application-cookies-show-url-decoded.msft.png" alt-text="用于显示 URL 解码的 Cookie 的选项" lightbox="../../media/2021/01/application-cookies-show-url-decoded.msft.png":::
   用于显示 URL 解码的 Cookie 的选项  
:::image-end:::  

#### <a name="filter-and-clear-visible-cookies"></a>筛选和清除可见的 Cookie  

在 Microsoft Edge 版本 88**** 或更早版本中，应用程序工具仅提供了一种使用"清除所有 Cookie"按钮清除所有**Cookie**的方法。  在 Microsoft Edge 版本 89 中，现在可以选择"清除筛选的 **Cookie"，** 以仅删除筛选的 Cookie。  若要筛选 Cookie，请导航到 **"应用程序**  >  **Cookie"，** 并在"**筛选器**"文本框中键入 。  若要删除显示的 Cookie，请选择" **清除筛选的 Cookie"** 按钮。  若要显示所有其他 Cookie，请清除筛选器文本。  若要查看 Chromium 开放源代码项目中此功能的历史记录，请导航到"问题[978059"。][CR978059]  

:::image type="complex" source="../../media/2021/01/application-cookies-clear-filtered-cookies.msft.png" alt-text="仅清除可见的 Cookie" lightbox="../../media/2021/01/application-cookies-clear-filtered-cookies.msft.png":::
   仅清除可见的 Cookie  
:::image-end:::  

#### <a name="new-option-to-clear-third-party-cookies-in-the-storage-pane"></a>在"存储"窗格中清除第三方 Cookie 的新选项  

默认情况下，DevTools 现在仅清除第一方 Cookie。  若要仅清除网站数据和第一方 Cookie，请导航到"**应用程序**存储  >  ****"，然后选择"**清除网站数据"。**  

若要清除网站数据和所有 Cookie，请导航到"**应用程序存储**  >  **"。**  选中包含第三方**Cookie 旁边的**复选框，然后选择"清除**站点数据"。**  

若要查看 Chromium 开源项目中此功能的历史记录，请导航到"问题[1012337"。][CR1012337]  

:::image type="complex" source="../../media/2021/01/application-storage-clear-site-data-including-third-party-cookies.msft.png" alt-text="用于清除第三方 Cookie 的选项" lightbox="../../media/2021/01/application-storage-clear-site-data-including-third-party-cookies.msft.png":::
   用于清除第三方 Cookie 的选项  
:::image-end:::  

### <a name="network-tool-updates"></a>网络工具更新  

#### <a name="persist-record-network-log-setting"></a>持久记录网络日志设置  

在 Microsoft Edge 版本 88 或更早版本中，DevTools 在网页刷新 **时** 重置"记录网络日志"设置。  在 Microsoft Edge 版本 89 中，DevTools 现在保留 **"记录网络日志"** 设置。  若要查看 Chromium 开放源代码项目中此功能的历史记录，请导航到"问题[1122580"。][CR1122580]  

:::image type="complex" source="../../media/2021/01/network-log.msft.png" alt-text="记录网络日志" lightbox="../../media/2021/01/network-log.msft.png":::
   记录网络日志  
:::image-end:::  

#### <a name="online-option-is-now-no-throttling-option"></a>联机选项现在为"无限制"选项  

网络模拟选项**Online**现已重命名为"**无限制"。**  若要查看 Chromium 开放源代码项目中此功能的历史记录，请导航到"问题[1028078"。][CR1028078]  

:::image type="complex" source="../../media/2021/01/network-no-throttling.msft.png" alt-text="无限制选项" lightbox="../../media/2021/01/network-no-throttling.msft.png":::
   **无限制** 选项  
:::image-end:::  

### <a name="new-copy-options-in-the-console-tool-sources-tool-and-styles-pane"></a>控制台工具、"源"工具和"样式"窗格中的新复制选项

#### <a name="copy-object-in-the-console-and-sources-tool"></a>复制控制台和源工具中的对象  

现在，你可以复制控制台和源 **工具** 中的 **对象** 值。  复制对象值的能力在使用大型对象时很有用。  若要查看 Chromium 开放源代码项目中此功能的历史记录，请导航到"问题[1148353"][CR1148353]和["1149859"。][CR1149859]  

:::row:::
   :::column span="":::
      在 **控制台工具** 中，将鼠标悬停在对象上，打开上下文菜单 \ (右键单击\) ，然后选择复制 **对象**。  
   :::column-end:::
   :::column span="":::
      在"**** 源"工具中的断点上，将鼠标悬停在对象上的"**** 对象"弹出窗口中，突出显示一个对象，打开上下文菜单 \ (右键单击\) ，然后选择"复制对象"。 ****  
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

#### <a name="copy-file-name-in-the-sources-tool-and-styles-pane"></a>复制"源"工具和"样式"窗格中的文件名  

现在，可以使用上下文菜单复制文件名。  若要查看 Chromium 开源项目中此功能的历史记录，请导航到"问题[1155120"。][CR1155120]  

:::row:::
   :::column span="":::
      在"**源**"工具中，将鼠标悬停在文件名上，打开上下文菜单 \ (右键单击\) ，然后选择"复制**文件名"。**  
   :::column-end:::
   :::column span="":::
      在"**元素**>样式"窗格中，**** 将鼠标悬停在文件名上，打开上下文菜单 \ (右键单击\) ，然后选择"复制**文件名"。**  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/sources-copy-file-name.msft.png" alt-text="复制源中的文件名" lightbox="../../media/2021/01/sources-copy-file-name.msft.png":::
         复制源中的 **文件名**  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../../media/2021/01/elements-styles-copy-file-name.msft.png" alt-text="在"样式"窗格中复制文件名" lightbox="../../media/2021/01/elements-styles-copy-file-name.msft.png":::
         在"样式"窗格中 **复制** 文件名  
      :::image-end:::  
   :::column-end:::
:::row-end:::  

### <a name="updates-to-frame-details"></a>帧详细信息更新  

#### <a name="service-workers-information-in-frame-details"></a>框架详细信息中的服务工作人员信息  

DevTools 现在在父框架下列出专用服务工作器。  下图显示了服务工作者的详细信息。  若要显示服务工作线程的详细信息，请导航到"**应用程序**框架  >  ****  >  `top`  >  **服务**工作者"，然后选择一个服务工作线程。  若要查看 Chromium 开源项目中此功能的历史记录，请导航到"问题[1122507"。][CR1122507]  

:::image type="complex" source="../../media/2021/01/application-frames-service-workers-details.msft.png" alt-text="框架详细信息中的服务工作人员信息" lightbox="../../media/2021/01/application-frames-service-workers-details.msft.png":::
   **框架详细信息** 中的服务 **工作人员** 信息  
:::image-end:::  

#### <a name="measure-memory-information-in-frame-details"></a>在帧详细信息中测量内存信息  

API `performance.measureMemory()` 状态现在显示在 **API** 可用性部分下。  新 `performance.measureMemory()` API 估计了整个网页的内存使用率。  若要查看 Chromium 开放源代码项目中此功能的历史记录，请导航到"问题[1139899"。][CR1139899]  

:::image type="complex" source="../../media/2021/01/application-frames-measure-memory.msft.png" alt-text="测量内存" lightbox="../../media/2021/01/application-frames-measure-memory.msft.png":::
   测量内存  
:::image-end:::  

### <a name="dropped-frames-in-the-performance-tool"></a>性能工具中丢弃的帧  

在性能 [工具中分析负载性能时][DevtoolsEvaluatePerformanceReferenceRecordLoadPerformance]，"框架 **"部分现在** 将丢弃的帧标记为红色。  若要显示帧速率，请将鼠标悬停在一个丢弃的帧上。  若要查看 Chromium 开源项目中此功能的历史记录，请导航到"问题[1075865"。][CR1075865]  

:::image type="complex" source="../../media/2021/01/performance-frames-dropped-frames-red.msft.png" alt-text="丢弃的帧" lightbox="../../media/2021/01/performance-frames-dropped-frames-red.msft.png":::
   丢弃的帧  
:::image-end:::  

#### <a name="new-color-contrast-calculation---advanced-perceptual-contrast-algorithm-apca"></a>新颜色对比度计算 - 高级感知对比度算法 (APCA)   

:::image type="icon" source="../../media/2020/06/experimental-tag-14px.msft.png":::  

APCA 高级感知对比度算法[ (APCA][GithubW3cSilverGuidelinesMethodsMethodFontCharacteristicContrastHtml]) 替换了颜色选取器中的[AA][W3cWaiWcag21QuickrefContrastMinimum] / [AAA][W3cWaiWcag21QuickrefContrastEnhanced]指南[对比率][DevtoolsAccessibilityReferenceViewContrastRatioTextElementColorPicker]。  APCA 是计算对比度的一种新方式。  它基于对颜色感知的新式研究。  与 AA/AAA 准则相比，APCA 更依赖于上下文。  对比度根据文本、颜色和上下文的以下空间属性计算。  

*   文本的空间属性，包括字体粗细和大小。  
*   包含文本和背景之间感知对比度的颜色的空间属性。  
*   包含环境光、周围环境和预期用途的上下文的空间属性。  
    
若要打开此实验，请导航到[][DevtoolsCustomizeIndexSettings]设置实验，并选中启用新的高级感知对比度算法 (APCA) 替换以前的对比度比率和  >  ******AA/AAA 指南旁边的复选框**。  若要查看 Chromium 开放源代码项目中此功能的历史记录，请导航到"问题[1121900"。][CR1121900]  

:::image type="complex" source="../../media/2021/01/advanced-perceptual-contrast-algorithm.msft.png" alt-text="颜色选取器中的 APCA" lightbox="../../media/2021/01/advanced-perceptual-contrast-algorithm.msft.png":::
   颜色选取器中的 APCA  
:::image-end:::  

## <a name="download-the-microsoft-edge-preview-channels"></a>下载 Microsoft Edge 预览频道  

如果你使用的是 Windows、Linux 或 macOS，请考虑使用 [Microsoft Edge 预览][MicrosoftEdgePreviewChannels] 通道作为默认开发浏览器。  预览频道使你能够访问最新的 DevTools 功能。  

## <a name="getting-in-touch-with-microsoft-edge-devtools-team"></a>联系 Microsoft Edge DevTools 团队  

[!INCLUDE [contact DevTools team note](../../includes/contact-whats-new-note.md)]

<!-- links -->  

[DevtoolsWhatsNew85]: ../../2020/06/devtools.md "Microsoft Edge 85 (开发工具中的新增) |Microsoft Docs"  

[DevtoolsAccessibilityReferenceViewContrastRatioTextElementColorPicker]: /microsoft-edge/devtools-guide-chromium/accessibility/reference#view-the-contrast-ratio-of-a-text-element-in-the-color-picker "查看颜色选取器中的文本元素的对比率 - 辅助功能参考|Microsoft Docs"  
[DevtoolsCssReferenceChangeCss]: /microsoft-edge/devtools-guide-chromium/css/reference#change-css "更改 CSS - CSS |Microsoft Docs"  
[DevtoolsCustomizeIndexSettings]: /microsoft-edge/devtools-guide-chromium/customize/index#settings "设置 - 自定义 Microsoft Edge DevTools | Microsoft Docs"  
[DevtoolsCustomizeShortcuts]: microsoft-edge/devtools-guide-chromium/customize/shortcuts "自定义 Microsoft Edge DevTools 工具中的键盘|Microsoft Docs"  
[DevtoolsDeviceModeDualScreenFoldablesTestingFoldableDualScreenDevices]: /microsoft-edge/devtools-guide-chromium/device-mode/dual-screen-and-foldables#testing-on-foldable-and-dual-screen-devices "在可折叠和双屏幕设备上进行测试 - 在 Microsoft Edge DevTools 设备上模拟双屏幕和可折叠|Microsoft Docs"  
[DevtoolsDeviceModeIndex]: /microsoft-edge/devtools-guide-chromium/device-mode/index "在 Microsoft Edge DevTools 中模拟移动设备 | Microsoft Docs"  
[DevtoolsDeviceModeIndexSimulateMobileViewport]: /microsoft-edge/devtools-guide-chromium/device-mode/index#simulate-a-mobile-viewport "模拟移动视区 - 模拟 Microsoft Edge DevTools |Microsoft Docs"  
[DevtoolsEvaluatePerformanceReferenceRecordLoadPerformance]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference#record-load-performance "记录负载性能 - 性能分析|Microsoft Docs"  
[DevtoolsInspectStylesEditFonts]: /microsoft-edge/devtools-guide-chromium/inspect-styles/edit-fonts "在 DevTools | 中的"样式"窗格中编辑 CSS 字体样式和|Microsoft Docs"  
[DevtoolsMain]: /microsoft-edge/devtools-guide-chromium/index "Microsoft Edge (Chromium) 开发人员工具概述|Microsoft Docs"  

[DualScreenIntroductionHowToWorkWithSeam]: /dual-screen/introduction#how-to-work-with-the-seam "如何使用设备 - 双屏幕设备应用|Microsoft Docs"  
[DualScreenWebCssMediaSpanning]: /dual-screen/web/css-media-spanning "用于双屏检测方法的 CSS 媒体屏幕跨越|Microsoft Docs"  
[DualScreenWebJavascriptGetwindowsegments]: /dual-screen/web/javascript-getwindowsegments "适用于双屏幕设备的 getWindowSegments JavaScript API |Microsoft Docs"  

[GithubMicrosoftedgeDevtoolssamplesWhatsNew89TargetCssDemoHtmlSection1]: https://microsoftedge.github.io/DevToolsSamples/whats-new/89/target-css-demo.html#section-1 "第 1 部分 - Microsoft Edge 89 (中的新增功能 CSS ：target) |GitHub"  
[GithubMicrosoftVscodeEdgeDevtools]: https://github.com/microsoft/vscode-edge-devtools "microsoft/vscode-edge-devtools |GitHub"  
[GithubMicrosoftVscodeEdgeDevtoolsPull229]: https://github.com/microsoft/vscode-edge-devtools/pull/229 "拉 229：在设置中实现下拉列表以更改主题|GitHub"  
[GithubMicrosoftVscodeEdgeDevtoolsPull233]: https://github.com/microsoft/vscode-edge-devtools/pull/233 "拉 233：将 Microsoft Edge 调试器作为依赖项|GitHub"  
[GithubMicrosoftVscodeEdgeDevtoolsPull235]: https://github.com/microsoft/vscode-edge-devtools/pull/235 "Pull 235：将 Edge DevTools 版本升级到 85.0.564.40 |GitHub"  
[GithubMicrosoftVscodeEdgeDevtoolsPull248]: https://github.com/microsoft/vscode-edge-devtools/pull/248 "拉 248：将单个关闭按钮添加到实例面板|GitHub"  
[GithubW3cSilverGuidelinesMethodsMethodFontCharacteristicContrastHtml]: https://w3c.github.io/silver/guidelines/methods/Method-font-characteristic-contrast.html "选择字体特征和背景颜色以提供足够的对比度，以便可读性|W3C"  
[GithubW3cWebappsecTrustedTypesDistSpec]: https://w3c.github.io/webappsec-trusted-types/dist/spec  "受信任类型|W3C"  

[MicrosoftSurfaceDevicesSurfaceDuo]: https://www.microsoft.com/surface/devices/surface-duo "新 Surface Duo |Microsoft"  

[MicrosoftEdgePreviewChannels]: https://www.microsoftedgeinsider.com/download "Microsoft Edge 预览频道"  

[VisualstudioCodeDocsEditorExtensionGalleryUpdateExtensionManually]: https://code.visualstudio.com/docs/editor/extension-gallery#_update-an-extension-manually "手动更新扩展 - 扩展市场|Visual Studio 代码"  

[VisualstudioMarketplaceMsEdgedevtoolsVscodeEdgeDevtools]: https://marketplace.visualstudio.com/items?itemName=ms-edgedevtools.vscode-edge-devtools "Microsoft Edge 代码Visual Studio工具|Visual Studio Marketplace"  
[VisualstudioMarketplaceMsjsdiagDebuggerMicrosoftEdge]: https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge "适用于 Microsoft Edge |Visual Studio Marketplace"  

[CRIssuesList]: https://bugs.chromium.org/p/chromium/issues/list "Chromium Bug"  
[CR978059]: https://crbug.com/978059 "问题 978059：在筛选 Cookie 时删除它们，删除所有 Cookie，而不只是删除筛选的|Chromium Bug"  
[CR997625]: https://crbug.com/997625 "问题 997625：新功能|需要查看 Cookie 中的 url 解码值的选项|Chromium Bug"  
[CR1003629]: https://crbug.com/1003629 "问题 1003629：捕获节点不再对折叠下方的节点进行屏幕截图。|Chromium Bug"  
[CR1012337]: https://crbug.com/1012337 "问题 1012337：清除网站数据会销毁非 Google 网站上 Google |Chromium Bug"  
[CR1028078]: https://crbug.com/1028078 "问题 1028078：联机和脱机在列表中彼此|Chromium Bug"  
[CR1054281]: https://crbug.com/1054281 "问题 1054281：功能请求：DevTools 应模拟可折叠和双屏幕设备|Chromium Bug"  
[CR1075865]: https://crbug.com/1075865 "问题 1075865：在开发工具时间线中显示丢弃|Chromium Bug"  
[CR1093229]: https://crbug.com/1093229 "问题 1093229：DevTools：提供专用的字样编辑器 UI |Chromium Bug"  
[CR1121900]: https://crbug.com/1121900 "问题 1121900：DevTools：根据新规范更新对比度计算|Chromium Bug"  
[CR1122507]: https://crbug.com/1122507 "问题 1122507：框架树视图中的 Surface 工作线程信息 | Chromium 漏洞"  
[CR1122580]: https://crbug.com/1122580 "问题 1122580：重载时无法禁用网络|Chromium Bug"  
[CR1136394]: https://crbug.com/1136394 "问题 1136394：Flexbox 工具 | Chromium 漏洞"  
[CR1139899]: https://crbug.com/1139899 "问题 1139899：在框架详细信息视图中报告封闭的 API 的可用性 | Chromium 漏洞"  
[CR1139949]: https://crbug.com/1139949 "问题 1139949：弹性框覆盖|Chromium Bug"  
[CR1147016]: https://crbug.com/1147016 "问题 1147016：颜色选取器不显示在 var () 函数中。|Chromium Bug"  
[CR1148353]: https://crbug.com/1148353 "问题 1148353：功能请求：从开发工具控制台控制台复制|Chromium Bug"  
[CR1149859]: https://crbug.com/1149859 "问题 1149859：[功能请求][控制台]将复制对象添加到剪贴板项到上下文菜单|Chromium Bug"  
[CR1150797]: https://crbug.com/1150797 "问题 1150797：在元素面板菜单中添加重复元素|Chromium Bug"  
[CR1152391]: https://crbug.com/1152391 "问题 1152391：支持将 CSS 上下文菜单复制到样式面板|Chromium Bug"  
[CR1155120]: https://crbug.com/1155120 "问题 1155120：[FR]支持复制文件名和行号|Chromium Bug"  
[CR1156628]: https://crbug.com/1156628 "问题 1156628：DevTools：添加对 ：target in force 元素状态功能|Chromium Bug"  
[CR1157329]: https://crbug.com/1157329 "问题 1157329：辅助功能 - 讲述人：讲述人不会在"样式"选项卡的"列表"中公布适用于代码的建议|Chromium Bug"  

[MdnDocsWebCssTarget]: https://developer.mozilla.org/docs/web/css/:target "：target |MDN"  

[SamsungUsMobileGalaxyFold]: https://www.samsung.com/us/mobile/galaxy-fold "百合|Samsung US"  

[W3cWaiWcag21QuickrefContrastEnhanced]: https://www.w3.org/WAI/WCAG21/quickref#contrast-enhanced "对比度 (增强) - 如何满足 WCAG (快速参考) |W3C"  
[W3cWaiWcag21QuickrefContrastMinimum]: https://www.w3.org/WAI/WCAG21/quickref#contrast-minimum "对比度 (最低) - 如何满足 WCAG (快速参考) |W3C"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于 [此处](https://developers.google.com/web/updates/2021/01/devtools/index)，并由 [Jecelyn Yeen][JecelynYeen] \（开发人员支持者，Chrome DevTools\）制作。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen

[SpanningPlaceholder]: link-t-b-d "跨区占位符"  
