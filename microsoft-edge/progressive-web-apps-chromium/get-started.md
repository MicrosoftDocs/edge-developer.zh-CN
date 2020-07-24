---
description: 本指南概括介绍了如何在 Windows 上构建渐进式 web 应用的 PWA 基础知识和工具。
title: 渐进式 Web 应用（Chromium）入门
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/23/2020
ms.topic: conceptual
ms.prod: microsoft-edge
keywords: 渐进式 web 应用、PWA、Edge、Windows、PWABuilder、web 清单、服务工作人员、推送
ms.openlocfilehash: a9a0cad2d771e52b783053e36f0f23dec5d8e70c
ms.sourcegitcommit: 515522959f517e194f93a27f5d360690600edd9d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/23/2020
ms.locfileid: "10894708"
---
# 渐进式 Web 应用（Chromium）入门  

渐进式 Web 应用 \ （PWAs \）是通过类似应用的功能（如安装、脱机支持和推送通知）[逐渐增强][WikiProgressiveEnhancement]的 web 应用。  你还可以将 PWA 打包到应用商店，包括 Microsoft Store 以及 Google Play、Mac 应用商店等。  Microsoft Store 是内置于 Windows 10 的商业应用商店。  

下面的指南通过创建一个简单的 web 应用并将其作为 PWA 进行扩展，为你提供了 PWA 基础知识的概述。  已完成的项目跨新式浏览器工作。  

> [!TIP]
> 你可以使用[PWABuilder][PwaBuilder]创建新的 pwa、增强现有 pwa 或将 pwa 打包到应用商店。  

## 必备条件  

*   使用[VS 代码][VisualstudioCodeMain]编辑 PWA 源代码。  
*   使用[Node.js][NodejsMain]作为本地 web 服务器。  

## 设置基本 web 应用  

若要创建空的 web 应用，请按照[节点 Express 应用生成器][ExpressjsApplicationGenerator]中的步骤进行操作，并为你的应用命名 `MySamplePwa` 。  

在提示符下，运行以下命令。  

```shell
npx express-generator --no-view
```  

```shell
npm install
```  

这些命令将创建一个空 web 应用并安装任何依赖项。  

现在，你有了一个简单的功能 web 应用。  若要启动它，请运行以下命令。  

```shell
npm start
```  

现在，浏览以 `http://localhost:3000` 查看你的新 web 应用。  

:::image type="complex" source="./media/vs-nodejs-express-index.png" alt-text="在 localhost 上运行新的 PWA":::
   在 localhost 上运行新的 PWA
:::image-end:::

## 开始构建 PWA  

