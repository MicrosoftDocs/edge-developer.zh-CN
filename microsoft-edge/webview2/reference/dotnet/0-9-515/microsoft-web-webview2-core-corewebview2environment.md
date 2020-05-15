---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/12/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: be8f475d4c1a886a92b46144f2bffde2d49dc9d4
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10653117"
---
# <span data-ttu-id="b846a-104">CoreWebView2Environment 类的 WebView2</span><span class="sxs-lookup"><span data-stu-id="b846a-104">Microsoft.Web.WebView2.Core.CoreWebView2Environment class</span></span> 

<span data-ttu-id="b846a-105">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="b846a-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="b846a-106">程序集： Microsoft WebView2</span><span class="sxs-lookup"><span data-stu-id="b846a-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="b846a-107">这表示 WebView2 环境。</span><span class="sxs-lookup"><span data-stu-id="b846a-107">This represents the WebView2 Environment.</span></span>

## <span data-ttu-id="b846a-108">摘要</span><span class="sxs-lookup"><span data-stu-id="b846a-108">Summary</span></span>

 <span data-ttu-id="b846a-109">成员</span><span class="sxs-lookup"><span data-stu-id="b846a-109">Members</span></span>                        | <span data-ttu-id="b846a-110">描述</span><span class="sxs-lookup"><span data-stu-id="b846a-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="b846a-111">BrowserVersionString</span><span class="sxs-lookup"><span data-stu-id="b846a-111">BrowserVersionString</span></span>](#browserversionstring) | <span data-ttu-id="b846a-112">当前 CoreWebView2Environment 的浏览器版本信息，包括频道名称（如果不是稳定频道）。</span><span class="sxs-lookup"><span data-stu-id="b846a-112">The browser version info of the current CoreWebView2Environment, including channel name if it is not the stable channel.</span></span>
