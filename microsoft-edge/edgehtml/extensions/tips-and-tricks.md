---
description: 了解有关 Microsoft Edge 扩展的一些方便提示和技巧
title: 提示和技巧|扩展
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/03/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge， Web 开发， html， css， javascript， 开发人员， 扩展
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 8a5ea19152f5524d86d17d6f978c677c45f8f3a8
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11399349"
---
# <a name="tips-and-tricks"></a><span data-ttu-id="db493-104">提示和技巧</span><span class="sxs-lookup"><span data-stu-id="db493-104">Tips and tricks</span></span>  

[!INCLUDE [deprecation-note](includes/deprecation-note.md)]  

<span data-ttu-id="db493-105">无论你当前是使用 Microsoft Edge 扩展还是已经发布了一个，以下提示和技巧都可能会派上用场。</span><span class="sxs-lookup"><span data-stu-id="db493-105">Whether you're currently working on a Microsoft Edge extension or have already published one, the following tips and tricks might come in handy.</span></span>  

## <a name="get-a-direct-link-to-your-extension-in-the-microsoft-store"></a><span data-ttu-id="db493-106">在 Microsoft Store 中获取指向扩展的直接链接</span><span class="sxs-lookup"><span data-stu-id="db493-106">Get a direct link to your extension in the Microsoft Store</span></span>  

<span data-ttu-id="db493-107">在 Windows 开发人员中心仪表板中，可以在 Microsoft Store 中找到指向扩展的直接链接。</span><span class="sxs-lookup"><span data-stu-id="db493-107">In the Windows Dev Center dashboard, you can find a direct link to your extension in the Microsoft Store.</span></span>  <span data-ttu-id="db493-108">此链接可用于广告和共享扩展。</span><span class="sxs-lookup"><span data-stu-id="db493-108">This link can be useful for advertising and sharing out your extension.</span></span>  

<span data-ttu-id="db493-109">登录到 Windows 开发人员中心并通过仪表板导航到扩展后，在应用标识页面上，你将在应用商店协议链接行 **中** 找到链接：</span><span class="sxs-lookup"><span data-stu-id="db493-109">After logging in to the Windows Dev Center and navigating to your extension through the dashboard, on the App identity page you’ll find the link in the **Store protocol link** row:</span></span>  

![存储协议链接](./media/store-link.png)  
 
## <a name="make-sure-youre-following-the-microsoft-store-policy"></a><span data-ttu-id="db493-111">确保你遵循 Microsoft Store 策略</span><span class="sxs-lookup"><span data-stu-id="db493-111">Make sure you’re following the Microsoft Store Policy</span></span>  

<span data-ttu-id="db493-112">创建扩展时，请务必记住提交到 Microsoft Store 的准则，该指南在 Microsoft Store 策略 [中突出显示](/windows/uwp/publish/store-policies)。</span><span class="sxs-lookup"><span data-stu-id="db493-112">When creating your extension, make sure you keep in mind the guidelines for submitting to the Microsoft Store highlighted in the [Microsoft Store Policy](/windows/uwp/publish/store-policies).</span></span>  
 
