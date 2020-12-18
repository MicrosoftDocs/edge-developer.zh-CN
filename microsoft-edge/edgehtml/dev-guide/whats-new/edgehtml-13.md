---
description: 此页面概述了 EdgeHTML 13 中的新增功能。
title: EdgeHTML 13 中的新功能和 API
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge， Web 开发， html， css， javascript， 开发人员
ms.date: 12/02/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 2119e576a637d5f78e073f49a3cb1868a7ce1ca4
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232680"
---
# EdgeHTML 13 中的新增功能  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

以下是 EdgeHTML 13 附带的更改，该引擎在 Windows 10 [](https://blogs.windows.com/windowsexperience/2015/11/12) \ (11/2015 内部版本 10586\) 的第一个主要更新中为 Microsoft Edge 浏览器提供电源。  有关整个 Microsoft Edge 浏览器更改的概述，请参阅介绍 [EdgeHTML 13，](https://blogs.windows.com/msedgedev/2015/11/16)这是 Microsoft Edge 的第一个平台更新。  

下面是以下更改列表的 permalink： [https://aka.ms/devguide_edgehtml_13](./edgehtml-13.md)  

## 功能  

### CSS  

EdgeHTML 13 支持新的 CSS 功能，包括：  

*   [CSS 可变性伪类](https://developer.microsoft.com/microsoft-edge/platform/status/cssmutabilitypseudoclasses)  
*   [CSS 范围伪类](https://developer.microsoft.com/microsoft-edge/platform/status/cssrangepseudoclasses)  
*   CSS[](https://developer.microsoft.com/microsoft-edge/platform/status/cssinitialvalue)初始[关键字和未设置](https://developer.microsoft.com/microsoft-edge/platform/status/cssunsetvalue)关键字  

### 加密媒体扩展  

Microsoft Edge 现在支持新的未准备加密 [媒体](https://w3.org/TR/encrypted-media) 扩展 API。  加密媒体扩展 \ (EME\) 扩展了视频和音频元素，以启用数字版权管理 \ (DRM\) 保护的内容，而无需使用插件。 阅读有关 EME：  [加密媒体扩展的更多内容](https://developer.mozilla.org/docs/Web/API/Encrypted_Media_Extensions_API)。  

### 显卡  

EdgeHTML 13 引入了以下图形更新：  

*   [画布椭圆](https://developer.microsoft.com/microsoft-edge/platform/status/canvas2dellipse)  
*   [画布混合模式](https://developer.microsoft.com/microsoft-edge/platform/status/compositingandblendingincanvas2d)  
*   [<picture> 元素](https://developer.microsoft.com/microsoft-edge/platform/status/pictureelement)  
*   [SVG 外部内容](https://developer.microsoft.com/microsoft-edge/platform/status/svgexternalcontent)  

### JavaScript  

EdgeHTML 13 包括主要改进和 [**（](https://blogs.windows.com/msedgedev/2015/09/30)支持 Microsoft Edge 的 JavaScript 引擎）中的新功能支持，包括：  

#### 新功能  

默认启用  

*   [asm.js](https://developer.microsoft.com/microsoft-edge/platform/status/asmjs/?q=asm.js) \ ([博客文章](https://blogs.windows.com/msedgedev/2015/11/10) [demo \) ](https://dev.windows.com/microsoft-edge/testdrive/demos/chess)  
*   [类](https://developer.microsoft.com/microsoft-edge/platform/status/asmjs/?q=classes) \ (ES2015\)   

#### 实验 JavaScript 功能  

已启用 `about:flags`  

*   [异步函数](https://developer.microsoft.com/microsoft-edge/platform/status/asyncfunctions/?q=async%20functions) \ (ES2016\)   
*   [Exponentiation 运算符](https://developer.microsoft.com/microsoft-edge/platform/status/exponentiationoperatores2016/?q=exponentiation%20operator) \ (ES2016\)   
*   [取消构造](https://developer.microsoft.com/microsoft-edge/platform/status/destructuringES2015/?q=destructuring) \ (ES2015\)   

### 用户输入  

EdgeHTML 13 中引入的以下功能改进了用户输入：  

*   [\<meter\> 元素](https://developer.microsoft.com/microsoft-edge/platform/status/meterelement)  
*   [元素文档和窗口的 oninvalid 事件处理程序](https://developer.microsoft.com/microsoft-edge/platform/status/oninvalideventhandler)  

### 指针锁定  

Microsoft Edge 现在支持指针锁定 API \ (以前称为"鼠标锁定"\) ，用于访问原始鼠标移动、将鼠标事件的目标锁定为单个元素、消除鼠标在单个方向上移动距离的限制以及从视图中删除光标。  

## EdgeHTML 13 中的新 API  

下面是 EdgeHTML 13 中新 API 的完整列表。  它们以 . `[interface name].[api name]`  

<iframe height='584' scrolling='no' title='EdgeHTML 13 中的新 API' src='//codepen.io/MicrosoftEdgeDocumentation/embed/vmzxEY/?height=584&theme-id=23761&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width:  100%;'>请参阅 EdgeHTML 13 中的笔新 API（由 Microsoft Edge 文档 <a href='https://codepen.io/MicrosoftEdgeDocumentation/pen/vmzxEY/'> </a> <a href='http://codepen.io/MicrosoftEdgeDocumentation'> (@MicrosoftEdgeDocumentation) </a> <a href='http://codepen.io'> CodePen 上 </a> ）。</iframe>  
