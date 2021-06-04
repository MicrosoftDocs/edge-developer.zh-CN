---
description: 将Microsoft Edge (Chromium) 扩展发布到Microsoft Edge加载项应用商店
title: 发布扩展
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/06/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium， 扩展开发， 浏览器扩展， 加载项， 合作伙伴中心， 开发人员
ms.openlocfilehash: c7d44a8c02a030cc11c763c35efb7111fff76665
ms.sourcegitcommit: 7f7922dbb6af87ecac1378d18359125770c5b8e5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2021
ms.locfileid: "11536800"
---
# <a name="publish-your-extension"></a>发布扩展  

开发和测试扩展后，你已准备好分发扩展。 使用Microsoft Edge加载项应用商店分配扩展。  若要为用户Chromium现有 Microsoft Edge 扩展，请导航到[移植现有][PortChromiumExtension]Chromium 扩展。  

将扩展发布到Microsoft Edge加载项应用商店，以增加其范围，使其可供Microsoft Edge用户使用。  本文提供将扩展提交到加载项Microsoft Edge的过程。  

## <a name="before-you-begin"></a>开始之前  

你应该已准备好扩展的工作原型。  若要了解如何创建扩展，请参阅 [入门教程][ExtensionsGettingStarted]。  

若要将扩展发布到Microsoft Edge加载项应用商店，请使用合作伙伴中心上的活动开发人员[帐户][MicrosoftPartnerCenter]。  如果你没有开发人员帐户，请创建新的开发人员帐户。  若要打开新的开发人员帐户并注册到 Microsoft Edge 外接程序 计划，请导航到"开发人员[注册"。][DeveloperRegistration]  

创建表示扩展包的 zip 文件。  扩展包必须包含以下文件。  

*   指定扩展名称、简短说明、权限和默认语言等详细信息的扩展清单。  
*   扩展名所需的图像和其他文件。  
    
清单中的以下字段将自动包含在应用商店一览详细信息中。  这些字段在"应用商店一览 **"网页上是只读** 的。  本文稍后将介绍应用商店一览网页。  在将程序包上载到合作伙伴中心之前，请确保字段值与你在应用商店详细信息网页上的首选显示相匹配。  有关清单文件所需的代码示例，请查看清单文件基础知识。  

*   `Name` 清单文件（即应用商店 **详细信息网页上** 的显示名称）中的 字段。  
*   `Description` 清单文件（即应用商店详细信息网页上的简短**** 说明）中的 字段。  提供一个简短、简短的说明，显示在扩展列表的顶部。  如果扩展清单文件包含简短说明，它会显示在应用商店一览中。  如果清单文件中不包含简短说明，则应用商店一览中的前 `Description` 几行显示。  提供简短说明以避免在应用商店一览网页上重复内容。  
    
## <a name="submit-your-extension-to-microsoft-edge-add-ons-store"></a>将扩展提交Microsoft Edge加载项应用商店  

若要将扩展提交到 [合作伙伴中心][MicrosoftPartnerCenter]，请执行以下步骤。  

## <a name="step-1--start-a-new-submission"></a>步骤 1：启动新提交  

导航到开发人员 [仪表板，][MicrosoftPartnerCenter] 然后选择 **"概述"网页上** 的"创建新 **扩展** "。  

## <a name="step-2--upload-the-extension-package"></a>步骤 2：Upload扩展包  

使用 **程序包** 网页上传扩展包的 zip 文件。  一次只能上传一个程序包。  如果程序包上传在程序包网页上未成功，你的 **提交将被** 阻止。  

若要上载程序包，请选择并将程序包拖动到上载字段。  此外，还可以选择"**浏览文件"。**  上传程序包后，将验证程序包。  验证成功后，查看扩展详细信息，然后选择" **下一步** "继续。  如果存在验证错误，请解决问题，然后再次尝试上载。  

## <a name="step-3--provide-availability-details"></a>步骤 3：提供可用性详细信息  

