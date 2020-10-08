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
#  (Chromium 的渐进式 Web 应用入门)   

渐进式 Web 应用 \ (PWAs \ ) 是 [逐渐增强][WikiProgressiveEnhancement]的 web 应用。  渐进式增强包括类似应用的功能，例如安装、脱机支持和推送通知。  你还可以将 PWA 打包到应用商店。  可能的应用商店包括 Microsoft Store、Google Play、Mac 应用商店等。  Microsoft Store 是内置于 Windows 10 的商业应用商店。  

下面的指南通过创建一个简单的 web 应用并将其作为 PWA 进行扩展，为你提供了 PWA 基础知识的概述。  已完成的项目跨新式浏览器工作。  

> [!TIP]
> 你可以使用 [PWABuilder][PwaBuilder] 创建新的 pwa、增强现有 pwa 或将 pwa 打包到应用商店。  

## 必备条件  

*   使用 [Visual Studio 代码][VisualstudioCodeMain] 编辑 PWA 源代码。  
*   使用 [Node.js][NodejsMain] 作为本地 web 服务器。  

## 创建基本 web 应用  

若要创建空的 web 应用，请按照 [节点 Express 应用生成器][ExpressjsApplicationGenerator]中的步骤进行操作，并为你的应用命名 `MySamplePwa` 。  

在提示符下，运行以下命令。  

```shell
npx express-generator --no-view
```  

```shell
npm install
```  

这些命令将创建一个空 web 应用并安装任何依赖项。  

现在，你有了一个简单的功能 web 应用。  若要启动 web 应用，请运行以下命令。  

```shell
npm start
```  

现在，浏览以 `http://localhost:3000` 查看你的新 web 应用。  

:::image type="complex" source="./media/vs-nodejs-express-index.png" alt-text="在 localhost 上运行新的 PWA" lightbox="./media/vs-nodejs-express-index.png":::
   在 localhost 上运行新的 PWA
:::image-end:::

## 开始构建 PWA  

