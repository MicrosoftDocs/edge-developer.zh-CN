---
ms.assetid: ''
description: 安全实验一段固定的时间，并提供有关新平台功能的反馈。
title: 原始试用版
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/29/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘、web 开发、html、css、原创试验、开发人员
ms.openlocfilehash: 470896435ab348419749a7de00adcdb83b784df3
ms.sourcegitcommit: 5cbc9237363b3a8ba212ca128aa03c71a33ec86f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2020
ms.locfileid: "10846524"
---
# <span data-ttu-id="7a1e9-104">在 Microsoft Edge 中使用原创试验</span><span class="sxs-lookup"><span data-stu-id="7a1e9-104">Use Origin Trials in Microsoft Edge</span></span>  

<span data-ttu-id="7a1e9-105">在有限的时间段内，开发人员可以使用初始试验在活动网站上试用实验性 Api。</span><span class="sxs-lookup"><span data-stu-id="7a1e9-105">Developers may use Origin Trials to try out experimental APIs on live sites for a limited period of time.</span></span>  <span data-ttu-id="7a1e9-106">使用原始试验时，访问你的网站的 Microsoft Edge 用户可能会运行使用实验性 Api 的代码。</span><span class="sxs-lookup"><span data-stu-id="7a1e9-106">When using Origin Trials, users of Microsoft Edge that visit your site may run code that uses experimental APIs.</span></span>  <span data-ttu-id="7a1e9-107">若要访问每台用户计算机上的实验性 Api，无需转到 `edge://flags` 并打开功能标志。</span><span class="sxs-lookup"><span data-stu-id="7a1e9-107">To access the experimental APIs on each user machine, you do not need to go to `edge://flags` and turn on feature flags.</span></span>  <span data-ttu-id="7a1e9-108">有关详细信息，请参阅[实验性 api][DeveloperMicrsoftEdgeOriginTrials]。</span><span class="sxs-lookup"><span data-stu-id="7a1e9-108">For more information, see [experimental APIs][DeveloperMicrsoftEdgeOriginTrials].</span></span>  <span data-ttu-id="7a1e9-109">此外，你还可以提供有关 API 设计、使用情况或你使用 Api 到浏览器工程师和 web 标准社区的体验的反馈。</span><span class="sxs-lookup"><span data-stu-id="7a1e9-109">Additionally, you may provide feedback on the design of the API, your use cases, or your experience using the APIs to browser engineers and the web standard community.</span></span>  

## <span data-ttu-id="7a1e9-110">开始使用初始试用版</span><span class="sxs-lookup"><span data-stu-id="7a1e9-110">Get started using Origin Trials</span></span>  

<span data-ttu-id="7a1e9-111">有关 Microsoft Edge 中可用的实验性 Api 的详细信息，请参阅[Microsoft Edge 原始试用开发人员控制台][DeveloperMicrsoftEdgeOriginTrials]。</span><span class="sxs-lookup"><span data-stu-id="7a1e9-111">For more information about the experimental APIs available in Microsoft Edge, see [Microsoft Edge Origin Trials Developer Console][DeveloperMicrsoftEdgeOriginTrials].</span></span>  <span data-ttu-id="7a1e9-112">确保查看 Microsoft Edge 的最低版本要求和试用结束日期，以评估在你的网站上使用实验性 Api 的适用性。</span><span class="sxs-lookup"><span data-stu-id="7a1e9-112">Ensure that you review the minimum version requirements for Microsoft Edge, and the trial end date to assess suitability of using the experimental APIs on your website.</span></span>  

