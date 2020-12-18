---
description: 本指南概述了在 Windows 上生成渐进式 Web 应用的 PWA 基础知识和工具。
title: 渐进式 Web 应用入门
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: 渐进式 Web 应用， PWA， Edge， Windows， PWABuilder， Web 清单， 服务工作者， 推送
ms.date: 12/02/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 9a76399616ab7645b82242b94dd4757b73b37f60
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232020"
---
# 渐进式 Web 应用入门  

渐进式 Web 应用 \ (PWA\) 只是 Web 应用，[][WikiProgressiveEnhancement]通过支持平台和浏览器引擎上的本机类似应用功能（如从主屏幕启动、脱机支持和推送通知）逐渐增强。  在具有 Microsoft Edge \ (EdgeHTML\) 引擎的 Windows 10 上，PWA 享受独立于浏览器窗口作为通用 [Windows 平台应用运行的附加][WindowsUwpGetStartedWhat] 优势。  

本指南通过使用 Microsoft Visual Studio 和一些 PWA 生成器实用程序将简单的 Web 应用 `localhost` 构建为 PWA，概述了 PWA 基础知识。  完成的产品在支持 PWA 的任何浏览器中的工作方式类似。  

> [!TIP]
> 若要快速将现有网站转换为 PWA 并将其打包用于 Windows 10 和其他应用平台，请查看 [PWA 生成器][PwaBuilder]。  

## 必备条件  

可以使用任何 Web 开发 IDE 生成 PWA。  下面只是本指南的先决条件，它可指导你完成 Windows 开发人员生态系统中的 PWA 工具支持。  

*   下载 \ (free\) Visual Studio Community [2017][VisualStudioDownloads]。  您还可以使用专业版、企业版 [或预览][VisualStudioPreview] 版。  从Visual Studio安装程序中，选择以下工作负载。  
    
    *   **通用 Windows 平台开发**  
    *   **Node.js开发**  

## 设置基本 Web 应用  

为简单起见，请使用 Visual Studio [Node.js 和 Express][VisualStudioNodeJsTutorial] 应用模板来创建提供页面的 Web `localhost` `index.html` 应用。  假设这是一个占位符，用于作为 PWA 进行开发且功能齐全的 Web 应用。  

1.  启动Visual Studio，然后启动新项目。  
    *   **文件**  > **新建**  > **项目...**  
    *   `Ctrl`+`Shift`+`N`  
1.  在 **JavaScript**下，选择 **Node.js Express 4 应用程序**。  设置名称和位置，然后选择"**确定"。**  
    
    ![选择Node.js Express 4 项目模板Visual Studio][ImageVsNodejsExpressTemplate]  
    
1.  加载新项目后，**选择"生成**\ (`Ctrl` + `Shift` + `B` \) "，然后启动调试**** \ (`F5` \) 。  验证在 `index.html` 浏览到 时文件是否加载 `http://localhost:1337` 。  
    
    ![在 localhost 上运行新网站][ImageVsNodejsExpressIndex]  

## 将应用转换为 PWA  

现在，可以连接 Web 应用的基本 [PWA][PwaEdgehtmlIndexRequirements] 要求 *：Web 应用程序*清单 *、HTTPS* *和服务工作者*。  

### Web 应用清单  

[Web 应用清单][MDNWebAppManifest]是描述应用的 JSON 元数据文件，包括名称、作者、条目页 URL 以及一个或多个图标。  因为它遵循基于 [标准的][W3cWebAppManifest]架构，因此只能提供要安装在任何支持 PWA 的平台、操作系统和设备组合上的 PWA 的单个 Web 应用清单。  在 Windows 生态系统中，Web 应用清单向必应 Web 索引器发出信号，表明您的 PWA 是自动包含在 [Microsoft Store][PwaEdgehtmlMicrosoftStore]中的候选项，其中每月有近 7 亿活跃用户作为 Windows 10 应用。  

如果这是一个现有的实时网站，可以使用 PWA 生成器生成 [Web 应用程序清单][PwaBuilder]。  由于它仍然是一个未发布的项目，因此请复制示例清单。  

