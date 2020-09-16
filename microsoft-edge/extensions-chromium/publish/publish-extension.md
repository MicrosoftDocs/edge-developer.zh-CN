---
description: 发布 Microsoft Edge (Chromium) Microsoft Edge 加载项应用商店的扩展。
title: 发布扩展
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/15/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium、扩展开发、浏览器扩展、addons、合作伙伴中心、开发人员
ms.openlocfilehash: 4f8433e74c0fd6dab3278792b94cf3cbaac05d2c
ms.sourcegitcommit: d360e419b5f96f4f691cf7330b0d8dff9126f82e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2020
ms.locfileid: "11015749"
---
# 发布扩展  

完成扩展的开发和测试后，您可能已准备好使用 Microsoft Edge 加载项目录分发扩展。  或者，如果您有一个您希望对 Microsoft Edge 用户可用的现有 chromium 扩展名，则可以将 [现有的 chromium 扩展移植][PortChromiumExtension] 到 microsoft edge。  

将扩展发布到 Microsoft Edge 加载项目录会增加扩展的范围，并使其对最终用户可用。  本主题提供将扩展提交到 Microsoft Edge 加载项目录的过程的演练。  

## 开始之前  

此时，你的扩展的工作原型应该准备就绪。  有关如何创建扩展的信息，请参阅 [入门教程][ExtensionsGettingStarted]。  

若要将扩展发布到 Microsoft Edge 加载项网站，必须在 [合作伙伴中心][MicrosoftPartnerCenter]拥有活动的开发人员帐户。  若要打开新的开发人员帐户并注册到 Microsoft Edge 加载项程序，请按照 [开发人员注册][DeveloperRegistration] 指南中所述的过程进行操作。  

创建一个表示您的扩展程序包的 zip 文件。  您的扩展程序包必须包含以下文件。  

*   扩展清单，用于指定详细信息，如扩展的名称、简短说明、权限和默认语言。  
*   您的扩展所需的图像和其他文件。  

清单中的以下字段将自动包含在你的应用商店明细详细信息中，并且无法从 "应用商店节目表" 页面中进行修改，本主题后面部分将对此进行了介绍。  确保在将程序包上载到合作伙伴中心之前，填写字段以与 "应用商店详细信息" 页面上的首选显示匹配。  有关清单文件所需代码的示例，请查看清单文件基础知识。  

*   `Name` 清单文件中的字段，它是 "应用商店详细信息" 页面上的 **显示名称** 。  
*   `Description` 清单文件中的字段，这是 "应用商店详细信息" 页面上的 **简短说明** 。  提供简短的 catchy 说明，以便在你的扩展列表的顶部显示。  如果包含，扩展清单文件中指定的简短说明将显示在应用商店的列表中。  如果清单文件中未包含简短说明，则显示前几行说明。  你应提供简短说明，以避免在你的应用商店摘要页面上重复内容。  

## 将扩展提交到 Microsoft Edge 加载项存储  

若要将扩展提交到 [合作伙伴中心][MicrosoftPartnerCenter]，请使用以下步骤。  

#### 步骤1：开始新提交  

转到[开发人员仪表板][MicrosoftPartnerCenter]，然后在 "**概述**" 页上选择 "**新建扩展名**"。  

#### 步骤2：上载扩展包  

使用 " **程序包** " 页面上载您的扩展程序包的 zip 文件。  您一次只能上载一个程序包。  如果 **软件包页面上的软件包** 上载未成功，您将无法继续提交。  

通过将程序包拖到 "上载" 字段，或选择 " **浏览文件**" 来上载程序包。  上载程序包后，将验证程序包。  验证成功后，查看扩展详细信息，然后选择 " **下一步** " 以继续。  如果存在验证错误，请解决问题并再次尝试上载。  

#### 步骤3：提供可用性详细信息  

在 " **可用性** " 页面上，输入有关扩展可用性的以下信息。  

##### 可见性  

选择以下可见性选项之一，定义是否可在 Microsoft Edge 加载项目录中发现你的扩展。  

*   `Public` \ (默认值 \ )   
    公共允许通过搜索、浏览 Microsoft Edge 加载项目录或在 Microsoft Edge 加载项存储中使用您的扩展的列表 URL，让所有人都能够发现扩展。  "扩展 **概述** " 页面上的 "合作伙伴中心" 仪表板上提供了 "列表" URL。  

*   `Hidden`  
    隐藏从搜索结果中删除扩展名或在 Microsoft Edge 加载项目录中浏览。  若要在 Microsoft Edge 加载项存储中分发隐藏的扩展，必须与客户共享列表 URL 和扩展。  

> [!NOTE]
> 您可以将您的扩展的可见性从 **公共** 更改为 **隐藏**。  当可见性设置为 "公共" 时，安装您的扩展的用户将保留对您的扩展的访问，并接收任何通过 Microsoft Edge 加载项网站提供的更新。  

##### 市场  

