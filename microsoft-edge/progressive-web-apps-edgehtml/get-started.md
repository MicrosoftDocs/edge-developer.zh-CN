---
description: 本指南概括介绍了如何在 Windows 上构建渐进式 web 应用的 PWA 基础知识和工具。
title: 渐进式 Web 应用入门
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/17/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 渐进式 web 应用、PWA、Edge、Windows、PWABuilder、web 清单、服务工作人员、推送
ms.openlocfilehash: 4d7b571b83048f9ce271f451a7537027bb92eebc
ms.sourcegitcommit: 9169d784485e3cb0b1987a8f395c4bb688bd9b2e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "10583782"
---
# 渐进式 Web 应用入门  

渐进式 Web 应用 \ （PWAs \）是一种 web 应用，可在支持平台和浏览器引擎（如从主屏幕安装、脱机支持和推送通知）中以类似于本机应用的功能[逐渐增强][WikiProgressiveEnhancement]。  在使用 Microsoft Edge \ （EdgeHTML \）引擎的 Windows 10 上，PWAs 将独立于浏览器窗口运行的额外优势视为[通用 Windows 平台][WindowsUwpGetStartedWhat]应用。  

本指南通过 `localhost` 使用 Microsoft Visual Studio 和一些 Pwa 生成器实用工具构建一个简单的 web 应用，为你提供了 pwa 基础知识的概述。  已完成的产品在任何支持 PWAs 的浏览器中的工作方式都类似。  

> [!TIP]
> 若要快速将现有网站转换为 PWA 并将其打包到 Windows 10 和其他应用平台，请查看[PWA 生成器][PwaBuilder]。  

## 必备条件  

你可以通过任何 web 开发 IDE 生成 PWAs。  以下仅是本指南的先决条件，本指南将指导你完成 Windows 开发人员生态系统中的 PWA 工具支持。  

*   下载 \ （免费 \） [Visual Studio 社区 2017][VisualStudioDownloads]。  您也可以使用专业版、企业版或[预览版][VisualStudioPreview]。  从 Visual Studio 安装程序中，选择以下工作负荷。  
    
    *   **通用 Windows 平台开发**  
    *   **Node.js 开发**  

## 设置基本 web 应用  

为了简便起见，请使用 Visual Studio node.js[和 Express 应用][VisualStudioNodeJsTutorial]模板来创建用于提供 `localhost` 页面的 web 应用 `index.html` 。  假设你是作为 PWA 开发的引人注目的全功能 web 应用的占位符。  

1.  启动 Visual Studio，然后启动新项目。  
    *   **文件**  > **新**  > **项目 ...**  
    *   `Ctrl`+`Shift`+`N`  
1.  在 " **JavaScript**" 下，选择 "**基本节点 .Js Express 4 应用程序**"。  设置 "名称" 和 "位置"，然后选择 **"确定"**。  
    
    ![在 Visual Studio 中选择节点 .js Express 4 项目模板][ImageVsNodejsExpressTemplate]  
    
1.  新项目加载后，选择 "**生成**\ （ `Ctrl` + `Shift` + `B` \）" 并**开始调试**\ （ `F5` \）。  验证在 `index.html` 浏览时是否加载文件 `http://localhost:1337` 。  
    
    ![在 localhost 上运行新网站][ImageVsNodejsExpressIndex]  

## 将应用转换为 PWA  

现在可以将 web 应用的基本[PWA 要求][PwaEdgehtmlIndexRequirements]连在一起： *web 应用清单*、 *HTTPS*和*服务工作人员*。  

### Web App 清单  

[Web 应用清单][MDNWebAppManifest]是一个 JSON 元数据文件，用于描述你的应用，包括名称、作者、条目页面 URL 和一个或多个图标。  由于它遵循[基于标准的架构][W3cWebAppManifest]，因此你必须仅为你在支持 PWAs 的任何平台、操作系统和设备组合上安装的 PWA 提供单个 web 应用清单。  在 Windows 生态系统中，你的 web 应用清单向 Bing web app 清单发出通知，表明你的 PWA 是 Microsoft Store 中自动包含的候选 web 索引器，在这种情况下，可能会在[Microsoft Store][PwaEdgehtmlMicrosoftStore]中将几乎700000000的每月活动用户作为 Windows 10 应用  

如果这是一个现有的实时网站，你可以使用[PWA 生成器][PwaBuilder]生成 web 应用清单。  由于它仍是未发布的项目，因此请复制示例清单。  

1.  在 Visual Studio "*解决方案资源管理器*" 中，右键单击*公用*文件夹，然后选择 "**添加**  >  **新文件 ...**"，将 `manifest.json` 其指定为项目名称。  
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
    
    在真正的 PWA 中，下一步是自定义*名称*、 *start_url*、 *short_name*、*说明*和*图标*\ （下一步中将介绍图标 \）。  
    
    若要了解有关不同成员值和关联用途的详细信息，请参阅[Web App 清单][MDNWebAppManifest]参考。  
    
1.  接下来， `icons` 使用 PWA 生成器应用图像生成器，使用实际图像路径填充空数组。  
    
    1.  使用 web 浏览器，下载此[示例 512X512 PWA 图像][ImagePwa]。  
    1.  转到 PWA 生成器[应用图像生成器][PwaBuilderAppImageGenerator]，选择 `pwa.png` 刚保存为**输入图像**的图像，然后选择 "**下载**" 按钮。  
    1.  **打开**并**解压缩**zip 文件。  
    1.  在 Visual Studio 的 "解决方案资源管理器" 中，右键单击 `public` 文件夹，然后**在文件资源管理器中打开文件夹**。  创建一个名为的**新文件夹** `images` 。  
    1.  将所有平台文件夹 \ （、、 `android` 等 `chrome` `windows10` ）从提取的 zip 复制到 `images` 文件夹，然后关闭 "文件资源管理器" 窗口。  将文件夹添加到 Visual Studio 项目 \ （在 "解决方案资源管理器" 中，右键单击 `images` 文件夹，然后**Add**  >  为每个文件夹选择 "添加**现有文件夹 ...** "）。  
    1.  从提取的 zip 中打开 \ （Visual Studio 或任何编辑器 \） `icons.json` 文件，并将该 `"icons": [...]` 数组复制到 `manifest.json` 项目文件中。  

1.  现在，你必须将 web 应用清单与你的应用相关联。  打开 `layout.pug` 文件 \ （在 `views` 文件夹 \ 中）进行编辑，并在样式表链接后立即添加此行。  \ （它只是节点[pug][PugAttributes]模板的速记形式 `<link rel='manifest' href='/manifest.json'>` \）。  
    
    ```html
    link(rel='manifest', href='/manifest.json')
    ```  
    
使用所有这些功能，你的 web 应用现在正在提供清单和主屏幕应用图标！  尝试运行应用程序 \ （ `F5` \）并加载清单。  

![从 localhost 加载的 Web 应用清单][ImageVsNodejsExpressManifest]  

和其中一个图标。  

![从 localhost 加载的 Square71x71Logo 应用徽标][ImageVsNodejsExpressIcon]  

如果你发布应用 live \ （具有实际的 `start_url` \），则 Bing 搜索引擎现在会将其标识为[可自动打包和提交到 Microsoft Store][PwaEdgehtmlMicrosoftStore]的候选项，作为可安装的 Windows 10 应用。  确保清单 json 文件包含[用于累进 Web 应用的质量信号][WindowsBlogsPwaEdge]，其中包含以下各项的必应扫描。   

*   `name`  
*   `description`  
*   至少一个图标 512px "平方" 或 "更大" \ （为了确保图像源的分辨率足以自动生成你的应用的初始屏幕，应用商店、磁贴图像等 \）。  

此外，使用[HTTPS](#https)、[服务工作者](#service-workers)以及遵守[Microsoft Store 策略][LegalWindowsAgrementsMicrosoftStorePolicies]。  

### HTTPS  

与服务工作者一起工作的[服务工作人员][MDNServiceWorkerApi]和其他关键 PWA 技术（如[缓存][MDNCache]、[推送][MDNPushApi]和[后台同步][MDNSyncManager]api \）仅在安全连接中工作，这意味着活动网站的[HTTPS][WikiHttps]或 `localhost` 用于调试的目的。  

如果你将[此 web 应用作为活动网站发布][VisualStudioNodejsTutorialPublishAzureAppService]\ （例如，通过设置[Azure 免费帐户][AzureCreateFreeAccount]\），则必须确保你的服务器配置了 HTTPS。  如果你使用[Microsoft Azure 应用服务][AzureWebApps]托管你的网站，则默认情况下它将通过 HTTPS 进行提供。  

对于本指南，请继续 `http://localhost` 将用作提供服务的活动网站的占位符 `https://` 。  

### 服务工作人员  

服务工作者是 PWAs 背后的关键技术。 服务工作人员充当你的 PWA 和网络之间的代理，使你的网站能够充当服务于脱机方案的已安装本机应用，响应服务器推送通知，并运行后台任务。  服务工作者还会打开新的性能策略。  你无需实现完整的 web 应用，即可为你的网站使用服务工作人员缓存来优化页面加载性能。  

服务工作线程是由 JavaScript 文件运行的事件驱动的后台线程，这些线程与为 web 应用供电的常规脚本一起提供。  由于服务工作人员不在主 UI 线程上运行，因此服务工作人员不具有 DOM 访问权限，尽管[UI 线程][MDNWorkerPrototypePostMessage]和[工作线程][MDNDedicatedWorkerGlobalScopePostMessage]能够使用 `postMessage()` 和 `onmessage` 事件处理程序进行通信。  

将服务工作者注册到你的应用，方法是将其注册到你的网站的 URL 源 \ （或其内部的指定路径 \）。  注册后，将在用户计算机上下载、安装和激活服务工作人员文件。  有关详细信息，MDN web 文档提供了有关[使用服务工作人员][MDNUsingServiceWorkers]和详细的[服务工作者 API][MDNServiceWorkerApi]参考的综合指南。  

对于本教程，请使用[PWA 生成器][PwaBuilderServiceWorker]上的脱机页面服务工作脚本。  开始自定义具有更多功能的脚本，具体取决于你的性能要求、网络带宽等。  查看由 Mozilla 提供的[服务工作人员手册][ServiceWorkerCookbook]，了解许多有用的服务工作人员缓存创意。  

1.  打开 [https://www.pwabuilder.com/serviceworker][PwaBuilderServiceWorker] 并选择 \ （默认 \）**脱机页面**服务工作人员，然后单击 "**下载服务工作人员**" 按钮。  
1.  打开下载文件夹并复制以下两个文件  

    *   ServiceWorker1\pwabuilder-sw-register.js  
    *   ServiceWorker1\pwabuilder-sw.js  
    
    将文件保存到 `public` Visual Studio web app 项目的文件夹中。  \ （从 Visual Studio 中，使用 `Ctrl` + `O` 将文件资源管理器打开到项目并导航到 `public` 文件夹 \）。  
    
    有必要查看这两个文件中的代码，以获取有关如何注册用于缓存指定页面的服务工作人员的 gist， `offline.html` 并在网络提取失败时提供服务。  接下来，创建一个简单 `offline.html` 页面作为应用的脱机功能的占位符。  
    
1.  在 "解决方案资源管理器" 中，打开 `views/layout.pug` 文件，然后在链接标记下方添加以下行。  
    
    ```html
    script(src='/pwabuilder-sw-register.js')
    ```  
    
    你的网站将加载并运行你的服务工作人员注册脚本。  
    
1.  在 "解决方案资源管理器" 中，右键单击该 `public` 文件夹，然后选择 "**添加**  >  **新文件 ...**"。 为其命名 `offline.html` ，然后添加一个 `<title>` 和部分正文内容，例如以下代码。  
    
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
    
1.  在 "解决方案资源管理器" 中，打开 `routes\index.js` 文件，然后在最后一个命令 \ （\）之前添加以下代码 `module.exports = router;` 。  
    
    ```javascript
    router.get('/offline.html', function (req, res) {
        res.sendFile('public/offline.html');
    });
    ```  
    
    这将指示你的应用为该文件提供服务 `offline.html` \ （当你的服务工作者为脱机缓存获取它时）。  
    
1.  测试你的 PWA！  生成 \ （ `Ctrl` + `Shift` + `B` \），运行 \ （ `F5` \）您的 web 应用以启动 Microsoft Edge 并打开您的 `localhost` 页面。  然后完成以下步骤。  
    
    1.  打开 Edge DevTools**控制台**\ （ `Ctrl` + `Shift` + `J` \），并验证服务工作人员是否已注册。  
    1.  在 "**调试器**" 面板中，展开 "**服务工作者**" 控件，然后单击您的来源。  在 "**服务工作人员概述**" 中，验证你的服务工作人员是否已激活并在运行。  
        
        ![Edge DevTools 服务工作者概览][ImageDevtoolsSwOverview]  
        
    1.  展开**缓存**控件并验证 `offline.html` 页面是否已缓存。  
        
        ![Edge DevTools 服务辅助缓存][ImageDevtoolsSwCache]  
        
1.  尝试将 PWA 作为脱机应用的时间！  在 Visual Studio 中，**停止调试**\ （ `Shift` + `F5` \）您的 web 应用，然后打开 Microsoft Edge \ （或刷新 \）到您的网站的本地登录地址。  现在应加载 `offline.html` 页面 \ （感谢你的服务工作者和脱机缓存 \）！  
    
    ![http://localhost:1337在 Microsoft Edge 中加载的 "脱机" html][ImageOfflineHtml]  

## 添加推送通知  

通过添加推送通知的客户端支持（使用[推送 api][MDNPushApi]订阅消息服务和[通知 API][MDNNotificationsApi]在接收消息时显示 toast 消息），让 PWA 更多应用。  与服务工作者一样，这些是基于标准的 Api，可跨浏览器使用，因此你只需编写一次代码即可在任何支持 PWAs 的地方工作。  在服务器端，使用[Web 推送][NPMWebPush]开放源代码库来处理向各种浏览器传递推送消息时所涉及的差异。  

以下各项适用于由 Mozilla 提供的[服务工作人员手册][ServiceWorkerCookbookPushRichDemo]中的 "推入大量演示"，它值得检查一下许多其他有用的 Web 推送和服务工作者食谱。  

### 步骤 1-安装 NPM web 推送库  

在 Visual Studio "解决方案资源管理器" 中，右键单击你的项目，然后**打开 Node.js 交互式窗口 ...**。 在其中键入以下代码。  

```javascript
.npm install web-push
```  

这将安装[Web 推送][NPMWebPush]库。  然后，打开 `index.js` 文件，并在其他要求语句后将以下行添加到文件顶部。  

```javascript
var webpush = require('web-push');
```  

### 步骤 2-为服务器生成 VAPID 项  

接下来，你必须为服务器生成 VAPID \ （自愿应用程序服务器标识 \）键，以将推送消息发送到 PWA 客户端。  您只需执行此操作 \ （即，服务器只需要一对 VAPID 键 \）。  在 node.js 交互式窗口中，键入以下代码。  

```javascript
var webpush = require('web-push');
webpush.generateVAPIDKeys();
```  

输出应产生一个包含公钥和私钥的 JSON 对象，该对象将复制到你的服务器逻辑中。  

在您 `index.js` 的文件中，在最后的 \ （ `module.exports = router` \）行之前添加以下代码。  

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

复制 `publicKey` `privateKey` 您刚生成的和值。  您也可以随意自定义 `mailto` 地址 \ （虽然不需要运行此示例 \）。  

如果你对 VAPID 和 WebPush 的工作原理的详细信息感兴趣，则[Mozilla Services 工程博客][MozillaServicesSendingVapidWebPushNotificationsPush]对和有很好的 explainer。  

### 步骤 3-处理与推送相关的服务器请求  

现在设置用于处理来自 PWA 客户端的推送相关请求的路由，包括提供 VAPID 公钥和注册客户端以接收推送。  

在实际方案中，推送通知可能源自服务器逻辑中的事件。  若要简化此处的操作，必须向 PWA 主页添加 "**推送通知**" 按钮，以便从我们的服务器生成推送，并使用 `/sendNotification` 终结点 \ （服务器路由 \）处理这些请求。  

在你的 `index.js` 文件中，在 [步骤 2] [#step-2 中添加的 VAPID 初始化代码后，附加以下路由，---生成-VAPID--------------服务器]。  

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

在 plumb 服务器端代码的情况下，在 PWA 客户端上的推送通知中进行。  

### 步骤 4-订阅推送通知  

作为 PWA 网络代理的角色的一部分，服务工作者处理推送事件和 toast 通知交互。  但是，与第一次设置 \ （或注册 \）服务工作者一样，在 PWA 的主 UI 线程上将 PWA 订阅到服务器推送通知，并且需要网络连接。  订阅推送通知需要活动的服务工作人员注册，因此必须首先验证服务工作人员是否已安装并处于活动状态，然后再尝试将其订阅到推送通知。  

在创建新推送订阅之前，Microsoft Edge 检查用户是否授予了 PWA 接收通知的权限。  如果不是，则浏览器会提示用户提供权限。  如果权限被拒绝，则请求 `registration.pushManager.subscribe` 引发 a `DOMException` ，因此你必须处理它。  有关权限管理的详细信息，请参阅[Microsoft Edge 中的推送通知][WindowsBlogsWebNotificationsEdge]。  

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

查看[PushManager][MDNPushManager]界面上的 MDN 文档和[Web 推送][NPMWebPushUsage]库上的 NPM 文档，以了解有关 api 如何工作以及各种相关选项的详细信息。  

### 步骤 5-设置推送和 notificationclick 事件处理程序  

设置了推送套餐后，剩余的工作将在服务工作人员中发生。  首先，你必须为服务器发送的推送事件设置处理程序，并使用 toast 通知 \ （如果授予权限 \）进行响应，从而显示推送数据负载。  接下来，为 toast 添加单击处理程序以关闭通知，并对当前打开的窗口的列表进行排序，以打开、焦点或打开所需的 PWA 客户端页面并对其进行焦点。  

在 `pwabuilder-sw.js` 文件中，附加以下处理程序。  

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

### 步骤 6-试用  

在 PWA 中测试推送通知的时间！  

1.  `F5`在浏览器中运行 \ （\）您的 PWA。  由于您修改了服务工作者代码 \ （ `pwabuilder-sw.js` \），因此必须打开 DevTools 调试程序 \ （\ `F12` ）到**服务工作者概述**面板，并**注销**服务工作人员并重新加载 \ （ `F5` \）页面以重新注册它 \ （或单击 "**更新**\"）。  在生产方案中，浏览器将定期检查服务工作人员更新并在后台安装更新。  应在此处强制执行立即结果。  
    
    当你的服务工作者激活并尝试将你的 PWA 订阅到推送通知时，你应该会在页面底部看到一个权限对话框。  
    
    ![用于启用通知的权限对话框][ImageNotificationPermission]  
    
    选择 **"是"** 为你的 PWA 启用 toast 通知。  
    
1.  在 "服务工作人员概述" 窗格中，尝试选择 "**下压**" 按钮。  应显示一个 toast 通知，其中包含 \ （具有硬编码的 "测试推送来自 DevTools" \）负载的消息。  
    
    ![推送来自 DevTools 的通知][ImageDevtoolsPush]  
    
1.  接下来，尝试在 PWA 的主页上选择 "**发送通知**" 按钮。  这次将显示来自服务器的负载的 toast。  
    
    ![推送来自 PWA 服务器的通知][ImagePwaPush]  
    
    如果您没有单击 "\" （或激活 \） toast 通知，它将在几秒钟后关闭，并在 Windows 操作中心上排队。  
    
    ![Windows 操作中心中的通知][ImageWindowsActionCenter]  
    
    你拥有 PWA 推送通知的基础知识。  在实际应用中，将以一种方式实现后续步骤，以管理和存储推送订阅以及正确地[加密][NPMWebPushEncrypt]通过线路发送的负载数据。  
    
## 深入探索  

本指南演示了渐进式 Web 应用和 Microsoft PWA 开发工具（包括 Visual Studio、PWA 生成器和 Edge DevTools）的基本解析。  

当然，还有很多其他内容，包括在此处阅读内容以外的内容，包括响应式设计、深度链接、[跨浏览器测试][BrowserStackTestEdgeBrowser]和其他[最佳做法][Webhint]\ （不要提及你的应用功能！ \），但希望本指南[让][PwaEdgehtmlIndexRequirements]你能够全面引入 PWA 基础知识和有关入门的一些想法。  如果在使用 Windows 或 Visual Studio 的 PWA 开发中还有其他问题，请留下评论！  

查看其他 PWA 指南以了解如何提高客户的参与并提供更流畅的操作系统集成的应用体验。  

*   [Windows 定制][PwaEdgehtmlWindowsFeatures]。 使用简单的功能检测，你可以通过本机 Windows 运行时 \ （WinRT \） Api 为 Windows 10 客户逐步增强 PWA，例如用于自定义 Windows**开始**菜单磁贴通知和任务栏 jumplists 的 PWA，以及处理用户资源（如照片、音乐和日历）的权限。  
*   [Microsoft Store 中的 PWAs][PwaEdgehtmlMicrosoftStore]。  了解有关应用商店分发的优点以及如何提交 PWA 的详细信息。  

## 另请参阅  

*   [MDN web 文档上的渐进式 Web 应用][MDNProgressiveWebApps]-有关渐进式 web 应用的绝佳指南。  
*   Web[上的渐进式 Web 应用。适用][WebDevProgressiveWebApps]于渐进式 web 应用的优秀指南。  
*   [渐进式 Web 应用 rocks][ProgressiveWebApps]展示 PWAs 的真实示例。  
*   [作为渐进 Web 应用的黑客新闻阅读器][HackerNewsProgressiveWebApps]-比较不同的框架和性能模式，用于实现示例 \ （黑客新闻阅读器 \） PWA。  

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

[PwaEdgehtmlIndexRequirements]: ../progressive-web-apps-edgehtml/index.md#requirements "要求-渐进式 Web 应用 \ （EdgeHTML \） Windows"  
[PwaEdgehtmlMicrosoftStore]: ../progressive-web-apps-edgehtml/microsoft-store.md "Microsoft Store 中的渐进式 Web 应用 \ （EdgeHTML \）"  
[PwaEdgehtmlWindowsFeatures]: ../progressive-web-apps-edgehtml/windows-features.md "为 Windows 定制 PWA \ （EdgeHTML \）"  

[LegalWindowsAgrementsMicrosoftStorePolicies]: /legal/windows/agreements/store-policies "Microsoft 应用商店政策 |Microsoft 文档"  

[VisualStudioNodeJsTutorial]: /visualstudio/nodejs/tutorial-nodejs "教程：在 Visual Studio 中创建 node.js 和 Express 应用 |Microsoft 文档"  
[VisualStudioNodejsTutorialPublishAzureAppService]: /visualstudio/nodejs/tutorial-nodejs#optional-publish-to-azure-app-service "发布到 Azure 应用服务-在 Visual Studio 中创建 node.js 和 Express 应用 |Microsoft 文档"  

[WindowsUwpGetStartedWhat]: /windows/uwp/get-started/whats-a-uwp "什么是通用 Windows 平台 \ （UWP）应用？ |Microsoft 文档"  

[AzureCreateFreeAccount]: https://azure.microsoft.com/free "创建 Azure 免费帐户 |Microsoft Azure"  
[AzureWebApps]: https://azure.microsoft.com/services/app-service/web "Web Apps |Microsoft Azure"  

<!--[DeveloperEdgeToolsRemote]: https://developer.microsoft.com/microsoft-edge/tools/remote/ "page not found"  -->  

[WindowsBlogsPwaEdge]: https://blogs.windows.com/msedgedev/2018/02/06/welcoming-progressive-web-apps-edge-windows-10/#4UOdrDJj3124VIkc.97 "将渐进式 Web 应用的欢迎应用到 Microsoft Edge 和 Windows 10 |Windows 博客"  
[WindowsBlogsWebNotificationsEdge]: https://blogs.windows.com/msedgedev/2016/05/16/web-notifications-microsoft-edge#UAbvU2ymUlHO8EUV.97 "Microsoft Edge 中的 Web 通知 |Windows 博客"  

[VisualStudioDownloads]: https://www.visualstudio.com/downloads "下载 |Visual Studio"  
[VisualStudioFree]: https://visualstudio.microsoft.com/free-developer-offers "免费的开发人员软件 & 服务 |Visual Studio"  
[VisualStudioPreview]: https://www.visualstudio.com/vs/preview "Visual Studio 预览版"  

[BrowserStackTestEdgeBrowser]: https://www.browserstack.com/test-on-microsoft-edge-browser "Windows 10 上的免费 Microsoft Edge 浏览器测试 |BrowserStack"  

[HackerNewsProgressiveWebApps]: https://hnpwa.com "作为渐进式 Web 应用的黑客新闻阅读器"  

[MDNCache]: https://developer.mozilla.org/docs/Web/API/Cache "缓存 |MDN"  
[MDNDedicatedWorkerGlobalScopePostMessage]: https://developer.mozilla.org/docs/Web/API/DedicatedWorkerGlobalScope/postMessage "DedicatedWorkerGlobalScope postMessage \ （\） |MDN"  
[MDNNotificationsApi]: https://developer.mozilla.org/docs/Web/API/Notifications_API "通知 API |MDN"  
[MDNProgressiveWebApps]: https://developer.mozilla.org/Apps/Progressive "渐进式 web 应用 \ （PWAs） |MDN"  
[MDNPushApi]: https://developer.mozilla.org/docs/Web/API/Push_API "推送 API |MDN"  
[MDNPushManager]: https://developer.mozilla.org/docs/Web/API/PushManager "PushManager |MDN"  
[MDNServiceWorkerApi]: https://developer.mozilla.org/docs/Web/API/Service_Worker_API "服务工作者 API |MDN"  
[MDNSyncManager]: https://developer.mozilla.org/docs/Web/API/SyncManager "SyncManager |MDN"  
[MDNUsingServiceWorkers]: https://developer.mozilla.org/docs/Web/API/Service_Worker_API/Using_Service_Workers "使用服务工作者 |MDN"  
[MDNWebAppManifest]: https://developer.mozilla.org/docs/Web/Manifest "Web App 清单 |MDN"  
[MDNWorkerPrototypePostMessage]: https://developer.mozilla.org/docs/Web/API/Worker/postMessage "PostMessage \ （\） |MDN"  

[MozillaServicesSendingVapidWebPushNotificationsPush]: https://blog.mozilla.org/services/2016/08/23/sending-vapid-identified-webpush-notifications-via-mozillas-push-service "通过 Mozilla 的推送服务发送 VAPID 标识的 WebPush 通知 |Mozilla 服务"  

[NPMWebPush]: https://www.npmjs.com/package/web-push "web-推送 |npm"  
[NPMWebPushEncrypt]: https://www.npmjs.com/package/web-push#encryptuserpublickey-userauth-payload-contentencoding "加密（userPublicKey、userAuth、负载、contentEncoding）-web 推送 |NPM"  
[NPMWebPushUsage]: https://www.npmjs.com/package/web-push#usage "使用情况-web 推送 |NPM"  

[ProgressiveWebApps]: https://pwa.rocks "渐进式 Web 应用"  

[PugAttributes]: https://pugjs.org/language/attributes.html "属性 |Pug"  

[PwaBuilder]: https://www.pwabuilder.com "PWA 生成器"  
[PwaBuilderAppImageGenerator]: https://www.pwabuilder.com/imageGenerator "应用图像生成器"  
[PwaBuilderServiceWorker]: https://www.pwabuilder.com/serviceworker "服务工作人员 |PWA 生成器"  

[ServiceWorkerCookbook]: https://serviceworke.rs "ServiceWorker 手册"  
[ServiceWorkerCookbookPushRichDemo]: https://serviceworke.rs/push-rich_demo.html "推送丰富的演示 |ServiceWorker 手册"  

[W3cWebAppManifest]: https://www.w3.org/TR/appmanifest "Web App 清单 |W3C"  

[Webhint]: https://sonarwhal.com "webhint，web 最佳做法的提示引擎" 
 
[MDNWebWorkers]: https://developer.mozilla.org/docs/Web/API/Web_Workers_API/Using_web_workers "使用 Web 工作人员" 

[WebDevProgressiveWebApps]: https://developers.google.com/web/progressive-web-apps "渐进式 Web 应用 |web 开发"  

[WikiHttps]: https://en.wikipedia.org/wiki/HTTPS "HTTPS |科"  
[WikiProgressiveEnhancement]: https://en.wikipedia.org/wiki/Progressive_enhancement "渐进式增强 |科"  
