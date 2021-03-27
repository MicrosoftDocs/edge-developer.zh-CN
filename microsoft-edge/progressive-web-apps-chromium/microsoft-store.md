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
# <a name="publish-your-progressive-web-app-to-the-microsoft-store"></a><span data-ttu-id="3172d-104">将渐进式 Web 应用发布到 Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="3172d-104">Publish your Progressive Web App to the Microsoft Store</span></span>  

<span data-ttu-id="3172d-105">将渐进式 Web 应用 \ (PWA\) 发布到 [Microsoft Store][WindowsUwpPublishIndex] 具有以下优点。</span><span class="sxs-lookup"><span data-stu-id="3172d-105">Publishing your Progressive Web App \(PWA\) to the [Microsoft Store][WindowsUwpPublishIndex] brings the following advantages.</span></span>  

:::row:::
   :::column span="1":::
      **<span data-ttu-id="3172d-106">可发现性</span><span class="sxs-lookup"><span data-stu-id="3172d-106">Discoverability</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="3172d-107">用户自然地在应用商店中查找应用。</span><span class="sxs-lookup"><span data-stu-id="3172d-107">Users naturally look for apps in the app store.</span></span>  <span data-ttu-id="3172d-108">通过发布到 Microsoft Store，数百万 Windows 用户可能会发现 PWA 与其他 Windows 应用一起。</span><span class="sxs-lookup"><span data-stu-id="3172d-108">By publishing to the Microsoft Store, millions of Windows users may discover your PWA alongside other Windows apps.</span></span>  <span data-ttu-id="3172d-109">应用商店通过类别、已选择的集合等展示应用。</span><span class="sxs-lookup"><span data-stu-id="3172d-109">The Store showcases apps through categories, curated collections, and more.</span></span>  <span data-ttu-id="3172d-110">应用发现门户为应用的潜在用户提供轻松的浏览和购物体验。</span><span class="sxs-lookup"><span data-stu-id="3172d-110">The app discovery portals provide an easy browsing and shopping experience for potential users of your app.</span></span>  <span data-ttu-id="3172d-111">你甚至可以 [使用屏幕截图、Hero][WindowsUwpPublishAppScreenshotsImages] 图像和视频预告片增强应用商店一览。</span><span class="sxs-lookup"><span data-stu-id="3172d-111">You may even [enhance your Store listing][WindowsUwpPublishAppScreenshotsImages] with screenshots, a hero image, and video trailers.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="3172d-112">Trustiness</span><span class="sxs-lookup"><span data-stu-id="3172d-112">Trustworthiness</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="3172d-113">Windows 客户知道他们可能会信任其 Microsoft Store 购买和下载，因为他们遵守严格的 Microsoft [质量和安全标准][LegalWindowsAgreementsStorePolicies]。</span><span class="sxs-lookup"><span data-stu-id="3172d-113">Windows customers know they may trust their Microsoft Store purchases and downloads, because they adhere to the rigorous Microsoft [quality and safety standards][LegalWindowsAgreementsStorePolicies].</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="3172d-114">易于安装</span><span class="sxs-lookup"><span data-stu-id="3172d-114">Easy install</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="3172d-115">Microsoft Store 在所有 [Windows 10][MicrosoftStoreAppsWindows]应用中提供一致且用户友好的安装体验。</span><span class="sxs-lookup"><span data-stu-id="3172d-115">The Microsoft Store provides a consistent and user-friendly install experience across [all Windows 10 apps][MicrosoftStoreAppsWindows].</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="3172d-116">应用分析</span><span class="sxs-lookup"><span data-stu-id="3172d-116">App analytics</span></span>**  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="3172d-117">[Windows 合作伙伴中心仪表板][WindowsUwpPublishIndex]提供有关应用[运行状况、][WindowsUwpPublishAnalytics]使用情况等的详细分析。</span><span class="sxs-lookup"><span data-stu-id="3172d-117">The [Windows Partner Center dashboard][WindowsUwpPublishIndex] provides you with [detailed analytics][WindowsUwpPublishAnalytics] about your app health, usage, and more.</span></span>  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="3172d-118">若要将 PWA 发布到 Microsoft Store，无需更改代码。</span><span class="sxs-lookup"><span data-stu-id="3172d-118">To publish your PWA to the Microsoft Store, no code changes are required.</span></span>  <span data-ttu-id="3172d-119">相反，你可以创建应用预订、打包 PWA，以及将程序包提交到应用商店。</span><span class="sxs-lookup"><span data-stu-id="3172d-119">Instead, you create an app reservation, package your PWA, and submit your package to the Store.</span></span>  <span data-ttu-id="3172d-120">以下各节将介绍这些步骤。</span><span class="sxs-lookup"><span data-stu-id="3172d-120">The following sections explain the steps.</span></span>   

