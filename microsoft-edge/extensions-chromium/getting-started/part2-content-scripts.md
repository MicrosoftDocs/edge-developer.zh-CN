---
description: 使用内容脚本在页面正文标记下方动态插入 "版"</a0>
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
# <a name="create-an-extension-tutorial-part-2"></a><span data-ttu-id="ef6b9-104">创建扩展教程第 2 部分</span><span class="sxs-lookup"><span data-stu-id="ef6b9-104">Create an extension tutorial Part 2</span></span>  
  
[<span data-ttu-id="ef6b9-105">此部件已完成的扩展包源</span><span class="sxs-lookup"><span data-stu-id="ef6b9-105">Completed Extension Package Source for This Part</span></span>][ArchiveExtensionGettingStartedPart2]    

## <a name="overview"></a><span data-ttu-id="ef6b9-106">概述</span><span class="sxs-lookup"><span data-stu-id="ef6b9-106">Overview</span></span>  

<span data-ttu-id="ef6b9-107">本教程介绍以下扩展技术。</span><span class="sxs-lookup"><span data-stu-id="ef6b9-107">This tutorial covers the following extension technologies.</span></span>
*   <span data-ttu-id="ef6b9-108">将 JavaScript 库注入扩展</span><span class="sxs-lookup"><span data-stu-id="ef6b9-108">Injecting JavaScript libraries into extension</span></span>  
*   <span data-ttu-id="ef6b9-109">向浏览器选项卡公开扩展资产</span><span class="sxs-lookup"><span data-stu-id="ef6b9-109">Exposing extension assets to browser tabs</span></span>  
*   <span data-ttu-id="ef6b9-110">将内容页包括在现有的浏览器选项卡中</span><span class="sxs-lookup"><span data-stu-id="ef6b9-110">Including content pages in existing browser tabs</span></span>  
*   <span data-ttu-id="ef6b9-111">让内容页侦听来自弹出窗口的消息并做出响应</span><span class="sxs-lookup"><span data-stu-id="ef6b9-111">Having content pages listen for messages from pop-ups and respond</span></span>  

<span data-ttu-id="ef6b9-112">你将了解如何更新弹出菜单，以将静态启动图像替换为标题和标准 HTML 按钮。</span><span class="sxs-lookup"><span data-stu-id="ef6b9-112">You'll learn to update your pop-up menu to replace your static starts image with a title and a standard HTML button.</span></span>  <span data-ttu-id="ef6b9-113">选择此按钮时，会将嵌入在扩展中的星形图像传递给内容页。</span><span class="sxs-lookup"><span data-stu-id="ef6b9-113">That button, when selected, passes that stars image, which is embedded in the extension, to the content page.</span></span>  <span data-ttu-id="ef6b9-114">该图像将插入到活动的浏览器选项卡中。请按照以下步骤了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="ef6b9-114">That image, is inserted into the active browser tab. Follow the below steps for further details.</span></span>

1.  <span data-ttu-id="ef6b9-115">从弹出窗口中删除图像，并将其替换为按钮</span><span class="sxs-lookup"><span data-stu-id="ef6b9-115">Remove the image from the pop-up and replace it with a button</span></span>  

<span data-ttu-id="ef6b9-116">首先，使用一些显示标题和按钮的直接 `popup.html` 标记更新文件。</span><span class="sxs-lookup"><span data-stu-id="ef6b9-116">First, update your `popup.html` file with some straight forward markup that displays a title and a button.</span></span>  <span data-ttu-id="ef6b9-117">你很快就会对按钮进行编程，但现在只需包含对空 JavaScript 文件的引用 `popup.js` 。</span><span class="sxs-lookup"><span data-stu-id="ef6b9-117">You'll program that button shortly, but for now, just include a reference to an empty JavaScript file `popup.js`.</span></span>  <span data-ttu-id="ef6b9-118">下面是更新 HTML。</span><span class="sxs-lookup"><span data-stu-id="ef6b9-118">Here is update HTML.</span></span>  

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

