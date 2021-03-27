---
description: 将用户从 Microsoft Edge Internet Explorer
title: 将用户从 Microsoft Edge Internet Explorer
author: MSEdgeTeam
ms.date: 11/13/2020
ms.author: msedgedevrel
ms.prod: microsoft-edge
keywords: microsoft edge， 兼容性， Web 平台， Internet Explorer
ms.openlocfilehash: c2106955ed79bd28dc1f847dee220944bb014689
ms.sourcegitcommit: bff24ab1f0a66aaf4c7f5ff81cea3eb28c6d8380
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/26/2021
ms.locfileid: "11461134"
---
# <a name="moving-users-to-microsoft-edge-from-internet-explorer"></a><span data-ttu-id="765e0-104">将用户从 Microsoft Edge Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="765e0-104">Moving users to Microsoft Edge from Internet Explorer</span></span>  

<span data-ttu-id="765e0-105">许多新式网站具有的设计与 Internet Explorer \ (IE\) 。</span><span class="sxs-lookup"><span data-stu-id="765e0-105">Many modern websites have designs that are incompatible with Internet Explorer \(IE\).</span></span>  <span data-ttu-id="765e0-106">当 IE 用户访问不兼容的公共网站时，用户可能会收到一条消息。</span><span class="sxs-lookup"><span data-stu-id="765e0-106">When an IE user visits an incompatible public website, the user may get a message.</span></span>  <span data-ttu-id="765e0-107">该消息表明该网站与浏览器不兼容。</span><span class="sxs-lookup"><span data-stu-id="765e0-107">The message states that the website is incompatible with the browser.</span></span>  <span data-ttu-id="765e0-108">消息显示后，用户需要手动切换到新式浏览器。</span><span class="sxs-lookup"><span data-stu-id="765e0-108">After the message is displayed, the user is expected to manually switch to a modern browser.</span></span>  <span data-ttu-id="765e0-109">为了最大限度地减少中断，从版本 84 开始，Microsoft Edge 支持自动重定向用户的新功能。</span><span class="sxs-lookup"><span data-stu-id="765e0-109">To minimize disruptions, starting with version 84, Microsoft Edge supports a new capability that automatically redirects users.</span></span>  <span data-ttu-id="765e0-110">当 IE 用户导航到与 IE 不兼容的网站时，Windows 会自动将用户重定向到 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="765e0-110">When an IE user navigates to a website that is incompatible with IE, Windows automatically redirects the user to Microsoft Edge.</span></span>  <span data-ttu-id="765e0-111">To review the websites on the list， navigate to [Need Microsoft Edge list][MicrosoftEdgeNeededgeV1].</span><span class="sxs-lookup"><span data-stu-id="765e0-111">To review the websites on the list, navigate to [Need Microsoft Edge list][MicrosoftEdgeNeededgeV1].</span></span>

<span data-ttu-id="765e0-112">本文介绍以下概念。</span><span class="sxs-lookup"><span data-stu-id="765e0-112">This article describes the following concepts.</span></span>  

*   <span data-ttu-id="765e0-113">网站添加到列表的原因</span><span class="sxs-lookup"><span data-stu-id="765e0-113">Why a website is added to the list</span></span>  
*   <span data-ttu-id="765e0-114">重定向的用户体验</span><span class="sxs-lookup"><span data-stu-id="765e0-114">The user experience for redirection</span></span>  
*   <span data-ttu-id="765e0-115">请求更新列表</span><span class="sxs-lookup"><span data-stu-id="765e0-115">Request an update to the list</span></span>  
    
## <a name="why-is-a-website-added-to-the-ie-compatibility-list"></a><span data-ttu-id="765e0-116">为什么将网站添加到 IE 兼容性列表？</span><span class="sxs-lookup"><span data-stu-id="765e0-116">Why is a website added to the IE compatibility list?</span></span>  

<span data-ttu-id="765e0-117">IE 兼容性列表仅在发生以下操作时添加网站。</span><span class="sxs-lookup"><span data-stu-id="765e0-117">The IE compatibility List only adds a website when the following actions occur.</span></span>  

*   <span data-ttu-id="765e0-118">向 IE 用户显示一条消息，建议出于兼容性原因，用户应使用不同的浏览器。</span><span class="sxs-lookup"><span data-stu-id="765e0-118">Shows an IE user a message suggesting the user should use a different browser for compatibility reasons.</span></span>  
*   <span data-ttu-id="765e0-119">所有者请求将网站添加到 IE 兼容性列表。</span><span class="sxs-lookup"><span data-stu-id="765e0-119">Owner requests to add the website to the IE compatibility list.</span></span>  

## <a name="redirection-experience"></a><span data-ttu-id="765e0-120">重定向体验</span><span class="sxs-lookup"><span data-stu-id="765e0-120">Redirection experience</span></span>

