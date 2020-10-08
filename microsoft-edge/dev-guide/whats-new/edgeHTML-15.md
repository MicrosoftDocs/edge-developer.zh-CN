---
description: 本指南概述了 EdgeHTML 15 中包含的开发人员功能和标准。
title: EdgeHTML 15 中的新功能和 Api
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/02/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘、web 开发、html、css、javascript、开发人员
ms.custom: seodec18
ms.openlocfilehash: 4fd0bbc06d27bace424ea99cfe9941aabc737fee
ms.sourcegitcommit: 204a284e21bf2da5cdc862c5e8b5839245abbbbc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/02/2020
ms.locfileid: "11094359"
---
# EdgeHTML 15 中的新增功能  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

以下是当前版本的 Microsoft Edge 平台（从 [Windows 10 创意者更新](https://blogs.windows.com/buildingapps/2017/04/05/windows-10-creators-update-creators-update-sdk-released/#MMhK2OdcrR12Vi6u.97) \ (04/2017，内部版本 15063 \ ) ）随附的更改。  有关 Microsoft Edge 整体浏览器更改的概述，请参阅 [Windows 10 创意者更新中 Microsoft Edge 中的新增功能](https://blogs.windows.com/msedgedev/2017/04/11)。  

有关后续 Windows 预览体验计划预览版本中的更改，请参阅 [EdgeHTML 中的新增功能](../whats-new.md)。  

下面是以下更改列表的固定链接：  [https://aka.ms/devguide_edgehtml_15](./edgehtml-15.md) 。  

## 新增功能  

### CSS 自定义属性  

Microsoft Edge 现在支持 [Css 自定义属性](https://drafts.csswg.org/css-variables)，即 css 变量。  CSS 变量允许你创建可在整个样式表中重复使用的自定义 CSS 属性，以帮助减少重复数据量（如重复的颜色）。  使用 CSS 变量非常简单：  

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

### 交集观察器  

EdgeHTML 15 引入了 [交集观察程序 API](https://w3c.github.io/IntersectionObserver) 规范。  "交集观察程序" API 允许你异步查询 DOM 元素相对于其他元素或全局视区的位置和可见性。  此 API 通过创建一种在视图中高效通知元素的方法，消除了自定义昂贵的代码的需要。  

### JavaScript  

性能优化采用 Chakra JavaScript 引擎的 EdgeHTML 15 次阶段。  通过 Windows 10 创意者更新，Chakra 可通过重新延迟函数和优化堆参数来节省内存，并提高 minified 代码的性能。  

此外，EdgeHTML 15 引入了以下功能预览：  

#### 实验性 JavaScript 功能  

已启用 `about:flags`  

*   [WebAssembly](https://developer.microsoft.com/microsoft-edge/platform/status/webassemblymvp/?q=WebAssembly) \ ([演示](https://webassembly.org/demo)\ )   
*   [共享内存和 Atomics](https://developer.microsoft.com/microsoft-edge/platform/status/sharedmemoryandatomics/?q=Atomics)  

有关进一步的详细信息，请参阅 [Microsoft Edge 中改进的 JavaScript 性能、WebAssembly 和共享内存](https://blogs.windows.com/msedgedev/2017/04/20) 。  

### 付款请求 API  

[付款请求 API](https://w3.org/TR/payment-request)现在受支持，在 Windows 10 电脑和手机上的 web 上支持更简单的结帐和付款。  此 API 使 Microsoft Edge 能够充当商家、消费者和付款方式 \ (（如信用卡）之间的媒介，如消费者已存储在云中的 ) 。  有关付款请求 API 的详细信息，请查看 [更简单的 web 付款：介绍付款请求 api](https://blogs.windows.com/msedgedev/2016/12/15) 和 [付款请求 api](/microsoft-edge/dev-guide/device/payment-request-api) 开发人员指南。  

### TCP 快速打开 (TFO)   
TCP Fast Open 功能可减少打开 TCP 连接所需的往返次数，从而提高浏览器网络性能。  有关更多详细信息，请参阅 [使用 TCP 快速打开构建更快、更安全的 web](https://blogs.windows.com/msedgedev/2016/06/15)。  由于各种网络拓扑中的互操作性差异，默认情况下，Microsoft Edge 中不支持此功能。  若要启用它，请 `about:flags` 在地址栏中键入，然后选中 "启用**网络**" 部分下的 "**启用 TCP 快速打开**" 复选框。  

### WebRTC 和互操作的 RTC 视频编解码器支持  

EdgeHTML 15 支持 WebRTC 1.0 API 的子集，与使用 W3C WebRTC-PC API 2015 circa 的早期版本一起构建的应用程序的互操作性。  有关详细信息，请参阅 [WEBRTC API 参考](/previous-versions//mt806139(v=vs.85)) 。  

若要充分利用对等音频和视频通信中的最高级功能，建议使用 [对象实时通信) API](https://ortc.org)。  对于你希望设置群组音频和视频呼叫或直接控制单个传输、发送方和接收方对象的情况，ORTC API 更适合。  

Microsoft Edge 支持1.0 和 WebRTC 的 AVC 和 VP8 视频，并提供以下功能来支持两种编解码器类型： [abs-发送时间](https://webrtc.org/experiments/rtp-hdrext/abs-send-time)、 [goog-Remb](https://tools.ietf.org/html/draft-alvestrand-rmcat-remb-03)、 [图片损失指示和常规 NACK 反馈](https://tools.ietf.org/html/rfc4585)， [RTP 重新传输](https://tools.ietf.org/html/rfc4588)。  

有关详细信息，请参阅 [在 Microsoft Edge 中介绍 WebRTC 1.0 和互操作实时通信](https://blogs.windows.com/msedgedev/2017/01/31)。  

### WebVR  

Microsoft Edge 现在支持 [WebVR](https://immersive-web.github.io/webxr)，即连接 Windows Mixed Reality head 挂载显示器和 Microsoft Edge 的实验 API。  此连接允许在网站中体验 VR 内容，这意味着沉浸式 VR 体验不再局限于桌面应用程序。  

Microsoft Edge 中的虚拟现实由 WebGL （用于呈现3D 和2D 图形的 JavaScript API）提供支持。  WebGL 支持 WebGL 库（如 BabylonJS）生成的应用程序和应用程序。  连接后，WebVR 将发送与耳机周围的位置和传感器信息相对应的视觉对象。  WebVR API 还支持空间控制器，感谢使用 [游戏板 API](../dom/gamepad-api.md)的扩展。  此 API 在默认情况下处于打开状态，因此无需切换标志。  

有关详细信息，请参阅 [WEBVR api 参考](/previous-versions//mt806281(v=vs.85)) 和 [游戏板 api 参考](https://developer.mozilla.org/docs/Web/API/Gamepad_API) 。  

 > [!NOTE] 
 > 由于 WebVR 规范仍在开发中，Microsoft Edge 的实现可能会在行的后面更改。  

## 更新的功能  

### 内容安全策略 (级别 2)   

已使用 CSP 1 的网站应继续与对 CSP 2 的 Microsoft Edge 支持配合使用，但最好切换 `frame-src` 将工作脚本加载到新指令的任何指令，以便 `child-src` 在以后对您的网站进行校对。  \ (在 CSP 3 中， `frame-src` 将不再适用于工作人员。 \n ) CSP 2 也会添加以下内容：  

:::row:::
   :::column span="1":::
      新指令  
   :::column-end:::
   :::column span="2":::
      `base-uri`、 `child-src` 、 `form-action` `frame-ancestors` 和 `plugin-types` 。  有关详细信息，请参阅 [Microsoft Edge 支持的 CSP 指令](../security/content-security-policy.md) 。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      工作人员支持  
   :::column-end:::
   :::column span="2":::
      后台辅助脚本由其自己的策略控制，与加载它们的文档的策略不同。  对于主文档，您可以在响应标题中为工作人员设置 CSP。  CSP 2 中的新增功能也是该  `allow-scripts` `allow-same-origin` 指令的标志 `sandbox` 现在会影响工作线程创建。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      内联脚本和样式  
   :::column-end:::
   :::column span="2":::
      CSP 2 允许通过提供 nonces 和哈希作为允许列表机制来执行内联脚本和样式块。  Nonces 是在 CSP 策略和页面的脚本标记中出现的每个页面加载上生成的随机 base 64 值。  当页面在加载时动态生成时，服务器将生成 nonce 值，将其插入到页面中的 NonceToken，并在内容安全策略 HTTP 标头中声明它。  哈希是使用 sha384 或 sha512 算法 \ ) 从在 `<script>` `<style>` `script-src` `style-src` CSP 策略中使用或指令 \ ) 指定 \ (或元素的内容 (生成的静态值。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      CSP 违反报告  
   :::column-end:::
   :::column span="2":::
      新事件 `SecurityPolicyViolationEvent` 现将在 CSP 违规时触发。  CSP 报告的早期机制 `report-uri` 继续受支持。  已向冲突报告添加了多个新字段，其中包含 `effectiveDirective` 违反 ) 的策略 \ (， `statusCode` \ (HTTP 响应代码 \ ) ，\ (了有问题的 `sourceFile` 资源的 URL \ ) 、 `lineNumber` 和 `columnNumber` 。  
   :::column-end:::
:::row-end:::  

### Web 身份验证  

使用[Windows Hello](https://www.microsoft.com/windows/comprehensive-security)生物识别的新兴[WEB 身份验证 API](../device/web-authentication.md)的 Microsoft Edge 支持已更新，但具有以下更改：  

*   [EdgeHTML 14](https://blogs.windows.com/msedgedev/2016/08/04) (Windows 10 周年更新、内部版本10240、7/2016 \ )  (通过 MSCredentials 接口 \ ) 公开了[MSCredentials](/previous-versions//mt697639(v=vs.85))接口 \ 中引入的实验性 Web 身份验证 API 的初始实现。  虽然这些 Api 在 EdgeHTML 15 中仍然可用，但它们现在已被弃用，取而代之的是在规范的 [更新快照](https://w3.org/TR/2016/WD-webauthn-20160928) 中定义的非前缀、基于标准的 api 和行为，并且可能会在规范逐渐提高标准化时继续进行更改。  

*   默认情况下，最新的 Microsoft Edge 实现处于关闭状态，并在您的地址栏中输入 "标志 \ (" `about:flags` 以打开功能 \ ) 。  

*   Microsoft Edge 尚不支持诸如 USB 密钥或蓝牙设备之类的外部凭据。  当前 API 仅限于 TPM 中存储的嵌入凭据。  如果 TPM 在设备上不可用，则使用软件回退。  

*   当前登录的 Windows 用户帐户必须配置为至少支持 PIN，并且最好是指纹或指纹生物识别。  这是为了确保 Windows 可以对 TPM 的访问进行身份验证。  

*   在规范中介绍的 [预定义扩展](https://w3.org/TR/webauthn/#extension-predef) ，Microsoft Edge 仅支持 [FIDO AppId](https://w3.org/TR/webauthn/#extension-appid) \ (`webauthn_txAuthSimple` \ ) 。  

*  该 `timeoutSeconds` 选项当前未评估  

### WebDriver  

EdgeHTML 15 提供少量的 WebDriver 更新，包括对无声命令行标志和新命令终结点的支持：  

| 方法 | URI 模板 | 命令 |  
|:--- |:---  |:--- |    
| POST | /session/{session id}/alert/accept | [接受通知](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-accept-alert) |  
| POST | /session/{session id}/alert/dismiss | [消除警告](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-dismiss-alert) |  
| GET | /session/{session id}/alert/text | [获取通知文本](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-get-alert-text) |  
| POST | /session/{session id}/alert/text | [发送提醒文本](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-send-alert-text) |  
| POST | /session/{session id}/execute/async | [执行异步脚本](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-execute-async-script) |  
| POST | /session/{session id}/execute/sync | [执行脚本](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-execute-script) |  
| GET | /session/{session id}/window | [获取窗口句柄](https://w3c.github.io/webdriver/webdriver-spec.html#get-window-handle) |  
| GET | /session/{session id}/window/handles | [获取窗口句柄](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-get-window-handles) |  

有关详细信息以及其他 WebDriver 功能的状态，请参阅 [WebDriver](../../webdriver.md)。  

## EdgeHTML 15 中的新 Api  

下面是 EdgeHTML 15 中新 Api 的完整列表。  它们以的格式列出 `[interface name].[api name]` 。  

<iframe height='582' scrolling='no' title='新的 EdgeHTML15 Api' src='//codepen.io/MicrosoftEdgeDocumentation/embed/evRjjZ/?height=582&theme-id=23761&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'>请参阅 <a href='http://codepen.io/MicrosoftEdgeDocumentation/pen/evRjjZ/'> </a> Microsoft Edge 文档 (<a href='http://codepen.io/MicrosoftEdgeDocumentation'> @MicrosoftEdgeDocumentation </a>) 上的 "CodePen" 中 <a href='http://codepen.io'> </a> 的 "新 EdgeHTML15 api"。</iframe>  

## 以前的 EdgeHTML 版本  

[EdgeHTML 12/Windows 内部版本 10240 (7/2015) ](./edgehtml-12.md)  

[EdgeHTML 13/Windows 内部版本 10586 (11/2015) ](./edgehtml-13.md)  

[EdgeHTML 14/Windows 内部版本 14393 (8/2016) ](./edgehtml-14.md)  
