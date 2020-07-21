---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2 Win32 c + + ICoreWebView2Settings
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: a2ecd4bdb2d27a5e881f52791ae21290c748966a
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886491"
---
# <span data-ttu-id="74d54-104">0.9.515-接口 ICoreWebView2Settings</span><span class="sxs-lookup"><span data-stu-id="74d54-104">0.9.515 - interface ICoreWebView2Settings</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2Settings
  : public IUnknown
```

<span data-ttu-id="74d54-105">定义启用、禁用或修改 Web 视图功能的属性。</span><span class="sxs-lookup"><span data-stu-id="74d54-105">Defines properties that enable, disable, or modify WebView features.</span></span>

## <span data-ttu-id="74d54-106">摘要</span><span class="sxs-lookup"><span data-stu-id="74d54-106">Summary</span></span>

 <span data-ttu-id="74d54-107">成员</span><span class="sxs-lookup"><span data-stu-id="74d54-107">Members</span></span>                        | <span data-ttu-id="74d54-108">描述</span><span class="sxs-lookup"><span data-stu-id="74d54-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="74d54-109">get_AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="74d54-109">get_AreDefaultContextMenusEnabled</span></span>](#get_aredefaultcontextmenusenabled) | <span data-ttu-id="74d54-110">AreDefaultContextMenusEnabled 属性用于阻止在 web 视图中向用户显示默认上下文菜单。</span><span class="sxs-lookup"><span data-stu-id="74d54-110">The AreDefaultContextMenusEnabled property is used to prevent default context menus from being shown to user in webview.</span></span>
[<span data-ttu-id="74d54-111">get_AreDefaultScriptDialogsEnabled</span><span class="sxs-lookup"><span data-stu-id="74d54-111">get_AreDefaultScriptDialogsEnabled</span></span>](#get_aredefaultscriptdialogsenabled) | <span data-ttu-id="74d54-112">加载新的 HTML 文档时，将使用 AreDefaultScriptDialogsEnabled。</span><span class="sxs-lookup"><span data-stu-id="74d54-112">AreDefaultScriptDialogsEnabled is used when loading a new HTML document.</span></span>
[<span data-ttu-id="74d54-113">get_AreDevToolsEnabled</span><span class="sxs-lookup"><span data-stu-id="74d54-113">get_AreDevToolsEnabled</span></span>](#get_aredevtoolsenabled) | <span data-ttu-id="74d54-114">AreDevToolsEnabled 控制用户是否可以使用上下文菜单或键盘快捷方式打开 DevTools 窗口。</span><span class="sxs-lookup"><span data-stu-id="74d54-114">AreDevToolsEnabled controls whether the user is able to use the context menu or keyboard shortcuts to open the DevTools window.</span></span>
[<span data-ttu-id="74d54-115">get_AreRemoteObjectsAllowed</span><span class="sxs-lookup"><span data-stu-id="74d54-115">get_AreRemoteObjectsAllowed</span></span>](#get_areremoteobjectsallowed) | <span data-ttu-id="74d54-116">AreRemoteObjectsAllowed 属性用于控制是否可以从 web 视图中的页面访问主机对象。</span><span class="sxs-lookup"><span data-stu-id="74d54-116">The AreRemoteObjectsAllowed property is used to control whether host objects are accessible from the page in webview.</span></span>
[<span data-ttu-id="74d54-117">get_IsBuiltInErrorPageEnabled</span><span class="sxs-lookup"><span data-stu-id="74d54-117">get_IsBuiltInErrorPageEnabled</span></span>](#get_isbuiltinerrorpageenabled) | <span data-ttu-id="74d54-118">IsBuiltInErrorPageEnabled 属性用于禁用内置错误页面，用于导航故障和呈现进程失败。</span><span class="sxs-lookup"><span data-stu-id="74d54-118">The IsBuiltInErrorPageEnabled property is used to disable built in error page for navigation failure and render process failure.</span></span>
[<span data-ttu-id="74d54-119">get_IsScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="74d54-119">get_IsScriptEnabled</span></span>](#get_isscriptenabled) | <span data-ttu-id="74d54-120">控制在 Web 视图中的所有未来导航中是否启用了 JavaScript 执行。</span><span class="sxs-lookup"><span data-stu-id="74d54-120">Controls if JavaScript execution is enabled in all future navigations in the WebView.</span></span>
[<span data-ttu-id="74d54-121">get_IsStatusBarEnabled</span><span class="sxs-lookup"><span data-stu-id="74d54-121">get_IsStatusBarEnabled</span></span>](#get_isstatusbarenabled) | <span data-ttu-id="74d54-122">IsStatusBarEnabled 控制状态栏是否将显示。</span><span class="sxs-lookup"><span data-stu-id="74d54-122">IsStatusBarEnabled controls whether the status bar will be displayed.</span></span>
[<span data-ttu-id="74d54-123">get_IsWebMessageEnabled</span><span class="sxs-lookup"><span data-stu-id="74d54-123">get_IsWebMessageEnabled</span></span>](#get_iswebmessageenabled) | <span data-ttu-id="74d54-124">加载新的 HTML 文档时，将使用 IsWebMessageEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="74d54-124">The IsWebMessageEnabled property is used when loading a new HTML document.</span></span>
[<span data-ttu-id="74d54-125">get_IsZoomControlEnabled</span><span class="sxs-lookup"><span data-stu-id="74d54-125">get_IsZoomControlEnabled</span></span>](#get_iszoomcontrolenabled) | <span data-ttu-id="74d54-126">IsZoomControlEnabled 属性用于阻止用户影响 Web 视图的缩放。</span><span class="sxs-lookup"><span data-stu-id="74d54-126">The IsZoomControlEnabled property is used to prevent the user from impacting the zoom of the WebView.</span></span>
[<span data-ttu-id="74d54-127">put_AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="74d54-127">put_AreDefaultContextMenusEnabled</span></span>](#put_aredefaultcontextmenusenabled) | <span data-ttu-id="74d54-128">设置 AreDefaultContextMenusEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="74d54-128">Set the AreDefaultContextMenusEnabled property.</span></span>
[<span data-ttu-id="74d54-129">put_AreDefaultScriptDialogsEnabled</span><span class="sxs-lookup"><span data-stu-id="74d54-129">put_AreDefaultScriptDialogsEnabled</span></span>](#put_aredefaultscriptdialogsenabled) | <span data-ttu-id="74d54-130">设置 AreDefaultScriptDialogsEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="74d54-130">Set the AreDefaultScriptDialogsEnabled property.</span></span>
[<span data-ttu-id="74d54-131">put_AreDevToolsEnabled</span><span class="sxs-lookup"><span data-stu-id="74d54-131">put_AreDevToolsEnabled</span></span>](#put_aredevtoolsenabled) | <span data-ttu-id="74d54-132">设置 AreDevToolsEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="74d54-132">Set the AreDevToolsEnabled property.</span></span>
[<span data-ttu-id="74d54-133">put_AreRemoteObjectsAllowed</span><span class="sxs-lookup"><span data-stu-id="74d54-133">put_AreRemoteObjectsAllowed</span></span>](#put_areremoteobjectsallowed) | <span data-ttu-id="74d54-134">设置 AreRemoteObjectsAllowed 属性。</span><span class="sxs-lookup"><span data-stu-id="74d54-134">Set the AreRemoteObjectsAllowed property.</span></span>
[<span data-ttu-id="74d54-135">put_IsBuiltInErrorPageEnabled</span><span class="sxs-lookup"><span data-stu-id="74d54-135">put_IsBuiltInErrorPageEnabled</span></span>](#put_isbuiltinerrorpageenabled) | <span data-ttu-id="74d54-136">设置 IsBuiltInErrorPageEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="74d54-136">Set the IsBuiltInErrorPageEnabled property.</span></span>
[<span data-ttu-id="74d54-137">put_IsScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="74d54-137">put_IsScriptEnabled</span></span>](#put_isscriptenabled) | <span data-ttu-id="74d54-138">设置 IsScriptEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="74d54-138">Set the IsScriptEnabled property.</span></span>
[<span data-ttu-id="74d54-139">put_IsStatusBarEnabled</span><span class="sxs-lookup"><span data-stu-id="74d54-139">put_IsStatusBarEnabled</span></span>](#put_isstatusbarenabled) | <span data-ttu-id="74d54-140">设置 IsStatusBarEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="74d54-140">Set the IsStatusBarEnabled property.</span></span>
[<span data-ttu-id="74d54-141">put_IsWebMessageEnabled</span><span class="sxs-lookup"><span data-stu-id="74d54-141">put_IsWebMessageEnabled</span></span>](#put_iswebmessageenabled) | <span data-ttu-id="74d54-142">设置 IsWebMessageEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="74d54-142">Set the IsWebMessageEnabled property.</span></span>
[<span data-ttu-id="74d54-143">put_IsZoomControlEnabled</span><span class="sxs-lookup"><span data-stu-id="74d54-143">put_IsZoomControlEnabled</span></span>](#put_iszoomcontrolenabled) | <span data-ttu-id="74d54-144">设置 IsZoomControlEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="74d54-144">Set the IsZoomControlEnabled property.</span></span>

<span data-ttu-id="74d54-145">在 NavigationStarting 事件之后设置所做的更改将不会应用到下一个顶级导航。</span><span class="sxs-lookup"><span data-stu-id="74d54-145">Setting changes made after NavigationStarting event will not apply until the next top level navigation.</span></span>

## <span data-ttu-id="74d54-146">成员</span><span class="sxs-lookup"><span data-stu-id="74d54-146">Members</span></span>

#### <span data-ttu-id="74d54-147">get_AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="74d54-147">get_AreDefaultContextMenusEnabled</span></span> 

<span data-ttu-id="74d54-148">AreDefaultContextMenusEnabled 属性用于阻止在 web 视图中向用户显示默认上下文菜单。</span><span class="sxs-lookup"><span data-stu-id="74d54-148">The AreDefaultContextMenusEnabled property is used to prevent default context menus from being shown to user in webview.</span></span>

> <span data-ttu-id="74d54-149">公共 HRESULT [get_AreDefaultContextMenusEnabled](#get_aredefaultcontextmenusenabled)（已启用 BOOL \*）</span><span class="sxs-lookup"><span data-stu-id="74d54-149">public HRESULT [get_AreDefaultContextMenusEnabled](#get_aredefaultcontextmenusenabled)(BOOL \* enabled)</span></span>

<span data-ttu-id="74d54-150">默认值为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="74d54-150">Defaults to TRUE.</span></span>

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

#### <span data-ttu-id="74d54-151">get_AreDefaultScriptDialogsEnabled</span><span class="sxs-lookup"><span data-stu-id="74d54-151">get_AreDefaultScriptDialogsEnabled</span></span> 

<span data-ttu-id="74d54-152">加载新的 HTML 文档时，将使用 AreDefaultScriptDialogsEnabled。</span><span class="sxs-lookup"><span data-stu-id="74d54-152">AreDefaultScriptDialogsEnabled is used when loading a new HTML document.</span></span>

> <span data-ttu-id="74d54-153">public HRESULT [get_AreDefaultScriptDialogsEnabled](#get_aredefaultscriptdialogsenabled)（BOOL \* AreDefaultScriptDialogsEnabled）</span><span class="sxs-lookup"><span data-stu-id="74d54-153">public HRESULT [get_AreDefaultScriptDialogsEnabled](#get_aredefaultscriptdialogsenabled)(BOOL \* areDefaultScriptDialogsEnabled)</span></span>

<span data-ttu-id="74d54-154">如果设置为 false，则 Web 视图不会呈现默认的 javascript 对话框（具体由 javascript 警报、confirm、prompt 函数和 beforeunload 事件所显示的对话框）。</span><span class="sxs-lookup"><span data-stu-id="74d54-154">If set to false, then WebView won't render the default javascript dialog box (Specifically those shown by the javascript alert, confirm, prompt functions and beforeunload event).</span></span> <span data-ttu-id="74d54-155">相反，如果 SetScriptDialogOpeningEventHandler 设置了事件处理程序，则 Web 视图将发送一个包含对话框的所有信息的事件，并允许主机应用显示其自己的自定义 UI。</span><span class="sxs-lookup"><span data-stu-id="74d54-155">Instead, if an event handler is set by SetScriptDialogOpeningEventHandler, WebView will send an event that will contain all of the information for the dialog and allow the host app to show its own custom UI.</span></span>

#### <span data-ttu-id="74d54-156">get_AreDevToolsEnabled</span><span class="sxs-lookup"><span data-stu-id="74d54-156">get_AreDevToolsEnabled</span></span> 

<span data-ttu-id="74d54-157">AreDevToolsEnabled 控制用户是否可以使用上下文菜单或键盘快捷方式打开 DevTools 窗口。</span><span class="sxs-lookup"><span data-stu-id="74d54-157">AreDevToolsEnabled controls whether the user is able to use the context menu or keyboard shortcuts to open the DevTools window.</span></span>

> <span data-ttu-id="74d54-158">public HRESULT [get_AreDevToolsEnabled](#get_aredevtoolsenabled)（BOOL \* AreDevToolsEnabled）</span><span class="sxs-lookup"><span data-stu-id="74d54-158">public HRESULT [get_AreDevToolsEnabled](#get_aredevtoolsenabled)(BOOL \* areDevToolsEnabled)</span></span>

<span data-ttu-id="74d54-159">默认情况下为 true。</span><span class="sxs-lookup"><span data-stu-id="74d54-159">It is true by default.</span></span>

#### <span data-ttu-id="74d54-160">get_AreRemoteObjectsAllowed</span><span class="sxs-lookup"><span data-stu-id="74d54-160">get_AreRemoteObjectsAllowed</span></span> 

<span data-ttu-id="74d54-161">AreRemoteObjectsAllowed 属性用于控制是否可以从 web 视图中的页面访问主机对象。</span><span class="sxs-lookup"><span data-stu-id="74d54-161">The AreRemoteObjectsAllowed property is used to control whether host objects are accessible from the page in webview.</span></span>

> <span data-ttu-id="74d54-162">公共 HRESULT [get_AreRemoteObjectsAllowed](#get_areremoteobjectsallowed)（允许使用 BOOL \*）</span><span class="sxs-lookup"><span data-stu-id="74d54-162">public HRESULT [get_AreRemoteObjectsAllowed](#get_areremoteobjectsallowed)(BOOL \* allowed)</span></span>

<span data-ttu-id="74d54-163">默认值为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="74d54-163">Defaults to TRUE.</span></span>

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

#### <span data-ttu-id="74d54-164">get_IsBuiltInErrorPageEnabled</span><span class="sxs-lookup"><span data-stu-id="74d54-164">get_IsBuiltInErrorPageEnabled</span></span> 

<span data-ttu-id="74d54-165">IsBuiltInErrorPageEnabled 属性用于禁用内置错误页面，用于导航故障和呈现进程失败。</span><span class="sxs-lookup"><span data-stu-id="74d54-165">The IsBuiltInErrorPageEnabled property is used to disable built in error page for navigation failure and render process failure.</span></span>

> <span data-ttu-id="74d54-166">公共 HRESULT [get_IsBuiltInErrorPageEnabled](#get_isbuiltinerrorpageenabled)（已启用 BOOL \*）</span><span class="sxs-lookup"><span data-stu-id="74d54-166">public HRESULT [get_IsBuiltInErrorPageEnabled](#get_isbuiltinerrorpageenabled)(BOOL \* enabled)</span></span>

<span data-ttu-id="74d54-167">默认值为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="74d54-167">Defaults to TRUE.</span></span> <span data-ttu-id="74d54-168">如果禁用，将在发生相关错误时显示空白页。</span><span class="sxs-lookup"><span data-stu-id="74d54-168">When disabled, blank page will be shown when related error happens.</span></span>

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

#### <span data-ttu-id="74d54-169">get_IsScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="74d54-169">get_IsScriptEnabled</span></span> 

<span data-ttu-id="74d54-170">控制在 Web 视图中的所有未来导航中是否启用了 JavaScript 执行。</span><span class="sxs-lookup"><span data-stu-id="74d54-170">Controls if JavaScript execution is enabled in all future navigations in the WebView.</span></span>

> <span data-ttu-id="74d54-171">public HRESULT [get_IsScriptEnabled](#get_isscriptenabled)（BOOL \* IsScriptEnabled）</span><span class="sxs-lookup"><span data-stu-id="74d54-171">public HRESULT [get_IsScriptEnabled](#get_isscriptenabled)(BOOL \* isScriptEnabled)</span></span>

<span data-ttu-id="74d54-172">这仅影响文档中的脚本;即使脚本被禁用，用 ExecuteScript 插入的脚本也会运行。</span><span class="sxs-lookup"><span data-stu-id="74d54-172">This only affects scripts in the document; scripts injected with ExecuteScript will run even if script is disabled.</span></span> <span data-ttu-id="74d54-173">默认情况下为 true。</span><span class="sxs-lookup"><span data-stu-id="74d54-173">It is true by default.</span></span>

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

#### <span data-ttu-id="74d54-174">get_IsStatusBarEnabled</span><span class="sxs-lookup"><span data-stu-id="74d54-174">get_IsStatusBarEnabled</span></span> 

<span data-ttu-id="74d54-175">IsStatusBarEnabled 控制状态栏是否将显示。</span><span class="sxs-lookup"><span data-stu-id="74d54-175">IsStatusBarEnabled controls whether the status bar will be displayed.</span></span>

> <span data-ttu-id="74d54-176">public HRESULT [get_IsStatusBarEnabled](#get_isstatusbarenabled)（BOOL \* IsStatusBarEnabled）</span><span class="sxs-lookup"><span data-stu-id="74d54-176">public HRESULT [get_IsStatusBarEnabled](#get_isstatusbarenabled)(BOOL \* isStatusBarEnabled)</span></span>

<span data-ttu-id="74d54-177">状态栏通常显示在 Web 视图的左下方，并且在用户悬停在其上方和其他信息时显示链接的 URI 等内容。</span><span class="sxs-lookup"><span data-stu-id="74d54-177">The status bar is usually displayed in the lower left of the WebView and shows things such as the URI of a link when the user hovers over it and other information.</span></span> <span data-ttu-id="74d54-178">默认情况下为 true。</span><span class="sxs-lookup"><span data-stu-id="74d54-178">It is true by default.</span></span>

#### <span data-ttu-id="74d54-179">get_IsWebMessageEnabled</span><span class="sxs-lookup"><span data-stu-id="74d54-179">get_IsWebMessageEnabled</span></span> 

<span data-ttu-id="74d54-180">加载新的 HTML 文档时，将使用 IsWebMessageEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="74d54-180">The IsWebMessageEnabled property is used when loading a new HTML document.</span></span>

> <span data-ttu-id="74d54-181">public HRESULT [get_IsWebMessageEnabled](#get_iswebmessageenabled)（BOOL \* IsWebMessageEnabled）</span><span class="sxs-lookup"><span data-stu-id="74d54-181">public HRESULT [get_IsWebMessageEnabled](#get_iswebmessageenabled)(BOOL \* isWebMessageEnabled)</span></span>

<span data-ttu-id="74d54-182">如果设置为 true，则通过 PostWebMessageAsJson、PostWebMessageAsString 和，从主机到 web 视图的顶级 HTML 文档的通信是允许通过 web 视图、和 window。 chrome 的消息事件（有关详细信息，请参阅 PostWebMessageAsJson 文档）。</span><span class="sxs-lookup"><span data-stu-id="74d54-182">If set to true, communication from the host to the webview's top level HTML document is allowed via PostWebMessageAsJson, PostWebMessageAsString, and window.chrome.webview's message event (see PostWebMessageAsJson documentation for details).</span></span> <span data-ttu-id="74d54-183">通过 window 的 postMessage 函数和 SetWebMessageReceivedEventHandler 方法，允许从 web 视图的顶级 HTML 文档到主机的通信（有关详细信息，请参阅 SetWebMessageReceivedEventHandler 文档）。</span><span class="sxs-lookup"><span data-stu-id="74d54-183">Communication from the webview's top level HTML document to the host is allowed via window.chrome.webview's postMessage function and the SetWebMessageReceivedEventHandler method (see the SetWebMessageReceivedEventHandler documentation for details).</span></span> <span data-ttu-id="74d54-184">如果设置为 false，则不允许通信。</span><span class="sxs-lookup"><span data-stu-id="74d54-184">If set to false, then communication is disallowed.</span></span> <span data-ttu-id="74d54-185">PostWebMessageAsJson 和 PostWebMessageAsString 将失败 E_ACCESSDENIED，并且通过引发 Error 对象的实例，postMessage 将失败。</span><span class="sxs-lookup"><span data-stu-id="74d54-185">PostWebMessageAsJson and PostWebMessageAsString will fail with E_ACCESSDENIED and window.chrome.webview.postMessage will fail by throwing an instance of an Error object.</span></span> <span data-ttu-id="74d54-186">默认情况下为 true。</span><span class="sxs-lookup"><span data-stu-id="74d54-186">It is true by default.</span></span>

```cpp
    ComPtr<ICoreWebView2Settings> settings;
    CHECK_FAILURE(m_webView->get_Settings(&settings));

    CHECK_FAILURE(settings->put_IsWebMessageEnabled(TRUE));
```

#### <span data-ttu-id="74d54-187">get_IsZoomControlEnabled</span><span class="sxs-lookup"><span data-stu-id="74d54-187">get_IsZoomControlEnabled</span></span> 

<span data-ttu-id="74d54-188">IsZoomControlEnabled 属性用于阻止用户影响 Web 视图的缩放。</span><span class="sxs-lookup"><span data-stu-id="74d54-188">The IsZoomControlEnabled property is used to prevent the user from impacting the zoom of the WebView.</span></span>

> <span data-ttu-id="74d54-189">公共 HRESULT [get_IsZoomControlEnabled](#get_iszoomcontrolenabled)（已启用 BOOL \*）</span><span class="sxs-lookup"><span data-stu-id="74d54-189">public HRESULT [get_IsZoomControlEnabled](#get_iszoomcontrolenabled)(BOOL \* enabled)</span></span>

<span data-ttu-id="74d54-190">默认值为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="74d54-190">Defaults to TRUE.</span></span> <span data-ttu-id="74d54-191">当禁用时，用户将无法使用 ctrl +/-或 ctrl + 鼠标滚轮进行缩放，但缩放可通过 ZoomFactor API 设置。</span><span class="sxs-lookup"><span data-stu-id="74d54-191">When disabled, user will not be able to zoom using ctrl+/- or ctrl+mouse wheel, but the zoom can be set via ZoomFactor API.</span></span>

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

#### <span data-ttu-id="74d54-192">put_AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="74d54-192">put_AreDefaultContextMenusEnabled</span></span> 

<span data-ttu-id="74d54-193">设置 AreDefaultContextMenusEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="74d54-193">Set the AreDefaultContextMenusEnabled property.</span></span>

> <span data-ttu-id="74d54-194">public HRESULT [put_AreDefaultContextMenusEnabled](#put_aredefaultcontextmenusenabled)（已启用 BOOL）</span><span class="sxs-lookup"><span data-stu-id="74d54-194">public HRESULT [put_AreDefaultContextMenusEnabled](#put_aredefaultcontextmenusenabled)(BOOL enabled)</span></span>

#### <span data-ttu-id="74d54-195">put_AreDefaultScriptDialogsEnabled</span><span class="sxs-lookup"><span data-stu-id="74d54-195">put_AreDefaultScriptDialogsEnabled</span></span> 

<span data-ttu-id="74d54-196">设置 AreDefaultScriptDialogsEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="74d54-196">Set the AreDefaultScriptDialogsEnabled property.</span></span>

> <span data-ttu-id="74d54-197">公共 HRESULT [put_AreDefaultScriptDialogsEnabled](#put_aredefaultscriptdialogsenabled)（布尔值 AreDefaultScriptDialogsEnabled）</span><span class="sxs-lookup"><span data-stu-id="74d54-197">public HRESULT [put_AreDefaultScriptDialogsEnabled](#put_aredefaultscriptdialogsenabled)(BOOL areDefaultScriptDialogsEnabled)</span></span>

#### <span data-ttu-id="74d54-198">put_AreDevToolsEnabled</span><span class="sxs-lookup"><span data-stu-id="74d54-198">put_AreDevToolsEnabled</span></span> 

<span data-ttu-id="74d54-199">设置 AreDevToolsEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="74d54-199">Set the AreDevToolsEnabled property.</span></span>

> <span data-ttu-id="74d54-200">公共 HRESULT [put_AreDevToolsEnabled](#put_aredevtoolsenabled)（布尔值 AreDevToolsEnabled）</span><span class="sxs-lookup"><span data-stu-id="74d54-200">public HRESULT [put_AreDevToolsEnabled](#put_aredevtoolsenabled)(BOOL areDevToolsEnabled)</span></span>

#### <span data-ttu-id="74d54-201">put_AreRemoteObjectsAllowed</span><span class="sxs-lookup"><span data-stu-id="74d54-201">put_AreRemoteObjectsAllowed</span></span> 

<span data-ttu-id="74d54-202">设置 AreRemoteObjectsAllowed 属性。</span><span class="sxs-lookup"><span data-stu-id="74d54-202">Set the AreRemoteObjectsAllowed property.</span></span>

> <span data-ttu-id="74d54-203">公共 HRESULT [put_AreRemoteObjectsAllowed](#put_areremoteobjectsallowed)（允许使用 BOOL）</span><span class="sxs-lookup"><span data-stu-id="74d54-203">public HRESULT [put_AreRemoteObjectsAllowed](#put_areremoteobjectsallowed)(BOOL allowed)</span></span>

#### <span data-ttu-id="74d54-204">put_IsBuiltInErrorPageEnabled</span><span class="sxs-lookup"><span data-stu-id="74d54-204">put_IsBuiltInErrorPageEnabled</span></span> 

<span data-ttu-id="74d54-205">设置 IsBuiltInErrorPageEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="74d54-205">Set the IsBuiltInErrorPageEnabled property.</span></span>

> <span data-ttu-id="74d54-206">public HRESULT [put_IsBuiltInErrorPageEnabled](#put_isbuiltinerrorpageenabled)（已启用 BOOL）</span><span class="sxs-lookup"><span data-stu-id="74d54-206">public HRESULT [put_IsBuiltInErrorPageEnabled](#put_isbuiltinerrorpageenabled)(BOOL enabled)</span></span>

#### <span data-ttu-id="74d54-207">put_IsScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="74d54-207">put_IsScriptEnabled</span></span> 

<span data-ttu-id="74d54-208">设置 IsScriptEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="74d54-208">Set the IsScriptEnabled property.</span></span>

> <span data-ttu-id="74d54-209">公共 HRESULT [put_IsScriptEnabled](#put_isscriptenabled)（布尔值 IsScriptEnabled）</span><span class="sxs-lookup"><span data-stu-id="74d54-209">public HRESULT [put_IsScriptEnabled](#put_isscriptenabled)(BOOL isScriptEnabled)</span></span>

#### <span data-ttu-id="74d54-210">put_IsStatusBarEnabled</span><span class="sxs-lookup"><span data-stu-id="74d54-210">put_IsStatusBarEnabled</span></span> 

<span data-ttu-id="74d54-211">设置 IsStatusBarEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="74d54-211">Set the IsStatusBarEnabled property.</span></span>

> <span data-ttu-id="74d54-212">公共 HRESULT [put_IsStatusBarEnabled](#put_isstatusbarenabled)（布尔值 IsStatusBarEnabled）</span><span class="sxs-lookup"><span data-stu-id="74d54-212">public HRESULT [put_IsStatusBarEnabled](#put_isstatusbarenabled)(BOOL isStatusBarEnabled)</span></span>

#### <span data-ttu-id="74d54-213">put_IsWebMessageEnabled</span><span class="sxs-lookup"><span data-stu-id="74d54-213">put_IsWebMessageEnabled</span></span> 

<span data-ttu-id="74d54-214">设置 IsWebMessageEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="74d54-214">Set the IsWebMessageEnabled property.</span></span>

> <span data-ttu-id="74d54-215">公共 HRESULT [put_IsWebMessageEnabled](#put_iswebmessageenabled)（布尔值 IsWebMessageEnabled）</span><span class="sxs-lookup"><span data-stu-id="74d54-215">public HRESULT [put_IsWebMessageEnabled](#put_iswebmessageenabled)(BOOL isWebMessageEnabled)</span></span>

#### <span data-ttu-id="74d54-216">put_IsZoomControlEnabled</span><span class="sxs-lookup"><span data-stu-id="74d54-216">put_IsZoomControlEnabled</span></span> 

<span data-ttu-id="74d54-217">设置 IsZoomControlEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="74d54-217">Set the IsZoomControlEnabled property.</span></span>

> <span data-ttu-id="74d54-218">public HRESULT [put_IsZoomControlEnabled](#put_iszoomcontrolenabled)（已启用 BOOL）</span><span class="sxs-lookup"><span data-stu-id="74d54-218">public HRESULT [put_IsZoomControlEnabled](#put_iszoomcontrolenabled)(BOOL enabled)</span></span>

