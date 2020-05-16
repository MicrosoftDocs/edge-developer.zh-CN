---
title: 使用服务工作人员管理网络请求和推送通知
description: 服务工作人员是 Web 工作人员，可帮助提高性能、响应各种网络条件以及增强与 Web 应用程序的连接。
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/15/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: pwa
keywords: 渐进式 web 应用、PWA、Edge、JavaScript、Windows、UWP、Microsoft Store
ms.openlocfilehash: 9bf573b668ade351716b69965f653e05857c32ec
ms.sourcegitcommit: d9cc829deb709b0866f6b43a5f4733682ddae5ca
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/16/2020
ms.locfileid: "10659298"
---
# <span data-ttu-id="91eba-104">使用服务工作人员管理网络请求和推送通知</span><span class="sxs-lookup"><span data-stu-id="91eba-104">Use Service Workers to manage network requests and push notifications</span></span>

<span data-ttu-id="91eba-105">服务工作人员是一种特殊类型的 Web 工作人员，它具有使用 API 截获、修改和响应所有网络请求的功能 `Fetch` 。</span><span class="sxs-lookup"><span data-stu-id="91eba-105">Service Workers are a special type of Web Worker with the ability to intercept, modify, and respond to all network requests using the `Fetch` API.</span></span>  <span data-ttu-id="91eba-106">服务工作人员可以访问 `Cache` API 和异步客户端数据存储（如 `IndexedDB` ）以存储资源。</span><span class="sxs-lookup"><span data-stu-id="91eba-106">Service Workers can access the `Cache` API, and asynchronous client-side data stores, such as `IndexedDB`, to store resources.</span></span>  

## <span data-ttu-id="91eba-107">注册服务工作人员</span><span class="sxs-lookup"><span data-stu-id="91eba-107">Registering a Service Worker</span></span>  

<span data-ttu-id="91eba-108">与其他 Web 工作人员类似，服务工作者必须存在于单独的文件中。</span><span class="sxs-lookup"><span data-stu-id="91eba-108">Similar to other Web Workers, Service Workers must exist in a separate file.</span></span> <span data-ttu-id="91eba-109">注册服务工作人员时引用此文件，如以下代码片段所示。</span><span class="sxs-lookup"><span data-stu-id="91eba-109">You reference this file when registering the Service Worker, as shown in the following code snippet.</span></span>  

```javascript
if ( "serviceWorker" in navigator ) {
    navigator.serviceWorker.register( "/serviceworker.min.js" );
}
```  

<span data-ttu-id="91eba-110">新式浏览器提供不同级别的服务工作人员支持。</span><span class="sxs-lookup"><span data-stu-id="91eba-110">Modern browsers provide different levels of support for Service Workers.</span></span> <span data-ttu-id="91eba-111">因此，在 `serviceWorker` 运行任何与服务工作人员相关的代码之前，最好先测试对象是否存在。</span><span class="sxs-lookup"><span data-stu-id="91eba-111">As such, it is a good practice to test for the existence of the `serviceWorker` object before running any Service Worker-related code.</span></span> <span data-ttu-id="91eba-112">在上面的代码段中，使用位于网站根目录的文件注册服务工作人员 `serviceworker.min.js` 。</span><span class="sxs-lookup"><span data-stu-id="91eba-112">In the above code snippet, a Service Worker is registered using the `serviceworker.min.js` file located at the root of the site.</span></span> <span data-ttu-id="91eba-113">确保定义你的服务工作人员的 JavaScript 文件存在于你希望它管理的最高级别目录中 \ （这称为服务工作人员的范围）。</span><span class="sxs-lookup"><span data-stu-id="91eba-113">Ensure that the JavaScript file that defines your Service Worker exists in the highest-level directory that you want it to manage \(which is referred to as the scope of the Service Worker\).</span></span>  <span data-ttu-id="91eba-114">在上面的代码段中，文件存储在根中，并且服务工作人员管理域中的所有页面。</span><span class="sxs-lookup"><span data-stu-id="91eba-114">In the above code snippet, the file is stored in the root, and the Service Worker manages all pages in the domain.</span></span> <span data-ttu-id="91eba-115">如果服务工作人员文件存储在目录中 `js` ，服务工作人员的范围将是 `js` 目录和任何子目录。</span><span class="sxs-lookup"><span data-stu-id="91eba-115">If the Service Worker file was stored in a `js` directory, the scope of the Service Worker would be the `js` directory and any subdirectories.</span></span>  <span data-ttu-id="91eba-116">最佳做法是将服务工作人员文件放在网站的根目录中，除非您需要缩小服务工作人员的范围。</span><span class="sxs-lookup"><span data-stu-id="91eba-116">As a best practice, place the Service Worker file in the root of your site, unless you need to reduce the scope of your Service Worker.</span></span>  