在 **可用性** 网页上，输入有关扩展可用性的以下信息。  

### <a name="visibility"></a>可见性  

选择以下可见性选项之一，以定义你的扩展在加载项Microsoft Edge中是否可发现。  

*   `Public` \(default\)   
    公共允许所有人通过搜索、在 Microsoft Edge 加载项应用商店中浏览，或者使用 Microsoft Edge 加载项应用商店中的扩展一览 URL 来发现你的扩展。  合作伙伴中心仪表板上的扩展概述网页中提供了列表**URL。**  
*   `Hidden`  
    Hidden 从搜索结果中或在加载项存储中Microsoft Edge扩展。  若要在加载项应用商店中Microsoft Edge隐藏的扩展，必须与客户共享扩展一览 URL。  
    
> [!NOTE]
> 你可以将扩展的可见性从"公共"**更改为****"隐藏"。**  当可见性设置为公共时安装扩展的用户将保留对扩展的访问权限，并接收你通过 Microsoft Edge 外接程序 网站提供的任何更新。  

### <a name="markets"></a>市场  

定义计划提供扩展的特定市场。  市场默认设置是所有市场，包括以后添加的任何未来市场。  若要选择特定市场，请选择"**更改市场"。**  切换个别市场以排除每个市场，或选择" **取消全** 选"，然后添加你选择的个别市场。  

> [!NOTE]
> 你可以更改提供扩展的市场。  在用户市场中提供扩展时安装扩展的用户将保留对扩展的访问权限。  但是，用户无法访问提交到加载项应用商店的任何Microsoft Edge更新。  

选择 **"保存** "以继续" **属性"** 部分。  

## <a name="step-4-select-properties-for-your-extension"></a>步骤 4：选择扩展的属性  

在 **"属性** "网页上，输入以下信息以指定扩展的属性。  这些属性将显示给加载项Microsoft Edge中的用户。  

| 扩展属性名称 | 说明 |  
|:--- |:--- |  
| Category \(required\)  | 最能描述扩展的类别。  在正确的类别中列出扩展可帮助用户轻松找到扩展并了解有关它的更多内容。  |  
| 隐私策略要求 \(\)  | 指示您的扩展是否访问、收集或传输任何个人信息。  如果选择"是"并且未提供 ，你的**** 扩展可能无法通过认证步骤 `Privacy policy URL` 。  |  
| 隐私策略 URL | 用于传达扩展如何遵循隐私法律和法规的有效隐私策略 URL。  你负责确保你的扩展遵循隐私法律和法规。  如果你的扩展正在访问、传输或收集任何个人信息，你还负责提供隐私策略 URL。  若要确定扩展是否要求隐私策略，请导航Microsoft Edge[开发人员][MicrosoftAppDeveloperAgreement]协议Microsoft Edge[加载项商店开发人员策略。][MicrosoftEdgeAddonsCatalogDeveloperPolicies]  |  
| 网站 URL | 提供有关扩展的其他信息的网页。  必须指向自己网站上的网页，而不是加载项商店中扩展Microsoft Edge `Website URL` Web 列表。  `Website URL`帮助用户了解有关扩展、扩展功能以及任何其他相关信息的更多信息。  |  
| 支持联系人详细信息 | 支持网页的 URL 或用于联系支持团队的电子邮件地址。  |  
| 成熟内容 | 用于指定扩展是否包含成熟内容的复选框。  扩展分级可帮助确定扩展的目标受众的适当年龄组。  若要帮助确定扩展内容是否成熟，请导航Microsoft Edge[加载项应用商店开发人员策略"][MicrosoftEdgeAddonsCatalogDeveloperPolicies]。  |  

选择 **"保存** "以继续浏览 **应用商店一览** 部分。  

> [!Important]
> 你的开发人员/组织名称、网站 URL 和支持你在注册期间提交的联系人详细信息将显示给加载项Microsoft Edge上的用户。  

## <a name="step-5-add-store-listing-details-for-your-extension"></a>步骤 5：为扩展添加应用商店一览详细信息  

以下部分中提供的信息显示给在加载项应用商店中查看Microsoft Edge列表的用户。  尽管某些字段是可选的，但您应该提供尽可能多的信息。  若要在应用商店中列出扩展，需要以下详细信息。  

*   **扩展** 包中每种语言的说明。  
*   **扩展包中** 每种语言的扩展应用商店徽标。  
    
> [!NOTE]
> 必须为扩展 zip 包中提到的至少一种语言填写所需的最低应用商店一览详细信息。  若要在加载项应用商店的应用商店一览中添加或删除Microsoft Edge，请使用"应用商店一览"网页上的"添加语言******"** 下拉列表。  此外，你可以选择使用语言详细信息网页上的重复功能按钮将资产从一种语言复制到另一种语言。  

| 语言详细信息属性名称 | 说明 |  
|:--- |:--- |  
| 显示名称 \(required\)  | `name`在扩展的清单文件中指定的扩展的 。  若要在提交显示名称应用商店，你可以更新清单文件中的名称，创建新的扩展包，然后重新加载它。  |  
| Description \(required\)  | 该字段重点介绍扩展执行哪些功能、为什么用户应安装它，或者用户需要知道 `description` 的其他相关信息。  它应小于 10，000 个字符。  |  
| 扩展存储徽标 \(必填\)  | 表示你的公司或纵横比 `extension logo` 为 1、建议大小为 300 x 300 像素的图像。  此外，你可以选择使用重复按钮将资源从一种语言复制到所有其他语言。  上传语言徽标后，可以在字段后找到按钮。  |  
| 小促销磁贴 \(可选\)  | 该 `Small promotional tile` 图像用于显示扩展以及应用商店中其他扩展。  图像的大小应为 440 x 280 像素。  此外，你可以选择使用重复按钮将资源从一种语言复制到所有其他语言。  在上传该语言的促销磁贴后，可以在字段后找到该按钮。  |  
| Screenshots \(optional\)  | 你最多可以提交 10 个描述扩展 `screenshots` 功能的详细信息。  屏幕截图的大小必须为 640 x 480 像素或 1280 x 800 像素。  此外，你可以选择使用重复按钮将资源从一种语言复制到所有其他语言。  在上载至少一种语言后，可以在字段后找到该按钮。|  
| 大型促销磁贴 \(可选\)  | `Large promotion tiles` 在应用商店中用于更醒目地在应用商店中Microsoft Edge 外接程序扩展。  图像（如果已提交）对用户可见。  PNG 文件的大小必须为 1400 x 560 像素。  此外，你可以选择使用重复按钮将资源从一种语言复制到所有其他语言。  在上传该语言的促销磁贴后，可以在字段后找到该按钮。  |  
| YouTube 视频 URL \(可选\)  | 你可以包含扩展的促销 YouTube 视频。  视频 `YouTube video URL` 显示在扩展的应用商店一览网页上。  |  
| 简短说明 \(必填\)  | 若要编辑 `short description` ，必须更新扩展包清单文件中的描述字段，然后重新加载它。  |  
| 搜索词 \(可选\)  | `Search terms` 是一个字词或短语，当用户在加载项应用商店中搜索时Microsoft Edge扩展。  搜索词不会向用户显示。  |  

### <a name="youtube-video-url-requirements"></a>YouTube 视频 URL 要求  

确保视频满足以下要求。  

*   验证 YouTube 视频的内容是否遵循加载项[Microsoft Edge开发人员策略。][MicrosoftEdgeAddonsCatalogDeveloperPolicies]  
*   关闭视频上的广告。  有关详细信息，请导航到"设置嵌入视频的默认[广告][GoogleYoutubeAnswer2531367Topic7072227]格式[和广告"。][GoogleYoutubeAnswer132596]  
*   为视频启用嵌入。  有关详细信息，请导航到嵌入 [视频&播放列表][GoogleYoutubeAnswer171780]。  
    
