---
description: Microsoft Edge for Web Apps 中的最新实验功能
title: 实验功能|渐进式 Web 应用
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/09/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， 实验， 渐进式 Web 应用， Web 应用， PWA， PWA
ms.openlocfilehash: 20bc4c90c1fe30be360b44294966415823f9b3a6
ms.sourcegitcommit: 4c6b74b9cdfca73c410d9eba9b42d229b695ee4a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "11482441"
---
# <a name="experimental-features-in-progressive-web-apps-pwas"></a><span data-ttu-id="ee5d0-104">渐进式 Web 应用和 PBA (实验) </span><span class="sxs-lookup"><span data-stu-id="ee5d0-104">Experimental features in Progressive Web Apps (PWAs)</span></span>  

<span data-ttu-id="ee5d0-105">Microsoft Edge 提供对仍在开发中的实验性功能的访问权限。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-105">Microsoft Edge provides access to experimental features that are still in development.</span></span>  <span data-ttu-id="ee5d0-106">若要确定每个功能是否就绪以及何时发布每个功能，请进行测试 [并提供反馈](#providing-feedback-on-experimental-features)。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-106">To determine if each feature is ready and when to release each, test and [provide feedback](#providing-feedback-on-experimental-features).</span></span>  

<span data-ttu-id="ee5d0-107">实验功能在 Microsoft Edge 的所有渠道中均可用，但最新的实验功能仅在 Microsoft Edge Canary 渠道中可用。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-107">Experimental features are available in all channels of Microsoft Edge, but the latest experimental features are only available in the Microsoft Edge Canary channel.</span></span>  

## <a name="turn-on-experimental-features"></a><span data-ttu-id="ee5d0-108">打开试验功能</span><span class="sxs-lookup"><span data-stu-id="ee5d0-108">Turn on experimental features</span></span>  

<span data-ttu-id="ee5d0-109">若要在 Microsoft Edge 中打开\（或关闭\）试验功能，请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-109">To turn on \(or off\) experimental features in Microsoft Edge, complete the following steps.</span></span>  
  
1.  <span data-ttu-id="ee5d0-110">打开 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-110">Open Microsoft Edge.</span></span>   
    
    > [!NOTE]
    > <span data-ttu-id="ee5d0-111">确保使用本文中列出的实验的 Microsoft Edge 版本。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-111">Ensure you use a Microsoft Edge version that has the Experiment listed in this article.</span></span>  <span data-ttu-id="ee5d0-112">导航到 [实验功能](#features-that-are-available-to-test)。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-112">Navigate to [Experimental features](#features-that-are-available-to-test).</span></span>  
    
1.  <span data-ttu-id="ee5d0-113">导航到 `edge://flags` 。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-113">Navigate to `edge://flags`.</span></span>  
1.  <span data-ttu-id="ee5d0-114">导航到相关实验。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-114">Navigate to the relevant experiment.</span></span>  
1.  <span data-ttu-id="ee5d0-115">选择实验说明旁边的下拉菜单并选择 `Enabled` 。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-115">Choose the dropdown menu next to the experiment description and choose `Enabled`.</span></span>  
    
    :::image type="complex" source="../media/turn-on-experimental-flag.png" alt-text="选择启用以打开实验" lightbox="../media/turn-on-experimental-flag.png":::
       <span data-ttu-id="ee5d0-117">选择 **启用** 以打开实验</span><span class="sxs-lookup"><span data-stu-id="ee5d0-117">Choose **Enabled** to turn on an experiment</span></span>  
    :::image-end:::  
    
    > [!NOTE]
    > <span data-ttu-id="ee5d0-118">每个实验通常都有一个下拉菜单来选择以下值。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-118">Each experiment usually has a dropdown menu to choose the following values.</span></span>  <span data-ttu-id="ee5d0-119">如果实验功能在实验上没有条目，则提供\*\*\*\* 说明以使用命令行使用该功能启动 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-119">If an experimental feature doesn't have an entry on **Experiments**, instructions are provided to start Microsoft Edge with that feature using the command-line.</span></span>
    > 
    > *   `Default`  
    > *   `Disabled`  
    > *   `Enabled`  
    
1.  <span data-ttu-id="ee5d0-120">重启 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-120">Restart Microsoft Edge.</span></span>  
    
### <a name="origin-trials"></a><span data-ttu-id="ee5d0-121">原始试验</span><span class="sxs-lookup"><span data-stu-id="ee5d0-121">Origin Trials</span></span>  

<span data-ttu-id="ee5d0-122">Microsoft Edge 有时使用源试用版来测试特定域或网站的功能。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-122">Microsoft Edge sometimes uses origin trials to test features for specific domains or websites.</span></span>  <span data-ttu-id="ee5d0-123">你可能想要对网站使用源试用版来应用特定功能。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-123">You may want to use an origin trial for your website to apply a specific feature.</span></span>  <span data-ttu-id="ee5d0-124">如果你是网站所有者，你可以注册源试用版。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-124">If you're a website owner, you may enroll in an origin trial.</span></span>  <span data-ttu-id="ee5d0-125">源试用版向访问你的网站的 Microsoft Edge 用户提供一定比例的功能。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-125">An origin trial provides features to a percentage of Microsoft Edge users who visit your website.</span></span>

<span data-ttu-id="ee5d0-126">有关源试用版详细信息，请导航到 [Microsoft Edge Origin Trials 开发人员控制台][MicrosoftDeveloperMicrosoftEdgeOriginTrials]。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-126">For more information about Origin Trials, navigate to [Microsoft Edge Origin Trials Developer Console][MicrosoftDeveloperMicrosoftEdgeOriginTrials].</span></span>  
    
> [!NOTE]
> <span data-ttu-id="ee5d0-127">实验性功能会不断更新，并且可能会导致性能问题。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-127">Experimental features are constantly updated and may cause performance issues.</span></span>  <span data-ttu-id="ee5d0-128">若要关闭实验功能，请导航到打开 [实验](#turn-on-experimental-features)功能，导航到实验，然后选择 `Disabled` 。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-128">To turn off an experimental feature, navigate to [Turn on experimental features](#turn-on-experimental-features), navigate to the experiment, and then choose `Disabled`.</span></span>  

## <a name="features-that-are-available-to-test"></a><span data-ttu-id="ee5d0-129">可供测试的功能</span><span class="sxs-lookup"><span data-stu-id="ee5d0-129">Features that are available to test</span></span>  

<span data-ttu-id="ee5d0-130">以下列表介绍了可在 Microsoft Edge 上测试和验证的新实验性 Web 应用功能。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-130">The following list describes the new experimental web app features that are available to test and validate on Microsoft Edge.</span></span>  

| <span data-ttu-id="ee5d0-131">功能</span><span class="sxs-lookup"><span data-stu-id="ee5d0-131">Feature</span></span> | <span data-ttu-id="ee5d0-132">Microsoft Edge 版本</span><span class="sxs-lookup"><span data-stu-id="ee5d0-132">Microsoft Edge version</span></span> | <span data-ttu-id="ee5d0-133">平台</span><span class="sxs-lookup"><span data-stu-id="ee5d0-133">Platform</span></span> |  
|:--- |:--- |:--- |  
| [<span data-ttu-id="ee5d0-134">URI 协议处理</span><span class="sxs-lookup"><span data-stu-id="ee5d0-134">URI Protocol Handling</span></span>](#uri-protocol-handling) | <span data-ttu-id="ee5d0-135">91 或更高版本</span><span class="sxs-lookup"><span data-stu-id="ee5d0-135">91 or later</span></span> | <span data-ttu-id="ee5d0-136">Windows</span><span class="sxs-lookup"><span data-stu-id="ee5d0-136">Windows</span></span> |    
| [<span data-ttu-id="ee5d0-137">URL 链接处理</span><span class="sxs-lookup"><span data-stu-id="ee5d0-137">URL Link Handling</span></span>](#url-link-handling) | <span data-ttu-id="ee5d0-138">91 或更高版本</span><span class="sxs-lookup"><span data-stu-id="ee5d0-138">91 or later</span></span> | <span data-ttu-id="ee5d0-139">Windows</span><span class="sxs-lookup"><span data-stu-id="ee5d0-139">Windows</span></span>|
| [<span data-ttu-id="ee5d0-140">适用于桌面应用的窗口控件覆盖层</span><span class="sxs-lookup"><span data-stu-id="ee5d0-140">Window Controls Overlay for Desktop Apps</span></span>](#window-controls-overlay-for-installed-desktop-web-apps) | <span data-ttu-id="ee5d0-141">91 或更高版本</span><span class="sxs-lookup"><span data-stu-id="ee5d0-141">91 or later</span></span> | <span data-ttu-id="ee5d0-142">Windows 10</span><span class="sxs-lookup"><span data-stu-id="ee5d0-142">Windows 10</span></span>|   
| [<span data-ttu-id="ee5d0-143">在操作系统登录时运行</span><span class="sxs-lookup"><span data-stu-id="ee5d0-143">Run on OS Login</span></span>](#run-on-os-login) | <span data-ttu-id="ee5d0-144">88 或更高版本</span><span class="sxs-lookup"><span data-stu-id="ee5d0-144">88 or later</span></span> | <span data-ttu-id="ee5d0-145">全部</span><span class="sxs-lookup"><span data-stu-id="ee5d0-145">All</span></span> |  
| [<span data-ttu-id="ee5d0-146">快捷方式</span><span class="sxs-lookup"><span data-stu-id="ee5d0-146">Shortcuts</span></span>](#shortcuts) | <span data-ttu-id="ee5d0-147">87 或更高版本</span><span class="sxs-lookup"><span data-stu-id="ee5d0-147">87 or later</span></span> | <span data-ttu-id="ee5d0-148">全部</span><span class="sxs-lookup"><span data-stu-id="ee5d0-148">All</span></span> |  
| [<span data-ttu-id="ee5d0-149">文件处理</span><span class="sxs-lookup"><span data-stu-id="ee5d0-149">File Handling</span></span>](#file-handling) | <span data-ttu-id="ee5d0-150">83 或更高版本</span><span class="sxs-lookup"><span data-stu-id="ee5d0-150">83 or later</span></span> | <span data-ttu-id="ee5d0-151">所有桌面</span><span class="sxs-lookup"><span data-stu-id="ee5d0-151">All Desktop</span></span> |  


## <a name="uri-protocol-handling"></a><span data-ttu-id="ee5d0-152">URI 协议处理</span><span class="sxs-lookup"><span data-stu-id="ee5d0-152">URI Protocol Handling</span></span>  

<span data-ttu-id="ee5d0-153">统一资源标识符 \ (URI\) 可用于定义使用 HTTP 或 FTP 协议的网页和 Web 内容的链接。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-153">A uniform resource identifier \(URI\) may be used to define more than just links to webpages and web content using the HTTP or FTP protocol.</span></span>  <span data-ttu-id="ee5d0-154">URI 可用于描述指向您编成架构中任何内容的链接。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-154">URIs may be used to describe links to anything that you codify into a schema.</span></span>  <span data-ttu-id="ee5d0-155">例如，协议用于描述电子邮件链接，操作系统 `mailto://` \ (OS\) 或浏览器决定哪个网页或应用应处理该协议。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-155">For example, the `mailto://` protocol is used to describe an email link and the operating system \(OS\) or browser decides which webpage or app should handle that protocol.</span></span>  

<span data-ttu-id="ee5d0-156">有关基于浏览器的现有支持，请导航到基于 [Web 的协议处理程序][MdnDocsWebApiNavigatorRegisterprotocolhandlerWebBasedProtocolHandlers]。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-156">For more information about existing browser-based support, navigate to [Web-based protocol handlers][MdnDocsWebApiNavigatorRegisterprotocolhandlerWebBasedProtocolHandlers].</span></span>  

<span data-ttu-id="ee5d0-157">此功能允许您完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-157">This feature allows you to complete the following actions.</span></span>  

*   <span data-ttu-id="ee5d0-158">使用 Web 应用程序的清单向主机操作系统注册 PWA</span><span class="sxs-lookup"><span data-stu-id="ee5d0-158">Register your PWA with the host OS using the manifest of your web app</span></span>
*   <span data-ttu-id="ee5d0-159">声明 PWA 处理特定 URI 协议</span><span class="sxs-lookup"><span data-stu-id="ee5d0-159">Declare that a PWA handles a specific URI protocol</span></span>  
     
<span data-ttu-id="ee5d0-160">将 PWA 注册为协议处理程序后，当用户选择具有特定方案（如浏览器或本机应用）的超链接时，已注册的 PWA 由操作系统激活并接收 `mailto://` `web+music://` URI。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-160">After you register a PWA as a protocol handler, when a user chooses a hyperlink with a specific scheme such as `mailto://` or `web+music://` from a browser or a native app, the registered PWA is activated by the OS and receives the URI.</span></span>  

<span data-ttu-id="ee5d0-161">此功能要求你更新 Web 应用清单以在需要指定两个字段的 `protocol_handlers` 数组中包括数组：</span><span class="sxs-lookup"><span data-stu-id="ee5d0-161">This feature requires you to update the web app manifest to include a `protocol_handlers` array, in the array you need to specify two fields:</span></span>  

*   `protocol`<span data-ttu-id="ee5d0-162">：用于处理请求的协议，例如 或 `mailto` `web+jngl` 。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-162">:  The protocol to handle the request, for example `mailto` or `web+jngl`.</span></span>  
*   `url`<span data-ttu-id="ee5d0-163">：处理协议的应用作用域中的 HTTPS URI。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-163">: The HTTPS URI in the app scope that handles the protocol.</span></span>  <span data-ttu-id="ee5d0-164">将来，计划替换以协议处理程序方案开始的 `%s` URI。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-164">In the future, the URI starting with the protocol handlers scheme is planned to replace the `%s` token.</span></span>  
    
<span data-ttu-id="ee5d0-165">更新清单以支持要注册的协议。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-165">Update your manifest to support the protocol that you want to register.</span></span>  <span data-ttu-id="ee5d0-166">启用此功能后，Microsoft Edge 将完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-166">After you turn on this feature, Microsoft Edge completes the following actions.</span></span>  

1.  <span data-ttu-id="ee5d0-167">检测清单中的更改</span><span class="sxs-lookup"><span data-stu-id="ee5d0-167">Detects changes in the manifest</span></span>  
1.  <span data-ttu-id="ee5d0-168">为协议注册应用</span><span class="sxs-lookup"><span data-stu-id="ee5d0-168">Registers the app for the protocol</span></span>  
    
<span data-ttu-id="ee5d0-169">如果多个应用注册协议，则向用户显示提示。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-169">If more than one app registers a protocol, the user is presented with a prompt.</span></span>  <span data-ttu-id="ee5d0-170">用户从操作系统或浏览器呈现的列表中选择相应的应用。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-170">The user chooses the appropriate app from the list presented by the OS or browser.</span></span>  

<span data-ttu-id="ee5d0-171">若要在 Windows 上的 Microsoft Edge 中[](#turn-on-experimental-features)预览协议处理，请导航到打开实验性功能，然后打开**桌面 PWA 协议处理**。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-171">To preview protocol handling in Microsoft Edge on Windows, navigate to [Turn on experimental features](#turn-on-experimental-features) and turn on **Desktop PWA Protocol handling**.</span></span>  

<span data-ttu-id="ee5d0-172">有关为协议处理程序运行的源试用版详细信息，请导航到注册 [Web 应用协议处理程序注册][MicrosoftDeveloperMicrosoftEdgeOriginTrialsWebAppProtocolHandlerRegistrationRegistration]。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-172">For more information about origin trial is running for protocol handlers, navigate to [Register for Web App Protocol Handler Registration][MicrosoftDeveloperMicrosoftEdgeOriginTrialsWebAppProtocolHandlerRegistrationRegistration].</span></span>  

### <a name="example-manifest"></a><span data-ttu-id="ee5d0-173">示例清单</span><span class="sxs-lookup"><span data-stu-id="ee5d0-173">Example Manifest</span></span>

<span data-ttu-id="ee5d0-174">在此例中，Web 应用清单声明应用应注册为处理协议 和 `web+jngl` `web+jnglstore` 。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-174">In this example, a web app manifest declares that the app should be registered to handle the protocols `web+jngl` and `web+jnglstore`.</span></span>

```json
{
  "name": "Jungle",
  "description": "A plant encyclopedia",
  "protocol_handlers": [
    {
      "protocol": "web+jngl",
      "url": "/lookup?type=%s"
    },
    {
      "protocol": "web+jnglstore",
      "url": "/shop?for=%s"
    }
  ],
  "icons": [
    {
      "src": "images/icons-192.png",
      "type": "image/png",
      "sizes": "192x192"
    },
  ],
  "background_color": "#007f87",

  "display": "standalone",
  "start_url": "/",
}
```  
 
## <a name="url-link-handling"></a><span data-ttu-id="ee5d0-175">URL 链接处理</span><span class="sxs-lookup"><span data-stu-id="ee5d0-175">URL Link Handling</span></span>  

<span data-ttu-id="ee5d0-176">统一资源定位器 \ (URL\) 是一种 URI。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-176">A uniform resource locator \(URL\) is a type of URI.</span></span>  <span data-ttu-id="ee5d0-177">当渐进 Web 应用 \ (PWA\) 注册为 https URI 的处理程序时，创建更具吸引力的体验。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-177">Create a more engaging experience when Progressive Web Apps \(PWAs\) register as handlers for https URIs.</span></span>  <span data-ttu-id="ee5d0-178">PBA 可能会请求在激活关联的 URI 时启动。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-178">PWAs may request to launch when associated URIs are activated.</span></span>  <span data-ttu-id="ee5d0-179">例如，如果用户从电子邮件中选择指向新闻文章的链接。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-179">For example, if a user chooses a link to a news story from an email message.</span></span>  <span data-ttu-id="ee5d0-180">用于显示新闻文章的关联 PWA 将自动启动以处理链接的激活。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-180">An associated PWA to display news stories is automatically launched to handle the activation of the link.</span></span>  

<span data-ttu-id="ee5d0-181">此功能允许您使用 Web 应用程序清单向浏览器注册 PWA，并声明浏览器处理特定链接。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-181">This feature allows you to register a PWA with the browser using the web app manifest and declare that the browser handles specific links.</span></span>  <span data-ttu-id="ee5d0-182">若要在浏览器中注册 PWA，请向清单 `url_handlers` 文件添加可选成员。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-182">To register a PWA with the browser, add the optional `url_handlers` member to the manifest file.</span></span>  <span data-ttu-id="ee5d0-183">`url_handlers`成员是 `object[]` 一个 ，用于对应用希望处理的 URI 的来源进行分组。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-183">The `url_handlers` member is an `object[]` that groups the origins of URIs that the app wishes to handle.</span></span>  

<span data-ttu-id="ee5d0-184">浏览器使用位于源上的 `web-app-origin-association` JSON 文件验证链接处理。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-184">Link handling is validated by the browser using a `web-app-origin-association` JSON file that is located on the origin.</span></span>  <span data-ttu-id="ee5d0-185">源文件进一步微调源的包含路径或排除路径。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-185">The origin file further fine-tunes the included or excluded paths at the origin.</span></span>  <span data-ttu-id="ee5d0-186">有关测试 URL 处理程序的详细说明，请导航到[作为 URL 处理程序的 PWA。][GithubWicgPwaUrlHandlerBlobMainExplainerMd]</span><span class="sxs-lookup"><span data-stu-id="ee5d0-186">For detailed instructions about testing the URL handler, navigate to [PWAs as URL Handlers][GithubWicgPwaUrlHandlerBlobMainExplainerMd].</span></span>  

<span data-ttu-id="ee5d0-187">若要在 Windows 上的 Microsoft Edge 中预览 URL 链接处理，请导航到"[打开](#turn-on-experimental-features)实验性功能"，然后打开"**桌面 PWA URL 处理"。**</span><span class="sxs-lookup"><span data-stu-id="ee5d0-187">To preview URL link handling in Microsoft Edge on Windows, navigate to [Turn on experimental features](#turn-on-experimental-features) and turn on **Desktop PWA URL  Handling**.</span></span>  

### <a name="example-of-the-url_handlers-in-the-manifest"></a><span data-ttu-id="ee5d0-188">清单url_handlers示例</span><span class="sxs-lookup"><span data-stu-id="ee5d0-188">Example of the url_handlers in the manifest</span></span>  

<span data-ttu-id="ee5d0-189">以下代码段是包含 成员的示例 Web 应用 `url_handlers` 清单。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-189">The following code snippet is an example web app manifest with the `url_handlers` member.</span></span>  

```json 
{
    "name": "Contoso Business App",
    "display": "standalone",
    "icons": [
        {
            "src": "images/icons-144.png",
            "type": "image/png",
            "sizes": "144x144"
        }
    ],
    "capture_links": "existing_client_event",
    "url_handlers" : [
        {
            "origin": "https://contoso.com"
        },
        {
            "origin": "https://conto.so"
        },
        {
            "origin": "https://*.contoso.com"
        }
    ]
}
```  

<span data-ttu-id="ee5d0-190">如果 URI 与 中的一个源字符串匹配，并且浏览器验证源是否同意允许此应用程序处理此类 URI，PWA 将匹配用于 URL 处理的 `url_handlers` URI。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-190">A PWA matches a URI for URL handling if the URI matches one of the origin strings in `url_handlers` and the browser validates that the origin agrees to allow this app handle such a URI.</span></span>  

<span data-ttu-id="ee5d0-191">成员 `url_handlers` 包含一个包含请求 PWA 的范围和其他不相关的源的源。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-191">The `url_handlers` member contains an origin that encompasses the scope and other unrelated origins of the requesting PWA.</span></span>  <span data-ttu-id="ee5d0-192">不将 URI 限制为与请求的 PWA 相同的范围或域，允许您对相同内容使用不同的域名，但使用相同的 PWA 处理它们。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-192">Not restricting URIs to the same scope or domain as the requesting PWA allows you to use different domain names for the same content but handle them with the same PWA.</span></span>  

#### <a name="wildcard-matching"></a><span data-ttu-id="ee5d0-193">通配符匹配</span><span class="sxs-lookup"><span data-stu-id="ee5d0-193">Wildcard matching</span></span>  

<span data-ttu-id="ee5d0-194">使用通配符 \ (`*` \) 匹配一个或多个字符。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-194">Use the wildcard character \(`*`\) to match one or more characters.</span></span>  

<span data-ttu-id="ee5d0-195">通配符前缀用于成员的来源字符串中 `url_handlers` ，以匹配不同的子域。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-195">A wildcard prefix is used in origin strings of the `url_handlers` member to match for different subdomains.</span></span>  <span data-ttu-id="ee5d0-196">前缀必须针对 `*.` 此用法。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-196">The prefix must be `*.` for this usage.</span></span>  <span data-ttu-id="ee5d0-197">使用 `https` 通配符前缀时将假定此方案。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-197">The `https` scheme is assumed when you use a wildcard prefix.</span></span>  

<span data-ttu-id="ee5d0-198">例如， `url_handlers` 成员值设置为 `*.contoso.com` matches 和 `tenant.contoso.com` `www.tenant.contoso.com` ，但不匹配 `contoso.com` 。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-198">For example, the `url_handlers` member value is set to `*.contoso.com` matches `tenant.contoso.com` and `www.tenant.contoso.com`, but doesn't match `contoso.com`.</span></span>  

## <a name="window-controls-overlay-for-installed-desktop-web-apps"></a><span data-ttu-id="ee5d0-199">窗口控件 已安装桌面 Web 应用的覆盖层</span><span class="sxs-lookup"><span data-stu-id="ee5d0-199">Window Controls Overlay for installed desktop web apps</span></span>  

<span data-ttu-id="ee5d0-200">若要为桌面安装的 Web 应用创建沉浸式标题栏（如本机应用），"窗口控件覆盖"功能将完成以下操作。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="ee5d0-200">To create an immersive title bar like a native app for your desktop installed web app, the **Window Controls Overlay** feature completes the following actions.</span></span>  
    
1.  <span data-ttu-id="ee5d0-201">删除系统保留的标题栏。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-201">Removes the system reserved title bar.</span></span>  <span data-ttu-id="ee5d0-202">它通常跨越客户端框架的宽度。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-202">It usually spans the width of the client frame.</span></span>  
1.  <span data-ttu-id="ee5d0-203">将其替换为覆盖层。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-203">Replaces it with an overlay.</span></span>  <span data-ttu-id="ee5d0-204">它仅包含用户控制窗口本身所需的关键系统所需窗口控件。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-204">It contains just the critical system required window controls necessary for a user to control the window itself.</span></span>  
    
<span data-ttu-id="ee5d0-205">提供覆盖后，可使用整个 Web 客户端区域。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-205">After it provides an overlay, the entire web client area is available for you to use.</span></span>  <span data-ttu-id="ee5d0-206">此功能包括清单更新。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-206">This feature includes a manifest update.</span></span>  <span data-ttu-id="ee5d0-207">它提供用于确定覆盖的大小和位置的方法，以帮助你安排内容。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-207">It provides ways for you to determine the size and position of the overlay to help you arrange content.</span></span>  

<span data-ttu-id="ee5d0-208">若要预览适用于 Windows 10 的 Microsoft Edge 中的窗口[](#turn-on-experimental-features)控件覆盖，请导航到"打开实验性功能"并导航到"**桌面 PWA 窗口控件覆盖"。**</span><span class="sxs-lookup"><span data-stu-id="ee5d0-208">To preview the Window Controls Overlays in Microsoft Edge for Windows 10, navigate to [Turn on experimental features](#turn-on-experimental-features) and navigate to **Desktop PWA Window Controls Overlay**.</span></span>   

### <a name="examples-of-title-bar-area-customization"></a><span data-ttu-id="ee5d0-209">标题栏区域自定义示例</span><span class="sxs-lookup"><span data-stu-id="ee5d0-209">Examples of title bar area customization</span></span>  

<span data-ttu-id="ee5d0-210">此功能基于本机应用中自定义标题栏的功能。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-210">This feature is based on the ability in native apps to customize the title bar.</span></span>  <span data-ttu-id="ee5d0-211">你可以自定义重要应用操作或通知的标题栏。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-211">You may customize a title bar for important app actions or notifications.</span></span>  <span data-ttu-id="ee5d0-212">查看 Microsoft Visual Studio Code 和 Microsoft Teams 的以下示例。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-212">Review the following examples for Microsoft Visual Studio Code and Microsoft Teams.</span></span>  

#### <a name="visual-studio-code"></a><span data-ttu-id="ee5d0-213">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="ee5d0-213">Visual Studio Code</span></span>  

<span data-ttu-id="ee5d0-214">Microsoft Visual Studio Code 是一款基于位于多个桌面平台上的"小程序"构建的热门编辑器。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-214">Microsoft Visual Studio Code is a popular editor built on Electron that ships on multiple desktop platforms.</span></span>  

<span data-ttu-id="ee5d0-215">以下示例显示Visual Studio代码如何使用标题栏来最大化可用屏幕空间以在标题栏中包括当前文件名和顶级菜单结构。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-215">The following example displays how Visual Studio Code uses the title bar to maximize available screen real estate to include the current file name and top-level menu structure in the title bar.</span></span>  

:::image type="complex" source="../media/visual-studio-code-title-customization.png" alt-text="代码标题栏中Visual Studio示例" lightbox="../media/visual-studio-code-title-customization.png":::
   <span data-ttu-id="ee5d0-217">代码标题栏中Visual Studio示例</span><span class="sxs-lookup"><span data-stu-id="ee5d0-217">An example of the title bar in Visual Studio Code</span></span>  
:::image-end:::  

#### <a name="microsoft-teams"></a><span data-ttu-id="ee5d0-218">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ee5d0-218">Microsoft Teams</span></span>  

<span data-ttu-id="ee5d0-219">Workplace collaboration and communication tool Microsoft Teams is also built with Teams and available on multiple desktop platforms.</span><span class="sxs-lookup"><span data-stu-id="ee5d0-219">Workplace collaboration and communication tool Microsoft Teams is also built with Electron and available on multiple desktop platforms.</span></span>  <span data-ttu-id="ee5d0-220">在下面的示例中，Microsoft Teams 显示 `back` 和 `forward` 导航按钮、搜索框和用户配置文件控件。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-220">In the following example, Microsoft Teams displays `back` and `forward` navigation buttons, a search box, and user profile controls.</span></span>  

:::image type="complex" source="../media/teams-title-customization.png" alt-text="Microsoft Teams 中标题栏的示例" lightbox="../media/teams-title-customization.png":::
   <span data-ttu-id="ee5d0-222">Microsoft Teams 中标题栏的示例</span><span class="sxs-lookup"><span data-stu-id="ee5d0-222">An example of the title bar in Microsoft Teams</span></span>  
:::image-end:::  

### <a name="overlay-window-controls-on-a-frameless-window"></a><span data-ttu-id="ee5d0-223">无框架窗口上的覆盖窗口控件</span><span class="sxs-lookup"><span data-stu-id="ee5d0-223">Overlay Window Controls on a Frameless Window</span></span>  

<span data-ttu-id="ee5d0-224">为了最大化 Web 内容的可地址区域，浏览器会创建无框架窗口。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-224">To maximize the addressable area for web content, the browser creates a frameless window.</span></span>  <span data-ttu-id="ee5d0-225">无框架窗口删除所有浏览器 UI，但作为覆盖提供的窗口控件除外。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-225">A frameless window removes all browser UI, except for the window controls provided as an overlay.</span></span>  <span data-ttu-id="ee5d0-226">窗口控件覆盖允许用户仍最小化、最大化、还原和关闭应用。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-226">The window controls overlay allows users to still minimize, maximize, restore, and close the app.</span></span>  <span data-ttu-id="ee5d0-227">它还提供对使用 Web 应用菜单的相关浏览器控件的访问。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-227">It also provides access to relevant browser controls using the web app menu.</span></span>  <span data-ttu-id="ee5d0-228">对于基于 Chromium 的浏览器，覆盖层包括以下控件。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-228">For Chromium-based browsers, the overlay includes the following controls.</span></span>  

*   <span data-ttu-id="ee5d0-229">每个窗口控件按钮的宽度和高度相同的可拖动区域</span><span class="sxs-lookup"><span data-stu-id="ee5d0-229">A draggable region the same width and height of each of the window control buttons</span></span>  
*   <span data-ttu-id="ee5d0-230">" **设置"和更多** \ (...\) 按钮</span><span class="sxs-lookup"><span data-stu-id="ee5d0-230">The **Settings and more** \(...\) button</span></span>  
*   <span data-ttu-id="ee5d0-231">窗口控件按钮最小化、最大化、还原和关闭</span><span class="sxs-lookup"><span data-stu-id="ee5d0-231">The window control buttons minimize, maximize, restore, and close</span></span>  
    
<span data-ttu-id="ee5d0-232">除了前面列出的控件之外，覆盖层中显示的 UI 将在以下方案中动态调整大小。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-232">Besides the previously listed controls, the UI displayed in the overlay is dynamically resized in the following scenarios.</span></span>  

*   <span data-ttu-id="ee5d0-233">启动已安装的 Web 应用后，网页的原点会在"设置"和更多\*\*\*\* \ (...\) 菜单的左侧显示几秒钟，然后消失。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-233">When an installed web app is launched, the origin of the webpage displays to the left of the **Settings and more** \(...\) menu for a few seconds and then disappears.</span></span>  
*   <span data-ttu-id="ee5d0-234">如果用户使用"设置"菜单和更多\*\*\*\* \ (...\) 菜单与扩展进行交互，则扩展的图标显示在三点菜单左侧的覆盖中。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-234">If a user interacts with an extension using the **Settings and more** \(...\) menu, the icon of the extension displays in the overlay to the left of the three-dot menu.</span></span>  <span data-ttu-id="ee5d0-235">退出任何扩展对话框后，图标将从覆盖层中删除。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-235">After you exit any extension dialog, the icon is removed from the overlay.</span></span>  
    
| <span data-ttu-id="ee5d0-236">语言方向</span><span class="sxs-lookup"><span data-stu-id="ee5d0-236">Language direction</span></span> | <span data-ttu-id="ee5d0-237">覆盖位置</span><span class="sxs-lookup"><span data-stu-id="ee5d0-237">Overlay location</span></span> | <span data-ttu-id="ee5d0-238">详细信息</span><span class="sxs-lookup"><span data-stu-id="ee5d0-238">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="ee5d0-239">从左到右 \ (LTR\) </span><span class="sxs-lookup"><span data-stu-id="ee5d0-239">Left-to-right \(LTR\)</span></span> | <span data-ttu-id="ee5d0-240">客户区域左上角</span><span class="sxs-lookup"><span data-stu-id="ee5d0-240">Upper left of the client area</span></span> | <span data-ttu-id="ee5d0-241">翻转控件</span><span class="sxs-lookup"><span data-stu-id="ee5d0-241">The controls are flipped</span></span> |  
| <span data-ttu-id="ee5d0-242">从右到左 \ (RTL\) </span><span class="sxs-lookup"><span data-stu-id="ee5d0-242">Right-to-left \(RTL\)</span></span> | <span data-ttu-id="ee5d0-243">工作区的右上角</span><span class="sxs-lookup"><span data-stu-id="ee5d0-243">Upper right corner of the client area</span></span> |  |  

> [!IMPORTANT]
> <span data-ttu-id="ee5d0-244">覆盖始终位于 Web 内容的 Z 索引顶部，并接受所有用户输入，而不会将输入流到 Web 内容。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-244">The overlay is always on top of the Z-index of the web content and accepts all user input without flowing it through to the web content.</span></span>  

### <a name="working-around-the-window-controls-overlay"></a><span data-ttu-id="ee5d0-245">处理窗口控件覆盖层</span><span class="sxs-lookup"><span data-stu-id="ee5d0-245">Working around the Window Controls Overlay</span></span>  

<span data-ttu-id="ee5d0-246">Web 内容必须知道控件覆盖的保留区域。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-246">Your web content must be aware of the reserved area for the controls overlay.</span></span>  <span data-ttu-id="ee5d0-247">确保保留区域不需要用户交互。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-247">Ensure the reserved area doesn't expect user interaction.</span></span>  <span data-ttu-id="ee5d0-248">在浏览器中查询控件覆盖的矩形边界和可见性。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-248">Query the browser for the bounding rectangle and visibility of the controls overlay.</span></span>  <span data-ttu-id="ee5d0-249">该信息通过 JavaScript API 和 CSS 环境变量提供给你。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-249">The information is provided to you through JavaScript APIs and CSS environment variables.</span></span>  

#### <a name="javascript-apis"></a><span data-ttu-id="ee5d0-250">JavaScript API</span><span class="sxs-lookup"><span data-stu-id="ee5d0-250">JavaScript APIs</span></span>  

<span data-ttu-id="ee5d0-251">属性 `windowControlsOverlay` 上的新 `window.navigator` 对象允许您查询控件覆盖的边框。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-251">A new `windowControlsOverlay` object on the `window.navigator` property allows you to query the bounding rectangle of the controls overlay.</span></span>  

<span data-ttu-id="ee5d0-252">对象 `windowControlsOverlay` 具有以下两个对象。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-252">The `windowControlsOverlay` object has the following two objects.</span></span>  

*   `getBoundingClientRect()` <span data-ttu-id="ee5d0-253"> 返回一个 `DOMRect` 对象。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-253">returns a `DOMRect` object.</span></span>  <span data-ttu-id="ee5d0-254">对象 `DOMRect` 表示窗口控件覆盖层下的区域。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-254">The `DOMRect` object represents the area under the window controls overlay.</span></span>  
*   `visible` <span data-ttu-id="ee5d0-255">是一个 boolean 值，指示呈现和显示控件覆盖。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-255">is a boolean that indicates that the controls overlay is rendered and displayed.</span></span>  
    
> [!IMPORTANT]
> <span data-ttu-id="ee5d0-256">出于隐私原因，Web 内容中的 `windowControlsOverlay` `iframe` 元素无法访问 。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-256">For privacy reasons, the `windowControlsOverlay` isn't accessible to `iframe` elements in the web content.</span></span>  

<span data-ttu-id="ee5d0-257">每当调整覆盖大小时，都会在对象上运行一个事件，以通知客户端 `geometrychange` `navigator.windowControlsOverlay` 重新计算内容布局。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-257">Whenever the overlay is resized, a `geometrychange` event runs on the `navigator.windowControlsOverlay` object to notify the client to recalculate the content layout.</span></span>  <span data-ttu-id="ee5d0-258">重新计算的内容布局基于覆盖层的新边界矩形。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-258">The recalculated content layout is based on the new bounding rectangle of the overlay.</span></span>  

#### <a name="css-environment-variables"></a><span data-ttu-id="ee5d0-259">CSS 环境变量</span><span class="sxs-lookup"><span data-stu-id="ee5d0-259">CSS Environment Variables</span></span>  

<span data-ttu-id="ee5d0-260">除了 JavaScript API 之外，您还可以使用 CSS 查询控件覆盖的边框。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-260">Besides the JavaScript API, you may use CSS to query the bounding rectangle of the controls overlay.</span></span>  <span data-ttu-id="ee5d0-261">使用以下四个新的 CSS 环境变量完成查询。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-261">Use the following four new CSS environment variables to accomplish to query.</span></span>  

*   `titlebar-area-x`  
*   `titlebar-area-y`  
*   `titlebar-area-width`  
*   `titlebar-area-height`  
    
### <a name="define-draggable-regions-in-web-content"></a><span data-ttu-id="ee5d0-262">在 Web 内容中定义可拖动区域</span><span class="sxs-lookup"><span data-stu-id="ee5d0-262">Define Draggable Regions in Web Content</span></span>  

<span data-ttu-id="ee5d0-263">用户希望抓取和拖动窗口的上半部分。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-263">Users expect to grab and drag the upper region of a window.</span></span>  <span data-ttu-id="ee5d0-264">若要满足预期要求，请声明 Web 内容的特定部分为可拖动。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-264">To accommodate the expectation, declare specific parts of the web content as draggable.</span></span>  
<span data-ttu-id="ee5d0-265">若要指定元素是可拖动的，请使用 WebKit 专有 `-webkit-app-region` CSS 属性。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-265">To specify an element is draggable, use the WebKit-proprietary `-webkit-app-region` CSS property.</span></span>  <span data-ttu-id="ee5d0-266">CSS 工作组将继续努力标准化 `app-region` 该属性。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-266">The CSS working group continues efforts to standardize the `app-region` property.</span></span>  

### <a name="custom-title-bar-example"></a><span data-ttu-id="ee5d0-267">自定义标题栏示例</span><span class="sxs-lookup"><span data-stu-id="ee5d0-267">Custom title bar example</span></span>  

<span data-ttu-id="ee5d0-268">以下示例显示新功能如何使用自定义标题栏创建 Web 应用。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-268">The following example displays how the new features create a web app with a custom title bar.</span></span>  

:::image type="complex" source="../media/teams-title-customization-example.png" alt-text="Microsoft Teams 中的自定义标题栏示例" lightbox="../media/teams-title-customization-example.png":::
   <span data-ttu-id="ee5d0-270">Microsoft Teams 中的自定义标题栏示例</span><span class="sxs-lookup"><span data-stu-id="ee5d0-270">Example of a custom title bar in Microsoft Teams</span></span>  
:::image-end:::  

#### <a name="manifestwebmanifest"></a><span data-ttu-id="ee5d0-271">manifest.webmanifest</span><span class="sxs-lookup"><span data-stu-id="ee5d0-271">manifest.webmanifest</span></span>  

<span data-ttu-id="ee5d0-272">在清单中，将 `display_override` array 设置为  `window-controls-overlay` 。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-272">In the manifest, set `display_override` array to  `window-controls-overlay`.</span></span>  <span data-ttu-id="ee5d0-273">将 `theme_color` 设置为标题栏的颜色选择。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-273">Set the `theme_color` to your choice of color for the title bar.</span></span>  <span data-ttu-id="ee5d0-274">在任一项或不受支持时，将显示模式 `display_override` `window-controls-overlay` 设置为适当的回退。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-274">Set the display mode to an appropriate fallback for when either `display_override` or `window-controls-overlay` isn't supported.</span></span>  

<span data-ttu-id="ee5d0-275">以下代码段包括建议的清单更新。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-275">The following code snippet includes the recommended manifest updates.</span></span>  

```json
{
  "name": "Example PWA",
  "display": "standalone",
  "display_override": [ 
    "window-controls-overlay" 
  ],
  "theme_color": "#254B85"
}
```  

### <a name="indexhtml"></a><span data-ttu-id="ee5d0-276">index.html</span><span class="sxs-lookup"><span data-stu-id="ee5d0-276">index.html</span></span>  

<span data-ttu-id="ee5d0-277">以下 ID 表示网页的两个主要区域。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-277">The following IDs represent the two main regions of the webpage.</span></span>  

*   `titleBarContainer`  
*   `mainContent`  
    
<span data-ttu-id="ee5d0-278">ID `div` 为 `titleBar` 的 元素设置为 ， `draggable` 搜索框 `input` 子元素设置为 `nonDraggable` 。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-278">The `div` element with the `titleBar` ID is set to `draggable` and the search box `input` child element is set to `nonDraggable`.</span></span>  

```html
<div id="titleBar" class=" draggable">
    <span class="draggable">Example PWA</span>
    <input class="nonDraggable" type="text" placeholder="Search"></input>
</div>
```

<span data-ttu-id="ee5d0-279">在具有 ID 的 元素中，具有 ID 的 表示标题栏区域中 `div` `titleBarContainer` `div` `titleBar` 的可见部分。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-279">In the `div` element with the `titleBarContainer` ID, the `div` with the `titleBar` ID represents the visible portion of the title bar area.</span></span>  

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width">
    <title>Example PWA</title>
    <link rel="stylesheet" href="style.css">
    <link rel="manifest" href="./manifest.webmanifest">
  </head>
  <body>
    <div id="titleBarContainer">
      <div id="titleBar" class=" draggable">
        <span class="draggable">Example PWA</span>
        <input class="nonDraggable" type="text" placeholder="Search"></input>
      </div>
    </div>
    <div id="mainContent"><!-- The rest of the webpage --></div>
  </body>
</html>
```  

### <a name="stylecss"></a><span data-ttu-id="ee5d0-280">style.css</span><span class="sxs-lookup"><span data-stu-id="ee5d0-280">style.css</span></span>  

<span data-ttu-id="ee5d0-281">使用 和 设置可拖动和非可拖动 `-webkit-app-region: drag` 区域 `-webkit-app-region: no-drag` 。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-281">The draggable and non-draggable regions are set using `-webkit-app-region: drag` and `-webkit-app-region: no-drag`.</span></span>  

```css
.draggable {
    app-region: drag;
    /* Pre-fix app-region during standardization process */
    -webkit-app-region: drag;
}

.nonDraggable {
    app-region: no-drag;
    /* Pre-fix app-region during standardization process */
    -webkit-app-region: no-drag;
}
```  

<span data-ttu-id="ee5d0-282">对于 `body` 元素，边距设置为 ，以确保标题栏 `0` 到达窗口的边缘。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-282">For the `body` element, margins are set to `0` to ensure the title bar reaches to the edges of the window.</span></span>  

```css
body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    margin: 0;
}
```  

<span data-ttu-id="ee5d0-283">`titleBarContainer`ID 使用 `position: absolute` 并设置 `top` `titlebar-area-inset-top` ，将容器附加到网页顶部。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-283">The `titleBarContainer` ID uses `position: absolute` and sets the `top` to `titlebar-area-inset-top`, which attaches the container to the top of the webpage.</span></span>  <span data-ttu-id="ee5d0-284">`bottom`如果窗口控件覆盖层不可见，则 设置为 并 `titlebar-area-inset-bottom` `100% - var(--fallback-title-bar-height)` 恢复为 。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-284">The `bottom` is set to `titlebar-area-inset-bottom` and falls back to `100% - var(--fallback-title-bar-height)` if the window controls overlay isn't visible.</span></span>  <span data-ttu-id="ee5d0-285">ID 的背景 `titleBarContainer` 颜色与 `theme_color` 相同。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-285">The background color of the `titleBarContainer` ID is the same as the `theme_color`.</span></span>  <span data-ttu-id="ee5d0-286">宽度设置为 ，以便元素填充网页的宽度，并且当对于连续外观可见时，该元素将流动在 `100%` `div` 覆盖层下。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-286">The width is set to `100%`, so that the `div` element fills the width of the webpage and flows under the overlay when it's visible for a contiguous appearance.</span></span>  

```css
#titleBarContainer {
    position: absolute;
    top: env(titlebar-area-y, 0);
    bottom: env(titlebar-area-height, calc(100% - var(--fallback-title-bar-height)));
    width: 100%;
    background-color:#254B85;
}
```  

<span data-ttu-id="ee5d0-287">`titleBar`ID 还使用 `position: absolute` 和 `top: titlebar-area-inset-top` ，以将它附加到窗口顶部。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-287">The `titleBar` ID also uses `position: absolute` and `top: titlebar-area-inset-top` to attaches it to the top of the window.</span></span>  <span data-ttu-id="ee5d0-288">默认情况下，它使用窗口的完整宽度。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-288">By default, it consumes the full width of the window.</span></span>  <span data-ttu-id="ee5d0-289">和 边缘分别设置为 和 ，两者在未 `left` `right` 设置值 `titlebar-area-inset-left` `titlebar-area-inset-right` `0` 时回退。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-289">The `left` and `right` edges are set to `titlebar-area-inset-left` and `titlebar-area-inset-right` respectively, both fall back to `0` when the values aren't set.</span></span>  <span data-ttu-id="ee5d0-290">它还设置 `user-select: none` 阻止任何尝试拖动占用的窗口，而是突出显示元素中的 `div` 文本。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-290">It also sets `user-select: none` to prevent any attempts to drag the window consumed instead it highlights text in the `div` element.</span></span>  

```css
#titleBar {
    position: absolute;
    top: 0;
    display: flex;
    user-select: none;
    height: 100%;
    left: env(titlebar-area-x, 0);
    right: env(titlebar-area-width, 0);
    color: #FFFFFF;
    font-weight: bold;
    text-align: center;
}

#titleBar > span {
    margin: auto;
    padding: 0px 16px 0px 16px;
}

#titleBar > input {
    flex: 1;
    margin: 8px;
    border-radius: 5px;
    border: none;
    padding: 8px;
}
```

<span data-ttu-id="ee5d0-291">ID 的 `mainContent` 容器也与 固定在一起 `position: absolute` ，并附加到网页底部。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-291">The container for the `mainContent` ID is also fixed in place with `position: absolute` and is attached to the bottom of the webpage.</span></span>  <span data-ttu-id="ee5d0-292">`height`设置为 并 `titlebar-area-inset-bottom` 回滚以填充 `100% - var(--fallback-titlebar-height)` 标题栏下方的剩余空间。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-292">The `height` is set to `titlebar-area-inset-bottom` and falls back to `100% - var(--fallback-titlebar-height)` to fill the remaining space below the title bar.</span></span>  <span data-ttu-id="ee5d0-293">它 `overflow-y: scroll` 设置 允许内容在容器中垂直滚动。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-293">It sets `overflow-y: scroll` to allow the contents to scroll vertically in the container.</span></span>  

```css
#mainContent {
    position: absolute;
    left: 0;
    right: 0;
    bottom: 0;
    height: env(titlebar-area-height, calc(100% - var(--fallback-title-bar-height)));
    overflow-y: scroll;
}
```

<span data-ttu-id="ee5d0-294">对于浏览器不支持窗口控件覆盖的情况，添加 CSS 变量以设置标题栏的默认高度。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-294">For cases where the browser doesn't support the window controls overlay, a CSS variable is added to set a default height for the title bar.</span></span>  <span data-ttu-id="ee5d0-295">和 ID 的界限最初设置为填充整个客户端区域，如果覆盖层不受支持，则不需要 `titleBarContainer` `mainContent` 更改。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-295">The bounds of the `titleBarContainer` and `mainContent` IDs are initially set to fill the entire client area, and you don't need to change it if the overlay isn't supported.</span></span>  

<span data-ttu-id="ee5d0-296">以下代码段包括所有建议的 CSS 更新。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-296">The following code snippet includes all the recommended CSS updates.</span></span>

```css
:root {
  --fallback-title-bar-height: 40px;
}

.draggable {
  app-region: drag;
  /* Pre-fix app-region during standardization process */
  -webkit-app-region: drag;
}

.nonDraggable {
  app-region: no-drag;
  /* Pre-fix app-region during standardization process */
  -webkit-app-region: no-drag;
}

body {
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  margin: 0;
}

#titleBarContainer {
  position: absolute;
  top: env(titlebar-area-y, 0);
  bottom: env(titlebar-area-height, calc(100% - var(--fallback-title-bar-height)));
  width: 100%;
  background-color:#254B85;
}

#titleBar {
  position: absolute;
  top: 0;
  display: flex;
  user-select: none;
  height: 100%;
  left: env(titlebar-area-x, 0);
  right: env(titlebar-area-width, 0);
  color: #FFFFFF;
  font-weight: bold;
  text-align: center;
}

#titleBar > span {
  margin: auto;
  padding: 0px 16px 0px 16px;
}

#titleBar > input {
  flex: 1;
  margin: 8px;
  border-radius: 5px;
  border: none;
  padding: 8px;
}

#mainContent {
  position: absolute;
  left: 0;
  right: 0;
  bottom: 0;
  height: env(titlebar-area-height, calc(100% - var(--fallback-title-bar-height)));
  overflow-y: scroll;
}
```  

## <a name="run-on-os-login"></a><span data-ttu-id="ee5d0-297">在操作系统登录时运行</span><span class="sxs-lookup"><span data-stu-id="ee5d0-297">Run On OS Login</span></span>  

<span data-ttu-id="ee5d0-298">此功能允许你将应用配置为在用户登录 Microsoft Windows 时自动启动。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-298">This feature allows you to configure your app to automatically launch when the user logs into Microsoft Windows.</span></span>  <span data-ttu-id="ee5d0-299">多个应用类利用此功能。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-299">Several classes of apps take advantage of the capability.</span></span>  <span data-ttu-id="ee5d0-300">应用类包括电子邮件、聊天、监视仪表板和实时数据显示应用。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-300">The classes of apps include email, chat, monitoring dashboard, and real-time data display apps.</span></span>  <span data-ttu-id="ee5d0-301">该功能允许用户在用户登录到操作系统后尽快使用应用。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-301">The capability allows a user to engage with the apps as soon as the user logs into the OS.</span></span>  <span data-ttu-id="ee5d0-302">此功能自动启动 PWA 的方式与手动启动 PWA 的方式相同。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-302">This feature automatically starts the PWA the same way it's launched manually.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="ee5d0-303">**在操作系统登录上运行** 是一 [项强大的功能][GithubW3cPermissionsPowerfulFeature]。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-303">**Run on OS Login** is a [powerful feature][GithubW3cPermissionsPowerfulFeature].</span></span>  <span data-ttu-id="ee5d0-304">用户应决定是否为已安装的 Web 应用启用该功能。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-304">Users should decide whether to turn on the capability for the installed web app.</span></span>  

### <a name="turn-on-run-on-os-login"></a><span data-ttu-id="ee5d0-305">打开"在操作系统登录时运行"</span><span class="sxs-lookup"><span data-stu-id="ee5d0-305">Turn on Run On OS Login</span></span>  

<span data-ttu-id="ee5d0-306">若要预览 PWA**的"在操作系统**登录时运行"功能，[](#turn-on-experimental-features)请导航到"打开实验性功能"，然后打开"在操作系统登录时**运行桌面 PWA"。**</span><span class="sxs-lookup"><span data-stu-id="ee5d0-306">To preview the **Run On OS Login** capabilities for your PWA, navigate to [Turn on experimental features](#turn-on-experimental-features) and turn on **Desktop PWAs run on OS login**.</span></span>  

:::image type="complex" source="../media/desktop-pwas-run-on-os-login-flag.png" alt-text="打开在操作系统登录实验上运行的桌面 PBA" lightbox="../media/desktop-pwas-run-on-os-login-flag.png":::
   <span data-ttu-id="ee5d0-308">打开在**操作系统登录实验上运行的桌面 PBA**</span><span class="sxs-lookup"><span data-stu-id="ee5d0-308">Turn on the **Desktop PWAs run on OS login** experiment</span></span>  
:::image-end:::  

### <a name="turn-on-the-feature-for-the-installed-web-app"></a><span data-ttu-id="ee5d0-309">打开已安装的 Web 应用的功能</span><span class="sxs-lookup"><span data-stu-id="ee5d0-309">Turn on the feature for the installed web app</span></span>  

<span data-ttu-id="ee5d0-310">若要为已安装 `Start app when you sign in` 的 PWA 启用该功能，</span><span class="sxs-lookup"><span data-stu-id="ee5d0-310">To turn on the `Start app when you sign in` feature for an installed PWA,</span></span> 

1.  <span data-ttu-id="ee5d0-311">打开 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-311">Open Microsoft Edge.</span></span>   
1.  <span data-ttu-id="ee5d0-312">导航到 `edge://apps` 。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-312">Navigate to `edge://apps`.</span></span>  
1.  <span data-ttu-id="ee5d0-313">将鼠标悬停在你的应用上。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-313">Hover on your app.</span></span>  
1.  <span data-ttu-id="ee5d0-314">打开上下文菜单 \ (右键单击\) 然后在登录时选择 **"启动应用"。**</span><span class="sxs-lookup"><span data-stu-id="ee5d0-314">Open the contextual menu \(right-click\) and then choose **Start app when you sign in**.</span></span>  
    
    :::image type="complex" source="../media/turn-on-run-on-os-login-flag.png" alt-text="在 Microsoft Edge 中登录功能时，使用上下文菜单打开开始应用" lightbox="../media/turn-on-run-on-os-login-flag.png":::
       <span data-ttu-id="ee5d0-316">在 Microsoft Edge 中登录功能时 **，** 使用上下文菜单打开"开始"应用</span><span class="sxs-lookup"><span data-stu-id="ee5d0-316">Use the contextual menu to turn on the **Start app when you sign in** feature in Microsoft Edge</span></span>  
    :::image-end:::  
    
## <a name="shortcuts"></a><span data-ttu-id="ee5d0-317">快捷方式</span><span class="sxs-lookup"><span data-stu-id="ee5d0-317">Shortcuts</span></span>  

`Shortcuts` <span data-ttu-id="ee5d0-318">是清单文件的一个新增成员。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-318">is a new member of the manifest file.</span></span>  <span data-ttu-id="ee5d0-319">它允许你在 Web 应用中定义指向部件、关键网页或操作的链接。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-319">It allows you to define links to parts, key webpages, or actions in your web app.</span></span>  <span data-ttu-id="ee5d0-320">Microsoft Windows 将其集成为 **Jumplists**。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-320">Microsoft Windows integrates it as **Jumplists**.</span></span>  <span data-ttu-id="ee5d0-321">**Jumplist 定义** 在下列 UI 元素之一上打开上下文菜单 \ (右键单击\) 时出现的弹出菜单。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-321">**Jumplists** define popup menus that appear when you on one of the following UI elements and open a contextual menu \(right-click\).</span></span>  

*   <span data-ttu-id="ee5d0-322">"开始"菜单上的磁贴</span><span class="sxs-lookup"><span data-stu-id="ee5d0-322">A tile on the Start Menu</span></span>  
*   <span data-ttu-id="ee5d0-323">任务栏上的图标</span><span class="sxs-lookup"><span data-stu-id="ee5d0-323">An icon on the Taskbar</span></span>  
    
<span data-ttu-id="ee5d0-324">当用户调用快捷方式时，用户将导航到该快捷方式的成员 `url` 指定的地址。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-324">When a user invokes a shortcut, the user navigates to the address specified by the `url` member of the shortcut.</span></span>  
  
:::image type="complex" source="../media/jumplists-on-windows-10.png" alt-text="Windows 10 上的 Jumplist 示例" lightbox="../media/jumplists-on-windows-10.png":::
   <span data-ttu-id="ee5d0-326">Windows 10 **上的 Jumplist** 示例</span><span class="sxs-lookup"><span data-stu-id="ee5d0-326">An example of **Jumplists** on Windows 10</span></span>  
:::image-end:::  

### <a name="shortcuts-in-the-manifest-file"></a><span data-ttu-id="ee5d0-327">清单文件的快捷方式</span><span class="sxs-lookup"><span data-stu-id="ee5d0-327">Shortcuts in the Manifest file</span></span>  

```json
"shortcuts" : [
  {
    "name": "Today's agenda",
    "url": "/today",
    "description": "List of events planned for today"
  },
  {
    "name": "New event",
    "url": "/create/event"
  },
  {
    "name": "New reminder",
    "url": "/create/reminder"
  }
]
```  

#### <a name="properties-of-shortcuts"></a><span data-ttu-id="ee5d0-328">快捷方式的属性</span><span class="sxs-lookup"><span data-stu-id="ee5d0-328">Properties of shortcuts</span></span>  

<span data-ttu-id="ee5d0-329">以下属性定义每个快捷方式。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-329">The following properties define each shortcut.</span></span>  

| <span data-ttu-id="ee5d0-330">属性</span><span class="sxs-lookup"><span data-stu-id="ee5d0-330">Property</span></span> | <span data-ttu-id="ee5d0-331">详细信息</span><span class="sxs-lookup"><span data-stu-id="ee5d0-331">Details</span></span> |  
|:--- |:--- |  
| `name` | <span data-ttu-id="ee5d0-332">在跳转列表或上下文 **菜单上向** 用户显示的字符串。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-332">A string that is displayed to the user on **Jumplists** or the contextual menu.</span></span> |  
| `short_name` | <span data-ttu-id="ee5d0-333">当空间不足，无法显示快捷方式的完整名称时显示的字符串。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-333">A string that is displayed when insufficient space exists to display the full name of the shortcut.</span></span> |  
| `description` | <span data-ttu-id="ee5d0-334">一个描述快捷方式用途的字符串。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-334">A string that describes the purpose of the shortcut.</span></span>  <span data-ttu-id="ee5d0-335">它可能会由辅助技术访问。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-335">It may be accessed by assistive technology.</span></span> |  
| `url` | <span data-ttu-id="ee5d0-336">激活快捷方式时打开的 Web 应用中的 URI。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-336">The URI in the web app that opens when the shortcut is activated.</span></span> |  
| `icons` | <span data-ttu-id="ee5d0-337">一组表示快捷方式的图标。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-337">A set of icons that represents the shortcut.</span></span> |  

## <a name="file-handling"></a><span data-ttu-id="ee5d0-338">文件处理</span><span class="sxs-lookup"><span data-stu-id="ee5d0-338">File Handling</span></span>  

<span data-ttu-id="ee5d0-339">注册为文件类型处理程序的能力在试验阶段。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-339">The ability to register as a file type handler is in the experimentation phase.</span></span>  <span data-ttu-id="ee5d0-340">你可以指定应用在清单条目中处理的文件类型。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-340">You may specify the file types that your app handles in a manifest entry.</span></span>  <span data-ttu-id="ee5d0-341">在安装过程中，用户的主机操作系统将你的应用注册为列出的文件类型的文件处理程序。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-341">During installation, the user's host OS registers your app as a file handler for the listed file types.</span></span>  <span data-ttu-id="ee5d0-342">确保应用启动代码中存在此功能， `launchQueue` 并确保它处理文件。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-342">Ensure the existence of the feature `launchQueue` in your apps startup code and that it handles the file.</span></span>  

<span data-ttu-id="ee5d0-343">基于 Chromium 的浏览器正在测试和塑造此功能。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-343">Chromium-based browsers are testing and shaping this feature.</span></span>  <span data-ttu-id="ee5d0-344">有关详细信息（包括代码示例），请导航到["允许 Web 应用程序成为文件处理程序"。][WebDevFileHandling]</span><span class="sxs-lookup"><span data-stu-id="ee5d0-344">For more information including code examples, navigate to [Let web applications be file handlers][WebDevFileHandling].</span></span>  

<span data-ttu-id="ee5d0-345">若要预览适用于 Windows 10 的 Microsoft Edge 中的文件处理，请导航到打开实验[性](#turn-on-experimental-features)功能，然后打开文件**处理 API。**</span><span class="sxs-lookup"><span data-stu-id="ee5d0-345">To preview file handling in Microsoft Edge for Windows 10, navigate to [Turn on experimental features](#turn-on-experimental-features) and turn on **File Handling API**.</span></span>  
    
## <a name="providing-feedback-on-experimental-features"></a><span data-ttu-id="ee5d0-346">提供有关试验功能的反馈</span><span class="sxs-lookup"><span data-stu-id="ee5d0-346">Providing feedback on experimental features</span></span>  

<span data-ttu-id="ee5d0-347">提供有关 Microsoft Edge Web 应用实验的反馈。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-347">To provide feedback on Microsoft Edge web app experiments.</span></span>  

*   <span data-ttu-id="ee5d0-348">使用 **设置和更多** \ (`...` \) > 将反馈发送到 Microsoft **发送反馈**。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-348">Send your feedback using **Settings and More** \(`...`\) > **Send Feedback to Microsoft**.</span></span>  
*   <span data-ttu-id="ee5d0-349">选择 `Alt` + `Shift` + `I` 。</span><span class="sxs-lookup"><span data-stu-id="ee5d0-349">Select `Alt`+`Shift`+`I`.</span></span>  
    
:::image type="complex" source="../media/send-feedback-from-progressive-web-app.png" alt-text="从 PWA 发送反馈" lightbox="../media/send-feedback-from-progressive-web-app.png":::
   <span data-ttu-id="ee5d0-351">从 PWA 发送反馈</span><span class="sxs-lookup"><span data-stu-id="ee5d0-351">Send Feedback from your PWA</span></span>  
:::image-end:::  

<!-- links -->  

[MicrosoftEdgeMain]: https://www.microsoft.com/edge "Microsoft Edge"  

[MicrosoftDeveloperMicrosoftEdgeOriginTrials]: https://developer.microsoft.com/microsoft-edge/origin-trials "源试用版|Microsoft Edge 开发人员"  
[MicrosoftDeveloperMicrosoftEdgeOriginTrialsWebAppProtocolHandlerRegistrationRegistration]: https://developer.microsoft.com/microsoft-edge/origin-trials/web-app-protocol-handler-registration/registration "注册 Web 应用协议处理程序|Microsoft 开发人员"  

[MdnDocsWebApiNavigatorRegisterprotocolhandlerWebBasedProtocolHandlers]: https://developer.mozilla.org/docs/Web/API/Navigator/registerProtocolHandler/Web-based_protocol_handlers "基于 Web 的协议处理程序|MDN"  

[GithubW3cPermissionsPowerfulFeature]: https://w3c.github.io/permissions#powerful-feature "强大的功能 - 权限|GitHub"  

[GithubWicgPwaUrlHandlerBlobMainExplainerMd]: https://github.com/WICG/pwa-url-handler/blob/main/explainer.md "作为 URL 处理程序的 PWA |GitHub"  

[WebDevFileHandling]: https://web.dev/file-handling "让 Web 应用程序成为文件处理程序|web.dev"  
