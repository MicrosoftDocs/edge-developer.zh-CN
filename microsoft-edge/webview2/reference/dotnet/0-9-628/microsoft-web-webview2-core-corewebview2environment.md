---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: CoreWebView2Environment 中的 WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、web 视图、新、wpf、winforms、app、edge、CoreWebView2、CoreWebView2Controller、浏览器控件、边缘 html、、浏览器控件、边缘 html、WebView2
ms.openlocfilehash: c6b1f1c62da5aa5ef64693575abb9cb46ac13851
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011704"
---
# <span data-ttu-id="eda40-104">CoreWebView2Environment 类的 WebView2</span><span class="sxs-lookup"><span data-stu-id="eda40-104">Microsoft.Web.WebView2.Core.CoreWebView2Environment class</span></span> 

<span data-ttu-id="eda40-105">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="eda40-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="eda40-106">程序集： Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="eda40-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="eda40-107">这表示 WebView2 环境。</span><span class="sxs-lookup"><span data-stu-id="eda40-107">This represents the WebView2 Environment.</span></span>

## <span data-ttu-id="eda40-108">摘要</span><span class="sxs-lookup"><span data-stu-id="eda40-108">Summary</span></span>

 <span data-ttu-id="eda40-109">成员</span><span class="sxs-lookup"><span data-stu-id="eda40-109">Members</span></span>                        | <span data-ttu-id="eda40-110">描述</span><span class="sxs-lookup"><span data-stu-id="eda40-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="eda40-111">BrowserVersionString</span><span class="sxs-lookup"><span data-stu-id="eda40-111">BrowserVersionString</span></span>](#browserversionstring) | <span data-ttu-id="eda40-112">当前 CoreWebView2Environment 的浏览器版本信息，包括频道名称（如果不是稳定频道）。</span><span class="sxs-lookup"><span data-stu-id="eda40-112">The browser version info of the current CoreWebView2Environment, including channel name if it is not the stable channel.</span></span>
[<span data-ttu-id="eda40-113">NewBrowserVersionAvailable</span><span class="sxs-lookup"><span data-stu-id="eda40-113">NewBrowserVersionAvailable</span></span>](#newbrowserversionavailable) | <span data-ttu-id="eda40-114">当已安装较新版本的 Edge 浏览器并可通过 WebView2 使用时，将触发 NewBrowserVersionAvailable。</span><span class="sxs-lookup"><span data-stu-id="eda40-114">NewBrowserVersionAvailable fires when a newer version of the Edge browser is installed and available for use via WebView2.</span></span>
[<span data-ttu-id="eda40-115">CreateCoreWebView2CompositionControllerAsync</span><span class="sxs-lookup"><span data-stu-id="eda40-115">CreateCoreWebView2CompositionControllerAsync</span></span>](#createcorewebview2compositioncontrollerasync) | <span data-ttu-id="eda40-116">异步创建用于可视化托管的新 Web 视图。</span><span class="sxs-lookup"><span data-stu-id="eda40-116">Asynchronously create a new WebView for use with visual hosting.</span></span>
[<span data-ttu-id="eda40-117">CreateCoreWebView2ControllerAsync</span><span class="sxs-lookup"><span data-stu-id="eda40-117">CreateCoreWebView2ControllerAsync</span></span>](#createcorewebview2controllerasync) | <span data-ttu-id="eda40-118">异步创建新的 Web 视图。</span><span class="sxs-lookup"><span data-stu-id="eda40-118">Asynchronously create a new WebView.</span></span>
[<span data-ttu-id="eda40-119">CreateCoreWebView2PointerInfo</span><span class="sxs-lookup"><span data-stu-id="eda40-119">CreateCoreWebView2PointerInfo</span></span>](#createcorewebview2pointerinfo) | <span data-ttu-id="eda40-120">创建一个空 CoreWebView2PointerInfo。</span><span class="sxs-lookup"><span data-stu-id="eda40-120">Create an empty CoreWebView2PointerInfo.</span></span>
[<span data-ttu-id="eda40-121">CreateWebResourceResponse</span><span class="sxs-lookup"><span data-stu-id="eda40-121">CreateWebResourceResponse</span></span>](#createwebresourceresponse) | <span data-ttu-id="eda40-122">创建新的 web 资源响应对象。</span><span class="sxs-lookup"><span data-stu-id="eda40-122">Create a new web resource response object.</span></span>
[<span data-ttu-id="eda40-123">GetProviderForHwnd</span><span class="sxs-lookup"><span data-stu-id="eda40-123">GetProviderForHwnd</span></span>](#getproviderforhwnd) | <span data-ttu-id="eda40-124">返回与给定 HWND 对应的 CoreWebView2CompositionController 的 UI 自动化提供程序。</span><span class="sxs-lookup"><span data-stu-id="eda40-124">Returns the UI Automation Provider for the CoreWebView2CompositionController that corresponds with the given HWND.</span></span>

<span data-ttu-id="eda40-125">在使用环境参数指定的浏览器进程中运行的环境中创建的 WebViews，应在同一环境中使用。</span><span class="sxs-lookup"><span data-stu-id="eda40-125">WebViews created from an environment run on the Browser process specified with environment parameters and objects created from an environment should be used in the same environment.</span></span> <span data-ttu-id="eda40-126">在不同的环境中使用它不保证兼容，并且可能会失败。</span><span class="sxs-lookup"><span data-stu-id="eda40-126">Using it in different environments are not guaranteed to be compatible and may fail.</span></span> 

<span data-ttu-id="eda40-127">在使用环境参数指定的浏览器进程中运行的环境中创建的 WebViews，应在同一环境中使用。</span><span class="sxs-lookup"><span data-stu-id="eda40-127">WebViews created from an environment run on the browser process specified with environment parameters and objects created from an environment should be used in the same environment.</span></span> <span data-ttu-id="eda40-128">在不同的环境中使用它不保证兼容，并且可能会失败。</span><span class="sxs-lookup"><span data-stu-id="eda40-128">Using it in different environments are not guaranteed to be compatible and may fail.</span></span>

## <span data-ttu-id="eda40-129">成员</span><span class="sxs-lookup"><span data-stu-id="eda40-129">Members</span></span>

#### <span data-ttu-id="eda40-130">BrowserVersionString</span><span class="sxs-lookup"><span data-stu-id="eda40-130">BrowserVersionString</span></span> 

<span data-ttu-id="eda40-131">当前 CoreWebView2Environment 的浏览器版本信息，包括频道名称（如果不是稳定频道）。</span><span class="sxs-lookup"><span data-stu-id="eda40-131">The browser version info of the current CoreWebView2Environment, including channel name if it is not the stable channel.</span></span>

> <span data-ttu-id="eda40-132">公共字符串 [BrowserVersionString](#browserversionstring)</span><span class="sxs-lookup"><span data-stu-id="eda40-132">public string [BrowserVersionString](#browserversionstring)</span></span>

<span data-ttu-id="eda40-133">这与 GetAvailableCoreWebView2BrowserVersionString API 的格式相匹配。</span><span class="sxs-lookup"><span data-stu-id="eda40-133">This matches the format of the GetAvailableCoreWebView2BrowserVersionString API.</span></span> <span data-ttu-id="eda40-134">信道名称为 "beta"、"dev" 和 "未设备"。</span><span class="sxs-lookup"><span data-stu-id="eda40-134">Channel names are 'beta', 'dev', and 'canary'.</span></span>

#### <span data-ttu-id="eda40-135">NewBrowserVersionAvailable</span><span class="sxs-lookup"><span data-stu-id="eda40-135">NewBrowserVersionAvailable</span></span> 

<span data-ttu-id="eda40-136">当已安装较新版本的 Edge 浏览器并可通过 WebView2 使用时，将触发 NewBrowserVersionAvailable。</span><span class="sxs-lookup"><span data-stu-id="eda40-136">NewBrowserVersionAvailable fires when a newer version of the Edge browser is installed and available for use via WebView2.</span></span>

> <span data-ttu-id="eda40-137">公共事件 EventHandler< 对象 > [NewBrowserVersionAvailable](#newbrowserversionavailable)</span><span class="sxs-lookup"><span data-stu-id="eda40-137">public event EventHandler< object > [NewBrowserVersionAvailable](#newbrowserversionavailable)</span></span>

<span data-ttu-id="eda40-138">若要使用较新版本的浏览器，必须创建新的环境和 Web 视图。</span><span class="sxs-lookup"><span data-stu-id="eda40-138">To use the newer version of the browser you must create a new environment and WebView.</span></span> <span data-ttu-id="eda40-139">将仅针对从其运行代码的同一边缘通道中的新版本引发此事件。</span><span class="sxs-lookup"><span data-stu-id="eda40-139">This event will only be fired for new version from the same Edge channel that the code is running from.</span></span> <span data-ttu-id="eda40-140">当不运行安装的边缘时，将不会触发任何事件。</span><span class="sxs-lookup"><span data-stu-id="eda40-140">When not running with installed Edge, no event will be fired.</span></span>

<span data-ttu-id="eda40-141">由于用户数据文件夹一次只能由一个浏览器进程使用，如果要在 WebViews 中使用新版本的浏览器使用同一用户数据文件夹，则必须先关闭使用早期版本的浏览器的环境和 WebViews。</span><span class="sxs-lookup"><span data-stu-id="eda40-141">Because a user data folder can only be used by one browser process at a time, if you want to use the same user data folder in the WebViews using the new version of the browser, you must close the environment and WebViews that are using the older version of the browser first.</span></span> <span data-ttu-id="eda40-142">或者只提示用户重新启动应用。</span><span class="sxs-lookup"><span data-stu-id="eda40-142">Or simply prompt the user to restart the app.</span></span>

#### <span data-ttu-id="eda40-143">CreateCoreWebView2CompositionControllerAsync</span><span class="sxs-lookup"><span data-stu-id="eda40-143">CreateCoreWebView2CompositionControllerAsync</span></span> 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

<span data-ttu-id="eda40-144">异步创建用于可视化托管的新 Web 视图。</span><span class="sxs-lookup"><span data-stu-id="eda40-144">Asynchronously create a new WebView for use with visual hosting.</span></span>

> <span data-ttu-id="eda40-145">公共异步任务< [CoreWebView2CompositionController](microsoft-web-webview2-core-corewebview2compositioncontroller.md)  >  [CreateCoreWebView2CompositionControllerAsync](#createcorewebview2compositioncontrollerasync) (IntPtr ParentWindow) </span><span class="sxs-lookup"><span data-stu-id="eda40-145">public async Task< [CoreWebView2CompositionController](microsoft-web-webview2-core-corewebview2compositioncontroller.md) > [CreateCoreWebView2CompositionControllerAsync](#createcorewebview2compositioncontrollerasync)(IntPtr ParentWindow)</span></span>

<span data-ttu-id="eda40-146">parentWindow 是应用将连接 Web 视图的可视化树的 HWND。</span><span class="sxs-lookup"><span data-stu-id="eda40-146">parentWindow is the HWND in which the app will connect the visual tree of the WebView.</span></span> <span data-ttu-id="eda40-147">这将是应用将接收指向 Web 视图的指针/鼠标输入的 HWND (并且需要使用 SendMouseInput/SendPointerInput 转发) 。</span><span class="sxs-lookup"><span data-stu-id="eda40-147">This will be the HWND that the app will receive pointer/ mouse input meant for the WebView (and will need to use SendMouseInput/ SendPointerInput to forward).</span></span> <span data-ttu-id="eda40-148">如果应用将 Web 视图可视化树移动到另一个窗口下方，则需要设置 CoreWebView2CompositionController 以更新可视化树的新父 HWND。</span><span class="sxs-lookup"><span data-stu-id="eda40-148">If the app moves the WebView visual tree to underneath a different window, then it needs to set CoreWebView2CompositionController.ParentWindow to update the new parent HWND of the visual tree.</span></span>

<span data-ttu-id="eda40-149">在创建的 CoreWebView2CompositionController 上设置 RootVisualTarget 属性，以提供视觉对象以托管浏览器的可视化树。</span><span class="sxs-lookup"><span data-stu-id="eda40-149">Set RootVisualTarget property on the created CoreWebView2CompositionController to provide a visual to host the browser's visual tree.</span></span>

<span data-ttu-id="eda40-150">建议为进程或应用程序窗口设置应用程序用户模型 ID。</span><span class="sxs-lookup"><span data-stu-id="eda40-150">It is recommended that the application set Application User Model ID for the process or the application window.</span></span> <span data-ttu-id="eda40-151">如果未设置，则在创建 Web 视图期间生成的应用程序用户模型 ID 将设置为 parentWindow 的根窗口。</span><span class="sxs-lookup"><span data-stu-id="eda40-151">If none is set, during WebView creation a generated Application User Model ID is set to root window of parentWindow.</span></span>

#### <span data-ttu-id="eda40-152">CreateCoreWebView2ControllerAsync</span><span class="sxs-lookup"><span data-stu-id="eda40-152">CreateCoreWebView2ControllerAsync</span></span> 

<span data-ttu-id="eda40-153">异步创建新的 Web 视图。</span><span class="sxs-lookup"><span data-stu-id="eda40-153">Asynchronously create a new WebView.</span></span>

> <span data-ttu-id="eda40-154">公共异步任务< [CoreWebView2Controller](microsoft-web-webview2-core-corewebview2controller.md)  >  [CreateCoreWebView2ControllerAsync](#createcorewebview2controllerasync) (IntPtr ParentWindow) </span><span class="sxs-lookup"><span data-stu-id="eda40-154">public async Task< [CoreWebView2Controller](microsoft-web-webview2-core-corewebview2controller.md) > [CreateCoreWebView2ControllerAsync](#createcorewebview2controllerasync)(IntPtr ParentWindow)</span></span>

<span data-ttu-id="eda40-155">parentWindow 是应在其中显示 Web 视图和接收输入的 HWND。</span><span class="sxs-lookup"><span data-stu-id="eda40-155">parentWindow is the HWND in which the WebView should be displayed and from which receive input.</span></span> <span data-ttu-id="eda40-156">在创建 Web 视图期间，Web 视图会将子窗口添加到提供的窗口中。</span><span class="sxs-lookup"><span data-stu-id="eda40-156">The WebView will add a child window to the provided window during WebView creation.</span></span> <span data-ttu-id="eda40-157">由同辈窗口顺序影响的 Z 顺序和其他项目将相应受到影响。</span><span class="sxs-lookup"><span data-stu-id="eda40-157">Z-order and other things impacted by sibling window order will be affected accordingly.</span></span>

<span data-ttu-id="eda40-158">建议为进程或应用程序窗口设置应用程序用户模型 ID。</span><span class="sxs-lookup"><span data-stu-id="eda40-158">It is recommended that the application set Application User Model ID for the process or the application window.</span></span> <span data-ttu-id="eda40-159">如果未设置，则在创建 Web 视图期间生成的应用程序用户模型 ID 将设置为 parentWindow 的根窗口。</span><span class="sxs-lookup"><span data-stu-id="eda40-159">If none is set, during WebView creation a generated Application User Model ID is set to root window of parentWindow.</span></span>

#### <span data-ttu-id="eda40-160">CreateCoreWebView2PointerInfo</span><span class="sxs-lookup"><span data-stu-id="eda40-160">CreateCoreWebView2PointerInfo</span></span> 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

<span data-ttu-id="eda40-161">创建一个空 CoreWebView2PointerInfo。</span><span class="sxs-lookup"><span data-stu-id="eda40-161">Create an empty CoreWebView2PointerInfo.</span></span>

> <span data-ttu-id="eda40-162">公共 [CoreWebView2PointerInfo](microsoft-web-webview2-core-corewebview2pointerinfo.md) [CreateCoreWebView2PointerInfo](#createcorewebview2pointerinfo) ( # A1</span><span class="sxs-lookup"><span data-stu-id="eda40-162">public [CoreWebView2PointerInfo](microsoft-web-webview2-core-corewebview2pointerinfo.md) [CreateCoreWebView2PointerInfo](#createcorewebview2pointerinfo)()</span></span>

<span data-ttu-id="eda40-163">在调用 SendPointerInput 之前，需要用所有相关信息填充返回的 CoreWebView2PointerInfo。</span><span class="sxs-lookup"><span data-stu-id="eda40-163">The returned CoreWebView2PointerInfo needs to be populated with all of the relevant info before calling SendPointerInput.</span></span>

#### <span data-ttu-id="eda40-164">CreateWebResourceResponse</span><span class="sxs-lookup"><span data-stu-id="eda40-164">CreateWebResourceResponse</span></span> 

<span data-ttu-id="eda40-165">创建新的 web 资源响应对象。</span><span class="sxs-lookup"><span data-stu-id="eda40-165">Create a new web resource response object.</span></span>

> <span data-ttu-id="eda40-166">公共 [CoreWebView2WebResourceResponse](microsoft-web-webview2-core-corewebview2webresourceresponse.md) [CreateWebResourceResponse](#createwebresourceresponse) (流内容、Int StatusCode、String ReasonPhrase、string 标题) </span><span class="sxs-lookup"><span data-stu-id="eda40-166">public [CoreWebView2WebResourceResponse](microsoft-web-webview2-core-corewebview2webresourceresponse.md) [CreateWebResourceResponse](#createwebresourceresponse)(Stream Content, int StatusCode, string ReasonPhrase, string Headers)</span></span>

<span data-ttu-id="eda40-167">标头是由换行符分隔的原始响应标题字符串。</span><span class="sxs-lookup"><span data-stu-id="eda40-167">The headers is the raw response header string delimited by newline.</span></span> <span data-ttu-id="eda40-168">也可以使用空的标头字符串创建此对象，然后使用 CoreWebView2HttpResponseHeaders 来逐行构造标题。</span><span class="sxs-lookup"><span data-stu-id="eda40-168">It's also possible to create this object with empty headers string and then use the CoreWebView2HttpResponseHeaders to construct the headers line by line.</span></span> <span data-ttu-id="eda40-169">有关其他参数的信息，请参阅 CoreWebView2WebResourceResponse。</span><span class="sxs-lookup"><span data-stu-id="eda40-169">For information on other parameters see CoreWebView2WebResourceResponse.</span></span>

#### <span data-ttu-id="eda40-170">GetProviderForHwnd</span><span class="sxs-lookup"><span data-stu-id="eda40-170">GetProviderForHwnd</span></span> 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

<span data-ttu-id="eda40-171">返回与给定 HWND 对应的 CoreWebView2CompositionController 的 UI 自动化提供程序。</span><span class="sxs-lookup"><span data-stu-id="eda40-171">Returns the UI Automation Provider for the CoreWebView2CompositionController that corresponds with the given HWND.</span></span>

> <span data-ttu-id="eda40-172">公共对象 [GetProviderForHwnd](#getproviderforhwnd) (IntPtr hwnd) </span><span class="sxs-lookup"><span data-stu-id="eda40-172">public object [GetProviderForHwnd](#getproviderforhwnd)(IntPtr hwnd)</span></span>

