---
description: 向 Microsoft Store 发布 Edge （Chromium）扩展的循序渐进过程。
title: 发布扩展
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/21/2020
ms.topic: article
ms.prod: microsoft-edge-chromium
keywords: edge-chromium、扩展开发、浏览器扩展、addons、合作伙伴中心、开发人员
ms.openlocfilehash: 7b5be511af1e81efd5da4fc4bc0691f317437f94
ms.sourcegitcommit: 531ec8aa1f89b28bc4d271e8e995f846f2392bc3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/29/2020
ms.locfileid: "10607375"
---
# 发布扩展  

在 Microsoft Edge Addons 目录 \ （Microsoft Edge Addons \）中发布您的扩展。  您必须首先在[合作伙伴中心][MicrosoftPartnerCenter]创建提交并提交。  本文档列出了创建扩展提交时必须提供的所有详细信息。  

## 开始之前  

*   您必须在 "[合作伙伴中心][MicrosoftPartnerCenter]" 上拥有活动的开发人员帐户，才能在 Microsoft Edge Addons 中提交您的扩展。  如果没有，请[创建一个新的开发人员帐户][MicrosoftPartnerCenter]。  
*   创建扩展程序包的 zip 文件，并确保它包含以下文件：  
    *   清单文件，并且它必须定义您的扩展名的名称和版本。  
    *   您的扩展所需的图像和其他文件。  


如果尚未开始构建扩展，则可以参阅构建 Microsoft Edge Chromium 扩展的[入门][ExtensionsGettingStarted]教程。  

若要在[合作伙伴中心][MicrosoftPartnerCenter]创建扩展提交，请执行以下步骤。  

## 步骤1：开始新提交  

转到[开发人员仪表板][MicrosoftPartnerCenter]。  在 "概述" 页上，单击 "**新建扩展名**"。  

## 步骤2：上载扩展 Zip 文件  

**程序包**页面是你为扩展提交上载 zip 文件的位置。  你一次只能上载一个程序包，因此，如果你的扩展不完整，你可能会在发布工作包时随时上载工作包和更新。  请确保程序包中包含该 `manifest.json` 文件，并且在上载之前在 Microsoft Edge 上正常工作。  
通过将程序包拖动到 "上载" 字段或选择 "**浏览文件**" 来上载程序包。  程序包页面验证扩展 zip 文件，并显示上载的**成功或失败状态**。  如果程序包通过验证，则为已成功上载该文件，你将看到一条成功消息。  如果程序包未通过验证，则为程序包未被接受，您将看到一条错误消息。  如果程序包中存在错误，请解决这些问题，然后再次尝试上载。  

成功上载后，查看扩展详细信息，然后单击 "**下一步**" 以继续。  

## 步骤3：提供可用性详细信息  

### 定义可见性  

选择 "**可见性**" 选项以定义可能发现并获取您的扩展的受众。  这为你提供了指定用户是否应在 Microsoft Edge Addons 中找到你的扩展的选项，或者根本看不到该列表。  当前，在 "可见性" 下有两个选项：  

*   `Public`  
    这是默认选项。  
    如果你选择 `Public` ，你的扩展可供 Microsoft Edge Addons 中的每个人使用和发现。  如果你希望在 Microsoft Edge Addons 中列出你的扩展，请保留此选项，以便用户通过搜索、浏览和扩展的直接链接进行查找。  

*   `Hidden`  
    如果你选择 `Hidden` ，你的扩展将在 Microsoft Edge Addons 中隐藏在用户搜索或浏览中，你必须共享你的列表 URL 才能分发你的扩展。  具有列表直接链接的用户可能会在 Microsoft Edge 中下载它 \ （你可能会在扩展提交的**扩展概述**页面下找到你的列表 URL \）。  

> [!NOTE]
> 如果你将扩展提交为 "**公共**"，然后再将其更改为 "**私人性质**"，则在其公开时安装了该扩展的用户将继续拥有访问权限并收到未来更新。  

### 定义市场  

您必须定义您要在其中提供扩展的特定市场，请在 "**可用性**" 页面上的 "**市场**" 部分中选择 "**显示选项**"。  将显示 "市场选择" 弹出窗口，您应在其中选择市场。  默认情况下，所有市场均处于选中状态，包括以后可能添加的任何**市场**。  你可以取消选择单个市场以排除它们，或者单击 "**取消全选**"，然后添加你选择的单个市场。  

> [!NOTE]
> 如果用户已在特定市场中拥有您的扩展，并且稍后删除该市场，则已在该市场中具有扩展的用户可能会继续使用它，但不会获取你提交的更新。  

单击 "**保存**" 以转到 "**属性**" 部分。  

## 步骤4：选择扩展的属性  

### 扩展属性  

