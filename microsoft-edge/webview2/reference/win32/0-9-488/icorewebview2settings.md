---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2 Win32 c + + ICoreWebView2Settings
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: a996660bb667ca0e556326e0bf2b71c15b9344c2
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10880330"
---
# <span data-ttu-id="9ad8d-104">0.9.515-接口 ICoreWebView2Settings</span><span class="sxs-lookup"><span data-stu-id="9ad8d-104">0.9.515 - interface ICoreWebView2Settings</span></span> 

> [!NOTE]
> <span data-ttu-id="9ad8d-105">SDK 版本0.9.515 后，此参考可能会更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="9ad8d-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="9ad8d-106">请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="9ad8d-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2Settings
  : public IUnknown
```

<span data-ttu-id="9ad8d-107">定义启用、禁用或修改 Web 视图功能的属性。</span><span class="sxs-lookup"><span data-stu-id="9ad8d-107">Defines properties that enable, disable, or modify WebView features.</span></span>

## <span data-ttu-id="9ad8d-108">摘要</span><span class="sxs-lookup"><span data-stu-id="9ad8d-108">Summary</span></span>

 <span data-ttu-id="9ad8d-109">成员</span><span class="sxs-lookup"><span data-stu-id="9ad8d-109">Members</span></span>                        | <span data-ttu-id="9ad8d-110">描述</span><span class="sxs-lookup"><span data-stu-id="9ad8d-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="9ad8d-111">get_AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="9ad8d-111">get_AreDefaultContextMenusEnabled</span></span>](#get_aredefaultcontextmenusenabled) | <span data-ttu-id="9ad8d-112">AreDefaultContextMenusEnabled 属性用于阻止在 web 视图中向用户显示默认上下文菜单。</span><span class="sxs-lookup"><span data-stu-id="9ad8d-112">The AreDefaultContextMenusEnabled property is used to prevent default context menus from being shown to user in webview.</span></span>
[<span data-ttu-id="9ad8d-113">get_AreDefaultScriptDialogsEnabled</span><span class="sxs-lookup"><span data-stu-id="9ad8d-113">get_AreDefaultScriptDialogsEnabled</span></span>](#get_aredefaultscriptdialogsenabled) | <span data-ttu-id="9ad8d-114">加载新的 HTML 文档时，将使用 AreDefaultScriptDialogsEnabled。</span><span class="sxs-lookup"><span data-stu-id="9ad8d-114">AreDefaultScriptDialogsEnabled is used when loading a new HTML document.</span></span>
[<span data-ttu-id="9ad8d-115">get_AreDevToolsEnabled</span><span class="sxs-lookup"><span data-stu-id="9ad8d-115">get_AreDevToolsEnabled</span></span>](#get_aredevtoolsenabled) | <span data-ttu-id="9ad8d-116">AreDevToolsEnabled 控制用户是否可以使用上下文菜单或键盘快捷方式打开 DevTools 窗口。</span><span class="sxs-lookup"><span data-stu-id="9ad8d-116">AreDevToolsEnabled controls whether the user is able to use the context menu or keyboard shortcuts to open the DevTools window.</span></span>
[<span data-ttu-id="9ad8d-117">get_AreRemoteObjectsAllowed</span><span class="sxs-lookup"><span data-stu-id="9ad8d-117">get_AreRemoteObjectsAllowed</span></span>](#get_areremoteobjectsallowed) | <span data-ttu-id="9ad8d-118">AreRemoteObjectsAllowed 属性用于控制是否可以从 web 视图中的页面访问主机对象。</span><span class="sxs-lookup"><span data-stu-id="9ad8d-118">The AreRemoteObjectsAllowed property is used to control whether host objects are accessible from the page in webview.</span></span>
[<span data-ttu-id="9ad8d-119">get_IsBuiltInErrorPageEnabled</span><span class="sxs-lookup"><span data-stu-id="9ad8d-119">get_IsBuiltInErrorPageEnabled</span></span>](#get_isbuiltinerrorpageenabled) | <span data-ttu-id="9ad8d-120">IsBuiltInErrorPageEnabled 属性用于禁用内置错误页面，用于导航故障和呈现进程失败。</span><span class="sxs-lookup"><span data-stu-id="9ad8d-120">The IsBuiltInErrorPageEnabled property is used to disable built in error page for navigation failure and render process failure.</span></span>
[<span data-ttu-id="9ad8d-121">get_IsScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="9ad8d-121">get_IsScriptEnabled</span></span>](#get_isscriptenabled) | <span data-ttu-id="9ad8d-122">控制在 Web 视图中的所有未来导航中是否启用了 JavaScript 执行。</span><span class="sxs-lookup"><span data-stu-id="9ad8d-122">Controls if JavaScript execution is enabled in all future navigations in the WebView.</span></span>
[<span data-ttu-id="9ad8d-123">get_IsStatusBarEnabled</span><span class="sxs-lookup"><span data-stu-id="9ad8d-123">get_IsStatusBarEnabled</span></span>](#get_isstatusbarenabled) | <span data-ttu-id="9ad8d-124">IsStatusBarEnabled 控制状态栏是否将显示。</span><span class="sxs-lookup"><span data-stu-id="9ad8d-124">IsStatusBarEnabled controls whether the status bar will be displayed.</span></span>
[<span data-ttu-id="9ad8d-125">get_IsWebMessageEnabled</span><span class="sxs-lookup"><span data-stu-id="9ad8d-125">get_IsWebMessageEnabled</span></span>](#get_iswebmessageenabled) | <span data-ttu-id="9ad8d-126">加载新的 HTML 文档时，将使用 IsWebMessageEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="9ad8d-126">The IsWebMessageEnabled property is used when loading a new HTML document.</span></span>
[<span data-ttu-id="9ad8d-127">get_IsZoomControlEnabled</span><span class="sxs-lookup"><span data-stu-id="9ad8d-127">get_IsZoomControlEnabled</span></span>](#get_iszoomcontrolenabled) | <span data-ttu-id="9ad8d-128">IsZoomControlEnabled 属性用于阻止用户影响 Web 视图的缩放。</span><span class="sxs-lookup"><span data-stu-id="9ad8d-128">The IsZoomControlEnabled property is used to prevent the user from impacting the zoom of the WebView.</span></span>
[<span data-ttu-id="9ad8d-129">put_AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="9ad8d-129">put_AreDefaultContextMenusEnabled</span></span>](#put_aredefaultcontextmenusenabled) | <span data-ttu-id="9ad8d-130">设置 AreDefaultContextMenusEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="9ad8d-130">Set the AreDefaultContextMenusEnabled property.</span></span>
[<span data-ttu-id="9ad8d-131">put_AreDefaultScriptDialogsEnabled</span><span class="sxs-lookup"><span data-stu-id="9ad8d-131">put_AreDefaultScriptDialogsEnabled</span></span>](#put_aredefaultscriptdialogsenabled) | <span data-ttu-id="9ad8d-132">设置 AreDefaultScriptDialogsEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="9ad8d-132">Set the AreDefaultScriptDialogsEnabled property.</span></span>
[<span data-ttu-id="9ad8d-133">put_AreDevToolsEnabled</span><span class="sxs-lookup"><span data-stu-id="9ad8d-133">put_AreDevToolsEnabled</span></span>](#put_aredevtoolsenabled) | <span data-ttu-id="9ad8d-134">设置 AreDevToolsEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="9ad8d-134">Set the AreDevToolsEnabled property.</span></span>
[<span data-ttu-id="9ad8d-135">put_AreRemoteObjectsAllowed</span><span class="sxs-lookup"><span data-stu-id="9ad8d-135">put_AreRemoteObjectsAllowed</span></span>](#put_areremoteobjectsallowed) | <span data-ttu-id="9ad8d-136">设置 AreRemoteObjectsAllowed 属性。</span><span class="sxs-lookup"><span data-stu-id="9ad8d-136">Set the AreRemoteObjectsAllowed property.</span></span>
[<span data-ttu-id="9ad8d-137">put_IsBuiltInErrorPageEnabled</span><span class="sxs-lookup"><span data-stu-id="9ad8d-137">put_IsBuiltInErrorPageEnabled</span></span>](#put_isbuiltinerrorpageenabled) | <span data-ttu-id="9ad8d-138">设置 IsBuiltInErrorPageEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="9ad8d-138">Set the IsBuiltInErrorPageEnabled property.</span></span>
[<span data-ttu-id="9ad8d-139">put_IsScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="9ad8d-139">put_IsScriptEnabled</span></span>](#put_isscriptenabled) | <span data-ttu-id="9ad8d-140">设置 IsScriptEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="9ad8d-140">Set the IsScriptEnabled property.</span></span>
[<span data-ttu-id="9ad8d-141">put_IsStatusBarEnabled</span><span class="sxs-lookup"><span data-stu-id="9ad8d-141">put_IsStatusBarEnabled</span></span>](#put_isstatusbarenabled) | <span data-ttu-id="9ad8d-142">设置 IsStatusBarEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="9ad8d-142">Set the IsStatusBarEnabled property.</span></span>
[<span data-ttu-id="9ad8d-143">put_IsWebMessageEnabled</span><span class="sxs-lookup"><span data-stu-id="9ad8d-143">put_IsWebMessageEnabled</span></span>](#put_iswebmessageenabled) | <span data-ttu-id="9ad8d-144">设置 IsWebMessageEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="9ad8d-144">Set the IsWebMessageEnabled property.</span></span>
[<span data-ttu-id="9ad8d-145">put_IsZoomControlEnabled</span><span class="sxs-lookup"><span data-stu-id="9ad8d-145">put_IsZoomControlEnabled</span></span>](#put_iszoomcontrolenabled) | <span data-ttu-id="9ad8d-146">设置 IsZoomControlEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="9ad8d-146">Set the IsZoomControlEnabled property.</span></span>

<span data-ttu-id="9ad8d-147">在 NavigationStarting 事件之后设置所做的更改将不会应用到下一个顶级导航。</span><span class="sxs-lookup"><span data-stu-id="9ad8d-147">Setting changes made after NavigationStarting event will not apply until the next top level navigation.</span></span>

## <span data-ttu-id="9ad8d-148">成员</span><span class="sxs-lookup"><span data-stu-id="9ad8d-148">Members</span></span>

#### <span data-ttu-id="9ad8d-149">get_AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="9ad8d-149">get_AreDefaultContextMenusEnabled</span></span> 

<span data-ttu-id="9ad8d-150">AreDefaultContextMenusEnabled 属性用于阻止在 web 视图中向用户显示默认上下文菜单。</span><span class="sxs-lookup"><span data-stu-id="9ad8d-150">The AreDefaultContextMenusEnabled property is used to prevent default context menus from being shown to user in webview.</span></span>

> <span data-ttu-id="9ad8d-151">公共 HRESULT [get_AreDefaultContextMenusEnabled](#get_aredefaultcontextmenusenabled)（已启用 BOOL \*）</span><span class="sxs-lookup"><span data-stu-id="9ad8d-151">public HRESULT [get_AreDefaultContextMenusEnabled](#get_aredefaultcontextmenusenabled)(BOOL \* enabled)</span></span>

<span data-ttu-id="9ad8d-152">默认值为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="9ad8d-152">Defaults to TRUE.</span></span>

```cpp
            BOOL allowContextMenus;
            CHECK_FAILURE(m_settings->get_AreDefaultContextMenusEnabled(
                &allowContextMenus));
            if (allowContextMenus) {
                CHECK_FAILURE(m_settings->put_AreDefaultContextMenusEnabled(FALSE));
                MessageBox(nullptr,
                L"Context menus will be disabled after the next navigation.",
                L"Settings change", MB_OK);
            }
            else {
                CHECK_FAILURE(m_settings->put_AreDefaultContextMenusEnabled(TRUE));
                MessageBox(nullptr,
                    L"Context menus will be enabled after the next navigation.",
                    L"Settings change", MB_OK);
            }
