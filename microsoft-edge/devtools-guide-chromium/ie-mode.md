---
description: IE 模式和 Microsoft Edge （Chromium） DevTools
title: Internet Explorer 模式和 DevTools
author: robpaveza
ms.author: ropaveza
ms.date: 01/15/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools、ie11、internet explorer 11、ie 模式
ms.openlocfilehash: 18e5f029d277e446857ec48b9cf129149f219256
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564162"
---
# Internet Explorer 模式和 DevTools

本文档介绍 Internet Explorer 模式（IE 模式）如何与 Microsoft Edge （Chromium） DevTools 集成。

## 了解 IE 模式

IE 模式是一种机制，企业可以使用该机制来指定一组网站，直到现在才在 Internet Explorer 11 中工作。 当在 Microsoft Edge （Chromium）中查看这些网站时，将在选项卡中运行并呈现一个完整的 Internet Explorer 11 实例。这允许企业管理 IE 文档模式、ActiveX 控件以及当前与任何新式 web 浏览器不兼容的其他旧版组件的兼容性。

在 IE 模式下，呈现过程完全基于 Internet Explorer 11。 Microsoft Edge （Chromium）管理器进程管理呈现过程的生存期，但它受限于给定网站或应用程序上的选项卡生存期。 在 IE 模式下呈现选项卡时，将在给定选项卡的地址栏中显示一个标记：

![地址栏中的 IE 模式标记](./media/ie-mode-badge.png)

IE 模式目前适用于 Windows 10 版本1903（可能2019更新），但即将推出所有受支持的 Windows 平台。

## 在 IE 模式下的选项卡上启动 DevTools

如果您尝试在 IE 模式下查看网站的文档模式，则可以在地址栏中单击锁屏提醒。

![通过 IE mode 徽章查看文档模式](./media/ie-mode-badge-doc-mode.png)

在 IE 模式下的选项卡上，DevTools 将不起作用。 按 `F12` 或 `Ctrl` + `Shift` + `I` 将仅启动 Microsoft Edge （Chromium） DevTools 的空白实例，其中包含以下消息： "开发工具在 Internet Explorer 模式中不可用。 若要调试页面，请在 Internet Explorer 11 中打开它。 " **查看源**将启动记事本，**检查元素**将在 IE 模式下的上下文菜单中不可见。

这是因为在 IE 模式下，DevTools 中的多个组件（如网络和性能工具）将中断，而在 IE 模式下从 Chromium 切换到 Internet Explorer 11。 若要向我们提供反馈，请单击 `:)` 图标。

![在 IE 模式下启动的 DevTools](./media/ie-mode-devtools.png)

如果你要开发或维护基于 Internet Explorer 11 的网站或应用程序，我们建议导航到 Internet Explorer 11 中的同一页面。 在 Windows 10 上，你可以在 "Windows 附件" 下的 "开始" 菜单中找到 Internet Explorer 11 的快捷方式。 在 Windows 7 上，你可以在主 "开始" 菜单上找到 Internet Explorer 11。 然后，你可以通过在 `F12` 上下文菜单中按下或单击 "**检查元素**" 来启动 Internet Explorer DevTools。 若要了解有关如何使用这些工具的详细信息，请单击[此处](/previous-versions/windows/internet-explorer/ie-developer/samples/bg182326(v%3dvs.85))。

## 远程调试和 IE 模式

你可以启动启用了远程调试的 Microsoft Edge （Chromium），它通常是从命令行中的工具（如 Visual Studio 或代码启动边缘）：

`start msedge --remote-debugging-port=9222`

使用此命令行参数启动 Microsoft Edge （Chromium）时，IE 模式将不可用。 你仍可以导航到将以其他方式在 IE 模式下显示的网站或应用程序，但内容将通过 Chromium （而不是 Internet Explorer 11）呈现。 你可以预见，依赖 IE11 的这些页面部分（如 ActiveX 控件）将无法正确呈现。 "IE 模式标记" 将不再显示在地址栏中。

在完全关闭 Microsoft Edge （Chromium）之前，IE 模式将一直不可用。