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
# 使用服务工作人员管理网络请求和推送通知

服务工作人员是一种特殊类型的 Web 工作人员，它具有使用 API 截获、修改和响应所有网络请求的功能 `Fetch` 。  服务工作人员可以访问 `Cache` API 和异步客户端数据存储（如 `IndexedDB` ）以存储资源。  

## 注册服务工作人员  

与其他 Web 工作人员类似，服务工作者必须存在于单独的文件中。 注册服务工作人员时引用此文件，如以下代码片段所示。  

```javascript
if ( "serviceWorker" in navigator ) {
    navigator.serviceWorker.register( "/serviceworker.min.js" );
}
```  

新式浏览器提供不同级别的服务工作人员支持。 因此，在 `serviceWorker` 运行任何与服务工作人员相关的代码之前，最好先测试对象是否存在。 在上面的代码段中，使用位于网站根目录的文件注册服务工作人员 `serviceworker.min.js` 。 确保定义你的服务工作人员的 JavaScript 文件存在于你希望它管理的最高级别目录中 \ （这称为服务工作人员的范围）。  在上面的代码段中，文件存储在根中，并且服务工作人员管理域中的所有页面。 如果服务工作人员文件存储在目录中 `js` ，服务工作人员的范围将是 `js` 目录和任何子目录。  最佳做法是将服务工作人员文件放在网站的根目录中，除非您需要缩小服务工作人员的范围。  

## 服务工作人员生命周期  

服务工作者的生命周期由多个步骤组成，每个步骤都触发一个事件。 你可以将侦听器添加到这些事件，以运行代码以执行操作。 以下列表显示了服务工作人员的生命周期和相关事件的高级别视图。 

1. 注册服务工作人员。  
1.  浏览器下载 JavaScript 文件、安装服务工作人员并触发 `install` 事件。 你可以使用该 `install` 事件从你的网站中预缓存任何重要和长生存期的文件，例如 CSS 文件、JavaScript 文件、徽标图像、脱机页面等。  
    
    ```javascript
    self.addEventListener( "install", function( event ){
        console.log( "WORKER: install event in progress." );
    });
    ```  
    
1.  激活服务工作人员，它会触发 `activate` 事件。  使用此事件清理过时的缓存。  
    
    ```javascript
    self.addEventListener( "activate", event => {
        console.log('WORKER: activate event in progress.');
    });
    ```  
    
1.  当刷新页面或用户导航到网站上的新页面时，服务工作者准备好运行。 如果要在不等待的情况下运行服务工作人员，请在 `self.skipWaiting()` 事件期间使用该方法 `install` 。  
    
    ```javascript
    self.addEventListener( "install", event => {
        self.skipWaiting();
        // …
    });
    ```
    
1.  服务工作者现在正在运行。     
    
## 使用提取服务工作人员  

您在服务工作人员中使用的主要事件是 `fetch` 事件。  `fetch`每当浏览器尝试访问服务工作人员范围内的内容时，该事件就会运行。 以下代码片段显示了如何将侦听器添加到 fetch 事件。  

```javascript
self.addEventListener( "fetch", event => {
  console.log('WORKER: Fetching', event.request);
});
```  

在该 `fetch` 处理程序中，你可以控制请求是否转到网络、从缓存中拉出，等等。  你的方法可能因所请求的资源类型、更新频率以及你的应用程序特有的其他业务逻辑而异。  下面是您可以执行的操作的一些示例：  

*   如果可用，则从缓存返回响应，否则回退以通过网络请求资源。  
*   从网络获取资源、缓存副本并返回响应。
*   允许用户指定保存数据的首选项。 
*   为某些图像请求提供占位符图像。  
*   直接在服务工作人员中生成响应。  

## 推送通知  

服务工作人员可以向用户推送通知。 推送通知有助于提示用户在一段时间后重新处理你的应用程序。 有关详细信息，请参阅[推送通知演练和演示][AzurewebsitesWebpushdemo]。  

## 另请参阅  

若要了解有关服务工作人员的详细信息，请参阅以下相关主题列表。  

*   [使 PWAs 与服务工作者脱机工作][MDNPwasMakingOfflineServiceWorkers]  
*   [如何使用通知和推送使 PWAs 重新 engageable][MDNPwasMakeReengageablesingNotificationsPush]  

<!-- links -->  

[AzurewebsitesWebpushdemo]: https://webpushdemo.azurewebsites.net "Web 推送通知 | Microsoft Edge 演示"  

[MDNPwasMakingOfflineServiceWorkers]: https://developer.mozilla.org/docs/Web/Progressive_web_apps/Offline_Service_workers "使 PWAs 与服务工作人员脱机工作-PWAs |MDN"  
[MDNPwasMakeReengageablesingNotificationsPush]: https://developer.mozilla.org/docs/Web/Progressive_web_apps/Re-engageable_Notifications_Push "如何使用通知和推送-PWAs 进行 PWAs engageableMDN"  
