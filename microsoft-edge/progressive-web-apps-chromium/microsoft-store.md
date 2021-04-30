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
# <a name="publish-your-progressive-web-app-to-the-microsoft-store"></a><span data-ttu-id="9a5ef-104">将渐进式 Web 应用发布到 Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="9a5ef-104">Publish your Progressive Web App to the Microsoft Store</span></span>  

<span data-ttu-id="9a5ef-105">将渐进式 Web 应用 \ (PWA\) 发布到 [Microsoft Store][WindowsUwpPublishIndex] 具有以下优点。</span><span class="sxs-lookup"><span data-stu-id="9a5ef-105">Publishing your Progressive Web App \(PWA\) to the [Microsoft Store][WindowsUwpPublishIndex] brings the following advantages.</span></span>  

:::row:::
   :::column span="1":::
      **<span data-ttu-id="9a5ef-106">可发现性</span><span class="sxs-lookup"><span data-stu-id="9a5ef-106">Discoverability</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="9a5ef-107">用户自然地在应用商店中查找应用。</span><span class="sxs-lookup"><span data-stu-id="9a5ef-107">Users naturally look for apps in the app store.</span></span>  <span data-ttu-id="9a5ef-108">当你发布到 Microsoft Store 时，数百万 Windows 用户可能会发现 PWA 与其他 Windows 应用一起。</span><span class="sxs-lookup"><span data-stu-id="9a5ef-108">When you publish to the Microsoft Store, millions of Windows users may discover your PWA alongside other Windows apps.</span></span>  <span data-ttu-id="9a5ef-109">应用商店通过类别、已选择的集合等展示应用。</span><span class="sxs-lookup"><span data-stu-id="9a5ef-109">The Store showcases apps through categories, curated collections, and more.</span></span>  <span data-ttu-id="9a5ef-110">应用发现门户为应用的潜在用户提供轻松的浏览和购物体验。</span><span class="sxs-lookup"><span data-stu-id="9a5ef-110">The app discovery portals provide an easy browsing and shopping experience for potential users of your app.</span></span>  <span data-ttu-id="9a5ef-111">你甚至可以 [使用屏幕截图、Hero][WindowsUwpPublishAppScreenshotsImages] 图像和视频预告片增强应用商店一览。</span><span class="sxs-lookup"><span data-stu-id="9a5ef-111">You may even [enhance your Store listing][WindowsUwpPublishAppScreenshotsImages] with screenshots, a hero image, and video trailers.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="9a5ef-112">Trustiness</span><span class="sxs-lookup"><span data-stu-id="9a5ef-112">Trustworthiness</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="9a5ef-113">Windows 客户知道他们可能会信任其 Microsoft Store 购买和下载，因为他们遵守严格的 Microsoft [质量和安全标准][LegalWindowsAgreementsStorePolicies]。</span><span class="sxs-lookup"><span data-stu-id="9a5ef-113">Windows customers know they may trust their Microsoft Store purchases and downloads, because they adhere to the rigorous Microsoft [quality and safety standards][LegalWindowsAgreementsStorePolicies].</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="9a5ef-114">易于安装</span><span class="sxs-lookup"><span data-stu-id="9a5ef-114">Easy install</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="9a5ef-115">Microsoft Store 在所有 [Windows 10][MicrosoftStoreAppsWindows]应用中提供一致且用户友好的安装体验。</span><span class="sxs-lookup"><span data-stu-id="9a5ef-115">The Microsoft Store provides a consistent and user-friendly install experience across [all Windows 10 apps][MicrosoftStoreAppsWindows].</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="9a5ef-116">应用分析</span><span class="sxs-lookup"><span data-stu-id="9a5ef-116">App analytics</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="9a5ef-117">[Windows 合作伙伴中心仪表板][WindowsUwpPublishIndex]提供有关应用[运行状况、][WindowsUwpPublishAnalytics]使用情况等的详细分析。</span><span class="sxs-lookup"><span data-stu-id="9a5ef-117">The [Windows Partner Center dashboard][WindowsUwpPublishIndex] provides you with [detailed analytics][WindowsUwpPublishAnalytics] about your app health, usage, and more.</span></span>  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="9a5ef-118">若要将 PWA 发布到 Microsoft Store，无需更改代码。</span><span class="sxs-lookup"><span data-stu-id="9a5ef-118">To publish your PWA to the Microsoft Store, no code changes are required.</span></span>  <span data-ttu-id="9a5ef-119">相反，你可以创建应用预订、打包 PWA，以及将程序包提交到应用商店。</span><span class="sxs-lookup"><span data-stu-id="9a5ef-119">Instead, you create an app reservation, package your PWA, and submit your package to the Store.</span></span>  <span data-ttu-id="9a5ef-120">以下各节将介绍这些步骤。</span><span class="sxs-lookup"><span data-stu-id="9a5ef-120">The following sections explain the steps.</span></span>   

## <a name="create-an-app-reservation"></a><span data-ttu-id="9a5ef-121">创建应用预订</span><span class="sxs-lookup"><span data-stu-id="9a5ef-121">Create an app reservation</span></span>  

<span data-ttu-id="9a5ef-122">[Windows 合作伙伴][MicrosoftPartnerDashboardWindowsOverview] 中心是你将应用提交到 Microsoft Store 的中心。</span><span class="sxs-lookup"><span data-stu-id="9a5ef-122">[Windows Partner Center][MicrosoftPartnerDashboardWindowsOverview] is the hub for you to submit your app to the Microsoft Store.</span></span>  

<span data-ttu-id="9a5ef-123">若要创建应用预订，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="9a5ef-123">To create an app reservation, complete the following actions.</span></span>  

1.  <span data-ttu-id="9a5ef-124">若要显示已注册的计划，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="9a5ef-124">To display your enrolled programs, complete the following actions.</span></span>  
    1.  <span data-ttu-id="9a5ef-125">使用你的 Microsoft 帐户登录到 Windows 合作伙伴中心，然后导航到合作伙伴 [中心仪表板][MicrosoftPartnerDashboardHome]。</span><span class="sxs-lookup"><span data-stu-id="9a5ef-125">Sign into Windows Partner Center with your Microsoft account and navigate to the [Partner Center Dashboard][MicrosoftPartnerDashboardHome].</span></span>  
    1.  <span data-ttu-id="9a5ef-126">导航到 **Windows & Xbox**</span><span class="sxs-lookup"><span data-stu-id="9a5ef-126">Navigate to **Windows & Xbox**</span></span>  
        *   <span data-ttu-id="9a5ef-127">如果 **显示 Windows &** Xbox，则应用已注册。</span><span class="sxs-lookup"><span data-stu-id="9a5ef-127">If **Windows & Xbox** is displayed, your app is already enrolled.</span></span>  
        *   <span data-ttu-id="9a5ef-128">如果未**显示 Windows & Xbox，** 请选择"**添加程序"。**</span><span class="sxs-lookup"><span data-stu-id="9a5ef-128">If **Windows & Xbox** isn't displayed, choose **Add program**.</span></span>  
    
    :::image type="complex" source="./media/windows-partner-center-add-program.msft.png" alt-text="在 Windows 合作伙伴中心仪表板中添加计划" lightbox="./media/windows-partner-center-add-program.msft.png":::
       <span data-ttu-id="9a5ef-130">在 Windows 合作伙伴中心仪表板中添加计划</span><span class="sxs-lookup"><span data-stu-id="9a5ef-130">Add a program in the Windows Partner Center dashboard</span></span>
    :::image-end:::  
    
1.  <span data-ttu-id="9a5ef-131">若要注册开发人员计划，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="9a5ef-131">To enroll in the developer program, complete the following actions.</span></span>  
    1.  <span data-ttu-id="9a5ef-132">导航到**Windows & Xbox。**</span><span class="sxs-lookup"><span data-stu-id="9a5ef-132">Navigate to **Windows & Xbox**.</span></span>  
    1.  <span data-ttu-id="9a5ef-133">选择 **"开始使用"。**</span><span class="sxs-lookup"><span data-stu-id="9a5ef-133">Choose **Get started**.</span></span>  
    1.  <span data-ttu-id="9a5ef-134">请按照提示操作。</span><span class="sxs-lookup"><span data-stu-id="9a5ef-134">Follow the prompts.</span></span>  
