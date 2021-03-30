---
description: 通过在浏览器中边载扩展来测试扩展
title: 旁加载分机
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/24/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium、web 开发、html、css、javascript、开发人员、扩展
ms.openlocfilehash: 7070878b9608e6d239179078390f2315e0b289a1
ms.sourcegitcommit: 845a0d53a86bee3678f421adee26b3372cefce57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/08/2020
ms.locfileid: "11104769"
---
# <span data-ttu-id="398b6-104">旁加载扩展</span><span class="sxs-lookup"><span data-stu-id="398b6-104">Sideload an extension</span></span>

<span data-ttu-id="398b6-105">在开发期间，你可以使用 Microsoft Edge \(Chromium \ ) 浏览器来安全地运行和调试扩展。</span><span class="sxs-lookup"><span data-stu-id="398b6-105">During development, you may use the Microsoft Edge \(Chromium\) browser to run and debug your extension safely.</span></span> <span data-ttu-id="398b6-106">通过在浏览器中本地加载您的扩展，可以运行和测试您的扩展。</span><span class="sxs-lookup"><span data-stu-id="398b6-106">By sideloading your extension locally in your browser, you can run and test your extension.</span></span> <span data-ttu-id="398b6-107">本文介绍如何将扩展旁加载到 Microsoft Edge 中。</span><span class="sxs-lookup"><span data-stu-id="398b6-107">This article explains how to sideload extensions into Microsoft Edge.</span></span>

<span data-ttu-id="398b6-108">若要旁加载您的分机号，请按照下列步骤操作。</span><span class="sxs-lookup"><span data-stu-id="398b6-108">To sideload your extension, follow these steps.</span></span>

1.  <span data-ttu-id="398b6-109">`edge://extensions`选择浏览器顶部的三个圆点，然后选择 "**扩展**"，打开页面。</span><span class="sxs-lookup"><span data-stu-id="398b6-109">Open the `edge://extensions` page by choosing the three dots at the top of your browser, and then selecting **Extensions**.</span></span>

       :::image type="complex" source="./media/part1-threedots.png" alt-text="打开 &quot;edge://extensions&quot; 页面":::
          <span data-ttu-id="398b6-111">打开 "edge://extensions" 页面</span><span class="sxs-lookup"><span data-stu-id="398b6-111">Open the edge://extensions page</span></span> :::image-end:::

1.  <span data-ttu-id="398b6-112">在的 "扩展管理" 页上 `edge://extensions` ，使用页面左下角的开关启用 **开发人员模式** 。</span><span class="sxs-lookup"><span data-stu-id="398b6-112">On the extension management page at `edge://extensions`, turn on **Developer mode** using the toggle at the bottom left of the page.</span></span>

       :::image type="complex" source="./media/part1-developermode-toggle.png" alt-text="打开 &quot;edge://extensions&quot; 页面":::
          <span data-ttu-id="398b6-114">启用开发人员模式</span><span class="sxs-lookup"><span data-stu-id="398b6-114">Turn on Developer Mode</span></span> :::image-end:::

1.  <span data-ttu-id="398b6-115">首次安装扩展时，请选择 " **加载解压缩**"。</span><span class="sxs-lookup"><span data-stu-id="398b6-115">When installing your extension for the first time, choose **Load Unpacked**.</span></span>  <span data-ttu-id="398b6-116">系统将提示你输入扩展名源文件的目录。</span><span class="sxs-lookup"><span data-stu-id="398b6-116">You'll be prompted for the directory with your extension source files.</span></span>  <span data-ttu-id="398b6-117">您的扩展已安装在您的浏览器中，类似于从应用商店安装的扩展。</span><span class="sxs-lookup"><span data-stu-id="398b6-117">Your extension is installed in your browser, similar to extensions installed from the store.</span></span>  

       :::image type="complex" source="./media/part1-installed-extension.png" alt-text="打开 &quot;edge://extensions&quot; 页面":::
          <span data-ttu-id="398b6-119">显示旁加载扩展的已安装扩展页面</span><span class="sxs-lookup"><span data-stu-id="398b6-119">Installed extensions page showing a sideloaded extension</span></span> :::image-end:::

<span data-ttu-id="398b6-120">在开发过程中，你可能还需要执行以下任务。</span><span class="sxs-lookup"><span data-stu-id="398b6-120">During development, you may also need to perform the following tasks.</span></span>
* <span data-ttu-id="398b6-121">更新扩展。</span><span class="sxs-lookup"><span data-stu-id="398b6-121">Update the extension.</span></span> <span data-ttu-id="398b6-122">导航到 `edge://extensions` ，然后选择 " **重新加载** " 以更新您的扩展。</span><span class="sxs-lookup"><span data-stu-id="398b6-122">Navigate to `edge://extensions`, and then select **Reload** to update your extension.</span></span>  
* <span data-ttu-id="398b6-123">从浏览器中删除扩展。</span><span class="sxs-lookup"><span data-stu-id="398b6-123">Remove the extension from your browser.</span></span> <span data-ttu-id="398b6-124">导航到 `edge://extensions` ，然后选择 `Remove` "在您的分机上"。</span><span class="sxs-lookup"><span data-stu-id="398b6-124">Navigate to `edge://extensions`, and then select `Remove` on your extension.</span></span>