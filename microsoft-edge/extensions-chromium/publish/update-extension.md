---
description: 更新或删除加载项存储中的Microsoft Edge的过程
title: 更新扩展列表
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/17/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium， 扩展开发， 浏览器扩展， 加载项， 合作伙伴中心， 开发人员
ms.openlocfilehash: 692c534ac0586d53002e4a032197e22ae24e2863
ms.sourcegitcommit: 916b4daa26c2c78611f7d837bd6ecf009f0082df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/17/2021
ms.locfileid: "11343158"
---
# 更新或删除扩展  

你随时可能会更新提交的扩展，也可以从加载项Microsoft Edge中删除已发布的扩展列表。  

##  <a name="update-your-extension-on-the-microsoft-edge-add-ons-store"></a>更新加载项Microsoft Edge扩展  

> [!NOTE]
> 更新到扩展的认证过程的持续时间可能需要几个小时到几天。  

###  <a name="update-an-existing-extension-in-the-microsoft-edge-add-ons-store"></a>更新加载项存储Microsoft Edge扩展  

若要更新应用商店上的扩展，请完成以下步骤。  

1.  导航到 [开发人员仪表板][MicrosoftPartnerCenter] ，然后选择要更新的扩展。  
1.  更新扩展包或扩展的元数据。  如果更新扩展包，请确保增加清单文件中的版本。  
1.  进行更改后，选择"保存**发布**"  >  **** 以更新扩展列表，并开始认证过程。  
1.  列 `Status` 显示后 `In the store` ，扩展更新在加载项Microsoft Edge上可用。  
    
###  <a name="update-your-extension-during-the-certification-step"></a>在认证步骤中更新扩展  

虽然你的扩展仍处于认证阶段，在将其发布到加载项Microsoft Edge之前，你可以更新它。 如果你的扩展未能通过认证过程，你可能还需要更新你的扩展。    

若要检查扩展的状态，请导航到与合作伙伴中心上的一览 [相关联的仪表板][MicrosoftPartnerCenter]。  

若要编辑提交，请完成以下步骤。  

1.  导航到 [开发人员仪表板][MicrosoftPartnerCenter] ，然后选择要更新的扩展。  将显示你在上一次提交期间填写的信息。  
1.  若要打开 **扩展概述** 部分，请使用左侧导航栏。  若要取消当前提交，请选择"**取消提交"。**  
1.  移动到其他部分并更新扩展包或扩展的元数据。  如果更新扩展包，请确保增加清单文件中的版本，以匹配自上一个程序包版本以来的更改。  
1.  进行更改后，选择"保存**发布**  >  **"。**  
    
> [!IMPORTANT]
> 此过程会停止当前提交，并从 Microsoft Edge扩展认证管道中删除你的当前提交，并且新评审从最新提交开始。  

###  <a name="update-your-extension-after-it-failed-the-certification"></a>在认证失败后更新扩展  

扩展失败认证过程后，你需要更新扩展并重新提交包含反馈的扩展。  

若要编辑扩展，请完成以下步骤。  

1.  导航到 [开发人员仪表板][MicrosoftPartnerCenter] 并选择未通过认证过程的扩展。  
1.  更新扩展包或包含从认证过程收到的反馈的元数据。  如果更新扩展包，请确保增加清单文件中的版本。  
1.  进行更改后，选择"保存**发布**  >  **"。**  
    
##  <a name="remove-extensions-from-the-microsoft-edge-add-ons-store"></a>从加载项存储Microsoft Edge扩展  

若要从加载项Microsoft Edge中删除扩展，请完成以下步骤。  

1.  导航到开发人员 [仪表板][MicrosoftPartnerCenter]。  从仪表板页面，选择要删除的一览。  
1.  选择 **一览上的扩展** 概述。  
1.  选择 **"取消发布**"以从加载项Microsoft Edge列表中删除列表。  
    
你的扩展现已从加载项Microsoft Edge中删除。  已安装扩展的用户可能会继续使用它，但新用户找不到它。  

<!-- links -->  

[MicrosoftPartnerCenter]: https://partner.microsoft.com/dashboard/microsoftedge/public/login?ref=dd "合作伙伴中心"  
