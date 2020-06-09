---
description: 使用 Microsoft Edge WebView2 发布应用时的分发选项
title: Microsoft Edge WebView2 应用程序的分发
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/19/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、wpf 应用、wpf、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: ec623da0181a4f21c3192652b0d098f922225b0d
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10697922"
---
# <span data-ttu-id="8b316-104">使用 WebView2 的应用程序的分发</span><span class="sxs-lookup"><span data-stu-id="8b316-104">Distribution of applications using WebView2</span></span> 

<span data-ttu-id="8b316-105">WebView2 控件利用 Microsoft Edge \ （Chromium \）浏览器。</span><span class="sxs-lookup"><span data-stu-id="8b316-105">The WebView2 control utilizes the Microsoft Edge \(Chromium\) browser.</span></span> <span data-ttu-id="8b316-106">当分发你的应用时，请确保应用程序运行的所有用户计算机上都安装了 Edge 浏览器。</span><span class="sxs-lookup"><span data-stu-id="8b316-106">When distributing your app, ensure that the Edge browser is installed on all user machines where your application runs.</span></span> <span data-ttu-id="8b316-107">WebView2 控件使用计算机上安装的最稳定版本的浏览器。</span><span class="sxs-lookup"><span data-stu-id="8b316-107">The WebView2 control uses the most stable version of the browser that’s installed on a machine.</span></span> <span data-ttu-id="8b316-108">例如，你可能同时安装了稳定、Beta、Dev 和 WebView2，在这种情况下，控件在稳定频道中运行。</span><span class="sxs-lookup"><span data-stu-id="8b316-108">For example, you may have Stable, Beta, Dev, and Canary installed at the same time, and in this situation, WebView2 controls run in the Stable channel.</span></span> <span data-ttu-id="8b316-109">请确保查看发行说明，确保运行 WebView2 控件的计算机上安装的浏览器版本满足最低版本要求。</span><span class="sxs-lookup"><span data-stu-id="8b316-109">Ensure you review the release notes to ensure that the version of the browser installed on your machines that run your WebView2 controls meet the minimum version requirements.</span></span>

## <span data-ttu-id="8b316-110">路线图</span><span class="sxs-lookup"><span data-stu-id="8b316-110">Roadmap</span></span>

<span data-ttu-id="8b316-111">我们认识到，在应用程序运行的所有用户计算机上，或者在整个组织中安装 Edge 浏览器的情况下，Edge 浏览器可能不可用。</span><span class="sxs-lookup"><span data-stu-id="8b316-111">We recognize that the Edge browser may not be available on all user machines where your application will run, or that installing Edge browser throughout your organization may be difficult.</span></span> <span data-ttu-id="8b316-112">为了确保你的应用程序在所有计算机上运行，而不依赖于已安装的 Microsoft Edge 浏览器，我们将释放 Microsoft Edge WebView2 运行时。</span><span class="sxs-lookup"><span data-stu-id="8b316-112">To ensure your application runs on all machines, independent of the installed Microsoft Edge browser, we will release the Microsoft Edge WebView2 Runtime.</span></span> <span data-ttu-id="8b316-113">此外，我们还将更新 WebView2 以搜索运行时的稳定版本，然后再搜索已安装浏览器的预发布版本。</span><span class="sxs-lookup"><span data-stu-id="8b316-113">Additionally, we will update WebView2 to search for the stable version of the runtime before searching for pre-release versions of the installed browser.</span></span>

<span data-ttu-id="8b316-114">将对使用 WebView2 运行时：长绿和固定版本的两个分发选项提供支持。</span><span class="sxs-lookup"><span data-stu-id="8b316-114">There will be support for two distribution options using the WebView2 Runtime: evergreen, and fixed version.</span></span>

<span data-ttu-id="8b316-115">长绿将成为大多数开发人员的推荐的分发模型。</span><span class="sxs-lookup"><span data-stu-id="8b316-115">Evergreen will be the recommended distribution model for most developers.</span></span> <span data-ttu-id="8b316-116">在此模式下，更新将自动推送到 WebView2 运行时，而不需要你的应用程序进行额外的工作。</span><span class="sxs-lookup"><span data-stu-id="8b316-116">In this mode, updates are pushed automatically to the WebView2 Runtime without additional effort from your application.</span></span> <span data-ttu-id="8b316-117">长时间模型可确保你的应用充分利用托管 web 内容的最新功能和安全更新。</span><span class="sxs-lookup"><span data-stu-id="8b316-117">The evergreen model ensures that your app is taking advantage of the latest features and security updates for hosted web content.</span></span>

<span data-ttu-id="8b316-118">对于受限环境，将支持固定版本分发模型。</span><span class="sxs-lookup"><span data-stu-id="8b316-118">For constrained environments there will be support for a fixed version distribution model.</span></span> <span data-ttu-id="8b316-119">在此模型中，你的应用程序选择并打包特定版本的 WebView2。</span><span class="sxs-lookup"><span data-stu-id="8b316-119">In this model, your application selects and packages a specific version of WebView2.</span></span> <span data-ttu-id="8b316-120">对 Web 视图版本的更新不会自动发生，并且将由应用程序负责。</span><span class="sxs-lookup"><span data-stu-id="8b316-120">Updates to the WebView version do not occur automatically, and will be the responsibility of the application.</span></span> <span data-ttu-id="8b316-121">当你需要控制浏览器版本以及应用程序更新时，修复版本模型非常有用。</span><span class="sxs-lookup"><span data-stu-id="8b316-121">The fixed version model is beneficial when you need to control the browser version, and when your application updates.</span></span> 

### <span data-ttu-id="8b316-122">Microsoft Edge WebView2 运行时</span><span class="sxs-lookup"><span data-stu-id="8b316-122">Microsoft Edge WebView2 Runtime</span></span>

<span data-ttu-id="8b316-123">Microsoft Edge WebView2 运行时将打包经优化以供 WebView2 应用程序使用的浏览器二进制文件。</span><span class="sxs-lookup"><span data-stu-id="8b316-123">The Microsoft Edge WebView2 Runtime will package the browser binaries optimized for use by WebView2 applications.</span></span> <span data-ttu-id="8b316-124">它将独立运行或与安装了客户端边缘浏览器并排运行。</span><span class="sxs-lookup"><span data-stu-id="8b316-124">It will function standalone or side-by-side with a client Edge Browser installed.</span></span> <span data-ttu-id="8b316-125">安装运行时一次将支持在客户端计算机上运行的许多 WebView2 应用程序。</span><span class="sxs-lookup"><span data-stu-id="8b316-125">Installing the runtime once will support many WebView2 applications running on the client machine.</span></span> <span data-ttu-id="8b316-126">安装运行时不会以浏览器的形式显示给最终用户，并且将没有桌面快捷方式、开始菜单入口点或协议注册。</span><span class="sxs-lookup"><span data-stu-id="8b316-126">Installing the runtime will not appear as a browser to end-users, and will have no desktop shortcuts, start menu entry point, or protocol registration.</span></span>

<span data-ttu-id="8b316-127">使用 WebView2 运行时的应用程序将需要确保运行时安装已完成。</span><span class="sxs-lookup"><span data-stu-id="8b316-127">Applications that use the WebView2 Runtime will need to ensure that the runtime installation completed.</span></span> <span data-ttu-id="8b316-128">若要确保你的应用程序将运行时安装为依赖项，你可以将运行时添加到你的安装流。</span><span class="sxs-lookup"><span data-stu-id="8b316-128">To ensure your application installs the runtime as a dependency, you’ll be able to add the runtime to your install flow.</span></span> 
