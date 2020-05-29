---
description: 了解 Microsoft Edge （Chromium）开发工具
title: Microsoft Edge （Chromium）开发人员工具
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/28/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 0034e23885020aae5047c69219bd51235a5882b0
ms.sourcegitcommit: a5392ab44133d742c0e1fa500ad9a872989b7c3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/28/2020
ms.locfileid: "10684683"
---
# Microsoft Edge （Chromium）开发人员工具  

Microsoft Edge 采用了 Chromium open 源项目以创建更好的 web 兼容性，并减少不同基础 web 平台的碎片。  此更改使你能够更轻松地在 Microsoft Edge 中构建和测试你的网站，并确保每个网站在不同的基于 Chromium 的浏览器（如 Google Chrome、Vivaldi、Opera 或 Brave \）中查看时都按预期方式工作。  

随着网络在不断扩大的各种设备类型数组中的使用日益增加，测试网站所涉及的复杂性和开销也随之增加。 由于 web 开发人员（尤其是小型公司的用户）必须对很多不同的系统进行测试，因此你可能会发现几乎无法确保网站在所有设备类型和所有浏览器上都能正常工作。  既然 Microsoft Edge 基于 Chromium，Microsoft Edge 团队通过将 Microsoft Edge web 平台与其他基于 Chromium 的浏览器相协调，并在浏览器中和你每天使用的其他开发人员工具（如 Visual Studio 代码 \）中提供了一流的开发工具体验来简化了矩阵。  

如果您要签出 Microsoft Edge，并且主要是在基于 Chromium 的浏览器中开发，则应立即体验。  Microsoft Edge \ （Chromium \）开发人员工具的工作方式与你已了解和使用的开发人员工具相同。  有关详细信息，请参阅[Microsoft Edge （Chromium） DevTools 中的新增功能][DevtoolsGuideChromiumWhatsNewIndex]。  

:::image type="complex" source="./devtools-guide-chromium/media/devtools.png" alt-text="Microsoft Edge （Chromium） DevTools":::
   Microsoft Edge （Chromium） DevTools
:::image-end:::

如果你要签出下一版本的 Microsoft Edge，并且以前是在 Microsoft Edge \ （EdgeHTML \）中开发的，则你现在具有一些非常好的新工具，可让你在 Microsoft Edge 中更轻松、更快地构建和测试网站！  

## 打开 DevTools  

如果您以前从未使用过 DevTools，则 Microsoft Edge 开发人员工具是一组直接内置于 Microsoft Edge 浏览器中的工具。  通过这些 DevTools，你可以执行以下操作。  
*   检查并对 HTML 网站进行更改  
*   编辑 CSS 并立即查看预览您的网站呈现方式  
*   查看 `console.log()` 前端 JavaScript 代码中的所有语句  
*   通过设置断点并逐行逐行执行调试来调试你的脚本  

直接在浏览器中。  以下是 DevTools 提供的一些功能的示例，可使你在 Microsoft Edge 中构建和测试网站变得更加轻松快捷。  

打开 DevTools  
*   按 `F12` 
*   按 `Ctrl` + `Shift` + `I` Windows \ （ `Command` + `Option` + `I` 在 macOS \）上  

如果要查看网站上某个元素的 HTML 或 CSS，请右键单击该元素，然后选择 "**检查**" 以跳转到 "元素" 面板。  你还可以按 `Ctrl` + `Shift` + `C` Windows \ （ `Command` + `Option` + `C` 在 macOS \）上打开 "**检查元素" 模式**中的 DevTools，该模式允许你在网站上选择元素并在 "**元素**" 面板中查看 HTML 和 CSS。  

如果你想要查看前端 JavaScript 代码中的日志或快速运行某些脚本，请按 `Ctrl` + `Shift` + `J` Windows \ （ `Command` + `Option` + `J` 在 macOS \）上启动 DevTools 中的控制台面板。  

## 核心工具  

:::image type="complex" source="./devtools-guide-chromium/media/devtools-core-tools.png" alt-text="Microsoft Edge （Chromium） DevTools 核心工具":::
   Microsoft Edge （Chromium） DevTools 核心工具
:::image-end:::

