---
description: 本指南概括介绍了 PWA 基础知识和用于在 Windows 上 (Chromium) 构建渐进式 Web 应用的工具。
title: " (Chromium 的渐进式 Web 应用入门) "
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/01/2020
ms.topic: conceptual
ms.prod: microsoft-edge
keywords: 渐进式 web 应用、PWA、Edge、Windows、PWABuilder、web 清单、服务工作人员、推送
ms.openlocfilehash: 065ced3afa8ecd4165325fd4f10a673d86c72fa7
ms.sourcegitcommit: be76feed0d616a96c77ea2748a9f0d6c0c06284b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2020
ms.locfileid: "11103922"
---
# <span data-ttu-id="1a03b-104"> (Chromium 的渐进式 Web 应用入门) </span><span class="sxs-lookup"><span data-stu-id="1a03b-104">Get started with Progressive Web Apps (Chromium)</span></span>  

<span data-ttu-id="1a03b-105">渐进式 Web 应用 \ (PWAs \ ) 是 [逐渐增强][WikiProgressiveEnhancement]的 web 应用。</span><span class="sxs-lookup"><span data-stu-id="1a03b-105">Progressive Web Apps \(PWAs\) are web apps that are [progressively enhanced][WikiProgressiveEnhancement].</span></span>  <span data-ttu-id="1a03b-106">渐进式增强包括类似应用的功能，例如安装、脱机支持和推送通知。</span><span class="sxs-lookup"><span data-stu-id="1a03b-106">The progressive enhancements include app-like features, such as installation, offline support, and push notifications.</span></span>  <span data-ttu-id="1a03b-107">你还可以将 PWA 打包到应用商店。</span><span class="sxs-lookup"><span data-stu-id="1a03b-107">You may also package your PWA for app stores.</span></span>  <span data-ttu-id="1a03b-108">可能的应用商店包括 Microsoft Store、Google Play、Mac 应用商店等。</span><span class="sxs-lookup"><span data-stu-id="1a03b-108">Possible app stores include the Microsoft Store, Google Play, Mac App Store, and more.</span></span>  <span data-ttu-id="1a03b-109">Microsoft Store 是内置于 Windows 10 的商业应用商店。</span><span class="sxs-lookup"><span data-stu-id="1a03b-109">The Microsoft Store is the commercial app store built into Windows 10.</span></span>  

<span data-ttu-id="1a03b-110">下面的指南通过创建一个简单的 web 应用并将其作为 PWA 进行扩展，为你提供了 PWA 基础知识的概述。</span><span class="sxs-lookup"><span data-stu-id="1a03b-110">The following guide gives you an overview of PWA basics by creating a simple web app and extending it as a PWA.</span></span>  <span data-ttu-id="1a03b-111">已完成的项目跨新式浏览器工作。</span><span class="sxs-lookup"><span data-stu-id="1a03b-111">The finished project works across modern browsers.</span></span>  

> [!TIP]
> <span data-ttu-id="1a03b-112">你可以使用 [PWABuilder][PwaBuilder] 创建新的 pwa、增强现有 pwa 或将 pwa 打包到应用商店。</span><span class="sxs-lookup"><span data-stu-id="1a03b-112">You may use [PWABuilder][PwaBuilder] to create a new PWA, enhance your existing PWA, or package your PWA for app stores.</span></span>  

## <span data-ttu-id="1a03b-113">必备条件</span><span class="sxs-lookup"><span data-stu-id="1a03b-113">Prerequisites</span></span>  

*   <span data-ttu-id="1a03b-114">使用 [Visual Studio 代码][VisualstudioCodeMain] 编辑 PWA 源代码。</span><span class="sxs-lookup"><span data-stu-id="1a03b-114">Use [Visual Studio Code][VisualstudioCodeMain] to edit your PWA source code.</span></span>  
*   <span data-ttu-id="1a03b-115">使用 [Node.js][NodejsMain] 作为本地 web 服务器。</span><span class="sxs-lookup"><span data-stu-id="1a03b-115">Use [Node.js][NodejsMain] as your local web server.</span></span>  

## <span data-ttu-id="1a03b-116">创建基本 web 应用</span><span class="sxs-lookup"><span data-stu-id="1a03b-116">Create a basic web app</span></span>  

<span data-ttu-id="1a03b-117">若要创建空的 web 应用，请按照 [节点 Express 应用生成器][ExpressjsApplicationGenerator]中的步骤进行操作，并为你的应用命名 `MySamplePwa` 。</span><span class="sxs-lookup"><span data-stu-id="1a03b-117">To create an empty web app, follow the steps in [Node Express App Generator][ExpressjsApplicationGenerator], and name your app `MySamplePwa`.</span></span>  

<span data-ttu-id="1a03b-118">在提示符下，运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="1a03b-118">In the prompt, run the following commands.</span></span>  

```shell
npx express-generator --no-view
```  

```shell
npm install
```  

<span data-ttu-id="1a03b-119">这些命令将创建一个空 web 应用并安装任何依赖项。</span><span class="sxs-lookup"><span data-stu-id="1a03b-119">The commands create an empty web app and install any dependencies.</span></span>  

<span data-ttu-id="1a03b-120">现在，你有了一个简单的功能 web 应用。</span><span class="sxs-lookup"><span data-stu-id="1a03b-120">You now have a simple, functional web app.</span></span>  <span data-ttu-id="1a03b-121">若要启动 web 应用，请运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="1a03b-121">To start your web app, run the following command.</span></span>  

```shell
npm start
```  

<span data-ttu-id="1a03b-122">现在，浏览以 `http://localhost:3000` 查看你的新 web 应用。</span><span class="sxs-lookup"><span data-stu-id="1a03b-122">Now browse to `http://localhost:3000` to view your new web app.</span></span>  

:::image type="complex" source="./media/vs-nodejs-express-index.png" alt-text="在 localhost 上运行新的 PWA" lightbox="./media/vs-nodejs-express-index.png":::
   <span data-ttu-id="1a03b-124">在 localhost 上运行新的 PWA</span><span class="sxs-lookup"><span data-stu-id="1a03b-124">Running your new PWA on localhost</span></span>
:::image-end:::

## <span data-ttu-id="1a03b-125">开始构建 PWA</span><span class="sxs-lookup"><span data-stu-id="1a03b-125">Get started building a PWA</span></span>  

