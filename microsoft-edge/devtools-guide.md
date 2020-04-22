---
description: 了解 Microsoft Edge （EdgeHTML）开发工具
title: Microsoft Edge （EdgeHTML）开发人员工具
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/03/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: microsoft edge、web 开发、f12 工具、devtools
experimental: true
experiment_id: 51fe4b97-3e55-41
localization_priority: Priority
ms.openlocfilehash: 1abc01af5c1b058687d9ba1402911d4367b6e2b3
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563519"
---
# Microsoft Edge （EdgeHTML）开发人员工具  

[!INCLUDE [new-devtools-version-note](includes/new-devtools-version-note.md)]  

Microsoft Edge \ （EdgeHTML \） DevTools 是使用[TypeScript][|::ref1::|Index]（由[开放源代码][GithubMicrosoftChakracore]支持）针对新式前端工作流进行了优化，现在可在 Microsoft Store 中以[独立 Windows 10 应用][MicrosoftStoreEdgeDevtoolsPreview]的形式提供！  

有关最新功能的详细信息，请查看[最新的 Windows 10 更新（EdgeHTML 18） DevTools][DevtoolsGuideEdgehtmlWhatsnew]。  

## 核心工具  

![Microsoft Edge \ （EdgeHTML \） DevTools][ImageDevtoolsEdgehtml]  

Microsoft Edge \ （EdgeHTML \） DevTools 包括：  

*   "[元素][DevtoolsGuideEdgehtml|::ref2::|]" 面板，用于编辑 HTML 和 CSS、检查辅助功能属性、查看事件侦听器和设置 DOM 转变断点  
*   用于查看和筛选日志消息、检查 JavaScript 对象和 DOM 节点以及在所选窗口或框架的上下文中运行 JavaScript 的[控制台][DevtoolsGuideEdgehtml|::ref3::|]  
*   用于逐句通过代码、设置监视和断点、实时编辑代码以及检查 web 存储和 cookie 缓存的[调试器][DevtoolsGuideEdgehtml|::ref4::|]  
*   用于监视和检查来自网络和浏览器缓存的请求和响应的[网络][DevtoolsGuideEdgehtml|::ref5::|]面板  
*   用于分析你的网站所需的时间和系统资源的[性能][DevtoolsGuideEdgehtml|::ref6::|]面板  
*   测量内存资源使用情况和比较不同状态的代码运行时中的堆快照的[内存][DevtoolsGuideEdgehtml|::ref7::|]面板  
*   用于检查和管理 web 存储、IndexedDB、cookie 和缓存数据的[存储][DevtoolsGuideEdgehtml|::ref8::|]面板  
*   用于管理和调试服务工作者的[服务工作者][DevtoolsGuideEdgehtmlServiceworkers]面板  
*   用于使用不同浏览器配置文件、屏幕分辨率和 GPS 位置坐标测试网站的[仿真][DevtoolsGuideEdgehtml|::ref9::|]面板  

请继续发送您的[反馈和功能请求](#feedback)！  

> [!TIP]
> [通过任何浏览器免费在 Microsoft Edge \ （EdgeHTML \）中进行测试][BrowserstackEdgehtml]：  
> 我们与[BrowserStack][BrowserstackEdgehtml]合作，在 Microsoft Edge \ （EdgeHTML \）中提供免费实时和自动测试。  

## Microsoft Store 应用  

**Microsoft Edge \ （EdgeHTML \） DevTools** [现在可][DevtoolsGuideEdgehtmlWhatsnew]作为 microsoft Store 中的独立[Windows 10 应用][MicrosoftStoreEdgeDevtoolsPreview]，除了浏览器 \ （`F12`\）工具体验。  使用应用商店版本时，将出现一个**选择器**面板，用于附加到打开本地和远程页面目标以及选项卡式布局，以便在 DevTools 实例之间轻松切换。  

### 本地调试  

若要在本地调试页面，只需启动 Microsoft Edge DevTools 应用。  选择器的**本地**面板将显示所有活动的 EdgeHTML 内容进程，包括打开的边缘浏览器选项卡、运行[PWAs][PwasEdgehtmlIndex] \`WWAHost.exe` （进程 \）和[web 视图][HostingWebview]控件。  单击所需的目标以附加并打开 DevTools 的新选项卡实例。  

![DevTools app 本地面板][ImageDevtoolsGuideEdgehtmlChooselocal]  

### 远程调试  

Microsoft Edge DevTools 应用通过我们新发布的[DevTools 协议][DevtoolsProtocolEdgehtmlIndex]引入了对远程计算机上的页面调试的基本支持。  使用最新版本，可远程访问[调试器][DevtoolsGuideEdgehtml|::ref10::|]、[元素][DevtoolsGuideEdgehtml|::ref11::|]\ （适用于只读操作 \）和[控制台][DevtoolsGuideEdgehtml|::ref12::|]面板中的核心功能。  远程调试限制为运行桌面主机的 Microsoft Edge \ （EdgeHTML \），并支持未来版本中的其他 EdgeHTML 主机和 Windows 10 设备。  

若要开始使用，请查看[DevTools 协议][DevtoolsProtocolEdgehtmlIndex]文档的[*Microsoft Edge DevTools*][DevtoolsProtocolEdgehtmlClientsEdgePreview]部分。  

![DevTools 应用程序远程面板][DevtoolsGuideEdgehtmlRemote]  

## 反馈  

请向我们发送您的反馈，以便我们可以继续为您改进 Microsoft Edge \ （EdgeHTML \） DevTools！  只需打开 "工具`F12`" （），然后单击 "[发送反馈](#microsoft-edge-edgehtml-developer-tools)" 按钮。  

成为[Windows 预览体验成员][WindowsInsiderProgram]，预览[即将 DevTools 的最新功能][DevtoolsGuideEdgehtmlWhatsnew]。  使用 Windows 反馈中心应用对常规 Windows 建议和问题进行发布、向上投票、跟踪和获取支持。  

## 常规快捷方式  

这些快捷方式控制主 DevTools 窗口，并且应在所有工具中运行。  

| 操作 | 快捷方式 |  
|:--- |:--- |  
| 显示/隐藏 DevTools \ （打开上次查看的面板 \） | `F12`, `Ctrl`+`Shift`+`I` |  
| 切换坞站 \ （脱开/右下/右 \） | `Ctrl`+`Shift`+`D` |  
| 打开文件 | `Ctrl`+`P`, `Ctrl`+`O` |  
| 在调试器中显示不可编辑的 HTML 源代码 | `Ctrl`+`U` |  
| 在任何其他工具的底部显示/隐藏控制台  | `Ctrl`+`` ` `` |  
| 切换到元素 \ （DOM 资源管理器 \） | `Ctrl`+`1` |  
| 切换到控制台 |  `Ctrl`+`2` |  
| 切换到调试器 | `Ctrl`+`3` |  
| 切换到网络 | `Ctrl`+`4` |  
| 切换到性能 | `Ctrl`+`5` |  
| 切换到内存 | `Ctrl`+`6` |  
| 切换到仿真 | `Ctrl`+`7` |  
| 帮助文档 | `F1` |  
| 下一个工具 | `Ctrl`+`F6` |  
| 上一个工具 | `Ctrl`+`Shift`+`F6` |  
| 上一个工具 \ （来自历史记录 \） | `Ctrl`+`Shift`+`[` |  
| 下一个工具 \ （来自历史记录 \） | `Ctrl`+`Shift`+`]` |  
| 下一个 Subframe | `F6` |  
| 以前的 Subframe | `Shift`+`F6` |  
| 搜索框中的下一个匹配项 | `F3` |  
| 搜索框中的上一个匹配项 | `Shift`+`F3` |  
| 在搜索框中查找 | `Ctrl`+`F` |  
| 向底部的控制台提供焦点 | `Alt`+`Shift`+`I` |  
| 启动 DevTools 到 Console | `Ctrl`+`Shift`+`J` |  
| 刷新页面 | `Ctrl`+`Shift`+`F5`, `Ctrl`+`R` |  

> [!NOTE]
> 如果你正在调试并在断点处暂停，则**刷新页面**操作将首先恢复运行时。

<!-- image links  -->  

[ImageDevtoolsEdgehtml]: /microsoft-edge/devtools-guide/media/devtools.png "Microsoft Edge （EdgeHTML） DevTools"  
[ImageDevtoolsGuideEdgehtmlChooselocal]: /microsoft-edge/devtools-guide/media/chooser_local.png "DevTools app 本地面板"  
[DevtoolsGuideEdgehtmlRemote]: /microsoft-edge/devtools-guide/media/chooser_remote.png "DevTools 应用程序远程面板"  

<!-- links  -->  

[DevtoolsGuideEdgehtmlConsole]: /microsoft-edge/devtools-guide/console "控制"  
[DevtoolsGuideEdgehtmlDebugger]: /microsoft-edge/devtools-guide/debugger "调试器"  
[DevtoolsGuideEdgehtmlElements]: /microsoft-edge/devtools-guide/elements "网元"  
[DevtoolsGuideEdgehtmlEmulation]: /microsoft-edge/devtools-guide/emulation "仿真"  
[DevtoolsGuideEdgehtmlMemory]: /microsoft-edge/devtools-guide/memory "闪存"  
[DevtoolsGuideEdgehtmlNetwork]: /microsoft-edge/devtools-guide/network "网络"  
[DevtoolsGuideEdgehtmlPerformance]: /microsoft-edge/devtools-guide/performance "能"  
[DevtoolsGuideEdgehtmlServiceworkers]: /microsoft-edge/devtools-guide/service-workers "服务工作人员"  
[DevtoolsGuideEdgehtmlStorage]: /microsoft-edge/devtools-guide/storage "Storage"  
[DevtoolsGuideEdgehtmlWhatsnew]: /microsoft-edge/devtools-guide/whats-new "最新 Windows 10 更新（EdgeHTML 18）中的 DevTools"  
[DevtoolsProtocolEdgehtmlIndex]: /microsoft-edge/devtools-protocol/index "Microsoft Edge （EdgeHTML） DevTools 协议"  
[DevtoolsProtocolEdgehtmlClientsEdgePreview]: /microsoft-edge/devtools-protocol/0.1/clients.md#microsoft-edge-devtools-preview "Microsoft Edge DevTools Preview-DevTools 协议客户端"  
[HostingWebview]: /microsoft-edge/hosting/webview "适用于 Windows 10 应用的 Web 视图（EdgeHTML）"  
[PwasEdgehtmlIndex]: /microsoft-edge/progressive-web-apps-edgehtml/index "Windows 上的渐进式 Web 应用（EdgeHTML）"  

[MicrosoftStoreEdgeDevtoolsPreview]: https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj "Microsoft Edge DevTools 预览"  

[WindowsInsiderProgram]: https://insider.windows.com "Windows 预览体验计划"  

[BrowserstackEdgehtml]: https://www.browserstack.com/test-on-microsoft-edge-browser "Microsoft Edge 浏览器免费测试 |BrowserStack"  

[GithubMicrosoftChakracore]: https://github.com/Microsoft/ChakraCore "microsoft/ChakraCore |GitHub"  

[TypeScriptIndex]: https://www.typescriptlang.org "TypeScript"  
