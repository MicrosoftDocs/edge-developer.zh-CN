---
description: 了解如何在 WebView2 应用程序中管理用户数据文件夹
title: 在 WebView2 应用程序中管理用户数据文件夹。
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/06/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html、用户数据文件夹
ms.openlocfilehash: a6399e59f153d4446946937461e61667f325f4ae
ms.sourcegitcommit: 777b16ef10363f2dfd755f115ee2d4c81a8de46f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2021
ms.locfileid: "11535817"
---
# <a name="manage-the-user-data-folder"></a><span data-ttu-id="22f28-104">管理用户数据文件夹</span><span class="sxs-lookup"><span data-stu-id="22f28-104">Manage the User Data Folder</span></span>  

<span data-ttu-id="22f28-105">WebView2 应用程序与用户数据文件夹交互，以存储浏览器数据，如 Cookie、权限和缓存的资源。</span><span class="sxs-lookup"><span data-stu-id="22f28-105">WebView2 applications interact with user data folders to store browser data, such as cookies, permissions, and cached resources.</span></span>  <span data-ttu-id="22f28-106">WebView2 控件的每个实例都与一个用户数据文件夹关联。</span><span class="sxs-lookup"><span data-stu-id="22f28-106">Each instance of a WebView2 control is associated with a user data folder.</span></span>  <span data-ttu-id="22f28-107">每个用户数据文件夹对于用户都是唯一的。</span><span class="sxs-lookup"><span data-stu-id="22f28-107">Each user data folder is unique to a user.</span></span>  

## <a name="best-practices"></a><span data-ttu-id="22f28-108">最佳做法</span><span class="sxs-lookup"><span data-stu-id="22f28-108">Best Practices</span></span>  

<span data-ttu-id="22f28-109">用户数据文件夹由 WebView2 自动创建。</span><span class="sxs-lookup"><span data-stu-id="22f28-109">User data folders are created automatically by WebView2.</span></span>  <span data-ttu-id="22f28-110">WebView2 开发人员控制用户数据文件夹的生命周期。</span><span class="sxs-lookup"><span data-stu-id="22f28-110">WebView2 developers control the lifetime of the user data folder.</span></span>  <span data-ttu-id="22f28-111">如果应用程序重新使用来自应用程序会话的用户数据，请考虑保存用户数据文件夹，否则可以将其删除。</span><span class="sxs-lookup"><span data-stu-id="22f28-111">If your application re-uses user data from application sessions, consider saving the user data folders, otherwise you may delete them.</span></span>  <span data-ttu-id="22f28-112">在决定如何管理用户数据文件夹时，请考虑以下方案：</span><span class="sxs-lookup"><span data-stu-id="22f28-112">Consider the following scenarios when deciding how to manage your user data folders:</span></span>  

*   <span data-ttu-id="22f28-113">如果同一用户反复使用您的应用程序，并且应用程序的 Web 内容依赖于用户的数据，请保存用户数据文件夹。</span><span class="sxs-lookup"><span data-stu-id="22f28-113">If the same user uses your application repeatedly, and the web content of the application relies on the user's data, save the user data folder.</span></span>  <span data-ttu-id="22f28-114">如果多个用户重复使用您的应用程序，请为每个新用户创建一个新的用户数据文件夹，并保存每个用户的用户数据文件夹。</span><span class="sxs-lookup"><span data-stu-id="22f28-114">If multiple users use your application repeatedly, create a new user data folder for each new user, and save the user data folder of each user.</span></span>
*   <span data-ttu-id="22f28-115">如果应用程序没有重复用户，请为每个用户创建一个新的用户数据文件夹，并删除以前的用户数据文件夹。</span><span class="sxs-lookup"><span data-stu-id="22f28-115">If your application does not have repeat users, create a new user data folder for each user, and delete the previous user data folder.</span></span>  
    
## <a name="create-user-data-folders"></a><span data-ttu-id="22f28-116">创建用户数据文件夹</span><span class="sxs-lookup"><span data-stu-id="22f28-116">Create user data folders</span></span>  

