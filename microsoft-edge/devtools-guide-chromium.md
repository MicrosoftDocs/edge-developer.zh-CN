---
description: 了解 Microsoft Edge (Chromium) 开发人员工具
title: Microsoft Edge (Chromium) 开发人员工具
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/08/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: ba925c402d33ba75c558006c7c43c5dc05515911
ms.sourcegitcommit: 6b577cb118f34f3ff2c65eab2908b65f155dc151
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/09/2020
ms.locfileid: "11003934"
---
# Microsoft Edge (Chromium) 开发人员工具  

Microsoft Edge 采用了 Chromium open 源项目以创建更好的 web 兼容性，并减少不同基础 web 平台的碎片。  此更改使你能够更轻松地在 Microsoft Edge 中构建和测试你的网站，并确保每个网站在不同的基于 Chromium 的浏览器 (（如 Google Chrome、Vivaldi、Opera 或 Brave \ ) ）中都可以正常工作。  

随着网络在不断扩大的各种设备类型数组中的使用日益增加，测试网站所涉及的复杂性和开销也随之增加。 由于 web 开发人员在小型公司 (尤其是在小型公司 ) 必须针对如此多的不同系统进行测试，因此你可能会发现几乎无法确保网站在所有设备类型和所有浏览器上都能正常工作。  既然 Microsoft Edge 基于 Chromium，Microsoft Edge 团队通过将 Microsoft Edge web 平台与其他基于 Chromium 的浏览器相协调，并在浏览器内以及你 (每天使用的其他开发人员工具（如 Visual Studio Code \ ) ）中提供了最佳的开发工具体验。  

如果您要签出 Microsoft Edge，并且主要是在基于 Chromium 的浏览器中开发，则应立即体验。  Microsoft Edge \ (Chromium \ ) 开发人员工具的工作方式与你已了解和使用的开发人员工具相同。  有关详细信息，请参阅 [Microsoft Edge (Chromium) DevTools 中的新增功能][DevtoolsGuideChromiumWhatsNewIndex]。  

:::image type="complex" source="./devtools-guide-chromium/media/devtools.png" alt-text="Microsoft Edge (Chromium) DevTools&quot;:::
   Microsoft Edge (Chromium) DevTools  
:::image-end:::  

如果您要签出下一版本的 Microsoft Edge，并且以前是在 Microsoft Edge \ (EdgeHTML \ ) 中开发的，现在您有了一些非常好的新工具，可让您在 Microsoft Edge 中更轻松、更快地构建和测试您的网站！  

## 打开 DevTools  

如果您以前从未使用过 DevTools，则 Microsoft Edge 开发人员工具是一组直接内置于 Microsoft Edge 浏览器中的工具。  通过这些 DevTools，你可以执行以下操作。  

*   检查并对 HTML 网站进行更改  
*   编辑 CSS 并立即查看预览您的网站呈现方式  
*   查看 `console.log()` 前端 JavaScript 代码中的所有语句  
*   通过设置断点并逐行逐行执行调试来调试你的脚本  

直接在浏览器中。  以下是 DevTools 提供的一些功能的示例，可使你在 Microsoft Edge 中构建和测试网站变得更加轻松快捷。  

打开 DevTools  

*   按 `F12` 
*   按 `Ctrl` + `Shift` + `I` `Command` + `Option` + `I` macOS \ ) 上的 &quot;Windows \ (&quot;  

如果要查看网站上某个元素的 HTML 或 CSS，请右键单击该元素，然后选择 &quot; **检查** &quot; 以跳转到 &quot;元素&quot; 面板。  你还可以按 `Ctrl` + `Shift` + `C` `Command` + `Option` + `C` macOS \ ) 上的 Windows \ (在 &quot;**检查元素&quot; 模式**下打开 DevTools，以便你在网站上选择元素并在 &quot;**元素**" 面板中查看 HTML 和 CSS。  

如果您想要查看前端 JavaScript 代码中的日志或快速运行某些脚本，请按 `Ctrl` + `Shift` + `J` Windows 或 `Command` + `Option` + `J` macOS 以启动 DevTools 中的控制台面板。  

## 核心工具  

:::image type="complex" source="./devtools-guide-chromium/media/devtools-core-tools.png" alt-text="Microsoft Edge (Chromium) DevTools&quot;:::
   Microsoft Edge (Chromium) DevTools  
:::image-end:::  

如果您要签出下一版本的 Microsoft Edge，并且以前是在 Microsoft Edge \ (EdgeHTML \ ) 中开发的，现在您有了一些非常好的新工具，可让您在 Microsoft Edge 中更轻松、更快地构建和测试您的网站！  

## 打开 DevTools  

如果您以前从未使用过 DevTools，则 Microsoft Edge 开发人员工具是一组直接内置于 Microsoft Edge 浏览器中的工具。  通过这些 DevTools，你可以执行以下操作。  

*   检查并对 HTML 网站进行更改  
*   编辑 CSS 并立即查看预览您的网站呈现方式  
*   查看 `console.log()` 前端 JavaScript 代码中的所有语句  
*   通过设置断点并逐行逐行执行调试来调试你的脚本  

直接在浏览器中。  以下是 DevTools 提供的一些功能的示例，可使你在 Microsoft Edge 中构建和测试网站变得更加轻松快捷。  

打开 DevTools  

*   按 `F12` 
*   按 `Ctrl` + `Shift` + `I` `Command` + `Option` + `I` macOS \ ) 上的 &quot;Windows \ (&quot;  

如果要查看网站上某个元素的 HTML 或 CSS，请右键单击该元素，然后选择 &quot; **检查** &quot; 以跳转到 &quot;元素&quot; 面板。  你还可以按 `Ctrl` + `Shift` + `C` `Command` + `Option` + `C` macOS \ ) 上的 Windows \ (在 &quot;**检查元素&quot; 模式**下打开 DevTools，以便你在网站上选择元素并在 &quot;**元素**" 类别中浏览 DevTools 扩展或搜索特定的扩展名。  

您也可以添加 [Chrome Web 应用商店][GoogleChromeWebstoreExtensions]的扩展。  

:::image type="complex" source="./devtools-guide-chromium/media/allow-extensions-from-stores.png" alt-text="Microsoft Edge (Chromium) DevTools&quot;:::
   Microsoft Edge (Chromium) DevTools  
:::image-end:::  

如果您要签出下一版本的 Microsoft Edge，并且以前是在 Microsoft Edge \ (EdgeHTML \ ) 中开发的，现在您有了一些非常好的新工具，可让您在 Microsoft Edge 中更轻松、更快地构建和测试您的网站！  

## 打开 DevTools  

如果您以前从未使用过 DevTools，则 Microsoft Edge 开发人员工具是一组直接内置于 Microsoft Edge 浏览器中的工具。  通过这些 DevTools，你可以执行以下操作。  

*   检查并对 HTML 网站进行更改  
*   编辑 CSS 并立即查看预览您的网站呈现方式  
*   查看 `console.log()` 前端 JavaScript 代码中的所有语句  
*   通过设置断点并逐行逐行执行调试来调试你的脚本  

直接在浏览器中。  以下是 DevTools 提供的一些功能的示例，可使你在 Microsoft Edge 中构建和测试网站变得更加轻松快捷。  

打开 DevTools  

*   按 `F12` 
*   按 `Ctrl` + `Shift` + `I` `Command` + `Option` + `I` macOS \ ) 上的 &quot;Windows \ (&quot;  

如果要查看网站上某个元素的 HTML 或 CSS，请右键单击该元素，然后选择 &quot; **检查** &quot; 以跳转到 &quot;元素&quot; 面板。  你还可以按 `Ctrl` + `Shift` + `C` `Command` + `Option` + `C` macOS \ ) 上的 Windows \ (在 &quot;**检查元素&quot; 模式**下打开 DevTools，以便你在网站上选择元素并在 &quot;**元素**" 以将你的 DevTools 扩展添加到 Microsoft Edge！  

:::image type="complex" source="./devtools-guide-chromium/media/install-extension-from-chrome-store.png" alt-text="Microsoft Edge (Chromium) DevTools&quot;:::
   Microsoft Edge (Chromium) DevTools  
:::image-end:::  

如果您要签出下一版本的 Microsoft Edge，并且以前是在 Microsoft Edge \ (EdgeHTML \ ) 中开发的，现在您有了一些非常好的新工具，可让您在 Microsoft Edge 中更轻松、更快地构建和测试您的网站！  

## 打开 DevTools  

如果您以前从未使用过 DevTools，则 Microsoft Edge 开发人员工具是一组直接内置于 Microsoft Edge 浏览器中的工具。  通过这些 DevTools，你可以执行以下操作。  

*   检查并对 HTML 网站进行更改  
*   编辑 CSS 并立即查看预览您的网站呈现方式  
*   查看 `console.log()` 前端 JavaScript 代码中的所有语句  
*   通过设置断点并逐行逐行执行调试来调试你的脚本  

直接在浏览器中。  以下是 DevTools 提供的一些功能的示例，可使你在 Microsoft Edge 中构建和测试网站变得更加轻松快捷。  

打开 DevTools  

*   按 `F12` 
*   按 `Ctrl` + `Shift` + `I` `Command` + `Option` + `I` macOS \ ) 上的 &quot;Windows \ (&quot;  

如果要查看网站上某个元素的 HTML 或 CSS，请右键单击该元素，然后选择 &quot; **检查** &quot; 以跳转到 &quot;元素&quot; 面板。  你还可以按 `Ctrl` + `Shift` + `C` `Command` + `Option` + `C` macOS \ ) 上的 Windows \ (在 &quot;**检查元素&quot; 模式**下打开 DevTools，以便你在网站上选择元素并在 &quot;**元素**"  
