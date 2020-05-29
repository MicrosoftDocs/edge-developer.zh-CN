---
description: 向 Microsoft Store 发布 Edge （Chromium）扩展的循序渐进过程。
title: 发布扩展
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/21/2020
ms.topic: article
ms.prod: microsoft-edge-chromium
keywords: edge-chromium、扩展开发、浏览器扩展、addons、合作伙伴中心、开发人员
ms.openlocfilehash: 7b5be511af1e81efd5da4fc4bc0691f317437f94
ms.sourcegitcommit: 531ec8aa1f89b28bc4d271e8e995f846f2392bc3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/29/2020
ms.locfileid: "10607375"
---
# <span data-ttu-id="48325-104">发布扩展</span><span class="sxs-lookup"><span data-stu-id="48325-104">Publish An Extension</span></span>  

<span data-ttu-id="48325-105">在 Microsoft Edge Addons 目录 \ （Microsoft Edge Addons \）中发布您的扩展。</span><span class="sxs-lookup"><span data-stu-id="48325-105">Publish your Extension on Microsoft Edge Addons catalog \(Microsoft Edge Addons\).</span></span>  <span data-ttu-id="48325-106">您必须首先在[合作伙伴中心][MicrosoftPartnerCenter]创建提交并提交。</span><span class="sxs-lookup"><span data-stu-id="48325-106">You must first create a submission on [Partner Center][MicrosoftPartnerCenter] and submit it.</span></span>  <span data-ttu-id="48325-107">本文档列出了创建扩展提交时必须提供的所有详细信息。</span><span class="sxs-lookup"><span data-stu-id="48325-107">This document lists all the details that you must provide to create an Extension submission.</span></span>  

## <span data-ttu-id="48325-108">开始之前</span><span class="sxs-lookup"><span data-stu-id="48325-108">Before You Begin</span></span>  

*   <span data-ttu-id="48325-109">您必须在 "[合作伙伴中心][MicrosoftPartnerCenter]" 上拥有活动的开发人员帐户，才能在 Microsoft Edge Addons 中提交您的扩展。</span><span class="sxs-lookup"><span data-stu-id="48325-109">You must have an active developer account on [Partner Center][MicrosoftPartnerCenter] to submit your Extension in Microsoft Edge Addons.</span></span>  <span data-ttu-id="48325-110">如果没有，请[创建一个新的开发人员帐户][MicrosoftPartnerCenter]。</span><span class="sxs-lookup"><span data-stu-id="48325-110">If you do not have one, [create a new developer account][MicrosoftPartnerCenter].</span></span>  
*   <span data-ttu-id="48325-111">创建扩展程序包的 zip 文件，并确保它包含以下文件：</span><span class="sxs-lookup"><span data-stu-id="48325-111">Create a zip file of your Extension package and ensure that it contains these files:</span></span>  
    *   <span data-ttu-id="48325-112">清单文件，并且它必须定义您的扩展名的名称和版本。</span><span class="sxs-lookup"><span data-stu-id="48325-112">The manifest file and it must define the name and version of your Extension.</span></span>  
    *   <span data-ttu-id="48325-113">您的扩展所需的图像和其他文件。</span><span class="sxs-lookup"><span data-stu-id="48325-113">The images and other files that are required for your Extension.</span></span>  


<span data-ttu-id="48325-114">如果尚未开始构建扩展，则可以参阅构建 Microsoft Edge Chromium 扩展的[入门][ExtensionsGettingStarted]教程。</span><span class="sxs-lookup"><span data-stu-id="48325-114">If you have not started building an Extension, you may refer to the [Getting Started][ExtensionsGettingStarted] tutorial for building a Microsoft Edge Chromium extension.</span></span>  

<span data-ttu-id="48325-115">若要在[合作伙伴中心][MicrosoftPartnerCenter]创建扩展提交，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="48325-115">To create an Extension submission on [Partner Center][MicrosoftPartnerCenter], follow these steps.</span></span>  

## <span data-ttu-id="48325-116">步骤1：开始新提交</span><span class="sxs-lookup"><span data-stu-id="48325-116">Step 1: Start a New Submission</span></span>  

<span data-ttu-id="48325-117">转到[开发人员仪表板][MicrosoftPartnerCenter]。</span><span class="sxs-lookup"><span data-stu-id="48325-117">Go to your [developer dashboard][MicrosoftPartnerCenter].</span></span>  <span data-ttu-id="48325-118">在 "概述" 页上，单击 "**新建扩展名**"。</span><span class="sxs-lookup"><span data-stu-id="48325-118">From the Overview page, click **Create new extension**.</span></span>  

## <span data-ttu-id="48325-119">步骤2：上载扩展 Zip 文件</span><span class="sxs-lookup"><span data-stu-id="48325-119">Step 2: Upload Your Extension Zip File</span></span>  

