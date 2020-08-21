---
description: 本指南概述了 EdgeHTML 15 中包括的开发人员功能和标准。
title: EdgeHTML 15 中的新功能和 API
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘， Web 开发， html， css， javascript， developer
ms.custom: seodec18
ms.openlocfilehash: 4febe4be1fce29207de7a57b61d96eae0a5c02ab
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "10941922"
---
# EdgeHTML 15 中的新增功能  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

截止到下面，截止到 [Windows 10 创意者](https://blogs.windows.com/buildingapps/2017/04/05/windows-10-creators-update-creators-update-sdk-released/#MMhK2OdcrR12Vi6u.97) 更新 \ (04/2017（内部版本 15063\) ），当前发布的 Microsoft Edge 平台随即发布的更改。  有关 Microsoft Edge 浏览器的整体更改的概述，请参阅 [Windows 10 创意者更新中 Microsoft Edge 中的新增功能](https://blogs.windows.com/msedgedev/2017/04/11)。  

有关随后的 Windows Insider Preview 版本中的更改，请参阅 [EdgeHTML 中的新增功能](../whats-new.md)。  

下面是下列更改列表的句号  [https://aka.ms/devguide_edgehtml_15](./edgehtml-15.md) ：。  

## 新增功能  

### CSS 自定义属性  

Microsoft Edge 现在支持 [CSS 自定义属性，即](https://drafts.csswg.org/css-variables)一个.k.a CSS 变量。  CSS 变量允许您创建自定义 CSS 属性，这些属性可在整个样式表中重复使用，以帮助减少重复数据量，如重复颜色。  使用 CSS 变量非常简单：  

```css
/* define a custom property by using two dashes and assign it a value */
body {   
   --default-color: #3390b1
}

/* reference it in your stylesheet with the "var()" function */
h1 {
   color: var(--default-color);
}
```  

### 交section Ob服务器  

EdgeHTML 15 引入了 [交集 Ob 服务器 API](https://w3c.github.io/IntersectionObserver) 规范。  利用交集 Observer API，你可以异步查询相对其他元素或全局视区的 DOM 元素的位置和可见性。  此 API 不需要通过创建一个高效地在视图中通知元素的方法，从而消除了自定义很高代码的需要。  

### JavaScript  

性能优化将使 EdgeHTML 15 复习 JavaScript 引子具有大概括视。这将使其占用大概括状态。  通过 Windows 10 创意者更新，Chakra 通过重新演示函数并优化堆参数来节省内存，并提高缩小代码的性能。  

此外，EdgeHTML 15 引入了以下功能预览：  

#### 实质 JavaScript 功能  

与 `about:flags`  

*   [WebAssembly](https://developer.microsoft.com/microsoft-edge/platform/status/webassemblymvp/?q=WebAssembly) \ ([demo](https://webassembly.org/demo)\)   
*   [共享内存和原子](https://developer.microsoft.com/microsoft-edge/platform/status/sharedmemoryandatomics/?q=Atomics)  

若要 [进一步细节，请参阅 Microsoft Edge 中改进的 JavaScript 性能、WebAssembly](https://blogs.windows.com/msedgedev/2017/04/20) 和共享内存。  

### 付款请求 API  

[现支持付款请求 API，](https://w3.org/TR/payment-request)从而在 Windows 10 电脑和手机上的 Web 上支持更加简单的结账和付款。  此 API 使 Microsoft Edge 能够成为商业、消费者和支付方式 \ (的用户存储在云中的中介方式。<)   有关付款请求 API 的详细信息，请查明较为简单的 [Web 付款：](https://blogs.windows.com/msedgedev/2016/12/15) 付款请求 API 和付 [款请求 API 开发](/microsoft-edge/dev-guide/device/payment-request-api) 人员指南。  

### TCP 快速打开 TCP (TFO)   
TCP 快速打开功能可减少打开 TCP 连接和提高浏览器网络性能所需的跨口行程的功能。  有关详细信息，请参阅"使用 [TCP](https://blogs.windows.com/msedgedev/2016/06/15)快速打开"更快、更安全的 Web。  由于各种网络拓扑的互操作性差异，Microsoft Edge 默认未启用此功能。  要启用此功能， `about:flags` 请在地址栏中键入，然后选中"启用 **TCP 快捷方式"的复选框，在"** 网络"部分下选择"启用 TCP 快速 **打开** "。  

### WebRTC 和可互操作的 RTC 视频编解码器支持  

EdgeHTML 15 支持 WebRTC 1.0 API 的子集，用于与使用早期版本 W3C WebRTC-PC API 线 2015 较早版本生成的应用程序进行互操作性。  有关详细信息， [请参阅 WebRTC API](/previous-versions//mt806139(v=vs.85)) 参考。  

为了利用对等音频和视频通信中最高级的功能，我们建议使用[API 实时通) API。](https://ortc.org)  ORTC API 更适合需要设置组音频和视频调用，或者直接控制各个传输、发送方和接收器对象。  

Microsoft Edge 支持具有 ORTC 和 WebRTC 1.0 的 H.264/AVC 和 VP8 视频，同时也支持以下两种支持以下功能[：abs-发送时](https://webrtc.org/experiments/rtp-hdrext/abs-send-time)[、Goog-Remb、Picture](https://tools.ietf.org/html/draft-alvestrand-rmcat-remb-03) [Loss 指示和一套 NACK 反转](https://tools.ietf.org/html/rfc4585)[;RTP 回转](https://tools.ietf.org/html/rfc4588)。  

有关详细信息，请参阅介绍 [Microsoft Edge 中的 WebRTC 1.0](https://blogs.windows.com/msedgedev/2017/01/31)和可互操作实时通信。  

### WebVR  

Microsoft Edge 现在支持 [WebVR，它](https://immersive-web.github.io/webxr)是一种可将 Windows Mixed Reality 头像建广的实例 API 连接到 Microsoft Edge。  此连接使 VR 内容能够在网站中体验，这意味着沉缩 VR 体验不再限于桌面应用程序。  

Microsoft Edge 中的虚拟现实由 WebGL 提供支持，这是一种用于呈现 3D 和 2D 图形的 JavaScript API。  支持使用 WebGL 库（如 BabylonJS）构建的 WebGL 应用程序和应用程序。  连接后，WebVR 将在耳机前发送与位置和传感器信息相对应的视觉对象。  与游戏板 API 的扩展，WebVR API 还支持单 [位控制器](../dom/gamepad-api.md)。  此 API 默认处于开机状态，因此无需切换标志。  

有关详细信息， [请参阅 WebVR API](/previous-versions//mt806281(v=vs.85)) [参考和游戏](https://developer.mozilla.org/docs/Web/API/Gamepad_API) 板 API 参考。  

 > [!NOTE] 
 > 由于 WebVR 规范仍在开发中，所以 Microsoft Edge 的实现可能会在以后更改。  

## 更新的功能  

### 内容安全策略 (2 级)   

已在使用 CSP 1 使用的网站可继续使用 CSP 2 的 Microsoft Edge 支持，但是最好将负载工作词转化为 `frame-src` 新的 `child-src` 指令，再以后校对您的网站校对。  \ (In CSP 3 `frame-src` 中，将不再适用于工作者.\) CSP 2 也添加以下内容：  

:::row:::
   :::column span="1":::
      新的指令  
   :::column-end:::
   :::column span="2":::
      `base-uri`、、 `child-src` `form-action` 和 `frame-ancestors` `plugin-types` .  有关详细信息 [，请参阅 Microsoft Edge 支持的 CSP 指](../security/content-security-policy.md) 令。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      Workers 支持  
   :::column-end:::
   :::column span="2":::
      后台工作者脚本受其自己的策略保护，独立于文档加载它们的策略。  与主机文档一然，你可以在响应头中为工作者设置 CSP。  此外，在 CSP 2 中新增了这一新增内容，指令的标志  `allow-scripts` `allow-same-origin` `sandbox` 现在会影响创建工作线程。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      嵌入脚本和样式  
   :::column-end:::
   :::column span="2":::
      CSP 2 允许通过将 nonce 和哈希作为白名机制提供来允许执行内联脚本和样式块。  Nonce 是在每个页面加载上生成的随机 base-64 值，该值同时出现在 CSP 策略和页面的脚本标记中。  当在加载时以动态方式生成页面时，服务器将生成一个 nonce 值，将其插入到页面的 NonceToken 中，并在内容安全策略 HTTP 标头中声明了该页面。  哈希 (是通过 sha256、sha384 或 sha512 算法\) 在 CSP 策略中通过 `<script>` `<style>` 或指令\) 指定 \ (指定的静态 `script-src` `style-src` 值。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      CSP 协议报告  
   :::column-end:::
   :::column span="2":::
      现在，在 `SecurityPolicyViolationEvent` CSP 值分音时引发新事件。  继续支持上述 CSP 报告的 `report-uri` 更早机制。  几个新字段已添加到两者通用报告中， `effectiveDirective` 包括 \ (的分布情况 ) 报告 \、\ (`statusCode` THE HTTP response code\) 、\ (`sourceFile` the offending resource\) ， `lineNumber` and `columnNumber` .  
   :::column-end:::
:::row-end:::  

### Web 身份验证  

已使用[Windows Hello](https://www.microsoft.com/windows/comprehensive-security)生物识别扩展[Web 身份验证 API](../device/web-authentication.md)的 Microsoft Edge 支持已进行了如下更改：  

*   在 EdgeHTML 14 \ (Windows 10 周年更新（版本 10240、7/2016\) 公开了 MS - 前缀 API \ ([MSCredentials](/previous-versions//mt697639(v=vs.85))接口\) 中引入的实际实现。 [EdgeHTML 14](https://blogs.windows.com/msedgedev/2016/08/04)  虽然这些 API 仍在 EdgeHTML 15 中可用，但这些 API 现已不支持以标准前缀的、基于标准的 API 和行为（ [以更加](https://w3.org/TR/2016/WD-webauthn-20160928) 高的规范的规范的形式定义）来弃用，并且可能随着标准化的规范的规格不断变化而继续更改。  

*   默认，最新的 Microsoft Edge 实现处于关闭状态，并以开启该功能\ (`about:flags` ) 。  

*   Microsoft Edge 尚不支持 USB 密钥或移动设备等外部 Bluetooth凭据。  当前 API 仅限于嵌入存储在 TPM 中的凭据。  如果 TPM 在设备上不可用，则使用软件回退。  

*   Windows 用户帐户必须配置为至少支持 PIN，最好是正面或指纹生物识别。  这是为了确保 Windows 可以对 TPM 的访问进行身份验证。  

*   在 [本机中描述的预](https://w3.org/TR/webauthn/#extension-predef) 定义扩展中，Microsoft Edge 此时仅支持 [FIDO AppId](https://w3.org/TR/webauthn/#extension-appid) \ (`webauthn_txAuthSimple` \) 。  

*  `timeoutSeconds`该选项当前未进行求值  

### WebDriver  

EdgeHTML 15 带来了少量 WebDriver 更新，包括对静色命令行标志和新命令终结点的支持：  

| 方法 | URI 模板 | 命令 |  
|:--- |:---  |:--- |    
| POST | /session/{session id}/alert/accept | [接受"接受的"](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-accept-alert) |  
| POST | /session/{session id}/alert/dismiss | [消除通知](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-dismiss-alert) |  
| GET | /session/{session id}/alert/text | [获取发件人文本](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-get-alert-text) |  
| POST | /session/{session id}/alert/text | [发送提示文本](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-send-alert-text) |  
| POST | /session/{session id}/execute/async | [执行异步脚本](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-execute-async-script) |  
| POST | /session/{session id}/execute/sync | [执行脚本](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-execute-script) |  
| GET | /session/{session id}/window | [获取窗口句柄](https://w3c.github.io/webdriver/webdriver-spec.html#get-window-handle) |  
| GET | /session/{session id}/window/handles | [获取 Window 句柄](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-get-window-handles) |  

有关详细信息和其他 WebDriver 功能的状态，请查看[WebDriver。](../../webdriver.md)  

## EdgeHTML 15 中的新 API  

下面是 EdgeHTML 15 中的新 API 的完整列表。  它们以格式列出 `[interface name].[api name]` 。  

<iframe height='582' scrolling='no' title='新版 EdgeHTML15 API' src='//codepen.io/MicrosoftEdgeDocumentation/embed/evRjjZ/?height=582&theme-id=23761&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>有关 <a href='http://codepen.io/MicrosoftEdgeDocumentation/pen/evRjjZ/'> 在 CodePen 上使用 Microsoft Edge 的文档和 </a> Microsoft Edge <a href='http://codepen.io/MicrosoftEdgeDocumentation'> (@MicrosoftEdgeDocumentation) 笔新 EdgeHTML15 </a> <a href='http://codepen.io'> </a> API。</iframe>  

## 以前的 EdgeHTML 版本  

[EdgeHTML 12 / Windows 内部版本 10240 (7/2015) ](./edgehtml-12.md)  

[EdgeHTML 13 / Windows 版本 10586 (11/2015 版) ](./edgehtml-13.md)  

[EdgeHTML 14/Windows 内部版本 14393 (，8) ](./edgehtml-14.md)  
