---
title: 渐进式 Web 应用中的脱机和网络连接支持
description: 了解如何使用支持技术创建复原体验，以满足不同的网络条件。
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/07/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: pwa
keywords: 渐进式 Web 应用， PWA， Edge， JavaScript， Windows， UWP， Microsoft Store
ms.openlocfilehash: 6b6031aac10161c16195c83496f8d8b5b842628e
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398075"
---
# <a name="offline-and-network-connectivity-support-in-progressive-web-apps"></a><span data-ttu-id="f5823-104">渐进式 Web 应用中的脱机和网络连接支持</span><span class="sxs-lookup"><span data-stu-id="f5823-104">Offline and network connectivity support in Progressive Web Apps</span></span>

<span data-ttu-id="f5823-105">多年来，组织不愿意通过本机软件大量投资基于 Web 的软件，因为 Web 应用程序依赖于稳定的网络连接。</span><span class="sxs-lookup"><span data-stu-id="f5823-105">For many years organizations were reluctant to invest heavily in web-based software over native software because web applications depended on stable network connections.</span></span> <span data-ttu-id="f5823-106">如今，Web 平台提供了强大的选项，使用户能够继续工作，即使网络连接变得不稳定或完全脱机也是如此。</span><span class="sxs-lookup"><span data-stu-id="f5823-106">Today, the web platform now offers robust options that enable users to continue working, even if the network connection becomes unstable or goes completely offline.</span></span>

## <a name="use-the-caching-to-improve-performance-of-pwas"></a><span data-ttu-id="f5823-107">使用缓存来提高 PWA 的性能</span><span class="sxs-lookup"><span data-stu-id="f5823-107">Use the caching to improve performance of PWAs</span></span>

<span data-ttu-id="f5823-108">随着服务 [工作者的][MDNServiceWorker]引入，Web 平台添加了 `Cache` API 以提供对托管缓存资源的访问权限。</span><span class="sxs-lookup"><span data-stu-id="f5823-108">With the introduction of [Service Workers][MDNServiceWorker], the web platform added the `Cache` API to provide access to managed cached resources.</span></span> <span data-ttu-id="f5823-109">此基于承诺的 API 允许开发人员存储和检索许多 Web 资源（HTML、CSS、JavaScript、图像、JSON 等）。</span><span class="sxs-lookup"><span data-stu-id="f5823-109">This Promise-based API allows developers to store and retrieve many web resources—HTML, CSS, JavaScript, images, JSON, and so on.</span></span> <span data-ttu-id="f5823-110">通常，缓存 API 在服务工作线程的上下文中使用，但它在对象的主线程中 `window` 也可用。</span><span class="sxs-lookup"><span data-stu-id="f5823-110">Usually, the Cache API is used within the context of a Service Worker, but it is also available in the main thread on the `window` object.</span></span>

<span data-ttu-id="f5823-111">API 的一个常见用途是在安装服务工作器时预缓存关键 `Cache` 资源，如以下代码片段所示。</span><span class="sxs-lookup"><span data-stu-id="f5823-111">One common use for the `Cache` API is to pre-cache critical resources when a Service Worker is installed, as shown in the following code snippet.</span></span>  

```javascript
self.addEventListener( "install", function( event ){
    event.waitUntil(
        caches.open( "static-cache" )
              .then(function( cache ){
            return cache.addAll([
                "/css/main.css",
                "/js/main.js",
                "/img/favicon.png",
                "/offline/"
            ]);
        })
    );
});
```  

<span data-ttu-id="f5823-112">此代码在服务工作线程生命周期事件期间运行，它将打开一个名为的缓存，然后在具有指向缓存的指针时，使用该方法向它添加 `install` `static-cache` 四 `addAll()` 个资源。</span><span class="sxs-lookup"><span data-stu-id="f5823-112">This code, which runs during the Service Worker `install` life cycle event, opens a cache named `static-cache` and then, when it has a pointer to the cache, adds four resources to it using the `addAll()` method.</span></span>  <span data-ttu-id="f5823-113">通常，此方法与事件期间缓存检索 `fetch` 结合</span><span class="sxs-lookup"><span data-stu-id="f5823-113">Often the approach is coupled with cache retrieval during a `fetch` event</span></span>   

```javascript
self.addEventListener( "fetch", event => {
    const request = event.request,
                    url = request.url;
    
    // If we are requesting an HTML page.
    if ( request.headers.get("Accept").includes("text/html") ) {
        event.respondWith(
            // Check the cache first to see if the asset exists, and if it does, return the cached asset.
            caches.match( request )
                  .then( cached_result => {
                if ( cached_result ) {
                    return cached_result;
                }
                // If the asset is not in the cache, fallback to a network request for the asset, and proceed to cache the result.
                return fetch( request )
                       .then( response => {
                    const copy = response.clone();
                    // Wait until the response we received is added to the cache.
                    event.waitUntil(
                        caches.open( "pages" )
                              .then( cache => {
                            return cache.put( request, response );
                        });
                    );
                    return response;
                })
                // If the network is unavailable to make a request, pull the offline page out of the cache.
                .catch(() => caches.match( "/offline/" ));
            })
        ); // end respondWith
    } // end if HTML
});
```  

<span data-ttu-id="f5823-114">只要浏览器对此网站提出请求，代码段就会在服务工作 `fetch` 器中运行。</span><span class="sxs-lookup"><span data-stu-id="f5823-114">The code snippet runs within the Service Worker whenever the browser makes a `fetch` request for this site.</span></span> <span data-ttu-id="f5823-115">在该事件中，存在一个条件语句，如果请求针对的是 HTML 文件，则运行该语句。</span><span class="sxs-lookup"><span data-stu-id="f5823-115">Within that event, there is a conditional statement that runs if the request is for an HTML file.</span></span> <span data-ttu-id="f5823-116">服务工作者使用方法\ (检查文件是否存在于任何缓存 `match()` \) 。</span><span class="sxs-lookup"><span data-stu-id="f5823-116">The Service Worker checks to see if the file already exists in any cache \(using the `match()` method\).</span></span> <span data-ttu-id="f5823-117">如果缓存中存在该请求，则返回缓存的结果。</span><span class="sxs-lookup"><span data-stu-id="f5823-117">If the request exists in the cache, that cached result is returned.</span></span> <span data-ttu-id="f5823-118">如果没有，将运行该资源的新功能，缓存响应副本供以后使用， `fetch` 并返回响应。</span><span class="sxs-lookup"><span data-stu-id="f5823-118">If not, a new `fetch` for that resource is run, a copy of the response is cached for later, and the response is returned.</span></span> <span data-ttu-id="f5823-119">如果 `fetch` 由于网络不可用而失败，则从缓存中返回脱机页面。</span><span class="sxs-lookup"><span data-stu-id="f5823-119">If the `fetch` fails because the network is unavailable, the offline page is returned from the cache.</span></span>

<span data-ttu-id="f5823-120">此简单介绍演示如何在渐进式 Web app (PWA) 。</span><span class="sxs-lookup"><span data-stu-id="f5823-120">This simple introduction shows how to use caching in your progressive web app (PWA).</span></span> <span data-ttu-id="f5823-121">每个 PWA 是不同的，并且可能使用不同的缓存策略。</span><span class="sxs-lookup"><span data-stu-id="f5823-121">Each PWA is different and may use different caching strategies.</span></span> <span data-ttu-id="f5823-122">代码可能看起来不同，并且你可能对同一应用程序中的不同路由使用不同的缓存策略。</span><span class="sxs-lookup"><span data-stu-id="f5823-122">Your code may look different, and you may use different caching strategies for different routes within the same application.</span></span>

## <a name="use-indexeddb-in-your-pwa-to-store-structured-data"></a><span data-ttu-id="f5823-123">在 PWA 中使用 IndexedDB 存储结构化数据</span><span class="sxs-lookup"><span data-stu-id="f5823-123">Use IndexedDB in your PWA to store structured data</span></span>

`IndexedDB` <span data-ttu-id="f5823-124">是存储结构化数据的 API。</span><span class="sxs-lookup"><span data-stu-id="f5823-124">is an API for storing structured data.</span></span> <span data-ttu-id="f5823-125">与 API 类似，它也是异步的，这意味着您可以在主线程或 Web 工作线程（如服务工作者） `Cache` 中使用它。</span><span class="sxs-lookup"><span data-stu-id="f5823-125">Similar to the `Cache` API, it is also asynchronous, which means you may use it in the main thread or with Web Workers such as Service Workers.</span></span> <span data-ttu-id="f5823-126">使用 API 在客户端或二进制数据（如加密媒体对象）上存储 `IndexedDB` 大量结构化数据。</span><span class="sxs-lookup"><span data-stu-id="f5823-126">Use the `IndexedDB` API for storing a significant amount of structured data on the client, or binary data, such as encrypted media objects.</span></span> <span data-ttu-id="f5823-127">有关详细信息，请导航到[使用 IndexedDB 的 MDN 开始。][MDNIndexeddbApiUsing]</span><span class="sxs-lookup"><span data-stu-id="f5823-127">For more information, navigate to [MDN primer on using IndexedDB][MDNIndexeddbApiUsing].</span></span>

## <a name="understand-storage-options-for-pwas"></a><span data-ttu-id="f5823-128">了解 PWA 的存储选项</span><span class="sxs-lookup"><span data-stu-id="f5823-128">Understand storage options for PWAs</span></span>

<span data-ttu-id="f5823-129">有时，你可能需要存储少量数据，以便为用户提供更好的脱机体验。</span><span class="sxs-lookup"><span data-stu-id="f5823-129">Sometimes you may need to store small amounts of data in order to provide a better offline experience for your users.</span></span> <span data-ttu-id="f5823-130">如果是这种情况，您可能会发现 Web 存储的键值对系统的简单性满足您的需求。</span><span class="sxs-lookup"><span data-stu-id="f5823-130">If that is the case, you may find the simplicity of the key-value pair system of web storage meets your needs.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="f5823-131">Web 存储是一个同步进程，在工作线程（如服务工作者）中不可用。</span><span class="sxs-lookup"><span data-stu-id="f5823-131">Web Storage is a synchronous process and is not available for use within worker threads such as Service Workers.</span></span> <span data-ttu-id="f5823-132">大量使用可能会为应用程序造成性能问题。</span><span class="sxs-lookup"><span data-stu-id="f5823-132">Heavy usage may create performance issues for your application.</span></span> 


<span data-ttu-id="f5823-133">有两种类型的 Web 存储： `localStorage` 和 `sessionStorage` 。</span><span class="sxs-lookup"><span data-stu-id="f5823-133">There are 2 types of Web Storage: `localStorage` and `sessionStorage`.</span></span> <span data-ttu-id="f5823-134">每个数据都作为单独的数据存储进行维护，与创建它的域隔离。</span><span class="sxs-lookup"><span data-stu-id="f5823-134">Each is maintained as a separate data store isolated to the domain that created it.</span></span> `sessionStorage` <span data-ttu-id="f5823-135">仅在浏览会话期间保留 (，例如，浏览器打开时，包括刷新和还原) 。</span><span class="sxs-lookup"><span data-stu-id="f5823-135">persists only for the duration of the browsing session (for example, while the browser is open, which includes refresh and restores).</span></span> `localStorage` <span data-ttu-id="f5823-136">保留，直到代码、用户或浏览器删除数据 (例如，当可用存储空间有限时) 。</span><span class="sxs-lookup"><span data-stu-id="f5823-136">persists until the data is removed by the code, the user, or the browser (for example, when there is limited storage available).</span></span> <span data-ttu-id="f5823-137">下面的代码段演示如何使用 `localStorage` ，这类似于如何使用 `sessionStorage` 。</span><span class="sxs-lookup"><span data-stu-id="f5823-137">The following code snippet shows how to use `localStorage`, which is similar to how `sessionStorage` is used.</span></span>

```javascript
var data = {
    title: document.querySelector("[property='og:title']").getAttribute("content"),
    description: document.querySelector( "meta[name='description']" ).getAttribute("content")
};
localStorage.setItem( window.location, JSON.stringify(data) );
```  

