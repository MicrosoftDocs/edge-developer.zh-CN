---
description: 在PWA中发布，使你的Microsoft Store
title: 将渐进式 Web 应用发布到Microsoft Store
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/28/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: 渐进 Web 应用、PWA、Edge、Windows、Microsoft Store
ms.openlocfilehash: 40a6b94412a0788c87f7231025809098c98f18e9
ms.sourcegitcommit: 7cba715ef71cbac4ee0ebe8f07c0c0e4a2c64221
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2021
ms.locfileid: "11643247"
---
# <a name="publish-your-progressive-web-app-to-the-microsoft-store"></a>将渐进式 Web 应用发布到Microsoft Store  

将渐进式 Web 应用 \ (PWA\) 发布到[Microsoft Store具有下列][WindowsUwpPublishIndex]优点。  

:::row:::
   :::column span="1":::
      **可发现性**  
   :::column-end:::
   :::column span="2":::
      用户自然地在应用商店中查找应用。  当你发布到应用Microsoft Store，Windows数百万PWA发现你的Windows应用。  应用商店通过类别、已选择的集合等展示应用。  应用发现门户为应用的潜在用户提供轻松的浏览和购物体验。  你甚至可以 [使用屏幕截图、Hero][WindowsUwpPublishAppScreenshotsImages] 图像和视频预告片增强应用商店一览。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **Trustiness**  
   :::column-end:::
   :::column span="2":::
      Windows客户知道他们可能会信任他们的Microsoft Store购买和下载，因为他们遵守严格的 Microsoft[质量和安全标准][LegalWindowsAgreementsStorePolicies]。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **易于安装**  
   :::column-end:::
   :::column span="2":::
      The Microsoft Store provides a consistent and user-friendly install experience across [all Windows 10 apps][MicrosoftStoreAppsWindows].  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **应用分析**  
   :::column-end:::
   :::column span="2":::
      合作伙伴[Windows][WindowsUwpPublishIndex]仪表板提供了有关应用运行状况、使用情况等的详细分析[][WindowsUwpPublishAnalytics]。  
   :::column-end:::
:::row-end:::  

若要将PWA发布到Microsoft Store，无需更改代码。  相反，你可以创建应用预订、打包PWA，然后提交到应用商店。  以下各节将介绍这些步骤。   

## <a name="create-an-app-reservation"></a>创建应用预订  

[Windows中心][MicrosoftPartnerDashboardWindowsOverview]是你将应用提交到应用中心Microsoft Store。  

若要创建应用预订，请完成以下操作。  

1.  若要显示已注册的计划，请完成以下操作。  
    1.  使用 Microsoft Windows登录到合作伙伴中心，然后导航到合作伙伴[中心仪表板][MicrosoftPartnerDashboardHome]。  
    1.  导航到**Windows & Xbox**  
        *   如果**Windows & Xbox，** 则应用已注册。  
        *   如果未**Windows & Xbox，** 请选择"添加**程序"。**  
    
    :::image type="complex" source="./media/windows-partner-center-add-program.msft.png" alt-text="在合作伙伴中心仪表板Windows计划" lightbox="./media/windows-partner-center-add-program.msft.png":::
       在合作伙伴中心仪表板Windows计划
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
        
    :::image type="complex" source="./media/windows-partner-center-create-app.msft.png" alt-text="在合作伙伴中心Windows应用预订" lightbox="./media/windows-partner-center-create-app.msft.png":::
       在合作伙伴中心Windows应用预订  
    :::image-end:::  
    
