---
description: 通过 Microsoft Store 分发 PWA，吸引 Windows 10 客户的世界
title: Microsoft Store 中的渐进式 Web 应用
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 渐进式 web 应用、PWA、Edge、Windows、Microsoft Store、Bing PWA 索引
ms.openlocfilehash: a4491f19b89e8b0f6fa511f146744499e2074f22
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564560"
---
# <span data-ttu-id="ad173-104">Microsoft Store 中的渐进式 Web 应用</span><span class="sxs-lookup"><span data-stu-id="ad173-104">Progressive Web Apps in the Microsoft Store</span></span>

<span data-ttu-id="ad173-105">当你将渐进式 Web 应用发布 (PWA) [Microsoft Store](https://developer.microsoft.com/store)时，你的潜在应用受众将扩展到将近700000000每月活动用户的整个 Windows 10 安装基础！</span><span class="sxs-lookup"><span data-stu-id="ad173-105">When you publish your Progressive Web App (PWA) to the [Microsoft Store](https://developer.microsoft.com/store), your potential app audience expands to the entire Windows 10 install base of nearly 700 million active monthly users!</span></span> 

<span data-ttu-id="ad173-106">Microsoft Store 中的 PWAs 有许多优点：</span><span class="sxs-lookup"><span data-stu-id="ad173-106">PWAs in the Microsoft Store enjoy a number of advantages:</span></span>

- <span data-ttu-id="ad173-107">可**发现**-Microsoft Store 中的应用通过不同的类别、特选集合和搜索筛选器者，从而为你的应用的潜在客户提供了一个简单的浏览和购物体验。</span><span class="sxs-lookup"><span data-stu-id="ad173-107">**Discoverability** - Apps in the Microsoft Store are showcased through different categories, curated collections, and search filters, providing an easy browsing and shopping experience for potential customers of your app.</span></span> <span data-ttu-id="ad173-108">您甚至可以使用屏幕截图、英雄图像和视频预告 [增强您的应用商店列表](/windows/uwp/publish/app-screenshots-and-images) ！</span><span class="sxs-lookup"><span data-stu-id="ad173-108">You can even [enhance your Store listing](/windows/uwp/publish/app-screenshots-and-images) with screenshots, a hero image, and video trailers!</span></span>

- <span data-ttu-id="ad173-109">可**信赖**-Windows 客户知道他们可以信任 Microsoft 应用商店购买和下载，因为它们遵守 microsoft 严格的[质量和安全标准](/legal/windows/agreements/store-policies)。</span><span class="sxs-lookup"><span data-stu-id="ad173-109">**Trustworthiness** - Windows customers know they can trust their Microsoft Store purchases and downloads because they adhere to Microsoft's rigorous [quality and safety standards](/legal/windows/agreements/store-policies).</span></span>

- <span data-ttu-id="ad173-110">**轻松安装** -Microsoft Store 在 [所有 Windows 10 应用](https://www.microsoft.com/store/apps/windows?icid=CNavAppsWindowsApps)中提供一致且用户友好的安装体验，让所有客户都可以轻松地安装 PWA，无论技术舒适的级别如何。</span><span class="sxs-lookup"><span data-stu-id="ad173-110">**Easy install** - The Microsoft Store provides a consistent and user friendly install experience across [all Windows 10 apps](https://www.microsoft.com/store/apps/windows?icid=CNavAppsWindowsApps), making it easy for all customers to install your PWA, regardless of technical comfort level.</span></span>

- <span data-ttu-id="ad173-111">**商业见解** -Microsoft Store 的 [Windows 开发人员中心仪表板](/windows/uwp/publish/using-the-windows-dev-center-dashboard) 为你提供有关从你的 PWA 已达到多少个 Windows 客户以及他们的使用方式以及所需含义的 [详细分析](/windows/uwp/publish/analytics) 。</span><span class="sxs-lookup"><span data-stu-id="ad173-111">**Business insights** - The [Windows Dev Center dashboard](/windows/uwp/publish/using-the-windows-dev-center-dashboard) for the Microsoft Store provides you with [detailed analytics](/windows/uwp/publish/analytics) about everything from how many Windows customers your PWA has reached to how they're using it and what they have to say.</span></span> <span data-ttu-id="ad173-112">你还可以在应用运行状况、广告使用等方面查找指标和遥测数据。</span><span class="sxs-lookup"><span data-stu-id="ad173-112">You can also find metrics and telemetry data on app health, ad usage, and more.</span></span>

<span data-ttu-id="ad173-113">有两个选项可用于将 PWA 转到 Microsoft Store 中：</span><span class="sxs-lookup"><span data-stu-id="ad173-113">There are two options for getting your PWA into the Microsoft Store:</span></span>

1. <span data-ttu-id="ad173-114">你可以 [手动提交它](#submitting-your-pwa-manually)，或者</span><span class="sxs-lookup"><span data-stu-id="ad173-114">You can [manually submit it](#submitting-your-pwa-manually), or</span></span>

2. <span data-ttu-id="ad173-115">如果 PWA 满足 [特定条件](#criteria-for-automatic-submission)，则可通过必应 web 爬网程序 [自动编制索引](#automatic-pwa-importing-with-bing) 。</span><span class="sxs-lookup"><span data-stu-id="ad173-115">If your PWA meets [certain criteria](#criteria-for-automatic-submission), it can be [automatically indexed](#automatic-pwa-importing-with-bing) by the Bing web crawler.</span></span> <span data-ttu-id="ad173-116"> (您还可以选择 [退出](#opting-out-of-automatic-microsoft-store-import) 自动提交。 ) </span><span class="sxs-lookup"><span data-stu-id="ad173-116">(You also have the option to [opt-out](#opting-out-of-automatic-microsoft-store-import) of auto-submission.)</span></span>

<span data-ttu-id="ad173-117">无论提交方法如何，在将 PWA 接受到 Microsoft Store 后，您将获得上述所有优点的访问权限。</span><span class="sxs-lookup"><span data-stu-id="ad173-117">Regardless of submission method, once your PWA is accepted to the Microsoft Store you'll gain access to all the benefits outlined above.</span></span>

## <span data-ttu-id="ad173-118">手动提交 PWA</span><span class="sxs-lookup"><span data-stu-id="ad173-118">Submitting your PWA manually</span></span>

<span data-ttu-id="ad173-119">为了通过 Microsoft Store 分发和提升应用，你需要将其作为 Windows 应用包 (*.appx* 文件) 提交。</span><span class="sxs-lookup"><span data-stu-id="ad173-119">In order to distribute and promote an app through the Microsoft Store, you'll need to submit it as a Windows app package (*.appx* file).</span></span>  <span data-ttu-id="ad173-120">对于服务器托管的 web 应用（如 PWAs），此程序包只包含应用元数据和主屏幕图标， (和任何实际的应用程序代码) 。</span><span class="sxs-lookup"><span data-stu-id="ad173-120">For server-hosted web apps such as PWAs, this package simply contains app metadata and home screen icons (and none of the actual application code).</span></span> <span data-ttu-id="ad173-121">通过这种方式，你的 web 应用可以从主屏幕和其他 [Windows 10 应用](/windows/uwp/get-started/whats-a-uwp) 安装和启动，方法是在 (*WWAHost.exe* 流程) （与 Microsoft Edge 浏览器窗口无关）的情况下运行。</span><span class="sxs-lookup"><span data-stu-id="ad173-121">With this, your web app can be installed and launched from the home screen alongside other [Windows 10 apps](/windows/uwp/get-started/whats-a-uwp) by running in a lightweight native app wrapper (*WWAHost.exe* process), independent from the Microsoft Edge browser window.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="ad173-122">EdgeHTML web 平台引擎由 WWAHost 应用包装程序使用，这可能会为你的 Microsoft Edge (Chromium) 基于的 PWA 带来兼容性差异。</span><span class="sxs-lookup"><span data-stu-id="ad173-122">The EdgeHTML web platform engine is used by the WWAHost app wrapper which could introduce compatibility differences for your Microsoft Edge (Chromium) based PWA.</span></span>  <span data-ttu-id="ad173-123">请确保在你的应用程序上使用 Microsoft Edge (EdgeHTML) 执行完整测试，因为 EdgeHTML 引擎不再使用较新的 web 标准进行更新。</span><span class="sxs-lookup"><span data-stu-id="ad173-123">Be sure to do a full test pass on your application using Microsoft Edge (EdgeHTML) before submitting your app to the Microsoft store as the EdgeHTML engine is no longer being updated with newer web standards.</span></span>  

<span data-ttu-id="ad173-124">下面介绍了如何操作。</span><span class="sxs-lookup"><span data-stu-id="ad173-124">Here's how to do it.</span></span>

### <span data-ttu-id="ad173-125">必备条件</span><span class="sxs-lookup"><span data-stu-id="ad173-125">Prerequisites</span></span>

- <span data-ttu-id="ad173-126">**现有 PWA**。</span><span class="sxs-lookup"><span data-stu-id="ad173-126">**An existing PWA**.</span></span> <span data-ttu-id="ad173-127">下面介绍了如何 [将你的 web 应用转换为 PWA](./get-started.md) （如果它尚未有）。</span><span class="sxs-lookup"><span data-stu-id="ad173-127">Here's how to [convert your web app to a PWA](./get-started.md) if it isn't one already.</span></span> 
- <span data-ttu-id="ad173-128">**用于 PWAs 的 WINDOWS APPX 打包工具**。</span><span class="sxs-lookup"><span data-stu-id="ad173-128">**A Windows APPX packaging tool for PWAs**.</span></span> <span data-ttu-id="ad173-129">下面介绍如何使用 Visual Studio [在 Windows 上生成和运行 PWA](./windows-features.md) 。</span><span class="sxs-lookup"><span data-stu-id="ad173-129">Here's how to [build and run your PWA on Windows](./windows-features.md) using Visual Studio.</span></span> <span data-ttu-id="ad173-130">你还可以使用 [PWA 生成器](https://www.pwabuilder.com/) 生成 Windows 程序包。</span><span class="sxs-lookup"><span data-stu-id="ad173-130">You can also use [PWA Builder](https://www.pwabuilder.com/) to build a Windows package.</span></span>
- <span data-ttu-id="ad173-131">[**Microsoft 应用商店应用开发人员帐户**](/windows/uwp/publish/opening-a-developer-account)。</span><span class="sxs-lookup"><span data-stu-id="ad173-131">[**Microsoft Store app developer account**](/windows/uwp/publish/opening-a-developer-account).</span></span> <span data-ttu-id="ad173-132">根据您所选择的帐户类型和位置有 [一次的费用](/windows/uwp/publish/account-types-locations-and-fees) ，注册需要有效的 [Microsoft 帐户](https://account.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="ad173-132">There is a [one-time fee](/windows/uwp/publish/account-types-locations-and-fees) depending on your chosen account type and location, and registration requires a valid [Microsoft Account](https://account.microsoft.com/).</span></span>


### <span data-ttu-id="ad173-133">通过*Visual Studio*提交应用商店</span><span class="sxs-lookup"><span data-stu-id="ad173-133">Store submission through *Visual Studio*</span></span> 

<span data-ttu-id="ad173-134">按照以下步骤在 Visual Studio 中为 PWA [创建应用包上传文件](/windows/uwp/packaging/packaging-uwp-apps#create-an-app-package-upload-file) 。</span><span class="sxs-lookup"><span data-stu-id="ad173-134">Follow these steps to [create an app package upload file](/windows/uwp/packaging/packaging-uwp-apps#create-an-app-package-upload-file) for your PWA in Visual Studio.</span></span> <span data-ttu-id="ad173-135">有关此过程的更多常规概述，请参阅将 [*UWP 应用打包到 Visual Studio*](/windows/uwp/packaging/packaging-uwp-apps) 。</span><span class="sxs-lookup"><span data-stu-id="ad173-135">See [*Package a UWP app with Visual Studio*](/windows/uwp/packaging/packaging-uwp-apps) for a more general overview of this process.</span></span>

<span data-ttu-id="ad173-136">说明还将指导你运行 [**Windows 应用认证工具包**](https://developer.microsoft.com/windows/develop/app-certification-kit) ，以测试你的应用是否符合 Microsoft Store 要求。</span><span class="sxs-lookup"><span data-stu-id="ad173-136">The instructions will also guide you through running the [**Windows App Certification Kit**](https://developer.microsoft.com/windows/develop/app-certification-kit) to test your app for compliance with Microsoft Store requirements.</span></span> <span data-ttu-id="ad173-137">这是可选的，但强烈建议这样做。</span><span class="sxs-lookup"><span data-stu-id="ad173-137">This is optional, but highly recommended.</span></span>

### <span data-ttu-id="ad173-138">通过*Windows 开发人员中心*提交应用商店</span><span class="sxs-lookup"><span data-stu-id="ad173-138">Store submission through *Windows Dev Center*</span></span>

<span data-ttu-id="ad173-139">下面介绍了如何使用 *PWA 生成器* 生成用于上载到 Windows 开发人员中心的应用包。</span><span class="sxs-lookup"><span data-stu-id="ad173-139">Here's how to use *PWA Builder* to generate an app package for upload to the Windows Dev Center.</span></span>

1. <span data-ttu-id="ad173-140">生成 Windows 10 应用。</span><span class="sxs-lookup"><span data-stu-id="ad173-140">Generate your Windows 10 app.</span></span> <span data-ttu-id="ad173-141">下面介绍了如何 [使用 Visual Studio 作为 Windows 应用运行 PWA](./windows-features.md)。</span><span class="sxs-lookup"><span data-stu-id="ad173-141">Here's how to run your [PWA as a Windows app with Visual Studio](./windows-features.md).</span></span> <span data-ttu-id="ad173-142">你还可以使用 [PWA 生成器](https://www.pwabuilder.com/) 生成 Windows 10 应用。</span><span class="sxs-lookup"><span data-stu-id="ad173-142">You can also use [PWA Builder](https://www.pwabuilder.com/) to generate your Windows 10 app.</span></span>

2. <span data-ttu-id="ad173-143">通过使用您的帐户信息登录到 [Windows 开发人员中心仪表板](https://developer.microsoft.com/dashboard/windows/overview) 并按照步骤 [通过保留名称创建你的应用](/windows/uwp/publish/create-your-app-by-reserving-a-name)，为 Microsoft Store 保留你的应用名称。</span><span class="sxs-lookup"><span data-stu-id="ad173-143">Reserve your app name for the Microsoft Store by logging into the [Windows Dev Center dashboard](https://developer.microsoft.com/dashboard/windows/overview) with your account info and following the steps to [create your app by reserving a name](/windows/uwp/publish/create-your-app-by-reserving-a-name).</span></span> <span data-ttu-id="ad173-144">每个保留的名称在 Microsoft Store 中都必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="ad173-144">Each reserved name must be unique throughout the Microsoft Store.</span></span>

3. <span data-ttu-id="ad173-145">当你上载应用的程序包时， *package.appxmanifest*文件中的*DisplayName*、 *Name*、 *Publisher*和*PublisherDisplayName*值必须与在保留其名称时在 Windows 开发人员中心仪表板中分配给你的应用的值相匹配。</span><span class="sxs-lookup"><span data-stu-id="ad173-145">When you upload your app's packages, the *DisplayName*, *Name*, *Publisher*, and *PublisherDisplayName* values in your *.appxmanifest* file must match the values assigned to your app in the Windows Dev Center dashboard upon reserving its name.</span></span> 

    <span data-ttu-id="ad173-146">登录到[Windows 开发人员中心仪表板](https://developer.microsoft.com/dashboard/windows/overview)，然后在 "**应用管理**  >  **应用标识**" 下找到你的应用标识值：</span><span class="sxs-lookup"><span data-stu-id="ad173-146">Log into the [Windows Dev Center dashboard](https://developer.microsoft.com/dashboard/windows/overview), and locate your app identity values under **App management** > **App identity**:</span></span>

    ![Windows 开发人员中心仪表板，应用标识设置](./media/dashboard-app-identity.png)

    <span data-ttu-id="ad173-148">然后，找到你的 `appxmanifest.xml` 文件并将以下值替换为 Windows 开发人员中心仪表板中分配的值：</span><span class="sxs-lookup"><span data-stu-id="ad173-148">Then, locate your `appxmanifest.xml` file and replace the following values with the ones assigned in the Windows Dev Center dashboard:</span></span>

    - <span data-ttu-id="ad173-149">**<标识名称 = "** *程序包/标识/名称*</span><span class="sxs-lookup"><span data-stu-id="ad173-149">**<Identity Name="** *Package/Identity/Name*</span></span>
    - <span data-ttu-id="ad173-150">**<身份发布者 = "** *程序包/标识/发布者*</span><span class="sxs-lookup"><span data-stu-id="ad173-150">**<Identity Publisher="** *Package/Identity/Publisher*</span></span>
    - <span data-ttu-id="ad173-151">**<DisplayName** \**>\*\*\*为你的应用保留的名称*</span><span class="sxs-lookup"><span data-stu-id="ad173-151">**<DisplayName** **>** *Name you reserved for your app*</span></span> 
    - <span data-ttu-id="ad173-152">**<PublisherDisplayName** **>***软件包/Properties/PublisherDisplayName***</PublisherDisplayName>**</span><span class="sxs-lookup"><span data-stu-id="ad173-152">**<PublisherDisplayName** **>** *Package/Properties/PublisherDisplayName* **</PublisherDisplayName>**</span></span>

4. <span data-ttu-id="ad173-153">现在，你可以将所有 PWA 资源编译为单个 `.appx` 文件，你可以上传到 Microsoft Store。</span><span class="sxs-lookup"><span data-stu-id="ad173-153">Now you're ready to compile all your PWA resources into a single `.appx` file you can upload to the Microsoft Store.</span></span> <span data-ttu-id="ad173-154">从命令提示符处，导航到 web 清单的目录，并创建以下指定的 Windows 10 程序包 (（可选调试日志记录) ：</span><span class="sxs-lookup"><span data-stu-id="ad173-154">From a command prompt, navigate to the directory of your web manifest and create a Windows 10 package (specified below w/ optional debug logging):</span></span>

    ```
    pwabuilder package -p windows10 -l debug
    ```

    <span data-ttu-id="ad173-155">您的 .appx 文件将生成到此位置： `PWA\Store packages\windows10\package\windows.appx` 。</span><span class="sxs-lookup"><span data-stu-id="ad173-155">Your .appx file will be generated to this location: `PWA\Store packages\windows10\package\windows.appx`.</span></span>

5. <span data-ttu-id="ad173-156">将 submisison 的应用上载到 Microsoft Store 之前，最好先测试你的应用是否符合 Microsoft 应用商店策略。</span><span class="sxs-lookup"><span data-stu-id="ad173-156">Before you upload your app for submisison to the Microsoft Store, its a good idea to test your app for compliance with Microsoft Store policies.</span></span> <span data-ttu-id="ad173-157">你可以通过以下方法执行此操作：下载 [**Windows 应用认证工具包**](https://developer.microsoft.com/windows/develop/app-certification-kit)，启动它，然后选择你的应用的 *.appx* 文件进行测试。</span><span class="sxs-lookup"><span data-stu-id="ad173-157">You can do this by downloading the [**Windows App Certification Kit**](https://developer.microsoft.com/windows/develop/app-certification-kit), launching it, and then selecting your app's *.appx* file for testing.</span></span> <span data-ttu-id="ad173-158">所有测试完成后，你将收到一个要解决的区域的报告。</span><span class="sxs-lookup"><span data-stu-id="ad173-158">You will receive a report of areas to address once all the tests are complete.</span></span>

6. <span data-ttu-id="ad173-159">通过登录回[Windows 开发人员中心仪表板](https://developer.microsoft.com/dashboard/windows/overview)并在**Submissions**  >  **Submisison 1**面板中展开提交，即可上传程序包并完成提交。</span><span class="sxs-lookup"><span data-stu-id="ad173-159">Upload your package and complete the submission by logging back into the [Windows Dev Center dashboard](https://developer.microsoft.com/dashboard/windows/overview) and expanding the **Submissions** > **Submisison 1** panel.</span></span> <span data-ttu-id="ad173-160">按照清单完成 [所需的应用商店清单信息](/windows/uwp/publish/app-submissions) 并 [上载你的应用包](/windows/uwp/publish/upload-app-packages)。</span><span class="sxs-lookup"><span data-stu-id="ad173-160">Follow the checklist to complete the [required store listing information](/windows/uwp/publish/app-submissions) and [upload your app package](/windows/uwp/publish/upload-app-packages).</span></span>

<span data-ttu-id="ad173-161">有关适用于 Microsoft Store 应用开发人员的所有功能和服务的详细信息，请参阅在[Windows 开发人员中心](https://developer.microsoft.com/windows)[*发布 windows 应用*](https://developer.microsoft.com/store/publish-apps)。</span><span class="sxs-lookup"><span data-stu-id="ad173-161">For more on the all the features and services available to Microsoft Store app developers, see [*Publish Windows apps*](https://developer.microsoft.com/store/publish-apps) on the [Windows Dev Center](https://developer.microsoft.com/windows).</span></span>

## <span data-ttu-id="ad173-162">与 Bing 进行自动 PWA 导入</span><span class="sxs-lookup"><span data-stu-id="ad173-162">Automatic PWA importing with Bing</span></span>

<span data-ttu-id="ad173-163">正如你的 PWA [web 应用清单](https://developer.mozilla.org/docs/Web/Manifest) 是支持平台的一种信号，你的应用可以脱机使用，并准备好作为完全集成的应用体验，它也是对 Bing web 爬行者的提示，可将其视为自动包含在 Microsoft Store 中。</span><span class="sxs-lookup"><span data-stu-id="ad173-163">Just as your PWA's [web app manifest](https://developer.mozilla.org/docs/Web/Manifest) is a signal to supporting platforms that your app is offline-capable and ready to be presented as a fully integrated app experience, it's also a hint to the Bing web crawler that your PWA should be considered for automatic inclusion in the Microsoft Store.</span></span> 

<span data-ttu-id="ad173-164">如果 PWA 满足下面的要求，必应索引服务将自动将你的 PWA 打包为在 Windows 10 上安装所需的 [*.appx*](#submitting-your-pwa-manually) 格式，并基于其 web 应用清单中的元数据汇编应用的应用商店产品页面。</span><span class="sxs-lookup"><span data-stu-id="ad173-164">If your PWA meets the requirements below, the Bing indexing service will automatically package your PWA in the [*.appx*](#submitting-your-pwa-manually) format required for installation on Windows 10 and assemble your app's store product page based on the metadata in its web app manifest.</span></span> <span data-ttu-id="ad173-165">在申报你的 PWA 后，你将能够通过 Windows 开发人员中心仪表板进一步自定义你的应用商店页面并获取用户分析和其他应用管理工具的访问权限。</span><span class="sxs-lookup"><span data-stu-id="ad173-165">After claiming your PWA, you'll be able to further customize your store page and gain access to user analytics and other app management tools through the Windows Dev Center dashboard.</span></span>

### <span data-ttu-id="ad173-166">自动提交的条件</span><span class="sxs-lookup"><span data-stu-id="ad173-166">Criteria for automatic submission</span></span>

<span data-ttu-id="ad173-167">若要为 Microsoft Store 自动打包和列出，你的 PWA 将需要：</span><span class="sxs-lookup"><span data-stu-id="ad173-167">To be automatically packaged and listed for the Microsoft Store, your PWA will need:</span></span>

- <span data-ttu-id="ad173-168">[X] 非空 web 应用清单文件，至少：</span><span class="sxs-lookup"><span data-stu-id="ad173-168">[X] A non-empty web app manifest file, with at minimum:</span></span>

  - <span data-ttu-id="ad173-169">名称</span><span class="sxs-lookup"><span data-stu-id="ad173-169">Name</span></span>
  - <span data-ttu-id="ad173-170">描述</span><span class="sxs-lookup"><span data-stu-id="ad173-170">Description</span></span>
  - <span data-ttu-id="ad173-171">至少 512 x 512 像素的应用图标</span><span class="sxs-lookup"><span data-stu-id="ad173-171">App icon that is at least 512 x 512 pixels</span></span>

- <span data-ttu-id="ad173-172">[X] 唯一的核心逻辑 (来自 [应用样板](https://en.wikipedia.org/wiki/Boilerplate_code) 模板的最少修改代码) </span><span class="sxs-lookup"><span data-stu-id="ad173-172">[X] Unique core logic (not minimally modified code from an [app boilerplate](https://en.wikipedia.org/wiki/Boilerplate_code) template)</span></span>

- <span data-ttu-id="ad173-173">[X] 通过安全连接进行服务 (HTTPS) </span><span class="sxs-lookup"><span data-stu-id="ad173-173">[X] To be served over a secure connection (HTTPS)</span></span>

- <span data-ttu-id="ad173-174">[X] 服务工作者脚本 (s) </span><span class="sxs-lookup"><span data-stu-id="ad173-174">[X] Service worker script(s)</span></span>

- <span data-ttu-id="ad173-175">[X] 不违反任何法律或 [Microsoft Store 政策](/legal/windows/agreements/store-policies)。</span><span class="sxs-lookup"><span data-stu-id="ad173-175">[X] To not violate any laws or [Microsoft Store policies](/legal/windows/agreements/store-policies).</span></span>

<span data-ttu-id="ad173-176">我们不会收到满足这些条件的每个应用，但在我们逐渐扩展我们的计划的应聘中将包括这些应用。</span><span class="sxs-lookup"><span data-stu-id="ad173-176">We won't ingest every app that meets these criteria, but will be including them in our considerations for candidates as we gradually expand our program.</span></span>

### <span data-ttu-id="ad173-177">退出自动 Microsoft Store 导入</span><span class="sxs-lookup"><span data-stu-id="ad173-177">Opting out of automatic Microsoft Store import</span></span>

<span data-ttu-id="ad173-178">通过提供包含以下内容的文件，你的 PWA 可以选择退出 Microsoft Store 的自动导入 `robots.txt` ：</span><span class="sxs-lookup"><span data-stu-id="ad173-178">Your PWA can opt out of automatic import to the Microsoft Store by serving a `robots.txt` file containing the following:</span></span>

```
User-agent: bingbot
Disallow: /manifest.json
```

<span data-ttu-id="ad173-179">这会将必应的 web 爬网程序 (Bingbot) ，以忽略 PWA 索引目的的 web 清单文件。</span><span class="sxs-lookup"><span data-stu-id="ad173-179">This directs the Bing web crawler (Bingbot) to disregard your web manifest file for PWA indexing purposes.</span></span> <span data-ttu-id="ad173-180">这不会影响你的网站在 Bing 的常规 [web 索引流程](https://www.bing.com/webmaster/help/help-center-661b2d18)中的搜索排名。</span><span class="sxs-lookup"><span data-stu-id="ad173-180">This will not affect your site's search ranking in Bing's regular [web indexing process](https://www.bing.com/webmaster/help/help-center-661b2d18).</span></span>
