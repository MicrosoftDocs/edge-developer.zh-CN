---
description: 此页面概述了 EdgeHTML 14 中的新增功能。
title: EdgeHTML 14 中的新功能和 Api
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘、web 开发、html、css、javascript、开发人员
ms.openlocfilehash: 7f3fcbbf84873fbf0851e1652bde48632e6c4378
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "10941906"
---
# EdgeHTML 14 中的新增功能  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

以下是 EdgeHTML 14 附带的更改，是 [Windows 10 周年更新](https://blogs.windows.com/windowsexperience/2016/06/29) \ (08/2016，内部版本 14393 \ ) 。  有关 Microsoft Edge 整体浏览器更改的概述，请参阅 [使用 Windows 10 周年更新介绍 EdgeHTML 14](https://blogs.windows.com/msedgedev/2016/08/04)。  

下面是以下更改列表的固定链接： [https://aka.ms/devguide_edgehtml_14](./edgehtml-14.md) 。  

## 新增功能  

### Extensions  

扩展是可用于向 Microsoft Edge 添加新功能或修改现有功能的小型程序。  扩展旨在通过提供对目标受众非常重要的小功能来改善用户的日常浏览体验。  Microsoft Edge 支持新的 HTML、JavaScript 和基于 CSS 的扩展模型。  此新模型是 Chrome 兼容的，这意味着现有的 Chrome 扩展开发人员能够将其扩展迁移到 Microsoft Edge，最小的更改。  有关详细信息，请查看 [Microsoft Edge 扩展](../../extensions/index.md) 开发人员文档。  

### 获取 API  
[获取 API](https://fetch.spec.whatwg.org#fetch-api)使用 `fetch` 获取资源的方法。  过去，这是通过提供的 `XMLHttpRequest` 。  提取不仅更易于使用，它还提供对请求和响应的较低级别的访问权限。  请阅读有关 Microsoft Edge 博客文章、 [获取 (或 XHR) 的 undeniable 限制的 ](https://blogs.windows.com/msedgedev/2016/05/24)详细信息，请参阅 Microsoft Edge 博客文章中的获取 API。  

### JavaScript  

EdgeHTML 14 为 Chakra 提供了许多新的和实验性功能，JavaScript 引擎可提供 Microsoft Edge 的功能：  

#### 新增功能  

默认启用  

*   [默认参数](https://developer.microsoft.com/microsoft-edge/platform/status/defaultparameteres6) \ (ES2015 \ ) 
*   [求幂运算符](https://developer.microsoft.com/microsoft-edge/platform/status/exponentiationoperatores2016) \ (ES2016 \ ) 
*   [Array. 包含](https://developer.microsoft.com/microsoft-edge/platform/status/arrayprototypeincludeses2016) \ (ES2016 \ ) 
*   [对象. 值](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object/values) 和 [对象.](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object/entries) \ (ES2017 \ )   

#### 实验性 JavaScript 功能  

已启用 `about:flags`  

*   [模块](https://blogs.windows.com/msedgedev/2016/05/17) \ (ES2015 \ )   
*   [Async/await](https://developer.microsoft.com/microsoft-edge/platform/status/asyncfunctionses2016) \ (ES2017 \ )   
*   [Regex 符号](https://developer.microsoft.com/microsoft-edge/platform/status/regexpbuiltinses6) \ (ES2015 \ )   

有关进一步的详细信息，请查看 [预览 ES6 模块以及其他 ES2015、ES2016 和更高](https://blogs.windows.com/msedgedev/2016/05/17) 版本，以及 [异步代码在 Chakra 和 Microsoft EDGE 中具有 ES2016 Async 函数支持变得更容易](https://blogs.windows.com/msedgedev/2015/09/30)。  

### Web 身份验证 API  

FIDO 2.0 Web API  

Web 身份验证 \ (以前的 FIDO 2.0 \ ) API 在 Microsoft Edge 中，web 应用程序可以使用 [Windows Hello](https://www.microsoft.com/windows/comprehensive-security) 生物识别进行用户身份验证，以便你和你的用户可以避免密码管理的所有麻烦和风险，包括密码猜测、网络钓鱼和 keylogging 攻击。  当前 Microsoft Edge \ (`ms-` 前缀 \ ) 实现基于 Web 身份验证规范的早期草案，将来可能会发生更改。  阅读有关 Web 身份验证的详细信息：  [web 身份验证和 Windows Hello](../windows-integration/web-authentication.md)。

### Web 通知
Web 通知允许网站显示通知，以向用户发送有关网页和浏览器上下文的通知，让用户知道新消息或警报，并允许网站提高用户的参与范围。  Microsoft Edge 中的 Web 通知与 Windows 10 中的通知平台和操作中心完全集成，可通过系统为其他应用提供一致的体验，并轻松控制权限和静音时间。  有关详细信息，请查看 [Microsoft Edge 中的 Web 通知](https://blogs.windows.com/msedgedev/2016/05/16) 。  

### Web 语音 API
[Web 语音 API](https://dvcs.w3.org/hg/speech-api/raw-file/tip/speechapi.html)是由两部分组成的 JavaScript api：语音识别和语音合成 \ (或文本转换为语音 ) 。  现在，Microsoft Edge 仅支持语音合成。  语音合成涉及用户通过扬声器听到的语音转换文本。  有关详细信息，请查看 [Web 语音：语音合成](https://developer.mozilla.org/docs/Web/API/Web_Speech_API) 开发人员指南文章。  

## EdgeHTML 14 中的新 Api

下面是 EdgeHTML 14 中新 Api 的完整列表。  它们以的格式列出 `[interface name].[api name]` 。  

<iframe height='585' scrolling='no' title='EdgeHTML 14 中的新 Api' src='//codepen.io/MSEdgeDev/embed/oWMEPE/?height=585&theme-id=23761&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'><a href='https://codepen.io/MSEdgeDev/pen/oWMEPE/'>在 </a> CodePen 上的 MSEdgeDev (<a href='https://codepen.io/MSEdgeDev'> @MSEdgeDev) 查看 EdgeHTML 14 中的笔新 api </a> <a href='https://codepen.io'> </a> 。</iframe>  
