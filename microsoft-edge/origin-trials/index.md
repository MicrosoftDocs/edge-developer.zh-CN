---
ms.assetid: ''
description: 在固定时段内安全地进行试验，并提供有关新平台功能的反馈。
title: 原始试验
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: edge， web development， html， css， origin trials， developer
ms.openlocfilehash: cc03ec556d4b32ca37cebcd4ee7ba155bfe4404b
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11397543"
---
# <a name="use-origin-trials-in-microsoft-edge"></a><span data-ttu-id="c709e-104">使用 Microsoft Edge 中的源试用版</span><span class="sxs-lookup"><span data-stu-id="c709e-104">Use Origin Trials in Microsoft Edge</span></span>  

<span data-ttu-id="c709e-105">开发人员可以使用源试用版在有限时段内在活动网站上试用实验性 API。</span><span class="sxs-lookup"><span data-stu-id="c709e-105">Developers may use Origin Trials to try out experimental APIs on live sites for a limited period of time.</span></span>  <span data-ttu-id="c709e-106">使用源试用版时，访问站点的 Microsoft Edge 用户可能会运行使用实验性 API 的代码。</span><span class="sxs-lookup"><span data-stu-id="c709e-106">When using Origin Trials, users of Microsoft Edge that visit your site may run code that uses experimental APIs.</span></span>  <span data-ttu-id="c709e-107">若要访问每个用户计算机上实验性 API，你无需转到 并 `edge://flags` 打开功能标志。</span><span class="sxs-lookup"><span data-stu-id="c709e-107">To access the experimental APIs on each user machine, you do not need to go to `edge://flags` and turn on feature flags.</span></span>  <span data-ttu-id="c709e-108">有关详细信息，请导航到 [实验性 API][DeveloperMicrsoftEdgeOriginTrials]。</span><span class="sxs-lookup"><span data-stu-id="c709e-108">For more information, navigate to [experimental APIs][DeveloperMicrsoftEdgeOriginTrials].</span></span>  <span data-ttu-id="c709e-109">此外，你可以向浏览器工程师和 Web 标准社区提供有关 API 设计、用例或使用 API 的体验的反馈。</span><span class="sxs-lookup"><span data-stu-id="c709e-109">Additionally, you may provide feedback on the design of the API, your use cases, or your experience using the APIs to browser engineers and the web standard community.</span></span>  

## <a name="get-started-using-origin-trials"></a><span data-ttu-id="c709e-110">源试用版使用入门</span><span class="sxs-lookup"><span data-stu-id="c709e-110">Get started using Origin Trials</span></span>  

<span data-ttu-id="c709e-111">有关 Microsoft Edge 中提供的实验性 API 详细信息，请导航到 [Microsoft Edge Origin Trials 开发人员控制台][DeveloperMicrsoftEdgeOriginTrials]。</span><span class="sxs-lookup"><span data-stu-id="c709e-111">For more information about the experimental APIs available in Microsoft Edge, navigate to [Microsoft Edge Origin Trials Developer Console][DeveloperMicrsoftEdgeOriginTrials].</span></span>  <span data-ttu-id="c709e-112">确保查看 Microsoft Edge 的最低版本要求，以及评估在网站上使用实验性 API 的适用性的试用结束日期。</span><span class="sxs-lookup"><span data-stu-id="c709e-112">Ensure that you review the minimum version requirements for Microsoft Edge, and the trial end date to assess suitability of using the experimental APIs on your website.</span></span>  

> [!NOTE]
> <span data-ttu-id="c709e-113">如果发生以下任一情况，实验可能会早于计划结束。</span><span class="sxs-lookup"><span data-stu-id="c709e-113">An experiment may end earlier than planned if any of the following situations occur.</span></span>  
> *   <span data-ttu-id="c709e-114">重大安全事件。</span><span class="sxs-lookup"><span data-stu-id="c709e-114">A major security incident.</span></span>  
> *   <span data-ttu-id="c709e-115">如果收集的充分反馈表明需要进行重大重新设计以满足 Web 开发人员的需求。</span><span class="sxs-lookup"><span data-stu-id="c709e-115">If sufficient feedback is collected that indicates a major redesign is needed to meet the needs of web developers.</span></span>  
> <span data-ttu-id="c709e-116">无论哪种情况，都向当前在实验中注册的所有开发人员发送通知电子邮件。</span><span class="sxs-lookup"><span data-stu-id="c709e-116">In either case, a notification email is sent to all developers currently enrolled in the experiment.</span></span>  

### <a name="register-for-a-trial-of-an-experimental-api"></a><span data-ttu-id="c709e-117">注册实验性 API 的试用版</span><span class="sxs-lookup"><span data-stu-id="c709e-117">Register for a trial of an experimental API</span></span>  

<span data-ttu-id="c709e-118">使用以下步骤注册实验性 API 的试用版。</span><span class="sxs-lookup"><span data-stu-id="c709e-118">Use the following steps to register for a trial of an experimental API.</span></span>  

1.  <span data-ttu-id="c709e-119">访问 [Microsoft Edge Origin Trials 开发人员控制台][DeveloperMicrsoftEdgeOriginTrials] 页面。</span><span class="sxs-lookup"><span data-stu-id="c709e-119">Visit the [Microsoft Edge Origin Trials Developer Console][DeveloperMicrsoftEdgeOriginTrials] page.</span></span>  
1.  <span data-ttu-id="c709e-120">在任何可用实验上选择"注册"按钮。</span><span class="sxs-lookup"><span data-stu-id="c709e-120">Choose the Register button on any of the available experiments.</span></span>  
1.  <span data-ttu-id="c709e-121">使用 GitHub 用户名和密码登录开发人员控制台。</span><span class="sxs-lookup"><span data-stu-id="c709e-121">Sign into the Developer Console using your GitHub username and password.</span></span>  
1.  <span data-ttu-id="c709e-122">选择 **"授权 MicrosoftEdge"。**</span><span class="sxs-lookup"><span data-stu-id="c709e-122">Choose **Authorize MicrosoftEdge**.</span></span>  
1.  <span data-ttu-id="c709e-123">填写表单。</span><span class="sxs-lookup"><span data-stu-id="c709e-123">Complete the form.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="c709e-124">若要注册单个或所有子域，请选择将 `Do you need to match all subdomains for the provided origin?` 设置设置为 `Yes` 。</span><span class="sxs-lookup"><span data-stu-id="c709e-124">To enroll a single or all subdomains, choose set the `Do you need to match all subdomains for the provided origin?` setting to `Yes`.</span></span>  <span data-ttu-id="c709e-125">例如， `https://dev.contoso.com` 是单个域， `https://*.contoso.com` 并使用通配符表示所有子域。</span><span class="sxs-lookup"><span data-stu-id="c709e-125">For example, `https://dev.contoso.com` is a single domain, and `https://*.contoso.com` uses a wildcard to represent all subdomains.</span></span>  
    
    > [!IMPORTANT]
    > <span data-ttu-id="c709e-126">不允许使用下列原点格式。</span><span class="sxs-lookup"><span data-stu-id="c709e-126">The following origin formats are not allowed.</span></span>  
    > *   <span data-ttu-id="c709e-127">指定源上的子文件夹。</span><span class="sxs-lookup"><span data-stu-id="c709e-127">Specifying a subfolder on the origin.</span></span>  <span data-ttu-id="c709e-128">例如，</span><span class="sxs-lookup"><span data-stu-id="c709e-128">For example,</span></span> `https://contoso.com/path/subfolder`  
    > 
    > *   <span data-ttu-id="c709e-129">将源与查询字符串参数一同使用。</span><span class="sxs-lookup"><span data-stu-id="c709e-129">Using an origin with query string parameters.</span></span>  <span data-ttu-id="c709e-130">例如，</span><span class="sxs-lookup"><span data-stu-id="c709e-130">For example,</span></span> `https://contoso.com/path/feature?query_parameter=12345`  
    
1.  <span data-ttu-id="c709e-131">选择 **接受并注册**。</span><span class="sxs-lookup"><span data-stu-id="c709e-131">Choose **ACCEPT and REGISTER**.</span></span>  
    
### <a name="apply-your-token"></a><span data-ttu-id="c709e-132">应用令牌</span><span class="sxs-lookup"><span data-stu-id="c709e-132">Apply your token</span></span>  

<span data-ttu-id="c709e-133">将立即生成令牌，并显示在 Microsoft [Edge Origin Trials 开发人员控制台][DeveloperMicrsoftEdgeOriginTrials] 页面上。</span><span class="sxs-lookup"><span data-stu-id="c709e-133">A token is instantly generated and displayed on the [Microsoft Edge Origin Trials Developer Console][DeveloperMicrsoftEdgeOriginTrials] page.</span></span>  <span data-ttu-id="c709e-134">若要开始在网站上使用试用版，请使用以下任一方法将令牌应用到你的页面。</span><span class="sxs-lookup"><span data-stu-id="c709e-134">To begin using the trial on your website, use either of the following methods to apply the token to your page.</span></span>  

*   <span data-ttu-id="c709e-135">将属性值和令牌添加到使用实验性 API 的每一页上 `origin-trial` `meta` 的 标记。</span><span class="sxs-lookup"><span data-stu-id="c709e-135">Add the `origin-trial` attribute value and your token to the `meta` tag on every page that uses the experimental API.</span></span>  
    
    ```html
    <meta http-equiv="origin-trial" content="replace-with-your-token">
    ```  
    
*   <span data-ttu-id="c709e-136">添加到 `Origin-Trial` 服务器的 HTTP 响应标头。</span><span class="sxs-lookup"><span data-stu-id="c709e-136">Add `Origin-Trial` to the HTTP response header of your server.</span></span>  
    
    ```json
    Origin-Trial: replace-with-your-token
    ```  
    
> [!NOTE]
> <span data-ttu-id="c709e-137">你的令牌有效期为 6 周。</span><span class="sxs-lookup"><span data-stu-id="c709e-137">Your token is valid for 6 weeks.</span></span>  <span data-ttu-id="c709e-138">在试用结束之前，会向用户发送提醒电子邮件，请求你提供反馈，并请求你考虑在令牌过期前续订试用版。</span><span class="sxs-lookup"><span data-stu-id="c709e-138">Before your trial ends, reminder emails are sent to you that ask for your feedback and ask you to consider renewing your trial before your token expires.</span></span>  

