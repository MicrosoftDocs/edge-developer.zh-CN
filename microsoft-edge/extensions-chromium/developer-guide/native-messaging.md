---
description: 本机消息文档
title: 本机消息传递
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/06/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium、扩展开发、浏览器扩展、addons、合作伙伴中心、开发人员
ms.openlocfilehash: c5da9acf79225c88ad5829c2b7f57d1d833ca49b
ms.sourcegitcommit: 75c200a029d19fe372c1505c0006dbfbfad90bf5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2020
ms.locfileid: "11100250"
---
# <span data-ttu-id="44e53-104">本机消息传递</span><span class="sxs-lookup"><span data-stu-id="44e53-104">Native messaging</span></span>  

<span data-ttu-id="44e53-105">扩展使用消息传递 Api 与用户设备上安装的本机 Win32 应用程序进行通信。</span><span class="sxs-lookup"><span data-stu-id="44e53-105">Extensions communicate with a native Win32 application installed on a user's device using message passing APIs.</span></span>  <span data-ttu-id="44e53-106">本机应用程序主机使用标准输入和标准输出发送和接收带有扩展的消息。</span><span class="sxs-lookup"><span data-stu-id="44e53-106">The native application host sends and receives messages with extensions using standard input and standard output.</span></span>  <span data-ttu-id="44e53-107">使用本机消息的扩展安装在与任何其他扩展类似的 Microsoft Edge 中。</span><span class="sxs-lookup"><span data-stu-id="44e53-107">Extensions using native messaging are installed in Microsoft Edge similar to any other extension.</span></span>  <span data-ttu-id="44e53-108">但是，本机应用程序不是由 Microsoft Edge 安装或管理的。</span><span class="sxs-lookup"><span data-stu-id="44e53-108">However, native applications are not installed or managed by Microsoft Edge.</span></span>  

<span data-ttu-id="44e53-109">若要获取扩展和本机应用程序主机，您有两种分布模型。</span><span class="sxs-lookup"><span data-stu-id="44e53-109">To acquire the extension and native application host, you have two distribution models.</span></span>  

*   <span data-ttu-id="44e53-110">将您的扩展和主机打包在一起。</span><span class="sxs-lookup"><span data-stu-id="44e53-110">Package your extension and the host together.</span></span>  <span data-ttu-id="44e53-111">当用户安装程序包时，将同时安装扩展和主机。</span><span class="sxs-lookup"><span data-stu-id="44e53-111">When a user installs the package, both the extension and the host are installed.</span></span>
*   <span data-ttu-id="44e53-112">使用 [Microsoft Edge 加载项存储区][EdgeAddons]安装你的扩展，并且你的扩展会提示用户安装主机。</span><span class="sxs-lookup"><span data-stu-id="44e53-112">Install your extension using the [Microsoft Edge Add-ons store][EdgeAddons], and your extension prompts users to install the host.</span></span>  

<span data-ttu-id="44e53-113">若要创建用于通过本机应用程序主机发送和接收消息的扩展，请参阅以下步骤。</span><span class="sxs-lookup"><span data-stu-id="44e53-113">To create your extension to send and receive messages with native application hosts, refer to the following steps.</span></span>  

## <span data-ttu-id="44e53-114">步骤 1-将权限添加到扩展清单</span><span class="sxs-lookup"><span data-stu-id="44e53-114">Step 1 - Add permissions to the extension manifest</span></span>  

<span data-ttu-id="44e53-115">`nativeMessaging`在扩展名的文件中添加对**manifest.js**的权限。</span><span class="sxs-lookup"><span data-stu-id="44e53-115">Add the `nativeMessaging` permission to the **manifest.json** file of the extension.</span></span>  <span data-ttu-id="44e53-116">下面的代码片段是 **manifest.js**的示例。</span><span class="sxs-lookup"><span data-stu-id="44e53-116">The following code snippet is an example of **manifest.json**.</span></span>  

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

## <span data-ttu-id="44e53-117">步骤 2-创建本机消息主机清单文件</span><span class="sxs-lookup"><span data-stu-id="44e53-117">Step 2 - Create your native messaging host manifest file</span></span>  

<span data-ttu-id="44e53-118">本机应用程序必须提供本机消息主机清单文件。</span><span class="sxs-lookup"><span data-stu-id="44e53-118">Native applications must provide a native messaging host manifest file.</span></span>  <span data-ttu-id="44e53-119">清单文件包含本机消息传递主机运行时的路径、与扩展的通信方法，以及与其通信的允许扩展名的列表。</span><span class="sxs-lookup"><span data-stu-id="44e53-119">The manifest file contains the path to the native messaging host runtime, the method of communication with the extension, and a list of allowed extensions to which it communicates.</span></span>  <span data-ttu-id="44e53-120">浏览器读取并验证本机消息主机清单。</span><span class="sxs-lookup"><span data-stu-id="44e53-120">The browser reads and validates the native messaging host manifest.</span></span>  <span data-ttu-id="44e53-121">浏览器不会安装或管理本机消息主机清单文件。</span><span class="sxs-lookup"><span data-stu-id="44e53-121">The browser does not install or manage the native messaging host manifest file.</span></span>  

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

<span data-ttu-id="44e53-122">主机清单文件必须是包含以下键的有效 JSON 文件。</span><span class="sxs-lookup"><span data-stu-id="44e53-122">The host manifest file must be a valid JSON file that contains the following keys.</span></span>  

:::row:::
   :::column span="1":::
      `name`  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="44e53-123">指定本机消息主机的名称。</span><span class="sxs-lookup"><span data-stu-id="44e53-123">Specifies the name of the native messaging host.</span></span>  <span data-ttu-id="44e53-124">客户端将此字符串传递给 `runtime.connectNative` 或 `runtime.sendNativeMessage` 。</span><span class="sxs-lookup"><span data-stu-id="44e53-124">Clients pass this string to `runtime.connectNative` or `runtime.sendNativeMessage`.</span></span>  
      
      *   <span data-ttu-id="44e53-125">此值必须仅包含小写字母数字字符、下划线和点状。</span><span class="sxs-lookup"><span data-stu-id="44e53-125">This value must only contain lowercase alphanumeric characters, underscores, and dots.</span></span>  
      *   <span data-ttu-id="44e53-126">此值不能以点开始或结束，并且一个点后面不得跟另一个点。</span><span class="sxs-lookup"><span data-stu-id="44e53-126">This value must not start or end with a dot, and a dot must not be followed by another dot.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      `description`  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="44e53-127">描述应用程序。</span><span class="sxs-lookup"><span data-stu-id="44e53-127">Describes the application.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      `path`  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="44e53-128">指定本机消息主机二进制文件的路径。</span><span class="sxs-lookup"><span data-stu-id="44e53-128">Specifies the path to the native messaging host binary.</span></span>  
      
      *   <span data-ttu-id="44e53-129">在 Windows 设备上，你可以使用包含清单文件的目录的相对路径。</span><span class="sxs-lookup"><span data-stu-id="44e53-129">On Windows devices, you may use relative paths to the directory that contains the manifest file.</span></span>  
      *   <span data-ttu-id="44e53-130">在 macOS 和 Linux 上，路径必须是绝对路径。</span><span class="sxs-lookup"><span data-stu-id="44e53-130">On macOS and Linux, the path must be absolute.</span></span>  
      
      <span data-ttu-id="44e53-131">主进程从设置为包含主机二进制文件的目录的当前目录开始。</span><span class="sxs-lookup"><span data-stu-id="44e53-131">The host process starts with the current directory set to the directory that contains the host binary.</span></span>  <span data-ttu-id="44e53-132">例如，\ (Windows \ ) ，如果此参数设置为 `C:\Application\nm_host.exe` ，将使用当前目录 \ (\ ) 启动二进制文件 `C:\Application\` 。</span><span class="sxs-lookup"><span data-stu-id="44e53-132">For example \(Windows\), if this parameter is set to `C:\Application\nm_host.exe`, the binary is started using the current directory \(`C:\Application\`\).</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      `type`  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="44e53-133">指定用于与本机消息主机通信的接口的类型。</span><span class="sxs-lookup"><span data-stu-id="44e53-133">Specifies the type of the interface used to communicate with the native messaging host.</span></span>  <span data-ttu-id="44e53-134">此值指示 Microsoft Edge 使用 `stdin` 和与 `stdout` 主机通信。</span><span class="sxs-lookup"><span data-stu-id="44e53-134">This value instructs Microsoft Edge to use `stdin` and `stdout` to communicate with the host.</span></span>  
      <span data-ttu-id="44e53-135">唯一可接受的值为 `stdio` 。</span><span class="sxs-lookup"><span data-stu-id="44e53-135">The only acceptable value is `stdio`.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      `allowed_origins` 
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="44e53-136">指定有权访问本机消息主机的扩展列表。</span><span class="sxs-lookup"><span data-stu-id="44e53-136">Specifies the list of extensions that have access to the native messaging host.</span></span>  <span data-ttu-id="44e53-137">若要使你的应用程序能够识别扩展并与之通信，请在你的本机消息主机清单文件中设置以下值。</span><span class="sxs-lookup"><span data-stu-id="44e53-137">To enable your application to identify and communicate with an extension, in your native messaging host manifest file set the following value.</span></span>  
      
      ```json
      "allowed_origins": ["chrome-extension://{microsoft_catalog_extension_id}"]
      ```  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="44e53-138">旁加载您的扩展，以通过主机测试本机消息传递。</span><span class="sxs-lookup"><span data-stu-id="44e53-138">Sideload your extension to test native messaging with the host.</span></span>  
<span data-ttu-id="44e53-139">若要在开发和检索期间旁加载扩展 `microsoft_catalog_extension_id` ，请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="44e53-139">To sideload your extension during development and retrieve `microsoft_catalog_extension_id`, complete the following steps.</span></span>  

1.  <span data-ttu-id="44e53-140">导航到 `edge://extensions` ，然后打开 "开发人员模式切换" 按钮。</span><span class="sxs-lookup"><span data-stu-id="44e53-140">Navigate to `edge://extensions`, and then turn on the Developer mode toggle button.</span></span>  
1.  <span data-ttu-id="44e53-141">选择 " **加载解包**"，然后选择扩展包到旁加载。</span><span class="sxs-lookup"><span data-stu-id="44e53-141">Choose **Load unpacked**, and then select your extension package to sideload.</span></span>  
1.  <span data-ttu-id="44e53-142">选择“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="44e53-142">Choose **OK**.</span></span>
1.  <span data-ttu-id="44e53-143">导航到 `edge://extensions` 页面并验证您的扩展是否已列出。</span><span class="sxs-lookup"><span data-stu-id="44e53-143">Navigate to `edge://extensions` page and verify your extension is listed.</span></span>  
1.  <span data-ttu-id="44e53-144">将密钥从 `microsoft_catalog_extension_id` 页面上的扩展列表中的 \ (ID \ ) 复制。</span><span class="sxs-lookup"><span data-stu-id="44e53-144">Copy the key from `microsoft_catalog_extension_id` \(ID\) from the extension listing on the page.</span></span>

<span data-ttu-id="44e53-145">准备好将扩展分发给用户后，将扩展发布到 Microsoft Edge 加载项存储。</span><span class="sxs-lookup"><span data-stu-id="44e53-145">When you are ready to distribute your extension to users, publish your extension to the Microsoft Edge add-ons store.</span></span>  <span data-ttu-id="44e53-146">已发布扩展的扩展 ID 可能与在旁加载你的扩展时使用的 ID 不同。</span><span class="sxs-lookup"><span data-stu-id="44e53-146">The extension ID of the published extension may differ from the ID used while sideloading your extension.</span></span>  <span data-ttu-id="44e53-147">如果 ID 已更改，请 `allowed_origins` 在具有已发布扩展的 ID 的主机清单文件中更新。</span><span class="sxs-lookup"><span data-stu-id="44e53-147">If the ID changed, update `allowed_origins` in the host manifest file with the ID of your published extension.</span></span>  

## <span data-ttu-id="44e53-148">步骤 3-将本机消息主机清单文件复制到系统</span><span class="sxs-lookup"><span data-stu-id="44e53-148">Step 3 - Copy the native messaging host manifest file to your system</span></span>  

<span data-ttu-id="44e53-149">最后一步是将本机消息主机清单文件复制到计算机，并确保它配置正确。</span><span class="sxs-lookup"><span data-stu-id="44e53-149">The final step involves copying the native messaging host manifest file to your computer, and ensuring it is configured correctly.</span></span>  <span data-ttu-id="44e53-150">若要确保清单文件放置在预期位置，请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="44e53-150">To ensure your manifest file is placed in the expected location, complete the following the steps.</span></span>  <span data-ttu-id="44e53-151">该位置因平台而异。</span><span class="sxs-lookup"><span data-stu-id="44e53-151">The location varies by platform.</span></span>  

