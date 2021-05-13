---
description: 了解如何将扩展从清单 V2 更新到 V3
title: 准备将扩展从清单 V2 更新到 V3
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium， 扩展开发， 边缘扩展， 浏览器扩展， 加载项， 开发人员， 清单 v3， 迁移到清单 v3
ms.openlocfilehash: 5aa1aa7446a312d581bacc4fa19ba7362c6c2a3e
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564614"
---
# <a name="prepare-to-update-your-extensions-from-manifest-v2-to-v3"></a><span data-ttu-id="1b2d1-104">准备将扩展从清单 v2 更新到 v3</span><span class="sxs-lookup"><span data-stu-id="1b2d1-104">Prepare to update your extensions from Manifest v2 to v3</span></span>  

<span data-ttu-id="1b2d1-105">本文档列出了作为清单 v3 的一部分实现的重要更改，清单 v3 是下一版本的 Chromium 扩展平台。</span><span class="sxs-lookup"><span data-stu-id="1b2d1-105">This document lists important changes being implemented as part of Manifest v3, which is the next version of the Chromium Extensions platform.</span></span>  <span data-ttu-id="1b2d1-106">应用Microsoft Edge团队将随着实现进度更新此文档。</span><span class="sxs-lookup"><span data-stu-id="1b2d1-106">The Microsoft Edge extensions team updates this document as the implementation progresses.</span></span>  <span data-ttu-id="1b2d1-107">有关将扩展迁移到清单 v3 的详细指南，请导航到"迁移到清单[V3"。][ChromeDeveloperDocsExtensionsMv3Mv3MigrationChecklist]</span><span class="sxs-lookup"><span data-stu-id="1b2d1-107">For detailed guidance on migrating your extension to Manifest v3, navigate to [Migrating to Manifest V3][ChromeDeveloperDocsExtensionsMv3Mv3MigrationChecklist].</span></span>  

## <a name="remotely-hosted-code"></a><span data-ttu-id="1b2d1-108">远程托管的代码</span><span class="sxs-lookup"><span data-stu-id="1b2d1-108">Remotely hosted code</span></span>  

<span data-ttu-id="1b2d1-109">目前，扩展代码的某些部分是远程托管的，并且不会在验证过程中作为扩展包的一部分包含。</span><span class="sxs-lookup"><span data-stu-id="1b2d1-109">Today, parts of the extensions code is hosted remotely, and not include it as part of the extension package during the validation process.</span></span>  <span data-ttu-id="1b2d1-110">虽然这样可以在不将扩展重新提交到存储区的情况下灵活更改代码，但代码在安装后可能会受到攻击。</span><span class="sxs-lookup"><span data-stu-id="1b2d1-110">While this offers flexibility to change code without resubmitting the extension to the store, the code may be exploited after installation.</span></span>  <span data-ttu-id="1b2d1-111">为了确保[Microsoft Edge加载项][MicrosoftMicrosoftedgeAddons]列出经过验证的扩展，Microsoft Edge团队禁止扩展使用远程托管的代码。</span><span class="sxs-lookup"><span data-stu-id="1b2d1-111">To ensure [Microsoft Edge Add-ons][MicrosoftMicrosoftedgeAddons] lists validated extensions, the Microsoft Edge extensions team disallows extensions from using remotely hosted code.</span></span>  <span data-ttu-id="1b2d1-112">此更改使扩展更安全。</span><span class="sxs-lookup"><span data-stu-id="1b2d1-112">This change makes extensions more secure.</span></span>  <span data-ttu-id="1b2d1-113">开发人员将需要打包并提交扩展使用的所有代码进行验证。</span><span class="sxs-lookup"><span data-stu-id="1b2d1-113">Developers will need to package and submit all code used by the extension for validation.</span></span>  <span data-ttu-id="1b2d1-114">或者，您可以在沙盒 `eval()` 环境中使用 [函数][ChromeDeveloperDocsExtensionsMv2Sandboxingeval]。</span><span class="sxs-lookup"><span data-stu-id="1b2d1-114">Alternatively, you may use the `eval()` function in a [sandboxed environment][ChromeDeveloperDocsExtensionsMv2Sandboxingeval].</span></span>  

## <a name="run-time-host-permissions"></a><span data-ttu-id="1b2d1-115">运行时主机权限</span><span class="sxs-lookup"><span data-stu-id="1b2d1-115">Run-time host permissions</span></span>  

<span data-ttu-id="1b2d1-116">在安装时，扩展可能会请求访问所有网站和内容所需的权限。</span><span class="sxs-lookup"><span data-stu-id="1b2d1-116">At installation time, extensions may request blanket permissions to access all sites and content.</span></span>  <span data-ttu-id="1b2d1-117">这些权限允许扩展在最小干预下运行，并给用户隐私和安全性带来风险。</span><span class="sxs-lookup"><span data-stu-id="1b2d1-117">These permissions allow extensions to operate with minimum intervention, and create a risk to user privacy and security.</span></span>  <span data-ttu-id="1b2d1-118">为了提高透明度，Microsoft Edge扩展团队为用户提供了一些控件，以允许或限制在运行时访问网站。</span><span class="sxs-lookup"><span data-stu-id="1b2d1-118">To improve transparency, the Microsoft Edge extensions team provides controls for users to allow or restrict access to websites at runtime.</span></span>  

## <a name="cross-origin-requests-in-content-scripts"></a><span data-ttu-id="1b2d1-119">内容脚本中的跨源请求</span><span class="sxs-lookup"><span data-stu-id="1b2d1-119">Cross-origin requests in content scripts</span></span>  

<span data-ttu-id="1b2d1-120">现在，内容脚本请求访问任何源，包括网站不允许的源。</span><span class="sxs-lookup"><span data-stu-id="1b2d1-120">Today, content scripts request access to any origin including origins that aren't allowed by the website.</span></span>  <span data-ttu-id="1b2d1-121">该行为会破坏跨来源原则。</span><span class="sxs-lookup"><span data-stu-id="1b2d1-121">The behavior breaks cross-origin principles.</span></span>  <span data-ttu-id="1b2d1-122">今后，Microsoft Edge扩展团队需要内容脚本具有与注入脚本的网页相同的权限，从而关闭潜在的安全隐患。</span><span class="sxs-lookup"><span data-stu-id="1b2d1-122">Going forward, the Microsoft Edge extensions team requires content scripts to have the same permissions as the webpage into which the scripts are injected, closing a potential security loophole.</span></span>  <span data-ttu-id="1b2d1-123">若要执行跨源请求，你需要使用后台脚本将响应中继回内容脚本。</span><span class="sxs-lookup"><span data-stu-id="1b2d1-123">To perform cross-origin requests, you need to use background scripts to relay responses back to content scripts.</span></span>  <span data-ttu-id="1b2d1-124">这些更改在标志后面可用。</span><span class="sxs-lookup"><span data-stu-id="1b2d1-124">These changes are available and behind a flag.</span></span>  <span data-ttu-id="1b2d1-125">有关详细信息，请导航到此 [文档][ChromiumHomeChromiumSecurityExtensionContentScriptFetches]。</span><span class="sxs-lookup"><span data-stu-id="1b2d1-125">For more information, navigate to this [document][ChromiumHomeChromiumSecurityExtensionContentScriptFetches].</span></span>  

## <a name="web-request-api"></a><span data-ttu-id="1b2d1-126">Web 请求 API</span><span class="sxs-lookup"><span data-stu-id="1b2d1-126">Web Request API</span></span>  

