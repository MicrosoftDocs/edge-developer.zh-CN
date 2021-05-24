---
description: 本文提供有关用户代理Microsoft Edge提示和用户代理字符串的文档
title: 如何检测Microsoft Edge网站中的内容
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/19/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， 兼容性， Web 平台， 用户代理字符串， ua 字符串， ua 替代， 用户代理客户端提示， 用户代理客户端提示， ua 客户端提示， ua ch
ms.openlocfilehash: 1957bb5bd33d9d921d8a12e16a4a52a23836027b
ms.sourcegitcommit: e90bbc210b5d510004bbc2145d49e14fe72ed54b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2021
ms.locfileid: "11578775"
---
# <a name="how-to-detect-microsoft-edge-in-your-website"></a><span data-ttu-id="aeb9a-104">如何检测Microsoft Edge网站中的内容</span><span class="sxs-lookup"><span data-stu-id="aeb9a-104">How to detect Microsoft Edge in your website</span></span>  

<span data-ttu-id="aeb9a-105">浏览器为网站提供检测浏览器信息（如品牌和版本号）的机制。</span><span class="sxs-lookup"><span data-stu-id="aeb9a-105">Browsers provide mechanisms for websites to detect browser information such as brand and version number.</span></span>  <span data-ttu-id="aeb9a-106">这些机制还会检测主机操作系统等其他设备特征。</span><span class="sxs-lookup"><span data-stu-id="aeb9a-106">The mechanisms also detect other device characteristics like the host operating system.</span></span>  <span data-ttu-id="aeb9a-107">在客户端上支持的两Microsoft Edge是[用户代理客户端提示](#user-agent-client-hints)和[用户代理字符串](#user-agent-string)。</span><span class="sxs-lookup"><span data-stu-id="aeb9a-107">Two such mechanisms supported on Microsoft Edge are [User-Agent Client Hints](#user-agent-client-hints) and [User-Agent strings](#user-agent-string).</span></span>  <span data-ttu-id="aeb9a-108">几十年后，User-Agent字符串已过时，并且作为网站兼容性问题的原因具有很长的历史。</span><span class="sxs-lookup"><span data-stu-id="aeb9a-108">After decades of use, User-Agent strings are outdated and have a long history as the cause of website compatibility issues.</span></span>  <span data-ttu-id="aeb9a-109">相反，Microsoft Edge建议使用改进的机制来检索名为[User-Agent Client Hints 的浏览器信息](#user-agent-client-hints)。</span><span class="sxs-lookup"><span data-stu-id="aeb9a-109">Instead, the Microsoft Edge team recommends you use an improved mechanism to retrieve browser information named [User-Agent Client Hints](#user-agent-client-hints).</span></span>  <span data-ttu-id="aeb9a-110">本文概述了检索用户代理Microsoft Edge两种机制。</span><span class="sxs-lookup"><span data-stu-id="aeb9a-110">This article outlines the two mechanisms Microsoft Edge supports for retrieving user agent information.</span></span>  

|  | <span data-ttu-id="aeb9a-111">服务器端</span><span class="sxs-lookup"><span data-stu-id="aeb9a-111">Server-side</span></span> | <span data-ttu-id="aeb9a-112">客户端</span><span class="sxs-lookup"><span data-stu-id="aeb9a-112">Client-side</span></span> |  
|:--- |:--- |:--- | 
| <span data-ttu-id="aeb9a-113">**用户代理客户端提示** \ (推荐\) </span><span class="sxs-lookup"><span data-stu-id="aeb9a-113">**User-Agent Client Hints** \(recommended\)</span></span> | `Sec-CH-UA` <span data-ttu-id="aeb9a-114">HTTPS 标头</span><span class="sxs-lookup"><span data-stu-id="aeb9a-114">HTTPS header</span></span> | `navigator.userAgentData` <span data-ttu-id="aeb9a-115">JavaScript 方法</span><span class="sxs-lookup"><span data-stu-id="aeb9a-115">JavaScript method</span></span> |  
| <span data-ttu-id="aeb9a-116">**User-Agent string** \ (legacy\) </span><span class="sxs-lookup"><span data-stu-id="aeb9a-116">**User-Agent string** \(legacy\)</span></span> | `User-Agent` <span data-ttu-id="aeb9a-117">HTTPS 标头</span><span class="sxs-lookup"><span data-stu-id="aeb9a-117">HTTPS header</span></span> | `navigator.userAgent` <span data-ttu-id="aeb9a-118">JavaScript 方法</span><span class="sxs-lookup"><span data-stu-id="aeb9a-118">JavaScript method</span></span> |  

<span data-ttu-id="aeb9a-119">出于以下原因，Microsoft 建议 [尽可能][MdnLearnToolsTestingCrossBrowserTestingFeatureDetection] 使用功能检测。</span><span class="sxs-lookup"><span data-stu-id="aeb9a-119">Microsoft recommends that you use [feature detection][MdnLearnToolsTestingCrossBrowserTestingFeatureDetection] whenever possible for the following reasons.</span></span>  

*   <span data-ttu-id="aeb9a-120">提高代码可维护性。</span><span class="sxs-lookup"><span data-stu-id="aeb9a-120">Improve code maintainability.</span></span>  
*   <span data-ttu-id="aeb9a-121">减少代码错误。</span><span class="sxs-lookup"><span data-stu-id="aeb9a-121">Reduce code fragility.</span></span>  
*   <span data-ttu-id="aeb9a-122">减少代码中断（由对字符串User-Agent更改。</span><span class="sxs-lookup"><span data-stu-id="aeb9a-122">Reduce code breakage from changes to the User-Agent string.</span></span>  
    
<span data-ttu-id="aeb9a-123">当[功能][MdnLearnToolsTestingCrossBrowserTestingFeatureDetection]检测不适用并且必须使用用户代理检测时，使用以下格式检测 Microsoft Edge 和 Android 上的Windows代理。</span><span class="sxs-lookup"><span data-stu-id="aeb9a-123">When [feature detection][MdnLearnToolsTestingCrossBrowserTestingFeatureDetection] isn't applicable and you must use user agent detection, use the following format to detect Microsoft Edge user agent on Windows and Android.</span></span>  

## <a name="user-agent-client-hints"></a><span data-ttu-id="aeb9a-124">User-Agent客户端提示</span><span class="sxs-lookup"><span data-stu-id="aeb9a-124">User-Agent Client Hints</span></span>  

<span data-ttu-id="aeb9a-125">从 Microsoft Edge版本 90 开始，以更简洁、更隐私的方式访问浏览器信息。</span><span class="sxs-lookup"><span data-stu-id="aeb9a-125">Starting in Microsoft Edge version 90, access browser information in a cleaner, more privacy-preserving way.</span></span>  

### <a name="user-agent-client-hints-https-header"></a><span data-ttu-id="aeb9a-126">User-Agent客户端提示 HTTPS 标头</span><span class="sxs-lookup"><span data-stu-id="aeb9a-126">User-Agent Client Hints HTTPS Header</span></span>  

<span data-ttu-id="aeb9a-127">默认情况下，Chromium包括 Microsoft Edge以 `Accept-CH-UA` 以下格式发送响应头。</span><span class="sxs-lookup"><span data-stu-id="aeb9a-127">By default, Chromium browsers including Microsoft Edge send the `Accept-CH-UA` response header in the following format.</span></span>  

```https
Sec-CH-UA: "Chromium";v="91", "Microsoft Edge";v="91","Dummy;Browser Brand";v="99"
Sec-CH-UA-Mobile: ?0
```  

> [!NOTE]
> <span data-ttu-id="aeb9a-128">客户端提示仅使用 通过安全连接发送 `HTTPS` 。</span><span class="sxs-lookup"><span data-stu-id="aeb9a-128">Client Hints are only sent over secure connections using `HTTPS`.</span></span>  

<span data-ttu-id="aeb9a-129">默认情况下发送以下低向异性提示。</span><span class="sxs-lookup"><span data-stu-id="aeb9a-129">The following low entropy hints are sent by default.</span></span>  <span data-ttu-id="aeb9a-130">如果需要访问更多信息，请发送以下请求标头之一。</span><span class="sxs-lookup"><span data-stu-id="aeb9a-130">If you need to access more information, send one of the following request headers.</span></span>  

#### <a name="user-agent-request-and-response-headers"></a><span data-ttu-id="aeb9a-131">User-Agent请求和响应头</span><span class="sxs-lookup"><span data-stu-id="aeb9a-131">User-Agent request and response headers</span></span>  

| <span data-ttu-id="aeb9a-132">请求头</span><span class="sxs-lookup"><span data-stu-id="aeb9a-132">Request header</span></span> | <span data-ttu-id="aeb9a-133">示例响应值</span><span class="sxs-lookup"><span data-stu-id="aeb9a-133">Example response value</span></span> |  
|:--- |:--- |  
| `Sec-CH-UA` | `"Chromium";v="91", "Microsoft Edge";v="91","GREASE";v="99"` |  
| `Sec-CH-UA-Mobile` | `false` |  
| `Sec-CH-UA-Full-Version` | `91.0.866.0` |  
| `Sec-CH-UA-Platform` | `Windows` |  
| `Sec-CH-UA Platform-Version` | `10.0` |  
| `Sec-CH-UA-Arch` | `x86` |  
| `Sec-CH-UA-Model` |  |  

### <a name="user-agent-client-hints-javascript-api"></a><span data-ttu-id="aeb9a-134">User-Agent客户端提示 JavaScript API</span><span class="sxs-lookup"><span data-stu-id="aeb9a-134">User-Agent Client Hints JavaScript API</span></span>  

<span data-ttu-id="aeb9a-135">中的默认响应 `navigator.userAgentData` 值采用以下格式。</span><span class="sxs-lookup"><span data-stu-id="aeb9a-135">The default response value from `navigator.userAgentData` uses the following format.</span></span>  

```javascript
{ brands: [ {brand: "Chromium","version":"91"}, {brand: "Microsoft Edge","version":"91"}, {brand: "GREASE","version":"99"}, ]
mobile: false }
```  

<span data-ttu-id="aeb9a-136">如果需要访问更多详细信息，请使用 [getHighEntropyValues ][GithubWicgUaClientHintsGethighentropyvalues] () 方法。</span><span class="sxs-lookup"><span data-stu-id="aeb9a-136">If you need to access more detailed information, use the [getHighEntropyValues()][GithubWicgUaClientHintsGethighentropyvalues] method.</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="aeb9a-137">以下代码段发送请求。</span><span class="sxs-lookup"><span data-stu-id="aeb9a-137">The following code snippet sends a request.</span></span>  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="aeb9a-138">接收以下响应。</span><span class="sxs-lookup"><span data-stu-id="aeb9a-138">To receive the following response.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      ```javascript
         navigator.userAgentData.getHighEntropyValues(
             ["architecture", "model", "platform", "platformVersion", "uaFullVersion"])
             .then(ua => { console.log(ua) });
      ```  
   :::column-end:::
   :::column span="":::
      ```javascript
      {architecture: "x86", 
      model: "", 
      platform: "Windows", 
      platformVersion: "10.0", 
      uaFullVersion: "92.0.866.0"}
      ```  
   :::column-end:::
:::row-end:::  

## <a name="recommended-uses-of-user-agent-client-hints"></a><span data-ttu-id="aeb9a-139">客户端提示User-Agent用法</span><span class="sxs-lookup"><span data-stu-id="aeb9a-139">Recommended uses of User-Agent Client Hints</span></span>  

<span data-ttu-id="aeb9a-140">品牌集和关联的显示顺序会随着时间的推移而改变，因此你绝不应该将索引硬编码为返回的品牌数组。</span><span class="sxs-lookup"><span data-stu-id="aeb9a-140">The set of brands and the associated display order change over time, so you should never hard-code indices into the array of returned brands.</span></span>  <span data-ttu-id="aeb9a-141">为了帮助确保尽早在网站中发现类似问题，浏览器包含的品牌值会随着时间的推移而更改，并因常见字符串分析问题而格式化 `GREASE` 为中断。</span><span class="sxs-lookup"><span data-stu-id="aeb9a-141">To help ensure you spot similar issues in your website early, the browser includes a `GREASE` brand value that changes over time and is formatted to break because of common string parsing issues.</span></span>  

<span data-ttu-id="aeb9a-142">如果阻止使用功能检测，请不要使用[][MdnLearnToolsTestingCrossBrowserTestingFeatureDetection]基于 Chromium 的已知浏览器的硬编码列表进行验证。</span><span class="sxs-lookup"><span data-stu-id="aeb9a-142">If you're prevented from using [feature detection][MdnLearnToolsTestingCrossBrowserTestingFeatureDetection], don't use a hardcoded list of known Chromium-based browsers for verification.</span></span>  <span data-ttu-id="aeb9a-143">硬编码浏览器名称的示例包括 `Microsoft Edge` 和 `Google Chrome` 。</span><span class="sxs-lookup"><span data-stu-id="aeb9a-143">Examples of hardcoded browser names include `Microsoft Edge` and `Google Chrome`.</span></span>  <span data-ttu-id="aeb9a-144">功能 [检测不适用][MdnLearnToolsTestingCrossBrowserTestingFeatureDetection] 的原因可能包括以下情况。</span><span class="sxs-lookup"><span data-stu-id="aeb9a-144">Reasons why [feature detection][MdnLearnToolsTestingCrossBrowserTestingFeatureDetection] isn't applicable may include the following situation.</span></span>  

*   <span data-ttu-id="aeb9a-145">必须避免在Chromium版本中修复错误，并且受影响的浏览器很难在品牌和版本验证之外检测到。</span><span class="sxs-lookup"><span data-stu-id="aeb9a-145">A fix for a Chromium bug in a later version must be avoided and the affected browsers are difficult to detect outside of a verification of the brand and version.</span></span>  
    
<span data-ttu-id="aeb9a-146">相反，你应该验证品牌， `Chromium` 以确保你的检测适用于所有受影响的Chromium浏览器。</span><span class="sxs-lookup"><span data-stu-id="aeb9a-146">Instead, you should verify the `Chromium` brand, which ensures your detection applies to all affected Chromium-based browsers.</span></span>  


```javascript
function isChromium() {
    for (brand_version_pair in navigator.userAgentData.brands) {
        if (brand_version_pair.brand == "Chromium") {
            return true;
        }
    }
    return false;
}
```  

## <a name="user-agent-string"></a><span data-ttu-id="aeb9a-147">用户代理字符串</span><span class="sxs-lookup"><span data-stu-id="aeb9a-147">User agent string</span></span>  

<span data-ttu-id="aeb9a-148">如果可能，Microsoft 建议根据用户代理字符串Microsoft Edge浏览器检测逻辑的使用。</span><span class="sxs-lookup"><span data-stu-id="aeb9a-148">Wherever possible, Microsoft recommends you minimize your use of Microsoft Edge browser detection logic based on the user agent string.</span></span>  <span data-ttu-id="aeb9a-149">如果你有一个很好的理由来检测用户代理，Microsoft Edge建议你使用[用户代理](#user-agent-client-hints)客户端提示作为主要检测逻辑。</span><span class="sxs-lookup"><span data-stu-id="aeb9a-149">If you have a good reason to detect the user agent, the Microsoft Edge team recommends you use [User-Agent Client Hints](#user-agent-client-hints) as the primary detection logic.</span></span>  <span data-ttu-id="aeb9a-150">[用户代理客户端提示](#user-agent-client-hints) 还可以减少所需的分析字符串数。</span><span class="sxs-lookup"><span data-stu-id="aeb9a-150">[User-Agent Client Hints](#user-agent-client-hints) also reduces the required number of parsed strings.</span></span>  <span data-ttu-id="aeb9a-151">但是，对于旧引用，以下格式用于User-Agent字符串。</span><span class="sxs-lookup"><span data-stu-id="aeb9a-151">However, for legacy reference, the following format is used for the User-Agent string.</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="aeb9a-152">在Windows上 `User-Agent` ，HTTP 请求标头采用以下格式。</span><span class="sxs-lookup"><span data-stu-id="aeb9a-152">On Windows, the `User-Agent` HTTP request header uses the following format.</span></span>  
   :::column-end:::
   :::column span="":::
      <span data-ttu-id="aeb9a-153">在 Android 上 `User-Agent` ，HTTP 请求标头采用以下格式。</span><span class="sxs-lookup"><span data-stu-id="aeb9a-153">On Android, the `User-Agent` HTTP request header uses the following format.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      ```https
      User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/90.0.4430.85 Safari/537.36 Edg/90.0.818.46
      ```  
   :::column-end:::
   :::column span="":::
      ```https
      User-Agent: Mozilla/5.0 (Linux; Android 6.0; Nexus 5 Build/MRA58N) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/90.0.4430.85 Mobile Safari/537.36 Edg/90.0.818.46
      ```  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="aeb9a-154">来自 方法的响应 `navigator.userAgent` 值采用以下格式。</span><span class="sxs-lookup"><span data-stu-id="aeb9a-154">The response value from `navigator.userAgent` method uses the following format.</span></span>  

```javascript
"Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/91.0.4501.0 Safari/537.36 Edg/91.0.866.0"
```  

<span data-ttu-id="aeb9a-155">平台标识符根据使用的操作系统发生变化，版本号也会随着时间推移而递增。</span><span class="sxs-lookup"><span data-stu-id="aeb9a-155">Platform identifiers change based on the operating system used, and the version numbers also increment as time passes.</span></span>  <span data-ttu-id="aeb9a-156">格式与用户代理Chromium，末尾添加 `Edg` 一个新令牌。</span><span class="sxs-lookup"><span data-stu-id="aeb9a-156">The format is the same as the Chromium user agent with the addition of a new `Edg` token at the end.</span></span>  <span data-ttu-id="aeb9a-157">Microsoft 选择令牌以避免由字符串引起的兼容性问题，字符串在基于 `Edg` `Edge` EdgeHTML Microsoft Edge旧版浏览器。</span><span class="sxs-lookup"><span data-stu-id="aeb9a-157">Microsoft chose the `Edg` token to avoid compatibility issues caused by `Edge` string, which was used legacy Microsoft Edge browser based on EdgeHTML.</span></span>  <span data-ttu-id="aeb9a-158">令牌 `Edg` 还与 iOS[][WindowsBlogsMsedgedev20171005MicrosoftEdgeIosAndroidDeveloper]和 Android 上使用的现有令牌一致。</span><span class="sxs-lookup"><span data-stu-id="aeb9a-158">The `Edg` token is also consistent with [existing tokens][WindowsBlogsMsedgedev20171005MicrosoftEdgeIosAndroidDeveloper] used on iOS and Android.</span></span>

## <a name="map-the-user-agent-string-to-browser-name"></a><span data-ttu-id="aeb9a-159">将用户代理字符串映射到浏览器名称</span><span class="sxs-lookup"><span data-stu-id="aeb9a-159">Map the user agent string to browser name</span></span>  

<span data-ttu-id="aeb9a-160">将用户代理字符串令牌映射到在代码中使用的更用户可读的浏览器名称。</span><span class="sxs-lookup"><span data-stu-id="aeb9a-160">Map the user agent string tokens to a more human-readable browser name to use in code.</span></span>  <span data-ttu-id="aeb9a-161">这是当今 Web 上的常见模式。</span><span class="sxs-lookup"><span data-stu-id="aeb9a-161">It's a common pattern on the web today.</span></span>  <span data-ttu-id="aeb9a-162">将新令牌映射到浏览器名称时，Microsoft 建议使用与旧版 Microsoft Edge 浏览器不同的名称，以避免意外应用不适用于基于 Chromium 的浏览器的任何旧解决方法。 `Edg`</span><span class="sxs-lookup"><span data-stu-id="aeb9a-162">When you map the new `Edg` token to a browser name, Microsoft recommends that you use a different name than the one used for the legacy Microsoft Edge browser to avoid accidentally applying any legacy workarounds that aren't applicable to Chromium-based browsers.</span></span>

## <a name="user-agent-overrides"></a><span data-ttu-id="aeb9a-163">用户代理替代</span><span class="sxs-lookup"><span data-stu-id="aeb9a-163">User Agent overrides</span></span>  

<span data-ttu-id="aeb9a-164">有时，网站无法识别新Microsoft Edge代理。</span><span class="sxs-lookup"><span data-stu-id="aeb9a-164">Sometimes, a website doesn't recognize the new Microsoft Edge user agent.</span></span>  <span data-ttu-id="aeb9a-165">因此，一组网站功能可能无法正常运行。</span><span class="sxs-lookup"><span data-stu-id="aeb9a-165">As a result, a set of the features of the website may not work correctly.</span></span>  <span data-ttu-id="aeb9a-166">当 Microsoft 收到问题类型通知时，Microsoft 将联系你 \ (网站所有者\) 并通知你更新的用户代理。</span><span class="sxs-lookup"><span data-stu-id="aeb9a-166">When Microsoft is notified about the types of issues, Microsoft contacts you \(a website owner\) and informs you about the updated user agent.</span></span>  

<span data-ttu-id="aeb9a-167">可能需要更多时间来更新和测试网站的用户代理检测逻辑，以解决 Microsoft 报告的问题。</span><span class="sxs-lookup"><span data-stu-id="aeb9a-167">You may need more time to update and test the user agent detection logic for your website to address the issues reported by Microsoft.</span></span>  <span data-ttu-id="aeb9a-168">为了最大限度地提高用户的兼容性，Microsoft Edge Beta和稳定渠道使用用户代理替代列表。</span><span class="sxs-lookup"><span data-stu-id="aeb9a-168">To maximize compatibility for your users, the Microsoft Edge Beta and Stable channels use a list of user agent overrides.</span></span>  <span data-ttu-id="aeb9a-169">更新网站时，请使用用户代理替代。</span><span class="sxs-lookup"><span data-stu-id="aeb9a-169">Use the user agent overrides while you update your website.</span></span>  <span data-ttu-id="aeb9a-170">Microsoft 提供的用户代理替代列表。</span><span class="sxs-lookup"><span data-stu-id="aeb9a-170">The list of user agent overrides provided by Microsoft.</span></span>  

<span data-ttu-id="aeb9a-171">替代指定要发送Microsoft Edge用户代理值，而不是指定特定网站的默认用户代理。</span><span class="sxs-lookup"><span data-stu-id="aeb9a-171">The overrides specify new user agent values that Microsoft Edge sends instead of the default user agent for specific websites.</span></span>  <span data-ttu-id="aeb9a-172">若要显示当前应用的用户代理替代列表，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="aeb9a-172">To display the list of user agent overrides that are currently applied, complete the following actions.</span></span>  

1.  <span data-ttu-id="aeb9a-173">打开 Microsoft Edge Beta 或 Stable 渠道。</span><span class="sxs-lookup"><span data-stu-id="aeb9a-173">Open the Microsoft Edge Beta or Stable channel.</span></span>  
1.  <span data-ttu-id="aeb9a-174">导航到 `edge://compat/useragent`。</span><span class="sxs-lookup"><span data-stu-id="aeb9a-174">Navigate to `edge://compat/useragent`.</span></span>  
    
<span data-ttu-id="aeb9a-175">Canary Microsoft Edge开发人员频道当前不会接收用户代理覆盖。</span><span class="sxs-lookup"><span data-stu-id="aeb9a-175">The Microsoft Edge Canary and Dev channels don't currently receive user agent overrides.</span></span>  <span data-ttu-id="aeb9a-176">Canary Microsoft Edge开发人员频道提供的环境使用默认模式Microsoft Edge代理。</span><span class="sxs-lookup"><span data-stu-id="aeb9a-176">The Microsoft Edge Canary and Dev channels provide environments that use the default Microsoft Edge user agent.</span></span>  <span data-ttu-id="aeb9a-177">使用Microsoft Edge Canary 和 Dev 渠道轻松重现由默认用户代理导致Microsoft Edge问题。</span><span class="sxs-lookup"><span data-stu-id="aeb9a-177">Use the Microsoft Edge Canary and Dev channels to easily reproduce issues on your website caused by the default Microsoft Edge user agent.</span></span>  <span data-ttu-id="aeb9a-178">若要在渠道或稳定渠道中Microsoft Edge Beta代理替代，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="aeb9a-178">To turn off user agent overrides in the Microsoft Edge Beta or Stable channels, complete the following actions.</span></span>  

1.  <span data-ttu-id="aeb9a-179">打开命令行应用。</span><span class="sxs-lookup"><span data-stu-id="aeb9a-179">Open your command-line app.</span></span>  
1.  <span data-ttu-id="aeb9a-180">复制并粘贴以下代码段。</span><span class="sxs-lookup"><span data-stu-id="aeb9a-180">Copy and paste the following code snippet.</span></span>  
    
    ```shell
    --disable-domain-action-user-agent-override
    ```  
    
1.  <span data-ttu-id="aeb9a-181">使用Microsoft Edge代码段运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="aeb9a-181">Run the Microsoft Edge app using the code snippet.</span></span>  
    
    ```shell
    {path/to/microsoft/edge.ext} --disable-domain-action-user-agent-override
    ```  
    
<!-- links -->  

[WindowsBlogsMsedgedev20171005MicrosoftEdgeIosAndroidDeveloper]: https://blogs.windows.com/msedgedev/2017/10/05/microsoft-edge-ios-android-developer "Microsoft Edge iOS 和 Android 版：开发人员需要知道哪些|Microsoft Windows 博客"  

[GithubWicgUaClientHintsGethighentropyvalues]: https://wicg.github.io/ua-client-hints#getHighEntropyValues "4.1.5. getHighEntropyValues 方法 - User-Agent客户端|GitHub"  

[MdnLearnToolsTestingCrossBrowserTestingFeatureDetection]: https://developer.mozilla.org/docs/Learn/Tools_and_testing/Cross_browser_testing/Feature_detection "实现功能检测|MDN"  
