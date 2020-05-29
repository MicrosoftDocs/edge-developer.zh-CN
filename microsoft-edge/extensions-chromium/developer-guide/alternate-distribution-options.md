---
description: 通过经验证的应用商店以外的机制分配扩展的过程
title: 分发扩展的备用方法
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/02/2019
ms.topic: article
ms.prod: microsoft-edge-chromium
keywords: edge-chromium、扩展开发、浏览器扩展、addons、合作伙伴中心、开发人员
ms.openlocfilehash: a1a3ffe7a54f96df7e665ab5dc6f5b99bacb8b8e
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563384"
---
# 分发扩展的备用方法  

如果你是要为其他软件的安装过程的一部分分发扩展的开发人员，或者是希望在其整个组织中分发扩展的网络管理员，Microsoft Edge 支持以下扩展安装方法：  

*   **使用 Windows 注册表 \ （仅限 Windows \）**  

Microsoft Edge 支持安装托管的扩展 `update_URL` 。  在 Windows 上， `update_URL` 必须指向必须托管扩展的 Microsoft Edge Addons 目录 \ （Microsoft Edge Addons \）。  

> [!NOTE]
> 通过 macOS 的首选项 json 文件进行扩展的外部安装 <!--and Linux--> 尚不支持。  此功能支持将很快推出。

## 使用 Windows 注册表  

首先，在 Microsoft Edge Addons 中发布扩展，或将 crx 文件打包，并确保它成功安装。  

通过 windows 中的注册表安装扩展的步骤如下：  

*   在注册表中查找或创建以下注册表项：  
    *   32位 Windows：  `HKEY_LOCAL_MACHINE\Software\Microsoft\Edge\Extensions`  
    *   64位 Windows：  `HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Edge\Extensions`  
*   在 "Extensions" 键下创建一个新的键 \ （文件夹 \），其名称与您的扩展名 \ （例如 \）的 ID 相同 `aaaaaaaaaabbbbbbbbbbcccccccccc` 。  
*   在你的扩展键中，创建一个属性， `update_url` 并将其设置为值： `https://edge.microsoft.com/extensionwebstorebase/v1/crx` ，\ （这指向 Microsoft Edge Addons \）中的 crx 扩展名。 如果想要从 Chrome Web Store 安装扩展，请提供 Chrome Web Store 更新 URL `https://clients2.google.com/service/update2/crx` 。  
    
    ```javascript
    {
        "update_url": "https://edge.microsoft.com/extensionwebstorebase/v1/crx"
    }
    ```  
    
*   启动浏览器并转到 `edge://extensions` ; 你应该看到列出的扩展名。  

## 更新和卸载  

每次浏览器启动时，Microsoft Edge 将扫描注册表中的元数据条目，并对已安装的外部扩展进行任何必要的更改。  

若要将扩展更新到新版本，请更新文件，然后更新注册表中的版本。  

若要卸载你的扩展 \ （例如，如果你的软件已卸载 \），请从注册表中删除你的首选项文件 \ （ `aaaaaaaaaabbbbbbbbbbcccccccccc.json` \）或元数据。  

<!-- image links -->  

<!-- links -->  

> [!NOTE]
> 此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。  
> 可在[此处](https://developer.chrome.com/apps/external_extensions)找到原始页面。  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies
