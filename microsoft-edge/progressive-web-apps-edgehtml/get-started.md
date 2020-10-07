---
description: This guide gives you an overview of PWA basics and tools for building progressive web apps on Windows.
title: Get started with Progressive Web Apps
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/17/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: progressive web apps, PWA, Edge, Windows, PWABuilder, web manifest, service worker, push
ms.openlocfilehash: 84d7c753cfece1591348e06b6728939187e37482
ms.sourcegitcommit: ef6d6adae1f4d18a219fa3e17f91b95b40367a40
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/18/2020
ms.locfileid: "10934903"
---
# <span data-ttu-id="efbc5-104">Get started with Progressive Web Apps</span><span class="sxs-lookup"><span data-stu-id="efbc5-104">Get started with Progressive Web Apps</span></span>  

<span data-ttu-id="efbc5-105">Progressive Web Apps \(PWAs\) are simply web apps that are [progressively enhanced][WikiProgressiveEnhancement] with native app-like features on supporting platforms and browser engines, such as launch-from-homescreen installation, offline support, and push notifications.</span><span class="sxs-lookup"><span data-stu-id="efbc5-105">Progressive Web Apps \(PWAs\) are simply web apps that are [progressively enhanced][WikiProgressiveEnhancement] with native app-like features on supporting platforms and browser engines, such as launch-from-homescreen installation, offline support, and push notifications.</span></span>  <span data-ttu-id="efbc5-106">On Windows 10 with the Microsoft Edge \(EdgeHTML\) engine, PWAs enjoy the added advantage of running independently of the browser window as [Universal Windows Platform][WindowsUwpGetStartedWhat] apps.</span><span class="sxs-lookup"><span data-stu-id="efbc5-106">On Windows 10 with the Microsoft Edge \(EdgeHTML\) engine, PWAs enjoy the added advantage of running independently of the browser window as [Universal Windows Platform][WindowsUwpGetStartedWhat] apps.</span></span>  

<span data-ttu-id="efbc5-107">This guide gives you an overview of PWA basics by building a simple `localhost` web app as a PWA using Microsoft Visual Studio and some PWA Builder utilities.</span><span class="sxs-lookup"><span data-stu-id="efbc5-107">This guide gives you an overview of PWA basics by building a simple `localhost` web app as a PWA using Microsoft Visual Studio and some PWA Builder utilities.</span></span>  <span data-ttu-id="efbc5-108">The finished product works similarly across any browser that supports PWAs.</span><span class="sxs-lookup"><span data-stu-id="efbc5-108">The finished product works similarly across any browser that supports PWAs.</span></span>  

> [!TIP]
> <span data-ttu-id="efbc5-109">For a quick way to convert an existing site to a PWA and package it for Windows 10 and other app platforms, review [PWA Builder][PwaBuilder].</span><span class="sxs-lookup"><span data-stu-id="efbc5-109">For a quick way to convert an existing site to a PWA and package it for Windows 10 and other app platforms, review [PWA Builder][PwaBuilder].</span></span>  

## <span data-ttu-id="efbc5-110">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="efbc5-110">Prerequisites</span></span>  

<span data-ttu-id="efbc5-111">You may build PWAs with any web development IDE.</span><span class="sxs-lookup"><span data-stu-id="efbc5-111">You may build PWAs with any web development IDE.</span></span>  <span data-ttu-id="efbc5-112">The following are only prerequisites for this guide, which walks you through PWA tooling support in the Windows developer ecosystem.</span><span class="sxs-lookup"><span data-stu-id="efbc5-112">The following are only prerequisites for this guide, which walks you through PWA tooling support in the Windows developer ecosystem.</span></span>  

*   <span data-ttu-id="efbc5-113">Download the \(free\) [Visual Studio Community 2017][VisualStudioDownloads].</span><span class="sxs-lookup"><span data-stu-id="efbc5-113">Download the \(free\) [Visual Studio Community 2017][VisualStudioDownloads].</span></span>  <span data-ttu-id="efbc5-114">You may also use the Professional, Enterprise, or [Preview][VisualStudioPreview] editions.</span><span class="sxs-lookup"><span data-stu-id="efbc5-114">You may also use the Professional, Enterprise, or [Preview][VisualStudioPreview] editions.</span></span>  <span data-ttu-id="efbc5-115">From the Visual Studio Installer, choose the following Workloads.</span><span class="sxs-lookup"><span data-stu-id="efbc5-115">From the Visual Studio Installer, choose the following Workloads.</span></span>  
    
    *   **<span data-ttu-id="efbc5-116">Universal Windows Platform development</span><span class="sxs-lookup"><span data-stu-id="efbc5-116">Universal Windows Platform development</span></span>**  
    *   **<span data-ttu-id="efbc5-117">Node.js development</span><span class="sxs-lookup"><span data-stu-id="efbc5-117">Node.js development</span></span>**  

## <span data-ttu-id="efbc5-118">Set up a basic web app</span><span class="sxs-lookup"><span data-stu-id="efbc5-118">Set up a basic web app</span></span>  

<span data-ttu-id="efbc5-119">For the sake of simplicity, use the Visual Studio [Node.js and Express app][VisualStudioNodeJsTutorial] template to create `localhost` web app that serves up an `index.html` page.</span><span class="sxs-lookup"><span data-stu-id="efbc5-119">For the sake of simplicity, use the Visual Studio [Node.js and Express app][VisualStudioNodeJsTutorial] template to create `localhost` web app that serves up an `index.html` page.</span></span>  <span data-ttu-id="efbc5-120">Imagine this as a placeholder for the compelling, full-featured web app that you are developing as a PWA.</span><span class="sxs-lookup"><span data-stu-id="efbc5-120">Imagine this as a placeholder for the compelling, full-featured web app that you are developing as a PWA.</span></span>  

1.  <span data-ttu-id="efbc5-121">Launch Visual Studio, and start a new project.</span><span class="sxs-lookup"><span data-stu-id="efbc5-121">Launch Visual Studio, and start a new project.</span></span>  
    *   <span data-ttu-id="efbc5-122">**File** > **New** > **Project...**</span><span class="sxs-lookup"><span data-stu-id="efbc5-122">**File** > **New** > **Project...**</span></span>  
    *   `Ctrl`+`Shift`+`N`  
1.  <span data-ttu-id="efbc5-123">Under **JavaScript**, select **Basic Node.js Express 4 Application**.</span><span class="sxs-lookup"><span data-stu-id="efbc5-123">Under **JavaScript**, select **Basic Node.js Express 4 Application**.</span></span>  <span data-ttu-id="efbc5-124">Set the name and location and choose **OK**.</span><span class="sxs-lookup"><span data-stu-id="efbc5-124">Set the name and location and choose **OK**.</span></span>  
    
    ![Selecting the Node.js Express 4 project template in Visual Studio][ImageVsNodejsExpressTemplate]  
    
1.  <span data-ttu-id="efbc5-126">Once your new project loads, choose **Build** \(`Ctrl`+`Shift`+`B`\) and **Start Debugging** \(`F5`\).</span><span class="sxs-lookup"><span data-stu-id="efbc5-126">Once your new project loads, choose **Build** \(`Ctrl`+`Shift`+`B`\) and **Start Debugging** \(`F5`\).</span></span>  <span data-ttu-id="efbc5-127">Verify that your `index.html` file loads when you browse to `http://localhost:1337`.</span><span class="sxs-lookup"><span data-stu-id="efbc5-127">Verify that your `index.html` file loads when you browse to `http://localhost:1337`.</span></span>  
    
    ![Running your new site on localhost][ImageVsNodejsExpressIndex]  

## <span data-ttu-id="efbc5-129">Turn your app into a PWA</span><span class="sxs-lookup"><span data-stu-id="efbc5-129">Turn your app into a PWA</span></span>  

<span data-ttu-id="efbc5-130">Now it is time to wire up the basic [PWA requirements][PwaEdgehtmlIndexRequirements] for your web app: a *Web App Manifest*, *HTTPS* and *Service Workers*.</span><span class="sxs-lookup"><span data-stu-id="efbc5-130">Now it is time to wire up the basic [PWA requirements][PwaEdgehtmlIndexRequirements] for your web app: a *Web App Manifest*, *HTTPS* and *Service Workers*.</span></span>  

### <span data-ttu-id="efbc5-131">Web App Manifest</span><span class="sxs-lookup"><span data-stu-id="efbc5-131">Web App Manifest</span></span>  

<span data-ttu-id="efbc5-132">A [Web App Manifest][MDNWebAppManifest] is a JSON metadata file describing your app, including the name, author, entry page URL, and one or more icons.</span><span class="sxs-lookup"><span data-stu-id="efbc5-132">A [Web App Manifest][MDNWebAppManifest] is a JSON metadata file describing your app, including the name, author, entry page URL, and one or more icons.</span></span>  <span data-ttu-id="efbc5-133">Because it follows a [standards-based schema][W3cWebAppManifest], you must only supply a single web app manifest for the PWA that you are installing on any platform, OS, and device combination that supports PWAs.</span><span class="sxs-lookup"><span data-stu-id="efbc5-133">Because it follows a [standards-based schema][W3cWebAppManifest], you must only supply a single web app manifest for the PWA that you are installing on any platform, OS, and device combination that supports PWAs.</span></span>  <span data-ttu-id="efbc5-134">In the Windows ecosystem, your web app manifest signals to the Bing web indexer that your PWA is a candidate for automatic inclusion in the [Microsoft Store][PwaEdgehtmlMicrosoftStore], where it may reach nearly 700 million active monthly users as a Windows 10 app.</span><span class="sxs-lookup"><span data-stu-id="efbc5-134">In the Windows ecosystem, your web app manifest signals to the Bing web indexer that your PWA is a candidate for automatic inclusion in the [Microsoft Store][PwaEdgehtmlMicrosoftStore], where it may reach nearly 700 million active monthly users as a Windows 10 app.</span></span>  

<span data-ttu-id="efbc5-135">If this were an existing live site, you may generate a web app manifest using [PWA Builder][PwaBuilder].</span><span class="sxs-lookup"><span data-stu-id="efbc5-135">If this were an existing live site, you may generate a web app manifest using [PWA Builder][PwaBuilder].</span></span>  <span data-ttu-id="efbc5-136">Since it is still an unpublished project, copy a sample manifest.</span><span class="sxs-lookup"><span data-stu-id="efbc5-136">Since it is still an unpublished project, copy a sample manifest.</span></span>  

1.  <span data-ttu-id="efbc5-137">In the Visual Studio *Solution Explorer*, right-click the *public* folder and select **Add** > **New File...**, specifying `manifest.json` as the item name.</span><span class="sxs-lookup"><span data-stu-id="efbc5-137">In the Visual Studio *Solution Explorer*, right-click the *public* folder and select **Add** > **New File...**, specifying `manifest.json` as the item name.</span></span>  
1.  <span data-ttu-id="efbc5-138">In the `manifest.json` file, copy the following code.</span><span class="sxs-lookup"><span data-stu-id="efbc5-138">In the `manifest.json` file, copy the following code.</span></span>  

    ```json
    {
        "dir": "ltr",
        "lang": "en-us",
        "name": "My Sample PWA",
        "scope": "/",
        "display": "browser",
        "start_url": "https://PLACEHOLDER-FOR-PWA-URL",
        "short_name": "SamplePWA",
        "theme_color": "transparent",
        "description": "A sample PWA for testing purposes",
        "orientation": "any",
        "background_color": "transparent",
        "related_applications": [],
        "prefer_related_applications": false,
        "icons": []
    }
    ```  
    
    <span data-ttu-id="efbc5-139">In a real PWA, the next step is to customize *name*, *start_url*, *short_name*, *description*, and *icons* \(icons are covered in the next step\).</span><span class="sxs-lookup"><span data-stu-id="efbc5-139">In a real PWA, the next step is to customize *name*, *start_url*, *short_name*, *description*, and *icons* \(icons are covered in the next step\).</span></span>  
    
    <span data-ttu-id="efbc5-140">To learn more about the different member values and associated purposes, see the [Web App Manifest][MDNWebAppManifest] reference.</span><span class="sxs-lookup"><span data-stu-id="efbc5-140">To learn more about the different member values and associated purposes, see the [Web App Manifest][MDNWebAppManifest] reference.</span></span>  
    
1.  <span data-ttu-id="efbc5-141">Next, fill in the empty `icons` array with actual image paths by using the PWA Builder App Image Generator.</span><span class="sxs-lookup"><span data-stu-id="efbc5-141">Next, fill in the empty `icons` array with actual image paths by using the PWA Builder App Image Generator.</span></span>  
    
    1.  <span data-ttu-id="efbc5-142">Using a web browser, download this [sample 512x512 PWA image][ImagePwa].</span><span class="sxs-lookup"><span data-stu-id="efbc5-142">Using a web browser, download this [sample 512x512 PWA image][ImagePwa].</span></span>  
    1.  <span data-ttu-id="efbc5-143">Go to the PWA Builder [App Image Generator][PwaBuilderAppImageGenerator], and select the `pwa.png` image you just saved as the **Input Image** and then choose the **Download** button.</span><span class="sxs-lookup"><span data-stu-id="efbc5-143">Go to the PWA Builder [App Image Generator][PwaBuilderAppImageGenerator], and select the `pwa.png` image you just saved as the **Input Image** and then choose the **Download** button.</span></span>  
    1.  <span data-ttu-id="efbc5-144">**Open** and **Extract** the zip file.</span><span class="sxs-lookup"><span data-stu-id="efbc5-144">**Open** and **Extract** the zip file.</span></span>  
    1.  <span data-ttu-id="efbc5-145">In the Visual Studio Solution Explorer, right-click the `public` folder and **Open Folder in File Explorer**.</span><span class="sxs-lookup"><span data-stu-id="efbc5-145">In the Visual Studio Solution Explorer, right-click the `public` folder and **Open Folder in File Explorer**.</span></span>  <span data-ttu-id="efbc5-146">Create a **New folder** named `images`.</span><span class="sxs-lookup"><span data-stu-id="efbc5-146">Create a **New folder** named `images`.</span></span>  
    1.  <span data-ttu-id="efbc5-147">Copy all of the platform folders \(`android`, `chrome`, `windows10`, and so on\) from your extracted zip to the `images` folder and close the file explorer window.</span><span class="sxs-lookup"><span data-stu-id="efbc5-147">Copy all of the platform folders \(`android`, `chrome`, `windows10`, and so on\) from your extracted zip to the `images` folder and close the file explorer window.</span></span>  <span data-ttu-id="efbc5-148">Add the folders to your Visual Studio project \(in Solution Explorer, right-click `images` folder and select **Add** > **Existing folder...** for each of the folders\).</span><span class="sxs-lookup"><span data-stu-id="efbc5-148">Add the folders to your Visual Studio project \(in Solution Explorer, right-click `images` folder and select **Add** > **Existing folder...** for each of the folders\).</span></span>  
    1.  <span data-ttu-id="efbc5-149">Open \(with Visual Studio or any editor\) the `icons.json` file from the extracted zip and copy the `"icons": [...]` array into the `manifest.json` file of your project.</span><span class="sxs-lookup"><span data-stu-id="efbc5-149">Open \(with Visual Studio or any editor\) the `icons.json` file from the extracted zip and copy the `"icons": [...]` array into the `manifest.json` file of your project.</span></span>  

1.  <span data-ttu-id="efbc5-150">Now you must associate your web app manifest with your app.</span><span class="sxs-lookup"><span data-stu-id="efbc5-150">Now you must associate your web app manifest with your app.</span></span>  <span data-ttu-id="efbc5-151">Open the `layout.pug` file \(in `views` folder\) for editing, and add this line right after the stylesheet link.</span><span class="sxs-lookup"><span data-stu-id="efbc5-151">Open the `layout.pug` file \(in `views` folder\) for editing, and add this line right after the stylesheet link.</span></span>  <span data-ttu-id="efbc5-152">\(It is simply the Node [pug][PugAttributes] template shorthand for `<link rel='manifest' href='/manifest.json'>`\).</span><span class="sxs-lookup"><span data-stu-id="efbc5-152">\(It is simply the Node [pug][PugAttributes] template shorthand for `<link rel='manifest' href='/manifest.json'>`\).</span></span>  
    
    ```html
    link(rel='manifest', href='/manifest.json')
    ```  
    
<span data-ttu-id="efbc5-153">With all that in place, your web app is now serving up a manifest and homescreen-ready app icons!</span><span class="sxs-lookup"><span data-stu-id="efbc5-153">With all that in place, your web app is now serving up a manifest and homescreen-ready app icons!</span></span>  <span data-ttu-id="efbc5-154">Try running your app \(`F5`\) and loading up the manifest.</span><span class="sxs-lookup"><span data-stu-id="efbc5-154">Try running your app \(`F5`\) and loading up the manifest.</span></span>  

