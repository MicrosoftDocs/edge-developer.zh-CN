---
description: 本指南概述了在 Windows 上生成渐进式 Web 应用 (Chromium) 的 PWA 基础知识和工具。
title: '渐进式 Web 应用和 chromium (入门) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/07/2021
ms.topic: conceptual
ms.prod: microsoft-edge
keywords: 渐进式 Web 应用， PWA， Edge， Windows， PWABuilder， Web 清单， 服务工作者， 推送
ms.openlocfilehash: 6ff24b2e9219b2f3755bb2e8f6db137dc7a721ec
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398131"
---
# <a name="get-started-with-progressive-web-apps-chromium"></a><span data-ttu-id="4b140-104">渐进式 Web 应用和 chromium (入门) </span><span class="sxs-lookup"><span data-stu-id="4b140-104">Get started with Progressive Web Apps (Chromium)</span></span>  

<span data-ttu-id="4b140-105">渐进式 Web 应用 \(PWA\) 是逐渐增强 [的 Web 应用][WikiProgressiveEnhancement]。</span><span class="sxs-lookup"><span data-stu-id="4b140-105">Progressive Web Apps \(PWAs\) are web apps that are [progressively enhanced][WikiProgressiveEnhancement].</span></span>  <span data-ttu-id="4b140-106">渐进式增强功能包括类似应用的功能，如安装、脱机支持和推送通知。</span><span class="sxs-lookup"><span data-stu-id="4b140-106">The progressive enhancements include app-like features, such as installation, offline support, and push notifications.</span></span>  <span data-ttu-id="4b140-107">还可以打包适用于应用商店的 PWA。</span><span class="sxs-lookup"><span data-stu-id="4b140-107">You may also package your PWA for app stores.</span></span>  <span data-ttu-id="4b140-108">可能的应用商店包括 Microsoft Store、Google Play、Mac 应用商店等。</span><span class="sxs-lookup"><span data-stu-id="4b140-108">Possible app stores include the Microsoft Store, Google Play, Mac App Store, and more.</span></span>  <span data-ttu-id="4b140-109">Microsoft Store 是内置于 Windows 10 的商业应用商店。</span><span class="sxs-lookup"><span data-stu-id="4b140-109">The Microsoft Store is the commercial app store built into Windows 10.</span></span>  

<span data-ttu-id="4b140-110">以下指南通过创建简单的 Web 应用并扩展为 PWA，概述了 PWA 基础知识。</span><span class="sxs-lookup"><span data-stu-id="4b140-110">The following guide gives you an overview of PWA basics by creating a simple web app and extending it as a PWA.</span></span>  <span data-ttu-id="4b140-111">已完成的项目适用于新式浏览器。</span><span class="sxs-lookup"><span data-stu-id="4b140-111">The finished project works across modern browsers.</span></span>  

> [!TIP]
> <span data-ttu-id="4b140-112">可以使用 [PWABuilder][PwaBuilder] 创建新的 PWA、增强现有 PWA 或打包 PWA 以用于应用商店。</span><span class="sxs-lookup"><span data-stu-id="4b140-112">You may use [PWABuilder][PwaBuilder] to create a new PWA, enhance your existing PWA, or package your PWA for app stores.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="4b140-113">必备条件</span><span class="sxs-lookup"><span data-stu-id="4b140-113">Prerequisites</span></span>  

*   <span data-ttu-id="4b140-114">使用 [Visual Studio代码][VisualstudioCodeMain] 编辑 PWA 源代码。</span><span class="sxs-lookup"><span data-stu-id="4b140-114">Use [Visual Studio Code][VisualstudioCodeMain] to edit your PWA source code.</span></span>  
*   <span data-ttu-id="4b140-115">将 [Node.js][NodejsMain] 用作本地 Web 服务器。</span><span class="sxs-lookup"><span data-stu-id="4b140-115">Use [Node.js][NodejsMain] as your local web server.</span></span>  
    
## <a name="create-a-basic-web-app"></a><span data-ttu-id="4b140-116">创建基本 Web 应用</span><span class="sxs-lookup"><span data-stu-id="4b140-116">Create a basic web app</span></span>  

<span data-ttu-id="4b140-117">若要创建空 Web 应用，请按照节点 [Express 应用生成器][ExpressjsApplicationGenerator]中的步骤操作，并命名你的应用 `MySamplePwa` 。</span><span class="sxs-lookup"><span data-stu-id="4b140-117">To create an empty web app, follow the steps in [Node Express App Generator][ExpressjsApplicationGenerator], and name your app `MySamplePwa`.</span></span>  

<span data-ttu-id="4b140-118">在提示符中，运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="4b140-118">In the prompt, run the following commands.</span></span>  

```shell
npx express-generator --no-view
```  

```shell
npm install
```  

<span data-ttu-id="4b140-119">这些命令将创建一个空的 Web 应用并安装任何依赖项。</span><span class="sxs-lookup"><span data-stu-id="4b140-119">The commands create an empty web app and install any dependencies.</span></span>  

<span data-ttu-id="4b140-120">现在，您具有一个简单的功能性 Web 应用。</span><span class="sxs-lookup"><span data-stu-id="4b140-120">You now have a simple, functional web app.</span></span>  <span data-ttu-id="4b140-121">若要启动 Web 应用，请运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="4b140-121">To start your web app, run the following command.</span></span>  

```shell
npm start
```  

<span data-ttu-id="4b140-122">现在浏览 `http://localhost:3000` 以查看新的 Web 应用。</span><span class="sxs-lookup"><span data-stu-id="4b140-122">Now browse to `http://localhost:3000` to view your new web app.</span></span>  

:::image type="complex" source="./media/vs-nodejs-express-index.png" alt-text="在 localhost 上运行新 PWA" lightbox="./media/vs-nodejs-express-index.png":::
   <span data-ttu-id="4b140-124">在 localhost 上运行新 PWA</span><span class="sxs-lookup"><span data-stu-id="4b140-124">Running your new PWA on localhost</span></span>
