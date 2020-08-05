---
description: Microsoft Edge 隐私白皮书
title: Microsoft Edge 隐私白皮书
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/03/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: browser
keywords: microsoft edge, 隐私, 白皮书, 信任
ms.localizationpriority: high
no-loc:
- Cast
- Google Cast
ms.openlocfilehash: ff4d2b9a10e225478aaacbe0b70604a730172187
ms.sourcegitcommit: 01940d5708339b03debc14001596f560cc9ab75a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/03/2020
ms.locfileid: "10903871"
---
# Microsoft Edge 隐私白皮书  

我们的浏览器隐私政策旨在向你提供应获得的保护、透明度、控制权和尊重。  为保证 Microsoft 产品的透明度，Microsoft Edge 团队提供了隐私白皮书，该白皮书介绍 Microsoft Edge 功能和服务的工作原理，以及这些功能和服务可能对你的隐私产生的影响。  Microsoft Edge 团队的目标是让你全面了解如何使用数据、如何控制不同功能，以及如何管理已收集的数据，以便你拥有为你提供正确隐私决策所需的信息。  

在本文的某些部分中，Microsoft 团队提供了有关访问 Microsoft Edge 设置和其他页面的步骤。  为了保持一致性，Microsoft Edge 团队在整个白皮书中使用了简写格式：你应会看到以 `edge://` 开头的 URL，例如 `edge://favorites` 或 `edge://settings/privacy`。  若要转到页面，请直接在 Microsoft Edge 地址栏中输入粗体文本。  页面仅可在 Microsoft Edge 中查看。  

白皮书重点介绍 Microsoft Edge 的桌面版本，部分内容可能包含并非所有用户都可用的功能和体验。  此外，白皮书讨论了当前产品中存在的功能和服务，但将来可能会发生改变。  Microsoft 践行数据收集最小化，这意味着数据将在最短时间内保留，但保留时间可能因所用功能或服务而异，并且可能会随时间的推移而发生变化。  

## 地址栏和建议  

通过地址栏，可输入网站 URL 并搜索 Web。  默认情况下，地址栏使用输入的字符提供搜索和网站建议。  应会在收藏夹、浏览历史记录、以前的搜索和默认搜索提供程序中看到建议。  

:::image type="complex" source="./media/whitepaper-media/address-bar.png" alt-text="地址栏" lightbox="./media/whitepaper-media/address-bar.png":::
   地址栏  
:::image-end:::  

为了更快地浏览和搜索，在地址栏中输入内容时，会将输入的字符发送到你的默认搜索提供程序，搜索提供程序将发送回建议的搜索查询。  地址栏将输入分类为 URL、搜索或未知。  该信息以及所选的建议、选择位置和其他地址栏数据将发送到你的默认搜索提供程序。  如果你的搜索提供程序为必应，则浏览器所特有的可重置标识符会与数据一起发送，以了解搜索查询和查询会话。  其他自动建议服务标识符将发送到你的默认搜索引擎，以完成搜索建议。  将你的 IP 地址和 cookie 发送到你的默认搜索提供程序，以提高搜索结果的相关性。  当你选择地址栏向提供商发出通知以便其提供建议时，将向你的默认搜索提供程序发送信号。  输入的字符和搜索查询不会发送给 Microsoft，除非你的搜索提供程序是必应。  若要将数据发送到默认搜索提供程序，请转到 `edge://settings/privacy`，然后在“服务****”下，选择“地址栏****”，并启用“使用我输入的字符显示搜索和网站建议****”设置。  如果禁用此设置，则输入的字符将不再发送到默认搜索提供程序。  搜索查询仍将发送到默认搜索提供程序，以提供搜索结果。  如果 Microsoft Edge 检测到地址栏中的输入内容可能包含敏感信息（如身份验证凭据、本地文件名或通常加密的 URL 数据），则不会发送输入的文本。  如果你希望 Microsoft Edge 收集有关地址栏的诊断数据（包括所有搜索提供程序提供的查询数），请转到 `edge://settings/privacy`，在“个性化 Web 体验****”下，启用“通过允许 Microsoft 使用来自此帐户的浏览历史记录来个性化广告、搜索、资讯和其他 Microsoft 服务以改进 Web 体验****”设置。  

击键和你访问的网站将按配置文件本地存储在设备上。  若要删除数据，请转到 `edge://settings/clearBrowserData`，在“清除浏览数据****”窗口中，选中“浏览历史记录****”复选框，然后选择“立即清除****”按钮。  如果必应是你的默认搜索提供程序，并且你已登录必应，则可以通过“[Microsoft 隐私仪表板][MicrosoftAccountPrivacy]”删除搜索。  若要清除浏览历史记录，并删除地址栏中出现的建议网站，请转到 `edge://history`，然后选择“清除浏览数据****”。  若要清除 Microsoft 从 Windows 10 上的地址栏和搜索建议功能中收集的数据，请打开“开始****” > “设置****” > “隐私****” > “诊断和反馈****”，然后在“删除诊断数据****”下选择“删除****”。  所有其他数据将在 36 个月后删除。  

如果你使用 Microsoft 工作或学校帐户登录到 Microsoft Edge，并且可以使用 Microsoft 搜索，则会随查询发送代表你的帐户的匿名令牌，以提供帐户特定功能，例如特定于贵公司的结果。  

所有数据均通过 HTTPS 安全传输。  如果[必应][|::ref1::|Main]是默认搜索提供程序，则搜索和输入的字符最多保存 6 个月。  

如果你在地址框中搜索一个词，Microsoft Edge 可能会向 DNS 服务器发送这个词，确定它是否对应于网络上的某个主机，并且可能会尝试连接到相应的主机。  通过此选项可导航到特定主机，而不是搜索。  例如，如果你的路由器使用主机名 `router`，并且你在地址栏中输入 `router`，则可以选择导航到 `https://router`，也可以使用你的默认搜索提供程序搜索字词 `router`。  该功能不受“使用我输入的字符显示搜索和网站建议****”设置控制，因为它不会将数据发送到默认搜索引擎。  

启用（或禁用）将数据发送到默认搜索提供程序的另一种方法是，转到 `edge://settings/search`，然后启用（或禁用）“使用我输入的字符显示搜索和网站建议****”设置。  若要更改默认搜索引擎，请转到 `edge://settings/search`，然后选择“地址栏中使用的搜索引擎****”下拉菜单。  如果你在使用 InPrivate 或来宾模式时进行浏览，自动建议将处于禁用状态。  InPrivate 显示有关本地浏览的建议，如浏览历史记录或过去的搜索，但不向默认搜索引擎发送输入的字符。  来宾模式不会显示任何建议，或将输入的字符发送到默认搜索引擎。  

其他搜索提供程序收集的数据遵循公司的隐私策略。  

## 自动填充  

可使用 Microsoft Edge 中的自动填充来保存密码、支付信息、地址以及其他表单输入数据，从而帮助你提高工作效率。  当你访问网站并开始填写表单时，Microsoft Edge 使用表单填写信息将已保存的自动填充数据与表单进行匹配。  当你遇到类似的表单时，Microsoft Edge 会提供你以前保存的表单输入数据。  密码和信用卡信息仅通过你对每个密码和卡的显式权限进行保存。  

默认情况下，将保存地址和其他表单项。  若要禁用电子邮件地址和其他表单数据的保存和自动填充，请转到 `edge://settings/addresses`，然后禁用“保存和填充地址****”设置。  

若要防止 Microsoft Edge 提示你保存密码，请转到 `edge://settings/passwords`，然后禁用“让我选择保存密码****”设置。  如果不希望 Microsoft Edge 自动填充现有的已保存密码，并且想要删除保存的密码，请转到 `edge://settings/passwords`，然后选择“保存的密码****”。  若要删除所有自动填充数据，请转到 `edge://settings/clearBrowserData`，选择“自动填充表单数据****”，选择所需的时间范围，然后选择“立即清除****”。  

如果已为配置文件启用同步，则将在使用相同凭据登录的所有 Microsoft Edge 版本之间同步自动填充数据。  启用同步后，所有自动填充数据都存储在已加密的 Microsoft 服务器上。  存储在 Microsoft 服务器上的自动填充数据仅用于同步目的。  若要禁用同步自动填充数据，请转到 `edge://settings/profiles/sync` 并在“配置文件”旁选择“禁用同步****”按钮。  如果对自动填充启用了同步，则在登录到 Microsoft Edge 时删除设备中的自动填充数据的这一操作，将从使用同一帐户登录的所有其他设备中删除自动填充数据。  

访问网页并提交表单时，Microsoft Edge 将向 Microsoft 表单填充服务发送有关表单的信息，如主机名和自动填充条目类型的哈希值（例如，框 1 正在查找电子邮件地址，框 2 正在查找密码，依此类推）。  不会向服务发送用户输入的信息或用户标识符。  该信息可帮助 Microsoft Edge 正确识别不同网页上的表单。  数据用于帮助将已保存的自动填充数据与表单匹配。  

使用来宾模式时，自动填充不可用，并且不会添加新的自动填充项。  浏览 InPrivate 时，Microsoft Edge 将提供自动填充项，但不会添加新的自动填充项。  

## Cast  

Cast 在 Microsoft Edge 中，可使用 Google Cast 将媒体显示到另一个屏幕上。  若要访问 Cast 功能，请打开 “设置和更多(...)****” > “更多工具****”并选择“**Cast 媒体到设备**”。  Cast 依赖于默认情况下未包含在 Microsoft Edge 中的媒体路由器扩展。  第一次使用 Cast 时，Microsoft Edge 会提示你允许安装媒体路由器扩展。  

选择“重启****”，从 Chrome Web Store 安装媒体路由器扩展。  若要使媒体路由器扩展保持最新状态，在 Microsoft Edge 启动时，Microsoft Edge 要定期向 Chrome Web Store 发送更新请求，其中包含有关你的 Microsoft Edge 版本的基本数据。  Google 可能会收集一些与媒体路由器扩展相关联的数据。  若要卸载媒体路由器扩展，请转到 `edge://flags`，并禁用“Edge-On-Demand-Media-Router****”。  这也将停止来自 Chrome Web Store 的更新。  扩展已隐藏，且不会显示在“安装的扩展****”列表中。  有关“安装的扩展****”列表，请转到 `edge://extensions`。  

## 收藏  

可以收集 Web 上的网站、文本和图像，并使用 Microsoft Edge 中的“集合”来组织内容。  所有集合数据均本地存储在设备上，并按 Microsoft Edge 配置文件进行组织。  如果对集合启用了同步，则创建的集合（包括任何备注或注释）将在所有登录和同步版本的 Microsoft Edge 中可用。  

Microsoft Edge 每隔 24 小时下载一个支持的网站列表，其中存在特殊的实体提取模板。  这些模板特定于各个网站。  在集合中创建新项目时，Microsoft Edge 会验证创建新集合项的网站是否位于支持的网站列表中。  如果该网站位于列表中，Microsoft Edge 会对特定网站模板的实体提取服务执行 ping 操作。  没有用户标识符与服务请求相关联。  该模板尝试识别有关所收集项目的名称、价格、评级、主图像和其他数据。  如果你创建新集合项的网站不在受支持的网站列表上，则 Microsoft Edge 不会下载模板。  使用这些模板，可在设备本地创建所有集合项。  不会向服务发送关于集合项的数据来创建集合。  

