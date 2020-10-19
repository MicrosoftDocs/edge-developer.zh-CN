---
description: 使用内容脚本在页面正文标记下方动态插入 NASA 图片
title: 创建扩展教程第 2 部分
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/15/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium、web 开发、html、css、javascript、开发人员、扩展
ms.openlocfilehash: 755b70635c93d7331ef3ac985625ba7ac5689679
ms.sourcegitcommit: 845a0d53a86bee3678f421adee26b3372cefce57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/08/2020
ms.locfileid: "11104712"
---
# 创建扩展教程第 2 部分  
  
[此部件的已完成扩展程序包源][ArchiveExtensionGettingStartedPart2]    

## 概述  

本教程介绍以下扩展技术。
*   将 JavaScript 库注入扩展  
*   向浏览器选项卡公开扩展资源  
*   在现有浏览器选项卡中包括内容页  
*   让内容页侦听来自弹出窗口的消息并进行响应  

你将了解如何更新你的弹出菜单，以使用标题和标准 HTML 按钮替换静态开始图像。  选中此按钮后，会将该星形图像（嵌入在扩展中）传递到内容页面。  该图像将插入到活动浏览器选项卡中。有关详细信息，请按照以下步骤进行操作。

1.  从弹出窗口中删除图像，并将其替换为按钮  

首先， `popup.html` 使用显示标题和按钮的一些直接向前标记更新你的文件。  你将很快对该按钮进行编程，但现在，只需包含对空 JavaScript 文件的引用 `popup.js` 。  下面是更新 HTML。  

```html
<html>
    <head>
        <meta charset="utf-8" />
        <style>
            body {
                width: 500px;
            }
            button {
                background-color: #336dab;
                border: none;
                color: white;
                padding: 15px 32px;
                text-align: center;
                font-size: 16px;
            }
        </style>
    </head>
    <body>
        <h1>Show the NASA picture of the day</h1>
        <h2>(select the image to remove)</h2>
        <button id="sendmessageid">Display</button>
        <script src="popup.js"></script>
    </body>
</html>
```  

更新并打开扩展后，将打开一个显示 "显示" 按钮的弹出窗口。  

:::image type="complex" source="./media/part2-popupdialog.png" alt-text="按下 &quot;扩展&quot; 图标后，popup.html 显示":::
   按下 &quot;扩展&quot; 图标后，popup.html 显示
:::image-end:::

<!--![popup.html display after pressing the Extension icon][ImagePart2Popupdialog]  -->  

2.  在浏览器选项卡顶部显示图像的更新策略  

添加按钮后，下一任务是使其 `images/stars.jpeg` 在活动选项卡页顶部打开图像文件。  

请记住，每个选项卡页都在其自己的线程中运行。 此外，该扩展还使用另一个线程。  首先，创建一个插入到选项卡页中的内容脚本。  然后，从弹出窗口发送一条消息，直到在选项卡页上运行该内容脚本。 内容脚本接收消息，该消息描述应显示哪个图像。  

3. 创建弹出 JavaScript 以发送消息  

首先，创建 `popup/popup.js` 并添加代码，以便向尚未创建的内容脚本发送邮件，您必须立即创建并插入到浏览器选项卡。 为此，以下代码将 `onclick` 事件添加到弹出的 &quot;显示" 按钮。  

```javascript
const sendMessageId = document.getElementById("sendmessageid");
if (sendMessageId) {
  sendMessageId.onclick = function() {
    // do something
  };
}
```  

在 `onclick` 事件中，找到 "当前浏览器" 选项卡。 然后，使用 `chrome.tabs.sendmessage` 扩展 API 将消息发送到该选项卡。  

在该消息中，必须包含要显示的图像的 URL。 此外，还应发送一个唯一的 ID 以分配给插入的图像。  你可以选择让内容插入 JavaScript 生成该内容，但对于稍后变得明显的原因，在此处生成唯一 ID `popup.js` 并将其传递给尚未创建的内容脚本。  

以下代码片段概述了更新的代码 `popup/popup.js` 。  此外，传递当前的选项卡 ID，本文稍后部分将使用该 ID。  

```javascript
const sendMessageId = document.getElementById("sendmessageid");
if (sendMessageId) {
    sendMessageId.onclick = function() {
        chrome.tabs.query({ active: true, currentWindow: true }, function(tabs) {
            chrome.tabs.sendMessage(
                tabs[0].id,
                {
                    url: chrome.extension.getURL("images/stars.jpeg"),
                    imageDivId: `${guidGenerator()}`,
                    tabId: tabs[0].id
                },
                function(response) {
                    window.close();
                }
            );
            function guidGenerator() {
                const S4 = function () {
                    return (((1 + Math.random()) * 0x10000) | 0).toString(16).substring(1);
                };
                return (S4() + S4() + "-" + S4() + "-" + S4() + "-" + S4() + "-" + S4() + S4() + S4());
            }
        });
    };
}
```  

4. 让您的星从任何浏览器选项卡中可用  

你可能会想知道，在传递时 `images/stars.jpeg` 必须使用 `chrome.extension.getURL` CHROME 扩展 API，而不是仅在没有额外前缀的情况下传递相对 URL，如上一节中所示。  顺便说一下，附加的前缀由附加的 `getUrl` 图像所返回，其外观类似于以下内容。  

```http
extension://inigobacliaghocjiapeaaoemkjifjhp/images/stars.jpeg
```  

原因是您要使用元素的属性将图像插入 `src` `img` 到内容页面。  内容页面在与运行扩展的线程不同的唯一线程上运行。  必须将静态图像文件作为 web 资产公开才能正常工作。  

在文件中添加其他条目 `manifest.json` 以声明图像可用于所有浏览器选项卡。  该条目如下所示 \ (`manifest.json` 当您添加即将出现的内容脚本声明时，请在下面的完整文件中看到该条目： \ ) 。  

```json
"web_accessible_resources": [
    "images/*.jpeg"
]
```  

现在，你已在文件中写入代码 `popup.js` ，以向嵌入当前活动选项卡页上的内容页发送消息，但尚未创建和注入该内容页面。  立即执行此操作。  

5.  更新内容和 web 访问的 manifest.js  

`manifest.json`包括的和的更新 `content-scripts` `web_accessible_resources` 如下所示。  

```json
{
    "name": "NASA picture of the day viewer",
    "version": "0.0.0.1",
    "manifest_version": 2,
    "description": "A Chromium extension to show the NASA picture of the day.",
    "icons": {
        "16": "icons/nasapod16x16.png",
        "32": "icons/nasapod32x32.png",
        "48": "icons/nasapod48x48.png",
        "128": "icons/nasapod128x128.png"
    },
    "browser_action": {
        "default_popup": "popup/popup.html"
    },
    "content_scripts": [
        {
            "matches": [
              "<all_urls>"
            ],
            "js": ["lib/jquery.min.js","content-scripts/content.js"]
        }
    ],
    "web_accessible_resources": [
        "images/*.jpeg"
    ]
}
```  

你添加的分区是 `content_scripts` 。  该 `matches` 属性设置为 `<all_urls>` ，这意味着 `content_scripts` 当加载每个选项卡时，中的所有文件都插入到所有浏览器选项卡页面中。  可注入的允许文件类型为 JavaScript 和 CSS。  您还添加了 `libjquery.min.js` 。  你可以从本部分顶部提及的下载中包含该内容。  

6. 添加 jQuery 并了解关联的线程  

在要插入的内容脚本中，使用 jQuery \ (`$` \ ) 进行计划。  你添加了一个 minified 版本的 jQuery，并将其放入你的扩展程序包中 `lib\jquery.min.js` 。  这些内容脚本在单个沙盒中运行，这意味着插入到页面中的 jQuery `popup.js` 不会与内容共享。  

请记住，即使浏览器选项卡在加载的网页上运行了 JavaScript，任何插入的内容也不会有访问权限。  所注入的 JavaScript 只对在该浏览器选项卡中加载的实际 DOM 具有访问权限。  

7. 添加内容脚本消息侦听器  

此处是 `content-scripts\content.js` 基于你的分区将其插入到每个浏览器选项卡页中的文件 `manifest.json` `content-scripts` 。  

