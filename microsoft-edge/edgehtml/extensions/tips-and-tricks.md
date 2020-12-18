---
description: 了解有关 Microsoft Edge 扩展的一些方便提示和技巧
title: 提示和技巧 |扩展
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge， Web 开发， html， css， javascript， 开发人员， 扩展
ms.date: 12/15/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: cd512085f13b76c5a8e474301ef296612eeb0414
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232244"
---
# <span data-ttu-id="ac550-104">提示和技巧</span><span class="sxs-lookup"><span data-stu-id="ac550-104">Tips and tricks</span></span>  

[!INCLUDE [deprecation-note](includes/deprecation-note.md)]  

<span data-ttu-id="ac550-105">无论你当前是使用 Microsoft Edge 扩展还是已经发布了一个，以下提示和技巧都很方便。</span><span class="sxs-lookup"><span data-stu-id="ac550-105">Whether you're currently working on a Microsoft Edge extension or have already published one, the following tips and tricks might come in handy.</span></span>

## <span data-ttu-id="ac550-106">在 Microsoft Store 中获取指向扩展的直接链接</span><span class="sxs-lookup"><span data-stu-id="ac550-106">Get a direct link to your extension in the Microsoft Store</span></span>

<span data-ttu-id="ac550-107">在 Windows 开发人员中心仪表板中，可以在 Microsoft Store 中查找指向扩展的直接链接。</span><span class="sxs-lookup"><span data-stu-id="ac550-107">In the Windows Dev Center dashboard, you can find a direct link to your extension in the Microsoft Store.</span></span> <span data-ttu-id="ac550-108">此链接可用于广告和共享扩展。</span><span class="sxs-lookup"><span data-stu-id="ac550-108">This link can be useful for advertising and sharing out your extension.</span></span>

<span data-ttu-id="ac550-109">登录到 Windows 开发人员中心并通过仪表板导航到扩展后，在应用标识页面上，你将在应用商店协议链接行 **中** 找到链接：</span><span class="sxs-lookup"><span data-stu-id="ac550-109">After logging in to the Windows Dev Center and navigating to your extension through the dashboard, on the App identity page you’ll find the link in the **Store protocol link** row:</span></span>

![存储协议链接](./media/store-link.png)
 
## <span data-ttu-id="ac550-111">确保你遵循 Microsoft Store 策略</span><span class="sxs-lookup"><span data-stu-id="ac550-111">Make sure you’re following the Microsoft Store Policy</span></span>