定义计划提供您的扩展的特定市场。  默认情况下，所有市场均已选中，包括以后添加的任何未来市场。  或者，选择 " **更改市场**"，选择特定市场。  取消选择单个市场以排除它们，或选择 " **取消全选** "，然后添加你选择的单个市场。  

> [!NOTE]
> 你可以更改提供扩展的市场。  已安装您的扩展的用户在其市场中可用时，将保留对您的扩展的访问。  但是，你的用户将无法再访问提交到 Microsoft Edge 加载项目录的任何未来更新。  

选择 " **保存** " 以继续转到 " **属性** " 部分。  

#### 步骤4：选择扩展的属性  

在 " **属性" 页**上，输入以下信息以指定扩展的属性。  将在 Microsoft Edge 加载项目录中向用户显示这些属性。  

| 扩展属性名称 | 描述 |  
|:--- |:--- |  
| 类别 \ (必需 \ )  | 最能描述您的分机的类别。  在右侧类别中列出您的扩展可帮助用户轻松地找到您的扩展并了解更多相关信息。  |  
| 隐私策略要求 \ (必需 \ )  | 指示你的扩展是否访问、收集或传输任何个人信息。  如果选择 **"是"** ，并且不提供，则你的扩展可能会失败认证步骤 `Privacy policy URL` 。  |  
| 隐私策略 URL | 有效的隐私策略 URL，用于传达您的扩展如何遵守隐私法律和法规。  您有责任确保您的分机符合隐私法律和法规，并提供有效的隐私政策 URL （如有必要）。  如果你的扩展正在访问、传输或收集任何个人信息，请提供隐私策略 URL。  若要确定你的扩展是否需要隐私策略，请转到 [Microsoft Edge 开发人员协议][MicrosoftAppDeveloperAgreement] 和 [microsoft edge 加载项目录开发人员策略][MicrosoftEdgeAddonsCatalogDeveloperPolicies]。  |  
| 网站 URL | 提供有关扩展的其他信息的网页。  `Website URL`必须指向您自己的网站上的页面，而不是 Microsoft Edge 加载项目录中您的扩展的 web 列表。  `Website URL`可帮助用户了解有关您的扩展、其功能和任何其他相关信息的更多信息。  |  
| 支持联系人详细信息 | 您的支持网页的 URL，或电子邮件地址以联系支持团队。  |  
| 成人内容 | 用于指定你的扩展是否包含成人内容的复选框。  扩展评级有助于确定你的扩展的目标受众的相应年龄组。  若要帮助确定你的分机号是否为成人内容，请转到 [Microsoft Edge 加载项目录开发人员策略][MicrosoftEdgeAddonsCatalogDeveloperPolicies]。  |  

选择 " **保存** " 以继续转到 " **应用商店节目表** " 部分。  

#### 步骤5：添加你的扩展的应用商店列表详细信息  

在 Microsoft Edge 加载项目录上访问列表的用户将向用户显示下节中提供的信息。  虽然某些字段是可选的，但你应该提供尽可能多的信息。  在应用商店中列出的扩展所需的最低详细信息（针对扩展程序包中提及的每种语言）是 **说明** 和 **扩展存储徽标**。  

> [!NOTE]
> 必须填写扩展 zip 包中提及的每种语言所需的最低应用商店列表详细信息。  若要在 Microsoft Edge 加载项目录上的应用商店中添加或删除语言，必须修改扩展包中的扩展支持的语言列表，创建新的扩展名包，然后重新上载。  

| 应用商店列表属性名称 | 描述 |  
|:--- |:--- |  
| 应用商店的待售房产语言 \ (必需 \ )  | 从 " **语言** " 下拉列表中选择一种语言，然后输入该语言的应用商店详细信息。  支持多种语言的扩展必须为每种支持的语言提供 "应用商店" 列表页面。  |  
| 显示名称 \ (必需 \ )  | 在您的扩展的清单文件中指定的扩展名的名称。  若要在提交后更改应用商店的显示名称，你可以更新清单文件中的名称，创建新的扩展包，然后重新上载它。  |  
| 说明 \ (必需 \ )  | "说明" 字段重点介绍扩展的功能、用户应安装的原因或用户需要了解的其他相关信息。  它应少于10000个字符。  |  
| 扩展存储徽标 \ (必需 \ )  | 表示你的公司或扩展徽标的图像，其纵横比为1，而建议的大小为 300 x 300 像素。  |  
| 小促销磁贴 (可选 \ )  | `Small promotional tile`图像用于在应用商店中与其他扩展一起显示您的扩展名。  图像的大小应为 440 x 280 像素。  |  
| 屏幕截图 \ (可选 \ )  | 你最多可以提交10个屏幕截图来详细描述你的扩展的功能。  屏幕截图的大小必须是 640 x 480 像素或 1280 x 800 像素。  |  
| 大型促销磁贴 (可选 \ )  | 在应用商店中，较大的促销图块用于 Microsoft Edge 加载项网站中更突出的功能扩展。  图像（如果已提交）将对用户可见。  PNG 文件的大小必须为 1400 x 560 像素。  |  
| YouTube 视频 URL \ (可选 \ )  | 您可以包括您的分机的促销 YouTube 视频。  `YouTube video URL`视频显示在您的扩展的 "应用商店" 页面上。  |  
| 简短说明 \ (必需 \ )  | 若要编辑简短说明，必须更新扩展包的清单文件中的说明字段，然后重新上载它。  |  
| 搜索词 \ (可选 \ )  | 搜索词是一个单词或短语，可帮助用户在 Microsoft Edge 加载项目录中搜索时发现你的扩展。  搜索词不会显示给用户。  |  

