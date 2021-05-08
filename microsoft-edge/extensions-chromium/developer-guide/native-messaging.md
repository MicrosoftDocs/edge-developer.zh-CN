---
description: 本机消息传递文档
title: 本机消息传递
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/31/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium， 扩展开发， 浏览器扩展， 加载项， 合作伙伴中心， 开发人员
ms.openlocfilehash: e6233289794bc1c3ef235af46402c23173c09857
ms.sourcegitcommit: e6a4f73be57439149e3cc56491d7364831d0079e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/05/2021
ms.locfileid: "11475209"
---
# <a name="native-messaging"></a><span data-ttu-id="b27cd-104">本机消息传递</span><span class="sxs-lookup"><span data-stu-id="b27cd-104">Native messaging</span></span>  

<span data-ttu-id="b27cd-105">扩展使用消息传递 API 与安装在用户设备上本机 Win32 应用进行通信。</span><span class="sxs-lookup"><span data-stu-id="b27cd-105">Extensions communicate with a native Win32 app installed on a user's device using message passing APIs.</span></span>  <span data-ttu-id="b27cd-106">本机应用主机使用标准输入和标准输出发送和接收扩展名的邮件。</span><span class="sxs-lookup"><span data-stu-id="b27cd-106">The native app host sends and receives messages with extensions using standard input and standard output.</span></span>  <span data-ttu-id="b27cd-107">使用本机消息传递的扩展安装在Microsoft Edge任何其他扩展类似。</span><span class="sxs-lookup"><span data-stu-id="b27cd-107">Extensions using native messaging are installed in Microsoft Edge similar to any other extension.</span></span>  <span data-ttu-id="b27cd-108">但是，本机应用不是由用户安装或Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="b27cd-108">However, native apps are not installed or managed by Microsoft Edge.</span></span>  

<span data-ttu-id="b27cd-109">若要获取扩展和本机应用主机，你有两个分发模型。</span><span class="sxs-lookup"><span data-stu-id="b27cd-109">To acquire the extension and native app host, you have two distribution models.</span></span>  

*   <span data-ttu-id="b27cd-110">将扩展和主机打包在一起。</span><span class="sxs-lookup"><span data-stu-id="b27cd-110">Package your extension and the host together.</span></span>  <span data-ttu-id="b27cd-111">当用户安装程序包时，将同时安装扩展和主机。</span><span class="sxs-lookup"><span data-stu-id="b27cd-111">When a user installs the package, both the extension and the host are installed.</span></span>  
*   <span data-ttu-id="b27cd-112">使用加载项Microsoft Edge安装扩展[][MicrosoftMicrosoftedgeAddonsMicrosoftEdgeExtensionsHome]，扩展会提示用户安装主机。</span><span class="sxs-lookup"><span data-stu-id="b27cd-112">Install your extension using the [Microsoft Edge Add-ons store][MicrosoftMicrosoftedgeAddonsMicrosoftEdgeExtensionsHome], and your extension prompts users to install the host.</span></span>  

<span data-ttu-id="b27cd-113">若要创建扩展以通过本机应用主机发送和接收消息，请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="b27cd-113">To create your extension to send and receive messages with native app hosts, complete the following steps.</span></span>  

## <a name="step-1---add-permissions-to-the-extension-manifest"></a><span data-ttu-id="b27cd-114">步骤 1 - 向扩展清单添加权限</span><span class="sxs-lookup"><span data-stu-id="b27cd-114">Step 1 - Add permissions to the extension manifest</span></span>  

<span data-ttu-id="b27cd-115">将 `nativeMessaging` 权限添加到扩展 **manifest.js** 上的文件。</span><span class="sxs-lookup"><span data-stu-id="b27cd-115">Add the `nativeMessaging` permission to the **manifest.json** file of the extension.</span></span>  <span data-ttu-id="b27cd-116">下面的代码段是 上manifest.js\*\* 的示例\*\*。</span><span class="sxs-lookup"><span data-stu-id="b27cd-116">The following code snippet is an example of **manifest.json**.</span></span>  

```json
{
    "name": "Native Messaging Example",
    "version": "1.0",
    "manifest_version": 2, 
    "description": "Send a message to a native app.",
    "app": { 
        "launch": { 
            "local_path": "main.html" 
        } 
    }, 
    "icons": { 
        "128": "icon-128.png"
    }, 
    "permissions": ["nativeMessaging"] 
}
```  

## <a name="step-2---create-your-native-messaging-host-manifest-file"></a><span data-ttu-id="b27cd-117">步骤 2 - 创建本机消息传递主机清单文件</span><span class="sxs-lookup"><span data-stu-id="b27cd-117">Step 2 - Create your native messaging host manifest file</span></span>  

<span data-ttu-id="b27cd-118">本机应用必须提供本机消息传递主机清单文件。</span><span class="sxs-lookup"><span data-stu-id="b27cd-118">Native apps must provide a native messaging host manifest file.</span></span>  <span data-ttu-id="b27cd-119">清单文件包含以下信息。</span><span class="sxs-lookup"><span data-stu-id="b27cd-119">The manifest file contains the following information.</span></span>  

*   <span data-ttu-id="b27cd-120">本机消息传递主机运行时的路径。</span><span class="sxs-lookup"><span data-stu-id="b27cd-120">The path to the native messaging host runtime.</span></span>  
*   <span data-ttu-id="b27cd-121">与扩展通信的方法。</span><span class="sxs-lookup"><span data-stu-id="b27cd-121">The method of communication with the extension.</span></span>  
*   <span data-ttu-id="b27cd-122">它所通信的允许扩展的列表。</span><span class="sxs-lookup"><span data-stu-id="b27cd-122">A list of allowed extensions to which it communicates.</span></span>  
    
<span data-ttu-id="b27cd-123">浏览器读取并验证本机消息传递主机清单。</span><span class="sxs-lookup"><span data-stu-id="b27cd-123">The browser reads and validates the native messaging host manifest.</span></span>  <span data-ttu-id="b27cd-124">浏览器不会安装或管理本机消息传递主机清单文件。</span><span class="sxs-lookup"><span data-stu-id="b27cd-124">The browser doesn't install or manage the native messaging host manifest file.</span></span>  

```json
{
    "name": "com.my_company.my_app",
    "description": "My App",
    "path": "C:\\Program Files\\My App\\chrome_native_messaging_host.exe",
    "type": "stdio",
    "allowed_origins": [
        "chrome-extension://knldjmfmopnpolahpmmgbagdohdnhkik/"
    ]
}
```  

<span data-ttu-id="b27cd-125">主机清单文件必须是包含以下密钥的有效 JSON 文件。</span><span class="sxs-lookup"><span data-stu-id="b27cd-125">The host manifest file must be a valid JSON file that contains the following keys.</span></span>  

:::row:::
   :::column span="1":::
      **<span data-ttu-id="b27cd-126">密钥</span><span class="sxs-lookup"><span data-stu-id="b27cd-126">Key</span></span>**  
   :::column-end:::
   :::column span="3":::
      **<span data-ttu-id="b27cd-127">详细信息</span><span class="sxs-lookup"><span data-stu-id="b27cd-127">Details</span></span>**  
:::row-end:::  
:::row:::
   :::column span="1":::
      ---  
      
      `name`  
   :::column-end:::
   :::column span="3":::
      ---  
      
      <span data-ttu-id="b27cd-128">指定本机消息传递主机的名称。</span><span class="sxs-lookup"><span data-stu-id="b27cd-128">Specifies the name of the native messaging host.</span></span>  <span data-ttu-id="b27cd-129">客户端将字符串传递到 `runtime.connectNative` 或 `runtime.sendNativeMessage` 。</span><span class="sxs-lookup"><span data-stu-id="b27cd-129">Clients pass the string to `runtime.connectNative` or `runtime.sendNativeMessage`.</span></span>  
      
      *   <span data-ttu-id="b27cd-130">该值只能包含小写字母数字字符、下划线和点。</span><span class="sxs-lookup"><span data-stu-id="b27cd-130">The value must only contain lowercase alphanumeric characters, underscores, and dots.</span></span>  
      *   <span data-ttu-id="b27cd-131">该值不得以点开始或结尾，而一个点不得后跟另一个点。</span><span class="sxs-lookup"><span data-stu-id="b27cd-131">The value must not start or end with a dot, and a dot must not be followed by another dot.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      ---  
      
      `description`  
   :::column-end:::
   :::column span="3":::
      ---  
      
      <span data-ttu-id="b27cd-132">描述应用。</span><span class="sxs-lookup"><span data-stu-id="b27cd-132">Describes the app.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      ---  
      
      `path`  
   :::column-end:::
   :::column span="3":::
      ---  
      
      <span data-ttu-id="b27cd-133">指定本机消息传递主机二进制文件的路径。</span><span class="sxs-lookup"><span data-stu-id="b27cd-133">Specifies the path to the native messaging host binary.</span></span>  
      
      *   <span data-ttu-id="b27cd-134">在Windows设备上，可以使用包含清单文件的目录的相对路径。</span><span class="sxs-lookup"><span data-stu-id="b27cd-134">On Windows devices, you may use relative paths to the directory that contains the manifest file.</span></span>  
      *   <span data-ttu-id="b27cd-135">在 macOS 和 Linux 上，路径必须为绝对路径。</span><span class="sxs-lookup"><span data-stu-id="b27cd-135">On macOS and Linux, the path must be absolute.</span></span>  
          
      <span data-ttu-id="b27cd-136">主机进程从将当前目录设置为包含主机二进制文件的目录开始。</span><span class="sxs-lookup"><span data-stu-id="b27cd-136">The host process starts with the current directory set to the directory that contains the host binary.</span></span>  <span data-ttu-id="b27cd-137">例如 \ (Windows\) ，如果参数设置为 ，则使用当前目录 `C:\App\nm_host.exe` \ (\) 启动二 `C:\App\` 进制文件。</span><span class="sxs-lookup"><span data-stu-id="b27cd-137">For example \(Windows\), if the parameter is set to `C:\App\nm_host.exe`, the binary is started using the current directory \(`C:\App\`\).</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      ---  
      
      `type`  
   :::column-end:::
   :::column span="3":::
      ---  
      
      <span data-ttu-id="b27cd-138">指定用于与本机消息传递主机通信的接口的类型。</span><span class="sxs-lookup"><span data-stu-id="b27cd-138">Specifies the type of the interface used to communicate with the native messaging host.</span></span>  <span data-ttu-id="b27cd-139">该值指示Microsoft Edge `stdin` 与主机 `stdout` 通信。</span><span class="sxs-lookup"><span data-stu-id="b27cd-139">The value instructs Microsoft Edge to use `stdin` and `stdout` to communicate with the host.</span></span>  
      <span data-ttu-id="b27cd-140">唯一可接受的值为 `stdio` 。</span><span class="sxs-lookup"><span data-stu-id="b27cd-140">The only acceptable value is `stdio`.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      ---  
      
      `allowed_origins` 
   :::column-end:::
   :::column span="3":::
      ---  
      
      <span data-ttu-id="b27cd-141">指定有权访问本机消息传递主机的扩展的列表。</span><span class="sxs-lookup"><span data-stu-id="b27cd-141">Specifies the list of extensions that have access to the native messaging host.</span></span>  <span data-ttu-id="b27cd-142">若要打开应用以标识扩展并与扩展通信，请在你的本机消息传递主机清单文件中设置以下值。</span><span class="sxs-lookup"><span data-stu-id="b27cd-142">To turn on your app to identify and communicate with an extension, in your native messaging host manifest file set the following value.</span></span>  
      
      ```json
      "allowed_origins": ["chrome-extension://{microsoft_catalog_extension_id}"]
      ```  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="b27cd-143">旁加载扩展以测试主机的本机消息传递。</span><span class="sxs-lookup"><span data-stu-id="b27cd-143">Sideload your extension to test native messaging with the host.</span></span>  
<span data-ttu-id="b27cd-144">若要在开发和检索期间旁加载扩展 `microsoft_catalog_extension_id` ，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="b27cd-144">To sideload your extension during development and retrieve `microsoft_catalog_extension_id`, complete the following actions.</span></span>  

1.  <span data-ttu-id="b27cd-145">导航到 `edge://extensions` ，然后打开"开发人员模式"切换按钮。</span><span class="sxs-lookup"><span data-stu-id="b27cd-145">Navigate to `edge://extensions`, and then turn on the Developer mode toggle button.</span></span>  
1.  <span data-ttu-id="b27cd-146">选择 **"加载解压缩**"，然后选择要旁加载的扩展包。</span><span class="sxs-lookup"><span data-stu-id="b27cd-146">Choose **Load unpacked**, and then choose your extension package to sideload.</span></span>  
1.  <span data-ttu-id="b27cd-147">选择“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b27cd-147">Choose **OK**.</span></span>  
1.  <span data-ttu-id="b27cd-148">导航到 `edge://extensions` 页面并验证扩展是否列出。</span><span class="sxs-lookup"><span data-stu-id="b27cd-148">Navigate to `edge://extensions` page and verify your extension is listed.</span></span>  
1.  <span data-ttu-id="b27cd-149">从页面上的扩展 `microsoft_catalog_extension_id` (\ (ID\) 复制该密钥。</span><span class="sxs-lookup"><span data-stu-id="b27cd-149">Copy the key from `microsoft_catalog_extension_id` \(ID\) from the extension listing on the page.</span></span>  
    
<span data-ttu-id="b27cd-150">准备好将扩展分发给用户时，将扩展发布到Microsoft Edge加载项商店。</span><span class="sxs-lookup"><span data-stu-id="b27cd-150">When you're ready to distribute your extension to users, publish your extension to the Microsoft Edge Add-ons store.</span></span>  <span data-ttu-id="b27cd-151">已发布扩展的扩展 ID 可能与旁加载扩展时所使用的 ID 不同。</span><span class="sxs-lookup"><span data-stu-id="b27cd-151">The extension ID of the published extension may differ from the ID used while sideloading your extension.</span></span>  <span data-ttu-id="b27cd-152">如果 ID 发生更改，则使用已发布扩展的 `allowed_origins` ID 在主机清单文件中更新。</span><span class="sxs-lookup"><span data-stu-id="b27cd-152">If the ID changed, update `allowed_origins` in the host manifest file with the ID of your published extension.</span></span>  

## <a name="step-3---copy-the-native-messaging-host-manifest-file-to-your-system"></a><span data-ttu-id="b27cd-153">步骤 3 - 将本机消息传递主机清单文件复制到系统中</span><span class="sxs-lookup"><span data-stu-id="b27cd-153">Step 3 - Copy the native messaging host manifest file to your system</span></span>  

<span data-ttu-id="b27cd-154">最后一步是将本机消息传递主机清单文件复制到计算机，并确保正确配置清单文件。</span><span class="sxs-lookup"><span data-stu-id="b27cd-154">The final step involves copying the native messaging host manifest file to your computer, and ensuring the manifest file is correctly configured.</span></span>  <span data-ttu-id="b27cd-155">若要确保清单文件放置在预期位置，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="b27cd-155">To ensure your manifest file is placed in the expected location, complete the following the actions.</span></span>  <span data-ttu-id="b27cd-156">位置因平台而异。</span><span class="sxs-lookup"><span data-stu-id="b27cd-156">The location varies by platform.</span></span>

> [!NOTE]
> <span data-ttu-id="b27cd-157">请确保对清单文件提供读取权限，并且对主机运行时运行权限。</span><span class="sxs-lookup"><span data-stu-id="b27cd-157">Ensure that you provide read permissions on the manifest file, and run permissions on the host runtime.</span></span>  

### [<a name="windows"></a><span data-ttu-id="b27cd-158">Windows</span><span class="sxs-lookup"><span data-stu-id="b27cd-158">Windows</span></span>](#tab/windows/)  

<a id="copy-manifest-file"></a>  

<span data-ttu-id="b27cd-159">清单文件可能位于文件系统中的任何位置。</span><span class="sxs-lookup"><span data-stu-id="b27cd-159">The manifest file may be located anywhere in the file system.</span></span>  <span data-ttu-id="b27cd-160">应用安装程序必须创建注册表项，并且将注册表项的默认值设置为清单文件的完整路径。</span><span class="sxs-lookup"><span data-stu-id="b27cd-160">The app installer must create a registry key and set the default value of the key to the full path of the manifest file.</span></span>  <span data-ttu-id="b27cd-161">以下位置是注册表项的示例。</span><span class="sxs-lookup"><span data-stu-id="b27cd-161">The following locations are examples of registry keys.</span></span>  

```output
HKEY_CURRENT_USER\SOFTWARE\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_app

HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_app
```  

<span data-ttu-id="b27cd-162">若要使用清单项将注册表项添加到目录，请完成以下操作之一。</span><span class="sxs-lookup"><span data-stu-id="b27cd-162">To add a registry key to the directory with the manifest key, complete one of the following actions.</span></span>  

*   <span data-ttu-id="b27cd-163">在命令提示符中运行命令。</span><span class="sxs-lookup"><span data-stu-id="b27cd-163">Run command in command prompt.</span></span>  
    
    1.  <span data-ttu-id="b27cd-164">运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="b27cd-164">Run the following command.</span></span>  
        
        ```shell
        REG ADD "HKCU\Software\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_app" /ve /t REG_SZ /d "C:\path\to\nmh-manifest.json" /f
        ```  
        
*   <span data-ttu-id="b27cd-165">创建 `.reg` 并运行文件。</span><span class="sxs-lookup"><span data-stu-id="b27cd-165">Create a `.reg` file and run it.</span></span>  
    
    1.  <span data-ttu-id="b27cd-166">将以下命令复制到 `.reg` 文件中。</span><span class="sxs-lookup"><span data-stu-id="b27cd-166">Copy the following command into a `.reg` file.</span></span>  
        
        ```shell
        Windows Registry Editor Version 5.00
        [HKEY_CURRENT_USER\Software\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_app]
        @="C:\\path\\to\\nmh-manifest.json"
        ```  
        
    1.  <span data-ttu-id="b27cd-167">运行 `.reg` 文件。</span><span class="sxs-lookup"><span data-stu-id="b27cd-167">Run the `.reg` file.</span></span>  
        
<span data-ttu-id="b27cd-168">Microsoft Edge查询后跟 `HKEY_CURRENT_USER` 的根键 `HKEY_LOCAL_MACHINE` 。</span><span class="sxs-lookup"><span data-stu-id="b27cd-168">Microsoft Edge queries the `HKEY_CURRENT_USER` root key followed by `HKEY_LOCAL_MACHINE`.</span></span>  <span data-ttu-id="b27cd-169">在这两个项中，首先搜索 32 位注册表，然后搜索 64 位注册表以标识本机消息传递主机。</span><span class="sxs-lookup"><span data-stu-id="b27cd-169">In both of the keys, the 32-bit registry is searched first, and then the 64-bit registry is searched to identify native messaging hosts.</span></span>  <span data-ttu-id="b27cd-170">注册表项指定本机消息传递主机清单的位置。</span><span class="sxs-lookup"><span data-stu-id="b27cd-170">The registry key specifies the location of the native messaging host manifest.</span></span>  <span data-ttu-id="b27cd-171">如果注册表项的Microsoft Edge没有主机清单的位置，Chromium Chrome 注册表位置将用作回退选项。</span><span class="sxs-lookup"><span data-stu-id="b27cd-171">If the registry entries for Microsoft Edge don't have the location of the host manifest, the Chromium and Chrome registry locations are used as fallback options.</span></span>  <span data-ttu-id="b27cd-172">如果Microsoft Edge在先前列出的任何位置找到注册表项，则它不会查询以下代码片段中列出的位置。</span><span class="sxs-lookup"><span data-stu-id="b27cd-172">If Microsoft Edge finds the registry key at any of the previously listed locations, it doesn't query the locations that are listed in the following code snippet.</span></span>  <span data-ttu-id="b27cd-173">如果作为批处理脚本的一部分运行所创建的文件， `.reg` 请确保使用管理员命令提示符运行它。</span><span class="sxs-lookup"><span data-stu-id="b27cd-173">If you run your created `.reg` file as part of a batch script, ensure you run it using an administrator command prompt.</span></span>

<span data-ttu-id="b27cd-174">以下列表是注册表位置的搜索顺序。</span><span class="sxs-lookup"><span data-stu-id="b27cd-174">The following list is the search order for the registry locations.</span></span>  

```output
HKEY_CURRENT_USER\SOFTWARE\WOW6432Node\Microsoft\Edge\NativeMessagingHosts\
HKEY_CURRENT_USER\SOFTWARE\WOW6432Node\Chromium\NativeMessagingHosts\
HKEY_CURRENT_USER\SOFTWARE\WOW6432Node\Google\Chrome\NativeMessagingHosts\
HKEY_CURRENT_USER\SOFTWARE\Microsoft\Edge\NativeMessagingHosts\
HKEY_CURRENT_USER\SOFTWARE\Chromium\NativeMessagingHosts\
HKEY_CURRENT_USER\SOFTWARE\Google\Chrome\NativeMessagingHosts\

HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Edge\NativeMessagingHosts\
HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Chromium\NativeMessagingHosts\
HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Google\Chrome\NativeMessagingHosts\
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Edge\NativeMessagingHosts\
HKEY_LOCAL_MACHINE\SOFTWARE\Chromium\NativeMessagingHosts\
HKEY_LOCAL_MACHINE\SOFTWARE\Google\Chrome\NativeMessagingHosts\
```  
 
> [!NOTE] 
> <span data-ttu-id="b27cd-175">如果您在 Microsoft Edge 加载项和 Chrome Webstore 上具有扩展，则必须添加与主机清单文件的 中的这两个存储对应的扩展名，因为只会读取与找到的第一个注册表位置对应的主机清单。 `allowed_origins`</span><span class="sxs-lookup"><span data-stu-id="b27cd-175">If you have extensions on the Microsoft Edge Add-ons and the Chrome Webstore, you must add the extension IDs corresponding to both the stores in the `allowed_origins` of the host manifest file because only the host manifest corresponding to the first registry location found is read.</span></span>  

### [<a name="macos"></a><span data-ttu-id="b27cd-176">macOS</span><span class="sxs-lookup"><span data-stu-id="b27cd-176">macOS</span></span>](#tab/macos/)  

<a id="copy-manifest-file"></a>  

<span data-ttu-id="b27cd-177">若要存储清单文件，请完成以下操作之一。</span><span class="sxs-lookup"><span data-stu-id="b27cd-177">To store the manifest file, complete one of the following actions.</span></span>  

*   <span data-ttu-id="b27cd-178">系统范围的本机消息传递主机（可供所有用户使用）存储在固定位置。</span><span class="sxs-lookup"><span data-stu-id="b27cd-178">System-wide native messaging hosts, which are available to all users, are stored in a fixed location.</span></span>  <span data-ttu-id="b27cd-179">例如，清单文件必须存储在以下位置。</span><span class="sxs-lookup"><span data-stu-id="b27cd-179">For example, the manifest file must be stored in following location.</span></span>  
    
    ```bash
    /Library/Microsoft/Edge/NativeMessagingHosts/com.my_company.my_app.json
    ```  
    
*   <span data-ttu-id="b27cd-180">用户特定的本机消息传递主机（仅对当前用户可用）位于用户配置文件目录中的子 `NativeMessagingHosts` 目录中。</span><span class="sxs-lookup"><span data-stu-id="b27cd-180">User-specific native messaging hosts, which are available to the current user only, are located in the `NativeMessagingHosts` subdirectory in the user profile directory.</span></span>  <span data-ttu-id="b27cd-181">例如，清单文件必须存储在以下位置。</span><span class="sxs-lookup"><span data-stu-id="b27cd-181">For example, the manifest file must be stored in following location.</span></span>  
    
    ```bash
    ~/Library/Application Support/Microsoft Edge {Channel_Name}/NativeMessagingHosts/com.my_company.my_app.json
    ```  
    
    <span data-ttu-id="b27cd-182">`{Channel_Name}`In `Microsoft Edge {Channel_Name}` 必须是下列值之一。</span><span class="sxs-lookup"><span data-stu-id="b27cd-182">The  `{Channel_Name}` in `Microsoft Edge {Channel_Name}` must be one of the following values.</span></span>  
    
    *   `Canary`  
    *   `Dev`  
    *   `Beta`  
        
    <span data-ttu-id="b27cd-183">使用 Stable 渠道 ` {Channel_Name}` 时，不是必需的。</span><span class="sxs-lookup"><span data-stu-id="b27cd-183">When using the Stable channel, ` {Channel_Name}` isn't required.</span></span>  
    
### [<a name="linux"></a><span data-ttu-id="b27cd-184">Linux</span><span class="sxs-lookup"><span data-stu-id="b27cd-184">Linux</span></span>](#tab/linux/)  

<a id="copy-manifest-file"></a>  

<span data-ttu-id="b27cd-185">若要存储清单文件，请完成以下操作之一。</span><span class="sxs-lookup"><span data-stu-id="b27cd-185">To store the manifest file, complete one of the following actions.</span></span>  

*   <span data-ttu-id="b27cd-186">系统范围的本机消息传递主机（可供所有用户使用）存储在固定位置。</span><span class="sxs-lookup"><span data-stu-id="b27cd-186">System-wide native messaging hosts, which are available to all users, are stored in a fixed location.</span></span>  <span data-ttu-id="b27cd-187">清单文件必须存储在以下位置。</span><span class="sxs-lookup"><span data-stu-id="b27cd-187">The manifest file must be stored in following location.</span></span>  
    
    ```bash
    /etc/opt/edge/native-messaging-hosts
    ```
    
*   <span data-ttu-id="b27cd-188">用户特定的本机消息传递主机（仅对当前用户可用）位于用户配置文件目录中的子 `NativeMessagingHosts` 目录中。</span><span class="sxs-lookup"><span data-stu-id="b27cd-188">User-specific native messaging hosts, which are available to the current user only, are located in the `NativeMessagingHosts` subdirectory in the user profile directory.</span></span>  <span data-ttu-id="b27cd-189">清单文件必须存储在以下位置。</span><span class="sxs-lookup"><span data-stu-id="b27cd-189">The manifest file must be stored in following location.</span></span>  
    
    ```bash
    ~/.config/microsoft-edge/NativeMessagingHosts
    ```  
    
* * *  

<!-- links -->  

[MicrosoftMicrosoftedgeAddonsMicrosoftEdgeExtensionsHome]: https://microsoftedge.microsoft.com/addons/Microsoft-Edge-Extensions-Home "Microsoft Edge 加载项"

> [!NOTE]
> <span data-ttu-id="b27cd-191">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="b27cd-191">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="b27cd-192">原始页面位于 [此处](https://developer.chrome.com/extensions/nativeMessaging)。</span><span class="sxs-lookup"><span data-stu-id="b27cd-192">The original page is found [here](https://developer.chrome.com/extensions/nativeMessaging).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="b27cd-194">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="b27cd-194">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies
