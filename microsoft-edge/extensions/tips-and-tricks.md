---
description: Learn about some handy tips and tricks regarding Microsoft Edge extensions
title: Extensions - Tips and tricks
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/16/2019
ms.topic: article
ms.prod: microsoft-edge
keywords: edge, web development, html, css, javascript, developer, extensions
ms.openlocfilehash: db15aa49649432a6c4400b4e6830501c40485a83
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563226"
---
# <span data-ttu-id="ddf8c-104">Tips and tricks</span><span class="sxs-lookup"><span data-stu-id="ddf8c-104">Tips and tricks</span></span>  

[!INCLUDE [deprecation-note](includes/deprecation-note.md)]  

<span data-ttu-id="ddf8c-105">Whether you're currently working on a Microsoft Edge extension or have already published one, the following tips and tricks might come in handy.</span><span class="sxs-lookup"><span data-stu-id="ddf8c-105">Whether you're currently working on a Microsoft Edge extension or have already published one, the following tips and tricks might come in handy.</span></span>

## <span data-ttu-id="ddf8c-106">Get a direct link to your extension in the Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="ddf8c-106">Get a direct link to your extension in the Microsoft Store</span></span>
<span data-ttu-id="ddf8c-107">In the Windows Dev Center dashboard, you can find a direct link to your extension in the Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="ddf8c-107">In the Windows Dev Center dashboard, you can find a direct link to your extension in the Microsoft Store.</span></span> <span data-ttu-id="ddf8c-108">This link can be useful for advertising and sharing out your extension.</span><span class="sxs-lookup"><span data-stu-id="ddf8c-108">This link can be useful for advertising and sharing out your extension.</span></span>


<span data-ttu-id="ddf8c-109">After logging in to the Windows Dev Center and navigating to your extension through the dashboard, on the App identity page you’ll find the link in the **Store protocol link** row:</span><span class="sxs-lookup"><span data-stu-id="ddf8c-109">After logging in to the Windows Dev Center and navigating to your extension through the dashboard, on the App identity page you’ll find the link in the **Store protocol link** row:</span></span>

![store protocol link](./media/store-link.png)
 
## <span data-ttu-id="ddf8c-111">Make sure you’re following the Microsoft Store Policy</span><span class="sxs-lookup"><span data-stu-id="ddf8c-111">Make sure you’re following the Microsoft Store Policy</span></span>
<span data-ttu-id="ddf8c-112">When creating your extension, make sure you keep in mind the guidelines for submitting to the Microsoft Store highlighted in the [Microsoft Store Policy](https://msdn.microsoft.com/library/windows/apps/dn764944.aspx).</span><span class="sxs-lookup"><span data-stu-id="ddf8c-112">When creating your extension, make sure you keep in mind the guidelines for submitting to the Microsoft Store highlighted in the [Microsoft Store Policy](https://msdn.microsoft.com/library/windows/apps/dn764944.aspx).</span></span> 
 
<span data-ttu-id="ddf8c-113">Microsoft Edge extensions also have an additional set of policies to follow seen [here](https://msdn.microsoft.com/library/windows/apps/dn764944.aspx#pol_10_12).</span><span class="sxs-lookup"><span data-stu-id="ddf8c-113">Microsoft Edge extensions also have an additional set of policies to follow seen [here](https://msdn.microsoft.com/library/windows/apps/dn764944.aspx#pol_10_12).</span></span>

## <span data-ttu-id="ddf8c-114">Improve your extension’s discoverability in the Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="ddf8c-114">Improve your extension’s discoverability in the Microsoft Store</span></span>

<span data-ttu-id="ddf8c-115">You can add keywords to your extension submission to imporove its discoverability through searches.</span><span class="sxs-lookup"><span data-stu-id="ddf8c-115">You can add keywords to your extension submission to imporove its discoverability through searches.</span></span> <span data-ttu-id="ddf8c-116">For example, "Microsoft Edge Extensions" and "name of my extension".</span><span class="sxs-lookup"><span data-stu-id="ddf8c-116">For example, "Microsoft Edge Extensions" and "name of my extension".</span></span> 

<span data-ttu-id="ddf8c-117">This can be done in the Windows Dev Center under the description section of your extension.</span><span class="sxs-lookup"><span data-stu-id="ddf8c-117">This can be done in the Windows Dev Center under the description section of your extension.</span></span> <span data-ttu-id="ddf8c-118">These keywords will need to be added for every language your extension supports.</span><span class="sxs-lookup"><span data-stu-id="ddf8c-118">These keywords will need to be added for every language your extension supports.</span></span>

![Submitting a response to a review](./media/keywords.png)

## <span data-ttu-id="ddf8c-120">Automate your submission to the Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="ddf8c-120">Automate your submission to the Microsoft Store</span></span>
<span data-ttu-id="ddf8c-121">You can automate and streamline your submissions to the Microsoft Store by using the new Microsoft Store Submission API, which allows you to update apps/games, add-ons (in-app purchases), and package flights through a REST API.</span><span class="sxs-lookup"><span data-stu-id="ddf8c-121">You can automate and streamline your submissions to the Microsoft Store by using the new Microsoft Store Submission API, which allows you to update apps/games, add-ons (in-app purchases), and package flights through a REST API.</span></span> <span data-ttu-id="ddf8c-122">Check out the [documentation and samples](https://docs.microsoft.com/windows/uwp/monetize/create-and-manage-submissions-using-windows-store-services) or use the open source [Submission API VSTS extension](https://github.com/Microsoft/windows-dev-center-vsts-extension) to get started.</span><span class="sxs-lookup"><span data-stu-id="ddf8c-122">Check out the [documentation and samples](https://docs.microsoft.com/windows/uwp/monetize/create-and-manage-submissions-using-windows-store-services) or use the open source [Submission API VSTS extension](https://github.com/Microsoft/windows-dev-center-vsts-extension) to get started.</span></span>

## <span data-ttu-id="ddf8c-123">Use the Windows Feedback Hub to gather feedback/reviews/feature requests</span><span class="sxs-lookup"><span data-stu-id="ddf8c-123">Use the Windows Feedback Hub to gather feedback/reviews/feature requests</span></span>

<span data-ttu-id="ddf8c-124">You can direct users to the Windows Feedback Hub subcategory for your extension by embedding a link that points to it.</span><span class="sxs-lookup"><span data-stu-id="ddf8c-124">You can direct users to the Windows Feedback Hub subcategory for your extension by embedding a link that points to it.</span></span> <span data-ttu-id="ddf8c-125">This link will need to be created using the following format:</span><span class="sxs-lookup"><span data-stu-id="ddf8c-125">This link will need to be created using the following format:</span></span> 

`feedback-hub://?tabid=2&appid=<PFN>!App`

<span data-ttu-id="ddf8c-126">You will need to substitute `<PFN>` with the Package Family Name of you extension.</span><span class="sxs-lookup"><span data-stu-id="ddf8c-126">You will need to substitute `<PFN>` with the Package Family Name of you extension.</span></span> <span data-ttu-id="ddf8c-127">This can be found under the **App identity** section for your extension in the Windows Dev Center.</span><span class="sxs-lookup"><span data-stu-id="ddf8c-127">This can be found under the **App identity** section for your extension in the Windows Dev Center.</span></span>

## <span data-ttu-id="ddf8c-128">Check out your ratings and reviews</span><span class="sxs-lookup"><span data-stu-id="ddf8c-128">Check out your ratings and reviews</span></span>
<span data-ttu-id="ddf8c-129">Log in regularly to check your user reviews and ratings.</span><span class="sxs-lookup"><span data-stu-id="ddf8c-129">Log in regularly to check your user reviews and ratings.</span></span> <span data-ttu-id="ddf8c-130">While the UWP app will only have info on the current user market, logging into the Windows Dev Center will display average rating across all markets.</span><span class="sxs-lookup"><span data-stu-id="ddf8c-130">While the UWP app will only have info on the current user market, logging into the Windows Dev Center will display average rating across all markets.</span></span>

## <span data-ttu-id="ddf8c-131">Respond to user reviews</span><span class="sxs-lookup"><span data-stu-id="ddf8c-131">Respond to user reviews</span></span>
<span data-ttu-id="ddf8c-132">You can respond to user reviews in the Microsoft Store through the Windows Dev Center's dashboard.</span><span class="sxs-lookup"><span data-stu-id="ddf8c-132">You can respond to user reviews in the Microsoft Store through the Windows Dev Center's dashboard.</span></span> <span data-ttu-id="ddf8c-133">Navigate to your extension and under Analytics select **Reviews**.</span><span class="sxs-lookup"><span data-stu-id="ddf8c-133">Navigate to your extension and under Analytics select **Reviews**.</span></span> <span data-ttu-id="ddf8c-134">A link will appear underneath each review that will allow you to respond directly to the customer.</span><span class="sxs-lookup"><span data-stu-id="ddf8c-134">A link will appear underneath each review that will allow you to respond directly to the customer.</span></span> <span data-ttu-id="ddf8c-135">This channel of communication enables you to offer feedback, resolutions, or send a thank you for the review!</span><span class="sxs-lookup"><span data-stu-id="ddf8c-135">This channel of communication enables you to offer feedback, resolutions, or send a thank you for the review!</span></span>

![Submitting a response to a review](./media/reviews.png)
