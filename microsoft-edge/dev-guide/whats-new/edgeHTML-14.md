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
# <span data-ttu-id="5624f-104">EdgeHTML 14 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="5624f-104">What's new in EdgeHTML 14</span></span>  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

<span data-ttu-id="5624f-105">以下是 EdgeHTML 14 附带的更改，是 [Windows 10 周年更新](https://blogs.windows.com/windowsexperience/2016/06/29) \ (08/2016，内部版本 14393 \ ) 。</span><span class="sxs-lookup"><span data-stu-id="5624f-105">Here are the changes shipped with EdgeHTML 14, as of the [Windows 10 Anniversary Update](https://blogs.windows.com/windowsexperience/2016/06/29) \(08/2016, Build 14393\).</span></span>  <span data-ttu-id="5624f-106">有关 Microsoft Edge 整体浏览器更改的概述，请参阅 [使用 Windows 10 周年更新介绍 EdgeHTML 14](https://blogs.windows.com/msedgedev/2016/08/04)。</span><span class="sxs-lookup"><span data-stu-id="5624f-106">For an overview of changes to the overall Microsoft Edge browser, see [Introducing EdgeHTML 14 with the Windows 10 Anniversary Update](https://blogs.windows.com/msedgedev/2016/08/04).</span></span>  

<span data-ttu-id="5624f-107">下面是以下更改列表的固定链接： [https://aka.ms/devguide_edgehtml_14](./edgehtml-14.md) 。</span><span class="sxs-lookup"><span data-stu-id="5624f-107">Here's the permalink for the following list of changes: [https://aka.ms/devguide_edgehtml_14](./edgehtml-14.md).</span></span>  

## <span data-ttu-id="5624f-108">新增功能</span><span class="sxs-lookup"><span data-stu-id="5624f-108">New Features</span></span>  

### <span data-ttu-id="5624f-109">Extensions</span><span class="sxs-lookup"><span data-stu-id="5624f-109">Extensions</span></span>  

<span data-ttu-id="5624f-110">扩展是可用于向 Microsoft Edge 添加新功能或修改现有功能的小型程序。</span><span class="sxs-lookup"><span data-stu-id="5624f-110">Extensions are small programs that can be used to add new features to Microsoft Edge or modify the existing functionality.</span></span>  <span data-ttu-id="5624f-111">扩展旨在通过提供对目标受众非常重要的小功能来改善用户的日常浏览体验。</span><span class="sxs-lookup"><span data-stu-id="5624f-111">Extensions are intended to improve a user's day-to-day browsing experience by providing niche functionality that is important to targeted audiences.</span></span>  <span data-ttu-id="5624f-112">Microsoft Edge 支持新的 HTML、JavaScript 和基于 CSS 的扩展模型。</span><span class="sxs-lookup"><span data-stu-id="5624f-112">Microsoft Edge supports a new HTML, JavaScript and CSS based extension model.</span></span>  <span data-ttu-id="5624f-113">此新模型是 Chrome 兼容的，这意味着现有的 Chrome 扩展开发人员能够将其扩展迁移到 Microsoft Edge，最小的更改。</span><span class="sxs-lookup"><span data-stu-id="5624f-113">This new model is Chrome-compatible which means that existing Chrome extension developers will be able to migrate their extensions to Microsoft Edge with minimal changes.</span></span>  <span data-ttu-id="5624f-114">有关详细信息，请查看 [Microsoft Edge 扩展](../../extensions/index.md) 开发人员文档。</span><span class="sxs-lookup"><span data-stu-id="5624f-114">For more information, check out [Microsoft Edge extensions](../../extensions/index.md) developer docs.</span></span>  

### <span data-ttu-id="5624f-115">获取 API</span><span class="sxs-lookup"><span data-stu-id="5624f-115">Fetch API</span></span>  
<span data-ttu-id="5624f-116">[获取 API](https://fetch.spec.whatwg.org#fetch-api)使用 `fetch` 获取资源的方法。</span><span class="sxs-lookup"><span data-stu-id="5624f-116">The [Fetch API](https://fetch.spec.whatwg.org#fetch-api) utilizes the `fetch` method for fetching resources.</span></span>  <span data-ttu-id="5624f-117">过去，这是通过提供的 `XMLHttpRequest` 。</span><span class="sxs-lookup"><span data-stu-id="5624f-117">In the past this was achieved with `XMLHttpRequest`.</span></span>  <span data-ttu-id="5624f-118">提取不仅更易于使用，它还提供对请求和响应的较低级别的访问权限。</span><span class="sxs-lookup"><span data-stu-id="5624f-118">Not only is fetch simpler to use, it also provides lower level access to requests and responses.</span></span>  <span data-ttu-id="5624f-119">请阅读有关 Microsoft Edge 博客文章、 [获取 (或 XHR) 的 undeniable 限制的 ](https://blogs.windows.com/msedgedev/2016/05/24)详细信息，请参阅 Microsoft Edge 博客文章中的获取 API。</span><span class="sxs-lookup"><span data-stu-id="5624f-119">Read more about the Fetch API in the Microsoft Edge blog post, [Fetch (or the undeniable limitations of XHR)](https://blogs.windows.com/msedgedev/2016/05/24).</span></span>  

### <span data-ttu-id="5624f-120">JavaScript</span><span class="sxs-lookup"><span data-stu-id="5624f-120">JavaScript</span></span>  

<span data-ttu-id="5624f-121">EdgeHTML 14 为 Chakra 提供了许多新的和实验性功能，JavaScript 引擎可提供 Microsoft Edge 的功能：</span><span class="sxs-lookup"><span data-stu-id="5624f-121">EdgeHTML 14 brings a number of new and experimental features to Chakra, the JavaScript engine powering Microsoft Edge:</span></span>  

#### <span data-ttu-id="5624f-122">新增功能</span><span class="sxs-lookup"><span data-stu-id="5624f-122">New features</span></span>  

<span data-ttu-id="5624f-123">默认启用</span><span class="sxs-lookup"><span data-stu-id="5624f-123">On by default</span></span>  

*   <span data-ttu-id="5624f-124">[默认参数](https://developer.microsoft.com/microsoft-edge/platform/status/defaultparameteres6) \ (ES2015 \ ) </span><span class="sxs-lookup"><span data-stu-id="5624f-124">[Default parameters](https://developer.microsoft.com/microsoft-edge/platform/status/defaultparameteres6) \(ES2015\)</span></span>
*   <span data-ttu-id="5624f-125">[求幂运算符](https://developer.microsoft.com/microsoft-edge/platform/status/exponentiationoperatores2016) \ (ES2016 \ ) </span><span class="sxs-lookup"><span data-stu-id="5624f-125">[Exponentiation operator](https://developer.microsoft.com/microsoft-edge/platform/status/exponentiationoperatores2016) \(ES2016\)</span></span>
*   <span data-ttu-id="5624f-126">[Array. 包含](https://developer.microsoft.com/microsoft-edge/platform/status/arrayprototypeincludeses2016) \ (ES2016 \ ) </span><span class="sxs-lookup"><span data-stu-id="5624f-126">[Array.prototype.includes](https://developer.microsoft.com/microsoft-edge/platform/status/arrayprototypeincludeses2016) \(ES2016\)</span></span>
*   <span data-ttu-id="5624f-127">[对象. 值](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object/values) 和 [对象.](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object/entries) \ (ES2017 \ ) </span><span class="sxs-lookup"><span data-stu-id="5624f-127">[Object.values](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object/values) and [object.entries](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object/entries) \(ES2017\)</span></span>  

#### <span data-ttu-id="5624f-128">实验性 JavaScript 功能</span><span class="sxs-lookup"><span data-stu-id="5624f-128">Experimental JavaScript features</span></span>  

<span data-ttu-id="5624f-129">已启用</span><span class="sxs-lookup"><span data-stu-id="5624f-129">Enabled with</span></span> `about:flags`  

*   <span data-ttu-id="5624f-130">[模块](https://blogs.windows.com/msedgedev/2016/05/17) \ (ES2015 \ ) </span><span class="sxs-lookup"><span data-stu-id="5624f-130">[Modules](https://blogs.windows.com/msedgedev/2016/05/17) \(ES2015\)</span></span>  
*   <span data-ttu-id="5624f-131">[Async/await](https://developer.microsoft.com/microsoft-edge/platform/status/asyncfunctionses2016) \ (ES2017 \ ) </span><span class="sxs-lookup"><span data-stu-id="5624f-131">[Async/await](https://developer.microsoft.com/microsoft-edge/platform/status/asyncfunctionses2016) \(ES2017\)</span></span>  
*   <span data-ttu-id="5624f-132">[Regex 符号](https://developer.microsoft.com/microsoft-edge/platform/status/regexpbuiltinses6) \ (ES2015 \ ) </span><span class="sxs-lookup"><span data-stu-id="5624f-132">[Regex symbols](https://developer.microsoft.com/microsoft-edge/platform/status/regexpbuiltinses6) \(ES2015\)</span></span>  

<span data-ttu-id="5624f-133">有关进一步的详细信息，请查看 [预览 ES6 模块以及其他 ES2015、ES2016 和更高](https://blogs.windows.com/msedgedev/2016/05/17) 版本，以及 [异步代码在 Chakra 和 Microsoft EDGE 中具有 ES2016 Async 函数支持变得更容易](https://blogs.windows.com/msedgedev/2015/09/30)。</span><span class="sxs-lookup"><span data-stu-id="5624f-133">For further details, check out [Previewing ES6 Modules and more from ES2015, ES2016 and beyond](https://blogs.windows.com/msedgedev/2016/05/17) and [Asynchronous code gets easier with ES2016 Async Function support in Chakra and Microsoft Edge](https://blogs.windows.com/msedgedev/2015/09/30).</span></span>  

### <span data-ttu-id="5624f-134">Web 身份验证 API</span><span class="sxs-lookup"><span data-stu-id="5624f-134">Web Authentication API</span></span>  

<span data-ttu-id="5624f-135">FIDO 2.0 Web API</span><span class="sxs-lookup"><span data-stu-id="5624f-135">FIDO 2.0 Web API</span></span>  

<span data-ttu-id="5624f-136">Web 身份验证 \ (以前的 FIDO 2.0 \ ) API 在 Microsoft Edge 中，web 应用程序可以使用 [Windows Hello](https://www.microsoft.com/windows/comprehensive-security) 生物识别进行用户身份验证，以便你和你的用户可以避免密码管理的所有麻烦和风险，包括密码猜测、网络钓鱼和 keylogging 攻击。</span><span class="sxs-lookup"><span data-stu-id="5624f-136">The Web Authentication \(formerly FIDO 2.0\) API in Microsoft Edge enables web applications to use [Windows Hello](https://www.microsoft.com/windows/comprehensive-security) biometrics for user authentication so that you and your users can avoid all the hassles and risks of password management, including password guessing, phishing, and keylogging attacks.</span></span>  <span data-ttu-id="5624f-137">当前 Microsoft Edge \ (`ms-` 前缀 \ ) 实现基于 Web 身份验证规范的早期草案，将来可能会发生更改。</span><span class="sxs-lookup"><span data-stu-id="5624f-137">The current Microsoft Edge \(`ms-` prefixed\) implementation is based on an earlier draft of the Web Authentication specification and is likely to change in the future.</span></span>  <span data-ttu-id="5624f-138">阅读有关 Web 身份验证的详细信息：  [web 身份验证和 Windows Hello](../windows-integration/web-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="5624f-138">Read more about Web Authentication:  [Web authentication and Windows Hello](../windows-integration/web-authentication.md).</span></span>

### <span data-ttu-id="5624f-139">Web 通知</span><span class="sxs-lookup"><span data-stu-id="5624f-139">Web Notifications</span></span>
<span data-ttu-id="5624f-140">Web 通知允许网站显示通知，以向用户发送有关网页和浏览器上下文的通知，让用户知道新消息或警报，并允许网站提高用户的参与范围。</span><span class="sxs-lookup"><span data-stu-id="5624f-140">Web Notifications allow sites to display notifications to alert users outside the context of the webpage and the browser, keeping users informed of new messages or alerts and allowing sites to improve user engagement.</span></span>  <span data-ttu-id="5624f-141">Microsoft Edge 中的 Web 通知与 Windows 10 中的通知平台和操作中心完全集成，可通过系统为其他应用提供一致的体验，并轻松控制权限和静音时间。</span><span class="sxs-lookup"><span data-stu-id="5624f-141">Web Notifications in Microsoft Edge are fully integrated with the notification platform and Action Center in Windows 10, providing a consistent experience with other apps across the system and easy controls over permissions and Quiet Hours.</span></span>  <span data-ttu-id="5624f-142">有关详细信息，请查看 [Microsoft Edge 中的 Web 通知](https://blogs.windows.com/msedgedev/2016/05/16) 。</span><span class="sxs-lookup"><span data-stu-id="5624f-142">Check out [Web Notifications in Microsoft Edge](https://blogs.windows.com/msedgedev/2016/05/16) for more information.</span></span>  

### <span data-ttu-id="5624f-143">Web 语音 API</span><span class="sxs-lookup"><span data-stu-id="5624f-143">Web Speech API</span></span>
<span data-ttu-id="5624f-144">[Web 语音 API](https://dvcs.w3.org/hg/speech-api/raw-file/tip/speechapi.html)是由两部分组成的 JavaScript api：语音识别和语音合成 \ (或文本转换为语音 ) 。</span><span class="sxs-lookup"><span data-stu-id="5624f-144">The [Web Speech API](https://dvcs.w3.org/hg/speech-api/raw-file/tip/speechapi.html) is a JavaScript API made up of two parts: speech recognition and speech synthesis \(or text to speech\).</span></span>  <span data-ttu-id="5624f-145">现在，Microsoft Edge 仅支持语音合成。</span><span class="sxs-lookup"><span data-stu-id="5624f-145">At this time Microsoft Edge supports only speech synthesis.</span></span>  <span data-ttu-id="5624f-146">语音合成涉及用户通过扬声器听到的语音转换文本。</span><span class="sxs-lookup"><span data-stu-id="5624f-146">Speech synthesis involves the conversion of text to speech that a user hears through their speakers.</span></span>  <span data-ttu-id="5624f-147">有关详细信息，请查看 [Web 语音：语音合成](https://developer.mozilla.org/docs/Web/API/Web_Speech_API) 开发人员指南文章。</span><span class="sxs-lookup"><span data-stu-id="5624f-147">Check out the [Web Speech: Speech Synthesis](https://developer.mozilla.org/docs/Web/API/Web_Speech_API) Developer Guide article for more information.</span></span>  

## <span data-ttu-id="5624f-148">EdgeHTML 14 中的新 Api</span><span class="sxs-lookup"><span data-stu-id="5624f-148">New APIs in EdgeHTML 14</span></span>

<span data-ttu-id="5624f-149">下面是 EdgeHTML 14 中新 Api 的完整列表。</span><span class="sxs-lookup"><span data-stu-id="5624f-149">Here's the full list of new APIs in EdgeHTML 14.</span></span>  <span data-ttu-id="5624f-150">它们以的格式列出 `[interface name].[api name]` 。</span><span class="sxs-lookup"><span data-stu-id="5624f-150">They are listed in the format of `[interface name].[api name]`.</span></span>  

<iframe height='585' scrolling='no' title='<span data-ttu-id="5624f-151">EdgeHTML 14 中的新 Api</span><span class="sxs-lookup"><span data-stu-id="5624f-151">New APIs in EdgeHTML 14</span></span>' src='//codepen.io/MSEdgeDev/embed/oWMEPE/?height=585&theme-id=23761&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'><span data-ttu-id="5624f-152"><a href='https://codepen.io/MSEdgeDev/pen/oWMEPE/'>在 </a> CodePen 上的 MSEdgeDev (<a href='https://codepen.io/MSEdgeDev'> @MSEdgeDev) 查看 EdgeHTML 14 中的笔新 api </a> <a href='https://codepen.io'> </a> 。</span><span class="sxs-lookup"><span data-stu-id="5624f-152">See the Pen <a href='https://codepen.io/MSEdgeDev/pen/oWMEPE/'>New APIs in EdgeHTML 14</a>by MSEdgeDev (<a href='https://codepen.io/MSEdgeDev'>@MSEdgeDev</a>) on <a href='https://codepen.io'>CodePen</a>.</span></span></iframe>  
