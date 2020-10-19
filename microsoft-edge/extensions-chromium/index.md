---
description: Microsoft Edge (Chromium) 扩展以及构建和发布浏览器扩展的概述。
title: Microsoft Edge (Chromium) 扩展
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/28/2020
ms.topic: conceptual
ms.prod: microsoft-edge
keywords: 边缘、扩展开发、浏览器扩展、addons、合作伙伴中心、开发人员、chromium 扩展
ms.openlocfilehash: 85858fc7e1159db3175c3a67c3cfd5f6dfbb448f
ms.sourcegitcommit: 845a0d53a86bee3678f421adee26b3372cefce57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/08/2020
ms.locfileid: "11104698"
---
# Microsoft Edge (Chromium) 扩展 

扩展是您 (开发人员的小程序 \ ) 可能会用来将新功能添加到 Microsoft Edge \ (Chromium \ ) 或修改现有功能。  扩展旨在通过提供对目标受众非常重要的小功能来改善用户的日常浏览体验。  

如果你的想法或产品依赖于特定的 web 浏览器的可用性，或者补充你希望提供的功能扩展现有网站的浏览体验，则可以创建扩展。  附带体验的示例包括 adblockers 和密码管理器。  

扩展的结构类似于常规 web 应用。  它至少包含应用清单 JSON 文件，该文件包含基本平台信息、用于定义功能的 JavaScript 文件以及 HTML 和 CSS 文件，以根据需要确定用户界面 \ (的外观 \ ) 。  若要直接处理部分浏览器（如窗口或选项卡），必须发送 API 请求，并且通常按名称引用浏览器。  

:::image type="complex" source="./media/example-extension-screenshot.png" alt-text="Microsoft Edge (Chromium) 扩展":::
  Microsoft Edge \ (Chromium \ ) 扩展名  
:::image-end:::  

## 基本指南  

一些最热门的浏览器可用于包含 Safari、Firefox、Chrome、Opera、Brave 和 Microsoft Edge。  开始扩展开发教程和文档检索的好地方是由浏览器组织托管的网站。  下表不是明确的，请将其用作有用的起始点。  

| Web 浏览器 | 基于 Chromium？ | 扩展开发主页 |  
|:--- |:--- |:--- |  
| Safari | 否 | [developer.apple.com/documentation/safariservices/safari_app_extensions][AppleDeveloperSafariservicesAppExtensions] |  
| Firefox | 否 | [developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions][MDNWebextensions] |  
| 镶边 | 是 | [developer.chrome.com/extensions][ChromeDeveloperExtensions] |  
| Opera | 是 | [dev.opera.com/extensions][OperaDevExtensions] |  
| Brave | 是 | 使用 [Chrome Web Store][GoogleChromeWebstoreCategoryExtensions] |  
| 新的 Microsoft Edge | 是 | [developer.microsoft.com/microsoft-edge/extensions][MicrosoftDeveloperEdgeExtensions] |  

> [!IMPORTANT]
> 网站的许多教程都使用特定于浏览器的 Api，这些 Api 可能与你要开发的浏览器不匹配。  在大多数情况下，Chromium 扩展在不同的 Chromium 浏览器中工作，并且 Api 按预期工作。  只有一些较少的常见 Api 才能严格地特定于浏览器。  有关教程的链接，请参阅另 [请参阅](#see-also)。  

## 为什么 Chromium？

如果你的目标是将扩展发布到尽可能多的浏览器扩展存储，则必须针对多个版本对其进行修改，以便在每个不同的浏览器环境中进行目标和运行。  与其他扩展类型不同， [Safari 扩展][AppleDeveloperSafariservicesAppExtensions]可以利用 web 和本机代码与对应的本机应用程序进行通信。  [Firefox 扩展][MDNWebextensions] 与其他扩展类型共享更多的内容，但也有一些 [差异][ExtensionworkshopPorting] 需要考虑。  但有一些好消息，上面的图表中的最后四个浏览器能够利用相同的代码程序包，并最大程度地减少更改和维护并行版本的要求。  这是因为浏览器基于 [Chromium 开放源代码项目][|::ref1::|Home]。  

通过创建 Chromium 扩展，你可以写入最少的代码，以最大程度地增加目标扩展存储的数量，并且最终可以找到并获取你的扩展的用户数。  

以下内容主要关注 Chromium 扩展。  

## 浏览器兼容性和扩展测试  

有时，Chromium 浏览器之间不存在 API 奇偶校验。  例如，标识和支付 Api 之间存在差异。  为确保您的扩展满足客户期望值，请通过官方浏览器文档（如 [Chrome api][ChromeDeveloperExtensionsApiIndex]、 [Opera 支持的扩展 Api][OperaDevExtensionsApis]和 [端口 CHROME (扩展][ExtensionsChromiumDeveloperGuidePortChrome]）查看 API 状态，Chromium) Edge。  

根据你所需的 Api，这些差异可能意味着你必须在每个应用商店的代码中创建稍有不同的代码包。  

开发扩展时，在将扩展提交到浏览器存储之前，你可以在浏览器中旁加载，以在不同的环境中对其进行测试。  

## 将扩展发布到浏览器存储  

你可以在以下浏览器存储中提交和查找浏览器扩展。  

*   [Firefox 浏览器加载项][MozillaAddonsFirefoxExtensions]  
*   [Chrome Web Store][GoogleChromeWebstoreCategoryExtensions]  
*   [Opera addons][OperaAddonsExtensions]  
*   [Microsoft Edge 加载项][MicrosoftEdgeAddonsCategoryExtensions]  

某些商店允许您从其他浏览器下载列出的扩展。  从另一个浏览器下载可能会将您 (开发人员 \ ) 的工作，如果用户能够导航到不同浏览器中的现有应用商店列表，则可以删除向其他商店提交的要求。  但是，浏览器存储不保证跨浏览器访问。  为了确保你的用户能够在不同的浏览器中找到你的扩展，你应该在每个浏览器扩展存储中维护一个列表。  

扩展可能具有重叠的访问群体，这些受众经常使用多个浏览器，或者你可能会发现它应该面向的读者不是以前的浏览器。  若要实现此目的，现有的 Chromium 扩展可能会从一个浏览器迁移到另一个浏览器。  

### 将现有扩展迁移到 Microsoft Edge  

如果你已为另一个 Chromium 浏览器开发了扩展，并且想要提供它并确保它通过 Microsoft Edge 工作，则不必重写你的扩展。  只要你使用的 Api 在不同的浏览器上可用，或者存在提供所需功能的其他 Api，将现有的 Chromium 扩展迁移到其他 Chromium 浏览器就非常简单。  

有关移植你的 Chrome 扩展的详细信息，请参阅 [向 Microsoft (Chromium) Edge 的端口 Chrome 扩展][ExtensionsChromiumDeveloperGuidePortChrome]。  将扩展移植到目标浏览器后，下一步是发布它。  

### 发布到 Microsoft Edge 加载项网站  

若要开始将扩展发布到 Microsoft Edge，您必须注册一个包含 MSA 电子邮件帐户的 [开发者帐户][MicrosoftDeveloperRegistration] \ ( @outlook .com、@live ) .com 等，以便在应用商店中提交您的扩展列表。  选择要注册的电子邮件地址时，请考虑是否必须与组织中的其他人一起转移或共享该扩展名的所有权。  注册完成后，您可以创建一个新的向应用商店提交的扩展。  

若要将扩展提交到应用商店，必须满足以下要求。  

*   存档 \ ( .zip \ ) 文件，其中包含你的代码文件。  
*   所有所需的视觉资源，包括徽标和小型促销图块。  
*   可选促销媒体，如屏幕截图、较大的促销图块、URL 或与您的分机的视频相结合的任意组合。  
*   描述你的扩展的信息，如名称、简短说明、详细说明和指向隐私策略的链接。  

> [!NOTE]
> 不同的存储可能具有不同的提交要求。  上面的列表总结了将扩展发布到 Microsoft Edge 的 [要求][ExtensionsChromiumPublish] 。  

完成提交过程后，将审阅您的扩展，并通过或失败认证过程。  将通知所有者，并根据需要执行后续步骤。  如果你向应用商店提交更新的扩展名（包括对扩展列表详细信息的更新），则会启动新的审阅过程。  

## 另请参阅  

*   [移植 Google Chrome 扩展][ExtensionworkshopPorting]  
*   [构建 Safari 应用扩展][AppleDeveloperSafariservicesAppExtensionsBuilding]  
*   [你的第一个扩展 (Firefox) ][MDNWebextensionsYourFirst]  
*   [入门教程 (Chrome) ][ChromeDeveloperExtensionsGetstarted]  
*   [ (Opera 入门) ][OperaDevExtensionsGettingStarted]  
*   [Microsoft Edge 入门 (Chromium) 扩展][ExtensionsChromiumGettingStartedIndex]  

<!-- image links -->  

<!-- links -->  

[ExtensionsChromiumDeveloperGuidePortChrome]: ./developer-guide/port-chrome-extension.md &quot;将端口 Chrome 扩展到 Microsoft (Chromium) Edge |Microsoft 文档&quot;  
[ExtensionsChromiumGettingStartedIndex]: ./getting-started/index.md &quot;Microsoft Edge 入门 (Chromium) 扩展 |Microsoft 文档&quot;  
[ExtensionsChromiumPublish]: ./publish/publish-extension.md &quot;发布扩展 |Microsoft 文档&quot;  

[MicrosoftDeveloperEdgeExtensions]: https://developer.microsoft.com/microsoft-edge/extensions &quot;开发 Microsoft Edge 的扩展 |Microsoft 开发人员&quot;  
[MicrosoftDeveloperRegistration]: https://developer.microsoft.com/registration &quot;合作伙伴中心 |Microsoft 开发人员&quot;  

[MicrosoftEdgeAddonsCategoryExtensions]: https://microsoftedge.microsoft.com/addons/category/Edge-Extensions &quot;Microsoft Edge 的扩展 |Microsoft Edge&quot;  

[AppleDeveloperSafariservicesAppExtensions]: https://developer.apple.com/documentation/safariservices/safari_app_extensions &quot;Safari 应用扩展 |Apple 开发人员&quot;  
[AppleDeveloperSafariservicesAppExtensionsBuilding]: https://developer.apple.com/documentation/safariservices/safari_app_extensions/building_a_safari_app_extension &quot;构建 Safari 应用扩展 |Apple 开发人员&quot;  

[ChromeDeveloperExtensions]: https://developer.chrome.com/extensions &quot;什么是扩展？ |Chrome 开发人员&quot;  
[ChromeDeveloperExtensionsApiIndex]: https://developer.chrome.com/extensions/api_index &quot;Chrome Api |Chrome 开发人员&quot;  
[ChromeDeveloperExtensionsGetstarted]: https://developer.chrome.com/extensions/getstarted &quot;入门教程 |Chrome 开发人员&quot;  

[ChromiumHome]: https://www.chromium.org/Home &quot;Chromium&quot;  

[ExtensionworkshopPorting]: https://extensionworkshop.com/documentation/develop/porting-a-google-chrome-extension &quot;移植 Google Chrome 扩展 |延长研讨会&quot;  

[GoogleChromeWebstoreCategoryExtensions]: https://chrome.google.com/webstore/category/extensions &quot;扩展名 |Chrome Web Store&quot;  

[MDNWebextensions]: https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions &quot;浏览器扩展 |MDN&quot;  
[MDNWebextensionsYourFirst]: https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/Your_first_WebExtension &quot;您的第一个扩展 |MDN&quot;  

[MozillaAddonsFirefoxExtensions]: https://addons.mozilla.org/firefox/extensions &quot;扩展名 |Firefox 的加载项&quot;  

[OperaAddonsExtensions]: https://addons.opera.com/extensions &quot;扩展名 |Opera Addons&quot;  

[OperaDevExtensions]: https://dev.opera.com/extensions &quot;扩展文档 |开发人员的 Opera&quot;  
[OperaDevExtensionsApis]: https://dev.opera.com/extensions/apis &quot;Opera 中支持的扩展 Api |开发人员的 Opera&quot;  
[OperaDevExtensionsGettingStarted]: https://dev.opera.com/extensions/getting-started &quot;入门 |开发人员的 Opera"  
