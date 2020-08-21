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
# <span data-ttu-id="33199-104">EdgeHTML 13 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="33199-104">What's new in EdgeHTML 13</span></span>  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

<span data-ttu-id="33199-105">下面是随 EdgeHTML 13 提供的更改，即 Windows 10 / (11/2015（内部版本 10586\) ）的首要更新中提供 Microsoft Edge 浏览器。 [first major update](https://blogs.windows.com/windowsexperience/2015/11/12)</span><span class="sxs-lookup"><span data-stu-id="33199-105">Here are the changes shipped with EdgeHTML 13, the engine powering the Microsoft Edge browser in the [first major update](https://blogs.windows.com/windowsexperience/2015/11/12) for Windows 10 \(11/2015, Build 10586\).</span></span>  <span data-ttu-id="33199-106">有关 Microsoft Edge 浏览器整体 Microsoft Edge 浏览器的更改的概述， [请参阅 EdgeHTML 13（Microsoft Edge 的第一个平台更新](https://blogs.windows.com/msedgedev/2015/11/16)）。</span><span class="sxs-lookup"><span data-stu-id="33199-106">For an overview of changes to the overall Microsoft Edge browser, see [Introducing EdgeHTML 13, our first platform update for Microsoft Edge](https://blogs.windows.com/msedgedev/2015/11/16).</span></span>  

<span data-ttu-id="33199-107">下面是下列更改列表的句号  [https://aka.ms/devguide_edgehtml_13](./edgehtml-13.md) ：。</span><span class="sxs-lookup"><span data-stu-id="33199-107">Here's the permalink for the following list of changes:  [https://aka.ms/devguide_edgehtml_13](./edgehtml-13.md).</span></span>  

## <span data-ttu-id="33199-108">功能</span><span class="sxs-lookup"><span data-stu-id="33199-108">Features</span></span>  

### <span data-ttu-id="33199-109">CSS</span><span class="sxs-lookup"><span data-stu-id="33199-109">CSS</span></span>  

<span data-ttu-id="33199-110">Microsoft EdgeHTML 13 支持新的 CSS 功能，其中包括：</span><span class="sxs-lookup"><span data-stu-id="33199-110">EdgeHTML 13 supports new CSS features, including:</span></span>  

*   [<span data-ttu-id="33199-111">CSS 多位功能强制性下</span><span class="sxs-lookup"><span data-stu-id="33199-111">CSS Mutability Pseudo-classes</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/cssmutabilitypseudoclasses)  
*   [<span data-ttu-id="33199-112">CSS 范围分类</span><span class="sxs-lookup"><span data-stu-id="33199-112">CSS Range Pseudo-classes</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/cssrangepseudoclasses)  
*   <span data-ttu-id="33199-113">CSS[初始和](https://developer.microsoft.com/microsoft-edge/platform/status/cssinitialvalue)[取消设置关](https://developer.microsoft.com/microsoft-edge/platform/status/cssunsetvalue)键字</span><span class="sxs-lookup"><span data-stu-id="33199-113">CSS [initial](https://developer.microsoft.com/microsoft-edge/platform/status/cssinitialvalue) and [unset](https://developer.microsoft.com/microsoft-edge/platform/status/cssunsetvalue) keywords</span></span>  

### <span data-ttu-id="33199-114">加密媒体扩展</span><span class="sxs-lookup"><span data-stu-id="33199-114">Encrypted Media Extensions</span></span>  

<span data-ttu-id="33199-115">Microsoft Edge 现在支持新的未加密的加密 [媒体扩展](https://w3.org/TR/encrypted-media) API。</span><span class="sxs-lookup"><span data-stu-id="33199-115">Microsoft Edge now supports the new unprefixed [Encrypted Media Extensions](https://w3.org/TR/encrypted-media) APIs.</span></span>  <span data-ttu-id="33199-116">加密媒体扩展 \ (EME\) 扩展视频和音频元素，而无需使用插件，直接启用数字版权管理 \ (DRM\) 保护内容。 阅读有关  [EME：加密媒体扩展的详细信息](https://developer.mozilla.org/docs/Web/API/Encrypted_Media_Extensions_API)。</span><span class="sxs-lookup"><span data-stu-id="33199-116">Encrypted Media Extensions \(EME\) extends the video and audio elements to enable Digital Rights Management \(DRM\) protected content without using plug-ins.  Read more about EME:  [Encrypted Media Extensions](https://developer.mozilla.org/docs/Web/API/Encrypted_Media_Extensions_API).</span></span>  

### <span data-ttu-id="33199-117">显卡</span><span class="sxs-lookup"><span data-stu-id="33199-117">Graphics</span></span>  

<span data-ttu-id="33199-118">EdgeHTML 13 引入了以下图形更新：</span><span class="sxs-lookup"><span data-stu-id="33199-118">EdgeHTML 13 introduces the following graphics updates:</span></span>  

*   [<span data-ttu-id="33199-119">画布省略号</span><span class="sxs-lookup"><span data-stu-id="33199-119">Canvas ellipse</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/canvas2dellipse)  
*   [<span data-ttu-id="33199-120">画布混合模式</span><span class="sxs-lookup"><span data-stu-id="33199-120">Canvas blending modes</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/compositingandblendingincanvas2d)  
*   [<picture> <span data-ttu-id="33199-121">元素</span><span class="sxs-lookup"><span data-stu-id="33199-121">element</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/pictureelement)  
*   [<span data-ttu-id="33199-122">SVG 外部内容</span><span class="sxs-lookup"><span data-stu-id="33199-122">SVG external content</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/svgexternalcontent)  

### <span data-ttu-id="33199-123">JavaScript</span><span class="sxs-lookup"><span data-stu-id="33199-123">JavaScript</span></span>  

<span data-ttu-id="33199-124">EdgeHTML 13 [包括重大改进和在 Chakra（](https://blogs.windows.com/msedgedev/2015/09/30)这是 JavaScript 引强权 Microsoft Edge）中提供的新功能支持，包括：</span><span class="sxs-lookup"><span data-stu-id="33199-124">EdgeHTML 13 includes [major improvements and new feature support in Chakra](https://blogs.windows.com/msedgedev/2015/09/30), the JavaScript engine powering Microsoft Edge, including:</span></span>  

#### <span data-ttu-id="33199-125">新增功能</span><span class="sxs-lookup"><span data-stu-id="33199-125">New features</span></span>  

<span data-ttu-id="33199-126">默认启用</span><span class="sxs-lookup"><span data-stu-id="33199-126">On by default</span></span>  

*   <span data-ttu-id="33199-127">[asm.js](https://developer.microsoft.com/microsoft-edge/platform/status/asmjs/?q=asm.js) \pded _ ([博客文章时，](https://blogs.windows.com/msedgedev/2015/11/10)[演示](https://dev.windows.com/microsoft-edge/testdrive/demos/chess)\) </span><span class="sxs-lookup"><span data-stu-id="33199-127">[asm.js](https://developer.microsoft.com/microsoft-edge/platform/status/asmjs/?q=asm.js) enabled by default \([blog post](https://blogs.windows.com/msedgedev/2015/11/10), [demo](https://dev.windows.com/microsoft-edge/testdrive/demos/chess)\)</span></span>  
*   <span data-ttu-id="33199-128">[Classes](https://developer.microsoft.com/microsoft-edge/platform/status/asmjs/?q=classes) \ (ES2015\) </span><span class="sxs-lookup"><span data-stu-id="33199-128">[Classes](https://developer.microsoft.com/microsoft-edge/platform/status/asmjs/?q=classes) \(ES2015\)</span></span>  

#### <span data-ttu-id="33199-129">实质 JavaScript 功能</span><span class="sxs-lookup"><span data-stu-id="33199-129">Experimental JavaScript features</span></span>  

<span data-ttu-id="33199-130">与</span><span class="sxs-lookup"><span data-stu-id="33199-130">Enabled with</span></span> `about:flags`  

*   <span data-ttu-id="33199-131">[异步函数](https://developer.microsoft.com/microsoft-edge/platform/status/asyncfunctions/?q=async%20functions) \ (ES2016\) </span><span class="sxs-lookup"><span data-stu-id="33199-131">[Async functions](https://developer.microsoft.com/microsoft-edge/platform/status/asyncfunctions/?q=async%20functions) \(ES2016\)</span></span>  
*   <span data-ttu-id="33199-132">[指数运算符](https://developer.microsoft.com/microsoft-edge/platform/status/exponentiationoperatores2016/?q=exponentiation%20operator) \ (ES2016\) </span><span class="sxs-lookup"><span data-stu-id="33199-132">[Exponentiation operator](https://developer.microsoft.com/microsoft-edge/platform/status/exponentiationoperatores2016/?q=exponentiation%20operator) \(ES2016\)</span></span>  
*   <span data-ttu-id="33199-133">[将](https://developer.microsoft.com/microsoft-edge/platform/status/destructuringES2015/?q=destructuring) \ (ES2015\) </span><span class="sxs-lookup"><span data-stu-id="33199-133">[Destructuring](https://developer.microsoft.com/microsoft-edge/platform/status/destructuringES2015/?q=destructuring) \(ES2015\)</span></span>  

### <span data-ttu-id="33199-134">用户输入</span><span class="sxs-lookup"><span data-stu-id="33199-134">User Input</span></span>  

<span data-ttu-id="33199-135">在 EdgeHTML 13 中引入的以下功能改进了用户输入：</span><span class="sxs-lookup"><span data-stu-id="33199-135">The following features introduced in EdgeHTML 13 improve user input:</span></span>  

*   [<meter> <span data-ttu-id="33199-136">元素</span><span class="sxs-lookup"><span data-stu-id="33199-136">element</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/meterelement)  
*   [<span data-ttu-id="33199-137">对于元素文档和窗口</span><span class="sxs-lookup"><span data-stu-id="33199-137">oninvalid event handler for the element document and window</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/oninvalideventhandler)  

### <span data-ttu-id="33199-138">指针锁</span><span class="sxs-lookup"><span data-stu-id="33199-138">Pointer Lock</span></span>  

<span data-ttu-id="33199-139">Microsoft Edge 现在支持指针 Lock API / (之前称为鼠标 Lock\) 以访问原始鼠标移动，锁定鼠标事件的目标，消除鼠标动作在单个方向的大小上限，以及从视图中删除光标。</span><span class="sxs-lookup"><span data-stu-id="33199-139">Microsoft Edge now supports the Pointer Lock API \(previously called Mouse Lock\) for access to raw mouse movement, locking the target of mouse events to a single element, eliminating limits of how far mouse movement can go in a single direction, and removing the cursor from view.</span></span>  

## <span data-ttu-id="33199-140">EdgeHTML 13 中的新 API</span><span class="sxs-lookup"><span data-stu-id="33199-140">New APIs in EdgeHTML 13</span></span>  

<span data-ttu-id="33199-141">下面是 EdgeHTML 13 中的新 API 的完整列表。</span><span class="sxs-lookup"><span data-stu-id="33199-141">Here's the full list of new APIs in EdgeHTML 13.</span></span>  <span data-ttu-id="33199-142">它们以格式列出 `[interface name].[api name]` 。</span><span class="sxs-lookup"><span data-stu-id="33199-142">They are listed in the format of `[interface name].[api name]`.</span></span>  

<iframe height='584' scrolling='no' title='<span data-ttu-id="33199-143">EdgeHTML 13 中的新 API</span><span class="sxs-lookup"><span data-stu-id="33199-143">New APIs in EdgeHTML 13</span></span>' src='//codepen.io/MicrosoftEdgeDocumentation/embed/vmzxEY/?height=584&theme-id=23761&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width:  100%;'><span data-ttu-id="33199-144">在 <a href='https://codepen.io/MicrosoftEdgeDocumentation/pen/vmzxEY/'> CodePen 上查看 Microsoft Edge 的 </a> Microsoft Edge (@MicrosoftEdgeDocumentation) 中的笔 <a href='http://codepen.io/MicrosoftEdgeDocumentation'> 新 </a> <a href='http://codepen.io'> </a> API。</span><span class="sxs-lookup"><span data-stu-id="33199-144">See the Pen <a href='https://codepen.io/MicrosoftEdgeDocumentation/pen/vmzxEY/'>New APIs in EdgeHTML 13</a> by Microsoft Edge Docs (<a href='http://codepen.io/MicrosoftEdgeDocumentation'>@MicrosoftEdgeDocumentation</a>) on <a href='http://codepen.io'>CodePen</a>.</span></span></iframe>  
