---
description: 了解 Microsoft Edge (Chromium) 开发人员工具
title: Microsoft Edge (Chromium) 开发人员工具概述
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/07/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: devtools
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: 3d91b0754f84579d770940503cf4a252e3926416
ms.sourcegitcommit: fa8bedfc83fbd1c4ce7bda8c69586c4f24007beb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/07/2021
ms.locfileid: "11481393"
---
# <a name="microsoft-edge-chromium-developer-tools-overview"></a>Microsoft Edge (Chromium) 开发人员工具概述  

安装 Microsoft Edge 时，将获取浏览器。 此外，您还可以获得检查、调试甚至创建 Web 项目的强大方法。  浏览器附带的开发人员工具基于 Chromium 开放源代码项目中的工具，因此您可能已经熟悉这些工具。  若要使本文中的说明保持简短， `Microsoft Edge Developer Tools` 现在称为 `DevTools` 。  

使用 DevTools 查看并了解有关以下开发任务有关详细信息。  

*   [检查并更改浏览器中的当前][DevtoolsGuideDomIndex] 网页。  
*   [模拟产品在不同设备上的行为方式，][DevtoolsGuideDeviceModeIndex] 并模拟具有不同网络条件的移动环境。  
*   [使用具有可视界面的][DevtoolsGuideInspectStylesEditFonts] 实时工具检查、调整和更改网页中元素的样式。  
*   [使用断][DevtoolsGuideJavascriptIndex]点调试和实时控制台 调试[JavaScript。][DevtoolsGuideConsoleIndex]  
*   在 [产品中查找][DevtoolsGuideIssuesIndex] 辅助功能、性能、兼容性和安全问题，并了解如何使用 DevTools 修复每个问题。  
*   [检查网络流量][DevtoolsGuideNetworkIndex] 并查看问题的位置。  
*   [检查浏览器以不同格式存储][DevtoolsGuideStorageSessionstorage] 内容的位置。  
*   [评估产品][DevtoolsGuideEvaluatePerformanceIndex]的性能，以查找[内存问题和][DevtoolsGuideMemoryProblemsIndex][呈现问题][DevtoolsGuideRenderingToolsIndex]。  
*   [使用开发环境将][DevtoolsGuideSourcesIndex] [DevTools][DevtoolsGuideWorkspacesIndex] 中的更改与文件系统同步， [并覆盖 Web][DevtoolsGuideJavascriptOverrides] 中的文件。  
    
<!-- Is the link meant to be local or session storage for "inspect where the browser stored content"? -->  

以及更多功能。  当你打开 DevTools 并根据需要自定义每个工具时，这一切将开始。  

## <a name="open-the-devtools"></a>打开 DevTools  

若要打开和浏览 DevTools，请使用以下任一操作。  

*   将鼠标悬停在网页上的任何元素上，打开上下文菜单 \ (右键单击\) ，然后选择"检查 **"。**  此操作将打开 **"元素"** 工具。  
*   选择 `F12`。  
*   在 `Ctrl` + `Shift` + `I` Windows/Linux 或 `Command` + `Option` + `I` macOS 上选择。  
    
:::row:::  
   :::column span="":::  
      :::image type="complex" source="./media/devtools-intro-inspect.msft.png" alt-text="从任何元素上的上下文菜单中选择"检查"" lightbox="./media/devtools-intro-inspect.msft.png":::  
         从 **任何元素** 上的上下文菜单中选择"检查"  
      :::image-end:::  
   :::column-end:::  
   :::column span="":::  
      :::image type="complex" source="./media/devtools-intro-inspect-devtools-open.png" alt-text="将打开 DevTools，并突出显示所选元素" lightbox="./media/devtools-intro-inspect-devtools-open.png":::  
         将打开 DevTools，并突出显示所选元素  
      :::image-end:::  
   :::column-end:::  
:::row-end:::  

有两种主要方式可以与 DevTools 进行交互。
*   使用鼠标  
*   [键盘快捷方式][DevtoolsGuideShortcutsIndex]。  键盘快捷方式提供了访问功能的快速方法，辅助功能需要这些快捷方式。  Microsoft Edge DevTools 团队致力于使用键盘和辅助技术（如屏幕阅读器）提供所有工具。  若要详细了解如何在 DevTools 中打开不同功能，请导航到 [Microsoft Edge DevTools 键盘快捷方式][DevtoolsGuideOpenIndex]。  

