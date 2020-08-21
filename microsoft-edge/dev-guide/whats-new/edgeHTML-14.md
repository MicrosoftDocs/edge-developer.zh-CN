---
description: 此页面概述了 EdgeHTML 14 中的新增功能。
title: EdgeHTML 14 中的新功能和 API
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘， Web 开发， html， css， javascript， developer
ms.openlocfilehash: 7f3fcbbf84873fbf0851e1652bde48632e6c4378
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "10941906"
---
# EdgeHTML 14 中的新增功能  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

截止到如下 Windows 10 年纪元更新 [\ (08/2016（](https://blogs.windows.com/windowsexperience/2016/06/29) 内部版本 14393\) ）随即随 EdgeHTML 14 提供的更改。  有关 Microsoft Edge 浏览器的整体更改概述，请参阅 Windows 10 将更新 [中的 EdgeHTML 14 引入](https://blogs.windows.com/msedgedev/2016/08/04)。  

下面是下列更改列表的句号 [https://aka.ms/devguide_edgehtml_14](./edgehtml-14.md) ：。  

## 新增功能  

### Extensions  

扩展是可用于向 Microsoft Edge 添加新功能或修改现有功能的小程序。  扩展专用于提供对目标受受触受用户很重要的错误，改进用户的日常浏览体验。  Microsoft Edge 支持新的 HTML、JavaScript 和 CSS 扩展模型。  此新模型是与 Chrome 兼容的，这意味着现有 Chrome 扩展开发人员能够只需最少的更改将扩展迁移到 Microsoft Edge。  有关详细信息，请查看 [Microsoft Edge 扩展开发](../../extensions/index.md) 人员文档。  

### 提出 API  
[获取 API](https://fetch.spec.whatwg.org#fetch-api)利用获取 `fetch` 资源的方法。  这过来，这是在此时会成功的 `XMLHttpRequest` 。  使用速度不仅更加简单，还可提供对请求和响应较低的级别访问权限。  在 Microsoft Edge 博客文章中阅读有关提取 API 的详细信息 [， (提取文件 () 取无法 ](https://blogs.windows.com/msedgedev/2016/05/24)。  

### JavaScript  

EdgeHTML 14 为 Chakra（JavaScript 引入 Microsoft Edge）提供了许多新的和实用功能。  

#### 新增功能  

默认启用  

*   [Default parameters](https://developer.microsoft.com/microsoft-edge/platform/status/defaultparameteres6) \ (ES2015\) 
*   [指数运算符](https://developer.microsoft.com/microsoft-edge/platform/status/exponentiationoperatores2016) \ (ES2016\) 
*   [Array.prototype.includes](https://developer.microsoft.com/microsoft-edge/platform/status/arrayprototypeincludeses2016) \ (ES2016\) 
*   [Object.values](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object/values) and [object.entries](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object/entries) \ (ES2017\)   

#### 实质 JavaScript 功能  

与 `about:flags`  

*   [模块](https://blogs.windows.com/msedgedev/2016/05/17) \ (ES2015\)   
*   [Async/await](https://developer.microsoft.com/microsoft-edge/platform/status/asyncfunctionses2016) \ (ES2017\)   
*   [Regex 符号 \ (](https://developer.microsoft.com/microsoft-edge/platform/status/regexpbuiltinses6) ES2015\)   

有关详细信息，请查看 [ES2015、ES2016](https://blogs.windows.com/msedgedev/2016/05/17) 及更高版本以及空格以及异步代码中的 ES2016 异步函数支持更加轻松。了解详细信息，请查看 ES2016、ES2016 及以上代码中的 D6 模块及更高版本。在 Chakra 和 Microsoft Edge 中，需轻松完成 [ES2016 异](https://blogs.windows.com/msedgedev/2015/09/30)步函数支持。  

### Web 身份验证 API  

FIDO 2.0 Web API  

Microsoft Edge 中的 Web 身份验证 \ (预览版 4.0\) API 支持 Web 应用程序使用 [Windows Hello](https://www.microsoft.com/windows/comprehensive-security) 生物识别进行用户身份验证，以便你和你的用户可以避免密码管理的所有功能，包括密码来宾、网络处理和密钥记录问题。  当前的 Microsoft Edge \ (`ms-` 前缀\) 实现基于早期的 Web 身份验证规范草稿并且在将来可能更改。  了解有关 Web 身份验证的更多[信息：Web 身份验证和 Windows Hello。](../windows-integration/web-authentication.md)

### Web 通知
借助 Web 通知，网站可显示通知，提高用户在网页及浏览器的上下文之外，让用户了解新消息或通知并允许网站改善用户的参与度。  Microsoft Edge 中的 Web 通知与 Windows 10 中的通知平台和操作中心集成，提供系统上其他应用的一致体验，并可轻松控制权限和免费时间。  有关详细信息， [请查看 Microsoft Edge 中的](https://blogs.windows.com/msedgedev/2016/05/16) Web 通知。  

### Web 语音 API
[Web 语音 API 是](https://dvcs.w3.org/hg/speech-api/raw-file/tip/speechapi.html)由两个部分组成的 JavaScript API：语音识别和语音合成 \ (或文本到 speech\) 。  目前 Microsoft Edge 仅支持语音合成。  语音合成涉及到用户听到的文本转换问题。  查看 [Web 语音：语音合](https://developer.mozilla.org/docs/Web/API/Web_Speech_API) 成开发人员指南文章，了解详细信息。  

## EdgeHTML 14 中的新 API

下面是 EdgeHTML 14 中的新 API 的完整列表。  它们以格式列出 `[interface name].[api name]` 。  

<iframe height='585' scrolling='no' title='EdgeHTML 14 中的新 API' src='//codepen.io/MSEdgeDev/embed/oWMEPE/?height=585&theme-id=23761&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>请参阅 <a href='https://codepen.io/MSEdgeDev/pen/oWMEPE/'> </a> CodePen 上 MSEdgeDev 代码的 MicrosoftEdgeDev 代码 <a href='https://codepen.io/MSEdgeDev'> </a> (@MSEdgeDev) Windows <a href='https://codepen.io'> 应用商店应用中的笔新 </a> API。</iframe>  
