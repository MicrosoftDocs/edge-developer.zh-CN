---
description: 从 Microsoft Edge 加载项存储更新或删除扩展的过程
title: 更新扩展列表
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/10/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium， 扩展开发， 浏览器扩展， 加载项， 合作伙伴中心， 开发人员
ms.openlocfilehash: 930d0f835e89451d09743a20ac4097c596ea5c30
ms.sourcegitcommit: fe7301d0f62493e42e6a1a81cdbda3457f0343b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/13/2021
ms.locfileid: "11327482"
---
# 更新或删除扩展  

你随时可能会更新提交的扩展，或者从 Microsoft Edge 加载项存储中删除已发布的扩展列表。  

## 更新 Microsoft Edge 加载项存储上的扩展  

> [!NOTE]
> 更新到扩展的认证过程持续时间可能从几小时到几天。  

### 更新 Microsoft Edge 加载项存储中的现有扩展  

若要更新应用商店上的扩展，请完成以下步骤。  

1.  导航到 [开发人员仪表板][MicrosoftPartnerCenter] ，然后选择想要更新的扩展。  
1.  更新扩展包或扩展的元数据。  如果更新扩展包，请确保增加清单文件中的版本。  
1.  进行更改后，选择"**保存**发布"以  >  **** 更新扩展列表，然后开始认证过程。  
1.  列 `Status` 显示后 `In the store` ，扩展更新在 Microsoft Edge 加载项存储中可用。  
    
### 在认证步骤中更新扩展  

虽然你的扩展仍处于认证阶段，在将其发布到 Microsoft Edge 加载项存储之前，你可以更新它。 如果你的扩展未能通过认证过程，你可能需要更新你的扩展。    

若要检查扩展的状态，请导航到与合作伙伴中心上的一览 [相关联的仪表板][MicrosoftPartnerCenter]。  

若要编辑提交，请完成以下步骤。  

1.  导航到 [开发人员仪表板][MicrosoftPartnerCenter] ，然后选择想要更新的扩展。  将显示你在上一次提交期间填写的信息。  
1.  若要打开 **"扩展概述** "部分，请使用左侧导航栏。  若要取消当前提交，请选择"**取消提交"。**  
1.  移动到其他部分并更新扩展包或扩展的元数据。  如果更新扩展包，请确保增加清单文件中的版本，以匹配自上一个程序包版本以来的更改。  
1.  进行更改后，选择"**保存**  >  **发布"。**  
    
> [!IMPORTANT]
> 此过程将停止并删除 Microsoft Edge 扩展认证管道中的当前提交，并从最新提交开始新评审。  

### 在认证失败后更新扩展  

扩展失败认证过程后，需要更新扩展并重新提交包含反馈的扩展。  

若要编辑扩展，请完成以下步骤。  

1.  导航到 [开发人员仪表板并选择][MicrosoftPartnerCenter] 未通过认证过程的扩展。  
1.  更新扩展包或包含从认证过程收到的反馈的元数据。  如果更新扩展包，请确保增加清单文件中的版本。  
1.  进行更改后，选择"**保存**  >  **发布"。**  
    
## 从 Microsoft Edge 加载项存储中删除扩展  

若要从 Microsoft Edge 加载项存储中删除扩展，请完成以下步骤。  

1.  导航到 [开发人员仪表板][MicrosoftPartnerCenter]。  在"仪表板"页中，选择要删除的一览。  
1.  选择 **列表上的扩展** 概述。  
1.  选择 **"取消发布** "以从 Microsoft Edge 加载项存储中删除列表。  
    
您的扩展现已从 Microsoft Edge 加载项存储中删除。  已安装扩展的用户可能会继续使用它，但新用户找不到它。  

<!-- links -->  

[MicrosoftPartnerCenter]: https://partner.microsoft.com/dashboard/microsoftedge/public/login?ref=dd "合作伙伴中心"  