## <a name="dock-the-devtools-in-your-browser"></a>在浏览器中停靠 DevTools  

打开 DevTools 时，它停靠在浏览器左侧。  若要更改 DevTools 的停靠位置，请完成以下操作。  

1.  选择" **自定义和控制 DevTools** \ (`...` \) "按钮。  
1.  在相对于页面 \ (**扩展**坞端 \) 的**DevTools**的右侧，选择"扩展**坞端**"选项。  
    
有关详细信息，请导航到更改[Microsoft Edge DevTools 放置位置 (Undock、Dock To Bottom、Dock To Left) 。 ][DevtoolsGuideCustomizePlacement]  

:::image type="complex" source="./media/devtools-intro-docking-menu.msft.png" alt-text="DevTools 中扩展坞侧菜单的屏幕截图" lightbox="./media/devtools-intro-docking-menu.msft.png":::  
   DevTools 中扩展坞侧菜单的屏幕截图  
:::image-end:::  

在 **扩展坞端**中，选择以下任一布局选项。  

*   **取消停靠到单独的窗口**。   帮助你使用多个监视器，或者如果你需要在全屏应用上工作。  
*   **扩展坞向左或****扩展坞向右**。  有助于将 DevTools 与 Web 产品并排使用，并且当你模拟移动设备时，它非常出色。  The **Dock to left** and Dock to **right** options work best with high-resolution displays.  有关模拟设备的信息，请导航到 Microsoft [Edge DevTools][DevtoolsGuideDeviceModeIndex]中的"模拟移动设备"。  
*   **停靠到底部**。  当你没有足够的水平显示空间，或者你想要在 DOM 或控制台中调试长文本时，可帮助 **你**。  
    
:::row:::  
   :::column span="":::  
      :::image type="complex" source="./media/devtools-intro-docking-left.msft.png" alt-text="选择停靠到左侧" lightbox="./media/devtools-intro-docking-left.msft.png":::  
         选择 **"停靠到左侧"**  
      :::image-end:::  
   :::column-end:::  
   :::column span="":::  
      :::image type="complex" source="media/devtools-intro-docking-bottom.msft.png" alt-text="选择停靠到底部" lightbox="media/devtools-intro-docking-bottom.msft.png":::  
         选择 **"扩展坞到底部"**  
      :::image-end:::  
   :::column-end:::  
:::row-end:::  
:::row:::  
   :::column span="":::  
      :::image type="complex" source="media/devtools-intro-docking-right.msft.png" alt-text="选择"扩展坞到右侧"" lightbox="media/devtools-intro-docking-right.msft.png":::  
         选择 **"扩展坞到右侧"**  
      :::image-end:::  
   :::column-end:::  
   :::column span="":::  
      :::image type="complex" source="media/devtools-intro-docking-own-window.msft.png" alt-text="选择"取消停靠到单独的窗口"" lightbox="media/devtools-intro-docking-own-window.msft.png":::  
         选择 **"取消停靠到单独的窗口"**  
      :::image-end:::  
   :::column-end:::  
:::row-end:::  

## <a name="learn-about-the-core-tools"></a>了解核心工具  

DevTools 为您提供了一项令人惊叹的功能，可以检查、调试和更改浏览器中当前显示的 Web 产品。  大多数工具实时显示更改。  实时更新使工具非常有用，无需刷新或生成即可优化 Web 项目的外观和导航或功能。  DevTools 还允许你更改计算机上基于 Web 的第三方产品。  

DevTools 在几年内逐渐增加。  你可能假设首次打开任何工具时很难了解 DevTools。  以下文本快速介绍了不同的部分。  主工具栏为您提供了一些部分，这些部分按从左到右的顺序排序。  

:::image type="complex" source="./media/devtools-intro-menu-bar.msft.png" alt-text="包含说明不同部分的标签的 DevTools 菜单栏的屏幕截图。  顺序：检查工具、设备仿真工具、"工具"选项卡组、JavaScript 错误、问题、设置、反馈、自定义和关闭。" lightbox="./media/devtools-intro-menu-bar.msft.png":::  
   包含说明不同部分的标签的 DevTools 菜单栏的屏幕截图。  顺序：检查工具、设备仿真工具、"工具"选项卡组、JavaScript 错误、问题、设置、反馈、自定义和关闭。  
:::image-end:::  

