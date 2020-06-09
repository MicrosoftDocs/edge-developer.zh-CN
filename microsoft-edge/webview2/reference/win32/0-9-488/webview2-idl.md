---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/07/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 8a684d2a00aa1ae580a3b4391c9f6037dc8f9085
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10697068"
---
# 全局变量 

> [!NOTE]
> SDK 版本0.9.515 后，此参考可能会更改或不可用。 请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[CompareBrowserVersions](#comparebrowserversions) | 此方法适用于任何人都希望正确比较版本以确定哪个版本较旧、更旧或相同。
[CreateCoreWebView2Environment](#createcorewebview2environment) | 使用安装的边缘版本创建长绿 WebView2 环境。
[CreateCoreWebView2EnvironmentWithDetails](#createcorewebview2environmentwithdetails) | 此 API 将在下一个 SDK 版本中被删除。
[CreateCoreWebView2EnvironmentWithOptions](#createcorewebview2environmentwithoptions) | DLL 导出以使用自定义版本的 Edge、用户数据目录和/或其他选项创建 WebView2 环境。
[GetAvailableCoreWebView2BrowserVersionString](#getavailablecorewebview2browserversionstring) | 获取包含频道名称的浏览器版本信息（如果不是稳定通道或嵌入边缘）。

## 成员

#### CompareBrowserVersions 

> 公共 STDAPI [CompareBrowserVersions](#comparebrowserversions)（PCWSTR VERSION1，PCWSTR version2，int * 结果）

此方法适用于任何人都希望正确比较版本以确定哪个版本较旧、更旧或相同。

它可用于确定是在版本上使用 webview2 还是特定功能库。 如果 version1 小于、等于或大于 version2，则将结果的值设置为-1、0或1。 如果无法解析任何版本字符串或任何输入参数为 null，则返回 E_INVALIDARG。 输入可以直接使用从 GetAvailableCoreWebView2BrowserVersionString 获取的 versionInfo，信道信息将被忽略。

#### CreateCoreWebView2Environment 

> 公共 STDAPI [CreateCoreWebView2Environment](#createcorewebview2environment)（[ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler](icorewebview2createcorewebview2environmentcompletedhandler.md) * environment_created_handler）

使用安装的边缘版本创建长绿 WebView2 环境。

这等效于对 browserExecutableFolder、userDataFolder、additionalBrowserArguments 调用 nullptr 的 CreateCoreWebView2EnvironmentWithOptions。 有关详细信息，请参阅 CreateCoreWebView2EnvironmentWithOptions。

#### CreateCoreWebView2EnvironmentWithDetails 

> 公共 STDAPI [CreateCoreWebView2EnvironmentWithDetails](#createcorewebview2environmentwithdetails)（PCWSTR BROWSEREXECUTABLEFOLDER、PCWSTR USERDATAFOLDER、PCWSTR additionalBrowserArguments、 [ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler * environment_created_handler](icorewebview2createcorewebview2environmentcompletedhandler.md) ）

此 API 将在下一个 SDK 版本中被删除。

请使用 CreateCoreWebView2EnvironmentWithOptions。

#### CreateCoreWebView2EnvironmentWithOptions 

> 公共 STDAPI [CreateCoreWebView2EnvironmentWithOptions](#createcorewebview2environmentwithoptions)（PCWSTR BROWSEREXECUTABLEFOLDER、PCWSTR UserDataFolder、 [ICoreWebView2EnvironmentOptions](icorewebview2environmentoptions.md) [* environmentOptions、ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler](icorewebview2createcorewebview2environmentcompletedhandler.md) * environment_created_handler）

DLL 导出以使用自定义版本的 Edge、用户数据目录和/或其他选项创建 WebView2 环境。

browserExecutableFolder 是包含嵌入边缘的文件夹的相对路径。 可以通过复制已安装边缘的命名文件夹的版本（如已安装的73.0.52.0 边缘的73.0.52.0 子文件夹）来获取嵌入的边缘。 该文件夹应具有 msedge、msedge 等。 为 browserExecutableFolder 使用 null 或空字符串，以使用计算机上安装的 Edge 创建 Web 视图，在这种情况下，API 将根据通道首选项尝试查找在计算机上安装的边缘兼容版本。

默认通道搜索顺序为稳定、beta、dev 和未固定。 如果存在替代值 WEBVIEW2_RELEASE_CHANNEL_PREFERENCE 环境变量或适用的 releaseChannelPreference 注册表值为1，则将反转频道搜索顺序。

可以指定 userDataFolder 以更改 WebView2 的默认用户数据文件夹位置。 路径可以是绝对文件路径或解释为相对于当前进程的可执行文件的相对文件路径。 否则，对于 UWP 应用，默认的用户数据文件夹将是程序包的应用数据文件夹;对于非 UWP 应用， `{Executable File Name}.WebView2` 将在应用可执行文件旁边的同一目录中创建默认的用户数据文件夹。 如果可执行文件在进程没有在其中创建新文件夹的权限的目录中运行，WebView2 创建可能失败。 应用负责清理已完成的用户数据文件夹。

请注意，作为浏览器进程可能在 WebViews 之间共享，如果指定的选项与当前在共享浏览器进程中运行的 WebViews 的选项不匹配，则使用 HRESULT_FROM_WIN32 （ERROR_INVALID_STATE）时，Web 视图创建将失败。

environment_created_handler 是对异步操作的处理程序结果，该操作将包含已创建的 WebView2Environment。

EnvironmentOptions 的 browserExecutableFolder、userDataFolder 和 additionalBrowserArguments 可能由环境变量或注册表中指定的值替代。

创建 WebView2Environment 时，将选中以下环境变量：

```
WEBVIEW2_BROWSER_EXECUTABLE_FOLDER
WEBVIEW2_USER_DATA_FOLDER
WEBVIEW2_ADDITIONAL_BROWSER_ARGUMENTS
WEBVIEW2_RELEASE_CHANNEL_PREFERENCE
```

如果找到替代环境变量，则使用 browserExecutableFolder、userDataFolder 和 additionalBrowserArguments 值作为 CreateCoreWebView2EnvironmentWithOptions 参数中对应值的替换项。

虽然并非严格替代，但也存在可设置的其他环境变量：

```
WEBVIEW2_WAIT_FOR_SCRIPT_DEBUGGER
```

当发现具有非空值时，这表示 Web 视图正在脚本调试程序下启动。 在这种情况下，Web 视图将发出 `Page.waitForDebugger` CDP 命令，该命令将导致 Web 视图内的脚本执行在启动时暂停，直到调试器发出相应 `Runtime.runIfWaitingForDebugger` 的 CDP 命令以继续执行。 注意：此环境变量没有等效的注册表项。

```
WEBVIEW2_PIPE_FOR_SCRIPT_DEBUGGER
```

当发现具有非空值时，这表示 Web 视图正在脚本调试程序下启动，该调试程序还支持使用多个 WebViews 的主机应用程序。 该值用作命名管道的标识符，该管道将在由宿主应用程序创建新的 Web 视图时打开并写入。 负载将与远程调试端口 JSON 目标的负载匹配，并可供外部调试器用于附加到特定的 Web 视图实例。 调试器创建的管道的格式应该是： `\\.\pipe\WebView2\Debugger\{app_name}\{pipe_name}` where：

* `{app_name}` 是主机应用程序 exe 文件名，例如 WebView2Example

* `{pipe_name}` 是为 WEBVIEW2_PIPE_FOR_SCRIPT_DEBUGGER 设置的值。

若要启用由 JSON 标识的目标的调试，你还需要设置 WEBVIEW2_ADDITIONAL_BROWSER_ARGUMENTS 环境变量以将其发送到 `--remote-debugging-port={port_num}` ：

* `{port_num}` 是 CDP 服务器将绑定到的端口。

请注意，设置 WEBVIEW2_PIPE_FOR_SCRIPT_DEBUGGER 和 WEBVIEW2_ADDITIONAL_BROWSER_ARGUMENTS 环境变量将导致应用程序中托管的 WebViews 以及它们的内容将向第三方应用程序（如调试器）公开。

注意：此环境变量没有等效的注册表项。

如果这些环境变量都不存在，则下一步检查注册表。 检查以下注册表项：

```
[{Root}\Software\Policies\Microsoft\EmbeddedBrowserWebView\LoaderOverride\{AppId}]
"releaseChannelPreference"=dword:00000000
"browserExecutableFolder"=""
"userDataFolder"=""
"additionalBrowserArguments"=""
```

在浏览器更新期间打开某些 Web 视图实例的不需要的情况下，我们最终会阻止删除旧的边缘浏览器。 为避免用尽磁盘空间，如果新的 Web 视图创建会在检测到存在许多旧版本的情况下失败，并显示下一个错误。

```
ERROR_DISK_FULL
```

允许的默认最大边缘版本数为20。

可以使用以下环境变量的值覆盖所允许的旧边缘版本的最大数量。

```
WEBVIEW2_MAX_INSTANCES
```

如果 Web 视图依赖于已安装的边缘，并且卸载后任何后续创建都将失败，并出现下一个错误

```
ERROR_PRODUCT_UNINSTALLED
```

首先，我们检查 Root 是 HKLM，然后是 HKCU。 AppId 首先设置为应用程序用户模型 ID （调用方的进程），如果没有相应的注册表项，则将 AppId 设置为调用方的进程的可执行名称，或者，如果不是注册表项，则为 "*"。 如果找到替代注册表项，则使用 browserExecutableFolder、userDataFolder 和 additionalBrowserArguments 注册表值作为 CreateCoreWebView2EnvironmentWithOptions 参数中对应值的替换项。

#### GetAvailableCoreWebView2BrowserVersionString 

> 公共 STDAPI [GetAvailableCoreWebView2BrowserVersionString](#getavailablecorewebview2browserversionstring)（PCWSTR BROWSEREXECUTABLEFOLDER，LPWSTR * versionInfo）

获取包含频道名称的浏览器版本信息（如果不是稳定通道或嵌入边缘）。

频道名称是 beta 版、开发人员和未带了设备。 如果 browserExecutableFolder 或通道首选项存在替代，将使用替代。 如果没有替代，则使用传递到 GetAvailableCoreWebView2BrowserVersionString 的参数。

