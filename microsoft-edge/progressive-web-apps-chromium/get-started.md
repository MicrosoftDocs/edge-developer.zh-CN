---
description: 本指南概括介绍了如何在 Windows 上构建渐进式 web 应用的 PWA 基础知识和工具。
title: 渐进式 Web 应用（Chromium）入门
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/15/2020
ms.topic: conceptual
ms.prod: microsoft-edge
keywords: 渐进式 web 应用、PWA、Edge、Windows、PWABuilder、web 清单、服务工作人员、推送
ms.openlocfilehash: 6c5fa5d6af8494f33e11a545d5dde1264604c787
ms.sourcegitcommit: 136642396bb8094a535e203067ee429e60d31d25
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2020
ms.locfileid: "10659207"
---
# <span data-ttu-id="e52e0-104">渐进式 Web 应用（Chromium）入门</span><span class="sxs-lookup"><span data-stu-id="e52e0-104">Get started with Progressive Web Apps (Chromium)</span></span>  

<span data-ttu-id="e52e0-105">渐进式 Web 应用 \ （PWAs \）是通过类似应用的功能（如安装、脱机支持和推送通知）[逐渐增强][WikiProgressiveEnhancement]的 web 应用。</span><span class="sxs-lookup"><span data-stu-id="e52e0-105">Progressive Web Apps \(PWAs\) are web apps that are [progressively enhanced][WikiProgressiveEnhancement] with app-like features, such as installation, offline support, and push notifications.</span></span>  <span data-ttu-id="e52e0-106">你还可以将 PWA 打包到应用商店，包括 Microsoft Store 以及 Google Play、Mac 应用商店等。</span><span class="sxs-lookup"><span data-stu-id="e52e0-106">You may also packaged your PWA for app stores, including the Microsoft Store as well as Google Play, Mac App Store and more.</span></span>  <span data-ttu-id="e52e0-107">Microsoft Store 是内置于 Windows 10 的商业应用商店。</span><span class="sxs-lookup"><span data-stu-id="e52e0-107">The Microsoft Store is the commercial app store built into Windows 10.</span></span>  

<span data-ttu-id="e52e0-108">下面的指南通过创建一个简单的 web 应用并将其作为 PWA 进行扩展，为你提供了 PWA 基础知识的概述。</span><span class="sxs-lookup"><span data-stu-id="e52e0-108">The following guide gives you an overview of PWA basics by creating a simple web app and extending it as a PWA.</span></span>  <span data-ttu-id="e52e0-109">已完成的项目跨新式浏览器工作。</span><span class="sxs-lookup"><span data-stu-id="e52e0-109">The finished project works across modern browsers.</span></span>  

> [!TIP]
> <span data-ttu-id="e52e0-110">你可以使用[PWABuilder][PwaBuilder]创建新的 pwa、增强现有 pwa 或将 pwa 打包到应用商店。</span><span class="sxs-lookup"><span data-stu-id="e52e0-110">You may use [PWABuilder][PwaBuilder] to create a new PWA, enhance your existing PWA, or package your PWA for app stores.</span></span>  

## <span data-ttu-id="e52e0-111">必备条件</span><span class="sxs-lookup"><span data-stu-id="e52e0-111">Prerequisites</span></span>  

*   <span data-ttu-id="e52e0-112">使用[VS 代码][VisualstudioCodeMain]编辑 PWA 源代码。</span><span class="sxs-lookup"><span data-stu-id="e52e0-112">Use [VS Code][VisualstudioCodeMain] to edit your PWA source code.</span></span>  
*   <span data-ttu-id="e52e0-113">将[node.js][NodejsMain]用作本地 web 服务器。</span><span class="sxs-lookup"><span data-stu-id="e52e0-113">Use [Node.js][NodejsMain] as your local web server.</span></span>  

## <span data-ttu-id="e52e0-114">设置基本 web 应用</span><span class="sxs-lookup"><span data-stu-id="e52e0-114">Set up a basic web app</span></span>  

<span data-ttu-id="e52e0-115">若要创建空的 web 应用，请按照[节点 Express 应用生成器][ExpressjsApplicationGenerator]中的步骤进行操作，并为你的应用命名 `MySamplePwa` 。</span><span class="sxs-lookup"><span data-stu-id="e52e0-115">To create an empty web app, follow the steps in [Node Express App Generator][ExpressjsApplicationGenerator], and name your app `MySamplePwa`.</span></span>  

<span data-ttu-id="e52e0-116">在提示符下，运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="e52e0-116">In the prompt, run the following commands.</span></span>  

```shell
npx express-generator --no-view
```  

```shell
npm install
```  

<span data-ttu-id="e52e0-117">这些命令将创建一个空 web 应用并安装任何依赖项。</span><span class="sxs-lookup"><span data-stu-id="e52e0-117">The commands creates an empty web app and install any dependencies.</span></span>  

<span data-ttu-id="e52e0-118">现在，你有了一个简单的功能 web 应用。</span><span class="sxs-lookup"><span data-stu-id="e52e0-118">Now you have a simple, functional web app.</span></span>  <span data-ttu-id="e52e0-119">若要启动它，请运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="e52e0-119">To start it, run the following command.</span></span>  

```shell
npm start
```  

<span data-ttu-id="e52e0-120">现在，浏览以 `http://localhost:3000` 查看你的新 web 应用。</span><span class="sxs-lookup"><span data-stu-id="e52e0-120">Now browse to `http://localhost:3000` to view your new web app.</span></span>  

:::image type="complex" source="./media/vs-nodejs-express-index.png" alt-text="在 localhost 上运行新的 PWA":::
   <span data-ttu-id="e52e0-122">在 localhost 上运行新的 PWA</span><span class="sxs-lookup"><span data-stu-id="e52e0-122">Running your new PWA on localhost</span></span>
:::image-end:::

## <span data-ttu-id="e52e0-123">开始构建 PWA</span><span class="sxs-lookup"><span data-stu-id="e52e0-123">Get started building a PWA</span></span>  

<span data-ttu-id="e52e0-124">既然你已拥有简单的 web 应用，请通过为 PWAs 添加3个要求将其扩展为 PWA</span><span class="sxs-lookup"><span data-stu-id="e52e0-124">Now that you have a simple web app, extend it as a PWA by adding the 3 requirements for PWAs</span></span><!--[3 requirements for PWAs][PwaEdgehtmlIndexRequirements]--><span data-ttu-id="e52e0-125">： [HTTPS](#step-1---use-https)、 [Web 应用清单](#step-2---create-a-web-app-manifest)和[服务工作人员](#step-3---add-a-service-worker)。</span><span class="sxs-lookup"><span data-stu-id="e52e0-125">: [HTTPS](#step-1---use-https), a [Web App Manifest](#step-2---create-a-web-app-manifest), and a [Service Worker](#step-3---add-a-service-worker).</span></span>  

### <span data-ttu-id="e52e0-126">步骤 1-使用 HTTPS</span><span class="sxs-lookup"><span data-stu-id="e52e0-126">Step 1 - Use HTTPS</span></span>  

<span data-ttu-id="e52e0-127">PWA 平台的关键部分（如[服务工作者][MDNServiceWorkerApi]）需要使用 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="e52e0-127">Key parts of the PWA platform, such as [Service Workers][MDNServiceWorkerApi], require the use of HTTPS.</span></span>  <span data-ttu-id="e52e0-128">当 PWA 进入活动时，必须将其发布到 HTTPS URL。</span><span class="sxs-lookup"><span data-stu-id="e52e0-128">When your PWA goes live, you must publish it to an HTTPS URL.</span></span>  

<span data-ttu-id="e52e0-129">出于调试目的，Microsoft Edge 还允许 `http://localhost` 使用 PWA api。</span><span class="sxs-lookup"><span data-stu-id="e52e0-129">For debugging purposes, Microsoft Edge also permits `http://localhost` to use the PWA APIs.</span></span>  

<span data-ttu-id="e52e0-130">如果你将[web 应用作为活动网站发布][VisualStudioNodejsTutorialPublishAzureAppService]\ （例如，通过设置[Azure 免费帐户][AzureCreateFreeAccount]\），则必须确保你的服务器配置了 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="e52e0-130">If you [publish your web app as a live site][VisualStudioNodejsTutorialPublishAzureAppService] \(for example, by setting up an [Azure free account][AzureCreateFreeAccount]\), you must ensure your server is configured for HTTPS.</span></span>  <span data-ttu-id="e52e0-131">如果你使用[Microsoft Azure 应用服务][AzureWebApps]托管你的网站，则默认情况下它将通过 HTTPS 进行提供。</span><span class="sxs-lookup"><span data-stu-id="e52e0-131">If you use the [Microsoft Azure App Service][AzureWebApps] to host your site, it is served over HTTPS by default.</span></span>  

<span data-ttu-id="e52e0-132">下面的指南，用于 `http://localhost` 构建 PWA。</span><span class="sxs-lookup"><span data-stu-id="e52e0-132">The following guide, use `http://localhost` to build your PWA.</span></span>  

### <span data-ttu-id="e52e0-133">步骤 2-创建 Web 应用部件清单</span><span class="sxs-lookup"><span data-stu-id="e52e0-133">Step 2 - Create a Web App Manifest</span></span>  

<span data-ttu-id="e52e0-134">[Web 应用清单][MDNWebAppManifest]是一个 JSON 文件，其中包含有关你的应用的元数据，例如名称、说明、图标等。</span><span class="sxs-lookup"><span data-stu-id="e52e0-134">A [Web App Manifest][MDNWebAppManifest] is a JSON file containing metadata about your app, such as name, description, icons, and more.</span></span>  

<span data-ttu-id="e52e0-135">若要向 web 应用添加应用清单，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e52e0-135">To add an app manifest to the web app:</span></span>  

1.  <span data-ttu-id="e52e0-136">在 "与代码" 中，转到 "**文件**  >  **打开" 文件夹**，然后选择 `MySamplePwa` 之前创建的目录。</span><span class="sxs-lookup"><span data-stu-id="e52e0-136">In VS Code, go **File** > **Open Folder** and choose the `MySamplePwa` directory you created earlier.</span></span>  
1.  <span data-ttu-id="e52e0-137">按下 `Ctrl` + `N` 以创建一个新文件，然后粘贴以下代码片段。</span><span class="sxs-lookup"><span data-stu-id="e52e0-137">Press `Ctrl`+`N` to create a new file, and paste in the following code snippet.</span></span>  
    
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
    
1.  <span data-ttu-id="e52e0-138">将文件另存为 `/MySamplePwa/public/manifest.json` 。</span><span class="sxs-lookup"><span data-stu-id="e52e0-138">Save the file as `/MySamplePwa/public/manifest.json`.</span></span>  
1.  <span data-ttu-id="e52e0-139">添加一个名为的512x512 应用图标图像 `icon512.png` `/MySamplePwa/public/images` 。</span><span class="sxs-lookup"><span data-stu-id="e52e0-139">Add a 512x512 app icon image named `icon512.png` to `/MySamplePwa/public/images`.</span></span>  <span data-ttu-id="e52e0-140">你可以使用[示例图像][ImagePwa]进行测试。</span><span class="sxs-lookup"><span data-stu-id="e52e0-140">You may use the [sample image][ImagePwa] for testing purposes.</span></span>  
1.  <span data-ttu-id="e52e0-141">在 VS 代码中，打开 `/public/index.html` 并在标记内添加以下代码段 `<head>` 。</span><span class="sxs-lookup"><span data-stu-id="e52e0-141">In VS Code, open `/public/index.html`, and add the following code snippet inside the `<head>` tag.</span></span>  
    
    ```html
    <link rel="manifest" href="/manifest.json">
    ```   
    
### <span data-ttu-id="e52e0-142">步骤 3-添加服务工作人员</span><span class="sxs-lookup"><span data-stu-id="e52e0-142">Step 3 - Add a Service Worker</span></span>  

<span data-ttu-id="e52e0-143">服务工作者是 PWAs 背后的关键技术，支持诸如离线支持、高级缓存和运行后台任务的方案，以前限制为本机应用。</span><span class="sxs-lookup"><span data-stu-id="e52e0-143">Service workers are the key technology behind PWAs, enabling scenarios like offline support, advanced caching, and running background tasks previously limited to native apps.</span></span>  

<span data-ttu-id="e52e0-144">服务工作人员是从你的 web 应用截取网络请求的后台任务。</span><span class="sxs-lookup"><span data-stu-id="e52e0-144">Service workers are background tasks that intercept network requests from your web app.</span></span>  <span data-ttu-id="e52e0-145">它们执行任务，即使你的 PWA 未在运行，例如从缓存中服务所请求的资源、发送推送通知、运行后台提取任务、提示标记图标等。</span><span class="sxs-lookup"><span data-stu-id="e52e0-145">They perform tasks, even when your PWA is not running, such as serving requested resources from a cache, sending push notifications, running background fetch tasks, badging icons, and so on.</span></span>  <span data-ttu-id="e52e0-146">服务工作人员在特殊的 JavaScript 文件中定义。</span><span class="sxs-lookup"><span data-stu-id="e52e0-146">Service workers are defined in a special JavaScript file.</span></span>  <span data-ttu-id="e52e0-147">有关详细信息，请参阅[使用服务工作人员][MDNUsingServiceWorkers]和[服务工作器 API][MDNServiceWorkerApi]。</span><span class="sxs-lookup"><span data-stu-id="e52e0-147">For more information, see [Using Service Workers][MDNUsingServiceWorkers] and [Service Worker API][MDNServiceWorkerApi].</span></span>  

<span data-ttu-id="e52e0-148">若要在你的项目中生成服务工作人员，请使用来自[PWA 生成器][PwaBuilderServiceWorker]的**第一网络**服务工作人员食谱。</span><span class="sxs-lookup"><span data-stu-id="e52e0-148">To build a service worker in your project, use the **Cache-first network** service worker recipe from [PWA Builder][PwaBuilderServiceWorker].</span></span>  

1.  <span data-ttu-id="e52e0-149">导航到[pwabuilder.com/serviceworker][PwaBuilderServiceWorker]，选择**缓存第一个网络**服务工作人员，然后选择 "**下载**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="e52e0-149">Navigate to [pwabuilder.com/serviceworker][PwaBuilderServiceWorker], select the **Cache-first network** service worker, and select the **Download** button.</span></span>  <span data-ttu-id="e52e0-150">下载的文件包含以下文件：</span><span class="sxs-lookup"><span data-stu-id="e52e0-150">The downloaded file contains the following files:</span></span>
    
    *   `pwabuilder-sw-register.js`  
    *   `pwabuilder-sw.js`  
    
1.  <span data-ttu-id="e52e0-151">将下载的文件复制到 `public` web 应用项目中的文件夹。</span><span class="sxs-lookup"><span data-stu-id="e52e0-151">Copy the downloaded files to the `public` folder in your web app project.</span></span>  
    
1.  <span data-ttu-id="e52e0-152">在 VS 代码中，打开 `/public/index.html` 并将以下代码片段添加到 `<head>` 标记中。</span><span class="sxs-lookup"><span data-stu-id="e52e0-152">In VS Code, open `/public/index.html` and add the following code snippet inside the `<head>` tag.</span></span>  
    
    ```html
    <script src="/pwabuilder-sw-register.js"></script>
    ```  
    
<span data-ttu-id="e52e0-153">你的 web 应用现在有一个服务工作人员使用缓存第一个策略，该策略首先从缓存中提取资源（如图像、JS、CSS 和 HTML），并根据需要回退到网络。</span><span class="sxs-lookup"><span data-stu-id="e52e0-153">Your web app now has a service worker that uses the cache-first strategy, which fetches resources like images, JS, CSS, and HTML from the cache first, and falls back to the network as needed.</span></span>  

<span data-ttu-id="e52e0-154">使用以下步骤确认你的服务工作人员运行。</span><span class="sxs-lookup"><span data-stu-id="e52e0-154">Use the following steps to confirm that your service worker runs.</span></span>  

1.  <span data-ttu-id="e52e0-155">使用导航到你的 web 应用 `http://localhost:3000` 。</span><span class="sxs-lookup"><span data-stu-id="e52e0-155">Navigate to your web app using `http://localhost:3000`.</span></span>  <span data-ttu-id="e52e0-156">如果你的 web 应用不可用，请运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="e52e0-156">If your web app is not available, run the following command.</span></span>   
    
    ```shell
    npm start
    ```
    
1.  <span data-ttu-id="e52e0-157">在 Microsoft Edge 中，选择 `F12` 以打开 Microsoft Edge DevTools。</span><span class="sxs-lookup"><span data-stu-id="e52e0-157">In Microsoft Edge, select `F12` to open the Microsoft Edge DevTools.</span></span>  <span data-ttu-id="e52e0-158">选择 "**应用程序**"，然后选择 "**服务工作人员**" 以查看服务工作人员。</span><span class="sxs-lookup"><span data-stu-id="e52e0-158">Select **Application**, then **Service Workers** to view the service workers.</span></span>  <span data-ttu-id="e52e0-159">如果看不到服务工作人员，可能需要刷新页面。</span><span class="sxs-lookup"><span data-stu-id="e52e0-159">If you do not see the service worker, you may need to refresh the page.</span></span>  
     
    :::image type="complex" source="./media/devtools-sw-overview.png" alt-text="Microsoft Edge DevTools 服务工作人员概述":::
       <span data-ttu-id="e52e0-161">Microsoft Edge DevTools 服务工作人员概述</span><span class="sxs-lookup"><span data-stu-id="e52e0-161">Microsoft Edge DevTools Service Worker overview</span></span>
    :::image-end:::
    
1.  <span data-ttu-id="e52e0-162">通过展开**缓存存储**来查看服务工作人员缓存并选择**pwabuilder-precache**。</span><span class="sxs-lookup"><span data-stu-id="e52e0-162">View the service worker cache by expanding **Cache Storage** and select **pwabuilder-precache**.</span></span>  <span data-ttu-id="e52e0-163">你应看到服务工作人员缓存的所有资源，例如应用图标、应用清单、CSS 和 JavaScript 文件。</span><span class="sxs-lookup"><span data-stu-id="e52e0-163">You should see all the resources cached by the service worker, such as the app icon, app manifest, CSS and JavaScript files.</span></span>  
    
    :::image type="complex" source="./media/devtools-cache.png" alt-text="Microsoft Edge DevTools 中的服务工作人员缓存":::
       <span data-ttu-id="e52e0-165">Microsoft Edge DevTools 中的服务工作人员缓存（F12）</span><span class="sxs-lookup"><span data-stu-id="e52e0-165">Service Worker cache in Microsoft Edge DevTools (F12)</span></span>
    :::image-end:::
    
1.  <span data-ttu-id="e52e0-166">以脱机应用的形式尝试 PWA。</span><span class="sxs-lookup"><span data-stu-id="e52e0-166">Try your PWA as an offline app.</span></span>  <span data-ttu-id="e52e0-167">在 Microsoft Edge DevTools \ （ `F12` \）中，选择 "**网络**"，然后将**联机**状态更改为 "**脱机**"。</span><span class="sxs-lookup"><span data-stu-id="e52e0-167">In Microsoft Edge DevTools \(`F12`\), choose **Network** then change the **Online** status to **Offline**.</span></span>  
    
    :::image type="complex" source="./media/devtools-offline.png" alt-text="在 Microsoft Edge DevTools 中将应用设置为脱机模式":::
       <span data-ttu-id="e52e0-169">在 Microsoft Edge DevTools 中将应用设置为脱机模式</span><span class="sxs-lookup"><span data-stu-id="e52e0-169">Setting app to offline mode in Microsoft Edge DevTools</span></span>
    :::image-end:::
    
1.  <span data-ttu-id="e52e0-170">刷新你的应用，你应该通过从缓存中为你的应用提供服务资源来查看它是否已脱机工作。</span><span class="sxs-lookup"><span data-stu-id="e52e0-170">Refresh your app and you should see it working offline by serving the resources of your app from the cache.</span></span>  
    
    :::image type="complex" source="./media/vs-nodejs-express-index.png" alt-text="PWA 在脱机状态下运行":::
       <span data-ttu-id="e52e0-172">PWA 在脱机状态下运行</span><span class="sxs-lookup"><span data-stu-id="e52e0-172">PWA running offline</span></span>
    :::image-end:::
    
## <span data-ttu-id="e52e0-173">向 PWA 添加推送通知</span><span class="sxs-lookup"><span data-stu-id="e52e0-173">Add push notifications to your PWA</span></span>  

<span data-ttu-id="e52e0-174">你可以通过完成以下任务来创建支持推送通知的 PWAs。</span><span class="sxs-lookup"><span data-stu-id="e52e0-174">You may create PWAs that support push notifications by completing the following tasks.</span></span>  

1.  <span data-ttu-id="e52e0-175">使用[推送 API][MDNPushApi]订阅消息服务</span><span class="sxs-lookup"><span data-stu-id="e52e0-175">Subscribe to a messaging service using the [Push API][MDNPushApi]</span></span>  
1.  <span data-ttu-id="e52e0-176">使用[通知 API][MDNNotificationsApi]从服务收到消息时显示 toast 消息</span><span class="sxs-lookup"><span data-stu-id="e52e0-176">Display a toast messages when a message is received from the service using the [Notifications API][MDNNotificationsApi]</span></span>  

<span data-ttu-id="e52e0-177">与服务工作者一样，这些是基于标准的 Api，可跨浏览器使用，因此你只需编写一次代码即可在任何支持 PWAs 的地方工作。</span><span class="sxs-lookup"><span data-stu-id="e52e0-177">As with Service Workers, these are standards-based APIs that work across browsers, so you only have to write the code once for it to work everywhere that PWAs are supported.</span></span>  <span data-ttu-id="e52e0-178">有关向服务器上的不同浏览器传递推送消息的详细信息，请使用[Web 推送][NPMWebPush]开放源代码库。</span><span class="sxs-lookup"><span data-stu-id="e52e0-178">For more information on delivering push messages to different browsers on your server, use the [Web-Push][NPMWebPush] open-source library.</span></span>  

<span data-ttu-id="e52e0-179">以下步骤适用于由 Mozilla 提供的[服务工作人员手册][ServiceWorkerCookbookPushRichDemo]中的 "推送丰富" 演示，这些演示具有许多其他有用的 Web 推送和服务工作人员食谱。</span><span class="sxs-lookup"><span data-stu-id="e52e0-179">The following steps have been adapted from the Push Rich Demo in [Service Worker Cookbook][ServiceWorkerCookbookPushRichDemo] provided by Mozilla, which has a number of other useful Web Push and service worker recipes.</span></span>  

### <span data-ttu-id="e52e0-180">步骤 1-生成 VAPID 键</span><span class="sxs-lookup"><span data-stu-id="e52e0-180">Step 1 - Generate VAPID keys</span></span>  

<span data-ttu-id="e52e0-181">推送通知需要 VAPID \ （自愿应用程序服务器标识 \）密钥才能向 PWA 客户端发送推送消息。</span><span class="sxs-lookup"><span data-stu-id="e52e0-181">Push notifications require VAPID \(Voluntary Application Server Identification\) keys in order to send push messages to the PWA client.</span></span>  <span data-ttu-id="e52e0-182">有多个 VAPID 密钥生成器可联机使用 \ （例如， [vapidkeys.com][VapidkeysMain]\）。</span><span class="sxs-lookup"><span data-stu-id="e52e0-182">There are several VAPID key generators available online \(for example, [vapidkeys.com][VapidkeysMain]\).</span></span>  <span data-ttu-id="e52e0-183">生成后，应获取包含公钥和私钥的 JSON 对象。</span><span class="sxs-lookup"><span data-stu-id="e52e0-183">After generation, you should get a JSON object containing a public and private key.</span></span>  <span data-ttu-id="e52e0-184">保存密钥以执行以下教程中的后续步骤。</span><span class="sxs-lookup"><span data-stu-id="e52e0-184">Save the keys for subsequent steps in the following tutorial.</span></span>  <span data-ttu-id="e52e0-185">有关 VAPID 和 WebPush 的工作方式的信息，请参阅[通过 Mozilla 的推送服务发送 VAPID 标识的 WebPush 通知][MozillaServicesSendingVapidWebPushNotificationsPush]。</span><span class="sxs-lookup"><span data-stu-id="e52e0-185">For information on how VAPID and WebPush works, see [Sending VAPID identified WebPush Notifications via Mozilla's Push Service][MozillaServicesSendingVapidWebPushNotificationsPush].</span></span>  

### <span data-ttu-id="e52e0-186">步骤 2-订阅推送通知</span><span class="sxs-lookup"><span data-stu-id="e52e0-186">Step 2 - Subscribe to push notifications</span></span>  

<span data-ttu-id="e52e0-187">服务工作者处理 PWA 中的推送事件和 toast 通知交互。</span><span class="sxs-lookup"><span data-stu-id="e52e0-187">Service workers handle push events and toast notification interactions in your PWA.</span></span>  <span data-ttu-id="e52e0-188">若要将 PWA 订阅到服务器推送通知，请确保满足以下条件。</span><span class="sxs-lookup"><span data-stu-id="e52e0-188">To subscribe the PWA to server push notifications, ensure the following conditions are met.</span></span>  

*   <span data-ttu-id="e52e0-189">您的 PWA 已安装、处于活动状态且已注册</span><span class="sxs-lookup"><span data-stu-id="e52e0-189">Your PWA is installed, active and registered</span></span>  
*   <span data-ttu-id="e52e0-190">执行订阅任务的代码位于 PWA 的主 UI 线程上</span><span class="sxs-lookup"><span data-stu-id="e52e0-190">Your code that performs the subscription task is on the main UI thread of the PWA</span></span>  
*   <span data-ttu-id="e52e0-191">您有网络连接</span><span class="sxs-lookup"><span data-stu-id="e52e0-191">You have network connectivity</span></span>  

<span data-ttu-id="e52e0-192">在创建新推送订阅之前，Microsoft Edge 检查用户是否授予了 PWA 接收通知的权限。</span><span class="sxs-lookup"><span data-stu-id="e52e0-192">Before a new push subscription is created, Microsoft Edge checks if the user granted the PWA permission to receive notifications.</span></span>  <span data-ttu-id="e52e0-193">如果不是，则浏览器会提示用户提供权限。</span><span class="sxs-lookup"><span data-stu-id="e52e0-193">If not, the user is prompted by the browser for permission.</span></span>  <span data-ttu-id="e52e0-194">如果权限被拒绝，则 `registration.pushManager.subscribe` 引发必须处理的请求 `DOMException` 。</span><span class="sxs-lookup"><span data-stu-id="e52e0-194">If the permission is denied, the request to `registration.pushManager.subscribe` throws a `DOMException`, which must be handled.</span></span>  <span data-ttu-id="e52e0-195">有关权限管理的详细信息，请参阅[Microsoft Edge 中的推送通知][WindowsBlogsWebNotificationsEdge]。</span><span class="sxs-lookup"><span data-stu-id="e52e0-195">For more on permission management, see [Push Notifications in Microsoft Edge][WindowsBlogsWebNotificationsEdge].</span></span>  

<span data-ttu-id="e52e0-196">在 `pwabuilder-sw-register.js` 文件中，附加以下代码片段。</span><span class="sxs-lookup"><span data-stu-id="e52e0-196">In your `pwabuilder-sw-register.js` file, append the following code snippet.</span></span>  

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

<span data-ttu-id="e52e0-197">有关详细信息，请参阅[PushManager][MDNPushManager]和[Web 推送][NPMWebPushUsage]。</span><span class="sxs-lookup"><span data-stu-id="e52e0-197">For more information, see [PushManager][MDNPushManager] and [Web-Push][NPMWebPushUsage].</span></span>  

### <span data-ttu-id="e52e0-198">步骤 3-侦听推送通知</span><span class="sxs-lookup"><span data-stu-id="e52e0-198">Step 3 - Listen for push notifications</span></span>  

<span data-ttu-id="e52e0-199">现在，在你的 PWA 中设置了订阅，向服务工作人员添加对推送事件（从服务器发送）的处理程序，以使用收到的消息的数据显示 toast 通知。</span><span class="sxs-lookup"><span data-stu-id="e52e0-199">Now that a subscription is set up in your PWA, add handlers to the service worker to respond to push events \(sent from the server\) to display toast notifications with the data of a received message.</span></span>  <span data-ttu-id="e52e0-200">必须添加一个单击处理程序来执行以下任一任务。</span><span class="sxs-lookup"><span data-stu-id="e52e0-200">You must add a click handler to perform the any of the following tasks.</span></span>  
*   <span data-ttu-id="e52e0-201">关闭 toast 通知</span><span class="sxs-lookup"><span data-stu-id="e52e0-201">dismiss the toast notification</span></span>  
*   <span data-ttu-id="e52e0-202">打开、焦点或打开所有打开的窗口并将焦点集中在该窗口</span><span class="sxs-lookup"><span data-stu-id="e52e0-202">open, focus, or open and focus any open windows</span></span>  
*   <span data-ttu-id="e52e0-203">打开并焦点一个新窗口以显示 PWA 客户端页面</span><span class="sxs-lookup"><span data-stu-id="e52e0-203">open and focus a new window to display a PWA client page</span></span>  

<span data-ttu-id="e52e0-204">在 `pwabuilder-sw.js` 文件中，添加以下处理程序。</span><span class="sxs-lookup"><span data-stu-id="e52e0-204">In your `pwabuilder-sw.js` file, add the following handlers.</span></span>  

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
    
    // This looks to see if the current notification is already open and focuses it.
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

### <span data-ttu-id="e52e0-205">步骤 4-试用</span><span class="sxs-lookup"><span data-stu-id="e52e0-205">Step 4 - Try it out</span></span>  

<span data-ttu-id="e52e0-206">执行以下步骤来测试 PWA 中的推送通知。</span><span class="sxs-lookup"><span data-stu-id="e52e0-206">Perform the following steps to test push notifications in your PWA.</span></span>  

1.  <span data-ttu-id="e52e0-207">在上导航到你的 PWA `http://localhost:3000` 。</span><span class="sxs-lookup"><span data-stu-id="e52e0-207">Navigate to your PWA at `http://localhost:3000`.</span></span>  <span data-ttu-id="e52e0-208">当你的服务工作者激活并尝试将你的 PWA 订阅到推送通知时，Microsoft Edge 会提示你允许 PWA 显示通知。</span><span class="sxs-lookup"><span data-stu-id="e52e0-208">When your service worker activates and attempts to subscribe your PWA to push notifications, Microsoft Edge prompts you to allow your PWA to show notifications.</span></span>  <span data-ttu-id="e52e0-209">选择 "**允许**"。</span><span class="sxs-lookup"><span data-stu-id="e52e0-209">Select **Allow**.</span></span>  
    
    :::image type="complex" source="./media/notification-permission.png" alt-text="用于启用通知的权限对话框":::
       <span data-ttu-id="e52e0-211">用于启用通知的权限对话框</span><span class="sxs-lookup"><span data-stu-id="e52e0-211">Permission dialog for enabling notifications</span></span>
    :::image-end:::
    
    
1.  <span data-ttu-id="e52e0-212">模拟服务器端推送通知。</span><span class="sxs-lookup"><span data-stu-id="e52e0-212">Simulate a server-side push notification.</span></span>  <span data-ttu-id="e52e0-213">`http://localhost:3000`在浏览器中打开 PWA 后，选择 `F12` 以打开 DevTools。</span><span class="sxs-lookup"><span data-stu-id="e52e0-213">With your PWA opened at `http://localhost:3000` in your browser, select `F12` to open the DevTools.</span></span>  <span data-ttu-id="e52e0-214">选择 "**应用程序**  >  **服务工作人员**  >  **推送**" 以向你的 PWA 发送测试推送通知。</span><span class="sxs-lookup"><span data-stu-id="e52e0-214">Choose **Application** > **Service Worker** > **Push** to send a test push notification to your PWA.</span></span>  <span data-ttu-id="e52e0-215">你应该会看到任务栏附近显示 "推送通知"。</span><span class="sxs-lookup"><span data-stu-id="e52e0-215">You should see a push notification appear near the taskbar.</span></span>  
    
    :::image type="complex" source="./media/devtools-push.png" alt-text="推送来自 DevTools 的通知":::
       <span data-ttu-id="e52e0-217">推送来自 DevTools 的通知</span><span class="sxs-lookup"><span data-stu-id="e52e0-217">Push a notification from DevTools</span></span>
    :::image-end:::
     
    <span data-ttu-id="e52e0-218">如果您没有选择 \ （或激活 \） toast 通知，则它将在几秒钟后关闭，并在 Windows 操作中心内排队。</span><span class="sxs-lookup"><span data-stu-id="e52e0-218">If you do not select \(or activate\) a toast notification, it is dismissed after several seconds and queues up in your Windows Action Center.</span></span>  
    
    :::image type="complex" source="./media/windows-action-center.png" alt-text="Windows 操作中心中的通知":::
       <span data-ttu-id="e52e0-220">Windows 操作中心中的通知</span><span class="sxs-lookup"><span data-stu-id="e52e0-220">Notifications in Windows Action Center</span></span>
    :::image-end:::
    
    
## <span data-ttu-id="e52e0-221">后续步骤</span><span class="sxs-lookup"><span data-stu-id="e52e0-221">Next steps</span></span>  

<span data-ttu-id="e52e0-222">以下是在构建现实世界 PWAs 时要了解的其他任务的列表：</span><span class="sxs-lookup"><span data-stu-id="e52e0-222">The following is a list of additional tasks to learn when building real-world PWAs:</span></span>  

*  <span data-ttu-id="e52e0-223">管理和存储推送订阅</span><span class="sxs-lookup"><span data-stu-id="e52e0-223">Manage and store push subscriptions</span></span>  
*  <span data-ttu-id="e52e0-224">[加密][NPMWebPushEncrypt]有效负载数据</span><span class="sxs-lookup"><span data-stu-id="e52e0-224">[Encrypt][NPMWebPushEncrypt] payload data</span></span>  
*  <span data-ttu-id="e52e0-225">响应式设计</span><span class="sxs-lookup"><span data-stu-id="e52e0-225">Responsive design</span></span>  
*  <span data-ttu-id="e52e0-226">深度链接</span><span class="sxs-lookup"><span data-stu-id="e52e0-226">Deep-linking</span></span>  
*  [<span data-ttu-id="e52e0-227">跨浏览器测试</span><span class="sxs-lookup"><span data-stu-id="e52e0-227">Cross-browser testing</span></span>][BrowserStackTestEdgeBrowser]  
*  <span data-ttu-id="e52e0-228">实现最佳做法，如[Webhint][Webhint]</span><span class="sxs-lookup"><span data-stu-id="e52e0-228">Implement best practices such as [Webhint][Webhint]</span></span>  

## <span data-ttu-id="e52e0-229">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e52e0-229">See also</span></span>  

*   <span data-ttu-id="e52e0-230">[MDN web 文档上的渐进式 Web 应用][MDNProgressiveWebApps]。</span><span class="sxs-lookup"><span data-stu-id="e52e0-230">[Progressive Web Apps on MDN web docs][MDNProgressiveWebApps].</span></span>  
*   <span data-ttu-id="e52e0-231">[Web 上的渐进式 Web 应用][WebDevProgressiveWebApps]。</span><span class="sxs-lookup"><span data-stu-id="e52e0-231">[Progressive Web Apps on web.dev][WebDevProgressiveWebApps].</span></span>  
*   <span data-ttu-id="e52e0-232">[作为渐进 Web 应用的黑客新闻阅读器][HackerNewsProgressiveWebApps]-比较不同的框架和性能模式，用于实现示例 \ （黑客新闻阅读器 \） PWA。</span><span class="sxs-lookup"><span data-stu-id="e52e0-232">[Hacker News readers as Progressive Web Apps][HackerNewsProgressiveWebApps] - Compares different frameworks and performance patterns for implementing a sample \(Hacker News reader\) PWA.</span></span>  

<!-- image links -->  

[ImagePwa]: ./media/pwa.png  

<!-- links -->  

<!--[PwaEdgehtmlIndexRequirements]: ../progressive-web-apps-edgehtml/index.md#requirements "Requirements - Progressive Web Apps \(EdgeHTML\) on Windows | Microsoft Docs"  -->  

[VisualStudioNodejsTutorialPublishAzureAppService]: /visualstudio/nodejs/tutorial-nodejs#optional-publish-to-azure-app-service "发布到 Azure 应用服务-在 Visual Studio 中创建 node.js 和 Express 应用 |Microsoft 文档"  

[AzureCreateFreeAccount]: https://azure.microsoft.com/free "创建 Azure 免费帐户 |Microsoft Azure"  
[AzureWebApps]: https://azure.microsoft.com/services/app-service/web "Web Apps |Microsoft Azure"  

[WindowsBlogsWebNotificationsEdge]: https://blogs.windows.com/msedgedev/2016/05/16/web-notifications-microsoft-edge#UAbvU2ymUlHO8EUV.97 "Microsoft Edge 中的 Web 通知 |Windows 博客"  

[VisualstudioCodeMain]: https://code.visualstudio.com "Visual Studio 代码"  

[BrowserStackTestEdgeBrowser]: https://www.browserstack.com/test-on-microsoft-edge-browser "Windows 10 上的免费 Microsoft Edge 浏览器测试 |BrowserStack"  

[ExpressjsApplicationGenerator]: https://expressjs.com/starter/generator.html "Express 应用程序生成器 |明确" 

[HackerNewsProgressiveWebApps]: https://hnpwa.com "作为渐进式 Web 应用的黑客新闻阅读器"  

[MDNDedicatedWorkerGlobalScopePostMessage]: https://developer.mozilla.org/docs/Web/API/
[MDNNotificationsApi]: https://developer.mozilla.org/docs/Web/API/Notifications_API "通知 API |MDN"  
[MDNProgressiveWebApps]: https://developer.mozilla.org/Apps/Progressive "渐进式 web 应用 \ （PWAs） |MDN"  
[MDNPushApi]: https://developer.mozilla.org/docs/Web/API/Push_API "推送 API |MDN"  
[MDNPushManager]: https://developer.mozilla.org/docs/Web/API/PushManager "PushManager |MDN"  
[MDNServiceWorkerApi]: https://developer.mozilla.org/docs/Web/API/Service_Worker_API "服务工作者 API |MDN"  
[MDNUsingServiceWorkers]: https://developer.mozilla.org/docs/Web/API/Service_Worker_API/Using_Service_Workers "使用服务工作者 |MDN"  
[MDNWebAppManifest]: https://developer.mozilla.org/docs/Web/Manifest "Web App 清单 |MDN"  

[MozillaServicesSendingVapidWebPushNotificationsPush]: https://blog.mozilla.org/services/2016/08/23/sending-vapid-identified-webpush-notifications-via-mozillas-push-service "通过 Mozilla 的推送服务发送 VAPID 标识的 WebPush 通知 |Mozilla 服务"  

[NodejsMain]: https://nodejs.org "Node.js"  

[NPMWebPush]: https://www.npmjs.com/package/web-push "web-推送 |npm"  
[NPMWebPushEncrypt]: https://www.npmjs.com/package/web-push#encryptuserpublickey-userauth-payload-contentencoding "加密（userPublicKey、userAuth、负载、contentEncoding）-web 推送 |NPM"  
[NPMWebPushUsage]: https://www.npmjs.com/package/web-push#usage "使用情况-web 推送 |NPM"  

[ProgressiveWebApps]: https://pwa.rocks "渐进式 Web 应用"  

[PwaBuilder]: https://www.pwabuilder.com "PWA 生成器"  
[PwaBuilderServiceWorker]: https://www.pwabuilder.com/serviceworker "服务工作人员 |PWA 生成器"  

[ServiceWorkerCookbookPushRichDemo]: https://serviceworke.rs/push-rich_demo.html "推送丰富的演示 |ServiceWorker 手册"  

[VapidkeysMain]: https://vapidkeys.com "安全 VAPID 密钥生成器 |VapidKeys" 

[Webhint]: https://sonarwhal.com "webhint，web 最佳做法的提示引擎"  

[WebDevProgressiveWebApps]: https://developers.google.com/web/progressive-web-apps "渐进式 Web 应用 |web 开发"  

[WikiProgressiveEnhancement]: https://en.wikipedia.org/wiki/Progressive_enhancement "渐进式增强 |科"  