*   "检查工具"允许您选择当前网页上的某个元素。  激活后，你可以将鼠标移动到网页的不同部分，以获取有关元素和颜色覆盖的详细信息以显示尺寸、填充和边距。  
    
    :::image type="complex" source="./media/devtools-intro-inspect-tool.msft.png" alt-text="Screenshot of the inspect tool with the first headline of this article chosen" lightbox="./media/devtools-intro-inspect-tool.msft.png":::  
       Screenshot of the inspect tool with the first headline of this article chosen  
    :::image-end:::  
    
*   [设备仿真工具][DevtoolsGuideDeviceModeIndex]在仿真设备模式下显示当前 Web 产品。  **设备仿真工具**允许你在调整浏览器大小时运行和测试产品的反应。  它还为你提供移动设备上的布局和行为估计。  
    
    :::image type="complex" source="./media/devtools-intro-device-emulation.msft.png" alt-text="本文在仿真移动电话中的 DevTools 显示的屏幕截图" lightbox="./media/devtools-intro-device-emulation.msft.png":::  
       本文在仿真移动电话中的 DevTools 显示的屏幕截图  
    :::image-end:::  
    
*   "工具"选项卡组是一组选项卡，表示在不同方案中使用的不同工具。  你可以自定义每个工具，并且每个工具可能会根据上下文更改。  若要打开更多工具的下拉菜单，请选择"更多 **选项卡** \ (`>>` \) "按钮。  以下部分稍后将介绍每一种工具。  
*   "工具"选项卡组旁边是可选错误和问题快捷方式。  在当前网页上出现 JavaScript 错误或问题时，会显示快捷方式。  " **打开控制台以查看 # 错误，# 警告** \ (**JavaScript**错误 \) "按钮显示一个红色圆圈，后跟 `X` JavaScript 错误数。  若要打开 [控制台并了解][DevtoolsGuideConsoleIndex] 错误，请选择 **"JavaScript 错误"** 按钮。  " **要查看 # 问题的** 打开问题 \ (**问题**\) "按钮是一个蓝色消息图标，后跟问题数。  若要打开"问题 ["][DevtoolsGuideIssuesIndex] 工具，请选择" **问题"** 按钮。  
*   " **设置** "按钮显示齿轮图标。  若要打开"DevTools **设置"** 网页，请选择"设置 **"** 按钮。  " **设置** "网页显示一个菜单，用于更改 **首选项**、打开 **实验**等。  
*   " **发送反馈** "按钮显示旁边有一个聊天气泡的 torso。  若要打开" **发送反馈** "对话框，请选择" **发送反馈"** 按钮。  " **发送反馈** "对话框允许你输入描述所发生情况的信息，并自动包含屏幕截图。  使用它与 DevTools 团队联系，以报告问题、问题或建议想法。  
*   " **自定义和控制 Devtools** \ (`...` \) "按钮将打开一个下拉菜单。  它允许你定义停靠 DevTools、搜索、打开不同工具等位置。  
    
在"工具"选项卡组中，你可以打开 DevTools 中提供的不同工具。  以下列表介绍了 DevTools 中最常用的工具。  

*   **欢迎**使用 。  包括有关 DevTools 的新功能、如何联系团队的信息，并提供有关某些功能的信息。  
*   **元素**。  允许您编辑或检查 HTML 和 CSS。  您可以在工具中编辑这两项操作，在浏览器中实时显示更改。  
*   [控制台][DevtoolsGuideConsoleIndex]。  允许您显示和筛选日志消息。  日志消息是浏览器的自动日志，如网络请求和开发人员生成的日志。  还可以在当前窗口或框架的上下文中直接在**** 控制台中运行 JavaScript。  
*   [源][DevtoolsGuideSourcesIndex]。  代码编辑器和 JavaScript 调试程序。  可以编辑项目、维护代码段和调试当前项目。  
*   [网络][DevtoolsGuideNetworkIndex]。  允许您监视和检查来自网络和浏览器缓存的请求或响应。  你可以筛选请求和响应以满足您的需求并模拟不同的网络条件。  其他专用工具也可用，如**性能**、内存、******应用程序****、安全性和****审核**。  

## <a name="power-tip-use-the-command-menu"></a>电源提示：使用命令菜单  

