---
description: 了解如何管理 WebView2 应用程序中的用户数据文件夹
title: 管理 WebView2 应用程序中的用户数据文件夹。
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html、用户数据文件夹
ms.openlocfilehash: 5f341458a85bfab93bd2618b4d274ad6a1edefa2
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11010738"
---
# <span data-ttu-id="541b9-104">管理用户数据文件夹</span><span class="sxs-lookup"><span data-stu-id="541b9-104">Managing the User Data Folder</span></span>  

<span data-ttu-id="541b9-105">WebView2 应用程序与用户数据文件夹交互以存储浏览器数据，如 cookie、权限和缓存资源。</span><span class="sxs-lookup"><span data-stu-id="541b9-105">WebView2 applications interact with user data folders to store browser data, such as cookies, permissions, and cached resources.</span></span>  <span data-ttu-id="541b9-106">WebView2 控件的每个实例都与一个用户数据文件夹相关联。</span><span class="sxs-lookup"><span data-stu-id="541b9-106">Each instance of a WebView2 control is associated with a user data folder.</span></span>  <span data-ttu-id="541b9-107">每个用户数据文件夹对用户来说都是唯一的。</span><span class="sxs-lookup"><span data-stu-id="541b9-107">Each user data folder is unique to a user.</span></span>  

## <span data-ttu-id="541b9-108">最佳做法</span><span class="sxs-lookup"><span data-stu-id="541b9-108">Best Practices</span></span>  

<span data-ttu-id="541b9-109">用户数据文件夹由 WebView2 自动创建。</span><span class="sxs-lookup"><span data-stu-id="541b9-109">User data folders are created automatically by WebView2.</span></span>  <span data-ttu-id="541b9-110">WebView2 开发人员控制用户数据文件夹的生命周期。</span><span class="sxs-lookup"><span data-stu-id="541b9-110">WebView2 developers control the lifetime of the user data folder.</span></span>  <span data-ttu-id="541b9-111">如果你的应用程序重新使用应用程序会话中的用户数据，请考虑保存用户数据文件夹，否则你可能会将其删除。</span><span class="sxs-lookup"><span data-stu-id="541b9-111">If your application re-uses user data from application sessions, consider saving the user data folders, otherwise you may delete them.</span></span>  <span data-ttu-id="541b9-112">确定如何管理用户数据文件夹时，请考虑以下方案：</span><span class="sxs-lookup"><span data-stu-id="541b9-112">Consider the following scenarios when deciding how to manage your user data folders:</span></span>  

*   <span data-ttu-id="541b9-113">如果同一用户重复使用你的应用程序，并且该应用程序的 web 内容依赖于用户的数据，请保存用户数据文件夹。</span><span class="sxs-lookup"><span data-stu-id="541b9-113">If the same user uses your application repeatedly, and the web content of the application relies on the user's data, save the user data folder.</span></span>  <span data-ttu-id="541b9-114">如果多个用户重复使用你的应用程序，请为每个新用户创建一个新的用户数据文件夹，并保存每个用户的 "用户数据" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="541b9-114">If multiple users use your application repeatedly, create a new user data folder for each new user, and save the user data folder of each user.</span></span>
*   <span data-ttu-id="541b9-115">如果你的应用程序没有重复的用户，请为每个用户创建新的用户数据文件夹，并删除以前的用户数据文件夹。</span><span class="sxs-lookup"><span data-stu-id="541b9-115">If your application does not have repeat users, create a new user data folder for each user, and delete the previous user data folder.</span></span>  

## <span data-ttu-id="541b9-116">创建用户数据文件夹</span><span class="sxs-lookup"><span data-stu-id="541b9-116">Create user data folders</span></span>  

<span data-ttu-id="541b9-117">若要指定用户数据文件夹的位置，请 `userDataFolder` 在调用 [ICoreWebView2Environment](../reference/win32/0-9-622/icorewebview2environment.md) \ (Win32 \ ) 或 [CoreWebView2Environment](../reference/dotnet/0-9-628/microsoft-web-webview2-core-corewebview2environment.md) \ ( .net \ ) 时包括该参数。</span><span class="sxs-lookup"><span data-stu-id="541b9-117">To specify the location of the user data folder, include the `userDataFolder` parameter when calling [ICoreWebView2Environment](../reference/win32/0-9-622/icorewebview2environment.md) \(Win32\) or [CoreWebView2Environment](../reference/dotnet/0-9-628/microsoft-web-webview2-core-corewebview2environment.md) \(.NET\).</span></span>  <span data-ttu-id="541b9-118">创建后，WebView2 控件中的浏览器数据存储在的子文件夹中 `userDataFolder` 。</span><span class="sxs-lookup"><span data-stu-id="541b9-118">After creation, browser data from your WebView2 control is stored in a subfolder of `userDataFolder`.</span></span>  <span data-ttu-id="541b9-119">如果 `userDataFolder` 未指定，WebView2 将在默认位置创建用户数据文件夹，如下所示：</span><span class="sxs-lookup"><span data-stu-id="541b9-119">When `userDataFolder` is not specified, WebView2 creates user data folders at default locations as follows:</span></span>  