##### YouTube 视频 URL 要求  

确保您的视频满足以下要求。  

*   验证 YouTube 视频的内容是否符合 [Microsoft Edge Addons 目录开发人员策略][MicrosoftEdgeAddonsCatalogDeveloperPolicies] 主题。  
*   关闭视频上的广告。  有关详细信息，请参阅[在嵌入式视频上][GoogleYoutubeAnswer132596][设置默认广告格式][GoogleYoutubeAnswer2531367Topic7072227]和广告。  
*   为你的视频打开 "嵌入"。  有关详细信息，请转到 " [嵌入视频" & 播放列表][GoogleYoutubeAnswer171780]。  

执行以下步骤来提交视频的 YouTube 视频 URL。  

1.  在 YouTube 上，找到要添加到应用商店列表页面的视频。  
1.  在 "视频" 下，选择 "**共享**  >  **嵌入**"。  
1.  复制显示的 HTML 代码。  
1.  在 "应用商店列表详细信息" 页面上，将 HTML 代码粘贴到 `YouTube video URL` 字段中。  

##### 搜索条件要求  

搜索词必须满足以下要求。  

*   您最多可以输入21个字的搜索词。  无论是用作单个单词、短语还是二者的组合，您最多只能有21个单词。  
*   最多可达7个搜索词：单个单词或短语。  每个搜索词的字符数限制为30个字符。  

#### 步骤6：完成提交  

在 " **提交您的扩展** " 页面上，为 "证书" 添加备注以帮助测试您的扩展。  

##### 认证说明 (可选)   

提交扩展时，请使用 " **证书说明** " 页面向认证测试人员提供其他信息。  其他信息可帮助确保正确地测试扩展。  如果您的扩展未经过完全测试，则它可能无法通过认证。  

请确保在必要时包含以下信息。  

*   测试帐户的用户名和密码。  
*   访问隐藏或锁定的功能的步骤。  
*   根据区域或其他用户设置，功能的预期差异。  
*   如果提交是对现有扩展的更新，请包括有关对扩展所做的更改的信息。  
*   测试人员必须了解你的提交的任何其他信息。  

提供信息后，选择 " **发布** " 以将扩展提交到 Microsoft Edge 加载项目录。  你的提交将继续进行认证步骤。  在提交后，认证过程可能需要长达7个工作日。  

提交通过认证后，将在 Microsoft Edge 加载项目录中发布您的分机号码。  "合作伙伴中心" 仪表板中的扩展状态将更改为 `In the Store` 。  

> [!NOTE]
> 如果你在提交或注册过程中遇到任何问题，请在 [此处][ExtensionsSupportForm] 提供支持票证或向 [ext_dev_support@microsoft.com](mailto:ext_dev_support@microsoft.com)发送电子邮件。  

<!-- links -->  

[ExtensionsGettingStarted]: ../getting-started/index.md "Microsoft Edge 入门 (Chromium) 扩展 |Microsoft 文档"  
[DeveloperRegistration]: ./create-dev-account.md "注册为 Microsoft Edge 扩展开发人员 |Microsoft 文档"  
[PortChromiumExtension]: ../developer-guide/port-chrome-extension.md "将 Chromium 扩展移植到 Microsoft Edge |Microsoft 文档"  
[MicrosoftEdgeAddonsCatalogDeveloperPolicies]: ../store-policies/developer-policies.md "Microsoft Edge Addons 目录开发人员策略 |Microsoft 文档"  

[MicrosoftAppDeveloperAgreement]: /legal/windows/agreements/app-developer-agreement "应用开发人员协议 |Microsoft 文档"  

[MicrosoftPartnerCenter]: https://partner.microsoft.com/dashboard/microsoftedge/public/login?ref=dd "合作伙伴中心"  

[ExtensionsSupportForm]: https://support.microsoft.com/supportrequestform/e7a381be-9c9a-fafb-ed76-262bc93fd9e4 "扩展新的支持请求 |Microsoft 支持"  

[GoogleYoutubeAnswer2531367Topic7072227]: https://support.google.com/youtube/answer/2531367?ref_topic=7072227 "设置默认广告格式-YouTube 帮助"  

[GoogleYoutubeAnswer132596]: https://support.google.com/youtube/answer/132596 "嵌入式视频上的广告-YouTube 帮助"
[GoogleYoutubeAnswer171780]: https://support.google.com/youtube/answer/171780 "& 播放列表中嵌入视频-YouTube 帮助"  
