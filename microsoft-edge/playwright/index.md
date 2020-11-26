---
description: 在 Microsoft Edge 中使用 Playwright 自动处理和测试
title: 编剧
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/24/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: microsoft edge、web 开发、开发人员、工具、自动化、测试、playwright、node、javascript、npm
ms.openlocfilehash: ac03923fb25da00f07cb70e81ac06b106a6e1452
ms.sourcegitcommit: 2e14ff82350f700d7eabc8d33b3ec3e5fc8c61fa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "11192210"
---
# <span data-ttu-id="975ac-104">编剧</span><span class="sxs-lookup"><span data-stu-id="975ac-104">Playwright</span></span>  

<span data-ttu-id="975ac-105">[Playwright][|::ref1::|Main] 是一种 [Node.js][NodejsMain] 库，可通过单个 API 自动化 [Chromium][ChromiumHome]、 [Firefox][FirefoxMain]和 [WebKit][|::ref2::|Main] 。</span><span class="sxs-lookup"><span data-stu-id="975ac-105">[Playwright][|::ref1::|Main] is a [Node.js][NodejsMain] library to automate [Chromium][ChromiumHome], [Firefox][FirefoxMain], and [WebKit][|::ref2::|Main] with a single API.</span></span>  <span data-ttu-id="975ac-106">Playwright 的构建使跨浏览器 web 自动化功能变得非常绿、功能可靠且速度更快。</span><span class="sxs-lookup"><span data-stu-id="975ac-106">Playwright is built to enable cross-browser web automation that is ever-green, capable, reliable, and fast.</span></span>  <span data-ttu-id="975ac-107">由于 [Microsoft edge 是在开放源代码 Chromium web 平台上构建][MicrosoftBlogsWindowsExperience20181206]的，因此 Playwright 也可以自动执行 Microsoft edge。</span><span class="sxs-lookup"><span data-stu-id="975ac-107">Since [Microsoft Edge is built on the open-source Chromium web platform][MicrosoftBlogsWindowsExperience20181206], Playwright is also able to automate Microsoft Edge.</span></span>  

<span data-ttu-id="975ac-108">默认情况下，Playwright 启动无 [头浏览器][WikiHeadlessBrowser] 。</span><span class="sxs-lookup"><span data-stu-id="975ac-108">Playwright launches [headless browsers][WikiHeadlessBrowser] by default.</span></span>  <span data-ttu-id="975ac-109">无外设浏览器不显示 UI，因此必须使用命令行。</span><span class="sxs-lookup"><span data-stu-id="975ac-109">Headless browsers do not display a UI, so instead you must use the command line.</span></span>  <span data-ttu-id="975ac-110">您也可以将 Playwright 配置为同时运行完全 \ (非无外设 \ ) Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="975ac-110">You may also configure Playwright to run full \(non-headless\) Microsoft Edge as well.</span></span>  

<span data-ttu-id="975ac-111">默认情况下，安装 Playwright 时，安装程序将下载 [Chromium][ChromiumHome]、 [Firefox][FirefoxMain]和 [WebKit][|::ref3::|Main]。</span><span class="sxs-lookup"><span data-stu-id="975ac-111">By default, when you install Playwright, the installer downloads [Chromium][ChromiumHome], [Firefox][FirefoxMain], and [WebKit][|::ref3::|Main].</span></span>  <span data-ttu-id="975ac-112">如果你有 Microsoft Edge \ (Chromium \ ) 已安装，Playwright 只需更改一个单行代码即可在 Microsoft Edge 中测试你的网站或应用。</span><span class="sxs-lookup"><span data-stu-id="975ac-112">If you have Microsoft Edge \(Chromium\) installed as well, Playwright just needs a one-line code change to test your website or app in Microsoft Edge.</span></span>  <span data-ttu-id="975ac-113">若要下载 Microsoft Edge \ (Chromium \ ) ，请导航到 " [下载 Microsoft edge][MicrosoftEdgeDownload]"。</span><span class="sxs-lookup"><span data-stu-id="975ac-113">To download Microsoft Edge \(Chromium\), navigate to [Download Microsoft Edge][MicrosoftEdgeDownload].</span></span>  

## <span data-ttu-id="975ac-114">安装 Playwright</span><span class="sxs-lookup"><span data-stu-id="975ac-114">Installing Playwright</span></span>  

<span data-ttu-id="975ac-115">安装 [Playwright][|::ref4::|Main] 以通过以下命令测试你的网站或应用。</span><span class="sxs-lookup"><span data-stu-id="975ac-115">Install [Playwright][|::ref4::|Main] to test your website or app with the following command.</span></span>  

```shell
npm i playwright
```  

## <span data-ttu-id="975ac-116">通过 Playwright 启动 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="975ac-116">Launch Microsoft Edge with Playwright</span></span>  

> [!NOTE]
> <span data-ttu-id="975ac-117">[Playwright][|::ref5::|Main] 需要 Node.js 版本10.17 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="975ac-117">[Playwright][|::ref5::|Main] requires Node.js version 10.17 or above.</span></span> <span data-ttu-id="975ac-118">`node -v`从命令行运行以确保你有兼容版本的 Node.js。</span><span class="sxs-lookup"><span data-stu-id="975ac-118">Run `node -v` from the command line to ensure you have a compatible version of Node.js.</span></span>  <span data-ttu-id="975ac-119">Chromium、Firefox 和 WebKit 的浏览器二进制文件在 Windows、macOS 和 Linux 中均可正常工作。</span><span class="sxs-lookup"><span data-stu-id="975ac-119">The browser binaries for Chromium, Firefox and WebKit work across Windows, macOS, and Linux.</span></span> <span data-ttu-id="975ac-120">有关详细信息，请导航到 [Playwright 系统要求][PlaywrightSystemRequirements]。</span><span class="sxs-lookup"><span data-stu-id="975ac-120">For more information, navigate to [Playwright System Requirements][PlaywrightSystemRequirements].</span></span>  

<span data-ttu-id="975ac-121">Playwright 应熟悉其他浏览器测试框架（如 [WebDriver][WebDriverChromiumMain] 或 [Puppeteer][PuppeteerMain]）的用户。</span><span class="sxs-lookup"><span data-stu-id="975ac-121">Playwright should be familiar to users of other browser-testing frameworks like [WebDriver][WebDriverChromiumMain] or [Puppeteer][PuppeteerMain].</span></span>  <span data-ttu-id="975ac-122">创建一个浏览器实例，打开一个页面，然后使用 [PLAYWRIGHT API][PlaywrightAPIReference]对其进行操作。</span><span class="sxs-lookup"><span data-stu-id="975ac-122">You create an instance of the browser, open a page, and then manipulate it with the [Playwright API][PlaywrightAPIReference].</span></span>  <span data-ttu-id="975ac-123">在以下代码段中，Playwright 将启动 Microsoft Edge \ (Chromium \ ) ，导航到 `https://www.microsoft.com/edge` 并将屏幕截图另存为 `example.png` 。</span><span class="sxs-lookup"><span data-stu-id="975ac-123">In the following code snippet, Playwright launches Microsoft Edge \(Chromium\), navigates to `https://www.microsoft.com/edge`, and saves a screenshot as `example.png`.</span></span>  

<span data-ttu-id="975ac-124">复制以下代码片段并将其另存为 `example.js` 。</span><span class="sxs-lookup"><span data-stu-id="975ac-124">Copy the following code snippet and save it as `example.js`.</span></span>  

```javascript
const { chromium } = require('playwright');

(async () => {
  const browser = await chromium.launch({
    executablePath: 'C:\\Program Files (x86)\\Microsoft\\Edge Dev\\Application\\msedge.exe'
  });
  const page = await browser.newPage();
  await page.goto('https://www.microsoft.com/edge');
  await page.screenshot({path: 'example.png'});

  await browser.close();
})();
```  