```

#### <span data-ttu-id="9ad8d-153">get_AreDefaultScriptDialogsEnabled</span><span class="sxs-lookup"><span data-stu-id="9ad8d-153">get_AreDefaultScriptDialogsEnabled</span></span> 

<span data-ttu-id="9ad8d-154">加载新的 HTML 文档时，将使用 AreDefaultScriptDialogsEnabled。</span><span class="sxs-lookup"><span data-stu-id="9ad8d-154">AreDefaultScriptDialogsEnabled is used when loading a new HTML document.</span></span>

> <span data-ttu-id="9ad8d-155">public HRESULT [get_AreDefaultScriptDialogsEnabled](#get_aredefaultscriptdialogsenabled)（BOOL \* AreDefaultScriptDialogsEnabled）</span><span class="sxs-lookup"><span data-stu-id="9ad8d-155">public HRESULT [get_AreDefaultScriptDialogsEnabled](#get_aredefaultscriptdialogsenabled)(BOOL \* areDefaultScriptDialogsEnabled)</span></span>

<span data-ttu-id="9ad8d-156">如果设置为 false，则 Web 视图不会呈现默认的 javascript 对话框（具体由 javascript 警报、confirm、prompt 函数和 beforeunload 事件所显示的对话框）。</span><span class="sxs-lookup"><span data-stu-id="9ad8d-156">If set to false, then WebView won't render the default javascript dialog box (Specifically those shown by the javascript alert, confirm, prompt functions and beforeunload event).</span></span> <span data-ttu-id="9ad8d-157">相反，如果 SetScriptDialogOpeningEventHandler 设置了事件处理程序，则 Web 视图将发送一个包含对话框的所有信息的事件，并允许主机应用显示其自己的自定义 UI。</span><span class="sxs-lookup"><span data-stu-id="9ad8d-157">Instead, if an event handler is set by SetScriptDialogOpeningEventHandler, WebView will send an event that will contain all of the information for the dialog and allow the host app to show its own custom UI.</span></span>

#### <span data-ttu-id="9ad8d-158">get_AreDevToolsEnabled</span><span class="sxs-lookup"><span data-stu-id="9ad8d-158">get_AreDevToolsEnabled</span></span> 

<span data-ttu-id="9ad8d-159">AreDevToolsEnabled 控制用户是否可以使用上下文菜单或键盘快捷方式打开 DevTools 窗口。</span><span class="sxs-lookup"><span data-stu-id="9ad8d-159">AreDevToolsEnabled controls whether the user is able to use the context menu or keyboard shortcuts to open the DevTools window.</span></span>

> <span data-ttu-id="9ad8d-160">public HRESULT [get_AreDevToolsEnabled](#get_aredevtoolsenabled)（BOOL \* AreDevToolsEnabled）</span><span class="sxs-lookup"><span data-stu-id="9ad8d-160">public HRESULT [get_AreDevToolsEnabled](#get_aredevtoolsenabled)(BOOL \* areDevToolsEnabled)</span></span>

<span data-ttu-id="9ad8d-161">默认情况下为 true。</span><span class="sxs-lookup"><span data-stu-id="9ad8d-161">It is true by default.</span></span>

#### <span data-ttu-id="9ad8d-162">get_AreRemoteObjectsAllowed</span><span class="sxs-lookup"><span data-stu-id="9ad8d-162">get_AreRemoteObjectsAllowed</span></span> 

<span data-ttu-id="9ad8d-163">AreRemoteObjectsAllowed 属性用于控制是否可以从 web 视图中的页面访问主机对象。</span><span class="sxs-lookup"><span data-stu-id="9ad8d-163">The AreRemoteObjectsAllowed property is used to control whether host objects are accessible from the page in webview.</span></span>

> <span data-ttu-id="9ad8d-164">公共 HRESULT [get_AreRemoteObjectsAllowed](#get_areremoteobjectsallowed)（允许使用 BOOL \*）</span><span class="sxs-lookup"><span data-stu-id="9ad8d-164">public HRESULT [get_AreRemoteObjectsAllowed](#get_areremoteobjectsallowed)(BOOL \* allowed)</span></span>

<span data-ttu-id="9ad8d-165">默认值为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="9ad8d-165">Defaults to TRUE.</span></span>

```cpp
            BOOL allowRemoteObjects;
            CHECK_FAILURE(m_settings->get_AreRemoteObjectsAllowed(&allowRemoteObjects));
            if (allowRemoteObjects)
            {
                CHECK_FAILURE(m_settings->put_AreRemoteObjectsAllowed(FALSE));
                MessageBox(
                    nullptr, L"Access to remote objects will be denied after the next navigation.",
                    L"Settings change", MB_OK);
            }
            else
            {
                CHECK_FAILURE(m_settings->put_AreRemoteObjectsAllowed(TRUE));
                MessageBox(
                    nullptr, L"Access to remote objects will be allowed after the next navigation.",
                    L"Settings change", MB_OK);
            }
