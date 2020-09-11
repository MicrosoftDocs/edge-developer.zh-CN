---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: WebView2 Win32 c + + ICoreWebView2Settings
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/09/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2Settings
ms.openlocfilehash: 1ad6754d2ff59a92e107c66644e389582ff6053b
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011737"
---
# <span data-ttu-id="d8006-104">interface ICoreWebView2Settings</span><span class="sxs-lookup"><span data-stu-id="d8006-104">interface ICoreWebView2Settings</span></span> 

```
interface ICoreWebView2Settings
  : public IUnknown
```

<span data-ttu-id="d8006-105">定义启用、禁用或修改 Web 视图功能的属性。</span><span class="sxs-lookup"><span data-stu-id="d8006-105">Defines properties that enable, disable, or modify WebView features.</span></span>

## <span data-ttu-id="d8006-106">摘要</span><span class="sxs-lookup"><span data-stu-id="d8006-106">Summary</span></span>

 <span data-ttu-id="d8006-107">成员</span><span class="sxs-lookup"><span data-stu-id="d8006-107">Members</span></span>                        | <span data-ttu-id="d8006-108">描述</span><span class="sxs-lookup"><span data-stu-id="d8006-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="d8006-109">get_AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="d8006-109">get_AreDefaultContextMenusEnabled</span></span>](#get_aredefaultcontextmenusenabled) | <span data-ttu-id="d8006-110">AreDefaultContextMenusEnabled 属性用于阻止在 Web 视图中向用户显示默认上下文菜单。</span><span class="sxs-lookup"><span data-stu-id="d8006-110">The AreDefaultContextMenusEnabled property is used to prevent default context menus from being shown to user in WebView.</span></span>