### <a name="opt-out-of-an-experiment"></a><span data-ttu-id="c709e-139">选择退出实验</span><span class="sxs-lookup"><span data-stu-id="c709e-139">Opt out of an experiment</span></span>  

<span data-ttu-id="c709e-140">若要选择退出实验，请使用以下方法之一删除令牌。</span><span class="sxs-lookup"><span data-stu-id="c709e-140">To opt out of an experiment, use one of the following methods to remove your token.</span></span>  

*   <span data-ttu-id="c709e-141">从 `meta` 使用实验性 API 的每一页中删除 标记。</span><span class="sxs-lookup"><span data-stu-id="c709e-141">Remove the `meta` tag from every page that used the experimental API.</span></span>  
    
    ```html
    <meta http-equiv="origin-trial" content="your-token">
    ```  
    
*   <span data-ttu-id="c709e-142">从 `Origin-Trial` 服务器的 HTTP 响应标头中删除。</span><span class="sxs-lookup"><span data-stu-id="c709e-142">Remove `Origin-Trial` from the HTTP response header of your server.</span></span>  
    
    ```json
    Origin-Trial: your-token
    ```  
    
### <a name="detect-experimental-features-and-provide-a-fallback"></a><span data-ttu-id="c709e-143">检测实验性功能并提供回退</span><span class="sxs-lookup"><span data-stu-id="c709e-143">Detect experimental features and provide a fallback</span></span>  

<span data-ttu-id="c709e-144">使用实验性 API 时，请确保为网站的所有访问者提供工作体验。</span><span class="sxs-lookup"><span data-stu-id="c709e-144">When using experimental APIs, ensure you provide a working experience to all visitors of your website.</span></span>  <span data-ttu-id="c709e-145">访问者可能会使用不支持您添加到代码中的实验性 API 的浏览器。</span><span class="sxs-lookup"><span data-stu-id="c709e-145">Visitors may use browsers that do not support the experimental APIs that you added to your code.</span></span>  <span data-ttu-id="c709e-146">此外，如果你的令牌在续订之前过期，实验性 API 将不再可用，这可能会导致错误。</span><span class="sxs-lookup"><span data-stu-id="c709e-146">Additionally, if your token expires before you renew it, the experimental API is no longer available which may result in errors.</span></span>  <span data-ttu-id="c709e-147">若要避免这种情况，请确保检测到浏览器中可用的功能。</span><span class="sxs-lookup"><span data-stu-id="c709e-147">To avoid this situation, ensure you detect features available in your browser.</span></span>  <span data-ttu-id="c709e-148">有关详细信息，请导航到["实现功能检测"。][MDNImplementingFeatureDetection]</span><span class="sxs-lookup"><span data-stu-id="c709e-148">For more information, navigate to [Implementing feature detection][MDNImplementingFeatureDetection].</span></span>

### <a name="roadmap-for-allowed-origins"></a><span data-ttu-id="c709e-149">允许的来源路线图</span><span class="sxs-lookup"><span data-stu-id="c709e-149">Roadmap for Allowed Origins</span></span>  

<span data-ttu-id="c709e-150">Microsoft Edge Origin Trials 门户现在仅支持启用 SSL 的源，这意味着网站必须正确实现 HTTPS 才能注册实验。</span><span class="sxs-lookup"><span data-stu-id="c709e-150">The Microsoft Edge Origin Trials portal today only supports SSL Enabled Origins, which means that websites must have HTTPS properly implemented to register for an experiment.</span></span>  <span data-ttu-id="c709e-151">将来，将规划以下安全源。</span><span class="sxs-lookup"><span data-stu-id="c709e-151">In the future, the following secure origins are planned.</span></span>  

*   <span data-ttu-id="c709e-152">注册 `http://localhost` 为实验的原点。</span><span class="sxs-lookup"><span data-stu-id="c709e-152">Register `http://localhost` as the origin for your experiments.</span></span>  <span data-ttu-id="c709e-153">若要使用 `http://localhost` 今天，请导航 `edge://flags` 到 ，将实验设置为 **已启用**。</span><span class="sxs-lookup"><span data-stu-id="c709e-153">To use `http://localhost` today, navigate to `edge://flags` and set the experiment to **Enabled**.</span></span>  
*   <span data-ttu-id="c709e-154">使用具有前缀 `extensions://` 来源的扩展注册实验。</span><span class="sxs-lookup"><span data-stu-id="c709e-154">Use extensions with `extensions://` prefixed origins to enroll in experiments.</span></span>  
    
<!-- links -->  

[DeveloperMicrsoftEdgeOriginTrials]: https://developer.microsoft.com/microsoft-edge/origin-trials "Microsoft Edge 源试用版开发人员控制台|Microsoft Docs"  

[MDNImplementingFeatureDetection]: https://developer.mozilla.org/docs/learn/tools_and_testing/cross_browser_testing/feature_detection "实现功能检测|MDN"  
