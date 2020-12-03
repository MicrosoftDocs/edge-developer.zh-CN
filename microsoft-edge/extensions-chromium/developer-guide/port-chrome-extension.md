---
description: 将 Chrome 扩展移植到 Microsoft Edge 的过程。
title: 将端口 Chrome 扩展到 Microsoft Edge
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/25/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium、扩展开发、浏览器扩展、addons、合作伙伴中心、开发人员
ms.openlocfilehash: 0f767107bfb259476d1ab35d081fb9bb05c81b46
ms.sourcegitcommit: e79503c6c53ea9b7de58f8cf1532b5c82116a6eb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2020
ms.locfileid: "11195157"
---
# 移植分机  

Microsoft Edge 允许你将 Chrome 扩展移植到最少的更改。  Chrome 支持的扩展 Api 和清单键是与 Microsoft Edge 兼容的代码。  有关 Microsoft Edge 支持的 Api 的列表，请导航到 [API 支持][ExtensionApiSupport]。  

若要移植 Chrome 扩展，请完成以下步骤。  

1.  使用 Microsoft Edge 扩展 [支持的 api][ExtensionApiSupport] 列表查看你的扩展中使用的 Chrome 扩展 api。  
    
    > [!NOTE]
    > 如果你的扩展使用的 Api 不受 Microsoft Edge 支持，则它不能直接移植。  
    
1.  如果 `Chrome` 要在扩展名的名称或说明中使用该名称，请为 rebrand 的扩展名 `Microsoft Edge` 。  必须执行此步骤才能传递认证过程。  
1.  通过 [旁加载你的扩展][ExtensionsGettingStartedExtensionSideloading]来测试你的扩展，以检查它在 Microsoft Edge 中是否正常工作。  
1.  如果你面临任何问题，你可以使用 DevTools 在 Microsoft Edge 中调试你的扩展 [，或者与我们联系][mailtoExtensionMicrosoft]。  
1.  按照 [发布指南][ExtensionsPublishPublishExtension] ，在 Microsoft Edge 加载项存储上发布扩展。  
    
    > [!NOTE]
    > 如果扩展使用 API 与本机应用交换消息 `chrome.runtime.connectNative` ，请确保在 `allowed_origins` `extension://[Microsoft-Catalog-extensionID]` 本机消息主机清单文件中设置为。  这使应用能够标识扩展。  
    
## 后续步骤  

扩展程序包准备好发布到 Microsoft Edge 加载项存储后， [创建一个开发者帐户][ExtensionsPublishCreateDevAccount] 并 [发布您的扩展][ExtensionsPublishPublishExtension]。  

<!-- links -->  

[ExtensionApiSupport]: ./api-support.md "API 支持 |Microsoft 文档"  
[ExtensionsGettingStartedExtensionSideloading]: ../getting-started/extension-sideloading.md "旁加载您的分机 |Microsoft 文档"  
[ExtensionsPublishCreateDevAccount]: ../publish/create-dev-account.md "开发人员注册 |Microsoft 文档"  
[ExtensionsPublishPublishExtension]: ../publish/publish-extension.md "发布您的分机 |Microsoft 文档"  

[ChromeDeveloperWebStorePayments]: https://developer.chrome.com/webstore/one_time_payments "一次性付款 |Chrome 开发人员"  

[mailtoExtensionMicrosoft]: mailto:ext_dev_support@microsoft.com "ext_dev_support@microsoft.com"  