```

#### <span data-ttu-id="9ad8d-166">get_IsBuiltInErrorPageEnabled</span><span class="sxs-lookup"><span data-stu-id="9ad8d-166">get_IsBuiltInErrorPageEnabled</span></span> 

<span data-ttu-id="9ad8d-167">IsBuiltInErrorPageEnabled 属性用于禁用内置错误页面，用于导航故障和呈现进程失败。</span><span class="sxs-lookup"><span data-stu-id="9ad8d-167">The IsBuiltInErrorPageEnabled property is used to disable built in error page for navigation failure and render process failure.</span></span>

> <span data-ttu-id="9ad8d-168">公共 HRESULT [get_IsBuiltInErrorPageEnabled](#get_isbuiltinerrorpageenabled)（已启用 BOOL \*）</span><span class="sxs-lookup"><span data-stu-id="9ad8d-168">public HRESULT [get_IsBuiltInErrorPageEnabled](#get_isbuiltinerrorpageenabled)(BOOL \* enabled)</span></span>

<span data-ttu-id="9ad8d-169">默认值为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="9ad8d-169">Defaults to TRUE.</span></span> <span data-ttu-id="9ad8d-170">如果禁用，将在发生相关错误时显示空白页。</span><span class="sxs-lookup"><span data-stu-id="9ad8d-170">When disabled, blank page will be shown when related error happens.</span></span>

```cpp
            BOOL enabled;
            CHECK_FAILURE(m_settings->get_IsBuiltInErrorPageEnabled(&enabled));
            if (enabled)
            {
                CHECK_FAILURE(m_settings->put_IsBuiltInErrorPageEnabled(FALSE));
                MessageBox(
                    nullptr, L"Built-in error page will be disabled for future navigation.",
                    L"Settings change", MB_OK);
            }
            else
            {
                CHECK_FAILURE(m_settings->put_IsBuiltInErrorPageEnabled(TRUE));
                MessageBox(
                    nullptr, L"Built-in error page will be enabled for future navigation.",
                    L"Settings change", MB_OK);
            }
