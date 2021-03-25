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
ms.translationtype: HT
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
   **控制台** 中的消息  
:::image-end:::  

本教程旨在按顺序排列。  它假定你了解 Web 开发的基础，例如如何使用 JavaScript 向页面添加交互性。  

## <a name="set-up-the-demo-and-devtools"></a>设置演示和 DevTools  

本教程旨在让你能够打开演示并自己尝试所有工作流。  当你实际遵循此流程时，将更有可能在之后记住该工作流。  

1.  按住 `Control` \(Windows, Linux\) 或 `Command` \(macOS\)，然后选择 **控制台记录示例** 以在新选项卡中打开。  
    
    [控制台日志示例][GlitchDevToolsConsoleLogExamples]
    
    <!--
    > [!TIP]
    > Move the demo to a separate window.  
    > 
    > :::image type="complex" source="../media/log-set-up-1.msft.png" alt-text="The tutorial on the left, and the demo on the right" lightbox="../media/log-set-up-1.msft.png":::
    >    The tutorial on the left, and the demo on the right  
    > :::image-end:::  
    -->
    
1.  关注演示，然后选择 `Control`+`Shift`+`J` \(Windows, Linux\) 或 `Command`+`Option`+`J` \(macOS\) 以打开 DevTools。  默认情况下，DevTools 将在演示的右侧打开。  
    
    :::row:::
       :::column span="":::
          :::image type="complex" source="../media/console-example-devtools-right-console.msft.png" alt-text="DevTools 将在演示右侧打开" lightbox="../media/console-example-devtools-right-console.msft.png":::
             DevTools 将在演示右侧打开  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          > [!TIP]
          > [扩展坞 DevTools 至 窗口底部][DevToolsCustomizePlacement]。  
          
          :::image type="complex" source="../media/console-example-devtools-bottom-console.msft.png" alt-text="DevTools 固定到演示底部" lightbox="../media/console-example-devtools-bottom-console.msft.png":::
             DevTools 固定到演示底部  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    :::row:::
       :::column span="":::
          > [!TIP]
          > [将 DevTools 取消停靠到单独窗口中][DevToolsCustomizePlacement]。  
          
          :::image type="complex" source="../media/console-example-devtools-separate-console-browse.msft.png" alt-text="单独窗口中的浏览器" lightbox="../media/console-example-devtools-separate-console-browse.msft.png":::
             单独窗口中的浏览器  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          > [!TIP]
          > [将 DevTools 取消停靠到单独窗口中][DevToolsCustomizePlacement]。  
          
          :::image type="complex" source="../media/console-example-devtools-separate-console-devtools.msft.png" alt-text="在单独的窗口中取消停靠 DevTools" lightbox="../media/console-example-devtools-separate-console-devtools.msft.png":::
             在单独的窗口中取消停靠 DevTools  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
## <a name="view-messages-logged-from-javascript"></a>查看从 JavaScript 记录的消息  

**控制台**中显示的大多数消息来自编写页面 JavaScript 的 Web 开发人员。  本节的目标是介绍你可能在**控制台**中查看的不同邮件类型，并解释如何从自己的 JavaScript 中自行记录每封邮件类型。  

1.  在演示中选择 **记录信息** 按钮。  `Hello, Console!` 记录到控制台。
    
    :::image type="complex" source="../media/console-log-info.msft.png" alt-text="选择 “记录信息” 后的控制台" lightbox="../media/console-log-info.msft.png":::
       选择 **“记录信息”** 后的 **“控制台”**  
    :::image-end:::  
    
1.  在控制台中的 `Hello, Console!` 消息旁选择 **“log.js:2”**。  将“源”面板打开并突出显示导致消息记录到控制台的代码行。  当页面的 JavaScript 运行 `console.log('Hello, Console!')` 时，会记录下该消息。
    
    :::image type="complex" source="../media/console-sources-logjs.msft.png" alt-text="选择 log.js:2 后，DevTools 打开“源”工具。" lightbox="../media/console-sources-logjs.msft.png":::
       选择后，DevTools 打开 **“源”** 工具 `log.js:2`  
    :::image-end:::  
    