<span data-ttu-id="f5823-138">此代码段获取当前页面的元数据，并存储在 JavaScript 对象中。</span><span class="sxs-lookup"><span data-stu-id="f5823-138">This code snippet grabs metadata about the current page and stores it in a JavaScript object.</span></span> <span data-ttu-id="f5823-139">然后，它使用该方法将该值存储为 JSON，并分配一个等于当前 `localStorage` `setItem()` URL 的 `window.location` 键。</span><span class="sxs-lookup"><span data-stu-id="f5823-139">Then it stores that value as JSON in `localStorage` using the `setItem()` method, and assigns a key equal to the current `window.location` URL.</span></span> <span data-ttu-id="f5823-140">您可以使用该方法检索 `localStorage` `getItem()` 信息。</span><span class="sxs-lookup"><span data-stu-id="f5823-140">You may retrieve the information from `localStorage` using the `getItem()` method.</span></span> 

<span data-ttu-id="f5823-141">以下代码段演示如何使用缓存来枚举缓存页面并提取元数据以执行任务，例如生成 `localstorage` 链接列表。</span><span class="sxs-lookup"><span data-stu-id="f5823-141">The following code snippet shows how to use caching with `localstorage` to enumerate cached pages and extract metadata to perform a task, such as building a list of links.</span></span>

```javascript
caches.open( "pages" )
      .then( cache => {
    cache.keys()
         .then( keys => {
        if ( keys.length )
        {
            keys.forEach( insertOfflineLink );
        }
    })
});

function insertOfflineLink( request ) {
    var data = JSON.parse( localStorage.getItem( request.url ) );
    // If data exists and this page is not an offline page, assuming that offline pages have the word offline in the URL.
    if ( data && request.url.indexOf('offline') < 0  )
    {
        // Build a link and insert it into the page.
    }
}
```  

<span data-ttu-id="f5823-142">`insertOfflineLink()`该方法将请求的 URL 传递给方法 `localStorage.getItem()` 以检索任何存储的元数据。</span><span class="sxs-lookup"><span data-stu-id="f5823-142">The `insertOfflineLink()` method passes the URL of the request into the `localStorage.getItem()` method to retrieve any stored metadata.</span></span> <span data-ttu-id="f5823-143">检查检索到的数据，以查看数据是否存在，如果数据存在，可以针对数据执行一些操作，例如生成和插入标记以显示数据。</span><span class="sxs-lookup"><span data-stu-id="f5823-143">The retrieved data is checked to see if it exists, and if it does, an action can be taken on the data, such as building and inserting the markup to display it.</span></span>

## <a name="test-for-network-connections-in-your-pwa"></a><span data-ttu-id="f5823-144">在 PWA 中测试网络连接</span><span class="sxs-lookup"><span data-stu-id="f5823-144">Test for network connections in your PWA</span></span>

<span data-ttu-id="f5823-145">除了存储信息以便脱机使用之外，了解网络连接何时可用以同步数据或通知用户网络状态已更改也很有用。</span><span class="sxs-lookup"><span data-stu-id="f5823-145">In addition to storing information for offline use, it is helpful to know when a network connection is available in order to synchronize data or inform users that the network status has changed.</span></span> <span data-ttu-id="f5823-146">使用以下选项测试网络连接。</span><span class="sxs-lookup"><span data-stu-id="f5823-146">Use the following options to test for network connectivity.</span></span>

### <a name="navigatoronline"></a><span data-ttu-id="f5823-147">navigator.onLine</span><span class="sxs-lookup"><span data-stu-id="f5823-147">navigator.onLine</span></span>  

<span data-ttu-id="f5823-148">`navigator.onLine`该属性是一个布尔值，可让你了解网络的当前状态。</span><span class="sxs-lookup"><span data-stu-id="f5823-148">The `navigator.onLine` property is a boolean that lets you know the current status of the network.</span></span> <span data-ttu-id="f5823-149">如果值为 ， `true` 则用户处于联机状态，否则用户处于脱机状态。</span><span class="sxs-lookup"><span data-stu-id="f5823-149">If the value is `true`, the user is online, otherwise the user is offline.</span></span>

### <a name="online-and-offline-events"></a><span data-ttu-id="f5823-150">联机和脱机事件</span><span class="sxs-lookup"><span data-stu-id="f5823-150">Online and Offline Events</span></span>  

