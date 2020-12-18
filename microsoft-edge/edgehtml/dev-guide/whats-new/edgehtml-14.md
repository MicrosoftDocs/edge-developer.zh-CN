---
description: 此页面概述了 EdgeHTML 14 中的新增功能。
title: EdgeHTML 14 中的新功能和 API
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge， Web 开发， html， css， javascript， 开发人员
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: c99dcb4efb253959d55d96a13ca2249eb5164b68
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232369"
---
# EdgeHTML 14 中的新增功能  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

下面是 EdgeHTML 14 附带的更改，自 [Windows 10](https://blogs.windows.com/windowsexperience/2016/06/29) 周年更新 \ (08/2016 内部版本 14393\) 起。  有关整个 Microsoft Edge 浏览器更改的概述，请参阅介绍 [EdgeHTML 14 和 Windows 10 周年更新](https://blogs.windows.com/msedgedev/2016/08/04)。  

下面是以下更改列表的 permalink： [https://aka.ms/devguide_edgehtml_14](./edgehtml-14.md)  

## 新功能  

### Extensions  

扩展是可用于向 Microsoft Edge 添加新功能或修改现有功能的小程序。  扩展旨在通过提供对目标受众非常重要的小范围功能来改进用户日常浏览体验。  Microsoft Edge 支持新的 HTML、JavaScript 和基于 CSS 的扩展模型。  此新模型与 Chrome 兼容，这意味着现有 Chrome 扩展开发人员将能够将其扩展迁移到 Microsoft Edge，更改最少。  有关详细信息，请查看 Microsoft [Edge 扩展开发人员](../../extensions/index.md) 文档。  

### 提取 API  
Fetch [API](https://fetch.spec.whatwg.org#fetch-api) 利用 `fetch` 该方法获取资源。  过去，这是通过 `XMLHttpRequest` .  不仅提取使用起来更简单，它还提供对请求和响应的较低级别访问。  在 Microsoft Edge 博客文章"Fetch ([或 XHR ](https://blogs.windows.com/msedgedev/2016/05/24)) 。  

### JavaScript  

EdgeHTML 14 为为 Microsoft Edge 提供电源的 JavaScript 引擎 Chakra 带来了许多新的实验性功能：  

#### 新功能  

默认启用  

*   [默认参数](https://developer.microsoft.com/microsoft-edge/platform/status/defaultparameteres6) \ (ES2015\) 
*   [Exponentiation 运算符](https://developer.microsoft.com/microsoft-edge/platform/status/exponentiationoperatores2016) \ (ES2016\) 
*   [Array.prototype.includes](https://developer.microsoft.com/microsoft-edge/platform/status/arrayprototypeincludeses2016) \ (ES2016\) 
*   [Object.values](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object/values) 和 [object.entries](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object/entries) \ (ES2017\)   

#### 实验 JavaScript 功能  

已启用 `about:flags`  

*   [模块](https://blogs.windows.com/msedgedev/2016/05/17) \ (ES2015\)   
*   [Async/await](https://developer.microsoft.com/microsoft-edge/platform/status/asyncfunctionses2016) \ (ES2017\)   
*   [正则表达式符号](https://developer.microsoft.com/microsoft-edge/platform/status/regexpbuiltinses6) \ (ES2015\)   

有关更多详细信息，请查看从 [ES2015、ES2016](https://blogs.windows.com/msedgedev/2016/05/17) 及以后预览 ES6 模块和更多模块，异步代码在 Chakra 和 Microsoft Edge 中通过 [ES2016 Async](https://blogs.windows.com/msedgedev/2015/09/30)函数支持变得更简单。  

### Web 身份验证 API  

FIDO 2.0 Web API  

Microsoft Edge 中的 Web 身份验证 \ (以前称为 FIDO 2.0\) API，允许 Web 应用程序使用 [Windows Hello](https://www.microsoft.com/windows/comprehensive-security) 生物识别进行用户身份验证，以便你和用户可以避免密码管理的所有麻烦和风险，包括密码猜测、网络钓鱼和密钥记录攻击。  当前的 Microsoft Edge \ (前缀\) 实现基于早期 Web 身份验证规范草稿，将来可能会 `ms-` 更改。  阅读有关 Web 身份验证  [：Web 身份验证和 Windows Hello 的更多内容](../windows-integration/web-authentication.md)。

### Web 通知
Web 通知允许网站显示通知，以在网页和浏览器上下文之外向用户发出警报，使用户随时了解新消息或警报，并允许网站提高用户参与度。  Microsoft Edge 中的 Web 通知与 Windows 10 中的通知平台和操作中心完全集成，为系统内的其他应用提供一致的体验，并轻松控制权限和安静时间。  有关详细信息， [请查看 Microsoft Edge](https://blogs.windows.com/msedgedev/2016/05/16) 中的 Web 通知。  

### Web 语音 API
Web 语音 API 是一个 JavaScript [API，](https://dvcs.w3.org/hg/speech-api/raw-file/tip/speechapi.html) 由两部分组成：语音识别和语音合成 \ (或文本到语音\) 。  目前，Microsoft Edge 仅支持语音合成。  语音合成涉及将文本转换为用户通过扬声器听到的语音。  有关详细信息， [请查看 Web 语音：语音合成](https://developer.mozilla.org/docs/Web/API/Web_Speech_API) 开发人员指南文章。  

## EdgeHTML 14 中的新 API

以下是 EdgeHTML 14 中新 API 的完整列表。  它们以 . `[interface name].[api name]`  

<iframe height='585' scrolling='no' title='EdgeHTML 14 中的新 API' src='//codepen.io/MSEdgeDev/embed/oWMEPE/?height=585&theme-id=23761&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>See the Pen <a href='https://codepen.io/MSEdgeDev/pen/oWMEPE/'> New API in EdgeHTML 14 </a> by MSEdgeDev (@MSEdgeDev <a href='https://codepen.io/MSEdgeDev'>) on </a> <a href='https://codepen.io'> </a> CodePen.</iframe>  
