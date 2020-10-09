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
# <span data-ttu-id="cd454-104">创建扩展教程第 2 部分</span><span class="sxs-lookup"><span data-stu-id="cd454-104">Create an extension tutorial Part 2</span></span>  
  
[<span data-ttu-id="cd454-105">此部件的已完成扩展程序包源</span><span class="sxs-lookup"><span data-stu-id="cd454-105">Completed Extension Package Source for This Part</span></span>][ArchiveExtensionGettingStartedPart2]    

## <span data-ttu-id="cd454-106">概述</span><span class="sxs-lookup"><span data-stu-id="cd454-106">Overview</span></span>  

<span data-ttu-id="cd454-107">本教程介绍以下扩展技术。</span><span class="sxs-lookup"><span data-stu-id="cd454-107">This tutorial covers the following extension technologies.</span></span>
*   <span data-ttu-id="cd454-108">将 JavaScript 库注入扩展</span><span class="sxs-lookup"><span data-stu-id="cd454-108">Injecting JavaScript libraries into extension</span></span>  
*   <span data-ttu-id="cd454-109">向浏览器选项卡公开扩展资源</span><span class="sxs-lookup"><span data-stu-id="cd454-109">Exposing extension assets to browser tabs</span></span>  
*   <span data-ttu-id="cd454-110">在现有浏览器选项卡中包括内容页</span><span class="sxs-lookup"><span data-stu-id="cd454-110">Including content pages in existing browser tabs</span></span>  
*   <span data-ttu-id="cd454-111">让内容页侦听来自弹出窗口的消息并进行响应</span><span class="sxs-lookup"><span data-stu-id="cd454-111">Having content pages listen for messages from pop-ups and respond</span></span>  

<span data-ttu-id="cd454-112">你将了解如何更新你的弹出菜单，以使用标题和标准 HTML 按钮替换静态开始图像。</span><span class="sxs-lookup"><span data-stu-id="cd454-112">You'll learn to update your pop-up menu to replace your static starts image with a title and a standard HTML button.</span></span>  <span data-ttu-id="cd454-113">选中此按钮后，会将该星形图像（嵌入在扩展中）传递到内容页面。</span><span class="sxs-lookup"><span data-stu-id="cd454-113">That button, when selected, passes that stars image, which is embedded in the extension, to the content page.</span></span>  <span data-ttu-id="cd454-114">该图像将插入到活动浏览器选项卡中。有关详细信息，请按照以下步骤进行操作。</span><span class="sxs-lookup"><span data-stu-id="cd454-114">That image, is inserted into the active browser tab. Follow the below steps for further details.</span></span>

1.  <span data-ttu-id="cd454-115">从弹出窗口中删除图像，并将其替换为按钮</span><span class="sxs-lookup"><span data-stu-id="cd454-115">Remove the image from the pop-up and replace it with a button</span></span>  

<span data-ttu-id="cd454-116">首先， `popup.html` 使用显示标题和按钮的一些直接向前标记更新你的文件。</span><span class="sxs-lookup"><span data-stu-id="cd454-116">First, update your `popup.html` file with some straight forward markup that displays a title and a button.</span></span>  <span data-ttu-id="cd454-117">你将很快对该按钮进行编程，但现在，只需包含对空 JavaScript 文件的引用 `popup.js` 。</span><span class="sxs-lookup"><span data-stu-id="cd454-117">You'll program that button shortly, but for now, just include a reference to an empty JavaScript file `popup.js`.</span></span>  <span data-ttu-id="cd454-118">下面是更新 HTML。</span><span class="sxs-lookup"><span data-stu-id="cd454-118">Here is update HTML.</span></span>  

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

<span data-ttu-id="cd454-119">更新并打开扩展后，将打开一个显示 "显示" 按钮的弹出窗口。</span><span class="sxs-lookup"><span data-stu-id="cd454-119">After updating and opening the extension, a pop-up opens with a display button.</span></span>  

:::image type="complex" source="./media/part2-popupdialog.png" alt-text="按下 &quot;扩展&quot; 图标后，popup.html 显示":::
   <span data-ttu-id="cd454-121">按下 "扩展" 图标后，popup.html 显示</span><span class="sxs-lookup"><span data-stu-id="cd454-121">popup.html display after pressing the Extension icon</span></span>
:::image-end:::

<!--![popup.html display after pressing the Extension icon][ImagePart2Popupdialog]  -->  

2.  <span data-ttu-id="cd454-122">在浏览器选项卡顶部显示图像的更新策略</span><span class="sxs-lookup"><span data-stu-id="cd454-122">Update strategy to display image at the top of the browser tab</span></span>  

<span data-ttu-id="cd454-123">添加按钮后，下一任务是使其 `images/stars.jpeg` 在活动选项卡页顶部打开图像文件。</span><span class="sxs-lookup"><span data-stu-id="cd454-123">After adding the button, the next task is to make it bring up the `images/stars.jpeg` image file at the top of the active tab page.</span></span>  

<span data-ttu-id="cd454-124">请记住，每个选项卡页都在其自己的线程中运行。</span><span class="sxs-lookup"><span data-stu-id="cd454-124">Remember, each tab page runs in its own thread.</span></span> <span data-ttu-id="cd454-125">此外，该扩展还使用另一个线程。</span><span class="sxs-lookup"><span data-stu-id="cd454-125">Also, the extension uses a different thread.</span></span>  <span data-ttu-id="cd454-126">首先，创建一个插入到选项卡页中的内容脚本。</span><span class="sxs-lookup"><span data-stu-id="cd454-126">First, create a content script that is injected into the tab page.</span></span>  <span data-ttu-id="cd454-127">然后，从弹出窗口发送一条消息，直到在选项卡页上运行该内容脚本。</span><span class="sxs-lookup"><span data-stu-id="cd454-127">Then, send a message from your pop-up to that content script running on the tab page.</span></span> <span data-ttu-id="cd454-128">内容脚本接收消息，该消息描述应显示哪个图像。</span><span class="sxs-lookup"><span data-stu-id="cd454-128">The content script receives the message, which describes which image should be displayed.</span></span>  

3. <span data-ttu-id="cd454-129">创建弹出 JavaScript 以发送消息</span><span class="sxs-lookup"><span data-stu-id="cd454-129">Create the pop-up JavaScript to send a message</span></span>  

<span data-ttu-id="cd454-130">首先，创建 `popup/popup.js` 并添加代码，以便向尚未创建的内容脚本发送邮件，您必须立即创建并插入到浏览器选项卡。 为此，以下代码将 `onclick` 事件添加到弹出的 "显示" 按钮。</span><span class="sxs-lookup"><span data-stu-id="cd454-130">First, create `popup/popup.js` and add code to send a message to your not-yet-created content script that you must momentarily create and inject into your browser tab.  To do that, the following code adds an `onclick` event to your pop-up display button.</span></span>  

```javascript
const sendMessageId = document.getElementById("sendmessageid");
if (sendMessageId) {
  sendMessageId.onclick = function() {
    // do something
  };
}
```  

<span data-ttu-id="cd454-131">在 `onclick` 事件中，找到 "当前浏览器" 选项卡。 然后，使用 `chrome.tabs.sendmessage` 扩展 API 将消息发送到该选项卡。</span><span class="sxs-lookup"><span data-stu-id="cd454-131">In the `onclick` event, find the current browser tab.  Then, use the `chrome.tabs.sendmessage` Extension API to send a message to that tab.</span></span>  

<span data-ttu-id="cd454-132">在该消息中，必须包含要显示的图像的 URL。</span><span class="sxs-lookup"><span data-stu-id="cd454-132">In that message you must include the URL to the image you want to display.</span></span> <span data-ttu-id="cd454-133">此外，还应发送一个唯一的 ID 以分配给插入的图像。</span><span class="sxs-lookup"><span data-stu-id="cd454-133">Also, send a unique ID to assign to the inserted image.</span></span>  <span data-ttu-id="cd454-134">你可以选择让内容插入 JavaScript 生成该内容，但对于稍后变得明显的原因，在此处生成唯一 ID `popup.js` 并将其传递给尚未创建的内容脚本。</span><span class="sxs-lookup"><span data-stu-id="cd454-134">You may choose to let the content insertion JavaScript generate that, but for reasons that become apparent later, generate that unique ID here in `popup.js` and pass it to the not-yet-created content script.</span></span>  

<span data-ttu-id="cd454-135">以下代码片段概述了更新的代码 `popup/popup.js` 。</span><span class="sxs-lookup"><span data-stu-id="cd454-135">The following code snippet outlines the updated code in `popup/popup.js`.</span></span>  <span data-ttu-id="cd454-136">此外，传递当前的选项卡 ID，本文稍后部分将使用该 ID。</span><span class="sxs-lookup"><span data-stu-id="cd454-136">Also, pass in the current tab ID, which is used later in this article.</span></span>  

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

4. <span data-ttu-id="cd454-137">让您的星从任何浏览器选项卡中可用</span><span class="sxs-lookup"><span data-stu-id="cd454-137">Make your stars.jpeg available from any browser tab</span></span>  

<span data-ttu-id="cd454-138">你可能会想知道，在传递时 `images/stars.jpeg` 必须使用 `chrome.extension.getURL` CHROME 扩展 API，而不是仅在没有额外前缀的情况下传递相对 URL，如上一节中所示。</span><span class="sxs-lookup"><span data-stu-id="cd454-138">You're probably wondering why, when you pass the `images/stars.jpeg` must you use the `chrome.extension.getURL` chrome Extension API instead of just passing in the relative URL without the extra prefix like in the previous section.</span></span>  <span data-ttu-id="cd454-139">顺便说一下，附加的前缀由附加的 `getUrl` 图像所返回，其外观类似于以下内容。</span><span class="sxs-lookup"><span data-stu-id="cd454-139">By the way, that extra prefix, returned by `getUrl` with the image attached looks something like the following.</span></span>  

```http
extension://inigobacliaghocjiapeaaoemkjifjhp/images/stars.jpeg
```  

<span data-ttu-id="cd454-140">原因是您要使用元素的属性将图像插入 `src` `img` 到内容页面。</span><span class="sxs-lookup"><span data-stu-id="cd454-140">The reason is that you're injecting the image using the `src` attribute of the `img` element into the content page.</span></span>  <span data-ttu-id="cd454-141">内容页面在与运行扩展的线程不同的唯一线程上运行。</span><span class="sxs-lookup"><span data-stu-id="cd454-141">The content page is running on a unique thread that isn't the same as the thread running the Extension.</span></span>  <span data-ttu-id="cd454-142">必须将静态图像文件作为 web 资产公开才能正常工作。</span><span class="sxs-lookup"><span data-stu-id="cd454-142">You must expose the static image file as a web asset for it to work correctly.</span></span>  

<span data-ttu-id="cd454-143">在文件中添加其他条目 `manifest.json` 以声明图像可用于所有浏览器选项卡。</span><span class="sxs-lookup"><span data-stu-id="cd454-143">Add another entry in the `manifest.json` file to declare that the image is available to all browser tabs.</span></span>  <span data-ttu-id="cd454-144">该条目如下所示 \ (`manifest.json` 当您添加即将出现的内容脚本声明时，请在下面的完整文件中看到该条目： \ ) 。</span><span class="sxs-lookup"><span data-stu-id="cd454-144">That entry is as follows \(you should see it in the full `manifest.json` file below when you add the content script declaration coming up\).</span></span>  

```json
"web_accessible_resources": [
    "images/*.jpeg"
]
```  

<span data-ttu-id="cd454-145">现在，你已在文件中写入代码 `popup.js` ，以向嵌入当前活动选项卡页上的内容页发送消息，但尚未创建和注入该内容页面。</span><span class="sxs-lookup"><span data-stu-id="cd454-145">You've now written the code in your `popup.js` file to send a message to the content page that is embedded on the current active tab page, but you haven't created and injected that content page.</span></span>  <span data-ttu-id="cd454-146">立即执行此操作。</span><span class="sxs-lookup"><span data-stu-id="cd454-146">Do that now.</span></span>  

5.  <span data-ttu-id="cd454-147">更新内容和 web 访问的 manifest.js</span><span class="sxs-lookup"><span data-stu-id="cd454-147">Update your manifest.json for content and web access</span></span>  

<span data-ttu-id="cd454-148">`manifest.json`包括的和的更新 `content-scripts` `web_accessible_resources` 如下所示。</span><span class="sxs-lookup"><span data-stu-id="cd454-148">The updated `manifest.json` that includes the `content-scripts` and `web_accessible_resources` is as follows.</span></span>  

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

<span data-ttu-id="cd454-149">你添加的分区是 `content_scripts` 。</span><span class="sxs-lookup"><span data-stu-id="cd454-149">The section you added is `content_scripts`.</span></span>  <span data-ttu-id="cd454-150">该 `matches` 属性设置为 `<all_urls>` ，这意味着 `content_scripts` 当加载每个选项卡时，中的所有文件都插入到所有浏览器选项卡页面中。</span><span class="sxs-lookup"><span data-stu-id="cd454-150">The `matches` attribute is set to `<all_urls>`, which means that all files in `content_scripts` are injected into all browser tab pages when each tab is loaded.</span></span>  <span data-ttu-id="cd454-151">可注入的允许文件类型为 JavaScript 和 CSS。</span><span class="sxs-lookup"><span data-stu-id="cd454-151">The allowed files types that can be injected are JavaScript and CSS.</span></span>  <span data-ttu-id="cd454-152">您还添加了 `libjquery.min.js` 。</span><span class="sxs-lookup"><span data-stu-id="cd454-152">You also added `libjquery.min.js`.</span></span>  <span data-ttu-id="cd454-153">你可以从本部分顶部提及的下载中包含该内容。</span><span class="sxs-lookup"><span data-stu-id="cd454-153">You're able to include that from the download mentioned at the top of the section.</span></span>  

