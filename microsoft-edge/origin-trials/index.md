---
ms.assetid: ''
description: 安全实验一段固定的时间，并提供有关新平台功能的反馈。
title: 原始试验
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/29/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘、web 开发、html、css、原创试验、开发人员
ms.openlocfilehash: 470896435ab348419749a7de00adcdb83b784df3
ms.sourcegitcommit: 5cbc9237363b3a8ba212ca128aa03c71a33ec86f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2020
ms.locfileid: "10846524"
---
# 在 Microsoft Edge 中使用原创试验  

在有限的时间段内，开发人员可以使用初始试验在活动网站上试用实验性 Api。  使用原始试验时，访问你的网站的 Microsoft Edge 用户可能会运行使用实验性 Api 的代码。  若要访问每台用户计算机上的实验性 Api，无需转到 `edge://flags` 并打开功能标志。  有关详细信息，请参阅 [实验性 api][DeveloperMicrsoftEdgeOriginTrials]。  此外，你还可以提供有关 API 设计、使用情况或你使用 Api 到浏览器工程师和 web 标准社区的体验的反馈。  

## 开始使用初始试用版  

有关 Microsoft Edge 中可用的实验性 Api 的详细信息，请参阅 [Microsoft Edge 原始试用开发人员控制台][DeveloperMicrsoftEdgeOriginTrials]。  确保查看 Microsoft Edge 的最低版本要求和试用结束日期，以评估在你的网站上使用实验性 Api 的适用性。  

> [!NOTE]
> 如果出现以下情况，则实验可能比计划提前结束。  
> *   重大安全事件。  
> *   如果收集了足够的反馈表明需要进行重大重新设计以满足 web 开发人员的需求。  
> 在任何一种情况下，通知电子邮件都将发送给当前注册了实验的所有开发人员。  

### 注册实验性 API 的试用版  

使用以下步骤注册实验性 API 的试用版。  

1.  访问 [Microsoft Edge 原始试用开发人员控制台][DeveloperMicrsoftEdgeOriginTrials] 页面。  
1.  在任何可用实验中选择 "注册" 按钮。  
1.  使用 GitHub 用户名和密码登录到开发人员控制台。  
1.  选择 " **授权 MicrosoftEdge**"。  
1.  填写表单。  
    
    > [!NOTE]
    > 若要注册单个或所有子域，请选择 "设置 `Do you need to match all subdomains for the provided origin?` 为" `Yes` 。  例如， `https://dev.contoso.com` 是单个域， `https://*.contoso.com` 使用通配符表示所有子域。  
    
    > [!IMPORTANT]
    > 不允许使用以下原始格式。  
    > *   在原始位置指定子文件夹。  例如， `https://contoso.com/path/subfolder`  
    > 
    > *   将原点与查询字符串参数配合使用。  例如， `https://contoso.com/path/feature?query_parameter=12345`  
    
1.  选择 " **接受和注册**"。  

### 应用您的令牌  

令牌将立即生成并显示在 [Microsoft Edge 原始试验开发人员控制台][DeveloperMicrsoftEdgeOriginTrials] 页面上。  若要开始在你的网站上使用试用版，请使用以下任一方法将令牌应用于你的页面。  

*   将该 `origin-trial` 属性值和你的令牌添加到 `meta` 使用实验性 API 的每个页面上的标记。  
    
    ```html
    <meta http-equiv="origin-trial" content="replace-with-your-token">
    ```  
    
*   添加 `Origin-Trial` 到服务器的 HTTP 响应头。  
    
    ```json
    Origin-Trial: replace-with-your-token
    ```  
    
> [!NOTE]
> 您的令牌有效期为6周。  试用期结束之前，会向您发送提醒电子邮件，询问您的反馈，并要求您在令牌到期之前续订您的试用版。  

### 选择退出实验  

若要退出实验，请使用以下方法之一删除你的令牌。  

*   `meta`从使用实验 API 的每个页面中删除标记。  
    
    ```html
    <meta http-equiv="origin-trial" content="your-token">
    ```  
    
*   `Origin-Trial`从服务器的 HTTP 响应头中删除。  
    
    ```json
    Origin-Trial: your-token
    ```  
    
### 检测实验性功能并提供回退  

使用实验性 Api 时，请确保为网站的所有访问者提供工作体验。  访问者可以使用不支持你添加到代码中的实验性 Api 的浏览器。  此外，如果你的令牌在续订之前到期，实验性 API 将不再可用，可能会导致错误。  为避免这种情况，请确保检测浏览器中的可用功能。  有关详细信息，请参阅 [实现功能检测][MDNImplementingFeatureDetection]。

### 允许的来源路线图  

现在，Microsoft Edge 原始试用门户仅支持 SSL 启用的来源，这意味着网站必须正确实现 HTTPS 才能注册实验。  将来，计划提供以下安全来源。  

*   注册 `http://localhost` 为实验的来源。  若要 `http://localhost` 立即使用，请转到 `edge://flags` 并将实验设置为 " **启用**"。  
*   使用具有前缀的来源的扩展名 `extensions://` 注册实验。  
    
<!-- links -->  

[DeveloperMicrsoftEdgeOriginTrials]: https://developer.microsoft.com/microsoft-edge/origin-trials "Microsoft Edge 原始试用开发人员控制台 |Microsoft 文档"  

[MDNImplementingFeatureDetection]: https://developer.mozilla.org/docs/learn/tools_and_testing/cross_browser_testing/feature_detection "实施功能检测 |MDN"  
