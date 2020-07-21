---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2Settings
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: 649506b28e0ecdbff33b44bbd8010ddb3d2a66b0
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885798"
---
# <span data-ttu-id="c363e-104">0.8.355-接口 IWebView2Settings</span><span class="sxs-lookup"><span data-stu-id="c363e-104">0.8.355 - interface IWebView2Settings</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2Settings
  : public IUnknown
```

<span data-ttu-id="c363e-105">定义启用、禁用或修改 Web 视图功能的属性。</span><span class="sxs-lookup"><span data-stu-id="c363e-105">Defines properties that enable, disable, or modify WebView features.</span></span>

## <span data-ttu-id="c363e-106">摘要</span><span class="sxs-lookup"><span data-stu-id="c363e-106">Summary</span></span>

 <span data-ttu-id="c363e-107">成员</span><span class="sxs-lookup"><span data-stu-id="c363e-107">Members</span></span>                        | <span data-ttu-id="c363e-108">描述</span><span class="sxs-lookup"><span data-stu-id="c363e-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="c363e-109">get_IsScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="c363e-109">get_IsScriptEnabled</span></span>](#get_isscriptenabled) | <span data-ttu-id="c363e-110">控制在 Web 视图中的所有未来导航中是否启用了 JavaScript 执行。</span><span class="sxs-lookup"><span data-stu-id="c363e-110">Controls if JavaScript execution is enabled in all future navigations in the WebView.</span></span>
[<span data-ttu-id="c363e-111">put_IsScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="c363e-111">put_IsScriptEnabled</span></span>](#put_isscriptenabled) | <span data-ttu-id="c363e-112">设置 IsScriptEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="c363e-112">Set the IsScriptEnabled property.</span></span>
[<span data-ttu-id="c363e-113">get_IsWebMessageEnabled</span><span class="sxs-lookup"><span data-stu-id="c363e-113">get_IsWebMessageEnabled</span></span>](#get_iswebmessageenabled) | <span data-ttu-id="c363e-114">加载新的 HTML 文档时，将使用 IsWebMessageEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="c363e-114">The IsWebMessageEnabled property is used when loading a new HTML document.</span></span>
[<span data-ttu-id="c363e-115">put_IsWebMessageEnabled</span><span class="sxs-lookup"><span data-stu-id="c363e-115">put_IsWebMessageEnabled</span></span>](#put_iswebmessageenabled) | <span data-ttu-id="c363e-116">设置 IsWebMessageEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="c363e-116">Set the IsWebMessageEnabled property.</span></span>
[<span data-ttu-id="c363e-117">get_AreDefaultScriptDialogsEnabled</span><span class="sxs-lookup"><span data-stu-id="c363e-117">get_AreDefaultScriptDialogsEnabled</span></span>](#get_aredefaultscriptdialogsenabled) | <span data-ttu-id="c363e-118">加载新的 HTML 文档时，将使用 AreDefaultScriptDialogsEnabled。</span><span class="sxs-lookup"><span data-stu-id="c363e-118">AreDefaultScriptDialogsEnabled is used when loading a new HTML document.</span></span>
[<span data-ttu-id="c363e-119">put_AreDefaultScriptDialogsEnabled</span><span class="sxs-lookup"><span data-stu-id="c363e-119">put_AreDefaultScriptDialogsEnabled</span></span>](#put_aredefaultscriptdialogsenabled) | <span data-ttu-id="c363e-120">设置 AreDefaultScriptDialogsEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="c363e-120">Set the AreDefaultScriptDialogsEnabled property.</span></span>
[<span data-ttu-id="c363e-121">get_IsFullscreenAllowed_deprecated</span><span class="sxs-lookup"><span data-stu-id="c363e-121">get_IsFullscreenAllowed_deprecated</span></span>](#get_isfullscreenallowed_deprecated) | <span data-ttu-id="c363e-122">此设置已弃用，并且将始终返回 false。</span><span class="sxs-lookup"><span data-stu-id="c363e-122">This setting is deprecated and will always return false.</span></span>
[<span data-ttu-id="c363e-123">put_IsFullscreenAllowed_deprecated</span><span class="sxs-lookup"><span data-stu-id="c363e-123">put_IsFullscreenAllowed_deprecated</span></span>](#put_isfullscreenallowed_deprecated) | <span data-ttu-id="c363e-124">此设置已弃用，并且将不起任何作用。</span><span class="sxs-lookup"><span data-stu-id="c363e-124">This setting is deprecated and will have no effect.</span></span>
[<span data-ttu-id="c363e-125">get_IsStatusBarEnabled</span><span class="sxs-lookup"><span data-stu-id="c363e-125">get_IsStatusBarEnabled</span></span>](#get_isstatusbarenabled) | <span data-ttu-id="c363e-126">IsStatusBarEnabled 控制状态栏是否将显示。</span><span class="sxs-lookup"><span data-stu-id="c363e-126">IsStatusBarEnabled controls whether the status bar will be displayed.</span></span>
[<span data-ttu-id="c363e-127">put_IsStatusBarEnabled</span><span class="sxs-lookup"><span data-stu-id="c363e-127">put_IsStatusBarEnabled</span></span>](#put_isstatusbarenabled) | <span data-ttu-id="c363e-128">设置 IsStatusBarEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="c363e-128">Set the IsStatusBarEnabled property.</span></span>
[<span data-ttu-id="c363e-129">get_AreDevToolsEnabled</span><span class="sxs-lookup"><span data-stu-id="c363e-129">get_AreDevToolsEnabled</span></span>](#get_aredevtoolsenabled) | <span data-ttu-id="c363e-130">AreDevToolsEnabled 控制用户是否可以使用上下文菜单或键盘快捷方式打开 DevTools 窗口。</span><span class="sxs-lookup"><span data-stu-id="c363e-130">AreDevToolsEnabled controls whether the user is able to use the context menu or keyboard shortcuts to open the DevTools window.</span></span>
[<span data-ttu-id="c363e-131">put_AreDevToolsEnabled</span><span class="sxs-lookup"><span data-stu-id="c363e-131">put_AreDevToolsEnabled</span></span>](#put_aredevtoolsenabled) | <span data-ttu-id="c363e-132">设置 AreDevToolsEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="c363e-132">Set the AreDevToolsEnabled property.</span></span>

<span data-ttu-id="c363e-133">在 NavigationStarting 事件之后设置所做的更改将不会应用到下一个顶级导航。</span><span class="sxs-lookup"><span data-stu-id="c363e-133">Setting changes made after NavigationStarting event will not apply until the next top level navigation.</span></span>

## <span data-ttu-id="c363e-134">成员</span><span class="sxs-lookup"><span data-stu-id="c363e-134">Members</span></span>

#### <span data-ttu-id="c363e-135">get_IsScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="c363e-135">get_IsScriptEnabled</span></span> 

<span data-ttu-id="c363e-136">控制在 Web 视图中的所有未来导航中是否启用了 JavaScript 执行。</span><span class="sxs-lookup"><span data-stu-id="c363e-136">Controls if JavaScript execution is enabled in all future navigations in the WebView.</span></span>

> <span data-ttu-id="c363e-137">public HRESULT [get_IsScriptEnabled](#get_isscriptenabled)（BOOL \* IsScriptEnabled）</span><span class="sxs-lookup"><span data-stu-id="c363e-137">public HRESULT [get_IsScriptEnabled](#get_isscriptenabled)(BOOL \* isScriptEnabled)</span></span>

<span data-ttu-id="c363e-138">这仅影响文档中的脚本;即使脚本被禁用，用 ExecuteScript 插入的脚本也会运行。</span><span class="sxs-lookup"><span data-stu-id="c363e-138">This only affects scripts in the document; scripts injected with ExecuteScript will run even if script is disabled.</span></span> <span data-ttu-id="c363e-139">默认情况下为 true。</span><span class="sxs-lookup"><span data-stu-id="c363e-139">It is true by default.</span></span>

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

#### <span data-ttu-id="c363e-140">put_IsScriptEnabled</span><span class="sxs-lookup"><span data-stu-id="c363e-140">put_IsScriptEnabled</span></span> 

<span data-ttu-id="c363e-141">设置 IsScriptEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="c363e-141">Set the IsScriptEnabled property.</span></span>

> <span data-ttu-id="c363e-142">公共 HRESULT [put_IsScriptEnabled](#put_isscriptenabled)（布尔值 IsScriptEnabled）</span><span class="sxs-lookup"><span data-stu-id="c363e-142">public HRESULT [put_IsScriptEnabled](#put_isscriptenabled)(BOOL isScriptEnabled)</span></span>

#### <span data-ttu-id="c363e-143">get_IsWebMessageEnabled</span><span class="sxs-lookup"><span data-stu-id="c363e-143">get_IsWebMessageEnabled</span></span> 

<span data-ttu-id="c363e-144">加载新的 HTML 文档时，将使用 IsWebMessageEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="c363e-144">The IsWebMessageEnabled property is used when loading a new HTML document.</span></span>

> <span data-ttu-id="c363e-145">public HRESULT [get_IsWebMessageEnabled](#get_iswebmessageenabled)（BOOL \* IsWebMessageEnabled）</span><span class="sxs-lookup"><span data-stu-id="c363e-145">public HRESULT [get_IsWebMessageEnabled](#get_iswebmessageenabled)(BOOL \* isWebMessageEnabled)</span></span>

<span data-ttu-id="c363e-146">如果设置为 true，则通过 PostWebMessageAsJson、PostWebMessageAsString 和，从主机到 web 视图的顶级 HTML 文档的通信是允许通过 web 视图、和 window。 chrome 的消息事件（有关详细信息，请参阅 PostWebMessageAsJson 文档）。</span><span class="sxs-lookup"><span data-stu-id="c363e-146">If set to true, communication from the host to the webview's top level HTML document is allowed via PostWebMessageAsJson, PostWebMessageAsString, and window.chrome.webview's message event (see PostWebMessageAsJson documentation for details).</span></span> <span data-ttu-id="c363e-147">通过 window 的 postMessage 函数和 SetWebMessageReceivedEventHandler 方法，允许从 web 视图的顶级 HTML 文档到主机的通信（有关详细信息，请参阅 SetWebMessageReceivedEventHandler 文档）。</span><span class="sxs-lookup"><span data-stu-id="c363e-147">Communication from the webview's top level HTML document to the host is allowed via window.chrome.webview's postMessage function and the SetWebMessageReceivedEventHandler method (see the SetWebMessageReceivedEventHandler documentation for details).</span></span> <span data-ttu-id="c363e-148">如果设置为 false，则不允许通信。</span><span class="sxs-lookup"><span data-stu-id="c363e-148">If set to false, then communication is disallowed.</span></span> <span data-ttu-id="c363e-149">PostWebMessageAsJson 和 PostWebMessageAsString 将失败 E_ACCESSDENIED，并且通过引发 Error 对象的实例，postMessage 将失败。</span><span class="sxs-lookup"><span data-stu-id="c363e-149">PostWebMessageAsJson and PostWebMessageAsString will fail with E_ACCESSDENIED and window.chrome.webview.postMessage will fail by throwing an instance of an Error object.</span></span> <span data-ttu-id="c363e-150">默认情况下为 true。</span><span class="sxs-lookup"><span data-stu-id="c363e-150">It is true by default.</span></span>

```cpp
    ComPtr<IWebView2Settings> settings;
    CHECK_FAILURE(m_webView->get_Settings(&settings));

    CHECK_FAILURE(settings->put_IsWebMessageEnabled(TRUE));
```

#### <span data-ttu-id="c363e-151">put_IsWebMessageEnabled</span><span class="sxs-lookup"><span data-stu-id="c363e-151">put_IsWebMessageEnabled</span></span> 

<span data-ttu-id="c363e-152">设置 IsWebMessageEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="c363e-152">Set the IsWebMessageEnabled property.</span></span>

> <span data-ttu-id="c363e-153">公共 HRESULT [put_IsWebMessageEnabled](#put_iswebmessageenabled)（布尔值 IsWebMessageEnabled）</span><span class="sxs-lookup"><span data-stu-id="c363e-153">public HRESULT [put_IsWebMessageEnabled](#put_iswebmessageenabled)(BOOL isWebMessageEnabled)</span></span>

#### <span data-ttu-id="c363e-154">get_AreDefaultScriptDialogsEnabled</span><span class="sxs-lookup"><span data-stu-id="c363e-154">get_AreDefaultScriptDialogsEnabled</span></span> 

<span data-ttu-id="c363e-155">加载新的 HTML 文档时，将使用 AreDefaultScriptDialogsEnabled。</span><span class="sxs-lookup"><span data-stu-id="c363e-155">AreDefaultScriptDialogsEnabled is used when loading a new HTML document.</span></span>

> <span data-ttu-id="c363e-156">public HRESULT [get_AreDefaultScriptDialogsEnabled](#get_aredefaultscriptdialogsenabled)（BOOL \* AreDefaultScriptDialogsEnabled）</span><span class="sxs-lookup"><span data-stu-id="c363e-156">public HRESULT [get_AreDefaultScriptDialogsEnabled](#get_aredefaultscriptdialogsenabled)(BOOL \* areDefaultScriptDialogsEnabled)</span></span>

<span data-ttu-id="c363e-157">如果设置为 false，则 Web 视图不会呈现默认 javascript 对话框（具体由 javascript 警报、确认和提示函数显示的对话框）。</span><span class="sxs-lookup"><span data-stu-id="c363e-157">If set to false, then WebView won't render the default javascript dialog box (Specifically those shown by the javascript alert, confirm, and prompt functions).</span></span> <span data-ttu-id="c363e-158">相反，如果 SetScriptDialogOpeningEventHandler 设置了事件处理程序，则 Web 视图将发送一个包含对话框的所有信息的事件，并允许主机应用显示其自己的自定义 UI。</span><span class="sxs-lookup"><span data-stu-id="c363e-158">Instead, if an event handler is set by SetScriptDialogOpeningEventHandler, WebView will send an event that will contain all of the information for the dialog and allow the host app to show its own custom UI.</span></span>

#### <span data-ttu-id="c363e-159">put_AreDefaultScriptDialogsEnabled</span><span class="sxs-lookup"><span data-stu-id="c363e-159">put_AreDefaultScriptDialogsEnabled</span></span> 

<span data-ttu-id="c363e-160">设置 AreDefaultScriptDialogsEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="c363e-160">Set the AreDefaultScriptDialogsEnabled property.</span></span>

> <span data-ttu-id="c363e-161">公共 HRESULT [put_AreDefaultScriptDialogsEnabled](#put_aredefaultscriptdialogsenabled)（布尔值 AreDefaultScriptDialogsEnabled）</span><span class="sxs-lookup"><span data-stu-id="c363e-161">public HRESULT [put_AreDefaultScriptDialogsEnabled](#put_aredefaultscriptdialogsenabled)(BOOL areDefaultScriptDialogsEnabled)</span></span>

#### <span data-ttu-id="c363e-162">get_IsFullscreenAllowed_deprecated</span><span class="sxs-lookup"><span data-stu-id="c363e-162">get_IsFullscreenAllowed_deprecated</span></span> 

<span data-ttu-id="c363e-163">此设置已弃用，并且将始终返回 false。</span><span class="sxs-lookup"><span data-stu-id="c363e-163">This setting is deprecated and will always return false.</span></span>

> <span data-ttu-id="c363e-164">public HRESULT [get_IsFullscreenAllowed_deprecated](#get_isfullscreenallowed_deprecated)（BOOL \* IsFullscreenAllowed）</span><span class="sxs-lookup"><span data-stu-id="c363e-164">public HRESULT [get_IsFullscreenAllowed_deprecated](#get_isfullscreenallowed_deprecated)(BOOL \* isFullscreenAllowed)</span></span>

<span data-ttu-id="c363e-165">这意味着 Web 视图中的元素将仅填充 Web 视图边界。</span><span class="sxs-lookup"><span data-stu-id="c363e-165">That means elements in the WebView will only fill the WebView bounds.</span></span> <span data-ttu-id="c363e-166">此属性将被完全删除。</span><span class="sxs-lookup"><span data-stu-id="c363e-166">This property will then be completely removed.</span></span> <span data-ttu-id="c363e-167">请改为收听 ContainsFullScreenElementChanged 事件。</span><span class="sxs-lookup"><span data-stu-id="c363e-167">Please listen to the ContainsFullScreenElementChanged event instead.</span></span>

<span data-ttu-id="c363e-168">控制 Web 视图中的元素是否允许全屏。</span><span class="sxs-lookup"><span data-stu-id="c363e-168">Controls if fullscreen is allowed for elements in the WebView.</span></span> <span data-ttu-id="c363e-169">如果允许，则允许 web 内容（如 web 视图中的视频元素）全屏显示。</span><span class="sxs-lookup"><span data-stu-id="c363e-169">When it is allowed, web content such as a video element in the WebView is allowed to be displayed full screen.</span></span> <span data-ttu-id="c363e-170">当不允许时，此类元素将在元素请求全屏时填充 Web 视图边界。</span><span class="sxs-lookup"><span data-stu-id="c363e-170">When it is not allowed, such element will fill the WebView bounds when the element requests full screen.</span></span> <span data-ttu-id="c363e-171">默认情况下为 true。</span><span class="sxs-lookup"><span data-stu-id="c363e-171">It is true by default.</span></span>

#### <span data-ttu-id="c363e-172">put_IsFullscreenAllowed_deprecated</span><span class="sxs-lookup"><span data-stu-id="c363e-172">put_IsFullscreenAllowed_deprecated</span></span> 

<span data-ttu-id="c363e-173">此设置已弃用，并且将不起任何作用。</span><span class="sxs-lookup"><span data-stu-id="c363e-173">This setting is deprecated and will have no effect.</span></span>

> <span data-ttu-id="c363e-174">公共 HRESULT [put_IsFullscreenAllowed_deprecated](#put_isfullscreenallowed_deprecated)（布尔值 IsFullscreenAllowed）</span><span class="sxs-lookup"><span data-stu-id="c363e-174">public HRESULT [put_IsFullscreenAllowed_deprecated](#put_isfullscreenallowed_deprecated)(BOOL isFullscreenAllowed)</span></span>

<span data-ttu-id="c363e-175">请改为收听 ContainsFullScreenElementChanged 事件。</span><span class="sxs-lookup"><span data-stu-id="c363e-175">Please listen to the ContainsFullScreenElementChanged event instead.</span></span>

<span data-ttu-id="c363e-176">设置 IsFullscreenAllowed 属性。</span><span class="sxs-lookup"><span data-stu-id="c363e-176">Set the IsFullscreenAllowed property.</span></span>

#### <span data-ttu-id="c363e-177">get_IsStatusBarEnabled</span><span class="sxs-lookup"><span data-stu-id="c363e-177">get_IsStatusBarEnabled</span></span> 

<span data-ttu-id="c363e-178">IsStatusBarEnabled 控制状态栏是否将显示。</span><span class="sxs-lookup"><span data-stu-id="c363e-178">IsStatusBarEnabled controls whether the status bar will be displayed.</span></span>

> <span data-ttu-id="c363e-179">public HRESULT [get_IsStatusBarEnabled](#get_isstatusbarenabled)（BOOL \* IsStatusBarEnabled）</span><span class="sxs-lookup"><span data-stu-id="c363e-179">public HRESULT [get_IsStatusBarEnabled](#get_isstatusbarenabled)(BOOL \* isStatusBarEnabled)</span></span>

<span data-ttu-id="c363e-180">状态栏通常显示在 Web 视图的左下方，并且在用户悬停在其上方和其他信息时显示链接的 URI 等内容。</span><span class="sxs-lookup"><span data-stu-id="c363e-180">The status bar is usually displayed in the lower left of the WebView and shows things such as the URI of a link when the user hovers over it and other information.</span></span> <span data-ttu-id="c363e-181">默认情况下为 true。</span><span class="sxs-lookup"><span data-stu-id="c363e-181">It is true by default.</span></span>

#### <span data-ttu-id="c363e-182">put_IsStatusBarEnabled</span><span class="sxs-lookup"><span data-stu-id="c363e-182">put_IsStatusBarEnabled</span></span> 

<span data-ttu-id="c363e-183">设置 IsStatusBarEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="c363e-183">Set the IsStatusBarEnabled property.</span></span>

> <span data-ttu-id="c363e-184">公共 HRESULT [put_IsStatusBarEnabled](#put_isstatusbarenabled)（布尔值 IsStatusBarEnabled）</span><span class="sxs-lookup"><span data-stu-id="c363e-184">public HRESULT [put_IsStatusBarEnabled](#put_isstatusbarenabled)(BOOL isStatusBarEnabled)</span></span>

#### <span data-ttu-id="c363e-185">get_AreDevToolsEnabled</span><span class="sxs-lookup"><span data-stu-id="c363e-185">get_AreDevToolsEnabled</span></span> 

<span data-ttu-id="c363e-186">AreDevToolsEnabled 控制用户是否可以使用上下文菜单或键盘快捷方式打开 DevTools 窗口。</span><span class="sxs-lookup"><span data-stu-id="c363e-186">AreDevToolsEnabled controls whether the user is able to use the context menu or keyboard shortcuts to open the DevTools window.</span></span>

> <span data-ttu-id="c363e-187">public HRESULT [get_AreDevToolsEnabled](#get_aredevtoolsenabled)（BOOL \* AreDevToolsEnabled）</span><span class="sxs-lookup"><span data-stu-id="c363e-187">public HRESULT [get_AreDevToolsEnabled](#get_aredevtoolsenabled)(BOOL \* areDevToolsEnabled)</span></span>

<span data-ttu-id="c363e-188">默认情况下为 true。</span><span class="sxs-lookup"><span data-stu-id="c363e-188">It is true by default.</span></span>

#### <span data-ttu-id="c363e-189">put_AreDevToolsEnabled</span><span class="sxs-lookup"><span data-stu-id="c363e-189">put_AreDevToolsEnabled</span></span> 

<span data-ttu-id="c363e-190">设置 AreDevToolsEnabled 属性。</span><span class="sxs-lookup"><span data-stu-id="c363e-190">Set the AreDevToolsEnabled property.</span></span>

> <span data-ttu-id="c363e-191">公共 HRESULT [put_AreDevToolsEnabled](#put_aredevtoolsenabled)（布尔值 AreDevToolsEnabled）</span><span class="sxs-lookup"><span data-stu-id="c363e-191">public HRESULT [put_AreDevToolsEnabled](#put_aredevtoolsenabled)(BOOL areDevToolsEnabled)</span></span>