<span data-ttu-id="1b2d1-127">扩展Microsoft Edge团队将 Web 请求[API][ChromeDeveloperDocsExtensionsReferenceWebrequest]替换为声明性 Net[请求 API，][ChromeDeveloperDocsExtensionsReferenceDeclarativenetrequest]但继续保留 Web 请求 API 的观察功能。</span><span class="sxs-lookup"><span data-stu-id="1b2d1-127">The Microsoft Edge extensions team replaces [Web Request API][ChromeDeveloperDocsExtensionsReferenceWebrequest] with [Declarative Net Request API][ChromeDeveloperDocsExtensionsReferenceDeclarativenetrequest], but continues to keep the observational capabilities of the Web Request API.</span></span>  <span data-ttu-id="1b2d1-128">除了扩展需要 Web 请求 API 的观察功能的一些特定情况之外，Microsoft Edge 扩展团队建议仅使用 DNR API。</span><span class="sxs-lookup"><span data-stu-id="1b2d1-128">Except in some specific scenarios where observational capabilities of the Web Request API are required by the extension, the Microsoft Edge extensions team recommends using the DNR APIs only.</span></span>  <span data-ttu-id="1b2d1-129">扩展Microsoft Edge团队认为此更改将对使用功能丰富的声明功能的扩展产生积极的影响。</span><span class="sxs-lookup"><span data-stu-id="1b2d1-129">The Microsoft Edge extensions team believes this change will have positive impact on extensions that use feature-rich declarative capabilities.</span></span>  <span data-ttu-id="1b2d1-130">随着更多扩展过渡到 DNR API，此更改将改进用户隐私，这有助于增强使用扩展的信任。</span><span class="sxs-lookup"><span data-stu-id="1b2d1-130">As more extensions transition to the DNR APIs, this change will improve user privacy, which contributes to enhancing trust in the use of extensions.</span></span>  
<span data-ttu-id="1b2d1-131">对于通过企业策略管理的扩展，企业可能会继续使用 Web 请求 API 的阻止行为。</span><span class="sxs-lookup"><span data-stu-id="1b2d1-131">Enterprises may continue to use the blocking behavior of the Web Request API for extensions managed through enterprise policies.</span></span>  <span data-ttu-id="1b2d1-132">有关扩展策略详细信息，请导航到"Microsoft Edge [– 策略"。][DeployedgeMicrosoftEdgePoliciesExtensions]</span><span class="sxs-lookup"><span data-stu-id="1b2d1-132">For more information about extension policies, navigate to [Microsoft Edge – Policies][DeployedgeMicrosoftEdgePoliciesExtensions].</span></span>  

## <a name="background-service-workers"></a><span data-ttu-id="1b2d1-133">后台服务工作者</span><span class="sxs-lookup"><span data-stu-id="1b2d1-133">Background service workers</span></span>  
 
<span data-ttu-id="1b2d1-134">服务工作人员可在 Canary 中进行测试。</span><span class="sxs-lookup"><span data-stu-id="1b2d1-134">Service workers are available for testing in Canary.</span></span>  <span data-ttu-id="1b2d1-135">若要将扩展从后台页面迁移到服务工作者，请参阅从后台页面 [迁移到服务工作者][ChromeDeveloperDocsExtensionsMv3MigratingToServiceWorkers]。</span><span class="sxs-lookup"><span data-stu-id="1b2d1-135">To migrate your extensions from background pages to service workers, refer to [Migrating from Background Pages to Service Workers][ChromeDeveloperDocsExtensionsMv3MigratingToServiceWorkers].</span></span>  <span data-ttu-id="1b2d1-136">开发人员Microsoft Edge团队正在评估并调查此更改对开发人员和用户的影响。</span><span class="sxs-lookup"><span data-stu-id="1b2d1-136">The Microsoft Edge extensions team is evaluating and investigating the impact that this change brings to both developers and users.</span></span>  <span data-ttu-id="1b2d1-137">Microsoft Edge扩展团队将来会向此文档添加有关更改的其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="1b2d1-137">The Microsoft Edge extensions team adds additional details on the change to this document in the future.</span></span>  

## <a name="when-are-these-changes-available-in-microsoft-edge"></a><span data-ttu-id="1b2d1-138">这些更改何时在Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="1b2d1-138">When are these changes available in Microsoft Edge</span></span>  

<span data-ttu-id="1b2d1-139">我们的 Stable 和 Beta 渠道中提供了当前声明性 Net 请求 API 实现。</span><span class="sxs-lookup"><span data-stu-id="1b2d1-139">The current declarative net request API implementation is available in our Stable and Beta channels.</span></span>  <span data-ttu-id="1b2d1-140">测试更改并提供反馈。</span><span class="sxs-lookup"><span data-stu-id="1b2d1-140">Test the changes, and provide feedback.</span></span>  <span data-ttu-id="1b2d1-141">扩展Microsoft Edge团队参与开发工作并调查进一步的更改。</span><span class="sxs-lookup"><span data-stu-id="1b2d1-141">The Microsoft Edge extensions team contributes to development efforts and investigate further changes.</span></span>  

