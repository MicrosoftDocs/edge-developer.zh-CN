---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: f0ac0bf7ae3b237bca45b22ed97ec16513666922
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10697551"
---
# <span data-ttu-id="26c41-104">CoreWebView2Settings 类的 WebView2</span><span class="sxs-lookup"><span data-stu-id="26c41-104">Microsoft.Web.WebView2.Core.CoreWebView2Settings class</span></span> 

> [!NOTE]
> <span data-ttu-id="26c41-105">SDK 版本0.9.515 后，此参考可能会更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="26c41-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="26c41-106">请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="26c41-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

<span data-ttu-id="26c41-107">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="26c41-107">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="26c41-108">程序集： Microsoft WebView2</span><span class="sxs-lookup"><span data-stu-id="26c41-108">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="26c41-109">定义启用、禁用或修改 Web 视图功能的属性。</span><span class="sxs-lookup"><span data-stu-id="26c41-109">Defines properties that enable, disable, or modify WebView features.</span></span>

## <span data-ttu-id="26c41-110">摘要</span><span class="sxs-lookup"><span data-stu-id="26c41-110">Summary</span></span>

 <span data-ttu-id="26c41-111">成员</span><span class="sxs-lookup"><span data-stu-id="26c41-111">Members</span></span>                        | <span data-ttu-id="26c41-112">描述</span><span class="sxs-lookup"><span data-stu-id="26c41-112">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="26c41-113">AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="26c41-113">AreDefaultContextMenusEnabled</span></span>](#aredefaultcontextmenusenabled) | <span data-ttu-id="26c41-114">AreDefaultContextMenusEnabled 属性用于阻止在 web 视图中向用户显示默认上下文菜单。</span><span class="sxs-lookup"><span data-stu-id="26c41-114">The AreDefaultContextMenusEnabled property is used to prevent default context menus from being shown to user in webview.</span></span>
[<span data-ttu-id="26c41-115">AreDefaultScriptDialogsEnabled</span><span class="sxs-lookup"><span data-stu-id="26c41-115">AreDefaultScriptDialogsEnabled</span></span>](#aredefaultscriptdialogsenabled) | <span data-ttu-id="26c41-116">加载新的 HTML 文档时，将使用 AreDefaultScriptDialogsEnabled。</span><span class="sxs-lookup"><span data-stu-id="26c41-116">AreDefaultScriptDialogsEnabled is used when loading a new HTML document.</span></span>
[<span data-ttu-id="26c41-117">AreDevToolsEnabled</span><span class="sxs-lookup"><span data-stu-id="26c41-117">AreDevToolsEnabled</span></span>](#aredevtoolsenabled) | <span data-ttu-id="26c41-118">AreDevToolsEnabled 控制用户是否可以使用上下文菜单或键盘快捷方式打开 DevTools 窗口。</span><span class="sxs-lookup"><span data-stu-id="26c41-118">AreDevToolsEnabled controls whether the user is able to use the context menu or keyboard shortcuts to open the DevTools window.</span></span>
[<span data-ttu-id="26c41-119">AreHostObjectsAllowed</span><span class="sxs-lookup"><span data-stu-id="26c41-119">AreHostObjectsAllowed</span></span>](#arehostobjectsallowed) | <span data-ttu-id="26c41-120">AreHostObjectsAllowed 属性用于控制是否可以从 web 视图中的页面访问主机对象。</span><span class="sxs-lookup"><span data-stu-id="26c41-120">The AreHostObjectsAllowed property is used to control whether host objects are accessible from the page in webview.</span></span>
[<span data-ttu-id="26c41-121">IsBuiltInErrorPageEnabled</span><span class="sxs-lookup"><span data-stu-id="26c41-121">IsBuiltInErrorPageEnabled</span></span>](#isbuiltinerrorpageenabled) | <span data-ttu-id="26c41-122">IsBuiltInErrorPageEnabled 属性用于禁用内置错误页面，用于导航故障和呈现进程失败。</span><span class="sxs-lookup"><span data-stu-id="26c41-122">The IsBuiltInErrorPageEnabled property is used to disable built in error page for navigation failure and render process failure.</span></span>
[<span data-ttu-id="26c41-123">IsScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="26c41-123">IsScriptEnabled</span></span>](#isscriptenabled) | <span data-ttu-id="26c41-124">控制在 Web 视图中的所有未来导航中是否启用了 JavaScript 执行。</span><span class="sxs-lookup"><span data-stu-id="26c41-124">Controls if JavaScript execution is enabled in all future navigations in the WebView.</span></span>
[<span data-ttu-id="26c41-125">IsStatusBarEnabled</span><span class="sxs-lookup"><span data-stu-id="26c41-125">IsStatusBarEnabled</span></span>](#isstatusbarenabled) | <span data-ttu-id="26c41-126">IsStatusBarEnabled 控制状态栏是否将显示。</span><span class="sxs-lookup"><span data-stu-id="26c41-126">IsStatusBarEnabled controls whether the status bar will be displayed.</span></span>
[<span data-ttu-id="26c41-127">IsWebMessageEnabled</span><span class="sxs-lookup"><span data-stu-id="26c41-127">IsWebMessageEnabled</span></span>](#iswebmessageenabled) | <span data-ttu-id="26c41-128">加载新的 HTML 文档时，将使用 IsWebMessageEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="26c41-128">The IsWebMessageEnabled property is used when loading a new HTML document.</span></span>
[<span data-ttu-id="26c41-129">IsZoomControlEnabled</span><span class="sxs-lookup"><span data-stu-id="26c41-129">IsZoomControlEnabled</span></span>](#iszoomcontrolenabled) | <span data-ttu-id="26c41-130">IsZoomControlEnabled 属性用于阻止用户影响 Web 视图的缩放。</span><span class="sxs-lookup"><span data-stu-id="26c41-130">The IsZoomControlEnabled property is used to prevent the user from impacting the zoom of the WebView.</span></span>

<span data-ttu-id="26c41-131">在 NavigationStarting 事件之后设置所做的更改将不会应用到下一个顶级导航。</span><span class="sxs-lookup"><span data-stu-id="26c41-131">Setting changes made after NavigationStarting event will not apply until the next top level navigation.</span></span>

## <span data-ttu-id="26c41-132">成员</span><span class="sxs-lookup"><span data-stu-id="26c41-132">Members</span></span>

#### <span data-ttu-id="26c41-133">AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="26c41-133">AreDefaultContextMenusEnabled</span></span> 

<span data-ttu-id="26c41-134">AreDefaultContextMenusEnabled 属性用于阻止在 web 视图中向用户显示默认上下文菜单。</span><span class="sxs-lookup"><span data-stu-id="26c41-134">The AreDefaultContextMenusEnabled property is used to prevent default context menus from being shown to user in webview.</span></span>

> <span data-ttu-id="26c41-135">公共 bool [AreDefaultContextMenusEnabled](#aredefaultcontextmenusenabled)</span><span class="sxs-lookup"><span data-stu-id="26c41-135">public bool [AreDefaultContextMenusEnabled](#aredefaultcontextmenusenabled)</span></span>

<span data-ttu-id="26c41-136">默认值为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="26c41-136">Defaults to TRUE.</span></span>

#### <span data-ttu-id="26c41-137">AreDefaultScriptDialogsEnabled</span><span class="sxs-lookup"><span data-stu-id="26c41-137">AreDefaultScriptDialogsEnabled</span></span> 

<span data-ttu-id="26c41-138">加载新的 HTML 文档时，将使用 AreDefaultScriptDialogsEnabled。</span><span class="sxs-lookup"><span data-stu-id="26c41-138">AreDefaultScriptDialogsEnabled is used when loading a new HTML document.</span></span>

> <span data-ttu-id="26c41-139">公共 bool [AreDefaultScriptDialogsEnabled](#aredefaultscriptdialogsenabled)</span><span class="sxs-lookup"><span data-stu-id="26c41-139">public bool [AreDefaultScriptDialogsEnabled](#aredefaultscriptdialogsenabled)</span></span>

<span data-ttu-id="26c41-140">如果设置为 false，则 Web 视图不会呈现默认的 javascript 对话框（具体由 javascript 警报、confirm、prompt 函数和 beforeunload 事件所显示的对话框）。</span><span class="sxs-lookup"><span data-stu-id="26c41-140">If set to false, then WebView won't render the default javascript dialog box (Specifically those shown by the javascript alert, confirm, prompt functions and beforeunload event).</span></span> <span data-ttu-id="26c41-141">相反，如果 SetScriptDialogOpeningEventHandler 设置了事件处理程序，则 Web 视图将发送一个包含对话框的所有信息的事件，并允许主机应用显示其自己的自定义 UI。</span><span class="sxs-lookup"><span data-stu-id="26c41-141">Instead, if an event handler is set by SetScriptDialogOpeningEventHandler, WebView will send an event that will contain all of the information for the dialog and allow the host app to show its own custom UI.</span></span>

#### <span data-ttu-id="26c41-142">AreDevToolsEnabled</span><span class="sxs-lookup"><span data-stu-id="26c41-142">AreDevToolsEnabled</span></span> 

<span data-ttu-id="26c41-143">AreDevToolsEnabled 控制用户是否可以使用上下文菜单或键盘快捷方式打开 DevTools 窗口。</span><span class="sxs-lookup"><span data-stu-id="26c41-143">AreDevToolsEnabled controls whether the user is able to use the context menu or keyboard shortcuts to open the DevTools window.</span></span>

> <span data-ttu-id="26c41-144">公共 bool [AreDevToolsEnabled](#aredevtoolsenabled)</span><span class="sxs-lookup"><span data-stu-id="26c41-144">public bool [AreDevToolsEnabled](#aredevtoolsenabled)</span></span>

<span data-ttu-id="26c41-145">默认情况下为 true。</span><span class="sxs-lookup"><span data-stu-id="26c41-145">It is true by default.</span></span>

#### <span data-ttu-id="26c41-146">AreHostObjectsAllowed</span><span class="sxs-lookup"><span data-stu-id="26c41-146">AreHostObjectsAllowed</span></span> 

<span data-ttu-id="26c41-147">AreHostObjectsAllowed 属性用于控制是否可以从 web 视图中的页面访问主机对象。</span><span class="sxs-lookup"><span data-stu-id="26c41-147">The AreHostObjectsAllowed property is used to control whether host objects are accessible from the page in webview.</span></span>

> <span data-ttu-id="26c41-148">公共 bool [AreHostObjectsAllowed](#arehostobjectsallowed)</span><span class="sxs-lookup"><span data-stu-id="26c41-148">public bool [AreHostObjectsAllowed](#arehostobjectsallowed)</span></span>

<span data-ttu-id="26c41-149">默认值为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="26c41-149">Defaults to TRUE.</span></span>

#### <span data-ttu-id="26c41-150">IsBuiltInErrorPageEnabled</span><span class="sxs-lookup"><span data-stu-id="26c41-150">IsBuiltInErrorPageEnabled</span></span> 

<span data-ttu-id="26c41-151">IsBuiltInErrorPageEnabled 属性用于禁用内置错误页面，用于导航故障和呈现进程失败。</span><span class="sxs-lookup"><span data-stu-id="26c41-151">The IsBuiltInErrorPageEnabled property is used to disable built in error page for navigation failure and render process failure.</span></span>

> <span data-ttu-id="26c41-152">公共 bool [IsBuiltInErrorPageEnabled](#isbuiltinerrorpageenabled)</span><span class="sxs-lookup"><span data-stu-id="26c41-152">public bool [IsBuiltInErrorPageEnabled](#isbuiltinerrorpageenabled)</span></span>

<span data-ttu-id="26c41-153">默认值为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="26c41-153">Defaults to TRUE.</span></span> <span data-ttu-id="26c41-154">如果禁用，将在发生相关错误时显示空白页。</span><span class="sxs-lookup"><span data-stu-id="26c41-154">When disabled, blank page will be shown when related error happens.</span></span>

#### <span data-ttu-id="26c41-155">IsScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="26c41-155">IsScriptEnabled</span></span> 

<span data-ttu-id="26c41-156">控制在 Web 视图中的所有未来导航中是否启用了 JavaScript 执行。</span><span class="sxs-lookup"><span data-stu-id="26c41-156">Controls if JavaScript execution is enabled in all future navigations in the WebView.</span></span>

> <span data-ttu-id="26c41-157">公共 bool [IsScriptEnabled](#isscriptenabled)</span><span class="sxs-lookup"><span data-stu-id="26c41-157">public bool [IsScriptEnabled](#isscriptenabled)</span></span>

<span data-ttu-id="26c41-158">这仅影响文档中的脚本;即使脚本被禁用，用 ExecuteScript 插入的脚本也会运行。</span><span class="sxs-lookup"><span data-stu-id="26c41-158">This only affects scripts in the document; scripts injected with ExecuteScript will run even if script is disabled.</span></span> <span data-ttu-id="26c41-159">默认情况下为 true。</span><span class="sxs-lookup"><span data-stu-id="26c41-159">It is true by default.</span></span>

#### <span data-ttu-id="26c41-160">IsStatusBarEnabled</span><span class="sxs-lookup"><span data-stu-id="26c41-160">IsStatusBarEnabled</span></span> 

<span data-ttu-id="26c41-161">IsStatusBarEnabled 控制状态栏是否将显示。</span><span class="sxs-lookup"><span data-stu-id="26c41-161">IsStatusBarEnabled controls whether the status bar will be displayed.</span></span>

> <span data-ttu-id="26c41-162">公共 bool [IsStatusBarEnabled](#isstatusbarenabled)</span><span class="sxs-lookup"><span data-stu-id="26c41-162">public bool [IsStatusBarEnabled](#isstatusbarenabled)</span></span>

<span data-ttu-id="26c41-163">状态栏通常显示在 Web 视图的左下方，并且在用户悬停在其上方和其他信息时显示链接的 URI 等内容。</span><span class="sxs-lookup"><span data-stu-id="26c41-163">The status bar is usually displayed in the lower left of the WebView and shows things such as the URI of a link when the user hovers over it and other information.</span></span> <span data-ttu-id="26c41-164">默认情况下为 true。</span><span class="sxs-lookup"><span data-stu-id="26c41-164">It is true by default.</span></span>

#### <span data-ttu-id="26c41-165">IsWebMessageEnabled</span><span class="sxs-lookup"><span data-stu-id="26c41-165">IsWebMessageEnabled</span></span> 

<span data-ttu-id="26c41-166">加载新的 HTML 文档时，将使用 IsWebMessageEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="26c41-166">The IsWebMessageEnabled property is used when loading a new HTML document.</span></span>

> <span data-ttu-id="26c41-167">公共 bool [IsWebMessageEnabled](#iswebmessageenabled)</span><span class="sxs-lookup"><span data-stu-id="26c41-167">public bool [IsWebMessageEnabled](#iswebmessageenabled)</span></span>

<span data-ttu-id="26c41-168">如果设置为 true，则通过 PostWebMessageAsJson、PostWebMessageAsString 和，从主机到 web 视图的顶级 HTML 文档的通信是允许通过 web 视图、和 window。 chrome 的消息事件（有关详细信息，请参阅 PostWebMessageAsJson 文档）。</span><span class="sxs-lookup"><span data-stu-id="26c41-168">If set to true, communication from the host to the webview's top level HTML document is allowed via PostWebMessageAsJson, PostWebMessageAsString, and window.chrome.webview's message event (see PostWebMessageAsJson documentation for details).</span></span> <span data-ttu-id="26c41-169">通过 window 的 postMessage 函数和 SetWebMessageReceivedEventHandler 方法，允许从 web 视图的顶级 HTML 文档到主机的通信（有关详细信息，请参阅 SetWebMessageReceivedEventHandler 文档）。</span><span class="sxs-lookup"><span data-stu-id="26c41-169">Communication from the webview's top level HTML document to the host is allowed via window.chrome.webview's postMessage function and the SetWebMessageReceivedEventHandler method (see the SetWebMessageReceivedEventHandler documentation for details).</span></span> <span data-ttu-id="26c41-170">如果设置为 false，则不允许通信。</span><span class="sxs-lookup"><span data-stu-id="26c41-170">If set to false, then communication is disallowed.</span></span> <span data-ttu-id="26c41-171">PostWebMessageAsJson 和 PostWebMessageAsString 将失败 E_ACCESSDENIED，并且通过引发 Error 对象的实例，postMessage 将失败。</span><span class="sxs-lookup"><span data-stu-id="26c41-171">PostWebMessageAsJson and PostWebMessageAsString will fail with E_ACCESSDENIED and window.chrome.webview.postMessage will fail by throwing an instance of an Error object.</span></span> <span data-ttu-id="26c41-172">默认情况下为 true。</span><span class="sxs-lookup"><span data-stu-id="26c41-172">It is true by default.</span></span>

#### <span data-ttu-id="26c41-173">IsZoomControlEnabled</span><span class="sxs-lookup"><span data-stu-id="26c41-173">IsZoomControlEnabled</span></span> 

<span data-ttu-id="26c41-174">IsZoomControlEnabled 属性用于阻止用户影响 Web 视图的缩放。</span><span class="sxs-lookup"><span data-stu-id="26c41-174">The IsZoomControlEnabled property is used to prevent the user from impacting the zoom of the WebView.</span></span>

> <span data-ttu-id="26c41-175">公共 bool [IsZoomControlEnabled](#iszoomcontrolenabled)</span><span class="sxs-lookup"><span data-stu-id="26c41-175">public bool [IsZoomControlEnabled](#iszoomcontrolenabled)</span></span>

<span data-ttu-id="26c41-176">默认值为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="26c41-176">Defaults to TRUE.</span></span> <span data-ttu-id="26c41-177">当禁用时，用户将无法使用 ctrl +/-或 ctrl + 鼠标滚轮进行缩放，但缩放可通过 ZoomFactor API 设置。</span><span class="sxs-lookup"><span data-stu-id="26c41-177">When disabled, user will not be able to zoom using ctrl+/- or ctrl+mouse wheel, but the zoom can be set via ZoomFactor API.</span></span>

