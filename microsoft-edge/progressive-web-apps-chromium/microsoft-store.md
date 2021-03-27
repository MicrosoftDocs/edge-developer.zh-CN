---
description: 在 Microsoft Store 中发布，使 PWA 更可发现
title: 将渐进式 Web 应用发布到 Microsoft Store
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/18/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: 渐进式 Web 应用， PWA， Edge， Windows， Microsoft Store
ms.openlocfilehash: 68471535446a2270a23b32205717da225fd9e4bf
ms.sourcegitcommit: bff24ab1f0a66aaf4c7f5ff81cea3eb28c6d8380
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/26/2021
ms.locfileid: "11461491"
---
# <a name="publish-your-progressive-web-app-to-the-microsoft-store"></a>将渐进式 Web 应用发布到 Microsoft Store  

将渐进式 Web 应用 \ (PWA\) 发布到 [Microsoft Store][WindowsUwpPublishIndex] 具有以下优点。  

:::row:::
   :::column span="1":::
      **可发现性**  
   :::column-end:::
   :::column span="2":::
      用户自然地在应用商店中查找应用。  通过发布到 Microsoft Store，数百万 Windows 用户可能会发现 PWA 与其他 Windows 应用一起。  应用商店通过类别、已选择的集合等展示应用。  应用发现门户为应用的潜在用户提供轻松的浏览和购物体验。  你甚至可以 [使用屏幕截图、Hero][WindowsUwpPublishAppScreenshotsImages] 图像和视频预告片增强应用商店一览。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **Trustiness**  
   :::column-end:::
   :::column span="2":::
      Windows 客户知道他们可能会信任其 Microsoft Store 购买和下载，因为他们遵守严格的 Microsoft [质量和安全标准][LegalWindowsAgreementsStorePolicies]。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **易于安装**  
   :::column-end:::
   :::column span="2":::
      Microsoft Store 在所有 [Windows 10][MicrosoftStoreAppsWindows]应用中提供一致且用户友好的安装体验。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **应用分析**  
   :::column-end:::
   :::column span="2":::
      [Windows 合作伙伴中心仪表板][WindowsUwpPublishIndex]提供有关应用[运行状况、][WindowsUwpPublishAnalytics]使用情况等的详细分析。  
   :::column-end:::
:::row-end:::  

若要将 PWA 发布到 Microsoft Store，无需更改代码。  相反，你可以创建应用预订、打包 PWA，以及将程序包提交到应用商店。  以下各节将介绍这些步骤。   

## <a name="create-an-app-reservation"></a>创建应用预订  

[Windows 合作伙伴][MicrosoftPartnerDashboardWindowsOverview] 中心是你将应用提交到 Microsoft Store 的中心。  

若要创建应用预订，请完成以下操作。  

1.  若要显示已注册的计划，请完成以下操作。  
    1.  使用你的 Microsoft 帐户登录到 Windows 合作伙伴中心，然后导航到合作伙伴 [中心仪表板][MicrosoftPartnerDashboardHome]。  
    1.  导航到 **Windows & Xbox**  
        *   如果 **显示 Windows &** Xbox，则应用已注册。  
        *   如果未**显示 Windows & Xbox，** 请选择"**添加程序"。**  
    
    :::image type="complex" source="./media/windows-partner-center-add-program.msft.png" alt-text="在 Windows 合作伙伴中心仪表板中添加计划" lightbox="./media/windows-partner-center-add-program.msft.png":::
       在 Windows 合作伙伴中心仪表板中添加计划
    :::image-end:::  
    
1.  若要注册开发人员计划，请完成以下操作。  
    1.  导航到**Windows & Xbox。**  
    1.  选择 **"开始使用"。**  
    1.  请按照提示操作。  
1.  现在，你的应用已注册应用开发人员计划。 若要创建应用预订，请完成以下操作。  
    1.  导航到**Windows & Xbox。**  
    1.  选择 **"**  >  **概述""新建应用"。**  
    1.  在提示符中键入 PWA 名称。  
    1.  选择`Reserve product name`。  
    
    :::image type="complex" source="./media/windows-partner-center-create-app.msft.png" alt-text="在 Windows 合作伙伴中心创建应用预订" lightbox="./media/windows-partner-center-create-app.msft.png":::
       在 Windows 合作伙伴中心创建应用预订  
    :::image-end:::  

1.  若要在"打包[PWA"](#package-your-pwa)部分显示要使用的发布者详细信息，请选择"**产品管理**""  >  **产品标识"。**  
    
    :::image type="complex" source="./media/windows-partner-center-publisher-info.msft.png" alt-text="从 Windows 合作伙伴中心复制发布者信息" lightbox="./media/windows-partner-center-publisher-info.msft.png":::
       从 Windows 合作伙伴中心复制发布者信息  
    :::image-end:::  

1.  复制并保存以下值。  
    *   **程序包 ID**  
    *   **发布者 ID**  
    *   **发布者显示名称**  
        
## <a name="package-your-pwa"></a>打包 PWA  

为 PWA 生成 Windows 应用包。  

应用包是包含应用元数据的文件，包括名称、说明、图标 `.msixbundle` 等。  它使用 [托管的应用程序模型，Microsoft][WindowsBlogWindowsdeveloperHostedAppModel]Edge 为 PWA 提供支持。  在此模型中，PWA 在用作 Windows 应用的同时使用新式 Web 功能。  新式 Web 功能包括服务工作者、脱机、推送通知、保护等。  

若要生成应用包，请完成以下操作。  

1.  导航到 [PWA 生成器][PwabuilderMain]。  
1.  键入 PWA 的 URL。  
1.  选择 **"开始**  >  **生成我的 PWA**  >  **Windows**  >  **选项"。**  
1.  粘贴你在创建应用预订 [部分中保存的以下](#create-an-app-reservation) 值。  
    *   **程序包 ID**  
    *   **发布者 ID**  
    *   **发布者显示名称**  
        
    :::image type="complex" source="./media/pwabuilder-publisher-info.msft.png" alt-text="将发布者信息粘贴到 PWABuilder 中" lightbox="./media/pwabuilder-publisher-info.msft.png":::
       将发布者信息粘贴到 PWABuilder 中  
    :::image-end:::  
    
1.  选择"**完成"。**  
1.  若要下载 Windows 应用包，请选择"下载 **"。**  下载内容 `.zip` 是包含文件的 `.msixbundle` 存档。  使用 `.msixbundle` "将应用 [包提交到应用商店"部分中的](#submit-your-app-package-to-the-store) 文件。  

### <a name="submit-your-app-package-to-the-store"></a>将应用包提交到应用商店  

现在，你已 `.msixbundle` 拥有应用包。  若要将应用包提交到应用商店，请完成以下操作。  

1.  导航到 [Windows 合作伙伴中心][MicrosoftPartnerDashboardWindowsOverview] 
1.  选择你的应用。  
1.  选择 **"开始提交"。**  
    
    :::image type="complex" source="./media/windows-partner-center-start-submission.msft.png" alt-text="在 Windows 合作伙伴中心上启动新应用提交" lightbox="./media/windows-partner-center-start-submission.msft.png":::
       在 Windows 合作伙伴中心上启动新应用提交  
    :::image-end:::  
    
1.  完成以下提示，获取有关应用的信息。
    *   pricing  
    *   年龄分级  
    *   和更多信息  
        
1.  在 **"程序包"** 提示符上，选择 `.msixbundle` 在"打包 [PWA"部分生成的](#package-your-pwa) 文件。  

完成提交后，通常会在 24 至 48 小时内查看你的应用。  收到批准后，PWA 将在 Microsoft Store 中提供。  

<!-- links -->  

[LegalWindowsAgreementsStorePolicies]: /legal/windows/agreements/store-policies "Microsoft Store 策略|Microsoft Docs"  

[WindowsUwpPublishAnalytics]: /windows/uwp/publish/analytics "分析应用性能|Microsoft Docs"  
[WindowsUwpPublishAppScreenshotsImages]: /windows/uwp/publish/app-screenshots-and-images "应用屏幕截图、图像和预告片|Microsoft Docs"  
[WindowsUwpPublishIndex]: /windows/uwp/publish/index "发布 Windows 应用和游戏|Microsoft Docs"  

[MicrosoftPartnerDashboardHome]: https://partner.microsoft.com/dashboard/home "家庭|Microsoft 合作伙伴中心"  
[MicrosoftPartnerDashboardWindowsOverview]: https://partner.microsoft.com/dashboard/windows/overview "合作伙伴资源|Microsoft 合作伙伴中心"  

[MicrosoftStoreAppsWindows]: https://www.microsoft.com/store/apps/windows "Windows 应用|Microsoft Store"  

[WindowsBlogWindowsdeveloperHostedAppModel]: https://blogs.windows.com/windowsdeveloper/hosted-app-model "托管的应用模型|Windows 开发人员博客"  

[PwabuilderMain]: https://www.pwabuilder.com "PWABuilder"  

