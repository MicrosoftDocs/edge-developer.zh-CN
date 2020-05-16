---
title: 在渐进 Web 应用中脱机和网络连接支持
description: 了解如何使用支持技术为不同的网络条件创建弹性体验。
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/15/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: pwa
keywords: 渐进式 web 应用、PWA、Edge、JavaScript、Windows、UWP、Microsoft Store
ms.openlocfilehash: 58ffb8e9ae596dec4b99143a3061995a6598ce44
ms.sourcegitcommit: d9cc829deb709b0866f6b43a5f4733682ddae5ca
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/16/2020
ms.locfileid: "10659305"
---
# 在渐进 Web 应用中脱机和网络连接支持

由于 web 应用程序依赖于稳定的网络连接，因此多年来，许多公司都不愿意在基于 web 的本地软件上投入大量资金。 现在，web 平台现在提供了强大的选项，使用户可以继续工作，即使网络连接变得不稳定或完全脱机也是如此。

## 使用缓存提高 PWAs 的性能

随着[服务工作者][MDNServiceWorker]的推出，web 平台添加了 `Cache` API 以提供对托管缓存资源的访问。 此基于承诺的 API 允许开发人员存储和检索许多 web 资源，例如 HTML、CSS、JavaScript、图像、JSON 等。 通常，缓存 API 在服务工作人员的上下文中使用，但也可在对象上的主线程中使用 `window` 。

API 的一个常见用途 `Cache` 是在安装服务工作者时预缓存关键资源，如以下代码片段所示。  

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

此代码在服务辅助 `install` 生命周期事件期间运行，它会打开一个名为的缓存， `static-cache` 然后当它具有指向缓存的指针时，使用该方法将四个资源添加到其中 `addAll()` 。  在事件期间，方法通常与缓存检索结合使用 `fetch`   

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

当浏览器发出此网站的请求时，代码段在服务工作人员内运行 `fetch` 。 在该事件中，有一个条件语句，该语句在请求用于 HTML 文件时运行。 服务工作人员检查文件是否已存在于任何缓存 \ （使用 `match()` 方法 \）。 如果缓存中存在该请求，则返回缓存的结果。 如果不是，则 `fetch` 运行该资源的新功能时，将缓存该响应的副本，以便稍后返回响应。 如果 `fetch` 由于网络不可用而失败，则从缓存中返回脱机页面。

此简单介绍介绍了如何在渐进式 web 应用（PWA）中使用缓存。 每个 PWA 不同，并且可能使用不同的缓存策略。 你的代码可能看起来不同，你可能会在同一应用程序中对不同的路由使用不同的缓存策略。

## 在 PWA 中使用 IndexedDB 存储结构化数据

`IndexedDB` 是用于存储结构化数据的 API。 与 API 类似 `Cache` ，它也是异步的，这意味着你可以在主线程或 Web 工作人员（如服务工作人员）中使用它。 使用 `IndexedDB` API 在客户端或二进制数据（如加密媒体对象）上存储大量的结构化数据。 有关详细信息，请参阅[使用 IndexedDB 中的 MDN 入门][MDNIndexeddbApiUsing]。

## 了解 PWAs 的存储选项

有时，您可能需要存储少量数据，以便为用户提供更好的脱机体验。 如果是这种情况，你可能会发现 web 存储的关键值对系统的简单性是否满足你的需要。  

> [!IMPORTANT]
> Web 存储是同步过程，不能在工作线程（如服务工作线程）内使用。 繁重的使用可能会为你的应用程序带来性能问题。 


有2种类型的 Web 存储： `localStorage` 和 `sessionStorage` 。 每个文件都将作为独立于创建它的域的独立数据存储进行维护。 `sessionStorage` 仅在浏览会话期间保持（例如，浏览器处于打开状态，包括刷新和还原）。 `localStorage` 持续到数据被代码、用户或浏览器（例如，可用存储空间有限）删除。 以下代码片段显示了如何使用 `localStorage` ，它与使用方式类似 `sessionStorage` 。

