---
description: 了解 Microsoft Edge (Chromium) 开发人员工具
title: Microsoft Edge (Chromium) 开发人员工具
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/09/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: fcae8f0974244e87ba781b94221cb5d8a1bb3dce
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232052"
---
# Microsoft Edge (Chromium) 开发人员工具概述  

Microsoft Edge 已采用 Chromium 开放源代码项目，以创建更好的 Web 兼容性和减少不同基础 Web 平台的碎片。  此更改应该可以更轻松地在 Microsoft Edge 中生成和测试网站，并确保每个网站按预期运行，即使在不同的基于 Chromium 的浏览器 \ (如 Google Chrome、Vivaldi、Opera 或 Cookie\) 中查看。  

随着 Web 在设备类型的不断扩展的数组中的使用率增加，测试网站中涉及的复杂性和开销已大为增强。 由于 Web 开发人员\ (特别是小型公司的开发人员\) 必须针对如此多的不同系统进行测试，您可能会发现几乎不可能确保网站在所有设备类型和所有浏览器上都运行良好。  现在，Microsoft Edge 基于 Chromium，Microsoft Edge 团队已经将 Microsoft Edge Web 平台与其他基于 Chromium 的浏览器保持一致，并提供了一流的开发人员工具体验，包括浏览器内部以及每天使用的其他开发人员工具（如 Visual Studio Code\) ）中的 (Chromium。  

如果你要签出 Microsoft Edge，并且主要在基于 Chromium 的浏览器中进行开发，你应该感觉在家吧。  Microsoft Edge \ (Chromium\) 开发人员工具的功能方式与已了解和使用的开发人员工具相同。  有关详细信息，请导航到 [DevTools 中的 Microsoft Edge (Chromium) 新增功能][DevtoolsGuideChromiumWhatsNewIndex]。  

:::image type="complex" source="./media/devtools.png" alt-text="Microsoft Edge (Chromium) DevTools" lightbox="./media/devtools.png":::
   Microsoft Edge (Chromium) DevTools  
:::image-end:::  

如果你要签出新的 Microsoft Edge，并且你之前在 Microsoft Edge \ (EdgeHTML\) 中开发，你现在有一些出色的新工具，这些工具应该可以更轻松、更快地在 Microsoft Edge 中生成和测试你的网站。  

## 打开 DevTools  

如果以前从未使用过 DevTools，Microsoft Edge 开发人员工具是直接内置于 Microsoft Edge 浏览器的一组工具。  使用 DevTools，你可以执行以下操作。  

*   检查 HTML 网站并进行更改  
*   编辑 CSS 并立即查看网站呈现的预览  
*   查看前端 `console.log()` JavaScript 代码的所有语句  
*   通过设置断点并逐行执行来调试脚本  
    
全部直接在浏览器中。  这些只是 DevTools 提供的一些功能的示例，以便更轻松地在 Microsoft Edge 中生成和测试网站。  

打开 DevTools  

*   选择 `F12` 
*   在 `Ctrl` + `Shift` + `I` `Command` + `Option` + `I` macOS\ (Windows/Linux \)   
    
如果要查看网站上某个元素的 HTML 或 CSS，请右键单击该元素，然后选择"检查****"跳转到"元素"面板。  还可以在 macOS\) 上按 Windows/Linux \ (以在"检查元素模式"中打开 `Ctrl` + `Shift` + `C` `Command` + `Option` + `C` DevTools，******** 这将允许你选择站点上的元素，并查看"元素"面板中的 HTML 和 CSS。  

如果你希望从前端 JavaScript 代码查看日志或快速运行某些脚本，请在 Windows/Linux 或 macOS 上选择以在 `Ctrl` + `Shift` + `J` `Command` + `Option` + `J` DevTools**** 中启动控制台面板。  

## 核心工具  

:::image type="complex" source="./media/devtools-core-tools.png" alt-text="Microsoft Edge (Chromium) DevTools 核心工具" lightbox="./media/devtools-core-tools.png":::
   Microsoft Edge (Chromium) DevTools 核心工具  
:::image-end::: 

Microsoft Edge \ (Chromium\) DevTools 包括以下面板。  

*   “**元素**”面板，用于编辑 HTML 和 CSS、检查辅助功能属性、查看事件侦听器和设置 DOM 变化断点  
*   **控制台**，用于查看和筛选日志消息、检查 JavaScript 对象和 DOM 节点，并在所选窗口或框架的上下文中运行 JavaScript  
*   一 **个** 源面板，用于打开和实时编辑代码、设置断点、逐步执行代码，并一次查看一行 JavaScript 的网站状态  
*   “**网络**”面板，用于从网络和浏览器缓存监视和检查请求和响应   
*   “**性能**”面板，用于分析网站所需的时间和系统资源  
*   “**内存**”面板，用于衡量内存资源的使用情况，并比较代码运行时的不同状态下的堆快照  
*   检查 **、** 修改和调试 Web 应用清单、服务工作者和服务工作者缓存的应用程序面板。  您还可以检查和管理应用程序面板中的存储、 **数据库和缓存** 。  
*   **安全**面板，可调试安全问题并确保已在网站上正确实现 HTTPS。  HTTPS 为您的网站和用户提供您网站上的个人信息提供了关键的安全性和数据完整性。  
*   审核 **面板** \ (现在重命名为 **Lighthouse**\) 以运行网站的审核。  审核结果有助于通过以下方式提高网站质量。  
    *   捕获与使您的网站可访问性、安全性、性能高等相关的常见错误。  
    *   修复每个错误。  
    *   生成 PWA。  
        
[!INCLUDE [audits-panel-note](./includes/audits-panel-note.md)]  

请发送 [反馈和功能请求](#getting-in-touch-with-the-microsoft-edge-devtools-team)。  

## Extensions  

你可能已使用 DevTools 扩展来帮助你在构建网站或应用时诊断和调试问题。  你可以从 Microsoft Edge 加载项页面获取 [Microsoft Edge 的][MicrosoftEdgeAddonsExtensions] 扩展。  从[Microsoft Edge 加载项][MicrosoftEdgeAddonsExtensions]页面，你可以从开发人员工具类别浏览 DevTools**** 扩展或搜索特定扩展。  

还可以从 [Chrome Web 应用商店添加扩展][GoogleChromeWebstoreExtensions]。  

:::image type="complex" source="./media/allow-extensions-from-stores.png" alt-text="Microsoft Edge 中的 Chrome Web Store" lightbox="./media/allow-extensions-from-stores.png":::
   Microsoft Edge 中的 Chrome Web Store  
:::image-end:::  

在顶部，选择"允许来自其他存储的扩展 **"，** 然后在出现的**** 对话框中选择"允许"。  

> [!NOTE]
> 从 Microsoft Store 外的其他源安装的扩展未经验证，可能会影响浏览器性能。  

选择 **"添加到 Chrome"** 以将 DevTools 扩展添加到 Microsoft Edge。  

:::image type="complex" source="./media/install-extension-from-chrome-store.png" alt-text="将扩展从 Chrome Web Store 添加到 Microsoft Edge" lightbox="./media/install-extension-from-chrome-store.png":::
   将扩展从 Chrome Web Store 添加到 Microsoft Edge  
:::image-end:::  

## 快捷方式  

这些快捷方式控制主 DevTools 窗口、跨所有工具或同时使用这两种工具。  

| 操作 | Windows/Linux | macOS |  
|:--- |:--- | :--- |  
| 显示/隐藏 DevTools\（打开至上次查看的面板\） | `F12` 或 `Ctrl`+`Shift`+`I` | `Command`+`Option`+`I` |  
| 显示控制台面板 | `Ctrl`+`Shift`+`J` | `Command`+`Option`+`J` |  
| 在"检查元素模式"中**** 显示 DevTools，该模式允许你选择网站上的元素，并查看"元素"面板中的 HTML**和**CSS | `Ctrl`+`Shift`+`C` | `Command`+`Option`+`C` |  
| 显示设置 | `?` 或 `Fn`+`F1` | `?` 或 `Fn`+`F1` |  
| 显示下一个面板 | `Ctrl`+`]` | `Command`+`]` |  
| 显示上一个面板 | `Ctrl`+`[` | `Command`+`[` |  
| 将 DevTools 停靠在上次使用的位置。  如果 DevTools 在整个会话的默认位置保留，快捷方式将 DevTools 撤消到单独的窗口中 | `Ctrl`+`Shift`+`D` | `Command`+`Shift`+`D` |  
| 切换 **设备模式** | `Ctrl`+`Shift`+`M` | `Command`+`Shift`+`M` |  
| 切换 **检查元素模式** ，该模式允许你选择网站上的元素，并查看"元素" **面板中的** HTML 和 CSS | `Ctrl`+`Shift`+`C` | `Command`+`Shift`+`C` |  
| 显示命令菜单 | `Ctrl`+`Shift`+`P` | `Command`+`Shift`+`P` |  
| 显示/隐藏箱 | `Esc` | `Esc` |  
| 刷新。  使用缓存对页面进行重新设置。  | `F5` 或 `Ctrl`+`R` | `Command`+`R` |  
| 硬刷新。  强制 Microsoft Edge 再次下载资源并重新加载。  使用的资源可能来自缓存版本 | `Ctrl`+`F5` 或 `Ctrl`+`Shift`+`R` | `Command`+`Shift`+`R` |  
| 搜索当前面板中的文本。  在审核、应用程序和安全面板中不受支持 | `Ctrl`+`F` | `Command`+`F` |  
| 在"箱"中显示"搜索"面板，可让你跨所有加载的资源搜索文本 | `Ctrl`+`Shift`+`F` | `Command`+`Option`+`F` |  
| 在"源"面板中打开文件 | `Ctrl`+`O` 或 `Ctrl`+`P` | `Command`+`O` 或 `Command`+`P` |  
| 放大 | `Ctrl`+`Shift`+`+` | `Command`+`Shift`+`+` |  
| 缩小 | `Ctrl`+`-` | `Command`+`-` |  
| 还原默认缩放级别 | `Ctrl`+`0` | `Command`+`0` |  
| 运行代码段 | `Ctrl`+`O``Ctrl` + `P` 或 ， `!` 键入后跟脚本的名称，然后按 `Enter` | 按 `Command` + `O` or `Command` + `P` ， `!` 键入后跟脚本的名称，然后按 `Enter` |  
| 在新建选项卡中显示不可编辑的 HTML 源代码 | `Ctrl`+`U` | 不适用 |  

> [!NOTE]
> 如果你正在调试并暂停在断点，则 **刷新** 快捷方式将首先恢复运行时。  

## 另请参阅  

*   [适用于初学者的 DevTools：HTML 和 DOM 入门][DevtoolsGuideChromiumBeginnersHtml]  
*   [Microsoft Edge (Chromium) DevTools 协议][DevtoolsProtocolChromiumIndex]  
    
## 联系 Microsoft Edge DevTools 团队  

[!INCLUDE [contact DevTools team note](./includes/contact-devtools-team-note.md)]  

如果你想要预览即将进入 [DevTools][DevtoolsGuideChromiumWhatsNewIndex]的最新功能，请下载 [Microsoft Edge Canary，该 Canary][MicrosoftedgeinsiderDownload]是夜间构建的。  

<!-- links -->  

[DevtoolsGuideChromiumBeginnersHtml]: /microsoft-edge/devtools-guide-chromium/beginners/html "适用于初学者的 DevTools：HTML 和 DOM 入门 |Microsoft Docs"  
[DevtoolsGuideChromiumWhatsNewIndex]: /microsoft-edge/devtools-guide-chromium/whats-new/2020/11/devtools "Microsoft Edge (DevTools) 的新增功能 |Microsoft Docs"  
[DevtoolsProtocolChromiumIndex]: /microsoft-edge/devtools-protocol-chromium "Microsoft Edge (Chromium) DevTools 协议 |Microsoft Docs"  

[MicrosoftEdgeAddonsExtensions]: https://microsoftedge.microsoft.com/addons/category/Edge-Extensions "Microsoft Edge 加载项"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "下载 Microsoft Edge 预览体验成员频道"  

[GoogleChromeWebstoreExtensions]: https://chrome.google.com/webstore/category/extensions "扩展 |Chrome Web Store"  