若要删除存储在设备上的模板并清除缓存数据，请转到 `edge://settings/privacy`，在“清除浏览数据****”下的“立即清除浏览数据****”旁选中“选择要清除的内容****”按钮，选择所需的时间范围和数据类型，然后选择“立即清除****”按钮。  另一种删除缓存数据的方法是，转到 `edge://settings/clearBrowserData`，选择所需的时间范围和数据类型，然后选择“立即清除****”按钮。  

如果你想看到集合使用集合标题执行 Microsoft 必应搜索，来查找相关的 Pinterest 主题页面，则可以启用“在集合中显示 Pinterest 的建议****”设置。  Microsoft Edge 不会向 Pinterest 发送有关集合的数据。  若要删除建议并停止搜索 Pinterest 主题页面，请转到 `edge://settings/privacy`，然后禁用“在集合中显示 Pinterest 的建议****”设置。  

使用 InPrivate 浏览或处于来宾模式时，集合不可用。  

## 故障  

如果已启用可选的诊断数据（包括故障报告），则 Microsoft 将在 Microsoft Edge 故障或遇到其他可靠性问题时收集诊断数据。  诊断数据用于诊断和修复 Microsoft Edge 及其他 Microsoft 产品和服务的可靠性问题。  

:::image type="complex" source="./media/whitepaper-media/crashes2.png" alt-text="故障" lightbox="./media/whitepaper-media/crashes2.png":::
   故障  
:::image-end:::  

收集到的诊断数据采用故障转储形式，其中包含 Microsoft Edge 遇到可靠性问题时捕获的设备和软件状态。  故障转储包含有关在遇到可靠性问题时所发生的情况的信息。  诊断数据中可能包含在出现故障时正在访问的网站或 CPU 使用情况等信息。  故障报告处于启用状态时，故障诊断数据将本地存储在设备上并通过加密链接发送给 Microsoft。  每个故障转储都包含一个唯一的设备标识符、浏览器所特有的可重置标识符和额外的诊断数据（如 URL、CPU 使用情况和网络使用情况），帮助你识别问题。  额外的诊断数据附加到故障转储，以帮助诊断可靠性问题，如了解遇到问题的设备数和严重程度。  

故障转储将被发送到 Microsoft 并存储在安全的 Microsoft 服务器上长达 30 天，然后删除。  若要请求删除 Windows 10 设备上的诊断数据，请打开“开始****” > “设置****” > “隐私****” > “诊断和反馈 **”**，然后在“删除诊断数据**** 下选择“删除****”。  将存储聚合故障信息（例如发生故障的类型的计数）用于报告和产品改进。  

若要从设备的文件系统中清除本地存储的故障诊断数据，请转到 `edge://crashes`，然后选择“全部清除****”按钮。  

若要在 Windows 10 上禁用故障诊断数据收集，请打开“开始****” > “设置****” > “隐私****”并选择“诊断和反馈****”。  对于所有其他平台上的 Microsoft Edge 版本，请转到 `edge://settings/privacy`，然后禁用“通过发送故障报告和有关如何使用浏览器的数据来改进 Microsoft 产品****”设置。  企业也可以通过[组织管理的组策略][DeployedgeEnterprisePrivacySettings]来禁用诊断数据收集功能。  

## 开发人员工具

Microsoft Edge 开发人员工具提供用于网站调试和测试的工具。 若要访问开发人员工具，请打开“设置和更多(...)****” > “更多工具****”并选择“开发人员工具****”。  当你在开发人员工具中启用某些功能时，Microsoft Edge 将从 Microsoft 服务器请求模块并将其下载到你的设备。  发送的模块请求是通过安全的 HTTPS 连接进行的，并且包含表示正在使用的 Microsoft Edge 版本的非唯一标识符。  需要远程下载的特定体验包括“3D 视图”和“元素工具辅助功能”窗格。  Webhint 集成需要在打开开发人员工具时自动请求的远程模块。  

## 有关如何使用浏览器的诊断数据  

Microsoft 使用诊断数据来改进 Microsoft 产品和服务，确保 Microsoft 产品安全和保持最新状态，帮助更好地了解 Microsoft 产品的执行情况。 每次 Microsoft Edge 团队收集数据时，都会为你验证所做的决策是否是正确之选。  Microsoft 认可并践行信息收集最小化。  Microsoft Edge 团队致力于仅收集所需的信息，并只存储改进 Microsoft 产品和服务所需的信息。  

在 Microsoft Edge 中以及使用 Microsoft Edge Web 平台的其他应用程序中使用功能和服务时，有关如何使用这些功能的诊断数据将发送到 Microsoft。  诊断数据包括安装 Microsoft Edge、功能使用情况、性能和内存使用情况等信息。  例如，如果你收藏一个网站，Microsoft Edge 团队将收到信息“已单击收藏夹按钮并已成功添加收藏夹”，但不会将具体网站设置为收藏项。  诊断数据还包含性能信息，如打开新选项卡所需的毫秒数。白皮书中提及的功能和服务收集诊断数据。  

:::image type="complex" source="./media/whitepaper-media/diagnostic-data2.png" alt-text="诊断数据" lightbox="./media/whitepaper-media/diagnostic-data2.png":::
   诊断数据  
:::image-end:::  

此外，Microsoft Edge 还收集一系列必需的诊断数据，以确保产品保持最新状态、安全可靠且正常运行。  必需的诊断数据包括设备连接、有关当前数据收集许可设置的配置信息、应用版本和安装状态。  仅可使用组织管理的组策略禁用此设置。  有关组织中诊断数据的详细信息，请参阅[在组织中配置 Windows 诊断数据][WindowsPrivacyConfigureDiagnosticDataOrganization]。  

Microsoft Edge 生成诊断数据并将其存储在本地，并定期发送给 Microsoft。  诊断数据是使用 HTTPS 发送的，并存储在 Microsoft 服务器上。  诊断数据与设备特有的标识符以及浏览器特有的可重置标识符相关联。  标识符不包含你的个人信息。  若要在 Windows 10 设备上重置浏览器特有的标识符，请打开“开始****” > “设置****” > “隐私****” > “诊断和反馈****”，在“删除诊断数据****”下选择“删除****”，或将“**诊断数据**”下的设置从“完整****”更改为“基本****”。  在其他平台上，若要生成浏览器特有的新的可重置标识符 (ID)，请转到 `edge://settings/privacy`，然后禁用“通过发送有关如何使用浏览器的数据来改进 Microsoft 产品****”设置。  对于由组织设置的组策略管理的设备，重置 ID 功能可能有所不同。  

若要查看在 Windows 10 版本 1803 \（2018 年 4 月更新\）或更高版本上诊断数据查看器中与 Microsoft 共享的产品数据，请转到“开始****” > “设置****” > “隐私****” > “诊断和反馈****”，然后在“查看诊断数据****”下选择“打开诊断数据查看器****”。  

对于其他平台或 Windows 10 版本 1803 及更低版本，若要查看诊断数据，请转到 `edge://data-viewer`。  若要查看自上次打开查看器后定期发送到 Microsoft 的数据，请转到 `edge://data-viewer`。  若要查看特定会话的哪些数据发送到 Microsoft，请刷新查看器。  用于填充 `edge://data-viewer` 的数据本地存储在设备上。  若要清除查看器中的数据，请关闭 `edge://data-viewer` 选项卡。  

诊断数据存储在 Microsoft 服务器上，最长可保留 18 个月。  若要删除 Windows 10 上的诊断数据，请打开“开始****” > “设置****” > “隐私****” > “诊断和反馈****”，然后在“删除诊断数据****”下，选择“删除****”。  仅 Windows 10 版本 1803 或更高版本支持删除诊断数据功能。  有关详细信息，请参阅 [Windows 10 中的诊断、反馈和隐私][MicrosoftSupport4468236]。  

对于 Windows 10 上的 Microsoft Edge，“通过发送有关如何使用浏览器的数据来改进 Microsoft 产品****”设置取决于你的 Windows 诊断数据设置。  若要查看设置的状态，请转到 `edge://settings/privacy`。  若要更改 Windows 设置，请打开“开始****” > “设置****” > “隐私****”并选择“诊断和反馈****”。  在控制诊断数据收集的所有其他平台上，转到 `edge://settings/privacy`，然后禁用“通过发送故障报告和有关如何使用浏览器的数据来改进 Microsoft 产品****”设置。  该设置用于与设备上安装 Microsoft Edge 相关联的所有配置文件。  此设置不会跨设备同步。  此设置适用于 InPrivate 浏览和来宾模式。  若要查看设备是否是由组织设置的组策略管理的，请转到 `edge://settings/privacy`。  

## 数字版权管理和媒体许可证  

当网站提供受数字版权管理 (DRM) 保护的媒体内容时，Microsoft Edge 将使用安全播放管道来确保不会复制或不当访问内容。  作为功能的一部分，Microsoft Edge 可能会在设备上存储与 DRM 相关的数据，包括唯一标识符和媒体许可证，并可能将唯一标识符传输到内容提供商指定的媒体许可服务器。  使用该网站时，Microsoft Edge 将检索 DRM 信息，确保你有权使用该内容。  数据可帮助验证对受保护内容的访问权限，并确保无缝媒体体验。  

Microsoft Edge 支持使用适用于 HTML5 网站的加密媒体扩展 API (EME API) 的 DRM。  EME API 允许网站与名为“内容解密模块 (CDM)”的 DRM 提供商进行通信。  开发人员的 CDM 实施可能支持其他 DRM 系统（例如，Google 的 Widevine 或 Microsoft 的 PlayReady）。  内容提供商可以选择支持一个或多个可能的 DRM 系统，并且可以利用 EME API 的功能来决定要用于特定客户端的 DRM 系统。  有关 EME 隐私的详细信息，请参阅[加密媒体扩展隐私][W3cEncryptedMediaPrivacy]。  

Microsoft Edge 仅支持 Windows 10 上的 PlayReady DRM。  PlayReady 是一种 DRM 实现，可提供 4K 视频和 Dolby Atmos 音频等媒体体验。  Microsoft Edge 使用 Windows 平台媒体基础 API 来支持 PlayReady。  为了验证对受保护的内容的访问权限，Microsoft Edge 利用 Windows 10 操作系统，该操作系统使用唯一的标识符 (ID)，并通过 PlayReady 服务传达 ID。  在设备上持久保存的 PlayReady 的所有 EME、CDM 和浏览器数据都将存储在 Microsoft Edge 中并保留。  有关 PlayReady 的详细信息，请参阅[简易端到端系统][PlayreadyOverviewSimpleEndSystem]。  

Microsoft Edge 支持 Google DRM 的 Widevine，默认情况下，此选项处于启用状态。  Microsoft Edge 定期从 Google 服务器获取 Widevine 更新。  使用 Widevine 可能包括与 Google 的通信。  若要选择退出使用 Microsoft Edge 中的 Widevine，请转到 `edge://flags/#edge-widevine-drm` 并禁用 Widevine DRM 设置。  Widevine 可创建唯一的设备标识符并将其传输到 Google。  有关 Widevine 和隐私的更多详细信息，请参阅 Google 隐私策略。  

