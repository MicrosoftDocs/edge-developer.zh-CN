---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/28/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 83193a6034184a630122864d5893ed6869ed88ce
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10653150"
---
# <span data-ttu-id="5a06c-104">interface ICoreWebView2Settings</span><span class="sxs-lookup"><span data-stu-id="5a06c-104">interface ICoreWebView2Settings</span></span> 

```
interface ICoreWebView2Settings
  : public IUnknown
```

<span data-ttu-id="5a06c-105">定义启用、禁用或修改 Web 视图功能的属性。</span><span class="sxs-lookup"><span data-stu-id="5a06c-105">Defines properties that enable, disable, or modify WebView features.</span></span>

## <span data-ttu-id="5a06c-106">摘要</span><span class="sxs-lookup"><span data-stu-id="5a06c-106">Summary</span></span>

 <span data-ttu-id="5a06c-107">成员</span><span class="sxs-lookup"><span data-stu-id="5a06c-107">Members</span></span>                        | <span data-ttu-id="5a06c-108">描述</span><span class="sxs-lookup"><span data-stu-id="5a06c-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="5a06c-109">get_AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="5a06c-109">get_AreDefaultContextMenusEnabled</span></span>](#get_aredefaultcontextmenusenabled) | <span data-ttu-id="5a06c-110">AreDefaultContextMenusEnabled 属性用于阻止在 web 视图中向用户显示默认上下文菜单。</span><span class="sxs-lookup"><span data-stu-id="5a06c-110">The AreDefaultContextMenusEnabled property is used to prevent default context menus from being shown to user in webview.</span></span>
