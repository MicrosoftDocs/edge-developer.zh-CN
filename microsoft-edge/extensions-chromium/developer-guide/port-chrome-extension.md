---
description: 将 Chrome 扩展移植到 Microsoft Edge 的过程。
title: 指向 Microsoft (Chromium) Edge 的端口 Chrome 扩展
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/15/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium、扩展开发、浏览器扩展、addons、合作伙伴中心、开发人员
ms.openlocfilehash: 1852e267579f0fb790c6b8cac75a566298223933
ms.sourcegitcommit: d360e419b5f96f4f691cf7330b0d8dff9126f82e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/15/2020
ms.locfileid: "11015686"
---
# <span data-ttu-id="9e13a-104">将端口 Chrome 扩展到 Microsoft \ (Chromium \ ) Edge</span><span class="sxs-lookup"><span data-stu-id="9e13a-104">Port Chrome Extension To Microsoft \(Chromium\) Edge</span></span>  

<span data-ttu-id="9e13a-105">将 Chrome 扩展移植到 Microsoft Edge 的过程非常简单。</span><span class="sxs-lookup"><span data-stu-id="9e13a-105">The process of porting a Chrome Extension to Microsoft Edge is very straightforward.</span></span>  <span data-ttu-id="9e13a-106">为 Chromium 编写的扩展在大多数情况下，只需在 Microsoft Edge 中运行即可获得最少的更改。</span><span class="sxs-lookup"><span data-stu-id="9e13a-106">Extensions written for Chromium, in most cases, run on Microsoft Edge with minimal changes.</span></span>  <span data-ttu-id="9e13a-107">Chrome 支持的扩展 Api 和清单键是与 Microsoft Edge 兼容的代码。</span><span class="sxs-lookup"><span data-stu-id="9e13a-107">The Extension APIs and manifest keys supported by Chrome are code-compatible with Microsoft Edge.</span></span>  <span data-ttu-id="9e13a-108">但是，Microsoft Edge 不支持以下扩展 Api：</span><span class="sxs-lookup"><span data-stu-id="9e13a-108">However, Microsoft Edge does not support the following Extension APIs:</span></span>  

*   `chrome.gcm`  
*   `chrome.identity.getAccounts`  
*   `chrome.identity.getAuthToken`  
*   `chrome.instanceID`  

> [!Note]
> <span data-ttu-id="9e13a-109">用户必须使用 MSA 或 AAD 帐户登录到 Microsoft Edge，才能使用该 `chrome.identity.getProfileUserInfo` API。</span><span class="sxs-lookup"><span data-stu-id="9e13a-109">The user must be signed into Microsoft Edge using an MSA or AAD account in order to use the `chrome.identity.getProfileUserInfo` API.</span></span>  <span data-ttu-id="9e13a-110">如果用户使用 **本地广告**登录到 Microsoft EDGE，API 将返回 `null` "电子邮件" 和 "ID" 值。</span><span class="sxs-lookup"><span data-stu-id="9e13a-110">If the user is signed into Microsoft Edge using **On-premise AD**, the API returns `null` for the email and ID values.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="9e13a-111">**付款**： Microsoft Edge 不直接支持使用 [Chrome Web Store 付款][ChromeDeveloperWebStorePayments] 的扩展，因为需要使用 `identity.getAuthtoken` 请求获取登录用户的令牌才能发送基于 REST 的授权 API 请求。</span><span class="sxs-lookup"><span data-stu-id="9e13a-111">**Payments**:  Microsoft Edge does not directly support an Extension that uses [Chrome Web Store payments][ChromeDeveloperWebStorePayments] due to the requirement to use the `identity.getAuthtoken` request to get the token for signed-in users to send the REST-based licensing API request.</span></span>  <span data-ttu-id="9e13a-112">Microsoft Edge 不支持该 `getAuthtoken` 请求，因此此流程不起作用。</span><span class="sxs-lookup"><span data-stu-id="9e13a-112">Microsoft Edge does not support the `getAuthtoken` request, so this flow does not work.</span></span>  

<span data-ttu-id="9e13a-113">若要移植 Chrome 扩展，请按照下列步骤操作：</span><span class="sxs-lookup"><span data-stu-id="9e13a-113">To port your Chrome Extension, follow these steps:</span></span>  

