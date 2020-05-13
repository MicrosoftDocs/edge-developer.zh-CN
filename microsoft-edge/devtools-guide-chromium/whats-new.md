---
description: 2019年3月在 Microsoft Edge （Chromium） DevTools 中添加的功能
title: 2019年3月的 Microsoft Edge （Chromium） DevTools 中的新增功能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: bf1919b0ab46df378880d664dd4e59aee96605e5
ms.sourcegitcommit: 24430258f363b7dd85f7067afd4565bf102b4a1f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "10645320"
---
# Microsoft Edge 中的新增功能（Chromium） DevTools

非常感谢你试用下一版本的 Microsoft Edge 的预览版！ 在此版本中，我们通过使用 Chromium 开源项目，在 Microsoft Edge 的基础 web 平台中进行了重大转变。 通过此更改，你可以更轻松地在 Microsoft Edge 中构建和测试你的网站，并确保即使你的用户在不同的基于 Chromium 的浏览器中浏览（如 Google Chrome、Vivaldi、Opera 或 Brave），它们仍将按预期工作。

## 新的 Microsoft Edge （Chromium） DevTools

如果您要签出 Microsoft Edge，并且主要是在基于 Chromium 的浏览器中开发，则应立即体验。 Microsoft Edge （Chromium）开发人员工具与你已了解和使用的开发人员工具完全一样！

![Microsoft Edge （Chromium） DevTools](./media/devtools.png)

如果你要签出下一版本的 Microsoft Edge，并且主要是在 Microsoft Edge （EdgeHTML）中开发的，我们将获得一些非常好的新工具，让你能够更轻松、更快地在 Microsoft Edge 中构建和测试你的网站！ 若要了解有关这些新工具的详细信息，请参阅[Microsoft Edge （Chromium） DevTools 指南](../devtools-guide-chromium.md)。

## 适用于 DevTools 的全新深色和浅色主题

我们为 DevTools 设计了一些新的深色和浅色主题，我们认为你会喜欢！ 默认情况下，Microsoft Edge （Chromium） DevTools 将使用深色主题。 若要更改 DevTools 的主题，请按 `Fn`  +  `F1` Windows 或 Mac 或使用 DevTools 右上角的按钮导航到 "设置" `...` 。

![Microsoft Edge （Chromium） DevTools 主菜单](./media/devtools-main-menu.png)

从 "设置" 中，您可以更改 DevTools 的主题。 如果你喜欢 DevTools 在基于 Chromium 的浏览器中的显示方式，则可以通过分别选择 "**深色" （Chromium** ）或 "**浅色" （Chromium）** 主题，使 Microsoft Edge （Chromium） DevTools 看起来完全类似。 

## 从 VS 代码调试 Microsoft Edge （Chromium）

通过[适用于 Microsoft Edge](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-edge)和代码扩展的调试器，现在可以直接从 VS 代码调试 microsoft Edge （EdgeHTML）和 microsoft Edge （Chromium）！

![用于边缘与代码扩展的调试器](./media/vscode-debugger.png)

若要从 VS 代码启动 Microsoft Edge （Chromium）而不是 Microsoft Edge （EdgeHTML），需要 `version` 使用要启动的 Microsoft edge **launch.json** （ `dev` 、 `beta` 或）版本将属性添加到现有的启动配置 `canary` 。 下面是一个示例**启动**配置，它将启动将 "Chromium" 版本的 Microsoft Edge （）设置为[bing.com](https://www.bing.com/)：

```json
{
    "type": "edge",
    "request": "launch",
    "version": "canary",
    "name": "Launch Microsoft Edge (Chromium) Canary against Bing",
    "url": "https://bing.com"
}
```

有关详细信息，请参阅[如何从 VS 代码调试 Microsoft Edge （Chromium）](../visual-studio-code/debugger-for-edge.md)。

## Edge DevTools 协议更新

通过 Microsoft Edge 基础 web 平台中的班次，Edge DevTools 协议将不会收到任何进一步的更新。 Microsoft Edge （Chromium） DevTools 将使用 Chrome DevTools 协议或 CDP。 若要参考 CDP 中的域和方法的文档，请参阅[cdp 查看器](https://chromedevtools.github.io/devtools-protocol/tot/Accessibility)。

在下一版本的 Microsoft Edge 中，将不支持任何带前缀的方法 `ms` 。 若要了解有关如何在 Microsoft Edge （Chromium）中使用 CDP 的详细信息，请参阅[DevTools 协议（Chromium）](../devtools-protocol-chromium.md)。

## 已知问题

从 Microsoft Edge （Chromium） DevTools 到托管在第三方网站上的内容的许多链接已被暂时删除。 一旦可以替换这些链接，我们会立即将其添加回 DevTools。


从 Microsoft Edge （Chromium）调试 Android 设备上的 web 内容时，当您单击 "**远程设备**" 工具中的 "**检查**" 按钮时，启动的 DevTools 版本可能与 Android 设备上的浏览器版本不匹配。 因此，你可能会在 DevTools 中看到不能在 Android 设备上使用浏览器的新功能。 如果这是你遇到的问题，我们希望听到它，请您的[反馈](../devtools-guide-chromium.md#getting-in-touch-with-the-microsoft-edge-devtools-team)！

最后，Windows 和 Mac 上的 Visual Studio 尚不支持 Microsoft Edge （Chromium）。 请先注册[此处](https://visualstudio.microsoft.com/vs/preview/)，了解当我们拥有 Visual Studio 预览版（支持在 Microsoft Edge （Chromium）内为 ASP.NET 项目进行 JavaScript 调试时）的第一个版本！  
