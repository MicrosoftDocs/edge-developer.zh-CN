---
description: 在浏览器中旁加载扩展来测试扩展
title: 旁加载扩展
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/24/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge-chromium， Web 开发， html， css， javascript， 开发人员， 扩展
ms.openlocfilehash: 7070878b9608e6d239179078390f2315e0b289a1
ms.sourcegitcommit: 845a0d53a86bee3678f421adee26b3372cefce57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/08/2020
ms.locfileid: "11104769"
---
# <span data-ttu-id="cc37a-104">旁加载扩展</span><span class="sxs-lookup"><span data-stu-id="cc37a-104">Sideload an extension</span></span>

<span data-ttu-id="cc37a-105">在开发期间，可以使用 Microsoft Edge \(Chromium\) 浏览器安全运行和调试扩展。</span><span class="sxs-lookup"><span data-stu-id="cc37a-105">During development, you may use the Microsoft Edge \(Chromium\) browser to run and debug your extension safely.</span></span> <span data-ttu-id="cc37a-106">通过在你的浏览器中本地旁加载扩展，你可以运行和测试扩展。</span><span class="sxs-lookup"><span data-stu-id="cc37a-106">By sideloading your extension locally in your browser, you can run and test your extension.</span></span> <span data-ttu-id="cc37a-107">本文介绍如何将扩展旁加载到Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="cc37a-107">This article explains how to sideload extensions into Microsoft Edge.</span></span>

<span data-ttu-id="cc37a-108">若要旁加载扩展，请按照以下步骤操作。</span><span class="sxs-lookup"><span data-stu-id="cc37a-108">To sideload your extension, follow these steps.</span></span>

1.  <span data-ttu-id="cc37a-109">通过 `edge://extensions` 选择浏览器顶部的三个点，然后选择扩展打开 **页面**。</span><span class="sxs-lookup"><span data-stu-id="cc37a-109">Open the `edge://extensions` page by choosing the three dots at the top of your browser, and then selecting **Extensions**.</span></span>

       :::image type="complex" source="./media/part1-threedots.png" alt-text="打开 edge://extensions 页":::
          <span data-ttu-id="cc37a-111">打开"edge://extensions"页</span><span class="sxs-lookup"><span data-stu-id="cc37a-111">Open the edge://extensions page</span></span> :::image-end:::

1.  <span data-ttu-id="cc37a-112">在扩展管理页面的 `edge://extensions` 上，使用\*\*\*\* 页面左下角的开关打开开发人员模式。</span><span class="sxs-lookup"><span data-stu-id="cc37a-112">On the extension management page at `edge://extensions`, turn on **Developer mode** using the toggle at the bottom left of the page.</span></span>

       :::image type="complex" source="./media/part1-developermode-toggle.png" alt-text="打开开发人员模式":::
          <span data-ttu-id="cc37a-114">打开开发人员模式</span><span class="sxs-lookup"><span data-stu-id="cc37a-114">Turn on Developer Mode</span></span> :::image-end:::

1.  <span data-ttu-id="cc37a-115">首次安装扩展时，选择"**加载未打包"。**</span><span class="sxs-lookup"><span data-stu-id="cc37a-115">When installing your extension for the first time, choose **Load Unpacked**.</span></span>  <span data-ttu-id="cc37a-116">系统将提示你输入包含扩展源文件的目录。</span><span class="sxs-lookup"><span data-stu-id="cc37a-116">You'll be prompted for the directory with your extension source files.</span></span>  <span data-ttu-id="cc37a-117">你的扩展安装在浏览器中，类似于从应用商店安装的扩展。</span><span class="sxs-lookup"><span data-stu-id="cc37a-117">Your extension is installed in your browser, similar to extensions installed from the store.</span></span>  

       :::image type="complex" source="./media/part1-installed-extension.png" alt-text="显示旁加载扩展的已安装扩展页":::
          <span data-ttu-id="cc37a-119">显示旁加载扩展的已安装扩展页</span><span class="sxs-lookup"><span data-stu-id="cc37a-119">Installed extensions page showing a sideloaded extension</span></span> :::image-end:::

<span data-ttu-id="cc37a-120">在开发过程中，可能还需要执行以下任务。</span><span class="sxs-lookup"><span data-stu-id="cc37a-120">During development, you may also need to perform the following tasks.</span></span>
* <span data-ttu-id="cc37a-121">更新扩展。</span><span class="sxs-lookup"><span data-stu-id="cc37a-121">Update the extension.</span></span> <span data-ttu-id="cc37a-122">导航到 `edge://extensions` ，然后选择" **重新加载** "以更新扩展。</span><span class="sxs-lookup"><span data-stu-id="cc37a-122">Navigate to `edge://extensions`, and then select **Reload** to update your extension.</span></span>  
* <span data-ttu-id="cc37a-123">从浏览器中删除扩展。</span><span class="sxs-lookup"><span data-stu-id="cc37a-123">Remove the extension from your browser.</span></span> <span data-ttu-id="cc37a-124">导航到 `edge://extensions` ，然后在 `Remove` 扩展上选择 。</span><span class="sxs-lookup"><span data-stu-id="cc37a-124">Navigate to `edge://extensions`, and then select `Remove` on your extension.</span></span>