<span data-ttu-id="22f28-117">若要指定用户数据文件夹的位置，在调用 `userDataFolder` [ICoreWebView2Environment](/microsoft-edge/webview2/reference/win32/icorewebview2environment) \ (Win32\) 或 [CoreWebView2Environment](/dotnet/api/microsoft.web.webview2.core.corewebview2environment) \ (.NET\) 时包括 参数。</span><span class="sxs-lookup"><span data-stu-id="22f28-117">To specify the location of the user data folder, include the `userDataFolder` parameter when calling [ICoreWebView2Environment](/microsoft-edge/webview2/reference/win32/icorewebview2environment) \(Win32\) or [CoreWebView2Environment](/dotnet/api/microsoft.web.webview2.core.corewebview2environment) \(.NET\).</span></span>  <span data-ttu-id="22f28-118">创建后，WebView2 控件中的浏览器数据存储在 的子文件夹内 `userDataFolder` 。</span><span class="sxs-lookup"><span data-stu-id="22f28-118">After creation, browser data from your WebView2 control is stored in a subfolder of `userDataFolder`.</span></span>  <span data-ttu-id="22f28-119">如果 `userDataFolder` 未指定，WebView2 将按如下方式在默认位置创建用户数据文件夹：</span><span class="sxs-lookup"><span data-stu-id="22f28-119">When `userDataFolder` is not specified, WebView2 creates user data folders at default locations as follows:</span></span>  

*   <span data-ttu-id="22f28-120">对于打包的 Windows 应用商店应用，默认用户文件夹是程序包文件夹中 `ApplicationData\LocalFolder` 的子文件夹。</span><span class="sxs-lookup"><span data-stu-id="22f28-120">For packaged Windows Store apps, the default user folder is the `ApplicationData\LocalFolder` subfolder in the package's  folder.</span></span>  
*   <span data-ttu-id="22f28-121">对于现有桌面应用，默认用户数据文件夹是应用程序 + 的 exe 路径 `.WebView2` 。</span><span class="sxs-lookup"><span data-stu-id="22f28-121">For existing desktop apps, the default user data folder is the exe path of your application + `.WebView2`.</span></span>  <span data-ttu-id="22f28-122">我们建议你指定用户数据文件夹，并且你在存储所有其他应用数据的同一文件夹中创建它，而不是使用默认值。</span><span class="sxs-lookup"><span data-stu-id="22f28-122">Instead of using the default, we recommend that you specify a user data folder, and that you create it in the same folder where all other app data is stored.</span></span>  
    
## <a name="delete-user-data-folders"></a><span data-ttu-id="22f28-123">删除用户数据文件夹</span><span class="sxs-lookup"><span data-stu-id="22f28-123">Delete user data folders</span></span>  

<span data-ttu-id="22f28-124">应用程序可能需要删除用户数据文件夹：</span><span class="sxs-lookup"><span data-stu-id="22f28-124">Your application may need to delete user data folders:</span></span>  

*   <span data-ttu-id="22f28-125">卸载应用时。</span><span class="sxs-lookup"><span data-stu-id="22f28-125">When uninstalling your app.</span></span>  <span data-ttu-id="22f28-126">如果要卸载打包的 Windows 应用商店应用，Windows 将自动删除用户数据文件夹。</span><span class="sxs-lookup"><span data-stu-id="22f28-126">If you are uninstalling packaged Windows Store apps, Windows deletes user data folders automatically.</span></span>  
*   <span data-ttu-id="22f28-127">清除所有浏览数据历史记录。</span><span class="sxs-lookup"><span data-stu-id="22f28-127">To clean up all browsing data history.</span></span>  
*   <span data-ttu-id="22f28-128">从数据损坏中恢复。</span><span class="sxs-lookup"><span data-stu-id="22f28-128">To recover from data corruption.</span></span>  
*   <span data-ttu-id="22f28-129">删除以前的会话数据。</span><span class="sxs-lookup"><span data-stu-id="22f28-129">To remove previous session data.</span></span>  
    
> [!NOTE]
> <span data-ttu-id="22f28-130">关闭 WebView2 应用程序后，用户数据文件夹中的文件可能仍在使用中。</span><span class="sxs-lookup"><span data-stu-id="22f28-130">Files in user data folders may still be in use after the WebView2 application is closed.</span></span>  <span data-ttu-id="22f28-131">在这种情况下，请等待浏览器进程及所有子进程退出，然后再删除该文件夹。</span><span class="sxs-lookup"><span data-stu-id="22f28-131">In this situation, wait for the browser process and all child processes to exit before deleting the folder.</span></span>  <span data-ttu-id="22f28-132">可以使用 WebView2 的 属性检索浏览器进程的进程 `BrowserProcessId` ID。</span><span class="sxs-lookup"><span data-stu-id="22f28-132">You may retrieve the process id of the browser process using the `BrowserProcessId` property of the WebView2.</span></span>  

## <a name="share-user-data-folders"></a><span data-ttu-id="22f28-133">共享用户数据文件夹</span><span class="sxs-lookup"><span data-stu-id="22f28-133">Share user data folders</span></span>  

<span data-ttu-id="22f28-134">WebView2 控件可以共享相同的用户数据文件夹，以：</span><span class="sxs-lookup"><span data-stu-id="22f28-134">WebView2 controls may share the same user data folders to:</span></span>  

*   <span data-ttu-id="22f28-135">[通过运行在](../concepts/process-model.md) 一个浏览器进程中优化系统资源。</span><span class="sxs-lookup"><span data-stu-id="22f28-135">[Optimize system resources](../concepts/process-model.md) by running in one browser process.</span></span>  
*   <span data-ttu-id="22f28-136">共享浏览器历史记录和缓存的资源。</span><span class="sxs-lookup"><span data-stu-id="22f28-136">Share browser history and cached resources.</span></span>  
    
<span data-ttu-id="22f28-137">共享用户数据文件夹时，请考虑以下事项：</span><span class="sxs-lookup"><span data-stu-id="22f28-137">Consider the following when sharing user data folders:</span></span>  

1.  <span data-ttu-id="22f28-138">当重新创建 WebView2 控件以使用 [add_NewBrowserVersionAvailable](/microsoft-edge/webview2/reference/win32/icorewebview2environment#add_newbrowserversionavailable) \ (Win32\) 或 [NewBrowserVersionAvailable](/dotnet/api/microsoft.web.webview2.core.corewebview2environment.newbrowserversionavailable) \ (.NET\) 事件更新浏览器版本时，请确保浏览器进程退出并关闭共享相同用户数据文件夹的 WebView2 控件。</span><span class="sxs-lookup"><span data-stu-id="22f28-138">When re-creating WebView2 controls to update browser versions using [add_NewBrowserVersionAvailable](/microsoft-edge/webview2/reference/win32/icorewebview2environment#add_newbrowserversionavailable) \(Win32\) or [NewBrowserVersionAvailable](/dotnet/api/microsoft.web.webview2.core.corewebview2environment.newbrowserversionavailable) \(.NET\) events, ensure browser processes exit and close WebView2 controls that share the same user data folder.</span></span>  <span data-ttu-id="22f28-139">若要检索浏览器进程的进程 ID，请使用 `BrowserProcessId` WebView2 控件的 属性。</span><span class="sxs-lookup"><span data-stu-id="22f28-139">To retrieve the process id of the browser process, use the `BrowserProcessId` property of the WebView2 control.</span></span>  
1.  <span data-ttu-id="22f28-140">共享相同用户数据文件夹的 WebView2 控件必须对 [ICoreWebView2Environment](/microsoft-edge/webview2/reference/win32/icorewebview2environment) \ (Win32\) 或 [CoreWebView2Environment](/dotnet/api/microsoft.web.webview2.core.corewebview2environment) \ (.NET\) 使用相同的选项。</span><span class="sxs-lookup"><span data-stu-id="22f28-140">WebView2 controls that share the same user data folder must use the same options for [ICoreWebView2Environment](/microsoft-edge/webview2/reference/win32/icorewebview2environment) \(Win32\) or [CoreWebView2Environment](/dotnet/api/microsoft.web.webview2.core.corewebview2environment) \(.NET\).</span></span>  <span data-ttu-id="22f28-141">如果没有，WebView2 的创建将失败 `HRESULT_FROM_WIN32(ERROR_INVALID_STATE)` 。</span><span class="sxs-lookup"><span data-stu-id="22f28-141">If not, the WebView2 creation will fail with `HRESULT_FROM_WIN32(ERROR_INVALID_STATE)`.</span></span>  
    
<span data-ttu-id="22f28-142">若要隔离应用程序的不同部分或不需要在 WebView2 控件之间共享数据，可以选择使用不同的用户数据文件夹。</span><span class="sxs-lookup"><span data-stu-id="22f28-142">To isolate different parts of your application or when sharing data between WebView2 controls is not needed, you may choose to use different user data folders.</span></span>  <span data-ttu-id="22f28-143">例如，应用程序可能由两个 WebView2 控件组成，一个控件用于显示广告，另一个控件用于显示应用程序内容。</span><span class="sxs-lookup"><span data-stu-id="22f28-143">For example, an application may consist of two WebView2 controls, one for displaying an advertisement and the other for displaying application content.</span></span>  <span data-ttu-id="22f28-144">在此方案中，开发人员可以选择针对每个 WebView2 控件使用不同的用户数据文件夹。</span><span class="sxs-lookup"><span data-stu-id="22f28-144">In this scenario, developers may opt to use different user data folders for each WebView2 control.</span></span>  

> [!NOTE]
> <span data-ttu-id="22f28-145">每个 WebView2 浏览器进程会占用额外的内存和磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="22f28-145">Each WebView2 browser process consumes additional memory and disk space.</span></span>  <span data-ttu-id="22f28-146">因此，我们建议不要同时运行包含过多不同用户数据文件夹的 WebView2。</span><span class="sxs-lookup"><span data-stu-id="22f28-146">Therefore, we recommend not running WebView2s with too many different user data folders at the same time.</span></span>  
