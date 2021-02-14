---
description: Microsoft Edge (Chromium) 扩展以及构建和发布浏览器扩展的概述。
title: Microsoft Edge (Chromium) 扩展
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/27/2020
ms.topic: conceptual
ms.prod: microsoft-edge
keywords: edge， 扩展开发， 浏览器扩展， 加载项， 合作伙伴中心， 开发人员， chromium 扩展
ms.openlocfilehash: 04b9ffb7ec175bad4f980310819ea6d3551ef9f8
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11230941"
---
# Microsoft Edge (Chromium) 扩展概述 

扩展是一个小程序， (开发人员\) 可以使用它向 Microsoft Edge \ (Chromium\) 添加新功能或修改现有功能。  扩展旨在通过提供对目标访问群体十分重要的浏览器功能，改善用户日常浏览体验。  

如果你的想法或产品取决于特定 Web 浏览器的可用性或希望提供扩展现有网站的功能的浏览体验，则可以创建扩展。  配套体验的示例包括 adblockers 和密码管理器。  

扩展的结构类似于常规 Web 应用。  至少，它包含一个应用清单 JSON 文件，其中包含基本平台信息、一个要定义功能的 JavaScript 文件以及一个 HTML 和 CSS 文件，用于确定用户界面 \（required\） 的外观。  若要直接使用部分浏览器（如窗口或选项卡），必须发送 API 请求，并通常按名称引用浏览器。  

:::image type="complex" source="./media/example-extension-screenshot.png" alt-text="Microsoft Edge (Chromium) 扩展":::
  Microsoft Edge \ (Chromium\) 扩展  
:::image-end:::  

## 基本指南  

要构建的一些最受欢迎的浏览器包括 Safari、Firefox、Chrome、Opera、Cookie 和 Microsoft Edge。  浏览器组织托管的网站是开始扩展开发教程和文档研究很好的位置。  下表并不明确，请使用它作为有用的起始点。  

| Web 浏览器 | 基于 Chromium？ | 扩展开发主页 |  
|:--- |:--- |:--- |  
| Safari | 否 | [developer.apple.com/documentation/safariservices/safari_app_extensions][AppleDeveloperSafariservicesAppExtensions] |  
| Firefox | 否 | [developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions][MDNWebextensions] |  
| 镶边 | 是 | [developer.chrome.com/extensions][ChromeDeveloperExtensions] |  
| Opera | 是 | [dev.opera.com/extensions][OperaDevExtensions] |  
| 勇敢 | 是 | 使用 [Chrome Web Store][GoogleChromeWebstoreCategoryExtensions] |  
| 新 Microsoft Edge | 是 | [developer.microsoft.com/microsoft-edge/extensions][MicrosoftDeveloperEdgeExtensions] |  

