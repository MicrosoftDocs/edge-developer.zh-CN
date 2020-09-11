---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: CoreWebView2Settings 中的 WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、web 视图、新、wpf、winforms、app、edge、CoreWebView2、CoreWebView2Controller、浏览器控件、边缘 html、、浏览器控件、边缘 html、WebView2
ms.openlocfilehash: 87b78956c29dac74bd023556a8c495222d248e9f
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011663"
---
# <span data-ttu-id="c4f2c-104">CoreWebView2Settings 类的 WebView2</span><span class="sxs-lookup"><span data-stu-id="c4f2c-104">Microsoft.Web.WebView2.Core.CoreWebView2Settings class</span></span> 

<span data-ttu-id="c4f2c-105">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="c4f2c-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="c4f2c-106">程序集： Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="c4f2c-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="c4f2c-107">定义启用、禁用或修改 Web 视图功能的属性。</span><span class="sxs-lookup"><span data-stu-id="c4f2c-107">Defines properties that enable, disable, or modify WebView features.</span></span>

## <span data-ttu-id="c4f2c-108">摘要</span><span class="sxs-lookup"><span data-stu-id="c4f2c-108">Summary</span></span>

 <span data-ttu-id="c4f2c-109">成员</span><span class="sxs-lookup"><span data-stu-id="c4f2c-109">Members</span></span>                        | <span data-ttu-id="c4f2c-110">描述</span><span class="sxs-lookup"><span data-stu-id="c4f2c-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="c4f2c-111">AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="c4f2c-111">AreDefaultContextMenusEnabled</span></span>](#aredefaultcontextmenusenabled) | <span data-ttu-id="c4f2c-112">AreDefaultContextMenusEnabled 属性用于阻止在 Web 视图中向用户显示默认上下文菜单。</span><span class="sxs-lookup"><span data-stu-id="c4f2c-112">The AreDefaultContextMenusEnabled property is used to prevent default context menus from being shown to user in WebView.</span></span>
