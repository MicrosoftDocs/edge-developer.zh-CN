---
description: Microsoft Edge for Web Apps 中的最新实验功能
title: 实验功能|渐进式 Web 应用
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/02/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， 实验， 渐进式 Web 应用， Web 应用， PWA， PWA
ms.openlocfilehash: 587797bc8577f1c1aaca42394eecb997d21e9955
ms.sourcegitcommit: f605e4e27fed88aca286f2ae236e27f9a396b517
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "11474954"
---
# <a name="experimental-features-in-progressive-web-apps-pwas"></a>渐进式 Web 应用和 PBA (实验)   

Microsoft Edge 提供对仍在开发中的实验性功能的访问权限。  若要确定每个功能是否就绪以及何时发布每个功能，请进行测试 [并提供反馈](#providing-feedback-on-experimental-features)。  

实验功能在 Microsoft Edge 的所有渠道中均可用，但最新的实验功能仅在 Microsoft Edge Canary 渠道中可用。  

## <a name="turn-on-experimental-features"></a>打开试验功能  

若要在 Microsoft Edge 中打开\（或关闭\）试验功能，请完成以下步骤。  
  
1.  打开 Microsoft Edge。   
    
    > [!NOTE]
    > 确保使用本文中列出的实验的 Microsoft Edge 版本。  导航到 [实验功能](#features-that-are-available-to-test)。  
    
1.  导航到 `edge://flags` 。  
1.  导航到相关实验。  
1.  选择实验说明旁边的下拉菜单并选择 `Enabled` 。  
    
    :::image type="complex" source="../media/turn-on-experimental-flag.png" alt-text="选择启用以打开实验" lightbox="../media/turn-on-experimental-flag.png":::
       选择 **启用** 以打开实验  
    :::image-end:::  
    
    > [!NOTE]
    > 每个实验通常都有一个下拉菜单来选择以下值。  如果实验功能在实验上没有条目，则提供**** 说明以使用命令行使用该功能启动 Microsoft Edge。
    > 
    > *   `Default`  
    > *   `Disabled`  
    > *   `Enabled`  
    
1.  重启 Microsoft Edge。  
    
### <a name="origin-trials"></a>原始试验  

Microsoft Edge 有时使用源试用版来测试特定域或网站的功能。  你可能想要对网站使用源试用版来应用特定功能。  如果你是网站所有者，你可以注册源试用版。  源试用版向访问你的网站的 Microsoft Edge 用户提供一定比例的功能。

有关源试用版详细信息，请导航到 [Microsoft Edge Origin Trials 开发人员控制台][MicrosoftDeveloperMicrosoftEdgeOriginTrials]。  
    
> [!NOTE]
> 实验性功能会不断更新，并且可能会导致性能问题。  若要关闭实验功能，请导航到打开 [实验](#turn-on-experimental-features)功能，导航到实验，然后选择 `Disabled` 。  

## <a name="features-that-are-available-to-test"></a>可供测试的功能  

以下列表介绍了可在 Microsoft Edge 上测试和验证的新实验性 Web 应用功能。  

| 功能 | Microsoft Edge 版本 | 平台 |  
|:--- |:--- |:--- |  
| [URI 协议处理](#uri-protocol-handling) | 91 或更高版本 | Windows |    
| [URL 链接处理](#url-link-handling) | 91 或更高版本 | Windows|  
| [在操作系统登录时运行](#run-on-os-login) | 88 或更高版本 | 全部 |  
| [快捷方式](#shortcuts) | 87 或更高版本 | 全部 |  
| [文件处理](#file-handling) | 83 或更高版本 | 所有桌面 |  


## <a name="uri-protocol-handling"></a>URI 协议处理  

统一资源标识符 \ (URI\) 可用于定义使用 HTTP 或 FTP 协议的网页和 Web 内容的链接。  URI 可用于描述指向您编成架构中任何内容的链接。  例如，协议用于描述电子邮件链接，操作系统 `mailto://` \ (OS\) 或浏览器决定哪个网页或应用应处理该协议。  

有关基于浏览器的现有支持，请导航到基于 [Web 的协议处理程序][MdnDocsWebApiNavigatorRegisterprotocolhandlerWebBasedProtocolHandlers]。  

此功能允许您完成以下操作。  

*   使用 Web 应用程序的清单向主机操作系统注册 PWA
*   声明 PWA 处理特定 URI 协议  
     
将 PWA 注册为协议处理程序后，当用户选择具有特定方案（如浏览器或本机应用）的超链接时，已注册的 PWA 由操作系统激活并接收 `mailto://` `web+music://` URI。  

此功能要求你更新 Web 应用清单以在需要指定两个字段的 `protocol_handlers` 数组中包括数组：  

*   `protocol`：用于处理请求的协议，例如 或 `mailto` `web+jngl` 。  
*   `url`：处理协议的应用作用域中的 HTTPS URI。  将来，计划替换以协议处理程序方案开始的 `%s` URI。  
    
更新清单以支持要注册的协议。  启用此功能后，Microsoft Edge 将完成以下操作。  

1.  检测清单中的更改  
1.  为协议注册应用  
    
如果多个应用注册协议，则向用户显示提示。  用户从操作系统或浏览器呈现的列表中选择相应的应用。  

若要在 Windows 上的 Microsoft Edge 中[](#turn-on-experimental-features)预览协议处理，请导航到打开实验性功能，然后打开**桌面 Web 应用支持协议处理程序**。  

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

统一资源定位器 \ (URL\) 是一种 URI。  当渐进 Web 应用 \ (PWA\) 注册为 https URI 的处理程序时，创建更具吸引力的体验。  PBA 可能会请求在激活关联的 URI 时启动。  例如，如果用户从电子邮件中选择指向新闻文章的链接。  用于显示新闻文章的关联 PWA 将自动启动以处理链接的激活。  

此功能允许您使用 Web 应用程序清单向浏览器注册 PWA，并声明浏览器处理特定链接。  若要在浏览器中注册 PWA，请向清单 `url_handlers` 文件添加可选成员。  `url_handlers`成员是 `object[]` 一个 ，用于对应用希望处理的 URI 的来源进行分组。  

浏览器使用位于源上的 `web-app-origin-association` JSON 文件验证链接处理。  源文件进一步微调源的包含路径或排除路径。  有关测试 URL 处理程序的详细说明，请导航到[作为 URL 处理程序的 PWA。][GithubWicgPwaUrlHandlerBlobMainExplainerMd]  

若要在 Windows 上的 Microsoft Edge 中预览 URL 链接处理，请导航到"[打开](#turn-on-experimental-features)实验性功能"，然后打开"**桌面 PWA URL 处理"。**  

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

如果 URI 与 中的一个源字符串匹配，并且浏览器验证源是否同意允许此应用程序处理此类 URI，PWA 将匹配用于 URL 处理的 `url_handlers` URI。  

成员包含一个源，该源包含请求的 PWA 的范围和其他 `url_handlers` 不相关的源。  不将 URI 限制为与请求的 PWA 相同的范围或域，允许您对相同内容使用不同的域名，但使用相同的 PWA 处理它们。  

#### <a name="wildcard-matching"></a>通配符匹配  

使用通配符 \ (`*` \) 匹配一个或多个字符。  

通配符前缀用于成员的来源字符串中 `url_handlers` ，以匹配不同的子域。  前缀必须针对 `*.` 此用法。  使用 `https` 通配符前缀时将假定此方案。  

例如， `url_handlers` 成员值设置为 `*.contoso.com` matches 和 `tenant.contoso.com` `www.tenant.contoso.com` ，但不匹配 `contoso.com` 。  

<!-- Hold for future release -->  
<!--  ## Window Controls Overlay for installed desktop web apps  

To create an immersive title bar similar to a native app for your desktop installed web app.  The **Window Controls Overlay** feature  completes the following actions.  
    
1.  Removes the system reserved title bar.  It usually spans the width of the client frame.  
1.  Replaces it with an overlay.  It contains just the critical system required window controls necessary for a user to control the window itself.  
    
After it provides an overlay, the entire web client area is available for you to use.  This feature includes a manifest update.  It provides ways for you to determine the size and position of the overlay to help you arrange content.  
    
### Examples of title bar area customization  

This feature is based on the ability in native apps to customize the title bar.  You may customize a title bar for important app actions or notifications.  Review the following examples for Microsoft Visual Studio Code and Microsoft Teams.  

#### Visual Studio Code  

Microsoft Visual Studio Code is a popular editor built on Electron that ships on multiple desktop platforms.  

The following example displays how Visual Studio Code uses the title bar to maximize available screen real estate to include the current file name and top-level menu structure in the title bar.  

:::image type="complex" source="../media/visual-studio-code-title-customization.png" alt-text="An example of the title bar in Visual Studio Code" lightbox="../media/visual-studio-code-title-customization.png":::
   An example of the title bar in Visual Studio Code  
:::image-end:::  

#### Microsoft Teams  

Workplace collaboration and communication tool Microsoft Teams is also built with Electron and available on multiple desktop platforms.  In the following example, Microsoft Teams displays `back` and `forward` navigation buttons, a search box, and user profile controls.  

:::image type="complex" source="../media/teams-title-customization.png" alt-text="An example of the title bar in Microsoft Teams" lightbox="../media/teams-title-customization.png":::
   An example of the title bar in Microsoft Teams  
:::image-end:::  

### Overlay Window Controls on a Frameless Window  

To provide the maximum addressable area for web content, the browser creates a frameless window, removing all browser UI except for the window controls provided as an overlay.  
The window controls overlay ensures users still minimize, maximize, restore, and close the app.  It also provides access to relevant browser controls using the web app menu.  For Chromium-based browsers, the controls in the overlay.

*   A draggable region the same width and height of each of the window control buttons  
*   The **Settings and more** \(...\) button  
*   The window control buttons minimize, maximize, restore, and close  
    
The following scenarios include when browser displays other content in the controls overlay.  

*   When an installed web app is launched, the origin of the webpage displays to the left of the **Settings and more** \(...\) menu for a few seconds and then disappears.  
*   If a user interacts with an extension using the **Settings and more** \(...\) menu, the icon of the extension displays in the overlay to the left of the three-dot menu.  After you exit any extension dialog, the icon is removed from the overlay.  
    
| Language direction | Overlay location | Details |  
|:--- |:--- |:--- |  
| Left-to-right \(LTR\) | Upper left of the client area | The controls are flipped |  
| Right-to-left \(RTL\) | Upper right corner of the client area |  |  

>[!IMPORTANT]
> The overlay is always on top of the Z-index of the web content and accepts all user input without flowing it through to the web content.  

### Working around the Window Controls Overlay  

Your web content must be aware of the reserved area for the controls overlay.  Ensure the reserved area doesn't expect user interaction.  Query the browser for the bounding rectangle and visibility of the controls overlay.  The information is provided to you through JavaScript APIs and CSS environment variables.  

#### JavaScript APIs  

A new `windowControlsOverlay` object on the `window.navigator` property allows you to query the bounding rectangle of the controls overlay.  

The `windowControlsOverlay` object has the following two objects.  

*   `getBoundingClientRect()` returns a `DOMRect` object.  The `DOMRect` object represents the area under the window controls overlay.  
*   `visible` is a boolean that indicates that the controls overlay is rendered and displayed.  
    
> [!IMPORTANT]
> For privacy reasons, the `windowControlsOverlay` isn't accessible to `iframe` elements in the web content.  

Whenever the overlay is resized, a `geometrychange` event runs on the `navigator.windowControlsOverlay` object to notify the client to recalculate the content layout.  The recalculated content layout is based on the new bounding rectangle of the overlay.  

#### CSS Environment Variables  

Besides the JavaScript API, you may use CSS to query the bounding rectangle of the controls overlay.  Use the following four new CSS environment variables to accomplish to query.  

*   `titlebar-area-x`  
*   `titlebar-area-y`  
*   `titlebar-area-width`  
*   `titlebar-area-height`  
    
### Define Draggable Regions in Web Content  

Users expect to grab and drag the upper region of a window.  To accommodate the expectation, declare specific parts of the web content as draggable.  
To specify an element is draggable, use the webkit proprietary `-webkit-app-region` CSS property.  The CSS working group continues efforts to standardize the `app-region` property.  

To preview this feature in Microsoft Edge for desktop OSs, navigate to [Turn on experimental features](#turn-on-experimental-features) and navigate to **Desktop PWA Window Controls Overlay**.   

### Custom title bar example  

The following example displays how the new features create a web app with a custom title bar.  

:::image type="complex" source="../media/teams-title-customization-example.png" alt-text="Example of a custom title bar in Microsoft Teams" lightbox="../media/teams-title-customization-example.png":::
   Example of a custom title bar in Microsoft Teams  
:::image-end:::  

#### manifest.webmanifest  

In the manifest, set `display_override` array to  `window-controls-overlay`.  Set the `theme_color` to your choice of color for the title bar.  Set the display mode to an appropriate fallback for when either `display_override` or `window-controls-overlay` isn't supported.  

The following code snippet includes the recommended manifest updates.  

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

### index.html  

The following IDs represent the two main regions of the webpage.  

*   `titleBarContainer`  
*   `mainContent`  
    
The `div` element with the `titleBar` ID is set to `draggable` and the search box `input` child element is set to `nonDraggable`.  

```html
<div id="titleBar" class=" draggable">
    <span class="draggable">Example PWA</span>
    <input class="nonDraggable" type="text" placeholder="Search"></input>
</div>
```

In the `div` element with the `titleBarContainer` ID, the `div` with the `titleBar` ID represents the visible portion of the title bar area.  

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
    <div id="mainContent">The rest of the webpage</div>
  </body>
</html>
```  

### style.css  

The draggable and non-draggable regions are set using `-webkit-app-region: drag` and `-webkit-app-region: no-drag`.  

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

For the `body` element, margins are set to `0` to ensure the title bar reaches to the edges of the window.  

```css
body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    margin: 0;
}
```  

The `titleBarContainer` ID uses `position: absolute` and sets the `top` to `titlebar-area-inset-top`, which attaches the container to the top of the webpage.  The `bottom` is set to `titlebar-area-inset-bottom` and falls back to `100% - var(--fallback-title-bar-height)` if the window controls overlay isn't visible.  The background color of the `titleBarContainer` ID is the same as the `theme_color`.  The width is set to `100%`, so that the `div` element fills the width of the webpage and flows under the overlay when it's visible for a contiguous appearance.  

```css
#titleBarContainer {
    position: absolute;
    top: env(titlebar-area-y, 0);
    bottom: env(titlebar-area-height, calc(100% - var(--fallback-title-bar-height)));
    width: 100%;
    background-color:#254B85;
}
```  

The `titleBar` ID also uses `position: absolute` and `top: titlebar-area-inset-top` to attaches it to the top of the window.  By default, it consumes the full width of the window.  The `left` and `right` edges are set to `titlebar-area-inset-left` and `titlebar-area-inset-right` respectively, both fall back to `0` when the values aren't set.  It also sets `user-select: none` to prevent any attempts to drag the window consumed instead it highlights text in the `div` element.  

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

The container for the `mainContent` ID is also fixed in place with `position: absolute` and is attached to the bottom of the webpage.  The `height` is set to `titlebar-area-inset-bottom` and falls back to `100% - var(--fallback-titlebar-height)` to fill the remaining space below the title bar.  It sets `overflow-y: scroll` to allow the contents to scroll vertically in the container.  

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

For cases where the browser doesn't support the window controls overlay, a CSS variable is added to set a default height for the title bar.  The bounds of the `titleBarContainer` and `mainContent` IDs are initially set to fill the entire client area, and you don't need to change it if the overlay isn't supported.  

The following code snippet includes all of the recommended css updates.

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
-->  

## <a name="run-on-os-login"></a>在操作系统登录时运行  

此功能允许你将应用配置为在用户登录 Microsoft Windows 时自动启动。  多个应用类利用此功能。  应用类包括电子邮件、聊天、监视仪表板和实时数据显示应用。  该功能允许用户在用户登录到操作系统后尽快使用应用。  此功能自动启动 PWA 的方式与手动启动 PWA 的方式相同。  

> [!IMPORTANT]
> **在操作系统登录上运行** 是一 [项强大的功能][GithubW3cPermissionsPowerfulFeature]。  用户应决定是否为已安装的 Web 应用启用该功能。  

### <a name="turn-on-run-on-os-login"></a>打开"在操作系统登录时运行"  

若要为 PWA 启用 **"在操作系统**登录时运行"功能，[](#turn-on-experimental-features)请导航到"打开实验性功能"，然后打开"在操作系统登录时**运行桌面 PWA"。**  

:::image type="complex" source="../media/desktop-pwas-run-on-os-login-flag.png" alt-text="打开在操作系统登录实验上运行的桌面 PBA" lightbox="../media/desktop-pwas-run-on-os-login-flag.png":::
   打开在**操作系统登录实验上运行的桌面 PBA**  
:::image-end:::  

### <a name="turn-on-the-feature-for-the-installed-web-app"></a>打开已安装的 Web 应用的功能  

若要为已安装 `Start app when you sign in` 的 PWA 启用该功能， 

1.  打开 Microsoft Edge。   
1.  导航到 `edge://apps` 。  
1.  将鼠标悬停在你的应用上。  
1.  打开上下文菜单 \ (右键单击\) 然后在登录时选择 **"启动应用"。**  
    
    :::image type="complex" source="../media/turn-on-run-on-os-login-flag.png" alt-text="在 Microsoft Edge 中登录功能时，使用上下文菜单打开"开始"应用" lightbox="../media/turn-on-run-on-os-login-flag.png":::
       在 Microsoft Edge 中登录功能时 **，** 使用上下文菜单打开"开始"应用  
    :::image-end:::  
    
## <a name="shortcuts"></a>快捷方式  

`Shortcuts` 是清单文件的一个新增成员。  它允许你在 Web 应用中定义指向部件、关键网页或操作的链接。  Microsoft Windows 将其集成为 **Jumplists**。  **Jumplist 定义** 在下列 UI 元素之一上打开上下文菜单 \ (右键单击\) 时出现的弹出菜单。  

*   "开始"菜单上的磁贴  
*   任务栏上的图标  
    
当用户调用快捷方式时，用户将导航到该快捷方式的成员 `url` 指定的地址。  
  
:::image type="complex" source="../media/jumplists-on-windows-10.png" alt-text="Windows 10 上的 Jumplist 示例" lightbox="../media/jumplists-on-windows-10.png":::
   Windows 10 **上的 Jumplist** 示例  
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

基于 Chromium 的浏览器正在测试和塑造此功能。  有关详细信息（包括代码示例），请导航到["允许 Web 应用程序成为文件处理程序"。][WebDevFileHandling]  

若要预览适用于桌面 OS 的 Microsoft Edge 中的文件处理，请导航到打开实验[性](#turn-on-experimental-features)功能，然后打开文件**处理 API。**  
    
## <a name="providing-feedback-on-experimental-features"></a>提供有关试验功能的反馈  

提供有关 Microsoft Edge Web 应用实验的反馈。  

*   使用 **设置和更多** \ (`...` \) > 将反馈发送到 Microsoft **发送反馈**。  
*   选择 `Alt` + `Shift` + `I` 。  
    
:::image type="complex" source="../media/send-feedback-from-progressive-web-app.png" alt-text="从 PWA 发送反馈" lightbox="../media/send-feedback-from-progressive-web-app.png":::
   从 PWA 发送反馈  
:::image-end:::  

<!-- links -->  

[MicrosoftEdgeMain]: https://www.microsoft.com/edge "Microsoft Edge"  

[MicrosoftDeveloperMicrosoftEdgeOriginTrials]: https://developer.microsoft.com/microsoft-edge/origin-trials "源试用版|Microsoft Edge 开发人员"  
[MicrosoftDeveloperMicrosoftEdgeOriginTrialsWebAppProtocolHandlerRegistrationRegistration]: https://developer.microsoft.com/microsoft-edge/origin-trials/web-app-protocol-handler-registration/registration "注册 Web 应用协议处理程序|Microsoft 开发人员"  

[MdnDocsWebApiNavigatorRegisterprotocolhandlerWebBasedProtocolHandlers]: https://developer.mozilla.org/docs/Web/API/Navigator/registerProtocolHandler/Web-based_protocol_handlers "基于 Web 的协议处理程序|MDN"  

[GithubW3cPermissionsPowerfulFeature]: https://w3c.github.io/permissions#powerful-feature "强大的功能 - 权限|GitHub"  

[GithubWicgPwaUrlHandlerBlobMainExplainerMd]: https://github.com/WICG/pwa-url-handler/blob/main/explainer.md "作为 URL 处理程序的 PWA |GitHub"  

[WebDevFileHandling]: https://web.dev/file-handling "让 Web 应用程序成为文件处理程序|web.dev"  
