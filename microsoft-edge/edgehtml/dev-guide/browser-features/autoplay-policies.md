---
description: 确保网站上媒体内容按预期方式运行
title: 自动播放策略 - 开发人员指南
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge， media， video， audio， autoplay
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 85b91a8b87d73d6fccc6eac2aa64513f283d7f21
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232308"
---
# 自动播放策略  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

Microsoft Edge 为客户提供了个性化浏览首选项的能力，这些首选项可以自动播放具有声音的媒体，以便最大程度地减少 Web 上的干扰并节省带宽。  此外，Microsoft Edge 自动禁止在后台选项卡中自动播放媒体。  

用户可以使用全局和每站点自动[](#global-media-autoplay-settings)播放控件[](#per-site-media-autoplay-settings)自定义媒体行为，这提供以下选项：  

*   `Allow`  默认选项，在首次在前台查看选项卡时将继续播放视频，由网站自行决定。  

*   `Limit`  将自动播放限制为仅在视频静音时工作，因此用户永远不会对声音感到意外。  用户单击页面上的任何位置后，自动播放将重新启用，并且将继续允许该选项卡中的该域中的自动播放。  

*   `Block`  阻止在所有网站上播放，直到用户直接与媒体内容交互。  

## 全局媒体自动播放设置  

用户可以控制高级设置媒体自动播放下的所有**网站**  >  **的默认自动播放行为**。  

:::image type="complex" source="../media/autoplay_global.png" alt-text="全局媒体自动播放设置" lightbox="../media/autoplay_global.png":::
   全局媒体自动播放设置  
:::image-end:::  

## 每站点媒体自动播放设置  

用户可以在网站信息窗格的"网站权限"部分下按网站**** 控制自动播放行为。  可以通过单击地址栏左侧的信息图标或锁定图标，然后单击媒体自动播放设置开始找到此设置。 ****  

每个站点设置将覆盖全局设置。  例如，如果用户已设置其全局设置，但将每个站点设置更改为，则该网站的自动播放将被 `Allow` `Block` 阻止。  

:::image type="complex" source="../media/autoplay_per-site.png" alt-text="每站点媒体自动播放设置" lightbox="../media/autoplay_per-site.png":::
   每站点媒体自动播放设置  
:::image-end:::  

## Web 开发人员的最佳实践  

下面是如何确保使用网站上托管的媒体获得良好的用户体验：  

*   假设每次使用媒体元素都需要用户手势才能启动播放 \ (因为用户可以在任意时间点阻止自动播放\) 进行相应规划。  全局和每站点自动播放策略适用于所有和元素，而不管 `<audio>` `<video>` 它们如何用于你的站点  

*   确保网站媒体和广告内容上始终存在媒体控件。  这样，如果用户在页面上自动播放被阻止，则用户可以重新启动播放。  

*   评估自动播放可能会如何影响用户在网站上的体验，并考虑以最大程度减少不需要的媒体播放的方式使用自动播放。  如果自动播放是体验的重要组成部分，请考虑使用静音内容启动并允许用户取消静音。  对于要自动播放的静音内容，必须显式静音或不设置音频源。  否则，不会将元素视为静音。  

*   除非绝对有必要否则，否则请使用本机浏览器控件进行媒体播放。  这将确保为用户提供一致的体验。  如果要改为生成自定义控件，请确保媒体控件始终存在，并且控件对自动播放抑制做出正确响应。  

### Iframe 委派  

无论内容源如何，在 an 中自动播放都将从 `<iframe>` 父页面继承自动播放权限。  在每个媒体文件由单独的 iframe 托管的播放列表方案中，用户只需为整个播放列表启动播放一次。  

### 检测何时允许自动播放  

通过检查媒体元素上函数返回的承诺，可以调整播放控件，以在自动播放被阻止时 `play()` 显示正确的状态：  

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