*   <span data-ttu-id="541b9-120">对于打包的 Windows 应用商店应用，默认的用户文件夹是 `ApplicationData\LocalFolder` 程序包文件夹中的子文件夹。</span><span class="sxs-lookup"><span data-stu-id="541b9-120">For packaged Windows Store apps, the default user folder is the `ApplicationData\LocalFolder` subfolder in the package's  folder.</span></span>  
*   <span data-ttu-id="541b9-121">对于现有桌面应用，默认的用户数据文件夹是应用程序 + 的 exe 路径 `.WebView2` 。</span><span class="sxs-lookup"><span data-stu-id="541b9-121">For existing desktop apps, the default user data folder is the exe path of your application + `.WebView2`.</span></span>  <span data-ttu-id="541b9-122">我们建议你指定一个用户数据文件夹，并在存储所有其他应用数据的同一文件夹中创建一个用户数据文件夹，而不是使用默认设置。</span><span class="sxs-lookup"><span data-stu-id="541b9-122">Instead of using the default, we recommend that you specify a user data folder, and that you create it in the same folder where all other app data is stored.</span></span>  

## <span data-ttu-id="541b9-123">删除用户数据文件夹</span><span class="sxs-lookup"><span data-stu-id="541b9-123">Delete user data folders</span></span>  

<span data-ttu-id="541b9-124">你的应用程序可能需要删除用户数据文件夹：</span><span class="sxs-lookup"><span data-stu-id="541b9-124">Your application may need to delete user data folders:</span></span>  

*   <span data-ttu-id="541b9-125">卸载你的应用时。</span><span class="sxs-lookup"><span data-stu-id="541b9-125">When uninstalling your app.</span></span>  <span data-ttu-id="541b9-126">如果你要卸载打包的 Windows 应用商店应用，Windows 将自动删除用户数据文件夹。</span><span class="sxs-lookup"><span data-stu-id="541b9-126">If you are uninstalling packaged Windows Store apps, Windows deletes user data folders automatically.</span></span>  
*   <span data-ttu-id="541b9-127">清理所有浏览数据历史记录。</span><span class="sxs-lookup"><span data-stu-id="541b9-127">To clean up all browsing data history.</span></span>  
*   <span data-ttu-id="541b9-128">恢复数据损坏。</span><span class="sxs-lookup"><span data-stu-id="541b9-128">To recover from data corruption.</span></span>  
*   <span data-ttu-id="541b9-129">删除以前的会话数据。</span><span class="sxs-lookup"><span data-stu-id="541b9-129">To remove previous session data.</span></span>  

> [!NOTE]
> <span data-ttu-id="541b9-130">WebView2 应用程序关闭后，用户数据文件夹中的文件可能仍在使用。</span><span class="sxs-lookup"><span data-stu-id="541b9-130">Files in user data folders may still be in use after the WebView2 application is closed.</span></span>  <span data-ttu-id="541b9-131">在这种情况下，请等待浏览器进程和所有子进程在删除文件夹之前退出。</span><span class="sxs-lookup"><span data-stu-id="541b9-131">In this situation, wait for the browser process and all child processes to exit before deleting the folder.</span></span>  <span data-ttu-id="541b9-132">你可以使用 WebView2 的属性检索浏览器进程的进程 id `BrowserProcessId` 。</span><span class="sxs-lookup"><span data-stu-id="541b9-132">You may retrieve the process id of the browser process using the `BrowserProcessId` property of the WebView2.</span></span>  

## <span data-ttu-id="541b9-133">共享用户数据文件夹</span><span class="sxs-lookup"><span data-stu-id="541b9-133">Share user data folders</span></span>  

<span data-ttu-id="541b9-134">WebView2 控件可能会共享相同的用户数据文件夹，以便：</span><span class="sxs-lookup"><span data-stu-id="541b9-134">WebView2 controls may share the same user data folders to:</span></span>  

*   <span data-ttu-id="541b9-135">通过在一个浏览器进程中运行[优化系统资源](../concepts/process-model.md)。</span><span class="sxs-lookup"><span data-stu-id="541b9-135">[Optimize system resources](../concepts/process-model.md) by running in one browser process.</span></span>  
*   <span data-ttu-id="541b9-136">共享浏览器历史记录和缓存的资源。</span><span class="sxs-lookup"><span data-stu-id="541b9-136">Share browser history and cached resources.</span></span>  

<span data-ttu-id="541b9-137">共享用户数据文件夹时，请考虑以下事项：</span><span class="sxs-lookup"><span data-stu-id="541b9-137">Consider the following when sharing user data folders:</span></span>  

1.  <span data-ttu-id="541b9-138">重新创建 WebView2 控件以使用 [add_NewBrowserVersionAvailable](../reference/win32/0-9-622/icorewebview2environment.md#add_newbrowserversionavailable) \ (Win32 \ ) 或 [NewBrowserVersionAvailable](../reference/dotnet/0-9-628/microsoft-web-webview2-core-corewebview2environment.md#newbrowserversionavailable) \ ( .net \ ) 事件来更新浏览器版本时，请确保浏览器进程退出并关闭共享同一用户数据文件夹的 WebView2 控件。</span><span class="sxs-lookup"><span data-stu-id="541b9-138">When re-creating WebView2 controls to update browser versions using [add_NewBrowserVersionAvailable](../reference/win32/0-9-622/icorewebview2environment.md#add_newbrowserversionavailable) \(Win32\) or [NewBrowserVersionAvailable](../reference/dotnet/0-9-628/microsoft-web-webview2-core-corewebview2environment.md#newbrowserversionavailable) \(.NET\) events, ensure browser processes exit and close WebView2 controls that share the same user data folder.</span></span>  <span data-ttu-id="541b9-139">若要检索浏览器进程的进程 id，请使用 `BrowserProcessId` WebView2 控件的属性。</span><span class="sxs-lookup"><span data-stu-id="541b9-139">To retrieve the process id of the browser process, use the `BrowserProcessId` property of the WebView2 control.</span></span>  

2.  <span data-ttu-id="541b9-140">共享同一用户数据文件夹的 WebView2 控件必须使用与 [ICoreWebView2Environment](../reference/win32/0-9-622/icorewebview2environment.md) \ (Win32 \ ) 或 [CoreWebView2Environment](../reference/dotnet/0-9-628/microsoft-web-webview2-core-corewebview2environment.md) \ ( .net \ ) 相同的选项。</span><span class="sxs-lookup"><span data-stu-id="541b9-140">WebView2 controls that share the same user data folder must use the same options for [ICoreWebView2Environment](../reference/win32/0-9-622/icorewebview2environment.md) \(Win32\) or [CoreWebView2Environment](../reference/dotnet/0-9-628/microsoft-web-webview2-core-corewebview2environment.md) \(.NET\).</span></span>  <span data-ttu-id="541b9-141">如果不是，WebView2 创建将失败 `HRESULT_FROM_WIN32(ERROR_INVALID_STATE)` 。</span><span class="sxs-lookup"><span data-stu-id="541b9-141">If not, the WebView2 creation will fail with `HRESULT_FROM_WIN32(ERROR_INVALID_STATE)`.</span></span>  

<span data-ttu-id="541b9-142">若要隔离你的应用程序的不同部分或不需要在 WebView2 控件之间共享数据，你可以选择使用不同的用户数据文件夹。</span><span class="sxs-lookup"><span data-stu-id="541b9-142">To isolate different parts of your application or when sharing data between WebView2 controls is not needed, you may choose to use different user data folders.</span></span>  <span data-ttu-id="541b9-143">例如，应用程序可能包含两个 WebView2 控件，一个用于显示广告，另一个用于显示应用程序内容。</span><span class="sxs-lookup"><span data-stu-id="541b9-143">For example, an application may consist of two WebView2 controls, one for displaying an advertisement and the other for displaying application content.</span></span>  <span data-ttu-id="541b9-144">在此方案中，开发人员可能选择对每个 WebView2 控件使用不同的用户数据文件夹。</span><span class="sxs-lookup"><span data-stu-id="541b9-144">In this scenario, developers may opt to use different user data folders for each WebView2 control.</span></span>  

> [!NOTE]
> <span data-ttu-id="541b9-145">每个 WebView2 浏览器进程都会占用额外的内存和磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="541b9-145">Each WebView2 browser process consumes additional memory and disk space.</span></span>  <span data-ttu-id="541b9-146">因此，我们建议不要同时运行包含太多不同用户数据文件夹的 WebView2s。</span><span class="sxs-lookup"><span data-stu-id="541b9-146">Therefore, we recommend not running WebView2s with too many different user data folders at the same time.</span></span>  