<span data-ttu-id="ef6b9-119">更新并打开扩展后，将打开一个弹出窗口，并显示一个显示按钮。</span><span class="sxs-lookup"><span data-stu-id="ef6b9-119">After updating and opening the extension, a pop-up opens with a display button.</span></span>  

:::image type="complex" source="./media/part2-popupdialog.png" alt-text="popup.htm扩展图标后显示":::
   <span data-ttu-id="ef6b9-121">popup.htm扩展图标后显示</span><span class="sxs-lookup"><span data-stu-id="ef6b9-121">popup.html display after selecting the Extension icon</span></span>
:::image-end:::

<!--![popup.html display after selecting the Extension icon][ImagePart2Popupdialog]  -->  

2.  <span data-ttu-id="ef6b9-122">更新策略以显示浏览器选项卡顶部的图像</span><span class="sxs-lookup"><span data-stu-id="ef6b9-122">Update strategy to display image at the top of the browser tab</span></span>  

<span data-ttu-id="ef6b9-123">添加按钮后，下一个任务是使其在活动选项卡页的顶部显示 `images/stars.jpeg` 图像文件。</span><span class="sxs-lookup"><span data-stu-id="ef6b9-123">After adding the button, the next task is to make it bring up the `images/stars.jpeg` image file at the top of the active tab page.</span></span>  

<span data-ttu-id="ef6b9-124">请记住，每个选项卡页在其自己的线程中运行。</span><span class="sxs-lookup"><span data-stu-id="ef6b9-124">Remember, each tab page runs in its own thread.</span></span> <span data-ttu-id="ef6b9-125">此外，扩展使用不同的线程。</span><span class="sxs-lookup"><span data-stu-id="ef6b9-125">Also, the extension uses a different thread.</span></span>  <span data-ttu-id="ef6b9-126">首先，创建注入到选项卡页的内容脚本。</span><span class="sxs-lookup"><span data-stu-id="ef6b9-126">First, create a content script that is injected into the tab page.</span></span>  <span data-ttu-id="ef6b9-127">然后，从弹出窗口向在选项卡页上运行的内容脚本发送邮件。</span><span class="sxs-lookup"><span data-stu-id="ef6b9-127">Then, send a message from your pop-up to that content script running on the tab page.</span></span> <span data-ttu-id="ef6b9-128">内容脚本接收消息，描述应显示的图像。</span><span class="sxs-lookup"><span data-stu-id="ef6b9-128">The content script receives the message, which describes which image should be displayed.</span></span>  

3. <span data-ttu-id="ef6b9-129">创建弹出式 JavaScript 以发送邮件</span><span class="sxs-lookup"><span data-stu-id="ef6b9-129">Create the pop-up JavaScript to send a message</span></span>  

<span data-ttu-id="ef6b9-130">首先，创建并添加代码以向尚未创建的内容脚本发送消息，您必须立即创建该脚本并将其注入 `popup/popup.js` 浏览器选项卡。 为此，以下代码向弹出式显示 `onclick` 按钮添加事件。</span><span class="sxs-lookup"><span data-stu-id="ef6b9-130">First, create `popup/popup.js` and add code to send a message to your not-yet-created content script that you must momentarily create and inject into your browser tab.  To do that, the following code adds an `onclick` event to your pop-up display button.</span></span>  

```javascript
const sendMessageId = document.getElementById("sendmessageid");
if (sendMessageId) {
  sendMessageId.onclick = function() {
    // do something
  };
}
```  

<span data-ttu-id="ef6b9-131">在这种情况下 `onclick` ，查找当前浏览器选项卡。 然后，使用 `chrome.tabs.sendmessage` 扩展 API 向该选项卡发送消息。</span><span class="sxs-lookup"><span data-stu-id="ef6b9-131">In the `onclick` event, find the current browser tab.  Then, use the `chrome.tabs.sendmessage` Extension API to send a message to that tab.</span></span>  

