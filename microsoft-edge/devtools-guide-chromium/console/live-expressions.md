---
description: 如果发现自己在控制台中重复键入相同的JavaScript表达式，请尝试使用动态表达式。
title: 使用 Live Expressions 实时观看 JavaScript 表达式值
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/13/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 51b7aa5119775f43861a84c1055ac9149a626d8a
ms.sourcegitcommit: 2e516a92272e38d8073603f860ae49f944718670
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "11483119"
---
# <a name="monitor-changes-in-javascript-using-live-expressions"></a>使用 Live Expressions 监视 JavaScript 中的更改  

**实时表达式** 是监视进行大量更改的 JavaScript 表达式的一种很好的方法。    你可以将特定 JavaScript 表达式固定到控制台的顶部，而不是使许多控制台消息阅读和 **导航**。  

## <a name="add-a-new-live-expression"></a>添加新实时表达式  

To start， choose the **Create live expression** \(eye\) button next to the **Filter** textbox.  选择它后，将显示一个文本框，供您在文本框中输入新表达式。  

:::image type="complex" source="../media/console-live-expressions-new.msft.png" alt-text="选择"新建实时表达式"按钮以打开文本框以键入表达式" lightbox="../media/console-live-expressions-new.msft.png":::
    选择 `New live expression` 按钮以打开文本框以键入表达式  
:::image-end:::  

**Live Expressions** 可能是任何有效的 JavaScript 表达式。  若要尝试，请完成以下操作。  

1.  打开 **Live Expression** 文本框。  
1.  键入 `document.activeElement`。  
1.  若要保存表达式，请完成以下操作之一。  
    *   选择 `Control`+`Enter`（Windows、Linux）或 `Command`+`Enter` (macOS)。  
    *   在 **"Live Expression"文本框之外** 选择。  
        
表达式现在为活动表达式， `body` 并显示为结果。  

:::image type="complex" source="../media/console-live-expressions-document-active-element.msft.png" alt-text="document.activeElement 实时表达式将正文显示为结果" lightbox="../media/console-live-expressions-document-active-element.msft.png":::
    结果中 `document.activeElement` 显示正文的 Live 表达式  
:::image-end:::  

如果在网页中导航，值将发生更改。  例如，在下图中，在网页中打开搜索菜单，表达式现在 `button.nav-bar-button.focus-visible` 显示为值。  

:::image type="complex" source="../media/console-live-expressions-document-active-element-nav-button.msft.png" alt-text="若要更改 Live Expression 的值，请与网页上的不同元素交互" lightbox="../media/console-live-expressions-document-active-element-nav-button.msft.png":::
    若要更改 **Live Expression 的值，** 请与网页上的不同元素交互  
:::image-end:::  

若要再次更改该值，请打开并选择网页上的"搜索"文本框。  

:::image type="complex" source="../media/console-live-expressions-document-active-element-search.msft.png" alt-text="导航到网页中的不同元素以更新 Live Expression" lightbox="../media/console-live-expressions-document-active-element-search.msft.png":::
    导航到网页中的不同元素以更新 Live **Expression**  
:::image-end:::  

## <a name="remove-live-expressions"></a>删除 Live Expressions  

只要 **使 Live Expression** 保持活动状态，该表达式就可用。  若要删除 Live **Expression，** 请选择它的 `x` 旁边。  

:::image type="complex" source="../media/console-live-expressions-remove.msft.png" alt-text="若要删除 Live Expressions，请选择其旁边的 x" lightbox="../media/console-live-expressions-remove.msft.png":::
    若要删除 **Live Expressions，** 请选择 `x` 其旁边的  
:::image-end:::  

## <a name="replace-console-logging-with-live-expressions"></a>将控制台日志记录替换为 Live Expressions  

您可以创建多个表达式，并跨浏览器会话和窗口保留每个表达式。  **实时** 表达式是一种减少调试工作流中的噪音的方法。  

例如，您希望监视当前网页中的鼠标移动。  导航到 ["记录鼠标移动][GithubMicrosoftedgeDevtoolssamplesConsoleMousemoveHtml]"演示，打开 **控制台**，并四处移动鼠标以显示包含大量信息的日志。  

:::image type="complex" source="../media/console-live-expression-mouse-logging.msft.png" alt-text="控制台显示有关鼠标位置的很多信息" lightbox="../media/console-live-expression-mouse-logging.msft.png":::
    **控制台** 显示有关鼠标位置的很多信息  
:::image-end:::  

大量信息不仅会减慢调试过程，还易于错过想要查看的更改。  当 **控制台** 显示更多消息并移动鼠标时，你想要查看的值将滚动到屏幕上。  

若要尝试 **Live Expressions** 作为替代方法，请完成以下操作。  

1.  导航到鼠标 [移动而不记录演示][GithubMicrosoftedgeDevtoolssamplesConsoleMouseNoLogHtml]。  
1.  为 和 创建 **Live** `x` `y` Expressions。  
    
使用**Live Expressions 时**，始终在屏幕的相同部分获取信息，并保留控制台**** 日志，查看不会更改太多值。

:::image type="complex" source="../media/console-live-expressions-x-and-y.msft.png" alt-text="将鼠标的 x 和 y 位置显示为 Live Expressions" lightbox="../media/console-live-expressions-x-and-y.msft.png":::
    将 `x` 鼠标 `y` 的 和 位置显示为 Live **Expressions**  
:::image-end:::  

**Live Expressions** 以独占方式在计算机上运行，无需更改代码中要显示任何内容。  **实时** 表达式是确保您仅显示要调试的信息的一种很好的方法。  此外 **，Live Expressions** 还可帮助您限制用户计算机上的噪音。

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge DevTools 团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[GithubMicrosoftedgeDevtoolssamplesConsoleMousemoveHtml]: https://microsoftedge.github.io/DevToolsSamples/console/mousemove.html "控制台消息示例：使用表|GitHub"  
[GithubMicrosoftedgeDevtoolssamplesConsoleMouseNoLogHtml]: https://microsoftedge.github.io/DevToolsSamples/console/mousemove-no-log.html "无需日志记录即可移动鼠标|GitHub"  
