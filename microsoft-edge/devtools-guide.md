---
description: 了解 Microsoft Edge (EdgeHTML) 开发人员工具标题
title: Microsoft Edge (EdgeHTML) 开发人员工具作者
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: microsoft edge, web development, f12 tools, devtools
experimental: true
experiment_id: "51fe4b97-3e55-41"
ms.localizationpriority: high
---

# Microsoft Edge (EdgeHTML) 开发人员工具  

[!INCLUDE [new-devtools-version-note](includes/new-devtools-version-note.md)]  

Microsoft Edge (EdgeHTML) 开发人员工具采用 [TypeScript][TypeScriptIndex] 构建，由[开放源代码][GithubMicrosoftChakracore]提供支持，针对现代前端工作流进行了优化，现在可在 Microsoft Store 中作为[独立的 Windows 10 应用][MicrosoftStoreEdgeDevtoolsPreview]提供！  

有关最新功能的详细信息，请参阅[最新 Windows 10 更新 (EdgeHTML 18) 中的开发人员工具][DevtoolsGuideEdgehtmlWhatsnew]。  

## 核心工具  

:::image type="complex" source="./devtools-guide/media/devtools.png" alt-text="Microsoft Edge (EdgeHTML) DevTools":::
  Microsoft Edge (EdgeHTML) DevTools
:::image-end:::

<!--![Microsoft Edge \(EdgeHTML\) DevTools][ImageDevtoolsEdgehtml]  -->  

Microsoft Edge (EdgeHTML) 开发人员工具包括：  

*   “[元素][DevtoolsGuideEdgehtmlElements]”面板，用于编辑 HTML 和 CSS，检查辅助功能属性，查看事件侦听器以及设置 DOM 突变断点  
*   “[控制台][DevtoolsGuideEdgehtmlConsole]”，用于查看和筛选日志消息，检查 JavaScript 对象和 DOM 节点，并在选定窗口或框架的上下文中运行 JavaScript  
*   “[调试程序][DevtoolsGuideEdgehtmlDebugger]”，用于逐步执行代码，设置监视和断点，实时编辑代码以及检查 Web 存储和 Cookie 缓存  
*   “[网络][DevtoolsGuideEdgehtmlNetwork]”面板，用于监视和检查来自网络和浏览器缓存的请求和响应  
*   “[性能][DevtoolsGuideEdgehtmlPerformance]”面板，用于剖析网站所需的时间和系统资源  
*   “[内存][DevtoolsGuideEdgehtmlMemory]”面板，用于衡量内存资源的使用情况，并比较代码运行时的不同状态下的堆快照  
*   “[存储][DevtoolsGuideEdgehtmlStorage]”面板，用于检查和管理 Web 存储、IndexedDB、Cookie 和缓存数据  
*   “[服务工作者][DevtoolsGuideEdgehtmlServiceworkers]”面板，用于管理和调试服务工作者  
*   “[枚举][DevtoolsGuideEdgehtmlEmulation]”面板，用于使用不同的浏览器配置文件、屏幕分辨率和 GPS 位置坐标测试你的网站  

