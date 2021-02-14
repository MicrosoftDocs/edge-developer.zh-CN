---
description: 构建和发布 Microsoft Edge (Chromium) 概述。
title: Microsoft Edge (Chromium) 扩展概述
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/10/2021
ms.topic: conceptual
ms.prod: microsoft-edge
keywords: edge， 扩展开发， 浏览器扩展， 加载项， 合作伙伴中心， 开发人员， chromium 扩展
ms.openlocfilehash: 3ed0871883acfb7c3cf08c2da9f47d18ae3465f0
ms.sourcegitcommit: fe7301d0f62493e42e6a1a81cdbda3457f0343b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/13/2021
ms.locfileid: "11327524"
---
# Microsoft Edge (Chromium) 扩展概述  

扩展是一个小程序， (开发人员\) 添加或修改 Microsoft Edge \ (Chromium\) 。  扩展旨在改善用户日常浏览体验。  它提供对目标受众非常重要的小功能。  

如果你有基于以下任一条件的想法或产品，可以创建扩展。  

*   特定的 Web 浏览器。  
*   对特定网页的功能进行了改进。  
    
配套体验的示例包括广告阻止者和密码管理器。  

扩展的结构类似于常规 Web 应用。  至少应包含以下功能。

*   包含基本平台信息的应用清单 JSON 文件。  
*   定义功能的 JavaScript 文件。  
*   定义用户界面的 HTML 和 CSS 文件。  

若要直接使用部分浏览器（如窗口或选项卡），必须发送 API 请求，并通常按名称引用浏览器。  

:::image type="complex" source="./media/example-extension-screenshot.png" alt-text="Microsoft Edge (Chromium) 扩展" lightbox="./media/example-extension-screenshot.png":::
  Microsoft Edge \ (Chromium\) 扩展  
:::image-end:::  

## 基本指南  

为 Safari、Firefox、Chrome、Opera、Cookie 和 Microsoft Edge 构建扩展的一些最受欢迎的浏览器。  浏览器组织托管的网站是开始扩展开发教程和文档研究很好的位置。  下表并不明确，可以用作起始点。  

| Web 浏览器 | 基于 Chromium？ | 扩展开发网页 |  
|:--- |:--- |:--- |  
| Safari | 否 | [developer.apple.com/documentation/safariservices/safari_app_extensions][AppleDeveloperSafariservicesAppExtensions] |  
| Firefox | 否 | [developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions][MDNWebextensions] |  
| 镶边 | 是 | [developer.chrome.com/extensions][ChromeDeveloperExtensions] |  
| Opera | 是 | [dev.opera.com/extensions][OperaDevExtensions] |  
| 勇敢 | 是 | 使用 [Chrome Web Store][GoogleChromeWebstoreCategoryExtensions] |  
| 新 Microsoft Edge | 是 | [developer.microsoft.com/microsoft-edge/extensions][MicrosoftDeveloperEdgeExtensions] |  

> [!IMPORTANT]
> 许多网站的教程使用与所开发浏览器不匹配的特定于浏览器的 API。  在大多数情况下，Chromium 扩展在不同 Chromium 浏览器中工作，且 API 按预期工作。  只有一些不太常见的 API 可能会严格特定于浏览器。  有关指向教程的链接，请导航到"[另请参阅"。](#see-also)  

## 为什么使用 Chromium？  

如果你的目标是在每个浏览器的扩展存储中发布扩展，则必须针对每个版本进行修改，以定位并在每个不同的浏览器环境中运行。  例如 [，Safari 扩展][AppleDeveloperSafariservicesAppExtensions] 可能同时使用 Web 和本机代码与对应的本机应用程序进行通信。  上表中最后四个浏览器使用相同的代码包，并最大限度地减少了维护并行版本的要求。  这些浏览器基于 [Chromium 开源项目][|::ref1::|Home]。  

创建 Chromium 扩展以写入最少的代码。  它还面向最大扩展存储数，并最终面向查找和获取扩展的最大用户数。  

以下内容主要侧重于 Chromium 扩展。  

## 浏览器兼容性和扩展测试  

有时，Chromium 浏览器之间不存在 API 奇偶校验。  例如，标识和付款 API 存在差异。  若要确保您的扩展符合客户期望，请通过以下官方浏览器文档查看 API 状态。  

*   [Chrome API][ChromeDeveloperExtensionsApiIndex]  
*   [操作中支持的扩展 API][OperaDevExtensionsApis]  
*   [将 Chrome 扩展移植到 Microsoft Edge (Chromium) ][ExtensionsChromiumDeveloperGuidePortChrome]  
    
您需要的 API 定义必须所做的更改以解决每个浏览器之间的差异。  这可能意味着你必须为每个存储创建略有不同的代码包，但略有不同。  

若要在将扩展提交到浏览器存储之前在不同环境中测试扩展，在开发时将其旁加载到浏览器中。  

## 将扩展发布到浏览器存储  

您可以在以下浏览器存储中提交和查找浏览器扩展。  

*   [Firefox 浏览器加载项][MozillaAddonsFirefoxExtensions]  
*   [Chrome Web Store][GoogleChromeWebstoreCategoryExtensions]  
*   [Opera加载项][OperaAddonsExtensions]  
*   [Microsoft Edge 加载项][MicrosoftEdgeAddonsCategoryExtensions]  

某些商店允许你从其他浏览器下载列出的扩展。  但是，浏览器存储无法保证跨浏览器访问。  若要确保用户在不同的浏览器中找到扩展，您应该在每个浏览器扩展存储上维护一个列表。  

用户可能需要在不同的浏览器中安装扩展。 在此方案中，你可以将现有 Chromium 扩展从一个浏览器迁移到另一个浏览器。  

### 将现有扩展迁移到 Microsoft Edge  

如果已针对另一个 Chromium 浏览器开发扩展，可以将其提交到 Microsoft Edge 加载项存储。 无需重写扩展，并且必须验证它在 Microsoft Edge 中是否正常工作。  将现有 Chromium 扩展迁移到其他 Chromium 浏览器时，请确保相同的 API 或替代项可用于目标浏览器。  

有关将 Chrome 扩展移植到 Microsoft Edge 的信息，请导航到将 Chrome 扩展移植到 Microsoft Edge ([Chromium) 。 ][ExtensionsChromiumDeveloperGuidePortChrome] 将扩展移植到目标浏览器后，下一步是发布它。  

### 发布到 Microsoft Edge 加载项网站  

若要开始将扩展发布到 Microsoft Edge，必须使用[][MicrosoftDeveloperRegistration]MSA 电子邮件帐户注册开发人员帐户，以将扩展列表提交到应用商店。  MSA 电子邮件帐户包括 `@outlook.com` ， `@live.com` 等等。  选择要注册的电子邮件地址时，请考虑是否必须与组织中其他人转移或共享扩展的所有权。  注册完成后，你可以向应用商店创建新的扩展提交。  

若要将扩展提交到应用商店，请确保提供以下项目。  

*   包含代码文件的存档 `.zip` \ (\) 文件。  
*   所有必需的视觉资源，包括徽标和小型促销磁贴。  
*   可选促销媒体，如屏幕截图、促销磁贴和视频 URL。  
*   描述扩展的信息，如名称、简短说明和隐私策略链接。  

> [!NOTE]
> 不同的应用商店可能具有不同的提交要求。  上述列表总结了 [发布][ExtensionsChromiumPublish] Microsoft Edge 扩展的要求。  

成功提交扩展后，扩展将经历审阅过程，并且通过或未能通过认证过程。  向所有者通知结果，并按需要提供下一步步骤。  如果向应用商店提交扩展更新，将启动新的审阅过程。  

## 另请参阅  

*   [移植 Google Chrome 扩展][ExtensionworkshopPorting]  
*   [生成 Safari 应用扩展][AppleDeveloperSafariservicesAppExtensionsBuilding]  
*   [第一个扩展 （Firefox）][MDNWebextensionsYourFirst]  
*   [Chrome (入门) ][ChromeDeveloperExtensionsGetstarted]  
*   [操作 (入门) ][OperaDevExtensionsGettingStarted]  
*   [Microsoft Edge (Chromium) 扩展入门][ExtensionsChromiumGettingStartedIndex]  

<!-- links -->  

[ExtensionsChromiumDeveloperGuidePortChrome]: ./developer-guide/port-chrome-extension.md "将 Chrome 扩展移植到 Microsoft Edge (Chromium) |Microsoft Docs"  
[ExtensionsChromiumGettingStartedIndex]: ./getting-started/index.md "Microsoft Edge (Chromium) Extensions |Microsoft Docs"  
[ExtensionsChromiumPublish]: ./publish/publish-extension.md "发布扩展|Microsoft Docs"  

[MicrosoftDeveloperEdgeExtensions]: https://developer.microsoft.com/microsoft-edge/extensions "开发 Microsoft Edge |Microsoft 开发人员"  
[MicrosoftDeveloperRegistration]: https://developer.microsoft.com/registration "合作伙伴中心|Microsoft 开发人员"  

[MicrosoftEdgeAddonsCategoryExtensions]: https://microsoftedge.microsoft.com/addons/category/Edge-Extensions "Microsoft Edge |Microsoft Edge"  

[AppleDeveloperSafariservicesAppExtensions]: https://developer.apple.com/documentation/safariservices/safari_app_extensions "Safari 应用扩展|Apple 开发人员"  
[AppleDeveloperSafariservicesAppExtensionsBuilding]: https://developer.apple.com/documentation/safariservices/safari_app_extensions/building_a_safari_app_extension "生成 Safari 应用扩展|Apple 开发人员"  

[ChromeDeveloperExtensions]: https://developer.chrome.com/extensions "什么是扩展？|Chrome 开发人员"  
[ChromeDeveloperExtensionsApiIndex]: https://developer.chrome.com/extensions/api_index "Chrome API |Chrome 开发人员"  
[ChromeDeveloperExtensionsGetstarted]: https://developer.chrome.com/extensions/getstarted "入门教程|Chrome 开发人员"  

[ChromiumHome]: https://www.chromium.org/Home "Chromium"  

[ExtensionworkshopPorting]: https://extensionworkshop.com/documentation/develop/porting-a-google-chrome-extension "移植 Google Chrome 扩展|扩展研讨会"  

[GoogleChromeWebstoreCategoryExtensions]: https://chrome.google.com/webstore/category/extensions "扩展|Chrome Web Store"  

[MDNWebextensions]: https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions "浏览器扩展|MDN"  
[MDNWebextensionsYourFirst]: https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/Your_first_WebExtension "你的第一个|MDN"  

[MozillaAddonsFirefoxExtensions]: https://addons.mozilla.org/firefox/extensions "扩展|Firefox 加载项"  

[OperaAddonsExtensions]: https://addons.opera.com/extensions "扩展|Opera Addons"  

[OperaDevExtensions]: https://dev.opera.com/extensions "扩展文档|Dev. Opera"  
[OperaDevExtensionsApis]: https://dev.opera.com/extensions/apis "操作方法支持扩展|Dev. Opera"  
[OperaDevExtensionsGettingStarted]: https://dev.opera.com/extensions/getting-started "入门|Dev. Opera"  
