---
description: 将 Microsoft Edge (Chromium) 扩展发布到 Microsoft Edge 加载项应用商店
title: 发布扩展
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/10/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium， 扩展开发， 浏览器扩展， 加载项， 合作伙伴中心， 开发人员
ms.openlocfilehash: b03a74d1faef914298729020e3c9ca4d465e0443
ms.sourcegitcommit: fe7301d0f62493e42e6a1a81cdbda3457f0343b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/13/2021
ms.locfileid: "11327673"
---
# 发布扩展  

开发和测试扩展后，即可分发扩展。 使用 Microsoft Edge 加载项目录分发扩展。  若要为 Microsoft Edge 用户释放现有 Chromium 扩展，请导航 [到移植现有的 Chromium 扩展][PortChromiumExtension]。  

将扩展发布到 Microsoft Edge 加载项目录，以扩大扩展范围，使其可供 Microsoft Edge 用户使用。  本文提供将扩展提交到 Microsoft Edge 加载项目录的过程。  

## 开始之前  

你应该准备好扩展的一个工作原型。  若要了解如何创建扩展，请参阅 [入门教程][ExtensionsGettingStarted]。  

若要将扩展发布到 Microsoft Edge 加载项目录，请使用合作伙伴中心上的活动开发人员 [帐户][MicrosoftPartnerCenter]。  如果你没有开发人员帐户，请创建新的开发人员帐户。  若要打开新的开发人员帐户并注册到 Microsoft Edge 加载项计划，请导航到 [开发人员注册][DeveloperRegistration]。  

创建表示扩展包的 zip 文件。  扩展包必须包含以下文件。  

*   指定扩展名称、简短说明、权限和默认语言等详细信息的扩展清单。  
*   扩展名所需的图像和其他文件。  

清单中的以下字段将自动包含在应用商店一览详细信息中。  这些字段在"应用商店一览" **页上是只读** 的。  本文稍后将介绍应用商店一览页。  在将程序包上载到合作伙伴中心之前，请确保字段值与你在应用商店详细信息页面上的首选显示相匹配。  有关清单文件所需的代码示例，请查看清单文件基础知识。  

*   `Name` 在清单文件中，字段是存储 **详细信息** 页上的显示名称。  
*   `Description` 清单文件中字段，这是 **应用商店详细信息页面上** 的简短说明。  提供一个简短、可捕获的说明，以显示在扩展列表的顶部。  包含后，扩展清单文件中指定的简短说明将显示在应用商店一览中。  如果清单文件中不包含简短说明，则显示"说明"的前几行。  提供简短说明以避免在应用商店一览页上重复内容。  

## 将扩展提交到 Microsoft Edge 加载项存储  

若要将扩展提交到 [合作伙伴中心][MicrosoftPartnerCenter]，请使用以下步骤。  

#### 步骤 1：启动新提交  

导航到 [开发人员仪表板，][MicrosoftPartnerCenter] 然后选择" **概述"** 页上的"创建新 **扩展** "。  

#### 步骤 2：上载扩展包  

使用 **"程序包** "页上载扩展包的 zip 文件。  一次只能上载一个程序包。  如果程序包上传在程序包页面上未成功，将无法**继续提交。**  

若要上传程序包，请选择该程序包并将其拖动到上传字段中。 还可以选择"**浏览文件"。**  上传程序包后，将验证程序包。  验证成功后，查看扩展详细信息， **然后选择"下** 一步"继续。  如果存在验证错误，请解决问题，然后再次尝试上载。  

#### 步骤 3：提供可用性详细信息  

在 **"可用性** "页上，输入有关扩展可用性的以下信息。  

##### 可见性  

选择以下可见性选项之一，以定义你的扩展在 Microsoft Edge 加载项目录中是否可发现。  

*   `Public` \ (default\)   
    公共允许所有人通过搜索、在 Microsoft Edge 加载项目录中浏览，或者使用 Microsoft Edge 加载项存储中扩展的一览 URL 来发现扩展。  在合作伙伴中心仪表板的"扩展概述"页上，列表 **URL** 可用。  
    
*   `Hidden`  
    隐藏将删除搜索结果或 Microsoft Edge 加载项目录中的浏览扩展。  若要在 Microsoft Edge 加载项存储中分发隐藏扩展，必须与客户共享扩展的一览 URL。  
    
> [!NOTE]
> 你可以将扩展的可见性从 **"** 公共"更改为 **"隐藏"。**  当可见性设置为公共时安装扩展的用户将保留对扩展的访问权限，并接收通过 Microsoft Edge 加载项网站提供的任何更新。  

##### 市场  

定义计划提供扩展的特定市场。  市场默认设置是所有市场，包括以后添加的任何未来市场。  若要选择特定市场，请选择"**更改市场"。**  切换个别市场以排除每个市场，或选择****"全部取消选择"，然后添加你选择的个别市场。  

> [!NOTE]
> 你可以更改提供扩展的市场。  在用户市场中提供扩展时安装扩展的用户将保留对扩展的访问权限。  但是，用户无法访问提交到 Microsoft Edge 加载项目录的任何未来更新。  

选择 **"** 保存"以继续" **属性"** 部分。  

#### 步骤 4：选择扩展的属性  

在 **"属性"** 页上，输入以下信息以指定扩展的属性。  这些属性向 Microsoft Edge 加载项目录中的用户显示。  

| 扩展属性名称 | 描述 |  
|:--- |:--- |  
| Category \ (required\)  | 最能描述扩展的类别。  在正确的类别中列出你的扩展可帮助用户轻松找到你的扩展并了解有关它更多内容。  |  
| 隐私策略要求 \ (必需\)  | 指示您的分机是否访问、收集或传输任何个人信息。  如果选择"是"并且未提供，你的扩展**** 可能无法通过认证步骤 `Privacy policy URL` 。  |  
| 隐私策略 URL | 一个有效的隐私策略 URL，用于传达你的扩展如何遵循隐私法律和法规。  你负责确保你的扩展遵循隐私法律和法规。  如果扩展正在访问、传输或收集任何个人信息，你还需要负责提供隐私策略 URL。  若要确定扩展是否要求隐私策略，请导航到 [Microsoft Edge][MicrosoftAppDeveloperAgreement] 开发人员协议和 [Microsoft Edge 加载项目录开发人员策略][MicrosoftEdgeAddonsCatalogDeveloperPolicies]。  |  
| 网站 URL | 提供有关扩展的其他信息的网页。  必须指向您自己的网站上的页面，而不是 Microsoft Edge 加载项目录中扩展 `Website URL` 的 Web 列表。  帮助 `Website URL` 用户了解有关扩展、其功能和任何其他相关信息的更多信息。  |  
| 支持联系人详细信息 | 支持网页的 URL，或联系支持团队的电子邮件地址。  |  
| 成熟内容 | 用于指定扩展是否包含成熟内容的复选框。  扩展分级有助于确定扩展的目标受众的适当年龄组。  若要帮助确定扩展是否具有成熟内容，请导航到 [Microsoft Edge 加载项目录开发人员策略][MicrosoftEdgeAddonsCatalogDeveloperPolicies]。  |  

选择 **"** 保存"以继续" **应用商店一览"** 部分。  

> [!Important]
> 你的开发人员/组织名称、网站 URL 和支持你在注册期间提交的联系人详细信息将显示给 Microsoft Edge 加载项存储上的用户。  

#### 步骤 5：添加扩展的应用商店一览详细信息  

以下部分中提供的信息向查看 Microsoft Edge 加载项目录列表的用户显示。  即使某些字段是可选的，您也应提供尽可能多的信息。  若要在应用商店中列出扩展，需要以下详细信息。  

*   **扩展** 包中每种语言的说明。  
*   **扩展包** 中每种语言的扩展存储徽标。  
    
> [!NOTE]
> 必须至少为扩展 zip 包中提到的一种语言填写所需的最低应用商店一览详细信息。  若要在 Microsoft Edge 加载项目录上的应用商店一览中添加或删除语言，请使用"应用商店一**** 览"页上的"添加语言 **"下拉列表。**  此外，你可以选择使用语言详细信息页面上的重复功能按钮跨其他语言复制资源。  

| 语言详细信息属性名称 | 描述 |  
|:--- |:--- |  
| 显示名称 \ (必填\)  | 扩展 `name` 的清单文件中指定的扩展名。  若要在提交显示名称应用商店，可以更新清单文件中的名称，创建新的扩展包，然后重新加载它。  |  
| Description \ (required\)  | 该字段重点介绍您的扩展功能、用户为什么应安装它，或者用户需要知道 `description` 的其他相关信息。  它应小于 10，000 个字符。  |  
| 扩展存储徽标 \ (必需\)  | 表示你的公司或纵横比为 1 的图像，建议大小 `extension logo` 为 300 x 300 像素。  此外，你可以选择使用重复按钮将资源从一种语言复制到所有其他语言。  在上传语言徽标后，可以在字段后找到该按钮。  |  
| 小型促销磁贴 \ (可选\)  | 该 `Small promotional tile` 图像用于将扩展与应用商店中其他扩展一起显示。  图像的大小应为 440 x 280 像素。  此外，你可以选择使用重复按钮将资源从一种语言复制到所有其他语言。  在上传该语言的促销磁贴后，可以在该字段后找到该按钮。  |  
| Screenshots \ (optional\)  | 最多可以提交 10 个描述扩展 `screenshots` 功能的详细信息。  屏幕截图的大小必须为 640 x 480 像素或 1280 x 800 像素。  此外，你可以选择使用重复按钮将资源从一种语言复制到所有其他语言。  在上传至少一种语言后，可以在该字段后找到该按钮。|  
| 大型促销磁贴 \ (可选\)  | `Large promotion tiles` 在 Microsoft Edge 加载项网站中更醒目地在应用商店中用于功能扩展。  图像（如果已提交）对用户可见。  PNG 文件的大小必须为 1400 x 560 像素。  此外，你可以选择使用重复按钮将资源从一种语言复制到所有其他语言。  在上传该语言的促销磁贴后，可以在该字段后找到该按钮。  |  
| YouTube 视频 URL \ (可选\)  | 可以包括扩展的促销 YouTube 视频。  视频 `YouTube video URL` 将显示在扩展的应用商店一览页面上。  |  
| 简短说明 \ (必填\)  | 若要编辑 `short description` ，必须更新扩展包的清单文件中的描述字段，然后重新加载它。  |  
| 搜索词 \ (可选\)  | `Search terms` 是单个字词或短语，可帮助用户在 Microsoft Edge 加载项目录中搜索时发现扩展。  搜索词不会向用户显示。  |  