1.  若要在"打包你的产品"[部分显示你的](#package-your-pwa-for-the-store)发布者PWA，**请选择"** 产品管理""  >  **产品标识"。**  
    
    :::image type="complex" source="./media/windows-partner-center-publisher-info.msft.png" alt-text="从合作伙伴中心复制Windows发布者信息" lightbox="./media/windows-partner-center-publisher-info.msft.png":::
       从合作伙伴中心复制Windows发布者信息  
    :::image-end:::  
    
1.  复制并保存以下值。  
    *   **程序包 ID**  
    *   **发布者 ID**  
    *   **Publisher显示名称**  
        
## <a name="package-your-pwa-for-the-store"></a>打包PWA应用商店 

现在你已拥有应用发布信息，请为Windows生成一个PWA。

若要生成应用包，请完成以下操作。  

1.  导航到[PWA生成器"][PwabuilderMain]。  
1.  键入您的 PWA。  
1.  Choose **Start**  >  **Build My PWA**  >  **Windows**  >  **Options**.  
1.  粘贴你在创建应用预订 [部分中保存的以下](#create-an-app-reservation) 值。  
    *   **程序包 ID**  
    *   **发布者 ID**  
    *   **Publisher显示名称**  
        
    :::image type="complex" source="./media/pwabuilder-publisher-info.msft.png" alt-text="将发布者信息粘贴到 PWABuilder 中" lightbox="./media/pwabuilder-publisher-info.msft.png":::
       将发布者信息粘贴到 PWABuilder 中  
    :::image-end:::  
    
1.  选择"**完成"。**  
1.  若要下载应用Windows程序包，请选择"下载 **"。**

下载的内容 `.zip` 是包含文件和 `.msixbundle` 文件的 `.classic.appxbundle` 存档。  这两个应用包PWA各种应用包上的Windows运行。  有关详细信息，请导航到什么是[经典程序包？。][GithubPwaBuilderPwabuilderWindowsChromiumDocsClassicPackageMd]  

### <a name="submit-your-app-package-to-the-store"></a>将应用包提交到应用商店  

若要将应用提交到应用商店，请完成以下操作。  

1.  导航到[Windows中心][MicrosoftPartnerDashboardWindowsOverview] 
1.  选择你的应用。  
1.  选择 **"开始提交"。**  
    
    :::image type="complex" source="./media/windows-partner-center-start-submission.msft.png" alt-text="在合作伙伴中心上开始Windows应用提交" lightbox="./media/windows-partner-center-start-submission.msft.png":::
       在合作伙伴中心上开始Windows应用提交  
    :::image-end:::  
    
1.  完成以下提示，获取有关应用的信息。
    *   pricing  
    *   年龄分级  
    *   和更多信息  
        
1.  在**程序包提示**符上，选择 和 你在打包你的程序包PWA `.msixbundle` `.classic.appxbundle` 文件。 [](#package-your-pwa-for-the-store)  
    
完成提交后，通常会在 24 至 48 小时内查看你的应用。  收到批准后，PWA中将Microsoft Store。  

### <a name="measure-usage-of-your-store-installed-pwa"></a>测量应用商店安装的应用商店的使用情况PWA

初始PWA时，如果 PWA 从 Microsoft Store 安装，Microsoft Edge 将包含以下标头，其中包含对 Web 应用第一次导航的请求。 `Referer`

```
Referer: app-info://platform/microsoft-store
```

使用此功能可测量与应用商店安装版本不同的PWA。  根据流量，你可以调整应用内容以改进用户体验。  客户端和服务器代码均可访问此功能。

此功能是在版本 91 Microsoft Edge引入的。

## <a name="see-also"></a>另请参阅  

PWABuilder 提供了更多文档，可帮助你PWA文档Microsoft Store。  

*   [测试和提交你的PWA包][GithubPwaBuilderPwabuilderWindowsChromiumDocsNextStepsMd]  
*   [将新PWA发布到应用商店][GithubPwaBuilderPwabuilderWindowsChromiumDocsPublishNewAppMd]  
*   [将现有应用商店应用更新到PWA][GithubPwaBuilderPwabuilderWindowsChromiumDocsUpdateExistingAppMd]  
*   [应用商店中 PBA 的图像建议][GithubPwaBuilderPwabuilderWindowsChromiumDocsImageRecommendationsMd]  
*   [应用打包解释器][GithubPwaBuilderPwabuilderWindowsChromiumDocsClassicPackageMd]  

<!-- links -->  

[LegalWindowsAgreementsStorePolicies]: /legal/windows/agreements/store-policies "Microsoft Store策略|Microsoft Docs"  

[WindowsUwpPublishAnalytics]: /windows/uwp/publish/analytics "分析应用性能|Microsoft Docs"  
[WindowsUwpPublishAppScreenshotsImages]: /windows/uwp/publish/app-screenshots-and-images "应用屏幕截图、图像和预告片|Microsoft Docs"  
[WindowsUwpPublishIndex]: /windows/uwp/publish/index "发布Windows应用和游戏|Microsoft Docs"  

[MicrosoftPartnerDashboardHome]: https://partner.microsoft.com/dashboard/home "家庭|Microsoft 合作伙伴中心"  
[MicrosoftPartnerDashboardWindowsOverview]: https://partner.microsoft.com/dashboard/windows/overview "合作伙伴资源|Microsoft 合作伙伴中心"  

[MicrosoftStoreAppsWindows]: https://www.microsoft.com/store/apps/windows "Windows应用|Microsoft Store"  

[WindowsBlogWindowsdeveloperHostedAppModel]: https://blogs.windows.com/windowsdeveloper/hosted-app-model "托管的应用模型|Windows开发人员博客"  

[GithubPwaBuilderPwabuilderWindowsChromiumDocsClassicPackageMd]: https://github.com/pwa-builder/pwabuilder-windows-chromium-docs/blob/master/classic-package.md "什么是经典程序包？|GitHub"  
[GithubPwaBuilderPwabuilderWindowsChromiumDocsImageRecommendationsMd]: https://github.com/pwa-builder/pwabuilder-windows-chromium-docs/blob/master/image-recommendations.md "程序包包Windows PWA图像|GitHub"  
[GithubPwaBuilderPwabuilderWindowsChromiumDocsNextStepsMd]: https://github.com/pwa-builder/pwabuilder-windows-chromium-docs/blob/master/next-steps.md "将你的应用程序PWA步骤Microsoft Store |GitHub"  
[GithubPwaBuilderPwabuilderWindowsChromiumDocsPublishNewAppMd]: https://github.com/pwa-builder/pwabuilder-windows-chromium-docs/blob/master/publish-new-app.md "将新应用发布到应用商店|GitHub"  
[GithubPwaBuilderPwabuilderWindowsChromiumDocsUpdateExistingAppMd]: https://github.com/pwa-builder/pwabuilder-windows-chromium-docs/blob/master/update-existing-app.md "更新应用商店应用中的现有|GitHub"  

[PwabuilderMain]: https://www.pwabuilder.com "PWABuilder"  
