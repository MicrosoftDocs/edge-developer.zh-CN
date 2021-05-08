---
description: 了解如何将扩展从清单 V2 更新到 V3
title: 准备将扩展从清单 V2 更新到 V3
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/13/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium， 扩展开发， 边缘扩展， 浏览器扩展， 加载项， 开发人员， 清单 v3， 迁移到清单 v3
ms.openlocfilehash: 262a5cab54dd23f596791c93ec1238619e247333
ms.sourcegitcommit: 1ad087b00df16fd7718a5d95226de57e29b335e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/14/2020
ms.locfileid: "11117825"
---
# 准备将扩展从清单 v2 更新到 v3 

本文档列出了作为清单 v3 的一部分实现的重要更改，清单 v3 是下一版本的 Chromium 扩展平台。 我们将在实现过程中更新本文档。 有关将扩展迁移到清单 v3 的详细指南，请导航到"迁移到清单[V3"。][Google_Migrate_to_MV3] 

## 远程托管的代码  

现在，扩展可以远程托管其代码的某些部分，而不是在验证过程中作为扩展包的一部分包含。 虽然这样可以在不将扩展重新提交到存储区的情况下灵活更改代码，但可以在安装后利用代码。 为了确保[Microsoft Edge][EdgeAddons]加载项列表验证的扩展，我们禁止扩展使用远程托管的代码。 此更改使扩展更安全。 开发人员将需要打包并提交扩展使用的所有代码进行验证。 或者，开发人员可以在沙盒 () eval[函数。][sandboxingEval] 

## 运行时主机权限  

在安装时，扩展可能会请求访问所有网站和内容所需的权限。 这些权限允许扩展在最小干预下运行，并给用户隐私和安全性带来风险。 为了提高透明度，我们为用户提供了一些控件，以允许或限制在运行时访问网站。 

## 内容脚本中的跨源请求  

现在，内容脚本可以请求访问任何源，包括网站不允许的来源。 此行为破坏跨源原则。 今后，我们将要求内容脚本具有与注入到的页面相同的权限，关闭潜在的安全隐患。 若要执行跨源请求，你需要使用后台脚本将响应中继回内容脚本。 这些更改在标志后面可用。 有关详细信息，请导航到此 [文档][CORS]。 

## Web 请求 API  

我们将 Web 请求 [API][WebRequestAPI] 替换为 [声明性 Net 请求 API，][DeclarativeNetRequestAPI]但将继续保留 Web 请求 API 的观察功能。 除了扩展需要 Web 请求 API 观察功能的一些特定情况之外，我们建议仅使用 DNR API。 我们认为此更改将对使用功能丰富的声明功能的扩展产生积极的影响。 随着更多扩展过渡到 DNR API，此更改将改进用户隐私，这有助于增强使用扩展的信任。
对于通过企业策略管理的扩展，企业可以继续使用 Web 请求 API 的阻止行为。 有关扩展策略详细信息，请导航到"Microsoft Edge [– 策略"。][MicrosoftEdgePolicies] 

## 后台服务工作者  
 
服务工作人员可在 Canary 中进行测试。 若要将扩展从后台页面迁移到服务工作者，请参阅从后台页面 [迁移到服务工作者][ServiceWorkers]。 我们正在评估&调查此更改对开发人员和用户的影响。 将来，我们将向此文档添加有关此更改的其他详细信息。 

## 这些更改将在何时在 Microsoft Edge？

我们的 Stable 和 Beta 渠道中提供了当前声明性 Net 请求 API 实现。 开发人员可以测试这些更改并提供反馈。 我们将参与开发工作并调查进一步的更改。 

| 频道名称 | 说明 |
|:--- |:--- |  
| Microsoft Edge 84 Stable | DNR API 可用于测试 |  
| Microsoft Edge 85 Beta | 提供标头修改支持| 

当对应用商店Chromium，我们将共享日程表，以便开发人员可以更新其代码，并重新向应用商店发布扩展。 

我们将继续在博客上发布更新。 可以通过 [TechCommunity][TechCommunity]提供有关这些更改的反馈。

<!-- links -->  

[EdgeAddons]: https://microsoftedge.microsoft.com/addons/ "Microsoft Edge加载项"  
[MicrosoftBlog]: https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/  
[MicrosoftEdgePolicies]: https://docs.microsoft.com/deployedge/microsoft-edge-policies#extensions 

[TechCommunity]: https://techcommunity.microsoft.com/t5/articles/manifest-v3-changes-are-now-available-in-microsoft-edge/m-p/1780254 "技术Community"  


[Google_Migrate_to_MV3]: https://developer.chrome.com/extensions/migrating_to_manifest_v3   
[SandboxingEval]: https://developer.chrome.com/apps/sandboxingEval "在 Chrome 扩展中使用 eval。安全。"
[CORS]: https://www.chromium.org/Home/chromium-security/extension-content-script-fetches "对扩展内容脚本中的跨源请求的更改"
[WebRequestAPI]: https://developer.chrome.com/extensions/webRequest "Web 请求 API"  
[DeclarativeNetRequestAPI]: https://developer.chrome.com/extensions/declarativeNetRequest/ "声明性 Net 请求 API"
[ServiceWorkers]:  https://developers.chrome.com/extensions/migrating_to_service_workers