<span data-ttu-id="765e0-121">重定向到 Microsoft Edge 时，用户会显示下一张屏幕截图中的一次对话框。</span><span class="sxs-lookup"><span data-stu-id="765e0-121">On redirection to Microsoft Edge, the user is shown the one-time dialog in the next screenshot.</span></span>  <span data-ttu-id="765e0-122">该对话框为用户提供以下信息。</span><span class="sxs-lookup"><span data-stu-id="765e0-122">The dialog provides the user with the following information.</span></span>  

*   <span data-ttu-id="765e0-123">它说明了重定向网站的原因。</span><span class="sxs-lookup"><span data-stu-id="765e0-123">It explains why the website is being redirected.</span></span>  
*   <span data-ttu-id="765e0-124">它会提示用户同意将浏览数据和首选项从 IE 复制到 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="765e0-124">It prompts the user for consent to copy browsing data and preferences from IE to Microsoft Edge.</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="765e0-125">将导入以下浏览数据。</span><span class="sxs-lookup"><span data-stu-id="765e0-125">The following browsing data is imported.</span></span>  
      
      *   <span data-ttu-id="765e0-126">收藏夹</span><span class="sxs-lookup"><span data-stu-id="765e0-126">Favorites</span></span>  
      *   <span data-ttu-id="765e0-127">密码</span><span class="sxs-lookup"><span data-stu-id="765e0-127">Passwords</span></span>  
      *   <span data-ttu-id="765e0-128">搜索引擎</span><span class="sxs-lookup"><span data-stu-id="765e0-128">Search engines</span></span>  
      *   <span data-ttu-id="765e0-129">打开选项卡</span><span class="sxs-lookup"><span data-stu-id="765e0-129">Open tabs</span></span>  
      *   <span data-ttu-id="765e0-130">历史记录</span><span class="sxs-lookup"><span data-stu-id="765e0-130">History</span></span>  
      *   <span data-ttu-id="765e0-131">“设置”</span><span class="sxs-lookup"><span data-stu-id="765e0-131">Settings</span></span>  
      *   <span data-ttu-id="765e0-132">Cookie</span><span class="sxs-lookup"><span data-stu-id="765e0-132">Cookies</span></span>  
      *   <span data-ttu-id="765e0-133">主页</span><span class="sxs-lookup"><span data-stu-id="765e0-133">The Home Page</span></span>  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/neededge-dialog1.msft.png" alt-text="浏览通知并提示导入数据和首选项" lightbox="../media/neededge-dialog1.msft.png":::
         <span data-ttu-id="765e0-135">浏览通知并提示导入数据和首选项</span><span class="sxs-lookup"><span data-stu-id="765e0-135">Browsing notification and prompt to import data and preferences</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::

<span data-ttu-id="765e0-136">如果用户未通过选中"始终显示我的浏览数据和首选项Internet Explorer复选框同意，用户可以选择"继续**浏览"** 以继续\*\*\*\*   浏览会话。</span><span class="sxs-lookup"><span data-stu-id="765e0-136">If the user does not consent by choosing the **Always bring over my browsing data and preferences from Internet Explorer** checkbox, the user may choose **Continue browsing** to continue the browsing session.</span></span>  

<span data-ttu-id="765e0-137">最后，网站不兼容横幅将显示在每个重定向的地址栏下。</span><span class="sxs-lookup"><span data-stu-id="765e0-137">Finally, a website incompatibility banner is displayed under the address bar for each redirection.</span></span>  <span data-ttu-id="765e0-138">下图显示了网站不兼容横幅的示例。</span><span class="sxs-lookup"><span data-stu-id="765e0-138">An example of a website incompatibility banner is displayed in following figure.</span></span>

:::image type="complex" source="../media/neededge-banner.msft.png" alt-text="有关新式站点的通知，并提示将 Microsoft Edge 设置为默认浏览器或浏览 Microsoft Edge" lightbox="../media/neededge-banner.msft.png":::
   <span data-ttu-id="765e0-140">有关新式站点的通知，并提示将 Microsoft Edge 设置为默认浏览器或浏览 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="765e0-140">Notification about modern sites and prompt to set Microsoft Edge as default browser or explore Microsoft Edge</span></span>  
:::image-end:::

<span data-ttu-id="765e0-141">网站不兼容横幅为用户提供了以下详细信息。</span><span class="sxs-lookup"><span data-stu-id="765e0-141">The website incompatibility banner provides the following details to the user.</span></span>  

*   <span data-ttu-id="765e0-142">建议用户切换到 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="765e0-142">Recommends that the user to switch to Microsoft Edge.</span></span>  
*   <span data-ttu-id="765e0-143">将 Microsoft Edge 设置为默认浏览器的产品/服务。</span><span class="sxs-lookup"><span data-stu-id="765e0-143">Offers to set Microsoft Edge as the default browser.</span></span>  
*   <span data-ttu-id="765e0-144">为用户提供浏览 Microsoft Edge 的选项。</span><span class="sxs-lookup"><span data-stu-id="765e0-144">Gives the user the option to explore Microsoft Edge.</span></span>    
    
<span data-ttu-id="765e0-145">将网站从 Internet Explorer Microsoft Edge 时，将发生以下操作之一。</span><span class="sxs-lookup"><span data-stu-id="765e0-145">When a website is redirected from Internet Explorer to Microsoft Edge, one of the following actions occurs.</span></span>

*   <span data-ttu-id="765e0-146">如果活动 IE 选项卡之前没有内容，它将关闭。</span><span class="sxs-lookup"><span data-stu-id="765e0-146">If the active IE tab had no prior content, it is closed.</span></span>  
*   <span data-ttu-id="765e0-147">如果活动 IE 选项卡之前包含内容，它将导航到 [Microsoft][MicrosoftSupportOfficeTheWebsiteYouWereTryingToReachDoesntWorkWithInternetExplorer]支持页面，说明网站被重定向到 Microsoft Edge 的原因。</span><span class="sxs-lookup"><span data-stu-id="765e0-147">If the active IE tab had prior content, it navigates to the [Microsoft support page that explains why the website was redirected to Microsoft Edge][MicrosoftSupportOfficeTheWebsiteYouWereTryingToReachDoesntWorkWithInternetExplorer].</span></span>  

> [!NOTE]
> <span data-ttu-id="765e0-148">重定向后，用户可以继续对不在 IE 兼容性列表中的网站使用 IE。</span><span class="sxs-lookup"><span data-stu-id="765e0-148">After a redirection, users may continue to use IE for websites that are not on the IE compatibility list.</span></span>  

## <a name="request-an-update-to-the-ie-compatibility-list"></a><span data-ttu-id="765e0-149">请求更新 IE 兼容性列表</span><span class="sxs-lookup"><span data-stu-id="765e0-149">Request an update to the IE compatibility list</span></span>  

<span data-ttu-id="765e0-150">IE 兼容性列表是上一个 XML [microsoft.com。][MicrosoftOfficialHome]</span><span class="sxs-lookup"><span data-stu-id="765e0-150">The IE compatibility list is an XML file on [microsoft.com][MicrosoftOfficialHome].</span></span>  <span data-ttu-id="765e0-151">此列表会定期更新，以响应用户和网站开发人员有关添加或删除网站的请求。</span><span class="sxs-lookup"><span data-stu-id="765e0-151">The list is regularly updated in response to user and website developer requests to have websites added or removed.</span></span>  <span data-ttu-id="765e0-152">对列表的更新会自动下载到用户计算机。</span><span class="sxs-lookup"><span data-stu-id="765e0-152">Updates to the list are automatically downloaded to user machines.</span></span>  

<span data-ttu-id="765e0-153">通过电子邮件将以下信息 [ietoedge@microsoft.com][MailtoMicrosoftIetoedge] IE 兼容性列表中添加或删除的网站。</span><span class="sxs-lookup"><span data-stu-id="765e0-153">Email the following information to [ietoedge@microsoft.com][MailtoMicrosoftIetoedge] for your website to be added or removed from the IE compatibility list.</span></span>    

*   <span data-ttu-id="765e0-154">所有者名称</span><span class="sxs-lookup"><span data-stu-id="765e0-154">Owner name</span></span>  
*   <span data-ttu-id="765e0-155">公司标题</span><span class="sxs-lookup"><span data-stu-id="765e0-155">Corporate title</span></span>  
*   <span data-ttu-id="765e0-156">电子邮件地址</span><span class="sxs-lookup"><span data-stu-id="765e0-156">Email address</span></span>  
*   <span data-ttu-id="765e0-157">公司名称</span><span class="sxs-lookup"><span data-stu-id="765e0-157">Company name</span></span>  
*   <span data-ttu-id="765e0-158">街道地址</span><span class="sxs-lookup"><span data-stu-id="765e0-158">Street address</span></span>  
*   <span data-ttu-id="765e0-159">网站地址</span><span class="sxs-lookup"><span data-stu-id="765e0-159">Website address</span></span>  
    
<span data-ttu-id="765e0-160">IE 兼容性列表在一周内更新。</span><span class="sxs-lookup"><span data-stu-id="765e0-160">The IE compatibility list is updated within a week.</span></span>

> [!NOTE]
> <span data-ttu-id="765e0-161">IE 兼容性列表设计为仅适用于公共网站。</span><span class="sxs-lookup"><span data-stu-id="765e0-161">The IE compatibility list is designed to work with public sites only.</span></span>  

<!-- links -->  

[MailtoMicrosoftIetoedge]: mailto:ietoedge@microsoft.com "向用户发送电子邮件 ietoedge@microsoft.com"  

[MicrosoftOfficialHome]: https://www.microsoft.com "Microsoft 官方主页"  

[MicrosoftEdgeNeededgeV1]:  https://edge.microsoft.com/neededge/v1 "需要 Microsoft Edge 列表 v1 xml |Microsoft Edge"  

[MicrosoftSupportOfficeTheWebsiteYouWereTryingToReachDoesntWorkWithInternetExplorer]: https://support.microsoft.com/office/the-website-you-were-trying-to-reach-doesn-t-work-with-internet-explorer-8f5fc675-cd47-414c-9535-12821ddfc554 "尝试访问的网站无法与Internet Explorer |Microsoft Office支持"  
