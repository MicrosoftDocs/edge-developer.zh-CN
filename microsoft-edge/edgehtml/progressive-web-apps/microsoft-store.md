---
description: 通过 Microsoft Store 分发 PWA，覆盖 Windows 10 客户的世界
title: Microsoft Store 中的渐进 Web 应用
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: 渐进式 Web 应用， PWA， Edge， Windows， Microsoft Store， 必应 PWA 索引
ms.date: 12/02/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: dae25bcdf37a2496e181ab915d1686fe5d3a4985
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232342"
---
# <span data-ttu-id="c287f-104">Microsoft Store 中的渐进 Web 应用</span><span class="sxs-lookup"><span data-stu-id="c287f-104">Progressive Web Apps in the Microsoft Store</span></span>

<span data-ttu-id="c287f-105">将渐进式 Web 应用 (PWA) 发布到 Microsoft [Store](https://developer.microsoft.com/store)时，潜在应用受众将扩展到整个 Windows 10 安装基础，每月有近 7 亿活跃用户！</span><span class="sxs-lookup"><span data-stu-id="c287f-105">When you publish your Progressive Web App (PWA) to the [Microsoft Store](https://developer.microsoft.com/store), your potential app audience expands to the entire Windows 10 install base of nearly 700 million active monthly users!</span></span> 

<span data-ttu-id="c287f-106">Microsoft Store 中的 PWA 具有许多优势：</span><span class="sxs-lookup"><span data-stu-id="c287f-106">PWAs in the Microsoft Store enjoy a number of advantages:</span></span>

-   <span data-ttu-id="c287f-107">**可发现** 性 - Microsoft Store 中的应用通过不同的类别、特展的集合和搜索筛选器进行展示，为应用的潜在客户提供轻松的浏览和购物体验。</span><span class="sxs-lookup"><span data-stu-id="c287f-107">**Discoverability** - Apps in the Microsoft Store are showcased through different categories, curated collections, and search filters, providing an easy browsing and shopping experience for potential customers of your app.</span></span> <span data-ttu-id="c287f-108">你甚至可以 [使用屏幕截图](/windows/uwp/publish/app-screenshots-and-images) 、人物图像和视频预告片增强应用商店一览！</span><span class="sxs-lookup"><span data-stu-id="c287f-108">You can even [enhance your Store listing](/windows/uwp/publish/app-screenshots-and-images) with screenshots, a hero image, and video trailers!</span></span>
-   <span data-ttu-id="c287f-109">**可信度** - Windows 客户知道他们可以信任 Microsoft Store 的购买和下载，因为他们遵守 Microsoft 严格的 [质量和安全标准](/legal/windows/agreements/store-policies)。</span><span class="sxs-lookup"><span data-stu-id="c287f-109">**Trustworthiness** - Windows customers know they can trust their Microsoft Store purchases and downloads because they adhere to Microsoft's rigorous [quality and safety standards](/legal/windows/agreements/store-policies).</span></span>
-   <span data-ttu-id="c287f-110">**易于安装** - Microsoft Store 在所有 [Windows 10](https://www.microsoft.com/store/apps/windows?icid=CNavAppsWindowsApps)应用中提供一致且用户友好的安装体验，使所有客户都可以轻松安装 PWA，无论技术舒适级别如何。</span><span class="sxs-lookup"><span data-stu-id="c287f-110">**Easy install** - The Microsoft Store provides a consistent and user friendly install experience across [all Windows 10 apps](https://www.microsoft.com/store/apps/windows?icid=CNavAppsWindowsApps), making it easy for all customers to install your PWA, regardless of technical comfort level.</span></span>
-   <span data-ttu-id="c287f-111">业务见解 **-** 适用于 Microsoft Store 的[Windows](/windows/uwp/publish/using-the-windows-dev-center-dashboard)开发人员[](/windows/uwp/publish/analytics)中心仪表板提供有关所有内容的详细分析，从 PWA 已接触的 Windows 客户数到客户使用方式以及必须说出的信息。</span><span class="sxs-lookup"><span data-stu-id="c287f-111">**Business insights** - The [Windows Dev Center dashboard](/windows/uwp/publish/using-the-windows-dev-center-dashboard) for the Microsoft Store provides you with [detailed analytics](/windows/uwp/publish/analytics) about everything from how many Windows customers your PWA has reached to how they're using it and what they have to say.</span></span> <span data-ttu-id="c287f-112">还可以查找有关应用运行状况、广告使用情况等的指标和遥测数据。</span><span class="sxs-lookup"><span data-stu-id="c287f-112">You can also find metrics and telemetry data on app health, ad usage, and more.</span></span>
    
<span data-ttu-id="c287f-113">有两个选项用于将 PWA 加入 Microsoft Store：</span><span class="sxs-lookup"><span data-stu-id="c287f-113">There are two options for getting your PWA into the Microsoft Store:</span></span>

1.  <span data-ttu-id="c287f-114">你可以 [手动提交它](#submitting-your-pwa-manually)，或者</span><span class="sxs-lookup"><span data-stu-id="c287f-114">You can [manually submit it](#submitting-your-pwa-manually), or</span></span>
2.  <span data-ttu-id="c287f-115">如果您的 PWA 满足[特定条件](#criteria-for-automatic-submission)，则 Bing [](#automatic-pwa-importing-with-bing) Web 爬网程序可自动对 PWA 编制索引。</span><span class="sxs-lookup"><span data-stu-id="c287f-115">If your PWA meets [certain criteria](#criteria-for-automatic-submission), it can be [automatically indexed](#automatic-pwa-importing-with-bing) by the Bing web crawler.</span></span> <span data-ttu-id="c287f-116"> (还可以选择退出自动提交。) [](#opting-out-of-automatic-microsoft-store-import)</span><span class="sxs-lookup"><span data-stu-id="c287f-116">(You also have the option to [opt-out](#opting-out-of-automatic-microsoft-store-import) of auto-submission.)</span></span>
    
<span data-ttu-id="c287f-117">无论采用哪种提交方法，一旦将 PWA 接受到 Microsoft Store，你都将获得上述所有权益的访问权限。</span><span class="sxs-lookup"><span data-stu-id="c287f-117">Regardless of submission method, once your PWA is accepted to the Microsoft Store you'll gain access to all the benefits outlined above.</span></span>

## <span data-ttu-id="c287f-118">手动提交 PWA</span><span class="sxs-lookup"><span data-stu-id="c287f-118">Submitting your PWA manually</span></span>

<span data-ttu-id="c287f-119">若要通过 Microsoft Store 分发和推广应用，你需要将其作为 Windows 应用包提交到 .appx (*.appx*) 。</span><span class="sxs-lookup"><span data-stu-id="c287f-119">In order to distribute and promote an app through the Microsoft Store, you'll need to submit it as a Windows app package (*.appx* file).</span></span>  <span data-ttu-id="c287f-120">对于服务器托管的 Web 应用（如 PWA），此包仅包含应用元数据和主屏幕图标 (而不包含任何实际应用程序) 。</span><span class="sxs-lookup"><span data-stu-id="c287f-120">For server-hosted web apps such as PWAs, this package simply contains app metadata and home screen icons (and none of the actual application code).</span></span> <span data-ttu-id="c287f-121">这样，可以在独立于 Microsoft Edge 浏览器窗口的轻型本机应用包装器 (*WWAHost.exe*进程) 中运行，将 Web 应用与其他[Windows 10](/windows/uwp/get-started/whats-a-uwp)应用一起从主屏幕安装和启动。</span><span class="sxs-lookup"><span data-stu-id="c287f-121">With this, your web app can be installed and launched from the home screen alongside other [Windows 10 apps](/windows/uwp/get-started/whats-a-uwp) by running in a lightweight native app wrapper (*WWAHost.exe* process), independent from the Microsoft Edge browser window.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="c287f-122">EdgeHTML Web 平台引擎由 WWAHost 应用包装器使用，它可能会为基于 PWA 的 Microsoft Edge (Chromium) 兼容性差异。</span><span class="sxs-lookup"><span data-stu-id="c287f-122">The EdgeHTML web platform engine is used by the WWAHost app wrapper which could introduce compatibility differences for your Microsoft Edge (Chromium) based PWA.</span></span>  <span data-ttu-id="c287f-123">在将应用提交到 Microsoft Store 之前，请确保使用 Microsoft Edge (EdgeHTML) 对应用程序执行完全测试，因为不再使用较新的 Web 标准更新 EdgeHTML 引擎。</span><span class="sxs-lookup"><span data-stu-id="c287f-123">Be sure to do a full test pass on your application using Microsoft Edge (EdgeHTML) before submitting your app to the Microsoft store as the EdgeHTML engine is no longer being updated with newer web standards.</span></span>  

<span data-ttu-id="c287f-124">下面是如何执行。</span><span class="sxs-lookup"><span data-stu-id="c287f-124">Here's how to do it.</span></span>

### <span data-ttu-id="c287f-125">必备条件</span><span class="sxs-lookup"><span data-stu-id="c287f-125">Prerequisites</span></span>

-   <span data-ttu-id="c287f-126">**现有的 PWA**。</span><span class="sxs-lookup"><span data-stu-id="c287f-126">**An existing PWA**.</span></span> <span data-ttu-id="c287f-127">下面将了解如何将 [Web 应用转换为 PWA（](./get-started.md) 如果尚未转换）。</span><span class="sxs-lookup"><span data-stu-id="c287f-127">Here's how to [convert your web app to a PWA](./get-started.md) if it isn't one already.</span></span> 
-   <span data-ttu-id="c287f-128">**适用于 PWA 的 Windows APPX 打包工具**。</span><span class="sxs-lookup"><span data-stu-id="c287f-128">**A Windows APPX packaging tool for PWAs**.</span></span> <span data-ttu-id="c287f-129">下面将了解如何使用 Visual Studio 在 Windows 上生成和运行[PWA。](./windows-features.md)</span><span class="sxs-lookup"><span data-stu-id="c287f-129">Here's how to [build and run your PWA on Windows](./windows-features.md) using Visual Studio.</span></span> <span data-ttu-id="c287f-130">您还可以使用 [PWA 生成器](https://www.pwabuilder.com/) 生成 Windows 程序包。</span><span class="sxs-lookup"><span data-stu-id="c287f-130">You can also use [PWA Builder](https://www.pwabuilder.com/) to build a Windows package.</span></span>
-   <span data-ttu-id="c287f-131">[**Microsoft Store 应用开发人员帐户**](/windows/uwp/publish/opening-a-developer-account)。</span><span class="sxs-lookup"><span data-stu-id="c287f-131">[**Microsoft Store app developer account**](/windows/uwp/publish/opening-a-developer-account).</span></span> <span data-ttu-id="c287f-132">有一 [次费用](/windows/uwp/publish/account-types-locations-and-fees) ，具体取决于你选择的帐户类型和位置，注册需要有效的 [Microsoft 帐户](https://account.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="c287f-132">There is a [one-time fee](/windows/uwp/publish/account-types-locations-and-fees) depending on your chosen account type and location, and registration requires a valid [Microsoft Account](https://account.microsoft.com/).</span></span>
    
### <span data-ttu-id="c287f-133">通过应用商店提交 *Visual Studio*</span><span class="sxs-lookup"><span data-stu-id="c287f-133">Store submission through *Visual Studio*</span></span> 

<span data-ttu-id="c287f-134">按照以下步骤在应用程序中 [为](/windows/uwp/packaging/packaging-uwp-apps#create-an-app-package-upload-file) PWA 创建应用程序包Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="c287f-134">Follow these steps to [create an app package upload file](/windows/uwp/packaging/packaging-uwp-apps#create-an-app-package-upload-file) for your PWA in Visual Studio.</span></span> <span data-ttu-id="c287f-135">有关 [*此过程的更一般Visual Studio，*](/windows/uwp/packaging/packaging-uwp-apps) 请参阅"将 UWP 应用打包"。</span><span class="sxs-lookup"><span data-stu-id="c287f-135">See [*Package a UWP app with Visual Studio*](/windows/uwp/packaging/packaging-uwp-apps) for a more general overview of this process.</span></span>

<span data-ttu-id="c287f-136">这些说明还将指导你运行 Windows [**应用认证工具包**](https://developer.microsoft.com/windows/develop/app-certification-kit) ，以测试你的应用是否符合 Microsoft Store 要求。</span><span class="sxs-lookup"><span data-stu-id="c287f-136">The instructions will also guide you through running the [**Windows App Certification Kit**](https://developer.microsoft.com/windows/develop/app-certification-kit) to test your app for compliance with Microsoft Store requirements.</span></span> <span data-ttu-id="c287f-137">这是可选的，但强烈建议这样做。</span><span class="sxs-lookup"><span data-stu-id="c287f-137">This is optional, but highly recommended.</span></span>

### <span data-ttu-id="c287f-138">通过 *Windows 开发人员中心进行应用商店提交*</span><span class="sxs-lookup"><span data-stu-id="c287f-138">Store submission through *Windows Dev Center*</span></span>

<span data-ttu-id="c287f-139">下面将了解如何使用 *PWA 生成器* 生成要上传到 Windows 开发人员中心的应用包。</span><span class="sxs-lookup"><span data-stu-id="c287f-139">Here's how to use *PWA Builder* to generate an app package for upload to the Windows Dev Center.</span></span>

1.  <span data-ttu-id="c287f-140">生成 Windows 10 应用。</span><span class="sxs-lookup"><span data-stu-id="c287f-140">Generate your Windows 10 app.</span></span> <span data-ttu-id="c287f-141">下面将说明如何将 PWA 作为 Windows 应用运行[，Visual Studio。](./windows-features.md)</span><span class="sxs-lookup"><span data-stu-id="c287f-141">Here's how to run your [PWA as a Windows app with Visual Studio](./windows-features.md).</span></span> <span data-ttu-id="c287f-142">您还可以使用 [PWA 生成器](https://www.pwabuilder.com/) 生成 Windows 10 应用。</span><span class="sxs-lookup"><span data-stu-id="c287f-142">You can also use [PWA Builder](https://www.pwabuilder.com/) to generate your Windows 10 app.</span></span>
2.  <span data-ttu-id="c287f-143">使用帐户信息登录到 [Windows](https://developer.microsoft.com/dashboard/windows/overview) 开发人员中心仪表板，然后按照步骤通过保留名称来创建应用，为 Microsoft Store [保留应用名称](/windows/uwp/publish/create-your-app-by-reserving-a-name)。</span><span class="sxs-lookup"><span data-stu-id="c287f-143">Reserve your app name for the Microsoft Store by logging into the [Windows Dev Center dashboard](https://developer.microsoft.com/dashboard/windows/overview) with your account info and following the steps to [create your app by reserving a name](/windows/uwp/publish/create-your-app-by-reserving-a-name).</span></span> <span data-ttu-id="c287f-144">每个保留的名称在 Microsoft Store 中都必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="c287f-144">Each reserved name must be unique throughout the Microsoft Store.</span></span>
3.  <span data-ttu-id="c287f-145">上传应用包时 *，.appxmanifest*文件的*DisplayName、Name、Publisher*和*PublisherDisplayName*值必须与在 Windows 开发人员中心仪表板中分配给应用的值匹配，且保留其名称。  </span><span class="sxs-lookup"><span data-stu-id="c287f-145">When you upload your app's packages, the *DisplayName*, *Name*, *Publisher*, and *PublisherDisplayName* values in your *.appxmanifest* file must match the values assigned to your app in the Windows Dev Center dashboard upon reserving its name.</span></span> 
    
    <span data-ttu-id="c287f-146">登录到[Windows 开发人员中心仪表板](https://developer.microsoft.com/dashboard/windows/overview)，并找到应用管理应用标识  >  **下的应用标识值**：</span><span class="sxs-lookup"><span data-stu-id="c287f-146">Log into the [Windows Dev Center dashboard](https://developer.microsoft.com/dashboard/windows/overview), and locate your app identity values under **App management** > **App identity**:</span></span>
    
    ![Windows 开发人员中心仪表板，应用标识设置](./media/dashboard-app-identity.png)
    
    <span data-ttu-id="c287f-148">然后，找到你的文件，并将以下值替换为在 Windows 开发人员中心仪表板中分配 `appxmanifest.xml` 的值：</span><span class="sxs-lookup"><span data-stu-id="c287f-148">Then, locate your `appxmanifest.xml` file and replace the following values with the ones assigned in the Windows Dev Center dashboard:</span></span>
    
    -   <span data-ttu-id="c287f-149">**<Identity Name="** *Package/Identity/Name*</span><span class="sxs-lookup"><span data-stu-id="c287f-149">**<Identity Name="** *Package/Identity/Name*</span></span>
    -   <span data-ttu-id="c287f-150">**<Identity Publisher="** *Package/Identity/Publisher*</span><span class="sxs-lookup"><span data-stu-id="c287f-150">**<Identity Publisher="** *Package/Identity/Publisher*</span></span>
    -   <span data-ttu-id="c287f-151">**<DisplayName** \**>\*为应用保留的名称*</span><span class="sxs-lookup"><span data-stu-id="c287f-151">**<DisplayName** **>** *Name you reserved for your app*</span></span> 
    -   <span data-ttu-id="c287f-152">**<PublisherDisplayName** **>***Package/Properties/PublisherDisplayName***</PublisherDisplayName>**</span><span class="sxs-lookup"><span data-stu-id="c287f-152">**<PublisherDisplayName** **>** *Package/Properties/PublisherDisplayName* **</PublisherDisplayName>**</span></span>
        
4.  <span data-ttu-id="c287f-153">现在，你已准备好将你的所有 PWA 资源编译为可上载到 Microsoft Store 的单个 `.appx` 文件。</span><span class="sxs-lookup"><span data-stu-id="c287f-153">Now you're ready to compile all your PWA resources into a single `.appx` file you can upload to the Microsoft Store.</span></span> <span data-ttu-id="c287f-154">在命令提示符下，导航到 Web 清单的目录，并创建一个 Windows 10 程序包 (以下指定的调试日志记录) ：</span><span class="sxs-lookup"><span data-stu-id="c287f-154">From a command prompt, navigate to the directory of your web manifest and create a Windows 10 package (specified below w/ optional debug logging):</span></span>
    
    ```shell
    pwabuilder package -p windows10 -l debug
    ```  
    
    <span data-ttu-id="c287f-155">.appx 文件将生成到此 `PWA\Store packages\windows10\package\windows.appx` 位置：</span><span class="sxs-lookup"><span data-stu-id="c287f-155">Your .appx file will be generated to this location: `PWA\Store packages\windows10\package\windows.appx`.</span></span>
    
5.  <span data-ttu-id="c287f-156">在将应用上载到 Microsoft Store 之前，建议测试你的应用是否符合 Microsoft Store 策略。</span><span class="sxs-lookup"><span data-stu-id="c287f-156">Before you upload your app for submisison to the Microsoft Store, its a good idea to test your app for compliance with Microsoft Store policies.</span></span> <span data-ttu-id="c287f-157">为此，你可以下载 [**Windows 应用**](https://developer.microsoft.com/windows/develop/app-certification-kit)认证工具包，启动它，然后选择应用的 *.appx* 文件进行测试。</span><span class="sxs-lookup"><span data-stu-id="c287f-157">You can do this by downloading the [**Windows App Certification Kit**](https://developer.microsoft.com/windows/develop/app-certification-kit), launching it, and then selecting your app's *.appx* file for testing.</span></span> <span data-ttu-id="c287f-158">完成所有测试后，您将收到要解决的区域报告。</span><span class="sxs-lookup"><span data-stu-id="c287f-158">You will receive a report of areas to address once all the tests are complete.</span></span>
6.  <span data-ttu-id="c287f-159">上传程序包并完成提交，方法为登录 Windows[开发人员](https://developer.microsoft.com/dashboard/windows/overview)中心仪表板并展开**提交**  >  **子组件 1**面板。</span><span class="sxs-lookup"><span data-stu-id="c287f-159">Upload your package and complete the submission by logging back into the [Windows Dev Center dashboard](https://developer.microsoft.com/dashboard/windows/overview) and expanding the **Submissions** > **Submisison 1** panel.</span></span> <span data-ttu-id="c287f-160">按照清单完成所需的应用商店[一览信息并](/windows/uwp/publish/app-submissions)[上传应用包](/windows/uwp/publish/upload-app-packages)。</span><span class="sxs-lookup"><span data-stu-id="c287f-160">Follow the checklist to complete the [required store listing information](/windows/uwp/publish/app-submissions) and [upload your app package](/windows/uwp/publish/upload-app-packages).</span></span>
    
<span data-ttu-id="c287f-161">有关可供 Microsoft Store 应用开发人员使用的所有功能和服务，请参阅在 [*Windows*](https://developer.microsoft.com/store/publish-apps) 开发人员中心上发布 [Windows 应用](https://developer.microsoft.com/windows)。</span><span class="sxs-lookup"><span data-stu-id="c287f-161">For more on the all the features and services available to Microsoft Store app developers, see [*Publish Windows apps*](https://developer.microsoft.com/store/publish-apps) on the [Windows Dev Center](https://developer.microsoft.com/windows).</span></span>

## <span data-ttu-id="c287f-162">使用必应自动导入 PWA</span><span class="sxs-lookup"><span data-stu-id="c287f-162">Automatic PWA importing with Bing</span></span>

<span data-ttu-id="c287f-163">正如 PWA 的 [Web](https://developer.mozilla.org/docs/Web/Manifest) 应用清单是支持平台的信号一样，你的应用支持脱机并且已准备好呈现为完全集成的应用体验，它还向必应 Web 爬网程序提供提示，提示应考虑将 PWA 自动包含在 Microsoft Store 中。</span><span class="sxs-lookup"><span data-stu-id="c287f-163">Just as your PWA's [web app manifest](https://developer.mozilla.org/docs/Web/Manifest) is a signal to supporting platforms that your app is offline-capable and ready to be presented as a fully integrated app experience, it's also a hint to the Bing web crawler that your PWA should be considered for automatic inclusion in the Microsoft Store.</span></span> 

<span data-ttu-id="c287f-164">如果您的 PWA 满足以下要求，必应索引服务将自动将 PWA 打包为在 Windows 10 上安装所需的 [*.appx*](#submitting-your-pwa-manually) 格式，并基于应用的 Web 应用清单中的元数据来组合应用的应用商店产品页面。</span><span class="sxs-lookup"><span data-stu-id="c287f-164">If your PWA meets the requirements below, the Bing indexing service will automatically package your PWA in the [*.appx*](#submitting-your-pwa-manually) format required for installation on Windows 10 and assemble your app's store product page based on the metadata in its web app manifest.</span></span> <span data-ttu-id="c287f-165">声明 PWA 后，你将能够进一步自定义应用商店页面，并通过 Windows 开发人员中心仪表板访问用户分析和其他应用管理工具。</span><span class="sxs-lookup"><span data-stu-id="c287f-165">After claiming your PWA, you'll be able to further customize your store page and gain access to user analytics and other app management tools through the Windows Dev Center dashboard.</span></span>

### <span data-ttu-id="c287f-166">自动提交的条件</span><span class="sxs-lookup"><span data-stu-id="c287f-166">Criteria for automatic submission</span></span>

<span data-ttu-id="c287f-167">若要自动打包并针对 Microsoft Store 列出，PWA 将需要：</span><span class="sxs-lookup"><span data-stu-id="c287f-167">To be automatically packaged and listed for the Microsoft Store, your PWA will need:</span></span>

-   <span data-ttu-id="c287f-168">非空 Web 应用清单文件，至少为：</span><span class="sxs-lookup"><span data-stu-id="c287f-168">A non-empty web app manifest file, with at minimum:</span></span>
    
    -   <span data-ttu-id="c287f-169">名称</span><span class="sxs-lookup"><span data-stu-id="c287f-169">Name</span></span>
    -   <span data-ttu-id="c287f-170">描述</span><span class="sxs-lookup"><span data-stu-id="c287f-170">Description</span></span>
    -   <span data-ttu-id="c287f-171">至少为 512 x 512 像素的应用图标</span><span class="sxs-lookup"><span data-stu-id="c287f-171">App icon that is at least 512 x 512 pixels</span></span>
        
-   <span data-ttu-id="c287f-172">唯一的核心逻辑 (来自应用样本模板模板的最少修改) [](https://en.wikipedia.org/wiki/Boilerplate_code)</span><span class="sxs-lookup"><span data-stu-id="c287f-172">Unique core logic (not minimally modified code from an [app boilerplate](https://en.wikipedia.org/wiki/Boilerplate_code) template)</span></span>
-   <span data-ttu-id="c287f-173">通过 HTTPS 安全连接 (服务) </span><span class="sxs-lookup"><span data-stu-id="c287f-173">To be served over a secure connection (HTTPS)</span></span>
-   <span data-ttu-id="c287f-174">服务工作 (脚本) </span><span class="sxs-lookup"><span data-stu-id="c287f-174">Service worker script(s)</span></span>
-   <span data-ttu-id="c287f-175">不违反任何法律或 [Microsoft Store 策略](/legal/windows/agreements/store-policies)。</span><span class="sxs-lookup"><span data-stu-id="c287f-175">To not violate any laws or [Microsoft Store policies](/legal/windows/agreements/store-policies).</span></span>
    
<span data-ttu-id="c287f-176">我们不会将符合这些条件的每一个应用都考虑在内，但在逐步扩展计划时，我们会将它们包括在候选项的注意事项中。</span><span class="sxs-lookup"><span data-stu-id="c287f-176">We won't ingest every app that meets these criteria, but will be including them in our considerations for candidates as we gradually expand our program.</span></span>

### <span data-ttu-id="c287f-177">选择退出 Microsoft Store 自动导入</span><span class="sxs-lookup"><span data-stu-id="c287f-177">Opting out of automatic Microsoft Store import</span></span>

<span data-ttu-id="c287f-178">PWA 可以通过提供包含以下内容的文件来选择退出自动导入到 Microsoft `robots.txt` Store：</span><span class="sxs-lookup"><span data-stu-id="c287f-178">Your PWA can opt out of automatic import to the Microsoft Store by serving a `robots.txt` file containing the following:</span></span>

```text
User-agent: bingbot
Disallow: /manifest.json
```  

<span data-ttu-id="c287f-179">这将指示必应 Web 爬网 (必应) 忽略 Web 清单文件以用于 PWA 索引。</span><span class="sxs-lookup"><span data-stu-id="c287f-179">This directs the Bing web crawler (Bingbot) to disregard your web manifest file for PWA indexing purposes.</span></span> <span data-ttu-id="c287f-180">这不会影响网站在必应常规 Web 索引进程中 [的搜索排名](https://www.bing.com/webmaster/help/help-center-661b2d18)。</span><span class="sxs-lookup"><span data-stu-id="c287f-180">This will not affect your site's search ranking in Bing's regular [web indexing process](https://www.bing.com/webmaster/help/help-center-661b2d18).</span></span>