1.  使用下列任何工作流导航回 **控制台** :  
    
    *   选择 **控制台** 工具。  
    *   选择 `Control`+`[` \(Windows, Linux\) 或 `Command`+`[` \(macOS\) 直到 **控制台** 工具成为焦点。  
    *   [打开命令菜单][DevToolsCommandMenu]，键入 `Console`，选择 **显示控制台面板** 命令，然后选择 `Enter`。  
    
1.  在演示中选择 **“记录警告”** 按钮。  `Abandon Hope All Ye Who Enter` 记录到 **控制台**。  像这样格式的邮件是警告。  
    
    :::image type="complex" source="../media/console-log-warning.msft.png" alt-text="选择“记录警告”后的控制台" lightbox="../media/console-log-warning.msft.png":::
       选择 **记录警告** 后的 **控制台**  
    :::image-end:::  
    
    > [!TIP]
    > 如果要显示导致以特定方式记录邮件的代码，请选择脚本 \(如 `log.js:12`\) 以查看导致邮件格式化的代码。  

1.  选择 `Abandon Hope All Ye Who Enter` 前面的 **展开** \(![Expand](../media/expand-icon.msft.png)\) 图标。  DevTools 显示调用前的 [堆栈跟踪][WikiStackTrace]。  
    
    :::image type="complex" source="../media/console-log-warning-expanded.msft.png" alt-text="堆栈跟踪" lightbox="../media/console-log-warning-expanded.msft.png":::
       堆栈跟踪  
    :::image-end:::  
    
    堆栈跟踪会告知你在运行名为 `logWarning` 的函数，而该函数又在运行名为 `quoteDante` 的函数。  换句话说，首先发生的请求位于堆栈跟踪的底部。  随时可能通过运行 `console.trace()` 记录堆栈跟踪。  

1.  选择 **“记录错误”**。  将记录以下错误消息: `I'm sorry, Dave.  I'm afraid I can't do that.`  
    
    :::image type="complex" source="../media/console-log-error.msft.png" alt-text="错误消息" lightbox="../media/console-log-error.msft.png":::
       错误消息  
    :::image-end:::  
    
1.  选择 **“记录表”**。  将有关著名艺术家的表格记录到**控制台**。  
    
    > [!NOTE]
    > `birthday` 列仅填充一行。  查看代码以确定原因。
    
    :::image type="complex" source="../media/console-log-table.msft.png" alt-text="控制台中的表" lightbox="../media/console-log-table.msft.png":::
       **控制台** 中的表  
    :::image-end:::  
    
1.  选择 **“记录组”**。  4 只著名打击犯罪的海龟名字归在 `Adolescent Irradiated Espionage Tortoises` 标签下。  
    
    :::image type="complex" source="../media/console-log-group.msft.png" alt-text="控制台中的一组消息" lightbox="../media/console-log-group.msft.png":::
       **控制台** 中的一组消息  
    :::image-end:::  
    
1.  选择 **“记录自定义”**。  将红色边框和蓝色背景的消息记录到控制台。  
    
    :::image type="complex" source="../media/console-log-custom.msft.png" alt-text="控制台中具有自定义格式的消息" lightbox="../media/console-log-custom.msft.png":::
       **控制台** 中具有自定义格式的消息  
    :::image-end:::  
    
此处的主要理念是，当你希望从 JavaScript 将消息记录到控制台时，请使用 `console` 中的其中一种方法。  每种方法都有不同的信息格式。  

除了本节中演示的方法外，还有更多方法。  本教程介绍如何浏览其余方法。  

## <a name="view-messages-logged-by-the-browser"></a>查看浏览器记录的消息  

浏览器也会将消息记录到控制台。  这种情况通常发生在页面出现问题的时候。  

1.  选择 **“原因 404”**。  浏览器记录 `404` 网络错误的 HTTP 状态代码，因为页面的 JavaScript 尝试获取不存在的文件。  
    
    :::image type="complex" source="../media/console-cause-404.msft.png" alt-text="控制台中出现 404 错误" lightbox="../media/console-cause-404.msft.png":::
       **控制台** 中出现 `404` 错误  
    :::image-end:::  
    
1.  选择 **“原因错误”**。  由于 JavaScript 试图更新不存在的 DOM 节点，浏览器记录了未捕获 `TypeError`。   
    
    :::image type="complex" source="../media/console-cause-error.msft.png" alt-text="控制台中的 TypeError" lightbox="../media/console-cause-error.msft.png":::
       **控制台** 中的 `TypeError`  
    :::image-end:::  
    
