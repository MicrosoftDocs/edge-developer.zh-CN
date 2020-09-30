---
description: 本机消息文档
title: 本机消息传递
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium、扩展开发、浏览器扩展、addons、合作伙伴中心、开发人员
ms.openlocfilehash: 9d33fc4e8c9449d539b6ea82cca87c3aad4d564e
ms.sourcegitcommit: 39636248d0266730089aa2e57b9cf04d9feb363d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/29/2020
ms.locfileid: "11088553"
---
# <span data-ttu-id="ff713-104">本机消息传递</span><span class="sxs-lookup"><span data-stu-id="ff713-104">Native messaging</span></span>  

<span data-ttu-id="ff713-105">扩展可以使用消息传递 Api 与用户设备上安装的本机 Win32 应用程序进行通信。</span><span class="sxs-lookup"><span data-stu-id="ff713-105">Extensions can communicate with a native Win32 application installed on a user’s device using message passing APIs.</span></span> <span data-ttu-id="ff713-106">本机应用程序主机可以使用标准输入和标准输出发送和接收带有扩展的消息。</span><span class="sxs-lookup"><span data-stu-id="ff713-106">The native application host can send and receive messages with extensions using standard input and standard output.</span></span> <span data-ttu-id="ff713-107">使用本机消息的扩展安装在与任何其他扩展类似的 Microsoft Edge 中。</span><span class="sxs-lookup"><span data-stu-id="ff713-107">Extensions using native messaging are installed in Microsoft Edge similar to any other extension.</span></span> <span data-ttu-id="ff713-108">但是，本机应用程序不是由 Microsoft Edge 安装或管理的。</span><span class="sxs-lookup"><span data-stu-id="ff713-108">However, native applications are not installed or managed by Microsoft Edge.</span></span>

<span data-ttu-id="ff713-109">若要获取扩展和本机应用程序宿主，可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ff713-109">To acquire the extension and native application host, you can:</span></span>

1. <span data-ttu-id="ff713-110">将扩展和主机打包在一起。</span><span class="sxs-lookup"><span data-stu-id="ff713-110">Package the extension and the host together.</span></span> <span data-ttu-id="ff713-111">当用户安装程序包时，将同时安装扩展和主机。</span><span class="sxs-lookup"><span data-stu-id="ff713-111">When users install the package, both the extension and the host are installed.</span></span>
1. <span data-ttu-id="ff713-112">从 [Microsoft Edge 加载项存储区][EdgeAddons]安装扩展，并让你的扩展提示用户安装主机。</span><span class="sxs-lookup"><span data-stu-id="ff713-112">Install the extension from the [Microsoft Edge Add-ons store][EdgeAddons], and have your extension prompt users to install the host.</span></span> 

<span data-ttu-id="ff713-113">请参阅下面的步骤以设置您的扩展，以通过本机应用程序主机发送和接收邮件。</span><span class="sxs-lookup"><span data-stu-id="ff713-113">Refer to the steps below to setup your extension to send and receive messages with native application hosts.</span></span>

### <span data-ttu-id="ff713-114">步骤1：向扩展清单添加权限</span><span class="sxs-lookup"><span data-stu-id="ff713-114">Step 1: Add permissions to the extension manifest</span></span>

<span data-ttu-id="ff713-115">将 nativeMessaging 权限添加到文件的扩展 **manifest.js** 。</span><span class="sxs-lookup"><span data-stu-id="ff713-115">Add the nativeMessaging permission to the extension’s **manifest.json** file.</span></span> <span data-ttu-id="ff713-116">下面是 manifest.js的示例：</span><span class="sxs-lookup"><span data-stu-id="ff713-116">Below is an example of manifest.json:</span></span>

```json
    {
          "name": "Native Messaging Example",
          "version": "1.0",
          "manifest_version": 2, 
          "description": "Send a message to a native application.",
          "app": { 
              "launch": { 
                  "local_path": "main.html" } 
                 }, 
          "icons": { 
              "128": "icon-128.png"}, 
          "permissions": ["nativeMessaging"] 
    }
```

### <span data-ttu-id="ff713-117">步骤2：创建本机消息主机清单文件</span><span class="sxs-lookup"><span data-stu-id="ff713-117">Step 2: Create your native messaging host manifest file</span></span>
    
<span data-ttu-id="ff713-118">本机应用程序必须提供本机消息主机清单文件。</span><span class="sxs-lookup"><span data-stu-id="ff713-118">Native applications must provide a native messaging host manifest file.</span></span> <span data-ttu-id="ff713-119">此清单文件包含本机消息传递主机可执行文件的路径、与扩展的通信方法以及可与之通信的允许扩展的列表。</span><span class="sxs-lookup"><span data-stu-id="ff713-119">This manifest file contains the path to the native messaging host executable, the method of communication with the extension, and a list of allowed extensions it can communicate with.</span></span> <span data-ttu-id="ff713-120">浏览器读取和验证本机消息主机清单，但它从不由浏览器安装或管理。</span><span class="sxs-lookup"><span data-stu-id="ff713-120">Browsers read and validate the native messaging host manifest, but it’s never installed or managed by the browser.</span></span> <span data-ttu-id="ff713-121">主机清单文件必须是包含以下字段的有效 json 文件。</span><span class="sxs-lookup"><span data-stu-id="ff713-121">The host manifest file must be a valid json file containing the following fields.</span></span>

    
```json
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




| <span data-ttu-id="ff713-122">名称</span><span class="sxs-lookup"><span data-stu-id="ff713-122">Name</span></span> | <span data-ttu-id="ff713-123">描述</span><span class="sxs-lookup"><span data-stu-id="ff713-123">Description</span></span> |  
|:--- |:--- |  
| `name` | <span data-ttu-id="ff713-124">本机消息主机的名称。</span><span class="sxs-lookup"><span data-stu-id="ff713-124">Name of the native messaging host.</span></span> <span data-ttu-id="ff713-125">客户端将此字符串传递给 `runtime.connectNative` 或 `runtime.sendNativeMessage` 。</span><span class="sxs-lookup"><span data-stu-id="ff713-125">Clients pass this string to `runtime.connectNative` or `runtime.sendNativeMessage`.</span></span>  <span data-ttu-id="ff713-126">此名称必须仅包含小写字母数字字符、下划线和点符。</span><span class="sxs-lookup"><span data-stu-id="ff713-126">This name must only contain lowercase alphanumeric characters, underscores, and dots.</span></span>  <span data-ttu-id="ff713-127">名称不能以点开始或结束，并且一个点后面不得跟另一个点。</span><span class="sxs-lookup"><span data-stu-id="ff713-127">The name must not start or end with a dot, and a dot must not be followed by another dot.</span></span> |  
| `description` | <span data-ttu-id="ff713-128">应用程序的简要说明。</span><span class="sxs-lookup"><span data-stu-id="ff713-128">Brief description of the application.</span></span> |  
| `path` | <span data-ttu-id="ff713-129">本机消息主机二进制文件的路径。</span><span class="sxs-lookup"><span data-stu-id="ff713-129">Path to the native messaging host binary.</span></span> <span data-ttu-id="ff713-130">在 Windows 设备上，你可以使用包含清单文件的目录的相对路径。</span><span class="sxs-lookup"><span data-stu-id="ff713-130">On Windows devices, you may use relative paths to the directory that contains the manifest file.</span></span> <span data-ttu-id="ff713-131">在 macOS 和 Linux 上，路径必须是绝对路径。</span><span class="sxs-lookup"><span data-stu-id="ff713-131">On macOS and Linux, the path must be absolute.</span></span> <span data-ttu-id="ff713-132">将启动主机进程，并将当前目录设置为包含主机二进制文件的目录。</span><span class="sxs-lookup"><span data-stu-id="ff713-132">The host process is started with the current directory set to the directory that contains the host binary.</span></span> <span data-ttu-id="ff713-133">例如，如果此参数设置为，将 `C:\Application\nm_host.exe` 使用当前目录启动二进制文件 `C:\Application\` 。</span><span class="sxs-lookup"><span data-stu-id="ff713-133">For example, if this parameter is set to `C:\Application\nm_host.exe`, the binary is started using the current directory `C:\Application\`.</span></span> |  
| `type` | <span data-ttu-id="ff713-134">用于与本机消息主机通信的接口类型。</span><span class="sxs-lookup"><span data-stu-id="ff713-134">Type of the interface used to communicate with the native messaging host.</span></span>  <span data-ttu-id="ff713-135">目前，此参数仅有一个可能的值： `stdio` 。</span><span class="sxs-lookup"><span data-stu-id="ff713-135">Currently there's only one possible value for this parameter: `stdio`.</span></span>  <span data-ttu-id="ff713-136">此值表示 Microsoft Edge 应使用 `stdin` 并与 `stdout` 主机通信。</span><span class="sxs-lookup"><span data-stu-id="ff713-136">This value indicates that Microsoft Edge should use `stdin` and `stdout` to communicate with the host.</span></span> |  
| `allowed_origins` |  <span data-ttu-id="ff713-137">可访问本机消息主机的扩展列表。</span><span class="sxs-lookup"><span data-stu-id="ff713-137">List of extensions that may have access to the native messaging host.</span></span>  <span data-ttu-id="ff713-138">若要使你的应用能够标识和通信，请 `allowed_origins` `chrome-extension://[Microsoft-Catalog-extensionID]` 在你的本机消息主机清单文件中设置为。</span><span class="sxs-lookup"><span data-stu-id="ff713-138">To enable your application to identify and communicate with an extension, set `allowed_origins` to `chrome-extension://[Microsoft-Catalog-extensionID]` in your native messaging host manifest file.</span></span> |  


<span data-ttu-id="ff713-139">在开发过程中，你可以通过以下方式旁加载扩展以通过主机测试本机消息传递：</span><span class="sxs-lookup"><span data-stu-id="ff713-139">While developing, you can sideload your extension to test native messaging with the host by:</span></span>
1. <span data-ttu-id="ff713-140">导航到 `edge://extensions` ，然后打开 "开发人员模式切换" 按钮。</span><span class="sxs-lookup"><span data-stu-id="ff713-140">Navigating to `edge://extensions`, and then turning on the Developer mode toggle button.</span></span> 
1. <span data-ttu-id="ff713-141">选择 "加载解包"，然后选择扩展包到旁加载。</span><span class="sxs-lookup"><span data-stu-id="ff713-141">Choose Load unpacked, and then select your extension package to sideload.</span></span>  
1. <span data-ttu-id="ff713-142">选择“确定”。</span><span class="sxs-lookup"><span data-stu-id="ff713-142">Choose OK.</span></span>
1. <span data-ttu-id="ff713-143">验证 `edge://extensions` 页面现在是否会列出你的扩展。</span><span class="sxs-lookup"><span data-stu-id="ff713-143">Verify the `edge://extensions` page now lists your extension.</span></span> 
1. <span data-ttu-id="ff713-144">从页面上的 "扩展" 列表中复制 "ID" 中的密钥。</span><span class="sxs-lookup"><span data-stu-id="ff713-144">Copy the key from ID from the extension listing on the page.</span></span>

<span data-ttu-id="ff713-145">准备好将扩展分发给用户后，将扩展发布到 Microsoft Edge 加载项存储。</span><span class="sxs-lookup"><span data-stu-id="ff713-145">When you're ready to distribute your extension to users, publish your extension to the Microsoft Edge add-ons store.</span></span> <span data-ttu-id="ff713-146">已发布扩展的扩展 ID 可能与在旁加载你的扩展时使用的 ID 不同。</span><span class="sxs-lookup"><span data-stu-id="ff713-146">The extension ID of the published extension may be different to the ID used while sideloading your extension.</span></span> <span data-ttu-id="ff713-147">如果 ID 已更改，请 `allowed_origins` 在具有已发布扩展的 ID 的主机清单文件中更新。</span><span class="sxs-lookup"><span data-stu-id="ff713-147">If the ID changed, update `allowed_origins` in the host manifest file with the ID of your published extension.</span></span> 



### <span data-ttu-id="ff713-148">步骤3：将本机消息主机清单文件复制到系统</span><span class="sxs-lookup"><span data-stu-id="ff713-148">Step 3: Copy the native messaging host manifest file to your system</span></span>

<span data-ttu-id="ff713-149">最后一步是将本机消息主机清单文件复制到你的计算机，并确保其配置正确。</span><span class="sxs-lookup"><span data-stu-id="ff713-149">The final step involves copying the native messaging host manifest file to your computer, and ensuring it’s configured correctly.</span></span> <span data-ttu-id="ff713-150">请按照下列步骤操作，确保将本机消息传递主机文件放置在预期位置，因为它因平台而异。</span><span class="sxs-lookup"><span data-stu-id="ff713-150">Follow the steps below to ensure the native messaging host file is placed in the expected location because it varies by platform.</span></span>
    
<span data-ttu-id="ff713-151">**Windows**。</span><span class="sxs-lookup"><span data-stu-id="ff713-151">**Windows**.</span></span> <span data-ttu-id="ff713-152">清单文件可能位于文件系统中的任何位置。</span><span class="sxs-lookup"><span data-stu-id="ff713-152">The manifest file may be located anywhere in the file system.</span></span> <span data-ttu-id="ff713-153">应用程序安装程序必须创建一个注册表项，并将该注册表项的默认值设置为清单文件的完整路径。</span><span class="sxs-lookup"><span data-stu-id="ff713-153">The application installer must create a registry key and set the default value of that key to the full path of the manifest file.</span></span> <span data-ttu-id="ff713-154">以下命令是注册表项的示例。</span><span class="sxs-lookup"><span data-stu-id="ff713-154">The following commands are examples of registry keys.</span></span>
    
`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_application`  
    <span data-ttu-id="ff713-155">或者</span><span class="sxs-lookup"><span data-stu-id="ff713-155">or</span></span>  
`HKEY_CURRENT_USER\SOFTWARE\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_application`<span data-ttu-id="ff713-156">,</span><span class="sxs-lookup"><span data-stu-id="ff713-156">,</span></span>  
    
<span data-ttu-id="ff713-157">在命令提示符处运行以下命令，将注册表项添加到带有清单文件的文件夹。</span><span class="sxs-lookup"><span data-stu-id="ff713-157">Run the following command at a command prompt to add a registry key to the folder with the manifest file.</span></span>
    
```shell
REG ADD "HKCU\Software\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_application" /ve /t REG_SZ /d "C:\path\to\nmh-manifest.json" /f
```  
    
<span data-ttu-id="ff713-158">或者，将以下命令复制到 .reg 文件，然后运行它以添加注册表项。</span><span class="sxs-lookup"><span data-stu-id="ff713-158">Alternatively, copy the following command to a .reg file and run it to add the registry key.</span></span> 
    
```shell
Windows Registry Editor Version 5.00
[HKEY_CURRENT_USER\Software\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_application]
@="C:\\path\\to\\nmh-manifest.json"
``` 

  <span data-ttu-id="ff713-159">Microsoft Edge 首先查询32位注册表，然后是64位注册表来标识本机消息主机。</span><span class="sxs-lookup"><span data-stu-id="ff713-159">Microsoft Edge queries the 32-bit registry first, and then the 64-bit registry to identify native messaging hosts.</span></span> <span data-ttu-id="ff713-160">如果作为批处理脚本的一部分运行上述 .reg 文件，请确保使用管理员命令提示符运行该文件。</span><span class="sxs-lookup"><span data-stu-id="ff713-160">If you run the above .reg file as part of a batch script, ensure you run it using an administrator command prompt.</span></span>


<span data-ttu-id="ff713-161">**macOS**。</span><span class="sxs-lookup"><span data-stu-id="ff713-161">**macOS**.</span></span> <span data-ttu-id="ff713-162">清单文件必须按如下方式存储：</span><span class="sxs-lookup"><span data-stu-id="ff713-162">The manifest file must be stored as follows:</span></span>

1. <span data-ttu-id="ff713-163">系统范围内可供所有用户使用的本机消息传递主机存储在固定位置。</span><span class="sxs-lookup"><span data-stu-id="ff713-163">System-wide native messaging hosts, which are available to all users, are stored in a fixed location.</span></span> <span data-ttu-id="ff713-164">例如，清单文件必须存储在</span><span class="sxs-lookup"><span data-stu-id="ff713-164">For example, the manifest file must be stored in</span></span> `/Library/Microsoft/Edge/NativeMessagingHosts/com.my_company.my_application.json`

1. <span data-ttu-id="ff713-165">特定于用户的本机消息主机（仅适用于当前用户）位于用户配置文件目录中的 NativeMessagingHosts 子目录中。</span><span class="sxs-lookup"><span data-stu-id="ff713-165">User-specific native messaging hosts, which are available to the current user only, are located in the NativeMessagingHosts  subdirectory in the user profile directory.</span></span> <span data-ttu-id="ff713-166">例如，清单文件必须存储在</span><span class="sxs-lookup"><span data-stu-id="ff713-166">For example, the manifest file must be stored in</span></span>  
    `~/Library/Application Support/Microsoft Edge <ChannelName>/NativeMessagingHosts/com.my_company.my_application.json`

    <span data-ttu-id="ff713-167">在哪里 `ChannelName` 可以是 "有地方"、"开发" 或 "Beta"。</span><span class="sxs-lookup"><span data-stu-id="ff713-167">where `ChannelName` may be Canary, Dev, or Beta.</span></span> <span data-ttu-id="ff713-168">使用稳定频道时， `ChannelName` 不需要。</span><span class="sxs-lookup"><span data-stu-id="ff713-168">When using the Stable channel, `ChannelName` isn't required.</span></span>


<span data-ttu-id="ff713-169">**Linux** 清单文件必须按如下方式存储：</span><span class="sxs-lookup"><span data-stu-id="ff713-169">**Linux** The manifest file must be stored as follows:</span></span>

1. <span data-ttu-id="ff713-170">系统范围内的本机消息传递主机：  `~/.config/microsoft-edge/NativeMessagingHosts`</span><span class="sxs-lookup"><span data-stu-id="ff713-170">System-wide native messaging hosts:  `~/.config/microsoft-edge/NativeMessagingHosts`</span></span>

1. <span data-ttu-id="ff713-171">特定于用户的本机消息主机：  `/etc/opt/edge/native-messaging-hosts`</span><span class="sxs-lookup"><span data-stu-id="ff713-171">User-specific native messaging hosts:  `/etc/opt/edge/native-messaging-hosts`</span></span>


> [!NOTE]
> <span data-ttu-id="ff713-172">确保提供对清单文件的读取权限以及对主机可执行文件的执行权限。</span><span class="sxs-lookup"><span data-stu-id="ff713-172">Ensure that you provide read permissions on the manifest file, and execute permissions on the host executable.</span></span>


> [!NOTE]
> <span data-ttu-id="ff713-173">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="ff713-173">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="ff713-174">可在 [此处](https://developer.chrome.com/extensions/nativeMessaging)找到原始页面。</span><span class="sxs-lookup"><span data-stu-id="ff713-174">The original page is found [here](https://developer.chrome.com/extensions/nativeMessaging).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="ff713-176">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="ff713-176">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  


<!-- image links -->  

<!-- links -->  

[EdgeAddons]: https://microsoftedge.microsoft.com/addons/Microsoft-Edge-Extensions-Home "Microsoft Edge 加载项"
[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies
