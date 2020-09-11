---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: 0.9.579-Globals
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 2c6a84a0fec68c0026fad61faa1c5ed8ed27ddd8
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11010794"
---
# <span data-ttu-id="f10f7-104">0.9.579-Globals</span><span class="sxs-lookup"><span data-stu-id="f10f7-104">0.9.579 - Globals</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

## <span data-ttu-id="f10f7-105">摘要</span><span class="sxs-lookup"><span data-stu-id="f10f7-105">Summary</span></span>

 <span data-ttu-id="f10f7-106">成员</span><span class="sxs-lookup"><span data-stu-id="f10f7-106">Members</span></span>                        | <span data-ttu-id="f10f7-107">描述</span><span class="sxs-lookup"><span data-stu-id="f10f7-107">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="f10f7-108">CompareBrowserVersions</span><span class="sxs-lookup"><span data-stu-id="f10f7-108">CompareBrowserVersions</span></span>](#comparebrowserversions) | <span data-ttu-id="f10f7-109">此方法适用于任何人都希望正确比较版本以确定哪个版本较旧、更旧或相同。</span><span class="sxs-lookup"><span data-stu-id="f10f7-109">This method is for anyone want to compare version correctly to determine which version is newer, older or same.</span></span>
[<span data-ttu-id="f10f7-110">CreateCoreWebView2Environment</span><span class="sxs-lookup"><span data-stu-id="f10f7-110">CreateCoreWebView2Environment</span></span>](#createcorewebview2environment) | <span data-ttu-id="f10f7-111">使用安装的边缘版本创建长绿 WebView2 环境。</span><span class="sxs-lookup"><span data-stu-id="f10f7-111">Creates an evergreen WebView2 Environment using the installed Edge version.</span></span>
[<span data-ttu-id="f10f7-112">CreateCoreWebView2EnvironmentWithOptions</span><span class="sxs-lookup"><span data-stu-id="f10f7-112">CreateCoreWebView2EnvironmentWithOptions</span></span>](#createcorewebview2environmentwithoptions) | <span data-ttu-id="f10f7-113">DLL 导出以使用自定义版本的 Edge、用户数据目录和/或其他选项创建 WebView2 环境。</span><span class="sxs-lookup"><span data-stu-id="f10f7-113">DLL export to create a WebView2 environment with a custom version of Edge, user data directory and/or additional options.</span></span>
[<span data-ttu-id="f10f7-114">GetAvailableCoreWebView2BrowserVersionString</span><span class="sxs-lookup"><span data-stu-id="f10f7-114">GetAvailableCoreWebView2BrowserVersionString</span></span>](#getavailablecorewebview2browserversionstring) | <span data-ttu-id="f10f7-115">获取包含频道名称的浏览器版本信息（如果不是稳定通道或嵌入边缘）。</span><span class="sxs-lookup"><span data-stu-id="f10f7-115">Get the browser version info including channel name if it is not the stable channel or the Embedded Edge.</span></span>

## <span data-ttu-id="f10f7-116">成员</span><span class="sxs-lookup"><span data-stu-id="f10f7-116">Members</span></span>

#### <span data-ttu-id="f10f7-117">CompareBrowserVersions</span><span class="sxs-lookup"><span data-stu-id="f10f7-117">CompareBrowserVersions</span></span> 

> <span data-ttu-id="f10f7-118">public STDAPI [CompareBrowserVersions](#comparebrowserversions) (PCWSTR VERSION1，PCWSTR version2，int \* 结果) </span><span class="sxs-lookup"><span data-stu-id="f10f7-118">public STDAPI [CompareBrowserVersions](#comparebrowserversions)(PCWSTR version1, PCWSTR version2, int \* result)</span></span>

<span data-ttu-id="f10f7-119">此方法适用于任何人都希望正确比较版本以确定哪个版本较旧、更旧或相同。</span><span class="sxs-lookup"><span data-stu-id="f10f7-119">This method is for anyone want to compare version correctly to determine which version is newer, older or same.</span></span>

<span data-ttu-id="f10f7-120">它可用于确定是在版本上使用 webview2 还是特定功能库。</span><span class="sxs-lookup"><span data-stu-id="f10f7-120">It can be used to determine whether to use webview2 or certain feature base on version.</span></span> <span data-ttu-id="f10f7-121">如果 version1 小于、等于或大于 version2，则将结果的值设置为-1、0或1。</span><span class="sxs-lookup"><span data-stu-id="f10f7-121">Sets the value of result to -1, 0 or 1 if version1 is less than, equal or greater than version2 respectively.</span></span> <span data-ttu-id="f10f7-122">如果无法解析任何版本字符串或任何输入参数为 null，则返回 E_INVALIDARG。</span><span class="sxs-lookup"><span data-stu-id="f10f7-122">Returns E_INVALIDARG if it fails to parse any of the version strings or any input parameter is null.</span></span> <span data-ttu-id="f10f7-123">输入可以直接使用从 GetAvailableCoreWebView2BrowserVersionString 获取的 versionInfo，信道信息将被忽略。</span><span class="sxs-lookup"><span data-stu-id="f10f7-123">Input can directly use the versionInfo obtained from GetAvailableCoreWebView2BrowserVersionString, channel info will be ignored.</span></span>

#### <span data-ttu-id="f10f7-124">CreateCoreWebView2Environment</span><span class="sxs-lookup"><span data-stu-id="f10f7-124">CreateCoreWebView2Environment</span></span> 

> <span data-ttu-id="f10f7-125">公共 STDAPI [CreateCoreWebView2Environment](#createcorewebview2environment) ([ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler](icorewebview2createcorewebview2environmentcompletedhandler.md) \* environment_created_handler) </span><span class="sxs-lookup"><span data-stu-id="f10f7-125">public STDAPI [CreateCoreWebView2Environment](#createcorewebview2environment)([ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler](icorewebview2createcorewebview2environmentcompletedhandler.md) \* environment_created_handler)</span></span>

<span data-ttu-id="f10f7-126">使用安装的边缘版本创建长绿 WebView2 环境。</span><span class="sxs-lookup"><span data-stu-id="f10f7-126">Creates an evergreen WebView2 Environment using the installed Edge version.</span></span>

<span data-ttu-id="f10f7-127">这等效于对 browserExecutableFolder、userDataFolder、additionalBrowserArguments 调用 nullptr 的 CreateCoreWebView2EnvironmentWithOptions。</span><span class="sxs-lookup"><span data-stu-id="f10f7-127">This is equivalent to calling CreateCoreWebView2EnvironmentWithOptions with nullptr for browserExecutableFolder, userDataFolder, additionalBrowserArguments.</span></span> <span data-ttu-id="f10f7-128">有关详细信息，请参阅 CreateCoreWebView2EnvironmentWithOptions。</span><span class="sxs-lookup"><span data-stu-id="f10f7-128">See CreateCoreWebView2EnvironmentWithOptions for more details.</span></span>

#### <span data-ttu-id="f10f7-129">CreateCoreWebView2EnvironmentWithOptions</span><span class="sxs-lookup"><span data-stu-id="f10f7-129">CreateCoreWebView2EnvironmentWithOptions</span></span> 

> <span data-ttu-id="f10f7-130">公共 STDAPI [CreateCoreWebView2EnvironmentWithOptions](#createcorewebview2environmentwithoptions) (PCWSTR BROWSEREXECUTABLEFOLDER、PCWSTR UserDataFolder、 [ICoreWebView2EnvironmentOptions](icorewebview2environmentoptions.md) \* [environmentOptions、ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler](icorewebview2createcorewebview2environmentcompletedhandler.md) \* environment_created_handler) </span><span class="sxs-lookup"><span data-stu-id="f10f7-130">public STDAPI [CreateCoreWebView2EnvironmentWithOptions](#createcorewebview2environmentwithoptions)(PCWSTR browserExecutableFolder, PCWSTR userDataFolder, [ICoreWebView2EnvironmentOptions](icorewebview2environmentoptions.md) \* environmentOptions, [ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler](icorewebview2createcorewebview2environmentcompletedhandler.md) \* environment_created_handler)</span></span>

<span data-ttu-id="f10f7-131">DLL 导出以使用自定义版本的 Edge、用户数据目录和/或其他选项创建 WebView2 环境。</span><span class="sxs-lookup"><span data-stu-id="f10f7-131">DLL export to create a WebView2 environment with a custom version of Edge, user data directory and/or additional options.</span></span>

<span data-ttu-id="f10f7-132">用于 `browserExecutableFolder` 指定 WebView2 控件是使用嵌入式版本的边缘，还是使用客户端计算机上存在的已安装版本的 edge。</span><span class="sxs-lookup"><span data-stu-id="f10f7-132">Use `browserExecutableFolder` to specify whether WebView2 controls use an embedded version of Edge, or the installed version of Edge that exists on a client machine.</span></span> <span data-ttu-id="f10f7-133">若要使用嵌入式版本的 Edge，请将包含嵌入式版本的边缘的文件夹的相对路径传递给 `browserExecutableFolder` 。</span><span class="sxs-lookup"><span data-stu-id="f10f7-133">To use an embedded version of Edge, pass the relative path of the folder that contains the embedded version of Edge to `browserExecutableFolder`.</span></span> <span data-ttu-id="f10f7-134">若要获取嵌入式版本的 Edge，请从客户端计算机上已安装的 Edge 版本中复制已进行版本控制的文件夹名称。</span><span class="sxs-lookup"><span data-stu-id="f10f7-134">To obtain the embedded version of Edge, copy the versioned folder name from your installed version of Edge on a client machine.</span></span> <span data-ttu-id="f10f7-135">例如， `73.0.52.0` 从安装了 Edge 版本73.0.52.0 的文件夹复制文件夹。</span><span class="sxs-lookup"><span data-stu-id="f10f7-135">For example, copy the `73.0.52.0` folder from the folder where Edge version 73.0.52.0 was installed.</span></span> <span data-ttu-id="f10f7-136">确保文件夹同时具有 " **msedgewebview2.exe** " 和 " **msedge.dll** " 文件。</span><span class="sxs-lookup"><span data-stu-id="f10f7-136">Ensure that the folder has both the **msedgewebview2.exe** and **msedge.dll** files.</span></span> <span data-ttu-id="f10f7-137">若要创建使用客户端计算机上存在的已安装版本的 Edge 的 WebView2 控件，请将 null 或空字符串传递给 `browserExecutableFolder` 。</span><span class="sxs-lookup"><span data-stu-id="f10f7-137">To create WebView2 controls that use the installed version of Edge that exists on client machines, pass a null or empty string to `browserExecutableFolder`.</span></span> <span data-ttu-id="f10f7-138">在此方案中，API 尝试查找安装在客户端计算机上的一种兼容版本， (首先在计算机级别上安装，然后按用户) 使用所选通道首选项。</span><span class="sxs-lookup"><span data-stu-id="f10f7-138">In this scenario, the API tries to find a compatible version of Edge that is installed on the client machine (first at the machine level, and then per user) using the selected channel preference.</span></span>

<span data-ttu-id="f10f7-139">默认通道搜索顺序为稳定、beta、dev 和未固定。</span><span class="sxs-lookup"><span data-stu-id="f10f7-139">The default channel search order is stable, beta, dev, and canary.</span></span> <span data-ttu-id="f10f7-140">如果存在替代值 WEBVIEW2_RELEASE_CHANNEL_PREFERENCE 环境变量或适用的 releaseChannelPreference 注册表值为1，则将反转频道搜索顺序。</span><span class="sxs-lookup"><span data-stu-id="f10f7-140">When there is an override WEBVIEW2_RELEASE_CHANNEL_PREFERENCE environment variable or applicable releaseChannelPreference registry value with the value of 1, the channel search order is reversed.</span></span>

<span data-ttu-id="f10f7-141">可以指定 userDataFolder 以更改 WebView2 的默认用户数据文件夹位置。</span><span class="sxs-lookup"><span data-stu-id="f10f7-141">userDataFolder can be specified to change the default user data folder location for WebView2.</span></span> <span data-ttu-id="f10f7-142">路径可以是绝对文件路径或解释为相对于当前进程的可执行文件的相对文件路径。</span><span class="sxs-lookup"><span data-stu-id="f10f7-142">The path can be an absolute file path or a relative file path that is interpreted as relative to the current process's executable.</span></span> <span data-ttu-id="f10f7-143">否则，对于 UWP 应用，默认的用户数据文件夹将是程序包的应用数据文件夹;对于非 UWP 应用， `{Executable File Name}.WebView2` 将在应用可执行文件旁边的同一目录中创建默认的用户数据文件夹。</span><span class="sxs-lookup"><span data-stu-id="f10f7-143">Otherwise, for UWP apps, the default user data folder will be the app data folder for the package; for non-UWP apps, the default user data folder `{Executable File Name}.WebView2` will be created in the same directory next to the app executable.</span></span> <span data-ttu-id="f10f7-144">如果可执行文件在进程没有在其中创建新文件夹的权限的目录中运行，WebView2 创建可能失败。</span><span class="sxs-lookup"><span data-stu-id="f10f7-144">WebView2 creation can fail if the executable is running in a directory that the process doesn't have permission to create a new folder in.</span></span> <span data-ttu-id="f10f7-145">应用负责清理已完成的用户数据文件夹。</span><span class="sxs-lookup"><span data-stu-id="f10f7-145">The app is responsible to clean up its user data folder when it is done.</span></span>

<span data-ttu-id="f10f7-146">请注意，作为浏览器进程可能在 WebViews 之间共享，如果指定的选项与当前在共享浏览器进程中运行的 WebViews 的选项不匹配，则 Web 视图创建将失败，并使用 HRESULT_FROM_WIN32 (ERROR_INVALID_STATE) 。</span><span class="sxs-lookup"><span data-stu-id="f10f7-146">Note that as a browser process might be shared among WebViews, WebView creation will fail with HRESULT_FROM_WIN32(ERROR_INVALID_STATE) if the specified options does not match the options of the WebViews that are currently running in the shared browser process.</span></span>

<span data-ttu-id="f10f7-147">environment_created_handler 是对异步操作的处理程序结果，该操作将包含已创建的 WebView2Environment。</span><span class="sxs-lookup"><span data-stu-id="f10f7-147">environment_created_handler is the handler result to the async operation which will contain the WebView2Environment that got created.</span></span>

<span data-ttu-id="f10f7-148">EnvironmentOptions 的 browserExecutableFolder、userDataFolder 和 additionalBrowserArguments 可能由环境变量或注册表中指定的值替代。</span><span class="sxs-lookup"><span data-stu-id="f10f7-148">The browserExecutableFolder, userDataFolder and additionalBrowserArguments of the environmentOptions may be overridden by values either specified in environment variables or in the registry.</span></span>

<span data-ttu-id="f10f7-149">创建 WebView2Environment 时，将选中以下环境变量：</span><span class="sxs-lookup"><span data-stu-id="f10f7-149">When creating a WebView2Environment the following environment variables are checked:</span></span>

```
WEBVIEW2_BROWSER_EXECUTABLE_FOLDER
WEBVIEW2_USER_DATA_FOLDER
WEBVIEW2_ADDITIONAL_BROWSER_ARGUMENTS
WEBVIEW2_RELEASE_CHANNEL_PREFERENCE
```

<span data-ttu-id="f10f7-150">如果找到替代环境变量，则使用 browserExecutableFolder、userDataFolder 和 additionalBrowserArguments 值作为 CreateCoreWebView2EnvironmentWithOptions 参数中对应值的替换项。</span><span class="sxs-lookup"><span data-stu-id="f10f7-150">If an override environment variable is found then we use the browserExecutableFolder, userDataFolder and additionalBrowserArguments values as replacements for the corresponding values in CreateCoreWebView2EnvironmentWithOptions parameters.</span></span>

<span data-ttu-id="f10f7-151">虽然并非严格替代，但也存在可设置的其他环境变量：</span><span class="sxs-lookup"><span data-stu-id="f10f7-151">While not strictly overrides, there exists additional environment variables that can be set:</span></span>

```
WEBVIEW2_WAIT_FOR_SCRIPT_DEBUGGER
```

<span data-ttu-id="f10f7-152">当发现具有非空值时，这表示 Web 视图正在脚本调试程序下启动。</span><span class="sxs-lookup"><span data-stu-id="f10f7-152">When found with a non-empty value, this indicates that the WebView is being launched under a script debugger.</span></span> <span data-ttu-id="f10f7-153">在这种情况下，Web 视图将发出 `Page.waitForDebugger` CDP 命令，该命令将导致 Web 视图内的脚本执行在启动时暂停，直到调试器发出相应 `Runtime.runIfWaitingForDebugger` 的 CDP 命令以继续执行。</span><span class="sxs-lookup"><span data-stu-id="f10f7-153">In this case, the WebView will issue a `Page.waitForDebugger` CDP command that will cause script execution inside the WebView to pause on launch, until a debugger issues a corresponding `Runtime.runIfWaitingForDebugger` CDP command to resume execution.</span></span> <span data-ttu-id="f10f7-154">注意：此环境变量没有等效的注册表项。</span><span class="sxs-lookup"><span data-stu-id="f10f7-154">Note: There is no registry key equivalent of this environment variable.</span></span>

```
WEBVIEW2_PIPE_FOR_SCRIPT_DEBUGGER
```

<span data-ttu-id="f10f7-155">当发现具有非空值时，这表示 Web 视图正在脚本调试程序下启动，该调试程序还支持使用多个 WebViews 的主机应用程序。</span><span class="sxs-lookup"><span data-stu-id="f10f7-155">When found with a non-empty value, this indicates that the WebView is being launched under a script debugger that also supports host applications that use multiple WebViews.</span></span> <span data-ttu-id="f10f7-156">该值用作命名管道的标识符，该管道将在由宿主应用程序创建新的 Web 视图时打开并写入。</span><span class="sxs-lookup"><span data-stu-id="f10f7-156">The value is used as the identifier for a named pipe that will be opened and written to when a new WebView is created by the host application.</span></span> <span data-ttu-id="f10f7-157">负载将与远程调试端口 JSON 目标的负载匹配，并可供外部调试器用于附加到特定的 Web 视图实例。</span><span class="sxs-lookup"><span data-stu-id="f10f7-157">The payload will match that of the remote-debugging-port JSON target and can be used by the external debugger to attach to a specific WebView instance.</span></span> <span data-ttu-id="f10f7-158">调试器创建的管道的格式应该是： `\\.\pipe\WebView2\Debugger\{app_name}\{pipe_name}` where：</span><span class="sxs-lookup"><span data-stu-id="f10f7-158">The format of the pipe created by the debugger should be: `\\.\pipe\WebView2\Debugger\{app_name}\{pipe_name}` where:</span></span>

* `{app_name}` <span data-ttu-id="f10f7-159">是主机应用程序 exe 文件名，例如 WebView2Example.exe</span><span class="sxs-lookup"><span data-stu-id="f10f7-159">is the host application exe filename, e.g. WebView2Example.exe</span></span>

* `{pipe_name}` <span data-ttu-id="f10f7-160">是为 WEBVIEW2_PIPE_FOR_SCRIPT_DEBUGGER 设置的值。</span><span class="sxs-lookup"><span data-stu-id="f10f7-160">is the value set for WEBVIEW2_PIPE_FOR_SCRIPT_DEBUGGER.</span></span>

<span data-ttu-id="f10f7-161">若要启用由 JSON 标识的目标的调试，你还需要设置 WEBVIEW2_ADDITIONAL_BROWSER_ARGUMENTS 环境变量以将其发送到 `--remote-debugging-port={port_num}` ：</span><span class="sxs-lookup"><span data-stu-id="f10f7-161">To enable debugging of the targets identified by the JSON you will also need to set the WEBVIEW2_ADDITIONAL_BROWSER_ARGUMENTS environment variable to send `--remote-debugging-port={port_num}` where:</span></span>

* `{port_num}` <span data-ttu-id="f10f7-162">是 CDP 服务器将绑定到的端口。</span><span class="sxs-lookup"><span data-stu-id="f10f7-162">is the port on which the CDP server will bind.</span></span>

<span data-ttu-id="f10f7-163">请注意，设置 WEBVIEW2_PIPE_FOR_SCRIPT_DEBUGGER 和 WEBVIEW2_ADDITIONAL_BROWSER_ARGUMENTS 环境变量将导致应用程序中托管的 WebViews 以及它们的内容将向第三方应用程序（如调试器）公开。</span><span class="sxs-lookup"><span data-stu-id="f10f7-163">Be aware that setting both the WEBVIEW2_PIPE_FOR_SCRIPT_DEBUGGER and WEBVIEW2_ADDITIONAL_BROWSER_ARGUMENTS environment variables will cause the WebViews hosted in your application and their contents to be exposed to 3rd party applications such as debuggers.</span></span>

<span data-ttu-id="f10f7-164">注意：此环境变量没有等效的注册表项。</span><span class="sxs-lookup"><span data-stu-id="f10f7-164">Note: There is no registry key equivalent of this environment variable.</span></span>

<span data-ttu-id="f10f7-165">如果这些环境变量都不存在，则下一步检查注册表。</span><span class="sxs-lookup"><span data-stu-id="f10f7-165">If none of those environment variables exist, then the registry is examined next.</span></span> <span data-ttu-id="f10f7-166">检查以下注册表项：</span><span class="sxs-lookup"><span data-stu-id="f10f7-166">The following registry keys are checked:</span></span>

```
[{Root}\Software\Policies\Microsoft\EmbeddedBrowserWebView\LoaderOverride\{AppId}]
"releaseChannelPreference"=dword:00000000
"browserExecutableFolder"=""
"userDataFolder"=""
"additionalBrowserArguments"=""
```

<span data-ttu-id="f10f7-167">在浏览器更新期间打开某些 Web 视图实例的不需要的情况下，我们最终会阻止删除旧的边缘浏览器。</span><span class="sxs-lookup"><span data-stu-id="f10f7-167">In the unlikely scenario where some instances of WebView are open during a browser update we could end up blocking the deletion of old Edge browsers.</span></span> <span data-ttu-id="f10f7-168">为避免用尽磁盘空间，如果新的 Web 视图创建会在检测到存在许多旧版本的情况下失败，并显示下一个错误。</span><span class="sxs-lookup"><span data-stu-id="f10f7-168">To avoid running out of disk space a new WebView creation will fail with the next error if it detects that there are many old versions present.</span></span>

```
ERROR_DISK_FULL
```

<span data-ttu-id="f10f7-169">允许的默认最大边缘版本数为20。</span><span class="sxs-lookup"><span data-stu-id="f10f7-169">The default maximum number of Edge versions allowed is 20.</span></span>

<span data-ttu-id="f10f7-170">可以使用以下环境变量的值覆盖所允许的旧边缘版本的最大数量。</span><span class="sxs-lookup"><span data-stu-id="f10f7-170">The maximum number of old Edge versions allowed can be overwritten with the value of the following environment variable.</span></span>

```
WEBVIEW2_MAX_INSTANCES
```

<span data-ttu-id="f10f7-171">如果 Web 视图依赖于已安装的边缘，并且卸载后任何后续创建都将失败，并出现下一个错误</span><span class="sxs-lookup"><span data-stu-id="f10f7-171">If the Webview depends on an installed Edge and it is uninstalled any subsequent creation will fail with the next error</span></span>

```
ERROR_PRODUCT_UNINSTALLED
```

<span data-ttu-id="f10f7-172">首先，我们检查 Root 是 HKLM，然后是 HKCU。</span><span class="sxs-lookup"><span data-stu-id="f10f7-172">First we check with Root as HKLM and then HKCU.</span></span> <span data-ttu-id="f10f7-173">AppId 首先设置为应用程序用户模型 ID （调用方的进程），如果没有相应的注册表项，则将 AppId 设置为调用方的进程的可执行名称，或者，如果不是注册表项，则为 "\*"。</span><span class="sxs-lookup"><span data-stu-id="f10f7-173">AppId is first set to the Application User Model ID of the caller's process, then if there's no corresponding registry key the AppId is set to the executable name of the caller's process, or if that isn't a registry key then '\*'.</span></span> <span data-ttu-id="f10f7-174">如果找到替代注册表项，则使用 browserExecutableFolder、userDataFolder 和 additionalBrowserArguments 注册表值作为 CreateCoreWebView2EnvironmentWithOptions 参数中对应值的替换项。</span><span class="sxs-lookup"><span data-stu-id="f10f7-174">If an override registry key is found then we use the browserExecutableFolder, userDataFolder and additionalBrowserArguments registry values as replacements for the corresponding values in CreateCoreWebView2EnvironmentWithOptions parameters.</span></span>

#### <span data-ttu-id="f10f7-175">GetAvailableCoreWebView2BrowserVersionString</span><span class="sxs-lookup"><span data-stu-id="f10f7-175">GetAvailableCoreWebView2BrowserVersionString</span></span> 

> <span data-ttu-id="f10f7-176">公共 STDAPI [GetAvailableCoreWebView2BrowserVersionString](#getavailablecorewebview2browserversionstring) (PCWSTR BROWSEREXECUTABLEFOLDER，LPWSTR \* versionInfo) </span><span class="sxs-lookup"><span data-stu-id="f10f7-176">public STDAPI [GetAvailableCoreWebView2BrowserVersionString](#getavailablecorewebview2browserversionstring)(PCWSTR browserExecutableFolder, LPWSTR \* versionInfo)</span></span>

<span data-ttu-id="f10f7-177">获取包含频道名称的浏览器版本信息（如果不是稳定通道或嵌入边缘）。</span><span class="sxs-lookup"><span data-stu-id="f10f7-177">Get the browser version info including channel name if it is not the stable channel or the Embedded Edge.</span></span>

<span data-ttu-id="f10f7-178">频道名称是 beta 版、开发人员和未带了设备。</span><span class="sxs-lookup"><span data-stu-id="f10f7-178">Channel names are beta, dev, and canary.</span></span> <span data-ttu-id="f10f7-179">如果 browserExecutableFolder 或通道首选项存在替代，将使用替代。</span><span class="sxs-lookup"><span data-stu-id="f10f7-179">If an override exists for the browserExecutableFolder or the channel preference, the override will be used.</span></span> <span data-ttu-id="f10f7-180">如果没有替代，则使用传递到 GetAvailableCoreWebView2BrowserVersionString 的参数。</span><span class="sxs-lookup"><span data-stu-id="f10f7-180">If there isn't an override, then the parameter passed to GetAvailableCoreWebView2BrowserVersionString is used.</span></span>