DevTools 提供了许多要用于 Web 产品的特性和功能。  通过多种方式访问 DevTools 的不同部分，但访问所需的功能的最快方式是使用命令菜单。  有关详细信息，请导航到使用 [Microsoft Edge DevTools][DevtoolsGuideCommandMenuIndex]命令菜单运行命令。  若要打开命令菜单，请完成以下操作之一。  

*   选择 `Control` + `Shift` + `P` \(Windows、Linux\) 或 `Command` + `Shift` + `P` \(macOS\)。  
*   Choose **Customize and Control DevTools** \ (`...` \) ， and then choose **Run Command**.  

:::image type="complex" source="./media/devtools-intro-command-menu.msft.png" alt-text="DevTools 中命令菜单的屏幕截图" lightbox="./media/devtools-intro-command-menu.msft.png":::  
DevTools 中命令菜单的屏幕截图  
:::image-end:::  

命令菜单允许你键入命令以在 DevTools 中显示、隐藏或运行功能。  打开命令菜单后，输入 **"更改"** 一词，然后选择"**箱显示更改"。**  The **Changes** tool opens which is useful when you edit CSS, but is difficult to find in the DevTools UI.  

:::row:::  
   :::column span="":::  
      :::image type="complex" source="./media/devtools-intro-command-menu-show-changes.msft.png" alt-text="键入更改后，命令菜单将显示选项" lightbox="./media/devtools-intro-command-menu-show-changes.msft.png":::  
         键入后，命令菜单将显示选项 `changes`  
      :::image-end:::  
   :::column-end:::  
   :::column span="":::  
      :::image type="complex" source="./media/devtools-intro-showing-changes.msft.png" alt-text="打开"更改"工具的 DevTools" lightbox="./media/devtools-intro-showing-changes.msft.png":::  
         打开"更改" **工具的** DevTools  
      :::image-end:::  
   :::column-end:::  
:::row-end:::  

## <a name="customize-the-devtools"></a>自定义 DevTools  

可自定义 DevTools 以满足你的需求或工作方式。  若要更改设置，请完成以下操作之一。  

*   Choose **Settings** \ (the gear icon on the top right\)   
*   选择 `F1` 或 `?` 。  
    
在 **首选项部分中** ，你可以更改 DevTools 的几个部分。  例如，可以使用"匹配浏览器语言 **"设置** 在浏览器中使用的 DevTools 中使用相同的语言。  有关另一个示例，请使用 **Theme** 设置更改 DevTools 的主题。  

:::image type="complex" source="media/devtools-intro-all-settings.msft.png" alt-text="DevTools 中所有设置的屏幕截图" lightbox="./media/devtools-intro-all-settings.msft.png":::  
   DevTools 中所有设置的屏幕截图  
:::image-end:::  

还可以更改高级功能的设置，包括以下功能。    

*   [工作区][DevtoolsGuideWorkspacesIndex]。  
*   具有"忽略列表"的 **筛选器库代码**。  
*   定义 **你想要** 包括在设备模拟和测试模式下的设备。  有关详细信息，请导航到在 [Microsoft Edge DevTools][DevtoolsGuideDeviceModeIndex]中模拟移动设备。  
*   选择网络 **限制** 配置文件。  
*   定义模拟 **的位置**。  
*   自定义键盘快捷方式。  若要在 DevTools 和代码Visual Studio快捷方式，请完成以下操作。  
    1.  从**预设中选择"匹配快捷方式"。**  
    1.  选择**Visual Studio代码"。**  
        
    :::image type="complex" source="./media/devtools-intro-match-keys.msft.png" alt-text="所有键盘快捷方式和菜单的屏幕截图，这些快捷方式与代码中的快捷方式Visual Studio匹配" lightbox="./media/devtools-intro-match-keys.msft.png":::  
       所有键盘快捷方式和菜单的屏幕截图，这些快捷方式与代码中的快捷方式Visual Studio匹配  
    :::image-end:::  
    
## <a name="try-experimental-features"></a>试用实验性功能  

DevTools 团队在 DevTools 中提供新功能作为实验。  若要获取实验的完整列表，请导航到"DevTools**设置**"，然后选择"实验 **"。**  你可以打开或关闭每个实验。  帮助确定哪一个实验对你有价值。  有关实验详细信息，请导航到实验 [功能][DevtoolsGuideExperimentalFeaturesIndex]。  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>与 Microsoft Edge 开发人员工具团队联系  

[!INCLUDE [contact DevTools team note](./includes/contact-devtools-team-note.md)]  

如果你想要预览 [DevTools][DevtoolsGuideWhatsNew202102Devtools]中提供的最新功能，请下载 [Microsoft Edge Canary][MicrosoftedgeinsiderDownload]，它在夜间生成。  

## <a name="see-also"></a>另请参阅  

*   [DevtoolsGuide for Beginners：HTML 和 DOM 入门][DevtoolsGuideBeginnersHtml]  
*   [Microsoft Edge (Chromium) DevTools 协议][DevtoolsProtocolIndex]  
    
<!-- links -->  

[DevtoolsGuideBeginnersHtml]: ./beginners/html.md "适用于初学者的 DevTools：HTML 和 DOM |Microsoft Docs"  
[DevtoolsGuideCommandMenuIndex]: ./command-menu/index.md "使用 Microsoft Edge DevTools 命令菜单菜单运行 | Microsoft Docs"  
[DevtoolsGuideConsoleIndex]: ./console/index.md "控制台概述 | Microsoft Docs"  
[DevtoolsGuideCustomizePlacement]: ./customize/placement.md "将 Microsoft Edge DevTools (Undock、Dock To Bottom、Dock To Left) |Microsoft Docs"  
[DevtoolsGuideDeviceModeIndex]: ./device-mode/index.md "在 Microsoft Edge 开发人员工具中模拟移动设备 | Microsoft Docs"  
[DevtoolsGuideDomIndex]: ./dom/index.md "开始查看和更改 DOM |Microsoft Docs"  
[DevtoolsGuideEvaluatePerformanceIndex]: ./evaluate-performance/index.md "开始分析运行时性能|Microsoft Docs"  
[DevtoolsGuideExperimentalFeaturesIndex]: ./experimental-features/index.md "试验功能 | Microsoft Docs"  
[DevtoolsGuideMemoryProblemsIndex]: ./memory-problems/index.md "修复内存|Microsoft Docs"  
[DevtoolsGuideInspectStylesEditFonts]: ./inspect-styles/edit-fonts.md "在&quot;样式&quot;窗格中编辑 CSS 字体样式|Microsoft Docs"  
[DevtoolsGuideIssuesIndex]: ./issues/index.md "查找并修复 Microsoft Edge DevTools 问题工具的问题 | Microsoft Docs"  
[DevtoolsGuideJavascriptIndex]: ./javascript/index.md "在 Microsoft Edge 开发人员工具中调试 JavaScript 入门 | Microsoft Docs"  
[DevtoolsGuideJavascriptOverrides]: ./javascript/overrides.md "使用 Microsoft Edge DevTools 工具替代具有本地副本的网页|Microsoft Docs"  
[DevtoolsGuideNetworkIndex]: ./network/index.md "检查 Microsoft Edge DevTools |Microsoft Docs"  
[DevtoolsGuideOpenIndex]: ./open/index.md "打开 Microsoft Edge DevTools | Microsoft Docs"  
[DevtoolsGuideRenderingToolsIndex]: ./rendering-tools/index.md "分析运行时性能|Microsoft Docs"  
[DevtoolsGuideShortcutsIndex]: ./shortcuts/index.md "Microsoft Edge DevTools 键盘快捷方式|Microsoft Docs"  
[DevtoolsGuideSourcesIndex]: ./sources/index.md "源工具概述 | Microsoft Docs"  
[DevtoolsGuideStorageSessionstorage]: ./storage/sessionstorage.md "使用 Microsoft Edge DevTools 工具查看和编辑|Microsoft Docs"  
[DevtoolsGuideWhatsNew202102Devtools]: ./whats-new/2021/02/devtools.md "Microsoft Edge 90 (DevTools 中的新增) |Microsoft Docs"  
[DevtoolsGuideWorkspacesIndex]: ./workspaces/index.md "使用 Workspaces |Microsoft Docs"  
[DevtoolsProtocolIndex]: ../devtools-protocol-chromium/index.md "Microsoft Edge (Chromium) DevTools 协议概述|Microsoft Docs"  

[MicrosoftEdgeAddonsExtensions]: https://microsoftedge.microsoft.com/addons/category/Edge-Extensions "Microsoft Edge 加载项"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "下载 Microsoft Edge 预览体验成员频道"  

[GoogleChromeWebstoreExtensions]: https://chrome.google.com/webstore/category/extensions "扩展|Chrome Web Store"  