<span data-ttu-id="975ac-125">更改 `executablePath` 为指向 Microsoft Edge \ (Chromium \ ) 的安装。</span><span class="sxs-lookup"><span data-stu-id="975ac-125">Change `executablePath` to point to your installation of Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="975ac-126">例如，在 macOS 上，" `executablePath` Microsoft Edge" 的 "关于" 应设置为 `/Applications/Microsoft\ Edge\ Canary.app/` 。</span><span class="sxs-lookup"><span data-stu-id="975ac-126">For example, on macOS, the `executablePath` for Microsoft Edge Canary should be set to `/Applications/Microsoft\ Edge\ Canary.app/`.</span></span>  <span data-ttu-id="975ac-127">若要查找 `executablePath` ，请导航到 `edge://version` 该页面并复制该页面上的 **可执行路径** ，或通过以下命令安装 [edge 路径][npmEdgePaths] 程序包。</span><span class="sxs-lookup"><span data-stu-id="975ac-127">To find the `executablePath`, navigate to `edge://version` and copy the **Executable path** on that page or install the [edge-paths][npmEdgePaths] package with the following command.</span></span>  

```shell
npm i edge-paths
```  

<span data-ttu-id="975ac-128">以下代码片段使用 [edge 路径][npmEdgePaths] 程序包以编程方式查找你的 Microsoft edge \ (Chromium \ ) 在你的操作系统上的安装路径。</span><span class="sxs-lookup"><span data-stu-id="975ac-128">The following code snippet uses the [edge-paths][npmEdgePaths] package to programmatically find the path to your installation of Microsoft Edge \(Chromium\) on your OS.</span></span>  

```javascript
const edgePaths = require("edge-paths");

const EDGE_PATH = edgePaths.getEdgePath();
```  

<span data-ttu-id="975ac-129">最后，设置 `executablePath: EDGE_PATH` `example.js` 。</span><span class="sxs-lookup"><span data-stu-id="975ac-129">Finally, set `executablePath: EDGE_PATH` in `example.js`.</span></span>  <span data-ttu-id="975ac-130">保存更改。</span><span class="sxs-lookup"><span data-stu-id="975ac-130">Save your changes.</span></span>  

> [!NOTE]
> <span data-ttu-id="975ac-131">Microsoft Edge \ (EdgeHTML \ ) 与 Playwright 不配合使用。</span><span class="sxs-lookup"><span data-stu-id="975ac-131">Microsoft Edge \(EdgeHTML\) does not work with Playwright.</span></span>  <span data-ttu-id="975ac-132">必须安装 [Microsoft Edge \ (Chromium \ ) ][MicrosoftEdgeDownload] ，才能继续关注本示例。</span><span class="sxs-lookup"><span data-stu-id="975ac-132">You must install [Microsoft Edge \(Chromium\)][MicrosoftEdgeDownload] to continue following this example.</span></span>  

<span data-ttu-id="975ac-133">现在 `example.js` 从命令行运行。</span><span class="sxs-lookup"><span data-stu-id="975ac-133">Now run `example.js` from the command line.</span></span>  

```shell
node example.js
```  

<span data-ttu-id="975ac-134">Playwright 启动 Microsoft Edge，导航到 `https://www.microsoft.com/edge` 并保存页面的屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="975ac-134">Playwright launches Microsoft Edge, navigates to `https://www.microsoft.com/edge`, and saves a screenshot of the page.</span></span>  <span data-ttu-id="975ac-135">你可以自定义 [setViewportSize ( # B1 ][PlaywrightAPIPageSetViewport]的页面大小。</span><span class="sxs-lookup"><span data-stu-id="975ac-135">You may customize the page size with [page.setViewportSize()][PlaywrightAPIPageSetViewport].</span></span>  

:::image type="complex" source="../media/playwright-example.png" alt-text="由 example.js 生成的 example.png 文件" lightbox="../media/playwright-example.png":::
    <span data-ttu-id="975ac-137">`example.png`生成的文件</span><span class="sxs-lookup"><span data-stu-id="975ac-137">The `example.png` file produced by</span></span> `example.js`  
:::image-end:::  

`example.js` <span data-ttu-id="975ac-138">只是由 Playwright 启用的自动化和测试方案的简单演示。</span><span class="sxs-lookup"><span data-stu-id="975ac-138">is just a simple demonstration of the automation and testing scenarios enabled by Playwright.</span></span>  <span data-ttu-id="975ac-139">若要在多个 web 浏览器中拍摄屏幕截图，请更改以下代码。</span><span class="sxs-lookup"><span data-stu-id="975ac-139">To take screenshots in multiple web browsers, change the following code.</span></span>  

*   <span data-ttu-id="975ac-140">Chromium</span><span class="sxs-lookup"><span data-stu-id="975ac-140">Chromium</span></span>  `await chromium.launch()`  
*   <span data-ttu-id="975ac-141">Firefox</span><span class="sxs-lookup"><span data-stu-id="975ac-141">Firefox</span></span>  `await firefox.launch()`  
*   <span data-ttu-id="975ac-142">WebKit</span><span class="sxs-lookup"><span data-stu-id="975ac-142">WebKit</span></span>  `await webkit.launch()`  

<span data-ttu-id="975ac-143">有关 Playwright 的详细信息，请导航到 [Playwright 网站][|::ref6::|Main]。</span><span class="sxs-lookup"><span data-stu-id="975ac-143">For more information about Playwright, navigate to the [Playwright website][|::ref6::|Main].</span></span>  <span data-ttu-id="975ac-144">查看 GitHub 上的  [Playwright][PlaywrightRepo] 存储库。</span><span class="sxs-lookup"><span data-stu-id="975ac-144">Check out the  [Playwright repo][PlaywrightRepo] on GitHub.</span></span>  <span data-ttu-id="975ac-145">若要与 Playwright 共享你的网站或应用的自动化和测试反馈，请将 [问题归档][PlaywrightRepoNewIssue]。</span><span class="sxs-lookup"><span data-stu-id="975ac-145">To share your feedback on automating and testing your website or app with Playwright, [file an issue][PlaywrightRepoNewIssue].</span></span>  

## <span data-ttu-id="975ac-146">与 Microsoft Edge 开发人员工具团队联系</span><span class="sxs-lookup"><span data-stu-id="975ac-146">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../devtools-guide-chromium/includes/contact-devtools-team-note.md)]  

<!-- links -->  

[WebdriverChromiumMain]: ../webdriver-chromium/index.md "WebDriver (Chromium) |Microsoft 文档"  
[PuppeteerMain]: ../puppeteer.md "Puppeteer |Microsoft 文档"  

[MicrosoftBlogsWindowsExperience20181206]: https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration "Microsoft Edge：通过更多打开源协作提高 web 效果 |Microsoft 体验博客"  

[MicrosoftEdgeDownload]: https://microsoft.com/edge "下载 Microsoft Edge"  

[ChromiumHome]: https://www.chromium.org/Home "Chromium |Chromium 项目"  

[FirefoxMain]: https://www.mozilla.org/firefox "Mozilla Firefox"  

[NodejsMain]: https://nodejs.org "Node.js"  

[npmEdgePaths]: https://www.npmjs.com/package/edge-paths "边缘-路径 |npm"  

[PlaywrightMain]: https://playwright.dev "Playwright"  
[PlaywrightAPIReference]: https://playwright.dev#?path=docs/api.md "Playwright API 参考"  
[PlaywrightAPIPageSetViewport]: https://playwright.dev#?path=docs%2Fapi.md&q=pagesetviewportsizeviewportsize "setViewportSize (viewportSize) |Playwright API 参考"    
[PlaywrightSystemRequirements]: https://playwright.dev#?path=docs/intro.md&q=system-requirements "Playwright 系统要求"  

[PlaywrightRepo]: https://github.com/microsoft/playwright "Playwright |GitHub"  
[PlaywrightRepoNewIssue]: https://github.com/microsoft/playwright/issues/new/choose "Playwright 存储库中的新问题 |GitHub"  

[WebKitMain]: https://webkit.org "WebKit"  

[WikiHeadlessBrowser]: https://en.wikipedia.org/wiki/Headless_browser "无外设浏览器 |科"  
