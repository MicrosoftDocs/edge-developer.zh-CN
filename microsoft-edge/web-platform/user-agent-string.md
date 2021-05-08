---
description: 此页面提供有关用户代理Microsoft Edge的文档
title: Microsoft Edge用户代理字符串
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/16/2019
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， 兼容性， Web 平台， 用户代理字符串， ua 字符串， ua 替代
ms.openlocfilehash: 73401219b7708a739292a46b6131fe40765e9c8c
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564599"
---
# <span data-ttu-id="d469d-104">Microsoft Edge桌面 (用户代理) </span><span class="sxs-lookup"><span data-stu-id="d469d-104">Microsoft Edge User Agent String (Desktop)</span></span>  

<span data-ttu-id="d469d-105">用户代理 \ (UA\) 字符串可用于检测特定浏览器正在特定操作系统中使用的版本。</span><span class="sxs-lookup"><span data-stu-id="d469d-105">A user agent \(UA\) string is able to be used to detect what version of a specific browser is being used on a certain operating system.</span></span>  <span data-ttu-id="d469d-106">与其他浏览器一Microsoft Edge，只要向网站提出请求，就会在 `User-Agent` HTTP 标头中包含此信息。</span><span class="sxs-lookup"><span data-stu-id="d469d-106">Like other browsers, Microsoft Edge includes this information in the `User-Agent` HTTP header whenever it makes a request to a site.</span></span>  <span data-ttu-id="d469d-107">还可通过查询 的值通过 JavaScript 访问 `navigator.userAgent` 它。</span><span class="sxs-lookup"><span data-stu-id="d469d-107">It may also be accessed via JavaScript by querying the value of `navigator.userAgent`.</span></span>  

<span data-ttu-id="d469d-108">Microsoft 建议 Web 开发人员尽可能[](https://developer.mozilla.org/docs/Learn/Tools_and_testing/Cross_browser_testing/Feature_detection)利用功能检测来提高代码可维护性、减少代码错误，并在将来的 UA 字符串更新中消除代码中断的风险。</span><span class="sxs-lookup"><span data-stu-id="d469d-108">Microsoft recommends that web developers make use of [feature detection](https://developer.mozilla.org/docs/Learn/Tools_and_testing/Cross_browser_testing/Feature_detection) whenever possible to improve code maintainability, reduce code fragility, and eliminate the risk of code breakage in the event of future UA string updates.</span></span>  

<span data-ttu-id="d469d-109">对于功能检测不适用且必须使用 UA 检测的情况，Microsoft Edge UA 的格式如下所示：</span><span class="sxs-lookup"><span data-stu-id="d469d-109">For cases where feature detection is not applicable and UA detection must be used, the format of the Microsoft Edge UA on desktop is as follows:</span></span>

<span data-ttu-id="d469d-110">请求 `User-Agent` 标头的格式如下：</span><span class="sxs-lookup"><span data-stu-id="d469d-110">The `User-Agent` request header is in the following format:</span></span>

```http
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/79.0.3945.74 Safari/537.36 Edg/79.0.309.43
``` 

<span data-ttu-id="d469d-111">的返回 `navigator.userAgent` 值采用以下格式：</span><span class="sxs-lookup"><span data-stu-id="d469d-111">The return value from `navigator.userAgent` is in the following format:</span></span>

```javascript
"Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/79.0.3945.74 Safari/537.36 Edg/79.0.309.43"
```  

<span data-ttu-id="d469d-112">平台标识符根据所使用的操作系统而更改，版本号也会随着时间推移而递增。</span><span class="sxs-lookup"><span data-stu-id="d469d-112">Platform identifiers change based on the operating system being used, and version numbers also increment as time passes.</span></span>  <span data-ttu-id="d469d-113">此格式与末尾添加Chromium标记的 UA `Edg` 格式相同。</span><span class="sxs-lookup"><span data-stu-id="d469d-113">This format is the same as the Chromium UA with the addition of a new `Edg` token at the end.</span></span>  <span data-ttu-id="d469d-114">Microsoft 选择了令牌以避免使用字符串 （由基于 EdgeHTML 的 Microsoft Edge使用）可能导致 `Edg` `Edge` 的兼容性问题。</span><span class="sxs-lookup"><span data-stu-id="d469d-114">Microsoft selected the `Edg` token to avoid compatibility issues that may be caused by using the string `Edge`, which is used by the version of Microsoft Edge based on EdgeHTML.</span></span>  <span data-ttu-id="d469d-115">令牌 `Edg` 还与 iOS[](https://blogs.windows.com/msedgedev/2017/10/05/microsoft-edge-ios-android-developer/)和 Android 上使用的现有令牌一致。</span><span class="sxs-lookup"><span data-stu-id="d469d-115">The `Edg` token is also consistent with [existing tokens](https://blogs.windows.com/msedgedev/2017/10/05/microsoft-edge-ios-android-developer/) used on iOS and Android.</span></span>

## <span data-ttu-id="d469d-116">将 UA 字符串映射到浏览器名称</span><span class="sxs-lookup"><span data-stu-id="d469d-116">Mapping UA String to Browser Name</span></span>
<span data-ttu-id="d469d-117">将 UA 字符串令牌映射到更可读的浏览器名称以用于代码是当今 Web 上的常见模式。</span><span class="sxs-lookup"><span data-stu-id="d469d-117">Mapping UA string tokens to a more human-readable browser name for use in code is a common pattern on the web today.</span></span> <span data-ttu-id="d469d-118">将新令牌映射到浏览器名称时，Microsoft 建议使用与开发人员用于旧版 Microsoft Edge 的不同名称，以避免意外应用不适用于基于 Chromium 的浏览器的任何旧解决方法。 `Edg`</span><span class="sxs-lookup"><span data-stu-id="d469d-118">When mapping the new `Edg` token to a browser name, Microsoft recommends using a different name than the one developers used for the legacy version of Microsoft Edge to avoid accidentally applying any legacy workarounds that are not applicable to Chromium-based browsers.</span></span>

## <span data-ttu-id="d469d-119">用户代理替代</span><span class="sxs-lookup"><span data-stu-id="d469d-119">User Agent Overrides</span></span>  

<span data-ttu-id="d469d-120">有时，网站无法识别更新版本的 Microsoft Edge UA。</span><span class="sxs-lookup"><span data-stu-id="d469d-120">Sometimes, a website does not recognize the updated version of the Microsoft Edge UA.</span></span>  <span data-ttu-id="d469d-121">因此，该网站的一组功能可能无法正常运行。</span><span class="sxs-lookup"><span data-stu-id="d469d-121">As a result, a set of the features of that website may not work correctly.</span></span>  <span data-ttu-id="d469d-122">当 Microsoft 收到有关这些类型问题的通知时，将联系网站所有者并通知他们有关更新的 UA 的信息。</span><span class="sxs-lookup"><span data-stu-id="d469d-122">When Microsoft is notified about these types of issues, website owners are contacted and informed about the updated UA.</span></span>  

<span data-ttu-id="d469d-123">网站通常需要一些时间来更新和测试 UA 检测逻辑，以解决 Microsoft 向网站所有者报告的问题。</span><span class="sxs-lookup"><span data-stu-id="d469d-123">The sites often need some time to update and test the UA detection logic to address the issues that Microsoft reports to site owners.</span></span>  <span data-ttu-id="d469d-124">在这些情况下，Microsoft 在我们的 Beta 和 Stable 渠道中使用 UA 替代列表，以最大限度地提高访问这些网站的用户的兼容性。</span><span class="sxs-lookup"><span data-stu-id="d469d-124">In these cases, Microsoft uses a list of UA overrides in our Beta and Stable channels to maximize compatibility for users who access these sites.</span></span>  <span data-ttu-id="d469d-125">替代指定应发送的新 UA Microsoft Edge，而不是特定站点的默认 UA。</span><span class="sxs-lookup"><span data-stu-id="d469d-125">The overrides specify new UA values that Microsoft Edge should send instead of the default UA for specific sites.</span></span>  <span data-ttu-id="d469d-126">通过导航到当前应用的 Beta 和稳定渠道中的 UA 替代列表 `edge://compat/useragent` ，Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="d469d-126">You are able to view the list of UA overrides that are currently being applied by navigating to `edge://compat/useragent` in the Beta and Stable channels of Microsoft Edge.</span></span> 

<span data-ttu-id="d469d-127">我们的 Canary 和 Dev 渠道当前不会收到 UA 覆盖，以便 Microsoft Edge Web 开发人员可以在其中轻松重现由默认 UA 导致的问题。</span><span class="sxs-lookup"><span data-stu-id="d469d-127">Our Canary and Dev channels do not currently receive UA overrides so that web developers have an environment where they can easily reproduce issues on their sites that are caused by the default Microsoft Edge UA.</span></span>  <span data-ttu-id="d469d-128">如果出于某种原因需要能够在 Microsoft Edge 的 Beta 或 Stable 渠道中禁用 UA 覆盖，可以使用以下命令行参数运行 Microsoft Edge 可执行文件：</span><span class="sxs-lookup"><span data-stu-id="d469d-128">If for some reason you require the ability to disable UA overrides in the Beta or Stable channels of Microsoft Edge, you may run the Microsoft Edge executable using the following command line argument:</span></span>  

```shell
--disable-domain-action-user-agent-override
```  