Microsoft Edge \ （Chromium \） DevTools 包括以下面板。  
*   "**元素**" 面板，用于编辑 HTML 和 CSS、检查辅助功能属性、查看事件侦听器和设置 DOM 转变断点  
*   用于查看和筛选日志消息、检查 JavaScript 对象和 DOM 节点以及在所选窗口或框架的上下文中运行 JavaScript 的**控制台**  
*   一个 "**源**" 面板，用于打开和实时编辑代码、设置断点、单步执行代码以及查看网站的状态一次 JavaScript 的每一行 JavaScript  
*   用于监视和检查来自网络和浏览器缓存的请求和响应的**网络**面板   
*   用于分析你的网站所需的时间和系统资源的**性能**面板  
*   测量内存资源使用情况和比较不同状态的代码运行时中的堆快照的**内存**面板  
*   用于检查、修改和调试 web 应用清单、服务工作人员和服务工作人员缓存的**应用程序**面板。  您也可以从 "**应用程序**" 面板中检查和管理存储、数据库和缓存。  
*   用于调试安全问题的**安全**面板，并确保你在网站上正确实现了 HTTPS。  HTTPS 为您的网站和用户提供网站上提供个人信息的重要安全和数据完整性。  
*   **审核**面板 \ （现已重命名为**Lighthouse**\）运行网站审核。  审核结果可帮助你通过以下方式改善网站的质量。  
    *   捕获与使网站易于访问、安全、性能等相关的常见错误。  
    *   修复每个错误。  
    *   构建 PWA。  

[!INCLUDE [audits-panel-note](./devtools-guide-chromium/includes/audits-panel-note.md)]  

