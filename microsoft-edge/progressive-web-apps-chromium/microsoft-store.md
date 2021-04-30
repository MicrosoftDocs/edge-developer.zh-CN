---
description: 在 Microsoft Store 中发布，使 PWA 更可发现
title: 将渐进式 Web 应用发布到 Microsoft Store
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/28/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: 渐进式 Web 应用， PWA， Edge， Windows， Microsoft Store
ms.openlocfilehash: 5e78e909187408566219ffe80779bb9221b585fa
ms.sourcegitcommit: e3cd336c9448277e0dde3b9da1521b5cbc7c44d2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/30/2021
ms.locfileid: "11527055"
---
# <a name="publish-your-progressive-web-app-to-the-microsoft-store"></a>将渐进式 Web 应用发布到 Microsoft Store  

将渐进式 Web 应用 \ (PWA\) 发布到 [Microsoft Store][WindowsUwpPublishIndex] 具有以下优点。  

:::row:::
   :::column span="1":::
      **可发现性**  
   :::column-end:::
   :::column span="2":::
      用户自然地在应用商店中查找应用。  当你发布到 Microsoft Store 时，数百万 Windows 用户可能会发现 PWA 与其他 Windows 应用一起。  应用商店通过类别、已选择的集合等展示应用。  应用发现门户为应用的潜在用户提供轻松的浏览和购物体验。  你甚至可以 [使用屏幕截图、Hero][WindowsUwpPublishAppScreenshotsImages] 图像和视频预告片增强应用商店一览。  
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
1.  现在，你的帐户已注册应用开发人员计划。 若要创建应用预订，请完成以下操作。  
    1.  导航到**Windows & Xbox。**  
    1.  选择 **"**  >  **概述""新建应用"。**  
    1.  在提示符中键入应用的名称。  
    1.  选择`Reserve product name`。  
        
    :::image type="complex" source="./media/windows-partner-center-create-app.msft.png" alt-text="在 Windows 合作伙伴中心创建应用预订" lightbox="./media/windows-partner-center-create-app.msft.png":::
       在 Windows 合作伙伴中心创建应用预订  
    :::image-end:::  
    
1.  若要在"打包[PWA"](#package-your-pwa-for-the-store)部分显示要使用的发布者详细信息，请选择"**产品管理**""  >  **产品标识"。**  
    
    :::image type="complex" source="./media/windows-partner-center-publisher-info.msft.png" alt-text="从 Windows 合作伙伴中心复制发布者信息" lightbox="./media/windows-partner-center-publisher-info.msft.png":::
       从 Windows 合作伙伴中心复制发布者信息  
    :::image-end:::  
    
1.  复制并保存以下值。  
    *   **程序包 ID**  
    *   **发布者 ID**  
    *   **发布者显示名称**  
        
## <a name="package-your-pwa-for-the-store"></a>打包适用于应用商店的 PWA 

现在你已拥有应用发布信息，请为 PWA 生成一个 Windows 应用包。

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
1.  若要下载 Windows 应用包，请选择"下载 **"。**

下载的内容 `.zip` 是包含文件和 `.msixbundle` 文件的 `.classic.appxbundle` 存档。  这两个应用程序包允许 PWA 在多种 Windows 版本上运行。  有关详细信息，请导航到什么是[经典程序包？。][GithubPwaBuilderPwabuilderWindowsChromiumDocsClassicPackageMd]  

### <a name="submit-your-app-package-to-the-store"></a>将应用包提交到应用商店  

若要将应用提交到应用商店，请完成以下操作。  

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
        
1.  在 **"程序包"** 提示符下，选择 在 `.msixbundle` `.classic.appxbundle` "打包 [PWA"](#package-your-pwa-for-the-store) 部分生成的 和 文件。  
    
完成提交后，通常会在 24 至 48 小时内查看你的应用。  收到批准后，PWA 将在 Microsoft Store 中提供。  

## <a name="see-also"></a>另请参阅  

PWABuilder 提供了更多文档，可帮助你在 Microsoft Store 中获取 PWA。  

*   [测试和提交 PWA 应用包][GithubPwaBuilderPwabuilderWindowsChromiumDocsNextStepsMd]  
*   [将新的 PWA 发布到应用商店][GithubPwaBuilderPwabuilderWindowsChromiumDocsPublishNewAppMd]  
*   [将现有应用商店应用更新到 PWA][GithubPwaBuilderPwabuilderWindowsChromiumDocsUpdateExistingAppMd]  
*   [应用商店中 PBA 的图像建议][GithubPwaBuilderPwabuilderWindowsChromiumDocsImageRecommendationsMd]  
*   [应用打包解释器][GithubPwaBuilderPwabuilderWindowsChromiumDocsClassicPackageMd]  

<!-- links -->  

[LegalWindowsAgreementsStorePolicies]: /legal/windows/agreements/store-policies "Microsoft Store 策略|Microsoft Docs"  

[WindowsUwpPublishAnalytics]: /windows/uwp/publish/analytics "分析应用性能|Microsoft Docs"  
[WindowsUwpPublishAppScreenshotsImages]: /windows/uwp/publish/app-screenshots-and-images "应用屏幕截图、图像和预告片|Microsoft Docs"  
[WindowsUwpPublishIndex]: /windows/uwp/publish/index "发布 Windows 应用和游戏|Microsoft Docs"  

[MicrosoftPartnerDashboardHome]: https://partner.microsoft.com/dashboard/home "家庭|Microsoft 合作伙伴中心"  
[MicrosoftPartnerDashboardWindowsOverview]: https://partner.microsoft.com/dashboard/windows/overview "合作伙伴资源|Microsoft 合作伙伴中心"  

[MicrosoftStoreAppsWindows]: https://www.microsoft.com/store/apps/windows "Windows 应用|Microsoft Store"  

[WindowsBlogWindowsdeveloperHostedAppModel]: https://blogs.windows.com/windowsdeveloper/hosted-app-model "托管的应用模型|Windows 开发人员博客"  

[GithubPwaBuilderPwabuilderWindowsChromiumDocsClassicPackageMd]: https://github.com/pwa-builder/pwabuilder-windows-chromium-docs/blob/master/classic-package.md "什么是经典程序包？|GitHub"  
[GithubPwaBuilderPwabuilderWindowsChromiumDocsImageRecommendationsMd]: https://github.com/pwa-builder/pwabuilder-windows-chromium-docs/blob/master/image-recommendations.md "Windows PWA 程序包图像|GitHub"  
[GithubPwaBuilderPwabuilderWindowsChromiumDocsNextStepsMd]: https://github.com/pwa-builder/pwabuilder-windows-chromium-docs/blob/master/next-steps.md "将 PWA 加入 Microsoft Store 应用商店的|GitHub"  
[GithubPwaBuilderPwabuilderWindowsChromiumDocsPublishNewAppMd]: https://github.com/pwa-builder/pwabuilder-windows-chromium-docs/blob/master/publish-new-app.md "将新应用发布到应用商店|GitHub"  
[GithubPwaBuilderPwabuilderWindowsChromiumDocsUpdateExistingAppMd]: https://github.com/pwa-builder/pwabuilder-windows-chromium-docs/blob/master/update-existing-app.md "更新应用商店应用中的现有|GitHub"  

[PwabuilderMain]: https://www.pwabuilder.com "PWABuilder"  