既然你已拥有简单的 web 应用，请通过为 PWAs 添加3个要求将其扩展为 PWA<!--[3 requirements for PWAs][PwaEdgehtmlIndexRequirements]-->： [HTTPS](#step-1---use-https)、 [Web 应用清单](#step-2---create-a-web-app-manifest)和[服务工作人员](#step-3---add-a-service-worker)。  

### 步骤 1-使用 HTTPS  

PWA 平台的关键部分（如[服务工作者][MDNServiceWorkerApi]）需要使用 HTTPS。  当 PWA 进入活动时，必须将其发布到 HTTPS URL。  

出于调试目的，Microsoft Edge 还允许 `http://localhost` 使用 PWA api。  

如果你将[web 应用作为活动网站发布][VisualStudioNodejsTutorialPublishAzureAppService]\ （例如，通过设置[Azure 免费帐户][AzureCreateFreeAccount]\），则必须确保你的服务器配置了 HTTPS。  如果你使用[Microsoft Azure 应用服务][AzureWebApps]托管你的网站，则默认情况下它将通过 HTTPS 进行提供。  

下面的指南，用于 `http://localhost` 构建 PWA。  

### 步骤 2-创建 Web 应用部件清单  

[Web 应用清单][MDNWebAppManifest]是一个 JSON 文件，其中包含有关你的应用的元数据，例如名称、说明、图标等。  

若要向 web 应用添加应用清单，请执行以下操作：  

1.  在 "与代码" 中，转到 "**文件**  >  **打开" 文件夹**，然后选择 `MySamplePwa` 之前创建的目录。  
1.  按下 `Ctrl` + `N` 以创建一个新文件，然后粘贴以下代码片段。  
    
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
1.  添加一个名为的512x512 应用图标图像 `icon512.png` `/MySamplePwa/public/images` 。  你可以使用[示例图像][ImagePwa]进行测试。  
1.  在 VS 代码中，打开 `/public/index.html` 并在标记内添加以下代码段 `<head>` 。  
    
    ```html
    <link rel="manifest" href="/manifest.json">
    ```   
    
### 步骤 3-添加服务工作人员  

服务工作者是 PWAs 背后的关键技术，支持诸如离线支持、高级缓存和运行后台任务的方案，以前限制为本机应用。  

服务工作人员是从你的 web 应用截取网络请求的后台任务。  它们执行任务，即使你的 PWA 未在运行，例如从缓存中服务所请求的资源、发送推送通知、运行后台提取任务、提示标记图标等。  服务工作人员在特殊的 JavaScript 文件中定义。  有关详细信息，请参阅[使用服务工作人员][MDNUsingServiceWorkers]和[服务工作器 API][MDNServiceWorkerApi]。  

若要在你的项目中生成服务工作人员，请使用来自[PWA 生成器][PwaBuilderServiceWorker]的**第一网络**服务工作人员食谱。  

1.  导航到[pwabuilder.com/serviceworker][PwaBuilderServiceWorker]，选择**缓存第一个网络**服务工作人员，然后选择 "**下载**" 按钮。  下载的文件包含以下文件：
    
    *   `pwabuilder-sw-register.js`  
    *   `pwabuilder-sw.js`  
    
1.  将下载的文件复制到 `public` web 应用项目中的文件夹。  
    
1.  在 VS 代码中，打开 `/public/index.html` 并将以下代码片段添加到 `<head>` 标记中。  
    
    ```html
    <script type="module" src="/pwabuilder-sw-register.js"></script>
    ```  
    
你的 web 应用现在有一个服务工作人员使用缓存第一个策略，该策略首先从缓存中提取资源（如图像、JS、CSS 和 HTML），并根据需要回退到网络。  

使用以下步骤确认你的服务工作人员运行。  

1.  使用导航到你的 web 应用 `http://localhost:3000` 。  如果你的 web 应用不可用，请运行以下命令。   
    
    ```shell
    npm start
    ```
    
1.  在 Microsoft Edge 中，选择 `F12` 以打开 Microsoft Edge DevTools。  选择 "**应用程序**"，然后选择 "**服务工作人员**" 以查看服务工作人员。  如果看不到服务工作人员，可能需要刷新页面。  
     
    :::image type="complex" source="./media/devtools-sw-overview.png" alt-text="Microsoft Edge DevTools 服务工作人员概述":::
       Microsoft Edge DevTools 服务工作人员概述
    :::image-end:::
    
1.  通过展开**缓存存储**来查看服务工作人员缓存并选择**pwabuilder-precache**。  你应看到服务工作人员缓存的所有资源，例如应用图标、应用清单、CSS 和 JavaScript 文件。  
    
    :::image type="complex" source="./media/devtools-cache.png" alt-text="Microsoft Edge DevTools 中的服务工作人员缓存":::
       Microsoft Edge DevTools 中的服务工作人员缓存（F12）
    :::image-end:::
    
1.  以脱机应用的形式尝试 PWA。  在 Microsoft Edge DevTools \ （ `F12` \）中，选择 "**网络**"，然后将**联机**状态更改为 "**脱机**"。  
    
    :::image type="complex" source="./media/devtools-offline.png" alt-text="在 Microsoft Edge DevTools 中将应用设置为脱机模式":::
       在 Microsoft Edge DevTools 中将应用设置为脱机模式
    :::image-end:::
    
1.  刷新你的应用，你应该通过从缓存中为你的应用提供服务资源来查看它是否已脱机工作。  
    
    :::image type="complex" source="./media/vs-nodejs-express-index.png" alt-text="PWA 在脱机状态下运行":::
       PWA 在脱机状态下运行
    :::image-end:::
    
## 向 PWA 添加推送通知  

你可以通过完成以下任务来创建支持推送通知的 PWAs。  

1.  使用[推送 API][MDNPushApi]订阅消息服务  
1.  使用[通知 API][MDNNotificationsApi]从服务收到消息时显示 toast 消息  

与服务工作者一样，这些是基于标准的 Api，可跨浏览器使用，因此你只需编写一次代码即可在任何支持 PWAs 的地方工作。  有关向服务器上的不同浏览器传递推送消息的详细信息，请使用[Web 推送][NPMWebPush]开放源代码库。  

以下步骤适用于由 Mozilla 提供的[服务工作人员手册][ServiceWorkerCookbookPushRichDemo]中的 "推送丰富" 演示，这些演示具有许多其他有用的 Web 推送和服务工作人员食谱。  

### 步骤 1-生成 VAPID 键  

推送通知需要 VAPID \ （自愿应用程序服务器标识 \）密钥才能向 PWA 客户端发送推送消息。  有多个 VAPID 密钥生成器可联机使用 \ （例如， [vapidkeys.com][VapidkeysMain]\）。  生成后，应获取包含公钥和私钥的 JSON 对象。  保存密钥以执行以下教程中的后续步骤。  有关 VAPID 和 WebPush 的工作方式的信息，请参阅[通过 Mozilla 的推送服务发送 VAPID 标识的 WebPush 通知][MozillaServicesSendingVapidWebPushNotificationsPush]。  

### 步骤 2-订阅推送通知  

服务工作者处理 PWA 中的推送事件和 toast 通知交互。  若要将 PWA 订阅到服务器推送通知，请确保满足以下条件。  

*   您的 PWA 已安装、处于活动状态且已注册  
*   执行订阅任务的代码位于 PWA 的主 UI 线程上  
*   您有网络连接  

在创建新推送订阅之前，Microsoft Edge 检查用户是否授予了 PWA 接收通知的权限。  如果不是，则浏览器会提示用户提供权限。  如果权限被拒绝，则 `registration.pushManager.subscribe` 引发必须处理的请求 `DOMException` 。  有关权限管理的详细信息，请参阅[Microsoft Edge 中的推送通知][WindowsBlogsWebNotificationsEdge]。  

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

有关详细信息，请参阅[PushManager][MDNPushManager]和[Web 推送][NPMWebPushUsage]。  

### 步骤 3-侦听推送通知  

现在，在你的 PWA 中设置了订阅，向服务工作人员添加对推送事件（从服务器发送）的处理程序，以使用收到的消息的数据显示 toast 通知。  必须添加一个单击处理程序来执行以下任一任务。  
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

### 步骤 4-试用  

执行以下步骤来测试 PWA 中的推送通知。  

1.  在上导航到你的 PWA `http://localhost:3000` 。  当你的服务工作者激活并尝试将你的 PWA 订阅到推送通知时，Microsoft Edge 会提示你允许 PWA 显示通知。  选择 "**允许**"。  
    
    :::image type="complex" source="./media/notification-permission.png" alt-text="用于启用通知的权限对话框":::
       用于启用通知的权限对话框
    :::image-end:::
    
    
1.  模拟服务器端推送通知。  `http://localhost:3000`在浏览器中打开 PWA 后，选择 `F12` 以打开 DevTools。  选择 "**应用程序**  >  **服务工作人员**  >  **推送**" 以向你的 PWA 发送测试推送通知。  你应该会看到任务栏附近显示 "推送通知"。  
    
    :::image type="complex" source="./media/devtools-push.png" alt-text="推送来自 DevTools 的通知":::
       推送来自 DevTools 的通知
    :::image-end:::
     
    如果您没有选择 \ （或激活 \） toast 通知，则它将在几秒钟后关闭，并在 Windows 操作中心内排队。  
    
    :::image type="complex" source="./media/windows-action-center.png" alt-text="Windows 操作中心中的通知":::
       Windows 操作中心中的通知
    :::image-end:::
    
    
## 后续步骤  

以下是在构建现实世界 PWAs 时要了解的其他任务的列表：  

*  管理和存储推送订阅  
*  [加密][NPMWebPushEncrypt]有效负载数据  
*  响应式设计  
*  深度链接  
*  [跨浏览器测试][BrowserStackTestEdgeBrowser]  
*  实现最佳做法，如[Webhint][Webhint]  

## 另请参阅  

*   [MDN web 文档上的渐进式 Web 应用][MDNProgressiveWebApps]。  
*   [Web 上的渐进式 Web 应用][WebDevProgressiveWebApps]。  
*   [作为渐进 Web 应用的黑客新闻阅读器][HackerNewsProgressiveWebApps]-比较不同的框架和性能模式，用于实现示例 \ （黑客新闻阅读器 \） PWA。  

<!-- image links -->  

[ImagePwa]: ./media/pwa.png  

<!-- links -->  

<!--[PwaEdgehtmlIndexRequirements]: ../progressive-web-apps-edgehtml/index.md#requirements "Requirements - Progressive Web Apps \(EdgeHTML\) on Windows | Microsoft Docs"  -->  

[VisualStudioNodejsTutorialPublishAzureAppService]: /azure/javascript/tutorial-vscode-azure-app-service-node-03 "使用 VS 代码将 Node.js 应用部署到 Azure |Microsoft 文档"  

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