### [<span data-ttu-id="44e53-152">Windows</span><span class="sxs-lookup"><span data-stu-id="44e53-152">Windows</span></span>](#tab/windows/)  

<a id="copy-manifest-file"></a>  

<span data-ttu-id="44e53-153">清单文件可能位于文件系统中的任何位置。</span><span class="sxs-lookup"><span data-stu-id="44e53-153">The manifest file may be located anywhere in the file system.</span></span>  <span data-ttu-id="44e53-154">应用程序安装程序必须创建一个注册表项，并将该注册表项的默认值设置为清单文件的完整路径。</span><span class="sxs-lookup"><span data-stu-id="44e53-154">The application installer must create a registry key and set the default value of that key to the full path of the manifest file.</span></span>  <span data-ttu-id="44e53-155">以下命令是注册表项的示例。</span><span class="sxs-lookup"><span data-stu-id="44e53-155">The following commands are examples of registry keys.</span></span>  

```text
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_application
```

```text
HKEY_CURRENT_USER\SOFTWARE\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_application
```

<span data-ttu-id="44e53-156">将注册表项添加到具有清单键的目录中。</span><span class="sxs-lookup"><span data-stu-id="44e53-156">To add a registry key to the directory with the manifest key.</span></span>  

*   <span data-ttu-id="44e53-157">在命令提示符下运行命令。</span><span class="sxs-lookup"><span data-stu-id="44e53-157">Run command in command prompt.</span></span>    
    
    1.  <span data-ttu-id="44e53-158">运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="44e53-158">Run the following command.</span></span>  
        
        ```shell
        REG ADD "HKCU\Software\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_application" /ve /t REG_SZ /d "C:\path\to\nmh-manifest.json" /f
        ```  
    
*   <span data-ttu-id="44e53-159">创建一个 `.reg` 文件并运行它。</span><span class="sxs-lookup"><span data-stu-id="44e53-159">Create a `.reg` file and run it.</span></span>  
    
    1.  <span data-ttu-id="44e53-160">将以下命令复制到 `.reg` 文件中。</span><span class="sxs-lookup"><span data-stu-id="44e53-160">Copy the following command into a `.reg` file.</span></span>  
        
        ```shell
        Windows Registry Editor Version 5.00
        [HKEY_CURRENT_USER\Software\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_application]
        @="C:\\path\\to\\nmh-manifest.json"
        ```  
        
    1.  <span data-ttu-id="44e53-161">运行该 `.reg` 文件。</span><span class="sxs-lookup"><span data-stu-id="44e53-161">Run the `.reg` file.</span></span>  
    
<span data-ttu-id="44e53-162">Microsoft Edge 首先查询32位注册表，然后是64位注册表来标识本机消息主机。</span><span class="sxs-lookup"><span data-stu-id="44e53-162">Microsoft Edge queries the 32-bit registry first, and then the 64-bit registry to identify native messaging hosts.</span></span>  <span data-ttu-id="44e53-163">如果将上述 `.reg` 文件作为批处理脚本的一部分运行，请确保使用管理员命令提示符运行它。</span><span class="sxs-lookup"><span data-stu-id="44e53-163">If you run the above `.reg` file as part of a batch script, ensure you run it using an administrator command prompt.</span></span>  

### [<span data-ttu-id="44e53-164">macOS</span><span class="sxs-lookup"><span data-stu-id="44e53-164">macOS</span></span>](#tab/macos/)  

<a id="copy-manifest-file"></a>  

<span data-ttu-id="44e53-165">若要存储清单文件，请完成以下操作之一。</span><span class="sxs-lookup"><span data-stu-id="44e53-165">To store the manifest file, complete one of the following actions.</span></span>  

*   <span data-ttu-id="44e53-166">系统范围内可供所有用户使用的本机消息传递主机存储在固定位置。</span><span class="sxs-lookup"><span data-stu-id="44e53-166">System-wide native messaging hosts, which are available to all users, are stored in a fixed location.</span></span>  <span data-ttu-id="44e53-167">例如，清单文件必须存储在以下位置。</span><span class="sxs-lookup"><span data-stu-id="44e53-167">For example, the manifest file must be stored in following location.</span></span> 
    
    ```bash
    /Library/Microsoft/Edge/NativeMessagingHosts/com.my_company.my_application.json
    ```  
    
*   <span data-ttu-id="44e53-168">特定于用户的本机消息主机（仅适用于当前用户）位于 `NativeMessagingHosts` 用户配置文件目录中的子目录中。</span><span class="sxs-lookup"><span data-stu-id="44e53-168">User-specific native messaging hosts, which are available to the current user only, are located in the `NativeMessagingHosts` subdirectory in the user profile directory.</span></span>  <span data-ttu-id="44e53-169">例如，清单文件必须存储在以下位置。</span><span class="sxs-lookup"><span data-stu-id="44e53-169">For example, the manifest file must be stored in following location.</span></span>  
    
    ```bash
    ~/Library/Application Support/Microsoft Edge {Channel_Name}/NativeMessagingHosts/com.my_company.my_application.json
    ```  
    
    <span data-ttu-id="44e53-170">`{Channel_Name}`In `Microsoft Edge {Channel_Name}` 必须是下列值之一。</span><span class="sxs-lookup"><span data-stu-id="44e53-170">The  `{Channel_Name}` in `Microsoft Edge {Channel_Name}` must be one of the following values.</span></span>  
    
    *   <span data-ttu-id="44e53-171">Canary</span><span class="sxs-lookup"><span data-stu-id="44e53-171">Canary</span></span>  
    *   <span data-ttu-id="44e53-172">Dev</span><span class="sxs-lookup"><span data-stu-id="44e53-172">Dev</span></span>  
    *   <span data-ttu-id="44e53-173">Beta</span><span class="sxs-lookup"><span data-stu-id="44e53-173">Beta</span></span>  

    <span data-ttu-id="44e53-174">使用稳定通道时， `{Channel_Name}` 不是必需的。</span><span class="sxs-lookup"><span data-stu-id="44e53-174">When using the Stable channel, `{Channel_Name}` is not required.</span></span>  

### [<span data-ttu-id="44e53-175">Linux</span><span class="sxs-lookup"><span data-stu-id="44e53-175">Linux</span></span>](#tab/linux/)  

<a id="copy-manifest-file"></a>  

<span data-ttu-id="44e53-176">若要存储清单文件，请完成以下操作之一。</span><span class="sxs-lookup"><span data-stu-id="44e53-176">To store the manifest file, complete one of the following actions.</span></span>  

*   <span data-ttu-id="44e53-177">系统范围内可供所有用户使用的本机消息传递主机存储在固定位置。</span><span class="sxs-lookup"><span data-stu-id="44e53-177">System-wide native messaging hosts, which are available to all users, are stored in a fixed location.</span></span>  <span data-ttu-id="44e53-178">清单文件必须存储在以下位置。</span><span class="sxs-lookup"><span data-stu-id="44e53-178">The manifest file must be stored in following location.</span></span>  
    
    ```bash
    /etc/opt/edge/native-messaging-hosts
    ```
    
*   <span data-ttu-id="44e53-179">特定于用户的本机消息主机（仅适用于当前用户）位于 `NativeMessagingHosts` 用户配置文件目录中的子目录中。</span><span class="sxs-lookup"><span data-stu-id="44e53-179">User-specific native messaging hosts, which are available to the current user only, are located in the `NativeMessagingHosts` subdirectory in the user profile directory.</span></span>  <span data-ttu-id="44e53-180">清单文件必须存储在以下位置。</span><span class="sxs-lookup"><span data-stu-id="44e53-180">The manifest file must be stored in following location.</span></span>  
    
    ```bash
    ~/.config/microsoft-edge/NativeMessagingHosts
    ```  
    
* * *  

> [!NOTE]
> <span data-ttu-id="44e53-181">确保在清单文件上提供读取权限，并确保在主机运行时上运行权限。</span><span class="sxs-lookup"><span data-stu-id="44e53-181">Ensure that you provide read permissions on the manifest file, and run permissions on the host runtime.</span></span>  

<!-- links -->  

> [!NOTE]
> <span data-ttu-id="44e53-182">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="44e53-182">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="44e53-183">可在 [此处](https://developer.chrome.com/extensions/nativeMessaging)找到原始页面。</span><span class="sxs-lookup"><span data-stu-id="44e53-183">The original page is found [here](https://developer.chrome.com/extensions/nativeMessaging).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="44e53-185">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="44e53-185">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[EdgeAddons]: https://microsoftedge.microsoft.com/addons/Microsoft-Edge-Extensions-Home "Microsoft Edge 加载项"
[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies
