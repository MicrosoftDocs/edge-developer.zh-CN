---
description: 本机消息传递文档
title: 本机消息传递
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/17/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium， 扩展开发， 浏览器扩展， 加载项， 合作伙伴中心， 开发人员
ms.openlocfilehash: d9c2370d6a4f9f7cd25001c1c58ce266423af19a
ms.sourcegitcommit: 916b4daa26c2c78611f7d837bd6ecf009f0082df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/17/2021
ms.locfileid: "11343064"
---
# <span data-ttu-id="e166f-104">本机消息传递</span><span class="sxs-lookup"><span data-stu-id="e166f-104">Native messaging</span></span>  

<span data-ttu-id="e166f-105">扩展使用消息传递 API 与安装在用户设备上本机 Win32 应用程序进行通信。</span><span class="sxs-lookup"><span data-stu-id="e166f-105">Extensions communicate with a native Win32 application installed on a user's device using message passing APIs.</span></span>  <span data-ttu-id="e166f-106">本机应用程序主机使用标准输入和标准输出发送和接收扩展的邮件。</span><span class="sxs-lookup"><span data-stu-id="e166f-106">The native application host sends and receives messages with extensions using standard input and standard output.</span></span>  <span data-ttu-id="e166f-107">使用本机消息传递的扩展安装在 Microsoft Edge 中，与任何其他扩展类似。</span><span class="sxs-lookup"><span data-stu-id="e166f-107">Extensions using native messaging are installed in Microsoft Edge similar to any other extension.</span></span>  <span data-ttu-id="e166f-108">但是，Microsoft Edge 不会安装或管理本机应用程序。</span><span class="sxs-lookup"><span data-stu-id="e166f-108">However, native applications are not installed or managed by Microsoft Edge.</span></span>  

<span data-ttu-id="e166f-109">若要获取扩展和本机应用程序主机，有两个分发模型。</span><span class="sxs-lookup"><span data-stu-id="e166f-109">To acquire the extension and native application host, you have two distribution models.</span></span>  

*   <span data-ttu-id="e166f-110">将扩展和主机打包在一起。</span><span class="sxs-lookup"><span data-stu-id="e166f-110">Package your extension and the host together.</span></span>  <span data-ttu-id="e166f-111">当用户安装程序包时，将同时安装扩展和主机。</span><span class="sxs-lookup"><span data-stu-id="e166f-111">When a user installs the package, both the extension and the host are installed.</span></span>  
*   <span data-ttu-id="e166f-112">使用 [Microsoft Edge 加载项] [MicrosoftMicrosoftedgeAddonsMicrosoftEdgeExtensionsHome]存储安装扩展，扩展会提示用户安装主机。</span><span class="sxs-lookup"><span data-stu-id="e166f-112">Install your extension using the [Microsoft Edge Add-ons store] [MicrosoftMicrosoftedgeAddonsMicrosoftEdgeExtensionsHome], and your extension prompts users to install the host.</span></span>  

<span data-ttu-id="e166f-113">若要创建扩展以使用本机应用程序主机发送和接收邮件，请参阅以下步骤。</span><span class="sxs-lookup"><span data-stu-id="e166f-113">To create your extension to send and receive messages with native application hosts, refer to the following steps.</span></span>  

## <span data-ttu-id="e166f-114">步骤 1 - 向扩展清单添加权限</span><span class="sxs-lookup"><span data-stu-id="e166f-114">Step 1 - Add permissions to the extension manifest</span></span>  

<span data-ttu-id="e166f-115">将 `nativeMessaging` 权限添加到扩展 **manifest.js** 文件的权限。</span><span class="sxs-lookup"><span data-stu-id="e166f-115">Add the `nativeMessaging` permission to the **manifest.json** file of the extension.</span></span>  <span data-ttu-id="e166f-116">下面的代码段是一个有关manifest.js 的示例。</span><span class="sxs-lookup"><span data-stu-id="e166f-116">The following code snippet is an example of **manifest.json**.</span></span>  

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