1.  选择 **“记录级别”** 下拉列表并启用 **“详细”** 选项(如果已禁用)。  可以在下一节了解更多关于筛选的信息。  需要这样做以确保记录的下一条消息是可见的。  
    
    > [!NOTE]
    > 如果“默认级别”下拉列表处于禁用状态，可能需要关闭 **控制台** 边栏。  通过下面的消息源过滤，以获得更多关于**控制台**侧栏的信息。
    
    :::image type="complex" source="../media/console-cause-error-log-levels.msft.png" alt-text="启用详细日志级别" lightbox="../media/console-cause-error-log-levels.msft.png":::
       启用详细日志级别  
    :::image-end:::  
    
1.  选择 **“原因冲突”**。  页面在几秒钟后将无响应，然后浏览器将消息 `[Violation] 'click' handler took 3000ms` 记录到控制台。  确切的持续时间可能会有所不同。  
    
    :::image type="complex" source="../media/console-cause-violation.msft.png" alt-text="控制台中的冲突" lightbox="../media/console-cause-violation.msft.png":::
       **控制台** 中的冲突  
    :::image-end:::  
    
## <a name="filter-messages"></a>筛选邮件  

在某些网页上，你查看 **控制台** 时会收到大量消息。  DevTools 提供了许多不同的方法来筛选出与当前任务不相关的消息。  

### <a name="filter-by-log-level"></a>按记录级别筛选  

每个 `console` 方法都分配有严重性级别: `Verbose`、`Info`、`Warning` 或 `Error`。  例如，`console.log()` 是 `Info`级邮件，而 `console.error()` 是 `Error`级邮件。  

1.  选择 **“记录级别”** 下拉列表并禁用 **“错误”**。  当一个级别旁边不再有选中标记时，将禁用该级别将。  `Error`级邮件将消失。  
    
    :::image type="complex" source="../media/console-cause-violation-log-levels.msft.png" alt-text="在控制台中禁用错误级邮件" lightbox="../media/console-cause-violation-log-levels.msft.png":::
       在**控制台**中禁用错误级别的邮件  
    :::image-end:::  
    
1.  再次选择 **“记录级别”** 下拉列表，然后重新启用 **“错误”**。  `Error`级消息将重新出现。  

### <a name="filter-by-text"></a>按文本筛选  

当只想查看包含确切字符串的邮件时，在 **“筛选器”** 文本框中键入该字符串。  

1.  键入 `Dave` 到“**筛选器**”文本框。  所有不包含字符串 `Dave` 的邮件都隐藏。  还可以查看 `Adolescent Irradiated Espionage Tortoises` 标签。  这是一个错误。  
    
    :::image type="complex" source="../media/console-all-messages-text-filter.msft.png" alt-text="筛选掉任何不包含 Dave 的邮件" lightbox="../media/console-all-messages-text-filter.msft.png":::
       筛选掉任何不包含的邮件 `Dave`  
    :::image-end:::  
    
1.  从 **“筛选器”** 文本框中删除 `Dave`。  所有邮件都重新出现。  

### <a name="filter-by-regular-expression"></a>按正则表达式筛选  

当你想要显示包含文本模式 (而不是特定字符串) 的所有邮件时，请使用 [正则表达式][MDNRegularExpressions]。  

1.  键入 `/^[AH]/` 到“**筛选器**”文本框。  在 [RegExr 中][|::ref1::|Main] 中键入模式，以说明它正在执行哪些操作。  
    
    :::image type="complex" source="../media/console-all-messages-regex-filter.msft.png" alt-text="筛选出任何与模式不匹配的邮件" lightbox="../media/console-all-messages-regex-filter.msft.png":::
       筛选出与模式不匹配的任何邮件 `/^[AH]/`  
    :::image-end:::  
    
1.  从 **“筛选器”** 文本框中删除 `/^[AH]/`。  所有邮件再次可见。  

### <a name="filter-by-message-source"></a>按邮件源筛选  

如果只想查看来自特定 URL 的邮件，请使用 **边栏**。  

1.  选择 **显示控制台边栏** \ (![ 显示控制器边栏 ](../media/show-console-sidebar-icon.msft.png) \)。  
    
    :::image type="complex" source="../media/console-sidebar-all-messages.msft.png" alt-text="边栏" lightbox="../media/console-sidebar-all-messages.msft.png":::
       边栏  
    :::image-end:::  
    
1.  选择“邮件数”旁边的 **“展开”** \ (![“展开”](../media/expand-icon.msft.png) \)。  在下图中，邮件数指示为 **“13 邮件”**。  **边栏**显示导致记录消息的 URL 列表。  例如， `log.js` 导致 11 条消息。  
    
    :::image type="complex" source="../media/console-sidebar-expanded-all-messages.msft.png" alt-text="在边栏中查看消息源" lightbox="../media/console-sidebar-expanded-all-messages.msft.png":::
       在边栏中查看消息源  
    :::image-end:::  
    
### <a name="filter-by-user-messages"></a>按用户邮件筛选  

此前，当你选择 **“记录信息”** 时，名为 `console.log('Hello, Console!')` 的脚本用于将消息记录到控制台。  像这样从 JavaScript 中记录的消息称为 **“用户消息”**。  相反，当你选择 **“原因 404”** 时，浏览器会记录一条 `Error`级消息，说明未找到所请求的资源。  类似这样的邮件视为 **“浏览器消息”**。  使用 **“边栏”** 筛选掉浏览器消息，并只显示用户消息。  

1.  选择 **“9 个用户消息”**。  浏览器消息处于隐藏状态。  
    
    :::image type="complex" source="../media/console-sidebar-user-messages.msft.png" alt-text="筛选掉浏览器消息" lightbox="../media/console-sidebar-user-messages.msft.png":::
       筛选掉浏览器消息  
    :::image-end:::  
    
1.  选择 **“13 邮件”** 以再次显示所有邮件。  

## <a name="use-the-console-alongside-any-other-tools"></a>与其他工具一起使用控制台  

如果要编辑样式，但需要快速检查控制台日志中的某内容，请使用 “抽屉”。  

1.  选择 **“元素”** 工具。  
1.  选择 `Escape`。  **抽屉** 中的 **控制台** 工具。  它拥有本教程中你一直使用的控制台面板的所有功能。  
    
    :::image type="complex" source="../media/console-elements-drawer-console-sidebar-all-messages.msft.png" alt-text="“抽屉” 中的控制台工具" lightbox="../media/console-elements-drawer-console-sidebar-all-messages.msft.png":::
         **“抽屉”** 中的 **控制台** 工具  
    :::image-end:::  
    
## <a name="see-also"></a>另请参阅  

*   若要浏览更多与 **“控制台** UI” 相关的功能和工作流，请导航到[“控制台参考”][DevToolsConsoleApi]。  
*   若要了解有关 [“查看从 JavaScript 记录的消息”](#view-messages-logged-from-javascript) 中演示的所有 `console` 方法，并浏览本文未涵盖的其他 `console` 方法，请导航到 [“控制台 API 参考”][DevToolsConsoleReference]。  
<!--*   Navigate to [Get Started](/microsoft-edge/devtools-guide-chromium/#start) to explore what else you are able to do with DevTools.  -->  
     
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge 开发工具团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium/index.md "Microsoft Edge \ (Chromium\) 开发人员工具 | Microsoft Docs"  
[DevToolsCommandMenu]: ../command-menu/index.md "使用 Microsoft Edge DevTools 命令菜单菜单运行 | Microsoft Docs"  
[DevToolsCustomizePlacement]: ../customize/placement.md "更改 Microsoft Edge DevTools 放置 | Microsoft Docs"  
[DevToolsConsoleApi]: ./api.md "控制台 API 参考 | Microsoft Docs"  
[DevToolsConsoleReference]: ./reference.md "控制台参考 | Microsoft Docs"  

[GlitchDevToolsConsoleLogExamples]: https://microsoft-edge-chromium-devtools.glitch.me/static/console/log.html "记录消息入门 | 故障"  

[MDNRegularExpressions]: https://developer.mozilla.org/docs/Web/JavaScript/Guide/Regular_Expressions "正则表达式 | MDN"  

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