*   [类型](#category)  
*   [隐私策略要求](#privacy-policy-requirements)  
*   [隐私策略 URL](#privacy-policy-url)  
*   [网站 URL](#website-url)  
*   [支持 URL/电子邮件地址](#support-urlemail-address)  
*   [扩展分级](#extension-rating)  

#### 类型  

在右侧类别中列出您的扩展可帮助用户轻松地找到您的扩展并了解更多相关信息。  选择最能描述您的扩展的类别。  

**可能的值**：  

*   `Accessibility`  
*   `Blogging`  
*   `Developer Tools`  
*   `Fun`  
*   `News & Weather`  
*   `Photos`  
*   `Productivity`  
*   `Search Tools`  
*   `Shopping`  
*   `Social & Communication`  
*   `Sports`  

#### 隐私策略要求  

指明您的扩展是访问、收集还是传输任何个人信息。  

> [!NOTE]
> 如果你的扩展要求隐私策略，但你没有提供，则你的提交可能无法通过认证。  

**可能的值**：  

*   `No`：隐私策略 URL 是可选的。  
*   `Yes`：需要隐私策略 URL。  

#### 隐私策略 URL  

您有责任确保您的分机符合隐私法律和法规，并根据需要提供有效的隐私政策 URL。  如果你的扩展正在访问、传输或收集任何个人信息，则必须提供隐私策略 URL。  
若要确定你的扩展是否需要隐私策略，请查看[Microsoft Edge 开发人员协议][MicrosoftAppDeveloperAgreement]和[Microsoft Edge Addons 目录开发人员策略文档][MicrosoftEdgeAddonsCatalogDeveloperPolicies]。  

**可能的值**：  

*   `{url}`  

#### 网站 URL  

此属性是可选的。  
用于您的扩展的网页的 URL。  此 URL 必须指向您自己的网站上的页面，而不是 Microsoft Edge Addons 中的扩展 web 列表。  

**可能的值**：  

*   `{url}`  

#### 支持 URL/电子邮件地址  

此属性是可选的。  
用户通过您的分机支持的网页的 URL，或用于联系您的电子邮件地址以获得支持。  你包括所有提交的支持信息，以便你的用户知道如何获取来自你的支持。  

**可能的值**：  

*   `{email_address}`  
*   `{url}`  

#### 扩展分级  

扩展评级可帮助我们确定你的扩展的目标受众的年龄。  
若要帮助确定你的扩展是否具有成人内容，请查看[Microsoft Edge Addons 目录开发人员策略文档][MicrosoftEdgeAddonsCatalogDeveloperPolicies]。  

**可能的值**：  

*   成人 \ （checkbox \）：如果您的分机包含任何成人内容，请选中此框。  如果你为扩展选择 "成人"，你的列表将提供单独的标记，指示扩展包含成人内容。  

单击 "**保存**" 以转到 "清单" 部分。  

## 步骤5：为您的扩展添加节目表信息  

这是用户在 Microsoft Edge Addons 中查看您的列表时看到的信息。  列表中的许多字段是可选的，但我们建议提供尽可能多的信息，以使你的清单与众不同。 要视为完整的 Microsoft Edge Addons 中的列表所需的最低要求是在扩展程序包中提及的每种语言的[文本说明](#description)、[扩展徽标](#store-logo)和[小促销图块](#small-promotional-tile)。  

### 商店的 "待售房产" 域  

*   [应用商店一览语言](#store-listing-languages)  
*   [应用商店显示名称](#store-display-name)  
*   [描述](#description)  
*   [应用商店徽标](#store-logo)  
*   [小型促销磁贴](#small-promotional-tile)  
*   [媒体](#media)  
*   [简短说明](#short-description)  
*   [搜索词](#search-terms)  

#### 应用商店一览语言  

如果您的扩展程序包支持多种语言，则您的扩展名必须具有每个语言的一个列表页。  
你必须为每种语言单独完成列表详细信息 \ （文本说明、图像等），即使你对每种语言使用相同的内容也是如此。  如果您的扩展是以多种语言本地化的，这些语言将显示在 "列出" 页面的顶部。  

1.  从 "**语言**" 下拉列表中选择任意一种语言名称。  
1.  填写列表详细信息。  
1.  单击 **“保存”**。  
1.  对所有支持的语言重复上述操作。  

> [!NOTE]
> 若要在 Microsoft Edge Addons 中为您的列表添加或删除语言，必须修改扩展程序包支持的语言列表，然后重新上传。  

**可能的值**：  

*   `English (United States)`：这是默认值。  如果你不提及程序包中的任何语言，我们将默认语言设置为英语 \ （美国 \），并且你必须提供英语的列表（美国 \）。  
*   `{language}` \(`{Country}`\)  

#### 应用商店显示名称  

扩展程序包清单中提及的扩展的名称。  

> [!NOTE]
> 若要编辑名称，必须更新扩展程序包中的清单，然后重新上载它。  

#### 描述  

此字段是必需的。  
适用于您的扩展的用户的说明。  

**可能的值**：  

*   {plain_text}：少于10000个字符。  

#### 应用商店徽标  

此字段是必需的。  
用于扩展徽标的1:1 图像。  

**可能的值**：  

*   128px x 128px，PNG \ （.png）  
*   150px x 140px，PNG \ （.png）  
*   300px x 300px，PNG \ （.png \）：建议的大小。  

#### 小型促销磁贴  

此字段是必需的。  
小尺寸的促销图块。  您的列表显示在此磁贴上。  

**可能的值**：  

*   440px x 280x，PNG \ （.png）  

#### 媒体  

此字段是可选的。  
你应该提供这些资源来帮助更有效地显示你的产品。  

*   屏幕截图  
    描述扩展功能的扩展图像。  
    
*   大型促销图块  
    要在 Microsoft Edge Addons 中更突出地使用扩展功能的大型促销图块。  
    
*   YouTube 视频 URL  
    [适用于您的扩展的有效 YouTube 视频 URL][MicrosoftEdgeAddonsUploadYouTubeVideo]。  你的视频的质量应很好，最短的长度。  您的 YouTube 视频必须先通过认证，然后才能在 Microsoft Edge Addons 中发布您的扩展。  验证你的 YouTube 视频是否符合[Microsoft Edge Addons 目录开发人员策略文档][MicrosoftEdgeAddonsCatalogDeveloperPolicies]。  

**可能的值**：  

*   10个最大屏幕截图。  
    *   640px x 480px，PNG \ （.png）：屏幕截图。  
    *   1280px x 800px，PNG \ （.png）：屏幕截图。  
*   1400px x 560px，PNG \ （.png \）：大型提升图块。  
*   60秒或更短、2GB 或更小的 YouTube 视频 URL。  

#### 简短说明  

可在产品清单顶部使用的简短 catchy 说明。  如果未提供，则改为使用较长说明中的前几行。  由于你的说明还会显示在此文本下方，因此你应提供具有不同文本的简短说明，以便你的列表更不重复。  扩展的简短说明直接从程序包的清单文件中选取。  

> [!NOTE]
> 若要编辑简短说明，必须更新扩展程序包中的清单，然后重新上载它。  

#### 搜索词  

搜索词是不会向用户显示的单个字词或短语，但当用户使用这些术语进行搜索时，可帮助你在 Microsoft Edge Addons 中发现你的扩展。  

**要求**：  

*   7个或更少的搜索词  
*   每个搜索词30个或更少的字符  
*   小于或等于21的组合搜索词  

单击 "**保存**" 以继续保存您的 "列表" 部分。  单击 "**发布**" 以提供提交详细信息。  

## 步骤6：完成提交，然后单击 "发布"  

扩展提交过程的 "提交选项" 页面是你提供详细信息以帮助我们正确测试你的产品的位置。  这是一个可选步骤，但建议对许多提交执行此操作。  

### 发布暂停选项  

默认情况下，提交证明后立即发布。  你可以选择在将提交发布到特定日期之前保留。  这个部分的选项如下所述。  

*   **在提交证书后立即发布你的提交**  

    这是默认选择。  这意味着提交证书后，你的提交将立即开始发布过程  

*   **在特定日期开始发布你的提交**  

    选择 **"开始在特定日期发布提交**"，以确保在特定日期之前不发布提交。  如果选择此选项，则会在你指定的日期或之后尽早释放你的提交。  该日期必须为 24 小时之后的一个日期。  除了日期，您可以指定应开始发布提交的时间。  

### 认证说明  

当你提交扩展时，你可以选择使用 "证书说明" 页面向认证测试人员提供其他信息。  此信息有助于确保正确地测试扩展。  如果我们无法完全测试你的提交，则它可能无法通过认证。  

请确保包含以下 \ （如果适用于您的扩展名 \）：  

*   测试帐户的用户名和密码。  
*   访问隐藏或锁定的功能的步骤。  
*   根据区域或其他用户设置，行为预期差异。  
*   有关应用更新中的更改的信息。  
*   你认为测试人员必须了解你的提交的任何其他内容。  

完成上述详细信息后，单击 "**发布**" 以在 Microsoft Edge Addons 中提交您的扩展。  

当您完成为您的扩展创建提交并单击 "**发布**" 时，提交将进入认证步骤。  此过程通常在几天内完成，但在某些情况下，可能需要长达7个工作日。  提交完成认证后，将在 Microsoft Edge Addons 中发布您的分机号码，除非您选择了 "发布保留" 选项以指定在特定日期之前不应将其释放。  提交发布后，您将收到通知，并且仪表板中的扩展状态将更改为 `In the Store` 。  

<!-- image links -->  

<!-- links -->  

[ExtensionsGettingStarted]: ../getting-started/index.md "Microsoft Edge \ （Chromium \）扩展的入门 |Microsoft 文档"  

[MicrosoftEdgeAddonsUploadYouTubeVideo]: ./upload-video.md "上载 YouTube 视频 |Microsoft 文档"  
[MicrosoftEdgeAddonsCatalogDeveloperPolicies]: ../store-policies/developer-policies.md "Microsoft Edge Addons 目录开发人员策略 |Microsoft 文档"  

[MicrosoftAppDeveloperAgreement]: /legal/windows/agreements/app-developer-agreement "应用开发人员协议 |Microsoft 文档"  

[MicrosoftPartnerCenter]: https://partner.microsoft.com/dashboard/microsoftedge/public/login?ref=dd "合作伙伴中心"  
