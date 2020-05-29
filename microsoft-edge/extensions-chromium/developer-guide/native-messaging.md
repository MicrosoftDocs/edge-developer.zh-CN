---
description: Chrome 文档的原始消息区别
title: 本机消息传递
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/31/2019
ms.topic: article
ms.prod: microsoft-edge-chromium
keywords: edge-chromium、扩展开发、浏览器扩展、addons、合作伙伴中心、开发人员
ms.openlocfilehash: 0fe45ea681c54ddea7b27a8d954022b8bda45770
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563380"
---
# <span data-ttu-id="bcffe-104">本机消息传递</span><span class="sxs-lookup"><span data-stu-id="bcffe-104">Native Messaging</span></span>  

<span data-ttu-id="bcffe-105">Microsoft Edge 现在允许从 Microsoft Edge Addons 目录 \ （Microsoft Edge Addons \）安装扩展，以使用消息传递 Api 与本机应用程序交换消息。</span><span class="sxs-lookup"><span data-stu-id="bcffe-105">Microsoft Edge now allows Extension installed from Microsoft Edge Addons catalog \(Microsoft Edge Addons\) to exchange messages with a native application using message passing APIs.</span></span>  <span data-ttu-id="bcffe-106">若要启用该功能，需要在实现本机应用程序的本机消息传递主机时确保执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="bcffe-106">To enable the feature, you need to make sure of following things while implementing native messaging host of your Native Application.</span></span>  

<!--
 > [!NOTE]
> Native messaging is currently not supported on macOS and Linux version of Microsoft Edge.  This feature support is planned to be implemented soon.  -->  

1.  <span data-ttu-id="bcffe-107">**本机消息主机**：</span><span class="sxs-lookup"><span data-stu-id="bcffe-107">**Native messaging host**:</span></span>  
    
    <span data-ttu-id="bcffe-108">为了注册本机消息主机，应用程序必须安装定义本机消息主机配置的清单文件。</span><span class="sxs-lookup"><span data-stu-id="bcffe-108">In order to register a native messaging host the application must install a manifest file that defines the native messaging host configuration.</span></span>  <span data-ttu-id="bcffe-109">下面是清单文件的示例：</span><span class="sxs-lookup"><span data-stu-id="bcffe-109">Below is an example of the manifest file:</span></span>  
    
    ```xml
    {
        "name": "com.my_company.my_application",
        "description": "My Application",
        "path": "C:\\Program Files\\My Application\\chrome_native_messaging_host.exe",
        "type": "stdio",
        "allowed_origins": [
            "chrome-extension://knldjmfmopnpolahpmmgbagdohdnhkik/"
        ]
    }
    ```  
    
<span data-ttu-id="bcffe-110">本机消息主机清单文件必须是有效的 JSON，并且包含以下字段：</span><span class="sxs-lookup"><span data-stu-id="bcffe-110">The native messaging host manifest file must be valid JSON and contains the following fields:</span></span>  

| <span data-ttu-id="bcffe-111">名称</span><span class="sxs-lookup"><span data-stu-id="bcffe-111">Name</span></span> | <span data-ttu-id="bcffe-112">描述</span><span class="sxs-lookup"><span data-stu-id="bcffe-112">Description</span></span> |  
|:--- |:--- |  
| `name` | <span data-ttu-id="bcffe-113">本机消息主机的名称。</span><span class="sxs-lookup"><span data-stu-id="bcffe-113">Name of the native messaging host.</span></span> <span data-ttu-id="bcffe-114">客户端将此字符串传递给 `runtime.connectNative` 或 `runtime.sendNativeMessage` 。</span><span class="sxs-lookup"><span data-stu-id="bcffe-114">Clients pass this string to `runtime.connectNative` or `runtime.sendNativeMessage`.</span></span>  <span data-ttu-id="bcffe-115">此名称必须仅包含小写字母数字字符、下划线和点符。</span><span class="sxs-lookup"><span data-stu-id="bcffe-115">This name must only contain lowercase alphanumeric characters, underscores, and dots.</span></span>  <span data-ttu-id="bcffe-116">名称不能以点开始或结束，并且一个点后面不得跟另一个点。</span><span class="sxs-lookup"><span data-stu-id="bcffe-116">The name must not start or end with a dot, and a dot must not be followed by another dot.</span></span> |  
| `description` | <span data-ttu-id="bcffe-117">简短的应用程序说明。</span><span class="sxs-lookup"><span data-stu-id="bcffe-117">Short application description.</span></span> |  
| `path` | <span data-ttu-id="bcffe-118">本机消息主机二进制文件的路径。</span><span class="sxs-lookup"><span data-stu-id="bcffe-118">Path to the native messaging host binary.</span></span>  <span data-ttu-id="bcffe-119">在 Windows 上，路径可能相对于清单文件所在的目录。</span><span class="sxs-lookup"><span data-stu-id="bcffe-119">On Windows, the path may be relative to the directory in which the manifest file is located.</span></span>  <span data-ttu-id="bcffe-120">在 macOS 上，路径必须是绝对路径。</span><span class="sxs-lookup"><span data-stu-id="bcffe-120">On macOS, the path must be absolute.</span></span>  <span data-ttu-id="bcffe-121">将启动主机进程，并将当前目录设置为包含主机二进制文件的目录。</span><span class="sxs-lookup"><span data-stu-id="bcffe-121">The host process is started with the current directory set to the directory that contains the host binary.</span></span> <span data-ttu-id="bcffe-122">例如，如果此参数设置为 `C:\Application\nm_host.exe` ，将使用当前目录启动二进制文件 `C:\Application\` 。</span><span class="sxs-lookup"><span data-stu-id="bcffe-122">For example if this parameter is set to `C:\Application\nm_host.exe`, the binary is started using the current directory `C:\Application\`.</span></span> |  
| `type` | <span data-ttu-id="bcffe-123">用于与本机消息主机通信的接口类型。</span><span class="sxs-lookup"><span data-stu-id="bcffe-123">Type of the interface used to communicate with the native messaging host.</span></span>  <span data-ttu-id="bcffe-124">目前，此参数仅有一个可能的值： `stdio` 。</span><span class="sxs-lookup"><span data-stu-id="bcffe-124">Currently there is only one possible value for this parameter: `stdio`.</span></span>  <span data-ttu-id="bcffe-125">此值表示 Chrome 应使用 `stdin` 并与 `stdout` 主机通信。</span><span class="sxs-lookup"><span data-stu-id="bcffe-125">This value indicates that Chrome should use `stdin` and `stdout` to communicate with the host.</span></span> |  
| `allowed_origins` |  <span data-ttu-id="bcffe-126">应访问本机消息主机的扩展列表。</span><span class="sxs-lookup"><span data-stu-id="bcffe-126">list of Extension that should access to the native messaging host.</span></span>  <span data-ttu-id="bcffe-127">若要使你的本机应用程序可识别 Microsoft Edge Addons 扩展并与之通信，请 `allowedorigins` `extension://[Microsoft-Catalog-extensionID]` 在你的本机消息主机清单文件中设置为。</span><span class="sxs-lookup"><span data-stu-id="bcffe-127">To enable your Native Application identify and communicate with Microsoft Edge Addons Extension, set `allowedorigins` to `extension://[Microsoft-Catalog-extensionID]` in your native messaging host manifest file.</span></span> |  

1.  **<span data-ttu-id="bcffe-128">本机消息主机位置</span><span class="sxs-lookup"><span data-stu-id="bcffe-128">Native messaging host location</span></span>**  
    
    <span data-ttu-id="bcffe-129">清单文件的位置取决于平台。</span><span class="sxs-lookup"><span data-stu-id="bcffe-129">The location of the manifest file depends on the platform.</span></span>  
    
    <span data-ttu-id="bcffe-130">在 Windows 上，清单文件可能位于文件系统中的任何位置。</span><span class="sxs-lookup"><span data-stu-id="bcffe-130">On Windows, the manifest file may be located anywhere in the file system.</span></span>  <span data-ttu-id="bcffe-131">应用程序安装程序必须创建注册表项</span><span class="sxs-lookup"><span data-stu-id="bcffe-131">The application installer must create registry key</span></span>  
    
    `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_application`  
    <span data-ttu-id="bcffe-132">或者</span><span class="sxs-lookup"><span data-stu-id="bcffe-132">or</span></span>  
    `HKEY_CURRENT_USER\SOFTWARE\Google\Chrome\NativeMessagingHosts\com.my_company.my_application`<span data-ttu-id="bcffe-133">,</span><span class="sxs-lookup"><span data-stu-id="bcffe-133">,</span></span>  
    
    <span data-ttu-id="bcffe-134">并将该注册表项的默认值设置为清单文件的完整路径。</span><span class="sxs-lookup"><span data-stu-id="bcffe-134">and set default value of that key to the full path to the manifest file.</span></span>  <span data-ttu-id="bcffe-135">例如，使用以下命令：</span><span class="sxs-lookup"><span data-stu-id="bcffe-135">For example, using the following command:</span></span>  
    
    ```shell
    REG ADD "HKCU\Software\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_application" /ve /t REG_SZ /d "C:\path\to\nmh-manifest.json" /f
    ```  
    
    <span data-ttu-id="bcffe-136">或使用以下 .reg 文件：</span><span class="sxs-lookup"><span data-stu-id="bcffe-136">or using the following .reg file:</span></span>  
    
    ```shell
    Windows Registry Editor Version 5.00
    [HKEY_CURRENT_USER\Software\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_application]
    @="C:\\path\\to\\nmh-manifest.json"
    ```  
    
    <span data-ttu-id="bcffe-137">当 Microsoft Edge 寻找本机邮件主机时，首先查询32位注册表，然后是64位的注册表。</span><span class="sxs-lookup"><span data-stu-id="bcffe-137">When Microsoft Edge looks for native messaging hosts, the 32-bit registry is queried first, then the 64-bit registry.</span></span>  

<span data-ttu-id="bcffe-138">在 macOS 上，系统范围内的本机消息主机在固定位置查找，而用户级的本机消息主机在用户配置文件目录中的子目录中查找 `NativeMessagingHosts` 。</span><span class="sxs-lookup"><span data-stu-id="bcffe-138">On macOS, the system-wide native messaging hosts are looked up at a fixed location, while the user-level native messaging hosts are looked up in a subdirectory within the user profile directory called `NativeMessagingHosts`.</span></span>  

<span data-ttu-id="bcffe-139">MacOS \ （系统范围 \）上的 Microsoft Edge：</span><span class="sxs-lookup"><span data-stu-id="bcffe-139">Microsoft Edge on macOS \(system-wide\) :</span></span>  
`/Library/Microsoft/Edge/NativeMessagingHosts/com.my_company.my_application.json`  

<span data-ttu-id="bcffe-140">MacOS \ 上的 Microsoft Edge \ （特定于用户的默认路径 \）：</span><span class="sxs-lookup"><span data-stu-id="bcffe-140">Microsoft Edge on macOS \(user-specific, default path\):</span></span>  
`~/Library/Application Support/Microsoft Edge <ChannelName>/ NativeMessagingHosts/com.my_company.my_application.json`  

`<ChannelName>` <span data-ttu-id="bcffe-141">可以是 "" "" 设备 "、" 开发 "或" Beta "。</span><span class="sxs-lookup"><span data-stu-id="bcffe-141">may be Canary, Dev, or Beta.</span></span> <span data-ttu-id="bcffe-142">对于稳定通道，仅 `Microsoft Edge` 应使用， `<ChannelName`>"不是必需的。</span><span class="sxs-lookup"><span data-stu-id="bcffe-142">For stable channel, only `Microsoft Edge` should be used, `<ChannelName`>\` is not required.</span></span>

<!-- image links -->  

<!-- links -->  

> [!NOTE]
> <span data-ttu-id="bcffe-143">此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="bcffe-143">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="bcffe-144">可在[此处](https://developer.chrome.com/extensions/nativeMessaging)找到原始页面。</span><span class="sxs-lookup"><span data-stu-id="bcffe-144">The original page is found [here](https://developer.chrome.com/extensions/nativeMessaging).</span></span>  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
<span data-ttu-id="bcffe-146">此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="bcffe-146">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies
