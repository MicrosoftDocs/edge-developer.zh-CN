---
description: 使用内容脚本在页面正文标记下方动态插入 "版"
title: 创建扩展教程第 2 部分
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium， Web 开发， html， css， javascript， 开发人员， 扩展
ms.openlocfilehash: 48af14c33a368a3449acb88b4dfb875ad5398e7a
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11397914"
---
# <a name="create-an-extension-tutorial-part-2"></a>创建扩展教程第 2 部分  
  
[此部件已完成的扩展包源][ArchiveExtensionGettingStartedPart2]    

## <a name="overview"></a>概述  

本教程介绍以下扩展技术。
*   将 JavaScript 库注入扩展  
*   向浏览器选项卡公开扩展资源  
*   将内容页包含到现有浏览器选项卡中  
*   让内容页侦听弹出窗口中的邮件并做出响应  

你将了解如何更新弹出菜单，以将静态启动图像替换为标题和标准 HTML 按钮。  选中该按钮时，会将嵌入扩展中的星形图像传递给内容页。  该图像将插入到活动的浏览器选项卡中。请按照以下步骤了解更多详细信息。

1.  从弹出窗口中删除图像，并将其替换为按钮  

首先，使用显示标题和按钮的直接标记 `popup.html` 更新文件。  你很快就会对按钮进行编程，但现在只需包含对空 JavaScript 文件的引用 `popup.js` 。  下面是更新 HTML。  

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

更新并打开扩展后，将打开一个弹出窗口，并显示一个显示按钮。  

:::image type="complex" source="./media/part2-popupdialog.png" alt-text="popup.htm扩展图标后显示":::
   popup.htm扩展图标后显示
:::image-end:::

<!--![popup.html display after selecting the Extension icon][ImagePart2Popupdialog]  -->  

2.  更新策略以在浏览器选项卡顶部显示图像  

添加按钮后，下一个任务是使其在活动选项卡页顶部显示 `images/stars.jpeg` 图像文件。  

请记住，每个选项卡页在其自己的线程中运行。 此外，扩展使用不同的线程。  首先，创建插入选项卡页的内容脚本。  然后，从弹出窗口向选项卡页上运行的内容脚本发送邮件。 内容脚本收到消息，其中描述了应显示的图像。  

3. 创建弹出式 JavaScript 以发送消息  

首先，创建并添加代码，以向尚未创建的内容脚本发送消息，您必须立即创建该脚本并将其注入 `popup/popup.js` 浏览器选项卡。 为此，以下代码将 `onclick` 事件添加到弹出式显示按钮。  

```javascript
const sendMessageId = document.getElementById("sendmessageid");
if (sendMessageId) {
  sendMessageId.onclick = function() {
    // do something
  };
}
```  

In the `onclick` event， find the current browser tab. 然后，使用 `chrome.tabs.sendmessage` 扩展 API 向该选项卡发送消息。  

在该消息中，必须包含要显示的图像的 URL。 此外，发送要分配给插入图像的唯一 ID。  您可以选择让内容插入 JavaScript 生成该 ID，但出于稍后显而易见的原因，请在此处生成该唯一 ID，并传递给尚未创建的内容 `popup.js` 脚本。  

以下代码段概述了 中更新的代码 `popup/popup.js` 。  此外，请传递当前选项卡 ID，这将在本文的稍后部分使用。  

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

4. 从任何浏览器选项卡提供你的星形.jpeg  

你可能想知道为什么在传递 时必须使用部件版式扩展 API，而不是像上一节一样仅传递不带额外前缀 `images/stars.jpeg` `chrome.extension.getURL` 的相对 URL。  另外，附加了图像返回的额外前缀如下所示 `getUrl` 。  

```http
extension://inigobacliaghocjiapeaaoemkjifjhp/images/stars.jpeg
```  

原因是你使用 元素的 属性将图像 `src` `img` 注入内容页面。  内容页在运行扩展的线程不同的唯一线程上运行。  必须将静态图像文件公开为 Web 资产，它必须能够正常工作。  

在文件中添加另 `manifest.json` 一项以声明该图像可供所有浏览器选项卡使用。  添加内容脚本声明时， (在下面的完整文件中看到该条目，如下所示 `manifest.json` \) 。  