## <a name="create-an-app-reservation"></a><span data-ttu-id="3172d-121">创建应用预订</span><span class="sxs-lookup"><span data-stu-id="3172d-121">Create an app reservation</span></span>  

<span data-ttu-id="3172d-122">[Windows 合作伙伴][MicrosoftPartnerDashboardWindowsOverview] 中心是你将应用提交到 Microsoft Store 的中心。</span><span class="sxs-lookup"><span data-stu-id="3172d-122">[Windows Partner Center][MicrosoftPartnerDashboardWindowsOverview] is the hub for you to submit your app to the Microsoft Store.</span></span>  

<span data-ttu-id="3172d-123">若要创建应用预订，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="3172d-123">To create an app reservation, complete the following actions.</span></span>  

1.  <span data-ttu-id="3172d-124">若要显示已注册的计划，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="3172d-124">To display your enrolled programs, complete the following actions.</span></span>  
    1.  <span data-ttu-id="3172d-125">使用你的 Microsoft 帐户登录到 Windows 合作伙伴中心，然后导航到合作伙伴 [中心仪表板][MicrosoftPartnerDashboardHome]。</span><span class="sxs-lookup"><span data-stu-id="3172d-125">Sign into Windows Partner Center with your Microsoft account and navigate to the [Partner Center Dashboard][MicrosoftPartnerDashboardHome].</span></span>  
    1.  <span data-ttu-id="3172d-126">导航到 **Windows & Xbox**</span><span class="sxs-lookup"><span data-stu-id="3172d-126">Navigate to **Windows & Xbox**</span></span>  
        *   <span data-ttu-id="3172d-127">如果 **显示 Windows &** Xbox，则应用已注册。</span><span class="sxs-lookup"><span data-stu-id="3172d-127">If **Windows & Xbox** is displayed, your app is already enrolled.</span></span>  
        *   <span data-ttu-id="3172d-128">如果未**显示 Windows & Xbox，** 请选择"**添加程序"。**</span><span class="sxs-lookup"><span data-stu-id="3172d-128">If **Windows & Xbox** isn't displayed, choose **Add program**.</span></span>  
    
    :::image type="complex" source="./media/windows-partner-center-add-program.msft.png" alt-text="在 Windows 合作伙伴中心仪表板中添加计划" lightbox="./media/windows-partner-center-add-program.msft.png":::
       <span data-ttu-id="3172d-130">在 Windows 合作伙伴中心仪表板中添加计划</span><span class="sxs-lookup"><span data-stu-id="3172d-130">Add a program in the Windows Partner Center dashboard</span></span>
    :::image-end:::  
    
1.  <span data-ttu-id="3172d-131">若要注册开发人员计划，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="3172d-131">To enroll in the developer program, complete the following actions.</span></span>  
    1.  <span data-ttu-id="3172d-132">导航到**Windows & Xbox。**</span><span class="sxs-lookup"><span data-stu-id="3172d-132">Navigate to **Windows & Xbox**.</span></span>  
    1.  <span data-ttu-id="3172d-133">选择 **"开始使用"。**</span><span class="sxs-lookup"><span data-stu-id="3172d-133">Choose **Get started**.</span></span>  
    1.  <span data-ttu-id="3172d-134">请按照提示操作。</span><span class="sxs-lookup"><span data-stu-id="3172d-134">Follow the prompts.</span></span>  
1.  <span data-ttu-id="3172d-135">现在，你的应用已注册应用开发人员计划。</span><span class="sxs-lookup"><span data-stu-id="3172d-135">Now, your app is enrolled in the app developer program.</span></span> <span data-ttu-id="3172d-136">若要创建应用预订，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="3172d-136">To create an app reservation, complete the following actions.</span></span>  
    1.  <span data-ttu-id="3172d-137">导航到**Windows & Xbox。**</span><span class="sxs-lookup"><span data-stu-id="3172d-137">Navigate to **Windows & Xbox**.</span></span>  
    1.  <span data-ttu-id="3172d-138">选择 **"**  >  **概述""新建应用"。**</span><span class="sxs-lookup"><span data-stu-id="3172d-138">Choose **Overview** > **Create a new app**.</span></span>  
    1.  <span data-ttu-id="3172d-139">在提示符中键入 PWA 名称。</span><span class="sxs-lookup"><span data-stu-id="3172d-139">Type your PWA name in the prompt.</span></span>  
    1.  <span data-ttu-id="3172d-140">选择`Reserve product name`。</span><span class="sxs-lookup"><span data-stu-id="3172d-140">Choose `Reserve product name`.</span></span>  
    
    :::image type="complex" source="./media/windows-partner-center-create-app.msft.png" alt-text="在 Windows 合作伙伴中心创建应用预订" lightbox="./media/windows-partner-center-create-app.msft.png":::
       <span data-ttu-id="3172d-142">在 Windows 合作伙伴中心创建应用预订</span><span class="sxs-lookup"><span data-stu-id="3172d-142">Create an app reservation in Windows Partner Center</span></span>  
    :::image-end:::  