![Web App Manifest loading from localhost][ImageVsNodejsExpressManifest]  

<span data-ttu-id="efbc5-156">And one of your icons.</span><span class="sxs-lookup"><span data-stu-id="efbc5-156">And one of your icons.</span></span>  

![Square71x71Logo app logo loading from localhost][ImageVsNodejsExpressIcon]  

<span data-ttu-id="efbc5-158">If you publish the app live \(with an actual `start_url`\), the Bing search engine now identifies it as a candidate for [automatic packaging and submission to the Microsoft Store][PwaEdgehtmlMicrosoftStore] as an installable Windows 10 app.</span><span class="sxs-lookup"><span data-stu-id="efbc5-158">If you publish the app live \(with an actual `start_url`\), the Bing search engine now identifies it as a candidate for [automatic packaging and submission to the Microsoft Store][PwaEdgehtmlMicrosoftStore] as an installable Windows 10 app.</span></span>  <span data-ttu-id="efbc5-159">Ensure that your manifest.json file includes the [Quality signals for Progressive Web Apps][WindowsBlogsPwaEdge] for which Bing scans including the following items.</span><span class="sxs-lookup"><span data-stu-id="efbc5-159">Ensure that your manifest.json file includes the [Quality signals for Progressive Web Apps][WindowsBlogsPwaEdge] for which Bing scans including the following items.</span></span>   

*   `name`  
*   `description`  
*   <span data-ttu-id="efbc5-160">At least one icon 512px square or larger \(to ensure an image source of sufficient resolution for auto-generating the splash screen of your app, store listing, tile image, and so on\).</span><span class="sxs-lookup"><span data-stu-id="efbc5-160">At least one icon 512px square or larger \(to ensure an image source of sufficient resolution for auto-generating the splash screen of your app, store listing, tile image, and so on\).</span></span>  

