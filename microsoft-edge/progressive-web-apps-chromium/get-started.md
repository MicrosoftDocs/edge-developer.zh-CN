---
description: 本指南概述了在 Windows 上生成渐进式 Web 应用和 Chromium (PWA) 工具。
title: '使用渐进式 Web 应用 (Chromium) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/16/2021
ms.topic: conceptual
ms.prod: microsoft-edge
keywords: 渐进式 Web 应用， PWA， Edge， Windows， PWABuilder， Web 清单， 服务工作者， 推送
ms.openlocfilehash: 3023c38790185ca6989f4a487928abc79b1d5a2c
ms.sourcegitcommit: 146072bf606b84e5145a48333abf9c6b892a12d8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/07/2021
ms.locfileid: "11480193"
---
# <a name="get-started-with-progressive-web-apps-chromium"></a>使用渐进式 Web 应用 (Chromium)   

渐进式 Web 应用 \ (PWA\) 是逐渐增强的 [Web 应用][WikiProgressiveEnhancement]。  渐进式增强功能包括类似应用的功能，如安装、脱机支持和推送通知。  还可以打包 PWA 以用于应用商店。  可能的应用商店包括 Microsoft Store、Google Play、Mac App Store 等。  Microsoft Store 是内置于 Windows 10 的商业应用商店。  

以下指南通过创建简单的 Web 应用程序并扩展为 PWA，概述了 PWA 基础知识。  已完成的项目适用于新式浏览器。  

> [!TIP]
> 可以使用 [PWABuilder][PwaBuilder] 创建新的 PWA、增强现有 PWA 或打包 PWA 以用于应用商店。  

## <a name="prerequisites"></a>必备条件  

*   使用 [Visual Studio][VisualstudioCodeMain] 代码编辑 PWA 源代码。  
*   使用 [Node.js][NodejsMain] 作为本地 Web 服务器。  
    
## <a name="create-a-basic-web-app"></a>创建基本 Web 应用  

若要创建空的 Web 应用，请按照 [Node Express App Generator][ExpressjsApplicationGenerator]中的步骤操作，并命名你的应用 `MySamplePwa` 。  

在提示符中，运行以下命令。  

```shell
npx express-generator --no-view
```  

```shell
npm install
```  

这些命令会创建一个空的 Web 应用并安装任何依赖项。  

现在，你拥有一个简单的功能性 Web 应用。  若要启动 Web 应用，请运行以下命令。  

```shell
npm start
```  

现在浏览 `http://localhost:3000` 到 以查看新的 Web 应用。  

:::image type="complex" source="./media/visual-studio-nodejs-express-index.png" alt-text="在 localhost 上运行新的 PWA" lightbox="./media/visual-studio-nodejs-express-index.png":::
   在 localhost 上运行新的 PWA  
:::image-end:::  

## <a name="get-started-building-a-pwa"></a>开始生成 PWA  

现在你已拥有一个简单的 Web 应用程序，请通过添加 PWA 的三个要求将其扩展为 PWA<!--[3 requirements for PWAs][ArchiveMicrosoftEdgeLegacyDeveloperPWAsIndexRequirements]-->[：HTTPS、Web](#step-1---use-https)[应用清单](#step-2---create-a-web-app-manifest)和服务[工作者](#step-3---add-a-service-worker)。  

### <a name="step-1---use-https"></a>步骤 1 - 使用 HTTPS  

PWA 平台的关键部分（如 [服务工作人员][MDNServiceWorkerApi]）需要使用 HTTPS。  PWA 发布后，必须将其发布到 HTTPS URL。  

出于调试目的，Microsoft Edge 还 `http://localhost` 允许使用 PWA API。  

[将 Web 应用发布为实时网站][VisualStudioNodejsTutorialPublishAzureAppService]，但请确保服务器配置为 HTTPS。  例如，你可以创建 Azure [免费帐户][AzureCreateFreeAccount]。  在 [Microsoft Azure 应用服务上][AzureWebApps] 托管网站，默认情况下它通过 HTTPS 提供。  

以下指南用于生成 `http://localhost` PWA。  

### <a name="step-2---create-a-web-app-manifest"></a>步骤 2 - 创建 Web 应用程序清单  

[Web 应用清单][MDNWebAppManifest]是一个 JSON 文件，其中包含有关应用的元数据，如名称、说明、图标等。  

若要将应用部件清单添加到 Web 应用，请运行以下操作：  

1.  In Visual Studio Code， choose **File**  >  **Open Folder** and choose the `MySamplePwa` directory you created earlier.  
1.  选择 `Ctrl` + `N` 以创建新文件，并粘贴以下代码段。  
    
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
1.  将名为 的 512x512 应用图标图像 `icon512.png` 添加到 `/MySamplePwa/public/images` 。  您可以使用示例 [图像](./media/progressive-web-app.png) 进行测试。  
1.  在Visual Studio代码"中，打开 `/public/index.html` ，在 标记内添加以下代码 `<head>` 段。  
    
    ```html
    <link rel="manifest" href="/manifest.json">
    ```   
    
### <a name="step-3---add-a-service-worker"></a>步骤 3 - 添加服务工作线程  

服务工作人员是 PBA 背后的关键技术，可实现脱机支持、高级缓存和运行后台任务等方案，以前仅限于本机应用。  

服务工作者是后台任务，可截获来自 Web 应用的网络请求。  即使 PWA 未运行，服务工作人员也尝试完成任务。  任务包括以下操作。  

*   为来自缓存的已请求资源提供服务  
*   发送推送通知  
*   运行后台提取任务  
*   标记图标  
*   和更多信息  
    
服务工作者在一个特殊的 JavaScript 文件中定义。  有关详细信息，请导航到"[使用服务工作者和服务][MDNUsingServiceWorkers][工作者 API"。][MDNServiceWorkerApi]  

若要在项目中生成服务工作器，请使用 PWA Builder 中的缓存 **第** 一个网络服务工作 [器方法][PwaBuilderServiceWorker]。  

1.  导航到 [pwabuilder.com/serviceworker，][PwaBuilderServiceWorker]选择 **"缓存第一个网络** 服务工作线程"，然后选择" **下载"** 按钮。  下载的文件包含以下文件：
    
    *   `pwabuilder-sw-register.js`  
    *   `pwabuilder-sw.js`  
        
1.  将下载的文件复制到 Web `public` 应用项目中的文件夹。  
1.  在Visual Studio代码"中 `/public/index.html` ，打开 标记内并添加以下代码 `<head>` 段。  
    
    ```html
    <script type="module" src="/pwabuilder-sw-register.js"></script>
    ```  
    
您的 Web 应用现在具有使用缓存第一策略的服务工作器。  新服务工作者首先从缓存获取资源，然后仅根据需要从网络获取资源。  缓存的资源包括图像、JavaScript、CSS 和 HTML。

使用以下步骤确认服务工作线程是否运行。  

1.  使用 导航到 Web 应用 `http://localhost:3000` 。  如果 Web 应用不可用，请运行以下命令。   
    
    ```shell
    npm start
    ```
    
1.  在 Microsoft Edge 中， `F12` 选择打开 Microsoft Edge DevTools。  选择 **"应用程序**"，然后选择" **服务** 工作人员"以查看服务工作人员。  如果未显示服务工作线程，则刷新页面。  
    
    :::image type="complex" source="./media/devtools-sw-overview.png" alt-text="Microsoft Edge DevTools 服务工作器概述" lightbox="./media/devtools-sw-overview.png":::
       Microsoft Edge DevTools 服务工作器概述  
    :::image-end:::  
    
1.  通过展开缓存存储查看服务工作 **器缓存** ，然后选择 **pwabuilder-precache**。  应显示服务工作线程缓存的所有资源。  服务工作者缓存的资源包括应用程序图标、应用程序清单、CSS 和 JavaScript 文件。  
    
    :::image type="complex" source="./media/devtools-cache.png" alt-text="Microsoft Edge DevTools 中的服务工作器缓存" lightbox="./media/devtools-cache.png":::
       Service Worker cache in Microsoft Edge DevTools \ (F12\)   
    :::image-end:::  
    
1.  尝试将 PWA 作为脱机应用。  在 Microsoft Edge DevTools \ (\) 中，选择"网络"，然后将 `F12` **"联机**状态"更改为"**脱机"。** ****  
    
    :::image type="complex" source="./media/devtools-offline.png" alt-text="在 Microsoft Edge DevTools 中将应用设置为脱机模式" lightbox="./media/devtools-offline.png":::
       在 Microsoft Edge DevTools 中将应用设置为脱机模式  
    :::image-end:::  
    
1.  刷新你的应用，它应显示用于从缓存提供应用资源的脱机机制。  
    
    :::image type="complex" source="./media/visual-studio-nodejs-express-index.png" alt-text="脱机运行的 PWA" lightbox="./media/visual-studio-nodejs-express-index.png":::
       脱机运行的 PWA  
    :::image-end:::  
    
## <a name="add-push-notifications-to-your-pwa"></a>将推送通知添加到 PWA  

通过完成以下任务，可以创建支持推送通知的 PWA。  

1.  使用推送 API 订阅 [消息传递服务][MDNPushApi]  
1.  使用通知 API 从服务接收消息时显示 [Toast 消息][MDNNotificationsApi]  
    
与服务工作人员一样，推送通知 API 是基于标准的 API。  推送通知 API 跨浏览器工作，因此代码应在支持 PA 的任何地方运行。  有关将推送消息发送到服务器上不同浏览器的信息，请导航到["Web 推送"。][NPMWebPush]  

以下步骤改编自 Mozilla 提供的 Push Rich Demo in [Service Worker Cookbook，][ServiceWorkerCookbookPushRichDemo] 该演示具有大量其他有用的 Web 推送和服务工作者方法。  

### <a name="step-1---generate-vapid-keys"></a>步骤 1 - 生成 VAPID 密钥  

推送通知需要 VAPID \ (自愿应用程序服务器标识\) 密钥才能将推送通知发送到 PWA 客户端。  联机 \ (提供了多个 VAPID 密钥生成器，例如，vapidkeys.com [\) 。][VapidkeysMain]  生成后，应获取包含公钥和私钥的 JSON 对象。  保存密钥，以执行以下教程中的稍后步骤。  有关 VAPID 和 WebPush 的信息，请导航到使用 Mozilla 推送服务发送 VAPID 标识的 [WebPush 通知][MozillaServicesSendingVapidWebPushNotificationsPush]。  

### <a name="step-2---subscribe-to-push-notifications"></a>步骤 2 - 订阅推送通知  

服务工作人员在 PWA 中处理推送事件和 Toast 通知交互。  若要订阅PWA推送通知，请确保满足以下条件。  

*   你的PWA安装、激活和注册  
*   用于完成订阅任务的代码位于应用程序主 UI 线程PWA  
*   您具有网络连接  
    
在新建推送订阅之前，Microsoft Edge验证用户是否被授予PWA接收通知的权限。  如果没有，浏览器会提示用户授予权限。  如果权限被拒绝，则引发 `registration.pushManager.subscribe` 的请求将引发 `DOMException` ，必须处理。  有关权限管理 More on， navigate to [Push Notifications in Microsoft Edge][WindowsBlogsWebNotificationsEdge].  

在文件中 `pwabuilder-sw-register.js` ，附加以下代码段。  

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

有关详细信息，请导航到[PushManager 和][MDNPushManager] [Web-Push。][NPMWebPushUsage]  

### <a name="step-3---listen-for-push-notifications"></a>步骤 3 - 侦听推送通知  

在服务中创建订阅PWA，将处理程序添加到服务工作者以响应推送事件。  推送事件从服务器发送以显示 Toast 通知。  Toast 通知显示已接收邮件的数据。  若要完成以下任务，必须添加 `click` 处理程序。  

*   消除 Toast 通知  
*   打开、聚焦或打开所有打开的窗口并聚焦  
*   打开并聚焦一个新窗口，以显示PWA页  
    
在你的 `pwabuilder-sw.js` 文件中，添加以下处理程序。  

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

### <a name="step-4---try-it-out"></a>步骤 4 - 试用  

若要为用户测试推送通知PWA，请完成以下步骤。  

1.  导航到 PWA `http://localhost:3000` 。。  当服务工作者激活并尝试订阅PWA推送通知时，Microsoft Edge提示你允许PWA显示通知。  选择 **"允许"。**  
    
    :::image type="complex" source="./media/notification-permission.png" alt-text="用于启用通知的权限对话框" lightbox="./media/notification-permission.png":::
       用于启用通知的权限对话框  
    :::image-end:::  
    
