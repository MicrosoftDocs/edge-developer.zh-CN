---
description: Chrome 文档的原始消息区别
title: 本机消息传递
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/15/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium、扩展开发、浏览器扩展、addons、合作伙伴中心、开发人员
ms.openlocfilehash: 811468e5f92319107c60606bc9268a9f7a25e560
ms.sourcegitcommit: d360e419b5f96f4f691cf7330b0d8dff9126f82e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2020
ms.locfileid: "11015674"
---
# 本机消息传递  

Microsoft Edge 现在允许从 Microsoft Edge Addons 目录 \ (Microsoft Edge Addons \ ) 中安装使用消息传递 Api 与本机应用程序交换消息的扩展。  若要启用该功能，需要在实现本机应用程序的本机消息传递主机时确保执行以下操作。  

<!--
 > [!NOTE]
> Native messaging is currently not supported on macOS and Linux version of Microsoft Edge.  This feature support is planned to be implemented soon.  -->  

1.  **本机消息主机**：  
    
    为了注册本机消息主机，应用程序必须安装定义本机消息主机配置的清单文件。  下面是清单文件的示例：  
    
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
    
本机消息主机清单文件必须是有效的 JSON，并且包含以下字段：  

| 名称 | 描述 |  
|:--- |:--- |  
| `name` | 本机消息主机的名称。 客户端将此字符串传递给 `runtime.connectNative` 或 `runtime.sendNativeMessage` 。  此名称必须仅包含小写字母数字字符、下划线和点符。  名称不能以点开始或结束，并且一个点后面不得跟另一个点。 |  
| `description` | 简短的应用程序说明。 |  
| `path` | 本机消息主机二进制文件的路径。  在 Windows 上，路径可能相对于清单文件所在的目录。  在 macOS 上，路径必须是绝对路径。  将启动主机进程，并将当前目录设置为包含主机二进制文件的目录。 例如，如果此参数设置为 `C:\Application\nm_host.exe` ，将使用当前目录启动二进制文件 `C:\Application\` 。 |  
| `type` | 用于与本机消息主机通信的接口类型。  目前，此参数仅有一个可能的值： `stdio` 。  此值表示 Chrome 应使用 `stdin` 并与 `stdout` 主机通信。 |  
| `allowed_origins` |  应访问本机消息主机的扩展列表。  若要使你的本机应用程序可识别 Microsoft Edge Addons 扩展并与之通信，请 `allowedorigins` `extension://[Microsoft-Catalog-extensionID]` 在你的本机消息主机清单文件中设置为。 |  

1.  **本机消息主机位置**  
    
    清单文件的位置取决于平台。  
    
    在 Windows 上，清单文件可能位于文件系统中的任何位置。  应用程序安装程序必须创建注册表项  
    
    `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_application`  
    或者  
    `HKEY_CURRENT_USER\SOFTWARE\Google\Chrome\NativeMessagingHosts\com.my_company.my_application`,  
    
    并将该注册表项的默认值设置为清单文件的完整路径。  例如，使用以下命令：  
    
    ```shell
    REG ADD "HKCU\Software\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_application" /ve /t REG_SZ /d "C:\path\to\nmh-manifest.json" /f
    ```  
    
    或使用以下 .reg 文件：  
    
    ```shell
    Windows Registry Editor Version 5.00
    [HKEY_CURRENT_USER\Software\Microsoft\Edge\NativeMessagingHosts\com.my_company.my_application]
    @="C:\\path\\to\\nmh-manifest.json"
    ```  
    
    当 Microsoft Edge 寻找本机邮件主机时，首先查询32位注册表，然后是64位的注册表。  

在 macOS 上，系统范围内的本机消息主机在固定位置查找，而用户级的本机消息主机在用户配置文件目录中的子目录中查找 `NativeMessagingHosts` 。  

MacOS 上的 Microsoft Edge (系统范围 \ ) ：  
`/Library/Microsoft/Edge/NativeMessagingHosts/com.my_company.my_application.json`  

MacOS \ 的 Microsoft Edge (特定于用户的默认路径 \ ) ：  
`~/Library/Application Support/Microsoft Edge <ChannelName>/ NativeMessagingHosts/com.my_company.my_application.json`  

`<ChannelName>` 可以是 "" "" 设备 "、" 开发 "或" Beta "。 对于稳定通道，仅 `Microsoft Edge` 应使用， `<ChannelName`>"不是必需的。

<!-- image links -->  

<!-- links -->  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 可在 [此处](https://developer.chrome.com/extensions/nativeMessaging)找到原始页面。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies
