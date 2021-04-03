---
description: Microsoft Edge for Web Apps 中的最新实验功能
title: 实验功能|渐进式 Web 应用
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/02/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， 实验， 渐进式 Web 应用， Web 应用， PWA， PWA
ms.openlocfilehash: 587797bc8577f1c1aaca42394eecb997d21e9955
ms.sourcegitcommit: f605e4e27fed88aca286f2ae236e27f9a396b517
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "11474954"
---
# <a name="experimental-features-in-progressive-web-apps-pwas"></a><span data-ttu-id="b36f6-104">渐进式 Web 应用和 PBA (实验) </span><span class="sxs-lookup"><span data-stu-id="b36f6-104">Experimental features in Progressive Web Apps (PWAs)</span></span>  

<span data-ttu-id="b36f6-105">Microsoft Edge 提供对仍在开发中的实验性功能的访问权限。</span><span class="sxs-lookup"><span data-stu-id="b36f6-105">Microsoft Edge provides access to experimental features that are still in development.</span></span>  <span data-ttu-id="b36f6-106">若要确定每个功能是否就绪以及何时发布每个功能，请进行测试 [并提供反馈](#providing-feedback-on-experimental-features)。</span><span class="sxs-lookup"><span data-stu-id="b36f6-106">To determine if each feature is ready and when to release each, test and [provide feedback](#providing-feedback-on-experimental-features).</span></span>  

<span data-ttu-id="b36f6-107">实验功能在 Microsoft Edge 的所有渠道中均可用，但最新的实验功能仅在 Microsoft Edge Canary 渠道中可用。</span><span class="sxs-lookup"><span data-stu-id="b36f6-107">Experimental features are available in all channels of Microsoft Edge, but the latest experimental features are only available in the Microsoft Edge Canary channel.</span></span>  

## <a name="turn-on-experimental-features"></a><span data-ttu-id="b36f6-108">打开试验功能</span><span class="sxs-lookup"><span data-stu-id="b36f6-108">Turn on experimental features</span></span>  

<span data-ttu-id="b36f6-109">若要在 Microsoft Edge 中打开\（或关闭\）试验功能，请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="b36f6-109">To turn on \(or off\) experimental features in Microsoft Edge, complete the following steps.</span></span>  
  
1.  <span data-ttu-id="b36f6-110">打开 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="b36f6-110">Open Microsoft Edge.</span></span>   
    
    > [!NOTE]
    > <span data-ttu-id="b36f6-111">确保使用本文中列出的实验的 Microsoft Edge 版本。</span><span class="sxs-lookup"><span data-stu-id="b36f6-111">Ensure you use a Microsoft Edge version that has the Experiment listed in this article.</span></span>  <span data-ttu-id="b36f6-112">导航到 [实验功能](#features-that-are-available-to-test)。</span><span class="sxs-lookup"><span data-stu-id="b36f6-112">Navigate to [Experimental features](#features-that-are-available-to-test).</span></span>  
    
1.  <span data-ttu-id="b36f6-113">导航到 `edge://flags` 。</span><span class="sxs-lookup"><span data-stu-id="b36f6-113">Navigate to `edge://flags`.</span></span>  
1.  <span data-ttu-id="b36f6-114">导航到相关实验。</span><span class="sxs-lookup"><span data-stu-id="b36f6-114">Navigate to the relevant experiment.</span></span>  
1.  <span data-ttu-id="b36f6-115">选择实验说明旁边的下拉菜单并选择 `Enabled` 。</span><span class="sxs-lookup"><span data-stu-id="b36f6-115">Choose the dropdown menu next to the experiment description and choose `Enabled`.</span></span>  
    
    :::image type="complex" source="../media/turn-on-experimental-flag.png" alt-text="选择启用以打开实验" lightbox="../media/turn-on-experimental-flag.png":::
       <span data-ttu-id="b36f6-117">选择 **启用** 以打开实验</span><span class="sxs-lookup"><span data-stu-id="b36f6-117">Choose **Enabled** to turn on an experiment</span></span>  
    :::image-end:::  
    
    > [!NOTE]
    > <span data-ttu-id="b36f6-118">每个实验通常都有一个下拉菜单来选择以下值。</span><span class="sxs-lookup"><span data-stu-id="b36f6-118">Each experiment usually has a dropdown menu to choose the following values.</span></span>  <span data-ttu-id="b36f6-119">如果实验功能在实验上没有条目，则提供\*\*\*\* 说明以使用命令行使用该功能启动 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="b36f6-119">If an experimental feature doesn't have an entry on **Experiments**, instructions are provided to start Microsoft Edge with that feature using the command-line.</span></span>
    > 
    > *   `Default`  
    > *   `Disabled`  
    > *   `Enabled`  
    
1.  <span data-ttu-id="b36f6-120">重启 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="b36f6-120">Restart Microsoft Edge.</span></span>  
    
### <a name="origin-trials"></a><span data-ttu-id="b36f6-121">原始试验</span><span class="sxs-lookup"><span data-stu-id="b36f6-121">Origin Trials</span></span>  

<span data-ttu-id="b36f6-122">Microsoft Edge 有时使用源试用版来测试特定域或网站的功能。</span><span class="sxs-lookup"><span data-stu-id="b36f6-122">Microsoft Edge sometimes uses origin trials to test features for specific domains or websites.</span></span>  <span data-ttu-id="b36f6-123">你可能想要对网站使用源试用版来应用特定功能。</span><span class="sxs-lookup"><span data-stu-id="b36f6-123">You may want to use an origin trial for your website to apply a specific feature.</span></span>  <span data-ttu-id="b36f6-124">如果你是网站所有者，你可以注册源试用版。</span><span class="sxs-lookup"><span data-stu-id="b36f6-124">If you're a website owner, you may enroll in an origin trial.</span></span>  <span data-ttu-id="b36f6-125">源试用版向访问你的网站的 Microsoft Edge 用户提供一定比例的功能。</span><span class="sxs-lookup"><span data-stu-id="b36f6-125">An origin trial provides features to a percentage of Microsoft Edge users who visit your website.</span></span>

<span data-ttu-id="b36f6-126">有关源试用版详细信息，请导航到 [Microsoft Edge Origin Trials 开发人员控制台][MicrosoftDeveloperMicrosoftEdgeOriginTrials]。</span><span class="sxs-lookup"><span data-stu-id="b36f6-126">For more information about Origin Trials, navigate to [Microsoft Edge Origin Trials Developer Console][MicrosoftDeveloperMicrosoftEdgeOriginTrials].</span></span>  
    
> [!NOTE]
> <span data-ttu-id="b36f6-127">实验性功能会不断更新，并且可能会导致性能问题。</span><span class="sxs-lookup"><span data-stu-id="b36f6-127">Experimental features are constantly updated and may cause performance issues.</span></span>  <span data-ttu-id="b36f6-128">若要关闭实验功能，请导航到打开 [实验](#turn-on-experimental-features)功能，导航到实验，然后选择 `Disabled` 。</span><span class="sxs-lookup"><span data-stu-id="b36f6-128">To turn off an experimental feature, navigate to [Turn on experimental features](#turn-on-experimental-features), navigate to the experiment, and then choose `Disabled`.</span></span>  

## <a name="features-that-are-available-to-test"></a><span data-ttu-id="b36f6-129">可供测试的功能</span><span class="sxs-lookup"><span data-stu-id="b36f6-129">Features that are available to test</span></span>  

<span data-ttu-id="b36f6-130">以下列表介绍了可在 Microsoft Edge 上测试和验证的新实验性 Web 应用功能。</span><span class="sxs-lookup"><span data-stu-id="b36f6-130">The following list describes the new experimental web app features that are available to test and validate on Microsoft Edge.</span></span>  

| <span data-ttu-id="b36f6-131">功能</span><span class="sxs-lookup"><span data-stu-id="b36f6-131">Feature</span></span> | <span data-ttu-id="b36f6-132">Microsoft Edge 版本</span><span class="sxs-lookup"><span data-stu-id="b36f6-132">Microsoft Edge version</span></span> | <span data-ttu-id="b36f6-133">平台</span><span class="sxs-lookup"><span data-stu-id="b36f6-133">Platform</span></span> |  
|:--- |:--- |:--- |  
| [<span data-ttu-id="b36f6-134">URI 协议处理</span><span class="sxs-lookup"><span data-stu-id="b36f6-134">URI Protocol Handling</span></span>](#uri-protocol-handling) | <span data-ttu-id="b36f6-135">91 或更高版本</span><span class="sxs-lookup"><span data-stu-id="b36f6-135">91 or later</span></span> | <span data-ttu-id="b36f6-136">Windows</span><span class="sxs-lookup"><span data-stu-id="b36f6-136">Windows</span></span> |    
| [<span data-ttu-id="b36f6-137">URL 链接处理</span><span class="sxs-lookup"><span data-stu-id="b36f6-137">URL Link Handling</span></span>](#url-link-handling) | <span data-ttu-id="b36f6-138">91 或更高版本</span><span class="sxs-lookup"><span data-stu-id="b36f6-138">91 or later</span></span> | <span data-ttu-id="b36f6-139">Windows</span><span class="sxs-lookup"><span data-stu-id="b36f6-139">Windows</span></span>|  
| [<span data-ttu-id="b36f6-140">在操作系统登录时运行</span><span class="sxs-lookup"><span data-stu-id="b36f6-140">Run on OS Login</span></span>](#run-on-os-login) | <span data-ttu-id="b36f6-141">88 或更高版本</span><span class="sxs-lookup"><span data-stu-id="b36f6-141">88 or later</span></span> | <span data-ttu-id="b36f6-142">全部</span><span class="sxs-lookup"><span data-stu-id="b36f6-142">All</span></span> |  
| [<span data-ttu-id="b36f6-143">快捷方式</span><span class="sxs-lookup"><span data-stu-id="b36f6-143">Shortcuts</span></span>](#shortcuts) | <span data-ttu-id="b36f6-144">87 或更高版本</span><span class="sxs-lookup"><span data-stu-id="b36f6-144">87 or later</span></span> | <span data-ttu-id="b36f6-145">全部</span><span class="sxs-lookup"><span data-stu-id="b36f6-145">All</span></span> |  
| [<span data-ttu-id="b36f6-146">文件处理</span><span class="sxs-lookup"><span data-stu-id="b36f6-146">File Handling</span></span>](#file-handling) | <span data-ttu-id="b36f6-147">83 或更高版本</span><span class="sxs-lookup"><span data-stu-id="b36f6-147">83 or later</span></span> | <span data-ttu-id="b36f6-148">所有桌面</span><span class="sxs-lookup"><span data-stu-id="b36f6-148">All Desktop</span></span> |  


## <a name="uri-protocol-handling"></a><span data-ttu-id="b36f6-149">URI 协议处理</span><span class="sxs-lookup"><span data-stu-id="b36f6-149">URI Protocol Handling</span></span>  

<span data-ttu-id="b36f6-150">统一资源标识符 \ (URI\) 可用于定义使用 HTTP 或 FTP 协议的网页和 Web 内容的链接。</span><span class="sxs-lookup"><span data-stu-id="b36f6-150">A uniform resource identifier \(URI\) may be used to define more than just links to webpages and web content using the HTTP or FTP protocol.</span></span>  <span data-ttu-id="b36f6-151">URI 可用于描述指向您编成架构中任何内容的链接。</span><span class="sxs-lookup"><span data-stu-id="b36f6-151">URIs may be used to describe links to anything that you codify into a schema.</span></span>  <span data-ttu-id="b36f6-152">例如，协议用于描述电子邮件链接，操作系统 `mailto://` \ (OS\) 或浏览器决定哪个网页或应用应处理该协议。</span><span class="sxs-lookup"><span data-stu-id="b36f6-152">For example, the `mailto://` protocol is used to describe an email link and the operating system \(OS\) or browser decides which webpage or app should handle that protocol.</span></span>  

<span data-ttu-id="b36f6-153">有关基于浏览器的现有支持，请导航到基于 [Web 的协议处理程序][MdnDocsWebApiNavigatorRegisterprotocolhandlerWebBasedProtocolHandlers]。</span><span class="sxs-lookup"><span data-stu-id="b36f6-153">For more information about existing browser-based support, navigate to [Web-based protocol handlers][MdnDocsWebApiNavigatorRegisterprotocolhandlerWebBasedProtocolHandlers].</span></span>  

<span data-ttu-id="b36f6-154">此功能允许您完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="b36f6-154">This feature allows you to complete the following actions.</span></span>  

*   <span data-ttu-id="b36f6-155">使用 Web 应用程序的清单向主机操作系统注册 PWA</span><span class="sxs-lookup"><span data-stu-id="b36f6-155">Register your PWA with the host OS using the manifest of your web app</span></span>
*   <span data-ttu-id="b36f6-156">声明 PWA 处理特定 URI 协议</span><span class="sxs-lookup"><span data-stu-id="b36f6-156">Declare that a PWA handles a specific URI protocol</span></span>  
     
<span data-ttu-id="b36f6-157">将 PWA 注册为协议处理程序后，当用户选择具有特定方案（如浏览器或本机应用）的超链接时，已注册的 PWA 由操作系统激活并接收 `mailto://` `web+music://` URI。</span><span class="sxs-lookup"><span data-stu-id="b36f6-157">After you register a PWA as a protocol handler, when a user chooses a hyperlink with a specific scheme such as `mailto://` or `web+music://` from a browser or a native app, the registered PWA is activated by the OS and receives the URI.</span></span>  

<span data-ttu-id="b36f6-158">此功能要求你更新 Web 应用清单以在需要指定两个字段的 `protocol_handlers` 数组中包括数组：</span><span class="sxs-lookup"><span data-stu-id="b36f6-158">This feature requires you to update the web app manifest to include a `protocol_handlers` array, in the array you need to specify two fields:</span></span>  

*   `protocol`<span data-ttu-id="b36f6-159">：用于处理请求的协议，例如 或 `mailto` `web+jngl` 。</span><span class="sxs-lookup"><span data-stu-id="b36f6-159">:  The protocol to handle the request, for example `mailto` or `web+jngl`.</span></span>  
*   `url`<span data-ttu-id="b36f6-160">：处理协议的应用作用域中的 HTTPS URI。</span><span class="sxs-lookup"><span data-stu-id="b36f6-160">: The HTTPS URI in the app scope that handles the protocol.</span></span>  <span data-ttu-id="b36f6-161">将来，计划替换以协议处理程序方案开始的 `%s` URI。</span><span class="sxs-lookup"><span data-stu-id="b36f6-161">In the future, the URI starting with the protocol handlers scheme is planned to replace the `%s` token.</span></span>  
    
<span data-ttu-id="b36f6-162">更新清单以支持要注册的协议。</span><span class="sxs-lookup"><span data-stu-id="b36f6-162">Update your manifest to support the protocol that you want to register.</span></span>  <span data-ttu-id="b36f6-163">启用此功能后，Microsoft Edge 将完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="b36f6-163">After you turn on this feature, Microsoft Edge completes the following actions.</span></span>  

1.  <span data-ttu-id="b36f6-164">检测清单中的更改</span><span class="sxs-lookup"><span data-stu-id="b36f6-164">Detects changes in the manifest</span></span>  
1.  <span data-ttu-id="b36f6-165">为协议注册应用</span><span class="sxs-lookup"><span data-stu-id="b36f6-165">Registers the app for the protocol</span></span>  
    
<span data-ttu-id="b36f6-166">如果多个应用注册协议，则向用户显示提示。</span><span class="sxs-lookup"><span data-stu-id="b36f6-166">If more than one app registers a protocol, the user is presented with a prompt.</span></span>  <span data-ttu-id="b36f6-167">用户从操作系统或浏览器呈现的列表中选择相应的应用。</span><span class="sxs-lookup"><span data-stu-id="b36f6-167">The user chooses the appropriate app from the list presented by the OS or browser.</span></span>  

<span data-ttu-id="b36f6-168">若要在 Windows 上的 Microsoft Edge 中[](#turn-on-experimental-features)预览协议处理，请导航到打开实验性功能，然后打开**桌面 Web 应用支持协议处理程序**。</span><span class="sxs-lookup"><span data-stu-id="b36f6-168">To preview protocol handling in Microsoft Edge on Windows, navigate to [Turn on experimental features](#turn-on-experimental-features) and turn on **Desktop Web Apps support Protocol Handlers**.</span></span>  

<span data-ttu-id="b36f6-169">有关为协议处理程序运行的源试用版详细信息，请导航到注册 [Web 应用协议处理程序注册][MicrosoftDeveloperMicrosoftEdgeOriginTrialsWebAppProtocolHandlerRegistrationRegistration]。</span><span class="sxs-lookup"><span data-stu-id="b36f6-169">For more information about origin trial is running for protocol handlers, navigate to [Register for Web App Protocol Handler Registration][MicrosoftDeveloperMicrosoftEdgeOriginTrialsWebAppProtocolHandlerRegistrationRegistration].</span></span>  

### <a name="example-manifest"></a><span data-ttu-id="b36f6-170">示例清单</span><span class="sxs-lookup"><span data-stu-id="b36f6-170">Example Manifest</span></span>

<span data-ttu-id="b36f6-171">在此例中，Web 应用清单声明应用应注册为处理协议 和 `web+jngl` `web+jnglstore` 。</span><span class="sxs-lookup"><span data-stu-id="b36f6-171">In this example, a web app manifest declares that the app should be registered to handle the protocols `web+jngl` and `web+jnglstore`.</span></span>

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
 
## <a name="url-link-handling"></a><span data-ttu-id="b36f6-172">URL 链接处理</span><span class="sxs-lookup"><span data-stu-id="b36f6-172">URL Link Handling</span></span>  

<span data-ttu-id="b36f6-173">统一资源定位器 \ (URL\) 是一种 URI。</span><span class="sxs-lookup"><span data-stu-id="b36f6-173">A uniform resource locator \(URL\) is a type of URI.</span></span>  <span data-ttu-id="b36f6-174">当渐进 Web 应用 \ (PWA\) 注册为 https URI 的处理程序时，创建更具吸引力的体验。</span><span class="sxs-lookup"><span data-stu-id="b36f6-174">Create a more engaging experience when Progressive Web Apps \(PWAs\) register as handlers for https URIs.</span></span>  <span data-ttu-id="b36f6-175">PBA 可能会请求在激活关联的 URI 时启动。</span><span class="sxs-lookup"><span data-stu-id="b36f6-175">PWAs may request to launch when associated URIs are activated.</span></span>  <span data-ttu-id="b36f6-176">例如，如果用户从电子邮件中选择指向新闻文章的链接。</span><span class="sxs-lookup"><span data-stu-id="b36f6-176">For example, if a user chooses a link to a news story from an email message.</span></span>  <span data-ttu-id="b36f6-177">用于显示新闻文章的关联 PWA 将自动启动以处理链接的激活。</span><span class="sxs-lookup"><span data-stu-id="b36f6-177">An associated PWA to display news stories is automatically launched to handle the activation of the link.</span></span>  

<span data-ttu-id="b36f6-178">此功能允许您使用 Web 应用程序清单向浏览器注册 PWA，并声明浏览器处理特定链接。</span><span class="sxs-lookup"><span data-stu-id="b36f6-178">This feature allows you to register a PWA with the browser using the web app manifest and declare that the browser handles specific links.</span></span>  <span data-ttu-id="b36f6-179">若要在浏览器中注册 PWA，请向清单 `url_handlers` 文件添加可选成员。</span><span class="sxs-lookup"><span data-stu-id="b36f6-179">To register a PWA with the browser, add the optional `url_handlers` member to the manifest file.</span></span>  <span data-ttu-id="b36f6-180">`url_handlers`成员是 `object[]` 一个 ，用于对应用希望处理的 URI 的来源进行分组。</span><span class="sxs-lookup"><span data-stu-id="b36f6-180">The `url_handlers` member is an `object[]` that groups the origins of URIs that the app wishes to handle.</span></span>  

<span data-ttu-id="b36f6-181">浏览器使用位于源上的 `web-app-origin-association` JSON 文件验证链接处理。</span><span class="sxs-lookup"><span data-stu-id="b36f6-181">Link handling is validated by the browser using a `web-app-origin-association` JSON file that is located on the origin.</span></span>  <span data-ttu-id="b36f6-182">源文件进一步微调源的包含路径或排除路径。</span><span class="sxs-lookup"><span data-stu-id="b36f6-182">The origin file further fine-tunes the included or excluded paths at the origin.</span></span>  <span data-ttu-id="b36f6-183">有关测试 URL 处理程序的详细说明，请导航到[作为 URL 处理程序的 PWA。][GithubWicgPwaUrlHandlerBlobMainExplainerMd]</span><span class="sxs-lookup"><span data-stu-id="b36f6-183">For detailed instructions about testing the URL handler, navigate to [PWAs as URL Handlers][GithubWicgPwaUrlHandlerBlobMainExplainerMd].</span></span>  

<span data-ttu-id="b36f6-184">若要在 Windows 上的 Microsoft Edge 中预览 URL 链接处理，请导航到"[打开](#turn-on-experimental-features)实验性功能"，然后打开"**桌面 PWA URL 处理"。**</span><span class="sxs-lookup"><span data-stu-id="b36f6-184">To preview URL link handling in Microsoft Edge on Windows, navigate to [Turn on experimental features](#turn-on-experimental-features) and turn on **Desktop PWA URL  Handling**.</span></span>  

### <a name="example-of-the-url_handlers-in-the-manifest"></a><span data-ttu-id="b36f6-185">清单url_handlers示例</span><span class="sxs-lookup"><span data-stu-id="b36f6-185">Example of the url_handlers in the manifest</span></span>  

<span data-ttu-id="b36f6-186">以下代码段是包含 成员的示例 Web 应用 `url_handlers` 清单。</span><span class="sxs-lookup"><span data-stu-id="b36f6-186">The following code snippet is an example web app manifest with the `url_handlers` member.</span></span>  

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

<span data-ttu-id="b36f6-187">如果 URI 与 中的一个源字符串匹配，并且浏览器验证源是否同意允许此应用程序处理此类 URI，PWA 将匹配用于 URL 处理的 `url_handlers` URI。</span><span class="sxs-lookup"><span data-stu-id="b36f6-187">A PWA matches a URI for URL handling if the URI matches one of the origin strings in `url_handlers` and the browser validates that the origin agrees to allow this app handle such a URI.</span></span>  

<span data-ttu-id="b36f6-188">成员包含一个源，该源包含请求的 PWA 的范围和其他 `url_handlers` 不相关的源。</span><span class="sxs-lookup"><span data-stu-id="b36f6-188">The `url_handlers` member contains an origin that encompasses the scope and also other unrelated origins of the requesting PWA.</span></span>  <span data-ttu-id="b36f6-189">不将 URI 限制为与请求的 PWA 相同的范围或域，允许您对相同内容使用不同的域名，但使用相同的 PWA 处理它们。</span><span class="sxs-lookup"><span data-stu-id="b36f6-189">Not restricting URIs to the same scope or domain as the requesting PWA allows you to use different domain names for the same content but handle them with the same PWA.</span></span>  

#### <a name="wildcard-matching"></a><span data-ttu-id="b36f6-190">通配符匹配</span><span class="sxs-lookup"><span data-stu-id="b36f6-190">Wildcard matching</span></span>  

<span data-ttu-id="b36f6-191">使用通配符 \ (`*` \) 匹配一个或多个字符。</span><span class="sxs-lookup"><span data-stu-id="b36f6-191">Use the wildcard character \(`*`\) to match one or more characters.</span></span>  

<span data-ttu-id="b36f6-192">通配符前缀用于成员的来源字符串中 `url_handlers` ，以匹配不同的子域。</span><span class="sxs-lookup"><span data-stu-id="b36f6-192">A wildcard prefix is used in origin strings of the `url_handlers` member to match for different subdomains.</span></span>  <span data-ttu-id="b36f6-193">前缀必须针对 `*.` 此用法。</span><span class="sxs-lookup"><span data-stu-id="b36f6-193">The prefix must be `*.` for this usage.</span></span>  <span data-ttu-id="b36f6-194">使用 `https` 通配符前缀时将假定此方案。</span><span class="sxs-lookup"><span data-stu-id="b36f6-194">The `https` scheme is assumed when you use a wildcard prefix.</span></span>  

<span data-ttu-id="b36f6-195">例如， `url_handlers` 成员值设置为 `*.contoso.com` matches 和 `tenant.contoso.com` `www.tenant.contoso.com` ，但不匹配 `contoso.com` 。</span><span class="sxs-lookup"><span data-stu-id="b36f6-195">For example, the `url_handlers` member value is set to `*.contoso.com` matches `tenant.contoso.com` and `www.tenant.contoso.com`, but doesn't match `contoso.com`.</span></span>  

<!-- Hold for future release -->  
<!--  ## Window Controls Overlay for installed desktop web apps  

To create an immersive title bar similar to a native app for your desktop installed web app.  The **Window Controls Overlay** feature  completes the following actions.  
    
1.  Removes the system reserved title bar.  It usually spans the width of the client frame.  
1.  Replaces it with an overlay.  It contains just the critical system required window controls necessary for a user to control the window itself.  
    
After it provides an overlay, the entire web client area is available for you to use.  This feature includes a manifest update.  It provides ways for you to determine the size and position of the overlay to help you arrange content.  
    
### Examples of title bar area customization  

This feature is based on the ability in native apps to customize the title bar.  You may customize a title bar for important app actions or notifications.  Review the following examples for Microsoft Visual Studio Code and Microsoft Teams.  

#### Visual Studio Code  

Microsoft Visual Studio Code is a popular editor built on Electron that ships on multiple desktop platforms.  

The following example displays how Visual Studio Code uses the title bar to maximize available screen real estate to include the current file name and top-level menu structure in the title bar.  

:::image type="complex" source="../media/visual-studio-code-title-customization.png" alt-text="An example of the title bar in Visual Studio Code" lightbox="../media/visual-studio-code-title-customization.png":::
   An example of the title bar in Visual Studio Code  
:::image-end:::  

#### Microsoft Teams  

Workplace collaboration and communication tool Microsoft Teams is also built with Electron and available on multiple desktop platforms.  In the following example, Microsoft Teams displays `back` and `forward` navigation buttons, a search box, and user profile controls.  

:::image type="complex" source="../media/teams-title-customization.png" alt-text="An example of the title bar in Microsoft Teams" lightbox="../media/teams-title-customization.png":::
   An example of the title bar in Microsoft Teams  
:::image-end:::  

### Overlay Window Controls on a Frameless Window  

To provide the maximum addressable area for web content, the browser creates a frameless window, removing all browser UI except for the window controls provided as an overlay.  
The window controls overlay ensures users still minimize, maximize, restore, and close the app.  It also provides access to relevant browser controls using the web app menu.  For Chromium-based browsers, the controls in the overlay.

*   A draggable region the same width and height of each of the window control buttons  
*   The **Settings and more** \(...\) button  
*   The window control buttons minimize, maximize, restore, and close  
    
The following scenarios include when browser displays other content in the controls overlay.  

*   When an installed web app is launched, the origin of the webpage displays to the left of the **Settings and more** \(...\) menu for a few seconds and then disappears.  
*   If a user interacts with an extension using the **Settings and more** \(...\) menu, the icon of the extension displays in the overlay to the left of the three-dot menu.  After you exit any extension dialog, the icon is removed from the overlay.  
    
| Language direction | Overlay location | Details |  
|:--- |:--- |:--- |  
| Left-to-right \(LTR\) | Upper left of the client area | The controls are flipped |  
| Right-to-left \(RTL\) | Upper right corner of the client area |  |  

>[!IMPORTANT]
> The overlay is always on top of the Z-index of the web content and accepts all user input without flowing it through to the web content.  

### Working around the Window Controls Overlay  

Your web content must be aware of the reserved area for the controls overlay.  Ensure the reserved area doesn't expect user interaction.  Query the browser for the bounding rectangle and visibility of the controls overlay.  The information is provided to you through JavaScript APIs and CSS environment variables.  

#### JavaScript APIs  

A new `windowControlsOverlay` object on the `window.navigator` property allows you to query the bounding rectangle of the controls overlay.  

The `windowControlsOverlay` object has the following two objects.  

*   `getBoundingClientRect()` returns a `DOMRect` object.  The `DOMRect` object represents the area under the window controls overlay.  
*   `visible` is a boolean that indicates that the controls overlay is rendered and displayed.  
    
> [!IMPORTANT]
> For privacy reasons, the `windowControlsOverlay` isn't accessible to `iframe` elements in the web content.  

Whenever the overlay is resized, a `geometrychange` event runs on the `navigator.windowControlsOverlay` object to notify the client to recalculate the content layout.  The recalculated content layout is based on the new bounding rectangle of the overlay.  

#### CSS Environment Variables  

Besides the JavaScript API, you may use CSS to query the bounding rectangle of the controls overlay.  Use the following four new CSS environment variables to accomplish to query.  

*   `titlebar-area-x`  
*   `titlebar-area-y`  
*   `titlebar-area-width`  
*   `titlebar-area-height`  
    
### Define Draggable Regions in Web Content  

Users expect to grab and drag the upper region of a window.  To accommodate the expectation, declare specific parts of the web content as draggable.  
To specify an element is draggable, use the webkit proprietary `-webkit-app-region` CSS property.  The CSS working group continues efforts to standardize the `app-region` property.  

To preview this feature in Microsoft Edge for desktop OSs, navigate to [Turn on experimental features](#turn-on-experimental-features) and navigate to **Desktop PWA Window Controls Overlay**.   

### Custom title bar example  

The following example displays how the new features create a web app with a custom title bar.  

:::image type="complex" source="../media/teams-title-customization-example.png" alt-text="Example of a custom title bar in Microsoft Teams" lightbox="../media/teams-title-customization-example.png":::
   Example of a custom title bar in Microsoft Teams  
:::image-end:::  

#### manifest.webmanifest  

In the manifest, set `display_override` array to  `window-controls-overlay`.  Set the `theme_color` to your choice of color for the title bar.  Set the display mode to an appropriate fallback for when either `display_override` or `window-controls-overlay` isn't supported.  

The following code snippet includes the recommended manifest updates.  

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

### index.html  

The following IDs represent the two main regions of the webpage.  

*   `titleBarContainer`  
*   `mainContent`  
    
The `div` element with the `titleBar` ID is set to `draggable` and the search box `input` child element is set to `nonDraggable`.  

```html
<div id="titleBar" class=" draggable">
    <span class="draggable">Example PWA</span>
    <input class="nonDraggable" type="text" placeholder="Search"></input>
</div>
```

In the `div` element with the `titleBarContainer` ID, the `div` with the `titleBar` ID represents the visible portion of the title bar area.  

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
    <div id="mainContent">The rest of the webpage</div>
  </body>
</html>
```  

### style.css  

The draggable and non-draggable regions are set using `-webkit-app-region: drag` and `-webkit-app-region: no-drag`.  

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

For the `body` element, margins are set to `0` to ensure the title bar reaches to the edges of the window.  

```css
body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    margin: 0;
}
```  

The `titleBarContainer` ID uses `position: absolute` and sets the `top` to `titlebar-area-inset-top`, which attaches the container to the top of the webpage.  The `bottom` is set to `titlebar-area-inset-bottom` and falls back to `100% - var(--fallback-title-bar-height)` if the window controls overlay isn't visible.  The background color of the `titleBarContainer` ID is the same as the `theme_color`.  The width is set to `100%`, so that the `div` element fills the width of the webpage and flows under the overlay when it's visible for a contiguous appearance.  

```css
#titleBarContainer {
    position: absolute;
    top: env(titlebar-area-y, 0);
    bottom: env(titlebar-area-height, calc(100% - var(--fallback-title-bar-height)));
    width: 100%;
    background-color:#254B85;
}
```  

The `titleBar` ID also uses `position: absolute` and `top: titlebar-area-inset-top` to attaches it to the top of the window.  By default, it consumes the full width of the window.  The `left` and `right` edges are set to `titlebar-area-inset-left` and `titlebar-area-inset-right` respectively, both fall back to `0` when the values aren't set.  It also sets `user-select: none` to prevent any attempts to drag the window consumed instead it highlights text in the `div` element.  

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

The container for the `mainContent` ID is also fixed in place with `position: absolute` and is attached to the bottom of the webpage.  The `height` is set to `titlebar-area-inset-bottom` and falls back to `100% - var(--fallback-titlebar-height)` to fill the remaining space below the title bar.  It sets `overflow-y: scroll` to allow the contents to scroll vertically in the container.  

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

For cases where the browser doesn't support the window controls overlay, a CSS variable is added to set a default height for the title bar.  The bounds of the `titleBarContainer` and `mainContent` IDs are initially set to fill the entire client area, and you don't need to change it if the overlay isn't supported.  

The following code snippet includes all of the recommended css updates.

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
-->  

## <a name="run-on-os-login"></a><span data-ttu-id="b36f6-196">在操作系统登录时运行</span><span class="sxs-lookup"><span data-stu-id="b36f6-196">Run On OS Login</span></span>  

<span data-ttu-id="b36f6-197">此功能允许你将应用配置为在用户登录 Microsoft Windows 时自动启动。</span><span class="sxs-lookup"><span data-stu-id="b36f6-197">This feature allows you to configure your app to automatically launch when the user logs into Microsoft Windows.</span></span>  <span data-ttu-id="b36f6-198">多个应用类利用此功能。</span><span class="sxs-lookup"><span data-stu-id="b36f6-198">Several classes of apps take advantage of the capability.</span></span>  <span data-ttu-id="b36f6-199">应用类包括电子邮件、聊天、监视仪表板和实时数据显示应用。</span><span class="sxs-lookup"><span data-stu-id="b36f6-199">The classes of apps include email, chat, monitoring dashboard, and real-time data display apps.</span></span>  <span data-ttu-id="b36f6-200">该功能允许用户在用户登录到操作系统后尽快使用应用。</span><span class="sxs-lookup"><span data-stu-id="b36f6-200">The capability allows a user to engage with the apps as soon as the user logs into the OS.</span></span>  <span data-ttu-id="b36f6-201">此功能自动启动 PWA 的方式与手动启动 PWA 的方式相同。</span><span class="sxs-lookup"><span data-stu-id="b36f6-201">This feature automatically starts the PWA the same way it's launched manually.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="b36f6-202">**在操作系统登录上运行** 是一 [项强大的功能][GithubW3cPermissionsPowerfulFeature]。</span><span class="sxs-lookup"><span data-stu-id="b36f6-202">**Run on OS Login** is a [powerful feature][GithubW3cPermissionsPowerfulFeature].</span></span>  <span data-ttu-id="b36f6-203">用户应决定是否为已安装的 Web 应用启用该功能。</span><span class="sxs-lookup"><span data-stu-id="b36f6-203">Users should decide whether to turn on the capability for the installed web app.</span></span>  

### <a name="turn-on-run-on-os-login"></a><span data-ttu-id="b36f6-204">打开"在操作系统登录时运行"</span><span class="sxs-lookup"><span data-stu-id="b36f6-204">Turn on Run On OS Login</span></span>  

<span data-ttu-id="b36f6-205">若要为 PWA 启用 **"在操作系统**登录时运行"功能，[](#turn-on-experimental-features)请导航到"打开实验性功能"，然后打开"在操作系统登录时**运行桌面 PWA"。**</span><span class="sxs-lookup"><span data-stu-id="b36f6-205">To turn on **Run On OS Login** capabilities for your PWA, navigate to [Turn on experimental features](#turn-on-experimental-features) and turn on **Desktop PWAs run on OS login**.</span></span>  

:::image type="complex" source="../media/desktop-pwas-run-on-os-login-flag.png" alt-text="打开在操作系统登录实验上运行的桌面 PBA" lightbox="../media/desktop-pwas-run-on-os-login-flag.png":::
   <span data-ttu-id="b36f6-207">打开在**操作系统登录实验上运行的桌面 PBA**</span><span class="sxs-lookup"><span data-stu-id="b36f6-207">Turn on the **Desktop PWAs run on OS login** experiment</span></span>  
:::image-end:::  

### <a name="turn-on-the-feature-for-the-installed-web-app"></a><span data-ttu-id="b36f6-208">打开已安装的 Web 应用的功能</span><span class="sxs-lookup"><span data-stu-id="b36f6-208">Turn on the feature for the installed web app</span></span>  

<span data-ttu-id="b36f6-209">若要为已安装 `Start app when you sign in` 的 PWA 启用该功能，</span><span class="sxs-lookup"><span data-stu-id="b36f6-209">To turn on the `Start app when you sign in` feature for an installed PWA,</span></span> 

1.  <span data-ttu-id="b36f6-210">打开 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="b36f6-210">Open Microsoft Edge.</span></span>   
1.  <span data-ttu-id="b36f6-211">导航到 `edge://apps` 。</span><span class="sxs-lookup"><span data-stu-id="b36f6-211">Navigate to `edge://apps`.</span></span>  
1.  <span data-ttu-id="b36f6-212">将鼠标悬停在你的应用上。</span><span class="sxs-lookup"><span data-stu-id="b36f6-212">Hover on your app.</span></span>  
1.  <span data-ttu-id="b36f6-213">打开上下文菜单 \ (右键单击\) 然后在登录时选择 **"启动应用"。**</span><span class="sxs-lookup"><span data-stu-id="b36f6-213">Open the contextual menu \(right-click\) and then choose **Start app when you sign in**.</span></span>  
    
    :::image type="complex" source="../media/turn-on-run-on-os-login-flag.png" alt-text="在 Microsoft Edge 中登录功能时，使用上下文菜单打开"开始"应用" lightbox="../media/turn-on-run-on-os-login-flag.png":::
       <span data-ttu-id="b36f6-215">在 Microsoft Edge 中登录功能时 **，** 使用上下文菜单打开"开始"应用</span><span class="sxs-lookup"><span data-stu-id="b36f6-215">Use the contextual menu to turn on the **Start app when you sign in** feature in Microsoft Edge</span></span>  
    :::image-end:::  
    
## <a name="shortcuts"></a><span data-ttu-id="b36f6-216">快捷方式</span><span class="sxs-lookup"><span data-stu-id="b36f6-216">Shortcuts</span></span>  

`Shortcuts` <span data-ttu-id="b36f6-217">是清单文件的一个新增成员。</span><span class="sxs-lookup"><span data-stu-id="b36f6-217">is a new member of the manifest file.</span></span>  <span data-ttu-id="b36f6-218">它允许你在 Web 应用中定义指向部件、关键网页或操作的链接。</span><span class="sxs-lookup"><span data-stu-id="b36f6-218">It allows you to define links to parts, key webpages, or actions in your web app.</span></span>  <span data-ttu-id="b36f6-219">Microsoft Windows 将其集成为 **Jumplists**。</span><span class="sxs-lookup"><span data-stu-id="b36f6-219">Microsoft Windows integrates it as **Jumplists**.</span></span>  <span data-ttu-id="b36f6-220">**Jumplist 定义** 在下列 UI 元素之一上打开上下文菜单 \ (右键单击\) 时出现的弹出菜单。</span><span class="sxs-lookup"><span data-stu-id="b36f6-220">**Jumplists** define popup menus that appear when you on one of the following UI elements and open a contextual menu \(right-click\).</span></span>  

*   <span data-ttu-id="b36f6-221">"开始"菜单上的磁贴</span><span class="sxs-lookup"><span data-stu-id="b36f6-221">A tile on the Start Menu</span></span>  
*   <span data-ttu-id="b36f6-222">任务栏上的图标</span><span class="sxs-lookup"><span data-stu-id="b36f6-222">An icon on the Taskbar</span></span>  
    
<span data-ttu-id="b36f6-223">当用户调用快捷方式时，用户将导航到该快捷方式的成员 `url` 指定的地址。</span><span class="sxs-lookup"><span data-stu-id="b36f6-223">When a user invokes a shortcut, the user navigates to the address specified by the `url` member of the shortcut.</span></span>  
  
:::image type="complex" source="../media/jumplists-on-windows-10.png" alt-text="Windows 10 上的 Jumplist 示例" lightbox="../media/jumplists-on-windows-10.png":::
   <span data-ttu-id="b36f6-225">Windows 10 **上的 Jumplist** 示例</span><span class="sxs-lookup"><span data-stu-id="b36f6-225">An example of **Jumplists** on Windows 10</span></span>  
:::image-end:::  

### <a name="shortcuts-in-the-manifest-file"></a><span data-ttu-id="b36f6-226">清单文件的快捷方式</span><span class="sxs-lookup"><span data-stu-id="b36f6-226">Shortcuts in the Manifest file</span></span>  

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

#### <a name="properties-of-shortcuts"></a><span data-ttu-id="b36f6-227">快捷方式的属性</span><span class="sxs-lookup"><span data-stu-id="b36f6-227">Properties of shortcuts</span></span>  

<span data-ttu-id="b36f6-228">以下属性定义每个快捷方式。</span><span class="sxs-lookup"><span data-stu-id="b36f6-228">The following properties define each shortcut.</span></span>  

| <span data-ttu-id="b36f6-229">属性</span><span class="sxs-lookup"><span data-stu-id="b36f6-229">Property</span></span> | <span data-ttu-id="b36f6-230">详细信息</span><span class="sxs-lookup"><span data-stu-id="b36f6-230">Details</span></span> |  
|:--- |:--- |  
| `name` | <span data-ttu-id="b36f6-231">在跳转列表或上下文 **菜单上向** 用户显示的字符串。</span><span class="sxs-lookup"><span data-stu-id="b36f6-231">A string that is displayed to the user on **Jumplists** or the contextual menu.</span></span> |  
| `short_name` | <span data-ttu-id="b36f6-232">当空间不足，无法显示快捷方式的完整名称时显示的字符串。</span><span class="sxs-lookup"><span data-stu-id="b36f6-232">A string that is displayed when insufficient space exists to display the full name of the shortcut.</span></span> |  
| `description` | <span data-ttu-id="b36f6-233">一个描述快捷方式用途的字符串。</span><span class="sxs-lookup"><span data-stu-id="b36f6-233">A string that describes the purpose of the shortcut.</span></span>  <span data-ttu-id="b36f6-234">它可能会由辅助技术访问。</span><span class="sxs-lookup"><span data-stu-id="b36f6-234">It may be accessed by assistive technology.</span></span> |  
| `url` | <span data-ttu-id="b36f6-235">激活快捷方式时打开的 Web 应用中的 URI。</span><span class="sxs-lookup"><span data-stu-id="b36f6-235">The URI in the web app that opens when the shortcut is activated.</span></span> |  
| `icons` | <span data-ttu-id="b36f6-236">一组表示快捷方式的图标。</span><span class="sxs-lookup"><span data-stu-id="b36f6-236">A set of icons that represents the shortcut.</span></span> |  

## <a name="file-handling"></a><span data-ttu-id="b36f6-237">文件处理</span><span class="sxs-lookup"><span data-stu-id="b36f6-237">File Handling</span></span>  

<span data-ttu-id="b36f6-238">注册为文件类型处理程序的能力在试验阶段。</span><span class="sxs-lookup"><span data-stu-id="b36f6-238">The ability to register as a file type handler is in the experimentation phase.</span></span>  <span data-ttu-id="b36f6-239">你可以指定应用在清单条目中处理的文件类型。</span><span class="sxs-lookup"><span data-stu-id="b36f6-239">You may specify the file types that your app handles in a manifest entry.</span></span>  <span data-ttu-id="b36f6-240">在安装过程中，用户的主机操作系统将你的应用注册为列出的文件类型的文件处理程序。</span><span class="sxs-lookup"><span data-stu-id="b36f6-240">During installation, the user's host OS registers your app as a file handler for the listed file types.</span></span>  <span data-ttu-id="b36f6-241">确保应用启动代码中存在此功能， `launchQueue` 并确保它处理文件。</span><span class="sxs-lookup"><span data-stu-id="b36f6-241">Ensure the existence of the feature `launchQueue` in your apps startup code and that it handles the file.</span></span>  

<span data-ttu-id="b36f6-242">基于 Chromium 的浏览器正在测试和塑造此功能。</span><span class="sxs-lookup"><span data-stu-id="b36f6-242">Chromium-based browsers are testing and shaping this feature.</span></span>  <span data-ttu-id="b36f6-243">有关详细信息（包括代码示例），请导航到["允许 Web 应用程序成为文件处理程序"。][WebDevFileHandling]</span><span class="sxs-lookup"><span data-stu-id="b36f6-243">For more information including code examples, navigate to [Let web applications be file handlers][WebDevFileHandling].</span></span>  

<span data-ttu-id="b36f6-244">若要预览适用于桌面 OS 的 Microsoft Edge 中的文件处理，请导航到打开实验[性](#turn-on-experimental-features)功能，然后打开文件**处理 API。**</span><span class="sxs-lookup"><span data-stu-id="b36f6-244">To preview file handling in Microsoft Edge for desktop OSs, navigate to [Turn on experimental features](#turn-on-experimental-features) and turn on **File Handling API**.</span></span>  
    
## <a name="providing-feedback-on-experimental-features"></a><span data-ttu-id="b36f6-245">提供有关试验功能的反馈</span><span class="sxs-lookup"><span data-stu-id="b36f6-245">Providing feedback on experimental features</span></span>  

<span data-ttu-id="b36f6-246">提供有关 Microsoft Edge Web 应用实验的反馈。</span><span class="sxs-lookup"><span data-stu-id="b36f6-246">To provide feedback on Microsoft Edge web app experiments.</span></span>  

*   <span data-ttu-id="b36f6-247">使用 **设置和更多** \ (`...` \) > 将反馈发送到 Microsoft **发送反馈**。</span><span class="sxs-lookup"><span data-stu-id="b36f6-247">Send your feedback using **Settings and More** \(`...`\) > **Send Feedback to Microsoft**.</span></span>  
*   <span data-ttu-id="b36f6-248">选择 `Alt` + `Shift` + `I` 。</span><span class="sxs-lookup"><span data-stu-id="b36f6-248">Select `Alt`+`Shift`+`I`.</span></span>  
    
:::image type="complex" source="../media/send-feedback-from-progressive-web-app.png" alt-text="从 PWA 发送反馈" lightbox="../media/send-feedback-from-progressive-web-app.png":::
   <span data-ttu-id="b36f6-250">从 PWA 发送反馈</span><span class="sxs-lookup"><span data-stu-id="b36f6-250">Send Feedback from your PWA</span></span>  
:::image-end:::  

<!-- links -->  

[MicrosoftEdgeMain]: https://www.microsoft.com/edge "Microsoft Edge"  

[MicrosoftDeveloperMicrosoftEdgeOriginTrials]: https://developer.microsoft.com/microsoft-edge/origin-trials "源试用版|Microsoft Edge 开发人员"  
[MicrosoftDeveloperMicrosoftEdgeOriginTrialsWebAppProtocolHandlerRegistrationRegistration]: https://developer.microsoft.com/microsoft-edge/origin-trials/web-app-protocol-handler-registration/registration "注册 Web 应用协议处理程序|Microsoft 开发人员"  

[MdnDocsWebApiNavigatorRegisterprotocolhandlerWebBasedProtocolHandlers]: https://developer.mozilla.org/docs/Web/API/Navigator/registerProtocolHandler/Web-based_protocol_handlers "基于 Web 的协议处理程序|MDN"  

[GithubW3cPermissionsPowerfulFeature]: https://w3c.github.io/permissions#powerful-feature "强大的功能 - 权限|GitHub"  

[GithubWicgPwaUrlHandlerBlobMainExplainerMd]: https://github.com/WICG/pwa-url-handler/blob/main/explainer.md "作为 URL 处理程序的 PWA |GitHub"  

[WebDevFileHandling]: https://web.dev/file-handling "让 Web 应用程序成为文件处理程序|web.dev"  