```javascript
chrome.runtime.onMessage.addListener(function(request, sender, sendResponse) {
    $("body").prepend(
        `<img  src="${request.url}" id="${request.imageDivId}"
               class="slide-image" /> `
    );
    $("head").prepend(
        `<style>
          .slide-image {
              height: auto;
              width: 100vw;
          }
        </style>`
    );
    $(`#${request.imageDivId}`).click(function() {
        $(`#${request.imageDivId}`).remove(`#${request.imageDivId}`);
    });
    sendResponse({ fromcontent: "This message is from content.js" });
});
```  

请注意，上述所有 JavaScript 都是 `listener` 使用 `chrome.runtime.onMessage.addListener` 扩展 API 方法注册 a。  此侦听器将等待你从 `popup.js` 前面介绍的带有扩展 API 方法的消息（如你发送给它的消息） `chrome.tabs.sendMessage` 。  

该方法的第一个参数 `addListener` 是一个函数，其第一个参数请求是正在传入的消息的详细信息。  请记住，在 `popup.js` 使用 `sendMessage` 方法时，第一个参数的这些属性是 `url` 和 `imageDivId` 。  

当侦听器处理事件时，将运行第一个参数的函数。  该函数的第一个参数是具有分配的属性的对象 `sendMessage` 。  该函数只处理三个 jQuery 脚本行。  

*   第一个脚本行将动态插入 **\<style\>** 必须作为类分配给你的元素的一个分区 `slide-image` `img` 。  
*   第二个脚本行在 `img` "浏览器" 选项卡下的 "浏览器" 选项卡的下方附加一个元素 `body` ，该元素具有 `slide-image` 分配给该类的类以及 `imageDivId` 作为该图像元素的 ID。  
*   第三个脚本行添加了一个 `click` 事件，该事件涵盖整个图像，允许用户选择图像上的任意位置，并且该图像将从页面 \ (中删除，同时它是事件侦听器 \ ) 。  

8. 添加功能以在选定时删除显示的图像  

现在，当您浏览到任意页面并选择您的 **扩展名** 图标时，弹出菜单显示如下。  

:::image type="complex" source="./media/part2-popupdialog.png" alt-text="按下 &quot;扩展&quot; 图标后，popup.html 显示":::
   按下 &quot;扩展&quot; 图标后，popup.html 显示
:::image-end:::

<!--![popup.html display after pressing the Extension icon][ImagePart2Popupdialog]  -->  

2.  在浏览器选项卡顶部显示图像的更新策略  

添加按钮后，下一任务是使其 `images/stars.jpeg` 在活动选项卡页顶部打开图像文件。  

请记住，每个选项卡页都在其自己的线程中运行。 此外，该扩展还使用另一个线程。  首先，创建一个插入到选项卡页中的内容脚本。  然后，从弹出窗口发送一条消息，直到在选项卡页上运行该内容脚本。 内容脚本接收消息，该消息描述应显示哪个图像。  

3. 创建弹出 JavaScript 以发送消息  

首先，创建 `popup/popup.js` 并添加代码，以便向尚未创建的内容脚本发送邮件，您必须立即创建并插入到浏览器选项卡。 为此，以下代码将 `onclick` 事件添加到弹出的 &quot;显示" 图标后，popup.html 显示
:::image-end:::

<!--![popup.html display after pressing the Extension icon][ImagePart2Popupdialog]  -->  

选择该按钮后 `Display` ，将获得以下内容。  如果选择图像上的任意位置 `stars.jpeg` ，则会删除该图像元素，并且选项卡页将折叠为最初显示的内容。  

:::image type="complex" source="./media/part2-showingimage.png" alt-text="按下 &quot;扩展&quot; 图标后，popup.html 显示":::
   按下 &quot;扩展&quot; 图标后，popup.html 显示
:::image-end:::

<!--![popup.html display after pressing the Extension icon][ImagePart2Popupdialog]  -->  

2.  在浏览器选项卡顶部显示图像的更新策略  

添加按钮后，下一任务是使其 `images/stars.jpeg` 在活动选项卡页顶部打开图像文件。  

请记住，每个选项卡页都在其自己的线程中运行。 此外，该扩展还使用另一个线程。  首先，创建一个插入到选项卡页中的内容脚本。  然后，从弹出窗口发送一条消息，直到在选项卡页上运行该内容脚本。 内容脚本接收消息，该消息描述应显示哪个图像。  

3. 创建弹出 JavaScript 以发送消息  

首先，创建 `popup/popup.js` 并添加代码，以便向尚未创建的内容脚本发送邮件，您必须立即创建并插入到浏览器选项卡。 为此，以下代码将 `onclick` 事件添加到弹出的 &quot;显示"  
