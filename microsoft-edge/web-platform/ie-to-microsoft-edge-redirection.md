---
description: 从 Internet Explorer 将用户移动到 Microsoft Edge
title: 从 Internet Explorer 将用户移动到 Microsoft Edge
author: MSEdgeTeam
ms.date: 11/04/2020
ms.author: msedgedevrel
ms.prod: microsoft-edge
keywords: microsoft edge、兼容性、web 平台、internet explorer
ms.openlocfilehash: 48f0f4121fb444d80603dcbb408397679c64753d
ms.sourcegitcommit: 7b4441b7656c8317139650f904b70cc87797d37e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2020
ms.locfileid: "11154328"
---
# <span data-ttu-id="02e59-104">从 Internet Explorer 将用户移动到 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="02e59-104">Moving users to Microsoft Edge from Internet Explorer</span></span> 

<span data-ttu-id="02e59-105">许多现代网站的设计与 Internet Explorer 不兼容 (IE \ ) 。</span><span class="sxs-lookup"><span data-stu-id="02e59-105">Many modern websites have designs that are incompatible with Internet Explorer \(IE\).</span></span>  <span data-ttu-id="02e59-106">当 IE 用户访问不兼容的公共网站时，用户可能会收到一条消息。</span><span class="sxs-lookup"><span data-stu-id="02e59-106">When an IE user visits an incompatible public website, the user may get a message.</span></span>  <span data-ttu-id="02e59-107">该消息表明网站与浏览器不兼容。</span><span class="sxs-lookup"><span data-stu-id="02e59-107">The message states that the website is incompatible with the browser.</span></span>  <span data-ttu-id="02e59-108">消息显示后，用户应手动切换到新式浏览器。</span><span class="sxs-lookup"><span data-stu-id="02e59-108">After the message is displayed, the user is expected to manually switch to a modern browser.</span></span>  <span data-ttu-id="02e59-109">为了最大程度地减少中断（从版本84开始），Microsoft Edge 支持自动重定向用户的新功能。</span><span class="sxs-lookup"><span data-stu-id="02e59-109">To minimize disruptions, starting with version 84, Microsoft Edge supports a new capability that automatically redirects users.</span></span>  <span data-ttu-id="02e59-110">当 IE 用户导航到与 IE 不兼容的网站时，Windows 会自动将用户重定向到 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="02e59-110">When an IE user navigates to a website that is incompatible with IE, Windows automatically redirects the user to Microsoft Edge.</span></span>  <span data-ttu-id="02e59-111">若要查看列表中的网站，请导航到 " [需要 Microsoft Edge 列表][MicrosoftEdgeNeededgeV1]"。</span><span class="sxs-lookup"><span data-stu-id="02e59-111">To review the websites on the list, navigate to [Need Microsoft Edge list][MicrosoftEdgeNeededgeV1].</span></span>

<span data-ttu-id="02e59-112">本文介绍以下概念。</span><span class="sxs-lookup"><span data-stu-id="02e59-112">This article describes the following concepts.</span></span>  

*   <span data-ttu-id="02e59-113">重定向的用户体验</span><span class="sxs-lookup"><span data-stu-id="02e59-113">The user experience for redirection</span></span>  
*   <span data-ttu-id="02e59-114">如何将您的网站添加到 IE 兼容性列表</span><span class="sxs-lookup"><span data-stu-id="02e59-114">How to add your website to the IE compatibility list</span></span>  
*   <span data-ttu-id="02e59-115">如何从 IE 兼容性列表中删除您的网站</span><span class="sxs-lookup"><span data-stu-id="02e59-115">How to remove your website from the IE compatibility list</span></span>  
    
## <span data-ttu-id="02e59-116">为什么将网站添加到 IE 兼容性列表？</span><span class="sxs-lookup"><span data-stu-id="02e59-116">Why is a website added to the IE compatibility list?</span></span>  

<span data-ttu-id="02e59-117">IE 兼容性列表仅在发生以下操作时才会添加网站。</span><span class="sxs-lookup"><span data-stu-id="02e59-117">The IE compatibility List only adds a website when the following actions occur.</span></span>  

*   <span data-ttu-id="02e59-118">向 IE 用户显示一条消息，建议用户应出于兼容性原因使用其他浏览器。</span><span class="sxs-lookup"><span data-stu-id="02e59-118">Shows an IE user a message suggesting the user should use a different browser for compatibility reasons.</span></span>  
*   <span data-ttu-id="02e59-119">将网站添加到 IE 兼容性列表的所有者请求。</span><span class="sxs-lookup"><span data-stu-id="02e59-119">Owner requests to add the website to the IE compatibility list.</span></span>  
    
## <span data-ttu-id="02e59-120">更新 IE 兼容性列表</span><span class="sxs-lookup"><span data-stu-id="02e59-120">Update the IE compatibility list</span></span>  

<span data-ttu-id="02e59-121">IE 兼容性列表是 [microsoft.com][MicrosoftOfficialHome]上的一个 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="02e59-121">The IE compatibility list is an XML file on [microsoft.com][MicrosoftOfficialHome].</span></span>  <span data-ttu-id="02e59-122">列表会定期更新，以响应用户和网站开发人员请求添加或删除网站的请求。</span><span class="sxs-lookup"><span data-stu-id="02e59-122">The list is regularly updated in response to user's and website developers requests to have websites added or removed.</span></span>  <span data-ttu-id="02e59-123">对列表的更新会自动下载到用户计算机。</span><span class="sxs-lookup"><span data-stu-id="02e59-123">Updates to the list are automatically downloaded to user machines.</span></span>  

<span data-ttu-id="02e59-124">将以下信息通过电子邮件发送到 [ietoedge@microsoft.com][MailtoMicrosoftIetoedge] ，以便在 IE 兼容性列表中添加或删除您的网站。</span><span class="sxs-lookup"><span data-stu-id="02e59-124">Email the following information to [ietoedge@microsoft.com][MailtoMicrosoftIetoedge] for your website to be added or removed from the IE compatibility list.</span></span>    

*   <span data-ttu-id="02e59-125">所有者姓名</span><span class="sxs-lookup"><span data-stu-id="02e59-125">Owner name</span></span>  
*   <span data-ttu-id="02e59-126">公司标题</span><span class="sxs-lookup"><span data-stu-id="02e59-126">Corporate title</span></span>  
*   <span data-ttu-id="02e59-127">电子邮件地址</span><span class="sxs-lookup"><span data-stu-id="02e59-127">Email address</span></span>  
*   <span data-ttu-id="02e59-128">公司名称</span><span class="sxs-lookup"><span data-stu-id="02e59-128">Company name</span></span>  
*   <span data-ttu-id="02e59-129">街道地址</span><span class="sxs-lookup"><span data-stu-id="02e59-129">Street address</span></span>  
*   <span data-ttu-id="02e59-130">网站地址</span><span class="sxs-lookup"><span data-stu-id="02e59-130">Website address</span></span>  
<!--  *   Telephone number  -->  
<!--  *   Target platform \(desktop, phone, Xbox\)  -->  
    
<!-- links -->  

[MailtoMicrosoftIetoedge]: mailto:ietoedge@microsoft.com "向 ietoedge@microsoft.com 发送电子邮件"  

[MicrosoftOfficialHome]: https://www.microsoft.com "Microsoft 官方家庭版"  

[MicrosoftEdgeNeededgeV1]:  https://edge.microsoft.com/neededge/v1 "需要 Microsoft Edge 列表 v1 xml |Microsoft Edge"  
