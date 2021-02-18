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
# 本机消息传递  

扩展使用消息传递 API 与安装在用户设备上本机 Win32 应用程序进行通信。  本机应用程序主机使用标准输入和标准输出发送和接收扩展的邮件。  使用本机消息传递的扩展安装在 Microsoft Edge 中，与任何其他扩展类似。  但是，Microsoft Edge 不会安装或管理本机应用程序。  

若要获取扩展和本机应用程序主机，有两个分发模型。  

*   将扩展和主机打包在一起。  当用户安装程序包时，将同时安装扩展和主机。  
*   使用 [Microsoft Edge 加载项] [MicrosoftMicrosoftedgeAddonsMicrosoftEdgeExtensionsHome]存储安装扩展，扩展会提示用户安装主机。  

若要创建扩展以使用本机应用程序主机发送和接收邮件，请参阅以下步骤。  

## 步骤 1 - 向扩展清单添加权限  

将 `nativeMessaging` 权限添加到扩展 **manifest.js** 文件的权限。  下面的代码段是一个有关manifest.js** 的示例**。  

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

## 步骤 2 - 创建本机邮件主机清单文件  

本机应用程序必须提供本机邮件主机清单文件。  清单文件包含以下信息。  

*   本机消息传递主机运行时的路径。  
*   与扩展通信的方法。  
*   它所通信的允许的扩展的列表。  
    
浏览器读取并验证本机邮件主机清单。  浏览器不会安装或管理本机邮件主机清单文件。  

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

主机清单文件必须是包含以下密钥的有效 JSON 文件。  

:::row:::
   :::column span="1":::
      `name`  
   :::column-end:::
   :::column span="2":::
      指定本机消息传递主机的名称。  客户端将此字符串传递给 `runtime.connectNative` 或 `runtime.sendNativeMessage` 。  
      
      *   此值只能包含小写字母数字字符、下划线和点。  
      *   此值不得以点开始或结尾，并且一个点不得后跟另一个点。  
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
      指定本机消息传递主机二进制文件的路径。  
      
      *   在 Windows 设备上，可以使用包含清单文件的目录的相对路径。  
      *   在 macOS 和 Linux 上，路径必须是绝对路径。  
      
      主机进程从当前目录设置为包含主机二进制文件的目录开始。  例如 \ (Windows\) ，如果此参数设置为 ，则使用当前目录 `C:\Application\nm_host.exe` \ (`C:\Application\` \) 启动二进制文件。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      `type`  
   :::column-end:::
   :::column span="2":::
      指定用于与本机消息传递主机进行通信的接口的类型。  此值指示 Microsoft Edge 使用 `stdin` 主机 `stdout` 并与主机通信。  
      唯一可接受的值为 `stdio` 。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      `allowed_origins` 
   :::column-end:::
   :::column span="2":::
      指定有权访问本机邮件主机的扩展的列表。  若要使应用程序能够标识扩展并与扩展通信，请在你的本机邮件主机清单文件中设置以下值。  
      
      ```json
      "allowed_origins": ["chrome-extension://{microsoft_catalog_extension_id}"]
      ```  
   :::column-end:::
:::row-end:::  

旁加载扩展以测试主机的本机消息。  
若要在开发和检索期间旁加载扩展 `microsoft_catalog_extension_id` ，请完成以下步骤。  

1.  导航 `edge://extensions` 到 ，然后打开开发人员模式切换按钮。  
1.  选择 **"加载解压缩"，** 然后选择要旁加载的扩展包。  
1.  选择“确定”****。  
1.  导航 `edge://extensions` 到页面并验证扩展是否列出。  
1.  从页面上的扩展 `microsoft_catalog_extension_id` (\ (ID\) 复制密钥。  

准备好将扩展分发给用户时，将扩展发布到 Microsoft Edge 加载项存储。  已发布扩展的扩展 ID 可能与旁加载扩展时所使用的 ID 不同。  如果 ID 发生更改，则使用已发布扩展的 ID 在主机清单 `allowed_origins` 文件中进行更新。  

## 步骤 3 - 将本机邮件主机清单文件复制到系统  

最后一步是将本机邮件主机清单文件复制到计算机，并确保清单文件配置正确。  若要确保清单文件放置在预期位置，请完成以下步骤。  位置因平台而异。  

### [Windows](#tab/windows/)  

<a id="copy-manifest-file"></a>  

清单文件可能位于文件系统中的任何位置。  应用程序安装程序必须创建注册表项，将注册表项的默认值设置为清单文件的完整路径。  以下命令是注册表项的示例。  

```text
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_application
```

```text
HKEY_CURRENT_USER\SOFTWARE\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_application
```

使用清单项向目录添加注册表项。  

*   在命令提示符中运行命令。  
    
    1.  运行以下命令。  
        
        ```shell
        REG ADD "HKCU\Software\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_application" /ve /t REG_SZ /d "C:\path\to\nmh-manifest.json" /f
        ```  
    
*   创建 `.reg` 并运行文件。  
    
    1.  将以下命令复制到 `.reg` 文件中。  
        
        ```shell
        Windows Registry Editor Version 5.00
        [HKEY_CURRENT_USER\Software\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_application]
        @="C:\\path\\to\\nmh-manifest.json"
        ```  
        
    1.  运行 `.reg` 该文件。  
    
Microsoft Edge 查询后 `HKEY_CURRENT_USER` 跟的根键 `HKEY_LOCAL_MACHINE` 。  在这两项中，首先搜索 32 位注册表，然后搜索 64 位注册表以标识本机邮件主机。  注册表项指定本机邮件主机清单的位置。  如果 Microsoft Edge 在之前列出的任何位置找到注册表项，则它不会查询此段落中列出的位置。  如果作为批处理脚本的一部分运行上述文件，请确保使用管理员命令提示符 `.reg` 运行该文件。  

### [macOS](#tab/macos/)  

<a id="copy-manifest-file"></a>  

若要存储清单文件，请完成以下操作之一。  

*   可供所有用户使用的系统范围的本机邮件主机存储在固定位置。  例如，清单文件必须存储在以下位置。  
    
    ```bash
    /Library/Microsoft/Edge/NativeMessagingHosts/com.my_company.my_application.json
    ```  
    
*   用户特定的本机消息传递主机（仅对当前用户可用）位于用户配置文件目录中的子 `NativeMessagingHosts` 目录中。  例如，清单文件必须存储在以下位置。  
    
    ```bash
    ~/Library/Application Support/Microsoft Edge {Channel_Name}/NativeMessagingHosts/com.my_company.my_application.json
    ```  
    
    in  `{Channel_Name}` `Microsoft Edge {Channel_Name}` 必须是下列值之一。  
    
    *   Canary  
    *   Dev  
    *   Beta  

    使用 Stable 渠道 `{Channel_Name}` 时，不是必需的。  

### [Linux](#tab/linux/)  

<a id="copy-manifest-file"></a>  

若要存储清单文件，请完成以下操作之一。  

*   可供所有用户使用的系统范围的本机邮件主机存储在固定位置。  清单文件必须存储在以下位置。  
    
    ```bash
    /etc/opt/edge/native-messaging-hosts
    ```
    
*   用户特定的本机消息传递主机（仅对当前用户可用）位于用户配置文件目录中的子 `NativeMessagingHosts` 目录中。  清单文件必须存储在以下位置。  
    
    ```bash
    ~/.config/microsoft-edge/NativeMessagingHosts
    ```  
    
* * *  

> [!NOTE]
> 确保对清单文件提供读取权限，并运行主机运行时的权限。  

<!-- links -->  


 [MicrosoftMicrosoftedgeAddonsMicrosoftEdgeExtensionsHome]: https://microsoftedge.microsoft.com/addons/Microsoft-Edge-Extensions-Home "Microsoft Edge 加载项"

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于 [此处](https://developer.chrome.com/extensions/nativeMessaging)。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies
