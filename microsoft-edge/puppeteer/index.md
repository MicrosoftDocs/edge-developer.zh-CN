---
description: 使用安装器在 Microsoft Edge 中自动执行和测试
title: Puppeteer
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/02/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: microsoft edge， Web 开发， 开发人员， 工具， 自动化， 测试
ms.openlocfilehash: 99d873a9b3988cb8a2827ecc9a69d574a196b037
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232054"
---
# <span data-ttu-id="fefee-104">Puppeteer 概述</span><span class="sxs-lookup"><span data-stu-id="fefee-104">Puppeteer overview</span></span>  

<span data-ttu-id="fefee-105">[表示器是][|::ref1::|Main][一个][NodejsMain]节点库，它提供高级 API 来控制 Microsoft Edge \ (Chromium\) [DevTools 协议][GithubChromedevtoolsProtocol]。</span><span class="sxs-lookup"><span data-stu-id="fefee-105">[Puppeteer][|::ref1::|Main] is a [Node][NodejsMain] library that provides a high-level API to control Microsoft Edge \(Chromium\) using the [DevTools Protocol][GithubChromedevtoolsProtocol].</span></span>  <span data-ttu-id="fefee-106">默认情况下，安装 [器将启动无][WikiHeadlessBrowser] 头浏览器。</span><span class="sxs-lookup"><span data-stu-id="fefee-106">Puppeteer launches [headless browsers][WikiHeadlessBrowser] by default.</span></span>  <span data-ttu-id="fefee-107">无头浏览器不显示 UI，因此您必须使用命令行。</span><span class="sxs-lookup"><span data-stu-id="fefee-107">Headless browsers do not display a UI, so instead you must use the command line.</span></span>  <span data-ttu-id="fefee-108">还可以将安装安装器配置为运行完全 \ (无头\) Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="fefee-108">You may also configure Puppeteer to run full \(non-headless\) Microsoft Edge as well.</span></span>  

<span data-ttu-id="fefee-109">默认情况下，安装器时，安装程序会下载 [最新版本的 Chromium，][ChromiumHome]这是 Microsoft Edge 也基于的开放 [源代码浏览器][MicrosoftBlogsWindowsExperience20181206]。</span><span class="sxs-lookup"><span data-stu-id="fefee-109">By default, when you install Puppeteer, the installer downloads a recent version of [Chromium][ChromiumHome], the open-source browser that [Microsoft Edge is also built upon][MicrosoftBlogsWindowsExperience20181206].</span></span>  <span data-ttu-id="fefee-110">如果已安装 Microsoft Edge \ (Chromium\) ， [可以使用安装程序核心][PuppeteerApivscore]。</span><span class="sxs-lookup"><span data-stu-id="fefee-110">If you have Microsoft Edge \(Chromium\) installed, you may use [puppeteer-core][PuppeteerApivscore].</span></span>  `puppeteer-core` <span data-ttu-id="fefee-111">是启动现有浏览器安装（如 Microsoft Edge \ (Chromium\) ）的轻型版本。</span><span class="sxs-lookup"><span data-stu-id="fefee-111">is a lightweight version of Puppeteer that launches an existing browser installation, like Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="fefee-112">若要下载 Microsoft Edge \ (Chromium\) ，请导航到"下载[Microsoft Edge 预览体验成员频道"。][MicrosoftedgeinsiderDownload]</span><span class="sxs-lookup"><span data-stu-id="fefee-112">To download Microsoft Edge \(Chromium\), navigate to [Download Microsoft Edge Insider Channels][MicrosoftedgeinsiderDownload].</span></span>  

## <span data-ttu-id="fefee-113">安装安装程序核心</span><span class="sxs-lookup"><span data-stu-id="fefee-113">Installing puppeteer-core</span></span>  

<span data-ttu-id="fefee-114">可以使用以下命令之一 `puppeteer-core` 添加到网站或应用。</span><span class="sxs-lookup"><span data-stu-id="fefee-114">You may add `puppeteer-core` to your website or app with one of the following commands.</span></span>  

```shell
npm i puppeteer-core
```  

```shell
yarn add puppeteer-core
```  

## <span data-ttu-id="fefee-115">启动具有中心处理器核心的 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="fefee-115">Launch Microsoft Edge with puppeteer-core</span></span>  

> [!NOTE]
> `puppeteer-core` <span data-ttu-id="fefee-116">依赖于 Node v8.9.0 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="fefee-116">relies on Node v8.9.0 or later.</span></span>  <span data-ttu-id="fefee-117">以下示例使用仅在 Node `async` / `await` v7.6.0 或更高版本中支持的示例。</span><span class="sxs-lookup"><span data-stu-id="fefee-117">The example below uses `async`/`await` which is only supported in Node v7.6.0 or later.</span></span>  <span data-ttu-id="fefee-118">从 `node -v` 命令行运行，以确保你的应用程序具有兼容的Node.js。</span><span class="sxs-lookup"><span data-stu-id="fefee-118">Run `node -v` from the command-line to ensure you have a compatible version of Node.js.</span></span>  

`puppeteer-core` <span data-ttu-id="fefee-119">应熟悉其他浏览器测试框架（如 [WebDriver）的用户][WebdriverChromiumMain]。</span><span class="sxs-lookup"><span data-stu-id="fefee-119">should be familiar to users of other browser-testing-frameworks like [WebDriver][WebdriverChromiumMain].</span></span>  <span data-ttu-id="fefee-120">创建浏览器实例，打开一个页面，然后使用更新程序 API 对其进行操作。</span><span class="sxs-lookup"><span data-stu-id="fefee-120">You create an instance of the browser, open a page, and then manipulate it with the Puppeteer API.</span></span>  <span data-ttu-id="fefee-121">In the following code sample， `puppeteer-core` launches Microsoft Edge \ (Chromium\) ， navigates `https://www.microsoftedgeinsider.com` to， and saves a screenshot as `example.png` .</span><span class="sxs-lookup"><span data-stu-id="fefee-121">In the following code sample, `puppeteer-core` launches Microsoft Edge \(Chromium\), navigates to `https://www.microsoftedgeinsider.com`, and saves a screenshot as `example.png`.</span></span>  

<span data-ttu-id="fefee-122">复制以下代码段并将其另存为 `example.js` 。</span><span class="sxs-lookup"><span data-stu-id="fefee-122">Copy the following code snippet and save it as `example.js`.</span></span>  

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

<span data-ttu-id="fefee-123">更改为 `executablePath` 指向安装 Microsoft Edge \ (Chromium\) 。</span><span class="sxs-lookup"><span data-stu-id="fefee-123">Change `executablePath` to point to your installation of Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="fefee-124">例如，在 macOS 上 `executablePath` ，Microsoft Edge Canary 应设置为 `/Applications/Microsoft\ Edge\ Canary.app/` 。</span><span class="sxs-lookup"><span data-stu-id="fefee-124">For example, on macOS, the `executablePath` for Microsoft Edge Canary should be set to `/Applications/Microsoft\ Edge\ Canary.app/`.</span></span>  <span data-ttu-id="fefee-125">若要查找，请导航到该页面上的"可执行文件"路径并复制该路径，或者使用以下命令之一安装边缘 `executablePath` `edge://version` 路径包。 \*\*\*\* [][npmEdgePaths]</span><span class="sxs-lookup"><span data-stu-id="fefee-125">To find the `executablePath`, navigate to `edge://version` and copy the **Executable path** on that page or install the [edge-paths][npmEdgePaths] package with one of the following commands.</span></span>  

```shell
npm i edge-paths
```  

```shell
yarn add edge-paths
```  
 
<span data-ttu-id="fefee-126">下面的代码示例使用 [边缘][npmEdgePaths] 路径包以编程方式查找在操作系统上安装 Microsoft Edge \ (Chromium\) 的路径。</span><span class="sxs-lookup"><span data-stu-id="fefee-126">The code sample below uses the [edge-paths][npmEdgePaths] package to programmatically find the path to your installation of Microsoft Edge \(Chromium\) on your OS.</span></span>

```javascript
const edgePaths = require("edge-paths");

const EDGE_PATH = edgePaths.getEdgePath();
```

<span data-ttu-id="fefee-127">最后，在 `executablePath: EDGE_PATH` `example.js` 中设置。</span><span class="sxs-lookup"><span data-stu-id="fefee-127">Finally, set `executablePath: EDGE_PATH` in `example.js`.</span></span>  <span data-ttu-id="fefee-128">保存更改。</span><span class="sxs-lookup"><span data-stu-id="fefee-128">Save your changes.</span></span>  

> [!NOTE]
> <span data-ttu-id="fefee-129">Microsoft Edge \ (EdgeHTML\) 不能与 `puppeteer-core` 。</span><span class="sxs-lookup"><span data-stu-id="fefee-129">Microsoft Edge \(EdgeHTML\) does not work with `puppeteer-core`.</span></span>  <span data-ttu-id="fefee-130">必须安装 [Microsoft Edge 预览体验成员频道][MicrosoftedgeinsiderDownload] ，以继续遵循此示例。</span><span class="sxs-lookup"><span data-stu-id="fefee-130">You must install the [Microsoft Edge Insider channels][MicrosoftedgeinsiderDownload] to continue following this example.</span></span>  

<span data-ttu-id="fefee-131">现在， `example.js` 从命令行运行。</span><span class="sxs-lookup"><span data-stu-id="fefee-131">Now, run `example.js` from the command line.</span></span>  

```shell
node example.js
```  

`puppeteer-core` <span data-ttu-id="fefee-132">启动 Microsoft Edge，导航到 `https://www.microsoftedgeinsider.com` 并保存网页的屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="fefee-132">launches Microsoft Edge, navigates to `https://www.microsoftedgeinsider.com`, and saves a screenshot of the webpage.</span></span>  <span data-ttu-id="fefee-133">使用 [page.setViewport () 自定义屏幕截图大小 ][PuppeteerApipagesetviewport]。</span><span class="sxs-lookup"><span data-stu-id="fefee-133">Customize the screenshot size with [page.setViewport()][PuppeteerApipagesetviewport].</span></span>  

:::image type="complex" source="./media/puppeteer-example.png" alt-text="由example.png生成的example.js" lightbox="./media/puppeteer-example.png":::
   <span data-ttu-id="fefee-135">`example.png`生成的文件</span><span class="sxs-lookup"><span data-stu-id="fefee-135">The `example.png` file produced by</span></span> `example.js`  
:::image-end:::  

<span data-ttu-id="fefee-136">这只是一个简单的示例，演示了由一名和一名用户启用的自动化和测试方案 `puppeteer-core` 。</span><span class="sxs-lookup"><span data-stu-id="fefee-136">This is just a simple example of the automation and testing scenarios enabled by Puppeteer and `puppeteer-core`.</span></span>  <span data-ttu-id="fefee-137">有关一些产品及其工作方式的信息，请参阅 ["一][|::ref2::|Main]线"。</span><span class="sxs-lookup"><span data-stu-id="fefee-137">For more information about Puppeteer and how it works, see [Puppeteer][|::ref2::|Main].</span></span>  

## <span data-ttu-id="fefee-138">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="fefee-138">Getting in touch with the Microsoft Edge DevTools team</span></span>  

<span data-ttu-id="fefee-139">Microsoft Edge 开发人员团队希望倾听你有关使用一线和 Microsoft `puppeteer-core` Edge 的反馈。</span><span class="sxs-lookup"><span data-stu-id="fefee-139">The Microsoft Edge Developer team is eager to hear your feedback about using Puppeteer, `puppeteer-core`, and Microsoft Edge.</span></span>  <span data-ttu-id="fefee-140">使用\*\*\*\* Microsoft Edge DevTools 或推文@EdgeDevTools中的"发送反馈"[图标][TwitterIntentTweetEdgedevtools]，让 Microsoft Edge 团队了解你的想法。</span><span class="sxs-lookup"><span data-stu-id="fefee-140">Use the **Send Feedback** icon in the Microsoft Edge DevTools or tweet [@EdgeDevTools][TwitterIntentTweetEdgedevtools] to let the Microsoft Edge team know what you think.</span></span>  

:::image type="complex" source="../devtools-guide-chromium/media/bing-devtools-send-feedback.msft.png" alt-text="Microsoft Edge DevTools 中的“发送反馈”图标" lightbox="../devtools-guide-chromium/media/bing-devtools-send-feedback.msft.png":::
   <span data-ttu-id="fefee-142">Microsoft **Edge** DevTools 中的"发送反馈"图标</span><span class="sxs-lookup"><span data-stu-id="fefee-142">The **Send Feedback** icon in the Microsoft Edge DevTools</span></span>  
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

[WebdriverChromiumMain]: ../webdriver-chromium/index.md "WebDriver (Chromium) |Microsoft Docs"  
<!--  [WebdriverEdgehtmlMain]: ../edgehtml/webdriver/index.md "WebDriver (EdgeHTML) | Microsoft Docs"  -->  

[GithubChromedevtoolsProtocol]: https://chromedevtools.github.io/devtools-protocol "Chrome DevTools 协议查看器 |GitHub"  

[MicrosoftBlogsWindowsExperience20181206]: https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration "Microsoft Edge：通过更多开放源代码协作改善 Web |Microsoft 体验博客"  

[MicrosoftedgeinsiderDownload]: https://www.microsoftedgeinsider.com/download "下载 Microsoft Edge 预览体验成员频道"  

[ChromiumHome]: https://www.chromium.org/Home "Chromium |Chromium 项目"  

[NodejsMain]: https://nodejs.org "Node.js"  

[npmEdgePaths]: https://www.npmjs.com/package/edge-paths "边缘路径 |npm"  

[PuppeteerMain]: https://pptr.dev "一线"  
[PuppeteerApivscore]: https://pptr.dev/#?product=Puppeteer&version=v2.0.0&show=api-puppeteer-vs-puppeteer-core "与er-core |一线"  
[PuppeteerApipagesetviewport]: https://pptr.dev/#?product=Puppeteer&version=v2.0.0&show=api-pagesetviewportviewport "page.setViewport (视口) |一线"  

[TwitterIntentTweetEdgedevtools]: https://twitter.com/intent/tweet?text=@EdgeDevTools "@EdgeDevTools - 发布推文 |Twitter"  

[WikiHeadlessBrowser]: https://en.wikipedia.org/wiki/Headless_browser "无头浏览器 |Wikipedia"  
