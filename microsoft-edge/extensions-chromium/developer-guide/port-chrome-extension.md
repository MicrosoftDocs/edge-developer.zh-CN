---
description: 将 Chrome 扩展移植到 Microsoft Edge 的过程
title: 将 Chrome 扩展移植到 Microsoft Edge
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/17/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium， 扩展开发， 浏览器扩展， 加载项， 合作伙伴中心， 开发人员
ms.openlocfilehash: 6be7d788ac22232475e278ae9a5b04de9b6e17f7
ms.sourcegitcommit: 916b4daa26c2c78611f7d837bd6ecf009f0082df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/17/2021
ms.locfileid: "11343134"
---
# <span data-ttu-id="8ad4d-104">移植扩展</span><span class="sxs-lookup"><span data-stu-id="8ad4d-104">Port your extension</span></span>  

<span data-ttu-id="8ad4d-105">Microsoft Edge 允许你以最少的更改移植 Chrome 扩展。</span><span class="sxs-lookup"><span data-stu-id="8ad4d-105">Microsoft Edge allows you to port your Chrome extension with minimal changes.</span></span>  <span data-ttu-id="8ad4d-106">Chrome 支持的扩展 API 和清单密钥与 Microsoft Edge 代码兼容。</span><span class="sxs-lookup"><span data-stu-id="8ad4d-106">The Extension APIs and manifest keys supported by Chrome are code-compatible with Microsoft Edge.</span></span>  <span data-ttu-id="8ad4d-107">有关 Microsoft Edge 支持的 API 列表，请导航到 [API 支持][ExtensionApiSupport]。</span><span class="sxs-lookup"><span data-stu-id="8ad4d-107">For a list of APIs supported by Microsoft Edge, navigate to [API support][ExtensionApiSupport].</span></span>  

<span data-ttu-id="8ad4d-108">若要移植 Chrome 扩展，请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="8ad4d-108">To port your Chrome extension, complete the following steps.</span></span>  

1.  <span data-ttu-id="8ad4d-109">使用 Microsoft Edge 扩展支持的 API 列表查看扩展中使用的 Chrome[扩展 API。][ExtensionApiSupport]</span><span class="sxs-lookup"><span data-stu-id="8ad4d-109">Review the Chrome extension APIs used in your extensions with the Microsoft Edge extensions [supported APIs][ExtensionApiSupport] list.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="8ad4d-110">如果你的扩展使用 Microsoft Edge 不支持的 API，它可能不会直接移植。</span><span class="sxs-lookup"><span data-stu-id="8ad4d-110">If your extension uses APIs that are not supported by Microsoft Edge, it may not port directly.</span></span>  
    
1.  <span data-ttu-id="8ad4d-111">在清单文件中，将 `update_URL` 字段设置为 `https://edge.microsoft.com/extensionwebstorebase/v1/crx` 。</span><span class="sxs-lookup"><span data-stu-id="8ad4d-111">In the manifest file, set the `update_URL` field to `https://edge.microsoft.com/extensionwebstorebase/v1/crx`.</span></span>  <span data-ttu-id="8ad4d-112">值指向 Microsoft Edge 加载项存储中的扩展文件，并允许 `.crx` Microsoft Edge 检查扩展更新。</span><span class="sxs-lookup"><span data-stu-id="8ad4d-112">The value points to the `.crx` file of your extension in the Microsoft Edge Add-ons store and allows Microsoft Edge to check for extension updates.</span></span>  
1.  <span data-ttu-id="8ad4d-113">如果在 `Chrome` 扩展的名称或说明中使用的，则使用 重新命名扩展 `Microsoft Edge` 。</span><span class="sxs-lookup"><span data-stu-id="8ad4d-113">If `Chrome` is used in either the name or the description of your extension, rebrand your extension using `Microsoft Edge`.</span></span>  <span data-ttu-id="8ad4d-114">若要通过认证过程，需要更改。</span><span class="sxs-lookup"><span data-stu-id="8ad4d-114">To pass the certification process, the changes are required.</span></span>  
1.  <span data-ttu-id="8ad4d-115">通过旁加载扩展来测试扩展，以检查它在 Microsoft Edge [中是否正常工作][ExtensionsGettingStartedExtensionSideloading]。</span><span class="sxs-lookup"><span data-stu-id="8ad4d-115">Test your extension to check if it works in Microsoft Edge by [sideloading your extension][ExtensionsGettingStartedExtensionSideloading].</span></span>  
1.  <span data-ttu-id="8ad4d-116">如果面临任何问题，可以使用 DevTools 在 Microsoft Edge 中调试扩展，或 [联系我们][mailtoExtensionMicrosoft]。</span><span class="sxs-lookup"><span data-stu-id="8ad4d-116">If you face any issues, you may debug your extensions in Microsoft Edge by using the DevTools, or [contact us][mailtoExtensionMicrosoft].</span></span>  
1.  <span data-ttu-id="8ad4d-117">按照 [发布指南在][ExtensionsPublishPublishExtension] Microsoft Edge 加载项应用商店中发布扩展。</span><span class="sxs-lookup"><span data-stu-id="8ad4d-117">Follow the [publishing guidelines][ExtensionsPublishPublishExtension] to publish your extension on Microsoft Edge Add-ons store.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="8ad4d-118">如果扩展使用 与本机应用交换邮件，请确保在本机消息传递主机清单 `chrome.runtime.connectNative` `allowed_origins` `extension://[Microsoft-Catalog-extensionID]` 文件中设置为 。</span><span class="sxs-lookup"><span data-stu-id="8ad4d-118">If your extension exchanges messages with a native app using `chrome.runtime.connectNative`, ensure that you set `allowed_origins` to `extension://[Microsoft-Catalog-extensionID]` in your native messaging host manifest file.</span></span>  <span data-ttu-id="8ad4d-119">该设置允许应用标识你的扩展。</span><span class="sxs-lookup"><span data-stu-id="8ad4d-119">The setting allows the app to identify your extension.</span></span>  
    
## <span data-ttu-id="8ad4d-120">后续步骤</span><span class="sxs-lookup"><span data-stu-id="8ad4d-120">Next steps</span></span>  

<span data-ttu-id="8ad4d-121">准备好在 Microsoft Edge 加载项应用商店中发布扩展包后，创建开发人员帐户[并][ExtensionsPublishCreateDevAccount][发布扩展][ExtensionsPublishPublishExtension]。</span><span class="sxs-lookup"><span data-stu-id="8ad4d-121">After your extension package is ready to publish in the Microsoft Edge Add-ons store, [create a developer account][ExtensionsPublishCreateDevAccount] and [publish your extension][ExtensionsPublishPublishExtension].</span></span>  

<!-- links -->  

[ExtensionApiSupport]: ./api-support.md "API 支持|Microsoft Docs"  
[ExtensionsGettingStartedExtensionSideloading]: ../getting-started/extension-sideloading.md "旁加载扩展|Microsoft Docs"  
[ExtensionsPublishCreateDevAccount]: ../publish/create-dev-account.md "开发人员注册|Microsoft Docs"  
[ExtensionsPublishPublishExtension]: ../publish/publish-extension.md "发布扩展|Microsoft Docs"  

[ChromeDeveloperWebStorePayments]: https://developer.chrome.com/webstore/one_time_payments "一次付款|Chrome 开发人员"  

[mailtoExtensionMicrosoft]: mailto:ext_dev_support@microsoft.com "ext_dev_support@microsoft.com"  
