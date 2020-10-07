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

:::image type="complex" source="./devtools-guide/media/chooser_local.png" alt-text="Microsoft Edge (EdgeHTML) DevTools":::
   DevTools 应用的“本地”面板
:::image-end:::

<!--![DevTools app Local panel][ImageDevtoolsGuideEdgehtmlChooselocal]  -->  

### 远程调试  

Microsoft Edge DevTools 应用引入了对通过我们最新发布的 [DevTools 协议][DevtoolsProtocolEdgehtmlIndex]在远程计算机上调试页面的基本支持。  在最新版本中，可以远程访问“[调试程序][DevtoolsGuideEdgehtml|::ref10::|]”、“[元素][DevtoolsGuideEdgehtml|::ref11::|]”（用于只读操作）和“[控制台][DevtoolsGuideEdgehtml|::ref12::|]”面板中的核心功能。  远程调试仅限于运行桌面主机的 Microsoft Edge \(EdgeHTML\)，将来的版本将支持其他 EdgeHTML 主机和 Windows 10 设备。  

若要开始，请查看“[DevTools 协议][DevtoolsProtocolEdgehtmlIndex]”文档的“[*Microsoft Edge DevTools*][DevtoolsProtocolEdgehtmlClientsEdgePreview]”部分。  

:::image type="complex" source="./devtools-guide/media/chooser_remote.png" alt-text="Microsoft Edge (EdgeHTML) DevTools"  
