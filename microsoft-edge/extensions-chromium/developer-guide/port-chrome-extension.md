---
description: 将 Chrome 扩展移植到 Microsoft Edge 的过程。
title: 将端口 Chrome 扩展到 Microsoft Edge
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/25/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium、扩展开发、浏览器扩展、addons、合作伙伴中心、开发人员
ms.openlocfilehash: 0f767107bfb259476d1ab35d081fb9bb05c81b46
ms.sourcegitcommit: e79503c6c53ea9b7de58f8cf1532b5c82116a6eb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2020
ms.locfileid: "11195157"
---
# <span data-ttu-id="33cb5-104">移植分机</span><span class="sxs-lookup"><span data-stu-id="33cb5-104">Port your extension</span></span>  

<span data-ttu-id="33cb5-105">Microsoft Edge 允许你将 Chrome 扩展移植到最少的更改。</span><span class="sxs-lookup"><span data-stu-id="33cb5-105">Microsoft Edge allows you to port your Chrome extension with minimal changes.</span></span>  <span data-ttu-id="33cb5-106">Chrome 支持的扩展 Api 和清单键是与 Microsoft Edge 兼容的代码。</span><span class="sxs-lookup"><span data-stu-id="33cb5-106">The Extension APIs and manifest keys supported by Chrome are code-compatible with Microsoft Edge.</span></span>  <span data-ttu-id="33cb5-107">有关 Microsoft Edge 支持的 Api 的列表，请导航到 [API 支持][ExtensionApiSupport]。</span><span class="sxs-lookup"><span data-stu-id="33cb5-107">For a list of APIs supported by Microsoft Edge, navigate to [API support][ExtensionApiSupport].</span></span>  

<span data-ttu-id="33cb5-108">若要移植 Chrome 扩展，请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="33cb5-108">To port your Chrome extension, complete the following steps.</span></span>  

1.  <span data-ttu-id="33cb5-109">使用 Microsoft Edge 扩展 [支持的 api][ExtensionApiSupport] 列表查看你的扩展中使用的 Chrome 扩展 api。</span><span class="sxs-lookup"><span data-stu-id="33cb5-109">Review the Chrome extension APIs used in your extensions with the Microsoft Edge extensions [supported APIs][ExtensionApiSupport] list.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="33cb5-110">如果你的扩展使用的 Api 不受 Microsoft Edge 支持，则它不能直接移植。</span><span class="sxs-lookup"><span data-stu-id="33cb5-110">If your extension uses APIs that are not supported by Microsoft Edge, it may not port directly.</span></span>  
    
1.  <span data-ttu-id="33cb5-111">如果 `Chrome` 要在扩展名的名称或说明中使用该名称，请为 rebrand 的扩展名 `Microsoft Edge` 。</span><span class="sxs-lookup"><span data-stu-id="33cb5-111">If the name `Chrome` is being used in either the name or the description of the extension, rebrand the extension for `Microsoft Edge`.</span></span>  <span data-ttu-id="33cb5-112">必须执行此步骤才能传递认证过程。</span><span class="sxs-lookup"><span data-stu-id="33cb5-112">This step is required to pass the certification process.</span></span>  
1.  <span data-ttu-id="33cb5-113">通过 [旁加载你的扩展][ExtensionsGettingStartedExtensionSideloading]来测试你的扩展，以检查它在 Microsoft Edge 中是否正常工作。</span><span class="sxs-lookup"><span data-stu-id="33cb5-113">Test your extension to check if it works in Microsoft Edge by [sideloading your extension][ExtensionsGettingStartedExtensionSideloading].</span></span>  
1.  <span data-ttu-id="33cb5-114">如果你面临任何问题，你可以使用 DevTools 在 Microsoft Edge 中调试你的扩展 [，或者与我们联系][mailtoExtensionMicrosoft]。</span><span class="sxs-lookup"><span data-stu-id="33cb5-114">If you face any issues, you may debug your extensions in Microsoft Edge by using the DevTools, or [contact us][mailtoExtensionMicrosoft].</span></span>  
1.  <span data-ttu-id="33cb5-115">按照 [发布指南][ExtensionsPublishPublishExtension] ，在 Microsoft Edge 加载项存储上发布扩展。</span><span class="sxs-lookup"><span data-stu-id="33cb5-115">Follow the [publishing guidelines][ExtensionsPublishPublishExtension] to publish your extension on Microsoft Edge Add-ons store.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="33cb5-116">如果扩展使用 API 与本机应用交换消息 `chrome.runtime.connectNative` ，请确保在 `allowed_origins` `extension://[Microsoft-Catalog-extensionID]` 本机消息主机清单文件中设置为。</span><span class="sxs-lookup"><span data-stu-id="33cb5-116">If the extension exchanges messages with a native app using `chrome.runtime.connectNative` API, ensure that you set `allowed_origins` to `extension://[Microsoft-Catalog-extensionID]` in your native messaging host manifest file.</span></span>  <span data-ttu-id="33cb5-117">这使应用能够标识扩展。</span><span class="sxs-lookup"><span data-stu-id="33cb5-117">This enables the app to identify the extension.</span></span>  
    
## <span data-ttu-id="33cb5-118">后续步骤</span><span class="sxs-lookup"><span data-stu-id="33cb5-118">Next steps</span></span>  

<span data-ttu-id="33cb5-119">扩展程序包准备好发布到 Microsoft Edge 加载项存储后， [创建一个开发者帐户][ExtensionsPublishCreateDevAccount] 并 [发布您的扩展][ExtensionsPublishPublishExtension]。</span><span class="sxs-lookup"><span data-stu-id="33cb5-119">Once your extension package is ready to be published to Microsoft Edge add-ons store, [create a developer account][ExtensionsPublishCreateDevAccount] and [publish your extension][ExtensionsPublishPublishExtension].</span></span>  

<!-- links -->  

[ExtensionApiSupport]: ./api-support.md "API 支持 |Microsoft 文档"  
[ExtensionsGettingStartedExtensionSideloading]: ../getting-started/extension-sideloading.md "旁加载您的分机 |Microsoft 文档"  
[ExtensionsPublishCreateDevAccount]: ../publish/create-dev-account.md "开发人员注册 |Microsoft 文档"  
[ExtensionsPublishPublishExtension]: ../publish/publish-extension.md "发布您的分机 |Microsoft 文档"  

[ChromeDeveloperWebStorePayments]: https://developer.chrome.com/webstore/one_time_payments "一次性付款 |Chrome 开发人员"  

[mailtoExtensionMicrosoft]: mailto:ext_dev_support@microsoft.com "ext_dev_support@microsoft.com"  
