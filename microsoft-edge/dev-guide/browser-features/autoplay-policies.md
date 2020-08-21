---
description: 确保网站上的媒体内容按预期运行
title: 自动播放策略 - 开发用户指南
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘、媒体、视频、音频、自动播放
ms.custom: seodec18
ms.openlocfilehash: 39c9bd8e9921167dfc3a9ab1a4cc12b2157f0f6f
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "10942058"
---
# 自动播放策略  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

Microsoft Edge 为客户提供了在网站上个性化其浏览首选项的功能，这些媒体可自动播放媒体，以便最大程度地减少 Web 上的分词并节约带宽。  此外，Microsoft Edge 会自动断放背景选项卡中的媒体自动播放。  

用户可以使用全局和每个站点的自动播放控件[global](#global-media-autoplay-settings)自定义媒体行为[per-site](#per-site-media-autoplay-settings)，这些控件提供以下选项：  

*   `Allow`  当在前台查看选项卡时，默认状态，并继续播放视频。  

*   `Limit`  仅在视频静音时限制自动播放功能才能正常工作，因此用户绝对不会被声音所打扰。  用户单击页面上任意位置后，将重新启用自动播放，并且将继续允许在该选项卡上该域内进行允许。  

*   `Block`  禁止在所有网站上进行无关播放，直到用户直接与媒体内容进行交互。  

## 全局媒体自动播放设置  

用户可以控制"高级设置媒体自动播放"下的所有**网站的默认自动播放**  >  **行为**。  

:::image type="complex" source="../media/autoplay_global.png" alt-text="全局媒体自动播放设置" lightbox="../media/autoplay_global.png":::
   全局媒体自动播放设置  
:::image-end:::  

## 站点媒体自动播放设置  

用户可以基于网站共享信息窗格的" **网站权限"** 部分控制自动播放操作。  可通过单击地址栏左侧的信息图标或锁图标并单击媒体自动播放设置以开始设置 **，找到** 此设置。  

每网站设置将覆盖全局设置。  例如，如果用户已将其全局设置设为"全局"， `Allow` 但将针对该网站将阻止 `Block` 自动播放。  

:::image type="complex" source="../media/autoplay_per-site.png" alt-text="站点媒体自动播放设置" lightbox="../media/autoplay_per-site.png":::
   站点媒体自动播放设置  
:::image-end:::  

## Web 开发人员的最佳实践  

下面介绍如何确保网站上托管的媒体获得良好用户体验：  

*   假设媒体元素的每个使用都要求用户手势才能启动播放 \ (，可能是用户随时在任何时间\) 阻止自动播放并相应地进行相应规划。  全局和每网站自动播放策略适用于所有和元素，无受这些策略 `<audio>` 在您的网站 `<video>` 上的使用方式  

*   确保媒体控件始终显示在网站媒体和广告内容上。  如果在页面上已被阻止了自动播放，这将使用户可以重新启动播放。  

*   评估自动播放如何影响您的网站上的用户体验，并考虑使用减少不需要的媒体播放的方式使用自动播放功能。  如果自动播放是体验的关键部分，请考虑使用静音内容以启动，并允许用户取消静音。  若要使内容自动播放，音频源必须显式静音或未设置。  否则，将不会视为静音元素。  

*   除非绝对必要执行其他操作，否则请使用本机浏览器控件执行媒体播放。  这样会确保用户体验的一致。  如果要改建自定义控件，请确保始终显示媒体控件，并且你的控件能正确地对自动播放来弹出内容进行正确反应。  

### Iframe 委发  

自动播放 `<iframe>` 功能将从父页面落后，无管内容来源是如何的。  在一个被单独的 iframe 托管的播放列表方案中，用户只需为整个播放列表启动一次播放。  

### 检测允许自动播放何时  

通过检查媒体元素上返回的承诺，你可以调整播放控件以在自动播放被阻止 `play()` 时显示正确的状态：  

```javascript
var promise = document.querySelector('video').play();

if (promise !== undefined) { 
    promise.catch(_error => { 
        // Autoplay was blocked
        // Show user media controls to manually start playback
    }).then(() => { 
        // Autoplay started
    }); 
}
```  