请发送您的[反馈和功能请求](#getting-in-touch-with-the-microsoft-edge-devtools-team)！  

## Extensions  

你可能已使用 DevTools 的扩展，可帮助你在构建网站或应用时诊断和调试问题。  你可以从[Microsoft Edge Addons][MicrosoftEdgeAddonsExtensions]页面获取 microsoft edge 的扩展。  从 " [Microsoft Edge Addons][MicrosoftEdgeAddonsExtensions] " 页面中，您可以从 "**开发工具**" 类别中浏览 DevTools 扩展或搜索特定的扩展名。  

您也可以添加[Chrome Web 应用商店][GoogleChromeWebstoreExtensions]的扩展。  

:::image type="complex" source="./devtools-guide-chromium/media/allow-extensions-from-stores.png" alt-text="Microsoft Edge 中的 Chrome Web Store":::
   Microsoft Edge 中的 Chrome Web Store
:::image-end:::

在顶部，选择 "**允许其他存储中的扩展**"，然后在出现的对话框中选择 "**允许**"。  

> [!NOTE]
> 从 Microsoft Store 以外的源安装的扩展未验证，可能会影响浏览器性能。  

选择 "**添加到 Chrome** " 以将你的 DevTools 扩展添加到 Microsoft Edge！  

:::image type="complex" source="./devtools-guide-chromium/media/install-extension-from-chrome-store.png" alt-text="将 Chrome Web Store 中的扩展添加到 Microsoft Edge":::
   将 Chrome Web Store 中的扩展添加到 Microsoft Edge
:::image-end:::

## 指向  

这些快捷方式控制主 DevTools 窗口，可在所有工具上工作，也可以同时使用这两者。  

| 操作 | Windows | macOS |  
|:--- |:--- | :--- |  
| 显示/隐藏 DevTools \ （打开上次查看的面板 \） | `F12` 或`Ctrl`+`Shift`+`I` | `Command`+`Option`+`I` |  
| 显示控制台面板 | `Ctrl`+`Shift`+`J` | `Command`+`Option`+`J` |  
| 在 "**检查元素" 模式下**显示 DevTools，使你可以在网站上选择元素并在 "**元素**" 面板中查看 HTML 和 CSS | `Ctrl`+`Shift`+`C` | `Command`+`Option`+`C` |  
| 显示设置 | `?` 或`Fn`+`F1` | `?` 或`Fn`+`F1` |  
| 显示下一个面板 | `Ctrl`+`]` | `Command`+`]` |  
| 显示上一个面板 | `Ctrl`+`[` | `Command`+`[` |  
| 将 DevTools 固定在最后一个所用位置。  如果 DevTools 保留在整个会话的默认位置，此快捷方式会将 DevTools 取消停靠到一个单独的窗口中 | `Ctrl`+`Shift`+`D` | `Command`+`Shift`+`D` |  
| 切换**设备模式** | `Ctrl`+`Shift`+`M` | `Command`+`Shift`+`M` |  
| 切换 "**检查元素" 模式**，使您可以选择网站上的元素并在 "**元素**" 面板中查看 HTML 和 CSS | `Ctrl`+`Shift`+`C` | `Command`+`Shift`+`C` |  
| 显示命令菜单 | `Ctrl`+`Shift`+`P` | `Command`+`Shift`+`P` |  
| 显示/隐藏抽屉 | `Esc` | `Esc` |  
| 恢复.  这将刷新使用缓存的页面。  | `F5` 或`Ctrl`+`R` | `Command`+`R` |  
| 硬刷新。  这会强制 Microsoft Edge 再次下载资源并重新加载。  已使用的资源可能来自缓存的版本 | `Ctrl`+`F5`或`Ctrl`+`Shift`+`R` | `Command`+`Shift`+`R` |  
| 在当前面板中搜索文本。  在 "审核"、"应用程序" 和 "安全" 面板中不受支持 | `Ctrl`+`F` | `Command`+`F` |  
| 在抽屉中显示 "搜索" 面板，用于在所有已加载的资源中搜索文本 | `Ctrl`+`Shift`+`F` | `Command`+`Option`+`F` |  
| 在 "源" 面板中打开文件 | `Ctrl`+`O`或`Ctrl`+`P` | `Command`+`O`或`Command`+`P` |  
| 放大 | `Ctrl`+`Shift`+`+` | `Command`+`Shift`+`+` |  
| 缩小 | `Ctrl`+`-` | `Command`+`-` |  
| 还原默认缩放级别 | `Ctrl`+`0` | `Command`+`0` |  
| 运行代码段 | `Ctrl`+`O`或者 `Ctrl` + `P` ，键入 `!` 后跟脚本的名称，然后按 `Enter` | 按 `Command` + `O` 或 `Command` + `P` ，然后键入 `!` 脚本名称，然后按 `Enter` |  
| 在新选项卡中显示不可编辑的 HTML 源代码 | `Ctrl`+`U` | 不适用 |  

> [!NOTE]
> 如果在断点处调试和暂停，**刷新**快捷方式将首先恢复运行时。  

## 另请参阅  

*   [初学者的 DevTools： HTML 和 DOM 入门][DevtoolsGuideChromiumBeginnersHtml]  
*   [Microsoft Edge （Chromium） DevTools 协议][DevtoolsProtocolChromiumIndex]  

## 与 Microsoft Edge DevTools 团队取得联系  

请发送您的反馈，让 Microsoft Edge 团队继续为您改进 Microsoft Edge DevTools！  只需在 DevTools 中选择 "**反馈**" 图标或按 `Alt` + `Shift` + `I` Windows \ （ `Option` + `Shift` + `I` 在 macOS \）上，然后输入针对 DevTools 的任何反馈或功能请求。  

:::image type="complex" source="./devtools-guide-chromium/media/devtools-feedback.png" alt-text="提供有关 Microsoft Edge 的反馈":::
   提供有关 Microsoft Edge 的反馈
:::image-end:::

如果你想要预览 DevTools 中的[最新功能][DevtoolsGuideChromiumWhatsNewIndex]，请下载[Microsoft Edge][MicrosoftedgeinsiderDownload]未安装，它将在夜间生成。  

<!-- image links -->  

<!-- links -->  

[DevtoolsGuideChromiumBeginnersHtml]: /microsoft-edge/devtools-guide-chromium/beginners/html "初学者的 DevTools： HTML 和 DOM 入门 |Microsoft 文档"  
[DevtoolsGuideChromiumWhatsNewIndex]: /microsoft-edge/devtools-guide-chromium/whats-new/2020/05/devtools "Microsoft Edge 中的新增功能（Chromium） DevTools |Microsoft 文档"  
[DevtoolsProtocolChromiumIndex]: /microsoft-edge/devtools-protocol-chromium "Microsoft Edge （Chromium） DevTools 协议 |Microsoft 文档"  

[MicrosoftEdgeAddonsExtensions]: https://microsoftedge.microsoft.com/addons/category/Edge-Extensions "Microsoft Edge 加载项"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "下载 Microsoft Edge 预览体验成员频道"  

[GoogleChromeWebstoreExtensions]: https://chrome.google.com/webstore/category/extensions "扩展名 |Chrome Web Store"  