<span data-ttu-id="48325-120">**程序包**页面是你为扩展提交上载 zip 文件的位置。</span><span class="sxs-lookup"><span data-stu-id="48325-120">The **Package** page is where you upload the zip file for your Extension submission.</span></span>  <span data-ttu-id="48325-121">你一次只能上载一个程序包，因此，如果你的扩展不完整，你可能会在发布工作包时随时上载工作包和更新。</span><span class="sxs-lookup"><span data-stu-id="48325-121">You may only upload one package at a time, so if your Extension is not complete you may upload a work-in-progress package and update at any time before you publish it.</span></span>  <span data-ttu-id="48325-122">请确保程序包中包含该 `manifest.json` 文件，并且在上载之前在 Microsoft Edge 上正常工作。</span><span class="sxs-lookup"><span data-stu-id="48325-122">Be sure that your package contains the `manifest.json` file and is working fine on Microsoft Edge prior to uploading.</span></span>  
<span data-ttu-id="48325-123">通过将程序包拖动到 "上载" 字段或选择 "**浏览文件**" 来上载程序包。</span><span class="sxs-lookup"><span data-stu-id="48325-123">Upload the package by dragging it into the upload field or by selecting **Browse your files**.</span></span>  <span data-ttu-id="48325-124">程序包页面验证扩展 zip 文件，并显示上载的**成功或失败状态**。</span><span class="sxs-lookup"><span data-stu-id="48325-124">The Package page validates the Extensions zip file and displays that **success or failure status of your upload**.</span></span>  <span data-ttu-id="48325-125">如果程序包通过验证，则为已成功上载该文件，你将看到一条成功消息。</span><span class="sxs-lookup"><span data-stu-id="48325-125">If the package passes validation; it is uploaded successfully and you see a success message.</span></span>  <span data-ttu-id="48325-126">如果程序包未通过验证，则为程序包未被接受，您将看到一条错误消息。</span><span class="sxs-lookup"><span data-stu-id="48325-126">If the package fails validation; the package is not accepted and you see an error message.</span></span>  <span data-ttu-id="48325-127">如果程序包中存在错误，请解决这些问题，然后再次尝试上载。</span><span class="sxs-lookup"><span data-stu-id="48325-127">If there are errors in the package, resolve the issues and try uploading it again.</span></span>  

<span data-ttu-id="48325-128">成功上载后，查看扩展详细信息，然后单击 "**下一步**" 以继续。</span><span class="sxs-lookup"><span data-stu-id="48325-128">After successful upload, review your Extension details and click **Next** to proceed.</span></span>  

## <span data-ttu-id="48325-129">步骤3：提供可用性详细信息</span><span class="sxs-lookup"><span data-stu-id="48325-129">Step 3: Provide Availability details</span></span>  

### <span data-ttu-id="48325-130">定义可见性</span><span class="sxs-lookup"><span data-stu-id="48325-130">Define Visibility</span></span>  

<span data-ttu-id="48325-131">选择 "**可见性**" 选项以定义可能发现并获取您的扩展的受众。</span><span class="sxs-lookup"><span data-stu-id="48325-131">Select a **Visibility** option to define the audience who may discover and acquire your Extension.</span></span>  <span data-ttu-id="48325-132">这为你提供了指定用户是否应在 Microsoft Edge Addons 中找到你的扩展的选项，或者根本看不到该列表。</span><span class="sxs-lookup"><span data-stu-id="48325-132">This gives you the option to specify whether users should find your Extension in Microsoft Edge Addons or see the listing at all.</span></span>  <span data-ttu-id="48325-133">当前，在 "可见性" 下有两个选项：</span><span class="sxs-lookup"><span data-stu-id="48325-133">Currently, you have two options under visibility:</span></span>  

*   `Public`  
    <span data-ttu-id="48325-134">这是默认选项。</span><span class="sxs-lookup"><span data-stu-id="48325-134">This is the default option.</span></span>  
    <span data-ttu-id="48325-135">如果你选择 `Public` ，你的扩展可供 Microsoft Edge Addons 中的每个人使用和发现。</span><span class="sxs-lookup"><span data-stu-id="48325-135">If you select `Public`, your Extension is available and discoverable to everyone in Microsoft Edge Addons.</span></span>  <span data-ttu-id="48325-136">如果你希望在 Microsoft Edge Addons 中列出你的扩展，请保留此选项，以便用户通过搜索、浏览和扩展的直接链接进行查找。</span><span class="sxs-lookup"><span data-stu-id="48325-136">Leave this option selected if you want your Extension to be listed in Microsoft Edge Addons for users to find via searching, browsing, and the direct link of your Extension.</span></span>  

*   `Hidden`  
    <span data-ttu-id="48325-137">如果你选择 `Hidden` ，你的扩展将在 Microsoft Edge Addons 中隐藏在用户搜索或浏览中，你必须共享你的列表 URL 才能分发你的扩展。</span><span class="sxs-lookup"><span data-stu-id="48325-137">If you select `Hidden`, your Extension is hidden in Microsoft Edge Addons from users searching or browsing; you must share your listing URL to distribute your Extension.</span></span>  <span data-ttu-id="48325-138">具有列表直接链接的用户可能会在 Microsoft Edge 中下载它 \ （你可能会在扩展提交的**扩展概述**页面下找到你的列表 URL \）。</span><span class="sxs-lookup"><span data-stu-id="48325-138">Users who have the direct link to the listing may download it on Microsoft Edge \(you may find your listing URL under **Extension Overview** page of Extension submission\).</span></span>  

> [!NOTE]
> <span data-ttu-id="48325-139">如果你将扩展提交为 "**公共**"，然后再将其更改为 "**私人性质**"，则在其公开时安装了该扩展的用户将继续拥有访问权限并收到未来更新。</span><span class="sxs-lookup"><span data-stu-id="48325-139">If you submit an Extension as **Public** and later change it to **Private**, Users who installed the Extension when it was public continue to have access and receive future updates.</span></span>  

### <span data-ttu-id="48325-140">定义市场</span><span class="sxs-lookup"><span data-stu-id="48325-140">Define markets</span></span>  

<span data-ttu-id="48325-141">您必须定义您要在其中提供扩展的特定市场，请在 "**可用性**" 页面上的 "**市场**" 部分中选择 "**显示选项**"。</span><span class="sxs-lookup"><span data-stu-id="48325-141">You must define the specific markets in which you are offering your Extension, select **Show options** in the **Markets** section on the **Availability** page.</span></span>  <span data-ttu-id="48325-142">将显示 "市场选择" 弹出窗口，您应在其中选择市场。</span><span class="sxs-lookup"><span data-stu-id="48325-142">The Market selection pop-up window is displayed, where you should choose the markets.</span></span>  <span data-ttu-id="48325-143">默认情况下，所有市场均处于选中状态，包括以后可能添加的任何**市场**。</span><span class="sxs-lookup"><span data-stu-id="48325-143">By default, all markets are selected, including any **future markets** that may be added later.</span></span>  <span data-ttu-id="48325-144">你可以取消选择单个市场以排除它们，或者单击 "**取消全选**"，然后添加你选择的单个市场。</span><span class="sxs-lookup"><span data-stu-id="48325-144">You may deselect individual markets to exclude them, or you may click **Unselect all** and then add individual markets of your choice.</span></span>  