| <span data-ttu-id="1b2d1-142">频道名称</span><span class="sxs-lookup"><span data-stu-id="1b2d1-142">Channel name</span></span> | <span data-ttu-id="1b2d1-143">详细信息</span><span class="sxs-lookup"><span data-stu-id="1b2d1-143">Details</span></span> |  
|:--- |:--- |  
| <span data-ttu-id="1b2d1-144">Microsoft Edge 84 Stable</span><span class="sxs-lookup"><span data-stu-id="1b2d1-144">Microsoft Edge 84 Stable</span></span> | <span data-ttu-id="1b2d1-145">DNR API 可用于测试</span><span class="sxs-lookup"><span data-stu-id="1b2d1-145">DNR API is available for testing</span></span> |  
| <span data-ttu-id="1b2d1-146">Microsoft Edge 85 Beta</span><span class="sxs-lookup"><span data-stu-id="1b2d1-146">Microsoft Edge 85 Beta</span></span> | <span data-ttu-id="1b2d1-147">提供标头修改支持</span><span class="sxs-lookup"><span data-stu-id="1b2d1-147">Header modification support is available</span></span>|  

<span data-ttu-id="1b2d1-148">当对应用商店Chromium时，Microsoft Edge扩展团队将共享日程表，以便你可以更新代码并重新向应用商店发布扩展。</span><span class="sxs-lookup"><span data-stu-id="1b2d1-148">When the changes are made to Chromium, the Microsoft Edge extensions team shares timelines so that you may update your code and republish extensions to the store.</span></span>  

<span data-ttu-id="1b2d1-149">Microsoft Edge扩展团队继续发布博客上的更新。</span><span class="sxs-lookup"><span data-stu-id="1b2d1-149">The Microsoft Edge extensions team continues publishing updates on the blog.</span></span>  <span data-ttu-id="1b2d1-150">可以通过 Tech Community[提供有关更改的反馈][MicrosoftTechcommunityT5ArticlesManifestV3ChnagesAreNowAvailableInMicrosoftEdgeMP1780254]。</span><span class="sxs-lookup"><span data-stu-id="1b2d1-150">You may provide your feedback on the changes through [Tech Community][MicrosoftTechcommunityT5ArticlesManifestV3ChnagesAreNowAvailableInMicrosoftEdgeMP1780254].</span></span>

<!-- links -->  

[DeployedgeMicrosoftEdgePoliciesExtensions]: /deployedge/microsoft-edge-policies#extensions "扩展 - Microsoft Edge - 策略|Microsoft Docs"  

[MicrosoftMicrosoftedgeAddons]: https://microsoftedge.microsoft.com/addons "Microsoft Edge 加载项"  

[MicrosoftTechcommunityT5ArticlesManifestV3ChnagesAreNowAvailableInMicrosoftEdgeMP1780254]: https://techcommunity.microsoft.com/t5/articles/manifest-v3-changes-are-now-available-in-microsoft-edge/m-p/1780254 "清单 V3 更改现已在 Microsoft Edge |Microsoft 技术Community"  

[ChromeDeveloperDocsExtensionsMv2Sandboxingeval]: https://developer.chrome.com/docs/extensions/mv2/sandboxingEval "在 Chrome 扩展中使用 eval |Chrome 开发人员"  
[ChromeDeveloperDocsExtensionsMv3MigratingToServiceWorkers]:  https://developer.chrome.com/docs/extensions/mv3/migrating_to_service_workers "从后台页面迁移到服务工作者|Chrome 开发人员"  
[ChromeDeveloperDocsExtensionsMv3Mv3MigrationChecklist]: https://developer.chrome.com/docs/extensions/mv3/mv3-migration-checklist "清单 V3 迁移清单|Chrome 开发人员"    

[ChromeDeveloperDocsExtensionsReferenceDeclarativenetrequest]: https://developer.chrome.com/docs/extensions/reference/declarativeNetRequest "chrome.declarativeNetRequest |Chrome 开发人员"  
[ChromeDeveloperDocsExtensionsReferenceWebrequest]: https://developer.chrome.com/docs/extensions/reference/webRequest "chrome.webRequest |Chrome 开发人员"  

[ChromiumHomeChromiumSecurityExtensionContentScriptFetches]: https://www.chromium.org/Home/chromium-security/extension-content-script-fetches "对 Chrome 扩展内容脚本中跨源请求的更改|项目Chromium"  