<span data-ttu-id="f5823-151">了解网络是否可用非常有用，但您可能需要在网络连接发生更改时采取措施。</span><span class="sxs-lookup"><span data-stu-id="f5823-151">Knowing whether the network is available is helpful, but you may want to take action  when your network connectivity changes.</span></span> <span data-ttu-id="f5823-152">在这种情况下，您可能需要侦听并采取措施以响应网络事件。</span><span class="sxs-lookup"><span data-stu-id="f5823-152">In this situation, you may want to listen and take action in response to network events.</span></span> <span data-ttu-id="f5823-153">事件在 、 和元素上可用 `window` `document` `document.body` ，如以下代码段所示。</span><span class="sxs-lookup"><span data-stu-id="f5823-153">The events are available on the `window`, `document`, and `document.body` elements as displayed in the following code snippet.</span></span>

```javascript
window.addEventListener("online",  function(){
    console.log("You are online!");
});
window.addEventListener("offline", function(){
    console.log("Oh no, you lost your network connection.");
});
```  

## <a name="see-also"></a><span data-ttu-id="f5823-154">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f5823-154">See also</span></span>  

<span data-ttu-id="f5823-155">若要了解有关管理脱机方案的信息，请导航到以下页面。</span><span class="sxs-lookup"><span data-stu-id="f5823-155">To learn more about managing offline scenarios, navigate to the following pages.</span></span>  

*   [<span data-ttu-id="f5823-156">缓存</span><span class="sxs-lookup"><span data-stu-id="f5823-156">Cache</span></span>][MDNCache]  
*   [<span data-ttu-id="f5823-157">IndexedDB</span><span class="sxs-lookup"><span data-stu-id="f5823-157">IndexedDB</span></span>][MDNIndexeddbApi]  
*   [<span data-ttu-id="f5823-158">服务工作线程</span><span class="sxs-lookup"><span data-stu-id="f5823-158">Service Worker</span></span>][MDNServiceWorker]  
*   [<span data-ttu-id="f5823-159">Web 存储</span><span class="sxs-lookup"><span data-stu-id="f5823-159">Web Storage</span></span>][MDNWebStorageApi]  
*   [<span data-ttu-id="f5823-160">navigator.onLine</span><span class="sxs-lookup"><span data-stu-id="f5823-160">navigator.onLine</span></span>][MDNNavigatoronline]  
*   [<span data-ttu-id="f5823-161">联机和脱机事件</span><span class="sxs-lookup"><span data-stu-id="f5823-161">Online and Offline Events</span></span>][MDNNavigatoronlineOfflineEvents]  
*   [<span data-ttu-id="f5823-162">具有意图的请求：在 PWA 时代缓存策略</span><span class="sxs-lookup"><span data-stu-id="f5823-162">Request with Intent: Caching Strategies in the Age of PWAs</span></span>][AlistapartRequestIntentCachingStrategiesAgePwas]
    
<!-- links -->  

[MDNCache]: https://developer.mozilla.org/docs/Web/API/Cache "缓存|MDN"  
[MDNIndexeddbApi]: https://developer.mozilla.org/docs/Web/API/IndexedDB_API "IndexedDB API |MDN"  
[MDNIndexeddbApiUsing]: https://developer.mozilla.org/docs/Web/API/IndexedDB_API/Using_IndexedDB "使用 IndexDb - IndexDB API |MDN"  
[MDNServiceWorker]: https://developer.mozilla.org/docs/Web/API/ServiceWorker "ServiceWorker |MDN"  
[MDNWebStorageApi]: https://developer.mozilla.org/docs/Web/API/Web_Storage_API "Web 存储 API |MDN"  
[MDNNavigatoronline]: https://developer.mozilla.org/docs/Web/API/NavigatorOnLine "NavigatorOnLine |MDN"  
[MDNNavigatoronlineOfflineEvents]: https://developer.mozilla.org/docs/Web/API/NavigatorOnLine/Online_and_offline_events "联机和脱机事件 - NavigatorOnLine |MDN"  

[AbookapartGoingOffline]: https://abookapart.com/products/going-offline "由 Keith |一本书分开"  

[AlistapartRequestIntentCachingStrategiesAgePwas]: https://alistapart.com/article/request-with-intent-caching-strategies-in-the-age-of-pwas "具有意图的请求：Aaron Gustafson |A List Apart"  