```

#### <span data-ttu-id="9ad8d-171">get_IsScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="9ad8d-171">get_IsScriptEnabled</span></span> 

<span data-ttu-id="9ad8d-172">控制在 Web 视图中的所有未来导航中是否启用了 JavaScript 执行。</span><span class="sxs-lookup"><span data-stu-id="9ad8d-172">Controls if JavaScript execution is enabled in all future navigations in the WebView.</span></span>

> <span data-ttu-id="9ad8d-173">public HRESULT [get_IsScriptEnabled](#get_isscriptenabled)（BOOL \* IsScriptEnabled）</span><span class="sxs-lookup"><span data-stu-id="9ad8d-173">public HRESULT [get_IsScriptEnabled](#get_isscriptenabled)(BOOL \* isScriptEnabled)</span></span>

<span data-ttu-id="9ad8d-174">这仅影响文档中的脚本;即使脚本被禁用，用 ExecuteScript 插入的脚本也会运行。</span><span class="sxs-lookup"><span data-stu-id="9ad8d-174">This only affects scripts in the document; scripts injected with ExecuteScript will run even if script is disabled.</span></span> <span data-ttu-id="9ad8d-175">默认情况下为 true。</span><span class="sxs-lookup"><span data-stu-id="9ad8d-175">It is true by default.</span></span>

```cpp
        // Changes to settings will apply at the next navigation, which includes the
        // navigation after a NavigationStarting event.  We can use this to change
        // settings according to what site we're visiting.
        if (ShouldBlockScriptForUri(uri.get()))
        {
            m_settings->put_IsScriptEnabled(FALSE);
        }
        else
        {
            m_settings->put_IsScriptEnabled(m_isScriptEnabled);
        }
