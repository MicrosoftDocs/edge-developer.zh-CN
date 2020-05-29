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
# <span data-ttu-id="d48c9-104">对象 RTC API</span><span class="sxs-lookup"><span data-stu-id="d48c9-104">Object RTC API</span></span>

<span data-ttu-id="d48c9-105">对象实时通信（ORTC）支持媒体（音频和/或视频）通过本机 Javascript Api 在 web 浏览器、移动设备和服务器之间直接进行数据流（发送和接收）。</span><span class="sxs-lookup"><span data-stu-id="d48c9-105">Object Real-Time Communications (ORTC) enables media (audio and/or video) to be streamed (sent and received) in real-time directly between web browsers, mobile devices, and servers via native Javascript APIs.</span></span>

> [!NOTE]
> <span data-ttu-id="d48c9-106">Microsoft Edge 现在实现适用于 Windows 10 设备的 ORTC。</span><span class="sxs-lookup"><span data-stu-id="d48c9-106">Microsoft Edge now implements ORTC for Windows 10 devices.</span></span> <span data-ttu-id="d48c9-107">但是，此实现不同于[ORTC API](https://go.microsoft.com/fwlink/p/?LinkID=690096)的最新版本。</span><span class="sxs-lookup"><span data-stu-id="d48c9-107">However, this implementation differs from the most recent version of the [ORTC API](https://go.microsoft.com/fwlink/p/?LinkID=690096).</span></span> <span data-ttu-id="d48c9-108">在开发和发布 Microsoft Edge 后，ORTC 已继续演化-浏览器不会实现 ORTC API 中的每个对象或方法，并且包含当前未合并在规范内的扩展。</span><span class="sxs-lookup"><span data-stu-id="d48c9-108">ORTC has continued to evolve since the development and release of Microsoft Edge -- the browser does not implement every object or method within the ORTC API, and includes extensions not currently incorporated within the specification.</span></span> <span data-ttu-id="d48c9-109">进一步开发将继续为全球各地的开发人员提供构建体验，包括与 Skype 用户和其他 WebRTC 兼容的通信服务的沟通。</span><span class="sxs-lookup"><span data-stu-id="d48c9-109">Further development will continue with the goal to enable developers around the world to build experiences that include the ability to talk to Skype users and other WebRTC compatible communication services.</span></span>



<span data-ttu-id="d48c9-110">若要使用 ORTC 获取实践体验，请尝试测试驱动器上的这些演示：</span><span class="sxs-lookup"><span data-stu-id="d48c9-110">To get a hands-on experience with ORTC, try out these demos on Test Drive:</span></span>
-  [<span data-ttu-id="d48c9-111">SimpleWebRTC</span><span class="sxs-lookup"><span data-stu-id="d48c9-111">SimpleWebRTC</span></span>](https://developer.microsoft.com/microsoft-edge/testdrive/demos/simplewebrtc/)
-  [<span data-ttu-id="d48c9-112">ORTC 电话呼叫</span><span class="sxs-lookup"><span data-stu-id="d48c9-112">ORTC phone call</span></span>](https://developer.microsoft.com/microsoft-edge/testdrive/demos/twilioortc/)
-  [<span data-ttu-id="d48c9-113">ORTC 演示</span><span class="sxs-lookup"><span data-stu-id="d48c9-113">ORTC demo</span></span>](https://developer.microsoft.com/microsoft-edge/testdrive/demos/ortcdemo/)


<span data-ttu-id="d48c9-114">有关 ORTC 的详细信息，请参阅 Microsoft Edge 开发人员博客上的[Microsoft edge 中现提供了 ORTC API](https://go.microsoft.com/fwlink/p/?LinkID=627564) 。</span><span class="sxs-lookup"><span data-stu-id="d48c9-114">For more information about ORTC, check out [ORTC API is now available in Microsoft Edge](https://go.microsoft.com/fwlink/p/?LinkID=627564) on the Microsoft Edge dev blog.</span></span>


## <span data-ttu-id="d48c9-115">概述图表</span><span class="sxs-lookup"><span data-stu-id="d48c9-115">Overview Diagram</span></span>


<span data-ttu-id="d48c9-116">下图提供了一个描述 ORTC 对象之间的关系的摘要。</span><span class="sxs-lookup"><span data-stu-id="d48c9-116">The diagram below provides a summary describing relationships between ORTC objects.</span></span> <span data-ttu-id="d48c9-117">水平或倾斜箭头表示媒体流或数据，而垂直箭头表示通过方法和事件的交互。</span><span class="sxs-lookup"><span data-stu-id="d48c9-117">Horizontal or slanted arrows denote the flow of media or data, whereas vertical arrows denote interactions via methods and events.</span></span>

<span data-ttu-id="d48c9-118">ORTC 使用 "*发件人*"、"*接收器*" 和 "*transport*" 对象，这些对象具有描述它们可以执行的操作的 "*功能*"，以及用于定义配置操作的 "*参数*"。</span><span class="sxs-lookup"><span data-stu-id="d48c9-118">ORTC uses "*sender*", "*receiver*" and "*transport*" objects, which have "*capabilities*" describing what they are capable of doing, as well as "*parameters*" which define what they are configured to do.</span></span> <span data-ttu-id="d48c9-119">"*跟踪*" 通过传输将媒体流捕获和编码，然后通过将媒体流跟踪呈现到视频/音频标记的接收器进行解码。</span><span class="sxs-lookup"><span data-stu-id="d48c9-119">"*Tracks*" capture and encode media streams by senders, traveling over transports, then decoded by receivers that render the media stream tracks to video/audio tags.</span></span>

![<span data-ttu-id="d48c9-120">Microsoft Edge ORTC 流图 ](./../media/ortc_diagram.png) 在上图中，对 [`RTCRtpSender`](https://msdn.microsoft.com/library/Mt502516) 提供的跟踪进行编码，将其作为输入进行传输，通过 a 或进行传输 [`RTCDtlsTransport`](https://msdn.microsoft.com/library/Mt502495) [`RTCSrtpSdesTransport`](https://msdn.microsoft.com/library/Mt502527) 。</span><span class="sxs-lookup"><span data-stu-id="d48c9-120">Microsoft Edge ORTC Flow Diagram](./../media/ortc_diagram.png) In the figure above, the [`RTCRtpSender`](https://msdn.microsoft.com/library/Mt502516) encodes the track provided as input, which is transported over a [`RTCDtlsTransport`](https://msdn.microsoft.com/library/Mt502495) or an [`RTCSrtpSdesTransport`](https://msdn.microsoft.com/library/Mt502527).</span></span> <span data-ttu-id="d48c9-121">通过发送双音频多频率（DTMF）音 [`RTCDtmfSender`](https://msdn.microsoft.com/library/Mt502496) 。</span><span class="sxs-lookup"><span data-stu-id="d48c9-121">Sending of Dual Tone Multi Frequency (DTMF) tones is supported via the [`RTCDtmfSender`](https://msdn.microsoft.com/library/Mt502496).</span></span>

<span data-ttu-id="d48c9-122">[`RTCDtlsTransport`](https://msdn.microsoft.com/library/Mt502495)和 [`RTCSrtpSdesTransport`](https://msdn.microsoft.com/library/Mt502527) 利用 [`RTCIceTransport`](https://msdn.microsoft.com/library/Mt433112) 来选择通信路径以到达接收对等的通信路径 `RTCIceTransport` ，该路径又与将 `RTCDtlsTransport` `RTCSrtpSdesTransport` multiplexes 媒体关联 [`RTCRtpReceiver`](https://msdn.microsoft.com/library/Mt502508) 。</span><span class="sxs-lookup"><span data-stu-id="d48c9-122">The [`RTCDtlsTransport`](https://msdn.microsoft.com/library/Mt502495) and [`RTCSrtpSdesTransport`](https://msdn.microsoft.com/library/Mt502527) utilize an [`RTCIceTransport`](https://msdn.microsoft.com/library/Mt433112) to select a communication path to reach the receiving peer's `RTCIceTransport`, which is in turn associated with an `RTCDtlsTransport` or `RTCSrtpSdesTransport` which de-multiplexes media to the [`RTCRtpReceiver`](https://msdn.microsoft.com/library/Mt502508).</span></span> <span data-ttu-id="d48c9-123">`RTCRtpReceiver`然后解码媒体，生成一个由音频或视频标记呈现的轨道。</span><span class="sxs-lookup"><span data-stu-id="d48c9-123">The `RTCRtpReceiver` then decodes media, producing a track which is rendered by an audio or video tag.</span></span>

<span data-ttu-id="d48c9-124">其他几个对象也扮演着角色。</span><span class="sxs-lookup"><span data-stu-id="d48c9-124">Several other objects also play a role.</span></span> <span data-ttu-id="d48c9-125">[`RTCIceGatherer`](https://msdn.microsoft.com/library/Mt433107)收集由单个对象使用的本地 ICE 候选人 [`RTCIceTransport`](https://msdn.microsoft.com/library/Mt433112) 。</span><span class="sxs-lookup"><span data-stu-id="d48c9-125">The [`RTCIceGatherer`](https://msdn.microsoft.com/library/Mt433107) gathers local ICE candidates for use by a single [`RTCIceTransport`](https://msdn.microsoft.com/library/Mt433112) object.</span></span> <span data-ttu-id="d48c9-126">API 的其余部分填写有关 RTP*功能*和*参数*、*操作统计信息*和与[WebRTC 1.0 API](https://go.microsoft.com/fwlink/p/?LinkID=627573)的兼容性的详细信息。</span><span class="sxs-lookup"><span data-stu-id="d48c9-126">Remaining sections of the API fill in details relating to RTP *capabilities* and *parameters*, *operational statistics* and compatibility with the [WebRTC 1.0 API](https://go.microsoft.com/fwlink/p/?LinkID=627573).</span></span>

> [!NOTE]
> <span data-ttu-id="d48c9-127">由于 Microsoft Edge 未实现数据通道， `RTCDataChannel` 因此 `RTCSctpTransport` 不支持和对象。</span><span class="sxs-lookup"><span data-stu-id="d48c9-127">Since Microsoft Edge does not implement the data channel, the `RTCDataChannel` and `RTCSctpTransport` objects are not supported.</span></span>




## <span data-ttu-id="d48c9-128">初始 Microsoft Edge 实现中支持的组件</span><span class="sxs-lookup"><span data-stu-id="d48c9-128">Components supported in the initial Microsoft Edge implementation</span></span>


* **<span data-ttu-id="d48c9-129">ORTC API 支持。</span><span class="sxs-lookup"><span data-stu-id="d48c9-129">ORTC API support.</span></span>** <span data-ttu-id="d48c9-130">音频/视频通信是主要焦点，包括以下对象：、、、、以及 [`RTCIceGatherer`](https://msdn.microsoft.com/library/Mt433107) [`RTCIceTransport`](https://msdn.microsoft.com/library/Mt433112) [`RTCDtlsTransport`](https://msdn.microsoft.com/library/Mt502495) [`RTCRtpSender`](https://msdn.microsoft.com/library/Mt502516) [`RTCRtpReceiver`](https://msdn.microsoft.com/library/Mt502508) [`RTCStats`](https://msdn.microsoft.com/library/Mt589726) 不直接在图表中显示的接口。</span><span class="sxs-lookup"><span data-stu-id="d48c9-130">Audio/video communications is the primary focus, including the following objects: [`RTCIceGatherer`](https://msdn.microsoft.com/library/Mt433107), [`RTCIceTransport`](https://msdn.microsoft.com/library/Mt433112), [`RTCDtlsTransport`](https://msdn.microsoft.com/library/Mt502495), [`RTCRtpSender`](https://msdn.microsoft.com/library/Mt502516), [`RTCRtpReceiver`](https://msdn.microsoft.com/library/Mt502508), as well as the [`RTCStats`](https://msdn.microsoft.com/library/Mt589726) interfaces that are not shown directly in the diagram.</span></span>
* **<span data-ttu-id="d48c9-131">RTP/RTCP 多路传输支持。</span><span class="sxs-lookup"><span data-stu-id="d48c9-131">RTP/RTCP multiplexing support.</span></span>** <span data-ttu-id="d48c9-132">[`RTP/RTCP multiplexing`](https://msdn.microsoft.com/library/Mt502503)与配合使用时需要 [`DtlsTransport`](https://msdn.microsoft.com/library/Mt502495) 。</span><span class="sxs-lookup"><span data-stu-id="d48c9-132">[`RTP/RTCP multiplexing`](https://msdn.microsoft.com/library/Mt502503) is required for use with the [`DtlsTransport`](https://msdn.microsoft.com/library/Mt502495).</span></span> <span data-ttu-id="d48c9-133">还支持 A/V 多路传输。</span><span class="sxs-lookup"><span data-stu-id="d48c9-133">A/V multiplexing is also supported.</span></span>
* **<span data-ttu-id="d48c9-134">STUN/车/冰支持。</span><span class="sxs-lookup"><span data-stu-id="d48c9-134">STUN/TURN/ICE support.</span></span>** <span data-ttu-id="d48c9-135">支持 STUN [（rfc 5389）](https://go.microsoft.com/fwlink/p/?LinkID=627619)、TURN （rfc [5766）](https://go.microsoft.com/fwlink/p/?LinkID=627620)以及 ICE [（rfc 5245）](https://go.microsoft.com/fwlink/p/?LinkID=627621)。</span><span class="sxs-lookup"><span data-stu-id="d48c9-135">STUN [(RFC 5389)](https://go.microsoft.com/fwlink/p/?LinkID=627619), TURN [(RFC 5766)](https://go.microsoft.com/fwlink/p/?LinkID=627620) as well as ICE [(RFC 5245)](https://go.microsoft.com/fwlink/p/?LinkID=627621), are supported.</span></span> <span data-ttu-id="d48c9-136">在 ICE 内，支持正常的 nomination，并受到部分支持的严格 nomination （作为接收器）。</span><span class="sxs-lookup"><span data-stu-id="d48c9-136">Within ICE, regular nomination is supported, with aggressive nomination partially supported (as a receiver).</span></span> <span data-ttu-id="d48c9-137">DTLS-SRTP [（RFC 5764）](https://go.microsoft.com/fwlink/p/?LinkID=627622)受支持，基于 DTLS 1.0 [（RFC4347）](https://go.microsoft.com/fwlink/p/?LinkID=627629)。</span><span class="sxs-lookup"><span data-stu-id="d48c9-137">DTLS-SRTP [(RFC 5764)](https://go.microsoft.com/fwlink/p/?LinkID=627622) is supported, based on DTLS 1.0 [(RFC4347)](https://go.microsoft.com/fwlink/p/?LinkID=627629).</span></span>
* **<span data-ttu-id="d48c9-138">编解码器支持。</span><span class="sxs-lookup"><span data-stu-id="d48c9-138">Codec support.</span></span>** <span data-ttu-id="d48c9-139">对于[音频编解码器](https://msdn.microsoft.com/library/Mt599587)，我们支持711、722、OPUS 和绞丝。</span><span class="sxs-lookup"><span data-stu-id="d48c9-139">For [audio codecs](https://msdn.microsoft.com/library/Mt599587), we support G.711, G.722, Opus and SILK.</span></span> <span data-ttu-id="d48c9-140">我们还根据 RTCWEB 音频要求支持舒适的噪音（CN）和 DTMF。</span><span class="sxs-lookup"><span data-stu-id="d48c9-140">We also support Comfort Noise (CN) and DTMF according to the RTCWEB audio requirements.</span></span> <span data-ttu-id="d48c9-141">对于目前我们支持 [`H.264UC`](https://msdn.microsoft.com/library/Mt589706) Skype 服务使用的编解码器的视频，支持高级功能，如 simulcast、可伸缩视频编码和转发纠错。</span><span class="sxs-lookup"><span data-stu-id="d48c9-141">For video we currently support the [`H.264UC`](https://msdn.microsoft.com/library/Mt589706) codec used by Skype services, supporting advanced features such as simulcast, scalable video coding and forward error correction.</span></span> <span data-ttu-id="d48c9-142">我们正在努力实现使用 H-p 的互操作视频。</span><span class="sxs-lookup"><span data-stu-id="d48c9-142">We're working toward to enabling interoperable video with H.264.</span></span>

> [!NOTE]
> <span data-ttu-id="d48c9-143">如果你熟悉 WebRTC 1.0 实现，并且对 WebRTC 1.0 和 ORTC 内对象支持的演变感兴趣，我们建议使用来自 2014 IIT RTC 会议的 Google、Microsoft 和 Hookflash 的以下演示： "[ORTC API Update](http://www.rtc-conference.com/2016/wp-content/uploads/gravity_forms/2-2f7a537445fa703985ab4d2372ac42ca/2014/10/ORTC_API_Update.pdf)"。</span><span class="sxs-lookup"><span data-stu-id="d48c9-143">If you are familiar with WebRTC 1.0 implementations, and are interested in the evolution of object support within WebRTC 1.0 and ORTC, we recommend the following presentation by Google, Microsoft, and Hookflash from the 2014 IIT RTC Conference: "[ORTC API Update](http://www.rtc-conference.com/2016/wp-content/uploads/gravity_forms/2-2f7a537445fa703985ab4d2372ac42ca/2014/10/ORTC_API_Update.pdf)."</span></span>




## <span data-ttu-id="d48c9-144">1:1 通信的应用级别代码流</span><span class="sxs-lookup"><span data-stu-id="d48c9-144">App level code flow for 1:1 communications</span></span>


<span data-ttu-id="d48c9-145">对于此方案，两个 Windows 10 计算机将充当两个对等的计算机对等方作为信号通道，以便在对等之间交换信息，以便可以在它们之间建立连接。</span><span class="sxs-lookup"><span data-stu-id="d48c9-145">For this scenario, two Windows 10 machines will act as two peers with a webserver as the signaling channel to exchange information between the peers so that a connection may be established between them.</span></span>

<span data-ttu-id="d48c9-146">下面的步骤将作用于由一个对等方执行的操作。</span><span class="sxs-lookup"><span data-stu-id="d48c9-146">The steps below are scoped to operations taken by one peer.</span></span> <span data-ttu-id="d48c9-147">两个对等都必须执行类似的步骤才能设置1:1 通信。</span><span class="sxs-lookup"><span data-stu-id="d48c9-147">Both peers must go through similar steps in order to set up the 1:1 communications.</span></span> <span data-ttu-id="d48c9-148">若要更好地理解以下代码片段，请参阅[Microsoft Edge 测试驱动器演示](https://go.microsoft.com/fwlink/p/?LinkID=627635)。</span><span class="sxs-lookup"><span data-stu-id="d48c9-148">To make better sense out of the code snippets below, refer to the [Microsoft Edge Test Drive Demo](https://go.microsoft.com/fwlink/p/?LinkID=627635).</span></span>

<span data-ttu-id="d48c9-149">此示例使用音频视频和 RTP/RTCP 多路传输，因此你只能看到单个 ICE 和 DTLS 传输，用于传输音频和视频的 RTP 和 RTCP 数据包。</span><span class="sxs-lookup"><span data-stu-id="d48c9-149">This example uses audio-video and RTP/RTCP multiplexing, so you will see only a single ICE and DTLS transport, used to transport RTP and RTCP packets for both audio and video.</span></span>

`Step #1.` <span data-ttu-id="d48c9-150">创建 [`MediaStream`](https://msdn.microsoft.com/library/Mt131875) 带有一个音频轨和一个视频轨的对象（即[媒体捕获和流 API](./../multimedia/media-Capture-and-Streams.md)）。</span><span class="sxs-lookup"><span data-stu-id="d48c9-150">Create [`MediaStream`](https://msdn.microsoft.com/library/Mt131875) object (i.e. [Media Capture and Streams API](./../multimedia/media-Capture-and-Streams.md)) with one audio track and one video track.</span></span>

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

`Step #2.` <span data-ttu-id="d48c9-151">创建 [`ICE gatherer`](https://msdn.microsoft.com/library/mt433107(v=vs.85).aspx) ，并启用本地 [`ICE candidates`](https://msdn.microsoft.com/library/Mt502499) 以向远程对等发出信号。</span><span class="sxs-lookup"><span data-stu-id="d48c9-151">Create the [`ICE gatherer`](https://msdn.microsoft.com/library/mt433107(v=vs.85).aspx), and enable local [`ICE candidates`](https://msdn.microsoft.com/library/Mt502499) to be signaled to remote peer.</span></span>

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

<span data-ttu-id="d48c9-152">为了帮助保护用户隐私，Microsoft Edge 引入了一个允许用户控制对象是否可以公开本地主机 IP 地址的选项 [`IceGatherer`](https://msdn.microsoft.com/library/Mt433107) 。</span><span class="sxs-lookup"><span data-stu-id="d48c9-152">To help protect user privacy, Microsoft Edge introduces an option that allows a user to control whether local host IP addresses can be exposed by the [`IceGatherer`](https://msdn.microsoft.com/library/Mt433107) objects.</span></span> <span data-ttu-id="d48c9-153">将提供一个接口选项以切换此设置。</span><span class="sxs-lookup"><span data-stu-id="d48c9-153">An interface option will be provided to toggle this setting.</span></span>

<span data-ttu-id="d48c9-154">在[Microsoft Edge 测试驱动器演示](https://go.microsoft.com/fwlink/p/?LinkID=627635)中，已设置了一个 "车削服务器"。</span><span class="sxs-lookup"><span data-stu-id="d48c9-154">In the [Microsoft Edge Test Drive Demo](https://go.microsoft.com/fwlink/p/?LinkID=627635), a TURN server has been set up.</span></span> <span data-ttu-id="d48c9-155">此车削服务器的吞吐量非常有限，因此仅限于演示页面使用。</span><span class="sxs-lookup"><span data-stu-id="d48c9-155">This TURN server has a very limited throughput, so is limited to only demo page use.</span></span>

`Step #3.` <span data-ttu-id="d48c9-156">创建 [`ICE transport`](https://msdn.microsoft.com/library/Mt433112) 用于音频和视频的，并准备处理 [`ICE candidates`](https://msdn.microsoft.com/library/Mt502499) ICE 传输上的远程。</span><span class="sxs-lookup"><span data-stu-id="d48c9-156">Create the [`ICE transport`](https://msdn.microsoft.com/library/Mt433112) for audio and video, and prepare to handle remote [`ICE candidates`](https://msdn.microsoft.com/library/Mt502499) on the ICE transport.</span></span>

```js
var iceTr = new RTCIceTransport();
mySignaller.onRemoteCandidate = function(remote) {
    iceTr.addRemoteCandidate(remote.candidate);
}
```

<span data-ttu-id="d48c9-157">此处的另一个选项是将所有远程 ICE 候选人累积到一个数组中 `remoteCandidates` ，并通过调用 `iceTr.setRemoteCandidates(remoteCandidates)` 将所有远程候选人添加到一起。</span><span class="sxs-lookup"><span data-stu-id="d48c9-157">Another option here is to accumulate all the remote ICE candidates into an array `remoteCandidates` and call `iceTr.setRemoteCandidates(remoteCandidates)` to add all the remote candidates together.</span></span>

`Step #4.` <span data-ttu-id="d48c9-158">创建 DTLS 传输。</span><span class="sxs-lookup"><span data-stu-id="d48c9-158">Create the DTLS transport.</span></span>

```js
var dtlsTr = new RTCDtlsTransport(iceTr);
```

`Step #5.` <span data-ttu-id="d48c9-159">创建发件人和收件人对象。</span><span class="sxs-lookup"><span data-stu-id="d48c9-159">Create the sender and receiver objects.</span></span>

```js
var audioTrack = mediaStreamLocal.getAudioTracks()[0];
var videoTrack = mediaStreamLocal.getVideoTracks()[0];
var audioSender = new RtpSender(audioTrack, dtlsTr);
var videoSender = new RtpSender(videoTrack, dtlsTr);
var audioReceiver = new RtpReceiver(dtlsTr, "audio");
var videoReceiver = new RtpReceiver(dtlsTr, "video");
```

<span data-ttu-id="d48c9-160">步骤 #6。</span><span class="sxs-lookup"><span data-stu-id="d48c9-160">Step #6.</span></span> <span data-ttu-id="d48c9-161">检索接收方和发件人功能。</span><span class="sxs-lookup"><span data-stu-id="d48c9-161">Retrieve the receiver and sender capabilities.</span></span>

```js
var recvAudioCaps = RTCRtpReceiver.getCapabilities("audio");
var recvVideoCaps = RTCRtpReceiver.getCapabilities("video");
var sendAudioCaps = RTCRtpSender.getCapabilities("audio");
var sendVideoCaps = RTCRtpSender.getCapabilities("video");
```

`Step #7.` <span data-ttu-id="d48c9-162">可以交换 ICE/DTLS 参数和发送/接收功能。</span><span class="sxs-lookup"><span data-stu-id="d48c9-162">ICE/DTLS parameters and Send/Receive capabilities can be exchanged.</span></span>

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

`Step #8.` <span data-ttu-id="d48c9-163">获取远程参数，启动 [`ICE`](https://msdn.microsoft.com/library/Mt433112) 和 [`DTLS`](https://msdn.microsoft.com/library/Mt502495) 传输，并设置音频和视频发送和接收参数。</span><span class="sxs-lookup"><span data-stu-id="d48c9-163">Get remote params, start the [`ICE`](https://msdn.microsoft.com/library/Mt433112) and [`DTLS`](https://msdn.microsoft.com/library/Mt502495) transports, and set the audio and video send and receive parameters.</span></span>

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

<span data-ttu-id="d48c9-164">下面是帮助程序函数的主干。</span><span class="sxs-lookup"><span data-stu-id="d48c9-164">Below is a skeleton of the helper functions.</span></span> <span data-ttu-id="d48c9-165">在[Microsoft Edge 测试驱动器演示](https://go.microsoft.com/fwlink/p/?LinkID=627635)中查找更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="d48c9-165">Find more details in the [Microsoft Edge Test Drive Demo](https://go.microsoft.com/fwlink/p/?LinkID=627635).</span></span>

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

`Step #9.` <span data-ttu-id="d48c9-166">通过视频标记呈现和播放远程媒体流跟踪。</span><span class="sxs-lookup"><span data-stu-id="d48c9-166">Render and play the remote media stream tracks through a video tag.</span></span>

```js
var videoRenderer = document.getElementById("myRtcVideoTag");
var mediaStreamRemote = new MediaStream();
mediaStreamRemote.addTrack(audioReceiver.track);
mediaStreamRemote.addTrack(videoReceiver.track);
videoRenderer.srcObject = mediaStreamRemote;
videoRenderer.play();
```

<span data-ttu-id="d48c9-167">在熟悉设置1:1 调用后，应用相同的原则，使用网状拓扑设置较小组调用，其中每个对等都将与组的其余部分有1:1 连接。</span><span class="sxs-lookup"><span data-stu-id="d48c9-167">Once familiar with setting up 1:1 calls, apply the same principles to set up small group calls using a mesh topology, where each peer will have a 1:1 connection with the rest of the group.</span></span> <span data-ttu-id="d48c9-168">由于 Microsoft Edge 平台不支持并行分叉，因此应通过1:1 信号进行处理，以便 [`IceGatherer`](https://msdn.microsoft.com/library/Mt433107) 将独立和 [`DtlsTransport`](https://msdn.microsoft.com/library/Mt502495) 对象用于每个连接。</span><span class="sxs-lookup"><span data-stu-id="d48c9-168">Since parallel forking is not supported on the Microsoft Edge platform, this should be handled via 1:1 signaling, so that independent [`IceGatherer`](https://msdn.microsoft.com/library/Mt433107) and [`DtlsTransport`](https://msdn.microsoft.com/library/Mt502495) objects will be used for each connection.</span></span>

## <span data-ttu-id="d48c9-169">Microsoft Edge 中的实现详细信息</span><span class="sxs-lookup"><span data-stu-id="d48c9-169">Implementation details in Microsoft Edge</span></span>


<span data-ttu-id="d48c9-170">ORTC 规范相对稳定，因为 ORTC 社区组在 JavaScript API 级别发出了 "调用实施"，并且不应出现重大挑战。</span><span class="sxs-lookup"><span data-stu-id="d48c9-170">The ORTC spec has been relatively stable since the ORTC Community Group issued the "Call for Implementations," and significant challenges at the JavaScript API level are not expected.</span></span> <span data-ttu-id="d48c9-171">基于此，已为在协议级别上的跨浏览器互操作性测试发布了 Microsoft Edge 实现。</span><span class="sxs-lookup"><span data-stu-id="d48c9-171">Based on this, Microsoft Edge implementation has been released for cross-browser interoperability testing at the protocol level.</span></span>

<span data-ttu-id="d48c9-172">应注意 Microsoft Edge 实现中的一些限制：</span><span class="sxs-lookup"><span data-stu-id="d48c9-172">A few limitations in the Microsoft Edge implementation should be noted:</span></span>

* `RTCIceTransportController` <span data-ttu-id="d48c9-173">不受支持。</span><span class="sxs-lookup"><span data-stu-id="d48c9-173">is not supported.</span></span> <span data-ttu-id="d48c9-174">Microsoft Edge 实现处理每个传输基础上的 ICE 冻结/unfreezing，因此 `IceTransports` 无需进行排序。</span><span class="sxs-lookup"><span data-stu-id="d48c9-174">Microsoft Edge implementation handles ICE freezing/unfreezing on a per-transport basis, so that ordering all the `IceTransports` is not necessary.</span></span> <span data-ttu-id="d48c9-175">此方法应与现有实现交互操作。</span><span class="sxs-lookup"><span data-stu-id="d48c9-175">This approach should interoperate with existing implementations.</span></span>
* `RtpListener` <span data-ttu-id="d48c9-176">尚不支持。</span><span class="sxs-lookup"><span data-stu-id="d48c9-176">is not yet supported.</span></span> <span data-ttu-id="d48c9-177">这意味着 SSRCs （stream 和同步源）需要提前在中指定 [`RtpReceiver`](https://msdn.microsoft.com/library/Mt502508) 。</span><span class="sxs-lookup"><span data-stu-id="d48c9-177">This means that SSRCs (stream and synchronization sources) need to be specified in advance within the [`RtpReceiver`](https://msdn.microsoft.com/library/Mt502508).</span></span>
* <span data-ttu-id="d48c9-178">在 `IceTransport` 、、或中尚不支持分叉 `IceGatherer` `DtlsTransport` 。</span><span class="sxs-lookup"><span data-stu-id="d48c9-178">Forking is not yet supported in either `IceTransport`, `IceGatherer`, or `DtlsTransport`.</span></span> <span data-ttu-id="d48c9-179">对分叉的解决方案 `DtlsTransport` 仍在 ORTC 社区组中讨论。</span><span class="sxs-lookup"><span data-stu-id="d48c9-179">The solution to `DtlsTransport` forking is still under discussion in the ORTC Community Group.</span></span>
* <span data-ttu-id="d48c9-180">尚不支持 RTP/RTCP 非 mux `DtlsTransport` 。</span><span class="sxs-lookup"><span data-stu-id="d48c9-180">RTP/RTCP non-mux with `DtlsTransport` is not yet supported.</span></span> <span data-ttu-id="d48c9-181">使用 `DtlsTransport` 你的应用程序时，需要支持 RTP/RTCP mux。</span><span class="sxs-lookup"><span data-stu-id="d48c9-181">When using `DtlsTransport` your application will need to support RTP/RTCP mux.</span></span>
* <span data-ttu-id="d48c9-182">在中 [`RTCRtpEncodingParameters Dictionary`](https://msdn.microsoft.com/library/mt502505(v=vs.85).aspx) ，Microsoft Edge 当前忽略大多数编码质量控件，但确实需要设置 "active" 和 "ssrc" 属性。</span><span class="sxs-lookup"><span data-stu-id="d48c9-182">In [`RTCRtpEncodingParameters Dictionary`](https://msdn.microsoft.com/library/mt502505(v=vs.85).aspx), Microsoft Edge currently ignores most of the encoding quality controls, but does require setting the 'active' and 'ssrc' attributes.</span></span>
* <span data-ttu-id="d48c9-183">该 `icecandidatepairchanged` 事件尚不受支持。</span><span class="sxs-lookup"><span data-stu-id="d48c9-183">The `icecandidatepairchanged` event is not yet supported.</span></span> <span data-ttu-id="d48c9-184">你可以通过方法提取候选对信息 [`getNominatedCandidatePair`](https://msdn.microsoft.com/library/Mt433087) 。</span><span class="sxs-lookup"><span data-stu-id="d48c9-184">You can extract the candidate pair information through the [`getNominatedCandidatePair`](https://msdn.microsoft.com/library/Mt433087) method.</span></span>
* <span data-ttu-id="d48c9-185">Microsoft Edge 目前不支持 `DataChannel` ORTC 规范中当前定义的任何功能。</span><span class="sxs-lookup"><span data-stu-id="d48c9-185">Microsoft Edge currently does not support any of the `DataChannel` functionality currently defined in the ORTC spec.</span></span>

#### <span data-ttu-id="d48c9-186">期待</span><span class="sxs-lookup"><span data-stu-id="d48c9-186">Looking forward</span></span>

<span data-ttu-id="d48c9-187">Microsoft Edge 实施仍在早期，预计功能集将在未来的几个月内继续增长。</span><span class="sxs-lookup"><span data-stu-id="d48c9-187">Microsoft Edge implementation is still early, expect the feature set to continue to grow in the coming months.</span></span> <span data-ttu-id="d48c9-188">Microsoft Edge 实施的目标是当今整个 web 的互操作性，以及长期的通信行业。</span><span class="sxs-lookup"><span data-stu-id="d48c9-188">The goal for Microsoft Edge implementation is interoperability across the web today as well as with the real-time communications industry in the long term.</span></span>



## <span data-ttu-id="d48c9-189">API 参考</span><span class="sxs-lookup"><span data-stu-id="d48c9-189">API reference</span></span>

[<span data-ttu-id="d48c9-190">ORTC （对象实时通信）</span><span class="sxs-lookup"><span data-stu-id="d48c9-190">ORTC (Object Real-Time Communications)</span></span>](https://msdn.microsoft.com/library/Mt433097)

## <span data-ttu-id="d48c9-191">演示</span><span class="sxs-lookup"><span data-stu-id="d48c9-191">Demos</span></span>

[<span data-ttu-id="d48c9-192">SimpleWebRTC</span><span class="sxs-lookup"><span data-stu-id="d48c9-192">SimpleWebRTC</span></span>](https://developer.microsoft.com/microsoft-edge/testdrive/demos/simplewebrtc/)

[<span data-ttu-id="d48c9-193">ORTC 电话呼叫</span><span class="sxs-lookup"><span data-stu-id="d48c9-193">ORTC phone call</span></span>](https://developer.microsoft.com/microsoft-edge/testdrive/demos/twilioortc/)

[<span data-ttu-id="d48c9-194">ORTC 演示</span><span class="sxs-lookup"><span data-stu-id="d48c9-194">ORTC demo</span></span>](https://developer.microsoft.com/microsoft-edge/testdrive/demos/ortcdemo/)

## <span data-ttu-id="d48c9-195">相关主题</span><span class="sxs-lookup"><span data-stu-id="d48c9-195">Related topics</span></span>

[<span data-ttu-id="d48c9-196">ORTC API 现在可在 Microsoft Edge 中使用</span><span class="sxs-lookup"><span data-stu-id="d48c9-196">ORTC API is now available in Microsoft Edge</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=627564)

[<span data-ttu-id="d48c9-197">SimpleWebRTC：使用 Microsoft Edge 的 ORTC API 和 Chrome 和 Firefox 中的 WebRTC Api 进行跨浏览器的会议呼叫。</span><span class="sxs-lookup"><span data-stu-id="d48c9-197">SimpleWebRTC: Use Microsoft Edge's ORTC API and the WebRTC APIs in Chrome and Firefox to make cross-browser conference calls.</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=629636)

[<span data-ttu-id="d48c9-198">通过 Skype、Skype for business 和 Microsoft Edge 实现 Web 的无缝通信体验。</span><span class="sxs-lookup"><span data-stu-id="d48c9-198">Enabling Seamless Communication Experiences for the Web with Skype, Skype for Business, and Microsoft Edge.</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=671722)

[<span data-ttu-id="d48c9-199">ORTC （对象实时通信）社区组</span><span class="sxs-lookup"><span data-stu-id="d48c9-199">ORTC (OBJECT REAL-TIME COMMUNICATIONS) COMMUNITY GROUP</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=671724)

## <span data-ttu-id="d48c9-200">书</span><span class="sxs-lookup"><span data-stu-id="d48c9-200">Specification</span></span>

[<span data-ttu-id="d48c9-201">用于 WebRTC 的 W3C 对象 RTC （ORTC） API</span><span class="sxs-lookup"><span data-stu-id="d48c9-201">W3C Object RTC (ORTC) API for WebRTC</span></span>](http://draft.ortc.org/)  