```javascript
var data = {
    title: document.querySelector("[property='og:title']").getAttribute("content"),
    description: document.querySelector( "meta[name='description']" ).getAttribute("content")
};
localStorage.setItem( window.location, JSON.stringify(data) );
```  

此代码片段将获取有关当前页面的元数据并将其存储在 JavaScript 对象中。 然后，使用该方法将该值存储为 JSON `localStorage` `setItem()` ，并分配一个等于当前 URL 的键 `window.location` 。 您可以使用方法检索信息 `localStorage` `getItem()` 。 

以下代码片段显示了如何使用缓存 `localstorage` 来枚举缓存的页面并提取元数据以执行某项任务，例如构建链接列表。

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

该 `insertOfflineLink()` 方法将请求的 URL 传递到方法中 `localStorage.getItem()` 以检索任何存储的元数据。 将检查检索的数据以查看它是否存在，如果是，则可以对数据执行操作，例如生成和插入标记以将其显示。

## 在 PWA 中测试网络连接

除了存储供脱机使用的信息，还有助于了解网络连接何时可用，以便同步数据或通知用户网络状态已更改。 使用以下选项测试网络连接性。

### 导航器。联机  

该 `navigator.onLine` 属性是一个布尔值，可让你了解网络的当前状态。 如果值为 `true` ，则用户处于联机状态，否则用户处于脱机状态。

### 联机和脱机事件  

了解网络是否可用是有用的，但你可能希望在网络连接更改时执行操作。 在这种情况下，你可能需要侦听并采取措施来响应网络事件。 在 `window` `document` `document.body` 以下代码片段中显示的、和元素上提供事件。

```javascript
window.addEventListener("online",  function(){
    console.log("You are online!");
});
window.addEventListener("offline", function(){
    console.log("Oh no, you lost your network connection.");
});
```  

## 另请参阅  

若要了解有关管理脱机方案的详细信息，请参阅以下页面。  

*   [缓存][MDNCache]  
*   [IndexedDB][MDNIndexeddbApi]  
*   [服务工作人员][MDNServiceWorker]  
*   [Web 存储][MDNWebStorageApi]  
*   [导航器。联机][MDNNavigatoronline]  
*   [联机和脱机事件][MDNNavigatoronlineOfflineEvents]  
*   [PWAs 中的请求：缓存策略在时期内][AlistapartRequestIntentCachingStrategiesAgePwas]

<!-- links -->  

[MDNCache]: https://developer.mozilla.org/docs/Web/API/Cache "缓存 |MDN"  
[MDNIndexeddbApi]: https://developer.mozilla.org/docs/Web/API/IndexedDB_API "IndexedDB API |MDN"  
[MDNIndexeddbApiUsing]: https://developer.mozilla.org/docs/Web/API/IndexedDB_API/Using_IndexedDB "使用 IndexDb-IndexDB API |MDN"  
[MDNServiceWorker]: https://developer.mozilla.org/docs/Web/API/ServiceWorker "ServiceWorker |MDN"  
[MDNWebStorageApi]: https://developer.mozilla.org/docs/Web/API/Web_Storage_API "Web 存储 API |MDN"  
[MDNNavigatoronline]: https://developer.mozilla.org/docs/Web/API/NavigatorOnLine "NavigatorOnLine |MDN"  
[MDNNavigatoronlineOfflineEvents]: https://developer.mozilla.org/docs/Web/API/NavigatorOnLine/Online_and_offline_events "联机和脱机事件-NavigatorOnLine |MDN"  

[AbookapartGoingOffline]: https://abookapart.com/products/going-offline "通过 Jeremy 基斯 | 脱机一本书分开"  

[AlistapartRequestIntentCachingStrategiesAgePwas]: https://alistapart.com/article/request-with-intent-caching-strategies-in-the-age-of-pwas "通过 PWAs 的请求：在的年龄中使用缓存策略李建 Gustafson |分离列表"  
