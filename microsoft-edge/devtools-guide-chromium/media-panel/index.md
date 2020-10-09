---
description: 使用 "媒体" 面板查看每个浏览器选项卡的信息和调试媒体播放器。
title: 查看和调试媒体播放器信息
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/08/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: dfcf17861c0296e347007bc3a1a02a2b80661e6f
ms.sourcegitcommit: 912609aa49864e3363aaa3b245ff2aa4bec3fc3e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/08/2020
ms.locfileid: "11105177"
---
# <span data-ttu-id="d6697-104">查看和调试媒体播放器信息</span><span class="sxs-lookup"><span data-stu-id="d6697-104">View and debug media players information</span></span>  

<span data-ttu-id="d6697-105">使用 Microsoft Edge DevTools 中的 " **媒体** " 面板查看每个浏览器选项卡的信息和调试媒体播放器。</span><span class="sxs-lookup"><span data-stu-id="d6697-105">Use the **Media** panel in Microsoft Edge DevTools to view information and debug the media players per browser tab.</span></span>  

## <span data-ttu-id="d6697-106">打开 "媒体" 面板</span><span class="sxs-lookup"><span data-stu-id="d6697-106">Open the Media panel</span></span>  

<span data-ttu-id="d6697-107">**媒体**面板是 DevTools 中用于检查网页媒体播放器的主要位置。</span><span class="sxs-lookup"><span data-stu-id="d6697-107">The **Media** panel is the main place in DevTools for inspecting the media player of a webpage.</span></span>

1.  <span data-ttu-id="d6697-108">[打开 DevTools][DevtoolsGuideChromiumOpen]。</span><span class="sxs-lookup"><span data-stu-id="d6697-108">[Open DevTools][DevtoolsGuideChromiumOpen].</span></span>  
1.  <span data-ttu-id="d6697-109">若要打开 "**媒体**" 面板，请选择 "**自定义和控制 DevTools** `...`  >  **更多工具**  >  **媒体**"。</span><span class="sxs-lookup"><span data-stu-id="d6697-109">To open the **Media** panel, choose **Customize and control DevTools** `...` > **More tools** > **Media**.</span></span>  
    
    :::image type="complex" source="../media/media-panel-empty.msft.png" alt-text="媒体面板" lightbox="../media/media-panel-empty.msft.png":::
       <span data-ttu-id="d6697-111">**媒体** 面板</span><span class="sxs-lookup"><span data-stu-id="d6697-111">**Media** panel</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="d6697-112">查看媒体播放器信息</span><span class="sxs-lookup"><span data-stu-id="d6697-112">View media players information</span></span>  

1.  <span data-ttu-id="d6697-113">导航到具有媒体播放器（如以下网页）的网页。</span><span class="sxs-lookup"><span data-stu-id="d6697-113">Navigate to a webpage with a media player, such as the following webpage.</span></span>  
    
    [<span data-ttu-id="d6697-114">通过 Edge 开发人员工具最大限度地提高工作效率</span><span class="sxs-lookup"><span data-stu-id="d6697-114">Maximizing productivity with the Edge Developer Tools</span></span>][BingVideosSearchViewDetailMidE0BA14EC0E0D18C06C8DE0BA14EC0E0D18C06C8]  
    
