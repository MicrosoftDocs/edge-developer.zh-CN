---
description: 本指南概述了在 Windows 上生成渐进式 Web 应用 (Chromium) 的 PWA 基础知识和工具。
title: '使用渐进式 Web 应用 (Chromium) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/02/2020
ms.topic: conceptual
ms.prod: microsoft-edge
keywords: 渐进式 Web 应用， PWA， Edge， Windows， PWABuilder， Web 清单， 服务工作者， 推送
ms.openlocfilehash: 7ad13f98f54c52891681d7591b21503c9d5825ff
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11231221"
---
# 使用渐进式 Web 应用 (Chromium)   

渐进式 Web 应用 \ (PWA\) 是逐渐增强的 [Web 应用][WikiProgressiveEnhancement]。  渐进式增强功能包括类似应用的功能，如安装、脱机支持和推送通知。  还可以打包 PWA 以用于应用商店。  可能的应用商店包括 Microsoft Store、Google Play、Mac App Store 等。  Microsoft Store 是内置于 Windows 10 的商业应用商店。  

下面的指南通过创建简单的 Web 应用并扩展为 PWA，概述了 PWA 基础知识。  已完成的项目适用于新式浏览器。  

> [!TIP]
> 可以使用 [PWABuilder][PwaBuilder] 创建新的 PWA、增强现有 PWA 或打包 PWA 以用于应用商店。  

## 必备条件  

*   使用 [Visual Studio代码][VisualstudioCodeMain] 编辑 PWA 源代码。  
*   将 [Node.js][NodejsMain] 用作本地 Web 服务器。  
    
## 创建基本 Web 应用  

若要创建空的 Web 应用，请按照 [Node Express 应用][ExpressjsApplicationGenerator]生成器中的步骤操作，并命名你的应用 `MySamplePwa` 。  

在提示符中，运行以下命令。  

```shell
npx express-generator --no-view
```  

```shell
npm install
```  

这些命令会创建一个空的 Web 应用并安装任何依赖项。  

现在，你已拥有一个功能简单的 Web 应用。  若要启动 Web 应用，请运行以下命令。  

```shell
npm start
```  

现在浏览 `http://localhost:3000` 以查看新的 Web 应用。  

:::image type="complex" source="./media/vs-nodejs-express-index.png" alt-text="在 localhost 上运行新 PWA" lightbox="./media/vs-nodejs-express-index.png":::
   在 localhost 上运行新 PWA
:::image-end:::

## 开始生成 PWA  