[<span data-ttu-id="d8006-111">get_AreDefaultScriptDialogsEnabled</span><span class="sxs-lookup"><span data-stu-id="d8006-111">get_AreDefaultScriptDialogsEnabled</span></span>](#get_aredefaultscriptdialogsenabled) | <span data-ttu-id="d8006-112">加载新的 HTML 文档时，将使用 AreDefaultScriptDialogsEnabled。</span><span class="sxs-lookup"><span data-stu-id="d8006-112">AreDefaultScriptDialogsEnabled is used when loading a new HTML document.</span></span>
[<span data-ttu-id="d8006-113">get_AreDevToolsEnabled</span><span class="sxs-lookup"><span data-stu-id="d8006-113">get_AreDevToolsEnabled</span></span>](#get_aredevtoolsenabled) | <span data-ttu-id="d8006-114">AreDevToolsEnabled 控制用户是否可以使用上下文菜单或键盘快捷方式打开 DevTools 窗口。</span><span class="sxs-lookup"><span data-stu-id="d8006-114">AreDevToolsEnabled controls whether the user is able to use the context menu or keyboard shortcuts to open the DevTools window.</span></span>
[<span data-ttu-id="d8006-115">get_AreHostObjectsAllowed</span><span class="sxs-lookup"><span data-stu-id="d8006-115">get_AreHostObjectsAllowed</span></span>](#get_arehostobjectsallowed) | <span data-ttu-id="d8006-116">AreHostObjectsAllowed 属性用于控制是否可以从 Web 视图中的页面访问主机对象。</span><span class="sxs-lookup"><span data-stu-id="d8006-116">The AreHostObjectsAllowed property is used to control whether host objects are accessible from the page in WebView.</span></span>
[<span data-ttu-id="d8006-117">get_IsBuiltInErrorPageEnabled</span><span class="sxs-lookup"><span data-stu-id="d8006-117">get_IsBuiltInErrorPageEnabled</span></span>](#get_isbuiltinerrorpageenabled) | <span data-ttu-id="d8006-118">IsBuiltInErrorPageEnabled 属性用于禁用内置错误页面，用于导航故障和呈现进程失败。</span><span class="sxs-lookup"><span data-stu-id="d8006-118">The IsBuiltInErrorPageEnabled property is used to disable built in error page for navigation failure and render process failure.</span></span>
[<span data-ttu-id="d8006-119">get_IsScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="d8006-119">get_IsScriptEnabled</span></span>](#get_isscriptenabled) | <span data-ttu-id="d8006-120">控制在 Web 视图中的所有未来导航中是否启用了 JavaScript 执行。</span><span class="sxs-lookup"><span data-stu-id="d8006-120">Controls if JavaScript execution is enabled in all future navigations in the WebView.</span></span>
[<span data-ttu-id="d8006-121">get_IsStatusBarEnabled</span><span class="sxs-lookup"><span data-stu-id="d8006-121">get_IsStatusBarEnabled</span></span>](#get_isstatusbarenabled) | <span data-ttu-id="d8006-122">IsStatusBarEnabled 控制状态栏是否将显示。</span><span class="sxs-lookup"><span data-stu-id="d8006-122">IsStatusBarEnabled controls whether the status bar will be displayed.</span></span>
[<span data-ttu-id="d8006-123">get_IsWebMessageEnabled</span><span class="sxs-lookup"><span data-stu-id="d8006-123">get_IsWebMessageEnabled</span></span>](#get_iswebmessageenabled) | <span data-ttu-id="d8006-124">加载新的 HTML 文档时，将使用 IsWebMessageEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="d8006-124">The IsWebMessageEnabled property is used when loading a new HTML document.</span></span>
[<span data-ttu-id="d8006-125">get_IsZoomControlEnabled</span><span class="sxs-lookup"><span data-stu-id="d8006-125">get_IsZoomControlEnabled</span></span>](#get_iszoomcontrolenabled) | <span data-ttu-id="d8006-126">IsZoomControlEnabled 属性用于阻止用户影响 Web 视图的缩放。</span><span class="sxs-lookup"><span data-stu-id="d8006-126">The IsZoomControlEnabled property is used to prevent the user from impacting the zoom of the WebView.</span></span>
[<span data-ttu-id="d8006-127">put_AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="d8006-127">put_AreDefaultContextMenusEnabled</span></span>](#put_aredefaultcontextmenusenabled) | <span data-ttu-id="d8006-128">设置 AreDefaultContextMenusEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="d8006-128">Set the AreDefaultContextMenusEnabled property.</span></span>
[<span data-ttu-id="d8006-129">put_AreDefaultScriptDialogsEnabled</span><span class="sxs-lookup"><span data-stu-id="d8006-129">put_AreDefaultScriptDialogsEnabled</span></span>](#put_aredefaultscriptdialogsenabled) | <span data-ttu-id="d8006-130">设置 AreDefaultScriptDialogsEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="d8006-130">Set the AreDefaultScriptDialogsEnabled property.</span></span>
[<span data-ttu-id="d8006-131">put_AreDevToolsEnabled</span><span class="sxs-lookup"><span data-stu-id="d8006-131">put_AreDevToolsEnabled</span></span>](#put_aredevtoolsenabled) | <span data-ttu-id="d8006-132">设置 AreDevToolsEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="d8006-132">Set the AreDevToolsEnabled property.</span></span>
[<span data-ttu-id="d8006-133">put_AreHostObjectsAllowed</span><span class="sxs-lookup"><span data-stu-id="d8006-133">put_AreHostObjectsAllowed</span></span>](#put_arehostobjectsallowed) | <span data-ttu-id="d8006-134">设置 AreHostObjectsAllowed 属性。</span><span class="sxs-lookup"><span data-stu-id="d8006-134">Set the AreHostObjectsAllowed property.</span></span>
[<span data-ttu-id="d8006-135">put_IsBuiltInErrorPageEnabled</span><span class="sxs-lookup"><span data-stu-id="d8006-135">put_IsBuiltInErrorPageEnabled</span></span>](#put_isbuiltinerrorpageenabled) | <span data-ttu-id="d8006-136">设置 IsBuiltInErrorPageEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="d8006-136">Set the IsBuiltInErrorPageEnabled property.</span></span>
[<span data-ttu-id="d8006-137">put_IsScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="d8006-137">put_IsScriptEnabled</span></span>](#put_isscriptenabled) | <span data-ttu-id="d8006-138">设置 IsScriptEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="d8006-138">Set the IsScriptEnabled property.</span></span>
[<span data-ttu-id="d8006-139">put_IsStatusBarEnabled</span><span class="sxs-lookup"><span data-stu-id="d8006-139">put_IsStatusBarEnabled</span></span>](#put_isstatusbarenabled) | <span data-ttu-id="d8006-140">设置 IsStatusBarEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="d8006-140">Set the IsStatusBarEnabled property.</span></span>
[<span data-ttu-id="d8006-141">put_IsWebMessageEnabled</span><span class="sxs-lookup"><span data-stu-id="d8006-141">put_IsWebMessageEnabled</span></span>](#put_iswebmessageenabled) | <span data-ttu-id="d8006-142">设置 IsWebMessageEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="d8006-142">Set the IsWebMessageEnabled property.</span></span>
[<span data-ttu-id="d8006-143">put_IsZoomControlEnabled</span><span class="sxs-lookup"><span data-stu-id="d8006-143">put_IsZoomControlEnabled</span></span>](#put_iszoomcontrolenabled) | <span data-ttu-id="d8006-144">设置 IsZoomControlEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="d8006-144">Set the IsZoomControlEnabled property.</span></span>

<span data-ttu-id="d8006-145">在 NavigationStarting 事件之后设置所做的更改将不会应用到下一个顶级导航。</span><span class="sxs-lookup"><span data-stu-id="d8006-145">Setting changes made after NavigationStarting event will not apply until the next top level navigation.</span></span>

## <span data-ttu-id="d8006-146">成员</span><span class="sxs-lookup"><span data-stu-id="d8006-146">Members</span></span>

#### <span data-ttu-id="d8006-147">get_AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="d8006-147">get_AreDefaultContextMenusEnabled</span></span> 

<span data-ttu-id="d8006-148">AreDefaultContextMenusEnabled 属性用于阻止在 Web 视图中向用户显示默认上下文菜单。</span><span class="sxs-lookup"><span data-stu-id="d8006-148">The AreDefaultContextMenusEnabled property is used to prevent default context menus from being shown to user in WebView.</span></span>

> <span data-ttu-id="d8006-149">公共 HRESULT [get_AreDefaultContextMenusEnabled](#get_aredefaultcontextmenusenabled) (BOOL \* 已启用) </span><span class="sxs-lookup"><span data-stu-id="d8006-149">public HRESULT [get_AreDefaultContextMenusEnabled](#get_aredefaultcontextmenusenabled)(BOOL \* enabled)</span></span>

<span data-ttu-id="d8006-150">默认情况下为 true。</span><span class="sxs-lookup"><span data-stu-id="d8006-150">It is true by default.</span></span>

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

#### <span data-ttu-id="d8006-151">get_AreDefaultScriptDialogsEnabled</span><span class="sxs-lookup"><span data-stu-id="d8006-151">get_AreDefaultScriptDialogsEnabled</span></span> 

<span data-ttu-id="d8006-152">加载新的 HTML 文档时，将使用 AreDefaultScriptDialogsEnabled。</span><span class="sxs-lookup"><span data-stu-id="d8006-152">AreDefaultScriptDialogsEnabled is used when loading a new HTML document.</span></span>

> <span data-ttu-id="d8006-153">公共 HRESULT [get_AreDefaultScriptDialogsEnabled](#get_aredefaultscriptdialogsenabled) (BOOL \* AreDefaultScriptDialogsEnabled) </span><span class="sxs-lookup"><span data-stu-id="d8006-153">public HRESULT [get_AreDefaultScriptDialogsEnabled](#get_aredefaultscriptdialogsenabled)(BOOL \* areDefaultScriptDialogsEnabled)</span></span>

<span data-ttu-id="d8006-154">如果设置为 false，则 Web 视图不会呈现默认的 JavaScript 对话框 (特定的 JavaScript 对话框，具体由 JavaScript 警报、确认、提示函数和 beforeunload 事件) 所示。</span><span class="sxs-lookup"><span data-stu-id="d8006-154">If set to false, then WebView won't render the default JavaScript dialog box (Specifically those shown by the JavaScript alert, confirm, prompt functions and beforeunload event).</span></span> <span data-ttu-id="d8006-155">相反，如果通过 add_ScriptDialogOpening 设置事件处理程序，则 Web 视图将发送一个包含对话框的所有信息的事件，并允许主机应用显示其自己的自定义 UI。</span><span class="sxs-lookup"><span data-stu-id="d8006-155">Instead, if an event handler is set via add_ScriptDialogOpening, WebView will send an event that will contain all of the information for the dialog and allow the host app to show its own custom UI.</span></span> <span data-ttu-id="d8006-156">默认情况下为 true。</span><span class="sxs-lookup"><span data-stu-id="d8006-156">It is true by default.</span></span>

#### <span data-ttu-id="d8006-157">get_AreDevToolsEnabled</span><span class="sxs-lookup"><span data-stu-id="d8006-157">get_AreDevToolsEnabled</span></span> 

<span data-ttu-id="d8006-158">AreDevToolsEnabled 控制用户是否可以使用上下文菜单或键盘快捷方式打开 DevTools 窗口。</span><span class="sxs-lookup"><span data-stu-id="d8006-158">AreDevToolsEnabled controls whether the user is able to use the context menu or keyboard shortcuts to open the DevTools window.</span></span>

> <span data-ttu-id="d8006-159">公共 HRESULT [get_AreDevToolsEnabled](#get_aredevtoolsenabled) (BOOL \* AreDevToolsEnabled) </span><span class="sxs-lookup"><span data-stu-id="d8006-159">public HRESULT [get_AreDevToolsEnabled](#get_aredevtoolsenabled)(BOOL \* areDevToolsEnabled)</span></span>

<span data-ttu-id="d8006-160">默认情况下为 true。</span><span class="sxs-lookup"><span data-stu-id="d8006-160">It is true by default.</span></span>

#### <span data-ttu-id="d8006-161">get_AreHostObjectsAllowed</span><span class="sxs-lookup"><span data-stu-id="d8006-161">get_AreHostObjectsAllowed</span></span> 

<span data-ttu-id="d8006-162">AreHostObjectsAllowed 属性用于控制是否可以从 Web 视图中的页面访问主机对象。</span><span class="sxs-lookup"><span data-stu-id="d8006-162">The AreHostObjectsAllowed property is used to control whether host objects are accessible from the page in WebView.</span></span>

> <span data-ttu-id="d8006-163">公共 HRESULT [get_AreHostObjectsAllowed](#get_arehostobjectsallowed) (BOOL \* 允许) </span><span class="sxs-lookup"><span data-stu-id="d8006-163">public HRESULT [get_AreHostObjectsAllowed](#get_arehostobjectsallowed)(BOOL \* allowed)</span></span>

<span data-ttu-id="d8006-164">默认情况下为 true。</span><span class="sxs-lookup"><span data-stu-id="d8006-164">It is true by default.</span></span>

```cpp
            BOOL allowHostObjects;
            CHECK_FAILURE(m_settings->get_AreHostObjectsAllowed(&allowHostObjects));
            if (allowHostObjects)
            {
                CHECK_FAILURE(m_settings->put_AreHostObjectsAllowed(FALSE));
                MessageBox(
                    nullptr, L"Access to host objects will be denied after the next navigation.",
                    L"Settings change", MB_OK);
            }
            else
            {
                CHECK_FAILURE(m_settings->put_AreHostObjectsAllowed(TRUE));
                MessageBox(
                    nullptr, L"Access to host objects will be allowed after the next navigation.",
                    L"Settings change", MB_OK);
            }
```

#### <span data-ttu-id="d8006-165">get_IsBuiltInErrorPageEnabled</span><span class="sxs-lookup"><span data-stu-id="d8006-165">get_IsBuiltInErrorPageEnabled</span></span> 

<span data-ttu-id="d8006-166">IsBuiltInErrorPageEnabled 属性用于禁用内置错误页面，用于导航故障和呈现进程失败。</span><span class="sxs-lookup"><span data-stu-id="d8006-166">The IsBuiltInErrorPageEnabled property is used to disable built in error page for navigation failure and render process failure.</span></span>

> <span data-ttu-id="d8006-167">公共 HRESULT [get_IsBuiltInErrorPageEnabled](#get_isbuiltinerrorpageenabled) (BOOL \* 已启用) </span><span class="sxs-lookup"><span data-stu-id="d8006-167">public HRESULT [get_IsBuiltInErrorPageEnabled](#get_isbuiltinerrorpageenabled)(BOOL \* enabled)</span></span>

<span data-ttu-id="d8006-168">默认情况下为 true。</span><span class="sxs-lookup"><span data-stu-id="d8006-168">It is true by default.</span></span> <span data-ttu-id="d8006-169">如果禁用，将在发生相关错误时显示空白页。</span><span class="sxs-lookup"><span data-stu-id="d8006-169">When disabled, blank page will be shown when related error happens.</span></span>

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

#### <span data-ttu-id="d8006-170">get_IsScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="d8006-170">get_IsScriptEnabled</span></span> 

<span data-ttu-id="d8006-171">控制在 Web 视图中的所有未来导航中是否启用了 JavaScript 执行。</span><span class="sxs-lookup"><span data-stu-id="d8006-171">Controls if JavaScript execution is enabled in all future navigations in the WebView.</span></span>

> <span data-ttu-id="d8006-172">公共 HRESULT [get_IsScriptEnabled](#get_isscriptenabled) (BOOL \* IsScriptEnabled) </span><span class="sxs-lookup"><span data-stu-id="d8006-172">public HRESULT [get_IsScriptEnabled](#get_isscriptenabled)(BOOL \* isScriptEnabled)</span></span>

<span data-ttu-id="d8006-173">这仅影响文档中的脚本;即使脚本被禁用，用 ExecuteScript 插入的脚本也会运行。</span><span class="sxs-lookup"><span data-stu-id="d8006-173">This only affects scripts in the document; scripts injected with ExecuteScript will run even if script is disabled.</span></span> <span data-ttu-id="d8006-174">默认情况下为 true。</span><span class="sxs-lookup"><span data-stu-id="d8006-174">It is true by default.</span></span>

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

#### <span data-ttu-id="d8006-175">get_IsStatusBarEnabled</span><span class="sxs-lookup"><span data-stu-id="d8006-175">get_IsStatusBarEnabled</span></span> 

<span data-ttu-id="d8006-176">IsStatusBarEnabled 控制状态栏是否将显示。</span><span class="sxs-lookup"><span data-stu-id="d8006-176">IsStatusBarEnabled controls whether the status bar will be displayed.</span></span>

> <span data-ttu-id="d8006-177">公共 HRESULT [get_IsStatusBarEnabled](#get_isstatusbarenabled) (BOOL \* IsStatusBarEnabled) </span><span class="sxs-lookup"><span data-stu-id="d8006-177">public HRESULT [get_IsStatusBarEnabled](#get_isstatusbarenabled)(BOOL \* isStatusBarEnabled)</span></span>

<span data-ttu-id="d8006-178">状态栏通常显示在 Web 视图的左下方，并且在用户悬停在其上方和其他信息时显示链接的 URI 等内容。</span><span class="sxs-lookup"><span data-stu-id="d8006-178">The status bar is usually displayed in the lower left of the WebView and shows things such as the URI of a link when the user hovers over it and other information.</span></span> <span data-ttu-id="d8006-179">默认情况下为 true。</span><span class="sxs-lookup"><span data-stu-id="d8006-179">It is true by default.</span></span>

#### <span data-ttu-id="d8006-180">get_IsWebMessageEnabled</span><span class="sxs-lookup"><span data-stu-id="d8006-180">get_IsWebMessageEnabled</span></span> 

<span data-ttu-id="d8006-181">加载新的 HTML 文档时，将使用 IsWebMessageEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="d8006-181">The IsWebMessageEnabled property is used when loading a new HTML document.</span></span>

> <span data-ttu-id="d8006-182">公共 HRESULT [get_IsWebMessageEnabled](#get_iswebmessageenabled) (BOOL \* IsWebMessageEnabled) </span><span class="sxs-lookup"><span data-stu-id="d8006-182">public HRESULT [get_IsWebMessageEnabled](#get_iswebmessageenabled)(BOOL \* isWebMessageEnabled)</span></span>

<span data-ttu-id="d8006-183">如果设置为 true，则通过 PostWebMessageAsJson、PostWebMessageAsString 和 window HTML 文档从主机到 Web 视图的顶级 HTML 文档的通信是允许的。 web 视图的消息事件 (有关详细信息) ，请参阅 PostWebMessageAsJson 文档。</span><span class="sxs-lookup"><span data-stu-id="d8006-183">If set to true, communication from the host to the WebView's top level HTML document is allowed via PostWebMessageAsJson, PostWebMessageAsString, and window.chrome.webview's message event (see PostWebMessageAsJson documentation for details).</span></span> <span data-ttu-id="d8006-184">通过 postMessage 函数和 add_WebMessageReceived 方法将从 Web 视图的顶级 HTML 文档到主机的通信被允许， (请参阅 add_WebMessageReceived 文档了解详细信息) 。</span><span class="sxs-lookup"><span data-stu-id="d8006-184">Communication from the WebView's top level HTML document to the host is allowed via window.chrome.webview's postMessage function and add_WebMessageReceived method (see add_WebMessageReceived documentation for details).</span></span> <span data-ttu-id="d8006-185">如果设置为 false，则不允许通信。</span><span class="sxs-lookup"><span data-stu-id="d8006-185">If set to false, then communication is disallowed.</span></span> <span data-ttu-id="d8006-186">PostWebMessageAsJson 和 PostWebMessageAsString 将失败 E_ACCESSDENIED，并且通过引发 Error 对象的实例，postMessage 将失败。</span><span class="sxs-lookup"><span data-stu-id="d8006-186">PostWebMessageAsJson and PostWebMessageAsString will fail with E_ACCESSDENIED and window.chrome.webview.postMessage will fail by throwing an instance of an Error object.</span></span> <span data-ttu-id="d8006-187">默认情况下为 true。</span><span class="sxs-lookup"><span data-stu-id="d8006-187">It is true by default.</span></span>

```cpp
    ComPtr<ICoreWebView2Settings> settings;
    CHECK_FAILURE(m_webView->get_Settings(&settings));

    CHECK_FAILURE(settings->put_IsWebMessageEnabled(TRUE));
```

#### <span data-ttu-id="d8006-188">get_IsZoomControlEnabled</span><span class="sxs-lookup"><span data-stu-id="d8006-188">get_IsZoomControlEnabled</span></span> 

<span data-ttu-id="d8006-189">IsZoomControlEnabled 属性用于阻止用户影响 Web 视图的缩放。</span><span class="sxs-lookup"><span data-stu-id="d8006-189">The IsZoomControlEnabled property is used to prevent the user from impacting the zoom of the WebView.</span></span>

> <span data-ttu-id="d8006-190">公共 HRESULT [get_IsZoomControlEnabled](#get_iszoomcontrolenabled) (BOOL \* 已启用) </span><span class="sxs-lookup"><span data-stu-id="d8006-190">public HRESULT [get_IsZoomControlEnabled](#get_iszoomcontrolenabled)(BOOL \* enabled)</span></span>

<span data-ttu-id="d8006-191">默认情况下为 true。</span><span class="sxs-lookup"><span data-stu-id="d8006-191">It is true by default.</span></span> <span data-ttu-id="d8006-192">当禁用时，用户将无法使用 ctrl +/-或 ctrl + 鼠标滚轮进行缩放，但缩放可通过 ZoomFactor API 设置。</span><span class="sxs-lookup"><span data-stu-id="d8006-192">When disabled, user will not be able to zoom using ctrl+/- or ctrl+mouse wheel, but the zoom can be set via ZoomFactor API.</span></span>

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

#### <span data-ttu-id="d8006-193">put_AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="d8006-193">put_AreDefaultContextMenusEnabled</span></span> 

<span data-ttu-id="d8006-194">设置 AreDefaultContextMenusEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="d8006-194">Set the AreDefaultContextMenusEnabled property.</span></span>

> <span data-ttu-id="d8006-195">已启用 (BOOL 的公共 HRESULT [put_AreDefaultContextMenusEnabled](#put_aredefaultcontextmenusenabled)) </span><span class="sxs-lookup"><span data-stu-id="d8006-195">public HRESULT [put_AreDefaultContextMenusEnabled](#put_aredefaultcontextmenusenabled)(BOOL enabled)</span></span>

#### <span data-ttu-id="d8006-196">put_AreDefaultScriptDialogsEnabled</span><span class="sxs-lookup"><span data-stu-id="d8006-196">put_AreDefaultScriptDialogsEnabled</span></span> 

<span data-ttu-id="d8006-197">设置 AreDefaultScriptDialogsEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="d8006-197">Set the AreDefaultScriptDialogsEnabled property.</span></span>

> <span data-ttu-id="d8006-198"> (BOOL areDefaultScriptDialogsEnabled 的公共 HRESULT [put_AreDefaultScriptDialogsEnabled](#put_aredefaultscriptdialogsenabled)) </span><span class="sxs-lookup"><span data-stu-id="d8006-198">public HRESULT [put_AreDefaultScriptDialogsEnabled](#put_aredefaultscriptdialogsenabled)(BOOL areDefaultScriptDialogsEnabled)</span></span>

#### <span data-ttu-id="d8006-199">put_AreDevToolsEnabled</span><span class="sxs-lookup"><span data-stu-id="d8006-199">put_AreDevToolsEnabled</span></span> 

<span data-ttu-id="d8006-200">设置 AreDevToolsEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="d8006-200">Set the AreDevToolsEnabled property.</span></span>

> <span data-ttu-id="d8006-201"> (BOOL areDevToolsEnabled 的公共 HRESULT [put_AreDevToolsEnabled](#put_aredevtoolsenabled)) </span><span class="sxs-lookup"><span data-stu-id="d8006-201">public HRESULT [put_AreDevToolsEnabled](#put_aredevtoolsenabled)(BOOL areDevToolsEnabled)</span></span>

#### <span data-ttu-id="d8006-202">put_AreHostObjectsAllowed</span><span class="sxs-lookup"><span data-stu-id="d8006-202">put_AreHostObjectsAllowed</span></span> 

<span data-ttu-id="d8006-203">设置 AreHostObjectsAllowed 属性。</span><span class="sxs-lookup"><span data-stu-id="d8006-203">Set the AreHostObjectsAllowed property.</span></span>

> <span data-ttu-id="d8006-204">public HRESULT [put_AreHostObjectsAllowed](#put_arehostobjectsallowed) (BOOL 允许) </span><span class="sxs-lookup"><span data-stu-id="d8006-204">public HRESULT [put_AreHostObjectsAllowed](#put_arehostobjectsallowed)(BOOL allowed)</span></span>

#### <span data-ttu-id="d8006-205">put_IsBuiltInErrorPageEnabled</span><span class="sxs-lookup"><span data-stu-id="d8006-205">put_IsBuiltInErrorPageEnabled</span></span> 

<span data-ttu-id="d8006-206">设置 IsBuiltInErrorPageEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="d8006-206">Set the IsBuiltInErrorPageEnabled property.</span></span>

> <span data-ttu-id="d8006-207">已启用 (BOOL 的公共 HRESULT [put_IsBuiltInErrorPageEnabled](#put_isbuiltinerrorpageenabled)) </span><span class="sxs-lookup"><span data-stu-id="d8006-207">public HRESULT [put_IsBuiltInErrorPageEnabled](#put_isbuiltinerrorpageenabled)(BOOL enabled)</span></span>

#### <span data-ttu-id="d8006-208">put_IsScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="d8006-208">put_IsScriptEnabled</span></span> 

<span data-ttu-id="d8006-209">设置 IsScriptEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="d8006-209">Set the IsScriptEnabled property.</span></span>

> <span data-ttu-id="d8006-210"> (BOOL isScriptEnabled 的公共 HRESULT [put_IsScriptEnabled](#put_isscriptenabled)) </span><span class="sxs-lookup"><span data-stu-id="d8006-210">public HRESULT [put_IsScriptEnabled](#put_isscriptenabled)(BOOL isScriptEnabled)</span></span>

#### <span data-ttu-id="d8006-211">put_IsStatusBarEnabled</span><span class="sxs-lookup"><span data-stu-id="d8006-211">put_IsStatusBarEnabled</span></span> 

<span data-ttu-id="d8006-212">设置 IsStatusBarEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="d8006-212">Set the IsStatusBarEnabled property.</span></span>

> <span data-ttu-id="d8006-213"> (BOOL isStatusBarEnabled 的公共 HRESULT [put_IsStatusBarEnabled](#put_isstatusbarenabled)) </span><span class="sxs-lookup"><span data-stu-id="d8006-213">public HRESULT [put_IsStatusBarEnabled](#put_isstatusbarenabled)(BOOL isStatusBarEnabled)</span></span>

#### <span data-ttu-id="d8006-214">put_IsWebMessageEnabled</span><span class="sxs-lookup"><span data-stu-id="d8006-214">put_IsWebMessageEnabled</span></span> 

<span data-ttu-id="d8006-215">设置 IsWebMessageEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="d8006-215">Set the IsWebMessageEnabled property.</span></span>

> <span data-ttu-id="d8006-216"> (BOOL isWebMessageEnabled 的公共 HRESULT [put_IsWebMessageEnabled](#put_iswebmessageenabled)) </span><span class="sxs-lookup"><span data-stu-id="d8006-216">public HRESULT [put_IsWebMessageEnabled](#put_iswebmessageenabled)(BOOL isWebMessageEnabled)</span></span>

#### <span data-ttu-id="d8006-217">put_IsZoomControlEnabled</span><span class="sxs-lookup"><span data-stu-id="d8006-217">put_IsZoomControlEnabled</span></span> 

<span data-ttu-id="d8006-218">设置 IsZoomControlEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="d8006-218">Set the IsZoomControlEnabled property.</span></span>

> <span data-ttu-id="d8006-219">已启用 (BOOL 的公共 HRESULT [put_IsZoomControlEnabled](#put_iszoomcontrolenabled)) </span><span class="sxs-lookup"><span data-stu-id="d8006-219">public HRESULT [put_IsZoomControlEnabled](#put_iszoomcontrolenabled)(BOOL enabled)</span></span>

