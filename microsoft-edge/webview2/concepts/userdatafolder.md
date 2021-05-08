---
description: 了解如何在 WebView2 应用程序中管理用户数据文件夹
title: 在 WebView2 应用程序中管理用户数据文件夹。
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/14/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html、用户数据文件夹
ms.openlocfilehash: ff11c4e83fa931a97ed1b5c8afa4a30b5c0b5d25
ms.sourcegitcommit: e3cd336c9448277e0dde3b9da1521b5cbc7c44d2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2021
ms.locfileid: "11536357"
---
# <a name="managing-the-user-data-folder"></a>管理用户数据文件夹  

WebView2 应用程序与用户数据文件夹交互，以存储浏览器数据，如 Cookie、权限和缓存的资源。  WebView2 控件的每个实例都与一个用户数据文件夹关联。  每个用户数据文件夹对于用户都是唯一的。  

## <a name="best-practices"></a>最佳做法  

用户数据文件夹由 WebView2 自动创建。  WebView2 开发人员控制用户数据文件夹的生命周期。  如果应用程序重新使用来自应用程序会话的用户数据，请考虑保存用户数据文件夹，否则可以将其删除。  在决定如何管理用户数据文件夹时，请考虑以下方案：  

*   如果同一用户反复使用您的应用程序，并且应用程序的 Web 内容依赖于用户的数据，请保存用户数据文件夹。  如果多个用户重复使用您的应用程序，请为每个新用户创建一个新的用户数据文件夹，并保存每个用户的用户数据文件夹。
*   如果应用程序没有重复用户，请为每个用户创建一个新的用户数据文件夹，并删除以前的用户数据文件夹。  

## <a name="create-user-data-folders"></a>创建用户数据文件夹  

若要指定用户数据文件夹的位置，在调用 `userDataFolder` [ICoreWebView2Environment](/microsoft-edge/webview2/reference/win32/icorewebview2environment) \ (Win32\) 或 [CoreWebView2Environment](/dotnet/api/microsoft.web.webview2.core.corewebview2environment) \ (.NET\) 时包括 参数。  创建后，WebView2 控件中的浏览器数据存储在 的子文件夹内 `userDataFolder` 。  如果 `userDataFolder` 未指定，WebView2 将按如下方式在默认位置创建用户数据文件夹：  

*   对于Windows应用商店应用，默认用户文件夹是程序包文件夹中 `ApplicationData\LocalFolder` 的子文件夹。  
*   对于现有桌面应用，默认用户数据文件夹是应用程序 + 的 exe 路径 `.WebView2` 。  我们建议你指定用户数据文件夹，并且你在存储所有其他应用数据的同一文件夹中创建它，而不是使用默认值。  

## <a name="delete-user-data-folders"></a>删除用户数据文件夹  

应用程序可能需要删除用户数据文件夹：  

*   卸载应用时。  如果要卸载已打包Windows应用商店应用，Windows自动删除用户数据文件夹。  
*   清除所有浏览数据历史记录。  
*   从数据损坏中恢复。  
*   删除以前的会话数据。  

> [!NOTE]
> 关闭 WebView2 应用程序后，用户数据文件夹中的文件可能仍在使用中。  在这种情况下，请等待浏览器进程及所有子进程退出，然后再删除该文件夹。  可以使用 WebView2 的 属性检索浏览器进程的进程 `BrowserProcessId` ID。  

## <a name="share-user-data-folders"></a>共享用户数据文件夹  

WebView2 控件可以共享相同的用户数据文件夹，以：  

*   [通过运行在](../concepts/process-model.md) 一个浏览器进程中优化系统资源。  
*   共享浏览器历史记录和缓存的资源。  

共享用户数据文件夹时，请考虑以下事项：  

1.  当重新创建 WebView2 控件以使用 [add_NewBrowserVersionAvailable](/microsoft-edge/webview2/reference/win32/icorewebview2environment#add_newbrowserversionavailable) \ (Win32\) 或 [NewBrowserVersionAvailable](/dotnet/api/microsoft.web.webview2.core.corewebview2environment.newbrowserversionavailable) \ (.NET\) 事件更新浏览器版本时，请确保浏览器进程退出并关闭共享相同用户数据文件夹的 WebView2 控件。  若要检索浏览器进程的进程 ID，请使用 `BrowserProcessId` WebView2 控件的 属性。  

2.  共享相同用户数据文件夹的 WebView2 控件必须对 [ICoreWebView2Environment](/microsoft-edge/webview2/reference/win32/icorewebview2environment) \ (Win32\) 或 [CoreWebView2Environment](/dotnet/api/microsoft.web.webview2.core.corewebview2environment) \ (.NET\) 使用相同的选项。  如果没有，WebView2 的创建将失败 `HRESULT_FROM_WIN32(ERROR_INVALID_STATE)` 。  

若要隔离应用程序的不同部分或不需要在 WebView2 控件之间共享数据，可以选择使用不同的用户数据文件夹。  例如，应用程序可能由两个 WebView2 控件组成，一个控件用于显示广告，另一个控件用于显示应用程序内容。  在此方案中，开发人员可以选择针对每个 WebView2 控件使用不同的用户数据文件夹。  

> [!NOTE]
> 每个 WebView2 浏览器进程会占用额外的内存和磁盘空间。  因此，我们建议不要同时运行包含过多不同用户数据文件夹的 WebView2。  
