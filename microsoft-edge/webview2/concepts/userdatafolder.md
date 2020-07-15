---
description: 了解如何管理 WebView2 应用程序中的用户数据文件夹
title: 管理 WebView2 应用程序中的用户数据文件夹。
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html、用户数据文件夹
ms.openlocfilehash: 870361e5f3edaea776538216c05e4114dc614342
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879149"
---
# 管理用户数据文件夹

WebView2 应用程序与用户数据文件夹交互以存储浏览器数据，如 cookie、权限和缓存资源。 WebView2 控件的每个实例都与一个用户数据文件夹相关联。 每个用户数据文件夹对用户来说都是唯一的。

## 最佳做法

用户数据文件夹由 WebView2 自动创建。 WebView2 开发人员控制用户数据文件夹的生命周期。 如果你的应用程序重新使用应用程序会话中的用户数据，请考虑保存用户数据文件夹，否则你可能会将其删除。 确定如何管理用户数据文件夹时，请考虑以下方案：

*   如果同一用户重复使用你的应用程序，并且该应用程序的 web 内容依赖于用户的数据，请保存用户数据文件夹。 如果多个用户重复使用你的应用程序，请为每个新用户创建一个新的用户数据文件夹，并保存每个用户的 "用户数据" 文件夹。
*   如果你的应用程序没有重复的用户，请为每个用户创建新的用户数据文件夹，并删除以前的用户数据文件夹。

## 创建用户数据文件夹

若要指定用户数据文件夹的位置，请 `userDataFolder` 在调用[ICoreWebView2Environment](../reference/win32/0-9-538/icorewebview2environment.md) （Win32）或[CoreWebView2Environment](../reference/dotnet/0-9-538/microsoft-web-webview2-core-corewebview2environment.md) （.net）时包括该参数。 创建后，WebView2 控件中的浏览器数据存储在的子文件夹中 `userDataFolder` 。 如果 `userDataFolder` 未指定，WebView2 将在默认位置创建用户数据文件夹，如下所示：

* 对于打包的 Windows 应用商店应用，默认的用户文件夹是 `ApplicationData\LocalFolder` 程序包文件夹中的子文件夹。
* 对于现有桌面应用，默认的用户数据文件夹是应用程序 + 的 exe 路径 `.WebView2` 。 我们建议你指定一个用户数据文件夹，并在存储所有其他应用数据的同一文件夹中创建一个用户数据文件夹，而不是使用默认设置。

## 删除用户数据文件夹

你的应用程序可能需要删除用户数据文件夹：

* 卸载你的应用时。 如果你要卸载打包的 Windows 应用商店应用，Windows 将自动删除用户数据文件夹。 
* 清理所有浏览数据历史记录。
* 恢复数据损坏。
* 删除以前的会话数据。 


> [!NOTE]
> WebView2 应用程序关闭后，用户数据文件夹中的文件可能仍在使用。 在这种情况下，请等待浏览器进程和所有子进程在删除文件夹之前退出。 你可以使用 WebView2 的属性检索浏览器进程的进程 id `BrowserProcessId` 。

## 共享用户数据文件夹

WebView2 控件可能会共享相同的用户数据文件夹，以便：

* 通过在一个浏览器进程中运行[优化系统资源](../reference/win32/0-9-538/icorewebview2.md#process-model)。
* 共享浏览器历史记录和缓存的资源。 

共享用户数据文件夹时，请考虑以下事项： 

1. 重新创建 WebView2 控件以使用[add_NewBrowserVersionAvailable](../reference/win32/0-9-538/icorewebview2environment.md#add_newbrowserversionavailable) （Win32）或[NewBrowserVersionAvailable](../reference/dotnet/0-9-538/microsoft-web-webview2-core-corewebview2environment.md#newbrowserversionavailable) （.net）事件更新浏览器版本时，请确保浏览器进程退出并关闭共享同一用户数据文件夹的 WebView2 控件。 若要检索浏览器进程的进程 id，请使用 `BrowserProcessId` WebView2 控件的属性。

2. 共享同一用户数据文件夹的 WebView2 控件必须对[ICoreWebView2Environment](../reference/win32/0-9-538/icorewebview2environment.md) （Win32）或[CoreWebView2Environment](../reference/dotnet/0-9-538/microsoft-web-webview2-core-corewebview2environment.md) （.net）使用相同的选项。 如果不是，WebView2 创建将失败 `HRESULT_FROM_WIN32(ERROR_INVALID_STATE)` 。 

若要隔离你的应用程序的不同部分或不需要在 WebView2 控件之间共享数据，你可以选择使用不同的用户数据文件夹。 例如，应用程序可能包含两个 WebView2 控件，一个用于显示广告，另一个用于显示应用程序内容。 在此方案中，开发人员可能选择对每个 WebView2 控件使用不同的用户数据文件夹。 

> [!NOTE]
> 每个 WebView2 浏览器进程都会占用额外的内存和磁盘空间。 因此，我们建议不要同时运行包含太多不同用户数据文件夹的 WebView2s。 
