---
description: Microsoft Edge Web Apps 中的最新实验功能
title: 实验功能|渐进式 Web 应用
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/19/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， 实验， 渐进式 Web 应用， Web 应用， PWA， PWA
ms.openlocfilehash: 641b6fd5185e7f96289c1de6482764979ee0981d
ms.sourcegitcommit: 9cc54ba3e731ecc8b713c3cf215018848f7405b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/19/2021
ms.locfileid: "11496753"
---
# <a name="experimental-features-in-progressive-web-apps-pwas"></a>渐进式 Web 应用和 PBA (实验)   

Microsoft Edge提供对仍在开发中的实验性功能的访问权限。  若要确定每个功能是否就绪以及何时发布每个功能，请进行测试 [并提供反馈](#providing-feedback-on-experimental-features)。  

实验功能在所有渠道中Microsoft Edge，但最新的实验功能仅在 Microsoft Edge Canary 渠道 中提供。  

## <a name="turn-on-experimental-features"></a>打开试验功能  

若要在 Microsoft Edge 中打开\（或关闭\）试验功能，请完成以下步骤。  
  
1.  打开 Microsoft Edge。   
    
    > [!NOTE]
    > 确保使用Microsoft Edge列出实验的最新版本。  导航到 [实验功能](#features-that-are-available-to-test)。  
    
1.  导航到 `edge://flags`。  
1.  导航到相关实验。  
1.  选择实验说明旁边的下拉菜单并选择 `Enabled` 。  
    
    :::image type="complex" source="../media/turn-on-experimental-flag.png" alt-text="选择启用以打开实验" lightbox="../media/turn-on-experimental-flag.png":::
       选择 **启用** 以打开实验  
    :::image-end:::  
    
    > [!NOTE]
    > 每个实验通常都有一个下拉菜单来选择以下值。  如果实验功能没有"实验"条目，则提供**** 说明以Microsoft Edge命令行开始使用该功能。
    > 
    > *   `Default`  
    > *   `Disabled`  
    > *   `Enabled`  
    
1.  重启 Microsoft Edge。  
    
### <a name="origin-trials"></a>原始试验  

Microsoft Edge有时使用源试用版来测试特定域或网站的功能。  你可能想要对网站使用源试用版来应用特定功能。  如果你是网站所有者，你可以注册源试用版。  源试用版向访问你的Microsoft Edge的用户提供一定比例的功能。

有关源试用版详细信息，请导航到Microsoft Edge[源试用版开发人员控制台。][MicrosoftDeveloperMicrosoftEdgeOriginTrials]  
    
> [!NOTE]
> 实验性功能会不断更新，并且可能会导致性能问题。  若要关闭实验功能，请导航到打开 [实验](#turn-on-experimental-features)功能，导航到实验，然后选择 `Disabled` 。  

## <a name="features-that-are-available-to-test"></a>可供测试的功能  

以下列表介绍了新的实验性 Web 应用功能，这些功能可用于测试和验证Microsoft Edge。  

| 功能 | Microsoft Edge 版本 | 平台 |  
|:--- |:--- |:--- |  
| [URI 协议处理](#uri-protocol-handling) | 91 或更高版本 | Windows 和 Linux |    
| [URL 链接处理](#url-link-handling) | 91 或更高版本 | Windows|
| [适用于桌面应用的窗口控件覆盖层](#window-controls-overlay-for-installed-desktop-web-apps) | 91 或更高版本 | Windows 10|   
| [在操作系统登录时运行](#run-on-os-login) | 88 或更高版本 | 全部 |  
| [快捷方式](#shortcuts) | 87 或更高版本 | 全部 |  
| [文件处理](#file-handling) | 83 或更高版本 | 所有桌面 |  


## <a name="uri-protocol-handling"></a>URI 协议处理  

统一资源标识符 \ (URI\) 可用于定义使用 HTTP 或 FTP 协议的网页和 Web 内容的链接。  URI 可用于描述指向您编成架构中任何内容的链接。  例如，协议用于描述电子邮件链接，操作系统 `mailto://` \ (OS\) 或浏览器决定哪个网页或应用应处理该协议。  

有关基于浏览器的现有支持，请导航到基于 [Web 的协议处理程序][MdnDocsWebApiNavigatorRegisterprotocolhandlerWebBasedProtocolHandlers]。  

此功能允许您完成以下操作。  

*   使用 web PWA清单向主机操作系统注册你的应用程序
*   声明PWA处理特定 URI 协议  
     
将 PWA 注册为协议处理程序后，当用户使用特定方案（如浏览器或本机应用）选择超链接时，操作系统将激活注册的 PWA 并接收 `mailto://` `web+music://` URI。  

此功能要求你更新 Web 应用清单以在需要指定两个字段的 `protocol_handlers` 数组中包括数组：  

*   `protocol`：用于处理请求的协议，例如 或 `mailto` `web+jngl` 。  
*   `url`：处理协议的应用作用域中的 HTTPS URI。  将来，计划替换以协议处理程序方案开始的 `%s` URI。  
    
更新清单以支持要注册的协议。  启用此功能后，Microsoft Edge执行以下操作。  

1.  检测清单中的更改  
1.  为协议注册应用  
    
如果多个应用注册协议，则向用户显示提示。  用户从操作系统或浏览器呈现的列表中选择相应的应用。  

若要在 Windows 上预览 Microsoft Edge 中的协议Windows，[请导航到](#turn-on-experimental-features)"打开实验性功能"并打开"桌面PWA**协议处理"。**  

有关为协议处理程序运行的源试用版详细信息，请导航到注册 [Web 应用协议处理程序注册][MicrosoftDeveloperMicrosoftEdgeOriginTrialsWebAppProtocolHandlerRegistrationRegistration]。  

### <a name="example-manifest"></a>示例清单

在此例中，Web 应用清单声明应用应注册为处理协议 和 `web+jngl` `web+jnglstore` 。

```json
{
  "name": "Jungle",
  "description": "A plant encyclopedia",
  "protocol_handlers": [
    {
      "protocol": "web+jngl",
      "url": "/lookup?type=%s"
    },
    {
      "protocol": "web+jnglstore",
      "url": "/shop?for=%s"
    }
  ],
  "icons": [
    {
      "src": "images/icons-192.png",
      "type": "image/png",
      "sizes": "192x192"
    },
  ],
  "background_color": "#007f87",

  "display": "standalone",
  "start_url": "/",
}
```  
 
## <a name="url-link-handling"></a>URL 链接处理  

统一资源定位器 \ (URL\) 是一种 URI。  当渐进 Web 应用 \ (PWA\) 注册为 https URI 的处理程序时，创建更具吸引力的体验。  PBA 可能会请求在激活关联的 URI 时启动。  例如，如果用户从电子邮件中选择指向新闻文章的链接。  用于PWA新闻文章的关联内容将自动启动以处理链接激活。  

此功能允许你使用 Web PWA向浏览器注册网站，并声明浏览器处理特定链接。  若要向PWA注册网站，请向清单 `url_handlers` 文件添加可选成员。  `url_handlers`成员是 `object[]` 一个 ，用于对应用希望处理的 URI 的来源进行分组。  

浏览器使用位于源上的 `web-app-origin-association` JSON 文件验证链接处理。  源文件进一步微调源的包含路径或排除路径。  有关测试 URL 处理程序的详细说明，请导航到[作为 URL 处理程序的 PWA。][GithubWicgPwaUrlHandlerBlobMainExplainerMd]  

To preview URL link handling in Microsoft Edge on Windows， navigate to [Turn on experimental features](#turn-on-experimental-features) and turn on Desktop PWA URL **Handling**.  

### <a name="example-of-the-url_handlers-in-the-manifest"></a>清单url_handlers示例  

以下代码段是包含 成员的示例 Web 应用 `url_handlers` 清单。  

```json 
{
    "name": "Contoso Business App",
    "display": "standalone",
    "icons": [
        {
            "src": "images/icons-144.png",
            "type": "image/png",
            "sizes": "144x144"
        }
    ],
    "capture_links": "existing_client_event",
    "url_handlers" : [
        {
            "origin": "https://contoso.com"
        },
        {
            "origin": "https://conto.so"
        },
        {
            "origin": "https://*.contoso.com"
        }
    ]
}
```  

如果PWA URI 与 中的一个源字符串匹配，并且浏览器验证源是否同意允许此应用处理此类 URI，该 URI 将匹配 URL 处理。 `url_handlers`  

`url_handlers`成员包含包含请求源的范围和其他不相关的PWA。  不将 URI 限制为与请求的 URI 相同的范围或域PWA允许对相同内容使用不同的域名，但使用相同的域名PWA。  

#### <a name="wildcard-matching"></a>通配符匹配  

使用通配符 \ (`*` \) 匹配一个或多个字符。  

通配符前缀用于成员的来源字符串中 `url_handlers` ，以匹配不同的子域。  前缀必须针对 `*.` 此用法。  使用 `https` 通配符前缀时将假定此方案。  

例如， `url_handlers` 成员值设置为 `*.contoso.com` matches 和 `tenant.contoso.com` `www.tenant.contoso.com` ，但不匹配 `contoso.com` 。  

## <a name="window-controls-overlay-for-installed-desktop-web-apps"></a>窗口控件 已安装桌面 Web 应用的覆盖层  

若要为桌面安装的 Web 应用创建沉浸式标题栏（如本机应用），"窗口控件覆盖"功能将完成以下操作。 ****  
    
1.  删除系统保留的标题栏。  它通常跨越客户端框架的宽度。  
1.  将其替换为覆盖层。  它仅包含用户控制窗口本身所需的关键系统所需窗口控件。  
    
提供覆盖后，可使用整个 Web 客户端区域。  此功能包括清单更新。  它提供用于确定覆盖的大小和位置的方法，以帮助你安排内容。  

若要预览窗口中窗口控件覆盖Microsoft Edge Windows 10，请导航到打开实验性功能并导航[](#turn-on-experimental-features)到桌面PWA**窗口控件覆盖**。   

### <a name="examples-of-title-bar-area-customization"></a>标题栏区域自定义示例  

此功能基于本机应用中自定义标题栏的功能。  你可以自定义重要应用操作或通知的标题栏。  查看以下代码和Microsoft Visual Studio示例Microsoft Teams。  

#### <a name="visual-studio-code"></a>Visual Studio Code  

Microsoft Visual Studio代码是在位于多个桌面平台上的"部署"上构建的常用编辑器。  

以下示例显示Visual Studio Code栏以最大化可用屏幕空间以在标题栏中包括当前文件名和顶级菜单结构。  

:::image type="complex" source="../media/visual-studio-code-title-customization.png" alt-text="标题栏中的示例Visual Studio Code" lightbox="../media/visual-studio-code-title-customization.png":::
   标题栏中的示例Visual Studio Code  
:::image-end:::  

#### <a name="microsoft-teams"></a>Microsoft Teams  

Workplace collaboration and communication tool Microsoft Teams is built with Desktop and available on multiple desktop platforms.  在下面的示例中，Microsoft Teams和导航 `back` `forward` 按钮、搜索框和用户配置文件控件。  

:::image type="complex" source="../media/teams-title-customization.png" alt-text="标题栏中的示例Microsoft Teams" lightbox="../media/teams-title-customization.png":::
   标题栏中的示例Microsoft Teams  
:::image-end:::  

### <a name="overlay-window-controls-on-a-frameless-window"></a>无框架窗口上的覆盖窗口控件  

为了最大化 Web 内容的可地址区域，浏览器会创建无框架窗口。  无框架窗口删除所有浏览器 UI，但作为覆盖提供的窗口控件除外。  窗口控件覆盖允许用户仍最小化、最大化、还原和关闭应用。  它还提供对使用 Web 应用菜单的相关浏览器控件的访问。  对于Chromium浏览器，覆盖层包括以下控件。  

*   每个窗口控件按钮的宽度和高度相同的可拖动区域  
*   The**设置 and more** \ (...\) button  
*   窗口控件按钮最小化、最大化、还原和关闭  
    
除了前面列出的控件之外，覆盖层中显示的 UI 将在以下方案中动态调整大小。  

*   启动已安装的 Web 应用后，网页的原点会在**设置**左侧显示更多 \ (...\) 菜单几秒钟，然后消失。  
*   如果用户使用**设置**和更多 \ (...\) 菜单与扩展进行交互，则扩展的图标显示在三点菜单左侧的覆盖中。  退出任何扩展对话框后，图标将从覆盖层中删除。  
    
| 语言方向 | 覆盖位置 | 详细信息 |  
|:--- |:--- |:--- |  
| 从左到右 \ (LTR\)  | 客户区域左上角 | 翻转控件 |  
| 从右到左 \ (RTL\)  | 工作区的右上角 |  |  

> [!IMPORTANT]
> 覆盖始终位于 Web 内容的 Z 索引顶部，并接受所有用户输入，而不会将输入流到 Web 内容。  

### <a name="working-around-the-window-controls-overlay"></a>处理窗口控件覆盖层  

Web 内容必须知道控件覆盖的保留区域。  确保保留区域不需要用户交互。  在浏览器中查询控件覆盖的矩形边界和可见性。  该信息通过 JavaScript API 和 CSS 环境变量提供给你。  

#### <a name="javascript-apis"></a>JavaScript API  

属性 `windowControlsOverlay` 上的新 `window.navigator` 对象允许您查询控件覆盖的边框。  

对象 `windowControlsOverlay` 具有以下两个对象。  

*   `getBoundingClientRect()`  返回一个 `DOMRect` 对象。  对象 `DOMRect` 表示窗口控件覆盖层下的区域。  
*   `visible` 是一个 boolean 值，指示呈现和显示控件覆盖。  
    
> [!IMPORTANT]
> 出于隐私原因，Web 内容中的 `windowControlsOverlay` `iframe` 元素无法访问 。  

每当调整覆盖大小时，都会在对象上运行一个事件，以通知客户端 `geometrychange` `navigator.windowControlsOverlay` 重新计算内容布局。  重新计算的内容布局基于覆盖层的新边界矩形。  

#### <a name="css-environment-variables"></a>CSS 环境变量  

除了 JavaScript API 之外，您还可以使用 CSS 查询控件覆盖的边框。  使用以下四个新的 CSS 环境变量完成查询。  

*   `titlebar-area-x`  
*   `titlebar-area-y`  
*   `titlebar-area-width`  
*   `titlebar-area-height`  
    
### <a name="define-draggable-regions-in-web-content"></a>在 Web 内容中定义可拖动区域  

用户希望抓取和拖动窗口的上半部分。  若要满足预期要求，请声明 Web 内容的特定部分为可拖动。  
若要指定元素是可拖动的，请使用 WebKit 专有 `-webkit-app-region` CSS 属性。  CSS 工作组将继续努力标准化 `app-region` 该属性。  

### <a name="custom-title-bar-example"></a>自定义标题栏示例  

以下示例显示新功能如何使用自定义标题栏创建 Web 应用。  

:::image type="complex" source="../media/teams-title-customization-example.png" alt-text="自定义标题栏中的示例Microsoft Teams" lightbox="../media/teams-title-customization-example.png":::
   自定义标题栏中的示例Microsoft Teams  
:::image-end:::  

#### <a name="manifestwebmanifest"></a>manifest.webmanifest  

在清单中，将 `display_override` array 设置为  `window-controls-overlay` 。  将 `theme_color` 设置为标题栏的颜色选择。  在任一项或不受支持时，将显示模式 `display_override` `window-controls-overlay` 设置为适当的回退。  

以下代码段包括建议的清单更新。  

```json
{
  "name": "Example PWA",
  "display": "standalone",
  "display_override": [ 
    "window-controls-overlay" 
  ],
  "theme_color": "#254B85"
}
```  

### <a name="indexhtml"></a>index.html  

以下 ID 表示网页的两个主要区域。  

*   `titleBarContainer`  
*   `mainContent`  
    
ID `div` 为 `titleBar` 的 元素设置为 ， `draggable` 搜索框 `input` 子元素设置为 `nonDraggable` 。  

```html
<div id="titleBar" class=" draggable">
    <span class="draggable">Example PWA</span>
    <input class="nonDraggable" type="text" placeholder="Search"></input>
</div>
```

在具有 ID 的 元素中，具有 ID 的 表示标题栏区域中 `div` `titleBarContainer` `div` `titleBar` 的可见部分。  

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width">
    <title>Example PWA</title>
    <link rel="stylesheet" href="style.css">
    <link rel="manifest" href="./manifest.webmanifest">
  </head>
  <body>
    <div id="titleBarContainer">
      <div id="titleBar" class=" draggable">
        <span class="draggable">Example PWA</span>
        <input class="nonDraggable" type="text" placeholder="Search"></input>
      </div>
    </div>
    <div id="mainContent"><!-- The rest of the webpage --></div>
  </body>
</html>
```  

### <a name="stylecss"></a>style.css  

使用 和 设置可拖动和非可拖动 `-webkit-app-region: drag` 区域 `-webkit-app-region: no-drag` 。  

```css
.draggable {
    app-region: drag;
    /* Pre-fix app-region during standardization process */
    -webkit-app-region: drag;
}

.nonDraggable {
    app-region: no-drag;
    /* Pre-fix app-region during standardization process */
    -webkit-app-region: no-drag;
}
```  

对于 `body` 元素，边距设置为 ，以确保标题栏 `0` 到达窗口的边缘。  

```css
body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    margin: 0;
}
```  

`titleBarContainer`ID 使用 `position: absolute` 并设置 `top` `titlebar-area-inset-top` ，将容器附加到网页顶部。  `bottom`如果窗口控件覆盖层不可见，则 设置为 并 `titlebar-area-inset-bottom` `100% - var(--fallback-title-bar-height)` 恢复为 。  ID 的背景 `titleBarContainer` 颜色与 `theme_color` 相同。  宽度设置为 ，以便元素填充网页的宽度，并且当对于连续外观可见时，该元素将流动在 `100%` `div` 覆盖层下。  

```css
#titleBarContainer {
    position: absolute;
    top: env(titlebar-area-y, 0);
    bottom: env(titlebar-area-height, calc(100% - var(--fallback-title-bar-height)));
    width: 100%;
    background-color:#254B85;
}
```  

`titleBar`ID 还使用 `position: absolute` 和 `top: titlebar-area-inset-top` ，以将它附加到窗口顶部。  默认情况下，它使用窗口的完整宽度。  和 边缘分别设置为 和 ，两者在未 `left` `right` 设置值 `titlebar-area-inset-left` `titlebar-area-inset-right` `0` 时回退。  它还设置 `user-select: none` 阻止任何尝试拖动占用的窗口，而是突出显示元素中的 `div` 文本。  

```css
#titleBar {
    position: absolute;
    top: 0;
    display: flex;
    user-select: none;
    height: 100%;
    left: env(titlebar-area-x, 0);
    right: env(titlebar-area-width, 0);
    color: #FFFFFF;
    font-weight: bold;
    text-align: center;
}

#titleBar > span {
    margin: auto;
    padding: 0px 16px 0px 16px;
}

#titleBar > input {
    flex: 1;
    margin: 8px;
    border-radius: 5px;
    border: none;
    padding: 8px;
}
```

ID 的 `mainContent` 容器也与 固定在一起 `position: absolute` ，并附加到网页底部。  `height`设置为 并 `titlebar-area-inset-bottom` 回滚以填充 `100% - var(--fallback-titlebar-height)` 标题栏下方的剩余空间。  它 `overflow-y: scroll` 设置 允许内容在容器中垂直滚动。  

```css
#mainContent {
    position: absolute;
    left: 0;
    right: 0;
    bottom: 0;
    height: env(titlebar-area-height, calc(100% - var(--fallback-title-bar-height)));
    overflow-y: scroll;
}
```

对于浏览器不支持窗口控件覆盖的情况，添加 CSS 变量以设置标题栏的默认高度。  和 ID 的界限最初设置为填充整个客户端区域，如果覆盖层不受支持，则不需要 `titleBarContainer` `mainContent` 更改。  

以下代码段包括所有建议的 CSS 更新。

```css
:root {
  --fallback-title-bar-height: 40px;
}

.draggable {
  app-region: drag;
  /* Pre-fix app-region during standardization process */
  -webkit-app-region: drag;
}

.nonDraggable {
  app-region: no-drag;
  /* Pre-fix app-region during standardization process */
  -webkit-app-region: no-drag;
}

body {
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  margin: 0;
}

#titleBarContainer {
  position: absolute;
  top: env(titlebar-area-y, 0);
  bottom: env(titlebar-area-height, calc(100% - var(--fallback-title-bar-height)));
  width: 100%;
  background-color:#254B85;
}

#titleBar {
  position: absolute;
  top: 0;
  display: flex;
  user-select: none;
  height: 100%;
  left: env(titlebar-area-x, 0);
  right: env(titlebar-area-width, 0);
  color: #FFFFFF;
  font-weight: bold;
  text-align: center;
}

#titleBar > span {
  margin: auto;
  padding: 0px 16px 0px 16px;
}

#titleBar > input {
  flex: 1;
  margin: 8px;
  border-radius: 5px;
  border: none;
  padding: 8px;
}

#mainContent {
  position: absolute;
  left: 0;
  right: 0;
  bottom: 0;
  height: env(titlebar-area-height, calc(100% - var(--fallback-title-bar-height)));
  overflow-y: scroll;
}
```  

## <a name="run-on-os-login"></a>在操作系统登录时运行  

此功能允许你将应用配置为在用户登录到 Microsoft Windows。  多个应用类利用此功能。  应用类包括电子邮件、聊天、监视仪表板和实时数据显示应用。  该功能允许用户在用户登录到操作系统后尽快使用应用。  此功能将自动启动PWA启动方式与手动启动方式相同。  

> [!IMPORTANT]
> **在操作系统登录上运行** 是一 [项强大的功能][GithubW3cPermissionsPowerfulFeature]。  用户应决定是否为已安装的 Web 应用启用该功能。  

### <a name="turn-on-run-on-os-login"></a>打开"在操作系统登录时运行"  

若要预览适用于**** 你的用户的运行操作系统登录PWA，请导航到打开实验性功能，[](#turn-on-experimental-features)然后打开在操作系统登录上运行的桌面**PWA。**  

:::image type="complex" source="../media/desktop-pwas-run-on-os-login-flag.png" alt-text="打开在操作系统登录实验上运行的桌面 PBA" lightbox="../media/desktop-pwas-run-on-os-login-flag.png":::
   打开在**操作系统登录实验上运行的桌面 PBA**  
:::image-end:::  

### <a name="turn-on-the-feature-for-the-installed-web-app"></a>打开已安装的 Web 应用的功能  

若要为已安装 `Start app when you sign in` 的 PWA， 

1.  打开 Microsoft Edge。   
1.  导航到 `edge://apps`。  
1.  将鼠标悬停在你的应用上。  
1.  打开上下文菜单 \ (右键单击\) 然后在登录时选择 **"启动应用"。**  
    
    :::image type="complex" source="../media/turn-on-run-on-os-login-flag.png" alt-text="在应用中登录功能时，使用上下文菜单打开"开始"Microsoft Edge" lightbox="../media/turn-on-run-on-os-login-flag.png":::
       使用上下文菜单在用户登录**功能时打开"开始"Microsoft Edge**  
    :::image-end:::  
    
## <a name="shortcuts"></a>快捷方式  

`Shortcuts` 是清单文件的一个新增成员。  它允许你在 Web 应用中定义指向部件、关键网页或操作的链接。  Microsoft Windows将其集成为**Jumplists**。  **Jumplist 定义** 在下列 UI 元素之一上打开上下文菜单 \ (右键单击\) 时出现的弹出菜单。  

*   "开始"菜单上的磁贴  
*   任务栏上的图标  
    
当用户调用快捷方式时，用户将导航到该快捷方式的成员 `url` 指定的地址。  
  
:::image type="complex" source="../media/jumplists-on-windows-10.png" alt-text="Jumplists 示例Windows 10" lightbox="../media/jumplists-on-windows-10.png":::
   **Jumplists 示例Windows 10**  
:::image-end:::  

### <a name="shortcuts-in-the-manifest-file"></a>清单文件的快捷方式  

```json
"shortcuts" : [
  {
    "name": "Today's agenda",
    "url": "/today",
    "description": "List of events planned for today"
  },
  {
    "name": "New event",
    "url": "/create/event"
  },
  {
    "name": "New reminder",
    "url": "/create/reminder"
  }
]
```  

#### <a name="properties-of-shortcuts"></a>快捷方式的属性  

以下属性定义每个快捷方式。  

| 属性 | 详细信息 |  
|:--- |:--- |  
| `name` | 在跳转列表或上下文 **菜单上向** 用户显示的字符串。 |  
| `short_name` | 当空间不足，无法显示快捷方式的完整名称时显示的字符串。 |  
| `description` | 一个描述快捷方式用途的字符串。  它可能会由辅助技术访问。 |  
| `url` | 激活快捷方式时打开的 Web 应用中的 URI。 |  
| `icons` | 一组表示快捷方式的图标。 |  

## <a name="file-handling"></a>文件处理  

注册为文件类型处理程序的能力在试验阶段。  你可以指定应用在清单条目中处理的文件类型。  在安装过程中，用户的主机操作系统将你的应用注册为列出的文件类型的文件处理程序。  确保应用启动代码中存在此功能， `launchQueue` 并确保它处理文件。  

Chromium浏览器正在测试和塑造此功能。  有关详细信息（包括代码示例），请导航到["允许 Web 应用程序成为文件处理程序"。][WebDevFileHandling]  

若要预览 Microsoft Edge for Windows 10 中的文件处理，请导航到[](#turn-on-experimental-features)"打开实验性功能"，然后打开"文件**处理 API"。**  
    
## <a name="providing-feedback-on-experimental-features"></a>提供有关试验功能的反馈  

提供有关 Web Microsoft Edge实验的反馈。  

*   使用更多**\设置**\ (`...` \) > 将反馈发送给 Microsoft 发送**反馈**。  
*   选择 `Alt` + `Shift` + `I` 。  
    
:::image type="complex" source="../media/send-feedback-from-progressive-web-app.png" alt-text="从用户发送PWA" lightbox="../media/send-feedback-from-progressive-web-app.png":::
   从用户发送PWA  
:::image-end:::  

<!-- links -->  

[MicrosoftEdgeMain]: https://www.microsoft.com/edge "Microsoft Edge"  

[MicrosoftDeveloperMicrosoftEdgeOriginTrials]: https://developer.microsoft.com/microsoft-edge/origin-trials "源试用版|Microsoft Edge开发人员"  
[MicrosoftDeveloperMicrosoftEdgeOriginTrialsWebAppProtocolHandlerRegistrationRegistration]: https://developer.microsoft.com/microsoft-edge/origin-trials/web-app-protocol-handler-registration/registration "注册 Web 应用协议处理程序|Microsoft 开发人员"  

[MdnDocsWebApiNavigatorRegisterprotocolhandlerWebBasedProtocolHandlers]: https://developer.mozilla.org/docs/Web/API/Navigator/registerProtocolHandler/Web-based_protocol_handlers "基于 Web 的协议处理程序|MDN"  

[GithubW3cPermissionsPowerfulFeature]: https://w3c.github.io/permissions#powerful-feature "强大的功能 - 权限|GitHub"  

[GithubWicgPwaUrlHandlerBlobMainExplainerMd]: https://github.com/WICG/pwa-url-handler/blob/main/explainer.md "作为 URL 处理程序的 PWA |GitHub"  

[WebDevFileHandling]: https://web.dev/file-handling "让 Web 应用程序成为文件处理程序|web.dev"  