```

#### <span data-ttu-id="9ad8d-176">get_IsStatusBarEnabled</span><span class="sxs-lookup"><span data-stu-id="9ad8d-176">get_IsStatusBarEnabled</span></span> 

<span data-ttu-id="9ad8d-177">IsStatusBarEnabled 控制状态栏是否将显示。</span><span class="sxs-lookup"><span data-stu-id="9ad8d-177">IsStatusBarEnabled controls whether the status bar will be displayed.</span></span>

> <span data-ttu-id="9ad8d-178">public HRESULT [get_IsStatusBarEnabled](#get_isstatusbarenabled)（BOOL \* IsStatusBarEnabled）</span><span class="sxs-lookup"><span data-stu-id="9ad8d-178">public HRESULT [get_IsStatusBarEnabled](#get_isstatusbarenabled)(BOOL \* isStatusBarEnabled)</span></span>

<span data-ttu-id="9ad8d-179">状态栏通常显示在 Web 视图的左下方，并且在用户悬停在其上方和其他信息时显示链接的 URI 等内容。</span><span class="sxs-lookup"><span data-stu-id="9ad8d-179">The status bar is usually displayed in the lower left of the WebView and shows things such as the URI of a link when the user hovers over it and other information.</span></span> <span data-ttu-id="9ad8d-180">默认情况下为 true。</span><span class="sxs-lookup"><span data-stu-id="9ad8d-180">It is true by default.</span></span>

#### <span data-ttu-id="9ad8d-181">get_IsWebMessageEnabled</span><span class="sxs-lookup"><span data-stu-id="9ad8d-181">get_IsWebMessageEnabled</span></span> 

<span data-ttu-id="9ad8d-182">加载新的 HTML 文档时，将使用 IsWebMessageEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="9ad8d-182">The IsWebMessageEnabled property is used when loading a new HTML document.</span></span>

> <span data-ttu-id="9ad8d-183">public HRESULT [get_IsWebMessageEnabled](#get_iswebmessageenabled)（BOOL \* IsWebMessageEnabled）</span><span class="sxs-lookup"><span data-stu-id="9ad8d-183">public HRESULT [get_IsWebMessageEnabled](#get_iswebmessageenabled)(BOOL \* isWebMessageEnabled)</span></span>

<span data-ttu-id="9ad8d-184">如果设置为 true，则通过 PostWebMessageAsJson、PostWebMessageAsString 和，从主机到 web 视图的顶级 HTML 文档的通信是允许通过 web 视图、和 window。 chrome 的消息事件（有关详细信息，请参阅 PostWebMessageAsJson 文档）。</span><span class="sxs-lookup"><span data-stu-id="9ad8d-184">If set to true, communication from the host to the webview's top level HTML document is allowed via PostWebMessageAsJson, PostWebMessageAsString, and window.chrome.webview's message event (see PostWebMessageAsJson documentation for details).</span></span> <span data-ttu-id="9ad8d-185">通过 window 的 postMessage 函数和 SetWebMessageReceivedEventHandler 方法，允许从 web 视图的顶级 HTML 文档到主机的通信（有关详细信息，请参阅 SetWebMessageReceivedEventHandler 文档）。</span><span class="sxs-lookup"><span data-stu-id="9ad8d-185">Communication from the webview's top level HTML document to the host is allowed via window.chrome.webview's postMessage function and the SetWebMessageReceivedEventHandler method (see the SetWebMessageReceivedEventHandler documentation for details).</span></span> <span data-ttu-id="9ad8d-186">如果设置为 false，则不允许通信。</span><span class="sxs-lookup"><span data-stu-id="9ad8d-186">If set to false, then communication is disallowed.</span></span> <span data-ttu-id="9ad8d-187">PostWebMessageAsJson 和 PostWebMessageAsString 将失败 E_ACCESSDENIED，并且通过引发 Error 对象的实例，postMessage 将失败。</span><span class="sxs-lookup"><span data-stu-id="9ad8d-187">PostWebMessageAsJson and PostWebMessageAsString will fail with E_ACCESSDENIED and window.chrome.webview.postMessage will fail by throwing an instance of an Error object.</span></span> <span data-ttu-id="9ad8d-188">默认情况下为 true。</span><span class="sxs-lookup"><span data-stu-id="9ad8d-188">It is true by default.</span></span>

```cpp
    ComPtr<ICoreWebView2Settings> settings;
    CHECK_FAILURE(m_webView->get_Settings(&settings));

    CHECK_FAILURE(settings->put_IsWebMessageEnabled(TRUE));
```

#### <span data-ttu-id="9ad8d-189">get_IsZoomControlEnabled</span><span class="sxs-lookup"><span data-stu-id="9ad8d-189">get_IsZoomControlEnabled</span></span> 

<span data-ttu-id="9ad8d-190">IsZoomControlEnabled 属性用于阻止用户影响 Web 视图的缩放。</span><span class="sxs-lookup"><span data-stu-id="9ad8d-190">The IsZoomControlEnabled property is used to prevent the user from impacting the zoom of the WebView.</span></span>

> <span data-ttu-id="9ad8d-191">公共 HRESULT [get_IsZoomControlEnabled](#get_iszoomcontrolenabled)（已启用 BOOL \*）</span><span class="sxs-lookup"><span data-stu-id="9ad8d-191">public HRESULT [get_IsZoomControlEnabled](#get_iszoomcontrolenabled)(BOOL \* enabled)</span></span>

<span data-ttu-id="9ad8d-192">默认值为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="9ad8d-192">Defaults to TRUE.</span></span> <span data-ttu-id="9ad8d-193">当禁用时，用户将无法使用 ctrl +/-或 ctrl + 鼠标滚轮进行缩放，但缩放可通过 ZoomFactor API 设置。</span><span class="sxs-lookup"><span data-stu-id="9ad8d-193">When disabled, user will not be able to zoom using ctrl+/- or ctrl+mouse wheel, but the zoom can be set via ZoomFactor API.</span></span>

```cpp
            BOOL zoomControlEnabled;
            CHECK_FAILURE(m_settings->get_IsZoomControlEnabled(&zoomControlEnabled));
            if (zoomControlEnabled)
            {
                CHECK_FAILURE(m_settings->put_IsZoomControlEnabled(FALSE));
                MessageBox(
                    nullptr, L"Zoom control will be disabled after the next navigation.", L"Settings change",
                    MB_OK);
            }
            else
            {
                CHECK_FAILURE(m_settings->put_IsZoomControlEnabled(TRUE));
                MessageBox(
                    nullptr, L"Zoom control will be enabled after the next navigation.", L"Settings change",
                    MB_OK);
            }