## <span data-ttu-id="e166f-117">步骤 2 - 创建本机邮件主机清单文件</span><span class="sxs-lookup"><span data-stu-id="e166f-117">Step 2 - Create your native messaging host manifest file</span></span>  

<span data-ttu-id="e166f-118">本机应用程序必须提供本机邮件主机清单文件。</span><span class="sxs-lookup"><span data-stu-id="e166f-118">Native applications must provide a native messaging host manifest file.</span></span>  <span data-ttu-id="e166f-119">清单文件包含以下信息。</span><span class="sxs-lookup"><span data-stu-id="e166f-119">The manifest file contains the following information.</span></span>  

*   <span data-ttu-id="e166f-120">本机消息传递主机运行时的路径。</span><span class="sxs-lookup"><span data-stu-id="e166f-120">The path to the native messaging host runtime.</span></span>  
*   <span data-ttu-id="e166f-121">与扩展通信的方法。</span><span class="sxs-lookup"><span data-stu-id="e166f-121">The method of communication with the extension.</span></span>  
*   <span data-ttu-id="e166f-122">它所通信的允许的扩展的列表。</span><span class="sxs-lookup"><span data-stu-id="e166f-122">A list of allowed extensions to which it communicates.</span></span>  
    
<span data-ttu-id="e166f-123">浏览器读取并验证本机邮件主机清单。</span><span class="sxs-lookup"><span data-stu-id="e166f-123">The browser reads and validates the native messaging host manifest.</span></span>  <span data-ttu-id="e166f-124">浏览器不会安装或管理本机邮件主机清单文件。</span><span class="sxs-lookup"><span data-stu-id="e166f-124">The browser doesn't install or manage the native messaging host manifest file.</span></span>  

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

<span data-ttu-id="e166f-125">主机清单文件必须是包含以下密钥的有效 JSON 文件。</span><span class="sxs-lookup"><span data-stu-id="e166f-125">The host manifest file must be a valid JSON file that contains the following keys.</span></span>  

:::row:::
   :::column span="1":::
      `name`  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="e166f-126">指定本机消息传递主机的名称。</span><span class="sxs-lookup"><span data-stu-id="e166f-126">Specifies the name of the native messaging host.</span></span>  <span data-ttu-id="e166f-127">客户端将此字符串传递给 `runtime.connectNative` 或 `runtime.sendNativeMessage` 。</span><span class="sxs-lookup"><span data-stu-id="e166f-127">Clients pass this string to `runtime.connectNative` or `runtime.sendNativeMessage`.</span></span>  
      
      *   <span data-ttu-id="e166f-128">此值只能包含小写字母数字字符、下划线和点。</span><span class="sxs-lookup"><span data-stu-id="e166f-128">This value must only contain lowercase alphanumeric characters, underscores, and dots.</span></span>  
      *   <span data-ttu-id="e166f-129">此值不得以点开始或结尾，并且一个点不得后跟另一个点。</span><span class="sxs-lookup"><span data-stu-id="e166f-129">This value must not start or end with a dot, and a dot must not be followed by another dot.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      `description`  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="e166f-130">描述应用程序。</span><span class="sxs-lookup"><span data-stu-id="e166f-130">Describes the application.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      `path`  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="e166f-131">指定本机消息传递主机二进制文件的路径。</span><span class="sxs-lookup"><span data-stu-id="e166f-131">Specifies the path to the native messaging host binary.</span></span>  
      
      *   <span data-ttu-id="e166f-132">在 Windows 设备上，可以使用包含清单文件的目录的相对路径。</span><span class="sxs-lookup"><span data-stu-id="e166f-132">On Windows devices, you may use relative paths to the directory that contains the manifest file.</span></span>  
      *   <span data-ttu-id="e166f-133">在 macOS 和 Linux 上，路径必须是绝对路径。</span><span class="sxs-lookup"><span data-stu-id="e166f-133">On macOS and Linux, the path must be absolute.</span></span>  
      
      <span data-ttu-id="e166f-134">主机进程从当前目录设置为包含主机二进制文件的目录开始。</span><span class="sxs-lookup"><span data-stu-id="e166f-134">The host process starts with the current directory set to the directory that contains the host binary.</span></span>  <span data-ttu-id="e166f-135">例如 \(Windows\) ，如果此参数设置为 ，则使用当前目录 `C:\Application\nm_host.exe` \(`C:\Application\` \) 启动二进制文件。</span><span class="sxs-lookup"><span data-stu-id="e166f-135">For example \(Windows\), if this parameter is set to `C:\Application\nm_host.exe`, the binary is started using the current directory \(`C:\Application\`\).</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      `type`  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="e166f-136">指定用于与本机消息传递主机进行通信的接口的类型。</span><span class="sxs-lookup"><span data-stu-id="e166f-136">Specifies the type of the interface used to communicate with the native messaging host.</span></span>  <span data-ttu-id="e166f-137">此值指示 Microsoft Edge 使用 `stdin` 主机 `stdout` 并与主机通信。</span><span class="sxs-lookup"><span data-stu-id="e166f-137">This value instructs Microsoft Edge to use `stdin` and `stdout` to communicate with the host.</span></span>  
      <span data-ttu-id="e166f-138">唯一可接受的值为 `stdio` 。</span><span class="sxs-lookup"><span data-stu-id="e166f-138">The only acceptable value is `stdio`.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      `allowed_origins` 
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="e166f-139">指定有权访问本机邮件主机的扩展的列表。</span><span class="sxs-lookup"><span data-stu-id="e166f-139">Specifies the list of extensions that have access to the native messaging host.</span></span>  <span data-ttu-id="e166f-140">若要使应用程序能够标识扩展并与扩展通信，请在你的本机邮件主机清单文件中设置以下值。</span><span class="sxs-lookup"><span data-stu-id="e166f-140">To enable your application to identify and communicate with an extension, in your native messaging host manifest file set the following value.</span></span>  
      
      ```json
      "allowed_origins": ["chrome-extension://{microsoft_catalog_extension_id}"]
      ```  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="e166f-141">旁加载扩展以测试主机的本机消息。</span><span class="sxs-lookup"><span data-stu-id="e166f-141">Sideload your extension to test native messaging with the host.</span></span>  
<span data-ttu-id="e166f-142">若要在开发和检索期间旁加载扩展 `microsoft_catalog_extension_id` ，请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="e166f-142">To sideload your extension during development and retrieve `microsoft_catalog_extension_id`, complete the following steps.</span></span>  

1.  <span data-ttu-id="e166f-143">导航 `edge://extensions` 到 ，然后打开开发人员模式切换按钮。</span><span class="sxs-lookup"><span data-stu-id="e166f-143">Navigate to `edge://extensions`, and then turn on the Developer mode toggle button.</span></span>  
1.  <span data-ttu-id="e166f-144">选择 **"加载解压缩"，** 然后选择要旁加载的扩展包。</span><span class="sxs-lookup"><span data-stu-id="e166f-144">Choose **Load unpacked**, and then select your extension package to sideload.</span></span>  
1.  <span data-ttu-id="e166f-145">选择“确定”。</span><span class="sxs-lookup"><span data-stu-id="e166f-145">Choose **OK**.</span></span>  
1.  <span data-ttu-id="e166f-146">导航 `edge://extensions` 到页面并验证扩展是否列出。</span><span class="sxs-lookup"><span data-stu-id="e166f-146">Navigate to `edge://extensions` page and verify your extension is listed.</span></span>  
1.  <span data-ttu-id="e166f-147">从页面上的扩展 `microsoft_catalog_extension_id` (\(ID\) 复制密钥。</span><span class="sxs-lookup"><span data-stu-id="e166f-147">Copy the key from `microsoft_catalog_extension_id` \(ID\) from the extension listing on the page.</span></span>  

<span data-ttu-id="e166f-148">准备好将扩展分发给用户时，将扩展发布到 Microsoft Edge 加载项存储。</span><span class="sxs-lookup"><span data-stu-id="e166f-148">When you're ready to distribute your extension to users, publish your extension to the Microsoft Edge Add-ons store.</span></span>  <span data-ttu-id="e166f-149">已发布扩展的扩展 ID 可能与旁加载扩展时所使用的 ID 不同。</span><span class="sxs-lookup"><span data-stu-id="e166f-149">The extension ID of the published extension may differ from the ID used while sideloading your extension.</span></span>  <span data-ttu-id="e166f-150">如果 ID 发生更改，则使用已发布扩展的 ID 在主机清单 `allowed_origins` 文件中进行更新。</span><span class="sxs-lookup"><span data-stu-id="e166f-150">If the ID changed, update `allowed_origins` in the host manifest file with the ID of your published extension.</span></span>  

## <span data-ttu-id="e166f-151">步骤 3 - 将本机邮件主机清单文件复制到系统</span><span class="sxs-lookup"><span data-stu-id="e166f-151">Step 3 - Copy the native messaging host manifest file to your system</span></span>  

<span data-ttu-id="e166f-152">最后一步是将本机邮件主机清单文件复制到计算机，并确保清单文件配置正确。</span><span class="sxs-lookup"><span data-stu-id="e166f-152">The final step involves copying the native messaging host manifest file to your computer, and ensuring the manifest file is correctly configured.</span></span>  <span data-ttu-id="e166f-153">若要确保清单文件放置在预期位置，请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="e166f-153">To ensure your manifest file is placed in the expected location, complete the following the steps.</span></span>  <span data-ttu-id="e166f-154">位置因平台而异。</span><span class="sxs-lookup"><span data-stu-id="e166f-154">The location varies by platform.</span></span>  

### [<span data-ttu-id="e166f-155">Windows</span><span class="sxs-lookup"><span data-stu-id="e166f-155">Windows</span></span>](#tab/windows/)  

<a id="copy-manifest-file"></a>  

<span data-ttu-id="e166f-156">清单文件可能位于文件系统中的任何位置。</span><span class="sxs-lookup"><span data-stu-id="e166f-156">The manifest file may be located anywhere in the file system.</span></span>  <span data-ttu-id="e166f-157">应用程序安装程序必须创建注册表项，将注册表项的默认值设置为清单文件的完整路径。</span><span class="sxs-lookup"><span data-stu-id="e166f-157">The application installer must create a registry key and set the default value of that key to the full path of the manifest file.</span></span>  <span data-ttu-id="e166f-158">以下命令是注册表项的示例。</span><span class="sxs-lookup"><span data-stu-id="e166f-158">The following commands are examples of registry keys.</span></span>  

```text
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_application
```

```text
HKEY_CURRENT_USER\SOFTWARE\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_application
```

<span data-ttu-id="e166f-159">使用清单项向目录添加注册表项。</span><span class="sxs-lookup"><span data-stu-id="e166f-159">To add a registry key to the directory with the manifest key.</span></span>  

*   <span data-ttu-id="e166f-160">在命令提示符中运行命令。</span><span class="sxs-lookup"><span data-stu-id="e166f-160">Run command in command prompt.</span></span>  
    
    1.  <span data-ttu-id="e166f-161">运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="e166f-161">Run the following command.</span></span>  
        
        ```shell
        REG ADD "HKCU\Software\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_application" /ve /t REG_SZ /d "C:\path\to\nmh-manifest.json" /f
        ```  
    
*   <span data-ttu-id="e166f-162">创建 `.reg` 并运行文件。</span><span class="sxs-lookup"><span data-stu-id="e166f-162">Create a `.reg` file and run it.</span></span>  
    
    1.  <span data-ttu-id="e166f-163">将以下命令复制到 `.reg` 文件中。</span><span class="sxs-lookup"><span data-stu-id="e166f-163">Copy the following command into a `.reg` file.</span></span>  
        
        ```shell
        Windows Registry Editor Version 5.00
        [HKEY_CURRENT_USER\Software\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_application]
        @="C:\\path\\to\\nmh-manifest.json"
        ```  
        
    1.  <span data-ttu-id="e166f-164">运行 `.reg` 该文件。</span><span class="sxs-lookup"><span data-stu-id="e166f-164">Run the `.reg` file.</span></span>  
    
<span data-ttu-id="e166f-165">Microsoft Edge 查询后 `HKEY_CURRENT_USER` 跟的根键 `HKEY_LOCAL_MACHINE` 。</span><span class="sxs-lookup"><span data-stu-id="e166f-165">Microsoft Edge queries the `HKEY_CURRENT_USER` root key followed by `HKEY_LOCAL_MACHINE`.</span></span>  <span data-ttu-id="e166f-166">在这两项中，首先搜索 32 位注册表，然后搜索 64 位注册表以标识本机邮件主机。</span><span class="sxs-lookup"><span data-stu-id="e166f-166">In both of the keys, the 32-bit registry is searched first, and then the 64-bit registry is searched to identify native messaging hosts.</span></span>  <span data-ttu-id="e166f-167">注册表项指定本机邮件主机清单的位置。</span><span class="sxs-lookup"><span data-stu-id="e166f-167">The registry key specifies the location of the native messaging host manifest.</span></span>  <span data-ttu-id="e166f-168">如果 Microsoft Edge 在之前列出的任何位置找到注册表项，则它不会查询此段落中列出的位置。</span><span class="sxs-lookup"><span data-stu-id="e166f-168">If Microsoft Edge finds the registry key at any of the previously listed locations, it doesn't query the locations that are listed in this paragraph.</span></span>  <span data-ttu-id="e166f-169">如果作为批处理脚本的一部分运行上述文件，请确保使用管理员命令提示符 `.reg` 运行该文件。</span><span class="sxs-lookup"><span data-stu-id="e166f-169">If you run the above `.reg` file as part of a batch script, ensure you run it using an administrator command prompt.</span></span>  

### [<span data-ttu-id="e166f-170">macOS</span><span class="sxs-lookup"><span data-stu-id="e166f-170">macOS</span></span>](#tab/macos/)  

<a id="copy-manifest-file"></a>  

<span data-ttu-id="e166f-171">若要存储清单文件，请完成以下操作之一。</span><span class="sxs-lookup"><span data-stu-id="e166f-171">To store the manifest file, complete one of the following actions.</span></span>  

*   <span data-ttu-id="e166f-172">可供所有用户使用的系统范围的本机邮件主机存储在固定位置。</span><span class="sxs-lookup"><span data-stu-id="e166f-172">System-wide native messaging hosts, which are available to all users, are stored in a fixed location.</span></span>  <span data-ttu-id="e166f-173">例如，清单文件必须存储在以下位置。</span><span class="sxs-lookup"><span data-stu-id="e166f-173">For example, the manifest file must be stored in following location.</span></span>  
    
    ```bash
    /Library/Microsoft/Edge/NativeMessagingHosts/com.my_company.my_application.json
    ```  
    
*   <span data-ttu-id="e166f-174">用户特定的本机消息传递主机（仅对当前用户可用）位于用户配置文件目录中的子 `NativeMessagingHosts` 目录中。</span><span class="sxs-lookup"><span data-stu-id="e166f-174">User-specific native messaging hosts, which are available to the current user only, are located in the `NativeMessagingHosts` subdirectory in the user profile directory.</span></span>  <span data-ttu-id="e166f-175">例如，清单文件必须存储在以下位置。</span><span class="sxs-lookup"><span data-stu-id="e166f-175">For example, the manifest file must be stored in following location.</span></span>  
    
    ```bash
    ~/Library/Application Support/Microsoft Edge {Channel_Name}/NativeMessagingHosts/com.my_company.my_application.json
    ```  
    
    <span data-ttu-id="e166f-176">in  `{Channel_Name}` `Microsoft Edge {Channel_Name}` 必须是下列值之一。</span><span class="sxs-lookup"><span data-stu-id="e166f-176">The  `{Channel_Name}` in `Microsoft Edge {Channel_Name}` must be one of the following values.</span></span>  
    
    *   <span data-ttu-id="e166f-177">Canary</span><span class="sxs-lookup"><span data-stu-id="e166f-177">Canary</span></span>  
    *   <span data-ttu-id="e166f-178">Dev</span><span class="sxs-lookup"><span data-stu-id="e166f-178">Dev</span></span>  
    *   <span data-ttu-id="e166f-179">Beta</span><span class="sxs-lookup"><span data-stu-id="e166f-179">Beta</span></span>  

    <span data-ttu-id="e166f-180">使用 Stable 渠道 `{Channel_Name}` 时，不是必需的。</span><span class="sxs-lookup"><span data-stu-id="e166f-180">When using the Stable channel, `{Channel_Name}` isn't required.</span></span>  

### [<span data-ttu-id="e166f-181">Linux</span><span class="sxs-lookup"><span data-stu-id="e166f-181">Linux</span></span>](#tab/linux/)  

<a id="copy-manifest-file"></a>  

<span data-ttu-id="e166f-182">若要存储清单文件，请完成以下操作之一。</span><span class="sxs-lookup"><span data-stu-id="e166f-182">To store the manifest file, complete one of the following actions.</span></span>  

*   <span data-ttu-id="e166f-183">可供所有用户使用的系统范围的本机邮件主机存储在固定位置。</span><span class="sxs-lookup"><span data-stu-id="e166f-183">System-wide native messaging hosts, which are available to all users, are stored in a fixed location.</span></span>  <span data-ttu-id="e166f-184">清单文件必须存储在以下位置。</span><span class="sxs-lookup"><span data-stu-id="e166f-184">The manifest file must be stored in following location.</span></span>  
    
    ```bash
    /etc/opt/edge/native-messaging-hosts
    ```
    
*   <span data-ttu-id="e166f-185">用户特定的本机消息传递主机（仅对当前用户可用）位于用户配置文件目录中的子 `NativeMessagingHosts` 目录中。</span><span class="sxs-lookup"><span data-stu-id="e166f-185">User-specific native messaging hosts, which are available to the current user only, are located in the `NativeMessagingHosts` subdirectory in the user profile directory.</span></span>  <span data-ttu-id="e166f-186">清单文件必须存储在以下位置。</span><span class="sxs-lookup"><span data-stu-id="e166f-186">The manifest file must be stored in following location.</span></span>  
    
    ```bash
    ~/.config/microsoft-edge/NativeMessagingHosts
    ```  
    
* * *  

> [!NOTE]
> <span data-ttu-id="e166f-187">确保对清单文件提供读取权限，并运行主机运行时的权限。</span><span class="sxs-lookup"><span data-stu-id="e166f-187">Ensure that you provide read permissions on the manifest file, and run permissions on the host runtime.</span></span>  

<!-- links -->  


 [MicrosoftMicrosoftedgeAddonsMicrosoftEdgeExtensionsHome]: https://microsoftedge.microsoft.com/addons/Microsoft-Edge-Extensions-Home "Microsoft Edge 加载项"

> [!NOTE]
> <span data-ttu-id="e166f-189">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="e166f-189">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="e166f-190">原始页面位于 [此处](https://developer.chrome.com/extensions/nativeMessaging)。</span><span class="sxs-lookup"><span data-stu-id="e166f-190">The original page is found [here](https://developer.chrome.com/extensions/nativeMessaging).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="e166f-192">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="e166f-192">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies
