---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: 全局变量
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/09/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 37a7d89dbd7d13befe5a07c72fc8baa750775108
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011762"
---
# <span data-ttu-id="d79fc-104">全局变量</span><span class="sxs-lookup"><span data-stu-id="d79fc-104">Globals</span></span> 

## <span data-ttu-id="d79fc-105">摘要</span><span class="sxs-lookup"><span data-stu-id="d79fc-105">Summary</span></span>

 <span data-ttu-id="d79fc-106">成员</span><span class="sxs-lookup"><span data-stu-id="d79fc-106">Members</span></span>                        | <span data-ttu-id="d79fc-107">描述</span><span class="sxs-lookup"><span data-stu-id="d79fc-107">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="d79fc-108">CompareBrowserVersions</span><span class="sxs-lookup"><span data-stu-id="d79fc-108">CompareBrowserVersions</span></span>](#comparebrowserversions) | <span data-ttu-id="d79fc-109">此方法适用于任何人都希望正确比较版本以确定哪个版本较旧、更旧或相同。</span><span class="sxs-lookup"><span data-stu-id="d79fc-109">This method is for anyone want to compare version correctly to determine which version is newer, older or same.</span></span>
[<span data-ttu-id="d79fc-110">CreateCoreWebView2Environment</span><span class="sxs-lookup"><span data-stu-id="d79fc-110">CreateCoreWebView2Environment</span></span>](#createcorewebview2environment) | <span data-ttu-id="d79fc-111">使用安装的边缘版本创建长绿 WebView2 环境。</span><span class="sxs-lookup"><span data-stu-id="d79fc-111">Creates an evergreen WebView2 Environment using the installed Edge version.</span></span>
[<span data-ttu-id="d79fc-112">CreateCoreWebView2EnvironmentWithOptions</span><span class="sxs-lookup"><span data-stu-id="d79fc-112">CreateCoreWebView2EnvironmentWithOptions</span></span>](#createcorewebview2environmentwithoptions) | <span data-ttu-id="d79fc-113">DLL 导出以使用自定义版本的 Edge、用户数据目录和/或其他选项创建 WebView2 环境。</span><span class="sxs-lookup"><span data-stu-id="d79fc-113">DLL export to create a WebView2 environment with a custom version of Edge, user data directory and/or additional options.</span></span>
[<span data-ttu-id="d79fc-114">GetAvailableCoreWebView2BrowserVersionString</span><span class="sxs-lookup"><span data-stu-id="d79fc-114">GetAvailableCoreWebView2BrowserVersionString</span></span>](#getavailablecorewebview2browserversionstring) | <span data-ttu-id="d79fc-115">获取包含频道名称的浏览器版本信息（如果不是稳定通道或嵌入边缘）。</span><span class="sxs-lookup"><span data-stu-id="d79fc-115">Get the browser version info including channel name if it is not the stable channel or the Embedded Edge.</span></span>

## <span data-ttu-id="d79fc-116">成员</span><span class="sxs-lookup"><span data-stu-id="d79fc-116">Members</span></span>

#### <span data-ttu-id="d79fc-117">CompareBrowserVersions</span><span class="sxs-lookup"><span data-stu-id="d79fc-117">CompareBrowserVersions</span></span> 

> <span data-ttu-id="d79fc-118">public STDAPI [CompareBrowserVersions](#comparebrowserversions) (PCWSTR VERSION1，PCWSTR version2，int \* 结果) </span><span class="sxs-lookup"><span data-stu-id="d79fc-118">public STDAPI [CompareBrowserVersions](#comparebrowserversions)(PCWSTR version1, PCWSTR version2, int \* result)</span></span>

<span data-ttu-id="d79fc-119">此方法适用于任何人都希望正确比较版本以确定哪个版本较旧、更旧或相同。</span><span class="sxs-lookup"><span data-stu-id="d79fc-119">This method is for anyone want to compare version correctly to determine which version is newer, older or same.</span></span>

<span data-ttu-id="d79fc-120">它可用于确定是在版本上使用 webview2 还是特定功能库。</span><span class="sxs-lookup"><span data-stu-id="d79fc-120">It can be used to determine whether to use webview2 or certain feature base on version.</span></span> <span data-ttu-id="d79fc-121">如果 version1 小于、等于或大于 version2，则将结果的值设置为-1、0或1。</span><span class="sxs-lookup"><span data-stu-id="d79fc-121">Sets the value of result to -1, 0 or 1 if version1 is less than, equal or greater than version2 respectively.</span></span> <span data-ttu-id="d79fc-122">如果无法解析任何版本字符串或任何输入参数为 null，则返回 E_INVALIDARG。</span><span class="sxs-lookup"><span data-stu-id="d79fc-122">Returns E_INVALIDARG if it fails to parse any of the version strings or any input parameter is null.</span></span> <span data-ttu-id="d79fc-123">输入可以直接使用从 GetAvailableCoreWebView2BrowserVersionString 获取的 versionInfo，信道信息将被忽略。</span><span class="sxs-lookup"><span data-stu-id="d79fc-123">Input can directly use the versionInfo obtained from GetAvailableCoreWebView2BrowserVersionString, channel info will be ignored.</span></span>

#### <span data-ttu-id="d79fc-124">CreateCoreWebView2Environment</span><span class="sxs-lookup"><span data-stu-id="d79fc-124">CreateCoreWebView2Environment</span></span> 

> <span data-ttu-id="d79fc-125">公共 STDAPI [CreateCoreWebView2Environment](#createcorewebview2environment) (ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler \* environmentCreatedHandler) </span><span class="sxs-lookup"><span data-stu-id="d79fc-125">public STDAPI [CreateCoreWebView2Environment](#createcorewebview2environment)(ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler \* environmentCreatedHandler)</span></span>

<span data-ttu-id="d79fc-126">使用安装的边缘版本创建长绿 WebView2 环境。</span><span class="sxs-lookup"><span data-stu-id="d79fc-126">Creates an evergreen WebView2 Environment using the installed Edge version.</span></span>

<span data-ttu-id="d79fc-127">这等效于对 browserExecutableFolder、userDataFolder、additionalBrowserArguments 调用 nullptr 的 CreateCoreWebView2EnvironmentWithOptions。</span><span class="sxs-lookup"><span data-stu-id="d79fc-127">This is equivalent to calling CreateCoreWebView2EnvironmentWithOptions with nullptr for browserExecutableFolder, userDataFolder, additionalBrowserArguments.</span></span> <span data-ttu-id="d79fc-128">有关详细信息，请参阅 CreateCoreWebView2EnvironmentWithOptions。</span><span class="sxs-lookup"><span data-stu-id="d79fc-128">See CreateCoreWebView2EnvironmentWithOptions for more details.</span></span>

#### <span data-ttu-id="d79fc-129">CreateCoreWebView2EnvironmentWithOptions</span><span class="sxs-lookup"><span data-stu-id="d79fc-129">CreateCoreWebView2EnvironmentWithOptions</span></span> 

> <span data-ttu-id="d79fc-130">public STDAPI [CreateCoreWebView2EnvironmentWithOptions](#createcorewebview2environmentwithoptions) (PCWSTR BROWSEREXECUTABLEFOLDER、PCWSTR UserDataFolder、 [ICoreWebView2EnvironmentOptions](icorewebview2environmentoptions.md) [\* environmentOptions、ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler](icorewebview2createcorewebview2environmentcompletedhandler.md) \* environmentCreatedHandler) </span><span class="sxs-lookup"><span data-stu-id="d79fc-130">public STDAPI [CreateCoreWebView2EnvironmentWithOptions](#createcorewebview2environmentwithoptions)(PCWSTR browserExecutableFolder, PCWSTR userDataFolder, [ICoreWebView2EnvironmentOptions](icorewebview2environmentoptions.md) \* environmentOptions, [ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler](icorewebview2createcorewebview2environmentcompletedhandler.md) \* environmentCreatedHandler)</span></span>

<span data-ttu-id="d79fc-131">DLL 导出以使用自定义版本的 Edge、用户数据目录和/或其他选项创建 WebView2 环境。</span><span class="sxs-lookup"><span data-stu-id="d79fc-131">DLL export to create a WebView2 environment with a custom version of Edge, user data directory and/or additional options.</span></span>

<span data-ttu-id="d79fc-132">WebView2 环境和所有其他 WebView2 对象都是单线程的，并且在需要为单线程单元初始化 COM 的 Windows 组件上具有依赖关系。</span><span class="sxs-lookup"><span data-stu-id="d79fc-132">The WebView2 environment and all other WebView2 objects are single threaded and have dependencies on Windows components that require COM to be initialized for a single-threaded apartment.</span></span> <span data-ttu-id="d79fc-133">在调用 CreateCoreWebView2EnvironmentWithOptions 之前，应用程序应调用 CoInitializeEx。</span><span class="sxs-lookup"><span data-stu-id="d79fc-133">The application is expected to call CoInitializeEx before calling CreateCoreWebView2EnvironmentWithOptions.</span></span>

```
CoInitializeEx(nullptr, COINIT_APARTMENTTHREADED);
```

<span data-ttu-id="d79fc-134">如果 CoInitializeEx 未被调用或以前用 COINIT_MULTITHREADED 调用，CreateCoreWebView2EnvironmentWithOptions 将失败，并出现以下错误之一。</span><span class="sxs-lookup"><span data-stu-id="d79fc-134">If CoInitializeEx was not called or has been previously called with COINIT_MULTITHREADED, CreateCoreWebView2EnvironmentWithOptions will fail with one of the following errors.</span></span>

```
CO_E_NOTINITIALIZED (if CoInitializeEx was not called)
RPC_E_CHANGED_MODE  (if CoInitializeEx was previously called with
                     COINIT_MULTITHREADED)
```

<span data-ttu-id="d79fc-135">用于 `browserExecutableFolder` 指定 WebView2 控件使用的是 WebView2 运行库的固定或已安装版本，该版本存在于客户端计算机上。</span><span class="sxs-lookup"><span data-stu-id="d79fc-135">Use `browserExecutableFolder` to specify whether WebView2 controls use a fixed or installed version of the WebView2 Runtime that exists on a client machine.</span></span> <span data-ttu-id="d79fc-136">若要使用 WebView2 运行时的固定版本，请将包含 WebView2 运行时的固定版本的文件夹的相对路径传递给 `browserExecutableFolder` 。</span><span class="sxs-lookup"><span data-stu-id="d79fc-136">To use a fixed version of the WebView2 Runtime, pass the relative path of the folder that contains the fixed version of the WebView2 Runtime to `browserExecutableFolder`.</span></span> <span data-ttu-id="d79fc-137">若要创建使用客户端计算机上存在的 WebView2 运行时的已安装版本的 WebView2 控件，请将 null 或空字符串传递给 `browserExecutableFolder` 。</span><span class="sxs-lookup"><span data-stu-id="d79fc-137">To create WebView2 controls that use the installed version of the WebView2 Runtime that exists on client machines, pass a null or empty string to `browserExecutableFolder`.</span></span> <span data-ttu-id="d79fc-138">在此方案中，API 尝试查找客户端计算机上安装的 WebView2 运行时的兼容版本， (首先在计算机级别，然后按用户) 使用所选的通道首选项。</span><span class="sxs-lookup"><span data-stu-id="d79fc-138">In this scenario, the API tries to find a compatible version of the WebView2 Runtime that is installed on the client machine (first at the machine level, and then per user) using the selected channel preference.</span></span> <span data-ttu-id="d79fc-139">WebView2 运行时的固定版本的路径不应包含 `\Edge\Application\` 。</span><span class="sxs-lookup"><span data-stu-id="d79fc-139">The path of fixed version of the WebView2 Runtime should not contain `\Edge\Application\`.</span></span> <span data-ttu-id="d79fc-140">使用此类路径时，API 将失败，并 ERROR_NOT_SUPPORTED。</span><span class="sxs-lookup"><span data-stu-id="d79fc-140">When such a path is used, the API will fail with ERROR_NOT_SUPPORTED.</span></span>

<span data-ttu-id="d79fc-141">默认频道搜索顺序为 WebView2 运行时、Beta、开发和 ""。</span><span class="sxs-lookup"><span data-stu-id="d79fc-141">The default channel search order is the WebView2 Runtime, Beta, Dev, and Canary.</span></span> <span data-ttu-id="d79fc-142">如果存在替代值 WEBVIEW2_RELEASE_CHANNEL_PREFERENCE 环境变量或适用的 releaseChannelPreference 注册表值为1，则将反转频道搜索顺序。</span><span class="sxs-lookup"><span data-stu-id="d79fc-142">When there is an override WEBVIEW2_RELEASE_CHANNEL_PREFERENCE environment variable or applicable releaseChannelPreference registry value with the value of 1, the channel search order is reversed.</span></span>

<span data-ttu-id="d79fc-143">可以指定 userDataFolder 以更改 WebView2 的默认用户数据文件夹位置。</span><span class="sxs-lookup"><span data-stu-id="d79fc-143">userDataFolder can be specified to change the default user data folder location for WebView2.</span></span> <span data-ttu-id="d79fc-144">路径可以是绝对文件路径或解释为相对于当前进程的可执行文件的相对文件路径。</span><span class="sxs-lookup"><span data-stu-id="d79fc-144">The path can be an absolute file path or a relative file path that is interpreted as relative to the current process's executable.</span></span> <span data-ttu-id="d79fc-145">否则，对于 UWP 应用，默认的用户数据文件夹将是程序包的应用数据文件夹;对于非 UWP 应用， `{Executable File Name}.WebView2` 将在应用可执行文件旁边的同一目录中创建默认的用户数据文件夹。</span><span class="sxs-lookup"><span data-stu-id="d79fc-145">Otherwise, for UWP apps, the default user data folder will be the app data folder for the package; for non-UWP apps, the default user data folder `{Executable File Name}.WebView2` will be created in the same directory next to the app executable.</span></span> <span data-ttu-id="d79fc-146">如果可执行文件在进程没有在其中创建新文件夹的权限的目录中运行，WebView2 创建可能失败。</span><span class="sxs-lookup"><span data-stu-id="d79fc-146">WebView2 creation can fail if the executable is running in a directory that the process doesn't have permission to create a new folder in.</span></span> <span data-ttu-id="d79fc-147">应用负责清理已完成的用户数据文件夹。</span><span class="sxs-lookup"><span data-stu-id="d79fc-147">The app is responsible to clean up its user data folder when it is done.</span></span>

<span data-ttu-id="d79fc-148">请注意，作为浏览器进程可能在 WebViews 之间共享，如果指定的选项与当前在共享浏览器进程中运行的 WebViews 的选项不匹配，则 Web 视图创建将失败，并使用 HRESULT_FROM_WIN32 (ERROR_INVALID_STATE) 。</span><span class="sxs-lookup"><span data-stu-id="d79fc-148">Note that as a browser process might be shared among WebViews, WebView creation will fail with HRESULT_FROM_WIN32(ERROR_INVALID_STATE) if the specified options does not match the options of the WebViews that are currently running in the shared browser process.</span></span>

<span data-ttu-id="d79fc-149">environmentCreatedHandler 是对异步操作的处理程序结果，它将包含已创建的 WebView2Environment。</span><span class="sxs-lookup"><span data-stu-id="d79fc-149">environmentCreatedHandler is the handler result to the async operation which will contain the WebView2Environment that got created.</span></span>

<span data-ttu-id="d79fc-150">EnvironmentOptions 的 browserExecutableFolder、userDataFolder 和 additionalBrowserArguments 可能由环境变量或注册表中指定的值替代。</span><span class="sxs-lookup"><span data-stu-id="d79fc-150">The browserExecutableFolder, userDataFolder and additionalBrowserArguments of the environmentOptions may be overridden by values either specified in environment variables or in the registry.</span></span>

<span data-ttu-id="d79fc-151">创建 WebView2Environment 时，将选中以下环境变量：</span><span class="sxs-lookup"><span data-stu-id="d79fc-151">When creating a WebView2Environment the following environment variables are checked:</span></span>

```
WEBVIEW2_BROWSER_EXECUTABLE_FOLDER
WEBVIEW2_USER_DATA_FOLDER
WEBVIEW2_ADDITIONAL_BROWSER_ARGUMENTS
WEBVIEW2_RELEASE_CHANNEL_PREFERENCE
```

<span data-ttu-id="d79fc-152">如果找到替代环境变量，则使用 browserExecutableFolder 和 userDataFolder 值作为 CreateCoreWebView2EnvironmentWithOptions 参数中对应值的替换项。</span><span class="sxs-lookup"><span data-stu-id="d79fc-152">If an override environment variable is found then we use the browserExecutableFolder and userDataFolder values as replacements for the corresponding values in CreateCoreWebView2EnvironmentWithOptions parameters.</span></span> <span data-ttu-id="d79fc-153">如果 additionalBrowserArguments 在环境变量或注册表中指定，它将追加到 CreateCoreWebView2EnvironmentWithOptions 参数中的 correspinding 值。</span><span class="sxs-lookup"><span data-stu-id="d79fc-153">If additionalBrowserArguments specified in environment variable or in the registry, it will be appended to the correspinding values in CreateCoreWebView2EnvironmentWithOptions parameters.</span></span>

<span data-ttu-id="d79fc-154">虽然并非严格替代，但也存在可设置的其他环境变量：</span><span class="sxs-lookup"><span data-stu-id="d79fc-154">While not strictly overrides, there exists additional environment variables that can be set:</span></span>

```
WEBVIEW2_WAIT_FOR_SCRIPT_DEBUGGER
```

<span data-ttu-id="d79fc-155">当发现具有非空值时，这表示 Web 视图正在脚本调试程序下启动。</span><span class="sxs-lookup"><span data-stu-id="d79fc-155">When found with a non-empty value, this indicates that the WebView is being launched under a script debugger.</span></span> <span data-ttu-id="d79fc-156">在这种情况下，Web 视图将发出 `Page.waitForDebugger` CDP 命令，该命令将导致 Web 视图内的脚本执行在启动时暂停，直到调试器发出相应 `Runtime.runIfWaitingForDebugger` 的 CDP 命令以继续执行。</span><span class="sxs-lookup"><span data-stu-id="d79fc-156">In this case, the WebView will issue a `Page.waitForDebugger` CDP command that will cause script execution inside the WebView to pause on launch, until a debugger issues a corresponding `Runtime.runIfWaitingForDebugger` CDP command to resume execution.</span></span> <span data-ttu-id="d79fc-157">注意：此环境变量没有等效的注册表项。</span><span class="sxs-lookup"><span data-stu-id="d79fc-157">Note: There is no registry key equivalent of this environment variable.</span></span>

```
WEBVIEW2_PIPE_FOR_SCRIPT_DEBUGGER
```

<span data-ttu-id="d79fc-158">当发现具有非空值时，这表示 Web 视图正在脚本调试程序下启动，该调试程序还支持使用多个 WebViews 的主机应用程序。</span><span class="sxs-lookup"><span data-stu-id="d79fc-158">When found with a non-empty value, this indicates that the WebView is being launched under a script debugger that also supports host applications that use multiple WebViews.</span></span> <span data-ttu-id="d79fc-159">该值用作命名管道的标识符，该管道将在由宿主应用程序创建新的 Web 视图时打开并写入。</span><span class="sxs-lookup"><span data-stu-id="d79fc-159">The value is used as the identifier for a named pipe that will be opened and written to when a new WebView is created by the host application.</span></span> <span data-ttu-id="d79fc-160">负载将与远程调试端口 JSON 目标的负载匹配，并可供外部调试器用于附加到特定的 Web 视图实例。</span><span class="sxs-lookup"><span data-stu-id="d79fc-160">The payload will match that of the remote-debugging-port JSON target and can be used by the external debugger to attach to a specific WebView instance.</span></span> <span data-ttu-id="d79fc-161">调试器创建的管道的格式应该是： `\\.\pipe\WebView2\Debugger\{app_name}\{pipe_name}` where：</span><span class="sxs-lookup"><span data-stu-id="d79fc-161">The format of the pipe created by the debugger should be: `\\.\pipe\WebView2\Debugger\{app_name}\{pipe_name}` where:</span></span>

* `{app_name}` <span data-ttu-id="d79fc-162">是主机应用程序 exe 文件名，例如 WebView2Example.exe</span><span class="sxs-lookup"><span data-stu-id="d79fc-162">is the host application exe filename, e.g. WebView2Example.exe</span></span>

* `{pipe_name}` <span data-ttu-id="d79fc-163">是为 WEBVIEW2_PIPE_FOR_SCRIPT_DEBUGGER 设置的值。</span><span class="sxs-lookup"><span data-stu-id="d79fc-163">is the value set for WEBVIEW2_PIPE_FOR_SCRIPT_DEBUGGER.</span></span>

<span data-ttu-id="d79fc-164">若要启用由 JSON 标识的目标的调试，你还需要设置 WEBVIEW2_ADDITIONAL_BROWSER_ARGUMENTS 环境变量以将其发送到 `--remote-debugging-port={port_num}` ：</span><span class="sxs-lookup"><span data-stu-id="d79fc-164">To enable debugging of the targets identified by the JSON you will also need to set the WEBVIEW2_ADDITIONAL_BROWSER_ARGUMENTS environment variable to send `--remote-debugging-port={port_num}` where:</span></span>

* `{port_num}` <span data-ttu-id="d79fc-165">是 CDP 服务器将绑定到的端口。</span><span class="sxs-lookup"><span data-stu-id="d79fc-165">is the port on which the CDP server will bind.</span></span>

<span data-ttu-id="d79fc-166">请注意，设置 WEBVIEW2_PIPE_FOR_SCRIPT_DEBUGGER 和 WEBVIEW2_ADDITIONAL_BROWSER_ARGUMENTS 环境变量将导致应用程序中托管的 WebViews 以及它们的内容将向第三方应用程序（如调试器）公开。</span><span class="sxs-lookup"><span data-stu-id="d79fc-166">Be aware that setting both the WEBVIEW2_PIPE_FOR_SCRIPT_DEBUGGER and WEBVIEW2_ADDITIONAL_BROWSER_ARGUMENTS environment variables will cause the WebViews hosted in your application and their contents to be exposed to 3rd party applications such as debuggers.</span></span>

<span data-ttu-id="d79fc-167">注意：此环境变量没有等效的注册表项。</span><span class="sxs-lookup"><span data-stu-id="d79fc-167">Note: There is no registry key equivalent of this environment variable.</span></span>

<span data-ttu-id="d79fc-168">如果这些环境变量都不存在，则下一步检查注册表。</span><span class="sxs-lookup"><span data-stu-id="d79fc-168">If none of those environment variables exist, then the registry is examined next.</span></span> <span data-ttu-id="d79fc-169">下列注册表值已选中：</span><span class="sxs-lookup"><span data-stu-id="d79fc-169">The following registry values are checked:</span></span>

```
[{Root}]\Software\Policies\Microsoft\Edge\WebView2\browserExecutableFolder
"{AppId}"=""

[{Root}]\Software\Policies\Microsoft\Edge\WebView2\releaseChannelPreference
"{AppId}"=""

[{Root}]\Software\Policies\Microsoft\Edge\WebView2\additionalBrowserArguments
"{AppId}"=""

[{Root}]\Software\Policies\Microsoft\Edge\WebView2\userDataFolder
"{AppId}"=""
```

<span data-ttu-id="d79fc-170">browserExecutableFolder 和 releaseChannelPreference 可以使用 "管理模板" 下的组策略进行配置，> Microsoft Edge WebView2。</span><span class="sxs-lookup"><span data-stu-id="d79fc-170">browserExecutableFolder and releaseChannelPreference can be configured using group policy under Administrative Templates > Microsoft Edge WebView2.</span></span> <span data-ttu-id="d79fc-171">旧的注册表位置将很快被弃用：</span><span class="sxs-lookup"><span data-stu-id="d79fc-171">The old registry location will be deprecated soon:</span></span>

```
[{Root}\Software\Policies\Microsoft\EmbeddedBrowserWebView\LoaderOverride\{AppId}]
"releaseChannelPreference"=dword:00000000
"browserExecutableFolder"=""
"userDataFolder"=""
"additionalBrowserArguments"=""
```

<span data-ttu-id="d79fc-172">在浏览器更新期间打开某些 Web 视图实例的不需要的情况下，我们最终会阻止删除旧的边缘浏览器。</span><span class="sxs-lookup"><span data-stu-id="d79fc-172">In the unlikely scenario where some instances of WebView are open during a browser update we could end up blocking the deletion of old Edge browsers.</span></span> <span data-ttu-id="d79fc-173">为避免用尽磁盘空间，如果新的 Web 视图创建会在检测到存在许多旧版本的情况下失败，并显示下一个错误。</span><span class="sxs-lookup"><span data-stu-id="d79fc-173">To avoid running out of disk space a new WebView creation will fail with the next error if it detects that there are many old versions present.</span></span>

```
ERROR_DISK_FULL
```

<span data-ttu-id="d79fc-174">允许的默认最大边缘版本数为20。</span><span class="sxs-lookup"><span data-stu-id="d79fc-174">The default maximum number of Edge versions allowed is 20.</span></span>

<span data-ttu-id="d79fc-175">可以使用以下环境变量的值覆盖所允许的旧边缘版本的最大数量。</span><span class="sxs-lookup"><span data-stu-id="d79fc-175">The maximum number of old Edge versions allowed can be overwritten with the value of the following environment variable.</span></span>

```
WEBVIEW2_MAX_INSTANCES
```

<span data-ttu-id="d79fc-176">如果 Web 视图依赖于已安装的边缘，并且卸载后任何后续创建都将失败，并出现下一个错误</span><span class="sxs-lookup"><span data-stu-id="d79fc-176">If the Webview depends on an installed Edge and it is uninstalled any subsequent creation will fail with the next error</span></span>

```
ERROR_PRODUCT_UNINSTALLED
```

<span data-ttu-id="d79fc-177">首先，我们检查 Root 是 HKLM，然后是 HKCU。</span><span class="sxs-lookup"><span data-stu-id="d79fc-177">First we check with Root as HKLM and then HKCU.</span></span> <span data-ttu-id="d79fc-178">AppId 首先设置为应用程序用户模型 ID （调用方的进程），如果没有相应的注册表项，则将 AppId 设置为调用方的进程的可执行名称，或者，如果不是注册表项，则为 "\*"。</span><span class="sxs-lookup"><span data-stu-id="d79fc-178">AppId is first set to the Application User Model ID of the caller's process, then if there's no corresponding registry key the AppId is set to the executable name of the caller's process, or if that isn't a registry key then '\*'.</span></span> <span data-ttu-id="d79fc-179">如果找到替代注册表项，则使用 browserExecutableFolder 和 userDataFolder 注册表值作为替换项，并为 CreateCoreWebView2EnvironmentWithOptions 参数中的相应值追加 additionalBrowserArguments 注册表值。</span><span class="sxs-lookup"><span data-stu-id="d79fc-179">If an override registry key is found, then we use the browserExecutableFolder and userDataFolder registry values as replacements and append additionalBrowserArguments registry values for the corresponding values in CreateCoreWebView2EnvironmentWithOptions parameters.</span></span>

#### <span data-ttu-id="d79fc-180">GetAvailableCoreWebView2BrowserVersionString</span><span class="sxs-lookup"><span data-stu-id="d79fc-180">GetAvailableCoreWebView2BrowserVersionString</span></span> 

> <span data-ttu-id="d79fc-181">公共 STDAPI [GetAvailableCoreWebView2BrowserVersionString](#getavailablecorewebview2browserversionstring) (PCWSTR BROWSEREXECUTABLEFOLDER，LPWSTR \* versionInfo) </span><span class="sxs-lookup"><span data-stu-id="d79fc-181">public STDAPI [GetAvailableCoreWebView2BrowserVersionString](#getavailablecorewebview2browserversionstring)(PCWSTR browserExecutableFolder, LPWSTR \* versionInfo)</span></span>

<span data-ttu-id="d79fc-182">获取包含频道名称的浏览器版本信息（如果不是稳定通道或嵌入边缘）。</span><span class="sxs-lookup"><span data-stu-id="d79fc-182">Get the browser version info including channel name if it is not the stable channel or the Embedded Edge.</span></span>

<span data-ttu-id="d79fc-183">频道名称是 beta 版、开发人员和未带了设备。</span><span class="sxs-lookup"><span data-stu-id="d79fc-183">Channel names are beta, dev, and canary.</span></span> <span data-ttu-id="d79fc-184">如果 browserExecutableFolder 或通道首选项存在替代，将使用替代。</span><span class="sxs-lookup"><span data-stu-id="d79fc-184">If an override exists for the browserExecutableFolder or the channel preference, the override will be used.</span></span> <span data-ttu-id="d79fc-185">如果没有替代，则使用传递到 GetAvailableCoreWebView2BrowserVersionString 的参数。</span><span class="sxs-lookup"><span data-stu-id="d79fc-185">If there isn't an override, then the parameter passed to GetAvailableCoreWebView2BrowserVersionString is used.</span></span>

