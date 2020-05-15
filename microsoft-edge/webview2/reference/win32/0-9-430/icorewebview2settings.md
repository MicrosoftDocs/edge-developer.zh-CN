---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/24/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 79f6e2712cab6d18025bd49ab0e7ceba01495d65
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10653190"
---
# <span data-ttu-id="94874-104">interface ICoreWebView2Settings</span><span class="sxs-lookup"><span data-stu-id="94874-104">interface ICoreWebView2Settings</span></span> 

> [!NOTE]
> <span data-ttu-id="94874-105">此接口可能会在 SDK 版本0.9.430 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="94874-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="94874-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="94874-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2Settings
  : public IUnknown
```

<span data-ttu-id="94874-107">定义启用、禁用或修改 Web 视图功能的属性。</span><span class="sxs-lookup"><span data-stu-id="94874-107">Defines properties that enable, disable, or modify WebView features.</span></span>

## <span data-ttu-id="94874-108">摘要</span><span class="sxs-lookup"><span data-stu-id="94874-108">Summary</span></span>

 <span data-ttu-id="94874-109">成员</span><span class="sxs-lookup"><span data-stu-id="94874-109">Members</span></span>                        | <span data-ttu-id="94874-110">描述</span><span class="sxs-lookup"><span data-stu-id="94874-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="94874-111">get_IsScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="94874-111">get_IsScriptEnabled</span></span>](#get_isscriptenabled) | <span data-ttu-id="94874-112">控制在 Web 视图中的所有未来导航中是否启用了 JavaScript 执行。</span><span class="sxs-lookup"><span data-stu-id="94874-112">Controls if JavaScript execution is enabled in all future navigations in the WebView.</span></span>
[<span data-ttu-id="94874-113">put_IsScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="94874-113">put_IsScriptEnabled</span></span>](#put_isscriptenabled) | <span data-ttu-id="94874-114">设置 IsScriptEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="94874-114">Set the IsScriptEnabled property.</span></span>
[<span data-ttu-id="94874-115">get_IsWebMessageEnabled</span><span class="sxs-lookup"><span data-stu-id="94874-115">get_IsWebMessageEnabled</span></span>](#get_iswebmessageenabled) | <span data-ttu-id="94874-116">加载新的 HTML 文档时，将使用 IsWebMessageEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="94874-116">The IsWebMessageEnabled property is used when loading a new HTML document.</span></span>
[<span data-ttu-id="94874-117">put_IsWebMessageEnabled</span><span class="sxs-lookup"><span data-stu-id="94874-117">put_IsWebMessageEnabled</span></span>](#put_iswebmessageenabled) | <span data-ttu-id="94874-118">设置 IsWebMessageEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="94874-118">Set the IsWebMessageEnabled property.</span></span>
[<span data-ttu-id="94874-119">get_AreDefaultScriptDialogsEnabled</span><span class="sxs-lookup"><span data-stu-id="94874-119">get_AreDefaultScriptDialogsEnabled</span></span>](#get_aredefaultscriptdialogsenabled) | <span data-ttu-id="94874-120">加载新的 HTML 文档时，将使用 AreDefaultScriptDialogsEnabled。</span><span class="sxs-lookup"><span data-stu-id="94874-120">AreDefaultScriptDialogsEnabled is used when loading a new HTML document.</span></span>
[<span data-ttu-id="94874-121">put_AreDefaultScriptDialogsEnabled</span><span class="sxs-lookup"><span data-stu-id="94874-121">put_AreDefaultScriptDialogsEnabled</span></span>](#put_aredefaultscriptdialogsenabled) | <span data-ttu-id="94874-122">设置 AreDefaultScriptDialogsEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="94874-122">Set the AreDefaultScriptDialogsEnabled property.</span></span>
[<span data-ttu-id="94874-123">get_IsStatusBarEnabled</span><span class="sxs-lookup"><span data-stu-id="94874-123">get_IsStatusBarEnabled</span></span>](#get_isstatusbarenabled) | <span data-ttu-id="94874-124">IsStatusBarEnabled 控制状态栏是否将显示。</span><span class="sxs-lookup"><span data-stu-id="94874-124">IsStatusBarEnabled controls whether the status bar will be displayed.</span></span>
[<span data-ttu-id="94874-125">put_IsStatusBarEnabled</span><span class="sxs-lookup"><span data-stu-id="94874-125">put_IsStatusBarEnabled</span></span>](#put_isstatusbarenabled) | <span data-ttu-id="94874-126">设置 IsStatusBarEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="94874-126">Set the IsStatusBarEnabled property.</span></span>
[<span data-ttu-id="94874-127">get_AreDevToolsEnabled</span><span class="sxs-lookup"><span data-stu-id="94874-127">get_AreDevToolsEnabled</span></span>](#get_aredevtoolsenabled) | <span data-ttu-id="94874-128">AreDevToolsEnabled 控制用户是否可以使用上下文菜单或键盘快捷方式打开 DevTools 窗口。</span><span class="sxs-lookup"><span data-stu-id="94874-128">AreDevToolsEnabled controls whether the user is able to use the context menu or keyboard shortcuts to open the DevTools window.</span></span>
[<span data-ttu-id="94874-129">put_AreDevToolsEnabled</span><span class="sxs-lookup"><span data-stu-id="94874-129">put_AreDevToolsEnabled</span></span>](#put_aredevtoolsenabled) | <span data-ttu-id="94874-130">设置 AreDevToolsEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="94874-130">Set the AreDevToolsEnabled property.</span></span>
[<span data-ttu-id="94874-131">get_AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="94874-131">get_AreDefaultContextMenusEnabled</span></span>](#get_aredefaultcontextmenusenabled) | <span data-ttu-id="94874-132">AreDefaultContextMenusEnabled 属性用于阻止在 web 视图中向用户显示默认上下文菜单。</span><span class="sxs-lookup"><span data-stu-id="94874-132">The AreDefaultContextMenusEnabled property is used to prevent default context menus from being shown to user in webview.</span></span>
[<span data-ttu-id="94874-133">put_AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="94874-133">put_AreDefaultContextMenusEnabled</span></span>](#put_aredefaultcontextmenusenabled) | <span data-ttu-id="94874-134">设置 AreDefaultContextMenusEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="94874-134">Set the AreDefaultContextMenusEnabled property.</span></span>
[<span data-ttu-id="94874-135">get_AreRemoteObjectsAllowed</span><span class="sxs-lookup"><span data-stu-id="94874-135">get_AreRemoteObjectsAllowed</span></span>](#get_areremoteobjectsallowed) | <span data-ttu-id="94874-136">AreRemoteObjectsAllowed 属性用于控制是否可以从 web 视图中的页面访问远程对象。</span><span class="sxs-lookup"><span data-stu-id="94874-136">The AreRemoteObjectsAllowed property is used to control whether remote objects are accessible from the page in webview.</span></span>
[<span data-ttu-id="94874-137">put_AreRemoteObjectsAllowed</span><span class="sxs-lookup"><span data-stu-id="94874-137">put_AreRemoteObjectsAllowed</span></span>](#put_areremoteobjectsallowed) | <span data-ttu-id="94874-138">设置 AreRemoteObjectsAllowed 属性。</span><span class="sxs-lookup"><span data-stu-id="94874-138">Set the AreRemoteObjectsAllowed property.</span></span>
[<span data-ttu-id="94874-139">get_IsZoomControlEnabled</span><span class="sxs-lookup"><span data-stu-id="94874-139">get_IsZoomControlEnabled</span></span>](#get_iszoomcontrolenabled) | <span data-ttu-id="94874-140">IsZoomControlEnabled 属性用于阻止用户影响 Web 视图的缩放。</span><span class="sxs-lookup"><span data-stu-id="94874-140">The IsZoomControlEnabled property is used to prevent the user from impacting the zoom of the WebView.</span></span>
[<span data-ttu-id="94874-141">put_IsZoomControlEnabled</span><span class="sxs-lookup"><span data-stu-id="94874-141">put_IsZoomControlEnabled</span></span>](#put_iszoomcontrolenabled) | <span data-ttu-id="94874-142">设置 IsZoomControlEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="94874-142">Set the IsZoomControlEnabled property.</span></span>

<span data-ttu-id="94874-143">在 NavigationStarting 事件之后设置所做的更改将不会应用到下一个顶级导航。</span><span class="sxs-lookup"><span data-stu-id="94874-143">Setting changes made after NavigationStarting event will not apply until the next top level navigation.</span></span>

## <span data-ttu-id="94874-144">成员</span><span class="sxs-lookup"><span data-stu-id="94874-144">Members</span></span>

#### <span data-ttu-id="94874-145">get_IsScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="94874-145">get_IsScriptEnabled</span></span> 

<span data-ttu-id="94874-146">控制在 Web 视图中的所有未来导航中是否启用了 JavaScript 执行。</span><span class="sxs-lookup"><span data-stu-id="94874-146">Controls if JavaScript execution is enabled in all future navigations in the WebView.</span></span>

> <span data-ttu-id="94874-147">public HRESULT [get_IsScriptEnabled](#get_isscriptenabled)（BOOL \* IsScriptEnabled）</span><span class="sxs-lookup"><span data-stu-id="94874-147">public HRESULT [get_IsScriptEnabled](#get_isscriptenabled)(BOOL \* isScriptEnabled)</span></span>

<span data-ttu-id="94874-148">这仅影响文档中的脚本;即使脚本被禁用，用 ExecuteScript 插入的脚本也会运行。</span><span class="sxs-lookup"><span data-stu-id="94874-148">This only affects scripts in the document; scripts injected with ExecuteScript will run even if script is disabled.</span></span> <span data-ttu-id="94874-149">默认情况下为 true。</span><span class="sxs-lookup"><span data-stu-id="94874-149">It is true by default.</span></span>

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

#### <span data-ttu-id="94874-150">put_IsScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="94874-150">put_IsScriptEnabled</span></span> 

<span data-ttu-id="94874-151">设置 IsScriptEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="94874-151">Set the IsScriptEnabled property.</span></span>

> <span data-ttu-id="94874-152">公共 HRESULT [put_IsScriptEnabled](#put_isscriptenabled)（布尔值 IsScriptEnabled）</span><span class="sxs-lookup"><span data-stu-id="94874-152">public HRESULT [put_IsScriptEnabled](#put_isscriptenabled)(BOOL isScriptEnabled)</span></span>

#### <span data-ttu-id="94874-153">get_IsWebMessageEnabled</span><span class="sxs-lookup"><span data-stu-id="94874-153">get_IsWebMessageEnabled</span></span> 

<span data-ttu-id="94874-154">加载新的 HTML 文档时，将使用 IsWebMessageEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="94874-154">The IsWebMessageEnabled property is used when loading a new HTML document.</span></span>

> <span data-ttu-id="94874-155">public HRESULT [get_IsWebMessageEnabled](#get_iswebmessageenabled)（BOOL \* IsWebMessageEnabled）</span><span class="sxs-lookup"><span data-stu-id="94874-155">public HRESULT [get_IsWebMessageEnabled](#get_iswebmessageenabled)(BOOL \* isWebMessageEnabled)</span></span>

<span data-ttu-id="94874-156">如果设置为 true，则通过 PostWebMessageAsJson、PostWebMessageAsString 和，从主机到 web 视图的顶级 HTML 文档的通信是允许通过 web 视图、和 window。 chrome 的消息事件（有关详细信息，请参阅 PostWebMessageAsJson 文档）。</span><span class="sxs-lookup"><span data-stu-id="94874-156">If set to true, communication from the host to the webview's top level HTML document is allowed via PostWebMessageAsJson, PostWebMessageAsString, and window.chrome.webview's message event (see PostWebMessageAsJson documentation for details).</span></span> <span data-ttu-id="94874-157">通过 window 的 postMessage 函数和 SetWebMessageReceivedEventHandler 方法，允许从 web 视图的顶级 HTML 文档到主机的通信（有关详细信息，请参阅 SetWebMessageReceivedEventHandler 文档）。</span><span class="sxs-lookup"><span data-stu-id="94874-157">Communication from the webview's top level HTML document to the host is allowed via window.chrome.webview's postMessage function and the SetWebMessageReceivedEventHandler method (see the SetWebMessageReceivedEventHandler documentation for details).</span></span> <span data-ttu-id="94874-158">如果设置为 false，则不允许通信。</span><span class="sxs-lookup"><span data-stu-id="94874-158">If set to false, then communication is disallowed.</span></span> <span data-ttu-id="94874-159">PostWebMessageAsJson 和 PostWebMessageAsString 将失败 E_ACCESSDENIED，并且通过引发 Error 对象的实例，postMessage 将失败。</span><span class="sxs-lookup"><span data-stu-id="94874-159">PostWebMessageAsJson and PostWebMessageAsString will fail with E_ACCESSDENIED and window.chrome.webview.postMessage will fail by throwing an instance of an Error object.</span></span> <span data-ttu-id="94874-160">默认情况下为 true。</span><span class="sxs-lookup"><span data-stu-id="94874-160">It is true by default.</span></span>

```cpp
    ComPtr<ICoreWebView2Settings> settings;
    CHECK_FAILURE(m_webView->get_Settings(&settings));

    CHECK_FAILURE(settings->put_IsWebMessageEnabled(TRUE));
```

#### <span data-ttu-id="94874-161">put_IsWebMessageEnabled</span><span class="sxs-lookup"><span data-stu-id="94874-161">put_IsWebMessageEnabled</span></span> 

<span data-ttu-id="94874-162">设置 IsWebMessageEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="94874-162">Set the IsWebMessageEnabled property.</span></span>

> <span data-ttu-id="94874-163">公共 HRESULT [put_IsWebMessageEnabled](#put_iswebmessageenabled)（布尔值 IsWebMessageEnabled）</span><span class="sxs-lookup"><span data-stu-id="94874-163">public HRESULT [put_IsWebMessageEnabled](#put_iswebmessageenabled)(BOOL isWebMessageEnabled)</span></span>

#### <span data-ttu-id="94874-164">get_AreDefaultScriptDialogsEnabled</span><span class="sxs-lookup"><span data-stu-id="94874-164">get_AreDefaultScriptDialogsEnabled</span></span> 

<span data-ttu-id="94874-165">加载新的 HTML 文档时，将使用 AreDefaultScriptDialogsEnabled。</span><span class="sxs-lookup"><span data-stu-id="94874-165">AreDefaultScriptDialogsEnabled is used when loading a new HTML document.</span></span>

> <span data-ttu-id="94874-166">public HRESULT [get_AreDefaultScriptDialogsEnabled](#get_aredefaultscriptdialogsenabled)（BOOL \* AreDefaultScriptDialogsEnabled）</span><span class="sxs-lookup"><span data-stu-id="94874-166">public HRESULT [get_AreDefaultScriptDialogsEnabled](#get_aredefaultscriptdialogsenabled)(BOOL \* areDefaultScriptDialogsEnabled)</span></span>

<span data-ttu-id="94874-167">如果设置为 false，则 Web 视图不会呈现默认的 javascript 对话框（具体由 javascript 警报、confirm、prompt 函数和 beforeunload 事件所显示的对话框）。</span><span class="sxs-lookup"><span data-stu-id="94874-167">If set to false, then WebView won't render the default javascript dialog box (Specifically those shown by the javascript alert, confirm, prompt functions and beforeunload event).</span></span> <span data-ttu-id="94874-168">相反，如果 SetScriptDialogOpeningEventHandler 设置了事件处理程序，则 Web 视图将发送一个包含对话框的所有信息的事件，并允许主机应用显示其自己的自定义 UI。</span><span class="sxs-lookup"><span data-stu-id="94874-168">Instead, if an event handler is set by SetScriptDialogOpeningEventHandler, WebView will send an event that will contain all of the information for the dialog and allow the host app to show its own custom UI.</span></span>

#### <span data-ttu-id="94874-169">put_AreDefaultScriptDialogsEnabled</span><span class="sxs-lookup"><span data-stu-id="94874-169">put_AreDefaultScriptDialogsEnabled</span></span> 

<span data-ttu-id="94874-170">设置 AreDefaultScriptDialogsEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="94874-170">Set the AreDefaultScriptDialogsEnabled property.</span></span>

> <span data-ttu-id="94874-171">公共 HRESULT [put_AreDefaultScriptDialogsEnabled](#put_aredefaultscriptdialogsenabled)（布尔值 AreDefaultScriptDialogsEnabled）</span><span class="sxs-lookup"><span data-stu-id="94874-171">public HRESULT [put_AreDefaultScriptDialogsEnabled](#put_aredefaultscriptdialogsenabled)(BOOL areDefaultScriptDialogsEnabled)</span></span>

#### <span data-ttu-id="94874-172">get_IsStatusBarEnabled</span><span class="sxs-lookup"><span data-stu-id="94874-172">get_IsStatusBarEnabled</span></span> 

<span data-ttu-id="94874-173">IsStatusBarEnabled 控制状态栏是否将显示。</span><span class="sxs-lookup"><span data-stu-id="94874-173">IsStatusBarEnabled controls whether the status bar will be displayed.</span></span>

> <span data-ttu-id="94874-174">public HRESULT [get_IsStatusBarEnabled](#get_isstatusbarenabled)（BOOL \* IsStatusBarEnabled）</span><span class="sxs-lookup"><span data-stu-id="94874-174">public HRESULT [get_IsStatusBarEnabled](#get_isstatusbarenabled)(BOOL \* isStatusBarEnabled)</span></span>

<span data-ttu-id="94874-175">状态栏通常显示在 Web 视图的左下方，并且在用户悬停在其上方和其他信息时显示链接的 URI 等内容。</span><span class="sxs-lookup"><span data-stu-id="94874-175">The status bar is usually displayed in the lower left of the WebView and shows things such as the URI of a link when the user hovers over it and other information.</span></span> <span data-ttu-id="94874-176">默认情况下为 true。</span><span class="sxs-lookup"><span data-stu-id="94874-176">It is true by default.</span></span>

#### <span data-ttu-id="94874-177">put_IsStatusBarEnabled</span><span class="sxs-lookup"><span data-stu-id="94874-177">put_IsStatusBarEnabled</span></span> 

<span data-ttu-id="94874-178">设置 IsStatusBarEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="94874-178">Set the IsStatusBarEnabled property.</span></span>

> <span data-ttu-id="94874-179">公共 HRESULT [put_IsStatusBarEnabled](#put_isstatusbarenabled)（布尔值 IsStatusBarEnabled）</span><span class="sxs-lookup"><span data-stu-id="94874-179">public HRESULT [put_IsStatusBarEnabled](#put_isstatusbarenabled)(BOOL isStatusBarEnabled)</span></span>

#### <span data-ttu-id="94874-180">get_AreDevToolsEnabled</span><span class="sxs-lookup"><span data-stu-id="94874-180">get_AreDevToolsEnabled</span></span> 

<span data-ttu-id="94874-181">AreDevToolsEnabled 控制用户是否可以使用上下文菜单或键盘快捷方式打开 DevTools 窗口。</span><span class="sxs-lookup"><span data-stu-id="94874-181">AreDevToolsEnabled controls whether the user is able to use the context menu or keyboard shortcuts to open the DevTools window.</span></span>

> <span data-ttu-id="94874-182">public HRESULT [get_AreDevToolsEnabled](#get_aredevtoolsenabled)（BOOL \* AreDevToolsEnabled）</span><span class="sxs-lookup"><span data-stu-id="94874-182">public HRESULT [get_AreDevToolsEnabled](#get_aredevtoolsenabled)(BOOL \* areDevToolsEnabled)</span></span>

<span data-ttu-id="94874-183">默认情况下为 true。</span><span class="sxs-lookup"><span data-stu-id="94874-183">It is true by default.</span></span>

#### <span data-ttu-id="94874-184">put_AreDevToolsEnabled</span><span class="sxs-lookup"><span data-stu-id="94874-184">put_AreDevToolsEnabled</span></span> 

<span data-ttu-id="94874-185">设置 AreDevToolsEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="94874-185">Set the AreDevToolsEnabled property.</span></span>

> <span data-ttu-id="94874-186">公共 HRESULT [put_AreDevToolsEnabled](#put_aredevtoolsenabled)（布尔值 AreDevToolsEnabled）</span><span class="sxs-lookup"><span data-stu-id="94874-186">public HRESULT [put_AreDevToolsEnabled](#put_aredevtoolsenabled)(BOOL areDevToolsEnabled)</span></span>

#### <span data-ttu-id="94874-187">get_AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="94874-187">get_AreDefaultContextMenusEnabled</span></span> 

<span data-ttu-id="94874-188">AreDefaultContextMenusEnabled 属性用于阻止在 web 视图中向用户显示默认上下文菜单。</span><span class="sxs-lookup"><span data-stu-id="94874-188">The AreDefaultContextMenusEnabled property is used to prevent default context menus from being shown to user in webview.</span></span>

> <span data-ttu-id="94874-189">公共 HRESULT [get_AreDefaultContextMenusEnabled](#get_aredefaultcontextmenusenabled)（已启用 BOOL \*）</span><span class="sxs-lookup"><span data-stu-id="94874-189">public HRESULT [get_AreDefaultContextMenusEnabled](#get_aredefaultcontextmenusenabled)(BOOL \* enabled)</span></span>

<span data-ttu-id="94874-190">默认值为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="94874-190">Defaults to TRUE.</span></span>

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

#### <span data-ttu-id="94874-191">put_AreDefaultContextMenusEnabled</span><span class="sxs-lookup"><span data-stu-id="94874-191">put_AreDefaultContextMenusEnabled</span></span> 

<span data-ttu-id="94874-192">设置 AreDefaultContextMenusEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="94874-192">Set the AreDefaultContextMenusEnabled property.</span></span>

> <span data-ttu-id="94874-193">public HRESULT [put_AreDefaultContextMenusEnabled](#put_aredefaultcontextmenusenabled)（已启用 BOOL）</span><span class="sxs-lookup"><span data-stu-id="94874-193">public HRESULT [put_AreDefaultContextMenusEnabled](#put_aredefaultcontextmenusenabled)(BOOL enabled)</span></span>

#### <span data-ttu-id="94874-194">get_AreRemoteObjectsAllowed</span><span class="sxs-lookup"><span data-stu-id="94874-194">get_AreRemoteObjectsAllowed</span></span> 

<span data-ttu-id="94874-195">AreRemoteObjectsAllowed 属性用于控制是否可以从 web 视图中的页面访问远程对象。</span><span class="sxs-lookup"><span data-stu-id="94874-195">The AreRemoteObjectsAllowed property is used to control whether remote objects are accessible from the page in webview.</span></span>

> <span data-ttu-id="94874-196">公共 HRESULT [get_AreRemoteObjectsAllowed](#get_areremoteobjectsallowed)（允许使用 BOOL \*）</span><span class="sxs-lookup"><span data-stu-id="94874-196">public HRESULT [get_AreRemoteObjectsAllowed](#get_areremoteobjectsallowed)(BOOL \* allowed)</span></span>

<span data-ttu-id="94874-197">默认值为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="94874-197">Defaults to TRUE.</span></span>

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

#### <span data-ttu-id="94874-198">put_AreRemoteObjectsAllowed</span><span class="sxs-lookup"><span data-stu-id="94874-198">put_AreRemoteObjectsAllowed</span></span> 

<span data-ttu-id="94874-199">设置 AreRemoteObjectsAllowed 属性。</span><span class="sxs-lookup"><span data-stu-id="94874-199">Set the AreRemoteObjectsAllowed property.</span></span>

> <span data-ttu-id="94874-200">公共 HRESULT [put_AreRemoteObjectsAllowed](#put_areremoteobjectsallowed)（允许使用 BOOL）</span><span class="sxs-lookup"><span data-stu-id="94874-200">public HRESULT [put_AreRemoteObjectsAllowed](#put_areremoteobjectsallowed)(BOOL allowed)</span></span>

#### <span data-ttu-id="94874-201">get_IsZoomControlEnabled</span><span class="sxs-lookup"><span data-stu-id="94874-201">get_IsZoomControlEnabled</span></span> 

<span data-ttu-id="94874-202">IsZoomControlEnabled 属性用于阻止用户影响 Web 视图的缩放。</span><span class="sxs-lookup"><span data-stu-id="94874-202">The IsZoomControlEnabled property is used to prevent the user from impacting the zoom of the WebView.</span></span>

> <span data-ttu-id="94874-203">公共 HRESULT [get_IsZoomControlEnabled](#get_iszoomcontrolenabled)（已启用 BOOL \*）</span><span class="sxs-lookup"><span data-stu-id="94874-203">public HRESULT [get_IsZoomControlEnabled](#get_iszoomcontrolenabled)(BOOL \* enabled)</span></span>

<span data-ttu-id="94874-204">默认值为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="94874-204">Defaults to TRUE.</span></span> <span data-ttu-id="94874-205">当禁用时，用户将无法使用 ctrl +/-或 ctrl + 鼠标滚轮进行缩放，但可以通过 put_ZoomFactor API 设置缩放。</span><span class="sxs-lookup"><span data-stu-id="94874-205">When disabled, user will not be able to zoom using ctrl+/- or ctrl+mouse wheel, but the zoom can be set via put_ZoomFactor API.</span></span>

```cpp
            BOOL zoomControlEnabled;
            CHECK_FAILURE(m_settings->get_IsZoomControlEnabled(&zoomControlEnabled));
            if (zoomControlEnabled)
            {
                CHECK_FAILURE(m_settings->put_IsZoomControlEnabled(FALSE));
                MessageBox(
                    nullptr, L"Zoom control is disabled after the next navigation.", L"Settings change",
                    MB_OK);
            }
            else
            {
                CHECK_FAILURE(m_settings->put_IsZoomControlEnabled(TRUE));
                MessageBox(
                    nullptr, L"Zoom control is enabled after the next navigation.", L"Settings change",
                    MB_OK);
            }
```

#### <span data-ttu-id="94874-206">put_IsZoomControlEnabled</span><span class="sxs-lookup"><span data-stu-id="94874-206">put_IsZoomControlEnabled</span></span> 

<span data-ttu-id="94874-207">设置 IsZoomControlEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="94874-207">Set the IsZoomControlEnabled property.</span></span>

> <span data-ttu-id="94874-208">public HRESULT [put_IsZoomControlEnabled](#put_iszoomcontrolenabled)（已启用 BOOL）</span><span class="sxs-lookup"><span data-stu-id="94874-208">public HRESULT [put_IsZoomControlEnabled](#put_iszoomcontrolenabled)(BOOL enabled)</span></span>