1.  <span data-ttu-id="9a5ef-135">现在，你的帐户已注册应用开发人员计划。</span><span class="sxs-lookup"><span data-stu-id="9a5ef-135">Now, your account is enrolled in the app developer program.</span></span> <span data-ttu-id="9a5ef-136">若要创建应用预订，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="9a5ef-136">To create an app reservation, complete the following actions.</span></span>  
    1.  <span data-ttu-id="9a5ef-137">导航到**Windows & Xbox。**</span><span class="sxs-lookup"><span data-stu-id="9a5ef-137">Navigate to **Windows & Xbox**.</span></span>  
    1.  <span data-ttu-id="9a5ef-138">选择 **"**  >  **概述""新建应用"。**</span><span class="sxs-lookup"><span data-stu-id="9a5ef-138">Choose **Overview** > **Create a new app**.</span></span>  
    1.  <span data-ttu-id="9a5ef-139">在提示符中键入应用的名称。</span><span class="sxs-lookup"><span data-stu-id="9a5ef-139">Type the name of your app in the prompt.</span></span>  
    1.  <span data-ttu-id="9a5ef-140">选择`Reserve product name`。</span><span class="sxs-lookup"><span data-stu-id="9a5ef-140">Choose `Reserve product name`.</span></span>  
        
    :::image type="complex" source="./media/windows-partner-center-create-app.msft.png" alt-text="在 Windows 合作伙伴中心创建应用预订" lightbox="./media/windows-partner-center-create-app.msft.png":::
       <span data-ttu-id="9a5ef-142">在 Windows 合作伙伴中心创建应用预订</span><span class="sxs-lookup"><span data-stu-id="9a5ef-142">Create an app reservation in Windows Partner Center</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9a5ef-143">若要在"打包[PWA"](#package-your-pwa-for-the-store)部分显示要使用的发布者详细信息，请选择"**产品管理**""  >  **产品标识"。**</span><span class="sxs-lookup"><span data-stu-id="9a5ef-143">To display your publisher details for use in the [Package your PWA](#package-your-pwa-for-the-store) section, choose **Product management** > **Product Identity**.</span></span>  
    
    :::image type="complex" source="./media/windows-partner-center-publisher-info.msft.png" alt-text="从 Windows 合作伙伴中心复制发布者信息" lightbox="./media/windows-partner-center-publisher-info.msft.png":::
       <span data-ttu-id="9a5ef-145">从 Windows 合作伙伴中心复制发布者信息</span><span class="sxs-lookup"><span data-stu-id="9a5ef-145">Copy your publisher information from Windows Partner Center</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9a5ef-146">复制并保存以下值。</span><span class="sxs-lookup"><span data-stu-id="9a5ef-146">Copy and save the following values.</span></span>  
    *   **<span data-ttu-id="9a5ef-147">程序包 ID</span><span class="sxs-lookup"><span data-stu-id="9a5ef-147">Package ID</span></span>**  
    *   **<span data-ttu-id="9a5ef-148">发布者 ID</span><span class="sxs-lookup"><span data-stu-id="9a5ef-148">Publisher ID</span></span>**  
    *   **<span data-ttu-id="9a5ef-149">发布者显示名称</span><span class="sxs-lookup"><span data-stu-id="9a5ef-149">Publisher Display Name</span></span>**  
        
## <a name="package-your-pwa-for-the-store"></a><span data-ttu-id="9a5ef-150">打包适用于应用商店的 PWA</span><span class="sxs-lookup"><span data-stu-id="9a5ef-150">Package your PWA for the Store</span></span> 

<span data-ttu-id="9a5ef-151">现在你已拥有应用发布信息，请为 PWA 生成一个 Windows 应用包。</span><span class="sxs-lookup"><span data-stu-id="9a5ef-151">Now that you have your app publishing information, generate a Windows app package for your PWA.</span></span>

<span data-ttu-id="9a5ef-152">若要生成应用包，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="9a5ef-152">To generate an app package, complete the following actions.</span></span>  

1.  <span data-ttu-id="9a5ef-153">导航到 [PWA 生成器][PwabuilderMain]。</span><span class="sxs-lookup"><span data-stu-id="9a5ef-153">Navigate to [PWA Builder][PwabuilderMain].</span></span>  
1.  <span data-ttu-id="9a5ef-154">键入 PWA 的 URL。</span><span class="sxs-lookup"><span data-stu-id="9a5ef-154">Type the URL of your PWA.</span></span>  
1.  <span data-ttu-id="9a5ef-155">选择 **"开始**  >  **生成我的 PWA**  >  **Windows**  >  **选项"。**</span><span class="sxs-lookup"><span data-stu-id="9a5ef-155">Choose **Start** > **Build My PWA** > **Windows** > **Options**.</span></span>  
1.  <span data-ttu-id="9a5ef-156">粘贴你在创建应用预订 [部分中保存的以下](#create-an-app-reservation) 值。</span><span class="sxs-lookup"><span data-stu-id="9a5ef-156">Paste the following values that you saved in the [Create an app reservation](#create-an-app-reservation) section.</span></span>  
    *   **<span data-ttu-id="9a5ef-157">程序包 ID</span><span class="sxs-lookup"><span data-stu-id="9a5ef-157">Package ID</span></span>**  
    *   **<span data-ttu-id="9a5ef-158">发布者 ID</span><span class="sxs-lookup"><span data-stu-id="9a5ef-158">Publisher ID</span></span>**  
    *   **<span data-ttu-id="9a5ef-159">发布者显示名称</span><span class="sxs-lookup"><span data-stu-id="9a5ef-159">Publisher Display Name</span></span>**  
        
    :::image type="complex" source="./media/pwabuilder-publisher-info.msft.png" alt-text="将发布者信息粘贴到 PWABuilder 中" lightbox="./media/pwabuilder-publisher-info.msft.png":::
       <span data-ttu-id="9a5ef-161">将发布者信息粘贴到 PWABuilder 中</span><span class="sxs-lookup"><span data-stu-id="9a5ef-161">Paste publisher information into PWABuilder</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9a5ef-162">选择"**完成"。**</span><span class="sxs-lookup"><span data-stu-id="9a5ef-162">Choose **Done**.</span></span>  
1.  <span data-ttu-id="9a5ef-163">若要下载 Windows 应用包，请选择"下载 **"。**</span><span class="sxs-lookup"><span data-stu-id="9a5ef-163">To download your Windows app package, choose **Download**.</span></span>

<span data-ttu-id="9a5ef-164">下载的内容 `.zip` 是包含文件和 `.msixbundle` 文件的 `.classic.appxbundle` 存档。</span><span class="sxs-lookup"><span data-stu-id="9a5ef-164">Your download is a `.zip` archive that contains an `.msixbundle` file and a `.classic.appxbundle` file.</span></span>  <span data-ttu-id="9a5ef-165">这两个应用程序包允许 PWA 在多种 Windows 版本上运行。</span><span class="sxs-lookup"><span data-stu-id="9a5ef-165">The two app packages allow your PWA to run on a wide variety of Windows versions.</span></span>  <span data-ttu-id="9a5ef-166">有关详细信息，请导航到什么是[经典程序包？。][GithubPwaBuilderPwabuilderWindowsChromiumDocsClassicPackageMd]</span><span class="sxs-lookup"><span data-stu-id="9a5ef-166">For more information, navigate to [What is a classic package?][GithubPwaBuilderPwabuilderWindowsChromiumDocsClassicPackageMd].</span></span>  

### <a name="submit-your-app-package-to-the-store"></a><span data-ttu-id="9a5ef-167">将应用包提交到应用商店</span><span class="sxs-lookup"><span data-stu-id="9a5ef-167">Submit your app package to the Store</span></span>  

<span data-ttu-id="9a5ef-168">若要将应用提交到应用商店，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="9a5ef-168">To submit your app to the Store, complete the following actions.</span></span>  

1.  <span data-ttu-id="9a5ef-169">导航到 [Windows 合作伙伴中心][MicrosoftPartnerDashboardWindowsOverview]</span><span class="sxs-lookup"><span data-stu-id="9a5ef-169">Navigate to [Windows Partner Center][MicrosoftPartnerDashboardWindowsOverview]</span></span> 
1.  <span data-ttu-id="9a5ef-170">选择你的应用。</span><span class="sxs-lookup"><span data-stu-id="9a5ef-170">Choose your app.</span></span>  
1.  <span data-ttu-id="9a5ef-171">选择 **"开始提交"。**</span><span class="sxs-lookup"><span data-stu-id="9a5ef-171">Choose **Start your Submission**.</span></span>  
    
    :::image type="complex" source="./media/windows-partner-center-start-submission.msft.png" alt-text="在 Windows 合作伙伴中心上启动新应用提交" lightbox="./media/windows-partner-center-start-submission.msft.png":::
       <span data-ttu-id="9a5ef-173">在 Windows 合作伙伴中心上启动新应用提交</span><span class="sxs-lookup"><span data-stu-id="9a5ef-173">Start a new app submission on Windows Partner Center</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9a5ef-174">完成以下提示，获取有关应用的信息。</span><span class="sxs-lookup"><span data-stu-id="9a5ef-174">Complete the following prompts for information about your app.</span></span>
    *   <span data-ttu-id="9a5ef-175">pricing</span><span class="sxs-lookup"><span data-stu-id="9a5ef-175">pricing</span></span>  
    *   <span data-ttu-id="9a5ef-176">年龄分级</span><span class="sxs-lookup"><span data-stu-id="9a5ef-176">age rating</span></span>  
    *   <span data-ttu-id="9a5ef-177">和更多信息</span><span class="sxs-lookup"><span data-stu-id="9a5ef-177">and more</span></span>  
        
1.  <span data-ttu-id="9a5ef-178">在 **"程序包"** 提示符下，选择 在 `.msixbundle` `.classic.appxbundle` "打包 [PWA"](#package-your-pwa-for-the-store) 部分生成的 和 文件。</span><span class="sxs-lookup"><span data-stu-id="9a5ef-178">On the **Packages** prompt, choose the `.msixbundle` and the `.classic.appxbundle` files you generated in the [Package your PWA](#package-your-pwa-for-the-store) section.</span></span>  
    
<span data-ttu-id="9a5ef-179">完成提交后，通常会在 24 至 48 小时内查看你的应用。</span><span class="sxs-lookup"><span data-stu-id="9a5ef-179">After you complete your submission, your app is reviewed, typically within between 24 and 48 hours.</span></span>  <span data-ttu-id="9a5ef-180">收到批准后，PWA 将在 Microsoft Store 中提供。</span><span class="sxs-lookup"><span data-stu-id="9a5ef-180">After you receive approval, your PWA is available in the Microsoft Store.</span></span>  

## <a name="see-also"></a><span data-ttu-id="9a5ef-181">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9a5ef-181">See also</span></span>  

<span data-ttu-id="9a5ef-182">PWABuilder 提供了更多文档，可帮助你在 Microsoft Store 中获取 PWA。</span><span class="sxs-lookup"><span data-stu-id="9a5ef-182">PWABuilder provides more documentation to help you get your PWA in the Microsoft Store.</span></span>  

*   [<span data-ttu-id="9a5ef-183">测试和提交 PWA 应用包</span><span class="sxs-lookup"><span data-stu-id="9a5ef-183">Test and submit your PWA app package</span></span>][GithubPwaBuilderPwabuilderWindowsChromiumDocsNextStepsMd]  
*   [<span data-ttu-id="9a5ef-184">将新的 PWA 发布到应用商店</span><span class="sxs-lookup"><span data-stu-id="9a5ef-184">Publish a new PWA to the Store</span></span>][GithubPwaBuilderPwabuilderWindowsChromiumDocsPublishNewAppMd]  
*   [<span data-ttu-id="9a5ef-185">将现有应用商店应用更新到 PWA</span><span class="sxs-lookup"><span data-stu-id="9a5ef-185">Update an existing Store app to a PWA</span></span>][GithubPwaBuilderPwabuilderWindowsChromiumDocsUpdateExistingAppMd]  
*   [<span data-ttu-id="9a5ef-186">应用商店中 PBA 的图像建议</span><span class="sxs-lookup"><span data-stu-id="9a5ef-186">Image recommendations for PWAs in the Store</span></span>][GithubPwaBuilderPwabuilderWindowsChromiumDocsImageRecommendationsMd]  
*   [<span data-ttu-id="9a5ef-187">应用打包解释器</span><span class="sxs-lookup"><span data-stu-id="9a5ef-187">App packaging explainer</span></span>][GithubPwaBuilderPwabuilderWindowsChromiumDocsClassicPackageMd]  

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