## <span data-ttu-id="91eba-117">服务工作人员生命周期</span><span class="sxs-lookup"><span data-stu-id="91eba-117">The Service Worker lifecycle</span></span>  

<span data-ttu-id="91eba-118">服务工作者的生命周期由多个步骤组成，每个步骤都触发一个事件。</span><span class="sxs-lookup"><span data-stu-id="91eba-118">The lifecycle of a Service Worker consists of multiple steps, with each step triggering an event.</span></span> <span data-ttu-id="91eba-119">你可以将侦听器添加到这些事件，以运行代码以执行操作。</span><span class="sxs-lookup"><span data-stu-id="91eba-119">You can add listeners to these events to run code to perform an action.</span></span> <span data-ttu-id="91eba-120">以下列表显示了服务工作人员的生命周期和相关事件的高级别视图。</span><span class="sxs-lookup"><span data-stu-id="91eba-120">The following list presents a high-level view of the lifecycle and related events of service workers.</span></span> 

1. <span data-ttu-id="91eba-121">注册服务工作人员。</span><span class="sxs-lookup"><span data-stu-id="91eba-121">Register the Service Worker.</span></span>  
1.  <span data-ttu-id="91eba-122">浏览器下载 JavaScript 文件、安装服务工作人员并触发 `install` 事件。</span><span class="sxs-lookup"><span data-stu-id="91eba-122">The browser downloads the JavaScript file, installs the Service Worker, and triggers the `install` event.</span></span> <span data-ttu-id="91eba-123">你可以使用该 `install` 事件从你的网站中预缓存任何重要和长生存期的文件，例如 CSS 文件、JavaScript 文件、徽标图像、脱机页面等。</span><span class="sxs-lookup"><span data-stu-id="91eba-123">You can use the `install` event to pre-cache any important and long-lived files, such as CSS files, JavaScript files, logo images, offline pages, and so on from your website.</span></span>  
    
    ```javascript
    self.addEventListener( "install", function( event ){
        console.log( "WORKER: install event in progress." );
    });
    ```  
    
1.  <span data-ttu-id="91eba-124">激活服务工作人员，它会触发 `activate` 事件。</span><span class="sxs-lookup"><span data-stu-id="91eba-124">The Service Worker is activated, which triggers the `activate` event.</span></span>  <span data-ttu-id="91eba-125">使用此事件清理过时的缓存。</span><span class="sxs-lookup"><span data-stu-id="91eba-125">Use this event to clean up outdated caches.</span></span>  
    
    ```javascript
    self.addEventListener( "activate", event => {
        console.log('WORKER: activate event in progress.');
    });
    ```  
    
1.  <span data-ttu-id="91eba-126">当刷新页面或用户导航到网站上的新页面时，服务工作者准备好运行。</span><span class="sxs-lookup"><span data-stu-id="91eba-126">The Service Worker is ready to run when the page is refreshed or when the user navigates to a new page on the site.</span></span> <span data-ttu-id="91eba-127">如果要在不等待的情况下运行服务工作人员，请在 `self.skipWaiting()` 事件期间使用该方法 `install` 。</span><span class="sxs-lookup"><span data-stu-id="91eba-127">If you want to run the Service Worker without waiting, use the `self.skipWaiting()` method during the `install` event.</span></span>  
    
    ```javascript
    self.addEventListener( "install", event => {
        self.skipWaiting();
        // …
    });
    ```
    
1.  <span data-ttu-id="91eba-128">服务工作者现在正在运行。</span><span class="sxs-lookup"><span data-stu-id="91eba-128">The Service Worker is now running.</span></span>     
    
## <span data-ttu-id="91eba-129">使用提取服务工作人员</span><span class="sxs-lookup"><span data-stu-id="91eba-129">Using fetch in Service Workers</span></span>  

<span data-ttu-id="91eba-130">您在服务工作人员中使用的主要事件是 `fetch` 事件。</span><span class="sxs-lookup"><span data-stu-id="91eba-130">The main event that you use in a Service Worker is the `fetch` event.</span></span>  <span data-ttu-id="91eba-131">`fetch`每当浏览器尝试访问服务工作人员范围内的内容时，该事件就会运行。</span><span class="sxs-lookup"><span data-stu-id="91eba-131">The `fetch` event runs every time the browser attempts to access content within the scope of the Service Worker.</span></span> <span data-ttu-id="91eba-132">以下代码片段显示了如何将侦听器添加到 fetch 事件。</span><span class="sxs-lookup"><span data-stu-id="91eba-132">The following code snippet shows how to add a listener to the fetch event.</span></span>  

