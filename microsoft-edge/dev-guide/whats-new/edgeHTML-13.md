---
description: 此页面概述了 EdgeHTML 13 中的新增功能。
title: EdgeHTML 13 中的新增功能和 Api
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘、web 开发、html、css、javascript、开发人员
ms.openlocfilehash: 033b8dacb107492624f3b8c7775a47285c9893dd
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "10941913"
---
# <span data-ttu-id="eda79-104">EdgeHTML 13 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="eda79-104">What's new in EdgeHTML 13</span></span>  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

<span data-ttu-id="eda79-105">下面是 EdgeHTML 13 所附的更改，该引擎会在 Windows 10 \ (11/2015 的 [第一个主要更新](https://blogs.windows.com/windowsexperience/2015/11/12) ，内部版本 10586 \ ) 中打开 Microsoft Edge 浏览器。</span><span class="sxs-lookup"><span data-stu-id="eda79-105">Here are the changes shipped with EdgeHTML 13, the engine powering the Microsoft Edge browser in the [first major update](https://blogs.windows.com/windowsexperience/2015/11/12) for Windows 10 \(11/2015, Build 10586\).</span></span>  <span data-ttu-id="eda79-106">有关 Microsoft edge 整体浏览器更改的概述，请参阅 [介绍 Microsoft edge 第一个平台更新 EdgeHTML 13](https://blogs.windows.com/msedgedev/2015/11/16)。</span><span class="sxs-lookup"><span data-stu-id="eda79-106">For an overview of changes to the overall Microsoft Edge browser, see [Introducing EdgeHTML 13, our first platform update for Microsoft Edge](https://blogs.windows.com/msedgedev/2015/11/16).</span></span>  

<span data-ttu-id="eda79-107">下面是以下更改列表的固定链接：  [https://aka.ms/devguide_edgehtml_13](./edgehtml-13.md) 。</span><span class="sxs-lookup"><span data-stu-id="eda79-107">Here's the permalink for the following list of changes:  [https://aka.ms/devguide_edgehtml_13](./edgehtml-13.md).</span></span>  

## <span data-ttu-id="eda79-108">功能</span><span class="sxs-lookup"><span data-stu-id="eda79-108">Features</span></span>  

### <span data-ttu-id="eda79-109">CSS</span><span class="sxs-lookup"><span data-stu-id="eda79-109">CSS</span></span>  

<span data-ttu-id="eda79-110">EdgeHTML 13 支持新的 CSS 功能，包括：</span><span class="sxs-lookup"><span data-stu-id="eda79-110">EdgeHTML 13 supports new CSS features, including:</span></span>  

*   [<span data-ttu-id="eda79-111">CSS Mutability 伪类</span><span class="sxs-lookup"><span data-stu-id="eda79-111">CSS Mutability Pseudo-classes</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/cssmutabilitypseudoclasses)  
*   [<span data-ttu-id="eda79-112">CSS 范围伪类</span><span class="sxs-lookup"><span data-stu-id="eda79-112">CSS Range Pseudo-classes</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/cssrangepseudoclasses)  
*   <span data-ttu-id="eda79-113">CSS [初始](https://developer.microsoft.com/microsoft-edge/platform/status/cssinitialvalue) 和未 [设置](https://developer.microsoft.com/microsoft-edge/platform/status/cssunsetvalue) 关键字</span><span class="sxs-lookup"><span data-stu-id="eda79-113">CSS [initial](https://developer.microsoft.com/microsoft-edge/platform/status/cssinitialvalue) and [unset](https://developer.microsoft.com/microsoft-edge/platform/status/cssunsetvalue) keywords</span></span>  

### <span data-ttu-id="eda79-114">加密媒体扩展</span><span class="sxs-lookup"><span data-stu-id="eda79-114">Encrypted Media Extensions</span></span>  

<span data-ttu-id="eda79-115">Microsoft Edge 现在支持新的 unprefixed [加密媒体扩展](https://w3.org/TR/encrypted-media) api。</span><span class="sxs-lookup"><span data-stu-id="eda79-115">Microsoft Edge now supports the new unprefixed [Encrypted Media Extensions](https://w3.org/TR/encrypted-media) APIs.</span></span>  <span data-ttu-id="eda79-116">加密媒体扩展 \ (EME \ ) 扩展视频和音频元素以启用数字权限管理 \ (DRM \ ) 受保护的内容，而不使用插件。 阅读有关 EME 的详细信息：  [加密媒体扩展](https://developer.mozilla.org/docs/Web/API/Encrypted_Media_Extensions_API)。</span><span class="sxs-lookup"><span data-stu-id="eda79-116">Encrypted Media Extensions \(EME\) extends the video and audio elements to enable Digital Rights Management \(DRM\) protected content without using plug-ins.  Read more about EME:  [Encrypted Media Extensions](https://developer.mozilla.org/docs/Web/API/Encrypted_Media_Extensions_API).</span></span>  

### <span data-ttu-id="eda79-117">显卡</span><span class="sxs-lookup"><span data-stu-id="eda79-117">Graphics</span></span>  

<span data-ttu-id="eda79-118">EdgeHTML 13 引入了以下图形更新：</span><span class="sxs-lookup"><span data-stu-id="eda79-118">EdgeHTML 13 introduces the following graphics updates:</span></span>  

*   [<span data-ttu-id="eda79-119">画布椭圆</span><span class="sxs-lookup"><span data-stu-id="eda79-119">Canvas ellipse</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/canvas2dellipse)  
*   [<span data-ttu-id="eda79-120">画布混合模式</span><span class="sxs-lookup"><span data-stu-id="eda79-120">Canvas blending modes</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/compositingandblendingincanvas2d)  
*   [<picture> <span data-ttu-id="eda79-121">元素</span><span class="sxs-lookup"><span data-stu-id="eda79-121">element</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/pictureelement)  
*   [<span data-ttu-id="eda79-122">SVG 外部内容</span><span class="sxs-lookup"><span data-stu-id="eda79-122">SVG external content</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/svgexternalcontent)  

### <span data-ttu-id="eda79-123">JavaScript</span><span class="sxs-lookup"><span data-stu-id="eda79-123">JavaScript</span></span>  

<span data-ttu-id="eda79-124">EdgeHTML 13 [在 Chakra 中包含重大改进和新增功能支持](https://blogs.windows.com/msedgedev/2015/09/30)，JavaScript 引擎支持 Microsoft Edge，包括：</span><span class="sxs-lookup"><span data-stu-id="eda79-124">EdgeHTML 13 includes [major improvements and new feature support in Chakra](https://blogs.windows.com/msedgedev/2015/09/30), the JavaScript engine powering Microsoft Edge, including:</span></span>  

#### <span data-ttu-id="eda79-125">新增功能</span><span class="sxs-lookup"><span data-stu-id="eda79-125">New features</span></span>  

<span data-ttu-id="eda79-126">默认启用</span><span class="sxs-lookup"><span data-stu-id="eda79-126">On by default</span></span>  

*   <span data-ttu-id="eda79-127">默认情况下， [asm.js](https://developer.microsoft.com/microsoft-edge/platform/status/asmjs/?q=asm.js)启用 \ ([博客文章](https://blogs.windows.com/msedgedev/2015/11/10)，[演示](https://dev.windows.com/microsoft-edge/testdrive/demos/chess)\ ) </span><span class="sxs-lookup"><span data-stu-id="eda79-127">[asm.js](https://developer.microsoft.com/microsoft-edge/platform/status/asmjs/?q=asm.js) enabled by default \([blog post](https://blogs.windows.com/msedgedev/2015/11/10), [demo](https://dev.windows.com/microsoft-edge/testdrive/demos/chess)\)</span></span>  
*   <span data-ttu-id="eda79-128">[类](https://developer.microsoft.com/microsoft-edge/platform/status/asmjs/?q=classes) \ (ES2015 \ ) </span><span class="sxs-lookup"><span data-stu-id="eda79-128">[Classes](https://developer.microsoft.com/microsoft-edge/platform/status/asmjs/?q=classes) \(ES2015\)</span></span>  

#### <span data-ttu-id="eda79-129">实验性 JavaScript 功能</span><span class="sxs-lookup"><span data-stu-id="eda79-129">Experimental JavaScript features</span></span>  

<span data-ttu-id="eda79-130">已启用</span><span class="sxs-lookup"><span data-stu-id="eda79-130">Enabled with</span></span> `about:flags`  

*   <span data-ttu-id="eda79-131">[异步函数](https://developer.microsoft.com/microsoft-edge/platform/status/asyncfunctions/?q=async%20functions) \ (ES2016 \ ) </span><span class="sxs-lookup"><span data-stu-id="eda79-131">[Async functions](https://developer.microsoft.com/microsoft-edge/platform/status/asyncfunctions/?q=async%20functions) \(ES2016\)</span></span>  
*   <span data-ttu-id="eda79-132">[求幂运算符](https://developer.microsoft.com/microsoft-edge/platform/status/exponentiationoperatores2016/?q=exponentiation%20operator) \ (ES2016 \ ) </span><span class="sxs-lookup"><span data-stu-id="eda79-132">[Exponentiation operator](https://developer.microsoft.com/microsoft-edge/platform/status/exponentiationoperatores2016/?q=exponentiation%20operator) \(ES2016\)</span></span>  
*   <span data-ttu-id="eda79-133">[Destructuring](https://developer.microsoft.com/microsoft-edge/platform/status/destructuringES2015/?q=destructuring) \ (ES2015 \ ) </span><span class="sxs-lookup"><span data-stu-id="eda79-133">[Destructuring](https://developer.microsoft.com/microsoft-edge/platform/status/destructuringES2015/?q=destructuring) \(ES2015\)</span></span>  

### <span data-ttu-id="eda79-134">用户输入</span><span class="sxs-lookup"><span data-stu-id="eda79-134">User Input</span></span>  

<span data-ttu-id="eda79-135">EdgeHTML 13 中引入的以下功能改进了用户输入：</span><span class="sxs-lookup"><span data-stu-id="eda79-135">The following features introduced in EdgeHTML 13 improve user input:</span></span>  

*   [<meter> <span data-ttu-id="eda79-136">元素</span><span class="sxs-lookup"><span data-stu-id="eda79-136">element</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/meterelement)  
*   [<span data-ttu-id="eda79-137">元素文档和窗口的 oninvalid 事件处理程序</span><span class="sxs-lookup"><span data-stu-id="eda79-137">oninvalid event handler for the element document and window</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/oninvalideventhandler)  

### <span data-ttu-id="eda79-138">指针锁</span><span class="sxs-lookup"><span data-stu-id="eda79-138">Pointer Lock</span></span>  

<span data-ttu-id="eda79-139">Microsoft Edge 现在支持指针锁定 API \ (以前称为鼠标锁定 \ ) 以访问原始鼠标移动，将鼠标事件的目标锁定到单个元素，从而消除了鼠标移动距离单个方向的限制，以及从视图中删除光标。</span><span class="sxs-lookup"><span data-stu-id="eda79-139">Microsoft Edge now supports the Pointer Lock API \(previously called Mouse Lock\) for access to raw mouse movement, locking the target of mouse events to a single element, eliminating limits of how far mouse movement can go in a single direction, and removing the cursor from view.</span></span>  

## <span data-ttu-id="eda79-140">EdgeHTML 13 中的新 Api</span><span class="sxs-lookup"><span data-stu-id="eda79-140">New APIs in EdgeHTML 13</span></span>  

<span data-ttu-id="eda79-141">下面是 EdgeHTML 13 中新 Api 的完整列表。</span><span class="sxs-lookup"><span data-stu-id="eda79-141">Here's the full list of new APIs in EdgeHTML 13.</span></span>  <span data-ttu-id="eda79-142">它们以的格式列出 `[interface name].[api name]` 。</span><span class="sxs-lookup"><span data-stu-id="eda79-142">They are listed in the format of `[interface name].[api name]`.</span></span>  

<iframe height='584' scrolling='no' title='<span data-ttu-id="eda79-143">EdgeHTML 13 中的新 Api</span><span class="sxs-lookup"><span data-stu-id="eda79-143">New APIs in EdgeHTML 13</span></span>' src='//codepen.io/MicrosoftEdgeDocumentation/embed/vmzxEY/?height=584&theme-id=23761&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width:  100%;'><span data-ttu-id="eda79-144">请参阅 <a href='https://codepen.io/MicrosoftEdgeDocumentation/pen/vmzxEY/'> Microsoft Edge 文档中 EdgeHTML 13 的笔新 api </a> (<a href='http://codepen.io/MicrosoftEdgeDocumentation'> @MicrosoftEdgeDocumentation </a>) 在 <a href='http://codepen.io'> CodePen 上 </a> 。</span><span class="sxs-lookup"><span data-stu-id="eda79-144">See the Pen <a href='https://codepen.io/MicrosoftEdgeDocumentation/pen/vmzxEY/'>New APIs in EdgeHTML 13</a> by Microsoft Edge Docs (<a href='http://codepen.io/MicrosoftEdgeDocumentation'>@MicrosoftEdgeDocumentation</a>) on <a href='http://codepen.io'>CodePen</a>.</span></span></iframe>  
