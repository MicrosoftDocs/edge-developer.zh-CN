---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + 全局
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: 5ee2461ca1b0aeb0a5f0d23f0918561065570523
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10877985"
---
# 0.8.355-Globals 

> [!NOTE]
> 此接口可能会在 SDK 版本0.8.355 后更改或不可用。 请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[CreateWebView2EnvironmentWithDetails](#createwebview2environmentwithdetails) | DLL 导出以使用自定义版本的 Edge、用户数据目录和/或其他浏览器开关创建 WebView2 环境。
[CreateWebView2Environment](#createwebview2environment) | 使用安装的边缘版本创建长绿 WebView2 环境。
[GetWebView2BrowserVersionInfo](#getwebview2browserversioninfo) | 获取包含频道名称的浏览器版本信息（如果不是稳定通道或嵌入边缘）。
[CompareBrowserVersions](#comparebrowserversions) | 此方法适用于任何人都希望正确比较版本以确定哪个版本较旧、更旧或相同。

## 成员

#### CreateWebView2EnvironmentWithDetails 

> 公共 STDAPI [CreateWebView2EnvironmentWithDetails](#createwebview2environmentwithdetails)（PCWSTR BROWSEREXECUTABLEFOLDER、PCWSTR USERDATAFOLDER、PCWSTR additionalBrowserArguments、[IWebView2CreateWebView2EnvironmentCompletedHandler * environment_created_handler](IWebView2CreateWebView2EnvironmentCompletedHandler.md) ）

DLL 导出以使用自定义版本的 Edge、用户数据目录和/或其他浏览器开关创建 WebView2 环境。

browserExecutableFolder 是包含嵌入边缘的文件夹的相对路径。 可以通过复制已安装边缘的命名文件夹的版本（如已安装的73.0.52.0 边缘的73.0.52.0 子文件夹）来获取嵌入的边缘。 文件夹应具有 msedge.exe、msedge.dll 等。为 browserExecutableFolder 使用 null 或空字符串，以使用计算机上安装的 Edge 创建 Web 视图，在这种情况下，API 将根据通道首选项尝试查找在计算机上安装的边缘兼容版本。

默认通道搜索顺序为稳定、beta、dev 和未固定。 如果存在替代值 WEBVIEW2_RELEASE_CHANNEL_PREFERENCE 环境变量或适用的 releaseChannelPreference 注册表值为1，则将反转频道搜索顺序。

可以指定 userDataFolder 以更改 WebView2 的默认用户数据文件夹位置。 路径可以是绝对文件路径或解释为相对于当前进程的可执行文件的相对文件路径。 否则，对于 UWP 应用，默认的用户数据文件夹将是程序包的应用数据文件夹;对于非 UWP 应用， `{Executable File Name}.WebView2` 将在应用可执行文件旁边的同一目录中创建默认的用户数据文件夹。 如果可执行文件在进程没有在其中创建新文件夹的权限的目录中运行，WebView2 创建可能失败。 应用负责清理已完成的用户数据文件夹。

可以指定 additionalBrowserArguments 以更改 Web 视图的行为。 这些内容将作为命令行的一部分传递到浏览器进程。 有关命令行开关的详细信息，请参阅[用标志运行 Chromium](https://aka.ms/RunChromiumWithFlags) ，了解如何切换到浏览器进程。 如果使用命令行开关启动应用 `--edge-webview-switches=xxx` ，则该开关的值（上面示例中的 xxx）也将追加到浏览器进程命令行。 某些交换机（如 `--user-data-dir` 内部）和对 Web 视图来说很重要。 即使指定，这些开关也将被忽略。 如果多次指定同一开关，则最后一个参数将获胜。 请注意，这也适用于交换机，如 `--enable-features` 。 不会尝试合并同一开关的不同值。 在 `--edge-webview-switches` 处理 additionalBrowserArguments 参数后，将处理应用进程的命令行值。 另请注意，由于浏览器进程可能在 WebViews 之间共享，因此不保证应用，除非启动浏览器进程的第一个 Web 视图除外。 如果指定开关的分析失败，则将忽略它们。 `nullptr` 将不带任何标志运行浏览器进程。

environment_created_handler 是对异步操作的处理程序结果，该操作将包含已创建的 WebView2Environment。

EnvironmentParams 的 browserExecutableFolder、userDataFolder 和 additionalBrowserArguments 成员可能会被在环境变量或注册表中指定的值覆盖。

创建 WebView2Environment 时，将选中以下环境变量：

```cpp
WEBVIEW2_BROWSER_EXECUTABLE_FOLDER
WEBVIEW2_USER_DATA_FOLDER
WEBVIEW2_ADDITIONAL_BROWSER_ARGUMENTS
WEBVIEW2_RELEASE_CHANNEL_PREFERENCE
```

如果找到替代环境变量，则使用 browserExecutableFolder、userDataFolder 和 additionalBrowserArguments 值作为 CreateWebView2EnvironmentWithDetails 参数中对应值的替换项。

虽然并非严格替代，但也存在可设置的其他环境变量：

```cpp
WEBVIEW2_WAIT_FOR_SCRIPT_DEBUGGER
```

当发现具有非空值时，这表示 Web 视图正在脚本调试程序下启动。 在这种情况下，Web 视图将发出 `Page.waitForDebugger` CDP 命令，该命令将导致 Web 视图内的脚本执行在启动时暂停，直到调试器发出相应 `Runtime.runIfWaitingForDebugger` 的 CDP 命令以继续执行。 注意：此环境变量没有等效的注册表项。

```cpp
WEBVIEW2_PIPE_FOR_SCRIPT_DEBUGGER
```

当发现具有非空值时，这表示 Web 视图正在脚本调试程序下启动，该调试程序还支持使用多个 WebViews 的主机应用程序。 该值用作命名管道的标识符，该管道将在由宿主应用程序创建新的 Web 视图时打开并写入。 负载将与远程调试端口 JSON 目标的负载匹配，并可供外部调试器用于附加到特定的 Web 视图实例。 调试器创建的管道的格式应该是： `\\.\pipe\WebView2\Debugger\{app_name}\{pipe_name}` where：

* `{app_name}` 是主机应用程序 exe 文件名，例如 WebView2Example.exe

* `{pipe_name}` 是为 WEBVIEW2_PIPE_FOR_SCRIPT_DEBUGGER 设置的值。

若要启用由 JSON 标识的目标的调试，你还需要设置 WEBVIEW2_ADDITIONAL_BROWSER_ARGUMENTS 环境变量以将其发送到 `--remote-debugging-port={port_num}` ：

* `{port_num}` 是 CDP 服务器将绑定到的端口。

请注意，设置 WEBVIEW2_PIPE_FOR_SCRIPT_DEBUGGER 和 WEBVIEW2_ADDITIONAL_BROWSER_ARGUMENTS 环境变量将导致应用程序中托管的 WebViews 以及它们的内容将向第三方应用程序（如调试器）公开。

注意：此环境变量没有等效的注册表项。

如果这些环境变量都不存在，则下一步检查注册表。 检查以下注册表项：

```cpp
[{Root}\Software\Policies\Microsoft\EmbeddedBrowserWebView\LoaderOverride\{AppId}]
"releaseChannelPreference"=dword:00000000
"browserExecutableFolder"=""
"userDataFolder"=""
"additionalBrowserArguments"=""
```

在浏览器更新期间打开某些 Web 视图实例的不需要的情况下，我们最终会阻止删除旧的边缘浏览器。 为避免用尽磁盘空间，如果新的 Web 视图创建会在检测到存在许多旧版本的情况下失败，并显示下一个错误。

```cpp
ERROR_DISK_FULL
```

允许的默认最大边缘版本数为20。

可以使用以下环境变量的值覆盖所允许的旧边缘版本的最大数量。

```cpp
WEBVIEW2_MAX_INSTANCES
```

如果 Web 视图依赖于已安装的边缘，并且卸载后任何后续创建都将失败，并出现下一个错误

```cpp
ERROR_PRODUCT_UNINSTALLED
```

首先，我们检查 Root 是 HKLM，然后是 HKCU。 AppId 首先设置为应用程序用户模型 ID （调用方的进程），如果没有相应的注册表项，则将 AppId 设置为调用方的进程的可执行名称，或者，如果不是注册表项，则为 "*"。 如果找到替代注册表项，则使用 browserExecutableFolder、userDataFolder 和 additionalBrowserArguments 注册表值作为 CreateWebView2EnvironmentWithDetails 参数中对应值的替换项。 如果这些注册表值中的任何一个不存在，则使用传递到 CreateWebView2Environment 的参数。

#### CreateWebView2Environment 

> 公共 STDAPI [CreateWebView2Environment](#createwebview2environment)（[IWebView2CreateWebView2EnvironmentCompletedHandler](IWebView2CreateWebView2EnvironmentCompletedHandler.md) * environment_created_handler）

使用安装的边缘版本创建长绿 WebView2 环境。

这等效于对 browserExecutableFolder、userDataFolder、additionalBrowserArguments 调用 nullptr 的 CreateWebView2EnvironmentWithDetails。 有关详细信息，请参阅 CreateWebView2EnvironmentWithDetails。

#### GetWebView2BrowserVersionInfo 

> 公共 STDAPI [GetWebView2BrowserVersionInfo](#getwebview2browserversioninfo)（PCWSTR BROWSEREXECUTABLEFOLDER，LPWSTR * versionInfo）

获取包含频道名称的浏览器版本信息（如果不是稳定通道或嵌入边缘）。

频道名称是 beta 版、开发人员和未带了设备。 如果 browserExecutableFolder 或通道首选项存在替代，将使用替代。 如果没有替代，则使用传递到 GetWebView2BrowserVersionInfo 的参数。

#### CompareBrowserVersions 

> 公共 STDAPI [CompareBrowserVersions](#comparebrowserversions)（PCWSTR VERSION1，PCWSTR version2，int * 结果）

此方法适用于任何人都希望正确比较版本以确定哪个版本较旧、更旧或相同。

它可用于确定是在版本上使用 webview2 还是特定功能库。 如果 version1 小于、等于或大于 version2，则将结果的值设置为-1、0或1。 如果无法解析任何版本字符串或任何输入参数为 null，则返回 E_INVALIDARG。 输入可以直接使用从 GetWebView2BrowserVersionInfo 获取的 versionInfo，信道信息将被忽略。

