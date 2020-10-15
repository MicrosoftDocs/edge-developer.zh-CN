---
description: 了解如何将扩展从清单 V2 更新到 V3
title: 准备将你的扩展从清单 V2 更新到 V3
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/13/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium，扩展开发，边缘扩展，浏览器扩展，addons，开发人员，清单 v3，迁移到清单 v3
ms.openlocfilehash: 262a5cab54dd23f596791c93ec1238619e247333
ms.sourcegitcommit: 1ad087b00df16fd7718a5d95226de57e29b335e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/14/2020
ms.locfileid: "11117825"
---
# <span data-ttu-id="ff02d-104">准备将你的扩展从清单 v2 更新到 v3</span><span class="sxs-lookup"><span data-stu-id="ff02d-104">Prepare to update your extensions from Manifest v2 to v3</span></span> 

<span data-ttu-id="ff02d-105">本文档列出了作为清单 v3 的一部分实现的重要更改，这是 Chromium 扩展平台的下一个版本。</span><span class="sxs-lookup"><span data-stu-id="ff02d-105">This document lists important changes that's being implemented as part of Manifest v3, which is the next version of the Chromium Extensions platform.</span></span> <span data-ttu-id="ff02d-106">我们将在实施过程中更新此文档。</span><span class="sxs-lookup"><span data-stu-id="ff02d-106">We'll update this document as the implementation progresses.</span></span> <span data-ttu-id="ff02d-107">有关将扩展迁移到清单 v3 的详细指南，请导航到 [清单 V3 迁移][Google_Migrate_to_MV3]。</span><span class="sxs-lookup"><span data-stu-id="ff02d-107">For detailed guidance on migrating your extension to Manifest v3, navigate to [Migrating to Manifest V3][Google_Migrate_to_MV3].</span></span> 

## <span data-ttu-id="ff02d-108">远程托管代码</span><span class="sxs-lookup"><span data-stu-id="ff02d-108">Remotely hosted code</span></span>  

<span data-ttu-id="ff02d-109">如今，扩展可以远程托管其代码的一部分，并且在验证过程中不将其包含在扩展程序包中。</span><span class="sxs-lookup"><span data-stu-id="ff02d-109">Today, extensions can host parts of their code remotely, and not include it as part of the extension package during the validation process.</span></span> <span data-ttu-id="ff02d-110">虽然这提供了在不重新提交对应用商店的扩展的情况下更改代码的灵活性，但在安装后可以利用该代码。</span><span class="sxs-lookup"><span data-stu-id="ff02d-110">While this offers flexibility to change code without resubmitting the extension to the store, the code can be exploited after installation.</span></span> <span data-ttu-id="ff02d-111">为了确保 [Microsoft Edge 加载项][EdgeAddons] 列出已验证的扩展，我们禁止扩展使用远程托管的代码。</span><span class="sxs-lookup"><span data-stu-id="ff02d-111">To ensure [Microsoft Edge Add-ons][EdgeAddons] lists validated extensions, we're disallowing extensions from using remotely hosted code.</span></span> <span data-ttu-id="ff02d-112">此更改使扩展更安全。</span><span class="sxs-lookup"><span data-stu-id="ff02d-112">This change makes extensions more secure.</span></span> <span data-ttu-id="ff02d-113">开发人员将需要打包和提交扩展所使用的所有代码以进行验证。</span><span class="sxs-lookup"><span data-stu-id="ff02d-113">Developers will need to package and submit all code that's used by the extension for validation.</span></span> <span data-ttu-id="ff02d-114">或者，开发人员可以在 [沙盒环境][sandboxingEval]中使用 eval ( # A1 函数。</span><span class="sxs-lookup"><span data-stu-id="ff02d-114">Alternatively, developers can use the eval() function in a [sandboxed environment][sandboxingEval].</span></span> 

## <span data-ttu-id="ff02d-115">运行时主机权限</span><span class="sxs-lookup"><span data-stu-id="ff02d-115">Run-time host permissions</span></span>  

<span data-ttu-id="ff02d-116">在安装时，扩展可能会请求访问所有网站和内容的总权限。</span><span class="sxs-lookup"><span data-stu-id="ff02d-116">At installation time, extensions may request blanket permissions to access all sites and content.</span></span> <span data-ttu-id="ff02d-117">这些权限允许扩展以最小的干预进行操作，并为用户隐私和安全带来风险。</span><span class="sxs-lookup"><span data-stu-id="ff02d-117">These permissions allow extensions to operate with minimum intervention, and create a risk to user privacy and security.</span></span> <span data-ttu-id="ff02d-118">为提高透明度，我们为用户提供了在运行时允许或限制访问网站的控件。</span><span class="sxs-lookup"><span data-stu-id="ff02d-118">To improve transparency, we're providing controls for users to allow or restrict access to websites at runtime.</span></span> 

## <span data-ttu-id="ff02d-119">内容脚本中的跨源请求</span><span class="sxs-lookup"><span data-stu-id="ff02d-119">Cross-origin requests in content scripts</span></span>  

<span data-ttu-id="ff02d-120">"今日内容脚本" 可以请求对任何来源（包括网站不允许的来源）的访问权限。</span><span class="sxs-lookup"><span data-stu-id="ff02d-120">Today content scripts can request access to any origin including origins that aren't allowed by the website.</span></span> <span data-ttu-id="ff02d-121">此行为中断了交叉起源原则。</span><span class="sxs-lookup"><span data-stu-id="ff02d-121">This behavior breaks cross-origin principles.</span></span> <span data-ttu-id="ff02d-122">接下来，我们将要求内容脚本拥有与它们所注入的页面相同的权限，从而关闭潜在的安全 loophole。</span><span class="sxs-lookup"><span data-stu-id="ff02d-122">Going forward, we'll require content scripts to have the same permissions as the page they're injected into, closing a potential security loophole.</span></span> <span data-ttu-id="ff02d-123">若要执行跨源请求，你需要使用后台脚本将回复中继回内容脚本。</span><span class="sxs-lookup"><span data-stu-id="ff02d-123">To perform cross-origin requests, you'll need to use background scripts to relay responses back to content scripts.</span></span> <span data-ttu-id="ff02d-124">这些更改可在标志之后使用。</span><span class="sxs-lookup"><span data-stu-id="ff02d-124">These changes are available and behind a flag.</span></span> <span data-ttu-id="ff02d-125">有关详细信息，请导航到 "此 [文档][CORS]"。</span><span class="sxs-lookup"><span data-stu-id="ff02d-125">For more information, navigate to this [document][CORS].</span></span> 

## <span data-ttu-id="ff02d-126">Web 请求 API</span><span class="sxs-lookup"><span data-stu-id="ff02d-126">Web Request API</span></span>  

<span data-ttu-id="ff02d-127">我们正在将 [Web 请求 api][WebRequestAPI] 替换为 [声明性 Net Request api][DeclarativeNetRequestAPI]，但将继续保持 web 请求 api 的见习功能。</span><span class="sxs-lookup"><span data-stu-id="ff02d-127">We're replacing [Web Request API][WebRequestAPI] with [Declarative Net Request API][DeclarativeNetRequestAPI], but will continue to keep Web Request API's observational capabilities.</span></span> <span data-ttu-id="ff02d-128">除了在某些特定情况下，扩展需要 Web 请求 API 的见习功能，我们建议仅使用 DNR Api。</span><span class="sxs-lookup"><span data-stu-id="ff02d-128">Except in some specific scenarios where observational capabilities of the Web Request API are required by the extension, we recommend using the DNR APIs only.</span></span> <span data-ttu-id="ff02d-129">我们认为，此更改将对使用功能丰富的声明性功能的扩展产生积极影响。</span><span class="sxs-lookup"><span data-stu-id="ff02d-129">We believe this change will have positive impact on extensions that use feature-rich declarative capabilities.</span></span> <span data-ttu-id="ff02d-130">随着更多扩展转换为 DNR Api，此更改将改进用户隐私，这有助于增强对使用扩展的信任。</span><span class="sxs-lookup"><span data-stu-id="ff02d-130">As more extensions transition to the DNR APIs, this change will improve user privacy, which contributes to enhancing trust in the use of extensions.</span></span>
<span data-ttu-id="ff02d-131">企业可以继续对通过企业策略管理的扩展使用 Web 请求 API 的阻止行为。</span><span class="sxs-lookup"><span data-stu-id="ff02d-131">Enterprises can continue to use the blocking behavior of the Web Request API for extensions managed through enterprise policies.</span></span> <span data-ttu-id="ff02d-132">有关扩展策略的详细信息，请导航到 [Microsoft Edge-"策略][MicrosoftEdgePolicies]"。</span><span class="sxs-lookup"><span data-stu-id="ff02d-132">For more information about extension policies, navigate to [Microsoft Edge – Policies][MicrosoftEdgePolicies].</span></span> 

## <span data-ttu-id="ff02d-133">后台服务工作人员</span><span class="sxs-lookup"><span data-stu-id="ff02d-133">Background service workers</span></span>  
 
<span data-ttu-id="ff02d-134">服务工作者可在未带里的测试中进行测试。</span><span class="sxs-lookup"><span data-stu-id="ff02d-134">Service workers are available for testing in Canary.</span></span> <span data-ttu-id="ff02d-135">若要将扩展从背景页迁移到服务工作人员，请参阅 [从背景页迁移到服务工作人员][ServiceWorkers]。</span><span class="sxs-lookup"><span data-stu-id="ff02d-135">To migrate your extensions from background pages to service workers, refer to [Migrating from Background Pages to Service Workers][ServiceWorkers].</span></span> <span data-ttu-id="ff02d-136">我们正在评估 & 调查此变更对开发人员和用户带来的影响。</span><span class="sxs-lookup"><span data-stu-id="ff02d-136">We're evaluating & investigating the impact that this change brings to both developers and users.</span></span> <span data-ttu-id="ff02d-137">我们将在以后对此文档的更改添加其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="ff02d-137">We'll add  additional details on this change to this document in the future.</span></span> 

## <span data-ttu-id="ff02d-138">这些更改将在 Microsoft Edge 中提供什么情况？</span><span class="sxs-lookup"><span data-stu-id="ff02d-138">When will these changes be available in Microsoft Edge?</span></span>

<span data-ttu-id="ff02d-139">当前的声明性 net request API 实现可在我们的稳定和 Beta 通道中使用。</span><span class="sxs-lookup"><span data-stu-id="ff02d-139">The current declarative net request API implementation is available in our Stable and Beta channels.</span></span> <span data-ttu-id="ff02d-140">开发人员可以测试这些更改，并提供反馈。</span><span class="sxs-lookup"><span data-stu-id="ff02d-140">Developers can test these changes, and provide feedback.</span></span> <span data-ttu-id="ff02d-141">我们将参与开发工作，并调查进一步的更改。</span><span class="sxs-lookup"><span data-stu-id="ff02d-141">We'll contribute to development efforts and investigate further changes.</span></span> 

| <span data-ttu-id="ff02d-142">频道名称</span><span class="sxs-lookup"><span data-stu-id="ff02d-142">Channel name</span></span> | <span data-ttu-id="ff02d-143">描述</span><span class="sxs-lookup"><span data-stu-id="ff02d-143">Description</span></span> |
|:--- |:--- |  
| <span data-ttu-id="ff02d-144">Microsoft Edge 84 稳定</span><span class="sxs-lookup"><span data-stu-id="ff02d-144">Microsoft Edge 84 Stable</span></span> | <span data-ttu-id="ff02d-145">DNR API 可用于测试</span><span class="sxs-lookup"><span data-stu-id="ff02d-145">DNR API is available for testing</span></span> |  
| <span data-ttu-id="ff02d-146">Microsoft Edge 85 Beta</span><span class="sxs-lookup"><span data-stu-id="ff02d-146">Microsoft Edge 85 Beta</span></span> | <span data-ttu-id="ff02d-147">标题修改支持可用</span><span class="sxs-lookup"><span data-stu-id="ff02d-147">Header modification support is available</span></span>| 

<span data-ttu-id="ff02d-148">对 Chromium 进行更改后，我们将共享时间线，以便开发人员可以更新其代码并将扩展重新发布到应用商店。</span><span class="sxs-lookup"><span data-stu-id="ff02d-148">When the changes are made to Chromium, we'll share timelines so that developers can update their code and republish extensions to the store.</span></span> 

<span data-ttu-id="ff02d-149">我们将继续发布博客上的更新。</span><span class="sxs-lookup"><span data-stu-id="ff02d-149">We'll continue publishing updates on our blog.</span></span> <span data-ttu-id="ff02d-150">你可以通过 [TechCommunity][TechCommunity]提供有关这些更改的反馈。</span><span class="sxs-lookup"><span data-stu-id="ff02d-150">You can provide your feedback on these changes through [TechCommunity][TechCommunity].</span></span>

<!-- links -->  

[EdgeAddons]: https://microsoftedge.microsoft.com/addons/ "Microsoft Edge 加载项"  
[MicrosoftBlog]: https://blogs.windows.com/windowsexperience/2018/12/06/microsoft-edge-making-the-web-better-through-more-open-source-collaboration/  
[MicrosoftEdgePolicies]: https://docs.microsoft.com/deployedge/microsoft-edge-policies#extensions 

[TechCommunity]: https://techcommunity.microsoft.com/t5/articles/manifest-v3-changes-are-now-available-in-microsoft-edge/m-p/1780254 "技术社区"  


[Google_Migrate_to_MV3]: https://developer.chrome.com/extensions/migrating_to_manifest_v3   
[SandboxingEval]: https://developer.chrome.com/apps/sandboxingEval "在 Chrome 扩展中使用 eval。放心."
[CORS]: https://www.chromium.org/Home/chromium-security/extension-content-script-fetches "扩展内容脚本中的跨原始请求的更改"
[WebRequestAPI]: https://developer.chrome.com/extensions/webRequest "Web 请求 API"  
[DeclarativeNetRequestAPI]: https://developer.chrome.com/extensions/declarativeNetRequest/ "声明性 Net 请求 API"
[ServiceWorkers]:  https://developers.chrome.com/extensions/migrating_to_service_workers