<span data-ttu-id="ef6b9-132">在该消息中，必须包含要显示的图像的 URL。</span><span class="sxs-lookup"><span data-stu-id="ef6b9-132">In that message you must include the URL to the image you want to display.</span></span> <span data-ttu-id="ef6b9-133">此外，发送要分配给插入图像的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="ef6b9-133">Also, send a unique ID to assign to the inserted image.</span></span>  <span data-ttu-id="ef6b9-134">你可以选择让内容插入 JavaScript 生成它，但出于稍后显而易见的原因，请在此处生成该唯一 ID，并传递给尚未创建的内容 `popup.js` 脚本。</span><span class="sxs-lookup"><span data-stu-id="ef6b9-134">You may choose to let the content insertion JavaScript generate that, but for reasons that become apparent later, generate that unique ID here in `popup.js` and pass it to the not-yet-created content script.</span></span>  

<span data-ttu-id="ef6b9-135">下面的代码段概述了 . `popup/popup.js`</span><span class="sxs-lookup"><span data-stu-id="ef6b9-135">The following code snippet outlines the updated code in `popup/popup.js`.</span></span>  <span data-ttu-id="ef6b9-136">此外，请传递当前选项卡 ID，这将在本文的稍后部分使用。</span><span class="sxs-lookup"><span data-stu-id="ef6b9-136">Also, pass in the current tab ID, which is used later in this article.</span></span>  

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

4. <span data-ttu-id="ef6b9-137">从任何浏览器选项卡提供你的星形.jpeg</span><span class="sxs-lookup"><span data-stu-id="ef6b9-137">Make your stars.jpeg available from any browser tab</span></span>  

<span data-ttu-id="ef6b9-138">你可能想知道为什么在传递部件版式扩展 API 时必须使用部件版式扩展 API，而不是像上一节一样，在没有额外前缀的情况下仅传递相对 `images/stars.jpeg` `chrome.extension.getURL` URL。</span><span class="sxs-lookup"><span data-stu-id="ef6b9-138">You're probably wondering why, when you pass the `images/stars.jpeg` must you use the `chrome.extension.getURL` chrome Extension API instead of just passing in the relative URL without the extra prefix like in the previous section.</span></span>  <span data-ttu-id="ef6b9-139">这样一来，附加图像返回的附加前缀 `getUrl` 如下所示。</span><span class="sxs-lookup"><span data-stu-id="ef6b9-139">By the way, that extra prefix, returned by `getUrl` with the image attached looks something like the following.</span></span>  

```http
extension://inigobacliaghocjiapeaaoemkjifjhp/images/stars.jpeg
```  

<span data-ttu-id="ef6b9-140">原因是你使用元素的属性将图像 `src` `img` 注入内容页。</span><span class="sxs-lookup"><span data-stu-id="ef6b9-140">The reason is that you're injecting the image using the `src` attribute of the `img` element into the content page.</span></span>  <span data-ttu-id="ef6b9-141">内容页在与运行扩展的线程不同的唯一线程上运行。</span><span class="sxs-lookup"><span data-stu-id="ef6b9-141">The content page is running on a unique thread that isn't the same as the thread running the Extension.</span></span>  <span data-ttu-id="ef6b9-142">您必须将静态图像文件作为 Web 资产公开，它必须能够正常运行。</span><span class="sxs-lookup"><span data-stu-id="ef6b9-142">You must expose the static image file as a web asset for it to work correctly.</span></span>  

<span data-ttu-id="ef6b9-143">在文件中添加另 `manifest.json` 一项以声明该图像可供所有浏览器选项卡使用。</span><span class="sxs-lookup"><span data-stu-id="ef6b9-143">Add another entry in the `manifest.json` file to declare that the image is available to all browser tabs.</span></span>  <span data-ttu-id="ef6b9-144">添加内容脚本声明时 (应在下面的完整文件中看到 `manifest.json` 该条目，如下所示\) 。</span><span class="sxs-lookup"><span data-stu-id="ef6b9-144">That entry is as follows \(you should see it in the full `manifest.json` file below when you add the content script declaration coming up\).</span></span>  

```json
"web_accessible_resources": [
    "images/*.jpeg"
]
```  

<span data-ttu-id="ef6b9-145">现在，你已在你的文件中编写代码，以向嵌入在当前活动选项卡页上的内容页发送邮件，但您尚未创建并 `popup.js` 注入该内容页。</span><span class="sxs-lookup"><span data-stu-id="ef6b9-145">You've now written the code in your `popup.js` file to send a message to the content page that is embedded on the current active tab page, but you haven't created and injected that content page.</span></span>  <span data-ttu-id="ef6b9-146">现在执行。</span><span class="sxs-lookup"><span data-stu-id="ef6b9-146">Do that now.</span></span>  

5.  <span data-ttu-id="ef6b9-147">更新manifest.js和 Web 访问功能</span><span class="sxs-lookup"><span data-stu-id="ef6b9-147">Update your manifest.json for content and web access</span></span>  

<span data-ttu-id="ef6b9-148">更新 `manifest.json` 后，包括 `content-scripts` 和 `web_accessible_resources` ，如下所示。</span><span class="sxs-lookup"><span data-stu-id="ef6b9-148">The updated `manifest.json` that includes the `content-scripts` and `web_accessible_resources` is as follows.</span></span>  

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

<span data-ttu-id="ef6b9-149">你添加的节是 `content_scripts` 。</span><span class="sxs-lookup"><span data-stu-id="ef6b9-149">The section you added is `content_scripts`.</span></span>  <span data-ttu-id="ef6b9-150">该属性设置为 ，这意味着加载每个选项卡时，所有文件将注入 `matches` `<all_urls>` `content_scripts` 所有浏览器选项卡页。</span><span class="sxs-lookup"><span data-stu-id="ef6b9-150">The `matches` attribute is set to `<all_urls>`, which means that all files in `content_scripts` are injected into all browser tab pages when each tab is loaded.</span></span>  <span data-ttu-id="ef6b9-151">可以注入的允许文件类型是 JavaScript 和 CSS。</span><span class="sxs-lookup"><span data-stu-id="ef6b9-151">The allowed files types that can be injected are JavaScript and CSS.</span></span>  <span data-ttu-id="ef6b9-152">你还添加了 `libjquery.min.js` 。</span><span class="sxs-lookup"><span data-stu-id="ef6b9-152">You also added `libjquery.min.js`.</span></span>  <span data-ttu-id="ef6b9-153">你可以从节顶部提到的下载中包括该内容。</span><span class="sxs-lookup"><span data-stu-id="ef6b9-153">You're able to include that from the download mentioned at the top of the section.</span></span>  

6. <span data-ttu-id="ef6b9-154">添加 jQuery 并理解关联的线程</span><span class="sxs-lookup"><span data-stu-id="ef6b9-154">Add jQuery and understanding the associated thread</span></span>  

<span data-ttu-id="ef6b9-155">在要注入的内容脚本中，规划使用 jQuery \ (`$` \) 。</span><span class="sxs-lookup"><span data-stu-id="ef6b9-155">In the content scripts that you're injecting, plan on using jQuery \(`$`\).</span></span>  <span data-ttu-id="ef6b9-156">你添加了 jQuery 的缩小版本，并作为 `lib\jquery.min.js`</span><span class="sxs-lookup"><span data-stu-id="ef6b9-156">You added a minified version of jQuery and put it in your Extension package as `lib\jquery.min.js`.</span></span>  <span data-ttu-id="ef6b9-157">这些内容脚本在单个沙盒中运行，这意味着注入页面的 jQuery `popup.js` 不会与内容共享。</span><span class="sxs-lookup"><span data-stu-id="ef6b9-157">These content scripts run in individual sandboxes, which means that the jQuery injected into the `popup.js` page isn't shared with the content.</span></span>  

<span data-ttu-id="ef6b9-158">请记住，即使浏览器选项卡在已加载网页上运行 JavaScript，注入的任何内容也无法访问它。</span><span class="sxs-lookup"><span data-stu-id="ef6b9-158">Keep in mind that even if the browser tab has JavaScript running on it on the loaded web page, any content injected doesn't have access to that.</span></span>  <span data-ttu-id="ef6b9-159">注入的 JavaScript 仅有权访问该浏览器选项卡中加载的实际 DOM。</span><span class="sxs-lookup"><span data-stu-id="ef6b9-159">That injected JavaScript just has access to the actual DOM loaded in that browser tab.</span></span>  

7. <span data-ttu-id="ef6b9-160">添加内容脚本消息侦听器</span><span class="sxs-lookup"><span data-stu-id="ef6b9-160">Add the content script message listener</span></span>  

<span data-ttu-id="ef6b9-161">下面是根据 `content-scripts\content.js` 你的部分注入到每个浏览器选项卡页 `manifest.json` `content-scripts` 的文件。</span><span class="sxs-lookup"><span data-stu-id="ef6b9-161">Here is that `content-scripts\content.js` file that gets injected into every browser tab page based on your `manifest.json` `content-scripts` section.</span></span>  

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

<span data-ttu-id="ef6b9-162">请注意，上述 JavaScript 所执行的所有操作都是使用扩展 `listener` API 方法 `chrome.runtime.onMessage.addListener` 注册。</span><span class="sxs-lookup"><span data-stu-id="ef6b9-162">Notice that all the above JavaScript does is to register a `listener` using the `chrome.runtime.onMessage.addListener` Extension API method.</span></span>  <span data-ttu-id="ef6b9-163">此侦听器等待消息，如使用扩展 API 方法从前面所述的 `popup.js` `chrome.tabs.sendMessage` 消息发送的消息。</span><span class="sxs-lookup"><span data-stu-id="ef6b9-163">This listener waits for messages like the one you sent from the `popup.js` described earlier with the `chrome.tabs.sendMessage` Extension API method.</span></span>  

<span data-ttu-id="ef6b9-164">该方法的第一个参数是一个函数，其第一个参数请求是传入 `addListener` 的消息的详细信息。</span><span class="sxs-lookup"><span data-stu-id="ef6b9-164">The first parameter of the `addListener` method is a function whose first parameter, request, is the details of the message being passed in.</span></span>  <span data-ttu-id="ef6b9-165">请记住，在使用此方法时，第一个参数 `popup.js` `sendMessage` 的这些属性为 `url` `imageDivId` 和 。</span><span class="sxs-lookup"><span data-stu-id="ef6b9-165">Remember, from `popup.js`, when you used the `sendMessage` method, those attributes of the first parameter are `url` and `imageDivId`.</span></span>  

<span data-ttu-id="ef6b9-166">当侦听器处理事件时，将运行作为第一个参数的函数。</span><span class="sxs-lookup"><span data-stu-id="ef6b9-166">When an event is processed by the listener, the function that is the first parameter is run.</span></span>  <span data-ttu-id="ef6b9-167">该函数的第一个参数是具有由 分配的属性的对象 `sendMessage` 。</span><span class="sxs-lookup"><span data-stu-id="ef6b9-167">The first parameter of that function is an object that has attributes as assigned by `sendMessage`.</span></span>  <span data-ttu-id="ef6b9-168">该函数只处理三个 jQuery 脚本行。</span><span class="sxs-lookup"><span data-stu-id="ef6b9-168">That function simply processes the three jQuery script lines.</span></span>  

*   <span data-ttu-id="ef6b9-169">第一个脚本行动态插入 DOM 标头中一个必须作为类分配给元素 **\<style\>** `slide-image` `img` 的部分。</span><span class="sxs-lookup"><span data-stu-id="ef6b9-169">The first script line dynamically inserts into the DOM header a **\<style\>** section that you must assign as a `slide-image` class to your `img` element.</span></span>  
*   <span data-ttu-id="ef6b9-170">第二个脚本行将一个元素追加到浏览器选项卡的正下方，该选项卡分配了类以及该 `img` `body` `slide-image` `imageDivId` 图像元素的 ID。</span><span class="sxs-lookup"><span data-stu-id="ef6b9-170">The second script line appends an `img` element right below the `body` of your browser tab that has the `slide-image` class assigned as well as the `imageDivId` as the ID of that image element.</span></span>  
*   <span data-ttu-id="ef6b9-171">第三个脚本行添加一个涵盖整个图像的事件，允许用户选择图像上的任意位置，并将该图像从页面 \ (以及事件侦听器 `click` \) 。</span><span class="sxs-lookup"><span data-stu-id="ef6b9-171">The third script line adds a `click` event that covers the entire image allowing the user to select anywhere on the image and that image is removed from the page \(along with it is event listener\).</span></span>  

8. <span data-ttu-id="ef6b9-172">添加功能以在选中时删除显示的图像</span><span class="sxs-lookup"><span data-stu-id="ef6b9-172">Add functionality to remove the displayed image when selected</span></span>  

<span data-ttu-id="ef6b9-173">现在，当您浏览到任何页面 **并选择扩展图标** 时，弹出菜单将显示如下。</span><span class="sxs-lookup"><span data-stu-id="ef6b9-173">Now, when you browse to any page and select your **Extension** icon, the pop-up menu is displayed as follows.</span></span>  

:::image type="complex" source="./media/part2-popupdialog.png" alt-text="popup.htm扩展图标后显示":::
   <span data-ttu-id="ef6b9-175">popup.htm扩展图标后显示</span><span class="sxs-lookup"><span data-stu-id="ef6b9-175">popup.html display after selecting the Extension icon</span></span>
:::image-end:::

<!--![popup.html display after selecting the Extension icon][ImagePart2Popupdialog]  -->  

<span data-ttu-id="ef6b9-176">选择该 `Display` 按钮时，将获取下面的内容。</span><span class="sxs-lookup"><span data-stu-id="ef6b9-176">When you select the `Display` button, you get what is below.</span></span>  <span data-ttu-id="ef6b9-177">如果在图像上的任意位置选择，该图像元素将被删除，选项卡页将折叠 `stars.jpeg` 回最初显示的内容。</span><span class="sxs-lookup"><span data-stu-id="ef6b9-177">If you select anywhere on the `stars.jpeg` image, that image element is removed and tab pages collapses back to what was originally displayed.</span></span>  

:::image type="complex" source="./media/part2-showingimage.png" alt-text="在浏览器中显示的图像":::
   <span data-ttu-id="ef6b9-179">在浏览器中显示的图像</span><span class="sxs-lookup"><span data-stu-id="ef6b9-179">The image showing in browser</span></span>
:::image-end:::

<span data-ttu-id="ef6b9-180">你已创建一个扩展，该扩展从扩展图标弹出窗口成功发送邮件，并动态插入作为浏览器选项卡上的内容运行的 JavaScript。 注入的内容设置图像元素以显示静态星形。</span><span class="sxs-lookup"><span data-stu-id="ef6b9-180">You've created an Extension that successfully sends a message from the extension icon pop-up, and dynamically inserted JavaScript running as content on the browser tab.  The injected content sets the image element to display your static stars jpeg.</span></span>  

<!-- image links -->  


<!-- links -->  

[ArchiveExtensionGettingStartedPart2]: https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/master/extension-getting-started-part2/extension-getting-started-part2 "已完成的扩展包源|Microsoft Docs"  