既然你已拥有简单的 web 应用，请通过为 PWAs 添加三个要求将其作为 PWA 扩展。<!--[3 requirements for PWAs][PwaEdgehtmlIndexRequirements]-->： [HTTPS](#step-1---use-https)、 [Web 应用清单](#step-2---create-a-web-app-manifest)和 [服务工作人员](#step-3---add-a-service-worker)。  

### 步骤 1-使用 HTTPS  

PWA 平台的关键部分（如 [服务工作者][MDNServiceWorkerApi]）需要使用 HTTPS。  当 PWA 进入活动时，必须将其发布到 HTTPS URL。  

出于调试目的，Microsoft Edge 还允许 `http://localhost` 使用 PWA api。  

将[web 应用作为实时网站发布][VisualStudioNodejsTutorialPublishAzureAppService]，但确保服务器已配置为使用 HTTPS。  例如，你可以创建一个 [Azure 免费帐户][AzureCreateFreeAccount]。  在 [Microsoft Azure 应用服务][AzureWebApps] 上托管你的网站，并且默认情况下它通过 HTTPS 提供。  

下面的指南，用于 `http://localhost` 构建 PWA。  

### 步骤 2-创建 Web 应用部件清单  

[Web 应用清单][MDNWebAppManifest]是一个 JSON 文件，其中包含有关你的应用的元数据，例如名称、说明、图标等。  

若要向 web 应用添加应用清单，请执行以下操作：  

1.  在 Visual Studio 代码中，选择 "**文件**  >  **打开文件夹**"，然后选择 `MySamplePwa` 之前创建的目录。  
1.  选择 `Ctrl` + `N` 以创建新文件，并粘贴以下代码片段。  
    
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
    
1.  将文件另存为 `/MySamplePwa/public/manifest.json` 。  
1.  添加一个名为的512x512 应用图标图像 `icon512.png` `/MySamplePwa/public/images` 。  你可以使用 [示例图像][ImagePwa] 进行测试。  
1.  在 Visual Studio 代码中，打开 `/public/index.html` 并在标记内添加以下代码段 `<head>` 。  
    
    ```html
    <link rel="manifest" href="/manifest.json">
    ```   
    
### 步骤 3-添加服务工作人员  

服务工作者是 PWAs 背后的关键技术，支持诸如离线支持、高级缓存和运行后台任务的方案，以前限制为本机应用。  

服务工作人员是从你的 web 应用截取网络请求的后台任务。  服务工作人员会尝试完成任务，即使你的 PWA 未在运行。  任务包括以下操作。  

*   从缓存中服务请求的资源  
*   发送推送通知  
*   运行后台获取任务  
*   提示标记图标  
*   及更多  

服务工作人员在特殊的 JavaScript 文件中定义。  有关详细信息，请导航到 [使用服务工作人员][MDNUsingServiceWorkers] 和 [服务工作者 API][MDNServiceWorkerApi]。  

若要在你的项目中生成服务工作人员，请使用来自[PWA 生成器][PwaBuilderServiceWorker]的**第一网络**服务工作人员食谱。  

1.  导航到 [pwabuilder.com/serviceworker][PwaBuilderServiceWorker]，选择 **缓存第一个网络** 服务工作人员，然后选择 " **下载** " 按钮。  下载的文件包含以下文件：
    
    *   `pwabuilder-sw-register.js`  
    *   `pwabuilder-sw.js`  
    
1.  将下载的文件复制到 `public` web 应用项目中的文件夹。  
    
1.  在 Visual Studio 代码中，打开 `/public/index.html` 并在标记内添加以下代码段 `<head>` 。  
    
    ```html
    <script type="module" src="/pwabuilder-sw-register.js"></script>
    ```  
    
你的 web 应用现在有一个使用缓存第一个策略的服务工作人员。  您的新服务工作者首先从缓存中获取资源，并且仅在需要时从网络中获取资源。  缓存的资源包括图像、JavaScript、CSS 和 HTML。

使用以下步骤确认你的服务工作人员运行。  

1.  使用导航到你的 web 应用 `http://localhost:3000` 。  如果你的 web 应用不可用，请运行以下命令。   
    
    ```shell
    npm start
    ```
    
1.  在 Microsoft Edge 中，选择 `F12` 以打开 Microsoft Edge DevTools。  选择 " **应用程序**"，然后选择 " **服务工作人员** " 以查看服务工作人员。  如果未显示服务工作人员，请刷新页面。  
     
    :::image type="complex" source="./media/devtools-sw-overview.png" alt-text="在 localhost 上运行新的 PWA" lightbox="./media/devtools-sw-overview.png":::
       Microsoft Edge DevTools 服务工作人员概述
    :::image-end:::
    
1.  通过展开 **缓存存储** 来查看服务工作人员缓存并选择 **pwabuilder-precache**。  应显示由服务工作人员缓存的所有资源。  由服务工作人员缓存的资源包括应用图标、应用清单、CSS 和 JavaScript 文件。  
    
    :::image type="complex" source="./media/devtools-cache.png" alt-text="在 localhost 上运行新的 PWA" lightbox="./media/devtools-cache.png":::
       Microsoft Edge DevTools 中的服务工作人员缓存 (F12) 
    :::image-end:::
    
1.  以脱机应用的形式尝试 PWA。  在 Microsoft Edge DevTools \ (`F12` \ ) 中，选择 " **网络** "，然后将 **联机** 状态更改为 " **脱机**"。  
    
    :::image type="complex" source="./media/devtools-offline.png" alt-text="在 localhost 上运行新的 PWA" lightbox="./media/devtools-offline.png":::
       在 Microsoft Edge DevTools 中将应用设置为脱机模式
    :::image-end:::
    
1.  刷新你的应用，并且它应显示用于从缓存中为应用的资源提供服务的脱机机制。  
    
    :::image type="complex" source="./media/vs-nodejs-express-index.png" alt-text="在 localhost 上运行新的 PWA" lightbox="./media/vs-nodejs-express-index.png":::
       PWA 在脱机状态下运行
    :::image-end:::
    
## 向 PWA 添加推送通知  

你可以通过完成以下任务来创建支持推送通知的 PWAs。  

1.  使用[推送 API][MDNPushApi]订阅消息服务  
1.  使用[通知 API][MDNNotificationsApi]从服务收到消息时显示 toast 消息  
    
与服务工作者一样，推送通知 Api 是基于标准的 Api。  推送通知 Api 跨浏览器运行，因此你的代码应在支持 PWAs 的任何位置工作。  有关向服务器上的不同浏览器传递推送消息的详细信息，请导航到 " [Web 推送][NPMWebPush]"。  

以下步骤适用于由 Mozilla 提供的 [服务工作人员手册][ServiceWorkerCookbookPushRichDemo] 中的 "推送丰富" 演示，这些演示具有许多其他有用的 Web 推送和服务工作人员食谱。  

### 步骤 1-生成 VAPID 键  

推送通知需要 VAPID \ (自愿应用服务器标识 \ ) 密钥才能向 PWA 客户端发送推送消息。  有多个 VAPID 密钥生成器可联机使用 (例如， [vapidkeys.com][VapidkeysMain]\ ) 。  生成后，应获取包含公钥和私钥的 JSON 对象。  保存注册表项，以便在以下教程中进行后续步骤。  有关 VAPID 和 WebPush 的信息，请 [使用 Mozilla 推送服务导航到发送 VAPID 标识的 WebPush 通知][MozillaServicesSendingVapidWebPushNotificationsPush]。  

### 步骤 2-订阅推送通知  

服务工作者处理 PWA 中的推送事件和 toast 通知交互。  若要将 PWA 订阅到服务器推送通知，请确保满足以下条件。  

*   PWA 已安装、处于活动状态且已注册  
*   完成订阅任务的代码位于 PWA 的主 UI 线程上  
*   您有网络连接  
    
在创建新推送订阅之前，Microsoft Edge 将验证用户是否已授予 PWA 接收通知的权限。  如果不是，则浏览器会提示用户提供权限。  如果权限被拒绝，则 `registration.pushManager.subscribe` 引发必须处理的请求 `DOMException` 。  有关权限管理的详细信息，请导航到 [Microsoft Edge 中的推送通知][WindowsBlogsWebNotificationsEdge]。  

在 `pwabuilder-sw-register.js` 文件中，附加以下代码片段。  

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

有关详细信息，请导航到 [PushManager][MDNPushManager] 和 [Web 推送][NPMWebPushUsage]。  

### 步骤 3-侦听推送通知  

在你的 PWA 中创建订阅后，向服务工作人员添加处理程序以响应推送事件。  将从服务器发送推送事件以显示 toast 通知。  Toast 通知显示已接收邮件的数据。  若要完成以下任务，必须添加一个 click 处理程序。  

*   关闭 toast 通知  
*   打开、焦点或打开所有打开的窗口并将焦点集中在该窗口  
*   打开并焦点一个新窗口以显示 PWA 客户端页面  
    
在 `pwabuilder-sw.js` 文件中，添加以下处理程序。  

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

### 步骤 4-试用  

若要测试 PWA 的推送通知，请完成以下步骤。  

1.  在上导航到你的 PWA `http://localhost:3000` 。  当你的服务工作者激活并尝试将你的 PWA 订阅到推送通知时，Microsoft Edge 会提示你允许 PWA 显示通知。  选择 " **允许**"。  
    
    :::image type="complex" source="./media/notification-permission.png" alt-text="在 localhost 上运行新的 PWA" lightbox="./media/notification-permission.png":::
       用于启用通知的权限对话框
    :::image-end:::
    
1.  模拟服务器端推送通知。  `http://localhost:3000`在浏览器中打开 PWA 后，选择 `F12` 以打开 DevTools。  选择 "**应用程序**  >  **服务工作人员**  >  **推送**" 以向你的 PWA 发送测试推送通知。  
    :::row:::
       :::column span="":::
          任务栏旁边应显示推送通知。  
          
          :::image type="complex" source="./media/devtools-push.png" alt-text="在 localhost 上运行新的 PWA" lightbox="./media/devtools-push.png":::
             推送来自 DevTools 的通知  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          如果不选择 \ (或激活 \ ) toast 通知，系统会在几秒钟后自动关闭它并将其排队到 Windows 操作中心。  
          
          :::image type="complex" source="./media/windows-action-center.png" alt-text="在 localhost 上运行新的 PWA" lightbox="./media/windows-action-center.png":::
             Windows 操作中心中的通知 :::image-end:::
       :::column-end:::
    :::row-end:::  
    
## 后续步骤  

以下步骤包括可帮助你理解构建现实世界 PWAs 的其他任务。  

*   管理和存储推送订阅  
*   [加密][NPMWebPushEncrypt] 有效负载数据  
*   响应式设计  
*   深度链接  
*   [跨浏览器测试][BrowserStackTestEdgeBrowser]  
*   实现验证和测试做法，如 [Webhint][Webhint]  
   
## 另请参阅  

*   [MDN web 文档上的渐进式 Web 应用][MDNProgressiveWebApps]  
*   [Web 上的渐进式 Web 应用][WebDevProgressiveWebApps]  
*   [作为渐进 Web 应用的黑客新闻阅读器][HackerNewsProgressiveWebApps] -比较不同的框架和性能模式，用于实现示例 \ (黑客新闻阅读器 \ ) PWA。  
*   [Myth Busting PWAs][Davrous20191018MythBustingPwasNewEdgeEdition]  
*   [渐进式 Web 应用的渐进式路线图][CloudfourThinksProgressiveRoadmapYourWebApp]  
*   [具有渐进的 Web 应用的脱机文章][MediumWebEdgeOfflinePostsProgressiveWebApps]  
*   [PWA 问答&][AaronGustafsonNotebookPwaQa]  
*   [在网上打赌][JoretegBlogBettingWeb]  
*   [命名渐进式 Web 应用][Fberriman20170626NamingProgressiveWebApps]  
*   [设计和构建不带框架 (第1部分) 的渐进式 Web 应用程序][Smashingmagazine201907ProgressiveWebApplicationFrameworkPart1]  
*   [设计和构建不带框架 (第2部分) 的渐进式 Web 应用程序][Smashingmagazine201907ProgressiveWebApplicationFrameworkPart2]  
*   [设计和构建不带框架 (第3部分) 的渐进式 Web 应用程序][Smashingmagazine201907ProgressiveWebApplicationFrameworkPart3]  
    
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