1.  <span data-ttu-id="3172d-143">若要在"打包[PWA"](#package-your-pwa)部分显示要使用的发布者详细信息，请选择"**产品管理**""  >  **产品标识"。**</span><span class="sxs-lookup"><span data-stu-id="3172d-143">To display your publisher details for use in the [Package your PWA](#package-your-pwa) section, choose **Product management** > **Product Identity**.</span></span>  
    
    :::image type="complex" source="./media/windows-partner-center-publisher-info.msft.png" alt-text="从 Windows 合作伙伴中心复制发布者信息" lightbox="./media/windows-partner-center-publisher-info.msft.png":::
       <span data-ttu-id="3172d-145">从 Windows 合作伙伴中心复制发布者信息</span><span class="sxs-lookup"><span data-stu-id="3172d-145">Copy your publisher information from Windows Partner Center</span></span>  
    :::image-end:::  

1.  <span data-ttu-id="3172d-146">复制并保存以下值。</span><span class="sxs-lookup"><span data-stu-id="3172d-146">Copy and save the following values.</span></span>  
    *   **<span data-ttu-id="3172d-147">程序包 ID</span><span class="sxs-lookup"><span data-stu-id="3172d-147">Package ID</span></span>**  
    *   **<span data-ttu-id="3172d-148">发布者 ID</span><span class="sxs-lookup"><span data-stu-id="3172d-148">Publisher ID</span></span>**  
    *   **<span data-ttu-id="3172d-149">发布者显示名称</span><span class="sxs-lookup"><span data-stu-id="3172d-149">Publisher Display Name</span></span>**  
        
## <a name="package-your-pwa"></a><span data-ttu-id="3172d-150">打包 PWA</span><span class="sxs-lookup"><span data-stu-id="3172d-150">Package your PWA</span></span>  

<span data-ttu-id="3172d-151">为 PWA 生成 Windows 应用包。</span><span class="sxs-lookup"><span data-stu-id="3172d-151">Generate a Windows app package for your PWA.</span></span>  

<span data-ttu-id="3172d-152">应用包是包含应用元数据的文件，包括名称、说明、图标 `.msixbundle` 等。</span><span class="sxs-lookup"><span data-stu-id="3172d-152">Your app package is an `.msixbundle` file that contains the metadata of your app including the name, description, icons, and so on.</span></span>  <span data-ttu-id="3172d-153">它使用 [托管的应用程序模型，Microsoft][WindowsBlogWindowsdeveloperHostedAppModel]Edge 为 PWA 提供支持。</span><span class="sxs-lookup"><span data-stu-id="3172d-153">It uses the [Hosted App Model][WindowsBlogWindowsdeveloperHostedAppModel], with Microsoft Edge powering your PWA.</span></span>  <span data-ttu-id="3172d-154">在此模型中，PWA 在用作 Windows 应用的同时使用新式 Web 功能。</span><span class="sxs-lookup"><span data-stu-id="3172d-154">In this model, your PWA uses modern web capabilities while functioning as a Windows app.</span></span>  <span data-ttu-id="3172d-155">新式 Web 功能包括服务工作者、脱机、推送通知、保护等。</span><span class="sxs-lookup"><span data-stu-id="3172d-155">Modern web capabilities include service worker, offline, push notifications, badging, and more.</span></span>  

<span data-ttu-id="3172d-156">若要生成应用包，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="3172d-156">To generate an app package, complete the following actions.</span></span>  

1.  <span data-ttu-id="3172d-157">导航到 [PWA 生成器][PwabuilderMain]。</span><span class="sxs-lookup"><span data-stu-id="3172d-157">Navigate to [PWA Builder][PwabuilderMain].</span></span>  
1.  <span data-ttu-id="3172d-158">键入 PWA 的 URL。</span><span class="sxs-lookup"><span data-stu-id="3172d-158">Type the URL of your PWA.</span></span>  
1.  <span data-ttu-id="3172d-159">选择 **"开始**  >  **生成我的 PWA**  >  **Windows**  >  **选项"。**</span><span class="sxs-lookup"><span data-stu-id="3172d-159">Choose **Start** > **Build My PWA** > **Windows** > **Options**.</span></span>  
1.  <span data-ttu-id="3172d-160">粘贴你在创建应用预订 [部分中保存的以下](#create-an-app-reservation) 值。</span><span class="sxs-lookup"><span data-stu-id="3172d-160">Paste the following values that you saved in the [Create an app reservation](#create-an-app-reservation) section.</span></span>  
    *   **<span data-ttu-id="3172d-161">程序包 ID</span><span class="sxs-lookup"><span data-stu-id="3172d-161">Package ID</span></span>**  
    *   **<span data-ttu-id="3172d-162">发布者 ID</span><span class="sxs-lookup"><span data-stu-id="3172d-162">Publisher ID</span></span>**  
    *   **<span data-ttu-id="3172d-163">发布者显示名称</span><span class="sxs-lookup"><span data-stu-id="3172d-163">Publisher Display Name</span></span>**  
        
    :::image type="complex" source="./media/pwabuilder-publisher-info.msft.png" alt-text="将发布者信息粘贴到 PWABuilder 中" lightbox="./media/pwabuilder-publisher-info.msft.png":::
       <span data-ttu-id="3172d-165">将发布者信息粘贴到 PWABuilder 中</span><span class="sxs-lookup"><span data-stu-id="3172d-165">Paste publisher information into PWABuilder</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="3172d-166">选择"**完成"。**</span><span class="sxs-lookup"><span data-stu-id="3172d-166">Choose **Done**.</span></span>  
1.  <span data-ttu-id="3172d-167">若要下载 Windows 应用包，请选择"下载 **"。**</span><span class="sxs-lookup"><span data-stu-id="3172d-167">To download your Windows app package, choose **Download**.</span></span>  <span data-ttu-id="3172d-168">下载内容 `.zip` 是包含文件的 `.msixbundle` 存档。</span><span class="sxs-lookup"><span data-stu-id="3172d-168">Your download is a `.zip` archive containing an `.msixbundle` file.</span></span>  <span data-ttu-id="3172d-169">使用 `.msixbundle` "将应用 [包提交到应用商店"部分中的](#submit-your-app-package-to-the-store) 文件。</span><span class="sxs-lookup"><span data-stu-id="3172d-169">Use the `.msixbundle` file in the [Submit your app package to the Store](#submit-your-app-package-to-the-store) section.</span></span>  

### <a name="submit-your-app-package-to-the-store"></a><span data-ttu-id="3172d-170">将应用包提交到应用商店</span><span class="sxs-lookup"><span data-stu-id="3172d-170">Submit your app package to the Store</span></span>  

<span data-ttu-id="3172d-171">现在，你已 `.msixbundle` 拥有应用包。</span><span class="sxs-lookup"><span data-stu-id="3172d-171">Now, you have your `.msixbundle` app package.</span></span>  <span data-ttu-id="3172d-172">若要将应用包提交到应用商店，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="3172d-172">To submit your app package to the Store, complete the following actions.</span></span>  

1.  <span data-ttu-id="3172d-173">导航到 [Windows 合作伙伴中心][MicrosoftPartnerDashboardWindowsOverview]</span><span class="sxs-lookup"><span data-stu-id="3172d-173">Navigate to [Windows Partner Center][MicrosoftPartnerDashboardWindowsOverview]</span></span> 
1.  <span data-ttu-id="3172d-174">选择你的应用。</span><span class="sxs-lookup"><span data-stu-id="3172d-174">Choose your app.</span></span>  
1.  <span data-ttu-id="3172d-175">选择 **"开始提交"。**</span><span class="sxs-lookup"><span data-stu-id="3172d-175">Choose **Start your Submission**.</span></span>  
    
    :::image type="complex" source="./media/windows-partner-center-start-submission.msft.png" alt-text="在 Windows 合作伙伴中心上启动新应用提交" lightbox="./media/windows-partner-center-start-submission.msft.png":::
       <span data-ttu-id="3172d-177">在 Windows 合作伙伴中心上启动新应用提交</span><span class="sxs-lookup"><span data-stu-id="3172d-177">Start a new app submission on Windows Partner Center</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="3172d-178">完成以下提示，获取有关应用的信息。</span><span class="sxs-lookup"><span data-stu-id="3172d-178">Complete the following prompts for information about your app.</span></span>
    *   <span data-ttu-id="3172d-179">pricing</span><span class="sxs-lookup"><span data-stu-id="3172d-179">pricing</span></span>  
    *   <span data-ttu-id="3172d-180">年龄分级</span><span class="sxs-lookup"><span data-stu-id="3172d-180">age rating</span></span>  
    *   <span data-ttu-id="3172d-181">和更多信息</span><span class="sxs-lookup"><span data-stu-id="3172d-181">and more</span></span>  
        
1.  <span data-ttu-id="3172d-182">在 **"程序包"** 提示符上，选择 `.msixbundle` 在"打包 [PWA"部分生成的](#package-your-pwa) 文件。</span><span class="sxs-lookup"><span data-stu-id="3172d-182">On the **Packages** prompt, choose the `.msixbundle` file your generated in the [Package your PWA](#package-your-pwa) section.</span></span>  

<span data-ttu-id="3172d-183">完成提交后，通常会在 24 至 48 小时内查看你的应用。</span><span class="sxs-lookup"><span data-stu-id="3172d-183">After you complete your submission, your app is reviewed, typically within between 24 and 48 hours.</span></span>  <span data-ttu-id="3172d-184">收到批准后，PWA 将在 Microsoft Store 中提供。</span><span class="sxs-lookup"><span data-stu-id="3172d-184">After you receive approval, your PWA is available in the Microsoft Store.</span></span>  

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

