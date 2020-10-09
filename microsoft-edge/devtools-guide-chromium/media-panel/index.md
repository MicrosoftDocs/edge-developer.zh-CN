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
# 查看和调试媒体播放器信息  

使用 Microsoft Edge DevTools 中的 " **媒体** " 面板查看每个浏览器选项卡的信息和调试媒体播放器。  

## 打开 "媒体" 面板  

**媒体**面板是 DevTools 中用于检查网页媒体播放器的主要位置。

1.  [打开 DevTools][DevtoolsGuideChromiumOpen]。  
1.  若要打开 "**媒体**" 面板，请选择 "**自定义和控制 DevTools** `...`  >  **更多工具**  >  **媒体**"。  
    
    :::image type="complex" source="../media/media-panel-empty.msft.png" alt-text="媒体面板" lightbox="../media/media-panel-empty.msft.png":::
       **媒体** 面板  
    :::image-end:::  
    
## 查看媒体播放器信息  

1.  导航到具有媒体播放器（如以下网页）的网页。  
    
    [通过 Edge 开发人员工具最大限度地提高工作效率][BingVideosSearchViewDetailMidE0BA14EC0E0D18C06C8DE0BA14EC0E0D18C06C8]  
    
1.  在 " **玩家** " 菜单下，显示一个媒体播放器。  
1.  选择玩家。  " **属性** " 选项卡显示媒体播放器的属性。  
    
    :::image type="complex" source="../media/media-panel-view.msft.png" alt-text="媒体面板" lightbox="../media/media-panel-view.msft.png":::
       媒体属性  
    :::image-end:::  
    
1.  若要查看所有媒体播放器事件，请选择 " **事件** " 选项卡。  
    
    :::image type="complex" source="../media/media-panel-events.msft.png" alt-text="媒体面板" lightbox="../media/media-panel-events.msft.png":::
       媒体事件  
    :::image-end:::  
    
1.  若要查看媒体播放器消息日志，请选择 " **消息** " 选项卡。 你可以按日志级别或字符串筛选邮件。  
    
    :::image type="complex" source="../media/media-panel-messages.msft.png" alt-text="媒体面板" lightbox="../media/media-panel-messages.msft.png":::
       媒体消息  
    :::image-end:::  
    
1.  在 " **时间线** " 选项卡上，媒体播放和缓冲状态显示为 "实时"。  
    
    :::image type="complex" source="../media/media-panel-timeline.msft.png" alt-text="媒体面板" lightbox="../media/media-panel-timeline.msft.png":::
       媒体日程表  
    :::image-end:::  
    
### 远程调试  

从 Windows 或 macOS 计算机上的 Android 设备上查看媒体播放器信息。  

1.  若要设置远程调试，请导航到 [开始使用 "远程调试 Android 设备][DevtoolsGuideChromiumRemoteDebuggingIndex]"。  
1.  远程查看媒体播放器信息。  
    
    <!-- TODO: recreate image using an Android device -->  
    <!--  
    :::image type="complex" source="../media/media-panel-remote-debug.msft.png" alt-text="媒体面板" lightbox="../media/media-panel-remote-debug.msft.png":::
       Remote debugging  
    :::image-end:::  
    -->  
    
## 隐藏和显示媒体播放器  

有时，您在一个网页上运行多个媒体播放器，或使用同一浏览器选项卡浏览不同的网页，每个网页都有媒体播放器。

你可以选择隐藏 \ (或显示 ) 每个媒体播放机，以便更轻松地进行调试体验。  

1.  使用相同的浏览器选项卡浏览到多个不同的视频网页。  
1.  若要隐藏媒体播放器，请完成以下操作之一。  
    *   若要隐藏一个媒体播放器，请将鼠标悬停在媒体播放器上，打开上下文菜单 \ (右键单击 "\ ) "，然后选择 " **隐藏播放器**"。  
    *   若要隐藏所有其他媒体播放器，请将鼠标悬停在媒体播放器上，打开上下文菜单 \ (右键单击 \ ) ，然后选择 " **隐藏其他所有人**"。  
    
    :::image type="complex" source="../media/media-panel-hide-show.msft.png" alt-text="媒体面板" lightbox="../media/media-panel-hide-show.msft.png":::
       隐藏媒体播放器  
    :::image-end:::  
    
## 导出媒体播放器信息  

1.  若要将媒体播放器信息作为 JSON 文件下载，请将鼠标悬停在媒体播放器上，打开上下文菜单 \ (右键单击 \ ) ，然后选择 " **保存播放器信息**"。  
    
    :::image type="complex" source="../media/media-panel-save.msft.png" alt-text="媒体面板" lightbox="../media/media-panel-save.msft.png":::
       导出媒体信息  
    :::image-end:::  
    
## 与 Microsoft Edge 开发人员工具团队联系  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsGuideChromiumOpen]: ../open.md "打开 Microsoft Edge DevTools"  

[DevtoolsGuideChromiumRemoteDebuggingIndex]: ../remote-debugging/index.md "开始使用 "远程调试 Android 设备" |Microsoft 文档"  

[BingVideosSearchViewDetailMidE0BA14EC0E0D18C06C8DE0BA14EC0E0D18C06C8]: https://www.bing.com/videos/search?view=detail&mid=DE0BA14EC0E0D18C06C8DE0BA14EC0E0D18C06C8 "利用 Edge 开发工具 | 提高工作效率必应视频"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面可在 [此处](https://developers.google.com/web/tools/chrome-devtools/media-panel/index) 找到，并由 [Jecelyn Yeen][JecelynYeen] (开发人员和 DevTools，Chrome \ ) 。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen  