> [!NOTE]
> <span data-ttu-id="48325-145">如果用户已在特定市场中拥有您的扩展，并且稍后删除该市场，则已在该市场中具有扩展的用户可能会继续使用它，但不会获取你提交的更新。</span><span class="sxs-lookup"><span data-stu-id="48325-145">If users already have your Extension in a certain market, and you later remove that market, users who already has the Extension in that market may continue to use it, but they do not get the later updates you submit.</span></span>  

<span data-ttu-id="48325-146">单击 "**保存**" 以转到 "**属性**" 部分。</span><span class="sxs-lookup"><span data-stu-id="48325-146">Click **Save** to proceed to **Properties** section.</span></span>  

## <span data-ttu-id="48325-147">步骤4：选择扩展的属性</span><span class="sxs-lookup"><span data-stu-id="48325-147">Step 4: Select Properties for Your Extension</span></span>  

### <span data-ttu-id="48325-148">扩展属性</span><span class="sxs-lookup"><span data-stu-id="48325-148">Extension properties</span></span>  

*   [<span data-ttu-id="48325-149">类型</span><span class="sxs-lookup"><span data-stu-id="48325-149">Category</span></span>](#category)  
*   [<span data-ttu-id="48325-150">隐私策略要求</span><span class="sxs-lookup"><span data-stu-id="48325-150">Privacy policy requirements</span></span>](#privacy-policy-requirements)  
*   [<span data-ttu-id="48325-151">隐私策略 URL</span><span class="sxs-lookup"><span data-stu-id="48325-151">Privacy policy URL</span></span>](#privacy-policy-url)  
*   [<span data-ttu-id="48325-152">网站 URL</span><span class="sxs-lookup"><span data-stu-id="48325-152">Website URL</span></span>](#website-url)  
*   [<span data-ttu-id="48325-153">支持 URL/电子邮件地址</span><span class="sxs-lookup"><span data-stu-id="48325-153">Support URL/email address</span></span>](#support-urlemail-address)  
*   [<span data-ttu-id="48325-154">扩展分级</span><span class="sxs-lookup"><span data-stu-id="48325-154">Extension Rating</span></span>](#extension-rating)  

#### <span data-ttu-id="48325-155">类型</span><span class="sxs-lookup"><span data-stu-id="48325-155">Category</span></span>  

<span data-ttu-id="48325-156">在右侧类别中列出您的扩展可帮助用户轻松地找到您的扩展并了解更多相关信息。</span><span class="sxs-lookup"><span data-stu-id="48325-156">Listing your Extension in the right category helps users find your Extension easily and understand more about it.</span></span>  <span data-ttu-id="48325-157">选择最能描述您的扩展的类别。</span><span class="sxs-lookup"><span data-stu-id="48325-157">Select a Category that best describes your Extension.</span></span>  

<span data-ttu-id="48325-158">**可能的值**：</span><span class="sxs-lookup"><span data-stu-id="48325-158">**Possible Values**:</span></span>  

*   `Accessibility`  
*   `Blogging`  
*   `Developer Tools`  
*   `Fun`  
*   `News & Weather`  
*   `Photos`  
*   `Productivity`  
*   `Search Tools`  
*   `Shopping`  
*   `Social & Communication`  
*   `Sports`  

#### <span data-ttu-id="48325-159">隐私策略要求</span><span class="sxs-lookup"><span data-stu-id="48325-159">Privacy policy requirements</span></span>  

<span data-ttu-id="48325-160">指明您的扩展是访问、收集还是传输任何个人信息。</span><span class="sxs-lookup"><span data-stu-id="48325-160">Indicate whether your Extension accesses, collects, or transmits any personal information.</span></span>  

> [!NOTE]
> <span data-ttu-id="48325-161">如果你的扩展要求隐私策略，但你没有提供，则你的提交可能无法通过认证。</span><span class="sxs-lookup"><span data-stu-id="48325-161">If your Extension requires a privacy policy and you have not provided one, your submission may fail certification.</span></span>  

<span data-ttu-id="48325-162">**可能的值**：</span><span class="sxs-lookup"><span data-stu-id="48325-162">**Possible Values**:</span></span>  

*   `No`<span data-ttu-id="48325-163">：隐私策略 URL 是可选的。</span><span class="sxs-lookup"><span data-stu-id="48325-163">:  A privacy policy URL is optional.</span></span>  
*   `Yes`<span data-ttu-id="48325-164">：需要隐私策略 URL。</span><span class="sxs-lookup"><span data-stu-id="48325-164">:  A privacy policy URL is required.</span></span>  

#### <span data-ttu-id="48325-165">隐私策略 URL</span><span class="sxs-lookup"><span data-stu-id="48325-165">Privacy policy URL</span></span>  

<span data-ttu-id="48325-166">您有责任确保您的分机符合隐私法律和法规，并根据需要提供有效的隐私政策 URL。</span><span class="sxs-lookup"><span data-stu-id="48325-166">You are responsible for ensuring your Extension complies with privacy laws and regulations, and for providing a valid privacy policy URL, if required.</span></span>  <span data-ttu-id="48325-167">如果你的扩展正在访问、传输或收集任何个人信息，则必须提供隐私策略 URL。</span><span class="sxs-lookup"><span data-stu-id="48325-167">You must provide a privacy policy URL if any personal information is being accessed, transmitted, or collected by your Extension.</span></span>  
<span data-ttu-id="48325-168">若要确定你的扩展是否需要隐私策略，请查看[Microsoft Edge 开发人员协议][MicrosoftAppDeveloperAgreement]和[Microsoft Edge Addons 目录开发人员策略文档][MicrosoftEdgeAddonsCatalogDeveloperPolicies]。</span><span class="sxs-lookup"><span data-stu-id="48325-168">To determine if your Extension requires a privacy policy, review the [Microsoft Edge Developer Agreement][MicrosoftAppDeveloperAgreement] and the [Microsoft Edge Addons Catalog Developer Policies document][MicrosoftEdgeAddonsCatalogDeveloperPolicies].</span></span>  

<span data-ttu-id="48325-169">**可能的值**：</span><span class="sxs-lookup"><span data-stu-id="48325-169">**Possible Values**:</span></span>  

*   `{url}`  

#### <span data-ttu-id="48325-170">网站 URL</span><span class="sxs-lookup"><span data-stu-id="48325-170">Website URL</span></span>  

<span data-ttu-id="48325-171">此属性是可选的。</span><span class="sxs-lookup"><span data-stu-id="48325-171">This property is Optional.</span></span>  
<span data-ttu-id="48325-172">用于您的扩展的网页的 URL。</span><span class="sxs-lookup"><span data-stu-id="48325-172">The URL of the web page for your Extension.</span></span>  <span data-ttu-id="48325-173">此 URL 必须指向您自己的网站上的页面，而不是 Microsoft Edge Addons 中的扩展 web 列表。</span><span class="sxs-lookup"><span data-stu-id="48325-173">This URL must point to a page on your own website, not the web listing for your Extension in Microsoft Edge Addons.</span></span>  

<span data-ttu-id="48325-174">**可能的值**：</span><span class="sxs-lookup"><span data-stu-id="48325-174">**Possible Values**:</span></span>  

*   `{url}`  

#### <span data-ttu-id="48325-175">支持 URL/电子邮件地址</span><span class="sxs-lookup"><span data-stu-id="48325-175">Support URL/email address</span></span>  

<span data-ttu-id="48325-176">此属性是可选的。</span><span class="sxs-lookup"><span data-stu-id="48325-176">This property is Optional.</span></span>  
<span data-ttu-id="48325-177">用户通过您的分机支持的网页的 URL，或用于联系您的电子邮件地址以获得支持。</span><span class="sxs-lookup"><span data-stu-id="48325-177">The URL of the web page where users go for support with your Extension, or an email address to contact you for support.</span></span>  <span data-ttu-id="48325-178">你包括所有提交的支持信息，以便你的用户知道如何获取来自你的支持。</span><span class="sxs-lookup"><span data-stu-id="48325-178">You include support information for all submissions, so that your users know how to get support from you.</span></span>  

<span data-ttu-id="48325-179">**可能的值**：</span><span class="sxs-lookup"><span data-stu-id="48325-179">**Possible Values**:</span></span>  

*   `{email_address}`  
*   `{url}`  

#### <span data-ttu-id="48325-180">扩展分级</span><span class="sxs-lookup"><span data-stu-id="48325-180">Extension Rating</span></span>  

<span data-ttu-id="48325-181">扩展评级可帮助我们确定你的扩展的目标受众的年龄。</span><span class="sxs-lookup"><span data-stu-id="48325-181">Extension rating helps us determine the age of the target audience of your Extension.</span></span>  
<span data-ttu-id="48325-182">若要帮助确定你的扩展是否具有成人内容，请查看[Microsoft Edge Addons 目录开发人员策略文档][MicrosoftEdgeAddonsCatalogDeveloperPolicies]。</span><span class="sxs-lookup"><span data-stu-id="48325-182">To help you determine if your Extensions has a mature content, review the [Microsoft Edge Addons Catalog Developer Policies document][MicrosoftEdgeAddonsCatalogDeveloperPolicies].</span></span>  

<span data-ttu-id="48325-183">**可能的值**：</span><span class="sxs-lookup"><span data-stu-id="48325-183">**Possible Values**:</span></span>  

*   <span data-ttu-id="48325-184">成人 \ （checkbox \）：如果您的分机包含任何成人内容，请选中此框。</span><span class="sxs-lookup"><span data-stu-id="48325-184">Mature \(checkbox\): Check this box if your Extension contains any mature content.</span></span>  <span data-ttu-id="48325-185">如果你为扩展选择 "成人"，你的列表将提供单独的标记，指示扩展包含成人内容。</span><span class="sxs-lookup"><span data-stu-id="48325-185">If you select mature for your Extension, your listing is available with a separate tag to indicate that the Extension contains mature content.</span></span>  

<span data-ttu-id="48325-186">单击 "**保存**" 以转到 "清单" 部分。</span><span class="sxs-lookup"><span data-stu-id="48325-186">Click **Save** to proceed to listing section.</span></span>  

## <span data-ttu-id="48325-187">步骤5：为您的扩展添加节目表信息</span><span class="sxs-lookup"><span data-stu-id="48325-187">Step 5: Add Listings Information for Your Extension</span></span>  

<span data-ttu-id="48325-188">这是用户在 Microsoft Edge Addons 中查看您的列表时看到的信息。</span><span class="sxs-lookup"><span data-stu-id="48325-188">This is the information that users see when viewing your listing in Microsoft Edge Addons.</span></span>  <span data-ttu-id="48325-189">列表中的许多字段是可选的，但我们建议提供尽可能多的信息，以使你的清单与众不同。 要视为完整的 Microsoft Edge Addons 中的列表所需的最低要求是在扩展程序包中提及的每种语言的[文本说明](#description)、[扩展徽标](#store-logo)和[小促销图块](#small-promotional-tile)。</span><span class="sxs-lookup"><span data-stu-id="48325-189">Many of the fields in a listing are optional, but we suggest providing as much information as possible to make your listing stand out.  The minimum required for your listing in Microsoft Edge Addons to be considered complete is the [text description](#description), [Extension logo](#store-logo), and [small promotional tile](#small-promotional-tile) in each language mentioned in your Extension package.</span></span>  

### <span data-ttu-id="48325-190">商店的 "待售房产" 域</span><span class="sxs-lookup"><span data-stu-id="48325-190">Store Listing fields</span></span>  

*   [<span data-ttu-id="48325-191">应用商店一览语言</span><span class="sxs-lookup"><span data-stu-id="48325-191">Store listing languages</span></span>](#store-listing-languages)  
*   [<span data-ttu-id="48325-192">应用商店显示名称</span><span class="sxs-lookup"><span data-stu-id="48325-192">Store display name</span></span>](#store-display-name)  
*   [<span data-ttu-id="48325-193">描述</span><span class="sxs-lookup"><span data-stu-id="48325-193">Description</span></span>](#description)  
*   [<span data-ttu-id="48325-194">应用商店徽标</span><span class="sxs-lookup"><span data-stu-id="48325-194">Store logo</span></span>](#store-logo)  
*   [<span data-ttu-id="48325-195">小型促销磁贴</span><span class="sxs-lookup"><span data-stu-id="48325-195">Small promotional tile</span></span>](#small-promotional-tile)  
*   [<span data-ttu-id="48325-196">媒体</span><span class="sxs-lookup"><span data-stu-id="48325-196">Media</span></span>](#media)  
*   [<span data-ttu-id="48325-197">简短说明</span><span class="sxs-lookup"><span data-stu-id="48325-197">Short description</span></span>](#short-description)  
*   [<span data-ttu-id="48325-198">搜索词</span><span class="sxs-lookup"><span data-stu-id="48325-198">Search terms</span></span>](#search-terms)  

#### <span data-ttu-id="48325-199">应用商店一览语言</span><span class="sxs-lookup"><span data-stu-id="48325-199">Store listing languages</span></span>  

<span data-ttu-id="48325-200">如果您的扩展程序包支持多种语言，则您的扩展名必须具有每个语言的一个列表页。</span><span class="sxs-lookup"><span data-stu-id="48325-200">If your Extension package supports multiple languages, your Extension must have a listing page for each one.</span></span>  
<span data-ttu-id="48325-201">你必须为每种语言单独完成列表详细信息 \ （文本说明、图像等），即使你对每种语言使用相同的内容也是如此。</span><span class="sxs-lookup"><span data-stu-id="48325-201">You must complete listing details \(text description, images, and so on\) for each language separately even if you are using the same content for each language.</span></span>  <span data-ttu-id="48325-202">如果您的扩展是以多种语言本地化的，这些语言将显示在 "列出" 页面的顶部。</span><span class="sxs-lookup"><span data-stu-id="48325-202">If your Extension is localized in more than one language, those languages are displayed at the top of listing page.</span></span>  

1.  <span data-ttu-id="48325-203">从 "**语言**" 下拉列表中选择任意一种语言名称。</span><span class="sxs-lookup"><span data-stu-id="48325-203">Select any one language name from **Languages** drop-down list.</span></span>  
1.  <span data-ttu-id="48325-204">填写列表详细信息。</span><span class="sxs-lookup"><span data-stu-id="48325-204">Fill the listing details.</span></span>  
1.  <span data-ttu-id="48325-205">单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="48325-205">Click **Save**.</span></span>  
1.  <span data-ttu-id="48325-206">对所有支持的语言重复上述操作。</span><span class="sxs-lookup"><span data-stu-id="48325-206">Repeat for all of your supported languages.</span></span>  

> [!NOTE]
> <span data-ttu-id="48325-207">若要在 Microsoft Edge Addons 中为您的列表添加或删除语言，必须修改扩展程序包支持的语言列表，然后重新上传。</span><span class="sxs-lookup"><span data-stu-id="48325-207">To add or remove languages for your listing in Microsoft Edge Addons, you must modify the list of languages supported by your Extension package and re-upload it.</span></span>  

<span data-ttu-id="48325-208">**可能的值**：</span><span class="sxs-lookup"><span data-stu-id="48325-208">**Possible Values**:</span></span>  

*   `English (United States)`<span data-ttu-id="48325-209">：这是默认值。</span><span class="sxs-lookup"><span data-stu-id="48325-209">:  This is the default value.</span></span>  <span data-ttu-id="48325-210">如果你不提及程序包中的任何语言，我们将默认语言设置为英语 \ （美国 \），并且你必须提供英语的列表（美国 \）。</span><span class="sxs-lookup"><span data-stu-id="48325-210">If you do not mention any language in your package, we set your default language to English \(United States\) and you must provide a listing in English \(United States\).</span></span>  
*   `{language}` <span data-ttu-id="48325-211">\(`{Country}`\)</span><span class="sxs-lookup"><span data-stu-id="48325-211">\(`{Country}`\)</span></span>  

#### <span data-ttu-id="48325-212">应用商店显示名称</span><span class="sxs-lookup"><span data-stu-id="48325-212">Store display name</span></span>  

<span data-ttu-id="48325-213">扩展程序包清单中提及的扩展的名称。</span><span class="sxs-lookup"><span data-stu-id="48325-213">The name of Extension as mentioned in your Extension package manifest.</span></span>  

> [!NOTE]
> <span data-ttu-id="48325-214">若要编辑名称，必须更新扩展程序包中的清单，然后重新上载它。</span><span class="sxs-lookup"><span data-stu-id="48325-214">To edit the name, you must update the manifest in your Extension package and re-upload it.</span></span>  

#### <span data-ttu-id="48325-215">描述</span><span class="sxs-lookup"><span data-stu-id="48325-215">Description</span></span>  

<span data-ttu-id="48325-216">此字段是必需的。</span><span class="sxs-lookup"><span data-stu-id="48325-216">This field is required.</span></span>  
<span data-ttu-id="48325-217">适用于您的扩展的用户的说明。</span><span class="sxs-lookup"><span data-stu-id="48325-217">The description for your users of what your Extension does.</span></span>  

<span data-ttu-id="48325-218">**可能的值**：</span><span class="sxs-lookup"><span data-stu-id="48325-218">**Possible Values**:</span></span>  

*   <span data-ttu-id="48325-219">{plain_text}：少于10000个字符。</span><span class="sxs-lookup"><span data-stu-id="48325-219">{plain_text}: Less than 10,000 characters.</span></span>  

#### <span data-ttu-id="48325-220">应用商店徽标</span><span class="sxs-lookup"><span data-stu-id="48325-220">Store logo</span></span>  

<span data-ttu-id="48325-221">此字段是必需的。</span><span class="sxs-lookup"><span data-stu-id="48325-221">This field is required.</span></span>  
<span data-ttu-id="48325-222">用于扩展徽标的1:1 图像。</span><span class="sxs-lookup"><span data-stu-id="48325-222">A 1:1 image for your Extension logo.</span></span>  

<span data-ttu-id="48325-223">**可能的值**：</span><span class="sxs-lookup"><span data-stu-id="48325-223">**Possible Values**:</span></span>  

*   <span data-ttu-id="48325-224">128px x 128px，PNG \ （.png）</span><span class="sxs-lookup"><span data-stu-id="48325-224">128px x 128px, PNG \(.png\)</span></span>  
*   <span data-ttu-id="48325-225">150px x 140px，PNG \ （.png）</span><span class="sxs-lookup"><span data-stu-id="48325-225">150px x 140px, PNG \(.png\)</span></span>  
*   <span data-ttu-id="48325-226">300px x 300px，PNG \ （.png \）：建议的大小。</span><span class="sxs-lookup"><span data-stu-id="48325-226">300px x 300px, PNG \(.png\):  The recommended size.</span></span>  

#### <span data-ttu-id="48325-227">小型促销磁贴</span><span class="sxs-lookup"><span data-stu-id="48325-227">Small promotional tile</span></span>  

<span data-ttu-id="48325-228">此字段是必需的。</span><span class="sxs-lookup"><span data-stu-id="48325-228">This field is required.</span></span>  
<span data-ttu-id="48325-229">小尺寸的促销图块。</span><span class="sxs-lookup"><span data-stu-id="48325-229">A small size promotional tile.</span></span>  <span data-ttu-id="48325-230">您的列表显示在此磁贴上。</span><span class="sxs-lookup"><span data-stu-id="48325-230">Your listing is displayed on this tile.</span></span>  

<span data-ttu-id="48325-231">**可能的值**：</span><span class="sxs-lookup"><span data-stu-id="48325-231">**Possible Values**:</span></span>  

*   <span data-ttu-id="48325-232">440px x 280x，PNG \ （.png）</span><span class="sxs-lookup"><span data-stu-id="48325-232">440px x 280x, PNG \(.png\)</span></span>  

#### <span data-ttu-id="48325-233">媒体</span><span class="sxs-lookup"><span data-stu-id="48325-233">Media</span></span>  

<span data-ttu-id="48325-234">此字段是可选的。</span><span class="sxs-lookup"><span data-stu-id="48325-234">This field is optional.</span></span>  
<span data-ttu-id="48325-235">你应该提供这些资源来帮助更有效地显示你的产品。</span><span class="sxs-lookup"><span data-stu-id="48325-235">You should provide these assets to help display your product more effectively.</span></span>  

*   <span data-ttu-id="48325-236">屏幕截图</span><span class="sxs-lookup"><span data-stu-id="48325-236">Screenshots</span></span>  
    <span data-ttu-id="48325-237">描述扩展功能的扩展图像。</span><span class="sxs-lookup"><span data-stu-id="48325-237">The images of your Extension that describe what your Extension does.</span></span>  
    
*   <span data-ttu-id="48325-238">大型促销图块</span><span class="sxs-lookup"><span data-stu-id="48325-238">Large promotion tiles</span></span>  
    <span data-ttu-id="48325-239">要在 Microsoft Edge Addons 中更突出地使用扩展功能的大型促销图块。</span><span class="sxs-lookup"><span data-stu-id="48325-239">A large promotional tile to be feature your Extension more prominently in Microsoft Edge Addons.</span></span>  
    
*   <span data-ttu-id="48325-240">YouTube 视频 URL</span><span class="sxs-lookup"><span data-stu-id="48325-240">YouTube video URL</span></span>  
    <span data-ttu-id="48325-241">[适用于您的扩展的有效 YouTube 视频 URL][MicrosoftEdgeAddonsUploadYouTubeVideo]。</span><span class="sxs-lookup"><span data-stu-id="48325-241">A valid [YouTube video URL for your Extension][MicrosoftEdgeAddonsUploadYouTubeVideo].</span></span>  <span data-ttu-id="48325-242">你的视频的质量应很好，最短的长度。</span><span class="sxs-lookup"><span data-stu-id="48325-242">Your video should be good quality and minimal length.</span></span>  <span data-ttu-id="48325-243">您的 YouTube 视频必须先通过认证，然后才能在 Microsoft Edge Addons 中发布您的扩展。</span><span class="sxs-lookup"><span data-stu-id="48325-243">Your YouTube video must pass certification before publishing your Extension in Microsoft Edge Addons.</span></span>  <span data-ttu-id="48325-244">验证你的 YouTube 视频是否符合[Microsoft Edge Addons 目录开发人员策略文档][MicrosoftEdgeAddonsCatalogDeveloperPolicies]。</span><span class="sxs-lookup"><span data-stu-id="48325-244">Verify that your YouTube video complies with the [Microsoft Edge Addons Catalog Developer Policies document][MicrosoftEdgeAddonsCatalogDeveloperPolicies].</span></span>  

<span data-ttu-id="48325-245">**可能的值**：</span><span class="sxs-lookup"><span data-stu-id="48325-245">**Possible Values**:</span></span>  

*   <span data-ttu-id="48325-246">10个最大屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="48325-246">10 Screenshots maximum.</span></span>  
    *   <span data-ttu-id="48325-247">640px x 480px，PNG \ （.png）：屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="48325-247">640px x 480px, PNG \(.png\):  Screenshots.</span></span>  
    *   <span data-ttu-id="48325-248">1280px x 800px，PNG \ （.png）：屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="48325-248">1280px x 800px, PNG \(.png\):  Screenshots.</span></span>  
*   <span data-ttu-id="48325-249">1400px x 560px，PNG \ （.png \）：大型提升图块。</span><span class="sxs-lookup"><span data-stu-id="48325-249">1400px x 560px, PNG \(.png\):  Large promotion tiles.</span></span>  
*   <span data-ttu-id="48325-250">60秒或更短、2GB 或更小的 YouTube 视频 URL。</span><span class="sxs-lookup"><span data-stu-id="48325-250">60 seconds or shorter and 2GB or smaller, YouTube video URL.</span></span>  

#### <span data-ttu-id="48325-251">简短说明</span><span class="sxs-lookup"><span data-stu-id="48325-251">Short description</span></span>  

<span data-ttu-id="48325-252">可在产品清单顶部使用的简短 catchy 说明。</span><span class="sxs-lookup"><span data-stu-id="48325-252">A short, catchy description that may be used at the top of the listing for your product.</span></span>  <span data-ttu-id="48325-253">如果未提供，则改为使用较长说明中的前几行。</span><span class="sxs-lookup"><span data-stu-id="48325-253">If not provided, the first few lines from your longer description are used instead.</span></span>  <span data-ttu-id="48325-254">由于你的说明还会显示在此文本下方，因此你应提供具有不同文本的简短说明，以便你的列表更不重复。</span><span class="sxs-lookup"><span data-stu-id="48325-254">Because your description also appears below this text, you should provide a short description with different text so that your listing is less repetitive.</span></span>  <span data-ttu-id="48325-255">扩展的简短说明直接从程序包的清单文件中选取。</span><span class="sxs-lookup"><span data-stu-id="48325-255">The Short description of your Extension is picked directly from the manifest file of your package.</span></span>  

> [!NOTE]
> <span data-ttu-id="48325-256">若要编辑简短说明，必须更新扩展程序包中的清单，然后重新上载它。</span><span class="sxs-lookup"><span data-stu-id="48325-256">To edit the short description, you must update the manifest in your Extension package and re-upload it.</span></span>  

#### <span data-ttu-id="48325-257">搜索词</span><span class="sxs-lookup"><span data-stu-id="48325-257">Search terms</span></span>  

<span data-ttu-id="48325-258">搜索词是不会向用户显示的单个字词或短语，但当用户使用这些术语进行搜索时，可帮助你在 Microsoft Edge Addons 中发现你的扩展。</span><span class="sxs-lookup"><span data-stu-id="48325-258">Search terms are single words or short phrases that are not displayed to users but help make your Extension discoverable in Microsoft Edge Addons when users search using those terms.</span></span>  

<span data-ttu-id="48325-259">**要求**：</span><span class="sxs-lookup"><span data-stu-id="48325-259">**Requirements**:</span></span>  

*   <span data-ttu-id="48325-260">7个或更少的搜索词</span><span class="sxs-lookup"><span data-stu-id="48325-260">7 or fewer search terms</span></span>  
*   <span data-ttu-id="48325-261">每个搜索词30个或更少的字符</span><span class="sxs-lookup"><span data-stu-id="48325-261">30 or fewer characters per search term</span></span>  
*   <span data-ttu-id="48325-262">小于或等于21的组合搜索词</span><span class="sxs-lookup"><span data-stu-id="48325-262">21 or fewer words for combined search terms</span></span>  

<span data-ttu-id="48325-263">单击 "**保存**" 以继续保存您的 "列表" 部分。</span><span class="sxs-lookup"><span data-stu-id="48325-263">Click **Save** to proceed to save your listing section.</span></span>  <span data-ttu-id="48325-264">单击 "**发布**" 以提供提交详细信息。</span><span class="sxs-lookup"><span data-stu-id="48325-264">Click **Publish** to provide submission details.</span></span>  

## <span data-ttu-id="48325-265">步骤6：完成提交，然后单击 "发布"</span><span class="sxs-lookup"><span data-stu-id="48325-265">Step 6: Complete your submission and click Publish</span></span>  

<span data-ttu-id="48325-266">扩展提交过程的 "提交选项" 页面是你提供详细信息以帮助我们正确测试你的产品的位置。</span><span class="sxs-lookup"><span data-stu-id="48325-266">The Submission options page of the Extension submission process is where you provide more information to help us test your product properly.</span></span>  <span data-ttu-id="48325-267">这是一个可选步骤，但建议对许多提交执行此操作。</span><span class="sxs-lookup"><span data-stu-id="48325-267">This is an optional step, but it is recommended for many submissions.</span></span>  

### <span data-ttu-id="48325-268">发布暂停选项</span><span class="sxs-lookup"><span data-stu-id="48325-268">Publishing hold options</span></span>  

<span data-ttu-id="48325-269">默认情况下，提交证明后立即发布。</span><span class="sxs-lookup"><span data-stu-id="48325-269">By default, your submission is published as soon as it passes certification.</span></span>  <span data-ttu-id="48325-270">你可以选择在将提交发布到特定日期之前保留。</span><span class="sxs-lookup"><span data-stu-id="48325-270">You may choose to place a hold on publishing your submission until a specific date.</span></span>  <span data-ttu-id="48325-271">这个部分的选项如下所述。</span><span class="sxs-lookup"><span data-stu-id="48325-271">The options in this section are described below.</span></span>  

*   **<span data-ttu-id="48325-272">在提交证书后立即发布你的提交</span><span class="sxs-lookup"><span data-stu-id="48325-272">Publish your submission as soon as it passes certification</span></span>**  

    <span data-ttu-id="48325-273">这是默认选择。</span><span class="sxs-lookup"><span data-stu-id="48325-273">This is the default selection.</span></span>  <span data-ttu-id="48325-274">这意味着提交证书后，你的提交将立即开始发布过程</span><span class="sxs-lookup"><span data-stu-id="48325-274">It means that your submission begins the publishing process as soon as it passes certification</span></span>  

*   **<span data-ttu-id="48325-275">在特定日期开始发布你的提交</span><span class="sxs-lookup"><span data-stu-id="48325-275">Start publishing your submission on a certain date</span></span>**  

    <span data-ttu-id="48325-276">选择 **"开始在特定日期发布提交**"，以确保在特定日期之前不发布提交。</span><span class="sxs-lookup"><span data-stu-id="48325-276">Choose **Start publishing your submission on a certain date** to ensure that the submission is not published until a specific date.</span></span>  <span data-ttu-id="48325-277">如果选择此选项，则会在你指定的日期或之后尽早释放你的提交。</span><span class="sxs-lookup"><span data-stu-id="48325-277">With this option, your submission is released as soon as possible on or after the date you specify.</span></span>  <span data-ttu-id="48325-278">该日期必须为 24 小时之后的一个日期。</span><span class="sxs-lookup"><span data-stu-id="48325-278">The date must be at least 24 hours in the future.</span></span>  <span data-ttu-id="48325-279">除了日期，您可以指定应开始发布提交的时间。</span><span class="sxs-lookup"><span data-stu-id="48325-279">Along with the date, you may specify the time at which the submission should begin to be published.</span></span>  

### <span data-ttu-id="48325-280">认证说明</span><span class="sxs-lookup"><span data-stu-id="48325-280">Notes for certification</span></span>  

<span data-ttu-id="48325-281">当你提交扩展时，你可以选择使用 "证书说明" 页面向认证测试人员提供其他信息。</span><span class="sxs-lookup"><span data-stu-id="48325-281">As you submit your Extension, you have the option to use the Notes for certification page to provide additional information to the certification testers.</span></span>  <span data-ttu-id="48325-282">此信息有助于确保正确地测试扩展。</span><span class="sxs-lookup"><span data-stu-id="48325-282">This information helps ensure that your Extension is tested correctly.</span></span>  <span data-ttu-id="48325-283">如果我们无法完全测试你的提交，则它可能无法通过认证。</span><span class="sxs-lookup"><span data-stu-id="48325-283">If we are not able to fully test your submission, it may fail certification.</span></span>  

<span data-ttu-id="48325-284">请确保包含以下 \ （如果适用于您的扩展名 \）：</span><span class="sxs-lookup"><span data-stu-id="48325-284">Make sure to include the following \(if applicable for your Extension\):</span></span>  

*   <span data-ttu-id="48325-285">测试帐户的用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="48325-285">User names and passwords for test accounts.</span></span>  
*   <span data-ttu-id="48325-286">访问隐藏或锁定的功能的步骤。</span><span class="sxs-lookup"><span data-stu-id="48325-286">Steps to access hidden or locked features.</span></span>  
*   <span data-ttu-id="48325-287">根据区域或其他用户设置，行为预期差异。</span><span class="sxs-lookup"><span data-stu-id="48325-287">Expected differences in behavior based on region or other user settings.</span></span>  
*   <span data-ttu-id="48325-288">有关应用更新中的更改的信息。</span><span class="sxs-lookup"><span data-stu-id="48325-288">Information about what changed in an app update.</span></span>  
*   <span data-ttu-id="48325-289">你认为测试人员必须了解你的提交的任何其他内容。</span><span class="sxs-lookup"><span data-stu-id="48325-289">Anything else you think testers must understand about your submission.</span></span>  

<span data-ttu-id="48325-290">完成上述详细信息后，单击 "**发布**" 以在 Microsoft Edge Addons 中提交您的扩展。</span><span class="sxs-lookup"><span data-stu-id="48325-290">After completing the above details, click **Publish** to submit your Extension in Microsoft Edge Addons.</span></span>  

<span data-ttu-id="48325-291">当您完成为您的扩展创建提交并单击 "**发布**" 时，提交将进入认证步骤。</span><span class="sxs-lookup"><span data-stu-id="48325-291">When you finish creating the submission for your Extension and click **Publish**, the submission enters the certification step.</span></span>  <span data-ttu-id="48325-292">此过程通常在几天内完成，但在某些情况下，可能需要长达7个工作日。</span><span class="sxs-lookup"><span data-stu-id="48325-292">This process usually is completed within a couple of days, though in some cases it may take up to 7 business days.</span></span>  <span data-ttu-id="48325-293">提交完成认证后，将在 Microsoft Edge Addons 中发布您的分机号码，除非您选择了 "发布保留" 选项以指定在特定日期之前不应将其释放。</span><span class="sxs-lookup"><span data-stu-id="48325-293">After your submission passes certification, your Extension is published in Microsoft Edge Addons unless you selected the Publishing hold options to specify that it should not be released until a certain date.</span></span>  <span data-ttu-id="48325-294">提交发布后，您将收到通知，并且仪表板中的扩展状态将更改为 `In the Store` 。</span><span class="sxs-lookup"><span data-stu-id="48325-294">You are notified when your submission is published, and the status of your Extension in the dashboard changes to `In the Store`.</span></span>  

<!-- image links -->  

<!-- links -->  

[ExtensionsGettingStarted]: ../getting-started/index.md "Microsoft Edge \ （Chromium \）扩展的入门 |Microsoft 文档"  

[MicrosoftEdgeAddonsUploadYouTubeVideo]: ./upload-video.md "上载 YouTube 视频 |Microsoft 文档"  
[MicrosoftEdgeAddonsCatalogDeveloperPolicies]: ../store-policies/developer-policies.md "Microsoft Edge Addons 目录开发人员策略 |Microsoft 文档"  

[MicrosoftAppDeveloperAgreement]: /legal/windows/agreements/app-developer-agreement "应用开发人员协议 |Microsoft 文档"  

[MicrosoftPartnerCenter]: https://partner.microsoft.com/dashboard/microsoftedge/public/login?ref=dd "合作伙伴中心"  