现在你已拥有一个简单的 Web 应用程序，请通过添加 PWA 的三个要求将其扩展为 PWA<!--[3 requirements for PWAs][PwaEdgehtmlIndexRequirements]-->[：HTTPS、Web](#step-1---use-https)[应用清单](#step-2---create-a-web-app-manifest)和服务[工作线程](#step-3---add-a-service-worker)。  

### 步骤 1 - 使用 HTTPS  

PWA 平台的关键部分（如 [服务][MDNServiceWorkerApi]工作者）需要使用 HTTPS。  PWA 发布后，必须将其发布到 HTTPS URL。  

出于调试目的，Microsoft Edge 还 `http://localhost` 允许使用 PWA API。  

[将 Web 应用发布为实时网站][VisualStudioNodejsTutorialPublishAzureAppService]，但请确保服务器已针对 HTTPS 进行配置。  例如，你可以创建 Azure [免费帐户][AzureCreateFreeAccount]。  在 [Microsoft Azure 应用服务上][AzureWebApps] 托管你的网站，默认情况下通过 HTTPS 提供服务。  

以下指南用于生成 `http://localhost` PWA。  

### 步骤 2 - 创建 Web 应用清单  

[Web 应用清单][MDNWebAppManifest]是一个 JSON 文件，其中包含有关应用的元数据，如名称、说明、图标等。  

若要将应用程序清单添加到 Web 应用：  

1.  在Visual Studio中，选择 **"文件**打开  >  **文件夹**"， `MySamplePwa` 然后选择之前创建的目录。  
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
1.  添加一个名为 "512x512"的应用图标 `icon512.png` 图像 `/MySamplePwa/public/images` 。  您可以使用示例 [图像][ImagePwa] 进行测试。  
1.  在Visual Studio代码中 `/public/index.html` ，打开并添加标记中的以下 `<head>` 代码段。  
    
    ```html
    <link rel="manifest" href="/manifest.json">
    ```   
    
### 步骤 3 - 添加服务工作线程  

服务工作者是 PWA 背后的关键技术，可实现脱机支持、高级缓存和运行后台任务等方案，以前仅限于本机应用。  

服务工作者是截获来自 Web 应用的网络请求的后台任务。  即使 PWA 未运行，服务工作人员也尝试完成任务。  任务包括以下操作。  

*   从缓存中提供请求的资源  
*   发送推送通知  
*   运行后台提取任务  
*   标记图标  
*   等  
    
服务工作者在特殊的 JavaScript 文件中定义。  有关详细信息，请导航到["使用服务工作者和服务][MDNUsingServiceWorkers][工作者 API"。][MDNServiceWorkerApi]  

若要在项目中生成服务工作者，请使用[PWA][PwaBuilderServiceWorker]Builder 中的**缓存第一个**网络服务工作者方法。  

1.  导航到 [pwabuilder.com/serviceworker，][PwaBuilderServiceWorker]选择 **缓存第一个网络** 服务工作线程，然后选择" **下载"** 按钮。  下载的文件包含以下文件：
    
    *   `pwabuilder-sw-register.js`  
    *   `pwabuilder-sw.js`  
        
1.  将下载的文件复制到 Web `public` 应用项目中的文件夹。  
1.  在Visual Studio代码中，在标记内打开 `/public/index.html` 并添加以下 `<head>` 代码段。  
    
    ```html
    <script type="module" src="/pwabuilder-sw-register.js"></script>
    ```  
    
您的 Web 应用现在具有使用缓存第一策略的服务工作者。  新服务工作者首先从缓存获取资源，然后仅根据需要从网络获取资源。  缓存的资源包括图像、JavaScript、CSS 和 HTML。

使用以下步骤确认服务工作线程是否运行。  

1.  使用 导航到 Web 应用 `http://localhost:3000` 。  如果 Web 应用不可用，请运行以下命令。   
    
    ```shell
    npm start
    ```
    
1.  在 Microsoft Edge 中， `F12` 选择打开 Microsoft Edge DevTools。  选择 **"应用程序**"， **然后选择"服务** 工作者"以查看服务工作者。  如果未显示服务工作线程，则刷新页面。  
    
    :::image type="complex" source="./media/devtools-sw-overview.png" alt-text="Microsoft Edge DevTools 服务工作者概述" lightbox="./media/devtools-sw-overview.png":::
       Microsoft Edge DevTools 服务工作者概述
    :::image-end:::
    
1.  通过展开缓存存储查看服务工作**** 器缓存并选择**pwabuilder-precache。**  应显示服务工作者缓存的所有资源。  服务工作者缓存的资源包括应用程序图标、应用程序清单、CSS 和 JavaScript 文件。  
    
    :::image type="complex" source="./media/devtools-cache.png" alt-text="Microsoft Edge DevTools 中的服务工作器缓存" lightbox="./media/devtools-cache.png":::
       Microsoft Edge DevTools (F12) 
    :::image-end:::
    
1.  尝试将 PWA 作为脱机应用。  在 Microsoft Edge DevTools \ (\) 中，选择"网络 `F12` "，然后将**联机**状态更改为 **"脱机"。** ****  
    
    :::image type="complex" source="./media/devtools-offline.png" alt-text="在 Microsoft Edge DevTools 中将应用设置为脱机模式" lightbox="./media/devtools-offline.png":::
       在 Microsoft Edge DevTools 中将应用设置为脱机模式
    :::image-end:::
    
1.  刷新应用，它应显示用于从缓存提供应用资源的脱机机制。  
    
    :::image type="complex" source="./media/vs-nodejs-express-index.png" alt-text="脱机运行的 PWA" lightbox="./media/vs-nodejs-express-index.png":::
       脱机运行的 PWA
    :::image-end:::
    
## 将推送通知添加到 PWA  

通过完成以下任务，可以创建支持推送通知的 PWA。  

1.  使用推送 API 订阅 [邮件服务][MDNPushApi]  
1.  使用通知 API 从服务接收消息时显示 [Toast 消息][MDNNotificationsApi]  
    
与服务工作人员一样，推送通知 API 是基于标准的 API。  推送通知 API 跨浏览器工作，因此代码应在支持 PWA 的任何地方运行。  有关将推送消息发送到服务器上不同浏览器的信息，请导航到["Web 推送"。][NPMWebPush]  

以下步骤改编自 Mozilla 提供的"服务工作者手册[][ServiceWorkerCookbookPushRichDemo]中的推送丰富演示"，Mozilla 提供了一些其他有用的 Web 推送和服务工作者方法。  

### 步骤 1 - 生成 VAPID 密钥  

推送通知需要 VAPID \ (自愿应用程序服务器标识\) 键才能向 PWA 客户端发送推送通知。  联机 \ (提供了多个 VAPID 密钥生成器，例如，vapidkeys.com [\) 。][VapidkeysMain]  生成后，应获取包含公钥和私钥的 JSON 对象。  保存密钥，以执行以下教程中的稍后步骤。  有关 VAPID 和 WebPush 的信息，请导航到使用 Mozilla 推送服务发送 VAPID 标识的 [WebPush 通知][MozillaServicesSendingVapidWebPushNotificationsPush]。  

### 步骤 2 - 订阅推送通知  

服务工作人员在 PWA 中处理推送事件和 Toast 通知交互。  若要将 PWA 订阅到服务器推送通知，请确保满足以下条件。  

*   PWA 已安装、激活和注册  
*   完成订阅任务的代码位于 PWA 的主 UI 线程上  
*   您具有网络连接  
    
在新建推送订阅之前，Microsoft Edge 会验证用户是否授予了 PWA 接收通知的权限。  如果没有，浏览器会提示用户授予权限。  如果权限被拒绝，则会引发 `registration.pushManager.subscribe` 一个 `DOMException` 必须处理的请求。  有关权限管理 More on permission management， navigate to [Push Notifications in Microsoft Edge][WindowsBlogsWebNotificationsEdge].  

在 `pwabuilder-sw-register.js` 文件中，附加以下代码段。  

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

有关详细信息，请导航到 [PushManager 和][MDNPushManager] [Web 推送][NPMWebPushUsage]。  

### 步骤 3 - 侦听推送通知  

在 PWA 中创建订阅后，向服务工作者添加处理程序以响应推送事件。  推送事件从服务器发送以显示 Toast 通知。  Toast 通知显示已接收邮件的数据。  若要完成以下任务，必须添加单击处理程序。  

*   消除 Toast 通知  
*   打开、聚焦或打开所有打开的窗口并聚焦  
*   打开并聚焦新窗口以显示 PWA 客户端页面  
    
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

### 步骤 4 - 试用  

若要测试 PWA 的推送通知，请完成以下步骤。  

1.  导航到 `http://localhost:3000` PWA。  当服务工作者激活并尝试订阅 PWA 以推送通知时，Microsoft Edge 会提示你允许 PWA 显示通知。  选择 **"允许"。**  
    
    :::image type="complex" source="./media/notification-permission.png" alt-text="用于启用通知的权限对话框" lightbox="./media/notification-permission.png":::
       用于启用通知的权限对话框
    :::image-end:::
    
1.  模拟服务器端推送通知。  在浏览器中打开 PWA 后，选择 `http://localhost:3000` `F12` 打开 DevTools。  选择 **"**  >  **应用程序服务工作**  >  **线程推送**"将测试推送通知发送到 PWA。  
    
    :::row:::
       :::column span="":::
          推送通知应显示在任务栏附近。  
          
          :::image type="complex" source="./media/devtools-push.png" alt-text="从 DevTools 推送通知" lightbox="./media/devtools-push.png":::
             从 DevTools 推送通知  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          如果未选择 \ (或 activate\) toast 通知，系统会在几秒钟后自动将其关闭，并排到 Windows 操作中心中。  
          
          :::image type="complex" source="./media/windows-action-center.png" alt-text="Windows 操作中心中的通知" lightbox="./media/windows-action-center.png":::
             Windows 操作中心中的通知 :::image-end:::
       :::column-end:::
    :::row-end:::  
    
## 后续步骤  

以下步骤包括其他任务，可帮助你了解构建实际 PBA。  

*   管理和存储推送订阅  
*   [加密][NPMWebPushEncrypt] 有效负载数据  
*   响应式设计  
*   深层链接  
*   [跨浏览器测试][BrowserStackTestEdgeBrowser]  
*   实现验证和测试实践，如 [Webhint][Webhint]  
    
## 另请参阅  

*   [MDN Web 文档上的渐进式 Web 应用][MDNProgressiveWebApps]  
*   [Web.dev 上的渐进 Web 应用][WebDevProgressiveWebApps]  
*   [作为渐进式 Web][HackerNewsProgressiveWebApps] 应用的黑客新闻阅读器 - 比较用于实现示例 \ (黑客新闻阅读器\) PWA 的不同框架和性能模式。  
*   [实现 PBA 的百万亿元][Davrous20191018MythBustingPwasNewEdgeEdition]  
*   [渐进式 Web 应用的渐进路线图][CloudfourThinksProgressiveRoadmapYourWebApp]  
*   [具有渐进式 Web 应用的脱机 POST][MediumWebEdgeOfflinePostsProgressiveWebApps]  
*   [PWA 问答&A][AaronGustafsonNotebookPwaQa]  
*   [Web 上的百元][JoretegBlogBettingWeb]  
*   [命名渐进式 Web 应用][Fberriman20170626NamingProgressiveWebApps]  
*   [设计和生成不带框架的渐进式 Web (第 1 部分) ][Smashingmagazine201907ProgressiveWebApplicationFrameworkPart1]  
*   [设计和生成不带框架的渐进式 Web (第 2 部分) ][Smashingmagazine201907ProgressiveWebApplicationFrameworkPart2]  
*   [设计和生成不带框架的渐进式 Web (第 3 部分) ][Smashingmagazine201907ProgressiveWebApplicationFrameworkPart3]  
    
<!-- image links -->  

[ImagePwa]: ./media/pwa.png  

<!-- links -->  

<!--[PwaEdgehtmlIndexRequirements]: ../progressive-web-apps/index.md#requirements "Requirements - Progressive Web Apps \(EdgeHTML\) on Windows | Microsoft Docs"  -->  

[VisualStudioNodejsTutorialPublishAzureAppService]: /azure/javascript/tutorial-vscode-azure-app-service-node-03 "使用 Node.js 代码将 Visual Studio 应用部署到 Azure |Microsoft Docs"  

[AzureCreateFreeAccount]: https://azure.microsoft.com/free "创建 Azure 免费帐户 |Microsoft Azure"  
[AzureWebApps]: https://azure.microsoft.com/services/app-service/web "Web 应用 |Microsoft Azure"  

[WindowsBlogsWebNotificationsEdge]: https://blogs.windows.com/msedgedev/2016/05/16/web-notifications-microsoft-edge#UAbvU2ymUlHO8EUV.97 "Microsoft Edge 中的 Web 通知 |Windows 博客"  

[VisualstudioCodeMain]: https://code.visualstudio.com "Visual Studio 代码"  

[AaronGustafsonNotebookPwaQa]: https://www.aaron-gustafson.com/notebook/pwa-qa "PWA 问答&A"  

[BrowserStackTestEdgeBrowser]: https://www.browserstack.com/test-on-microsoft-edge-browser "Windows 10 上的免费 Microsoft Edge 浏览器测试 |BrowserStack"  

[CloudfourThinksProgressiveRoadmapYourWebApp]: https://cloudfour.com/thinks/a-progressive-roadmap-for-your-progressive-web-app "渐进式 Web 应用的渐进路线图"  

[Davrous20191018MythBustingPwasNewEdgeEdition]: https://www.davrous.com/2019/10/18/myth-busting-pwas-the-new-edge-edition "实现 PBA - 新边缘版本"  

[ExpressjsApplicationGenerator]: https://expressjs.com/starter/generator.html "Express 应用程序生成器 |Express" 

[Fberriman20170626NamingProgressiveWebApps]: https://fberriman.com/2017/06/26/naming-progressive-web-apps "命名渐进式 Web 应用"  

[HackerNewsProgressiveWebApps]: https://hnpwa.com "作为渐进式 Web 应用的黑客新闻阅读器"  

[JoretegBlogBettingWeb]: https://joreteg.com/blog/betting-on-the-web "Web 上的百元"  

[MDNDedicatedWorkerGlobalScopePostMessage]: https://developer.mozilla.org/docs/Web/API/
[MDNNotificationsApi]: https://developer.mozilla.org/docs/Web/API/Notifications_API "通知 API |MDN"  
[MDNProgressiveWebApps]: https://developer.mozilla.org/Apps/Progressive "渐进式 Web 应用 \ (PWA) |MDN"  
[MDNPushApi]: https://developer.mozilla.org/docs/Web/API/Push_API "推送 API |MDN"  
[MDNPushManager]: https://developer.mozilla.org/docs/Web/API/PushManager "PushManager |MDN"  
[MDNServiceWorkerApi]: https://developer.mozilla.org/docs/Web/API/Service_Worker_API "服务工作者 API |MDN"  
[MDNUsingServiceWorkers]: https://developer.mozilla.org/docs/Web/API/Service_Worker_API/Using_Service_Workers "使用服务工作者 |MDN"  
[MDNWebAppManifest]: https://developer.mozilla.org/docs/Web/Manifest "Web 应用清单 |MDN"  

[MediumWebEdgeOfflinePostsProgressiveWebApps]: https://medium.com/web-on-the-edge/offline-posts-with-progressive-web-apps-fc2dc4ad895 "具有渐进式 Web 应用的脱机 POST"  

[MozillaServicesSendingVapidWebPushNotificationsPush]: https://blog.mozilla.org/services/2016/08/23/sending-vapid-identified-webpush-notifications-via-mozillas-push-service "通过 Mozilla 推送服务发送 VAPID 标识的 WebPush 通知 |Mozilla 服务"  

[NodejsMain]: https://nodejs.org "Node.js"  

[NPMWebPush]: https://www.npmjs.com/package/web-push "Web 推送 |npm"  
[NPMWebPushEncrypt]: https://www.npmjs.com/package/web-push#encryptuserpublickey-userauth-payload-contentencoding "encrypt (userPublicKey， userAuth， payload， contentEncoding) - web-push |NPM"  
[NPMWebPushUsage]: https://www.npmjs.com/package/web-push#usage "用法 - Web 推送 |NPM"  

[ProgressiveWebApps]: https://pwa.rocks "渐进式 Web 应用"  

[PwaBuilder]: https://www.pwabuilder.com "PWA 生成器"  
[PwaBuilderServiceWorker]: https://www.pwabuilder.com/serviceworker "服务工作者 |PWA 生成器"  

[ServiceWorkerCookbookPushRichDemo]: https://serviceworke.rs/push-rich_demo.html "推送丰富演示 |ServiceWorker 手册"  

[Smashingmagazine201907ProgressiveWebApplicationFrameworkPart1]: https://www.smashingmagazine.com/2019/07/progressive-web-application-pwa-framework-part-1 "设计和生成不带框架的渐进式 Web (第 1 部分) "  

[Smashingmagazine201907ProgressiveWebApplicationFrameworkPart2]: https://www.smashingmagazine.com/2019/07/progressive-web-application-pwa-framework-part-2 "设计和构建不带框架的渐进式 Web (第 2 部分) "  

[Smashingmagazine201907ProgressiveWebApplicationFrameworkPart3]: https://www.smashingmagazine.com/2019/07/progressive-web-application-pwa-framework-part-3 "设计和生成不带框架的渐进式 Web 应用程序 (第 3 部分) "  

[VapidkeysMain]: https://vapidkeys.com "安全 VAPID 密钥生成器 |VapidKeys" 

[Webhint]: https://webhint.io "webhint"  

[WebDevProgressiveWebApps]: https://developers.google.com/web/progressive-web-apps "渐进式 Web 应用 |web.dev"  

[WikiProgressiveEnhancement]: https://en.wikipedia.org/wiki/Progressive_enhancement "渐进式增强 |Wikipedia"  