<span data-ttu-id="1a03b-126">既然你已拥有简单的 web 应用，请通过为 PWAs 添加三个要求将其作为 PWA 扩展。</span><span class="sxs-lookup"><span data-stu-id="1a03b-126">Now that you have a simple web app, extend it as a PWA by adding the three requirements for PWAs</span></span><!--[3 requirements for PWAs][PwaEdgehtmlIndexRequirements]--><span data-ttu-id="1a03b-127">： [HTTPS](#step-1---use-https)、 [Web 应用清单](#step-2---create-a-web-app-manifest)和 [服务工作人员](#step-3---add-a-service-worker)。</span><span class="sxs-lookup"><span data-stu-id="1a03b-127">: [HTTPS](#step-1---use-https), a [Web App Manifest](#step-2---create-a-web-app-manifest), and a [Service Worker](#step-3---add-a-service-worker).</span></span>  

### <span data-ttu-id="1a03b-128">步骤 1-使用 HTTPS</span><span class="sxs-lookup"><span data-stu-id="1a03b-128">Step 1 - Use HTTPS</span></span>  

<span data-ttu-id="1a03b-129">PWA 平台的关键部分（如 [服务工作者][MDNServiceWorkerApi]）需要使用 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="1a03b-129">Key parts of the PWA platform, such as [Service Workers][MDNServiceWorkerApi], require the use of HTTPS.</span></span>  <span data-ttu-id="1a03b-130">当 PWA 进入活动时，必须将其发布到 HTTPS URL。</span><span class="sxs-lookup"><span data-stu-id="1a03b-130">When your PWA goes live, you must publish it to an HTTPS URL.</span></span>  

<span data-ttu-id="1a03b-131">出于调试目的，Microsoft Edge 还允许 `http://localhost` 使用 PWA api。</span><span class="sxs-lookup"><span data-stu-id="1a03b-131">For debugging purposes, Microsoft Edge also permits `http://localhost` to use the PWA APIs.</span></span>  

<span data-ttu-id="1a03b-132">将[web 应用作为实时网站发布][VisualStudioNodejsTutorialPublishAzureAppService]，但确保服务器已配置为使用 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="1a03b-132">[Publish your web app as a live site][VisualStudioNodejsTutorialPublishAzureAppService], but ensure your server is configured for HTTPS.</span></span>  <span data-ttu-id="1a03b-133">例如，你可以创建一个 [Azure 免费帐户][AzureCreateFreeAccount]。</span><span class="sxs-lookup"><span data-stu-id="1a03b-133">For example, you may create an [Azure free account][AzureCreateFreeAccount].</span></span>  <span data-ttu-id="1a03b-134">在 [Microsoft Azure 应用服务][AzureWebApps] 上托管你的网站，并且默认情况下它通过 HTTPS 提供。</span><span class="sxs-lookup"><span data-stu-id="1a03b-134">Host your site on the [Microsoft Azure App Service][AzureWebApps] and it is served over HTTPS by default.</span></span>  

<span data-ttu-id="1a03b-135">下面的指南，用于 `http://localhost` 构建 PWA。</span><span class="sxs-lookup"><span data-stu-id="1a03b-135">The following guide, use `http://localhost` to build your PWA.</span></span>  

### <span data-ttu-id="1a03b-136">步骤 2-创建 Web 应用部件清单</span><span class="sxs-lookup"><span data-stu-id="1a03b-136">Step 2 - Create a Web App Manifest</span></span>  

<span data-ttu-id="1a03b-137">[Web 应用清单][MDNWebAppManifest]是一个 JSON 文件，其中包含有关你的应用的元数据，例如名称、说明、图标等。</span><span class="sxs-lookup"><span data-stu-id="1a03b-137">A [Web App Manifest][MDNWebAppManifest] is a JSON file containing metadata about your app, such as name, description, icons, and more.</span></span>  

<span data-ttu-id="1a03b-138">若要向 web 应用添加应用清单，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="1a03b-138">To add an app manifest to the web app:</span></span>  

1.  <span data-ttu-id="1a03b-139">在 Visual Studio 代码中，选择 "**文件**  >  **打开文件夹**"，然后选择 `MySamplePwa` 之前创建的目录。</span><span class="sxs-lookup"><span data-stu-id="1a03b-139">In Visual Studio Code, choose **File** > **Open Folder** and choose the `MySamplePwa` directory you created earlier.</span></span>  
1.  <span data-ttu-id="1a03b-140">选择 `Ctrl` + `N` 以创建新文件，并粘贴以下代码片段。</span><span class="sxs-lookup"><span data-stu-id="1a03b-140">Select `Ctrl`+`N` to create a new file, and paste in the following code snippet.</span></span>  
    
    ```json
    {
        "lang": "en-us",
        "name": "My Sample PWA",
        "short_name": "SamplePWA",
        "description": "A sample PWA for testing purposes",
        "start_url": "/",
        "background_color": "#2f3d58",
        "theme_color": "#2f3d58",        
        "orientation": "any",
        "display": "standalone",
        "icons": [
            {
                "src": "/icon512.png",
                "sizes": "512x512"
            }
        ]
    }
    ```  
    
1.  <span data-ttu-id="1a03b-141">将文件另存为 `/MySamplePwa/public/manifest.json` 。</span><span class="sxs-lookup"><span data-stu-id="1a03b-141">Save the file as `/MySamplePwa/public/manifest.json`.</span></span>  
1.  <span data-ttu-id="1a03b-142">添加一个名为的512x512 应用图标图像 `icon512.png` `/MySamplePwa/public/images` 。</span><span class="sxs-lookup"><span data-stu-id="1a03b-142">Add a 512x512 app icon image named `icon512.png` to `/MySamplePwa/public/images`.</span></span>  <span data-ttu-id="1a03b-143">你可以使用 [示例图像][ImagePwa] 进行测试。</span><span class="sxs-lookup"><span data-stu-id="1a03b-143">You may use the [sample image][ImagePwa] for testing purposes.</span></span>  
1.  <span data-ttu-id="1a03b-144">在 Visual Studio 代码中，打开 `/public/index.html` 并在标记内添加以下代码段 `<head>` 。</span><span class="sxs-lookup"><span data-stu-id="1a03b-144">In Visual Studio Code, open `/public/index.html`, and add the following code snippet inside the `<head>` tag.</span></span>  
    
    ```html
    <link rel="manifest" href="/manifest.json">
    ```   
    
### <span data-ttu-id="1a03b-145">步骤 3-添加服务工作人员</span><span class="sxs-lookup"><span data-stu-id="1a03b-145">Step 3 - Add a Service Worker</span></span>  

<span data-ttu-id="1a03b-146">服务工作者是 PWAs 背后的关键技术，支持诸如离线支持、高级缓存和运行后台任务的方案，以前限制为本机应用。</span><span class="sxs-lookup"><span data-stu-id="1a03b-146">Service workers are the key technology behind PWAs, enabling scenarios like offline support, advanced caching, and running background tasks previously limited to native apps.</span></span>  

<span data-ttu-id="1a03b-147">服务工作人员是从你的 web 应用截取网络请求的后台任务。</span><span class="sxs-lookup"><span data-stu-id="1a03b-147">Service workers are background tasks that intercept network requests from your web app.</span></span>  <span data-ttu-id="1a03b-148">服务工作人员会尝试完成任务，即使你的 PWA 未在运行。</span><span class="sxs-lookup"><span data-stu-id="1a03b-148">Service workers attempt to complete tasks, even when your PWA is not running.</span></span>  <span data-ttu-id="1a03b-149">任务包括以下操作。</span><span class="sxs-lookup"><span data-stu-id="1a03b-149">Tasks include the following actions.</span></span>  

*   <span data-ttu-id="1a03b-150">从缓存中服务请求的资源</span><span class="sxs-lookup"><span data-stu-id="1a03b-150">Serving requested resources from a cache</span></span>  
*   <span data-ttu-id="1a03b-151">发送推送通知</span><span class="sxs-lookup"><span data-stu-id="1a03b-151">Sending push notifications</span></span>  
*   <span data-ttu-id="1a03b-152">运行后台获取任务</span><span class="sxs-lookup"><span data-stu-id="1a03b-152">Running background fetch tasks</span></span>  
*   <span data-ttu-id="1a03b-153">提示标记图标</span><span class="sxs-lookup"><span data-stu-id="1a03b-153">Badging icons</span></span>  
*   <span data-ttu-id="1a03b-154">及更多</span><span class="sxs-lookup"><span data-stu-id="1a03b-154">and more</span></span>  

<span data-ttu-id="1a03b-155">服务工作人员在特殊的 JavaScript 文件中定义。</span><span class="sxs-lookup"><span data-stu-id="1a03b-155">Service workers are defined in a special JavaScript file.</span></span>  <span data-ttu-id="1a03b-156">有关详细信息，请导航到 [使用服务工作人员][MDNUsingServiceWorkers] 和 [服务工作者 API][MDNServiceWorkerApi]。</span><span class="sxs-lookup"><span data-stu-id="1a03b-156">For more information, navigate to [Using Service Workers][MDNUsingServiceWorkers] and [Service Worker API][MDNServiceWorkerApi].</span></span>  

<span data-ttu-id="1a03b-157">若要在你的项目中生成服务工作人员，请使用来自[PWA 生成器][PwaBuilderServiceWorker]的**第一网络**服务工作人员食谱。</span><span class="sxs-lookup"><span data-stu-id="1a03b-157">To build a service worker in your project, use the **Cache-first network** service worker recipe from [PWA Builder][PwaBuilderServiceWorker].</span></span>  

1.  <span data-ttu-id="1a03b-158">导航到 [pwabuilder.com/serviceworker][PwaBuilderServiceWorker]，选择 **缓存第一个网络** 服务工作人员，然后选择 " **下载** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="1a03b-158">Navigate to [pwabuilder.com/serviceworker][PwaBuilderServiceWorker], select the **Cache-first network** service worker, and select the **Download** button.</span></span>  <span data-ttu-id="1a03b-159">下载的文件包含以下文件：</span><span class="sxs-lookup"><span data-stu-id="1a03b-159">The downloaded file contains the following files:</span></span>
    
    *   `pwabuilder-sw-register.js`  
    *   `pwabuilder-sw.js`  
    
1.  <span data-ttu-id="1a03b-160">将下载的文件复制到 `public` web 应用项目中的文件夹。</span><span class="sxs-lookup"><span data-stu-id="1a03b-160">Copy the downloaded files to the `public` folder in your web app project.</span></span>  
    
1.  <span data-ttu-id="1a03b-161">在 Visual Studio 代码中，打开 `/public/index.html` 并在标记内添加以下代码段 `<head>` 。</span><span class="sxs-lookup"><span data-stu-id="1a03b-161">In Visual Studio Code, open `/public/index.html` and add the following code snippet inside the `<head>` tag.</span></span>  
    
    ```html
    <script type="module" src="/pwabuilder-sw-register.js"></script>
    ```  
    
<span data-ttu-id="1a03b-162">你的 web 应用现在有一个使用缓存第一个策略的服务工作人员。</span><span class="sxs-lookup"><span data-stu-id="1a03b-162">Your web app now has a service worker that uses the cache-first strategy.</span></span>  <span data-ttu-id="1a03b-163">您的新服务工作者首先从缓存中获取资源，并且仅在需要时从网络中获取资源。</span><span class="sxs-lookup"><span data-stu-id="1a03b-163">You new service worker fetches resources from the cache first, and from the network only as needed.</span></span>  <span data-ttu-id="1a03b-164">缓存的资源包括图像、JavaScript、CSS 和 HTML。</span><span class="sxs-lookup"><span data-stu-id="1a03b-164">Cached resources include images, JavaScript, CSS, and HTML.</span></span>

<span data-ttu-id="1a03b-165">使用以下步骤确认你的服务工作人员运行。</span><span class="sxs-lookup"><span data-stu-id="1a03b-165">Use the following steps to confirm that your service worker runs.</span></span>  

1.  <span data-ttu-id="1a03b-166">使用导航到你的 web 应用 `http://localhost:3000` 。</span><span class="sxs-lookup"><span data-stu-id="1a03b-166">Navigate to your web app using `http://localhost:3000`.</span></span>  <span data-ttu-id="1a03b-167">如果你的 web 应用不可用，请运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="1a03b-167">If your web app is not available, run the following command.</span></span>   
    
    ```shell
    npm start
    ```
    
1.  <span data-ttu-id="1a03b-168">在 Microsoft Edge 中，选择 `F12` 以打开 Microsoft Edge DevTools。</span><span class="sxs-lookup"><span data-stu-id="1a03b-168">In Microsoft Edge, select `F12` to open the Microsoft Edge DevTools.</span></span>  <span data-ttu-id="1a03b-169">选择 " **应用程序**"，然后选择 " **服务工作人员** " 以查看服务工作人员。</span><span class="sxs-lookup"><span data-stu-id="1a03b-169">Select **Application**, then **Service Workers** to view the service workers.</span></span>  <span data-ttu-id="1a03b-170">如果未显示服务工作人员，请刷新页面。</span><span class="sxs-lookup"><span data-stu-id="1a03b-170">If the service worker is not displayed, refresh the page.</span></span>  
     
    :::image type="complex" source="./media/devtools-sw-overview.png" alt-text="在 localhost 上运行新的 PWA" lightbox="./media/devtools-sw-overview.png":::
       <span data-ttu-id="1a03b-172">Microsoft Edge DevTools 服务工作人员概述</span><span class="sxs-lookup"><span data-stu-id="1a03b-172">Microsoft Edge DevTools Service Worker overview</span></span>
    :::image-end:::
    
1.  <span data-ttu-id="1a03b-173">通过展开 **缓存存储** 来查看服务工作人员缓存并选择 **pwabuilder-precache**。</span><span class="sxs-lookup"><span data-stu-id="1a03b-173">View the service worker cache by expanding **Cache Storage** and select **pwabuilder-precache**.</span></span>  <span data-ttu-id="1a03b-174">应显示由服务工作人员缓存的所有资源。</span><span class="sxs-lookup"><span data-stu-id="1a03b-174">All of the resources cached by the service worker should be displayed.</span></span>  <span data-ttu-id="1a03b-175">由服务工作人员缓存的资源包括应用图标、应用清单、CSS 和 JavaScript 文件。</span><span class="sxs-lookup"><span data-stu-id="1a03b-175">The resources cached by the service worker include the app icon, app manifest, CSS, and JavaScript files.</span></span>  
    
    :::image type="complex" source="./media/devtools-cache.png" alt-text="在 localhost 上运行新的 PWA" lightbox="./media/devtools-cache.png":::
       <span data-ttu-id="1a03b-177">Microsoft Edge DevTools 中的服务工作人员缓存 (F12) </span><span class="sxs-lookup"><span data-stu-id="1a03b-177">Service Worker cache in Microsoft Edge DevTools (F12)</span></span>
    :::image-end:::
    
1.  <span data-ttu-id="1a03b-178">以脱机应用的形式尝试 PWA。</span><span class="sxs-lookup"><span data-stu-id="1a03b-178">Try your PWA as an offline app.</span></span>  <span data-ttu-id="1a03b-179">在 Microsoft Edge DevTools \ (`F12` \ ) 中，选择 " **网络** "，然后将 **联机** 状态更改为 " **脱机**"。</span><span class="sxs-lookup"><span data-stu-id="1a03b-179">In Microsoft Edge DevTools \(`F12`\), choose **Network** then change the **Online** status to **Offline**.</span></span>  
    
    :::image type="complex" source="./media/devtools-offline.png" alt-text="在 localhost 上运行新的 PWA" lightbox="./media/devtools-offline.png":::
       <span data-ttu-id="1a03b-181">在 Microsoft Edge DevTools 中将应用设置为脱机模式</span><span class="sxs-lookup"><span data-stu-id="1a03b-181">Setting app to offline mode in Microsoft Edge DevTools</span></span>
    :::image-end:::
    
1.  <span data-ttu-id="1a03b-182">刷新你的应用，并且它应显示用于从缓存中为应用的资源提供服务的脱机机制。</span><span class="sxs-lookup"><span data-stu-id="1a03b-182">Refresh your app and it should display the offline mechanism for serving the resources of your app from the cache.</span></span>  
    
    :::image type="complex" source="./media/vs-nodejs-express-index.png" alt-text="在 localhost 上运行新的 PWA" lightbox="./media/vs-nodejs-express-index.png":::
       <span data-ttu-id="1a03b-184">PWA 在脱机状态下运行</span><span class="sxs-lookup"><span data-stu-id="1a03b-184">PWA running offline</span></span>
    :::image-end:::
    
## <span data-ttu-id="1a03b-185">向 PWA 添加推送通知</span><span class="sxs-lookup"><span data-stu-id="1a03b-185">Add push notifications to your PWA</span></span>  

<span data-ttu-id="1a03b-186">你可以通过完成以下任务来创建支持推送通知的 PWAs。</span><span class="sxs-lookup"><span data-stu-id="1a03b-186">You may create PWAs that support push notifications by completing the following tasks.</span></span>  

1.  <span data-ttu-id="1a03b-187">使用[推送 API][MDNPushApi]订阅消息服务</span><span class="sxs-lookup"><span data-stu-id="1a03b-187">Subscribe to a messaging service using the [Push API][MDNPushApi]</span></span>  
1.  <span data-ttu-id="1a03b-188">使用[通知 API][MDNNotificationsApi]从服务收到消息时显示 toast 消息</span><span class="sxs-lookup"><span data-stu-id="1a03b-188">Display a toast message when a message is received from the service using the [Notifications API][MDNNotificationsApi]</span></span>  
    
<span data-ttu-id="1a03b-189">与服务工作者一样，推送通知 Api 是基于标准的 Api。</span><span class="sxs-lookup"><span data-stu-id="1a03b-189">Just like with Service Workers, the push notification APIs are standards-based APIs.</span></span>  <span data-ttu-id="1a03b-190">推送通知 Api 跨浏览器运行，因此你的代码应在支持 PWAs 的任何位置工作。</span><span class="sxs-lookup"><span data-stu-id="1a03b-190">The push notification APIs work across browsers, so your code should work everywhere that PWAs are supported.</span></span>  <span data-ttu-id="1a03b-191">有关向服务器上的不同浏览器传递推送消息的详细信息，请导航到 " [Web 推送][NPMWebPush]"。</span><span class="sxs-lookup"><span data-stu-id="1a03b-191">For more information about delivering push messages to different browsers on your server, navigate to [Web-Push][NPMWebPush].</span></span>  

<span data-ttu-id="1a03b-192">以下步骤适用于由 Mozilla 提供的 [服务工作人员手册][ServiceWorkerCookbookPushRichDemo] 中的 "推送丰富" 演示，这些演示具有许多其他有用的 Web 推送和服务工作人员食谱。</span><span class="sxs-lookup"><span data-stu-id="1a03b-192">The following steps have been adapted from the Push Rich Demo in [Service Worker Cookbook][ServiceWorkerCookbookPushRichDemo] provided by Mozilla, which has a number of other useful Web Push and service worker recipes.</span></span>  

### <span data-ttu-id="1a03b-193">步骤 1-生成 VAPID 键</span><span class="sxs-lookup"><span data-stu-id="1a03b-193">Step 1 - Generate VAPID keys</span></span>  

<span data-ttu-id="1a03b-194">推送通知需要 VAPID \ (自愿应用服务器标识 \ ) 密钥才能向 PWA 客户端发送推送消息。</span><span class="sxs-lookup"><span data-stu-id="1a03b-194">Push notifications require VAPID \(Voluntary Application Server Identification\) keys in order to send push messages to the PWA client.</span></span>  <span data-ttu-id="1a03b-195">有多个 VAPID 密钥生成器可联机使用 (例如， [vapidkeys.com][VapidkeysMain]\ ) 。</span><span class="sxs-lookup"><span data-stu-id="1a03b-195">There are several VAPID key generators available online \(for example, [vapidkeys.com][VapidkeysMain]\).</span></span>  <span data-ttu-id="1a03b-196">生成后，应获取包含公钥和私钥的 JSON 对象。</span><span class="sxs-lookup"><span data-stu-id="1a03b-196">After generation, you should get a JSON object containing a public and private key.</span></span>  <span data-ttu-id="1a03b-197">保存注册表项，以便在以下教程中进行后续步骤。</span><span class="sxs-lookup"><span data-stu-id="1a03b-197">Save the keys for later steps in the following tutorial.</span></span>  <span data-ttu-id="1a03b-198">有关 VAPID 和 WebPush 的信息，请 [使用 Mozilla 推送服务导航到发送 VAPID 标识的 WebPush 通知][MozillaServicesSendingVapidWebPushNotificationsPush]。</span><span class="sxs-lookup"><span data-stu-id="1a03b-198">For information about VAPID and WebPush, navigate to [Sending VAPID identified WebPush Notifications using the Mozilla Push Service][MozillaServicesSendingVapidWebPushNotificationsPush].</span></span>  

### <span data-ttu-id="1a03b-199">步骤 2-订阅推送通知</span><span class="sxs-lookup"><span data-stu-id="1a03b-199">Step 2 - Subscribe to push notifications</span></span>  

<span data-ttu-id="1a03b-200">服务工作者处理 PWA 中的推送事件和 toast 通知交互。</span><span class="sxs-lookup"><span data-stu-id="1a03b-200">Service workers handle push events and toast notification interactions in your PWA.</span></span>  <span data-ttu-id="1a03b-201">若要将 PWA 订阅到服务器推送通知，请确保满足以下条件。</span><span class="sxs-lookup"><span data-stu-id="1a03b-201">To subscribe the PWA to server push notifications, ensure the following conditions are met.</span></span>  

*   <span data-ttu-id="1a03b-202">PWA 已安装、处于活动状态且已注册</span><span class="sxs-lookup"><span data-stu-id="1a03b-202">Your PWA is installed, active, and registered</span></span>  
*   <span data-ttu-id="1a03b-203">完成订阅任务的代码位于 PWA 的主 UI 线程上</span><span class="sxs-lookup"><span data-stu-id="1a03b-203">Your code to complete the subscription task is on the main UI thread of the PWA</span></span>  
*   <span data-ttu-id="1a03b-204">您有网络连接</span><span class="sxs-lookup"><span data-stu-id="1a03b-204">You have network connectivity</span></span>  
    
<span data-ttu-id="1a03b-205">在创建新推送订阅之前，Microsoft Edge 将验证用户是否已授予 PWA 接收通知的权限。</span><span class="sxs-lookup"><span data-stu-id="1a03b-205">Before a new push subscription is created, Microsoft Edge verifies if the user granted the PWA permission to receive notifications.</span></span>  <span data-ttu-id="1a03b-206">如果不是，则浏览器会提示用户提供权限。</span><span class="sxs-lookup"><span data-stu-id="1a03b-206">If not, the user is prompted by the browser for permission.</span></span>  <span data-ttu-id="1a03b-207">如果权限被拒绝，则 `registration.pushManager.subscribe` 引发必须处理的请求 `DOMException` 。</span><span class="sxs-lookup"><span data-stu-id="1a03b-207">If the permission is denied, the request to `registration.pushManager.subscribe` throws a `DOMException`, which must be handled.</span></span>  <span data-ttu-id="1a03b-208">有关权限管理的详细信息，请导航到 [Microsoft Edge 中的推送通知][WindowsBlogsWebNotificationsEdge]。</span><span class="sxs-lookup"><span data-stu-id="1a03b-208">For more on permission management, navigate to [Push Notifications in Microsoft Edge][WindowsBlogsWebNotificationsEdge].</span></span>  

<span data-ttu-id="1a03b-209">在 `pwabuilder-sw-register.js` 文件中，附加以下代码片段。</span><span class="sxs-lookup"><span data-stu-id="1a03b-209">In your `pwabuilder-sw-register.js` file, append the following code snippet.</span></span>  

```javascript
// Ask the user for permission to send push notifications.
navigator.serviceWorker.ready
    .then(function (registration) {
        // Check if the user has an existing subscription
        return registration.pushManager.getSubscription()
            .then(function (subscription) {
                if (subscription) {
                    return subscription;
                }
                
                const vapidPublicKey = "PASTE YOUR PUBLIC VAPID KEY HERE";             
                return registration.pushManager.subscribe({
                    userVisibleOnly: true,
                    applicationServerKey: urlBase64ToUint8Array(vapidPublicKey)
                });
            });
    });

// Utility function for browser interoperability
function urlBase64ToUint8Array(base64String) {
    var padding = '='.repeat((4 - base64String.length % 4) % 4);
    var base64 = (base64String + padding)
        .replace(/\-/g, '+')
        .replace(/_/g, '/');
        
    var rawData = window.atob(base64);
    var outputArray = new Uint8Array(rawData.length);
    
    for (var i = 0; i < rawData.length; ++i) {
        outputArray[i] = rawData.charCodeAt(i);
    }
    return outputArray;
}
```  

<span data-ttu-id="1a03b-210">有关详细信息，请导航到 [PushManager][MDNPushManager] 和 [Web 推送][NPMWebPushUsage]。</span><span class="sxs-lookup"><span data-stu-id="1a03b-210">For more information, navigate to [PushManager][MDNPushManager] and [Web-Push][NPMWebPushUsage].</span></span>  

### <span data-ttu-id="1a03b-211">步骤 3-侦听推送通知</span><span class="sxs-lookup"><span data-stu-id="1a03b-211">Step 3 - Listen for push notifications</span></span>  

<span data-ttu-id="1a03b-212">在你的 PWA 中创建订阅后，向服务工作人员添加处理程序以响应推送事件。</span><span class="sxs-lookup"><span data-stu-id="1a03b-212">After a subscription is created in your PWA, add handlers to the service worker to respond to push events.</span></span>  <span data-ttu-id="1a03b-213">将从服务器发送推送事件以显示 toast 通知。</span><span class="sxs-lookup"><span data-stu-id="1a03b-213">Push event are sent from the server to display toast notifications.</span></span>  <span data-ttu-id="1a03b-214">Toast 通知显示已接收邮件的数据。</span><span class="sxs-lookup"><span data-stu-id="1a03b-214">Toast notifications display data for a received message.</span></span>  <span data-ttu-id="1a03b-215">若要完成以下任务，必须添加一个 click 处理程序。</span><span class="sxs-lookup"><span data-stu-id="1a03b-215">To complete the following tasks, you must add a click handler.</span></span>  

*   <span data-ttu-id="1a03b-216">关闭 toast 通知</span><span class="sxs-lookup"><span data-stu-id="1a03b-216">Dismiss the toast notification</span></span>  
*   <span data-ttu-id="1a03b-217">打开、焦点或打开所有打开的窗口并将焦点集中在该窗口</span><span class="sxs-lookup"><span data-stu-id="1a03b-217">Open, focus, or open and focus any open windows</span></span>  
*   <span data-ttu-id="1a03b-218">打开并焦点一个新窗口以显示 PWA 客户端页面</span><span class="sxs-lookup"><span data-stu-id="1a03b-218">Open and focus a new window to display a PWA client page</span></span>  
    
<span data-ttu-id="1a03b-219">在 `pwabuilder-sw.js` 文件中，添加以下处理程序。</span><span class="sxs-lookup"><span data-stu-id="1a03b-219">In your `pwabuilder-sw.js` file, add the following handlers.</span></span>  

```javascript
// Respond to a server push with a user notification.
self.addEventListener('push', function (event) {
    if (Notification.permission === "granted") {
        const notificationText = event.data.text();
        const showNotification = self.registration.showNotification('Sample PWA', {
            body: notificationText,
            icon: 'images/icon512.png'
        });
        // Ensure the toast notification is displayed before exiting the function.
        event.waitUntil(showNotification);
    }
});

// Respond to the user selecting the toast notification.
self.addEventListener('notificationclick', function (event) {
    console.log('On notification click: ', event.notification.tag);
    event.notification.close();
    
    // This attempts to display the current notification if it is already open and then focuses on it.
    event.waitUntil(clients.matchAll({
        type: 'window'
    }).then(function (clientList) {
        for (var i = 0; i < clientList.length; i++) {
            var client = clientList[i];
            if (client.url == 'http://localhost:1337/' && 'focus' in client)
                return client.focus();
        }
        if (clients.openWindow)
            return clients.openWindow('/');
    }));
});
```  

### <span data-ttu-id="1a03b-220">步骤 4-试用</span><span class="sxs-lookup"><span data-stu-id="1a03b-220">Step 4 - Try it out</span></span>  

<span data-ttu-id="1a03b-221">若要测试 PWA 的推送通知，请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="1a03b-221">To test push notifications for your PWA, complete the following steps.</span></span>  

1.  <span data-ttu-id="1a03b-222">在上导航到你的 PWA `http://localhost:3000` 。</span><span class="sxs-lookup"><span data-stu-id="1a03b-222">Navigate to your PWA at `http://localhost:3000`.</span></span>  <span data-ttu-id="1a03b-223">当你的服务工作者激活并尝试将你的 PWA 订阅到推送通知时，Microsoft Edge 会提示你允许 PWA 显示通知。</span><span class="sxs-lookup"><span data-stu-id="1a03b-223">When your service worker activates and attempts to subscribe your PWA to push notifications, Microsoft Edge prompts you to allow your PWA to show notifications.</span></span>  <span data-ttu-id="1a03b-224">选择 " **允许**"。</span><span class="sxs-lookup"><span data-stu-id="1a03b-224">Select **Allow**.</span></span>  
    
    :::image type="complex" source="./media/notification-permission.png" alt-text="在 localhost 上运行新的 PWA" lightbox="./media/notification-permission.png":::
       <span data-ttu-id="1a03b-226">用于启用通知的权限对话框</span><span class="sxs-lookup"><span data-stu-id="1a03b-226">Permission dialog for enabling notifications</span></span>
    :::image-end:::
    
1.  <span data-ttu-id="1a03b-227">模拟服务器端推送通知。</span><span class="sxs-lookup"><span data-stu-id="1a03b-227">Simulate a server-side push notification.</span></span>  <span data-ttu-id="1a03b-228">`http://localhost:3000`在浏览器中打开 PWA 后，选择 `F12` 以打开 DevTools。</span><span class="sxs-lookup"><span data-stu-id="1a03b-228">With your PWA opened at `http://localhost:3000` in your browser, select `F12` to open the DevTools.</span></span>  <span data-ttu-id="1a03b-229">选择 "**应用程序**  >  **服务工作人员**  >  **推送**" 以向你的 PWA 发送测试推送通知。</span><span class="sxs-lookup"><span data-stu-id="1a03b-229">Choose **Application** > **Service Worker** > **Push** to send a test push notification to your PWA.</span></span>  
    :::row:::
       :::column span="":::
          <span data-ttu-id="1a03b-230">任务栏旁边应显示推送通知。</span><span class="sxs-lookup"><span data-stu-id="1a03b-230">A push notification should display near the taskbar.</span></span>  
          
          :::image type="complex" source="./media/devtools-push.png" alt-text="在 localhost 上运行新的 PWA" lightbox="./media/devtools-push.png":::
             <span data-ttu-id="1a03b-232">推送来自 DevTools 的通知</span><span class="sxs-lookup"><span data-stu-id="1a03b-232">Push a notification from DevTools</span></span>  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          <span data-ttu-id="1a03b-233">如果不选择 \ (或激活 \ ) toast 通知，系统会在几秒钟后自动关闭它并将其排队到 Windows 操作中心。</span><span class="sxs-lookup"><span data-stu-id="1a03b-233">If you do not select \(or activate\) a toast notification, the system automatically dismisses it after several seconds and queues it in your Windows Action Center.</span></span>  
          
          :::image type="complex" source="./media/windows-action-center.png" alt-text="在 localhost 上运行新的 PWA" lightbox="./media/windows-action-center.png":::
             <span data-ttu-id="1a03b-235">Windows 操作中心中的通知</span><span class="sxs-lookup"><span data-stu-id="1a03b-235">Notifications in Windows Action Center</span></span> :::image-end:::
       :::column-end:::
    :::row-end:::  
    
## <span data-ttu-id="1a03b-236">后续步骤</span><span class="sxs-lookup"><span data-stu-id="1a03b-236">Next steps</span></span>  

<span data-ttu-id="1a03b-237">以下步骤包括可帮助你理解构建现实世界 PWAs 的其他任务。</span><span class="sxs-lookup"><span data-stu-id="1a03b-237">The following steps include additional tasks to help you understand building real-world PWAs.</span></span>  

*   <span data-ttu-id="1a03b-238">管理和存储推送订阅</span><span class="sxs-lookup"><span data-stu-id="1a03b-238">Manage and store push subscriptions</span></span>  
*   <span data-ttu-id="1a03b-239">[加密][NPMWebPushEncrypt] 有效负载数据</span><span class="sxs-lookup"><span data-stu-id="1a03b-239">[Encrypt][NPMWebPushEncrypt] payload data</span></span>  
*   <span data-ttu-id="1a03b-240">响应式设计</span><span class="sxs-lookup"><span data-stu-id="1a03b-240">Responsive design</span></span>  
*   <span data-ttu-id="1a03b-241">深度链接</span><span class="sxs-lookup"><span data-stu-id="1a03b-241">Deep-linking</span></span>  
*   [<span data-ttu-id="1a03b-242">跨浏览器测试</span><span class="sxs-lookup"><span data-stu-id="1a03b-242">Cross-browser testing</span></span>][BrowserStackTestEdgeBrowser]  
*   <span data-ttu-id="1a03b-243">实现验证和测试做法，如 [Webhint][Webhint]</span><span class="sxs-lookup"><span data-stu-id="1a03b-243">Implement validation and testing practices such as [Webhint][Webhint]</span></span>  
   
## <span data-ttu-id="1a03b-244">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1a03b-244">See also</span></span>  

*   [<span data-ttu-id="1a03b-245">MDN web 文档上的渐进式 Web 应用</span><span class="sxs-lookup"><span data-stu-id="1a03b-245">Progressive Web Apps on MDN web docs</span></span>][MDNProgressiveWebApps]  
*   [<span data-ttu-id="1a03b-246">Web 上的渐进式 Web 应用</span><span class="sxs-lookup"><span data-stu-id="1a03b-246">Progressive Web Apps on web.dev</span></span>][WebDevProgressiveWebApps]  
*   <span data-ttu-id="1a03b-247">[作为渐进 Web 应用的黑客新闻阅读器][HackerNewsProgressiveWebApps] -比较不同的框架和性能模式，用于实现示例 \ (黑客新闻阅读器 \ ) PWA。</span><span class="sxs-lookup"><span data-stu-id="1a03b-247">[Hacker News readers as Progressive Web Apps][HackerNewsProgressiveWebApps] - Compares different frameworks and performance patterns for implementing a sample \(Hacker News reader\) PWA.</span></span>  
*   [<span data-ttu-id="1a03b-248">Myth Busting PWAs</span><span class="sxs-lookup"><span data-stu-id="1a03b-248">Myth Busting PWAs</span></span>][Davrous20191018MythBustingPwasNewEdgeEdition]  
*   [<span data-ttu-id="1a03b-249">渐进式 Web 应用的渐进式路线图</span><span class="sxs-lookup"><span data-stu-id="1a03b-249">A Progressive Roadmap for your Progressive Web App</span></span>][CloudfourThinksProgressiveRoadmapYourWebApp]  
*   [<span data-ttu-id="1a03b-250">具有渐进的 Web 应用的脱机文章</span><span class="sxs-lookup"><span data-stu-id="1a03b-250">Offline POSTs with Progressive Web Apps</span></span>][MediumWebEdgeOfflinePostsProgressiveWebApps]  
*   [<span data-ttu-id="1a03b-251">PWA 问答&</span><span class="sxs-lookup"><span data-stu-id="1a03b-251">PWA Q&A</span></span>][AaronGustafsonNotebookPwaQa]  
*   [<span data-ttu-id="1a03b-252">在网上打赌</span><span class="sxs-lookup"><span data-stu-id="1a03b-252">Betting on the Web</span></span>][JoretegBlogBettingWeb]  
*   [<span data-ttu-id="1a03b-253">命名渐进式 Web 应用</span><span class="sxs-lookup"><span data-stu-id="1a03b-253">Naming Progressive Web Apps</span></span>][Fberriman20170626NamingProgressiveWebApps]  
*   [<span data-ttu-id="1a03b-254">设计和构建不带框架 (第1部分) 的渐进式 Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="1a03b-254">Designing And Building A Progressive Web Application Without A Framework (Part 1)</span></span>][Smashingmagazine201907ProgressiveWebApplicationFrameworkPart1]  
*   [<span data-ttu-id="1a03b-255">设计和构建不带框架 (第2部分) 的渐进式 Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="1a03b-255">Designing And Building A Progressive Web Application Without A Framework (Part 2)</span></span>][Smashingmagazine201907ProgressiveWebApplicationFrameworkPart2]  
*   [<span data-ttu-id="1a03b-256">设计和构建不带框架 (第3部分) 的渐进式 Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="1a03b-256">Designing And Building A Progressive Web Application Without A Framework (Part 3)</span></span>][Smashingmagazine201907ProgressiveWebApplicationFrameworkPart3]  
    
<!-- image links -->  

[ImagePwa]: ./media/pwa.png  

<!-- links -->  

<!--[PwaEdgehtmlIndexRequirements]: ../progressive-web-apps-edgehtml/index.md#requirements "Requirements - Progressive Web Apps \(EdgeHTML\) on Windows | Microsoft Docs"  -->  

[VisualStudioNodejsTutorialPublishAzureAppService]: /azure/javascript/tutorial-vscode-azure-app-service-node-03 "使用 Visual Studio 代码将 Node.js 应用部署到 Azure |Microsoft 文档"  

[AzureCreateFreeAccount]: https://azure.microsoft.com/free "创建 Azure 免费帐户 |Microsoft Azure"  
[AzureWebApps]: https://azure.microsoft.com/services/app-service/web "Web Apps |Microsoft Azure"  

[WindowsBlogsWebNotificationsEdge]: https://blogs.windows.com/msedgedev/2016/05/16/web-notifications-microsoft-edge#UAbvU2ymUlHO8EUV.97 "Microsoft Edge 中的 Web 通知 |Windows 博客"  

[VisualstudioCodeMain]: https://code.visualstudio.com "Visual Studio 代码"  

[AaronGustafsonNotebookPwaQa]: https://www.aaron-gustafson.com/notebook/pwa-qa "PWA 问答&"  

[BrowserStackTestEdgeBrowser]: https://www.browserstack.com/test-on-microsoft-edge-browser "Windows 10 上的免费 Microsoft Edge 浏览器测试 |BrowserStack"  

[CloudfourThinksProgressiveRoadmapYourWebApp]: https://cloudfour.com/thinks/a-progressive-roadmap-for-your-progressive-web-app "渐进式 Web 应用的渐进式路线图"  

[Davrous20191018MythBustingPwasNewEdgeEdition]: https://www.davrous.com/2019/10/18/myth-busting-pwas-the-new-edge-edition "Myth Busting PWAs-新的边缘版本"  

[ExpressjsApplicationGenerator]: https://expressjs.com/starter/generator.html "Express 应用程序生成器 |明确" 

[Fberriman20170626NamingProgressiveWebApps]: https://fberriman.com/2017/06/26/naming-progressive-web-apps "命名渐进式 Web 应用"  

[HackerNewsProgressiveWebApps]: https://hnpwa.com "作为渐进式 Web 应用的黑客新闻阅读器"  

[JoretegBlogBettingWeb]: https://joreteg.com/blog/betting-on-the-web "在网上打赌"  

[MDNDedicatedWorkerGlobalScopePostMessage]: https://developer.mozilla.org/docs/Web/API/
[MDNNotificationsApi]: https://developer.mozilla.org/docs/Web/API/Notifications_API "通知 API |MDN"  
[MDNProgressiveWebApps]: https://developer.mozilla.org/Apps/Progressive "渐进式 web 应用 (PWAs) |MDN"  
[MDNPushApi]: https://developer.mozilla.org/docs/Web/API/Push_API "推送 API |MDN"  
[MDNPushManager]: https://developer.mozilla.org/docs/Web/API/PushManager "PushManager |MDN"  
[MDNServiceWorkerApi]: https://developer.mozilla.org/docs/Web/API/Service_Worker_API "服务工作者 API |MDN"  
[MDNUsingServiceWorkers]: https://developer.mozilla.org/docs/Web/API/Service_Worker_API/Using_Service_Workers "使用服务工作者 |MDN"  
[MDNWebAppManifest]: https://developer.mozilla.org/docs/Web/Manifest "Web App 清单 |MDN"  

[MediumWebEdgeOfflinePostsProgressiveWebApps]: https://medium.com/web-on-the-edge/offline-posts-with-progressive-web-apps-fc2dc4ad895 "具有渐进的 Web 应用的脱机文章"  

[MozillaServicesSendingVapidWebPushNotificationsPush]: https://blog.mozilla.org/services/2016/08/23/sending-vapid-identified-webpush-notifications-via-mozillas-push-service "通过 Mozilla 的推送服务发送 VAPID 标识的 WebPush 通知 |Mozilla 服务"  

[NodejsMain]: https://nodejs.org "Node.js"  

[NPMWebPush]: https://www.npmjs.com/package/web-push "web-推送 |npm"  
[NPMWebPushEncrypt]: https://www.npmjs.com/package/web-push#encryptuserpublickey-userauth-payload-contentencoding "加密 (userPublicKey、userAuth、负载、contentEncoding) web 推送 |NPM"  
[NPMWebPushUsage]: https://www.npmjs.com/package/web-push#usage "使用情况-web 推送 |NPM"  

[ProgressiveWebApps]: https://pwa.rocks "渐进式 Web 应用"  

[PwaBuilder]: https://www.pwabuilder.com "PWA 生成器"  
[PwaBuilderServiceWorker]: https://www.pwabuilder.com/serviceworker "服务工作人员 |PWA 生成器"  

[ServiceWorkerCookbookPushRichDemo]: https://serviceworke.rs/push-rich_demo.html "推送丰富的演示 |ServiceWorker 手册"  

[Smashingmagazine201907ProgressiveWebApplicationFrameworkPart1]: https://www.smashingmagazine.com/2019/07/progressive-web-application-pwa-framework-part-1 "设计和构建不带框架 (第1部分) 的渐进式 Web 应用程序 "  

[Smashingmagazine201907ProgressiveWebApplicationFrameworkPart2]: https://www.smashingmagazine.com/2019/07/progressive-web-application-pwa-framework-part-2 "设计和构建不带框架 (第2部分) 的渐进式 Web 应用程序 "  

[Smashingmagazine201907ProgressiveWebApplicationFrameworkPart3]: https://www.smashingmagazine.com/2019/07/progressive-web-application-pwa-framework-part-3 "设计和构建不带框架 (第3部分) 的渐进式 Web 应用程序 "  

[VapidkeysMain]: https://vapidkeys.com "安全 VAPID 密钥生成器 |VapidKeys" 

[Webhint]: https://webhint.io "webhint"  

[WebDevProgressiveWebApps]: https://developers.google.com/web/progressive-web-apps "渐进式 Web 应用 |web 开发"  

[WikiProgressiveEnhancement]: https://en.wikipedia.org/wiki/Progressive_enhancement "渐进式增强 |科"  
