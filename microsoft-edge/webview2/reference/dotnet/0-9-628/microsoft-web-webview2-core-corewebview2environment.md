---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: CoreWebView2Environment 中的 WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/11/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、web 视图、新、wpf、winforms、app、edge、CoreWebView2、CoreWebView2Controller、浏览器控件、边缘 html、、浏览器控件、边缘 html、WebView2
ms.openlocfilehash: 05b8a10c723ae57b2c95551f4d5043f3336eba3b
ms.sourcegitcommit: 65db518273b3cd69f1b3c528809600719b9b70aa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/16/2020
ms.locfileid: "11016324"
---
# <span data-ttu-id="62266-104">CoreWebView2Environment 类的 WebView2</span><span class="sxs-lookup"><span data-stu-id="62266-104">Microsoft.Web.WebView2.Core.CoreWebView2Environment class</span></span> 

<span data-ttu-id="62266-105">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="62266-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="62266-106">程序集： Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="62266-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="62266-107">这表示 WebView2 环境。</span><span class="sxs-lookup"><span data-stu-id="62266-107">This represents the WebView2 Environment.</span></span>

## <span data-ttu-id="62266-108">摘要</span><span class="sxs-lookup"><span data-stu-id="62266-108">Summary</span></span>

 <span data-ttu-id="62266-109">成员</span><span class="sxs-lookup"><span data-stu-id="62266-109">Members</span></span>                        | <span data-ttu-id="62266-110">描述</span><span class="sxs-lookup"><span data-stu-id="62266-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="62266-111">BrowserVersionString</span><span class="sxs-lookup"><span data-stu-id="62266-111">BrowserVersionString</span></span>](#browserversionstring) | <span data-ttu-id="62266-112">当前 CoreWebView2Environment 的浏览器版本信息，包括频道名称（如果不是稳定频道）。</span><span class="sxs-lookup"><span data-stu-id="62266-112">The browser version info of the current CoreWebView2Environment, including channel name if it is not the stable channel.</span></span>
[<span data-ttu-id="62266-113">NewBrowserVersionAvailable</span><span class="sxs-lookup"><span data-stu-id="62266-113">NewBrowserVersionAvailable</span></span>](#newbrowserversionavailable) | <span data-ttu-id="62266-114">当已安装较新版本的 Edge 浏览器并可通过 WebView2 使用时，将触发 NewBrowserVersionAvailable。</span><span class="sxs-lookup"><span data-stu-id="62266-114">NewBrowserVersionAvailable fires when a newer version of the Edge browser is installed and available for use via WebView2.</span></span>
[<span data-ttu-id="62266-115">CompareBrowserVersions</span><span class="sxs-lookup"><span data-stu-id="62266-115">CompareBrowserVersions</span></span>](#comparebrowserversions) | <span data-ttu-id="62266-116">比较浏览器版本以确定它们是否匹配或不同。</span><span class="sxs-lookup"><span data-stu-id="62266-116">Compare browser versions to determine if they match or are different.</span></span>
[<span data-ttu-id="62266-117">CreateAsync</span><span class="sxs-lookup"><span data-stu-id="62266-117">CreateAsync</span></span>](#createasync) | <span data-ttu-id="62266-118">使用已安装的 Microsoft Edge 版本创建长绿 WebView2 环境。</span><span class="sxs-lookup"><span data-stu-id="62266-118">Creates an evergreen WebView2 Environment using the installed version of Microsoft Edge.</span></span>
[<span data-ttu-id="62266-119">CreateCoreWebView2CompositionControllerAsync</span><span class="sxs-lookup"><span data-stu-id="62266-119">CreateCoreWebView2CompositionControllerAsync</span></span>](#createcorewebview2compositioncontrollerasync) | <span data-ttu-id="62266-120">异步创建用于可视化托管的新 Web 视图。</span><span class="sxs-lookup"><span data-stu-id="62266-120">Asynchronously create a new WebView for use with visual hosting.</span></span>
[<span data-ttu-id="62266-121">CreateCoreWebView2ControllerAsync</span><span class="sxs-lookup"><span data-stu-id="62266-121">CreateCoreWebView2ControllerAsync</span></span>](#createcorewebview2controllerasync) | <span data-ttu-id="62266-122">异步创建新的 Web 视图。</span><span class="sxs-lookup"><span data-stu-id="62266-122">Asynchronously create a new WebView.</span></span>
[<span data-ttu-id="62266-123">CreateCoreWebView2PointerInfo</span><span class="sxs-lookup"><span data-stu-id="62266-123">CreateCoreWebView2PointerInfo</span></span>](#createcorewebview2pointerinfo) | <span data-ttu-id="62266-124">创建一个空 CoreWebView2PointerInfo。</span><span class="sxs-lookup"><span data-stu-id="62266-124">Create an empty CoreWebView2PointerInfo.</span></span>
[<span data-ttu-id="62266-125">CreateWebResourceResponse</span><span class="sxs-lookup"><span data-stu-id="62266-125">CreateWebResourceResponse</span></span>](#createwebresourceresponse) | <span data-ttu-id="62266-126">创建新的 web 资源响应对象。</span><span class="sxs-lookup"><span data-stu-id="62266-126">Create a new web resource response object.</span></span>
[<span data-ttu-id="62266-127">GetAvailableBrowserVersionString</span><span class="sxs-lookup"><span data-stu-id="62266-127">GetAvailableBrowserVersionString</span></span>](#getavailablebrowserversionstring) | <span data-ttu-id="62266-128">获取浏览器版本信息。</span><span class="sxs-lookup"><span data-stu-id="62266-128">Get the browser version information.</span></span>
[<span data-ttu-id="62266-129">GetProviderForHwnd</span><span class="sxs-lookup"><span data-stu-id="62266-129">GetProviderForHwnd</span></span>](#getproviderforhwnd) | <span data-ttu-id="62266-130">返回与给定 HWND 对应的 CoreWebView2CompositionController 的 UI 自动化提供程序。</span><span class="sxs-lookup"><span data-stu-id="62266-130">Returns the UI Automation Provider for the CoreWebView2CompositionController that corresponds with the given HWND.</span></span>

<span data-ttu-id="62266-131">在使用环境参数指定的浏览器进程中运行的环境中创建的 WebViews，应在同一环境中使用。</span><span class="sxs-lookup"><span data-stu-id="62266-131">WebViews created from an environment run on the Browser process specified with environment parameters and objects created from an environment should be used in the same environment.</span></span> <span data-ttu-id="62266-132">在不同的环境中使用它不保证兼容，并且可能会失败。</span><span class="sxs-lookup"><span data-stu-id="62266-132">Using it in different environments are not guaranteed to be compatible and may fail.</span></span> 

## <span data-ttu-id="62266-133">成员</span><span class="sxs-lookup"><span data-stu-id="62266-133">Members</span></span>

#### <span data-ttu-id="62266-134">BrowserVersionString</span><span class="sxs-lookup"><span data-stu-id="62266-134">BrowserVersionString</span></span> 

<span data-ttu-id="62266-135">当前 CoreWebView2Environment 的浏览器版本信息，包括频道名称（如果不是稳定频道）。</span><span class="sxs-lookup"><span data-stu-id="62266-135">The browser version info of the current CoreWebView2Environment, including channel name if it is not the stable channel.</span></span>

> <span data-ttu-id="62266-136">公共字符串 [BrowserVersionString](#browserversionstring)</span><span class="sxs-lookup"><span data-stu-id="62266-136">public string [BrowserVersionString](#browserversionstring)</span></span>

<span data-ttu-id="62266-137">这与 GetAvailableCoreWebView2BrowserVersionString API 的格式相匹配。</span><span class="sxs-lookup"><span data-stu-id="62266-137">This matches the format of the GetAvailableCoreWebView2BrowserVersionString API.</span></span> <span data-ttu-id="62266-138">信道名称为 "beta"、"dev" 和 "未设备"。</span><span class="sxs-lookup"><span data-stu-id="62266-138">Channel names are 'beta', 'dev', and 'canary'.</span></span>

#### <span data-ttu-id="62266-139">NewBrowserVersionAvailable</span><span class="sxs-lookup"><span data-stu-id="62266-139">NewBrowserVersionAvailable</span></span> 

<span data-ttu-id="62266-140">当已安装较新版本的 Edge 浏览器并可通过 WebView2 使用时，将触发 NewBrowserVersionAvailable。</span><span class="sxs-lookup"><span data-stu-id="62266-140">NewBrowserVersionAvailable fires when a newer version of the Edge browser is installed and available for use via WebView2.</span></span>

> <span data-ttu-id="62266-141">公共事件 EventHandler< 对象 > [NewBrowserVersionAvailable](#newbrowserversionavailable)</span><span class="sxs-lookup"><span data-stu-id="62266-141">public event EventHandler< object > [NewBrowserVersionAvailable](#newbrowserversionavailable)</span></span>

<span data-ttu-id="62266-142">若要使用较新版本的浏览器，必须创建新的环境和 Web 视图。</span><span class="sxs-lookup"><span data-stu-id="62266-142">To use the newer version of the browser you must create a new environment and WebView.</span></span> <span data-ttu-id="62266-143">将仅针对从其运行代码的同一边缘通道中的新版本引发此事件。</span><span class="sxs-lookup"><span data-stu-id="62266-143">This event will only be fired for new version from the same Edge channel that the code is running from.</span></span> <span data-ttu-id="62266-144">当不运行安装的边缘时，将不会触发任何事件。</span><span class="sxs-lookup"><span data-stu-id="62266-144">When not running with installed Edge, no event will be fired.</span></span>

<span data-ttu-id="62266-145">由于用户数据文件夹一次只能由一个浏览器进程使用，如果要在 WebViews 中使用新版本的浏览器使用同一用户数据文件夹，则必须先关闭使用早期版本的浏览器的环境和 WebViews。</span><span class="sxs-lookup"><span data-stu-id="62266-145">Because a user data folder can only be used by one browser process at a time, if you want to use the same user data folder in the WebViews using the new version of the browser, you must close the environment and WebViews that are using the older version of the browser first.</span></span> <span data-ttu-id="62266-146">或者只提示用户重新启动应用。</span><span class="sxs-lookup"><span data-stu-id="62266-146">Or simply prompt the user to restart the app.</span></span>

#### <span data-ttu-id="62266-147">CompareBrowserVersions</span><span class="sxs-lookup"><span data-stu-id="62266-147">CompareBrowserVersions</span></span> 

<span data-ttu-id="62266-148">比较浏览器版本以确定它们是否匹配或不同。</span><span class="sxs-lookup"><span data-stu-id="62266-148">Compare browser versions to determine if they match or are different.</span></span>

> <span data-ttu-id="62266-149">公共静态 int [CompareBrowserVersions](#comparebrowserversions) (string version1，string version2) </span><span class="sxs-lookup"><span data-stu-id="62266-149">public static int [CompareBrowserVersions](#comparebrowserversions)(string version1, string version2)</span></span>

<span data-ttu-id="62266-150">返回-1、0或1，具体取决于第一个版本是否小于、等于或大于要比较的第二个版本。</span><span class="sxs-lookup"><span data-stu-id="62266-150">Returns -1, 0 or 1 depending on whether the first version is less than, equal to or greater than the second version being compared.</span></span>

<span data-ttu-id="62266-151">输入可以直接使用从 GetAvailableCoreWebView2BrowserVersionString 获取的 versionInfo，信道信息将被忽略。</span><span class="sxs-lookup"><span data-stu-id="62266-151">Input can directly use the versionInfo obtained from GetAvailableCoreWebView2BrowserVersionString, channel info will be ignored.</span></span>

##### <span data-ttu-id="62266-152">参数</span><span class="sxs-lookup"><span data-stu-id="62266-152">Parameters</span></span>
* `version1` <span data-ttu-id="62266-153">要比较的第一个版本。</span><span class="sxs-lookup"><span data-stu-id="62266-153">The first version to compare.</span></span> 

* `version2` <span data-ttu-id="62266-154">要比较的第二个版本。</span><span class="sxs-lookup"><span data-stu-id="62266-154">The second version to compare.</span></span>

#### <span data-ttu-id="62266-155">CreateAsync</span><span class="sxs-lookup"><span data-stu-id="62266-155">CreateAsync</span></span> 

<span data-ttu-id="62266-156">使用已安装的 Microsoft Edge 版本创建长绿 WebView2 环境。</span><span class="sxs-lookup"><span data-stu-id="62266-156">Creates an evergreen WebView2 Environment using the installed version of Microsoft Edge.</span></span>

> <span data-ttu-id="62266-157">公共静态异步任务< [CoreWebView2Environment](microsoft-web-webview2-core-corewebview2environment.md)  >  [CreateAsync](#createasync) (string browserExecutableFolder、string userDataFolder、CoreWebView2EnvironmentOptions 选项) </span><span class="sxs-lookup"><span data-stu-id="62266-157">public static async Task< [CoreWebView2Environment](microsoft-web-webview2-core-corewebview2environment.md) > [CreateAsync](#createasync)(string browserExecutableFolder, string userDataFolder, CoreWebView2EnvironmentOptions options)</span></span>

##### <span data-ttu-id="62266-158">参数</span><span class="sxs-lookup"><span data-stu-id="62266-158">Parameters</span></span>
* `browserExecutableFolder` <span data-ttu-id="62266-159">包含 WebView2 运行时的固定版本的文件夹的相对路径。</span><span class="sxs-lookup"><span data-stu-id="62266-159">The relative path to the folder that contains the fixed version of the WebView2 Runtime.</span></span> 

* `userDataFolder` <span data-ttu-id="62266-160">可以指定 userDataFolder 以更改 WebView2 的默认用户数据文件夹位置。</span><span class="sxs-lookup"><span data-stu-id="62266-160">userDataFolder can be specified to change the default user data folder location for WebView2.</span></span> 

* `options` <span data-ttu-id="62266-161">用于创建 WebView2 环境的选项。</span><span class="sxs-lookup"><span data-stu-id="62266-161">Options used to create WebView2 Environment.</span></span>

#### <span data-ttu-id="62266-162">CreateCoreWebView2CompositionControllerAsync</span><span class="sxs-lookup"><span data-stu-id="62266-162">CreateCoreWebView2CompositionControllerAsync</span></span> 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

<span data-ttu-id="62266-163">异步创建用于可视化托管的新 Web 视图。</span><span class="sxs-lookup"><span data-stu-id="62266-163">Asynchronously create a new WebView for use with visual hosting.</span></span>

> <span data-ttu-id="62266-164">公共异步任务< [CoreWebView2CompositionController](microsoft-web-webview2-core-corewebview2compositioncontroller.md)  >  [CreateCoreWebView2CompositionControllerAsync](#createcorewebview2compositioncontrollerasync) (IntPtr ParentWindow) </span><span class="sxs-lookup"><span data-stu-id="62266-164">public async Task< [CoreWebView2CompositionController](microsoft-web-webview2-core-corewebview2compositioncontroller.md) > [CreateCoreWebView2CompositionControllerAsync](#createcorewebview2compositioncontrollerasync)(IntPtr ParentWindow)</span></span>

<span data-ttu-id="62266-165">parentWindow 是应用将连接 Web 视图的可视化树的 HWND。</span><span class="sxs-lookup"><span data-stu-id="62266-165">parentWindow is the HWND in which the app will connect the visual tree of the WebView.</span></span> <span data-ttu-id="62266-166">这将是应用将接收指向 Web 视图的指针/鼠标输入的 HWND (并且需要使用 SendMouseInput/SendPointerInput 转发) 。</span><span class="sxs-lookup"><span data-stu-id="62266-166">This will be the HWND that the app will receive pointer/ mouse input meant for the WebView (and will need to use SendMouseInput/ SendPointerInput to forward).</span></span> <span data-ttu-id="62266-167">如果应用将 Web 视图可视化树移动到另一个窗口下方，则需要设置 CoreWebView2CompositionController 以更新可视化树的新父 HWND。</span><span class="sxs-lookup"><span data-stu-id="62266-167">If the app moves the WebView visual tree to underneath a different window, then it needs to set CoreWebView2CompositionController.ParentWindow to update the new parent HWND of the visual tree.</span></span>

<span data-ttu-id="62266-168">在创建的 CoreWebView2CompositionController 上设置 RootVisualTarget 属性，以提供视觉对象以托管浏览器的可视化树。</span><span class="sxs-lookup"><span data-stu-id="62266-168">Set RootVisualTarget property on the created CoreWebView2CompositionController to provide a visual to host the browser's visual tree.</span></span>

<span data-ttu-id="62266-169">建议为进程或应用程序窗口设置应用程序用户模型 ID。</span><span class="sxs-lookup"><span data-stu-id="62266-169">It is recommended that the application set Application User Model ID for the process or the application window.</span></span> <span data-ttu-id="62266-170">如果未设置，则在创建 Web 视图期间生成的应用程序用户模型 ID 将设置为 parentWindow 的根窗口。</span><span class="sxs-lookup"><span data-stu-id="62266-170">If none is set, during WebView creation a generated Application User Model ID is set to root window of parentWindow.</span></span>

#### <span data-ttu-id="62266-171">CreateCoreWebView2ControllerAsync</span><span class="sxs-lookup"><span data-stu-id="62266-171">CreateCoreWebView2ControllerAsync</span></span> 

<span data-ttu-id="62266-172">异步创建新的 Web 视图。</span><span class="sxs-lookup"><span data-stu-id="62266-172">Asynchronously create a new WebView.</span></span>

> <span data-ttu-id="62266-173">公共异步任务< [CoreWebView2Controller](microsoft-web-webview2-core-corewebview2controller.md)  >  [CreateCoreWebView2ControllerAsync](#createcorewebview2controllerasync) (IntPtr ParentWindow) </span><span class="sxs-lookup"><span data-stu-id="62266-173">public async Task< [CoreWebView2Controller](microsoft-web-webview2-core-corewebview2controller.md) > [CreateCoreWebView2ControllerAsync](#createcorewebview2controllerasync)(IntPtr ParentWindow)</span></span>

<span data-ttu-id="62266-174">parentWindow 是应在其中显示 Web 视图和接收输入的 HWND。</span><span class="sxs-lookup"><span data-stu-id="62266-174">parentWindow is the HWND in which the WebView should be displayed and from which receive input.</span></span> <span data-ttu-id="62266-175">在创建 Web 视图期间，Web 视图会将子窗口添加到提供的窗口中。</span><span class="sxs-lookup"><span data-stu-id="62266-175">The WebView will add a child window to the provided window during WebView creation.</span></span> <span data-ttu-id="62266-176">由同辈窗口顺序影响的 Z 顺序和其他项目将相应受到影响。</span><span class="sxs-lookup"><span data-stu-id="62266-176">Z-order and other things impacted by sibling window order will be affected accordingly.</span></span>

<span data-ttu-id="62266-177">建议为进程或应用程序窗口设置应用程序用户模型 ID。</span><span class="sxs-lookup"><span data-stu-id="62266-177">It is recommended that the application set Application User Model ID for the process or the application window.</span></span> <span data-ttu-id="62266-178">如果未设置，则在创建 Web 视图期间生成的应用程序用户模型 ID 将设置为 parentWindow 的根窗口。</span><span class="sxs-lookup"><span data-stu-id="62266-178">If none is set, during WebView creation a generated Application User Model ID is set to root window of parentWindow.</span></span>

#### <span data-ttu-id="62266-179">CreateCoreWebView2PointerInfo</span><span class="sxs-lookup"><span data-stu-id="62266-179">CreateCoreWebView2PointerInfo</span></span> 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

<span data-ttu-id="62266-180">创建一个空 CoreWebView2PointerInfo。</span><span class="sxs-lookup"><span data-stu-id="62266-180">Create an empty CoreWebView2PointerInfo.</span></span>

> <span data-ttu-id="62266-181">公共 [CoreWebView2PointerInfo](microsoft-web-webview2-core-corewebview2pointerinfo.md) [CreateCoreWebView2PointerInfo](#createcorewebview2pointerinfo) ( # A1</span><span class="sxs-lookup"><span data-stu-id="62266-181">public [CoreWebView2PointerInfo](microsoft-web-webview2-core-corewebview2pointerinfo.md) [CreateCoreWebView2PointerInfo](#createcorewebview2pointerinfo)()</span></span>

<span data-ttu-id="62266-182">在调用 SendPointerInput 之前，需要用所有相关信息填充返回的 CoreWebView2PointerInfo。</span><span class="sxs-lookup"><span data-stu-id="62266-182">The returned CoreWebView2PointerInfo needs to be populated with all of the relevant info before calling SendPointerInput.</span></span>

#### <span data-ttu-id="62266-183">CreateWebResourceResponse</span><span class="sxs-lookup"><span data-stu-id="62266-183">CreateWebResourceResponse</span></span> 

<span data-ttu-id="62266-184">创建新的 web 资源响应对象。</span><span class="sxs-lookup"><span data-stu-id="62266-184">Create a new web resource response object.</span></span>

> <span data-ttu-id="62266-185">公共 [CoreWebView2WebResourceResponse](microsoft-web-webview2-core-corewebview2webresourceresponse.md) [CreateWebResourceResponse](#createwebresourceresponse) (流内容、Int StatusCode、String ReasonPhrase、string 标题) </span><span class="sxs-lookup"><span data-stu-id="62266-185">public [CoreWebView2WebResourceResponse](microsoft-web-webview2-core-corewebview2webresourceresponse.md) [CreateWebResourceResponse](#createwebresourceresponse)(Stream Content, int StatusCode, string ReasonPhrase, string Headers)</span></span>

<span data-ttu-id="62266-186">标头是由换行符分隔的原始响应标题字符串。</span><span class="sxs-lookup"><span data-stu-id="62266-186">The headers is the raw response header string delimited by newline.</span></span> <span data-ttu-id="62266-187">也可以使用空的标头字符串创建此对象，然后使用 CoreWebView2HttpResponseHeaders 来逐行构造标题。</span><span class="sxs-lookup"><span data-stu-id="62266-187">It's also possible to create this object with empty headers string and then use the CoreWebView2HttpResponseHeaders to construct the headers line by line.</span></span> <span data-ttu-id="62266-188">有关其他参数的信息，请参阅 CoreWebView2WebResourceResponse。</span><span class="sxs-lookup"><span data-stu-id="62266-188">For information on other parameters see CoreWebView2WebResourceResponse.</span></span>

#### <span data-ttu-id="62266-189">GetAvailableBrowserVersionString</span><span class="sxs-lookup"><span data-stu-id="62266-189">GetAvailableBrowserVersionString</span></span> 

<span data-ttu-id="62266-190">获取浏览器版本信息。</span><span class="sxs-lookup"><span data-stu-id="62266-190">Get the browser version information.</span></span>

> <span data-ttu-id="62266-191">公共静态字符串 [GetAvailableBrowserVersionString](#getavailablebrowserversionstring) (字符串 browserExecutableFolder) </span><span class="sxs-lookup"><span data-stu-id="62266-191">public static string [GetAvailableBrowserVersionString](#getavailablebrowserversionstring)(string browserExecutableFolder)</span></span>

<span data-ttu-id="62266-192">如果信道不是稳定通道，也可以获取信道名称。</span><span class="sxs-lookup"><span data-stu-id="62266-192">You also get the channel name if the channel is not a stable channel.</span></span> <span data-ttu-id="62266-193">如果使用 WebView2 运行时，则不会返回任何信道名称。</span><span class="sxs-lookup"><span data-stu-id="62266-193">If you use the WebView2 Runtime, no channel name is returned.</span></span>

##### <span data-ttu-id="62266-194">参数</span><span class="sxs-lookup"><span data-stu-id="62266-194">Parameters</span></span>
* `browserExecutableFolder` <span data-ttu-id="62266-195">包含 WebView2 运行时的固定版本的文件夹的相对路径。</span><span class="sxs-lookup"><span data-stu-id="62266-195">The relative path to the folder that contains the fixed version of the WebView2 Runtime.</span></span>

#### <span data-ttu-id="62266-196">GetProviderForHwnd</span><span class="sxs-lookup"><span data-stu-id="62266-196">GetProviderForHwnd</span></span> 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

<span data-ttu-id="62266-197">返回与给定 HWND 对应的 CoreWebView2CompositionController 的 UI 自动化提供程序。</span><span class="sxs-lookup"><span data-stu-id="62266-197">Returns the UI Automation Provider for the CoreWebView2CompositionController that corresponds with the given HWND.</span></span>

> <span data-ttu-id="62266-198">公共对象 [GetProviderForHwnd](#getproviderforhwnd) (IntPtr hwnd) </span><span class="sxs-lookup"><span data-stu-id="62266-198">public object [GetProviderForHwnd](#getproviderforhwnd)(IntPtr hwnd)</span></span>