1.  <span data-ttu-id="9e13a-114">查看扩展中使用的 Chrome 扩展 Api。</span><span class="sxs-lookup"><span data-stu-id="9e13a-114">Review the Chrome Extension APIs used in your Extensions.</span></span>  <span data-ttu-id="9e13a-115">如果你使用的是 Microsoft Edge 不支持的功能或 Api，你可能无法移植你的扩展。</span><span class="sxs-lookup"><span data-stu-id="9e13a-115">If you are using features or APIs that are not supported by Microsoft Edge, you may not be able to port your Extension.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="9e13a-116">`getAuthToken`API 不能与 Microsoft Edge 配合使用，但你可以使用 `launchWebAuthFlow` 获取 OAuth2 令牌来对用户进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="9e13a-116">The `getAuthToken` API does not work with Microsoft Edge, however you may use `launchWebAuthFlow` to fetch an OAuth2 token to authenticate users.</span></span>  
    
1.  <span data-ttu-id="9e13a-117">如果您 `Chrome` 在分机的名称或说明中使用，请重新标记的分机号 `Microsoft Edge` 。</span><span class="sxs-lookup"><span data-stu-id="9e13a-117">If you are using `Chrome` in the name or description of your Extension, re-brand the Extension for `Microsoft Edge`.</span></span>  <span data-ttu-id="9e13a-118">您必须通过认证流程。</span><span class="sxs-lookup"><span data-stu-id="9e13a-118">You must pass the certification process.</span></span>  
    
1.  <span data-ttu-id="9e13a-119">测试您的扩展，以检查它在 Microsoft Edge 中是否正常工作。</span><span class="sxs-lookup"><span data-stu-id="9e13a-119">Test your Extension to check if it works in Microsoft Edge.</span></span>  <span data-ttu-id="9e13a-120">执行此操作的第一步是确保已打开扩展开发人员功能。</span><span class="sxs-lookup"><span data-stu-id="9e13a-120">The first step to do this is to ensure that you have Extension developer features turned on.</span></span>  <span data-ttu-id="9e13a-121">这使你可以在 Microsoft Edge 中加载扩展文件，以便你可以在开发时测试扩展。</span><span class="sxs-lookup"><span data-stu-id="9e13a-121">This enables you to side load Extension files in Microsoft Edge so that you are able to test your Extension while developing it.</span></span>  
    
1.  <span data-ttu-id="9e13a-122">如果你有任何问题，请使用 DevTools 在 Microsoft Edge 中调试你的扩展， [或与我们联系][mailtoExtensionPartnerOpsMicrosoft]。</span><span class="sxs-lookup"><span data-stu-id="9e13a-122">If you have any issues, debug your Extensions in Microsoft Edge by using the DevTools, or [contact us][mailtoExtensionPartnerOpsMicrosoft].</span></span>  
    
1.  <span data-ttu-id="9e13a-123">现在，你的扩展已是 "精美"，可随时打包。</span><span class="sxs-lookup"><span data-stu-id="9e13a-123">Now your Extension is finally polished up and ready to be packaged.</span></span>  <span data-ttu-id="9e13a-124">如果你希望准备提交到 Microsoft Edge Addons 目录 \ (Microsoft Edge Addons \ ) ，则无需打包你的扩展。</span><span class="sxs-lookup"><span data-stu-id="9e13a-124">If you wish to prepare for submission to the Microsoft Edge Addons catalog \(Microsoft Edge Addons\), you do not need to package your Extension.</span></span>  <span data-ttu-id="9e13a-125">此外，请遵循我们的 [发布指南][ExtensionsPublishExtension] 以在 Microsoft Edge Addons 上发布您的扩展。</span><span class="sxs-lookup"><span data-stu-id="9e13a-125">Further, follow our [publishing guidelines][ExtensionsPublishExtension] to publish your Extension on Microsoft Edge Addons.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="9e13a-126">如果你的扩展使用 API 与本机应用程序交换消息 `chrome.runtime.connectNative` ，请确保你 `allowedorigins` `extension://[Microsoft-Catalog-extensionID]` 在本机消息主机清单文件中设置为 ""。</span><span class="sxs-lookup"><span data-stu-id="9e13a-126">If your Extension exchanges messages with a native application using `chrome.runtime.connectNative` API, ensure that you set `allowedorigins` to "`extension://[Microsoft-Catalog-extensionID]`" in your native messaging host manifest file.</span></span>  <span data-ttu-id="9e13a-127">这使应用能够标识扩展。</span><span class="sxs-lookup"><span data-stu-id="9e13a-127">This enables the app to identify the Extension.</span></span>  

<!-- image links -->  

<!-- links -->  

[ExtensionsPublishExtension]: ../publish/publish-extension.md "发布扩展"  

[mailtoExtensionPartnerOpsMicrosoft]: mailto:extensionpartnerops@microsoft.com "ExtensionPartnerOps@microsoft.com"  

[ChromeDeveloperWebStorePayments]: https://developer.chrome.com/webstore/one_time_payments "一次性付款-Google Chrome"  