若要提交视频的 YouTube 视频 URL，请完成以下步骤。  

1.  在 YouTube 上，找到要添加到应用商店一览网页的视频。  
1.  在视频下，选择"**共享**  >  **嵌入"。**  
1.  复制显示的 HTML 代码。  
1.  在应用商店一览详细信息网页上，将 HTML 代码粘贴到 `YouTube video URL` 字段中。  
    
### <a name="search-terms-requirements"></a>搜索词要求  

搜索词必须满足以下要求。  

*   输入搜索词最多可使用 21 个单词。  无论是用作单个单词、短语还是同时用作两者的组合，您最多只能使用 21 个单词。  
*   最多七个搜索词：单个单词或短语。  每个搜索词的字符限制为 30 个字符。  
    
## <a name="step-6-complete-your-submission"></a>步骤 6：完成提交  

在 **"提交扩展"** 网页上，添加认证说明以帮助测试扩展。  

### <a name="notes-for-certification-optional"></a>认证说明 (可选)   

提交扩展时，请使用认证 **网页** 的"说明"向认证测试人员提供其他信息。  其他信息有助于确保正确测试扩展。  如果你的扩展未经过完全测试，它可能无法通过认证。  

必要时，请确保包含以下信息。  

*   测试帐户的用户名和密码。  
*   访问隐藏或锁定功能的步骤。  
*   根据区域或其他用户设置预期功能差异。  
*   如果你的提交是对现有扩展的更新，请包含有关对扩展所做的更改的信息。  
*   测试人员必须了解的有关你的提交的其他信息。  
    
提供相关信息后，**选择"发布**"以将扩展Microsoft Edge加载项应用商店。  你的提交将继续执行认证步骤。  提交后，认证过程最多可能需要 7 个工作日。  

提交通过认证后，你的扩展Microsoft Edge加载项商店中。  合作伙伴中心仪表板中扩展的状态将更改为 `In the Store` 。  

> [!NOTE]
> 如果你在提交或注册过程中遇到任何问题，请向扩展新支持请求提交支持票证[][ExtensionsSupportForm]，[或][MailtoExtDevSupportMicrosoftCom]向应用 ext_dev_support@microsoft.com。  

<!-- links -->  

[ExtensionsGettingStarted]: ../getting-started/index.md "Microsoft Edge (Chromium) 扩展 | Microsoft Docs 入门"  
[DeveloperRegistration]: ./create-dev-account.md "注册为Microsoft Edge开发人员|Microsoft Docs"  
[PortChromiumExtension]: ../developer-guide/port-chrome-extension.md "将Chromium扩展移植到Microsoft Edge |Microsoft Docs"  
[MicrosoftEdgeAddonsCatalogDeveloperPolicies]: ../store-policies/developer-policies.md "Microsoft Edge加载项存储 开发人员策略|Microsoft Docs"  

[MicrosoftAppDeveloperAgreement]: /legal/windows/agreements/app-developer-agreement "应用开发人员协议|Microsoft Docs"  

[MicrosoftPartnerCenter]: https://partner.microsoft.com/dashboard/microsoftedge/public/login?ref=dd "合作伙伴中心"  

[ExtensionsSupportForm]: https://support.microsoft.com/supportrequestform/e7a381be-9c9a-fafb-ed76-262bc93fd9e4 "Extensions 新的支持请求|Microsoft 支持"  

[GoogleYoutubeAnswer2531367Topic7072227]: https://support.google.com/youtube/answer/2531367?ref_topic=7072227 "设置默认广告格式|YouTube 帮助"  

[GoogleYoutubeAnswer132596]: https://support.google.com/youtube/answer/132596 "嵌入视频上的|YouTube 帮助"  
[GoogleYoutubeAnswer171780]: https://support.google.com/youtube/answer/171780 "嵌入视频&播放列表|YouTube 帮助"  

[MailtoExtDevSupportMicrosoftCom]: mailto:ext_dev_support@microsoft.com "将电子邮件 ext_dev_support@microsoft.com" 
