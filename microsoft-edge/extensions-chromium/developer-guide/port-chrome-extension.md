---
description: 将 Chrome 扩展移植到 Microsoft Edge 的过程。
title: 指向 Microsoft （Chromium） Edge 的端口 Chrome 扩展
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/26/2020
ms.topic: article
ms.prod: microsoft-edge-chromium
keywords: edge-chromium、扩展开发、浏览器扩展、addons、合作伙伴中心、开发人员
ms.openlocfilehash: 794e8806a95ce0a70069c65c306c30131b01e24d
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563379"
---
# 将端口 Chrome 扩展到 Microsoft \ （Chromium \） Edge  

将 Chrome 扩展移植到 Microsoft Edge 的过程非常简单。  为 Chromium 编写的扩展在大多数情况下，只需在 Microsoft Edge 中运行即可获得最少的更改。  Chrome 支持的扩展 Api 和清单键是与 Microsoft Edge 兼容的代码。  但是，Microsoft Edge 不支持以下扩展 Api：  

*   `chrome.gcm`  
*   `chrome.identity.getAccounts`  
*   `chrome.identity.getAuthToken`  
*   `chrome.instanceID`  

> [!Note]
> 用户必须使用 MSA 或 AAD 帐户登录到 Microsoft Edge，才能使用该 `chrome.identity.getProfileUserInfo` API。  如果用户使用**本地广告**登录到 Microsoft EDGE，API 将返回 `null` "电子邮件" 和 "ID" 值。  

> [!IMPORTANT]
> **付款**： Microsoft Edge 不直接支持使用[Chrome Web Store 付款][ChromeDeveloperWebStorePayments]的扩展，因为需要使用 `identity.getAuthtoken` 请求获取登录用户的令牌才能发送基于 REST 的授权 API 请求。  Microsoft Edge 不支持该 `getAuthtoken` 请求，因此此流程不起作用。  

若要移植 Chrome 扩展，请按照下列步骤操作：  

1.  查看扩展中使用的 Chrome 扩展 Api。  如果你使用的是 Microsoft Edge 不支持的功能或 Api，你可能无法移植你的扩展。  
    
    > [!NOTE]
    > `getAuthToken`API 不能与 Microsoft Edge 配合使用，但你可以使用 `launchWebAuthFlow` 获取 OAuth2 令牌来对用户进行身份验证。  
    
1.  如果您 `Chrome` 在分机的名称或说明中使用，请重新标记的分机号 `Microsoft Edge` 。  您必须通过认证流程。  
    
1.  测试您的扩展，以检查它在 Microsoft Edge 中是否正常工作。  执行此操作的第一步是确保已打开扩展开发人员功能。  这使你可以在 Microsoft Edge 中加载扩展文件，以便你可以在开发时测试扩展。  
    
1.  如果你有任何问题，请使用 DevTools 在 Microsoft Edge 中调试你的扩展，[或与我们联系][mailtoExtensionPartnerOpsMicrosoft]。  
    
1.  现在，你的扩展已是 "精美"，可随时打包。  如果你希望准备提交到 Microsoft Edge Addons 目录 \ （Microsoft Edge Addons \），则无需打包你的扩展。  此外，请遵循我们的[发布指南][ExtensionsPublishExtension]以在 Microsoft Edge Addons 上发布您的扩展。  
    
    > [!NOTE]
    > 如果你的扩展使用 API 与本机应用程序交换消息 `chrome.runtime.connectNative` ，请确保你 `allowedorigins` `extension://[Microsoft-Catalog-extensionID]` 在本机消息主机清单文件中设置为 ""。  这使应用能够标识扩展。  

<!-- image links -->  

<!-- links -->  

[ExtensionsPublishExtension]: ../publish/publish-extension.md "发布扩展"  

[mailtoExtensionPartnerOpsMicrosoft]: mailto:extensionpartnerops@microsoft.com "ExtensionPartnerOps@microsoft.com"  

[ChromeDeveloperWebStorePayments]: https://developer.chrome.com/webstore/one_time_payments "一次性付款-Google Chrome"  
