---
description: 了解如何将扩展从清单 V2 更新到 V3
title: 准备将扩展从清单 V2 更新到 V3
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium， 扩展开发， 边缘扩展， 浏览器扩展， 加载项， 开发人员， 清单 v3， 迁移到清单 v3
ms.openlocfilehash: 5aa1aa7446a312d581bacc4fa19ba7362c6c2a3e
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564614"
---
# <a name="prepare-to-update-your-extensions-from-manifest-v2-to-v3"></a>准备将扩展从清单 v2 更新到 v3  

本文档列出了作为清单 v3 的一部分实现的重要更改，清单 v3 是下一版本的 Chromium 扩展平台。  应用Microsoft Edge团队将随着实现进度更新此文档。  有关将扩展迁移到清单 v3 的详细指南，请导航到"迁移到清单[V3"。][ChromeDeveloperDocsExtensionsMv3Mv3MigrationChecklist]  

## <a name="remotely-hosted-code"></a>远程托管的代码  

目前，扩展代码的某些部分是远程托管的，并且不会在验证过程中作为扩展包的一部分包含。  虽然这样可以在不将扩展重新提交到存储区的情况下灵活更改代码，但代码在安装后可能会受到攻击。  为了确保[Microsoft Edge加载项][MicrosoftMicrosoftedgeAddons]列出经过验证的扩展，Microsoft Edge团队禁止扩展使用远程托管的代码。  此更改使扩展更安全。  开发人员将需要打包并提交扩展使用的所有代码进行验证。  或者，您可以在沙盒 `eval()` 环境中使用 [函数][ChromeDeveloperDocsExtensionsMv2Sandboxingeval]。  

## <a name="run-time-host-permissions"></a>运行时主机权限  

在安装时，扩展可能会请求访问所有网站和内容所需的权限。  这些权限允许扩展在最小干预下运行，并给用户隐私和安全性带来风险。  为了提高透明度，Microsoft Edge扩展团队为用户提供了一些控件，以允许或限制在运行时访问网站。  

## <a name="cross-origin-requests-in-content-scripts"></a>内容脚本中的跨源请求  

现在，内容脚本请求访问任何源，包括网站不允许的源。  该行为会破坏跨来源原则。  今后，Microsoft Edge扩展团队需要内容脚本具有与注入脚本的网页相同的权限，从而关闭潜在的安全隐患。  若要执行跨源请求，你需要使用后台脚本将响应中继回内容脚本。  这些更改在标志后面可用。  有关详细信息，请导航到此 [文档][ChromiumHomeChromiumSecurityExtensionContentScriptFetches]。  

## <a name="web-request-api"></a>Web 请求 API  

扩展Microsoft Edge团队将 Web 请求[API][ChromeDeveloperDocsExtensionsReferenceWebrequest]替换为声明性 Net[请求 API，][ChromeDeveloperDocsExtensionsReferenceDeclarativenetrequest]但继续保留 Web 请求 API 的观察功能。  除了扩展需要 Web 请求 API 的观察功能的一些特定情况之外，Microsoft Edge 扩展团队建议仅使用 DNR API。  扩展Microsoft Edge团队认为此更改将对使用功能丰富的声明功能的扩展产生积极的影响。  随着更多扩展过渡到 DNR API，此更改将改进用户隐私，这有助于增强使用扩展的信任。  
对于通过企业策略管理的扩展，企业可能会继续使用 Web 请求 API 的阻止行为。  有关扩展策略详细信息，请导航到"Microsoft Edge [– 策略"。][DeployedgeMicrosoftEdgePoliciesExtensions]  

## <a name="background-service-workers"></a>后台服务工作者  
 
服务工作人员可在 Canary 中进行测试。  若要将扩展从后台页面迁移到服务工作者，请参阅从后台页面 [迁移到服务工作者][ChromeDeveloperDocsExtensionsMv3MigratingToServiceWorkers]。  开发人员Microsoft Edge团队正在评估并调查此更改对开发人员和用户的影响。  Microsoft Edge扩展团队将来会向此文档添加有关更改的其他详细信息。  

## <a name="when-are-these-changes-available-in-microsoft-edge"></a>这些更改何时在Microsoft Edge  

我们的 Stable 和 Beta 渠道中提供了当前声明性 Net 请求 API 实现。  测试更改并提供反馈。  扩展Microsoft Edge团队参与开发工作并调查进一步的更改。  

| 频道名称 | 详细信息 |  
|:--- |:--- |  
| Microsoft Edge 84 Stable | DNR API 可用于测试 |  
| Microsoft Edge 85 Beta | 提供标头修改支持|  

当对应用商店Chromium时，Microsoft Edge扩展团队将共享日程表，以便你可以更新代码并重新向应用商店发布扩展。  

Microsoft Edge扩展团队继续发布博客上的更新。  可以通过 Tech Community[提供有关更改的反馈][MicrosoftTechcommunityT5ArticlesManifestV3ChnagesAreNowAvailableInMicrosoftEdgeMP1780254]。

<!-- links -->  

[DeployedgeMicrosoftEdgePoliciesExtensions]: /deployedge/microsoft-edge-policies#extensions "扩展 - Microsoft Edge - 策略|Microsoft Docs"  

[MicrosoftMicrosoftedgeAddons]: https://microsoftedge.microsoft.com/addons "Microsoft Edge 加载项"  

[MicrosoftTechcommunityT5ArticlesManifestV3ChnagesAreNowAvailableInMicrosoftEdgeMP1780254]: https://techcommunity.microsoft.com/t5/articles/manifest-v3-changes-are-now-available-in-microsoft-edge/m-p/1780254 "清单 V3 更改现已在 Microsoft Edge |Microsoft 技术Community"  

[ChromeDeveloperDocsExtensionsMv2Sandboxingeval]: https://developer.chrome.com/docs/extensions/mv2/sandboxingEval "在 Chrome 扩展中使用 eval |Chrome 开发人员"  
[ChromeDeveloperDocsExtensionsMv3MigratingToServiceWorkers]:  https://developer.chrome.com/docs/extensions/mv3/migrating_to_service_workers "从后台页面迁移到服务工作者|Chrome 开发人员"  
[ChromeDeveloperDocsExtensionsMv3Mv3MigrationChecklist]: https://developer.chrome.com/docs/extensions/mv3/mv3-migration-checklist "清单 V3 迁移清单|Chrome 开发人员"    

[ChromeDeveloperDocsExtensionsReferenceDeclarativenetrequest]: https://developer.chrome.com/docs/extensions/reference/declarativeNetRequest "chrome.declarativeNetRequest |Chrome 开发人员"  
[ChromeDeveloperDocsExtensionsReferenceWebrequest]: https://developer.chrome.com/docs/extensions/reference/webRequest "chrome.webRequest |Chrome 开发人员"  

[ChromiumHomeChromiumSecurityExtensionContentScriptFetches]: https://www.chromium.org/Home/chromium-security/extension-content-script-fetches "对 Chrome 扩展内容脚本中跨源请求的更改|项目Chromium"  
