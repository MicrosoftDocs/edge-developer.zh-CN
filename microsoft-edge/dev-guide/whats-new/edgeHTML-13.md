---
description: 此页面概述了 EdgeHTML 13 中的新增功能。
title: EdgeHTML 13 中的新增功能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘、web 开发、html、css、javascript、开发人员
ms.openlocfilehash: 8fb9d6bd78af5d595e217fa2bf210632f4c1a61f
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10562615"
---
# EdgeHTML 13 中的新增功能
下面是在 Windows 10 的[第一个重大更新](https://blogs.windows.com/windowsexperience/2015/11/12/first-major-update-for-windows-10-available-today/)（11/2015，内部版本10586）中提供的 EdgeHTML 13 所附的更改。 有关 Microsoft edge 整体浏览器更改的概述，请参阅[介绍 Microsoft edge 第一个平台更新 EdgeHTML 13](https://blogs.windows.com/msedgedev/2015/11/16/introducing-edgehtml-13-our-first-platform-update-for-microsoft-edge/)。

下面是以下更改列表的固定链接： [https://aka.ms/devguide_edgehtml_13](https://aka.ms/devguide_edgehtml_13) 。

## 功能

### CSS
' ' EdgeHTML 13 支持新的 CSS 功能，包括：
* [CSS Mutability 伪类](https://developer.microsoft.com/microsoft-edge/platform/status/cssmutabilitypseudoclasses/)
* [CSS 范围伪类](https://developer.microsoft.com/microsoft-edge/platform/status/cssrangepseudoclasses/)
* CSS[初始](https://developer.microsoft.com/microsoft-edge/platform/status/cssinitialvalue/)和未[设置](https://developer.microsoft.com/microsoft-edge/platform/status/cssunsetvalue/)关键字

### 加密媒体扩展
Microsoft Edge 现在支持新的 unprefixed[加密媒体扩展](https://w3.org/TR/encrypted-media/)api。 加密媒体扩展（EME）将视频和音频元素扩展为启用数字版权管理（DRM）受保护的内容，而不使用插件。阅读有关 EME：[加密媒体扩展](https://docs.microsoft.com/microsoft-edge/dev-guide/multimedia/encrypted-media-extensions)的详细信息。

### 显卡

EdgeHTML 13 引入了以下图形更新：
* [画布椭圆](https://developer.microsoft.com/microsoft-edge/platform/status/canvas2dellipse/)
* [画布混合模式](https://developer.microsoft.com/microsoft-edge/platform/status/compositingandblendingincanvas2d/)
* [`<picture>` 元素](https://developer.microsoft.com/microsoft-edge/platform/status/pictureelement/)
* [SVG 外部内容](https://developer.microsoft.com/microsoft-edge/platform/status/svgexternalcontent/)

### JavaScript
EdgeHTML 13[在 Chakra 中包含重大改进和新增功能支持](https://blogs.windows.com/msedgedev/2015/09/30/asynchronous-code-gets-easier-with-es2016-async-function-support-in-chakra-and-microsoft-edge/)，JavaScript 引擎支持 Microsoft Edge，包括：

#### 新增功能（默认情况下处于打开状态）

* 默认情况下启用[.asm](https://developer.microsoft.com/microsoft-edge/platform/status/asmjs/?q=asm.js) （[博客文章](https://blogs.windows.com/msedgedev/2015/11/10/supercharging-javascript-performance-with-asm-js/)、[演示](https://dev.windows.com/microsoft-edge/testdrive/demos/chess/)）
* [类](https://developer.microsoft.com/microsoft-edge/platform/status/asmjs/?q=classes)（ES2015）

#### 实验性 JavaScript 功能（已启用，带有*关于：标志*）

* [Async 函数](https://developer.microsoft.com/microsoft-edge/platform/status/asyncfunctions/?q=async%20functions)（ES2016）
* [求幂运算符](https://developer.microsoft.com/microsoft-edge/platform/status/exponentiationoperatores2016/?q=exponentiation%20operator)（ES2016）
* [Destructuring](https://developer.microsoft.com/microsoft-edge/platform/status/destructuringES2015/?q=destructuring) （ES2015）

### 用户输入
EdgeHTML 13 中引入的以下功能改进了用户输入：
* [`<meter>` 元素](https://developer.microsoft.com/microsoft-edge/platform/status/meterelement/)
* [`oninvalid` 元素文档和窗口的事件处理程序](https://developer.microsoft.com/microsoft-edge/platform/status/oninvalideventhandler/)

### 指针锁
Microsoft Edge 现在支持指针锁定 API （以前称为鼠标锁定）以访问原始鼠标移动，将鼠标事件的目标锁定到单个元素，消除了鼠标移动距离一个方向的限制，以及从视图中删除光标。 


## EdgeHTML 13 "" "中的新 Api

下面是 EdgeHTML 13 中新 Api 的完整列表。 它们以 **[界面名称] 的格式列出。 [api 名称]**。
<iframe height='584' scrolling='no' title='EdgeHTML 13 中的新 Api' src='//codepen.io/MicrosoftEdgeDocumentation/embed/vmzxEY/?height=584&theme-id=23761&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>在 <a href='https://codepen.io/MicrosoftEdgeDocumentation/pen/vmzxEY/'> </a> CodePen 上的 Microsoft Edge 文档（@MicrosoftEdgeDocumentation）中查看 EdgeHTML 13 中的笔新 api <a href='http://codepen.io/MicrosoftEdgeDocumentation'> </a> <a href='http://codepen.io'> </a> 。</iframe>""''""''""