[<span data-ttu-id="b846a-113">NewBrowserVersionAvailable</span><span class="sxs-lookup"><span data-stu-id="b846a-113">NewBrowserVersionAvailable</span></span>](#newbrowserversionavailable) | <span data-ttu-id="b846a-114">当已安装更高版本的 Edge 浏览器并可通过 WebView2 使用时，将引发 NewBrowserVersionAvailable 事件。</span><span class="sxs-lookup"><span data-stu-id="b846a-114">The NewBrowserVersionAvailable event fires when a newer version of the Edge browser is installed and available to use via WebView2.</span></span>
[<span data-ttu-id="b846a-115">CreateAsync</span><span class="sxs-lookup"><span data-stu-id="b846a-115">CreateAsync</span></span>](#createasync) | <span data-ttu-id="b846a-116">使用安装的边缘版本创建长绿 WebView2 环境。</span><span class="sxs-lookup"><span data-stu-id="b846a-116">Creates an evergreen WebView2 Environment using the installed Edge version.</span></span>
[<span data-ttu-id="b846a-117">CreateCoreWebView2ControllerAsync</span><span class="sxs-lookup"><span data-stu-id="b846a-117">CreateCoreWebView2ControllerAsync</span></span>](#createcorewebview2controllerasync) | <span data-ttu-id="b846a-118">异步创建新的 Web 视图。</span><span class="sxs-lookup"><span data-stu-id="b846a-118">Asynchronously create a new WebView.</span></span>
[<span data-ttu-id="b846a-119">CreateWebResourceResponse</span><span class="sxs-lookup"><span data-stu-id="b846a-119">CreateWebResourceResponse</span></span>](#createwebresourceresponse) | <span data-ttu-id="b846a-120">创建新的 web 资源响应对象。</span><span class="sxs-lookup"><span data-stu-id="b846a-120">Create a new web resource response object.</span></span>

<span data-ttu-id="b846a-121">在使用环境参数指定的浏览器进程中运行的环境中创建的 WebViews，应在同一环境中使用。</span><span class="sxs-lookup"><span data-stu-id="b846a-121">WebViews created from an environment run on the Browser process specified with environment parameters and objects created from an environment should be used in the same environment.</span></span> <span data-ttu-id="b846a-122">在不同的环境中使用它不保证兼容，并且可能会失败。</span><span class="sxs-lookup"><span data-stu-id="b846a-122">Using it in different environments are not guaranteed to be compatible and may fail.</span></span>

## <span data-ttu-id="b846a-123">成员</span><span class="sxs-lookup"><span data-stu-id="b846a-123">Members</span></span>

#### <span data-ttu-id="b846a-124">BrowserVersionString</span><span class="sxs-lookup"><span data-stu-id="b846a-124">BrowserVersionString</span></span> 

<span data-ttu-id="b846a-125">当前 CoreWebView2Environment 的浏览器版本信息，包括频道名称（如果不是稳定频道）。</span><span class="sxs-lookup"><span data-stu-id="b846a-125">The browser version info of the current CoreWebView2Environment, including channel name if it is not the stable channel.</span></span>

> <span data-ttu-id="b846a-126">公共字符串[BrowserVersionString](#browserversionstring)</span><span class="sxs-lookup"><span data-stu-id="b846a-126">public string [BrowserVersionString](#browserversionstring)</span></span>

<span data-ttu-id="b846a-127">这与 GetAvailableCoreWebView2BrowserVersionString API 的格式相匹配。</span><span class="sxs-lookup"><span data-stu-id="b846a-127">This matches the format of the GetAvailableCoreWebView2BrowserVersionString API.</span></span> <span data-ttu-id="b846a-128">信道名称为 "beta"、"dev" 和 "未设备"。</span><span class="sxs-lookup"><span data-stu-id="b846a-128">Channel names are 'beta', 'dev', and 'canary'.</span></span>

#### <span data-ttu-id="b846a-129">NewBrowserVersionAvailable</span><span class="sxs-lookup"><span data-stu-id="b846a-129">NewBrowserVersionAvailable</span></span> 

<span data-ttu-id="b846a-130">当已安装更高版本的 Edge 浏览器并可通过 WebView2 使用时，将引发 NewBrowserVersionAvailable 事件。</span><span class="sxs-lookup"><span data-stu-id="b846a-130">The NewBrowserVersionAvailable event fires when a newer version of the Edge browser is installed and available to use via WebView2.</span></span>

> <span data-ttu-id="b846a-131">公共事件 EventHandler< 对象 > [NewBrowserVersionAvailable](#newbrowserversionavailable)</span><span class="sxs-lookup"><span data-stu-id="b846a-131">public event EventHandler< object > [NewBrowserVersionAvailable](#newbrowserversionavailable)</span></span>

<span data-ttu-id="b846a-132">若要使用较新版本的浏览器，必须创建新的环境和 Web 视图。</span><span class="sxs-lookup"><span data-stu-id="b846a-132">To use the newer version of the browser you must create a new environment and WebView.</span></span> <span data-ttu-id="b846a-133">将仅针对从其运行代码的同一边缘通道中的新版本引发此事件。</span><span class="sxs-lookup"><span data-stu-id="b846a-133">This event will only be fired for new version from the same Edge channel that the code is running from.</span></span> <span data-ttu-id="b846a-134">当不运行安装的边缘时，将不会触发任何事件。</span><span class="sxs-lookup"><span data-stu-id="b846a-134">When not running with installed Edge, no event will be fired.</span></span>

<span data-ttu-id="b846a-135">由于用户数据文件夹一次只能由一个浏览器进程使用，如果要在 WebViews 中使用新版本的浏览器使用同一用户数据文件夹，则必须先关闭使用早期版本的浏览器的环境和 WebViews。</span><span class="sxs-lookup"><span data-stu-id="b846a-135">Because a user data folder can only be used by one browser process at a time, if you want to use the same user data folder in the WebViews using the new version of the browser, you must close the environment and WebViews that are using the older version of the browser first.</span></span> <span data-ttu-id="b846a-136">或者只提示用户重新启动应用。</span><span class="sxs-lookup"><span data-stu-id="b846a-136">Or simply prompt the user to restart the app.</span></span>

#### <span data-ttu-id="b846a-137">CreateAsync</span><span class="sxs-lookup"><span data-stu-id="b846a-137">CreateAsync</span></span> 

<span data-ttu-id="b846a-138">使用安装的边缘版本创建长绿 WebView2 环境。</span><span class="sxs-lookup"><span data-stu-id="b846a-138">Creates an evergreen WebView2 Environment using the installed Edge version.</span></span>

> <span data-ttu-id="b846a-139">公共异步任务< [CoreWebView2Environment](microsoft-web-webview2-core-corewebview2environment.md)  >  [CreateAsync](#createasync)（string browserExecutableFolder、string userDataFolder、CoreWebView2EnvironmentOptions 选项）</span><span class="sxs-lookup"><span data-stu-id="b846a-139">public async Task< [CoreWebView2Environment](microsoft-web-webview2-core-corewebview2environment.md) > [CreateAsync](#createasync)(string browserExecutableFolder, string userDataFolder, CoreWebView2EnvironmentOptions options)</span></span>

##### <span data-ttu-id="b846a-140">参数</span><span class="sxs-lookup"><span data-stu-id="b846a-140">Parameters</span></span>
* `browserExecutableFolder` <span data-ttu-id="b846a-141">包含嵌入边缘的文件夹的相对路径。</span><span class="sxs-lookup"><span data-stu-id="b846a-141">The relative path to the folder that contains the embedded Edge.</span></span> 

* `userDataFolder` <span data-ttu-id="b846a-142">可以指定 userDataFolder 以更改 WebView2 的默认用户数据文件夹位置。</span><span class="sxs-lookup"><span data-stu-id="b846a-142">userDataFolder can be specified to change the default user data folder location for WebView2.</span></span> 

* `options` <span data-ttu-id="b846a-143">用于创建 WebView2 环境的选项。</span><span class="sxs-lookup"><span data-stu-id="b846a-143">Options used to create WebView2 Environment.</span></span>

#### <span data-ttu-id="b846a-144">CreateCoreWebView2ControllerAsync</span><span class="sxs-lookup"><span data-stu-id="b846a-144">CreateCoreWebView2ControllerAsync</span></span> 

<span data-ttu-id="b846a-145">异步创建新的 Web 视图。</span><span class="sxs-lookup"><span data-stu-id="b846a-145">Asynchronously create a new WebView.</span></span>

> <span data-ttu-id="b846a-146">公共异步任务< [CoreWebView2Controller](microsoft-web-webview2-core-corewebview2controller.md)  >  [CreateCoreWebView2ControllerAsync](#createcorewebview2controllerasync)（IntPtr ParentWindow）</span><span class="sxs-lookup"><span data-stu-id="b846a-146">public async Task< [CoreWebView2Controller](microsoft-web-webview2-core-corewebview2controller.md) > [CreateCoreWebView2ControllerAsync](#createcorewebview2controllerasync)(IntPtr ParentWindow)</span></span>

<span data-ttu-id="b846a-147">parentWindow 是应在其中显示 Web 视图和接收输入的 HWND。</span><span class="sxs-lookup"><span data-stu-id="b846a-147">parentWindow is the HWND in which the WebView should be displayed and from which receive input.</span></span> <span data-ttu-id="b846a-148">在创建 Web 视图期间，Web 视图会将子窗口添加到提供的窗口中。</span><span class="sxs-lookup"><span data-stu-id="b846a-148">The WebView will add a child window to the provided window during WebView creation.</span></span> <span data-ttu-id="b846a-149">由同辈窗口顺序影响的 Z 顺序和其他项目将相应受到影响。</span><span class="sxs-lookup"><span data-stu-id="b846a-149">Z-order and other things impacted by sibling window order will be affected accordingly.</span></span>

<span data-ttu-id="b846a-150">建议为进程或应用程序窗口设置应用程序用户模型 ID。</span><span class="sxs-lookup"><span data-stu-id="b846a-150">It is recommended that the application set Application User Model ID for the process or the application window.</span></span> <span data-ttu-id="b846a-151">如果未设置，则在创建 Web 视图期间生成的应用程序用户模型 ID 将设置为 parentWindow 的根窗口。</span><span class="sxs-lookup"><span data-stu-id="b846a-151">If none is set, during WebView creation a generated Application User Model ID is set to root window of parentWindow.</span></span>

#### <span data-ttu-id="b846a-152">CreateWebResourceResponse</span><span class="sxs-lookup"><span data-stu-id="b846a-152">CreateWebResourceResponse</span></span> 

<span data-ttu-id="b846a-153">创建新的 web 资源响应对象。</span><span class="sxs-lookup"><span data-stu-id="b846a-153">Create a new web resource response object.</span></span>

> <span data-ttu-id="b846a-154">公共 HttpResponseMessage [CreateWebResourceResponse](#createwebresourceresponse)（流内容、int StatusCode、string ReasonPhrase、string 头）</span><span class="sxs-lookup"><span data-stu-id="b846a-154">public HttpResponseMessage [CreateWebResourceResponse](#createwebresourceresponse)(Stream Content, int StatusCode, string ReasonPhrase, string Headers)</span></span>

<span data-ttu-id="b846a-155">标头是由换行符分隔的原始响应标题字符串。</span><span class="sxs-lookup"><span data-stu-id="b846a-155">The headers is the raw response header string delimited by newline.</span></span> <span data-ttu-id="b846a-156">也可以使用空的标头字符串创建此对象，然后使用 CoreWebView2HttpResponseHeaders 来逐行构造标题。</span><span class="sxs-lookup"><span data-stu-id="b846a-156">It's also possible to create this object with empty headers string and then use the CoreWebView2HttpResponseHeaders to construct the headers line by line.</span></span> <span data-ttu-id="b846a-157">有关其他参数的信息，请参阅 CoreWebView2WebResourceResponse。</span><span class="sxs-lookup"><span data-stu-id="b846a-157">For information on other parameters see CoreWebView2WebResourceResponse.</span></span>

