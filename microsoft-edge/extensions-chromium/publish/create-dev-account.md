---
description: 了解如何注册开发人员帐户以将扩展Microsoft Edge加载项应用商店
title: 注册为Microsoft Edge开发人员以发布扩展
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/17/2021
ms.topic: conceptual
ms.prod: microsoft-edge
keywords: edge-chromium， 扩展开发， 浏览器扩展， 加载项， 合作伙伴中心， 开发人员
ms.openlocfilehash: 0c3b4d70da214a171b7a6ebb308e89bad2ab16c2
ms.sourcegitcommit: 916b4daa26c2c78611f7d837bd6ecf009f0082df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/17/2021
ms.locfileid: "11343057"
---
# 注册为Microsoft Edge扩展开发人员  

若要将扩展提交到Microsoft Edge加载项应用商店，你必须在加载项Microsoft Edge注册。  该Microsoft Edge计划位于合作伙伴[中心上][MicrosoftPartnerCenter]。  

> [!IMPORTANT]
> 向应用计划提交扩展时，无需Microsoft Edge费用。  

##  <a name="before-you-begin"></a>开始之前  

如果你没有帐户，或者如果你有合作伙伴中心的现有商业帐户，请创建一个新的 Microsoft 帐户[ (MSA) ][WindowsCommunityEverythingAboutMicrosoftAccounts]注册到 Microsoft Edge 计划。  若要创建 Microsoft 帐户 \(Outlook/live/Hotmail\) ，请完成以下操作。  

1.  导航到 [account.microsoft.com][MicrosoftAccount]。  
1.  选择 **"创建 Microsoft 帐户"。**  
    
如果你在合作伙伴中心注册了开发人员帐户，请使用相应的 Microsoft 帐户 \(MSA\) 登录到你的开发人员帐户，然后注册 Microsoft Edge 计划。  

> [!NOTE]
> 如今，Microsoft Edge不支持使用工作或学校帐户注册。  将来，Microsoft Edge扩展团队计划支持将 Azure AD 租户链接到 MSA 帐户进行扩展管理。  

##  <a name="enroll-in-the-microsoft-edge-program-on-partner-center"></a>在合作伙伴中心Microsoft Edge注册计划  

1.  导航到开发人员[页面，][MicrosoftPartnerCenter]然后选择 **"转到仪表板"。**  
1.  如果你有 Microsoft 帐户，立即登录。  如果没有，请创建新的 Microsoft 帐户。  使用用于登录开发人员帐户的同一 Microsoft 帐户。  登录后，将显示注册表单。 下表介绍了注册表单上的字段。  
    
    若要注册Microsoft Edge计划，请登录帐户并填写表单。  
    
    :::row:::
       :::column span="1":::
          **帐户国家/地区**  
       :::column-end:::
       :::column span="2":::
          此字段是您的生活或企业所在的位置。  
          
          > [!IMPORTANT]
          > 注册后，此字段的值为只读。  
          
       :::column-end:::
    :::row-end:::  
    :::row:::
       :::column span="1":::
          **帐户类型**  
       :::column-end:::
       :::column span="2":::
          合作伙伴Microsoft Edge[计划提供][MicrosoftPartnerCenter]个人和公司帐户。  以下项目符号详细介绍了这些帐户。  这两种帐户类型都允许你将扩展Microsoft Edge加载项存储。  
          
          > [!IMPORTANT]
          > 注册后，你将无法更改此字段的值。  
          
          *   `Individual account`  
              个人帐户适用于未与公司关联的开发人员。  帐户验证过程较短，涉及验证发布者显示名称可用。  

          *   `Company account`  
              公司帐户与组织或企业关联。  帐户验证过程较长，包括确认你有权为公司创建帐户。  该过程的持续时间可能从几天到几周。  你的公司可能会收到来自 Microsoft 验证合作伙伴的电话呼叫。  
              
       :::column-end:::
    :::row-end:::  
    :::row:::
       :::column span="1":::
          **发布者显示名称**  
       :::column-end:::
       :::column span="2":::
          此字段包含加载项存储Microsoft Edge显示的名称。  只有在名称可用且您具有使用该名称的权利时，您才能使用该名称。  公司帐户必须使用组织的注册公司名称。  
          
          > [!NOTE]
          > 此字段的最大长度为 50 个字符。  
          
       :::column-end:::
    :::row-end:::  
    :::row:::
       :::column span="1":::
          **联系人详情**  
       :::column-end:::
       :::column span="2":::
          此字段包含 Microsoft 用于就任何帐户问题与您联系的任何联系人信息。  注册完成后，会向用户发送电子邮件确认。  对于公司帐户，必须使用与组织关联的注册电子邮件地址。  
       :::column-end:::
    :::row-end:::  
    :::row:::
       :::column span="1":::
          **公司审批者**  
       :::column-end:::
       :::column span="2":::
          对于公司帐户，您必须提供公司审批者的联系信息。  联系人信息包括姓名、电子邮件地址和电话号码。  Microsoft 与指定为验证流程一部分的公司审批者联系，以确保你的扩展属于你的组织。  
       :::column-end:::
    :::row-end:::  
    
1.  在提交注册表单之前，请阅读并接受《开发人员Microsoft Edge[条款和条件][MicrosoftAppDeveloperAgreement]。  
1.  若要完成注册，请选择"完成 **"。**  
    
##  <a name="next-steps"></a>后续步骤  

若要显示你的验证状态，请导航到"合作伙伴中心>**帐户设置"。**  等待验证过程完成时，请继续生成、测试和准备提交。  

有关详细信息，请导航到"[发布扩展"。][ExtensionsChromiumPublishExtension]  有关扩展入门的信息，请导航到开始[Microsoft Edge (Chromium) 扩展。][ExtensionsChromiumGettingStartedIndex]  

<!-- links -->  

[ExtensionsChromiumGettingStartedIndex]: ../getting-started/index.md "有关扩展Microsoft Edge (Chromium) 入门|Microsoft Docs"  
[ExtensionsChromiumPublishExtension]:  ./publish-extension.md "发布扩展|Microsoft Docs"  

[MicrosoftAppDeveloperAgreement]:  /legal/windows/agreements/app-developer-agreement "应用开发人员协议|Microsoft Docs"  

[MicrosoftAccount]:  https://account.microsoft.com/account "Microsoft 帐户"  

[MicrosoftPartnerCenter]:  https://partner.microsoft.com/dashboard/microsoftedge/public/login?ref=dd "合作伙伴中心"  

[WindowsCommunityEverythingAboutMicrosoftAccounts]:  https://community.windows.com/stories/everything-you-need-to-know-about-microsoft-accounts "你需要了解的 Microsoft 帐户信息|Windows Community"  
