---
description: 扩展入门第2部分
title: 使用内容脚本在页面正文标记下方动态插入 NASA 图片
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/15/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium、web 开发、html、css、javascript、开发人员、扩展
ms.openlocfilehash: fd2276c069116a7f69f06ae50f201e284b60f3ea
ms.sourcegitcommit: 744e2ecf42bcc427ae33e5dadbf6cd48ee0ab6a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2020
ms.locfileid: "11016727"
---
# 使用内容脚本在页面正文标记下方动态插入 NASA 图片  

<!--  
[Completed Extension Package Source for This Part][ArchiveExtensionGettingStartedPart2]  
-->  

## 概述  

在第2部分中，你将了解如何更新你的弹出菜单，使其不显示你以前拥有的静态星图像，但将该图像替换为 "标题" 和 "标准 HTML" 按钮。  选中此按钮后，会将该星形图像（嵌入在扩展中）传递到内容页面。  该图像将插入到活动浏览器选项卡中。  

*   本指南中介绍的扩展技术  
    *   将 JavaScript 库注入扩展  
    *   向浏览器选项卡公开扩展资源  
    *   在现有浏览器选项卡中包括内容页  
    *   让内容页侦听来自弹出窗口的消息并进行响应  

## 从弹出窗口中删除图像，并将其替换为按钮  

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
        <h1>Show the NASA Picture of the Day</h1>
        <h2>(select the image to remove)</h2>
        <button id="sendmessageid">Display</button>
        <script src="popup.js"></script>
    </body>
</html>
```  

更新您的扩展并选择 "扩展启动" 图标后，"具有以下弹出窗口" 包含 "显示" 按钮。  

:::image type="complex" source="./media/part2-popupdialog.png" alt-text="按下 "扩展" 图标后，popup.html 显示":::
   按下 "扩展" 图标后，popup.html 显示
:::image-end:::

<!--![popup.html display after pressing the Extension icon][ImagePart2Popupdialog]  -->  

## 在浏览器选项卡顶部显示图像的已更新策略  

添加按钮后，下一任务是使其 `images/stars.jpeg` 在活动选项卡页顶部打开图像文件。  

请记住，每个选项卡页都具有唯一的线程，并且扩展具有单独的线程。  因此，必须首先创建内容脚本，并将该内容脚本插入到选项卡页中。  执行此操作后，你必须从弹出窗口发送一条消息，告知该内容脚本在选项卡页上运行，指示内容脚本要显示的图像以及如何显示。  

## 创建弹出 JavaScript 以发送消息  

首先，创建 `popup/popup.js` 并添加代码，以便向尚未创建的内容脚本发送邮件，您必须立即创建并插入到浏览器选项卡。 为此，以下代码将 `onclick` 事件添加到弹出的 "显示" 按钮。  

```javascript
const sendMessageId = document.getElementById("sendmessageid");
if (sendMessageId) {
  sendMessageId.onclick = function() {
    // do something
  };
}
```  

在此 `onclick` 事件中，你必须执行的操作是查找当前浏览器选项卡 \ (如果只有一个打开的浏览器选项卡，则它是一个 \ ) 。  然后，找到该选项卡后，使用 `chrome.tabs.sendmessage` 扩展 API 将消息发送到该选项卡。  

在该消息中，你必须包含要显示的图像的 URL，并且你希望发送应分配给插入的图像的唯一 ID。  你可以选择让内容插入 JavaScript 生成该内容，但对于稍后变得明显的原因，在此处生成唯一 ID `popup.js` 并将其传递给尚未创建的内容脚本。  

下面是您的更新 `popup/popup.js` 文件。  此外，还不会使用您在后面的部分中应该需要的当前选项卡 ID。  

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

## 用任何浏览器选项卡提供 jpeg。  

你可能会想知道，在传递时 `images/stars.jpeg` 必须使用 `chrome.extension.getURL` CHROME 扩展 API，而不是仅在没有额外前缀的情况下传递相对 URL，如上一节中所示。  顺便说一下，附加的前缀由附加的 `getUrl` 图像所返回，其外观类似于以下内容。  

```http
extension://inigobacliaghocjiapeaaoemkjifjhp/images/stars.jpeg
```  

原因是使用元素的属性将图像插入 `src` `img` 内容页面。  内容页面在与运行扩展的线程不同的唯一线程上运行。  必须将静态图像文件作为 web 资产公开才能正常工作。  

若要执行此操作，必须在文件中添加其他条目 `manifest.json` 。  必须声明可从任何浏览器选项卡访问的图像。 该条目如下所示 \ (`manifest.json` 当您添加即将出现的内容脚本声明时，请在下面的完整文件中看到该条目： \ ) 。  

```json
"web_accessible_resources": [
    "images/*.jpeg"
]
```  

现在，你已在文件中写入代码 `popup.js` ，以便向嵌入当前活动选项卡页上的内容页发送消息，但尚未创建和注入该内容页面。  立即执行此操作。  

## 更新内容和 web 访问的 manifest.js  

`manifest.json`包括的和的更新 `content-scripts` `web_accessible_resources` 如下所示。  

```json
{
    "name": "NASA Picture of the day viewer",
    "version": "0.0.0.1",
    "manifest_version": 2,
    "description": "A Chromium Extension to show the NASA Picture of the Day.",
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

你添加的分区是 `content_scripts` 。  属性 `matches` 设置为 `<all_urls>` 表示在加载每个文件时，" **content_scripts** " 部分中提及的所有文件都插入到所有浏览器选项卡页面中。  可在此处注入的允许文件类型有 javascript 和 css。  您还添加了 `libjquery.min.js` 。  你可以从本部分顶部提及的下载中包含该内容。  

## 添加 jQuery 并了解关联的线程  

在您要插入的内容脚本中，请使用 jQuery \ (`$` \ ) 进行计划。  你添加了一个 minified 版本的 jQuery，并将其放入你的扩展程序包中 `lib\jquery.min.js` 。  这些内容脚本在排序的单个沙箱中运行，这意味着插入到页面中的 jQuery 不 `popup.js` 会与内容共享。  

请记住，即使浏览器选项卡在加载的网页上运行了 JavaScript，任何插入的内容都不具有访问权限。  所注入的 JavaScript 只对在该浏览器选项卡中加载的实际 DOM 具有访问权限。  

## 添加内容脚本消息侦听器  

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

*   第一次动态地插入到 DOM 标头中 **\<style\>** 必须作为 `slide-image` 类分配给你的元素的部分 `img` 。  
*   第二个元素将在 " `img` 浏览器" 选项卡的下方附加一个元素， `body` 该选项卡具有 `slide-image` 指定的类以及 `imageDivId` 作为该图像元素的 ID。  
*   第三个示例添加一个 `click` 事件，其中包含整个图像，允许用户选择图像上的任何位置，并且该图像将从页面 \ (中删除，并且该图像是事件侦听器 \ ) 。  

## 添加功能以在选定时删除显示的图像  

现在，当您浏览到任意页面并选择您的 **扩展名** 图标时，弹出菜单显示如下。  

:::image type="complex" source="./media/part2-popupdialog.png" alt-text="按下 "扩展" 图标后，popup.html 显示":::
   按下 "扩展" 图标后，popup.html 显示
:::image-end:::

<!--![popup.html display after pressing the Extension icon][ImagePart2Popupdialog]  -->  

选择该按钮后 `Display` ，将获得以下内容。  如果选择图像上的任意位置 `stars.jpeg` ，则会删除该图像元素，并且选项卡页将折叠为最初显示的内容。  

:::image type="complex" source="./media/part2-showingimage.png" alt-text="浏览器中显示的图像":::
   浏览器中显示的图像
:::image-end:::

<!--![The image showing in browser][ImagePart2Showingimage]  -->  

现在，你已创建了一个可成功将消息从 "扩展" 图标弹出窗口发送到 "浏览器" 选项卡上作为内容运行的动态插入的 JavaScript 的扩展。 这一插入的内容设置了 image 元素，以显示您的静态星 jpeg。  

<!-- image links -->  

<!--[ImagePart2Popupdialog]: ./media/part2-popupdialog.png "popup.html display after pressing the Extension icon"  -->  
<!--[ImagePart2Showingimage]: ./media/part2-showingimage.png "The image showing in browser"  -->

<!-- links -->  

[ArchiveExtensionGettingStartedPart2]: ./extension-source/extension-getting-started-part2.zip "已完成此部件的扩展程序包源 |Microsoft 文档"  