```

#### <span data-ttu-id="9ad8d-194">put_AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="9ad8d-194">put_AreDefaultContextMenusEnabled</span></span> 

<span data-ttu-id="9ad8d-195">设置 AreDefaultContextMenusEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="9ad8d-195">Set the AreDefaultContextMenusEnabled property.</span></span>

> <span data-ttu-id="9ad8d-196">public HRESULT [put_AreDefaultContextMenusEnabled](#put_aredefaultcontextmenusenabled)（已启用 BOOL）</span><span class="sxs-lookup"><span data-stu-id="9ad8d-196">public HRESULT [put_AreDefaultContextMenusEnabled](#put_aredefaultcontextmenusenabled)(BOOL enabled)</span></span>

#### <span data-ttu-id="9ad8d-197">put_AreDefaultScriptDialogsEnabled</span><span class="sxs-lookup"><span data-stu-id="9ad8d-197">put_AreDefaultScriptDialogsEnabled</span></span> 

<span data-ttu-id="9ad8d-198">设置 AreDefaultScriptDialogsEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="9ad8d-198">Set the AreDefaultScriptDialogsEnabled property.</span></span>

> <span data-ttu-id="9ad8d-199">公共 HRESULT [put_AreDefaultScriptDialogsEnabled](#put_aredefaultscriptdialogsenabled)（布尔值 AreDefaultScriptDialogsEnabled）</span><span class="sxs-lookup"><span data-stu-id="9ad8d-199">public HRESULT [put_AreDefaultScriptDialogsEnabled](#put_aredefaultscriptdialogsenabled)(BOOL areDefaultScriptDialogsEnabled)</span></span>

#### <span data-ttu-id="9ad8d-200">put_AreDevToolsEnabled</span><span class="sxs-lookup"><span data-stu-id="9ad8d-200">put_AreDevToolsEnabled</span></span> 

<span data-ttu-id="9ad8d-201">设置 AreDevToolsEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="9ad8d-201">Set the AreDevToolsEnabled property.</span></span>

> <span data-ttu-id="9ad8d-202">公共 HRESULT [put_AreDevToolsEnabled](#put_aredevtoolsenabled)（布尔值 AreDevToolsEnabled）</span><span class="sxs-lookup"><span data-stu-id="9ad8d-202">public HRESULT [put_AreDevToolsEnabled](#put_aredevtoolsenabled)(BOOL areDevToolsEnabled)</span></span>

#### <span data-ttu-id="9ad8d-203">put_AreRemoteObjectsAllowed</span><span class="sxs-lookup"><span data-stu-id="9ad8d-203">put_AreRemoteObjectsAllowed</span></span> 

<span data-ttu-id="9ad8d-204">设置 AreRemoteObjectsAllowed 属性。</span><span class="sxs-lookup"><span data-stu-id="9ad8d-204">Set the AreRemoteObjectsAllowed property.</span></span>

> <span data-ttu-id="9ad8d-205">公共 HRESULT [put_AreRemoteObjectsAllowed](#put_areremoteobjectsallowed)（允许使用 BOOL）</span><span class="sxs-lookup"><span data-stu-id="9ad8d-205">public HRESULT [put_AreRemoteObjectsAllowed](#put_areremoteobjectsallowed)(BOOL allowed)</span></span>

#### <span data-ttu-id="9ad8d-206">put_IsBuiltInErrorPageEnabled</span><span class="sxs-lookup"><span data-stu-id="9ad8d-206">put_IsBuiltInErrorPageEnabled</span></span> 

<span data-ttu-id="9ad8d-207">设置 IsBuiltInErrorPageEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="9ad8d-207">Set the IsBuiltInErrorPageEnabled property.</span></span>

> <span data-ttu-id="9ad8d-208">public HRESULT [put_IsBuiltInErrorPageEnabled](#put_isbuiltinerrorpageenabled)（已启用 BOOL）</span><span class="sxs-lookup"><span data-stu-id="9ad8d-208">public HRESULT [put_IsBuiltInErrorPageEnabled](#put_isbuiltinerrorpageenabled)(BOOL enabled)</span></span>

#### <span data-ttu-id="9ad8d-209">put_IsScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="9ad8d-209">put_IsScriptEnabled</span></span> 

<span data-ttu-id="9ad8d-210">设置 IsScriptEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="9ad8d-210">Set the IsScriptEnabled property.</span></span>

> <span data-ttu-id="9ad8d-211">公共 HRESULT [put_IsScriptEnabled](#put_isscriptenabled)（布尔值 IsScriptEnabled）</span><span class="sxs-lookup"><span data-stu-id="9ad8d-211">public HRESULT [put_IsScriptEnabled](#put_isscriptenabled)(BOOL isScriptEnabled)</span></span>

#### <span data-ttu-id="9ad8d-212">put_IsStatusBarEnabled</span><span class="sxs-lookup"><span data-stu-id="9ad8d-212">put_IsStatusBarEnabled</span></span> 

<span data-ttu-id="9ad8d-213">设置 IsStatusBarEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="9ad8d-213">Set the IsStatusBarEnabled property.</span></span>

> <span data-ttu-id="9ad8d-214">公共 HRESULT [put_IsStatusBarEnabled](#put_isstatusbarenabled)（布尔值 IsStatusBarEnabled）</span><span class="sxs-lookup"><span data-stu-id="9ad8d-214">public HRESULT [put_IsStatusBarEnabled](#put_isstatusbarenabled)(BOOL isStatusBarEnabled)</span></span>

#### <span data-ttu-id="9ad8d-215">put_IsWebMessageEnabled</span><span class="sxs-lookup"><span data-stu-id="9ad8d-215">put_IsWebMessageEnabled</span></span> 

<span data-ttu-id="9ad8d-216">设置 IsWebMessageEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="9ad8d-216">Set the IsWebMessageEnabled property.</span></span>

> <span data-ttu-id="9ad8d-217">公共 HRESULT [put_IsWebMessageEnabled](#put_iswebmessageenabled)（布尔值 IsWebMessageEnabled）</span><span class="sxs-lookup"><span data-stu-id="9ad8d-217">public HRESULT [put_IsWebMessageEnabled](#put_iswebmessageenabled)(BOOL isWebMessageEnabled)</span></span>

#### <span data-ttu-id="9ad8d-218">put_IsZoomControlEnabled</span><span class="sxs-lookup"><span data-stu-id="9ad8d-218">put_IsZoomControlEnabled</span></span> 

<span data-ttu-id="9ad8d-219">设置 IsZoomControlEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="9ad8d-219">Set the IsZoomControlEnabled property.</span></span>

> <span data-ttu-id="9ad8d-220">public HRESULT [put_IsZoomControlEnabled](#put_iszoomcontrolenabled)（已启用 BOOL）</span><span class="sxs-lookup"><span data-stu-id="9ad8d-220">public HRESULT [put_IsZoomControlEnabled](#put_iszoomcontrolenabled)(BOOL enabled)</span></span>

