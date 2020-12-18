---
description: 本指南概述了 EdgeHTML 15 中包含的开发人员功能和标准。
title: EdgeHTML 15 中的新功能和 API
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge， Web 开发， html， css， javascript， 开发人员
ms.custom: seodec18
ms.date: 12/02/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 126fbc5f2a077052654063237c669089a3376ab0
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232679"
---
# EdgeHTML 15 中的新增功能  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

下面是 Microsoft Edge 平台当前版本附带的更改，自 [Windows 10](https://blogs.windows.com/buildingapps/2017/04/05/windows-10-creators-update-creators-update-sdk-released/#MMhK2OdcrR12Vi6u.97) 创意者更新 \ (04/2017 内部版本 15063\) 起。  有关整个 Microsoft Edge 浏览器更改的概述，请参阅 [Windows 10](https://blogs.windows.com/msedgedev/2017/04/11)创意者更新中的 Microsoft Edge 的新增功能。  

有关后续 Windows Insider Preview 内部版本的变化，请参阅 [EdgeHTML 中的新增功能](../whats-new.md)。  

下面是以下更改列表的 permalink： [https://aka.ms/devguide_edgehtml_15](./edgehtml-15.md)  

## 新功能  

### CSS 自定义属性  

Microsoft Edge 现在支持 [CSS 自定义属性](https://drafts.csswg.org/css-variables)（即 CSS 变量）。  CSS 变量允许您创建自定义 CSS 属性，这些属性可在样式表内重复使用，以帮助减少重复数据量，如重复颜色。  使用 CSS 变量非常简单：  

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

### 交集者  

EdgeHTML 15 引入了 [交集器 API](https://w3c.github.io/IntersectionObserver) 规范。  交集 Api 允许你异步查询 DOM 元素相对于其他元素或全局视口的位置和可见性。  此 API 通过创建在元素查看时有效通知元素的方法，无需自定义昂贵的代码。  

### JavaScript  

性能优化在 EdgeHTML 15 修订版的 Chakra JavaScript 引擎中处于中心阶段。  借助 Windows 10 创意者更新，Chakra 通过重新延迟函数并优化堆参数来节省内存，并改进缩小代码的性能。  

此外，EdgeHTML 15 还引入了以下功能预览：  

#### 实验 JavaScript 功能  

已启用 `about:flags`  

*   [WebAssembly](https://developer.microsoft.com/microsoft-edge/platform/status/webassemblymvp/?q=WebAssembly) \ ([demo](https://webassembly.org/demo)\)   
*   [共享内存和原子](https://developer.microsoft.com/microsoft-edge/platform/status/sharedmemoryandatomics/?q=Atomics)  

有关更多详细信息，请参阅 Microsoft Edge 中改进的 [JavaScript 性能、WebAssembly](https://blogs.windows.com/msedgedev/2017/04/20) 和共享内存。  

### 付款请求 API  

现在 [支持付款请求 API，](https://w3.org/TR/payment-request) 从而在 Windows 10 电脑和手机上实现更简单的 Web 结帐和付款。  此 API 使 Microsoft Edge 能够充当商家、消费者以及消费者存储在云中的付款方式 \ (（如信用卡\) ）之间的中介。  有关付款请求 API 详细信息，请查看"更简单 [的 Web](https://blogs.windows.com/msedgedev/2016/12/15) 付款：付款请求 API 介绍"和" [付款请求 API](/microsoft-edge/dev-guide/device/payment-request-api) 开发人员指南"。  

### TCP 快速打开 (TFO)   
TCP 快速打开是一项功能，可以减少打开 TCP 连接所需的往返次数，从而提高浏览器网络性能。  有关详细信息，请参阅使用 TCP 快速打开构建更快[、更安全的 Web。](https://blogs.windows.com/msedgedev/2016/06/15)  由于各种网络拓扑的互操作性差异，默认情况下，Microsoft Edge 中不启用此功能。  若要启用它，请在地址栏中键入，然后选中"网络"部分下的"启用 `about:flags` **TCP 快速** 打开 **"** 复选框。  

### WebRTC 和可互操作 RTC 视频编解码器支持  

EdgeHTML 15 支持 WebRTC 1.0 API 的子集，用于与使用 W3C WebRTC-PC API（大约 2015 年）的早期版本构建的应用程序进行互操作。  有关详细信息， [请参阅 WebRTC API](/previous-versions//mt806139(v=vs.85)) 参考。  

若要利用对等音频和视频通信中的最高级功能，我们建议使用[Object Real-Time Communication) API。](https://ortc.org)  ORTC API 更适用于要设置组音频和视频呼叫或直接控制单个传输、发件人和接收器对象的情况。  

Microsoft Edge 支持带有 ORTC 和 WebRTC 1.0 的 H.264/AVC 和 VP8 视频，并提供以下功能来支持这两种编解码器类型：abs-send-time、goog-remb、Picture [Loss Indication 和 Generic NACK feedback](https://tools.ietf.org/html/rfc4585)， [](https://webrtc.org/experiments/rtp-hdrext/abs-send-time) [RTP Retransmission。](https://tools.ietf.org/html/rfc4588) [](https://tools.ietf.org/html/draft-alvestrand-rmcat-remb-03)  

有关详细信息，请参阅 [Microsoft Edge 中的 WebRTC 1.0](https://blogs.windows.com/msedgedev/2017/01/31)简介和可互操作实时通信。  

### WebVR  

Microsoft Edge 现在支持 [WebVR，](https://immersive-web.github.io/webxr)这是一个实验性 API，用于连接 Windows Mixed Reality 头安装显示器和 Microsoft Edge。  此连接使 WEB 内容能够在网站中体验，这意味着沉浸式VR 体验不再局限于桌面应用程序。  

Microsoft Edge 中的虚拟网络由 WebGL（用于呈现 3D 和 2D 图形的 JavaScript API）提供支持。  支持使用 WebGL 库（如 BabylonJS）构建的 WebGL 应用程序和应用程序。  连接后，WebVR 将发送与耳机周围的位置和传感器信息相对应的视觉对象。  由于对游戏板 API 的扩展，WebVR API 还支持 **空间控制器**。  此 API 默认处于打开状态，因此无需切换标志。  

<!--  Virtual reality in Microsoft Edge is powered by WebGL, a JavaScript API for rendering 3D and 2D graphics.  WebGL applications and applications built with WebGL libraries like BabylonJS are supported.  Once connected, WebVR sends visuals corresponding to the position and sensor information around the headset.  The WebVR API also supports spatial controllers thanks to an extension to the [Gamepad API](../dom/gamepad-api.md).  This API is on by default, so no need to toggle a flag.  -->  

有关详细信息，[请参阅 WebVR API 参考](/previous-versions/mt806281(v=vs.85))[和游戏板 API](https://developer.mozilla.org/docs/Web/API/Gamepad_API)参考。  

 > [!NOTE] 
 > 由于 WebVR 规范仍处于开发阶段，因此 Microsoft Edge 的实现可能会稍后发生变化。  

## 更新的功能  

### 内容安全策略 (级别 2)   

已使用云解决方案提供商 1 的网站应继续使用 Microsoft Edge 对 CSP 2 的支持，但最好将加载工作脚本的任何指令切换到新指令，以面向未来的 `frame-src` `child-src` 站点。  \ (在 CSP 3 中，将不再适用于工作者 `frame-src` 。\) CSP 2 还添加了以下内容：  

:::row:::
   :::column span="1":::
      新指令  
   :::column-end:::
   :::column span="2":::
      `base-uri``child-src`、、 `form-action` `frame-ancestors` 和 `plugin-types` 。  <!--  See [Microsoft Edge supported CSP directives](../security/content-security-policy.md) for more.  -->  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      工作人员支持  
   :::column-end:::
   :::column span="2":::
      后台工作线程脚本由其自己的策略管理，独立于加载它们的文档策略。  与主机文档一样，您可以在响应标头中为工作者设置 CSP。  CSP 2 中的新增功能是，指令 `allow-scripts` `allow-same-origin` `sandbox` 的标志现在会影响工作线程创建。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      内联脚本和样式  
   :::column-end:::
   :::column span="2":::
      CSP 2 通过提供非索引和哈希作为允许列表机制，允许执行内联脚本和样式块。  Nonces 是在云解决方案提供商策略和页面脚本标记中显示的每个页面加载上生成的随机基 64 值。  加载时动态生成页面时，服务器将生成 nonce 值，将其插入到页面中的 NonceToken 中，并声明它在内容安全策略 HTTP 标头中。  哈希是使用 sha256、sha384 或 sha512 算法\) 从随后使用 CSP 策略中的 or 指令\ (指定 \ (的内容生成的 `<script>` `<style>` 静态值 `script-src` `style-src` \) 。 (  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      云解决方案提供商违反报告  
   :::column-end:::
   :::column span="2":::
      新的事件， `SecurityPolicyViolationEvent` 现在在 CSP 冲突时触发。  云解决方案提供商报告早期 `report-uri` 机制继续受支持。  向这两者通用的冲突报告中添加了几个新字段，包括 `effectiveDirective` \ (违反的策略\) 、\ (HTTP 响应代码 `statusCode` \) 、\ (违反资源的 `sourceFile` URL\) `lineNumber` 和 `columnNumber` 。  
   :::column-end:::
:::row-end:::  

### Web 身份验证  

通过以下更改更新了对使用[Windows Hello](https://www.microsoft.com/windows/comprehensive-security)生物识别的新兴 Web 身份验证**API**的 Microsoft Edge 支持：  

<!--  Microsoft Edge support for the emerging [Web Authentication API](../device/web-authentication.md) using [Windows Hello](https://www.microsoft.com/windows/comprehensive-security) biometrics has been updated with the following changes:  -->  

*   [EdgeHTML 14](https://blogs.windows.com/msedgedev/2016/08/04) \ (Windows 10 周年更新版本 10240，7/2016\) 中引入的实验性 Web 身份验证 API 的初始实现通过 MS 前缀 API \ ([MSCredentials](/previous-versions/mt697639(v=vs.85))接口\) 公开。  虽然这些 API 在 EdgeHTML 15 中仍然可用，但现在已弃用它们，以支持在规范的最近快照中定义的无前缀、基于标准的 API[](https://w3.org/TR/2016/WD-webauthn-20160928)和行为，并且可能会随着规范逐渐向标准化的方向发展而继续更改。  

*   默认情况下，最新的 Microsoft Edge 实现处于关闭状态，并附带在地址栏中 (标记 `about:flags` \) 。  

*   Microsoft Edge 尚不支持外部凭据，如 U 盘或Bluetooth设备。  当前 API 仅限于 TPM 中存储的嵌入凭据。  如果 TPM 在设备上不可用，则使用软件回退。  

*   当前登录的 Windows 用户帐户必须配置为支持至少一个 PIN，最好是人脸或指纹生物识别。  这是为了确保 Windows 可以验证对 TPM 的访问。  

*   在规范 [中描述的](https://w3.org/TR/webauthn/#extension-predef) 预定义扩展中，Microsoft Edge 目前仅支持 [FIDO AppId](https://w3.org/TR/webauthn/#extension-appid) \ (`webauthn_txAuthSimple` \) 。  

*  `timeoutSeconds`当前未评估该选项  

### WebDriver  

EdgeHTML 15 带来了一些 WebDriver 更新，包括对无提示命令行标志和新命令终结点的支持：  

| 方法 | URI 模板 | 命令 |  
|:--- |:---  |:--- |    
| POST | /session/{session id}/alert/accept | [接受警报](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-accept-alert) |  
| POST | /session/{session id}/alert/dismiss | [消除警报](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-dismiss-alert) |  
| GET | /session/{session id}/alert/text | [获取警报文本](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-get-alert-text) |  
| POST | /session/{session id}/alert/text | [发送通知文本](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-send-alert-text) |  
| POST | /session/{session id}/execute/async | [执行异步脚本](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-execute-async-script) |  
| POST | /session/{session id}/execute/sync | [执行脚本](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-execute-script) |  
| GET | /session/{session id}/window | [获取窗口句柄](https://w3c.github.io/webdriver/webdriver-spec.html#get-window-handle) |  
| GET | /session/{session id}/window/handles | [获取窗口句柄](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-get-window-handles) |  

有关详细信息和其他 WebDriver 功能的状态，请查看[WebDriver。](../../webdriver/index.md)  

## EdgeHTML 15 中的新 API  

以下是 EdgeHTML 15 中新 API 的完整列表。  它们以 . `[interface name].[api name]`  

<iframe height='582' scrolling='no' title='新的 EdgeHTML15 API' src='//codepen.io/MicrosoftEdgeDocumentation/embed/evRjjZ/?height=582&theme-id=23761&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>请参阅 Microsoft Edge 文档在 <a href='http://codepen.io/MicrosoftEdgeDocumentation/pen/evRjjZ/'> CodePen 上 (@MicrosoftEdgeDocumentation) </a> <a href='http://codepen.io/MicrosoftEdgeDocumentation'> </a> <a href='http://codepen.io'> EdgeHTML15 </a> API。</iframe>  

## 以前的 EdgeHTML 版本  

[EdgeHTML 12 /Windows 版本 10240 (2015 年 7 月 7 日) ](./edgehtml-12.md)  

[EdgeHTML 13 /Windows 版本 10586 (2015 年 11 月 11 日) ](./edgehtml-13.md)  

[EdgeHTML 14 /Windows 版本 14393 (2016 年 8 月 8 日) ](./edgehtml-14.md)  