> [!NOTE]
> <span data-ttu-id="7a1e9-113">如果出现以下情况，则实验可能比计划提前结束。</span><span class="sxs-lookup"><span data-stu-id="7a1e9-113">An experiment may end earlier than planned if any of the following situations occur.</span></span>  
> *   <span data-ttu-id="7a1e9-114">重大安全事件。</span><span class="sxs-lookup"><span data-stu-id="7a1e9-114">A major security incident.</span></span>  
> *   <span data-ttu-id="7a1e9-115">如果收集了足够的反馈表明需要进行重大重新设计以满足 web 开发人员的需求。</span><span class="sxs-lookup"><span data-stu-id="7a1e9-115">If sufficient feedback is collected that indicates a major redesign is needed to meet the needs of web developers.</span></span>  
> <span data-ttu-id="7a1e9-116">在任何一种情况下，通知电子邮件都将发送给当前注册了实验的所有开发人员。</span><span class="sxs-lookup"><span data-stu-id="7a1e9-116">In either case, a notification email is sent to all developers currently enrolled in the experiment.</span></span>  

### <span data-ttu-id="7a1e9-117">注册实验性 API 的试用版</span><span class="sxs-lookup"><span data-stu-id="7a1e9-117">Register for a trial of an experimental API</span></span>  

<span data-ttu-id="7a1e9-118">使用以下步骤注册实验性 API 的试用版。</span><span class="sxs-lookup"><span data-stu-id="7a1e9-118">Use the following steps to register for a trial of an experimental API.</span></span>  

1.  <span data-ttu-id="7a1e9-119">访问[Microsoft Edge 原始试用开发人员控制台][DeveloperMicrsoftEdgeOriginTrials]页面。</span><span class="sxs-lookup"><span data-stu-id="7a1e9-119">Visit the [Microsoft Edge Origin Trials Developer Console][DeveloperMicrsoftEdgeOriginTrials] page.</span></span>  
1.  <span data-ttu-id="7a1e9-120">在任何可用实验中选择 "注册" 按钮。</span><span class="sxs-lookup"><span data-stu-id="7a1e9-120">Choose the Register button on any of the available experiments.</span></span>  
1.  <span data-ttu-id="7a1e9-121">使用 GitHub 用户名和密码登录到开发人员控制台。</span><span class="sxs-lookup"><span data-stu-id="7a1e9-121">Sign into the Developer Console using your GitHub username and password.</span></span>  
1.  <span data-ttu-id="7a1e9-122">选择 "**授权 MicrosoftEdge**"。</span><span class="sxs-lookup"><span data-stu-id="7a1e9-122">Choose **Authorize MicrosoftEdge**.</span></span>  
1.  <span data-ttu-id="7a1e9-123">填写表单。</span><span class="sxs-lookup"><span data-stu-id="7a1e9-123">Complete the form.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="7a1e9-124">若要注册单个或所有子域，请选择 "设置 `Do you need to match all subdomains for the provided origin?` 为" `Yes` 。</span><span class="sxs-lookup"><span data-stu-id="7a1e9-124">To enroll a single or all subdomains, choose set the `Do you need to match all subdomains for the provided origin?` setting to `Yes`.</span></span>  <span data-ttu-id="7a1e9-125">例如， `https://dev.contoso.com` 是单个域， `https://*.contoso.com` 使用通配符表示所有子域。</span><span class="sxs-lookup"><span data-stu-id="7a1e9-125">For example, `https://dev.contoso.com` is a single domain, and `https://*.contoso.com` uses a wildcard to represent all subdomains.</span></span>  
    
    > [!IMPORTANT]
    > <span data-ttu-id="7a1e9-126">不允许使用以下原始格式。</span><span class="sxs-lookup"><span data-stu-id="7a1e9-126">The following origin formats are not allowed.</span></span>  
    > *   <span data-ttu-id="7a1e9-127">在原始位置指定子文件夹。</span><span class="sxs-lookup"><span data-stu-id="7a1e9-127">Specifying a subfolder on the origin.</span></span>  <span data-ttu-id="7a1e9-128">例如，</span><span class="sxs-lookup"><span data-stu-id="7a1e9-128">For example,</span></span> `https://contoso.com/path/subfolder`  
    > 
    > *   <span data-ttu-id="7a1e9-129">将原点与查询字符串参数配合使用。</span><span class="sxs-lookup"><span data-stu-id="7a1e9-129">Using an origin with query string parameters.</span></span>  <span data-ttu-id="7a1e9-130">例如，</span><span class="sxs-lookup"><span data-stu-id="7a1e9-130">For example,</span></span> `https://contoso.com/path/feature?query_parameter=12345`  
    
1.  <span data-ttu-id="7a1e9-131">选择 "**接受和注册**"。</span><span class="sxs-lookup"><span data-stu-id="7a1e9-131">Choose **ACCEPT and REGISTER**.</span></span>  

### <span data-ttu-id="7a1e9-132">应用您的令牌</span><span class="sxs-lookup"><span data-stu-id="7a1e9-132">Apply your token</span></span>  

<span data-ttu-id="7a1e9-133">令牌将立即生成并显示在[Microsoft Edge 原始试验开发人员控制台][DeveloperMicrsoftEdgeOriginTrials]页面上。</span><span class="sxs-lookup"><span data-stu-id="7a1e9-133">A token is instantly generated and displayed on the [Microsoft Edge Origin Trials Developer Console][DeveloperMicrsoftEdgeOriginTrials] page.</span></span>  <span data-ttu-id="7a1e9-134">若要开始在你的网站上使用试用版，请使用以下任一方法将令牌应用于你的页面。</span><span class="sxs-lookup"><span data-stu-id="7a1e9-134">To begin using the trial on your website, use either of the following methods to apply the token to your page.</span></span>  

*   <span data-ttu-id="7a1e9-135">将该 `origin-trial` 属性值和你的令牌添加到 `meta` 使用实验性 API 的每个页面上的标记。</span><span class="sxs-lookup"><span data-stu-id="7a1e9-135">Add the `origin-trial` attribute value and your token to the `meta` tag on every page that uses the experimental API.</span></span>  
    
    ```html
    <meta http-equiv="origin-trial" content="replace-with-your-token">
    ```  
    
*   <span data-ttu-id="7a1e9-136">添加 `Origin-Trial` 到服务器的 HTTP 响应头。</span><span class="sxs-lookup"><span data-stu-id="7a1e9-136">Add `Origin-Trial` to the HTTP response header of your server.</span></span>  
    
    ```json
    Origin-Trial: replace-with-your-token
    ```  
    
> [!NOTE]
> <span data-ttu-id="7a1e9-137">您的令牌有效期为6周。</span><span class="sxs-lookup"><span data-stu-id="7a1e9-137">Your token is valid for 6 weeks.</span></span>  <span data-ttu-id="7a1e9-138">试用期结束之前，会向您发送提醒电子邮件，询问您的反馈，并要求您在令牌到期之前续订您的试用版。</span><span class="sxs-lookup"><span data-stu-id="7a1e9-138">Before your trial ends, reminder emails are sent to you that ask for your feedback and ask you to consider renewing your trial before your token expires.</span></span>  

### <span data-ttu-id="7a1e9-139">选择退出实验</span><span class="sxs-lookup"><span data-stu-id="7a1e9-139">Opt out of an experiment</span></span>  

<span data-ttu-id="7a1e9-140">若要退出实验，请使用以下方法之一删除你的令牌。</span><span class="sxs-lookup"><span data-stu-id="7a1e9-140">To opt out of an experiment, use one of the following methods to remove your token.</span></span>  

*   <span data-ttu-id="7a1e9-141">`meta`从使用实验 API 的每个页面中删除标记。</span><span class="sxs-lookup"><span data-stu-id="7a1e9-141">Remove the `meta` tag from every page that used the experimental API.</span></span>  
    
    ```html
    <meta http-equiv="origin-trial" content="your-token">
    ```  
    
*   <span data-ttu-id="7a1e9-142">`Origin-Trial`从服务器的 HTTP 响应头中删除。</span><span class="sxs-lookup"><span data-stu-id="7a1e9-142">Remove `Origin-Trial` from the HTTP response header of your server.</span></span>  
    
    ```json
    Origin-Trial: your-token
    ```  
    
### <span data-ttu-id="7a1e9-143">检测实验性功能并提供回退</span><span class="sxs-lookup"><span data-stu-id="7a1e9-143">Detect experimental features and provide a fallback</span></span>  

<span data-ttu-id="7a1e9-144">使用实验性 Api 时，请确保为网站的所有访问者提供工作体验。</span><span class="sxs-lookup"><span data-stu-id="7a1e9-144">When using experimental APIs, ensure you provide a working experience to all visitors of your website.</span></span>  <span data-ttu-id="7a1e9-145">访问者可以使用不支持你添加到代码中的实验性 Api 的浏览器。</span><span class="sxs-lookup"><span data-stu-id="7a1e9-145">Visitors may use browsers that do not support the experimental APIs that you added to your code.</span></span>  <span data-ttu-id="7a1e9-146">此外，如果你的令牌在续订之前到期，实验性 API 将不再可用，可能会导致错误。</span><span class="sxs-lookup"><span data-stu-id="7a1e9-146">Additionally, if your token expires before you renew it, the experimental API is no longer available which may result in errors.</span></span>  <span data-ttu-id="7a1e9-147">为避免这种情况，请确保检测浏览器中的可用功能。</span><span class="sxs-lookup"><span data-stu-id="7a1e9-147">To avoid this situation, ensure you detect features available in your browser.</span></span>  <span data-ttu-id="7a1e9-148">有关详细信息，请参阅[实现功能检测][MDNImplementingFeatureDetection]。</span><span class="sxs-lookup"><span data-stu-id="7a1e9-148">For more information, see [Implementing feature detection][MDNImplementingFeatureDetection].</span></span>

### <span data-ttu-id="7a1e9-149">允许的来源路线图</span><span class="sxs-lookup"><span data-stu-id="7a1e9-149">Roadmap for Allowed Origins</span></span>  

<span data-ttu-id="7a1e9-150">现在，Microsoft Edge 原始试用门户仅支持 SSL 启用的来源，这意味着网站必须正确实现 HTTPS 才能注册实验。</span><span class="sxs-lookup"><span data-stu-id="7a1e9-150">The Microsoft Edge Origin Trials portal today only supports SSL Enabled Origins, which means that websites must have HTTPS properly implemented to register for an experiment.</span></span>  <span data-ttu-id="7a1e9-151">将来，计划提供以下安全来源。</span><span class="sxs-lookup"><span data-stu-id="7a1e9-151">In the future, the following secure origins are planned.</span></span>  

*   <span data-ttu-id="7a1e9-152">注册 `http://localhost` 为实验的来源。</span><span class="sxs-lookup"><span data-stu-id="7a1e9-152">Register `http://localhost` as the origin for your experiments.</span></span>  <span data-ttu-id="7a1e9-153">若要 `http://localhost` 立即使用，请转到 `edge://flags` 并将实验设置为 "**启用**"。</span><span class="sxs-lookup"><span data-stu-id="7a1e9-153">To use `http://localhost` today, go to `edge://flags` and set the experiment to **Enabled**.</span></span>  
*   <span data-ttu-id="7a1e9-154">使用具有前缀的来源的扩展名 `extensions://` 注册实验。</span><span class="sxs-lookup"><span data-stu-id="7a1e9-154">Use extensions with `extensions://` prefixed origins to enroll in experiments.</span></span>  
    
<!-- links -->  

[DeveloperMicrsoftEdgeOriginTrials]: https://developer.microsoft.com/microsoft-edge/origin-trials "Microsoft Edge 原始试用开发人员控制台 |Microsoft 文档"  

[MDNImplementingFeatureDetection]: https://developer.mozilla.org/docs/learn/tools_and_testing/cross_browser_testing/feature_detection "实施功能检测 |MDN"  
