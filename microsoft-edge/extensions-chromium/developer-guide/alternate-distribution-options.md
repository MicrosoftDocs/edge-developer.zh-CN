---
description: 了解如何使用不使用已验证存储的备用方法分发扩展
title: 分发扩展的备用方法
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/17/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium， 扩展开发， 浏览器扩展， 加载项， 合作伙伴中心， 开发人员
ms.openlocfilehash: 3b2c72e13488632e2fadea2a7e8eb95888f67170
ms.sourcegitcommit: 916b4daa26c2c78611f7d837bd6ecf009f0082df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/17/2021
ms.locfileid: "11343148"
---
# 备用扩展分发方法  

通常，扩展通过 Microsoft Edge 加载项存储分发。 在某些情况下，开发人员可能需要使用备用方法分发扩展。 例如：

1.  扩展与其他软件相关联，并且应该与捆绑软件的其余部分一起安装。   
1.  网络管理员希望在整个组织中分发扩展。   

未从边缘加载项存储加载的扩展称为外部安装的扩展。 以下列表提供了分发外部安装的扩展的备用方法。 

*   使用 Windows 注册表 (Windows) 。  
*   将首选项 JSON 文件 (macOS 和 Linux) 。  
    
## 开始之前  

请确保在 Microsoft Edge 加载项存储中发布扩展名，或打包文件，并确保它 `.crx` 已成功安装在您的计算机上。  如果使用 安装 `.crx` 文件， `update_URL` 请确保可以导航到该 URL 的扩展名。  

此外，请确保你拥有以下信息。    

1.  文件的文件 `.crx` 路径或扩展 `update_URL` 名。
1.  扩展的版本。  版本信息可在清单文件中提供，或在加载打包的扩展后在 Microsoft Edge `edge://extensions` 中提供。   
1.  扩展的 ID。  在加载打包的扩展后，Microsoft Edge 中会提供 `edge://extensions` ID 信息。  

> [!NOTE] 
> 以下示例用作 `1.0` 版本和 `aaaaaaaaaabbbbbbbbbbcccccccccc` ID。  

## 使用 Windows 注册表 (Windows 注册表)   

若要使用 Windows 注册表分发扩展，请执行以下步骤。

1.  在注册表中查找或创建以下项：  
    *   32 位 Windows：  `HKEY_LOCAL_MACHINE\Software\Microsoft\Edge\Extensions` .  
    *   64 位 Windows：  `HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Edge\Extensions` .  
1.  在扩展名下新建一个密钥或**** 文件夹，其名称与扩展的 ID 相同。 例如，使用名称创建键 `aaaaaaaaaabbbbbbbbbbcccccccccc` 。  
1.  在 **Extensions** 键中，创建 `update_url` 属性，将值设置为 `https://edge.microsoft.com/extensionwebstorebase/v1/crx` 。  该属性指向 Microsoft Edge 加载项存储 `update_url` `.crx` 中扩展名的文件。  

    ```json
    {
        "update_url": "https://edge.microsoft.com/extensionwebstorebase/v1/crx"
    }
    ```  
    
    > [!NOTE]
    > 如果要从 Chrome Web 应用商店安装扩展，将值 `update_url` 设置为 `https://clients2.google.com/service/update2/crx` 。  
  
1.  通过导航到验证你的扩展是否列在 Microsoft Edge 中 `edge://extensions` 。  

## 将首选项 JSON 文件 (macOS 和 Linux)   

若要使用首选项 JSON 文件分发扩展名，请执行以下步骤。

1.  使用 Linux 时，请确保扩展文件在将安装扩展的计算机 `.crx` 中可用。 将扩展文件复制到本地目录，或使用计算机可访问的网络 `.crx` 共享。 
1.  创建一个 JSON 文件，该文件的名称对应于扩展名的 ID。 例如，创建具有文件名的 JSON 文件 `aaaaaaaaaabbbbbbbbbbcccccccccc.json` 。  
1.  根据您的操作系统，将 JSON 文件保存到以下文件夹之一。   
    *   **macOS**  
        *   特定于用户： `~USERNAME/Library/Application Support/Microsoft Edge/External Extensions/`  
        *   所有用户： `/Library/Application Support/Microsoft/Edge/External Extensions/`  
        
        若要防止未经授权的用户为所有用户安装扩展，请确保扩展文件是只读的。 此外，请确保满足以下条件：
        
        *   路径中的每个目录归用户根所有。  
        *   路径中的每个目录都分配给或 `admin` `wheel` 组。  
        *   路径中的每个目录都不可写入。  
        *   路径还必须没有符号链接。  
        
    *   **Linux**  
        *   特定于用户： `~/.config/microsoft-edge/External Extensions/`  
        *   所有用户： `/usr/share/microsoft-edge/extensions/`  
1.  根据您的方案，将相应的代码复制到 JSON 文件。 
    *   仅适用于 Linux。 如果从文件安装，则使用 和 指定位置和 `external_crx` 版本 `external_version` 。  
            
        ```json
        {
            "external_crx": "/home/share/extension.crx",
            "external_version": "1.0"
        }
        ```  

    *   适用于 macOS 和 Linux。 如果从安装位置 `update_URL` 安装，则使用 指定更新 `external_update_url` URL。 
        
        仅在 Linux 上从本地文件安装时，将以下代码 `.crx` 复制到 JSON 文件。  
    
        ```json
        {
            "external_update_url": "http://myhost.com/mytestextension/updates.xml"
        }
        ```  
 
    *  从 macOS 和 Linux 上的 Microsoft Edge 加载项存储安装时，将以下代码复制到 JSON 文件。
    
        ```json
        {
            "external_update_url": "https://edge.microsoft.com/extensionwebstorebase/v1/crx"
        }
        ```  
    
1.  若要安装特定区域设置扩展，使用 列出受支持的区域设置 `supported_locale` 。  还可以指定父区域设置，为使用该父级的所有语言区域设置安装扩展。 例如，使用父区域设置时，扩展会针对所有英语区域设置（如 `en` `en-US` ， `en-GB` 等）进行安装。  当用户在浏览器中更改其区域设置时，将卸载外部安装的扩展。  若要安装任何区域设置扩展，请不要使用 `supported_locales` 。  

    ```json
    {
        "external_update_url": "https://edge.microsoft.com/extensionwebstorebase/v1/crx",
        "supported_locales": [ "en", "fr", "de" ]
    }
    ```  

1.  通过导航到验证你的扩展是否安装在 Microsoft Edge 中 `edge://extensions` 。  

## 更新和卸载外部安装的扩展

每次浏览器启动时，Microsoft Edge 会扫描注册表中的元数据条目，并更改外部安装的扩展。  

若要将扩展更新到新版本，请更新清单文件中的版本，然后在注册表中更新版本。  

您可能需要卸载外部安装的扩展，这些扩展作为以前安装在计算机上的软件捆绑包的一部分进行安装。  若要卸载扩展，请删除首选项 JSON 文件或从注册表中删除项。   

<!-- links -->  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  原始页面位于 [此处](https://developer.chrome.com/apps/external_extensions)。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