:::image-end:::

## <a name="get-started-building-a-pwa"></a><span data-ttu-id="4b140-125">开始生成 PWA</span><span class="sxs-lookup"><span data-stu-id="4b140-125">Get started building a PWA</span></span>  

<span data-ttu-id="4b140-126">现在，你已拥有一个简单的 Web 应用，通过添加 PWA 的三个要求将其扩展为 PWA</span><span class="sxs-lookup"><span data-stu-id="4b140-126">Now that you have a simple web app, extend it as a PWA by adding the three requirements for PWAs</span></span><!--[3 requirements for PWAs][PwaEdgehtmlIndexRequirements]--><span data-ttu-id="4b140-127">[：HTTPS、Web](#step-1---use-https)[应用清单](#step-2---create-a-web-app-manifest)和服务[工作线程](#step-3---add-a-service-worker)。</span><span class="sxs-lookup"><span data-stu-id="4b140-127">: [HTTPS](#step-1---use-https), a [Web App Manifest](#step-2---create-a-web-app-manifest), and a [Service Worker](#step-3---add-a-service-worker).</span></span>  

### <a name="step-1---use-https"></a><span data-ttu-id="4b140-128">步骤 1 - 使用 HTTPS</span><span class="sxs-lookup"><span data-stu-id="4b140-128">Step 1 - Use HTTPS</span></span>  

<span data-ttu-id="4b140-129">PWA 平台的关键部分（如 [服务][MDNServiceWorkerApi]工作者）需要使用 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="4b140-129">Key parts of the PWA platform, such as [Service Workers][MDNServiceWorkerApi], require the use of HTTPS.</span></span>  <span data-ttu-id="4b140-130">PWA 发布后，必须将其发布到 HTTPS URL。</span><span class="sxs-lookup"><span data-stu-id="4b140-130">When your PWA goes live, you must publish it to an HTTPS URL.</span></span>  

<span data-ttu-id="4b140-131">出于调试目的，Microsoft Edge 还 `http://localhost` 允许使用 PWA API。</span><span class="sxs-lookup"><span data-stu-id="4b140-131">For debugging purposes, Microsoft Edge also permits `http://localhost` to use the PWA APIs.</span></span>  

<span data-ttu-id="4b140-132">[将 Web 应用发布为实时网站][VisualStudioNodejsTutorialPublishAzureAppService]，但请确保服务器已针对 HTTPS 进行配置。</span><span class="sxs-lookup"><span data-stu-id="4b140-132">[Publish your web app as a live site][VisualStudioNodejsTutorialPublishAzureAppService], but ensure your server is configured for HTTPS.</span></span>  <span data-ttu-id="4b140-133">例如，你可以创建 Azure [免费帐户][AzureCreateFreeAccount]。</span><span class="sxs-lookup"><span data-stu-id="4b140-133">For example, you may create an [Azure free account][AzureCreateFreeAccount].</span></span>  <span data-ttu-id="4b140-134">在 [Microsoft Azure 应用服务上][AzureWebApps] 托管网站，默认情况下通过 HTTPS 提供服务。</span><span class="sxs-lookup"><span data-stu-id="4b140-134">Host your site on the [Microsoft Azure App Service][AzureWebApps] and it is served over HTTPS by default.</span></span>  

<span data-ttu-id="4b140-135">以下指南用于生成 `http://localhost` PWA。</span><span class="sxs-lookup"><span data-stu-id="4b140-135">The following guide, use `http://localhost` to build your PWA.</span></span>  

### <a name="step-2---create-a-web-app-manifest"></a><span data-ttu-id="4b140-136">步骤 2 - 创建 Web 应用清单</span><span class="sxs-lookup"><span data-stu-id="4b140-136">Step 2 - Create a Web App Manifest</span></span>  

<span data-ttu-id="4b140-137">[Web 应用清单][MDNWebAppManifest]是一个 JSON 文件，其中包含有关应用的元数据，如名称、说明、图标等。</span><span class="sxs-lookup"><span data-stu-id="4b140-137">A [Web App Manifest][MDNWebAppManifest] is a JSON file containing metadata about your app, such as name, description, icons, and more.</span></span>  

<span data-ttu-id="4b140-138">若要将应用程序清单添加到 Web 应用，请运行以下操作：</span><span class="sxs-lookup"><span data-stu-id="4b140-138">To add an app manifest to the web app:</span></span>  

1.  <span data-ttu-id="4b140-139">在Visual Studio中，选择 **"文件**打开  >  **文件夹**"并选择 `MySamplePwa` 之前创建的目录。</span><span class="sxs-lookup"><span data-stu-id="4b140-139">In Visual Studio Code, choose **File** > **Open Folder** and choose the `MySamplePwa` directory you created earlier.</span></span>  
1.  <span data-ttu-id="4b140-140">选择 `Ctrl` + `N` 以创建新文件，并粘贴到以下代码段中。</span><span class="sxs-lookup"><span data-stu-id="4b140-140">Select `Ctrl`+`N` to create a new file, and paste in the following code snippet.</span></span>  
    
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
    
1.  <span data-ttu-id="4b140-141">将文件另存为 `/MySamplePwa/public/manifest.json` 。</span><span class="sxs-lookup"><span data-stu-id="4b140-141">Save the file as `/MySamplePwa/public/manifest.json`.</span></span>  
1.  <span data-ttu-id="4b140-142">添加名为 .的 512x512 应用图标 `icon512.png` 图像 `/MySamplePwa/public/images` 。</span><span class="sxs-lookup"><span data-stu-id="4b140-142">Add a 512x512 app icon image named `icon512.png` to `/MySamplePwa/public/images`.</span></span>  <span data-ttu-id="4b140-143">您可以使用示例 [图像][ImagePwa] 进行测试。</span><span class="sxs-lookup"><span data-stu-id="4b140-143">You may use the [sample image][ImagePwa] for testing purposes.</span></span>  
1.  <span data-ttu-id="4b140-144">在Visual Studio中 `/public/index.html` ，打开并添加标记内的以下 `<head>` 代码段。</span><span class="sxs-lookup"><span data-stu-id="4b140-144">In Visual Studio Code, open `/public/index.html`, and add the following code snippet inside the `<head>` tag.</span></span>  
    
    ```html
    <link rel="manifest" href="/manifest.json">
    ```   
    
### <a name="step-3---add-a-service-worker"></a><span data-ttu-id="4b140-145">步骤 3 - 添加服务工作线程</span><span class="sxs-lookup"><span data-stu-id="4b140-145">Step 3 - Add a Service Worker</span></span>  

<span data-ttu-id="4b140-146">服务工作者是 PWA 背后的关键技术，支持脱机支持、高级缓存和运行之前仅限于本机应用的后台任务等方案。</span><span class="sxs-lookup"><span data-stu-id="4b140-146">Service workers are the key technology behind PWAs, enabling scenarios like offline support, advanced caching, and running background tasks previously limited to native apps.</span></span>  

<span data-ttu-id="4b140-147">服务工作者是截获来自 Web 应用的网络请求的后台任务。</span><span class="sxs-lookup"><span data-stu-id="4b140-147">Service workers are background tasks that intercept network requests from your web app.</span></span>  <span data-ttu-id="4b140-148">即使 PWA 未运行，服务工作人员也尝试完成任务。</span><span class="sxs-lookup"><span data-stu-id="4b140-148">Service workers attempt to complete tasks, even when your PWA is not running.</span></span>  <span data-ttu-id="4b140-149">任务包括以下操作。</span><span class="sxs-lookup"><span data-stu-id="4b140-149">Tasks include the following actions.</span></span>  

*   <span data-ttu-id="4b140-150">从缓存中提供请求的资源</span><span class="sxs-lookup"><span data-stu-id="4b140-150">Serving requested resources from a cache</span></span>  
*   <span data-ttu-id="4b140-151">发送推送通知</span><span class="sxs-lookup"><span data-stu-id="4b140-151">Sending push notifications</span></span>  
*   <span data-ttu-id="4b140-152">运行后台提取任务</span><span class="sxs-lookup"><span data-stu-id="4b140-152">Running background fetch tasks</span></span>  
*   <span data-ttu-id="4b140-153">标记图标</span><span class="sxs-lookup"><span data-stu-id="4b140-153">Badging icons</span></span>  
*   <span data-ttu-id="4b140-154">和更多信息</span><span class="sxs-lookup"><span data-stu-id="4b140-154">and more</span></span>  
    
<span data-ttu-id="4b140-155">服务工作者在特殊的 JavaScript 文件中定义。</span><span class="sxs-lookup"><span data-stu-id="4b140-155">Service workers are defined in a special JavaScript file.</span></span>  <span data-ttu-id="4b140-156">有关详细信息，请导航到["使用服务工作者和服务][MDNUsingServiceWorkers][工作者 API"。][MDNServiceWorkerApi]</span><span class="sxs-lookup"><span data-stu-id="4b140-156">For more information, navigate to [Using Service Workers][MDNUsingServiceWorkers] and [Service Worker API][MDNServiceWorkerApi].</span></span>  

<span data-ttu-id="4b140-157">若要在项目中生成服务工作者，请使用[PWA Builder][PwaBuilderServiceWorker]中的**缓存第一个**网络服务工作者方法。</span><span class="sxs-lookup"><span data-stu-id="4b140-157">To build a service worker in your project, use the **Cache-first network** service worker recipe from [PWA Builder][PwaBuilderServiceWorker].</span></span>  

1.  <span data-ttu-id="4b140-158">导航到 [pwabuilder.com/serviceworker，][PwaBuilderServiceWorker]选择 **缓存第一个网络** 服务工作线程，然后选择" **下载"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="4b140-158">Navigate to [pwabuilder.com/serviceworker][PwaBuilderServiceWorker], select the **Cache-first network** service worker, and select the **Download** button.</span></span>  <span data-ttu-id="4b140-159">下载的文件包含以下文件：</span><span class="sxs-lookup"><span data-stu-id="4b140-159">The downloaded file contains the following files:</span></span>
    
    *   `pwabuilder-sw-register.js`  
    *   `pwabuilder-sw.js`  
        
1.  <span data-ttu-id="4b140-160">将下载的文件复制到 Web `public` 应用项目中的文件夹。</span><span class="sxs-lookup"><span data-stu-id="4b140-160">Copy the downloaded files to the `public` folder in your web app project.</span></span>  
1.  <span data-ttu-id="4b140-161">在Visual Studio中， `/public/index.html` 打开并添加标记内的以下 `<head>` 代码段。</span><span class="sxs-lookup"><span data-stu-id="4b140-161">In Visual Studio Code, open `/public/index.html` and add the following code snippet inside the `<head>` tag.</span></span>  
    
    ```html
    <script type="module" src="/pwabuilder-sw-register.js"></script>
    ```  
    
<span data-ttu-id="4b140-162">Web 应用现在具有使用缓存第一策略的服务工作者。</span><span class="sxs-lookup"><span data-stu-id="4b140-162">Your web app now has a service worker that uses the cache-first strategy.</span></span>  <span data-ttu-id="4b140-163">新服务工作者首先从缓存提取资源，然后仅根据需要从网络获取资源。</span><span class="sxs-lookup"><span data-stu-id="4b140-163">You new service worker fetches resources from the cache first, and from the network only as needed.</span></span>  <span data-ttu-id="4b140-164">缓存的资源包括图像、JavaScript、CSS 和 HTML。</span><span class="sxs-lookup"><span data-stu-id="4b140-164">Cached resources include images, JavaScript, CSS, and HTML.</span></span>

<span data-ttu-id="4b140-165">使用以下步骤确认服务工作线程是否运行。</span><span class="sxs-lookup"><span data-stu-id="4b140-165">Use the following steps to confirm that your service worker runs.</span></span>  

1.  <span data-ttu-id="4b140-166">使用 导航到 Web 应用 `http://localhost:3000` 。</span><span class="sxs-lookup"><span data-stu-id="4b140-166">Navigate to your web app using `http://localhost:3000`.</span></span>  <span data-ttu-id="4b140-167">如果 Web 应用不可用，请运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="4b140-167">If your web app is not available, run the following command.</span></span>   
    
    ```shell
    npm start
    ```
    
1.  <span data-ttu-id="4b140-168">在 Microsoft Edge 中， `F12` 选择打开 Microsoft Edge DevTools。</span><span class="sxs-lookup"><span data-stu-id="4b140-168">In Microsoft Edge, select `F12` to open the Microsoft Edge DevTools.</span></span>  <span data-ttu-id="4b140-169">选择 **"应用程序**"， **然后选择"服务** 工作人员"以查看服务工作者。</span><span class="sxs-lookup"><span data-stu-id="4b140-169">Select **Application**, then **Service Workers** to view the service workers.</span></span>  <span data-ttu-id="4b140-170">如果未显示服务工作线程，则刷新页面。</span><span class="sxs-lookup"><span data-stu-id="4b140-170">If the service worker is not displayed, refresh the page.</span></span>  
    
    :::image type="complex" source="./media/devtools-sw-overview.png" alt-text="Microsoft Edge DevTools Service Worker 概述" lightbox="./media/devtools-sw-overview.png":::
       <span data-ttu-id="4b140-172">Microsoft Edge DevTools Service Worker 概述</span><span class="sxs-lookup"><span data-stu-id="4b140-172">Microsoft Edge DevTools Service Worker overview</span></span>
    :::image-end:::
    
1.  <span data-ttu-id="4b140-173">通过展开缓存存储并选择**pwabuilder-precache 查看服务工作器缓存**。 </span><span class="sxs-lookup"><span data-stu-id="4b140-173">View the service worker cache by expanding **Cache Storage** and select **pwabuilder-precache**.</span></span>  <span data-ttu-id="4b140-174">应显示服务工作者缓存的所有资源。</span><span class="sxs-lookup"><span data-stu-id="4b140-174">All of the resources cached by the service worker should be displayed.</span></span>  <span data-ttu-id="4b140-175">服务工作者缓存的资源包括应用图标、应用程序清单、CSS 和 JavaScript 文件。</span><span class="sxs-lookup"><span data-stu-id="4b140-175">The resources cached by the service worker include the app icon, app manifest, CSS, and JavaScript files.</span></span>  
    
    :::image type="complex" source="./media/devtools-cache.png" alt-text="Microsoft Edge DevTools 中的服务工作器缓存" lightbox="./media/devtools-cache.png":::
       <span data-ttu-id="4b140-177">Microsoft Edge DevTools (F12) </span><span class="sxs-lookup"><span data-stu-id="4b140-177">Service Worker cache in Microsoft Edge DevTools (F12)</span></span>
    :::image-end:::
    
1.  <span data-ttu-id="4b140-178">尝试将 PWA 作为脱机应用。</span><span class="sxs-lookup"><span data-stu-id="4b140-178">Try your PWA as an offline app.</span></span>  <span data-ttu-id="4b140-179">在 Microsoft Edge DevTools \(`F12` \) 中，选择 **"** 网络"，然后将**联机**状态更改为 **"脱机"。**</span><span class="sxs-lookup"><span data-stu-id="4b140-179">In Microsoft Edge DevTools \(`F12`\), choose **Network** then change the **Online** status to **Offline**.</span></span>  
    
    :::image type="complex" source="./media/devtools-offline.png" alt-text="在 Microsoft Edge DevTools 中将应用设置为脱机模式" lightbox="./media/devtools-offline.png":::
       <span data-ttu-id="4b140-181">在 Microsoft Edge DevTools 中将应用设置为脱机模式</span><span class="sxs-lookup"><span data-stu-id="4b140-181">Setting app to offline mode in Microsoft Edge DevTools</span></span>
    :::image-end:::
    
1.  <span data-ttu-id="4b140-182">刷新应用，它应显示用于从缓存中提供应用资源的脱机机制。</span><span class="sxs-lookup"><span data-stu-id="4b140-182">Refresh your app and it should display the offline mechanism for serving the resources of your app from the cache.</span></span>  
    
    :::image type="complex" source="./media/vs-nodejs-express-index.png" alt-text="脱机运行的 PWA" lightbox="./media/vs-nodejs-express-index.png":::
       <span data-ttu-id="4b140-184">脱机运行的 PWA</span><span class="sxs-lookup"><span data-stu-id="4b140-184">PWA running offline</span></span>
    :::image-end:::
    
## <a name="add-push-notifications-to-your-pwa"></a><span data-ttu-id="4b140-185">将推送通知添加到 PWA</span><span class="sxs-lookup"><span data-stu-id="4b140-185">Add push notifications to your PWA</span></span>  

<span data-ttu-id="4b140-186">通过完成以下任务，可以创建支持推送通知的 PWA。</span><span class="sxs-lookup"><span data-stu-id="4b140-186">You may create PWAs that support push notifications by completing the following tasks.</span></span>  

1.  <span data-ttu-id="4b140-187">使用推送 API 订阅 [邮件服务][MDNPushApi]</span><span class="sxs-lookup"><span data-stu-id="4b140-187">Subscribe to a messaging service using the [Push API][MDNPushApi]</span></span>  
1.  <span data-ttu-id="4b140-188">使用通知 API 从服务接收消息时显示 [Toast 消息][MDNNotificationsApi]</span><span class="sxs-lookup"><span data-stu-id="4b140-188">Display a toast message when a message is received from the service using the [Notifications API][MDNNotificationsApi]</span></span>  
    
<span data-ttu-id="4b140-189">与服务工作人员一样，推送通知 API 也是基于标准的 API。</span><span class="sxs-lookup"><span data-stu-id="4b140-189">Just like with Service Workers, the push notification APIs are standards-based APIs.</span></span>  <span data-ttu-id="4b140-190">推送通知 API 跨浏览器工作，因此代码应在支持 PWA 的任何地方运行。</span><span class="sxs-lookup"><span data-stu-id="4b140-190">The push notification APIs work across browsers, so your code should work everywhere that PWAs are supported.</span></span>  <span data-ttu-id="4b140-191">有关将推送消息发送到服务器上不同浏览器的信息，请导航到["Web 推送"。][NPMWebPush]</span><span class="sxs-lookup"><span data-stu-id="4b140-191">For more information about delivering push messages to different browsers on your server, navigate to [Web-Push][NPMWebPush].</span></span>  

<span data-ttu-id="4b140-192">以下步骤改编自 Mozilla 提供的"服务工作者指南[][ServiceWorkerCookbookPushRichDemo]中的推送丰富演示"，该演示具有大量其他有用的 Web 推送和服务工作者方法。</span><span class="sxs-lookup"><span data-stu-id="4b140-192">The following steps have been adapted from the Push Rich Demo in [Service Worker Cookbook][ServiceWorkerCookbookPushRichDemo] provided by Mozilla, which has a number of other useful Web Push and service worker recipes.</span></span>  

### <a name="step-1---generate-vapid-keys"></a><span data-ttu-id="4b140-193">步骤 1 - 生成 VAPID 密钥</span><span class="sxs-lookup"><span data-stu-id="4b140-193">Step 1 - Generate VAPID keys</span></span>  

<span data-ttu-id="4b140-194">推送通知需要 VAPID \(自愿应用程序服务器标识\) 密钥才能向 PWA 客户端发送推送消息。</span><span class="sxs-lookup"><span data-stu-id="4b140-194">Push notifications require VAPID \(Voluntary Application Server Identification\) keys in order to send push messages to the PWA client.</span></span>  <span data-ttu-id="4b140-195">联机 \(提供了多个 VAPID 密钥生成器，例如 [，vapidkeys.com][VapidkeysMain]\) 。</span><span class="sxs-lookup"><span data-stu-id="4b140-195">There are several VAPID key generators available online \(for example, [vapidkeys.com][VapidkeysMain]\).</span></span>  <span data-ttu-id="4b140-196">生成后，应获取包含公钥和私钥的 JSON 对象。</span><span class="sxs-lookup"><span data-stu-id="4b140-196">After generation, you should get a JSON object containing a public and private key.</span></span>  <span data-ttu-id="4b140-197">保存密钥，以执行以下教程中的稍后步骤。</span><span class="sxs-lookup"><span data-stu-id="4b140-197">Save the keys for later steps in the following tutorial.</span></span>  <span data-ttu-id="4b140-198">有关 VAPID 和 WebPush 的信息，请导航到使用 Mozilla 推送服务发送 VAPID 标识的 [WebPush 通知][MozillaServicesSendingVapidWebPushNotificationsPush]。</span><span class="sxs-lookup"><span data-stu-id="4b140-198">For information about VAPID and WebPush, navigate to [Sending VAPID identified WebPush Notifications using the Mozilla Push Service][MozillaServicesSendingVapidWebPushNotificationsPush].</span></span>  

### <a name="step-2---subscribe-to-push-notifications"></a><span data-ttu-id="4b140-199">步骤 2 - 订阅推送通知</span><span class="sxs-lookup"><span data-stu-id="4b140-199">Step 2 - Subscribe to push notifications</span></span>  

<span data-ttu-id="4b140-200">服务工作人员在 PWA 中处理推送事件和 Toast 通知交互。</span><span class="sxs-lookup"><span data-stu-id="4b140-200">Service workers handle push events and toast notification interactions in your PWA.</span></span>  <span data-ttu-id="4b140-201">若要将 PWA 订阅到服务器推送通知，请确保满足以下条件。</span><span class="sxs-lookup"><span data-stu-id="4b140-201">To subscribe the PWA to server push notifications, ensure the following conditions are met.</span></span>  

*   <span data-ttu-id="4b140-202">PWA 已安装、处于活动状态和已注册</span><span class="sxs-lookup"><span data-stu-id="4b140-202">Your PWA is installed, active, and registered</span></span>  
*   <span data-ttu-id="4b140-203">完成订阅任务的代码位于 PWA 的主 UI 线程上</span><span class="sxs-lookup"><span data-stu-id="4b140-203">Your code to complete the subscription task is on the main UI thread of the PWA</span></span>  
*   <span data-ttu-id="4b140-204">您具有网络连接</span><span class="sxs-lookup"><span data-stu-id="4b140-204">You have network connectivity</span></span>  
    
<span data-ttu-id="4b140-205">在新建推送订阅之前，Microsoft Edge 会验证用户是否授予了 PWA 接收通知的权限。</span><span class="sxs-lookup"><span data-stu-id="4b140-205">Before a new push subscription is created, Microsoft Edge verifies if the user granted the PWA permission to receive notifications.</span></span>  <span data-ttu-id="4b140-206">如果没有，浏览器会提示用户授予权限。</span><span class="sxs-lookup"><span data-stu-id="4b140-206">If not, the user is prompted by the browser for permission.</span></span>  <span data-ttu-id="4b140-207">如果权限被拒绝，则会引发 `registration.pushManager.subscribe` `DOMException` 一个必须处理的请求。</span><span class="sxs-lookup"><span data-stu-id="4b140-207">If the permission is denied, the request to `registration.pushManager.subscribe` throws a `DOMException`, which must be handled.</span></span>  <span data-ttu-id="4b140-208">有关权限管理更多信息，请导航到 [Microsoft Edge 中的推送通知][WindowsBlogsWebNotificationsEdge]。</span><span class="sxs-lookup"><span data-stu-id="4b140-208">For more on permission management, navigate to [Push Notifications in Microsoft Edge][WindowsBlogsWebNotificationsEdge].</span></span>  

<span data-ttu-id="4b140-209">在文件中 `pwabuilder-sw-register.js` ，附加以下代码段。</span><span class="sxs-lookup"><span data-stu-id="4b140-209">In your `pwabuilder-sw-register.js` file, append the following code snippet.</span></span>  

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

<span data-ttu-id="4b140-210">有关详细信息，请导航到 [PushManager 和][MDNPushManager] [Web 推送][NPMWebPushUsage]。</span><span class="sxs-lookup"><span data-stu-id="4b140-210">For more information, navigate to [PushManager][MDNPushManager] and [Web-Push][NPMWebPushUsage].</span></span>  

### <a name="step-3---listen-for-push-notifications"></a><span data-ttu-id="4b140-211">步骤 3 - 侦听推送通知</span><span class="sxs-lookup"><span data-stu-id="4b140-211">Step 3 - Listen for push notifications</span></span>  

<span data-ttu-id="4b140-212">在 PWA 中创建订阅后，向服务工作者添加处理程序以响应推送事件。</span><span class="sxs-lookup"><span data-stu-id="4b140-212">After a subscription is created in your PWA, add handlers to the service worker to respond to push events.</span></span>  <span data-ttu-id="4b140-213">推送事件从服务器发送以显示 Toast 通知。</span><span class="sxs-lookup"><span data-stu-id="4b140-213">Push event are sent from the server to display toast notifications.</span></span>  <span data-ttu-id="4b140-214">Toast 通知显示已接收邮件的数据。</span><span class="sxs-lookup"><span data-stu-id="4b140-214">Toast notifications display data for a received message.</span></span>  <span data-ttu-id="4b140-215">若要完成以下任务，必须添加 `click` 处理程序。</span><span class="sxs-lookup"><span data-stu-id="4b140-215">To complete the following tasks, you must add a `click` handler.</span></span>  

*   <span data-ttu-id="4b140-216">消除 Toast 通知</span><span class="sxs-lookup"><span data-stu-id="4b140-216">Dismiss the toast notification</span></span>  
*   <span data-ttu-id="4b140-217">打开、聚焦或打开并聚焦任何打开的窗口</span><span class="sxs-lookup"><span data-stu-id="4b140-217">Open, focus, or open and focus any open windows</span></span>  
*   <span data-ttu-id="4b140-218">打开并聚焦新窗口以显示 PWA 客户端页面</span><span class="sxs-lookup"><span data-stu-id="4b140-218">Open and focus a new window to display a PWA client page</span></span>  
    
<span data-ttu-id="4b140-219">在 `pwabuilder-sw.js` 文件中，添加以下处理程序。</span><span class="sxs-lookup"><span data-stu-id="4b140-219">In your `pwabuilder-sw.js` file, add the following handlers.</span></span>  

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

### <a name="step-4---try-it-out"></a><span data-ttu-id="4b140-220">步骤 4 - 试用</span><span class="sxs-lookup"><span data-stu-id="4b140-220">Step 4 - Try it out</span></span>  

<span data-ttu-id="4b140-221">若要测试 PWA 的推送通知，请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="4b140-221">To test push notifications for your PWA, complete the following steps.</span></span>  

1.  <span data-ttu-id="4b140-222">导航到 `http://localhost:3000` PWA。</span><span class="sxs-lookup"><span data-stu-id="4b140-222">Navigate to your PWA at `http://localhost:3000`.</span></span>  <span data-ttu-id="4b140-223">当服务工作者激活并尝试订阅 PWA 推送通知时，Microsoft Edge 会提示你允许 PWA 显示通知。</span><span class="sxs-lookup"><span data-stu-id="4b140-223">When your service worker activates and attempts to subscribe your PWA to push notifications, Microsoft Edge prompts you to allow your PWA to show notifications.</span></span>  <span data-ttu-id="4b140-224">选择 **"允许"。**</span><span class="sxs-lookup"><span data-stu-id="4b140-224">Select **Allow**.</span></span>  
    
    :::image type="complex" source="./media/notification-permission.png" alt-text="用于启用通知的权限对话框" lightbox="./media/notification-permission.png":::
       <span data-ttu-id="4b140-226">用于启用通知的权限对话框</span><span class="sxs-lookup"><span data-stu-id="4b140-226">Permission dialog for enabling notifications</span></span>
    :::image-end:::
    
1.  <span data-ttu-id="4b140-227">模拟服务器端推送通知。</span><span class="sxs-lookup"><span data-stu-id="4b140-227">Simulate a server-side push notification.</span></span>  <span data-ttu-id="4b140-228">在浏览器中打开 PWA 后，选择 `http://localhost:3000` `F12` 打开 DevTools。</span><span class="sxs-lookup"><span data-stu-id="4b140-228">With your PWA opened at `http://localhost:3000` in your browser, select `F12` to open the DevTools.</span></span>  <span data-ttu-id="4b140-229">选择 **"**  >  **应用程序服务工作**  >  **线程推送**"将测试推送通知发送到 PWA。</span><span class="sxs-lookup"><span data-stu-id="4b140-229">Choose **Application** > **Service Worker** > **Push** to send a test push notification to your PWA.</span></span>  
    
    :::row:::
       :::column span="":::
          <span data-ttu-id="4b140-230">推送通知应在任务栏附近显示。</span><span class="sxs-lookup"><span data-stu-id="4b140-230">A push notification should display near the taskbar.</span></span>  
          
          :::image type="complex" source="./media/devtools-push.png" alt-text="从 DevTools 推送通知" lightbox="./media/devtools-push.png":::
             <span data-ttu-id="4b140-232">从 DevTools 推送通知</span><span class="sxs-lookup"><span data-stu-id="4b140-232">Push a notification from DevTools</span></span>  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          <span data-ttu-id="4b140-233">如果未选择 \(或激活\) toast 通知，系统会在几秒钟后自动将其关闭，并排队到 Windows 操作中心。</span><span class="sxs-lookup"><span data-stu-id="4b140-233">If you do not select \(or activate\) a toast notification, the system automatically dismisses it after several seconds and queues it in your Windows Action Center.</span></span>  
          
          :::image type="complex" source="./media/windows-action-center.png" alt-text="Windows 操作中心中的通知" lightbox="./media/windows-action-center.png":::
             <span data-ttu-id="4b140-235">Windows 操作中心中的通知</span><span class="sxs-lookup"><span data-stu-id="4b140-235">Notifications in Windows Action Center</span></span> :::image-end:::
       :::column-end:::
    :::row-end:::  
    
## <a name="next-steps"></a><span data-ttu-id="4b140-236">后续步骤</span><span class="sxs-lookup"><span data-stu-id="4b140-236">Next steps</span></span>  

<span data-ttu-id="4b140-237">以下步骤包括帮助您了解构建实际 PWA 的其他任务。</span><span class="sxs-lookup"><span data-stu-id="4b140-237">The following steps include additional tasks to help you understand building real-world PWAs.</span></span>  

*   <span data-ttu-id="4b140-238">管理和存储推送订阅</span><span class="sxs-lookup"><span data-stu-id="4b140-238">Manage and store push subscriptions</span></span>  
*   <span data-ttu-id="4b140-239">[加密][NPMWebPushEncrypt] 有效负载数据</span><span class="sxs-lookup"><span data-stu-id="4b140-239">[Encrypt][NPMWebPushEncrypt] payload data</span></span>  
*   <span data-ttu-id="4b140-240">响应式设计</span><span class="sxs-lookup"><span data-stu-id="4b140-240">Responsive design</span></span>  
*   <span data-ttu-id="4b140-241">深层链接</span><span class="sxs-lookup"><span data-stu-id="4b140-241">Deep-linking</span></span>  
*   [<span data-ttu-id="4b140-242">跨浏览器测试</span><span class="sxs-lookup"><span data-stu-id="4b140-242">Cross-browser testing</span></span>][BrowserStackTestEdgeBrowser]  
*   <span data-ttu-id="4b140-243">实现验证和测试做法，如 [Webhint][Webhint]</span><span class="sxs-lookup"><span data-stu-id="4b140-243">Implement validation and testing practices such as [Webhint][Webhint]</span></span>  
    
## <a name="see-also"></a><span data-ttu-id="4b140-244">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4b140-244">See also</span></span>  

*   [<span data-ttu-id="4b140-245">MDN Web 文档上的渐进式 Web 应用</span><span class="sxs-lookup"><span data-stu-id="4b140-245">Progressive Web Apps on MDN web docs</span></span>][MDNProgressiveWebApps]  
*   [<span data-ttu-id="4b140-246">Web.dev 上的渐进式 Web 应用</span><span class="sxs-lookup"><span data-stu-id="4b140-246">Progressive Web Apps on web.dev</span></span>][WebDevProgressiveWebApps]  
*   <span data-ttu-id="4b140-247">[作为渐进式 Web][HackerNewsProgressiveWebApps] 应用的黑客新闻阅读器 - 比较实现示例 \(黑客新闻阅读器\) PWA 的不同框架和性能模式。</span><span class="sxs-lookup"><span data-stu-id="4b140-247">[Hacker News readers as Progressive Web Apps][HackerNewsProgressiveWebApps] - Compares different frameworks and performance patterns for implementing a sample \(Hacker News reader\) PWA.</span></span>  
*   [<span data-ttu-id="4b140-248">破坏 PBA</span><span class="sxs-lookup"><span data-stu-id="4b140-248">Myth Busting PWAs</span></span>][Davrous20191018MythBustingPwasNewEdgeEdition]  
*   [<span data-ttu-id="4b140-249">渐进式 Web 应用的渐进路线图</span><span class="sxs-lookup"><span data-stu-id="4b140-249">A Progressive Roadmap for your Progressive Web App</span></span>][CloudfourThinksProgressiveRoadmapYourWebApp]  
*   [<span data-ttu-id="4b140-250">使用渐进式 Web 应用的脱机 POST</span><span class="sxs-lookup"><span data-stu-id="4b140-250">Offline POSTs with Progressive Web Apps</span></span>][MediumWebEdgeOfflinePostsProgressiveWebApps]  
*   [<span data-ttu-id="4b140-251">PWA 问答&A</span><span class="sxs-lookup"><span data-stu-id="4b140-251">PWA Q&A</span></span>][AaronGustafsonNotebookPwaQa]  
*   [<span data-ttu-id="4b140-252">Web 上的支持</span><span class="sxs-lookup"><span data-stu-id="4b140-252">Betting on the Web</span></span>][JoretegBlogBettingWeb]  
*   [<span data-ttu-id="4b140-253">命名渐进式 Web 应用</span><span class="sxs-lookup"><span data-stu-id="4b140-253">Naming Progressive Web Apps</span></span>][Fberriman20170626NamingProgressiveWebApps]  
*   [<span data-ttu-id="4b140-254">设计和生成不带框架的渐进式 Web (第 1 部分) </span><span class="sxs-lookup"><span data-stu-id="4b140-254">Designing And Building A Progressive Web Application Without A Framework (Part 1)</span></span>][Smashingmagazine201907ProgressiveWebApplicationFrameworkPart1]  
*   [<span data-ttu-id="4b140-255">设计和构建不带框架的渐进式 Web (第 2 部分) </span><span class="sxs-lookup"><span data-stu-id="4b140-255">Designing And Building A Progressive Web Application Without A Framework (Part 2)</span></span>][Smashingmagazine201907ProgressiveWebApplicationFrameworkPart2]  
*   [<span data-ttu-id="4b140-256">设计和构建不带框架的渐进式 Web 应用程序 (第 3 部分) </span><span class="sxs-lookup"><span data-stu-id="4b140-256">Designing And Building A Progressive Web Application Without A Framework (Part 3)</span></span>][Smashingmagazine201907ProgressiveWebApplicationFrameworkPart3]  
    
<!-- image links -->  

[ImagePwa]: ./media/pwa.png  

<!-- links -->  

<!--[PwaEdgehtmlIndexRequirements]: ../progressive-web-apps/index.md#requirements "Requirements - Progressive Web Apps \(EdgeHTML\) on Windows | Microsoft Docs"  -->  

[VisualStudioNodejsTutorialPublishAzureAppService]: /azure/javascript/tutorial-vscode-azure-app-service-node-03 "使用Node.js代码将应用部署到 Azure Visual Studio Azure |Microsoft Docs"  

[AzureCreateFreeAccount]: https://azure.microsoft.com/free "创建 Azure 免费帐户|Microsoft Azure"  
[AzureWebApps]: https://azure.microsoft.com/services/app-service/web "Web 应用|Microsoft Azure"  

[WindowsBlogsWebNotificationsEdge]: https://blogs.windows.com/msedgedev/2016/05/16/web-notifications-microsoft-edge#UAbvU2ymUlHO8EUV.97 "Microsoft Edge |Windows 博客"  

[VisualstudioCodeMain]: https://code.visualstudio.com "Visual Studio 代码"  

[AaronGustafsonNotebookPwaQa]: https://www.aaron-gustafson.com/notebook/pwa-qa "PWA 问答&A"  

[BrowserStackTestEdgeBrowser]: https://www.browserstack.com/test-on-microsoft-edge-browser "在 Windows 10 | 上免费 Microsoft Edge 浏览器|BrowserStack"  

[CloudfourThinksProgressiveRoadmapYourWebApp]: https://cloudfour.com/thinks/a-progressive-roadmap-for-your-progressive-web-app "渐进式 Web 应用的渐进路线图"  

[Davrous20191018MythBustingPwasNewEdgeEdition]: https://www.davrous.com/2019/10/18/myth-busting-pwas-the-new-edge-edition "破坏 PBA – 新边缘版本"  

[ExpressjsApplicationGenerator]: https://expressjs.com/starter/generator.html "Express 应用程序生成器|Express" 

[Fberriman20170626NamingProgressiveWebApps]: https://fberriman.com/2017/06/26/naming-progressive-web-apps "命名渐进式 Web 应用"  

[HackerNewsProgressiveWebApps]: https://hnpwa.com "作为渐进式 Web 应用的黑客新闻阅读器"  

[JoretegBlogBettingWeb]: https://joreteg.com/blog/betting-on-the-web "Web 上的支持"  

[MDNDedicatedWorkerGlobalScopePostMessage]: https://developer.mozilla.org/docs/Web/API/
[MDNNotificationsApi]: https://developer.mozilla.org/docs/Web/API/Notifications_API "通知 API |MDN"  
[MDNProgressiveWebApps]: https://developer.mozilla.org/Apps/Progressive "渐进式 Web 应用 \(PWA) |MDN"  
[MDNPushApi]: https://developer.mozilla.org/docs/Web/API/Push_API "推送 API |MDN"  
[MDNPushManager]: https://developer.mozilla.org/docs/Web/API/PushManager "PushManager |MDN"  
[MDNServiceWorkerApi]: https://developer.mozilla.org/docs/Web/API/Service_Worker_API "服务工作 API |MDN"  
[MDNUsingServiceWorkers]: https://developer.mozilla.org/docs/Web/API/Service_Worker_API/Using_Service_Workers "使用服务工作者|MDN"  
[MDNWebAppManifest]: https://developer.mozilla.org/docs/Web/Manifest "Web 应用清单|MDN"  

[MediumWebEdgeOfflinePostsProgressiveWebApps]: https://medium.com/web-on-the-edge/offline-posts-with-progressive-web-apps-fc2dc4ad895 "使用渐进式 Web 应用的脱机 POST"  

[MozillaServicesSendingVapidWebPushNotificationsPush]: https://blog.mozilla.org/services/2016/08/23/sending-vapid-identified-webpush-notifications-via-mozillas-push-service "通过 Mozilla 推送服务中心发送 VAPID 标识的 WebPush |Mozilla Services"  

[NodejsMain]: https://nodejs.org "Node.js"  

[NPMWebPush]: https://www.npmjs.com/package/web-push "Web 推送|npm"  
[NPMWebPushEncrypt]: https://www.npmjs.com/package/web-push#encryptuserpublickey-userauth-payload-contentencoding "encrypt (userPublicKey， userAuth， payload， contentEncoding) - web-push |NPM"  
[NPMWebPushUsage]: https://www.npmjs.com/package/web-push#usage "用法 - Web 推送|NPM"  

[ProgressiveWebApps]: https://pwa.rocks "渐进式 Web 应用"  

[PwaBuilder]: https://www.pwabuilder.com "PWA 生成器"  
[PwaBuilderServiceWorker]: https://www.pwabuilder.com/serviceworker "服务工作|PWA 生成器"  

[ServiceWorkerCookbookPushRichDemo]: https://serviceworke.rs/push-rich_demo.html "推送丰富演示|ServiceWorker 手册"  

[Smashingmagazine201907ProgressiveWebApplicationFrameworkPart1]: https://www.smashingmagazine.com/2019/07/progressive-web-application-pwa-framework-part-1 "设计和构建不带框架的渐进式 Web (第 1 部分) "  

[Smashingmagazine201907ProgressiveWebApplicationFrameworkPart2]: https://www.smashingmagazine.com/2019/07/progressive-web-application-pwa-framework-part-2 "设计和构建不带框架的渐进式 Web (第 2 部分) "  

[Smashingmagazine201907ProgressiveWebApplicationFrameworkPart3]: https://www.smashingmagazine.com/2019/07/progressive-web-application-pwa-framework-part-3 "设计和生成不带框架的渐进式 Web 应用程序 (第 3 部分) "  

[VapidkeysMain]: https://vapidkeys.com "保护 VAPID 密钥生成器|VapidKeys" 

[Webhint]: https://webhint.io "webhint"  

[WebDevProgressiveWebApps]: https://developers.google.com/web/progressive-web-apps "渐进式 Web 应用|web.dev"  

[WikiProgressiveEnhancement]: https://en.wikipedia.org/wiki/Progressive_enhancement "渐进式|Wikipedia"  
