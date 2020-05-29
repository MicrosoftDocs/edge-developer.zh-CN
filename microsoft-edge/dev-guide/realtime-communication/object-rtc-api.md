---
ms.assetid: ef705c70-73f8-445b-84ed-4f83679f1980
description: 了解对象实时通信（ORTC）如何使媒体在 web 浏览器、移动设备或服务器之间直接进行实时流处理。
title: 开发人员指南-对象 RTC API
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘、web 开发、html、css、javascript、开发人员
ms.openlocfilehash: ac033ea26fa7c1eb435b0164e5dbd2a3a5428474
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10562625"
---
# 对象 RTC API

对象实时通信（ORTC）支持媒体（音频和/或视频）通过本机 Javascript Api 在 web 浏览器、移动设备和服务器之间直接进行数据流（发送和接收）。

> [!NOTE]
> Microsoft Edge 现在实现适用于 Windows 10 设备的 ORTC。 但是，此实现不同于[ORTC API](https://go.microsoft.com/fwlink/p/?LinkID=690096)的最新版本。 在开发和发布 Microsoft Edge 后，ORTC 已继续演化-浏览器不会实现 ORTC API 中的每个对象或方法，并且包含当前未合并在规范内的扩展。 进一步开发将继续为全球各地的开发人员提供构建体验，包括与 Skype 用户和其他 WebRTC 兼容的通信服务的沟通。



若要使用 ORTC 获取实践体验，请尝试测试驱动器上的这些演示：
-  [SimpleWebRTC](https://developer.microsoft.com/microsoft-edge/testdrive/demos/simplewebrtc/)
-  [ORTC 电话呼叫](https://developer.microsoft.com/microsoft-edge/testdrive/demos/twilioortc/)
-  [ORTC 演示](https://developer.microsoft.com/microsoft-edge/testdrive/demos/ortcdemo/)


有关 ORTC 的详细信息，请参阅 Microsoft Edge 开发人员博客上的[Microsoft edge 中现提供了 ORTC API](https://go.microsoft.com/fwlink/p/?LinkID=627564) 。


## 概述图表


下图提供了一个描述 ORTC 对象之间的关系的摘要。 水平或倾斜箭头表示媒体流或数据，而垂直箭头表示通过方法和事件的交互。

ORTC 使用 "*发件人*"、"*接收器*" 和 "*transport*" 对象，这些对象具有描述它们可以执行的操作的 "*功能*"，以及用于定义配置操作的 "*参数*"。 "*跟踪*" 通过传输将媒体流捕获和编码，然后通过将媒体流跟踪呈现到视频/音频标记的接收器进行解码。

![Microsoft Edge ORTC 流图 ](./../media/ortc_diagram.png) 在上图中，对 [`RTCRtpSender`](https://msdn.microsoft.com/library/Mt502516) 提供的跟踪进行编码，将其作为输入进行传输，通过 a 或进行传输 [`RTCDtlsTransport`](https://msdn.microsoft.com/library/Mt502495) [`RTCSrtpSdesTransport`](https://msdn.microsoft.com/library/Mt502527) 。 通过发送双音频多频率（DTMF）音 [`RTCDtmfSender`](https://msdn.microsoft.com/library/Mt502496) 。

[`RTCDtlsTransport`](https://msdn.microsoft.com/library/Mt502495)和 [`RTCSrtpSdesTransport`](https://msdn.microsoft.com/library/Mt502527) 利用 [`RTCIceTransport`](https://msdn.microsoft.com/library/Mt433112) 来选择通信路径以到达接收对等的通信路径 `RTCIceTransport` ，该路径又与将 `RTCDtlsTransport` `RTCSrtpSdesTransport` multiplexes 媒体关联 [`RTCRtpReceiver`](https://msdn.microsoft.com/library/Mt502508) 。 `RTCRtpReceiver`然后解码媒体，生成一个由音频或视频标记呈现的轨道。

其他几个对象也扮演着角色。 [`RTCIceGatherer`](https://msdn.microsoft.com/library/Mt433107)收集由单个对象使用的本地 ICE 候选人 [`RTCIceTransport`](https://msdn.microsoft.com/library/Mt433112) 。 API 的其余部分填写有关 RTP*功能*和*参数*、*操作统计信息*和与[WebRTC 1.0 API](https://go.microsoft.com/fwlink/p/?LinkID=627573)的兼容性的详细信息。

> [!NOTE]
> 由于 Microsoft Edge 未实现数据通道， `RTCDataChannel` 因此 `RTCSctpTransport` 不支持和对象。




## 初始 Microsoft Edge 实现中支持的组件


* **ORTC API 支持。** 音频/视频通信是主要焦点，包括以下对象：、、、、以及 [`RTCIceGatherer`](https://msdn.microsoft.com/library/Mt433107) [`RTCIceTransport`](https://msdn.microsoft.com/library/Mt433112) [`RTCDtlsTransport`](https://msdn.microsoft.com/library/Mt502495) [`RTCRtpSender`](https://msdn.microsoft.com/library/Mt502516) [`RTCRtpReceiver`](https://msdn.microsoft.com/library/Mt502508) [`RTCStats`](https://msdn.microsoft.com/library/Mt589726) 不直接在图表中显示的接口。
* **RTP/RTCP 多路传输支持。** [`RTP/RTCP multiplexing`](https://msdn.microsoft.com/library/Mt502503)与配合使用时需要 [`DtlsTransport`](https://msdn.microsoft.com/library/Mt502495) 。 还支持 A/V 多路传输。
* **STUN/车/冰支持。** 支持 STUN [（rfc 5389）](https://go.microsoft.com/fwlink/p/?LinkID=627619)、TURN （rfc [5766）](https://go.microsoft.com/fwlink/p/?LinkID=627620)以及 ICE [（rfc 5245）](https://go.microsoft.com/fwlink/p/?LinkID=627621)。 在 ICE 内，支持正常的 nomination，并受到部分支持的严格 nomination （作为接收器）。 DTLS-SRTP [（RFC 5764）](https://go.microsoft.com/fwlink/p/?LinkID=627622)受支持，基于 DTLS 1.0 [（RFC4347）](https://go.microsoft.com/fwlink/p/?LinkID=627629)。
* **编解码器支持。** 对于[音频编解码器](https://msdn.microsoft.com/library/Mt599587)，我们支持711、722、OPUS 和绞丝。 我们还根据 RTCWEB 音频要求支持舒适的噪音（CN）和 DTMF。 对于目前我们支持 [`H.264UC`](https://msdn.microsoft.com/library/Mt589706) Skype 服务使用的编解码器的视频，支持高级功能，如 simulcast、可伸缩视频编码和转发纠错。 我们正在努力实现使用 H-p 的互操作视频。

> [!NOTE]
> 如果你熟悉 WebRTC 1.0 实现，并且对 WebRTC 1.0 和 ORTC 内对象支持的演变感兴趣，我们建议使用来自 2014 IIT RTC 会议的 Google、Microsoft 和 Hookflash 的以下演示： "[ORTC API Update](http://www.rtc-conference.com/2016/wp-content/uploads/gravity_forms/2-2f7a537445fa703985ab4d2372ac42ca/2014/10/ORTC_API_Update.pdf)"。




## 1:1 通信的应用级别代码流


对于此方案，两个 Windows 10 计算机将充当两个对等的计算机对等方作为信号通道，以便在对等之间交换信息，以便可以在它们之间建立连接。

下面的步骤将作用于由一个对等方执行的操作。 两个对等都必须执行类似的步骤才能设置1:1 通信。 若要更好地理解以下代码片段，请参阅[Microsoft Edge 测试驱动器演示](https://go.microsoft.com/fwlink/p/?LinkID=627635)。

此示例使用音频视频和 RTP/RTCP 多路传输，因此你只能看到单个 ICE 和 DTLS 传输，用于传输音频和视频的 RTP 和 RTCP 数据包。

`Step #1.` 创建 [`MediaStream`](https://msdn.microsoft.com/library/Mt131875) 带有一个音频轨和一个视频轨的对象（即[媒体捕获和流 API](./../multimedia/media-Capture-and-Streams.md)）。

```js
navigator.MediaDevices.getUserMedia ({
    "audio": true,
    "video": {
        width: 640,
        height: 360,
        facingMode: "user"
    }
}).then(
    gotStream
).catch(
    gotMediaError
);

function gotStream(stream) {
    var mediaStreamLocal = stream;
    …
}
```

`Step #2.` 创建 [`ICE gatherer`](https://msdn.microsoft.com/library/mt433107(v=vs.85).aspx) ，并启用本地 [`ICE candidates`](https://msdn.microsoft.com/library/Mt502499) 以向远程对等发出信号。

```js
var iceOptions = new RTCIceGatherOptions;
iceOptions.gatherPolicy = "all";
iceOptions.iceservers = ... ;
var iceGathr = new RTCIceGatherer(iceOptions);
iceGathr.onlocalcandidate = function(evt) {
    mySignaller.signalMessage({
        "candidate": evt.candidate
    });
};
```

为了帮助保护用户隐私，Microsoft Edge 引入了一个允许用户控制对象是否可以公开本地主机 IP 地址的选项 [`IceGatherer`](https://msdn.microsoft.com/library/Mt433107) 。 将提供一个接口选项以切换此设置。

在[Microsoft Edge 测试驱动器演示](https://go.microsoft.com/fwlink/p/?LinkID=627635)中，已设置了一个 "车削服务器"。 此车削服务器的吞吐量非常有限，因此仅限于演示页面使用。

`Step #3.` 创建 [`ICE transport`](https://msdn.microsoft.com/library/Mt433112) 用于音频和视频的，并准备处理 [`ICE candidates`](https://msdn.microsoft.com/library/Mt502499) ICE 传输上的远程。

```js
var iceTr = new RTCIceTransport();
mySignaller.onRemoteCandidate = function(remote) {
    iceTr.addRemoteCandidate(remote.candidate);
}
```

此处的另一个选项是将所有远程 ICE 候选人累积到一个数组中 `remoteCandidates` ，并通过调用 `iceTr.setRemoteCandidates(remoteCandidates)` 将所有远程候选人添加到一起。

`Step #4.` 创建 DTLS 传输。

```js
var dtlsTr = new RTCDtlsTransport(iceTr);
```

`Step #5.` 创建发件人和收件人对象。

```js
var audioTrack = mediaStreamLocal.getAudioTracks()[0];
var videoTrack = mediaStreamLocal.getVideoTracks()[0];
var audioSender = new RtpSender(audioTrack, dtlsTr);
var videoSender = new RtpSender(videoTrack, dtlsTr);
var audioReceiver = new RtpReceiver(dtlsTr, "audio");
var videoReceiver = new RtpReceiver(dtlsTr, "video");
```

步骤 #6。 检索接收方和发件人功能。

```js
var recvAudioCaps = RTCRtpReceiver.getCapabilities("audio");
var recvVideoCaps = RTCRtpReceiver.getCapabilities("video");
var sendAudioCaps = RTCRtpSender.getCapabilities("audio");
var sendVideoCaps = RTCRtpSender.getCapabilities("video");
```

`Step #7.` 可以交换 ICE/DTLS 参数和发送/接收功能。

```js
mySignaller.signalMessage({
    "ice": iceGathr.getLocalParameters(),
    "dtls": dtlsTr.getLocalParameters(),
    "recvAudioCaps": recvAudioCaps,
    "recvVideoCaps": recvVideoCaps,
    "sendAudioCaps": sendAudioCaps,
    "sendVideoCaps": sendVideoCaps
};
```

`Step #8.` 获取远程参数，启动 [`ICE`](https://msdn.microsoft.com/library/Mt433112) 和 [`DTLS`](https://msdn.microsoft.com/library/Mt502495) 传输，并设置音频和视频发送和接收参数。

```js
mySignaller.onRemoteParams = function(params) {
    // The responder answers with its preferences, parameters and capabilities
    // Derive the send and receive parameters.
    var audioSendParams = myCapsToSendParams(sendAudioCaps, params.recvAudioCaps);
    var videoSendParams = myCapsToSendParams(sendVideoCaps, params.recvVideoCaps);
    var audioRecvParams = myCapsToRecvParams(recvAudioCaps, params.sendAudioCaps);
    var videoRecvParams = myCapsToRecvParams(recvVideoCaps, params.sendVideoCaps);
    iceTr.start(iceGathr, params.ice, RTCIceRole.controlling);
    dtlsTr.start(params.dtls);
    audioSender.send(audioSendParams);
    videoSender.send(videoSendParams);
    audioReceiver.receive(audioRecvParams);
    videoReceiver.receive(videoRecvParams);
};
```

下面是帮助程序函数的主干。 在[Microsoft Edge 测试驱动器演示](https://go.microsoft.com/fwlink/p/?LinkID=627635)中查找更多详细信息。

```js
RTCRtpParameters function myCapsToSendParams (RTCRtpCapabilities sendCaps, RTCRtpCapabilities remoteRecvCaps) {
    // Function returning the sender RTCRtpParameters, based on intersection of the local sender and remote receiver capabilities.
    // Steps to be followed:
    // 1. Determine the RTP features that the receiver and sender have in common.
    // 2. Determine the codecs that the sender and receiver have in common.
    // 3. Within each common codec, determine the common formats and rtcpFeedback mechanisms.
    // 4. Determine the payloadType to be used, based on the receiver preferredPayloadType.
    // 5. Set RTCRtcpParameters such as mux to their default values.  
}

RTCRtpParameters function myCapsToRecvParams(RTCRtpCapabilities recvCaps, RTCRtpCapabilities remoteSendCaps) {
    return myCapsToSendParams(remoteSendCaps, recvCaps);
}
```

`Step #9.` 通过视频标记呈现和播放远程媒体流跟踪。

```js
var videoRenderer = document.getElementById("myRtcVideoTag");
var mediaStreamRemote = new MediaStream();
mediaStreamRemote.addTrack(audioReceiver.track);
mediaStreamRemote.addTrack(videoReceiver.track);
videoRenderer.srcObject = mediaStreamRemote;
videoRenderer.play();
```

在熟悉设置1:1 调用后，应用相同的原则，使用网状拓扑设置较小组调用，其中每个对等都将与组的其余部分有1:1 连接。 由于 Microsoft Edge 平台不支持并行分叉，因此应通过1:1 信号进行处理，以便 [`IceGatherer`](https://msdn.microsoft.com/library/Mt433107) 将独立和 [`DtlsTransport`](https://msdn.microsoft.com/library/Mt502495) 对象用于每个连接。

## Microsoft Edge 中的实现详细信息


ORTC 规范相对稳定，因为 ORTC 社区组在 JavaScript API 级别发出了 "调用实施"，并且不应出现重大挑战。 基于此，已为在协议级别上的跨浏览器互操作性测试发布了 Microsoft Edge 实现。

应注意 Microsoft Edge 实现中的一些限制：

* `RTCIceTransportController` 不受支持。 Microsoft Edge 实现处理每个传输基础上的 ICE 冻结/unfreezing，因此 `IceTransports` 无需进行排序。 此方法应与现有实现交互操作。
* `RtpListener` 尚不支持。 这意味着 SSRCs （stream 和同步源）需要提前在中指定 [`RtpReceiver`](https://msdn.microsoft.com/library/Mt502508) 。
* 在 `IceTransport` 、、或中尚不支持分叉 `IceGatherer` `DtlsTransport` 。 对分叉的解决方案 `DtlsTransport` 仍在 ORTC 社区组中讨论。
* 尚不支持 RTP/RTCP 非 mux `DtlsTransport` 。 使用 `DtlsTransport` 你的应用程序时，需要支持 RTP/RTCP mux。
* 在中 [`RTCRtpEncodingParameters Dictionary`](https://msdn.microsoft.com/library/mt502505(v=vs.85).aspx) ，Microsoft Edge 当前忽略大多数编码质量控件，但确实需要设置 "active" 和 "ssrc" 属性。
* 该 `icecandidatepairchanged` 事件尚不受支持。 你可以通过方法提取候选对信息 [`getNominatedCandidatePair`](https://msdn.microsoft.com/library/Mt433087) 。
* Microsoft Edge 目前不支持 `DataChannel` ORTC 规范中当前定义的任何功能。

#### 期待

Microsoft Edge 实施仍在早期，预计功能集将在未来的几个月内继续增长。 Microsoft Edge 实施的目标是当今整个 web 的互操作性，以及长期的通信行业。



## API 参考

[ORTC （对象实时通信）](https://msdn.microsoft.com/library/Mt433097)

## 演示

[SimpleWebRTC](https://developer.microsoft.com/microsoft-edge/testdrive/demos/simplewebrtc/)

[ORTC 电话呼叫](https://developer.microsoft.com/microsoft-edge/testdrive/demos/twilioortc/)

[ORTC 演示](https://developer.microsoft.com/microsoft-edge/testdrive/demos/ortcdemo/)

## 相关主题

[ORTC API 现在可在 Microsoft Edge 中使用](https://go.microsoft.com/fwlink/p/?LinkID=627564)

[SimpleWebRTC：使用 Microsoft Edge 的 ORTC API 和 Chrome 和 Firefox 中的 WebRTC Api 进行跨浏览器的会议呼叫。](https://go.microsoft.com/fwlink/p/?LinkID=629636)

[通过 Skype、Skype for business 和 Microsoft Edge 实现 Web 的无缝通信体验。](https://go.microsoft.com/fwlink/p/?LinkID=671722)

[ORTC （对象实时通信）社区组](https://go.microsoft.com/fwlink/p/?LinkID=671724)

## 书

[用于 WebRTC 的 W3C 对象 RTC （ORTC） API](http://draft.ortc.org/)  