Microsoft Edge 支持 Adobe 的 Flash Access DRM，由某些网站使用，而不是由 HTML5 使用。  当网站请求 Adobe Flash 时，你必须给予许可。  当网站使用 Adobe 的 Flash Access DRM 时，Microsoft Edge 将为 Adobe 提供对唯一设备标识符的访问权限。  若要清除并重置任何本地存储的标识符实例，请转到 `edge://settings/privacy`，并在“清除浏览数据****”下选择“选择要清除的内容****”，选中“Cookie 和其他网站数据****”复选框，然后选择“立即清除****”以删除任何存储的标识符。  若要阻止使用 Adobe Flash DRM，请转到 `edge://settings/content/flash`。  

当你请求访问加密的 HTML5 媒体（如在线影片）时，Microsoft Edge 将创建许可证请求来解密媒体。  正在使用的 CDM 将创建包含请求 ID 的许可证请求。  请求将发送到许可证服务器。  许可证请求的任何部分均不包含任何个人身份信息，并且许可证请求不存储在设备上。  

返回媒体许可证时，将创建一个媒体标识符，该标识符是用户和网站所特有的。  ID 不在网站之间共享，并且因每个网站而异。  用于识别播放会话的会话 ID 将与媒体标识符一起发送，用于解密媒体。  媒体标识符本地存储在设备上，可随内容提供商一起存储。  

若要禁用所有 DRM 和内容保护，请转到 `edge://settings/content/protectedContent`，然后禁用“允许网站播放受保护的内容(建议)****”和“允许对受保护的内容使用标识符(可能需要重启计算机)****”设置。  

*   禁用“允许网站播放受保护的内容****”设置将禁用基于 CDM 的 DRM 系统的播放（例如 PlayReady 和 Widevine），而不是针对 Flash Access DRM 之类的并非基于 CDM 的系统。  若要管理 Flash 网站权限，请转到 `edge://settings/content/flash`。  禁用该设置将导致媒体功能停止正常工作。  
*   禁用“允许对受保护的内容使用标识符****”设置将阻止为 Flash Access DRM 创建标识符，并阻止 Widevine 定期提取 Google 中的更新。  禁用该设置可能会导致某些网站上的某些媒体功能停止正常工作。  

## 禁止跟踪  

若要在 Microsoft Edge 上启用“禁止跟踪****”，请转到 `edge://settings/privacy` 并启用“发送‘禁止跟踪’请求****”设置。  如果启用“禁止跟踪****”功能，Microsoft Edge 将向你访问的网站发送一个 DNT:1 HTTP 头，其中包含你即将发送的 HTTP、HTTPS 和 SPDY 浏览流量请求，以请求它们不要使用跟踪器。  但是，启用“发送‘禁止跟踪’请求****”设置并不能保证网站无法跟踪你。  某些网站可能会通过向你显示非以前浏览过的广告来接受请求。  Microsoft Edge 不控制是否接受请求。  若要帮助防止网站跟踪你，请转到 `edge://settings/privacy`，将“跟踪防护****”设置更改为“平衡****”或“严格****”。  

使用来宾模式时，Microsoft Edge 不会发送“**禁止跟踪**”请求。  使用 InPrivate 浏览时，如果为正在使用的配置文件启用了“发送‘禁止跟踪’请求****”设置，则 Microsoft Edge 仅发送“禁止跟踪****”请求。  

## 下载  

