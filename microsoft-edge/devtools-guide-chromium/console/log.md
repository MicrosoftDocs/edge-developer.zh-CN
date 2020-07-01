---
title: 在控制台中记录消息入门
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/24/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 4c930caf60af2b5e276e003378546e147c249548
ms.sourcegitcommit: 0048eb692d49eab4755c0c3ef6866e6a9122d579
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/01/2020
ms.locfileid: "10843962"
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





# 在控制台中记录消息入门   



此交互式教程介绍如何在[Microsoft Edge DevTools][MicrosoftEdgeDevTools]控制台中记录和筛选邮件。  

> ##### 图 1  
> 控制台中的消息  
> ![控制台中的消息][ImageLogExample]  

本教程旨在按顺序完成。  它假定你了解 web 开发的基础知识，例如如何使用 JavaScript 向页面添加交互。  

## 设置演示和 DevTools   

本教程旨在使您能够打开演示并自行尝试所有工作流。  当您进行物理跟踪时，更有可能会在以后记忆工作流。  

1.  保留 `Control` \ （Windows \）或 `Command` \ （macOS \），然后单击 "**控制台日志示例**" 以在新选项卡中打开。  
    
    [控制台日志示例][GlitchDevToolsConsoleLogExamples]
    
    <!-- > [!TIP]
    > Move the demo to a separate window.  
    > 
    > > ##### old Figure 2  
    > > The tutorial on the left, and the demo on the right  
    > > ![The tutorial on the left, and the demo on the right][ImageLogSetUp1]  -->
    
1.  聚焦演示，然后按 `Control` + `Shift` + `J` \ （Windows \）或 `Command` + `Option` + `J` \ （macOS \）打开 DevTools。  默认情况下，DevTools 将在演示右侧打开。  
    
    > ##### 图 2  
    > DevTools 将在演示右侧打开  
    > ![DevTools 将在演示右侧打开][ImageDevToolsRight]  
    
    > [!TIP]
    > [将 DevTools 停靠在窗口底部或将其移到一个单独的窗口中][DevToolsCustomizePlacement]。  
    
    > ##### 图 3  
    > DevTools 停靠在演示底部  
    > ![DevTools 固定在演示底部][ImageDevToolsBottom]  
    
    > ##### 图 4  
    > 单独窗口中的浏览器  
    > ![浏览器在单独窗口中][ImageDevToolsSeparateBrowse]  
    
    > ##### 图 5  
    > DevTools 在单独窗口中取消停靠  
    > ![DevTools 在单独窗口中取消停靠][ImageDevToolsSeparateDevTools]  
    
## 查看从 JavaScript 记录的消息   

您在控制台中看到的大多数消息来自于编写页面 JavaScript 的 web 开发人员。  本部分的目标是介绍你可能会在控制台中看到的不同消息类型，并介绍如何从你自己的 JavaScript 中自己记录每种消息类型。  

1.  单击演示中的 "**日志信息**" 按钮。  `Hello, Console!` 记录到控制台。
    
    > ##### 图 6  
    > 单击 "**日志信息**" 后的控制台  
    > ![单击 "日志信息" 后的控制台][ImageLogInfo]  
    
1.  `Hello, Console!`在控制台中的邮件旁边，单击 " **log.js： 2**"。  "源" 面板将打开并突出显示导致消息登录到控制台的代码行。  当页面的 JavaScript 运行时，将记录此消息 `console.log('Hello, Console!')` 。
    
    > ##### 图 7  
    > 单击 "log.js" 后，DevTools 将打开 "源" 面板 **： 2**  
    > ![DevTools 在你单击 "log.js： 2] 后打开" 源 "面板[ImageSourceLog]  
    
1.  使用以下任一工作流向后导航到控制台：  
    
    *   单击 "**控制台**" 选项卡。  
    *   按 `Control` + `[` \ （Windows \）或 `Command` + `[` \ （macOS \），直到控制台面板处于焦点。  
    *   [打开 "命令" 菜单][DevToolsCommandMenu]，开始键入 `Console` ，选择 "**显示控制台面板**" 命令，然后按 `Enter` 。  
    
1.  单击演示中的 "**日志警告**" 按钮。  `Abandon Hope All Ye Who Enter` 记录到控制台。  此类消息的格式是警告。  
    
    > ##### 图 8  
    > 单击 "**日志警告**" 后的控制台  
    > ![单击 "日志警告" 后的控制台][ImageConsoleLogWarning]  
    
    > [!TIP]
    > 如果想要查看导致邮件以特定方式记录的代码，请单击脚本 \ （如 `log.js:12` \）以查看导致邮件格式的代码。  

1.  单击**Expand** ![ 前面的展开展开 ][ImageExpandIcon] 图标 `Abandon Hope All Ye Who Enter` 。  DevTools 显示调用的[堆栈跟踪][WikiStackTrace]。  
    
    > ##### 图 9  
    > 堆栈跟踪  
    > ![堆栈跟踪][ImageStackTrace]  
    
    堆栈跟踪告诉你调用了名为的函数 `logWarning` ，而该函数又称为一个名为的函数 `quoteDante` 。  换句话说，首先发生的调用位于堆栈跟踪的底部。  你可以随时通过调用来记录堆栈跟踪 `console.trace()` 。  

1.  单击 "**日志错误**"。  已记录以下错误消息： `I'm sorry, Dave.  I'm afraid I can't do that.`  
    
    > ##### 图 10  
    > 一条错误消息  
    > ![一条错误消息][ImageLogError]  
    
1.  单击 "**日志表**"。  将有关著名音乐家的表格记录到控制台。  
    
    > [!NOTE]
    > `birthday`列仅填充一行。  检查代码，找出原因。
    
    > ##### 图 11  
    > 控制台中的表  
    > ![控制台中的表][ImageConsoleTable]  
    
1.  单击 "**日志组**"。  4个著名的犯罪 turtles 的名称在标签下分组 `Adolescent Irradiated Espionage Tortoises` 。  
    
    > ##### 图 12  
    > 控制台中的一组消息  
    > ![控制台中的一组消息][ImageConsoleLogGroup]  
    
1.  单击 "**日志自定义**"。  带有红色边框和蓝色背景的消息将记录到控制台。  
    
    > ##### 图 13  
    > 在控制台中自定义格式的邮件  
    > ![在控制台中有自定义格式的邮件][ImageConsoleLogCustomFormatting]  
    
此处的主要概念是，当你希望从 JavaScript 将消息记录到控制台时，请使用其中一种 `console` 方法。  每种方法设置邮件的格式都不同。  

此部分中介绍的方法甚至更多。  本教程介绍如何浏览方法的其余部分。  

## 查看浏览器记录的消息   

浏览器也将消息记录到控制台。  当页面出现问题时，通常会发生这种情况。  

1.  单击 "**原因 404**"。  `404`由于页面的 JavaScript 尝试提取不存在的文件，因此浏览器会记录网络错误。  
    
    > ##### 图 14  
    > 控制台中的404错误  
    > ![在控制台中出现404错误][ImageConsoleLogError]  
    
1.  单击 "**导致错误**"。  `TypeError`由于 JavaScript 尝试更新不存在的 DOM 节点，因此浏览器将记录未捕获。  
    
    > ##### 图 15  
    > 控制台中的 TypeError  
    > ![控制台中的 TypeError][ImageConsoleLogTypeError]  
    
1.  单击 "**日志级别**" 下拉列表，并启用 "**详细**" 选项（如果已禁用）。  在下一节中了解有关筛选的详细信息。  您需要执行此操作，以确保您记录的下一条消息是可见的。  
    **注意：** 如果 "默认级别" 下拉列表处于禁用状态，您可能需要关闭控制台边栏。 有关控制台边栏的详细信息，请按以下消息源进行筛选。
    
    > ##### 图 16  
    > 启用**详细**日志级别  
    > ![启用详细日志级别][ImageVerboseLogLevel]  
    
1.  单击 "**导致冲突**"。  该页面将在几秒钟后停止响应，然后浏览器将消息记录 `[Violation] 'click' handler took 3000ms` 到控制台。  确切持续时间可能会有所不同。  
    
    > ##### 图 17  
    > 控制台中的冲突  
    > ![在控制台中的冲突][ImageConsoleLogViolation]  
    
## 筛选邮件   

在某些页面上，你会看到该控制台会使消息淹没。  DevTools 提供了多种不同的方法来筛选出与手边的任务无关的邮件。  

### 按日志级别筛选   

每个 `console` 方法都分配了一个严重性级别： `Verbose` 、、 `Info` `Warning` 或 `Error` 。  例如， `console.log()` 是一种 `Info` 级别的消息，而 `console.error()` 是一种 `Error` 级别的消息。  

1.  单击 "**日志级别**" 下拉列表并禁用**错误**。  如果该级别旁边不再有选中标记，则该级别将被禁用。  `Error`级别消息消失。  
    
    > ##### 图18  
    > `Error`在控制台中禁用级别消息  
    > ![在控制台中禁用错误级别消息][ImageConsoleDisablingLogError]  
    
1.  再次单击 "**日志级别**" 下拉列表，然后重新启用**错误**。  `Error`级邮件再次出现。  

### 按文本进行筛选   

如果只希望查看包含确切字符串的邮件，请将该字符串键入到 "**筛选器**" 文本框中。  

1.  在 `Dave` "**筛选器**" 文本框中键入内容。  不包含该字符串的所有消息 `Dave` 均被隐藏。  您可能还会看到 `Adolescent Irradiated Espionage Tortoises` 标签。  这是一个 bug。  
    
    > ##### 图19  
    > 筛选出不包含的任何邮件 `Dave`  
    > ![筛选掉不包含 Dave 的任何消息][ImageLogTextFiltering]  
    
1.  `Dave`从 "**筛选器**" 文本框中删除。  所有邮件再次出现。  

### 按正则表达式筛选   

当你想要显示包含文本模式的所有消息（而不是特定字符串）时，请使用[正则表达式][MDNRegularExpressions]。  

1.  在 `/^[AH]/` "**筛选器**" 文本框中键入内容。  在[RegExr][|::ref1::|Main]中键入此模式，获取对其执行操作的说明。  
    
    > ##### 图20  
    > 筛选出与模式不匹配的任何邮件 `/^[AH]/`  
    > ![筛选出与模式不匹配的任何消息][ImageLogRegExFiltering]  
    
1.  `/^[AH]/`从 "**筛选器**" 文本框中删除。  所有邮件都将再次显示。  

### 按消息源筛选   

如果只希望查看来自特定 URL 的邮件，请使用**边栏**。  

1.  单击 "**显示控制台边栏** ![ 显示控制台边栏" ][ImageShowConsoleSidebarIcon] 。  
    
    > ##### 图21  
    > 边栏  
    > ![提要栏][ImageConsoleSidebar]  
    
1.  单击**Expand** ![ ][ImageExpandIcon] 邮件数旁边的展开展开图标。  在[图 21](#figure-21)中，邮件数显示为**13 条消息**。  **边栏**显示导致记录消息的 url 的列表。  例如， `log.js` 导致了11条消息。  
    
    > ##### 图22  
    > 查看边栏中的邮件源  
    > ![查看边栏中的邮件源][ImageConsoleSidebarLogSource]  
    
### 按用户消息筛选   

较早版本中，当您单击 "**日志信息**" 时，将调用一个脚本，以便 `console.log('Hello, Console!')` 将消息记录到控制台。  从属于此类的 JavaScript 记录的消息称为 "**用户消息**"。  相比之下，当你单击 "**原因 404**" 时，浏览器记录了一个 `Error` 级别消息，指出找不到所请求的资源。  类似消息被视为**浏览器消息**。  使用**边栏**筛选出浏览器消息，并仅显示用户消息。  

1.  单击 " **9 个用户消息**"。  浏览器消息处于隐藏状态。  
    
    > ##### 图23  
    > 筛选出浏览器消息  
    > ![筛选出浏览器消息][ImageConsoleLogBrowserFiltering]  
    
1.  单击**13 条消息**，再次显示所有消息。  

## 将控制台与任何其他面板一起使用   

如果正在编辑样式，但需要快速检查控制台日志是否有什么内容？ 使用抽屉。  

1.  单击 "**元素**" 选项卡。  
1.  按 `Escape` 。  将打开**抽屉**的 "控制台" 选项卡。  它具有您在整个教程中使用的控制台面板的所有功能。  
    
    > ##### 图24  
    > 抽屉中的 "控制台" 选项卡  
    > ![抽屉中的 "控制台" 选项卡][ImageDrawerConsole]  
    
<!--## Next steps  -->

<!--
*   See [Console Reference][DevToolsConsoleApi] to explore more features and workflows related to the Console UI.
*   See [Console API Reference][DevToolsConsoleReference] to learn more about all of the `console` methods that were demonstrated in [View messages logged from JavaScript(#view-messages-logged-from-javascript) and explore the other `console` methods that were not covered in this tutorial.  
*   See [Get Started](/microsoft-edge/devtools-guide-chromium/#start) to explore what else you are able to do with DevTools.  -->  

 



<!-- image links -->  

[ImageExpandIcon]: /microsoft-edge/devtools-guide-chromium/media/expand-icon.msft.png  
[ImageShowConsoleSidebarIcon]: /microsoft-edge/devtools-guide-chromium/media/show-console-sidebar-icon.msft.png  

[ImageLogExample]: /microsoft-edge/devtools-guide-chromium/media/console-ars-technica-console-onload.msft.png "图1：控制台中的邮件"  
<!--[ImageLogSetUp1]: /microsoft-edge/devtools-guide-chromium/media/log-set-up-1.msft.png "old Figure 2: The tutorial on the left, and the demo on the right"  -->  
[ImageDevToolsRight]：/microsoft-edge/devtools-guide-chromium/media/console-example-devtools-right-console.msft.png "图2： DevTools 将在演示的右侧打开"  
[ImageDevToolsBottom]：/microsoft-edge/devtools-guide-chromium/media/console-example-devtools-bottom-console.msft.png "图3： DevTools 停靠到演示的底部"  
[ImageDevToolsSeparateBrowse]：/microsoft-edge/devtools-guide-chromium/media/console-example-devtools-separate-console-browse.msft.png "图4：浏览器在单独的窗口中"  
[ImageDevToolsSeparateDevTools]：/microsoft-edge/devtools-guide-chromium/media/console-example-devtools-separate-console-devtools.msft.png "图5：在单独的窗口中取消停靠 DevTools"  
[ImageLogInfo]：/microsoft-edge/devtools-guide-chromium/media/console-log-info.msft.png "图6：单击" 日志信息 "后的控制台"  
[ImageSourceLog]：/microsoft-edge/devtools-guide-chromium/media/console-sources-logjs.msft.png "图7：单击" log.js： 2 "后 DevTools 打开" 源 "面板。  
[ImageConsoleLogWarning]：/microsoft-edge/devtools-guide-chromium/media/console-log-warning.msft.png "图8：单击" 日志警告 "后的控制台"  
[ImageStackTrace]：/microsoft-edge/devtools-guide-chromium/media/console-log-warning-expanded.msft.png "图9：堆栈跟踪"  
[ImageLogError]：/microsoft-edge/devtools-guide-chromium/media/console-log-error.msft.png "图10：错误消息"  
[ImageConsoleTable]：/microsoft-edge/devtools-guide-chromium/media/console-log-table.msft.png "图11：控制台中的表格"  
[ImageConsoleLogGroup]：/microsoft-edge/devtools-guide-chromium/media/console-log-group.msft.png "图12：一组在控制台中的邮件"  
[ImageConsoleLogCustomFormatting]：/microsoft-edge/devtools-guide-chromium/media/console-log-custom.msft.png "图13：在控制台中有自定义格式的邮件"  
[ImageConsoleLogError]：/microsoft-edge/devtools-guide-chromium/media/console-cause-404.msft.png "图14：控制台中的404错误"  
[ImageConsoleLogTypeError]：/microsoft-edge/devtools-guide-chromium/media/console-cause-error.msft.png "图15：控制台中的 TypeError"  
[ImageVerboseLogLevel]：/microsoft-edge/devtools-guide-chromium/media/console-cause-error-log-levels.msft.png "图16：启用详细日志级别"  
[ImageConsoleLogViolation]：/microsoft-edge/devtools-guide-chromium/media/console-cause-violation.msft.png "图17：控制台中的冲突"  
[ImageConsoleDisablingLogError]：/microsoft-edge/devtools-guide-chromium/media/console-cause-violation-log-levels.msft.png "图18：在控制台中禁用错误级别消息"  
[ImageLogTextFiltering]：/microsoft-edge/devtools-guide-chromium/media/console-all-messages-text-filter.msft.png "图19：筛选出不包含 Dave 的任何邮件"  
[ImageLogRegExFiltering]：/microsoft-edge/devtools-guide-chromium/media/console-all-messages-regex-filter.msft.png "图20：筛选出与模式不匹配的任何邮件"  
[ImageConsoleSidebar]：/microsoft-edge/devtools-guide-chromium/media/console-sidebar-all-messages.msft.png "图21：边栏"  
[ImageConsoleSidebarLogSource]：/microsoft-edge/devtools-guide-chromium/media/console-sidebar-expanded-all-messages.msft.png "图22：查看边栏中邮件的来源"  
[ImageConsoleLogBrowserFiltering]：/microsoft-edge/devtools-guide-chromium/media/console-sidebar-user-messages.msft.png "图23：筛选出浏览器消息"  
[ImageDrawerConsole]：/microsoft-edge/devtools-guide-chromium/media/console-elements-drawer-console-sidebar-all-messages.msft.png "图24：抽屉中的控制台" 选项卡  

<!-- links -->  

[MicrosoftEdgeDevTools]: /microsoft-edge/devtools-guide-chromium "Microsoft Edge \ （Chromium \）开发人员工具"  
[DevToolsCommandMenu]: /microsoft-edge/devtools-guide-chromium/command-menu/index "通过 Microsoft Edge DevTools 命令菜单运行命令"  
[DevToolsCustomizePlacement]: /microsoft-edge/devtools-guide-chromium/customize/placement "更改 Microsoft Edge DevTools 位置（"取消停靠"、"停靠到底部"、"停靠到左侧"）"  
[DevToolsConsoleApi]: /microsoft-edge/devtools-guide-chromium/console/api "控制台 API 参考"  
[DevToolsConsoleReference]: /microsoft-edge/devtools-guide-chromium/console/reference "控制台参考"  

[GlitchDevToolsConsoleLogExamples]: https://microsoft-edge-chromium-devtools.glitch.me/static/console/log.html "记录消息入门 |故障"  

[MDNRegularExpressions]: https://developer.mozilla.org/docs/Web/JavaScript/Guide/Regular_Expressions "正则表达式 |MDN"  

[RegExrMain]: https://regexr.com "RegExr"  

[WikiStackTrace]: https://en.wikipedia.org/wiki/Stack_trace "堆栈跟踪-维基百科"  


> [!NOTE]
> 此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/console/log)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools \ & Lighthouse \）创作。  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