1.  模拟服务器端推送通知。  在浏览器中PWA打开应用后，选择 `http://localhost:3000` `F12` 打开 DevTools。  选择 **"**  >  **应用程序服务工作者**  >  **推送**"将测试推送通知发送到PWA。  
    
    :::row:::
       :::column span="":::
          推送通知应显示在任务栏附近。  
          
          :::image type="complex" source="./media/devtools-push.png" alt-text="从 DevTools 推送通知" lightbox="./media/devtools-push.png":::
             从 DevTools 推送通知  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          如果未选择 \ (或 activate\) toast 通知，系统会在几秒钟后自动将其关闭，Windows操作中心中将其排好队列。  
          
          :::image type="complex" source="./media/windows-action-center.png" alt-text="Windows操作中心中的通知" lightbox="./media/windows-action-center.png":::
             Windows操作中心中的通知  
          :::image-end:::  
       :::column-end:::
    :::row-end:::  
    
## <a name="next-steps"></a>后续步骤  

以下步骤包括其他任务，可帮助你了解构建实际 PBA。  

*   管理和存储推送订阅  
*   [加密][NPMWebPushEncrypt] 有效负载数据  
*   响应式设计  
*   深层链接  
*   [跨浏览器测试][BrowserStackTestEdgeBrowser]  
*   实现验证和测试实践，如 [Webhint][Webhint]  
    
## <a name="see-also"></a>另请参阅  

*   [MDN Web 文档上的渐进 Web 应用][MDNProgressiveWebApps]  
*   [渐进式 Web 应用 web.dev][WebDevProgressiveWebApps]  
*   [作为渐进 Web 应用的][HackerNewsProgressiveWebApps]黑客新闻阅读器 - 比较用于实现示例 \ (黑客新闻阅读器\) PWA 的不同框架和性能模式。  
*   [为 PBA 提供一些支持][Davrous20191018MythBustingPwasNewEdgeEdition]  
*   [渐进式 Web 应用的渐进路线图][CloudfourThinksProgressiveRoadmapYourWebApp]  
*   [使用渐进 Web 应用的脱机 POS][MediumWebEdgeOfflinePostsProgressiveWebApps]  
*   [PWA问答&][AaronGustafsonNotebookPwaQa]  
*   [Web 上的百年][JoretegBlogBettingWeb]  
*   [命名渐进式 Web 应用][Fberriman20170626NamingProgressiveWebApps]  
*   [设计和生成不带框架的渐进式 Web (第 1) ][Smashingmagazine201907ProgressiveWebApplicationFrameworkPart1]  
*   [设计和构建不带框架的渐进式 Web (第 2) ][Smashingmagazine201907ProgressiveWebApplicationFrameworkPart2]  
*   [设计和构建不带框架的渐进式 Web (第 3) ][Smashingmagazine201907ProgressiveWebApplicationFrameworkPart3]  

<!-- links -->  

<!--[ArchiveMicrosoftEdgeLegacyDeveloperPWAsIndexRequirements]: /archive/microsoft-edge/legacy/developer/progressive-web-apps/index#requirements "Requirements - Progressive Web Apps \(EdgeHTML\) on Windows | Microsoft Docs"  -->  

[VisualStudioNodejsTutorialPublishAzureAppService]: /azure/javascript/tutorial-vscode-azure-app-service-node-03 "使用 Node.js 将应用部署到 Azure Visual Studio Code |Microsoft Docs"  

[AzureCreateFreeAccount]: https://azure.microsoft.com/free "创建 Azure 免费帐户|Microsoft Azure"  
[AzureWebApps]: https://azure.microsoft.com/services/app-service/web "Web 应用|Microsoft Azure"  

[WindowsBlogsWebNotificationsEdge]: https://blogs.windows.com/msedgedev/2016/05/16/web-notifications-microsoft-edge#UAbvU2ymUlHO8EUV.97 "Web 通知Microsoft Edge |Windows博客"  

[VisualstudioCodeMain]: https://code.visualstudio.com "Visual Studio 代码"  

[AaronGustafsonNotebookPwaQa]: https://www.aaron-gustafson.com/notebook/pwa-qa "PWA问答&"  

[BrowserStackTestEdgeBrowser]: https://www.browserstack.com/test-on-microsoft-edge-browser "Microsoft Edge浏览器测试Windows 10 |BrowserStack"  

[CloudfourThinksProgressiveRoadmapYourWebApp]: https://cloudfour.com/thinks/a-progressive-roadmap-for-your-progressive-web-app "渐进式 Web 应用的渐进路线图"  

[Davrous20191018MythBustingPwasNewEdgeEdition]: https://www.davrous.com/2019/10/18/myth-busting-pwas-the-new-edge-edition "百年计划 PBA – 新边缘版本"  

