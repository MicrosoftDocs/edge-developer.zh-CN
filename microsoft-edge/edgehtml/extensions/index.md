---
description: 了解如何开发 Microsoft Edge 扩展。 这些小型程序可用于向 Microsoft Edge 添加新功能或修改现有功能。
title: Extensions
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
ms.technology: extensions
keywords: edge， Web 开发， html， css， javascript， 开发人员， 扩展
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: cc54e3512cf315183ce8baa59abde3db568d1828
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232586"
---
# <span data-ttu-id="47a0f-105">Microsoft Edge (EdgeHTML) 扩展</span><span class="sxs-lookup"><span data-stu-id="47a0f-105">Microsoft Edge (EdgeHTML) extensions</span></span>  

[!INCLUDE [deprecation-note](includes/deprecation-note.md)]  

<span data-ttu-id="47a0f-106">扩展是小型程序，可用于将新功能添加到 Microsoft Edge (EdgeHTML) 或修改现有功能。</span><span class="sxs-lookup"><span data-stu-id="47a0f-106">Extensions are small programs that can be used to add new features to Microsoft Edge (EdgeHTML) or modify the existing functionality.</span></span> <span data-ttu-id="47a0f-107">扩展旨在通过提供对目标受众非常重要的小范围功能来改进用户日常浏览体验。</span><span class="sxs-lookup"><span data-stu-id="47a0f-107">Extensions are intended to improve a user’s day-to-day browsing experience by providing niche functionality that is important to targeted audiences.</span></span>

<span data-ttu-id="47a0f-108">Microsoft Edge (EdgeHTML) 支持新的基于 HTML、JavaScript 和 CSS 的扩展模型。</span><span class="sxs-lookup"><span data-stu-id="47a0f-108">Microsoft Edge (EdgeHTML) supports a new HTML, JavaScript and CSS based extension model.</span></span> <span data-ttu-id="47a0f-109">此新模型与 Chrome 兼容，这意味着现有 Chrome 扩展开发人员将能够将其扩展迁移到 Microsoft Edge (EdgeHTML) 更改。</span><span class="sxs-lookup"><span data-stu-id="47a0f-109">This new model is Chrome-compatible which means that existing Chrome extension developers will be able to migrate their extensions to Microsoft Edge (EdgeHTML) with minimal changes.</span></span>

<span data-ttu-id="47a0f-110">若要大致了解从开发到发布创建 Microsoft Edge (EdgeHTML) 的端到端旅程，请查看入门 [指南](./getting-started.md)！</span><span class="sxs-lookup"><span data-stu-id="47a0f-110">To get an overview of the end to end journey of creating a Microsoft Edge (EdgeHTML) extension from development to publishing, check out the [Getting started guide](./getting-started.md)!</span></span>


## <span data-ttu-id="47a0f-111">热门文章</span><span class="sxs-lookup"><span data-stu-id="47a0f-111">Popular articles</span></span>

<table>
  <tr>
    <td><a href = "./api-support/extension-api-roadmap.md"><span data-ttu-id="47a0f-112">扩展 API 路线图</span><span class="sxs-lookup"><span data-stu-id="47a0f-112">Extension API roadmap</span></span></a></td>
    <td><span data-ttu-id="47a0f-113">查看 Windows 10 Insider Preview 和 Microsoft Edge 公开发布的内部版本在开发中支持/开发哪些 API。</span><span class="sxs-lookup"><span data-stu-id="47a0f-113">Check out what APIs are supported/in development for Windows 10 Insider Preview and publicly released builds of Microsoft Edge.</span></span></td></p>
<p>  </tr>
  <tr>
    <td><a href = "./api-support/supported-apis.md"><span data-ttu-id="47a0f-114">支持的 API</span><span class="sxs-lookup"><span data-stu-id="47a0f-114">Supported APIs</span></span></a></td>
    <td><span data-ttu-id="47a0f-115">获取有关受支持的 API 的信息，包括已知问题和 Chrome 不兼容。</span><span class="sxs-lookup"><span data-stu-id="47a0f-115">Get info on our supported APIs including known issues and Chrome incompatibilities.</span></span></td>

  </tr>
  <tr>
    <td><a href = "./guides/creating-an-extension.md"><span data-ttu-id="47a0f-116">创建扩展</span><span class="sxs-lookup"><span data-stu-id="47a0f-116">Creating an extension</span></span></a></td>
    <td><span data-ttu-id="47a0f-117">对扩展开发世界的新人？</span><span class="sxs-lookup"><span data-stu-id="47a0f-117">New to the world of extension development?</span></span> <span data-ttu-id="47a0f-118">尝试一些教程以快速入门。</span><span class="sxs-lookup"><span data-stu-id="47a0f-118">Try out some tutorials to get up to speed.</span></span></td>

  </tr>
  <tr>
    <td><a href = "./guides/packaging.md"><span data-ttu-id="47a0f-119">打包</span><span class="sxs-lookup"><span data-stu-id="47a0f-119">Packaging</span></span></a></td>
    <td><span data-ttu-id="47a0f-120">了解如何在完成开发后打包&#39;包。</span><span class="sxs-lookup"><span data-stu-id="47a0f-120">Learn how to package up your extension after you&#39;ve finished development.</span></span></td>

  </tr>
  <tr>
    <td><a href = "./guides/porting-chrome-extensions.md"><span data-ttu-id="47a0f-121">移植 Chrome 扩展</span><span class="sxs-lookup"><span data-stu-id="47a0f-121">Porting Chrome extensions</span></span></a></td>
    <td><span data-ttu-id="47a0f-122">已创建要&#39;Microsoft Edge 上的 Chrome 扩展？</span><span class="sxs-lookup"><span data-stu-id="47a0f-122">Created a Chrome extension you&#39;d like to see on Microsoft Edge?</span></span> <span data-ttu-id="47a0f-123">了解如何使用 Microsoft Edge 扩展Toolkit。</span><span class="sxs-lookup"><span data-stu-id="47a0f-123">See how to port it with the Microsoft Edge Extension Toolkit.</span></span></td>

  </tr>
</table>