<span data-ttu-id="ac550-112">创建扩展时，请务必记住提交到 Microsoft Store 的指南，该准则在 Microsoft Store 策略 [中突出显示](https://msdn.microsoft.com/library/windows/apps/dn764944.aspx)。</span><span class="sxs-lookup"><span data-stu-id="ac550-112">When creating your extension, make sure you keep in mind the guidelines for submitting to the Microsoft Store highlighted in the [Microsoft Store Policy](https://msdn.microsoft.com/library/windows/apps/dn764944.aspx).</span></span> 
 
<span data-ttu-id="ac550-113">Microsoft Edge 扩展还有一组要遵循的其他策略，在此处 [可以看到](https://msdn.microsoft.com/library/windows/apps/dn764944.aspx#pol_10_12)。</span><span class="sxs-lookup"><span data-stu-id="ac550-113">Microsoft Edge extensions also have an additional set of policies to follow seen [here](https://msdn.microsoft.com/library/windows/apps/dn764944.aspx#pol_10_12).</span></span>

## <span data-ttu-id="ac550-114">提高扩展在 Microsoft Store 中的可发现性</span><span class="sxs-lookup"><span data-stu-id="ac550-114">Improve your extension’s discoverability in the Microsoft Store</span></span>

<span data-ttu-id="ac550-115">你可以向扩展提交添加关键字，以通过搜索提高其可发现性。</span><span class="sxs-lookup"><span data-stu-id="ac550-115">You can add keywords to your extension submission to improve its discoverability through searches.</span></span> <span data-ttu-id="ac550-116">例如，"Microsoft Edge Extensions"和"name of my extension"。</span><span class="sxs-lookup"><span data-stu-id="ac550-116">For example, "Microsoft Edge Extensions" and "name of my extension".</span></span> 

<span data-ttu-id="ac550-117">这可以在 Windows 开发人员中心中的扩展说明部分下完成。</span><span class="sxs-lookup"><span data-stu-id="ac550-117">This can be done in the Windows Dev Center under the description section of your extension.</span></span> <span data-ttu-id="ac550-118">需要为扩展支持的每种语言添加这些关键字。</span><span class="sxs-lookup"><span data-stu-id="ac550-118">These keywords will need to be added for every language your extension supports.</span></span>

![提交评价回复 - 关键字](./media/keywords.png)

## <span data-ttu-id="ac550-120">自动提交到 Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="ac550-120">Automate your submission to the Microsoft Store</span></span>

<span data-ttu-id="ac550-121">通过使用新的 Microsoft Store 提交 API，你可以自动完成并简化提交到 Microsoft Store，这允许你更新应用/游戏、加载项 (应用内购买) ，并通过 REST API 打包测试版本。</span><span class="sxs-lookup"><span data-stu-id="ac550-121">You can automate and streamline your submissions to the Microsoft Store by using the new Microsoft Store Submission API, which allows you to update apps/games, add-ons (in-app purchases), and package flights through a REST API.</span></span> <span data-ttu-id="ac550-122">请查看文档 [和示例或使用](https://docs.microsoft.com/windows/uwp/monetize/create-and-manage-submissions-using-windows-store-services) 开放源代码提交 API [VSTS 扩展](https://github.com/Microsoft/windows-dev-center-vsts-extension) 开始使用。</span><span class="sxs-lookup"><span data-stu-id="ac550-122">Check out the [documentation and samples](https://docs.microsoft.com/windows/uwp/monetize/create-and-manage-submissions-using-windows-store-services) or use the open source [Submission API VSTS extension](https://github.com/Microsoft/windows-dev-center-vsts-extension) to get started.</span></span>

## <span data-ttu-id="ac550-123">使用 Windows 反馈中心收集反馈/评论/功能请求</span><span class="sxs-lookup"><span data-stu-id="ac550-123">Use the Windows Feedback Hub to gather feedback/reviews/feature requests</span></span>

<span data-ttu-id="ac550-124">通过嵌入指向扩展的链接，你可以将用户引导到扩展的 Windows 反馈中心子类别。</span><span class="sxs-lookup"><span data-stu-id="ac550-124">You can direct users to the Windows Feedback Hub subcategory for your extension by embedding a link that points to it.</span></span> <span data-ttu-id="ac550-125">需要按照以下格式创建此链接：</span><span class="sxs-lookup"><span data-stu-id="ac550-125">This link will need to be created using the following format:</span></span> 

```text
feedback-hub://?tabid=2&appid=<PFN>!App
```  

<span data-ttu-id="ac550-126">你将需要替换为 `<PFN>` 扩展的程序包系列名称。</span><span class="sxs-lookup"><span data-stu-id="ac550-126">You will need to substitute `<PFN>` with the Package Family Name of you extension.</span></span> <span data-ttu-id="ac550-127">这可以在 Windows 开发人员中心内 **扩展的应用标识** 部分下找到。</span><span class="sxs-lookup"><span data-stu-id="ac550-127">This can be found under the **App identity** section for your extension in the Windows Dev Center.</span></span>

## <span data-ttu-id="ac550-128">查看你的评分和评论</span><span class="sxs-lookup"><span data-stu-id="ac550-128">Check out your ratings and reviews</span></span>

<span data-ttu-id="ac550-129">定期登录以检查用户评论和评级。</span><span class="sxs-lookup"><span data-stu-id="ac550-129">Log in regularly to check your user reviews and ratings.</span></span> <span data-ttu-id="ac550-130">尽管 UWP 应用将仅包含当前用户市场的信息，但登录到 Windows 开发人员中心将显示所有市场的平均评分。</span><span class="sxs-lookup"><span data-stu-id="ac550-130">While the UWP app will only have info on the current user market, logging into the Windows Dev Center will display average rating across all markets.</span></span>

## <span data-ttu-id="ac550-131">回复用户评论</span><span class="sxs-lookup"><span data-stu-id="ac550-131">Respond to user reviews</span></span>

<span data-ttu-id="ac550-132">可以通过 Windows 开发人员中心仪表板回复 Microsoft Store 中的用户评论。</span><span class="sxs-lookup"><span data-stu-id="ac550-132">You can respond to user reviews in the Microsoft Store through the Windows Dev Center's dashboard.</span></span> <span data-ttu-id="ac550-133">导航到扩展，并在"分析"下选择 **"评价"。**</span><span class="sxs-lookup"><span data-stu-id="ac550-133">Navigate to your extension and under Analytics select **Reviews**.</span></span> <span data-ttu-id="ac550-134">每个评论下方都会显示一个链接，可让你直接回复客户。</span><span class="sxs-lookup"><span data-stu-id="ac550-134">A link will appear underneath each review that will allow you to respond directly to the customer.</span></span> <span data-ttu-id="ac550-135">通过此通信渠道，你可以提供反馈、解决方案或发送对评价的感谢！</span><span class="sxs-lookup"><span data-stu-id="ac550-135">This channel of communication enables you to offer feedback, resolutions, or send a thank you for the review!</span></span>

![提交评价回复](./media/reviews.png)
