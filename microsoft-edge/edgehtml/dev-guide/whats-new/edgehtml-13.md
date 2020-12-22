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
# <span data-ttu-id="6988b-104">EdgeHTML 13 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="6988b-104">What's new in EdgeHTML 13</span></span>  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

<span data-ttu-id="6988b-105">以下是 EdgeHTML 13 附带的更改，该引擎在 Windows 10 [](https://blogs.windows.com/windowsexperience/2015/11/12) \ (11/2015 内部版本 10586\) 的第一个主要更新中为 Microsoft Edge 浏览器提供电源。</span><span class="sxs-lookup"><span data-stu-id="6988b-105">Here are the changes shipped with EdgeHTML 13, the engine powering the Microsoft Edge browser in the [first major update](https://blogs.windows.com/windowsexperience/2015/11/12) for Windows 10 \(11/2015, Build 10586\).</span></span>  <span data-ttu-id="6988b-106">有关整个 Microsoft Edge 浏览器更改的概述，请参阅介绍 [EdgeHTML 13，](https://blogs.windows.com/msedgedev/2015/11/16)这是 Microsoft Edge 的第一个平台更新。</span><span class="sxs-lookup"><span data-stu-id="6988b-106">For an overview of changes to the overall Microsoft Edge browser, see [Introducing EdgeHTML 13, our first platform update for Microsoft Edge](https://blogs.windows.com/msedgedev/2015/11/16).</span></span>  

<span data-ttu-id="6988b-107">下面是以下更改列表的 permalink： [https://aka.ms/devguide_edgehtml_13](./edgehtml-13.md)</span><span class="sxs-lookup"><span data-stu-id="6988b-107">Here's the permalink for the following list of changes:  [https://aka.ms/devguide_edgehtml_13](./edgehtml-13.md).</span></span>  

## <span data-ttu-id="6988b-108">功能</span><span class="sxs-lookup"><span data-stu-id="6988b-108">Features</span></span>  

### <span data-ttu-id="6988b-109">CSS</span><span class="sxs-lookup"><span data-stu-id="6988b-109">CSS</span></span>  

<span data-ttu-id="6988b-110">EdgeHTML 13 支持新的 CSS 功能，包括：</span><span class="sxs-lookup"><span data-stu-id="6988b-110">EdgeHTML 13 supports new CSS features, including:</span></span>  

*   [<span data-ttu-id="6988b-111">CSS 可变性伪类</span><span class="sxs-lookup"><span data-stu-id="6988b-111">CSS Mutability Pseudo-classes</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/cssmutabilitypseudoclasses)  
*   [<span data-ttu-id="6988b-112">CSS 范围伪类</span><span class="sxs-lookup"><span data-stu-id="6988b-112">CSS Range Pseudo-classes</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/cssrangepseudoclasses)  
*   <span data-ttu-id="6988b-113">CSS[](https://developer.microsoft.com/microsoft-edge/platform/status/cssinitialvalue)初始[关键字和未设置](https://developer.microsoft.com/microsoft-edge/platform/status/cssunsetvalue)关键字</span><span class="sxs-lookup"><span data-stu-id="6988b-113">CSS [initial](https://developer.microsoft.com/microsoft-edge/platform/status/cssinitialvalue) and [unset](https://developer.microsoft.com/microsoft-edge/platform/status/cssunsetvalue) keywords</span></span>  

### <span data-ttu-id="6988b-114">加密媒体扩展</span><span class="sxs-lookup"><span data-stu-id="6988b-114">Encrypted Media Extensions</span></span>  

<span data-ttu-id="6988b-115">Microsoft Edge 现在支持新的未准备加密 [媒体](https://w3.org/TR/encrypted-media) 扩展 API。</span><span class="sxs-lookup"><span data-stu-id="6988b-115">Microsoft Edge now supports the new unprefixed [Encrypted Media Extensions](https://w3.org/TR/encrypted-media) APIs.</span></span>  <span data-ttu-id="6988b-116">加密媒体扩展 \ (EME\) 扩展了视频和音频元素，以启用数字版权管理 \ (DRM\) 保护的内容，而无需使用插件。 阅读有关 EME：  [加密媒体扩展的更多内容](https://developer.mozilla.org/docs/Web/API/Encrypted_Media_Extensions_API)。</span><span class="sxs-lookup"><span data-stu-id="6988b-116">Encrypted Media Extensions \(EME\) extends the video and audio elements to enable Digital Rights Management \(DRM\) protected content without using plug-ins.  Read more about EME:  [Encrypted Media Extensions](https://developer.mozilla.org/docs/Web/API/Encrypted_Media_Extensions_API).</span></span>  

### <span data-ttu-id="6988b-117">显卡</span><span class="sxs-lookup"><span data-stu-id="6988b-117">Graphics</span></span>  

<span data-ttu-id="6988b-118">EdgeHTML 13 引入了以下图形更新：</span><span class="sxs-lookup"><span data-stu-id="6988b-118">EdgeHTML 13 introduces the following graphics updates:</span></span>  

*   [<span data-ttu-id="6988b-119">画布椭圆</span><span class="sxs-lookup"><span data-stu-id="6988b-119">Canvas ellipse</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/canvas2dellipse)  
*   [<span data-ttu-id="6988b-120">画布混合模式</span><span class="sxs-lookup"><span data-stu-id="6988b-120">Canvas blending modes</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/compositingandblendingincanvas2d)  
*   [<picture> <span data-ttu-id="6988b-121">元素</span><span class="sxs-lookup"><span data-stu-id="6988b-121">element</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/pictureelement)  
*   [<span data-ttu-id="6988b-122">SVG 外部内容</span><span class="sxs-lookup"><span data-stu-id="6988b-122">SVG external content</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/svgexternalcontent)  

### <span data-ttu-id="6988b-123">JavaScript</span><span class="sxs-lookup"><span data-stu-id="6988b-123">JavaScript</span></span>  

<span data-ttu-id="6988b-124">EdgeHTML 13 包括主要改进和 [\*\*（](https://blogs.windows.com/msedgedev/2015/09/30)支持 Microsoft Edge 的 JavaScript 引擎）中的新功能支持，包括：</span><span class="sxs-lookup"><span data-stu-id="6988b-124">EdgeHTML 13 includes [major improvements and new feature support in Chakra](https://blogs.windows.com/msedgedev/2015/09/30), the JavaScript engine powering Microsoft Edge, including:</span></span>  

#### <span data-ttu-id="6988b-125">新功能</span><span class="sxs-lookup"><span data-stu-id="6988b-125">New features</span></span>  

<span data-ttu-id="6988b-126">默认启用</span><span class="sxs-lookup"><span data-stu-id="6988b-126">On by default</span></span>  

*   <span data-ttu-id="6988b-127">[asm.js](https://developer.microsoft.com/microsoft-edge/platform/status/asmjs/?q=asm.js) \ ([博客文章](https://blogs.windows.com/msedgedev/2015/11/10) [demo \) ](https://dev.windows.com/microsoft-edge/testdrive/demos/chess)</span><span class="sxs-lookup"><span data-stu-id="6988b-127">[asm.js](https://developer.microsoft.com/microsoft-edge/platform/status/asmjs/?q=asm.js) enabled by default \([blog post](https://blogs.windows.com/msedgedev/2015/11/10), [demo](https://dev.windows.com/microsoft-edge/testdrive/demos/chess)\)</span></span>  
*   <span data-ttu-id="6988b-128">[类](https://developer.microsoft.com/microsoft-edge/platform/status/asmjs/?q=classes) \ (ES2015\) </span><span class="sxs-lookup"><span data-stu-id="6988b-128">[Classes](https://developer.microsoft.com/microsoft-edge/platform/status/asmjs/?q=classes) \(ES2015\)</span></span>  

#### <span data-ttu-id="6988b-129">实验 JavaScript 功能</span><span class="sxs-lookup"><span data-stu-id="6988b-129">Experimental JavaScript features</span></span>  

<span data-ttu-id="6988b-130">已启用</span><span class="sxs-lookup"><span data-stu-id="6988b-130">Enabled with</span></span> `about:flags`  

*   <span data-ttu-id="6988b-131">[异步函数](https://developer.microsoft.com/microsoft-edge/platform/status/asyncfunctions/?q=async%20functions) \ (ES2016\) </span><span class="sxs-lookup"><span data-stu-id="6988b-131">[Async functions](https://developer.microsoft.com/microsoft-edge/platform/status/asyncfunctions/?q=async%20functions) \(ES2016\)</span></span>  
*   <span data-ttu-id="6988b-132">[Exponentiation 运算符](https://developer.microsoft.com/microsoft-edge/platform/status/exponentiationoperatores2016/?q=exponentiation%20operator) \ (ES2016\) </span><span class="sxs-lookup"><span data-stu-id="6988b-132">[Exponentiation operator](https://developer.microsoft.com/microsoft-edge/platform/status/exponentiationoperatores2016/?q=exponentiation%20operator) \(ES2016\)</span></span>  
*   <span data-ttu-id="6988b-133">[取消构造](https://developer.microsoft.com/microsoft-edge/platform/status/destructuringES2015/?q=destructuring) \ (ES2015\) </span><span class="sxs-lookup"><span data-stu-id="6988b-133">[Destructuring](https://developer.microsoft.com/microsoft-edge/platform/status/destructuringES2015/?q=destructuring) \(ES2015\)</span></span>  

### <span data-ttu-id="6988b-134">用户输入</span><span class="sxs-lookup"><span data-stu-id="6988b-134">User Input</span></span>  

<span data-ttu-id="6988b-135">EdgeHTML 13 中引入的以下功能改进了用户输入：</span><span class="sxs-lookup"><span data-stu-id="6988b-135">The following features introduced in EdgeHTML 13 improve user input:</span></span>  

*   [\<meter\> <span data-ttu-id="6988b-136">元素</span><span class="sxs-lookup"><span data-stu-id="6988b-136">element</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/meterelement)  
*   [<span data-ttu-id="6988b-137">元素文档和窗口的 oninvalid 事件处理程序</span><span class="sxs-lookup"><span data-stu-id="6988b-137">oninvalid event handler for the element document and window</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/oninvalideventhandler)  

### <span data-ttu-id="6988b-138">指针锁定</span><span class="sxs-lookup"><span data-stu-id="6988b-138">Pointer Lock</span></span>  

<span data-ttu-id="6988b-139">Microsoft Edge 现在支持指针锁定 API \ (以前称为"鼠标锁定"\) ，用于访问原始鼠标移动、将鼠标事件的目标锁定为单个元素、消除鼠标在单个方向上移动距离的限制以及从视图中删除光标。</span><span class="sxs-lookup"><span data-stu-id="6988b-139">Microsoft Edge now supports the Pointer Lock API \(previously called Mouse Lock\) for access to raw mouse movement, locking the target of mouse events to a single element, eliminating limits of how far mouse movement can go in a single direction, and removing the cursor from view.</span></span>  

## <span data-ttu-id="6988b-140">EdgeHTML 13 中的新 API</span><span class="sxs-lookup"><span data-stu-id="6988b-140">New APIs in EdgeHTML 13</span></span>  

<span data-ttu-id="6988b-141">下面是 EdgeHTML 13 中新 API 的完整列表。</span><span class="sxs-lookup"><span data-stu-id="6988b-141">Here's the full list of new APIs in EdgeHTML 13.</span></span>  <span data-ttu-id="6988b-142">它们以 . `[interface name].[api name]`</span><span class="sxs-lookup"><span data-stu-id="6988b-142">They are listed in the format of `[interface name].[api name]`.</span></span>  

<iframe height='584' scrolling='no' title='<span data-ttu-id="6988b-143">EdgeHTML 13 中的新 API</span><span class="sxs-lookup"><span data-stu-id="6988b-143">New APIs in EdgeHTML 13</span></span>' src='//codepen.io/MicrosoftEdgeDocumentation/embed/vmzxEY/?height=584&theme-id=23761&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width:  100%;'><span data-ttu-id="6988b-144">请参阅 EdgeHTML 13 中的笔新 API（由 Microsoft Edge 文档 <a href='https://codepen.io/MicrosoftEdgeDocumentation/pen/vmzxEY/'> </a> <a href='http://codepen.io/MicrosoftEdgeDocumentation'> (@MicrosoftEdgeDocumentation) </a> <a href='http://codepen.io'> CodePen 上 </a> ）。</span><span class="sxs-lookup"><span data-stu-id="6988b-144">See the Pen <a href='https://codepen.io/MicrosoftEdgeDocumentation/pen/vmzxEY/'>New APIs in EdgeHTML 13</a> by Microsoft Edge Docs (<a href='http://codepen.io/MicrosoftEdgeDocumentation'>@MicrosoftEdgeDocumentation</a>) on <a href='http://codepen.io'>CodePen</a>.</span></span></iframe>  