```json
"web_accessible_resources": [
    "images/*.jpeg"
]
```  

现在，你已在你的文件中编写代码，以向嵌入在当前活动选项卡页上的内容页发送消息，但是尚未创建和注入 `popup.js` 该内容页。  现在执行。  

5.  更新manifest.js和 Web 访问的"打开"  

包括 `manifest.json` 和 `content-scripts` `web_accessible_resources` 的更新如下所示。  

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

您添加的节是 `content_scripts` 。  属性设置为 ，这意味着在加载每个选项卡时，所有文件将注入 `matches` `<all_urls>` `content_scripts` 所有浏览器选项卡页。  允许注入的文件类型为 JavaScript 和 CSS。  还添加了 `libjquery.min.js` 。  你可以从部分顶部提到的下载中包括该内容。  

6. 添加 jQuery 并理解关联的线程  

在你要注入的内容脚本中，计划使用 jQuery \ (`$` \) 。  你添加了 jQuery 的缩小版本，并作为 放入扩展包 `lib\jquery.min.js` 中。  这些内容脚本在单个沙盒中运行，这意味着注入到页面中的 jQuery `popup.js` 不会与内容共享。  

请记住，即使浏览器选项卡上的 JavaScript 在加载的网页上运行，注入的任何内容也无法访问它。  注入的 JavaScript 仅有权访问该浏览器选项卡中加载的实际 DOM。  

7. 添加内容脚本消息侦听器  

下面是根据 `content-scripts\content.js` 你的部分注入到每个浏览器选项卡页 `manifest.json` `content-scripts` 的文件。  

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

请注意，上述 JavaScript 所执行的所有操作都是使用 `listener` 扩展 `chrome.runtime.onMessage.addListener` API 方法注册 。  此侦听器等待使用扩展 API 方法从前面所述的消息 `popup.js` 发送的消息 `chrome.tabs.sendMessage` 。  

方法的第一个参数是一个函数，其第一个参数 request 是 `addListener` 传入的消息的详细信息。  请记住， `popup.js` 在 使用 方法时，第一个参数 `sendMessage` 的这些属性是 和 `url` `imageDivId` 。  

当侦听器处理事件时，将运行作为第一个参数的函数。  该函数的第一个参数是属性由 分配的对象 `sendMessage` 。  该函数只处理三个 jQuery 脚本行。  

*   第一个脚本行将一个必须作为类分配给元素的节动态插入到 DOM **\<style\>** `slide-image` 标头 `img` 中。  
*   第二个脚本行在浏览器选项卡的 正下方追加一个元素，该元素分配了 类，并将 `img` `body` 作为该 `slide-image` `imageDivId` 图像元素的 ID。  
*   第三个脚本行添加一个涵盖整个图像的事件，允许用户选择图像上的任意位置，并且该图像将从页面 \ (以及事件侦听器 `click` \) 。  

8. 添加功能以在选中时删除显示的图像  

现在，当您浏览到任何页面 **并选择扩展图标** 时，弹出菜单将显示如下。  

:::image type="complex" source="./media/part2-popupdialog.png" alt-text="popup.htm扩展图标后显示":::
   popup.htm扩展图标后显示
:::image-end:::

<!--![popup.html display after selecting the Extension icon][ImagePart2Popupdialog]  -->  

选择该按钮 `Display` 时，将获取下面的内容。  如果在图像上的任意位置选择，该图像元素将被删除，选项卡页折叠 `stars.jpeg` 回最初显示的内容。  

:::image type="complex" source="./media/part2-showingimage.png" alt-text="在浏览器中显示的图像":::
   在浏览器中显示的图像
:::image-end:::

你已创建一个扩展，该扩展从扩展图标弹出窗口成功发送消息，并动态插入作为浏览器选项卡上的内容运行的 JavaScript。 注入的内容设置图像元素以显示静态星形 jpeg。  

<!-- image links -->  


<!-- links -->  

[ArchiveExtensionGettingStartedPart2]: https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/extension-getting-started-part2/extension-getting-started-part2 "已完成的扩展包源|Microsoft Docs"  
