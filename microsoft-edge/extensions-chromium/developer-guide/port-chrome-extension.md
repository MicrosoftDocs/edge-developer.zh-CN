---
description: Process of porting Chrome Extension to Microsoft Edge.
title: Port Chrome Extension To Microsoft (Chromium)Edge
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/15/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium, extensions development, browser extensions, addons, partner center, developer
ms.openlocfilehash: 1852e267579f0fb790c6b8cac75a566298223933
ms.sourcegitcommit: d360e419b5f96f4f691cf7330b0d8dff9126f82e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2020
ms.locfileid: "11015686"
---
# <span data-ttu-id="ab526-104">Port Chrome Extension To Microsoft \(Chromium\) Edge</span><span class="sxs-lookup"><span data-stu-id="ab526-104">Port Chrome Extension To Microsoft \(Chromium\) Edge</span></span>  

<span data-ttu-id="ab526-105">The process of porting a Chrome Extension to Microsoft Edge is very straightforward.</span><span class="sxs-lookup"><span data-stu-id="ab526-105">The process of porting a Chrome Extension to Microsoft Edge is very straightforward.</span></span>  <span data-ttu-id="ab526-106">Extensions written for Chromium, in most cases, run on Microsoft Edge with minimal changes.</span><span class="sxs-lookup"><span data-stu-id="ab526-106">Extensions written for Chromium, in most cases, run on Microsoft Edge with minimal changes.</span></span>  <span data-ttu-id="ab526-107">The Extension APIs and manifest keys supported by Chrome are code-compatible with Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="ab526-107">The Extension APIs and manifest keys supported by Chrome are code-compatible with Microsoft Edge.</span></span>  <span data-ttu-id="ab526-108">However, Microsoft Edge does not support the following Extension APIs:</span><span class="sxs-lookup"><span data-stu-id="ab526-108">However, Microsoft Edge does not support the following Extension APIs:</span></span>  

*   `chrome.gcm`  
*   `chrome.identity.getAccounts`  
*   `chrome.identity.getAuthToken`  
*   `chrome.instanceID`  

> [!Note]
> <span data-ttu-id="ab526-109">The user must be signed into Microsoft Edge using an MSA or AAD account in order to use the `chrome.identity.getProfileUserInfo` API.</span><span class="sxs-lookup"><span data-stu-id="ab526-109">The user must be signed into Microsoft Edge using an MSA or AAD account in order to use the `chrome.identity.getProfileUserInfo` API.</span></span>  <span data-ttu-id="ab526-110">If the user is signed into Microsoft Edge using **On-premise AD**, the API returns `null` for the email and ID values.</span><span class="sxs-lookup"><span data-stu-id="ab526-110">If the user is signed into Microsoft Edge using **On-premise AD**, the API returns `null` for the email and ID values.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="ab526-111">**Payments**:  Microsoft Edge does not directly support an Extension that uses [Chrome Web Store payments][ChromeDeveloperWebStorePayments] due to the requirement to use the `identity.getAuthtoken` request to get the token for signed-in users to send the REST-based licensing API request.</span><span class="sxs-lookup"><span data-stu-id="ab526-111">**Payments**:  Microsoft Edge does not directly support an Extension that uses [Chrome Web Store payments][ChromeDeveloperWebStorePayments] due to the requirement to use the `identity.getAuthtoken` request to get the token for signed-in users to send the REST-based licensing API request.</span></span>  <span data-ttu-id="ab526-112">Microsoft Edge does not support the `getAuthtoken` request, so this flow does not work.</span><span class="sxs-lookup"><span data-stu-id="ab526-112">Microsoft Edge does not support the `getAuthtoken` request, so this flow does not work.</span></span>  

<span data-ttu-id="ab526-113">To port your Chrome Extension, follow these steps:</span><span class="sxs-lookup"><span data-stu-id="ab526-113">To port your Chrome Extension, follow these steps:</span></span>  

1.  <span data-ttu-id="ab526-114">Review the Chrome Extension APIs used in your Extensions.</span><span class="sxs-lookup"><span data-stu-id="ab526-114">Review the Chrome Extension APIs used in your Extensions.</span></span>  <span data-ttu-id="ab526-115">If you are using features or APIs that are not supported by Microsoft Edge, you may not be able to port your Extension.</span><span class="sxs-lookup"><span data-stu-id="ab526-115">If you are using features or APIs that are not supported by Microsoft Edge, you may not be able to port your Extension.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="ab526-116">The `getAuthToken` API does not work with Microsoft Edge, however you may use `launchWebAuthFlow` to fetch an OAuth2 token to authenticate users.</span><span class="sxs-lookup"><span data-stu-id="ab526-116">The `getAuthToken` API does not work with Microsoft Edge, however you may use `launchWebAuthFlow` to fetch an OAuth2 token to authenticate users.</span></span>  
    
1.  <span data-ttu-id="ab526-117">If you are using `Chrome` in the name or description of your Extension, re-brand the Extension for `Microsoft Edge`.</span><span class="sxs-lookup"><span data-stu-id="ab526-117">If you are using `Chrome` in the name or description of your Extension, re-brand the Extension for `Microsoft Edge`.</span></span>  <span data-ttu-id="ab526-118">You must pass the certification process.</span><span class="sxs-lookup"><span data-stu-id="ab526-118">You must pass the certification process.</span></span>  
    
1.  <span data-ttu-id="ab526-119">Test your Extension to check if it works in Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="ab526-119">Test your Extension to check if it works in Microsoft Edge.</span></span>  <span data-ttu-id="ab526-120">The first step to do this is to ensure that you have Extension developer features turned on.</span><span class="sxs-lookup"><span data-stu-id="ab526-120">The first step to do this is to ensure that you have Extension developer features turned on.</span></span>  <span data-ttu-id="ab526-121">This enables you to side load Extension files in Microsoft Edge so that you are able to test your Extension while developing it.</span><span class="sxs-lookup"><span data-stu-id="ab526-121">This enables you to side load Extension files in Microsoft Edge so that you are able to test your Extension while developing it.</span></span>  
    
1.  <span data-ttu-id="ab526-122">If you have any issues, debug your Extensions in Microsoft Edge by using the DevTools, or [contact us][mailtoExtensionPartnerOpsMicrosoft].</span><span class="sxs-lookup"><span data-stu-id="ab526-122">If you have any issues, debug your Extensions in Microsoft Edge by using the DevTools, or [contact us][mailtoExtensionPartnerOpsMicrosoft].</span></span>  
    
1.  <span data-ttu-id="ab526-123">Now your Extension is finally polished up and ready to be packaged.</span><span class="sxs-lookup"><span data-stu-id="ab526-123">Now your Extension is finally polished up and ready to be packaged.</span></span>  <span data-ttu-id="ab526-124">If you wish to prepare for submission to the Microsoft Edge Addons catalog \(Microsoft Edge Addons\), you do not need to package your Extension.</span><span class="sxs-lookup"><span data-stu-id="ab526-124">If you wish to prepare for submission to the Microsoft Edge Addons catalog \(Microsoft Edge Addons\), you do not need to package your Extension.</span></span>  <span data-ttu-id="ab526-125">Further, follow our [publishing guidelines][ExtensionsPublishExtension] to publish your Extension on Microsoft Edge Addons.</span><span class="sxs-lookup"><span data-stu-id="ab526-125">Further, follow our [publishing guidelines][ExtensionsPublishExtension] to publish your Extension on Microsoft Edge Addons.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="ab526-126">If your Extension exchanges messages with a native application using `chrome.runtime.connectNative` API, ensure that you set `allowedorigins` to "`extension://[Microsoft-Catalog-extensionID]`" in your native messaging host manifest file.</span><span class="sxs-lookup"><span data-stu-id="ab526-126">If your Extension exchanges messages with a native application using `chrome.runtime.connectNative` API, ensure that you set `allowedorigins` to "`extension://[Microsoft-Catalog-extensionID]`" in your native messaging host manifest file.</span></span>  <span data-ttu-id="ab526-127">This enables the app to identify the Extension.</span><span class="sxs-lookup"><span data-stu-id="ab526-127">This enables the app to identify the Extension.</span></span>  

<!-- image links -->  

<!-- links -->  

[ExtensionsPublishExtension]: ../publish/publish-extension.md "Publish An Extension"  

[mailtoExtensionPartnerOpsMicrosoft]: mailto:extensionpartnerops@microsoft.com "ExtensionPartnerOps@microsoft.com"  

[ChromeDeveloperWebStorePayments]: https://developer.chrome.com/webstore/one_time_payments "One-Time Payments - Google Chrome"  
