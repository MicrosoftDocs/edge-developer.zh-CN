---
description: 了解如何将扩展从清单 V2 更新到 V3
title: 准备将你的扩展从清单 V2 更新到 V3
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/13/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium，扩展开发，边缘扩展，浏览器扩展，addons，开发人员，清单 v3，迁移到清单 v3
ms.openlocfilehash: 262a5cab54dd23f596791c93ec1238619e247333
ms.sourcegitcommit: 1ad087b00df16fd7718a5d95226de57e29b335e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/14/2020
ms.locfileid: "11117825"
---
# 准备将你的扩展从清单 v2 更新到 v3 

本文档列出了作为清单 v3 的一部分实现的重要更改，这是 Chromium 扩展平台的下一个版本。 我们将在实施过程中更新此文档。 有关将扩展迁移到清单 v3 的详细指南，请导航到 [清单 V3 迁移][Google_Migrate_to_MV3]。 

## 远程托管代码  

如今，扩展可以远程托管其代码的一部分，并且在验证过程中不将其包含在扩展程序包中。 虽然这提供了在不重新提交对应用商店的扩展的情况下更改代码的灵活性，但在安装后可以利用该代码。 为了确保 [Microsoft Edge 加载项][EdgeAddons] 列出已验证的扩展，我们禁止扩展使用远程托管的代码。 此更改使扩展更安全。 开发人员将需要打包和提交扩展所使用的所有代码以进行验证。 或者，开发人员可以在 [沙盒环境][sandboxingEval]中使用 eval ( # A1 函数。 

## 运行时主机权限  

在安装时，扩展可能会请求访问所有网站和内容的总权限。 这些权限允许扩展以最小的干预进行操作，并为用户隐私和安全带来风险。 为提高透明度，我们为用户提供了在运行时允许或限制访问网站的控件。 

## 内容脚本中的跨源请求  

"今日内容脚本" 可以请求对任何来源（包括网站不允许的来源）的访问权限。 此行为中断了交叉起源原则。 接下来，我们将要求内容脚本拥有与它们所注入的页面相同的权限，从而关闭潜在的安全 loophole。 若要执行跨源请求，你需要使用后台脚本将回复中继回内容脚本。 这些更改可在标志之后使用。 有关详细信息，请导航到 "此 [文档][CORS]"。 

## Web 请求 API  

我们正在将 [Web 请求 api][WebRequestAPI] 替换为 [声明性 Net Request api][DeclarativeNetRequestAPI]，但将继续保持 web 请求 api 的见习功能。 除了在某些特定情况下，扩展需要 Web 请求 API 的见习功能，我们建议仅使用 DNR Api。 我们认为，此更改将对使用功能丰富的声明性功能的扩展产生积极影响。 随着更多扩展转换为 DNR Api，此更改将改进用户隐私，这有助于增强对使用扩展的信任。
企业可以继续对通过企业策略管理的扩展使用 Web 请求 API 的阻止行为。 有关扩展策略的详细信息，请导航到 [Microsoft Edge-"策略][MicrosoftEdgePolicies]"。 

## 后台服务工作人员  
 
服务工作者可在未带里的测试中进行测试。 若要将扩展从背景页迁移到服务工作人员，请参阅 [从背景页迁移到服务工作人员][ServiceWorkers]。 我们正在评估 & 调查此变更对开发人员和用户带来的影响。 我们将在以后对此文档的更改添加其他详细信息。 

## 这些更改将在 Microsoft Edge 中提供什么情况？

当前的声明性 net request API 实现可在我们的稳定和 Beta 通道中使用。 开发人员可以测试这些更改，并提供反馈。 我们将参与开发工作，并调查进一步的更改。 

| 频道名称 | 描述 |
|:--- |:--- |  
| Microsoft Edge 84 稳定 | DNR API 可用于测试 |  
| Microsoft Edge 85 Beta | 标题修改支持可用| 

对 Chromium 进行更改后，我们将共享时间线，以便开发人员可以更新其代码并将扩展重新发布到应用商店。 

我们将继续发布博客上的更新。 你可以通过 [TechCommunity][TechCommunity]提供有关这些更改的反馈。

<!-- links -->  

[EdgeAddons]: https://microsoftedge.microsoft.com/addons/ "Microsoft Edge 加载项"  
[MicrosoftBlog]: https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/  
[MicrosoftEdgePolicies]: https://docs.microsoft.com/deployedge/microsoft-edge-policies#extensions 

[TechCommunity]: https://techcommunity.microsoft.com/t5/articles/manifest-v3-changes-are-now-available-in-microsoft-edge/m-p/1780254 "技术社区"  


[Google_Migrate_to_MV3]: https://developer.chrome.com/extensions/migrating_to_manifest_v3   
[SandboxingEval]: https://developer.chrome.com/apps/sandboxingEval "在 Chrome 扩展中使用 eval。放心."
[CORS]: https://www.chromium.org/Home/chromium-security/extension-content-script-fetches "扩展内容脚本中的跨原始请求的更改"
[WebRequestAPI]: https://developer.chrome.com/extensions/webRequest "Web 请求 API"  
[DeclarativeNetRequestAPI]: https://developer.chrome.com/extensions/declarativeNetRequest/ "声明性 Net 请求 API"
[ServiceWorkers]:  https://developers.chrome.com/extensions/migrating_to_service_workers


