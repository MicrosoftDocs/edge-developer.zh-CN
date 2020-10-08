---
description: 了解有关 Microsoft Edge 扩展的一些便捷提示和技巧
title: 扩展-提示和技巧
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/16/2019
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘、web 开发、html、css、javascript、开发人员、扩展
ms.openlocfilehash: db15aa49649432a6c4400b4e6830501c40485a83
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563226"
---
# <span data-ttu-id="5e2ae-104">提示和技巧</span><span class="sxs-lookup"><span data-stu-id="5e2ae-104">Tips and tricks</span></span>  

[!INCLUDE [deprecation-note](includes/deprecation-note.md)]  

<span data-ttu-id="5e2ae-105">无论您当前正在处理的是 Microsoft Edge 扩展还是已经发布过，以下提示和技巧都可能会很方便。</span><span class="sxs-lookup"><span data-stu-id="5e2ae-105">Whether you're currently working on a Microsoft Edge extension or have already published one, the following tips and tricks might come in handy.</span></span>

## <span data-ttu-id="5e2ae-106">在 Microsoft Store 中获取指向您的扩展的直接链接</span><span class="sxs-lookup"><span data-stu-id="5e2ae-106">Get a direct link to your extension in the Microsoft Store</span></span>
<span data-ttu-id="5e2ae-107">在 Windows 开发人员中心仪表板中，你可以在 Microsoft Store 中找到指向你的扩展的直接链接。</span><span class="sxs-lookup"><span data-stu-id="5e2ae-107">In the Windows Dev Center dashboard, you can find a direct link to your extension in the Microsoft Store.</span></span> <span data-ttu-id="5e2ae-108">此链接对于广告和分享您的分机很有用。</span><span class="sxs-lookup"><span data-stu-id="5e2ae-108">This link can be useful for advertising and sharing out your extension.</span></span>


<span data-ttu-id="5e2ae-109">登录到 Windows 开发人员中心并通过仪表板导航到您的扩展后，在 "应用标识" 页面上，您将在 "应用程序标识" 页面上找到 "应用 **商店协议" 链接** 行的链接：</span><span class="sxs-lookup"><span data-stu-id="5e2ae-109">After logging in to the Windows Dev Center and navigating to your extension through the dashboard, on the App identity page you’ll find the link in the **Store protocol link** row:</span></span>

![存储协议链接](./media/store-link.png)
 
## <span data-ttu-id="5e2ae-111">请确保你关注的是 Microsoft Store 策略</span><span class="sxs-lookup"><span data-stu-id="5e2ae-111">Make sure you’re following the Microsoft Store Policy</span></span>
<span data-ttu-id="5e2ae-112">创建扩展时，请务必记住提交到 microsoft [Store 策略](https://msdn.microsoft.com/library/windows/apps/dn764944.aspx)中突出显示的 microsoft store 的指南。</span><span class="sxs-lookup"><span data-stu-id="5e2ae-112">When creating your extension, make sure you keep in mind the guidelines for submitting to the Microsoft Store highlighted in the [Microsoft Store Policy](https://msdn.microsoft.com/library/windows/apps/dn764944.aspx).</span></span> 
 
<span data-ttu-id="5e2ae-113">Microsoft Edge 扩展还包含一组要[关注的其他策略。](https://msdn.microsoft.com/library/windows/apps/dn764944.aspx#pol_10_12)</span><span class="sxs-lookup"><span data-stu-id="5e2ae-113">Microsoft Edge extensions also have an additional set of policies to follow seen [here](https://msdn.microsoft.com/library/windows/apps/dn764944.aspx#pol_10_12).</span></span>

## <span data-ttu-id="5e2ae-114">改善扩展在 Microsoft Store 中的可发现性</span><span class="sxs-lookup"><span data-stu-id="5e2ae-114">Improve your extension’s discoverability in the Microsoft Store</span></span>

<span data-ttu-id="5e2ae-115">你可以将关键字添加到你的扩展提交，以通过搜索 imporove 它的发现。</span><span class="sxs-lookup"><span data-stu-id="5e2ae-115">You can add keywords to your extension submission to imporove its discoverability through searches.</span></span> <span data-ttu-id="5e2ae-116">例如，"Microsoft Edge 扩展" 和 "我的扩展名的名称"。</span><span class="sxs-lookup"><span data-stu-id="5e2ae-116">For example, "Microsoft Edge Extensions" and "name of my extension".</span></span> 

<span data-ttu-id="5e2ae-117">可以在 Windows 开发人员中心中的扩展的 "说明" 部分下执行此操作。</span><span class="sxs-lookup"><span data-stu-id="5e2ae-117">This can be done in the Windows Dev Center under the description section of your extension.</span></span> <span data-ttu-id="5e2ae-118">对于扩展支持的每种语言，都需要添加这些关键字。</span><span class="sxs-lookup"><span data-stu-id="5e2ae-118">These keywords will need to be added for every language your extension supports.</span></span>

![提交对审阅的答复](./media/keywords.png)

## <span data-ttu-id="5e2ae-120">自动提交到 Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="5e2ae-120">Automate your submission to the Microsoft Store</span></span>
<span data-ttu-id="5e2ae-121">你可以使用新的 Microsoft Store 提交 API 自动化和优化 Microsoft Store 的提交，该 API 允许你更新应用/游戏、加载项 (应用内购买) 以及通过 REST API 包装航班。</span><span class="sxs-lookup"><span data-stu-id="5e2ae-121">You can automate and streamline your submissions to the Microsoft Store by using the new Microsoft Store Submission API, which allows you to update apps/games, add-ons (in-app purchases), and package flights through a REST API.</span></span> <span data-ttu-id="5e2ae-122">查看 [文档和示例](https://docs.microsoft.com/windows/uwp/monetize/create-and-manage-submissions-using-windows-store-services) ，或使用 "打开源 [提交 API VSTS 扩展](https://github.com/Microsoft/windows-dev-center-vsts-extension) " 开始。</span><span class="sxs-lookup"><span data-stu-id="5e2ae-122">Check out the [documentation and samples](https://docs.microsoft.com/windows/uwp/monetize/create-and-manage-submissions-using-windows-store-services) or use the open source [Submission API VSTS extension](https://github.com/Microsoft/windows-dev-center-vsts-extension) to get started.</span></span>

## <span data-ttu-id="5e2ae-123">使用 Windows 反馈中心收集反馈/评论/功能请求</span><span class="sxs-lookup"><span data-stu-id="5e2ae-123">Use the Windows Feedback Hub to gather feedback/reviews/feature requests</span></span>

<span data-ttu-id="5e2ae-124">你可以通过嵌入指向扩展的链接来将用户定向到你的扩展的 Windows 反馈中心子类别。</span><span class="sxs-lookup"><span data-stu-id="5e2ae-124">You can direct users to the Windows Feedback Hub subcategory for your extension by embedding a link that points to it.</span></span> <span data-ttu-id="5e2ae-125">此链接将需要使用以下格式创建：</span><span class="sxs-lookup"><span data-stu-id="5e2ae-125">This link will need to be created using the following format:</span></span> 

`feedback-hub://?tabid=2&appid=<PFN>!App`

<span data-ttu-id="5e2ae-126">你需要替换 `<PFN>` 为你的扩展的程序包系列名称。</span><span class="sxs-lookup"><span data-stu-id="5e2ae-126">You will need to substitute `<PFN>` with the Package Family Name of you extension.</span></span> <span data-ttu-id="5e2ae-127">这可以在 Windows 开发人员中心中的扩展的 **应用标识** 部分下找到。</span><span class="sxs-lookup"><span data-stu-id="5e2ae-127">This can be found under the **App identity** section for your extension in the Windows Dev Center.</span></span>

## <span data-ttu-id="5e2ae-128">查看您的评级和评论</span><span class="sxs-lookup"><span data-stu-id="5e2ae-128">Check out your ratings and reviews</span></span>
<span data-ttu-id="5e2ae-129">定期登录，检查您的用户评论和评价。</span><span class="sxs-lookup"><span data-stu-id="5e2ae-129">Log in regularly to check your user reviews and ratings.</span></span> <span data-ttu-id="5e2ae-130">虽然 UWP 应用只有当前用户市场的信息，但登录到 Windows 开发人员中心的信息将显示所有市场的平均分级。</span><span class="sxs-lookup"><span data-stu-id="5e2ae-130">While the UWP app will only have info on the current user market, logging into the Windows Dev Center will display average rating across all markets.</span></span>

## <span data-ttu-id="5e2ae-131">响应用户评论</span><span class="sxs-lookup"><span data-stu-id="5e2ae-131">Respond to user reviews</span></span>
<span data-ttu-id="5e2ae-132">你可以通过 Windows 开发人员中心的仪表板来响应 Microsoft Store 中的用户评论。</span><span class="sxs-lookup"><span data-stu-id="5e2ae-132">You can respond to user reviews in the Microsoft Store through the Windows Dev Center's dashboard.</span></span> <span data-ttu-id="5e2ae-133">导航到您的扩展，并在 "分析" 下选择 " **评论**"。</span><span class="sxs-lookup"><span data-stu-id="5e2ae-133">Navigate to your extension and under Analytics select **Reviews**.</span></span> <span data-ttu-id="5e2ae-134">每个评论下将显示一个链接，允许您直接答复客户。</span><span class="sxs-lookup"><span data-stu-id="5e2ae-134">A link will appear underneath each review that will allow you to respond directly to the customer.</span></span> <span data-ttu-id="5e2ae-135">此通信渠道使你能够提供反馈、解决方法或向你发送一则感谢你的评论！</span><span class="sxs-lookup"><span data-stu-id="5e2ae-135">This channel of communication enables you to offer feedback, resolutions, or send a thank you for the review!</span></span>

![提交对审阅的答复](./media/reviews.png)