> [!IMPORTANT]
> 许多网站教程使用的浏览器特定的 API 可能与开发中的浏览器不匹配。  在大多数情况下，Chromium 扩展在不同 Chromium 浏览器中工作，且 API 按预期工作。  只有一些不太常见的 API 可能会严格特定于浏览器。  有关教程的链接，请参阅 [另请参阅](#see-also)。  

## 为什么使用 Chromium？

如果你的目标是将扩展发布到尽可能多的浏览器扩展存储，必须为多个版本修改扩展，才能在每个不同的浏览器环境中定位并运行。  [Safari 扩展][AppleDeveloperSafariservicesAppExtensions]与其他扩展类型不同，可能利用 Web 和本机代码与对应的本机应用程序进行通信。  [Firefox 扩展][MDNWebextensions] 与其他扩展类型共享得更为常见，但也需要考虑一些 [差异][ExtensionworkshopPorting]。  但是，有一些好消息;上图中的最后四个浏览器能够使用相同的代码包，并尽可能减少更改和维护并行版本的要求。  这是因为浏览器基于 [Chromium 开源项目][|::ref1::|Home]。  

创建 Chromium 扩展可实现最小代码量，以将目标扩展存储数以及最终能够查找和获取扩展的用户数最大化。  

以下内容主要侧重于 Chromium 扩展。  

## 浏览器兼容性和扩展测试  

有时，Chromium 浏览器之间不存在 API 奇偶校验。  例如，标识和付款 API 存在差异。  为确保扩展符合客户期望，请通过官方浏览器文档查看 API 状态，如 [Chrome API][ChromeDeveloperExtensionsApiIndex]、[Opera中支持的 扩展 API][OperaDevExtensionsApis] 和 Microsoft 的 [端口 Chrome 扩展 （Chromium） Edge][ExtensionsChromiumDeveloperGuidePortChrome]。  

根据你需要的 API，这些差异可能意味着你必须创建略有不同的代码包，每个存储的代码差异很小。  

开发扩展时，您可以在浏览器中旁加载它，以在不同环境中测试它，然后再将扩展提交到浏览器存储。  

## 将扩展发布到浏览器存储  

您可以在以下浏览器存储中提交和查找浏览器扩展。  

*   [Firefox 浏览器加载项][MozillaAddonsFirefoxExtensions]  
*   [Chrome Web Store][GoogleChromeWebstoreCategoryExtensions]  
*   [Opera加载项][OperaAddonsExtensions]  
*   [Microsoft Edge 加载项][MicrosoftEdgeAddonsCategoryExtensions]  

某些商店允许你从其他浏览器下载列出的扩展。  从另一浏览器下载可能会预先节省 \（developer\） 工作，并且如果用户能够跨不同浏览器导航至现有应用商店列表，则无需再提交到其他商店。  但是，浏览器存储无法保证跨浏览器访问。  为了确保你的用户能够在不同的浏览器中找到扩展，你应该在每个浏览器扩展存储上维护一个列表。  

扩展可能具有经常使用多个浏览器的重叠访问群体，或者你可能会发现它应面向以前没有的受众。  为此，现有 Chromium 扩展可能从一个浏览器迁移到另一个浏览器。  

### 将现有扩展迁移到 Microsoft Edge  

如果已针对另一个 Chromium 浏览器开发扩展，并且想要提供扩展并确保它通过 Microsoft Edge 运行，则不需要重写扩展。  将现有 Chromium 扩展迁移到其他 Chromium 浏览器非常简单，只要你使用的 API 在不同的浏览器上可用，或者存在提供所需功能的其他 API。  

有关移植Chrome扩展的详细信息，请参阅 [将Chrome扩展移植到Microsoft(Chromium)Edge][ExtensionsChromiumDeveloperGuidePortChrome]。  将扩展移植到目标浏览器后，下一步是发布它。  

### 发布到 Microsoft Edge 加载项网站  

若要开始将扩展发布到 Microsoft Edge，必须在 [使用 MSA 电子邮件帐户 \（@outlook.com、@live.com 等）注册开发人员帐户][MicrosoftDeveloperRegistration] 才能在应用商店中提交扩展列表。  选择要注册的电子邮件地址时，请考虑是否必须与组织中其他人转移或共享扩展的所有权。  注册完成后，你可以向应用商店创建新的扩展提交。  

若要将扩展提交到应用商店，必须满足以下要求。  

*   包含代码文件的存档 \ (.zip\) 文件。  
*   所有必需的视觉资源，包括徽标和小型促销磁贴。  
*   可选促销媒体，如屏幕截图、较大的促销磁贴、URL 或你的扩展视频的任意组合。  
*   描述扩展的信息，例如名称、简短说明、长描述和隐私策略链接。  

> [!NOTE]
> 不同的应用商店可能具有不同的提交要求。  上面的列表总结了 [Microsoft Edge][ExtensionsChromiumPublish] 发布扩展的一些要求。  

完成提交过程后，你的扩展将经过审查，并且通过或未能通过认证过程。  向所有者通知结果，并按需要提供下一步步骤。  如果向应用商店提交更新的扩展，包括扩展一览详细信息的更新，将启动新的审阅过程。  

## 另请参阅  

*   [移植 Google Chrome 扩展][ExtensionworkshopPorting]  
*   [生成 Safari 应用扩展][AppleDeveloperSafariservicesAppExtensionsBuilding]  
*   [第一个扩展 （Firefox）][MDNWebextensionsYourFirst]  
*   [入门教程 （Opera）][ChromeDeveloperExtensionsGetstarted]  
*   [入门（Opera）][OperaDevExtensionsGettingStarted]  
*   [Microsoft Edge (Chromium) 扩展入门][ExtensionsChromiumGettingStartedIndex]  

<!-- image links -->  

<!-- links -->  

[ExtensionsChromiumDeveloperGuidePortChrome]: ./developer-guide/port-chrome-extension.md "将 Chrome 扩展移植到 Microsoft (Chromium) Edge |Microsoft Docs"  
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

[OperaDevExtensions]: https://dev.opera.com/extensions "扩展文档|Dev.Opera"  
[OperaDevExtensionsApis]: https://dev.opera.com/extensions/apis "操作方法支持扩展|Dev.Opera"  
[OperaDevExtensionsGettingStarted]: https://dev.opera.com/extensions/getting-started "入门|Dev.Opera"  
