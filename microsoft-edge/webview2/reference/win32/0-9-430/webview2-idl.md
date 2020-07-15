---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.430-WebView2 Win32 c + + 全局
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 9adad4fa65a2082f1fd4b25009f5c1e0d0c953a3
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10877747"
---
# <span data-ttu-id="d85fd-104">0.9.430-Globals</span><span class="sxs-lookup"><span data-stu-id="d85fd-104">0.9.430 - Globals</span></span> 

> [!NOTE]
> <span data-ttu-id="d85fd-105">此接口可能会在 SDK 版本0.9.430 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="d85fd-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="d85fd-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="d85fd-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

## <span data-ttu-id="d85fd-107">摘要</span><span class="sxs-lookup"><span data-stu-id="d85fd-107">Summary</span></span>

 <span data-ttu-id="d85fd-108">成员</span><span class="sxs-lookup"><span data-stu-id="d85fd-108">Members</span></span>                        | <span data-ttu-id="d85fd-109">描述</span><span class="sxs-lookup"><span data-stu-id="d85fd-109">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="d85fd-110">CreateCoreWebView2EnvironmentWithDetails</span><span class="sxs-lookup"><span data-stu-id="d85fd-110">CreateCoreWebView2EnvironmentWithDetails</span></span>](#createcorewebview2environmentwithdetails) | <span data-ttu-id="d85fd-111">DLL 导出以使用自定义版本的 Edge、用户数据目录和/或其他浏览器开关创建 WebView2 环境。</span><span class="sxs-lookup"><span data-stu-id="d85fd-111">DLL export to create a WebView2 environment with a custom version of Edge, user data directory and/or additional browser switches.</span></span>
[<span data-ttu-id="d85fd-112">CreateCoreWebView2Environment</span><span class="sxs-lookup"><span data-stu-id="d85fd-112">CreateCoreWebView2Environment</span></span>](#createcorewebview2environment) | <span data-ttu-id="d85fd-113">使用安装的边缘版本创建长绿 WebView2 环境。</span><span class="sxs-lookup"><span data-stu-id="d85fd-113">Creates an evergreen WebView2 Environment using the installed Edge version.</span></span>
[<span data-ttu-id="d85fd-114">GetCoreWebView2BrowserVersionInfo</span><span class="sxs-lookup"><span data-stu-id="d85fd-114">GetCoreWebView2BrowserVersionInfo</span></span>](#getcorewebview2browserversioninfo) | <span data-ttu-id="d85fd-115">获取包含频道名称的浏览器版本信息（如果不是稳定通道或嵌入边缘）。</span><span class="sxs-lookup"><span data-stu-id="d85fd-115">Get the browser version info including channel name if it is not the stable channel or the Embedded Edge.</span></span>
[<span data-ttu-id="d85fd-116">CompareBrowserVersions</span><span class="sxs-lookup"><span data-stu-id="d85fd-116">CompareBrowserVersions</span></span>](#comparebrowserversions) | <span data-ttu-id="d85fd-117">此方法适用于任何人都希望正确比较版本以确定哪个版本较旧、更旧或相同。</span><span class="sxs-lookup"><span data-stu-id="d85fd-117">This method is for anyone want to compare version correctly to determine which version is newer, older or same.</span></span>

## <span data-ttu-id="d85fd-118">成员</span><span class="sxs-lookup"><span data-stu-id="d85fd-118">Members</span></span>

#### <span data-ttu-id="d85fd-119">CreateCoreWebView2EnvironmentWithDetails</span><span class="sxs-lookup"><span data-stu-id="d85fd-119">CreateCoreWebView2EnvironmentWithDetails</span></span> 

> <span data-ttu-id="d85fd-120">公共 STDAPI [CreateCoreWebView2EnvironmentWithDetails](#createcorewebview2environmentwithdetails)（PCWSTR BROWSEREXECUTABLEFOLDER、PCWSTR USERDATAFOLDER、PCWSTR additionalBrowserArguments、[ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler \* environment_created_handler](ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler.md) ）</span><span class="sxs-lookup"><span data-stu-id="d85fd-120">public STDAPI [CreateCoreWebView2EnvironmentWithDetails](#createcorewebview2environmentwithdetails)(PCWSTR browserExecutableFolder,PCWSTR userDataFolder,PCWSTR additionalBrowserArguments,[ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler](ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler.md) \* environment_created_handler)</span></span>

<span data-ttu-id="d85fd-121">DLL 导出以使用自定义版本的 Edge、用户数据目录和/或其他浏览器开关创建 WebView2 环境。</span><span class="sxs-lookup"><span data-stu-id="d85fd-121">DLL export to create a WebView2 environment with a custom version of Edge, user data directory and/or additional browser switches.</span></span>

<span data-ttu-id="d85fd-122">browserExecutableFolder 是包含嵌入边缘的文件夹的相对路径。</span><span class="sxs-lookup"><span data-stu-id="d85fd-122">browserExecutableFolder is the relative path to the folder that contains the embedded Edge.</span></span> <span data-ttu-id="d85fd-123">可以通过复制已安装边缘的命名文件夹的版本（如已安装的73.0.52.0 边缘的73.0.52.0 子文件夹）来获取嵌入的边缘。</span><span class="sxs-lookup"><span data-stu-id="d85fd-123">The embedded Edge can be obtained by copying the version named folder of an installed Edge, like 73.0.52.0 sub folder of an installed 73.0.52.0 Edge.</span></span> <span data-ttu-id="d85fd-124">文件夹应具有 msedge.exe、msedge.dll 等。为 browserExecutableFolder 使用 null 或空字符串，以使用计算机上安装的 Edge 创建 Web 视图，在这种情况下，API 将根据通道首选项尝试查找在计算机上安装的边缘兼容版本。</span><span class="sxs-lookup"><span data-stu-id="d85fd-124">The folder should have msedge.exe, msedge.dll, etc. Use null or empty string for browserExecutableFolder to create WebView using Edge installed on the machine, in which case the API will try to find a compatible version of Edge installed on the machine according to the channel preference trying to find first per user install and then per machine install.</span></span>

<span data-ttu-id="d85fd-125">默认通道搜索顺序为稳定、beta、dev 和未固定。</span><span class="sxs-lookup"><span data-stu-id="d85fd-125">The default channel search order is stable, beta, dev, and canary.</span></span> <span data-ttu-id="d85fd-126">如果存在替代值 WEBVIEW2_RELEASE_CHANNEL_PREFERENCE 环境变量或适用的 releaseChannelPreference 注册表值为1，则将反转频道搜索顺序。</span><span class="sxs-lookup"><span data-stu-id="d85fd-126">When there is an override WEBVIEW2_RELEASE_CHANNEL_PREFERENCE environment variable or applicable releaseChannelPreference registry value with the value of 1, the channel search order is reversed.</span></span>

<span data-ttu-id="d85fd-127">可以指定 userDataFolder 以更改 WebView2 的默认用户数据文件夹位置。</span><span class="sxs-lookup"><span data-stu-id="d85fd-127">userDataFolder can be specified to change the default user data folder location for WebView2.</span></span> <span data-ttu-id="d85fd-128">路径可以是绝对文件路径或解释为相对于当前进程的可执行文件的相对文件路径。</span><span class="sxs-lookup"><span data-stu-id="d85fd-128">The path can be an absolute file path or a relative file path that is interpreted as relative to the current process's executable.</span></span> <span data-ttu-id="d85fd-129">否则，对于 UWP 应用，默认的用户数据文件夹将是程序包的应用数据文件夹;对于非 UWP 应用， `{Executable File Name}.WebView2` 将在应用可执行文件旁边的同一目录中创建默认的用户数据文件夹。</span><span class="sxs-lookup"><span data-stu-id="d85fd-129">Otherwise, for UWP apps, the default user data folder will be the app data folder for the package; for non-UWP apps, the default user data folder `{Executable File Name}.WebView2` will be created in the same directory next to the app executable.</span></span> <span data-ttu-id="d85fd-130">如果可执行文件在进程没有在其中创建新文件夹的权限的目录中运行，WebView2 创建可能失败。</span><span class="sxs-lookup"><span data-stu-id="d85fd-130">WebView2 creation can fail if the executable is running in a directory that the process doesn't have permission to create a new folder in.</span></span> <span data-ttu-id="d85fd-131">应用负责清理已完成的用户数据文件夹。</span><span class="sxs-lookup"><span data-stu-id="d85fd-131">The app is responsible to clean up its user data folder when it is done.</span></span>

<span data-ttu-id="d85fd-132">可以指定 additionalBrowserArguments 以更改 Web 视图的行为。</span><span class="sxs-lookup"><span data-stu-id="d85fd-132">additionalBrowserArguments can be specified to change the behavior of the WebView.</span></span> <span data-ttu-id="d85fd-133">这些内容将作为命令行的一部分传递到浏览器进程。</span><span class="sxs-lookup"><span data-stu-id="d85fd-133">These will be passed to the browser process as part of the command line.</span></span> <span data-ttu-id="d85fd-134">有关命令行开关的详细信息，请参阅[用标志运行 Chromium](https://aka.ms/RunChromiumWithFlags) ，了解如何切换到浏览器进程。</span><span class="sxs-lookup"><span data-stu-id="d85fd-134">See [Run Chromium with Flags](https://aka.ms/RunChromiumWithFlags) for more information about command line switches to browser process.</span></span> <span data-ttu-id="d85fd-135">如果使用命令行开关启动应用 `--edge-webview-switches=xxx` ，则该开关的值（上面示例中的 xxx）也将追加到浏览器进程命令行。</span><span class="sxs-lookup"><span data-stu-id="d85fd-135">If the app is launched with a command line switch `--edge-webview-switches=xxx` the value of that switch (xxx in the above example) will also be appended to the browser process command line.</span></span> <span data-ttu-id="d85fd-136">某些交换机（如 `--user-data-dir` 内部）和对 Web 视图来说很重要。</span><span class="sxs-lookup"><span data-stu-id="d85fd-136">Certain switches like `--user-data-dir` are internal and important to WebView.</span></span> <span data-ttu-id="d85fd-137">即使指定，这些开关也将被忽略。</span><span class="sxs-lookup"><span data-stu-id="d85fd-137">Those switches will be ignored even if specified.</span></span> <span data-ttu-id="d85fd-138">如果多次指定同一开关，则最后一个参数将获胜。</span><span class="sxs-lookup"><span data-stu-id="d85fd-138">If the same switches are specified multiple times, the last one wins.</span></span> <span data-ttu-id="d85fd-139">请注意，这也适用于交换机，如 `--enable-features` 。</span><span class="sxs-lookup"><span data-stu-id="d85fd-139">Note that this also applies to switches like `--enable-features`.</span></span> <span data-ttu-id="d85fd-140">不会尝试合并同一开关的不同值。</span><span class="sxs-lookup"><span data-stu-id="d85fd-140">There is no attempt to merge the different values of the same switch.</span></span> <span data-ttu-id="d85fd-141">在 `--edge-webview-switches` 处理 additionalBrowserArguments 参数后，将处理应用进程的命令行值。</span><span class="sxs-lookup"><span data-stu-id="d85fd-141">App process's command line `--edge-webview-switches` value are processed after the additionalBrowserArguments parameter is processed.</span></span> <span data-ttu-id="d85fd-142">另请注意，由于浏览器进程可能在 WebViews 之间共享，因此不保证应用，除非启动浏览器进程的第一个 Web 视图除外。</span><span class="sxs-lookup"><span data-stu-id="d85fd-142">Also note that as a browser process might be shared among WebViews, the switches are not guaranteed to be applied except for the first WebView that starts the browser process.</span></span> <span data-ttu-id="d85fd-143">如果指定开关的分析失败，则将忽略它们。</span><span class="sxs-lookup"><span data-stu-id="d85fd-143">If parsing failed for the specified switches, they will be ignored.</span></span> `nullptr` <span data-ttu-id="d85fd-144">将不带任何标志运行浏览器进程。</span><span class="sxs-lookup"><span data-stu-id="d85fd-144">will run browser process with no flags.</span></span>

<span data-ttu-id="d85fd-145">environment_created_handler 是对异步操作的处理程序结果，该操作将包含已创建的 WebView2Environment。</span><span class="sxs-lookup"><span data-stu-id="d85fd-145">environment_created_handler is the handler result to the async operation which will contain the WebView2Environment that got created.</span></span>

<span data-ttu-id="d85fd-146">EnvironmentParams 的 browserExecutableFolder、userDataFolder 和 additionalBrowserArguments 成员可能会被在环境变量或注册表中指定的值覆盖。</span><span class="sxs-lookup"><span data-stu-id="d85fd-146">The browserExecutableFolder, userDataFolder and additionalBrowserArguments members of the environmentParams may be overridden by values either specified in environment variables or in the registry.</span></span>

<span data-ttu-id="d85fd-147">创建 WebView2Environment 时，将选中以下环境变量：</span><span class="sxs-lookup"><span data-stu-id="d85fd-147">When creating a WebView2Environment the following environment variables are checked:</span></span>

```cpp
WEBVIEW2_BROWSER_EXECUTABLE_FOLDER
WEBVIEW2_USER_DATA_FOLDER
WEBVIEW2_ADDITIONAL_BROWSER_ARGUMENTS
WEBVIEW2_RELEASE_CHANNEL_PREFERENCE
```

<span data-ttu-id="d85fd-148">如果找到替代环境变量，则使用 browserExecutableFolder、userDataFolder 和 additionalBrowserArguments 值作为 CreateCoreWebView2EnvironmentWithDetails 参数中对应值的替换项。</span><span class="sxs-lookup"><span data-stu-id="d85fd-148">If an override environment variable is found then we use the browserExecutableFolder, userDataFolder and additionalBrowserArguments values as replacements for the corresponding values in CreateCoreWebView2EnvironmentWithDetails parameters.</span></span>

<span data-ttu-id="d85fd-149">虽然并非严格替代，但也存在可设置的其他环境变量：</span><span class="sxs-lookup"><span data-stu-id="d85fd-149">While not strictly overrides, there exists additional environment variables that can be set:</span></span>

```cpp
WEBVIEW2_WAIT_FOR_SCRIPT_DEBUGGER
```

<span data-ttu-id="d85fd-150">当发现具有非空值时，这表示 Web 视图正在脚本调试程序下启动。</span><span class="sxs-lookup"><span data-stu-id="d85fd-150">When found with a non-empty value, this indicates that the WebView is being launched under a script debugger.</span></span> <span data-ttu-id="d85fd-151">在这种情况下，Web 视图将发出 `Page.waitForDebugger` CDP 命令，该命令将导致 Web 视图内的脚本执行在启动时暂停，直到调试器发出相应 `Runtime.runIfWaitingForDebugger` 的 CDP 命令以继续执行。</span><span class="sxs-lookup"><span data-stu-id="d85fd-151">In this case, the WebView will issue a `Page.waitForDebugger` CDP command that will cause script execution inside the WebView to pause on launch, until a debugger issues a corresponding `Runtime.runIfWaitingForDebugger` CDP command to resume execution.</span></span> <span data-ttu-id="d85fd-152">注意：此环境变量没有等效的注册表项。</span><span class="sxs-lookup"><span data-stu-id="d85fd-152">Note: There is no registry key equivalent of this environment variable.</span></span>

```cpp
WEBVIEW2_PIPE_FOR_SCRIPT_DEBUGGER
```

<span data-ttu-id="d85fd-153">当发现具有非空值时，这表示 Web 视图正在脚本调试程序下启动，该调试程序还支持使用多个 WebViews 的主机应用程序。</span><span class="sxs-lookup"><span data-stu-id="d85fd-153">When found with a non-empty value, this indicates that the WebView is being launched under a script debugger that also supports host applications that use multiple WebViews.</span></span> <span data-ttu-id="d85fd-154">该值用作命名管道的标识符，该管道将在由宿主应用程序创建新的 Web 视图时打开并写入。</span><span class="sxs-lookup"><span data-stu-id="d85fd-154">The value is used as the identifier for a named pipe that will be opened and written to when a new WebView is created by the host application.</span></span> <span data-ttu-id="d85fd-155">负载将与远程调试端口 JSON 目标的负载匹配，并可供外部调试器用于附加到特定的 Web 视图实例。</span><span class="sxs-lookup"><span data-stu-id="d85fd-155">The payload will match that of the remote-debugging-port JSON target and can be used by the external debugger to attach to a specific WebView instance.</span></span> <span data-ttu-id="d85fd-156">调试器创建的管道的格式应该是： `\\.\pipe\WebView2\Debugger\{app_name}\{pipe_name}` where：</span><span class="sxs-lookup"><span data-stu-id="d85fd-156">The format of the pipe created by the debugger should be: `\\.\pipe\WebView2\Debugger\{app_name}\{pipe_name}` where:</span></span>

* `{app_name}` <span data-ttu-id="d85fd-157">是主机应用程序 exe 文件名，例如 WebView2Example.exe</span><span class="sxs-lookup"><span data-stu-id="d85fd-157">is the host application exe filename, e.g. WebView2Example.exe</span></span>

* `{pipe_name}` <span data-ttu-id="d85fd-158">是为 WEBVIEW2_PIPE_FOR_SCRIPT_DEBUGGER 设置的值。</span><span class="sxs-lookup"><span data-stu-id="d85fd-158">is the value set for WEBVIEW2_PIPE_FOR_SCRIPT_DEBUGGER.</span></span>

<span data-ttu-id="d85fd-159">若要启用由 JSON 标识的目标的调试，你还需要设置 WEBVIEW2_ADDITIONAL_BROWSER_ARGUMENTS 环境变量以将其发送到 `--remote-debugging-port={port_num}` ：</span><span class="sxs-lookup"><span data-stu-id="d85fd-159">To enable debugging of the targets identified by the JSON you will also need to set the WEBVIEW2_ADDITIONAL_BROWSER_ARGUMENTS environment variable to send `--remote-debugging-port={port_num}` where:</span></span>

* `{port_num}` <span data-ttu-id="d85fd-160">是 CDP 服务器将绑定到的端口。</span><span class="sxs-lookup"><span data-stu-id="d85fd-160">is the port on which the CDP server will bind.</span></span>

<span data-ttu-id="d85fd-161">请注意，设置 WEBVIEW2_PIPE_FOR_SCRIPT_DEBUGGER 和 WEBVIEW2_ADDITIONAL_BROWSER_ARGUMENTS 环境变量将导致应用程序中托管的 WebViews 以及它们的内容将向第三方应用程序（如调试器）公开。</span><span class="sxs-lookup"><span data-stu-id="d85fd-161">Be aware that setting both the WEBVIEW2_PIPE_FOR_SCRIPT_DEBUGGER and WEBVIEW2_ADDITIONAL_BROWSER_ARGUMENTS environment variables will cause the WebViews hosted in your application and their contents to be exposed to 3rd party applications such as debuggers.</span></span>

<span data-ttu-id="d85fd-162">注意：此环境变量没有等效的注册表项。</span><span class="sxs-lookup"><span data-stu-id="d85fd-162">Note: There is no registry key equivalent of this environment variable.</span></span>

<span data-ttu-id="d85fd-163">如果这些环境变量都不存在，则下一步检查注册表。</span><span class="sxs-lookup"><span data-stu-id="d85fd-163">If none of those environment variables exist, then the registry is examined next.</span></span> <span data-ttu-id="d85fd-164">检查以下注册表项：</span><span class="sxs-lookup"><span data-stu-id="d85fd-164">The following registry keys are checked:</span></span>

```cpp
[{Root}\Software\Policies\Microsoft\EmbeddedBrowserWebView\LoaderOverride\{AppId}]
"releaseChannelPreference"=dword:00000000
"browserExecutableFolder"=""
"userDataFolder"=""
"additionalBrowserArguments"=""
```

<span data-ttu-id="d85fd-165">在浏览器更新期间打开某些 Web 视图实例的不需要的情况下，我们最终会阻止删除旧的边缘浏览器。</span><span class="sxs-lookup"><span data-stu-id="d85fd-165">In the unlikely scenario where some instances of WebView are open during a browser update we could end up blocking the deletion of old Edge browsers.</span></span> <span data-ttu-id="d85fd-166">为避免用尽磁盘空间，如果新的 Web 视图创建会在检测到存在许多旧版本的情况下失败，并显示下一个错误。</span><span class="sxs-lookup"><span data-stu-id="d85fd-166">To avoid running out of disk space a new WebView creation will fail with the next error if it detects that there are many old versions present.</span></span>

```cpp
ERROR_DISK_FULL
```

<span data-ttu-id="d85fd-167">允许的默认最大边缘版本数为20。</span><span class="sxs-lookup"><span data-stu-id="d85fd-167">The default maximum number of Edge versions allowed is 20.</span></span>

<span data-ttu-id="d85fd-168">可以使用以下环境变量的值覆盖所允许的旧边缘版本的最大数量。</span><span class="sxs-lookup"><span data-stu-id="d85fd-168">The maximum number of old Edge versions allowed can be overwritten with the value of the following environment variable.</span></span>

```cpp
WEBVIEW2_MAX_INSTANCES
```

<span data-ttu-id="d85fd-169">如果 Web 视图依赖于已安装的边缘，并且卸载后任何后续创建都将失败，并出现下一个错误</span><span class="sxs-lookup"><span data-stu-id="d85fd-169">If the Webview depends on an installed Edge and it is uninstalled any subsequent creation will fail with the next error</span></span>

```cpp
ERROR_PRODUCT_UNINSTALLED
```

<span data-ttu-id="d85fd-170">首先，我们检查 Root 是 HKLM，然后是 HKCU。</span><span class="sxs-lookup"><span data-stu-id="d85fd-170">First we check with Root as HKLM and then HKCU.</span></span> <span data-ttu-id="d85fd-171">AppId 首先设置为应用程序用户模型 ID （调用方的进程），如果没有相应的注册表项，则将 AppId 设置为调用方的进程的可执行名称，或者，如果不是注册表项，则为 "\*"。</span><span class="sxs-lookup"><span data-stu-id="d85fd-171">AppId is first set to the Application User Model ID of the caller's process, then if there's no corresponding registry key the AppId is set to the executable name of the caller's process, or if that isn't a registry key then '\*'.</span></span> <span data-ttu-id="d85fd-172">如果找到替代注册表项，则使用 browserExecutableFolder、userDataFolder 和 additionalBrowserArguments 注册表值作为 CreateCoreWebView2EnvironmentWithDetails 参数中对应值的替换项。</span><span class="sxs-lookup"><span data-stu-id="d85fd-172">If an override registry key is found then we use the browserExecutableFolder, userDataFolder and additionalBrowserArguments registry values as replacements for the corresponding values in CreateCoreWebView2EnvironmentWithDetails parameters.</span></span> <span data-ttu-id="d85fd-173">如果这些注册表值中的任何一个不存在，则使用传递到 CreateCoreWebView2Environment 的参数。</span><span class="sxs-lookup"><span data-stu-id="d85fd-173">If any of those registry values isn't present, then the parameter passed to CreateCoreWebView2Environment is used.</span></span>

#### <span data-ttu-id="d85fd-174">CreateCoreWebView2Environment</span><span class="sxs-lookup"><span data-stu-id="d85fd-174">CreateCoreWebView2Environment</span></span> 

> <span data-ttu-id="d85fd-175">公共 STDAPI [CreateCoreWebView2Environment](#createcorewebview2environment)（[ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler](ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler.md) \* environment_created_handler）</span><span class="sxs-lookup"><span data-stu-id="d85fd-175">public STDAPI [CreateCoreWebView2Environment](#createcorewebview2environment)([ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler](ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler.md) \* environment_created_handler)</span></span>

<span data-ttu-id="d85fd-176">使用安装的边缘版本创建长绿 WebView2 环境。</span><span class="sxs-lookup"><span data-stu-id="d85fd-176">Creates an evergreen WebView2 Environment using the installed Edge version.</span></span>

<span data-ttu-id="d85fd-177">这等效于对 browserExecutableFolder、userDataFolder、additionalBrowserArguments 调用 nullptr 的 CreateCoreWebView2EnvironmentWithDetails。</span><span class="sxs-lookup"><span data-stu-id="d85fd-177">This is equivalent to calling CreateCoreWebView2EnvironmentWithDetails with nullptr for browserExecutableFolder, userDataFolder, additionalBrowserArguments.</span></span> <span data-ttu-id="d85fd-178">有关详细信息，请参阅 CreateCoreWebView2EnvironmentWithDetails。</span><span class="sxs-lookup"><span data-stu-id="d85fd-178">See CreateCoreWebView2EnvironmentWithDetails for more details.</span></span>

#### <span data-ttu-id="d85fd-179">GetCoreWebView2BrowserVersionInfo</span><span class="sxs-lookup"><span data-stu-id="d85fd-179">GetCoreWebView2BrowserVersionInfo</span></span> 

> <span data-ttu-id="d85fd-180">公共 STDAPI [GetCoreWebView2BrowserVersionInfo](#getcorewebview2browserversioninfo)（PCWSTR BROWSEREXECUTABLEFOLDER，LPWSTR \* versionInfo）</span><span class="sxs-lookup"><span data-stu-id="d85fd-180">public STDAPI [GetCoreWebView2BrowserVersionInfo](#getcorewebview2browserversioninfo)(PCWSTR browserExecutableFolder,LPWSTR \* versionInfo)</span></span>

<span data-ttu-id="d85fd-181">获取包含频道名称的浏览器版本信息（如果不是稳定通道或嵌入边缘）。</span><span class="sxs-lookup"><span data-stu-id="d85fd-181">Get the browser version info including channel name if it is not the stable channel or the Embedded Edge.</span></span>

<span data-ttu-id="d85fd-182">频道名称是 beta 版、开发人员和未带了设备。</span><span class="sxs-lookup"><span data-stu-id="d85fd-182">Channel names are beta, dev, and canary.</span></span> <span data-ttu-id="d85fd-183">如果 browserExecutableFolder 或通道首选项存在替代，将使用替代。</span><span class="sxs-lookup"><span data-stu-id="d85fd-183">If an override exists for the browserExecutableFolder or the channel preference, the override will be used.</span></span> <span data-ttu-id="d85fd-184">如果没有替代，则使用传递到 GetCoreWebView2BrowserVersionInfo 的参数。</span><span class="sxs-lookup"><span data-stu-id="d85fd-184">If there isn't an override, then the parameter passed to GetCoreWebView2BrowserVersionInfo is used.</span></span>

#### <span data-ttu-id="d85fd-185">CompareBrowserVersions</span><span class="sxs-lookup"><span data-stu-id="d85fd-185">CompareBrowserVersions</span></span> 

> <span data-ttu-id="d85fd-186">公共 STDAPI [CompareBrowserVersions](#comparebrowserversions)（PCWSTR VERSION1，PCWSTR version2，int \* 结果）</span><span class="sxs-lookup"><span data-stu-id="d85fd-186">public STDAPI [CompareBrowserVersions](#comparebrowserversions)(PCWSTR version1,PCWSTR version2,int \* result)</span></span>

<span data-ttu-id="d85fd-187">此方法适用于任何人都希望正确比较版本以确定哪个版本较旧、更旧或相同。</span><span class="sxs-lookup"><span data-stu-id="d85fd-187">This method is for anyone want to compare version correctly to determine which version is newer, older or same.</span></span>

<span data-ttu-id="d85fd-188">它可用于确定是在版本上使用 webview2 还是特定功能库。</span><span class="sxs-lookup"><span data-stu-id="d85fd-188">It can be used to determine whether to use webview2 or certain feature base on version.</span></span> <span data-ttu-id="d85fd-189">如果 version1 小于、等于或大于 version2，则将结果的值设置为-1、0或1。</span><span class="sxs-lookup"><span data-stu-id="d85fd-189">Sets the value of result to -1, 0 or 1 if version1 is less than, equal or greater than version2 respectively.</span></span> <span data-ttu-id="d85fd-190">如果无法解析任何版本字符串或任何输入参数为 null，则返回 E_INVALIDARG。</span><span class="sxs-lookup"><span data-stu-id="d85fd-190">Returns E_INVALIDARG if it fails to parse any of the version strings or any input parameter is null.</span></span> <span data-ttu-id="d85fd-191">输入可以直接使用从 GetCoreWebView2BrowserVersionInfo 获取的 versionInfo，信道信息将被忽略。</span><span class="sxs-lookup"><span data-stu-id="d85fd-191">Input can directly use the versionInfo obtained from GetCoreWebView2BrowserVersionInfo, channel info will be ignored.</span></span>