1.  在Visual Studio资源管理器中，右** 键单击该公用文件夹，然后选择**"添加新文件****  >  **..."，** 指定为 `manifest.json` 项目名称。  
1.  在 `manifest.json` 文件中，复制以下代码。  

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
    
    在真实的 PWA 中，下一步是自定义** 名称、start_url、short_name、说明** 和图标*\ (* 图标，下一步\) 。 ** **  
    
    若要了解有关不同成员值和相关用途的信息，请参阅 [Web 应用清单][MDNWebAppManifest] 参考。  
    
1.  接下来，使用 PWA 生成器应用图像生成器使用实际图像路径 `icons` 填充空数组。  
    
    1.  使用 Web 浏览器，下载此示例 [512x512 PWA 图像][ImagePwa]。  
    1.  转到 PWA 生成器 [应用图像][PwaBuilderAppImageGenerator]生成器，选择刚保存为输入图像 `pwa.png` **的图像** ，然后选择"下载 **"** 按钮。  
    1.  **打开** 并 **提取** zip 文件。  
    1.  在Visual Studio资源管理器中，右键单击文件夹，在文件 `public` **资源管理器中打开文件夹**。  创建一 **个名为 "新建"** 的文件夹 `images` 。  
    1.  将提取的 zip 的所有平台文件夹 \ (， ，等等\) 复制到文件夹并 `android` `chrome` `windows10` `images` 关闭文件资源管理器窗口。  将文件夹添加到解决方案资源管理器Visual Studio \ (项目 \ (，右键单击文件夹，然后针对每个文件夹选择"添加现有文件夹 `images` ****  >  ****..."\) 。  
    1.  从 (zip 中打开 \Visual Studio 或任何编辑器\) 文件，将数组复制到 `icons.json` `"icons": [...]` `manifest.json` 项目文件中。  

1.  现在，必须将 Web 应用清单与你的应用关联。  在 folder\ (中打开文件 \) 进行编辑，然后直接在样式表链接后 `layout.pug` `views` 添加此行。  \ (它只是 [\) ][PugAttributes] 的 Node pug `<link rel='manifest' href='/manifest.json'>` 模板简写。  
    
    ```html
    link(rel='manifest', href='/manifest.json')
    ```  
    
所有这些就绪后，Web 应用现在即可提供清单和主屏幕就绪应用图标！  尝试运行应用 \ (`F5` \) 并加载清单。  

![从 localhost 加载 Web 应用清单][ImageVsNodejsExpressManifest]  

以及你的图标之一。  

![从 localhost 加载 Square71x71Logo 应用徽标][ImageVsNodejsExpressIcon]  

如果使用实际 \) 发布实时 \ (应用，必应搜索引擎现在将其标识为自动打包并提交到 Microsoft Store 的候选项，作为可安装的 `start_url` Windows 10 应用。 [][PwaEdgehtmlMicrosoftStore]  确保你的manifest.js文件包含必应扫描的渐进式 [Web 应用][WindowsBlogsPwaEdge] 的质量信号，包括以下项目。   

*   `name`  
*   `description`  
*   至少一个图标 512px 正方形或更大的 \ (以确保图像源具有足够的分辨率，以便自动生成应用的初始屏幕、应用商店一览、磁贴图像等\) 。  

此外，使用[HTTPS，](#https)[服务工作者](#service-workers)，并遵守[Microsoft Store 策略][LegalWindowsAgrementsMicrosoftStorePolicies]。  

### HTTPS  

[][MDNServiceWorkerApi]服务工作人员和其他关键 PWA 技术与服务工作人员 \ (（如缓存、推送和后台[][MDNCache]同步[][MDNPushApi]API\) ）仅跨安全连接工作，这意味着[HTTPS][WikiHttps]用于实时网站或调试目的。 [][MDNSyncManager] `localhost`  

如果你将 [此 Web][VisualStudioNodejsTutorialPublishAzureAppService] 应用发布为实时网站 \ (例如，通过设置 [Azure][AzureCreateFreeAccount]免费帐户 \) ，则必须确保服务器已针对 HTTPS 进行配置。  如果使用 Microsoft [Azure 应用服务][AzureWebApps] 托管网站，默认情况下通过 HTTPS 提供服务。  

对于本指南，继续使用 `http://localhost` 作为所服务实时网站的占位符 `https://` 。  

### 服务工作者  

服务工作人员是 PBA 背后的关键技术。 服务工作人员充当 PWA 和网络之间的代理，以使您的网站能够充当已安装的本机应用，提供脱机方案、响应服务器推送通知和运行后台任务。  服务工作人员还打开了新的性能策略。  无需实现完整的 Web 应用，就需使用服务工作器缓存来为网站微调页面加载性能。  

服务工作者是事件驱动的后台线程，从 JavaScript 文件运行，与支持 Web 应用的常规脚本一起提供。  由于服务工作者不在主 UI 线程上运行，因此服务工作者没有 DOM 访问权限，尽管[UI][MDNWorkerPrototypePostMessage]线程和[][MDNDedicatedWorkerGlobalScopePostMessage]工作线程能够使用和事件 `postMessage()` `onmessage` 处理程序进行通信。  

将服务工作者注册到网站 \ (的 URL 源或其中指定的路径\) 。  注册后，将在用户计算机上下载、安装和激活服务工作文件。  有关详细信息，MDN Web 文档具有有关使用 [服务][MDNUsingServiceWorkers] 工作者的综合指南和详细的 [服务工作者 API][MDNServiceWorkerApi] 参考。  

对于本教程，请使用 PWA 生成器上的脱机页面服务 [工作器脚本][PwaBuilderServiceWorker]。  首先，根据性能要求、网络带宽等自定义具有更多功能的脚本。  查看 [Mozilla 提供的][ServiceWorkerCookbook]  服务工作者手册，了解许多有用的服务工作者缓存想法。  

1.  打开 [https://www.pwabuilder.com/serviceworker][PwaBuilderServiceWorker] 并选择 \ (default\) **脱机页面** 服务工作线程，然后单击 **"下载服务工作线程"** 按钮。  
1.  打开下载文件夹并复制以下两个文件  

    *   ServiceWorker1\pwabuilder-sw-register.js  
    *   ServiceWorker1\pwabuilder-sw.js  
    
    将文件保存到 `public` Web 应用项目Visual Studio文件夹。  \ (From Visual Studio， use `Ctrl` + `O` to open file explorer to your project and navigate to the `public` folder\) .  
    
    在解决方案资源管理器中 `public/pwabuilder-sw.js` ，打开文件，将值 `offlineFallbackPage` 更改为 `offline.html` 。  
    
    ```javascript
    const offlineFallbackPage = "offline.html";
    ```
    
    值得一看这两个文件的代码，以了解如何注册缓存指定页面 \ (\) 的服务工作器，在网络提取失败时提供服务。 `offline.html`  接下来，创建一 `offline.html` 个简单的页面作为应用的脱机功能的占位符。  
    
1.  在解决方案资源管理器中， `views/layout.pug` 打开该文件，并添加链接标记下方的以下行。  
    
    ```html
    script(src='/pwabuilder-sw-register.js' type='module')
    ```  
    
    您的网站加载并运行服务工作者注册脚本。  
    
1.  在解决方案资源管理器中，右键单击该 `public` 文件夹，然后选择 **"**  >  **添加新文件..."。** 将其命名 `offline.html` ，并添加 `<title>` 一个和一些正文内容，例如以下代码。  
    
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
    
    此时，你的 `public` 文件夹应具有三个新文件。  
    
    ![添加到解决方案的公用文件夹的文件][ImageVsNodejsExpressPublic]  
    
1.  在解决方案资源管理器中，打开该文件，并添加以下代码，然后最后一个命令 `routes\index.js` \ (`module.exports = router;` \) 。  
    
    ```javascript
    router.get('/offline.html', function (req, res) {
        res.sendFile('public/offline.html');
    });
    ```  
    
    这会指示你的应用在服务工作线程为脱机缓存 `offline.html` \ (提取文件时为该文件 \) 。  
    
1.  测试 PWA！  生成 \ (\) 并运行 \ (\) Web 应用以启动 `Ctrl` + `Shift` + `B` Microsoft `F5` Edge 并打开 `localhost` 你的页面。  然后完成以下步骤。  
    
    1.  打开 Edge DevTools**控制台**\ (`Ctrl` + `Shift` + `J` \) 并验证服务工作者已注册。  
    1.  在 **调试器面板** 中，展开 **服务工作者** 控件并单击源。  在 **"服务工作器概述**"中，验证服务工作器是否激活并正在运行。  
        
        ![Edge DevTools Service Worker 概述][ImageDevtoolsSwOverview]  
        
    1.  展开 **缓存** 控件并验证 `offline.html` 页面是否缓存。  
        
        ![Edge DevTools 服务工作器缓存][ImageDevtoolsSwCache]  
        
1.  尝试将 PWA 作为脱机应用的时间！  In Visual Studio， **Stop Debugging** \ (`Shift` + `F5` \) your web app， then open Microsoft Edge \ (or refresh\) to the localhost address of your website.  它现在应该会加载 `offline.html` 页面 \ (，这要归功于服务工作线程和脱机缓存\) ！  
    
    ![offline.htmmicrosoft Edge http://localhost:1337 中加载的 l][ImageOfflineHtml]  

## 添加推送通知  

通过添加对推送通知的客户端支持（使用推送 [API][MDNPushApi] 订阅消息传递服务和通知 [API，][MDNNotificationsApi] 以在收到消息时显示 Toast 消息）使 PWA 更像应用。  与服务工作人员一样，这些 API 是基于标准的 API，可跨浏览器工作，因此只需编写代码一次，它才能在支持 PWA 的任何地方工作。  在服务器端，使用 Web [推送][NPMWebPush] 开放源代码库处理将推送消息发送到各种浏览器所涉及的差异。  

以下内容改编自 Mozilla 提供的"服务[][ServiceWorkerCookbookPushRichDemo]工作者手册中的推送丰富演示"，值得查看其他一些有用的 Web 推送和服务工作者方法。  

### 步骤 1 - 安装 NPM Web 推送库  

在Visual Studio资源管理器中，右键单击您的项目，然后打开Node.js **交互窗口...** 在它内，键入以下代码。  

```javascript
.npm install web-push
```  

这将安装 [Web 推送][NPMWebPush] 库。  然后，打开文件，在其他要求语句之后将以下行 `index.js` 添加到文件顶部。  

```javascript
var webpush = require('web-push');
```  

### 步骤 2 - 为服务器生成 VAPID 密钥  

接下来，必须生成 VAPID \ (自愿应用程序服务器标识\) 密钥，服务器向 PWA 客户端发送推送消息。  只需执行一次 \ (，即服务器只需要一对 VAPID 密钥\) 。  在Node.js窗口中，键入以下代码。  

```javascript
var webpush = require('web-push');
webpush.generateVAPIDKeys();
```  

输出结果应包含一个公钥和私钥的 JSON 对象，你可以将其复制到服务器逻辑中。  

在文件 `index.js` 的最后一个 \ (`module.exports = router` \) 行之前，添加以下代码。  

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

复制 `publicKey` 刚 `privateKey` 生成的和值。  可以随意自定义 `mailto` \ (，尽管运行此示例不需要\) 。  

如果你对 VAPID 和 WebPush 的后台工作原理的详细信息感兴趣 [，Mozilla][MozillaServicesSendingVapidWebPushNotificationsPush] 服务工程博客有一个很好的解释者。  

### 步骤 3 - 处理与推送相关的服务器请求  

现在设置用于处理来自 PWA 客户端的推送相关请求的路由，包括提供 VAPID 公钥和注册客户端以接收推送。  

在真实方案中，推送通知可能源自服务器逻辑中的事件。  若要简化此处的一些操作，必须将**** 推送通知按钮添加到 PWA 主页以从我们的服务器生成推送，并添加终结点 `/sendNotification` \ (服务器路由\) 来处理这些请求。  

在文件中，将以下路由附加到在 `index.js` [步骤 2][#step-2---generate-vapid-keys-for-your-server] 中添加的 VAPID 初始化代码之后。  

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

在服务器端代码就位后，PWA 客户端上的推送通知就位。  

### 步骤 4 - 订阅推送通知  

作为 PWA 网络代理角色的一部分，服务工作人员处理推送事件和 Toast 通知交互。  但是，与首次设置 \ (或注册\) 服务工作者一样，将 PWA 订阅到服务器推送通知发生在 PWA 的主 UI 线程上，并且需要网络连接。  订阅推送通知需要活动的服务工作者注册，因此必须先验证服务工作者是否已安装并处于活动状态，然后再尝试订阅推送通知。  

在新建推送订阅之前，Microsoft Edge 会检查用户是否授予了 PWA 接收通知的权限。  如果没有，浏览器会提示用户授予权限。  如果权限被拒绝，则会引发 `registration.pushManager.subscribe` 一个 `DOMException` 请求，因此您必须处理它。  有关权限管理 More on permission management， see [Push Notifications in Microsoft Edge][WindowsBlogsWebNotificationsEdge].  

在 `pwabuilder-sw-register.js` 文件中，附加以下代码。  

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

查看有关 [PushManager][MDNPushManager] 接口的 MDN 文档和 Web [推送][NPMWebPushUsage] 库上的 NPM 文档，了解有关 API 如何工作以及各种相关选项的更多详细信息。  

### 步骤 5 - 设置推送和 notificationclick 事件处理程序  

设置推送订阅后，剩余工作将发生在服务工作者中。  首先，您必须为服务器发送的推送事件设置处理程序，并响应 toast 通知 \ (如果授予权限\) 显示推送数据负载。  接下来，为 Toast 添加一个单击处理程序以关闭通知，并浏览当前打开的窗口的列表，以打开、聚焦或打开并聚焦预期的 PWA 客户端页面。  

在 `pwabuilder-sw.js` 文件中，追加以下处理程序。  

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

### 步骤 6 - 试用  

在 PWA 中测试推送通知的时间！  

1.  在浏览器中 (`F5` \) \) PWA。  由于修改了服务工作器代码 \ (\) ，因此您必须打开 `pwabuilder-sw.js` DevTools Debugger \ (\) 到"服务工作者概述"面板并注销服务工作器并重新加载 \ (\) 页面以重新注册它 \ (或者单击"更新 `F12` ******** `F5` ") 。 ****  在生产方案中，浏览器会定期检查服务工作者更新，并在后台安装更新。  你应在此处强制它，以立即获得结果。  
    
    当服务工作者激活并尝试订阅 PWA 以推送通知时，您应在页面底部看到一个权限对话框。  
    
    ![用于启用通知的权限对话框][ImageNotificationPermission]  
    
    选择 **"是** "为 PWA 启用 Toast 通知。  
    
1.  从"服务工作者概述"窗格中，尝试选择  **"推送"** 按钮。  应显示包含 \ (硬编码的"从 DevTools 测试推送消息"\) 通知。  
    
    ![从 DevTools 推送通知][ImageDevtoolsPush]  
    
1.  接下来 **，尝试选择** PWA 主页上的"发送通知"按钮。  此时将显示包含服务器有效负载的 Toast。  
    
    ![从 PWA 服务器推送通知][ImagePwaPush]  
    
    如果不单击 \ (或 activate\) toast 通知，它将在几秒钟后关闭，并排入 Windows 操作中心。  
    
    ![Windows 操作中心中的通知][ImageWindowsActionCenter]  
    
    您具有 PWA 推送通知的基础知识。  在真实的应用中，通过管理和存储推送订阅以及正确加密通过线路发送的有效负载数据的方式实现接下来的步骤。 [][NPMWebPushEncrypt]  
    
## 深入探索  

本指南演示了渐进式 Web 应用和 Microsoft PWA 开发工具（包括 Visual Studio、PWA 生成器和 Edge DevTools）的基本分析。  

当然，除了您在此处阅读的 PWA 之外，制作出色的[PWA][PwaEdgehtmlIndexRequirements]还涉及很多内容，包括响应式设计、深度链接[][BrowserStackTestEdgeBrowser]、跨浏览器测试和其他最佳实践[\ (][Webhint]不要提及您的应用程序功能！\) ，但希望本指南能够深入介绍 PWA 基础知识和入门的一些想法。  如果你对 Windows 或 windows 的 PWA 开发有进一Visual Studio，请留下评论！  

查看其他 PWA 指南，了解如何提高客户参与度并提供更加无缝、与操作系统集成的应用体验。  

*   [Windows 定制][PwaEdgehtmlWindowsFeatures]。 使用简单的功能检测，可以通过本机 Windows 运行时 \ (WinRT\) API 逐步增强适用于 Windows 10 客户的 PWA，例如用于自定义 **Windows"** 开始"菜单磁贴通知和任务栏跳转列表的 API，以及使用用户资源（如照片、音乐和日历）的 \ (权限\) 。  
*   [Microsoft Store 中的 PWA。][PwaEdgehtmlMicrosoftStore]  详细了解应用商店分发的好处以及如何提交 PWA。  

## 另请参阅  

*   [MDN Web 文档上的渐进][MDNProgressiveWebApps] Web 应用 - 关于渐进式 Web 应用的出色指南。  
*   [Web.dev 上的][WebDevProgressiveWebApps] 渐进 Web 应用 - 关于渐进式 Web 应用的出色指南。  
*   [渐进式 Web 应用中心][ProgressiveWebApps] - 展示 PBA 的真实示例。  
*   [作为渐进式 Web][HackerNewsProgressiveWebApps] 应用的黑客新闻阅读器 - 比较用于实现示例 \ (黑客新闻阅读器\) PWA 的不同框架和性能模式。  

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

[PwaEdgehtmlIndexRequirements]: ../progressive-web-apps/index.md#requirements "要求 - Windows 上的渐进式 Web 应用 \ (EdgeHTML\) |Microsoft Docs"  
[PwaEdgehtmlMicrosoftStore]: ../progressive-web-apps/microsoft-store.md "渐进式 Web 应用 \ (Microsoft Store ) EdgeHTML\) |Microsoft Docs"  
[PwaEdgehtmlWindowsFeatures]: ../progressive-web-apps/windows-features.md "定制适用于 Windows 的 PWA \ (EdgeHTML\) |Microsoft Docs"  

[LegalWindowsAgrementsMicrosoftStorePolicies]: /legal/windows/agreements/store-policies "Microsoft Store 策略 |Microsoft Docs"  

[VisualStudioNodeJsTutorial]: /visualstudio/nodejs/tutorial-nodejs "教程：在 Node.js 创建应用和 Express Visual Studio |Microsoft Docs"  
[VisualStudioNodejsTutorialPublishAzureAppService]: /visualstudio/nodejs/tutorial-nodejs#optional-publish-to-azure-app-service "发布到 Azure 应用服务 - 在 Node.js 和 Express Visual Studio |Microsoft Docs"  

[WindowsUwpGetStartedWhat]: /windows/uwp/get-started/whats-a-uwp "什么是通用 Windows 平台 \ (UWP\) 应用？ |Microsoft Docs"  

[AzureCreateFreeAccount]: https://azure.microsoft.com/free "创建 Azure 免费帐户 |Microsoft Azure"  
[AzureWebApps]: https://azure.microsoft.com/services/app-service/web "Web 应用 |Microsoft Azure"  

<!--[DeveloperEdgeToolsRemote]: https://developer.microsoft.com/microsoft-edge/tools/remote/ "page not found"  -->  

[WindowsBlogsPwaEdge]: https://blogs.windows.com/msedgedev/2018/02/06/welcoming-progressive-web-apps-edge-windows-10/#4UOdrDJj3124VIkc.97 "使渐进式 Web 应用与 Microsoft Edge 和 Windows 10 保持一致 |Windows 博客"  
[WindowsBlogsWebNotificationsEdge]: https://blogs.windows.com/msedgedev/2016/05/16/web-notifications-microsoft-edge#UAbvU2ymUlHO8EUV.97 "Microsoft Edge 中的 Web 通知 |Windows 博客"  

[VisualStudioDownloads]: https://www.visualstudio.com/downloads "下载 |Visual Studio"  
[VisualStudioFree]: https://visualstudio.microsoft.com/free-developer-offers "免费开发人员软件&服务 |Visual Studio"  
[VisualStudioPreview]: https://www.visualstudio.com/vs/preview "Visual Studio预览"  

[BrowserStackTestEdgeBrowser]: https://www.browserstack.com/test-on-microsoft-edge-browser "Windows 10 上的免费 Microsoft Edge 浏览器测试 |BrowserStack"  

[HackerNewsProgressiveWebApps]: https://hnpwa.com "作为渐进式 Web 应用的黑客新闻阅读器"  

[MDNCache]: https://developer.mozilla.org/docs/Web/API/Cache "缓存 |MDN"  
[MDNDedicatedWorkerGlobalScopePostMessage]: https://developer.mozilla.org/docs/Web/API/DedicatedWorkerGlobalScope/postMessage "DedicatedWorkerGlobalScope.postMessage\ (\) |MDN"  
[MDNNotificationsApi]: https://developer.mozilla.org/docs/Web/API/Notifications_API "通知 API |MDN"  
[MDNProgressiveWebApps]: https://developer.mozilla.org/Apps/Progressive "渐进式 Web 应用 \ (PWA) |MDN"  
[MDNPushApi]: https://developer.mozilla.org/docs/Web/API/Push_API "推送 API |MDN"  
[MDNPushManager]: https://developer.mozilla.org/docs/Web/API/PushManager "PushManager |MDN"  
[MDNServiceWorkerApi]: https://developer.mozilla.org/docs/Web/API/Service_Worker_API "服务工作者 API |MDN"  
[MDNSyncManager]: https://developer.mozilla.org/docs/Web/API/SyncManager "SyncManager |MDN"  
[MDNUsingServiceWorkers]: https://developer.mozilla.org/docs/Web/API/Service_Worker_API/Using_Service_Workers "使用服务工作者 |MDN"  
[MDNWebAppManifest]: https://developer.mozilla.org/docs/Web/Manifest "Web 应用清单 |MDN"  
[MDNWorkerPrototypePostMessage]: https://developer.mozilla.org/docs/Web/API/Worker/postMessage "Worker.prototype.postMessage\ (\) |MDN"  

[MozillaServicesSendingVapidWebPushNotificationsPush]: https://blog.mozilla.org/services/2016/08/23/sending-vapid-identified-webpush-notifications-via-mozillas-push-service "通过 Mozilla 推送服务发送 VAPID 标识的 WebPush 通知 |Mozilla 服务"  

[NPMWebPush]: https://www.npmjs.com/package/web-push "Web 推送 |npm"  
[NPMWebPushEncrypt]: https://www.npmjs.com/package/web-push#encryptuserpublickey-userauth-payload-contentencoding "encrypt (userPublicKey， userAuth， payload， contentEncoding) - web-push |NPM"  
[NPMWebPushUsage]: https://www.npmjs.com/package/web-push#usage "用法 - Web 推送 |NPM"  

[ProgressiveWebApps]: https://pwa.rocks "渐进式 Web 应用"  

[PugAttributes]: https://pugjs.org/language/attributes.html "属性 |Pug"  

[PwaBuilder]: https://www.pwabuilder.com "PWA 生成器"  
[PwaBuilderAppImageGenerator]: https://www.pwabuilder.com/imageGenerator "应用映像生成器"  
[PwaBuilderServiceWorker]: https://www.pwabuilder.com/serviceworker "服务工作者 |PWA 生成器"  

[ServiceWorkerCookbook]: https://serviceworke.rs "ServiceWorker 手册"  
[ServiceWorkerCookbookPushRichDemo]: https://serviceworke.rs/push-rich_demo.html "推送丰富演示 |ServiceWorker 手册"  

[W3cWebAppManifest]: https://www.w3.org/TR/appmanifest "Web 应用清单 |W3C"  

[Webhint]: https://sonarwhal.com "webhint，Web 最佳实践的提示引擎" 
 
[MDNWebWorkers]: https://developer.mozilla.org/docs/Web/API/Web_Workers_API/Using_web_workers "使用 Web 工作人员" 

[WebDevProgressiveWebApps]: https://developers.google.com/web/progressive-web-apps "渐进式 Web 应用 |web.dev"  

[WikiHttps]: https://en.wikipedia.org/wiki/HTTPS "HTTPS |Wikipedia"  
[WikiProgressiveEnhancement]: https://en.wikipedia.org/wiki/Progressive_enhancement "渐进式增强 |Wikipedia"  