6. <span data-ttu-id="cd454-154">添加 jQuery 并了解关联的线程</span><span class="sxs-lookup"><span data-stu-id="cd454-154">Add jQuery and understanding the associated thread</span></span>  

<span data-ttu-id="cd454-155">在要插入的内容脚本中，使用 jQuery \ (`$` \ ) 进行计划。</span><span class="sxs-lookup"><span data-stu-id="cd454-155">In the content scripts that you're injecting, plan on using jQuery \(`$`\).</span></span>  <span data-ttu-id="cd454-156">你添加了一个 minified 版本的 jQuery，并将其放入你的扩展程序包中 `lib\jquery.min.js` 。</span><span class="sxs-lookup"><span data-stu-id="cd454-156">You added a minified version of jQuery and put it in your Extension package as `lib\jquery.min.js`.</span></span>  <span data-ttu-id="cd454-157">这些内容脚本在单个沙盒中运行，这意味着插入到页面中的 jQuery `popup.js` 不会与内容共享。</span><span class="sxs-lookup"><span data-stu-id="cd454-157">These content scripts run in individual sandboxes, which means that the jQuery injected into the `popup.js` page isn't shared with the content.</span></span>  

<span data-ttu-id="cd454-158">请记住，即使浏览器选项卡在加载的网页上运行了 JavaScript，任何插入的内容也不会有访问权限。</span><span class="sxs-lookup"><span data-stu-id="cd454-158">Keep in mind that even if the browser tab has JavaScript running on it on the loaded web page, any content injected doesn't have access to that.</span></span>  <span data-ttu-id="cd454-159">所注入的 JavaScript 只对在该浏览器选项卡中加载的实际 DOM 具有访问权限。</span><span class="sxs-lookup"><span data-stu-id="cd454-159">That injected JavaScript just has access to the actual DOM loaded in that browser tab.</span></span>  

7. <span data-ttu-id="cd454-160">添加内容脚本消息侦听器</span><span class="sxs-lookup"><span data-stu-id="cd454-160">Add the content script message listener</span></span>  

<span data-ttu-id="cd454-161">此处是 `content-scripts\content.js` 基于你的分区将其插入到每个浏览器选项卡页中的文件 `manifest.json` `content-scripts` 。</span><span class="sxs-lookup"><span data-stu-id="cd454-161">Here is that `content-scripts\content.js` file that gets injected into every browser tab page based on your `manifest.json` `content-scripts` section.</span></span>  

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

<span data-ttu-id="cd454-162">请注意，上述所有 JavaScript 都是 `listener` 使用 `chrome.runtime.onMessage.addListener` 扩展 API 方法注册 a。</span><span class="sxs-lookup"><span data-stu-id="cd454-162">Notice that all the above JavaScript does is to register a `listener` using the `chrome.runtime.onMessage.addListener` Extension API method.</span></span>  <span data-ttu-id="cd454-163">此侦听器将等待你从 `popup.js` 前面介绍的带有扩展 API 方法的消息（如你发送给它的消息） `chrome.tabs.sendMessage` 。</span><span class="sxs-lookup"><span data-stu-id="cd454-163">This listener waits for messages like the one you sent from the `popup.js` described earlier with the `chrome.tabs.sendMessage` Extension API method.</span></span>  

<span data-ttu-id="cd454-164">该方法的第一个参数 `addListener` 是一个函数，其第一个参数请求是正在传入的消息的详细信息。</span><span class="sxs-lookup"><span data-stu-id="cd454-164">The first parameter of the `addListener` method is a function whose first parameter, request, is the details of the message being passed in.</span></span>  <span data-ttu-id="cd454-165">请记住，在 `popup.js` 使用 `sendMessage` 方法时，第一个参数的这些属性是 `url` 和 `imageDivId` 。</span><span class="sxs-lookup"><span data-stu-id="cd454-165">Remember, from `popup.js`, when you used the `sendMessage` method, those attributes of the first parameter are `url` and `imageDivId`.</span></span>  

<span data-ttu-id="cd454-166">当侦听器处理事件时，将运行第一个参数的函数。</span><span class="sxs-lookup"><span data-stu-id="cd454-166">When an event is processed by the listener, the function that is the first parameter is run.</span></span>  <span data-ttu-id="cd454-167">该函数的第一个参数是具有分配的属性的对象 `sendMessage` 。</span><span class="sxs-lookup"><span data-stu-id="cd454-167">The first parameter of that function is an object that has attributes as assigned by `sendMessage`.</span></span>  <span data-ttu-id="cd454-168">该函数只处理三个 jQuery 脚本行。</span><span class="sxs-lookup"><span data-stu-id="cd454-168">That function simply processes the three jQuery script lines.</span></span>  

*   <span data-ttu-id="cd454-169">第一个脚本行将动态插入 **\<style\>** 必须作为类分配给你的元素的一个分区 `slide-image` `img` 。</span><span class="sxs-lookup"><span data-stu-id="cd454-169">The first script line dynamically inserts into the DOM header a **\<style\>** section that you must assign as a `slide-image` class to your `img` element.</span></span>  
*   <span data-ttu-id="cd454-170">第二个脚本行在 `img` "浏览器" 选项卡下的 "浏览器" 选项卡的下方附加一个元素 `body` ，该元素具有 `slide-image` 分配给该类的类以及 `imageDivId` 作为该图像元素的 ID。</span><span class="sxs-lookup"><span data-stu-id="cd454-170">The second script line appends an `img` element right below the `body` of your browser tab that has the `slide-image` class assigned as well as the `imageDivId` as the ID of that image element.</span></span>  
*   <span data-ttu-id="cd454-171">第三个脚本行添加了一个 `click` 事件，该事件涵盖整个图像，允许用户选择图像上的任意位置，并且该图像将从页面 \ (中删除，同时它是事件侦听器 \ ) 。</span><span class="sxs-lookup"><span data-stu-id="cd454-171">The third script line adds a `click` event that covers the entire image allowing the user to select anywhere on the image and that image is removed from the page \(along with it is event listener\).</span></span>  

8. <span data-ttu-id="cd454-172">添加功能以在选定时删除显示的图像</span><span class="sxs-lookup"><span data-stu-id="cd454-172">Add functionality to remove the displayed image when selected</span></span>  

<span data-ttu-id="cd454-173">现在，当您浏览到任意页面并选择您的 **扩展名** 图标时，弹出菜单显示如下。</span><span class="sxs-lookup"><span data-stu-id="cd454-173">Now, when you browse to any page and select your **Extension** icon, the pop-up menu is displayed as follows.</span></span>  

:::image type="complex" source="./media/part2-popupdialog.png" alt-text="按下 &quot;扩展&quot; 图标后，popup.html 显示":::
   <span data-ttu-id="cd454-175">按下 "扩展" 图标后，popup.html 显示</span><span class="sxs-lookup"><span data-stu-id="cd454-175">popup.html display after pressing the Extension icon</span></span>
:::image-end:::

<!--![popup.html display after pressing the Extension icon][ImagePart2Popupdialog]  -->  

<span data-ttu-id="cd454-176">选择该按钮后 `Display` ，将获得以下内容。</span><span class="sxs-lookup"><span data-stu-id="cd454-176">When you select the `Display` button, you get what is below.</span></span>  <span data-ttu-id="cd454-177">如果选择图像上的任意位置 `stars.jpeg` ，则会删除该图像元素，并且选项卡页将折叠为最初显示的内容。</span><span class="sxs-lookup"><span data-stu-id="cd454-177">If you select anywhere on the `stars.jpeg` image, that image element is removed and tab pages collapses back to what was originally displayed.</span></span>  

:::image type="complex" source="./media/part2-showingimage.png" alt-text="按下 &quot;扩展&quot; 图标后，popup.html 显示":::
   <span data-ttu-id="cd454-179">浏览器中显示的图像</span><span class="sxs-lookup"><span data-stu-id="cd454-179">The image showing in browser</span></span>
:::image-end:::

<span data-ttu-id="cd454-180">你创建了一个扩展，该扩展将从 "扩展" 图标弹出窗口成功发送一条消息，并在浏览器选项卡上以内容的形式动态插入 JavaScript。 插入的内容将设置 image 元素以显示您的静态星 jpeg。</span><span class="sxs-lookup"><span data-stu-id="cd454-180">You've created an Extension that successfully sends a message from the extension icon pop-up, and dynamically inserted JavaScript running as content on the browser tab.  The injected content sets the image element to display your static stars jpeg.</span></span>  

<!-- image links -->  


<!-- links -->  

[ArchiveExtensionGettingStartedPart2]: https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/extension-getting-started-part2/extension-getting-started-part2 "已完成扩展程序包源 |Microsoft 文档"  