<span data-ttu-id="db493-113">Microsoft Edge 扩展还有一组要遵循的其他策略，在此处 [看到](/windows/uwp/publish/store-policies#pol_10_12)。</span><span class="sxs-lookup"><span data-stu-id="db493-113">Microsoft Edge extensions also have an additional set of policies to follow seen [here](/windows/uwp/publish/store-policies#pol_10_12).</span></span>  

## <a name="improve-your-extensions-discoverability-in-the-microsoft-store"></a><span data-ttu-id="db493-114">在 Microsoft Store 中提高扩展的可发现性</span><span class="sxs-lookup"><span data-stu-id="db493-114">Improve your extension’s discoverability in the Microsoft Store</span></span>  

<span data-ttu-id="db493-115">你可以向扩展提交添加关键字，以通过搜索来提高其可发现性。</span><span class="sxs-lookup"><span data-stu-id="db493-115">You can add keywords to your extension submission to improve its discoverability through searches.</span></span>  <span data-ttu-id="db493-116">例如，`Microsoft Edge Extensions` 和 `name of my extension`。</span><span class="sxs-lookup"><span data-stu-id="db493-116">For example, `Microsoft Edge Extensions` and `name of my extension`.</span></span>  

<span data-ttu-id="db493-117">这可以在 Windows 开发人员中心扩展的说明部分下完成。</span><span class="sxs-lookup"><span data-stu-id="db493-117">This can be done in the Windows Dev Center under the description section of your extension.</span></span>  <span data-ttu-id="db493-118">需要为扩展支持的每种语言添加这些关键字。</span><span class="sxs-lookup"><span data-stu-id="db493-118">These keywords will need to be added for every language your extension supports.</span></span>  

![使用关键字提交评价回复](./media/keywords.png)  

## <a name="automate-your-submission-to-the-microsoft-store"></a><span data-ttu-id="db493-120">自动提交到 Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="db493-120">Automate your submission to the Microsoft Store</span></span>  

<span data-ttu-id="db493-121">通过使用新的 Microsoft Store 提交 API，你可以自动执行并简化提交到 Microsoft Store，这允许你更新应用/游戏、加载项 \(应用内购买\) ，并通过 REST API 打包测试。</span><span class="sxs-lookup"><span data-stu-id="db493-121">You can automate and streamline your submissions to the Microsoft Store by using the new Microsoft Store Submission API, which allows you to update apps/games, add-ons \(in-app purchases\), and package flights through a REST API.</span></span>  <span data-ttu-id="db493-122">请查看文档 [和示例或使用](/windows/uwp/monetize/create-and-manage-submissions-using-windows-store-services) 开源提交 [API VSTS 扩展](https://github.com/Microsoft/windows-dev-center-vsts-extension) 开始。</span><span class="sxs-lookup"><span data-stu-id="db493-122">Check out the [documentation and samples](/windows/uwp/monetize/create-and-manage-submissions-using-windows-store-services) or use the open source [Submission API VSTS extension](https://github.com/Microsoft/windows-dev-center-vsts-extension) to get started.</span></span>  

## <a name="use-the-windows-feedback-hub-to-gather-feedbackreviewsfeature-requests"></a><span data-ttu-id="db493-123">使用 Windows 反馈中心收集反馈/评论/功能请求</span><span class="sxs-lookup"><span data-stu-id="db493-123">Use the Windows Feedback Hub to gather feedback/reviews/feature requests</span></span>  

<span data-ttu-id="db493-124">可以通过嵌入指向扩展的链接，将用户引导到扩展的 Windows 反馈中心子类别。</span><span class="sxs-lookup"><span data-stu-id="db493-124">You can direct users to the Windows Feedback Hub subcategory for your extension by embedding a link that points to it.</span></span>  <span data-ttu-id="db493-125">需要按照以下格式创建此链接：</span><span class="sxs-lookup"><span data-stu-id="db493-125">This link will need to be created using the following format:</span></span>  

```text
feedback-hub://?tabid=2&appid=<PFN>!App
```  

<span data-ttu-id="db493-126">你将需要替换为 `<PFN>` 扩展的程序包系列名称。</span><span class="sxs-lookup"><span data-stu-id="db493-126">You will need to substitute `<PFN>` with the Package Family Name of you extension.</span></span>  <span data-ttu-id="db493-127">这可在 Windows 开发人员 **中心扩展的应用** 标识部分下找到。</span><span class="sxs-lookup"><span data-stu-id="db493-127">This can be found under the **App identity** section for your extension in the Windows Dev Center.</span></span>  

## <a name="check-out-your-ratings-and-reviews"></a><span data-ttu-id="db493-128">查看评分和评论</span><span class="sxs-lookup"><span data-stu-id="db493-128">Check out your ratings and reviews</span></span>  

<span data-ttu-id="db493-129">定期登录以检查用户评论和评级。</span><span class="sxs-lookup"><span data-stu-id="db493-129">Log in regularly to check your user reviews and ratings.</span></span>  <span data-ttu-id="db493-130">尽管 UWP 应用将仅包含当前用户市场的信息，但登录到 Windows 开发人员中心将显示所有市场的平均评分。</span><span class="sxs-lookup"><span data-stu-id="db493-130">While the UWP app will only have info on the current user market, logging into the Windows Dev Center will display average rating across all markets.</span></span>  

## <a name="respond-to-user-reviews"></a><span data-ttu-id="db493-131">回复用户评论</span><span class="sxs-lookup"><span data-stu-id="db493-131">Respond to user reviews</span></span>  

<span data-ttu-id="db493-132">可以通过 Windows 开发人员中心的仪表板在 Microsoft Store 中回复用户评论。</span><span class="sxs-lookup"><span data-stu-id="db493-132">You can respond to user reviews in the Microsoft Store through the Windows Dev Center's dashboard.</span></span>  <span data-ttu-id="db493-133">导航到你的扩展，并在"分析"下选择 **"评价"。**</span><span class="sxs-lookup"><span data-stu-id="db493-133">Navigate to your extension and under Analytics select **Reviews**.</span></span>  <span data-ttu-id="db493-134">每个评论下方都会显示一个链接，允许你直接回复客户。</span><span class="sxs-lookup"><span data-stu-id="db493-134">A link will appear underneath each review that will allow you to respond directly to the customer.</span></span>  <span data-ttu-id="db493-135">通过此通信渠道，你可以提供反馈、解决方案或发送对评价的感谢！</span><span class="sxs-lookup"><span data-stu-id="db493-135">This channel of communication enables you to offer feedback, resolutions, or send a thank you for the review!</span></span>  

![回复用户评论](./media/reviews.png)  
