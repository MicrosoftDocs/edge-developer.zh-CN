---
description: 在 Microsoft Edge 中使用 Puppeteer 自动处理和测试
title: Puppeteer
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/25/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: microsoft edge，web 开发，开发人员，工具，自动化，测试
ms.openlocfilehash: e92a863f28c96157b4c7692bd88ba6884cbf8f52
ms.sourcegitcommit: 2e14ff82350f700d7eabc8d33b3ec3e5fc8c61fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "11192231"
---
# <span data-ttu-id="8910f-104">Puppeteer</span><span class="sxs-lookup"><span data-stu-id="8910f-104">Puppeteer</span></span>  

<span data-ttu-id="8910f-105">[Puppeteer][|::ref1::|Main] 是一个 [节点][NodejsMain] 库，它提供了一个高级 API，用于控制 Microsoft Edge \ (Chromium \ ) 使用 [DevTools 协议][GithubChromedevtoolsProtocol]。</span><span class="sxs-lookup"><span data-stu-id="8910f-105">[Puppeteer][|::ref1::|Main] is a [Node][NodejsMain] library that provides a high-level API to control Microsoft Edge \(Chromium\) using the [DevTools Protocol][GithubChromedevtoolsProtocol].</span></span>  <span data-ttu-id="8910f-106">默认情况下，Puppeteer 启动无 [头浏览器][WikiHeadlessBrowser] 。</span><span class="sxs-lookup"><span data-stu-id="8910f-106">Puppeteer launches [headless browsers][WikiHeadlessBrowser] by default.</span></span>  <span data-ttu-id="8910f-107">无外设浏览器不显示 UI，因此必须使用命令行。</span><span class="sxs-lookup"><span data-stu-id="8910f-107">Headless browsers do not display a UI, so instead you must use the command line.</span></span>  <span data-ttu-id="8910f-108">您也可以将 Puppeteer 配置为同时运行完全 \ (非无外设 \ ) Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="8910f-108">You may also configure Puppeteer to run full \(non-headless\) Microsoft Edge as well.</span></span>  

<span data-ttu-id="8910f-109">默认情况下，当你安装 Puppeteer 时，安装程序将下载 [Chromium][ChromiumHome]的最新版本， [还会生成 Microsoft Edge][MicrosoftBlogsWindowsExperience20181206]的 "开放源代码浏览器"。</span><span class="sxs-lookup"><span data-stu-id="8910f-109">By default, when you install Puppeteer, the installer downloads a recent version of [Chromium][ChromiumHome], the open-source browser that [Microsoft Edge is also built upon][MicrosoftBlogsWindowsExperience20181206].</span></span>  <span data-ttu-id="8910f-110">如果已安装了 Microsoft Edge \ (Chromium \ ) ，则可以使用 [puppeteer-core][PuppeteerApivscore]。</span><span class="sxs-lookup"><span data-stu-id="8910f-110">If you have Microsoft Edge \(Chromium\) installed, you may use [puppeteer-core][PuppeteerApivscore].</span></span>  `puppeteer-core` <span data-ttu-id="8910f-111">是一种轻量级版本的 Puppeteer，用于启动现有的浏览器安装，如 Microsoft Edge \ (Chromium \ ) 。</span><span class="sxs-lookup"><span data-stu-id="8910f-111">is a lightweight version of Puppeteer that launches an existing browser installation, like Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="8910f-112">若要下载 Microsoft Edge \ (Chromium \ ) ，请导航到 " [下载 Microsoft Edge 预览体验计划" 频道][MicrosoftedgeinsiderDownload]。</span><span class="sxs-lookup"><span data-stu-id="8910f-112">To download Microsoft Edge \(Chromium\), navigate to [Download Microsoft Edge Insider Channels][MicrosoftedgeinsiderDownload].</span></span>  

## <span data-ttu-id="8910f-113">安装 puppeteer</span><span class="sxs-lookup"><span data-stu-id="8910f-113">Installing puppeteer-core</span></span>  

<span data-ttu-id="8910f-114">你可以 `puppeteer-core` 通过以下命令之一添加到你的网站或应用。</span><span class="sxs-lookup"><span data-stu-id="8910f-114">You may add `puppeteer-core` to your website or app with one of the following commands.</span></span>  

```shell
npm i puppeteer-core
```  

```shell
yarn add puppeteer-core
```  

## <span data-ttu-id="8910f-115">通过 puppeteer 启动 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="8910f-115">Launch Microsoft Edge with puppeteer-core</span></span>  

> [!NOTE]
> `puppeteer-core` <span data-ttu-id="8910f-116">依赖于节点 v 8.9.0 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="8910f-116">relies on Node v8.9.0 or later.</span></span>  <span data-ttu-id="8910f-117">下面的示例使用 `async` / `await` 了仅在节点 v 7.6.0 或更高版本中才受支持的示例。</span><span class="sxs-lookup"><span data-stu-id="8910f-117">The example below uses `async`/`await` which is only supported in Node v7.6.0 or later.</span></span>  <span data-ttu-id="8910f-118">`node -v`从命令行运行以确保你有兼容版本的 Node.js。</span><span class="sxs-lookup"><span data-stu-id="8910f-118">Run `node -v` from the command-line to ensure you have a compatible version of Node.js.</span></span>  

`puppeteer-core` <span data-ttu-id="8910f-119">应熟悉其他浏览器测试框架（如 [WebDriver][WebDriverEdgehtmlMain]）的用户。</span><span class="sxs-lookup"><span data-stu-id="8910f-119">should be familiar to users of other browser-testing frameworks like [WebDriver][WebDriverEdgehtmlMain].</span></span>  <span data-ttu-id="8910f-120">创建一个浏览器实例，打开一个页面，然后使用 Puppeteer API 对其进行操作。</span><span class="sxs-lookup"><span data-stu-id="8910f-120">You create an instance of the browser, open a page, and then manipulate it with the Puppeteer API.</span></span>  <span data-ttu-id="8910f-121">在以下代码示例中， `puppeteer-core` 启动 Microsoft Edge \ (Chromium \ ) ，导航到 `https://www.microsoftedgeinsider.com` 并将屏幕截图另存为 `example.png` 。</span><span class="sxs-lookup"><span data-stu-id="8910f-121">In the following code sample, `puppeteer-core` launches Microsoft Edge \(Chromium\), navigates to `https://www.microsoftedgeinsider.com`, and saves a screenshot as `example.png`.</span></span>  

<span data-ttu-id="8910f-122">复制以下代码片段并将其另存为 `example.js` 。</span><span class="sxs-lookup"><span data-stu-id="8910f-122">Copy the following code snippet and save it as `example.js`.</span></span>  

```javascript
const puppeteer = require('puppeteer-core');

(async () => {
  const browser = await puppeteer.launch({
    executablePath: 'C:\\Program Files (x86)\\Microsoft\\Edge Dev\\Application\\msedge.exe'
  });
  const page = await browser.newPage();
  await page.goto('https://www.microsoftedgeinsider.com');
  await page.screenshot({path: 'example.png'});

  await browser.close();
})();
```  

<span data-ttu-id="8910f-123">更改 `executablePath` 为指向 Microsoft Edge \ (Chromium \ ) 的安装。</span><span class="sxs-lookup"><span data-stu-id="8910f-123">Change `executablePath` to point to your installation of Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="8910f-124">例如，在 macOS 上，" `executablePath` Microsoft Edge" 的 "关于" 应设置为 `/Applications/Microsoft\ Edge\ Canary.app/` 。</span><span class="sxs-lookup"><span data-stu-id="8910f-124">For example, on macOS, the `executablePath` for Microsoft Edge Canary should be set to `/Applications/Microsoft\ Edge\ Canary.app/`.</span></span>  <span data-ttu-id="8910f-125">若要查找 `executablePath` ，请导航到 `edge://version` 该页面并复制该页面上的 **可执行路径** ，或安装带有以下命令之一的 [edge 路径][npmEdgePaths] 程序包。</span><span class="sxs-lookup"><span data-stu-id="8910f-125">To find the `executablePath`, navigate to `edge://version` and copy the **Executable path** on that page or install the [edge-paths][npmEdgePaths] package with one of the following commands.</span></span>  

```shell
npm i edge-paths
```  

```shell
yarn add edge-paths
```  
 
<span data-ttu-id="8910f-126">下面的代码示例使用 [edge 路径][npmEdgePaths] 程序包以编程方式查找 Microsoft edge \ (Chromium \ ) 在操作系统上的安装路径。</span><span class="sxs-lookup"><span data-stu-id="8910f-126">The code sample below uses the [edge-paths][npmEdgePaths] package to programmatically find the path to your installation of Microsoft Edge \(Chromium\) on your OS.</span></span>

```javascript
const edgePaths = require("edge-paths");

const EDGE_PATH = edgePaths.getEdgePath();
```

<span data-ttu-id="8910f-127">最后，设置 `executablePath: EDGE_PATH` `example.js` 。</span><span class="sxs-lookup"><span data-stu-id="8910f-127">Finally, set `executablePath: EDGE_PATH` in `example.js`.</span></span>  <span data-ttu-id="8910f-128">保存更改。</span><span class="sxs-lookup"><span data-stu-id="8910f-128">Save your changes.</span></span>  

> [!NOTE]
> <span data-ttu-id="8910f-129">Microsoft Edge \ (EdgeHTML \ ) 不起作用 `puppeteer-core` 。</span><span class="sxs-lookup"><span data-stu-id="8910f-129">Microsoft Edge \(EdgeHTML\) does not work with `puppeteer-core`.</span></span>  <span data-ttu-id="8910f-130">必须安装 [Microsoft Edge 预览体验成员频道][MicrosoftedgeinsiderDownload] 才能继续关注此示例。</span><span class="sxs-lookup"><span data-stu-id="8910f-130">You must install the [Microsoft Edge Insider channels][MicrosoftedgeinsiderDownload] to continue following this example.</span></span>  

<span data-ttu-id="8910f-131">现在， `example.js` 从命令行运行。</span><span class="sxs-lookup"><span data-stu-id="8910f-131">Now, run `example.js` from the command line.</span></span>  

```shell
node example.js
```  

`puppeteer-core` <span data-ttu-id="8910f-132">启动 Microsoft Edge，导航到 `https://www.microsoftedgeinsider.com` 并保存网页的屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="8910f-132">launches Microsoft Edge, navigates to `https://www.microsoftedgeinsider.com`, and saves a screenshot of the webpage.</span></span>  <span data-ttu-id="8910f-133">在 [setViewport ( # B1 ][PuppeteerApipagesetviewport]中自定义屏幕截图大小。</span><span class="sxs-lookup"><span data-stu-id="8910f-133">Customize the screenshot size with [page.setViewport()][PuppeteerApipagesetviewport].</span></span>  

:::image type="complex" source="./media/puppeteer-example.png" alt-text="由 example.js 生成的 example.png 文件" lightbox="./media/puppeteer-example.png":::
   <span data-ttu-id="8910f-135">`example.png`生成的文件</span><span class="sxs-lookup"><span data-stu-id="8910f-135">The `example.png` file produced by</span></span> `example.js`  
:::image-end:::  

<span data-ttu-id="8910f-136">下面的简单示例使用由 Puppeteer 和支持的自动化和测试方案 `puppeteer-core` 。</span><span class="sxs-lookup"><span data-stu-id="8910f-136">The following simple example uses automation and testing scenarios enabled by Puppeteer and `puppeteer-core`.</span></span>  <span data-ttu-id="8910f-137">有关 Puppeteer 及其工作原理的详细信息，请导航到 [Puppeteer][|::ref2::|Main]。</span><span class="sxs-lookup"><span data-stu-id="8910f-137">For more information about Puppeteer and how it works, navigate to [Puppeteer][|::ref2::|Main].</span></span>  

## <span data-ttu-id="8910f-138">与 Microsoft Edge 开发人员工具团队联系</span><span class="sxs-lookup"><span data-stu-id="8910f-138">Getting in touch with the Microsoft Edge DevTools team</span></span>  

<span data-ttu-id="8910f-139">Microsoft Edge 开发人员团队渴望听到有关使用 Puppeteer、 `puppeteer-core` 和 Microsoft Edge 的反馈。</span><span class="sxs-lookup"><span data-stu-id="8910f-139">The Microsoft Edge Developer team is eager to hear your feedback about using Puppeteer, `puppeteer-core`, and Microsoft Edge.</span></span>  <span data-ttu-id="8910f-140">使用 Microsoft Edge DevTools 或 tweet [@EdgeDevTools][TwitterIntentTweetEdgedevtools]中的 "**发送反馈**" 图标，让 Microsoft edge 团队知道您的想法。</span><span class="sxs-lookup"><span data-stu-id="8910f-140">Use the **Send Feedback** icon in the Microsoft Edge DevTools or tweet [@EdgeDevTools][TwitterIntentTweetEdgedevtools] to let the Microsoft Edge team know what you think.</span></span>  


:::image type="complex" source="./devtools-guide-chromium/media/bing-devtools-send-feedback.msft.png" alt-text="Microsoft Edge DevTools 中的 "发送反馈" 图标" lightbox="./devtools-guide-chromium/media/bing-devtools-send-feedback.msft.png":::
   <span data-ttu-id="8910f-142">Microsoft Edge DevTools 中的 " **发送反馈** " 图标</span><span class="sxs-lookup"><span data-stu-id="8910f-142">The **Send Feedback** icon in the Microsoft Edge DevTools</span></span>  
:::image-end:::  

<!--## See also  

*   [WebDriver (Chromium)][WebdriverChromiumMain]  
*   [WebDriver (EdgeHTML)][WebdriverEdgehtmlMain]  
*   [Chrome DevTools Protocol Viewer on GitHub][GithubChromedevtoolsProtocol]  
*   [Microsoft Edge:  Making the web better through more open source collaboration on Microsoft Experience Blog][MicrosoftBlogsWindowsExperience20181206]  
*   [Download Microsoft Edge Insider Channels][MicrosoftedgeinsiderDownload]  
*   [Chromium on The Chromium Projects][ChromiumHome]  
*   [Node.js][NodejsMain]  
*   [Puppeteer][PuppeteerMain]  
*   [puppeteer vs. puppeteer-core][PuppeteerApivscore]  
*   [page.setViewport() on Puppeteer][PuppeteerApipagesetviewport]  
*   [Headless browser on Wikipedia][WikiHeadlessBrowser]  -->  

<!-- links -->  

[WebdriverChromiumMain]: ./webdriver-chromium "WebDriver (Chromium) |Microsoft 文档"  
[WebdriverEdgehtmlMain]: ./webdriver.md "WebDriver (EdgeHTML) |Microsoft 文档"  

[GithubChromedevtoolsProtocol]: https://chromedevtools.github.io/devtools-protocol "Chrome DevTools 协议查看器 |GitHub"  

[MicrosoftBlogsWindowsExperience20181206]: https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration "Microsoft Edge：通过更多打开源协作提高 web 效果 |Microsoft 体验博客"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "下载 Microsoft Edge 预览体验成员频道"  

[ChromiumHome]: https://www.chromium.org/Home "Chromium |Chromium 项目"  

[NodejsMain]: https://nodejs.org "Node.js"  

[npmEdgePaths]: https://www.npmjs.com/package/edge-paths "边缘路径 |npm"  

[PuppeteerMain]: https://pptr.dev "Puppeteer"  
[PuppeteerApivscore]: https://pptr.dev/#?product=Puppeteer&version=v2.0.0&show=api-puppeteer-vs-puppeteer-core "puppeteer 与 puppeteer-核心 |Puppeteer"  
[PuppeteerApipagesetviewport]: https://pptr.dev/#?product=Puppeteer&version=v2.0.0&show=api-pagesetviewportviewport "setViewport (视区) |Puppeteer"  

[TwitterIntentTweetEdgedevtools]: https://twitter.com/intent/tweet?text=@EdgeDevTools "@EdgeDevTools 发布 Tweet |Twitter"  

[WikiHeadlessBrowser]: https://en.wikipedia.org/wiki/Headless_browser "无外设浏览器 |科"  