##### YouTube 视频 URL 要求  

确保视频满足以下要求。  

*   验证 YouTube 视频的内容是否遵循 [Microsoft Edge 加载项目录开发人员策略][MicrosoftEdgeAddonsCatalogDeveloperPolicies]。  
*   关闭视频上的广告。  有关详细信息，请[导航到"][GoogleYoutubeAnswer2531367Topic7072227]在嵌入式视频上设置默认广告格式[和广告"。][GoogleYoutubeAnswer132596]  
*   为视频启用嵌入。  有关详细信息，请导航到" [在播放列表&视频][GoogleYoutubeAnswer171780]。  
    
若要提交视频的 YouTube 视频 URL，请完成以下步骤。  

1.  在 YouTube 上，找到要添加到应用商店一览页的视频。  
1.  在视频下，选择 **"共享**  >  **嵌入"。**  
1.  复制显示的 HTML 代码。  
1.  在应用商店一览详细信息页上，将 HTML 代码粘贴到 `YouTube video URL` 字段中。  
    
##### 搜索词要求  

搜索词必须满足以下要求。  

*   您可以输入搜索词以最多使用 21 个单词。  无论是用作单个单词、短语还是同时用作这两者的组合，您最多只能使用 21 个单词。  
*   最多七个搜索词：单个单词或短语。  每个搜索词的字符限制为 30 个字符。  
    
#### 步骤 6：完成提交  

在 **"提交扩展"** 页上，添加认证说明以帮助测试扩展。  

##### 认证说明 (可选)   

提交扩展时，请使用认证说明页**** 向认证测试人员提供其他信息。  其他信息有助于确保正确测试扩展。  如果你的扩展未经过完全测试，它可能无法通过认证。  

如有必要，请确保包含以下信息。  

*   测试帐户的用户名和密码。  
*   访问隐藏或锁定功能的步骤。  
*   基于区域或其他用户设置的功能预期差异。  
*   如果你的提交是对现有扩展的更新，请包含有关对扩展所做的更改的信息。  
*   测试人员必须了解的有关你的提交的其他信息。  

提供信息后，选择" **发布** "将扩展提交到 Microsoft Edge 加载项目录。  你的提交将继续执行认证步骤。  提交后，认证过程最多可能需要 7 个工作日。  

当你的提交通过认证时，你的扩展将发布到 Microsoft Edge 加载项目录中。  合作伙伴中心仪表板中扩展的状态将更改为 `In the Store` 。  

> [!NOTE]
> 如果你在提交或注册过程中遇到任何问题，请向扩展新支持请求提交支持票证[][ExtensionsSupportForm]，或向用户[ext_dev_support@microsoft.com。][MailtoExtDevSupportMicrosoftCom]  

<!-- links -->  

[ExtensionsGettingStarted]: ../getting-started/index.md "Microsoft Edge (Chromium) Extensions |Microsoft Docs"  
[DeveloperRegistration]: ./create-dev-account.md "注册为 Microsoft Edge 扩展开发人员|Microsoft Docs"  
[PortChromiumExtension]: ../developer-guide/port-chrome-extension.md "将 Chromium 扩展移植到 Microsoft Edge |Microsoft Docs"  
[MicrosoftEdgeAddonsCatalogDeveloperPolicies]: ../store-policies/developer-policies.md "Microsoft Edge 加载项目录开发人员策略|Microsoft Docs"  

[MicrosoftAppDeveloperAgreement]: /legal/windows/agreements/app-developer-agreement "应用开发人员协议|Microsoft Docs"  

[MicrosoftPartnerCenter]: https://partner.microsoft.com/dashboard/microsoftedge/public/login?ref=dd "合作伙伴中心"  

[ExtensionsSupportForm]: https://support.microsoft.com/supportrequestform/e7a381be-9c9a-fafb-ed76-262bc93fd9e4 "扩展新支持请求|Microsoft 支持"  

[GoogleYoutubeAnswer2531367Topic7072227]: https://support.google.com/youtube/answer/2531367?ref_topic=7072227 "设置默认广告格式|YouTube 帮助"  

[GoogleYoutubeAnswer132596]: https://support.google.com/youtube/answer/132596 "嵌入视频上的|YouTube 帮助"  
[GoogleYoutubeAnswer171780]: https://support.google.com/youtube/answer/171780 "将视频&播放列表|YouTube 帮助"  

[MailtoExtDevSupportMicrosoftCom]: mailto:ext_dev_support@microsoft.com "将电子邮件发送到ext_dev_support@microsoft.com" 
