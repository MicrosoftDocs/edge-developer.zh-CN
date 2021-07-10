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
# <a name="publish-your-progressive-web-app-to-the-microsoft-store"></a><span data-ttu-id="8d032-104">将渐进式 Web 应用发布到Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="8d032-104">Publish your Progressive Web App to the Microsoft Store</span></span>  

<span data-ttu-id="8d032-105">将渐进式 Web 应用 \ (PWA\) 发布到[Microsoft Store具有下列][WindowsUwpPublishIndex]优点。</span><span class="sxs-lookup"><span data-stu-id="8d032-105">Publishing your Progressive Web App \(PWA\) to the [Microsoft Store][WindowsUwpPublishIndex] brings the following advantages.</span></span>  

:::row:::
   :::column span="1":::
      **<span data-ttu-id="8d032-106">可发现性</span><span class="sxs-lookup"><span data-stu-id="8d032-106">Discoverability</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="8d032-107">用户自然地在应用商店中查找应用。</span><span class="sxs-lookup"><span data-stu-id="8d032-107">Users naturally look for apps in the app store.</span></span>  <span data-ttu-id="8d032-108">当你发布到应用Microsoft Store，Windows数百万PWA发现你的Windows应用。</span><span class="sxs-lookup"><span data-stu-id="8d032-108">When you publish to the Microsoft Store, millions of Windows users may discover your PWA alongside other Windows apps.</span></span>  <span data-ttu-id="8d032-109">应用商店通过类别、已选择的集合等展示应用。</span><span class="sxs-lookup"><span data-stu-id="8d032-109">The Store showcases apps through categories, curated collections, and more.</span></span>  <span data-ttu-id="8d032-110">应用发现门户为应用的潜在用户提供轻松的浏览和购物体验。</span><span class="sxs-lookup"><span data-stu-id="8d032-110">The app discovery portals provide an easy browsing and shopping experience for potential users of your app.</span></span>  <span data-ttu-id="8d032-111">你甚至可以 [使用屏幕截图、Hero][WindowsUwpPublishAppScreenshotsImages] 图像和视频预告片增强应用商店一览。</span><span class="sxs-lookup"><span data-stu-id="8d032-111">You may even [enhance your Store listing][WindowsUwpPublishAppScreenshotsImages] with screenshots, a hero image, and video trailers.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="8d032-112">Trustiness</span><span class="sxs-lookup"><span data-stu-id="8d032-112">Trustworthiness</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="8d032-113">Windows客户知道他们可能会信任他们的Microsoft Store购买和下载，因为他们遵守严格的 Microsoft[质量和安全标准][LegalWindowsAgreementsStorePolicies]。</span><span class="sxs-lookup"><span data-stu-id="8d032-113">Windows customers know they may trust their Microsoft Store purchases and downloads, because they adhere to the rigorous Microsoft [quality and safety standards][LegalWindowsAgreementsStorePolicies].</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="8d032-114">易于安装</span><span class="sxs-lookup"><span data-stu-id="8d032-114">Easy install</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="8d032-115">The Microsoft Store provides a consistent and user-friendly install experience across [all Windows 10 apps][MicrosoftStoreAppsWindows].</span><span class="sxs-lookup"><span data-stu-id="8d032-115">The Microsoft Store provides a consistent and user-friendly install experience across [all Windows 10 apps][MicrosoftStoreAppsWindows].</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="8d032-116">应用分析</span><span class="sxs-lookup"><span data-stu-id="8d032-116">App analytics</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="8d032-117">合作伙伴[Windows][WindowsUwpPublishIndex]仪表板提供了有关应用运行状况、使用情况等的详细分析[][WindowsUwpPublishAnalytics]。</span><span class="sxs-lookup"><span data-stu-id="8d032-117">The [Windows Partner Center dashboard][WindowsUwpPublishIndex] provides you with [detailed analytics][WindowsUwpPublishAnalytics] about your app health, usage, and more.</span></span>  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="8d032-118">若要将PWA发布到Microsoft Store，无需更改代码。</span><span class="sxs-lookup"><span data-stu-id="8d032-118">To publish your PWA to the Microsoft Store, no code changes are required.</span></span>  <span data-ttu-id="8d032-119">相反，你可以创建应用预订、打包PWA，然后提交到应用商店。</span><span class="sxs-lookup"><span data-stu-id="8d032-119">Instead, you create an app reservation, package your PWA, and submit your package to the Store.</span></span>  <span data-ttu-id="8d032-120">以下各节将介绍这些步骤。</span><span class="sxs-lookup"><span data-stu-id="8d032-120">The following sections explain the steps.</span></span>   

## <a name="create-an-app-reservation"></a><span data-ttu-id="8d032-121">创建应用预订</span><span class="sxs-lookup"><span data-stu-id="8d032-121">Create an app reservation</span></span>  

<span data-ttu-id="8d032-122">[Windows中心][MicrosoftPartnerDashboardWindowsOverview]是你将应用提交到应用中心Microsoft Store。</span><span class="sxs-lookup"><span data-stu-id="8d032-122">[Windows Partner Center][MicrosoftPartnerDashboardWindowsOverview] is the hub for you to submit your app to the Microsoft Store.</span></span>  

<span data-ttu-id="8d032-123">若要创建应用预订，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="8d032-123">To create an app reservation, complete the following actions.</span></span>  

1.  <span data-ttu-id="8d032-124">若要显示已注册的计划，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="8d032-124">To display your enrolled programs, complete the following actions.</span></span>  
    1.  <span data-ttu-id="8d032-125">使用 Microsoft Windows登录到合作伙伴中心，然后导航到合作伙伴[中心仪表板][MicrosoftPartnerDashboardHome]。</span><span class="sxs-lookup"><span data-stu-id="8d032-125">Sign into Windows Partner Center with your Microsoft account and navigate to the [Partner Center Dashboard][MicrosoftPartnerDashboardHome].</span></span>  
    1.  <span data-ttu-id="8d032-126">导航到**Windows & Xbox**</span><span class="sxs-lookup"><span data-stu-id="8d032-126">Navigate to **Windows & Xbox**</span></span>  
        *   <span data-ttu-id="8d032-127">如果**Windows & Xbox，** 则应用已注册。</span><span class="sxs-lookup"><span data-stu-id="8d032-127">If **Windows & Xbox** is displayed, your app is already enrolled.</span></span>  
        *   <span data-ttu-id="8d032-128">如果未**Windows & Xbox，** 请选择"添加**程序"。**</span><span class="sxs-lookup"><span data-stu-id="8d032-128">If **Windows & Xbox** isn't displayed, choose **Add program**.</span></span>  
    
    :::image type="complex" source="./media/windows-partner-center-add-program.msft.png" alt-text="在合作伙伴中心仪表板Windows计划" lightbox="./media/windows-partner-center-add-program.msft.png":::
       <span data-ttu-id="8d032-130">在合作伙伴中心仪表板Windows计划</span><span class="sxs-lookup"><span data-stu-id="8d032-130">Add a program in the Windows Partner Center dashboard</span></span>
    :::image-end:::  
    
1.  <span data-ttu-id="8d032-131">若要注册开发人员计划，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="8d032-131">To enroll in the developer program, complete the following actions.</span></span>  
    1.  <span data-ttu-id="8d032-132">导航到**Windows & Xbox。**</span><span class="sxs-lookup"><span data-stu-id="8d032-132">Navigate to **Windows & Xbox**.</span></span>  
    1.  <span data-ttu-id="8d032-133">选择 **"开始使用"。**</span><span class="sxs-lookup"><span data-stu-id="8d032-133">Choose **Get started**.</span></span>  
    1.  <span data-ttu-id="8d032-134">请按照提示操作。</span><span class="sxs-lookup"><span data-stu-id="8d032-134">Follow the prompts.</span></span>  
