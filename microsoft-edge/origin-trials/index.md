---
ms.assetid: ''
description: 安全试验固定一段时间，并提供有关新平台功能的反馈。
title: 原始试验
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: edge， Web 开发， html， css， 源试用版， 开发人员
ms.openlocfilehash: cc03ec556d4b32ca37cebcd4ee7ba155bfe4404b
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11397543"
---
# <a name="use-origin-trials-in-microsoft-edge"></a>在 Microsoft Edge 中使用源试用版  

开发人员可以使用源试用版在有限的一段时间内在实时网站上试用实验性 API。  使用源试用版时，访问站点的 Microsoft Edge 用户可能会运行使用实验性 API 的代码。  若要访问每个用户计算机上实验性 API，无需转到 `edge://flags` 并打开功能标志。  有关详细信息，请导航到[实验 API。][DeveloperMicrsoftEdgeOriginTrials]  此外，你可以向浏览器工程师和 Web 标准社区提供有关 API 设计、用例或使用 API 的体验的反馈。  

## <a name="get-started-using-origin-trials"></a>开始使用源试用版  

有关 Microsoft Edge 中提供的实验性 API 详细信息，请导航到 [Microsoft Edge 源试用版开发人员控制台][DeveloperMicrsoftEdgeOriginTrials]。  确保查看 Microsoft Edge 的最低版本要求和试用结束日期，以评估在网站上使用实验性 API 的适用性。  

> [!NOTE]
> 如果发生以下任一情况，则实验可能会早于计划结束。  
> *   重大安全事件。  
> *   如果收集到足够的反馈，表明需要进行重大重新设计以满足 Web 开发人员的需求。  
> 无论哪种情况，都向当前在实验中注册的所有开发人员发送通知电子邮件。  

### <a name="register-for-a-trial-of-an-experimental-api"></a>注册实验性 API 试用版  

使用以下步骤注册实验性 API 试用版。  

1.  访问 [Microsoft Edge Origin Trials 开发人员控制台][DeveloperMicrsoftEdgeOriginTrials] 页。  
1.  选择任何可用实验上的"注册"按钮。  
1.  使用 GitHub 用户名和密码登录开发人员控制台。  
1.  选择 **"授权 MicrosoftEdge"。**  
1.  填写表单。  
    
    > [!NOTE]
    > 若要注册单个或所有子域，请选择将 `Do you need to match all subdomains for the provided origin?` 设置设置为 `Yes` 。  例如， `https://dev.contoso.com` 是单个域， `https://*.contoso.com` 并使用通配符表示所有子域。  
    
    > [!IMPORTANT]
    > 不允许以下源格式。  
    > *   指定源上的子文件夹。  例如， `https://contoso.com/path/subfolder`  
    > 
    > *   将原点与查询字符串参数一同使用。  例如， `https://contoso.com/path/feature?query_parameter=12345`  
    
1.  选择 **"接受"并注册**。  
    
### <a name="apply-your-token"></a>应用令牌  

将立即生成令牌，并显示在 Microsoft [Edge 源试用版开发人员控制台][DeveloperMicrsoftEdgeOriginTrials] 页面上。  若要开始在网站上使用试用版，请使用以下任一方法将令牌应用到你的页面。  

*   将 `origin-trial` 属性值和令牌添加到使用实验性 API 的每一 `meta` 页上的标记中。  
    
    ```html
    <meta http-equiv="origin-trial" content="replace-with-your-token">
    ```  
    
*   添加到 `Origin-Trial` 服务器的 HTTP 响应标头。  
    
    ```json
    Origin-Trial: replace-with-your-token
    ```  
    
> [!NOTE]
> 你的令牌有效期为 6 周。  在试用结束之前，会向你发送提醒电子邮件，请求你提供反馈，并要求你考虑在令牌过期之前续订试用版。  

### <a name="opt-out-of-an-experiment"></a>选择退出实验  

若要选择退出实验，请使用以下方法之一删除令牌。  

*   从每个使用实验性 API 的页面 `meta` 中删除标记。  
    
    ```html
    <meta http-equiv="origin-trial" content="your-token">
    ```  
    
*   从 `Origin-Trial` 服务器的 HTTP 响应标头中删除。  
    
    ```json
    Origin-Trial: your-token
    ```  
    
### <a name="detect-experimental-features-and-provide-a-fallback"></a>检测实验功能并提供回退  

使用实验性 API 时，请确保为网站的所有访问者提供工作体验。  访问者可能会使用不支持添加到代码中的实验性 API 的浏览器。  此外，如果你的令牌在续订之前过期，实验性 API 将不再可用，这可能会导致错误。  若要避免这种情况，请确保检测到浏览器中可用的功能。  有关详细信息，请导航到["实现功能检测"。][MDNImplementingFeatureDetection]

### <a name="roadmap-for-allowed-origins"></a>允许来源的路线图  

Microsoft Edge Origin Trials 门户现在仅支持启用 SSL 的源，这意味着网站必须正确实现 HTTPS 才能注册实验。  将来，将规划以下安全源。  

*   注册 `http://localhost` 为实验的来源。  若要在 `http://localhost` 今天使用，请导航 `edge://flags` 到实验，将实验设置为 **"已启用"。**  
*   使用具有前缀 `extensions://` 来源的扩展以注册实验。  
    
<!-- links -->  

[DeveloperMicrsoftEdgeOriginTrials]: https://developer.microsoft.com/microsoft-edge/origin-trials "Microsoft Edge Origin Trials 开发人员控制台|Microsoft Docs"  

[MDNImplementingFeatureDetection]: https://developer.mozilla.org/docs/learn/tools_and_testing/cross_browser_testing/feature_detection "实现功能检测|MDN"  