[ExpressjsApplicationGenerator]: https://expressjs.com/starter/generator.html "Express 应用程序生成器|Express" 

[Fberriman20170626NamingProgressiveWebApps]: https://fberriman.com/2017/06/26/naming-progressive-web-apps "命名渐进式 Web 应用"  

[HackerNewsProgressiveWebApps]: https://hnpwa.com "作为渐进式 Web 应用的黑客新闻阅读器"  

[JoretegBlogBettingWeb]: https://joreteg.com/blog/betting-on-the-web "Web 上的百年"  

[MDNDedicatedWorkerGlobalScopePostMessage]: https://developer.mozilla.org/docs/Web/API/
[MDNNotificationsApi]: https://developer.mozilla.org/docs/Web/API/Notifications_API "通知 API | MDN"  
[MDNProgressiveWebApps]: https://developer.mozilla.org/Apps/Progressive "渐进式 Web 应用 \ (PWA) |MDN"  
[MDNPushApi]: https://developer.mozilla.org/docs/Web/API/Push_API "推送 API | MDN"  
[MDNPushManager]: https://developer.mozilla.org/docs/Web/API/PushManager "PushManager |MDN"  
[MDNServiceWorkerApi]: https://developer.mozilla.org/docs/Web/API/Service_Worker_API "服务工作线程 API |MDN"  
[MDNUsingServiceWorkers]: https://developer.mozilla.org/docs/Web/API/Service_Worker_API/Using_Service_Workers "使用服务工作人员|MDN"  
[MDNWebAppManifest]: https://developer.mozilla.org/docs/Web/Manifest "Web 应用清单|MDN"  

[MediumWebEdgeOfflinePostsProgressiveWebApps]: https://medium.com/web-on-the-edge/offline-posts-with-progressive-web-apps-fc2dc4ad895 "使用渐进 Web 应用的脱机 POS"  

[MozillaServicesSendingVapidWebPushNotificationsPush]: https://blog.mozilla.org/services/2016/08/23/sending-vapid-identified-webpush-notifications-via-mozillas-push-service "通过 Mozilla 的推送服务中心发送 VAPID 标识的 WebPush |Mozilla 服务"  

[NodejsMain]: https://nodejs.org "Node.js"  

[NPMWebPush]: https://www.npmjs.com/package/web-push "Web 推送|npm"  
[NPMWebPushEncrypt]: https://www.npmjs.com/package/web-push#encryptuserpublickey-userauth-payload-contentencoding "encrypt (userPublicKey， userAuth， payload， contentEncoding) - web-push |NPM"  
[NPMWebPushUsage]: https://www.npmjs.com/package/web-push#usage "用法 - Web 推送|NPM"  

[ProgressiveWebApps]: https://pwa.rocks "渐进式 Web 应用"  

[PwaBuilder]: https://www.pwabuilder.com "PWA生成器"  
[PwaBuilderServiceWorker]: https://www.pwabuilder.com/serviceworker "服务工作|PWA生成器"  

[ServiceWorkerCookbookPushRichDemo]: https://serviceworke.rs/push-rich_demo.html "推送丰富演示|ServiceWorker Cookbook"  

[Smashingmagazine201907ProgressiveWebApplicationFrameworkPart1]: https://www.smashingmagazine.com/2019/07/progressive-web-application-pwa-framework-part-1 "设计和构建不带框架的渐进式 Web (第 1) "  

[Smashingmagazine201907ProgressiveWebApplicationFrameworkPart2]: https://www.smashingmagazine.com/2019/07/progressive-web-application-pwa-framework-part-2 "设计和生成不带框架的渐进式 Web (第 2) "  

[Smashingmagazine201907ProgressiveWebApplicationFrameworkPart3]: https://www.smashingmagazine.com/2019/07/progressive-web-application-pwa-framework-part-3 "设计和构建不带框架的渐进式 Web (第 3) "  

[VapidkeysMain]: https://vapidkeys.com "安全 VAPID 密钥生成器|VapidKeys" 

[Webhint]: https://webhint.io "webhint"  

[WebDevProgressiveWebApps]: https://developers.google.com/web/progressive-web-apps "渐进式 Web 应用|web.dev"  

[WikiProgressiveEnhancement]: https://en.wikipedia.org/wiki/Progressive_enhancement "渐进式|Wikipedia"  
