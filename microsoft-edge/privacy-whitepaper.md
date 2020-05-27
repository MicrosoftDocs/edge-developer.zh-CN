---
description: Microsoft Edge 隐私白皮书
title: Microsoft Edge 隐私白皮书
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/26/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: browser
keywords: microsoft edge、隐私、白皮书、信任
localization_priority: Priority
ms.openlocfilehash: 6aba8f6c1ae7212d5af702bcf13ff9dde6b8659b
ms.sourcegitcommit: 3f625231067df343d5afbb3f47c1063982067bcb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/26/2020
ms.locfileid: "10678223"
---
# Microsoft Edge 隐私白皮书  

我们的浏览器隐私承诺为您提供您可以获得的保护、透明度、控制和尊重。  为保持承诺以向 Microsoft 产品提供透明度，Microsoft Edge 团队提供了一个隐私声明，该白皮书介绍 Microsoft Edge 功能和服务的工作原理以及每种功能对您的隐私有何影响。  Microsoft Edge 团队的目标是让你完全了解如何使用数据、如何控制不同功能，以及如何管理所收集的数据，以便你拥有为你做出正确的隐私决策所需的信息。  

在纸张的某些部分中，Microsoft 团队提供了转到 Microsoft Edge 设置和其他页面的步骤。  为了保持一致性，Microsoft edge 团队在整个白皮书中使用了一种简写格式：你应该看到以如下方式开头或的 Url `edge://` `edge://favorites` `edge://settings/privacy` 。  若要转到页面，请直接在 Microsoft Edge 地址栏中键入粗体文本。  这些页面仅可在 Microsoft Edge 中查看。  

白皮书重点介绍 Microsoft Edge 的桌面版本，部分内容可能包括并非所有用户都提供的功能或体验。  此外，白皮书还讨论当前产品中存在的功能和服务，但将来可能会发生更改。  Microsoft 实践数据收集的 "最小化"，这意味着你的数据将保留最少的时间，但保留时间可能会有所不同，具体取决于所使用的功能或服务，并且可能会随着时间的推移而变化。  

## 地址栏和建议  

地址栏允许您输入网站 Url 和搜索网页。  默认情况下，地址栏使用您键入的字符提供搜索和网站建议。  你应看到来自你的收藏夹、浏览历史记录、以前的搜索和默认搜索提供程序的建议。  

![AddressBar](./media/whitepaper-media/address-bar.png)  

为了使浏览和搜索更快，在地址栏中键入时，键入的字符将发送到您的默认搜索提供程序，以供搜索提供程序发送回建议的搜索查询。  地址栏将你的条目分类为 URL、搜索或未知。  该信息以及你选择的建议、所选内容的位置以及其他地址栏数据将发送到你的默认搜索提供程序。  如果你的搜索提供商是必应，则会向你的浏览器提供唯一的 resettable 标识符，以了解搜索查询和查询会话。  其他面向服务标识符将发送到您的默认搜索引擎以完成搜索建议。  您的 IP 地址和 cookie 将发送到您的默认搜索提供商以增加搜索结果的相关性。  当你选择地址栏时，将向你的默认搜索提供程序发送信号，以通知提供商准备提供建议。  除非您的搜索提供商是必应，否则不会向 Microsoft 发送键入的字符和搜索查询。  如果你拥有打开的 "我的键入字符" 设置的 "**显示我的搜索和网站建议**"，则仅将此数据发送到默认搜索提供程序。  关闭该功能将使键入的字符停止发送到默认的搜索提供程序。  你的搜索查询仍将发送到你的默认搜索提供程序，以提供搜索结果。  如果 Microsoft Edge 检测到你在地址栏中键入内容可能包含敏感信息（如身份验证凭据、本地文件名或通常加密的 URL 数据），则不会发送键入的文本。  如果你已**通过发送崩溃报告和有关如何使用浏览器设置的数据来改进 microsoft 产品**，microsoft Edge 将收集有关地址栏的诊断数据，例如提供多少个查询，而与你的搜索提供商无关。  

击键和您访问的网站将存储在每个配置文件的设备本地。  您可以删除中的数据 `edge://settings/clearBrowserData` ，选中 "**浏览历史记录**" 复选框，然后选择 "**立即清除**"。  如果 "必应" 是你的默认搜索提供程序，并且你已登录到必应，你可以通过[Microsoft 隐私仪表板](https://account.microsoft.com/account/privacy?ref=privacy-edge-browse&ru=https%3A%2F%2Faccount.microsoft.com%2Fprivacy%2Fbrowse%3Fref%3Dprivacy-edge-browse&destrt=privacy-dashboard)删除搜索。  你可以清除中的浏览历史记录 `edge://history` ，以删除这些网站，使其在地址栏中显示为 "建议"。  在 Windows 10 上，你可以通过转到 "**开始**  >  **设置**  >  **隐私**  >  **诊断 \ & 反馈**"，然后在 "**删除诊断数据**" 下选择 "**删除**"，清除 Microsoft 从地址栏收集的数据和搜索建议功能。  所有其他数据将在36个月后删除。  

如果你使用 Microsoft 工作或学校帐户登录到 Microsoft Edge，并且可以使用 Microsoft Search，则会向该查询发送一个表示你的帐户的匿名令牌，以提供特定于你公司的特定于帐户的功能，例如特定于你的公司的结果。  

所有数据通过 HTTPS 进行安全传输。  如果 "[必应](https://bing.com)" 是你的默认搜索提供程序，则搜索和类型字符将保存多达6个月。  

如果在 "地址" 框中搜索单个字词，Microsoft Edge 可能会将单个单词发送到 DNS 服务器，以查看它是否对应于您的网络上的主机，并且可能会尝试连接到相应的主机。  这为你提供了导航到该主机的选项，而不是搜索。  例如，如果你的路由器按主机名进行操作， `router` 然后 `router` 在地址栏中键入，你将获得导航到的选项 `https://router/` ，以及 `router` 使用默认搜索提供程序搜索该单词。  此功能不受使用 "我的键入字符" 设置的 "**显示我的搜索和网站建议**" 的控制，因为它不涉及将数据发送到默认搜索引擎。  

可以使用 "键入的字符" 设置关闭 "**显示我的搜索和网站建议**" 设置，并在中更改默认搜索引擎 `edge://settings/search` 。  在浏览 InPrivate 或以来宾模式浏览时，autosuggestions 处于关闭状态。  InPrivate 显示来自本地浏览的建议，如浏览历史记录或过去的搜索，但不会向默认搜索引擎发送任何键入的字符。  来宾模式不会显示任何建议，也不会向你的默认搜索引擎发送键入的字符。  

其他搜索提供商收集的数据遵循公司的隐私策略。  

## 自动填充  

Microsoft Edge 中的自动填充可让你保存密码、支付信息、地址和其他表单输入数据，从而帮助你提高工作效率。  当您访问网站并开始填写表单时，Microsoft Edge 使用表单填写信息将已保存的自动填充数据与窗体相匹配。  Microsoft Edge 提供了您在遇到类似窗体时以前保存的表单输入数据。  密码和信用卡信息仅与你的每个密码和卡的显式权限一起保存。  

默认情况下，将保存地址和其他表单条目。  但是，你可能会在中关闭地址和其他表单数据的保存和自动填充 `edge://settings/addresses` 。  

通过关闭中的 "**保存密码**" 设置，防止 Microsoft Edge 提示您保存密码 `edge://settings/passwords` 。  如果你不希望 Microsoft Edge 自动填充现有保存的密码，你可以删除中保存的密码 `edge://settings/passwords` 以删除所有自动填充数据。请转到 Microsoft Edge 隐私和服务设置中的 "**清除浏览数据**" 设置。  选择 "自动**填充表单数据**"，选择所需的时间范围，然后**清除 "立即清除**"。  

如果你已为你的配置文件启用同步，则自动填充数据将在你登录到同一凭据的所有 Microsoft Edge 版本之间同步。  启用同步时，所有自动填充数据均存储在加密的 Microsoft 服务器上。  存储在 Microsoft 服务器上的自动填充数据仅用于同步用途。  你可以在中关闭自动填充数据的同步 `edge://settings/profiles/sync` 。  如果你为 "自动填充" 启用了同步，从你登录到 Microsoft Edge 的设备中删除自动填充数据将从你登录的其他设备中删除自动填充数据。  

当你访问网页并提交表单时，Microsoft Edge 会发送有关窗体的信息，例如主机名和自动填充条目类型的哈希值 \ （例如，box 1 正在查找电子邮件地址，框2正在查找密码，依此类推 \）到 Microsoft 表单填写服务。  不会向服务发送任何用户输入的信息或用户标识符。  此信息可帮助 Microsoft Edge 正确标识不同网页上的表单。  此数据用于帮助将保存的自动填充数据与窗体匹配。  

使用来宾模式时，自动填充不可用，并且不会添加新的自动填充条目。  浏览 InPrivate 时，Microsoft Edge 会提供自动填充条目，但不会添加新的自动填充条目。  

## Cast  

Microsoft Edge 中的 "强制转换" 允许您使用 Google Cast 将媒体显示到另一个屏幕。  你可以从 "设置"**和 "更多（...）**  >  " 中访问该功能**更多工具**  > **将媒体转换为设备**。  强制转换不使用任何 Microsoft 或 Google 服务。 

## 集锦  

您可以收集 web 上的网站、文本和图像，并在 Microsoft Edge 中用集合组织内容。  所有集合数据都存储在设备上，并按 Microsoft Edge 配置文件进行组织。  如果已为集合打开同步，则创建的集合（包括任何注释或注释）在所有登录和同步版本的 Microsoft Edge 中均可用。  

Microsoft Edge 每天24小时下载支持的网站的列表，其中存在特殊的实体提取模板。  模板特定于每个网站。  在你的集合中创建新项目时，Microsoft Edge 会验证你创建新集合项目的网站是否位于支持的网站列表中。  如果网站位于列表中，则 Microsoft Edge ping 特定网站模板的实体提取服务。  没有用户标识符与该服务的请求相关联。  此模板将尝试识别有关正在收集的项目的名称、价格、评分、主图像和其他数据。  如果您要从中创建新集合项的网站不在受支持的列表网站上，Microsoft Edge 不会下载模板。  模板允许在设备上本地创建所有集合项。  不会将有关集合项的数据发送到服务以创建集合。  

通过清除中的 "**清除浏览数据**" 设置下的缓存数据，可以删除设备上存储的模板 `edge://settings/privacy` 。

如果在 "集合" 中打开 "**显示 Pinterest 建议**"，则集合将使用你的集合的标题执行 Microsoft 必应搜索，以查找相关的 Pinterest 主题页面。  Microsoft Edge 不会将有关您的集合的数据发送到 Pinterest。  你可以通过转到 `edge://settings/privacy` 和关闭**集合中的 "显示建议**" 来删除建议并停止搜索 Pinterest 主题页面。  

使用 InPrivate 浏览或来宾模式时，集合不可用。  

## 崩溃  

如果启用了可选诊断数据（包括崩溃报告），Microsoft 将在 Microsoft Edge 崩溃或遇到其他可靠性问题时收集诊断数据。  此诊断数据用于诊断和修复 Microsoft Edge 和其他 Microsoft 产品和服务的可靠性问题。  

![崩溃](./media/whitepaper-media/crashes2.png)  

收集的诊断数据采用故障转储的形式，其中包含在 Microsoft Edge 遇到可靠性问题时捕获的设备和软件状态。  故障转储包含有关在可靠性问题时所发生的情况的信息。  诊断数据中可能包含您在崩溃时访问的网站或 CPU 使用率等信息。  崩溃诊断数据将存储在设备上，并在崩溃报告打开时使用加密的链接发送给 Microsoft。  每个崩溃转储都包含你的设备唯一的标识符、你的浏览器唯一的 resettable 标识符和额外的诊断数据 \ （如 URL、CPU 使用情况和网络使用情况 \）以帮助识别问题。  此额外的诊断数据将附加到故障转储，以帮助诊断可靠性问题，例如了解有多少设备遇到问题和严重性。  

故障转储将发送到 Microsoft 并存储在最多30天的安全的 Microsoft 服务器上，然后删除。  请求在 Windows 10 设备上删除诊断数据通过 "**开始**  >  **设置**  >  **隐私**  >  **诊断" & 反馈**，然后选择 "**删除诊断数据**" 设置下的 "**删除**"。  用于报告和产品改进的聚合崩溃信息（如出现的崩溃类型数）将存储。  

本地存储在设备上的崩溃诊断数据可能会从文件系统中清除 `edge://crashes` 。  

若要在 Windows 10 上关闭崩溃诊断数据收集，请转到**诊断 \ &** windows 诊断 \ & 反馈设置中的反馈。  对于所有其他平台上的 Microsoft Edge 版本，请转到 `edge://settings/privacy` "**通过发送崩溃报告和有关使用浏览器**设置的数据" 来关闭改进 Microsoft 产品。  也可以通过[您的组织管理的组策略](/deployedge/microsoft-edge-enterprise-privacy-settings)为企业关闭此诊断数据收集。  

## 有关如何使用浏览器的诊断数据  

Microsoft 使用诊断数据改进 Microsoft 产品和服务、保持 Microsoft 产品的安全和最新状态，并帮助更好地了解 Microsoft 产品的执行情况。当 Microsoft Edge 团队收集数据时，将验证决策是否适合你。  Microsoft 的 "相信" 和 "做法信息收集" 最佳做法。  Microsoft Edge 团队致力于仅收集所需的信息，并且仅在需要时才存储这些信息，以便改进 Microsoft 产品和服务。  

当你在 Microsoft Edge 和其他使用 Microsoft Edge web 平台的应用程序中使用功能和服务时，有关如何使用这些功能的诊断数据将发送给 Microsoft。  此诊断数据包括安装 Microsoft Edge、功能使用情况、性能和内存使用等信息。  例如，如果你喜欢某个网站，Microsoft Edge 团队将收到 "收藏夹" 按钮已被单击且已成功添加收藏夹的信息，但未将哪个网站设置为收藏项。  此诊断数据还包括性能信息，例如打开新选项卡所花的毫秒数。 白皮书中提及的功能和服务将收集诊断数据。  

![DiagnosticData](./media/whitepaper-media/diagnostic-data2.png)  

此外，Microsoft Edge 将收集一组必需的诊断数据，以使产品保持最新状态，确保产品安全并正常运行。  这包括设备连接和有关当前数据收集同意设置、应用版本和安装状态的配置信息。  您只能使用由您的组织管理的组策略关闭该设置。  [了解有关您的组织中的诊断数据的详细信息](/windows/privacy/configure-windows-diagnostic-data-in-your-organization)。  

Microsoft Edge 生成诊断数据，将其存储在本地，并定期将其发送给 Microsoft。  诊断数据使用 HTTPS 发送并存储在 Microsoft 服务器上。  此诊断数据与你的设备唯一的标识符以及你的浏览器唯一的 resettable 标识符相关联。  标识符不包含您的个人信息。  若要在 Windows 10 设备上重置你的浏览器独有的标识符，请转到 "**开始**  >  **设置**  >  **隐私**  >  **诊断" & 反馈**，然后在 "**删除诊断数据**" 设置下选择 "**删除**"，或将 "从**完整**到**基本**的**诊断数据**" 设置为 "  在其他平台上，每当您通过将 "**浏览器"** 设置 `edge://settings/privacy` 从 **"** 开始" 设置为 "**关闭**" 时，你的浏览器的数据都将再次生成你的浏览器特有的 resettable 标识符。  对于使用组织设置的组策略管理的设备，此重置功能可能会有所不同。  

如果你使用的是 Windows 10 版本 1803 \ （2018更新 \）或更高版本，你可以在诊断数据查看器中通过转到 "**开始**  >  **设置**  >  **隐私**  >  **诊断" & 反馈**，并选择 "**查看诊断数据**" 设置下的 "**打开诊断数据查看器**" 来查看与 Microsoft 共享的产品数据。  

对于低于版本1803的其他平台或 Windows 10 版本，请转到 `edge://data-viewer` 查看诊断数据。  数据将定期发送到 Microsoft，并且 `edge://data-viewer` 仅显示自上次打开查看器以来已发送给 microsoft 的数据。  你可能需要刷新查看器，以查看你的给定会话已向 Microsoft 发送了哪些数据。  用于填充的数据 `edge://data-viewer` 存储在设备上的本地。  若要清除查看器中的数据，只需关闭 `edge://data-viewer` 选项卡。  

诊断数据存储在 Microsoft 服务器上最多可达18个月。  在 Windows 10 中，你可以通过转到 " **Start**  >  **Settings**  >  **Privacy**  >  **删除诊断数据**" 设置下的 "开始设置隐私**诊断" & 反馈**，然后选择 "**删除**" 来删除诊断数据。  "删除诊断数据" 功能仅在 Windows 10 2018 更新和更高版本上受支持。  有关详细信息，请参阅[Windows 10 中的 "诊断"、"反馈" 和 "隐私"](https://support.microsoft.com/help/4468236/diagnostics-feedback-and-privacy-in-windows-10-microsoft-privacy)。  

对于 Windows 10 上的 Microsoft Edge，该设置由你的 Windows 诊断数据设置确定。  这会反映在 Microsoft Edge 隐私和服务设置中。  通过转到**启动**  >  **设置**  >  **隐私**  >  **诊断 \ & 反馈**来更改 Windows 设置。  在所有其他频道和平台上，你可以 `edge://settings/privacy` **通过发送崩溃报告以及有关如何使用浏览器设置的数据来**控制诊断数据收集并打开或关闭 "改进 Microsoft 产品"。  对于与你的设备上的 Microsoft Edge 安装相关联的所有配置文件，此设置是相同的。  此设置不会跨设备同步。  此设置适用于 InPrivate 浏览和来宾模式。  如果你的设备由你的组织设置的组策略管理，则会反映在中 `edge://settings/privacy` 。  

## 数字权利管理和媒体许可证  

当网站提供受数字权限管理保护的媒体内容 \ （DRM \）时，Microsoft Edge 使用安全的播放管道确保内容不会被正确复制或访问。  作为功能的一部分，Microsoft Edge 可能会在你的设备上存储与 DRM 相关的数据，包括唯一标识符和媒体许可证，并且可能会将该唯一标识符传输到内容提供商指定的媒体授权服务器。  使用该网站时，Microsoft Edge 将检索 DRM 信息，以确保你有权使用该内容。  此数据有助于验证对受保护内容的访问，并确保无缝媒体体验。  

Microsoft Edge 支持针对 HTML5 网站使用加密媒体扩展 API \ （EME API \）的 DRM。  EME API 允许网站与名为内容解密模块 \ （清洁 \）的 DRM 提供程序进行通信。  开发人员的清洁实现可能支持不同的 DRM 系统（如 Widevine 由 Microsoft 的 Google 或 PlayReady）。  内容提供商可以选择支持一个或多个可能的 DRM 系统，并且可以利用 EME API 的功能确定要用于特定客户端的 DRM 系统。  [了解有关 EME 隐私的详细信息](https://w3.org/TR/encrypted-media/#privacy)。  

Microsoft Edge 仅在 Windows 10 上支持 PlayReady DRM。  PlayReady 是一种 DRM 实现，可提供4K 视频和杜比 Atmos 音频等媒体体验。  Microsoft Edge 使用 Windows 平台媒体基础 Api 来支持 PlayReady。  为了验证对受保护内容的访问权限，Microsoft Edge 使用 Windows 10 操作系统，该操作系统使用唯一的标识符并通过 PlayReady 服务进行通信。  在设备上保留的 PlayReady 的所有 EME、清洁和浏览器数据将在 Microsoft Edge 上存储和维护。  [了解有关 PlayReady 的详细信息](/playready/overview/simple-end-to-end-system)。  

Microsoft Edge 支持使用 Google DRM 的 Widevine，默认情况下，此选项处于打开状态。  Microsoft Edge 定期从 Google server 获取 Widevine 的更新。  使用 Widevine 可能包括与 Google 的通信。  用户可以通过禁用 Microsoft Edge 中的 Widevine DRM 标志退出使用 Widevine `edge://flags/#edge-widevine-drm` 。  Widevine 具有创建唯一设备标识符并将其传输到 Google 的功能。  有关 Widevine 和隐私的更多特定信息，请参阅 Google 隐私策略。  

Microsoft Edge 支持由 Adobe 使用的 Flash Access DRM，由某些网站而不是 HTML5 使用。  你必须授予允许 Adobe Flash 在网站请求时允许 Adobe Flash 的权限。  当网站使用 Adobe 的 Flash Access DRM 时，Microsoft Edge 将为 Adobe 提供对唯一设备标识符的访问权限。  你可以在中清除和重置标识符的任何本地存储实例 `edge://settings/privacy` 。  在 "**清除浏览数据**" 下，选择 "**选择要清除的内容**"，选中 " **cookie 和其他网站数据**" 复选框，然后选择 "**立即清除**" 以删除任何存储的标识符。  停止在其中使用 Adobe Flash DRM `edge://settings/content/flash` 。  

当您请求对诸如联机电影之类的加密 HTML5 媒体的访问权限时，Microsoft Edge 会创建一个许可证请求来解密媒体。  正在使用的清洁将创建包含请求 ID 的许可证请求。  此请求将发送到许可证服务器。  许可证请求的任何部分均不包含任何个人身份信息，并且许可证请求未存储在设备上。  

当返回媒体许可证时，将创建一个媒体标识符，该标识符对用户和网站是唯一的。  此 ID 不会在网站之间共享，并且对于每个网站都是不同的。  用于标识播放会话的会话 ID 与媒体标识符一起发送，用于解密媒体。  媒体标识符存储在设备上的本地，并且可能与内容提供商存储在一起。  

所有 DRM 和内容保护均可在中关闭 `edge://settings/content/protectedContent` 。  

- 关闭 "**允许网站播放受保护的内容**" 设置将禁用基于清洁的 DRM 系统（如 PlayReady 和 Widevine）播放，但不适用于不基于清洁的系统（如 FLASH Access DRM）。  Flash 由中的单独网站权限管理 `edge://settings/content/flash` 。  关闭该设置会导致媒体功能停止正常工作。  
- 关闭 "**允许受保护内容的标识符**" 设置可阻止为 FLASH Access DRM 创建标识符，防止 Widevine 定期从 Google 提取更新。  这可能会导致某些网站上的某些媒体功能停止正常工作。  

## 请勿跟踪  

当您打开 **"发送时" 中的 "请勿跟踪" 请求**设置时 `edge://settings/privacy` ，Microsoft Edge 会向您的传出 http、HTTPS 和 SPDY 浏览流量请求发送一个 DNT： 1 http 标头，以请求每个网站不使用跟踪程序。  但是，打开 "不**跟踪" 请求**设置不能保证网站无法跟踪您。  某些网站可能会通过向你显示不基于任何以前浏览的广告来接受请求。  如果请求生效，Microsoft Edge 没有控制权。  若要帮助防止网站跟踪你，请将**跟踪防护**设置更改 `edge://settings/privacy` 为 "已**平衡**" 或 "**严格**"。  

使用来宾模式时，Microsoft Edge 不会发送 "不跟踪" 请求。  使用 InPrivate 浏览时，如果已为你正在使用的配置文件启用 "**不跟踪" 请求设置，** Microsoft Edge 将仅发送 "不要跟踪" 请求。  

## 下载  

Microsoft Edge 允许您安全、安全地下载文件。  你可以选择在设备上下载文件的位置 `edge://settings/downloads` 。  如果启用了 SmartScreen，有关文件（如文件名和 URL）的信息将发送到 SmartScreen 以检查文件的声誉。  这可帮助你避免意外下载已知的已知恶意软件，从而损害你的设备。  您可以打开或关闭 SmartScreen `edge://settings/privacy` 。  [了解有关 SmartScreen 的详细信息](#smartscreen)。  

可在中查看以前下载的历史记录 `edge://downloads` 。  在中清除浏览数据 `edge://settings/clearBrowserData` 可能会用于删除浏览数据，包括下载历史记录。  从 Microsoft Edge 删除下载历史记录不会从你的设备中删除文件。  从设备删除下载的文件不会从下载历史记录中删除文件。  当你使用 InPrivate 浏览或来宾模式时，当你关闭 InPrivate 或来宾窗口时，将清除该会话的下载历史记录，但文件会保存在设备上。  

## 扩展名和 Microsoft Edge 加载项  

你可以在 Microsoft Edge 中安装将功能添加到浏览器的扩展。  从 Microsoft Edge 加载项网站或其他扩展存储安装扩展时，Microsoft 会收集有关这些扩展的信息，以帮助开发人员和 Microsoft 了解如何使用该信息。  Microsoft Edge 收集聚合数据，包括扩展已下载的次数和有关其执行方式的信息，如崩溃数据。  Microsoft 与扩展的开发人员共享聚合数据。  来自用户的批注和评论在加载项网站上是公共的，并且也与开发人员共享。 如果你已登录到 Microsoft Edge，则已安装 Microsoft Edge 加载项网站中的扩展将与你的帐户相关联，并提供扩展建议。  此数据在聚合中用于了解扩展的普及程度。   

如果你在配置文件设置中启用了扩展的同步，则这些扩展的扩展和首选项将同步到 Microsoft Edge 的所有登录同步版本。   

安装扩展是可选的，并且可以随时通过 Microsoft Edge 卸载所有扩展 `edge://extensions` 。  当扩展已安装时，它指定需要访问的用户数据，并且 Microsoft Edge 要求在安装扩展之前提供权限。  在安装之前，请始终确保扩展是可靠且安全的，并查看该扩展的开发人员隐私策略。  

将使用 Microsoft Edge 更新服务更新扩展。  Microsoft Edge 将已安装的扩展列表发送到更新服务，以检查是否有更新可用。  如果您从 Chrome Web Store 安装扩展程序，请求将定期发送到 Chrome Web 应用商店，以检查扩展更新。  扩展标识符、扩展版本以及有关 Microsoft Edge 的信息包含在查找更新的请求中。  若要停止对 Chrome Web 应用商店的请求，请**从的 "其他来源**" 下卸载扩展 `edge://extensions` 。   

从其他浏览器导入扩展名（如 Google Chrome）时，如果 Microsoft Edge 加载项网站中有扩展可用，Microsoft Edge 会自动从 Microsoft Edge 加载项网站中安装扩展，并将其打开（如果你以前已启用了该扩展）。  如果在 Microsoft Edge 加载项网站中无法使用该扩展，Microsoft Edge 将从 Google Chrome 复制并安装您的扩展，而无需将其打开或连接到 Chrome Web Store。  Microsoft Edge 要求你允许打开该扩展并允许其他应用商店的扩展。  如果你授予权限，Microsoft Edge 允许从其他存储中安装扩展，并使用 Chrome Web Store 更新你的扩展。  您可以打开或关闭 "**允许来自其他应用商店的扩展**" `edge://extensions` 。

## 家庭安全  

Microsoft 提供了许多工具来帮助家庭保持连接，并使儿童在运行 Microsoft 启动器的 Windows 10、Xbox 和 Android 设备上更加安全。  

在家庭组中，在使用 Microsoft Edge 时，应该为儿童启用家庭设置。  家庭组组织者必须为组中的用户启用这些设置。  家庭组提供的三个主要功能是 web 筛选、活动报告和安全搜索。  

Web 筛选可防止家庭组中的儿童转到由家庭组织者特别阻止的成熟网站或网站。  

活动报告记录关于儿童访问的信息，以及搜索、屏幕时间、使用的设备和尝试访问阻止的网站。  家庭组组织者可能会在[family.microsoft.com](https://family.microsoft.com)处看到信息。  此数据在传输过程中进行收集、加密，并发送到 Microsoft 并存储在安全的 Microsoft 存储服务器上。  此数据是利用孩子的 Microsoft 帐户收集的，因此它可以管理。  活动报表存储在[family.microsoft.com](https://family.microsoft.com)上最多30天，然后删除。  

安全搜索向搜索引擎的标题请求添加安全的关键字。  必应读取 safe 关键字并筛选返回到子元素的搜索结果。  其他搜索引擎可能还会根据关键字返回经过筛选的结果。  将收集所有孩子的搜索并使其可供家庭组织者在活动报告或[family.microsoft.com](https://family.microsoft.com)中查看。  此数据是利用孩子的 Microsoft 帐户收集的，因此它可能会被正确管理。  

孩子的浏览数据存储在 Microsoft 安全的服务器上，并且在30天内可供家长使用，然后立即被删除。  可随时从[Microsoft 隐私仪表板](https://account.microsoft.com/account/privacy)中删除这些数据。  在设备上本地存储的浏览数据必须在中从 Microsoft Edge 中清除浏览数据 `edge://settings/clearBrowserData` 。  

孩子必须使用 Microsoft 帐户登录到 Windows 10，并且 "活动报告" 设置必须由 "家庭管理器" 打开，以便能够收集数据并与家庭组组织者共享。  不需要为数据集登录到 Microsoft Edge 的子数据。  如果家庭安全功能在你的 Windows 10 版本上不可用，你可以更新到最新版本的 Windows 来获取这些功能。  

如果启用了 web 筛选或活动报告功能，将禁用来宾模式和 InPrivate 浏览。  

家庭组组织者可能会停止家庭安全门户中的数据收集。  [了解有关 Microsoft 家庭安全功能的详细信息](https://support.microsoft.com/help/12413/microsoft-account-what-is-family-group)。  

## 反馈  

Microsoft Edge 团队将始终听取客户的价值并重视您的反馈。  若要在 Microsoft Edge 中提供反馈，请选择 "**设置" 和 "更多**  >  **帮助" 和 "反馈**"  >  **发送反馈**。  对于渐进式 Web 应用 \ （PWA \），请选择 "**设置" 和 "更多 ...**  >  "**向 Microsoft 发送反馈**。  您必须提供有关反馈的详细信息，但所有其他信息都是可选的。  如果从 Microsoft Edge 档案中检测到电子邮件，则会将其预填充到网站的当前 URL 以及相关诊断数据。  诊断数据可能包含有关已打开的功能以及浏览器使用情况的数据。  屏幕截图、设备中的文件以及浏览器的录制也可能也会包括在内。  您提供的可选附加录制可能包含个人身份信息。  此数据仅用于诊断和产品改进用途。  

用户反馈将使用 HTTPS 安全地发送到 Microsoft，并存储在安全的 Microsoft 服务器上。  如果你包含电子邮件地址，并且**通过发送崩溃报告以及有关在 Microsoft Edge 隐私设置中使用浏览器设置的数据来改进 microsoft 产品**，则你的设备上的浏览器安装所特有的标识符将与你的反馈相关联。  所有诊断数据（包括诊断日志、录制和附件）最多可存储30天。  剩余的反馈数据（包括可选屏幕截图）最多可存储15个月。  如果您提供了包含反馈项目的电子邮件，请发出删除反馈的[请求](https://www.microsoft.com/concern/privacy)。  

## 地理位置  

Microsoft Edge 支持[地理位置 API](https://w3.org/TR/geolocation-api)，该 API 允许网站使用你的权限访问你的位置信息。  网站可能会询问你的位置，例如，当你尝试查找你的 "柜咖啡店" 时。  Microsoft Edge 始终要求你提供权限，然后才能授予网站访问你的位置的权限。  若要管理权限或始终阻止网站访问您的位置，请转到 `edge://settings/content/location` 。  

在地址栏右侧，Microsoft Edge 指示您所在位置或未共享位置。  

![位置](./media/whitepaper-media/geolocation2.png)  

如果你允许与网站共享你的位置，Microsoft Edge 会将本地网络信息（如你的 IP 地址）和附近的 Wi-fi 访问点发送到 Microsoft 位置服务。  Microsoft 服务使用该信息估计地理位置坐标。  地理位置估计将与您同意与其共享您所在位置的网站共享。  在 Windows 10 上，如果打开 "**允许访问此设备上的位置**" 和 "**允许应用访问您**在**Windows**设置中的**位置**设置中的位置"，Microsoft Edge 将为网站提供更精确的位置。  如果关闭 "**允许访问此设备上的位置**" 和 "允许**应用访问您的位置**"，将向网站提供一个近似位置。  该信息仅与以前允许查看您所在位置的网站共享。  [Windows 位置设置](https://support.microsoft.com/help/4468240/windows-10-location-service-and-privacy)。  

当向 Microsoft location 服务发出请求时，将使用新的随机生成的 ID。  Microsoft Edge 位置服务不会在任何时间段内存储地理位置坐标。  

InPrivate 浏览使用启动 InPrivate 会话的配置文件的 "位置" 权限设置。  来宾模式将始终要求你提供权限，然后再向网站授予你的位置。  

## 导入浏览器数据  

第一次启动浏览器时，Microsoft Edge 提供交互式且无缝的体验。  作为体验的一部分，您可以选择将浏览器数据从另一个浏览器导入到 Microsoft Edge。  在导入体验过程中，你可能会保留导入的数据或将其删除并从头开始。  此数据包括你的收藏夹、浏览历史记录、自动填充数据、扩展、设置和其他浏览数据。  当你更新到新的 Microsoft Edge 时，将自动包含来自早期版本的 Microsoft Edge 的浏览数据。  通过你的确认，Microsoft Edge 从其他浏览器（如 Google Chrome、Mozilla Firefox 和 Internet Explorer）导入浏览器数据，并根据你的操作系统定义的最常用浏览器确定。  导入的数据全部在你的设备上本地完成，存储在本地，并且不会发送到 Microsoft，除非你同意同步浏览数据。  

![导入](./media/whitepaper-media/migration.png)  

从其他浏览器（如 Google Chrome）导入扩展时，Microsoft Edge 将导入一个本地副本，并在其处于打开状态之前要求权限。  某些扩展的权限可能已更改。  若要查看扩展权限，请转到 `edge://extensions` 。  

你可以随时从其他浏览器中选择导入数据 `edge://settings/importData` 。  

## 安装和更新  

你可以在 Windows 和 macOS 等平台上下载并安装 Microsoft Edge。  Microsoft Edge 使用更新服务使 Microsoft Edge 版本保持最新，并且安全。  

下载并安装 Microsoft Edge 时，有关设备的信息（如发布频道、基本硬件信息、更新标识符）在安装过程中将向 Microsoft 发送与你的设备唯一的标识符，以及你的浏览器特有的 resettable 标识符。  设备的 IP 地址已发送到更新服务，但最后一个小数位会被清理以增加隐私保护。  在每个浏览会话期间，将创建新的随机生成的令牌以安装 Microsoft Edge 的更新版本。  令牌不与任何个人信息相关联，并且仅用于安装和更新过程以及改进更新服务。  

Microsoft Edge ping Microsoft Edge 更新服务，了解安装和更新的各个阶段。  如果安装或更新失败，并且已启用故障报告，则会创建一个日志并将其发送给 Microsoft。  [了解如何将崩溃报告发送到 Microsoft](#crashes)。  Microsoft 将收集有关如何下载 Microsoft Edge、安装成功以及任何未安装以更好地了解 Microsoft Edge 下载成功的信息。  

默认情况下，所有 Microsoft Edge 用户都已启用自动更新。  在所有平台上，Microsoft Edge 会在启动时检查更新，并且在运行时定期检查更新。  在 MacOS 设备上，Microsoft 自动更新还会定期检查 Microsoft 产品的更新。  其他控件和配置可用于组织。  [了解有关其他控件和配置的详细信息](/deployedge/microsoft-edge-update-policies#update)。  

## Internet Explorer 模式  

Microsoft Edge 通过 Internet Explorer 的集成提供简化的体验 \ （IE \）。  Microsoft Edge 仅支持 IE 11 和 IE 模式，并且仅在 Windows 上可用。  此功能对组织通过组策略提供。  管理员选择在 Microsoft Edge 中打开 IE 模式下的网站列表。  

![位置](./media/whitepaper-media/ie-mode.png)  

Microsoft Edge 通过策略从管理员定义的位置下载网站列表，并缓存文件以确定必须在 IE 模式下打开的网站。  根据你的 Windows 或 IE 11 设置，Microsoft Edge 收集有关使用 IE 模式的诊断数据，例如用户访问的网站、性能数据、可靠性数据和功能使用数据。  在 Windows 10 上，诊断数据根据你的 Windows 诊断数据设置收集。  在 Windows 8.1 上，如果用户选择加入到 IE 中的 "先行翻转" 或 "推荐的网站" 功能，将收集网站信息。  IE 模式可能不遵循 Microsoft Edge 隐私和服务设置中相同的数据收集切换。  

如果你的管理员已启用企业网站发现，将收集浏览历史记录数据，以帮助管理员查看用户定期访问的网站，并确保任何系统升级继续支持这些网站。  [了解有关 IE11 中的企业网站发现的详细信息](/internet-explorer/ie11-deploy-guide/collect-data-using-enterprise-site-discovery)。  

Internet Explorer 浏览在本地存储在 Microsoft Edge 和 Internet Explorer 中。  此数据可能会从清除浏览数据中清除，并在中清除 Internet Explorer 的浏览数据 `edge://settings/privacy` 。  

## 侵入式广告  

为了提供更好的浏览体验，Microsoft Edge 提供广告阻止功能，防止广告在显示干扰或误导广告的网站上加载。  当广告阻止功能打开时，Microsoft Edge 会定期从 Microsoft 服务器下载最新的网站列表，显示有干扰或误导性广告，并将其存储在您的设备上的本地。  下载请求中不包含任何用户标识符。  如果你访问列表中的网站，Microsoft Edge 将阻止该网站上的所有广告，你应该会看到 "广告被阻止" 消息。  通过管理中的广告设置，允许网站上的广告 `edge://settings/content/ads` 。  除了下载具有侵入式广告的网站列表外，广告阻止功能不会向 Microsoft 发送其他信息，也不会在您浏览 web 时向 microsoft 请求其他信息。  

## 跳转列表  

Microsoft Edge 中的跳转列表让你可以通过右键单击任务栏中的 Microsoft Edge 图标轻松找到最近关闭的网站。  在本地为每个配置文件存储最后三个关闭的选项卡。  您可以在 "跳转列表" 中右键单击每个 Windows 10 中的网站，将其删除。  如果您不想在跳转列表中显示最近关闭的选项卡，则可以[清除浏览数据](https://support.microsoft.com/help/10607)或更改设置以在关闭浏览器时清除浏览数据。  使用 InPrivate 窗口时，Microsoft Edge 不会将已关闭的选项卡信息添加到跳转列表。  使用来宾模式时，跳转列表不可用。  

## 网络时间  

Microsoft Edge 使用 Microsoft 网络时间服务跟踪来自外部源（如时间服务器）的时间。  在随机时间间隔或 Microsoft Edge 遇到已过期的 SSL 证书时，Microsoft Edge 可能会向 Microsoft 发送请求以获取来自受信任源的时间。  如果 Microsoft Edge 检测到系统时钟不准确，这些请求会更频繁地发生。  如果用户更改了操作系统上的时间并与正确的时区冲突，则会发生这种情况。  Microsoft 网络时间服务用于获取协调世界时 \ （UTC \）。  这些请求不包含 cookie 或用户标识符，并且不记录任何数据。  

## 新建选项卡页  

Microsoft Edge 提供了一个具有吸引力且用户为中心的新选项卡页面体验，其中搜索框由[Bing.com](https://bing.com)、您最常访问的网站以及来自 Microsoft News 或 Office 365 的相关内容的快速链接磁贴所支持。  通过选择 "自定义" 按钮自定义新选项卡页的外观。  为每个配置文件设置新的选项卡页首选项，并将其存储在你的设备上，并且这些首选项不会在设备之间同步。  

![NTP](./media/whitepaper-media/n-t-p1.png)  

### Microsoft 新闻  

若要为你的交互和首选项定制内容，Microsoft Edge 中的 "新选项卡" 页面将 cookie 存储在设备上随机生成的标识符。  您的 IP 地址的 "已清理" 版本也用于将内容调整到您的常规区域。  Cookie 将一直保留在您的设备上，直到被清除 `edge://settings/siteData` 。  

通过转到 "Microsoft 隐私" 仪表板上的[广告设置](https://account.microsoft.com/privacy/ad-settings/signedout?ru=https:%2F%2Faccount.microsoft.com%2Fprivacy%2Fad-settings)，并关闭 "**在浏览器中查看个性化广告**" 设置，防止广告的个性化。  您也可以通过选择 "自**定义" 按钮**  >  **Custom** ，然后关闭 "**显示快速链接**" 设置来关闭快速链接图块。  Microsoft Edge 使用您的本地浏览历史记录对快速链接图块进行个性化设置，并且您可以删除或创建新磁贴。  此数据仅存储在设备上的每个配置文件中。  

"新建" 选项卡页面上的 "搜索" 框基于您键入的搜索查询执行必应搜索。  若要自动提供搜索建议和结果，Microsoft Edge 将与必应共享键入的字符、搜索查询、IP 地址和搜索标识符。  搜索框可能配置有组策略，以便从 Microsoft Search 中提供搜索结果，从而从您的组织（如文档和 intranet 内容）中返回信息。  为了提供集成的搜索体验，Microsoft Edge 将 cookie 存储在设备上本地。  

如果你已通过 Microsoft 帐户登录到 Microsoft Edge，你可以通过 " [Microsoft 隐私" 仪表板](https://account.microsoft.com/privacy/ad-settings/signedout?ru=https:%2F%2Faccount.microsoft.com%2Fprivacy%2Fad-settings)管理与新的选项卡页面关联的浏览活动。  

Microsoft Edge 将收集有关如何使用新选项卡页的诊断数据，例如，与搜索框的交互和单击快速链接图块，如果**通过发送崩溃报告以及有关如何使用浏览器设置的数据来改善 Microsoft 产品**，请打开 `edge://settings/privacy` 。  浏览器向 Microsoft 发送有关如何使用 Microsoft 新闻页面的诊断数据，以帮助我们了解用户与新闻内容的交互并改进 Microsoft 产品。  你可以通过选择 "新建" 选项卡页上的 "自定义" 按钮来关闭 Microsoft 新闻内容。  新闻数据将使用 HTTPS 发送到 Microsoft，并存储最多13个月，之后将被聚合并进行匿名。  

新的选项卡页还允许你将自定义图像设置为背景。  此图像存储在设备上的本地，并且可以通过删除映像或上载新图像来删除。  未向 Microsoft 发送有关图像的任何信息。  

### Office 365  

如果你使用工作或学校帐户登录到 Microsoft Edge，你的组织可能会在 "新建选项卡" 页上启用 Office 365 作为页面内容的选项。  此功能当前仅适用于商业客户，并且受[Microsoft Online Services 术语（OST）](https://www.microsoft.com/licensing/product-licensing/products)的制约。  [了解有关 Office 365 的隐私的详细信息](/deployoffice/privacy/overview-privacy-controls)。  

InPrivate 浏览和来宾模式提供了替代新的选项卡页体验。  

## 启动时  

Microsoft Edge 让你可以通过在上一个浏览会话中打开最后一个打开的选项卡来从离开的位置开始浏览。  如果你选择 "**继续**" 中的 "继续" `edge://settings/onStartup` ，则以前会话中的信息（包括会话 cookie）在启动时仍保持可用，可从以前的会话中还原选项卡，并使你登录到已访问的网站。  如果您在每次关闭浏览器时清除浏览数据，但选中了 "**继续**"，则您指定的数据将被删除，但 URL 将在下一个会话中保持。  

您也可以设置 Microsoft Edge 以在启动时打开特定页面。  你指定的页面存储在你的设备上，并且特定于配置文件。  如果在中打开 "设置同步" `edge://settings/profiles/sync` ，则指定的页面将在你登录的所有 Microsoft Edge 版本之间同步。  

启动时不会还原 InPrivate 和来宾选项卡。  

## 密码监视器
Microsoft Edge 承诺在 web 上保持安全。  为了帮助保护您的个人信息，如果您已登录到 Microsoft Edge，则密码监视器会在第三方数据破坏中看到您的凭据时向您发出警告。  如果密码监视器处于打开状态，则你保存的凭据将在你的设备上本地进行哈希处理和加密，并通过 HTTPS 发送到 Microsoft 服务器，并与已知破坏的凭据的加密列表进行比较。  你的登录帐户标识符与你的哈希和加密凭据一起被安全地发送到密码监视器服务。  如果在已知的被破坏的凭据列表中发现凭据，Microsoft 会将加密的响应发送回你的 Microsoft Edge 版本，以提醒你的凭据已检测为攻击或入侵的一部分。  检查完成后，Microsoft 服务器上不会存储任何数据。   

此功能仅适用于已登录到 Microsoft Edge 的用户。  Microsoft Edge 要求您提供打开密码监视器的权限。  若要打开或关闭 "密码监视器"，请转到 `edge://passwords` 。

## 付款  

Microsoft Edge 通过将您的付款信息保存到您的浏览器配置文件，并在浏览时使用信息自动填写付款表单，从而帮助您提高工作效率。  当您遇到类似的付款窗体时，Microsoft Edge 将使用保存的信息填写表单。  信用卡和其他支付信息仅通过您的明确权限保存。  

如果启用了付款自动填充，Microsoft Edge 会询问您是否要存储付款信息。  此信息在你的设备上本地加密。  您可以在中删除任何已保存的付款信息 `edge://settings/payments` 。  当您删除已保存的付款信息时，该信息不再显示为自动填充建议。  您可以选择不保存任何付款信息，方法是在中关闭该功能 `edge://settings/payments` 。  

Microsoft Edge 支持 PaymentRequest API，方法是使用以前使用 "自动填充" 保存的付款信息支付购买额。  PaymentRequest API 允许商家请求以下信息：信用卡号码、信用卡有效期、全名、帐单地址、电子邮件地址、电话号码和送货地址。  该 API 告知商家已保存了信用卡信息，但没有与商家共享任何信息，除非您同意。  您可以在中关闭该功能 `edge://settings/privacy` 。  

如果您以前已将付款信息保存到您的 Microsoft 帐户，则它也可用于浏览器中的自动填充。  存储在 Microsoft 帐户中的存储在所有设备上的付款信息。  如果你以前进行过任何 Xbox 或 Microsoft 应用商店购买，你可能已将付款信息保存到你的 Microsoft 帐户。  在付款自动填充期间，你的 Microsoft 帐户中的卡将被屏蔽，并且仅在两个因素身份验证后才完全暴露。  这将在检索付款信息时提供额外的安全性。  

## 个性化广告、搜索、新闻和其他 Microsoft 服务  

如果允许进行个性化设置，Microsoft Edge 团队将收集并使用 Microsoft Edge 浏览历史记录，以个性化体验 `Bing.com` 、Microsoft 新闻和其他 Microsoft 服务的体验和广告。  这将提供更多相关和有用的搜索结果、广告和新闻内容。  例如，如果 Microsoft Edge 团队根据你希望在特定商店购买的浏览方式推断出你所看到的广告，则可能会针对该商店中的产品定制你看到的广告。  同样，如果您经常查看旅行博客和阅读旅行文章，您的新闻源可能包含有关旅行的更多相关新闻内容。  
 
此功能仅适用于具有非子 Microsoft 帐户的用户。  对于使用工作帐户登录到 Microsoft Edge 的用户，此功能不可用。  

仅当满足所有四个条件时，才会收集和使用你的浏览历史记录来进行个性化设置：  

*   用户登录到非子 Microsoft 帐户   
*   用户已授予用于个性化的数据的收集和使用的权限。  
*   由组织管理的用户组策略 \ （雇主、学校等）允许进行个性化设置。  
*   用户未在来宾模式或 InPrivate 模式下使用浏览器。  

你的浏览历史记录和其他相关数据将通过 HTTPS 进行传输并附加到你的 Microsoft 帐户信息。  你的浏览历史记录存储在安全的 Microsoft 服务器上。  你可以转到[Microsoft 隐私声明仪表板](https://account.microsoft.com/account/privacy?ref=privacy-edge-browse&ru=https%3A%2F%2Faccount.microsoft.com%2Fprivacy%2Fbrowse%3Fref%3Dprivacy-edge-browse&destrt=privacy-dashboard)，查看和删除以前共享的浏览历史记录。  你的浏览历史记录存储在安全的 Microsoft 服务器上，最多可达45天。  45天后，数据被删除，并且不用于个性化。  

您可以从[Microsoft 隐私仪表板广告设置](https://account.microsoft.com/privacy/ad-settings/signedout?ru=https:%2F%2Faccount.microsoft.com%2Fprivacy%2Fad-settings)中修改您的兴趣或选择退出个性化广告。  

> [!NOTE]
> 在 Microsoft 隐私仪表板上退出个性化广告不会关闭浏览历史记录的收集和使用，以便对搜索结果和您的新闻源中的内容进行个性化设置。  若要关闭用于个性化搜索结果和新闻的 Microsoft Edge 浏览历史记录的收集和使用，请转到 `edge://settings/privacy` 并关闭 "**通过帐户中的浏览历史记录来增强 web 体验"，使 Microsoft 能够在 "个性化 web 体验" 下使用自定义广告、搜索、新闻和其他 Microsoft 服务**设置。 **Personalize your web experience**  如果停止共享数据，Microsoft 不再收集和使用浏览历史记录来个性化广告、搜索结果和新闻。  [了解有关 Microsoft Edge 中的个性化的详细信息](https://support.microsoft.com/help/4532583/microsoft-edge-browsing-history-personalized-advertising?ocid=EdgeUI-PersonalizedAds)。  

## 打印  

Microsoft Edge 允许你使用各种设备和应用程序打印网页、PDF 文件或其他内容。  当您打印到打印机、应用程序或 PDF 时，Microsoft Edge 会将命令和文件信息发送到设备的操作系统。  此信息不会发送给 Microsoft，并且在完成或取消打印后，发送到设备操作系统的所有数据将立即删除。  若要更改打印目标，请转到 `edge://settings/printing` 。  

您也可以使用 Microsoft "打印为 PDF" 将网页和文件打印为 PDF 格式，这不会将有关文件的任何数据发送回 Microsoft。  对 PDF 文件的任何注释都保存在本地文件中。  

## 配置文件  

Microsoft Edge 中的配置文件允许你将浏览数据分成独立的配置文件。  与其他配置文件关联的数据与一个配置文件相关联的数据分开。  例如，如果你在不同的配置文件中设置了你的个人收藏夹和历史记录，则不会与工作帐户同步。  

但是，用户可以轻松地在 Microsoft Edge 中的现有配置文件之间进行切换，而无需密码。  如果用户有权访问同一设备，则用户可以在同一版本的 Microsoft Edge 上创建另一个配置文件，而无需配置文件所有者的权限。  从 Microsoft Edge 设置中删除配置文件将永久删除存储在设备上的浏览数据，如浏览历史记录、收藏夹、表单填写数据和密码。  同步到你的帐户的数据可能仍然存储在 Microsoft 云中，并且可能会从[microsoft 隐私仪表板](https://support.microsoft.com/help/4532583/microsoft-edge-browsing-history-personalized-advertising?ocid=EdgeUI-PersonalizedAds)中清除。  

来宾模式是全新配置文件的临时实例。  它允许你在不修改登录配置文件的情况下在其他用户的设备上进行浏览。  在关闭所有来宾模式窗口后，从来宾模式（例如 "收藏夹"、"浏览历史记录"、"密码" 和 "表单填充数据"）浏览数据不会保留。  下载存储在设备上，但下载的历史记录已删除。  来宾模式允许你在不自动登录到其他网站的情况下浏览 web。  Microsoft Edge 不会向网站发送任何信息，以指示用户正在以来宾模式浏览。  使用来宾模式时，获取有关如何使用浏览器和你所访问的网站的诊断数据的权限来自启动来宾模式会话的 Microsoft Edge 的配置文件。  所有来宾窗口关闭后，将清除来宾模式会话的所有浏览数据。  

InPrivate 浏览是一种专用浏览模式，其中不会记住任何浏览历史记录、下载历史记录、cookie 和网站数据以及表单填充数据。  Microsoft Edge 将保存下载的文件，以及浏览 InPrivate 时创建的任何新收藏夹。  默认情况下，浏览 InPrivate 时，Microsoft 不会收集有关您所访问的网站的任何信息以供产品改进之用。  你的学校、工作场所或 internet 服务提供商可能仍然能够查看你的浏览活动。  关闭所有 InPrivate 窗口后，将清除该 InPrivate 会话的浏览数据。  使用 Windows 输入法编辑器（IME）键盘进行键入和墨迹书写时，可能会收集数据以改进语言识别和建议功能。  若要停止墨迹书写和键入由 Microsoft 使用 Windows IME 在 InPrivate 和普通浏览窗口中的数据，请转到 Windows 设置 > 隐私 > 墨迹书写 & 键入个性化。  [了解有关 InPrivate 浏览的详细信息](https://support.microsoft.com/help/4533513)。  
  

## 大声阅读  

Microsoft Edge 提供大声朗读，这将向用户阅读网页的内容。  从单击页面上的右键单击上下文菜单或转到 "**设置"，然后单击 "更多" （...）**   > 开始大声朗读 **大声阅读**。  大声朗读提供多个可用于阅读网页内容的语音。  如果在 Windows 10 的 " **& 语言**" 部分中使用[windows 10 上安装](https://support.office.com/article/download-voices-for-immersive-reader-read-mode-and-read-aloud-4c83a8d8-7486-42f7-8e46-2b0fdf753130)的语音，则以前使用过的任何声音都将存储在本地缓存中，并且可能会在中清除 `edge://settings/clearBrowserData` 。  

当您开始大声朗读时，Microsoft Edge 将使用[Web 语音 API](https://wicg.github.io/speech-api/)。  根据你选择的语音，使用平台提供的客户端库 \ （例如，特定于操作系统 \）或由 Microsoft 认知服务支持的服务器端库将页面内容从文本转换为语音。  如果使用客户端库将内容转换为语音，则不会向 Microsoft 服务器发送任何信息。  如果您的内容已使用 Microsoft 认知服务（由任何语音名称 \）中的单词 "Online" 转换为语音，则文本和随机生成的令牌将发送到 Microsoft。  转换完成后，服务会将音频文件中的口述文本返回到你的设备。  将所有数据从您的设备传输到 Microsoft 时进行加密，反之亦然。  发送给 Microsoft 的文本和生成的音频文件均会在转换后立即删除;在任何时间段内，不会存储有关您的 web 内容的其他数据。  

## 发布新功能  

为了改进 Microsoft Edge，Microsoft Edge 团队始终从用户处学习。  作为学习的一部分，某些用户在向所有人提供新功能之前可能会遇到新功能。  若要为随机选定的用户启用新功能，Microsoft Edge 会定期向 Microsoft Edge 配置服务发送有关你的操作系统、频道、版本、国家或地区以及其他设备配置数据的所需信息。  此数据将与你的浏览器独有的 resettable 标识符一起发送。  数据通过 HTTPS 传输到服务。  此数据用于接收更新以启用新功能、保持 Microsoft Edge 最新并正常运行以及改进 Microsoft 产品和服务。  其他控件和配置可用于组织。  [了解有关组织的其他控件和配置的详细信息](/deployedge/edge-configuration-and-experiments)。  

作为用户，你无法关闭由你的组织控制或配置的浏览器更新，但你可以控制你的产品使用数据是否已发送给 Microsoft `edge://settings/privacy` 并在 "**帮助改进 Microsoft Edge** " 设置下更改设置。  

若要了解新功能对 Microsoft Edge 和 Microsoft 服务有何影响，Microsoft Edge 将向你的浏览器提供唯一的 resettable 标识符和一个功能标记，用于对 Microsoft Edge 和 Microsoft 服务启用的新功能进行编码。  这有助于我们为每个人生成体验和最佳浏览器。  功能标记不是你的 Microsoft Edge 安装所特有的，并且在共享同一组启用功能的所有 Microsoft Edge 安装中共享。  Microsoft Edge 仅将 HTTPS 头中的信息发送到 Microsoft 服务。  浏览 InPrivate 或来宾模式时，浏览器不会发送页眉。  你可以 `edge://settings/privacy` **通过发送崩溃报告和有关如何使用浏览器设置的数据来**阻止发送数据并关闭改进 Microsoft 产品。  [了解如何重置你的浏览器独有的标识符](#diagnostic-data-about-how-you-use-the-browser)。  

## 解决导航错误  

如果 Microsoft Edge 检测到 SSL 连接超时、证书错误或其他可能由固定门户导致的网络问题 \ （例如，在旅馆或机场的 Wi-fi 网络），Microsoft Edge 会将请求发送到 `http://edge.microsoft.com/captiveportal/generate_204` 并检查响应代码。  如果请求被重定向到另一个 URL，Microsoft Edge 将在新选项卡中打开该 URL （假定它是登录页面）。  对 "捕获门户检测" 页面的请求是一种无状态服务，不会记录请求，也不会发送或保存 cookie。  在 Windows 平台上，Microsoft Edge 使用 Windows 固定门户服务。  否则，将使用 Microsoft Edge 捕获门户服务。  若要关闭服务，请转到 `edge://settings/privacy` 并关闭 "**使用 web 服务" 来帮助解决导航错误**设置。  

## 登录和标识  

登录 Microsoft Edge 提供了更多的功能，使浏览器更高效。  若要在首次启动 Microsoft Edge 时无缝登录，Microsoft Edge 团队会尝试从操作系统检测您的身份。  如果 Microsoft Edge 团队从操作系统检测到你的身份，但你不希望保持登录到 Microsoft Edge，请转到 Microsoft Edge 配置文件设置，然后注销或删除你的配置文件。  如果 Microsoft Edge 团队没有从操作系统中检测到您的身份，您可以从您的配置文件登录到 Microsoft Edge。  

如果将新标识添加到操作系统，而你的 Microsoft Edge 配置文件当前没有标识，Microsoft Edge 会将该标识添加到你的配置文件。  如果你使用 Microsoft 帐户或工作或学校帐户登录 Microsoft Edge，并且你的 Windows 10 配置文件上没有标识，则该帐户将添加到你的 Windows 10 配置文件，除非你在登录时特别选择不将其添加到 Windows 10。  

当你首次启动 Microsoft Edge 或登录浏览器时，你的登录配置文件不会开始同步你的数据，而无需你的显式权限。  

登录到 Microsoft Edge 可启用单一登录 \ （当您访问网站等网站时登录 `Bing.com\` ）和其他标识的支持（如同步）。 如果你希望仅登录到 Microsoft Edge，而不是其他 Microsoft 网站（如[Bing.com](https://bing.com)），则可以注销特定网站。  Microsoft Edge 团队创建一个注销 cookie，告诉 Microsoft Edge 不登录该站点以供将来访问。  你可以通过输入用户名和密码或从 Microsoft Edge 设置中清除 cookie，登录到该网站。  [了解有关清除浏览数据的详细信息](https://support.microsoft.com/help/10607)。  

若要阻止任何标识与 Microsoft Edge 相关联，请删除 Microsoft Edge 配置文件或注销 Microsoft Edge。  若要删除与你的设备上的 Microsoft Edge 配置文件关联的所有数据，必须删除你的 Microsoft Edge 配置文件。  删除所有数据不会删除以前同步的与该标识关联的数据。  

你在 MacOS 上的 Microsoft Edge 中的标识是在 Microsoft 应用之间共享的。  这使你可以登录到 Microsoft 应用，而无需单独输入你的凭据，如果你已登录到设备上的其他 Microsoft 应用。  在 MacOS 上，你不会根据你的身份验证状态在另一个 Microsoft 应用中自动登录到 Microsoft Edge。  当你尝试登录到 Microsoft Edge 时，Microsoft Edge 团队提供使用其他 Microsoft 应用的凭据来无缝登录到 Microsoft Edge。  同样，当你登录到 Microsoft Edge 时，如果你尝试登录到其他 Microsoft 应用，你的 Microsoft Edge 凭据可能会用于帮助你在设备上登录其他 Microsoft 应用，而无需再次输入你的凭据。  

使用来宾模式或 InPrivate 浏览时，你无法登录到 Microsoft Edge。  

## SmartScreen  

SmartScreen 旨在帮助您安全浏览 web。  转到网站或下载文件时，SmartScreen 会检查 URL 或文件的声誉。  如果 SmartScreen 确定网站或文件是恶意的，则会阻止你转到网站或下载文件。  

![SmartScreen](./media/whitepaper-media/smart-screen.png)  

浏览 web 时，SmartScreen 将网站和下载分类为热门流量、危险或未知。  热门流量是 SmartScreen 已确定的受信任站点。  如果您转到标记为危险的网站，则 SmartScreen 会立即阻止您访问该网站。  转到未知网站时，SmartScreen 会检查信誉，确定是否应访问该网站。  

SmartScreen 使用三种类型的信誉检查。  首先，SmartScreen 检查你访问的网站的 URL，以确定该网站是否属于热门流量或是否为已知危险的网站。  访问顶部流量网站时，SmartScreen 不会将 URL 发送到 SmartScreen 服务。  如果 URL 位于危险网站的本地列表中，则 SmartScreen 会阻止它，从而阻止加载恶意 web 内容的任何部分。  Microsoft Edge 定期将顶部流量和危险站点的更新列表下载到设备。  第二种类型的 URL 检查是对 SmartScreen 服务的异步信誉检查。  SmartScreen 对未分类为热门流量的所有 Url 执行检查。  Microsoft Edge 传递 URL、有关网站的相关信息、你的设备的唯一标识符和 SmartScreen 服务的常规位置以确定网站的安全。  这使服务能够识别新的危险站点并掌握最新的安全威胁。  URL 检查的结果存储在设备上的本地，并且会在浏览器会话结束时自动清除。  所有对 SmartScreen 服务的请求都通过 TLS 加密进行。  

第三，SmartScreen 检查下载的文件，以帮助防止损害你的设备。  下载完成后，SmartScreen 会同步执行二进制文件信誉检查。  Microsoft Edge 发送有关文件的信息，例如文件哈希、文件名、下载 URI 和设备特有的标识符被发送到 SmartScreen 以执行信誉检查。  所有 SmartScreen 请求都通过 TLS 加密进行。  SmartScreen 服务返回检查结果，该结果允许文件完全下载。  这些结果将本地存储在设备上。  

SmartScreen 服务存储有关信誉检查的数据，并构建已知恶意 Url 和文件的数据库。  此数据存储在安全的 Microsoft 服务器上，仅用于 Microsoft 安全服务。  此数据从不用于以任何方式标识或确定目标。  清除浏览缓存将清除本地存储的 SmartScreen URL 数据。  清除下载历史记录将删除任何本地存储的 SmartScreen 数据（有关文件下载）。  

默认情况下，将为 Microsoft Edge 启用 SmartScreen。  要关闭 SmartScreen，请在**Services**"  >  **Microsoft Defender SmartScreen** " 下的 "服务" 下 `edge://settings/privacy` 。  对于与你的设备上的 Microsoft Edge 安装相关联的所有配置文件，此设置是相同的。  此设置不会跨设备同步。  此设置适用于 InPrivate 浏览和来宾模式。  如果你的设备由你的组织设置的组策略管理，则该设置将反映在中 `edge://settings/privacy` 。  [了解有关 SmartScreen 的详细信息](https://support.microsoft.com/help/17443)。  

### 阻止可能有害的应用  

SmartScreen 会检查你下载的文件的 URL，以查看是否已将其分类为可能有害的应用。  阻止可能有害的应用可提供更高效、更具性能和 delightful 的 Windows 体验。  此设置默认情况下处于关闭状态，并且仅在 Windows 10 设备上可用。  你可以在中启用 "**阻止可能有害的应用**" 设置 `edge://settings/privacy` 。  了解如何[对可能有害的应用进行分类](/windows/security/threat-protection/intelligence/criteria#potentially-unwanted-application-pua)或如何[配置](/windows/security/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus)该设置。  

## 拼写检查  

当您在浏览器中键入时，Microsoft Edge 会检查您的拼写。  拼写检查服务在设备上本地完成-Microsoft Edge 不会将有关键入的信息发送到 Microsoft for 拼写检查。  您可以在中关闭拼写检查 `edge://settings/languages` 。  

将新语言添加到 Microsoft Edge 时，浏览器将使用 HTTPS 将新语言的词典下载到设备。  词典用于内置的拼写检查服务。  您也可以在中添加或删除本地词典中的单词 `edge://settings/languages` 。  从 Microsoft Edge 设置中删除语言将从设备中删除词典。  来宾模式不使用来自配置文件或任何添加的语言的自定义词典。  

## 建议类似网站  

为了帮助解决导致网站错误的地址栏中的 URL 拼写错误，Microsoft Edge 可能会推荐一个已更正的 URL。  当出现网站导航错误时，Microsoft Edge 会将 web 地址的域发送到 Microsoft 服务，以建议已更正的 URL。  Microsoft Edge 不包括标识符或域的标记。  如果服务发现建议，则返回建议的 URL。  Microsoft 存储不正确的域和建议的域以帮助改进服务。  为了帮助您导航到正确的网站，默认情况下该功能处于打开状态。  若要关闭该功能，请转到 `edge://settings/privacy` 并关闭 "当找不到网站时建议类似网站"。  

## 同步  

使用 Microsoft 帐户登录到 Microsoft Edge 后，您可以在所有登录的 Microsoft Edge 版本中同步浏览数据。  您可以同步您的 "收藏夹"、"设置"、"表单填写" 数据 \ （地址及更多 \）和密码。  必须允许在 Microsoft Edge 中打开同步的权限，并且每个同步的数据类型可能会单独打开或关闭。  "收藏夹" 包括你以前在旧版 Microsoft Edge 中保留的任何选项卡，并与你的常用联系人同步。  从 Microsoft Edge 的一个登录版本中删除或修改收藏夹以及其他数据类型到已打开同步的 Microsoft Edge 的所有其他登录版本。  可以在中管理同步配置 `edge://settings/profiles/sync` 。  

![同步](./media/whitepaper-media/sync.png)  

若要同步到函数，有其他设备连接和配置数据，如提供同步体验所必需的设备、型号和型号。  此数据可能会从[Microsoft 设备仪表板](https://account.microsoft.com/devices/)中删除。  您可以在中管理已同步的收藏夹 `edge://favorites` 。  所有其他数据类型均可通过 Microsoft Edge 配置文件设置进行管理 `edge://settings/profiles` 。  

在浏览器和 Microsoft 服务器之间传输时，所有已同步数据在通过 HTTPS 传输时进行加密。  已同步的数据也以加密状态存储在 Microsoft 服务器中。  敏感数据类型（如地址和密码）在同步之前将在设备上进一步加密。  如果你使用的是工作帐户，则会在使用 Microsoft 信息保护进行同步之前对所有数据类型进行进一步加密。  将存储所有其他已同步的数据类型，直到删除数据、删除帐户或帐户处于非活动状态。  帐户 ID 附加到所有已同步的数据，则该 ID 是在多个设备上执行同步所必需的。  

InPrivate 和来宾模式浏览数据不会同步到你的 Microsoft 帐户。  但是，在 InPrivate 会话期间创建的收藏夹将在已启用同步的 Microsoft Edge 的已登录版本之间同步。  

## 跟踪防护  

Microsoft Edge 旨在检测和阻止已知跟踪跟踪。  用户可以从三个级别的跟踪防护中进行选择： "基本"、"已平衡" 和 "严格"。  为保护用户的隐私，默认情况下，"已平衡" 处于选中状态。  Microsoft Edge 通过使用已知跟踪器的打开源列表，在页面上加载任意跟踪器之前检测跟踪器。  当列表更新时，此列表会定期下载到设备上。  被阻止的跟踪程序数和这些跟踪程序的名称将存储在设备上，以供统计之用。  此数据可能已在中清除 `edge://settings/privacy/blockedTrackers` 。  跟踪装置的检测和阻止在本地设备上进行。  您可能会在中关闭 "跟踪防护" `edge://settings/privacy` 。  [了解有关跟踪防护的详细信息](https://support.microsoft.com/help/4533959)。  

你可以使用组策略：[在 Microsoft Edge 中启用组件更新](/deployedge/microsoft-edge-policies#componentupdatesenabled)，关闭列表更新。  

![TrackingPrevention](./media/whitepaper-media/tracking-prevention.png)  

## 翻译  

在 Microsoft Edge 中，您可以浏览 web 并将网页翻译为所选语言。  内置翻译功能使用您的设备上的一项服务，该服务会让网页的随机部分检测原始语言。  如果检测到的语言不是默认语言之一，Microsoft Edge 会将该网页转换为您所显示的语言或您选择的其他语言。  Microsoft Edge 在没有您的许可的情况下不翻译网页。  您也可以通过右键单击页面并选择 "**翻译**" 来翻译网页。  若要翻译网页，Microsoft Edge 通过安全 SSL 连接将页面内容和随机生成的令牌发送到 Microsoft Azure 翻译服务。  出于任何目的，不会存储页面内容。  若要从产品中停止 Microsoft Edge 以翻译网页，请转到 `edge://settings/languages` 并关闭 **"提供" 以翻译您阅读的语言之外的页面**。  

## Web 应用和固定网站  

Microsoft Edge 允许你安装由网站开发人员创建的 web 应用，并固定你的收藏网站。  


固定网站时，它将添加到任务栏或停靠。  此数据存储在您的设备上本地存储。  对于某些网站，有关网站是否已固定的信息是否与网站共享，以便网站知道不会提示进行固定。  你可以从任务栏或 dock 管理已固定的网站。  已驻留的网站在 Microsoft Edge windows 中打开，并使用与你使用的浏览器和网站相同的网站权限和诊断数据作为该版本的 Microsoft Edge。  

## WebView

Microsoft Edge Web Edge 允许应用开发人员在 Windows 10 和 Windows 7 上的本机应用程序中托管 web 内容。  托管 Microsoft Edge web Edge 的应用程序可能会发送有关如何使用 Microsoft Edge web 平台和你在应用程序到 Microsoft 中访问的网站的诊断数据。  此诊断数据收集由你的帮助改进 Microsoft Edge 隐私和服务设置中的**Microsoft edge**设置确定。  若要在 Windows 10 上关闭 Microsoft Edge 的诊断数据收集，请转到 Windows 诊断数据设置。  若要为所有其他平台关闭诊断数据收集，请转到 `edge://settings/privacy` 正常浏览会话，然后**通过发送崩溃报告和有关如何使用浏览器的数据关闭改进 microsoft 产品**，并**通过发送有关在 Microsoft Edge 设置中访问的网站的信息来更好地进行搜索和 Microsoft 产品**。  托管 Microsoft Edge Web Edge 的应用程序可能会收集其他数据并包括开发人员和隐私策略的数据收集管理。  

## 您访问的用于产品和服务改进的网站  

如果您选择改进搜索和其他 Microsoft 产品和服务，Microsoft Edge 将发送有关您访问 Microsoft 的网站的信息。  此诊断数据用于聚合以改善所有用户的 Microsoft 产品和服务，并且不会与你的 Microsoft 帐户一起收集或存储。  发送有关您在 Microsoft Edge 中访问的网站的信息有助于我们了解网站的加载速度并提高搜索结果的相关性。  

此诊断数据包括你访问的页面的 URL、网站指标、页面的标题、访问页面的方式、有关页面内容的信息以及有关页面导航的其他相关信息。  某些诊断数据附加了你的设备独有的标识符。  否则，诊断数据与你的浏览器独有的 resettable 标识符相关联。  这些标识符不包含您的个人信息。  Microsoft Edge 团队通过限制数据访问和/或擦除个人身份信息来尊重诊断数据的灵敏度。  若要在 Windows 10 设备上重置你的浏览器独有的标识符，你可以在 "从**完整**到**基本**的**诊断数据**" 下更改设置。  在其他平台上，每当您**通过将您在 Microsoft Edge 设置中访问的网站的相关信息发送**到 "禁用" 时，您的浏览器特有的 resettable 标识符将再次生成 `edge://settings/privacy` 。 **on** **off**  对于使用组织设置的组策略管理的设备，此重置功能可能会有所不同。  

对于 Windows 10 上的 Microsoft Edge，该设置由你的 Windows 诊断数据设置确定。  这会反映在 Microsoft Edge 隐私和服务设置中。  你可以通过转到**启动**  >  **设置**  >  **隐私**  >  **诊断 \ & 反馈**来更改 Windows 设置。  在所有其他平台上，你可以 `edge://settings/privacy` **通过发送有关你在 Microsoft Edge 设置中访问的网站的信息**，在中控制诊断数据收集并打开或关闭更好的搜索和 Microsoft 产品。  对于与你的设备上的 Microsoft Edge 安装相关联的所有配置文件，此设置是相同的。  此设置不会跨设备同步。  如果你的设备由你的组织设置的组策略管理，则该设置将反映在中 `edge://settings/privacy` 。  

此诊断数据在传输过程中被加密，并以原始形式存储在最多30天的安全 Microsoft 服务器上。  诊断数据被取消识别和聚合，或者原始诊断数据被删除后。  已识别和聚合的诊断数据最多可存储2年，以继续改进 Microsoft 产品和服务。  由于不会从你的 Microsoft 帐户收集或存储诊断数据，因此可能无法从 Microsoft 隐私仪表板查看或删除诊断数据。  在 Windows 10 设备上，你可以请求删除与你的设备关联的诊断数据，方法是转到**开始**  >  **设置**  >  **隐私**  >  **诊断 \ & 反馈**，然后选择 "**删除诊断数据**" 下的 "**删除**"。  在其他平台上，诊断数据将被删除或完全聚合，并在30天内进行匿名处理。  

通过转到**启动**  >  **设置**  >  **隐私**  >  **诊断 \ & 反馈**  >  **查看诊断数据**，查看在 Windows 10 上使用诊断数据查看器收集的诊断数据。  在其他平台上， `edge://data-viewer` 如果打开**了 "通过发送有关 microsoft Edge 中所访问的网站的信息" 来更好地获得搜索和 Microsoft 产品**，则可以在其他平台上查看数据 `edge://settings/privacy` 。  

浏览 InPrivate 或来宾模式时，从不发送此诊断数据。  

## Windows Defender 应用程序防护  

Windows Defender 应用程序防护 \ （WDAG \）是适用于组织的功能。  当 Windows Defender 应用程序防护处于打开状态时，Microsoft Edge 将在隔离的容器内打开不受信任的网站，以保护组织中的资源免受恶意网站或网络钓鱼攻击。  此功能仅适用于由你的组织管理的组策略，并且仅适用于 Windows 10 设备的最新版本。  WDAG 收集有关在隔离的容器中打开不受信任的网站的产品改进诊断数据，例如打开新应用程序防护窗口所需的时间。  

有了你的权限，WDAG 还会收集有关如何使用浏览器的信息以及有关你所访问的网站的信息。  若要在 Windows 10 上关闭 Microsoft Edge 的诊断数据收集，请转到 Windows 诊断数据设置。  若要为所有其他平台关闭诊断数据收集，请转到 `edge://settings/privacy` 正常浏览会话，然后**通过发送崩溃报告和有关如何使用浏览器的数据关闭改进 microsoft 产品**，并**通过发送有关在 Microsoft Edge 设置中访问的网站的信息来更好地进行搜索和 Microsoft 产品**。  

## Windows 信息保护  

Windows 信息保护 \ （WIP）帮助防止意外泄漏公司信息。  它仅适用于组织通过您的组织管理的组策略。  对于标识为公司资产的那些站点，启用 WIP。  从 "地址栏" 中的 "管理" 图标确定哪些网站是公司资产。  WIP 强制执行某些功能，例如阻止从浏览器复制和粘贴或将某些文件上载到组织外部的网站。  

![发货](./media/whitepaper-media/w-i-p.png)  

如果你的 Microsoft Edge 版本启用了 WIP，该浏览器将收集事件日志，并将其发送给你的组织。  [了解有关由 WIP 捕获的事件日志的详细信息](/windows/security/information-protection/windows-information-protection/collect-wip-audit-event-logs)。  如果已启用 WIP，则无法选择退出数据收集。  WIP 仅适用于8月2016和更高版本的 Windows 10 版本。  

## 谢谢！  

Microsoft Edge 可通过[Chromium](https://www.chromium.org/)开放源代码项目和其他开放源代码软件进行 `edge://credits/` 。  [Google Chrome 的隐私白皮书](https://www.google.com/chrome/privacy/whitepaper.html)用作收集有关 Chromium open 源项目的相关信息的源。  

Microsoft Edge 承诺保护和尊重您的隐私，同时提供您所享有的透明度和控制。  通过转到[@MSEdgeDev](https://twitter.com/MSEdgeDev) "设置" 和 "**更多" （...）**  >  ，与 Twitter 上的 @MSEdgeDev 进行操作或提交反馈**帮助和反馈**  > 通过问题或意见**发送反馈**。  
