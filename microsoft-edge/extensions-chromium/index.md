---
description: 构建和发布 Microsoft Edge (Chromium) 扩展的概述。
title: Microsoft Edge (Chromium) 扩展概述
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/10/2021
ms.topic: conceptual
ms.prod: microsoft-edge
keywords: edge， 扩展开发， 浏览器扩展， 加载项， 合作伙伴中心， 开发人员， chromium 扩展
ms.openlocfilehash: 3ed0871883acfb7c3cf08c2da9f47d18ae3465f0
ms.sourcegitcommit: fe7301d0f62493e42e6a1a81cdbda3457f0343b8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/13/2021
ms.locfileid: "11327524"
---
# Microsoft Edge (Chromium) 扩展概述  

扩展是你\（开发人员\）使用它来添加或修改 Microsoft Edge \(Chromium\) 功能的小程序。  扩展旨在改善用户的日常浏览体验。  它提供了对目标受众很重要的功能。  

如果有基于以下任一条件的想法或产品，则可以创建扩展。  

*   特定的 web 浏览器。  
*   对特定网页功能的改进。  
    
配套体验的示例包括广告拦截器和密码管理器。  

扩展的结构类似于常规 Web 应用。  它至少应该包括以下功能。

*   包含基本平台信息的应用程序清单 JSON 文件。  
*   定义功能的 JavaScript 文件。  
*   定义用户界面的 HTML 和 CSS 文件。  

若要直接使用部分浏览器（如窗口或选项卡），必须发送 API 请求，并通常按名称引用浏览器。  

:::image type="complex" source="./media/example-extension-screenshot.png" alt-text="Microsoft Edge (Chromium) 扩展" lightbox="./media/example-extension-screenshot.png":::
  Microsoft Edge \(Chromium\) 扩展  
:::image-end:::  

## 基本指南  

为一些最受欢迎的浏览器包括 Safari、Firefox、Chrome、Opera、Cookie 和 Microsoft Edge 构建扩展。  浏览器组织托管的网站是开始扩展开发教程和文档研究很好的位置。  下表不确定的，可以作为起点。  

| Web 浏览器 | 基于 Chromium？ | 扩展开发网页 |  
|:--- |:--- |:--- |  
| Safari | 否 | [developer.apple.com/documentation/safariservices/safari_app_extensions][AppleDeveloperSafariservicesAppExtensions] |  
| Firefox | 否 | [developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions][MDNWebextensions] |  
| 镶边 | 是 | [developer.chrome.com/extensions][ChromeDeveloperExtensions] |  
| Opera | 是 | [dev.opera.com/extensions][OperaDevExtensions] |  
| 勇敢 | 是 | 使用 [Chrome Web Store][GoogleChromeWebstoreCategoryExtensions] |  
| 新 Microsoft Edge | 是 | [developer.microsoft.com/microsoft-edge/extensions][MicrosoftDeveloperEdgeExtensions] |  

> [!IMPORTANT]
> 许多网站教程使用的浏览器特定的 API 可能与为其开发的浏览器不匹配。  在大多数情况下，Chromium 扩展在不同 Chromium 浏览器中工作，且 API 按预期工作。  只有一些不太常见的 API 可能会严格特定于浏览器。  有关教程的链接，请导航至“[另请参见](#see-also)”。  

## 为什么使用 Chromium？  

如果目标是在每个浏览器扩展应用商店中发布扩展，则必须为每个版本对其进行修改，以便在不同浏览器环境中运行。  例如，[Safari 扩展][AppleDeveloperSafariservicesAppExtensions]可以同时使用 web 和本机代码与对应的本机应用通信。  上表中的最后四个浏览器使用相同的代码包，并将维护并行版本的要求降到最低。  这些浏览器基于 [Chromium 开源项目][|::ref1::|Home]。  

创建 Chromium 扩展以编写最少的代码。  它还以扩展应用商店的最大数量以及最终以找到和获取扩展的最大用户数为目标。  

以下内容主要侧重于 Chromium 扩展。  

## 浏览器兼容性和扩展测试  

有时，Chromium 浏览器之间不存在 API 奇偶校验。  例如，标识和付款 API 存在差异。  为了确保扩展满足客户的期望，请通过以下官方浏览器文档查看 API 状态。  

*   [Chrome API][ChromeDeveloperExtensionsApiIndex]  
*   [Opera 支持的扩展 API][OperaDevExtensionsApis]  
*   [将 Chrome 扩展移植到 Microsoft Edge (Chromium)][ExtensionsChromiumDeveloperGuidePortChrome]  
    
所需 API 定义了为解决各浏览器之间差异而必须进行的更改。  这可能意味着必须为每个应用商店创建略有差异的不同代码包。  

若要在将扩展提交到浏览器应用商店之前在不同环境中进行测试，请在开发扩展时将其旁加载到浏览器中。  

## 将扩展发布到浏览器应用商店  

您可以在以下浏览器存储中提交和查找浏览器扩展。  

*   [Firefox 浏览器加载项][MozillaAddonsFirefoxExtensions]  
*   [Chrome Web Store][GoogleChromeWebstoreCategoryExtensions]  
*   [Opera加载项][OperaAddonsExtensions]  
*   [Microsoft Edge 加载项][MicrosoftEdgeAddonsCategoryExtensions]  

某些商店允许你从其他浏览器下载列出的扩展。  但是，浏览器商店无法保证跨浏览器访问。  为了确保你的用户可在不同的浏览器中找到扩展，应该在每个浏览器扩展商店上维护一个列表。  

用户可能需要在不同的浏览器中安装扩展。 在这种情况下，可以将现有的 Chromium 扩展从一个浏览器迁移到另一个浏览器。  

### 将现有扩展迁移到 Microsoft Edge  

如果已经为另一个 Chrome 浏览器开发了扩展，则可以将其提交到 Microsoft Edge 加载项商店。 不需要重写扩展，并且必须验证它在 MicrosoftEdge 中是否工作。  将现有的 Chromium 扩展迁移到其他 Chromium 浏览器时，请确保相同的 API 或替代方案可用于该目标浏览器。  

有关将 Chrome 扩展移植到 Microsoft Edge 的更多信息，请导航到[将 Chrome 扩展移植到 Microsoft Edge (Chrome)][ExtensionsChromiumDeveloperGuidePortChrome]。 将扩展移植到目标浏览器后，下一步是发布它。  

### 发布到 Microsoft Edge 外接程序网站  

若要开始将扩展发布到 Microsoft Edge，必须[使用 MSA 电子邮件帐户注册开发人员帐户][MicrosoftDeveloperRegistration]，才能将扩展列表提交到商店。  MSA 电子邮件帐户包括 `@outlook.com`、`@live.com` 等。  选择要注册的电子邮件地址时，请考虑是否必须与组织中其他人转移或共享扩展的所有权。  注册完成后，你可以向应用商店创建新的扩展提交。  

若要向应用商店提交扩展，请确保提供以下项目。  

*   包含代码文件的存档 \(`.zip`\) 文件。  
*   所有必需的视觉资源，包括徽标和小型促销磁贴。  
*   可选促销媒体，如屏幕截图、促销贴片和视频 URL。  
*   描述扩展名的信息，如名称、简短描述和隐私策略链接。  

> [!NOTE]
> 不同的应用商店可能具有不同的提交要求。  上面的列表总结了发布 [Microsoft Edge][ExtensionsChromiumPublish] 扩展的要求。  

成功提交扩展后，扩展将经历审核过程，它将通过或不通过认证过程。  向所有者通知结果，并按需要提供下一步步骤。  如果向应用商店提交扩展更新，则会启动新的审阅过程。  

## 另请参阅  

*   [移植 Google Chrome 扩展][ExtensionworkshopPorting]  
*   [构建 Safari 应用扩展][AppleDeveloperSafariservicesAppExtensionsBuilding]  
*   [第一个扩展 (Firefox)][MDNWebextensionsYourFirst]  
*   [入门教程 (Opera)][ChromeDeveloperExtensionsGetstarted]  
*   [入门 (Opera)][OperaDevExtensionsGettingStarted]  
*   [Microsoft Edge (Chromium) 扩展入门][ExtensionsChromiumGettingStartedIndex]  

<!-- links -->  

[ExtensionsChromiumDeveloperGuidePortChrome]: ./developer-guide/port-chrome-extension.md "将 Chrome 扩展移植到 Microsoft Edge (Chromium) |Microsoft Docs"  
[ExtensionsChromiumGettingStartedIndex]: ./getting-started/index.md "Microsoft Edge (Chromium) 扩展 | Microsoft Docs 入门"  
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
[OperaDevExtensionsGettingStarted]: https://dev.opera.com/extensions/getting-started "入门 | Dev. Opera"  
