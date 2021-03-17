---
description: 了解如何将消息记录到控制台。
title: 开始在控制台中记录消息
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: fb428154b00959db1627096819c565dd5dc11346
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439287"
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

# <a name="get-started-with-logging-messages-in-the-console"></a>开始在控制台中记录消息  

此交互式教程介绍如何在 [Microsoft Edge DevTools][MicrosoftEdgeDevTools] 控制台中记录并筛选消息。  

:::image type="complex" source="../media/console-ars-technica-console-onload.msft.png" alt-text="控制台中的消息" lightbox="../media/console-ars-technica-console-onload.msft.png":::
   控制台中的 **消息**  
:::image-end:::  

本教程旨在按顺序排列。  它假定你了解 Web 开发的基础，例如如何使用 JavaScript 向页面添加交互性。  

## <a name="set-up-the-demo-and-devtools"></a>设置演示和 DevTools  

本教程旨在让你能够打开演示并自己尝试所有工作流。  当您实际遵循此流程时，您以后更有可能会记住工作流。  

1.  按住 `Control` \ (Windows、Linux\) 或 `Command` \ (macOS\) **** 并选择"控制台日志示例"以在新选项卡中打开。  
    
    [控制台日志示例][GlitchDevToolsConsoleLogExamples]
    
    <!--
    > [!TIP]
    > Move the demo to a separate window.  
    > 
    > :::image type="complex" source="../media/log-set-up-1.msft.png" alt-text="The tutorial on the left, and the demo on the right" lightbox="../media/log-set-up-1.msft.png":::
    >    The tutorial on the left, and the demo on the right  
    > :::image-end:::  
    -->
    
1.  关注演示，然后选择 `Control` + `Shift` + `J` \ (Windows、Linux\) 或 `Command` + `Option` + `J` \ (macOS\) 打开 DevTools。  默认情况下，DevTools 将在演示的右侧打开。  
    
    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/console-example-devtools-right-console.msft.png" alt-text="DevTools 将在演示右侧打开" lightbox="../media/console-example-devtools-right-console.msft.png":::
             DevTools 将在演示右侧打开  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          > [!TIP]
          > [窗口底部的扩展坞 DevTools。][DevToolsCustomizePlacement]  
          
          :::image type="complex" source="../media/console-example-devtools-bottom-console.msft.png" alt-text="DevTools 固定到演示底部" lightbox="../media/console-example-devtools-bottom-console.msft.png":::
             DevTools 固定到演示底部  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    :::row:::
       :::column span="":::
          > [!TIP]
          > [将 DevTools 撤消到单独的窗口中][DevToolsCustomizePlacement]。  
          
          :::image type="complex" source="../media/console-example-devtools-separate-console-browse.msft.png" alt-text="单独窗口中的浏览器" lightbox="../media/console-example-devtools-separate-console-browse.msft.png":::
             单独窗口中的浏览器  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          > [!TIP]
          > [将 DevTools 撤消到单独的窗口中][DevToolsCustomizePlacement]。  
          
          :::image type="complex" source="../media/console-example-devtools-separate-console-devtools.msft.png" alt-text="在单独的窗口中取消停靠的 DevTools" lightbox="../media/console-example-devtools-separate-console-devtools.msft.png":::
             在单独的窗口中取消停靠的 DevTools  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
## <a name="view-messages-logged-from-javascript"></a>查看从 JavaScript 记录的消息  

控制台中显示的大多数消息来自编写页面**** JavaScript 的 Web 开发人员。  本节的目的是介绍您可能在控制台中查看的不同邮件类型，并说明如何从自己的 JavaScript 自行记录**** 每封邮件类型。  

1.  在演示 **中选择** "日志信息"按钮。  `Hello, Console!` 记录到控制台。
    
    :::image type="complex" source="../media/console-log-info.msft.png" alt-text="选择"日志信息"后的控制台" lightbox="../media/console-log-info.msft.png":::
       选择 **"** 日志信息 **"后的控制台**  
    :::image-end:::  
    
1.  在控制台中 `Hello, Console!` 的消息旁边，选择 **"log.js：2"。**  "源"面板将打开并突出显示导致消息记录到控制台的代码行。  当页面的 JavaScript 运行 时，会记录该消息 `console.log('Hello, Console!')` 。
    
    :::image type="complex" source="../media/console-sources-logjs.msft.png" alt-text="选择"源"工具后，DevTools 将打开log.js：2" lightbox="../media/console-sources-logjs.msft.png":::
       选择后，DevTools **将** 打开"源"工具 `log.js:2`  
    :::image-end:::  
    
1.  使用下列任何 **工作流** 导航回控制台：  
    
    *   选择 **控制台** 工具。  
    *   选择 `Control` + `[` \ (Windows、Linux\) 或 `Command` + `[` \ (macOS\) 直到控制台工具成为焦点。 ****  
    *   [打开命令菜单，][DevToolsCommandMenu]键入 `Console` ，选择显示 **控制台面板** 命令，然后选择 `Enter` 。  
    
1.  在演示 **中选择** "日志警告"按钮。  `Abandon Hope All Ye Who Enter` 记录到 **控制台**。  如下所示的邮件是警告。  
    
    :::image type="complex" source="../media/console-log-warning.msft.png" alt-text="选择"日志警告"后的控制台" lightbox="../media/console-log-warning.msft.png":::
       选择 **"** 日志警告"后的 **控制台**  
    :::image-end:::  
    
    > [!TIP]
    > 如果要显示导致以特定方式记录消息的代码，请选择脚本 \ (如 \) 以查看导致邮件格式化的代码 `log.js:12` 。  

1.  选择前面的 **展开** \ (展开 ![ ](../media/expand-icon.msft.png) \) 图标 `Abandon Hope All Ye Who Enter` 。  DevTools 显示 [调用][WikiStackTrace] 前导的堆栈跟踪。  
    
    :::image type="complex" source="../media/console-log-warning-expanded.msft.png" alt-text="堆栈跟踪" lightbox="../media/console-log-warning-expanded.msft.png":::
       堆栈跟踪  
    :::image-end:::  
    
    堆栈跟踪会告知你，名为 `logWarning` 的函数运行，而该函数又运行名为 的函数 `quoteDante` 。  换句话说，首先发生的请求位于堆栈跟踪的底部。  你随时可能通过运行 记录堆栈跟踪 `console.trace()` 。  

1.  选择 **"日志错误"。**  将记录以下错误消息： `I'm sorry, Dave.  I'm afraid I can't do that.`  
    
    :::image type="complex" source="../media/console-log-error.msft.png" alt-text="错误消息" lightbox="../media/console-log-error.msft.png":::
       错误消息  
    :::image-end:::  
    
1.  选择 **"日志表"。**  有关艺术家的表将被记录到**控制台。**  
    
    > [!NOTE]
    > 仅为 `birthday` 一行填充该列。  查看代码以确定原因。
    
    :::image type="complex" source="../media/console-log-table.msft.png" alt-text="控制台中的表" lightbox="../media/console-log-table.msft.png":::
       控制台中的 **表**  
    :::image-end:::  
    
1.  选择 **"日志组"。**  4 个动物、反犯罪团体的名称在标签下 `Adolescent Irradiated Espionage Tortoises` 分组。  
    
    :::image type="complex" source="../media/console-log-group.msft.png" alt-text="控制台中的一组消息" lightbox="../media/console-log-group.msft.png":::
       控制台中的一组 **消息**  
    :::image-end:::  
    
1.  选择 **"日志自定义"。**  将红色边框和蓝色背景的消息记录到控制台。  
    
    :::image type="complex" source="../media/console-log-custom.msft.png" alt-text="控制台中具有自定义格式的消息" lightbox="../media/console-log-custom.msft.png":::
       控制台中具有自定义格式 **的消息**  
    :::image-end:::  
    
此处的主要理念是，当您希望从 JavaScript 将消息记录到控制台时，请使用其中一 `console` 种方法。  每个方法对邮件的格式都不同。  

除了本节中演示的方法外，还有更多方法。  本教程介绍如何浏览其余方法。  

## <a name="view-messages-logged-by-the-browser"></a>查看浏览器记录的消息  

浏览器将消息记录到控制台。  当页面出现问题时，通常会发生这种情况。  

1.  选择 **"原因 404"。**  浏览器记录网络错误的 HTTP 状态代码， `404` 因为页面的 JavaScript 尝试获取不存在的文件。  
    
    :::image type="complex" source="../media/console-cause-404.msft.png" alt-text="控制台中出现 404 错误" lightbox="../media/console-cause-404.msft.png":::
       控制台 `404` 中的 **错误**  
    :::image-end:::  
    
1.  选择 **"原因错误"。**  浏览器未记录，因为 JavaScript 尝试更新不存在的 `TypeError` DOM 节点。  
    
    :::image type="complex" source="../media/console-cause-error.msft.png" alt-text="控制台中的 TypeError" lightbox="../media/console-cause-error.msft.png":::
       控制台 `TypeError` 中的**** A  
    :::image-end:::  
    
1.  选择" **日志级别** "下拉列表并启用" **详细"** 选项（如果已禁用）。  您可以在下一节中了解有关筛选功能的内容。  需要这样做以确保所记录的下一条消息可见。  
    
    > [!NOTE]
    > 如果"默认级别"下拉列表处于禁用状态，可能需要关闭 **控制台** 边栏。  按下面的消息源筛选，了解有关控制台边 **栏** 的详细信息。
    
    :::image type="complex" source="../media/console-cause-error-log-levels.msft.png" alt-text="启用详细日志级别" lightbox="../media/console-cause-error-log-levels.msft.png":::
       启用详细日志级别  
    :::image-end:::  
    
1.  选择 **"原因冲突"。**  页面在几秒钟后将无响应，然后浏览器将消息记录 `[Violation] 'click' handler took 3000ms` 到控制台。  确切的持续时间可能会有所不同。  
    
    :::image type="complex" source="../media/console-cause-violation.msft.png" alt-text="控制台中的冲突" lightbox="../media/console-cause-violation.msft.png":::
       控制台中的 **冲突**  
    :::image-end:::  
    
## <a name="filter-messages"></a>筛选邮件  

在某些网页上，你查看 **控制台** 时收到大量消息。  DevTools 提供了许多不同的方法来筛选出与当前任务不相关的消息。  

### <a name="filter-by-log-level"></a>按日志级别筛选  

每个 `console` 方法都分配有严重性级别 `Verbose` `Info` ：、、或 `Warning` `Error` 。  例如， `console.log()` 是 `Info` -level 邮件， `console.error()` 而 是 `Error` -level 邮件。  

1.  选择"**日志级别**"下拉列表并禁用 **"错误"。**  当一个级别旁边不再有选中标记时，该级别将被禁用。  `Error`-level 消息将消失。  
    
    :::image type="complex" source="../media/console-cause-violation-log-levels.msft.png" alt-text="在控制台中禁用错误级别的消息" lightbox="../media/console-cause-violation-log-levels.msft.png":::
       在控制台中禁用错误级别 **的消息**  
    :::image-end:::  
    
1.  再次**选择"日志**级别"下拉列表，然后重新启用 **"错误"。**  `Error`-level 消息将重新出现。  

### <a name="filter-by-text"></a>按文本筛选  

当只想查看包含确切字符串的邮件时，在"筛选器"文本框中 **键入该字符串** 。  

1.  键入 `Dave` 到“**筛选器**”文本框。  所有不包含字符串的邮件 `Dave` 都隐藏。  还可以查看 `Adolescent Irradiated Espionage Tortoises` 标签。  这是一个错误。  
    
    :::image type="complex" source="../media/console-all-messages-text-filter.msft.png" alt-text="筛选掉不包含 Dave 的任何邮件" lightbox="../media/console-all-messages-text-filter.msft.png":::
       筛选掉任何不包含的邮件 `Dave`  
    :::image-end:::  
    
1.  从 `Dave` " **筛选器"文本框** 中删除。  所有邮件都重新出现。  

### <a name="filter-by-regular-expression"></a>按正则表达式筛选  

当您想要显示包含文本模式（而不是特定字符串）的所有邮件时，请使用 [正则表达式][MDNRegularExpressions]。  

1.  键入 `/^[AH]/` 到“**筛选器**”文本框。  在 [RegExr 中][|::ref1::|Main] 键入模式，以说明它正在执行哪些操作。  
    
    :::image type="complex" source="../media/console-all-messages-regex-filter.msft.png" alt-text="筛选出任何与模式不匹配的邮件" lightbox="../media/console-all-messages-regex-filter.msft.png":::
       筛选出与模式不匹配的任何邮件 `/^[AH]/`  
    :::image-end:::  
    
1.  从 `/^[AH]/` " **筛选器"文本框** 中删除。  所有邮件再次可见。  

### <a name="filter-by-message-source"></a>按邮件源筛选  

如果只想查看来自特定 URL 的邮件，请使用 **边栏**。  

1.  Choose **Show Console Sidebar** \ (![ Show Console Sidebar ](../media/show-console-sidebar-icon.msft.png) \) .  
    
    :::image type="complex" source="../media/console-sidebar-all-messages.msft.png" alt-text="边栏" lightbox="../media/console-sidebar-all-messages.msft.png":::
       边栏  
    :::image-end:::  
    
1.  选择" **展开** \ (![ 展开 ](../media/expand-icon.msft.png) \) "图标旁边的"邮件数"。  在下图中，邮件数指示为 **"13 邮件"。**  **边栏**显示导致记录消息的 URL 列表。  例如， `log.js` 导致 11 条消息。  
    
    :::image type="complex" source="../media/console-sidebar-expanded-all-messages.msft.png" alt-text="在边栏中查看消息源" lightbox="../media/console-sidebar-expanded-all-messages.msft.png":::
       在边栏中查看消息源  
    :::image-end:::  
    
### <a name="filter-by-user-messages"></a>按用户消息筛选  

之前，当你选择"日志 **信息**"时，名为 `console.log('Hello, Console!')` 的脚本用于将消息记录到控制台。  从 JavaScript 中记录的消息（如下所示）称为 **用户消息**。  相反，当你选择 **"原因 404"** 时，浏览器会记录一条 -level 消息，指出未找到请求 `Error` 的资源。  类似这样的邮件被视为 **浏览器消息**。  使用 **边栏筛选** 掉浏览器消息，并只显示用户消息。  

1.  选择 **"9 个用户消息"。**  浏览器消息处于隐藏状态。  
    
    :::image type="complex" source="../media/console-sidebar-user-messages.msft.png" alt-text="筛选掉浏览器消息" lightbox="../media/console-sidebar-user-messages.msft.png":::
       筛选掉浏览器消息  
    :::image-end:::  
    
1.  选择 **"13 邮件"** 可再次显示所有邮件。  

## <a name="use-the-console-alongside-any-other-tools"></a>将控制台与任何其他工具一同使用  

如果要编辑样式，但需要快速检查控制台日志中的某内容，请使用"箱"。  

1.  选择" **元素"** 工具。  
1.  选择 `Escape`。  将 **打开** "箱" **中的控制台** 工具。  它拥有你在整个教程中一直使用的控制台面板的所有功能。  
    
    :::image type="complex" source="../media/console-elements-drawer-console-sidebar-all-messages.msft.png" alt-text=""箱"中的控制台工具" lightbox="../media/console-elements-drawer-console-sidebar-all-messages.msft.png":::
         " **箱** "中的控制台 **工具**  
    :::image-end:::  
    
## <a name="see-also"></a>另请参阅  

*   若要浏览更多与控制台**UI**相关的功能和工作流，请导航到"控制台[参考"。][DevToolsConsoleApi]  
*   若要了解有关查看从 JavaScript 记录的消息中演示的所有方法，并浏览本文未涵盖的其他方法，请导航到"控制台 API 参考 `console` [](#view-messages-logged-from-javascript) `console` ["。][DevToolsConsoleReference]  
<!--*   Navigate to [Get Started](/microsoft-edge/devtools-guide-chromium/#start) to explore what else you are able to do with DevTools.  -->  
     
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge 开发工具团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge \ (Chromium\) 开发人员工具|Microsoft Docs"  
[DevToolsCommandMenu]: ../command-menu/index.md "使用 Microsoft Edge DevTools 命令菜单菜单运行|Microsoft Docs"  
[DevToolsCustomizePlacement]: ../customize/placement.md "更改 Microsoft Edge DevTools 放置 | Microsoft Docs"  
[DevToolsConsoleApi]: ./api.md "控制台 API 参考|Microsoft Docs"  
[DevToolsConsoleReference]: ./reference.md "控制台参考|Microsoft Docs"  

[GlitchDevToolsConsoleLogExamples]: https://microsoft-edge-chromium-devtools.glitch.me/static/console/log.html "记录消息记录|小故障"  

[MDNRegularExpressions]: https://developer.mozilla.org/docs/Web/JavaScript/Guide/Regular_Expressions "正则表达式|MDN"  

[RegExrMain]: https://regexr.com "RegExr"  

[WikiStackTrace]: https://en.wikipedia.org/wiki/Stack_trace "堆栈跟踪 - Wikipedia"  
> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/console/log)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
