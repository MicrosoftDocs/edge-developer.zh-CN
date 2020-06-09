---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 3de9cd454f693179a0d1dc63e6ccb1332f80c875
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698459"
---
# interface ICoreWebView2EnvironmentOptions 

```
interface ICoreWebView2EnvironmentOptions
  : public IUnknown
```

用于创建 WebView2 环境的选项。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[get_AdditionalBrowserArguments](#get_additionalbrowserarguments) | 可以指定 AdditionalBrowserArguments 以更改 Web 视图的行为。
[get_Language](#get_language) | 将运行 Web 视图运行的默认语言。
[get_TargetCompatibleBrowserVersion](#get_targetcompatiblebrowserversion) | 需要与调用应用程序兼容的 Edge WebView2 运行时二进制文件的版本。
[put_AdditionalBrowserArguments](#put_additionalbrowserarguments) | 设置 AdditionalBrowserArguments 属性。
[put_Language](#put_language) | 设置 "语言" 属性。
[put_TargetCompatibleBrowserVersion](#put_targetcompatiblebrowserversion) | 设置 TargetCompatibleBrowserVersion。

默认实现在 WebView2EnvironmentOptions 中提供。

```cpp
    auto options = Microsoft::WRL::Make<CoreWebView2EnvironmentOptions>();
    if(!m_language.empty())
        CHECK_FAILURE(options->put_Language(m_language.c_str()));
    HRESULT hr = CreateCoreWebView2EnvironmentWithOptions(
        subFolder, nullptr, options.Get(),
        Callback<ICoreWebView2CreateCoreWebView2EnvironmentCompletedHandler>(
            this, &AppWindow::OnCreateEnvironmentCompleted)
            .Get());
```

## 成员

#### get_AdditionalBrowserArguments 

可以指定 AdditionalBrowserArguments 以更改 Web 视图的行为。

> public HRESULT [get_AdditionalBrowserArguments](#get_additionalbrowserarguments)（LPWSTR * value）

这些内容将作为命令行的一部分传递到浏览器进程。 有关命令行开关的详细信息，请参阅[用标志运行 Chromium](https://aka.ms/RunChromiumWithFlags) ，了解如何切换到浏览器进程。 如果使用命令行开关启动应用 `--edge-webview-switches=xxx` ，则该开关的值（上面示例中的 xxx）也将追加到浏览器进程命令行。 某些交换机（如 `--user-data-dir` 内部）和对 Web 视图来说很重要。 即使指定，这些开关也将被忽略。 如果多次指定同一开关，则最后一个参数将获胜。 除了禁用和启用的功能外，不会尝试合并同一开关的不同值。 将使用简单的逻辑合并 "" 和 "" 的功能 `--enable-features` `--disable-features` ：这些功能将是指定功能和内置功能的联合，如果某个功能被禁用，它将从 "启用的功能" 列表中删除。 在 `--edge-webview-switches` 处理 additionalBrowserArguments 参数后，将处理应用进程的命令行值。 某些功能在内部禁用且无法启用。 如果指定开关的分析失败，则将忽略它们。 默认情况下，不执行任何额外的标志即可运行浏览器进程。

#### get_Language 

将运行 Web 视图运行的默认语言。

> public HRESULT [get_Language](#get_language)（LPWSTR * value）

它适用于浏览器 Ui，如上下文菜单和对话框。 它还适用于 web 视图发送到网站的接受语言 HTTP 头。 它采用的格式 `language[-country]` `language` 是 iso 639 中的2个字母代码， `country` 是 iso 3166 中的2个字母代码。

#### get_TargetCompatibleBrowserVersion 

需要与调用应用程序兼容的 Edge WebView2 运行时二进制文件的版本。

> public HRESULT [get_TargetCompatibleBrowserVersion](#get_targetcompatiblebrowserversion)（LPWSTR * value）

这将默认为与应用程序所使用的 SDK 版本相对应的 Edge WebView2 运行时版本。 此值的格式与 BrowserVersionString 属性和其他 BrowserVersion 值的格式相同。 仅考虑 BrowserVersion 值的版本部分。 如果存在信道后缀，则将其忽略。 实际使用的 Edge WebView2 运行时二进制文件的版本可能与指定的 TargetCompatibleBrowserVersion 不同。 它们只能保证兼容性。 可以在 ICoreWebView2Environment 的 BrowserVersionString 属性上检查实际版本。

#### put_AdditionalBrowserArguments 

设置 AdditionalBrowserArguments 属性。

> public HRESULT [put_AdditionalBrowserArguments](#put_additionalbrowserarguments)（LPCWSTR 值）

#### put_Language 

设置 "语言" 属性。

> public HRESULT [put_Language](#put_language)（LPCWSTR 值）

#### put_TargetCompatibleBrowserVersion 

设置 TargetCompatibleBrowserVersion。

> public HRESULT [put_TargetCompatibleBrowserVersion](#put_targetcompatiblebrowserversion)（LPCWSTR 值）

