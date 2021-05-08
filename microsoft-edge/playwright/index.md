---
description: 使用 Playwright 自动执行和测试Microsoft Edge
title: 编剧
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/24/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: devtools
keywords: microsoft edge， Web 开发， 开发人员， 工具， 自动化， 测试， playwright， 节点， javascript， npm
ms.openlocfilehash: 5ce51864177731dd1bafb845466abb00cce1e0aa
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11231081"
---
# <span data-ttu-id="8a32e-104">编剧</span><span class="sxs-lookup"><span data-stu-id="8a32e-104">Playwright</span></span>  

<span data-ttu-id="8a32e-105">[Playwright][|::ref1::|Main]是[一Node.js][NodejsMain] API 自动[Chromium、Firefox][FirefoxMain]和[WebKit][|::ref2::|Main]的一个库。 [][ChromiumHome]</span><span class="sxs-lookup"><span data-stu-id="8a32e-105">[Playwright][|::ref1::|Main] is a [Node.js][NodejsMain] library to automate [Chromium][ChromiumHome], [Firefox][FirefoxMain], and [WebKit][|::ref2::|Main] with a single API.</span></span>  <span data-ttu-id="8a32e-106">Playwright 是专为启用跨浏览器 Web 自动化而构建的，该自动化功能非常绿色、功能可靠且快速。</span><span class="sxs-lookup"><span data-stu-id="8a32e-106">Playwright is built to enable cross-browser web automation that is ever-green, capable, reliable, and fast.</span></span>  <span data-ttu-id="8a32e-107">由于[Microsoft Edge构建于开放源代码Chromium，][MicrosoftBlogsWindowsExperience20181206]因此 Playwright 还能够自动Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="8a32e-107">Since [Microsoft Edge is built on the open-source Chromium web platform][MicrosoftBlogsWindowsExperience20181206], Playwright is also able to automate Microsoft Edge.</span></span>  

<span data-ttu-id="8a32e-108">默认情况下，Playwright [启动无][WikiHeadlessBrowser] 头浏览器。</span><span class="sxs-lookup"><span data-stu-id="8a32e-108">Playwright launches [headless browsers][WikiHeadlessBrowser] by default.</span></span>  <span data-ttu-id="8a32e-109">无头浏览器不显示 UI，因此您必须使用命令行。</span><span class="sxs-lookup"><span data-stu-id="8a32e-109">Headless browsers do not display a UI, so instead you must use the command line.</span></span>  <span data-ttu-id="8a32e-110">还可以将 Playwright 配置为运行完整 \ (无头\) Microsoft Edge运行。</span><span class="sxs-lookup"><span data-stu-id="8a32e-110">You may also configure Playwright to run full \(non-headless\) Microsoft Edge as well.</span></span>  

<span data-ttu-id="8a32e-111">默认情况下，安装 Playwright 时，安装程序会[Chromium、Firefox][FirefoxMain]和[WebKit。][|::ref3::|Main] [][ChromiumHome]</span><span class="sxs-lookup"><span data-stu-id="8a32e-111">By default, when you install Playwright, the installer downloads [Chromium][ChromiumHome], [Firefox][FirefoxMain], and [WebKit][|::ref3::|Main].</span></span>  <span data-ttu-id="8a32e-112">如果你还安装了 \Microsoft Edge \ (Chromium\) ，Playwright 只需更改一行代码，在 Microsoft Edge 中测试您的网站或应用。</span><span class="sxs-lookup"><span data-stu-id="8a32e-112">If you have Microsoft Edge \(Chromium\) installed as well, Playwright just needs a one-line code change to test your website or app in Microsoft Edge.</span></span>  <span data-ttu-id="8a32e-113">若要下载Microsoft Edge \ (Chromium\) ，请导航到"下载[Microsoft Edge"。][MicrosoftEdgeDownload]</span><span class="sxs-lookup"><span data-stu-id="8a32e-113">To download Microsoft Edge \(Chromium\), navigate to [Download Microsoft Edge][MicrosoftEdgeDownload].</span></span>  

## <span data-ttu-id="8a32e-114">安装 Playwright</span><span class="sxs-lookup"><span data-stu-id="8a32e-114">Installing Playwright</span></span>  

<span data-ttu-id="8a32e-115">安装 [Playwright][|::ref4::|Main] 以通过以下命令测试网站或应用。</span><span class="sxs-lookup"><span data-stu-id="8a32e-115">Install [Playwright][|::ref4::|Main] to test your website or app with the following command.</span></span>  

```shell
npm i playwright
```  

## <span data-ttu-id="8a32e-116">启动Microsoft Edge Playwright</span><span class="sxs-lookup"><span data-stu-id="8a32e-116">Launch Microsoft Edge with Playwright</span></span>  

> [!NOTE]
> <span data-ttu-id="8a32e-117">[Playwright][|::ref5::|Main] 需要Node.js版本 10.17 或以上版本。</span><span class="sxs-lookup"><span data-stu-id="8a32e-117">[Playwright][|::ref5::|Main] requires Node.js version 10.17 or above.</span></span> <span data-ttu-id="8a32e-118">从 `node -v` 命令行运行，以确保具有兼容的 Node.js。</span><span class="sxs-lookup"><span data-stu-id="8a32e-118">Run `node -v` from the command line to ensure you have a compatible version of Node.js.</span></span>  <span data-ttu-id="8a32e-119">适用于 Chromium、Firefox 和 WebKit 的浏览器二进制文件跨 Windows、macOS 和 Linux 工作。</span><span class="sxs-lookup"><span data-stu-id="8a32e-119">The browser binaries for Chromium, Firefox and WebKit work across Windows, macOS, and Linux.</span></span> <span data-ttu-id="8a32e-120">有关详细信息，请导航到["Playwright 系统要求"。][PlaywrightSystemRequirements]</span><span class="sxs-lookup"><span data-stu-id="8a32e-120">For more information, navigate to [Playwright System Requirements][PlaywrightSystemRequirements].</span></span>  

<span data-ttu-id="8a32e-121">Playwright 应该为其他浏览器测试框架（如 [WebDriver][WebDriverChromiumMain] 或一台 [）的用户所熟悉][PuppeteerMain]。</span><span class="sxs-lookup"><span data-stu-id="8a32e-121">Playwright should be familiar to users of other browser-testing frameworks like [WebDriver][WebDriverChromiumMain] or [Puppeteer][PuppeteerMain].</span></span>  <span data-ttu-id="8a32e-122">创建浏览器实例，打开页面，然后使用 [Playwright API 对其进行操作][PlaywrightAPIReference]。</span><span class="sxs-lookup"><span data-stu-id="8a32e-122">You create an instance of the browser, open a page, and then manipulate it with the [Playwright API][PlaywrightAPIReference].</span></span>  <span data-ttu-id="8a32e-123">In the following code snippet， Playwright launchs Microsoft Edge \ (Chromium\) ， navigates to `https://www.microsoft.com/edge` ， and saves a screenshot as `example.png` .</span><span class="sxs-lookup"><span data-stu-id="8a32e-123">In the following code snippet, Playwright launches Microsoft Edge \(Chromium\), navigates to `https://www.microsoft.com/edge`, and saves a screenshot as `example.png`.</span></span>  

<span data-ttu-id="8a32e-124">复制以下代码段并将其另存为 `example.js` 。</span><span class="sxs-lookup"><span data-stu-id="8a32e-124">Copy the following code snippet and save it as `example.js`.</span></span>  

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

<span data-ttu-id="8a32e-125">更改为 `executablePath` 指向安装 Microsoft Edge \ (Chromium\) 。</span><span class="sxs-lookup"><span data-stu-id="8a32e-125">Change `executablePath` to point to your installation of Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="8a32e-126">例如，在 macOS 上 `executablePath` ，Microsoft Edge Canary 应设置为 `/Applications/Microsoft\ Edge\ Canary.app/` 。</span><span class="sxs-lookup"><span data-stu-id="8a32e-126">For example, on macOS, the `executablePath` for Microsoft Edge Canary should be set to `/Applications/Microsoft\ Edge\ Canary.app/`.</span></span>  <span data-ttu-id="8a32e-127">若要查找 ，请导航到 并复制该页面上的可执行路径，或者使用以下命令安装边缘 `executablePath` `edge://version` 路径包。 \*\*\*\* [][npmEdgePaths]</span><span class="sxs-lookup"><span data-stu-id="8a32e-127">To find the `executablePath`, navigate to `edge://version` and copy the **Executable path** on that page or install the [edge-paths][npmEdgePaths] package with the following command.</span></span>  

```shell
npm i edge-paths
```  

<span data-ttu-id="8a32e-128">以下代码段使用[边缘][npmEdgePaths]路径包以编程方式查找在操作系统上安装 Microsoft Edge \ (Chromium\) 的路径。</span><span class="sxs-lookup"><span data-stu-id="8a32e-128">The following code snippet uses the [edge-paths][npmEdgePaths] package to programmatically find the path to your installation of Microsoft Edge \(Chromium\) on your OS.</span></span>  

```javascript
const edgePaths = require("edge-paths");

const EDGE_PATH = edgePaths.getEdgePath();
```  

<span data-ttu-id="8a32e-129">最后，在 `executablePath: EDGE_PATH` 中设置 `example.js` 。</span><span class="sxs-lookup"><span data-stu-id="8a32e-129">Finally, set `executablePath: EDGE_PATH` in `example.js`.</span></span>  <span data-ttu-id="8a32e-130">保存更改。</span><span class="sxs-lookup"><span data-stu-id="8a32e-130">Save your changes.</span></span>  

> [!NOTE]
> <span data-ttu-id="8a32e-131">Microsoft Edge \ (EdgeHTML\) 不能与 Playwright 一起工作。</span><span class="sxs-lookup"><span data-stu-id="8a32e-131">Microsoft Edge \(EdgeHTML\) does not work with Playwright.</span></span>  <span data-ttu-id="8a32e-132">必须安装[\Microsoft Edge \ (Chromium\) ][MicrosoftEdgeDownload]以继续按照此示例操作。</span><span class="sxs-lookup"><span data-stu-id="8a32e-132">You must install [Microsoft Edge \(Chromium\)][MicrosoftEdgeDownload] to continue following this example.</span></span>  

<span data-ttu-id="8a32e-133">现在 `example.js` 从命令行运行。</span><span class="sxs-lookup"><span data-stu-id="8a32e-133">Now run `example.js` from the command line.</span></span>  

```shell
node example.js
```  

<span data-ttu-id="8a32e-134">Playwright 启动Microsoft Edge，导航到 `https://www.microsoft.com/edge` ，并保存页面的屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="8a32e-134">Playwright launches Microsoft Edge, navigates to `https://www.microsoft.com/edge`, and saves a screenshot of the page.</span></span>  <span data-ttu-id="8a32e-135">可以使用 [page.setViewportSize ][PlaywrightAPIPageSetViewport]自定义页面 () 。</span><span class="sxs-lookup"><span data-stu-id="8a32e-135">You may customize the page size with [page.setViewportSize()][PlaywrightAPIPageSetViewport].</span></span>  

:::image type="complex" source="../media/playwright-example.png" alt-text="由example.png生成的example.js" lightbox="../media/playwright-example.png":::
    <span data-ttu-id="8a32e-137">`example.png`生成的文件</span><span class="sxs-lookup"><span data-stu-id="8a32e-137">The `example.png` file produced by</span></span> `example.js`  
:::image-end:::  

`example.js` <span data-ttu-id="8a32e-138">只是由 Playwright 启用的自动化和测试方案的一个简单演示。</span><span class="sxs-lookup"><span data-stu-id="8a32e-138">is just a simple demonstration of the automation and testing scenarios enabled by Playwright.</span></span>  <span data-ttu-id="8a32e-139">若要在多个 Web 浏览器中拍摄屏幕截图，请更改以下代码。</span><span class="sxs-lookup"><span data-stu-id="8a32e-139">To take screenshots in multiple web browsers, change the following code.</span></span>  

*   <span data-ttu-id="8a32e-140">Chromium</span><span class="sxs-lookup"><span data-stu-id="8a32e-140">Chromium</span></span>  `await chromium.launch()`  
*   <span data-ttu-id="8a32e-141">Firefox</span><span class="sxs-lookup"><span data-stu-id="8a32e-141">Firefox</span></span>  `await firefox.launch()`  
*   <span data-ttu-id="8a32e-142">WebKit</span><span class="sxs-lookup"><span data-stu-id="8a32e-142">WebKit</span></span>  `await webkit.launch()`  

<span data-ttu-id="8a32e-143">有关 Playwright 的信息，请导航到 [Playwright 网站][|::ref6::|Main]。</span><span class="sxs-lookup"><span data-stu-id="8a32e-143">For more information about Playwright, navigate to the [Playwright website][|::ref6::|Main].</span></span>  <span data-ttu-id="8a32e-144">请查看 GitHub 上的[Playwright][PlaywrightRepo]存储库。</span><span class="sxs-lookup"><span data-stu-id="8a32e-144">Check out the  [Playwright repo][PlaywrightRepo] on GitHub.</span></span>  <span data-ttu-id="8a32e-145">若要与 Playwright 共享有关自动执行和测试网站或应用的反馈， [请提交问题][PlaywrightRepoNewIssue]。</span><span class="sxs-lookup"><span data-stu-id="8a32e-145">To share your feedback on automating and testing your website or app with Playwright, [file an issue][PlaywrightRepoNewIssue].</span></span>  

## <span data-ttu-id="8a32e-146">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="8a32e-146">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../devtools-guide-chromium/includes/contact-devtools-team-note.md)]  

<!-- links -->  

[WebdriverChromiumMain]: ../webdriver-chromium/index.md "WebDriver (Chromium) |Microsoft Docs"  
[PuppeteerMain]: ../puppeteer/index.md "百年|Microsoft Docs"  

[MicrosoftBlogsWindowsExperience20181206]: https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration "Microsoft Edge：通过更多开放源代码协作功能改善|Microsoft 体验博客"  

[MicrosoftEdgeDownload]: https://microsoft.com/edge "下载Microsoft Edge"  

[ChromiumHome]: https://www.chromium.org/Home "Chromium |项目Chromium"  

[FirefoxMain]: https://www.mozilla.org/firefox "Mozilla Firefox"  

[NodejsMain]: https://nodejs.org "Node.js"  

[npmEdgePaths]: https://www.npmjs.com/package/edge-paths "边缘路径|npm"  

[PlaywrightMain]: https://playwright.dev "Playwright"  
[PlaywrightAPIReference]: https://playwright.dev#?path=docs/api.md "Playwright API 参考"  
[PlaywrightAPIPageSetViewport]: https://playwright.dev#?path=docs%2Fapi.md&q=pagesetviewportsizeviewportsize "page.setViewportSize (viewportSize) |Playwright API 参考"    
[PlaywrightSystemRequirements]: https://playwright.dev#?path=docs/intro.md&q=system-requirements "Playwright 系统要求"  

[PlaywrightRepo]: https://github.com/microsoft/playwright "Playwright |GitHub"  
[PlaywrightRepoNewIssue]: https://github.com/microsoft/playwright/issues/new/choose "Playwright 存储库管理中的|GitHub"  

[WebKitMain]: https://webkit.org "WebKit"  

[WikiHeadlessBrowser]: https://en.wikipedia.org/wiki/Headless_browser "无头浏览器|Wikipedia"  