```javascript
self.addEventListener( "fetch", event => {
  console.log('WORKER: Fetching', event.request);
});
```  

<span data-ttu-id="91eba-133">在该 `fetch` 处理程序中，你可以控制请求是否转到网络、从缓存中拉出，等等。</span><span class="sxs-lookup"><span data-stu-id="91eba-133">Within the `fetch` handler, you may control whether a request goes to the network, pulls from the cache, and so on.</span></span>  <span data-ttu-id="91eba-134">你的方法可能因所请求的资源类型、更新频率以及你的应用程序特有的其他业务逻辑而异。</span><span class="sxs-lookup"><span data-stu-id="91eba-134">The approach you take likely varies based upon the type of resource being requested, how frequently it is updated, and other business logic unique to your application.</span></span>  <span data-ttu-id="91eba-135">下面是您可以执行的操作的一些示例：</span><span class="sxs-lookup"><span data-stu-id="91eba-135">Here are a few examples of what you may do:</span></span>  

*   <span data-ttu-id="91eba-136">如果可用，则从缓存返回响应，否则回退以通过网络请求资源。</span><span class="sxs-lookup"><span data-stu-id="91eba-136">If available, return a response from the cache, otherwise fallback to request the resource over the network.</span></span>  
*   <span data-ttu-id="91eba-137">从网络获取资源、缓存副本并返回响应。</span><span class="sxs-lookup"><span data-stu-id="91eba-137">Fetch a resource from the network, cache a copy, and return the response.</span></span>
*   <span data-ttu-id="91eba-138">允许用户指定保存数据的首选项。</span><span class="sxs-lookup"><span data-stu-id="91eba-138">Allow user's to specify a preference to save data.</span></span> 
*   <span data-ttu-id="91eba-139">为某些图像请求提供占位符图像。</span><span class="sxs-lookup"><span data-stu-id="91eba-139">Supply a placeholder image for certain image requests.</span></span>  
*   <span data-ttu-id="91eba-140">直接在服务工作人员中生成响应。</span><span class="sxs-lookup"><span data-stu-id="91eba-140">Generate a response directly in the Service Worker.</span></span>  

## <span data-ttu-id="91eba-141">推送通知</span><span class="sxs-lookup"><span data-stu-id="91eba-141">Push Notifications</span></span>  

<span data-ttu-id="91eba-142">服务工作人员可以向用户推送通知。</span><span class="sxs-lookup"><span data-stu-id="91eba-142">Service workers can push notifications to users.</span></span> <span data-ttu-id="91eba-143">推送通知有助于提示用户在一段时间后重新处理你的应用程序。</span><span class="sxs-lookup"><span data-stu-id="91eba-143">Push Notifications are helpful to prompt users to re-engage with your application after some time has elapsed.</span></span> <span data-ttu-id="91eba-144">有关详细信息，请参阅[推送通知演练和演示][AzurewebsitesWebpushdemo]。</span><span class="sxs-lookup"><span data-stu-id="91eba-144">For more information, see [Push Notifications walkthrough and demo][AzurewebsitesWebpushdemo].</span></span>  

## <span data-ttu-id="91eba-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="91eba-145">See also</span></span>  

<span data-ttu-id="91eba-146">若要了解有关服务工作人员的详细信息，请参阅以下相关主题列表。</span><span class="sxs-lookup"><span data-stu-id="91eba-146">To learn more about Service Workers, see the following list of related topics.</span></span>  

*   [<span data-ttu-id="91eba-147">使 PWAs 与服务工作者脱机工作</span><span class="sxs-lookup"><span data-stu-id="91eba-147">Making PWAs work offline with Service workers</span></span>][MDNPwasMakingOfflineServiceWorkers]  
*   [<span data-ttu-id="91eba-148">如何使用通知和推送使 PWAs 重新 engageable</span><span class="sxs-lookup"><span data-stu-id="91eba-148">How to make PWAs re-engageable using Notifications and Push</span></span>][MDNPwasMakeReengageablesingNotificationsPush]  

<!-- links -->  

[AzurewebsitesWebpushdemo]: https://webpushdemo.azurewebsites.net "Web 推送通知 | Microsoft Edge 演示"  

[MDNPwasMakingOfflineServiceWorkers]: https://developer.mozilla.org/docs/Web/Progressive_web_apps/Offline_Service_workers "使 PWAs 与服务工作人员脱机工作-PWAs |MDN"  
[MDNPwasMakeReengageablesingNotificationsPush]: https://developer.mozilla.org/docs/Web/Progressive_web_apps/Re-engageable_Notifications_Push "如何使用通知和推送-PWAs 进行 PWAs engageableMDN"  