借助 Microsoft Edge，可安全可靠地下载文件。  若要选择在设备上下载文件的位置，请转到 `edge://settings/downloads`。  如果启用了 SmartScreen，有关文件的信息（如文件名和 URL）将发送到 SmartScreen，以检查文件的信誉。  信誉检查可帮助你避免意外下载会损害设备的已知恶意软件。  若要启用\（或禁用\）SmartScreen，请转到 `edge://settings/privacy` 并启用\（或禁用\）SmartScreen。  有关 SmartScreen 的详细信息，请参阅 [SmartScreen](#smartscreen) 部分。  

若要查看先前下载的历史记录，请转到 `edge://downloads`。  若要清除浏览数据并删除下载历史记录，请转到 `edge://settings/clearBrowserData`。  从 Microsoft Edge 中删除下载历史记录不会删除设备中的文件。  从设备中删除下载的文件不会从下载历史记录中删除文件。  使用 InPrivate 浏览或来宾模式时，当你关闭 InPrivate 或来宾窗口时，会话中的下载历史记录将被清除，但文件会保存在设备上。  

## 扩展和 Microsoft Edge 加载项  

可在 Microsoft Edge 中安装扩展，向浏览器添加功能。  从 Microsoft Edge 加载项网站或其他扩展存储中安装扩展时，Microsoft 会收集扩展信息，帮助开发人员和 Microsoft 了解如何使用扩展。  Microsoft Edge 收集聚合数据，包括扩展的下载次数和有关其执行方式的信息（如故障数据）。  Microsoft 将与扩展的开发人员共享聚合数据。  来自用户的评论和意见在加载项网站上是公开的，并且也会与开发人员共享。 如果你已登录到 Microsoft Edge，则 Microsoft Edge 加载项网站中安装的扩展将与你的帐户相关联，以提供扩展建议。  该数据用于汇总以了解扩展的普及程度。   

如果你希望扩展和扩展首选项可在所有登录的 Microsoft Edge 同步版本之间同步，请转到 `edge://settings/profiles/sync`，然后选择“启用同步****”按钮。   

安装扩展是可选的，若要在任何时候卸载任何扩展，请转到 `edge://extensions`。  安装扩展后，它指定需要访问的用户数据，并且 Microsoft Edge 会在安装扩展之前请求许可。  安装之前，请务必确保扩展可靠且安全，并检查开发人员针对特定扩展的隐私策略。  

扩展使用 Microsoft Edge 更新服务进行更新。  Microsoft Edge 将已安装的扩展列表发送到更新服务，以检查是否有可用的更新。  如果安装 Chrome Web Store 中的扩展，请求将定期发送到 Chrome Web Store，以检查扩展更新。  扩展标识符、扩展版本和有关 Microsoft Edge 的信息包含在查找更新的请求中。  若要停止向 Chrome Web Sore 发送请求，请转到 `edge://extensions`，在“从其他源****”下卸载扩展。  

在导入其他浏览器（如 Google Chrome）中的扩展时，如果 Microsoft Edge 加载项网站中有可用的扩展，则 Microsoft Edge 会自动安装 Microsoft Edge 加载项网站中的扩展，如果你以前启用了此扩展，则会将其打开。  如果 Microsoft Edge 加载项网站中不提供扩展，则 Microsoft Edge 将本地复制和安装 Google Chrome 的扩展，而无需将其打开或连接到 Chrome Web Store。  Microsoft Edge 需要你的许可才能启用该扩展，并允许启用其他存储中的扩展。  如果你已授予权限，则 Microsoft Edge 将允许安装其他存储中的扩展，并使用 Chrome Web Store 来更新你的扩展。  若要启用（或禁用）该选项，请转到 `edge://extensions` 并启用（或禁用）“允许其他存储中的扩展****”设置。

## 家庭安全  

Microsoft 提供了多种工具来帮助家庭成员保持联系，并确保孩子在使用运行微软桌面的 Windows 10、Xbox 和 Android 设备时更加安全。  

在家庭组中，使用 Microsoft Edge 时应为孩子启用家庭设置。  家庭组组织者必须为组中的用户启用设置。  为家庭组提供的三个主要功能是“Web 筛选”、“活动报告”和“安全搜索”。  

Web 筛选可防止家庭组中的孩子访问成人网站或由家庭组织者专门屏蔽的网站。  

“活动报告”记录有关孩子访问的网站的信息，以及搜索、屏幕时间、使用的设备和尝试访问阻止的网站。  家庭组组织者可以在 [family.microsoft.com][MicrosoftAccountFamilyMain] 上看到信息。  数据将被收集到，在传输中加密，发送到 Microsoft 并存储在安全的 Microsoft 存储服务器上。  这些数据是通过孩子的 Microsoft 帐户收集的，因此可以妥善管理。  活动报告存储在 [family.microsoft.com][MicrosoftAccountFamilyMain] 上长达 30 天，之后会将其删除。  

“安全搜索”可向搜索引擎的头请求添加安全关键字。  必应读取安全关键字，并筛选返回给孩子的搜索结果。  其他搜索引擎还可能返回因关键字而生成的筛选结果。  将收集孩子搜索的所有数据，并供家庭组织者在活动报告或 [family.microsoft.com][MicrosoftAccountFamilyMain] 中查看。  这些数据是通过孩子的 Microsoft 帐户收集的，因此可以妥善管理。  

孩子的浏览数据存储在安全的 Microsoft 服务器上，可供家长在 30 天内查看，然后会立即删除。  可随时从“[Microsoft 隐私仪表板][MicrosoftAccountPrivacy]”中删除数据。  若要清除在设备本地存储的浏览数据，请转到 `edge://settings/clearBrowserData`。  

孩子必须使用 Microsoft 帐户登录到 Windows 10，并且必须由家庭组织者启用“活动报告”设置，以便能够收集数据并与家庭组组织者共享。  无需孩子登录 Microsoft Edge 即可收集数据。  如果家庭安全功能在你的 Windows 10 版本中不可用，你可以更新到最新版本的 Windows 来获得这些功能。  

如果启用了 Web 筛选或活动报告功能，则来宾模式和 InPrivate 浏览将被禁用。  

家庭组组织者可能会停止从家庭安全门户中收集数据。  有关 Microsoft 家庭安全功能的详细信息，请参阅[什么是 Microsoft 家庭组？][MicrosoftSupport12413]  

## 地理位置  

Microsoft Edge 支持 [地理位置 API][W3cGeolocationApiMain]，这允许网站在你的允许下访问你的位置信息。  网站可能会询问你的位置，例如，在尝试查找离你最近的咖啡店时。  在允许网站访问你的位置之前，Microsoft Edge 会始终征求你的许可。  若要管理权限或始终阻止网站访问你所在的位置，请转到 `edge://settings/content/location`。  

在地址栏右侧，Microsoft Edge 指示什么情况下共享/不共享你的位置。  

:::image type="complex" source="./media/whitepaper-media/geolocation2.png" alt-text="位置" lightbox="./media/whitepaper-media/geolocation2.png":::
   位置  
:::image-end:::  

如果你允许与网站共享你的位置，Microsoft Edge 会将本地网络信息（如 IP 地址和临近 Wi-Fi 接入点）发送给 Microsoft 位置服务。  Microsoft 服务使用该信息来估计你的地理位置坐标。  地理位置估计与你同意与其共享位置的网站共享。  若要指定 Microsoft Edge 向请求网站提供 Windows 10 上更精确的位置，请打开“设置****” > “隐私****” > “位置****”，然后启用“允许访问此设备上的位置****”和“允许应用访问你的位置****”设置。  如果禁用“允许访问此设备上的位置****”和“允许应用访问你的位置****”设置，Microsoft Edge 将提供指向请求网站的近似位置。  此信息仅与请求网站共享，前提是你以前允许其查看你的位置。  有关 Windows 位置设置的详细信息，请参阅 [Windows 10 位置服务和隐私][MicrosoftSupport4468240]。  

请求 Microsoft Edge 位置服务时，将使用随机生成的新 ID。  Microsoft Edge 位置服务不会存储任何时段的地理位置坐标。  

InPrivate 浏览使用启动 InPrivate 会话的配置文件中的位置权限设置。  在授予网站访问你的位置之前，来宾模式将始终征求你的同意。  

## 导入浏览器数据  

第一次启动浏览器时，Microsoft Edge 将提供交互式无缝体验。  作为体验的一部分，可选择将浏览器数据从其他浏览器导入到 Microsoft Edge。  在导入过程中，你可能会保留导入的数据，或者将其删除并重新开始。  数据包括收藏夹、浏览历史记录、自动填充数据、扩展、设置以及其他浏览数据。  更新到新的 Microsoft Edge 时，将自动导入旧版本 Microsoft Edge 中的浏览数据。  确认后，Microsoft Edge 将从其他浏览器导入浏览器数据（如 Google Chrome、Mozilla Firefox 或 Internet Explorer），并根据你的 OS 定义的最常用浏览器确定从中导入数据的浏览器。  导入数据全部在设备本地完成，并存储在本地，且不会发送到 Microsoft，除非你同意同步浏览数据。  

:::image type="complex" source="./media/whitepaper-media/migration.png" alt-text="Import" lightbox="./media/whitepaper-media/migration.png":::
   Import  
:::image-end:::  

从其他浏览器（如 Google Chrome）中导入扩展时，Microsoft Edge 会导入一个本地副本，如果该扩展在 Microsoft Edge 加载项网站上不可用，则需要获得许可才可打开。  某些扩展的权限可能已更改。  若要查看扩展权限，请转到 `edge://extensions`。  

若要随时导入其他浏览器中的数据，请转到 `edge://settings/importData`。  

## 安装和更新  

可在 Windows 和 macOS 等平台上下载和安装 Microsoft Edge。  Microsoft Edge 使用更新服务使 Microsoft Edge 版本处于最新状态，并确保安全。  

下载和安装 Microsoft Edge 时，将在安装过程中向 Microsoft 发送设备相关信息（如发布频道、基本硬件信息、更新标识符、设备特有的标识符，以及浏览器所特有的可重置标识符）。  设备的 IP 地址将发送到更新服务，但会清除最后一个数字来增强隐私保护。  在每个浏览会话过程中，将创建一个随机生成的新令牌来安装 Microsoft Edge 的更新版本。  令牌不与任何个人信息相关联，仅用于安装和更新过程以及改进更新服务。  

Microsoft Edge 就安装和更新进度对 Microsoft Edge 更新服务执行 ping 操作。  如果安装或更新失败，并且启用了故障报告，则会创建一个日志并发送到 Microsoft。  有关向 Microsoft 发送故障报告的详细信息，请参阅[故障](#crashes)部分。  Microsoft 收集有关 Microsoft Edge 的下载方式、成功安装以及任何卸载的信息，以便更好地理解如何成功下载 Microsoft Edge。  

默认情况下，所有 Microsoft Edge 用户都会启用自动更新。  在所有平台上，Microsoft Edge 都会在启动时和运行时定期检查更新。  在 MacOS 设备上，Microsoft AutoUpdate 还会定期检查 Microsoft 产品的更新。  组织还可以使用其他控制和配置。  有关其他控制和配置的详细信息，请参阅[更新][DeployedgeUpdatePoliciesUpdate]。  

## Internet Explorer 模式  

Microsoft Edge 通过 Internet Explorer (IE) 集成简化了体验。  Microsoft Edge 仅支持 IE 11，而 IE 模式仅在 Windows 上可用。  通过组策略，组织可以使用 IE 模式功能。  管理员选择在 Microsoft Edge 的 IE 模式下打开特定网站。  

:::image type="complex" source="./media/whitepaper-media/ie-mode.png" alt-text="IE 模式" lightbox="./media/whitepaper-media/ie-mode.png":::
   IE 模式  
:::image-end:::  

Microsoft Edge 通过策略从管理员定义的位置下载网站列表，并缓存确定必须以 IE 模式打开的网站的文件。  根据 Windows 或 IE 11 设置，Microsoft Edge 会收集有关 IE 模式使用情况的诊断数据，如用户访问的网站、性能数据、可靠性数据和功能使用情况数据。  在 Windows 10 上，将根据 Windows 诊断数据设置收集诊断数据。  在 Windows 8.1 中，如果用户选择使用 IE 中的“快速翻页”或“建议的网站”功能，则会收集网站信息。  IE 模式可能不会遵循 Microsoft Edge 隐私设置中的相同数据收集设置。  

如果你的管理员已启用“企业网站发现”，将定期收集浏览历史记录数据，以帮助管理员查看用户访问的网站，并确保任何系统升级继续支持这些网站。  有关 IE11 中“企业网站发现”功能的详细信息，请参阅[使用企业网站发现收集数据][InternetExplorer11DeployGuideCollectDataEnterpriseSiteDiscovery]。  

Windows 设备上的非企业用户也可以访问 IE 模式。  若要启用 IE 模式，请转到 `edge://settings/defaultBrowser`，然后选择“允许在 Internet Explorer 模式下重新加载网站****”设置。  若要打开 IE 模式下的选项卡，请打开“设置和更多(...)****” > “更多工具****”并选择“在 Internet Explorer 模式下重新加载****”。  启用 IE 模式后，Microsoft Edge 会定期从 Microsoft 服务请求不受支持的网站的列表。  请求是通过 HTTPS 发送的，且不包含任何标识符。  

Internet Explorer 浏览数据本地存储在 Microsoft Edge 和 Internet Explorer 中。  若要在 IE 模式下浏览时删除浏览数据，请转到 `edge://settings/privacy`，并从“清除浏览数据****”和“清除 Internet Explorer 的浏览数据****”中清除数据。  


## 侵入式广告  

为了提供更好的浏览体验，Microsoft Edge 将阻止在显示侵入性或误导性广告的网站上加载广告。  启用“广告屏蔽”后，Microsoft Edge 将定期从 Microsoft 服务器下载显示有侵入性或误导性广告的最新网站列表，并存储在设备本地。  下载请求中不包含任何用户标识符。  如果访问列表上的网站，Microsoft Edge 会阻止该网站上的所有广告，并且你会看到 `Ads blocked` 消息。  为获得网站广告，请转到 `edge://settings/content/ads` 并更改设置。  除了下载具有侵入式广告的网站列表之外，“广告屏蔽”功能不会向 Microsoft 发送其他信息，也不会在你浏览网站时向 Microsoft 请求其他信息。  

## 跳转列表  

使用 Microsoft Edge 中的“跳转列表”，你可以通过将鼠标悬停在任务栏中的 Microsoft Edge 图标上并打开上下文菜单\（右键单击\）轻松找到最近关闭的网站。  为每个配置文件本地存储最后三个关闭的选项卡。  若要从 Windows 10 的“跳转列表”中删除网站，请将鼠标悬停在每个网站上并打开上下文菜单 \（右键单击 \）。  若要清除或更改跳转列表中最近关闭的选项卡的显示，请转到 `edge://settings/privacy`，然后选择“选择每次关闭浏览器时要清除的内容****”设置。  使用 InPrivate 窗口时，Microsoft Edge 不会将关闭的选项卡信息添加到“跳转列表”。  使用来宾模式时，“跳转列表”不可用。  有关清除浏览数据的详细信息，请参阅[查看和删除 Microsoft Edge 中的浏览器历史记录][MicrosoftSupport10607]。  

## 网络时间  

Microsoft Edge 使用 Microsoft 网络时间服务来跟踪来自外部源（如时间服务器）的时间。  通过随机间隔或当 Microsoft Edge 遇到过期的 SSL 证书时，Microsoft Edge 可能会向 Microsoft 发送请求，以获取来自受信任源的时间。  如果 Microsoft Edge 检测到系统时钟不准确，将会更频繁地发出请求。  如果用户更改了操作系统上的时间且该时间与正确时区相冲突，则会导致系统时钟不准确。  Microsoft 网络时间服务用于获取协调世界时 (UTC)。  请求中不包含 cookie 或用户标识符，并且不会记录任何数据。  

## “新建选项卡”页面  

Microsoft Edge 提供了具有吸引力且以用户为中心的新选项卡页面体验，其中包括由[必应][|::ref2::|Main]提供支持的搜索框、最常访问网站的快速链接磁贴和来自 Microsoft 资讯或 Office 365 的相关内容。  选择“自定义”按钮来自定义新选项卡页面的外观。  将为每个配置文件设置新的选项卡页面首选项，并将其本地存储在设备上，而不会跨设备同步这些首选项。  

:::image type="complex" source="./media/whitepaper-media/n-t-p1.png" alt-text="“新建选项卡”页面" lightbox="./media/whitepaper-media/n-t-p1.png":::
   “新建选项卡”页面  
:::image-end:::  

### Microsoft 资讯  

为了根据用户的交互和偏好定制内容，Microsoft Edge 中的“新建选项卡”页面会在设备上使用随机生成的标识符存储 cookie。  还会使用你的 IP 地址的精制版本，来根据你的通用区域定制内容。  若要清除设备上保留的 cookie，请转到 `edge://settings/siteData`。  

若要防止广告个性化，请转到“[Microsoft 隐私仪表板][MicrosoftAccountPrivacy]”上的“[广告设置][MicrosoftAccountPrivacyAdSettings]”，然后禁用“在浏览器中查看个性化广告****”设置。  若要禁用快速链接磁贴，请打开“自定义按钮****” > “自定义****，禁用“显示快速链接****”设置。  Microsoft Edge 使用本地浏览历史记录对快速链接磁贴进行个性化设置，你可以删除或新建磁贴。  根据配置文件，数据只是本地存储在设备上。  

“新建选项卡”页面上的搜索框根据输入的搜索查询执行必应搜索。  若要自动提供搜索建议和结果，Microsoft Edge 可与必应共享输入的字符、搜索查询、IP 地址和搜索标识符。  搜索框可能配置了组策略来提供 Microsoft 搜索中的搜索结果，进而返回来自贵组织的信息，如文档和 Intranet 内容。  为了提供集成搜索体验，Microsoft Edge 将在设备上本地存储 cookie。  

如果你已使用 Microsoft 帐户登录到 Microsoft Edge，可以从“[Microsoft 隐私仪表板][MicrosoftAccountPrivacyAdSettings]”管理与“新建选项卡”页面相关联的浏览活动。  

Microsoft Edge 收集有关如何使用新选项卡页的诊断数据，如与搜索框的交互以及单击快速链接磁贴的情况。  要启用有关如何使用新选项卡页的诊断数据的收集，请转到 `edge://settings/privacy`，然后启用“通过发送故障报告和有关如何使用浏览器的数据来改进 Microsoft 产品****”设置。  浏览器将有关如何使用“Microsoft 资讯”页面的诊断数据发送到 Microsoft，以帮助了解用户与资讯内容的交互并改进 Microsoft 产品。  可通过选择“新建选项卡”页面上的“自定义”按钮来禁用“Microsoft 资讯内容”。  资讯数据通过 HTTPS 发送到 Microsoft，并保存长达 13 个月，之后会被聚合并进行匿名处理。  

通过“新建选项卡”页面，你还可以将自定义图像设置为背景。  图像本地存储在设备上，可通过删除图像或上传新图像进行删除。  不会向 Microsoft 发送有关图像的任何信息。  

### Office 365  

如果你使用工作或学校帐户登录到 Microsoft Edge，则你的组织可能会在“新建选项卡”页面上启用 Office 365 作为页面内容的选项。  此功能目前仅适用于商业客户，并受到 [Microsoft 在线服务条款 (OST)][MicrosoftLicensingProductProducts] 的制约。  有关 Office 365 隐私的详细信息，请参阅 [Microsoft 365 企业应用版的隐私控制概述][DeployedgePrivacyOverviewControls]。  

InPrivate 浏览和来宾模式提供了备选“新建选项卡”页面体验。  

## 启动时  

Microsoft Edge 通过打开上一个浏览会话中的上次打开的选项卡（包括会话 cookie），使你可以从上次离开的位置继续浏览，并在启动时仍可用，以便从上次会话中还原选项卡，并使你在访问过的网站上保持登录状态。  若要启用打开上一个浏览会话中的上次打开的选项卡，请转到 `edge://settings/onStartup` 并启用“从上次离开的位置继续**Continue where you left off**”设置。  如果你选择“从上次离开的位置继续****”设置并在每次关闭浏览器时清除浏览数据，则将删除你指定的数据，但该 URL 会保留到下一次会话。  

你还可以设置 Microsoft Edge，以便在启动时打开特定页面。  指定的页面本地存储在设备上，并特定于配置文件。  如果启用了设置同步，指定的页面将同步到你登录的所有 Microsoft Edge 版本。  若要启用同步你的设置，请转到 `edge://settings/profiles/sync` 并启用“设置****”设置。  

启动时不会还原 InPrivate 和来宾模式选项卡。  

## 密码监视器
Microsoft Edge 致力于保证你在 Web 上的安全性。  为了帮助保护你个人信息的隐私和安全，如果你登录到了 Microsoft Edge，密码监视器会在第三方数据泄露你的凭据时提醒你。  如果启用了密码监视器，则已保存的凭据将在你的设备上进行本地哈希和加密，然后通过 HTTPS 发送到 Microsoft 服务器，并与已知泄露凭据的加密列表进行比较。  将登录帐户标识符与哈希和加密凭据一起安全发送到密码监视器服务。  如果在已知的泄露凭据列表中发现凭据，Microsoft 将向你的 Microsoft Edge 版本发送加密响应，提醒在黑客入侵或泄露过程检测到你的凭据。  检查完成后，Microsoft 服务器上不会存储任何数据。   

该功能仅适用于已登录到 Microsoft Edge 的用户。  Microsoft Edge 要求你提供启用密码监视器的权限。  若要启用\（或禁用\）“密码监视器”，请转到 `edge://passwords`。

## 付款  

通过 Microsoft Edge，你可以将付款信息保存到你的浏览器配置文件，以及在你浏览时根据需要使用信息自动填充付款表单，从而帮助你提高工作效率。  遇到类似付款表单时，Microsoft Edge 将使用保存的信息填写表单。  信用卡和其他付款信息仅通过显式权限保存。  

如果启用了付款自动填充功能，则 Microsoft Edge 会询问你是否要存储付款信息。  将在你的设备上本地加密此信息。  若要删除保存的付款信息，请转到 `edge://settings/payments`。  删除保存的付款信息后，该信息不再显示为自动填充建议。  若要不保存任何付款信息，请转到 `edge://settings/payments`，然后关闭该功能。  

Microsoft Edge 支持 PaymentRequest API，方法是让你用之前使用自动填充保存的付款信息在购买时付款。  PaymentRequest API 允许商家请求以下信息：信用卡号码、信用卡到期日、全名、帐单邮寄地址、电子邮件地址、电话号码和送货地址。  该 API 告诉商家用户已保存信用卡信息，但在用户同意前，不会与商家共享任何信息。  若要关闭“付款”功能，请转到 `edge://settings/privacy`。  

如果你以前将付款信息保存到你的 Microsoft 帐户，也可在浏览器中自动填充。  存储在 Microsoft 帐户中的付款信息将跨设备同步。  如果你以前在任何 Xbox 或 Microsoft Store 进行了购买，则可能已将付款信息保存到 Microsoft 帐户。  在付款自动填充过程中，来自 Microsoft 帐户的信用卡将使用掩码，并且仅在双因素身份验证后才完全显示。  掩码在检索付款信息时提供额外的安全性。  

## 个性化广告、搜索、资讯和其他 Microsoft 服务  

如果你允许个性化，Microsoft Edge 团队会收集并使用你的 Microsoft Edge 浏览历史记录，以便对[必应][|::ref3::|Main]、Microsoft 资讯和其他 Microsoft 服务的体验和广告进行个性化设置。  个性化设置提供了更为相关且有用的搜索结果、广告和资讯内容。  例如，如果 Microsoft Edge 团队根据你的浏览情况推断出你喜欢在某个商店购物，则你看到的广告可能是根据特定商店中的产品定制的。  类似地，如果经常查看旅行博客和阅读旅行文章，你的新闻源可能包含更多旅行相关的资讯内容。  
 
该功能仅适用于具有非 Microsoft 子帐户的用户。  对于使用工作或学校帐户登录到 Microsoft Edge 的用户，此功能不可用。  

只有在满足以下四个条件时，才会收集浏览历史记录，并将其用于个性化设置：  

*   用户已登录到非 Microsoft 子帐户。 
*   用户已授予收集和使用数据进行个性化设置的权限。  
*   由组织管理的用户组策略（雇主、学校等）允许进行个性化设置。  
*   用户未在来宾模式或 InPrivate 中使用浏览器。  

浏览历史记录和其他相关数据将通过 HTTPS 传输并附加到你的 Microsoft 帐户信息。  浏览历史记录存储在安全的 Microsoft 服务器上。  可通过“[Microsoft 隐私仪表板][MicrosoftAccountPrivacy]”查看和删除以前共享的浏览历史记录。  浏览历史记录存储在安全的 Microsoft 服务器上长达 45 天。  45 天后，数据将被删除，且不用于个性化设置。  

可从“[Microsoft 隐私仪表板][MicrosoftAccountPrivacy]”上的“[广告设置][MicrosoftAccountPrivacyAdSettings]”中修改兴趣或选择退出个性化广告。  

> [!NOTE]
> 选择退出“[Microsoft 隐私仪表板][MicrosoftAccountPrivacy]”上的个性化广告，不会禁用对个性化搜索结果和新闻源内容的浏览历史记录的收集和使用。  如要禁用收集和使用 Microsoft Edge 浏览历史记录来个性化搜索结果和资讯，请转到 `edge://settings/privacy`，在“个性化 Web 体验****”下，禁用“通过允许 Microsoft 使用来自此帐户的浏览历史记录来个性化广告、搜索、资讯和其他 Microsoft 服务以改进 Web 体验****”设置。  如果停止共享数据，Microsoft 将不再收集和使用你的浏览历史记录来个性化广告、搜索结果和资讯。 有关 Microsoft Edge 中的个性化设置的详细信息，请参阅[用于个性化广告和体验的 Microsoft Edge 浏览历史记录][MicrosoftSupport4532583]。  

## Print  

借助 Microsoft Edge，可使用多种设备和应用程序来打印网页、PDF 文件或其他内容。  打印到打印机、应用程序或 PDF 时，Microsoft Edge 会将命令和文件信息发送到设备的操作系统。  该信息不会发送给 Microsoft，且所有发送到设备操作系统的数据在完成或取消打印后将立即删除。  若要更改打印目标，请转到 `edge://settings/printing`。  

也可以使用 Microsoft Print to PDF 将网页和文件打印到 PDF，此操作不会将有关该文件的任何数据发送回 Microsoft。  对 PDF 文件所做的任何批注将本地保存到文件。  

## 配置文件  

Microsoft Edge 中的配置文件使你能够将浏览数据分隔到独立的配置文件中。  与一个配置文件关联的数据独立于与其他配置文件关联的数据。  例如，如果你在不同的配置文件中设置了个人收藏夹和历史记录，那么它们就不会与你的工作帐户同步。  

但是，用户可以在 Microsoft Edge 中轻松切换现有配置文件，而无需密码。  如果用户有权访问同一设备，则可以在相同版本的 Microsoft Edge 上创建另一个配置文件，而无需获得当前配置文件所有者的许可。  从 Microsoft Edge 设置中删除配置文件，将永久删除设备上存储的特定配置文件的浏览数据，如浏览历史记录、收藏夹、表单填充数据和密码。  同步到你的帐户的数据可能仍存储在 Microsoft 云中，并且可能会从“[Microsoft 隐私仪表板][MicrosoftAccountPrivacy]”中清除。  

来宾模式是新配置文件的临时实例。  它允许你在不修改已登录配置文件的情况下浏览其他用户的设备。  关闭所有来宾模式窗口后，来宾模式中的浏览数据（如收藏夹、浏览历史记录、密码和表单填充数据）将不会保留。  下载的文件存储在设备上，但下载的历史记录将被删除。  来宾模式可用于浏览 Web，而无需自动登录到其他网站。  Microsoft Edge 不向网站发送任何表明用户在来宾模式下浏览的信息。  使用来宾模式时，收集有关如何使用浏览器和访问网站的诊断数据的权限，是从启动来宾模式会话的 Microsoft Edge 配置文件中获取的。  关闭所有来宾窗口后，特定来宾模式会话的所有浏览数据都将被清除。  

InPrivate 浏览是一种私有浏览模式，在该模式下，不会记住浏览历史记录、下载历史记录、cookie 和网站数据以及表单填充数据。  Microsoft Edge 会保存下载的文件和浏览 InPrivate 时创建的任何新收藏夹。  默认情况下，浏览 InPrivate 时，Microsoft 不会收集有关你所访问的网站的任何信息，因此可改进产品。  你的学校、工作场所或 Internet 服务提供商可能仍然能够看到你的浏览活动。  关闭所有 InPrivate 窗口后，将清除特定 InPrivate 会话的浏览数据。  使用 Windows 输入法编辑器 (IME) 键盘进行输入和墨迹书写时，可能会收集数据以改进语言识别和建议功能。  若要在 InPrivate 和正常浏览窗口中使用 Windows IME 键盘期间停止 Microsoft 收集墨迹书写和输入数据，请打开“开始****” > “设置****” > “隐私****”并选择“墨迹书写和输入个性化****”。  有关 InPrivate 浏览的详细信息，请参阅[浏览 Microsoft Edge 中的 InPrivate][MicrosoftSupport4533513]。  
  

## 大声朗读  

Microsoft Edge 提供大声朗读功能，它向用户朗读网页内容。  若要启动“大声朗读”，请将鼠标悬停在页面上的任意位置，并打开上下文菜单 \（右键单击 \）或打开““设置和更多(...)****” 并选择“大声朗读 ****”。  大声朗读提供了多种语音，可用于阅读网页内容。  如果你使用的是 [Windows 10 上安装][OfficeSupport4c83a8d8748642f78e462b0fdf753130]的语音（在 Windows 10 设置的“时间和语言****”部分下），并想清除本地缓存中以前使用过的所有声音，请转到 `edge://settings/clearBrowserData`。  

当你启动“大声朗读”时，Microsoft Edge 将使用 [Web 语音 API][GithubW3cIncubatorCommunityGroupSpeechApi]。  根据你选择的语音，将使用平台提供的客户端库（例如，特定于你的操作系统的客户端库）或由 Microsoft 认知服务提供支持的服务器端库，将页面内容从文本转换为语音。  如果使用客户端库将内容转换为语音，则不会向 Microsoft 服务器发送任何信息。  如果使用 Microsoft 认知服务（如任何语音名称中的“Online”一词所示）将内容转换为语音，则文本以及随机生成的令牌将发送到 Microsoft。  转换完成后，服务会将音频文件中的口述文本返回到你的设备。  所有数据在从设备传输到 Microsoft 时都会加密，反之亦然。  发送给 Microsoft 的文本和生成的音频文件将在转换发生后立即删除；任何时间段内均不会存储有关你的 Web 内容的其他数据。  

## 发布新功能  

为改进 Microsoft Edge，Microsoft Edge 团队一直在向用户学习。  在学习过程中，某些用户可能会在新功能公开发布之前体验这些新功能。  若要为随机选定的用户启用新功能，Microsoft Edge 会定期向 Microsoft Edge 配置服务发送有关你的操作系统、频道、版本、国家/地区和其他设备配置数据的所需信息。  将使用你的浏览器所特有的可重置标识符发送数据。  数据通过 HTTPS 传输到服务。  这些数据用于接收更新以启用新功能，使 Microsoft Edge 保持最新状态并正常运行，以及改进 Microsoft 产品和服务。  组织还可以使用其他控制和配置。  有关组织的其他控制和配置的详细信息，请参阅 [Microsoft Edge 配置和试验][DeployedgeConfigurationExperiments]。  

作为用户，你无法禁用由组织控制或配置的浏览器更新，但若要控制是否将产品使用情况数据发送到 Microsoft，请转到 `edge://settings/privacy`，在“**帮助改进 Microsoft Edge**”下更改设置。  

若要了解新功能如何影响 Microsoft Edge 和 Microsoft 服务，Microsoft Edge 将发送浏览器特有的可重置标识符，并提供一个功能标记，用于对 Microsoft Edge 和 Microsoft 服务启用的新功能进行编码。  新功能有助于为每个用户构建最佳体验和最佳的浏览器。  功能标记不是 Microsoft Edge 安装所特有的，且在共享同一组启用功能的所有 Microsoft Edge 安装中共享。  Microsoft Edge 将 HTTPS 中的信息发送给 Microsoft 服务。  浏览 InPrivate 或来宾模式时，浏览器不会发送信息。  要阻止发送数据，请转到 `edge://settings/privacy`，然后禁用“通过发送故障报告和有关如何使用浏览器的数据来改进 Microsoft 产品****”设置。  有关如何重置浏览器特有的标识符的详细信息，请参阅“[有关如何使用浏览器的诊断数据](#diagnostic-data-about-how-you-use-the-browser)”部分。  

## 解决导航错误  

如果 Microsoft Edge 检测到 SSL 连接超时、证书错误或可能由强制网络门户（例如，旅馆或机场的 Wi-Fi 网络）导致的其他网络问题，Microsoft Edge 将向 `http://edge.microsoft.com/captiveportal/generate_204` 发送请求并检查响应代码。  如果请求重定向到另一个 URL，Microsoft Edge 将在新选项卡中打开该 URL，假定该 URL 是一个登录页面。  对强制网络门户检测页面的请求为无状态服务，不会记录请求，也不会发送或保存 cookie。  在 Windows 平台上，Microsoft Edge 使用 Windows 强制网络门户服务。  否则，将使用 Microsoft Edge 强制网络门户服务。  若要关闭该服务，请转到 `edge://settings/privacy`，然后禁用“使用 Web 服务来帮助解决导航错误****”设置。  

## 登录和标识  

登录到 Microsoft Edge 可提供更多功能，使浏览器更加高效。  若要无缝登录，首次启动 Microsoft Edge 时，它会尝试从操作系统中检测你的身份。  如果 Microsoft Edge 从操作系统检测到你的标识，但你不希望继续登录 Microsoft Edge，请转到 `edge://settings/profiles`，注销或删除配置文件。  若要登录 Microsoft Edge，未从操作系统检测到你的身份，请转到 `edge://settings/profiles`。  

如果向操作系统添加了新的标识，而你的 Microsoft Edge 配置文件当前尚无标识，则 Microsoft Edge 会将特定标识添加到你的配置文件。  如果你使用 Microsoft 帐户或工作或学校帐户登录 Microsoft Edge，并且在 Windows 10 配置文件上没有标识，则会将特定帐户添加到 Windows 10 配置文件，除非你在登录时明确选择不将其添加到 Windows 10。  

当你首次启动 Microsoft Edge 或登录浏览器时，没有你的明确许可，登录配置文件不会开始同步数据。  

登录到 Microsoft Edge 将启用单一登录（你将自动登录到某些网站，如必应）和其他标识支持的体验（如同步）。如果只需登录到 Microsoft Edge，而不是其他 Microsoft 网站（如[必应][|::ref4::|Main]），则可以注销特定网站。  Microsoft Edge 将创建一个注销 cookie，告知 Microsoft Edge 不要登录到特定网站来方便日后访问。  若要使用用户名和密码再次登录到特定网站或清除 cookie ，请转到 `edge://settings/privacy`。  有关清除浏览数据的详细信息，请参阅[查看和删除 Microsoft Edge 中的浏览器历史记录][MicrosoftSupport10607]。  

若要阻止任何标识与 Microsoft Edge 关联，请删除 Microsoft Edge 配置文件或注销 Microsoft Edge。  若要从设备中删除与 Microsoft Edge 配置文件关联的所有数据，必须删除 Microsoft Edge 配置文件。  删除所有数据不会删除以前同步的与该标识相关联的数据。  

macOS 上 Microsoft Edge 中的标识在 Microsoft 应用间共享。  可使用共享标识登录 Microsoft 应用，而无需在设备上登录到其他 Microsoft 应用时单独输入凭据。  在 macOS 上，系统不会根据你在其他 Microsoft 应用中的身份验证状态使你自动登录到 Microsoft Edge。  尝试登录到 Microsoft Edge 时，可使用设备上来自其他 Microsoft 应用的凭据无缝登录到 Microsoft Edge。  同样，当你登录到 Microsoft Edge 的帐户时，如果尝试登录到其他 Microsoft 应用，可使用 Microsoft Edge 凭据来帮助登录设备上的其他 Microsoft 应用，而无需再次输入凭据。  

使用来宾模式或 InPrivate 时，无法登录到 Microsoft Edge。  

## SmartScreen  

SmartScreen 旨在帮助你安全浏览 Web。  访问网站或下载文件时，SmartScreen 会检查 URL 或文件的信誉。  如果 SmartScreen 确定网站或文件有恶意，则会阻止你访问网站或下载文件。  

:::image type="complex" source="./media/whitepaper-media/smart-screen.png" alt-text="SmartScreen" lightbox="./media/whitepaper-media/smart-screen.png":::
   SmartScreen  
:::image-end:::  

浏览 Web 时，SmartScreen 将网站和下载分类为主要流量、危险或未知。  主要流量是被 SmartScreen 确定为可信的网站。  如果转到标记为危险的网站，SmartScreen 将立即阻止你访问此网站。  转到未知网站时，SmartScreen 会检查其信誉以确定是否应访问此网站。  

SmartScreen 采用三种类型的信誉检查。  第一种是，SmartScreen 对照本地列表检查你访问的网站的 URL，确定该网站是主要流量的一部分还是已知危险网站。  访问主要流量网站时，SmartScreen 不会向 SmartScreen 服务发送 URL。  如果 URL 位于危险网站的本地列表中，SmartScreen 就会阻止它，以防加载恶意 Web 内容的任何部分。  Microsoft Edge 定期将更新的主要流量和危险网站列表下载到设备。  第二种类型的 URL 检查是对 SmartScreen 服务的异步信誉检查。  SmartScreen 会对所有未分类为主要流量的 URL 执行检查。  Microsoft Edge 将 URL、网站相关信息、设备特有的标识符和常规位置信息传递到 SmartScreen 服务，以确定网站的安全性。  Microsoft Edge 提供的信息使服务能够识别新的危险网站，并随时了解最新安全威胁。  URL 检查的结果本地存储在设备上，并且会在浏览器会话结束时自动清除。  所有 SmartScreen 服务请求均可使用 HTTPS 加密进行。  

第三种信誉检查类型是，SmartScreen 检查下载的文件，以防止对设备造成损害。  下载完成后，SmartScreen 会同步执行二进制文件信誉检查。  Microsoft Edge 将有关文件的信息（如文件哈希、文件名、下载 URI 和设备特有的标识符）发送到 SmartScreen，以执行信誉检查。  所有 SmartScreen 请求均可使用 HTTPS 加密进行。  SmartScreen 服务会将检查结果发送回来，以便文件完全下载或不下载。  这些结果将本地存储在设备上。  

SmartScreen 服务存储有关信誉检查的数据，并生成已知恶意 URL 和文件的数据库。  此数据存储在安全的 Microsoft 服务器上，仅用于 Microsoft 安全服务。  数据不会用于以任何方式识别或瞄准你。  清除浏览缓存将清除所有本地存储的 SmartScreen URL 数据。  清除下载历史记录将删除本地存储的任何有关文件下载的 SmartScreen 数据。  

默认情况下，Microsoft Edge 将启用 SmartScreen。  若要禁用 SmartScreen，请转到 `edge://settings/privacy`，在“**服务**”下禁用“**Microsoft Defender SmartScreen**”设置。  对于与设备上 Microsoft Edge 安装相关的所有配置文件，此设置相同。  此设置不会跨设备同步。  此设置适用于 InPrivate 浏览和来宾模式。  如果设备是通过组织设置的组策略进行管理的，则设置会反映在 Microsoft Edge 中。  若要查看设置，请转到 `edge://settings/privacy`。  有关 SmartScreen 的详细信息，请参阅 [SmartScreen：FAQ][MicrosoftSupport17443]。  

此外，SmartScreen 还可以检查下载文件的 URL，确定是否有任何内容可能归类为不需要的应用。  阻止可能不需要的应用有助于提供更高效、高性能和更愉悦的 Windows 体验。  此设置默认情况下处于禁用状态，并且仅在 Windows 10 设备上可用。  若要启用该功能，请转到 `edge://settings/privacy`，启用“**阻止可能不需要的应用**”设置。  有关如何对可能不需要的应用进行分类的详细信息，请参阅[可能不需要的应用程序 (PUA)][WindowsSecurityThreatProtectionIntelligenceCriteriaPotentiallyUnwanted]。  有关如何配置设置的详细信息，请参阅[检测并阻止可能不需要的应用程序][WindowsSecurityThreatProtectionWindowsDefender]。  

## 语音识别

若要将语音转换为文本，Microsoft Edge 支持 [Web 语音 API][GithubW3cIncubatorCommunityGroupSpeechApi]。  如果网站所含 Web 功能需要将语音捕获和转换为文本并请求访问你的麦克风，则 Microsoft Edge 会将捕获的音频发送到 Microsoft 服务，将其转换为文本。  录制的音频通过与 Microsoft Azure 认知服务的安全 HTTPS 连接使用随机生成的令牌发送。  不会出于任何目的存储录制的音频内容。  文本将发送回你的设备，然后发送到网站。  

若要关闭将语音转换为文本，可以拒绝任何提示许可的站点的麦克风访问。  若要关闭所有网站的麦克风权限，请转到 `edge://settings/content/microphone`。  

## 拼写检查  

当你在浏览器中输入时，Microsoft Edge 将检查拼写。  已在设备本地完成拼写检查服务；Microsoft Edge 不会将有关你输入内容的信息发送到 Microsoft 进行拼写检查。  若要关闭该功能，请转到 `edge://settings/languages`，然后在“检查拼写****”下禁用每种语言的设置。  

向 Microsoft Edge 添加新语言后，浏览器将使用 HTTPS 将新语言字典下载到设备。  该字典用于内置拼写检查服务。  从 Microsoft Edge 设置中删除语言将从设备中删除字典。  来宾模式不使用来自配置文件或任何添加的语言的自定义字典。  若要添加或删除本地字典中的单词，请转到 `edge://settings/languages`，在“检查拼写****”下选择“添加或删除单词****”。  

## 建议类似网站  

为了帮助解决地址栏中导致网站错误的 URL 拼写错误，Microsoft Edge 可能会建议使用正确的 URL。  出现网站导航错误时，Microsoft Edge 会将 Web 地址的域发送到 Microsoft 服务，以建议更正的 URL。  Microsoft Edge 不包含域中的标识符或令牌。  如果服务找到建议，它将返回建议的 URL。  Microsoft 将存储不正确的域和建议的域以帮助改进服务。  为了帮助导航到正确的网站，默认情况下将启用该功能。  若要关闭该功能，请转到 `edge://settings/privacy`，然后在“服务****”下禁用“建议在找不到网站时显示类似网站****”设置。  

## Sync  

使用 Microsoft 帐户登录到 Microsoft Edge，可在所有登录的 Microsoft Edge 版本之间同步浏览数据。  可同步收藏夹、设置、表单填充数据（地址和其他）、密码、扩展和收集。  必须允许在 Microsoft Edge 中启用同步，并且可能会单独启用或禁用每个同步的数据类型。  收藏夹包括先前在旧版 Microsoft Edge 中设置的任何选项卡，它与其他收藏夹一起同步。  从 Microsoft Edge 的一个已登录版本中删除或修改收藏夹或其他数据，将同步到已启用同步的 Microsoft Edge 的所有其他已登录版本。  若要管理同步配置，请转到 `edge://settings/profiles/sync`。  你的同步设置可能由组织进行管理。

:::image type="complex" source="./media/whitepaper-media/sync.png" alt-text="Sync" lightbox="./media/whitepaper-media/sync.png":::
   Sync  
:::image-end:::  

若要同步到函数，需要发送额外的设备连接和配置数据来提供同步体验，如设备名称、品牌和型号。  可从“[Microsoft 设备仪表板][MicrosoftAccountDevices]”中删除数据。  若要管理同步收藏夹，请转到 `edge://favorites`。  若要管理所有其他数据类型，请转到 `edge://settings/profiles`。  

在浏览器和 Microsoft 服务器之间传输时，将通过 HTTPS 加密传输所有同步数据。  同步的数据同样以加密状态存储在 Microsoft 服务器中。  敏感数据类型（如地址和密码）将在同步前在设备上进一步加密。  如果使用工作或学校帐户，所有数据类型在同步之前都会使用 Microsoft 信息保护进一步加密。  将存储所有其他同步数据类型，直至你删除数据、删除帐户或者帐户处于非活动状态。  帐户 ID 附加到所有同步数据，因为需要使用 ID 才能跨多个设备执行同步。 

InPrivate 和来宾模式浏览数据不会同步到你的 Microsoft 帐户。  但是，在 InPrivate 会话过程中创建的收藏夹将同步到已启用同步的 Microsoft Edge 已登录版本。  

## 跟踪防护  

Microsoft Edge 旨在检测和阻止已知跟踪器。  用户可以从三个跟踪防护级别中进行选择：“基本”、“平衡”和“严格”。  为了保护用户隐私，默认情况下选择“平衡”。  Microsoft Edge 使用已知跟踪器的开源列表，在页面上加载任意跟踪器之前对其进行检测。  列表更新时，会定期将列表下载到设备。  出于统计目的，被阻止的跟踪器数和这些跟踪器名称将本地存储在设备上。  若要清除数据，请转到 `edge://settings/privacy/blockedTrackers`。  检测和阻止跟踪器在设备本地上进行。  若要禁用跟踪防护，请转到 `edge://settings/privacy`。  有关跟踪防护的详细信息，请参阅[了解 Microsoft Edge 中的跟踪防护][MicrosoftAccount4533959]。  

可使用以下组策略“[启用 Microsoft Edge 中的组件更新][DeployedgePoliciesComponentupdatesenabled]”禁用列表更新。  

:::image type="complex" source="./media/whitepaper-media/tracking-prevention.png" alt-text="跟踪防护" lightbox="./media/whitepaper-media/tracking-prevention.png":::
   跟踪防护  
:::image-end:::  

## 翻译  

在 Microsoft Edge 中，你可以浏览 Web 并将网页翻译为你选择的语言。  内置翻译功能使用设备上的一项服务，可对页面的随机部分进行采样，以检测原始语言。  如果检测到的语言不是其中一种默认语言，则 Microsoft Edge 会将该网页翻译为所显示的语言或你选择的其他语言。  Microsoft Edge 不会在未经你允许的情况下翻译网页。  你也可以通过右键单击页面，然后选择“翻译****”来翻译网页。  为了翻译网页，Microsoft Edge 通过安全 HTTPS 连接将页面的内容和随机生成的令牌发送到 Microsoft Azure 翻译服务。  存储的页面内容不用于任何目的。  若要停止 Microsoft Edge 提供的网页翻译功能，请转到 `edge://settings/languages`，然后禁用“主动翻译非你所读语言的页面****”设置。  

## Web 应用和已固定网站  

Microsoft Edge 可用于安装网站开发人员制作的 Web 应用，并固定你最喜爱的网站。  

固定网站时，会将其添加到任务栏或快捷栏。  数据本地存储在设备上。  对于某些网站，有关网站是否已固定的信息将与网站共享，以便该网站知悉不进行固定提示。  可通过任务栏或快捷栏管理已固定网站。  已固定网站在 Microsoft Edge 窗口中打开，并使用与特定版本的 Microsoft Edge 相同的网站权限和诊断数据设置。  

## WebView

Microsoft Edge WebViews 允许应用开发人员在 Windows 10 和 Windows 7 上的本机应用程序中托管 Web 内容。  托管 Microsoft Edge WebView 的应用程序可能会向 Microsoft 发送诊断数据，例如，如何使用 Microsoft Edge Web 平台和你在应用程序中访问的网站。  若要启用诊断数据收集，请转到 `edge://settings/privacy`，在“帮助改进 Microsoft Edge****”下启用该设置。  若要在 Windows 10 上禁用 Microsoft Edge 故障诊断数据收集，请打开“开始****” > “设置****” > “隐私****”并选择“诊断和反馈****”。  若要关闭所有其他平台的诊断数据收集，请在正常浏览会话中转到 `edge://settings/privacy`，禁用“通过发送故障报告和有关如何使用浏览器的数据来改进 Microsoft 产品****”和“通过发送在 Microsoft Edge 中访问的网站信息来实现高效搜索和改进 Microsoft 产品****”设置。  托管 Microsoft Edge WebView 的应用程序可能会收集由开发人员的数据收集管理以及相关隐私策略所管理的其他数据。  

## 为提高产品和服务质量而访问的网站  

如果你选择改进搜索和其他 Microsoft 产品和服务，Microsoft Edge 将向 Microsoft 发送有关你访问的网站的信息。  将聚合诊断数据，用于为所有用户改进 Microsoft 产品和服务，而不是收集或存储在你的 Microsoft 帐户中。  在 Microsoft Edge 中发送有关你访问的网站的信息，有助于 Microsoft 了解网站的加载速度，并提高搜索结果的相关性。  

诊断数据包括你访问的页面的 URL、网站指标、页面标题、页面的访问方式、有关页面内容的信息，以及有关页面导航的其他相关信息。  某些诊断数据附加了设备特有的标识符。  否则，诊断数据与浏览器特有的可重置标识符相关联。  标识符不包含你的个人信息。  Microsoft Edge 团队通过限制数据访问和/或清除个人身份信息来尊重诊断数据的敏感性。  若要在 Windows 10 设备上重置浏览器特有的标识符，请打开“开始****” > “设置****” > “隐私****” > “诊断和反馈****”，在“诊断数据****”下，将“完整****”更改为“基本****”。  在其他平台上，若要为你的浏览器生成一个新的可重置标识符，请转到 `edge://settings/privacy`，然后将“通过发送在 Microsoft Edge 中访问的网站信息来实现高效搜索和改进 Microsoft 产品****”设置从“启用****”更改为“禁用****”。  对于由组织设置的组策略管理的设备，重置功能可能有所不同。  

对于 Windows 10 上的 Microsoft Edge，该设置取决于你的 Windows 诊断数据设置。  若要查看 Microsoft Edge 中的反射设置，请转到 `edge://settings/privacy` 的“隐私****”和“服务****”下方。  若要更改 Windows 设置，请打开“开始****” > “设置****” > “隐私****”并选择“诊断和反馈****”。  在所有其他平台上，若要控制诊断数据收集，请转到 `edge://settings/privacy`，然后启用或禁用“通过发送在 Microsoft Edge 中访问的网站信息来实现高效搜索和改进 Microsoft 产品****”设置。  对于与设备上 Microsoft Edge 安装相关的所有配置文件，此设置相同。  此设置不会跨设备同步。  若要查看设备是否是由组织设置的组策略管理的，请转到 `edge://settings/privacy`。  

诊断数据在传输过程中加密，并以原始格式存储在安全的 Microsoft 服务器上长达 30 天。  去识别化并聚合诊断数据后，将删除原始诊断数据。  去识别化和聚合的诊断数据最多可存储 2 年，以继续改进 Microsoft 产品和服务。  由于不会从 Microsoft 帐户中收集或保存诊断数据，因此可能无法从“[Microsoft 隐私仪表板][MicrosoftAccountPrivacy]”查看或删除诊断数据。  在 Windows 10 设备上，若要请求删除与设备相关联的诊断数据，请打开“开始****” > “设置****” > “隐私****” > “诊断和反馈 **”**，然后在“删除诊断数据**** 下选择“删除****”。  在其他平台上，诊断数据将被删除或完全聚合，并在 30 天内进行匿名处理。  

若要查看 Windows 10 上收集的数据，请打开“开始****” > “设置****” > “隐私****”并选择“诊断和反馈****”，然后选择“查看诊断数据****”。  若要在其他平台上查看数据，请转到 `edge://data-viewer`。  在其他平台上，若要启用诊断数据查看器功能，请转到 `edge://settings/privacy`，然后启用“通过发送在 Microsoft Edge 中访问的网站信息来实现高效搜索和改进 Microsoft 产品****”设置。  

浏览 InPrivate 或处于来宾模式时，不会发送诊断数据。  

## Windows Defender 应用程序保护  

Windows Defender 应用程序防护 (WDAG) 是一项适用于组织的功能。  当 Windows Defender 应用程序防护处于启用状态时，Microsoft Edge 将在独立容器内打开不受信任的网站，以保护组织中的资源免受恶意网站或钓鱼攻击。  该功能仅通过组织管理的组策略打开，并且仅适用于 Windows 10 的最新版本。  WDAG 收集有关在独立容器中打开不受信任的网站的产品改进诊断数据（例如打开新应用程序防护窗口所需的时间）。  

在你允许的情况下，WDAG 还会收集你如何使用浏览器的信息以及所访问的网站的信息。  若要在 Windows 10 上禁用 Microsoft Edge 故障诊断数据收集，请打开“开始****” > “设置****” > “隐私****”并选择“诊断和反馈****”。  若要禁用所有其他平台的诊断数据收集，请在正常浏览会话中转到 `edge://settings/privacy`，禁用“通过发送故障报告和有关如何使用浏览器的数据来改进 Microsoft 产品****”和“通过发送在 Microsoft Edge 中访问的网站信息来实现高效搜索和改进 Microsoft 产品****”设置。  

## Windows 信息保护  

Windows 信息保护 (WIP) 可帮助防止意外泄漏公司信息。  仅可通过组织管理的组策略供组织使用。  对标识为企业资产的网站启用 WIP。  通过地址栏中的“管理”图标标识属于企业资产的网站。  WIP 强制执行某些功能，例如防止从浏览器复制和粘贴或将某些文件上传到组织之外的网站。  

:::image type="complex" source="./media/whitepaper-media/w-i-p.png" alt-text="Windows 信息保护" lightbox="./media/whitepaper-media/w-i-p.png":::
   Windows 信息保护  
:::image-end:::  

如果你的 Microsoft Edge 版本启用了 WIP，该浏览器将收集事件日志，并将其发送给你的组织。  如果启用了 WIP，则不能选择退出数据收集。  WIP 只适用于 2016 年 8 月或更高版本的 Windows 10 版本。  有关由 WIP 捕获的事件日志的详细信息，请参阅[如何收集 Windows 信息保护 (WIP) 审核事件日志][WindowsSecurityInformationProtectionCollectAuditEventLogs]。  

## 谢谢！  

Microsoft Edge 可通过 [Chromium][ChromiumMain] 开源项目和其他开源软件实现。  若要查看所有软件积分，请转到 `edge://credits`。  [Google Chrome 隐私白皮书][GoogleChromePrivacyWhitepaper]被用作收集 Chromium 开源项目相关信息的来源。  

<!--Microsoft Edge is committed to protecting and respecting your privacy while giving you the transparency and control you deserve.  Reach out to [@MSEdgeDev][TwitterMsedgedev] on Twitter or submit feedback by opening **Settings and more (...)** > **Help and feedback** and selecting **Send feedback** with questions or comments.  -->  

## 与 Microsoft Edge 团队联系  

Microsoft Edge 团队将始终倾听客户的意见，且非常重视客户的反馈。  若要在 Microsoft Edge 中提供反馈，请打开“设置和更多****” > “帮助和反馈****”并选择“发送反馈****”。  对于渐进式 Web 应用 (PWA)，请打开“设置和更多(...)****”并选择“向 Microsoft 发送反馈****”。  必须提供有关反馈的详细信息，但可以选择是否提供其他信息。  如果从 Microsoft Edge 配置文件检测到电子邮件，它将预填充你所在网站的当前 URL 和相关诊断数据。  诊断数据可能包含有关已启用的 Microsoft Edge 功能和浏览器使用情况的数据。  也可以选择将屏幕截图、设备中的文件和浏览器记录包含在内。  提供的可选屏幕截图、文件或记录可能包含个人身份信息。  数据仅用于诊断和产品改进目的。  

用户反馈将通过 HTTPS 安全发送到 Microsoft，并存储在安全的 Microsoft 服务器上。  如果包含电子邮件地址，且 Microsoft Edge 隐私设置中启用了“通过发送故障报告和有关如何使用浏览器的数据来改进 Microsoft 产品****”设置，则设备上的浏览器安装所特有的标识符将与你的反馈相关联。  所有诊断数据（包括诊断日志、记录和附件）最多保存 30 天。  剩下的反馈数据（包括可选的屏幕截图）最多保存 15 个月。  如果你提供了含反馈项的电子邮件，则[请求][MicrosoftConcernPrivacy]删除反馈。  

<!-- links -->  

[DeployedgeConfigurationExperiments]: /deployedge/edge-configuration-and-experiments "Microsoft Edge 配置和实验 | Microsoft Docs"  
[DeployedgePoliciesComponentupdatesenabled]: /deployedge/microsoft-edge-policies#componentupdatesenabled "ComponentUpdatesEnabled - Microsoft Edge - 策略 | Microsoft Docs"  
[DeployedgeUpdatePoliciesUpdate]: /deployedge/microsoft-edge-update-policies#update "更新 - Microsoft Edge - 更新策略 | Microsoft Docs"  
[DeployedgeEnterprisePrivacySettings]: /deployedge/microsoft-edge-enterprise-privacy-settings "配置 Microsoft Edge 策略以支持企业隐私 | Microsoft Docs"  
[DeployedgePrivacyOverviewControls]: /deployoffice/privacy/overview-privacy-controls "Microsoft 365 企业应用版的隐私控制概述 | Microsoft Docs"  

[InternetExplorer11DeployGuideCollectDataEnterpriseSiteDiscovery]: /internet-explorer/ie11-deploy-guide/collect-data-using-enterprise-site-discovery "使用“企业网站发现”收集数据 | Microsoft Docs"  

[PlayreadyOverviewSimpleEndSystem]: /playready/overview/simple-end-to-end-system "简单的端到端系统 | Microsoft Docs"  

[WindowsPrivacyConfigureDiagnosticDataOrganization]: /windows/privacy/configure-windows-diagnostic-data-in-your-organization "在组织中配置 Windows 诊断数据 | Microsoft Docs"  

[WindowsSecurityInformationProtectionCollectAuditEventLogs]: /windows/security/information-protection/windows-information-protection/collect-wip-audit-event-logs "如何收集 Windows 信息保护 (WIP) 审核事件日志 | Microsoft Docs"  
[WindowsSecurityThreatProtectionIntelligenceCriteriaPotentiallyUnwanted]: /windows/security/threat-protection/intelligence/criteria#potentially-unwanted-application-pua "可能不需要的应用程序 (PUA) - Microsoft 识别恶意软件和可能不需要的应用程序的方式 | Microsoft Docs"  
[WindowsSecurityThreatProtectionWindowsDefender]: /windows/security/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus "检测并阻止可能不需要的应用程序 | Microsoft Docs"  

[BingMain]: https://bing.com "必应"  

[ChromiumMain]: https://www.chromium.org "Chromium 项目"  

[GithubW3cIncubatorCommunityGroupSpeechApi]: https://wicg.github.io/speech-api "Web 语音 API 草稿报告 | W3C Incubator 社区组" 

[GoogleChromePrivacyWhitepaper]: https://www.google.com/chrome/privacy/whitepaper.html "Google Chrome 隐私白皮书"  

[MicrosoftAccountDevices]: https://account.microsoft.com/devices "设备 | Microsoft 帐户"  
[MicrosoftAccountFamilyMain]: https://account.microsoft.com/family "家庭 | Microsoft 帐户"  
[MicrosoftAccountPrivacy]:  https://account.microsoft.com/privacy/ "隐私 | Microsoft 帐户"  
[MicrosoftAccountPrivacyAdSettings]: https://account.microsoft.com/privacy/ad-settings "添加设置 - 隐私 | Microsoft 帐户"  

[MicrosoftConcernPrivacy]: https://www.microsoft.com/concern/privacy "报告隐私问题 | Microsoft"  
[MicrosoftLicensingProductProducts]: https://www.microsoft.com/licensing/product-licensing/products "许可条款 - Microsoft 批量许可"  

[MicrosoftSupport10607]: https://support.microsoft.com/help/10607 "在 Microsoft Edge 中查看和删除浏览器历史记录 | Microsoft Edge 支持"  
[MicrosoftSupport12413]: https://support.microsoft.com/help/12413 "什么是 Microsoft 家庭组？| Microsoft 帐户支持"  
[MicrosoftSupport17443]: https://support.microsoft.com/help/17443 "SmartScreen：FAQ | Microsoft Edge 支持"  
[MicrosoftSupport4468236]: https://support.microsoft.com/help/4468236 "Windows 10 中的诊断、反馈和隐私 | Microsoft 隐私支持"  
[MicrosoftSupport4468240]: https://support.microsoft.com/help/4468240 "Windows 10 位置服务和隐私 | Microsoft 隐私支持"  
[MicrosoftSupport4532583]: https://support.microsoft.com/help/4532583 "用于个性化广告和体验的 Microsoft Edge 浏览历史记录 | Microsoft 隐私支持"  
[MicrosoftSupport4533513]: https://support.microsoft.com/help/4533513 "在 Microsoft Edge 中浏览 InPrivate | Microsoft Edge 支持"  
[MicrosoftAccount4533959]: https://support.microsoft.com/help/4533959 "了解 Microsoft Edge 中的跟踪防护 | Microsoft 隐私支持"  

[OfficeSupport4c83a8d8748642f78e462b0fdf753130]: https://support.office.com/article/4c83a8d8-7486-42f7-8e46-2b0fdf753130 "为沉浸式阅读器、阅读模式和大声朗读下载语音 | Office 支持"  

[W3cEncryptedMediaPrivacy]: https://w3.org/TR/encrypted-media#privacy "11. 隐私 - 加密媒体扩展 | W3C"  
[W3cGeolocationApiMain]: https://w3.org/TR/geolocation-api "地理位置 API 规范第 2 版 | W3C"  

[TwitterMsedgedev]: https://www.twitter.com/MSEdgeDev "Microsoft Edge Dev | Twitter"  
