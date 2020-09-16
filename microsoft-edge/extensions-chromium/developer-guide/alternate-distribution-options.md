---
description: 通过经验证的应用商店以外的机制分配扩展的过程
title: 分发扩展的备用方法
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/15/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium、扩展开发、浏览器扩展、addons、合作伙伴中心、开发人员
ms.openlocfilehash: e28a84fd75ad1ac0be2000a22c26371ca73d0293
ms.sourcegitcommit: d360e419b5f96f4f691cf7330b0d8dff9126f82e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2020
ms.locfileid: "11015693"
---
# 分发扩展的备用方法  

如果你是要为其他软件的安装过程的一部分分发扩展的开发人员，或者是希望在其整个组织中分发扩展的网络管理员，Microsoft Edge 支持以下扩展安装方法：  

*   **仅使用 Windows 注册表 \ (Windows ) **  

Microsoft Edge 支持安装托管的扩展 `update_URL` 。  在 Windows 上， `update_URL` 必须指向 Microsoft Edge Addons catalog \ (Microsoft Edge Addons \ ) 必须在其中托管扩展的位置。  

> [!NOTE]
> 通过 macOS 的首选项 json 文件进行扩展的外部安装 <!--and Linux--> 尚不支持。  此功能支持将很快推出。

## 使用 Windows 注册表  

首先，在 Microsoft Edge Addons 中发布扩展，或将 crx 文件打包，并确保它成功安装。  

通过 windows 中的注册表安装扩展的步骤如下：  

*   在注册表中查找或创建以下注册表项：  
    *   32位 Windows：  `HKEY_LOCAL_MACHINE\Software\Microsoft\Edge\Extensions`  
    *   64位 Windows：  `HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Edge\Extensions`  
*   创建一个新的键 \ (文件夹 \ ) ，使用与扩展名 \ 的 ID 相同的扩展名 \ (例如， `aaaaaaaaaabbbbbbbbbbcccccccccc` \ ) 。  
*   在你的扩展键中，创建一个属性， `update_url` 并将其设置为值： `https://edge.microsoft.com/extensionwebstorebase/v1/crx` ，\ (这一点指向 Microsoft Edge Addons \ ) 中的扩展 crx。 如果想要从 Chrome Web Store 安装扩展，请提供 Chrome Web Store 更新 URL `https://clients2.google.com/service/update2/crx` 。  
    
    ```javascript
    {
        "update_url": "https://edge.microsoft.com/extensionwebstorebase/v1/crx"
    }
    ```  
    
*   启动浏览器并转到 `edge://extensions` ; 你应该看到列出的扩展名。  

## 更新和卸载  

每次浏览器启动时，Microsoft Edge 将扫描注册表中的元数据条目，并对已安装的外部扩展进行任何必要的更改。  

若要将扩展更新到新版本，请更新文件，然后更新注册表中的版本。  

若要卸载扩展 \ (例如，如果软件已卸载 \ ) ，请从注册表中删除您的首选项文件 \ (`aaaaaaaaaabbbbbbbbbbcccccccccc.json` \ ) 或元数据。  

<!-- image links -->  

<!-- links -->  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 可在 [此处](https://developer.chrome.com/apps/external_extensions)找到原始页面。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies
