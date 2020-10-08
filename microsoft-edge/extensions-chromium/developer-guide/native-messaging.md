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
# 本机消息传递  

扩展使用消息传递 Api 与用户设备上安装的本机 Win32 应用程序进行通信。  本机应用程序主机使用标准输入和标准输出发送和接收带有扩展的消息。  使用本机消息的扩展安装在与任何其他扩展类似的 Microsoft Edge 中。  但是，本机应用程序不是由 Microsoft Edge 安装或管理的。  

若要获取扩展和本机应用程序主机，您有两种分布模型。  

*   将您的扩展和主机打包在一起。  当用户安装程序包时，将同时安装扩展和主机。
*   使用 [Microsoft Edge 加载项存储区][EdgeAddons]安装你的扩展，并且你的扩展会提示用户安装主机。  

若要创建用于通过本机应用程序主机发送和接收消息的扩展，请参阅以下步骤。  

## 步骤 1-将权限添加到扩展清单  

`nativeMessaging`在扩展名的文件中添加对**manifest.js**的权限。  下面的代码片段是 **manifest.js**的示例。  

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

## 步骤 2-创建本机消息主机清单文件  

本机应用程序必须提供本机消息主机清单文件。  清单文件包含本机消息传递主机运行时的路径、与扩展的通信方法，以及与其通信的允许扩展名的列表。  浏览器读取并验证本机消息主机清单。  浏览器不会安装或管理本机消息主机清单文件。  

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

主机清单文件必须是包含以下键的有效 JSON 文件。  

:::row:::
   :::column span="1":::
      `name`  
   :::column-end:::
   :::column span="2":::
      指定本机消息主机的名称。  客户端将此字符串传递给 `runtime.connectNative` 或 `runtime.sendNativeMessage` 。  
      
      *   此值必须仅包含小写字母数字字符、下划线和点状。  
      *   此值不能以点开始或结束，并且一个点后面不得跟另一个点。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      `description`  
   :::column-end:::
   :::column span="2":::
      描述应用程序。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      `path`  
   :::column-end:::
   :::column span="2":::
      指定本机消息主机二进制文件的路径。  
      
      *   在 Windows 设备上，你可以使用包含清单文件的目录的相对路径。  
      *   在 macOS 和 Linux 上，路径必须是绝对路径。  
      
      主进程从设置为包含主机二进制文件的目录的当前目录开始。  例如，\ (Windows \ ) ，如果此参数设置为 `C:\Application\nm_host.exe` ，将使用当前目录 \ (\ ) 启动二进制文件 `C:\Application\` 。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      `type`  
   :::column-end:::
   :::column span="2":::
      指定用于与本机消息主机通信的接口的类型。  此值指示 Microsoft Edge 使用 `stdin` 和与 `stdout` 主机通信。  
      唯一可接受的值为 `stdio` 。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      `allowed_origins` 
   :::column-end:::
   :::column span="2":::
      指定有权访问本机消息主机的扩展列表。  若要使你的应用程序能够识别扩展并与之通信，请在你的本机消息主机清单文件中设置以下值。  
      
      ```json
      "allowed_origins": ["chrome-extension://{microsoft_catalog_extension_id}"]
      ```  
   :::column-end:::
:::row-end:::  

旁加载您的扩展，以通过主机测试本机消息传递。  
若要在开发和检索期间旁加载扩展 `microsoft_catalog_extension_id` ，请完成以下步骤。  

1.  导航到 `edge://extensions` ，然后打开 "开发人员模式切换" 按钮。  
1.  选择 " **加载解包**"，然后选择扩展包到旁加载。  
1.  选择“确定”****。
1.  导航到 `edge://extensions` 页面并验证您的扩展是否已列出。  
1.  将密钥从 `microsoft_catalog_extension_id` 页面上的扩展列表中的 \ (ID \ ) 复制。

准备好将扩展分发给用户后，将扩展发布到 Microsoft Edge 加载项存储。  已发布扩展的扩展 ID 可能与在旁加载你的扩展时使用的 ID 不同。  如果 ID 已更改，请 `allowed_origins` 在具有已发布扩展的 ID 的主机清单文件中更新。  

## 步骤 3-将本机消息主机清单文件复制到系统  

最后一步是将本机消息主机清单文件复制到计算机，并确保它配置正确。  若要确保清单文件放置在预期位置，请完成以下步骤。  该位置因平台而异。  

### [Windows](#tab/windows/)  

<a id="copy-manifest-file"></a>  

清单文件可能位于文件系统中的任何位置。  应用程序安装程序必须创建一个注册表项，并将该注册表项的默认值设置为清单文件的完整路径。  以下命令是注册表项的示例。  

```text
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_application
```

```text
HKEY_CURRENT_USER\SOFTWARE\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_application
```

将注册表项添加到具有清单键的目录中。  

*   在命令提示符下运行命令。    
    
    1.  运行以下命令。  
        
        ```shell
        REG ADD "HKCU\Software\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_application" /ve /t REG_SZ /d "C:\path\to\nmh-manifest.json" /f
        ```  
    
*   创建一个 `.reg` 文件并运行它。  
    
    1.  将以下命令复制到 `.reg` 文件中。  
        
        ```shell
        Windows Registry Editor Version 5.00
        [HKEY_CURRENT_USER\Software\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_application]
        @="C:\\path\\to\\nmh-manifest.json"
        ```  
        
    1.  运行该 `.reg` 文件。  
    
Microsoft Edge 首先查询32位注册表，然后是64位注册表来标识本机消息主机。  如果将上述 `.reg` 文件作为批处理脚本的一部分运行，请确保使用管理员命令提示符运行它。  

### [macOS](#tab/macos/)  

<a id="copy-manifest-file"></a>  

若要存储清单文件，请完成以下操作之一。  

*   系统范围内可供所有用户使用的本机消息传递主机存储在固定位置。  例如，清单文件必须存储在以下位置。 
    
    ```bash
    /Library/Microsoft/Edge/NativeMessagingHosts/com.my_company.my_application.json
    ```  
    
*   特定于用户的本机消息主机（仅适用于当前用户）位于 `NativeMessagingHosts` 用户配置文件目录中的子目录中。  例如，清单文件必须存储在以下位置。  
    
    ```bash
    ~/Library/Application Support/Microsoft Edge {Channel_Name}/NativeMessagingHosts/com.my_company.my_application.json
    ```  
    
    `{Channel_Name}`In `Microsoft Edge {Channel_Name}` 必须是下列值之一。  
    
    *   Canary  
    *   Dev  
    *   Beta  

    使用稳定通道时， `{Channel_Name}` 不是必需的。  

### [Linux](#tab/linux/)  

<a id="copy-manifest-file"></a>  

若要存储清单文件，请完成以下操作之一。  

*   系统范围内可供所有用户使用的本机消息传递主机存储在固定位置。  清单文件必须存储在以下位置。  
    
    ```bash
    /etc/opt/edge/native-messaging-hosts
    ```
    
*   特定于用户的本机消息主机（仅适用于当前用户）位于 `NativeMessagingHosts` 用户配置文件目录中的子目录中。  清单文件必须存储在以下位置。  
    
    ```bash
    ~/.config/microsoft-edge/NativeMessagingHosts
    ```  
    
* * *  

> [!NOTE]
> 确保在清单文件上提供读取权限，并确保在主机运行时上运行权限。  

<!-- links -->  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 可在 [此处](https://developer.chrome.com/extensions/nativeMessaging)找到原始页面。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[EdgeAddons]: https://microsoftedge.microsoft.com/addons/Microsoft-Edge-Extensions-Home "Microsoft Edge 加载项"
[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies
