---
description: This page provides documentation on the Microsoft Edge user agent string
title: Microsoft Edge User Agent String
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/16/2019
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, compatibility, web platform, user agent string, ua string, ua overrides
ms.openlocfilehash: 73401219b7708a739292a46b6131fe40765e9c8c
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564599"
---
# <span data-ttu-id="ea317-104">Microsoft Edge User Agent String (Desktop)</span><span class="sxs-lookup"><span data-stu-id="ea317-104">Microsoft Edge User Agent String (Desktop)</span></span>  

<span data-ttu-id="ea317-105">A user agent \(UA\) string is able to be used to detect what version of a specific browser is being used on a certain operating system.</span><span class="sxs-lookup"><span data-stu-id="ea317-105">A user agent \(UA\) string is able to be used to detect what version of a specific browser is being used on a certain operating system.</span></span>  <span data-ttu-id="ea317-106">Like other browsers, Microsoft Edge includes this information in the `User-Agent` HTTP header whenever it makes a request to a site.</span><span class="sxs-lookup"><span data-stu-id="ea317-106">Like other browsers, Microsoft Edge includes this information in the `User-Agent` HTTP header whenever it makes a request to a site.</span></span>  <span data-ttu-id="ea317-107">It may also be accessed via JavaScript by querying the value of `navigator.userAgent`.</span><span class="sxs-lookup"><span data-stu-id="ea317-107">It may also be accessed via JavaScript by querying the value of `navigator.userAgent`.</span></span>  

<span data-ttu-id="ea317-108">Microsoft recommends that web developers make use of [feature detection](https://developer.mozilla.org/docs/Learn/Tools_and_testing/Cross_browser_testing/Feature_detection) whenever possible to improve code maintainability, reduce code fragility, and eliminate the risk of code breakage in the event of future UA string updates.</span><span class="sxs-lookup"><span data-stu-id="ea317-108">Microsoft recommends that web developers make use of [feature detection](https://developer.mozilla.org/docs/Learn/Tools_and_testing/Cross_browser_testing/Feature_detection) whenever possible to improve code maintainability, reduce code fragility, and eliminate the risk of code breakage in the event of future UA string updates.</span></span>  

<span data-ttu-id="ea317-109">For cases where feature detection is not applicable and UA detection must be used, the format of the Microsoft Edge UA on desktop is as follows:</span><span class="sxs-lookup"><span data-stu-id="ea317-109">For cases where feature detection is not applicable and UA detection must be used, the format of the Microsoft Edge UA on desktop is as follows:</span></span>

<span data-ttu-id="ea317-110">The `User-Agent` request header is in the following format:</span><span class="sxs-lookup"><span data-stu-id="ea317-110">The `User-Agent` request header is in the following format:</span></span>

```http
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/79.0.3945.74 Safari/537.36 Edg/79.0.309.43
``` 

<span data-ttu-id="ea317-111">The return value from `navigator.userAgent` is in the following format:</span><span class="sxs-lookup"><span data-stu-id="ea317-111">The return value from `navigator.userAgent` is in the following format:</span></span>

```javascript
"Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/79.0.3945.74 Safari/537.36 Edg/79.0.309.43"
```  

<span data-ttu-id="ea317-112">Platform identifiers change based on the operating system being used, and version numbers also increment as time passes.</span><span class="sxs-lookup"><span data-stu-id="ea317-112">Platform identifiers change based on the operating system being used, and version numbers also increment as time passes.</span></span>  <span data-ttu-id="ea317-113">This format is the same as the Chromium UA with the addition of a new `Edg` token at the end.</span><span class="sxs-lookup"><span data-stu-id="ea317-113">This format is the same as the Chromium UA with the addition of a new `Edg` token at the end.</span></span>  <span data-ttu-id="ea317-114">Microsoft selected the `Edg` token to avoid compatibility issues that may be caused by using the string `Edge`, which is used by the version of Microsoft Edge based on EdgeHTML.</span><span class="sxs-lookup"><span data-stu-id="ea317-114">Microsoft selected the `Edg` token to avoid compatibility issues that may be caused by using the string `Edge`, which is used by the version of Microsoft Edge based on EdgeHTML.</span></span>  <span data-ttu-id="ea317-115">The `Edg` token is also consistent with [existing tokens](https://blogs.windows.com/msedgedev/2017/10/05/microsoft-edge-ios-android-developer/) used on iOS and Android.</span><span class="sxs-lookup"><span data-stu-id="ea317-115">The `Edg` token is also consistent with [existing tokens](https://blogs.windows.com/msedgedev/2017/10/05/microsoft-edge-ios-android-developer/) used on iOS and Android.</span></span>

## <span data-ttu-id="ea317-116">Mapping UA String to Browser Name</span><span class="sxs-lookup"><span data-stu-id="ea317-116">Mapping UA String to Browser Name</span></span>
<span data-ttu-id="ea317-117">Mapping UA string tokens to a more human-readable browser name for use in code is a common pattern on the web today.</span><span class="sxs-lookup"><span data-stu-id="ea317-117">Mapping UA string tokens to a more human-readable browser name for use in code is a common pattern on the web today.</span></span> <span data-ttu-id="ea317-118">When mapping the new `Edg` token to a browser name, Microsoft recommends using a different name than the one developers used for the legacy version of Microsoft Edge to avoid accidentally applying any legacy workarounds that are not applicable to Chromium-based browsers.</span><span class="sxs-lookup"><span data-stu-id="ea317-118">When mapping the new `Edg` token to a browser name, Microsoft recommends using a different name than the one developers used for the legacy version of Microsoft Edge to avoid accidentally applying any legacy workarounds that are not applicable to Chromium-based browsers.</span></span>

## <span data-ttu-id="ea317-119">User Agent Overrides</span><span class="sxs-lookup"><span data-stu-id="ea317-119">User Agent Overrides</span></span>  

<span data-ttu-id="ea317-120">Sometimes, a website does not recognize the updated version of the Microsoft Edge UA.</span><span class="sxs-lookup"><span data-stu-id="ea317-120">Sometimes, a website does not recognize the updated version of the Microsoft Edge UA.</span></span>  <span data-ttu-id="ea317-121">As a result, a set of the features of that website may not work correctly.</span><span class="sxs-lookup"><span data-stu-id="ea317-121">As a result, a set of the features of that website may not work correctly.</span></span>  <span data-ttu-id="ea317-122">When Microsoft is notified about these types of issues, website owners are contacted and informed about the updated UA.</span><span class="sxs-lookup"><span data-stu-id="ea317-122">When Microsoft is notified about these types of issues, website owners are contacted and informed about the updated UA.</span></span>  

<span data-ttu-id="ea317-123">The sites often need some time to update and test the UA detection logic to address the issues that Microsoft reports to site owners.</span><span class="sxs-lookup"><span data-stu-id="ea317-123">The sites often need some time to update and test the UA detection logic to address the issues that Microsoft reports to site owners.</span></span>  <span data-ttu-id="ea317-124">In these cases, Microsoft uses a list of UA overrides in our Beta and Stable channels to maximize compatibility for users who access these sites.</span><span class="sxs-lookup"><span data-stu-id="ea317-124">In these cases, Microsoft uses a list of UA overrides in our Beta and Stable channels to maximize compatibility for users who access these sites.</span></span>  <span data-ttu-id="ea317-125">The overrides specify new UA values that Microsoft Edge should send instead of the default UA for specific sites.</span><span class="sxs-lookup"><span data-stu-id="ea317-125">The overrides specify new UA values that Microsoft Edge should send instead of the default UA for specific sites.</span></span>  <span data-ttu-id="ea317-126">You are able to view the list of UA overrides that are currently being applied by navigating to `edge://compat/useragent` in the Beta and Stable channels of Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="ea317-126">You are able to view the list of UA overrides that are currently being applied by navigating to `edge://compat/useragent` in the Beta and Stable channels of Microsoft Edge.</span></span> 

<span data-ttu-id="ea317-127">Our Canary and Dev channels do not currently receive UA overrides so that web developers have an environment where they can easily reproduce issues on their sites that are caused by the default Microsoft Edge UA.</span><span class="sxs-lookup"><span data-stu-id="ea317-127">Our Canary and Dev channels do not currently receive UA overrides so that web developers have an environment where they can easily reproduce issues on their sites that are caused by the default Microsoft Edge UA.</span></span>  <span data-ttu-id="ea317-128">If for some reason you require the ability to disable UA overrides in the Beta or Stable channels of Microsoft Edge, you may run the Microsoft Edge executable using the following command line argument:</span><span class="sxs-lookup"><span data-stu-id="ea317-128">If for some reason you require the ability to disable UA overrides in the Beta or Stable channels of Microsoft Edge, you may run the Microsoft Edge executable using the following command line argument:</span></span>  

```shell
--disable-domain-action-user-agent-override
```  