1.  <span data-ttu-id="8d032-135">现在，你的帐户已注册应用开发人员计划。</span><span class="sxs-lookup"><span data-stu-id="8d032-135">Now, your account is enrolled in the app developer program.</span></span> <span data-ttu-id="8d032-136">若要创建应用预订，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="8d032-136">To create an app reservation, complete the following actions.</span></span>  
    1.  <span data-ttu-id="8d032-137">导航到**Windows & Xbox。**</span><span class="sxs-lookup"><span data-stu-id="8d032-137">Navigate to **Windows & Xbox**.</span></span>  
    1.  <span data-ttu-id="8d032-138">选择 **"**  >  **概述""新建应用"。**</span><span class="sxs-lookup"><span data-stu-id="8d032-138">Choose **Overview** > **Create a new app**.</span></span>  
    1.  <span data-ttu-id="8d032-139">在提示符中键入应用的名称。</span><span class="sxs-lookup"><span data-stu-id="8d032-139">Type the name of your app in the prompt.</span></span>  
    1.  <span data-ttu-id="8d032-140">选择`Reserve product name`。</span><span class="sxs-lookup"><span data-stu-id="8d032-140">Choose `Reserve product name`.</span></span>  
        
    :::image type="complex" source="./media/windows-partner-center-create-app.msft.png" alt-text="在合作伙伴中心Windows应用预订" lightbox="./media/windows-partner-center-create-app.msft.png":::
       <span data-ttu-id="8d032-142">在合作伙伴中心Windows应用预订</span><span class="sxs-lookup"><span data-stu-id="8d032-142">Create an app reservation in Windows Partner Center</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="8d032-143">若要在"打包你的产品"[部分显示你的](#package-your-pwa-for-the-store)发布者PWA，**请选择"** 产品管理""  >  **产品标识"。**</span><span class="sxs-lookup"><span data-stu-id="8d032-143">To display your publisher details for use in the [Package your PWA](#package-your-pwa-for-the-store) section, choose **Product management** > **Product Identity**.</span></span>  
    
    :::image type="complex" source="./media/windows-partner-center-publisher-info.msft.png" alt-text="从合作伙伴中心复制Windows发布者信息" lightbox="./media/windows-partner-center-publisher-info.msft.png":::
       <span data-ttu-id="8d032-145">从合作伙伴中心复制Windows发布者信息</span><span class="sxs-lookup"><span data-stu-id="8d032-145">Copy your publisher information from Windows Partner Center</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="8d032-146">复制并保存以下值。</span><span class="sxs-lookup"><span data-stu-id="8d032-146">Copy and save the following values.</span></span>  
    *   **<span data-ttu-id="8d032-147">程序包 ID</span><span class="sxs-lookup"><span data-stu-id="8d032-147">Package ID</span></span>**  
    *   **<span data-ttu-id="8d032-148">发布者 ID</span><span class="sxs-lookup"><span data-stu-id="8d032-148">Publisher ID</span></span>**  
    *   **<span data-ttu-id="8d032-149">Publisher显示名称</span><span class="sxs-lookup"><span data-stu-id="8d032-149">Publisher Display Name</span></span>**  
        
## <a name="package-your-pwa-for-the-store"></a><span data-ttu-id="8d032-150">打包PWA应用商店</span><span class="sxs-lookup"><span data-stu-id="8d032-150">Package your PWA for the Store</span></span> 

<span data-ttu-id="8d032-151">现在你已拥有应用发布信息，请为Windows生成一个PWA。</span><span class="sxs-lookup"><span data-stu-id="8d032-151">Now that you have your app publishing information, generate a Windows app package for your PWA.</span></span>

<span data-ttu-id="8d032-152">若要生成应用包，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="8d032-152">To generate an app package, complete the following actions.</span></span>  

1.  <span data-ttu-id="8d032-153">导航到[PWA生成器"][PwabuilderMain]。</span><span class="sxs-lookup"><span data-stu-id="8d032-153">Navigate to [PWA Builder][PwabuilderMain].</span></span>  
1.  <span data-ttu-id="8d032-154">键入您的 PWA。</span><span class="sxs-lookup"><span data-stu-id="8d032-154">Type the URL of your PWA.</span></span>  
1.  <span data-ttu-id="8d032-155">Choose **Start**  >  **Build My PWA**  >  **Windows**  >  **Options**.</span><span class="sxs-lookup"><span data-stu-id="8d032-155">Choose **Start** > **Build My PWA** > **Windows** > **Options**.</span></span>  
1.  <span data-ttu-id="8d032-156">粘贴你在创建应用预订 [部分中保存的以下](#create-an-app-reservation) 值。</span><span class="sxs-lookup"><span data-stu-id="8d032-156">Paste the following values that you saved in the [Create an app reservation](#create-an-app-reservation) section.</span></span>  
    *   **<span data-ttu-id="8d032-157">程序包 ID</span><span class="sxs-lookup"><span data-stu-id="8d032-157">Package ID</span></span>**  
    *   **<span data-ttu-id="8d032-158">发布者 ID</span><span class="sxs-lookup"><span data-stu-id="8d032-158">Publisher ID</span></span>**  
    *   **<span data-ttu-id="8d032-159">Publisher显示名称</span><span class="sxs-lookup"><span data-stu-id="8d032-159">Publisher Display Name</span></span>**  
        
    :::image type="complex" source="./media/pwabuilder-publisher-info.msft.png" alt-text="将发布者信息粘贴到 PWABuilder 中" lightbox="./media/pwabuilder-publisher-info.msft.png":::
       <span data-ttu-id="8d032-161">将发布者信息粘贴到 PWABuilder 中</span><span class="sxs-lookup"><span data-stu-id="8d032-161">Paste publisher information into PWABuilder</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="8d032-162">选择"**完成"。**</span><span class="sxs-lookup"><span data-stu-id="8d032-162">Choose **Done**.</span></span>  
1.  <span data-ttu-id="8d032-163">若要下载应用Windows程序包，请选择"下载 **"。**</span><span class="sxs-lookup"><span data-stu-id="8d032-163">To download your Windows app package, choose **Download**.</span></span>

<span data-ttu-id="8d032-164">下载的内容 `.zip` 是包含文件和 `.msixbundle` 文件的 `.classic.appxbundle` 存档。</span><span class="sxs-lookup"><span data-stu-id="8d032-164">Your download is a `.zip` archive that contains an `.msixbundle` file and a `.classic.appxbundle` file.</span></span>  <span data-ttu-id="8d032-165">这两个应用包PWA各种应用包上的Windows运行。</span><span class="sxs-lookup"><span data-stu-id="8d032-165">The two app packages allow your PWA to run on a wide variety of Windows versions.</span></span>  <span data-ttu-id="8d032-166">有关详细信息，请导航到什么是[经典程序包？。][GithubPwaBuilderPwabuilderWindowsChromiumDocsClassicPackageMd]</span><span class="sxs-lookup"><span data-stu-id="8d032-166">For more information, navigate to [What is a classic package?][GithubPwaBuilderPwabuilderWindowsChromiumDocsClassicPackageMd].</span></span>  

### <a name="submit-your-app-package-to-the-store"></a><span data-ttu-id="8d032-167">将应用包提交到应用商店</span><span class="sxs-lookup"><span data-stu-id="8d032-167">Submit your app package to the Store</span></span>  

<span data-ttu-id="8d032-168">若要将应用提交到应用商店，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="8d032-168">To submit your app to the Store, complete the following actions.</span></span>  

1.  <span data-ttu-id="8d032-169">导航到[Windows中心][MicrosoftPartnerDashboardWindowsOverview]</span><span class="sxs-lookup"><span data-stu-id="8d032-169">Navigate to [Windows Partner Center][MicrosoftPartnerDashboardWindowsOverview]</span></span> 
1.  <span data-ttu-id="8d032-170">选择你的应用。</span><span class="sxs-lookup"><span data-stu-id="8d032-170">Choose your app.</span></span>  
1.  <span data-ttu-id="8d032-171">选择 **"开始提交"。**</span><span class="sxs-lookup"><span data-stu-id="8d032-171">Choose **Start your Submission**.</span></span>  
    
    :::image type="complex" source="./media/windows-partner-center-start-submission.msft.png" alt-text="在合作伙伴中心上开始Windows应用提交" lightbox="./media/windows-partner-center-start-submission.msft.png":::
       <span data-ttu-id="8d032-173">在合作伙伴中心上开始Windows应用提交</span><span class="sxs-lookup"><span data-stu-id="8d032-173">Start a new app submission on Windows Partner Center</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="8d032-174">完成以下提示，获取有关应用的信息。</span><span class="sxs-lookup"><span data-stu-id="8d032-174">Complete the following prompts for information about your app.</span></span>
    *   <span data-ttu-id="8d032-175">pricing</span><span class="sxs-lookup"><span data-stu-id="8d032-175">pricing</span></span>  
    *   <span data-ttu-id="8d032-176">年龄分级</span><span class="sxs-lookup"><span data-stu-id="8d032-176">age rating</span></span>  
    *   <span data-ttu-id="8d032-177">和更多信息</span><span class="sxs-lookup"><span data-stu-id="8d032-177">and more</span></span>  
        
1.  <span data-ttu-id="8d032-178">在**程序包提示**符上，选择 和 你在打包你的程序包PWA `.msixbundle` `.classic.appxbundle` 文件。 [](#package-your-pwa-for-the-store)</span><span class="sxs-lookup"><span data-stu-id="8d032-178">On the **Packages** prompt, choose the `.msixbundle` and the `.classic.appxbundle` files you generated in the [Package your PWA](#package-your-pwa-for-the-store) section.</span></span>  
    
<span data-ttu-id="8d032-179">完成提交后，通常会在 24 至 48 小时内查看你的应用。</span><span class="sxs-lookup"><span data-stu-id="8d032-179">After you complete your submission, your app is reviewed, typically within between 24 and 48 hours.</span></span>  <span data-ttu-id="8d032-180">收到批准后，PWA中将Microsoft Store。</span><span class="sxs-lookup"><span data-stu-id="8d032-180">After you receive approval, your PWA is available in the Microsoft Store.</span></span>  

### <a name="measure-usage-of-your-store-installed-pwa"></a><span data-ttu-id="8d032-181">测量应用商店安装的应用商店的使用情况PWA</span><span class="sxs-lookup"><span data-stu-id="8d032-181">Measure usage of your Store-installed PWA</span></span>

<span data-ttu-id="8d032-182">初始PWA时，如果 PWA 从 Microsoft Store 安装，Microsoft Edge 将包含以下标头，其中包含对 Web 应用第一次导航的请求。 `Referer`</span><span class="sxs-lookup"><span data-stu-id="8d032-182">When your PWA is initially launched, if the PWA was installed from the Microsoft Store, Microsoft Edge includes the following `Referer` header with the request for the first navigation of your web app.</span></span>

```
Referer: app-info://platform/microsoft-store
```

<span data-ttu-id="8d032-183">使用此功能可测量与应用商店安装版本不同的PWA。</span><span class="sxs-lookup"><span data-stu-id="8d032-183">Use this feature to measure distinct traffic from your Store-installed PWA.</span></span>  <span data-ttu-id="8d032-184">根据流量，你可以调整应用内容以改进用户体验。</span><span class="sxs-lookup"><span data-stu-id="8d032-184">Based on the traffic, you can adjust your app’s content to improve the user experience.</span></span>  <span data-ttu-id="8d032-185">客户端和服务器代码均可访问此功能。</span><span class="sxs-lookup"><span data-stu-id="8d032-185">This feature is accessible to both client and server code.</span></span>

<span data-ttu-id="8d032-186">此功能是在版本 91 Microsoft Edge引入的。</span><span class="sxs-lookup"><span data-stu-id="8d032-186">This feature was introduced in Microsoft Edge version 91.</span></span>

## <a name="see-also"></a><span data-ttu-id="8d032-187">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8d032-187">See also</span></span>  

<span data-ttu-id="8d032-188">PWABuilder 提供了更多文档，可帮助你PWA文档Microsoft Store。</span><span class="sxs-lookup"><span data-stu-id="8d032-188">PWABuilder provides more documentation to help you get your PWA in the Microsoft Store.</span></span>  

*   [<span data-ttu-id="8d032-189">测试和提交你的PWA包</span><span class="sxs-lookup"><span data-stu-id="8d032-189">Test and submit your PWA app package</span></span>][GithubPwaBuilderPwabuilderWindowsChromiumDocsNextStepsMd]  
*   [<span data-ttu-id="8d032-190">将新PWA发布到应用商店</span><span class="sxs-lookup"><span data-stu-id="8d032-190">Publish a new PWA to the Store</span></span>][GithubPwaBuilderPwabuilderWindowsChromiumDocsPublishNewAppMd]  
*   [<span data-ttu-id="8d032-191">将现有应用商店应用更新到PWA</span><span class="sxs-lookup"><span data-stu-id="8d032-191">Update an existing Store app to a PWA</span></span>][GithubPwaBuilderPwabuilderWindowsChromiumDocsUpdateExistingAppMd]  
*   [<span data-ttu-id="8d032-192">应用商店中 PBA 的图像建议</span><span class="sxs-lookup"><span data-stu-id="8d032-192">Image recommendations for PWAs in the Store</span></span>][GithubPwaBuilderPwabuilderWindowsChromiumDocsImageRecommendationsMd]  
*   [<span data-ttu-id="8d032-193">应用打包解释器</span><span class="sxs-lookup"><span data-stu-id="8d032-193">App packaging explainer</span></span>][GithubPwaBuilderPwabuilderWindowsChromiumDocsClassicPackageMd]  

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
