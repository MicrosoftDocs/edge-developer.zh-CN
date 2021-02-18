---
description: 将 Chrome 扩展移植到 Microsoft Edge 的过程
title: 将 Chrome 扩展移植到 Microsoft Edge
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/17/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium， 扩展开发， 浏览器扩展， 加载项， 合作伙伴中心， 开发人员
ms.openlocfilehash: 6be7d788ac22232475e278ae9a5b04de9b6e17f7
ms.sourcegitcommit: 916b4daa26c2c78611f7d837bd6ecf009f0082df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/17/2021
ms.locfileid: "11343134"
---
# 移植扩展  

Microsoft Edge 允许你以最少的更改移植 Chrome 扩展。  Chrome 支持的扩展 API 和清单密钥与 Microsoft Edge 代码兼容。  有关 Microsoft Edge 支持的 API 列表，请导航到 [API 支持][ExtensionApiSupport]。  

若要移植 Chrome 扩展，请完成以下步骤。  

1.  使用 Microsoft Edge 扩展支持的 API 列表查看扩展中使用的 Chrome[扩展 API。][ExtensionApiSupport]  
    
    > [!NOTE]
    > 如果你的扩展使用 Microsoft Edge 不支持的 API，它可能不会直接移植。  
    
1.  在清单文件中，将 `update_URL` 字段设置为 `https://edge.microsoft.com/extensionwebstorebase/v1/crx` 。  该值指向 Microsoft Edge 加载项存储中的扩展文件，并允许 `.crx` Microsoft Edge 检查扩展更新。  
1.  如果在扩展的名称或说明中使用，则使用重新 `Chrome` 命名扩展 `Microsoft Edge` 。  若要通过认证过程，需要更改。  
1.  通过旁加载扩展测试扩展以检查它在 Microsoft Edge [中是否正常工作][ExtensionsGettingStartedExtensionSideloading]。  
1.  如果面临任何问题，可以使用 DevTools 在 Microsoft Edge 中调试扩展， [或联系我们][mailtoExtensionMicrosoft]。  
1.  按照 [发布指南在][ExtensionsPublishPublishExtension] Microsoft Edge 加载项存储上发布扩展。  
    
    > [!NOTE]
    > 如果扩展使用本机应用交换邮件，请确保在本机邮件主机清单文件中 `chrome.runtime.connectNative` `allowed_origins` `extension://[Microsoft-Catalog-extensionID]` 设置为。  该设置允许应用标识你的扩展。  
    
## 后续步骤  

在扩展包准备好在 Microsoft Edge 加载项存储中发布后，创建开发人员[帐户][ExtensionsPublishCreateDevAccount][并发布扩展][ExtensionsPublishPublishExtension]。  

<!-- links -->  

[ExtensionApiSupport]: ./api-support.md "API 支持|Microsoft Docs"  
[ExtensionsGettingStartedExtensionSideloading]: ../getting-started/extension-sideloading.md "旁加载扩展|Microsoft Docs"  
[ExtensionsPublishCreateDevAccount]: ../publish/create-dev-account.md "开发人员注册|Microsoft Docs"  
[ExtensionsPublishPublishExtension]: ../publish/publish-extension.md "发布扩展|Microsoft Docs"  

[ChromeDeveloperWebStorePayments]: https://developer.chrome.com/webstore/one_time_payments "一次付款|Chrome 开发人员"  

[mailtoExtensionMicrosoft]: mailto:ext_dev_support@microsoft.com "ext_dev_support@microsoft.com"  