1.  <span data-ttu-id="d6697-115">在 " **玩家** " 菜单下，显示一个媒体播放器。</span><span class="sxs-lookup"><span data-stu-id="d6697-115">Under the **Players** menu, a media player is displayed.</span></span>  
1.  <span data-ttu-id="d6697-116">选择玩家。</span><span class="sxs-lookup"><span data-stu-id="d6697-116">Select the player.</span></span>  <span data-ttu-id="d6697-117">" **属性** " 选项卡显示媒体播放器的属性。</span><span class="sxs-lookup"><span data-stu-id="d6697-117">The **Properties** tab displays the properties of the media player.</span></span>  
    
    :::image type="complex" source="../media/media-panel-view.msft.png" alt-text="媒体面板" lightbox="../media/media-panel-view.msft.png":::
       <span data-ttu-id="d6697-119">媒体属性</span><span class="sxs-lookup"><span data-stu-id="d6697-119">Media properties</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="d6697-120">若要查看所有媒体播放器事件，请选择 " **事件** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="d6697-120">To view all the media player events, choose the **Events** tab.</span></span>  
    
    :::image type="complex" source="../media/media-panel-events.msft.png" alt-text="媒体面板" lightbox="../media/media-panel-events.msft.png":::
       <span data-ttu-id="d6697-122">媒体事件</span><span class="sxs-lookup"><span data-stu-id="d6697-122">Media events</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="d6697-123">若要查看媒体播放器消息日志，请选择 " **消息** " 选项卡。 你可以按日志级别或字符串筛选邮件。</span><span class="sxs-lookup"><span data-stu-id="d6697-123">To view the media player message logs, choose the **Messages** tab.  You may filter the messages by log level or string.</span></span>  
    
    :::image type="complex" source="../media/media-panel-messages.msft.png" alt-text="媒体面板" lightbox="../media/media-panel-messages.msft.png":::
       <span data-ttu-id="d6697-125">媒体消息</span><span class="sxs-lookup"><span data-stu-id="d6697-125">Media messages</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="d6697-126">在 " **时间线** " 选项卡上，媒体播放和缓冲状态显示为 "实时"。</span><span class="sxs-lookup"><span data-stu-id="d6697-126">On the **Timeline** tab, the media playback and buffer status is displayed live.</span></span>  
    
    :::image type="complex" source="../media/media-panel-timeline.msft.png" alt-text="媒体面板" lightbox="../media/media-panel-timeline.msft.png":::
       <span data-ttu-id="d6697-128">媒体日程表</span><span class="sxs-lookup"><span data-stu-id="d6697-128">Media timeline</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="d6697-129">远程调试</span><span class="sxs-lookup"><span data-stu-id="d6697-129">Remote debugging</span></span>  

<span data-ttu-id="d6697-130">从 Windows 或 macOS 计算机上的 Android 设备上查看媒体播放器信息。</span><span class="sxs-lookup"><span data-stu-id="d6697-130">View the media players information on an Android device from your Windows or macOS computer.</span></span>  

1.  <span data-ttu-id="d6697-131">若要设置远程调试，请导航到 [开始使用 "远程调试 Android 设备][DevtoolsGuideChromiumRemoteDebuggingIndex]"。</span><span class="sxs-lookup"><span data-stu-id="d6697-131">To set up remote debugging, navigate to [Get started with remote debugging Android devices][DevtoolsGuideChromiumRemoteDebuggingIndex].</span></span>  
1.  <span data-ttu-id="d6697-132">远程查看媒体播放器信息。</span><span class="sxs-lookup"><span data-stu-id="d6697-132">View the media players information remotely.</span></span>  
    
    <!-- TODO: recreate image using an Android device -->  
    <!--  
    :::image type="complex" source="../media/media-panel-remote-debug.msft.png" alt-text="媒体面板" lightbox="../media/media-panel-remote-debug.msft.png":::
       Remote debugging  
    :::image-end:::  
    -->  
    
## <span data-ttu-id="d6697-133">隐藏和显示媒体播放器</span><span class="sxs-lookup"><span data-stu-id="d6697-133">Hide and show media players</span></span>  

<span data-ttu-id="d6697-134">有时，您在一个网页上运行多个媒体播放器，或使用同一浏览器选项卡浏览不同的网页，每个网页都有媒体播放器。</span><span class="sxs-lookup"><span data-stu-id="d6697-134">Sometimes you run more than one media player on a webpage, or use the same browser tab to browse different webpages, each with media players.</span></span>

<span data-ttu-id="d6697-135">你可以选择隐藏 \ (或显示 ) 每个媒体播放机，以便更轻松地进行调试体验。</span><span class="sxs-lookup"><span data-stu-id="d6697-135">You may choose to hide \(or show\) each media player for an easier debugging experience.</span></span>  

1.  <span data-ttu-id="d6697-136">使用相同的浏览器选项卡浏览到多个不同的视频网页。</span><span class="sxs-lookup"><span data-stu-id="d6697-136">Browse to several different video webpages using the same browser tab.</span></span>  
1.  <span data-ttu-id="d6697-137">若要隐藏媒体播放器，请完成以下操作之一。</span><span class="sxs-lookup"><span data-stu-id="d6697-137">To hide media players, complete one of the following actions.</span></span>  
    *   <span data-ttu-id="d6697-138">若要隐藏一个媒体播放器，请将鼠标悬停在媒体播放器上，打开上下文菜单 \ (右键单击 "\ ) "，然后选择 " **隐藏播放器**"。</span><span class="sxs-lookup"><span data-stu-id="d6697-138">To hide one media player, hover on a media player, open the contextual menu \(right-click\), and choose **Hide player**.</span></span>  
    *   <span data-ttu-id="d6697-139">若要隐藏所有其他媒体播放器，请将鼠标悬停在媒体播放器上，打开上下文菜单 \ (右键单击 \ ) ，然后选择 " **隐藏其他所有人**"。</span><span class="sxs-lookup"><span data-stu-id="d6697-139">To hide all of the other media players, hover on a media player, open the contextual menu \(right-click\), and choose **Hide all others**.</span></span>  
    
    :::image type="complex" source="../media/media-panel-hide-show.msft.png" alt-text="媒体面板" lightbox="../media/media-panel-hide-show.msft.png":::
       <span data-ttu-id="d6697-141">隐藏媒体播放器</span><span class="sxs-lookup"><span data-stu-id="d6697-141">Hide media players</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="d6697-142">导出媒体播放器信息</span><span class="sxs-lookup"><span data-stu-id="d6697-142">Export media player information</span></span>  

1.  <span data-ttu-id="d6697-143">若要将媒体播放器信息作为 JSON 文件下载，请将鼠标悬停在媒体播放器上，打开上下文菜单 \ (右键单击 \ ) ，然后选择 " **保存播放器信息**"。</span><span class="sxs-lookup"><span data-stu-id="d6697-143">To download the media player info as a JSON file, hover on a media player, open the contextual menu \(right-click\), and choose **Save player info**.</span></span>  
    
    :::image type="complex" source="../media/media-panel-save.msft.png" alt-text="媒体面板" lightbox="../media/media-panel-save.msft.png":::
       <span data-ttu-id="d6697-145">导出媒体信息</span><span class="sxs-lookup"><span data-stu-id="d6697-145">Export media information</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="d6697-146">与 Microsoft Edge 开发人员工具团队联系</span><span class="sxs-lookup"><span data-stu-id="d6697-146">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsGuideChromiumOpen]: ../open.md "打开 Microsoft Edge DevTools"  

[DevtoolsGuideChromiumRemoteDebuggingIndex]: ../remote-debugging/index.md "开始使用 "远程调试 Android 设备" |Microsoft 文档"  

[BingVideosSearchViewDetailMidE0BA14EC0E0D18C06C8DE0BA14EC0E0D18C06C8]: https://www.bing.com/videos/search?view=detail&mid=DE0BA14EC0E0D18C06C8DE0BA14EC0E0D18C06C8 "利用 Edge 开发工具 | 提高工作效率必应视频"  

> [!NOTE]
> <span data-ttu-id="d6697-150">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="d6697-150">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="d6697-151">原始页面可在 [此处](https://developers.google.com/web/tools/chrome-devtools/media-panel/index) 找到，并由 [Jecelyn Yeen][JecelynYeen] (开发人员和 DevTools，Chrome \ ) 。</span><span class="sxs-lookup"><span data-stu-id="d6697-151">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/media-panel/index) and is authored by [Jecelyn Yeen][JecelynYeen] \(Developer advocate, Chrome DevTools\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="d6697-153">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="d6697-153">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen  