[<span data-ttu-id="5a06c-111">get_AreDefaultScriptDialogsEnabled</span><span class="sxs-lookup"><span data-stu-id="5a06c-111">get_AreDefaultScriptDialogsEnabled</span></span>](#get_aredefaultscriptdialogsenabled) | <span data-ttu-id="5a06c-112">加载新的 HTML 文档时，将使用 AreDefaultScriptDialogsEnabled。</span><span class="sxs-lookup"><span data-stu-id="5a06c-112">AreDefaultScriptDialogsEnabled is used when loading a new HTML document.</span></span>
[<span data-ttu-id="5a06c-113">get_AreDevToolsEnabled</span><span class="sxs-lookup"><span data-stu-id="5a06c-113">get_AreDevToolsEnabled</span></span>](#get_aredevtoolsenabled) | <span data-ttu-id="5a06c-114">AreDevToolsEnabled 控制用户是否可以使用上下文菜单或键盘快捷方式打开 DevTools 窗口。</span><span class="sxs-lookup"><span data-stu-id="5a06c-114">AreDevToolsEnabled controls whether the user is able to use the context menu or keyboard shortcuts to open the DevTools window.</span></span>
[<span data-ttu-id="5a06c-115">get_AreRemoteObjectsAllowed</span><span class="sxs-lookup"><span data-stu-id="5a06c-115">get_AreRemoteObjectsAllowed</span></span>](#get_areremoteobjectsallowed) | <span data-ttu-id="5a06c-116">AreRemoteObjectsAllowed 属性用于控制是否可以从 web 视图中的页面访问主机对象。</span><span class="sxs-lookup"><span data-stu-id="5a06c-116">The AreRemoteObjectsAllowed property is used to control whether host objects are accessible from the page in webview.</span></span>
[<span data-ttu-id="5a06c-117">get_IsBuiltInErrorPageEnabled</span><span class="sxs-lookup"><span data-stu-id="5a06c-117">get_IsBuiltInErrorPageEnabled</span></span>](#get_isbuiltinerrorpageenabled) | <span data-ttu-id="5a06c-118">IsBuiltInErrorPageEnabled 属性用于禁用内置错误页面，用于导航故障和呈现进程失败。</span><span class="sxs-lookup"><span data-stu-id="5a06c-118">The IsBuiltInErrorPageEnabled property is used to disable built in error page for navigation failure and render process failure.</span></span>
[<span data-ttu-id="5a06c-119">get_IsScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="5a06c-119">get_IsScriptEnabled</span></span>](#get_isscriptenabled) | <span data-ttu-id="5a06c-120">控制在 Web 视图中的所有未来导航中是否启用了 JavaScript 执行。</span><span class="sxs-lookup"><span data-stu-id="5a06c-120">Controls if JavaScript execution is enabled in all future navigations in the WebView.</span></span>
[<span data-ttu-id="5a06c-121">get_IsStatusBarEnabled</span><span class="sxs-lookup"><span data-stu-id="5a06c-121">get_IsStatusBarEnabled</span></span>](#get_isstatusbarenabled) | <span data-ttu-id="5a06c-122">IsStatusBarEnabled 控制状态栏是否将显示。</span><span class="sxs-lookup"><span data-stu-id="5a06c-122">IsStatusBarEnabled controls whether the status bar will be displayed.</span></span>
[<span data-ttu-id="5a06c-123">get_IsWebMessageEnabled</span><span class="sxs-lookup"><span data-stu-id="5a06c-123">get_IsWebMessageEnabled</span></span>](#get_iswebmessageenabled) | <span data-ttu-id="5a06c-124">加载新的 HTML 文档时，将使用 IsWebMessageEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="5a06c-124">The IsWebMessageEnabled property is used when loading a new HTML document.</span></span>
[<span data-ttu-id="5a06c-125">get_IsZoomControlEnabled</span><span class="sxs-lookup"><span data-stu-id="5a06c-125">get_IsZoomControlEnabled</span></span>](#get_iszoomcontrolenabled) | <span data-ttu-id="5a06c-126">IsZoomControlEnabled 属性用于阻止用户影响 Web 视图的缩放。</span><span class="sxs-lookup"><span data-stu-id="5a06c-126">The IsZoomControlEnabled property is used to prevent the user from impacting the zoom of the WebView.</span></span>
[<span data-ttu-id="5a06c-127">put_AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="5a06c-127">put_AreDefaultContextMenusEnabled</span></span>](#put_aredefaultcontextmenusenabled) | <span data-ttu-id="5a06c-128">设置 AreDefaultContextMenusEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="5a06c-128">Set the AreDefaultContextMenusEnabled property.</span></span>
[<span data-ttu-id="5a06c-129">put_AreDefaultScriptDialogsEnabled</span><span class="sxs-lookup"><span data-stu-id="5a06c-129">put_AreDefaultScriptDialogsEnabled</span></span>](#put_aredefaultscriptdialogsenabled) | <span data-ttu-id="5a06c-130">设置 AreDefaultScriptDialogsEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="5a06c-130">Set the AreDefaultScriptDialogsEnabled property.</span></span>
[<span data-ttu-id="5a06c-131">put_AreDevToolsEnabled</span><span class="sxs-lookup"><span data-stu-id="5a06c-131">put_AreDevToolsEnabled</span></span>](#put_aredevtoolsenabled) | <span data-ttu-id="5a06c-132">设置 AreDevToolsEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="5a06c-132">Set the AreDevToolsEnabled property.</span></span>
[<span data-ttu-id="5a06c-133">put_AreRemoteObjectsAllowed</span><span class="sxs-lookup"><span data-stu-id="5a06c-133">put_AreRemoteObjectsAllowed</span></span>](#put_areremoteobjectsallowed) | <span data-ttu-id="5a06c-134">设置 AreRemoteObjectsAllowed 属性。</span><span class="sxs-lookup"><span data-stu-id="5a06c-134">Set the AreRemoteObjectsAllowed property.</span></span>
[<span data-ttu-id="5a06c-135">put_IsBuiltInErrorPageEnabled</span><span class="sxs-lookup"><span data-stu-id="5a06c-135">put_IsBuiltInErrorPageEnabled</span></span>](#put_isbuiltinerrorpageenabled) | <span data-ttu-id="5a06c-136">设置 IsBuiltInErrorPageEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="5a06c-136">Set the IsBuiltInErrorPageEnabled property.</span></span>
[<span data-ttu-id="5a06c-137">put_IsScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="5a06c-137">put_IsScriptEnabled</span></span>](#put_isscriptenabled) | <span data-ttu-id="5a06c-138">设置 IsScriptEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="5a06c-138">Set the IsScriptEnabled property.</span></span>
[<span data-ttu-id="5a06c-139">put_IsStatusBarEnabled</span><span class="sxs-lookup"><span data-stu-id="5a06c-139">put_IsStatusBarEnabled</span></span>](#put_isstatusbarenabled) | <span data-ttu-id="5a06c-140">设置 IsStatusBarEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="5a06c-140">Set the IsStatusBarEnabled property.</span></span>
[<span data-ttu-id="5a06c-141">put_IsWebMessageEnabled</span><span class="sxs-lookup"><span data-stu-id="5a06c-141">put_IsWebMessageEnabled</span></span>](#put_iswebmessageenabled) | <span data-ttu-id="5a06c-142">设置 IsWebMessageEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="5a06c-142">Set the IsWebMessageEnabled property.</span></span>
[<span data-ttu-id="5a06c-143">put_IsZoomControlEnabled</span><span class="sxs-lookup"><span data-stu-id="5a06c-143">put_IsZoomControlEnabled</span></span>](#put_iszoomcontrolenabled) | <span data-ttu-id="5a06c-144">设置 IsZoomControlEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="5a06c-144">Set the IsZoomControlEnabled property.</span></span>

<span data-ttu-id="5a06c-145">在 NavigationStarting 事件之后设置所做的更改将不会应用到下一个顶级导航。</span><span class="sxs-lookup"><span data-stu-id="5a06c-145">Setting changes made after NavigationStarting event will not apply until the next top level navigation.</span></span>

## <span data-ttu-id="5a06c-146">成员</span><span class="sxs-lookup"><span data-stu-id="5a06c-146">Members</span></span>

#### <span data-ttu-id="5a06c-147">get_AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="5a06c-147">get_AreDefaultContextMenusEnabled</span></span> 

<span data-ttu-id="5a06c-148">AreDefaultContextMenusEnabled 属性用于阻止在 web 视图中向用户显示默认上下文菜单。</span><span class="sxs-lookup"><span data-stu-id="5a06c-148">The AreDefaultContextMenusEnabled property is used to prevent default context menus from being shown to user in webview.</span></span>

> <span data-ttu-id="5a06c-149">公共 HRESULT [get_AreDefaultContextMenusEnabled](#get_aredefaultcontextmenusenabled)（已启用 BOOL \*）</span><span class="sxs-lookup"><span data-stu-id="5a06c-149">public HRESULT [get_AreDefaultContextMenusEnabled](#get_aredefaultcontextmenusenabled)(BOOL \* enabled)</span></span>

<span data-ttu-id="5a06c-150">默认值为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="5a06c-150">Defaults to TRUE.</span></span>

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

#### <span data-ttu-id="5a06c-151">get_AreDefaultScriptDialogsEnabled</span><span class="sxs-lookup"><span data-stu-id="5a06c-151">get_AreDefaultScriptDialogsEnabled</span></span> 

<span data-ttu-id="5a06c-152">加载新的 HTML 文档时，将使用 AreDefaultScriptDialogsEnabled。</span><span class="sxs-lookup"><span data-stu-id="5a06c-152">AreDefaultScriptDialogsEnabled is used when loading a new HTML document.</span></span>

> <span data-ttu-id="5a06c-153">public HRESULT [get_AreDefaultScriptDialogsEnabled](#get_aredefaultscriptdialogsenabled)（BOOL \* AreDefaultScriptDialogsEnabled）</span><span class="sxs-lookup"><span data-stu-id="5a06c-153">public HRESULT [get_AreDefaultScriptDialogsEnabled](#get_aredefaultscriptdialogsenabled)(BOOL \* areDefaultScriptDialogsEnabled)</span></span>

<span data-ttu-id="5a06c-154">如果设置为 false，则 Web 视图不会呈现默认的 javascript 对话框（具体由 javascript 警报、confirm、prompt 函数和 beforeunload 事件所显示的对话框）。</span><span class="sxs-lookup"><span data-stu-id="5a06c-154">If set to false, then WebView won't render the default javascript dialog box (Specifically those shown by the javascript alert, confirm, prompt functions and beforeunload event).</span></span> <span data-ttu-id="5a06c-155">相反，如果 SetScriptDialogOpeningEventHandler 设置了事件处理程序，则 Web 视图将发送一个包含对话框的所有信息的事件，并允许主机应用显示其自己的自定义 UI。</span><span class="sxs-lookup"><span data-stu-id="5a06c-155">Instead, if an event handler is set by SetScriptDialogOpeningEventHandler, WebView will send an event that will contain all of the information for the dialog and allow the host app to show its own custom UI.</span></span>

#### <span data-ttu-id="5a06c-156">get_AreDevToolsEnabled</span><span class="sxs-lookup"><span data-stu-id="5a06c-156">get_AreDevToolsEnabled</span></span> 

<span data-ttu-id="5a06c-157">AreDevToolsEnabled 控制用户是否可以使用上下文菜单或键盘快捷方式打开 DevTools 窗口。</span><span class="sxs-lookup"><span data-stu-id="5a06c-157">AreDevToolsEnabled controls whether the user is able to use the context menu or keyboard shortcuts to open the DevTools window.</span></span>

> <span data-ttu-id="5a06c-158">public HRESULT [get_AreDevToolsEnabled](#get_aredevtoolsenabled)（BOOL \* AreDevToolsEnabled）</span><span class="sxs-lookup"><span data-stu-id="5a06c-158">public HRESULT [get_AreDevToolsEnabled](#get_aredevtoolsenabled)(BOOL \* areDevToolsEnabled)</span></span>

<span data-ttu-id="5a06c-159">默认情况下为 true。</span><span class="sxs-lookup"><span data-stu-id="5a06c-159">It is true by default.</span></span>

#### <span data-ttu-id="5a06c-160">get_AreRemoteObjectsAllowed</span><span class="sxs-lookup"><span data-stu-id="5a06c-160">get_AreRemoteObjectsAllowed</span></span> 

<span data-ttu-id="5a06c-161">AreRemoteObjectsAllowed 属性用于控制是否可以从 web 视图中的页面访问主机对象。</span><span class="sxs-lookup"><span data-stu-id="5a06c-161">The AreRemoteObjectsAllowed property is used to control whether host objects are accessible from the page in webview.</span></span>

> <span data-ttu-id="5a06c-162">公共 HRESULT [get_AreRemoteObjectsAllowed](#get_areremoteobjectsallowed)（允许使用 BOOL \*）</span><span class="sxs-lookup"><span data-stu-id="5a06c-162">public HRESULT [get_AreRemoteObjectsAllowed](#get_areremoteobjectsallowed)(BOOL \* allowed)</span></span>

<span data-ttu-id="5a06c-163">默认值为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="5a06c-163">Defaults to TRUE.</span></span>

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

#### <span data-ttu-id="5a06c-164">get_IsBuiltInErrorPageEnabled</span><span class="sxs-lookup"><span data-stu-id="5a06c-164">get_IsBuiltInErrorPageEnabled</span></span> 

<span data-ttu-id="5a06c-165">IsBuiltInErrorPageEnabled 属性用于禁用内置错误页面，用于导航故障和呈现进程失败。</span><span class="sxs-lookup"><span data-stu-id="5a06c-165">The IsBuiltInErrorPageEnabled property is used to disable built in error page for navigation failure and render process failure.</span></span>

> <span data-ttu-id="5a06c-166">公共 HRESULT [get_IsBuiltInErrorPageEnabled](#get_isbuiltinerrorpageenabled)（已启用 BOOL \*）</span><span class="sxs-lookup"><span data-stu-id="5a06c-166">public HRESULT [get_IsBuiltInErrorPageEnabled](#get_isbuiltinerrorpageenabled)(BOOL \* enabled)</span></span>

<span data-ttu-id="5a06c-167">默认值为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="5a06c-167">Defaults to TRUE.</span></span> <span data-ttu-id="5a06c-168">如果禁用，将在发生相关错误时显示空白页。</span><span class="sxs-lookup"><span data-stu-id="5a06c-168">When disabled, blank page will be shown when related error happens.</span></span>

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

#### <span data-ttu-id="5a06c-169">get_IsScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="5a06c-169">get_IsScriptEnabled</span></span> 

<span data-ttu-id="5a06c-170">控制在 Web 视图中的所有未来导航中是否启用了 JavaScript 执行。</span><span class="sxs-lookup"><span data-stu-id="5a06c-170">Controls if JavaScript execution is enabled in all future navigations in the WebView.</span></span>

> <span data-ttu-id="5a06c-171">public HRESULT [get_IsScriptEnabled](#get_isscriptenabled)（BOOL \* IsScriptEnabled）</span><span class="sxs-lookup"><span data-stu-id="5a06c-171">public HRESULT [get_IsScriptEnabled](#get_isscriptenabled)(BOOL \* isScriptEnabled)</span></span>

<span data-ttu-id="5a06c-172">这仅影响文档中的脚本;即使脚本被禁用，用 ExecuteScript 插入的脚本也会运行。</span><span class="sxs-lookup"><span data-stu-id="5a06c-172">This only affects scripts in the document; scripts injected with ExecuteScript will run even if script is disabled.</span></span> <span data-ttu-id="5a06c-173">默认情况下为 true。</span><span class="sxs-lookup"><span data-stu-id="5a06c-173">It is true by default.</span></span>

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

#### <span data-ttu-id="5a06c-174">get_IsStatusBarEnabled</span><span class="sxs-lookup"><span data-stu-id="5a06c-174">get_IsStatusBarEnabled</span></span> 

<span data-ttu-id="5a06c-175">IsStatusBarEnabled 控制状态栏是否将显示。</span><span class="sxs-lookup"><span data-stu-id="5a06c-175">IsStatusBarEnabled controls whether the status bar will be displayed.</span></span>

> <span data-ttu-id="5a06c-176">public HRESULT [get_IsStatusBarEnabled](#get_isstatusbarenabled)（BOOL \* IsStatusBarEnabled）</span><span class="sxs-lookup"><span data-stu-id="5a06c-176">public HRESULT [get_IsStatusBarEnabled](#get_isstatusbarenabled)(BOOL \* isStatusBarEnabled)</span></span>

<span data-ttu-id="5a06c-177">状态栏通常显示在 Web 视图的左下方，并且在用户悬停在其上方和其他信息时显示链接的 URI 等内容。</span><span class="sxs-lookup"><span data-stu-id="5a06c-177">The status bar is usually displayed in the lower left of the WebView and shows things such as the URI of a link when the user hovers over it and other information.</span></span> <span data-ttu-id="5a06c-178">默认情况下为 true。</span><span class="sxs-lookup"><span data-stu-id="5a06c-178">It is true by default.</span></span>

#### <span data-ttu-id="5a06c-179">get_IsWebMessageEnabled</span><span class="sxs-lookup"><span data-stu-id="5a06c-179">get_IsWebMessageEnabled</span></span> 

<span data-ttu-id="5a06c-180">加载新的 HTML 文档时，将使用 IsWebMessageEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="5a06c-180">The IsWebMessageEnabled property is used when loading a new HTML document.</span></span>

> <span data-ttu-id="5a06c-181">public HRESULT [get_IsWebMessageEnabled](#get_iswebmessageenabled)（BOOL \* IsWebMessageEnabled）</span><span class="sxs-lookup"><span data-stu-id="5a06c-181">public HRESULT [get_IsWebMessageEnabled](#get_iswebmessageenabled)(BOOL \* isWebMessageEnabled)</span></span>

<span data-ttu-id="5a06c-182">如果设置为 true，则通过 PostWebMessageAsJson、PostWebMessageAsString 和，从主机到 web 视图的顶级 HTML 文档的通信是允许通过 web 视图、和 window。 chrome 的消息事件（有关详细信息，请参阅 PostWebMessageAsJson 文档）。</span><span class="sxs-lookup"><span data-stu-id="5a06c-182">If set to true, communication from the host to the webview's top level HTML document is allowed via PostWebMessageAsJson, PostWebMessageAsString, and window.chrome.webview's message event (see PostWebMessageAsJson documentation for details).</span></span> <span data-ttu-id="5a06c-183">通过 window 的 postMessage 函数和 SetWebMessageReceivedEventHandler 方法，允许从 web 视图的顶级 HTML 文档到主机的通信（有关详细信息，请参阅 SetWebMessageReceivedEventHandler 文档）。</span><span class="sxs-lookup"><span data-stu-id="5a06c-183">Communication from the webview's top level HTML document to the host is allowed via window.chrome.webview's postMessage function and the SetWebMessageReceivedEventHandler method (see the SetWebMessageReceivedEventHandler documentation for details).</span></span> <span data-ttu-id="5a06c-184">如果设置为 false，则不允许通信。</span><span class="sxs-lookup"><span data-stu-id="5a06c-184">If set to false, then communication is disallowed.</span></span> <span data-ttu-id="5a06c-185">PostWebMessageAsJson 和 PostWebMessageAsString 将失败 E_ACCESSDENIED，并且通过引发 Error 对象的实例，postMessage 将失败。</span><span class="sxs-lookup"><span data-stu-id="5a06c-185">PostWebMessageAsJson and PostWebMessageAsString will fail with E_ACCESSDENIED and window.chrome.webview.postMessage will fail by throwing an instance of an Error object.</span></span> <span data-ttu-id="5a06c-186">默认情况下为 true。</span><span class="sxs-lookup"><span data-stu-id="5a06c-186">It is true by default.</span></span>

```cpp
    ComPtr<ICoreWebView2Settings> settings;
    CHECK_FAILURE(m_webView->get_Settings(&settings));

    CHECK_FAILURE(settings->put_IsWebMessageEnabled(TRUE));
```

#### <span data-ttu-id="5a06c-187">get_IsZoomControlEnabled</span><span class="sxs-lookup"><span data-stu-id="5a06c-187">get_IsZoomControlEnabled</span></span> 

<span data-ttu-id="5a06c-188">IsZoomControlEnabled 属性用于阻止用户影响 Web 视图的缩放。</span><span class="sxs-lookup"><span data-stu-id="5a06c-188">The IsZoomControlEnabled property is used to prevent the user from impacting the zoom of the WebView.</span></span>

> <span data-ttu-id="5a06c-189">公共 HRESULT [get_IsZoomControlEnabled](#get_iszoomcontrolenabled)（已启用 BOOL \*）</span><span class="sxs-lookup"><span data-stu-id="5a06c-189">public HRESULT [get_IsZoomControlEnabled](#get_iszoomcontrolenabled)(BOOL \* enabled)</span></span>

<span data-ttu-id="5a06c-190">默认值为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="5a06c-190">Defaults to TRUE.</span></span> <span data-ttu-id="5a06c-191">当禁用时，用户将无法使用 ctrl +/-或 ctrl + 鼠标滚轮进行缩放，但缩放可通过 ZoomFactor API 设置。</span><span class="sxs-lookup"><span data-stu-id="5a06c-191">When disabled, user will not be able to zoom using ctrl+/- or ctrl+mouse wheel, but the zoom can be set via ZoomFactor API.</span></span>

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

#### <span data-ttu-id="5a06c-192">put_AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="5a06c-192">put_AreDefaultContextMenusEnabled</span></span> 

<span data-ttu-id="5a06c-193">设置 AreDefaultContextMenusEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="5a06c-193">Set the AreDefaultContextMenusEnabled property.</span></span>

> <span data-ttu-id="5a06c-194">public HRESULT [put_AreDefaultContextMenusEnabled](#put_aredefaultcontextmenusenabled)（已启用 BOOL）</span><span class="sxs-lookup"><span data-stu-id="5a06c-194">public HRESULT [put_AreDefaultContextMenusEnabled](#put_aredefaultcontextmenusenabled)(BOOL enabled)</span></span>

#### <span data-ttu-id="5a06c-195">put_AreDefaultScriptDialogsEnabled</span><span class="sxs-lookup"><span data-stu-id="5a06c-195">put_AreDefaultScriptDialogsEnabled</span></span> 

<span data-ttu-id="5a06c-196">设置 AreDefaultScriptDialogsEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="5a06c-196">Set the AreDefaultScriptDialogsEnabled property.</span></span>

> <span data-ttu-id="5a06c-197">公共 HRESULT [put_AreDefaultScriptDialogsEnabled](#put_aredefaultscriptdialogsenabled)（布尔值 AreDefaultScriptDialogsEnabled）</span><span class="sxs-lookup"><span data-stu-id="5a06c-197">public HRESULT [put_AreDefaultScriptDialogsEnabled](#put_aredefaultscriptdialogsenabled)(BOOL areDefaultScriptDialogsEnabled)</span></span>

#### <span data-ttu-id="5a06c-198">put_AreDevToolsEnabled</span><span class="sxs-lookup"><span data-stu-id="5a06c-198">put_AreDevToolsEnabled</span></span> 

<span data-ttu-id="5a06c-199">设置 AreDevToolsEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="5a06c-199">Set the AreDevToolsEnabled property.</span></span>

> <span data-ttu-id="5a06c-200">公共 HRESULT [put_AreDevToolsEnabled](#put_aredevtoolsenabled)（布尔值 AreDevToolsEnabled）</span><span class="sxs-lookup"><span data-stu-id="5a06c-200">public HRESULT [put_AreDevToolsEnabled](#put_aredevtoolsenabled)(BOOL areDevToolsEnabled)</span></span>

#### <span data-ttu-id="5a06c-201">put_AreRemoteObjectsAllowed</span><span class="sxs-lookup"><span data-stu-id="5a06c-201">put_AreRemoteObjectsAllowed</span></span> 

<span data-ttu-id="5a06c-202">设置 AreRemoteObjectsAllowed 属性。</span><span class="sxs-lookup"><span data-stu-id="5a06c-202">Set the AreRemoteObjectsAllowed property.</span></span>

> <span data-ttu-id="5a06c-203">公共 HRESULT [put_AreRemoteObjectsAllowed](#put_areremoteobjectsallowed)（允许使用 BOOL）</span><span class="sxs-lookup"><span data-stu-id="5a06c-203">public HRESULT [put_AreRemoteObjectsAllowed](#put_areremoteobjectsallowed)(BOOL allowed)</span></span>

#### <span data-ttu-id="5a06c-204">put_IsBuiltInErrorPageEnabled</span><span class="sxs-lookup"><span data-stu-id="5a06c-204">put_IsBuiltInErrorPageEnabled</span></span> 

<span data-ttu-id="5a06c-205">设置 IsBuiltInErrorPageEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="5a06c-205">Set the IsBuiltInErrorPageEnabled property.</span></span>

> <span data-ttu-id="5a06c-206">public HRESULT [put_IsBuiltInErrorPageEnabled](#put_isbuiltinerrorpageenabled)（已启用 BOOL）</span><span class="sxs-lookup"><span data-stu-id="5a06c-206">public HRESULT [put_IsBuiltInErrorPageEnabled](#put_isbuiltinerrorpageenabled)(BOOL enabled)</span></span>

#### <span data-ttu-id="5a06c-207">put_IsScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="5a06c-207">put_IsScriptEnabled</span></span> 

<span data-ttu-id="5a06c-208">设置 IsScriptEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="5a06c-208">Set the IsScriptEnabled property.</span></span>

> <span data-ttu-id="5a06c-209">公共 HRESULT [put_IsScriptEnabled](#put_isscriptenabled)（布尔值 IsScriptEnabled）</span><span class="sxs-lookup"><span data-stu-id="5a06c-209">public HRESULT [put_IsScriptEnabled](#put_isscriptenabled)(BOOL isScriptEnabled)</span></span>

#### <span data-ttu-id="5a06c-210">put_IsStatusBarEnabled</span><span class="sxs-lookup"><span data-stu-id="5a06c-210">put_IsStatusBarEnabled</span></span> 

<span data-ttu-id="5a06c-211">设置 IsStatusBarEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="5a06c-211">Set the IsStatusBarEnabled property.</span></span>

> <span data-ttu-id="5a06c-212">公共 HRESULT [put_IsStatusBarEnabled](#put_isstatusbarenabled)（布尔值 IsStatusBarEnabled）</span><span class="sxs-lookup"><span data-stu-id="5a06c-212">public HRESULT [put_IsStatusBarEnabled](#put_isstatusbarenabled)(BOOL isStatusBarEnabled)</span></span>

#### <span data-ttu-id="5a06c-213">put_IsWebMessageEnabled</span><span class="sxs-lookup"><span data-stu-id="5a06c-213">put_IsWebMessageEnabled</span></span> 

<span data-ttu-id="5a06c-214">设置 IsWebMessageEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="5a06c-214">Set the IsWebMessageEnabled property.</span></span>

> <span data-ttu-id="5a06c-215">公共 HRESULT [put_IsWebMessageEnabled](#put_iswebmessageenabled)（布尔值 IsWebMessageEnabled）</span><span class="sxs-lookup"><span data-stu-id="5a06c-215">public HRESULT [put_IsWebMessageEnabled](#put_iswebmessageenabled)(BOOL isWebMessageEnabled)</span></span>

#### <span data-ttu-id="5a06c-216">put_IsZoomControlEnabled</span><span class="sxs-lookup"><span data-stu-id="5a06c-216">put_IsZoomControlEnabled</span></span> 

<span data-ttu-id="5a06c-217">设置 IsZoomControlEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="5a06c-217">Set the IsZoomControlEnabled property.</span></span>

> <span data-ttu-id="5a06c-218">public HRESULT [put_IsZoomControlEnabled](#put_iszoomcontrolenabled)（已启用 BOOL）</span><span class="sxs-lookup"><span data-stu-id="5a06c-218">public HRESULT [put_IsZoomControlEnabled](#put_iszoomcontrolenabled)(BOOL enabled)</span></span>