请继续发送你的[反馈和功能请求](#getting-in-touch-with-the-microsoft-edge-devtools-team)！  

> [!提示]
> [从任何浏览器免费测试 Microsoft Edge (EdgeHTML)][BrowserstackEdgehtml]。  
> Microsoft Edge 团队与 [BrowserStack][BrowserstackEdgehtml] 合作，在 Microsoft Edge (EdgeHTML) 上提供免费的实时和自动化测试。  

## Microsoft Store 应用  

**Microsoft Edge (EdgeHTML) 开发人员工具**[当前][DevtoolsGuideEdgehtmlWhatsnew]作为独立的 [Windows 10 应用在 Microsoft Store 上提供][MicrosoftStoreEdgeDevtoolsPreview]，此外还提供浏览器内(`F12`)工具体验。应用商店版本中提供了一个**选择器**面板和一个选项卡式布局，前者用于附加到打开的本地和远程页面目标，后者用于在开发人员工具实例之间轻松切换。  

### 本地调试  

若要在本地调试页面，只需启动 Microsoft Edge 开发人员工具应用即可。选择器的“**本地**”面板显示所有活动的 EdgeHTML 内容进程，包括打开的 Edge 浏览器选项卡、正在运行的 [PWAs][PwasEdgehtmlIndex]（`WWAHost.exe` 进程）和 [webview][HostingWebview] 控件。选择所需目标以附加并打开开发人员工具的新选项卡实例。  

:::image type="complex" source="./devtools-guide/media/chooser_local.png" alt-text="DevTools app Local panel":::
  DevTools app Local panel
:::image-end:::

<!--![DevTools app Local panel][ImageDevtoolsGuideEdgehtmlChooselocal]  -->  

### 远程调试  

Microsoft Edge 开发人员工具应用通过最新发布的[开发人员工具协议][DevtoolsProtocolEdgehtmlIndex]引入了对在远程计算机上调试页面的基本支持。在最新版本中，可以远程访问“[调试程序][DevtoolsGuideEdgehtmlDebugger]”、“[元素][DevtoolsGuideEdgehtmlElements]”（用于只读操作）和“[控制台][DevtoolsGuideEdgehtmlConsole]”面板中的核心功能。远程调试仅限于运行桌面主机的 Microsoft Edge (EdgeHTML)，将来的版本将支持其他 EdgeHTML 主机和 Windows 10 设备。  

若要开始，请查看“[开发人员工具协议][DevtoolsProtocolEdgehtmlIndex]”文档的“[*Microsoft Edge 开发人员工具*][DevtoolsProtocolEdgehtmlClientsEdgePreview]”部分。  

:::image type="complex" source="./devtools-guide/media/chooser_remote.png" alt-text="DevTools app Remote panel":::
  DevTools app Remote panel
:::image-end:::

<!--![DevTools app Remote panel][ImageDevtoolsGuideEdgehtmlRemote]  -->  

## 通用快捷方式  

> [!重要提示]
> 所有快捷方式均已在最新版本的 Windows 中验证。  
> 如果无法使用快捷方式，请更新你的 Windows 副本。  

这些快捷方式控制主开发人员工具窗口，并且应能在所有工具中都正常工作。  

| 操作 |快捷方式 |  
|:--- |:--- |  
| 显示/隐藏开发人员工具（打开至上次查看的面板）| `F12`、`Ctrl`+`Shift`+`I` |  
| 切换停靠（取消停靠/底部/右侧）| `Ctrl`+`Shift`+`D` |  
| 打开文件 | `Ctrl`+`P`, `Ctrl`+`O` |  
| 在调试程序中显示不可编辑的 HTML 源代码 | `Ctrl`+`U` |  
| 在任何其他工具的底部显示/隐藏控制台 | `Ctrl`+`` ` `` |  
| 切换到“元素”（DOM 资源管理器）| `Ctrl`+`1` ||  
| 切换到“控制台”| `Ctrl`+`2` |  
| 切换到“调试程序”| `Ctrl`+`3` |  
| 切换到“网络”| `Ctrl`+`4` |  
| 切换到“性能”| `Ctrl`+`5` |  
| 切换到“内存”| `Ctrl`+`6` |  
| 切换到“枚举”| `Ctrl`+`7` |  
| 帮助文档 | `F1` |  
| 下一个工具 | `Ctrl`+`F6` |  
| 上一个工具 | `Ctrl`+`Shift`+`F6` |  
| 上一个工具（来自历史记录）| `Ctrl`+`Shift`+`[` |  
| 下一个工具（来自历史记录）| `Ctrl`+`Shift`+`]` |  
| 下一个子框架 | `F6` |  
| 上一个子框架 | `Shift`+`F6` |  
| 搜索框中的下一个匹配项 | `F3` |  
| 搜索框中的上一个匹配项 | `Shift`+`F3` |  
| 在搜索框中查找 | `Ctrl`+`F` |  
| 将焦点放在底部的控制台 | `Alt`+`Shift`+`I` |  
| 启动开发人员工具到控制台 | `Ctrl`+`Shift`+`J` |  
| 刷新页面 | `Ctrl`+`Shift`+`F5`、`Ctrl`+`R` |  

> [!注意]
> 如果正在调试并在断点处暂停，“**刷新页面**”操作会先恢复运行时。  

## 与 Microsoft Edge 开发人员工具团队联系  

请发送你的反馈以帮助改进 Microsoft Edge (EdgeHTML) 开发人员工具！只需打开工具 (`F12`) 并选择“[发送反馈](#microsoft-edge-edgehtml-developer-tools)”按钮。  

成为 [Windows 预览体验成员][WindowsInsiderProgram]，以预览[开发人员工具的最新功能][DevtoolsGuideEdgehtmlWhatsnew]。使用 Windows 反馈中心应用发布、投票、跟踪和获取对一般 Windows 建议和问题的支持。  

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
[DevtoolsGuideEdgehtmlServiceworkers]: /microsoft-edge/devtools-guide/service-workers "服务工作者"  
[DevtoolsGuideEdgehtmlStorage]: /microsoft-edge/devtools-guide/storage "存储"  
[DevtoolsGuideEdgehtmlWhatsnew]: /microsoft-edge/devtools-guide/whats-new "最新 Windows 10 更新 (EdgeHTML 18) 中的开发人员工具"  
[DevtoolsProtocolEdgehtmlIndex]: /microsoft-edge/devtools-protocol/index "Microsoft Edge (EdgeHTML) 开发人员工具协议"  
[DevtoolsProtocolEdgehtmlClientsEdgePreview]: /microsoft-edge/devtools-protocol/0.1/clients.md#microsoft-edge-devtools-preview "Microsoft Edge 开发人员工具预览版 - 开发人员工具协议客户端"  
[HostingWebview]: /microsoft-edge/hosting/webview "Windows 10 应用的 Web 视图 (EdgeHTML)"  
[PwasEdgehtmlIndex]: /microsoft-edge/progressive-web-apps-edgehtml/index "Windows 上的渐进式 Web 应用 (EdgeHTML)"  

[MicrosoftStoreEdgeDevtoolsPreview]: https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj "Microsoft Edge 开发人员工具预览版"  

[WindowsInsiderProgram]: https://insider.windows.com "Windows 预览体验计划"  

[BrowserstackEdgehtml]: https://www.browserstack.com/test-on-microsoft-edge-browser "Microsoft Edge 浏览器免费测试 | BrowserStack"  

[GithubMicrosoftChakracore]: https://github.com/Microsoft/ChakraCore "microsoft/ChakraCore | GitHub"  

[TypeScriptIndex]: https://www.typescriptlang.org "TypeScript"  