[<span data-ttu-id="c4f2c-113">AreDefaultScriptDialogsEnabled</span><span class="sxs-lookup"><span data-stu-id="c4f2c-113">AreDefaultScriptDialogsEnabled</span></span>](#aredefaultscriptdialogsenabled) | <span data-ttu-id="c4f2c-114">加载新的 HTML 文档时，将使用 AreDefaultScriptDialogsEnabled。</span><span class="sxs-lookup"><span data-stu-id="c4f2c-114">AreDefaultScriptDialogsEnabled is used when loading a new HTML document.</span></span>
[<span data-ttu-id="c4f2c-115">AreDevToolsEnabled</span><span class="sxs-lookup"><span data-stu-id="c4f2c-115">AreDevToolsEnabled</span></span>](#aredevtoolsenabled) | <span data-ttu-id="c4f2c-116">AreDevToolsEnabled 控制用户是否可以使用上下文菜单或键盘快捷方式打开 DevTools 窗口。</span><span class="sxs-lookup"><span data-stu-id="c4f2c-116">AreDevToolsEnabled controls whether the user is able to use the context menu or keyboard shortcuts to open the DevTools window.</span></span>
[<span data-ttu-id="c4f2c-117">AreHostObjectsAllowed</span><span class="sxs-lookup"><span data-stu-id="c4f2c-117">AreHostObjectsAllowed</span></span>](#arehostobjectsallowed) | <span data-ttu-id="c4f2c-118">AreHostObjectsAllowed 属性用于控制是否可以从 Web 视图中的页面访问主机对象。</span><span class="sxs-lookup"><span data-stu-id="c4f2c-118">The AreHostObjectsAllowed property is used to control whether host objects are accessible from the page in WebView.</span></span>
[<span data-ttu-id="c4f2c-119">IsBuiltInErrorPageEnabled</span><span class="sxs-lookup"><span data-stu-id="c4f2c-119">IsBuiltInErrorPageEnabled</span></span>](#isbuiltinerrorpageenabled) | <span data-ttu-id="c4f2c-120">IsBuiltInErrorPageEnabled 属性用于禁用内置错误页面，用于导航故障和呈现进程失败。</span><span class="sxs-lookup"><span data-stu-id="c4f2c-120">The IsBuiltInErrorPageEnabled property is used to disable built in error page for navigation failure and render process failure.</span></span>
[<span data-ttu-id="c4f2c-121">IsScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="c4f2c-121">IsScriptEnabled</span></span>](#isscriptenabled) | <span data-ttu-id="c4f2c-122">控制在 Web 视图中的所有未来导航中是否启用了 JavaScript 执行。</span><span class="sxs-lookup"><span data-stu-id="c4f2c-122">Controls if JavaScript execution is enabled in all future navigations in the WebView.</span></span>
[<span data-ttu-id="c4f2c-123">IsStatusBarEnabled</span><span class="sxs-lookup"><span data-stu-id="c4f2c-123">IsStatusBarEnabled</span></span>](#isstatusbarenabled) | <span data-ttu-id="c4f2c-124">IsStatusBarEnabled 控制状态栏是否将显示。</span><span class="sxs-lookup"><span data-stu-id="c4f2c-124">IsStatusBarEnabled controls whether the status bar will be displayed.</span></span>
[<span data-ttu-id="c4f2c-125">IsWebMessageEnabled</span><span class="sxs-lookup"><span data-stu-id="c4f2c-125">IsWebMessageEnabled</span></span>](#iswebmessageenabled) | <span data-ttu-id="c4f2c-126">加载新的 HTML 文档时，将使用 IsWebMessageEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="c4f2c-126">The IsWebMessageEnabled property is used when loading a new HTML document.</span></span>
[<span data-ttu-id="c4f2c-127">IsZoomControlEnabled</span><span class="sxs-lookup"><span data-stu-id="c4f2c-127">IsZoomControlEnabled</span></span>](#iszoomcontrolenabled) | <span data-ttu-id="c4f2c-128">IsZoomControlEnabled 属性用于阻止用户影响 Web 视图的缩放。</span><span class="sxs-lookup"><span data-stu-id="c4f2c-128">The IsZoomControlEnabled property is used to prevent the user from impacting the zoom of the WebView.</span></span>

<span data-ttu-id="c4f2c-129">在 NavigationStarting 事件之后设置所做的更改将不会应用到下一个顶级导航。</span><span class="sxs-lookup"><span data-stu-id="c4f2c-129">Setting changes made after NavigationStarting event will not apply until the next top level navigation.</span></span>

## <span data-ttu-id="c4f2c-130">成员</span><span class="sxs-lookup"><span data-stu-id="c4f2c-130">Members</span></span>

#### <span data-ttu-id="c4f2c-131">AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="c4f2c-131">AreDefaultContextMenusEnabled</span></span> 

<span data-ttu-id="c4f2c-132">AreDefaultContextMenusEnabled 属性用于阻止在 Web 视图中向用户显示默认上下文菜单。</span><span class="sxs-lookup"><span data-stu-id="c4f2c-132">The AreDefaultContextMenusEnabled property is used to prevent default context menus from being shown to user in WebView.</span></span>

> <span data-ttu-id="c4f2c-133">公共 bool [AreDefaultContextMenusEnabled](#aredefaultcontextmenusenabled)</span><span class="sxs-lookup"><span data-stu-id="c4f2c-133">public bool [AreDefaultContextMenusEnabled](#aredefaultcontextmenusenabled)</span></span>

<span data-ttu-id="c4f2c-134">默认情况下为 true。</span><span class="sxs-lookup"><span data-stu-id="c4f2c-134">It is true by default.</span></span>

#### <span data-ttu-id="c4f2c-135">AreDefaultScriptDialogsEnabled</span><span class="sxs-lookup"><span data-stu-id="c4f2c-135">AreDefaultScriptDialogsEnabled</span></span> 

<span data-ttu-id="c4f2c-136">加载新的 HTML 文档时，将使用 AreDefaultScriptDialogsEnabled。</span><span class="sxs-lookup"><span data-stu-id="c4f2c-136">AreDefaultScriptDialogsEnabled is used when loading a new HTML document.</span></span>

> <span data-ttu-id="c4f2c-137">公共 bool [AreDefaultScriptDialogsEnabled](#aredefaultscriptdialogsenabled)</span><span class="sxs-lookup"><span data-stu-id="c4f2c-137">public bool [AreDefaultScriptDialogsEnabled](#aredefaultscriptdialogsenabled)</span></span>

<span data-ttu-id="c4f2c-138">如果设置为 false，则 Web 视图不会呈现默认的 JavaScript 对话框 (特定的 JavaScript 对话框，具体由 JavaScript 警报、确认、提示函数和 beforeunload 事件) 所示。</span><span class="sxs-lookup"><span data-stu-id="c4f2c-138">If set to false, then WebView won't render the default JavaScript dialog box (Specifically those shown by the JavaScript alert, confirm, prompt functions and beforeunload event).</span></span> <span data-ttu-id="c4f2c-139">如果设置为 true，则还可以订阅将包含对话框的所有信息的 ScriptDialogOpening 事件，并允许主机应用显示其自己的自定义 UI。</span><span class="sxs-lookup"><span data-stu-id="c4f2c-139">If set to true, one can also subscribe to ScriptDialogOpening event that will contain all of the information for the dialog and allow the host app to show its own custom UI.</span></span> <span data-ttu-id="c4f2c-140">默认情况下为 true。</span><span class="sxs-lookup"><span data-stu-id="c4f2c-140">It is true by default.</span></span>

#### <span data-ttu-id="c4f2c-141">AreDevToolsEnabled</span><span class="sxs-lookup"><span data-stu-id="c4f2c-141">AreDevToolsEnabled</span></span> 

<span data-ttu-id="c4f2c-142">AreDevToolsEnabled 控制用户是否可以使用上下文菜单或键盘快捷方式打开 DevTools 窗口。</span><span class="sxs-lookup"><span data-stu-id="c4f2c-142">AreDevToolsEnabled controls whether the user is able to use the context menu or keyboard shortcuts to open the DevTools window.</span></span>

> <span data-ttu-id="c4f2c-143">公共 bool [AreDevToolsEnabled](#aredevtoolsenabled)</span><span class="sxs-lookup"><span data-stu-id="c4f2c-143">public bool [AreDevToolsEnabled](#aredevtoolsenabled)</span></span>

<span data-ttu-id="c4f2c-144">默认情况下为 true。</span><span class="sxs-lookup"><span data-stu-id="c4f2c-144">It is true by default.</span></span>

#### <span data-ttu-id="c4f2c-145">AreHostObjectsAllowed</span><span class="sxs-lookup"><span data-stu-id="c4f2c-145">AreHostObjectsAllowed</span></span> 

<span data-ttu-id="c4f2c-146">AreHostObjectsAllowed 属性用于控制是否可以从 Web 视图中的页面访问主机对象。</span><span class="sxs-lookup"><span data-stu-id="c4f2c-146">The AreHostObjectsAllowed property is used to control whether host objects are accessible from the page in WebView.</span></span>

> <span data-ttu-id="c4f2c-147">公共 bool [AreHostObjectsAllowed](#arehostobjectsallowed)</span><span class="sxs-lookup"><span data-stu-id="c4f2c-147">public bool [AreHostObjectsAllowed](#arehostobjectsallowed)</span></span>

<span data-ttu-id="c4f2c-148">默认情况下为 true。</span><span class="sxs-lookup"><span data-stu-id="c4f2c-148">It is true by default.</span></span>

#### <span data-ttu-id="c4f2c-149">IsBuiltInErrorPageEnabled</span><span class="sxs-lookup"><span data-stu-id="c4f2c-149">IsBuiltInErrorPageEnabled</span></span> 

<span data-ttu-id="c4f2c-150">IsBuiltInErrorPageEnabled 属性用于禁用内置错误页面，用于导航故障和呈现进程失败。</span><span class="sxs-lookup"><span data-stu-id="c4f2c-150">The IsBuiltInErrorPageEnabled property is used to disable built in error page for navigation failure and render process failure.</span></span>

> <span data-ttu-id="c4f2c-151">公共 bool [IsBuiltInErrorPageEnabled](#isbuiltinerrorpageenabled)</span><span class="sxs-lookup"><span data-stu-id="c4f2c-151">public bool [IsBuiltInErrorPageEnabled](#isbuiltinerrorpageenabled)</span></span>

<span data-ttu-id="c4f2c-152">默认情况下为 true。</span><span class="sxs-lookup"><span data-stu-id="c4f2c-152">It is true by default.</span></span> <span data-ttu-id="c4f2c-153">如果禁用，将在发生相关错误时显示空白页。</span><span class="sxs-lookup"><span data-stu-id="c4f2c-153">When disabled, blank page will be shown when related error happens.</span></span>

#### <span data-ttu-id="c4f2c-154">IsScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="c4f2c-154">IsScriptEnabled</span></span> 

<span data-ttu-id="c4f2c-155">控制在 Web 视图中的所有未来导航中是否启用了 JavaScript 执行。</span><span class="sxs-lookup"><span data-stu-id="c4f2c-155">Controls if JavaScript execution is enabled in all future navigations in the WebView.</span></span>

> <span data-ttu-id="c4f2c-156">公共 bool [IsScriptEnabled](#isscriptenabled)</span><span class="sxs-lookup"><span data-stu-id="c4f2c-156">public bool [IsScriptEnabled](#isscriptenabled)</span></span>

<span data-ttu-id="c4f2c-157">这仅影响文档中的脚本;即使脚本被禁用，用 ExecuteScript 插入的脚本也会运行。</span><span class="sxs-lookup"><span data-stu-id="c4f2c-157">This only affects scripts in the document; scripts injected with ExecuteScript will run even if script is disabled.</span></span> <span data-ttu-id="c4f2c-158">默认情况下为 true。</span><span class="sxs-lookup"><span data-stu-id="c4f2c-158">It is true by default.</span></span>

#### <span data-ttu-id="c4f2c-159">IsStatusBarEnabled</span><span class="sxs-lookup"><span data-stu-id="c4f2c-159">IsStatusBarEnabled</span></span> 

<span data-ttu-id="c4f2c-160">IsStatusBarEnabled 控制状态栏是否将显示。</span><span class="sxs-lookup"><span data-stu-id="c4f2c-160">IsStatusBarEnabled controls whether the status bar will be displayed.</span></span>

> <span data-ttu-id="c4f2c-161">公共 bool [IsStatusBarEnabled](#isstatusbarenabled)</span><span class="sxs-lookup"><span data-stu-id="c4f2c-161">public bool [IsStatusBarEnabled](#isstatusbarenabled)</span></span>

<span data-ttu-id="c4f2c-162">状态栏通常显示在 Web 视图的左下方，并且在用户悬停在其上方和其他信息时显示链接的 URI 等内容。</span><span class="sxs-lookup"><span data-stu-id="c4f2c-162">The status bar is usually displayed in the lower left of the WebView and shows things such as the URI of a link when the user hovers over it and other information.</span></span> <span data-ttu-id="c4f2c-163">默认情况下为 true。</span><span class="sxs-lookup"><span data-stu-id="c4f2c-163">It is true by default.</span></span>

#### <span data-ttu-id="c4f2c-164">IsWebMessageEnabled</span><span class="sxs-lookup"><span data-stu-id="c4f2c-164">IsWebMessageEnabled</span></span> 

<span data-ttu-id="c4f2c-165">加载新的 HTML 文档时，将使用 IsWebMessageEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="c4f2c-165">The IsWebMessageEnabled property is used when loading a new HTML document.</span></span>

> <span data-ttu-id="c4f2c-166">公共 bool [IsWebMessageEnabled](#iswebmessageenabled)</span><span class="sxs-lookup"><span data-stu-id="c4f2c-166">public bool [IsWebMessageEnabled](#iswebmessageenabled)</span></span>

<span data-ttu-id="c4f2c-167">如果设置为 true，则通过 PostWebMessageAsJson、PostWebMessageAsString 和 window HTML 文档从主机到 Web 视图的顶级 HTML 文档的通信是允许的。 web 视图的消息事件 (有关详细信息) ，请参阅 PostWebMessageAsJson 文档。</span><span class="sxs-lookup"><span data-stu-id="c4f2c-167">If set to true, communication from the host to the WebView's top level HTML document is allowed via PostWebMessageAsJson, PostWebMessageAsString, and window.chrome.webview's message event (see PostWebMessageAsJson documentation for details).</span></span> <span data-ttu-id="c4f2c-168">通过 postMessage 函数和 WebMessageReceived (事件，从 Web 视图的顶级 HTML 文档到主机的通信是允许的，请参阅 WebMessageReceived 文档了解详细信息) 。</span><span class="sxs-lookup"><span data-stu-id="c4f2c-168">Communication from the WebView's top level HTML document to the host is allowed via window.chrome.webview's postMessage function and the WebMessageReceived event (see WebMessageReceived documentation for details).</span></span> <span data-ttu-id="c4f2c-169">如果设置为 false，则不允许通信。</span><span class="sxs-lookup"><span data-stu-id="c4f2c-169">If set to false, then communication is disallowed.</span></span> <span data-ttu-id="c4f2c-170">PostWebMessageAsJson 和 PostWebMessageAsString 将失败 E_ACCESSDENIED，并且通过引发 Error 对象的实例，postMessage 将失败。</span><span class="sxs-lookup"><span data-stu-id="c4f2c-170">PostWebMessageAsJson and PostWebMessageAsString will fail with E_ACCESSDENIED and window.chrome.webview.postMessage will fail by throwing an instance of an Error object.</span></span> <span data-ttu-id="c4f2c-171">默认情况下为 true。</span><span class="sxs-lookup"><span data-stu-id="c4f2c-171">It is true by default.</span></span>

#### <span data-ttu-id="c4f2c-172">IsZoomControlEnabled</span><span class="sxs-lookup"><span data-stu-id="c4f2c-172">IsZoomControlEnabled</span></span> 

<span data-ttu-id="c4f2c-173">IsZoomControlEnabled 属性用于阻止用户影响 Web 视图的缩放。</span><span class="sxs-lookup"><span data-stu-id="c4f2c-173">The IsZoomControlEnabled property is used to prevent the user from impacting the zoom of the WebView.</span></span>

> <span data-ttu-id="c4f2c-174">公共 bool [IsZoomControlEnabled](#iszoomcontrolenabled)</span><span class="sxs-lookup"><span data-stu-id="c4f2c-174">public bool [IsZoomControlEnabled](#iszoomcontrolenabled)</span></span>

<span data-ttu-id="c4f2c-175">默认情况下为 true。</span><span class="sxs-lookup"><span data-stu-id="c4f2c-175">It is true by default.</span></span> <span data-ttu-id="c4f2c-176">当禁用时，用户将无法使用 ctrl +/-或 ctrl + 鼠标滚轮进行缩放，但缩放可通过 ZoomFactor API 设置。</span><span class="sxs-lookup"><span data-stu-id="c4f2c-176">When disabled, user will not be able to zoom using ctrl+/- or ctrl+mouse wheel, but the zoom can be set via ZoomFactor API.</span></span>