<span data-ttu-id="efbc5-161">In addition, use [HTTPS](#https), [service workers](#service-workers), and comply with [Microsoft Store Policies][LegalWindowsAgrementsMicrosoftStorePolicies].</span><span class="sxs-lookup"><span data-stu-id="efbc5-161">In addition, use [HTTPS](#https), [service workers](#service-workers), and comply with [Microsoft Store Policies][LegalWindowsAgrementsMicrosoftStorePolicies].</span></span>  

### <span data-ttu-id="efbc5-162">HTTPS</span><span class="sxs-lookup"><span data-stu-id="efbc5-162">HTTPS</span></span>  

<span data-ttu-id="efbc5-163">[Service Workers][MDNServiceWorkerApi] and other key PWA technologies that work with service workers \(such as the [Cache][MDNCache], [Push][MDNPushApi], and [Background Sync][MDNSyncManager] APIs\) only work across secure connections, which means [HTTPS][WikiHttps] for live sites or `localhost` for debugging purposes.</span><span class="sxs-lookup"><span data-stu-id="efbc5-163">[Service Workers][MDNServiceWorkerApi] and other key PWA technologies that work with service workers \(such as the [Cache][MDNCache], [Push][MDNPushApi], and [Background Sync][MDNSyncManager] APIs\) only work across secure connections, which means [HTTPS][WikiHttps] for live sites or `localhost` for debugging purposes.</span></span>  

<span data-ttu-id="efbc5-164">If you [publish this web app as a live site][VisualStudioNodejsTutorialPublishAzureAppService] \(for example, by setting up an [Azure free account][AzureCreateFreeAccount]\), you must ensure your server is configured for HTTPS.</span><span class="sxs-lookup"><span data-stu-id="efbc5-164">If you [publish this web app as a live site][VisualStudioNodejsTutorialPublishAzureAppService] \(for example, by setting up an [Azure free account][AzureCreateFreeAccount]\), you must ensure your server is configured for HTTPS.</span></span>  <span data-ttu-id="efbc5-165">If you use the [Microsoft Azure App Service][AzureWebApps] to host your site, it is served over HTTPS by default.</span><span class="sxs-lookup"><span data-stu-id="efbc5-165">If you use the [Microsoft Azure App Service][AzureWebApps] to host your site, it is served over HTTPS by default.</span></span>  

<span data-ttu-id="efbc5-166">For this guide, continue using `http://localhost` as a placeholder for a live site served over `https://`.</span><span class="sxs-lookup"><span data-stu-id="efbc5-166">For this guide, continue using `http://localhost` as a placeholder for a live site served over `https://`.</span></span>  

### <span data-ttu-id="efbc5-167">Service Workers</span><span class="sxs-lookup"><span data-stu-id="efbc5-167">Service Workers</span></span>  

<span data-ttu-id="efbc5-168">Service Workers is the key technology behind PWAs.</span><span class="sxs-lookup"><span data-stu-id="efbc5-168">Service Workers is the key technology behind PWAs.</span></span> <span data-ttu-id="efbc5-169">Service Workers act as a proxy between your PWA and the network to enable your website to function as an installed native app that serves up offline scenarios, responds to server push notifications, and runs background tasks.</span><span class="sxs-lookup"><span data-stu-id="efbc5-169">Service Workers act as a proxy between your PWA and the network to enable your website to function as an installed native app that serves up offline scenarios, responds to server push notifications, and runs background tasks.</span></span>  <span data-ttu-id="efbc5-170">Service workers also open up new performance strategies.</span><span class="sxs-lookup"><span data-stu-id="efbc5-170">Service workers also open up new performance strategies.</span></span>  <span data-ttu-id="efbc5-171">You are not required to implement a full web app to use the service worker cache for fine-tuned page load performance for your website.</span><span class="sxs-lookup"><span data-stu-id="efbc5-171">You are not required to implement a full web app to use the service worker cache for fine-tuned page load performance for your website.</span></span>  

<span data-ttu-id="efbc5-172">Service workers are event-driven background threads that run from JavaScript files served up alongside the regular scripts that power your web app.</span><span class="sxs-lookup"><span data-stu-id="efbc5-172">Service workers are event-driven background threads that run from JavaScript files served up alongside the regular scripts that power your web app.</span></span>  <span data-ttu-id="efbc5-173">Because Service workers do not run on the main UI thread, service workers do not have DOM access, though the [UI thread][MDNWorkerPrototypePostMessage] and a [worker thread][MDNDedicatedWorkerGlobalScopePostMessage] is able to communicate using `postMessage()` and `onmessage` event handlers.</span><span class="sxs-lookup"><span data-stu-id="efbc5-173">Because Service workers do not run on the main UI thread, service workers do not have DOM access, though the [UI thread][MDNWorkerPrototypePostMessage] and a [worker thread][MDNDedicatedWorkerGlobalScopePostMessage] is able to communicate using `postMessage()` and `onmessage` event handlers.</span></span>  

<span data-ttu-id="efbc5-174">You associate a service worker with your app by registering it to the URL origin of your site \(or a specified path within it\).</span><span class="sxs-lookup"><span data-stu-id="efbc5-174">You associate a service worker with your app by registering it to the URL origin of your site \(or a specified path within it\).</span></span>  <span data-ttu-id="efbc5-175">Once registered, the service worker file is then downloaded, installed, and activated on the user machine.</span><span class="sxs-lookup"><span data-stu-id="efbc5-175">Once registered, the service worker file is then downloaded, installed, and activated on the user machine.</span></span>  <span data-ttu-id="efbc5-176">For more, MDN web docs has a comprehensive guide on [Using Service Workers][MDNUsingServiceWorkers] and a detailed [Service Worker API][MDNServiceWorkerApi] reference.</span><span class="sxs-lookup"><span data-stu-id="efbc5-176">For more, MDN web docs has a comprehensive guide on [Using Service Workers][MDNUsingServiceWorkers] and a detailed [Service Worker API][MDNServiceWorkerApi] reference.</span></span>  

<span data-ttu-id="efbc5-177">For this tutorial, use the Offline page service worker script on [PWA Builder][PwaBuilderServiceWorker].</span><span class="sxs-lookup"><span data-stu-id="efbc5-177">For this tutorial, use the Offline page service worker script on [PWA Builder][PwaBuilderServiceWorker].</span></span>  <span data-ttu-id="efbc5-178">Start by customizing the script with more functionality according to your performance requirements, network bandwidth, and so on.</span><span class="sxs-lookup"><span data-stu-id="efbc5-178">Start by customizing the script with more functionality according to your performance requirements, network bandwidth, and so on.</span></span>  <span data-ttu-id="efbc5-179">Review the [Service Worker Cookbook][ServiceWorkerCookbook]  provided by Mozilla for a number of useful service worker caching ideas.</span><span class="sxs-lookup"><span data-stu-id="efbc5-179">Review the [Service Worker Cookbook][ServiceWorkerCookbook]  provided by Mozilla for a number of useful service worker caching ideas.</span></span>  

1.  <span data-ttu-id="efbc5-180">Open [https://www.pwabuilder.com/serviceworker][PwaBuilderServiceWorker] and select the \(default\) **Offline page** service worker and click the **Download service worker** button.</span><span class="sxs-lookup"><span data-stu-id="efbc5-180">Open [https://www.pwabuilder.com/serviceworker][PwaBuilderServiceWorker] and select the \(default\) **Offline page** service worker and click the **Download service worker** button.</span></span>  
1.  <span data-ttu-id="efbc5-181">Open the download folder and copy the following two files</span><span class="sxs-lookup"><span data-stu-id="efbc5-181">Open the download folder and copy the following two files</span></span>  

    *   <span data-ttu-id="efbc5-182">ServiceWorker1\pwabuilder-sw-register.js</span><span class="sxs-lookup"><span data-stu-id="efbc5-182">ServiceWorker1\pwabuilder-sw-register.js</span></span>  
    *   <span data-ttu-id="efbc5-183">ServiceWorker1\pwabuilder-sw.js</span><span class="sxs-lookup"><span data-stu-id="efbc5-183">ServiceWorker1\pwabuilder-sw.js</span></span>  
    
    <span data-ttu-id="efbc5-184">Save the files to the `public` folder of your Visual Studio web app project.</span><span class="sxs-lookup"><span data-stu-id="efbc5-184">Save the files to the `public` folder of your Visual Studio web app project.</span></span>  <span data-ttu-id="efbc5-185">\(From Visual Studio, use `Ctrl`+`O` to open file explorer to your project and navigate to the `public` folder\).</span><span class="sxs-lookup"><span data-stu-id="efbc5-185">\(From Visual Studio, use `Ctrl`+`O` to open file explorer to your project and navigate to the `public` folder\).</span></span>  
    
    <span data-ttu-id="efbc5-186">In Solution Explorer, open the `public/pwabuilder-sw.js` file, and change the value of `offlineFallbackPage` to `offline.html`.</span><span class="sxs-lookup"><span data-stu-id="efbc5-186">In Solution Explorer, open the `public/pwabuilder-sw.js` file, and change the value of `offlineFallbackPage` to `offline.html`.</span></span>  
    
    ```javascript
    const offlineFallbackPage = "offline.html";
    ```
    
    <span data-ttu-id="efbc5-187">It is worth reviewing the code in both of these files, to get the gist of how to register a service worker that caches a designated page \(`offline.html`\) and serves it when a network fetch fails.</span><span class="sxs-lookup"><span data-stu-id="efbc5-187">It is worth reviewing the code in both of these files, to get the gist of how to register a service worker that caches a designated page \(`offline.html`\) and serves it when a network fetch fails.</span></span>  <span data-ttu-id="efbc5-188">Next, create a simple `offline.html` page as a placeholder for the offline functionality of your app.</span><span class="sxs-lookup"><span data-stu-id="efbc5-188">Next, create a simple `offline.html` page as a placeholder for the offline functionality of your app.</span></span>  
    
1.  <span data-ttu-id="efbc5-189">In Solution Explorer, open the `views/layout.pug` file, and add the following line below your link tags.</span><span class="sxs-lookup"><span data-stu-id="efbc5-189">In Solution Explorer, open the `views/layout.pug` file, and add the following line below your link tags.</span></span>  
    
    ```html
    script(src='/pwabuilder-sw-register.js' type='module')
    ```  
    
    <span data-ttu-id="efbc5-190">Your site loads and runs your service worker registration script.</span><span class="sxs-lookup"><span data-stu-id="efbc5-190">Your site loads and runs your service worker registration script.</span></span>  
    
1.  <span data-ttu-id="efbc5-191">In Solution Explorer, right-click on the `public` folder and select **Add** > **New File...**.  Name it `offline.html`, and add a `<title>` and some body content, for example the following code.</span><span class="sxs-lookup"><span data-stu-id="efbc5-191">In Solution Explorer, right-click on the `public` folder and select **Add** > **New File...**.  Name it `offline.html`, and add a `<title>` and some body content, for example the following code.</span></span>  
    
    ```html
    <!DOCTYPE html>
    
    <html xmlns="http://www.w3.org/1999/xhtml">
    <head>
        <meta charset="utf-8" />
        <title>Offline mode</title>
    </head>
    <body>
        You are now offline.
    </body>
    </html>
    ```  
    
    <span data-ttu-id="efbc5-192">At this point, your `public` folder should have three new files.</span><span class="sxs-lookup"><span data-stu-id="efbc5-192">At this point, your `public` folder should have three new files.</span></span>  
    
    ![Files added to the public folder of the solution][ImageVsNodejsExpressPublic]  
    
1.  <span data-ttu-id="efbc5-194">In Solution Explorer, open the `routes\index.js` file, and add the following code just before the final command \(`module.exports = router;`\).</span><span class="sxs-lookup"><span data-stu-id="efbc5-194">In Solution Explorer, open the `routes\index.js` file, and add the following code just before the final command \(`module.exports = router;`\).</span></span>  
    
    ```javascript
    router.get('/offline.html', function (req, res) {
        res.sendFile('public/offline.html');
    });
    ```  
    
    <span data-ttu-id="efbc5-195">This instructs your app to serve the `offline.html` file \(when your service worker fetches it for the offline cache\).</span><span class="sxs-lookup"><span data-stu-id="efbc5-195">This instructs your app to serve the `offline.html` file \(when your service worker fetches it for the offline cache\).</span></span>  
    
1.  <span data-ttu-id="efbc5-196">Test out your PWA!</span><span class="sxs-lookup"><span data-stu-id="efbc5-196">Test out your PWA!</span></span>  <span data-ttu-id="efbc5-197">Build \(`Ctrl`+`Shift`+`B`\) and Run \(`F5`\) your web app to launch Microsoft Edge and open your `localhost` page.</span><span class="sxs-lookup"><span data-stu-id="efbc5-197">Build \(`Ctrl`+`Shift`+`B`\) and Run \(`F5`\) your web app to launch Microsoft Edge and open your `localhost` page.</span></span>  <span data-ttu-id="efbc5-198">Then complete the following steps.</span><span class="sxs-lookup"><span data-stu-id="efbc5-198">Then complete the following steps.</span></span>  
    
    1.  <span data-ttu-id="efbc5-199">Open the Edge DevTools **Console** \(`Ctrl`+`Shift`+`J`\) and verify the Service worker was registered.</span><span class="sxs-lookup"><span data-stu-id="efbc5-199">Open the Edge DevTools **Console** \(`Ctrl`+`Shift`+`J`\) and verify the Service worker was registered.</span></span>  
    1.  <span data-ttu-id="efbc5-200">In the **Debugger** panel, expand the **Service Workers** control and click on your origin.</span><span class="sxs-lookup"><span data-stu-id="efbc5-200">In the **Debugger** panel, expand the **Service Workers** control and click on your origin.</span></span>  <span data-ttu-id="efbc5-201">In the **Service Worker Overview**, verify your service worker is activated and running.</span><span class="sxs-lookup"><span data-stu-id="efbc5-201">In the **Service Worker Overview**, verify your service worker is activated and running.</span></span>  
        
        ![Edge DevTools Service Worker overview][ImageDevtoolsSwOverview]  
        
    1.  <span data-ttu-id="efbc5-203">Expand the **Cache** control and verify that the `offline.html` page is cached.</span><span class="sxs-lookup"><span data-stu-id="efbc5-203">Expand the **Cache** control and verify that the `offline.html` page is cached.</span></span>  
        
        ![Edge DevTools service worker Cache][ImageDevtoolsSwCache]  
        
1.  <span data-ttu-id="efbc5-205">Time to try your PWA as an offline app!</span><span class="sxs-lookup"><span data-stu-id="efbc5-205">Time to try your PWA as an offline app!</span></span>  <span data-ttu-id="efbc5-206">In Visual Studio, **Stop Debugging** \(`Shift`+`F5`\) your web app, then open Microsoft Edge \(or refresh\) to the localhost address of your website.</span><span class="sxs-lookup"><span data-stu-id="efbc5-206">In Visual Studio, **Stop Debugging** \(`Shift`+`F5`\) your web app, then open Microsoft Edge \(or refresh\) to the localhost address of your website.</span></span>  <span data-ttu-id="efbc5-207">It should now load the `offline.html` page \(thanks to your service worker and offline cache\)!</span><span class="sxs-lookup"><span data-stu-id="efbc5-207">It should now load the `offline.html` page \(thanks to your service worker and offline cache\)!</span></span>  
    
    ![offline.html from http://localhost:1337 loaded in Microsoft Edge][ImageOfflineHtml]  

## <span data-ttu-id="efbc5-209">Add push notifications</span><span class="sxs-lookup"><span data-stu-id="efbc5-209">Add push notifications</span></span>  

<span data-ttu-id="efbc5-210">Make your PWA more app-like by adding client-side support for push notifications using the [Push API][MDNPushApi] to subscribe to a messaging service and the [Notifications API][MDNNotificationsApi] to display a toast message upon receiving a message.</span><span class="sxs-lookup"><span data-stu-id="efbc5-210">Make your PWA more app-like by adding client-side support for push notifications using the [Push API][MDNPushApi] to subscribe to a messaging service and the [Notifications API][MDNNotificationsApi] to display a toast message upon receiving a message.</span></span>  <span data-ttu-id="efbc5-211">As with Service Workers, these are standards-based APIs that work cross-browser, so you only have to write the code once for it to work everywhere PWAs are supported.</span><span class="sxs-lookup"><span data-stu-id="efbc5-211">As with Service Workers, these are standards-based APIs that work cross-browser, so you only have to write the code once for it to work everywhere PWAs are supported.</span></span>  <span data-ttu-id="efbc5-212">On the server side, use the [Web-Push][NPMWebPush] open-source library to handle the differences involved in delivering push messages to various browsers.</span><span class="sxs-lookup"><span data-stu-id="efbc5-212">On the server side, use the [Web-Push][NPMWebPush] open-source library to handle the differences involved in delivering push messages to various browsers.</span></span>  

<span data-ttu-id="efbc5-213">The following is adapted from the Push Rich Demo in [Service Worker Cookbook][ServiceWorkerCookbookPushRichDemo] provided by Mozilla, which is worth checking out for a number of other useful Web Push and service worker recipes.</span><span class="sxs-lookup"><span data-stu-id="efbc5-213">The following is adapted from the Push Rich Demo in [Service Worker Cookbook][ServiceWorkerCookbookPushRichDemo] provided by Mozilla, which is worth checking out for a number of other useful Web Push and service worker recipes.</span></span>  

### <span data-ttu-id="efbc5-214">Step 1 - Install the NPM web-push library</span><span class="sxs-lookup"><span data-stu-id="efbc5-214">Step 1 - Install the NPM web-push library</span></span>  

<span data-ttu-id="efbc5-215">In Visual Studio Solution Explorer, right-click your project and **Open Node.js Interactive Window...**.  In it, type the following code.</span><span class="sxs-lookup"><span data-stu-id="efbc5-215">In Visual Studio Solution Explorer, right-click your project and **Open Node.js Interactive Window...**.  In it, type the following code.</span></span>  

```javascript
.npm install web-push
```  

<span data-ttu-id="efbc5-216">This installs the [Web-Push][NPMWebPush] library.</span><span class="sxs-lookup"><span data-stu-id="efbc5-216">This installs the [Web-Push][NPMWebPush] library.</span></span>  <span data-ttu-id="efbc5-217">Then, open up your `index.js` file, and add the following line to the top of your file after the other requirement statements.</span><span class="sxs-lookup"><span data-stu-id="efbc5-217">Then, open up your `index.js` file, and add the following line to the top of your file after the other requirement statements.</span></span>  

```javascript
var webpush = require('web-push');
```  

### <span data-ttu-id="efbc5-218">Step 2 - Generate VAPID keys for your server</span><span class="sxs-lookup"><span data-stu-id="efbc5-218">Step 2 - Generate VAPID keys for your server</span></span>  

<span data-ttu-id="efbc5-219">Next you must generate VAPID \(Voluntary Application Server Identification\) keys for your server to send push messages to the PWA client.</span><span class="sxs-lookup"><span data-stu-id="efbc5-219">Next you must generate VAPID \(Voluntary Application Server Identification\) keys for your server to send push messages to the PWA client.</span></span>  <span data-ttu-id="efbc5-220">You only have to do this once \(that is, your server only requires a single pair of VAPID keys\).</span><span class="sxs-lookup"><span data-stu-id="efbc5-220">You only have to do this once \(that is, your server only requires a single pair of VAPID keys\).</span></span>  <span data-ttu-id="efbc5-221">In the Node.js Interactive Window, type the following code.</span><span class="sxs-lookup"><span data-stu-id="efbc5-221">In the Node.js Interactive Window, type the following code.</span></span>  

```javascript
var webpush = require('web-push');
webpush.generateVAPIDKeys();
```  

<span data-ttu-id="efbc5-222">The output should result in a JSON object containing a public and private key, which you copy into your server logic.</span><span class="sxs-lookup"><span data-stu-id="efbc5-222">The output should result in a JSON object containing a public and private key, which you copy into your server logic.</span></span>  

<span data-ttu-id="efbc5-223">In your `index.js` file, just before the final  \(`module.exports = router`\) line, add the following code.</span><span class="sxs-lookup"><span data-stu-id="efbc5-223">In your `index.js` file, just before the final  \(`module.exports = router`\) line, add the following code.</span></span>  

```javascript
const vapidKeys = {
    publicKey: '',
    privateKey: ''
};

webpush.setVapidDetails(
    'mailto:pwa@example.com',
    vapidKeys.publicKey,
    vapidKeys.privateKey
);
```  

<span data-ttu-id="efbc5-224">Copy the `publicKey` and `privateKey` values that you just generated.</span><span class="sxs-lookup"><span data-stu-id="efbc5-224">Copy the `publicKey` and `privateKey` values that you just generated.</span></span>  <span data-ttu-id="efbc5-225">Feel free to customize the `mailto` address as well \(though it is not required in order to run this sample\).</span><span class="sxs-lookup"><span data-stu-id="efbc5-225">Feel free to customize the `mailto` address as well \(though it is not required in order to run this sample\).</span></span>  

<span data-ttu-id="efbc5-226">The [Mozilla Services engineering blog][MozillaServicesSendingVapidWebPushNotificationsPush] has a nice explainer on VAPID and WebPush if you are interested in the details of how it works behind the scenes.</span><span class="sxs-lookup"><span data-stu-id="efbc5-226">The [Mozilla Services engineering blog][MozillaServicesSendingVapidWebPushNotificationsPush] has a nice explainer on VAPID and WebPush if you are interested in the details of how it works behind the scenes.</span></span>  

### <span data-ttu-id="efbc5-227">Step 3 - Handle push-related server requests</span><span class="sxs-lookup"><span data-stu-id="efbc5-227">Step 3 - Handle push-related server requests</span></span>  

<span data-ttu-id="efbc5-228">Now set up routes for handling push-related requests from the PWA client, including serving up the VAPID public key and registering the client to receive pushes.</span><span class="sxs-lookup"><span data-stu-id="efbc5-228">Now set up routes for handling push-related requests from the PWA client, including serving up the VAPID public key and registering the client to receive pushes.</span></span>  

<span data-ttu-id="efbc5-229">In a real scenario, a push notification likely originates from an event in your server logic.</span><span class="sxs-lookup"><span data-stu-id="efbc5-229">In a real scenario, a push notification likely originates from an event in your server logic.</span></span>  <span data-ttu-id="efbc5-230">To simplify things here, you must add a **Push Notification** button to our PWA homepage for generating pushes from our server, and a `/sendNotification` endpoint \(server route\)for handling those requests.</span><span class="sxs-lookup"><span data-stu-id="efbc5-230">To simplify things here, you must add a **Push Notification** button to our PWA homepage for generating pushes from our server, and a `/sendNotification` endpoint \(server route\)for handling those requests.</span></span>  

<span data-ttu-id="efbc5-231">In your `index.js` file, append the following routes just after the VAPID initialization code you added in [Step 2][#step-2---generate-vapid-keys-for-your-server].</span><span class="sxs-lookup"><span data-stu-id="efbc5-231">In your `index.js` file, append the following routes just after the VAPID initialization code you added in [Step 2][#step-2---generate-vapid-keys-for-your-server].</span></span>  

```javascript
router.get('/vapidPublicKey', function (req, res) {
    res.send(vapidKeys.publicKey);
});

router.post('/register', function (req, res) {
    // A real world application stores the subscription info.
    res.sendStatus(201);
});

router.post('/sendNotification', function (req, res) {
    const subscription = req.body.subscription;
    const payload = 'payload';
    const options = null;
    
    webpush.sendNotification(subscription, payload, options)
        .then(function () {
            res.sendStatus(201);
        })
        .catch(function (error) {
            res.sendStatus(500);
            console.log(error);
        });
});
```  

<span data-ttu-id="efbc5-232">With the server-side code in place, plumb in push notifications on the PWA client.</span><span class="sxs-lookup"><span data-stu-id="efbc5-232">With the server-side code in place, plumb in push notifications on the PWA client.</span></span>  

### <span data-ttu-id="efbc5-233">Step 4 - Subscribe to push notifications</span><span class="sxs-lookup"><span data-stu-id="efbc5-233">Step 4 - Subscribe to push notifications</span></span>  

<span data-ttu-id="efbc5-234">As part of their role as PWA network proxies, service workers handle push events and toast notification interactions.</span><span class="sxs-lookup"><span data-stu-id="efbc5-234">As part of their role as PWA network proxies, service workers handle push events and toast notification interactions.</span></span>  <span data-ttu-id="efbc5-235">However, as it is with first setting up \(or registering\) a service worker, subscribing the PWA to server push notifications happens on the main UI thread of the PWA and requires network connectivity.</span><span class="sxs-lookup"><span data-stu-id="efbc5-235">However, as it is with first setting up \(or registering\) a service worker, subscribing the PWA to server push notifications happens on the main UI thread of the PWA and requires network connectivity.</span></span>  <span data-ttu-id="efbc5-236">Subscribing to push notifications requires an active service worker registration, so you must first verify that your service worker is installed and active before trying to subscribe it to push notifications.</span><span class="sxs-lookup"><span data-stu-id="efbc5-236">Subscribing to push notifications requires an active service worker registration, so you must first verify that your service worker is installed and active before trying to subscribe it to push notifications.</span></span>  

<span data-ttu-id="efbc5-237">Before a new push subscription is created, Microsoft Edge check if the user granted the PWA permission to receive notifications.</span><span class="sxs-lookup"><span data-stu-id="efbc5-237">Before a new push subscription is created, Microsoft Edge check if the user granted the PWA permission to receive notifications.</span></span>  <span data-ttu-id="efbc5-238">If not, the user is prompted by the browser for permission.</span><span class="sxs-lookup"><span data-stu-id="efbc5-238">If not, the user is prompted by the browser for permission.</span></span>  <span data-ttu-id="efbc5-239">If the permission is denied, the request to `registration.pushManager.subscribe` throws a `DOMException`, so you must handle it.</span><span class="sxs-lookup"><span data-stu-id="efbc5-239">If the permission is denied, the request to `registration.pushManager.subscribe` throws a `DOMException`, so you must handle it.</span></span>  <span data-ttu-id="efbc5-240">For more on permission management, see [Push Notifications in Microsoft Edge][WindowsBlogsWebNotificationsEdge].</span><span class="sxs-lookup"><span data-stu-id="efbc5-240">For more on permission management, see [Push Notifications in Microsoft Edge][WindowsBlogsWebNotificationsEdge].</span></span>  

<span data-ttu-id="efbc5-241">In your `pwabuilder-sw-register.js` file, append the following code.</span><span class="sxs-lookup"><span data-stu-id="efbc5-241">In your `pwabuilder-sw-register.js` file, append the following code.</span></span>  

```javascript
// Subscribe this PWA to push notifications from the server
navigator.serviceWorker.ready
    .then(function (registration) {
        // Check if the user has an existing subscription
        return registration.pushManager.getSubscription()
            .then(async function (subscription) {
                if (subscription) {
                    return subscription;
                }
                
                // Otherwise subscribe with the server public key
                const response = await fetch('./vapidPublicKey');
                const vapidPublicKey = await response.text();
                const convertedVapidKey = urlBase64ToUint8Array(vapidPublicKey);
                
                return registration.pushManager.subscribe({
                    userVisibleOnly: true,
                    applicationServerKey: convertedVapidKey
                });
            });
    }).then(function (subscription) {
        // Send the subscription details to the server
        fetch('./register', {
            method: 'post',
            headers: {
                'Content-type': 'application/json'
            },
            body: JSON.stringify({
                subscription: subscription
            }),
        });
        
        // Create a button to mimic server pushes for testing purposes
        var button = document.createElement('input');
        button.type = 'button';
        button.id = 'notify';
        button.value = 'Send Notification';
        document.body.appendChild(button);
        document.getElementById('notify').addEventListener('click', function () {
            fetch('./sendNotification', {
                method: 'post',
                headers: {
                    'Content-type': 'application/json'
                },
                body: JSON.stringify({
                    subscription: subscription
                }),
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

<span data-ttu-id="efbc5-242">Review the MDN documentation on the [PushManager][MDNPushManager] interface and NPM docs on the [Web-Push][NPMWebPushUsage] library for more details on how the APIs work and various related options.</span><span class="sxs-lookup"><span data-stu-id="efbc5-242">Review the MDN documentation on the [PushManager][MDNPushManager] interface and NPM docs on the [Web-Push][NPMWebPushUsage] library for more details on how the APIs work and various related options.</span></span>  

### <span data-ttu-id="efbc5-243">Step 5 - Set up push and notificationclick event handlers</span><span class="sxs-lookup"><span data-stu-id="efbc5-243">Step 5 - Set up push and notificationclick event handlers</span></span>  

<span data-ttu-id="efbc5-244">With our push subscription set up, the remainder of the work happens in the service worker.</span><span class="sxs-lookup"><span data-stu-id="efbc5-244">With our push subscription set up, the remainder of the work happens in the service worker.</span></span>  <span data-ttu-id="efbc5-245">First you must set up a handler for server-sent push events, and respond with a toast notification \(if permission was granted\) displaying the push data payload.</span><span class="sxs-lookup"><span data-stu-id="efbc5-245">First you must set up a handler for server-sent push events, and respond with a toast notification \(if permission was granted\) displaying the push data payload.</span></span>  <span data-ttu-id="efbc5-246">Next you add a click handler for the toast to dismiss the notification and sort through a list of currently open windows to open, focus, or open and focus the intended PWA client page.</span><span class="sxs-lookup"><span data-stu-id="efbc5-246">Next you add a click handler for the toast to dismiss the notification and sort through a list of currently open windows to open, focus, or open and focus the intended PWA client page.</span></span>  

<span data-ttu-id="efbc5-247">In your `pwabuilder-sw.js` file, append the following handlers.</span><span class="sxs-lookup"><span data-stu-id="efbc5-247">In your `pwabuilder-sw.js` file, append the following handlers.</span></span>  

```javascript
//Respond to a server push with a user notification
self.addEventListener('push', function (event) {
    if ("granted" === Notification.permission) {
        var payload = event.data ? event.data.text() : 'no payload';
        const promiseChain = self.registration.showNotification('Sample PWA', {
            body: payload,
            icon: 'images/windows10/Square44x44Logo.scale-100.png'
        });
        //Ensure the toast notification is displayed before exiting this function
        event.waitUntil(promiseChain);
    }
});
    
//Respond to the user clicking the toast notification
self.addEventListener('notificationclick', function (event) {
    console.log('On notification click: ', event.notification.tag);
    event.notification.close();
    
    // This looks to see if the current is already open and focuses it
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

### <span data-ttu-id="efbc5-248">Step 6 - Try it out</span><span class="sxs-lookup"><span data-stu-id="efbc5-248">Step 6 - Try it out</span></span>  

<span data-ttu-id="efbc5-249">Time to test push notifications in your PWA!</span><span class="sxs-lookup"><span data-stu-id="efbc5-249">Time to test push notifications in your PWA!</span></span>  

1.  <span data-ttu-id="efbc5-250">Run \(`F5`\) your PWA in the browser.</span><span class="sxs-lookup"><span data-stu-id="efbc5-250">Run \(`F5`\) your PWA in the browser.</span></span>  <span data-ttu-id="efbc5-251">Because you modified the service worker code \(`pwabuilder-sw.js`\), you must open the DevTools Debugger \(`F12`\) to the **Service Worker Overview** panel and **Unregister** the service worker and reload \(`F5`\) the page to re-register it \(or you click **Update**\).</span><span class="sxs-lookup"><span data-stu-id="efbc5-251">Because you modified the service worker code \(`pwabuilder-sw.js`\), you must open the DevTools Debugger \(`F12`\) to the **Service Worker Overview** panel and **Unregister** the service worker and reload \(`F5`\) the page to re-register it \(or you click **Update**\).</span></span>  <span data-ttu-id="efbc5-252">In a production scenario, the browser checks regularly check for service worker updates and install the updates in the background.</span><span class="sxs-lookup"><span data-stu-id="efbc5-252">In a production scenario, the browser checks regularly check for service worker updates and install the updates in the background.</span></span>  <span data-ttu-id="efbc5-253">You should force it here for immediate results.</span><span class="sxs-lookup"><span data-stu-id="efbc5-253">You should force it here for immediate results.</span></span>  
    
    <span data-ttu-id="efbc5-254">As your service worker activates and attempts to subscribe your PWA to push notifications, you should see a permission dialog at the bottom of the page.</span><span class="sxs-lookup"><span data-stu-id="efbc5-254">As your service worker activates and attempts to subscribe your PWA to push notifications, you should see a permission dialog at the bottom of the page.</span></span>  
    
    ![Permission dialog for enabling notifications][ImageNotificationPermission]  
    
    <span data-ttu-id="efbc5-256">Choose **Yes** to enable toast notifications for your PWA.</span><span class="sxs-lookup"><span data-stu-id="efbc5-256">Choose **Yes** to enable toast notifications for your PWA.</span></span>  
    
1.  <span data-ttu-id="efbc5-257">From the Service Worker Overview pane, try choosing the  **Push** button.</span><span class="sxs-lookup"><span data-stu-id="efbc5-257">From the Service Worker Overview pane, try choosing the  **Push** button.</span></span>  <span data-ttu-id="efbc5-258">A toast notification with the \(hard-coded "Test push message from DevTools"\) payload should appear.</span><span class="sxs-lookup"><span data-stu-id="efbc5-258">A toast notification with the \(hard-coded "Test push message from DevTools"\) payload should appear.</span></span>  
    
    ![Push a notification from DevTools][ImageDevtoolsPush]  
    
1.  <span data-ttu-id="efbc5-260">Next try choosing the **Send Notification** button on the homepage of your PWA.</span><span class="sxs-lookup"><span data-stu-id="efbc5-260">Next try choosing the **Send Notification** button on the homepage of your PWA.</span></span>  <span data-ttu-id="efbc5-261">This time a toast with the payload from your server appears.</span><span class="sxs-lookup"><span data-stu-id="efbc5-261">This time a toast with the payload from your server appears.</span></span>  
    
    ![Push a notification from PWA server][ImagePwaPush]  
    
    <span data-ttu-id="efbc5-263">If you do not click \(or activate\) a toast notification, it is dismissed after several seconds and queue up in your Windows Action Center.</span><span class="sxs-lookup"><span data-stu-id="efbc5-263">If you do not click \(or activate\) a toast notification, it is dismissed after several seconds and queue up in your Windows Action Center.</span></span>  
    
    ![Notifications in Windows Action Center][ImageWindowsActionCenter]  
    
    <span data-ttu-id="efbc5-265">You have the basics of PWA push notifications.</span><span class="sxs-lookup"><span data-stu-id="efbc5-265">You have the basics of PWA push notifications.</span></span>  <span data-ttu-id="efbc5-266">In a real app, the next steps are implemented in a way to manage and store push subscriptions and to properly [encrypt][NPMWebPushEncrypt] payload data being sent across the wire.</span><span class="sxs-lookup"><span data-stu-id="efbc5-266">In a real app, the next steps are implemented in a way to manage and store push subscriptions and to properly [encrypt][NPMWebPushEncrypt] payload data being sent across the wire.</span></span>  
    
## <span data-ttu-id="efbc5-267">Going further</span><span class="sxs-lookup"><span data-stu-id="efbc5-267">Going further</span></span>  

<span data-ttu-id="efbc5-268">This guide demonstrated the basic anatomy of a Progressive Web App and Microsoft PWA development tools including Visual Studio, PWA Builder, and Edge DevTools.</span><span class="sxs-lookup"><span data-stu-id="efbc5-268">This guide demonstrated the basic anatomy of a Progressive Web App and Microsoft PWA development tools including Visual Studio, PWA Builder, and Edge DevTools.</span></span>  

<span data-ttu-id="efbc5-269">Of course, there is a lot more that goes into [making a great PWA][PwaEdgehtmlIndexRequirements] beyond what you read here, including responsive design, deep-linking, [cross-browser testing][BrowserStackTestEdgeBrowser] and other [best practices][Webhint] \(not to mention your app functionality!\), but hopefully this guide gave you a solid introduction of PWA basics and some ideas on getting started.</span><span class="sxs-lookup"><span data-stu-id="efbc5-269">Of course, there is a lot more that goes into [making a great PWA][PwaEdgehtmlIndexRequirements] beyond what you read here, including responsive design, deep-linking, [cross-browser testing][BrowserStackTestEdgeBrowser] and other [best practices][Webhint] \(not to mention your app functionality!\), but hopefully this guide gave you a solid introduction of PWA basics and some ideas on getting started.</span></span>  <span data-ttu-id="efbc5-270">If you have further questions on PWA development with Windows or with Visual Studio, please leave a comment!</span><span class="sxs-lookup"><span data-stu-id="efbc5-270">If you have further questions on PWA development with Windows or with Visual Studio, please leave a comment!</span></span>  

<span data-ttu-id="efbc5-271">Review the other PWA guides to learn how to increase customer engagement and provide a more seamless, OS-integrated app experience.</span><span class="sxs-lookup"><span data-stu-id="efbc5-271">Review the other PWA guides to learn how to increase customer engagement and provide a more seamless, OS-integrated app experience.</span></span>  

*   <span data-ttu-id="efbc5-272">[Windows tailoring][PwaEdgehtmlWindowsFeatures].</span><span class="sxs-lookup"><span data-stu-id="efbc5-272">[Windows tailoring][PwaEdgehtmlWindowsFeatures].</span></span> <span data-ttu-id="efbc5-273">Using simple feature detection, you may progressively enhance your PWA for Windows 10 customers through native Windows Runtime \(WinRT\) APIs, such as those for customizing Windows **Start** menu tile notifications and taskbar jumplists, and \(upon permission\) working with user resources, such as photos, music, and calendar.</span><span class="sxs-lookup"><span data-stu-id="efbc5-273">Using simple feature detection, you may progressively enhance your PWA for Windows 10 customers through native Windows Runtime \(WinRT\) APIs, such as those for customizing Windows **Start** menu tile notifications and taskbar jumplists, and \(upon permission\) working with user resources, such as photos, music, and calendar.</span></span>  
*   <span data-ttu-id="efbc5-274">[PWAs in the Microsoft Store][PwaEdgehtmlMicrosoftStore].</span><span class="sxs-lookup"><span data-stu-id="efbc5-274">[PWAs in the Microsoft Store][PwaEdgehtmlMicrosoftStore].</span></span>  <span data-ttu-id="efbc5-275">Learn more about the benefits of app store distribution and how to submit your PWA.</span><span class="sxs-lookup"><span data-stu-id="efbc5-275">Learn more about the benefits of app store distribution and how to submit your PWA.</span></span>  

## <span data-ttu-id="efbc5-276">See also</span><span class="sxs-lookup"><span data-stu-id="efbc5-276">See also</span></span>  

*   <span data-ttu-id="efbc5-277">[Progressive Web Apps on MDN web docs][MDNProgressiveWebApps] - Excellent guide on Progressive Web Apps.</span><span class="sxs-lookup"><span data-stu-id="efbc5-277">[Progressive Web Apps on MDN web docs][MDNProgressiveWebApps] - Excellent guide on Progressive Web Apps.</span></span>  
*   <span data-ttu-id="efbc5-278">[Progressive Web Apps on web.dev][WebDevProgressiveWebApps] - Excellent guide on Progressive Web Apps.</span><span class="sxs-lookup"><span data-stu-id="efbc5-278">[Progressive Web Apps on web.dev][WebDevProgressiveWebApps] - Excellent guide on Progressive Web Apps.</span></span>  
*   <span data-ttu-id="efbc5-279">[Progressive Web Apps rocks][ProgressiveWebApps] - Showcases real-world examples of PWAs.</span><span class="sxs-lookup"><span data-stu-id="efbc5-279">[Progressive Web Apps rocks][ProgressiveWebApps] - Showcases real-world examples of PWAs.</span></span>  
*   <span data-ttu-id="efbc5-280">[Hacker News readers as Progressive Web Apps][HackerNewsProgressiveWebApps] - Compares different frameworks and performance patterns for implementing a sample \(Hacker News reader\) PWA.</span><span class="sxs-lookup"><span data-stu-id="efbc5-280">[Hacker News readers as Progressive Web Apps][HackerNewsProgressiveWebApps] - Compares different frameworks and performance patterns for implementing a sample \(Hacker News reader\) PWA.</span></span>  

<!-- image links -->  

[ImageDevtoolsPush]: ./media/devtools-push.png  
[ImageDevtoolsSwCache]: ./media/devtools-cache.png  
[ImageDevtoolsSwOverview]: ./media/devtools-sw-overview.png  
[ImageNotificationPermission]: ./media/notification-permission.png  
[ImageOfflineHtml]: ./media/offline-html.png  
[ImagePwa]: ./media/pwa.png  
[ImagePwaPush]: ./media/pwa-push.png  
[ImageVsNodejsExpressIcon]: ./media/vs-nodejs-express-icon.png  
[ImageVsNodejsExpressIndex]: ./media/vs-nodejs-express-index.png  
[ImageVsNodejsExpressManifest]: ./media/vs-nodejs-express-manifest.png  
[ImageVsNodejsExpressPublic]: ./media/vs-nodejs-express-public.png  
[ImageVsNodejsExpressTemplate]: ./media/vs-nodejs-express-template.png  
[ImageWindowsActionCenter]: ./media/windows-action-center.png  

<!-- links -->  

[PwaEdgehtmlIndexRequirements]: ../progressive-web-apps-edgehtml/index.md#requirements "Requirements - Progressive Web Apps \(EdgeHTML\) on Windows"  
[PwaEdgehtmlMicrosoftStore]: ../progressive-web-apps-edgehtml/microsoft-store.md "Progressive Web Apps \(EdgeHTML\)in the Microsoft Store"  
[PwaEdgehtmlWindowsFeatures]: ../progressive-web-apps-edgehtml/windows-features.md "Tailor your PWA \(EdgeHTML\) for Windows"  

[LegalWindowsAgrementsMicrosoftStorePolicies]: /legal/windows/agreements/store-policies "Microsoft Store Policies | Microsoft Docs"  

[VisualStudioNodeJsTutorial]: /visualstudio/nodejs/tutorial-nodejs "Tutorial: Create a Node.js and Express app in Visual Studio | Microsoft Docs"  
[VisualStudioNodejsTutorialPublishAzureAppService]: /visualstudio/nodejs/tutorial-nodejs#optional-publish-to-azure-app-service "Publish to Azure App Service - Create a Node.js and Express app in Visual Studio | Microsoft Docs"  

[WindowsUwpGetStartedWhat]: /windows/uwp/get-started/whats-a-uwp "What's a Universal Windows Platform \(UWP\) app?  | Microsoft Docs"  

[AzureCreateFreeAccount]: https://azure.microsoft.com/free "Create Azure free account | Microsoft Azure"  
[AzureWebApps]: https://azure.microsoft.com/services/app-service/web "Web Apps | Microsoft Azure"  

<!--[DeveloperEdgeToolsRemote]: https://developer.microsoft.com/microsoft-edge/tools/remote/ "page not found"  -->  

[WindowsBlogsPwaEdge]: https://blogs.windows.com/msedgedev/2018/02/06/welcoming-progressive-web-apps-edge-windows-10/#4UOdrDJj3124VIkc.97 "Welcoming Progressive Web Apps to Microsoft Edge and Windows 10 | Windows Blogs"  
[WindowsBlogsWebNotificationsEdge]: https://blogs.windows.com/msedgedev/2016/05/16/web-notifications-microsoft-edge#UAbvU2ymUlHO8EUV.97 "Web Notifications in Microsoft Edge | Windows Blogs"  

[VisualStudioDownloads]: https://www.visualstudio.com/downloads "Downloads | Visual Studio"  
[VisualStudioFree]: https://visualstudio.microsoft.com/free-developer-offers "Free Developer Software & Services | Visual Studio"  
[VisualStudioPreview]: https://www.visualstudio.com/vs/preview "Visual Studio Preview"  

[BrowserStackTestEdgeBrowser]: https://www.browserstack.com/test-on-microsoft-edge-browser "Free Microsoft Edge Browser Testing on Windows 10 | BrowserStack"  

[HackerNewsProgressiveWebApps]: https://hnpwa.com "Hacker News readers as Progressive Web Apps"  

[MDNCache]: https://developer.mozilla.org/docs/Web/API/Cache "Cache | MDN"  
[MDNDedicatedWorkerGlobalScopePostMessage]: https://developer.mozilla.org/docs/Web/API/DedicatedWorkerGlobalScope/postMessage "DedicatedWorkerGlobalScope.postMessage\(\) | MDN"  
[MDNNotificationsApi]: https://developer.mozilla.org/docs/Web/API/Notifications_API "Notifications API | MDN"  
[MDNProgressiveWebApps]: https://developer.mozilla.org/Apps/Progressive "Progressive web apps \(PWAs) | MDN"  
[MDNPushApi]: https://developer.mozilla.org/docs/Web/API/Push_API "Push API | MDN"  
[MDNPushManager]: https://developer.mozilla.org/docs/Web/API/PushManager "PushManager | MDN"  
[MDNServiceWorkerApi]: https://developer.mozilla.org/docs/Web/API/Service_Worker_API "Service Worker API | MDN"  
[MDNSyncManager]: https://developer.mozilla.org/docs/Web/API/SyncManager "SyncManager | MDN"  
[MDNUsingServiceWorkers]: https://developer.mozilla.org/docs/Web/API/Service_Worker_API/Using_Service_Workers "Using Service Workers | MDN"  
[MDNWebAppManifest]: https://developer.mozilla.org/docs/Web/Manifest "Web App Manifest | MDN"  
[MDNWorkerPrototypePostMessage]: https://developer.mozilla.org/docs/Web/API/Worker/postMessage "Worker.prototype.postMessage\(\) | MDN"  

[MozillaServicesSendingVapidWebPushNotificationsPush]: https://blog.mozilla.org/services/2016/08/23/sending-vapid-identified-webpush-notifications-via-mozillas-push-service "Sending VAPID identified WebPush Notifications via Mozilla's Push Service | Mozilla Services"  

[NPMWebPush]: https://www.npmjs.com/package/web-push "web-push | npm"  
[NPMWebPushEncrypt]: https://www.npmjs.com/package/web-push#encryptuserpublickey-userauth-payload-contentencoding "encrypt(userPublicKey, userAuth, payload, contentEncoding) - web-push | NPM"  
[NPMWebPushUsage]: https://www.npmjs.com/package/web-push#usage "Usage - web-push | NPM"  

[ProgressiveWebApps]: https://pwa.rocks "Progressive Web Apps"  

[PugAttributes]: https://pugjs.org/language/attributes.html "Attributes | Pug"  

[PwaBuilder]: https://www.pwabuilder.com "PWA Builder"  
[PwaBuilderAppImageGenerator]: https://www.pwabuilder.com/imageGenerator "App Image Generator"  
[PwaBuilderServiceWorker]: https://www.pwabuilder.com/serviceworker "Service Worker | PWA Builder"  

[ServiceWorkerCookbook]: https://serviceworke.rs "ServiceWorker Cookbook"  
[ServiceWorkerCookbookPushRichDemo]: https://serviceworke.rs/push-rich_demo.html "Push Rich Demo | ServiceWorker Cookbook"  

[W3cWebAppManifest]: https://www.w3.org/TR/appmanifest "Web App Manifest | W3C"  

[Webhint]: https://sonarwhal.com "webhint, the hinting engine for web best practices" 
 
[MDNWebWorkers]: https://developer.mozilla.org/docs/Web/API/Web_Workers_API/Using_web_workers "Using Web Workers" 

[WebDevProgressiveWebApps]: https://developers.google.com/web/progressive-web-apps "Progressive Web Apps | web.dev"  

[WikiHttps]: https://en.wikipedia.org/wiki/HTTPS "HTTPS | Wikipedia"  
[WikiProgressiveEnhancement]: https://en.wikipedia.org/wiki/Progressive_enhancement "Progressive enhancement | Wikipedia"  
