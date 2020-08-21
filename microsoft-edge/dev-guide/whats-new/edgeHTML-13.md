---
description: 此页面概述了 EdgeHTML 13 中的新增功能。
title: EdgeHTML 13 中的新功能和 API
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘， Web 开发， html， css， javascript， developer
ms.openlocfilehash: 033b8dacb107492624f3b8c7775a47285c9893dd
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "10941913"
---
# EdgeHTML 13 中的新增功能  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

下面是随 EdgeHTML 13 提供的更改，即 Windows 10 / (11/2015（内部版本 10586\) ）的首要更新中提供 Microsoft Edge 浏览器。 [first major update](https://blogs.windows.com/windowsexperience/2015/11/12)  有关 Microsoft Edge 浏览器整体 Microsoft Edge 浏览器的更改的概述， [请参阅 EdgeHTML 13（Microsoft Edge 的第一个平台更新](https://blogs.windows.com/msedgedev/2015/11/16)）。  

下面是下列更改列表的句号  [https://aka.ms/devguide_edgehtml_13](./edgehtml-13.md) ：。  

## 功能  

### CSS  

Microsoft EdgeHTML 13 支持新的 CSS 功能，其中包括：  

*   [CSS 多位功能强制性下](https://developer.microsoft.com/microsoft-edge/platform/status/cssmutabilitypseudoclasses)  
*   [CSS 范围分类](https://developer.microsoft.com/microsoft-edge/platform/status/cssrangepseudoclasses)  
*   CSS[初始和](https://developer.microsoft.com/microsoft-edge/platform/status/cssinitialvalue)[取消设置关](https://developer.microsoft.com/microsoft-edge/platform/status/cssunsetvalue)键字  

### 加密媒体扩展  

Microsoft Edge 现在支持新的未加密的加密 [媒体扩展](https://w3.org/TR/encrypted-media) API。  加密媒体扩展 \ (EME\) 扩展视频和音频元素，而无需使用插件，直接启用数字版权管理 \ (DRM\) 保护内容。 阅读有关  [EME：加密媒体扩展的详细信息](https://developer.mozilla.org/docs/Web/API/Encrypted_Media_Extensions_API)。  

### 显卡  

EdgeHTML 13 引入了以下图形更新：  

*   [画布省略号](https://developer.microsoft.com/microsoft-edge/platform/status/canvas2dellipse)  
*   [画布混合模式](https://developer.microsoft.com/microsoft-edge/platform/status/compositingandblendingincanvas2d)  
*   [<picture> 元素](https://developer.microsoft.com/microsoft-edge/platform/status/pictureelement)  
*   [SVG 外部内容](https://developer.microsoft.com/microsoft-edge/platform/status/svgexternalcontent)  

### JavaScript  

EdgeHTML 13 [包括重大改进和在 Chakra（](https://blogs.windows.com/msedgedev/2015/09/30)这是 JavaScript 引强权 Microsoft Edge）中提供的新功能支持，包括：  

#### 新增功能  

默认启用  

*   [asm.js](https://developer.microsoft.com/microsoft-edge/platform/status/asmjs/?q=asm.js) \pded _ ([博客文章时，](https://blogs.windows.com/msedgedev/2015/11/10)[演示](https://dev.windows.com/microsoft-edge/testdrive/demos/chess)\)   
*   [Classes](https://developer.microsoft.com/microsoft-edge/platform/status/asmjs/?q=classes) \ (ES2015\)   

#### 实质 JavaScript 功能  

与 `about:flags`  

*   [异步函数](https://developer.microsoft.com/microsoft-edge/platform/status/asyncfunctions/?q=async%20functions) \ (ES2016\)   
*   [指数运算符](https://developer.microsoft.com/microsoft-edge/platform/status/exponentiationoperatores2016/?q=exponentiation%20operator) \ (ES2016\)   
*   [将](https://developer.microsoft.com/microsoft-edge/platform/status/destructuringES2015/?q=destructuring) \ (ES2015\)   

### 用户输入  

在 EdgeHTML 13 中引入的以下功能改进了用户输入：  

*   [<meter> 元素](https://developer.microsoft.com/microsoft-edge/platform/status/meterelement)  
*   [对于元素文档和窗口](https://developer.microsoft.com/microsoft-edge/platform/status/oninvalideventhandler)  

### 指针锁  

Microsoft Edge 现在支持指针 Lock API / (之前称为鼠标 Lock\) 以访问原始鼠标移动，锁定鼠标事件的目标，消除鼠标动作在单个方向的大小上限，以及从视图中删除光标。  

## EdgeHTML 13 中的新 API  

下面是 EdgeHTML 13 中的新 API 的完整列表。  它们以格式列出 `[interface name].[api name]` 。  

<iframe height='584' scrolling='no' title='EdgeHTML 13 中的新 API' src='//codepen.io/MicrosoftEdgeDocumentation/embed/vmzxEY/?height=584&theme-id=23761&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width:  100%;'>在 <a href='https://codepen.io/MicrosoftEdgeDocumentation/pen/vmzxEY/'> CodePen 上查看 Microsoft Edge 的 </a> Microsoft Edge (@MicrosoftEdgeDocumentation) 中的笔 <a href='http://codepen.io/MicrosoftEdgeDocumentation'> 新 </a> <a href='http://codepen.io'> </a> API。</iframe>  
