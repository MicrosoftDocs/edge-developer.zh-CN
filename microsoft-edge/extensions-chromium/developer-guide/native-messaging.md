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
# 本机消息传递  

扩展可以使用消息传递 Api 与用户设备上安装的本机 Win32 应用程序进行通信。 本机应用程序主机可以使用标准输入和标准输出发送和接收带有扩展的消息。 使用本机消息的扩展安装在与任何其他扩展类似的 Microsoft Edge 中。 但是，本机应用程序不是由 Microsoft Edge 安装或管理的。

若要获取扩展和本机应用程序宿主，可以执行以下操作：

1. 将扩展和主机打包在一起。 当用户安装程序包时，将同时安装扩展和主机。
1. 从 [Microsoft Edge 加载项存储区][EdgeAddons]安装扩展，并让你的扩展提示用户安装主机。 

请参阅下面的步骤以设置您的扩展，以通过本机应用程序主机发送和接收邮件。

### 步骤1：向扩展清单添加权限

将 nativeMessaging 权限添加到文件的扩展 **manifest.js** 。 下面是 manifest.js的示例：

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

### 步骤2：创建本机消息主机清单文件
    
本机应用程序必须提供本机消息主机清单文件。 此清单文件包含本机消息传递主机可执行文件的路径、与扩展的通信方法以及可与之通信的允许扩展的列表。 浏览器读取和验证本机消息主机清单，但它从不由浏览器安装或管理。 主机清单文件必须是包含以下字段的有效 json 文件。

    
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




| 名称 | 描述 |  
|:--- |:--- |  
| `name` | 本机消息主机的名称。 客户端将此字符串传递给 `runtime.connectNative` 或 `runtime.sendNativeMessage` 。  此名称必须仅包含小写字母数字字符、下划线和点符。  名称不能以点开始或结束，并且一个点后面不得跟另一个点。 |  
| `description` | 应用程序的简要说明。 |  
| `path` | 本机消息主机二进制文件的路径。 在 Windows 设备上，你可以使用包含清单文件的目录的相对路径。 在 macOS 和 Linux 上，路径必须是绝对路径。 将启动主机进程，并将当前目录设置为包含主机二进制文件的目录。 例如，如果此参数设置为，将 `C:\Application\nm_host.exe` 使用当前目录启动二进制文件 `C:\Application\` 。 |  
| `type` | 用于与本机消息主机通信的接口类型。  目前，此参数仅有一个可能的值： `stdio` 。  此值表示 Microsoft Edge 应使用 `stdin` 并与 `stdout` 主机通信。 |  
| `allowed_origins` |  可访问本机消息主机的扩展列表。  若要使你的应用能够标识和通信，请 `allowed_origins` `chrome-extension://[Microsoft-Catalog-extensionID]` 在你的本机消息主机清单文件中设置为。 |  


在开发过程中，你可以通过以下方式旁加载扩展以通过主机测试本机消息传递：
1. 导航到 `edge://extensions` ，然后打开 "开发人员模式切换" 按钮。 
1. 选择 "加载解包"，然后选择扩展包到旁加载。  
1. 选择“确定”。
1. 验证 `edge://extensions` 页面现在是否会列出你的扩展。 
1. 从页面上的 "扩展" 列表中复制 "ID" 中的密钥。

准备好将扩展分发给用户后，将扩展发布到 Microsoft Edge 加载项存储。 已发布扩展的扩展 ID 可能与在旁加载你的扩展时使用的 ID 不同。 如果 ID 已更改，请 `allowed_origins` 在具有已发布扩展的 ID 的主机清单文件中更新。 



### 步骤3：将本机消息主机清单文件复制到系统

最后一步是将本机消息主机清单文件复制到你的计算机，并确保其配置正确。 请按照下列步骤操作，确保将本机消息传递主机文件放置在预期位置，因为它因平台而异。
    
**Windows**。 清单文件可能位于文件系统中的任何位置。 应用程序安装程序必须创建一个注册表项，并将该注册表项的默认值设置为清单文件的完整路径。 以下命令是注册表项的示例。
    
`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_application`  
    或者  
`HKEY_CURRENT_USER\SOFTWARE\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_application`,  
    
在命令提示符处运行以下命令，将注册表项添加到带有清单文件的文件夹。
    
```shell
REG ADD "HKCU\Software\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_application" /ve /t REG_SZ /d "C:\path\to\nmh-manifest.json" /f
```  
    
或者，将以下命令复制到 .reg 文件，然后运行它以添加注册表项。 
    
```shell
Windows Registry Editor Version 5.00
[HKEY_CURRENT_USER\Software\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_application]
@="C:\\path\\to\\nmh-manifest.json"
``` 

  Microsoft Edge 首先查询32位注册表，然后是64位注册表来标识本机消息主机。 如果作为批处理脚本的一部分运行上述 .reg 文件，请确保使用管理员命令提示符运行该文件。


**macOS**。 清单文件必须按如下方式存储：

1. 系统范围内可供所有用户使用的本机消息传递主机存储在固定位置。 例如，清单文件必须存储在 `/Library/Microsoft/Edge/NativeMessagingHosts/com.my_company.my_application.json`

1. 特定于用户的本机消息主机（仅适用于当前用户）位于用户配置文件目录中的 NativeMessagingHosts 子目录中。 例如，清单文件必须存储在  
    `~/Library/Application Support/Microsoft Edge <ChannelName>/NativeMessagingHosts/com.my_company.my_application.json`

    在哪里 `ChannelName` 可以是 "有地方"、"开发" 或 "Beta"。 使用稳定频道时， `ChannelName` 不需要。


**Linux** 清单文件必须按如下方式存储：

1. 系统范围内的本机消息传递主机：  `~/.config/microsoft-edge/NativeMessagingHosts`

1. 特定于用户的本机消息主机：  `/etc/opt/edge/native-messaging-hosts`


> [!NOTE]
> 确保提供对清单文件的读取权限以及对主机可执行文件的执行权限。


> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 可在 [此处](https://developer.chrome.com/extensions/nativeMessaging)找到原始页面。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  


<!-- image links -->  

<!-- links -->  

[EdgeAddons]: https://microsoftedge.microsoft.com/addons/Microsoft-Edge-Extensions-Home "Microsoft Edge 加载项"
[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies
