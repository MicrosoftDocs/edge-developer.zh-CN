---
description: 了解 Microsoft Edge (EdgeHTML) Developer Tools
title: Microsoft Edge (EdgeHTML) Developer Tools
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: microsoft edge, web 开发, f12 工具, devtools
experimental: true
experiment_id: 51fe4b97-3e55-41
ms.localizationpriority: high
ms.openlocfilehash: 0c01b761d1aa1fb645b15b0be5d5d6e4265e646e
ms.sourcegitcommit: b88d2a55a59db8373ff2bac275d3730977bf19c9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2020
ms.locfileid: "10985966"
---
# Microsoft Edge (EdgeHTML) Developer Tools  

[!INCLUDE [new-devtools-version-note](includes/new-devtools-version-note.md)]  

Microsoft Edge \(EdgeHTML\) DevTools 是使用 [TypeScript][|::ref1::|Index] 构建的，由[开放源代码][GithubMicrosoftChakracore]提供支持，并已针对新式前端工作流进行了优化，当前在 Microsoft Store 中作为[独立 Windows 10 应用][MicrosoftStoreEdgeDevtoolsPreview]提供！  

有关最新功能的详细信息，请参阅 [Windows 10 最新更新中的 DevTools (EdgeHTML 18)][DevtoolsGuideEdgehtmlWhatsnew]。  

## 核心工具  

:::image type="complex" source="./devtools-guide/media/devtools.png" alt-text="Microsoft Edge (EdgeHTML) DevTools":::
   Microsoft Edge (EdgeHTML) DevTools
:::image-end:::

<!--![Microsoft Edge \(EdgeHTML\) DevTools][ImageDevtoolsEdgehtml]  -->  

Microsoft Edge \(EdgeHTML\) DevTools 包括：  

*   “[元素][DevtoolsGuideEdgehtml|::ref2::|]”面板，用于编辑 HTML 和 CSS、检查辅助功能属性、查看事件侦听器和设置 DOM 变化断点  
*   [控制台][DevtoolsGuideEdgehtml|::ref3::|]，用于查看和筛选日志消息、检查 JavaScript 对象和 DOM 节点，并在所选窗口或框架的上下文中运行 JavaScript  
*   [调试程序][DevtoolsGuideEdgehtml|::ref4::|]，用于逐步执行代码、设置监视和断点、实时编辑代码以及检查 Web 存储和 Cookie 缓存  
*   “[网络][DevtoolsGuideEdgehtml|::ref5::|]”面板，用于从网络和浏览器缓存监视和检查请求和响应  
*   “[性能][DevtoolsGuideEdgehtml|::ref6::|]”面板，用于分析网站所需的时间和系统资源  
*   “[内存][DevtoolsGuideEdgehtml|::ref7::|]”面板，用于衡量内存资源的使用情况，并比较代码运行时的不同状态下的堆快照  
*   “[存储][DevtoolsGuideEdgehtml|::ref8::|]”面板，用于检查和管理 Web 存储、IndexedDB、Cookie 和缓存数据  
*   “[服务工作进程][DevtoolsGuideEdgehtmlServiceworkers]”面板，用于管理和调试服务工作进程  
*   “[枚举][DevtoolsGuideEdgehtml|::ref9::|]”面板，可使用不同的浏览器配置文件、屏幕分辨率和 GPS 位置坐标来测试网站  

请继续发送你的[反馈和功能请求](#getting-in-touch-with-the-microsoft-edge-devtools-team)！  

> [!TIP]
> [从任何浏览器免费测试 Microsoft Edge \(EdgeHTML)][BrowserstackEdgehtml]。  
> Microsoft Edge 团队与 [BrowserStack][BrowserstackEdgehtml] 合作，在 Microsoft Edge \(EdgeHTML) 上提供免费的实时和自动化测试。  

## Microsoft Store 应用  

除了浏览器内 \(`F12`\) 工具体验之前，**Microsoft Edge \(EdgeHTML\) DevTools** 当前还作为独立 [Windows 10 应用在 [Microsoft Store][DevtoolsGuideEdgehtmlWhatsnew] 上提供][MicrosoftStoreEdgeDevtoolsPreview]。  应用商店版本提供了一个**选择器**面板（用于连接以打开本地和远程页面目标）以及一个选项卡式布局（便于在 DevTools 实例之间进行切换）。  

### 本地调试  

若要在本地调试页面，只需启动 Microsoft Edge DevTools 应用。  选择器的“**本地**”面板将显示所有活动的 EdgeHTML 内容进程，包括打开的 Edge 浏览器选项卡、运行的 [PWA][PwasEdgehtmlIndex]\（`WWAHost.exe` 进程\）和 [webview][HostingWebview] 控件。  选择所需目标，并打开 DevTools 的新选项卡实例。  

:::image type="complex" source="./devtools-guide/media/chooser_local.png" alt-text="DevTools 应用的“本地”面板":::
   DevTools 应用的“本地”面板
:::image-end:::

<!--![DevTools app Local panel][ImageDevtoolsGuideEdgehtmlChooselocal]  -->  

### 远程调试  

Microsoft Edge DevTools 应用引入了对通过我们最新发布的 [DevTools 协议][DevtoolsProtocolEdgehtmlIndex]在远程计算机上调试页面的基本支持。  在最新版本中，可以远程访问“[调试程序][DevtoolsGuideEdgehtml|::ref10::|]”、“[元素][DevtoolsGuideEdgehtml|::ref11::|]”（用于只读操作）和“[控制台][DevtoolsGuideEdgehtml|::ref12::|]”面板中的核心功能。  远程调试仅限于运行桌面主机的 Microsoft Edge \(EdgeHTML\)，将来的版本将支持其他 EdgeHTML 主机和 Windows 10 设备。  

若要开始，请查看“[DevTools 协议][DevtoolsProtocolEdgehtmlIndex]”文档的“[*Microsoft Edge DevTools*][DevtoolsProtocolEdgehtmlClientsEdgePreview]”部分。  

:::image type="complex" source="./devtools-guide/media/chooser_remote.png" alt-text="DevTools 应用“远程”面板":::
   DevTools 应用“远程”面板
:::image-end:::

<!--![DevTools app Remote panel][ImageDevtoolsGuideEdgehtmlRemote]  -->  

## 常规快捷方式  

> [!IMPORTANT]
> 所有快捷方式都已在最新 Windows 版本中验证。  
> 如果无法使用快捷方式，请更新你的 Windows 副本。  

这些快捷方式控制主 DevTools 窗口，并应在所有工具中正常工作。  

| 操作 | 快捷方式 |  
|:--- |:--- |  
| 显示/隐藏 DevTools\（打开至上次查看的面板\） | `F12`, `Ctrl`+`Shift`+`I` |  
| 切换扩展连接\（移除/下/右\） | `Ctrl`+`Shift`+`D` |  
| 打开文件 | `Ctrl`+`P`, `Ctrl`+`O` |  
| 在调试程序中显示不可编辑的 HTML 源代码 | `Ctrl`+`U` |  
| 在任何其他工具底部显示/隐藏“控制台”  | `Ctrl`+`` ` `` |  
| 切换到“元素”\（DOM 资源管理器\） | `Ctrl`+`1` |  
| 切换到“控制台” |  `Ctrl`+`2` |  
| 切换到“调试程序” | `Ctrl`+`3` |  
| 切换到“网络” | `Ctrl`+`4` |  
| 切换到“性能” | `Ctrl`+`5` |  
| 切换到“内存” | `Ctrl`+`6` |  
| 切换到“枚举” | `Ctrl`+`7` |  
| 帮助文档 | `F1` |  
| 下一个工具 | `Ctrl`+`F6` |  
| 上一个工具 | `Ctrl`+`Shift`+`F6` |  
| 上一个工具\（来自历史记录\） | `Ctrl`+`Shift`+`[` |  
| 下一个工具\（来自历史记录\） | `Ctrl`+`Shift`+`]` |  
| 下一个子框架 | `F6` |  
| 上一个子框架 | `Shift`+`F6` |  
| 搜索框中的下一个匹配项 | `F3` |  
| 搜索框中的上一个匹配项 | `Shift`+`F3` |  
| 在搜索框中查找 | `Ctrl`+`F` |  
| 将焦点放在底部的控制台上 | `Alt`+`Shift`+`I` |  
| 启动 DevTools 到“控制台” | `Ctrl`+`Shift`+`J` |  
| 刷新页面 | `Ctrl`+`Shift`+`F5`, `Ctrl`+`R` |  

> [!NOTE]
> 如果你正在调试并在断点处暂停，则“**刷新页面**”操作会首先恢复运行时。  

## 与 Microsoft Edge 开发人员工具团队联系  

请发送你的反馈以帮助改进 Microsoft Edge \(EdgeHTML\) DevTools！  只需打开工具 \(`F12`\) 并选择“[发送反馈](#microsoft-edge-edgehtml-developer-tools)”按钮。  

成为 [Windows 预览体验成员][WindowsInsiderProgram]，预览[即将推出的 DevTools 最新功能][DevtoolsGuideEdgehtmlWhatsnew]。  使用 Windows 反馈中心应用发布、投票、跟踪和获取对常规 Windows 建议和问题的支持。  

<!-- image links  -->  

<!--[ImageDevtoolsEdgehtml]: /microsoft-edge/devtools-guide/media/devtools.png "Microsoft Edge (EdgeHTML) DevTools"  -->  
<!--[ImageDevtoolsGuideEdgehtmlChooselocal]: /microsoft-edge/devtools-guide/media/chooser_local.png "DevTools app Local panel"  -->  
<!--[ImageDevtoolsGuideEdgehtmlRemote]: /microsoft-edge/devtools-guide/media/chooser_remote.png "DevTools app Remote panel"  -->  

<!-- links  -->  

[DevtoolsGuideEdgehtmlConsole]: /microsoft-edge/devtools-guide/console "控制台"  
[DevtoolsGuideEdgehtmlDebugger]: /microsoft-edge/devtools-guide/debugger "调试程序"  
[DevtoolsGuideEdgehtmlElements]: /microsoft-edge/devtools-guide/elements "元素"  
[DevtoolsGuideEdgehtmlEmulation]: /microsoft-edge/devtools-guide/emulation "枚举"  
[DevtoolsGuideEdgehtmlMemory]: /microsoft-edge/devtools-guide/memory "内存"  
[DevtoolsGuideEdgehtmlNetwork]: /microsoft-edge/devtools-guide/network "网络"  
[DevtoolsGuideEdgehtmlPerformance]: /microsoft-edge/devtools-guide/performance "性能"  
[DevtoolsGuideEdgehtmlServiceworkers]: /microsoft-edge/devtools-guide/service-workers "服务工作进程"  
[DevtoolsGuideEdgehtmlStorage]: /microsoft-edge/devtools-guide/storage "存储"  
[DevtoolsGuideEdgehtmlWhatsnew]: /microsoft-edge/devtools-guide/whats-new "最新 Windows 10 更新中的 DevTools (EdgeHTML 18)"  
[DevtoolsProtocolEdgehtmlIndex]: /microsoft-edge/devtools-protocol/index "Microsoft Edge (EdgeHTML) DevTools 协议"  
[DevtoolsProtocolEdgehtmlClientsEdgePreview]: /microsoft-edge/devtools-protocol/0.1/clients.md#microsoft-edge-devtools-preview "Microsoft Edge DevTools Preview-DevTools 协议客户端"  
[HostingWebview]: /microsoft-edge/hosting/webview "Windows 10 应用的 WebView (EdgeHTML)"  
[PwasEdgehtmlIndex]: /microsoft-edge/progressive-web-apps-edgehtml/index "Windows 上的渐进式 Web 应用 (EdgeHTML)"  

[MicrosoftStoreEdgeDevtoolsPreview]: https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj "Microsoft Edge DevTools 预览版"  

[WindowsInsiderProgram]: https://insider.windows.com "Windows 预览体验计划"  

[BrowserstackEdgehtml]: https://www.browserstack.com/test-on-microsoft-edge-browser "Microsoft Edge 浏览器免费测试 | BrowserStack"  

[GithubMicrosoftChakracore]: https://github.com/Microsoft/ChakraCore "microsoft/ChakraCore | GitHub"  

[TypeScriptIndex]: https://www.typescriptlang.org "TypeScript"  
