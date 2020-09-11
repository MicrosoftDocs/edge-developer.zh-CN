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
# 全局变量 

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[CompareBrowserVersions](#comparebrowserversions) | 此方法适用于任何人都希望正确比较版本以确定哪个版本较旧、更旧或相同。
[CreateCoreWebView2Environment](#createcorewebview2environment) | 使用安装的边缘版本创建长绿 WebView2 环境。
[CreateCoreWebView2EnvironmentWithOptions](#createcorewebview2environmentwithoptions) | DLL 导出以使用自定义版本的 Edge、用户数据目录和/或其他选项创建 WebView2 环境。
[GetAvailableCoreWebView2BrowserVersionString](#getavailablecorewebview2browserversionstring) | 获取包含频道名称的浏览器版本信息（如果不是稳定通道或嵌入边缘）。

## 成员

#### CompareBrowserVersions 

> public STDAPI [CompareBrowserVersions](#comparebrowserversions) (PCWSTR VERSION1，PCWSTR version2，int * 结果) 

此方法适用于任何人都希望正确比较版本以确定哪个版本较旧、更旧或相同。

它可用于确定是在版本上使用 webview2 还是特定功能库。 如果 version1 小于、等于或大于 version2，则将结果的值设置为-1、0或1。 如果无法解析任何版本字符串或任何输入参数为 null，则返回 E_INVALIDARG。 输入可以直接使用从 GetAvailableCoreWebView2BrowserVersionString 获取的 versionInfo，信道信息将被忽略。

#### CreateCoreWebView2Environment 

> 公共 STDAPI [CreateCoreWebView2Environment](#createcorewebview2environment) (ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler * environmentCreatedHandler) 

使用安装的边缘版本创建长绿 WebView2 环境。

这等效于对 browserExecutableFolder、userDataFolder、additionalBrowserArguments 调用 nullptr 的 CreateCoreWebView2EnvironmentWithOptions。 有关详细信息，请参阅 CreateCoreWebView2EnvironmentWithOptions。

#### CreateCoreWebView2EnvironmentWithOptions 

> public STDAPI [CreateCoreWebView2EnvironmentWithOptions](#createcorewebview2environmentwithoptions) (PCWSTR BROWSEREXECUTABLEFOLDER、PCWSTR UserDataFolder、 [ICoreWebView2EnvironmentOptions](icorewebview2environmentoptions.md) [* environmentOptions、ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler](icorewebview2createcorewebview2environmentcompletedhandler.md) * environmentCreatedHandler) 

DLL 导出以使用自定义版本的 Edge、用户数据目录和/或其他选项创建 WebView2 环境。

WebView2 环境和所有其他 WebView2 对象都是单线程的，并且在需要为单线程单元初始化 COM 的 Windows 组件上具有依赖关系。 在调用 CreateCoreWebView2EnvironmentWithOptions 之前，应用程序应调用 CoInitializeEx。

```
CoInitializeEx(nullptr, COINIT_APARTMENTTHREADED);
```

如果 CoInitializeEx 未被调用或以前用 COINIT_MULTITHREADED 调用，CreateCoreWebView2EnvironmentWithOptions 将失败，并出现以下错误之一。

```
CO_E_NOTINITIALIZED (if CoInitializeEx was not called)
RPC_E_CHANGED_MODE  (if CoInitializeEx was previously called with
                     COINIT_MULTITHREADED)
```

用于 `browserExecutableFolder` 指定 WebView2 控件使用的是 WebView2 运行库的固定或已安装版本，该版本存在于客户端计算机上。 若要使用 WebView2 运行时的固定版本，请将包含 WebView2 运行时的固定版本的文件夹的相对路径传递给 `browserExecutableFolder` 。 若要创建使用客户端计算机上存在的 WebView2 运行时的已安装版本的 WebView2 控件，请将 null 或空字符串传递给 `browserExecutableFolder` 。 在此方案中，API 尝试查找客户端计算机上安装的 WebView2 运行时的兼容版本， (首先在计算机级别，然后按用户) 使用所选的通道首选项。 WebView2 运行时的固定版本的路径不应包含 `\Edge\Application\` 。 使用此类路径时，API 将失败，并 ERROR_NOT_SUPPORTED。

默认频道搜索顺序为 WebView2 运行时、Beta、开发和 ""。 如果存在替代值 WEBVIEW2_RELEASE_CHANNEL_PREFERENCE 环境变量或适用的 releaseChannelPreference 注册表值为1，则将反转频道搜索顺序。

可以指定 userDataFolder 以更改 WebView2 的默认用户数据文件夹位置。 路径可以是绝对文件路径或解释为相对于当前进程的可执行文件的相对文件路径。 否则，对于 UWP 应用，默认的用户数据文件夹将是程序包的应用数据文件夹;对于非 UWP 应用， `{Executable File Name}.WebView2` 将在应用可执行文件旁边的同一目录中创建默认的用户数据文件夹。 如果可执行文件在进程没有在其中创建新文件夹的权限的目录中运行，WebView2 创建可能失败。 应用负责清理已完成的用户数据文件夹。

请注意，作为浏览器进程可能在 WebViews 之间共享，如果指定的选项与当前在共享浏览器进程中运行的 WebViews 的选项不匹配，则 Web 视图创建将失败，并使用 HRESULT_FROM_WIN32 (ERROR_INVALID_STATE) 。

environmentCreatedHandler 是对异步操作的处理程序结果，它将包含已创建的 WebView2Environment。

EnvironmentOptions 的 browserExecutableFolder、userDataFolder 和 additionalBrowserArguments 可能由环境变量或注册表中指定的值替代。

创建 WebView2Environment 时，将选中以下环境变量：

```
WEBVIEW2_BROWSER_EXECUTABLE_FOLDER
WEBVIEW2_USER_DATA_FOLDER
WEBVIEW2_ADDITIONAL_BROWSER_ARGUMENTS
WEBVIEW2_RELEASE_CHANNEL_PREFERENCE
```

如果找到替代环境变量，则使用 browserExecutableFolder 和 userDataFolder 值作为 CreateCoreWebView2EnvironmentWithOptions 参数中对应值的替换项。 如果 additionalBrowserArguments 在环境变量或注册表中指定，它将追加到 CreateCoreWebView2EnvironmentWithOptions 参数中的 correspinding 值。

虽然并非严格替代，但也存在可设置的其他环境变量：

```
WEBVIEW2_WAIT_FOR_SCRIPT_DEBUGGER
```

当发现具有非空值时，这表示 Web 视图正在脚本调试程序下启动。 在这种情况下，Web 视图将发出 `Page.waitForDebugger` CDP 命令，该命令将导致 Web 视图内的脚本执行在启动时暂停，直到调试器发出相应 `Runtime.runIfWaitingForDebugger` 的 CDP 命令以继续执行。 注意：此环境变量没有等效的注册表项。

```
WEBVIEW2_PIPE_FOR_SCRIPT_DEBUGGER
```

当发现具有非空值时，这表示 Web 视图正在脚本调试程序下启动，该调试程序还支持使用多个 WebViews 的主机应用程序。 该值用作命名管道的标识符，该管道将在由宿主应用程序创建新的 Web 视图时打开并写入。 负载将与远程调试端口 JSON 目标的负载匹配，并可供外部调试器用于附加到特定的 Web 视图实例。 调试器创建的管道的格式应该是： `\\.\pipe\WebView2\Debugger\{app_name}\{pipe_name}` where：

* `{app_name}` 是主机应用程序 exe 文件名，例如 WebView2Example.exe

* `{pipe_name}` 是为 WEBVIEW2_PIPE_FOR_SCRIPT_DEBUGGER 设置的值。

若要启用由 JSON 标识的目标的调试，你还需要设置 WEBVIEW2_ADDITIONAL_BROWSER_ARGUMENTS 环境变量以将其发送到 `--remote-debugging-port={port_num}` ：

* `{port_num}` 是 CDP 服务器将绑定到的端口。

请注意，设置 WEBVIEW2_PIPE_FOR_SCRIPT_DEBUGGER 和 WEBVIEW2_ADDITIONAL_BROWSER_ARGUMENTS 环境变量将导致应用程序中托管的 WebViews 以及它们的内容将向第三方应用程序（如调试器）公开。

注意：此环境变量没有等效的注册表项。

如果这些环境变量都不存在，则下一步检查注册表。 下列注册表值已选中：

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

browserExecutableFolder 和 releaseChannelPreference 可以使用 "管理模板" 下的组策略进行配置，> Microsoft Edge WebView2。 旧的注册表位置将很快被弃用：

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

首先，我们检查 Root 是 HKLM，然后是 HKCU。 AppId 首先设置为应用程序用户模型 ID （调用方的进程），如果没有相应的注册表项，则将 AppId 设置为调用方的进程的可执行名称，或者，如果不是注册表项，则为 "*"。 如果找到替代注册表项，则使用 browserExecutableFolder 和 userDataFolder 注册表值作为替换项，并为 CreateCoreWebView2EnvironmentWithOptions 参数中的相应值追加 additionalBrowserArguments 注册表值。

#### GetAvailableCoreWebView2BrowserVersionString 

> 公共 STDAPI [GetAvailableCoreWebView2BrowserVersionString](#getavailablecorewebview2browserversionstring) (PCWSTR BROWSEREXECUTABLEFOLDER，LPWSTR * versionInfo) 

获取包含频道名称的浏览器版本信息（如果不是稳定通道或嵌入边缘）。

频道名称是 beta 版、开发人员和未带了设备。 如果 browserExecutableFolder 或通道首选项存在替代，将使用替代。 如果没有替代，则使用传递到 GetAvailableCoreWebView2BrowserVersionString 的参数。

